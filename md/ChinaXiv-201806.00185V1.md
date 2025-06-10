基础研究

# 基于投影数据全广义变分最小化的低剂量CT重建

牛善洲,吴恒,喻泽峰，郑子君,喻高航赣南师范大学数学与计算机科学学院，江西 赣州341000摘要：目的 提出基于投影数据全广义变分最小化的低剂量CT重建方法。方法 首先，通过非线性Anscombe变换将满足Poisson分布的投影数据转化为近似Gaussian分布,然后基于全广义变分正则化模型对变换后的Gaussan型数据进行噪声去除。最后，对去噪的结果进行Anscombe逆变换后实现传统的滤波反投影(FBP)CT重建。结果 数值体膜实验结果表明本文提出的方法可以大大地改进重建图像的质量。FBP方法重建的Clock和Shepp-Logan体膜图像的信噪比分别为17.752 dB和$1 9 . 3 7 9 ~ \mathrm { d B }$ ,本文方法重建的图像的信噪比提高到24.0352 dB 和 $2 3 . 4 1 8 1 ~ \mathrm { d B }$ 。FBP方法重建方法重建的Clock和 Shepp-Logan体膜图像的均方误差分别为 $0 . 8 6 \%$ 和 $0 . 5 8 \%$ ,本文方法重建的图像的均方误差降低到到 $0 . 2 \%$ 和 $0 . 2 3 \text{‰}$ 结论 本文方法可以在投影数据不满足分段常数假设的前提下去除噪声和条形伪影，从而提高低剂量CT图像重建质量。

关键词：低剂量CT重建;全变分；全广义变分正则化；Gaussian分布；滤波反投影算法

# Total generalized variation minimization based on projection data for low-dose CT reconstruction

NIU Shanzhou,WU Heng,YU Zefeng, ZHENG Zijun,YU Gaohang School of Mathematics and Computer Science,Gannan Normal University,Ganzhou 341ooo,China

Abstract: Objective Toobtain high-qualitylow-doseCT images using total generalized variation regularization based on the projectiondataforlow-dose CTreconstruction.MethodsThe projectiondataof theCTimages weretransformedfromPoisson distributiontoGaussian distributionusingthelinear Anscombe transform.Thetransformeddatawerethenrestored byan fficienttotal generalizedvariationminimization algorithm.Reconstruction was finallyachieved by inverse Anscombe transform and fltered back projection (FBP) method.Results The imagequalityoflow-dose CT was greatly improved bythe proposed algorithm in both Clock and Shepp-Logan phantoms.The signal-to-noise ratios (SNRs)of the Clock and SheppLoganimagesreconstructed byFBPalgorithm were17.752dBand19.379dB, which were increasedbythe proposedalgorithm to 24.0352 and23.4181dB,respectively.TheNMSEof the ClckandShepp-LoganimagesreconstructedbyFBPalgorithm was $0 . 8 6 \%$ and $0 . 5 8 \%$ ， which was reduced by the proposed algorithm to $0 . 2 \%$ and $0 . 2 3 \%$ , respectively. Conclusion The proposed method can efectively suppress noise and stripartifacts inlow-dose CT images when piecewiseconstant assumption is not possible.

Keywords:ow-ose CTreconstruction;total variation;total generalizedvariation;Gaussiandistribution;filteredback-prjec tion algorithm

X射线计算机断层成像(CT)因其在时间、空间分辨率上的卓越表现，已经广泛应用于临床诊断和治疗。CT图像的质量与X射线辐射剂量密切相关，剂量越高图像质量越好，然而，过量的X射线照射又会诱发恶性肿瘤、白血病以及其他遗传性疾病。当前，临床上采用低剂量的CT扫描方案虽然能在一定程度上减少X射线的照射剂量，但采集到的投影数据会含有较高的噪声，直接滤波反投影重建图像的质量往往无法满足临床诊断的需要[2]。因此，如何在降低X射线辐射剂量的同时保证图像质量已经成为CT成像领域的迫切要求，

为了降低X射线的辐射剂量，许多优化的低剂量CT扫描方案[3-5]以及抑制噪声和伪影的重建算法[6-15]相继被提出。目前，直接降低管电流、管电压或者减少扫描角向采样数目是实现低剂量CT扫描最简单且最有效的方法。但是，降低管电流会导致投影数据中光子噪声大幅增加而且电子噪声的影响也会更加突出;降低管电压则会因X射线的穿透能力下降造成射束硬化效应；减少扫描角向采样数目使得投影数据不满足香农采样定理而造成重建图像产生严重的条形伪影。不同于传统的滤波反投影算法，基于低剂量CT投影数据恢复的图像重建方法对CT成像系统进行精确建模(包括X线源、探测器、电子噪声、成像物体等)，可以实现优质的低剂量CT图像重建[16-22]。其目标函数是根据测量数据的噪声特性来构建的，通常包含两项，即数据保真项和正则化项，前者用于描述投影数据的统计特性，后者用于修正解的特性。在图像分段常量的假设下，全变分(TV)正则化模型[23-24]其在去除噪声的同时可以保持图像的边缘信息。然而，许多临床CT图像并不是完全满足分段常量的假设，在剂量特别低时或者投影角度特别少时，TV重建的图像会产生阶梯效应和块状伪影。因此TV正则化在基于投影数据恢复的低剂量CT重建中会失去效力。为了解决这个问题，本文提出一个基于全广义变分(TGV)正则化的低剂量CT重建算法，其可以在投影数据不满足分段常数假设的前提下去除噪声和条形伪影。

本文结构安排形式如下：介绍Anscombe变换公式、全广义变分概念和基于全广义变分最小化恢复模型以及解此模型的优化算法；对Clock体模和 Shepp-Logan体模实验结果定性和定量的分析,来验证所提出方法的有效性;对本文所提出的方法进行总结和讨论。

# 1方法

# 1.1 Anscombe变换

低剂量CT成像系统中，探测数据可以描述为$I { = } I _ { \mathrm { { 0 } } } \exp ( - u )$ ,其中 $I _ { \mathrm { 0 } }$ 为X射线入射光子的数目， ${ \mathbf { } } _ { , I }$ 为出射光子的数目并且服从Poisson分布[25] $u$ 表示经过对数变换后的投影数据,即Sinogram(正弦图)。

服从Poisson分布的数据可以通过Anscombe变换[26]使其变为近似服从Gaussian分布的数据。假设 $x$ 服从Poission分布,通过如下的Anscombe变换：

$$
y ( x ) = 2 \sqrt { x + \frac { 3 } { 8 } }
$$

我们可以将服从Poission分布的 $x$ 变换成近似服从方差为1的Gaussian分布[26]。

假设投影数据每个像素间是互相独立的，并且经过Anscombe变换后都服从方差为1的Gaussion分布，令$f { = } \left( f _ { 1 } , f _ { 2 } , \cdots , f _ { n } \right) ^ { T }$ 为待估计投影数据的理想值,$\boldsymbol { u } = \left( u _ { 1 } , u _ { 2 } , \cdots , u _ { n } \right) ^ { T }$ 表示投影数据经过Anscombe变化后近似满足Gaussian分布的数据，其中表示转置运算。

1.2全广义变分(TGV)

TGV正则化模型由Berdies等 $[ 2 7 , 2 9 ]$ 提出并用于图像去噪。给定图像 $f , k$ 阶TGV的定义为：

$$
\begin{array} { r l } & { T G V _ { \alpha } ^ { k } ( f ) = \operatorname* { s u p } \{ \int _ { \Omega } u \mathrm { d i v } ^ { k } \nu \mathrm { d } x | \nu \in C _ { c } ^ { k } ( \Omega , S y m ^ { k } ( R ^ { d } ) ) } \\ & { \left. \nu \right. _ { \infty } \leq \alpha _ { 0 } , \left. \mathrm { d i v } \nu \right. _ { \infty } \leq \alpha _ { 1 } \} } \end{array}
$$

其中， $l { = } 0 , \cdots , k { - } 1 , k { \in } N$ 是TGV的阶数，

$\alpha = \mathrm { ~ ( ~ } \alpha _ { _ 0 } , \mathrm { ~ } \alpha _ { _ 1 } , \mathrm { ~ } \cdots , \mathrm { ~ } \alpha _ { _ { k - 1 } } \mathrm { ~ ) ~ }$ 是TGV的权重。 $S y m ^ { k } ( R ^ { d } )$ 是 $k$ 阶对称张量空间， $l$ 阶散度算子定义是：

$$
\mathrm { d i v } ^ { l } \nu { = } \Sigma _ { \gamma \in M _ { l } } \frac { l ! } { \gamma ! } \frac { \displaystyle \hat { \sigma } ^ { l } \nu _ { \eta + \gamma } } { \displaystyle \hat { \sigma } x ^ { \gamma } } , \eta \in M _ { k - 1 }
$$

其中， $\begin{array} { r } { M _ { k } = \{ \eta \in N ^ { d } | \sum _ { i = 1 } ^ { d } \eta _ { i } = k \} } \end{array}$ ， $k$ 阶张量对称张量的无穷范数定义为：

$$
\left\| \nu \right\| _ { _ { \infty } } = \operatorname* { s u p } _ { x \in \Omega } \left\{ ( \sum _ { \eta \in M _ { k } } \frac { k ! } { \eta ! } \nu _ { \eta } ( x ) ^ { 2 } ) ^ { \frac { 1 } { 2 } } \right\}
$$

当 $k = 1$ 时，TGV和TV是等价，即可以表示为：$T G V _ { \alpha } ^ { k } = \alpha _ { 0 } T V$ 。在本文中,我们只考虑二阶TGV,定义为：

$$
\begin{array} { r l } & { T G V _ { \alpha } ^ { 2 } ( f ) { = } \operatorname* { s u p } \{ \int _ { \Omega } u \mathrm { d i v } ^ { 2 } \nu \mathrm { d } x | \nu { \in } C _ { c } ^ { 2 } ( \Omega , S ^ { d \times d } ) } \\ & { \left. \nu \right. _ { \infty } \leq \alpha _ { 0 } , \left. \mathrm { d i v } \nu \right. _ { \infty } \leq \alpha _ { 1 } \} } \end{array} ,
$$

其中, $S ^ { d \times d }$ 是 $d \times d$ 维矩阵空间, $a = \mathrm { ~ ( ~ } a _ { 0 } , \mathrm { ~ } a _ { 1 } \mathrm { ~ ) ~ }$ 是正数,进一步，对称矩阵的一阶和二阶散度可以由下式表示：

$$
( \mathrm { d i v } \nu ) _ { i } = \sum _ { j = 1 } ^ { d } \frac { \hat { \partial } \nu _ { i j } } { \hat { \partial } x _ { j } } , \mathrm { d i v } ^ { 2 } \nu \ = \sum _ { i = 1 } ^ { d } \frac { \hat { \partial } ^ { 2 } \nu _ { i i } } { \hat { \partial } x _ { i } ^ { 2 } } + 2 \sum _ { i < j } \frac { \hat { \partial } \nu _ { i j } } { \hat { \partial } x _ { i } \hat { \partial } x _ { j } }
$$

类似的，(5)式中的无穷范数定义为：

$$
\left\| \nu \right\| _ { \infty } = \operatorname* { s u p } _ { x \in \Omega } \Biggl ( \sum _ { i = 1 } ^ { d } \bigl | \nu _ { i i } ( x ) \bigr | ^ { 2 } + 2 \sum _ { i < j } \bigl | \nu _ { i j } ( x ) \bigr | ^ { 2 } \Biggr ) ^ { \frac { 1 } { 2 } }
$$

$$
\left\| \operatorname { d i v } \nu \right\| _ { \infty } = \operatorname { s u p } \left( \sum _ { i = 1 } ^ { d } \Biggl | \sum _ { j = 1 } ^ { d } \frac { \hat { \sigma } \nu _ { i j } } { \hat { \sigma } x _ { j } } ( x ) \Biggr | ^ { 2 } \right) ^ { \frac { 1 } { 2 } }
$$

其中，文献[27给出了与式(5)互相等价的二阶TGV的定义：

$$
T G V _ { a } ^ { 2 } ( f ) = \operatorname* { m i n } _ { \omega } \alpha _ { 1 } \int _ { \Omega } \lvert \nabla f - \omega \rvert d x + \alpha _ { 0 } \int _ { \Omega } \lvert \varepsilon ( \omega ) \rvert d x
$$

其中， $\varepsilon ( \omega ) = \frac { \mathrm { 1 } } { 2 } ( \mathrm { \nabla } \omega + \mathrm { \nabla } \omega ^ { \mathrm { T } } )$ 为Radon测度， $a _ { 0 }$ 和 $a _ { \scriptscriptstyle 1 }$ 是TGV的权重，来平衡(5)式的前一项的一阶导数和后一项的二阶导数。由于TGV用高阶导数信息描述图像的特性,TGV不需要满足投影数据是分段常数的假设[28-29]

1.3基于投影数据TGV最小化的CT重建方法投影数据恢复的一般模型[22]可以表示为：

$$
\tilde { f } { = } \underset { f } { \arg \operatorname* { m i n } } \frac { 1 } { 2 } { \left\| { u - f } \right\| } _ { { 2 } } ^ { 2 } + \lambda R ( f )
$$

其中，第1项为数据保真项，第2项为正则化项$\lambda > 0$ 是正则化参数。

本文用TGV正则化代替式(10)中的正则化项$R ( f )$ ,得到基于TGV最小化的理想数据恢复模型为：

$$
\tilde { f } { = } \underset { f } { \arg \operatorname* { m i n } } \frac { 1 } { 2 } { \| u - f \| } _ { 2 } ^ { 2 } + \lambda T G V ( f )
$$

其中，是正则化参数。

公式(11)的离散形式为：

$$
\operatorname* { m i n } _ { f \in { \cal F } , \omega \in { \cal W } } \frac { 1 } { 2 } \big \| u - f \big \| _ { 2 } ^ { 2 } + \beta _ { 1 } \big \| \nabla f - \omega \big \| _ { 1 } + \beta _ { 0 } \big \| \varepsilon ( \omega ) \big \| _ { 1 }
$$

其中, $\boldsymbol { F } = \boldsymbol { R } ^ { N \times N }$ ， $\boldsymbol { W } = \boldsymbol { R } ^ { 2 N \times N }$ 以及微分算子div， $\varepsilon \ , \nabla$ 可以由限差分算子近似得到[29]

根据对偶原理[23]，我们可以将(12)转化为如下的鞍点问题：

$$
\operatorname* { m i n } _ { f \in F , \omega \in W } \operatorname* { m a x } _ { p \in P , q \in \mathcal { Q } } \frac { 1 } { 2 } \big \| u - f \big \| _ { 2 } ^ { 2 } + p ^ { \mathrm { { r } } } \mathbf { \Psi } ( \nabla f - \omega ) + q ^ { \mathrm { { r } } } \varepsilon ( \omega )
$$

其中， $p$ 和 $q$ 为对偶变量,并且 $P$ 和 $\boldsymbol { \mathcal { Q } }$ 定义为：

$$
\begin{array} { c } { P = \{ p \in R ^ { 2 N \times N } \Vert \big | \left| \begin{array} { c } { P _ { \mathrm { l } } \leq \beta _ { \mathrm { l } } \} } \\ { Q = \{ q \in R ^ { 3 N \times N } \Vert \big | q \big | \big | _ { \infty } \leq \beta _ { \mathrm { 0 } } \} } \end{array} \right. } \end{array}
$$

$p r o j _ { { P } } ( \tilde { p } )$ 和 $p r o j _ { { P } } ( \tilde { q } )$ 的定义如下：

$$
p r o j _ { P } \big ( \tilde { p } \big ) = \frac { \tilde { p } } { \operatorname* { m a x } ( 1 , | \tilde { p } | / \beta _ { 1 } ) }
$$

$$
p r o j _ { \varrho } ( \tilde { q } ) = \frac { \tilde { q } } { \operatorname* { m a x } ( 1 , | \tilde { q } | / \beta _ { 0 } ) }
$$

$p r o x _ { 1 } \big ( \tilde { f } \big )$ 是邻近算子,其由下式表示：

$$
p r o x _ { 1 } \big ( \tilde { f } \big ) = \underset { f \in F } { \arg \operatorname* { m i n } } \frac { \big \| f - u \big \| _ { 2 } ^ { 2 } } { 2 } + \frac { \big \| f - \tilde { f } \big \| _ { 2 } ^ { 2 } } { 2 \tau }
$$

由上述方法求出(11)式的解并对其进行Anscombe逆变换，最后由滤波反投影算法进行重建。

下面我们给出基于TGV正则化的低剂量CT重建方法的计算步骤：

步骤1对低剂量CT投影数据进行Anscombe变换，将服从Poission分布的投影数据转化为近似Gaussian分布的数据。

步骤2基于全广义变分最小化模型，我们使用Chambolle-Pock算法3o求解，从而达到对Anscombe变换后投影数据去噪的目的。

(1)初始化参数： $\beta _ { \scriptscriptstyle 0 } , \beta _ { \scriptscriptstyle 1 } , \tau , \rho$ ;

(2)初始化变量: $p ^ { 0 } , q ^ { 0 } , \omega ^ { 0 } , \varpi ^ { 0 } , f ^ { 0 } , { \bar { f } } ^ { 0 }$

(3)对数据进行迭代恢复，迭代形式如下：

$$
\begin{array} { r l } & { \boldsymbol { p } ^ { n + 1 } = \boldsymbol { p r o j } \boldsymbol { \hat { p } } \big ( \boldsymbol { p } ^ { n } + \boldsymbol { \rho } \big ( \boldsymbol { \sqrt { f } } ^ { n } - \boldsymbol { \hat { w } } ^ { n } \big ) \big ) } \\ & { \boldsymbol { q } ^ { n + 1 } = \boldsymbol { p r o j } \boldsymbol { \hat { q } } \big ( \boldsymbol { q } ^ { n } + \boldsymbol { \rho } \boldsymbol { \varepsilon } \big ( \boldsymbol { \hat { \sigma } } ^ { n } \big ) \big ) , } \\ & { \boldsymbol { f } ^ { n + 1 } = \boldsymbol { f } ^ { n } , } \\ & { \boldsymbol { f } ^ { n + 1 } = \boldsymbol { p r o x } _ { 1 } ^ { n } \big ( \boldsymbol { f } ^ { n } + \boldsymbol { \tau } \mathrm { d i v } _ { 1 } \boldsymbol { p } ^ { n + 1 } \big ) , } \\ & { \boldsymbol { \hat { f } } ^ { n + 1 } = \boldsymbol { 2 } \boldsymbol { f } ^ { n + 1 } , } \\ & { \boldsymbol { O } ^ { n d } = \boldsymbol { \omega } ^ { n } , } \\ & { \boldsymbol { O } ^ { n + 1 } = \boldsymbol { \omega } ^ { n } + \boldsymbol { \tau } ( \boldsymbol { p } ^ { n + 1 } + \mathrm { d i v } _ { 2 } \boldsymbol { q } ^ { n + 1 } ) \mathrm { ~ , ~ } } \\ & { \boldsymbol { \hat { \omega } } ^ { n + 1 } = \boldsymbol { 2 } \boldsymbol { \hat { \omega } } ^ { n + 1 } - \boldsymbol { \omega } ^ { \omega } , } \end{array}
$$

步骤3对步骤2得到的数据其进行Anscombe逆变换，得到去噪后的投影数据

步骤4对步骤3得到的投影数据进行FBP重建得到CT图像。

# 2实验与分析

为了验证全广义变分最小化方法在低剂量CT图像重建中的有效性,本文通过Clock和Shepp-Logan数值体模进行定量和定性分析。并且与斜波滤波反投影算法、汉宁滤波反投影算法和非单调全变分最小化算法[28]进行比较。CT成像几何采用弧形探测器的扇形束，其中射线源到旋转中心和探测器的距离分别为 $5 7 0 ~ \mathrm { m m }$ 和 $1 0 4 0 ~ \mathrm { { m m } }$ ，旋转角在 $[ 0 , 2 \pi ]$ 间的采样值为1160,探测器个数为672。体模大小设定为 $5 1 2 \times 5 1 2$ ，对于Clock体模，入射光子数为 $5 . 0 \times 1 0 ^ { 4 }$ ;相应的Shepp-Logan体模的入射光子数为 $1 . 0 { \times } 1 0 ^ { 5 }$ O

# 2.1Clock体模实验

Clock体模实验结果如图1所示。其中，图1A为真实的体模图像；图1B为斜波滤波反投影算法重建的结果；图1C为汉宁滤波反投影算法重建的结果；图1D为非单调全变分最小化(NTVM)算法重建的结果;图1E为本文提出的全广义变分最小化方法重建的结果。为了进一步展现本方法重建效果，图2给出了对应图1的局部放大图。由图2可以清晰的看出本文方法对噪声和伪影的抑制效果。

通过计算重建图像的信噪比和均方误差可以定量地分析不同方法的差异。信噪比计算公式为：

$$
S N R = 1 0 \log _ { 1 0 } \left( \frac { \sum _ { i } \bigl ( F _ { r e c } ( i ) - \bar { F } _ { r e c } \bigr ) ^ { 2 } } { \sum _ { i } \bigl ( F _ { r e c } ( i ) - F _ { t u r e } ( i ) \bigr ) ^ { 2 } } \right)
$$

均方误差计算公式为：

$$
\mathit { N M S E } = \left( \frac { \sum _ { i } ( F _ { \mathit { r e c } } ( i ) - F _ { \mathit { t u r e } } ( i ) ) ^ { 2 } } { \sum _ { i } ( F _ { \mathit { t u r e } } ( i ) ) ^ { 2 } } \right)
$$

其中, $F _ { r e c } ( i )$ 表示像素点 $i$ 通过算法得到的重建图像的灰度值, $\bar { F } _ { r e c }$ 表示重建图像 $\boldsymbol { F } _ { r e c }$ 中所有像素点灰度的平均值; $F _ { _ { t u r e } } ( i )$ 表示真实图像像素点 $i$ 处的灰度值。

由表1的性噪比和均方误差分析可以看出，相对于滤波反投影和非单调最小化方法，本文提出的重建图像的方法具有最高的信噪比和最小的均方误差。与NTVM算法相比，TGV方法信噪比提高了 $2 . 6 1 \%$ ，而相应的均方误差减少了 $1 3 . 0 4 \%$ O

为了进一步验证本文提出方法的优越性，我们分别给出了4种方法重建结果的线剖面图(图3)，其中横坐标为图像像素位置，横坐标为图像的衰减值。由图3可以看出本文提出的重建图像的方法与其他3种方法相比，能够较好的接近真实图像的线剖面。

# 2.2Shepp-Logan 体模实验

Shepp-Logan体模实验结果如图4所示。其中，图4A为真实的体模图像；图4B为通过斜波滤波反投影算法重建的结果；图4C为汉宁滤波反投影算法重建的结果；图4D为非单调全变分最小化算法重建的结果；图4E为本文提出的全广义变分方法重建的结果。图5给出了低剂量CT重建结果的一个局部的放大图。

：：：：

由表2的信噪比和均方误差分析可以看出，与其他3种方法相比，本文提出的全广义变分方法在提高图像重建的信噪比，降低重建图像均方误差方面均有上佳表现。与NTVM算法相比，TGV方法信噪比提高了$1 . 0 3 \%$ ，而相应的均方误差减少了 $8 \%$ □

![](images/b0b233485dcb036cd83cf2cc7491e54ffdeec9f8ee9010a20a325ba1ef1c9fa3.jpg)  
图1Clock体模图像和不同方法重建的图像 Fig.1 Clock phantom and image reconstructed by different methods.A: Clock phantom; B: Image reconstructed by FBP algorithm with ramp filter; C: Image reconstructed by FBP algorithm with hanning filter; $D$ Image reconstructed by NTVM method; E: Image reconstructed by TGV method.   
图2Clock体膜图像局部放大图  
Fig.2 Zoomed-in views of the Clock phantom and images reconstructed by different methods.Clock phantom (first column); Image reconstructed by FBP algorithm with ramp filter (second column); Image reconstructed by FBP algorithm with hanning filter (third column);Image reconstructed by NTVM method (fourth column); Image reconstructed by TGV method (fifth column).

此外，为了更直观的验证重建图像的质量，我们画出了重建图像的线剖面图(图6)，其中横坐标为图像像素位置，横坐标为图像的衰减值。由线剖面图可以看出本文提出的方法重建的图像与真实图像的线剖面有更高的吻合度。

表1Clock体膜图像的信噪比和均方误差Tab.1 SNR and NMSE of the Clock phantor  

<html><body><table><tr><td>Methods</td><td>FBP (ramp)</td><td>FBP (hann)</td><td>NTVM</td><td>TGV</td></tr><tr><td>SNR (dB)</td><td>17.7521</td><td>22.0859</td><td>23.4227</td><td>24.0352</td></tr><tr><td>NMSE</td><td>0.0086</td><td>0.0031</td><td>0.0023</td><td>0.0020</td></tr></table></body></html>

# 3讨论

基于TV最小化的CT图像重建方法在抑制噪声和伪影方面取得了很好的效果。由于TV是基于图像分段常量的假设，当噪声水平非常高时，会产生严重的阶梯效应。针对TV方法重建的图像会产生阶梯效应的问题，本文提出了一个基于TGV正则化的低剂量CT重建算法，该方法不需要在投影数据满足分段常数假设。由于TGV利用了高阶导数信息，在不满足分段常量的假设下，本文方法可以有效去除噪声的同时，可以有效地抑制噪声与条形伪影。数值仿真实验结果表明本文提出的方法可以有效地抑制低剂量CT图像中的噪声和伪影，消除TV正常产生的阶梯效应，从而改善低剂量CT图像重建的质量。

![](images/b6a3ac1023570ca1c6b1ed5b663f9a50b4b340b1602614c4f01df2641150661b.jpg)  
图3Clock体膜图像的线剖面图Fig.3Profiles of the clock phantom.

![](images/975c6904fe43fff14341c0e851e2380f0f1e656409af5e784c7506d854b78faf.jpg)  
图4Shepp-Logan体模图像和不同方法重建的图像 Fig.4 Shepp-Logan phantom and images reconstructed by different methods.A: Clock phantom; B: Image reconstructed by FBP algorithm with ramp filter; C:Image reconstructed by FBP algorithm with hanning filter;D:Image reconstructed by NTVM method;E: Image reconstructed by TGV method.

在Clock体膜实验中，由图1可以看出斜波滤波反投影和汉宁滤波反投影算法重建的图像含有大量的噪声和条形伪影，图像质量严重退化。非单调全变分算法重建的图像虽然在一定程度上减少了CT图像的条形伪影和噪声，但由于TV正则化的缺陷，部分伪影和噪声仍然存在。从视觉效果评价来看，我们提出的方法在去除图像的噪声和条形伪影方面具有更佳的表现。在Shepp-Logan体膜实验中，由图4我们可以看到,相比滤波反投影和非单调全变分最小化方法，我们提出的全广义变分最小化方法在抑制噪声与条形伪影和保持边缘方面都有良好表现，可以更好的保持图像一致性。进一步，由体膜图像重建结果的放大图可以明显的看出，本文提出的全广义变分方法重建的图像对噪声和伪影有更好的抑制作用。此外,Clock和 Shepp-Logan体膜实验的定量实验结果进一步表明，本文提出的方法比非单调全变分算法更具优越性。

![](images/3b2474eebe3049caadaf5b78012e8cd79b04175bc4e7e602d40f527e094e093c.jpg)  
图5Shepp-Logan体膜图像局部放大图 Fig.5 Zoomed-in views of the Shepp-Logan phantom and images reconstructed by diferent methods. A: Clock phantom; B: Image reconstructed byFBP algorithm with ramp filter; C: Image reconstructed by FBP algorithm with hanning filter; D: Image reconstructed by NTVM method; E: Image reconstructed by TGV method (fifth column).

表2Shepp-Logan体膜图像的信噪比和均方误差Tab.2 SNR and NMSE of the Shepp-Logan phantom  

<html><body><table><tr><td>Methods</td><td>FBP (ramp)</td><td>FBP (hann)</td><td>NTVM</td><td>TGV</td></tr><tr><td>SNR (dB)</td><td>19.3790</td><td>22.2822</td><td>23.1767</td><td>23.4181</td></tr><tr><td>NMSE</td><td>0.0058</td><td>0.0030</td><td>0.0025</td><td>0.0023</td></tr></table></body></html>

由于本文提出的方法需要根据具体的重建目标人工选择正则化参数，大大限制了其更为广泛的应用。从国内外的研究现状来看，目前还没一种有效的参数选择方式，使得正则化的自适应参数调整达到最佳状态。因此，如何自适应选择正则化化参数是我们今后研究的一个重点课题。

![](images/101716d0b6af9baa216aa6bcc072b4c8603d5e5730829cacf0478dc0d4ebd591.jpg)  
图6Shepp-Logan体膜图像的线剖面图Fig.6 Profiles of the Shepp-Logan phantom.

# 参考文献：

[1]Einstein A. Henzlova M and rajagopalan S.estimating risk of cancer associated with radiation exposure from 64-slice CT coronary angiography[J]. JAm Med Assoc,2007,298(3): 317-23.   
[2]Kopka L,Funke M,Breiter N,et al.An anatomically adapted variation of the tube current in CT. Studies on radiation dosage reduction and image quality[J].Rofo,1995,163(6): 383-7.   
[3]Herzog C,MulvihillDM,Nguyen SA,et al.Pediatric cardiovascular CT angiography:Radiation dose reduction using automatic anatomic tube current modulation[J].AJR Am JRoentgenol, 2008,190(5): 1232-40.   
[4]Rudin LI, Osher S,Fatemi E.Nonlinear total variation based noise removal algorithms[J].Physica D,1992,60(1/4): 259-68.   
[5] Wang J, Guan H, Solberg T. Inverse determination of the penalty parameter in penalized weighted least-squares algorithm for noise reduction of low-dose CBCT[J].Med Phys,2011,38(7): 4066-72.   
[6] Niu S, Gao Y, Bian Z,et al. Sparse-view X-ray CT Reconstruction via total generalized variation regularization[J].Phys Med Biol, 2014,59(12): 2997-3017.   
[7］马建华,陈武凡.基于最大互信息量熵差分割的CT金属伪影消除[J]. 电子学报,2009,37(8):1779-83.   
[8］张善立,张 华,胡德斌,等.基于边缘检测算子的Huber正则化阈值选 择方法在低剂量CT重建中的应用[J].南方医科大学学报,2015,35 (3): 375-9.   
[9]Niu S,Huang J,Bian Z,et al. Iterative Reconstruction for sparse-view X-ray CT using alpha-divergence constrained total generalized variation minimization[J].JXray Sci Technol,2017,25 (4): 673-88.   
[10] Zhang Y, Ma J, Iyengar P,et al. A new CT Reconstruction technique using adaptive deformation recovery and intensity correction (ADRIC)[J]. Med Phys,2017,44(6): 2223-41.   
[11]Gao Y，Bian Z，Huang J,et al.Low-dose X-ray computed tomography image Reconstruction with a combined low-mAs and sparse-view protocol[J]. Opt Express,2014,22(12): 15190-210.   
[12]Huang J ZY, Chen WF. Iterative image Reconstruction for sparseview CT using normal-dose image induced total variation prior[J]. PLoS One,2013,8(11): e79709.   
[13]Li J,Niu S,Huang J,et al.An efficient augmented lagrangian method for statistical X-Ray CT image reconstruction[J]. PLoS One,2015,10(10): e0140579.   
[14]Li TF, Xiang L,Jing W,et al. Nonlinear sinogram smoothing for low-dose X-ray CT[J].IEEE Trans Nucl Sci,2004,51(5): 2505-13.   
[15]Huang J, Ma J,Liu N,et al. Sparse angular CT Reconstruction using non-local means based iterative-correction POCs[J]. Comput Biol Med,2011,41(4): 195-205.   
[16] Wang J,Li TF.Lu H B and liang Z G,penalized weighted leastsquaresapproach to sinogram noise reduction and image Reconstruction for low-dose x-ray computed tomography[J]. IEEE Trans Med Imaging,2006,25(10): 1272-83.   
[17] Sonka M,Fitzpatrick JM. Handbook of medical imaging[M]. SPIE, Bellingham, Washington,2000: 1-70.   
[18]Wang J,Li T,Xing L. Iterative image Reconstruction for CBCT using edge-preserving prior[J].Med Phys,2009,36(1): 252-60.   
[19]Wang J,Liang Z,Lu H. Multiscale penalized weighted leastsquaressinogram restoration for low-dose X-ray computed tomography[J].Conf Proc IEEE Eng Med Biol Soc,2006,1(3): 3282-5.   
[20] Wang J,Li T,Lu H,et al. Noise reduction for Low-Dose SigleSlice helical CT sinograms[J].IEEE Trans Nucl Sci,2006,53(3): 1230-7.   
[21] Xu JY. Taguchi K and Tsui B M.statistical projection completion in X-ray CT using consistency conditions [J].IEEE Trans Med Imaging,2010,29(8): 1528-40.   
[22]Bian Z, Ma J, Huang J,et al. SR-NLM: asinogram restoration induced non-local means image filtering for low-dose computed tomography[J]. Comput Med Imaging Graph,2013,37(4): 293-303.   
[23]Tang J. Nett B and Chen G. Performance comparison between total variation(TV)-based compressed sensing and statistical iterative Reconstruction algorithms[J]. Phys Med Biol, 2009,54(19): 5781- 804.   
[24] Yu GH,Qi LQ,Dai YH. On nonmonotonechambolle gradient projection algorithms for total variation image restoration [J].J Mathemat Imaging and Vision,2009,35(2): 143-54.   
[25]Makitalo M,Foi A.On the inversion of the anscombe transformation in low-count poisson image denoising[C]//LNLA: 2009InternationalWorkshoponLocalandNon-local Approximation in Image Processing,2009: 26-32.   
[26]Anscombe FJ.The transformation of poisson，binomial and negative-binomial data[J].Biometrika,1948,35(3/4):246-54.   
[27]Bredies K,Dong Y,Hintermuller M.Spatially dependent regularization parameter selection in total generalized variation models for image restoration[J]. Int J Comput Math,2013,90(1): 109-23.   
[28]钱珊珊,黄 静.基于投影数据非单调性全变分恢复的低剂量CT重建 [J].电子学报,2011,39(7):1702-7.   
[29]KnollF1,Bredies K,Pock T, et al.Second order total generalized variation(TGV)for MRI[J].Magn Reson Med,2011,65(2): 480-91.   
[30] Chambolle A,Pock T.A First-Order Primal-Dual algorithm for convex problems with applications to imaging［J]. J Math Imaging Vis,2011,40(1): 120-45.