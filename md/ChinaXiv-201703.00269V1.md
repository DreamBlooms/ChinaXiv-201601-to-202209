# 基于交叉点数据和三维非参数模型的雷达高度计海况偏差估计方法

蒋茂飞\*①②③ 许可② 刘亚龙④ 王磊②①(中国科学院微波遥感技术重点实验室北京100190)②(中国科学院国家空间科学中心北京100190)③（中国科学院大学北京100049）(国家海洋局烟台海洋环境监测中心站 烟台264000)

摘要：海况偏差(Sea State Bias,SSB)是雷达高度计测量海面高度的重要误差源。目前，业务化运行的雷达高度计的海况偏差校正都是采用基于风速 $( U )$ 和有效波高(SWH)的2维经验模型方法，其海况偏差校正不确定度约为 $2 \mathrm { c m }$ 。该文提出了一种基于交叉点数据和3维非参数模型的海况偏差估计方法，该方法利用星下交叉点数据，采用基于U,SWH以及平均波周期(MWP)的3 维非参数模型进行海况偏差估计。该文利用这种估计方法对 Jason-2卫星雷达高度计 $2 0 0 9 { \sim } 2 0 1 1$ 三年的数据进行了处理，将处理结果与 Jason-2卫星高度计的地球物理数据集(Geophysical DataRecords,GDR)中的海况偏差校正项进行对比，结果表明该文提出的海况偏差估计方法平均能降低 1.64 $\mathrm { c m } ^ { 2 }$ 的交叉点海面高度不符值的方差和 $\mathrm { 0 . 9 2 c m } ^ { 2 }$ 的沿轨海面高度异常值的方差,分别对应于 $1 . 2 8 ~ \mathrm { c m }$ 和 $0 . 9 6 ~ \mathrm { c m }$ 的均方根(RMS)海面高度，这对于提高高度计数据产品的精度具有重要意义。

中图分类号：TN953 文献标识码：A 文章编号：DOI:10.11999/JEIT160195

# A New Method for Radar Altimeter Sea State Bias Estimation Based on Crossover Data and Three-dimensional Nonparametric Model

JIANG Maofei ②③ XU Ke0② LIU Yalong WANG Lei 0② (Key Laboratory of Microwave Remote Sensing, Chinese Academy of Sciences,Beijing 1Oo19o, China) (National Space Science Center, Chinese Academy of Sciences,Beijing 1Ooi9o, China) (University of Chinese Academy of Sciences,Beijing 1Ooo49,China) (YantaiMarine Environmental Monitoring Center Station,State Oceanic Administration,antai 264ooo,China)

Abstract:The Sea State Bias (SSB)isan important source of eror insatelitealtimetry.Operational SSBcorrection models are based on the altimeter-measured Wind Speed $( U )$ and Significant Wave Height (SWH). This paper presents a new method to estimate the SB from the crossover differences usingathree-dimensional nonparametric modelbased on $U$ ,SWH and the Mean Wave Period (MWP).Evaluated by the separate annual data sets from 2009 to 2O11,the SSB values estimated with the presented method can decrease the variance of the crossver Sea Surface Height (SSH) differences by $1 . 6 4 \mathrm { c m } ^ { 2 }$ ，or $1 . 2 8 ~ \mathrm { c m }$ RMS,and decrease the variance of the Sea Level Anomalies (SLA) by $\mathrm { 0 . 9 2 c m } ^ { 2 }$ ，or 0.96 cm RMS in comparison to the SSB values in the Geophysical Data Records (GDR)of Jason-2.It is of great significance for improving the precision of altimeter products.

Key words: Radar altimeter; Sea state bias; Crossover; Three-dimensional nonparametric model

# 1引言

全球海平面上升已经越来越引起人们的关注，雷达高度计的一个主要应用就是测量平均海面高度[1-3]。然而，由于海面是非高斯分布的，波谷的曲率半径比波峰大，所以波谷能反射更多的电磁能量，从而使得高度计测得的平均海面低于真实的平均海面，这种效应称为电磁偏差[+]。在高度计的回波跟踪算法中，通常假设海面高度的概率密度函数为高斯函数，而实际海面高度的概率密度函数是有偏斜度的，这样就会产生偏斜度偏差。电磁偏差和偏斜度偏差一起统称为海况偏差(Sea State Bias,SSB)，海况偏差的不确定度很大，能够达到 $\mathrm { 2 ~ c m } \mathrm { \Delta } [ \mathrm { 5 } , \mathrm { 6 } ]$ ，随着精密定轨技术的发展，在Jason系列测高卫星中，海况偏差已经取代轨道误差成为

雷达高度计测高最大的误差源[6,7]。

国际上主要从理论模型[4,7-10]和经验模型[5,1-17两个方面对海况偏差进行研究。海况偏差的机理非常复杂，目前理论模型并不实用，业务化运行的高度计都是采用经验模型对海况偏差进行校正。海况偏差经验模型包括参数模型[,3,17]和非参数模型[5,12,14-16]，非参数模型精度更高，被广泛应用于海况偏差校正。传统的海况偏差经验模型使用高度计测得的 $U$ 和 SWH作为模型的输入，但仅仅由 $U$ 和SWH只能得到有限的海况偏差信息，新参量的引入成为海况偏差经验模型新的研究方向[15,16]。文献[15,16]在 2010年利用全球波模式数据WAVEWATCHIII生成了平均波周期(MWP)，利用海面高度异常数据建立了一个基于 $U _ { ☉ }$ SWH和MWP的3维海况偏差估计模型，结果表明和传统的基于 $U$ 和SWH的2维模型相比，3维海况偏差估计模型可以减小 $1 . 2 6 ~ \mathrm { c m ^ { 2 } }$ 的海面高度方差[17]。这个3维海况模型中的平均海平面是通过不同高度计多年测高数据平均得到，这样会引入较大误差，由此得到的 SSB估计值误差也比较大。

在文献[15,16]的基础上，本文提出了一种基于交叉点数据和3维非参数模型的海况偏差估计方法。本文利用非线性海浪理论简单分析了波周期和海况偏差的大致关系，为将波周期信息引入海况偏差估计提供了理论依据。利用本文方法分别对Jason-2卫星雷达高度计 ${ 2 0 0 9 } { \sim } 2 0 1 1$ 三年的数据进行了处理，并将处理结果与 Jason-2卫星高度计的GDR产品中的海况偏差校正项进行对比，结果表明本文提出的海况偏差估计方法能极大地降低交叉点海面高度不符值的方差和沿轨海面高度异常值的方差，这对于提高雷达高度计的测高精度具有重要意义。

# 2波周期与海况偏差的关系

文献[15,16]曾将平均波周期引入海况偏差估计中，但是国内外还没有公开资料论述波周期与海况偏差的关系，本文希望通过海浪理论将波周期与海况偏差联系起来，从而为将波周期信息引入海况偏差估计提供理论依据。海况偏差主要是由海面的非线性特性所引起的，所以可以使用非线性海浪理论来进行研究。常用的非线性海浪理论主要有斯托克斯(Stokes)波理论、椭圆余弦(Cnoidal)波理论和孤立(Solitary)波理论，椭圆余弦波理论、孤立波理论以及五阶 Stokes 波理论都主要适用于浅水，而高度计的绝大部分有效测量点都在深水区，所以本文使用四阶Stokes波理论。

根据四阶Stokes波理论，波面轮廓可以表示为[18]：

$$
\begin{array} { l } { { V ( x ) = \displaystyle { \frac { 1 } { 2 } } k a ^ { 2 } + k ^ { 3 } a ^ { 4 } + a ( 1 + \frac { 9 } { 8 } k ^ { 2 } a ^ { 2 } ) \mathrm { c o s } ( k x ) + ( \frac { 1 } { 2 } k a ^ { 2 } + \frac { 1 1 } { 6 } k ^ { 3 } a ^ { 4 } ) \mathrm { c o s } ( 2 k x ) } } \\ { { \displaystyle ~ + \frac { 3 } { 8 } k ^ { 2 } a ^ { 3 } \mathrm { c o s } ( 3 k x ) + \frac { 1 } { 3 } k ^ { 3 } a ^ { 4 } \mathrm { c o s } ( 4 k x ) } } \end{array}
$$

式中， $L = \frac { g T ^ { 2 } } { 2 p } ( 1 + k ^ { 2 } a ^ { 2 } )$ ， $H = 2 a ( 1 + { \frac { 3 } { 2 } } k ^ { 2 } a ^ { 2 } )$ 愛和 $k = { \frac { 2 p } { L } }$ 分别为波长、波高和波数，T为波周期，a为与波高 $H$ 有关的待定实常数。波面轮廓 $V ( x )$ 满足：

$$
\dot { \ O } _ { 0 } ^ { 2 p / k } [ V \left( x \right) - \ ( \frac { 1 } { 2 } k a ^ { 2 } + k ^ { 3 } a ^ { 4 } ) ] d x = 0
$$

式 $( 2 )$ 表明， $z _ { \scriptscriptstyle 0 } = \frac { 1 } { 2 } k a ^ { 2 } + k ^ { 3 } a ^ { 4 }$ 为静止时的自由面，或者说坐标原点位于静止水面以下 $\frac { 1 } { 2 } k a ^ { 2 } + k ^ { 3 } a ^ { 4 }$ 处。波峰到坐标原点的距离为：

$$
\begin{array} { l } { { \displaystyle { H _ { c } = \frac { 1 } { 2 } k a ^ { 2 } + k ^ { 3 } a ^ { 4 } + a ( 1 + \frac { 9 } { 8 } k ^ { 2 } a ^ { 2 } ) + ( \frac { 1 } { 2 } k a ^ { 2 } + \frac { 1 1 } { 6 } k ^ { 3 } a ^ { 4 } ) } } } \\ { { \displaystyle { + \frac { 3 } { 8 } k ^ { 2 } a ^ { 3 } + \frac { 1 } { 3 } k ^ { 3 } a ^ { 4 } } } } \end{array}
$$

波谷到坐标原点的距离为：

$$
\begin{array} { c } { { H _ { \ L _ { t } } = \displaystyle \frac { 1 } { 2 } k a ^ { 2 } + k ^ { 3 } a ^ { 4 } - a ( 1 + \frac { 9 } { 8 } k ^ { 2 } a ^ { 2 } ) + ( \frac { 1 } { 2 } k a ^ { 2 } + \frac { 1 1 } { 6 } k ^ { 3 } a ^ { 4 } ) } } \\ { { - \displaystyle \frac { 3 } { 8 } k ^ { 2 } a ^ { 3 } + \displaystyle \frac { 1 } { 3 } k ^ { 3 } a ^ { 4 } } } \end{array}
$$

半波面高度到原点的距离为：

$$
H _ { h } = \frac { 1 } { 2 } ( H _ { c } + H _ { t } ) = \frac { 1 } { 2 } k a ^ { 2 } + k ^ { 3 } a ^ { 4 } + ( \frac { 1 } { 2 } k a ^ { 2 } + \frac { 1 1 } { 6 } k ^ { 3 } a ^ { 4 } ) + \frac { 1 } { 3 } k ^ { 3 } a ^ { 4 }
$$

半波面高度到静止水面的距离为：

$$
H _ { _ { r } } = H _ { _ { h } } - \ z _ { _ { 0 } } = { \frac { 1 } { 2 } } k a ^ { 2 } + { \frac { 1 1 } { 6 } } k ^ { 3 } a ^ { 4 } + { \frac { 1 } { 3 } } k ^ { 3 } a ^ { 4 }
$$

式(6)表明水面质点的振动中心不在静止水面上，而是高于静止水面，高出静止水面的距离约为 $H _ { _ { r } }$ ，20=2 =  ka²+ k'a4可以看作是高度计测得的平均海面，Hn可以看作是真实的平均海面，也就是高度计测得的平均海面会低于实际的平均海面，而真实的平均海面与高度计测得的平均海面之差就可以看作是电磁偏差，所以 $H _ { _ { r } }$ 也可以看作是四阶 Stokes 波理论得到的电磁偏差。

![](images/4b4defe546b15d33ddfcb16bf209259a5179a2103718d78ba1b619a8b6161371.jpg)  
图1.四阶Stokes波理论得到的电磁偏差 $H _ { r }$ 随波高 $H$ 和波周期 $T$ 的变化

图1(a)给出了当波周期 $T$ 固定为9s时， $H _ { _ { r } }$ 随波高 $H$ 的变化关系，当波周期 $T$ 固定时， $\boldsymbol { H } _ { r }$ 随波高 $H$ 的增大而增大；图 $1 ( \mathrm { b } )$ 给出了当波高 $H$ 固定为 $2 . 5 \mathrm { ~ m ~ }$ 时， $H _ { , }$ 随波周期 $T$ 的变化关系，当波高 $H$ 固定时， $H _ { , }$ （204号随波周期 $T$ 的增大而减小。而电磁偏差是海况偏差的最主要成分，所以图1也可以大致反映海况偏差与波长和波周期的关系。

以上提到的波浪是具有固定波高、周期的单一波浪，其波面形状是规则的，然而实际海面上的波浪都是不规则的，由不同波高和周期的单一波浪叠加而成。所以，在利用经验模型来估计海况偏差时，我们使用有效波高和平均波周期。

# 3已有的3维非参数海况偏差模型

# 3.13维非参数回归模型

假设y为因变量， $\pmb { x } = ( x _ { 1 } , x _ { 2 } , x _ { 3 } )$ 为自变量，那么一般的3维回归模型可以表示为：

$$
y = r ( { \pmb x } ) + e
$$

式中 $r ( { \pmb x } )$ 为回归函数， $e$ 为零均值的误差项，即 $E ( e ) = 0$ 。给定 $\mathbf { \Pi } _ { \mathrm { n } }$ 组观测值 $( y _ { i } , \pmb { x } _ { i } ) , i = 1 , 2 , . . . , n$ ，在 $\boldsymbol { x }$ 的邻域对回归函数 $r ( { \pmb x } )$ 进行一阶Taylor 展开有[12]：

$$
r ( z ) = b _ { _ 0 } + \mathsf { \Pi } _ { j = 1 } ^ { 3 } b _ { j } ( z _ { j } - x _ { j } )
$$

式中， $z$ 是一个在 $\boldsymbol { x }$ 的邻域含有3个变量的向量。通过找到一组 $\pmb { b } = { ( b _ { 0 } b _ { 1 } , b _ { 2 } , b _ { 3 } ) } ^ { \mathrm { T } }$ 使得式(9)最小:

$$
{ \operatorname * { j } _ { i = 1 } ^ { n } } [ { y _ { i } } - { b _ { 0 } } ^ { - } \ _ { j = 1 } ^ { 3 } { b _ { j } } ( { x _ { i } } _ { j } ^ { - } \ x \ ) ] ^ { 2 } { \cal K } _ { H } ( { x \cdot x } \ )
$$

这是典型的加权最小二乘回归问题， $\textbf { \textit { b } }$ 的估计值为

$$
\overset \vartriangle { b } = ( \boldsymbol { X } _ { D } ^ { \mathrm { ~ T ~ } } \boldsymbol { W } \boldsymbol { X } _ { D } ) ^ { \cdot 1 } \boldsymbol { X } _ { D } ^ { \mathrm { ~ T ~ } } \boldsymbol { W } \boldsymbol { y }
$$

我写 X11 X x12-x2 x13-x3式中， $\boldsymbol { { X } } _ { D } =$ 獨廄 X1-x1 （204 ${ x _ { } } _ { 2 2 } \ldots { x _ { } } _ { 2 }$ x23-χ,W=diag{Kn(x-x)）是一个(n’n)的加权矩阵，Kn(x-x)通M Mxn1-x x22-x2 xn3-x3

常是由核函数构成的概率密度函数。

$r ( { \pmb x } )$ 的局部线性回归估计器 $\oint _ { \mathrm { L L R } } ( x )$ 为 $\ S _ { o }$ ，而 $\ S$ 的其它成分是函数 $r$ 的一阶偏导数，即

$$
\oint _ { { \cal { I } } \mathrm { L } \mathrm { L } } ( { \bf { \mathcal { x } } } ) = \oint _ { { \cal { b } } _ { o } } = e _ { 1 } ^ { \mathrm { \scriptscriptstyle { T } } } ( X _ { _ { D } } ^ { \mathrm { \scriptscriptstyle { T } } } W X _ { _ { D } } ) ^ { \mathrm { \scriptscriptstyle { - 1 } } } X _ { _ { D } } ^ { \mathrm { \scriptscriptstyle { T } } } W y
$$

式中， $\mathbf { y } ^ { \mathrm { ~ T ~ } } = [ y _ { _ { 1 } } , y _ { _ { 2 } } , . . . , y _ { _ { n } } ]$ ， $\pmb { e } _ { 1 }$ 是一个单位向量， $\pmb { e } _ { 1 } ^ { \mathrm { ~ T ~ } } = [ 1 , 0 , 0 , 0 ]$ 。

3.2文献15,16]的3维非参数海况偏差模型

传统的非参数海况偏差模型主要是利用 $U$ 和 SWH作为模型输入的2维经验模型，文献[15,16]在2010年提出的3维非参数海况偏差模型采用 $U _ { : }$ SWH和MWP作为模型的输入[16]。如何提取SSB信息是建立SSB模型的关键，TRAN等人将未经 SSB 校正的瞬时海面高度减去通过平均海面模型得到的平均海面高度，从而得到未经SSB校正的海面高度异常值并从中提取SSB信息。

假设海况偏差 SSB 是 $\pmb { x } = ( U , \operatorname { S W H } , \operatorname { M W P } )$ 的函数 $g$ ，即 $\mathbf { S S B } = g ( \pmb { x } )$ ， $\mathrm { S S H } _ { i } ^ { ' }$ 表示未经 SSB 校正的海面高度，MSS表示由平均海面模型得到的平均海面， $y _ { i } = \mathrm { S S H } _ { i } ^ { ' }$ - MSS,表示未经 SSB 校正的海面高度异常值，由文献[15和文献[16]可知，观测方程可以写为：

$$
y _ { i } = ( \mathrm { S S B } ) _ { i } + e _ { i } = g ( \pmb { x } _ { i } ) + e _ { i }
$$

这样就得到了式(7)中典型的回归模型的表达式，给定 $\mathbf { \Pi } _ { \mathrm { n } }$ 组观测值 $( \boldsymbol { y } _ { i } , \boldsymbol { x } _ { i } )$ ，通过式(11)就可以得到任意 $\boldsymbol { x }$ 所对应的 SSB 估计值 $\ S _ { g ( \pmb { x } ) }$ 。

# 4基于交叉点数据的3维非参数海况偏差估计

# 4.1基于交叉点数据的3维非参数海况偏差估计方法

与文献[15,16]提取SSB信息的方法不同，本文从未经SSB校正的交叉点海面高度不符值中提取 SSB 信息。具体思路如下[7,12]：

SSH 表示未经 SSB校正的海面高度，在交叉点处，通过降轨和升轨的SSH相减，可以消除大地水准面中不随时间变化的部分，假设 SSB 是 $\pmb { x } = ( U , \operatorname { S W H } , \operatorname { M W P } )$ 的函数 $g$ ，即 $\mathbf { S S B } = g ( \pmb { x } )$ ，令 $y = \mathrm { S S H } _ { 2 } ^ { ' } { \cdot } \mathrm { S S H } _ { 1 } ^ { ' }$ ，根据文献 $[ 5 ]$ 和文献[10]，观测方程可以写为：

$$
y = g ( { \pmb x } _ { _ 2 } ) - \ g ( { \pmb x } _ { _ 1 } ) + e
$$

在给定 $\pmb { x } _ { 2 } = \pmb { x }$ 的条件下， $y$ 的条件期望为：

$$
E [ y \mid { \pmb x } _ { 2 } = { \pmb x } ] = g ( { \pmb x } ) - E [ g ( { \pmb x } _ { 1 } ) \mid { \pmb x } _ { 2 } = { \pmb x } ]
$$

根据非参数估计理论，条件期望 $r ( { \pmb x } ) = E [ { \pmb y } \mid { \pmb x } ]$ 的核估计器 $\$ 1$ 可以看作是一系列观测值 $y _ { i }$ 的加权平均：

$$
\ S _ { r ( \pmb { x } ) } = \sum _ { i = 1 } ^ { n } y _ { i } a _ { n } ( \pmb { x } - \ \pmb { x } _ { i } )
$$

权函数 $a _ { _ n } ( { \pmb x } - { \pmb x } _ { i } )$ 可以通过式(11)得到。在式(11)中，令 $\textbf { \textit { T } } = e _ { _ { 1 } } ^ { \mathrm { ~ T ~ } } ( \boldsymbol { X } _ { D } ^ { \mathrm { ~ T ~ } } W \boldsymbol { X } _ { _ D } ) ^ { - 1 } \boldsymbol { X } _ { D } ^ { \mathrm { ~ T ~ } } W$ ，可以得到权函数：

$$
a _ { _ n } ( { \pmb x } \cdot { \pmb x } _ { i } ) = { \pmb T } ( i )
$$

给定 $\mathbf { \Pi } _ { \mathrm { n } }$ 组观测值 $( \boldsymbol { y } _ { i } , \pmb { x } _ { 1 i } , \pmb { x } _ { 2 i } )$ ，利用式(14)和式(15)可以得到：

$$
g ( { \pmb x } ) = \operatorname * { \gamma } _ { i = 1 } ^ { \overset { n } { \underset { i \leq 4 } { \longrightarrow } } } { \operatorname * { \gamma } _ { i \leq 8 } ^ { \overset { n } { \underset { i } { \bigotimes } } } } { \operatorname * { \delta } _ { n } ( { \pmb x } - { \pmb x } _ { 2 i } ) } + \operatorname * { \gamma } _ { i = 1 } ^ { n } g ( { \pmb x } _ { 1 i } ) { \pmb u } _ { n } ( { \pmb x } - { \pmb x } _ { 2 i } )
$$

只要知道了 $g ( \pmb { x } _ { 1 i } )$ ，就可以得到任意 $\boldsymbol { x }$ 所对应的 $g ( \pmb { x } )$ ，将式(17)中的 $\boldsymbol { x }$ 替换为 $\pmb { x } _ { 1 j }$ ，可以得到：

$$
\begin{array} { r } { g ( \pmb { x } _ { 1 j } ) = \overset { \overset { n } { \hat { \lambda } } \overset { \leq \hat { \leq } } { \operatorname { i } } } { \underset { i = 1 } { \overset { \mathrm { n } } { \operatorname { i } } } } u _ { n } ( \pmb { x } _ { 1 j } - \pmb { x } _ { 2 i } ) + \overset { n } { \underset { i = 1 } { \overset { \mathrm { n } } { \operatorname { i } } } } g ( \pmb { x } _ { 1 i } ) u _ { n } ( \pmb { x } _ { 1 j } - \pmb { x } _ { 2 i } ) } \\ { \overset { \overset { } { \underset { i = 1 } { \overset { \mathrm { n } } { \operatorname { i } } } } } { \underset { i = 1 } { \overset { \mathrm { n } } { \operatorname { i } } } } \partial _ { i } \overset { \mathrm { n } } { \operatorname { i } } } \end{array}
$$

转化为矩阵的形式可以得到：

$$
{ \bf ( } I { \bf \nabla } - A { \bf ) } g _ { { \mathrm { 1 } } } = A { \bf y }
$$

式中 $\textbf { \textit { I } }$ 是 $( n ^ { \prime } n )$ 的单位矩阵， $A$ 也是 $( n ^ { \prime } n )$ 的矩阵，它的元素为 $a _ { _ { j i } } = a _ { _ n } ( \pmb { x } _ { _ { 1 j } } - \pmb { x } _ { _ { 2 i } } )$ 。${ \pmb g } _ { 1 } ^ { \top } = [ g ( { \pmb x } _ { _ { 1 1 } } ) , g ( { \pmb x } _ { _ { 1 2 } } ) , . . . , g ( { \pmb x } _ { _ { 1 n } } ) ] , ~ { \pmb y } ^ { \top } = [ y _ { 1 } , y _ { 2 } , . . . , y _ { n } ] \circ$

$\pmb { g } _ { 1 }$ 不能通过线性系统式(19)直接求得，因为 $_ { I \ - A }$ 是一个奇异矩阵，它的秩为 $\mathrm { \ n - 1 }$ ，为了消除这种不确定性，可以给 $\pmb { g } _ { 1 }$ 中的第1个元素强加一个值： $g ( \pmb { x } _ { 1 1 } ) = g _ { 0 }$ ，式(19)可以重写为:

$$
B _ { \vartheta } = A \mathbf { y } - \mathbf { \delta } B _ { \vartheta _ { 0 } }
$$

式中 $\pmb { g }$ 包含 $\pmb { g } _ { 1 }$ 中除 $g ( \pmb { x } _ { 1 1 } )$ 之外的 $\mathrm { n - 1 }$ 个元素， ${ \pmb g } ^ { \mathrm { T } } = [ g ( { \pmb x } _ { 1 2 } ) , . . . , g ( { \pmb x } _ { 1 n } ) ]$ ， $\boldsymbol { B } _ { _ { 0 } }$ 是 $\pmb { I } \ { - } A$ 的第 $^ { 1 }$ 列， $\pmb { B } _ { _ { 1 } }$ 是其余列,$\pmb { g }$ 的最小二乘解为：

$$
\begin{array} { r } { \pmb { \Sigma } = ( \pmb { B } _ { 1 } ^ { \top } \pmb { B } _ { 1 } ) ^ { - 1 } \pmb { B } _ { 1 } ^ { \top } ( \pmb { A } \pmb { y } - \pmb { B } _ { o } \pmb { g } _ { 0 } ) } \end{array}
$$

再联合 $g ( \pmb { x } _ { 1 1 } ) = g _ { 0 }$ ，就可以得到 $\pmb { g } _ { 1 }$ ，将它带入式(17)就可以得到任意 $\boldsymbol { x }$ 所对应的 $g ( \pmb { x } )$ 的估计 $\ S _ { g ( \pmb { x } ) }$ u

对于每一个输入变量 $\boldsymbol { x }$ ，要得到其对应的 SSB 估计值都需要经过大量的矩阵运算，这很难直接应用于高度计数据的实时处理当中，为了解决这个问题，可以制作一个SSB 估计值关于 $U _ { ☉ }$ SWH和MWP的3维查找表，分别计算查找表中每个网格点的输入变量 $\boldsymbol { x }$ 所对应的 SSB 估计值，再通过插值的方法得到任意高度计测量点的SSB估计值。

# 4.2两种3维非参数海况偏差估计方法的比较

利用海面高度异常数据估计 SSB 和利用交叉点数据估计 SSB的主要区别是获取SSB信息的方式不同，前者是从海面高度异常值中获取SSB信息，而后者是从交叉点的海面高度不符值中获取 SSB信息。与利用海面高度异常数据估计 SSB的方法相比，利用交叉点数据估计SSB的方法具有以下优势：

(1)海面高度异常值是高度计测得的瞬时海面高度与通过平均海面模型计算得到的平均海面高度之差，对于同一个平均海面模型，在某一个位置，平均海面高度是固定的，其中高度计的系统误差会影响 SSB 的测量结果，由于高度计的系统误差在交叉点数据获取过程中是不变的，通过在交叉点处将升轨和降轨的海面高度做差就可以消除这样的误差。

(2)计算海面高度异常值需要用到平均海面模型，平均海面模型是通过多个高度计多年测高数据平均得到，不同高度计所采用的数据处理方法有差异，所用到的误差校正方法也不一样，这些都会引入误差。同时，利用不同平均海面模型得到的 SSB 估计值也相差很大[14]；而利用交叉点的方法则没有这一问题。

# 5Jason2卫星高度计海况偏差估计

# 5.1交叉点数据处理

本文使用的平均波周期来自于欧洲中期天气预报中心(European Centre for Medium-range WeatherForecasts,ECMWF)再分析数据集 ERA-Interim，ERA-Interim 是ECMWF 的第s代全球再分析数据产品，提供了自1979 年以来的再分析资料，并实时更新。ERA-Interim 提供每天4个时刻的数据，分别在00：00,06：00，12:00和 18:00UTC，数据以网格的形式提供，本文使用数据的网格分辨率为0.25按 $0 . 2 \bar { \mathfrak { T } }$ 。ERA-Interim只提供每天4个时刻的数据，所以需要将数据在空间和时间上插值到高度计测量点处。本文采用先在空间上双线性插值，再在时间上线性插值的方法。本文用到的风速、有效波高以及计算海面高度所需要的数据都来源于 Jason-2卫星经过完全定标的D版本的GDR数据。Jason-2卫星于 2008年6月发射，它是TOPEX/POSEIDON,Jason-1测高卫星的后继星，被公认为目前测高精度最高的卫星。

利用交叉点数据和3维非参数模型估计 SSB 时需要用到风速、有效波高、平均波周期和交叉点处未经SSB 校正的海面高度不符值，需要把它们插值到交叉点处。本文采用三次样条插值的方法，只有在交叉点两侧各有4个连续的测量点时得到的交叉点才有效，这样可以保证较好的高度计数据质量。

# 5.2Jason-2海况偏差估计过程

在利用非参数估计方法估计 SSB 时，需要建立一个关于 $U ,$ SWH和MWP的3维查找表，图2给出了$U ,$ SWH和MWP的分布直方图，图中的结果是利用2011年全年的数据统计得到的。在本文所采用的查找表中， $U ,$ SWH和MWP 的取值范围分别为： $0 { \sim } 3 0 \mathrm { m } / \mathrm { s }$ $\mathrm { 0 } { \sim } 1 2 \mathrm { ~ m ~ }$ 和 $0 \mathrm { \sim } 1 8 \mathrm { ~ s ~ }$ 。在利用 $_ { 2 }$ 维非参数模型估计 SSB时，在得到 $\ S _ { g ( \pmb { x } ) }$ 后，需要整体减去 $\ S _ { \cal M } = 0 , \ S _ { \cal M \mathrm { H } } = 0 )$ ，使得 $\ S _ { \cal { Y } } ( U = 0 , \ S \mathrm { { W H } = 0 } ) = 0$ ，即平坦无风的海面的海况偏差为零。在利用‘维非参数模型估计 SSB 时，在得到 $\ S _ { g ( \pmb { x } ) }$ 后，本文采用将 $\ S _ { ( \pmb { x } ) }$ 整体减去$\ S _ { \mathbf { \Phi } } ( U = 0 , \mathrm { S W H } = 0 , \mathrm { M W P } = 9 s )$ 的方法得到最终的 SSB 估计值的查找表，选择 $\mathrm { \Delta M W P = 9 ~ s ~ }$ 是因为MWP 的平均值在9s附近。利用交叉点数据和3维非参数模型估计SSB的步骤如下：

步骤1 对单个重复周期(Cycle)的交叉点数据，假设一个 $g ( \pmb { x } _ { 1 1 } ) = g _ { 0 }$ ， $g _ { \mathrm { 0 } }$ 可以是任意一个合理的值，例如 $g _ { \mathrm { 0 } } =  { \mathrm { ~ \ - ~ } } 1 0  { \mathrm { c m } }$ 。

步骤通过式(21)得到 $\oint _ { \pmb { g } }$ ，联合 $g _ { \mathrm { 0 } }$ 得到 $\pmb { g } _ { 1 }$ 。  
步骤3 通过式(17)计算 $g ( \pmb { x } )$ 在( $U$ ，SWH，MWP)的三维网格的值，得到一个3维查找表。  
步骤 4 对每个Cycle的交叉点数据重复步骤 $^ { 1 }$ ，步骤 $_ { 2 }$ ，步骤3，再对所有Cycle 得到的结果取平均得到 $g ( \pmb { x } )$ 。

步骤 5在所有网格点，将计算得到的 $g ( \pmb { x } )$ 同时减去 $\overset { - } { g } ( U = 0 , \overset { \triangledown } { \mathbf { S } } \mathbf { W } \mathbf { H } = \ : 0 , \mathbf { M } \mathbf { W } \mathbf { P } = \ : 9 s )$ 就得到3维查找表中每个网格点所对应的SSB估计值。

步骤6在得到3维 SSB查找表后，根据沿轨任意一个测量点的 $U$ ，SWH和MWP，通过插值的方法得到该测量点的SSB估计值。

![](images/564e43b31bfdc9f75a291bd640c2bbc9a2c587b4a8797fdecfd12b9004cfc30c.jpg)  
图2风速U、有效波高SWH和平均波周期MWP的分布直方图

# 5.3Jason-2海况偏差估计结果

分别使用了2009,2010和 2011三年的交叉点数据和3维非参数模型得到SSB估计值(CR3D)，因为利用不同年份数据得到的 SSB 估计值相差不大，在数据密集区都在1cm 以下，这里仅以利用 2011年的数据得到的 SSB估计值的查找表作为参考。为了更好地表示结果，固定第3个输入参量，以 $_ { 2 }$ 维网格的形式给出SSB 估计值在各个平面的等值线分布,如图3所示,等值线的单位为 $\mathrm { c m } , 3$ 个固定值分别选在 $U _ { ☉ }$ SWH, MWP的平均值附近，这样可以保证在相应的平面有较多的测量点，3个固定值分别为： $\scriptstyle \mathrm { M W P = 9 }$ s, $\mathrm { U } { = } 7 . 5 \mathrm { m / s } ,$ （20（20 $\mathrm { S W H } { = } 2 . 5 \ \mathrm { m }$ 。图中阴影部分为测量点个数小于20的区域，代表数据稀疏区域，而图中白色部分代表数据密集区域，统计数据来源于2011年全年的数据，我们主要关心的是数据密集区域。

图 3(a)是在MWP等于9 s时，SSB 估计值在(U,SWH)平面的分布图，当MWP 固定时，和 $U$ 相比，SSB随 SWH的变化更为明显，在 $U$ 给定的条件下，SSB的幅值是SWH的递增函数，这和传统的利用基于 $U$ 和 SWH的2维非参数模型得到的结果[5,12,14]是一致的，也和图1(a)的结果吻合。图 $\boldsymbol { \mathscr { s } } ( \mathrm { b } )$ 是当 $U$ 等于 $7 . 5 ~ \mathrm { m / s }$ 时，SSB 估计值在(MWP,SWH)平面的分布图，当 $U$ 和 SWH固定时，SSB会随着MWP变化，MWP越大，SSB 的幅值越小。高度计的绝大部分有效测量点都在深水区，而在深水区，影响海面非线性的主要是波陡，在波高一定时，波周期越大，波陡越小，海面非线性越弱，海况偏差也就越小，所以得到的结果是合理的，也和图1(b)的结果吻合。 在数据密集区域，对于给定的 SWH，随着MWP 的变化，SSB 有约 $3 { \sim } 4 ~ \mathrm { c m }$ 的变化。图3(c)给出了当SWH等于 $2 . 5 \mathrm { ~ m ~ }$ 时，SSB估计值在(U,MWP)平面的分布图，在数据密集区域，当SWH固定时，SSB 随MWP的变化比随 $U$ 的变化更为明显，这表明MWP对SSB的影响比 $U$ 对 SSB的影响大，在其它条件都相同时，MWP越大，SSB的幅值越小。

![](images/d4e67e1285f320143d3c4bd92fa1e8c8e39e923b19357bf18540f47eefcfe1ab.jpg)

图3利用CR3D得到的 Jason-2 SSB 估计值(cm)在各平面的分布  
表1利用交叉点数据和3维非参数模型得到的 SSB估计值与Jason-2的GDR中的SSB校正项的比较  

<html><body><table><tr><td rowspan="2">SSB 估计值</td><td colspan="3">△SSH方差(cm2)</td><td colspan="3">SLA方差（cm2)</td></tr><tr><td></td><td>验证数据集</td><td></td><td></td><td>验证数据集</td><td></td></tr><tr><td></td><td>2009</td><td>2010</td><td>2011</td><td>2009</td><td>2010</td><td>2011</td></tr><tr><td>JA2GDR</td><td>25.16</td><td>25.44</td><td>25.39</td><td>44.66</td><td>46.21</td><td>49.64</td></tr><tr><td>2009 version,CRsD</td><td>23.62</td><td>23.83</td><td>23.85</td><td>43.95</td><td>45.39</td><td>48.45</td></tr><tr><td>2009 version, difference (CR3D - JA2GDR)</td><td>-1.54</td><td>-1.61</td><td>-1.54</td><td>-0.71</td><td>-0.82</td><td>-0.79</td></tr><tr><td>2010 version,CR3D</td><td>23.53</td><td>23.71</td><td>23.74</td><td>43.72</td><td>45.13</td><td>48.54</td></tr><tr><td>2010 version,difference (CRsD-JA2GDR)</td><td>-1.63</td><td>-1.73</td><td>-1.65</td><td>-0.94</td><td>-1.08</td><td>-1.10</td></tr><tr><td>2011version,CR3D</td><td>23.52</td><td>23.69</td><td>23.71</td><td>43.83</td><td>45.26</td><td>48.50</td></tr><tr><td>2011 version,difference (CRsD- JA2GDR)</td><td>-1.64</td><td>-1.75</td><td>-1.68</td><td>-0.83</td><td>-0.95</td><td>-1.04</td></tr></table></body></html>

注：表中△SSH方差表示交叉点海面高度不符值的方差，第1栏中的"JA2GDR"表示Jason-2的GDR产品中的SSB校正项，“2009 version,CR3D"表示利用2009年的交叉点数据和s维非参数模型得到的SSB估计值，"2009 version,diference (CR3D-JA2GDR）”所在的行表示相对于Jason-2的GDR 产品中 SSB 校正项，利用2009 年的交叉点数据和3维非参数模型得到的 SSB估计值所计算得到的△SSH或 SLA 的方差的减少量。

Jason-2的GDR产品中含有 SSB校正项，本文将利用交叉点数据和3维非参数模型得到的 SSB 估计值(CR3D)和 Jason-2 的GDR 产品中 SSB 校正项(JA2GDR)作比较，以此来评估利用本文所提出的 SSB 估计方法得到的 SSB 估计值。由于目前还不能直接利用卫星高度计自身测得的数据得到海况偏差的精度，所以通常是通过海况偏差校正对整个测高系统的贡献来评估SSB估计值。

海面高度不符值是最主要的用于分析整个测高系统性能的工具，通过海面高度不符值可以分析升轨和降轨的海面高度(Sea Surface Height,SSH)在交叉点处的一致性。在理想的条件下，交叉点海面高度不符值应该为零，但是由于轨道误差、地球物理校正误差和海洋波动等因素的影响，交叉点海面高度不符值通常不为零。交叉点海面高度不符值的方差可以估计整个测高系统的表现，其值越小，表明测高系统的整体表现越好[19,20]。从表1可以看出，和 Jason-2的GDR中的 SSB 校正项相比，在其它条件都相同时，CR3D 可以将海面高度不符值的方差降低 $1 . 5 4 { \sim } 1 . 7 5 ~ \mathrm { c m ^ { 2 } }$ ，平均降低了 $1 . 6 4 ~ \mathrm { c m ^ { 2 } }$ ，对应于 $1 . 2 8 ~ \mathrm { c m }$ 的均方根(RMS)海面高度。

沿轨海面高度异常(Sea Level Anomalies,SLA)也是估计测高系统整体表现的一个重要工具，沿轨 SLA 是通过沿轨的瞬时海面高度减去相应的平均海面得到，本文所用到的平均海面由CLS2011平均海面模型得到。沿轨 SLA 的方差可以用来监测测高系统的长期稳定性，其值越小表明测高系统的整体性能越好[19,20]。从表1可以看出，和 Jason-2的GDR中的 SSB 校正项相比，在其它条件都相同时，CR3D 可以将沿轨 SLA 的方差降低 $0 . 7 1 \sim 1 . 1 0 ~ \mathrm { c m } ^ { 2 }$ ，平均降低了 $\mathrm { 0 . 9 2 \ c m ^ { 2 } }$ ，对应于 $0 . 9 6 \mathrm { c m }$ 的均方根(RMS)海面高度。

综上所述，和Jason-2中的SSB校正项相比，CR3D可以大幅降低海面高度不符值的方差和沿轨 SLA的方差，这表明CR3D可以大幅提高雷达高度计的测高精度。

文献[15,16]的3维 SSB 模型是通过海面高度异常数据得到的，为了将利用本文方法得到的 SSB 估计值和利用文献[15,16]的3维 SSB 模型得到的 SSB 估计值进行比较，本文利用 2010 年的海面高度异常数据建立了一个3维 SSB 模型，并使用该模型得到了相应的 SSB 估计值(SLA3D)。图4给出了相对海面高度不符值的方差，它是通过分别利用CR3D 和 SLA3D 进行 SSB 校正后得到的海面高度不符值的方差减去利用JA2GDR进行 SSB校正后的海面高度不符值的方差得到。图5给出了相对沿轨 SLA方差，它是通过分别利用CR3D和SLA3D进行SSB校正后得到的沿轨SLA方差减去利用JA2GDR进行 SSB校正后的沿轨 SLA方差得到。图4和图5的结果都是利用 2011年(Cycle 93-Cycle 127)的数据通过每个Cycle 单独计算得到。从图4和图5可以看出，和JA2GDR相比，CR3D和 SLA3D都可以降低交叉点海面高度不符值的方差和沿轨SLA 的方差。而和 SLA3D 相比，利用CR3D得到的交叉点海面高度不符值的方差和沿轨 SLA的方差都更小，这也表明CR3D比 SLA3D 有更好的性能。

![](images/79987dfc340db99e9bf3d990d1059098a5e40fe9934d74726a9e3aa30879cb04.jpg)  
图4相对方差（CR3D 和 SLA3D 得到的海面高度不符值的方差-JA2GDR 得到的海面高度不符值的方差)

![](images/439bf5235abc2b217b88f846d5373852940d88da4307be285d90b2617155751f.jpg)  
图5相对方差（CR3D 和 SLA3D得到的 SLA的方差-JA2GDR得到的SLA的方差）

# 6结论

海况偏差由于其较大的不确定度已经成为雷达高度计测量海面高度最大的误差来源。传统的海况偏差校正采用以高度计测得的风速和有效波高为输入参量的2维经验模型，本文从非线性海浪理论的角度简单分析了波周期和海况偏差的大致关系，并联合ECMWF再分析数据集提供的平均波周期以及高度计测得的风速和有效波高，提出了一种利用交叉点数据和三维非参数模型估计海况偏差的方法。利用 Jason-2卫星雷达高度计 $2 0 0 9 { \sim } 2 0 1 1$ 三年的数据对得到的 SSB 估计值进行评估，和 Jason-2 的GDR产品中的 SSB 校正项相比,利用本文方法所得到的SSB估计值能将交叉点海面高度不符值的方差和沿轨 SLA方差分别降低 $1 . 6 4 ~ \mathrm { c m ^ { 2 } }$ 和 $\mathrm { 0 . 9 2 \ c m ^ { 2 } }$ ，分别对应于 $1 . 2 8 ~ \mathrm { c m }$ 和 $0 . 9 6 ~ \mathrm { c m }$ 的均方根(RMS)海面高度。而和现有的利用海面高度异常数据得到的3维 SSB 模型相比，利用本文方法所得到的3维 SSB 模型也具有更好的表现。由于ECMWF 的再分析数据已经被广泛应用于业务化雷达高度计二级数据处理，所以本文提出的海况偏差估计方法具有较强的实用性。

# 参考文献

[1]万珺之．基于有源定标器的海洋二号高度计系统延迟在轨绝对定标研究[D].[博士论文]，中国科学院国家空间科学中心,2015.WANJZ.StudyonHY-2altimetersystemdelayin-orbitabsolutecalbrationusingreconstructivetransponderD.Ph.DdiertationNational Space Science Center, Chinese Academy of Sciences, 2015  
[2]王磊．高精度卫星雷达高度计数据处理技术研究[D].「博士论文]，中国科学院国家空间科学中心,2015WANGL.StudyotedataproceingforghpisosatelitedaralieterD.DssratioatioalSpceSeeCteChinese Academy of Sciences,2015  
[3]王磊，许可，史灵卫，等．一种消除合成孔径雷达高度计延迟校正中残余误差的新算法及仿真验证[J]电子与信息学报,2015,37(1):2713-2718. doi: 10.11999/JEIT150282.WANGL,XUK,SLWetalgeigracoeoagoriditssilatioforRaltieter.JolofocsInformation Technology,2015,37(11): 2713-2718. doi: 10.11999/JEIT150282.  
[4]GHAVIDELA,SCHAVULLID,andCAMPSANumericalcomputationoftheelectromagneticbiasinGNS-RaltimetryJ].EEETransactions on Geoscience and Remote Sensing,2016,54(1):489-498.doi: 10.1109/TGRS.2015.2460212.  
[5] GASPARPandFLORENSJP.Estimationof thesea state bias inradar altimeter measurementsof sea level: Results fromanewnonparametricmethodJ.JournalofGeophysicalResearch-Oceans,1998，103(Co8):15803-15814.doi:10.1029/98JCo1194.  
[6] DUMONT J P, ROSMORDUC V, PICOT N, et al. OSTM/Jason-2 products book[R]. 2011.  
[7] GHAVIDELAandCAMPSA.Time-domainstatisticsof theelectromagneticbias inGNSS-ReflectometryJ]. Remte Sensing,015,7(1): 11151-11162.doi: 10.3390/rs70911151.  
[8] MILLETF W，WARNICK KF，NAGELJR，etal.Physicaloptics-basedelectromagneticbiastheorywith surface height-slopecros-correationandhyrodynamicmodulationJIEEETrasactionsonGeoscieceandRemoteSensing0，44(6):4748do10.1109/TGRS.2005.863852.  
[9]ELFOUOR,OtalpovedogticstrJualfesialRsecc2000,105(C1): 1299-1310.doi: 10.1029/1999JC900277.  
[10]ELFOUHAILYT，THOMPSON DR，CHAPRON D,etal. Improvedelectromagnetic bias theory:Inclusionof hydrodynamicmodulationsJ.Journal ofGeophysical Research-Oceans,2001,106(C3): 4655-4664.doi: 10.1029/199JCo00086.  
[11]CHELTODB.hesea-statebiasialtimeterstimatesofsea-levelfrocoliaranalsisftopxdataJJoualofGicalResearch-Oceans,1994,99(C12): 24995-25008.doi: 10.1029/94JC02113.  
[12]GASPARP,LABROUES,OGORF,etal. Improving nonparametric estimatesoftheseatatebias inadaraltimetermeasureentsof sea level[J]. Journal of Atmospheric and Oceanic Technology, 2002， 19(10):1690-1707. doi:10.1175/1520-0426(2002)019 $<$ 1690:INEOTS>2.0.CO;2.  
[13]GASPPGRF,etalEstatigthtateasfteseletersfooJournal ofGeophysical Research-Oceans,1994,99(C12): 24981-24994.doi: 10.1029/94JC01430.  
[14]LABROUES,GASPARP,DORANDEUJ,etalNonparametric estimatesofthesea state biasfortheJason-1radaraltieterJ].Marine Geodesy,2004,27(3-4): 453-481. doi: 10.1080/01490410490902089.  
[15]TRANNANDEMARKDCHAPRONB,etal.Newmodelsfrsatelitaltimetersstebiasorecondevelodusigglobalwave modeldataJ].JournalofGeophysical Research-Oceans,206,111(C9):141-152.doi:10.1029/2005JC003406.  
[16]TRANN,VANDEMARKD,LABROUES,etal.atatebias ialtimetersealevelstimates determinedbyombining waveodelandsatellte dataJ].JournalofGeophysicalResearch-Oceans,201,115 (Co302):1-7.doi:10.129/200JC005534.  
[17]苗洪利，王鑫，王桂忠，等.改进的高度计海况偏差估计参数模型研究[J]中国海洋大学学报(自然科学版),2015,4.5(12):119-124+130.doi: 10.16441/j.cnki.hdxb.20150125.MIAOHL,WANGX,WANGZ,etal.tudyontheimprovedsstatebiasparametricmodelJeriodicalofOceanUiestfCia(Science and Technology),2015,2015,45(12): 119-124+130.doi:10.16441/j.cnki.hdxb.20150125.  
[18]文圣常，余宙文.海浪理论与计算原理.北京：科学出版社,1984:95-115WEN S Hand YU Z W.Wave Theory and Calculation Principles. Beijing: Science Press,1984: 95-115  
[19]ABLtoisoi33(S1):162-185.doi: 10.1080/01490419.2010.487805.  
[20PRANDPPSGOV,etalRL/Altiagobalsatisticalessmentndo-calibationithJasorieGeodesy,2015,84(5): 297-312. doi: 10.1080/01490419.2014.995840.蒋茂飞：男，1989 年生，博士生，研究方向为雷达高度计数据处理.  
许可：男，1967年生，博士，研究员，博士生导师，主要研究方向为星载雷达高度计系统技术、合成孔径雷达高度计系统技术和信号处理技术.  
刘亚龙：男，1985年生，博士，研究方向为雷达高度计数据处理.  
王磊：男，1986 年生，博士，研究方向为雷达高度计信号处理