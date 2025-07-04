# 一种基于日期码的快速缺陷检测算法\*

冯玮，方春，孙福振(山东理工大学 计算机科学与技术学院，山东 淄博 255049)

摘要：日期码缺陷检测仍然以人工为主，现有的用于检测日期码缺陷的算法受限于时间复杂度和准确率，无法在工业界获得较大范围的应用。针对这样的情况，提出了一种新的基于迭代配准的post-rotate iterativeclosest point (PRICP)算法。该算法把日期码抽象为点特征，通过对模板和特征点进行配准来快速检测日期码的缺陷，引入机器学习进一步提高了该算法的准确性、鲁棒性及缺陷分类能力。该算法已经成功应用于青岛啤酒厂流水线喷码日期的缺陷检测，现场运行结果显示该算法在鲁棒性和效率方面明显优于其他方法。适用于多个连通域的信息码的快速缺陷检测，同时不受条件及背景约束，抗噪声能力强，可直接应用与其他的视觉领域。

关键词：特征提取；模板匹配；机器学习；post-rotate iterative closest point（PRICP）算法 中图分类号：TN391.4 doi:10.3969/j.issn.1001-3695.2018.01.0058

# Fast defect detection algorithm based on date code

Feng Wei, Fang Chun+, Sun Fuzhen (SchoolofComputer Science&Technology Shandong Universityof Technology,Zibo Shandong 255049,Cina)

Abstract: The defect detectionofdatecode relies mainlyupon manualinspection.Due to the high complexityoftime and the low accuracy,the existing algorithms fordetecting thedefect ofcodescan not obtain a widerange of applications in industry. For suchasituation,thispaperproposedanalgorithmnamedPRICPbasedoniterativeregistration.ThisalgorithmfistAbstract: dthedatecode as a point feature,andthenregistered the templateand feature points toachieve the purposeof detecting the defect.Machine learingasanupgradeauxiliary function,improved itsauracy,robustness anddefectclassificationability. This algorithm hasbeen successullyappliedtothe inspectionofthe datecodeof Tsingtao.Theoperationresultsdemonstrate thatthealgorithminsensitivetoconstraintconditions,backgroundandnoiseissuperiortothetraditionalmethodintermsof robustnessandeficiency,candetectedefectofinformationcodesofmultipleconnecteddomainsfastlyandbedirectlyapplied to other visual field.

Key words:feature extraction;template matching; machine learing; post-rotate iterative closest point (PRICP）algorithm

# 0 引言

为了方便管理与标志，喷印日期码广泛应用于商品的包装，日期码是否符合标准，是否清晰美观，影响到商品出厂质量，而喷码大部分在高速流水线上进行，在兼顾生产效率的同时标志缺陷时有发生，使得缺陷特征不可避免，如果大量流入市场，必然影响商品的使用以及生产厂家的信誉。

在工程项目当中，针对信息码缺陷的检测算法的研发面临如下困难：a)需要对快速传送带上的物品进行喷码，所以必须具备较高的检测速度，工业传送带的速度最快可达 $3 \ \mathrm { m } / \mathrm { s } ; \mathrm { b } )$ 很多产品缺陷类型较多，所以需要具备检测多种缺陷类型（如无码、缺损码、重码、码区偏移等）的能力，很多工业需求甚至需要在特定的时间仅对特定的缺陷进行检测;c目前很多商品由于流水线速度很快、产品包装材质以及成本等原因，难添加剔除装置，只能添加报警装置来辅助人工剔除，考虑工人的工作效率及强度，这就需要更高的检测准确率;d)一款产品往往会有很多的规格，缺陷检测算法需要适应不同的规格。

针对上述问题，现有的解决方案仅能适应传送带速度较慢的情况，而且无法对缺陷进行分类和过滤[4\~6]；基于灰度的模板匹配算法[12,14]时间复杂度较高，运行效率低下，无法在PLC上运行，所以不适用于本课题；基于特征的模板匹配算法[13]，具有明显的特征冗余。无论是基于特征的还是基于灰度的算法，都需要提前制作模板，存在大偏转角度不适应的问题，因此它们虽然有较高的准确率，但无法适应不断变化的码字和环境。Optical character recognition(OCR)[10,15]需要把完整的几何结构都识别出来，对计算资源要求高，限制了算法效率。本文针对上述问题，提出了快速的抗噪声能力强的post-rotate iterativeclosestpoint(PRICP)算法。它可兼顾高效率以及高稳定性的要求，可以适用于大部分印刷行业的缺陷检测。

该算法已经成功应用于青岛啤酒厂的瓶盖喷码日期的缺陷检测。据在青岛啤酒厂流水线成功运行三个月的经验，缺陷检测的精确率可以达到 $9 7 \%$ 以上，如果作为扩展功能再引入LeNet-5模型，精确率可达 $9 9 . 9 \%$ 以上，并且可以对缺陷进行有效的分类和过滤，这表明该算法在高速传送带上即使没有剔除装置的也可以很好地为生产服务。

# 1 滤波器

# 1.1特征提取 (轮廓提取[2])

相比于神经网络提取特征，人工提取可能会过早地丢掉关键信息[]。但是，如果特征过于明显，人工特征会更有利于提高效率以及检测成功率，人工神经网络则更适合于特征不明显的需求。

喷印信息码的预处理首先是二值化，这依赖于合适的相机、镜头及光源，一些特殊的需求可以添加滤光片。一个好的打光会极大地提高二值化的效果，二值化后就是轮廓分析（如图1所示，红色圆圈代表去噪声后的轮廓的中心点（15个字符，15个轮廓))。本算法主体部分是基于拓扑，通过轮廓提取算法形成轮廓树，轮廓树的分枝是轮廓的同调类（同一个连通域的内轮廓与外轮廓同调)，每个连通域的面积可以过滤噪声，以及通过轮廓的伦型来甄别某些缺陷。例如，当重码发生时，由于字符相交，内轮廓就很有可能会增多，这时内轮廓就可以作为一个特征为最终的判断服务（如图9)。

![](images/ffcbd75689586b9f656e66d357dc24960ab1b35ddabae3c2da81f8b358c2dc99.jpg)  
图1青岛啤酒喷印日期轮廓中心点 (红色)

# 1.2制作模板

基于上一步提取到的轮廓的中心点集合制作模板。例如，图1所示的青啤瓶盖喷码日期的模板制作就是第一行8个点、第二行7个点的总共15个点的坐标集合。仅用每个字符的中心点坐标作为模板有如下好处：

a)相对于一般的模板匹配，仅用几个中心点进行匹配更有利于提高效率。b)字符中心点集合代表了喷印信息码的基本位置信息，具备明显的特征，抗噪声能力强，适合用来检测缺陷。

# 1.3模板匹配

Iterativeclosestpoint（ICP）是做刚性配准的常用算法[]，简洁实用，数学推导清晰：首先利用协方差巧妙的构造$4 \times 4$ 对称矩阵 $Q ( \sum _ { p x } )$ ，然后计算出最大特征值对应的特征向量来构造单位四元数表示空间旋转，利用四元数可以方便地构造绕任意轴任意角度的旋转，同时也避免了万向锁的问题。ICP在保持了其简洁的数学美之外，不可避免地也存在工程应用上的不足：不支持大的旋转角以及待配准的模型必须具有清晰的主元（生成的协方差矩阵最大的特征值需要远大于次大的特征值)，且不能引起旋转二义性，这严重地影响了其工程项目中的应用范围及效果。

本文提出的PRICP算法摒弃了依赖主元进行旋转的限制，非常适合于喷印日期码为代表的缺陷检测。首先进行转正操作，然后再进行平移迭代，在平移迭代过程中利用PCA进行修正。转正基于轮廓的中心点集合，首先提取轮廓中的直线特征，绝大部分喷印信息码的字符中心点集合都存在明显的直线特征，如图1的“20170520”大约在同一直线上。依据点线对偶的原理，轮询 $0 \mathrm { \sim } 1 8 0$ °，获取点最多的那条直线的角度，即为喷印码偏转的角度。由于该算法对很小的点集进行操作，性能稳定性好。根据现场运行结果统计，该算法误判率在百万分之一以下。获得偏转角度算法的 $\mathrm { C } { + } { + }$ 代码如下

#define CV_PI 3.1415926535897932384626433832795   
#defineMAXPOINTCOUNT1000

typedef struct CvPoint   
{ int x; int y;   
1   
vPoint;   
/ <summary>   
／得到旋转角度   
/ </summary>   
/ <param name="center_ps">轮廓中心点集合</param>   
/ <param name $\mathrel { \mathop : } =$ cont_size">轮廓数量</param>   
Duble get_angle(vector<CvPoint>center_ps   
,int cont_size) int angle_set[MAXPOINTCOUNT][180]={0}; int maxvalue=0; double angle=0; for(int i=O;i!=cont_size;++i) { for(int j=0:j<180;++j) { double theta=j\*CV_PI/180; double rho $\ c =$ center_ps[i].x\*cos(theta) $^ +$ center_ps[i].y : sin(theta); int $\mathrm { k } =$ static_cast<int>(rho); angle_set[k][j] $^ { + + }$ ： if(angle_set[k]lj]>maxvalue) { maxvalue=angle_set[k][j]; angle=j; 1 1

return angle; 1

为方便下面讲述配准算法，先下一个定义：

定义1 设点集 $M$ 的协方差矩阵 $E$ ，以及 $E$ 的绝对值最大特征值为 $\lambda$ ，对应的特征向量为 $x$ ，则M的主元为（204号 $p = \lambda x$ □

转正完成后再进行基于中心点的平移迭代配准，其中点集$B$ 是有效点集（不是点集中的每个点在迭代中都起作用)；另外，也利用了主元的思想对迭代进行小幅度的纠正，降低误差。具体步骤如下：

a)开辟内存，定义集合变量T、 $A$ 、 $B$ 、 $\boldsymbol { \mathbf { \mathit { C } } }$ ，模板坐标集合赋给T，当前帧的轮廓中心点坐标集合赋给 $A$ 和 $B$ 。计算T的主元 $p ^ { \prime }$ ，计算T和 $B$ 的中心点，公式为： $a \nu e r = \frac { \displaystyle \sum _ { n = 1 } ^ { m } a _ { n } } { m }$ ，其中： $m$ 是点的数量。

b)设定阈值SUPPORTDIST（本项目中设定为40，需要根据具体需求在调试中进行设置)。初始化整形变量last_error为0。

c)计算 $B$ 的主元 $p$ ，如果 $\left| p \right| > \left| p ^ { \prime } \right|$ ，计算 $\nabla p = p - p ^ { \prime }$ ，计算得到 $B$ 的中心点 $b$ 与 $\mathrm { \Delta T }$ 的中心点 $t$ ，计算 $\boldsymbol { s } = \boldsymbol { b } - \boldsymbol { t } - \boldsymbol { c } \times \nabla p$ （其中 $c$ 是实系数，可根据具体情况进行设置，在本项目中设置为0.1)，然后把 $\mathrm { \Delta T }$ 的每一个点平移 $s$ 。 $s$ 指向远离噪声的方向，见图2、3、4。

d)初始化整形变量distadd为0、count为0、error为0。

e)轮询T中的每一个点 $t$ ，计算 $t$ 在 $A$ 中的与最近点a的距离dist，判断dist是否小于SUPPORTDIST。如果小于就添加到集合 $C$ ，同时把distadd加上dist，以及count加1。由于这里点比较少，寻找关联点不需要作加速处理。

f)轮询结束后，计算error=distadd/ $e r r o r = d i s t a d d _ { \bigg / c o u n t ^ { 2 } }$ 把集合 $C$ 赋给集合 $B$ 0

g)设定阈值ITERTHRES（本项目中设置为0.1)，如果$\left| l a s t \_ e r r o r - e r r o r \right| < I T E R T H R E S$ ，迭代停止，算法达到收敛；否则赋值操作 $l a s t \_ e r r o r = e r r o r$ ，然后回到步骤c)继续迭代。

![](images/9a9dd837a2f3b168dce0978617ac01e462cf24647e12b5e870846d538732a024.jpg)  
图2离散点的主元 (红色)

![](images/b212f82ca9719340bf1c2f647a2f09f08d37de297e2c8ed604c4cc9c3df49c09.jpg)  
图3增加了噪声点（右下）的离散点的主元（红色）

![](images/a45c2155434dd8b8e4be6fc3988c720360ac6b0ac0356953056f44c9a0ae0269.jpg)  
图4主元的差指向远离噪声的方向 (绿色)

该算法是基于轮廓分析算法，提取轮廓树的时间复杂度是 $O ( W H )$ （其中 $W$ 是图像的宽度， $H$ 是图像高度)。剩下的转正算法和平移迭代算法的时间复杂度是 $O ( n ^ { 2 } )$ （其中 $n$ 是特征点的数量，青啤项目中是15)。由于是对很少的点进行，所以几乎不会对最终模块的效率问题造成影响。算法抗噪声能力强，适用于高速流水线上的缺陷检测。PRICP算法实现起来比ICP算法简单，并且更容易扩展。利用先验转正，然后平移迭代的思路使存在大的偏转角度的缺陷检测需求得以稳定地解决。

# 2 扩展功能

# 2.1机器学习

对像青啤瓶盖（图5）喷码日期与背景的对比度不明显的需求，设置参数使得在保证漏检率可以忽略的前提下，缺陷检测的准确率可以达到 $9 7 \%$ 以上。但是仅用滤波器，如果不添加机械剔除，考虑到实施工程师现场实施可能存在不规范的情况，检测装置很难进行大规模的扩展，所以在完成PRICP以后需要对产品做升级一一引入机器学习算法。

![](images/72eda364a8e3fc4ed56642203916945ef6175ea2bcb944ebc7f677fa9a94cd9f.jpg)  
图5青啤瓶盖喷码日期

滤波器可作为第一版本缺陷检测系统，应该先于机器学习完成。在实施规范的前提下，第一版本系统已经可以进行很好的缺陷检测，同时可以在工业现场采集用于制作训练集、测试集的图片。

机器学习在这里适合作为一个扩展辅助功能，在产品的第二版本中体现，仅对滤波器的置信区间的补集进行训练，可以极大地提高检测系统的准确率，并且可以对如细小划痕等的"缺陷”进行屏蔽。

使用前面的滤波器，可以保证有 $9 5 \%$ 的产品落入算法置信区间内，也就是可以保证 $9 5 \%$ 的产品分类（正常或缺陷）的准确率（比如在青啤车间运行数据，在算法置信区间之内的准确率可达到 $9 9 . 9 9 \%$ ，并且漏检率低于十万分之一，可以忽略不计)，算法在置信区间的补集上的准确率相对较低，这时可用机器学习算法针对PRICP置信区间的补集进行训练。如果训练样本组织足够合理，至少可以训练到 $9 9 \%$ 以上的准确率。总的准确率至少是： $9 5 \% \times 9 9 . 9 9 \% + 5 \% \times 9 9 \% = 9 9 . 9 4 \%$ 。针对置信区间之外的漏检的情况，可额外地增加一些偏执。例如，可把模棱两可（可判可不判）的样本加到负样本中，使得训练好的网络漏检率也是可以忽略的。

缺陷检测系统处理流程如图6所示。

![](images/9f42ee797557e90385f02d9e21e62639dcf1f0b295d0c4fbeef776e47f082099.jpg)  
图6缺陷检测系统处理流程

缺陷检测系统一般要求能够在PLC上高效运行，以及训练可采用在线训练，可选择LeNet-5模型[3]。在线训练时，PRICP的少量的误判在反向传播中只产生可以忽略的偏置，对最终拟合的结果有非常小的影响。在线训练省去了人工添加标签的成本。也可采用离线批量训练，这就需要人工添加标签，增加了成本但是也提高了模型的稳定性，同时可供选择的机器学习模型更多。

# 2.2机械剔除装置

机械剔除装置可以从根本上解放人工，同时也降低了算法的压力。但考虑很多工业线体运行高速，并且传送带的结构以及产品的材质（玻璃)，有时候添加起来还是有难度，同时也极大地增加了设备的成本。

# 3 实验结果与分析

本文的PRICP 算法，在实验室做了充分的前期实验之后，去青啤现场去调试、修改、升级，直到验收。同时，也利用Halcon中基于灰度的模板匹配模块对青岛啤酒做实验，并与本文算法进行对比。

笔者把一瓶青岛啤酒放在机器视觉圆形实验台的中央，模拟现场速度匀速旋转实验台，做360‘旋转检测，通过本文的PRICP算法以及halcon 模板匹配提取每个字符区域，在RAM:4GB，CPU:CORE i5-7500 的机器上PRICP 只需平均10 mS的运行时间，准确率 $9 9 . 9 \%$ ，如图7所示。其中红色的点表示滤波后提取的轮廓中心点，其中含有噪声。

![](images/01864c691db4cf82c77012b83cf0f77caa91b3491fa9dc6374f1c7c4a3fc1f95.jpg)  
图7PRICP提取字符区域（绿色）

用halcon基于灰度的模板匹配需要提前抠图制作模板。

在本测试用例中，准确率和PRICP不分伯仲，但运行时间是20ms 左右。这是由于PRICP仅对十几个特征点作迭代配准，效率上远远高于基于灰度的模板匹配。

在青岛啤酒厂的瓶盖喷印日期缺陷检测项目，硬件采用高帧率工业黑白相机，镜头添加蓝色滤光片；外加低角度环形白光源；触发器采用对射式光电触发。青啤现场硬件结构如图 8所示。

![](images/e6847a2c8a6c69a1bd6d9ce204df8d49cfd7725753d60b5208afa41619e70180.jpg)  
图8青啤现场硬件结构

在青啤为适应高速传送带，算法在工控机（RAM:2GB，CPU:COREi5-6400）上的运行时间是 $2 0 ~ \mathrm { { \ m s } }$ ，可同时检测无码、缺损码、重码、粘连、划痕等缺陷，见图 $9 \mathrm { \sim } 1 3$ 。

![](images/3fa342a511ec08ffed403517c4017f376e48f1f22644c1863210e58916f6670f.jpg)  
图9无码

![](images/1e87b662284abb55934a25e1fc58c1a201e79af4377c29504cef7e38d0da8ce1.jpg)  
图10 缺损码

![](images/da3d84d3ba2b7c208dd01e2774d671a8443f5b311d4b2f321679249e20059d17.jpg)  
图11粘连码

![](images/52ae22b1b6fd3df3dec496e76f62af9c4be4d118b4aad3b7c627ec1deaebd856.jpg)  
图12重码

![](images/144171f9e750e7369c9c16ffc8c228697d21728d20770950244f3cfd66170e2d.jpg)  
图13划痕

在工业现场实测，本文算法在不添加机器学习的情况下总的误捡率是低于1/20000的。由于有数据不平衡问题（正样本远远多于负样本)，所以在这里采用检测缺陷的精确率和召回率来衡量算法。据青啤现场的测试的553216瓶，误检数是10瓶，缺陷检出数是340瓶，漏检数是4瓶，检测缺陷的精确率约为97. $0 6 \%$ 、召回率约为 $9 8 . 8 \%$ (表1)。考虑到现场喷码机不稳定、缺陷形式多样以及现场生产缺陷数较少（大约每一个小时生产一个缺陷),这样的缺陷检测在不添加剔除装置的前提下也可以达到现场使用的需求，不会对工人造成负担。

之所以会达到这样的效果，是因为PRICP算法基于合理的人工特征，利用较少的信息（15个特征点）表达了日期码的不变量，降低了算法的复杂度。算法对点集的中心点进行平移迭代，且经过前期基于轮廓树的滤波，仅有较少的噪声点，很快就可以达到收敛（经实验验证：一般在3一5次迭代就可以收敛，使得残差缩小到允许的范围内)，最终兼顾了高准确率和高效率。

扩展功能---添加机器学习模型可以进一步的提高缺陷检测精确率和适用范围。例如，由于PRICP基于拓扑伦型不变量，无法屏蔽细小划痕而不把它算做缺陷，所以需借助于机器学习模型，把细小划痕的样本贴上“正常”的标签，使得算法对其适应。同样可以选择在线学习，相比于整帧的测度，由于细小划痕造成的误标签所占比例很小（据在青啤的实测结果低于1/20000)，细小划痕可以忽略。这对最终的模型只带来了极小的影响，几乎不会影响到拟合结果。

表1缺陷检测统计  

<html><body><table><tr><td>日期</td><td>总数</td><td>缺陷数</td><td>误检数</td><td>漏检数</td></tr><tr><td>05-04</td><td>56017</td><td>127</td><td>3</td><td>2</td></tr><tr><td>05-05</td><td>139531</td><td>44</td><td>2</td><td>1</td></tr><tr><td>05-06</td><td>126512</td><td>41</td><td>2</td><td>1</td></tr><tr><td>05-07</td><td>147726</td><td>110</td><td>3</td><td>0</td></tr><tr><td>05-08</td><td>83430</td><td>18</td><td>0</td><td>0</td></tr><tr><td>共计</td><td>553216</td><td>340</td><td>10</td><td>4</td></tr><tr><td>精确</td><td>97.06%</td><td></td><td>召回</td><td>98.8%</td></tr></table></body></html>

# 4 结束语

本文提出的PRICP算法稳定，该算法简单、高效，且易实现，并且它不受大角度旋转角和主元是否清晰的影响，非常适合快速传送带上的信息码的缺陷检测。然而仅仅依赖于PRICP算法，缺陷检测系统依然难以摆脱人工而实现全自动化检测的需要。这时，结合辅助的机器学习自动识别算法，在PRICP算法的置信区间之外再一次对样本进行分类。两者结合，即使在不添加剔除装置的情况下，也可获得较好的检测效果，极大地减小人工成本，并且也极大地提高了流水线的检错能力。然而，PRICP毕竟是通过两步（转正、平移迭代配准）完成，如何将其更加高内聚的统一起来，并且在稳定性和适用性上优于ICP算法，是笔者下一步需要研究的问题。

# 参考文献：

[1]BeslPJ,Mckay HD.A method for registration of 3-D shapes[J].IEEE Trans on Pattern Analysis and Machine Intelligence,2002,14 (2): 239-256.   
[2]Suzuki S,Be K. Topological structural analysis of digitized binary images by border following [J]. Computer Vision Graphics and Image Processing, 1985,30(1):32-46.   
[3]Lecun Y,Botou L,Bengio Y,et al.Gradient-based learning applied to document recognition [J]. Proceedings of the IEEE,1998,86 (11): 2278- 2324.   
[4]Blackledge JM,Dubovitskiy D A.A surface inspection machine vision system that includes fractal texture analysis [R].[S.1.]: Dublin Institute of Technology, 2008.   
[5]Park JK,Kwon B K,Park JH, et al. Machine learning-based imaging system for surface defect inspection [J]. International Journal of Precision Engineering and Manufacturing-Green Technology,2016,3 (3): 303-310.   
[6] Mishra R，Shukla M D.A survey on various defect detection [J]. International Journal of Engineering Trends and Technology,2O14,10 (13): 642-648.   
[7] 张慧，王坤峰，王飞跃．深度学习在目标视觉检测中的应用进展与展望 [J]．自动化学报,2017,43(8):1289-1305.   
[8]Rusinkiewicz S,Levoy M.Eficient variants of the ICP algorithm [C]// Proc of IEEE International Conference on 3-D Digital Imaging and Modeling. 2002:145-152.   
[9]Hanebeck U D.Template matching using fast normalized cross correlation [C]//Proc of International Society for Optics and Photonics.20o1: 95-102.   
[10] Smith R W. History of the tesseract OCR engine: what worked and what didn't [C]/ Proc of SPIE Document Recognition and Retrieval. 2013.   
[11]张岩，李建增，李德良，等．特征匹配算法鲁棒性与速度的对比分析 [J]．飞航导弹,2017(1):71-79.   
[12]缪源．图像匹配算法的研究[D].合肥：合肥工业大学,2013.   
[13]刘锦峰．图像模板匹配快速算法研究[D]．长沙：中南大学,2007.   
[14]金佳．瓶盖表面排码缺陷检测与算法研究[D].沈阳：东北大学,2014.   
[15]梁坤．基于机器视觉罐装食品瓶盖字符识别与缺陷检测[D]．天津：天 津科技大学,2016.