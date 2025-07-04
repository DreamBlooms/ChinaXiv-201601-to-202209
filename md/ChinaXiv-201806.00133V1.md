# 基于视觉颜色感知一光学相似的图像去雾方法

赵雪青la,1b,2，师昕la,1b,2

(1．西安工程大学a.计智能化陕西省重点实验室;b.计算机科学学院，西安 710048;2.新型网络智能信息服务国家地方联合工程研究中心，西安 710048)

摘要：针对雾霾环境影响致使户外获取的图像质量严重下降问题，提出了一种基于视觉颜色感知-光学相似的图像去雾方法。充分利用人眼感知颜色的视觉机理，结合图像的相似性原理，构造了光学相似度函数，建立了新的基于视觉颜色感知-光学相似的图像去雾模型并设计相关算法，进而进行仿真验证。仿真实验结果表明，提出的方法在对有雾图像清晰化处理过程中效果明显，并与现有的图像去雾方法在主观视觉和客观量化方面进行图像去雾效果对比，进一步表明提出的方法在清晰化含雾图像处理中取得了较好的效果。

关键词：视觉颜色感知；图像相似性；图像去雾 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2018.03.0192

# Image dehazing method based on vision color perception-photometric similarity

Zhao Xueqingla, 1b,2, Shi Xinla, 1b, 2 (1.a.ShaanxiKeyLaboratoryofClothingIntellgence,b.SchoolofComputerScience,XianPolytechnic University,Xi'an 710048,China;2.National&LocalJoint Engineering Research CenterforAdvancedNetworking&Inteligent Information Service,Xi'an 710048, China)

Abstract: This paper proposedanimage dehazing methodbasedonvisioncolorperception-photometric similarity,to solvethe outdoor-accessed images’qualitydecliningcaused bythe hazeenvironment.Theoptical similarity function isconducted by usingthe human vision color perception mechanism,combining with the principle ofimage similarity.Anew image dehazing model basedon visioncolorperception-photometricsimilarityis established,andtherelevant algorithmis designed.The simulation experimental results showed the proposed method has an obvious efect on dehazing image processing,while comparing with the existing relevant methods in terms ofsubjective visualandobjectivequantification,the proposed method achieves better results.

Key words: Vision color perception; Image similarity; Image dehazing

# 0 引言

随着现代科技的飞速发展，图像作为人类感知外界信息的重要媒介，已然与人类生活密不可分，然而，图像在获取过程中会受到各种因素的影响导致图像质量下降，其中，户外获取的图像往往会由于频发的雾靈天气环境影响致使图像质量严重下降，很多重要的图像特征被雾遮掩，从而影响其后续的应用价值[1]。鉴于对有雾图像的实际应用需求，自20世纪50年代以来，已有众多国内外学者致力于研究图像去雾，现有的图像去雾的方法主要从两个角度进行研究：一类是从有雾图像的特征入手基于图像对比度增强的角度；另一类是从图像复原方法入手基于图像物理模型的角度[2]。从增强图像对比度的角度，早期的一些研究方法，主要通过直方图均衡化方法来研究，此类方法能够在一定程度上提升去雾图像的视觉效果，但是由于直方图均衡化是对整幅图像进行处理，图像局部的细节信息并不能很好地得以体现，因此，Kim 等人[3提出了局部重叠子块直方图均衡图像去雾方法实现局部细节信息增强；艾等人[4通过消除邻域子块图像直方图之间的差异达到恢复去雾图像的细节信息；除此之外，基于Retinex 和基于小波变换等方法也被用于处理图像去雾以增强图像的对比度，如基于单尺度Retinex以及张赛楠等人[5提出了基于单尺度Retinex的改进算法，采用符合人眼视觉特性的拟合函数进行自适应调节单尺度Retinex函数，以增强含雾图像颜色特征，扩展其动态分布；根据含雾图像中雾霾信息的低频特性，曹永妹等人[在小波域上进一步扩展了Retinex算法，对雾霾和目标信息在不同尺度上分别进行处理，进一步提升了去雾图像的质量。从基于图像物理模型的角度，根据雾霾在形成过程中的物理意义，通过构建大气物理模型并反解获得的去雾图像。Kopf 等人[7首先通过GoogleEarth 获取3D地理信息特征，如场景深度信息、地表纹理特征等，然后对大气物理模型求解复原图像。Narasimhan 等人[8]通过与用户交互输入的方式获取上述信息，进而求得去雾图像。

近年来，He等人[9创造性的提出了一种基于暗通道先验的图像去雾方法，该方法基于大量的户外图像的统计先验，对于大多数的雾霾图像复原具有较好的性能，此外，He等人[10改进了基于暗通道先验的图像去雾方法，采用导向滤波的方法细化传输图进一步提高了图像去雾的性能，降低了时间复杂度。本文基于人类颜色视觉神经感知机理，提出了基于视觉颜色感知-光学相似的图像去雾方法，充分利用人眼视觉颜色感知特性，结合图像的相似度计算模型，构造新的基于视觉颜色感知一光学相似的图像去雾模型，然后估计透射率与大气光值，进而复原图像。。

# 1基于颜色视觉感知一光学相似计算模型的图像去雾方法

# 1.1人眼视觉颜色感知

# 1.1.1人眼视觉颜色感知生理机制

人眼感知外界物体的颜色主要通过视网膜感光和视网膜神经元信息传输两个过程。前者即三色感知机制，视锥细胞对不同波长（长、中、短）的光刺激产生不同的反映通道；后者是视网膜神经元信息传输阶段，即四色感知机制，分别由三色感知通道相互交错，形成黑一白、红一绿、黄一蓝对立色通道。第一个过程主要完成视网膜对光源的敏感反映，第二个过程主要完成人眼视觉神经元对颜色对立色通道的融合，视觉系统感受野区神经元细胞相互交错，从而形成更加复杂的颜色视觉感知。如图1中（a）（b）所示，颜色视觉在视网膜中的形成过程及光源在物体中的传播过程[I]。

![](images/44e5373071919224782cc6ab9a1f4e21e1823f9ed640d75437883fe4c350de4a.jpg)  
图1a)颜色视觉在视网膜中的形成过程;(b)光源在物体中的传播过程1.1.2人眼视觉颜色感知模型

人类视网膜如何通过感知物体的颜色来完成视觉信息处理任务，一直是人类视觉系统研究中的热点问题，而视觉颜色计算模型是阐明该研究问题的有效手段[12.13]。如式（1）所示，物体的颜色信息通过三种不同视锥细胞编码到三原色体系中。考虑到相邻视锥细胞之间的电耦合作用，对于输入图像 $I _ { \mathrm { c } } ( x , y )$ ，$c \in \{ R , G , B \}$ ，视锥细胞的响应为[14]

$$
F _ { c } ( x , y ) = I _ { c } ( x , y ) * g ( x , y ; \sigma )
$$

其中\*是卷积操作符， $g ( x , y ; \sigma )$ 是模拟视锥感受野的二维高斯函数。

$$
g ( x , y ; \sigma ) = { \frac { 1 } { 2 \pi \sigma ^ { 2 } } } \exp ( { \frac { - ( x ^ { 2 } + y ^ { 2 } ) } { 2 \sigma ^ { 2 } } } )
$$

其中： $\pmb { \sigma }$ 是二维高斯函数的标准差，主要用于控制其平滑程度。本模型中，根据实验经验，设置 $g ( x , y ; \sigma )$ 为 $\pmb { \sigma } = 3 . 0$ ，图像处理过程中滑动窗口大小为 $3 \times 3$ 。

# 1.2图像光学相似度计算模型

# 1.2.1图像的相似性

文献[15]中给出了二维图像的相似性假设、相似性原理、相关证明及图像相似度计算模型。令 $\nu = \{ \nu ( i ) | i \in I \}$ 表示一副二维图像，其像素点为 $i \in I$ ，且有 $I _ { i } \subset I$ ， $\left| I _ { i } \right|$ 表示集合 $I _ { \ O _ { i } }$ 的势，则图像的相似度计算模型可由式（3）来表示。

$$
\operatorname* { l i m } _ { | I _ { i } | \to \infty } \nu ^ { 0 } ( i ) = u ( i )
$$

其中：

$$
\nu ^ { 0 } ( i ) = \frac { \sum _ { j \in I _ { i } } w ^ { 0 } ( i , j ) \nu ( j ) } { \sum _ { j \in I _ { i } } w ^ { 0 } ( i , j ) }
$$

$$
w ^ { 0 } ( i ) = \exp ( - \frac { \left\| \nu ( N _ { i } ^ { 0 } ) - \nu ( N _ { j } ^ { 0 } ) \right\| _ { 2 , a } ^ { 2 } } { 2 h ^ { 2 } } )
$$

式(3)表明当图像的像素集合 $I _ { \mathbf { \Phi } _ { i } }$ 的势 $\left| I _ { i } \right|$ 越大，图像的相似度越大。式(5）中， $N _ { i } ( d )$ 表示以i为像素点处理中心的像素点集合，处理的窗口大小为 $d \times d$ ， ${ N } _ { i } ^ { 0 }$ 为像素点集合 $N _ { i } ( d )$ 中不包含中心点i的像素点集合； $\mathbf { h }$ 为权值因子； $\nu ( N _ { i } ^ { 0 } )$ 表示素点值构成的向量，向量 $\nu ( N _ { i } ^ { 0 } )$ 和向量 $\nu ( N _ { j } ^ { 0 } )$ 的加权范数课由下式来表示：

$$
\left\| \nu ( N _ { i } ^ { 0 } ) - \nu ( N _ { j } ^ { 0 } ) \right\| _ { 2 , a } ^ { 2 } = \sum _ { k \in N _ { i } } a ( i , k ) \left| \nu ( k ) - \nu ( T k ) \right| ^ { 2 }
$$

其中：图像中像素点之间的平移变换为 $\mathrm { ~ T ~ }$ ，即 $N _ { j } = T N _ { i }$ ；当$a ( i , k ) > 0$ 为权重参数，一般可以用欧式范数来表示。

# 1.2.2图像光学相似度函数

图像在获取过程中，外界光源的光照环境会直接影响图像的质量，尤其在太空探索或航空拍摄过程中，光照条件非常有限，对获取的图像质量产生更加明显影响；此外，大量研究表明，图像的像素值在[0,255]内呈Gaussian分布，在相邻像素点集合中，图像的像素值在局部区域内同样呈Gaussian分布，由此得知，二维图像在局部区域内均呈现Gaussian分布分布，具有一定的相似性，这为后续图像的相似性数学建模过程提供了一定的依据。同时，相似性是人类从认识外界事物特点、感知其特性与识别事物的关键特征过程中总结出的一种经验度量，是对事物的进一步判别与推理的基础[16]。因此，根据二维图像的相似性，结合图像与光照环境的密切相关性[17]，本文提建立了图像光学相似度函数（photometric similarity function，PSF），

其定义如下：

$$
P S F I = \frac { 1 } { w _ { i , j } } \sum _ { m = - q } ^ { q } \sum _ { l = - q } ^ { q } \exp ( - \frac { ( I ( i , j ) - I ( i - m , j - l ) ) ^ { 2 } } { 2 \sigma _ { p } ^ { 2 } } ) \exp ( - \frac { m ^ { 2 } + l ^ { 2 } } { 2 \sigma _ { g } ^ { 2 } } ) I ( i - m , j - l )
$$

式（7）中参数 $w _ { i , j }$ 的取值如下：

$$
w _ { i , j } = \sum _ { m = - q } ^ { q } ~ \sum _ { l = - q } ^ { q } \exp ( - \frac { ( I ( i , j ) - I ( i - m , j - l ) ) ^ { 2 } } { 2 \sigma _ { p } ^ { 2 } } ) \exp ( - \frac { m ^ { 2 } + l ^ { 2 } } { 2 \sigma _ { g } ^ { 2 } } )
$$

其中： $I ( i , j )$ 表示图像中的像素值，其局部区域窗口大小为$( 2 \mathrm { m } + 1 ) { \times } ( 2 \mathrm { n } + 1 )$ ： $\sigma _ { p }$ 和 $\sigma _ { g }$ 分别为局部和全局相似因子，即可以根据图像相似性自适应的平滑图像并保护图像细节信息。

# 1.3图像去雾模型

# 1.3.1大气散射与雾天成像模型

光在大气中传输作用于物体上，物体反射其光线成像，如图1（b）所示。在天气晴朗的环境中，物体的反射光线在成像过程中基本不会受到大气分子的影响，然而，在雾天环境中，由于光线在传播过程中受到大气中气溶胶粒子的影响，主要包括吸收、辐射和散射三种不同程度的影响，吸收和辐射的影响效果较小，而散射对物体的成像影响较大，因此，散射也被列为是导致光学图像降质的主要原因。本文主要考虑大气的散射作用，该作用可以用下式(9)-(11)所示的大气散射数学模型来描述：

$$
E ( d , \lambda ) = E _ { d t } ( d , t ) + E _ { a } ( d , \lambda )
$$

$$
E _ { a } ( d , \lambda ) = E _ { \infty } ( \lambda ) ( 1 - e ^ { - \beta ( \lambda ) d } )
$$

$$
E _ { d t } ( d , t ) = E _ { 0 } ( \lambda ) e ^ { - \beta ( \lambda ) d }
$$

其中：d 是实际场景中被测目标与观测者的距离， $E _ { 0 } ( \lambda )$ 是被测目标表面零距离处未衰减的反射光， $E _ { \infty } ( \lambda )$ 是地平线无穷远处的大气光， $\beta$ 为散射系数，与入射光线波长 $\lambda$ 的关系如下：

$$
\beta ( \lambda ) \propto { \frac { 1 } { \lambda ^ { \gamma } } } , \qquad 0 \leq \gamma \leq 4
$$

雾天成像模型文献[18]表明，在有雾天环境中获取的图像会不同程度受到大气影响，大气中的微粒半径通常大于可见光波长，即 $\gamma \approx 0$ ，大气光的散射系数对可见波波长没有明显影响，可近似为常数，式（9）～（11）可简化为雾天图像成像的物理模型：

$$
I ( x ) = J ( x ) t ( x ) + A ( 1 - t ( x ) )
$$

其中： $I ( x )$ 为有雾图像， $x$ 表示图像点坐标， $J ( x )$ 为场景无衰减反射光的图像，A为大气光成分， $t ( x )$ 为介质传递函数，反映大气光线通过传输介质传递的能力，即透射率。

# 1.3.2基于视觉颜色感知一光学相似的图像去雾模型

文献[9]中何凯明等人根据原始无雾图像的统计特征，提出了暗通道原理，指出绝大多数的无雾图像的某些局部区域内广泛存在着暗原色点，结合人眼视觉颜色感知计算模型式（1），

有如下公式：

$$
J _ { \mathbf { \Phi } _ { c } } ^ { \mathbf { \Phi } _ { d a r k } } ( \boldsymbol { x } ) = \operatorname* { m i n } _ { \substack { c \in \{ R , G , B \} } } [ \operatorname* { m i n } ( \mathbf { \Phi } _ { \boldsymbol { y } \in \Omega ( \boldsymbol { x } ) } ( \boldsymbol { y } ) ) ]
$$

其中： ${ J } _ { c } ^ { d a r k }$ 为原始图像 $J$ 中 $\mathrm { ~ R ~ }$ 、G和 $\mathbf { B }$ 三个颜色通道的某一个颜色通道的暗原色， $F _ { c }$ 表示原始图像 $J$ 的3个颜色通道中任意一个人眼视觉感知的颜色通道， $\varOmega ( x )$ 表示以像素点 $x$ 为中心的局部区域的一个滑动窗口， $y$ 位置坐标， $\mathbf { \Psi } _ { c }$ 为颜色通道。根据文献[9]中提出的暗通道先验理论，则有

$$
{ J _ { c } } ^ { d a r k } \to 0
$$

根据上述内容，构建基于视觉颜色感知-光学相似的图像去雾模型如下：

$$
\begin{array} { r l } & { P S F I _ { c } ^ { d a r k } ( i , j ) = } \\ & { \frac { \displaystyle \sum _ { m = - q } ^ { q } \sum _ { l = - q } ^ { q } \exp ( - \frac { ( I _ { c } ^ { d a r k } ( i , j ) - I _ { c } ^ { d a r k } ( i - m , j - l ) ) ^ { 2 } } { 2 \sigma _ { p } ^ { 2 } } ) \exp ( - \frac { m ^ { 2 } + l ^ { 2 } } { 2 \sigma _ { g } ^ { 2 } } ) I _ { c } ^ { d a r k } ( i - m , j - l ) } { \displaystyle \sum _ { m = - q } ^ { q } \sum _ { l = - q } ^ { q } \exp ( - \frac { ( I _ { c } ^ { d a r k } ( i , j ) - I _ { c } ^ { d a r k } ( i - m , j - l ) ) ^ { 2 } } { 2 \sigma _ { p } ^ { 2 } } ) \exp ( - \frac { m ^ { 2 } + l ^ { 2 } } { 2 \sigma _ { g } ^ { 2 } } ) } } \end{array}
$$

其中： ${ J } _ { c } ^ { d a r k }$ 表示为有雾图像的人眼视觉感知的颜色暗通道图，局部区域窗口大小为 $( 2 \mathrm { m } + 1 ) \times ( 2 \mathrm { n } + 1 )$ 。

# 1.3.3透射率估计

对雾天图像成像的物理模型式（13）在人眼视觉感知的不同颜色通道进行变换得到：

$$
\frac { I ^ { c } ( x ) } { A ^ { c } } = t ( x ) \frac { J ^ { c } ( x ) } { A ^ { c } } + 1 - t ( x )
$$

在每个颜色通道上的暗原色为

$$
\operatorname* { m i n } _ { c \in \{ R , G , B \} } [ \operatorname* { m i n } [ \frac { I ^ { c } ( x ) } { A ^ { c } } ] ] = \widetilde { t } \left( x \right) \operatorname* { m i n } _ { c \in \{ R , G , B \} } [ \operatorname* { m i n } \frac { J ^ { c } ( x ) } { A ^ { c } } ] ] + 1 - \widetilde { t } \left( x \right) \Theta ( x , x ) ,
$$

根据暗通道先验原理有

$$
J _ { c } ^ { \mathit { d a r k } } ( x ) = \operatorname* { m i n } _ { \mathit { c } \in \{ R , G , B \} } [ ( \left. J _ { c } \right. ( y ) ) ] \approx \mathbf { 0 }
$$

将式（19）代入到式（18）得

$$
\widetilde t \left( x \right) = 1 - \operatorname* { m i n } _ { c } [ \operatorname* { m i n } _ { y \in \Omega \left( x \right) } \frac { I ^ { c } \left( y \right) } { A ^ { c } } ]
$$

结合构建的基于视觉颜色感知一光学相似的图像去雾模型进一步改进式（20），得到改进后的大气透射率的估计计算模型为

$$
t ( x ) = 1 - \zeta \operatorname* { m i n } _ { c } [ \operatorname* { m i n } _ { y \in \Omega ( x ) } \frac { P S F I _ { c } ^ { d a r k } ( y ) } { A ^ { c } } ]
$$

其中： $\zeta$ 为权值系数，用以保留少量的雾，增加图像的真实感。  
本文中取值为 $0 . 9 6$ 。

# 1.3.4大气光估计

文献[9]中何凯明等人对大气光的取值是暗通道图的前$10 \%$ 的最亮的像素，在相对应的原始图像中找到这些像素所对应的三原色通道中的最大值作为大气光值。本文根据这一思路，改进了原有的大气光取值，充分结合人眼视觉颜色感知计算模型，提出新的大气光估计计算模型如下：

$$
A ^ { c } = \left\{ \begin{array} { l l } { m e a n [ { J _ { c } } ^ { d a r k } ( x ) ] , } & { \quad x \in [ 2 0 0 , 2 5 5 ] } \\ { y \in \Omega ( x ) } & { } \\ { \displaystyle \operatorname* { m a x } _ { y \in \Omega ( x ) } [ { J _ { c } } ^ { d a r k } ( x ) ] , } & { \quad \sharp \sharp / \sharp } \end{array} \right.
$$

该模型能够有效地解决去雾以后的图像颜色失真问题。

1.3.5基于视觉颜色感知-光学相似的图像去雾算法本文提出方法的算法如下所示，流程图如图2所示。

算法1基于视觉颜色感知-光学相似的图像去雾方法算法  
输入：有雾图像 $\mathbb { I } ( { \mathsf x } , { \mathsf y } )$ ，其大小为 $\mathsf { M } \times \mathsf { N }$   
输出：去雾图像 $\Im ( { \times } , { y } )$ ，其大小为 $\mathsf { M } \times \mathsf { N }$

步骤：

第1步 选取待复原的含雾图像中（即 $\mathsf { M } \times \mathsf { N }$ 个像素点集合）像素点$\mathbf { \nabla } \times ( \mathrm { i } , \mathrm { j } )$ 。（注： $\mathbf { 1 } \leqslant \mathbf { i } \leqslant \mathsf { M }$ 且 $\theta { \leqslant } { \mathfrak { j } } \leqslant { \mathsf { N } }$ ）  
第2步 初始化相关参数o，σp 和 $\mathfrak { o } \ \mathbf { g }$ ， $\zeta$   
第3步 根据式（19），获得暗通道Jcdark.  
第4步 根据式（21），得到大气透射率传输图  
第5步 根据式（22），得到大气光值A  
第6步 根据式(13），恢复场景中去雾图像J(i,j)

输入图像 设置参数 获取暗通 I(i,j) ${ \sigma } , { \sigma _ { p } } , { \sigma _ { g } }$ 和 $\zeta$ 道图 输出去雾 大气光值 透射率传 图像 $J ( i , j )$ 估计 输图t(x)

# 2 实验结果及分析

# 2.1仿真实验测试平台

针对本文所提出的基于视觉颜色感知-光学相似的图像去雾方法，以Matlab2017b为仿真测试平台完成图像去雾仿真验证，选取6张典型测试图像，参见图3所示。

![](images/21c2b1b39edffa0a5eb86e279913f714d69453d9f6336f9b3065c48ea360af26.jpg)  
图2本文提出方法的流程图  
图3含雾测试图像

# 2.2本文提出方法的实验结果

采用本文提出方法去雾图像效果如图4所示，图中，（a)为含雾图像，（b）为本文提出的方法去雾处理过程中的透射率估计传输图，（c)为本文提出的方法去雾处理以后的清晰图像。从实验结果可以看出，本文提出的基于视觉颜色感知-光学相似的图像去雾方法能够有效的去除含雾图像中的雾，有效的提高图像的质量，并且能够在一定程度上较好的保护图像的细节信息。如图4（a）中远处地上的落叶清晰可见，图4（b）中建筑物的清晰程度与含雾图像相比明显有所提高；图4（c）中远处的山脉及天空更加清楚；图4（d）天安门的清晰化呈现；图4（e）草坪与湖水的深度信息也明显能够展现；以及图4（e）中的植物能够清晰的显示出来。

综上所述，本文提出的基于视觉颜色感知-光学相似的图像去雾方法不仅能够从含雾图像的视觉效果上，而且从图像的细节信息保护方面能够明显的提高含雾图像的质量。

![](images/b22529e329e7b740938a30a339dfcb631ec283acf999a4795f534ba30c239b14.jpg)  
图4本文提出方法图像去雾实验结果

# 2.3 与其他方法的对比

基于视觉颜色感知一光学相似的图像去雾方法与现有的双边滤波一暗通道先验图像去雾方法[9]、软抠图图像去雾方法[10]、传输图未优化方法，以及近年来提出的方法进行比较，如Berman等人[19]于2016年CVPR提出的非局部图像去雾和2017年Fan 等人[20]提出的双层高斯回归图像去雾方法进行去雾效果比较，结果见图5所示，与其他方法相比，本文提出的方法在图像细节的保护、颜色保护和清晰度上具有一定的优势。如图5中第一行图像，森林图像中远处去雾效果，与其他传统的和近来的方法相比，本文提出的方法具有一定的优势；图5中第二行图像天空部分，以及图5中第三行图像湖与边界的接壤部分，本文中提出的方法对图像颜色的保护能力较好。

本文采用基于梯度信息与人类视觉系统（humanvisionsystem,HVS）滤波器的无参考清晰度评价算法(GI_F)[2I进行定量评价本文方法的有效性，如表1所示。

表1其他图像去雾方法与本文提出方法GIF对比结果  

<html><body><table><tr><td rowspan="2">原始 图像</td><td colspan="4">导向滤波和</td><td rowspan="2">软抠图 传输图未 Non- GPR2</td><td rowspan="2">本文 提出方法</td></tr><tr><td>含雾图像</td><td>暗通道先验</td><td>方法</td><td>优化方法Local</td></tr><tr><td>森林</td><td>0.42</td><td>0.62</td><td>0.61</td><td>0.60</td><td>0.63</td><td>0.58</td><td>0.66</td></tr><tr><td>山脉</td><td>0.46</td><td>0.56</td><td>0.56</td><td>0.55</td><td>0.57</td><td>0.50</td><td>0.60</td></tr><tr><td>天鹅</td><td>0.34</td><td>0.45</td><td>0.45</td><td>0.48</td><td>0.51</td><td>0.46</td><td>0.53</td></tr></table></body></html>

# 3 结束语

本文所提出的基于视觉颜色感知一光学相似的图像去雾方法，充分利用人眼感知颜色的视觉机理，结合图像的相似性原理，构造了光学相似度函数，基于图像的暗通道原理，建立基于视觉颜色感知-光学相似的图像去雾模型并设计相关算法，进而进行仿真验证。仿真实验结果表明，本文提出的方法在对有雾图像清晰化处理过程中效果明显，并与现有的图像去雾方法进行比较表明，本文提出的方法清晰化含雾图像处理中取得了较好的效果。本文的下一步研究工作将根据含雾图像的视觉特征，进一步优化所构建去雾模型的参数。

# 参考文献：

[1]乔伟伟，谢从华，刘永俊，等．基于暗通道先验和核回归的图像去雾研 究[J].计算机应用研究，2017,34(4):1277-1280.(Qiao Weiwei,Xie Conghua,Liu Yongjun,et al.Research of image dehazing based on darkness-channel prior knowledge and kernel regression [J].Application Research ofComputers,2017,34(4):1277-1280.)   
[2]陈俊君，徐冰．雾霾天气条件下的机器视觉图像清晰化研究[J].计算 机工程，2017,43(2):280-285.(Chen Junjun,Xu Bing.Research on machine vision image clearness under fog and haze weather conditions [J]. Computer Engineering,2017,43(2): 280-285.)   
[3]Kim JY, Kim L S,Hwang S H.An advanced contrast enhancement using partially overlapped sub-block histogram equalization [J].IEEE Trans on Circuits& Systems for Video Technology,2001,11(4): 475-484.   
[4]艾明晶，戴隆忠，曹庆华.雾天环境下自适应图像增强去雾方法研究 [J].计算机仿真,2009,26(7): 244-247.(Ai mingjing,Dai longzhong,Cao qinghua.A self-adaptation image enhancement method for fog elimination in foggy environment [J].Computer Simulation,2009,26(7): 244-247)   
[5] 张赛楠，吴亚东，张红英，等.改进的单尺度Retinex 雾天图像增强算 法[J].激光与红外,2013,43(6):698-702.(Zhang Sainan,Wu Yadong, Zhang Hongying,et al.Haze image enhancement method based on improved single-scale Retinex [J].Laser and Infrared,2013,43 (6): 698-702)   
[6]曹永妹，张尤赛．图像去雾的小波域Retinex 算法[J].江苏科技大学学

报：自然科学版，2014,28(1):50-55.(Cao Yongmei,Zhang Yousai.

Wavelet-based retinex algorithm for image defogging [J]. Journal ofJiangsu University of Science and Technology (Natural Science Edition),2014, 28 (1): 50-55. )   
[7]Kopf J,Neubert B,Chen B,et al.Deep photo: model-based photograph enhancement and viewing [J].ACMTrans on Graphics,2008,27(5): 1-10.   
[8]Naragimhan S G,Nayar S K. Interactive (de) weathering of an image using physical models [C]//Proc of IEEE Workshop on Color and Photometric Methods in Computer Vision. 2003.   
[9]He Kaiming, Sun Jian,Tang Xiaoou. Single image haze removal using dark channel prior [C]/ Proc of IEEE Conference on Computer Vision and Pattern Recognition. 2009:1956-1963.   
[10] He Kaiming,Sun Jian,Tang Xiaoou. Guided image filtering[J]. IEEE Trans on Pattern Analysis& Machine Intelligence,2013,35(6):1397-1409.   
[11] Akers A,Barton J,CosseyR,etal. Visualcolorperceptioningreenexercise: Positive effects on mood and perceived exertion [J].Environmental science & technology,2012,46 (16): 8661-8666.   
[12] Thorpe S,Fize D,Marlot C.Speed of processingin the human visual system [J]. Nature,1996,381(6582): 520.   
[13] Eickenberg M, Gramfort A, Varoquaux G,et al.Seeingital: convoltional network layersmap the function of the human visual system [J]. NeuroImage,2017,152: 184-194.   
[14]Dartnall HJ,BowmakerJK,Mollon JD.Human visual pigments: microspectrophotometric results from the eyes of seven persons [J]. Proceedings of the Royal Society ofLondon B: Biological Sciences,1983, 220 (1218): 115-130.   
[15]赵雪青．降质图像复原方法研究[D].陕西：陕西师范大学,2013.   
[16]李兵，刘全升，徐家伟，等．去除混合噪声的一种新方法[J].中国科 学：信息科学,2010,40(9):165-1175.(LiBin,Liu Quansheng,XuJiawei, et al. A new way to remove mixed noise [J]. Science China Information Sciences,2010,40 (9): 1165-1175. )   
[17] Ji Zexuan,Xia Yong,Sun Quansen,et al.Local Gaussian distribution fitting based FCMalgorithm for brain MR image segmentation [J]. Intelligent Science and Intelligent Data Engineering,2012,7202: 318-325.   
[18] Srinivasa G. Narasimhan, Shree K. Nayar. Contrast restoration of weather degraded images[J]. IEEE Trans on Pattern Analysisand Machine Intelligence,2003,25 (6): 713-724.   
[19] Dana Berman,Tali Treibitz,Shai Avidan.Non-local image dehazing [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. Washington DC: IEEE Computer Society,2016: 1674-1682.   
[20]Fan Xin,Wang Yi,Tang Xianxuan,et al. Two-layer Gaussianprocess regression with example selection for image dehazing[J]. IEEE Trans on Circuits & Systems forVideo Technology,2017,27(12): 2505-257.   
[21]应凌楷，李子印，张聪聪．融合梯度信息与HVS 滤波器的无参考清晰 度评价[J].中国图象图形学报,2015,20(11):1446-1452.(YingLingkai, Li Ziyin, Zhang Congcong. No-reference sharpness assssment with fusion

if gradient information and HVS filter [J].Journal of Image and Graphics

2015,20 (11): 1446-1452)