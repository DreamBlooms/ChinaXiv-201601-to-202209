# 形式一致的高阶修正Komar质量与角动量定义式

刘惠发1 彭俊金1,2\*

1贵州师范大学物理与电子科学学院，贵州 贵阳 550001

2贵州师范大学，贵州省射电天文数据处理重点实验室，贵州 贵阳 550001摘要：Komar积分公式可以方便地用于定义渐近平直时空的质量与角动量。但是，二者的表达式在形式上不一致，彼此之间存在一个差异因子。为了消除这种不一致性，采用把保持微分形式次不变的微分算子作用于1-形式矢量场来生成守恒流的方法，得到了含Kiling矢量非线性三阶导数项的修正Komar势。基于该势的守恒荷定义实现了渐近平直时空的质量与角动量在形式上的一致性。

关键词：Komar积分；引力场的守恒荷；Kerr黑洞；Myers-Perry黑洞

# 1引言

自爱因斯坦的广义相对论诞生以来，寻求引力场的能量、动量和角动量等守恒荷的恰当定义，一直是理论物理与基础数学相关研究领域中的重要疑难问题。至今为止，在广义相对论框架内，已存在多种定义渐近平直时空的质量与角动量等守恒荷的方法，其中包括著名的Moller定义，Landau-Lifshitz定义，Penrose准局域守恒荷方法，Arnowitt-Deser-Misner(ADM)公式以及Komar积分公式等，对这些方法的介绍以及优缺点分析，参考文献[1,2]以及文中所引文献。在本文中，我们将关注由Komar 积分公式3给出的质量和角动量定义。该定义的核心涉及到学者Komar在1959 年从爱因斯坦引力场方程出发构造的2-形式 $K = \mathrm { d } \xi$ (文献中常称之为Komar势，也可基于诺特定理由Einstein-Hilbert作用量变分导出)，这里 $\xi$ 为表征时空对称性的Killing矢量场。在余维-2的光滑曲面 $\partial \Sigma$ 上对势 $K$ 进行积分，就可得到 $D ( D \geq 4 )$ 维渐近平直时空的Komar守恒量定义 $Q _ { K } ( \xi )$ ，即

$$
Q _ { K } ( \xi ) = \frac { 1 } { 8 \pi } \int _ { \partial \Sigma } \star K
$$

上式中，曲面8∑是类时坐标为常量的超曲面Σ的边界，算符 $\star$ 表示霍奇对偶算子。

Komar积分不仅形式简单，而且计算过程极易操作，因此，它可以非常方便地用于计算渐近平直时空的守恒荷，如真空爱因斯坦引力理论中的转动Kerr黑洞[4]及其在 $D$ 维时空中的一般性推广Myers-Perry黑洞[5]的质量与角动量。但是，已有相关研究工作表明（在下一节中即将看到）[6,7,8,9,10,11]，当把(1)式中的Komar积分用来定义这些渐近平直转动黑洞的守恒荷时，为了得到有物理意义的满足热力学第一定律的质量与角动量，不能仅是简单替换与之分别对应的Killing矢量，二者相关的表达式也应做改变，若 $M _ { K }$ 与 $J _ { K }$ 分别指代质量和角动量，则它们依次记为

$$
M _ { K } = \frac { 1 } { 2 } \frac { D - 2 } { D - 3 } Q _ { K } ( \xi _ { t } ) , \qquad J _ { K } = \frac { 1 } { 2 } Q _ { K } ( \xi _ { s } )
$$

这里以及下文一致约定： $\xi _ { t }$ 指代与质量相对应的类时Killing矢量场，而 $\dot { \zeta } _ { s }$ 表示与角动量相对应的类空轴向Killing矢量场。很显然，(2)式表明，质量与角动量的定义在形式上不统一，前者比后者多出一个因子 $( D - 2 ) / ( D - 3 )$ 。特别地，当时空维度 $D = 4$ 时，计算Kerr黑洞的质量与角动量表达式相差因子2，文献[12]中称之为四维Komar守恒荷定义的异常因子2问题。

根据诺特定理，引力场的守恒荷与时空几何的对称性之间存在一一对应关系，对引力场的质量和角动量而言，与之相关的对称性在本质上没有区别，因此，二者的定义理应在形式上完全一致，而不是如原初的Komar守恒荷定义所示，彼此之间存在差异因子 $( D - 2 ) / ( D - 3 )$ 。为了消除该因子，从而得到形式上统一的Komar质量与角动量定义，在工作[12]中，学者Katz首次讨论了四维Komar守恒荷定义中出现的异常因子2问题，并通过对Einstein-Hilbert作用量加上一个边界项来修正原初的Komar势这一途径解决了该问题。在此基础上，后来发展出了定义爱因斯坦引力理论守恒荷的更一般方法，即所谓的Katz-Bicak-Lynden-Bell(KBL)超势方法[12,13]。基于该方法， $D$ 维Komar质量定义式中出现的异常因子亦不存在。除此以外，已有研究中还给出一些别的方法，例如，经典的ADM定义[14]以及协变相空间方法[15,16,17]等，也可给出引力场质量与角动量二者的统一定义式，尤其后者也是通过引入边界项的贡献来消除质量与角动量表达式的差异性。

在本文中，针对因差异因子 $( D - 2 ) / ( D - 3 )$ 的出现而导致渐近平直转动Myers-Perry 黑洞的Komar质量与角动量定义式不一致这一问题，我们将通过引入Killng矢量场的非线性高阶导数项来修正原初Komar势的方式提供解决该问题的又一可能途径。具体地，基于文献[18,19,20]中构造矢量场的守恒流与势的方法，把刻画时空对称性的Kiling 矢量场与守恒流均视为1-形式，然后让保持微分形式次不变的所有可能的二阶与四阶微分算子作用于Kiling矢量，并对生成的所有1-形式取线性组合构造守恒流。在此基础上，由流与势的散度关系读取势的表达式，进一步确定线性组合系数，最终得到能够在形式上统一定义质量与角动量的高阶修正Komar势。

本文结构安排如下：在第二节中，应用原初的Komar积分公式计算任意维度Myers-Perry黑洞的质量与角动量，得到有物理意义的结果，从而证实Komar守恒荷定义中质量与角动量表达式之间存在一个不同的因子；在第三节中，基于保持微分形式次不变的微分算子对1-形式Killing矢量场的作用，推导Komar流与势的含非线性高阶导数项的修正量，然后给出形式上统一定义渐近平直时空质量与角动量的修正Komar积分公式；第四节对全文进行总结并对结果做一个简单讨论。

# 2任意维Myers-Perry黑洞的Komar质量与角动量

学者Kerr于1963年找到了四维真空爱因斯坦引力场方程的第一个稳态轴对称解[4]，这就是著名的Kerr黑洞解。23年后，学者Myers和Perry实现了Kerr黑洞在任意 $D ( D \geq 4 )$ 维时空的推广[5]，文献中常称之为Myers-Perry 黑洞，它在高维广义相对论与黑洞物理学中有着重要的理论意义。在本节中，我们将应用(2)式中给出的Komar守恒荷公式来计算Myers-Perry黑洞的质量与角动量。

首先，给出 $D$ 维Myers-Perry黑洞线元的具体形式。该黑洞在 $n$ 个彼此正交的二维平面上具有 $\overset { \cdot } { n }$ 个独立的转动，可由 $a _ { i }$ 个独立常参数和 $\mathbf { \Psi } _ { n }$ 个方位角 $\phi _ { i } ( 1 \le i \le n , 0 \le \phi _ { i } \le 2 \pi )$ 来刻画，其中 $n$ 满足 $n = ( D - \varepsilon - 1 ) / 2$ (当 $D$ 为偶数时 $\varepsilon { = } 1$ ，当 $D$ 为奇数时 $\scriptstyle \varepsilon = 0$ )。在坐标系 $\{ t , r , \mu _ { j } , \phi _ { i } \}$ 下(按惯例，本文约定 $t$ 代表类时坐标，其余均表示类空坐标，特别地， $\boldsymbol { r }$ 为径向坐标)，Myers-Perry黑洞的时空线元记为[5,6]

$$
\begin{array} { l } { { d s _ { ( D ) } ^ { 2 } = - d t ^ { 2 } + \left( 1 + \frac { 2 m } { V - 2 m } \right) r ^ { 2 } U d r ^ { 2 } + \displaystyle \sum _ { i = 1 } ^ { n } \mu _ { i } ^ { 2 } ( r ^ { 2 } + a _ { i } ^ { 2 } ) d \phi _ { i } ^ { 2 } } } \\ { { + \displaystyle \sum _ { i = 1 } ^ { n + \varepsilon } ( r ^ { 2 } + a _ { i } ^ { 2 } ) d \mu _ { i } ^ { 2 } + \frac { 2 m } { r ^ { 2 } U V } ( d t - \displaystyle \sum _ { i = 1 } ^ { n } a _ { i } \mu _ { i } ^ { 2 } d \phi _ { i } ) ^ { 2 } } } \end{array}
$$

其中函数 $U$ 和 $V$ 表示为

$$
U = \sum _ { \mathrm { i } = 1 } ^ { \mathrm { n } + \varepsilon } \frac { \mu _ { i } ^ { 2 } } { r ^ { 2 } + { a _ { i } } ^ { 2 } } , \quad \quad V = r ^ { \varepsilon - 2 } \prod _ { i = 1 } ^ { n } ( r ^ { 2 } + a _ { i } ^ { 2 } )
$$

在(3)、 (4)两式中，常参量 $m$ 与黑洞质量关联，所有 $\mu _ { i }$ 坐标之间遵循约束 $\begin{array} { r } { \sum _ { i = 1 } ^ { n + \varepsilon } { \mu _ { i } } ^ { 2 } = 1 } \end{array}$ ，在计算守恒量的过程中，方便起见，变量 $\mu _ { n + \varepsilon }$ 的值可以求解为 $\begin{array} { r } { \left| \mu _ { n + \varepsilon } \right| = \sqrt { 1 - \sum _ { k = 1 } ^ { n + \varepsilon - 1 } { \mu _ { k } } ^ { 2 } } } \end{array}$ ，每个 $\cdot \mu _ { i }$ 的取值范围为 $0 \leq \mu _ { i } \leq 1 ( i = 1 , 2 , \cdot \cdot \cdot , n )$ ，而当 $D$ 为偶数时， $\mu _ { n + 1 }$ 的取值范围是 $- 1 \leq \mu _ { n + 1 } \leq 1$ ，并且 $a _ { n + 1 } = 0 \circ$

接下来，具体计算Myers-Perry黑洞的Komar质量与角动量。由于计算过程中需要用到体元，在此给出度规行列式绝对值的平方根，即

$$
{ \sqrt { - g } } = { \frac { r ^ { 3 } U V \prod _ { j = 1 } ^ { n } \mu _ { j } } { \mu _ { n + \varepsilon } } }
$$

通常情况下，与质量和角动量对应的类时与类空Kiling矢量场分别选取为 $\xi _ { ( t ) } ^ { \mu } = - \delta _ { t } ^ { \mu }$ 和 $\xi _ { ( \varphi _ { i } ) } ^ { \mu } = \delta _ { \varphi _ { i } } ^ { \mu }$ ，基

于Komar势 $K$ 的定义 $K = d \xi$ ，计算其 $( t , r )$ 分量得到

$$
\begin{array} { r l r } & { } & { \sqrt { - g } K ^ { t r } \left( \xi _ { ( t ) } ^ { \mu } \right) = \frac { 2 ( D - 3 ) m \prod _ { j = 1 } ^ { n } \mu _ { j } } { \mu _ { n + \varepsilon } } + O \left( \frac { 1 } { r } \right) , } \\ & { } & { \sqrt { - g } K ^ { t r } \left( \xi _ { ( \phi _ { i } ) } ^ { \mu } \right) = \frac { 2 ( D - 1 ) m a _ { i } \mu _ { i } ^ { 2 } \prod _ { j = 1 } ^ { n } \mu _ { j } } { \mu _ { n + \varepsilon } } + O \left( \frac { 1 } { r } \right) . } \end{array}
$$

在此基础上，如果直接选用(1)式来计算Myers-Perry黑洞的质量和角动量，尽管可以得到有限量，但它们不满足黑洞热力学第一定律，故应当排除。若采用(2)式中的Komar质量与角动量定义，积分后得到的结果依次表示为

$$
M _ { ( D ) } = \frac { V _ { D - 2 } } { 4 \pi } \left( n - \frac { 1 - \varepsilon } { 2 } \right) m ,
$$

$$
J _ { ( D ) } ^ { ( i ) } = \frac { V _ { D - 2 } } { 4 \pi } m a _ { i } .
$$

上式中， $V _ { D - 2 }$ 表示 $( D - 2 )$ 维单位球体的体积，由下式给出

$$
V _ { D - 2 } = \frac { 2 \pi ^ { ( D - 1 ) / 2 } } { \Gamma ( \frac { D - 1 } { 2 } ) }
$$

最后，对(7)式中的结果做一个简单讨论。Myers-Perry黑洞的Komar质量和角动量与其它一些代表性方法，其中包括KBL超势方法[12,13]，ADM定义[14] 以及协变相空间方法[15,16,17]等，给出的结果完全一致[6,7,8,9,10,11,20]。并且，这些守恒量完全满足黑洞热力学第一定律的积分与微分形式(这点已在不少研究工作中得以验证，比如，可以参见文献[6,7]中宇宙学常数为零情形的Kerr-AdS黑洞热力学第一定律)，因此它们具有物理意义。特别地，我们在表1（Tab.1）中给出了4到9维Myers-Perry 黑洞的质量与角动量的详细表达式。但是，需要指出的是，根据诺特定理，原则上来说黑洞的质量与角动量的定义在形式上应该保持一致，而不是上文所述彼此之间存在一个差异因子 $( D - 2 ) / ( D - 3 )$ 。为此，我们将在下一节中分析如何通过修正Komar 势来消除守恒荷定义在形式上的差异性。

表14到9维Myers-Perry黑洞的质量与角动量  
Table 1. Mass and angular momentum for Myers-Perry black holes in dimensions from 4 to 9   

<html><body><table><tr><td>维度(i取值)</td><td>4(1)</td><td>5(1,2)</td><td>6(1,2)</td><td>7(1,2,3)</td><td>8(1,2,3)</td><td>9(1,2,3,4)</td></tr><tr><td>体积VD-2</td><td>4π</td><td>2π2</td><td>π²</td><td></td><td>16</td><td>4 T</td></tr><tr><td>质量</td><td>m</td><td>3 Tm</td><td>πm</td><td>π2m</td><td>π2m 元</td><td>7 3m</td></tr><tr><td>角动量</td><td>mai</td><td>rmai</td><td>2 πmai</td><td>m2mai</td><td>π2mai</td><td>1 1mai</td></tr></table></body></html>

# 3 含非线性高阶项修正的Komar积分

在本节中，针对上一节中涉及到的Myers-Perry黑洞的Komar质量和角动量定义之间存在差异因子这一问题，我们将采用工作[18,19,20]中构造与矢量场相对应的守恒流与势的方法，尝试引入Killing 矢量的高阶导数项来修正传统的Komar 流，从而得到定义渐近平直黑洞的质量和角动量的统一表达式。在推导过程中，需要外导数d、余微分算子 $\hat { \delta }$ 以及达朗贝尔算子□ $\mathsf { I } = \nabla ^ { \rho } \nabla _ { \rho }$ 等三个微分算子，对d、 $\hat { \delta }$ 和□三者性质的了解以及它们对微分形式的作用可以参考工作[18,19]以及其中所引用文献。

在微分形式下，文献[3]中得到的与1-形式Killing矢量 $\boldsymbol { \xi }$ 对应的Komar 流 $J _ { K }$ 可以表示为 $J _ { K } = - \hat { \delta } K$ ，或

$$
{ \cal J } _ { K } = - \hat { \delta } \mathrm { d } \xi
$$

该守恒流可以由诺特定理给出，故也称为诺特流。此外，把保持微分形式次不变的所有三个二阶微分算符δd、 $\mathrm { d } \hat { \delta }$ 和□分别作用于Killing矢量场，然后取三者的线性组合，即

$$
J ^ { ( 2 t h ) } ( \xi ) = c _ { 1 } \hat { \delta } \mathrm { d } \xi + c _ { 2 } \mathrm { d } \hat { \delta } \xi + c _ { 3 } \square \xi
$$

亦可得到Komar流，上式中的 $c _ { 1 }$ 、 $c _ { 2 }$ 和 $c _ { 3 }$ 为常参数。根据Killing 矢量满足的恒等式 $\hat { \delta } \xi = 0$ 和 $\hat { \delta } \mathrm { d } \xi = 2 \big \sqcup \xi$ 容易验证，只要让三个组合系数满足 $2 c _ { 1 } + c _ { 3 } + 2 = 0$ ，(10)式中的守恒流就精确回到(9)式中Komar流。由此可见，除了在诺特定理统领下，还可以由保持微分形式次不变的微分算子作用在1-形式Killing矢量上，然后对所有生成量取线性组合来构造守恒流。

经由分析发现，除了二阶守恒流，如果增加微分算子的个数，我们可以继续构造含Kiling矢量的四阶导数的守恒流。把d、 $\hat { \delta }$ 和□三个微分算子所有可能生成四阶导数的组合作用在Killing矢量上，并取线性组合，我们得到最一般的含四阶导数项的1-形式，即

$$
J ^ { ( 4 t h ) } ( \xi ) = \sum _ { i , j = 1 } ^ { 3 } \lambda _ { i j } P _ { i } P _ { j } \xi + c _ { 4 } \hat { \delta } \Pi \mathrm { d } \xi + c _ { 5 } \mathrm { d } \Pi \hat { \delta } \xi
$$

上式中，二阶微分算符 $( P _ { 1 } , P _ { 2 } , P _ { 3 } ) = ( \hat { \delta } \mathrm { d } , \mathrm { d } \hat { \delta } , \bigsqcup )$ ， $\lambda _ { i j }$ 以及 $c _ { 4 } , \ c _ { 5 }$ 都是组合系数。上式看似复杂，但是，基于Killing矢量的性质以及时空几何度规满足真空爱因斯坦引力场方程 $R _ { \mu \nu } { = } 0$ 这一事实，为了保证(11)式中的1-形式对任意Killing矢量始终守恒，则仅能留下包含 $\widehat { \delta } \square \mathrm { d } \xi$ 的这一项(具体过程可以参考文献[20])。取(10)与(11)两式的和，得到不超过四阶导数项的守恒流

$$
\mathcal { I } = - k _ { 1 } \left( \hat { \delta } \mathrm { d } \xi + k _ { 2 } \hat { \delta } \big \lbrack \mathrm { d } \xi \right)
$$

上式中 $k _ { 1 }$ 和 $k _ { 2 }$ 是对(10)、 (11)两式简化后重新给出的待定系数，显然 $\hat { \delta } \mathcal { I } = 0$ ，即1-形式 $\mathcal { I }$ 恒定守恒。当然，理论上可以继续增加微分算子的个数从而生成任意偶数阶导数的更高阶的守恒流，但是，如工作[20]所示，下文将展示含四阶导数的守恒流能够符合我们的预期，故而不需考虑更高阶导数项。与通常的Komar流比较，(12)式中守恒流额外包含了Killing矢量的四阶导数项，因此，后者可以看作前者的高阶修正。特别地，在工作[20]中已证明，含四阶导数项修正的守恒流 $\mathcal { I }$ 能够统一地定义渐近AdS时空的质量与角动量，而这恰好是原初Komar 流的失败之处。

根据庞加莱引理，一个无散矢量场可以局域地（非唯一地）表示成一个2-形式的余微分。因此，在(12)式中守恒流的基础上，由关系 ${ \mathcal { I } } = - \hat { \delta } { \mathcal { K } }$ ，与守恒流 $\mathcal { I }$ 对应的2-形式势K直接读取为

$$
\mathcal { K } = k _ { 1 } \left( \mathrm { d } \xi + k _ { 2 } \bigsqcup \mathrm { d } \xi \right)
$$

为了便于分析，借助引力场运动方程，上式中高阶导数项表示成

$$
\begin{array} { r } { \boxed { \begin{array} { r l } { \boxed { \mathrm { I d } \xi } = \boxed { \mathrm { I } K } = - 2 R _ { \mu \nu } ^ { \rho \sigma } \nabla _ { \rho } \xi _ { \sigma } \mathrm { d } x ^ { \mu } \wedge \mathrm { d } x ^ { \nu } } \end{array} } } \end{array}
$$

与通常的Komar势 $K = \mathrm { d } \xi$ 比较，(13)式中势多了一个三阶导数项，因此，后者可以看作前者的高阶推广。如果能够把 $\kappa$ 的具体形式确定下来，根据通常的做法，对势在余维-2的曲面上进行积分，就可得到与Killing矢量对应的守恒荷定义。

在本节余下部分，我们将详细分析如何确定(13)式中的两个参量 $k _ { 1 }$ 与 $k _ { 2 }$ ，从而给出统一定义MyersPerry黑洞的质量与角动量的势K。首先，由(14)式观察到，(13)式中高阶导数项比通常的Komar势增加了一个黎曼曲率张量因子，基于渐近平直时空在类空无穷远处黎曼曲率张量为零这一事实，我们发现高阶导数项比Komar势衰减更快，在此情形下，如果仍把 $k _ { 2 }$ 当常量处理，2-形式C中高阶导数项 $k _ { 2 } \bigsqcup K$ 对守恒量的贡献为零，势K实质上等同于通常的Komar势 $K$ ，仅能单独地给出质量或角动量的定义，如此就不符合我们的预期目标，即期望基于势K 的守恒荷定义能够在形式上统一地给出二者。因此，考虑到守恒量与Killing矢量之间的对应关系，可以尝试视 $k _ { 2 }$ 为一个依赖Killing矢量 $\xi$ 的变量， $k _ { 2 }$ 的标量属性可令它进一步表示成 $\xi$ 与自身的内积 $\xi ^ { 2 } = \xi ^ { \rho } \xi _ { \rho }$ 的函数，即 $k _ { 2 } = f ( \xi ^ { 2 } )$ ，其恰当形式可以通过分析势的渐近行为来获得。具体地，基于渐近平直时空的度规张量行列式满足条件 $\sqrt { - g } \sim O ( r ^ { D - 2 } )$ ，由(6)式可知，与守恒荷关联的Komar势的分量 $K ^ { t r } \sim O ( r ^ { 2 - D } )$ ，因此，其二阶导数项□ $K$ 的分量 $( \sqcup K ) ^ { t r } \sim O ( r ^ { - D } )$ 进一步有 $\sqrt { - g } ( \ d [ \ d ] ^ { T } ) ^ { t r } \sim O ( r ^ { - 2 } )$ 。这样，为了保证三阶导数项 $k _ { 2 } \sqrt { - g } \bigcirc K$ 在类空无穷远可积，势必要求 $k _ { 2 } \sim O ( r ^ { l } )$ ，这里需要 $l \leq 2 $ ，对Myers-Perry黑洞而言，分析表明 $\boldsymbol { \xi } ^ { 2 }$ 满足：当Killing矢量 $\xi$ 为与质量对应的类时Killing矢量 $\cdot \xi _ { t }$ 时， $\xi _ { t } ^ { 2 } \sim O ( 1 )$ ，导致 $r  \infty$ 时， $k _ { 2 } \sqrt { - g } ( \bigtriangledown K ) ^ { t r } = 0$ ，即高阶项对质量贡献为零；当 $\xi$ 为与角动量对应的类空Killing矢量 $\xi _ { s }$ 时， $\xi _ { s } ^ { 2 } \sim O ( r ^ { 2 } )$ ，使得 $k _ { 2 } \sqrt { - g } ( \boxed { \ d } K ) ^ { t r } \sim O ( 1 )$ ，从而对角动量产生贡献。鉴于 $\boldsymbol { \xi } ^ { 2 }$ 的特性，可令 $k _ { 2 }$ 具有形式

$$
k _ { 2 } = \lambda \xi ^ { 2 }
$$

这里入为待定常参数。这样，一旦 $k _ { 2 }$ 具有(15)式所示形式，基于势K的守恒荷定义中高阶导数项对角动量但不对质量带来贡献。

接下来，我们确定常量 $k _ { 1 }$ 与 $\lambda$ 的具体取值。它们可以由势 $\kappa$ 在余维-2的曲面8∑上积分而得到的守恒荷定义

$$
Q ( \xi ) = \frac { 1 } { 8 \pi } \int _ { \partial \Sigma } { \star \mathcal { K } }
$$

来确定。上式中，若与高阶导数项□d $\xi$ 相关的积分定义为

$$
Q _ { 3 t h } ( \xi ) = \frac { 1 } { 8 \pi } \int _ { \partial \Sigma } \star \big ( \xi ^ { 2 } \big \lrcorner \mathrm { d } \xi \big )
$$

当 $Q _ { K }$ 与 $Q _ { 3 t h }$ 都可积时，利用(13)式中势 $\kappa$ 的定义，可由二者的线性组合来表示守恒荷 $Q$ ，即

$$
Q ( \xi ) = k _ { 1 } \left[ Q _ { K } ( \xi ) + \lambda Q _ { 3 t h } ( \xi ) \right]
$$

由(2)式中Myers-Perry黑洞的角动量定义可以看出，为了让守恒荷表达式在形式上统一地给出质量和角动量的定义，从而消除彼此之间的因子差异，需要确保

$$
{ \cal Q } ( \xi _ { t } ) = \frac { 1 } { 2 } \frac { D - 2 } { D - 3 } { \cal Q } _ { K } ( \xi _ { t } ) , \qquad { \cal Q } ( \xi _ { s } ) = \frac { 1 } { 2 } { \cal Q } _ { K } ( \xi _ { s } )
$$

联立(18)与(19)两式解出系数 $k _ { 1 }$ 与 $\lambda$ ，得到

$$
k _ { 1 } = \frac 1 2 \frac { D - 2 } { D - 3 } , \qquad \lambda = - \frac 1 { D - 2 } \frac { Q _ { K } ( \xi _ { s } ) } { Q _ { 3 t h } ( \xi _ { s } ) }
$$

到此为止，为了完全确定 $\lambda$ ，仅需基于(3)式中Myers-Perry黑洞的线元确定 $Q _ { K } ( \xi _ { s } )$ 与 $Q _ { 3 t h } ( \xi _ { s } )$ 二者的具体比值。利用(7)式中的结果，前者是角动量的两倍，而计算表明后者取值为

$$
Q _ { 3 t h } ( \xi _ { s } ) = - 4 \frac { D - 3 } { D + 1 } Q _ { K } ( \xi _ { s } )
$$

把(21)式中的结果代入(20)式，得到

$$
\lambda = \frac { D + 1 } { 4 ( D - 2 ) ( D - 3 ) }
$$

最后，把系数 $k _ { 1 }$ 与入的取值代入(13)式，我们得到含非线性项的高阶修正Komar势

$$
\kappa = \frac { D - 2 } { 2 ( D - 3 ) } \mathrm { d } \xi + \frac { D + 1 } { 8 ( D - 3 ) ^ { 2 } } \xi ^ { 2 } \big \sqcup \xi
$$

上式为本文核心结论。把势 $\kappa$ 的表达式代入(16)式中的守恒荷定义，我们再次得到定义渐近平直转动Myers-Perry黑洞的质量 $M _ { K }$ 与角动量 $J _ { K }$ 的表达式，即

$$
\begin{array} { r } { M _ { K } = Q ( \xi _ { t } ) , \qquad J _ { K } = Q ( \xi _ { s } ) } \end{array}
$$

与(2)式中Komar守恒荷公式比较，显然，这里的质量与角动量表达式在形式上完全一致，也就是说，由于Killing矢量的非线性高阶导数项的介入，原存于Komar 积分中的异常因子 $( D - 3 ) / ( D - 2 )$ 已不复存在。这样，基于势K的守恒荷定义式(16)能够一致地给出(7)式中Myers-Perry黑洞的的质量与角动量。不仅如此，由于类光Killing矢量与自身的内积等于零导致非线性高阶项在事件视界上的贡献也为零，含非线性高阶导数项修正的Komar守恒荷公式还可统一地导出Myers-Perry黑洞的热力学第一定律的Smarr公式[21]。

# 结果与讨论

基于Komar守恒荷定义，计算了任意维渐近平直转动Myers-Perry黑洞的质量和角动量。计算表明，为了保证所得结果具有物理意义，定义质量与角动量的表达式之间必须存在一个差异因子 $( D - 2 ) / ( D - 3 ) .$ 。为了消除该因子，借助保持微分形式次不变的微分算子对1-形式Killing 矢量场的作用，推导出了含Kiling矢量场的非线性三阶导数项的修正Komar势，由(23)式给出。在此基础上，对该高阶修正势在余维-2的曲面上积分，得到了形式上完全一致的质量与角动量定义式，如(16)、(24)两式所示。

尽管导出(23)式中高阶修正Komar势K的前提条件是渐近平直时空的度规张量满足真空爱因斯坦引力场方程，但是，对于含物质场的爱因斯坦引力理论，如果物质场在无穷远处衰减足够快，且时空几何渐近平直，势K应该仍然可以给出质量与角动量的统一定义式，例如，可以验证，渐近平直转动带电Kerr-Newman黑洞的质量与角动量也可由基于势K的守恒荷定义统一给出。此外，KBL超势方法与协变相空间方法均是通过引入边界项的贡献来消除Komar质量和角动量表达式之间的差异性，而本文是通过引入非线性高阶导数项来解决这一问题，相较而言，本文的结果在数学结构上更接近于原来的Komar形式，但是，前两种方法都是在诺特定理的引领下采用变分原理来导出守恒流，相关结果的物理和几何基础更为坚实。为此，也可仿照KBL超势方法中的处理方式，在Einstein-Hilbert作用量中引入一个恰当的边界项，该项不影响场的运动方程但对流与势带来贡献，要求所做贡献恰好等于势K 中Kiling 矢量场的非线性高阶导数项。这样，就可基于诺特定理对作用量进行变分来导出本文的修正Komar流与势。

# References

[1] L.B. Szabados, Quasi-Local Energy-Momentum and Angular Momentum in General Relativity[J], Living Rev. Relativity 12, 4 (2009).

[2] D.N. Vollick,On the Meaning of Various Mass Definitions for Asymptotically Flat Spacetimes, arXiv:2101.12570 [gr-qc].

[3] A. Komar, Covariant conservation laws in general relativity[J],Phys. Rev.113, 934 (1959).   
[4] R.P. Kerr, Gravitational field of a spinning mass as an example of algebraically special metrics, Phys. Rev. Lett.11, 237 (1963).   
[5] R.C. Myers and M.J. Perry, Black holes in higher dimensional space-times, Ann. Phys.172, 304 (1986).   
[6] R.C. Myers and M.J. Perry, Black holes in higher dimensional space-times, Class. Quantum Grav. 22, 1503 (2005).   
[7] G.Barnich and G. Compere, Generalized Smarr relation for Kerr AdS black holes from improved surface integrals, Phys. Rev. D 71, 044016 (2005).   
[8] N. Deruelle and J. Katz, On the mass of a Kerr-anti-de Sitter spacetime in D dimensions, Class. Quantum Grav. 22, 421 (2005).   
[9] Y.D. Jing and J.J. Peng, A note on the mass of Kerr-AdS black holes in the of-shell generalized ADT formalism, Chin. Phys.B 26,100401 (2017).   
[10] R. Olea, Regularization of odd-dimensional AdS gravity: Kounterterms, JHEP 0704, 073 (2007).   
[11] S.Deser, I. Kanik and B. Tekin， Conserved charges of higher D Kerr-AdS spacetimes, Class. Quantum Grav. 22, 3383 (2005).   
[12] J. Katz, A note on Komar's anomalous factor, Class. Quantum Grav. 2, 423 (1985).   
[13] J. Katz, J. Bicak and D.Lynden-Bell, Relativistic conservation laws and integral constraints for large cosmological perturbations, Phys. Rev. D 55, 5957 (1997).   
[14] R. Arnowitt, S. Deser and C.W. Misner, The Dynamics of general relativity, Gen. Rel. Grav. 40, 1997 (2008).   
[15] J. Lee and R. M. Wald, Local symmetries and constraints, J. Math. Phys.31, 725 (1990).   
[16] V. Iyer and R.M. Wald, Some properties of the Noether charge and a proposal for dynamical black hole entropy, Phys. Rev. D 50, 846 (1994).   
[17] R.M. Wald and A. Zoupas,A general definition of conserved quantities’ in general relativity and other theories of gravity, Phys. Reu. D 61 084027 (2000).   
[18] J.J. Peng and C.L. Zou, Generalized Komar currents for vector fields, arXiv:1910.00339 [gr-qc].   
[19] J.J.Peng, Constructing p,n-forms from p-forms via the Hodge star operator and the exterior derivative, Commun. Theor. Phys.72, 065402 (2000).   
[20] J.J. Peng, C.L. Zou and H.F. Liu,A Komar-like integral for mass and angular momentum of asymptotically AdS black holes in Einstein gravity, Phys. Scr. 96,125207 (2021).   
[21] L. Smarr, Mass Formula for Kerr Black Holes Phys. Rev. Lett.,30, 71 (1973).

# The unified higher-order corrected Komar formulas for

# mass and angular momentum

Liu Hui-Fa1 Peng Jun-Jin $^ { 1 , 2 }$ （20

（20 $^ { 1 }$ School of Physics and Electronic Science, Guizhou Normal University, Guiyang, Guizhou 55001, China $^ 2$ Guizhou Provincial Key Laboratory of Radio Astronomy and Data Processing, Guizhou Normal University, Guiyang,Guizhou 550001，China

# Abstract

It is of great convenience to apply Komar integral to define mass and angular momentum of asymptotically-fat spacetimes.However,their expressions differ from each other in form due to the existence of a diferent factor.In order to eliminate the difference between them,by utilizing the method in which the conserved current is generated via the action of the degree-preserving differential operators on a 1-form vector field,we modify the conventional Komar potential by including a nonlinearthird-order derivative term of Killing vector.Conserved charges based on the higher-order corrected Komar potential unify the definitions of mass and angular momentum for asymptotically-flat spacetimes.

Keywords: Komar integral,conserved charges for gravitational field,Kerr black hole,Myers-Perry black hole