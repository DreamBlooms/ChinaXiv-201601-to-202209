# 基于引力搜索算法的分数阶变异时序回归GSA-TSGM(1,1)模型

高飞，方海莲(武汉理工大学 理学院，武汉 430070)

摘要：为了利用分数阶累加算子在灰色短期预测中的高效性能，首次将分数阶累加算子引入变异时序回归模型以期取得更高的预测精度。主要方法如下：首先取湖北省链子崖某监测点1978—1987年的十年数据作为训练集并使用引力搜索算法确定最佳分数阶累加阶数，而1988—1993年的六年数据作为验证集验证提出的模型；其次对比了经典灰色模型 GM(1,1)、分数阶累加灰色模型、变异时序回归模型 TSGM(1,1)三种灰色模型。结果如下：首先修正了陈西江等人变异时序回归模型仿真时出现的错误，其次表明了相比于其他的模型，基于引力搜索算法的分数阶累加时序回归模型在进行灰色长期预测中具有较高的预测精度。因此，通过分数阶累加算子提高了灰色理论中长期预测模型的精度，为灰色长期预测提供了指导。

关键词：分数阶累加算子；引力搜索算法；变异时序回归模型；灰色长期预测模型 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2018.01.0004

# Fractional order grey model GSA-TSGM(1,1) with time sequence variation regression driven by gravitational search algorithm

Gao Fei, Fang Hailian

(Schoolof Sciences,Wuhan Universityof Technology,Wuhan 43oo70,China)

Abstract: In order touse the high performance offractional accumulated generating operator (FAGO)inthe short-termgrey prediction,inthis paper,itfirstlyaddedFAGO inthetimesequencevariation greymodelTSGM(1,1)togethigheraccuracy. The mainmethod organizedas follow.Firstly,use thedataof1978 to1987from the monitoring stationof“Lianziya"mountain in Hubei provinceas trainingdatatooptimalFAGObyusing gravitationalsearchalgorithmandthenusethedataof1988-1993 as verifyingdatatotesttheaccuracyoftheproposed greymodel.Secondly,itcomparedother greymodelGM(1,1),fractioal accumulated generatingGM(1,l)andGM(1,1).Theresultwas thatasfolow.Firstlycorectedteerrorin theChen'sarticle. Moreover,itshowedthattheproposed model inthispaperhas higher predictionaccuracy.Therefore,the novel modelimproves accuracyof thegreytheoryinlong-term predictionbyfractionalaccumulated generating operatorandit provides the guide in the long-term prediction.

Key words:fractional accumulated generating operator;gravitational search algorithm;impulse noise; grey model with time sequence variation; long-term in grey models

# 0 引言

为解决数据特征为不完整、不明确的小数据的预测问题，邓聚龙教授[1在1982年提出灰色模型理论，其中“灰”表示数据的部分信息已知，部分信息未知。与现有的数据挖掘方法如聚类，分类，关联2等相比，灰色模型可以利用有限的、较少的数据代替大数据来实现预测。在灰色系统中，由于初始序列信息的灰特征，常规的拟合回归方法已经难以对其进行预测。经典灰色模型GM(1,1)是通过对初始序列建立具有一个变量的一阶微分模型，自其提出后已经广泛的解决了安全控制、环境科学、能源控制等众多问题[3]。G指的是灰色，M指的是模型，第一个“1”指的是灰微分建模方程的阶数，第二个“1”指的是该灰色系统的变量个数。该模型有三个特点：第一，可以利用有限的灰信息代替大数据对事物未来的发展趋势进行控制；第二，模型建立相对简单便于使用；第三，长期预测效果不佳。因此，灰色理论作为一门新兴的学科并且作为小数据拟和回归的有效手段，仍有值得学者们进一步研究和改进的地方。

随着GM(1,1)模型深入研究，文献[4,5]中提出了不同的背景值会带来不同的系统误差。且经典GM（1,1）模型中运用最小二乘法原理确定灰参数本身就会引入一定的误差。针对背景值优化，谭等人[6首次构造出新的背景值来替代GM(1,1)模型中经典的背景值，并且新的背景值不仅对低增长序列而且对高增长序列也能起到较好的拟合及预测结果。针对灰参数的优化，文献[7,8]分别采用扩展灰参数为时间序列和采用智能算法估计灰参数以减小误差。而间接减少背景值与灰参数带来的误差也是当时研究的热点。文献[9,10]均是先接受背景值与灰参数带来的误差，但是都通过残差的原理进行分析和优化。基于文献[9],陈等人[11]认为时序残差GM(1,1)通过原序列的时序仍存在一定的缺陷，于是对1阶累加生成算子处理后的序列时序进行分析，通过对时间序列拟合回归得到变异时序从而建模提出变异时序回归GM(1,1)模型。对比时序残差GM(1,1)的分析结果，变异时序回归GM(1,1)的精度略有提高。并且文献[11]中利用变异时序回归GM(1,1)模型进行实例分析时，存在一定的错误。但变异时序回归模型在预测未来六年的数据时可以具有较好的适用性因此变异时序回归GM(1,1)模型仍有研究价值且其预测精度有待提高。

近些年，随着分数阶微积分在不同领域的广泛应用[2]。

Wu等人[13]首次将分数阶微积分概念引入到灰色模型，建立分数阶累加灰色模型，并通过实例表明当预测未来近三年来的数据时，分数阶累加灰色模型可以得到较高的预测精度。Mao等人[14将分数阶累加算子扩展到矩阵形式，为建模的计算提供了方便。而将平均相对误差作为目标函数并运用启发式智能算法进行估计这一方法已成为估计分数阶累加阶数的优先选择。文献15\~17]均采用粒子群优化算法对分数阶累加算子的阶数进行估计。

目前，灰色理论在研究人员的不断努力下得以快速的发展，但是正是由于灰色理论的不断丰富，新问题也在不断涌现。本文利用分数阶累加算子在预测方面的高性能以及目前变异时序回归模型的预测精度有待提高的特点对变异时序回归GM(1,1)模型进行改进，将分数阶累加算子与变异时序回归GM(1,1)模型相结合提出分数阶累加变异时序回归GM(1,1)模型。这样既能利用分数阶累加算子预测精度高的特点也能提高变异时序回归GM(1,1)模型的预测精度。基于文献[18]中基准测试函数作为目标函数对引力搜索算法与粒子群优化算法的性能进行比较，表明了对于大部分基准测试函数而言，引力搜索算法性能是优于粒子群优化算法的。因此，本文采用引力搜索智能启发式优化算法进行分数阶累加算子估计。

# 1 变异时序回归TSGM（1,1）模型

# 1.1 GM(1,1)[3]

主要建模流程如下：  
GM(1,1)  
输入：已有原非负序列 $\boldsymbol { X } ^ { ^ { ( 0 ) } } = ( x ^ { ( 0 ) } ( 1 ) , x ^ { ^ { ( 0 ) } } ( 2 ) , . . . , x ^ { ^ { ( 0 ) } } ( n ) )$ 。

a）规律化：用一阶累加算子1-AGO 处理 $\boldsymbol { X } ^ { ^ { ( 0 ) } }$ 得到 $\boldsymbol { X } ^ { ^ { ( 1 ) } } =$ （20 $( x ^ { ( 1 ) } ( 1 ) , x ^ { ^ { ( 1 ) } } ( 2 ) , . . . , x ^ { ^ { ( 1 ) } } ( n ) )$ ，即 $x ^ { ( 1 ) } ( k ) = \sum _ { i = 1 } ^ { k } x ^ { ( 0 ) } ( i )$ ，其中$k = 1 , 2 , . . . , n$ 。现 $X ^ { ^ { ( 1 ) } }$ 为单调递增序列。

b）建模1： $x ^ { ( 0 ) } ( k ) + a z ^ { ( 1 ) } ( k ) = b$ ，其中 $z ^ { ( 1 ) } ( k ) = 0 . 5 x ^ { ( 1 ) } ( k ) +$ $0 . 5 x ^ { ( 1 ) } ( k - 1 )$ ， $k = 2 , 3 , . . . , n$ 称为背景值。利用最小二乘法估计灰参数 $^ { a , b }$ 。即令 $B = \left( - z ^ { ( 1 ) } ( k ) \textit { \textbf { e } } \right)$ ， $Y = ( x ^ { ^ { ( 0 ) } } ( 2 ) , . . . , x ^ { ^ { ( 0 ) } } ( n ) ) ^ { \prime }$ 其中 $e = ( 1 , . . . , 1 ) ^ { \prime }$ 为长度为 $n { - } 1$ 的单位向量。则灰参数的估计值为 $P = \left( a b ^ { \prime } b \right) ^ { \prime } = ( B ^ { \prime } B ) ^ { - 1 } B ^ { \prime } Y$ 。

c）建模2：将上述估计的灰参数 $\hat { a } , \hat { b }$ 代入灰微分建模方程${ \frac { d x ^ { ( 1 ) } ( t ) } { d t } } + a x ^ { ( 1 ) } ( t ) = b$ （20 的时间响应曲线中$\begin{array} { r } { \hat { x } ^ { ( 1 ) } ( t ) = ( x ^ { ( 0 ) } ( 1 ) - \frac { \hat { b } } { \hat { a } } ) e ^ { - \hat { a } ( t - 1 ) } + \frac { \hat { b } } { \hat { a } } \ , \quad t = 1 , 2 , 3 , \dots { _ { \circ } } } \end{array}$

d)还原输出：对得到的序列 $\hat { X } ^ { ( 1 ) }$ 做一阶累减还原算子

(1-IAGO）即 $\hat { x } ^ { ( 0 ) } ( t ) = \hat { x } ^ { ( 1 ) } ( t + 1 ) - \hat { x } ^ { ( 1 ) } ( t )$ ， $t = 2 , 3 , \dots$ ， $t > n$ 时，$\hat { x } ^ { ( 0 ) } ( t )$ 为预测值，否则为拟合值。

以上便是经典灰色模型的五步建模思想。

# 1.2变异时序回归 GM(1,1)

可以看出GM(1,1)五步建模中，建模的误差主要来源于背景值和灰参数的确立。因此陈[1等人将误差引入到时间序列中，形成变异时序。即现先接受背景值和灰参数带来的误差，假设根据GM(1,1）建模得到的 $\hat { X } ^ { ^ { ( 1 ) } } ( t )$ 没有误差。

主要建模流程如下：

变异时序回归 TSGM(1,1)

a)时序误差引入：假设 $\hat { X } ^ { ^ { ( 1 ) } } ( t + 1 )$ 没有误差，即 $\hat { X } ^ { ^ { ( 1 ) } } ( t + 1 ) =$ $X ^ { ( 1 ) } ( t + 1 )$ 。令 $t ^ { ( 0 ) } = t + \delta _ { t }$ ，

$$
\begin{array} { r } { \hat { x } ^ { \scriptscriptstyle ( 1 ) } ( t + 1 ) = ( x ^ { \scriptscriptstyle ( 0 ) } ( 1 ) - \frac { \hat { b } } { \hat { a } } ) e ^ { - \hat { a } ( t + \delta _ { t } ) } + \frac { \hat { b } } { \hat { a } } , t = 1 , 2 , 3 , \ldots . } \end{array}
$$

b)变异时序曲线：上述变异时序解曲线为 $t ^ { ( 0 ) } =$

$- \frac { 1 } { \hat { a } } \mathrm { l n } \frac { ( \hat { x } ^ { ( 1 ) } ( t + 1 ) - \frac { \hat { b } } { \hat { a } } ) } { x ^ { ( 0 ) } ( 1 ) - \frac { \hat { b } } { \hat { a } } } = - \frac { 1 } { \hat { a } } \mathrm { l n } \frac { ( x ^ { ( 1 ) } ( t + 1 ) - \frac { \hat { b } } { \hat { a } } ) } { x ^ { ( 0 ) } ( 1 ) - \frac { \hat { b } } { \hat { a } } }$ n(x(t+1)-）。为防止t)规律不明显，这里同样使用1阶累加生成算子1-AGO 处理 $t ^ { ( 0 ) }$ 生成$t ^ { ( 1 ) }$

c)变异时序回归：针对数据条目数选取几类常用的曲

线回归方程进行回归，文献[12]中选取二次多项式f=ao$+ a _ { 1 } t + a _ { 2 } t ^ { 2 }$ ，三次多项式 $f = a _ { 0 } + a _ { 1 } t + a _ { 2 } t ^ { 2 } + a _ { 3 } t ^ { 3 }$ ，四次多项式（202 $f = a _ { 0 } + a _ { 1 } t + a _ { 2 } t ^ { 2 } + a _ { 3 } t ^ { 3 } + a _ { 4 } t ^ { 4 }$ ，含常数的幂函数 $f = a t ^ { b } + c$ 。其中 $t = 1 , 2 , 3 , . . . , 9 \ , f = t ^ { ( 1 ) } ( 2 ) , t ^ { ( 1 ) } ( 3 ) , . . . . , t ^ { ( 1 ) } ( 1 0 ) \ ^ { \circ }$ 。数据和曲线确定后利用MATLAB自带最小二乘法原理多项式曲线回归函数polyfit(t,f,n)，其中n为多项式次数，而含有常数的幂函数为非线性曲线最小二乘法原理曲线拟合可利用 MATLAB自带函数lsqcurvefit来实现。

d）最佳变异时序回归曲线：计算上述各回归曲线的拟

合误差，为防止过拟合现象的发生，文献[11]选择拟合误差为次小误差的拟合曲线作为最佳变异时序回归曲线 $\hat { t } ^ { ( 1 ) }$ 。利用$\hat { t } ^ { ( 1 ) }$ 曲线计算预测值，最终将得到的序列做1阶累减还原(1-IAGO)得到 $\hat { t } ^ { ( 0 ) }$ 的拟合和预测值。

e）还原输出：代入 $\begin{array} { r } { \hat { \boldsymbol { x } } ^ { ( 1 ) } ( t + 1 ) = ( \boldsymbol { x } ^ { ( 0 ) } ( 1 ) - \frac { \hat { b } } { \hat { a } } ) e ^ { - \hat { a } ( \hat { t } ^ { ( 0 ) } ) } + \frac { \hat { b } } { \hat { a } } } \end{array}$ ，计算出（204号 $\hat { X } ^ { ( 1 ) }$ 。使用1-IAGO 进行累减还原得到初始序列的拟合及预测值 $\hat { X } ^ { ( 0 ) }$ 。以上便是文献[11]提出的变异时序回归模型的理论思想。

# 2 分数阶变异时序回归模型

# 2.1分数阶累加生成算子

在经典灰色模型GM(1,1)建模过程中，为了使初始序列$X ^ { ( 0 ) }$ 规律化，采用1阶累加生成算子对其处理，即 $x ^ { ( 1 ) } ( k ) =$ $\sum _ { i = 1 } ^ { k } x ^ { ( 0 ) } ( i )$ 。采用矩阵的形式表示如下:

$$
( \boldsymbol { x } ^ { ( 1 ) } ( 1 ) , \boldsymbol { x } ^ { ( 1 ) } ( 2 ) , . . . , \boldsymbol { x } ^ { ( 1 ) } ( n ) ) = \left( \begin{array} { l l l l } { 1 } & & & \\ { 1 } & { 1 } & & \\ { \vdots } & { \vdots } & { \ddots } & \\ { 1 } & { 1 } & { 1 } & { 1 } \end{array} \right) _ { n \times n } ( \boldsymbol { x } ^ { ( 0 ) } ( 1 ) , \boldsymbol { x } ^ { ( 0 ) } ( 2 ) , . . . , \boldsymbol { x } ^ { ( 0 ) } ( n ) )
$$

系数矩阵设为 $A$ ， $A$ 为下三角元素全为1的矩阵。则 $r$ 阶累加生成算子为 $x ^ { ( r ) } ( k ) = \sum _ { i = 1 } ^ { k } x ^ { ( r ) } ( i )$ ，即

$$
( { x ^ { ( r ) } } ( 1 ) , { x ^ { ( r ) } } ( 2 ) , . . . , { x ^ { ( r ) } } ( n ) ) = \left( \begin{array} { l l l l } { 1 } & { } & { } & { } \\ { 1 } & { 1 } & { } & { } \\ { \vdots } & { \vdots } & { \ddots } & { } \\ { 1 } & { 1 } & { 1 } & { 1 } \end{array} \right) _ { n \times n } ( { x ^ { ( r - 1 ) } } ( 1 ) , { x ^ { ( r - 1 ) } } ( 2 ) , . . . , { x ^ { ( r - 1 ) } } ( n ) ) =
$$

$$
\begin{array} { r } { \left( \begin{array} { c c c c c } { 1 } & & & & \\ { 1 } & { 1 } & & \\ { \vdots } & { \vdots } & { \ddots } & \\ { 1 } & { 1 } & { 1 } & { 1 } \end{array} \right) ^ { 2 } \qquad ( x ^ { ( r - 2 ) } ( 1 ) , x ^ { ( r - 2 ) } ( 2 ) , . . . , x ^ { ( r - 2 ) } ( n ) ) = } \end{array}
$$

$$
\begin{array} { r } { \left( \begin{array} { l l l l } { 1 } & & & \\ { 1 } & { 1 } & & \\ { \vdots } & { \vdots } & { \ddots } & \\ { 1 } & { 1 } & { 1 } & { 1 } \end{array} \right) ^ { r } \qquad ( x ^ { ( 1 ) } ( 1 ) , x ^ { ^ { ( 1 ) } } ( 2 ) , . . . , x ^ { ^ { ( 1 ) } } ( n ) ) = A ^ { r } ( x ^ { ( 1 ) } ( 1 ) , x ^ { ^ { ( 1 ) } } ( 2 ) , . . . , x ^ { ^ { ( 1 ) } } ( n ) ) _ { \mathrm { ~ o u t } } } \\ { \left( \begin{array} { l l l l } { 1 } & { 1 } & { 1 } & { 1 } \end{array} \right) _ { n \times n } } \end{array}
$$

$$
A ^ { r } = \left( \begin{array} { c c c c c c } { { 1 } } & { { 0 } } & { { 0 } } & { { \cdots } } & { { 0 } } \\ { { r } } & { { 1 } } & { { 0 } } & { { \cdots } } & { { 0 } } \\ { { \frac { r ( r + 1 ) } { 2 ! } } } & { { r } } & { { 1 } } & { { \cdots } } & { { 0 } } \\ { { \vdots } } & { { \vdots } } & { { \vdots } } & { { \ddots } } & { { 0 } } \\ { { \frac { r ( r + 1 ) \cdots ( r + n - 2 ) } { ( n - 1 ) ! } } } & { { \frac { r ( r + 1 ) \cdots ( r + n - 3 ) } { ( n - 2 ) ! } } } & { { \frac { r ( r + 1 ) \cdots ( r + n - 4 ) } { ( n - 3 ) ! } } } & { { \cdots } } & { { 1 } } \end{array} \right)
$$

$\left( a _ { i j } \right) _ { n \times n } = \left\{ \begin{array} { c c } { C _ { i - j + r - 1 } ^ { r - 1 } = \frac { \left( i - j + r - 1 \right) ! } { \left( r - 1 \right) ! \left( i - j \right) ! } } & { \quad j } \\ { 0 } & { \quad j } \end{array} \right.$ ≤i令 $A ^ { r } = \left( a _ { i j } \right) _ { n \times n }$ ，则 j>i，其证明可用数学归纳法参见文献[13,14]。

可见此时 $r$ 是整数，根据分数阶微积分组合数的推广定义，可将 $r$ 扩展成有理数。

# 2.2分数阶累减生成算子

同样地，在GM(1,1)建模过程最后需要对 $\hat { X } ^ { ( 1 ) }$ 做一阶累减还原得到初始序列的拟合预测值。即 $\hat { x } ^ { ( 0 ) } ( t ) = \hat { x } ^ { ( 1 ) } ( t + 1 ) - \hat { x } ^ { ( 1 ) } ( t )$ ，

转换为矩阵形式为

$$
\left( { \hat { x } } ^ { ( 0 ) } ( 1 ) , { \hat { x } } ^ { ( 0 ) } ( 2 ) , . . . , { \hat { x } } ^ { ( 0 ) } ( n ) \right) = \left( { \begin{array} { c c c c } { 1 } \\ { - 1 } & { 1 } \\ { \ddots } & { \ddots } \\ & { - 1 } & { 1 } \end{array} } \right) _ { n \times n } \left( { \hat { x } } ^ { ( 1 ) } ( 1 ) , { \hat { x } } ^ { ( 1 ) } ( 2 ) , . . . , { \hat { x } } ^ { ( 1 ) } ( n ) \right)
$$

其中系数矩阵为对角线全为1，对角线左下斜线位置元素全为$^ { - 1 }$ 以及剩余位置元素全为0的矩阵。显然，根据矩阵运算，此系数矩阵为 $\boldsymbol { A } ^ { - 1 }$ 。因此，1阶累加生成算子与1阶累减还原算子互为逆算子。同样的，根据矩阵运算可知， $r$ 阶累减还原系数矩阵为 $\left( A ^ { - 1 } \right) ^ { r } = A ^ { - r } = \left( A ^ { r } \right) ^ { - 1 }$ ，即 $\boldsymbol { r }$ 阶分数阶累加生成算子与 $\boldsymbol { r }$ 阶累减还原互为逆算子。

# 2.3分数阶变异时序回归GSA-TSGM(1,1)模型

主要建模流程如下：分数阶变异时序回归GSA-TSGM(1,1)模型输入：已有原非负序列x=(x(),x(2),.,x(n))‘

a)规律化：用 $\boldsymbol { r }$ 阶累加算子 $\boldsymbol { r }$ -AGO 处理 $X ^ { ^ { ( 0 ) } }$ ，即 $X ^ { ( r ) }$ = AX() 。

b)建模1: $x ^ { ( r - 1 ) } ( k ) + a z ^ { ( r ) } ( k ) = b$ ，其中 $x ^ { ( r - 1 ) } ( k ) = x ^ { ( r ) } ( k ) -$ $x ^ { ( r ) } ( k - 1 ) ~ , ~ z ^ { ( r ) } ( k ) = 0 . 5 x ^ { ( r ) } ( k ) + 0 . 5 x ^ { ( r ) } ( k - 1 ) ~ , ~ k = 2 , 3 , . . . ,$ 。利用最小二乘法估计灰参数 ${ \mathbf { \Omega } } _ { a , b }$ 。即令 $B _ { 1 } = \left( - z ^ { ( r ) } ( k ) \mathrm { ~ \it ~ e ~ } \right)$ Y=(x"(2).,x"(n))，其中e=(l...,1)为长度为n-1的单位向量。则灰参数的估计值为P=(ab)=(BB)BY

c）建模2：将上述估计的灰参数 $\hat { a } , \hat { b }$ 代入灰微分建模白化方程 $\frac { d x ^ { ( r ) } ( t ) } { d t } + a x ^ { ( r ) } ( t ) = b$ 的时间响应曲线中 $\hat { x } ^ { ( r ) } ( t + 1 ) =$ $\begin{array} { r } { ( x ^ { ( 0 ) } ( 1 ) - \frac { \hat { b } } { \hat { a } } ) e ^ { - \hat { a } ( t ) } + \frac { \hat { b } } { \hat { a } } ~ , \quad t = 1 , 2 , 3 , \dots \circ } \end{array}$ （204号

d)降低初值的影响：对得到的序列 $\hat { X } ^ { \left( r \right) }$ 再次做最小二乘估计，即令 $\hat { x } ^ { ( r ) } ( t + 1 ) = c e ^ { - \hat { a } ( t ) } + d , B _ { 2 } = \left( e ^ { - \hat { a } t } \quad e \right) , Y _ { 2 } =$ (x(2).,x"()’，t=1.,,..,n-，其中e=(1...1),为长度为$n - 1$ 的单位向量。则灰参数的估计值为 $P _ { 2 } = \left( { \hat { c } } \quad { \hat { d } } \right) ^ { \prime } =$ (B'B)-B'Y。此时x(")(t+1)=ce-a()+d。

e)若此时对 $\hat { X } ^ { \ d ( r ) }$ 进行 $\boldsymbol { r }$ 阶累减还原，则此模型为文献[14]里的分数阶累加灰色模型。本文首次对 $\hat { X } ^ { \ d ( r ) }$ 进行变异时序处理，即假设 $\hat { X } ^ { ^ { ( 1 ) } } ( t + 1 )$ 没有误差，即 $\hat { X } ^ { ( r ) } \left( t + 1 \right) = X ^ { ( r ) } \left( t + 1 \right)$ 。令（204号 $t ^ { ( 0 ) } = t + \delta _ { t }$ ，即 $\hat { \boldsymbol x } ^ { ( r ) } ( t + 1 ) = \hat { c } e ^ { - \hat { a } ( t + \delta _ { t } ) } + \hat { d }$ ， $t = 1 , 2 , 3 , \ldots$ （20

f)变异时序曲线：上述变异时序解曲线为 $t ^ { ( 0 ) } =$ 1n(m(t+1)-d)=_1n(x(t+1)-d)。为防止规律不明显,这里同样使用1阶累加生成算子1-AGO 处理 $t ^ { ( 0 ) }$ 生成 $t ^ { ( 1 ) }$ 。g）最佳时序回归曲线：先使用变异时序回归 $\mathrm { G M } ( 1 , 1 )$ 模型对初始数据进行拟合预测得到最佳时序回归曲线 $f$ 。此时可以利用曲线 $f$ 对 $t ^ { ( 1 ) }$ 进行拟合及预测得到 $\hat { t } ^ { ( 1 ) }$ 。最后将得到的序列做1阶累减还原(1-IAGO)得到 $\hat { t } ^ { ( 0 ) }$ 的拟合和预测值。

h）还原输出：代入 $\hat { x } ^ { ( r ) } ( t + 1 ) = \hat { c } e ^ { - \hat { a } ( \hat { t } ^ { ( 0 ) } ) } + \hat { d }$ ，计算出 $\hat { X } ^ { \ d ( r ) }$ 。使用 $\boldsymbol { r }$ -IAGO进行累减还原得到初始序列的拟合及预测值$\hat { X } ^ { \scriptscriptstyle ( 0 ) } = A ^ { - r } \hat { X } ^ { \scriptscriptstyle ( r ) }$ 。

模型特点：:

(a)与变异时序回归模型TSGM(1,1)相比，分数阶变异时序 回归模型GSA-TSGM(1,1)将用来处理初始序列规律化的1阶累 加算子扩展为分数阶累加算子，即将原来的定值“1”扩充为动 态值“分数 $\boldsymbol { r }$ ”。也就是说变异时序回归模型TSGM(1,1)其实是 分数阶变异时序回归模型GSA-TSGM(1,1)的特例形式。因此， 分数阶变异时序回归模型GSA-TSGM(1,1)扩展了原始变异时 序回归模型TSGM(1,1)的适用性范围。

b)动态值“分数 $\boldsymbol { r }$ ”是由与初始序列中训练集的平均绝对百分比误差作为目标函数使用启发式智能算法优化决定的。这就意味着，如果复杂问题的系统不同即初始序列的训练集不同，动态值“分数 $\boldsymbol { r }$ ”是不同的，即动态值“分数r”是由初始序列训练集决定的并控制在最小MAPE误差函数下的。因此，新模型提高了原有模型的精度。

c)变异时序回归模型TSGM(1,1)是灰色长期预测模型，但 由于模型精度并不高所以应用的并不广泛。而分数阶累加算子 在短期预测中是提高模型预测精度的强有力工具。因此，将分 数阶累加算子加入到变异时序回归模型TSGM(1,1)中可以提高 灰色长期预测的精度。

# 3 引力搜索算法优化

# 3.1 目标函数

平均绝对误差百分比(mean absolute percentage error)定义为

$$
M A P E = \sum _ { i = 1 } ^ { n } \Bigl ( \Bigl \vert x ^ { ( 0 ) } ( i ) - \hat { x } ^ { ( 0 ) } ( i ) \Bigr \vert \Bigl / \hat { x } ^ { ( 0 ) } ( i ) \Bigr ) \Biggl / ( n - 1 ) \times 1 0 0 \%
$$

文献[18]表明MAPE是最常用的也是最有效的衡量模型精度标准之一。

# 3.2引力搜索优化算法

和粒子群优化算法相比，引力搜索算法也是一种新型启发式智能优化算法。自Rashedi等人[19]于2009 年提出了引力搜索算法之后，引力搜索算法已经成功地应用于不同领域的参数控制[20]。

在引力搜索算法里，每个对象可看成一个质点。而每个质点在搜索空间里受重力影响互相吸引。适应度函数用来代表每个质点的性能，当较轻的质点运动到最佳位置迭代过程结束。此时，适应度函数已成为全局最佳适应度值。

显然，当引力搜索算法对分数阶变异时序回归模型进行优化时，第 $i$ 个质点 $t$ 时刻适应度函数如下：

$$
\mathit { f i t } _ { i } ( t ) = M A P E ( r )
$$

可以看到，适应度函数是关于 $\boldsymbol { r }$ 的一维函数。当 $r$ 确定后，就可以对应一个MAPE值即一个适应度值。

引力搜索算法估计分数阶变异时序回归模型阶数的流程图

如图1所示。利用引力搜索算法估计出最佳阶数后，再代入分数阶变异时序回归GM(1,1)中求得拟合和预测值 $\hat { X } ^ { \left( 0 \right) }$ 。

![](images/1ed3591358057c0877e8a6a3ea2d39d53076993c090ec6888d30bc9143ad65af.jpg)  
图1引力搜索算法优化分数阶变异时序回归GM(1,1)流程图

# 4 实例分析

链子崖坐落于湖北省长江三峡沿岸，以危崖而成为著名

的风景区。正因为其地理位置以及危崖体的存在，安全问题成为了众多地质灾害专家研究的首要对象。本文以其中一个监测点的观测数据作为实例来验证分数阶灰色变异时序模型GM(1,1)的性能。其中1978-1987年的数据作为训练集来得到模型参数，然后1988年至1993年的数据作为验证集验证引力搜索算法优化的模型。并分别给出GM(1,1)模型，分数阶累加模型FAGM(1,1)模型，变异时序回归模型GM(1,1)的拟合预测结果，与之对比分析。接下来首先修正文献[11中出现的错误。

# 4.1修正文献[11]的错误

a)对初始序列用GM(1,1)模型进行估计，可以得到参 数$P = ( - 0 . 1 4 3 6 3 , 4 . 8 8 8 9 ) ^ { \prime }$ 以及 $\hat { X } ^ { ( 1 ) } = ( 0 . 2 , 5 . 4 8 8 3 , 1 1 . 5 9 3 4 , 1 8 . 6 4 1 4$ 26.7781,36.1716,47.0159,59.5352,73.9881,90.6734)。

b)根据变异时序回归 $\mathbf { G M } ( 1 , 1 )$ 模型中的 $t ^ { ( 0 ) }$ 公式计算可得$t ^ { ( 0 ) } = ( 0 , 0 . 8 0 5 6 , 1 . 6 5 7 0 , 2 . 5 8 6 0 , 3 . 8 4 0 4 , 4 . 9 0 3 0 , 6 . 0 6 7 0 , 6 . 8 9 2 4 , )$ （204号

8.0008,8.9285)'。

从而 $t ^ { ( 1 ) } = ( 0 , 0 . 8 0 5 6 , 2 . 4 6 2 6 , 5 . 0 4 8 6 , 8 . 8 8 9 0 , 1 3 . 7 9 2 0 ,$ $1 9 . 8 5 9 0 , 2 6 . 7 5 1 4 , 3 4 . 7 5 2 2 , 4 3 . 6 8 0 7 ) ^ { \prime }$ 。

c)对 $t ^ { ( 1 ) }$ 进行二次、三次、四次多项式拟合，含有常数的幂函数拟合，拟合曲线如下：

$$
t ^ { ( 1 ) } = 0 . 1 0 8 5 + 0 . 1 0 6 7 t + 0 . 5 2 7 2 t ^ { 2 }
$$

$$
-
$$

$$
t ^ { ( 1 ) } = 0 . 3 6 9 3 - 0 . 0 9 8 4 7 t + 0 . 5 5 2 2 t ^ { 2 } +
$$

$$
0 . 0 0 3 2 3 4 t ^ { 3 } - 0 . 0 0 0 4 4 1 3 t ^ { 4 }
$$

$$
t ^ { ( 1 ) } = 0 . 5 7 0 8 t ^ { 1 . 9 7 3 } + 0 . 1 7 2
$$

其中红色标注的地方便是文献[11]中的错误，结果修正会在之后的表1中给出。

d)计算以上四种曲线拟合误差并选择次小误差的拟合曲线作为最佳曲线拟合即三次多项式。

# 4.2 模拟和预测

表1、2将给出GM(1,1),分数阶累加FAGM(1,1),变异时序回归GM(1,1),分数阶变异时序GM(1,1)的模拟值以及预测值对比分析。其中分数阶累加 FAGM(1,1)累加阶数为 $r = 0 . 7 0 6 0$ 。分数阶变异时序GM(1,1)模型的累加阶数为

$r = 1 . 0 3 6 5$ ， $t ^ { ( 1 ) }$ 的拟合曲线为 $t ^ { ( 1 ) } = 0 . 4 7 8 5 - 0 . 2 5 0 8 t + 0 . 6 1 1 3 t ^ { 2 }$

仿真结果表明：

a)分数阶累加FAGM(1,1)模型在进行长期预测时，精度不 如变异时序回归TSGM(1,1)和分数阶GSA-TSGM(1,1)。

b)变异时序回归TSGM(1,1)与分数阶GSA-TSGM(1,1)的预 测精度明显优于GM(1,1)与分数阶累加FAGM(1,1)。

c)从图5可以明显看到本文提出的GSA-TSGM(1,1)预测误差是最接近于0的，即预测精度最高。

表1四种灰色模型的拟合值对比  

<html><body><table><tr><td rowspan="2">年份</td><td>实际值</td><td colspan="2">GM(1,1)</td><td colspan="2">分数阶累加FAGM(1,1)</td><td colspan="2">变异时序回归 TSGM(1,1)</td><td colspan="2">分数阶 GSA-TSGM(1,1)</td></tr><tr><td>x(0)/cm</td><td>x /cm</td><td>|x(-x()</td><td>x /cm</td><td>|x(-x(0)</td><td>x /cm</td><td>|x(x()</td><td>x /cm</td><td>|x-x(0)</td></tr><tr><td>1978</td><td>0.2</td><td>0.2</td><td>0</td><td>0.2</td><td>0</td><td>0.2</td><td>0</td><td>0.2</td><td>0</td></tr><tr><td>1979</td><td>4.2</td><td>5.2883</td><td>1.0883</td><td>4.1999</td><td>7.6348e-012</td><td>4.3702</td><td>0.1702</td><td>4.3721</td><td>0.1721</td></tr><tr><td>1980</td><td>5</td><td>6.1051</td><td>1.1051</td><td>5.8055</td><td>8.0548e-001</td><td>4.1521</td><td>0.8479</td><td>4.1170</td><td>0.8830</td></tr><tr><td>1981</td><td>6.2</td><td>7.0481</td><td>0.8481</td><td>7.1535</td><td>9.5354e-001</td><td>7.7167</td><td>1.5167</td><td>7.6790</td><td>1.4790</td></tr><tr><td>1982</td><td>9.8</td><td>8.1367</td><td>1.6633</td><td>8.4540</td><td>1.3460</td><td>8.8229</td><td>0.9771</td><td>8.7286</td><td>1.0714</td></tr><tr><td>1983</td><td>9.8</td><td>9.3934</td><td>0.4066</td><td>9.7788</td><td>2.1179e-002</td><td>10.0302</td><td>0.2302</td><td>9.8853</td><td>0.0853</td></tr><tr><td>1984</td><td>12.6</td><td>10.8443</td><td>1.7557</td><td>11.1657</td><td>1.4343</td><td>11.3371</td><td>1.2629</td><td>11.1382</td><td>1.4618</td></tr><tr><td>1985</td><td></td><td>12.5193</td><td>2.2193</td><td>12.6402</td><td>2.3402</td><td>12.7398</td><td>2.4398</td><td>12.4806</td><td>2.1806</td></tr><tr><td>1986</td><td>15.9</td><td>14.4530</td><td>1.4470</td><td>14.2229</td><td>1.6771</td><td>14.2320</td><td>1.6680</td><td>13.9046</td><td>1.9954</td></tr><tr><td>1987</td><td>15.4</td><td>16.6853</td><td>1.2853</td><td>15.9324</td><td>5.3239e-001</td><td>15.8042</td><td>0.4042</td><td>15.4000</td><td>1.3838e-010</td></tr><tr><td colspan="2">MAPE</td><td></td><td>15.0823%</td><td></td><td>10.3934%</td><td></td><td>11.6244%</td><td></td><td>11.4152%</td></tr></table></body></html>

表2四种模型的预测值对比  

<html><body><table><tr><td rowspan="2">年份</td><td>实际值</td><td colspan="2">GM(1,1)</td><td colspan="2">分数阶累加FAGM(1,1)</td><td colspan="2">变异时序回归TSGM(1,1)</td><td colspan="2">分数阶 GSA-TSGM(1,1)</td></tr><tr><td>x( /cm</td><td>x /cm</td><td>|x(-x</td><td>x/cm</td><td>|x(-x()</td><td>x/cm</td><td>|x(_x|</td><td>x /cm</td><td>|x(-x(|</td></tr><tr><td>1988</td><td>18.1</td><td>19.2625</td><td>1.1625</td><td>17.7868</td><td>0.3132</td><td>17.4443</td><td>0.6557</td><td>16.9540</td><td>1.1460</td></tr><tr><td>1989</td><td>21.3</td><td>22.2377</td><td>0.9377</td><td>19.8046</td><td>1.4954</td><td>19.1365</td><td>2.1635</td><td>18.5507</td><td>2.7493</td></tr><tr><td>1990</td><td>20.1</td><td>25.6724</td><td>5.5724</td><td>22.0047</td><td>1.9047</td><td>20.8621</td><td>0.7621</td><td>20.1715</td><td>7.1455e-002</td></tr><tr><td>1991</td><td>22.0</td><td>29.6377</td><td>7.6377</td><td>24.4077</td><td>2.4077</td><td>22.5991</td><td>0.5991</td><td>21.7944</td><td>0.2056</td></tr><tr><td>1992</td><td>22.6</td><td>34.2154</td><td>11.6154</td><td>27.0355</td><td>4.4355</td><td>24.3223</td><td>1.7223</td><td>23.3952</td><td>0.7952</td></tr><tr><td>1993</td><td>21.4</td><td>39.5002</td><td>18.1002</td><td>29.9117</td><td>8.5117</td><td>26.0037</td><td>4.6037</td><td>24.9468</td><td>3.5468</td></tr><tr><td colspan="2">MAPE</td><td></td><td>34.8734%</td><td></td><td>14.7619%</td><td></td><td>8.2382%</td><td></td><td>6.7702%</td></tr></table></body></html>

![](images/ab0a22095f9f951f8ce05b5ffc1ea892749ca833041edfb7cce1f1b24d6c1f63.jpg)  
图2四种模型拟合曲线对比

![](images/c2d981630bbae822988e359ace72b9d3b374b2ebfb69bcd84d3fced04bb0f14f.jpg)  
图3四种模型拟合绝对误差对比

![](images/65d599ee37ec817e80c292428f681bbc220ae194664ca4a180e7ef2e3c0503e3.jpg)  
图4四种模型预测值曲线对比

![](images/336041e40bfdabe39827c2b75ad2a8e37afc5b4e914e732bb06001c386c89f6c.jpg)  
图5四种模型预测值绝对误差曲线对比

# 5 结束语

本文主要解决了两大问题。首先修正了文献[11]中对1阶累加变异时序序列拟合曲线的拟合错误，以及变异时序回归GM(1,1)对实例的仿真结果。其次，本文基于变异时序回归模型以及分数阶累加灰色模型首次将分数阶累加算子引入到变异时序回归模型中，并利用启发式智能算法进行估计。

实例表明，本文提出的基于引力搜索算法的分数阶变异时序回归模型具有较高的精度。同时为分数阶累加算子在进行灰色长期预测提供了指导。

可以看到，在引力搜索算法对分数阶变异时序回归模型的阶数进行估计时，变异时序回归的拟合曲线是在变异时序回归模型进行仿真时提前确定了的。但是当算法优化过程中累加阶数是不断变化的，最佳变异时序回归的拟合曲线可能也会随之变化。因此，针对变异时序回归的拟合曲线方法的选取仍值得进一步探讨。

# 参考文献：

[1]Deng JL. Control problems of grey systems [J].Systems & Control Leters, 1982,1(5): 288-294.   
[2]Frank E,Hall M,Trigg L,et al.Data mining in bioinformatics using Weka [J].Bioinformatics,2004,20 (15): 2479.   
[3]肖新平，邓旅成，查金茂．灰色系统分析理论及其应用[M].大连：大 连海事大学出版社,1997:203-267.   
[4]刘思峰.GM(1,1）模型的适用范围[J]．系统工程理论与实践,2000,20 (5): 121-125.   
[5]Wen,JC,Huang KH,and Wen KL.The study of alpha in GM(1,1) model [J]. Journal ofChinese Institute of Engineers,2000,23 (5): 583-589.   
[6] 谭冠军，檀甲友，王加阳.GM(1,1）模型的背景值构造方法和应用（I) [J]．系统工程理论与实践,2000,20(5):125-128.   
[7]汪孔政．时变参数 PGM $( 1 , 1 )$ 变形预测模型及其应用[J].武汉大学学 报·信息科学版,2005,30(5):456-459.   
[8] Hsu L. Using improved grey forecasting models to forecast the output of opto-electronics industry [J]. Expert Systems with Application,2011,38 (11): 13879-13885.   
[9]李希灿，李丽．时序残差GM(1,1）模型[J]．系统工程理论与实践, 1998,18 (10): 59-63.   
[10] 陈西江，鲁铁定．残差自适应回归 MGM(1,n)[J]．测绘科学,2012,37 (2): 90-93.   
[11]陈西江，鲁铁定．变异时序回归 $\mathbf { G M } ( 1 , 1 )$ 模型[J]．测绘科学,2011,36 (6): 184-186.   
[12] Kilbas AA,Srivastava H M,Trujillo JJ.Theory and applications of fractional differential equations,volume204,North-Holland mathematics studies [M].[S.1.] : Elsevier Science Publishers,2006: 433-463.   
[13] Wu L,Liu S,Yao L,et al.Grey system model with the fractional order accumulation [J].Communications in Nonlinear Science & Numerical Simulation,2013,18(7): 1775-1785.   
[14] Mao S,Zhu M, Yan X,et al. Modeling mechanism ofa novel fractional grey model based on matrix analysis [J].Journal of Systems Engineering and Electronics,2016,27(5): 1040-1053.   
[15]毛树华，高明运，肖新平.分数阶累加时滞GM(1,N，T）模型及其应 用[J]．系统工程理论与实践,2015,35(2):430-436.   
[16]Mao S,Gao M,Xiao X,et al.A novel fractional grey system model and its application [J].Applied Mathematical Modelling,2016,40(7-8):5063- 5076.   
[17]Ma W,Zhu X,Wang M.Forecasting iron ore import and consumption of China using grey model optimized by particle swarm optimization algorithm [J].Resources Policy,2013,38(4): 613-620.   
[18]Rashedi E,Nezamabadi-pour H, Saryazdi S.GSA:A gravitational search algorithm [J].Information Sciences,2009,179(13):2232-2248.   
[19] Tofallis C.Erratum: A better measure of relative prediction accuracy for model selection and model estimation [J].Journal of the Operational Research Society,2015,66 (3): 524-524.   
[20] LiChaoshun，Li Hongshun，Kou Pangao．Piecewise function based gravitational search algorithm and its application on parameter identification of AVR system [J]. Neurocomputing,2014,124 (2): 139-148.