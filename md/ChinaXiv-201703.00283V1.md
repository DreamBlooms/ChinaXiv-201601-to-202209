# 一种改进的局部线性回归估计器及其在雷达高度计海况偏差估计中的应用

蒋茂飞①②③ 许可\*①② 刘亚龙④ 王磊①②①(中国科学院微波遥感技术重点实验室 北京100190)②(中国科学院国家空间科学中心 北京100190)③(中国科学院大学北京 100049)(国家海洋局烟台海洋环境监测中心站 烟台264000)

摘要：在建立雷达高度计海况偏差(Sea State Bias，SSB)非参数模型时，通常会用到局部线性回归(Local LinearRegression,LLR)估计器，而传统的局部线性回归估计器涉及高维矩阵运算，当建模的数据量较大时，估计海况偏差需要大量的时间，从而使得非参数估计方法很难用于高维海况偏差模型。该文提出一种改进的局部线性回归(Improved Local Linear Regression,ILLR)估计器，可以避免传统的LLR 估计器所需的高维矩阵运算，在不影响海况偏差估计结果的条件下，将局部线性回归估计器获取加权函数的时间复杂度由 $O ( N ^ { 2 } )$ 降低为 $O ( N )$ ，从而大幅地降低估计海况偏差所需的时间，为实现高维非参数海况偏差模型的实时运算奠定了基础。

关键词：雷达高度计；海况偏差；非参数估计；LLR估计器

中图分类号：TN953文献标识码：A 文章编号：

# Improved Local Linear Regression Estimator and Its Application to the Estimation for Radar Altimeter Sea State Bias

JIANG Maofei@②③ XU Ke@② LIU Yalong ④ WANG Lei@②

(Key Laboratory of Microwave Remote Sensing, Chinese Academy of Sciences, Beijing 1Ool9o, China) (National Space Science Center, Chinese Academy of Sciences,Beijing 10o19o, China) ③(University of Chinese Academy of Sciences,Beijing 10o049,China) ③Yntaist

Abstract: The Local Linear Regression (LLR) estimator is usually used when developing a nonparametric model for radar altimeter Sea State Bias (SSB). However,the conventional LLR estimator contains matrices with high dimension. Whena large numberof data are used to develop the SSB model,the SSB estimationcosts too much time.Therefore,the nonparametric estimation method can hardly be used to develop high-dimensional SSB models.This paper presents an improved LLR estimator,whichcan avoid high-dimensional matrix operations.The improved LLR estimatorcan greatly reduce the time for SSB estimation without afecting the estimated accuracy.So the improved LLR estimator can laid the foundation for high-dimensional SSB models.

Key words:Radar altimeter; Sea state bias;Nonparametric estimation; LLR estimator

# 1引言

全球海平面上升已越来越引起人们的关注，雷达高度计的一个重要应用就是测量平均海面高度[1,2]。但是由于海况偏差的存在，高度计测量得到的平均海面会低于实际的平均海面，必须对它进行校正。海况偏差主要是由于海面的非高斯分布特性引起，包括电磁偏差和偏斜度偏差[3]。利用现有方法得到的海况偏差的不确定度能够达到 $\mathrm { 2 c m [ ^ { 4 } ] }$ ，已经成为Jason 系列测高卫星最大的误差源[5,6]。

目前，业务化运行的雷达高度计的海况偏差校正主要采用以高度计测得的风速和有效波高作为输入的非参数 SSB 模型[6,7]。非参数 SSB 模型的构建通常需要用到局部线性回归估计器，而传统的局部线性回归估计器需要大量的矩阵运算，从而消耗大量的运算时间，极大地限制了非参数估计在高维SSB 模型中的应用。

本文提出了一种改进的局部线性回归估计器，该估计器避免了高维矩阵运算，将从局部线性回归估计器获取加权函数的时间复杂度由 $O ( N ^ { 2 } )$ 降低为 $O ( N )$ 。数值实验结果表明，在其它条件都相同的条件下，和传统的局部线性回归估计器相比，改进的局部线性回归估计器不会影响 SSB 估计的结果，但可以大幅地减低估计 SSB 所需的时间。

# 2局部线性回归估计器及其在海况偏差非参数估计中的应用

GASPAR等人[8]在1998年首次将非参数估计的方法用于SSB模型的构建，和参数模型[4,9]相比，非参数模型的精度更高，从而被更广泛地应用于高度计测量海面高度的海况偏差校正。用于非参数 SSB 模型的估计器主要有 Nadaraya-Watson (NW)估计器[8]和局部线性回归估计器[10]，NW 估计器在接近边界处会出现较大偏差，而局部线性回归估计器则可以很好解决这一问题[1,12]，所以局部线性回归估计器得到了更广泛的使用。

# 2.1局部线性回归估计器

给定N组观测值 $( \boldsymbol { y } _ { i } , \pmb { x } _ { i } )$ ， $\mathbf { \lambda } _ { \pmb { x } _ { i } }$ 是含有 $\mathrm { ~ \tt ~ p ~ }$ 个变量的向量， $\mathbf { \boldsymbol { x } } _ { i }$ 和 $y _ { _ i }$ 满足：

$$
y _ { _ i } = r ( \pmb { x } _ { _ i } ) + e _ { _ i }
$$

其中 $\boldsymbol { r }$ 是回归函数， $e _ { _ i }$ 是一个零均值的误差项。对于回归函数 $r ( { \pmb x } )$ ，在 $\boldsymbol { x }$ 的邻域 $z$ 对其进行Taylor 展开有：

$$
r ( \boldsymbol { z } ) = b _ { _ 0 } + \underset { j = 1 } { \overset { p } { \ a } } b _ { _ j } ( \boldsymbol { z } _ { _ j } - \boldsymbol { \ x } _ { _ j } )
$$

对于给定的 $\mathrm { \Delta N }$ 组观测值 $( y _ { i } , \pmb { x } _ { i } )$ ，可以通过加权最小二乘的方法找到一组 $\pmb { b } = ( b _ { 0 } , b _ { 1 } , . . . , b _ { _ p } ) ^ { \mathrm { T } }$ ，使得式 $( 3 )$ 最小：

$$
\underset { i = 1 } { \overset { N } { \sum } } [ \boldsymbol { y } _ { i } - \boldsymbol { b } _ { 0 } - \mathrm { ~ \boldsymbol ~ { ~ p ~ } ~ } _ { j } ^ { p } ( \boldsymbol { x } _ { i j } - \boldsymbol { x } _ { j } ) ] ^ { 2 } \boldsymbol { K } _ { \scriptscriptstyle H } ( \boldsymbol { x } _ { i } - \boldsymbol { x } )
$$

式中， $K _ { _ { H } } ( \pmb { x } _ { i } - \pmb { x } )$ 是加权函数，对于局部线性回归估计器， $K _ { _ { H } } ( \pmb { x } _ { i } - \pmb { x } )$ 通常选用核函数，常用的核函数有高

p-x 斯核函数和Epanechnikov核函数。令 $\boldsymbol { { X } } _ { D } =$ X 2p-xp $\pmb { y } ^ { \mathrm { ~ T ~ } } = [ y _ { _ 1 } , y _ { _ 2 } , . . . , y _ { _ N } ]$ 殿 M M $x _ { _ { N 1 } } - \ x _ { _ { 1 } } \mathrm { ~  ~ { ~ L ~ ~ } ~ } x _ { _ { N p } } - \ x _ { _ { p } }$

$W = \mathrm { d i a g } \{ K _ { \scriptscriptstyle H } ( { \pmb x } _ { \scriptscriptstyle i } - { \pmb x } ) \}$ 是一个 $( N ^ { \mathbf { \Omega } { } ^ { \prime } } \mathbf { \Omega } N )$ 的加权矩阵，式(3)可以改写为：

$$
( { \pmb y } \ { - } { \pmb X } _ { _ D } { \pmb b } ) ^ { \operatorname { T } } { \pmb W } \ ( { \pmb y } \ { - } { \pmb X } _ { _ D } { \pmb b } )
$$

最小化式(4)，可以得到：

$$
\pmb { \not p } ^ { \bot } = ( \pmb { X } _ { D } ^ { \mathrm { \scriptscriptstyle T } } \pmb { W } \pmb { X } _ { D } ) ^ { \circ } \overset { \mathrm { \scriptscriptstyle 1 } } { \pmb { X } } _ { D } ^ { \mathrm { \scriptscriptstyle T } } \pmb { W } \pmb { y }
$$

$r ( { \pmb x } )$ 的局部线性回归估计器 $\$ 123,456$ 为 $\pmb { \ b } _ { 0 } ^ { \mathrm { ~ \tiny ~ { ~ \chi ~ } ~ } }$ ，而 $\pmb { b } ^ { \mathrm { u } }$ 的其它成分是函数 $r$ 的一阶偏导数，即

$$
\oint _ { { \mathrm { \small L L R } } } ( { \bf x } ) = \big \bf R _ { \mathrm { \scriptsize ~ 0 } } ^ { \mathrm { \scriptsize ~ \mathrm { \large ~ \textmu ~ } } } = e _ { 1 } ^ { \mathrm { \scriptsize ~ \mathrm { \scriptsize ~ T } } } ( X _ { \cal D } ^ { \mathrm { \scriptsize ~ T } } W X _ { \cal D } ) ^ { \mathrm { \scriptsize ~ - \mathrm { \scriptsize ~ 1 } } } X _ { \cal D } ^ { \mathrm { \scriptsize ~ T } } W y
$$

式中 $\pmb { \mathscr { e } } _ { 1 }$ 是一个含有 $\mathrm { { p } } { + } 1$ 个变量的单位向量， $\pmb { e } _ { 1 } ^ { \textup { T } } = [ 1 , 0 , . . . , 0 ]$ 。

对于给定的 $\mathrm { ~  ~ N ~ }$ 组观测值 $( y _ { i } , \pmb { x } _ { i } )$ ，根据非参数估计理论，条件期望 $E [ y \mid x ]$ 表示在给定 $\boldsymbol { x }$ 的条件下 $y$ 的均值，其核估计器 $\$ 1$ 可以看作是观测值 $y _ { i }$ 的加权平均：

$$
\mathring { \mathbb { P } } ( { \pmb x } ) = \mathring { \underset { i = 1 } { \overset { N } { \ b \bigcirc } } } y _ { i } { a } _ { N } ( { \pmb x } - { \pmb x } _ { i } )
$$

对于局部线性回归估计器 $\oint _ { \mathrm { L L R } } ( x )$ ，在式(6)中，令 $\textbf { \textit { T } } = e _ { \mathrm { ~ 1 ~ } } ^ { \mathrm { ~ T ~ } } ( \textbf { \textit { X } } _ { D } ^ { \mathrm { ~ T ~ } } W \textbf { \textit { X } } _ { D } ) ^ { \mathrm { ~ - ~ } 1 } \textbf { \textit { X } } _ { D } ^ { \mathrm { ~ T ~ } } W$ ，就可以得到权函数：

$$
a _ { \scriptscriptstyle N } ( { \pmb x } - { \pmb x } _ { i } ) = { \pmb T } ( i )
$$

2.2局部线性回归估计器在海况偏差非参数估计中的应用

通常使用交叉点处的海面高度不符值来建立SSB模型,卫星绕地球运行一周的轨迹包括两个弧段(Pass)，分别为上升轨道和下降轨道，上升轨道和下降轨道的交点就称为交叉点，而交叉点海面高度不符值是指上升轨道和下降轨道在交叉点处测得的海面高度之差[13]。

SSH 表示未经 SSB 校正的海面高度测量值，假设 SSB 是输入变量 $\pmb { x } = ( U , \mathrm { S W H } )$ 的函数 $j$ ，并令$y = \mathrm { S S H } _ { 2 } ^ { ' }$ ， $\mathrm { S S H } _ { \mathrm { 1 } } ^ { \mathrm { ' } }$ ，根据文献[8]和文献[10]可知：

$$
y = j \ ( { \pmb x } _ { 2 } ) - j \ ( { \pmb x } _ { 1 } ) + e
$$

式中， $e$ 是一个零均值的误差项，角标1和角标 $_ { 2 }$ 分别对应上升轨道和下降轨道。在给定 $\pmb { x } _ { 2 } = \pmb { x }$ 的条件下,

$y$ 的条件期望为：

$$
E [ y \mid { \pmb x } _ { 2 } = { \pmb x } ] = j \ ( { \pmb x } ) - \ E [ j \ ( { \pmb x } _ { 1 } ) \mid { \pmb x } _ { 2 } = { \pmb x } ]
$$

对于 $\mathrm { ~  ~ { ~ N ~ } ~ }$ 组测量值 $( \boldsymbol { y } _ { i } , \pmb { x } _ { 1 i } , \boldsymbol { x } _ { 2 i } )$ ，利用式（7）和式（10）可以得到：

$$
\begin{array} { r } { j \mathbf { \Sigma } ( \pmb { x } ) = \underset { i = 1 } { \overset { N _ { \pm \pm } } { \mathrm { I } } } \underset { i } { \overset { N _ { i } \pmb { \Sigma } } {  } } \underset { i } { \overset { N } { \operatorname { \Sigma } } } a _ { N } ( \pmb { x } - \pmb { x } _ { 2 i } ) + \underset { i = 1 } { \overset { N } { \operatorname { \Sigma } } } j \mathbf { \Sigma } ( \pmb { x } _ { 1 i } ) a _ { \scriptscriptstyle N } ( \pmb { x } - \pmb { x } _ { 2 i } ) } \end{array}
$$

式(11)给出了估计 ${ \dot { \boldsymbol { j } } } \left( \pmb { x } \right)$ 的方法，只要知道了 $j ~ ( \pmb { x } _ { _ { 1 i } } )$ ，就可以估计出任意输入 $\boldsymbol { x }$ 所对应的 SSB 估计值 $j \left( { \pmb x } \right)$ 。利用 $\boldsymbol { \mathscr { x } } _ { 1 j }$ 替换式(11)中 $\boldsymbol { x }$ ，式(11)可以重写为：

$$
\textit { j } ( \pmb { x } _ { 1 j } ) = \overset { \underset { 1 \leq j } { \mathrm { M a x } } } { \overbrace { \lambda } } y _ { i } a _ { N } ( \pmb { x } _ { 1 j } - \pmb { x } _ { 2 i } ) + \overset { N } { \underset { i = 1 } { \mathrm { M } } } j ( \pmb { x } _ { 1 i } ) a _ { N } ( \pmb { x } _ { 1 j } - \pmb { x } _ { 2 i } ) , ^ { \ast } j = 1 , . . . , N
$$

将式(12)转化为矩阵的形式可以得到：

$$
( \pmb { I } - \pmb { A } ) \pmb { j } _ { _ { 1 } } = \pmb { A } \pmb { y }
$$

式中， $\textbf { \textit { I } }$ 和 $A$ 都是 $( N ^ { \mathbf { \Omega } { } ^ { \prime } } \mathbf { \Omega } N )$ 的矩阵，矩阵 $\boldsymbol { { I } }$ 是一个单位矩阵，而矩阵 $A$ 的元素为 $a _ { _ { j i } } = a _ { _ { N } } ( \pmb { x } _ { _ { 1 j } } - \pmb { x } _ { _ { 2 i } } )$ ，$\pmb { j } _ { \textsc { i } } ^ { \textsc { i } } = [ j \ ( \pmb { x } _ { _ { 1 1 } } ) , j \ ( \pmb { x } _ { _ { 1 2 } } ) , . . . , j \ ( \pmb { x } _ { _ { 1 N } } ) ] , \ \pmb { y } ^ { \textsc { i } } = [ y _ { _ { 1 } } , y _ { _ { 2 } } , . . . , y _ { _ { N } } ] \circ$

矩阵 $\pmb { I } - \pmb { A }$ 是一个奇异矩阵，其秩为 N-1。为了消除不确定性，可以先给 $\textit { \textbf { j } } _ { 1 }$ 中的第一个元素一个假设值： $\textit { j } ( \pmb { x } _ { _ { 1 1 } } ) = \boldsymbol { j } _ { \mathrm { ~ 0 ~ } }$ ，那么式(13)可以重写为:

$$
\boldsymbol { B } \boldsymbol { j } ^ { \mathrm { ~ } } = \boldsymbol { A } \boldsymbol { y } - \boldsymbol { B } _ { \mathrm { ~ } \mathrm { ~ } } \boldsymbol { j } ^ { \mathrm { ~ } } ,
$$

式中， $j$ 包含 $\textbf { \textit { j } } _ { 1 }$ 除 $j \left( \pmb { x } _ { 1 1 } \right)$ 之外的 $\mathbf { N } _ { - 1 }$ 个元素，即j ${ \bf \Pi } ^ { \mathrm { ~ T ~ } } = [ j { \bf \Pi } ( { \pmb x } _ { _ { 1 2 } } ) , . . . , j { \bf \Pi } ( { \pmb x } _ { _ { 1 N } } ) ]$ ， $\boldsymbol { B } _ { 0 }$ 是矩阵 $\pmb { I } - \pmb { A }$ 的第1列， $\pmb { B } _ { 1 }$ 是其余各列组成的矩阵，利用最小二乘法求解j：

$$
\pmb { j } ^ { \mu } = ( \pmb { B } _ { 1 } ^ { \mathrm { ~ T } } \pmb { B } _ { 1 } ) ^ { - 1 } \pmb { B } _ { 1 } ^ { \mathrm { ~ T } } ( \pmb { A } \pmb { y } - \pmb { B } _ { \theta } \pmb { j } _ { 0 } )
$$

再联合 ${ j \bf \Pi } ( { \pmb x } _ { _ { 1 1 } } )$ ，就可以得到 $\mid j _ { \mathbf { \alpha } _ { 1 } }$ ，将它带入式(11)就可以得到任意 $\boldsymbol { x }$ 所对应的 $j \left( { \pmb x } \right)$ 的估计值。

在估计SSB时，可制作一个SSB估计值关于风速U、有效波高 SWH的 $\mathbf { \varepsilon } _ { 2 }$ 维查找表，再通过插值的方法得到任意高度计测量点的 SSB 估计值。为了得到 SSB 估计值的查找表，通常是先利用一个cycle 的数据计算查找表中每个网格点的输入变量 $\boldsymbol { x }$ 所对应的 SSB 估计值 $j \left( { \pmb x } \right)$ ，再对多个cycle得到的结果进行平均。每个cycle 的交叉点的有效个数一般可达 $5 0 0 0 { \sim } 7 0 0 0$ 个，如果将所有交叉点都用于建模，那么式(15)中矩阵求逆需要大量的运算，消耗大量计算时间。在文献[8的模型中，从每个cycle 随机抽取 500 个有效的交叉点来建立 SSB 估计模型。为了避免了式(15)中矩阵求逆运算，GASPAR等人[10]在 2002 年利用LSQR 算法来求线性方程式(14)的解，并将每个cycle 的所有交叉点数据都用于 SSB 的建模。LSQR 算法是 PAIGE 等人[14]在1982 年提出的一种解稀疏线性方程组的迭代方法，它被用于求线性方程组 $A x = b$ 的解或者使 $\left\| A x - b \right\| _ { 2 }$ 最小的解。为了进一步提高求解线性方程式(14)的速度，本文使用了LSMR 算法来解方程式(14)，LSMR 算法是FONG 等人[15]在 2010 年提出的一种解线性方程组的迭代算法。和 LSQR 算法一样，LSMR 算法也是用于求线性方程组 $A x = b$ 的解或者使 $\left\| A x - b \right\| _ { 2 }$ 最小的解，但和 LSQR 算法相比，使用 LSMR 算法可以更快和更安全的达到收敛条件。

# 2.3改进的局部线性回归估计器

非参数 SSB 模型最终得到的是一个关于风速U和有效波高 SWH的2维查找表，需要计算查找表中每个网格点的输入 $\pmb { x } = ( U , \mathrm { S W H } )$ 所对应的 SSB 估计值。虽然利用LSQR 和LSMR 算法来解线性方程式(14)可以避免式(15)式矩阵求逆运算，但式(11)中的加权函数 $a _ { \scriptscriptstyle N } ( { \pmb x } - { \pmb x } _ { _ { 2 i } } )$ 和式(12)中加权矩阵A中的元素（20 $a _ { \scriptscriptstyle N } ^ { \mathrm { ~ ~ } } ( { \pmb x } _ { { \scriptscriptstyle 1 j } } - { \pmb x } _ { { \scriptscriptstyle 2 i } } )$ 都是通过局部线性回归估计器得到，从式(5)和式(8)也可以看出通过局部线性回归估计器得到加权函数时也需要用到高维矩阵运算，本文希望避免高维矩阵运算，在对结果影响不大的条件下，能大大降低运算时间。

对于传统的利用风速(U)和有效波高(SWH)来建立 SSB 估计模型时， $\pmb { x } = ( x _ { 1 } , x _ { 2 } ) = ( U , \mathrm { S W H } )$ ， $z$ 在 $\boldsymbol { x }$ 的邻域，回归函数 $r$ 的局部线性模型可以表示为：

$$
r ( z ) = b _ { { \mathrm { 0 } } } + b _ { { \mathrm { 1 } } } ( z _ { 1 } - x _ { 1 } ) + b _ { { \mathrm { 2 } } } ( z _ { 2 } - x _ { 2 } )
$$

通过找到 $\pmb { b } = { ( b _ { 0 } , b _ { 1 } , b _ { 2 } ) } ^ { \mathrm { T } }$ ，使得式(17)的函数最小：

$$
Z = \underset { i = 1 } { \overset { N } { \mathrm { \Large ~ \alpha ~ } } } \left[ y _ { i } \cdot \textit { b } _ { \mathrm { \Large ~ 0 } } - \textit { b } _ { \mathrm { \Large ~ 1 } } ( x _ { i 1 } - \textit { x } _ { \mathrm { \Large ~ 1 } } ) - \textit { b } _ { \mathrm { \Large ~ 2 } } ( x _ { i 2 } - \textit { x } _ { \mathrm { \Large ~ 2 } } ) \right] ^ { \mathrm { \Large ~ 2 } } K _ { \scriptscriptstyle _ { H } } ( { \pmb { x } } _ { i } - { \pmb { x } } )
$$

$\frac { \ P Z } { \ P b _ { \ _ } } = \ 0 , \frac { \ P Z } { \ P b _ { \ _ } } = \ 0 , \frac { \ P Z } { \ P b _ { \ _ } } = \ 0$ ，那么可以得到一个方程组：

$$
\begin{array} { r } { { S } _ { _ { 0 0 } } b _ { _ { 0 } } + { S } _ { _ { 1 0 } } b _ { _ { 1 } } + { S } _ { _ { 0 1 } } b _ { _ { 2 } } = a _ { \pm } ^ { \dagger } } \\ { { S } _ { _ { 1 0 } } b _ { _ { 0 } } + { S } _ { _ { 2 0 } } b _ { _ { 1 } } + { S } _ { _ { 1 1 } } b _ { _ { 2 } } = b _ { \mathbf { V } } ^ { \dagger } } \\ { { S } _ { _ { 0 1 } } b _ { _ { 0 } } + { S } _ { _ { 1 1 } } b _ { _ { 1 } } + { S } _ { _ { 0 2 } } b _ { _ { 2 } } = c _ { \dot { \mathbf { p } } } ^ { \dagger } } \end{array}
$$

其中，a,b,c 和 $S _ { m n }$ 可以表示为：

$$
\begin{array} { r l } { \boldsymbol { a } } & { = \frac { \displaystyle \sum _ { i } ^ { N } { \boldsymbol { y } } _ { i } K _ { H } ( { \boldsymbol { x } } \cdot { \boldsymbol { x } } _ { i } ) } { \displaystyle \sum _ { i = 1 } ^ { N } { \boldsymbol { y } } _ { i } K _ { H } ( { \boldsymbol { x } } \cdot { \boldsymbol { x } } _ { i } ) } } \\ { \boldsymbol { b } } &  = \frac { \displaystyle \sum _ { i = 1 } ^ { N } { \boldsymbol { y } } _ { i } \left( { \boldsymbol { x } } _ { i 1 } \cdot { \boldsymbol { x } } _ { 1 } \right) { \boldsymbol { K } } _ { H } ( { \boldsymbol { x } } \cdot { \boldsymbol { x } } _ { i } ) } \\ { \boldsymbol { c } } &  = \frac { \displaystyle \sum _ { i = 1 } ^ { N } { \boldsymbol { y } } _ { i } \left( { \boldsymbol { x } } _ { i 2 } \cdot { \boldsymbol { x } } _ { 2 } \right) { \boldsymbol { K } } _ { H } ( { \boldsymbol { x } } \cdot { \boldsymbol { x } } _ { i } ) } \\ { \boldsymbol { N } } & { } \\  \displaystyle S _ { m n } = \frac { \displaystyle \sum _ { i = 1 } ^ { N } { \left( { \boldsymbol { x } } _ { i 1 } \cdot { \boldsymbol { x } } _ { 1 } \right) ^ { m } \left( { \boldsymbol { x } } _ { i 2 } \cdot { \boldsymbol { x } } _ { 2 } \right) ^ { n } { \boldsymbol { K } } _ { H } ( { \boldsymbol { x } } \cdot { \boldsymbol { x } } _ { i } ) \frac { \mathrm { ~ \boldsymbol { x } } _ { i } } { \displaystyle \sum _ { j = 1 } ^ { N } { \boldsymbol { y } } _ { i } } } } \end{array}
$$

至 mpO $S _ { _ { 1 0 } }$ （20 $S _ { \mathrm { 0 1 } }$ 令 $s =$ $S _ { _ { 2 0 } }$ $S _ { _ { 1 1 } }$ ，方程组式(18)可以表示为 $S b =$ （204号 ，这里用伪逆来求b：漫1 电 $S _ { \scriptscriptstyle { 1 1 } }$ $S _ { _ { 0 2 } }$

令 $Q = e _ { \mathrm { \scriptscriptstyle ~ l } } ^ { \mathrm { \scriptscriptstyle ~ T } } \operatorname { \mathrm { ? p i n v } } ( S )$ ，那么

$$
\begin{array} { r l } & { \pmb { \dot { b } } _ { 0 } ^ { 1 } = \pmb { Q } ( 1 ) \geq a \quad \pmb { Q } ( 2 ) \geq b \quad \pmb { Q } ( 3 ) \geq c } \\ & { \qquad = \underset { i = 1 } { \overset { N } { \sum } } \frac { \hbar \pmb { \hat { z } } } { 2 \pmb { \hat { z } } } ( 1 ) + \pmb { Q } ( 2 ) \operatorname { \hat { z } } ( x _ { i 1 } \quad x _ { 1 } ) + \pmb { Q } ( 3 ) \operatorname { \hat { z } } ( x _ { i 2 } \quad x _ { 2 } ) K _ { \ b { H } } ( \pmb { x } _ { i } - \pmb { x } ) \operatorname { \hat { z } } y _ { i } } \end{array}
$$

所以，权值函数可以表示为：

$$
a _ { _ N } ( { \pmb x } _ { i } \cdot { \pmb x } ) = \mathinner { \operatorname * { \arg } _ { \pmb { \hat { \mathbb { B } } } \pmb { \hat { \mathbb { B } } } } } ( 1 ) + Q ( 2 ) \mathinner { \gamma \mathopen { ( { \pmb x } _ { i 1 }  \kern - delimiterspace } { \pmb x } _ { _ { 1 } } ) } + Q ( 3 ) \mathinner { \gamma \mathopen { ( { \pmb x } _ { i 2 }  \kern - delimiterspace } { \pmb x } _ { _ { 2 } } ) } ~ K _ { _ { H } } ( { \pmb x } _ { i } \cdot { \pmb x } )
$$

将式(23)替换到式(8)，就可以将 ILLR 估计器用于非参数 SSB 模型的构建，和LLR估计器相比，ILLR 估计器避免了高维矩阵运算。

由式(8)和式(23)可知，两种估计器得到的权函数有所区别，ILLR 估计器和LLR 估计器在本质上是相同的，都是通过对式(3)求偏导，并使其偏导为零得到，如果将式 $( 5 )$ 重写为 $X _ { _ { \mathrm { D } } } ^ { \mathrm { { \mathrm { T } } } } W X _ { _ { D } } b = X _ { _ { D } } ^ { \mathrm { { T } } } W y$ ，其展开后就得到了式(18)，所以只要 $X _ { _ D } ^ { ^ \mathrm { { T } } } W X _ { _ D }$ 不是奇异矩阵，ILLR 估计器和 LLR 估计器得到的结果就完全相同。在LLR 估计器中，由于W是对角矩阵， $X _ { \mathbf { \delta } _ { D } } ^ { \mathrm { ~ T ~ } } W$ 和 $X _ { \cal D } ^ { \mathrm { \tiny ~ T } } { \cal W }$ 在运算过程中会产生很多结果为零值,它们会继续参与$X _ { _ D } ^ { ^ \mathrm { \tiny ~ T } } W X _ { _ D }$ 和 $X _ { _ D } ^ { \mathrm { ~ T ~ } } W _ { } y$ 的矩阵运算，而在ILLR 估计器中，LLR 估计器中 $X _ { _ D } ^ { ^ \mathrm { \tiny ~ T } } W X _ { _ D }$ 和 $X _ { _ D } ^ { \mathrm { ~ T ~ } } W _ { } y$ 在计算过程中产生的那些中间结果为零的值不会参与式(18)，式(9)的运算，这就大大节约了计算时间。从算法时间复杂度方面分析，在LLR 估计器中，权函数 $a _ { \scriptscriptstyle N } ( { \pmb x } _ { \scriptscriptstyle i } - { \pmb x } )$ 由 $\pmb { T } = \pmb { e } _ { 1 } ^ { \intercal } ( \pmb { X } _ { D } ^ { \intercal } \pmb { W } \pmb { X } _ { D } ) ^ { \intercal } \ : ^ { 1 } \pmb { X } _ { D } ^ { \intercal } \pmb { W }$ 得到， $\pmb { e } _ { 1 } ^ { \textup { T } }$ 是 $( 1 ^ { \prime } 3 )$ 的矩阵， $\boldsymbol { { X } } _ { D }$ 是$( N ^ { \cdot } ~ 3 )$ 的矩阵， $W$ 是 $( N ^ { \mathbf { \Omega } { } ^ { \prime } } \mathbf { \Omega } N )$ 的矩阵， $X _ { \mathbf { \delta } _ { D } } ^ { \mathrm { ~ T ~ } } W$ 是 $( 3 ^ { \prime } N )$ 的矩阵， $X _ { _ D } ^ { ^ \mathrm { T } } W X _ { _ D }$ 是 $( 3 ^ { \prime } 3 )$ 的矩阵，所以 $\boldsymbol { X } _ { \Dot { \boldsymbol { D } } } ^ { \mathrm { ~ T ~ } }$ 和W相乘需要 $3 N ^ { 2 }$ 次乘法运算， $\smash { \boldsymbol { X } _ { D } ^ { \mathrm { ~ T ~ } } \boldsymbol { W } }$ 和 $\boldsymbol { { X } } _ { D }$ 相乘需要 $3 ^ { 2 } N$ 次乘法运算，矩阵 $X _ { _ D } ^ { ^ \mathrm { \tiny ~ T } } W X _ { _ D }$ 求逆需要 $3 ^ { 3 }$ 次乘法运算，$( \pmb { X } _ { D } ^ { \operatorname { T } } \pmb { W } \pmb { X } _ { D } ) ^ { - 1 }$ 和 $\smash {  { \boldsymbol { X } } _ { D } ^ { \mathrm { \scriptscriptstyle T } }  { \boldsymbol { W } } }$ 相乘需要 $3 ^ { 2 } N$ 次乘法运算， $\pmb { e } _ { 1 } ^ { \textup { T } }$ 和 $( \boldsymbol { X } _ { D } ^ { \mathrm { ~ T ~ } } \boldsymbol { W } \boldsymbol { X } _ { D } ) ^ { \mathrm { ~ - ~ } 1 } \boldsymbol { X } _ { D } ^ { \mathrm { ~ T ~ } } \boldsymbol { W }$ 相乘需要3N 次乘法运算，所以利用 LLR 估计器获得权函数的时间复杂度为 $\mathrm { O } ( N ^ { 2 } )$ 。由式(18)可知，计算a, $\mathbf { b }$ ， $\mathrm { ~  ~ \bar { ~ } { ~ c ~ } ~ }$ 和 $S _ { m n }$ 分别需要进行N，2N,2N和 $( m + n + 1 ) ? N$ 次乘法运算， $s$ 是 $( 3 ^ { \prime } 3 )$ 的矩阵，所以利用ILLR 估计器获得权函数的时间复杂度为$\mathrm { O } ( N )$ 。

# 3数值实验

# 3.1数据来源和处理

本文使用 Jason-2 高度计的地球物理数据集(GDR)产品，Jason-2 卫星于 2008 年6月发射，它是TOPEX/POSEIDON、Jason-1 测高卫星的后继星，被公认为目前精度最高的测高卫星。本文在建立非参数SSB 模型时使用了cycle $5 1 \sim 1 0 0$ 共 50个cycle 的数据，而在评估ILLR 估计器对 SSB 估计结果的影响时使用了 2009(cycle19\~cycle55)， 2010(cycle56\~cycle92)和 2011(cycle93\~cycle128)共 3 年的数据。

建立 SSB模型需要用到风速、有效波高、交叉点处未经SSB校正的海面高度不符值。计算海面高度所需的各种校正项都需要插值到交叉点处，本文采用3次样条插值的方法，为了得到更好的插值效果，只有在交叉点两侧各有4个连续的测量点时得到的交叉点才有效，这样可以保证较好的高度计数据质量。

# 3.2核函数和带宽的选择

核函数和带宽的选择对于非参数 SSB 模型非常重要。目前，最常用的核函数有高斯核函数和Epanechnikov核函数，而用于非参数 SSB 模型的带宽包括全局带宽和局部带宽两种，全局带宽是指对于所有的输入 $\pmb { x } = ( U , \mathrm { S W H } )$ ，风速的带宽 $h _ { { } _ { U } }$ 和有效波高的带宽 $h _ { \mathrm { { s w H } } }$ 都为固定值，而局部带宽是指 $h _ { { } _ { U } }$ 和 $h _ { \mathrm { { s w H } } }$ 会根据数据密度自动进行调节。

和高斯核函数相比，Epanechnikov 核函数可以将线性系统式(14)中矩阵 $\pmb { { B } } _ { 1 }$ 转换稀疏矩阵，从而大大提高了计算效率，但在数据稀疏区域估计的效果比较差。和全局带宽相比，局部带宽可以根据数据的密集程度调节带宽，从而在数据稀疏区域优势较为明显。本文的数值实验只是为了评估改进的局部线性估计器的计算效率以及对估计结果的影响，所以对核函数和带宽的选择没有太多的要求。本文采用了两种核函数和带宽的组合，第1种是采用高斯核函数和全局带宽，对应于文献[10]的模型，第2种是 Epanechnikov 核函数和局部带宽，对应于文献[12]的模型。

# 3.3实验结果

# 3.3.1LLR估计器和ILLR估计器估计SSB 效率比较

首先比较利用LLR估计器和ILLR估计器估计 SSB所用的时间，表1给出了利用高斯函数和全局带宽得到的结果，随着每次用于 SSB估计的交叉点数N的增大，LLR估计器里的矩阵的维度就相应地增大，所需的计算时间也会明显增大。ILLR估计器中矩阵的维度不会随着N的增大而改变，虽然其所需的时间也会随着 N 的增大而增大，但其增大的幅度相对较小。表2给出了利用 Epanechnikov 核函数和局部带宽估计 SSB所用的时间，正常情况下，Epanechnikov 核函数可以将线性系统式(14)中的矩阵 ${ \bf B _ { 1 } }$ 转换为稀疏矩阵，从而提高计算效率，降低估计 SSB 所需的时间，但由于采用了局部带宽，在估计 SSB时，对于每一输入 $\boldsymbol { x }$ ，都需要先确定其所在网格所对应的带宽，这样就会增加计算量，从而使得计算时间增大。和表1一样，随着 N的增大，利用LLR估计器估计 SSB 所需的计算时间大幅增加，而利用 ILLR估计器估计 SSB 所需的计算时间增幅相对较小。从表1和表2可以看出，和LLR估计器相比，利用ILLR估计器大可以大幅度地降低估计 SSB 所需的时间，N 越大，改进的效果越明显。

非参数 SSB模型最终得到的是一个关于U和SWH的查找表，需要计算每个查找表中每个网格点所对应的 SSB 估计值，通过U和 SWH 只能得到有限的 SSB 的信息，将新的参量(如波周期参数)引入 SSB 模型的构建已经成为 SSB 估计的一个新的研究方向[6,16,17]。在建立高维非参数 SSB 模型时，最终得到的结果将是一个高维查找表，其所对应的网格点数将远远多于2维查找表的网格点数，使用LLR估计器所需消耗的时间将非常巨大，并且随着维度的增加，必须要有更多的数据参与模型的构建才能保证模型的有效性，这对于LLR估计器是巨大的挑战，而ILLR估计器则可以很好地解决这一问题。

表1利用高斯核函数和全局带宽估计SSB所用的时间  

<html><body><table><tr><td>估计器</td><td>N=500</td><td>N=2000</td><td>N=5000</td></tr><tr><td>LLR</td><td>174 s</td><td>37 min</td><td>6.8h</td></tr><tr><td>ILLR</td><td>28s</td><td>1.5 min</td><td>6min</td></tr></table></body></html>

表2利用Epanechnikov核函数和局部带宽估计SSB所用的时间  

<html><body><table><tr><td>估计器</td><td>N=500</td><td>N=2000</td><td>N=5000</td></tr><tr><td>LLR</td><td>330 s</td><td>77 min</td><td>12.4 h</td></tr><tr><td>ILLR</td><td>38s</td><td>2 min</td><td>8.9 min</td></tr></table></body></html>

# 3.3.2LLR估计器和ILLR估计器估计SSB结果比较

图1是利用高斯核函数和全局带宽得到的结果，根据数据的密集程度将数据划分为两部分，图中阴影部分表示高度计测量值个数小于100 的区域，代表数据稀疏区域，而另外一部分则代表数据密集区域。图1(a)和图1(b)的等值线分别表示利用 LLR 估计器和 ILLR 估计器得到的 SSB 查找表在(U,SWH)平面的分布，等值线的单位为cm。很明显，利用两种估计器得到的SSB随U和SWH的变化趋势完全相同，在U相同的条件下，SSB 的幅值都随着 SWH的增大而增大；而在SWH相同的条件下，随着U的增大，SSB的幅值都是先增大，而当U增大到一定值时，SSB 的幅值都逐渐减小。图1(c)的等值线表示利用LLR估计器和 ILLR估计器得到的 SSB 之差在(U,SWH)平面的分布，可以看出，在数据密集区域，两种估计器得到的 SSB 之差大约在 $1 0 ^ { - 4 } \mathrm { c m }$ 量级，基本上可以忽略。

图2是利用 Epanechnikov 核函数和局部带宽得到的结果，图2(a)和图 2(b)的等值线分别表示利用LLR估计器和 ILLR 估计器得到的 SSB 查找表在(U,SWH)平面的分布，等值线的单位为 $\mathrm { c m }$ ，同图1一样，利用两种估计器得到的 SSB随U和 SWH的变化趋势也是相同的，由于使用了Epanechnikov 核函数，在低风速高海况和高风速低海况的数据稀疏区域，由于使用到的数据比较少，得到的结果不如图1中利用高斯核函数得到的结果平滑。图2(c)的等值线表示利用LLR 估计器和ILLR 估计器得到的 SSB之差在(U,SWH)平面的分布，在数据密集区域，利用两种估计器得到的SSB之差大约在 $1 0 ^ { - 6 } \mathrm { c m }$ 量级，可以认为利用两种估计器得到的 SSB 基本相同。

图3给出了利用LLR 估计器和ILLR 估计器得到的 SSB 估计值的散点图，图中的结果是通过将两种估计器得到的 SSB 查找表分别用于 2011年 Jason-2 高度计 SSB 的估计得到，可以看出，两种估计器得到的 SSB估计值一致性非常好。再将两种估计器得到的 SSB 的查找表分别用于 $2 0 0 9 { \sim } 2 0 1 1$ 年Jason-2 高度计 SSB 的估计，分别利用每年的数据进行统计，表3给出了统计结果，当利用高斯核函数和全局带宽时，两种估计器得到的 SSB 估计值之差的最大值在 $1 0 ^ { - 3 } ~ \mathrm { { c m } }$ 量级，平均值在 $1 0 ^ { - 4 } \mathrm { c m }$ 量级；而当利用 Epanechnikov 核函数和局部带宽时，两种估计器得到的SSB估计值之差的最大值在 $1 0 ^ { - 5 }$ cm 量级，平均值在 $1 0 ^ { - 6 } ~ \mathrm { { c m } }$ 量级。所以不管是哪种核函数和带宽的组合，ILLR 估计器对 SSB 的估计结果的影响都可以忽略。

目前，国际上主要采用解释方差来对 SSB 模型进行评估。解释方差是指未经 SSB 校正的海面高度不符值的方差减去经过SSB校正后的海面高度不符值的方差，解释方差可以理解为海面高度不符值的方差中 SSB能够解释的部分，解释方差越大，说明 SSB 模型越有效。对两种不同的核函数和带宽组合，分别使用${ 2 0 0 9 } { \sim } 2 0 1 1 \ 3 \$ 年的数据计算利用两种估计器得到的 SSB 的解释方差，表4给出了利用两种估计器得到的 SSB的解释方差之差。当使用高斯核函数和全局带宽时，两种估计器得到的 SSB的解释方差之差在 $\mathrm { 1 0 ^ { - 5 } c m ^ { 2 } }$ 量级，而当使用 Epanechnikov 核函数和局部带宽时，两种估计器得到的 SSB 的解释方差之差在 $1 0 ^ { - 9 } { \sim } 1 0 ^ { - 7 } ~ \mathrm { c m } ^ { 2 }$ 量级，所以不管是哪种核函数和带宽的组合，和LLR 估计器相比，ILLR 估计器对 SSB 模型有效性的影响都可以忽略，从而也不会影响高度计最终的测高精度。

![](images/c7c0a4aa2a28cefbbd19125c867d4ea6c0174d2c88caa657056f442f1650916c.jpg)  
图1利用高斯核函数和全局带宽得到的结果在(USWH)平面的分布

![](images/f4ddb6fdccacaa412b46c463f34c05ae6bbe595d2683da904737d4c9c1fbcf1b.jpg)  
图2利用Epanechnikov 核函数和局部带宽得到的结果在(U,SWH)平面的分布

![](images/0c5c756c3b7d313a9cb7ac9ed3977d445524c0f3dd7589068fde4b2e4a392023.jpg)  
图3利用LLR估计器和ILLR估计器得到的SSB估计值的散点图

表3利用两种估计器得到的SSB之差(cm)统计  

<html><body><table><tr><td>核函数和带宽组合</td><td>最大值</td><td>平均值</td></tr></table></body></html>

<html><body><table><tr><td></td><td>2009年</td><td>2010年</td><td>2011年</td><td>2009年</td><td>2010年</td><td>2011年</td></tr><tr><td>高斯核+全局带宽</td><td>1.26×10-3</td><td>1.01×10-3</td><td>1.13×10-3</td><td>5.45×104</td><td>5.51×10-4</td><td>5.49×10-4</td></tr><tr><td>Epanechnikov核+局部带宽</td><td>3.63×10-5</td><td>8.13×10-5</td><td>5.01×10-5</td><td>2.39×10-6</td><td>2.41×10-6</td><td>2.40×10-6</td></tr></table></body></html>

表4利用两种估计器得到的 SSB 的解释方差之差 $\mathrm { ( c m ^ { 2 } ) }$   

<html><body><table><tr><td rowspan="2">核函数和带宽组合</td><td colspan="3">检验数据集</td></tr><tr><td>2009年</td><td>2010年</td><td>2011年</td></tr><tr><td>高斯核+全局带宽</td><td>4.83×10-5</td><td>4.88×10-5</td><td>5.27×10-5</td></tr><tr><td>Epanechnikov核+局部带宽</td><td>7.88×10-8</td><td>1.28×10-7</td><td>1.77×10-9</td></tr></table></body></html>

# 4结论

非参数模型由于其较高的精度已被广泛用于雷达高度计的 SSB 校正，在利用非参数估计方法估计 SSB时，通常会采用LLR估计器来求加权矩阵里的权函数，而LLR估计器涉及高维矩阵运算，当数据量较大时需要大量的计算时间。

本文提出了一种ILLR估计器，该估计器可以避免高维矩阵运算，从而极大地提高计算效率。本文分别使用高斯核函数加全局带宽以及 Epanechnikov 核函数加局部带宽这两种组合来估计 SSB，在两种组合中，利用 ILLR 估计器得到的 SSB 和利用 LLR 估计器得到的 SSB 之差基本上可以忽略；ILLR 估计器可以大幅度地降低估计 SSB 所需要的时间，当数据量很大时，这种改进的效果更为明显。目前业务化运行的高度计都是采用基于风速和有效波高的2维 SSB 模型，将新的参量引入 SSB 模型已经成为 SSB 经验模型研究的一个新方向，本文提出的ILLR估计器可以在不影响 SSB估计结果条件下大幅度降低估计 SSB所需要的时间，这为实现高维非参数SSB模型的实时运算奠定了基础。

# 参考文献

[1]王磊.高精度卫星雷达高度计数据处理技术研究[D].[博士论文]，中国科学院(国家空间科学中心),2015.WANGL.Studyohedataprocessingforghprecisionsatelitedaalimeter.Dssertatio,atioalSpaceSeeteChinese Academy of Sciences, 2015.  
[2]王磊，许可，史灵卫，等．一种消除合成孔径雷达高度计延迟校正中残余误差的新算法及仿真验证[J]．电子与信息学报，2015，37(11):2713-2718.doi:1O.11999/JEIT150282.WANGL,XUK,SLWetal.nragemigatiocorrectioalgritanditsimulatioforRaltieter.JoulofElctoicsInformation Technology,2015,37(11): 2713-2718.doi: 10.11999/JEIT150282.  
[3]刘亚龙.HY-2 雷达高度计海面高度定标技术研究[D].[博士论文」中国海洋大学,2014.LIUYL.CalibrationtechnologyforHY-2adaraltimeterseasurfacehightD]Ph.D.disertation,Ocean UniversityofCha,204.  
[4]GAPARGRFOY,etlEatittateofddoaleersosoJournal of Geophysical Research-Oceans,1994,99(C12): 24981-24994.doi: 10.1029/94JC01430.  
[5]PRANDVetl/ltatatisticesdolibrat-de2015,38(10): 297-312. doi: 10.1080/01490419.2014.995840.  
[6]TRAN NVANDEMARKDCHAROB,etalNeodelsftelltealimetersetateiasorectioeveloduinggloalwvemodel datalJ].Journal of Geophysical Research-Oceans,2006,111(C9):141-152.doi: 10.1029/2005JC003406.  
[7BONNEFOPEXEREPLAURAIO,etalRAL/AtiKaabsutecalbratiofrotheulti-isioncrsicafciliJieGeodesy,2015,38(10): 171-192. doi: 10.1080/01490419.2015.1029656.  
[8]GASPARPandFLOREANSJP.Estimationofthesea state bias inradaraltimeter measurementsofsea level: Results fromanewnonparametric methodJ].Journalof GeophysicalResearch-Oceans,1998,103(Co8):15803-15814.doi:10.1029/98JC01194  
[9]CHLTODB.Tesea-statebiasinaltimeterestimatesofsea-levelfrocolinearanalysisofopex DataJJournalofGeohyicalResearch-Oceans,1994,99(C12): 24995-25008.doi: 10.1029/94JC02113  
[10]GASPARPLABRUESOGORFetalImprovingoparametricstiatesof teseastatebias indaraltietermeasureetsofalevel[J.JournalofAtmospheric andOceanic Technology,2002,19(1O):169-17O7.doi:10.1175/1520-0426(2002)019 $\kappa 1$ 1690:INEOTS>2.0.CO;2.  
[11]WANGJXand XIAOQX.Local polynomial estimationof time-dependent difusionparameterfordiscretelybserved SDEmodels.Filomat, 2014,28(4): 871-878. doi: 10.2298/FIL1404871W.  
[12]SULdcalplatifaeclasatisdelsalfoeic)193-218. doi:10.1016/j.jeconom.2008.01.002.  
[13]DETTMERING D,SCHWATKEC，and BOSCH W.Globalcalibrationof SARAL/AltiKausing multi-missonseasurfaceheightcrossovers[J]. Marine Ge0desy,2015,38(10): 206-218.doi: 10.1080/01490419.2014.988832.  
[14]PAIGECCandSAUNDERSMA.LSQR:Analgorithmforsparselinear-equationsandsparseleast-squaresJAcmTransactiosonMathematical Software,1982,8(1): 43-71. doi: 10.1145/355984.355989.  
[15]FOGDCLandSAUNDERS.LR: Aniterativealgorithforsparseleast-squaresprobles.SiamJournalonSientifiCptig2010,33(5):2950-2971. doi: 10.1137/10079687X.  
[16]TRANN,VANDEMARKD,LABROUES,etal.SeastatebasilimetersealevelstimatesdeterminedbyombiningwaveodelandsatellitedataJ].Journalof GeophysicalResearch-Oceans,201o,115(Co302):1-7.doi:10.1029/2009JC005534.  
[17]FENGH,IetlbasedoraetrittiofeieratatesoetioEceRemote Sensing Letters,2010,7(3): 577-581. doi: 10.1109/LGRS.2010.2041894.蒋茂飞：男，1989 年生，博士生，研究方向为雷达高度计数据处理.  
许可：男，1963年生，博士，研究员，博士生导师，主要研究方向为星载雷达高度计系统技术、合成孔径雷达高度计系统技术和信号处理技术.  
刘亚龙：男，1985年生，博士，研究方向为雷达高度计数据处理.  
王磊：男，1986年生，博士，研究方向为雷达高度计信号处理