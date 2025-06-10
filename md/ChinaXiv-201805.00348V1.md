# 改进金字塔融合技术的低照度图像色彩恢复和细节提取

谢伟1，胡欢君1，王莉明‘，涂志刚²(1．华中师范大学 计算机学院，武汉 430079;2．南洋理工大学 电器电子工程学院，新加坡 639798)

摘要：针对低照度图像亮度大、色彩不均衡的现象进行了改进金字塔融合技术的低照度图像色彩恢复算子的研究。该算法将原图和用去雾模型或MSRCR改善后的预处理图用金子塔技术将色彩对比度、饱和度、曝光亮度三者融合到金字塔算法中，并根据图像的信息赋予了不同的权重参数，从而能够有效地解决传统低照度图像色彩增强存在的问题。并提出一种CIELAB 通道内用加权最小二乘数的保边平滑滤波器平滑L通道的图像，设置不同的色调映射的参数值来提升图像细节信息的算子，使夜视中图像的信息更显眼和真实。实验结果表明，所提算法在低照度图像色彩增强中有了很好的效果，并在信息熵和psnr评价取得了约 $10 \%$ 的质量提升。所选择三种不同类型的图像进行实验，图形质量都得到了提高，也表明所提算法具有一定普适性。

关键词：金字塔；去雾模型；MSRCR；自适应参数；WSL；色调映射；细节提升 中图分类号：TP391.41 doi:10.3969/j.issn.1001-3695.2017.09.0960

# Color reduction and detail extraction of low illumination image with improved pyramid fusion

Xie Wei1,Hu Huanjun1, Wang Liming1, Tu Zhigang² (1.CollegeofComputercience,CentralChinaNormalUniversityWuhan4o79,China;2.CollgeofElectrical&Electroic Engineering,Nanyang Technological University,Singapore 639798)

Abstract:Aimingatthephenomenonthatthelow luminanceimageis brightand thethecolorisnotbalanced,this paperhad carriedonthestudyofthecolorrecoveryoperatorofthelow ilumination image with improved pyramid fusion technology.The algorithmcombinedtheoriginalimageandthepretreatmentdiagram withthedefogmodelorMSRCRtofuse thecolorcontrast, saturation and brightness into the pyramid algorithm with thegold tower technique,and assign different weight parameters according totheinformationoftheimage,whichcouldefectivelysolvethetraditionallow-lightimagecolorenhancement problems.And it proposedaFouriersmoothing filter with weighted least squares inthe CIELABchanneltosmooththeimage oftheLchannel,settheparametersofdifferenttone mappngtoenhancetheimagedetailinformation,sothat theinformation of the image innight vision ismore Conspicuous and true.Itselectedthree diferenttypes ofimages forexperimentation,and improved the quality of graphics.It also shows that this algorithm has some universality.

Key Words: pyramid; defog model; MSRCR; adaptive parameter; WSL; Tone mapping; detail prmotion

# 0 引言

随着互联网的时代的到来，高清图像和视频监控技术迅速发展起来，但在晚上或者白天光亮不足的地方，拍摄的图像和视频质量不高。为了便利人们的工作或者满足大家的视觉要求，就必须对这些质量不佳的图片进行增强处理，即低照度图像处理来改善图像的质量。

低照度图像处理一直是近几年的研究热点。传统的低照度图像增强的算法有直方图均衡化、灰度变换。这些算法原理简单、计算复杂度低，但在处理过程中容易造成图像的色彩丢失和噪声过大等问题。Zhou 等人[1]在 2014年此提出了一种同时增强全局亮度及局部对比度的方法,但是只对一些特定的图像有效果，且效果也不明显。Land等人在俄亥俄州第一次描述了Retinex思想，并建立了Retinex照射反射模型，之后Jobson等人[2.3]模仿人类视觉系统发展了Retinex算法，从单尺度Retinex算法（single scaleretinex,SSR）改进成多尺度加权平均的Retinex算法（multi-scaleretinex,MSR),再发展成带彩色恢复的多尺度 Retinex 算法（multi-scale retinex with color restoration,

MSRCR)。Wang等人[4提出了多尺度Retinex彩色图像增强算法,该算法可改善色彩失真，但算法复杂度大,自适应性差。随后将Retinex用到了图形去雾过程中[5]和低照度图像增强中[6],取得了不错的结果。但色彩和噪声问题仍然存在。Li等人[7专门针对低照度的去噪和对比度进行低照度图像加强,Su 等人[8]则采用两步噪声压缩的方法改善低照度图像的噪声。2011年,Dong等人[将低照度图像进行求反,得到与雾天图像的相似图,用去雾的算法来改进低照度图像的质量。随后王小元等人[10]也在此基础上做了改进,提出了基于物理模型的低照度图像增强算法。

1987年，Burt等人[1]提出了拉普拉斯金字塔变换,随后他将该变换应用到图像融合中,首次提出了基于拉普拉斯金字塔的图像融合算法[12],并获得了较好的融合效果。随后 Merterns 等人[13]将融合技术用到了高动态范围图像中,对一系列不同曝光程度的图片进行融合处理,但是在图像边缘信息上保持效果不好。后来,Singh等人[14]在这个的基础上加入引导滤波改进了图像的融合技术，图像细节和边缘信息更加明显,质量得到了明显改善。

针对低照度图像中对比度大、色彩失真的问题，本文提出一种将改进融合金字塔技术的低照度图像色彩恢复和细节提取算法，在保持图像细节信息的同时，使图像的色彩更均衡，符合人眼的视觉效果。

# 相关算法分析

# 1.1金字塔融合技术

金字塔融合技术经常使用在多曝光图融合中，本文将这种算法应用到低照度图像增强过程中来。具体步骤如下：首先，将一组图片(本文 $I ^ { \textit { n } }$ ，表示 $n$ 个输入融合图像（ $n = 1 , 2 .$ 分别代表原图、预处理图）进行高斯金字塔分解，设源图像为 $G _ { 0 }$ ,将 $G _ { 0 }$ 当做高斯金字塔底层,对输入图像与具有低通特性的窗口函数$w ( m , n )$ 进行卷积,再将卷积出来的结果进行隔行隔列的下采样,得到高斯金字塔的上一层，每一级图像均为前一级图形与具有低通特性的窗口进行卷积后作隔行隔列降采样得到的，如式(1)所示。

$$
G _ { L } ( i , j ) = \sum _ { m = - 2 } ^ { 2 } \sum _ { n = - 2 } ^ { 2 } w ( m , n ) G _ { L - 1 } ~ ( 2 i + m , 2 j + n )
$$

$$
1 \le L \le N , 0 < i < C _ { L } , 0 < j < R _ { L }
$$

即 $G _ { 0 } , G _ { 1 } , \cdots$ ， $G _ { N }$ 便构成了一个高斯金子塔图像。其中：$G _ { L } ( i , j )$ 为第 $L$ 层高斯金字塔图像； $G _ { 0 }$ 为源图像作为金字塔的底层； $N$ 为金字塔的总层数； $\boldsymbol { C } _ { L }$ 为金字塔第 $L$ 层列数； $R _ { L }$ 为金字塔第 $L$ 层的行数。然后将 $G _ { L }$ 的内插放大。内插的灰度值是对原来像素的灰度值加权平均得到的,这样便可以得到放大后的图像 $\boldsymbol { G } _ { L } ^ { * }$ ,使放大后的图像的尺寸与 $G _ { L - 1 }$ 的尺寸大小相同。由于 $G _ { L }$ 是通过对 $G _ { L - 1 }$ 卷积降采样得到的,所以 $\boldsymbol { G } _ { L } ^ { * }$ 所包含的信息是少于 $G _ { L - 1 }$ 的。由 $L P _ { 0 } , L P _ { 1 }$ ,…， $L P _ { N }$ 构成了拉普拉斯的细节金字塔,如式(2)所示。

$$
\begin{array} { r l r } & { L P _ { L } = G _ { L } - E x p a n d ( G _ { L + 1 } ) \qquad } & { 0 \leq L \leq N } \\ & { L P _ { N } = G _ { N } \qquad } & { L = N } \end{array}
$$

按照上述公式,从拉普拉斯金子塔最顶层开始逐层由上至下,细节信息逐层递加,最终便可得到细节增强后图像 $G _ { 0 } ^ { ' }$ ，如式(3)所示。

$$
\begin{array} { l l } { G ^ { ' } { } _ { N } = L P _ { N } } & { L = N } \\ { G ^ { ' } { } _ { L } = L P _ { L } + E x p a n d ( G _ { L + 1 } ) } & { 0 \leq L \leq N } \end{array}
$$

其中：金字塔技术可以增强一幅图像的质量，也可以融合增强几幅不同曝光程度的图像的质量，但直接使用其进行增强，效果不明显，所以提出改进算子来提升图像的色彩信息和细节。

# 2 改进金字塔融合算法

本文算法将金字塔图像融合技术运用到低照度图像增强中来,提出了基于加权参数的金字塔融合的低照度图像色彩增强算法。该算法思想如下：将输入的低照度图像进行传统的图像增强处理,得到预处理图；然后和原图进行金字塔细节图像增强，并设置自适应参数权值的三个度量因子来提取图像的细节和色彩信息,得到图像融合的融合权重；最终融合两幅图像的重要信息,得到质量更高的增强图像。

# 2.1度量因子

为了改变图像的色彩失真、不均衡的现象，本文引入了三个度量因子来恢复图像的色彩信息，分别是对比度、饱和度和明亮度。图像的色彩是衡量一张图像质量的重要指标，而色彩的饱和可以让图像看起来更加生动和形象。不同的图像的亮度也不一样，人的视觉系统观察到的细节信息的多少与图像的曝光亮度有着直接的关系，太亮或太暗的图像不能传递任何的细节信息。所以选择这三个因子作为度量来融合进金字塔技术中，提升图像的色彩质量。

# 2.1.1色彩对比度

首先对输入图像 $I ^ { n }$ 的灰度图 $G ^ { n }$ 应用拉普拉斯滤波器 $L$ ，得到原图像的高通部分 $D ^ { n }$ ,包含细节信息.再对 $D ^ { n }$ 的绝对值应用高斯低通滤波器 $\varphi _ { 2 }$ ,平滑得到对比度度量因子 $C ^ { n }$ 。

$$
D ^ { n } ( i , j ) = G ^ { n } ( i , j ) ^ { * } L
$$

$$
C ^ { n } ( i , j ) = \left| D ^ { n } ( i , g ) \right| * \varphi _ { 2 }
$$

# 2.1.2色彩饱和度

在输入图像 $I ^ { n }$ 的颜色通道 $R \setminus G \setminus B$ 通道数据 $I _ { R } ^ { n } \setminus I _ { G } ^ { n }$ 、$\boldsymbol { I } _ { B } ^ { n }$ 先求平均得到 $\boldsymbol { I } _ { a \nu g } ^ { n }$ ,再做标准差,可以得到饱和度度量因子A。

$$
I _ { a \nu g } ^ { n } \left( i , j \right) = \frac { ( I _ { R } ^ { n } ( i , j ) + I _ { G } ^ { n } ( i , j ) + I _ { B } ^ { n } ( i , j ) ) } { 3 }
$$

$$
\boldsymbol { A } ^ { n } ( i , j ) = \left| \frac { ( ( I _ { a \nu g } ^ { n } ( i , j ) - I _ { R } ^ { n } ( i , j ) ) ^ { 2 } + ( I _ { a \nu g } ^ { n } ( i , j ) } { 3 } ) ^ { 2 } )  { \frac { - I _ { G } ^ { n } ( i , j ) ) ^ { 2 } + ( I _ { a \nu g } ^ { n } ( i , j ) - I _ { B } ^ { n } ( i , j ) ) ^ { 2 } ) } { 3 } } \right|
$$

# 2.1.3曝光亮度

曝光亮度合适的图像能呈现丰富的纹理细节和色彩信息，而过曝光和欠曝光区域则不能几乎不能传递什么信息。首先将图像分成R、G、B三个颜色通道并做归一化处理，根据各个像素的曝光度利用高斯方程为每个像素分配相应的权值，同时也排除一些太亮和太暗(即多曝光和欠曝光)像素对融合产生的影响。其公式定义如式（8）所示。

$$
E _ { R } ^ { n } ( i , j ) = e ^ { - \frac { [ I _ { R } ^ { n } ( i , j ) - \mu ( i , j ) ] ^ { 2 } } { 2 \sigma ^ { 2 } } }
$$

其中： $E _ { R } ^ { n }$ 表示像素 $( \mathrm { i } , \mathrm { j } )$ 在 $\mathtt { R }$ 通道分配的权值； $\sigma$ 为高斯方程的标准差，取值为0.2； $\mu ( i , j ) = 0 . 5 + 0 . 2 5 ^ { * } \left[ \frac { 1 } { N } \sum _ { n = 1 } ^ { N } I _ { R } ^ { n } ( i , j ) - 0 . 5 \right] \circ$ 并对 $\boldsymbol { I } _ { R } ^ { n }$ 设置一个阈值 $T$ ，当 $T < I _ { R } ^ { n } < 1 - T$ 时，该点的像素值满足要求，即是曝光亮度合适的点，可以提供细节和色彩信息；若 $\boldsymbol { I } _ { R } ^ { n }$ 不在此范围内，当 $0 \leq I _ { R } ^ { n } \leq T$ 或者 $1 - T \le I _ { R } ^ { n } \le 1$ 时，给这些像素分配权值为0,避免这些不合适的像素对融合结果产生影响，根据实验效果，本文 $T$ 取0.1。对G和B通道进行相同步骤的处理，得到 $E _ { G } ^ { n }$ 和 $\boldsymbol { E } _ { B } ^ { n }$ 。即图像像素(i,j)的权值分配为

$$
E ^ { n } = E _ { R } ^ { n } * E _ { G } ^ { n } * E _ { B } ^ { n }
$$

# 2.2权重参数融合

经过低照度图像增强预处理后，生成的图像和源图像的有效信息也不相同。显然,包含细节信息较多和色彩更饱满的部分应该赋予更大的权重,综合考虑色彩对比度、饱和度、明亮度。每个因子赋予不同的权重参数,分别为 $\lambda _ { 1 }$ 、 $\lambda _ { 2 }$ 、 $\lambda _ { 3 }$ 。根据大量的实验数据显示， $\lambda _ { 3 }$ 选择1是最好的，图像亮度不宜过大，否则图像色彩信息太明艳。 $\lambda _ { 1 }$ 的值为了体现图像的颜色的对比度，选择2或3最佳。 $\lambda _ { 2 }$ 最适合的值是 $[ 0 \sim 5 ]$ 间的正整数，具体的值要根据图像的信息来整合，如果图像太亮，则饱和度选择较小的值如2，否则就如3或4。最后选择将三个度量因子相乘,得到 $\stackrel { \wedge } { W } ^ { n }$ ,然后归一化 $\stackrel { \wedge } { W } ^ { n }$ ，确保权重参数使用到每一个像素值上，最终得到初始的融合权重 $\boldsymbol { W } ^ { n }$ 。

$$
\stackrel { \wedge } { W ^ { n } } ( x , y ) = C ^ { n } ( x , y ) ^ { \lambda _ { 1 } } \times A ^ { n } ( x , y ) ^ { \lambda _ { 2 } } \times Y ^ { n } ( x , y ) ^ { \lambda _ { 3 } }
$$

$$
\begin{array} { c c c } { { W ^ { n } = \displaystyle \frac { \stackrel { \wedge } { W } ^ { n } ( x , y ) + \varepsilon } { \displaystyle \sum _ { n = 1 } ^ { N } ( W ^ { n } ( x , y ) + \varepsilon ) } } } \end{array}
$$

其中： $N$ 取3。为了避免出现除零的情况，本文加入了一个ε值，在这里， $\varepsilon$ 取一个小的正值,如 $1 0 ^ { - 1 2 }$ 。

得到的这个权重融合值是加入到金字塔技术中去的，原始的金字塔技术在重建过程中使用的是如下公式：

$$
\begin{array} { l l } { { G _ { N } = L P _ { N } \ } } & { { L = N } } \\ { { G _ { L } = L P _ { L } + E x p a n d ( G _ { L + 1 } ) \ } } & { { 0 \leq L \leq N } } \end{array}
$$

将 $\boldsymbol { W } ^ { n }$ 融入公式后变成了：

$$
\begin{array} { l r } { { } } & { { G _ { N } = L P _ { N } \ } } & { { L = N } } \\ { { } } & { { G _ { L } = W ^ { n } * L P _ { L } + E x p a n d ( G _ { L + 1 } ) \qquad 0 \leq L \leq N } } \end{array}
$$

根据上式最后的结果图。

# 3 细节提升算子

晚上的视频监控需要对低照度图像更细节的信息进行增强。例如晚上违规的汽车的车牌照、犯罪分子的人脸，这些都需要对低照度图像增强后，将图像中的部分内容提取出来，然后增强得到所需要的信息。第二部分就是对图像所需提取的部分进行细节增强。它的效果对整张图像或许不是很好，但对于部分细节质量提升有很大的帮助。

# 3.1平滑滤波的选取

低照度图像在恢复色彩过程中容易产生噪声，所以在细节提取前需要对图像进行平滑来减轻噪声的影响。常见的基于去躁的是双边滤波和引导滤波，但双边滤波在去躁过程中容易丢失纹理细节信息，而引导滤波改进了这一点，但也有它的缺陷，平滑后的图像容易产生光晕，特别是在梯度较大的位置，都不太适合用到细节提取过程中来，本文选择的是基于加权最小二乘法的保边缘平滑滤波器(WLS)。为了避免图像在平滑过程中产生额外的噪声，本文的图像平滑是在lab通道中进行的。大量的实验数据表明，在lab 通道中处理图像比在rgb通道中处理图像噪声会小很多。以一维信号为例，简要分析双边滤波平滑图像、引导滤波平滑图像、WLS滤波增强图像的对比。WLS滤波不仅能够保证除去噪声，还对图像的边缘和细节信息得到保留。结果显示如图1所示。

由图1(a)可以看出，双边滤波对图像的平滑效果明显差于引导滤波和WLS滤波，在尖峰和低估区域，平滑力度不够，在一些噪声大的区域，只达到了减缓没有很好的去躁能力。引导滤波和WLS的差别不大,而由图1(b)中，WLS滤波在噪声大和梯度信息明显的区域效果更好，且WLS是分通道进行图像平滑的，在L通道进行平滑图像效果更好，即滤除了原始图像的噪声，有能防止在平滑过程中产生新噪声，使得图像在细节提

取上能取得更好的结果。

![](images/445acfaf18924ad6dce89c9210cacdc4102405742c3b05bcbb4033135489b2af.jpg)  
图1三种滤波方法对一维信号处理效果对比

加权最小二乘(werghted least squares,WLS)滤波器是基于加权最小二乘法的最优值来进行图像的平滑。给定输入图像g,寻找目的图像u,使得 $\mathrm { ~  ~ u ~ }$ 在尽可能接近 $\mathbf { g }$ 的同时，图像的细节也尽可能地平滑保存。这表示寻求最小值,用如下公式表示：

$$
\sum _ { p } \left( \left( u _ { p } - u _ { g } \right) ^ { 2 } + k \left( a _ { x , p ( g ) } { \left( \frac { \widehat { o } u } { \widehat { \sigma } x } \right) } _ { p } ^ { 2 } + a _ { y , p ( g ) } { \left( \frac { \widehat { o } u } { \widehat { \sigma } y } \right) } _ { p } ^ { 2 } \right) \right) ^ { ( 2 ) }
$$

其中：下标 $p$ 表示像素的空间位置；数据项 ${ ( u _ { p } - u _ { g } ) } ^ { 2 }$ 表示输入图像8与目的图像 $u$ 之间的差距，使其尽可能小，后面的项数表示通过对 $\mathrm { ~  ~ u ~ }$ 求偏导来实现图像平滑。根据输入图像 $\mathbf { g }$ 确定两个平滑权重 $a _ { x }$ 和 $a _ { y }$ ， $k$ 则是负责这两项之间的平衡，增加$k$ 值会使图像更平滑。一般 $k$ 的默认值是1.0。但在本文中，为了突出图像的细节，参数设定不能太大，本文设置的分别是0.125和0.5。在色调映射时，涉及到了两个细节，所以需要有两个不同参数的平滑图像。将lab通道中的 $L$ 通道图进行WLS滤波后，得到 $\boldsymbol { L 1 }$ 和 $L 2$ ，用 $L$ 图分别减去滤波后的图像 $\boldsymbol { L 1 }$ 和$L 2$ 得到了图像的细节。

# 3.2 色调映射

色调映射主要解决的问题是进行大幅度的对比度衰减将场景亮度变换到可以显示的范围，同时要保持图像细节与颜色。本文定义一个函数，旨在CIELAB色彩空间中获取图像，并根据设置的参数进行色调映射。具体步骤如下：给定一张图像，从$r g b$ 通道换到 $l a b$ 通道，得到 $l a b$ 图，提取L分量，进行WLS滤波并相减得到的 $d ^ { 1 }$ 和 $d ^ { 2 }$ ，lab是一张粗糙的含有少量信息的图，定义为基础层 $b$ ；然后用一系列的滑块控制基础层 $b$ 的曝光值 $\eta$ ，给对应基础层提供一个增强因子 $\delta ^ { 0 }$ ，对应两细节层的增强因子 $\delta ^ { 1 }$ 、 $\delta ^ { 2 }$ ；最后给每个像素 $p$ 实现下列公式操作：

$$
\stackrel { \wedge } { g _ { p } } = \mu + S ( \delta ^ { 0 } , \eta b _ { p } - \mu ) + S ( \delta ^ { 1 } , d _ { p } ^ { 1 } ) + S ( \delta ^ { 2 } , d _ { p } ^ { 2 } )
$$

其中： $\mu$ 是亮度范围的平均值； $s$ 是一个数学模型曲线，公式表示为

$$
S ( a , x ) = 1 / ( 1 + \exp ( - a x ) + 0 . 5 )
$$

$s$ 表示适当的将曲线移动和归一化，数据0.5是大量实验得出来的值。定义 $S ( a , x )$ 的目的是避免当细节层信息被大量提升的时候，图像太生硬和突兀。 $S ( \delta ^ { 0 } , \eta b _ { p } - \mu )$ 是控制基础层（204号 $b$ 的曝光和对比度，而 $\mu$ 、 $S ( \delta ^ { 1 } , d _ { p } ^ { 1 } )$ 、 $S ( \delta ^ { 2 } , d _ { p } ^ { 2 } )$ 则控制两细节层的提升。 $S ( \delta ^ { 0 } , \eta b _ { p } - \mu )$ 、 $S ( \delta ^ { 1 } , d _ { p } ^ { 1 } )$ 、 $S ( \delta ^ { 2 } , d _ { p } ^ { 2 } )$ 三个参数是在[-1,1]内，曝光度 $\eta$ 和饱和度在零到无穷大范围内，gamme 在(0,1]的内。

# 3.3 gamme色彩校正

Gamme校正就是对图像的伽马曲线进行处理，主要原理是对图像进行非线性色调编辑，检出图像信号中的深色和浅色部分，并使两者比例变大，提高图像的对比度效果。需要对每个像素值进行校正，先将像素值归一化得到A，根据伽马公式求出像素归一化后的数据1/gamme为指数的对应值，即$A ^ { 1 / g a m m a }$ 。对归一化后的值进行色彩补偿。Gamme只要是针对颜色太过艳丽、对比度非常大的图像。一般的默认值是1，但在图像太明亮的情况下，可以适当地调小，根据具体要求来设定。

# 4 实验结果与分析

本文实验在MATLABR2014a上运行，运行环境是Inter(R)Core(TM) i7-6700 CPU $@$ $\mathcal { D } \ 3 . 4 0 \ \mathrm { G H z }$ ，操作系统是64位Windows7,实验数据分析采用主观评价与客观评价相结合的方式。

# 4.1权重融合算法的实验对比

# 4.1.1主观评价

本文从近两年用的比较多的低照度图像增强算法在进行改进，提出了低照度图像色彩恢复和重要信息增强提取的算法。用去雾模型[]和多尺度Retinex的色彩恢复[作为对比算法来验证本文的算子的优越性。且本文通过三组不同类型的图像来验证提出的算法。实验1选择的是含有点光源的低照度图像；实验2选择很暗的低照度图像；实验3选择透光的低照度图像。从三组不同的实验来进行图像质量的评价，分别从主观评价和客观评价两个方面来比较，图像的质量都得到了提升。其结果如图 $2 { \sim } 5$ 所示。

实验结果分析：实验1、2、3中图(b)和(d)是分别用去雾算法和MSRCR算法实现的低照度增强后的效果，但是它们对比度差,色彩不均衡,细节信息不明显；(c)和(e)是在它们的基础上加入改进金字塔技术后融合生成的图像,结合了原图和预处理图后的两者的优点,使结果图的色彩更饱满,符合人眼的视觉效果。实验1中，图(b)和(d)在黑色墙上还存在明显的光晕现象,色彩太过明亮；而(c)和(e)色彩得到了很好的恢复，地毯的细节信息也更加明显清晰,光晕现象也不明显；(f)是对(c)的细节增强,可以看出整个图像的色彩得到了提升，边缘更明显，细节部分也更突出。在实验2中，图(b)严重失真；(b)和(d)娃娃脚下的盘子失去了原本的轮廓,桌子上的颜色都掉色了，色彩很不均衡,而且(b)图像的噪声很大；但是(c)和(e)盘子有明显的形状,桌子颜色恢复正常,整体色彩也更均匀,不突兀,噪声也小了很多。实验3中，图(b)和(d)亮度、对比度太大,颜色太艳丽,看上去很刺眼,而且图像太平滑，一些建筑物的角落细节信息已经丢失了，窗户外面的东西因为太亮而看不清；但是(c)和(e)色彩很饱满,也不觉得对比度很强烈,建筑物的细节信息也很清晰,图像质量大大提高。总的来说,本文算法在原基础上图像质量得到了很大的提高。

有为合合合合(a)原图 (b)去雾模型增强图 (c)本文算法 (d)MSRCR增强图 (e)本文算法 (f)细节增强图

![](images/7606569b0d100decf27e6bc01b104c4ad094a8ae1a0cb367e040c205920dfc19.jpg)  
图2实验1图像质量对比

![](images/b5eaa555fa7c374b94249e9179aa0a71f960b2a41d9a3ec2fd09673b0cf0c69b.jpg)  
图3实验2图像质量对比  
图4实验3图像质量对比  
图5三组实验中(a)(c)(e)(d)的局部细节放大图

省合者

# 4.1.2客观评价

对低照度图像的质量判定，仅仅是主观评价是不够的，本文还使用了四个客观评价标准对算法的增强效果进行客观评价，分别是信息熵、平均梯度、SSIM(结构相似性)和PSNR(峰值信噪比)。其中,信息熵是从信息论的角度反映图像信息丰富程度，通常情况下，图像信息熵越大,其信息量就越丰富；平均梯度可敏感地反映图像对微小细节反差表达的能力,在图像中,某一方向的灰度级变化率大,它的梯度也就大。因此，可以用平均梯度值来衡量图像的清晰度,还同时反映出图像中微小细节反差和纹理变换特征。SSIM反映了相邻像素之间的关联性,承载了场景中物体的结构信息,用来衡量图像的结构失真程度,其值越高说明两者结构相似性越高。PSNR是原图像与被处理图像之间的均方误差相对于 $( 2 \mathord { \uparrow } \mathfrak { n } - 1 ) \mathord { \uparrow } 2$ 的对数值,通常PSNR的值越高，表示图像质量越好，图像失真越小,噪声也越小。三组实验图像客观质量评价如表1所示。

表1三组实验图像客观质量评价  

<html><body><table><tr><td>分组</td><td>评价方法</td><td>(a)</td><td>(b)</td><td>(c）</td><td>(d)</td><td>(e)</td><td>(f)</td></tr><tr><td rowspan="3">第一 组实 验</td><td>entropy</td><td>7.0905 7.1457</td><td></td><td>7.5443</td><td>7.8201</td><td>7.8465</td><td>8.0577</td></tr><tr><td>Mean_gradient 5.1262 6.0148</td><td></td><td></td><td>6.1958</td><td>6.0694</td><td>6.3105</td><td>9.6743</td></tr><tr><td>ssim</td><td></td><td>0.5940</td><td>0.7836</td><td>0.5600</td><td>0.6842</td><td>0.7689</td></tr><tr><td></td><td>psnr</td><td></td><td></td><td>12.7371 19.0043 10.7568 14.0997 17.1874</td><td></td><td></td><td></td></tr><tr><td rowspan="4">第二 组实</td><td></td><td>(a)</td><td>(b)</td><td>(c)</td><td>(d)</td><td>(e)</td><td>(f)</td></tr><tr><td>entropy</td><td>6.0266 7.0683</td><td></td><td>7.4530</td><td>7.5983</td><td>7.4797</td><td>7.8668</td></tr><tr><td>Mean_gradient 2.9499 6.3878</td><td></td><td></td><td>6.5269</td><td>6.8518</td><td>6.9198</td><td>12.3283</td></tr><tr><td>ssim</td><td></td><td>0.3406</td><td>0.3564</td><td>0.2222</td><td>0.2543</td><td>0.2929</td></tr><tr><td></td><td>psnr</td><td></td><td></td><td>13.4962 14.6194</td><td>9.6498</td><td>10.6211 12.6524</td><td></td></tr><tr><td rowspan="4">第三 组实</td><td></td><td>(a)</td><td>(b)</td><td>(c）</td><td>(d)</td><td>(e)</td><td>(f)</td></tr><tr><td>entropy</td><td></td><td>7.3506 7.7121</td><td>7.8435</td><td>7.4396</td><td>7.5742</td><td>7.6269</td></tr><tr><td>Mean_gradient 5.6999 5.5103</td><td></td><td></td><td>6.3657</td><td>4.4834</td><td>5.7161</td><td>13.0024</td></tr><tr><td>ssim psnr</td><td></td><td>0.5868</td><td>0.7136 12.2530 15.7111 10.865413.671513.9120</td><td>0.5337</td><td>0.6852</td><td>0.6460</td></tr></table></body></html>

由表可知，在实验1、2中，图(c)和(e)的信息熵值和平均梯度比(b)和(d)都得到了提高，而且(c)比(b)的信息熵值大了约0.4,PSNR值也得到了很大的提高。实验3中,信息熵值也得到了提高,虽然没有实验1和2中的明显,但是PSNR也提高了不少。在细节提取部分，图(f)的主观评价值都得到了很大提高，特别是平均梯度，平均梯度主要反映的是细节信息，从侧面也证明了本文算法的良好性。

通过做这三组实验，从主观评价和客观评价充分证明了本文算法在原有基础上得到了很大的改进,图像的细节信息更丰富,整体对比度、亮度、色彩饱和度更符合人眼的视觉享受，图像的噪声也小了，还对部分图像能达到去除光晕的效果,并能广泛应用在多范围的低照度图像领域中,具有一定普适性。

# 4.2不同参数条件下细节信息提取对比

由于曝光度 $\eta$ ，gamma值和饱和度在前文中已经有涉及，默认值保持不变，曝光值 $\eta$ 默认值为1，gamme 值默认为1,饱和度默认值为也为1，具体可以根据要求变化，但本文设置的值都为1。而影响图像的细节质量主要的是 $\delta ^ { 0 }$ 、 $\delta ^ { 1 }$ 、 $\delta ^ { 2 }$ 的值。图 $6 { \sim } 8$ 是不同的参数值对细节提取的对比效果。

通过toy图像看出，在不同参数的基础层增强因子 $\delta ^ { 0 }$ 和两细节层的增强 $\delta ^ { 1 }$ ， $\delta ^ { 2 }$ 会出现不同的效果。本文取$\mathcal { S } ^ { 0 } = 2 5 , \mathcal { S } ^ { 0 } = 1 0 , \mathcal { S } ^ { 0 } = 1$ 进行了对 $\delta ^ { 0 }$ 参数对图像的影响的实现，分析图 $6 { \sim } 8$ 中的(a)， $\delta ^ { 0 }$ 越大，toy图像的细节信息更明显，图6的细节信息明显高于图7和8，图像的边缘区域和梯度大的地方如胡须和鼻子等部位有了更多的增强，整体图像的色彩也更加艳丽。对比整个图 $6 { \sim } 8$ ，基础层增强因子 $\delta ^ { 0 }$ 对整个图像的细节提取起到了最关键的作用。 $\delta ^ { 1 }$ 和 $\delta ^ { 2 }$ 控制着更微小的细节信息，分析图 $6 { \sim } 8$ 中(a)(b)和(a)(e)，图像得到了一定的平滑，在 $\delta ^ { 0 }$ 较大的情况下，图像的纹理信息更突出，没有(a)那么明艳，胡须毛部位保持得更好。在其他值不变的情况下，$\delta ^ { 1 }$ 越大，图像的平滑度会大一些，图像的整体效果好于值小的图像； $\delta ^ { 2 }$ 也控制图像的整体对比度，它放大了背景和事物的色彩对比，让图像中的实物突显出来，但也损失了部分细节，在其他值不变的情况下， $\delta ^ { 2 }$ 的值越大，背景和实物颜色对比越大，背景会偏暗，而实物却更亮。

![](images/f554af4ddfb38a5628e012450ce16cb98c733ed68c36db43e58ddc51390bf80d.jpg)  
图6时， $\delta ^ { 1 }$ 和 $\delta ^ { 2 }$ 不同参数效果

![](images/5c6b465cd3bcfd1e29aa176112523c0d3519976a85a8ee3c5887b5698253de5b.jpg)  
图7时， $\delta ^ { 1 }$ 和 $\delta ^ { 2 }$ 不同参数效果

$$
{ \mathrm { ~ l ) } } \delta ^ { 1 } = 1 , \delta ^ { 2 } = 1 \qquad { \mathrm { ( e ) } } \delta ^ { 1 } = 2 0 , \delta ^ { 2 } = 1 \qquad { \mathrm { ( f ) } } \delta ^ { 1 } = 1 , \delta ^ { 2 } = 2 0
$$

![](images/bb24b2f05ce8d59ef913a46d2f4a4746cc418902ad0c4aba38806ed3ab99d6d2.jpg)  
(d) 图8时， $\delta ^ { 1 }$ 和 $\delta ^ { 2 }$ 不同参数效果

# 5 结束语

本文提出了一种新的低照度图像增强的算法,将金字塔融合的应用到低照度图像增强中来,并改进了融合算法中的加权融合因子，使低照度图像色彩恢复效果更好,解决了近几年来将去雾和MSRCR用到低照度图像增强中的不足，如图像亮度和对比度大、色彩不均衡、噪声大等。本文算法将原始图和预处理图进行加权融合,通过融合中参数的选择和处理,将原始图与预处理图中的优点融合在一起,保证了图像信息不丢失、色彩饱和，更符合人眼的直观视觉等特点。为了得到更有效的图像，本文提出了一种细节增强算子，可将需要重点处理的局部图进行增强，得到需要的信息。通过三组不同低照度类型的实验,含有点光源的图像、很暗的图像、透光的图像都采用本文算法和传统的算法在从主观和客观两个方面进行比较,能够得出本文算法有着更好的效果。因此,本文算法成功克服了传统低照度信息细节不明显、色彩不均衡的问题,最终实现了一种有效的提高低照度图像质量的算法。

# 参考文献：

[1]Zhou Z,Sang N,Hu X.Global brightness and local contrast adaptive enhancement for low illumination color image [J].Optik-International Journal for Light and Electron Optics,2014,125 (6): 1795-1799.   
[2]Mccann JJ,Rizzi A.32.Retinex algorithms [M]//The Art and Science of HDRImaging.[S.1.]:John Wiley& Sons,Ltd,2011: 293-340.   
[3]Jobson D J,Rahman Z,Woodell GA.A multiscale retinex for bridging the gap between color images and the human observation of scenes [J].IEEE Trans on Image Processing,1997,6(7): 965-976.   
[4]Wang W,LiB, Zheng J,et al.A fast multi-scale retinex algorithm for color image enhancement [C]//Proc of IEEE International Conference on Wavelet Analysis and Pattern Recognition. 2oo8:80-85.   
[5]Xie B,Guo F,Cai Z. Improved single image dehazing using dark channel prior and multi-scale retinex [C]// Proc of IEEE International Conference on Intelligent System Design and Engineering Application.2011: 848-851.   
[6]Lee HG, Yang S,Sim JY.Color preserving contrast enhancement for low light level images based on Retinex [C]//Proc of IEEE Asia-Pacific Signal and Information Processing Association Summit and Conference.2015: 884-887.   
[7]Li L,Wang R,Wang W, et al.A low-light image enhancement method for both denoising and contrast enlarging [C]// Proc of IEEE International Conference on Image Processing.2015:3730-3734.   
[8]Su Haonan,Jung C.Low light image enhancement based on two-step noise suppression [EB/OL]. (2017-07-22).http://sigport.org/1523.   
[9]Dong X,Wang G,Pang Y,et al.Fast efficient algorithm for enhancement of low lighting video [C]// Proc of IEEE International Conference on Multimedia and Expo.2011: 1-6.   
[10]王小元，张红英，吴亚东，等．基于物理模型的低照度图像增强算法 [J]．计算机应用,2015,35(8):2301-2304.   
[11] Burt P J, Adelson E H. The Laplacian pyramid as a compact image code （204号 $[ \mathbf { M } ] / \AA$ Readings in Computer Vision:Issues,Problems,Principles，and Paradigms.[S.1.] : Morgan Kaufmann Publishers Inc.1987: 671-679.   
[12] Burt P J. The pyramid as a structure for efficient computation [M]// Multiresolution Image Processing and Analysis.Berlin: Springer,1984: 6- 35.   
[13] Mertens T,Kautz J,Reeth F V.Exposure fusion: a simple and practical alternative to high dynamic range photography [J]. Computer Graphics Forum,2010,28 (1): 161-171.   
[14] Singh H,Kumar V,Bhooshan S.A novel approach for detail-enhanced exposure fusion using guided filter [J].The Scientific World Journal, 2014 (2): 659217.