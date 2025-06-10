# 考虑DG、DS和EV协同运行的配电网无功优化方法

陈嘉威」　吴杰康²　郭清元」赵守安²　徐宏海}（1.广东电网有限责任公司东莞供电局东莞5230082.广东工业大学自动化学院广州510006）

![](images/d610e5addfb2f00b657b8a5c25636bb9938a64fd0fa5ef688b2731a510fac86d.jpg)

陈嘉威男1988年生，工程师，从事电网调度运行方面的工作。

摘要：综合考虑分布式电源、电动汽车充放电和分布式储能运行的协调配合，并与不同类型无功补偿装置输出无功功率的协同控制，以配电网有功网损及电压波动量最小化为目标函数，建立配电网无功优化的多目标优化模型。考虑风速的概率特性、日照强度的不确定性、荷电状态和充放电特性以及运行效率，构建分布式风电机组出力、光伏发电系统出力、电动汽车充放电功率以及储能装置充放电功率的随机模型。选择DG、DS 和EV等无功功率作为控制变量，采用遗传算法对优化问题进行求解。仿真计算表明了本文构建的无功优化模型的适应性和所提算法的可行性和有效性。

关键词：新能源配电网无功优化DG、DS 和EV协同运行无功补偿装置中图分类号：TM315

![](images/361bb53a7da87af05d91addd79ce804d915d7a484208713464f4aab89db7a7a4.jpg)

# Reactive Power Optimization Method for Distribution Network Considering DG, DS and EV Cooperative Operation

吴杰康男 1965年生，博士，教授，研究方向为电力系统运行与控制。

Chen JiaweilWu Jiekang²Guo Qingyuan'Zhao Shouan²Xu Honghail (1.Dongguan Power Supply Bureau Guangdong Power Grid Corporation Dongguan 523008China 2. School of Automation Guangdong University of TechnologyGuangzhou51006China ）

Abstract: A reactive power optimization model is presented considering operation coordination of distributed generation, electric vehicle charging and distributed storage systems,and coordinative control of DG,DS,EV and other different types of reactive power compensation devices in power distribution network. In the proposed model, power loss and voltage fluctuation minimization is taken as the objective function. Considering the probabilistic characteristics of wind speed,the uncertainty of sunshine intensity,charge state and charge discharge characteristics，and the operation efficiency, a stochastic probabilistic model is constructed for power output of distributed wind turbine power output of PV system, charging and discharging power of electric vehicle, and charging and discharging power of energy storage device. The reactive power of DG, DS and EV is chosen as control variable,and genetic algorithm is used to solve the optimization problem. The simulation results show the adaptability of the proposed reactive power optimization model,and the feasibility and effectiveness of the proposed algorithm.

Keywords: Distribution grids with renewable energy, reactive power optimization, coordinative operation of DG, DS and EV, reactive power compensation devices

# 1 引言

能源枯竭和环境恶化是目前世界面临的两大难题，如何开发和利用可再生能源，以及减少环境污染成为世界各国共同关注的问题。在这种环境下，分布式发电（DistributedGeneration，DG）和电动汽车（ElectricVehicle，EV）将在电力行业和汽车行业的未来发展规划中占据重要位置，渗透率将逐步提高。但大规模的DG和EV无计划接入电网会对传统的配电网造成影响[1-2]。

分布式电源、分布式储能装置（DistributionStorage，DS）和电动汽车充电站的大规模接入会对配电网运行造成很大的影响。目前，有文献对DG和EV接入配电网后如何协调运行进行了深入的研究。文献[3]介绍了一种以降损为目标的电动汽车有序充电优化方案。文献[4]提出一种基于分层控制的有序充电控制架构，在能够与传统电网控制架构融合的基础上，实现配电网范围内电动汽车和分布式可再生电源的协同有序控制。文献[5-6]建立了电动汽车和分布式发电协调控制的多目标优化模型。该模型以等效负荷率最大、节点电压越限和损耗率最小、入网服务成本和车主充电成本最低为目标，动态调节电动汽车充放电功率，能很好地匹配负荷和分布式发电的功率波动，降低分布式发电间歇性对电网的影响。文献[7-10]针对风电、光伏发电和电动汽车负荷的协同优化问题进行了研究，提出了优化模型与方法。文献[11]建立了路径选择模型与交通满意度评价模型，并研究了分布式电源的时序特性与互补性。

总之，分布式电源和电动汽车接入配电网，对节点电压和网络损耗具有一定的影响[12-16]。如何提高分布式电源和电动汽车接入配电网后电压的稳定性及减小网络损耗是目前研究中面临的难题。

本文在上述研究的基础上，考虑到分布式电源出力的随机性，通过概率潮流计算[17]，获得某一时刻的电网参数，同时，为了平衡分布式电源接入后带来的影响，系统装有储能装置和无功补偿装置，通过DS、EV、无功补偿装置以及分布式电源无功输出[18]的协调运行以满足维持节点电压稳定和减小网络损耗的要求。本文以DS、EV、无功补偿装置以及分布式电源无功输出为控制变量，建立了节点电压偏差最小和网络损耗最小两个目标函数，并使用遗传算法进行求解，最后通过IEEE33节点系统进行实例验证。

# 2 DG出力的随机概率模型

# 2.1分布式风电机组出力的随机概率模型

风速可由Weibull分布来描述[5]，其分布函数可以表示为

$$
f ( \nu ) = \frac { k } { c } \left( \frac { \nu - \nu _ { 0 } } { c } \right) ^ { k - 1 } \exp \left[ - \left( \frac { \nu - \nu _ { 0 } } { c } \right) ^ { k } \right]
$$

式中， $\nu$ 为风速； $\nu _ { 0 }$ 、k、 $\mathbf { \Psi } _ { c }$ 分别为Weibull分布曲线的位置参数、形状参数和尺度参数。

考虑风速 $\nu$ 的概率特性，得到风电机组输出功率的概率密度函数为

$$
f ( P _ { \mathrm { { w } } } ) = \left\{ \begin{array} { c c } { \displaystyle { \int _ { 0 } ^ { \nu _ { \mathrm { o } } } f ( \nu ) \mathrm { d } \nu + \int _ { \nu _ { \mathrm { o } } } ^ { \infty } f ( \nu ) \mathrm { d } \nu } } & { P _ { \mathrm { w } } = 0 } \\ { \displaystyle { \frac { k } { k _ { 1 } c } \mathrm { e x p } \Bigg [ - \left( \frac { P _ { \mathrm { { w } } } - k _ { 2 } } { k _ { 1 } c } \right) ^ { k } \Bigg ] \left( \frac { P _ { \mathrm { { w } } } - k _ { 2 } } { k _ { 1 } c } \right) ^ { k - 1 } } } & { 0 < P _ { \mathrm { w } } < P _ { \mathrm { e } } } \\ { \displaystyle { \int _ { \nu _ { \mathrm { { r } } } } ^ { \infty } f ( \nu ) \mathrm { d } \nu } } & { P _ { \mathrm { w } } = P _ { \mathrm { e } } } \end{array} \right.
$$

其中

$$
k _ { \mathrm { _ 1 } } = \frac { P _ { \mathrm { e } } } { \nu _ { \mathrm { _ r } } - \nu _ { \mathrm { _ c i } } }
$$

$$
k _ { 2 } = k _ { 1 } \nu _ { \mathrm { c i } }
$$

式中， $P _ { \mathrm { ~ e ~ } }$ 为风电机组额定功率； $\nu _ { \mathrm { c i } }$ 为切入风速； $\nu _ { \mathrm { c o } }$   
为切出风速； $\nu _ { \mathrm { r } }$ 为额定风速。

# 2.2光伏发电系统出力的随机概率模型

一段时间内太阳光强度可近似视为Beta分布，太阳能电池输出功率的概率密度函数也呈Beta分布，其密度函数为

$$
f ( P _ { \mathrm { p v } } ) { = } \frac { \Gamma ( \alpha + \beta ) } { \Gamma ( \alpha ) + \Gamma ( \beta ) } { \left( \frac { P _ { \mathrm { p v } } } { P _ { \mathrm { m a x } } } \right) } ^ { \alpha - 1 } { \left( 1 - \frac { P _ { \mathrm { p v } } } { P _ { \mathrm { m a x } } } \right) } ^ { \beta - 1 }
$$

式中， $P _ { \mathrm { P V } }$ 为太阳能发电系统输出的有功功率； $P _ { \mathrm { { m a x } } }$ 为太阳能电池方阵最大输出有功功率； $\scriptstyle { \alpha }$ ， $\beta$ 为Beta形式参数。

# 3 EV和DS充放电特性

# 3.1电动汽车充放电特性

# 3.1.1电动汽车荷电状态

电动汽车荷电状态与用户的行驶里程具有很大的关系，根据文献[19]可以得到电动汽车行驶里程与电池荷电状态 $\mathrm { s o c } _ { \mathrm { \scriptscriptstyle E V } i }$ 之间的关系为

$$
\mathrm { S O C } _ { \mathrm { E V } i , \mathrm { h } } = \mathrm { S O C } _ { \mathrm { E V } i , \mathrm { q } } - \frac { L } { M }
$$

式中， $\mathrm { S O C } _ { \mathrm { E V } i , \mathrm { q } }$ 、 $\mathrm { S O C } _ { \mathrm { E V } i , \mathrm { h } }$ 为电动汽车使用前后的荷电状态； $L$ 为电动汽车一次行驶的实际里程； $M$ 为该电动汽车充满电后可以持续行驶的最大里程。

# 3.1.2电动汽车充放电特性

由于技术限制，电动汽车的充放电功率不可能维持恒定运行，假设电动汽车在进行充放电时均以恒定功率进行，则电动汽车的充放电特性[19]可表示为

$$
\mathrm { S O C } _ { _ { \mathrm { E V i c } } } = \mathrm { S O C } _ { _ { \mathrm { E V i 0 } } } + \Delta \mathrm { S O C } _ { _ { \mathrm { E V } } } = \mathrm { S O C } _ { _ { \mathrm { E V i 0 } } } + \frac { P _ { _ { \mathrm { E V i c } } } T _ { \mathrm { c } } } { E _ { \mathrm { E V } } }
$$

$$
\mathrm { S O C } _ { _ { \mathrm { E V i d c } } } = \mathrm { S O C } _ { _ { \mathrm { E V i 0 } } } - \Delta \mathrm { S O C } _ { _ { \mathrm { E V } } } = \mathrm { S O C } _ { _ { \mathrm { E V i 0 } } } + \frac { P _ { _ { \mathrm { E V i d c } } } T _ { \mathrm { d c } } } { E _ { \mathrm { E V } } }
$$

式中， ${ \mathrm { s o c } } _ { \mathrm { { E V } } i 0 }$ ， $\mathrm { s o c } _ { \mathrm { { E V } \it { i c } } }$ 和 ${ \mathrm { S O C } } _ { \mathrm { E V } i \mathrm { d c } }$ 分别为电动汽车的初始荷电状态、充电后的荷电状态和放电后的荷电状态； $\Delta \mathrm { S O C } _ { \mathrm { E V } }$ 为电动汽车荷电状态的变化量； $P _ { \mathrm { E V } i \mathrm { c } }$ ， $P _ { \mathrm { E V } i \mathrm { d c } }$ 分别为电动汽车的充电功率和放电功率； $T _ { \mathrm { c } }$ ， $T _ { \mathrm { d c } }$ 为电动汽车的充电时间和放电时间；$E _ { \mathrm { E V } }$ 为电动汽车满电时的电量。

# 3.1.3电动汽车充放电功率

为了保证电动汽车电池的使用寿命，要保证$\mathrm { s o c } _ { \mathrm { \scriptscriptstyle E V } i 0 }$ 满足一定的约束要求，即

$$
\mathrm { S O C } _ { \mathrm { E V m i n } } < \mathrm { S O C } _ { \mathrm { E V } i 0 } < \mathrm { S O C } _ { \mathrm { E V m a x } }
$$

当 $\mathrm { S O C } _ { \mathrm { E V } { i 0 } } < \mathrm { S O C } _ { \mathrm { E V } { \operatorname * { m i n } } }$ 时，电动汽车只能进行充电；当 $S O C _ { \mathrm { E V m a x } } < S O C _ { \mathrm { E V } i 0 }$ 时，电动汽车只能进行放电。

假设系统中有 $\mathbf { \Sigma } _ { m }$ 部电动汽车，在某时间段接入配电网的电动汽车数目 $N _ { \mathrm { E V } }$ 服从正态分布[20]，即

$$
E _ { _ { N _ { \mathrm { E V } } } } = m f ( t )
$$

式中， $\mathbf { \nabla } _ { m }$ 为电动汽车数量； $\mathbf { \chi } _ { t }$ 为时段； $f \left( t \right)$ 为电动汽车充电的概率分布函数。

单个时间段内实际接入进行充电的电动汽车数目可由泊松分布表示为

能接入配电网的电动汽车的数目。

根据文献[19]，可以得到某个时间段第 $i$ ( $i <$ $N _ { \mathrm { E V } }$ ）辆电动汽车的最大充放电功率为

$$
\left\{ \begin{array} { l l } { P _ { \mathrm { E V } i \mathrm { c m a x } } = \operatorname* { m i n } \left\{ \displaystyle \frac { E _ { \mathrm { E V } i } } { T } ( \mathrm { S O C } _ { \mathrm { E V } \mathrm { m a x } } - \mathrm { S O C } _ { \mathrm { E V } i 0 } ) , P _ { \mathrm { E V } i \mathrm { c N } } \right\} } \\ { P _ { \mathrm { E V } i \mathrm { d c } \mathrm { m a x } } = \operatorname* { m i n } \left\{ \displaystyle \frac { E _ { \mathrm { E V } i } } { T } ( \mathrm { S O C } _ { \mathrm { E V } i 0 } - \mathrm { S O C } _ { \mathrm { E V } \mathrm { m i n } } ) , P _ { \mathrm { E V } i \mathrm { d c } \mathrm { N } } \right\} } \end{array} \right.
$$

式中， $P _ { \mathrm { E V } i \mathrm { c m a x } }$ ， $P _ { \mathrm { E V } i \mathrm { d c m a x } }$ 分别为第 $i$ 辆电动汽车在某个时间段最大充、放电功率； $P _ { \mathrm { E V } i \mathrm { c N } }$ 、 $P _ { \mathrm { E V } i \mathrm { d c N } }$ 分别为第 $i$ 辆电动汽车的额定充电功率和额定放电功率。

某时间段电动汽车最大充放电功率为

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { \displaystyle P _ { \mathrm { E V c m a x } } = \sum _ { i = 1 } ^ { N _ { \mathrm { E V } } } P _ { \mathrm { E V i c m a x } } } \\ { \displaystyle P _ { \mathrm { E V d c m a x } } = \sum _ { i = 1 } ^ { N _ { \mathrm { E V } } } P _ { \mathrm { E V i d c m a x } } } \end{array} \right. } \end{array}
$$

式中， $N _ { \mathrm { E V } }$ 为电动汽车的数量。

# 3.2储能装置运行特性

(1）效率 $\eta$ 。单个储能装置容量为 $E _ { \mathrm { D S } i }$ ，即为该储能装置的最大存储电量，若此时储能装置的电量为 $E _ { \mathrm { D S } i \mathrm { i n } }$ ，则该储能装置可以输出的电量 $^ { [ 2 1 ] } E _ { \mathrm { D S } i \mathrm { o u t } }$ 为

$$
E _ { \mathrm { D S } i \mathrm { o u t } } = \eta _ { i } E _ { \mathrm { D S } i \mathrm { i n } }
$$

储能装置存在技术和工艺上的差距，导致 $\eta _ { i }$ 取值不同[21]。

(2）最大充放电功率。储能装置受安全和技术限制，单个储能装置的最大充电功率 $P _ { \mathrm { D S } _ { i } \mathrm { c m a x } }$ 和最大放电功率 $P _ { \mathrm { D S } i \mathrm { d c m a x } }$ 在储能装置的使用过程中不应超过装置本身的限制[21]。

(3）荷电状态 $\mathrm { s o c } _ { \mathrm { D S } i }$ 。 $\mathrm { S O C } _ { \mathrm { D S } i }$ 表示单个储能装置当前的容量占储能装置设计的最大存储电量，即

$$
\mathrm { S O C } _ { \mathrm { D S } i } = \frac { E _ { \mathrm { D S } i \mathrm { i n } } } { E _ { \mathrm { D S } i } }
$$

因为储能装置的过充或过放对储能装置的使用寿命具有一定影响，因此荷电状态 $\mathrm { S O C } _ { \mathrm { D S } { i } }$ 应满足[22]

$$
p ( N _ { \mathrm { E V } } ) { = } \frac { ( \lambda _ { \mathrm { E V } } ) ^ { N _ { \mathrm { E V } } } } { N _ { \mathrm { E V } } ! } \mathrm { e x p } ( - \lambda _ { \mathrm { E V } } )
$$

式中， $N _ { \mathrm { { E V } } } = 0 , 1 , \cdots , \ \lambda _ { \mathrm { { E V } } }$ 为式（7）求得的某个时间段接入电网充电的电动汽车台数期望值； $N _ { \mathrm { E V } }$ 为可

$$
\mathrm { S O C } _ { \mathrm { D S } i \operatorname* { m i n } } < \mathrm { S O C } _ { \mathrm { D S } i } < \mathrm { S O C } _ { \mathrm { D S } i \operatorname* { m a x } }
$$

与储能装置的运行效率类似，受储能装置的自身因素影响，不同装置 $\mathrm { S O C } _ { \mathrm { D S } i }$ 的上限与下限存在差异性。

# 4多目标无功优化模型

DG 接入配电网会引起局部区域电压升高。DS和EV作为两种最典型的可控型负荷，当分布式电源输出功率发生不确定性变化时，通过控制DS和EV的有功输入或有功输出等变量来减小电网电压波动，并实现全网功率损耗的大幅减少，这是一个分布式新能源配电网无功优化问题，是一个多变量、多约束复杂的规划问题，可以构建多目标无功优化模型为

$$
\left\{ \begin{array} { l l } { \operatorname* { m i n } } & { f ( x ) = \lbrack f _ { 1 } ( x ) , f _ { 2 } ( x ) , \cdots , f _ { n } ( x ) \rbrack } \\ { \mathrm { ~ s . ~ t . ~ } } & { g ( x ) = 0 } \\ & { x _ { \operatorname* { m i n } } < x < x _ { \operatorname* { m a x } } } \\ & { y _ { \operatorname* { m i n } } < y < y _ { \operatorname* { m a x } } } \end{array} \right.
$$

式中， $f$ 为目标函数； $f _ { i }$ 为子目标函数， $i = 1 , 2 , \cdots , n$ （204号 $x$ 为包含控制变量的 $N$ 维列向量， $x { \in } R ^ { N }$ ， $x = ( P _ { \mathrm { D S } }$ ，$P _ { \mathrm { E V } }$ ， $\varrho _ { \mathrm { c } }$ ， $Q _ { \mathrm { w } }$ ， $\varrho _ { \mathrm { p v } } )$ ； $P _ { \mathrm { D S } }$ 为储能装置输出或输入有功功率； $P _ { \mathrm { E V } }$ 为电动汽车输出或输入有功功率； $\varrho _ { \mathrm { w } }$ 为可控的光伏发电装置无功功率； $\varrho _ { \mathrm { c } }$ 为可控的电容器投切无功功率； $\varrho _ { \mathrm { w } }$ 为可控的风电机组无功功率；$g ( x )$ 为潮流约束方程； $x _ { \mathrm { m i n } }$ ， $x _ { \mathrm { m a x } }$ 为控制变量的下限值和上限值； $y _ { \mathrm { m i n } }$ ， $y _ { \mathrm { m a x } }$ 为系统其他变量约束的下限值和上限值。

# 4.1 目标函数

本文以有功损耗和电压偏移量为目标函数，分别为

$$
f _ { \mathrm { l o s s } } = \operatorname* { m i n } \sum _ { i \in N _ { \mathrm { L } } , j \in B _ { i } } G _ { i j } ( V _ { i } ^ { 2 } + V _ { j } ^ { 2 } - 2 V _ { i } V _ { j } \cos \theta _ { i j } )
$$

# 4.2约束条件函数

（1）潮流平衡方程。分布式发电输出功率具有不确定性，在不同控制要求下分布式储能和电动汽车充放电功率也具有不确定性，在任何状态下需要满足等潮流方程

$$
\begin{array} { r } { \left\{ \begin{array} { l } { \displaystyle \Delta P _ { i } = P _ { i } - V _ { i } \sum _ { j = 1 } ^ { N } \nu _ { j } ( G _ { i j } \cos \theta _ { i j } + B _ { i j } \sin \theta _ { i j } ) = 0 } \\ { \displaystyle } \\ { \displaystyle \Delta Q _ { i } = Q _ { i } - V _ { i } \sum _ { j = 1 } ^ { N } \nu _ { j } ( G _ { i j } \sin \theta _ { i j } - B _ { i j } \cos \theta _ { i j } ) = 0 } \end{array} \right. } \end{array}
$$

式中， $P _ { i }$ 、 $Q _ { i }$ 分别为节点 $i$ 注入的有功功率和无功功率，即为节点有功电源注入功率、有功负荷（负的）注入功率等之和。

$$
P _ { \mathrm { E V } i \mathrm { d c } \operatorname* { m i n } } < P _ { \mathrm { E V } i \mathrm { d c } } < P _ { \mathrm { E V } i \mathrm { d c } \operatorname* { m a x } }
$$

(2）控制变量不等式约束条件。本文构建的无功优化问题涉及分布式电源输出无功功率、无功补偿装置输出的无功功率、分布式储能装置充放电功率、电动汽车充放电功率等控制变量。上述控制变量要满足不等式约束条件

$$
Q _ { \mathrm { D G } i \mathrm { m i n } } < Q _ { \mathrm { D G } i } < Q _ { \mathrm { D G } i \mathrm { m a x } }
$$

$$
Q _ { \mathrm { { C } i m i n } } < Q _ { \mathrm { { C } } i } < Q _ { \mathrm { { C } } i \operatorname* { m a x } }
$$

$$
P _ { \mathrm { D S } i \mathrm { c } \operatorname* { m i n } } < P _ { \mathrm { D S } i \mathrm { c } } < P _ { \mathrm { D S } i \mathrm { c } \operatorname * { m a x } }
$$

$$
P _ { \mathrm { D S } i \mathrm { d c m i n } } < P _ { \mathrm { D S } i \mathrm { d c } } < P _ { \mathrm { D S } i \mathrm { d c } \operatorname * { m a x } }
$$

$$
P _ { \mathrm { E V } i \mathrm { c } \operatorname* { m i n } } < P _ { \mathrm { E V } i \mathrm { c } } < P _ { \mathrm { E V } i \mathrm { c } \operatorname * { m a x } }
$$

$$
f _ { \Delta V } = \operatorname* { m i n } \sum _ { i = 1 } ^ { N } \Biggl ( \frac { V _ { B i } - V _ { i } } { V _ { i \operatorname* { m a x } } - V _ { i \operatorname* { m i n } } } \Biggr ) ^ { 2 }
$$

式中， $f _ { \mathrm { l o s s } }$ ， $f _ { \Delta V }$ 分别为网损和电压偏差； $N _ { \mathrm { L } }$ 为总母线； $V _ { i \cdot }$ ： $V _ { j }$ 分别为节点 $i$ 和 $j$ 处的电压幅值； $G _ { i j }$ 为节点 $i , j$ 的互电导； $\theta _ { i j }$ 为节点 $i , j$ 的相位差； $N$ 为系统节点总数；B;为节点i的邻近节点集合；Vimax、$V _ { \mathrm { i m i n } }$ ， $V _ { B i }$ 分别为节点电压的上限值、下限值和节点电压的基准值。

多目标函数为

$$
F = \operatorname* { m i n } [ \lambda _ { \scriptscriptstyle 1 } f _ { \mathrm { l o s s } } + \lambda _ { \scriptscriptstyle 2 } f _ { \scriptscriptstyle \Delta V } ]
$$

式中， $\lambda _ { 1 } 、 \lambda _ { 2 }$ 为权重系数， $\lambda _ { 1 } + \lambda _ { 2 } = 1$ ， $0 \leqslant \lambda _ { 1 } \leqslant 1$ $0 \leqslant \lambda _ { 1 } \leqslant 1$ 。

式中， $\boldsymbol { \mathcal { Q } } _ { \mathrm { D G \it { i } } }$ 、 $\boldsymbol { \mathcal { Q } } _ { \mathrm { c } i }$ ， $P _ { \mathrm { D S } i \mathrm { c } }$ 、 $P _ { \mathrm { D S } i \mathrm { d c } }$ ， $P _ { \mathrm { E V } i \mathrm { c } }$ ， $P _ { \mathrm { E V } i \mathrm { d c } }$ 分别为分布式电源输出的无功功率、无功补偿装置输出的无功功率、储能装置充电的有功功率、储能装置放电的有功功率、电动汽车充电的有功功率、电动汽车放电的有功功率；下标“min”和“max”分别表示对应参数的下限值和上限值。

(3）状态变量约束条件。优化问题中状态变量为节点电压，其应小于允许的最大值、大于允许的最小值，即

$$
V _ { i \operatorname* { m i n } } < V _ { i } < V _ { i \operatorname* { m a x } }
$$

# 5 遗传算法

遗传算法[23]是通过模拟生物在自然环境中的遗传和进化过程而形成的一种自适应全局优化概率搜索算法。将实际要求解的变量进行编码，形成可以遗传变异的染色体，相应于一组变量值的目标函数，经过变换作为个体的适应度函数。首先随机的给出初始值，经过优胜劣汰，选择其中相对满足条件的个体，对这些个体进行复制、交叉、变异等遗传操作，得到下一代个体。不断重复这种操作，一直到有最优解或遗传代数到达设定值[24]。

将遗传算法应用于电力系统优化问题[25]时，可以理解为：电力系统下的潮流解，受到多种约束条件的制约，通过目标函数评价其优劣，评价值低的被抛弃，只有评价值高的有机会将其特征迭代至下一轮解，最后趋于优化。

# 5.1编码

由于遗传算法具有适合混合整数优化的特点，无功优化问题与染色体之间的编码非常方便。每个染色体可以表示一个优化方案。

本文采用整数编码方式，这里取并联补偿电容器、电动汽车、储能装置、分布式电源等输出无功功率作为控制变量，并全部用整数表示。因此，控制变量的染色体可表示为

$$
\begin{array} { r c l l l } { { } } & { { X = \left[ Q _ { \mathrm { c } } \quad Q _ { \mathrm { D s } } \quad Q _ { \mathrm { E v } } \quad Q _ { \mathrm { G } } \right] } } & { { } } & { { } } & { { } } \\ { { } } & { { } } & { { } } & { { } } & { { } } \\ { { } } & { { = \left[ Q _ { \mathrm { c } 1 } \cdots Q _ { \mathrm { c } i } \quad Q _ { \mathrm { D s } 1 } \cdots Q _ { \mathrm { D s } i } \quad Q _ { \mathrm { E v } 1 } \cdots Q _ { \mathrm { E v } i } \quad Q _ { \mathrm { G } 1 } \cdots Q _ { \mathrm { G } i } \right] } } \end{array}
$$

式中， $\varrho _ { \mathrm { c } }$ ， $\varrho _ { \mathrm { D S } }$ 、 $\boldsymbol { \mathcal { Q } } _ { \mathrm { E V } }$ ， $\varrho _ { \mathrm { G } }$ 分别为电容器、储能装置、电动汽车分布式电源的无功输出。

$\boldsymbol { \mathcal { Q } } _ { \mathrm { c } i }$ ， $\varrho _ { \mathrm { D S } }$ ， $\mathrm { E V } _ { i }$ ， $\varrho _ { \mathrm { E V } }$ 初始值为

$$
X _ { _ i } = \frac { ( X _ { \operatorname* { m a x } } - X _ { \operatorname* { m i n } } ) d } { 2 ^ { k } - 1 } + X _ { \operatorname* { m i n } }
$$

式中，d为随机数；k为单个参数字串长度[26]。

# 5.2适应度函数

适应度函数作为整个遗传算法的基础，遗传算法的性能会因合理的适应度函数而获得很大的提升。对适应度进行拉伸改进，变换公式为

$$
f = { \frac { 1 } { F } }
$$

式中， $F$ 为目标函数值[26]。

# 5.3求解步骤

根据以上描述，基于遗传算法的电力系统无功优化解算步骤如下：

(1）输入网络的原始数据、网络的等式约束条件和不等式约束条件。(2）将变量写成码的形式，编码产生初始染色体域。(3）计算每个染色体的适应函数值。（4）用繁殖、交叉、变异三种遗传操作在前代染色体域的基础上产生新一代染色体域。(5）对进行遗传操作后的第I代染色体解码后计算其适应函数值。(6）若遗传代数大于最先设定的最大遗传代数，则结束循环；反之，返回 (4)。（7）进行约束条件的校验，包括状态变量的等式和不等式约束条件、控制变量的取值范围约束条件。如果控制变量值和状态变量值不能满足约束条件要求，则返回 (4)。(8）提取无功优化结果。当基于遗传算法的电力系统无功优化问题收敛时获得无功优化方案，染色体中适应度最好的即为最优解[27]

# 6 实例计算与分析

本文采用如图1所示的改进的IEEE33配电系统作为算例[28]。IEEE33配电网系统是纯辐射状的配电网，网络节点33个，支路数32条。该算例基准电压为 $1 2 . 6 6 \mathrm { k V }$ ，基准容量 $1 0 \ 0 0 0 \mathrm { k V \cdot A }$ 负荷节点电压区间为[0.95，1.05]，负荷有功功率为5084.26kW、无功功率为3347.32kvar[29]。

![](images/f1393f1aed88b66183832c7007a9811b3f5ad0b20fb0d6d7ece793e5835dad4b.jpg)  
图1IEEE33配电系统  
Fig.1 IEEE 33 distribution system

假设节点31装有并联电容， $0 . 1 5 \times 4 ~ 0 0 0 \mathrm { k v a r }$ 在节点3接入额定容量为 $8 5 0 \mathrm { k W }$ 的双馈异步发电机组；节点26接入光伏发电系统，额定容量为$5 0 0 \mathrm { k W }$ ；蓄电池最大持续放电功率为 $8 0 \mathrm { k W }$ ，额定容量分别为 $2 0 0 \mathrm { k W \cdot h }$ ；单台电动汽车最大持续充放电功率为3kW，假设节点3和节点26处的电动汽车保有量分别为500台和400台。

计算中相关参数设置为：遗传算法群体规模$M = 4 0$ ，终止代数 $T = 1 0 0$ 。遗传算法的交叉概率 $p _ { \mathrm { c } } =$ 0.8，变异概率 $p _ { \mathrm { m } } = 0 . 1 ^ { [ 3 0 ] }$ 。由于本文采用整数编码的方式，故染色体总长即为控制变量个数7。

通过遗传算法进行优化后，有功网损为 $8 6 \mathrm { k W }$ 与优化前网损值 $1 4 1 \mathrm { k W }$ 相比，网损下降了 $3 9 \%$ 。各节点电压与参考电压偏差幅度变小，如图2所示。图中，方案1为未接入DG时的节点电压波动情况；方案2为接入DG但未进行优化时的电压波动情况；方案3为接入DG并进行优化时的电压波动情况。优化前节点电压最小值为0.978，优化后节点电压最低为 $0 . 9 9 0 \ 6$ 。上述优化结果表明优化后节点电压波动明显减小，电压稳定性增强。优化后各控制变量最优值见下表。

![](images/e2b7090bcdb3bc519502c5d3b6c375f8942aad30168fb27a5bfbd941b5b7a8e0.jpg)  
图2节点电压幅值变化 Fig.2Nodal voltage variation

# 表优化后各控制变量最优值

Tab.Optimal value of each control variable after optimization   

<html><body><table><tr><td>控制变量</td><td>最优值</td></tr><tr><td>无功补偿/kvar</td><td>309.7</td></tr><tr><td>储能放电（节点3）/kW</td><td>26</td></tr><tr><td>储能放电（节点26）/kW</td><td>29</td></tr><tr><td>电动汽车放电（节点3）/kW</td><td>38.7</td></tr><tr><td>电动汽车放电（节点26）/kW</td><td>48.4</td></tr><tr><td>DG 无功输出 （节点3）/kvar</td><td>154.8</td></tr><tr><td>DG 无功输出（节点26）/kvar</td><td>206.5</td></tr></table></body></html>

# 7 结束语

分布式发电、分布式储能和电动汽车充放电的协同运行是目前研究的热点。分布式发电、分布式储能和电动汽车充放电站点的大规模接入会对传统的配电网供电能力、电压质量、运行经济性和可靠性造成很大的影响。电动汽车动力电池系统与储能装置作为可控负荷，可以对分布式电源接入后引起的电压波动有一定程度的缓解，对维持电压的稳定具有重要的意义。本文考虑分布式电源出力的不确定性，以网损和电压稳定性指标为目标函数，通过分布式储能装置、电动汽车充电站、无功补偿装置以及分布式电源等无功功率作为控制变量，构建考虑分布式发电、分布式储能和电动汽车充放电协同运行的配电网无功优化模型，采用遗传算法对优化问题进行求解，仿真结果表明了该优化方法的有效性。

# 参考文献

[1] 胡泽春，宋永华，徐智威，等．电动汽车接入电 网的影响与利用[J]．中国电机工程学报，2012, 32(4):1-10，25. Hu Zechun, Song Yonghua, Xu Zhiwei, et al. Impacts and utilization of electric vehicles integration into power systems[J]. Proceedings of the CSEE,2012, 32(4): 1-10, 25.   
[2] 王辉，文福拴，辛建波．电动汽车充放电特性及 其对配电系统的影响分析[J]．华北电力大学学报 （自然科学版），2011，38(5)：17-24. Wang Hui, Wen Fushuan, Xin Jianbo. Charging and discharging characteristics of electric vehicles as well as their impacts on distribution systems[J]. Journal of North China Electric Power University, 2011, 38(5): 17-24.   
[3] 占恺峤，宋永华，胡泽春，等．以降损为目标的 电动汽车有序充电优化[J]．中国电机工程学报, 2012，32(31)：11-18，213. Zhan Kaiqiao, Song Yonghua, Hu Zechun,et al. Coordination of electric vehicle charging to minimize active power losses[J]. Proceedings of the CSEE, 2012,32(31): 11-18,213.   
[4] 杨冰，王丽芳，廖承林，等．电动汽车与分布式 电源协同有序控制研究[J]．电工技术学报，2015, 30(14): 419-426. Yang Bing, Wang Lifang,Liao Chenglin, et al. Study of coordinated charging control for electric vehicles in correlation with distributed power source[J]. Transactions of China Electrotechnical Society, 2015,30(14): 419-426.   
[5] 李惠玲，白晓民，谭闻，等．电动汽车与分布式 发电入网的协调控制研究[J]．电网技术，2013, 37(8): 2108-2115. Li Huiling,Bai Xiaomin, Tan Wen,et al. Coordination control for grid-connection of plug-in hybrid electric vehicles and distributed generation[J]. Power System Technology,2013,37(8): 2108-2115.   
[6] 李惠玲，白晓民，谭闻，等．电动汽车入网技术在 配电网的应用研究[J]．中国电机工程学报，2012, 32(S1): 22-27. Li Huiling,Bai Xiaomin, Tan Wen,et al.Application of vehicle to grid to the distribution grid[J]. Proceedings of the CSEE,2012, 32(S1): 22-27.   
[7] 刘浩军．风电、光伏发电和电动汽车负荷协同控 制的模型和方法[J]．电力系统及其自动化学报, 2015(S1): 12-17. Liu Haojun. Cooperative control model and method of the regional wind farm, photovoltaic generation and electric vehicles[J]. Proceedings of the CSUEPSA,2015(S1): 12-17.   
[8] 于大洋，宋曙光，张波，等．区域电网电动汽车 充电与风电协同调度的分析[J]．电力系统自动化, 2011，35(14): 24-29. Yu Dayang, Song Shuguang, Zhang Bo, et al. Synergistic dispatch of PEVs charging and wind power in Chinese regional power grids[J]. Automation of Electric Power Systems,2011,35(14): 24-29.   
[9] 张颖达，刘念，张建华，等．含电动汽车充电站 的风光互补系统容量优化配置[J]．电力系统保护 与控制，2013，41(15)：126-134. Zhang Yingda,Liu Nian, Zhang Jianhua,et al. Optimum sizing of a stand-alone hybrid PV/wind generation system integrated with electric vehicle charging stations[J]. Power System Protection and Control, 2013,41(15): 126-134.   
[10]王贵斌，赵俊华，文福拴，等．配电系统中电动 汽车与可再生能源的随机协同调度[J]．电力系统 自动化，2012，36(19)：22-29. Wang Guibin, Zhao Junhua,Wen Fushuan,et al. Stochastic optimization dispatching of plug-in hybrid electric vehicles in coordination with renewable generation in distribution systems[J]. Automation of Electric Power System,2012,36(19): 22-29.   
[11]刘柏良，黄学良，李军，等．含分布式电源及电 动汽车充电站的配电网多目标规划研究[J]．电网 技术，2015，39(2)：450-456. Liu Bailiang, Huang Xueliang, Li Jun, et al. Multiobjective planning of distribution network containing distributed generation and electric vehicle charging stations[J]. Power System Technology, 2015,39(2): 450-456.   
[12]胡泽春，宋永华，徐智威，等．电动汽车接入电 网的影响与利用[J]．中国电机工程学报，2012, 32(4):1-10. Hu Zechun, Song Yonghua, Xu Zhiwei, et al. Impacts and utilization of electric vehicles integration into power systems[J]. Proceedings of the CSEE,2012, 32(4): 1-10.   
[13]李惠玲，白晓民．电动汽车充电对配电网的影响及 对策[J]．电力系统自动化，2011，35(17)：38-43. Li Huiling, Bai Xiaomin. Impacts of electric vehicles charging on distribution grid[J]. Automation of Electric Power Systems,2011,35(17): 38-43.   
[14]万路路，王磊，丁昊．配电网电动汽车优化充电 研究[J]．华东电力，2011，39(12)：2049-2053. Wan Lulu,Wang Lei,Ding Hao.Research on charging optimization for distributed plug-in hybrid EV[J].East China Electric Power, 2011,39(12): 2049-2053.   
[15]高赐威，张亮．电动汽车充电对电网影响的综述 [J]．电网技术，2011，35(2)：127-131. Gao Ciwei, Zhang Liang.A survey of influence of electrics vehicle charging on power grid[J]. Power System Technology,2011,35(2): 127-131.   
[16]许晓艳，黄越辉，刘纯，等．分布式光伏发电对 配电网电压的影响及电压越限的解决方案[J]．电 网技术，2010，34(10)：140-146. Xu Xiaoyan, Huang Yuehui, Liu Chun,et al. Influence of distributed photovoltaic generation on voltage in distribution network and solution of voltage beyond limits[J]. Power System Technology, 2010, 34(10): 140-146.   
[17]吴晨曦，文福拴，陈勇，等．含有风电与光伏发 电以及电动汽车的电力系统概率潮流[J]．电力自 动化设备，2013，33(10)：8-15. Wu Chenxi, Wen Fushuan, Chen Yong,et al. Probabilistic load flow of power system with WFs, PVs and PEVs[J]. Electric Power Automation Equipment, 2013, 33(10): 8-15.   
[18]张丽，徐玉琴，王增平，等．包含分布式电源的配 申网无功优化[J]．电T技术学报，2011．26(3). Zhang Li, Xu Yuqin, Wang Zengping, et al. Reactive power optimization for distribution system with distributed generators[J]. Transactions of China Electrotechnical Society,2011,26(3): 168-174.   
[19]苏栗，蒋小超，王玮，等．计及电动汽车和光伏— 储能的微网能量优化管理[J]．电力系统自动化， 2015，39(9):164-171. Su Su, Jiang Xiaochao,Wang Wei, et al. Optimal engergy management for microgrids considering electric vehicles and photovoltaic-engergy storage[J]. Automation of Electric Power Systems, 2009,39(9): 164-171.   
[20]吴杰康，林奕鑫，吴志山 等．考虑不确定性的含 DG 与EV配电网无功电压协调优化方法[J]．现代 电力，2016，33(4)：23-29. Wu Jiekang, Lin Yixin, Wu Zhishan, et al. Optimized method for coordinating reactive power and voltage level in distribution network by considering the uncertainty of DG and EV[J]. Modern Electric Power,2016,33(4): 23-29.   
[21]杨家豪，欧阳森，吴裕生，等．计及风-储联合 系统概率模型的配电网随机潮流[J]．电网技术, 2016，40(1): 234-241. Yang Jiahao, Ouyang Sen, Wu Yusheng, et al. Stochastic power flow of distribution network considering probability model of wind-storage combined systems[J]. Power System Technology, 2016,40(1): 234-241.   
[22]吴小刚，刘宗歧，田立亭，等．独立光伏系统光储 容量优化配置方法[J]．电网技术，2014，38(5)： 1271-1276. Wu Xiaogang, Liu Zongqi, Tian Liting, et al. Optimized capacity configuration of photovoltaic generation and energy storage device for stand-alone photovoltaic generation system[J]. Power System Technology, 2014,38(5): 1271-1276.   
[23]Cao Y J, Wu Q H. Optimal reactive power dispatch using an adaptive genetic algorithm[C]. In Proceedings of Int. Conf. on Genetic Algorithm in Engineering Systems, Glasgow, UK,1997: 117-122.   
[24]李敏强，寇纪淞．遗传算法的基本理论与应用[M]. 北京：科学出版社，2003.   
[25]何正文．基于遗传算法的电网无功优化[J]．低压 电器，2007(1)：40-44. He Zhengwen. Reactive power optmiization based on genetic algorithms in electrical power system[J]. Low Voltage Apparatus, 2007(1): 40-44.   
[26]杨旭红，卢栋青．基于遗传算法的电力系统无功 优化[J]．上海电力学院学报，2011，27(5)：435- 438，443. Yang Xuhong, Lu Dongqing. Reactive power optimization based on genetic algorithm[J]. Journal of Shanghai University of Electric Power,2011, 27(5): 435-438,443.   
[27]程浩忠．基于遗传算法的电力系统无功优化[J]. 上海交通大学学报，1998(1)：129-132. Cheng Haozhong. Reactive power optimization based on enetic algorithms in electric power systems[J]. Journal of Shang Hai Jiao Tong University,1998(1): 129-132.   
[28]刘健，毕鹏翔，董海鹏．复杂配电网简化分析与 优化[M]．北京：中国电力出版社，2002.   
[29]Baran M E,Wu F F. Network reconfiguration in distribution systems for loss reduction and load balancing[J]. IEEE Trans.on Power Delivery,1989, 4(4): 1401-1407.   
[30]张武军，叶剑锋，梁伟杰，等．基于改进遗传算法 的多目标无功优化[J]．电网技术，2004，28(11)： 67-71. Zhang Wujun, Ye Jianfeng,Liang Weijie,et al. Multiple-objective reactive power optimization based on improved genetic algorithm[J]. Power System Technology,2004,28(11): 67-71.