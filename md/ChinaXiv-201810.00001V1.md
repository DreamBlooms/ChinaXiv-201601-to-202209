# 霍奇星算子与外微分算符的组合规律

彭俊金

(贵州师范大学 物理与电子科学学院，贵州贵阳550001)

摘要：本文系统地探讨了霍奇星算子与外微分算符作用于任意微分形式场时两者的一般组合规律。首先，找到了保持微分形式场的次不变的两个组合算符，并通过二者的线性组合得到了一个新算符。其次，当由任意数目的霍奇星算子与外微分算符进行组合时，作者导出了所有形式上彼此互异的组合算符的统一表达式，这些表达式由单个霍奇星算子与外微分算符以及二者的任选两个的非零组合构成。在此基础上，分析了所有算符之间的相互作用关系，并根据这些算符对微分形式的次的改变情况，对它们进行了具体分类。最后，作为一个应用，作者详细讨论了如何由次相同的微分形式的线性组合来构造电磁场的麦克斯韦方程。

关键词：霍奇星算子；外微分算符；麦克斯韦方程；广义相对论；微分几何中图分类号：00412.1 文献标识码：A 文章编号：

【DOI】

由著名数学家嘉当(Cartan)率先倡导的微分形式[](differential form)的现代观念，在几何与拓扑等数学领域以及物理学的诸多领域有着非常广泛的应用，尤其在数学物理与理论物理等物理学分支，微分形式已成为一种研究广义相对论、规范场论（如电磁理论与Yang-Mills理论等）、超引力以及弦理论等极其有效的工具。

对微分形式的操作过程中，必然离不开楔形积(wedge product)、霍奇星算子(Hodge staroperator，用\*表示)与外微分算符(exterior differentiation operator，由 $d$ 表示)等三种基本操作。楔形积易于理解，因此，本文只关注最后两种算符，在此对它们做一个简单介绍，下文即将给出二者的具体定义与主要性质，部分详细过程可参考文献[1-5]等。由著名数学家霍奇(Hodge)首次引入的Hodge 星算子是一个定义在有限维定向向量空间的外代数3上的线性映射，在单个Hodge 星算子的作用下,维度为n的微分流形上的p-形式(p-form)可转换成一个(n-p)-形式，但是，偶数个霍奇星算子的连续作用不改变微分形式场的次，也不改变其分量的大小，仅有可能整体上带来一个负号。另一方面，外微分算符是作用于函数的普通微分算符在微分形式场上的延展，也常称为外导数(exterior derivative)，当它作用于p次微分形式时相当于把各个分量分别看成一个函数并对其进行偏微分，生成 $( \mathsf { p } { + } 1 )$ 次形式，连续两次作用于微分形式的结果恒等于零。

归因于霍奇星算子与外微分算符自身属性的限制，两者中的任意一个连续两次及以上作用于微分形式场时，前者在偶数次作用的前提下几乎对这些场不带来影响，后者直接为零，因此，孤立地考虑二者中的某一个，终究对场的改变有限。为了拓展这两类算符对微分形式的作用效果，一条有效的途径就是考虑二者的所有可能的非零组合，其中如余微分算子[3]。那么，它们彼此之间究竟有怎样的一般组合规律？这正是本文拟将解决的问题。

# 1保持微分形式场的次不变的组合算符

在本节中，我们将详细探讨如何把Hodge 对偶星算子与外微分算符作用于微分形式来构造分量大小有变化但微分形式的次仍然不变的新的量。在此基础上，给出两个以及三个

Hodge星算子与外微分算符组合的一般规律。

考虑让Hodge 星算子 $^ *$ 与外微分算符 $d$ 分别作用于 $\mathbf { n }$ 维时空流形上的任意 $\mathsf { p }$ 次微分形式场 $A$ 来给出它们的定义，微分形式 $A$ 记为

$$
A = \frac { 1 } { p ! } A _ { \mu _ { 1 } \cdots \mu _ { p } } d \boldsymbol { X } ^ { \mu _ { 1 } \cdots \mu _ { p } }
$$

采用通常做法，上式以及下文中，把对偶坐标基底的楔形积 $d X ^ { \mu _ { 1 } } \wedge \cdots \wedge d X ^ { \mu _ { p } }$ 简写为（204号 $d _ { X } ^ { \mu _ { 1 } \cdots \mu _ { p } }$ ， $A _ { \mu _ { 1 } \cdots \mu _ { p } }$ 就是一个 $\mathsf { p }$ 阶完全反对称量。为了方便于讨论，在整个行文过程中，把霍奇星算子与外微分算符分别记为 $\ast = P _ { 1 }$ 与 $d = P _ { 2 }$ ，二者简称为基本算符，并约定 $P$ 的下脚指标“1”与“2”依次对应于算符 $^ { 6 6 } * \prime$ 与“ $d$ ”。 $P _ { 1 }$ 与 $P _ { 2 }$ 作用于 $\mathsf { p }$ 形式场 $A$ 分别得到其对偶微分形式 $\ast A = P _ { 1 } A$ 以及 $d A = P A$ ，由分量形式表示为

$$
\begin{array} { r c l } { { \displaystyle ( P _ { 1 } A ) _ { \mu _ { 1 } \cdots \mu _ { q } } ~ = ~ \frac { 1 } { p ! } ~ A ^ { \nu _ { 1 } \cdots \nu _ { p } } \tilde { \varepsilon } _ { \nu _ { 1 } \cdots \nu _ { p } \mu _ { 1 } \cdots \mu _ { q } } } } \\ { { \displaystyle ( P _ { 2 } A ) _ { \mu _ { 1 } \cdots \mu _ { p + 1 } } ~ = ~ ( p + 1 ) \hat { \sigma } _ { [ \mu _ { 1 } } A _ { \mu _ { 2 } \cdots \mu _ { p + 1 } ] } } } \end{array}
$$

这里以及下文中，设定 $q \ : = \ : n \ : - \ : p$ ， $\mathbf { n } \cdot$ -阶完全反对称的协变Levi-Civita张量定义为（204 $\tilde { \varepsilon } _ { _ { 1 \cdots n } } = \sqrt { | _ { g } | }$ ， $g$ 为时空度规的行列式。上式第二个方程中的偏微分 $\hat { o }$ 可替换成通常的协变导数算符 $\nabla$ ，并满足 $d ^ { 2 } A = 0$ ，也就是说，任意微分形式经过外微分算符的连续两次作用后始终等于零。很显然， $P _ { 1 } P _ { 2 } \ne P _ { 2 } P _ { 1 }$ 。

首先，我们考虑如何把Hodge 对偶星算子与外微分算符或二者的组合作用于 $\mathbf { p } \cdot$ 形式 $A$ 来构造分量大小有变化的新的 $\mathfrak { p }$ 次形式场。如果任意选取二者中的两个作用于 $A$ ，有四种基本组合模式，相应可得四种操作：

$$
\begin{array} { c c } { { P _ { _ { 1 2 } } = \ast d , P _ { _ { 2 1 } } = d \ast , } } \\ { { } } & { { } } \\ { { P _ { _ { 1 1 } } = \ast \ast , P _ { _ { 2 2 } } = d d } } \end{array}
$$

$P _ { 1 2 }$ 与 $P _ { 2 1 }$ 作用于 $\mathsf { p }$ 次微分形式场分别得到(q-1)与 $( \mathsf { q } + \mathsf { 1 } )$ 次形式，两者的次相差为2。不难验证，$P _ { 1 2 }$ 与 $P _ { 2 1 }$ 互易且相继作用于 $A$ 等于零，这样，

$$
P _ { 1 2 } P _ { 2 1 } = P _ { 2 1 } P _ { 1 2 } = 0
$$

由 $P _ { 1 1 }$ 作用于 $A$ ，借助两个Levi-Civita 张量的乘积关系式以及推广的Kronecker delta 符号部分或全部指标缩并的关系式

$$
\begin{array} { c } { { \tilde { \varepsilon } ^ { \nu _ { 1 } \cdots \nu _ { n } } \tilde { \varepsilon } _ { \mu _ { 1 } \cdots \mu _ { n } } = \mathrm { s g n \left( g \right) } \delta _ { \mu _ { 1 } \cdots \mu _ { n } } ^ { \nu _ { 1 } \cdots \nu _ { n } } } } \\ { { \mathrm { } } } \\ { { \delta _ { \alpha _ { 1 } \cdots \alpha _ { n - m } \mu _ { 1 } \cdots \mu _ { m } } ^ { \alpha _ { 1 } \cdots \alpha _ { n - m } \nu _ { 1 } \cdots \nu _ { m } } = \left( n - m \right) ! \delta _ { \mu _ { 1 } \cdots \mu _ { m } } ^ { \nu _ { 1 } \cdots \nu _ { m } } } } \end{array}
$$

（推广的 Kronecker delta 符号定义为 $\delta _ { \mu _ { 1 } \cdots \mu _ { m } } ^ { \nu _ { 1 } \cdots \nu _ { m } } = m ! \delta _ { \mu _ { 1 } } ^ { [ \nu _ { 1 } } \cdot \cdot \cdot \delta _ { \mu _ { m } } ^ { \nu _ { m } ] }$ ，而逆变 Levi-Civita 张量约定为 $\widetilde { \varepsilon } ^ { 1 \cdots n } { = } _ { \mathrm { { S g n } } } ( \mathrm { { g } } ) / \sqrt { | \varrho | }$ ，这里 $\operatorname { s g n } \left( \operatorname { g } \right)$ 为符号函数，欲了解两式的更多详情，参见文献[6])，得到

$$
\begin{array} { c } { { P _ { 1 1 } ^ { ~ 2 k } A = A , } } \\ { { P _ { 1 1 } ^ { ~ 2 k + 1 } A = \mathrm { s g n } ( g ) ( - 1 ) ^ { p q } A } } \end{array}
$$

除非特别说明，这里以及下文中 $k$ 默认为非负整数。(6)式表明 $P _ { 1 1 }$ 不改变微分形式的次，尽管如此，当符号系数 $\operatorname { s g n } \left( g \right) ( - 1 ) ^ { p q } = - 1$ 时，它在整体上给微分形式场带来一个负号但不会导致分量大小的变化。此外， $P _ { 2 2 } A = 0$ （可令 $P _ { \mathrm { 2 2 } } = 0$ )，因此，为了构造有实质变化的不同的 $\mathsf { p } \cdot$ -形式场，完全可以排除 $P _ { 1 1 }$ 与 $P _ { 2 2 }$ 这两个平庸操作。

再来分析 $P _ { 1 1 }$ 与 $P _ { 2 }$ ， $P _ { 1 2 }$ 以及 $P _ { 2 1 }$ 分别交换作用顺序的关系，它们依次为

$$
\begin{array} { c } { { P _ { _ { 1 1 } } P _ { _ { 2 } } = ( - 1 ) ^ { n - 1 } P _ { _ { 2 } } P _ { _ { 1 1 } } , } } \\ { { { } } } \\ { { P _ { _ { 1 1 } } P _ { _ { 1 2 } } = ( - 1 ) ^ { n - 1 } P _ { _ { 1 2 } } P _ { _ { 1 1 } } , } } \\ { { { } } } \\ { { P _ { _ { 1 1 } } P _ { _ { 2 1 } } = ( - 1 ) ^ { n - 1 } P _ { _ { 2 1 } } P _ { _ { 1 1 } } } } \end{array}
$$

如果两个算符交换顺序前后生成次不同的微分形式场，本文认为二者没有可比性，如 $P _ { 1 } P _ { 2 }$ 与${ \cal P } _ { 2 } { \cal P } _ { 1 }$ ， $P _ { 2 } P _ { 1 2 }$ 与 $P _ { 1 2 } P _ { 2 }$ ，以及 $P _ { 2 } P _ { 2 1 }$ 与 $P _ { 2 1 } P _ { 2 }$ 等。很显然， $P _ { 1 1 }$ 与 $P _ { 1 }$ 对易，即 $[ P _ { 1 1 } , P _ { 1 } ] = 0$ ，但是，只有当时空流形的维度 $\boldsymbol { \mathit { \Pi } } _ { n }$ 为奇数时， $[ P _ { 1 1 } , P _ { 2 } ] = 0$ ， $\left[ P _ { \mathrm { 1 1 } } , P _ { \mathrm { 1 2 } } \right] = 0$ 以及 $\lbrack P _ { 1 1 } , P _ { 2 1 } ] = 0$ ;当 $\boldsymbol { \eta }$ 为偶数时， $\left[ P _ { 1 1 } , P _ { 2 } \right] _ { + } = 0$ ， $\left[ P _ { \mathrm { 1 1 } } , P _ { \mathrm { 1 2 } } \right] _ { + } = 0$ 以及 $\left[ P _ { \mathrm { 1 1 } } , P _ { \mathrm { 2 1 } } \right] _ { + } = 0$ ，也就是说， $P _ { 1 1 }$ 与 $P _ { 2 }$ ，$P _ { 1 2 }$ 以及 $P _ { 2 1 }$ 三者中的任意一个反对易。

鉴于(4)与(7)两式，可以证明，从 $P _ { 1 }$ ， $P _ { 2 }$ ， $P _ { 1 1 }$ ， $P _ { 1 2 }$ 与 $P _ { 2 1 }$ 等五个算符中选取的任意操作组合，能够生成新的有实质不同的 $\mathsf { p } \cdot$ -形式场的最少操作组合只能是

$$
O _ { 1 } \ = \ { P _ { 1 2 } } ^ { 2 } , O _ { 2 } \ = \ { P _ { 2 1 } } ^ { 2 }
$$

这两种。显然， $O _ { 1 } O _ { 2 } = O _ { 2 } O _ { 1 } = 0$ 。二者的更具体表达式可由它们对 $\mathsf { p } ^ { \mathsf { \_ p } }$ 形式 $A$ 的作用来给出。

为了得到 $O _ { 1 } A$ 与 ${ \cal O } _ { 2 } A$ 的具体结果，先由推广的Kronecker符号的性质来求解 $\mathsf { p } \cdot$ 形式 $A$ 依

次由外微分算符与霍奇对偶的作用 $\ast d A = P _ { 1 2 } A$ ，以及它的对偶微分形式经由外微分算子的作用 $d * A = P _ { 2 1 } A$ 。利用(2)式，前者的分量形式可表示为

$$
( P _ { _ { 1 2 } } A ) _ { { \mu _ { 1 } } \cdots { \mu _ { q - 1 } } } = \frac { 1 } { p ! } \tilde { \varepsilon } _ { _ { \alpha _ { 1 } \cdots \alpha _ { p + 1 } \mu _ { 1 } \cdots \mu _ { q - 1 } } } \nabla ^ { \alpha _ { 1 } } A ^ { \alpha _ { 2 } \cdots \alpha _ { p + 1 } }
$$

而在(5)式的帮助下，后者的分量形式为

$$
( P _ { 2 1 } A ) _ { \mu _ { 1 } \cdots \mu _ { q + 1 } } = \frac { 1 } { ( p - 1 ) ! } \tilde { \varepsilon } _ { \alpha _ { 1 } \cdots \alpha _ { p - 1 } \mu _ { 1 } \cdots \mu _ { q + 1 } } \nabla _ { \rho } A ^ { \alpha _ { 1 } \cdots \alpha _ { p - 1 } \rho }
$$

再用 $P _ { 1 2 }$ 操作一次(9)式，并应用(5)式，有

$$
( { \cal O } _ { 1 } A ) _ { \mu _ { 1 } \cdots \mu _ { p } } = c _ { 3 } ( p + 1 ) \nabla ^ { \rho } \nabla _ { [ \rho } A _ { \mu _ { 1 } \cdots \mu _ { p } ] }
$$

得到一个新的 $\mathsf { p } \cdot$ -形式场，全文中，约定符号系数 $c _ { 3 } = \mathrm { s g n } ( g ) ( - 1 ) ^ { p ( q - 1 ) }$ 。下文中即将看到,组合算符 $O _ { \scriptscriptstyle 1 }$ 与熟知的达朗贝尔算子之间有一定的联系。同样，再让 $P _ { 2 1 }$ 作用于(10)式，又可得一个 $\mathsf { p } ^ { \mathsf { \_ p } }$ -形式场

$$
\left( { \cal O } _ { 2 } A \right) _ { \mu _ { 1 } \cdots \mu _ { p } } = ( - 1 ) ^ { n } c _ { 3 } p \nabla _ { [ \mu _ { 1 } } \nabla ^ { \rho } A _ { \rho | \mu _ { 2 } \cdots \mu _ { p } ] }
$$

如果再次以(11)与(12)两式中的 $\mathsf { p } \cdot$ 形式场 $O _ { 1 } A$ 与 $O _ { 2 } A$ 为出发点，重复上述过程，又可导出两个新的 $\mathsf { p } ^ { \mathsf { \_ p } }$ -形式场。如此反复，以 $A$ 出发，最终能够得到一系列形式上彼此独立的 $\mathsf { p }$ 次微分形式场 $P _ { 1 2 } ^ { ~ 2 j } A = O _ { 1 } ^ { j } A$ 以及 $P _ { 2 1 } ^ { ~ 2 j } A = O _ { 2 } ^ { ~ j } A ( { \bf \Phi } j$ 为非负整数)。与此不同的是， $P _ { 1 2 } O _ { 1 } ^ { j } A$ 与 $P _ { 2 1 } O _ { 2 } ^ { j } A$ （20分别为 $( \mathsf { q } \mathsf { - } 1 )$ 与 $( \mathsf { q } + \mathsf { l } )$ 次形式场，而(4)式直接排除了 $P _ { 1 2 }$ 与 $P _ { 2 1 }$ 的混合对 $A$ 的作用。值得强调的是,由于算符 $O _ { \mathrm { { _ { l } } } }$ 与 $O _ { 2 }$ 具有保持微分形式的次不变的优点，如果考虑四个及以上基本算符 $P _ { 1 }$ 与$P _ { 2 }$ 的组合操作时，可以尝试尽量让 $O _ { 1 }$ 与 $O _ { 2 }$ 来表示它们。

既然 $O _ { 1 }$ 与 $O _ { 2 }$ 保持微分形式的次不变，就能够实现二者之间的线性叠加，考虑由它们的线性组合定义一个新的算符 $\Psi$ ，具体有

$$
\begin{array} { c } { { \Psi = \gamma _ { { } _ { 1 } } O _ { { 1 } } + \gamma _ { { } _ { 2 } } O _ { { 2 } } } } \\ { { \Psi ^ { j } = { } \gamma _ { { } _ { 1 } } ^ { ~ j } O _ { { 1 } } ^ { ~ j } + { } \gamma _ { { } _ { 2 } } ^ { ~ j } O _ { { 2 } } ^ { ~ j } } } \end{array}
$$

上式第二个方程的导出用到了性质 $O _ { 1 } O _ { 2 } = O _ { 2 } O _ { 1 } = 0$ 。当系数 $\gamma _ { _ 1 } = \gamma _ { _ 2 } = - 1$ 时， $\Psi$ 为通常的 Laplace-de Rham 算子。为了理解 $\Psi$ 的意义，有必要确定 $O _ { \mathrm { { _ { l } } } }$ 与 $O _ { 2 }$ 作用于任意微分形式时彼此的具体联系。基于推广的Kronecker符号的解除反对称方括号的性质及其展开式，

以及黎曼曲率张量(Riemann curvature tensor)的定义 ${ } ^ { [ 4 ] } ( \nabla _ { \rho } \nabla _ { \sigma } - \nabla _ { \sigma } \nabla _ { \rho } ) _ { V _ { \mu } } = R _ { \rho \sigma \mu \nu } { } ^ { V }$ （这里$\boldsymbol { V } _ { \mu }$ 为任意协变矢量)，经过冗长的计算，我们进一步导出(11)式中 ${ \cal O } _ { 1 } A$ 与(12)式中 ${ \cal O } _ { 2 } A$ 两者的如下关系

$$
\begin{array} { r } { \left( { \cal O } _ { 1 } { \cal A } \right) _ { \mu _ { 1 } \cdots \mu _ { p } } = \left( - 1 \right) ^ { n + 1 } \left( { \cal O } _ { 2 } { \cal A } \right) _ { \mu _ { 1 } \cdots \mu _ { p } } + } \\ { c _ { 3 } \boxed { A } _ { \mu _ { 1 } \cdots \mu _ { p } } + \Omega _ { \mu _ { 1 } \cdots \mu _ { p } } } \end{array}
$$

上式中，达朗贝尔算子(d'Alembert operator) $\begin{array} { r } { \bigsqcup = \nabla ^ { \sigma } \nabla _ { \sigma } } \end{array}$ ， $\mathsf { p }$ 阶反对称张量 $\Omega _ { \mu _ { 1 } \cdots \mu _ { p } }$ 是一个与黎曼曲率张量 $R _ { \rho \sigma \mu \nu }$ 有关的量，定义为

$$
\begin{array} { r } { \Omega _ { \mu _ { 1 } \cdots \mu _ { p } } = - 2 ^ { - 1 } c _ { 3 } p ( 2 R _ { \rho [ \mu _ { 1 } } A ^ { \rho } { } _ { \mu _ { 2 } \cdots \mu _ { p } ] } - } \\ { ( p - 1 ) R _ { \rho \sigma [ \mu _ { 1 } \mu _ { 2 } } A ^ { \rho \sigma } { } _ { \mu _ { 3 } \cdots \mu _ { p } ] } ) } \end{array}
$$

由此可知，如果时空平直，即 $R _ { \rho \sigma \mu \nu } ~ = ~ 0$ ，相应地 $\Omega _ { \mu _ { 1 } \cdots \mu _ { p } } ~ = ~ 0$ ，该条件下，当 $\gamma _ { _ { 1 } } = 1 / c _ { _ { 3 } }$ 且 $\gamma _ { _ 2 } \ = \ ( - 1 ) ^ { n } { c _ { _ 3 } } ^ { - 1 }$ 时，组合算符 $\Psi \ { = } \boxed { }$ ，正好是达朗贝尔算子；反之，若 $R _ { \rho \sigma \mu \nu } \neq 0$ ，可以证明，对于任意 $\mathsf { p } \cdot$ 形式 $A$ ，并不能保证 $\Omega _ { \mu _ { 1 } \cdots \mu _ { p } } ~ = ~ 0$ 恒成立。综合可得结论：当且仅当时空平直时， $\Psi$ 才能表示成适用于任意微分形式的达朗贝尔算子。尽管如此，如果对微分形式场进行特殊选择，比如，对于1次形式 $A _ { \phantom { } \mu }$ ，只要Ricci 曲率张量 $R _ { \mu \nu } = 0$ ，或更一般地,只需要求 $\mathsf { p } \cdot$ 形式 $A$ 满足 $\Omega _ { \mu _ { 1 } \cdots \mu _ { p } } ~ = ~ 0$ 的限制条件，也能确保 $\Psi \ { = } \breve { \sqcup }$ 成立。

其次，基于上述对 $P _ { 1 }$ ， $P _ { 2 }$ ， $P _ { 1 1 }$ ， $P _ { 1 2 }$ 与 $P _ { 2 1 }$ 等五个算符的分析，可以总结其中任意二者的组合作用于 $\mathsf { p } \cdot$ -形式场 $A$ 的一般规律，具体见下表1:

表1五个算符之间相互作用关系  

<html><body><table><tr><td></td><td>P</td><td>P</td><td>P</td><td>P</td><td>Pe</td></tr><tr><td>P</td><td>c1</td><td>P2</td><td>cP</td><td>c2P2</td><td>P1</td></tr><tr><td>P</td><td>Pe</td><td>0</td><td>cP</td><td>P212</td><td>0</td></tr><tr><td>P</td><td>cP</td><td>C</td><td>1</td><td>C2P2</td><td>C2P</td></tr><tr><td>P</td><td>Pa</td><td>0</td><td></td><td>0</td><td>0</td></tr><tr><td>P2</td><td>qP</td><td>P212</td><td>cP2</td><td>0</td><td>02</td></tr></table></body></html>

表1中，除第1行与第1列以外，所有元素均是其所在行第一个元素与其所在列第一个元素的依次组合的结果（列中算符先作用于A），如第3行与第5列所在元素为P2P2= P212。表中所有组合算符作用于任意微分形式时，只有经由对角元素的操作才能保持它们的次不变，由此进一步验证了(8)式中的结论。“1”理解为单位算符，两个符号系数 $c _ { 1 }$ 与 $c _ { 2 }$ 分别定义为

$$
\begin{array} { l } { { c _ { _ { 1 } } = \mathrm { s g n } \left( g \right) ( - 1 ) ^ { p q } } } \\ { { { c _ { _ { 2 } } } = ( - 1 ) ^ { n - 1 } c _ { _ { 1 } } } } \end{array}
$$

也就是说， $c _ { 1 , 2 }$ 只可能取正负1，与 $c _ { 3 }$ 的关系为 $c _ { 3 } = ( - 1 ) ^ { p } c _ { 1 }$ 。当时空流形的维度 $\boldsymbol { \mathit { \Pi } } _ { n }$ 为奇数时， $c _ { 1 }$ 与 $c _ { 2 }$ 同号，此外，为偶数时，二者异号。 $P _ { 1 1 }$ 、 $P _ { 2 2 }$ 、 $O _ { 1 }$ 与 $O _ { 2 }$ 对 $A$ 的作用由(9)与(12)四式依次给出，而操作 $P _ { 1 2 1 }$ 与 $P _ { 2 1 2 }$ 定义如下

$$
P _ { 1 2 1 } = * d * , P _ { 2 1 2 } = d * d
$$

显然，二者有 ${ P _ { 2 1 2 } } ^ { 2 } \ = \ { P _ { 1 2 1 } } ^ { 2 } \ = \ 0$ ， $P _ { 1 2 1 } P _ { 2 1 2 } = P _ { 1 2 } ^ { 3 }$ ， $P _ { 2 1 2 } P _ { 1 2 1 } = P _ { 2 1 } ^ { 3 }$ ， $P _ { 1 } P _ { 2 1 2 } = P _ { 1 2 1 } P _ { 2 }$ ，$P _ { 2 1 2 } P _ { 1 } = P _ { 2 } P _ { 1 2 1 } , [ P _ { 1 1 } , P _ { 2 1 2 } ] = 0$ 以及 $P _ { 1 1 } P _ { 1 2 1 } = ( - 1 ) ^ { n - 1 } P _ { 1 2 1 } P _ { 1 1 }$ 等相互作用关系，它们作用于任意 $\mathsf { p } ^ { \mathsf { \_ p } }$ -形式场 $A$ 的具体结果分别为

$$
\begin{array} { l } { { ( P _ { _ { 1 2 1 } } A ) _ { \mu _ { 1 } \cdots \mu _ { p - 1 } } = ( - 1 ) ^ { n } c _ { 3 } \nabla ^ { \rho } A _ { \rho \mu _ { 1 } \cdots \mu _ { p - 1 } } \hfill } } \\ { { \displaystyle ( P _ { _ { 2 1 2 } } A ) _ { \mu _ { 1 } \cdots \mu _ { q } } = \frac { p + 1 } { p ! } \tilde { \varepsilon } _ { \alpha _ { 1 } \cdots \alpha _ { p } \mu _ { 1 } \cdots \mu _ { q } } \hfill \times } } \\ { { \mathrm { V } _ { \rho } \nabla ^ { [ \alpha _ { 1 } ] \alpha _ { 2 } \cdots \alpha _ { p } \rho ] } } } \end{array}
$$

由此可见，操作 $P _ { 1 2 1 }$ 与微分形式相作用实质上就是对其作用对象进行物理学上的散度运算，它与余微分[3] (codifferential) $\delta$ 有这样的关系

$$
\delta = \operatorname { s g n } \left( g \right) ( - 1 ) ^ { n p + n } P _ { 1 2 1 }
$$

易得 $\delta ^ { 2 } { = } c _ { { } _ { 2 } } P _ { { } _ { 1 2 } } P _ { { } _ { 2 1 } } = 0$ 。

最后,把基本算符 $P _ { 1 }$ 与 $P _ { 2 }$ 作用于任意两个Hodge对偶与外微分算符的3个非零组合 $P _ { 1 1 }$ ，（204号 $P _ { 1 2 }$ 与 $P _ { 2 1 }$ ，可以得到由三个基本算符构成的5个非零的独立组合操作。除了(17)式中的两个操作 $P _ { 1 2 1 } = P _ { 1 } P _ { 2 1 }$ 与 $P _ { \mathrm { 2 1 2 } } { = } P _ { \mathrm { 2 } } P _ { \mathrm { 1 2 } }$ 外，还有如下三者

$$
\begin{array} { r l } { { \displaystyle P _ { _ { 1 1 1 } } = P _ { _ { 1 } } P _ { _ { 1 1 } } , } } & { { } { P _ { _ { 2 1 1 } } = P _ { _ { 2 } } P _ { _ { 1 1 } } , } } \\ { { \displaystyle P _ { _ { 1 1 2 } } = P _ { _ { 1 } } P _ { _ { 1 2 } } = ( - 1 ) ^ { n - 1 } P _ { _ { 2 } } P _ { _ { 1 1 } } } } \end{array}
$$

根据表1，它们作用于 $\mathsf { p } ^ { \mathsf { \_ p } }$ -形式场 $A$ 有这样一些结果：

$$
\begin{array} { l } { { P _ { 2 1 1 } A = \mathrm { s g n } \left( g \right) ( - 1 ) ^ { p q } d A } } \\ { { P _ { 1 1 1 } A = \mathrm { s g n } \left( g \right) ( - 1 ) ^ { p q } \ast A } } \\ { { P _ { 1 1 2 } A = \mathrm { s g n } \left( g \right) ( - 1 ) ^ { p q + n - 1 } d A } } \end{array}
$$

到此为止，(18)与(21)两式给出了三个基本算符的非零组合操作作用于微分形式的所有结果，

但与 $P _ { 1 }$ 、 $P _ { 2 }$ 作用的结果有本质区别的只有 $P _ { 1 2 1 }$ 与 $P _ { 2 1 2 }$ 这两个操作。

# 2任意霍奇星算子与外微分算符的一般组合规律

在上一节的基础上，本节中，我们将进一步全面系统地探讨任意数目的 Hodge 星算子与外微分算符共同作用于微分形式场的一般组合规律,给出所有可能的非零且形式上独立的组合操作的一般表达式，在此基础上，再来分析它们的相互作用关系，并依据这些操作生成的微分形式的次来对它们进行分类。

# 2.1所有非零独立组合算符的统一表达式

考虑把上一节中两个以及三个基本算符 $P _ { 1 }$ 与 $P _ { 2 }$ 的组合模式推广到任意 $N$ 个的情形。一方面，由于 $P _ { 2 } ^ { 2 } = 0$ 以及 $P _ { 1 1 }$ 仅有可能改变微分形式场的符号，因此，不能连续出现两个外微分算符，并且，相邻两个外微分算符 $P _ { 2 }$ 之间仅能有奇数个 Hodge 对偶的组合 $P _ { 1 } P _ { 1 1 } ^ { \ k }$ ，形成 $P _ { 2 } P _ { 1 } P _ { 1 1 } ^ { \ k } P _ { 2 }$ 的结构 （利用(7)式中 $P _ { 1 1 }$ 与 $P _ { 2 }$ 的交换关系，等价为 $( - 1 ) ^ { k ( n - 1 ) } P _ { _ 2 } P _ { _ 1 } P _ { _ 2 } P _ { _ { 1 1 } } ^ {  { k } } )$ ，也就是说，两个相邻 $P _ { 1 2 }$ 或 $P _ { 2 1 }$ 之间只可能出现算符 $P _ { 1 1 } ^ { \ k }$ ，一起构成形如 $P _ { 1 2 } P _ { 1 1 } ^ { \ k } P _ { 1 2 }$ 或 $P _ { 2 1 } P _ { 1 1 } ^ { \ k } P _ { 2 1 }$ 的组合。另一方面， (7)式表明 $P _ { 1 1 }$ 与 $P _ { 1 2 }$ 、 $P _ { 2 1 }$ 二者中的任意一个交换先后作用顺序时乘上一个符号系数 $( - 1 ) ^ { n - 1 }$ ，仅有可能带来符号的变化，这样，总可以通过置换排列顺序，把相邻 $P _ { 1 2 }$ （204号（ $P _ { 2 1 }$ ）之间的所有 $P _ { 1 1 }$ 算符置换到最左端或最右端，而(4)式直接排除了混合 $P _ { 1 2 }$ 与 $P _ { 2 1 }$ 的操作组合 $P _ { 1 2 } P _ { 1 1 } ^ { \ k } P _ { 2 1 }$ 与 $P _ { 2 1 } P _ { 1 1 } ^ { \ k } P _ { 1 2 }$ 的出现。基于此，对于 $N$ 个 Hodge 星算子与外微分算符的任意非零值组合，总可以表示成如下

$$
\begin{array} { l } { { U _ { 1 } } = ( - 1 ) ^ { { m ( n - 1 ) } } P _ { 1 } ^ { \tau } P _ { 1 2 } ^ { \phantom { } j } P _ { 1 1 } ^ { \phantom { } k } , } \\ { { \phantom { = } } } \\ { { U _ { 2 } } = ( - 1 ) ^ { { m ( n - 1 ) } } P _ { 1 } ^ { \tau } P _ { 2 1 } ^ { \phantom { } j } P _ { 1 1 } ^ { \phantom { } k } , } \\ { { \phantom { = } } } \\ { { U _ { 3 } } = ( - 1 ) ^ { { m ( n - 1 ) } } P _ { 2 } ^ { \phantom { } j } P _ { 1 2 } ^ { \phantom { } j } P _ { 1 1 } ^ { \phantom { } k } } \end{array}
$$

三种形式之一。上式以及下文中，约定 $\tau = 0 , 1$ ； $\boldsymbol { \mathit { m } }$ 与 $j$ 默认为非负整数(除非特别指出)，m指代把所有 $P _ { 1 1 }$ 置换到最右端时 $P _ { 1 1 }$ 与 $P _ { 2 }$ 、 $P _ { 1 2 }$ 、 $P _ { 2 1 }$ 三者置换的总次数，很显然， $j$ 与 $k$ 满足约束条件

$$
\begin{array} { r } { \tau + 2 ( j + k ) = N } \\ { 1 + 2 ( j + k ) = N } \end{array}
$$

值得注意的是，(22)式中的三个表达式并不是彼此完全独立的，当 $\tau = 1$ 时， $U _ { 1 }$ 被 $U _ { 2 }$ 与 $U _ { 3 }$ 共同覆盖。

更具体地，当 $N$ 为偶数时，所有 $( 2 N - 1 )$ 个非零且独立的操作只能表示成(22)式中

$\tau = 0$ 时的更为简洁的 $U _ { 1 0 }$ 与 $U _ { 2 0 }$ ，即

$$
\begin{array}{c} \begin{array} { l } { { U _ { _ { 1 0 } } } } \end{array} = \sigma { P _ { _ { 1 2 } } ^ { _ { \ j } } } { P _ { _ { 1 1 } } ^ { _ { \ k } } }  \\ { { U _ { _ { 2 0 } } } } \end{array}
$$

不可能出现 $U _ { 3 }$ 形式，而 $2 ( j + k ) = N$ ；当 $N$ 为奇数时，要求(22)式中 $\tau = 1$ ，所有形式上独立的非零组合操作可表示为

$$
\begin{array} { r } { { U _ { _ { 2 1 } } } = \sigma { P _ { _ { 1 } } } { P _ { _ { 2 1 } } } ^ { j } { P _ { _ { 1 1 } } } ^ { k } } \\ { { U _ { _ { 3 1 } } } = \sigma { P _ { _ { 2 } } } { P _ { _ { 1 2 } } } ^ { j } { P _ { _ { 1 1 } } } ^ { k } } \end{array}
$$

要求 $2 ( j + k ) = N - 1$ 。当奇数 $N \geq 3$ 时，非零操作总数也为 $( 2 N - 1 )$ ，因此，尽管含$N ( \geq 2 )$ 个基本算符 $P _ { 1 }$ 与 $P _ { 2 }$ 的组合模式有 $2 ^ { N }$ 种，但非零的独立组合操作只有 $( 2 N - 1 )$ 个，如果 $P _ { 1 1 }$ 与 $P _ { 2 }$ ， $P _ { 1 2 }$ 以及 $P _ { 2 1 }$ 等置换最终不带来符号差异，它们的数目会更少，比如，当时空流形的维度 $\boldsymbol { \mathit { \Pi } } _ { n }$ 为奇数时， $P _ { 1 1 }$ 与 $P _ { 2 }$ ， $P _ { 1 2 }$ 以及 $P _ { 2 1 }$ 分别对易，因此，始终有 $( - 1 ) ^ { m ( n - 1 ) } = 1$ ，这时，所有由 $N$ 个基本算符 $P _ { 1 }$ 与 $P _ { 2 }$ 组合的非零独立操作的个数仅为 $( N + 1 )$ 。在(24)与(25)两式中，因为 $\boldsymbol { \mathit { m } }$ 要么为偶数次置换，要么为奇数次置换，因此，不需要关心 $\boldsymbol { \mathit { m } }$ 的具体取值，完全可以由 $\sigma = ( - 1 ) ^ { \tau ( n - 1 ) }$ 替代符号系数 $( - 1 ) ^ { m ( n - 1 ) }$ 。当 $j = 0$ （排除 $U _ { 3 1 }$ 的 $j = 0$ 且（204号 $k \neq 0$ 情形）或 $k = 0$ 时，也就是说，组合操作中不出现 $P _ { 1 1 }$ 或仅存在 ${ P _ { 1 1 } } ^ { k } ( P _ { 1 } { P _ { 1 1 } } ^ { k } )$ 时，$\tau = 0$ ，使得符号系数 $\sigma = 1$ ；其余情形（包含 $U _ { \mathrm { 3 1 } }$ 的 $j = 0$ 且 $k \neq 0$ 情形)，即 $P _ { 1 1 }$ 混合$P _ { 2 }$ ， $P _ { 1 2 }$ 与 $P _ { 2 1 }$ 三者中任意一个时， $\tau = 0$ 与 $\tau = 1$ 操作同时存在。对于 $U _ { 1 0 }$ 、 $U _ { 2 0 }$ 、 $U _ { \mathrm { 2 1 } }$ 与 $U _ { \mathrm { 3 1 } }$ 彼此之间的相互作用关系，下文即将给予探讨。

(22)式表明，完全可由 $P _ { 1 }$ ， $P _ { 2 }$ ， $P _ { 1 1 }$ ， $P _ { 1 2 }$ 与 $P _ { 2 1 }$ 等五个算符表示由 Hodge 对偶与外微分算符构造的任意非零值操作，这样，借助表1给出的算符之间的相互作用关系以及它们作用于 $\mathsf { p }$ -形式场 $A$ 的各具体表达式，可以逐步计算这些操作对微分形式场的作用结果。接下来，讨论三个有关(24)与(25)两式的具体应用例子，其一， $N = 4$ 时，把 $P _ { 1 }$ 与 $P _ { 2 }$ 分别作用于(20)式中由三个基本算符构成的所有5个非零操作，进一步得到由四个 $P _ { 1 }$ 与 $P _ { 2 }$ 组合的7个彼此互异的非零操作，也就是(24)式中 $( j , k )$ 取值为(0,2)、 $( 1 , 1 )$ 与(2,0)时的结果

$$
\begin{array} { r l } { { ( - 1 ) ^ { \tau ^ { ( n - 1 ) } } P _ { 1 2 } P _ { 1 1 } , } } & { { O _ { 1 } , P _ { 1 1 } P _ { 1 1 } , } } \\ { { ( - 1 ) ^ { \tau ^ { ( n - 1 ) } } P _ { 2 1 } P _ { 1 1 } , } } & { { O _ { 2 } } } \end{array}
$$

若时空维度 $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 为奇数， $( - 1 ) ^ { n - 1 } = 1$ ，因此，(26)式中真正独立的量只有5个。其二， $N = 5$ （204号时，再次把 $P _ { 1 }$ 与 $P _ { 2 }$ 分别作用于(26)式中各量，又可得到9个由五个 $P _ { 1 }$ 与 $P _ { 2 }$ 组合的独立非零操作，它们对应于(25)式中 $( j , k )$ 依然取值为(0,2)、 $( 1 , 1 )$ 与(2,0)时的值：

$$
\begin{array} { r l } & { ( - 1 ) ^ { \tau ^ { ( n - 1 ) } } P _ { 2 } P _ { 1 1 } P _ { 1 1 } , P _ { 1 } P _ { 1 1 } P _ { 1 1 } , } \\ & { ( - 1 ) ^ { \tau ^ { ( n - 1 ) } } P _ { 1 } P _ { 2 1 } P _ { 1 1 } , P _ { 1 } O _ { 2 } , } \\ & { ( - 1 ) ^ { \tau ^ { ( n - 1 ) } } P _ { 2 } P _ { 1 2 } P _ { 1 1 } , P _ { 2 } O _ { 1 } } \end{array}
$$

同样，如果时空维度 $\mathfrak { n }$ 为奇数，(27)式中仅包含6个独立组合算符。其三，当(24)式中 $( j , k )$ 分别等于(0,3)、(1,2)、(2,1)与(3,0)时，能够得到由六个基本算符组合的11个独立的非零操作

$$
\begin{array} { r l } { P _ { 1 2 } O _ { 1 } , } & { \sigma P _ { 1 2 } , \sigma O _ { 1 } P _ { 1 1 } , P _ { 1 1 } , } \\ { P _ { 2 1 } O _ { 2 } , } & { \sigma P _ { 2 1 } , \sigma O _ { 2 } P _ { 1 1 } } \end{array}
$$

上式中，已利用单位算符 $P _ { 1 1 } P _ { 1 1 } = 1$ 对部分量进行了化简。

# 2.2算符之间的相互作用关系

基于上一小节的分析，尽管 $N$ 个基本算符的组合总共可以得到 $( 2 N - 1 )$ 个形式上完全独立的操作，事实上，从依赖Hodge 对偶与外微分算符的作用构造有实质不同的微分形式场的角度来看，由于 $P _ { 1 1 }$ 仅有可能改变微分形式的符号，如果不是关注此，真正有实质性区别的组合算符只可能是形如

$$
\begin{array} { r l } & { X _ { 1 } = P _ { 1 2 } ^ { \ j } , X _ { 2 } = P _ { 2 1 } ^ { \ j } } \\ & { \Upsilon _ { 1 } = P _ { 2 } P _ { 1 2 } ^ { \ j } = P _ { 2 1 } ^ { \ j } P _ { 2 } } \\ & { \Upsilon _ { 2 } = P _ { 1 } P _ { 2 1 } ^ { \ j } = P _ { 1 2 } ^ { \ j } P _ { 1 } } \end{array}
$$

等四类。上式中， $X _ { 1 }$ 与 $X _ { _ 2 }$ 适用于 $N$ 为偶数时， $j$ 可取尽区间[0, $N / 2 ]$ 内的所有整数，特别地， $X _ { 1 } ( 0 ) = X _ { 2 } ( 0 ) = 1$ 是单位算符； $Y _ { 1 }$ 与 $Y _ { _ 2 }$ 适用于 $N$ 为奇数时，同样， $j$ 取完区间[ $\mathrm { ~ 0 , \left( \it { N } \mathrm { ~ - ~ } 1 \right) / \mathrm { ~ 2 ] } }$ 中的所有整数。这样， $N$ 个基本算符的组合总共只能得到 $( N + 1 )$ 个有实质区别的组合操作，并且，它们覆盖了所有小于 $N$ 情形的结果。

为了理解(29)式中所有算符的内在联系，我们来分析它们的相互作用关系。任意 $X _ { 1 }$ 与 $X _ { 2 }$ 的自身或彼此之间的相继作用得到

$$
X _ { _ { j } } ( j ) X _ { _ { r } } ( k ) = \delta _ { _ { i r } } X _ { _ { j } } ( j + k )
$$

(30)式中，指标 $\dot { \boldsymbol { \mathit { I } } }$ $; r = 1 , 2$ ；对于 $Y _ { 1 }$ 与 $Y _ { _ 2 }$ 的自身或相互之间的作用，有

$$
Y _ { _ { i } } ( j ) Y _ { _ { r } } ( k ) = ( 1 - \delta _ { _ { i r } } ) X _ { _ { r } } ( j + k + 1 )
$$

由此可见，不同于 $X _ { _ { i } }$ ， $Y _ { 1 }$ 与 $Y _ { _ 2 }$ 二者的相互作用并不是封闭的；所有 $X _ { _ i }$ 与 $Y _ { _ { r } }$ 之间的彼此作用关系为

$$
\begin{array} { r l } { \left[ { Y } _ { _ { r } } ( j ) , { X } _ { _ { i } } ( k ) \right] _ { + } = { Y } _ { _ { r } } ( j + k ) } & { } \\ { \left[ { Y } _ { _ { r } } ( j ) , { X } _ { _ { i } } ( k ) \right] } & { = ( 2 \delta _ { _ { r i } } - 1 ) { Y } _ { _ { r } } ( j + k ) } \end{array}
$$

上式第一个方程为 $X _ { _ { i } }$ 与 $Y _ { _ { r } }$ 二者的反对易关系，由(32)式可知，它们的相继作用结果完全由$Y _ { _ { r } }$ 来确定。需要注意的是，在上述(30)、(31)与(32)三式中，已设定整数 $j , k > 0$ ，因此，它们并没有包括 $j = 0$ 时 $Y _ { 1 } ( 0 ) = P _ { 2 }$ 与 $\mathrm { \mathit { Y } _ { 2 } } ( 0 ) \ : = \ : \mathrm { \mathit { P } _ { 1 } }$ 二者分别与 $X _ { _ { i } } ( k ) , \ Y _ { _ { r } } ( k )$ （这里同样要求 $k > 0$ ）的相互作用关系。为此，通过计算，我们给出 $P _ { _ i }$ 与 $X _ { _ { r } } ( k )$ 彼此之间的如下相互作用关系

$$
\begin{array} { l } { { P _ { _ i } X _ { _ 1 } ( k ) = c _ { _ 4 } Y _ { _ 1 } ( k - \delta _ { _ 1 i } ) } } \\ { { X _ { _ 2 } ( k ) P _ { _ i } = c _ { _ 5 } Y _ { _ 1 } ( k - \delta _ { _ 1 i } ) } } \\ { { P _ { _ i } X _ { _ 2 } ( k ) = X _ { _ 1 } ( k ) P _ { _ i } = \delta _ { _ 1 i } Y _ { _ 2 } ( k ) } } \end{array}
$$

以及 $P _ { _ i }$ 与 $Y _ { _ { r } } ( k )$ 之间的作用关系

$$
\begin{array} { l } { { Y _ { 1 } ( k ) P _ { i } = \delta _ { 1 i } X _ { 2 } ( k + 1 ) } } \\ { { P _ { i } Y _ { 1 } ( k ) = \delta _ { 1 i } X _ { 1 } ( k + 1 ) } } \\ { { P _ { i } Y _ { 2 } ( k ) = c _ { 4 } X _ { 2 } ( k + \delta _ { 2 i } ) } } \\ { { Y _ { 2 } ( k ) P _ { i } = c _ { 5 } X _ { 1 } ( k + \delta _ { 2 i } ) } } \end{array}
$$

在(33)与(34)两式中，因 $P _ { 1 1 }$ 的出现而引入的符号系数 $c _ { 4 }$ 与 $c _ { 5 }$ 只可能取正负1，具体来说，当（204号 $\textit { i } = 1$ 时， $c _ { _ 4 } \ = \ ( - 1 ) ^ { k ( n - 1 ) } c _ { _ 1 }$ ， $c _ { 5 } \ = \ c _ { 1 }$ ；当 $\begin{array} { r } { \dot {  { 1 } } = 2 } \end{array}$ 时， $c _ { 4 , 5 } \ = 1$ 。综合(30)到(34)这五个式子，并考虑到 $P _ { 1 } P _ { 2 } = X _ { 1 } ( 1 )$ ， $P _ { 2 } P _ { 1 } = X _ { 2 } ( 1 )$ 以及单位算符 $X _ { 1 } ( 0 )$ 或 $X _ { 2 } ( 0 )$ 与任意算符作用还是该算符本身，不难发现，在(7)式中给出的 $P _ { 1 1 }$ 与 $P _ { 2 }$ 、 $P _ { 1 2 }$ 、 $P _ { 2 1 }$ 三者交换作用顺序的关系的帮助下，只要把上述算符之间的相继作用关系拓展到(24)与(25)两式中的所有 $U _ { 1 0 }$ 、 $U _ { 2 0 }$ 、$U _ { 2 1 }$ 与 $U _ { 3 1 }$ ，就能够进一步导出这些算符的所有相互作用规律。比如，借助(30)式，能够导出$U _ { i 0 } ( { \boldsymbol { x } } ) = \sigma ( \tau ) X _ { { \scriptscriptstyle i } } ( { \boldsymbol { j } } ) P _ { 1 1 } ^ { \ k }$ 的如下作用关系

$$
U _ { _ { i 0 } } ( x _ { 1 } ) U _ { _ { r 0 } } ( x _ { 2 } ) = ( - 1 ) ^ { k _ { 1 } j _ { 2 } ( n - 1 ) } \delta _ { i r } U _ { _ { i 0 } } ( x _ { 1 } + x _ { 2 } )
$$

这里约定 $( \boldsymbol { \cal X } ) = ( \tau , j , k )$ ， $X _ { _ { j } }$ 指 $X$ 的每个量标注下指标 $\mathbf { \nabla } _ { \boldsymbol { { i } } }$ ， $\left( { { \cal { X } } _ { 1 } } + { { \cal { X } } _ { 2 } } \right)$ 表示对应的两个量分别相加。此外，文献[7,8]中，在设定 $P _ { 1 1 } = 1$ 为单位算符的前提下（此时，(3)与(34)两式中的 $c _ { 4 , 5 }$ 始终等于1)，已验证单位算符1， $P _ { 1 }$ ， $P _ { 2 }$ ， $X _ { _ { i } } ( k )$ 与 $Y _ { _ { r } } ( k )$ （要求 $k > 0$ ）一起构成一个算符代数。

方便起见，借助 $O _ { 1 }$ 与 $O _ { 2 }$ ，进一步把(29)式中所有独立操作表示为如下

$$
\begin{array} { r l } { P _ { 2 } ^ { \tau } { O _ { 1 } } ^ { k } , } & { P _ { 1 2 } O _ { 1 } ^ { k } , P _ { 2 1 2 } O _ { 1 } ^ { k } , } \\ { P _ { 1 } ^ { \tau } { O _ { 2 } } ^ { k } , } & { P _ { 2 1 } O _ { 2 } ^ { k } , P _ { 1 2 1 } O _ { 2 } ^ { k } } \end{array}
$$

等八类。例如，在 $N = 4$ 的情形，(26)式中的有实质区别的组合操作只有 $j = 0 , 1 , 2$ 时的单位算符1, $P _ { 1 2 }$ ， $P _ { 2 1 }$ ， $O _ { 1 }$ 与 $O _ { 2 }$ 五个，前三个正好是 $N = 2$ 时的所有操作（已令 $P _ { 1 1 } = 1$ ）而当 $N = 5$ 时，(27)式中仅包含 $j = 0 , 1 , 2$ 时的 $P _ { 1 }$ ， $P _ { 2 }$ ， $P _ { 2 1 2 }$ ， $P _ { 1 2 1 }$ ， $P _ { 2 } O _ { 1 }$ 与 $P _ { 1 } { \cal O } _ { 2 }$ 六个实质性独立操作，覆盖了 $N = 1 , 3$ 情形的所有可能的结果，没有单位算符，这是因为，奇数个基本算符的组合一定不会存在单位算符。

# 2.3根据生成的次不同的微分形式对操作分类

由上述操作的组合规则可进一步得到结论，当Hodge 对偶与外微分算符作用于 $\mathsf { p } ^ { \mathsf { \_ p } }$ 形式场 $A$ 时，不管操作多少次，最终的结果要么为零，要么为六种t次形式场之一，这里 $\mathfrak { t }$ 只能从集合 $\{ p , q , p \pm 1 , q \pm 1 \}$ 中取值。除此以外，尽管霍奇星算子与外微分算符的所有组合不能再生成更多类型的微分形式，但是，相较于单个基本算符的组合 $P _ { 1 } ^ { j }$ 与 $P _ { 2 } ^ { j }$ 仅能分别生成 $\mathsf { q }$ （或p）与 $( \mathsf { p } { + } 1 )$ 次的微分形式来说，两者的混合组合已很具有影响性了。

具体来说，当组合操作含基本算符的总个数 $N$ 为偶数时，由(24)式可知，只可能生成$( \mathsf { q } + \mathsf { 1 } )$ 、(q-1)与 $\mathsf { p }$ 三种次的微分形式场，对应的操作集合依次为

$$
\begin{array} { r l } & { S _ { q + 1 } = \{ \sigma P _ { 2 1 } { O _ { 2 } } ^ { j } P _ { 1 1 } ^ { \ k } \} } \\ & { S _ { q - 1 } = \{ \sigma P _ { 1 2 } { O _ { 1 } } ^ { j } P _ { 1 1 } ^ { \ k } \} } \\ & { S _ { p } = \{ \sigma O _ { 1 } ^ { \ j } P _ { 1 1 } ^ { \ k } , \sigma O _ { 2 } ^ { \ j } P _ { 1 1 } ^ { \ k } \} } \end{array}
$$

因此，如果要求经由组合算符作用后仍然保持微分形式的次不变，如此的算符只能包含偶数个基本算符 $P _ { 1 }$ 与 $P _ { 2 }$ 。当 $N$ 为奇数时，由(25)式可知，作用于 $\mathsf { p }$ -形式场时，也只可能生成次为 $( \mathsf { p } { + } 1 )$ 、(p-1)与 $\mathsf { q }$ 三种的微分形式，相应的操作集合分别为

$$
\begin{array} { r l } & { S _ { p + 1 } = \{ \sigma P _ { 2 } { O _ { 1 } } ^ { j } P _ { 1 1 } ^ { \ k } \} } \\ & { S _ { p - 1 } = \{ \sigma P _ { 1 2 1 } { O _ { 2 } } ^ { j } P _ { 1 1 } ^ { \ k } \} } \\ & { S _ { q } = \{ \sigma P _ { 1 } { O _ { 2 } } ^ { j } P _ { 1 1 } ^ { \ k } , \sigma P _ { 2 1 2 } { O _ { 1 } } ^ { j } P _ { 1 1 } ^ { \ k } \} } \end{array}
$$

(38)式表明，任意奇数个基本算符 $P _ { 1 }$ 与 $P _ { 2 }$ 的组合不可能得到单位算符。在(37)与(38)两式中，已要求所有的组合操作含基本算符的总数必须为 $N$ 。由于 $P _ { 1 1 }$ 仅有可能改变微分形式场的符号，为了构造有本质差别的各种微分形式，如(36)式所示，完全可以去掉以上集合中的所有（204号 $P _ { 1 1 } ^ { \ k }$ 操作与符号系数 $\sigma$ 。

结束本节之前，为了简单说明(37)与(38)两式的应用，具体来看(26)式中的四个基本算符的组合，它们作用于 $\mathsf { p }$ 次微分形式场时，生成 $\mathsf { p }$ -形式的操作集合是 $\{ { P } _ { 1 1 } ^ { \ 2 } , { O } _ { 1 } , { O } _ { 2 } \}$ ，生成(q-1)与 $( \mathsf { q } + 1 )$ 次形式的操作分别为 $( - 1 ) ^ { \tau ( n - 1 ) } P _ { 1 2 } P _ { 1 1 }$ 与寶 $( - 1 ) ^ { \tau ( n - 1 ) } P _ { 2 1 } P _ { 1 1 }$ 。而对于(27)式中五个基本算符的组合，只可能生成(p-1)、 $( \mathsf { p } { + } 1 )$ 与 $\mathsf { q }$ 次三种微分形式，生成前两种的所有操作集合分别为（204号 $\{ ( - 1 ) ^ { \tau ^ { ( n - 1 ) } } P _ { 1 2 1 } P _ { 1 1 } \}$ 与 $\{ ( - 1 ) ^ { \tau ( n - 1 ) } P _ { 2 } P _ { 1 1 } ^ { \ 2 } , P _ { 2 } O _ { 1 } \}$ ，生成 $\mathsf { q }$ -形式的所有算符依次为 $P _ { 1 } P _ { 1 1 } ^ { \mathrm { ~ 2 ~ } }$ ， $P _ { 1 } { \cal O } _ { 2 }$ 与（204号 $( - 1 ) ^ { \tau ( n - 1 ) } P _ { 2 1 2 } P _ { 1 1 }$ 。这些操作可由表1进一步简化。

# 3 应用举例

本节中，作为上述一般理论的应用，具体考虑四个及以下 $( N \leq 4 )$ 基本算符 $P _ { 1 }$ 与 $P _ { 2 }$ 的所有组合操作分别作用于 $\mathsf { p }$ 形式 $A$ 与(p-1)-形式 $B$ 而如何生成次相同的微分形式场。当组合操作含基本算符的个数不大于四个时，它们作用于 $\mathsf { p }$ -形式场 $A$ ，由 (37)与(38)两式可知，能够生成(q-1)、 $\mathsf { p }$ 与 $( \mathsf { q } + \mathsf { l } )$ -形式的操作只能是基本算符总数 $N { = } 2 , 4$ 的组合操作，分别形成如下三个集合

$$
\begin{array} { l } { { { \cal W } _ { q - 1 } = \{ { \cal P } _ { 1 2 } , { \cal c } _ { 1 } { \cal P } _ { 1 2 } , { \cal c } _ { 2 } { \cal P } _ { 1 2 } \} } } \\ { { { \cal W } _ { p } = \{ { \cal c } _ { 1 } { 1 } , { 1 } , { { \cal O } } _ { 1 } , { { \cal O } } _ { 2 } \} } } \\ { { { { \cal W } _ { q + 1 } = \{ { \cal P } _ { 2 1 } , { \cal c } _ { 1 } { \cal P } _ { 2 1 } , { \cal c } _ { 2 } { \cal P } _ { 2 1 } \} } } } \end{array}
$$

$N { = } 1 , 3$ 的组合算符能够生成(p-1)、 $\mathsf { q }$ 与 $( \mathsf { p } + \mathsf { l } )$ 次形式，它们构成的集合依次为

$$
\begin{array} { r l } & { \psi _ { _ { p - 1 } } = \{ P _ { _ { 1 2 1 } } \} } \\ & { \psi _ { _ { q } } ^ { \phantom { ' } } = \{ P _ { _ { 1 } } , c _ { _ { 1 } } P _ { _ { 1 } } , P _ { _ { 2 1 2 } } \} } \\ & { \psi _ { _ { p + 1 } } ^ { \phantom { ' } } = \{ P _ { _ { 2 } } , c _ { _ { 1 } } P _ { _ { 2 } } , c _ { _ { 2 } } P _ { _ { 2 } } \} } \end{array}
$$

如果忽略所有的符号差异，由上述(39)与(40)两式不难发现， $N \leq 4$ 的所有操作中真正独立的量只有单位算符1, $P _ { 1 2 }$ ， $P _ { 2 1 }$ ， $O _ { 1 }$ ， $O _ { 2 }$ ， $P _ { 1 }$ ， $P _ { 2 }$ ， $P _ { 1 2 1 }$ 与 $P _ { 2 1 2 }$ 等9个，而不是上述更一般情形下的17个。

接下来，在(39)与(40)两式的帮助下，我们来讨论经由各类算符作用于 $\mathsf { p } \cdot$ 形式 $A$ 与(p-1)-形式 $B$ 后得到的所有次相同的微分形式场，有如下四种情况：

(a).同为(p-1)-形式场。作用于 $A$ 与 $B$ 的操作集合分别为 $\boldsymbol { { \cal W } } _ { p - 1 }$ 与 $\mathcal { W } _ { p } ( p  p - 1 )$ ；

(b).同为 $\mathsf { p } \cdot$ -形式场。作用于 $A$ 与 $B$ 的操作集合分别为 $\textstyle { \mathcal { W } } _ { p }$ 与 ${ / W } _ { p + 1 } ( p \to p - 1 )$ ：

(c).同为 $\mathsf { q }$ -形式场。作用于 $A$ 与 $B$ 的操作集合分别为 ${ \it W _ { q } }$ 与 ${ / W } _ { q - 1 } ( p \to p - 1 )$ ：

(d).同为 $( \mathsf { q } { + } 1 )$ -形式场。作用于 $A$ 与 $B$ 的操作集合分别为 $\boldsymbol { { \mathscr { W } } } _ { q + 1 }$ 与 ${ \cal W } _ { q } ( p  p \mathrm { ~ - ~ } 1 )$ 。以上出现的 $( p  p - 1 )$ 表示把集合中含 $c _ { 1 }$ 与 $c _ { 2 }$ 操作的这两个参数中的 $p$ 替换成$( p - 1 )$ ，相应地， $q$ 需要替换成 $( q + 1 )$ 。

当 $p \ = \ 2$ 时，对于2-形式 $A _ { ( 2 ) }$ 以及1-形式 $B _ { ( 1 ) }$ 与 $J _ { ( 1 ) }$ ，经上述算符作用后得到的全部有实质性差异的(n-1)次形式只可能为（已经忽略符号差异) $P _ { 2 1 } A _ { ( 2 ) }$ 、 $P _ { 1 } B _ { ( 1 ) }$ 、 $P _ { 2 1 2 } B _ { ( 1 ) }$ 、 $P _ { 1 } J _ { ( 1 ) }$ 与（204号 $P _ { 2 1 2 } J _ { ( 1 ) }$ 五个。我们考虑取这五个(n-1)次形式中的任意两个的线性组合来构造含 $A _ { ( 2 ) }$ 、 $B _ { ( 1 ) }$ 与$J _ { ( 1 ) }$ 三者中的任意两个的方程。一种可行的处理方式是，先从五个(n-1)次形式中任意选取含$A _ { ( 2 ) }$ 、 $B _ { ( 1 ) }$ 与 $J _ { ( 1 ) }$ 的三个量归为一组，总共有四组：(1). $P _ { 2 1 } A _ { ( 2 ) } \setminus P _ { 2 1 2 } B _ { ( 1 ) }$ 与 $P _ { 1 } J _ { ( 1 ) }$ ； (2). $P _ { 2 1 } A _ { ( 2 ) }$ 、$P _ { 1 } B _ { ( 1 ) }$ 与 $P _ { 2 1 2 } J _ { ( 1 ) }$ ； (3). $P _ { 2 1 } A _ { ( 2 ) }$ 、 $P _ { 1 } B _ { ( 1 ) }$ 与 $P _ { 1 } J _ { ( 1 ) }$ ； (4). $P _ { 2 1 } A _ { ( 2 ) }$ 、 $P _ { 2 1 2 } B _ { ( 1 ) }$ 与 $P _ { 2 1 2 } J _ { ( 1 ) }$ 。然后，由每组的三个量中任选两个进行线性组合来构造方程。显然， (1)与(2)两组完全等价，因为 $B _ { ( 1 ) }$ 与 $J _ { ( 1 ) }$ 互换有不变性；在(3)与(4)两组中，由于 $B _ { ( 1 ) }$ 与 $J _ { ( 1 ) }$ 在形式上的等价性，我们认为完全可以排除 $( P _ { 1 } B _ { ( 1 ) } , P _ { 1 } J _ { ( 1 ) } )$ 与 $( P _ { 2 1 2 } B _ { ( 1 ) } , P _ { 2 1 2 } J _ { ( 1 ) } )$ 这两对平庸组合，并且， $( P _ { 2 1 } A _ { ( 2 ) } , P _ { 1 } B _ { ( 1 ) } )$ 与$( P _ { 2 1 } A _ { ( 2 ) } , P _ { 1 } J _ { ( 1 ) } )$ 两对以及 $( P _ { 2 1 } A _ { ( 2 ) } , P _ { 2 1 2 } B _ { ( 1 ) } )$ 与 $( P _ { 2 1 } A _ { ( 2 ) } , P _ { 2 1 2 } J _ { ( 1 ) } )$ 两对的各自线性组合实质上分别等同，这样，相当于(3)中仅能从 $( P _ { 2 1 } A _ { ( 2 ) } , P _ { 1 } B _ { ( 1 ) } )$ 与 $( P _ { 2 1 } A _ { ( 2 ) } , P _ { 1 } J _ { ( 1 ) } )$ 的组合任取其一，同样,(4)中也只能选取 $( P _ { 2 1 } A _ { ( 2 ) } , P _ { 2 1 2 } B _ { ( 1 ) } )$ 与 $( P _ { 2 1 } A _ { ( 2 ) } , P _ { 2 1 2 } J _ { ( 1 ) } )$ 的组合中的一种，但不管怎样，这些组合均可由(1)或(2)覆盖，故可以不予考虑(3)与(4)。通过(1)中三个量彼此配对得到$( P _ { 2 1 } A _ { ( 2 ) } , P _ { 1 } J _ { ( 1 ) } ) \setminus ( P _ { 2 1 } A _ { ( 2 ) } , P _ { 2 1 2 } B _ { ( 1 ) } )$ 与 $( P _ { 1 } J _ { ( 1 ) } , P _ { 2 1 2 } B _ { ( 1 ) } )$ 三对，由各自的线性组合依次构造如下三个方程

$$
\begin{array} { c } { { d * A _ { ( 2 ) } = \lambda _ { 1 } * J _ { ( 1 ) } } } \\ { { { } } } \\ { { A _ { ( 2 ) } = \lambda _ { 2 } d B _ { ( 1 ) } } } \\ { { { } } } \\ { { d * d B _ { ( 1 ) } = \lambda _ { 3 } * J _ { ( 1 ) } } } \end{array}
$$

上式中， $\lambda _ { _ { 1 } }$ 、 $\lambda _ { _ 2 }$ 与 $\lambda _ { _ 3 }$ 为常量，若 $B _ { ( 1 ) }$ 与 $J _ { ( 1 ) }$ 互换，便是(2)给出的结果。需要注意的是，我们认为(41)式中三个方程是彼此独立的。不妨让1-形式 $B _ { ( 1 ) }$ 与 $J _ { ( 1 ) }$ 分别理解为电磁矢势与流，(41)式中第一个方程正是大家熟知的由微分形式描述的麦克斯韦方程组的两个成员之一；第二个方程可用来定义二阶反对称电磁张量，用微分算符作用一次便得到另一个麦克斯韦方程；第三个方程是电磁场的运动方程。如果需要联立(41)式中的三个方程来自洽地描述电磁场的运动，还需要限制条件 $\lambda _ { _ 2 } = 1$ 与 $\lambda _ { 1 } = \lambda _ { 3 }$ ,这样，确保第二个方程给出了电磁张量 $A _ { ( 2 ) }$ ，而第一与第三个方程完全一致，均为电磁场的运动方程。

此外，除了上述包含 $A _ { ( 2 ) }$ 、 $B _ { ( 1 ) }$ 与 $J _ { ( 1 ) }$ 三者中任意两个混合量的组合外，还有仅包含 $B _ { ( 1 ) }$ 或 $J _ { ( 1 ) }$ 的线性组合，即形式上等价的 $( P _ { 2 1 2 } B _ { ( 1 ) } , P _ { 1 } B _ { ( 1 ) } )$ 与 $( P _ { 2 1 2 } J _ { ( 1 ) } , P _ { 1 } J _ { ( 1 ) } )$ 两对，它们的线性组合可构造 $d * d B _ { _ { ( 1 ) } } = \lambda _ { _ { 4 } } * B _ { _ { ( 1 ) } }$ 与 $d * d J _ { _ { ( 1 ) } } = \lambda _ { _ { 5 } } * J _ { _ { ( 1 ) } }$ 这两个方程，这里 $\lambda _ { _ 4 }$ 与 $\lambda _ { 5 }$ 为常量，应用(15)式中第二个方程，有

$$
\begin{array} { r l } { \lambda _ { 4 } B _ { ( 1 ) } ^ { \mu } } & { = 2 \nabla _ { \nu } \nabla ^ { [ \mu } B _ { ( 1 ) } ^ { \nu ] } } \\ & { \lambda _ { 5 } J _ { ( 1 ) } ^ { \mu } = 2 \nabla _ { \nu } \nabla ^ { [ \mu } J _ { ( 1 ) } ^ { \nu ] } } \end{array}
$$

如果能把 $B _ { ( 1 ) }$ 与 $J _ { ( 1 ) }$ 求解出来，也许可以得到一类特殊的矢量场。综合可得，从纯数学的角度来看，如果通过五个(n-1)次形式 $P _ { 2 1 } A _ { ( 2 ) }$ 、 $P _ { 1 } B _ { ( 1 ) }$ 、 $P _ { 2 1 2 } B _ { ( 1 ) }$ 、 $P _ { 1 } J _ { ( 1 ) }$ 与 $P _ { 2 1 2 } J _ { ( 1 ) }$ 中任选两个进行线性组合来构造方程，考虑到 $B _ { ( 1 ) }$ 与 $J _ { ( 1 ) }$ 在形式上的等价性，当要求方程含 $A _ { ( 2 ) }$ 、 $B _ { ( 1 ) }$ 与 $J _ { ( 1 ) }$ 三者中的任意两个时，能得到(41)式中的三个方程；当只包含三者中的一个时，只能得到(42)式给出的两个方程。若 $B _ { ( 1 ) }$ 与 $J _ { ( 1 ) }$ 互换，(41)式又可给出其余的混合 $A _ { ( 2 ) }$ 、 $B _ { ( 1 ) }$ 与 $J _ { ( 1 ) }$ 任意二者的三个方程，但不管怎样，所有这些方程在形式上都可归入(41)式中的三个方程，由此可知，这三个方程在某种意义上来说是唯一的，而它们的联合能够完整地描述电磁场的麦克斯韦方程。

最后，值得再次强调的是，考虑由微分形式 $P _ { 2 1 2 } B _ { ( 1 ) }$ 与上述剩余的四个量中任选一个进行线性组合构造方程时，真正可能有意义的方程只能是(41)式中的最后两个方程以及(42)式中的第一个方程，如果把 $B _ { ( 1 ) }$ 理解为电磁矢势并要求运动方程包含它的二阶导数项，那么，该运动方程只能是(41)式中第三个方程。同样，当由 $P _ { 2 1 } A _ { ( 2 ) }$ 与其余四个量的任意一个线性组合构造方程时，总共有四对组合，若选取其中两对来构造一个同时含 $A _ { ( 2 ) }$ 、 $B _ { ( 1 ) }$ 与 $J _ { ( 1 ) }$ 三者的方程组，真正有意义的只能是形式上彼此完全等价的这两组，一组由 $( P _ { 2 1 } A _ { ( 2 ) } , P _ { 1 } B _ { ( 1 ) } )$ 与$( P _ { 2 1 } A _ { ( 2 ) } , P _ { 2 1 2 } J _ { ( 1 ) } )$ 两对构成，另一组为 $( P _ { 2 1 } A _ { ( 2 ) } , P _ { 1 } J _ { ( 1 ) } )$ 与 $( P _ { 2 1 } A _ { ( 2 ) } , P _ { 2 1 2 } B _ { ( 1 ) } )$ ，后一组的各自线性组合构造的方程就是(41)式中前两个，它们刚好能同时满足麦克斯韦方程组的要求。

# 4结论

在本文中，我们全面系统地探讨了Hodge 星算子与外微分算符（分别记为基本算符 $P _ { 1 }$ 与

$P _ { \mathrm { 2 } }$ ）作用于任意微分形式场的一般组合规律。首先，找到了两个能够保持微分形式场的次不变的最少组合算符 $O _ { \scriptscriptstyle 1 }$ 与 $O _ { 2 }$ ，它们作用于任意微分形式的结果分别由(11)与(12)两式给出，两者有(14)式中的相互关系，它们的线性叠加又可构造出(13)式中的算符 $\Psi$ ，它可覆盖Laplace-deRham 算子以及平直时空的达朗贝尔算子。其次，考虑了任意 $N$ 个基本算符 $P _ { 1 }$ 与$P _ { 2 }$ 的组合，当 $N$ 为偶数或奇数时，每种情形下的所有 $( 2 N - 1 )$ 个非零且独立的操作总可分别表示成 (24)与(25)两式中由 $P _ { 1 }$ ， $P _ { 2 }$ ， $P _ { 1 1 }$ ， $P _ { 1 2 }$ 与 $P _ { 2 1 }$ 等五个算符（这些算符之间的相互作用关系参见表1）给出的统一形式 $U _ { 1 0 }$ ， $U _ { 2 0 }$ ， $U _ { 2 1 }$ 与 $U _ { \mathrm { 3 1 } }$ ；若忽略符号差异，全部有实质性区别的独立操作只能是(29)式中的 $X _ { _ { 1 } }$ ， $X _ { 2 }$ ， $Y _ { 1 }$ 与 $Y _ { _ 2 }$ ，它们的所有相互作用关系由(30)到(34)这五个式子给出。再次，依照组合算符作用于任意 $\mathsf { p }$ -形式场时对微分形式的次的影响，对它们进行了分类，当基本算符的个数 $N$ 为偶数时，组合操作只可能生成(q-1)、p与 $( \mathsf { q } { + } 1 )$ 三种次的微分形式场，对应于(37)式中的操作集合；当 $N$ 为奇数时，仅能生成次分别为 (p-1)、q与 $( \mathsf { p } { + } 1 )$ 三种的微分形式，相应的操作集合由(38)式给出。最后，作为一个例子，我们详细分析了如何把所有基本算符个数满足 $1 \leq N \leq 4$ 的操作应用到(p-1)-与 $\mathsf { p }$ -形式场来生成次相同的微分形式，特别地，当 $p \ = \ 2$ 时，作用于1与2次形式时生成的所有独立的(n-1)次形式足够用来描述电磁场的麦克斯韦方程组。

# 参考文献：

[1] WaldR M. General Relativity [M]. Chicago: Chicago University Press,1984:88,428.   
[2] Padmanabhan T.Gravitation:Foundations and Frontiers(影印版)[M].北京：北京大学出版社,2013:516-518. [3] Straumann N. General Relativity Second Edition [M]. Springer,2O13:6O3,613,619,622.   
[4] 梁灿彬，周彬.微分几何入门与广义相对论（上册·第二版）[M].北京：科学出版社,2006:77,107,122. [5] 侯伯元，侯伯宇.物理学家用微分几何（第二版）[M].北京：科学出版社,2004:31-35.   
[6]彭俊金，雷良建.由反对称化操作探究Levi-Civita与Kronecker符号的性质[J].中山大学学报（自然科学 版），投稿中.   
[7] Sharma C S.,Egele U. Some properties of the operator algebra generated by Hodge's star and the exterior derivative [J].J.Math.Phys.1981,22:1519-1520.   
[8] Sharma C S.,Egele U.Thecenter of the operator algebra generated by Hodge's star and the exterior derivative [J]. Lett. Nuovo Cim. 1981, 31:412-414.

# Combination Rules of Hodge Star and the Exterior Derivative

Peng Jun-jin

(School of Physics and Electronic Science，Guizhou Normal University，Guiyang，Guizhou 550o01，China)

Abstract: In the present paper, we have systematically explored the general rules for all kinds of combination of Hodge star and exterior differentiation operators.We have derived the unified forms of the non-vanishing and independent operators made up of arbitrary numbers of Hodge star and exterior differentiation operators. On basis of this,we have explicitly investigated the

interaction of all the combined operators.What is more,all the operators have been classified according to the ranks of the newly generated differential forms.As an application, it has been demonstrated that the Maxwell's equations for U(1) gauge field can be constructed from the linear combinations of two (n-1)-forms.

Key words: Hodge star operator; exterior derivative; Maxwell's equations; general relativity; differential geometry