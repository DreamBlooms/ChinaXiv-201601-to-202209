# Lax-Friderichs格式在磁流体模拟中的改进和应用

刘强1,² 李会超2,3

1（洛阳师范学院，物理与电子信息学院，空间物理研究所，洛阳471022)²（中国科学院国家空间科学中心，空间天气学国家重点实验室，北京100190）（中国科学院大学）

摘要：磁流体数值模拟是空间物理研究的重要手段。本文采用具有TVD（TotalVariationDiminishing）特性的Lax-Friderichs 差分格式求解了GLM-MHD（Generalized Lagrange Multiplier-Magnetohydrodynamics）方程。为降低格式的数值耗散，引入耗散修正系数对算法的通量计算过程进行了改进。对二维 Rotor算例和磁云-电流片相互作用算例的模拟结果表明，GLM-MHD 方法可以有效的控制磁场散度误差，相对于泊松校正法可以节省一半以上的计算时间。在不破坏格式稳定性的基础上，耗散修正系数有效降低了算法的数值耗散。

关键词：磁流体力学，差分格式，散度误差，数值耗散中国分类号P353

# Improvement and application of Lax-Friderichs scheme in MHD numerical simulation

Abstract: Magnetohydrodynamics (MHD) numerical simulation is an important tool for space physics research.In this paper, Lax-Friderchs scheme with TVD property is employed to solve GLM-MHD equations. The diffusion turning coefficient is introduced for scheme optimization. Simulation result of 2D rotor test and magnetic cloud current sheet interaction test demonstrates GLM-MHD method's divergence control capability. The simulation consumes less than half of the computational time comparing with simulation utilizing Poisson correction method.While numerical stability is not damaged，numerical diffusion is reduced by the diffusion tuning coefficient.

Keywords: Magnetohydrodynamic, Difference Scheme，Divergence Error， Numerical Dissipation

# 一、引言

日地空间物理学中的许多现象可以用磁流体力学（Magnetohydrodynamic,简称 MHD）模型来描述。由于MHD 方程组的高度非线性，很难求出一般问题的解析解。应用MHD方程组进行理论研究时，一般要借助数值模拟的方法。同时，MHD 数值模拟可以给出空间物理学现象在所有关心的空间位置和时间点上的物理参数，弥补了观测数据在时间与空间上的局限。此外，空间物理学所研究的现象，很难在实验室中重复出来。MHD 数值模拟为空间物理理论研究提供了可控的实验途径。随着数值技术和计算技术的不断发展，MHD 数值模拟在日冕、行星际、磁层以及电离层等大尺度、复杂物理过程研究中得到了越来越广泛的应用。[1]

MHD方程是Navier-Staokes方程、Maxwell方程以及广义欧姆定律的耦合，具有典型的非线性以及非严格的双曲性。MHD 方程的数值模拟方法，大都从流体力学（Hydrodynamic,简称 HD）方程的数值模拟中借鉴而来。然而，MHD 方程的特征系统比 HD 方程的要复杂很多[2]，这就使得数值求解MHD 方程组比求解HD 方程组要困难。早期数值求解MHD 方程的方法主要是以 Lax-Wendroff（LF）格式为代表的有限差分方法。[3]虽然他们的精度可以达到二阶，但他们在间断附近会产生振荡，不能精确的捕捉到激波、接触间断等非线性结构。1983年Harten首次提出了数值格式的总差不增（Total Variation Diminishing，简称 TVD）性质(Harten1983)[4]。具备这种性质的数值格式能够保证数值解的单调性，有效地抑制间断附近的振荡，一般被称为TVD 格式。早期的TVD 格式在极值点上只有一阶精度，通过MUsCL（Monotonic Upstream-Centered Scheme）重构方法，可以使格式的精度达到二阶[5]。通过 PPM（Piecewise Parabolic Method）重构方法，可以使格式的精度达到三阶。[6] ENO/WENO(Weighted Essentially Non-oscillatory)重构方法[7]，能使格式的精度达到四阶乃至更高。然而，由于高阶重构方法在间断附近会自动降低精度以抑制震荡，对于存在大量非线性间断的问题，没有必要使用精度在二阶以上的重构方法。[8] Tanaka 等提出了求解 MHD 方程的一种TVD 格式，并将磁场分裂成本底磁场场 $( B _ { 0 }$ ）和变化磁场 $( B _ { 1 }$ )，以增强格式在地球磁层模拟中的性能。[9]冯学尚、魏奉思以及范全林等采用修正的TVD-Lax-Friedrich 格式，发展了一种快捷具有TVD 特性的组合数值方法[10-13],在三维球坐标以及2.5维直角坐标系下对MHD 进行模拟，解释并证明了大尺度太阳风结构以及磁云边界等问题。

Maxwel方程组要求磁场的散度必须处处为零 $( \boldsymbol { \nabla } \cdot \vec { B } = 0$ )。但在多维的MHD数值模拟中，这个条件的满足需要特别的处理方法。这是MHD 数值模拟比 HD数值模拟更复杂的另一个原因。在保持磁场散度为0的方法中，常用的泊松校正法[13]需要在每一步求解泊松方程，数值计算耗时比较严重。8 波法[14,15]则会破坏 MHD 方程的守恒性。CT（Constrain Transport）一般需要将交错网格来实现，步骤比较繁琐。[6]广义拉格朗日乘子（Generalized Lagrangian Multiplier，简称GLM）方法[16]通过在MHD方程中增加变量 $\psi$ 的方式，构成GLM-MHD方程组，在不破坏方程守恒性的前提下，使磁场散度误差在输运的同时被耗散。标准算例的测试结果表明，这种方法能够有效的控制磁场散度误差，得到精确的数值结果。同时可能在间断附近产生不正确的解。

本文用到修正的TVD-Lax-Friedrich 格式求解了GLM-MHD方程，引入了耗散修正系数（diffusion reduction coefficient）以降低格式的耗散。通过对二维 Rotor问题和行星际磁云边界层问题的模拟，验证了格式的性能。本文第二章介绍了TVD-LF、TVD-TD 格式求解GLM-MHD 方程的具体步骤。第三、四章分析了 Rotor问题和行星际磁云边界层问题的模拟结果。第五章得出结论。

# 二、基本方程和方法

# 1、控制方程

本文求解的是2.5维守恒形式的电阻GLM-MHD方程：

$$
\begin{array} { r } { \frac { \partial U } { \partial t } + \frac { \partial F } { \partial x } + \frac { \partial G } { \partial y } = S _ { 1 } + S _ { 2 } } \end{array}
$$

式中，

$$
U = \left[ \begin{array} { c } { \rho } \\ { \rho u } \\ { \rho v } \\ { \rho w } \\ { B _ { x } } \\ { B _ { y } } \\ { B _ { z } } \\ { T _ { y } } \\ { \psi } \end{array} \right] \hphantom { . }
$$

$$
\begin{array} { r } { F = \left[ { \begin{array} { c } { \rho u } \\ { \rho u ^ { 2 } + p - \frac { B _ { x } ^ { 2 } - B _ { y } ^ { 2 } - B _ { z } ^ { 2 } } { 2 i _ { 0 } } } \\ { \rho u ^ { 2 } + p - \frac { B _ { x } ^ { 2 } - B _ { y } ^ { 2 } } { 2 i _ { 0 } } } \\ { \rho u v - \frac { B _ { x } \rho _ { y } } { \mu _ { 0 } } } \\ { \rho u w - \frac { B _ { x } \rho _ { z } } { \mu _ { 0 } } } \\ { 0 } \\ { 0 } \\ { u B _ { y } - v B _ { x } } \\ { u B _ { z } - w B _ { x } } \\ { T u } \\ { c _ { n } ^ { n } u } \end{array} } \right] ( 3 ) \quad G = \left[ { \begin{array} { c } { \rho v } \\ { \rho u v - \frac { B _ { x } B _ { y } } { \mu _ { 0 } } } \\ { \rho v ^ { 2 } + p - \frac { B _ { x } ^ { 2 } + B _ { y } ^ { 2 } - B _ { z } ^ { 2 } } { 2 i _ { 0 } } } \\ { \rho v ^ { 3 } - \frac { B _ { y } B _ { z } } { \mu _ { 0 } } } \\ { \rho v w - \frac { B _ { y } B _ { z } } { \mu _ { 0 } } } \\ { - u B _ { y } + v B _ { x } } \\ { 0 } \\ { v B _ { z } - w B _ { y } } \\ { T v } \\ { c _ { n } ^ { n } B _ { y } } \end{array} } \right] } \end{array}
$$

$$
S _ { 1 } = \left[ \begin{array} { c } { 0 } \\ { 0 } \\ { 0 } \\ { 0 } \\ { \frac { L ( B _ { x } ) } { \sigma _ { \mu _ { 0 } } } } \\ { \frac { L ( B _ { y } ) } { \sigma _ { \mu _ { 0 } } } } \\ { \frac { L ( B _ { z } ) } { \sigma _ { \mu _ { 0 } } } } \\ { \frac { L ( B _ { z } ) } { \sigma _ { \mu _ { 0 } } } } \\ { \frac { T } { 3 } \left( \frac { \partial \vec { u } } { \partial x } + \frac { \partial \vec { v } } { \partial y } \right) } \end{array} \right] \quad S _ { 2 } = \left[ \begin{array} { c } { 0 } \\ { 0 } \\ { 0 } \\ { 0 } \\ { 0 } \\ { 0 } \\ { 0 } \\ { 0 } \\ { - \frac { c _ { \vec { u } } ^ { 2 } } { c _ { \vec { v } } ^ { 2 } } \psi } \end{array} \right]
$$

其中L（）=+ 为拉普拉斯（Laplacian）算符。方程中的拉格朗日乘子 $\psi$ 是一个标量，它是与磁场散度误差相关的一个量。 $\scriptstyle { c _ { h } }$ 用来散度误差传播速度。若用$c _ { f , x } , c _ { f , y }$ 表示 $\textsf { \textbf { x } }$ 和 $\mathsf { y }$ 方向的快磁声波速度，则可令 $c _ { h } = m a x \big ( | u | + c _ { f , x } , | v | + c _ { f , y } \big )$ ，从而在不对计算时间步长产生附加限制的前提下，以最大的速度将产生的磁场散度误差输运出去。同时，按照文献[16]，将常数 $c _ { p }$ 的取值为 $\begin{array} { r } { c _ { p } = \sqrt { 0 . 1 8 c _ { h } } . } \end{array}$

# 2.GLM-TVD-LF格式

我们将冯学尚等[1O]求解MHD方程的TVDLF格式应用到求解GLM-MHD 方程上。这种格式将一个时间步的求解过程分成预估步和校正步两个步骤。求解的具体过程为

（1）预估步：通过预估步，得到U在两个时间步之间的中间值

$$
\begin{array} { r l r } & { U _ { i , j , k } ^ { n + \frac { 1 } { 2 } } = U _ { i , j , k } ^ { n } - \frac { \Delta t } { 2 \Delta x } \Big [ F \left( U _ { i , j , k } ^ { n } + \frac { 1 } { 2 } \delta U _ { i } ^ { n } \right) - F \left( U _ { i , j , k } ^ { n } - \frac { 1 } { 2 } \delta U _ { i } ^ { n } \right) \Big ] } & { - \frac { \Delta t } { 2 \Delta y } \Big [ G \left( U _ { i , j , k } ^ { n } + \frac { 1 } { 2 } \delta U _ { i } ^ { n } \right) \Big ] } & \\ & { \frac { 1 } { 2 } \delta U _ { j } ^ { n } \Big ) - G \left( U _ { i , j , k } ^ { n } - \frac { 1 } { 2 } \delta U _ { j } ^ { n } \right) \Big ] + \frac { \Delta t } { 2 } S _ { 1 } \left( U _ { i , j , k } ^ { n } \right) } & { ( 6 ) } & \end{array}
$$

(6)式中 $F , ~ G .$ ，的具体形式分别见（3)，（4）式。

$$
\delta U _ { i } ^ { n } = m i n m o d \big ( \Delta U _ { i - 1 / 2 , j , k } ^ { n } , \Delta U _ { i + 1 / 2 , j , k } ^ { n } \big ) , \Delta U _ { i + 1 / 2 , j , k } ^ { n } = U _ { i + 1 , j , k } ^ { n } - U _ { i , j , k } ^ { n }
$$

$\delta U _ { j } ^ { n }$ 的定义与之类似。这里使用minmod 限制器来抑制间断附近震荡的产生：

$$
\begin{array} { l l } { m i n m o d ( { \bf x } , { \bf y } ) = s g n ( x ) M a x ( 0 , m i n [ \vert x \vert , y s g n ( x ) ] ) } \\ { s g n ( x ) = \left\{ \begin{array} { l l } { 1 , } & { x > 0 } \\ { 0 , } & { x = 0 } \\ { - 1 , } & { x < 0 } \end{array} \right. } \end{array}
$$

源项S中的空间导数均由中心差分计算，以 $\frac { \partial \mathbf { u } } { \partial \mathbf { x } } \mathcal { F } \mathbb { I } \frac { \partial ^ { 2 } \mathbf { B } _ { \mathbf { x } } } { \partial x ^ { 2 } } .$ 为例：

$$
\left( \frac { \partial \mathrm { u } } { \partial \mathrm { x } } \right) _ { \mathrm { i , j , k } } = \frac { \mathrm { u _ { i + 1 , j , k } - u _ { i - 1 , j , k } } } { 2 \Delta \mathrm { x } }
$$

$$
\left( \frac { \partial ^ { 2 } \mathrm { B _ { x } } } { \partial \mathrm { x ^ { 2 } } } \right) _ { \mathrm { i , j , k } } = \frac { \mathrm { B _ { x \mathrm { i + 1 , j , k } } } - 2 \mathrm { B _ { x \mathrm { i , j , k } } } + \mathrm { B _ { x \mathrm { i - 1 , j , k } } } } { \Delta \mathrm { x ^ { 2 } } }
$$

在计算（6）式后，参考文献[16]中的方法对 $\psi$ 值再做更新

$$
\begin{array} { r } { \psi _ { i , j , k } ^ { * n + \frac { 1 } { 2 } } = \psi _ { i , j , k } ^ { n + \frac { 1 } { 2 } } e x p \left( - \frac { c _ { h } ^ { 2 } \Delta { \sf t } } { 2 c _ { p } ^ { 2 } } \right) } \end{array}
$$

以体现源项S2的作用，并以ψi,j,² 作为 $\psi$ 在校正步中使用的值。

(2） 校正步

通过校正步，得到物理量在下一个时间步的值 $U _ { i , j , k } ^ { n + 1 }$

$$
\begin{array} { r } { U _ { i , j , k } ^ { n + 1 } = U _ { i , j , k } ^ { n } - \frac { \Delta t } { \Delta x } \bigg ( \hat { F } _ { i + \frac { 1 } { 2 } , j , k } ^ { n + \frac { 1 } { 2 } } - \hat { F } _ { i - \frac { 1 } { 2 } , j , k } ^ { n + \frac { 1 } { 2 } } \bigg ) - \frac { \Delta t } { \Delta y } \bigg ( \hat { G } _ { i , j + \frac { 1 } { 2 } , k } ^ { n + \frac { 1 } { 2 } } - \hat { G } _ { i , j - \frac { 1 } { 2 } , k } ^ { n + \frac { 1 } { 2 } } \bigg ) + } \end{array}
$$

$$
\Delta t S _ { 1 } \big ( U _ { i , j , k } ^ { n + 1 / 2 } \big )
$$

以 $x$ 方向的通量 $\hat { F } _ { i + \frac { 1 } { 2 } , j , k } ^ { n + \frac { 1 } { 2 } }$ 为例介绍校正步中通量的计算方法。定义

$$
\begin{array} { r } { U _ { i + \frac { 1 } { 2 } , j , k } ^ { L } = U _ { i , j , k } ^ { n + 1 / 2 } + \frac { 1 } { 2 } \delta U _ { i } ^ { n } , ~ U _ { i + \frac { 1 } { 2 } , j , k } ^ { R } = U _ { i , j , k } ^ { n + 1 / 2 } - \frac { 1 } { 2 } \delta U _ { i + 1 } ^ { n } } \end{array}
$$

其中， $\delta U _ { i } ^ { n }$ 的值已在预估步中由(7)式算出，这里无需再次计算。在计算 $F _ { i + \frac { 1 } { 2 } , j , k }$ 时，参考[16]的方法，首先解出GLM子系统的黎曼问题，得到：

$$
B _ { x i + \frac { 1 } { 2 } , j , k } = \frac { B _ { x i + \frac { 1 } { 2 } , j , k } ^ { L } + B _ { x i + \frac { 1 } { 2 } , j , k } ^ { L } } { 2 } - \frac { 1 } { 2 c _ { h } } \bigg ( \psi _ { i + \frac { 1 } { 2 } , j , k } ^ { R } - \psi _ { i + \frac { 1 } { 2 } , j , k } ^ { L } \bigg )
$$

$$
\begin{array} { r } { \psi _ { i + \frac { 1 } { 2 } , j , k } = \frac { \psi _ { i + \frac { 1 } { 2 } , j , k } ^ { L } + \psi _ { i + \frac { 1 } { 2 } , j , k } ^ { R } } { 2 } - \frac { c _ { h } } { 2 } \Big ( B _ { x i + \frac { 1 } { 2 } , j , k } ^ { R } - B _ { x i + \frac { 1 } { 2 } , j , k } ^ { L } \Big ) } \end{array}
$$

再令B $B _ { x i + \frac { 1 } { 2 } , j , k } ^ { L } = B _ { x i + \frac { 1 } { 2 } , j , k } ^ { R } = B _ { x i + \frac { 1 } { 2 } , j , k } , \psi _ { i + \frac { 1 } { 2 } , j , k } ^ { L } = \psi _ { i + \frac { 1 } { 2 } , j , k } ^ { R } = \psi _ { i + \frac { 1 } { 2 } , j , k } $ i+j。随后，用Lax-Friedrich方法计算出通量：

$$
\begin{array} { r } { \hat { F } _ { i + \frac { 1 } { 2 } , j , k } ^ { n + \frac { 1 } { 2 } } = \frac { 1 } { 2 } \bigg [ F \left( \mathbf { \it U } _ { i + \frac { 1 } { 2 } , j , k } ^ { L } \right) + F \left( \mathbf { \it U } _ { i + \frac { 1 } { 2 } , j , k } ^ { R } \right) - \frac { 1 } { 2 } | \lambda _ { m a x } | _ { L R } \left( \mathbf { \it U } _ { i + \frac { 1 } { 2 } , j , k } ^ { R } - \mathbf { \it U } _ { i + \frac { 1 } { 2 } , j , k } ^ { L } \right) \bigg ] } \end{array}
$$

定义 $c _ { f , x } ( U )$ 为以 $U$ 中物理量的值计算出的 $\textsf { x }$ 方向的快磁声波波速，则

$$
\lambda _ { m a x } = m a x \left( c _ { f , x } \left( U _ { i + \frac { 1 } { 2 } , j , k } ^ { R } \right) , c _ { f x } \left( U _ { i + \frac { 1 } { 2 } , j , k } ^ { L } \right) \right)
$$

在计算完(9)式后，采用与预估步相似的方法，更新 $\psi$ 的值

$$
\psi _ { i , j , k } ^ { * n + 1 } = \psi _ { i , j , k } ^ { n + 1 } e x p \left( - \frac { c _ { h } ^ { 2 } \Delta { \sf t } } { c _ { p } ^ { 2 } } \right)
$$

3、GLM-TVD-TD（Tunable Dissipation）修正

用Lax-Friedrich方法计算数值通量，虽然稳定性较好，但其将粘性项$| \lambda _ { m a x } | _ { L R } \left( U _ { i + \frac { 1 } { 2 } , j , k } ^ { R } - U _ { i + \frac { 1 } { 2 } , j , k } ^ { L } \right)$ 的系数固定为 $\frac { 1 } { 2 }$ ，数值粘性较大。Diebel、Yalim[17,18]提出引入一个取值范围在(0,1]之间的耗散修正系数 $\varepsilon$ ，用来控制通量的耗散的大小。于是，数值通量(13)可以改写：

$$
\begin{array} { r } { \hat { F } _ { i + \frac { 1 } { 2 } , j , k } ^ { n + \frac { 1 } { 2 } } = \frac { 1 } { 2 } \Big [ F \left( \mathbf { \it U } _ { i + \frac { 1 } { 2 } , j , k } ^ { L } \right) + F \left( \mathbf { \it U } _ { i + \frac { 1 } { 2 } , j , k } ^ { R } \right) - \frac { \varepsilon } { 2 } | \lambda _ { m a x } | _ { L R } \left( \mathbf { \it U } _ { i + \frac { 1 } { 2 } , j , k } ^ { R } - \mathbf { \it U } _ { i + \frac { 1 } { 2 } , j , k } ^ { L } \right) \Big ] } \end{array}
$$

$\varepsilon$ 的值取的越小，数值通量的耗散越低。但 $\varepsilon$ 取的过小时，间断面附件会产生数值振荡，使得计算不能稳定进行。目前，非线性方程数值解法的稳定性还没有严格的判断准则， $\varepsilon$ 难以通过理论推导给出。我们采用Yalim[18]的方法，通过采用不同ε值进行多次数值实验的方式，选取结果中不存在振荡等非物理现象的最小的ε值。这样就可以在追求精确度和保证数值计算稳定性之间寻求到一个最佳平衡点。

# 三、二维Rotor问题数值试验

为了对GLM-TVD-LF 和GLM-TVD-TD 方法进行验证，本文选取Rotor 问题进行数值模拟。1999 年 Balsara and Spicer[19]为了研究强扭转AIfven 波结构和传播提出了二维 Rotor 问题。由于 Rotor问题具有典型的磁场和流场间断面结构，使其成为了验证MHD 模拟方法的重要算例。

本文选取的模拟区域为 $x , y \in \left[ - 0 . 5 , 0 . 5 \right]$ ，采用 $4 0 0 \times 4 0 0$ 的均匀网格。算例的初始条件[16]为：

$$
\left( \rho , v _ { x } , v _ { y } \right) = \left\{ \begin{array} { c c } { \left( 1 0 , - \omega y , \omega x \right) } & { \quad i f r \leq r _ { 0 } } \\ { \left( 1 + 9 f , - \frac { f \omega y r _ { 0 } } { r } , \frac { f \omega x r _ { 0 } } { r } \right) } & { \quad i f r _ { 0 } < r < r _ { 1 } } \\ { \left( 1 , 0 , 0 \right) } & { \quad i f r \geq r _ { 1 } } \end{array} \right.
$$

其中 $^ { \mathrm { ~ i ~ } } \omega = 2 0 , r _ { 0 } = 0 . 1 , r _ { 1 } = 0 . 1 1 5 , r = { \sqrt { x ^ { 2 } + y ^ { 2 } } } , f = ( r _ { 1 } - r ) / ( r _ { 1 } - r _ { 0 } )$ ，磁场$B _ { x } = 5 . 0 / \sqrt { 4 \pi }$ ，热压 $p = 1$ ，绝热系数 $\gamma = 1 . 4$ 。计算在 $t = 0 . 1 5$ 时停止。

图1中自上而下分别为使用[10]中的TVD-LF方法、本文的GLM-TVD-LF方法和 GLM-TVD-TD 方法模拟得到的 Rotor 问题的密度 $\rho$ 等值线和磁场 $B ^ { 2 }$ 等值线图，其中耗散修正系数选取为通过试验得到的最优值 $\varepsilon = 0 . 5$ 。通过对比等值线结果，我们发现三种方法得到的解的结构大致相似，与参考文献中的结果一致。图 2给出了三种方法计算结果中，在 $\boldsymbol { \mathrm { y } } = \boldsymbol { 0 }$ 处密度和总磁场强度随 $\times$ 的变化。从中可以看出，在激波处TVD-GLM-TD格式的耗散最小，这种方法有效的降低了算法的数值粘性。

![](images/11365b7b39a0f370164ace361c981c754ec9e949464a7e43dd0e18047c825a48.jpg)  
图1二维Rotor 问题的密度p和磁场 $B ^ { 2 }$ 在 $\mathrm { t } = 0 . 1 5$ 时刻的等值线。(a)和(b)采用的TVD-LF方法，(c)和(d)采用TVD-GLM修正，(e)和(f)采用TVD-GLM-TD 修正。

Fig.1 Level curves of density $\rho$ and magnetic field magnitude $B ^ { 2 }$ of 2D Rotor question at $\mathrm { t } = 0 . 1 5$

![](images/fa98f2d86d779b272f5695ebb4f00d0df3d1501da9f66b2192b3530d043b3520.jpg)  
图2.二维 Rotor 问题： $\mathrm { t } = 0 . 1 5$ 时刻x方向，使用不同方法计算的密度p和磁场 $| B |$ 对比图。 Fig.2 Comparison diagram of density $\rho$ and magnetic field magnitude $| B |$ by using different methods in X direction at $\mathrm { t } = 0 . 1 5$

# 四、磁云边界问题数值试验

# 1、计算初始条件

磁云是行星际空间中磁场和等离子体的一种大尺度扰动现象。其特征是较低的等离子体密度和温度、较低的等离子体β和磁场方向的旋转。对行星际磁云的研究有助于了解CME 爆发时物质质量、磁场和能量的相互关系。Fan[13]通过数值模拟磁云和电流片相互作用过程，验证了Wei[11]对磁云边界层给出的定义。为了用空间物理研究中的实际问题验证改进算法的计算效果，本文对这一问题，用[13]中的TVD-LF 原始方法和新改进的GLM-TVD-LF 和 GLM-TVD-TD 两种方法进行了数值模拟。模拟采用矩形网格，网格间距 $\Delta x = 2 \times \Delta y = 0 . 2$ ，计算区域$L _ { x } \times L _ { y } = 2 0 \times 2 0$ 。令 $\mathbf { \tilde { x } } = - 1 0 . 0 + \mathrm { i } \times \Delta x , \mathbf { y } = - 1 0 . 0 + \mathrm { j } \times \Delta y$ ，初始的背景磁场为Harris型电流片：

$$
\begin{array} { r } { B _ { 0 } = B _ { \infty } t a n h \left( \frac { y - y _ { 0 } } { L } \right) i _ { x } } \end{array}
$$

磁云初始的中心位置 $( x _ { 0 } , y _ { 0 } ) = ( 0 , 3 . 5 )$ ，磁雷诺系数 $R _ { m } = 5 0 0 0$ ，磁云的位形采用Lundquist[20]给出的无力场模型：当 $r \leq r _ { c }$ 时， $B _ { r } = 0 , B _ { \varphi } = C _ { 0 } B _ { \infty } J _ { 1 } ( \alpha r ) , B _ { z } = C _ { 0 } B _ { \infty } J _ { 0 } ( \alpha r ) ;$ 当<r时，($B _ { z } = 0$ 。其中， $\mathrm { \bf ~ r }$ 为计算点距离磁云中心的距离，磁云半径 ${ r _ { c } } = 3 . 0$ ， $r _ { b } = 2 . 0 r _ { c }$ 。

$J _ { 0 }$ 和 $J _ { 1 }$ 是第1类贝塞尔(Bessel)函数， $\alpha$ 为无力场常数且 $\alpha = - 2 . 4 / r _ { c } , C _ { 0 } = 5 . 7 8 5 0$ 。

# 2、数值模拟结果

首先通过数值试验确定GLM-TVD-TD 修正中可调参数 $\varepsilon$ 的最佳取值。图3为计算进行到 $t = 2$ 时刻，不同耗散修正系数 $\varepsilon$ 模拟结果的磁场强度 $| B |$ 和等离子体温度T的模拟结果在 $\mathbf { x } = 0$ 处随 $\mathsf { \pmb { y } }$ 变化的曲线。计算结果表明当 $\varepsilon < 0 . 5$ 时，如 $\varepsilon = 0 . 3$ 时，得到的曲线在间断面和极值附近有细微的振荡出现，而 $\varepsilon = 0 . 5$ 对应的结果过渡区较窄，在计算稳定的同时具有较低的数值粘性。因此在此问题的数值模拟中，选取 $\varepsilon = 0 . 5$ 。

![](images/7e4149a063c9ba711767de707e849b57eedc19dba9ede92e90cdf9f5511d16b8.jpg)  
图3 $t = 2$ 时刻，不同耗散修正系数ε对应磁场 $| B |$ 曲线和等离子体温度 $T$ 曲线。

Fig. 3 Curves of magnetic field magnitude $| B |$ and plasma temperature $\boldsymbol { \mathrm { \Delta T } }$ by using different diffusion reduction coefficient ε at $\mathrm { t } = 0 . 1 5$

图4给出了三种方法的模拟结果在 $t = 2$ 时刻，沿着 $x = 0$ 方向跨越磁云边界层时磁场强度 $| B |$ 、磁场 $\textsf { x }$ 轴夹角 $\Phi _ { B }$ 、等离子温度T、等离子体密度D以及等离子热压和磁压之比的对数 $\log \beta$ 随y的变化曲线。对照发现，三种方法得到的结果图形大致相同。但是相比于[13]中 TVD-LF 方法得到的结果，GLM-TVD-LF 和GLM-TVD-TD 方法的结果中 $\mathrm { y } = - 2 . 5$ 附近的重联点的位置有所变化。我们在应用TVD-LF方法求解8波形式的MHD方程，再次对本问题进行计算后，发现8波法结果中重联点的位置与GLM-TVD-LF及GLM-TVD-TD 的结果更接近。文献[13]使用柏松校正法控制磁场散度，并用一种伪时间步方法求解柏松方程。我们的数值试验表明这种求解柏松方程的方法并不能完全收敛。这可能是造成重联点位置变化的原因。同时，在磁云中心，GLM-TVD-LF 和 GLM-TVD-TD 格式的磁场方向的变化区更窄，说明这两种方法的数值耗散较低。

![](images/6dccd5af79056a8801602f72b7f79f46d70fb5fccc963d166e2ff708ece2cbc2.jpg)

图 $4 { \textrm { T } } = 2$ 时刻，沿着 $\mathbf { x } = 0$ 使用不同方法模拟磁场强度 $| B |$ 、磁场和x轴夹角 $\Phi _ { B }$ 、等离子温度T、等离子体密度D以及等离子热压和磁压之比的对数logβ随y的变化曲线。图中实线使用的是求解GLM-MHD 的TVD-TD 方法，点划线使用的是求解GLM-MHD 的TVD 方法，虚线使用的是[13]中的原始数值方法。

Fig. 4 Variety curves of magnetic field magnitude $| B | ,$ ,the angle between the filed vector B and the $\mathsf { x }$ -axis $\Phi _ { B }$ ，plasma temperature T，plasma density D and the ratio $\beta$ of the magnetic pressure and plasma pressure.

为了定量观察磁场散度 $\nabla \cdot { \vec { B } }$ 的大小和变化情况，本文计算了平均磁场散度误差[21]:

$$
\begin{array} { r } { e r r o r = \frac { \sum _ { k = 1 } ^ { M } \left| \left( \nabla \cdot \vec { B } \right) _ { k } \right| } { M } } \end{array}
$$

式中 $M$ 为总的网格数。

图5给出用TVD-LF、TVD-GLM和TVD-GLM-TD方法对磁云激波相互作用问题进行模拟时，计算结果的平均磁场散度误差随时间变化曲线。从图中可知，三种方法中，TVD-LF方法使用泊松校正法，对磁场散度误差的抑制最为有效，其次是TVD-GLM方法。随着计算的进行，三种方法得到的平均磁场散度误差均逐渐减小。应用GLM方法控制磁场散度误差时，虽然磁场散度误差绝对值比泊松校正法要大，但前文展示的计算结果表明磁场散度误差对计算结果无明显影响。这说明在本算例中，GLM方法能够有效的控制磁场散度误差。

![](images/c688b7f92b37181aae157eadb230360aa4c86d7481cff879c8d656155a816668.jpg)  
图5error 随时间变化曲线  
Fig.5The variety curves of error over time

本算例的数值程序使用IntelFortran 编译器，以-O2优化选项编译，在配备Intel Xeon E7450 CPU(2.4GHz主频)的计算机上运行。运行到物理时间 $\scriptstyle { \mathrm { t } } = 2$ 时刻，文献[13]的 TVD-LF 格式耗费的计算时间为 307 秒，而本文的 GLM-TVD-LF 和GLM-TVD-TD 方法中耗费的计算时间为123 秒。文献[13]的TVD-LF在用柏松校正法控制磁场散度时，需要用迭代的方法求解柏松方程，需要额外耗费较多时间。这可能是其计算耗时较长的原因。

# 五、结论

本文对2.5维笛卡尔坐标系下的MHD方程组采用TVD格式差分，分别对耗散项和磁场散度约束条件进行修正，发展出两种快捷具有TVD 特性的组合数值模拟新方法。有别于其它的TVD 格式，TD修正稳定有效，可对耗散项进行人为优化，TVD-GLM 方法则简单易行，相同条件下模拟计算耗时减少一半。在二维

Rotor问题中所得结果与相关文献吻合，能够准确模拟复杂螺旋阿尔芬波结构。在磁云和电流片相互作用过程的数值模拟试验中，两种修正方法得到的结果具有更高的精确度和分辨率，与观测数据相符。为今后将其推广到更为复杂的高维数值模拟计算奠定了坚实的基础。

# 参考文献:

[1] Buchner J, Dum CT,et al. Space Plasma Simulation [M]. Berlin: Springer, 2003.

[2] Roe P L, Balsara D S. Notes on the eigensystem of magnetohydrodynamics [J]. Siam J. Appl.   
Math., 1996,56(1): 57-67.

[3] Han S M,Wu S T,et al. A three-dimensional, time-dependent numerical modeling of super-sonic,super-alfvénic MHD flow[J]. Computers & Fluids.1988,16(1): 81.

[4] Harten, Ami. High resolution schemes for hyperbolic conservation laws [J].J. Comput. Phys., 1983,49: 357-393.

[5] Waagan K.A positive MUSCL-Hancock scheme for ideal magnetohydrodynamics [J].Journal of Computational Physics,2009,228(23): 8609-8626.

[6] Gardiner TA, Stone JM.An unsplit Godunov method for ideal MHD via constrained transport in three dimensions [J].Journal of Computational Physics,2005,205(2): 509-539.

[7] Feng Xueshang, Zhou Yufen, Hu Yanqi. A 3rd Order WENO GLM-MHD Scheme for Magnetic Reconnection [J]. Chinese Journal of Space Science,2006,26(1):1-7.In Chinese(冯学尚,周玉 芬,等.A 3rd Order WENO GLM-MHD Scheme for Magnetic Reconnection[J].空间科学学报, 2006, 26(1): 1-7)

[8] Greenough JA，Rider W J.A quantitative comparison of numerical methods for the compressble Euler equations: fifth-order WENO and piecewise-linear Godunov [J]. Journal of Computational Physics,2004,196: 259-281.

[9] Tanaka T. Finite Volume TVD Scheme on an Unstructured Grid System for Three-Dimensional MHD Simulation of Inhomogeneous Systems Including Strong Background Potential Fields [J]. Journal of Computational Physics,1994,111(2):381-389.

[10] Feng Xueshang，Wu S T， Fan Quanlin,Wei Fengsi. Scheme for MHD equations and itsapplication to MHD numerical simulation [J]. Chinese Journal of Space Science，2002，22(4):300-308.In Chinese(冯学尚,Wu ST，范全林，魏奉思，姚久胜．一类TVD 型组合差分方法及其在磁流体数值计算中的应用[J].空间科学学报,2002,22(4):300-308)

[11] Wei Fengsi,Liu Rui，Fan Quanlin, Feng Xueshang. Characteristics of the boundary layer of magnetic clouds and a new definition of the cloud boundary [J]. Science in China Series E: Technological Sciences, 2003, 46(1): 19-32.

[12] Feng Xueshang, Xiang Changqing, Zhong Dingkun, Fan Quanlin.The comparison research of Ulysses observation and MHD simulation of 3D solar wind structure [J]. Chinese Science Bulletin, 2005，50(8):820-826 In Chinese（冯学尚，向长青，钟鼎坤，范全林．三维太阳风结构的 Ulysses 观测和 MHD 模拟的比较研究[J]．科学通报,2005,50(8):820-826)

[13] Fan Quanlin,Wei Fengsi, Feng Xueshang. Numerical simulation on a possible formation mechanism of interplanetary magnetic cloud boundaries [J]. Communications in Theoretical Physics,2003,40:247-252.

[14] PowellK G,et al. A Solution-Adaptive Upwind Scheme for Ideal Magneto- hydrodynamics [J].   
J.Comput. Phys., 1999,154: 284-309.

[15] Janhunen P.A Positive Conservative Method for Magnetohydrodynamics Based on HLL and Roe Methods[J].J.Comput. Phys.,2000,160:649-661.

[16]Dedner A, Kemm F,et al. Hyperbolic divergence cleaning for the MHD equations[J].Journal of Computational Physics,2002,175: 645-673.

[17] Yalim M S, Vanden D, Abeele,Lani A, Quintino T, Deconinck H.A finite volume implicit time integration method for solving the equations of ideal magneto- hydrodynamics for the hyperbolic divergence cleaning approach[J].Journal of Computational Physics,2011,230: 6136-6154.

[18] Diebel J. Numerical Simulation of sub- and supersonic flows in inductively coupled plasma tunnels [R]. Technical Report O9, von Karman Institute for Fluid Dynamics,2003.

[19] Balsara D S,Spicer D S.A Staggered Mesh Algorithm Using High Order Godunov Fluxes to Ensure Solenoidal Magnetic Fields in Magnetohydrody-namic Simulations [J]. J. Comput. Phys., 1999,149: 270-292.

[20] Hidalgo M A, Cid C, Medina J, Vinas A F. A new model for the topology of magnetic clouds in the solar wind [J]. Solar Phys., 2000,194: 165-174.

[21] Feng Xueshang, Zhou Yufen,Wu S T. A Novel Numerical Implementation for Solar Wind Modeling By The Modified Conservation Element/Solution Element Method [J].The Astrophysical Journal, 2007,655:1110-1126.