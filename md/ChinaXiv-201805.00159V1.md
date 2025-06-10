# 一种基于多尺度带通滤波的洁化算法与GPU实现

梅盈14，邓辉³，张晓丽2,1，王锋1,3,4，陈腾达²(1．中国科学院云南天文台，云南昆明650011；2.昆明理工大学，云南昆明 650500；3.广州大学天体物理中心，广东广州510006；4.中国科学院大学，北京 100049)

摘要：中国新一代频电频谱日像仪-明安图射电频谱日像仪（Mingantu SpectralRadioheliograph，MUSER）以高时间、高空间、高频率分辨率工作在0.4GHz\~15GHz，为太阳爆发活动初始能量释放区的物理过程、太阳电子加速等研究开辟了新的窗口。高性能高质量太阳成像算法是MUSER数据处理流水线至关重要的研究内容。参考法国墨东天文台太阳干涉阵的数据处理方法，系统讨论分析了多尺度（Multi-Scale）CLEAN算法，给出了适用于MUSER的多尺度CLEAN算法参数，并重点讨论了算法的GPU并行。实验结果表明，改进的多尺度CLEAN在算法效率上比基于GPU实现的HogbomCLEAN提高了近3倍，有效提高了整个MUSER数据处理流水线的性能。

关键词：多尺度洁化；射电成像；图形处理器中图分类号：TP274文献标识码：A文章编号：1672-7673（2018）03

射电观测是研究太阳剧烈活动的重要探测手段。建于中国明安图的螺旋天线阵列-明安图射电频谱日像仪（Mingantu Spectral Radioheliograph，MUSER）在 400MHz\~15GHz 的584个频点上对太阳进行高分辨率成像，其观测将填补日本野边山日像仪（2个频点，17GHz,34GHz）、法国南茜日像仪（5个频点，150\~450MHz）、俄罗斯伊尔库茨克射电日像仪（5.7GHz）等在厘米分米波段的空白区域，对太阳活动及对人类影响的研究起到重要作用[1]。

明安图射电频谱日像仪分为低频阵（MUSER-I,400MHz\~2GHz）和高频阵（MUSER-II,2GHz\~15GHz），其高时间、高空间和高频率分辨率给数据处理系统提出了较大的挑战。高频阵和低频阵的数据接收机每3ms分别接收一次包含16通道的观测数据。在后续的数据处理过程中，如何高效地获取高质量的太阳图像成为数据处理系统的关键问题。

射电干涉阵成图的主要过程包含加权（Weighting）、网格化（Gridding）、傅里叶变换，退卷积等主要步骤，其中退卷积是对脏图进行洁化的过程，是成像过程中最耗时的部分。对日像仪成像来说，退卷积过程也是整个管线设计中最令人关注的问题。本文在细致调研相关工作的基础上，进一步对射电干涉阵成像中的多尺度退卷积方法进行了讨论，给出了相应的实现方法。

# 1．相关研究工作

射电干涉成像的基本原理是天空实际亮度是可见度函数的傅里叶变换。由于在实际观测过程中UV覆盖的不完全性，采样函数是离散的。自1974年Hogbom提出CLEAN算法的思想后，CLEAN算法得到了极大的发展并在射电望远镜的图像重建算法中得到了广泛的应用。经典HogbomCLEAN算法的关键是为天空实际亮度提供一个模型（），迭代寻找亮度的峰值位置，并如（1）式进行叠加，其中参数为迭代过程中的峰值亮度，为峰值亮度的位置，由残留图像的峰值亮度确定[2-3]。（2）式中的为脏图亮度，为脏束，为公式（1）计算的出的叠加后的亮度值，为残图的亮度，标记迭代次数。

Hogbom CLEAN 算法的一些变种算法，如 Clark,Cotton-Schwab 算法、最大熵算法

MEM（the Maximum Entropy Method，MEM）随后被提出。Steer Clean 算法被用于日本野边山日像仪的成像，其洁化效率是Hogbom算法的近10

[4]。然而，基本的Hogbom CLEAN 算法由于在处理点源和展源上表现的优势，一直被广泛使用。

但随着新一代射电干涉仪的不断发展，在确保基本CLEAN算法的简单性和信噪比的前提下，多尺度成为提高效率的方法之一。Multi-Resolution CLEAN,Multi-Scale MaximumEntropy,Wavelets CLEAN等多尺度算法有效提高了洁化效率，但存在尺度大小固定和计算代价高等问题。

Comwell于2008年提出的Multi-ScaleCLEAN[3]算法被认为算法直接且具有稳定性和收敛性好等特点。Multi-ScaleCLEAN为减少算法的迭代次数，提高算法的稳定性，采用多个不同尺度大小的卷积核与脏图进行卷积，得到多个卷积图像，在多个图像中寻找全局亮度峰值。Multi-ScaleCLEAN算法的基本流程如下：

(1） 选取不同的尺度大小，与脏图进行卷积，得到卷积后的系列图像；  
(2) 寻找全局亮度最大点，记录亮度最大点的位置和所在的尺度大小；  
(3) 计算步骤（2）中的尺度与脏束的卷积，再乘以增益值，存储计算结果及尺度大小；  
(4) 从（1）中所有的卷积图像中减去（3）的计算结果；  
(5) 重复以上4个步骤直至到达循环阈值或达到预设循环次数；  
(6) 将（3）中存储的结果与洁束卷积并加上参与图得到最终的洁图。

为了控制算法的迭代次数，提高图片质量，Multi-ScaleCLEAN算法需要指定不同尺度的卷积图像不同的权值，每次迭代循环结束后，残图需要乘以所在尺度的权值来增加或减少亮度幅值。经过系列实验，（3）式中权值被认为是较合适的参数值[3]。，(3)其中，为权值； $\mathbf { \Delta } _ { a }$ 为当前尺度大小；为最大尺度大小；为权重参数。

为了减小迭代算法对增益的依赖，Cormwell选择抛物线函数作为Multi-ScaleCLEAN的卷积核函数如下：

# (4)

其中，为球面波函数； $( x , y$ 为像素点的位置坐标）；为尺度大小。当式中时， $m ( r , a )$ 对应Högbom CLEAN 中的 Dirac 。

由于高斯卷积核与（4）式给出的卷积核函数仅在较高动态范围下存在较小的差异，一般来说，Comwell采用不同尺度的高斯卷积核。以洁束大小为基准，卷积核大小选取常用的等比数列，即依次取洁束大小的1、2、4、8倍。

为进一步提高处理速度，近几年利用图形处理器技术加快退卷积处理成为主要的方法，如基于图形处理器的网格化算法使得w-projection的效率较中央处理器提高近百倍15；项目组在前期基于图形处理器的Hogbom CLEAN算法较中央处理器下的 Hogbom效率提高了十倍以上。但从Cormwell提出的多尺度CLEAN算法来看，其并行实现存在较大的难度。因为搜索最大值过程虽然可以并行，但需要利用找出的最大值要同时在所有尺度的图像中退卷积，这意味着一个尺度的数据处理必须与其它尺度的数据处理相交叉，影响了并行的实现。

# 2．基于频域的多尺度洁化

# 2.1基本思想

参考Comwell洁化方法，要加快洁化的效率，关键是能够同时进行洁化。实际上，由于 HogbomClean的基本原理，洁化迭代的过程始终是串行的，要并行的唯一可能性，是同时能够独立地进行多个洁化迭代。

法国默东天文台太阳干涉阵与MUSER $$ 样，也是 $$ 个太阳专用的射电干涉阵。其数据处理采用了基于频率带通滤波的多尺度洁化方法。该方法基于两个简化：（1）没有过

多的展源存在；（2）空间尺度中只有相对较窄的谱。对于太阳观测来说，完全可以满足这两个简化需要。该方法与Cormwell多尺度洁化方法有一定的相似性，但更易于并行实现。

参考法国默东天文台的洁化思想，结合明安图射电频谱日像仪的天线分布情况和最长基线情况，最终在本文实现的算法基本原理如下：

-（1）在频域uv平面上，构建一系列连续的带通滤波器F(u,v)，k为滤波器编号，滤波器的半径以2的倍数增长。不同的滤波器对应着不同的空间尺度；与法国不同，在实现时每次将计算最长基线和相应的uv分布，反过来计算相应的滤波器带通频率。

-（2）通过滤波器，将原来的稀疏UV分布D(u,v)进一步拆分为若干个不同尺度的独立分布，即：，

（3）对于一个不同尺度的uv分布，通过逆傅里叶变换（FT）得到脏图：，然后进行常规的洁化处理；

（4）最后的洁图等于各尺度洁图的累加。

# 2.2尺度的考虑

从上述的基本实现原理可见，合适的带通滤器器数量是整个算法的关键。在法国默东太阳干涉阵数据处理中，已经开展了前期的研究，共采用子-5个滤波器。在明安图射电频谱日像仪数据处理中，也借鉴了相同的方法，但进一步做了改进：即根据太阳方位与高度位置，计算实时的UV分布，然后根据最远的UV点位置，动态计算每个滤波器覆盖的频率。在MUSER成图过程中，滤波器一共-5个，Fe到F4，不同尺度的UV滤波设计见图1。横坐标为频率范围，单位为(动态计算的最长基线除以60，60为自定义数据)，由于在日像仪中UV覆盖对称，UV的频率范围相同，在图中用 $-$ 条曲线表示，对应的UV平面如图2。

根据5个不同尺度大小，将脏图分成不同的频率段，随着k值增大，尺度依次减小，直到覆盖所有的UV值。当 $\scriptstyle \mathcal { k } = 0$ 时，滤波器为高斯滤波。其尺度为最长UV的20%，从成像来看，这也是最大的尺度。k-1、2、3、4时，滤波器在频率域呈现一个环状，实现一个带通滤波。无论分成多少级，但本质上要确保这些滤波器的和所合成的滤波器在频率上是连续的，覆盖全部UV点，如图1和图2-中的最后一张图。在使用高斯滤波的情况下，最终合成的滤波器在边缘逐渐减小的滤波性质，正好减小了由于较大的UV处的稀疏导致的成图不可靠信息。

![](images/e96f46abcc3e01906ae450cfaba71679fa50a76faeb5746a56ff64b4de427470.jpg)  
图1滤波器设计

ig.1 Filters profiles along u(-) and v(-) axes

![](images/da70da7434bfa38d9bb6e0e10ce615a13a652ed67283133d0982c71b327051c9.jpg)  
图2UV滤波器设计 Fig. 2Filters in the uv-plane according to Figure 2.

# 3．算法的图形处理器实现及效率

# 3.1图形处理器实现

明安图射电频谱日像仪的成图的图形处理器实现采用-GPU-CUDA架构，采用Python编程语言，PyCUDA，Seikit-CUDA-作为CUDA并行编程接口库。实现了数据处理的单机命令行模式及分布式运行模式，其中数据预处理（数据格式转换f78，相位校准，异常数据标记等）在中央处理器环境下运行，成图及洁化在图形处理器环境下运行，包含8台服务器的高性能计算机群（CPUs+GPUs）已在观测站搭建好。成像流程图如图-3，其中MUSER Multi-Seale CLEAN-算法描述如表1。以低频阵观测数据“2015-11-0104:08:49.354161240 (UTC),1.7125 GHz,右旋”为例，最终洁化图像如图4（a）。在实验过程中，CASA用于验证数据处理各个阶段的正确性。将数据处理系统生成的UVFITS-文件通过CASA转换成MS-文件并使用multi-scale成图可得到基本一致的成图结果。为说明当前处理的正确性，文中给出了目本野边山天文台已经公布的观测处理结果图-4（b）作为对比。由于当前的数据处理过程中没有进行P角改正，图像中存在一些误差，在后期的工作中将进行改正。

表1MUSER多尺度洁化 Table 1Multi-Seale CLEAN for MSUER

# 初始化

1. 脏图（dirty image）：，初始情况下两者等价  
2. 计算uv覆盖值的范围，选取尺度大小，设计滤波器  
3. 根据原始uv和滤波器得到不同频率范围的脏图  
4. 选取估计的最大天空亮度值作为迭代阈值，增益大小为0.1

# a) 迭代计算

Repeat

并行在各个滤波后的图像中：  
(1)找到最亮的点，记录峰值亮度大小，位置及对应的尺度的大小，并计算最亮值与脏束（）卷积再乘以增益（gain）的结果，存储计算结果；  
$\textcircled { 2 }$ 在图像中减去(1）中的计算结果，得到残余图像;  
Until  
最大亮度值达到阈值（或达到预设迭代次数200

# b) 得到洁化图

在各个尺度中：

(1) 与结束卷积得到洁化图：，，为洁束(2) 将残余图像加到洁化图中：将不同尺度得到的不同频率范围的洁图进行叠加，得到最终结果

![](images/f35bdbf8c6ca0d9d0806479692c291c20ea16642e6fa6451eb635aa5eec98b73.jpg)

![](images/04ad7ff3538e48718d768e71a1f8d86079288a93846c092b89f7cac173c0942d.jpg)  
图3.基于图形处理器的成像流程  
图4(a)MUSER洁化图(Multi-seale) (MUSER-Iat 2015-11-0104:08:49.354161240(UTC),频率:1.7125GHz,右旋）(b)野边山天 文台洁化图 (2015-11-01 at 04:10:00 (UTC), frequeney:17 GHz (R+L).

# 3.2算法效率

由于多个滤波后的图像同时进行洁化,每个滤波后的图像有不同的迭代次数，且洁化算法的迭代次数动态改变，因此本文仅以具体实例说明多尺度带通滤波的性能。在NVIDIACorporation GM200-测试环境下，对于处理图-4中的2015-11-011.7125GHz的一张使用基于带通滤波的多尺度洁化时间为1.424-s，前期实验中的HogbomCLEAN算法f的洁化时间为4.03748 s。经过多次洁化处理实验，表明当前的-Multi-Seale CLEAN能有效将成图效率提高近3

，同时可以减少迭代次数，对数据处理流水线性能的提升有重要意义。

# 4.总结

本文在分析Multi-SealeCLEAN算法原理的基础上，实现了基于带通滤波的多尺度洁化算法，较Comwell的多尺度洁化算法在全局不同尺度的图像中的迭代而言，完全实现了不同尺度的并行。实验选取了针对MUSER成像的滤波器，尺度大小及不同尺度的取值。同时，基于图形处理器的实现表明，基于带通滤波的多尺度洁化算法比同等条件下的HogbomCLEAN性能提高了近三倍，并且可有效减少迭代次数。本文的研究结果将有效提高整个数据处理系统的性能，并对射电干涉成像提供了有价值的参考。

# 参考文献：

[1] Yan Yihua, Zhang Jian, Chen Zhijun, ct al. Progress on Chinese speetral radioheliograph CSRH eonstruetion[C]// Proeeedings of the General Assembly and Seientific Symposium. 2011 .

[2]Taylor G B, Carilli C L, Perley R A. Synthesis imaging in radio astronomy H[C]//-ASP Conferenee Series. 1999.   
[3]Cornwell T J. Multiseale CLEAN deeonvolution of radio synthesis images [J]. IEEE Journal of Seleeted Topies in Signal Processing, 2008, 2(5): 793-801.   
[4] Koshiishi H. Restoration of solar images by the Steer algorithm [J]. Astronomy & Astrophysies, 2003, 412(3): 893-896.   
[5]MUSCAT D. High-Performanee Image Synthesis for Radio Interferometry [J]. arXiv preprint arXiv:14034209, 2014.   
[56] Mereier C, Subramanian P, Kerdraon A, et al. Combining visibilities from the giant meterwave radio teleseope and the Nancay radio heliograph-High dynamie range snapshot images of the solar corona at 327 MHz [J]. Astronomy & Astrophysics, 2006, 447(3): 1189-201.   
[67] 卫守林,刘鹏翔,王锋,等.基于 Spark Streaming 的明安图射电频谱日像仪实时数据处理-[J]: 天文研究与技术,2017,14(4):421-428. Wei Shoulin, Liu Pengxiang, Wang Feng,et al. Real-time data proeessing in Mingantu Ultrawide Speetral Radio Heliograph based on Spark Streaming[J]. Astronomical Research & Technology; 2017,14(4): 421-428.   
[Z8]陈泰燃,王威,王锋,等.基于MPI的高性能UVFITS 数据合成研究与应用[J].天文研究与技 术, 2016, 13(2): 184-189. Chen Tairan, Wang Wei, Wang Feng,et al. The study and applieation of a high performanee UVFITS assembly system based on MPI [J]. Astronomieal Researeh & Technology, 2016,13(2): 184-189.   
[89] Wang F, Mei Y, Deng H, et al. Distributed data-proeessing pipeline for Mingantu Ultrawide Speetral Radioheliograph [J]. Publieations of the Astronomieal Soeicty of the Paeific, 2015, 127(950): 383-396.

# and its GPU implemention

Ying Mei+,4, Hui Deng³, Xiaoli Zhang²,Feng Wang+:3 4,Tengda Chen² (1. Yunnan Observatories, Chinese Aeademy of Seienees, Kunming 650011, China; 2. Kunming University of Seienee and Teehnology, Kunming 650500, China; 3. Center of Astrophysies, Guangzhou University, Guangzhou 510006, China; 3. University ofChinese Aeademy of Seienees, Beijing 100049, China)

Abstraet:China's new generation Radio teleseope-The MingantUSpEetralRadioHeliograph (MUSER) generates high-quality radio images with high temporal, high spatial, and high speetral resolutions in the frequeney range of 400 MHz\~15 GHz. The MUSER which will provide a new observational window on researehes such as solar aetivities, solar eleetron aeeelerations. Highperformanee and high-quality imaging forms a signifieantlyimportant aspeet of MUSER's massive data processing requirements.Referring to the data processing method of the MEUDON observatory in Franee, we give a detail analysis of multi-seale CLAEN. Appropriate parameters are given for MUSER CLEAN and the implementation based on GPU is presented. The experimental results show that the multi-seale CLAEN is nearly three times faster than the previously realizedHogbom CLEAN, which will improve the performanee of the whole data processing system effeetively.

Key Words:Multi-Seale CLEAN; Radio interferometrie imaging; GPU