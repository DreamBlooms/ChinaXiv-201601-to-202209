# 基础研究

# 基于快速亚像素运动估计的肺4D-CT图像超分辨率重建

肖 珊」,王婷婷²，吕庆文²,张 煜²  
1吉安市中心人民医院器械科,江西吉安 343000；南方医科大学生物医学工程学院,广东广州 510515

摘要:肺4D-CT图像超分辨率重建技术对于提高肺4D-CT图像分辨率有重要作用。本文提出一种基于快速亚像素运动估计的超分辨率处理方法，以重建清晰的肺4D-CT图像。首先采用快速亚像素运动估计方法估计不同"帧"图像间的运动场,然后采用迭代反投影方法重建高分辨率肺4D-CT图像。实验结果表明,与传统的插值方法及基于全搜索运动估计的超分辨率重建算法相比较,本方法能得到更清晰的肺部图像，图像结构明显增强。同时，与全搜索算法相比，运算时间显著缩减。

关键词：肺4D-CT数据，可以整体表达；超分辨率重建；运动估计；亚像素

# Super-resolution reconstruction of lung 4D-CT images based on fast sub-pixel motion estimation

XIAO Shan1,WANG Tingting²,LU Qingwen²,ZHANGYu   
Departmentaafdl   
Guangzhou 510515,China

Abstract: Super-resolution image reconstruction techniques play an important role for improving image resolution of lung 4D-CT. We presents a super-resolution approach based on fastsub-pixel motion estimation to reconstruct lung 4D-CT images. Afastsub-pixelmotionestimationmethodwasusedtoestimatethedeformationfieldsbetween "frames",andtheniterative back projection (IBP)algorithmwas employed toreconstruct high-resolution images.Experimentalresultsshowed that compared with traditional interpolation methodandsuper-resolutionreconstructionalgorithmbasedonfullsearchmotion estimation, the proposed method produced clearer images with significantly enhanced image structure details and reduced time for computation.

Key words: lung 4D-CT data; super-resolution reconstruction; motion estimation; sub-pixel

4D-CT在肺癌放射治疗中发挥着重要的作用，它提供了一个全面的高精度放射治疗呼吸运动表征，有助于跟踪肿瘤运动，实施精确放射治疗，减少对正常组织的损伤。肺4D-CT数据的获取，通常是根据床位和肺体积,将多个自由呼吸3D-CT数据段排序而得。然而，由于CT固有的高剂量照射23,故往往只能降低沿纵向(Z轴方向)的采样来减少4D-CT扫描时间以求降低辐射量，从而导致肺4D-CT图像层间分辨率远低于层内分辨率，造成数据显著的各向异性。因此，在对肺各相位3D数据进行冠矢状面观察时，为了获得正确比例的图像，需要根据3D数据的层间分辨率和层内分辨率的比例，沿乙轴方向进行插值放大。常用的插值方法为最近邻或双线性插值法，这些方法都会导致图像的模糊，尤其当层间分辨率与层内分辨率比例差别比较大时。因此，研究如何提高肺4D-CT图像分辨率有着实际意义。

图像超分辨率重建技术是一种提高图像分辨率的有效方法。其原理是利用多帧关于同一场景的有相互位移的低分辨率降质图像来重建高分辨率图像[4]。本文的主要目的是提高肺4D-CT数据多平面显示图像的质量。肺4D-CT数据提供随呼吸运动变化的肺部低分辨率图像序列，故多平面间不同相位对应图像可以认为是一系列低分辨率图像“帧”，这些图像间信息是互补的，根据这个特征我们可采用超分辨率技术重建清晰的高分辨率图像。超分辨率重建方法已有多年的研究。其可大体划分为两类：频域方法和空域方法[5]。频域方法是基于傅里叶变换的方法，将图像变换到频域内以消除低分辨率图像的频谱混叠。其算法简单，运行速度快，但是难以处理图像噪声问题，而且只能处理全局整体运动的降质模型。因此,该方法有很大的局限性,并不常用。目前的研究主要集中在空域方法方面。常用空域超分辨率重建方法有凸集投影法(POCS）迭代反投影法(IBP)、最大后验法(MAP)等。他们各有优缺点，其中迭代反投影法因为理论简单、收敛快而得到了广泛应用。在文献[7]中，我们提出基于运动估计的迭代反投影的超分辨率重建方法，实现了肺4D-CT数据冠(矢)状面图像分辨率增强。在此方法中，图像间运动场的估计是影响重建精度和速度的主要因素。由于我们采用的是全搜索运动估计法估计不同帧图像之间的运动场，因此该方法的缺点是速度慢，且只能是固定搜索步长，这样既影响重建速度，也影响重建精度。

本文中我们结合三步搜索法[9和光流场方法[10-12]，实现了快速的图像间亚像素运动估计，而后，采用迭代反投影(IBP)算法[,重建出高分辨率的肺4D-CT图像。实验结果表明，本文基于快速亚像素运动估计的超分辨率技术的重建结果显著优于传统的双线性插值法；并且，本文算法重建结果较文献[7]提出的基于完全搜索块匹配运动估计的超分辨率重建结果好，计算时间也大幅度缩减。

# 1方法

1.1不同相位间肺4D-CT图像运动估计

本文将多相位低分辨率图像作为输入“帧”，首先估计各帧图像间的运动场。具体包含两个步骤：(1)采用三步搜索法，搜索图像块之间的整数像素位移；(2)采用光流法搜索亚像素位移。整个过程叙述如下。

1.1.1 三步搜索法(three step search,TSS）TSS采用的是一种由粗到细的搜索模式，从搜索窗中心点开始，按一定步长取周围8个点构成每次搜索的点群，然后按照匹配准则进行匹配计算，找到误差最小的匹配块中心点。匹配准则本文仍选择简便有效的绝对误差和(SAD)来求解两图像间的初始运动矢量，SAD定义如下：

$$
\begin{array} { r } { S ( \nu _ { x } , \nu _ { y } ) = \sum _ { i = 0 } ^ { N - 1 } \sum _ { j = 0 } ^ { N - 1 } \bigr | I _ { t } ( p + i , q + j ) - I _ { t - \Delta _ { t } } ( p + \nu _ { x } + i , q + \nu _ { y } + j ) \bigr | } \end{array}
$$

式中，图像块的大小为 $N \times N$ ,左上角的坐标为（204号 $( p , q )$ ;运动矢量为 $( \nu _ { x } , \nu _ { y } ) ; I _ { t } ( i , j )$ 和 $I _ { t - \Delta _ { t } } ( i , j )$ 分别为当前帧和参考帧在像素 $( i , j )$ 处的值。在搜索区域内使$S ( \nu _ { x } , \nu _ { y } )$ 值最小的运动矢量即为当前块的最优运动矢量。

TSS的步骤为：第一步,首先确定一个中心点，设定最大搜索长度，以最大搜索长度的1/2作为步长，将中心点及周围距离相同步长的8个检测点根据匹配准则，找到最小块误差点，如果最小块误差点位于原中心点，则算法结束，否则，进行下一步;第二步，步长减半，在上一步确定的最小块误差点及其周围相同步长的8个检测点中找到最小误差匹配块的中心点;第三部，重复第一部和第二步，直到步长达到搜素精度要求，即得到最佳匹配点。其原理示意图如图1所示[9]

1.1.2光流法采用三步搜索法进行初始运动估计之后，所得运动矢量精度为整数，其为图像运动矢量的粗略估计，因此本文还将采用光流法对初始运动矢量进行精度优化，精确到亚像素。

![](images/b70eed168553fd081c6756c10ebe168fbe2ce5b4dc575782ce4913f0ebc43e13.jpg)  
图1块匹配三步搜索法 Fig.1 Three-step search of block matching algorithm.

假设运动前后两帧连续图像分别为 $f ( x , y )$ 和$g ( x , y )$ ,根据经典光流简化模型[12]，可得式(2)：$g ( x , y ) = f ( x + \Delta x _ { s } , y + \Delta y _ { s } ) \approx f ( x , y ) + \Delta x _ { s } { \frac { \hat { \mathcal { O } } } { \hat { \mathcal { O } } x } } f ( x , y ) + \Delta y _ { s } { \frac { \hat { \mathcal { O } } } { \hat { \mathcal { O } } y } } f ( x , y )$ (2)

该式近似为一阶泰勒级数展开式。

对(2)式进行最小化求解可得最优位移矢量：

$$
\operatorname* { m i n } _ { \Delta x _ { s } , \Delta y _ { s } } i m i z e \Phi ( \Delta x _ { s } , \Delta y _ { s } )
$$

其中：

$$
\Phi ( \Delta x _ { s } , \Delta y _ { s } ) = \sum _ { x , y } ( g ( x , y ) - f ( x , y ) - \Delta x _ { s } \frac { \hat { \sigma } } { \hat { \sigma } x } f ( x , y ) - \Delta y _ { s } \frac { \hat { \sigma } } { \hat { \sigma } y } f ( x , y ) ) ^ { 2 }
$$

式(4)可看作线性最小二乘求解问题，可将目标函数的偏导数置0得到最优值 $\Delta x _ { s } , \Delta y _ { s ^ { \circ } }$ 因此,可有如下方程：

$$
\frac { \partial \Phi } { \partial \Delta x _ { _ { s } } } = 0 \mathrm { ~ } \mathcal { F } \mathbb { H } \frac { \partial \Phi } { \partial \Delta y _ { _ { s } } } = 0
$$

求解方程(5),可得最优解△x,△y

设三步搜索法得到的初始运动矢量为 $\Delta x _ { I } , \Delta y _ { I } ,$ 则最终得到的总运动矢量 $\Delta x , \Delta y$ 为：

$$
\Delta x = \Delta x _ { I } + \Delta x _ { s } , ~ \Delta y = \Delta y _ { I } + \Delta y _ { s }
$$

1.2迭代反投影(IBP)超分辨率重建

IBP算法是由Irani和Peleg[3率先提出，其基本思想是：首先,假设一个初始高分辨率图像 $\boldsymbol { H } ^ { ( 0 ) }$ ,然后,根据退化模型[14模拟成像过程得到一个低分辨图像的集合$\Big \{ L _ { k } ^ { ( n ) } \Big \} , k = 1 , \dots , K , K$ 表示原始序列低分辨率图像的数量， $n$ 为迭代次数。如果 ${ \boldsymbol H } ^ { ( 0 ) }$ 是正确的高分辨率图像，则得到的这一集合就应该和已知的低分辨率图像序列集合 $\left\{ L _ { k } \right\}$ 相等。如果 $\cdot H ^ { ( 0 ) }$ 不是理想的高分辨率图像,则 $\left\{ \boldsymbol { L } _ { k } \right\}$

$\left( L _ { k } ^ { ( n ) } \right)$ 将产生差值 $\left\{ { L } _ { k } - { L } _ { k } ^ { ( n ) } \right\} _ { \circ }$ 将此差值返回给 $\cdot \boldsymbol { H } ^ { ( 0 ) }$ 并更新之,得到一个相对较接近的正确结果 $\boldsymbol { H } ^ { ( 1 ) }$ 。反复迭代该过程直至收敛，则重建结束，误差计算为：

$$
\begin{array} { r } { e ^ { ( n ) } = \sqrt { \displaystyle \frac { 1 } { K } \sum _ { k = 1 } ^ { K } \biggl \| L _ { k } - L _ { k } ^ { ( n ) } \biggr \| _ { 2 } ^ { 2 } } } \end{array}
$$

在第n次迭代过程中， $\boldsymbol { L } _ { k } ^ { ( n ) }$ 可表示为：

$$
\boldsymbol { L } _ { \boldsymbol { k } } ^ { ( n ) } = ( \boldsymbol { T } _ { \boldsymbol { k } } ( \boldsymbol { H } ^ { ( n ) } ) h ) \downarrow \boldsymbol { s }
$$

式中， $\boldsymbol { \mathit { 1 } } _ { k }$ 表示从 $H$ 到 $\left| L _ { k } \right.$ 的二维几何变换，且可逆； $\downarrow _ { s }$ 是下采样算子， $. h$ 为高斯模糊算子。

重建的高分辨率图像的更新过程表示为：

$$
\boldsymbol { H } ^ { ( n + 1 ) } = \boldsymbol { H } ^ { ( n ) } + \frac { 1 } { K } \sum _ { k = 1 } ^ { K } \boldsymbol { T } _ { k } ^ { - 1 } ( ( ( \boldsymbol { L } _ { k } - \boldsymbol { L } _ { k } ^ { ( n ) } ) \uparrow \boldsymbol { s } ) \boldsymbol { p } )
$$

式中,↑s表示上采样算子; $p$ 表示背投影算子，可设定为h的逆。

本文中选定一幅需要重建的低分辨率肺4D-CT图像，插值重建为初始高分辨率图像 $\boldsymbol { H } ^ { ( 0 ) }$ ,其他相位图像作为已知低分辨率图像序列，根据获得的运动场，采用IBP方法重建出高分辨率4D-CT图像

# 1.3超分辨率重建结果量化评价

本实验采用一个公共可用的数据集[15，该数据集由10组肺4D-CT数据组成，每组数据包含10个相位。各组图像数据层内分辨率为 $0 . 9 7 { \sim } 1 . 1 6 ~ \mathrm { m m }$ ,层间分辨率均为 $2 . 5 \ \mathrm { m m }$ 。实验针对10组数据,在不同相位中选取冠矢状面低分辨率图像，然后分别采用双线性插值，文献[5算法和本文算法进行图像重建。

本文采用图像平均梯度这个量化指标来评价重建结果。平均梯度能够反映出图像细微反差的程度，平均梯度越大，表明影像越清晰、反差越好、细节保持的越好。其定义为：

$$
\nabla \bar { f } = \frac 1 { ( M - 1 ) ( N - 1 ) } \times \sum _ { i = 1 } ^ { M - 1 } \sum _ { j = 1 } ^ { N - 1 } \sqrt { \frac { \nabla _ { i } ^ { 2 } f ( i , j ) + \nabla _ { j } ^ { 2 } f ( i , j ) } { 2 } }
$$

式中， $f ( i , j ) , \nabla _ { i } f ( i , j ) \bar { { \mathbb { F } } } \mathbb { H } \nabla _ { j } f ( i , j )$ 分别为像素点灰度以及其在行、列方向上的梯度； $M$ 和N分别为图像的行数和列数。

# 2结果

# 2.1超分辨率重建结果视觉评价

图2显示了1例典型的冠(矢)状面图像重建结果。从左至右，分别为双线性插值，基于全搜索运动估计超分辨率重建(文献[5」)和本文基于快速亚像素运动估计超分辨率的重建结果。第1、3行分别为冠状面和矢状面图像，为了更清楚地进行效果对比，我们分别将红色方框内的区域进行了放大，置于原图下方显示。从实验结果可看出，本文算法获得的超分辨率重建结果比双线性插值法有很大改进，图像的分辨率有较明显的提高，从局部放大图像来看，肺实质中的血管和周边组织的亮度和清晰度更有明显增强。同时，本文结果相比于基于全搜索的超分辨率重建结果，清晰度亦有所改善。这是因为全搜索只能设定固定步长，为了节约时间，步长不能设置太小，故影响了它的运动估计精度。另外，在运算时间方面，基于全搜索的超分辨重建时间大约 $4 0 ~ \mathrm { m i n }$ 而本文方法只需约 $2 \mathrm { m i n }$ 。时间缩短了近20倍，重建效率明显改进。

# 2.2超分辨率重建结果量化评价

平均梯度既反映了图像中的微小细节反差与纹理变化特征，也反映了图像的清晰度。本文根据图像平均梯度量化指标，针对10组数据重建的图像进行了量化评价。根据式(10)对10组图像的双线性插值，基于全搜索运动估计重建(文献[5」)和本文方法的重建结果分别进行平均梯度计算，结果如表1所示。可见，本文算法较双线性插值方法的平均梯度值显著增大，且与基于全搜索重建结果相比，亦有一定的提高，图像更清晰，细节保持更好。

# 2.3参数讨论

我们选取大小为 $1 6 ^ { * } 1 6$ 的图像块进行匹配运算，其主要原因是：在图像块搜索过程中，常用图像块大小有$8 ^ { * } 8$ 像素、 $. 1 6 ^ { * } 1 6$ 像素和 $3 2 ^ { * } 3 2$ 像素等。若选取大的图像块，将会明显增加搜索计算。如： $3 2 ^ { * } 3 2$ 的块与 $1 6 ^ { * } 1 6$ 的块相比，其块相似度匹配的运算量将增加3倍。而如果图像块过小，由于肺纹理比较稀疏，有时会导致块包含的结构特征较少，影响匹配搜索精度。因此，本文设定图像块大小为 $1 6 ^ { * } 1 6$ 像素，同时考虑肺的运动幅度不大(像素位移一般为10个像素以内），故我们将搜索范围设定为 $1 6 ^ { * } 1 6$ 像素，也就是在目标像素点周围 $1 6 ^ { * } 1 6$ 像素的范围内搜索。

在公式(4)计算中，数值解法将影响结果。我们采用实验图像，比较了5点差分和中心差分方法这两种较典型方法对运动矢量估计的影响，并用均方根误差(RMSE)评价两种方法估计的运动场差异，其结果为$\mathrm { R M S E { = } 0 . 1 5 0 4 }$ 。这意味着使用两种差分方法，得到的运动场差异较小。这是因为，5点差分法是结合前后5个像素点的灰度进行差分计算，其结果有平滑作用。但因为我们在运动估计前，首先对图像进行了平滑预处理，因此，采用5点差分与采用中心差分方法，其结果差异不大是合理的。本文选择了相对简单的中心差分法求解。

IBP方法作为一种迭代处理方法，Irani等[13证明了它的收敛性。他们指出：算法收敛与初始高分辨率图像估计无关，且能较快速收敛(通常在5次迭代以内)。同时，背投影算子 $p$ 是影响数值稳定性和收敛速度的一个主要因素。 $p { \mathrm { . } }$ 取h的逆能获得稳定的解，但收敛较慢，如果p选择脉冲函数，则可快速收敛，但数值稳定性可能会有所降低。文中，我们设定 $p$ 为h的逆，采用数据集1中的图像进行了测试，其迭代误差曲线如图3所示。该曲线呈单调下降趋势，验证了算法的收敛性。

![](images/1b93a3d5bc5f7c4f7b9873e5fb579ecc8cd775e1d1a43941f98e8d5069f05a86.jpg)  
图2实验结果 Fig.2Theexperimentalresults.Fromlefttoright,theresolution-enhancedimagesof thecoronalandsagital viewsobtained by bilinear interpolation,reconstructed basedon fullsearchand our methodare shown in the firstand third rows, respectively. The areas in red box are enlarged and shown below.

# 3结论

本文提出了一种基于快速亚像素运动估计的超分辨率重建算法。与传统的双线性插值方法相比，本文算法可使图像清晰度显著增强。同时，本文算法要优于基于全搜索运动估计的重建算法。由于运动矢量估计速度和精度的优化，本文算法不仅使最后重建图像更清晰，而且计算时间较全搜索算法缩减了近20倍，是很有意义的改进。从视觉效果和定量评估两方面结果综合说明，本文算法能较快速重建出结构更清晰的肺部图像。

# 表1重建图像的平均梯度值

Tab.1 Average gradient value of the images reconstructed by differentalgorithms   

<html><body><table><tr><td></td><td>Bilinear</td><td>Full search</td><td>Our method</td></tr><tr><td>Data 1</td><td>5.67</td><td>8.97</td><td>9.14</td></tr><tr><td>Data 2</td><td>5.18</td><td>7.68</td><td>8.45</td></tr><tr><td>Data 3</td><td>5.37</td><td>7.93</td><td>8.31</td></tr><tr><td>Data 4</td><td>5.41</td><td>7.97</td><td>8.52</td></tr><tr><td>Data 5</td><td>5.32</td><td>7.92</td><td>8.49</td></tr><tr><td>Data 6</td><td>5.57</td><td>8.76</td><td>8.96</td></tr><tr><td>Data 7</td><td>5.44</td><td>8.18</td><td>8.92</td></tr><tr><td>Data 8</td><td>5.29</td><td>7.73</td><td>8.53</td></tr><tr><td>Data 9</td><td>6.29</td><td>8.59</td><td>8.99</td></tr><tr><td>Data 10</td><td>5.64</td><td>7.53</td><td>8.15</td></tr><tr><td>Mean±SD</td><td>5.52±0.22</td><td>8.13±0.49</td><td>8.65±0.33</td></tr></table></body></html>

![](images/bc00acae95c851e27d16c9aa37a9bbdb6e2baa966bfaa054015641fee03742e7.jpg)  
图3迭代误差曲线 Fig.3 Error curve of iterative approach.

# 参考文献：

[1」张书旭，周凌宏，陈光杰,等.4D-CT重建及其在肺癌放疗中的应用研

究进展[J].中国辐射卫生,2008,17(3):375-7.   
[2]Khan F,Bell G,Antony J,et al. The use of 4DCT to reduce lung dose: a dosimetric analysis[J].Med Dosim,2009,34(4): 273-8.   
[3]Li T, Schreibmann E, Thorndyke B,et al.Radiation dose reduction in four-dimensional computed tomography[J].Med Phys,2005,32 (12): 3650-60.   
[4]浦 剑,张军平,黄 华.超分辨率算法研究综述[J].山东大学学报:工学 版,2009,39(1): 27-32.   
[5]苏 衡,周杰,张志浩.超分辨率图像重建方法综述[J].自动化学报, 2013,39(8):1202-13.   
[6]Rousseau F,Alzheimer's Disease Neuroimaging Initiative.A non-local approach for image super-resolution using intermodality priors[J].Med Image Anal,2010,14(4): 594-605.   
[7］肖 珊,王婷婷,张 煜.基于运动估计的肺4D-CT图像冠矢状面超分 辨率重建[J].中国生物医学工程学报,2014,33(2):170-7.   
[8]De Vos L,Stegherr M.Parameterizable VLSI architectures for the full-search block-matching algorithm[J].IEEE Trans Circuits Sys, 1989,36(10): 1309-16.   
[9]Koga T. Motion-compensated interframe coding forvideo conferencing[C]//Proc.NTC'81,1981: 3-5.   
[10]李凤山.视频序列电子稳像技术研究[D].天津:天津大学,2009.   
[11]郭伟伟,章品正.基于迭代反投影的超分辨率图像重建[J].计算机科 学与探索,2009,3(3):321-9.   
[12]Chan SH, VoD T,Nguyen TQ. Subpixel motion estimation without interpolation [C//AcousticsSpeech and Signal Processing (ICASSP),Dallas: IEEE,2010: 722-5.   
[13]Irani M, Peleg S.Motion analysis for image enhancement: resolution，occlusion，and transparency [J].JVis Commun Image Represent,1993,4(4): 324-35.   
[14]李 桐.超分辨率图像重建技术[J].哈尔滨师范大学自然科学学报, 2006,(5): 69-71.   
[15]Castillo R,Castillo E,Guerra R,et al.A framework for evaluation of deformable image registration spatial accuracy using large landmark point sets[J].Phys Med Biol,2009,54(7): 1849-70.   
[16]徐美芳,刘晶红.基于边缘保持的航拍图像凸集投影超分辨率重建算 法[J].液晶与显示,2010,25(6):873-8.

(编辑：黄开颜）