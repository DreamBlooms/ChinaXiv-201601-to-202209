# 带加性时变时滞的不确定神经网络鲁棒散耗性研究‘

杨飞¹，唐乾²，林果园1

(1．中国矿业大学 计算机科学与技术学院，江苏 徐州 221000;2.中国电子科技集团公司第二十八研究所，南京210007)

摘要：针对加性时变时滞不确定神经网络的时滞相关鲁棒耗散性问题，提出了一种更一般化的激活函数。与以往研究不同，充分考虑了关于神经元激活函数和加性时变时滞的充分信息。通过使用一些新的积分项构造合适的Lyapunov-Krasovskii泛函(LKF)，并利用新生成的单积分不等式来计算其导数，包括延森不等式和维特林积分不等式的特殊情形。利用线性矩阵不等式（LMI）技术，建立了一个新的时滞相关的不守恒全局渐近稳定性和耗散准则。最终通过计算和数值仿真验证了所提理论的有效性。

关键词：神经网络；人工智能；时变时滞；LKF泛函 中图分类号：TP183 doi:10.19734/j.issn.1001-3695.2018.06.0501

# Research on robust dissipation of uncertain neural networks with additive time-varying delays

Yang Fei1, Tang Qian²,Lin Guoyuan1 (1.SchoolofComputerScience&Technology,ChinaUniversityofMining&TechnologyXuzhouJiangsu21ooo,China;2. The28th Research Institute of China Electronics Technology Group Corporation,Nanjing 210oo7,China)

Abstract:Aimatthe problemof thedelaydependentrobust disipative problemofuncertain neural networkswithaditive time-varyingdelays,ageneralizedactivationfunctionswas studied.Differentfrompreviousstudies,some sufficientiformation on neuron activation function and additive time-varyingdelays has been considered.Byconstructing a suitable LyapunovKrasovskiifunctional (LKF）with some new integral terms,and estimatingtheirderivative byusing newlydeveloped single integraliequalitythat includesJensen'sinequalityand Wirtinger-based integral inequalityasaspecialcase.Anewdelaydependentlessconservativeglobalasymptoticstabilityanddissipativecriteriahavebeen establishedintheformoflinearmatrix inequalities (LMIs)technique.Finally,tevalidityoftheproposed theoryisverifiedbycalculationandnumerical simulation. Key words: neural network; artificial intelligence; time-varying delays; Lyapunov-Krasovskii functional

# 0 引言

众所周知，神经网络（NN）因其在信号处理、模式识别、组合优化等多个实际系统中的广泛应用而引起了越来越多学者的研究兴趣[1\~4]。而以上这些应用都依赖于系统的动态性能。另一方面，时间延迟通常影响系统行为，如不稳定、性能差、振荡等[5-6]。因此，需要深入研究具有时滞的神经网络的动力学行为。

一般情况下，假设状态变量的时间延迟以简单或单数形式出现。在文献[7]中，引入了一种新的系统模型，该模型包含状态向量在某种意义下的连续时变延迟分量。文献[7]所提的系统模型可以应用于多种场合，如远程控制、网络控制系统(NCS)。在 NCS中，有时在两个节点之间传输的信号可以是系统双段的。因此，在文献[7]中，通过可变的传输特性，考虑了两个延时分量的系统，此类时延比单时延具有更强的应用意义。因此，带加性时变时滞的概念在神经网络中的稳定性分析中得到了广泛的关注[8\~10]。近几年来，研究者一直致力于研究具有加性时滞的神经网络的稳定性，并取得了良好的结果。在文献[10]中，利用自由权矩阵法，提出了包含马尔可夫跳变参数和加性时滞的广义NNS 的稳定性判据。在文献[9]中，通过引入一个新的增强LKF，利用系统的加性时滞信息，提出了改进的稳定性判据。近年来，文献[11]研究了具有两个附加时变时滞分量的不确定神经网络的鲁棒时滞相关稳定性判据。在文献[12]中，通过构造合适的Lyapunov泛函，并利用自由加权矩阵方法，导出了具有可加时变延迟分量神经网络的一些新的渐近准则。在文献[13]中，提出了基于二次凸组合的依赖于模式的加时变时滞的LKF方法的较不保守的稳定性条件。最近，在文献[14]中，提出了一种改进的神经网络稳定性准则方法，该方法具有加性的时变时

延和泄漏延迟。

另一方面，耗散性分析是神经网络研究的热点之一，它是物理系统的与能量损失或耗散的直观现象密切相关一个基础属性。Willems首先介绍了耗散系统在动力系统中的概念，此后，文献[15]将该概念推广到工作中的非线性系统中。耗散理论为控制系统的设计和分析提供了能量相关的输入/输出描述模型的基本思想。它在现代控制应用，如机器人、主动减振、机电系统、内燃机、电路理论等方向提供了更灵活的理论基础。

在以上研究的启发下，本文利用一个更一般的激活函数方法，然后将该条件推广到寻址神经网络的耗散性分析上。本文的主要工作是尽可能地减少以往研究中的保守性。为此，考虑了一个新的单积分不等式，以获得比最近研究工作更优越的结果。同时，不等式还考虑了延森不等式和维特林格积分不等式两个特例。此外，还对神经元激活函数进行了更进一步的研究，将神经元激活函数的界分为两个子区间，定义一个参数 $\sigma$ ，有$L _ { i } ^ { \sigma } = L _ { i } ^ { - } + \delta ( L _ { i } ^ { + } - L _ { i } ^ { - } )$ 和 $L _ { i } ^ { - } \leq \frac { g _ { i } ( \sigma _ { 1 } ) - g _ { i } ( \sigma _ { 2 } ) } { \sigma _ { 1 } - \sigma _ { 2 } } \leq L _ { i } ^ { \delta }$ （20$L _ { i } ^ { \delta } \leq \frac { g _ { i } ( \sigma _ { 1 } ) - g _ { i } ( \sigma _ { 2 } ) } { \sigma _ { 1 } - \sigma _ { 2 } } \leq L _ { i } ^ { + }$ 。此外，一般化的激活函数概念进一步扩展到加性时变延迟分量。最后，通过三个算例验证了该方法的有效性。

# 1 问题描述与预备知识

首先介绍本文将要用到的一些概念， $\ast$ 表示对称块矩阵主对角线下面的元素， $\mathbb { R } ^ { n }$ 表示 $n$ 维欧几里得空间， $\mathbb { R } ^ { m \times n }$ 是 $m \times n$ 维实矩阵， $\left\| \cdot \right\|$ 表示欧几里得范数， $P$ 是对称正定矩阵， $\boldsymbol { I } _ { n _ { } }$ 是单位矩阵。diag{}表示块对角矩阵。对于对称矩阵 $^ { A , B }$ ，$A > B$ 则意味着 $A - B$ 是正定的。 $N ^ { T }$ 是 $N$ 的转置矩阵。 $L ^ { n }$ 是$n$ 维平方可积函数向量空间。

在本章中考虑了具有加性时变时滞的不确定神经网络：

$$
\begin{array} { r l } & { \dot { \boldsymbol { x } } ( t ) = - ( D + \Delta D ( t ) ) \boldsymbol { x } ( t ) + ( A + \Delta A ( t ) ) f ( \boldsymbol { x } ( t ) ) } \\ & { \qquad + ( B + \Delta B ( t ) ) f ( \boldsymbol { x } ( t - \boldsymbol { \tau } _ { 1 } ( t ) - \boldsymbol { \tau } _ { 2 } ( t ) ) ) + \boldsymbol { \eta } } \\ & { \boldsymbol { x } ( t ) = \boldsymbol { \psi } ( t ) , t \in [ - \tau , 0 ] } \end{array}
$$

其中： $x ( t ) = [ x _ { 1 } ( t ) , x _ { 2 } ( t ) , . . . , x _ { n } ( t ) ] ^ { T } \in \mathbb { R } ^ { n }$ 表示与 $\mathfrak { n }$ 个神经元相关的状态向量； $D \in \mathbb { R } ^ { n \times n }$ 是一个正对角矩阵且每一个 $d _ { i } > 0$ ·$A \in \mathbb { R } ^ { n \times n }$ 和 $\ b { B } \in \mathbb { R } ^ { n \times n }$ 分别是已知的连接矩阵和延迟连接权矩阵； $f ( x ( \cdot ) ) = [ f _ { 1 } ( x ( \cdot ) ) , f _ { 2 } ( x ( \cdot ) ) , . . . , f _ { n } ( x ( \cdot ) ) ] ^ { T } \in \mathbb { R } ^ { n }$ 表示神经元激活函数； $\boldsymbol { \eta } = [ \eta _ { 1 } , \eta _ { 1 } , . . , \eta _ { n } ]$ 表示输出向量； $\psi ( t )$ 是初始化条件;实值矩阵 $\Delta D ( t ) , \Delta A ( t )$ 和 $\Delta B ( t )$ 代表式(2)中的有界范数参数不确定性：

$$
[ \Delta D ( t ) \Delta A ( t ) \Delta A ( t ) ] = C F ( t ) { \big | } { \mathcal { E } } _ { d } { \mathcal { E } } _ { a } { \mathcal { E } } _ { b } { \big | }
$$

其中： $C$ 和 $\mathcal { E } _ { d } , \mathcal { E } _ { a } , \mathcal { E } _ { b }$ 是已知的常数矩阵；未知实时变矩阵$\ b { F } ( t ) \in \mathbb { R } ^ { n \times n }$ 满足

$$
F ^ { T } ( t ) F ( t ) \leq I , \forall t > 0
$$

接下来的假设、定义和引理在推导主要结果中起着重要的作用。

假设 $H _ { 1 }$ ：时变时滞 $\tau _ { 1 } ( t ) , \tau _ { 2 } ( t )$ 表示加性时变时滞，并满足下列条件：

$$
\left\{ \begin{array} { l l } { 0 \leq \tau _ { 1 } ( t ) \leq \tau _ { 1 } , \dot { \tau } _ { 1 } ( t ) \leq u _ { 1 } } \\ { 0 \leq \tau _ { 2 } ( t ) \leq \tau _ { 2 } , \dot { \tau } _ { 2 } ( t ) \leq u _ { 2 } } \end{array} \right.
$$

其中： $\tau _ { 1 } , \tau _ { 2 }$ 和 $u _ { 1 } , u _ { 2 }$ 是已知实常数。为了简单起见，本文定义 $\tau ( t ) = \tau _ { 1 } ( t ) + \tau _ { 2 } ( t ) \ , \tau = \tau _ { 1 } + \tau _ { 2 }$ 和 $\boldsymbol { u } = \boldsymbol { u } _ { 1 } + \boldsymbol { u } _ { 2 }$

假设 $H _ { 2 }$ ：式(1)中的每一个神经元激活函数 $f _ { i } ( \cdot )$ 是连续有界的，并满足

$$
L _ { i } ^ { - } \leq \frac { f _ { i } ( \sigma _ { 1 } ) - f _ { i } ( \sigma _ { 2 } ) } { \sigma _ { 1 } - \sigma _ { 2 } } \leq L _ { i } ^ { + }
$$

$$
f _ { i } ( 0 ) = 0 , ~ \sigma _ { 1 } , \sigma _ { 2 } \in \mathbb { R } , i = 1 , 2 , . . . , n
$$

其中： $\boldsymbol { L } _ { \boldsymbol { i } } ^ { - }$ 和 $\boldsymbol { L } _ { \boldsymbol { i } } ^ { + }$ 是已知实数标量，取值可正、可负或为0。这意味着所得到的激活函数可以是非单调的，并且比通常的sigmoid函数和Lipschitz 条件更一般化。

在假设 $H _ { \sb 2 }$ 下，系统式(1)存在一个平衡点 $\overline { { x } }$ 。通过转换公式 $y ( \cdot ) = x ( \cdot ) - \overline { { x } } , g ( y ( t ) ) = f ( ( y ( t ) + \overline { { x } } ) + \eta ) - f ( \overline { { x } } + \eta )$ 和$\varphi ( t ) = [ \psi ( t ) ]$ ，系统式(1)能够转换为以下形式：

$$
\left\{ \begin{array} { l l } { \dot { y } ( t ) = - ( D + \Delta D ( t ) ) y ( t ) + ( A + \Delta A ( t ) ) g ( y ( t ) ) } \\ { \qquad + ( B + \Delta B ( t ) ) g ( t - \tau _ { 1 } ( t ) - \tau _ { 2 } ( t ) ) } \\ { y ( t ) = \varphi ( t ) , t \in [ - \tau , 0 ] } \end{array} \right.
$$

假设 $H _ { 3 }$ ：式(6)的每一个激活函数 $g _ { i } ( \cdot )$ 都是连续有界的，并满足

$$
L _ { i } ^ { - } \leq \frac { g _ { i } ( \sigma _ { 1 } ) - g _ { i } ( \sigma _ { 2 } ) } { \sigma _ { 1 } - \sigma _ { 2 } } \leq L _ { i } ^ { + }
$$

$$
g _ { i } ( 0 ) = 0 , ~ \sigma _ { 1 } , \sigma _ { 2 } \in \mathbb { R } , i = 1 , 2 , . . . , n
$$

当式(6)出现一个外部干扰时，可以写成如下形式：

$$
\left\{ \begin{array} { l l } { \dot { y } ( t ) = - ( D + \Delta D ( t ) ) y ( t ) + ( A + \Delta A ( t ) ) g ( y ( t ) ) } \\ { \qquad + ( B + \Delta B ( t ) ) g ( t - \tau _ { 1 } ( t ) - \tau _ { 2 } ( t ) ) + w ( t ) } \\ { y ( t ) = \varphi ( t ) , t \in [ - \tau , 0 ] } \\ { z ( t ) = g ( y ( t ) ) } \end{array} \right.
$$

为了简单起见，式(8)可以表示成如下形式：

$$
\left\{ \begin{array} { l l } { \dot { y } ( t ) = - D y ( t ) + A g ( y ( t ) ) + B g ( t - \tau _ { 1 } ( t ) - \tau _ { 2 } ( t ) ) } \\ { \qquad + w ( t ) + C p ( t ) } \\ { p ( t ) = F ( t ) q ( t ) } \\ { q ( t ) = \varepsilon _ { d } y ( t ) + \varepsilon _ { a } g ( y ( t ) ) + \varepsilon _ { b } g ( y ( t - \tau _ { 1 } ( t ) - \tau _ { 2 } ( t ) ) ) } \\ { \qquad \quad y ( t ) = \varphi ( t ) , t \in [ - \tau , 0 ] } \\ { \qquad \quad z ( t ) = g ( y ( t ) ) } \end{array} \right.
$$

其中： $z ( t ) = g ( y ( t ) )$ 是式(8)中的输出信号； $w ( t )$ 是不能完全测量的干扰输入并假设 $w ( t ) \in L [ 0 , \infty )$ ,这意味着它是有限能量的函数。同时，定义 $( Q , S , R ) - \gamma$ -散耗度，其中， $\gamma$ 是散耗性能水平。有关 $( Q , S , R ) - \gamma$ 的具体定义可参考文献[16,17]。

定义1不确定神经网络式(8)是严格 $( Q , S , R ) - \gamma$ 散耗的，如果 $\gamma > 0$ 且下面的不等式在0初始化条件下成立：

$$
G ( w , z , t _ { f } ) \ge \gamma \big < w , w \big > _ { t _ { r } } , \forall t _ { t } \ge 0
$$

其中： $G ( w , z , t _ { f } )$ 是能量提供函数，被定义为

$$
G ( w , z , t _ { f } ) = \left. z , Q z \right. _ { t _ { f } } + 2 \left. z , S w \right. _ { t _ { f } } + \left. w , R w \right. _ { t _ { f } } , \forall t _ { f } \geq 0
$$

其中： $Q , S , R$ 是实值矩阵，且 $Q , R$ 是对称的。$\left. a , b \right. _ { t _ { f } } = \int _ { 0 } ^ { t _ { f } } a ^ { T } d t$ 。因此，式(10)可用成不确定神经网络式(8)的散耗度性能写成如下形式：

$$
J _ { \gamma , t _ { f } } = \int _ { 0 } ^ { t _ { f } } \left[ \left( \begin{array} { l } { z ( t ) } \\ { w ( t ) } \end{array} \right) ^ { T } \left( \begin{array} { l l } { Q } & { S } \\ { * } & { R } \end{array} \right) \left( \begin{array} { l } { z ( t ) } \\ { w ( t ) } \end{array} \right) - \gamma w ( t ) ^ { T } w ( t ) \right] d t
$$

引理 $\mathbf { 1 } ^ { [ 1 8 ] }$ 对于任意的常数矩阵 $W \in \mathbb { R } ^ { n \times n }$ $W > 0$ ，和一个标量函数 $y ( \alpha ) : [ a , b ] \to \mathbb { R } ^ { n }$ ，则

$$
- ( b - a ) \int _ { a } ^ { b } y ^ { T } ( \alpha ) W y ( \alpha ) d \alpha \leq \left( \int _ { a } ^ { b } y ( \alpha ) d \alpha \right) ^ { T } W \left( \int _ { a } ^ { b } y ( \alpha ) d \alpha \right)
$$

引理 $2 ^ { \left[ 1 9 \right] }$ 令 $f _ { 1 } , f _ { 2 } , f _ { 3 } , . . . , f _ { N } : \mathbb { R } ^ { m }  \mathbb { R }$ 在 $\mathbb { R } ^ { m }$ 上一个开子集 $\mathrm { ~ D ~ }$ 有一个正值，则在 $\mathrm { ~ D ~ }$ 上 $f _ { i }$ 的反凸组合满足

$$
\operatorname* { m i n } _ { \{ \alpha _ { i } | \alpha _ { i } > 0 , \sum _ { i } \alpha _ { i } = 1 \} } \sum _ { i } { \frac { 1 } { \alpha _ { 1 } } } f _ { i } ( t ) = \sum _ { i } f _ { i } ( t ) + \operatorname* { m a x } _ { g _ { i j } ( t ) } \sum _ { i \neq j } g _ { i j } ( t )
$$

Subject to

$$
\{ g _ { i j } ( t ) : \mathbb { R } ^ { m }  \mathbb { R } , g _ { i , j } ( t ) \triangleq g _ { j , i } ( t ) , { [ \begin{array} { l l } { f _ { i } ( t ) } & { g _ { i , j } ( t ) } \\ { g _ { i , j } ( t ) } & { f _ { i } ( t ) } \end{array} ] } \geq 0 \}
$$

引理3对于任意的常量矩阵 $x , y , z \in \mathbb { R } ^ { n \times n }$ 和一个正矩阵

$\begin{array} { r } { W \in \mathbb { R } ^ { n \times n } \ , \ l _ { 1 } = \left[ \begin{array} { c c } { W } & { x } \\ { x ^ { T } } & { W } \end{array} \right] , \ l _ { 2 } = \left[ \begin{array} { c c } { 3 W } & { y } \\ { y ^ { T } } & { 3 W } \end{array} \right] \sharp \mathbb { I } \ l _ { 3 } = \left[ \begin{array} { c c } { 5 W } & { z } \\ { z ^ { T } } & { 5 W } \end{array} \right] , } \end{array}$ 标量 $0 \leq \tau _ { 0 } \leq \tau ( t ) \leq \tau _ { M }$ 和向量函数 $\dot { y } : [ - \tau _ { M } , - \tau _ { 0 } ] \to \mathbb { R } ^ { n }$ ，使得积分被明确定义，则有

$$
\begin{array} { r l } & { \quad - ( \tau _ { W } - \tau _ { 0 } ) \int _ { - \tau _ { e } } ^ { \tau _ { h } } \dot { y } ^ { T } ( \boldsymbol { \omega } ) W \dot { y } ( \boldsymbol { \omega } ) d \boldsymbol { \omega } } \\ & { \quad \le E ^ { T } ( t ) [ e _ { 3 } ^ { \tau _ { h } } - e _ { 4 } ^ { 2 } ] [ W ^ { T } \| e _ { 5 } ^ { T } - e _ { 2 } ^ { 2 } \| ^ { T }  } \\ & { \quad    [ e _ { 2 } ^ { T } - e _ { 4 } ] ] X ^ { T } \| e _ { 2 } ^ { T } - e _ { 4 } ] } \\ & { \quad - E ^ { T } ( t ) [ e _ { 3 } ^ { T } + e _ { 2 } - 2 e _ { 5 } ] [ 3 W \mathcal { V } ] [ e _ { 3 } ^ { T } + e _ { 2 } - 2 e _ { 5 } ] ^ { T }  } \\ & { \quad    - E ^ { T } ( t ) [ e _ { 2 } ^ { T } + e _ { 4 } - 2 e _ { 6 } ] [ y ^ { T } \mathcal { I } \mathcal { M } ] [ e _ { 2 } ^ { T } + e _ { 4 } - 2 e _ { 6 } ] ^ { T } ] E ( t )  } \\ & { \quad - E ^ { T } ( t ) [ e _ { 3 } ^ { T } - e _ { 4 } + 6 e _ { 6 } - 1 2 e _ { 6 } ] [ 5 W \mathcal { U }    } \\ & { \quad     \times [ e _ { 3 } ^ { T } - e _ { 2 } + 6 e _ { 3 } - 1 2 e _ { 6 } ] ] Z ^ { T } \mathcal { K } \mathcal { W } ] } \\ & { \quad \times [ e _ { 2 } ^ { T } - e _ { 4 } + 6 e _ { 5 } - 1 2 e _ { 7 } ] ^ { T } E ^ { T } ( t ) } \end{array}
$$

其中：

$$
\begin{array} { l } { { \displaystyle E ( t ) = \{ y ^ { T } ( t ) y ^ { T } ( t - \tau ( t ) ) y ^ { T } ( t - \tau _ { M } ) y ^ { T } ( t - \tau _ { 0 } ) } y ^ { T } ( t - \tau _ { 0 } ) }  \\ { { \displaystyle \frac { 1 } { \tau _ { M } - \tau _ { 0 } } \int _ { t - \tau _ { M } } ^ { t - \tau ( t ) } y ^ { T } ( \alpha ) d \alpha \frac { 1 } { \tau ( t ) - \tau _ { 0 } } \int _ { t - \tau ( t ) } ^ { t - \tau _ { 0 } } y ^ { T } ( \alpha ) d \alpha } }  \\ { { \displaystyle \frac { 1 } { ( \tau _ { M } - \tau ( t ) ) ^ { 2 } } \int _ { t - \tau _ { u } } ^ { t - \tau ( t ) } y ^ { T } ( \alpha ) d \alpha } } \\ { { \displaystyle \frac { 1 } { ( \tau ( t ) - \tau _ { 0 } ) ^ { 2 } } \int _ { t - \tau ( t ) } ^ { t - \tau _ { 0 } } \int _ { \beta } ^ { t } y ^ { T } ( \alpha ) d \alpha d \beta \} ^ { T } } } \end{array}
$$

（204 $\boldsymbol { e } _ { i } \in \mathbb { R } ^ { 8 n \times n }$ 0 $\cdot j = 1 , 2 , 3 , . . . , 8 )$ 。为了简单起见，本文将其表示为矩阵和向量，如 $e _ { 6 } = [ 0 _ { n } \ 0 _ { n } \ 0 _ { n } \ 0 _ { n } \ 0 _ { n } \ I _ { n } \ 0 _ { n } \ 0 _ { n } ] ^ { T }$ 。

证明当 $0 \leq \tau _ { 0 } \leq \tau ( t ) \leq \tau _ { M }$ 时，有

$$
+ [ y ( t - \tau _ { M } ) - y ( t - \tau ( t ) ) + \frac { 6 } { \tau _ { M } - \tau ( t ) } \int _ { t - \tau _ { M } } ^ { t - \tau ( t ) } y ( \alpha ) d \alpha - \frac { 1 2 } { ( \tau _ { M } - \tau ( t ) ) ^ { 2 } } \int _ { t - \tau _ { M } } ^ { t - \tau ( t ) } \int _ { \beta } ^ { t } y ( \alpha ) d \alpha d \beta ] ^ { T }
$$

$$
\times 5 W [ y ( t - \tau _ { M } ) - y ( t - \tau ( t ) ) + \frac { 6 } { \tau _ { M } - \tau ( t ) } \int _ { t - \tau _ { M } } ^ { t - \tau ( t ) } y ( \alpha ) d \alpha - \frac { 1 2 } { ( \tau _ { M } - \tau ( t ) ) ^ { 2 } } \int _ { t - \tau _ { M } } ^ { t - \tau ( t ) } \int _ { \beta } ^ { t } y ( \alpha ) d \alpha d \beta ] \}
$$

$$
\displaystyle - \frac { \tau _ { M } - \tau _ { 0 } } { \tau _ { M } - \tau ( t ) } \{ [ y ( t - \tau ( t ) ) - y ( t - \tau _ { 0 } ) ] ^ { T } W [ y ( t - \tau ( t ) ) - y ( t - \tau _ { 0 } ) ] + [ y ( t - \tau ( t ) ) - y ( t - \tau _ { 0 } ) ] \} \log ( t - \tau _ { 0 } ) ,
$$

$$
- \frac { 2 } { \tau ( t ) - \tau _ { 0 } } \int _ { t - \tau ( t ) } ^ { t - \tau _ { 0 } } \left[ y ( \alpha ) d \alpha \right] ^ { T } 3 W [ y ( t - \tau ( t ) ] + y ( t - \tau _ { 0 } ) - \frac { 2 } { \tau ( t ) - \tau _ { 0 } } \int _ { t - \tau ( t ) } ^ { t - \tau _ { 0 } } y ( \alpha ) d \alpha ]
$$

$$
+ [ y ( t - \tau ( t ) ) - y ( t - \tau _ { 0 } ) + \frac { 6 } { \tau ( t ) - \tau _ { 0 } } \int _ { t - \tau ( t ) } ^ { t - \tau _ { 0 } } y ( \alpha ) d \alpha - \frac { 1 2 } { ( \tau ( t ) - \tau _ { 0 } ) ^ { 2 } } \int _ { t - \tau ( t ) } ^ { t - \tau _ { 0 } } \int _ { \beta } ^ { t } y ( \alpha ) d \alpha d \beta ] ^ { T }
$$

$$
\begin{array} { r l } & { \times 5 W [ y ( t - \tau ( t ) ) - y ( t - \tau _ { 0 } ) + \cfrac { 6 } { \tau ( t ) - \tau _ { 0 } } \int _ { t - \tau _ { u } } ^ { t - \tau ( t ) } y ( \alpha ) d \alpha - \cfrac { 1 2 } { \left( \tau ( t ) - \tau _ { 0 } \right) ^ { 2 } } \int _ { t - \tau ( t ) } ^ { t - \tau _ { 0 } } \int _ { \beta } ^ { t } y ( \alpha ) d \alpha d \beta ] \} } \\ & { = - ( 1 + V _ { 1 } ) \{ E ^ { T } ( t ) ( e _ { 3 } - e _ { 2 } ) W ( e _ { 3 } - e _ { 2 } ) ^ { T } E ( t ) + E ^ { T } ( t ) ( e _ { 3 } + e _ { 2 } - 2 e _ { 5 } ) 3 W ( e _ { 3 } + e _ { 2 } - 2 e _ { 5 } ) ^ { T } E ( t ) } \\ & { + E ^ { T } ( t ) ( e _ { 3 } - e _ { 2 } + 6 e _ { 5 } - 1 2 e _ { \tau } ) 5 W ( e _ { 3 } - e _ { 2 } + 6 e _ { 5 } - 1 2 e _ { \tau } ) ^ { T } E ^ { T } ( t ) \} } \\ & { - ( 1 + V _ { 2 } ) \{ E ^ { T } ( t ) ( e _ { 2 } - e _ { 4 } ) W ( e _ { 2 } - e _ { 4 } ) ^ { T } E ( t ) + E ^ { T } ( t ) ( e _ { 2 } + e _ { 4 } - 2 e _ { 6 } ) 3 W ( e _ { 2 } + e _ { 4 } - 2 e _ { 6 } ) ^ { T } E ( t ) } \\ & { + E ^ { T } ( t ) ( e _ { 2 } - e _ { 4 } + 6 e _ { 6 } - 1 2 e _ { 8 } ) 5 W ( e _ { 2 } - e _ { 4 } + 6 e _ { 6 } - 1 2 e _ { 8 } ) ^ { T } E ^ { T } ( t ) \} } \end{array}
$$

其中： $V _ { 1 } = \frac { \tau ( t ) - \tau _ { 0 } } { \tau _ { M } - \tau ( t ) }$ 和V $V _ { 2 } = \frac { \tau _ { M } - \tau ( t ) } { \tau ( t ) - \tau _ { 0 } }$ 因此，对于任意的常

量 $x , y , z$ ，有

$$
\begin{array} { r l } & { \quad - V _ { 1 } E ^ { T } ( t ) ( e _ { 3 } - e _ { 2 } ) W ( e _ { 3 } - e _ { 2 } ) ^ { T } E ( t ) - V _ { 2 } E ^ { T } ( t ) ( e _ { 2 } - e _ { 4 } ) W ( e _ { 2 } - e _ { 4 } ) ^ { T } E ( t ) } \\ & { \quad \le - E ^ { T } ( t ) ( e _ { 3 } - e _ { 2 } ) x ^ { T } ( e _ { 3 } - e _ { 2 } ) ^ { T } E ( t ) - E ^ { T } ( t ) ( e _ { 2 } - e _ { 4 } ) x ( e _ { 2 } - e _ { 4 } ) ^ { T } E ( t ) } \\ & { \quad - V _ { 1 } E ^ { T } ( t ) ( e _ { 3 } + e _ { 2 } - 2 e _ { 3 } ) 3 W ( e _ { 3 } + e _ { 2 } - 2 e _ { 5 } ) ^ { T } E ( t ) - V _ { 2 } E ^ { T } ( t ) ( e _ { 2 } + e _ { 4 } - 2 e _ { 6 } ) 3 W ( e _ { 2 } + e _ { 4 } - 2 e _ { 6 } ) ^ { T } E ( t ) } \\ & { \quad \le - E ^ { T } ( t ) ( e _ { 3 } + e _ { 2 } - 2 e _ { 5 } ) y ^ { T } ( e _ { 3 } + e _ { 2 } - 2 e _ { 5 } ) ^ { T } E ( t ) - E ^ { T } ( t ) ( e _ { 2 } + e _ { 4 } - 2 e _ { 6 } ) y ( e _ { 2 } + e _ { 4 } - 2 e _ { 6 } ) ^ { T } E ( t ) } \\ & { \quad - V _ { 1 } E ^ { T } ( t ) ( e _ { 3 } - e _ { 2 } + 6 e _ { 5 } - 1 2 e _ { 7 } ) 5 W ( e _ { 3 } - e _ { 2 } + 6 e _ { 5 } - 1 2 e _ { 7 } ) ^ { T } E ( t ) - V _ { 2 } E ^ { T } ( t ) ( e _ { 2 } - e _ { 4 } + 6 e _ { 6 } } \\ & { \quad + 1 2 e _ { 6 } ) 5 W ( e _ { 2 } - e _ { 4 } + 6 e _ { 6 } + 1 2 e _ { 5 } ) ^ { T } E ( t ) } \\ & { \quad \le - E ^ { T } ( t ) ( e _ { 3 } - e _ { 2 } + 6 e _ { 5 } - 1 2 e _ { 7 } ) \tau ^ { 2 } ( e _ { 3 } - e _ { 2 } + 6 e _ { 5 } - 1 2 e _ { 7 } ) ^ { T } E ( t ) } \\ & { \quad - E ^ { T } ( t ) ( e _ { 2 } - e _ { 4 } + 6 e _ { 6 } + 1 2 e _ { 7 } ) y ( e _ { 2 } - e _ { 2 } + 6 e _ { 6 } - 1 2 e _ { 7 } ) ^ { T } E ( t ) } \\ &  \quad - E ^ { T } ( t ) ( e _ { 2 } - e _ { 4 } + 6 e _ { 6 } + 1 2 e _ { 8 } ) y ( e _ { 2 } - \end{array}
$$

通过简单的移项即可得到式(13)成立，证毕。

# 2 稳定性分析

在本章中根据文献[19]所提的LKF 和LMI技术建立更一般化激活函数的模型。为了简单起见，本文定义矩阵和向量为块矩阵。本节所用到的符号定义如下：

$$
\begin{array} { l } { { \displaystyle \overline { { { L } } } _ { 1 } = d i g a ( L _ { 1 } ^ { - } , L _ { 2 } ^ { - } , . . . , L _ { n } ^ { - } ) , \overline { { { L } } } _ { 2 } = d i g a ( L _ { 1 } ^ { + } , L _ { 2 } ^ { + } , . . . , L _ { n } ^ { + } ) } } \\ { { \displaystyle \overline { { { L } } } _ { 3 } = d i g a ( L _ { 1 } ^ { - } L _ { 1 } ^ { + } , L _ { 2 } ^ { - } L _ { 2 } ^ { + } , . . . , L _ { n } ^ { - } L _ { n } ^ { + } ) } } \\ { { \displaystyle \overline { { { L } } } _ { 4 } = d i g a ( \frac { L _ { 1 } ^ { - } + { L _ { 1 } ^ { + } } } { 2 } , \frac { L _ { 2 } ^ { - } + L _ { 2 } ^ { + } } { 2 } , . . . , \frac { L _ { n } ^ { - } + { L _ { n } ^ { + } } } { 2 } ) } } \\ { { \displaystyle L ^ { \sigma } = d i g a ( L _ { 1 } ^ { \sigma } , L _ { 2 } ^ { \sigma } , . . . , L _ { n } ^ { \sigma } ) = \overline { { { L } } } _ { 3 } + \sigma ( \overline { { { L } } } _ { 4 } - \overline { { { L } } } _ { 3 } ) } } \end{array}
$$

$$
\begin{array} { r l } & { \xi ^ { T } ( t ) = \{ y ^ { T } ( t ) \} ^ { \tau } ( t ) ( t - \tau ( t ) ) y ^ { T } ( t ) ( t - \tau ) } \\ & { y ^ { T } ( t ) ( t - \tau _ { 1 } ( t ) ) y ^ { T } ( t ) ( t - \tau _ { 1 } ) y ^ { T } ( t ) ( t - \tau _ { 2 } ( t ) ) } \\ & { y ^ { T } ( t ) ( t - \tau _ { 2 } ) g ^ { T } ( y ( t ) ) g ^ { T } ( t - \tau ( t ) ) g ^ { T } ( t ) ( t - \tau ) } \\ & { g ^ { T } ( t ) ( t - \tau _ { 1 } ( t ) ) g ^ { T } ( t ) ( t - \tau _ { 1 } ) g ^ { T } ( t ) ( t - \tau _ { 2 } ( t ) ) } \\ & { g ^ { T } ( t ) ( t - \tau _ { 2 } ) \frac { 1 } { \tau - \tau ( t ) } \int _ { t - \tau } ^ { t - \tau ( t ) } y ^ { T } ( s ) d s \frac { 1 } { \tau ( t ) } \int _ { t - \tau ( t ) } ^ { 1 } y ^ { T } ( s ) d s } \\ & { \frac { 1 } { ( \tau - \tau ( t ) ) ^ { 2 } } \int _ { 0 } ^ { t - \tau ( t ) } y ^ { T } ( s ) d s d \theta \ \frac { 1 } { ( \tau ( t ) ) ^ { 2 } } \int _ { t - \tau ( t ) } ^ { t - \tau ( s ) } \int _ { 0 } ^ { \tau } y ^ { T } ( s ) d s d \theta } \\ &  \dot { y } ^ { T } ( t ) \ : p ^ { T } ( t ) \} \end{array}
$$

$$
\begin{array} { r l } { \mathcal { D } _ { k _ { 1 } } ^ { k _ { 2 } } - \mathcal { D } _ { k _ { 2 } } ^ { k _ { 1 } } \mathcal { R } _ { k _ { 2 } } ^ { k _ { 2 } } + \mathcal { D } _ { k _ { 1 } } ^ { k _ { 2 } } \mathcal { R } _ { k _ { 2 } } ^ { k _ { 1 } } } & { = \frac { \mathcal { N } _ { k _ { 1 } } ^ { k _ { 2 } } } { \mathcal { N } _ { k _ { 1 } } ^ { k _ { 2 } } } } \\ { \mathcal { D } _ { k _ { 1 } } ^ { k _ { 1 } } - \mathcal { D } _ { k _ { 2 } } ^ { k _ { 1 } } \mathcal { R } _ { k _ { 2 } } ^ { k _ { 2 } } + \mathcal { D } _ { k _ { 1 } } ^ { k _ { 2 } } \mathcal { R } _ { k _ { 2 } } ^ { k _ { 1 } } } & { = \mathcal { N } _ { k _ { 1 } } ^ { k _ { 2 } } \mathcal { R } _ { k _ { 2 } } ^ { k _ { 2 } } } \\ { \quad } & { \quad + \mathcal { N } _ { k _ { 1 } } ^ { k _ { 2 } } \mathcal { R } _ { k _ { 2 } } ^ { k _ { 1 } } + \mathcal { D } _ { k _ { 1 } } ^ { k _ { 2 } } \mathcal { R } _ { k _ { 2 } } ^ { k _ { 1 } } } \\ { \quad } & { = \mathcal { N } _ { k _ { 1 } } ^ { k _ { 2 } } \mathcal { R } _ { k _ { 2 } } ^ { k _ { 1 } } + \mathcal { D } _ { k _ { 1 } } ^ { k _ { 2 } } \mathcal { R } _ { k _ { 2 } } ^ { k _ { 2 } } } \\ { \quad } & { \quad + \mathcal { D } _ { k _ { 1 } } ^ { k _ { 2 } } \mathcal { R } _ { k _ { 2 } } ^ { k _ { 1 } } } \\ { \quad } & { = \mathcal { N } _ { k _ { 1 } } ^ { k _ { 2 } } \mathcal { R } _ { k _ { 2 } } ^ { k _ { 1 } } + \mathcal { D } _ { k _ { 1 } } ^ { k _ { 2 } } \mathcal { R } _ { k _ { 2 } } ^ { k _ { 2 } } } \\ { \mathcal { D } _ { k _ { 1 } } ^ { k _ { 1 } } ( \mathcal { R } _ { k _ { 1 } } ^ { k _ { 2 } } + \mathcal { D } _ { k _ { 1 } } ^ { k _ { 2 } } ) + \mathcal { D } _ { k _ { 1 } } ^ { k _ { 1 } } ( \mathcal { R } _ { k _ { 1 } } ^ { k _ { 2 } } + \mathcal { D } _ { k _ { 1 } } ^ { k _ { 2 } } ) } \\  \mathcal { D } _ { k _ { 1 } } ^ { k _ { 2 } } ( \mathcal { R } _ { k _ { 1 } } ^ { k _ { 1 } } + \ \end{array}
$$

$$
\begin{array} { r l } { \Psi ^ { * } - 2 [ \mathbf { c } _ { 6 } - \mathbf { c } _ { 6 } , \mathbf { \tilde { c } } _ { 7 } - \mathbf { \tilde { c } } _ { 1 6 } , ( \mathbf { c } _ { 7 } , \mathbf { \tilde { c } } _ { 8 } ) ] M _ { 1 } [ \mathbf { c } _ { 1 6 } , \mathbf { \tilde { c } } _ { 6 } , - D _ { 1 } ( \mathbf { c } _ { 1 6 } , \mathbf { \tilde { c } } _ { 1 6 } ) ] } \\ & { - 2 [ \mathbf { c } _ { 1 6 } , \mathbf { c } _ { 1 7 } , \mathbf { \tilde { c } } _ { 1 7 } , \mathbf { \tilde { c } } _ { 1 6 } , \mathbf { \tilde { c } } _ { 1 6 } , \mathbf { \tilde { c } } _ { 1 6 } , \mathbf { \tilde { c } } _ { 1 6 } , \mathbf { \tilde { c } } _ { 1 7 } , \mathbf { \tilde { c } } _ { 2 6 } , \mathbf { \tilde { \nu } } _ { 6 } , \mathbf { \tilde { \nu } } _ { 6 } , \mathbf { \tilde { \nu } } _ { 6 } , \mathbf { \tilde { \nu } } _ { 7 } ] } \\ & { - 2 [ \mathbf { c } _ { 2 6 } , \mathbf { c } _ { 1 6 } , \mathbf { \tilde { c } } _ { 1 5 } , \mathbf { \tilde { \tilde { \nu } } } _ { \tilde { } \tilde { } \tilde { } \tilde { } \tilde { } \tilde { } \mathbf { } } _ { \tilde { } \tilde { } \tilde { } \mathbf { } \tilde { } \mathbf { } \tilde { } \mathbf { } \tilde { } \tilde { } \mathbf { } } \tilde { } \mathbf { } \tilde { } \tilde { } \mathbf { } \tilde { } \mathbf { } } \tilde \mathbf { } \tilde { } \tilde { } \mathbf { } \tilde { } \tilde \nu  \mathrm { } \tilde { } \tilde \mathrm { } \tilde { } \tilde { } \tilde \nu  \mathrm { } \tilde { } \tilde \mathrm { } \tilde { } \tilde { } \nu \mathrm { } \tilde \mathrm { } \tilde { } \tilde { } \nu \mathrm { } \tilde { } \tilde  \mathrm { } \tilde { } \tilde { } \tilde { } \nu \mathrm { } \tilde { } \tilde { } \mathrm { } \tilde { } \nu \mathrm { } \tilde { } \tilde { } \nu \mathrm { } \tilde { } \mathrm { } \tilde { } \nu \mathrm { } \tilde { } \tilde { } \nu \mathrm { } \tilde { } \mathrm { } \tilde { } \nu \mathrm { } \tilde { } \tilde { } \nu \mathrm { } \tilde { } \mathrm { } \tilde { } \nu \mathrm { } \tilde { } \tilde { } \nu \mathrm { } \tilde { } \mathrm { } \tilde { } \nu \mathrm { } \tilde { } \mathrm { } \tilde { } \nu \mathrm { } \tilde { } \nu \mathrm { } \tilde { } \nu \mathrm { } \tilde { } \nu \mathrm { } \tilde { } \nu \mathrm { } \tilde { } \nu \mathrm { } \tilde { }  \end{array}
$$

$$
\begin{array} { r l } & { \Gamma = \varepsilon [ e _ { 1 } \varepsilon _ { d } ^ { T } e _ { 1 } ^ { T } + e _ { 1 } \varepsilon _ { d } ^ { T } \varepsilon _ { a } e _ { 8 } ^ { T } + e _ { 1 } \varepsilon _ { d } ^ { T } \varepsilon _ { b } e _ { 2 } ^ { T } + e _ { 8 } \varepsilon _ { a } ^ { T } \varepsilon _ { d } e _ { 1 } ^ { T } } \\ & { \qquad + e _ { 8 } \varepsilon _ { a } ^ { T } \varepsilon _ { a } e _ { 8 } ^ { T } + e _ { 8 } \varepsilon _ { a } ^ { T } \varepsilon _ { b } e _ { 2 } ^ { T } + e _ { 2 } \varepsilon _ { b } ^ { T } \varepsilon _ { d } e _ { 1 } ^ { T } ] } \\ & { \Phi = 2 [ e _ { 1 } S _ { 1 } + e _ { 1 9 } S _ { 2 } ] [ - e _ { 1 9 } - D e _ { 1 } } \\ & { \qquad + A e _ { 8 } + B e _ { 2 } + C e _ { 2 0 } ] ^ { T } } \\ & { \sum = U _ { 1 } + U _ { 2 } + U _ { 3 } + \Gamma + \Phi } \end{array}
$$

定理1如果假设 $H _ { 1 } , H _ { 2 }$ 和 $H _ { 3 }$ 成立，对于任意正标量$\tau _ { 1 } , \tau _ { 2 } , u _ { 1 } , u _ { 2 }$ 和 $\sigma$ ，不确定神经网络式(6)是全局渐进稳定的，如果存在一个正定矩阵 $P \in \mathbb { R } ^ { n \times n } , Q _ { i } \in \mathbb { R } ^ { n \times n } ( i = 1 , 2 , . . . , 1 2 )$ ，$R _ { j } \in \mathbb { R } ^ { n \times n } \ ( j = 1 , 2 , 3 )$ （204号 ， 正对角矩阵$\Omega , M _ { i } \in \mathbb { R } ^ { n \times n } ( k = 1 , 2 , . . . , 1 2 )$ 和任意矩阵 $x , y , z \in \mathbb { R } ^ { n \times n }$ （$S _ { l } \in \mathbb { R } ^ { n \times n } \ ( l = 1 , 2 )$ 和一个正标量 $\varepsilon$ 使得以下LMI成立：

$$
\Upsilon _ { 1 } = \sum \ + \Psi ^ { i } < 0 ( i = a , b )
$$

证明考虑双积分项的Lyapunov-Krasovskii 泛函：

$$
V ( t ) = { \sum } _ { j = 1 } ^ { 3 } V _ { j } ( t )
$$

其中：

$$
\begin{array} { r l } & { V _ { 1 } ( t ) = y ^ { \top } ( t ) P y ( t ) + 2 \sum _ { i = 1 } ^ { n } w _ { i } \int _ { 0 } ^ { t ( t ) } g _ { i } ( s ) d s } \\ & { V _ { 2 } ( t ) = \textstyle \prod _ { i < \ell \in \mathcal { B } } \big [ \textstyle \mathsf { y } ^ { \top } ( s ) Q _ { 1 } y ( s ) + g ^ { \top } ( y ( s ) ) Q _ { 2 } g ( y ( s ) ) \big ] d s } \\ & { \quad + \textstyle \int _ { t = - \ell \in \mathcal { B } } \big [ \textstyle \mathsf { y } ^ { \top } ( s ) Q _ { 3 } y ( s ) + g ^ { \top } ( y ( s ) ) Q _ { 4 } g ( y ( s ) ) \big ] d s } \\ & { \quad + \textstyle \int _ { t \in \mathcal { B } } ^ { 1 } \big [ \textstyle \mathsf { y } ^ { \top } ( s ) Q _ { 3 } y ( s ) + g ^ { \top } ( y ( s ) ) Q _ { 4 } g ( y ( s ) ) \big ] d s } \\ & { \quad + \textstyle \int _ { t \in \mathcal { B } } ^ { 1 } \big [ \textstyle \mathsf { y } ^ { \top } ( s ) Q _ { 3 } y ( s ) + g ^ { \top } ( y ( s ) ) Q _ { 4 } g ( y ( s ) ) \big ] d s } \\ & { \quad + \textstyle \int _ { t \in \mathcal { B } } ^ { 1 } \big [ \textstyle \mathsf { y } ^ { \top } ( s ) Q _ { 3 } y ( s ) + g ^ { \top } ( y ( s ) ) Q _ { 4 } g ( y ( s ) ) \big ] d s } \\ & { \quad + \textstyle \int _ { t \in \mathcal { B } } ^ { 1 } \big [ \textstyle \mathsf { y } ^ { \top } ( s ) \big ( g ) \big ( g ) + g ^ { \top } ( y ( s ) ) Q _ { 1 } g ( y ( s ) ) \big ] d s } \\ & { \quad + \textstyle \int _ { t \in \mathcal { B } } ^ { 1 } \big [ \textstyle \mathsf { y } ^ { \top } ( s ) Q _ { 1 } y ( s ) + g ^ { \top } ( y ( s ) ) Q _ { 1 } g ( y ( s ) ) \big ] d s } \\ & { \quad + \textstyle \int _ { t \in \mathcal { B } } ^ { 1 } [ \textstyle \mathsf { y } ^ { \top } ( s ) Q _ { 1 } y ( s ) + g ^ { \top } ( y ( s ) ) Q _ { 1 } g ( y ( s ) ) ] d s } \\ & { \quad + \textstyle \int _ { t \in \mathcal { B } } ^ { 1 } [ \textstyle \mathsf { y } ^ { \top } ( s ) Q _ { 1 } y ( s ) + g ^ { \top } ( y ( s ) ) Q _ { 1 } g ( y ( s ) ) ] d s } \end{array}
$$

$$
\begin{array} { l } { { V _ { 3 } ( t ) = \tau { \displaystyle \int _ { t - \tau } ^ { t } } \int _ { \theta } ^ { t } \dot { y } ^ { T } ( s ) R _ { 1 } \dot { y } ( s ) d s d \theta } } \\ { { \ ~ + \left( \tau - \tau _ { 1 } \right) \displaystyle \int _ { - \tau } ^ { - \tau _ { 1 } } \int _ { t + \theta } ^ { t } \dot { y } ^ { T } ( s ) R _ { 2 } \dot { y } ( s ) d s d \theta } } \\ { { \ ~ + \left( \tau - \tau _ { 2 } \right) \displaystyle \int _ { - \tau } ^ { - \tau _ { 2 } } \int _ { t + \theta } ^ { t } \dot { y } ^ { T } ( s ) R _ { 3 } \dot { y } ( s ) d s d \theta } } \end{array}
$$

$V ( t )$ 的时间导数为

$$
{ \dot { V } } ( t ) = \sum _ { j = 1 } ^ { 3 } { \dot { V } } _ { j } ( t )
$$

其中：

$$
\begin{array} { r l } & { \dot { V _ { 1 } } ( t ) = s y m \mathbf { i } _ { \mathbf { j } } ^ { T } ( t ) P \dot { \mathbf { j } } ( t ) \dag + s y m \{ g ^ { T } \left( y ( t ) \right) \Omega \dot { y } ( t ) \} } \\ & { \qquad = \xi ^ { T } ( t ) U _ { 1 } \dot { \xi } ( t ) } \\ & { \dot { V _ { 2 } } ( t ) \le \xi ^ { T } ( t ) U _ { 2 } \xi ( t ) } \\ & { \dot { V _ { 2 } } ( t ) = \tau ^ { 2 } \dot { y } ^ { T } ( t ) R _ { 1 } \dot { y } ( t ) + ( \tau - \tau _ { 1 } ) ^ { 2 } \dot { y } ^ { T } ( t ) R _ { 3 } \dot { y } ( t ) } \\ & { \qquad - \tau \int _ { t - \tau } ^ { t } \dot { y } ^ { T } ( s ) R _ { 1 } \dot { y } ( s ) d s } \\ & { \qquad - ( \tau - \tau _ { 1 } ) \int _ { t - \tau } ^ { t - \tau } \dot { y } ^ { T } ( s ) R _ { 2 } \dot { y } ( s ) d s } \\ & { \qquad - ( \tau - \tau _ { 2 } ) \int _ { t - \tau } ^ { t - \tau _ { 2 } } \dot { y } ^ { T } ( s ) R _ { 3 } \dot { y } ( s ) d s } \end{array}
$$

根据引理3，有

$$
\begin{array}{c} \begin{array}{c} \begin{array} { r l } & { - \tau _ { f \iota } ^ { \int } \dot { \tau } ( s ) R _ { 1 } \dot { y } ( s ) d s } \\ & { \quad \le - \xi ^ { 2 } ( t ) \left[ \begin{array} { l } { e _ { 1 } - e _ { 2 } } \\ { e _ { 2 } - e _ { 3 } } \end{array} \right] \left[ \begin{array} { l } { R _ { 1 } x } \\ { R _ { 2 } ^ { \prime } } \end{array} \right] \left[ e _ { 1 } - e _ { 2 } \right]} \\ { \varepsilon _ { 2 } - e _ { 3 } } \end{array}  ^ { T } \xi ( t )  \\ & { \quad - \xi ^ { 2 } ( t ) \left[ \begin{array} { l } { e _ { 1 } + e _ { 2 } - 2 e _ { \mathrm { t i } _ { \mathrm { R } } } } \\ { e _ { 2 } + e _ { 3 } - 2 e _ { \mathrm { t i } _ { \mathrm { R } } } } \end{array} \right] \left[ 3 R _ { 1 } y } \\ { \qquad \right] \left[ \varepsilon _ { 1 } + e _ { 2 } - 2 e _ { \mathrm { t i } _ { \mathrm { R } } } \right]} \end{array}  ^ { T } \xi ( t )  \\ & { \quad - \xi ^ { 2 } ( t ) \left[ \begin{array} { l } { e _ { 1 } - e _ { 2 } + 6 e _ { \mathrm { t i } _ { \mathrm { { B } } } } - 1 2 e _ { \mathrm { t i } _ { \mathrm { { B } } } } } \\ { e _ { 2 } - e _ { 3 } + 6 e _ { \mathrm { t i } _ { \mathrm { { B } } } } - 1 2 e _ { \mathrm { t i } _ { \mathrm { { B } } } } } \end{array} \right] \left[ \begin{array} { l } { E _ { 1 } } \\ { E _ { 2 } + e _ { 3 } - 2 e _ { \mathrm { t i } _ { \mathrm { { B } } } } } \end{array} \right] ^ { T } \xi ( t ) } \\ & { \qquad \times \left[ \begin{array} { l } { e _ { 1 } - e _ { 3 } + 6 e _ { \mathrm { t i } _ { \mathrm { { B } } } } - 1 2 e _ { \mathrm { t i } _ { \mathrm { { B } } } } } \\ { e _ { 2 } - e _ { 3 } + 6 e _ { \mathrm { t i } _ { \mathrm { { B } } } } - 1 2 e _ { \mathrm { t i } _ { \mathrm { B } } } } \end{array} \right] \left[ \begin{array} { l } { E _ { 1 } } \\ { E _ { 2 } } \end{array} \right] } \\ & { \qquad \times \left[ \begin{array} { l } { e _ { 1 } - e _ { 2 } + 6 e _ { \mathrm { t i } _ { \mathrm { B } } } - 1 2 e _ { \mathrm { t i } _ { \mathrm { B } } } } \\ { e _ { 2 } - e _ { 3 } + 6 e _ { \mathrm { t i } _ { \mathrm { { B } } } } - 1 2 e _ { \mathrm { t i } _ { \mathrm { B } } } } \end{array} \right] \xi ( t ) } \end{array}
$$

根据引理1，得

$$
\begin{array} { r l } & { - ( \tau - \tau _ { 1 } ) \displaystyle \int _ { t - \tau } ^ { t - \tau _ { 1 } } \dot { y } ^ { T } ( s ) R _ { 2 } \dot { y } ( s ) d s } \\ & { \qquad \le - \xi ^ { T } ( t ) ( e _ { 5 } - e _ { 3 } ) R _ { 2 } ( e _ { 5 } - e _ { 3 } ) ^ { T } \xi ( t ) } \\ & { - ( \tau - \tau _ { 2 } ) \displaystyle \int _ { t - \tau } ^ { t - \tau _ { 2 } } \dot { y } ^ { T } ( s ) R _ { 3 } \dot { y } ( s ) d s } \\ & { \qquad \le - \xi ^ { T } ( t ) ( e _ { 7 } - e _ { 3 } ) R _ { 2 } ( e _ { 7 } - e _ { 3 } ) ^ { T } \xi ( t ) } \end{array}
$$

因此有

$$
\dot { V } _ { 3 } ( t ) \leq \xi ^ { T } ( t ) U _ { 3 } \xi ( t )
$$

此外，对于任意的矩阵 $S _ { 1 } , S _ { 2 }$ ，有以下等式成立：

$$
\begin{array} { c } { { 0 = 2 \Big [ y ^ { T } ( t ) S _ { 1 } + \dot { y } ^ { T } ( t ) S _ { 2 } \Big ] \big [ - \dot { y } ( t ) - D y ( t ) } } \\ { { } } \\ { { + A g ( y ( t ) ) + B g ( y ( t - \tau _ { 1 } ( t ) ) ) + C p ( t ) \big ] } } \\ { { 0 = \xi ^ { T } ( t ) \Phi \xi ( t ) } } \end{array}
$$

同时，通过引入参数 $\delta$ 在神经元激活函数中，根据式(7)考虑两个子区间： $L _ { i } ^ { - } \leq \frac { g _ { i } ( \sigma _ { 1 } ) - g _ { i } ( \sigma _ { 2 } ) } { \sigma _ { 1 } - \sigma _ { 2 } } \leq L _ { i } ^ { \delta }$ 和

$L _ { i } ^ { \delta } \leq \frac { g _ { i } ( \sigma _ { 1 } ) - g _ { i } ( \sigma _ { 2 } ) } { \sigma _ { 1 } - \sigma _ { 2 } } \leq L _ { i } ^ { + }$ ，其中， $L _ { i } ^ { \delta } = L _ { i } ^ { - } + \delta ( L _ { i } ^ { + } - L _ { i } ^ { - } )$ 。Casel: $L _ { i } ^ { - } \leq \frac { g _ { i } ( \sigma _ { 1 } ) - g _ { i } ( \sigma _ { 2 } ) } { \sigma _ { 1 } - \sigma _ { 2 } } \leq L _ { i } ^ { \delta }$ 。对于 casel，,有以下条件成立：

$$
\begin{array} { r l } & { E _ { 1 } ^ { x } \leq \frac { g _ { 1 } ( x , ( y , t ) ) - g _ { 2 } ( x , ( y - \tau ( t ) ) ) } { y ( t ) } \leq L _ { 2 } ^ { x } , i = 1 , 2 , \ldots , n } \\ & { E _ { 2 } ^ { y } \leq \frac { g _ { 1 } ( y , t ) - g _ { 2 } ( x , ( y - \tau ( t ) ) ) } { y _ { 1 } ( t ) - y _ { 2 } ( t - \tau ( t ) ) } \leq L _ { 2 } ^ { x } , i = 1 , 2 , \ldots , n } \\ & { E _ { 2 } ^ { x } \leq \frac { g _ { 1 } ( y , t ) ( \tau ) - g _ { 2 } ( y , t ) ( \tau - \tau ( t ) ) ) } { y _ { 1 } ( t ) - y _ { 2 } ( t - \tau ( t ) ) } \leq L _ { 2 } ^ { y } , i = 1 , 2 , \ldots , n } \\ & { E _ { 3 } ^ { x } \leq \frac { g _ { 1 } ( y , t ) ( \tau ) - g _ { 2 } ( y , t ) ( \tau - \tau ( t ) ) ) } { y _ { 1 } ( t ) - y _ { 2 } ( t - \tau ( t ) ) } \leq L _ { 2 } ^ { y } , i = 1 , 2 , \ldots , n } \\ & { I _ { 4 } ^ { x } \leq \frac { g _ { 1 } ( y , t ) ( y ) - g _ { 2 } ( y , ( t - \tau ) ) } { y _ { 1 } ( t ) - y _ { 1 } ( t - \tau ) } \leq L _ { 2 } ^ { x } , i = 1 , 2 , \ldots , n } \\ & { E _ { 5 } ^ { x } \leq \frac { g _ { 1 } ( y , t ) ( \tau ) - g _ { 2 } ( y , ( t - \tau ) ) ) } { y _ { 1 } ( t ) - y _ { 2 } ( t ) - y _ { 1 } ( t - \tau ( t ) ) } \leq L _ { 2 } ^ { y } , i = 1 , 2 , \ldots , n } \\ & { E _ { 4 } ^ { y } = \frac { g _ { 1 } ( y , t ) - g _ { 2 } ( y , ( t - \tau ) ) } { y _ { 1 } ( t ) - y _ { 2 } ( t ) - y _ { 2 } ( t - \tau ( t ) ) } \leq L _ { 2 } ^ { x } , i = 1 , 2 , \ldots , n } \\ & { E _ { 5 } ^ { y } = \frac { g _ { 1 } ( y , t ) } { y _ { 1 } ( t ) - y _ { 2 } ( t ) - y _ { 3 } ( t - \tau ( t ) ) } } \\ & { E _ { 5 } ^ { x } \leq \frac { g _ { 1 } ( y , t ) } { y _ { 1 } ( t ) - y _ { 2 } ( t ) } } \\ &  E _ { 6 } ^ { y } = \frac { g _ { 2 } ( y , t ) - g _ { 2 } ( y , ( t - \tau _ { 2 } ) ) }  y _ { 2 } ( t ) - y _ { 2 } ( t ) - y _ { 2 } ( t - \tau _ { 2 } )  \end{array}
$$

因此，对于任意合适维度的对角矩阵$M _ { i } = d i a g \{ m _ { i 1 } , m _ { i 2 } , . . . , m _ { i n } \} , i = 1 , 2 , . . , 6$ ，有

$$
0 \leq - 2 \xi ^ { T } ( t ) \left[ e _ { 8 } - e _ { 9 } - \overline { { L } } _ { 3 } ( e _ { 1 } - e _ { 2 } ) \right] M _ { 1 } \left[ e _ { 8 } - e _ { 9 } - L ^ { \delta } \left( e _ { 1 } - e _ { 2 } \right) \right] ^ { T } \xi ( t )
$$

$$
\begin{array} { r l } & { \begin{array} { r l } & { ( 0 \leq - 2 \xi _ { \eta } ^ { T } ( t ) [ \ell \epsilon _ { 1 } - \epsilon _ { t _ { 1 } } - \overline { { L } } _ { 1 } ( \epsilon _ { t _ { 1 } } - \epsilon _ { t _ { 4 } } ) ] M _ { 2 } [ \epsilon _ { \delta } - \epsilon _ { t _ { 1 } } - L ^ { \delta } ( \epsilon _ { t _ { 1 } } - \epsilon _ { t _ { 3 } } ) ] ^ { T } \xi ( t ) } \end{array} } \\ & { \begin{array} { r l } & { ( 0 \leq - 2 \xi _ { \eta } ^ { T } ( t ) [ \epsilon _ { 1 } - \epsilon _ { t _ { 1 } } - \overline { { L } } _ { 1 } ( \epsilon _ { t _ { 1 } } - \epsilon _ { t _ { 6 } } ) ] M _ { 2 } [ \epsilon _ { \delta } - \epsilon _ { t _ { 1 } } - L ^ { \delta } ( \epsilon _ { t _ { 1 } } - \epsilon _ { t _ { 6 } } ) ] ^ { T } \xi ( t ) } \\ & { ( 0 \leq - 2 \xi _ { \eta } ^ { T } ( t ) [ \epsilon _ { 1 } - \epsilon _ { t _ { 1 } } - \overline { { L } } _ { 1 } ( \epsilon _ { t _ { 1 } } - \epsilon _ { t _ { 6 } } ) ] M _ { 2 } [ \epsilon _ { t _ { 3 } } - \epsilon _ { t _ { 1 } } - L ^ { \delta } ( \epsilon _ { t _ { 3 } } - \epsilon _ { t _ { 3 } } ) ] ^ { T } \xi ( t ) } \end{array} } \\ & { \begin{array} { r l } & { ( 0 \leq - 2 \xi _ { \eta } ^ { T } ( t ) [ \epsilon _ { 1 } - \epsilon _ { t _ { 3 } } - \overline { { L } } _ { 1 } ( \epsilon _ { t _ { 2 } } - \epsilon _ { t _ { 3 } } ) ] M _ { 2 } [ \epsilon _ { t _ { 3 } } - \epsilon _ { t _ { 1 } } - L ^ { \delta } ( \epsilon _ { t _ { 2 } } - \epsilon _ { t _ { 3 } } ) ] ^ { T } \xi ( t ) } \end{array} } \\ &  \begin{array} { r l } & { ( 0 \leq - 2 \xi ^ { T } ( t ) [ \epsilon _ { 1 } - \epsilon _ { t _ { 1 } } - \overline { { L } } _ { 1 } ( \epsilon _ { t _ { 3 } } - \epsilon _ { t _ { 3 } } ) ] M _ { 2 } [ \epsilon _ { 1 } - \epsilon _ { t _ { 1 } } - L ^ { \delta } ( \epsilon _ { t _ { 3 } } - \epsilon _ { t _ { 3 } } ) ] ^ { T } \xi ( t ) } \\ &  ( 0 \leq - 2 \xi ^ { T } ( t ) [ \epsilon _ { 1 } - \epsilon _ { t _ { 1 } } - \overline { { L } } _ { 1 } ( \epsilon _ { t _ { 1 } } -  \end{array} \end{array}
$$

因此有

$$
0 \leq \xi ^ { T } ( t ) \Psi ^ { a } \xi ( t )
$$

因此有下列不等式成立：

$$
p ^ { T } ( t ) p ( t ) \leq q ^ { T } ( t ) q ( t )
$$

则存在一个正参数 $\varepsilon$ 满足以下不等式：

$$
\boldsymbol { \varepsilon } \Big [ \boldsymbol { q } ^ { T } ( t ) \boldsymbol { q } ( t ) - \boldsymbol { p } ^ { T } ( t ) \boldsymbol { p } ( t ) \Big ] = \boldsymbol { \xi } ^ { T } ( t ) \Gamma \boldsymbol { \xi } ( t )
$$

综合上述有

$$
\dot { V } ( t ) \leq \xi ^ { T } ( t ) \Big [ \sum + \Psi ^ { a } \Big ] \xi ( t )
$$

cse2: $L _ { i } ^ { \delta } \leq \frac { g _ { i } ( \sigma _ { 1 } ) - g _ { i } ( \sigma _ { 2 } ) } { \sigma _ { 1 } - \sigma _ { 2 } } \leq L _ { i } ^ { + }$ 。Case2的讨论与 asel 类似。因此可以轻易得到

$$
0 \leq \xi ^ { T } ( t ) \Psi ^ { b } \xi ( t )
$$

结合上述式子，可得 $\dot { V } ( t )$ 的上界：

$$
\dot { V } ( t ) \leq \xi ^ { T } ( t ) \Big [ \sum + \Psi ^ { b } \Big ] \xi ( t )
$$

因此，根据式(24)(26)和LMI成立，有 $\dot { V } ( t ) < 0$ ，这将意味着，对于一个足够小的参数 $\kappa { > } 0$ 有 $\dot { V } ( t ) < - \kappa \| y ( t ) \| ^ { 2 }$ ，确保不确定神经网络式(6)是全局渐进稳定的，证毕。

推论1如果假设 $H _ { 1 } , H _ { 3 }$ 成立，对于任意正标量$\tau _ { 1 } , \tau _ { 2 } , u _ { 1 } , u _ { 2 }$ 和 $\sigma$ ，不确定神经网络式(8)是全局渐进稳定且严格$( Q , S , R ) - \gamma$ 散耗的，如果存在一个正定矩阵$P \in \mathbb { R } ^ { n \times n } , Q _ { i } \in \mathbb { R } ^ { n \times n } ( i = 1 , 2 , . . . , 1 2 ) , R _ { j } \in \mathbb { R } ^ { n \times n } ( j = 1 , 2 , 3 )$ ，正对角矩阵 $\Omega , M _ { i } \in \mathbb { R } ^ { n \times n } ( k = 1 , 2 , . . . , 1 2 )$ 和任意矩阵$x , y , z \in \mathbb { R } ^ { n \times n }$ ， $S _ { l } \in \mathbb { R } ^ { n \times n } ( l = 1 , 2 )$ 和一个正标量 $\varepsilon$ 使得以下LMI成立：

$$
\Upsilon _ { _ 2 } = \left[ \begin{array} { l l } { \Upsilon _ { _ { 1 1 } } } & { \Upsilon _ { _ { 1 2 } } } \\ { * } & { \Upsilon _ { _ { 2 2 } } } \end{array} \right] < 0 \quad ( i = a , b )
$$

其中： ${ \Upsilon } _ { 1 1 } = { \sum } + { \Psi } ^ { i } - e _ { 8 } Q e _ { 8 } ^ { T } , { \Upsilon } _ { 1 2 } = e _ { 1 } S _ { 1 } + e _ { 1 9 } S _ { 2 } - e _ { 8 } S$ ，$\Upsilon _ { 1 2 } = - ( R - \gamma I ) \circ \overline { { \xi } } ^ { T } \left( t \right) = \left[ \xi ^ { T } \left( t \right) , w ^ { T } \left( t \right) \right]$

证明为了阐述散耗性分析，本文使用于式(15)相似的LK泛函。并定义系统式(8)的散耗性能指数：

$$
J _ { \gamma , t _ { f } } = \int _ { 0 } ^ { t _ { f } } \left[ \left( \begin{array} { c } { z ( t ) } \\ { w ( t ) } \end{array} \right) ^ { T } \left( \begin{array} { c c } { Q } & { S } \\ { * } & { R } \end{array} \right) \left( \begin{array} { c } { z ( t ) } \\ { w ( t ) } \end{array} \right) - \gamma w ( t ) ^ { T } w ( t ) \right] d t
$$

根据定理1中case1和case2的证明，有

$$
\int _ { 0 } ^ { t _ { f } } \dot { V } ( t ) d t - J _ { \gamma , t _ { f } } \leq \int _ { 0 } ^ { t _ { f } } \overline { { \xi } } ^ { T } ( t ) \Upsilon _ { 2 } \overline { { \xi } } ( t ) d t
$$

根据式(27)成立，可以推断出

$$
\int _ { 0 } ^ { t _ { f } } \dot { V } ( t ) d t \le J _ { { \gamma } , t _ { f } }
$$

在式(30)的0初始化条件下，可以确保式(10)成立，这将意味着不确定神经网络式(8)是严格 $( Q , S , R ) - \gamma$ 散耗的，证毕。

对于在系统式(6)中每一不确定项的不确定神经网络，可以写成以下形式：

$$
\left\{ \begin{array} { l } { { \dot { y } } ( t ) = - D y ( t ) + A g \left( y ( t ) \right) + B g \left( y ( t - \tau _ { 1 } ( t ) - \tau _ { 2 } ( t ) ) \right) } \\ { y ( t ) = \varphi ( t ) , t \in [ - \tau , 0 ] } \end{array} \right.
$$

在推论2中给出系统式(31)的全局渐进稳定依据。

推论2如果假设 $H _ { 1 } , H _ { 3 }$ 成立，对于任意正标量$\tau _ { 1 } , \tau _ { 2 } , u _ { 1 } , u _ { 2 }$ 和 $\sigma$ ，不确定神经网络式(31)是全局渐进稳定，如果存在一个正定矩阵 $P \in \mathbb { R } ^ { n \times n } , Q _ { i } \in \mathbb { R } ^ { n \times n } ( i = 1 , 2 , . . . , 1 2 )$ ，

R, ∈Rn (j=1,2,3) 正对角矩阵$\Omega , M _ { i } \in \mathbb { R } ^ { n \times n } ( k = 1 , 2 , . . . , 1 2 )$ 和任意矩阵 $x , y , z \in \mathbb { R } ^ { n \times n }$ （20$S _ { l } \in \mathbb { R } ^ { n \times n } \ ( l = 1 , 2 )$ 和一个正标量 $\varepsilon$ 使得以下LMI成立：

$$
{ \overline { { \Upsilon } } } _ { 1 } = \sum _ { 1 } \ + \Psi ^ { i } < 0 ( i = a , b )
$$

其中： $\sum _ { 1 } = U _ { 1 } + U _ { 2 } + U _ { 3 } + \overline { { \Phi } } \ ,$

$$
\overline { { \Phi } } = 2 \big [ e _ { 1 } S _ { 1 } + e _ { 1 9 } S _ { 2 } \big ] \big [ - e _ { 1 9 } - D e _ { 1 } + A e _ { 8 } + B e _ { 2 } \big ] ^ { T } \ \mathrm { ~ o ~ }
$$

# 3 实验分析

本文将与文献[8,9,11,13,12]的结果进行比较。

例子1考虑不确定神经网络式(6)，所涉及的参数如下：

$$
D = { \left[ \begin{array} { l l } { 1 } & { 0 } \\ { 0 } & { 1 } \end{array} \right] } , A = { \left[ \begin{array} { l l } { - 1 } & { 0 . 5 } \\ { 0 . 5 } & { - 1 } \end{array} \right] } , B = { \left[ \begin{array} { l l } { - 2 } & { 0 . 5 } \\ { 0 . 5 } & { - 0 . 2 } \end{array} \right] }
$$

$$
, C = \left[ { \begin{array} { c c } { 0 } & { 0 } \\ { - 0 . 1 } & { - 0 . 1 } \end{array} } \right] , \varepsilon _ { d } = \left[ { \begin{array} { c c } { 1 } & { 0 } \\ { 0 } & { 0 . 5 } \end{array} } \right] , \varepsilon _ { a } = \left[ { \begin{array} { c c } { 0 . 5 } & { 0 } \\ { 0 } & { 1 } \end{array} } \right]
$$

$$
, \varepsilon _ { b } = { \left[ \begin{array} { l l } { 0 . 1 } & { 0 . 1 } \\ { 0 } & { 0 } \end{array} \right] } , { \overline { { L } } } _ { 1 } = { \left[ \begin{array} { l l } { 0 } & { 0 } \\ { 0 } & { 0 } \end{array} \right] } , { \overline { { L } } } _ { 2 } = { \left[ \begin{array} { l l } { 0 . 4 } & { 0 } \\ { 0 } & { 0 . 8 } \end{array} \right] }
$$

$$
F ( t ) = 0 . 5 \sin t
$$

通过使用MATLABLMI工具箱，发现LMI式(14)是可行的。最大允许边界 $\tau _ { 2 }$ 可通过定理1求得，其中$u _ { 1 } = 0 . 7 , u _ { 2 } = 0 . 1 , \delta = 0 . 6$ 。考虑激活函数$g _ { 1 } ( s ) = 0 . 2 ( \left| s + 1 \right| - \left| s - 1 \right| )$ 和 $g _ { 2 } ( s ) = 0 . 4 ( \left| s + 1 \right| - \left| s - 1 \right| )$ 。令时变时滞分量为 $\tau _ { 1 } ( t ) = 0 . 3 + 0 . 3 \sin t$ 和 $\tau _ { 2 } ( t ) = 0 . 7 0 2 7 + 0 . 1 \sin { t }$ 初始化状态 $y ( 0 ) = [ 0 . 2 , - 0 . 2 ] ^ { T }$ 。不同 $\tau _ { 1 }$ 下的 $\tau _ { 2 }$ 仿真结果如表1所示。

表1本文与文献[11]仿真结果对比  
Table 1 Comparison between this paper and [11]   

<html><body><table><tr><td>方法</td><td>T</td><td>0.5</td><td>0.6</td></tr><tr><td>[11]</td><td>T2</td><td>0.7688</td><td></td></tr><tr><td>定理1</td><td>T</td><td>0.8207</td><td>0.7802</td></tr></table></body></html>

例子2考虑不确定神经网络式(8)，所涉及的参数如下：

$$
D = { \left[ \begin{array} { l l } { 5 . 1 } & { 0 } \\ { 0 } & { 4 . 7 } \end{array} \right] } , A = { \left[ \begin{array} { l l } { 1 . 1 } & { - 0 . 7 } \\ { 0 . 9 } & { 1 . 2 } \end{array} \right] } , B = { \left[ \begin{array} { l l } { 1 . 2 } & { 0 . 6 } \\ { 0 . 8 } & { 1 } \end{array} \right] }
$$

$$
, C = \left[ { \begin{array} { c c } { 0 . 4 } & { 0 } \\ { 0 } & { 0 . 4 } \end{array} } \right] , \varepsilon _ { d } = \left[ { \begin{array} { c c } { 0 . 2 } & { 0 } \\ { 0 } & { 0 . 2 } \end{array} } \right] , \varepsilon _ { a } = \left[ { \begin{array} { c c } { 0 . 1 5 } & { 0 } \\ { 0 } & { 0 . 1 5 } \end{array} } \right]
$$

$$
\begin{array} { r } { \mathbf { \varepsilon } , \varepsilon _ { b } = \left[ \begin{array} { l l } { 0 . 1 } & { \phantom { - } 0 } \\ { 0 } & { 0 . 1 } \end{array} \right] , \overline { { L } } _ { 1 } = \left[ \begin{array} { l l } { 0 } & { 0 } \\ { 0 } & { 0 } \end{array} \right] , \overline { { L } } _ { 2 } = \left[ \begin{array} { l l } { 0 . 4 } & { \phantom { - } 0 } \\ { 0 } & { 0 . 8 } \end{array} \right] } \\ { F ( t ) = 0 . 5 \sin t \phantom { \frac { 1 } { \cos t } } t } \end{array}
$$

对于 $( Q , S , R ) - \gamma$ 散耗度，本文选择：

$$
Q = { \left[ \begin{array} { l l } { - 0 . 9 } & { \ 0 } \\ { \ 0 } & { - 0 . 9 } \end{array} \right] } , S = { \left[ \begin{array} { l l } { 0 . 5 } & { 0 } \\ { 0 . 3 } & { 1 } \end{array} \right] } , Q = { \left[ \begin{array} { l l } { 2 } & { 0 } \\ { 0 } & { 2 } \end{array} \right] }
$$

其中：参数 $\tau _ { 1 } = 0 . 1 , \tau _ { 2 } = 0 . 3 , u _ { 1 } = 0 . 3 , u _ { 2 } = 0 . 2$ 。在不同 $\delta$ 下的

最优散耗性能等级可以通过推论1获得。最优散耗性能等级Y如表2所示。

Table 2 Optimal dissipativity performance $\gamma$ for different $\delta$   

<html><body><table><tr><td>方法</td><td>8</td><td>0.25</td><td>0.50</td><td>0.75</td></tr><tr><td>推论1</td><td></td><td>1.3302</td><td>1.2704</td><td>0.9200</td></tr></table></body></html>

例子3考虑不确定神经网络式(31)，所涉及的参数如下：

$$
\begin{array} { r l } & { D = \left[ \begin{array} { l l } { 2 } & { 0 } \\ { 0 } & { 2 } \end{array} \right] , A = \left[ \begin{array} { l l } { 1 } & { 1 } \\ { - 1 } & { - 1 } \end{array} \right] , B = \left[ \begin{array} { l l } { 0 . 8 8 } & { 1 } \\ { 1 } & { 1 } \end{array} \right] } \\ & { \bar { L } _ { 1 } = \left[ \begin{array} { l l } { 0 } & { 0 } \\ { 0 } & { 0 } \end{array} \right] , \bar { L } _ { 2 } = \left[ \begin{array} { l l } { 0 . 4 } & { 0 } \\ { 0 } & { 0 . 8 } \end{array} \right] } \end{array}
$$

参数 $u _ { 1 } = 0 . 7 , u _ { 2 } = 0 . 1 , \delta = 0 . 8$ 。考虑如下激活函数$g _ { 1 } ( s ) = 0 . 2 ( \left| s + 1 \right| - \left| s - 1 \right| )$ 和 $g _ { 2 } ( s ) = 0 . 4 ( \left| s + 1 \right| - \left| s - 1 \right| )$ 。时变时滞分量为 $\tau _ { 1 } ( t ) = 0 . 4 + 0 . 4 \sin t$ 和 $\tau _ { 2 } ( t ) = 1 . 8 3 5 0 + 0 . 1 \sin { t }$ 。初始化状态 $y ( 0 ) = [ 0 . 5 , - 0 . 5 ] ^ { T }$ 。全局渐近稳定性仿真结果如表3所示。

表2不同 $\delta$ 下的最优散耗性能等级》  
表3例3全局渐近稳定性仿真结果  
Table 3Global asymptotic stability simulation results of example 3   

<html><body><table><tr><td>方法</td><td>T1</td><td>0.8</td><td>1</td><td>1.2</td></tr><tr><td>[8]</td><td>T2</td><td>1.5666</td><td>1.3668</td><td>1.1664</td></tr><tr><td>[9]</td><td>T2</td><td>1.9666</td><td>1.8351</td><td>1.6803</td></tr><tr><td>[11]</td><td>T2</td><td>2.0164</td><td>1.8203</td><td>1.6197</td></tr><tr><td>[13]</td><td>T2</td><td>2.2448</td><td>1.9642</td><td>1.8591</td></tr><tr><td>[12]</td><td>T2</td><td>2.3547</td><td>2.0053</td><td>1.9217</td></tr><tr><td>推论2</td><td>T2</td><td>2.9792</td><td>2.6659</td><td>2.3173</td></tr></table></body></html>

# 4 结束语

在本文对一类带有时滞的不确定连续时间神经网络的全局渐近稳定性和耗散性分析问题进行了广泛的研究。通过使用更一般的激活函数方法、Lyapunov稳定性理论，用线性矩阵不等式的形式获得新的充分条件，最终得所需的结果。此外，与以往的研究结果不同，本文采用新的单积分不等式来处理不保守的LKF泛函导数。最终，通过数值仿真证明了本文研究成果的有效性。

在实际工程应用，如远程控制、网络控制系统等两个节点之间传输的信号可以是系统双段的，考虑了两个延时分量的系统，因此传统的线性控制和最优控制的精确数学模型由于忽略了不定性的存在，从而使所设计的控制器难以达到预期的性能指标。因此，以本文研究的耗散理论为控制系统的设计和分析提供了能量相关的输入/输出描述模型的基本思想，并为现代控制应用，如机器人、主动减振、机电系统、内燃机、电路理论等工程方向提供了更灵活的理论基础。在未来的工作中，将会尝试将此结果推广到许多不连续激活的神经网络中。

# 参考文献： >三\

[1]SainathTN,WeissRJ, WilsoKW,etal.Multichannelsignalprocesin with deep neural networks for automatic speech recognition[J]. IEEE//ACM Trans on Audio,Speech,and Language Processing,2017,25(5): 965-979.   
[2]Song Hui,Dai Jiejie,Sheng Gehao,et al.GIS partial discharge patern recognition via deep convolutional neural network under complex data source[J]. IEEE Trans on Dielectricsand Electrical Insulation,2018,25 (2): 678-685.   
[3]Kalaam R N, Muyeen S M,Ahmed AD,et al. Optimisation of controller parameters for grid-tied photovoltaic system at faulty network using artificial neural network-based cuckoo search algorithm[J].IETRenewable Power Generation,2017,11(12): 1517-1526.   
[4]Emary E, Zawbaa H M, Grosan C. Experienced gray wolf optimization through reinforcement learning and neural networks [J].IEEE Trans on Neural Networks and Learning Systems,2018,29 (3): 681-694.   
[5]Fu Caifen,Tan Wen.Decentralised load frequency control for power systems with communication delays via active disturbance rejection [J].IET Generation,Transmission & Distribution,2018,12(6):1397-1403.   
[6]Le Van Hien, Le Huy V, Phat VN. Improved delay-dependent exponential stability ofsingularsystems with mixed interval time-varying delays [J]. IET Control Theory& Applications,2015,9(9): 1364-1372.   
[7]Zhao Yu,Gao Huijun,Mou Shaoshuai. Asymptotic stability analysis of neuralnetworkswithsuccessivetimedelaycomponents[J]. Neurocomputing,2008,71: 2848-2856.   
[8]Shao Hanyong,Han Qinglong.New delay-dependent stability criteria for neural networks with two additive time-varying delay components [J]. IEEE Trans on Neural Networks,2011,22 (5): 812-818.   
[9]Zhang Chuanke,He Yong,JiangL,et al.Delay-dependent stability criteria for generalized neural networks with two delay components [J].IEEE Trans on Neural Networks,2014,25(7):1263-1276.   
[10]SamiduraiR,ManivannanR,Ahn CK,etal.New criteria for stability of generalized neural networks including Markov jump parametersand additive time delays [J]. IEEE Trans on Systems,Man,and Cybernetics: Systems,2018,48 (4): 485-499.   
[11] Liu Yu,Lee S,Lee H.Robust delay-dependent stability criteria foruncertain neural networks with two additive time-varying delay components [J]. Neurocomputing,2015,151: 770-775.   
[12]DingLiming,HeYong,Liao Yiwei,etal.Newresult for generalized neural networks with additive time-varying delays using free-matrix-based integral inequality method [J]. Neurocomputing,2017,238:205-211.   
[13] Muthukumar P,Subramanian K. Stability criteria for Markovian jump neural networks with modedependent additive time-varying delays via quadratic convex combination [J].Neurocomputing,2016,205:75-83.   
[14] Samidurai R,Rajavel S,Sriraman R,et al. Novelresults on stability analysis of neutral-type neural networkswith additive time-varyingdelay components and leakage delay [J]. International Journal Control Autom., 2017,15: 1-13.   
[15]Hill D,Moylan P.The stability of nonlinear dissipative systems [J].IEEE Trans on Automatic Control,1976,21 (5): 708-711.   
[16] Feng Zhiguang,Lam J.Stability and dissipativity analysis of distributed delay cellular neural networks [J].IEEE Trans on Neural Networks,2011, 22 (6): 976-981.   
[17] Wu Zhengguang,LamJ,Su H,et al. Stability and dissipativity analysis of static neural networkswith time delay[J].IEEE Trans on Neural Networks and Learning Systems,2012,23 (2): 199-210.   
[18] Gu K,Kharitonov V, Chen J. Stability of time-delay systems [M].[S.1.] : Birkhauser,2003.   
[19] Wang Xin, She Kun,Zhong Shouming,et al.On extended dissipativity analysis for neural networks with time-varying delay and general activation functions [J].Advances in Difference Equations,2016,79:1-16.