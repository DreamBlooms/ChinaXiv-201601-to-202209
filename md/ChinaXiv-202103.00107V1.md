# 基于盲退卷积的AIA图像增强方法

沐芳’，黄欢’，尚振宏1,3\*，强振平²(1.昆明理工大学信息工程与自动化学院，云南 昆明 650500;2.西南林业大学大数据与智能工程学院，云南 昆明 650224;3.昆明理工大学云南省人工智能重点实验室，云南 昆明 650500)

摘 要：太阳图像中存在着各种尺度，亮度，结构不同的物理活动现象，由于太阳日冕高动态的活动和传感器设备等因素，造成太阳图像成像质量不佳。根据太阳动力学天文台（SolarDynamicObservatory,SDO）的大气成像仪（Atmospheric Imaging Assenbly,AIA）拍摄不同波段数据结构的动态范围大、噪声大、结构相对模糊等特点，本文提出一种有效基于盲退卷积的 SDO/AIA图像增强方法。首先对SDO/AIA图像进行去噪和降低动态范围的处理，基于图像功率谱的分布假设，从原图中估计出点扩散函数(point spread function，PSF)的功率谱，然后使用相位提取算法恢复出 PSF的相位，再退卷积出较高质量的目标图像；最后通过轮廓切片分析、功率谱分析以及PSF分析对增强结果进行定量和定性分析。实验结果表明，相比现有图像增强方法，该方法在有效增强太阳日冕图像细节结构的同时，复原出原图因模糊无法辨识的结构。

关键词：太阳图像；SDO/AIA;功率谱；盲退卷积；相位提取中图分类号： $\mathrm { P l } 8 2 . 6 \substack { + 2 }$ 文献标识码：A

# 0引言

为了研究高度动态的太阳日冕结构，人们一直在提高时间、空间分辨率上，不断探索。由于太阳日冕结构的密度、位置和形状短至几秒钟就会发生变化，较大的动态范围，造成望远镜拍摄的日冕结构边缘模糊且噪声较大，使得可视化困难。目前已经研究出几种较为有效的增强图像算法用于太阳日冕图像增强。基于直方图均衡的方法，可以利用不同分布直方图对不同图像规定化处理[1，也可以高斯滤波后，再独立均衡各个分区，如保持亮度的动态直方图均衡化[2]（Brightness Preserving DynamicHistogram Equalization，BPDHE）这些方法能够有效提高图像整体对比度。但由于直方图的邻域形状通常是正方形，会导致严重的伪影，从而影响日冕环状结构；其次会放大图像中低对比度噪声，进一步模糊图像细节；亮度不同的区域之间也会失去有效结构。基于曝光融合框架的对比度增强算法[3]（ExposureFusionFramework，EFF）可以解决直方图均衡出现的对比度过高或者过低的问题。基于多种经典图像增强算法融合的方法[4]（Multi-deviation Fusion method，MF）融合多种经典图像增强算法进行取长补短，使图像增强时能够同时兼顾细节增强、对比度提升和主观感知效果等方面。这些方法大部分预处理都采用对数变换，能够使得计算复杂度降低。但由于对数变换抑制了亮区梯度幅度的变化，这可能会导致某些区域的精细结构细节丢失。为解决这个问题，基于Retinex的方法，可以压缩动态范围压缩的同时，兼顾边缘增强和保持颜色稳定，其中（Robust Retinex Model，rR）算法[5]可提高对噪声的鲁棒性，使用一种基于拉格朗日乘子的交替方向最小化算法代替对数变换，有效解决模型优化过程问题，能有效保持细节结构和边缘稳定。上述方法都仅为太阳日冕图像提供了一种可视化方法，对于其中因为日冕动态变化、望远镜抖动、CCD欠采样以及杂散光等因素造成精确结构的模糊问题，无法有效增强。随着数字图像处理技术的发展，盲退卷积算法对于要求恢复结构准确性和真实性方面提供了科学的理论依据。PaoloG等人[根据望远镜设计理论估计出理论上满足 SDO/AIA不同波段的PSF 用于退卷积，但造成图像模糊的原因除传感器设备外，还有太阳活动位移、形状变化等造成的模糊。所以理论估计的 PSF 并不能很好的退卷积出清晰图像。在使用空间望远镜 SDO/AIA 观测太阳日冕结构时，对由于日冕位移、形状改变、CCD欠采样以及杂散光等因素造成成像模糊过程，可建模为：

$$
B { \big ( } \mathbf { x } { \big ) } = I { \big ( } \mathbf { x } { \big ) } * k { \big ( } \mathbf { x } { \big ) } + n { \big ( } \mathbf { x } { \big ) }
$$

其中，\*表示卷积运算， $B$ 表示获得的模糊图像，即 SDO/AIA 图像， $I$ 表示潜在的清晰图像， $k$ 表示未知的 PSF， $n \big ( \mathbf { x } \big )$ 表示在每个像素 $\scriptstyle \mathbf { X } = \left( x , y \right)$ 处相同且独立分布的噪声项。

根据求解方法的不同，盲退卷积算法大致可分为两类：一类是通过引入额外约束条件同时对目标图像和PSF估计进行交替迭代，并基于最大后验概率估计（maximuma posterior,MAP）完成盲退卷积的算法；另一类是先估计模糊核，再退卷积得到清晰图像。第一类方法对噪声有一定的抑制效果，但涉及目标图像和PSF估计的多次迭代计算，使得估计过程非常耗时，且严重依赖于清晰图像和 PSF的先验特性。对于 SDO/AIA 图像而言，很难获得清晰图像的统计先验信息。第二类方法以基于显著性边缘[和基于功率谱的方法[8-9为主，基于边缘的方法是从原图显著边缘估计模糊核，这一方法很大程度上取决于边缘选择，更适用于运动模糊估计。SDO/AIA 图像结构模糊，无法较好的选择边缘。而基于功率谱的方法直接从输入图像功率谱中恢复出PSF的功率谱，再使用相位检索算法求解 PSF的相位。

因此，本文研究了一种利用模糊图像功率谱估计PSF的单帧图像盲退卷积算法用于太阳 SDO/AIA图像增强。首先对数据预处理(包括去噪和灰度值变换处理)，从AIA中估计出PSF的功率谱；再用相位检索算法恢复出PSF，为了使该相位检索算法对噪声更鲁棒，额外引入了权重参数 $\alpha$ ，限制使用PSF功率谱对PSF相位估计的硬性约束。并对该算法随机初始化求解多次，避免陷入局部极小值。计算 PSF所有可能解之间的 $\mathbf { L } _ { 2 }$ 范数距离，通过多次随机初始化计算PSF，如果可能解之间的 $\mathbf { L } _ { 2 }$ 距离越小，可以认为是最接近真解的 PSF，最后利用该 PSF 于式(1)退卷积出目标图像。为进一步减少噪声影响，将待增强图像分隔为四幅相邻局部子图，并按上述方法估计每幅子图的PSF，对四个PSF进行归一化和求取均值得到恢复整幅图像的PSF。实验分析使用轮廓切片曲线、功率谱分析以及PSF分析以及和其他较为先进的的增强算法结果对比分析，对重建出的目标图像细节结构进行客观分析，将高分辨率日冕成像仪(The High-Resolution Coronal Imager，Hi-C)图像功率谱假设模型验证和精细结构增强效果对比。结果显示本文方法对于 SDO/AIA193A、211A、171A 波段结构的增强和复原有较好的效果，且对噪声鲁棒。此外，由于该方法不涉及目标像的反复重建，在图像恢复速度上也有一定优势。

# 1 SDO/AIA数据

SDO/AIA[1主要目标是了解太阳能量存储与释放机制，确定太阳如何以及为何发生变化。通过研究太阳周围等离子体的相互作用，以增强我们对太阳如何影响地球大气和社会生产的理解。SDO/AIA由四个望远镜组成，可同时提供十个波段的全日面像，包括7个极紫外波段(94A、131A、171A、193 A、211 A、304A、 $3 3 5 \mathrm { ~ \AA ~ }$ 和2个紫外波段(1600A、1700A)和1个可见光波段 $( 4 5 0 0 \mathrm { \AA } )$ 。观测范围包括太阳过渡区和日冕上最高可达 $0 . 5 R _ { \odot }$ 的日冕，其空间分辨率为1.5-arcsec，时间分辨率为12s，视场达到了$4 1 \times 4 1$ arcmin，于2010年2月11日启动。

高分辨率日冕成像仪（Hi-C）[1-12提供了日冕更精细结构视角，获得高空间分辨率（ ${ \approx } 0 . 3 ~ \sim 0 . 4$ arcsec)，高时间分辨率（ ${ \approx } 5 \mathrm { s }$ ）的太阳活动区域结构图像，是目前为止可获得的最高分辨率太阳日冕图像。使许多人了解到一些小尺度日冕特征和发生在过渡区的活动现象，以及它们之间可能存在的相互关联也得到进一步验证。

如表1数据对比可知，Hi-C虽然拥有更高的时空分辨率，但其视场小、拍摄时长较短，无法稳定长期的对日冕进行观测，相较而言，SDO/AIA 能够提供大视场、长期全日面观测图像，然而其图像质量低于Hi-C，因此对SDO/AIA图像增强处理显得尤为重要。

表1.SDO/AIA与Hi-C数据特点对比表Table1.Comparisonof SDO/AIAandHi-C data characteristics  

<html><body><table><tr><td rowspan="2">Data</td><td colspan="7">Data Properties</td></tr><tr><td>Data Acquisition Time</td><td>Field of view (arcmin)</td><td>Image Size (pixel)</td><td>Spatial Resolution (arcsec)</td><td>Tempotal Resolution (s)</td><td>Channel (A)</td></tr><tr><td>SDO/AIA</td><td>2010.02.11-now</td><td>41×41</td><td>4096x4096</td><td>1.5</td><td>12</td><td>94、131、171、193、211、 304、335、1600、1700、4500</td></tr><tr><td>Hi-C</td><td>2012.07.11 18:52:10-18:57:49</td><td>6.66x7.03</td><td>≤3880×4096</td><td>0.3~0.4</td><td>~5</td><td>193</td></tr></table></body></html>

本工作采用 SDO/AIA数据是可以观察到热耀斑等离子体和日冕的 2012年7月11日18:53:32 时刻193A波段局部像，和观测活动区日冕的2014年2月2日23:40:11的211A波段局部像，这两组数据由同一望远镜拍摄。此外，实验中还包括不同望远镜拍摄的观测宁静区日冕的 2014 年10月4日10:13:11的171A波段局部像。其中193A波段实验中，也采用了活动区域11520的 2012年7月11日18:53:27时刻Hi-C图像作为清晰图像功率谱假设验证和实验对比，除此之外，实验对比图还包括文献[3]估计的PSF退卷积图。数据预处理包括：根据 SDO/AIA的数据的高动态特点，对图像对数变换，这一步能够有效降低图像的动态范围，然后使用中值滤波对图像去噪处理，该算法在去除部分噪声的同时不会平滑过渡，能有效保持图像结构。

# 2盲退卷积算法理论

本文方法分为三部分：自然图像功率谱假设模型，Hi-C 功率谱分析和AIA 图像 PSF求解。

# 3.1自然图像功率谱假设模型

Amit8等人研究表明，清晰图像的功率谱(或自相关)是各向同性的，模糊过程中图像的中、高频分量降低，对模糊图像不同方向使用微分滤波后再计算自相关，当模糊方向与微分方向一致时，损失最大，能够认为此时能量绝对值之和最小的方向为模糊方向。根据以上结论，我们对清晰图像和模糊图像分别进行不同角度 $\left( { \bf { \theta } } ; 1 ^ { \circ } \right) \big [ \mathrm { { 1 8 0 } } ^ { \circ }$ ）的傅里叶中心投影变换，得到不同投影角度对应的一维切片后，再对这些切片一维微分滤波，最后计算其自相关即可得到：

$$
\Big ( \mathfrak { R } _ { \mathrm { d } * \mathrm { P } _ { \mathfrak { h } } \big ( I \big ) } \Big ) \big ( \mathrm { x } \big ) \approx c _ { \mathfrak { h } } \big [ \delta \big ( \mathrm { x } \big )
$$

$$
\Big ( \mathfrak { R } _ { \mathrm { d } \ast \mathrm { P } _ { \mathfrak { \theta } } \left( B \right) } \Big ) \big ( \mathrm { x } \big ) \approx c _ { \mathfrak { \theta } } \big [ \mathfrak { R } _ { \mathtt { P } _ { \mathfrak { \theta } } \left( k \right) } \big ( \mathrm { x } \big )
$$

其中，d为一维微分滤波器， $c _ { \mathfrak { g } }$ 表示一个随着角度变化的乘性因子， $\Re$ 表示对图像自相关计算，P表示投影算子，δ表示冲激函数，即：

$$
\delta = { \left\{ \begin{array} { l l } { 1 } & { \left( x , y \right) = \left( 0 , 0 \right) { \Big ] } } \\ { 0 } & { \quad o t h e r w i s e { \Big ] } } \end{array} \right. }
$$

# $3 . 2 \mathrm { H i - C }$ 功率谱分析

如图1所示，对 Hi-C 图的功率谱特性进行分析。将图 Hi-C(a)的一个局部子图的 $\mathfrak { R } _ { \mathrm { d } * \mathrm { P } _ { \theta } ( \mathrm { I } ) }$ 绘制如图(b)，图(b)将 $4 5 ^ { \circ } , 9 0 ^ { \circ } , 1 3 5 ^ { \circ } , 1 8 0 ^ { \circ }$ 方向功率谱截面绘制如图(c)，将图(c)中四条曲线对应数值相除得到结果图(d)。通过观察图(c)，清晰图像(a)经过(2)式计算得到功率谱并不是一个精确的δ函数，(d)图可以看出不同角度的功率谱相除得到不同常数， $c _ { \mathfrak { g } }$ 随着投影角度的变化而变化，即太阳清晰图像Hi-C功率谱随着θ不同有不同乘性因子的变化量。进而证明(2)(3)式用于AIA 图像PSF估计是可靠的。图中多个尖峰是除数存在0值造成的。

为了不增加图像的总能量，滤波器d均值为0，在进行 $\mathtt { d } * \mathrm { P } _ { \mathfrak { p } } \left( B \right)$ 计算时，会导致 $\mathrm { P } _ { \theta } \left( B \right)$ 的均值缺失(为0)，但图像本身功率谱并非为0，所以在计算过程中，引入参数 $m _ { \theta }$ 来代替0值。即 $\mathfrak { R } _ { \mathrm { P } _ { \mathrm { \theta } } ( k ) } \left( \mathrm { x } \right)$ 的均值使用 ${ m _ { \mathrm { \theta } } } / { c _ { \mathrm { \theta } } }$ 代替。令 $f _ { \mathfrak { g } } \left( \mathbf { x } \right) = \mathfrak { R } _ { \mathrm { d } * \mathrm { P } _ { \mathfrak { g } } \left( B \right) } \left( \mathbf { x } \right)$ ，由(3)式可以得到：

$$
\mathfrak { R } _ { \mathrm { p } _ { \mathfrak { g } } ( k ) } \left( \mathbf { x } \right) = \big ( f _ { \mathfrak { g } } \left( \mathbf { x } \right) + m _ { \mathfrak { g } } \big ) \big / c _ { \mathfrak { g } }
$$

![](images/a01cef5b0d45dbeb83af1112b477801a3e137dd91c7c0868fb115439e278704c.jpg)  
图1.Hi-C功率谱模型说明 Figure 1.Explanation of Hi-C power spectrum model

# 3.3 PSF估计

(4)式是一个欠定方程，为了成功恢复 $\mathfrak { R } _ { \mathrm { P } _ { \mathfrak { g } } ( k ) } \left( \mathrm { x } \right)$ ，需要引入额外约束条件估计出 $c _ { \mathfrak { \mathfrak { \theta } } }$ 和 $m _ { \theta }$ 。 3.3.1估计 $c _ { \mathfrak { \mathfrak { \mathrm { \theta } } } }$

采用关于PSF的三个假设[I3对式(4)进行等价计算：

1．相机曝光，光子在传感器上累积图像，由于光子能量非负，故PSF 是非负的，即 $k \geq 0$ ，所以关于 $k$ 的投影 ${ \bf P } _ { \boldsymbol \theta } \left( k \right)$ 和自相关 $\mathfrak { R } _ { \mathrm { p } _ { \theta } ( k ) }$ 都是非负的，根据(4)式能够得到 $f _ { \theta } \left( \mathbf { x } \right) + m _ { \theta } \geq 0$ 。

2．相机曝光时移动有限，故模糊过程有限， $k$ 支持域紧凑，所以对于每个角度的投影的自相关 $\mathfrak { R } _ { \mathrm { p } _ { \theta } ( k ) }$ 来说，都存在一个 $s _ { \theta }$ 使得 $\mathfrak { R } _ { _ { \mathrm { P } _ { \mathrm { \Phi } } \mathrm { \Phi } } \mathrm { \left( \mathrm { \mathbf { x } } \right) } } \left( \mathrm { \frac { \mathcal { I } _ { \mathrm { \Theta } } \left( \mathrm { \mathbf { x } } \right) + m _ { \mathrm { \theta } } } { c _ { \mathrm { \theta } } } \quad } \middle | \mathrm { \mathbf { x } } \right| < s _ { \mathrm { \theta } } \Bigg \downarrow$ ，故 $m _ { \theta }$ 满足 $m _ { \theta } = - f _ { \theta } \left( s _ { \theta } \right)$ 。

3．理论上，模糊并不会影响光子达到传感器的总量，所以可以认为 $\int k \big ( \mathbf { x } \big ) \mathrm { d } \mathbf { x } = 1$ ，也意味着$\int \mathfrak { R } _ { \mathrm { p } _ { \mathfrak { g } } ( k ) } \left( \mathbf { x } \right) \mathrm { d } \mathbf { x } = 1$ 。根据式(4)得到： $c _ { \theta } = \int \big ( f _ { \theta } \left( \mathbf { x } \right) + m _ { \theta } \big ) \mathrm { d } \mathbf { x }$ （即是对模糊核 $k$ 归一化)。综上，计算式(4)可以等价于下式的计算：

$$
\mathfrak { R } _ { \mathrm { p } _ { \mathfrak { \mathfrak { h } } } ( k ) } \left( \mathrm { x } \right) = \frac { f _ { \mathfrak { \mathfrak { h } } } \left( \mathrm { x } \right) - f _ { \mathfrak { \mathfrak { h } } } \left( \boldsymbol { s } _ { \mathfrak { \mathfrak { \mathfrak { h } } } } \right) } { \displaystyle \int \Bigl ( f _ { \mathfrak { \mathfrak { \theta } } } \left( \mathrm { x } \right) + m _ { \mathfrak { \mathfrak { \theta } } } \Bigr ) \mathrm { d } \mathrm { x } } = \frac { f _ { \mathfrak { \mathfrak { \theta } } } \left( \mathrm { x } \right) - f _ { \mathfrak { \mathfrak { \theta } } } \left( \boldsymbol { s } _ { \mathfrak { \mathfrak { \theta } } } \right) } { \displaystyle \int \Bigl ( f _ { \mathfrak { \theta } } \left( \mathrm { x } \right) - f _ { \mathfrak { \mathfrak { \theta } } } \left( \boldsymbol { s } _ { \mathfrak { \theta } } \right) \Bigr ) \mathrm { d } \mathrm { x } }
$$

3.3.2估计支持范围 $s _ { \theta }$

通过在 PSF 估计和 $s _ { \scriptscriptstyle \theta }$ 估计之间进行最大期望（Expectation-maximization EM）迭代，从而估计出 $s _ { \theta }$ 和 PSF。EM算法的每一次迭代都是对 PSF 的再一次修正，能够更准确估计 PSF，使其在盲复原工作中有效抑制振铃和伪影。

(1）首先初始化 $s _ { \theta } ^ { ( 0 ) } = \arg \operatorname* { m i n } _ { \mathbf { \lambda } } f _ { \theta } \left( \mathbf { \lambda x } \right)$ ，之后每次更新为 $s _ { \theta } ^ { ( i ) }$ ;  
(2）使用 $s _ { \theta } ^ { ( i ) }$ 估计出 $\mathfrak { R } _ { \mathrm { P } _ { \theta } ( k ) } ^ { ( i ) } \left( \mathrm { x } \right)$ ，再根据相位检索算法（算法2）迭代出当前满足最大期望值的 $\boldsymbol { k } ^ { ( i ) }$ ；  
(3）根据第(2)步的 $\boldsymbol { k } ^ { ( i ) }$ 更新出 $s _ { \boldsymbol { \Theta } } ^ { ( i + 1 ) }$ 用于第 $i { + } 1$ 次迭代；  
(4)(2)(3)两步反复迭代直到满足条件 $s _ { \theta } ^ { ( i + 1 ) } > 0 . 1 \mathrm { I m a x } \left( \mathfrak { R } _ { \mathrm { P } _ { \theta } ( k ) } \right)$ 时则停止迭代。

图2展示了支持域 $s _ { \theta }$ 迭代过程(a)和根据最终 $s _ { \scriptscriptstyle \theta }$ 迭代结果恢复的PSF一维自相关(b)。(a)中蓝色曲线表示初始化的 $s _ { \theta }$ ，根据EM迭代更新 $s _ { \theta }$ (红色曲线)，达到终止条件后 $s _ { \theta }$ (绿色曲线)的数值用于作为(b)图横轴的支持域数值。

![](images/6b24277ca4ec18f3c220d391de3201dadd702f3b69ce52033b43f57df9123343.jpg)  
图2. $s _ { \scriptscriptstyle { \Theta } }$ 迭代路径(a)和一维PSF功率谱(b)  
Figure 2. $s _ { \scriptscriptstyle \theta }$ Iterative path (a) and one dimensional PSF power spectrum (b)

算法1(求解 $k$ )的步骤可归纳为如下：

输入：模糊图像 $B$ ;  
输出： $k { = } \Big ( \sum _ { \mathfrak { r } = 1 } ^ { \mathrm { T } } k _ { \mathfrak { r } } \Big ) \Big / \mathrm { T }$ ；  
Step1. $f _ { \theta } \left( \mathbf { x } \right) = \Re _ { \mathrm { d } * \mathrm { P } _ { \theta } \left( B \right) }$ ；  
Step2.初始化 $s _ { \theta } ^ { ( 0 ) } = \arg \operatorname* { m i n } _ { \mathrm { ~ x ~ } } f _ { \theta } \left( \mathrm { ~ x \right) ~ }$ Step3.外循环开始，令次数 $\mathbf { t } = 1$ ：Step4.内循环开始：

Step4.1.使用给定的 $s _ { \scriptscriptstyle \theta }$ ，根据式(5)计算模糊核功率谱 $\left| k \right| ^ { 2 }$ （表示对信号做傅里叶变换)；

Step4.2.通过算法2计算出模糊核 $k _ { \mathrm { t } }$ ;

Step4.3.EM迭代更新 $s _ { \theta }$

Step5.当满足 $s _ { \mathrm { \theta } } \leq 0 . \ 1 \mathrm { I m a x } \big ( \mathfrak { R } _ { \mathrm { p } _ { \mathrm { \theta } } ( k ) } \big )$ 时内循环结束；

Step6. $\scriptstyle \mathrm { \mathtt { t } = T _ { \mathrm { o u t e r } } }$ （T 表示剪切图像张数）时外循环结束。

图3 是本文算法流程，首先对原图(a)去噪和对数变化得到(b)，计算(b)的一维自相关(c)，根据(c)迭代出支持域 $s _ { \mathfrak { d } } \left( \mathfrak { d } \right)$ ，最后使用该 $s _ { \theta }$ 校准PSF一维功率谱(e)，复原为二维功率谱(f)，相位提取算法计算出相位后恢复出 $\mathrm { P S F } ( \mathbf { g } )$ ，最后非盲退卷积得到目标图像(h)。

![](images/59ca73b8487e6bad9588b0699d579d350f574ee336ce508c03b06878508466c0.jpg)  
3.本文算法的执行过程:输入AIA 观测的局部太阳模糊图(a)；进行对数增强后的图(b)；一维自相关投影(c)； $s _ { \scriptscriptstyle \theta }$ 迭代路径(d)； $s _ { \scriptscriptstyle \theta }$ 优化后的一维自相关投影(e)；恢复后的二维模糊核功率谱(f)；相位恢复后的模糊核 $( \mathrm { g ) }$ ；本文算法增强后的太阳图(h)；  
Figure 3.The processofthealgorithmin this paper:input theAIAlocal image(a);the logarithmic enhancementimage(b); one-dimensional autocorrelation projection (c); $s _ { \scriptscriptstyle \theta }$ iterative path (d); $s _ { \scriptscriptstyle \theta }$ optimized one-dimensional autocorrelation projection (E); recovered two-dimensional PSF power spectrum (f); phase recovered PSF(g);the final enhanced image (h);

# 3.4PSF的相位恢复

求出 $\left| k \right| ^ { 2 }$ 之后，使用相位提取算法，通过添加约束条件求解模糊核 $k$ 的相位分量 $\boldsymbol { \Phi } \big ( \boldsymbol { \omega } \big )$ ，最终得到模糊核 $k$ 。相位提取算法是一种欠定算法，该算法的解存在平凡模糊的问题，通常会收敛到平凡解或局部极小值。典型的相位恢复方法以误差下降算法（Error-reduction，ER）为例，在迭代过程中降低误差，但其将不满足约束的信号设为0值的方式常常使得迭代停滞，后出现混合输入输出（Hybrid in-put-output，HIO）算法[14改进了此问题，对解设置了一个小扰动，可使得迭代的时候跳出停滞现象快速收敛。Luke[15]提出了一种叫做松弛平均交替反射（Relaxed Averaged Alternating Reflection，RAAR)的算法，该方法能够使得收敛更快更平稳，但该方法将输入的功率谱作为一种硬性约束，即需要恢复出的信号完全满足输入的功率谱，当输入信号含有噪声的时候，会使得收敛震荡，鲁棒性欠佳。SDO/AIA图像噪声复杂，并不能在数据预处理阶段完全消除，故本文算法放宽了模糊核功率谱的硬性约束要求（通过调整权重参数 $\alpha$ )，可提高算法对噪声的鲁棒性。初始阶段采用随机初始化相位分量，多次重复此随机过程，可以避免收敛到局部极小值。其次，还引入了HIO算法中对解的扰动方法（即算法2中$\beta$ 项)，可以使得解跳出停滞现象快速收敛。最后计算所有可能解的 $\mathbf { L } _ { 2 }$ 距离，求出最优解。

算法2(求解 $k _ { \mathrm { t } }$ )迭代包括以下步骤：输入： $\scriptstyle \rho ( \infty ) = \left| k { \bigl ( } \infty { \bigr ) } \right|$ ,PSF 尺寸s;输出： $k _ { \mathrm { t } }$ ;  
Stepl.外循环 $\mathfrak { n } = 1$

Stepl.1随机初始化相位 $\varphi \big ( \infty \big ) \big ( \big [ - \pi , \pi \big ]$ 之间)；

Stepl.2 计算G=F -l $\mathbf { G } = \mathrm { F } ^ { \mathrm { \Phi ^ { - 1 } } } \bigl ( \rho \mathbb { e } ^ { \mathrm { i } \varphi ( \omega ) } \bigr \ )$

Stepl.3内循环 $\mathrm { m } = 1$ ：

Step1.3.1施加傅里叶域约束(即是对幅值 $\rho$ 放宽至 $\alpha$ 倍）：

$$
\mathbf { G } _ { 2 } = \mathbf { F \Sigma } ^ { - 1 } ( \Big ( \mathbf { \alpha } \mathbf { \rho } + \big ( 1 - \alpha \big ) \Big | \mathbf { G } \Big | ) \mathbf { \rho } ^ { \mathrm { i } \mathrm { i } \mathrm { \top } \varphi \mathbf { G } } ) ;
$$

Step1.3.2施加空间域约束（即PSF非负性约束和支持域约束)：

$$
\mathbf { G } ( \mathbf { x } ) = \{ \begin{array} { l l } { \mathbf { \beta } \mathbf { G } ( \mathbf { x } ) + ( 1 - 2 \beta ) \mathbf { G } _ { 2 } ( \mathbf { x } ) } & { \mathbf { x } \in \Omega } \\ { \mathbf { G } _ { 2 } ( \mathbf { x } ) } & { \mathbf { x } \notin \Omega \} } \end{array} 
$$

其中， $\Omega = \left\{ \mathbf { x } : 2 \mathbf { g } _ { 2 } \left( \mathbf { x } \right) - \mathbf { g } \left( \mathbf { x } \right) < 0 \right\} \bigcup \left\{ \mathbf { x } : \mathbf { x } \notin \left[ 0 , \mathbf { s } \right] \times \left[ 0 , \mathbf { s } \right] \right\}$ ，为使 $\mathfrak { m }$ 次迭代中，信号能够平稳快速的收敛，将采用 HIO 算法中对 $\beta$ 的设置，即 $\scriptstyle \beta = \beta _ { 0 } + { \big ( } 1 - \beta _ { 0 } { \big ) } { \Big ( } 1 - \mathbf { e } ^ { ( - \mathrm { m } / 7 ) ^ { 3 } } { \Big ) }$ ，本实验中 $\beta _ { \mathrm { 0 } } { = } 0 . 7 5$ ，当出现 $\mathbf { x } \in \Omega$ （204号时，为G赋予一个较小的值 $\mathsf { B } \mathbf { G } \left( \mathbf { x } \right) + \left( 1 - 2 \mathsf { \beta } \right) \mathbf { G } _ { 2 } \left( \mathbf { x } \right)$ ，以便能够逃出迭代过程中的停滞现象;

Step1.4 $\scriptstyle \mathbf { m } = \mathbf { M } _ { \mathrm { o u t e r } }$ 时，内循环结束;

Step1.5复原 $k _ { \mathrm { n } } \left( \mathrm { x } \right) = \left\{ \begin{array} { l l } { \mathrm { G } _ { 2 } \left( \mathrm { x } \right) } & { \mathrm { x } \notin \Omega } \\ { 0 } & { \mathrm { x } \in \Omega } \end{array} \right\}$ ，其中 $\Omega = \left\{ \mathbf { x } : \mathbf { G } _ { 2 } \left( \mathbf { \Delta x } \right) < 0 \right\} \bigcup \left\{ \mathbf { \Delta x } : \mathbf { x } \notin \left[ \mathbf { \Delta } 0 , \right] \times \left[ \begin{array} { l } { 0 , \frac { 1 } { 2 } } \end{array} \right] \right\}$ Step2 $\scriptstyle \mathtt { n } = \mathrm { N } _ { \mathrm { o u t e r } }$ 时，外循环结束， $k _ { \mathrm { n } }$ 两两计算 $\mathbf { L } _ { 2 }$ 距离，得到最优解 $k _ { \mathrm { t } }$ ；

算法2包括两个循环结构，设置外循环为了避免解陷入局部极小值，当初始化值越接近真值，越容易收敛到全局最小值。多次相位随机初始化求解 $k \big ( \mathbf { x } \big )$ ，最终通过求不同解之间的范数距离，范数距离最小的解可认为是最优解 $k \big ( \mathbf { x } \big )$ ；设置内循环能够使得算法平稳快速的收敛，在迭代求解过程中交替引入频域约束（幅值约束）和空间域约束（PSF 的非负性约束和支持域约束)，当出现 $\mathbf { x } \in \Omega$ 时，将为G赋予一个较小的值 $\mathsf { \beta } \mathsf { G } \left( \mathrm { \boldsymbol { x } } \right) + \left( 1 - 2 \mathsf { \beta } \right) \mathsf { G } _ { 2 } \left( \mathrm { \boldsymbol { x } } \right)$ ，以便能够逃出迭代过程中的停滞现象。文献[15]指出通过逐步增大 $\beta$ 值能够引导解稳定收敛。故本文通过内循环将 $\beta$ 值设置为一个不断接近1的动态值。

如式 (1)所示，已知模糊核 $k$ 和模糊图像 $B$ ，求解目标清晰图像的方法叫做非盲退卷积算法。实验使用文献[16]中交替最小化的方法，即半二次分裂求解方法来求解目标图像 $I$ 0

# 3实验结果分析

为了评估该方法的有效性和准确性，本文实验中对 AIA193A，AIA211A，AIA171A三个波段不同区域进行增强，图中AIA图像均通过对数显示。图4中三个波段在增强后，细节结构更锐，尤其冕环之间的相对模糊结构也在增强后较好的分离开来，边界也更为清晰。如第三列本文算法估计出的 PSF尺寸大小可知，193和 211波段PSF较171波段更大，这说明前两个波段图像模糊程度更大，由于193波段和211波段图像主要是拍摄太阳活动区得到的，活动区更大的动态范围和冕环相对望远镜的运动造成模糊程度更高。在第四列功率谱图中，三个波段图像增强后的功率谱曲线相对AIA图像曲线在中频处都有一定程度的提高。中频的提高在增强图像中表现为已有结构边界更锐，以及由于模糊没观察到细节结构也恢复出来。

![](images/ceb2b65acd26cc6b402f0f5147cb24e6129fda5935c3b9ccc4144abcab2fa6f1.jpg)

![](images/48d64d7089141865d89141155f85dd877ea02bdd4a054bc7cb38b4682668f8b8.jpg)  
Figure4.EnhancementimagesofAIAindifferentbands

为了更好的对比细节结构的增强情况，我们在图5中引入了结构的轮廓切片图，文献[6]根据 AIA望远镜的理论估计出不同波段PSF 用于增强 AIA 图像，太阳一个波段的所有图像均使用同一个 PSF退卷积得到，这是不准确的，图像模糊原因也只考虑了望远镜设备的因素。所以恢复结果不佳（如图5 第二列)，图5中，我们对不同波段不同的区域分别增强，并将本文估计的PSF与文献[6」PSF 作对比。如 193波段的两张局部图，本文估计的PSF尺寸相当，但形状不同，对于结构A和结构B，冕环被较好的分离开来，如轮廓切片图所示。同样，在211波段和171波段增强图中，C、D、E结构的模糊方向与PSF形状一致，不同的区域，太阳的活动不一致，冕环位置和形状的变化，相互干扰是不可控的。这也是必须分区域单独估计PSF退卷积图像的原因。

![](images/a9a61f0757b6a6a06f8bba9a3ae59d0b4b04035f908da132fe71784774903127.jpg)  
图4.AIA不同波段增强图

![](images/9078a94213c934bb7b48c3959663a224558052b9a17445c275bb054684dd70c2.jpg)  
Figure 5.Detail enhancement images of different bands and regions

如图6所示，通过引入更高分辨率的Hi-C 图像进行细节结构对比，评估本文增强方法的准确性。为了便于与Hi-C 图对比，图(a)(b)经过放大和对数处理，观察三者的能量图可知，AIA 图像细节区域颜色相近，模糊明显，几乎看不到细节结构，增强后的图像与 Hi-C 相近。通过三者的功率谱图(d)可以看出，AIA几乎没有高频细节，中频部分也很弱。经过本文方法增强后的图像，中高频都有一定的提高，略弱于Hi-C图像，说明恢复细节结构的数量是少于Hi-C 图像的，中频处有一点略高于Hi-C 图像，在细节图(e)中可观察到，本文方法不仅能较好的分离冕环的相对模糊结构，且对于已存在的冕环，能更好的保持边缘。细节结构边缘较Hi-C锐，所以中频曲线略高于Hi-C。图中的A、B、C结构都是由于模糊无法分辨的结构，增强后，与Hi-C对比可知，结构保持稳定，且恢复情况较为准确。如对应的轮廓切片图(f)A 结构所示，AIA中表现为一个冕环的结构，成功的分离为两条冕环，与Hi-C保持一致。

![](images/3b8ad9f9e55daeffc0f4b8685f3dcb4f6f4ae745ce8277d1dcf2fb0e43840970.jpg)  
图5.不同波段不同区域细节增强图  
(e)Detail map

![](images/5e4daacbc6fc3e249f143f4a5f5a74f19817105de81222d56499c6b297641265.jpg)  
图6.与Hi-C细节对比图  
Figure 6.Detail comparison with Hi-C

图7给出了经典的基于直方图的BPDHE 算法，以及目前较为先进的EFF，MF，rR算法的实验结果，第一行局部放大细节中能看出，BPDHE 方法使得图像局部过度增强且细节模糊，本文算法的增强图对细节增强效果更好，边缘结构也较为稳定。第二行为各个算法对应的直方图，根据直方图像素值的分布情况可看出，MF 算法的可视化效果最好。对比其他增强算法，本文算法在保证对比度和亮度增强的同时，能复原出更精细的细节结构。如表二所示，我们对不同算法分别计算了标准差和信息熵。这两者可有效的反映图像的对比度和亮度信息。其值越大，表示图像信息丰富。亮度误差[]（LightnessOrder Error，LOE）能够客观的衡量图像的亮度失真情况，值越小代表亮度越好。SSIM（structuralsimilarity）可用来衡量图像恢复质量，是图像亮度，对比度和结构对比三者均评估的指标。其值越接近于1，图像质量越好。表中的方法均与Hi-C 图像作对比计算 SSIM。相较而言，虽然本文算法运行时间较长，但对细节结构的增强更为准确。

图7.不同增强算法对比  
![](images/2c81be187255e622a0398f2d83ab7c8805288995dd7d99f7344269b9b60a9959.jpg)  
Figure7.Comparison of different enhancement algorithms

# 表二.图像增强测量参数

Table2.Image enhancement measurement parameters   

<html><body><table><tr><td></td><td>AIA</td><td>BPDHE</td><td>EFF</td><td>MF</td><td>rR</td><td>Ours</td></tr><tr><td>Standard deviation</td><td>647.7</td><td>953.1</td><td>1768</td><td>1974. 6</td><td>2270.1</td><td>2416.9</td></tr><tr><td>Entropy</td><td>2.679</td><td>6.428</td><td>7.223</td><td>7.653</td><td>7.306</td><td>11. 873</td></tr><tr><td>LOE</td><td>871</td><td>926</td><td>374</td><td>326</td><td>344</td><td>349</td></tr><tr><td>SSIM</td><td>0.2708</td><td>0.210</td><td>0.303</td><td>0.435</td><td>0.326</td><td>0.716</td></tr><tr><td>Running time(s）（400×400)</td><td>一</td><td>1. 033</td><td>1. 134</td><td>1.332</td><td>21.151</td><td>13. 718</td></tr></table></body></html>

# 4结论

本文提出了一种基于盲退卷积的太阳 AIA 图像质量增强方法，基于图像功率谱特性的PSF估计模型，从AIA图中估计出PSF，最后退卷积出增强图像。文中采用轮廓切片分析评估方法准确性，功率谱分析评估方法有效性，不同区域 PSF分析评估方法的合理性。实验结果表明，本文方法对SDO/AIA193A,171A,211A 波段图像增强效果较好，尤其纹理细节，边缘结构的增强效果最好。其次，本文算法也有一定的噪声抑制效果，得益于PSF相位估计过程的松弛设计，恢复新细节结构也较为准确，因为这三个波段的图像噪声较小，日冕结构特征也更丰富和明显，能够更为准确的估计出模糊核。对比其他图像增强方法，本文方法的实时性较差，PSF 估计和退卷积的最优化迭代过程是主要的耗时原因。将来可以通过提高计算设备的性能和采用较为快速且有效的最优化方法来提高算法的实时性。在 AIA 的其他波段图像中，同样可以观测日冕的 SDO/AIA94A，131A，335A波段图像噪声很大，异常点较多，结构相对模糊导致增强效果不佳，将来能够通过研究更好的去噪算法和对噪声更加鲁棒的退

卷积算法对其他波段有效增强。

# 参考文献(References):

[1]王瑞，徐稚，杨磊，等．基于直方图规定化的太阳图像增强方法[J].天文研究与技术,2018,15(2):158-168. WangRui,XuZhi,YangLeietal.Solarimageenhancementbasedonhistogramspecification[J].AstronomicalResearch&Technolo   
gy,2018,15(2):158-168.   
[2]Yung-YaoCEposebasdedaicgaalatifogtrastaceentJ]teatioaualooti & Smart Technology,2015,4(4):27-38.   
[3]ZYing,GLiYeneal.Anewimagecotrastehancementalgorithusingexposurfusionframework[C].InteatioalCofereceon Computer Analysis of Images and Patterns,2017:36-46.   
[4]Xu,Dng,aglsibsiodfoealladgs]iaoes,6.   
[5]MLiJLiu,WYangetal.tructureevealinglow-lightiageeancementviaobustRetieodel[J].EETrasactiosoger cessing,2018,27(6):2828-2841.   
[6] PaoloGrigis，Yingna Su，Mark Weber，etal.AIAPSFcharacterzationandimagedeconvolution.SDODocumentation.2012 (http://www.lmsal.com/sdodocs)   
[7]PaJ,ZtaKetifotcuefoobtoebug]alrigtio 2013,28(9):1156-1170.   
[8]GoldsteiFtaeatralisCi.   
[9]SunghyunCho.Hybridimagedebluringbyfusingedgeandpowerspectruminformation[C].EuropeanConferenceinComputerVision(ECCV),2014:79-93.   
[10]LemenJR,TitleA,AinJ,etal.eAtosphericIagingsebly(A)oeSolarDamicsObsevatory(SDO)[J].oayic 2012,275(1-2):17-40.   
[11]KobayashiK,Crtai,WebargerAetal.TeigResolutionoroalIager(H-C)[J].Solarysics,4(89):441.   
[12]RachelerL,ebger,geSet.igRsolutioCoalgeFig2.1Jolarics,4)4.   
[13] Hu W,XueJ.PSFestimationviagradientdomaincorrelation[J].IEETransactionsonImageProcessing,2O12,21(1):386-392.   
[14]FienupJR,Wackerman CC.Phase retrieval stagnation problems and solutions[J].J.opt.soc.am.a,1986,3:1897-1907.   
[15] Luke,DRussellRelaxedaveragedalternatingreflections fordifractionimaging[J].InverseProblems,2O4,21(1):37-50.   
[16]ChenL,SunQWangFPoisonimagedeconvolutionbpromotinghyper-Laplacianpriorwithgeneraledlp/qegularzatioJ].Otical Engineering,2019,58(9):1.

# AIA Images Enhancement Method Based on Blind Deconvolution Mu Fang', Huang Huan', Shang Zhenhong1,3\*, Qiang Zhenping²

(1.Faculty of Information Enginering and Automation,Kunming Universityof Scienceand Technology,Kunming 650500 2.College of Big Data and Intelligent Engineering,Southwest Forestry University,Kunming650224; 3.Yunnan KeyLaboratoryof Artifical Intellgence,Kunming Universityof Science and Technology,Kunming650500)

Abstract: There are various physical activities in the solar image,such as different scales,brightness and structure.Due to the high dynamic activity of the solar corona and sensor equipment, the image quality of the solar image is poor. According to the characteristics of large dynamic range,large noise and relatively fuzzy structure of diferent waveband data structures captured by the atmospheric imaging asset (AIA)of the solar dynamic Observatory (SDO),an effective SDO /AIA image enhancement method based on blind deconvolution is proposed in this paper. Firstly,the SDO /AIA image is denoised and the dynamic range is reduced. Based on the distribution assumption of image power spectrum,the point spread function (PSF) is estimated from the original image Then,phase retrieval algorithm is used to recover the phase of PSF,and then deconvolute the high-quality target image; finaly,the enhancement results are analyzed quantitatively and qualitatively through slice analysis, power spectrum analysis and PSF analysis. The experimental results show that,compared with the existing image enhancement methods,the proposed method can efectively enhance the detail structure of the solar corona image,and restore the structure that cannot be identified due to the blur of the original image.

Key words: solar image; SDO/AIA; power spectrum; blind deconvolution; phase retrieval