# 基于VSG控制的微网逆变器最优虚拟惯性研究

毛福斌 章雪萌李玉良　祝　青　孟祥娟 陈晓峰（中国能源建设集团安徽省电力设计院有限公司合肥 230601)

![](images/99b1041e3423ab8189a4386882bac22130f8929f5ae627fad7284ec7f05b98e6.jpg)

毛福斌男 1990年生，硕士，研究方向为新能源并网发电、微电网等。

摘要：为了能够支撑微电网的电压和频率，提高微电网运行的稳定性，本文针对采用虚拟同步发电机（VSG）控制策略的微网逆变器进行了研究。由于VSG中虚拟惯性的存在，在功率调度指令突变时，微网逆变器的频率和输出功率会发生振荡，严重时将导致逆变器因过流保护而停机。本文在功率闭环传递函数根轨迹分析影响VSG 稳定性和动态性能的参数变化范围的基础上，采用线性二次型最优控制，以功率和频率变化量为约束条件，提出了最优虚拟惯性控制策略，通过对VSG参数进行优化配置解决了上述问题。Matlab 仿真和实验结果验证了该控制策略的正确性和有效性。

关键词：微电网虚拟同步发电机频率控制功率振荡 最优虚拟惯性中图分类号：TM464

# Research on Optimal Virtual Inertia of Micro-Grid Inverter Based on VSG Control

![](images/3a8fe371dd81f4d3c829eb45271092264131d6bf463e85cd5c2c4684c2b28821.jpg)

章雪萌女 1983年生，硕士，工程师，研究方向为电力系统及其自动化等。

Mao Fubin Zhang Xuemeng Li Yuliang Zhu Qing Meng Xiangjuan Chen Xiaofeng （Anhui Electric Power Design Institute,CEECHefei 230601 China ）

Abstract: In order to support the voltage and frequency of micro-grid and improve the stability of it, micro-grid inverter based on virtual synchronous generator control is studied in this paper. Due to the existence of virtual inertia in the VSG, the frequency and output power of micro-grid inverter will oscillate and the inverter will break down in severe cases due to over-current protection. Firstly,on the basis of power closed loop transfer function,a detail analysis was available to quantify the scope of the influence of VSG parameter variation on the stability and dynamic performance of the system by root locus.Besides,with power and frequency change as the constraint condition,an optimal virtual inertia control strategy based on the linear quadratic optimal control was proposed. Additionally, these problems were solved through the optimization of the parameters of VSG.Finally, simulated results on Matlab and experimental results were utilized to confirm the validation and feasibility of the proposed control strategy.

Keywords: Micro-grid, virtual synchronous generator, frequency control, power oscillation, optimal virtual inertia

# 1 引言

作为一种新的微网逆变器控制方案，虚拟同步发电机（Virtual Synchronous Generator，VSG）控制策略越来越受到学者的关注[1-3]。和下垂控制相比，VSG不仅具有稳态的功率下垂特性，而且模拟了同步发电机的定子电气特性和转子惯性，使得微网逆变器在外特性和机理上均能与同步发电机相媲美。

然而，由于基于VSG的微网逆变器模拟了电力系统一次调频调压以及同步发电机的转子惯性和阻尼特性，与同步发电机类似，在功率调度指令发生变化或者直流侧分布式电源出力发生扰动时，并网或多机并联运行的逆变器输出频率和功率就会不可避免地发生振荡。但对于逆变器来说，其瞬态抗扰能力和过载能力远不如同步发电机，振荡造成的冲击电流可能导致逆变器保护动作而停机，严重时甚至危及功率器件的安全和微电网的稳定运行。

基于四阶小信号模型，文献[4]分析了双机并联采用虚拟惯性时可能引起的功率振荡问题，文中通过优化主电路和控制器参数抑制了振荡，但该方案主电路增加的线路阻抗将增大输出电压降落，控制器参数的改变除增加阻尼外也减慢了动态响应。

对比同步发电机，VSG由于没有真实的转子，可以通过灵活改变同步发电机模型中的参数来抑制这种振荡，以获得更快更稳定的运行特性。文献[5]通过小信号模型，以系统的稳态特性、动态特性、解耦性能和稳定性为约束条件对所提出的VSG模型参数进行优化，改善了逆变器多工作模式的动静态特性，但模型的建立相对复杂，多性能指标间难以兼顾。

受同步发电机惯性和阻尼特性的束缚，绝大部分文献都认为VSG的惯性也是一个固定的正常数。针对功率振荡，文献[6-7]提出了一种自适应虚拟惯性控制策略，阐述了变虚拟惯性和负虚拟惯性的概念，但该方案中虚拟惯性的取值采用Bang-Bang控制，虚拟惯性的频繁变化会造成功率的抖动。

VSG的具体实现离不开分布式电源、储能装置和逆变器。但现有关于VSG的研究，都假定配置的储能单元容量足够大且控制策略仅针对逆变器本身，还没有文献在考虑分布式电源和储能装置的基础上对逆变器的协调控制进行深入研究。

基于以上研究现状，本文充分利用VSG参数可灵活配置的优点，在通过功率闭环传递函数分析影响VSG稳定性和动态性能参数变化范围的基础上，以逆变器功率和频率变化量为约束条件，采用线性二次型最优控制，提出了最优虚拟惯性控制策略，有效解决了上述频率和功率振荡的问题。

# 2基于VSG控制的微网逆变器

# 2.1主电路拓扑及其控制结构

本文所研究的基于VSG的微网逆变器主电路拓扑及其控制结构如图1所示。其中： $U _ { \mathrm { d c } }$ 为直流侧电压； $L$ 和 $C$ 分别为滤波电感和滤波电容；T为隔离变压器； $\mathrm { \Delta S _ { T } }$ 为同步接触器； $L _ { 1 }$ 和 $r _ { \mathrm { l } }$ 为微网逆变器与公共交流母线间的耦合阻抗； $i _ { \mathrm { L k } }$ ， $i _ { \mathrm { o k } }$ 、 $u _ { \mathrm { o k } }$ 和 $e _ { \mathrm { k } }$ 分别为电感电流、输出电流、输出电压和电网电压； $P _ { \mathrm { ~ e ~ } }$ 和 $\varrho _ { \mathrm { e } }$ 分别为经过低通滤波器后计算得到的有功与无功功率； $\boldsymbol { \theta } ^ { * }$ 和 $\boldsymbol { U } ^ { * }$ 分别为经过VSG算法模块得到的电压幅值和相位指令； $\boldsymbol { u } _ { k }$ 为双环控制得到的调制波；其中 $k = \mathrm { a , b , c }$ 。

![](images/d4da7a8f762be88450820bbfdedc4f39a0666daf807678fe008f08a7c6bf307e.jpg)  
图1基于VSG的微网逆变器主电路拓扑及其控制结构  
Fig.1Main circuit topology and its control structure of three-phase VSG

基于VSG的微网逆变器控制结构分为3层：第1层为VSG控制器，引入同步发电机的二阶机电暂态模型来模拟其机械惯量和电气特性，得到端口电压给定值；第2层为内环控制器，通常为输出电压和电容电流控制双环，用以跟踪VSG控制器输出的给定；第3层为驱动控制器，包括SVPWM调制模块及IGBT驱动模块。

# 2.2VSG的具体实现

VSG算法模块包括有功－频率控制及无功－电压控制。VSG的有功－频率控制模拟了同步发电机的一次调频特性和同步发电机转子的惯性和阻尼[8],包括调速器方程和转子运动方程，如图2所示。

![](images/10db4df5b61ac21a13efb419ceae04e695634af99a8878c7cf22a40cad988ddf.jpg)  
Fig.2Active power-frequency control structure diagram

VSG调速器方程为

$$
( \omega _ { _ \mathrm { r e f } } - \omega _ { _ \mathrm { m } } ) \frac { 1 } { m } + P _ { _ \mathrm { r e f } } = P _ { _ \mathrm { m } }
$$

VSG转子运动方程为

$$
P _ { \mathrm { { m } } } - P _ { \mathrm { { e } } } - D ( \omega _ { \mathrm { { m } } } - \omega _ { \mathrm { { g } } } ) = J { \frac { \mathrm { { d } } \omega _ { \mathrm { { m } } } } { \mathrm { { d } } t } }
$$

式中， $\omega _ { \mathrm { r e f } } , \omega _ { \mathrm { m } }$ 和 $\omega _ { \mathrm { g } }$ 分别为VSG给定角频率、输出角频率和电网角频率； $\mathbf { \nabla } _ { m }$ 为有功下垂系数； $P _ { \mathrm { r e f } } ,$ $P _ { \mathrm { { m } } }$ 和 $P _ { \mathrm { ~ e ~ } }$ 分别为VSG 给定功率、机械功率和输出电磁功率； $J _ { 0 }$ ， $D _ { 0 }$ 分别为VSG虚拟惯性系数和虚拟阻尼系数； ${ \cal J } = { \cal J } _ { 0 } \omega _ { \mathrm { m } }$ 为虚拟惯性， $D = D _ { \mathrm { 0 } } \omega _ { \mathrm { m } }$ 为虚拟阻尼。

由图（2）可以得到

$$
\frac { \Delta \omega ( s ) } { \Delta P ( s ) } = \frac { 1 } { J s + \left( D + \displaystyle \frac { 1 } { m } \right) }
$$

由式（3）可知，频率增量 $\Delta \omega$ 关于有功功率增量 $\Delta P$ 的闭环传递函数为一阶惯性环节，下垂系数$m$ 和虚拟阻尼 $D$ 决定了VSG输出频率的稳态特性，而动态特性可以通过虚拟惯性 $J$ 进行优化。VSG参数配置存在3个可控的自由度，使其控制具有更大的灵活性，在一定程度上可以改善VSG的稳定性和

动态性能。

# 2.3VSG单机并网数学模型

考虑到逆变器电压电流内环的控制带宽远大于功率外环的控制带宽，为简化分析，本文仅建立基于功率外环的有功-频率闭环传递函数来对VSG的稳定性和动态性能进行研究。

图3为VSG并网运行的等效电路图，U、 $E$ 分别为逆变器输出电压及电网电压， $\delta$ 为 $U$ 和 $E$ 间的相位差，Z为逆变器等效输出阻抗、变压器漏感以及线路阻抗之和，一般呈感性。

![](images/6dfb0779d60939c8dbc30a217003b8f7200c990ae82a178c3ac2f95d12d3c053.jpg)  
图2有功-频率控制结构图  
图3基于VSG的微网逆变器并网等效电路图Fig.3Equivalent circuit of VSG connecting to grid

VSG输出的视在功率为

$$
S = P _ { \mathrm { e } } + j Q _ { \mathrm { e } } = { \frac { U E } { X } } \mathrm { s i n } \delta + \mathrm { j } { \frac { U E \cos \delta - E ^ { 2 } } { X } }
$$

由于功角 $\delta$ 一般很小， $\sin { \delta } \approx \delta$ ，有功功率表达式可以化简为

$$
P _ { \mathrm { e } } = { \frac { U E } { X } } \delta
$$

因为 $\delta = \int ( \omega _ { _ \mathrm { m } } - \omega _ { _ \mathrm { g } } ) \mathrm { d } t$ ，所以

$$
{ \left\{ \begin{array} { l l } { \displaystyle { \frac { \mathrm { d } P _ { \mathrm { e } } } { \mathrm { d } t } } = { \frac { U E } { X } } { \frac { \mathrm { d } \delta } { \mathrm { d } t } } = { \frac { U E } { X } } ( \omega _ { \mathrm { m } } - \omega _ { \mathrm { g } } ) } \\ { \displaystyle { \frac { \mathrm { d } ^ { 2 } P _ { \mathrm { e } } } { \mathrm { d } t ^ { 2 } } } = { \frac { U E } { X } } { \frac { \mathrm { d } \omega _ { \mathrm { m } } } { \mathrm { d } t } } } \end{array} \right. }
$$

则式（2）可以写成

$$
P _ { \mathrm { m } } = P _ { \mathrm { e } } + D \frac { \mathrm { d } P _ { \mathrm { e } } } { \mathrm { d } t } \frac { 1 } { \frac { U E } { X } } + J \frac { \mathrm { d } ^ { 2 } P _ { \mathrm { e } } } { \mathrm { d } t ^ { 2 } } \frac { 1 } { \frac { U E } { X } }
$$

经Laplace变换，得

$$
\frac { P _ { \mathrm { e } } } { P _ { \mathrm { m } } } = \frac { \displaystyle { \frac { 1 } { J } \frac { U E } { X } } } { s ^ { 2 } + \displaystyle { \frac { D } { J } s + \frac { 1 } { J } \frac { U E } { X } } }
$$

式（8）对应的控制结构如图4所示。

![](images/da077129de0a7ee2c2f71453ff3b419ca539c273dafa085e072e6558b90b3d4d.jpg)  
图4VSG功率闭环等效控制框图

不难发现，VSG输入功率和输出功率之间的传递函数是一个典型的二阶系统，对照典型二阶系统的闭环传递函数

$$
G ( s ) = { \frac { \omega _ { \mathrm { n } } ^ { 2 } } { s ^ { 2 } + 2 \xi \omega _ { \mathrm { n } } s + \omega _ { \mathrm { n } } ^ { 2 } } }
$$

则VSG对应的自然振荡角频率 $\omega _ { \mathrm { n } } = { \sqrt { { \frac { 1 } { J } } { \frac { U E } { X } } } }$ 阻尼比 $\xi = \frac { D } { J } \frac { 1 } { 2 \omega _ { _ \mathrm { n } } } = \frac { D } { 2 } \sqrt { \frac { 1 } { J } \frac { U E } { X } } \ .$

![](images/49c64526bce0da3e8619599ee74580dd7aaa40996b1da5b6ed5d0047c8292bf0.jpg)  
Fig.4Closed loop control diagram of VSG active power

因此，通过式（8）特征方程的根轨迹便可以对VSG的稳定性和动态性能进行分析，如图5所示。

图5给出了在虚拟惯性 $J$ 分别为5、15、30、150和300的条件下，虚拟阻尼 $D$ 从0到无穷大变化时的特征根轨迹族，系统有一对共轭复根，变化趋势由箭头标出。

对于某个特定的虚拟惯性 $J$ ，随着 $D$ 的增大,共轭复根位于复平面左侧，动态特性较好，但有超调；随着 $D$ 的进一步增大，系统由欠阻尼振荡系统变为过阻尼衰减系统，超调减小，动态响应减慢；但是 $D$ 过大，一个特征根趋向于零点，系统的稳定裕度减小。

随着虚拟惯性 $J$ 的增大，共轭复根的分离点靠近虚轴，系统的响应速度减慢，动态性能变差；但是 $J$ 过大，系统超调严重，稳定性也变差。

不难发现，VSG的虚拟惯性 $J$ 决定了其动态响应过程中的振荡频率，而虚拟阻尼 $D$ 决定了其振荡衰减的速率。一般地，在虚拟阻尼整定过程中，可以利用“西门子二阶最佳系统”的方法以获得较快的响应速度和较小的超调量，将系统的阻尼比定义在 $\xi = 0 . 7 0 7$ 处，即

$$
D = \sqrt { 2 J \frac { U E } { X } }
$$

# 3 最优虚拟惯性控制策略

# 3.1单机并网功率振荡问题

由上述分析可知，由于惯性和阻尼特性的引入，基于VSG的微网逆变器能够有效应对DG随机性、不可控性等带来的不利影响；但同时也使得VSG 输出有功功率在动态过程中出现与同步发电机类似的振荡特性。

下面来分析在功率调度指令突变时，微网逆变器输出频率和功率的振荡过程。由式（8）得，VSG的机械功率 $P _ { \mathrm { { m } } }$ 阶跃 $\Delta P _ { \mathrm { { m } } }$ 时，输出电磁功率 $P _ { \mathrm { ~ e ~ } }$ 的动态响应为

$$
\Delta P _ { \mathrm { { e } } } = { \frac { { \displaystyle { \frac { 1 } { J } } } { \frac { U E } { X } } } { s ^ { 2 } + { \displaystyle { \frac { D } { J } } } s + { \frac { 1 } { J } } { \frac { U E } { X } } } } { \frac { \Delta P _ { \mathrm { { m } } } } { s } }
$$

在工程应用中，由于过阻尼系统响应缓慢，通常不希望采用过阻尼系统。考虑欠阻尼（ $0 < \xi$ $< 1$ ）时，系统的动态响应曲线如图6所示，对应VSG的功角特性曲线如图7所示。

![](images/ebd2585cfc384d91d36fbfcd6054aad14260351e1f06cc07d9f54530123d8d2f.jpg)  
图5 $J$ 和 $D$ 不同取值时并网系统的特征根族 Fig.5Family root locus of VSG with various $J$ and $D$   
图6某一惯性和阻尼时的系统阶跃响应  
Fig.6Step response of the VSG with one of the $J$ and $D$

初始状态时，VSG空载稳定运行， $P _ { \mathrm { e } } = P _ { \mathrm { m } } =$ 0， $\omega _ { \mathrm { m } } = \omega _ { \mathrm { g } }$ ，此时功角 $\delta = 0$ ，对应图中a点；某一时刻，输入功率增加或者调度指令突然增加，VSG输出的机械功率 $P _ { \mathrm { { m } } }$ 增加造成 $P _ { \mathrm { { m } } } > P _ { \mathrm { { e } } }$ ，VSG开始加速， $\omega _ { \mathrm { m } } > \omega _ { \mathrm { g } }$ ，转子运动方程产生频率偏差，频率偏差经过时间积分后进一步增加功角， $\delta$ 增加,VSG 输出的电磁功率 $P _ { \mathrm { ~ e ~ } }$ 随之增加，直至 $P _ { \mathrm { e } } = P _ { \mathrm { m } }$ ，对应图中 $\mathsf { a { - } b }$ ；但由于 $\omega _ { \mathrm { m } } > \omega _ { \mathrm { g } }$ ， $\delta$ 继续增加, $P _ { \mathrm { ~ e ~ } }$ 出现超调， $\omega _ { \mathrm { m } }$ 减小，直至 $\omega _ { \mathrm { m } } = \omega _ { \mathrm { g } }$ ，此时VSG输出的电磁功率 $P _ { \mathrm { ~ e ~ } }$ 达到最大，对应图中 $\mathsf { b { - } c }$ 。由于 $P _ { \mathrm { { m } } }$ $< P _ { \mathrm { ~ e ~ } }$ ，VSG没有达到功率平衡状态， $\omega _ { \mathrm { m } }$ 继续减小,$\delta$ 减小，VSG输出的电磁功率 $P _ { \mathrm { ~ e ~ } }$ 减小，直至 $P _ { \mathrm { e } } =$ $P _ { \mathrm { { m } } }$ ，对应图中 $\mathrm { c - b }$ ；而 $\omega _ { \mathrm { m } } < \omega _ { \mathrm { g } }$ ， $\delta$ 继续减小， $P _ { \mathrm { { m } } }$ $> P _ { \mathrm { { e } } }$ ， $\omega _ { \mathrm { m } }$ 增大，直至 $\omega _ { \mathrm { m } } = \omega _ { \mathrm { g } }$ ，此时VSG输出的电磁功率 $P _ { \mathrm { ~ e ~ } }$ 达到最小，对应图中 $\mathsf { b { - } a }$ 。

![](images/c6daa30ca518b5bf88447cfdc4d80ce0293a928a1622c53d3a526c0d648ba939.jpg)  
图7VSG的功角特性曲线Fig.7Power-angle curve of VSG

这样，在惯性和阻尼的作用下，经过往复动态振荡，VSG最终被电网拖入同步，VSG进入新的稳态运行点，输出电磁功率 $P _ { \mathrm { { m } } } = P _ { \mathrm { { e } } }$ ，输出角频率 $\omega _ { \mathrm { m } } =$ $\omega _ { \mathrm { g } }$ ，功角 $\delta = \delta _ { 1 }$ ，对应图中b点。

上述振荡过程可以总结如下：

$_ { \mathrm { a - b } }$ ： $\mathrm { d } \delta / \mathrm { d } t > 0$ $\left( \omega _ { \mathrm { m } } - \omega _ { \mathrm { g } } > 0 \right)$ 且 $\mathrm { d } \omega _ { \mathrm { m } } / \mathrm { d } t > 0$ $\mathsf { b { - c } }$ ： $\mathrm { d } \delta / \mathrm { d } t > 0$ $\left( \omega _ { \mathrm { m } } - \omega _ { \mathrm { g } } > 0 \right)$ 且 $\mathrm { d } \omega _ { \mathrm { m } } / \mathrm { d } t < 0$ $c { - } b$ ： $\mathrm { d } \delta / \mathrm { d } t < 0$ $( \omega _ { \mathrm { m } } - \omega _ { \mathrm { g } } < 0 )$ 且 $\mathrm { d } \omega _ { \mathrm { m } } / \mathrm { d } t < 0$ $\mathtt { b - a }$ ： $\mathrm { d } \delta / \mathrm { d } t < 0$ 1 $\langle \omega _ { \mathrm { m } } - \omega _ { \mathrm { g } } < 0 \rangle$ 且 $\mathrm { d } \omega _ { \mathrm { m } } / \mathrm { d } t > 0$ 。

不难发现，功率的振荡伴随着频率的变化，功角的变化率 $\mathrm { d } \delta / \mathrm { d } t$ （即角频率 $\omega$ 的变化）和频率的变化率 $\mathrm { d } \omega / \mathrm { d } t$ 共同决定了振荡的过程，等效于扰动发生时传统同步发电机的加速和减速过程。因此，为了抑制扰动发生时动态调节过程中的功率振荡，减少频率波动，可以定性得到：在 $^ { \mathrm { a - b } }$ 和 $\displaystyle \mathrm { c - b }$ 加速过程中需要增大虚拟惯性 $J$ 来减少功率的超调，减小频率的偏移；在b-c和 $\mathsf { b { - } a }$ 减速过程中需要减小虚拟惯性 $J$ 来加快功率达到新的平衡点。

# 3.2最优虚拟惯性控制策略

在定性分析的基础上，本文采用线性二次型最优控制方法来定量配置虚拟惯性和虚拟阻尼值。该方法可以用较小的控制能量为代价，减少储能释放的能量，来保持动态功率振荡和频率波动最小，以达到能量和误差综合最优的目的，提高微电网运行的稳定性和经济性[9。下面来具体阐述最优虚拟惯性控制策略。

由式（2）可以得到VSG小信号模型

$$
\Delta \dot { \omega } _ { _ { \mathrm { m } } } = - \frac { D } { J } \Delta \omega _ { _ { \mathrm { m } } } - \frac { 1 } { J } \Delta P
$$

令 $a = - D / J , b = - 1 / J$ ，则式（12）可化简为标准形式

$$
\Delta \dot { \omega } _ { _ { \mathrm { m } } } = a \Delta \omega _ { _ { \mathrm { m } } } - b \Delta P
$$

由于系统达到稳态时 $\Delta \omega _ { \mathrm { { m } } } = 0$ ，则该系统的线性二次型问题可以简化为状态调节器形式，其二次型性能指标为

$$
I = \frac { 1 } { 2 } \int ( H \Delta \omega _ { \mathrm { m } } ^ { 2 } + R \Delta P ^ { 2 } ) \mathrm { d } t = \frac { 1 } { 2 } \int ( \Delta \omega _ { \mathrm { m } } ^ { 2 } + R \Delta P ^ { 2 } ) \mathrm { d } t
$$

式（14）包括两部分能量：一部分是SH△ω²dt称作过程代价，用它来限制动态调节过程中角频率的误差，以保证系统响应具有适当的快速性，取加权矩阵 $\pmb { H } = 1$ ；另一部分是 $\frac { 1 } { 2 } \int R \Delta P ^ { 2 } \mathrm { d } t$ R△P²dt，称作控制代价，用它来限制控制输出功率的幅值及平滑性，以保证系统稳定运行。另外，应当考虑到直流侧的储能，它对限制整个控制过程中总能量输出也能起到重要的作用，从而保证系统具有适当的节能性和经济性，因此取加权矩阵 $\pmb { R } = m ^ { 2 }$ 。

为使式（14）中 $I$ 取极小值，对应的最优解

$$
\Delta P ^ { * } = - \frac { b } { R } F \Delta \omega _ { _ { \mathrm { m } } }
$$

式中， $F = \frac { R } { b } \Bigg ( \frac { a } { b } + \sqrt { \frac { a ^ { 2 } } { b ^ { 2 } } + \frac { 1 } { R } } \Bigg ) \div$ 为Riccati方程 $F ^ { 2 } - \frac { 2 a R } { b ^ { 2 } } F -$ ${ \frac { R } { b ^ { 2 } } } = 0$ =0的正数解。

化简可得

$$
\Delta P ^ { * } = \left( D + \sqrt { D ^ { 2 } + \frac { 1 } { R } } \right) \Delta \omega _ { \mathrm { { m } } }
$$

VSG中的储能可以表示为

$$
E _ { \mathrm { k } } = \frac { 1 } { 2 } J _ { \mathrm { 0 } } \omega _ { \mathrm { m } } ^ { 2 }
$$

因此，功率调度指令突变时VSG输出有功功率

的变化为

$$
\Delta P = - \frac { \mathrm { d } \Delta E _ { \mathrm { k } } } { \mathrm { d } t } = - J \Delta \dot { \omega } _ { \mathrm { m } }
$$

对照式（15)，此时最优解 ${ \Delta } P ^ { * }$ 对应的最优虚拟惯性为

$$
J ^ { * } = \left( D + \sqrt { D ^ { 2 } + \frac { 1 } { R } } \right) \frac { \Delta \omega _ { \mathrm { m } } } { \Delta \dot { \omega } _ { \mathrm { m } } }
$$

代入由式(10)，得

$$
J ^ { * } = \left( { \sqrt { 2 J ^ { * } \frac { U E } { X } } } + { \sqrt { 2 J ^ { * } \frac { U E } { X } + \frac { 1 } { R } } } \right) \frac { \Delta \omega _ { \mathrm { m } } } { \Delta \dot { \omega } _ { \mathrm { m } } }
$$

解得关于 $\boldsymbol { J } ^ { * }$ 的一元二次方程正的解析解

$$
J ^ { * } = 4 A C ^ { 2 } + \sqrt { C ^ { 2 } ( 1 6 A ^ { 2 } C ^ { 2 } + B ) }
$$

式中， $A = \frac { U E } { X } \ , B = \frac { 1 } { R } \ , C = \frac { \Delta \omega _ { \mathrm { m } } } { \Delta \dot { \omega } _ { \mathrm { m } } } \ \mathrm { ~ , }$

当角频率偏差 $\Delta \omega _ { \mathrm { m } } { \in } ( - 0 . 2 \pi , \ 0 . 2 \pi ) \mathrm { r a d / s }$ 且角频率变化率 $\Delta \dot { \omega } _ { _ { m } } \in ( - 0 . 2 4 \pi$ ， $0 . 2 4 \pi ) \mathrm { r a d / s } ^ { 2 }$ 时，微网逆变器最优虚拟惯性 $\boldsymbol { J } ^ { * }$ 的取值如图8所示，此时对应的虚拟阻尼 $D$ 根据式（10）确定；当角频率偏差和变化率不在上述范围时，虚拟惯性 $\boldsymbol { J } ^ { * }$ 取定值200，虚拟阻尼根据式（10）确定。

![](images/80fee91644b0e81d98dff9226156a61820e76d317bdf3556b4b21fce89006aae.jpg)  
图8最优虚拟惯性取值曲线族

这样，最优虚拟惯性控制策略就将VSG的下垂系数、虚拟惯性和虚拟阻尼3个控制自由度有机结合起来，兼顾了系统的稳定性和动态性能指标，实现VSG关键参数的优化配置的同时解决了因虚拟惯性而引入的功率振荡问题。

# 4 仿真结果与分析

为了验证上述理论分析结果，利用Matlab建立了如图1所示的微网逆变器仿真模型。逆变器容量为 $1 0 0 \mathrm { k V \cdot A }$ ，变压器联结组号为Dy11，变压比为$2 7 0 \mathrm { V } / 4 0 0 \mathrm { V }$ ，主电路参数如下表表示。

表VSG系统参数 Tab．Parameters ofVSG   

<html><body><table><tr><td>参数</td><td>数值</td><td>参数</td><td>数值</td></tr><tr><td>额定功率/kV·A</td><td>100</td><td>滤波电容/uF</td><td>90</td></tr><tr><td>额定线电压/V</td><td>380</td><td>功角下垂系数m/(Hz/kW)</td><td>0.005</td></tr><tr><td>直流侧电压/V</td><td>600</td><td>无功下垂系数n/(V/kvar)</td><td>0.076</td></tr><tr><td>桥臂电感/mH</td><td>0.24</td><td>开关频率/kHz</td><td>5</td></tr></table></body></html>

起始时刻，微网逆变器并网空载稳定运行，直至4s时突加给定 $5 0 \mathrm { k W }$ 。为了对比分析，仿真给出了采用不同控制策略时的输出有功功率波形，如图9所示。可以发现，采用恒定虚拟惯性时，功率输出没有超调，相当于欠阻尼状态，2s才达到功率给定值，动态响应过慢，调节时间过长；而采用自适应虚拟惯性时，动态响应非常快，但是出现了严重的功率超调，动态瞬时功率达到了 $8 0 \mathrm { k W }$ ，而且在动态调节过程中功率出现不断的振荡，达到稳态的时间较长；对比前两种控制策略，采用最优虚拟惯性时，功率动态响应较快，0.75s即达到功率给定，略有超调，能够很快进入稳态，没有动态的振荡。

![](images/50d995903ff8b33075c38b66191e032e868fcf0d72e2d04bbc2fc3e3184f532e.jpg)  
图9采用不同控制策略时的输出功率Fig.9Output active power of VSG in differentcontrol strategies

图10给出了系统的频率响应波形，从图中可以看出，采用恒定虚拟惯性时频率超调最小，但达到稳态时间最长；采用自适应虚拟惯性时频率出现振荡，很难达到稳态；采用本文所提出的最优虚拟惯性时，频率超调在允许的范围内，而且能够很快地达到稳态工作点。

![](images/0b48f838776800029f2167208f489e1d9d9a2537702323696ca139fce1a9ca24.jpg)  
Fig.8Curve family of optimal virtual inertia   
图10采用不同控制策略时的频率  
Fig.10Frequency of VSG in different control strategies

# 5 实验结果

为了进一步验证所提方案的有效性，本文在一台 $1 0 0 \mathrm { k V \cdot A }$ 的实验样机上进行了实验验证。电网线电压有效值和频率分别为 $3 8 0 \mathrm { V }$ 和 $5 0 \mathrm { { H z } }$ ，VSG的直流母线电压为 $6 0 0 \mathrm { V }$ ，其他系统参数同仿真模型，见上表。

为了对比分析，图11为对 $J$ 和 $D$ 选择的一种极端情况，由图11a可以看出，突加功率给定之后，输出电流增加并且超调，超过瞬时电流保护值，逆变器因保护而停机，相应的输出功率波形如图11b所示。

![](images/a239ba3e90ee6693765f8ebfd205201c2108fa2ff2b1ea0ae03499dc98bfd3d3.jpg)  
图11瞬时过电流保护实验结果 Fig.11Experimental results of over-current

图 $1 2 \sim$ 图14分别给出了在不同控制策略下，VSG开机从0kW阶跃到 $5 0 \mathrm { k W }$ 时并网电流和输出

![](images/ef3684952906c85839bfc40bacd5c2632bc76da0a7fcf1daa7a2e20c70a1c8c7.jpg)  
图12采用恒定虚拟惯性时实验结果  
Fig.12Experimental results with constant virtual inertia

功率的动态响应情况。

采用恒定虚拟惯性控制策略时，功率给定突加$5 0 \mathrm { k W }$ 阶跃，并网电流缓慢增加，1s后才达到稳态值，如图12a所示；虽然避免了功率超调，但是调节时间过长，对应的功率波形如图12b所示，可以看出1s左右功率才达到给定值，与仿真结果分析一致。

采用自适应虚拟惯性控制策略，功率给定突加$5 0 \mathrm { k W }$ 阶跃时，并网电流和输出功率出现严重超调和振荡，2s左右才达到稳态值，如图13所示，由于采用Bang-Bang控制，虚拟惯性频繁突变，造成持续振荡，与理论分析一致。

![](images/29c9919afc46737a75d6ca39a20aada46634d02ccab50135a714d110f5e561e6.jpg)  
图13采用自适应虚拟惯性时实验结果

采用最优虚拟惯性控制策略时，功率给定突加$5 0 \mathrm { k W }$ 阶跃，并网电流和功率略有超调并迅速达到稳态运行点，动态响应响应速度快，调节时间短，在保证动态性能指标的前提下也解决了功率和频率振荡的问题，实验结果如图14所示。

![](images/d7a17b375f6f9b043f8025553aa95f9d3cbe541a001ca0389e07ed4f2891d98f.jpg)  
Fig.13Experimental results with adaptive virtual inertia   
图14采用最优虚拟惯性时实验结果  
Fig.14Experimental results with optimal virtual inertia

# 6 结论

本文针对基于VSG控制的微网逆变器的主电路拓扑、控制结构和数学模型进行了研究，通过根轨迹分析了影响VSG稳定性和动态性能的参数变化范围；以功率和频率变化量为约束条件，提出了最优虚拟惯性控制策略，通过对VSG参数进行优化配置解决了VSG单机并网时存在的频率和功率振荡问题，Matlab仿真和实验结果均验证了该控制策略的正确性和有效性。由于最优虚拟惯性的引入，在兼顾动稳态性能的基础上，大大加快了动态过程中VSG与电网之间功率的交换。因此，由于惯性、阻尼和调频调压环节引入造成的多VSG并联均流和功率分享减慢的问题在一定程度上是否也可以通过最优虚拟惯性得到解决还有待进一步的研究。

# 参考文献

[1] 吕志鹏，盛万兴，钟庆昌，等．虚拟同步发电机 及其在微电网中的应用[J]．中国电机工程学报， 2014，34(16):2591-2603. Lü Zhipeng, Sheng Wanxing, Zhong Qingchang, et al. Virtual synchronous generator and its applications in micro-grid[J].Proceedings of the CSEE,2014, 34(16): 2591-2603.   
[2] 张兴，朱德斌，徐海珍．分布式发电中的虚拟同 步发电机技术[J]．电源学报，2012，10(3)：1-6. Zhang Xing,Zhu Debin,Xu Haizhen.Review of virtual synchronous generator technology in distributed generation[J]. Journal of Power Supply, 2012,10(3): 1-6.   
[3] JaberAlipoor, Yushi Miura,Toshifumi.Power system stabilization using virtual synchronous generator with adoptive moment of inertia[J]. IEEE Emerging and Selected Topics in Power Electronics,2014, 3(2): 451-458.   
[4] 杜威，姜齐荣，陈蛟瑞．微电网电源的虚拟惯性频 率控制策略[J]．电力系统自动化，2011，35(23)： 26-31. Du Wei, Jiang Qirong, Chen Jiaorui. Frequency control strategy of distributed generations based on virtual inertia in a microgrid[J].Automation of Electric Power Systems,2011,35(23): 26-31.   
[5] Shintai T,Miura Y, Ise T. Oscillation damping of a distributed generator using a virtual synchronous generator[J]. IEEE Transactions on Power Delivery, 2014,29(2): 668-676.   
[6] 杜燕，苏建徽，张榴晨，等．一种模式自适应的 微网调频控制方法[J]．中国电机工程学报，2013, 33(19): 67-75. Du Yan,Su Jianhui, Zhang Liuchen,et al.A mode adaptive frequency controller for microgrid[J]. Proceedings of the CSEE,2013,33(19): 67-75.   
[7] Alipoor J,Miura Y, Ise T. Distributed generation grid integration using virtual synchronous generator with adoptive virtual inertia[C]. IEEE Energy Conversion Congress and Exposition, 2013: 4546-4552.   
[8] 倪以信，陈寿孙，张宝霖．动态电力系统的理论 和分析[M]．北京：清华大学出版社，2002.   
[9] 李传江，马广富．最优控制[M]．北京：科学出版 社，2011.