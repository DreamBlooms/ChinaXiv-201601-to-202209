编号：164394

# Rijke管热声不稳定非线性动力学研究 -分岔分析

冯建畅，敖文\*，刘佩进（西北工业大学，燃烧、流动和热结构国家级重点实验室，西安710072）

摘要：建立了水平Rijke 管热声模型，利用Galerkin方法对控制方程组进行展开，实现数值求解。确定了Galerkin模态收敛阶数为10，利用非线性动力学理论对系统进行分岔分析。Rijke 管热声系统分岔行为属于亚临界Hopf 分岔。系统稳定性区域分为全局稳定、全局不稳定及双稳态区域。获得了无量纲加热功率 $K$ ，加热器位置 $x _ { f }$ ，阻尼系数 $\scriptstyle { c _ { 1 } }$ 和时间延迟 $\boldsymbol { \tau }$ 等参数的分岔图谱，发现加热器位置 $x _ { f }$ 的分岔图谱存在两个Hopf分岔点。在线性不稳定区域内，振荡幅值随时间延迟 $\boldsymbol { \tau }$ 的增大呈现先增大后减小的趋势。

关键词：热声不稳定；Rijke管；Galerkin方法；分岔分析；非线性动力学中图分类号：V231.12 文献标识码：A

# Ri jke Tube Thermoacoustic lnstability Nonlinear Dynamics Study-Bifurcation Analysis

FENG Jian-ChangAO WenLIUPei-Jin (Science and Technology on Combustion, Internal Flow and Thermal-structure Laboratory, Northwestern Polytechnical University，Xi'an 710072，China)

Abstract:The thermoacoustic model of a horizontal Rijke tube is established.The governing equations are expanded and solved by using the Galerkin method.The convergence order of Galerkin modes is determined as 10.The bifurcation analysis of the system is carred out by using nonlinear dynamics theory. The bifurcation behaviors of the horizontal Rijke tube thermoacoustic system is found to be subcritical Hopf bifurcation. The system stability regions are divided into globally stable region, globally unstable region and bistable region. The bifurcation diagrams of the non-dimensional heater power $( K )$ , the position of the heater $( x _ { f } )$ ，the damping coefficient $( c _ { 1 } )$ and the time delay $( \tau )$ are obtained,and the bifurcation diagram of the position of the heater $\left( x _ { f } \right)$ has two Hopf bifurcation points. In linear unstable region,the amplitude of the oscillation firstly increases and then decreases with the increase of time lag $( \tau )$ ：

Key words: thermoacoustic；Rijke tube；Galerkin method；bifurcation analysis；nonlinear dynamics

# 0引言

燃烧不稳定（combustioninstability）是指燃烧器中压力和速度的大幅度自激振荡，这一振荡带来的循环负荷会造成结构过度振动和燃烧室壁面的热量过度传递等问题，对结构组件造成致命的破坏。长久以来，燃烧不稳定一直都是火箭发动机，燃气轮机，航空发动机和电站锅炉等许多高性能燃烧装置面临的重大挑战。热声不稳定（thermoacousticinstability）是燃烧不稳定的最为主要的一种形式，一般认为，热声不稳定是由于不稳定放热和声场振荡的耦合引起的，将引发接近固有声场频率的大振幅压力振荡，其本质是热源的放热与声场环境存在正反馈机理[1]。

燃烧不稳定现象背后所蕴含的机理十分复杂，包含燃烧，流动和声场的相互耦合作用。火焰面的变化，当量比波动，流体动力学不稳定导致的涡脱落以及燃料的雾化及蒸发过程中的振荡都可能驱动燃烧不稳定。而燃烧室几何结构，燃料/空气混合度，燃料的类型和构成，以及工作环境(注入空气温度，燃烧室压强，当量比，涡流强度，贫油预混等）都将对燃烧不稳定产生影响[2]。

流动和火焰的非线性动力学特性是燃烧不稳定中最为重要的现象之一。燃烧室中的流动和火焰特性随着控制参数的变化会发生剧烈改变，尤其是当参数变化经过分岔点时。燃烧过程本身可能会，抑或不会出现分岔现象，但一旦发生分岔，非线性行为在许多燃烧装置中将占据主导地位[3-4]。系统参数的微小扰动有可能会引起分岔，导致系统由稳态（小振荡或无振荡）转换为不稳定状态（大振幅的极限环)。相反地，在相同的临界参数值时，系统由不稳定状态转变为稳态则不一定会发生，这是由于滞后现象的存在。

燃烧不稳定中出现的分岔，滞后，极限环和触发等现象均可以用动力系统理论来解释和描述，这也是目前研究的一大新兴热点。通过非线性动力学理论，可对非线性系统的特征进行深入的刻画、分析和诊断。现有研究大部分以燃气轮机和火箭发动机出现的热声不稳定问题为背景，研究对象则通常为各种简化的燃烧器或实际的燃气轮机和发动机。其中，Rijke管是研究热声现象最方便最典型的实验系统，也是研究燃烧室火焰区燃烧与声场的相互作用导致的不稳定机理及控制的基础，因此有许多研究是针对Rijke 管来开展的[5-8]。不稳定放热作为热声不稳定的激励，是不稳定发生的一个关键环节。热声系统中的能量输入可以有多种形式，例如燃烧室中放热的化学反应，电热丝，电热薄膜（hotgauze）等[9]。Jahnke 和Culick[10]最早将现代动力系统理论引入燃烧不稳定研究之中，以分析非线性燃烧不稳定。他们提出了一种延拓算法，可对各稳态和极限环的解进行体系化高效计算，由此可得到稳态和极限环下的稳定性，通过分岔分析可以判定不稳定发生点。不稳定发生点处的声波的性质取决于分岔的类型和分岔点处极限环的性质。Ananthkrishnan 等[11]针对燃烧室中的不稳定运动建立了降阶模型，并求解分析了触发和极限环性质。分析表明，对于轴向振荡模态，一阶不稳定需要至少四阶Galerkin级数展开，而二阶不稳定则至少需要八阶级数展开，才能确保计算的准确性。Balasubramanian[l2]研究了非正则性在简单热声系统中的作用和影响，通过推导水平Rijke管的声场控制方程并求解，重点讨论非正则性和非线性效应带来的结果。Subramanian[13]分析了热声系统中亚临界分岔的性质，以及随后导致的双稳定性问题。Waugh等[14-15]研究了热声系统中的触发和流体力学中的向湍流的旁路转捩("逾越型”转捩）的比拟，二者机理均是小扰动导致系统变为大幅度自持振荡，尽管系统是线性稳定的。研究证明了某些类型的噪声更能触发振荡。

现有研究对Rijke管热声不稳定非线性动力学有一定认识，但对系统分岔性质的认识尚不够清晰，对于无量纲加热功率、加热器位置、阻尼系数等系统参数对分岔的影响规律缺乏了解。本文建立了Rijke管热声不稳定的简化模型，得到其一维声场的控制方程，并对其进行了求解，通过对Rijke 管的热声不稳定性进行分岔分析，加深对Rijke 管热声不稳定产生机理和振荡现象的认识。

# 1热声不稳定模型及求解

# 1.1 Rijke 管模型

本文所研究的水平Rijke管模型如图1所示。在该模型中，管长 $L$ 是固定不变的，加热器的位置$x _ { f }$ 的值可以通过改变加热器在管道内的位置来改变，热源为电热丝加热装置，在实验条件下其加热强度可以通过改变通过的电流来改变。

![](images/7297f136c00a3e72b797edd38a4438c1781bcf8a71b057c8f31720be4bfe1b85.jpg)  
图1水平Rijke管的结构示意图，来流平均速度为 $u$ ，管长为 $L$ ，热源与来流开口端距离为 $x _ { f \circ }$

Fig.1 Structure schematic ofahorizontalRijke tube.The mean flow velocity is $u$ ,the length of the duct is $L$ and the distance between the heat source and the incoming flow open end is $x _ { f }$

# 1.2控制方程

忽略平均流量与温度梯度的影响，控制管内声场的动量和能量方程如下[7]：

$$
\bar { \rho } \frac { \partial \bar { \theta } \partial } { \partial \bar { t } / o } + \frac { \partial \bar { p } \partial } { \partial \bar { \theta } _ { o } } = 0
$$

$$
\frac { \partial \beta \rho } { \partial \rho } + \gamma \overline { { p } } \frac { \partial \delta \theta \rho } { \partial \delta \rho } + \varsigma \beta \rho = ( \gamma - 1 ) \mathcal { \dot { Q } } ^ { s } ( t )
$$

为了简化和方便分析，对式（1）和（2）进行无量纲化处理，得到无量纲化的系统控制方程组：

$$
\gamma M _ { a } \frac { \partial u ^ { \prime } } { \partial t } { + } \frac { \partial p ^ { \prime } } { \partial x } { = } 0
$$

$$
\frac {  { \hat { \sigma } } p ^ { \prime } } {  { \hat { \sigma } } t } + \gamma M _ { a } \frac {  { \hat { \sigma } } u ^ { \prime } } {  { \hat { \sigma } } x } + \xi p ^ { \prime } = ( \gamma - 1 )  { \hat { \mathcal { Q } } } ^ { s } ( t ) \delta ( x - x _ { f } )
$$

其中无量纲化的尺度如下：

$$
t = \frac { c _ { 0 } } { L } \dot { t } , \dot { \eta } _ { \mathrm { \uparrow } } ^ { o } x = \frac { \mathcal { K } } { L } ; \boldsymbol { u } ^ { \mathrm { \prime } } = \frac { \mathcal { U } } { \overline { { u } } } ; p ^ { \prime } = \frac { \beta \widetilde { \mathcal { U } } } { \overline { { p } } } ; \rho = \frac { \beta \widetilde { \mathcal { C } } } { \overline { { \rho } } } ; M _ { a } = \frac { \overline { { u } } } { c _ { 0 } }
$$

式（1）-（5）中， $x$ 是沿轴向方向的距离， $t$ 是时间， $\overline { { p } }$ 为管内的平均压强， $u$ 为声波速度， $p$ '为声波压强， $\mathbf { \sigma } _ { \rho }$ 为流体密度， $\gamma$ 是介质的比热比，声速为 $c _ { 0 }$ 而 ${ \mathbf { } } M _ { a }$ 为平均流马赫数。此外， $\xi$ 为阻尼系数， $\mathcal { E } ( t )$ 为单位面积上由于电加热器产生的热释放速率波动， $\delta$ 为标准狄拉克分布， $\cdot \boldsymbol { x } _ { f }$ 为热源位置。符号‘\~’和‘-’分别表示有量纲量和平均量。

阻尼可以用下式表示：

$$
\xi _ { j } = \frac { 1 } { 2 \pi } ( c _ { 1 } \frac { w _ { j } } { w _ { 1 } } + c _ { 2 } \sqrt { \frac { w _ { 1 } } { w _ { j } } } )
$$

参数 $c _ { 1 }$ 和 $c _ { 2 }$ 保持常数不变， $w _ { j } = j \pi$ 为第 $j$ 阶管内声模态的无量纲频率。

热源模型采用Heckl经验公式[16]：

$$
\frac { 2 L _ { w } ( T _ { w } - \overline { { T } } ) } { S \sqrt { 3 } c _ { 0 } \overline { { p } } } \times \sqrt { \pi \lambda C _ { \nu } \overline { { \rho } } \frac { d _ { w } } { 2 } } \times [ \sqrt { \frac { \overline { { u } } } { 3 } + u _ { f } ^ { \prime } ( t - \tau ) } | - \sqrt { \frac { \overline { { u } } } { 3 } } ]
$$

其中， $L _ { \phantom { } _ { w } }$ 和 $d _ { \scriptscriptstyle { w } }$ 代表电热丝的长度和直径， $T _ { \scriptscriptstyle w }$ 为电热丝的温度， $\overline { T }$ 代表周围空气的平均温度， $s$ 为管道截面积， $\lambda$ 代表空气的热传导率， $c _ { \nu }$ 表示恒定体积内单位质量空气的比热容， $\overline { { \rho } }$ 为气体的平均密度。由于热惯性的存在，传热和流动速度之间有一个时间延迟 $\tau$ 。需要注意的是，此热源模型只适用于“紧凑型”热源的描述，即热源厚度相对波长而言可以忽略不计。

将式（7）代入能量方程（4）中，则能量方程可改写为：

$$
\begin{array} { r l } & { \frac { \hat { c } p ^ { \prime } } { \hat { \alpha } t } + \gamma M \frac { \hat { \alpha } u ^ { \prime } } { \hat { \alpha } x } + \xi p ^ { \prime } = \mathcal { S } ( x - x _ { f } ) ( \gamma - 1 ) } \\ & { \times \frac { 2 L _ { w } ( T _ { w } - \bar { T } ) } { S \sqrt { 3 } c _ { 0 } \overline { { p } } } \sqrt { \pi \lambda c _ { \nu } \overline { { \rho } } \frac { d _ { w } } { 2 } \overline { { u } } } \left[ \sqrt { \left| \frac { 1 } { 3 } + u _ { f } ^ { ' } ( t - \tau ) \right| } - \sqrt { \frac { 1 } { 3 } } \right] } \end{array}
$$

# 1.3 Galerkin展开

求解Rijke管装置热声问题的常规方法是使用Galerkin投影和模态扩展。Galerkin方法的原理是任何域中的函数都可以表达成该域内展开函数的叠加。基础函数的选取原则是它们须满足边界条件，且基础函数的选择不是唯一的。在这样的方法中，从满足边界条件的空间基函数来看，空间和时间上变化的压力和速度信号被扩展，这些基函数的选择不是唯一的。本文选择的基础函数是任意的，并非系统的特征函数，而是线性化后的系统自共轭（self-adjoint）部分的特征函数。因此，速度场和压力场可以表示成管道固有模态的形式：

$$
u ^ { \prime } { = } \sum _ { j { = 1 } } ^ { N } U _ { j } \cos ( k _ { j } x )
$$

$$
p ^ { \prime } = \gamma M \sum _ { j = 1 } ^ { N } P _ { j } \sin ( k _ { j } x )
$$

其中， $k _ { j } = j \pi$ 为第 $j$ 个管道模态的无量纲波长。在极限 $N \to \infty$ 条件下，这些基函数形成一个完整的

基础系，显然，本文选取的展开函数满足边界条件。

将式（9）和（10）替换到式（3）和（8）中，并投影（projectingalong）到基础函数系，得到：

$$
{ \mathcal { V } } _ { j } ^ { { \& } } + k _ { j } P _ { j } = 0
$$

$$
\begin{array} { l } { { \displaystyle { \cal P } _ { j } ^ { \mathrm { \tiny \mathrm { 8 } } } + 2 \xi _ { j } \omega _ { j } { \cal P } _ { j } - k _ { j } U _ { j } } } \\ { { \displaystyle = K \left[ \sqrt { \left\| \frac { 1 } { 3 } + \sum _ { i = 1 } ^ { N } \cos ( k _ { i } x _ { f } ) U _ { i } ( t - \tau ) \right| } - \sqrt { \frac { 1 } { 3 } } \right] \sin ( k _ { j } x _ { f } ) } } \end{array}
$$

其中，无量纲加热功率为：

$$
K = \frac { 4 ( \gamma - 1 ) L _ { w } } { \gamma M a S c _ { 0 } \overline { { { p } } } \sqrt { 3 } } ( T _ { w } - \bar { T } ) \sqrt { \pi \lambda c _ { \nu } \overline { { { \rho } } } \frac { d _ { w } } { 2 } \overline { { { u } } } }
$$

上述完全耦合的Galerkin模型可以通过线性化延迟进一步简化，该方法只适用于满足 $\tau < T _ { j }$ 的Galerkin 模态下，其中 $T _ { j } = 2 / j$ 为第 $j$ 阶Galerkin 模态的时间周期。在满足这种假设的条件下，延迟项可以写成：

$$
U _ { i } ( t - \tau ) \approx U _ { i } + \tau k _ { i } P _ { i }
$$

通过线性化延迟，得到最终Galerkin展开的常微分方程组：

$$
{ \cal U } _ { j } ^ { \& } + k _ { j } P _ { j } = 0
$$

$$
\begin{array} { l } { { \displaystyle r _ { j } + \angle \zeta _ { j } \omega _ { j } { r _ { j } } - \kappa _ { j } \upsilon _ { j } } } \\ { { \displaystyle = K \left[ \sqrt { \left| \frac { 1 } { 3 } + \sum _ { i = 1 } ^ { N } \cos ( k _ { i } x _ { f } ) \big ( U _ { i } + \tau k _ { i } P _ { i } \big ) \right| } - \sqrt { \frac { 1 } { 3 } } \right] \sin ( k _ { j } x _ { f } ) } } \end{array}
$$

$$
\left( j = 1 , 2 , . . . , N . \right)
$$

其中， $k _ { j } = j \pi$ 为第 $j$ 阶管内声模态的无量纲波数。

# 1.4Galerkin模态收敛

在极限 $N \to \infty$ 条件下，式（9）和（10）这些基函数形成一个完整的基础系，但是考虑到计算的可行性，我们只能使用有限数量的模态数目。精确捕捉到系统的线性和非线性行为所需的Galerkin模态的数目被称为模态收敛。利用Matlab编程实现了对式（15)和（16)的数值求，对不同数目的Galerkin模态下的系统演化进行比较。对于在线性不稳定区域，具有不同数量声学模态的该系统的时间演化的比较见图2。可以得到1阶Galerkin声学模态下极限环的振幅和相位与10阶Galerkin声学模态下极限环的振幅和相位差别较大，但随着Galerkin模态数目的增加，极限环的振幅和相位差别逐渐减小。根据图2，我们可以看出，当取9阶和10阶声学模态得到数值解的差异是几乎可以忽略不计，也再次说明了10阶声学模态Galerkin投影的收敛性。对于10阶声学模态，增加一阶Galerkin模态所改变的声波速度极限环振幅小于 $1 . 4 \% ^ { [ 1 2 ] }$ 。因此，在本文以后的所有计算中，我们采用10阶Galerkin模态的模型来进行线性和非线性稳定性分析以确保收敛性。

![](images/27662663d423cbddc76a2263986248506b1d4b893213285a8bd2e5b3e2dc7037.jpg)  
图2不同声学Galerkin模态数目下系统随时间演化的比较，系统参数为： $K { = } 1$ $_ { c _ { 1 } = 0 . 1 }$ ， $c _ { 2 } { = } 0 . 0 6$ ， $\scriptstyle x _ { f } = 0 . 3$ ， $\tau = 0 . 2 \$ 0Fig.2 Comparison of time evolution of the system with differentacoustic Galerkin mode numbers.The parameter values of thesystemare $K { = } 1$ $c _ { 1 } { = } 0 . 1$ $c _ { 2 } { = } 0 . 0 6$ $\scriptstyle x f = 0 . 3$ and $\tau = 0 . 2$

# 2线性稳定性分析

为研究无穷小扰动对系统稳定性的影响，首先对系统进行线性稳定性分析。如果系统逐渐远离稳定状态，则系统最终是不稳定的，如果系统逐渐接近稳定状态，那么系统最终达到稳定状态。这是指局部分析系统在稳定状态附近时的稳定性变化。另一方面，非线性稳定性分析是研究有限振幅扰动对系统的影响效果，并用于表征所得到的系统渐近状态。由于系统平衡解失稳，系统的行为发生改变的临界点称为分岔点。一旦一个分岔点根据某个参数被确定，该分岔点本身继续与系统另一个相关参数变化。分岔点分支提供了线性稳定的边界，该边界可以分离相关参数空间中线性稳定和线性不稳定的区域。这个稳定边界是在所有自由参数变化空间的一个超曲面，但比较方便的是我们可以表示几个适当的二维投影曲线。

在Rijke管中，系统参数有加热器的无量纲加热功率、加热器的位置、阻尼系数以及时间延迟，但是在实际实验操作条件下，可以精确改变的参数只有无量纲加热功率和加热器的具体位置，时间延迟和阻尼系数都是根据其他条件来改变的。我们以加热器位置和时间延迟项的线性稳定性边界为例，对加热器位置和时间延迟变化时的线性稳定性区域和线性不稳定区域进行分析。一个典型的加热器的位置和时间延迟的线性稳定边界变化如图3所示，显示了对于确定的阻尼和加热器功率等固定系统参数值，对于加热器位置 $( \boldsymbol { \mathbf { \mathit { x } } } _ { f } )$ 的一个选择范围，系统是否为线性不稳定则取决于时间延迟 $\mathbf { \Xi } ( \mathbf { \Lambda } _ { \tau } \mathbf { \Lambda } )$ ，反之亦然。对于较小或合理大的 $\tau$ ，比如 $\tau < 0 . 1 5$ 和$\tau > 0 . 8 5$ ，加热器在任何位置时，Rijke管系统都是线性稳定的，即对于小扰动，系统都最终趋于稳定状态。只有在 $0 . 1 5 < \tau < 0 . 8 5$ 范围内，系统平衡解的稳定性取决于加热器的位置。

![](images/417b9dd6aecf3df5f7bbece9a4799e4c4c0ae7301d62ef2680fffaccfbd49a2d.jpg)  
图3加热器位置xf和时间延迟 $\boldsymbol { \tau }$ 的线性稳定性边界，系统其他参数为： $K { = } 0 . 8$ ， $_ { c 1 = 0 . 1 }$ ， $c _ { 2 } { = } 0 . 0 6$ 。Fig.3Linear stability boundary between $x _ { f }$ and $\tau .$ The otherparametervaluesof the system are $K { = } 0 . 8$ ， $c _ { 1 } { = } 0 . 1$ and $c _ { 2 } { = } 0 . 0 6$ 中

# 3分叉分析

分岔分析是研究分岔现象的特性和产生机理。分岔现象是指对于某些完全确定的非线性系统，当系统的某一参数 $\mu$ 连续变化到某个临界值 $\mu _ { c }$ 时，系统的全局性性态（定性性质、拓扑性质等）会发生突然变化。 $\mu _ { c }$ 称为参数 $\mu$ 的分岔值或分支值。系统稳定状态失去稳定性出现孤立的极限环周期解的分岔称为Hopf 分岔。极限环的新兴分支的稳定性决定了Hopf分支的性质或类型。这两种Hopf分岔类型图4所示。如果极限环是不稳定，如图4（a）所示，不稳定极限环分支形成一个双稳态区域，在该区域内稳态解对于小扰动是稳定的而对于大扰动是不稳定的。然而，不稳定极限环的这一分支可能会发生折叠分岔和稳定平衡。对于小于折叠点的参数值，稳定解对于任何幅度的扰动都是稳定的，因此系统是全局稳定的。因此在亚临界分岔情况下，线性（局部）和非线性（全局）的稳定性边界是不同的。这种分岔行为被称为亚临界Hopf 分岔。但如果极限环是稳定的如图4（b）所示，系统平稳地从稳定的稳态解发展为一种具有递增极限环振幅不稳定的稳态解。这种分岔类型称为超临界Hopf分岔。

![](images/eb5628fa6c59495292c54a1f54801fb3ac5999fb426f60074ab1f5c42be7610b.jpg)  
图4（a）亚临界和（b）超临界Hopf分岔附近参数变化时 对应的分岔行为[13]。 Fig.4Bifurcation behavior of a measure for the variation of a parameter near(a) Subcritical and (b) Super-critical Hopf bifurcation.

可通过定性分析方法判定亚临界和超临界Hopf分岔。 $\left( 1 \pm X \right) ^ { \alpha }$ 形式的源项非线性分岔的性质可以通过把非线性项 $X$ 展开成级数，并放弃高阶项来判断。上述 $\left( 1 \pm X \right) ^ { \alpha }$ 表达式的二项扩展的结果为

下面的式子：

$$
1 \pm \alpha X + { \frac { \alpha { \left( \alpha - 1 \right) } } { 2 ! } } X ^ { 2 } \pm { \frac { \alpha { \left( \alpha - 1 \right) } { \left( \alpha - 2 \right) } } { 3 ! } } X ^ { 3 } + \ldots
$$

在上述表达式中，当 $0 < | \alpha | < 1$ 和 $\left| \alpha \right| > 2$ 时，一阶项$\alpha X$ 和三阶项 $\alpha ( \alpha - 1 ) ( \alpha - 2 ) X ^ { 3 } / 3 !$ 的符号是相同的，而当 $\displaystyle { 1 < \left| \alpha \right| < 2 }$ 时，一阶项 $\alpha X$ 和三阶项$\alpha ( \alpha - 1 ) ( \ \alpha - 2 ) X ^ { 3 } / 3 !$ 这两项的符号是不同的。一阶和三阶项的符号标志决定了分岔点的性质。每当这两项具有相同的符号时，分岔是亚临界分岔类型的，而当这两项具有不同的符号时，分岔为超临界分岔类型的。对于Rijke 管模型中的热释放速率波动，$\alpha = 1 / 2$ ，这意味着该模型将出现亚临界类型Hopf分岔。

在Rijke管热声系统中，可变的系统参数有有加热器的无量纲加热功率 $K$ 、加热器的位置 $\displaystyle x _ { f \setminus }$ 阻尼系数 $c _ { 1 }$ 以及时间延迟 $\tau$ 。分别对系统内无量纲加热功率 $K$ 、加热器的位置 $\quad x _ { f \setminus }$ 阻尼系数 $c _ { 1 }$ 以及时间延迟 $\tau$ 的变化进行分岔分析。

# 3.1加热器功率的影响

在Rijke管热声系统中的加热器为电热丝加热，通过改变 $K$ 值来探究加热器功率对系统产生的影响。无量纲加热器功率可以通过增加提供给加热器的功率来达到，其增大代表着系统驱动力的增加，增加的驱动力使得系统变得更加不稳定。因此，对于较小的 $K$ 值，系统的平衡是稳定的，在所有初始扰动下，都会衰减渐近接近于零。增加 $K$ 值将降低流动的稳定性裕度，在分岔点附近，系统演变为线性不稳定，从而导致管内的振荡流模式。图5为计算得到的无量纲加热器功率（ $K$ ）的变化对系统演化的影响。空心圆表明不稳定解，实心圆代表稳定解。由图可知靠近Hopf分岔点的小振幅极限环是不稳定的，这些不稳定的极限环与稳定平衡解共存。这些极限环的不稳定分支进一步经历一个折叠点分岔获得稳定。据此可判定分岔属于亚临界类型，证实了之前的结论。在其他系统参数一定的条件下，系统随时间的演化行为取决于 $K$ 值的变化。在$K < 0 . 5 1 5$ 时，系统对于任何幅度的扰动，都最终趋于零，此区域为全局稳定区域。随着 $K$ 值的不断增大，当 $0 . 5 1 5 < K < 0 . 6 1 5$ 时，系统有三种可能的状态，稳定状态，不稳定极限环以及稳定极限环。根据初始条件的不同，系统可能最终进入稳定状态或者周期振荡，该区域被称为双稳态区域。当

$K > 0 . 6 1 5$ 时，系统进入全局不稳定区域，对于任意小幅度的初始扰动，系统最终都会达到极限环状态。通过无量纲加热功率的分岔图也可以证明无量纲加热功率的增大是系统产生热声不稳定的主要原因。

![](images/a036cc079bb7c4ca8bd7265aa230f74ee3e2835e3cb18c46b2add961beb28374.jpg)  
图5无量纲加热器功率 $K$ 变化时的分岔图，系统其他参数值： $c _ { 1 } { = } 0 . 1$ ， $\scriptstyle c 2 = 0 . 0 6$ ， $\scriptstyle x f = 0 . 3$ ， $\tau = 0 . 2$ 。Fig.5Bifurcation plot for variation of non-dimensional heaterpower $K$ .The other parameter values of the system are $c _ { 1 } { = } 0 . 1$ $c _ { 2 } { = } 0 . 0 6$ $\scriptstyle x _ { f } = 0 . 3$ and $\tau = 0 . 2$

# 3.2阻尼系数的影响

为了研究系统中阻尼变化对系统响应的影响，阻尼模型中的一个阻尼参数 $\ d ( \ c _ { 1 } \ ) $ 是可以变化的。在实际的实验条件下，系统阻尼的大小是通过改变管道的末端条件来改变。根据非线性理论，增加阻尼可以增强系统的稳定性。图6为系统行为演化随阻尼系数 $\left( \mathbf { \Phi } _ { c _ { 1 } } \right)$ 的变化的分岔图谱。如预期的一样，增加阻尼确具有增强系统稳定的作用，因为平衡解对于较大的阻尼系数，取任意时间延迟 $\tau$ 都是稳定的，降低阻尼则使系统失去稳定性。对于图示的时间延迟值、无量纲加热功率以及加热器位置参数，存在一个临界值 $c _ { 1 } = 0 . 1 9$ ，当低于该值时，系统对于任何幅度的初始扰动最终都会发展成稳定振幅的极限环，该临界值即为亚临界Hopf分岔点。当$c _ { 1 } < 0 . 1 9$ 时，对于任何幅度的初始扰动，系统最终都会发展成具有稳定振幅的极限环；当$0 . 1 9 < c _ { 1 } < 0 . 2 5$ 时，该区域为双稳态区域，在该区域内，对于较大幅度的初始扰动，系统发展成为稳定极限环，而对于小振幅的扰动，系统最终会趋于平衡；随着阻尼系数 $c _ { 1 }$ 的进一步增大，当 $c _ { 1 } > 0 . 2 5$ 时对于任意幅度的初始扰动，系统都最终趋于稳定状态， $c _ { 1 } = 0 . 2 5$ 即为折叠点。

![](images/2c0c4cd75aa88438ed9c8933b8e141a4b54e55714db69d7b3e2678c6b42b607e.jpg)

图6阻尼系数 $( c _ { 1 } )$ 变化时的分岔图，系统的其它参数值为：$K { = } 1$ $, ~ c _ { 2 } { = } 0 . 0 6 , ~ x _ { f } { = } 0 . 3 , ~ \tau = 0 . 2 \circ$   
Fig.6 Bifurcation plot for variation of damping coeficient $c _ { 1 }$ The other parameter values of the system are $K { = } 1$ ， $c _ { 2 } { = } 0 . 0 6$ $x _ { f }$ $\scriptstyle = 0 . 3$ and $\tau = 0 . 2$ 车

# 3.3加热器位置的影响

加热器的位置 $( x _ { f } )$ 对系统动力学也有显著的影响，加热器位置的改变是通过把加热器放置在沿管道长度不同的位置处来实现。系统稳定性的变化以一种特别的方式取决于管道内加热器的位置变化加热器位置 $( \boldsymbol { x } _ { f } )$ 变化时的分岔图谱如图7所示。当管道内加热器的位置从上游的开端开始变化时，该系统最初是线性稳定的。在加热器的位置 $x _ { f I }$ 的临界值，系统演变为线性不稳定。随着加热器位置的进一步变化，系统仍然是线性不稳定的，直到加热器位置位于 $x _ { f 2 }$ ，在该点形成另一个Hopf 分岔点，系统也重新变成稳定状态。加热器位置 $( \boldsymbol { \mathbf { \mathit { x } } } _ { f } )$ 变化的分岔图表明，在管的两端，Hopf分岔点均为亚临界Hopf分岔。在两个Hopf分岔点之间，存在一个全局不稳定区域。在全局不稳定的区域内，对于任何的初始条件，系统将渐近达到相应稳定振幅的极限环。根据加热器位置变化时的分岔图，我们可以得到两个亚临界Hopf 分岔点的具体值。对于我们选定的其他系统参数，当 $x _ { f } < 0 . 1 1$ 时，对于任何幅度的初始扰动，系统最终都会趋于稳定；当$0 . 1 1 < x _ { f } < 0 . 1 4$ 时，系统处于双稳态区域，系统根据初始条件的不同产生不同的演化行为，则第一个亚临界Hopf分岔点位置 $x _ { f 1 } = 0 \mathrm { ~ . ~ } 1$ ；当（20 $0 \cdot 1 { < } 4 \kappa _ { f } < 0$ 时，系统处于全局不稳定区域，对于任何的初始条件，系统将渐近达到相应稳定振幅的极限环；当 $0 . 3 6 5 < x _ { f } < 0 . 3 9$ 时，系统又进入双稳态区域，则第二个亚临界Hopf分岔点位置

Xf2=0.36；随着加热器位置进一步变化，当xf>0.39时，系统重新进入全局稳定性区域，对于任何幅度的初始扰动，系统最终都会趋于稳定。

![](images/95046676aaf1efb3d09c69390becca712ca833783b28e21bc57ec291a93c4ede.jpg)

图7加热器位置 $( \boldsymbol { \mathbf { \mathit { x } } } _ { f } )$ 变化时的分岔图，系统的其它参数为：$c _ { 1 } { = } 0 . 1$ ， $\scriptstyle c 2 = 0 . 0 6$ ， $K { = } 0 . 8$ ， $\tau = 0 . 2$ 。  
Fig.7Bifurcation plot for variation of location of heater $( x _ { f } )$ The other parameter values of the system are $c _ { 1 } = 0 . 1$ $c _ { 2 } = 0 . 0 6$ $K = 0 . 8$ and $\tau = 0 . 2$

# 3.4时间延迟的影响

在 Rijke 管中，由于加热器与流动介质之间热惯性（thermalinertia）的存在，传热和流动速率的变化之间存在一个时间延迟 $\tau$ ，其大小与加热器中电热丝的直径以及来流速度有关。在实际实验条件下，时间延迟项 $\mathbf { \Xi } ( \mathbf { \Lambda } _ { \tau } \mathbf { \Lambda } )$ 很难精确的进行改变。时间延迟（τ）变化时对应的分岔图谱见图8。亚临界Hopf分岔点对应的时间延迟值为 $\tau = 0 . 1 5 5$ 。当$\tau < 0 . 1$ 3时，系统为处于线性稳定状态，对于任意幅度的初始扰动，系统最终都趋于稳定状态；当$0 . 1 3 < \tau < 0 . 1 5 5$ 时，系统对于小振幅的扰动最终趋于平衡，而对于大振幅的扰动，系统发展成为极限环，即双稳态区域；当 $\tau > 0 . 1 5 5$ 时，系统处于线性不稳定区域，对于任意小的初始扰动，系统最终都会发展成为极限环。值得注意的是，发现在$\tau > 0 . 1 5 5$ 的线性不稳定区域内，随着时间延迟 $\mathbf { \Xi } ( \mathbf { \Lambda } _ { \tau } \mathbf { \Lambda } )$ （204号的逐渐增大，振幅 $\left| U _ { 1 } \right|$ 的值先逐渐增大后又逐渐减小。这一现象可通过瑞利准则来解释[17]。时间延迟的存在是因为热源的放热和流动之间存在热惯性，当加热器功率增大时，时间延迟会随之增大。时间延迟的增大使得声场振荡和放热脉动的相位差发生变化，当二者相位差逐渐增大而远离 $0 ^ { \circ }$ 时，振荡幅度会逐渐减小，从而形成了这一现象。据此也可以推测当 $\tau = 0 . 4$ 时，声场振荡和放热脉动的相位差刚好为 $0 ^ { \circ }$ ，故此时振荡幅值最大。

![](images/9aff70c152a1583a666f0e9ff4b9ef1eb6f0fa1e6ef6f36c40b26247b3d87c8a.jpg)  
图8时间延迟 $( \tau )$ 变化的分岔图，系统的其它参数为： $c _ { 1 } { = } 0 . 1$ $c _ { 2 } { = } 0 . 0 6$ ， $K { = } 0 . 8$ ， $\scriptstyle x f = 0 . 3$ 。Fig.8Bifurcation plotforvariation of time lag(t).The otherparameter values of the system are $c _ { 1 } { = } 0 . 1$ $c _ { 2 } { = } 0 . 0 6$ $K { = } 0 . 8$ xf$\scriptstyle = 0 . 3$

# 4结论

本文对Rijke管热声系统进行建模，利用Galerkin方法对控制方程进行数值求解，分析了系统相关动力学特性，得出如下结论：（1）在Rijke管热声不稳定模型求解时，采用10阶Galerkin模态来计算足以确保收敛性。（2）Rijke管热声系统分岔行为属于亚临界Hopf分岔，系统存在一个线性稳定边界和一个非线性稳定边界，在此二者之间为双稳态区域。（3）获得了系统对无量纲加热功率 $K ,$ 加热器位置 $x _ { f \setminus }$ 阻尼系数 $c _ { 1 }$ 以及时间延迟 $\tau$ 的分岔图谱。无量纲加热功率 $K$ 、阻尼系数 $c _ { 1 }$ 和时间延迟 $\tau$ 的分岔图谱只存在一个Hopf 分岔点，而加热器位置 $x _ { f }$ 的分岔图谱存在两个Hopf分岔点。

# 参考文献

[1] Huang X M, Baumann W T. Reduced-order modelingofdynamicheatrelease for thermoacousticinstability prediction[J]. Combustion Science and Technology，2007, 179(3): 617-636.   
[2] Huang Y, Yang V. Dynamics and stability of lean-premixedswirl-stabilized combustion[J]. Progress in Energy and Combustion Science, 2009,35(4): 293-364.   
[3] Lieuwen T C. Experimental investigation of limit-cycle oscillationsin an unstablegas turbine combustor[J]. Journal of Propulsion and Power,2002,18(1): 61-67.   
[4] Knoop P,CulickFEC,ZukoskiEE.Extension of the stability of motions in a combustion chamber by nonlinear active control based on hysteresis[J].Combustion Science and Technol0gy, 1997,123(1-6): 363-376.   
[5] Olgac N, Cepeda-Gomez R, Zalluhoglu U, et al. Parametricinvestigation ofthermoacoustic instability (TAI) in a rijke tube: a time-delay perspective[J]. International Journal of Spray and Combustion Dynamics,2015,7(1): 39-67.   
[6] Weng F L, Zhu M, Jing L Y. Beat: a nonlinear thermoacoustic instability in Rijke burners[J]. International Journal of Spray and Combustion Dynamics,2014,6(3): 247-265.   
[7] Sayadi T, Le Chenadec V, Schmid P J,et al. Thermoacoustic instability - a dynamical system and time domain analysis[J]. Journal of Fluid Mechanics,2014, 753448-471.   
[8] Olgac N, Zalluhoglu U, Kammer A S. Predicting Thermoacoustic Instability:A Novel Analytical Approach and Its Experimental Validation[J]. Journal of Propulsion and Power,2014,30(4): 1005-1015.   
[9] Raun RL, Beckstead M W,Finlinson J C, et al. A Review of Rijke Tubes,Rijke Burners and Related Devices[J]. Progress in Energy and Combustion Science,1993,19(4): 313-364.   
[10] Jahnke C C,Culick F E C.Application of Dynamical-SystemsTheorytoNonlinear Combustion Instabilities[J]. Journal of Propulsion and Power, 1994,10(4): 508-517.   
[11] Ananthkrishnan N,Deo S,Culick F E C. Reduced-order modeling and dynamicsof nonlinear acoustic waves in a combustion chamber[J]. Combustion Science and Technol0gy, 2005,177(2): 221-247.   
[12] BalasubramanianK, SujithR I.Thermoacoustic instability in a Rijke tube: Non-normality and nonlinearity[J].Physics of Fluids,2Oo8,20(4).   
[13] Subramanian P, Mariappan S,Sujith R I,et al. Bifurcationanalysis of thermoacoustic instabilityinahorizontalRijketube[J]. International Journal of Spray and Combustion Dynamics,2010,2(4): 325-355.   
[14] Waugh I,Geuss M,Juniper M. Triggering, bypass transition and the effect of noise on a linearlystablethermoacousticsystem[J]. Proceedings of the Combustion Institute,2011, 332945-2952.   
[15] Waugh I C， Juniper M P. Triggering in a thermoacoustic system with stochastic noise[J]. International Journal of Spray and Combustion Dynamics,2011,3(3): 225-241.   
[16] Heckl M A.Nonlinear Acoustic Effects in the Rijke Tube[J]. Acustica,1990,72(1): 63-71.   
[17] Nicoud F,Poinsot T.Thermoacoustic instabilities: Should the Rayleigh criterion be extended to include entropychanges?[J]. Combustion and Flame， 2005, 142(1-2): 153-159.

# 附页：

第一作者：冯建畅  
通讯地址：陕西省西安市友谊西路127号西北工业大学  
手机号码：18710955930  
电子邮箱：fengjianchang@mail.nwpu.edu.cn