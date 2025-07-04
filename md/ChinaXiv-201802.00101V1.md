# 激波计算不稳定现象机理研究

李雪松

（清华大学热能工程系·热科学与动力工程教育部重点实验室，北京100084)

摘要：激波计算不稳定问题是激波捕获格式的一个重要缺陷，多年来受到学术界的广泛关注与研究。本文针对 Roe格式，对这一问题进行了机理研究，提出了新的观点，认为造成这一问题的原因在于激波计算格式未能真正考虑流动的多维性，而保留了本应消失的类动量插值机制，即界面修正速度中的压力梯度项。通过这一机理认识，提出了简明的修正方案，改进了Roe 格式。数值算例表明这一改进的Roe 格式可以有效的消除激波不稳定现象。

关键词：Roe格式；激波计算不稳定现象；动量插值机制中图分类号：0354 文献标识码：A

# The Research of the Mechanism of Numerical Shock Instability

Xue-Song Li

(KeyLaboratoryforThermalSienceandPowerEngineeringofMinistryofEducation,DepartmentofThermalEngiering,Tsinghua University, Beijing 100080,China)

Abstract: The numerical shock instability is a famous and important problem for the shock-capturing scheme.For the classcal Roe scheme,the mechanism of this problem is researched by the paper. A new viewpoint is proposed to explain the reason.In detail of the explanation, flow multi-dimensional property is not really reflected by the shock-capturing scheme，and thus a mechanism similar to the momentum interpolation method,the term of pressure gradient in the modified interface velocity,is held although it should disappear. Based on this viewpoint for the mechanism,the improved Roe scheme is proposed by a concise method.The numerical examples show that the improved Roe scheme can cure the shock instability.

Key words: Roe scheme; numerical shock instability; momentum interpolation method

# 0引言

近几十年来，激波捕获格式研究取得了巨大的进展，发展了诸如Roe[1]、HLL[2]、AUSM[3]等著名的系列格式，基本解决了激波能否自动捕获计算的难题，是现代计算流体力学（CFD)辉煌的成就之一。

然而，对于计算激波，以上激波捕获格式仍然存在一些缺陷未能解决，如红斑、马赫杆、奇偶失联等激波不稳定现象[4]。对于这些激波不稳定现象，目前的解决方式主要有三类：

# （1）格式混合方法

研究表明高精度低耗散的激波捕获格式如Roe格式往往受制于激波不稳定现象，而一些较粗糙的高耗散格式如HLL格式则没有这个问题。因此一种思路是将这两类格式通过一个压力梯度探测函数联接起来[4]，即在激波区域使用高耗散格式而在其它区域使用低耗散格式。但这一方法未能触及激波不稳定现象的机理，探测函数的构造也较为困难。

# （2）旋转黎曼求解器

另一种方法将激波计算不稳定现象归咎于黎曼求解器（也就是激波捕获格式）在多维情况下仅仅是一维的简单推广。也就是说，黎曼求解器是一维条件下推导出来的，而在多维条件下，通常的做法是将一维黎曼求解器简单推广，未真正考虑多维特性。因此，旋转黎曼求解器试图改进这一点，通过寻找特征方向反映流动的多维性，如旋转Roe格式[5]，从而可以消除激波不稳定现象。

# （3）压力梯度修正方法

第三种方法认为激波计算不稳定的原因在于格式耗散中的压力梯度项，从而通过压力梯度探测因子进行修正，在压力梯度变化大的地方取消压力梯度项，如激波稳定型Roe 格式[]。实践证明这一做法

也是有效的。

本文提出了一种对激波计算不稳定机理新的解释，并应用这一解释针对Roe格式给出了简洁有效的修正方法。这一解释与方法可以视作结合了以上所述第二类与第三类方法。

# 1主导方程及格式通用形式

以二维Euler方程为例，流体力学主导方程为：

$$
\frac { \partial Q } { \partial t } + \frac { \partial F } { \partial x } + \frac { \partial G } { \partial y } = 0
$$

其中 $\pmb { Q } = \left[ \begin{array} { l } { \rho } \\ { \rho u } \\ { \rho v } \\ { \rho E } \end{array} \right]$ 为守恒变量， $\begin{array} { r } { \boldsymbol { F } = \left[ \begin{array} { l } { \rho u } \\ { \rho u ^ { 2 } + p } \\ { \rho u \nu } \\ { u \big ( \rho E + p \big ) } \end{array} \right] . } \end{array}$ $\mathbf { G } = \left[ \begin{array} { l } { \rho \nu } \\ { \rho u \nu } \\ { \rho \nu ^ { 2 } + p } \\ { \nu \big ( \rho E + p \big ) } \end{array} \right] \mathcal { H } \mathbb { X } \mathbb { Y } \mathbb { Y } \mathbb { Z } \mathbb { \breve { I } } \mathbb { \breve { I } } \mathbb { \breve { Z } }$ 量。

对于大多数数值离散格式，对流数值通量可以用如下通用方式表达：

$$
{ \tilde { F } } = { \tilde { F } } _ { c } + { \tilde { F } } _ { d }
$$

其中 $\tilde { F } _ { c }$ 代表中心差分， $\tilde { F } _ { d }$ 代表数值粘性，即对流数值通量由中心差分与数值耗散构成。由于格式的区别主要在数值粘性项上，本文将只讨论 $\tilde { F } _ { d }$ 。

# 2Roe格式及其展开

本节将基于Roe 格式进行分析。为简便起见且不失一般性，本文的讨论只针对直角正交网格 $i + \frac 1 2$ 交接面。

Roe格式的数值粘性项可以表达为如下形式：

$$
\tilde { F } _ { d , i + \frac { 1 } { 2 } } ^ { R o e } = - \frac { 1 } { 2 } { \cal R } _ { i + \frac { 1 } { 2 } } \bigg | \Lambda _ { i + \frac { 1 } { 2 } } \bigg | { \pmb R } _ { i + \frac { 1 } { 2 } } ^ { - 1 } \big ( { \pmb Q } _ { i + 1 } - { \pmb Q } _ { i } \big )
$$

其中 $\pmb { R }$ 是 $\frac { \partial F } { \partial Q }$ 的右特征矩阵， $\Lambda$ 是相应的特征值对角矩阵，其中特征值是：

$$
\lambda _ { 1 , 2 } = \left| U \right| , \quad \lambda _ { 3 } = \left| U - c \right| , \quad \lambda _ { 4 } = \left| U + c \right|
$$

这里 $\boldsymbol { \mathbf { \mathit { c } } }$ 为音速， $U = n _ { x } u + n _ { y } \nu$ 为界面法向速度，$n _ { x }$ 、 $n _ { y }$ 为界面法向向量在坐标轴上的分量。

根据文献[7]给出的激波捕获格式统一表达方式，三维条件下Roe格式的耗散项可以展开为如下形式：

$$
\tilde { F } _ { d , i + \frac { 1 } { 2 } } ^ { R e e } = - \frac { 1 } { 2 } \left\{ \left[ \begin{array} { l } { \Delta \rho } \\ { \Delta \left( \rho u \right) } \\ { \Delta \left( \rho v \right) } \\ { \Delta \left( \rho w \right) } \\ { \Delta \left( \rho E \right) } \end{array} \right] + \delta p \left[ \begin{array} { l } { 0 } \\ { n _ { x } } \\ { n _ { y } } \\ { n _ { z } } \\ { U } \end{array} \right] + \delta U \left[ \begin{array} { l } { \rho } \\ { \rho u } \\ { \rho v } \\ { \rho w } \\ { \rho H } \end{array} \right] \right\}
$$

方程（5）右端项具有明确的物理意义，第一项为基本的迎风耗散项，第二项为界面修正压力，第三项为界面修正速度。这三项的表达式如下：

$$
\xi = \lambda _ { 1 } = \left| U \right|
$$

$$
\delta p = - \frac { \lambda _ { 4 } - \lambda _ { 5 } } { 2 } c \beta + \biggl [ \lambda _ { 1 } - \frac { \lambda _ { 4 } + \lambda _ { 5 } } { 2 } \biggr ] \ \bigl [ U \Delta \rho - \Delta \bigl ( \rho U \bigr ) \bigr ]
$$

$$
\delta U = \frac { 1 } { \rho } \Bigg ( \frac { \lambda _ { 4 } + \lambda _ { 5 } } { 2 } - \lambda _ { 1 } \Bigg ) \beta + \frac { \lambda _ { 4 } - \lambda _ { 5 } } { 2 \rho c } \Big [ U \Delta \rho - \Delta \big ( \rho U \big ) \Big ]
$$

这里：

$$
\begin{array} { l } { { \displaystyle \beta = \frac { \gamma - 1 } { { c } ^ { 2 } } \Bigg [ \frac { u ^ { 2 } + { \nu } ^ { 2 } } { 2 } \Delta \rho - u \Delta \big ( \rho u \big ) - \nu \Delta \big ( \rho \nu \big ) + \Delta \big ( \rho E \big ) \Bigg ] } } \\ { { \displaystyle = \frac { \Delta p } { { c } ^ { 2 } } } } \end{array}
$$

如文献[8]所述，第三项 $\delta U$ 中压力梯度项的机制类似动量插值，在低马赫数条件下起到抑制压力速度失偶的作用。然而，本文认为，正是这一项导致了多维高马赫数条件下激波计算不稳定现象，将在下节讨论。

# 3激波计算不稳定现象机理分析与改进

如前所述，&U中压力梯度项的机制类似动量插值，在低马赫数计算中是非常必要的，否则将导致压力振荡甚至计算发散。然而，动量插值方法的理论核心，在于界面速度中的压力梯度项采用计算获得，而界面速度中的其它项通过插值获得。也就是说，本该由插值获得的压力梯度项，在动量插值法中是以计算获得的，因此与其它项并不匹配。

对于低马赫数流动，由于流动的非线性不强，因此这一做法并不会带来大的匹配误差，反而能够抑制棋盘型压力的发生。然而，对于高马赫数流动，一方面棋盘型压力本身已不再出现；另一方面，由于流动的强非线性，动量插值法造成的匹配误差已不可忽视。因此，在高马赫数流动计算时，不应该再有动量插值法或其类似的机制。也就是说，当流动马赫数趋近于1或大于等于1时， $\delta U$ 不应该再包含压力梯度项，即应满足以下条件：

$$
\delta U = 0 \mathrm { o r } \delta U = f \big ( \Delta U \big )
$$

下面针对Roe格式分析 $\delta U$ ，即公式（8）可以进一步展开为如下形式：

$$
\delta U = \left( \frac { \lambda _ { 4 } + \lambda _ { 5 } } { 2 } - \lambda _ { 1 } \right) \frac { \Delta p } { \rho c ^ { 2 } } - \frac { \lambda _ { 4 } - \lambda _ { 5 } } { 2 c } \Delta U
$$

可以看到，当 $U \to 0$ 时，公式（11）变为：

$$
\delta U \approx { \frac { \Delta p } { \rho c } } + { \frac { U } { c } } \Delta U = f \left( \Delta p , \Delta U \right)
$$

而当 $U \geq c$ 时，公式（11）变为：

$$
\delta U = \Delta U = f { \big ( } \Delta U { \big ) }
$$

在一维条件下，可以看到，公式（12）中Roe格式为低马赫数流动提供了类动量插值机制；而公式（13）中这一机制消失，因此完全符合公式（11)，不存在激波计算不稳定的问题。然而，在多维条件下，存在这样一种可能性，即：

$U \to 0$ 但 $M \geq 1$

对于这种情况，从马赫数的角度看要求 $\delta U$ 满足公式（10)，但此时 $\delta U$ 实际上是由公式（12）决定的。因此，本文认为造成激波计算不稳定现象的原因，在于由于格式未考虑流动的多维性，而保留了本应消失的类动量插值机制。

从这一观点出发，修正Roe格式的方法也将非常清楚了，即将具有多维含义的马赫数引入 $\delta U$ 中的压力梯度项，例如：

$$
\begin{array} { c } { { \displaystyle \delta U = \frac { 1 } { \rho } \bigg ( \frac { \lambda _ { 4 } + \lambda _ { 5 } } { 2 } - \lambda _ { 1 } \bigg ) \beta \Big [ 1 - f \big ( M \big ) \Big ] } } \\ { { \displaystyle + \frac { \lambda _ { 4 } - \lambda _ { 5 } } { 2 \rho c } \big [ U \Delta \rho - \Delta \big ( \rho U \big ) \big ] } } \end{array}
$$

其中 $f ( M )$ 为马赫数的函数，构造方式可以很多，较好的方式可以参见文献[9]。本文为机理清晰起见，采用最简单的定义方式如下：

$$
f \left( M \right) = \operatorname* { m i n } \left( M , 1 \right)
$$

此时，公式（14）所引发的问题即可获得解决。

对于激波计算不稳定问题，本文所提出的机制解释与修正方法，与引言中所述第二类旋转黎曼求解器方法相比，同样认为是由于流动的多维性引起的，但具体机制与解决方式完全不同；与引言中所述第三类压力梯度修正方法相比，同样认为原因在于压力梯度项，但指出只有具有类动量插值性质的压力梯度项才是问题真正的根源，并且修正函数应基于马赫数。

# 4数值验证

为了验证修正公式（15）的有效性，下面给出经典的三个算例。

# 4.1运动激波不稳定（奇偶失联）算例

该算例中，一个二维管道中，一道激波在以马赫数6的速度向前运动。网格等间距为1并且平行分布，但管道中心网格线奇数点与偶数点坐标分别按平行线坐标上移与下移0.0001.

从图1中可以看到，使用经典Roe格式计算该运动激波，在一定迭代步后从激波中部出现扰动并逐步放大，最终无法保持。而图2表明，使用本文改进后的Roe格式，即采用公式（15）所定义的 $\delta U$ ，可以很好的保持该激波的运动。

![](images/55e57931ee1d7c91022b0a1e2d2ad3ed28b03eb2fb74f2647134bc35872facaa.jpg)  
图1经典Roe 格式计算结果

![](images/0355afd3027525ba943b9fbf4e31dc356e73944d4b8bf701ce73b7f8949e20ab.jpg)  
Fig.1 Results by the classical Roe scheme

![](images/4cbc0fb38c96c9129b4bc428de355c51dd0c933b591c7cc819ea1914ae10e589.jpg)  
图2本文改进Roe 格式计算结果 Fig.2 Results by the improved Roe scheme

# 4.2双马赫数反射问题

一道运动马赫数为10的激波，以 ${ 6 0 } ^ { \circ }$ 角扫过平板，形成复杂的激波系。图3与图4给出了0.2秒时计算所得的密度云图。可以看到，采用经典Roe 格式时，激波系中本应与平板近乎垂直的激波变得倾斜并且出现了非物理的三岔点现象，即马赫杆问题。这也是激波计算不稳定的经典现象之一。而本文改进的Roe格式则较好的避免了这一问题。

![](images/93441a16587728a5102f3992ab0812a79edf01bfb879b2807c87faa30d464898.jpg)

![](images/c2975697ca5e2f76706a34dee200149e8b57affefef4da746996fd6664973351.jpg)  
Fig.3The classical Roe scheme   
图4本文改进Roe 格式Fig.4The improved Roe scheme

4.3高超音钝体绕流问题

![](images/d361d850ef8aba5f9b9d09e02af1f9984ea5c4420db56682ddd62cc208434a0a.jpg)  
图3经典Roe格式  
图5经典Roe格式图6本文改进Roe格式Fig.5 The classical RoeFig.6 The improved Roe马赫数为20的高超音来流绕流通过如图5与图6所示的圆球钝体，并在球体前缘形成了强脱体激波。图5中采用经典Roe格式所获得的结果，在正前方位置的激波出现扭曲现象，即激波计算不稳定

的经典现象之一红斑问题。而图6中采用本文改进Roe格式的结果则校正了这一问题。

# 5结论

本文对激波计算不稳定现象进行了机理分析，提出了新的看法，即认为原因在于由于激波计算格式未真正考虑流动的多维性，而保留了本应消失的类动量插值机制。通过这一认识，提出了简明的修正方案。数值算例表明了这一修正方法的有效性。

# 参考文献

[1]Roe P L.Approximate Riemann solvers: parameter vectors and difference schemes [J]. Journal of Computational Physics,1981,Vol.43(2):357-372.   
[2] Hartern A，Lax P D,and Van Leer B.On upstream differencing and Godunov-type schemes for hyperbolic conservation laws [J]. SIAMReview,1983, Vol.25:35-61.   
[3] Liou M S,and Steffen C J. A new flux splitting scheme [J]. Journal of Computational Physics,1993，Vol. 107(1): 23-39.   
[4]Quirk JJ.A contribution to the great Riemann solver debate [J].International Journal for Numerical Methods in Fluids, 1994, Vol. 18: 555-574.   
[5]REN Yuxin. A robust shock-capturing scheme based on rotated Riemann solvers[J].Computers&Fluids,2oo3,Vol. 32: 1379-1403.   
[6]Kim S,Kim C,Rho O,and Hong S K. Cures for the shock instability: development of a shock-stable Roe scheme [J]. Journal of Computational Physics,2003, Vol. 185: 342-374.   
[7]LI Xuesong.A Uniform Algorithm for All-Speed Shock-Capturing Schemes [C]. The 4th Asian Symposium on Computational Heat Transfer and Fluid Flow, Hong Kong,3-6 June 2013,ASCHT0063-T01-1-P.   
[8]LI Xuesong,GU Chunwei. The momentum interpolation method based on the time-marching algorithm for all-speed flows [J]. Journal of Computational Physics，2010,Vol. 229(20): 7806-7818.   
[9]LI Xuesong, GU Chunwei, XU Jianzhong. Development of Roe-Type Scheme for All-Speed Flows Basedon Preconditioning Method [J]. Computers and Fluids,2009, Vol. 38: 810-817.