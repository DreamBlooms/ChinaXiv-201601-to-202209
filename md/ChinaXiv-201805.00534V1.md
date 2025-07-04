# 基于直方图规定化的太阳图像增强方法

王瑞1²，徐稚1，杨磊1，季凯帆1(1.中国科学院云南天文台，云南 昆明 650011；2.中国科学院大学，北京 100049)

摘要：太阳图像中包含了各种不同尺度、不同结构以及不同亮度的活动现象，它们都是实测太阳物理的研究目标。这些活动现象经常会使图像显示的跨度过大，导致图像暗弱细节结构被隐藏。对于地基望远镜，由于地球大气对观测数据的影响，也造成图像整体对比度下降。这些都不利于人们直观地从图像中发现感兴趣的太阳活动现象或结构特征。针对这些问题，运用直方图规定化的方法对实测太阳物理中常遇到的几类观测目标图像（太阳极紫外像，太阳光球黑子像，色球活动区像以及色球日珥像）进行处理，通过瑞利分布、双高斯分布以及三重瑞利混合分布等直方图形式实现对这几类图像的显示对比度增强。通过对空间望远镜 SDO的极紫外太阳像和1m新真空太阳望远镜（NewVacuum SolarTelescope,NVST）的色球和光球像的处理展示了该方法的处理效果。结果表明,方法可以有效提高各类太阳活动现象的显示度，便于人们在研究初期发现感兴趣的活动现象。

关键词：太阳图像；直方图规定化；图像增强中图分类号：P182.2 文献标识码：A 文章编号：1672-7673(2018)

图像增强是图像处理的一个重要分支，它通过有目的地强调显示图像的整体或是局部特性改善图像的视觉效果，便于人们辨识图像中感兴趣的内容和特征。直方图规定化作为一种常用的图像增强方法，它的基本思想是根据输入图像强度分布构造一个单调、非线性的映射函数。通过这个映射函数重新分配输入图像各像素值的显示灰度，使输出图像具有目标直方图的分布特征[1-4]。目标直方图可用多种形式给出，可以是另一幅图像的直方图，也可以是对原直方图的修改，还可以是给定形状的直方图等等，这取决于图像显示的不同需求和目的以及显示效果[5-7]。

在实测太阳物理的研究中，人们经常先通过对太阳图像的视觉观察发现自己感兴趣的活动现象或精细结构，然后再针对所关注的目标进行进一步的科学分析[8-9]。但是由于太阳大气的各种物理原因（如密度、温度、磁场强度等），图像的灰度显示范围由图像中的暗区域和部分亮区域的强度决定。通常观测到的数据多为16位的图像，而图像的显示多采用256级灰度，从原始数据到显示灰度图像的线性映射过程中，图像的对比度会被压缩。因此在图像的显示过程中，由于部分过亮区域的存在使得暗区域中的细节结构被隐藏，这使人们关心的很多太阳活动细节无法被清晰地看到。且对于地基太阳观测来说，常常因为地球大气透明度等原因造成图像显示对比度下降，影响人们对各种太阳活动现象的观察和发现。针对这些问题，本文研究了一套基于直方图规定化的方法，对实测太阳物理研究中常涉及的几类观测目标图像进行直方图规定化处理，增强图像中各强度分布区域细节结构的显示对比度。包括对太阳极紫外像以及太阳色球活动区像采用瑞利分布的直方图形式；对太阳光球黑子像采用双高斯分布的直方图形式；对太阳色球日面边缘的日珥像采用三重瑞利混合分布的直方图形式进行规定化处理,并与目前常用的太阳图像对比度增强方法（如对数变换、灰度门限化）进行比较。结果表明，通过本文方法的处理，可有效提高图像整体的显示对比度，同时又提高了特定强度区域的显示度，便于人们从图像中发现和观察感兴趣的太阳活动现象。

# 1直方图规定化理论及算法实现

根据经典的直方图规定化理论，考虑原始图像强度是一个在区间 $[ 0 , L ]$ 上连续分布的随机变量，并且用概率密度函数（ProbabilityDistributionFunction,PDF）表示它的分布特征，其累积分布函数（CumulativeDistribution Function,CDF）为。若规定化直方图的概率密度函数为，累积分布函数为，那么直方图规定化的过程即需要找到一个单调增函数，满足，即满足概率密度直方图对应强度值以下的面积相等[10]。

在实际的数字图像中，各像素强度取值是离散的，它的概率密度函数用各强度值在图像中出现的频次表示（归一化直方图），积分变换用求和变换代替。通过将输入图像的累积分布函数匹配到目标累积分布函数实现直方图规定化[1,II-3]，具体实现过程可分为以下4个步骤：

（1）计算输入图像归一化直方图：， (1)其中，为第个强度值；为具有该强度值的像素个数；为输入图像的总像素个数。

(2） 计算输入图像的累积分布函数CDFi:

# (2)

(3） 计算目标直方图的累积分布函数CDFh：

(3)其中，为归一化目标直方图；为第个强度值。

(4） 由CDFi和CDFh得到映射函数 $M$ ，再由函数 $M$ 给出各目标直方图强度值对应的输入图像强度值。整个映射关系的实现过程如图1（a）。

S1：在CDFh曲线中找到与强度 $Z _ { j }$ 对应的累积分布值 $\mathrm { C D F h } ( z _ { j } )$

S2：将CDFi曲线的累积分布值从0到1逐次与累积分布值 $\mathrm { C D F h } ( z _ { j } )$ 进行比较，直到第 $k { + } 1$ 个强度值对应的累积分布值 $\mathrm { C D F i } ( r _ { k + 1 } )$ 首次大于目标累积分布值 $\mathrm { C D F h } ( z _ { j } )$ 为止。这时就找到了目标累积分布值 $\mathrm { C D F h } ( z _ { j } )$ 在输入累积分布函数CDFi中的近似值为CDFiO;

S3：通过CDFiO值确定与之对应的输入图像强度值。由上述过程得到输入图像强度与规定化输出图像强度之间的映射函数 $M$ 可表示为(4)

![](images/045776e3d2587d6b290ce13805fe70b68ab8cff54c571889c6826a68abff0e56.jpg)  
图1（b）是最终得到的映射函数 $M$ 的输入输出图像强度曲线，将这个映射关系应用到俞入图像中，实现图像的直方图规定化。  
图1累计分布直方图映射算法图解（a），映射函数M曲线（b）。Fig.l Graphical representation of cumulative distribution histogram(a),the mapping function (M)curve (b).

# 2太阳图像直方图规定化

太阳大气活动现象多种多样（比如光球米粒结构，黑子半影纤维，色球暗条结构，色球磁环，增亮现象，日冕磁环，耀斑爆发等）[14-15]。这些活动现象在实测太阳数据中主要涉及太阳光球黑子像、色球活动区像、色球日珥像和太阳极紫外图像。本节介绍如何运用适当的直方图形式对这几类数据进行规定化处理，从而达到增强图像中相应活动现象显示度的目的。

# 2.1太阳极紫外活动区像和色球活动区像的直方图规定化

针对太阳极紫外图像以及色球高分辨率活动区图像，其强度直方图的分布特性类似于瑞利分布，本文运用简单的瑞利分布对他们进行规定化，达到改善图像对比度的目的。瑞利分布直方图表达形式如下：

，(5）其中， $L$ 为规定化直方图的强度级数； $k$ 为取值在区间[0,1]的可调扩展因子，通过对 $k$ 的调整可拉伸直方图的宽度，从而调节输出图像显示的动态范围， $k$ 越大，动态范围越大。

# 2.2光球黑子像的直方图规定化

对于太阳高分辨率光球黑子像，图像强度直方图由两部分组成（呈双峰分布），即低强度值的黑子区域以及高强度值的米粒区域。根据这个特点，运用双高斯分布对其进行规定化处理，从而可以凸显黑子半影纤维的结构、本影亮点，同时使米粒结构对比度也有所增强。双高斯分布直方图的表达形式如下：

其中，第1项（左项）为主高斯项，主要针对光球米粒区域的强度值调整；第2项（右项）为次高斯项，主要针对光球黑子区域的强度值调整； $L$ 为规定化直方图的强度级数， $k$ 为取值区间在[0,1]的主高斯项方差调节系数，通过 $k$ 的调节来改变主高斯分布的半宽，获得满意的增强效果。 $\scriptstyle A _ { 0 }$ 和 $\boldsymbol { A } _ { 1 }$ 分别为两个高斯项的峰值增益，与原图像两个强度区域中总像素个数的开方成正比,且有，其中 $S _ { \mathrm { i } }$ 为各强度区域的像素总数， $N$ 为输入图像的像素总数，$p _ { \mathrm { g } }$ 为规定化直方图 $\mathbf { \nabla } _ { J \subsetneq }$ 是输出直方图强度级的合并大小。分别是对原图像米粒区域和黑子区域强度均值的估计（如（7）式），是对原图像黑子区域强度方差的估计（如（8）式）。原直方图的平均强度(即图像强度均值):

直方图的强度方差（即图像强度方差）：

其中，令表示第个强度值；为该强度值在图像中出现的频率。

为了计算各项参数，首先需要根据原图像强度直方图，将图像强度分为米粒区域和黑子区域两部分。Otsu提出的最大类间方差法（大津法）作为常用的一种自动阈值选择方法，其算法具有简单性以及稳定性量大显著特点[16-17]。在大津法中，阈值t把图像强度分为了前景与背景两大类，为类间方差，最优阈值t由类间方差的最大值得到，即。本文应用该方法通过阈值t将原图像强度分为黑子区域和米粒区域两部分，再根据分割得到的强度子区域计算各分布的参数。

# 2.3色球日珥像的直方图规定化

对于色球日珥高分辨率观测这种特殊数据，图像强度明显由3部分组成（直方图呈三峰分布），即色球日面高强度值区域，色球边缘针状物中间强度区域，以及日面以外的低强度日珥和暗背景区域。针对这一特点，本文提出运用三重瑞利混合分布对其进行规定化处理，从而达到突出日珥结构的目的，同时一定程度地保留了日面色球结构细节。本文给出的三重瑞利混合分布直方图的表达形式如下：

(9)

其中， $A _ { \mathrm { i } }$ 为各瑞利分布的峰值增益，与原图像各强度区域中总像素个数的开方成正比，且计算方法与双高斯峰值增益的计算方法相同； $z _ { \mathrm { t h i } }$ 为各瑞利分布的起始强度值；是输入图像各区域的强度方差（如（8）式）；为强度方差的平均值（即）； $k _ { \mathrm { i } }$ 为各瑞利分布的可调扩展系数，取值区间在[0,1]，用来调节输出图像各部分的显示对比度。

为了确定各瑞利分布项的参数，同样需要先对原图像的强度进行分割。这里用推广到多阈值的大津法对原强度直方图进行两阈值分割[18]，将其分为色球日面（高强度值）区域、色球边缘针状物（中间强度值）区域、日珥及暗背景（低强度值）区域3部分。基本思路是设有两个阈值 $\mathbf { t } _ { 1 } , \mathbf { t } _ { 2 }$ 可将原图像分成3类。强度阈值区间被分成,在阈值空间内找到最优阈值组合使得类间方差最大，即,其中，分别表示每一类出现的概率以及均值。

图2给出了本文直方图规定化程序的详细流程图。经过强度直方图规定化之后，原图像的强度得到了重新分配，再线性映射到256级灰度图像并显示。这使得图像整体的显示动态范围得到扩充，增强了图像各灰度区域的显示度。这里需要强调，对太阳图像的直方图规定化属于图像强度的非线性变换。处理后的图像是为了帮助人们在研究的初始阶段更直观地从图像中发现感兴趣的活动现象，经过灰度对比度增强的图像不直接用于后期的定量科学计算与分析。

![](images/6aba92c07bcb20491b9fc86bdc8459d3f491fa19690a14ed73fd6befe9c04af4.jpg)  
图2太阳图像的直方图规定化程序流程图。 Fig.2Flow chart of histogram specification program of solar image.

# 3结果分析与讨论

太阳日冕的极紫外像包含着各种大气活动现象和大气结构，比如太阳活动区，不同增亮区域附近的暗条通道，磁环等等[19-22]。图3是对空间太阳望远镜的AIA171A图像的处理比较以及相应的直方图。图3(a)是原始图像，由于局部高亮耀斑区域的存在，使得图像中其他暗部区域的细节无法显示。这通过直方图也可以反应（图3d），图像强度值大部分集中在了低强度区域，且高强度区域也有少量分布，这些高强度值的存在使图像中集中在低强度区域的细节被隐藏。图3(b)，3(e)是经过图像处理包中的对数化处理后的图像和直方图分布。经过对数化处理的图像得到明显改善，暗部细节以及日冕磁环都能清晰地看到，但是图像整体的灰度对比度不够，磁环下方的暗条结构细节不是很突出。图3(c)，3(f)是经过本文方法处理后的图像以及直方图分布,这里标准差 $\scriptstyle \sigma = 4 2 4 . 4$ 是由原始图像（图a）的强度分布得到，扩展因子 $k { = } 0 . 8 2$ 是对输出图像直方图的动态范围扩充。从直方图中可以看出，具有中间强度值的像素得到了扩充，图像的对比度明显提高，冕环结构增强的同时暗条结构的细节也有适当的增强。图4是对同一区域的AIA304A图像的处理比较以及相应的直方图，本文对该波段图像同样采用了瑞利分布直方图进行规定化处理。图4（a），4（d)是原始图像和直方图，图像显示整体过暗。图4（b），4（e）是对数化处理后的图像和直方图，可以看出经过对数化处理的图像暗部结构亮度虽然得到了显著提升，但是对比度不够强，不利于暗条等低强度结构的观察。图4（c），4（f）是经过本文的瑞利分布直方图规定化后的图像和直方图，这里原始图像标准差 $\scriptstyle \sigma = 2 7 1 . 4$ ，输出图像扩展因子 $k { = } 0 . 6 4$ 。可以看出，相对于单纯的对数化处理，经过本文方法的处理，图像的对比度和细节都有明显的提高，活动区的暗条环细节更加清晰可见。这有助于人们清晰地看到太阳日冕磁环与色球活动区暗条的细节以及他们的足点结构。

![](images/7292bb962ee90887483eaf55640273a3a74989f98ec6fd544f7993c9bbd7d445.jpg)  
图3AIA171A原图像（a）和直方图（d），AIA171A对数化图像（b）和直方图（e）；AIA171A瑞利分布直方图规定化图像（c）和直方图（f）。Fig.3AIA17image()andtestoa(d),Aimageaferalogproessng(b)dtheistogm(e); eerRayleigh distribution histogram specification (c) and the histogram (f).

![](images/82806b3934568ae8ff3c743776a5a481ba0f5b79447ba4822582335896555397.jpg)  
图4AIA304A原图像（a）和直方图（d），AIA304A对数化图像（b）和直方图（e）；AIA304A瑞利分布直方图规定化图像（c）和直方图（f）。Fig.4AI304Aimage(a)andthehistoga(d),A3Aimageafteralogprocesing(b)andthestogam(e);0eterRayleigh distribution histogram specification (c) and the histogram (f).

在太阳色球的高分辨率观测研究中，对活动区暗条的结构和演化过程以及日珥的动力学特性的研究是实测太阳物理中的重要课题[23-24]。图5展示了对1m太阳望远镜（NewVacuum Solar Telescope,NVST）[25]的Hα色球活动区高分辨率像用瑞利直方图规定化处理的结果，以及与1m太阳望远镜数据处理中所用的强度门限化处理结果的比较。图5(a)，5(d)是原始图像和强度直方图，图像整体偏暗，不利于观察分析。图5(b)，5(e)是强度门限化处理之后的图像和直方图，图像亮度得到了整体的提升，暗条细节清晰可见，但是活动区部分出现过饱和现象。图5(c)，5(f)是经过本文方法处理之后的图像和直方图，在这里原始图像强度标准差 $\scriptstyle \sigma = 3 5 4 0 . 7$ ，输出图像扩展因子 $k { = } 0 . 7 9$ 。可以看出经过处理后，暗条细节清晰可见，同时又没有造成局部亮区域的过饱和现象，图像整体显示对比度也明显提高。

![](images/c4df68b09ac3a588443931c2a5c8f62994cf294a1d2d647e627ed523fa7476a3.jpg)  
图5Hα/NVST太阳色球活动区原图像（a）和直方图（d）；强度门限化处理图像（b）和直方图（e）；瑞利分布直方图规定化 图像（c）和直方图（f）。 Fig.5OriginalimageofsolarchromosphereactivregioofH/NVST(a)andtheistogram(b);mageaftergraycalethresholding(b) andthehistogram(e);image afterRayleighdistributionhistogram specification(c)andthecorresponding histogram (f).

在对太阳光球的高分辨率观测研究中，常常分析黑子半影纤维的动力学特性，比如半影波、半影纤维的扭缠运动等[26-27]。图6是用双高斯直方图对1m太阳望远镜的TiO波段太阳光球黑子像进行规定化处理前后的对比。图6（a），6（c）是未经任何增强处理的太阳黑子像以及直方图，黑子半影结构清晰但对比度不够，不利于观察。图6（b），6（d）是本文双高斯规定化处理后的图像和直方图，图中红线（G1，即主高斯项）给出了对米粒结构强度的规定化曲线，绿线（G2，即次高斯项）给出了对黑子结构强度的规定化曲线。其中主高斯项的原始图像强度标准差 $\sigma _ { 0 } { = } 2 3 2 7 . 8$ ，均值 $\mu _ { 0 } { = } 3 0 6 5 3 . 2$ 次高斯项 $\sigma _ { 1 } { = } 4 4 3 9 . 1$ ，均值$\mu _ { 1 } { = } 1 7 2 6 9 . 9$ ，输出调节系数 $k _ { \sigma } ~ = ~ 0 . 5 4$ ，两个高斯项的峰值增益分别为$A _ { 0 } { = } 2 6 0 8 9 . 7$ ， $A _ { 1 } = 1 6 5 7 . 2 8$ 。从图6（b）中可以看出黑子半影纤维的显示对比度得到了明显增强，半影纤维的结构以及本影亮点更加清晰，有助于人们观察本影亮点的变化以及半影纤维的运动特性。同时，双高斯规定化也增强了米粒的显示对比度，有利于观察米粒结构的演化过程。

![](images/9bcd49586cab866b0445e7c95fde6fd60f22d53669cd776540a01c16bbfcafb1.jpg)  
图6 TiO/NVST光球黑子像（a）和直方图（c），高斯分布直方图规定化之后的黑子像（b）和直方图（d）。Fig.6sunspotimageofTiO/NVT(a)andthestogram(b),imagefterGausiadistributionhistogramspecification(candthehistogram (d).

图7展示了1m太阳望远镜观测到的一个 $\mathrm { H } \alpha$ 日珥数据的原始图像和直方图（图7（a），7（d）），强度门限化处理的图像和直方图（图7（b），7（e））以及本文的三重瑞利混合直方图规定化处理的图像和直方图（图7（c），7（f））。在图7（f）中同时给出了各瑞利分布的轮廓，其中红线（Ray1）是对日面外暗区域的强度规定曲线，绿线（Ray2）是对色球针状物区域的强度规定曲线，青线（Ray3）是对日面色球的强度规定曲线。各部分瑞利分布的峰值增益分别是 $A _ { 1 } = 1 6 9 5 7 . 0$ 5 $\scriptstyle A _ { 2 } = 3 0 0 1 . 6 6$ ， $A _ { 3 } { = } 6 7 2 1 . 9 5$ ，原图强度标准差分别是 $\sigma _ { 1 } { = } 4 7 1 . 2 6$ ， $\sigma _ { { 2 } } \mathrm { { = } } 1 2 0 1 . 0$ ， $\scriptstyle \sigma _ { 3 } = 1 0 8 4 . 9$ ，输出调节系数分别是 $k _ { 1 } { = } 0 . 5 2$ ， $k _ { 2 } { = } 0 . 1 7$ 5 $k _ { 3 } { = } 0 . 1 7$ 。可以看出，在原图像中日面高强度值区域与日面之外的低强度值区域的过大反差，使得暗弱的日珥结构无法清晰地显示。经过1m太阳望远镜常用的强度门限化处理之后，日珥结构虽有所凸显，但是日面区域过饱和，日面与日珥之间的过渡区域结构消失。而经过本文的三重瑞利直方图规定化处理之后，日面色球结构得以保留，日面边缘色球结构也得到了一定程度的保留。与此同时，日珥结构更加清晰可见，更有利于人们的观察分析。

![](images/7ad8bc37f70b466406db477bcc008edad21933d7fa574141360de118349d6f8e.jpg)  
图7Hα/NVST太阳边缘日珥原图像（a）和直方图（d）；强度门限化处理图像（b）和直方图（e）；瑞利分布直方图规定化图 像（c）和直方图（f）。 Fig.7OriginalimageofsolarlimbprominenceofH/NVT(a)andthehistogram(b);imageaftergrayscalethresholding(b)andthe histogram (e); image after Rayleigh distribution histogram specification (c)and the histogram (f).

为了定量说明本文程序对上述各波段太阳图像显示对比度的增强效果，需要用到一些评价图像对比度的参数分析直方图处理前后图像对比度的变化情况。本文分别用图像的标准差（standard deviation,SDEV），文[28]提出的增强测量（measure of enhancement,EME）以及基于熵的增强测量（measure of enhancement by entropy,EMEE）参数来衡量图像对比度的变化[28]。表1列出了对空间太阳望远镜的AIA171A色球图像，AIA304A日冕图像以及1m太阳望远镜的Hα色球图像，TiO光球图像和色球日珥像处理前后的SDEV、EME、EMEE的计算结果。其中，AIA171A、AIA304A、Hα/NVST活动区（AR）和Hα/NVST日珥（prominence）表格中左侧为未处理图像的评价参数，中间为对数化或强度门限化处理图像的评价参数，右侧为本文的瑞利直方图规定化处理图像的评价参数；TiO/NVST表格中左侧为未处理图像的评价参数，右侧为本文的双高斯直方图规定化处理图像的评价参数。从这些参数中可以看到，经过本文的处理，图像的对比度均好于原图像以及一般的对数化处理和强度门限化处理的图像，这与从图像的视觉效果得出的结论相一致。

表1图像对比度增强测量参数Tab.1 Measurement parameters for Image contrast enhancement  

<html><body><table><tr><td colspan="4"></td><td colspan="3">EME</td><td colspan="3">EMEE</td></tr><tr><td>AIA171A/SDO</td><td>424.4</td><td>2125.5</td><td>2723. 2</td><td>14.43</td><td>10.91</td><td>16.58</td><td>2.014</td><td>1.513</td><td>7.273</td></tr><tr><td>AIA304A/SDO</td><td>271.4</td><td>1810.1</td><td>2389. 1</td><td>21.49</td><td>16.10</td><td>28.40</td><td>3.968</td><td>2.166</td><td>19.15</td></tr><tr><td>Ha/NVST(AR)</td><td>2719.4</td><td>5539.8</td><td>7573. 9</td><td>4.470</td><td>17.31</td><td>25.68</td><td>0.294</td><td>2.672</td><td>10.73</td></tr><tr><td>TiO/NVST(sunspot)</td><td>3626.9</td><td></td><td>5687. 5</td><td>4.687</td><td></td><td>9.672</td><td>0.312</td><td></td><td>0.889</td></tr></table></body></html>

<html><body><table><tr><td>Ha/NVST(prominence ）</td><td>3914.4</td><td>3997.0</td><td>4843. 6</td><td>21.56</td><td>21.23</td><td>33.54</td><td>4.031</td><td>3.995</td><td>38.71</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# 4结论

本文运用基于直方图规定化的图像增强方法，提出了用瑞利分布、双高斯分布以及三重瑞利混合分布的直方图形式对实测太阳物理中常见的几类观测数据（即太阳极紫外像，色球高分辨率像，光球黑子高分辨率像，以及色球日珥像）进行直方图规定化处理。实现了对这些图像的显示对比度增强的目的，提高了图像中人们感兴趣的几类活动现象的显示清晰度，有助于对这些太阳活动现象的观察与分析。文中还用了SDEV，EME，EMEE等参数对对比度增强的效果进行了定量的分析和评价。从这3个参数上看，在对 SDO望远镜的AIA171A和AIA304A极紫外图像，1m太阳望远镜的高分辨率Hα色球图像和TiO光球图像进行适当的直方图规定化处理之后，显示对比度均有所提升。

因此，经过本文所设计的直方图规定化程序处理之后，可有效地实现对不同波段太阳像的不同活动现象进行有目的的显示增强，有利于人们从图像中发现和观察自己感兴趣的活动现象。但需要说明的是，太阳大气活动现象复杂，本文只是对常见的几类活动现象运用双高斯直方图和（三重）瑞利直方图处理并得到较好的效果，说明了该方法的可行性。在未来的研究中，对于其他活动现象以及观测情况，需要进一步探索合适的直方图形式进行处理，得到所需效果。

# 参考文献

[1] Gonzales R C. woods R E. Digital iamge processing [M]. Englewood: Prentice Hall 2002.   
[2] Thomas G,Flores-Tapia D,Pistorius S.Histogram specification: a fast and flexible method to process digital images[J].IEEE Transactions on Instrumentation and Measurement,2011,60(5):1565-1578. [3]Gayakwad S B,Ravishankar S S. Image enhancement by Histogram Specification[J]. International Journal ofRecent Advances in Engineering& Technology,2014,2(4):10-12.   
[4] Maini R,Aggarwal H.A comprehensive review of image enhancement techniques [J]. Journal of Computing,2010,2(3): 8-13.   
[5] Kenneth R C. Digital image processing [M]. Englewood: Prentice Hall, 1996.   
[6] Kong J, Jiang M, Halidan A,et al. Image Specification Based on Multimodal Gaussian-Like Function[M//Unifying Electrical Engineering and Electronics Engineering.Springer New York,2014:1197- 1205. [7]Cobra D T.A generalization of the method of quadratic hyperbolization of image histograms[C]// Proceedings of the 38th Midwest Symposium on Circuits and Systems.1995:141-144. [8]Glackin DL, Martin S F.Application of digital image processing techniques to faint solar flare phenomena[Cl//Conference on Applications of Digital Image Processing to Astronomy. 1980: 236-242.   
[9]Morgan H.An observation of solar active region expansion into the heliosphere[J]. Monthly Notices of the Royal Astronomical Society: Letters,2013,433(1): L74-L78. [10]Papoulis A,Pillai S U.Probability,random variables,and stochastic processes [M].New York: Tata McGraw-Hill Education, 2002.   
[11] Wegener M. Destriping multiple sensor imagery by improved histogram matching[J]. International Journal of Remote Sensing,1990,11(5): 859-875.   
[12] Stricker MA, Orengo M. Similarity of Color Images [C]//Storage and Retrieval for Image and Video Databases (SPIE).1995:381-392.   
[13] Fecker U, Barkowsky M, Kaup A. Improving the prediction eficiency for multi-view video coding using histogram matching [C]//Picture Coding Symposium (PCS 2006). 2006. [14]Wedemeyer-Bohm S,Lagg A, Nordlund A. Coupling from the photosphere to the chromosphere and the corona [J]. Space Science Reviews,2009,144(1-4): 317-350.   
[15] Berkebile-Stoiser S,Gomory P, Veronig A M, etal.Multi-wavelength fine structure and mass flows in solar microflares [J].Astronomy & Astrophysics,2009,505(2):811-823. [16] Otsu N．A threshold selection method from gray-level histogram [J]． IEEE Transactions on Systems Man & Cybernetics，1979，9(1) :62-66.   
[17] Liu D, Yu J. Otsu Method and K-means[Cl//Ninth International Conferenceon Hybrid Inteligent Systems. 2009:344-349.   
[18] Liao P S, Chen T S,Chung PC.A fast algorithm of multilevel thresholding [J] .Journal of Information Science and Engineering,2001,17(5) : 713-727.   
[19] Guglielmino SL,Rubio LR B, Zuccarello F,et al.Multiwavelength observations of small-scale reconnection events triggered by magnetic flux emergence in the solar atmosphere [J]. The Astrophysical Journal,2010,724(2): 1083-1098.   
[20] Suresh S, Dube R.A multi-channel approach for segmentation of solar corona in images from the solar dynamics observatory [C]/Image Processing Workshop (WNYIPW),2012 Western New York.2012: 33-36.   
[21] Martens PC H,Atrill G DR,Davey AR,et al. Computer vision for the solar dynamics observatory (SDO) [J]. Solar Physics,2012,275(1-2): 79-113.   
[22] Cirtain JW, Golub L, Winebarger AR, et al.Energy release in the solar corona from spatially resolved magnetic braids [J].Nature,2013,493(7433): 501-503.   
[23] Lin Y.Filament thread-like structures and their small-amplitude oscillations [J]. Space Science Reviews,2011,158(2): 237-266.   
[24] Xu Z, Jin Z Y,XuFY, et al. Primary observations of solar filaments using the multi-channel imaging system of the New Vacuum Solar Telescope[Cl/Proceedings of the International Astronomical Union.2013: 117-120.   
[25] Liu Z, Xu J.1-meter near-infrared solar telescope [C]/Astronomical Society of India Conference Series. 2011.   
[26] Ichimoto K,Suematsu Y,Tsuneta S,et al.Twisting motions of sunspot penumbral filaments [J].Science, 2007, 318(5856): 1597-1599.   
[27] Scharmer G B,Henriques VM J, Kiselman D,et al. Detection of convective downflows in a sunspot Penumbra[J]. Science,2011,333(6040): 316-319.   
[28] Agaian S S, Paneta K, Grigoryan A M. A new measure of image enhancement [C]/IASTED International Conference on Signal Processing & Communication Citeseer. 20oo:19-22.

# Solar image enhancement based on histogram specification

Wang Rui1,²,Xu Zhi',YangLei¹, JiKaifanl 1.Yunnan Observatories,Chinese Academy of Sciences,Kunming 65oo11, China; 2.University of Chinese Academy of Sciences,Beijing1ooo49,China

Abstract: The solar image contains a variety of different scales, different structures and different brightness active phenomena.These phenomena often causes the span of the image is too large,resulting in hidden of faint detail structures.Furthermore,for the ground-based telescope, because of the influence of the earth atmosphere on the observations,the overall contrast of the image is decreased. These factors are not conducive for people to view the features of interest from images intuitively. To solve these problems, this paper uses the histogram specification method to deal with several targets (solar extreme ultra-violate image, sunspot, solar $\mathrm { H } \alpha$ active region and solar prominence） commonly encountered in solar observations.In this paper, the Rayleigh distribution,Double-Gaussian distribution and Triple-Rayleigh distribution is proposed to realize the contrast enhancement of these images. The effect of this method is demonstrated by the processing of solar ultraviolet images from Atmospheric Imaging Assembly on the Solar Dynamics Observatory (AIA/SDO), solar $\mathrm { H } \alpha$ image and sunspot image from New Vacuum Solar Telescope (NVST). The results show that this method can effectively improve the visibility of these solar active phenomena,and it is convenient for people to find interesting active phenomena in the early stage of the study.

Keywords: Solar image; Histogram specification; Image enhancement