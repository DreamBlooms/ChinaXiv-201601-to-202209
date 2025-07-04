# 一类非光滑非凸优化问题的神经网络方法“

喻昕，陈昭蓉

(广西大学 计算机与电子信息学院，南宁 530004)

摘要：提出了解决一类带等式与不等式约束的非光滑非凸优化问题的神经网络模型。证明了当目标函数有下界时，神经网络的解轨迹在有限时间收敛到可行域。同时，神经网络的平衡点集与优化问题的关键点集一致，且神经网络最终收敛于优化问题的关键点集。与传统基于罚函数的神经网络模型不同，提出的模型无须计算罚因子。最后，通过仿真实验验证了所提出模型的有效性。

关键词：神经网络；非凸非光滑优化；有限时间收敛 中图分类号：TP183 doi:10.3969/j.issn.1001-3695.2018.03.0150

# Neural network optimization method for class of nonconvex nonsmooth optimization problems

Yu Xin, Chen Zhaorong† (School Of Computer & Electronic Information Guangxi University,Nanning 53ooo4,China)

Abstract: This paper proposedanovel neural network to solve nonsmoth nonconvex optimization problems with equalityand inequalityconstraints.It was proved that when theobjective function hasalowerbound,the neural network converges toa feasibledomaininafinite time.Meanwhile,thesolutiontrajectoryof nural network converges tooptimal solutionsetf the corresponding optimizationproblems,which finally converge to critical point setof optimization problems.Comparing with traditional neural network which basedonpenaltyfunction,the neural network model does notneed tocalculateany penalty parameters.Finally,the effectiveness of the proposed model is verified by simulation experiments.

Key words: Neural network; Nonconvex nonsmooth optimization; Limited time convergence

# 0 引言

1986 年，Tank和Hopfield[1]首次介绍了模拟神经网络方法解决限制性最优化问题，并在文献[2]中得到更进一步的阐述。其核心思想是利用动力学神经网络同时模拟目标函数与约束函数，并利用神经网络的模拟与并行处理能力计算问题的最优解。文献[1]首次提出了递归神经网络解决线性规划问题，在此基础上，Kennedy和Chua[2]对文献[1]中的神经网络进行改进，通过构建一个有限的惩罚参数的神经网络来解决非线性规划问题。Zhang[3]在早期惩罚参数研究的基础上，提出了一种基于Lagrange乘子法的递归神经网络以解决非线性凸优化问题。Lagrange神经网络模型中有两种神经元：变量神经元和Lagrange神经元。其中，变量神经元负责寻找目标函数的最小点以及提供解决问题的平衡点；而拉格朗日神经元负责将动态轨迹快速的引入可行域。有关Lagrange 神经网络的详细研究请参考文献[4-6]。

在最优化问题的研究发展中，早期的神经网络模型均为光滑非线性规划问题而设计，为了解决非光滑非线性规划问题，

Forti等人[7提出了一种G-NPC神经网络模型，G-NPC是基于NPC的一个微分包含形式的梯度系统，其目标函数和约束函数不需要是光滑的而仅仅是正则函数即可。为了使非光滑规划更具普遍性，文献[8,9]提出了一些基于惩罚函数和次梯度的递归神经网络解决非光滑凸与非光滑非凸规划问题。神经网络的收敛行为，包括全局收敛和局部收敛。如果规划问题的目标函数的定义域域中任意的初始点的解轨迹收敛于最优解（或近似最优解），则该神经网络模型是全局收敛的，如文献[10]的神经网络模型，在满足一些条件的情况下是全局收敛；然而，如果限制条件是初始状态的解必须从可行域中选取，则其收敛是局部的。基于惩罚参数和函数的神经网络模型，其解集很在大程度上是非全局收敛的，因为此类神经网络模型，其可行域上发现的一个内部点通常是一个特殊域包含的可行域的中心，因此，为了保证收敛，初始解集必须在可行域范围内部选取，并且惩罚参数必须保证足够大。再者，惩罚函数神经网络模型的有效性依赖于确定的或非确定的惩罚参数，而确定性惩罚参数在实际应用是很难估算的。为解决这个问题，Zheng 等人[1提出了一种新的解决非光滑凸优化的递归神经网络，文献[11]所提出的神经网络在解决带约束的非光滑凸规划问题的同时，不需要任何的惩罚参数。然而，文献[11提出的神经网络的结构却异常复杂。

为了降低网络模型的复杂度，文献[12\~16]提出了一些一层递归神经网络。Gou等人[14]提出了一种解决线性等式约束的伪凸优化的一层递归神经网络，并证明了在等式约束条件下，解轨迹能在有限时间收敛到可行域中。基于惩罚函数方法，Liu等人[15]提出了一种新的一层递归神经网络来解决线性等式约束的伪凸最优化问题。为解决线性规划问题，Liu[16]早期同样提出一种基于次梯度的神经网络，证明了该神经网络定义域内是全局收敛的。国内有关神经网络解决最优化的研究可参考文献[21\~23]

传统的神经网络模型解决工程优问题大多要求求解适当的罚函数，而这个参数在某些目标函数下是难以计算的，这为网络执行计算带来困难。本文结合传统的递归神经网络模型，提出新的一种解决带等式约束和不等式约束的递归神经网络模型。该模型的优点如下：a)与传统基于罚函数的神经网络模型不同，本文提出的模型无需计算罚因子;b）许多模型的网络模型的初始点往往只能在一个有界球体内选取，而此模型的网络初始点可以任意选取;c）到目前为止，所提出的大部分模型仅能解决目标函数为凸的优化问题，而此模型可解决一类目标函数为非凸的优化问题。

# 1 预备知识

在本文中，考虑如下的非光滑非凸约束的最优化问题：

$$
\begin{array} { l } { \operatorname* { m i n } \quad f ( x ) = f ( x ) } \\ { \mathrm { s . } t . \left\{ g ( x ) \leq 0 \right. } \\ { h ( x ) = 0 } \end{array}
$$

其中: $x = ( x _ { 1 } , x _ { 2 } , . . . , x _ { n } ) ^ { T } \in \mathbb { R } ^ { n }$ 是变量向量， $f : \mathbb { R } ^ { n }  \mathbb { R }$ 是非光滑凸或非凸的目标函数，其中 $f ( x )$ 可以是非光滑非凸的正则函数。 $g ( x ) = ( g _ { 1 } ( x ) , g ( \mathfrak { z } _ { 2 } x ) , . . . , g _ { m } ( x ) ) ^ { T } : \mathbb { R } ^ { n }  \mathbb { R } ^ { m }$ 是 $m$ 维向量的不等式约束向量函数，且 $g _ { i } ( x ) , i = 1 , . . . , m$ 可以是非光滑的凸函数。 $h ( \boldsymbol { x } ) = ( h ( x _ { 1 } ) , h ( x _ { 2 } ) , . . . , h _ { p } ( \boldsymbol { x } ) ) ^ { T } : \mathbb { R } ^ { n }  \mathbb { R } ^ { p }$ 是 $p$ （204号维线性等式约束向量函数。不失一般性，我们假设非线性规划(1)至少有一个最优解。定义 $S _ { 1 } = \left\{ { \pmb x } \in R ^ { n } : { \pmb g } ( { \pmb x } ) \leq 0 \right\}$ ，$S _ { 2 } = \left\{ { \pmb x } \in { \pmb R } ^ { n } : { \pmb h } ( { \pmb x } ) = 0 \right\}$ 。满足约束函数的可行域定义为$S = \left\{ { \pmb x } \in R ^ { n } : { \pmb g } ( { \pmb x } ) \leq 0 , { \pmb h } ( { \pmb x } ) = 0 \right\}$ ，显然 $S = S _ { 1 } \cap S _ { 2 }$ 。

对于本文研究的优化问题，我们一直假定存在 $\tilde { \mathbf { x } } \in R ^ { n }$ 和$\delta > 0$ ，满足 $\tilde { \pmb { x } } \in \mathrm { i n t } ( S _ { 1 } ) \cap S _ { 2 }$ ， $\tilde { S _ { 1 } } \subseteq \tilde { B ( x , \delta ) }$ ，其中（204号 $\mathrm { i n t } ( S _ { 1 } )$ 表示集合 $S _ { 1 }$ 的内部， $\tilde { B ( x , \delta ) }$ 表示以 $\tilde { \mathbf { x } }$ 为中心半径为 $\delta$ 的开球区域，且 $G _ { { \scriptscriptstyle m } } = \operatorname* { m i n } _ { 1 \le j \le m } - g _ { { \scriptscriptstyle j } } ( \overset { \sim } { \boldsymbol { x } } ) > 0$ 。

为了便于解决问题，定义

$$
G ( { \pmb x } ) = \left\{ \sum _ { j \in J ^ { + } ( { \pmb x } ) } ^ { 0 , { \pmb x } \in S _ { 1 } } { \pmb x } _ { j } ( { \pmb x } ) , { \pmb x } \notin S _ { 1 } \right.
$$

$J ^ { + } ( x ) = \left\{ j \in \{ 1 , 2 , \cdots , m \} : g _ { j } ( x ) > 0 \right\} \quad ,$ 显然， $\left\{ \vphantom { \frac { 1 } { 1 } } \mathbf { x } : G ( \pmb { x } ) \leq 0 \right\} = S _ { 1 } , \left\{ \pmb { x } : H ( \pmb { x } ) = 0 \right\} = S _ { 2 } \circ$ （20

定义 $1 ^ { [ 1 9 ] }$ 如果存在正整数 $k , \varepsilon$ ，对于任意的（204号 $x _ { 1 } , x _ { 2 } \in x + \varepsilon B ( 0 , 1 )$ 使得 $\vert f ( x _ { 1 } ) - f ( x _ { 2 } ) \vert \leq k ( x _ { 1 } - x _ { 2 } )$ 成立，则称函数 $f : \mathbb { R } ^ { n }  \mathbb { R }$ 在 $\boldsymbol { x } \in \mathbb { R } ^ { n }$ 附近Lipschitz。如果 $f$ 在其定义域每一个点的附近都Lipschitz，则称 $f$ 为局部Lipschitz。

如果 $f : \mathbb { R } ^ { n } \to \mathbb { R }$ 在 $\mathbb { R } ^ { n }$ 上是局部Lipschitz 的，则 $f$ 在 $x$ 点沿方向 $\boldsymbol \nu \in \mathbb { R } ^ { n }$ 的广义方向导数为：

$$
f ^ { 0 } ( x ; \nu ) = \operatorname* { l i m } _ { \stackrel { y \to x } { t \to 0 + } } { \frac { f ( y + t \nu ) - f ( y ) } { t } }
$$

如果 $f ^ { 0 } ( x ; \nu )$ 是有定义且有限的， $f$ 在 $x$ 处的次微分可以定义为

$$
\begin{array} { r } { \hat { \mathcal { O } } f ( x ) = \{ \xi \in \mathbb { R } ^ { n } : \forall \nu \in \mathbb { R } ^ { n } , ~ f ^ { 0 } ( x ; \nu ) \geq \left. \nu , \xi \right. \} } \end{array}
$$

引理1链式法则[20]。如果 $W : \mathbb { R } ^ { n }  \mathbb { R }$ 在 $x ( t )$ 处是正则的， $x ( t ) : \mathbb { R } ^ { n }  \mathbb { R }$ 在 $t$ 上是可微且是局部Lipschitz 的，则$\dot { W } ( x ( t ) ) = < \xi , x ( t ) > , \xi \in \partial W ( x ( t ) ) \ t \in [ 0 , \infty ) \ \circ$ （204号

本文提出以下微分包含的神经网络动力学模型：

$$
\dot { x } \in - ( I - P ) ( \hat { \mathcal { O } } f ( \mathbf { x } ) + u \hat { \mathcal { O } } G ( x ) ) - A ^ { T } h ( A x ( t ) - b )
$$

$$
\begin{array}{c} \Dot { u } = \left\{ { 0 , { \pmb x } \in S _ { 1 } } _ { } \right. _ { }  \\ { G ( x ) + \varepsilon , { \pmb x } \in \mathbb { R } ^ { n } / S _ { 1 } ^ { , u ( 0 ) > 0 } } \end{array}
$$

其中： $I$ 是单位矩阵, $P = A ^ { T } ( A A ^ { T } ) ^ { - 1 } A$

# 2 神经网络收敛分析

定义 $\pmb { 2 } ^ { [ 8 ] }$ 在区间 $[ t _ { 0 } , t _ { 1 } ] , ( t _ { 1 } > t _ { 0 } )$ 上， ${ \dot { x } } ( t ) \in - { \hat { O } } W ( x ( t ) )$ 满足初始条件 $x ( t _ { 0 } ) = x _ { 0 }$ 的一个解，是一个绝对连续函数 $x ( t )$ ，则对于 $x ( t _ { 0 } ) = x _ { 0 }$ 和所有的 $t \in \left[ t _ { 0 } , t _ { 1 } \right]$ ，有 ${ \dot { x } } ( t ) \in - { \hat { O } } W ( x ( t ) )$ 。

式(10)中的一个平衡点 $\boldsymbol { x } ^ { * } \in \mathbb { R } ^ { n }$ ，为式(10)的一个解，也就是说， $x ( t ) = x ^ { * } , t \in ( t _ { 0 } , \infty )$ 。显然，当且仅当满足$0 \in - \partial W ( x ( t ) )$ 时， $x ^ { * }$ 才为其平衡点。

引理 $\pmb { 2 } ^ { [ 8 ] }$ （20 对任意 $\pmb { x } \in S _ { 2 } \setminus S _ { 1 }$ ， $\boldsymbol { \xi } \in \partial G ( \boldsymbol { x } )$ ，有$( x - \widetilde { x } ) ^ { T } ( I - P ) \xi \ge G _ { m }$ 。

引理3神经网络模型式（2）具有局部解。

证明由于式（2）的右边是一个非空、紧凸的上半连续的集值映射，因此神经网络（10）至少存在一个具有满足初始条件 $\ x ( 0 ) = x _ { 0 }$ 的局部解 $x ( t )$ ， $t \in [ 0 , T )$ □

定理1对于任意的初始点 $\pmb { x } _ { 0 }$ ，神经网络模型（2）的轨迹在有限时间内必进入等式限制区域 $S _ { 2 }$ ，且停留在其中。

证明 设 $H ( x ) = \left\| A x - b \right\| _ { 1 }$ ，则

$S _ { 2 } = \{ x \in \mathbb { R } ^ { n } : H ( x ) = 0 \}$ ，且 $\partial H ( x ) = A ^ { T } h \big ( A x - b \big ) \circ$ 根据链式法则，存在 $\gamma { \big ( } t { \big ) } \in { \widehat { \cal O } } f { \big ( } x { \big ( } t { \big ) } { \big ) }$ ， $\xi \big ( t \big ) \in \widehat { \cal O } \ G \big ( x \big ( t \big ) \big )$ ，以及 $\eta \left( t \right) \in h \left( A x \left( t \right) - b \right)$ 满足

$$
\begin{array} { c } { \displaystyle \frac { d } { d t } H \left( x \left( t \right) \right) = < A ^ { T } \eta \left( t \right) , \dot { x } \left( t \right) > } \\ { = - \eta \left( t \right) ^ { T } A ( I - P ) ( \gamma \left( t \right) + u \xi \left( t \right) ) - \eta \left( t \right) ^ { T } A A ^ { T } \eta \left( t \right) } \end{array}
$$

因 $A { \big ( } I - P { \big ) } = A - A A ^ { T } \left( A A ^ { T } \right) ^ { - 1 } A = 0$ ，有

$$
\begin{array} { c } { \displaystyle \frac { d } { d t } H \big ( \boldsymbol { x } \big ( t \big ) \big ) = - \eta \big ( t \big ) ^ { T } A A ^ { T } \eta \big ( t \big ) } \\ { \leq - \lambda _ { m } \big ( A A ^ { T } \big ) \big \| \eta \big ( t \big ) \big \| ^ { 2 } } \end{array}
$$

其中： $\lambda _ { \scriptscriptstyle m } \left( A A ^ { \scriptscriptstyle T } \right) > 0$ 是 $\boldsymbol { A } \boldsymbol { A } ^ { T }$ 的最小特征值。

由 $x ( t ) \notin S _ { 2 }$ ，根据 $h$ 的定义知， $\left\| \eta ( t ) \right\| \geq 1$ ，因此：

$$
\frac { d } { d t } H \big ( x ( t ) \big ) \leq - \lambda _ { M } \big ( A A ^ { T } \big ) < 0
$$

对上式两边从0到 $t$ 进行积分得

$$
0 \leq H \left( x ( t ) \right) \leq H \left( x ( 0 ) \right) - \lambda _ { m } \left( A A ^ { T } \right) t
$$

显然，神经网络的轨迹 $x \big ( t \big )$ 能在有限时间进入 $S _ { 2 }$ 。

下面证明轨迹 $x \big ( t \big )$ 一直停留在 $S _ { 2 }$ 中。采用反证法，假定$x ( t )$ 在时刻 $t _ { 1 }$ 离开 $S _ { 2 }$ ，且在时间 $t \in ( t _ { 1 } , t _ { 2 } ) , t _ { 1 } < t _ { 2 }$ 内在 $S _ { 2 }$ 外。由 $H ( x ( t _ { 1 } ) ) = 0$ 及 $\frac { d } { d t } H \left( x ( t ) \right) \leq - \lambda _ { m } \left( A A ^ { T } \right)$ $t \in \left( t _ { 1 } , t _ { 2 } \right)$ ，可知 $H ( x ( t ) ) < 0 , t \in ( t _ { 1 } , t _ { 2 } )$ ，这与$H ( x ( t ) ) > 0$ ， $x ( t ) \notin S _ { 2 }$ 不符，定理1得证。

为了便于后面的证明，介绍如下假设：

假设1目标函数 $f ( x )$ 有下界。

定理2若假设1成立，则对于任意初始点 $\pmb { x } _ { 0 }$ ,神经网络模型式（2）具有全局解

证明首先证明神经网络状态向量 $x ( t )$ 有界。

根据定理1可知，神经网络状态向量 $x ( t )$ 进入 $S _ { 2 }$ 并停留其中，因此神经网络模型（2）可简化为：

$$
{ \dot { x } } \in - ( I - P ) ( { \widehat { \partial } } f ( \mathbf { x } ) + u { \widehat { \partial } } G ( x ) )
$$

定义能量函数：

$$
W ( \pmb { x } ( t ) ) = \mu ^ { - 1 } ( t ) ( f ( x ( t ) ) - \operatorname* { i n f } _ { x \in R ^ { n } } f ( x ) ) + G ( x ( t ) )
$$

根据链式法则，存在 $\gamma { \big ( } t { \big ) } \in { \widehat { c } } f { \big ( } x { \big ( } t { \big ) } { \big ) }$

$\xi \big ( t \big ) \in \widehat { \cal O } G \big ( x \big ( t \big ) \big )$ ，满足：

$$
\begin{array} { c } { { ( d \mathbf { \Omega } / d t ) W ( { \pmb x } ( t ) ) = < \mu ^ { - 1 } ( t ) \gamma ( t ) + \xi ( t ) , \dot { x } ( t ) > + } } \\ { { ( f ( x ( t ) ) - \underset { x \in R ^ { n } } { \operatorname* { i n f } } f ( x ) ) ( d \mathbf { \Omega } / d t ) \mu ^ { - 1 } ( t ) } } \end{array}
$$

由 $u ( 0 ) > 0$ 可知对任意 $t \in [ 0 , T )$ ， $\mu ( t ) > 0$ ，因此

$( d / d t ) \mu ^ { - 1 } ( t ) { = } - \mu ^ { 2 } ( t ) ( G ( x ) + \varepsilon ) < 0$ 又由$f ( x ( t ) ) - \operatorname* { i n f } _ { x \in R ^ { n } } f ( x ) \geq 0$ ，式(4)可转换为

$$
\begin{array} { r l } & { ( d / d t ) W ( x ( t ) ) \leq < \mu ^ { - 1 } ( t ) \gamma ( t ) + \xi ( t ) , \dot { x } ( t ) > } \\ & { = \xi ( t ) ^ { T } ) ( I - P ) ^ { T } ( I - P ) ( \gamma ( t ) + \mu ( t ) \xi ( t ) ) } \\ & { \qquad - ( \mu ^ { - 1 } ( t ) \gamma ( t ) ^ { T } } \\ & { = \ \frac { \left\| ( I - P ) ( \gamma ( t ) + \mu ( t ) \xi ( t ) ) \right\| ^ { 2 } } { \mu ( t ) } } \\ & { \leq \quad 0 } \end{array}
$$

结合式（3）和（5）可知，对对任意 $t \in [ 0 , T )$

$$
W ( { \pmb x } ( 0 ) ) \geq W ( { \pmb x } ( t ) ) \geq G ( { \pmb x } ( t ) )
$$

而 $G ( x ( t ) )$ 是强制的，因此也是水平集有界的，从而可知神经网络状态向量 $x ( t )$ 有界。

另一方面，根据解的可扩展理论，局部解可从 $t \in [ 0 , T )$ 扩展到 $t \in [ 0 , + \infty )$ ，即神经网络模型存在全局解。

定理3若假设1成立，对于任意的初始点 $\pmb { x } _ { 0 }$ ，神经网络模型式（2)的轨迹在有限时间内必进入可行域 $S$ ，且停留在其中。

证明根据定理1可知，神经网络状态向量 $x ( t )$ 进入 $S _ { 2 }$ 并停留其中。不失一般性，我们只需证明对任意初始点$\pmb { x } _ { 0 } \in S _ { 2 } \setminus S _ { 1 }$ ，神经网络状态向量 $x ( t )$ 进入 $S$ 并最终停留其中。

此时神经网络模型（10）可简化为

$$
{ \dot { x } } \in - ( I - P ) ( { \widehat { \sigma } } f ( \mathbf { x } ) + u { \widehat { \sigma } } G ( x ) )
$$

定义能量函数为

$$
W _ { 1 } ( { \pmb x } ( t ) ) = G ( { \pmb x } ( t ) )
$$

显然， $\left\{ \mathbf { } x : W _ { 1 } ( \mathbf { } x ( t ) ) \leq 0 \right\} = S _ { 1 }$ 。根据链式法则，对任意给定 ${ \pmb x } ( t ) \in S _ { 2 } \backslash S _ { 1 }$ ，存在 $\gamma { \big ( } t { \big ) } \in { \widehat { \cal O } } f { \big ( } x { \big ( } t { \big ) } { \big ) }$ ，$\xi \big ( t \big ) \in \widehat { \cal O } \ G \big ( x \big ( t \big ) \big )$ 满足

$$
( d / d t ) W _ { 1 } ( { \pmb x } ( t ) ) = < \xi ( t ) , \dot { x } ( t ) > =
$$

$$
- \xi ( t ) ^ { T } ( I - P ) ( \gamma ( t ) + \mu ( t ) \xi ( t ) ) \ \leq
$$

$$
\begin{array} { r } { \left\| ( I - P ) \xi ( t ) \right\| \left\| \gamma ( t ) \right\| - \mu ( t ) \left\| ( I - P ) \xi ( t ) \right\| ^ { 2 } \leq } \end{array}
$$

$$
\big \| ( I - P ) \xi ( t ) \big \| \mathrm { ~ ( ~ } \big \| \gamma ( t ) \big \| - \mu ( t ) \mathrm { ~ } \big \| ( I - P ) \xi ( t ) \big \| \mathrm { ~ ) ~ }
$$

根据定理2的证明过程可知， ${ \mathbf { } } x ( t )$ 有界，因此存在一个足够大的 $M > 0$ ，使得 $\left\| \mathbf { x } ( t ) - \tilde { { x } } \right\| \leq M$ 。由于目标函数 $f ( x )$ 是局部李普西兹函数，设 $l _ { f } ~ , ~ l _ { g }$ 分别为 $f ( { \pmb x } )$ ， $G ( \pmb { x } )$ 在$B ( \tilde { x } , M )$ 上的 Lipschitz 常数，可知 $\left\| \gamma ( t ) \right\| \leq l _ { f }$ ， $\left\| \xi ( t ) \right\| \leq l _ { f }$ （2另一方面，根据引理1可推出，对任意给定$\pmb { x } ( t ) \in \{ S _ { 2 } \setminus S _ { 1 } \} \bigcap B ( \tilde { x } , M )$ $\left\| ( \boldsymbol { x } ( t ) - \tilde { \boldsymbol { x } } ) ^ { T } \bigl ( \boldsymbol { I } - \boldsymbol { P } \bigr ) \boldsymbol { \xi } \right\| \geq G _ { m }$ ，从而有

$$
\left\| \left( I - P \right) \xi \right\| \geq G _ { \scriptscriptstyle m } / M > 0 .
$$

此外，对任意 $\ b { x } ( t ) \in \mathbb { R } ^ { n }$ ， $G ( t ) \geq 0$ ，因此 $\mu ( t )$ 是正单调递增的。从而必存在一个时刻 $t ^ { \prime } \geq 0$ ，使得对任意 $t > t ^ { \prime }$

$$
\mu ( t ) > l _ { f } \ M / G _ { m }
$$

综上，对任意 $t > t ^ { \prime }$ ，存在一个实数 $\varepsilon _ { \scriptscriptstyle 0 } > 0$ ，满足

$$
( d / d t ) W _ { 1 } ( { \pmb x } ( t ) ) \le \ - \varepsilon _ { 0 }
$$

对（9）两边从 $t ^ { \prime }$ 到 $t$ 进行积分得

$$
W _ { 1 } ( { \pmb x } ( t ) ) - W _ { 1 } ( { \pmb x } ( t ^ { \prime } ) ) \leq \ - \varepsilon _ { 0 } \ ( t - t ^ { \prime } \ )
$$

而 $W _ { 1 } ( { \pmb x } ( t ^ { \prime } ) \geq 0$ 且有上界，结合$\left\{ \mathbf { } x : W _ { 1 } ( \mathbf { } x ( t ) ) \leq 0 \right\} = S _ { 1 }$ ，可导出 ${ \mathbf { } } x ( t )$ 必在有限时间内进入$S _ { 1 }$ ，即进入可行域 $S$ 。

下面仍需证明，若 $\mathbf { } x ( t _ { 0 } ) , t _ { 0 } > t ^ { \prime }$ 在 $S$ 中，则当 $t > t ^ { \prime }$ ，${ \mathbf { } } x ( t )$ 将一直停留在那里。

采用反证法，假定 $x ( t )$ 在时刻 $t _ { 1 } ^ { \prime } > t _ { 0 }$ 离开 $S$ ，且在时间$t \in ( t _ { 1 } ^ { \prime } , t _ { 2 } ^ { \prime } )$ ， $t _ { 1 } ^ { \prime } < t _ { 2 } ^ { \prime }$ 内在 $s$ 外。由 $W _ { 1 } ( x ( t _ { 1 } ^ { \prime } ) ) = 0$ 及dw(x())<-ε，t∈(t,t），可知W(x(t))<0，$t \in ( t _ { 1 } ^ { \prime } , t _ { 2 } ^ { \prime } )$ ，这与 $W _ { 1 } ( x ( t ) ) > 0$ ， $x ( t ) \notin S _ { 1 }$ 相矛盾，定理3得证。

定义3神经网络的平衡点集合 $\scriptstyle { \varepsilon _ { \sigma } }$ 为

$$
\varepsilon _ { \sigma } = \{ \begin{array} { l } { x ^ { * } , \lambda ^ { * } , \mu ^ { * } | 0 \in \partial f ( x ^ { * } ) + \displaystyle \sum _ { j = 1 } ^ { n } \lambda _ { j } ^ { * } \partial h _ { j } ( x ^ { * } ) | } \\ { \qquad } \\ { + \displaystyle \sum _ { i = 1 } ^ { m } u _ { i } ^ { * } \partial g _ { i } ( x ^ { * } ) + 2 c \displaystyle \sum _ { j = 1 } ^ { n } ( \partial h _ { i } ( x ^ { * } ) ) ^ { T } h _ { j } ( x ) | } \\ { + c \displaystyle \sum _ { i = 1 } ^ { m } ( \hat { Q } g _ { i } ( x ^ { * } ) ) ^ { T } u _ { i } ^ { 2 } g _ { i } ( x ^ { * } ) } \\ { \qquad } \\ { 0 = \displaystyle \sum _ { j = 1 } ^ { n } \lambda _ { j } ^ { * } \partial h _ { j } ( x ^ { * } ) , 0 = \displaystyle \sum _ { i = 1 } ^ { m } u _ { i } ^ { * } \hat { Q } g _ { i } ( x ^ { * } ) } \\ { } \end{array} \}
$$

定理4当假设1成立，给定任意的初始点 $\pmb { x } _ { 0 } \in \mathbb { R } ^ { n }$ ，神经网络轨迹 ${ \mathbf { } } x ( t )$ 满足 $\begin{array} { r } { \operatorname* { l i m } _ { t  + \infty } \operatorname { d i s t } ( \boldsymbol { x } ( t ) , \boldsymbol { \varepsilon } _ { \sigma } ) = 0 , } \end{array}$

证明为了便于后文的证明，首先定义能量函数：

$W ^ { \prime } ( x ) = f ( x )$ 。由定理3可知，对于任意初始点 $x _ { 0 } \in S$ ， $x ( t )$   
会一直停留在 $s$ 中。因为 $W ^ { \prime } ( x )$ 是正则函数，存在可测函数  
$\gamma { \big ( } t { \big ) } \in { \widehat { c } } f { \big ( } x { \big ( } t { \big ) } { \big ) }$ ， $\xi \big ( t \big ) \in \partial G \big ( x \big ( t \big ) \big )$ ，以及  
$\eta \big ( t \big ) \in h \big ( A x \big ( t \big ) - b \big )$ ，有  
$( d / d t ) W ^ { \prime } ( x ( t ) ) = < \gamma ( t ) , - ( I - P ) ( \gamma ( t ) + u \xi ( t ) ) >$   
与此同时，因为 $x ( t ) \in S , \partial G ( x ) = 0$ ，也就是说  
$< \xi ( t ) , \dot { x } ( t ) > = 0$ 。上式则可以改写成  
$( d / d t ) W ^ { \prime } ( x ( t ) ) = < \gamma ( t ) + u \xi ( t ) , - ( I - P ) ( \gamma ( t ) + u \xi ( t ) ) >$   
而 $\left( I - P \right) ^ { 2 } = I - P$ ， $( I - P ) ^ { T } = ( I - P )$ ，所以

$$
\begin{array} { r } { ( d / d t ) W ^ { \prime } ( x ( t ) ) = - \big \| ( I - P ) ( \gamma ( t ) + u \xi ( t ) ) \big \| ^ { 2 } } \\ { = - \big \| \dot { x } ( t ) \big \| ^ { 2 } } \end{array}
$$

根据假设1， $f ( x )$ 有下界，可知 $W ^ { \prime } ( x )$ 有界。

接下来，通过反证法证明定理2，假设$\begin{array} { r } { \operatorname* { l i m } _ { t  + \infty } \mathrm { d i s t } ( \boldsymbol { x } ( t _ { n } ) , \boldsymbol { \varepsilon } _ { \sigma } ) = \mathtt { p } } \end{array}$ ，那么存在一个序列 $\{ \mathfrak { t } _ { \mathfrak { n } } \}$ ，当$\operatorname* { l i m } _ { n \to \infty } t _ { n } = + \infty$ （20 时，有 $\begin{array} { r } { \operatorname* { l i m } _ { t  + \infty } \mathrm { d i s t } ( \boldsymbol { x } ( t _ { n } ) , \varepsilon _ { \sigma } ) = \boldsymbol { \mathrm { p } } } \end{array}$ 并且$d i s t ( x ( t _ { n } ) , \varepsilon _ { \delta } ) > p / 2$ 。不妨假定 $H { = } \mathbf { B } ( \tilde { x } , R ) \setminus ( \varepsilon _ { \delta } { + } \frac { p } { 4 } \mathbf { B } ( 0 , 1 ) )$ $\Upsilon ( x ) { : = - ( I - P ) ( \hat { \sigma } f ( x ) + u \hat { \sigma } G ( x ) ) }$ 。由前文的分析，可知$\dot { { \boldsymbol x } } ( t ) \in \Upsilon ( { \boldsymbol x } ( t ) )$ 。

对于任意的 $x ( t ) \in H$ ，有 $0 \not \in \Upsilon ( x ( t ) )$ 。而 $\Upsilon ( x ( t ) )$ 是一个紧凸集，则在 $H$ 上存在最小值与最大值，分别表示为

$$
m _ { H } = \operatorname* { m i n } _ { x \in H } \operatorname* { m i n } _ { \zeta \in \Upsilon ( x ) } \left\| \zeta \right\| > 0
$$

$$
M _ { H } = \operatorname* { m a x } _ { x \in H } \operatorname* { m a x } _ { \zeta \in \Upsilon ( x ) } \left\| \zeta \right\| > 0
$$

此外，对于任意时间间隔 $t \in \left[ t _ { n } , t _ { n } + \alpha \right]$ ， $x ( t ) \in H$ ，有 $0 \leq \alpha \leq p / ( 4 M _ { H } )$ 。结合式（11），可得

$$
\begin{array} { r l } & { \displaystyle \operatorname* { l i m } _ { t \to + \infty } W ^ { \prime } ( x ( t ) ) = W ^ { \prime } ( x _ { 0 } ) - \int _ { 0 } ^ { + \infty } \left\| \dot { x } ( t ) \right\| ^ { 2 } d t } \\ & { \qquad \leq W ^ { \prime } ( x _ { 0 } ) - \displaystyle \int _ { \bigcup \{ t _ { \delta } , t _ { \delta } + \alpha \} } \left\| \dot { x } ( t ) \right\| ^ { 2 } d t } \\ & { \qquad \leq W ^ { \prime } ( x _ { 0 } ) - \displaystyle \int _ { \bigcup \{ t _ { \delta } , t _ { \delta } + \alpha \} } m _ { H } ^ { 2 } d t } \\ & { \qquad = W ^ { \prime } ( x _ { 0 } ) - \displaystyle \sum _ { n \in \mathbb { N } } \alpha m _ { H } ^ { 2 } = - \infty } \end{array}
$$

这与 $W ^ { \prime } ( x ( t ) )$ 有界矛盾，假设不成立。因此，$\begin{array} { r } { \operatorname* { l i m } _ { \ t \to + \infty } \mathrm { d i s t } ( \boldsymbol { x } ( t ) , \boldsymbol { \varepsilon } _ { \sigma } ) = 0 } \end{array}$ ，证毕。

定义4 优化问题的关键点集合 $C$ 为$C = \left\{ \pmb { x } \in S : 0 \in \partial f ( \pmb { x } ) + N _ { s } ( \pmb { x } ) \right\}$ ，其中 $N _ { s } ( { \pmb x } )$ 是 $\boldsymbol { x }$ 在可行域 $S$ 上的法锥。

定理5当假设1成立，给定任意的初始点 $\pmb { x } _ { 0 } \in \mathbb { R } ^ { n }$ ，神经网络模型（2）的任意一个聚点都是优化问题（1）的关键点。

证明为了便于后文的证明，首先定义能量函数：$W ^ { \prime } ( x ) = f ( x )$ 。由定理3可知，对于任意初始点 $x _ { 0 } \in S$ ， $x ( t )$ 会一直停留在 $s$ 中。由网络模型(2)可知当 $x ( t ) \in S$ ， $u ( t ) \equiv \overline { { u } }$ 0

因 $W ^ { \prime } ( x )$ 是正则函数，存在可测函数 $\gamma { \big ( } t { \big ) } \in { \widehat { \cal O } } f { \big ( } x { \big ( } t { \big ) } { \big ) }$ $\xi \big ( t \big ) \in \partial G \big ( x \big ( t \big ) \big )$ 满足

$$
( d / d t ) W ^ { \prime } ( x ( t ) ) = < \gamma ( t ) , - ( I - P ) ( \gamma ( t ) + \overline { { u } } \xi ( t ) ) >
$$

因 $x ( t ) \in S$ ， $\dot { G } ( x ) = 0$ ，即 $< \xi ( t ) , \dot { x } ( t ) > = 0$ 。上式则可以改写成

$( d / d t ) W ^ { \prime } ( x ( t ) ) = < \gamma ( t ) + \overline { { u } } \xi ( t ) , - ( I - P ) ( \gamma ( t ) + \overline { { u } } \xi ( t ) ) >$ ，而$\left( I - P \right) ^ { 2 } = I - P$ ， $( I - P ) ^ { T } = ( I - P )$ ，所以

$$
\begin{array} { l } { ( d / d t ) W ^ { \prime } ( x ( t ) ) = } \\ { - \bigl \| ( I - P ) ( \gamma ( t ) + \overline { { u } } \xi ( t ) ) \bigr \| ^ { 2 } = - \bigl \| \dot { x } ( t ) \bigr \| ^ { 2 } \leq 0 } \end{array}
$$

可知 $W ^ { \prime } ( x )$ 是一个非增函数。又由 $s$ 有界可知 $W ^ { \prime } ( x ( t ) )$ 有下界，从而可知 $\scriptstyle \operatorname* { l i m } _ { t \to + \infty } W ^ { \prime } ( x ( t ) )$ 存在，且

$$
\scriptstyle \operatorname* { l i m } _ { t \to + \infty } \left\| { \dot { x } } ( t ) \right\| = 0
$$

由 $x ( t )$ 在 $s$ 中且 $s$ 有界，可知存在一个聚点 $\overline { { x } }$ 和一个时间序列 $\{ t _ { k } \}$ 满足 $\begin{array} { r } { \operatorname* { l i m } _ { k \to + \infty } t _ { k } = + \infty } \end{array}$ ， $\begin{array} { r } { \operatorname* { l i m } _ { n  + \infty } \pmb { x } ( t _ { n } ) = \overline { { x } } } \end{array}$ 。

由式（12）可知 $\scriptstyle \operatorname* { l i m } _ { k \to + \infty } \left\| { \dot { x } } _ { t _ { k } } \right\| = 0$ ，从而有

$$
\begin{array} { r } { \operatorname* { l i m } _ { k  + \infty } - ( I - P ) ( \gamma _ { _ { t _ { k } } } + \overline { u } \xi _ { _ { t _ { k } } } ) = 0 } \end{array}
$$

其中 $\boldsymbol { \gamma } _ { t _ { k } } \in \partial f ( \boldsymbol { x } _ { t _ { k } } )$ ， $\boldsymbol { \xi } _ { t _ { k } } \in \partial G ( \boldsymbol { x } _ { t _ { k } } )$ 。由 ${ \widehat { o f } } ( x )$ 及 $\partial G ( \boldsymbol { x } )$ 是上半连续的集值映射，可知

$$
\mathrm { l i m } _ { k  + \infty } \gamma _ { t _ { k } } \in \partial f ( \overline { x } )
$$

$$
\begin{array} { r } { \operatorname* { l i m } _ { k  + \infty } \xi _ { t _ { k } } \in \hat { \sigma } G ( \overline { { x } } ) } \end{array}
$$

$$
0 \in h ( A { \overline { { x } } } - b )
$$

有 $0 \in - ( I - P ) ( \hat { \sigma } f ( \overline { { x } } ) + \overline { { u } } \hat { \sigma } G ( \overline { { x } } ) ) - A ^ { T } h ( A \overline { { x } } - b )$ 可知 $( { \overline { { x } } } , { \overline { { u } } } )$ 是网络模型式（2）的一个平衡点。

从式（13）可知，存在 $\overline { { \gamma } } \in \partial f ( \overline { { x } } )$ ， $\overline { { \xi } } \in \partial G ( \overline { { x } } )$ ，${ \overline { { \eta } } } \in h ( A { \overline { { x } } } - b )$ ，满足：

$$
\ k _ { 0 = - } ( \ I - \{ P \} ( \overline { { \gamma } } + \overline { { u } } \overline { { \xi } } ) - A ^ { T } \overline { { \eta } }
$$

令 $\pi = \overline { { { \eta } } } - ( A A ^ { T } ) ^ { - 1 } A ( \overline { { { \gamma } } } + \overline { { { u } } } \overline { { { \xi } } } )$ ，于是式（14）可以改写 成 $\boldsymbol { 0 } = \overline { { \gamma } } + \overline { { u } } \overline { { \xi } } + \boldsymbol { A } ^ { T } \boldsymbol { \pi }$ 。根据法锥的定义可知 $A ^ { T } \pi \in N _ { s _ { 2 } } ( \overline { { x } } )$ ， $u \overline { { \xi } } \in N _ { s _ { 1 } } ( \overline { { x } } )$ ，从而有

$$
0 \in \partial f ( \overline { { x } } ) + { N _ { s _ { 1 } } } ( \overline { { x } } ) + { N _ { s _ { 2 } } } ( \overline { { x } } )
$$

考虑优化问题的假定 $\mathrm { i n t } ( S _ { 1 } ) \cap S _ { 2 } \neq \emptyset$ ，有$N _ { \mathfrak { s } } ( \overline { { \mathfrak { x } } } ) { = } N _ { \mathfrak { s } _ { 1 } } ( \overline { { \mathfrak { x } } } ) + N _ { \mathfrak { s } _ { 2 } } ( \overline { { \mathfrak { x } } } )$ ，从而有

$$
0 \in \partial f ( \overline { { x } } ) + N _ { s } ( \overline { { x } } )
$$

即 $\overline { { x } }$ 是优化问题的一个关键点。

综上可知，网络模型的每一个聚点都是优化问题（1）的关键点，证毕。

# 3 实验仿真

神经网络最优化模式与常规的最优化算法的最大不同为神经网络模型的并行计算能力。得益于这种并行性能，神经网络模型已经被应用于广泛变化的科学工程应用中。为了检验微分包含的神经网络模型(2)的有效性，使用MATLAB2012a来仿真最优化问题式(1)，验证解轨迹 $x ( t )$ 最终收敛于 $\boldsymbol { D } ^ { * }$ 中的一个最优解。由于MATLAB2012a的默认数据类型为short，数据精度为保留小数点后四位，因此本文仿真的所有数据结果均保留四位小数。

例1 (目标函数非光滑，约束函数光滑)

$$
\begin{array} { l } { f ( \pmb { x } ) = \vert x _ { 1 } \vert + \cos ( x _ { 3 } ) + 2 x _ { 2 } ^ { 2 } } \\ { x _ { 1 } ^ { 2 } + x _ { 3 } ^ { 2 } - 1 0 \leq 0 } \\ { 2 x _ { 2 } + x _ { 2 } ^ { 2 } + x _ { 3 } - 5 \leq 0 } \\ { x _ { 1 } + x _ { 2 } + x _ { 3 } - 1 = 0 } \end{array}
$$

其中，目标函数为非光滑非凸，约束为光滑凸函数。取 5组随机初始点 $( - 1 . 5 , 1 . 5 , 1 . 5 ) ^ { T }$ 、 $( - 3 , 2 , 3 ) ^ { T }$ 、(0.5,-0.5,2.5)t、$( - 2 , 3 , 1 ) ^ { T } \cdot \ : \left( - 1 , 1 , 2 \right) ^ { T }$ ，其中， ${ \boldsymbol x } = ( x _ { 1 } , x _ { 2 } , x _ { 3 } ) ^ { T }$ 的轨迹如图1所示，所有解轨迹均可以收敛到唯一的平衡点。其解为$x = ( - 1 . 7 9 2 1 , - 0 . 2 1 5 6 , 3 . 0 0 3 8 ) ^ { T }$

![](images/7819d79af62c9136b65d0e02d05ca6cbcbb6515909a002e3cdf7fd8d37446ef5.jpg)  
图1例1解收敛轨迹

例2 (目标函数和约束函数均非光滑凸函数)

$$
x _ { 1 } ^ { 2 } + x _ { 2 } ^ { 2 } + x _ { 3 } ^ { 2 } - 8 \leq 0
$$

在例2中，目标函数是非光滑凸函数，其实一个不等式约束为非光滑凸函数。选取五组初始点： $( - 1 , 0 , 3 ) ^ { T }$ 、 $( - 2 , - 1 , 2 ) ^ { T }$ 、$( - 3 , 2 . 5 , 0 . 5 ) ^ { T } \cdot ( - 4 , 1 , 1 . 5 ) ^ { T } \cdot ( - 1 . 5 , 1 . 5 , 1 ) ^ { T }$ 。状态向量 $x ( t )$ 的解轨迹如图2所示， $x ( t )$ 均可以收敛于唯一解。其中，解为$x = ( 0 . 0 0 4 3 , 0 . 2 6 4 0 , 3 . 7 3 7 7 ) ^ { T } .$ 0

![](images/aef01cd1fa71c5ce5679a913459c190b6e1206e2f378f6f3bb7c2a3b13b4f9fb.jpg)  
图2例2解轨迹收敛

# 4 结束语

本文提出了一种新的解决非光滑非凸优化的等式和不等式约束的递归神经网络模型。跟传统神经网络模型相比，本文所提出的递归神经网络模型不需要任何的惩罚函数，解决了惩罚参数在实际中难以计算的问题，同时，网络收敛速度得到了极大的提高。最后，本文使用了两个例子验证了本文所提递归神经网络求解非光滑凸优化问题的理论的正确性。接下来的工作，我们将探索其他神经网络模型(尤其是混沌神经网络)对非光滑非凸最优化问题进行求解。

# 参考文献：

[1]Tank D W,Hopfield JJ. Simple neural optimization networks:an A//D converter, signal decision circuit,and a linear programming circuit [J].IEEE Trans on Circuits Systems,1986,33 (5): 533-541.   
[2]Kennedy M P, Chua L O. Neural networks for nonlinear programming [J]. IEEE Trans on Circuits Systems,1988,35(5):554-562.   
[3] Zhang Shengwei, Constantinides A G.Lagrange programming neural networks [J].IEEE Trans on Circuits and Systems I :Analog and Digital Signal Processing,1992,39(7): 441-452.   
[4] Feng Ruibin,Leung ChiSing,Constantinides A G,et al.Lagrange programming neural network for nondifferentiable optimization problems in sparse approximation [J]. IEEE Trans on Neural Networks and Learning Systems,2017,28 (10): 2395-2407.   
[5]Liang Junli,Leung Chising, So Hingcheung.Lagrange programming neural network approach for target localization in distributed MIMO radar [J]. IEEE Trans on Signal Processing,2016,64(6):1574-1585.   
[6]Liang Junli, So Hingcheung,Leung Chising,et al. Waveform design with unit modulus and spectral shape constraints via lagrange programming neural network [J]. IEEE Journal of Selected Topics In Signal Processing, 2015,9(8): 1377-1386.   
[7] Forti M,Nistri P,Quincampoix M.Generalized neural network for nonsmooth nonlinear programming problems [J].IEEE Trans on Circuits and Systems I: Regular Papers,2004,51 (9):1741-1754.   
[8]Bian Wei,Xue XiaoPing.Subgradient-based neural networksfor nonsmooth nonconvex optimization problems [J].IEEE Trans on Neural Networks,2009,20 (6):1024-1038.   
[9] Bian Wei， Xue XiaoPing.Subgradient-based neural networksfor nonsmooth convex optimization problems [J] IEEE Trans on Circuits and Systems I: Regular Papers,2008,55(8): 2378-2391.   
[10] Hu XiaoLin,Wang Jun. Solving pseudomonotone variational inequalities and pseudoconvex optimization problems using the projection neural network [J].IEEE Trans on Neural Networks,2006,17 (6):1487-1499.   
[11] Cheng Long, Hou Zengguang, Lin Yingzi,et al. Recurrent neural network for non-smooth convex optimization problems with application to the identification of genetic regulatory networks[J].IEEE Trans on Neural Networks,2011,22 (5): 714-726.   
[12] Qin Sitian,Feng Jiqiang,Song JiaHui,et al.Aone-layer recurrnt neural network for constrained complex-variable convex optimization [J].IEEE Trans on Neural Networks and Learning Systems,2018,29 (3): 534-544.   
[13] Liu Xiaolan, Zhou Mi.Aone-layer recurrent neural network for non-smooth convexoptimization subject to linear inequality constraints [J].Chaos, Solitons and Fractals,2016 (87): 39-46.   
[14] Guo Zhishan, Liu Qingshan,Wang Jun.A one-layer recurrent neural network for pseudoconvex optimization subject to linear equality constraints [J]. IEEE Trans on Neural Networks,2011,22(12):1982-1900.   
[15]Liu Qingshan,Guo Zhishan,Wang Jun.A one-layer recurrent neural network for constrained pseudoconvex optimization and its application for dynamic portfolio optimization [J].Neural Networks,2012,21(1): 99-109.   
[16] Liu Qingshan， Cao Jinde,Chen Guangrong. A novel recurrent neural network with finite-time convergence for linear programming [J]. Neural Computation,2010,22 (11): 2962-2978.   
[17] Huang Yuancan, Yu Chuang. Improved lagrange nonlinear programming neural networks for inequality constraints [C]// Proc of International Joint Conference on Neural Networks.2007: 962-966   
[18]喻昕，许治健，陈昭蓉，等．拉格朗日神经网络解决带等式和不等式约 束的非光滑非凸优化问题[J].电子与信息学报，2017,39(8):1950- 1955.(Yu Xin,Xu Zhijian,Zhen Zhaorong,et al.Lagrange neural network fornonsmooth nonconvex optimization problems with equalityand inequality constrains[J]. Journal of Electronics &Information Technology, 2017,39 (8): 1950-1955. )   
[19] Aubin JP, Cellina A.Differential inclusion: set-valued maps and viability theory [M].Berlin: Springer-Verlag,1984.   
[20] Clarke FH. Optimization and nonsmooth analysis [M]. New York,USA: Wiley, 1983.   
[21]喻昕，李晨宇，许治健，等．一种新型拉格朗日神经网络解决非光滑优 化问题[J].计算机应用研究,2016,33(11):3261-3264,3269.(Yn Xin, Li Chenyu, Xu Zhijian,et al. Novel lagrange neural network for nonsmooth optimization problems [J]. Application Research of Computers,2016,33 (11): 3261-3264,3269. )   
[22]喻昕，于琰，谢缅．光滑拉格朗日神经网络解决非光滑最优化问题 [J]. 计算机应用研究,2014,31(5):1349-1352.(Yu Xin,Yu Yan,Xie Mian. Smoothing Lagrange neural network for constrained nonsmooth

optimization problems [J].Application Research of Computers,2014,31 (5): 1349-1352.)

[23]喻昕，谢缅，李晨宇．光滑神经网络解决非李普西茨优化问题的研究[J].计算机工程与科学,2015,37(12):2262-2269.(Yu Xin,Xie Mian,Li

Chenyu. Solving non-Lipschitz optimization problems by smoothing neural networks [J]. Computer Engineering and Science,2015,37 (12): 2262- 2269.)