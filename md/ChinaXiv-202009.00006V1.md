# 基于系列斑点图像的视宁度估算精度方法研究

胡钢¹²，向永源¹，刘忠¹²，王新华1,2(1.中国科学院云南天文台 云南 昆明 650011；2.中国科学院大学 北京 100049)

摘要：半高宽法和像运动法是估算大气视宁度的常用方法。这两种方法的估算精度都会受到望远镜跟踪误差，风或机械振动等因素的影响。提高视宁度估算精度在高分辨成像、选址、台站视宁度监测等领域有重要意义。对于半高宽法，用二维高斯函数拟合长曝光点源单星星像并选取合适方向的半高宽估算视宁度，与谱比法对照发现可以有效改善跟踪误差，风或机械振动等因素的影响。对于像运动法，用主成分分析方法找到一系列斑点图重心位置在合适方向上投影的方差，以此估算视宁度，与谱比法对照发现可以有效改善跟踪误差，风或机械振动等因素的影响。

关键词：视宁度；半高宽；像运动法；跟踪误差中图分类号：P11 文献标识码：A

# 1引言

大气湍流是降低地面大型光学望远镜成像质量的主要因素之一，它会使图像在像面发生随机的抖动，畸变和破碎。为描述大气湍流对成像过程的影响，基于Komolgorov 关于大气湍流的统计模型，D.L.Fried[1]引入了视宁度参数 $r _ { O }$ ，又被称为Fried参数，或者大气相干长度。根据定义， $r _ { 0 }$ 表征着地面望远镜实现衍射极限成像的极限口径[2，也代表着大气湍流的剧烈程度。 $r _ { O }$ 值在选址和高分辨成像等领域有极高的重要性，比如斑点干涉术[的理论传递函数模型与 $r _ { 0 }$ 值有关[4]，自适应光学中 Shack-Hartmann 波前传感器微透镜阵列的数量由 $r _ { O }$ 所决定[5]。

估算视宁度 $r _ { O }$ 有许多种方法。有些需要使用专门的仪器，比如，利用北极星星轨的横向抖动方差估算视宁度[6-8]，利用探空气球或者声雷达测量不同高度大气的温度结构常数从而推导出大气视宁度[9-10]，利用刀口前后焦面光强变化程度从而推导出视宁度[11]，利用干涉仪中被大气干扰的星像的干涉条纹来推导出视宁度，利用望远镜上两个间距超过 $r _ { O }$ 的子孔径的差分到达角方差来推算视宁度[12]，利用星像闪烁的程度来推算视宁度[13-14]等等。

有些则可以利用望远镜观测过程中的斑点图[3][5][15](曝光时间在大气相干时间量级的短曝光图像)估算，比如，将一组点源星像的实际平均长曝光或者平均短曝光传递函数[与对应的理论传递函数相比较从而推导出视宁度[16],通过将一组图像的实际谱比值与理论值相比较来得到视宁度[17] (在扩展源图像的高分辨重建领域应用广泛，本文称为谱比法)，利用大气湍流对图像对比度造成的变化从而反推出视宁度[8]，直接利点源目标长曝光星像的半高宽(FWHM)估算视宁度[12][1]，利用星像在像面抖动的方差来估算视宁度[20]（本文称为像运动法(ImageMotion)）等等。

在诸多方法中，FWHM法和像运动法可以较为方便快捷的估算出视宁度参数，是应用十分广泛的方法。当望远镜受到跟踪误差，风或者机械振动等因素(以下统称为综合因素)的影响时，这两种方法往往会受到影响，从而降低视宁度的估算精度。

本文将介绍FWHM法估算视宁度的基本原理，分析其应用条件，及综合因素将产生何种影响，并给出应对方法。介绍像运动法的基本原理，跟踪误差等因素的影响及给出应对方法。随后将应对方法应用到实际数据中去，并分析取得的结果，将结果与用谱比法对照，以说明应对方法的有效性。

# 2方法

在等晕区内，大气-望远镜综合系统可以看做一个线性空不变系统，短曝光成像过程在空域和频域可分别用(1)式和(2)式表示表示：

$$
i ( x ) = o ( x ) * s ( x )
$$

$$
I ( q ) = O ( q ) S ( q )
$$

式中， $i ( x )$ 表示短曝光图像， $I ( q )$ 是其对应的频域表示， $o ( x )$ 表示目标， $O ( q )$ 表示其傅里叶变换， $s ( x )$ 表示点扩散函数，对于点源目标来说 $i ( x ) { = } s ( x )$ ， $S ( q )$ 表示短曝光大气-望远镜综合系统的传递函数， $q$ 表示归一化空间频率，\*表示卷积。

短曝光大气-望远镜综合系统的传递函数又可以分解为望远镜的传递函数与短曝光大气的传递函数之积：

$$
S ( q ) = T ( q ) B ( q )
$$

# 2.1半高宽(FWHM)法

半高宽法的本质是利用点源单星长曝光图像的半高宽与视宁度参数之间的简单关系：

$$
F W H M = 0 . 9 8 \frac { \lambda } { r _ { 0 } }
$$

其中λ表示波长。长曝光图像可以通过多张短曝光图像的统计平均来获得[21]。因为长曝光星像的强度分布近似于高斯函数[15]，常常使用高斯函数拟合以计算半高宽[8][2],高斯函数的半高宽与标准差存在一简单关系：

$$
F W H M = 2 \sqrt { 2 \ln { 2 } } \sigma
$$

分析长曝光大气-望远镜综合系统的分辨率与大气的分辨率的比值随 $D / r _ { O }$ 的变化情况，分辨率定义为在频率域对 MTF 积分[[2][2]。发现当望远镜口径 $D$ 远大于视宁度 $r _ { O }$ 时，系统分辨率越来越接近大气的分辨率，因此，当 $D \gg r _ { 0 }$ 时，可以将长曝光综合系统的传递函数与长曝光大气的传递函数划等号。

$$
\left. S ( q ) \right. _ { L E } \approx \left. B ( q ) \right. _ { L E } = \exp ( - 3 . 4 4 \biggl ( \frac { q } { \alpha } \biggr ) ^ { \frac { 5 } { 3 } } )
$$

()表示系综平均， $\scriptstyle { a = r _ { \theta } } ( D$ ， $L E$ 表示长曝光。

为了获取空域长曝光点扩散函数 $\langle s ( x ) \rangle _ { L E }$ 的半高宽，需将(6)式做反傅里叶变换，再取其半高宽，但是， $5 / 3$ 次方使我们难以得到解析解，一种近似方法是用2次来替代5/3次以用高斯函数来近似传递函数，如此即可得到半高宽的解析式(4)。

根据上述分析，公式(4)的推导过程实际上做了两处近似，1.用大气的传递函数代替系统的传递函数，2.用2次方替代5/3次方。为了说明两处近似在何种程度上影响着(4)式的准确度，使用数值方法计算出理论上系统长曝光点扩散函数的半高宽然后将其与(4)式的半高宽做比较。其结果如图1所示。

![](images/34b67751dc5c6068d9a881b650ad47e78c19dd0216d164d7dd7291bfd5006a6f.jpg)  
图1 (4)式半高宽与综合系统的半高宽的比值随 $D / r _ { 0 }$ 的变化情况

Fig.1RatioofFWHMcalculatedby equation (4)and theoretical FWHMof the synthetic systemasafunctionof $D / r _ { 0 }$

图1说明，当 $D \gg r _ { 0 }$ 时， (4)式才能达到较高的准确度，比如当 $D = I m$ ， $r _ { O } = I O c m$ 时，半高宽比值可以达到0.93。说明对于口径 $\boldsymbol { l m }$ 级别的望远镜， (4)式在理论上已经能够达到较高的准确度，因此本文使用(4)式估算 $r _ { 0 } \text{ textperthousand}$

上述分析是基于假设望远镜是理想望远镜的情况，即无像差，无跟踪误差，无风载荷影响，支撑系统完全刚性等。实际上，这些因素都会使得实际拍摄的长曝光点源星像偏大，从而使得公式(4)估算的 $r _ { O }$ 值偏小。

当受到综合因素影响时，长曝光图像往往会在某个方向上延展开来，强度分布表现出类椭圆形，选择合适的方向来计算半高宽变得尤为重要。应对方法是使用二维高斯函数拟合受到综合因素影响的长曝光点源单星图像，将方差最大的方向视为受到影响较大的方向。用于拟合的二维高斯函数如下所示：

$$
f ( x 1 , x 2 ) = A \exp ( - \frac { 1 } { 2 ( 1 - \rho ^ { 2 } ) } ( ( \frac { x _ { 1 } - \mu _ { 1 } } { \sigma _ { 1 } } ) ^ { 2 } + ( \frac { x _ { 2 } - \mu _ { 2 } } { \sigma _ { 2 } } ) ^ { 2 } - 2 \rho ( \frac { x _ { 1 } - \mu _ { 1 } } { \sigma _ { 1 } } ) ( \frac { x _ { 2 } - \mu _ { 2 } } { \sigma _ { 2 } } ) ) )
$$

对应的协方差矩阵为：

$$
\left[ \begin{array} { c c } { \sigma _ { 1 } ^ { 2 } } & { \rho \sigma _ { 1 } \sigma _ { 2 } } \\ { \rho \sigma _ { 1 } \sigma _ { 2 } } & { \sigma _ { 2 } ^ { 2 } } \end{array} \right]
$$

绝大多数情况下，相关系数 $\rho$ 不为零，协方差矩阵不是对角矩阵，需将协方差矩阵化为对角矩阵以找到受到影响较大的方向，再取与之垂直方向上的方差，即对角矩阵中较小的方差，以此来计算半高宽，进而使用公式(4)估算 $r _ { O }$ ，如图2所示。

![](images/c9f33e619b2f2b1213c0f528d4c162a158e4e1a2db39396b245b0de3e5dd4284.jpg)

图2 左图是一张受到综合因素影响的点源单星的长曝光图像，右图是拟合长曝光图像的二维高斯函数图像

Fig.2Alongexposureimageaectedbytrackingeor,windorechanicalibratio(Left),Atwodimensionalgaussanfuction

# 2.2像运动法 (ImageMotion)

大气湍流对成像过程的一种影响就是改变瞳面的波前到达角，造成像面图像的随机抖动，因此测量图像抖动的剧烈程度就可以间接地推导出视宁度参数 $r _ { 0 }$ 。D.L.Fried[20]揭示了 $r _ { 0 }$ 与波前到达角方差之间的关系：

$$
\sigma _ { m } ^ { 2 } = 0 . 3 5 8 ( \frac { \lambda } { r _ { 0 } } ) ^ { \frac { 5 } { 3 } } ( \frac { \lambda } { D } ) ^ { \frac { 1 } { 3 } }
$$

其中 $D$ 表示光学系统的有效口径， $\sigma _ { m }$ 表示波前到达角标准差。

对于点源单星图像，重心的位置变化就对应着瞳面的波前到达角起伏[24]。因此可以根据计算像面图像重心的抖动方差推算出视宁度参数 $r _ { O }$ 。其中，重心的计算方法如下[25]：

$$
X = { \frac { \sum x \cdot I ( x , y ) } { \sum I ( x , y ) } } \quad Y = { \frac { \sum y \cdot I ( \ x \ y ) } { \sum I ( \ x , \ y ) } }
$$

其中 $^ { \phantom { \dagger } } x , y$ 表示某像素坐标位置， $I ( x , y )$ 表示 $( x , y )$ 坐标处的像素值， $X$ 与 $Y$ 表示重心坐标位置。

像运动法会受到综合因素的影响。假设仅存在大气湍流影响时图像重心位置为 $X _ { A }$ ，综合因素造成的偏移量为 $X _ { V }$ ，且 $X _ { A }$ 与 $X _ { V }$ 相互独立，则实际重心位置为 $\scriptstyle { X = X _ { A } + X _ { V } }$ ，易得出实际重心位置的方差 $D X { = } D X _ { A } { + } D X _ { V } ,$ 则 $D X \geqslant D X _ { A }$ 。因此，一般来说，综合因素会造成图像抖动方差增大，从而使得估算的 $r _ { O }$ 值偏小。

每张图的曝光时间长度也会影响到像运动法[26-28]，理想情况下，曝光时长小于或等于大气相干时间，不同斑点图对应着不同状态的“冻结”的大气，图像重心位置也不一样。当每张图的曝光时长增加时，重心位置会被平滑掉，从而降低重心位置抖动的方差，造成估算的$r _ { 0 }$ 值偏大。

需要指出的是，望远镜口径大小也会对像运动法造成影响。H.M.Martin[26认为像运动实际上是由大于口径的湍流元胞造成的，小尺度的湍流尽管会造成图像的斑点结构，但是口径内众多的小尺度湍流会平滑掉重心位置，造成重心位置偏移不明显。G.Ricort[8使用 40cm口径的望远镜估算视宁度，结果显示像运动法估算的视宁度是对比度法的1.4 倍。P.R.GOODE[29]使用 $6 5 \mathrm { c m }$ 口径的望远镜估算视宁度，结果显示像运动法的结果是谱比法的1.5倍。Bin $\mathbf { M } \mathbf { a } ^ { [ 8 ] }$ 使用 $5 0 \mathrm { c m }$ 口径的望远镜对比了星轨法(本质上是像运动法)与DIMM，发现星轨法的结果偏大。这些研究表明，大口径的望远镜使用像运动法估算视宁度，会导致结果偏大。

公式(9)是根据 kolmogorov 谱推导的，并没有考虑大气湍流外尺度的影响，实际上，VonKarman谱的数值模拟表明，当考虑有限外尺度时，重心的抖动方差会偏小，导致估算的视宁度偏大。

当图像信噪比较低时，CCD读出噪声会影响图像重心位置的计算，造成像运动法视宁度的不准确估算，通常的应对方法有：1.门限值法，对图像设置门限值（一般使用图像最大值乘以某个小于1的系数来表示)，仅仅使用门限值以上的像素值计算重心，2.加窗法，设置一个窗口范围，仅仅使用窗口内部的像素值计算重心。如果对一组图像直接使用门限值法估算视宁度，可以发现门限值的大小会严重影响到估算结果。如图3所示：

![](images/24a1328a7eb84e9bdda63f4091d0188c8c2ca9c95bdd9f84af93b8eea7851078.jpg)  
图3门限值大小对视宁度估算的影响  
Fig .3 Influence of threshold on seeing estimation

J.Vernin[30等人分析了CCD 噪声对重心位置影响，发现重心位置抖动方差与窗口大小呈四次方关系，是严重影响因素，设置门限值在某种意义上就是限制了窗口大小，加窗法则是直接就将窗口限制为某个较小的范围。

本文将加窗法与门限值法相结合，首先以图像最大值为中心，以 $\mathrm { w _ { D } }$ 为直径加窗， $\mathbf { W } _ { \mathrm { D } }$ 定义为使用高斯函数近似点扩散函数之后，强度值下降为最大值的 $1 / \mathrm { e }$ 时的直径，类似于衍射受限点扩散函数的rms 宽度的定义[31]。理论上， $\mathrm { W _ { D } } { \approx } 1 . 2 \mathrm { F W H M _ { p s f } }$ 。随后，考虑到SandrineThomas[32]与Chao Li[33]等人模拟分析发现以3倍的读出噪声作为门限值可以有效地降低读出噪声的影响，本文也以3倍的读出噪声作为门限值计算重心位置，读出噪声可以从一系列暗场图像中分析获得。

当受到综合因素的影响时，一系列点源单星斑点图的重心位置往往会在某个方向延展开来，使得这个方向上的抖动方差要大于其他方向。应对策略是使用主成分分析方法(PCA)找到一组重心坐标数据中方差最大的方向，即第一主成分方向，将此方向看做受到影响较大的方向。将坐标数据降维在第二主成分方向上(与第一主成分正交的方向)，并计算其方差，然后利用该方差来估算 $r _ { 0 }$ 值。在图4的情况下，就是取 $y$ 方向上的方差来估算 $r _ { 0 }$ 。

主成分分析方法是一种应用广泛的数据降维手段，在天文数据处理领域也有应用[34]，一般是将数据降维到前 $n$ 阶方差最大的方向上以保留原始数据的主要信息特征，本文的用法则是将二维的重心位置坐标数据降维到方差小的方向上。具体的算法实现如下：

(1）将所有重心坐标组成矩阵

$$
X = ( \begin{array} { l l l l } { x _ { 1 } } & { x _ { 2 } } & { \dots } & { x _ { N } } \\ { y _ { 1 } } & { y _ { 2 } } & { \dots } & { y _ { N } } \end{array} )
$$

(2)将 $X$ 每一行进行零均值化

$$
X _ { _ { n e w } } = X - \overline { { X } }
$$

(3）计算出协方差矩阵

$$
\boldsymbol { C } = \frac { 1 } { N } \boldsymbol { X } _ { n e w } \boldsymbol { X } _ { n e w } ^ { T }
$$

(4）将协方差矩阵 $c$ 对角化为 $C$ 中

(5) $C$ 中对角线的元素即为第一主成分和第二主成分方向的方差，值小的方差即为所需要的方差

![](images/9f10814a9aafbae465b6c5db26f817a379ae0eef6dba91f068840570c568aa04.jpg)  
图4一系列斑点图重心坐标位置及第一主成分方向和第二主成分方向

ig.4 Coordinatesofcenterof gravityofaseries of speckle images and directions of thefirstandsecond principle comp

尽管选取了方差小的方向来估算视宁度，但是并非认为此方向完全不受到任何影响，有必要限制一组斑点图的拍摄时间，因为长时间风向等因素可能发生剧烈变化，导致各个方向上都会受到影响。可以用以下方法判断所选择的方向是否也受到了较大的干扰：将重心坐标在第二主成分方向的投影以直方图的形式表示，并使用高斯函数拟合，并考察其决定系数，因为当不存在任何影响时，重心位置的变化应当符合高斯分布，受到影响较小的方向也应该符合高斯分布。实际应用中可以限制决定系数，比如当决定系数大于0.8时才使用本文的方法，否则应当放弃使用该组图像估算。图5为一组斑点图在第二主成分上投影的直方图。

![](images/ef91e53ecb8850fdd044e21edc97940be5aa25ace402d0e3390f2f5d0949c42c.jpg)  
图5在第二主成分方向上投影的重心坐标以及拟合的高斯函数

Fig.5 Coordinates of center of gravity projected on the second PCA direction and fited gaussian function

# 2.3 谱比法

谱比法由O.Von DerLuhe 提出[17]，是通过计算一组图像平均频谱的平方与平均能谱的比值，再将此值与理论值作比较，对于给定的望远镜来说，理论值仅仅是视宁度参数 $r _ { O }$ 的函数。其表达式如下：

$$
R = \frac { \left. I ( \pmb q ) \right. ^ { 2 } } { \left. I ^ { 2 } ( \pmb q ) \right. } = \frac { O ^ { 2 } \left( \pmb q \right) \left. S ( \pmb q ) \right. ^ { 2 } } { O ^ { 2 } ( \pmb q ) \left. S ^ { 2 } ( \pmb q ) \right. } = \frac { \left. S ( \pmb q ) \right. ^ { 2 } } { \left. S ^ { 2 } ( \pmb q ) \right. }
$$

其中， $\langle S ( \pmb q ) \rangle$ 既可指平均长曝光传递函数也可指平均短曝光传递函数，当指平均短曝光传递函数时，意味着将所有图像按照重心对齐再做计算，因此可以不受跟踪误差等因素的影响，表示平均短曝光传递函数时，其理论表达式如下：

$$
\left. S ( \pmb q ) \right. _ { S E } ^ { 2 } = T ^ { 2 } ( \pmb q ) \exp ( - 6 . 8 8 ( \frac { \pmb q } { \alpha } ) ^ { \frac { 5 } { 3 } } ( 1 - \pmb q ^ { \frac { 1 } { 3 } } ) )
$$

平均能谱的理论表达式如下：

$$
\left. S ^ { 2 } ( pmb q ) \right. = \frac { 1 } { N } \int Q ( \pmb y , \pmb q ) S ( \pmb y , \pmb q ) d \pmb y
$$

其中,

$$
Q ( y , q ) = \exp ( - 6 . 8 8 \left\{ \left( q \cdot \alpha \right) ^ { \frac { 5 } { 3 } } + \left( y \cdot \alpha \right) ^ { \frac { 5 } { 3 } } - { \frac { 1 } { 2 } } \Biggl [ \left( \left| y + q \right| \cdot \alpha \right) ^ { \frac { 5 } { 3 } } + \left( \left| y - q \right| \cdot \alpha \right) ^ { \frac { 5 } { 3 } } \Biggr ] \right\} )
$$

$$
S ( { \bf y } , { \bf q } ) = \int W ( { \frac { s + y - 2 \cdot { \bf q } } { 2 } } \cdot D ) W ( { \frac { s + y } { 2 } } \cdot D ) W ( { \frac { s - y - 2 \cdot { \bf q } } { 2 } } \cdot D ) W ( { \frac { s - y } { 2 } } \cdot D ) d s
$$

$$
W ( \pmb { x } ) = \left\{ \begin{array} { l } { 1 \quad \displaystyle \left| \pmb { x } \right| \leq \frac { D } { 2 } } \\ { 0 \quad \displaystyle \left| \pmb { x } \right| > \frac { D } { 2 } } \end{array} \right.
$$

$N$ 为归一化常数， $y$ 与 $\pmb q$ 都是模的范围为0到1的矢量。 $S ( { \bf y } , { \pmb q } )$ 为四个半径为1的圆的交叉面积，很显然，对于给定望远镜， $\langle S ^ { 2 } ( { \pmb q } ) \rangle$ 只与 $\mathbf { \nabla } _ { r _ { 0 } }$ 有关， $\langle S ( { \pmb q } ) \rangle _ { S E } ^ { 2 }$ 也只与 $\mathbf { \nabla } _ { r _ { 0 } }$ 有关，因此 $R$ 的理论比值是 $r _ { O }$ 的函数，任意给定 $r _ { 0 }$ 值就可以计算理论上对应的谱比曲线，将其与实际谱比曲线比较就可以估算出视宁度参数 $r _ { 0 \circ }$

# 3数据处理与分析

# 3.1数据

为验证本文应对综合因素影响的方法的有效性，我们采用二组实测数据进行试验

第一组数据是2014年9月12日晚UT18:48:28到UT19:12:03时间段内，抚仙湖1米新真空太阳望远镜(NVST)所拍摄的25 组数据，每组数据含 200 张斑点图，详细信息如表1所示：

表1实验参数Table1ExperimentParameters  

<html><body><table><tr><td>Parameter</td><td>Value</td></tr><tr><td>Aperture Diameter</td><td>0.98m</td></tr><tr><td>Central Wavelength</td><td>705.8nm</td></tr><tr><td>Pixel Size</td><td>6μm/0.04 arcsec</td></tr><tr><td>Target</td><td>HIP9487</td></tr><tr><td>Region of Interest Size</td><td>192x192 pixels</td></tr><tr><td>Exposure Time</td><td>30ms</td></tr><tr><td>Duration of Observation</td><td>23 min 34 sec</td></tr><tr><td>Number of Groups</td><td>25</td></tr><tr><td>Frames per Group</td><td>200</td></tr><tr><td>Duration per Group</td><td>20 sec</td></tr><tr><td>Zenith Angle</td><td>23°4'59"--25°33' 55"</td></tr></table></body></html>

第二组数据是2009年2月9日晚UT12:49到UT20:46内，使用丽江高美古观测站的2.4米望远镜针对10个目标拍摄的95组图像，每组500帧。详细信息如表2所示。

表2实验参数Table2ExperimentParameters  

<html><body><table><tr><td>Parameter</td><td>Value</td></tr><tr><td>Aperture Diameter</td><td>2.4m</td></tr><tr><td>Central Wavelength</td><td>550nm</td></tr><tr><td>Pixel Size</td><td>0.021 arcsec</td></tr><tr><td>Target</td><td>HIP30960,HIP25245,HIP32993,HIP43635,HIP48670,</td></tr><tr><td></td><td>HIP53360,HIP64543,HR4300,HR4335,HR4518</td></tr><tr><td>Region of Interest Size</td><td>256x256 pixels</td></tr><tr><td>Exposure Time</td><td>8ms</td></tr><tr><td>Duration of Observation</td><td>7hours57minutes</td></tr><tr><td>Number of Groups</td><td>95</td></tr><tr><td>Frames per Group</td><td>500</td></tr><tr><td>Duration per Group</td><td><10 sec</td></tr><tr><td>Zenith Angle</td><td>8°16′12″--21°4'3"</td></tr></table></body></html>

对所有图像按照文献[35]中的方法进行预处理。

对于 NVST 的每一组数据，以任意一张图(本文选取第一张图)的最大值为中心，将图像裁剪成192x192 像素的小子图，目的是为了避免非等晕效应的影响和加快处理速度。

对于高美古2.4m望远镜的数据，因为图像数据已经是以5.376x5.376角秒的小子图读出的，因此不用再做裁切处理了。

图6是经过预处理所得到的斑点图。

![](images/00c0a1820db70476cef62b6cc15a26830f335f059828685e5a303231162b9ca5.jpg)  
图6左边为校准完成的NVST拍摄的斑点图，右边为校准完成的2.4m望远镜拍摄的斑点图  
Fig.6aframe of calibrated speckle image takenbyNVST(Left),a frame of calibrated speckle image taken by $2 . 4 \mathrm { m }$ tele

scope(Right)

# 3.2处理与分析

对所获数据采用以上三种方法进行处理。详细处理流程如图7所示。对半高宽法，预处理完成后，直接将所有斑点图叠加，等效为单张长曝光图像，再对该图像使用二维高斯函数拟合，并使用上述方法找到合适方向的半高宽从而估算视宁度。对像运动法，预处理完成后，计算所有图像重心坐标，并使用第二节所述方法将重心坐标投影在第二主成分上，以直方图表示该方向上重心坐标，计算决定系数，如果决定系数 $\boldsymbol { R } ^ { 2 }$ 大于0.8，就使用该方向上方差估算视宁度，否则就不使用这组图像，这个条件也应用于半高宽法。对于谱比法，预处理完成后，将所有点源单星图像按照重心对齐，随后以对齐后的图像计算平均短曝光频谱与平均能谱，得到实际谱比值，与理论谱比值比较，找到最为接近的视宁度参数值。

为了方便比较，将所估算的 $r _ { O }$ 全部归算到天顶距为 $0 ^ { \circ }$ ，且波长为 $5 0 0 \mathrm { n m }$ 时的值。归算所依据的公式如下：

$$
r _ { 0 } = 0 . 1 8 5 ( \frac { \lambda ^ { 2 } \cos \gamma } { \displaystyle \int C _ { N } ^ { 2 } ( h ) d h } ) ^ { \frac { 3 } { 5 } }
$$

其中， $\lambda$ 为波长， $\gamma$ 为天顶距， $C _ { N } ^ { 2 }$ 为折射率结构常数。

![](images/6c83bd7b06d0396e1d67f274aa671d6f5f17692604cdf59b5c9d7598187774be.jpg)  
图7三种方法的流程图  
Fig.7Flowchart of three methods

作为对比，同时使用以上应对综合因素的修正方法和选取任一方向的方差来估算视宁度(本文选取纵向的方差)。对于NVST 的数据，使用纵向方差估算的视宁度如图8所示。使用修正方法估算的视宁度如图9所示。对于高美古2.4m望远镜的数据，使用纵向方差估算的视宁度如图10所示。使用修正方法估算的视宁度如图11所示。

![](images/25d13521fee131e40c2dc5fd188570e59f08b7062fee7d4d6975317b8dc1d63f.jpg)  
图8 NVST数据：点划线是在FWHM法中使用纵向半高宽估算的视宁度，虚线是在像运动法中使用纵向方差估算的视宁度，实线是使用谱比法估算的视宁度

Fig.8NVSTdata:Dash-dotedineshowsseingparameterestimatedbyusinglongitudinalFWHMintheFWHMmethod,dotted lineshowsseingparameterestimatedbyemployinglongitudinalvarianceintheImage Motion method,solidlinshowsseingparame ter estimated by spectral ratio technic.

![](images/89b9b79dace29e6f3639b21c1c2814c3b6e7f198334fe2d1d7fb1d7294ef7376.jpg)  
图9 NVST数据：点划线是使用修正的FWHM法估算的视宁度，虚线是使用修正的像运动法估算的视宁度，实线是使用谱比法估算的视宁度

Fig.9NVSTdata:Dash-dottdlineshowsseeingparameterestimatedusingcorrectedFWHMmethod,dotted lineshowsseing parameterestimatedbycorrctedImageMotionmethod,solidlinesowsseeingparameterestimatedbyspectralratiotechnic

![](images/8d79d88a8d9d3e8f4fc59450974c57a9f40a7b89f116715894758372d225adad.jpg)  
图 $1 0 2 . 4 \mathrm { { m } }$ 望远镜数据：点划线是在FWHM法中使用纵向半高宽估算的视宁度，虚线是在像运动法中使用纵向方差估算的视宁度，实线是使用谱比法估算的视宁度

Fig telescope data: Dash-doted line shows seing parameter estimated by using longitudinal FWHM in the FWHM method,dotedinesowssengprameterstiatedbymploynglogiudalanceinteIageotioetod,solidlieows seeing parameter estimated by spectral ratio technic.

![](images/dd21da6e5294dd1bb5c0e49bf1fe7d4280afd85892b96a64b9fb8ce416a153a9.jpg)  
图 $1 1 2 . 4 \mathrm { m }$ 望远镜数据：点划线是使用修正的FWHM法估算的视宁度，虚线是使用修正的像运动法估算的视宁度，实线是使用谱比法估算的视宁度  
Fig.11 $2 . 4 \mathrm { m }$ telescope data: Dash-dotted line shows seeing parameter estimated using correctedFWHM method,dotted line shows eing parameterestimatedbycorrected ImageMotiomethod,solidinesowsseingparameterestimatedbyspectralratiotechnic

图9 显示,对于NVST的数据,在观测时间段内，使用FWHM法得到的 $r _ { O }$ 均值为 $9 . 9 6 \mathrm { c m }$ 标准差为 $0 . 7 3 \mathrm { c m }$ ，像运动法得到的 $r _ { O }$ 均值为 $1 7 . 4 4 \mathrm { c m }$ ，标准差为 $2 . 1 2 \mathrm { c m }$ ，谱比法得到的$r _ { 0 }$ 均值为 $1 1 . 0 4 \mathrm { c m }$ ，标准差为 $0 . 6 2 \mathrm { c m }$ 。图11显示，对于高美古 $2 . 4 \mathrm { { m } }$ 望远镜的数据，使用FWHM法得到的 $_ { \mathrm { r 0 } }$ 均值为 $7 . 1 3 \mathrm { c m }$ ，标准差为 $0 . 8 2 \mathrm { c m }$ ，像运动法得到的 $_ { \mathrm { r 0 } }$ 均值为 $1 3 . 4 8 \mathrm { c m }$ 标准差为 $2 \mathrm { c m }$ ，谱比法得到的 $_ { \mathrm { r 0 } }$ 均值为 $7 . 8 8 \mathrm { c m }$ ，标准差为 $0 . 9 7 \mathrm { c m }$ 。

从以上四幅图可以得到以下信息：

第一，FWHM 法得到的视宁度比谱比法偏小，可能的原因有1.(4)式的推导过程本身就说明，估算的r0值会稍微偏小，2.望远镜像差，残余的跟踪误差，风或机械振动因素仍然使得半高宽偏大，从而使估算出的 $\mathrm { { r 0 } }$ 值更偏小。

第二，像运动法估算的视宁度比谱比法偏大，可能的原因有1.曝光时间过长，导致实际测量的像运动方差偏小，造成估算的视宁度偏大，2.望远镜口径过大，像运动更多的反应的是大于口径的湍流元胞的起伏，3.没有考虑有限外尺度的影响4.CCD噪声和光子噪声对重心抖动方差计算的影响仍然存在。

第三，纵向方差估算的 $\mathrm { r 0 }$ 比修正方法估算的 $_ { \mathrm { r 0 } }$ 偏小，这是因为纵向方差更多的包括了跟踪误差，风或机械振动等因素的影响而偏大，使得估算的 $_ { \mathrm { r 0 } }$ 值偏小

第四，对于nvst的数据，修正的FWHM法估算的视宁度与谱比法之间的相关系数为0.79,而纵向半高宽估算的视宁度与谱比法之间的相关系数为0.39。修正的像运动法与谱比法之间的相关系数为0.52，而纵向方差估算的视宁度与谱比法之间的相关系数为-0.01。对于高美古2.4m望远镜的数据，修正的FWHM 法估算的视宁度与谱比法之间的相关系数为0.91，而纵向半高宽估算的视宁度与谱比法之间的相关系数为0.58，。修正像运动法与谱比法之间的相关系数为0.65，而纵向方差估算的视宁度之间的相关系数为0.24。这说明，在一定时间内，当一系列斑点图受到了综合因素的影响，而本文所选取的方向并未受到严重影响时(最低要求决定系数大于0.8)，使用本文的方法可以有效提高半高宽法，像运动法与谱比法之间的相关性，对比任意选择一个方向估算视宁度，本文的方法可以有效提高半高宽法和像运动法的视宁度估算精度。

# 4总结与展望

本文分析了影响半高宽法和像运动法估算精度的各种因素，提出了一种可以改善跟踪误差，风或机械振动等因素影响的方法，并使用实测数据进行了验证。我们有以下几点初步结论：

1．使用半高宽法估算视宁度时，使用更大口径的望远镜有利于提高理论上的估算精度  
2．像运动法估算的视宁度比谱比法偏大，可能的原因是曝光时间过长，望远镜口径过大，有限外尺度的影响，或者CCD 噪声或者光子噪声的影响。  
3．一系列斑点图受到跟踪误差，风或者机械振动等因素的影响，而表现为在某个方向上尤其延展开来时，使用本文的方法选择合适的方向来估算视宁度，可以有效改善跟踪误差，风或者机械振动等因素的影响。方向选择的依据是：a).此方向上的方差小，b).重心坐标投影在此方向上依然较好的符合高斯分布。

本文提出的方法改善了跟踪误差，风或机械振动等因素对半高宽法，像运动法的影响，提高了半高宽法，像运动法和谱比法之间的相关性。但是，这三种方法估算的 $r _ { O }$ 值之间仍然存在着一定的偏差。造成偏差的影响因素，量化影响因素与偏差程度之间的关系的方法，以及补偿偏差的方法是未来工作中的研究对象。

# 参考文献

[1]. D.L. Fried, Optical resolution through a randomly inhomogeneous medium for very long and very short exposures [J]. Journal of the Optical Society of America,1966, 56: 1372-1379   
[2].F.Roddier, The efects of atmospheric turbulence in optical astronomy [M]. Progress in Optics XIX,E. Wolf, ed, 1981,19: 281-376   
[3].A.Labeyrie,Attainment of diffraction-limited resolution in large telescopes by Fourier analyzing speckle patterns in star images [J]. Astronomy and Astrophysics,1970,6: 85-87   
[4].D.Korff,Analysis of a method for obtaining near-difraction-limited information in the presence of atmospheric turbulence [J]. Journal of the Optical Society of America,1973, 63(8): 971-980   
[5]. M. C. Roggemann & B. M. Welsh, Imaging through turbulence [M]. Boca Raton, FL: CRC Press,1996,10   
[6].E.A. Harlan & M. F. Walker, A star-trail telescope for astronomical site-testing [J]. Publications of the Astronomical Society of the Pacific,1965,77(457):246-252   
[7]. E. Moroder & A. Righini, The evaluation of night time seeing from polar star trails [J]. Astronomy and Astrophysics,1973,23: 307-310   
[8]. Bin Ma, Zhaohui Shang, Yi Hu, et al. Atmospheric seeing measurement from bright star trails with frame transfer CCDs [J].Proceedings of the SPIE,2016, 9906   
[9]. Su Wu, Xiaodan Hu, Yajuan Han et al, Measurement and analysis of atmospheric optical turbulence in Lhasa based on thermosonde [J]. Journal of Atmospheric and Solar-Terrestrial Physics,2020,201   
[10].Xuan Qian, Yongqiang Yao , Hongshuai Wang, et al, The characteristics at the Ali Observatory based on radiosonde observations [J]. Publications of the Astronomical Society of the Pacific,2018,130:125002   
[11].谭徽松，选址中的大气视宁度测量[J].天文学进展,1992,10(1):48-55 Tan Huisong, Seeing measurements for the site testing [J]. Progress in Astronomy, 1992, 10(1): 48-55   
[12].M. Sarazin,F. Roddier, The ESO differential image motion monitor [J]. Astronomy and Astrophysics,1990, 227: 294-300   
[13].E.J. Seikora, Solar scintillation and the monitoring of solar seeing [J]. Solar Physics,1993, 145: 389-397   
[14].Liu Zhong, J. M. Beckers, Comparative solar seeing and scintillation studies at the Fuxian Lake Solar Station, Solar Physics,2001,198: 197-209   
[15].刘忠，天文图像高分辨重建及空域性质研究 [D].中国科学院研究生院(云南天文台), 2003 Liu Zhong,Research on high-resolution image reconstruction and spatial characteristics of astronomical images [D]. Graduate school of Chinese Academy of Science(Yunnan Astronomical Observatory), 2003   
[16].A. C. Slavin, A. L. Wells, R. Q. Fugate, et al, Comparison of three methods of measuring the atmospheric coherence length [J]. Proceedings of the SPIE   
[17].O. von der Luhe,Estimating fried's parameter from a time series of an arbitrary resolved object imaged through atmospheric turbulence [J]. Journal of the Optical Society of America, 1984, 1(5): 510-519   
[18].G. Ricort, J. Borgnino, C. Aime, A comparison between estimations of fried's parameter r0 simultaneously obtained by measurements of solar granulation contrast and of the variance of angle of arrival fluctuations [J]. Solar Physics,1982,75: 377-394   
[19].A. Irbah, J. Borgnino,D. Djafer, et al, Solar seeing monitor MISOLFA: A new method for estimating atmospheric turbulence parameters [J]. Astronomy and Astrophysics,2016, 591: A150   
[20].D. L. Fried, Differential angle of arrival: Theory, evaluation, and measurement feasibility [J]. Radio Science,1974, 10(1):71-76   
[21].Sreekanth Reddy V, Ravinder Kumar Banyal, Sridharan R,et al. Measurements of atmospheric turbulence parameters at Vainu Bappu Observatory using short-exposure CCD [J]. Research in Astronomy and Astrophysics, 2019,19(5): 74   
[22].林京,刘忠,金振宇，天文高分辨像复原技术检测地基天文光学望远镜成像质量[J]．天 文研究与技术，2004,1(3):188-195 Lin Jing,Liu Zhong, Jin Zhenyu, High-resolution image reconstruction technology applied to the optical testing of ground-based astronomical telescopes [J],Astronomical Research and Technology, 2004,1(3): 188-195   
[23].D. L. Fried. Limiting resolution looking down through the atmosphere [J]. Journal of the Optical Society of America, 1966, 56(10): 1380-1384   
[24].刘忠,戴懿纯,金振宇,等,斑点图的重心与波前倾斜[J],天文研究与技术,2009,6(2):

# Seeing estimation accuracy study based on a sequence of speckle images

Hu Gang1,2, Xiang Yongyuan1,Liu Zhong1,2, Wang Xinhua1.2 (1. Yunnan Astronomical Observatory, Chinese Academy of Science, Kunming 65o011 China; 2. University of Chinese Academy of Science, Beijing 100o49 China)

Abstract: FWHM and image motion are two frequently used methods in the field of astronomy. However, estimation accuracy of these two methods will be affected by tracking error, wind and mechanical vibration. Raising its accuracy plays a rather important role in the area of high-resolution imaging, site selection and seeing monitoring of observatories,etc.For FWHM method, we fit the long exposure image with a two-dimensional gaussian function and choose an appropriate direction to measure its FWHM by which we estimate the seeing parameter. A comparison with spectral ratio method shows a great improvement of our approach against tracking error, wind and mechanical vibration. For image motion method,we employ principle component analysis to project center of gravity coordinates of a sequence of tracking error affected speckle images onto a proper direction on which we find its variance.We further utilize the variance to estimate the seing parameter. A comparison with spectral ratio method also denotes a considerable improvement of our approach against tracking error, wind and mechanical vibration.

Key words: Seeing; FWHM; Image Motion; Tracking Error