# 基于优化后透射率和半逆法的暗通道图像去雾方法

彭莉婷，李波

(武汉科技大学 智能信息处理与实时工业系统湖北省重点实验室，武汉 430065)

摘要：为了解决去雾过程中图像边缘产生光带的情况和去雾之后图像整体变暗的现象，提出了一种新颖的基于优化后透射率和半逆法的图像去雾算法。首先，针对图像边缘处暗通道失效情况，运用透射率修正机制来消除边缘处的光带现象，从而提高暗通道先验的适用范围；其次，从大气散射模型出发，利用半逆算法得到大气整体光照值；最后，针对去雾之后整幅图片颜色变暗淡的现象，采用基于小波变换的图像对比度算法来进行增强处理，改善去雾图像的视觉效果。实验结果表明，该算法能够更有效地去雾，而且去雾能力优于原算法。

关键词：暗通道先验；透射率；小波变换；半逆法；图像去雾 中图分类号：TP391.41 doi:10.3969/j.issn.1001-3695.2018.03.0329

# Dark channel prior image dehazing method based on optimization transmission and semi-inverse algorithm

Peng Liting, Li Bo (HubeiKeyLaboratoryofIntelligent InformationProcessing&Real-timeIndustrialSystem,Wuhan UniversityofScience& Technology,Wuhan 430065,China)

Abstract: Inorderto solvethephenomenonofthe edges of the image produce light bands in thede-hazing process and the whole image'scolorbecomes dimafterde-hazing,this paper proposedanovelalgorithm basedon improved transmissionand semi-inversealgorithm.Aimingatthedarkchannelpriorfailureattheedgeoftheimage,atransmissioncorrction mechanism is proposed inthispapertoeliminatethebandphenomenonattheedgeandimprovetheappicationof thedarkchannel prior. Secondly,basedontheatmosphericscatering model,theatmosphericlightisobtainedbyusingthesemi-inversealgorithm. Then for the situationthatthecolorofthe whole image become dim after de-hazing,the image contrast algorithm based on waveletransform isused to enhance the stretchingtreatmentandimprovethe visual efectof image.The experimentalresults showthat thealgorithmcanremove fog more effectively,andtheabilitytode-hazeisbettr thantheoriginalalgorithm.

Key words: dark channel prior; transmission; wavelet transform; semi-inverse; image de-hazing

# 0 引言

计算机视觉和数字图像处理技术的飞速发展，使其在智能交通、遥感监测、资源勘查等诸多领域都得到了广泛应用。然而在恶劣的天气条件下，如雨雪、雾霾等，室外的计算机视觉系统受到大气中随机介质的影响，导致成像传感器采集到的景物图像在一定程度上退化和降质。为了提高计算机视觉系统在恶劣天气下工作的效果，研究图像去雾技术具有非常重要的意义。

一般而言，模糊图像的修复方法可以分为基于图像处理的方法和基于物理模型的方法两大类。前者包括直方图均衡[1、小波变化、retinex 算法[2和滤波算法等，这些方法都被很广泛地运用在图像去雾上。这些方法没有考虑到图像降质，适用范围广，但是很难得到较好的恢复图像，往往造成恢复的图像对比度过强、部分区域细节丢失等现象[3]。后者主要是基于大气散射模型的方法。而利用大气散射模型将有雾图像恢复到无雾图像的方法总体上可以分成基于深度信息的方法、基于大气光偏振特性的去雾算法、基于暗通道先验知识的方法三类。在单幅有雾图像处理方法中，大部分去雾算法都假设图像满足大气散射模型，利用一个附加的深度图或者单独的透射图来增强图像的可见度。McCartney[4]引入大气散射模型来描述雾图像中的信息，这一模型已经被许多计算机视觉和计算机图形学研究人员广泛研究。Schehner和Shwartz等人[5.6提出了一种基于用偏振器在各个不同方向拍摄的多幅图片的图像恢复算法。在文献[7,8]中，在不同天气条件下捕捉到的多个图像被用来获得更多的约束来去除雾霾。Tan[认为清晰图像与雾化图像相比，具有更高更好的对比度，于是他采用了最大化局部对比度的方法实现去雾。该方法没有从图像退化的机理入手，导致去雾之后图像存在过饱和现象。Fattal[10]假设透射率与表面色度在局部是不相关的，该算法取决于数据的统计特性，由于浓雾时颜色信息过少，极易造成统计不可靠。He等人[1在暗通道先验方面做出了重大贡献，通过加入先验约束条件，使用软抠图方法对初始投射图进行细化并取得成功的处理结果，但是软抠图技术在计算上太过耗时。根据这个缺点，He 等人[2]在2010 年用导向滤波代替软抠图来加速。但是计算复杂度还是比较高；另外在天空区域和边缘区域的透射率估计不准确，极易导致去雾后的图像失真等问题。赵锦威等人[13]针对基于暗通道先验图像去雾方法中存在的大气光误判问题，采用SVM对候选大气光进行可靠性判断，相比之前的方法减弱了光晕，保持了饱满的深度信息，但是对于有雾图像中存在的物理上不符合暗通道先验的区域，算法结果容易产生色彩偏色等不良效果。肖进胜等人[14]对天空中颜色变形进行了一系列的改进，其中去雾效果还是明显的，但是图像中的细节保持的不是很好。文献[15\~17]对不符合暗通道先验的天空部分做出改进，但是他们均是对图像分割得到的天空单独处理，严重依赖于分割效果。邱东芳等人[18]基于暗通道先验的去雾算法，对此改进了求大气光值的方法，有效去除了光晕，解决了天空区域的颜色失真问题，大大降低了求大气光值的时间复杂度；但是由于复原图像进行了滤波处理，会导致图像的高频信息丢失、边界模糊。沈逸云等人[19]对估计值过高的大气光进行自适应校正，并且对透射率进行一个优化校正；但是实验表明文中所采用地天空检测方法的准确度会对大气光自适应校正结果产生一定的影响。

本文对原有暗原色先验方法的不足提出一些改进措施：为了减少边缘处出现的光带情况，在暗通道先验中用改进的透射率来代替原始的透射率估计值，一定意义上来消除光带现象；为了让大气光值更加准确，利用半逆法来修正大气光值；针对去雾之后整幅图片颜色变暗淡的现象，采用基于小波变换的图像对比度算法来进行增强处理，在提高图像对比度的同时，还可以使图像整体颜色更加自然更有深度。

# 1 相关工作

# 1.1大气散射模型

在计算机视觉和计算机成像中，暗通道先验模型被广泛地用来描述一张模糊图像的信息。具体公式[9-21]如式（1）所示。

$$
I ( x ) = J ( x ) t ( x ) + A ( 1 - t ( x ) )
$$

其中： $I ( x )$ 是观察者接收的有雾图像在 $x$ 像素点的亮度； $J ( x )$ 是清晰图像； $A$ 代表周围环境的大气光强； $t ( x ) \in [ 0 , 1 J$ 是大气反射光的透射率， $t ( x ) = e ^ { - \beta d ( x ) }$ 。

# 1.2暗通道先验

He等人[1着眼于无雾图像的统计特征，通过对收集到的大量的无雾图像做实验，发现了这个客观存在的统计规律，即在绝大多数户外无雾图像中的任意局部小块中，总存在一些(至少有一个）像素，它们的某一个或几个颜色通道的强度值很低且接近于零，本文将此称为暗原色[]。本文给暗通道一个数学定义，对于任意的输入图像 $J ( x )$ ，其暗通道可以用式（2）表示为

$$
J ^ { d a r k } ( x ) = \underset { c e ( r , g , b ) } { m i n } ( \underset { y = \Omega ( x ) } { m i n } ( J ^ { c } ( y ) ) ) \approx 0
$$

其中： $J ( y )$ 表示彩色图像的每个通道； $\Omega ( x )$ 表示以像素 $x$ 为中心的一个窗口。对大气散射模型式(1)两边分别在三颜色通道进行局部区域大小为 $\Omega ( x )$ 的最小值滤波，则得到

$$
m i n ( \operatorname* { m i n } _ { { x \in \Omega \left( x \right) } } ( \frac { I ^ { c } ( y ) } { A ^ { c } } ) ) = t ^ { \prime } ( x ) m i n ( \operatorname* { m i n } _ { { x \in \Omega \left( x \right) } } ( \frac { J ^ { c } ( y ) } { A ^ { c } } ) ) + ( 1 - t ( x ) )
$$

由式(2)和(3)可以得到粗略透射率 $t ( x )$ ：

$$
t ( x ) = 1 - { m i n } ( \operatorname* { m i n } _ { y \in \Omega ( x ) } ( \frac { I ^ { c } ( y ) } { A ^ { c } } ) )
$$

但在现实生活中，即使是天气晴朗的时候，空气中也会存在着一些颗粒，因此，看远处的物体还是能感觉到雾的影响。另外，雾的存在能让人感受到场景的深度。所以在做去雾实验时就有必要刻意地保留一定程度的雾。因此，在式(4)中引入一个值在[0,1]间的因子，则式(4)就修改成

$$
t ^ { \prime } ( x ) = 1 - w m i n ( \operatorname* { m i n } _ { y \in \Omega ( x ) } ( \frac { I ^ { c } ( y ) } { A ^ { c } } ) ) , 0 < \omega < 1
$$

若大气光强已知，由式(1)和(5)可以得到复原后无雾的图像：

$$
J ( x ) = \frac { I ( x ) - A _ { 0 } } { m a x ( t _ { 0 } , t ^ { \prime } ( x ) ) } + A _ { 0 }
$$

# 1.3光带现象

图像去雾时，由于不知道景深的确切信息，在物体景深突变的边缘处会出现光带现象，即产生的白色光晕。有光带效应的图像的边缘细节反而比没有光带效应的图像边缘细节多。从人类的视觉感受出发，有光带效应的图像会使图像视觉效果变差。如果采用没有修复的透射率复原无雾图像就会产生白色光晕。如图1所示，可以看到在屋顶、国旗与天空的交界处都出现了光晕现象，影响去雾图像的视觉效果。

![](images/bcdb3c1885b83d28f2ea0d42a4415ba7e1eaa47e66f39f941a2729e23cff3b81.jpg)  
图1去雾过程中出现的光带效应

# 2 暗通道优化算法

# 2.1优化后的算法流程

本文首先是对原图像求取R/G/B颜色通道图，再经过改进后的最小值滤波，之后用Canny算子检测边缘部分。如果是边缘部分就用小模板(3x3)来求取 $t _ { 1 } ( x )$ ，如果不是边缘部分就用大模板(6x6)来求取 $t _ { 2 } ( x )$ 。然后将这两个部分的透射率相加得到粗略透射率 $t ( x )$ 。再让粗略透射率通过中值滤波和维纳滤波，得到最后优化过的透射率 $t ^ { ' } ( x )$ 。整个求取过程中还需要估计大气光值 $A$ 。由于图片中可能会有白色物体存在，导致最亮的像素可能并不存在于天空区域，所以采用了半逆法来获取大气光 $A$ 的估计值。最后获得去雾之后的图像。经过前面步骤之后的图片整体会变得暗淡，这时需要小波变换对比度增强算法来增强图像。这样就得到最终的去雾图像 $J ( x )$ 。图2是本文算法流程。

![](images/311584c45236c5bbedfc20d0b0902979f2bd5ec3f28076a0e4c287710f272395.jpg)  
图2算法流程

# 2.2半逆法求大气光值

He 等人[选择图像暗原色通道中值最大的 $1 \%$ 的像素点作为整体大气光值，这种选择思路基于图像中包含天空区域和没有纯白色的饱和点。与暗原色先验知识类似，Ancuti 等人[22]提出在雾区除了深度不连续的区域，亮度值变化非常小。基于这个假设，将降质图像 $I ( x )$ 与其半逆图像 $I s i ( x )$ 转换到 HSI或者CIE色彩空间比较色调差异，并设定一色差阈值，以这个阈值为判据将降质图像分为雾区和非雾区，检测出雾区，进一步在邻近天空区域的雾区中选择最亮像素点作为整体大气光值。产生的半逆图像表示为 $I _ { s i } ( x ) = I I _ { s i } ^ { r } , I _ { s i } ^ { s } , I _ { s i } ^ { b } J$ ，在RGB三通道中分别用原像素点和逆像素点的最大值代替原像素点。半逆图像公式可描述为

$$
\begin{array} { c } { { I _ { s i } ^ { r } ( x ) = m a x ( I ^ { r } ( x ) , 1 - I ^ { r } ( x ) ) } } \\ { { { } } } \\ { { I _ { s i } ^ { g } ( x ) = m a x ( I ^ { g } ( x ) , 1 - I ^ { g } ( x ) ) } } \\ { { { } } } \\ { { I _ { s i } ^ { b } ( x ) = m a x ( I ^ { b } ( x ) , 1 - I ^ { b } ( x ) ) } } \end{array}
$$

其中： $I ^ { r } ( x )$ 、 $I ^ { g } ( x )$ 和 $I ^ { b } ( x )$ 表示RGB三个通道的像素灰度值。通过研究计算：

$$
a b s ( I _ { s i } ^ { h u e } ( x ) - I ^ { h u e } ( x ) ) < T
$$

其中： $T$ 是预先设定的阈值，按照视觉特性取 $T = 1 0 ^ { \circ } ~ ; ~ I ^ { h u e } ( x )$ 表示降质图像的色度； $I _ { s i } ^ { h u e } ( x )$ 表示其半逆图像的色度。将原始降质图像 $I ( x )$ 和其半逆图像 $I s i ( x )$ 转换到HIS或者CIE色彩空间后比较色度差异，并把所有小于阈值 $T$ 的那些图像像素作为雾气区域，然后选择雾气区域的最亮像素点作为整体大气光照值$A$ 。但是这样的方法也不能很好地解决白色物体对整体大气光值估计的干扰，所以本文采用了改进的半逆检测算法来确定整体大气光照值。首先，取雾气区域亮度分量上方1/10的像素区域做四叉树分割，将这些区域分为四个小块区域，分别比较四个小块区域灰度均值与灰度方差之差，选择差值最小的区域，继续做四叉树分割，一直到选出的矩形区域达到固定边宽，停正分割，取这个矩形区域中最大灰度值做为整体大气光照值A。

# 2.3粗略透射率的求解

用于求暗图像的最小值滤波的窗口 $\Omega$ ，在整幅图像中采用同样大小的窗口，这表明图像中多数像素点的透射率是用它的临近区域像素点的透射率作为计算值，而非其本身的透射率值。由此推断，在整幅图像中场景点透射估计暗含了一个这样的假设，即认为在图像局部区域内，它们的透射率值相等或相近。这个假设在场景点的景深相等或相似是合理的，因为透射率与场景景深相关，这正好符合图像局部区域内场景景深变化缓慢的这一事实。如果在最小值滤波窗口 $\Omega$ 内场景景深发生变化，上述结论就不成立，求暗图像采用的最小值滤波就会使景深变化处的暗图像被低估，景深边缘一侧的粗略透射率 $t ( x )$ 被过高估计，导致光带效应现象的产生，影响去雾图像的质量。He 等人的去雾算法是采用窗口大小为 $1 5 \times 1 5$ 的最小值滤波求暗图像，导致粗略透射率被错误估计，进而导致在景深边缘处产生光晕。为了解决这个问题，本文求粗略透射率时用的不再是文献[12]中的最小值滤波算法，而是改进后的最小值滤波。为了让求出来的粗透射率效果更好一些，那么最小值滤波模板的范围就不是滑动窗口中一出现边缘部分就用小模板，而是当窗口的中心点是边缘时才能够用小模板。

实验发现：最小值滤波窗口 $\Omega$ 大， $J ^ { d a r k } ( x )  0$ 的程度越大，去雾程度也越大，但是会在景深突变处产生光带效应现象；最小值滤波窗口越小，虽然光晕效应现象减弱，但 $J ^ { d a r k } ( x )  0$ 的程度也越小，去雾程度减弱。针对这一问题，对求出来的暗图像，本文采用在边缘处用小模板，即3x3的模板；非边缘处采用大模板，即6x6的模板，这样既能保证有效的去除雾对图像的影响，又能降低光带效应现象的产生。暗图像的变化，导致粗略透射率发生变化。景深边缘的粗略透射率记为 $t _ { { \it e d g e } } ( x )$ ，非景深边缘的粗略透射率记为 $t _ { n o t e d g e } ( x )$ ，则整幅图像的粗略透射率由式（7）变化为

$$
t ( x ) = t _ { e d g e } ( x ) + t _ { n o t e d g e } ( x )
$$

# 2.4修复粗略透射率

透射率图越平滑，就能恢复出更多的图像节点。在文献[12]中优化粗略透射率时，采用的是导向滤波来修复粗略透射率。该模型被证明在图像超分辨率[23]、图像消光[24]和除雾[11]等操作中是非常有用的。但是本文为了更接近实际的暗原色和保留住更多图像节点，对暗原色图采用的是先进行中值滤波，再通过维纳滤波。

通过中值滤波过程，虽然可以去除暗原色中所含的原始图像的部分错误信息，但未完全去除，此时的暗原色图也不够平滑。因此，下一步采用维纳滤波对透射率进行细化，去除暗原色图中的错误信息的同时保持着透射率在局部区域的平稳变化。

通过图3能看到对暗通道进行大气光值和透射率优化之后，效果比较明显，随便也可以来对比一下粗略透射率(图3(d))和优化之后透射率(图3(e))的区别：图3 (d)中三处红色框框的图像是比较模糊的，基本上看不出建筑物的形状，但是在(e)中，优化透射率后建筑物的形状就很明显。

![](images/75790cf0481c1e08bbe56c259c6720ffb55d34fe6709a0de441c63d451ae73d0.jpg)  
图3城市粗略透射率比较

# 2.5小波变换对比度增强算法

信号从产生、传输与处理的过程中有多个环节，每个环节中的数据都不可避免地会受到外界引入的噪声或者算法本身产生的噪声不同程度的干扰，因而造成对信号分析的极大困扰。所以，信号去噪处理环节就很重要[25]。小波变换下的图像对比度增强技术实质上是通过小波变换把图像信号分解成不同子带，针对不同子带应用不同的算法来增强不同频率范围内的图像分量，突出不同尺度下的近似和细节，从而达到增强图像层次感的目的。

根据小波的多分辨率分析原理将图像进行多级二维离散小波变换，可以将图像分解成图像近似信号的低频子带和图像细节信号的高频子带。其中，图像中大部分的噪声和一些边缘细节都属于高频子带，而低频子带主要表征图像的近似信号。为了能够在增强图像的同时减少噪声的影响，可以对低频子带进行非线性图像增强，用于增强目标的对比度，抑制背景；而对高频部分进行小波去噪处理，减少噪声对图像的影响。最后小波重构得到增强的去雾图像。基于小波变换的图像增强步骤如图4所示。

![](images/25b83903b41a45a7564a2ca950ec8e65732b735c816d5a741d7469fc5ebc42ca.jpg)  
图4小波变换图像增强流程

图5(b)是在得到透射率和大气光值之后所求取的去雾图像。在此时会看到图像近处的建筑物颜色有点偏暗，部分细节被隐藏，而远处的建筑物并没有很好地被描述。图5(c)是经过小波变换增强算法之后的无雾图像。在这张图片中，明显感觉图像的颜色会有所提升，细节会保持得更好，而远处的雾也能去除得更干净。

![](images/ccdd43639e3401460c271e80c9cd90b9f5037363bb472b6ffc8477569cd19d20.jpg)  
图5小波变换前后图像细节增强的对比

# 3 实验结果

为了验证所提出的有雾方法的有效性，利用多幅含雾图像对其进行测试，并且与He、Zhao、Qiu、Shen的方法进行比较。所有的算法都是在MATLABR2014a上实现的，实验系统环境是处理器为3.50GHz和4GBRAM的PC。

# 3.1主观分析

所有的去雾算法对一般室外图像能够得到非常好的结果，但是大多数现有的去雾算法对白色都是不敏感的，因此本文特意对一些具有白色或灰色区域的挑战性图像进行处理来更客观地比较这几种算法的效果。本组实验用不同的算法分别对7幅图像进行去雾，去雾效果对比如图6-12 所示。图6\~12中：(a)为原有雾图像；(b)为He[1等算法的去雾效果，边缘部分处理较差，在天空区域和边缘区域的透射率估计不准确，会使得去雾后的图片出现过饱和并伴随着“halo 效应"；(c)为Zhao[12]算法去雾效果，相比之前的方法减弱了光晕，保持了饱满的深度信息，但是对于有雾图像中存在的物理上不符合暗通道先验的区域，算法结果容易产生色彩偏色等不良效果，比如在6(c)和8(c)中图片都出现了不同程度的色彩偏差；(d)为Qiu[18]算法去雾效果，该算法改进了求大气光值的方法，但是由于复原图像进行了滤波处理，会导致图像的高频信息丢失、边界模糊；(e)为 Shen[算法的去雾效果，该算法是对估计值过高的大气光进行自适应的校正，并且对透射率进行了优化校正，但是实验表明文中所采用的方法对天空区域效果还是有误差；(f)为本文改进算法去雾图，可以看出本文算法效果图去雾效果最强，而且在颜色上更加自然，亮度更加明亮，场景的层次感更加丰富。

![](images/ed4e6822d24b9b9e1b228849e18ac3c19a40c976cc4be7f1fcefa0eb4b25194a.jpg)  
图6天安门图的去雾效果比较

![](images/15b2e4d2bb0e2b9f00148e328024a66b71a98354bdd17582969534ed3910ee1a.jpg)  
图7canon 图的去雾效果比较

![](images/6e01369aa2b05427983756136ecd87abe5bd9a70b79a7f8cedd0f35765b215c9.jpg)  
图8city_4图的去雾效果比较

![](images/d321b4408a860bfa3f693acaefc6fbf64f724e10cc5e8d32f0507c7a32e0b6cd.jpg)  
图9cones图的去雾效果比较

![](images/eff0bedb468992bd836cfca2a0b0630e1c30fa1be4fe8734284232e09da1bca9.jpg)  
图10ny_2图的去雾效果比较

![](images/59062b7a79d94daeed538abba44fafc2c1bf6b19bfa5ad58ff9e433d281cdb72.jpg)  
图11pumpkins 图的去雾效果比较

![](images/512a21ec63533e7304e9e7445554da3f00310d27fb5b315fcb7772163aa0e166.jpg)  
图12体育馆图的去雾效果比较

注：图6\~12为本文与其他方法的对比效果。从左往右依次是:(a)原始图像；(b)He的结果；(c)Zhao 的结果；(d)Qiu的结果；(e)Shen的结果；(f本文结果

# 3.2客观分析

在客观评价中，为了更加直观地比较各种算法的性能，本文使用到3个参数，分别是对比度(contrast)、信息熵(entropy)和结构相似度(SSIM)来作为比较。Contrast为图像对比度，其值越大越好；entropy是图像的信息熵，表示的是图像中所包含的信息值，越大越好；SSIM 是描述去雾前后两幅图像的结构相似度，结构保存越完好，去雾图像保留的有用信息就越多，所以该值也是越高越好，最大的为1。对比结果如表1所示。

表1图像的定量分析  

<html><body><table><tr><td>Image</td><td>Criterion</td><td>original</td><td>He</td><td>Zhao</td><td>Qiu</td><td>Shen</td><td>Ours</td></tr><tr><td rowspan="3">Tiananmen</td><td>Entropy</td><td>7.2641</td><td>7.2161</td><td>7.3266</td><td>7.3312</td><td>7.3495</td><td>7.3672</td></tr><tr><td>Contrast</td><td>80.1589</td><td>92.1512</td><td>105.6297</td><td>118.2729</td><td>125.1397</td><td>136.2164</td></tr><tr><td>SSIM</td><td>1</td><td>0.8575</td><td>0.8812</td><td>0.8910</td><td>0.9035</td><td>0.9257</td></tr><tr><td rowspan="2">Canon</td><td>Entropy</td><td>6.1750</td><td>6.2174</td><td>6.3614</td><td>6.6514</td><td>6.8493</td><td>6.9803</td></tr><tr><td>Contrast</td><td>27.5831</td><td>54.8575</td><td>70.3792</td><td>86.2641</td><td>95.8527</td><td>102.3019</td></tr></table></body></html>

<html><body><table><tr><td></td><td>SSIM</td><td>1</td><td>0.8341</td><td>0.8713</td><td>0.8731</td><td>0.8879</td><td>0.9247</td></tr><tr><td rowspan="4">Brand</td><td>Entropy</td><td>5.7754</td><td>6.4127</td><td>7.0235</td><td>7.4831</td><td>7.6719</td><td>7.7925</td></tr><tr><td>Contrast</td><td>5.6976</td><td>8.0201</td><td>10.4229</td><td>12.7995</td><td>13.8184</td><td>16.3174</td></tr><tr><td>SSIM</td><td>1</td><td>0.9325</td><td>0.9573</td><td>0.9605</td><td>0.9657</td><td>0.9791</td></tr><tr><td>Entropy</td><td>7.1457</td><td>7.1692</td><td>7.1920</td><td>7.2063</td><td>7.2450</td><td>7.3160</td></tr><tr><td>City_1</td><td>Contrast</td><td>143.4234</td><td>152.1598</td><td>159.7825</td><td>163.3839</td><td>171.9515</td><td>182.8193</td></tr><tr><td rowspan="4">City_2</td><td>SSIM</td><td>1</td><td>0.8094</td><td>0.8290</td><td>0.8317</td><td>0.8540</td><td>0.9026</td></tr><tr><td>Entropy</td><td>7.1367</td><td>7.1524</td><td>7.1738</td><td>7.1864</td><td>7.2028</td><td>7.2297</td></tr><tr><td>Contrast</td><td>153.2828</td><td>160.2581</td><td>168.1594</td><td>170.2447</td><td>172.1594</td><td>185.2549</td></tr><tr><td>SSIM</td><td>1</td><td>0.8295</td><td>0.8461</td><td>0.8582</td><td>0.8917</td><td>0.9051</td></tr><tr><td rowspan="4">City_3</td><td></td><td>6.7442</td><td>6.9816</td><td>7.1486</td><td></td><td></td><td></td></tr><tr><td>Entropy Contrast</td><td>146.8199</td><td>248.2651</td><td>297.4632</td><td>7.2592</td><td>7.3118 338.0931</td><td>7.3409</td></tr><tr><td>SSIM</td><td>1</td><td>0.8851</td><td>0.9075</td><td>328.1986 0.9105</td><td></td><td>351.0794</td></tr><tr><td>Entropy</td><td>6.9026</td><td>6.9815</td><td>7.1468</td><td>7.1980</td><td>0.9210 7.2672</td><td>0.9376 7.3062</td></tr><tr><td rowspan="4">City_4</td><td></td><td>165.6592</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Contrast SSIM</td><td>1</td><td>224.3678</td><td>285.1667 0.9314</td><td>298.3113</td><td>304.7364</td><td>312.0753</td></tr><tr><td>Entropy</td><td>6.8845</td><td>0.9267 6.9723</td><td>7.0919</td><td>0.9357</td><td>0.9414</td><td>0.9647</td></tr><tr><td>Contrast</td><td>138.6504</td><td></td><td>200.1937</td><td>7.0985</td><td>7.1057</td><td>7.1542</td></tr><tr><td rowspan="4">Cones</td><td></td><td></td><td>165.1846</td><td></td><td>210.4247</td><td>215.0972</td><td>226.2847</td></tr><tr><td>SSIM</td><td>1</td><td>0.8613</td><td>0.8753</td><td>0.8839</td><td>0.8916</td><td>0.9216</td></tr><tr><td>Entropy Contrast</td><td>7.2516 35.5232</td><td>7.3971</td><td>7.4375</td><td>7.4663</td><td>7.5178</td><td>7.6128</td></tr><tr><td></td><td>1</td><td>38.1637</td><td>40.7557</td><td>41.4446</td><td>45.1697</td><td>46.8239</td></tr><tr><td rowspan="4">Ny_1</td><td>SSIM</td><td></td><td>0.9215</td><td>0.9308</td><td>0.9392</td><td>0.9427</td><td>0.9685</td></tr><tr><td>Entropy</td><td>6.4591</td><td>6.6819</td><td>6.7371</td><td>6.8118</td><td>7.0194</td><td>7.2146</td></tr><tr><td>Contrast</td><td>34.0703</td><td>46.1659</td><td>50.2359</td><td>55.2611</td><td>57.6834</td><td>67.3905</td></tr><tr><td>SSIM</td><td>1</td><td>0.8735</td><td>0.8992</td><td>0.9069</td><td>0.9260</td><td>0.9641</td></tr><tr><td rowspan="4">Ny_2</td><td>Entropy</td><td>6.8101</td><td>7.4415</td><td>7.6356</td><td>7.7032</td><td>7.7951</td><td>7.8613</td></tr><tr><td>Contrast</td><td>53.9254</td><td>68.0593</td><td>75.5398</td><td>82.7387</td><td>90.2649</td><td>101.5206</td></tr><tr><td>SSIM</td><td>1</td><td>0.8945</td><td>0.9036</td><td>0.9106</td><td>0.9376</td><td>0.9579</td></tr><tr><td>Entropy</td><td>7.3855</td><td>7.4461</td><td>7.5094</td><td>7.5224</td><td>7.5417</td><td>7.6042</td></tr><tr><td rowspan="3">Pumpkins</td><td>Contrast</td><td>193.4393</td><td>235.7913</td><td>280.1946</td><td>309.5983</td><td>319.4592</td><td>330.7218</td></tr><tr><td>SSIM</td><td>1</td><td>0.8691</td><td>0.8852</td><td>0.8921</td><td>0.9046</td><td>0.9405</td></tr><tr><td>Entropy</td><td>6.5250</td><td>6.6408</td><td>6.7864</td><td>6.9205</td><td>7.0866</td><td>7.2830</td></tr><tr><td rowspan="4"> Stadium</td><td>Contrast</td><td>32.2878</td><td>55.3728</td><td>63.8226</td><td>72.5800</td><td>78.0361</td><td>85.1975</td></tr><tr><td>SSIM</td><td>1</td><td>0.8917</td><td>0.8981</td><td>0.9091</td><td>0.9150</td><td>0.9397</td></tr><tr><td>Entropy</td><td>7.0427</td><td>7.3874</td><td>7.4018</td><td>7.4518</td><td>7.5419</td><td>7.5610</td></tr><tr><td>Contrast</td><td>43.0934</td><td>85.9620</td><td>113.4143</td><td>132.8781</td><td>140.9137</td><td>156.0826</td></tr><tr><td rowspan="4"></td><td>SSIM</td><td>1</td><td>0.7316</td><td>0.7485</td><td>0.7577</td><td>0.7610</td><td>0.7805</td></tr><tr><td>Entropy</td><td>6.3837</td><td>6.5127</td><td>6.7810</td><td>6.9502</td><td>6.9784</td><td>7.0736</td></tr><tr><td>Contrast</td><td>160.1864</td><td>183.9524</td><td>198.3647</td><td>210.9557</td><td>214.3291</td><td>221.9271</td></tr><tr><td>SSIM</td><td>1</td><td>0.9258</td><td>0.9391</td><td>0.9401</td><td>0.9559</td><td>0.9740</td></tr></table></body></html>

没有发生太大的失真。综上所述，本文算法对大部分的图像都能达到一个很好的保持细节的去雾效果。

从表1中可以看出，对于测试的图像来说，本文算法上都是处于一个比较高的状态。本文方法的图像对比度都高于其他算法，说明本文方法能更好地将有雾和无雾区域检测出来；信息熵也基本高于其他方法，说明本文方法能保留下来的图像信息更多更全面，细节能更好地描述；结构相似度也是基本保持最高水平，说明本文方法能更多地保持住原图像的图像结构，

表2主要算法的时间复杂度比较  

<html><body><table><tr><td>Image</td><td>He's</td><td>Shen's</td><td>Ours</td></tr><tr><td>Fig.5</td><td>1.5624</td><td>1.2170</td><td>0.9815</td></tr><tr><td>Fig.6</td><td>4.9980</td><td>4.0316</td><td>2.8651</td></tr></table></body></html>

<html><body><table><tr><td>Fig.7</td><td>7.9291</td><td>7.2504</td><td>5.3028</td></tr><tr><td>Fig.8</td><td>2.9073</td><td>2.0791</td><td>1.6174</td></tr><tr><td>Fig.9</td><td>10.2274</td><td>6.1698</td><td>5.2536</td></tr><tr><td>Fig.10</td><td>4.5457</td><td>3.5208</td><td>2.3097</td></tr><tr><td>Fig.11</td><td>4.7113</td><td>3.2948</td><td>2.8143</td></tr></table></body></html>

除了上述三个方法的客观比较之外，本文对三种主要的算法增加了时间复杂度的比较（表2)。实验结果表明，本文方法在实验中消耗的时间最少、运行速度最快。同样的测试图像，相比于Shen的时间复杂度，本文的时间复杂度降低了 $2 5 \%$ 左右。

# 4 结束语

本文提出一种基于改进透射率和半逆法估计大气光值的算法对图像进行处理，不仅保留了暗通道先验简单有效的优势，而且还针对处理过程中的光带效应和去雾之后图像颜色暗淡、对比度不高等问题进行了提升。实验结果显示，本文算法对于没有阳光直接照射的地方处理效果比较好，去雾效果相比于之前的算法也好很多，但是对天空区域比较亮就没有想象中的那么好，日后还有待改进。

# 参考文献：

[1]Chen S D,Ramli A.Preserving brightness in histogram equalization based contrast enhancement techniques [J].Digital Signal Process,2OO4,14 (5): 413-428.   
[2]Rahman Z, Jobson D J,Woodell G A.Multi-scale retinex for color image enhancement [C// Proc of International Conference on Image Processings. Lausanne,Switzerland:[s.n.],1996:1003-1006.   
[3]杨燕，陈高科．基于光补偿和逐像素透射率的图像复原算法[J].通信 学报,2017,38 (5):48-56.(YangyanChenggaoke. Single image visibility restoration using optical compensation and pixel-by-pixel transmission estimation [J]. Journal on Communications.2017,38 (5): 48-56.)   
[4] McCartney E J.Optics of atmosphere:scattering by molecules and particles [M]. New York: John Wiley and Sons,1976.   
[5]Schechner YY,Narasimhan S G, Nayar S K. Instant dehazing of images using polarization [C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition.2001: 325-332.   
[6]Shwartz S,Namer E,Schechner Y Y.Blind haze separation.[C]//Proc of IEEE Conference on Computer Vision and Pattern Recognition. 2006: 1984-1991.   
[7]Narasimhan S G, Nayar S K.Contrast restoration of weather degraded images [J]. IEEE Trans.on Pattern Analysis and Machine Intelligence, 2003,25 (6): 713-724.   
[8]Nayar S K,Narasimhan S G. Vision in bad weather [C]// Proc of the 7th IEEE International Conference on Computer Vision.1999: 820-827.   
[9]Tan R.Visibility in bad weather from a single image [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition.2Oo8:1-8.

[10]Fattal R.Single image dehazing [C]// Proc of ACM SIGGRAPH.2008: 1-9.

[11] He Kaiming,Sun Jian,Tang Xiaoou. Single image haze removal using dark channel prior [C]// Proc IEEE Conference Computer Vision and PatternRecognition.2009.

[12] He Kaiming, Sun Jian,Tang Xiaoou. Guided image filtering [C]// Proc of European Conference on Computer Vision. 2010: 1-14.   
[13]赵锦威，沈逸云，刘春晓，等．暗通道先验图像去雾的大气光效验和光 晕消除[J].中国图象图形学报，2016,21(9):1221-1228.(Zhao Jinwei, Shen Yiyun,Liu Chunxiao,et al. Dark channel prior-based image dehazing with atmospheric light validation and halo elimination [J].Journal of Image and Graphics,2016,21(9):1221-1228.)   
[14]肖进胜，高威，邹白昱，等．基于天空约束暗通道先验的图像去雾[J]. 电子学报.2017,45 (2):346-352.(Xiao Jinsheng,Gao Wei,Zou Baiyu,et al. Image dehazing based on sky-constrained dark channel prior[J].Acta Electronica Sinica,2017,45 (2): 346-352. )   
[15]刘兴云，戴声奎．消除 halo 效应和色彩失真的去雾算法[J]．中国图象 图形学报，2015，20 (11):1453-1461.(Liu Xingyun，Dai Shengkui. Halo-freeand color-distortion-free algorithm for image dehazing [J]. Journal of Image and Graphics,2015,20 (11): 1453-1461. )   
[16]李加元，胡庆武，艾明耀，等．结合天空识别和暗通道原理的图像去雾 [J].2015,20(4):514-519.(Li Jiayuan,HuQingwu,AiMingyao,et al. Image haze removal based on sky region detection and dark channel prior [J]. Journal of Image and Graphics,2015,20(4): 514-519.)   
[17]Liu Chunxiao,Zhao Jinwei,Shen Yiyun，etal.Texture filter based physically plausible image dehazing [J]. The Visual Computer,2016,32 (6): 911-920.   
[18]邱东芳，黄光辉，刘星，等．透射率和大气光自适应估计的暗通道去雾 [J].计算机应用，2017,37(S1):176-179，186.(Qiu Dongfang，Huang Guanghui,Liu Xing,et al. Dark channel haze removal based on adaptive transmission and airlight estimation [J]. Journal of Computer Application. 2017,37 (S1): 176-179,186. )   
[19]沈逸云，刘春晓，张金栋，等．鲁棒图像去雾的大气光校正与透射率优 化算法[J].计算机辅助设计与图形学学报，2017,9(29):1604-1612. (Shen Yiyun,Liu Chunxiao,Zhang Jindong，et al.Atmospheric light correction and transmission optimization based robust image dehazing [J]. Journal of Computer-Aided Design & Computer Graphics,2017,9 (29): 1604-1612. )   
[20] Narasimhan SG,Nayar S K.Chromatic framework for vision in bad weather [C]// Proc of CVPR.200O: 598-605.   
[21] Narasimhan S G, Nayar S K. Vision and the atmosphere [C]// Proc of IJCV. 2002: 233-254.   
[22] Ancuti C O, Ancuti C,Hermans C,et al. A fast semi-inverse approach to detect and remove the haze froma single image [Cl// Proc of the 10th Asian Conference on ComputerVision.New Zealand:[s.n.]，2010: 510-514.   
[23]WangKe,Enrique D,Joseph T,et al.Combining semantic scene priors and haze removal for single image depth estimation [C]//Proc of IEEE Winter Conference on Applications of Computer Vision.2O14: 800-807.   
[24] Levin A,Lischinski D,Weiss Y.A closed form solution to natural image matting [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. 2006.

[25]张志禹，李向月，李向阳．同步挤压小波变换对随机噪声抑制的研究 [J].计算机工程与应用,2018,54(5):57-60.(Zhang Zhiyu,LiXiangyue, Li Xiangyang. Research on random noise suppression by synchrosqueezing wavelet transform [J].Computer Engineering and Applications,2O18,54 (5): 57-60.)