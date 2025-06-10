# 非互易Aubry-André模型的经典电路模拟 (Electrical circuit's simulation of nonreciprocal Aubry-André models)

成恩宏 (Enhong Cheng)¹ and 郎利君 (Li-Jun Lang)1,2,\*

1 华南师范大学物理与电信工程学院，广东省量子调控工程与材料重点实验室，广州 510006   
(Guangdong Provincial Key Laboratory of Quantum Engineering and Quantum Materials, School of Physics and Telecommunication Engineering, South China Normal University，Guangzhou 51ooo6，China) 2 华南师范大学量子物质研究院，广东省核物质科学与技术重点实验室，广州 510006   
(Guangdong Provincial Key Laboratory of Nuclear Science,Institute of Quantum Matter, South China Normal University，Guangzhou 51ooo6，China)

(Dated:2022年3月24日)

非厄米的引入扩展了传统厄米量子系统中的概念并诱导出许多新奇的物理现象，比如非厄米系统所独有的非厄米趋肤效应，这使得对非厄米量子模型的模拟成为大家关注的热点，相比于量子平台，经典系统具有成本低廉、技术成熟、室温条件等优势，而其中的经典电路系统则更加灵活，原则上可以模拟任意维度、任意格点间跃迁、任意边界条件下的量子紧束缚模型，已经成为模拟量子物态的有力平台.本文利用经典电路通过 SPICE 成功模拟了一个重要的非厄米量子模型—— 非互易 Aubry-Andreé 模型——的稳态性质，此模型同时具有非互易的格点跃迁和准周期的格点在位势．以此为例，详细介绍了如何建立经典电路的拉普拉辛形式与量子紧束缚模型哈密顿矩阵在不同边界条件下的映射，尤其是如何利用电流型负阻抗变换器构建模型的非互易性：然后，根据电路的格林函数，通过AC电流驱动并测量电压响应的方式，用 SPICE 模拟了周期边界条件下的复能谱和相应的能谱缠绕数，以及开边界条件下的趋肤与局域模式的竞争，其中，为了使电路的响应不发散，本文还解析地给出辅助元件的设置原则，结果显示，SPICE 模拟与理论计算很好地吻合，为进一步的实验实现提供了详细的指导．由于本文电路设计与测量方案的普适性，原则上可以直接应用于其他非厄米量子模型的电路模拟.

The introduction of non-Hermiticity into traditional Hermitian quantum systems generalizes their basic notions and brings about many novel phenomena,e.g.,the non-Hermitian skin efect that is exclusive to non-Hermitian systems,attracting enormous attention from almost all branches of physics. Contrary to the quantum platforms,classical systems have the advantages of low cost and mature techniques under room temperature.Among them,the classcal electrical circuits are more fexible on simulating quantum tight-binding models in principle with any range of hopping under any boundary conditions inany dimension,and have become a powerful platform for the simulation of quantum matters. In this paper,by constructing an electrical circuit,we simulate by SPICE the static properties of a prototypical non-Hermitian model - the nonreciprocal Aubry-André (AA) model that has the nonreciprocal hopping and on-site quasiperiodic potentials.

The paper is organized as follows:Following the introduction,in Sec.II we review in detail the Laplacian formalism of electrical circuits and the mapping to the quantum tight-binding model. Then,in Sec.II,an electrical circuit is proposed with resistors,capacitors, inductors,and the negative impedance converters with current inversion (INICs)，establishing a mapping between the circuit's Laplacian and the non-reciprocal AA model's Hamiltonian under periodic boundary conditions (PBCs) or open boundary conditions (OBCs). Especially, the nonreciprocity, the key of this model, is realized by INICs. In Sec IV,based on the mapping,for the proposed circuit under PBCs,we reconstruct the circuit's Laplacian via SPICE by measuring voltage responses of an AC current input at each node.The complex spectrum and its winding number $\nu$ can be calculated by the measured Laplacian,which are consistent with the theoretical prediction, showing $\nu = \pm 1$ for non-Hermitian topological regimes with complex eigenenergies and extended eigenstates,and （204 $\nu = 0$ for topologically trivial regimes with real eigenenergies and localized eigenstates. In Sec V, for the circuit under OBCs,a similar method is used for measuring the node distribution of the voltage response,which simulates the competition of non-Hermitian skin efects and the Anderson localization, depending on the strength of quasiperiodic potentials; the phase transition points also appear in the inverse participation ratios of the voltage responses.

During the design process, the parameters of auxiliary resistors and capacitors are evaluated for obtaining stable responses, because the complex eigenfrequecies of the circuits are inevitable under PBCs.Our detailed scheme can directly instruct further potential experiments,and the designing method of the electrical circuit is universal and can in principle be applied to the simulation for other quantum tight-binding models.

# I．引言

近些年，非厄米物理[1]引起了物理学各个领域的广泛关注，它除了传统上可以描述经典系统中增益损耗带来的现象，还被用来描述量子开放系统的性质 [2]．不同于封闭系统的厄米哈密顿量，非厄米的引入扩展了传统量子力学的范式 [3]，比如复数能谱、双正交基等，这诱导出许多新奇现象：手征-时间反演对称性 (parity-timesymmetry，简称PT 对称性）的破缺 [4-9]、非厄米简并点[10,11]、模式转换(mode switching)[12]等．非厄米性同样扩展了大家对于拓扑态的理解．一个典型的反常是，在厄米拓扑系统中作为基本原则的体-边对应关系(bulk-boundary correspondence）在非厄米系统中不总是适用 [13-26],而仅在非厄米系统中存在的非厄米趋肤效应[16,23]被认为是此原则失效的一个重要原因．非厄米趋肤效应的发现引发了对于传统的厄米量子效应与其竞争关系的广泛研究，比如与安德森局域化的竞争 [27-33]和与Hubbard 相互作用的竞争[34-39]等.

鉴于非厄米物理的重要性，在实验上模拟非厄米模型及其独有的新奇现象就显得格外重要．相比传统的量子平台（比如冷原子系统[8,9,40])，经典系统对于模拟非厄米模型有着天然的优势，除了成本低廉、技术成熟等特点，它可以非常直接地利用自身的增益和损耗实现非厄米性，并已成为模拟非厄米系统的有力平台，比如光学系统[7,41-45]和机械系统 [46,47]等．其中，经典电路系统因其不受限的网络形式和高度的调控自由度，原则上可以模拟任意维度、任意格点间跃迁、任意边界条件下的量子紧束缚模型，成为量子系统模拟的有力竞争者．目前在电路系统下已经成功实现了很多非厄米的量子模型及其现象，比如PT 对称性破缺 [48,49]、非互易Su-Schrieffr-Heeger(SSH)模型 [50,51]、二维非互易陈绝缘体 [52,53]、非互易高维模型 [54,55]、非互易狄拉克模型[56]以及非厄米异常线[57]等.

对于非厄米趋肤效应与准无序的竞争关系，文献 [27]提出了非互易（non-reciprocal)Aubry-André（AA）模型：

$$
\hat { H } = \kappa \sum _ { n = 1 } ^ { N - 1 } \left( e ^ { \alpha } | n + 1 \rangle \langle n | + e ^ { - \alpha } | n \rangle \langle n + 1 | + v _ { n } | n \rangle \langle n | \right) + \kappa \big ( e ^ { \alpha } e ^ { - i \Phi } | 1 \rangle \langle N | + e ^ { - \alpha } e ^ { i \Phi } | N \rangle \langle 1 |
$$

其中， $\kappa e ^ { \pm \alpha }$ 描述最近邻格点间的跃迁强度，如 $\alpha \neq 0$ 则表示前后两方向的跃迁强度不相等，即跃迁具有非互易性（nonreciprocity); $v _ { n } = 2 \lambda \cos ( 2 \pi \beta n )$ 表示在位的准周期/无序势, $\lambda$ 表示无序强度， $\beta$ 一般取无理数．对于有限尺寸的系统，可以取格点数 $N = F _ { s }$ 且 $\beta = F _ { s - 1 } / F _ { s }$ 以保证准周期势的周期与格点的周期在系统尺寸内不匹配(incommensurate)，其中 $F _ { s }$ 表示斐波那契数列的第 $s$ 个值．为清楚表示有限尺寸下的边界条件，在公式 (1)中特别将首尾之间的跃迁项显示写出 (第二个圆括号内)，并且可以表示在整个一维环中间加入磁通 $\Phi$ 后的哈密顿量 (取特定规范后)．为方便后面的电路模拟，以格点态 $\{ | n \rangle \}$ 为基矢写出哈密顿量 $\hat { H }$ 的矩阵形式:

$$
\mathcal { H } = \kappa \left( \begin{array} { c c c c c } { v _ { 1 } } & { e ^ { - \alpha } } & & & { e ^ { \alpha } e ^ { - i \Phi } } \\ { e ^ { \alpha } } & { v _ { 2 } } & { e ^ { - \alpha } } & & \\ & { \ddots } & { \ddots } & { \ddots } & \\ & & { e ^ { \alpha } } & { v _ { N - 1 } } & { e ^ { - \alpha } } \\ { e ^ { - \alpha } e ^ { i \Phi } } & & & { e ^ { \alpha } } & { v _ { N } } \end{array} \right) .
$$

此模型的非厄米拓扑性质以及趋肤效应与局域化的竞争关系，文献 [27]已经在理论上详细讨论，这里简单回顾下主要结论：在周期边界条件下,准无序强度较弱 $( \lambda < \operatorname* { m a x } { \{ e ^ { \alpha } , e ^ { - \alpha } \} } \equiv \lambda _ { c } )$ 时，系统的本征态为扩展态，其本征能谱在复平面上为绕原点的圈，表明处于非厄米拓扑相，可由能量缠绕数 (winding number) $\nu = \pm 1$ 表征；随着准无序强度的增强，当 $\lambda > \lambda _ { c }$ 时，系统的本征态经历从扩展态到局域态的转变，与此同时，本征能谱收缩成实轴上的一条线，表明处于拓扑平庸相，相应的能量缠绕数 $\nu = 0$ ．有趣的是，拓扑相变与局域相变点完全一致，这是由于局域化改变了系统的本征能谱在复平面的分布，进而影响了能量缠绕数．相应地，在开边界条件下，因为局域的转变使系统对边界不再敏感，系统具有同样的相变点，区别只是拓扑相区的本征态由于趋肤效应变为趋向某一边缘（由 $\alpha$ 的正负决定哪个边缘)，且本征能谱变为实数；局域相区的本征态两边的衰减长度变得不同

本文的主要目的是通过对非互易AA量子模型的经典电路模拟，详细介绍如何用电路的拉普拉辛形式模拟量子紧束缚模型，便于感兴趣的读者利用类似方法模拟其他量子模型，以及为实验实现提供详细指引．剩下的内容安排如下：第二节详细介绍如何构建经典电路的拉普拉辛形式与量子紧束缚模型的映射，第三节具体给出实现不同边界条件下非互易 AA 模型的电路设计方案,第四节和第五节利用 SPICE 分别模拟非互易AA 模型在周期边界条件下的能谱和能量缠绕数以及在开边界条件下趋肤与局域模式的竞争，最后一节进行总结

# II．经典电路的拉普拉辛形式与紧束缚模型的对应

任意经典电路组成的网络都可以用一个图（graph）来表示，其节点和边分别对应电路的连接点和元件 [48,58,59]．比如由电阻、电感和电容(简称RLC)等被动元件组成的电路，元件各自的物性方程为

$$
V = R I , V = L { \frac { d I } { d t } } , C { \frac { d V } { d t } } = I ,
$$

这里的 $V$ 和 $I$ 分别表示元件两端的电压差和通过元件的电流， $( R , L , C )$ 分别为元件的电阻、电感和电容．根据基尔霍夫(Kirchhoff）电流定律，利用以上物性方程，可以得到图中每个节点关于时间 $\mathbf { \Psi } _ { t }$ 的微分方程:

$$
\begin{array} { l } { \displaystyle { \frac { d } { d t } I _ { n } ( t ) = C _ { n g } \frac { d ^ { 2 } } { d t ^ { 2 } } V _ { n } ( t ) + R _ { n g } ^ { - 1 } \frac { d } { d t } V _ { n } ( t ) + L _ { n g } ^ { - 1 } V _ { n } ( t ) } } \\ { \displaystyle { \qquad + \sum _ { m \neq n } \left\{ C _ { n m } \frac { d ^ { 2 } } { d t ^ { 2 } } [ V _ { n } ( t ) - V _ { m } ( t ) ] + R _ { n m } ^ { - 1 } \frac { d } { d t } [ V _ { n } ( t ) - V _ { m } ( t ) ] + L _ { n m } ^ { - 1 } [ V _ { n } ( t ) - V _ { m } ( t ) ] \right\} } } \end{array}
$$

其中, $I _ { n } ( t )$ 和 $V _ { n } ( t )$ 分别代表电路节点 $n$ 的外界输入电流和对地电压，这里用 $( R _ { n m } , L _ { n m } , C _ { n m } )$ 分别表示从节点 $n$ 到节点 $m$ （下标 $g$ 代表接地)的等效电阻、等效电感和等效电容，以便描述更一般的具有非互易特性的元件，通常的被动 RLC 元件为互易的，即 $R _ { n m } = R _ { m n } \equiv R , L _ { n m } = L _ { m n } \equiv L , C _ { n m } = C _ { m n } \equiv C .$ ，上述方程可以写成更紧凑的矩阵形式：

$$
\frac { d } { d t } \mathcal { T } ( t ) = \mathcal { C } \frac { d ^ { 2 } } { d t ^ { 2 } } \mathcal { V } ( t ) + \mathcal { R } \frac { d } { d t } \mathcal { V } ( t ) + \mathcal { L } \mathcal { V } ( t ) ,
$$

其中， $\boldsymbol { \mathcal { I } } ( t )$ 和 $\nu ( t )$ 分别表示节点输入电流和对地电压的列矢量， $( \mathcal { R } , \mathcal { L } , \mathcal { C } )$ 分别为等效电阻、等效电感和等效电容构成的系数矩阵，其矩阵元为

$$
\begin{array} { l } { { \displaystyle { \mathcal { C } } _ { n n } = C _ { n g } + \sum _ { m \neq n } C _ { n m } , \qquad { \mathcal { R } } _ { n n } = R _ { n g } ^ { - 1 } + \sum _ { m \neq n } R _ { n m } ^ { - 1 } , \qquad { \mathcal { L } } _ { n n } = L _ { n g } ^ { - 1 } + \sum _ { m \neq n } L _ { n m } ^ { - 1 } ; } } \\ { { \displaystyle { \mathcal { C } } _ { n m } = - C _ { n m } ( n \neq m ) , \qquad { \mathcal { R } } _ { n m } = - R _ { n m } ^ { - 1 } ( n \neq m ) , \qquad { \mathcal { L } } _ { n m } = - L _ { n m } ^ { - 1 } ( n \neq m ) . } } \end{array}
$$

对于微分方程 (5),考虑具有固定频率 $\omega$ 的 AC 电流源 $\boldsymbol { \mathcal { I } } ( t )$ 及其电压响应 $\nu ( t )$ ，其形式为

$$
\begin{array} { r } { \mathcal { T } ( t ) = \mathcal { T } e ^ { i \omega t } , \quad \mathcal { V } ( t ) = \mathcal { V } e ^ { i \omega t } . } \end{array}
$$

将它们代入方程 (5)，得到不含时的矩阵方程:

$$
\begin{array} { r } { \mathcal { T } = ( i \omega \mathcal { C } + \mathcal { R } + \mathcal { L } / i \omega ) \mathcal { V } \equiv \mathcal { I } ( \omega ) \mathcal { V } . } \end{array}
$$

这里定义的 $\mathcal { I } ( \omega )$ 被称为电路的拉普拉辛(Laplacian）矩阵或基尔霍夫矩阵 [48]，具有导纳的量纲，其矩阵元一般为复数，并且依赖于驱动频率 $\omega$ ．如果没有外界电流输入，即 $\mathcal { I } ( \omega ) \nu = 0$ ，则 $\operatorname* { d e t } { \mathcal I } ( \omega _ { c } ) = 0$ 决定了电路的本征频率谱 $\{ \omega _ { c } \}$ ．另外，也可以将等式 (8)的两边求逆，得

$$
\mathcal { V } = \mathcal { I } ^ { - 1 } ( \omega ) \mathcal { I } \equiv \mathcal { G } ( \omega ) \mathcal { I } ,
$$

其中, $\mathcal { G } ( \omega ) \equiv \mathcal { I } ^ { - 1 } ( \omega )$ 被称为电路的格林函数(circuitGreen's function)，具有阻抗的量纲

实际上，对于具有形式（7）的稳态解，任意电路网络都可以表示为拉普拉辛的形式，比如包含放大器的主动电路[49,50,53]和具有非线性元件的非线性电路[60,61]等，

为了利用经典电路系统模拟量子紧束缚模型，可以将电路拉普拉辛矩阵 $\mathcal { I } ( \omega )$ 直接与紧束缚模型在实空间的哈密顿量矩阵 $\mathcal { H }$ 相对应[59]，且拉普拉辛 $\mathcal { I } ( \omega )$ 的本征方程

$$
\mathcal { I } ( \omega ) \psi _ { n } ^ { ( r ) } ( \omega ) = j _ { n } ( \omega ) \psi _ { n } ^ { ( r ) } ( \omega ) , \quad \mathcal { I } ^ { \dagger } ( \omega ) \psi _ { n } ^ { ( l ) } ( \omega ) = j _ { n } ^ { * } ( \omega ) \psi _ { n } ^ { ( l ) } ( \omega ) ,
$$

可以直接对应哈密顿量矩阵的定态薛定谔方程.这里， $j _ { n } ( \omega )$ 为拉普拉辛矩阵的第 $n$ 个本征值,构成本征导纳谱,可以完整模拟 $\mathcal { H }$ 的能谱．特别地，由 $\operatorname* { d e t } { \mathcal I } ( \omega _ { c } ) = 0$ 可知,本征频率 $\omega _ { c }$ 使至少一个本征导纳为零，即 $j _ { n } ( \omega _ { c } ) = 0$ 由于 $\mathcal { I } ( \omega )$ 一般为非厄米矩阵，即 $\mathcal { I } ^ { \dagger } ( \omega ) \neq \mathcal { I } ( \omega )$ ，相应的本征矢通常包含本征右矢和本征左矢 $\psi _ { n } ^ { ( r , l ) } ( \omega )$ ，利用电路的交流分析，可以得到 $\mathcal { I } ( \omega )$ 的右本征模式 $\psi _ { n } ^ { ( r ) } ( \omega )$ ，从而模拟 $\mathcal { H }$ 的右本征态；左本征态可以用 $\mathcal { I } ^ { \dagger } ( \omega )$ 模拟通过元件以及驱动频率的设计和调节， $\mathcal { I } ( \omega )$ 具有高度可控性,原则上可以模拟任意维度、任意边界条件、非线性和非厄米等非常广泛的量子模型的稳态性质，

接下来，应用以上电路的拉普拉辛形式构建 $\mathcal { I } ( \omega )$ 与非互易AA模型哈密顿量矩阵 $\mathcal { H }$ 的对应关系，从而对其稳态性质进行模拟，包括周期边界条件下的能谱和缠绕数以及开边界条件下趋肤和局域模式的竞争.

# III．非互易 AA 模型的电路拉普拉辛

在交流驱动下，被动元件往往呈现出互易性，这是由最基本的基尔霍夫电流定律决定的，例如电容与电感的导纳 $J _ { C } ( \omega ) = i \omega C$ 和 $J _ { L } ( \omega ) = 1 / i \omega L$ 均不依赖于正向或反向测量即可表征。而根据公式(8)的描述，要实现拉普拉辛矩阵的非互易性 ${ \mathcal { I } } _ { m n } ( \omega ) \neq { \mathcal { I } } _ { n m } ( \omega )$ ，则需要电路中某一元件的导纳值依赖于测量的方式，这通常需要引入主动元件，比如电流型负阻抗变换器(negative impedance converter with current inversion，简称 INIC)[53].如图1(b)所示的INIC 由放大器和若干线性元件构成，根据基尔霍夫电流定律，容易得出两端的输入电流分别为

$$
{ \cal I } _ { l } = - \frac { i \omega C _ { I } Z _ { - } } { Z + } ( V _ { l } - V _ { r } ) , ~ { \cal I } _ { r } = i \omega C _ { I } ( V _ { r } - V _ { l } ) .
$$

这表明一般情况下INIC 两端不同方向的导纳不相等:

$$
J _ { l } ( \omega ) = - \frac { i \omega C _ { I } Z _ { - } } { Z + } , ~ J _ { r } ( \omega ) = i \omega C _ { I } .
$$

为方便起见，理论上选取INIC中的阻抗满足 ${ \cal Z } _ { + } = { \cal Z } _ { - }$ ，使得元件两端流向放大器的电流大小相同方向相反，即$I _ { l } = I _ { r }$ ，从而得到两个方向符号相反的导纳： $J _ { l } ( \omega ) = - J _ { r } ( \omega )$

另外，这里会用到具有负值的元件(比如负电阻等)，其两种实现形式如图1(c）所示 [49]，它们通过放大器分别实现了对地单端口和自由两端口的等效负阻抗(导纳)．根据基尔霍夫定律，可得对地单端口电路 [图1(c）左图|的输入阻抗为

$$
Z _ { g } = \frac { V _ { g } } { I _ { g } } = \frac { V _ { g } } { ( V _ { g } - 2 V _ { g } ) / Z } = - Z .
$$

类似地，自由端口电路[图1(c)右图]两端的输入阻抗分别为

$$
Z _ { i j } = \frac { V _ { i } - V _ { j } } { I _ { i } } = \frac { V _ { i } - V _ { j } } { [ V _ { i } - ( 2 V _ { i } - V _ { j } ) ] / Z } = - Z , ~ Z _ { j i } = \frac { V _ { j } - V _ { i } } { I _ { j } } = \frac { V _ { j } - V _ { i } } { [ V _ { j } - ( 2 V _ { j } - V _ { i } ) ] / Z } = - V _ { i } - V _ { j } ,
$$

即， $Z _ { j i } = Z _ { i j } = - Z$

利用以上关键元件,在由电感 $L _ { 0 }$ 和电容 $C _ { 0 }$ 组成的左手传输线离散模型(lumped-element circuit model fora left-handed transmission line） [62]的基础上，设计了如图1(a)所示的非互易AA 模型的电路模拟示意图，由图1.(a)上图：非互易AA模型的电路模拟示意图，包含 $N$ 个有效电压节点 $V _ { n }$ $( n = 1 , \cdots , N )$ ，节点间元件 $C _ { 0 }$ 和 $\mathrm { I N I C } _ { ( b ) }$ 模拟格点间的耦合，其中 $\mathrm { I N I C } _ { ( b ) }$ 用于实现关键的非互易耦合，其定义见 (b)；接地元件 $( L _ { 0 } , R _ { 0 } , C _ { 0 , r , n } )$ 模拟格点的在位势; $X$ 相关模块和开关控制边界条件的模拟．下图: $X$ 相关模块的定义．(b)INIC 元件的内部电路图，由理想放大器、阻抗 $Z _ { \pm }$ 和目标元件 $C _ { I }$ (没有 $X _ { b }$ ）构成，可以实现 $V _ { l , r }$ 两端不同方向的导纳不同; $\mathrm { I N I C } _ { b }$ 仅需将INIC 中的目标元件 $C _ { I }$ 再并联一个 $X _ { b }$ 即可.(c)负阻抗模块[49]．左右图分别实现对地单端口和自由两端口间的等效负阻抗 $- Z$ ，其中理想放大器上的标记表示输出电压与输入电压的关系．各元件的具体功能描述详见正文.

![](images/8f1cb9bf2da897f3980b502ab36d456f9aa355b671e50ac92596a9567777d447.jpg)

Fig.1.(a) Upper panel: Sketch of an electrical circuit simulating the nonreciprocal AA model.It includes $N$ voltage nodes $V _ { n }$ $( n = 1 , \cdots , N )$ with elements $C _ { 0 }$ and $\mathrm { I N I C } _ { ( b ) }$ simulating the intersite couplings,where $\mathrm { I N I C } _ { ( b ) }$ defined in (b) is the key element to realize the nonrecprocity,and the grounded elements $( L _ { 0 } , R _ { 0 } , C _ { 0 , r , n } )$ simulating the on-site potentials; $X$ modules and the switches control the simulation of boundary conditions.Lower panel: Definitions of $X$ modules.(b）The internal circuit of the INIC,constructed by the ideal operational amplifier (opamp),impedance elements $Z _ { \pm }$ ,and the targeted element （204号 $C _ { I }$ (without $X _ { b }$ ),which can realize unequal effective input inductances from the two different ports $V _ { l , r }$ ; INIC $^ { b }$ is defined by adding an extra $X _ { b }$ module in parallel with $C _ { I }$ in INIC. (c) Modules of negative impedance [49]. The internal circuits of the grounded one-port and the floated two-port negative impedances $- Z$ for the left and right panels,respectively,where the labels oftheidealopampsrepresenttherelationoftheoutput voltagetothe inputvoltages.Seerelevant textsforthedetailed description of each element.

RLC 和INIC 等元件组成,包含有 $N$ 个有效电压节点，对应模拟模型的 $N$ 个格点.根据方程 (8),容易写出此电路的拉普拉辛矩阵:

$$
\mathcal { I } ( \omega ) = - i \omega \left( \begin{array} { c c c c c } { - C _ { 1 } } & { C _ { 0 } - C _ { I } } & { 0 } & { X _ { R } } \\ { C _ { 0 } + C _ { I } } & { - C _ { 2 } } & { C _ { 0 } - C _ { I } } & & \\ & { \ddots } & { \ddots } & { \ddots } & \\ & & { C _ { 0 } + C _ { I } } & { - C _ { N - 1 } } & { C _ { 0 } - C _ { I } } \\ { X _ { L } } & & { 0 } & { C _ { 0 } + C _ { I } } & { - C _ { N } } \end{array} \right) + \left[ i \omega ( 2 C _ { 0 } + C _ { r } ) + \frac { 1 } { i \omega L _ { 0 } + C _ { r } } \right] \sin \left( \left( \frac { \omega + 2 C _ { 0 } + C _ { r } } { 2 } \right) \right) ,
$$

其中，

$$
X _ { R / L } = C _ { 0 } \pm C _ { I } - ( \omega ^ { 2 } L _ { a } ) ^ { - 1 } \mp ( \omega ^ { 2 } L _ { b } ) ^ { - 1 } + ( i \omega R _ { a } ) ^ { - 1 } \pm ( i \omega R _ { b } ) ^ { - 1 } ,
$$

电容 $C _ { n , I }$ 、电感 $\textstyle L _ { a , b }$ 、电阻 $R _ { a , b }$ 和 $R _ { 0 }$ 在图1中定义, $\mathcal { E }$ 为单位矩阵;边界条件由图1(a)中 $X$ 相关模块与开关控制：当两端的开关同时接入端口 $\mid o \mid$ 并且 $X$ 相关模块 $( X _ { a , b }$ 和 $X _ { l , r } \big |$ ）均开路时，系统对应于开边界条件；当两端的开关同时接入端口 $p$ 时，下文中将会看到,通过 $X$ 相关模块参数的调节可以模拟具有磁通的周期边界条件.

将此电路的拉普拉辛矩阵(15)与非互易AA 模型的哈密顿量矩阵(2）相比较，可以建立除 $\mathcal { D }$ (正比于单位矩阵 $\mathcal { E }$ ）外两者间的映射 $\mathcal { A } \Leftrightarrow \mathcal { H }$ ，并利用对应的无量纲化参数得到如下等式关系，

对于电路的主体部分 (不包含边界)，由

$$
\frac { C _ { 0 } + C _ { I } } { C _ { 0 } - C _ { I } } = e ^ { 2 \alpha } \ , \frac { - C _ { n } } { C _ { 0 } + C _ { I } } = \frac { 2 \lambda \cos ( 2 \pi \beta n ) } { e ^ { \alpha } } ,
$$

可得

$$
\frac { C _ { I } } { C _ { 0 } } = \operatorname { t a n h } \alpha , \frac { C _ { n } } { C _ { 0 } } = - \frac { 2 \lambda \cos ( 2 \pi \beta n ) } { \cosh \alpha } ,
$$

这里将 $C _ { 0 }$ 作为参考电容．由此可以理解电路主体各元件的作用： $( C _ { 0 } , C _ { r } , L _ { 0 } )$ 构成紧束缚模型的整体参考势（ $\mathbf { \bar { \nabla } } _ { \mathcal { D } }$ 部分）， $C _ { 0 }$ 还承担格点间互易耦合的作用，非互易耦合和变化的在位势由INIC 中的电容 $C _ { I }$ 和接地电容 $C _ { n }$ 分别实现；随后可以看到，电阻 $R _ { 0 }$ 和电容 $C _ { r }$ 的引入是为了使电路的响应不发散，它们仅使导纳谱在复平面内作整体平移．需注意的是, $C _ { n }$ 随着节点 $n$ 的变化会被要求为负数，等效负电容可以使用图1(c)的方案实现.

对于边界部分，同样利用对应的无量纲化参数关系

$$
\frac { X _ { R } + X _ { L } } { 2 C _ { 0 } } = \frac { e ^ { \alpha } e ^ { - i \Phi } + e ^ { - \alpha } e ^ { i \Phi } } { e ^ { \alpha } + e ^ { - \alpha } } , \qquad \frac { X _ { R } - X _ { L } } { 2 C _ { I } } = \frac { e ^ { \alpha } e ^ { - i \Phi } - e ^ { - \alpha } e ^ { i \Phi } } { e ^ { \alpha } - e ^ { - \alpha } } ,
$$

可得

$$
\frac { L _ { a } } { L _ { 0 } } = \frac { \omega _ { 0 } ^ { 2 } } { \omega ^ { 2 } ( 1 - \cos \Phi ) } , L _ { b } = L _ { a } \coth \alpha ; \frac { R _ { b } } { R _ { 0 } } = \frac { \omega _ { 0 } \gamma } { \omega \sin \Phi } , R _ { a } = R _ { b } \coth \alpha .
$$

这里将 $L _ { 0 }$ 和 $R _ { 0 }$ 分别作为参考电感和参考电阻， $\omega _ { 0 } \equiv 1 / \sqrt { L _ { 0 } C _ { 0 } }$ 作为参考频率,并定义无量纲量 $\gamma \equiv R _ { 0 } ^ { - 1 } \sqrt { L _ { 0 } C _ { 0 } ^ { - 1 } }$ 当 $\Phi$ 为 $2 \pi$ 的整数倍时, $\boldsymbol { L } _ { a , b }$ 和 $R _ { a , b }$ 均发散，代表开路，对应于无磁通的周期边界条件．随着 $\Phi$ 的变化, $R _ { a , b }$ （20会为负数，同样可以使用图1(c)方案实现.

# IV．周期边界条件下能谱和缠绕数的模拟

众所周知，即使在周期边界条件下，无序系统也不再具有平移不变性，因而无法通过将哈密顿量变换到动量空间的方法计算系统的缠绕数，而通常的办法是在链环中心加入磁通量为 $\Phi$ 的磁场，此时系统变为 $\Phi$ 的周期函数(周期为 $2 \pi$ )，从而进行计算．对于非厄米系统，由于能量一般为复数，可以定义复能量在复平面的缠绕数来刻画非厄米系统的拓扑相[17,27]：

$$
\nu = \int _ { 0 } ^ { 2 \pi } \frac { \partial _ { \Phi } \ln \operatorname* { d e t } \mathcal { H } ( \Phi ) } { 2 \pi i } d \Phi = \int _ { 0 } ^ { 2 \pi } \frac { \partial _ { \Phi } \ \theta ( \Phi ) } { 2 \pi } d \Phi ,
$$

其中, $\theta ( \Phi )$ 是 $\operatorname* { d e t } \mathcal { H } ( \Phi )$ 的幅角．对于非互易 AA 模型，由文献 [27]可知，不同的缠绕数表示不同的拓扑相：在周期边界条件下, $\nu = 0$ 表示拓扑平庸的局域相， $\nu = \pm 1$ 表示两种拓扑非平庸的扩展相.

为了通过电路模拟并测量非互易AA模型的缠绕数 $\nu$ ，利用两者的对应关系可以将定义(21）中的 $\mathcal { H }$ 用拉普拉辛矩阵(15）中的 $\mathcal { A } / C _ { 0 }$ 替换 (这里除以 $C _ { 0 }$ 是为了保证 $\ln$ 等函数的作用对象是无量纲的，整体的倍数并不会影响 $\nu$ 的结果)．因此，只要能从实验上测量出不同 $\Phi$ 下的 $\mathcal { A } ( \Phi )$ 矩阵，即可计算出相应的缠绕数，

![](images/fd61a476e0452fa9a39eaf5f813b01d91987c88924dde21491da24779d09e219.jpg)

图2．(a)非互易AA 模型的参考相图，相边界(红色实线）由文献 [27]附录中的解析表达式(B6)计算缠绕数 $\nu$ 求得．虚线用于 图3的计算.(b,c)分别对应(a)中B、C两点的电路本征频率谱（取 $\gamma = 0$ 时)(左图)以及矩阵 $\mathcal { A } / C _ { 0 }$ 的本征谱 (取 $\Phi = 0$ 时) (右图)．红色实点和蓝色实方块分别代表周期和开边界条件下的理论结果．左图中的空心菱形标记驱动频率 $\omega$ 的位置，右图中的空 心菱形表示周期边界条件下 SPICE 的模拟结果.(d）根据 SPICE 模拟得到的 $\mathcal { A } ( \Phi )$ 计算得出 $\theta ( \Phi ) = \ln \operatorname* { d e t } \left[ \mathcal { A } ( \Phi ) / C 0 \right]$ 随 $\Phi$ 的 变化．左向三角、右向三角和菱形分别对应(a)中 A、B 和C 三点，虚线为相应的理论值．以上所有计算取有限尺寸 $N = 2 1$ ，电 路元件的具体设置参见相关正文.   
Fig.2.(a)Referenced phase diagramof the non-reciprocal AA model,wherephase boundaries (solidred lines)areobtained by calculating the winding number $\nu$ with Eq. (B6) in the Appendix of Ref. [27]. The dashed lines are for the plots in Fig. 3. (b,c） The eigenfrequencies of the circuit at $\gamma = 0$ (left panels） and the eigenvalues of $\mathcal { A } / C _ { 0 }$ at $\Phi = 0$ (right panels). Solidreddots and solid blue squares represents the theoretical resultsunder PBCsand OBCs,respectively.Thehollow diamonds inleft panelslbel thedriving frequency,andthose inright panelsare thesimulatedresultsunder PBCs via SPICE. (d) $\theta ( \Phi ) = \ln \operatorname* { d e t } \left[ A ( \Phi ) / C 0 \right]$ versus $\Phi$ based on the simulated $\mathcal A ( \Phi )$ via SPICE,where left-pointing triangles, right-pointing triangles，and solid diamondsrepresent pointsA,B,and Cin(a)，respectively.Thedashed linesare thecorresponding theoretical results.All figures are calculated in a finite size $N = 2 1$ . See relevant texts for the specific setting of the circuit's elements.

本文利用电路的格林函数形式(9)进行 SPICE 模拟．对于具有周期边界(将图1所示电路两端的开关均置到 $p$ 端口）的电路，仅在第 $n$ 节点接入频率为 $\omega$ 的 AC 电流源,测量所有 $N$ 个节点的电压响应，并除以输入电流强度，即可得到电路的格林函数矩阵 $\mathcal { G } ( \omega )$ 的第 $n$ 列矩阵元；每个节点均操作一次，便可得到整个电路的格林函数矩阵．然后根据关系 $\mathcal { I } ( \omega ) = \mathcal { G } ^ { - 1 } ( \omega )$ 得出拉普拉辛矩阵以及相应的矩阵 $\mathcal { A }$ [63]．得到实验测量的拉普拉辛矩阵 $\mathcal { I } ( \omega )$ ，就可以计算其导纳谱及相应的左/右本征矢量，以及由此定义的一切物理量，从而和理论相比较，

需要注意的是，上述分析是基于电路系统在AC 电流驱动下的稳态响应，即式(7)．而事实上，在驱动频率接近本征频率时，除了会产生明显的共振响应外，还会激发电路系统的其他本征模式，这类响应通常被称为暂态响应．实验上获得稳态响应的方法一般是进行延时测量，待暂态响应消逝后再使用锁相放大器 (lock-in amplifer)实现对稳态响应信号的捕捉．而在周期边界条件下，非互易AA 模型的本征能量会出现复数，相应地，此电路的本征频率 $\omega _ { c }$ 一般也为复数[图 $\mathbf { \pi } _ { 2 ( \mathrm { b , c } ) }$ 左图]，这就意味着此频率下的暂态响应会随着时间发散 $\left( \mathrm { I m } [ \omega _ { c } ] < 0 \right)$ 或衰减 $\left( \mathrm { I m } [ \omega _ { c } ] > 0 \right) ,$ ．对于以频率 $\boldsymbol { \omega } \in \mathbb { R }$ 为驱动频率的系统，发散的产生不利于系统响应的稳定，因此必须考虑对暂态响应的抑制，这里通过选取合适的 $R _ { 0 }$ 达到此目的.

可以采用无磁通（ $\mathbf { \Phi } \cdot \mathbf { \Phi } \Phi = 0 .$ ）的电路（此时的 $\mathcal { A }$ 与 $\omega$ 无关）计算本征频率的虚部，从而估算出所需要的 $R _ { 0 }$ .将公式 $\mathcal { I } ( \omega _ { c } ) \nu = 0$ 写成本征方程的形式

$$
\frac { \mathcal { A } } { C _ { 0 } } \mathcal { V } = \Big [ ( 2 + r ) - \frac { \omega _ { 0 } ^ { 2 } } { \omega _ { c } ^ { 2 } } - i \gamma \frac { \omega _ { 0 } } { \omega _ { c } } \Big ] \mathcal { V } ,
$$

可以求出本征频率 $\omega _ { c }$ 满足

$$
\frac { \omega _ { c , n } } { \omega _ { 0 } } = \Bigg ( - \frac { i \gamma } { 2 } \pm \sqrt { \left( 2 + r \right) - a _ { n } - \frac { \gamma ^ { 2 } } { 4 } } \Bigg ) ^ { - 1 } ,
$$

其中， $r = C _ { r } / C _ { 0 }$ ：， $\textstyle { a _ { n } }$ 表示矩阵 $\mathcal { A } / C _ { 0 }$ 的第 $n$ 个本征值，在周期边界条件下一般为复数[27]．因此，只要选取合适的 $R _ { 0 }$ 以及 $C _ { r }$ 使所有本征频率的虚部都不小于0，即 $\mathrm { m i n } _ { n } ( \mathrm { I m } [ \omega _ { c , n } ] ) \geq 0$ ，则系统的响应不会随时间发散．当系统以特定频率 $\omega$ 驱动时，系统的稳定响应将以 $\omega$ 模式为主[27]．根据附录的推导A，可以得出使电路响应不发散的条件为

$$
\gamma \geq \operatorname* { m a x } _ { n } \left( { \frac { | \mathrm { I m } [ a _ { n } ] | } { { \sqrt { 2 + r - \mathrm { R e } [ a _ { n } ] } } } } \right) .
$$

另外，为了尽可能多地诱导出本征模式，驱动频率需要处于本征谱中间．由于非互易 AA 模型 $\mathcal { H }$ 的能谱分布于复平面的原点附近，相应地，矩阵 $\mathcal { A } ( \Phi = 0 ) / C _ { 0 }$ 的本征值 $\textstyle { a _ { n } }$ 也具有同样的特点，所以根据式 (23)，设$\gamma = a _ { n } = 0$ 可以得到合适的驱动频率 $\omega = \omega _ { 0 } / \sqrt { 2 + r }$ 。这样的取值同时可以保证公式（15）中 $\begin{array} { r } { \mathcal { D } = R _ { 0 } ^ { - 1 } \mathcal { E } } \end{array}$ 尽可能简洁．除特别说明外，以下计算保持 $\omega = \omega _ { 0 } / \sqrt { 2 + r }$ 的取值.

利用 SPICE 模拟周期边界条件下含有 $N = 2 1$ 个节点的电路[图1(a)],基本的元件取值为 $( L _ { 0 } , C _ { 0 } , R _ { 0 } , C _ { r } ) =$ $( 1 0 \mu \mathrm { H } , 0 . 4 \mu \mathrm { F } , 5 \Omega , 1 . 6 \mu \mathrm { F } )$ ，即 $\omega _ { 0 } = 0 . 5 \mathrm { M H z }$ 和 $( r , \gamma ) = ( 4 , 1 )$ ，驱动频率选为 $\omega = \omega _ { 0 } / \sqrt { 6 } \approx 0 . 2 \mathrm { M H z }$ ，其他元件的取值 $( C _ { I } , C _ { n } , L _ { a , b } , R _ { a , b } )$ 根据公式(18)和(20）由模型参数确定，准周期势的周期参数选为 $\beta = 1 3 / 2 1$ .利用以上方案，对理论相图[图 $2 ( \mathrm { a } ) ]$ 中的三个典型区域进行 SPICE 模拟．在 $\nu = \pm 1$ 的拓扑区，模拟的 $\mathcal { A } / C _ { 0 }$ 本征谱在复平面内是绕原点的圈[图2(b)右图]，而在缠绕数 $\nu = 0$ 的局域区,则变成了实轴上的直线[图2(c)右图]；用模拟得到的 $\mathcal { A } ( \Phi ) / C _ { 0 }$ 计算相位 $\theta ( \Phi ) = \operatorname* { d e t } A ( \Phi ) / C _ { 0 }$ 随 $\Phi$ 的变化[图2(d)]，可以得到相应缠绕数的模拟值．结果显示，模拟结果与理论结果吻合得很好.

# V．开边界条件下趋肤与局域模式竞争的模拟

文献 [27]里证明了非互易AA模型在开边界与周期边界条件下的相图一致，只是拓扑相区的态在开边界条件下表现出趋肤态，而在周期边界条件下表现为扩展态．本节将同样利用电路的拉普拉辛方法模拟开边界条件下趋肤与局域模式的竞争.

在电路的设计上，只需要将图1(a）中两端的开关同时接入端口 $\mathbf { \xi } _ { o }$ 并且令 $X$ 相关模块均开路，即可实现开边界条件．同样地，可以利用与上一节周期边界条件类似的方法，通过 SPICE 模拟重构出开边界条件下的电路拉普拉辛矩阵以及相应的矩阵 $\mathcal { A } / C _ { 0 }$ ，然后用此矩阵计算出相应的本征左/右矢，即可看到趋肤和局域模式在不同参数下的竞争关系．这里将采用一个相对简单的方法，无须将AC 电流源依次接入每个节点也可以达到此目的

![](images/6ae6c2dbe02a58735d645f77003819b395278e05ba88c7abbc06877a82f4c10a.jpg)

图3．(a,b）由 SPICE 模拟得到的电压响应(已经归一化)在节点上的分布,分别对应图 2(a）中 $\alpha = 0 . 5$ 和 $\lambda = 0 . 5$ 的两条虚线.频率为 $\omega = \omega _ { 0 } / \sqrt { 6 }$ 的AC 电流源接在第11个节点上.(c,d)分别由(a,b)中的电压分布根据公式(26)计算的 IPR,其中菱形为模拟值，虚线为理论值．箭头指的是最小模拟值，虚线标出的是理论相变值.

Fig.3.(a,b) Node distributions of voltages (normalized) simulated by SPICE along dashed lines of $\alpha = 0 . 5$ and $\lambda = 0 . 5$ in Fig. 2(a), respectively. The AC current source with $\omega = \omega _ { 0 } / \sqrt { 6 }$ is connected to the 1lth node.(c,d) IPRs of the voltage distributionsin(a,b),respectively,calculatedbyEq.(26),wherediamonds (dashedlines)arethesimulation (theoretical) results.The arrows indicate the minima ofsimulated IPRs,while the dashed lines indicate the phase transition points in theory.

电路的格林函数形式 (9)可以用拉普拉辛的本征左/右矢表示为

$$
\mathcal { V } = \mathcal { G } ( \omega ) \mathcal { T } = \sum _ { n } \frac { [ \psi _ { n } ^ { ( l ) } ( \omega ) ] ^ { \dagger } \mathcal { T } } { j _ { n } ( \omega ) } \psi _ { n } ^ { ( r ) } ( \omega ) ,
$$

这里，趋肤或局域模式表现为本征左/右矢矩阵元的分布是趋向于一端还是局域在某个中间位置．可以简单地在单一节点接入AC 电流源,测量相应的电压响应，根据上式可知，此电压响应是同一相区下所有本征右矢 $\psi _ { n } ^ { ( r ) } ( \omega )$ 按系数 $j _ { n } ^ { - 1 } ( \omega ) [ \psi _ { n } ^ { ( l ) } ( \omega ) ] ^ { \dagger } \mathcal { T }$ 线性叠加的结果，所以必然表现为趋肤或局域效应.

取与周期边界条件时相同的元件参数，除了 $\gamma = 0$ （即 $R _ { 0 }$ 开路)，这是因为开边界条件下所有的本征频率都是实数，如图 $\scriptstyle 2 ( \log , \mathrm { c } )$ 所示，不存在响应发散的问题，所以不需要用电阻抑制发散．另外，需要拉普拉辛矩阵中的$\mathcal { D } ( \omega ) = 0$ ，否则当此项很大时，所有本征值 $j _ { n } ( \omega )$ 趋向于常数 $j$ ，由公式（25）可知 $\mathcal { V }  j ^ { - 1 } \mathcal { T }$ 。其正比于输入电流，无法反映出竞争关系，这也是取 $\gamma = 0$ 的一个原因.

用 SPICE 同样模拟了开边界条件下 $N = 2 1$ 个节点的电路系统,在节点 $n _ { i } = 1 1$ 接入频率为 $\omega = \omega _ { 0 } / \sqrt { 6 }$ 的AC 电流源，然后测量每个节点频率为 $\omega$ 的电压幅值，得到如图3(a）和3(b)所示结果，清楚地显示在拓扑相区时，响应电压分布在右/左边界附近，表现为右/左趋肤态；在非拓扑相区时，响应电压始终分布在驱动节点附近，表现为局域态.为了表征相应电压的局域化程度，定义倒参与率 (inverse participationratio,简称 IPR):

$$
\mathrm { I P R } = \big ( \sum _ { n } | V _ { n } | ^ { 4 } \big ) \Big / \big ( \sum _ { n } | V _ { n } | ^ { 2 } \big ) ^ { 2 } .
$$

图3(c)和3(d)显示 IPR 最低的点与理论相变点很接近，因为趋肤和局域态都有较大的局域性，对应较大的 IPR值，而相变点附近扩展性最强，对应的 IPR 值都很小．在左右趋肤的相边界（即 $\nu = \pm 1$ 之间的边界),对应于互易模型，因为趋肤效应消失，所以其本征态为扩展态；在趋肤与局域的相边界（即 $\nu = \pm 1$ 与 $\nu = 0$ 之间的边界),对应于趋肤与局域竞争的平衡，同样为扩展态.

# VI．总结

本文通过构建经典电路，将其拉普拉辛矩阵与非互易 AA 模型的哈密顿量矩阵对应，利用 SPICE 成功模拟了非互易AA 模型重要的稳态性质，包括周期边界条件下体现系统非厄米拓扑性质的复能谱和能谱缠绕数，以及开边界下非厄米趋肤效应与准无序局域化的竞争．其中，详细讨论了电路参数的设置原则和理论依据，为进一步的实验实现提供了具体的指导方案：由于方案的普适性，本文中所讨论的设计原则和理论可以直接应用于其他量子紧束缚模型的模拟和实验，比如文献 [27]中提到的非互易 AA 模型的对偶模型，仅需将图1中的电路方案适当修改，去除节点间的INIC 元件以实现互易跃迁，并调节相应的接地元件以实现准周期复在位势即可.

本文中的 SPICE 模拟使用了LTspice 软件．为了更接近于理论结果，这里采用的电容、电感和电阻均为理想线性器件，并且将INIC 中放大器的开环增益倍数与输入阻抗分别设置为 $5 0 0 \mathrm { G }$ 和 $5 0 0 \mathrm { G } \Omega$ 用于模拟理想放大器．由于实际器件的非理想性，模拟或者实验结果可能会有一定偏差，需要根据情况具体分析.

本文只涉及对量子紧束缚模型稳态性质的模拟，实际上，经典电路也可以用于对动力学性质的模拟．对于非互易AA模型，文献[27]已有讨论．另外，由于电路元件的丰富特性，同样可以利用非线性的电路元件实现对非线性量子系统的模拟[64]．所以，对于模拟量子系统而言，经典电路是一个成本低廉、技术成熟、模拟范围广的有力平台.

# 致谢

本文为国家自然科学基金(批准号：11904109)和广东省基础与应用基础研究基金(批准号：2019A1515111101)资助的课题.

Project supported by the National Natural Science Foundation of China (Grant No.11904109) and the Guangdong Basic and Applied Basic Research Foundation (Grant No. 2019A151511101).

# 附录A：电路响应不发散的条件

根据本征频率的表达式 (23)，如使电路响应不发散,需要满足 $\mathrm { I m } [ \omega _ { c } ^ { ( n ) } / \omega _ { 0 } ] \ge 0$ ，即

$$
\begin{array} { r l } & { 0 \geq 2 \mathrm { I m } [ - \frac { i \gamma } { 2 } + \sqrt { ( 2 + r ) - a _ { n } - \frac { \gamma ^ { 2 } } { 4 } } ] = - \gamma - \sqrt { \frac { \gamma ^ { 2 } } { 4 } - ( 2 + r ) + a _ { n } } - [ \sqrt { \frac { \gamma ^ { 2 } } { 4 } - ( 2 + r ) + a }  } \\ & { \qquad \Rightarrow \quad - \gamma \leq \sqrt { \frac { \gamma ^ { 2 } } { 4 } - ( 2 + r ) + a _ { n } } + [ \sqrt { \frac { \gamma ^ { 2 } } { 4 } - ( 2 + r ) + a _ { n } } ] ^ { * } , } \end{array}
$$

这里将根式 $\sqrt { \cdot }$ 整体看作复数，由于不等式左边为非正数 $( \gamma \geq 0 )$ ，所以只需考虑不等式右边 (为根式的两倍实部)为非正数时满足的条件即可．因此，将不等式(A1)两边平方并化简，得

$$
\frac { \gamma ^ { 2 } } { 4 } + \left( 2 + r \right) - \frac { a _ { n } + a _ { n } ^ { * } } { 2 } \geq \sqrt { \frac { \gamma ^ { 2 } } { 4 } - \left( 2 + r \right) + a _ { n } } \left[ \sqrt { \frac { \gamma ^ { 2 } } { 4 } - \left( 2 + r \right) + a _ { n } } { \right] ^ { * } } ,
$$

两边再平方并化简，得

$$
( 2 + r - \mathrm { R e } [ a _ { n } ] ) \gamma ^ { 2 } \geq ( \mathrm { I m } [ a _ { n } ] ) ^ { 2 } .
$$

由于不等式右方为非负数，所以必须要求

$$
2 + r - \mathrm { R e } [ a _ { n } ] \geq 0 \Rightarrow r \geq \mathrm { R e } [ a _ { n } ] - 2 ,
$$

且

$$
\gamma \geq | \mathrm { I m } [ a _ { n } ] | / \sqrt { 2 + r - \mathrm { R e } [ a _ { n } ] } .
$$

因为需保证所有本征频率都满足以上条件，所以要求

$$
r \geq \operatorname* { m a x } _ { n } ( \operatorname { R e } [ a _ { n } ] ) - 2 \textup { \AA } \gamma \geq \operatorname* { m a x } _ { n } \Bigg ( \frac { | \mathrm { I m } [ a _ { n } ] | } { \sqrt { 2 + r - \mathrm { R e } [ a _ { n } } ] } \Bigg ) .
$$

[1]Y.Ashida,Z.Gong，andM.Ueda,AdvancesinPhysics69,249(2020),https://doi.org/10.1080/0018732.2021.1876991.   
[2] A.J.Daley,Advances in Physics 63,77 (2014),https://doi.org/10.1080/00018732.2014.933502. [3] N. Moiseyev,Non-Hermitian Quantum Mechanics,lst ed. (Cambridge University Pres, Cambridge, 2011). [4] C.MBender and S.Boettcher,Phys.Rev.Lett.80,5243(1998).   
[5]A.Guo，G.J. Salamo,D.Duchesne,R.Morandoti，M. Volatier-Ravat，V.Aimez,G.A.Siviloglou，and D.N. Christodoulides,Phys.Rev.Lett.103,093902 (2009). [6] B.Peng,S.K.Ozdemir,F.Lei,F.Monif,M.Gianfreda,G.L.Long,S.Fan,F.Nori, C.M.Bender，andL.Yang,Nat. Phys.10,394 (2014).   
[7] C.Poli, M. Bellec,U.Kuhl,F.Mortessagne,and H. Schomerus,Nature Communications 6,6710 (2015).   
[8] J.Li,A.K.Harter,J.Liu,L.de Melo, Y.N.Joglekar，and L.Luo,Nature Communications 10,855 (2019). [9] Z.Ren,D.Liu,E.Zhao,C.He,K.K.Pak,J.LiandG.-B.JoarXive-prints,arXiv:2106.04874(2021),arXiv:2106.04874 [cond-mat.quant-gas].   
[10]M.-A.MiriandA.Alu,Science 363,eaar7709 (2019),https://www.science.org/doi/pdf/10.1126/scienceaar7709.   
[11] E. J. Bergholtz, J.C. Budich，and F.K.Kunst,Rev. Mod. Phys. 93,015005 (2021).   
[12] X.-L. Zhang, T. Jiang，and C. T. Chan, Light: Science & Applications 8,88 (2019).   
[13] T.E.Lee,Phys.Rev.Lett.116,133903 (2016).   
[14] D.Leykam, K. Y. Bliokh, C. Huang,Y. Chong，and F. Nori,Phys. Rev. Lett.118,040401 (2017). [15] H. Shen,B. Zhen，and L.Fu, Phys.Rev.Lett.120,146402 (2018).   
[16] S. Yao and Z. Wang, Phys.Rev. Lett. 121,086803 (2018).   
[17] Z. Gong, Y.Ashida,K. Kawabata,K. Takasan,S. Higashikawa,and M. Ueda,Phys.Rev.X 8,031079 (2018).   
[18] Y. Xiong, J. Phys. Commun. 2, 035043 (2018).   
[19] F.K.Kunst,E. Edvardssn,J. C.Budich，and E.J. Bergholtz,Phys. Rev. Lett.121,026808 (2018).   
[20] V.M. Martinez Alvarez,J. E.Baros Vargas,and L.E.F.Foa Torres,Phys.Rev.B97,121401(R)(2018).   
[21] C.Yin, H. Jiang,L.Li, R. Lu,and S.Chen, Phys. Rev.A 97,052115 (2018).   
[22] L. Jin and Z. Song, Phys. Rev. B 99,081103 (2019).   
[23] C.H. Lee and R. Thomale, Phys. Rev. B 99, 201103 (2019).   
[24] K. Zhang, Z. Yang，and C. Fang,Phys. Rev. Lett.125,126402 (2020).   
[25] Z. Yang,K. Zhang,C. Fang，and J. Hu,Phys. Rev. Lett.125, 226402 (2020).   
[26]K.YokomizoandS.Murakami,Progresof TheoreticalandExperimental Physics202 (2020),0.193/ptep/ptaa40, 12A102, https://academic.oup.com/ptep/article-pdf/2020/12/12A102/35611788/ptaa140.pdf.   
[27] H. Jiang,L.-J. Lang,C. Yang, S.-L. Zhu, and S. Chen, Phys. Rev. B 100,054301 (2019).   
[28] S.Longhi,Phys.Rev.Lett.122,237601 (2019).   
[29] Q.-B. Zeng,Y.-B. Yang,and Y. Xu,Phys.Rev. B 101,020201 (2020).   
[30]D.-W.Zhang,L.-Z.Tang,L.-J.Lang,H.Yan,andS.-L.Zhu,Science ChinaPhysics,Mechanics&Astronomy63,267062 (2020).   
[31] Z.-H.Xu, X. Xia,and S. Chen,Science China Physics,Mechanics & Astronomy 65, 227211 (2021).   
[32] Y. Liu, Y. Wang,X.-J. Liu, Q. Zhou, and S. Chen, Phys. Rev. B 103,014203 (2021).   
[33]Q.Lin,T.Li,L. Xiao,K.Wang,W.YiandP.Xue,arXive-prints,arXiv:2112.15024(2021),arXiv:212.15024condmat.mes-hall.   
[34] S. Mu, C.H. Lee,L. Li, and J. Gong,Phys.Rev. B 102,081115 (2020).   
[35] D.-W. Zhang,Y.-L.Chen, G.-Q. Zhang,L.-J.Lang,Z.Li，and S.-L. Zhu,Phys.Rev.B101,235150 (2020).   
[36] Z. Xu and S. Chen, Phys. Rev. B 102,035153 (2020).   
[37] E.Lee,H. Lee,and B.-J. Yang,Phys. Rev.B 101,121109 (2020).   
[38] T.Liu, J. J. He, T. Yoshida, Z.-L. Xiang，and F. Nori,Phys. Rev. B 102, 235151 (2020).   
[39] Z. Wang,L.-J. Lang,and L. He, Phys.Rev. B 105,054315 (2022).   
[40]W.Gou,T.Chen,D.Xie,T.Xiao,T.-S.Deng,B.Gadway,W.Yi,andB.Yan,Phys.Rev.Let.124,070402 (2020).   
[41] J.M. Zeuner,M. C.Rechtsman, Y.Plotnik,Y.Lumer,S.Nolte,M.S.Rudner,M.Segev,andA.Szameit,Phys.Rev.   
Lett.115, 040402 (2015).   
[42] S.Weimann,M.Kremer,Y.Plotnik,Y.Lumer,S.Nolte,K.G.Makris,M.Segev,M.Rechtsman,andA.Szameit,Nature Materials 16, 433 (2017).   
[43] X.-Y.Zhu,S.K.Gupta,X.-C.Sun,C.He,G.-X.Li,J.-H.Jiang,M.-H.Lu,X.-P.Liu,andY.-F.Chen,arXive-pints, arXiv:1801.10289 (2018),arXiv:1801.10289 [physics.optics].   
[44]A. Cerjan, S. Huang,M. Wang,K.P.Chen,Y. Chong, and M. C.Rechtsman, Nature Photonics 13,623 (2019).   
[45]K.Wang，A.DuttK.Y. Yang，C.C.Wojcik，J.Vuckovic,and S. Fan，Science 371，1240 (2021), https://www.science.org/doi/pdf/10.1126/science.abf6568.   
[46] M. Brandenbourger, X. Locsin, E. Lerner， and C. Coulais, Nat. Comm. 10, 4608 (2019).   
[47]A. Ghatak,M.Brandenbourger,J.van Wezel，and C. Coulais,Proc. Natl. Acad.Sci. U.S.A.117,29561 (2020).   
[48]F.Y.Wu, Journal of Physics A: Mathematical and General 37, 6653 (2004).   
[49] J.Schindler,Z.Lin,J.M.Lee,H.Ramezani,F.M.Elis，and T.Kottos,Journalof Physics A: Mathematical and Theoretical 45, 444029 (2012).   
[50]T.Helbig,T.Hofmann,S.Imhof,M.Abdelghany,T.Kiessling,L.W.Molenkamp,C.H.Le,A.Szameit,M.Greiter, and R. Thomale, Nature Physics 16,747 (2020).   
[51] L.-J. Lang, Y. Weng, Y. Zhang, E. Cheng，and Q. Liang,Phys.Rev. B 103,014302 (2021).   
[52] M.Ezawa,Phys.Rev.B 100,081401 (2019).   
[53] T.Hofmann,T.Helbig, C.H.Lee,M.Greiter，and R.Thomale,Phys.Rev.Lett.122, 247702 (2019).   
[54] M.Ezawa,Phys.Rev.B 99,121411 (2019).   
[55] D. Zou,T.Chen,W.He,J.Bao, C.H. Lee,H.Sun，and X. Zhang,Nature Communications 12,7201 (2021).   
[56] X.-X. Zhang and M. Franz, Phys.Rev. Lett.124, 046401 (2020).   
[57]S.M.Raf-Ul-Islam,Z.B.Siu，and M.B.A.Jalil,arXive-prints,arXiv:2102.03727(2021),arXiv:2102.03727[condmat.mes-hall].   
[58] W.J. Tzeng and F. Y.Wu, Journal of Physics A: Mathematical and General 39,8579 (2006).   
[59]C.H.Lee,S.Imhof, C.Berger,F.Bayer,J.Brehm,L.W.Molenkamp,T.Kiessing，andR.Thomale,Communications Physics 1,39 (2018).   
[60] Y. Hadad, J. C. Soric,A. B.Khanikaev, and A. Alu, Nature Electronics 1, 178 (2018).   
[61] Y.Wang,L.-J. Lang,C.H. Lee,B. Zhang，and Y.D. Chong, Nature Communications 10,1102 (2019).   
[62] D. M. Pozar, Microwave Engineering, edited by 4th (John Wiley & Sons, Inc., 2012).   
[63]T.Helbig,T.Hofmann,C.H.L,R.Thomale,S.Imhof,L.W.Molenkamp，andT.Kiessling,Phys.Rev.B99,16114 (2019).   
[64] L.-J. Lang, S.-L. Zhu，and Y. D. Chong, Phys. Rev.B 104, L020303 (2021).