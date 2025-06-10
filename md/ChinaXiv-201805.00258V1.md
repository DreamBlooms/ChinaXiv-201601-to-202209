# 基于GPU的单幅图像去雾的实现及优化

张津，周祥全，舒漫，王玉兰，魏友华，柳炳利(成都理工大学 数学地质四川省重点实验室，成都 610059)

摘要：基于暗通道先验规律的去雾算法已取得了良好的去雾效果，但算法所需要的计算时间过长，无法达到实时去雾的要求。使用GPU初步并行实现了去雾算法，并确定了算法中需要优化的部分。在优化过程中，一方面将数据存储到高速内存中以实现对数据的快速读取，另一方面设计新的算法实现方式以减少算法的计算量，最终提高了加速比。优化后的加速算法，处理 $7 6 8 \times 1 0 2 4$ 的图像仅需 $2 1 ~ \mathrm { m s }$ ，达到了实时去雾的要求。

关键词：图像去雾；GPU；并行优化；实时去雾 中图分类号：TP303 doi:10.3969/j.issn.1001-3695.2017.07.0889

# Implementation and optimization of single image haze removal based on GPU

Zhang Jin, Zhou Xiangquan, Shu Man, Wang Yulan†,Wei Youhua,Liu Binli (GeomathematicsKeyLaboratoryofSichuan Province,Chengdu UniversityofTechnology,Chengdu 610o59,China)

Abstract:The defogging algorithm which basedon dark channel priorhasachieved good results,but the time spent on computing is toolong to meeterequirements ofreal-time defogging. Withparalel GPU,thispaperimplemented thedefogging algorithmand tdeterminedtheportionofalgorithmwhichneedtooptimized.During theoptimizationproces,ontheonehand, it storedthe data in the high-speed memory toachieverapid dataread;on theother hand,designed anew algorithm implementationtoeducetheamountofcalculation,itimprovedtheacelerationrateultimately.Theaccelerationalgorithmjust need 21 ms when dealing with images of $7 6 8 \times 1 0 2 4$ after optimized, it has reached real-time defogging implementation.

Key Words: image defogging; GPU; parallel optimization; real-time fog removal

# 0 引言

大气中悬浮雾、霾等类似大气粒子的散射导致场景能见度低，此场景下所拍摄的图像的对比度和颜色的饱和度等都会有一定程度的衰减[1]。而在计算机视觉和图像处理领域，如目标探测、户外监控、遥感图像处理等[2]，都需要能还原真实场景的高质量图像，且在实时导航、自动驾驶等需要实时响应的技术领域中，不仅需要有效地去雾技术，更需要快速地实现技术[3]。

对于去雾技术，追求的是更好的去雾效果、更广的适用范围、更低的算法复杂度[4]，目前比较受推崇的去雾技术是He等人[5]提出的基于暗通道先验的去雾方法，该方法有较好的去雾效果以及适用范围，该方法最开始采用的是软抠图（Soft imagematting）优化透射率，算法复杂度较高，而后He等人[采用导向滤波取代了软抠图，而导向滤波的算法复杂度是线性的，并证明了其去雾效果与使用软抠图时基本相同，因此，采用导向滤波的去雾算法成为去雾技术中最有效的算法之一。

去雾技术已日趋成熟，那么现在需要解决的就是如何快速实现。最初使用软抠图时处理一张 $6 0 0 \mathrm { x } 4 0 0$ 的图像大约需要$1 0 { \sim } 2 0 ~ \mathrm { s } ^ { [ 6 ] }$ ，使用导向滤波可以缩短计算时间，都仍达不到实时的要求，且对于分辨率更高的图像，其计算速度依然较慢，因此，需要更快地实现技术[7]。自2007年 NVIDIA团队推出了CUDA接口，便于研究者使用GPU进行研发，基于GPU的快速去雾技术也被研究者们实现，如Lvy等人[使用GPU处理$6 0 0 \mathrm { x } 4 0 0$ 的图像所需 $0 . 0 8 3 \mathrm { ~ s ~ }$ ；Xue等人[8]也使用GPU实现了算法，最终处理时间0.036s左右等。计算时间已被缩短，但对于高清图像，加速效果依然不够。因此，本文深入探讨了算法加速的优化部分，从高速内存的高效率使用以及减少算法复杂度两方面入手，进一步提高了算法的加速比，对高清图像基本达到实时处理的效果。

# 1 算法简介

目前广泛使用的雾图形成模型是由大气散射模型变形而来[9,10]，即

$$
I ( x ) = J ( x ) t ( x ) + A ( 1 - t ( x ) )
$$

其中： $\operatorname { I } ( \mathbf { x } )$ 表示需要去雾的原始图像； $\mathrm { J } ( \mathrm { x } )$ 是需要恢复的图像(无雾图像)；A表示大气环境光； $\operatorname { t } ( \mathbf { x } )$ 为透射率。去雾算法就是从$\operatorname { I } ( \mathbf { x } )$ 恢复到 $\operatorname { J } ( \mathbf { x } )$ 。暗通道先验规律是指：无雾图像的暗通道像素亮度很小，趋近于零[6]。

$$
J ^ { \mathrm { d a r k } } ( x ) = \operatorname* { m i n } _ { c \in \{ r , g , b \} } ( \operatorname* { m i n } _ { y \in \Omega ( x ) } ( J ^ { c } ( y ) ) ) \approx 0
$$

基于暗通道先验规律，才有了这个去雾算法，其算法流程如图1所示。

![](images/8f5df87c38574fa440c6a1e670d308a306224bb15096636167aa0754fc1e4d37.jpg)  
图1图像去雾算法流程

具体步骤如下：

a）计算暗通道。设原始图像在 $\Omega ( x )$ 的区域内，透射率为常数 $\tilde { t } ( x )$ ，此时的透射率为粗略透射率，则原始图像的暗通道为

$$
I ^ { \mathrm { ^ { d a r k } } } ( x ) = J ^ { \mathrm { ^ { d a r k } } } ( x ) \tilde { t } ( x ) + A ( 1 - \tilde { t } ( x ) )
$$

b）估计大气光。选取暗通道中亮度最大的 $0 . 1 \%$ 像素，并根据这些像素点的位置获取原始图像中与之对应的颜色数值，计算器均值作为大气光的估计值A。

c）计算粗略透射率。由于 $J ^ { \mathrm { d a r k } } ( \boldsymbol { x } ) \approx 0$ ，可推出：

$$
\tilde { t } ( x ) = 1 - \omega \frac { J ^ { \mathrm { d a r k } } ( x ) } { \overline { { A } } }
$$

大气不可能没有任何颗粒[11,12]，彻底清除雾霾，图像可能看起来不自然。因此，引入了一个参数 $\omega$ ，使图像保留了非常小的雾度，参考文献将其固定为0.95，表示保留0.05的雾度[67]。

d)计算灰色图与优化透射率。如果使用粗略透射率还原图像，会出现“块效应”[13]，使用导向滤波算法优化粗略透射率。

$$
a _ { k } = \frac { \displaystyle \frac { 1 } { \mid \omega \mid } _ { i \in \omega _ { k } } I _ { i } p _ { i } - \mu _ { k } \overline { { p } } _ { k } } { \sigma _ { k } ^ { 2 } + \varepsilon }
$$

$$
b _ { k } = \overline { { p } } _ { k } - a _ { k } \mu _ { k }
$$

其中：I为参考图像（ $\mathrm { H e } ^ { [ 7 ] }$ 提供的MATLAB代码中I为原始图像的灰度图，本文也采用同样的方法)； $p$ 为粗略透射率； $q$ 为需要求解的优化后的透射率，在局部领域内 $a , b$ 取平均值，得出

$$
\overline { { a } } _ { i } = \frac { 1 } { \mid \omega \mid } \sum _ { k \in \omega _ { i } } a _ { k }
$$

$$
\overline { { b } } _ { i } = \frac { 1 } { \mid \omega \mid } \sum _ { k \in \omega _ { i } } b _ { k } \left( 7 \right)
$$

$$
q _ { i } = \overline { { a } } _ { i } I _ { i } + \overline { { b } } _ { i }
$$

e）复原图像。为避免透射率过小，恢复的时候产生噪声，设定了下限值 $t o$ 为0.1，恢复公式为

$$
J ( x ) = \frac { I ( x ) - A } { \operatorname* { m a x } ( t ( x ) , t _ { 0 } ) } + A
$$

本文主要介绍算法的加速及优化，具体的算法流程和公式请参考文献[6,7]。本文的去雾效果如图2所示。

![](images/c489729145d524b88d68a5329929ebaa7bf73dde99fd34bc04fb7a80d868f00a.jpg)  
图2图像去雾效果

图2(a)(c)为原始图像，即有雾的图像，(b)(d)为去雾后的图像。通过与文献[7]提供的MATLAB代码的计算出的像素点数值比较，计算结果基本相同。

# 2 并行加速和优化

采用CUDA平台的GPU并行加速，需要了解其硬件体系。CUDA 设备的核心是由一个可扩展的流多处理器（streamingmultiprocessorsSMs,）整列组成，当调用内核函数时，SM以线程块（block）为划分单位划分计算资源，同一个SM上并发执行多个线程块中的多个线程(thread)，每个线程负责计算一个或多个数据，这就是CUDA的 SIMT（single instruction，multiplethread）执行模型[14]。

本文加速设计是一个线程执行一个像素点的计算，线程块与线程都以二维的形式，以便于与图像的像素点一一对应，如图3所示。

![](images/c60a72571aab9603ed8dba189599b3f7e3e2cbdb2fb9613e7fed5eec9421d1b1.jpg)  
图3线程网格与图像网格的对应关系

线程网格初步设计完毕，现在先分析整个算法中哪些步骤需要提高性能，即找出哪些步骤占程序的大部分运行时间，再根据算法复杂度分析其并行性，估计其并行加速效果，如果并行度高，再进一步优化，以提高算法的加速比。

![](images/6f3fe14fe961de0059bd1eab3a9a70534d685df20fab48963dcab2eb8dbfba22.jpg)  
CPU去雾算法各步骤计算时间

CPU去雾算法各步骤计算时间如图4所示。由图4可看出，整个算法中费时的步骤主要是计算暗通道以及优化透射率，因此，本文主要讨论这两个步骤的加速以及优化，其余步骤基本并行加速即可，对于整个程序的运行时间并没有多大的影响。

# 2.1计算暗通道

暗通道的计算量不仅受图像尺寸大小的影响，还与按通道的宽度有关，设暗通道的宽度为r，图像的尺寸为 $\mathbf { m } ^ { * } \mathbf { n }$ ，则暗通道的计算量大致为 $\mathrm { m } ^ { * } \mathrm { n } ^ { * } \mathrm { r } ^ { * } \mathrm { r } ^ { * } 3$ ，除了计算量较大之外，还有一些在实际算法实现中的难点，例如在计算图像边缘的暗通道时，会出现越界现象，如图5所示。

![](images/2a3b93d0103e5aa08ee64830da29745121b5ab441136016ce63db5820540fec4.jpg)  
图5计算暗通道的难点分析

对于图5左上角的第一个像素点（黑色方块)，设暗通道的宽度为3，则有五个像素点属于越界，在实际计算中，需要判断上下左右四个方向是否越界，且计算暗通道是找出通道内的最小值，所以整个计算涉及了大量的判断语句，导致该步骤运行时间过长。

图5的右侧，像素点（1，4）和（3，4）在计算暗通道时会出现重复加载数据(图中的三个黄色方块)，可以将数据先读取到一个拥有高速带宽的内存中，以减少对全局内存的访问。寄存器是访问最快的内存，但寄存器是每个线程私有的且容量有限[1]，而相邻线程计算所需的数据有部分重叠，因此，使用共享内存，即能满足线程之间数据的重复使用，又能满足对数据的快速读取。

![](images/bd45a2f050e430428d7da32e229ac6efee63264d768da299f69c8c065d6bb8dd.jpg)  
图4CPU去雾算法各步骤计算时间  
图6数据从全局内存到共享内存的读取方式

设暗通道的宽度为3，图6（a)中白色区域为一个线程块，该线程块中每个线程与图像的像素点位置一一对应，周围的灰色方块为计算暗通道所需要的“越界”数据，图6（b）（c）中黄色方块的线程需要读取包括自身以及周围橙色方块的区域的数据，6（d）中灰色方块仅需读取自身所在区域的数据，通过这种方式读取，可以将该线程块中所有线程计算所需的数据存储在共享内存中。但对于全部数据，不同的线程块也会出现重复读取。

![](images/d7bd56184cef0174fc43fcd9784eb140863d3b267d3eb1b29c50e421fe22d788.jpg)  
图7不同线程块之间的数据的重复读取

每个线程块读取的数据如图6（a）所示。不同线程块之间的数据的重复读取如图7所示。再根据图7可知，相邻线程块对于“越界"数据是会出现重复读取的，黄色区域为读取1次，橙色区域表示读取2次，而黑色区域为4次。但总体而言，使用共享内存减少了对全局内存的访问。

![](images/4d9c3c5b9e8ecaeedc0b015489052e019967cc16be95f3b2f661692826421ed9.jpg)  
图8使用共享内存与全局内存的GPU暗通道计算时间对比

使用共享内存与全局内存的GPU暗通道计算时间对比如图8所示。根据图8可看出，使用共享内存，能有效地减少算法的计算时间，使用共享内存后计算速度平均为使用全局内存的7倍，充分利用高速内存，有效地提高加速比。

# 2.2优化透射率

优化透射率的公式为式 $( 5 ) \sim ( 8 )$ 。若直接根据公式加速算法，通过合并核函数后仅需启动两个核函数即可，但需要考虑边界、共享内存的大小、合并访存等问题，而导向滤波则需要启动二十多次内核函数，且多次调用box_filter函数。为此，作了多次实验，分析了在不同的窗口大小的情况下，两种算法计算所需的时长。

两种优化透射率方法计算时长的比较如图9所示。由图9可看出，随窗口宽度变大，使用box_filter函数的优势越大，所以本次实验使用box_filter 函数。box_filter函数在并行中分为两个部分，一部分是行中实现累加，另一部分是在列中实现累加，其余的都是一些简单的矩阵运算。因此，优化并行加速就得提高累加效率。

![](images/492f31c293bf31acd45340586d8dfee5527b6956836ce43f30050bfd9fce94e5.jpg)  
图9两种优化透射率方法计算时长的比较

![](images/8b36e86269882961be1e19417461eaae105bf889e09c7fb5fc17473700a39ab8.jpg)  
图10累加的一般并行方法

图10显示了累加的初步加速方法，只有8个数据时也需要进行17次加法运算。当数据量为 $\mathrm { ~  ~ N ~ }$ 时，需要进行 $( \mathrm { N } { - } 1 ) { + } ( \mathrm { N } { - }$ $2 ) + ( \mathrm { N } { - } 4 ) { + } . . . { + } \mathrm { N } / 2$ 次，即 Nlog2(N)-(N-1)次运算，计算效率太低了，随着 $\mathrm { ~  ~ N ~ }$ 的增大，所需要的计算时间也急剧增长。

![](images/df6122e8fec076e354634075771d859088e6932fd7b5a682eedae884631d17c0.jpg)  
图11优化后的并行累加

图11为优化后的并行累加。可以看出，同样是8个数据，一共只需要11次运算，依然假设数据量为N，则优化后的累加算法需要 $( \mathrm { N - 1 } ) { + } ( \mathrm { N } / 2 { - } 1 ) { + } \ldots { + } ( 4 { - } 1 ) { + } ( 2 { - } 1 )$ ，即 2N-log2(N)-2 次运算，算法复杂度降低了很多。

初始版本与优化版本的计算量比较如图12所示。优化版本的计算量是呈线性增长的，根据图12可看出，相比于初始版本，计算1024个数据时仅需要四分之一不到的计算资源。因此，随着图像尺寸的增大，加速效果也会越来越明显。

![](images/b8626421a6fbfe16d2e84f7230c8351cd23104ed4e7fe678f181a0a55c70d3b9.jpg)  
图12初始版本与优化版本的计算量比较

# 3 实验结果

与本次实验相关的环境如表1所示，程序运行版本为release。

表1实验环境  

<html><body><table><tr><td colspan="2">硬件环境：</td></tr><tr><td rowspan="2">主机端：</td><td>AMDFX(tm)-6300 Six-Core Processor 3.50GHz</td></tr><tr><td>8.00GB内存</td></tr><tr><td>设备端：</td><td>GeForceGTX970GPU，4GB显存</td></tr><tr><td></td><td>软件环境：</td></tr><tr><td rowspan="2">主机端：</td><td>Microsoft Windows 10(64bit Edition),</td></tr><tr><td>Microsoft Visual Studio 2013</td></tr><tr><td>设备端：</td><td>CUDA Toolkit 7.5</td></tr></table></body></html>

在此环境下，实验了不同尺寸的图像，其效果如表2所示。

表2不同尺寸图像的计算时间  

<html><body><table><tr><td>图像尺寸</td><td>CPU版本 /ms</td><td>GPU 初始版本 /ms</td><td>GPU 优化版本 /ms</td></tr><tr><td>300*400</td><td>220.41</td><td>32.13</td><td>4.3</td></tr><tr><td>400*600</td><td>431.57</td><td>60.06</td><td>7.36</td></tr><tr><td>600*800</td><td>823.18</td><td>127.53</td><td>14.18</td></tr><tr><td>768*1024</td><td>1269.24</td><td>173.72</td><td>20.91</td></tr></table></body></html>

由表2可看出，优化后的版本工作效率大约是优化前的十倍左右，对于 $7 6 8 ^ { * } 1 0 2 4$ 高分辨率图像，也仅需21ms不到，也就是说近50帧每秒，这已经达到实时处理的要求了。

# 4 结束语

国内外已有不少对去雾算法的加速研究，本文对于$6 0 0 ^ { * } 4 0 0$ 的图像的处理速度确实优于前人，然而因为不同的实验环境，实在难以比较哪种方案的优劣。而本文的重点是提出了对于加速优化的一些建议，主要是以下两点：

a)充分利用硬件设施中的高速内存，减少对全局内存的访问。如果该数据是同一个线程块中的不同线程需要重复使用的，可以存储到共享内存中，如果数据量小，且是线程私有的，可放入寄存器。

b)降低算法的复杂度，有效地减少计算量。同一个算法也会有不同的实现方式，尽量在保证算法并行度的同时降低复杂度。

对于去雾算法的并行优化，下一步工作是：数据存储到共享内存中时，如何以合并访存的方式对全局内存进行访问；在优化透射率的时候减少内核函数的启动开销。

# 参考文献：

[1]Narasimhan S G,Nayar S K. Contrast restoration of weather degraded images [J]. IEEE Trans on Pattern Analysis Machine Intelligence,2003,25 (6): 713-724.   
[2]Liu Qi,Gao Xinbo,He Lihuo,et al. Haze removal for a single visible remote sensing image [J].Signal Processing,2017,137: 33-43.   
[3]Hung C L,Ma Zhaohui,Lin Chunyuan,et al. Image haze removal of optimized contrast enhancement based on GPU [J].Frontier Computing, 2016,375: 53-63   
[4]郭璠，蔡自兴，谢斌，等．图像去雾技术研究综述与展望[J].计算机 应用,2010,30 (9):2417-2421.   
[5] He Kaiming, Sun Jian, Tang X. Single image haze removal using dark channel prior [J]. IEEE Trans on Pattrn Analysis and Machine Intelligence, 2011,33 (12): 2341-2353.   
[6]He Kaiming, Sun Jian,Tang Xiaoou. Guided image filtering [J]. IEEE Trans on Pattern Analysis and Machine Intelligence,2013,35 (6): 1397-1409.   
[7]Lvy Xingyong, Chen Wenbin, Shen IF.Real-time dehazing for image and video [C]//Proc of the 18th IEEE Conference on Pacific Computer Graphics and Applications.2010.   
[8] Xue Y G,Ren Ju,Su Huayou,et al. Parallel implementation and optimization of haze removal using dark channel prior based on CUDA [J]. High Performance Computing,2013,207: 99-109.   
[9]李佳童，章毓晋．图像去雾算法的改进和主客观性能评价[J].光学精 密工程,2017,25 (3):735-741.   
[10]魏颖慧，张彦娥，梅树立，等．基于暗通道先验和区间插值小波变换的 图像去雾霾方法[J]．农业工程学报,2017,33(S1):281-287.   
[11]宋颖超，罗海波，惠斌，等．尺度自适应暗通道先验去雾方法[J].红 外与激光工程,2016,45(9):286-297.   
[12]陈书贞，任占广，练秋生．基于改进暗通道和导向滤波的单幅图像去雾 算法[J]．自动化学报,2016,42(3):455-465.   
[13] TarelJP, Hautiere N.Fast visibility restoration from a single color or gray level image [C]// Proc of the 12th IEEE International Conference on Computer Vision. 2009.   
[14] Nicholas Wilt.2014.CUDA专家手册—GPU 权威编程指南[M].北

京：机械工业出版社.