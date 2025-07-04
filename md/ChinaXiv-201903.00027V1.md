# 基于比例谐振的永磁直驱风电机组高电压穿越控制策略

![](images/e26d06ab0cd998a4d7cf3107f95efc423cd76776295008b35264d563795ffc87.jpg)

张明锐尉芬（同济大学电子与信息工程学院上海 201804)

张明锐男 1971年生，博士，教授，博士生导师，主要研究方向为分布式发电与微网技术、电力系统能量管理与优化运行和轨道交通牵引供电系统。

摘要：本文提出一种基于比例谐振的永磁直驱风电机组高电压穿越控制策略。依据电网电压骤升幅度，网侧变流器优先向故障电网输出一定比例的感性无功电流。在直流母线电压超出限值后，超级电容器储存能量以稳定直流母线电压。本文所提策略与传统的PI控制策略相比，能够在静止坐标系下对交流输入信号进行无静差控制。同时，该策略减少了坐标旋转变换，不存在受温度及电路参数影响的耦合项和前馈补偿项，简化了控制算法。仿真结果表明，该控制策略不仅可以保证永磁直驱风电机组在电网高压故障期间不脱网连续运行，又可使该系统为电网电压的恢复提供一定的感性无功。

关键词：永磁同步发电机高电压穿越 比例谐振中图分类号：TM614

# The HVRT Control Strategy of Direct-Driven PMSG Based on Proportional-Resonant Controller

Zhang MingruiWei Fen（Tongji UniversityShanghai201804 China）

![](images/f07460045c82439775a3717e64089d72e9cc87e507099323783e7b7ee270891a.jpg)

尉芬女1993年生，硕士研究生，主要研究方向为分布式发电并网技术。

Abstract: Put forward a HVRT control strategy of direct-driven PMSG based on proportional resonant controller. Based on the extent of grid voltage swell, the grid side converter give priority to output certain inductive reactive current to the fault grid. The super-capacitor stores energy to stabilize the DC bus voltage when the DC voltage exceed the limit. Proportional resonant (PR) controller can control the AC input signal without static difference in stationary reference frame. Compared with the traditional PI control strategy, this strategy reduces the coordinate rotation transform, does not have coupling terms and feed-forward compensation terms which is affected by the temperature and the circuit parameters. The simulation results show that the control strategy can not only ensure the direct-driven PMSG in continuous operation during the fault, but also can make the system provides inductive reactive power for the recovery of the grid voltage.

Keywords: Permanent magnet synchronous generation, high voltage ride through, proportional resonant

# 1 引言

永磁直驱风电机组（PermanentMagnet SynchronousGenerator，PMSG）具有机械损耗小、运行可靠性高、发电效率高和便于维护等优点，近年来在风电场中逐步得到了广泛应用。目前，随着风电机组容量的快速增加，电网电压骤升故障对风电机组安全稳定运行的影响已经引起人们的广泛关注。

电压骤升是一种常见电网异常现象，通常发生在电网无功功率过剩情况下。电容补偿未及时退出、电网单相接地故障、风电场负载突然切除和投入大容量补偿器等都会引起电网电压的骤升。电网电压骤升时，PMSG由于瞬时能量不平衡导致直流母线电压上升，变流器和直流母线电容对过电压和过电流的承受能力有限会引起风电机组脱网。因此，要求风力发电机组在电网电压骤升期间具备一定程度的不脱网连续运行能力，即高电压穿越（HighVoltage RideThrough，HVRT）特性。

近年来，各国逐渐开始重视发电设备高电压穿越问题，并制定高电压穿越标准[1]。各国的标准都是根据本国的电网结构以及新能源发电所占比例决定的。澳大利亚并网导则要求当电网电压骤升至额定电压的 $130 \%$ 时，风电机组应持续 $6 0 \mathrm { m s }$ 而不脱网；电网电压骤升至额定电压的 $120 \%$ 时，风电机组应持续0.4s不脱网；电网电压骤升至1.1倍额定电压时，风电机组应一直保持并网。德国E.ON在并网导则中规定，当电网电压骤升为额定电压的$12 5 \%$ 时，风电机组能保持 $1 0 0 \mathrm { { m s } }$ 运行不脱网，且要求在高电压情况下风电机组需要吸收一定比例的无功电流。

目前，实现永磁直驱风电机组高电压穿越的方案主要分为增加硬件电路和改进系统控制策略。增加的辅助装置又可按照其工作方式分为主动式和被动式，其中主动式主要包括静止同步无功补偿器（Static Synchronous Compensator，STATCOM）、静止无功补偿 器（StaticVarCompensator，SVC)及动态电压恢复器（DynamicVoltageRestorer,DVR)，这类装置的特点是将风电机组与电网故障隔离开来，从而实现系统的不脱网安全运行；被动式装置主要有交流撬棒电阻和直流母线斩波电路，故障期间通过额外的卸荷回路来消耗掉系统中多余的能量，以实现故障穿越。

动态电压补偿器主要用来实现双馈感应电机(Doubly-Fed Induction Generator，DFIG）与 恒速异步电机（Fixed Speed Induction Generator，FSIG)的故障穿越[2-4]。DVR串联接入风电机组机端和电网公共连接点之间，电网故障时，利用DVR通过变压器在风电机组和电网之间实现串联电压补偿。文献[5]提出了变速恒频双馈风电场与STATCOM间的无功电压协调控制方案，在电网电压故障时对风电机组转子侧及网侧变流器与STATCOM进行无功功率分配，协调控制实现风电场LVRT。文献[6]将STATCOM通过电抗器串联在风电机组的公共连接点上，在电网电压骤升时，采用双闭环反馈控制策略对 STATCOM进行控制，使其吸收电网容性无功并补偿感性无功，实现风电机组的高电压穿越。文献[7]所提出的HVRT控制策略基于电网电压和发电侧负载电流的信息对直流母线电压的参考值进行在线调整，以增加并网逆变器在高电压故障期间的控制裕度。文献[8]根据电网电压骤升幅度及直流母线电压升高程度利用模式选择器设定有功电流与无功电流参考值，使永磁直驱风电机组具备高电压故障穿越能力。文献[9]通过卸荷电阻的升级和并网逆变器控制环节的优化，实现了PMSG 较好的HVRT功能。文献[10]从有功功率和无功功率的角度提出一种联合紧急变桨技术、并联直流电容器技术和网侧变流器电压控制方式的方法，提升风电系统的故障穿越能力。文献[11]在转子旋转坐标系中采用PR控制器控制定子电压。与传统PI控制策略相比，该策略能够简化控制算法，提高控制系统的鲁棒性。文献[12]对PI控制与PR控制进行了对比分析，得出在逆变器的控制中可以用PR控制代替传统PI控制的结论。文献[13]采用基于PR控制器的网侧变换器控制系统，实现维持直流电压稳定及调节功率因数的控制任务，该方法易于实现对DFIG 系统低次谐波电流的补偿，能减小控制算法的实现难度。

本文将PR控制器引入到永磁同步发电系统网侧变流器的电流调节中，提出一种基于比例谐振（ProportionalResonant，PR）的永磁直驱风电机组的高电压穿越控制策略。在电网电压骤升时，改变网侧工作状态，使风力发电机组快速向电网提供感性无功。在直流母线电压超出限值时，超级电容器储存多余的电网能量以维持直流母线电压恒定，使PMSG具备高电压穿越的能力。文中采用一种基于固态变压器的永磁直驱风电并网系统对所提控制策略进行验证[14]

# 2 风电系统并网模型

基于固态变压器的永磁同步风力发电机并网系统能够实现整流和逆变部分的电气隔离，明显减小并网冲击电流，是有效的永磁同步风力发电机并网方法。系统结构如图1所示，正常工作时，风力机带动PMSG产生三相交流电，定子侧输出的交流电通过机侧整流器转换成低压直流，通过单向全桥逆变器调制成高频方波，高频变压器将电压升高后经单相全桥整流器转换为直流，并网逆变器将高压直流电转换成稳定的三相交流电，输送至电网。

![](images/f3d15a14dd3ac6ada7df48507160ec369c877589b88abfe389fd5ac755cbec6e.jpg)  
Fig.1A grid-connected PMSG wind power system

永磁直驱风电机组控制系统包括机侧变流器控制系统、直流升压环节控制系统、网侧变流器控制系统和超级电容控制系统。其中直流升压环节的两个变流器均采用PWM控制[15]，超级电容器采用电压电流双闭环进行控制。文中机侧变流器采用解耦的PI控制器进行控制[16]，网侧变流器采用基于比例谐振的电压定向控制。其控制框图如图1所示，图中， $i _ { \mathrm { s } }$ 为发电机定子侧电流； $u _ { \mathrm { s d } }$ 、 $u _ { \mathrm { s q } }$ 分别为定子电压的d轴、q轴分量； $i _ { \mathrm { s d } }$ ， $i _ { \mathrm { s q } }$ 分别为定子电流的d轴、q轴分量； $u _ { \mathrm { g } }$ ， $i _ { \mathrm { g } }$ 分别为电网侧电压、并网电流； $u _ { \mathrm { g a } } .$ ， $u _ { \mathrm { g \beta } }$ 分别为网侧变流器输出电压的 $\mathbf { \alpha } _ { \mathrm { ~ \textsc ~ { ~ a ~ } ~ } }$ 轴、$\beta$ 轴分量； $i _ { \mathrm { g a } } , i _ { \mathrm { g \beta } }$ 分别为并网电流的 $\mathbf { a }$ 轴、 $\beta$ 轴分量； $e _ { \mathrm { a } }$ ， $e _ { \beta }$ 分别为并网电压的 $\mathbf { \alpha } _ { \mathrm { ~ \tiny ~ d ~ } }$ 轴、 $\beta$ 轴分量。

# 3 电网电压骤升下PMSG暂态过程分析

直驱型风力发电机组采用图1所示并网系统，定子端与电网完全隔离，电网故障不会对发电机产生直接影响，因此在分析HVRT控制策略时只需将网侧变流器的控制作为主要研究对象。

网侧变流器在同步旋转坐标系下的稳态方程为

$$
\begin{array} { r } { \left\{ \boldsymbol { u } _ { _ { \mathrm { g d } } } = R \boldsymbol { i } _ { _ \mathrm { g d } } + \boldsymbol { e } _ { _ \mathrm { d } } - \omega L \boldsymbol { i } _ { _ \mathrm { g q } } \right. } \\ { \left. \left[ \boldsymbol { u } _ { _ \mathrm { g q } } = R \boldsymbol { i } _ { _ \mathrm { g q } } + \boldsymbol { e } _ { _ \mathrm { q } } + \omega L \boldsymbol { i } _ { _ \mathrm { g d } } \right. \right. } \end{array}
$$

式中， $u _ { \mathrm { g d } }$ 、 $u _ { \mathrm { g q } }$ 分别为网侧变流器输出电压矢量的d、q轴分量； $i _ { \mathrm { g d } }$ 、 $i _ { \mathrm { g q } }$ 分别为网侧变流器输出电流矢量的d、q轴分量； $e _ { \mathrm { d } }$ ， $e _ { \mathrm { q } }$ 分别为电网电压矢量的d、q轴分量； $R$ 为网侧变流器进线电阻； $L$ 为网侧变流器进线电感； $\omega$ 为电网角频率。

根据电压空间矢量调制理论，在不产生过调制情况下，调制比 $\mathbf { \nabla } _ { m }$ 需满足

$$
m = \frac { \sqrt { u _ { \mathrm { g d } } ^ { 2 } + u _ { \mathrm { g q } } ^ { 2 } } } { u _ { \mathrm { d c } } / 2 } \leqslant \frac { 2 } { \sqrt { 3 } }
$$

式中， $u _ { \mathrm { d c } }$ 为直流母线电压。

由图2及式（2）联合得出：若功率因数角 $\varphi$ 一定，则其输出电压矢量 $u _ { \mathrm { g } }$ 的末端必然落在阻抗三角形的斜边上，且最大值 $u _ { \mathrm { g m a x } }$ 受到直流侧电压 $U _ { \mathrm { d c } }$ 的严格限制。

![](images/a25ec28db944a304b3174418223a568a7683a78f0c486a3ebbceea094c0de6de.jpg)  
图1永磁同步风力发电并网系统  
图2网侧变流器稳态电压空间矢量关系  
Fig.2Space voltage vector relation of grid side converter

当采用电网电压定向控制时，即d轴与电网电动势矢量 $E$ 重合时，电网电动势矢量q轴分量 $e _ { \mathrm { q } } =$ 0， $e _ { \mathrm { d } } = E$ （ $E$ 为电网相电压峰值)，将式（1）代人式（2）且同时忽略电阻 $R$ 可得

$$
u _ { _ { \mathrm { d c } } } \geqslant \sqrt { 3 } \sqrt { ( E + \omega L i _ { _ \mathrm { g d } } ) ^ { 2 } + ( \omega L i _ { _ \mathrm { g q } } ) ^ { 2 } }
$$

从图1知，PMSG主回路功率平衡方程式为

$$
P _ { \mathrm { g e n } } - P _ { \mathrm { g r i d } } + P _ { \mathrm { n e g } } = P _ { \mathrm { d c } } = U _ { \mathrm { d c } } I _ { \mathrm { d c } } = U _ { \mathrm { d c } } C { \frac { \mathrm { d } U _ { \mathrm { d c } } } { \mathrm { d } t } }
$$

式中， $P _ { \mathrm { g e n } }$ 为发电机输出有功功率； $P _ { \mathrm { g r i d } }$ 为风机系统注入电网的有功功率； $P _ { \mathrm { n e g } }$ 为从电网注入到风机系统的逆向能量； $P _ { \mathrm { d c } }$ 为变流器直流母线功率； $U _ { \mathrm { d c } }$ 为直流侧电压； $\boldsymbol { I } _ { \mathrm { d c } }$ 为直流侧电流； $C _ { \mathrm { d c } }$ 为直流侧稳压电容。

由式（3）可知，当电网电压升高时，直流母线电压也将随之升高。由式（4）可知，当电网电压骤升时，电网侧功率无法正常送出，功率由电网侧流入变流器，导致直流母线电压升高，直接威胁变流器的正常运行。因此为保证电网电压骤升期间风力发电机组的正常运行，需采取有效的高电压穿越控制策略。

# 4基于比例谐振的永磁同步电机高电压穿越控制

# 4.1比例谐振控制器

比例谐振（ProportionalResonant，PR）控制器，是由比例环节和广义积分（GeneralizedIntegral,GI）环节组成，其传递函数为

$$
G _ { \mathrm { { P R } } } \left( s \right) = K _ { \mathrm { { P } } } + K _ { \mathrm { { r } } } \frac { s } { s ^ { 2 } + \omega _ { \mathrm { { 0 } } } ^ { 2 } }
$$

式中， $\omega _ { 0 }$ 为谐振频率； $K _ { \mathfrak { p } }$ ， $K _ { \mathrm { r } }$ 分别为比例常数和积分时间常数。当给定交流信号的角频率为 $\omega _ { 0 }$ 时，由上式可知，此时的幅值 $G _ { \mathrm { P R } }$ 变得无穷大，即可实现交流信号的无静差跟踪。

在实际系统中，由于受模拟系统元器件参数精度和数字系统精度的限制，PR控制器不易实现，因此文中采用准 PR控制器，其传递函数为[17]

$$
G ( s ) = K _ { \mathrm { p } } + \frac { 2 K _ { \mathrm { r } } \omega _ { \mathrm { c } } s } { s ^ { 2 } + 2 \omega _ { \mathrm { c } } s + \omega _ { 0 } ^ { 2 } }
$$

由文献[18-19]可知，控制器的带宽 $\omega _ { \mathrm { { c } } }$ 体现了跟踪输入信号的能力，为了提高响应速度，系统应具有较大的带宽，但随着带宽的增加，开关频率等高频干扰噪声将对系统产生影响。故须折中考虑加以选取。 $\omega _ { \mathrm { c } }$ 不仅影响控制器的增益，还影响控制器的带宽。随着 $\omega _ { \mathrm { c } }$ 的增加，控制器的带宽和增益都会增大。依据GB/T15945—2008的定义，由用户冲击负荷引起的电力系统频率偏差允许波动的限值为$\pm 0 . 5 \mathrm { H z }$ ，则有 $\omega _ { \mathrm { c } } / \pi = 1 . 0 \mathrm { H z }$ ，为 $3 . 1 4 \mathrm { r a d / s }$ 。

$K _ { \mathrm { r } }$ 只影响控制器的增益，而不影响控制器的带宽。控制器的增益和 $K _ { \mathrm { r } }$ 成正比。 $K _ { \mathfrak { p } }$ 影响系统的带宽与稳定性，随着增益值增加，系统的带宽、稳定裕度先增大再减小，因此需要选取最优增益系数以实现系统稳定域量最大。

综上，准控制器的设计步骤如下： $\textcircled{1}$ 根据需要选择控制器的带宽 $\omega _ { \mathrm { c } }$ 。 $\textcircled{2}$ 根据控制器需要的增益选择 $K _ { \mathrm { r } }$ 。 $\textcircled{3}$ 根据最优增益系数选择 $K _ { \mathfrak { p } }$

在网侧变流器的控制中，将旋转坐标系下的有功电流和无功电流转换到静止坐标系下，利用准PR控制器对其进行调节。同时对并网逆变器准PR控制系统进行设计，以实现风电机组的高电压穿越。

# 4.2网侧变流器无功控制

电网电压骤升期间风力发电机组的无功输出主要取决于电网电压骤升幅度，具体逻辑关系可参考德国E.ON公司的HVRT并网要求：并网点电压骤升至1.1倍标称值及以上时，机组需按电网电压每升高 $1 \%$ ，至少提供 $2 \%$ 额定无功电流的原则优先对故障电网进行补偿，即

$$
\left| \boldsymbol { i } _ { \mathrm { g q } } ^ { * } \right| \geqslant 2 \frac { U _ { \mathrm { r e f } } - U _ { \mathrm { r e f } } ^ { * } } { U _ { \mathrm { r e f } } ^ { * } } \left| \boldsymbol { i } _ { \mathrm { N } } ^ { * } \right|
$$

式中， $i _ { \mathrm { g q } } ^ { * }$ 为无功电流； $U _ { \mathrm { r e f } }$ 为实测电网电压有效值；  
$i _ { \mathrm { N } }$ 为额定电流。

同时，为避免网侧变流器过电流，要求有功电流的幅值 $i _ { \mathrm { g d } } ^ { * }$ 需满足

$$
i _ { \mathrm { g d } } ^ { * } \leqslant \sqrt { i _ { \mathrm { m a x } } ^ { 2 } - i _ { \mathrm { g d } } ^ { 2 } }
$$

式中， $i _ { \mathrm { m a x } }$ 为网侧变流器允许的最大值。

网侧变流器在同步变流器下的动态方程为

$$
\left\{ \begin{array} { l l } { L \displaystyle \frac { \mathrm { d } i _ { _ \mathrm { g d } } } { \mathrm { d } t } = u _ { _ \mathrm { g d } } - R i _ { _ \mathrm { g d } } - e _ { _ \mathrm { d } } + \omega L i _ { _ \mathrm { g d } } } \\ { L \displaystyle \frac { \mathrm { d } i _ { _ \mathrm { g d } } } { \mathrm { d } t } = u _ { _ \mathrm { g q } } - R i _ { _ \mathrm { g q } } - e _ { _ \mathrm { q } } - \omega L i _ { _ \mathrm { g d } } } \end{array} \right.
$$

式中， $u _ { \mathrm { g d } }$ 、 $u _ { \mathrm { g q } }$ 分别为网侧变流器输出电压的d、q轴分量； $i _ { \mathrm { g d } }$ ， $i _ { \mathrm { g q } }$ 分别为网侧变流器输出电流的d、q轴分量。网侧变流器的控制框图如图3所示，将$i _ { \mathrm { g q 1 } } ^ { * }$ 与 $i _ { \mathrm { g q 2 } } ^ { * }$ 作为 selectorl的输入；将 $i _ { \mathrm { g d 1 } } ^ { * }$ 和 $i _ { \mathrm { g d } 2 } ^ { * }$ 作为selector2的输入信号。

![](images/ccc0ab6b922962e5ba6cff13c09a06eca94e811143234eed0b4e0296bfa6262c.jpg)  
图3网侧变流器PI控制系统

电网电压正常情况下，电网电压标幺值不超过1.1，则无功电流参考值选定 $i _ { \mathrm { g q 1 } } ^ { * }$ ，给定为0，同时有功电流 $i _ { \mathrm { g d 1 } } ^ { * } < i _ { \mathrm { g d 2 } } ^ { * }$ 时，则有功电流参考值选定 $i _ { \mathrm { g d 1 } } ^ { * }$ 。

当电网电压标幺值超过1.1时，无功电流参考值选为 $i _ { \mathrm { g q 2 } } ^ { * }$ ，此时，有功电流 $i _ { \mathrm { g d 1 } } ^ { * } > i _ { \mathrm { g d 2 } } ^ { * }$ 时，有功电流参考值选定为 $i _ { \mathrm { g d } 2 } ^ { * }$ 。与此同时，实时监测直流母线电压值，在直流母线电压超过限值之后将能量储存在超级电容中，保证风力发电机组的正常运行。

# 4.3基于比例谐振的控制系统

假定三相电网电压平衡，三相并网逆变器输出电流在静止 $\alpha \beta$ 坐标系下的动态方程为

$$
\left\{ \begin{array} { l l } { { \displaystyle { \cal L } \frac { \mathrm { d } i _ { \mathrm { g a } } } { \mathrm { d } t } = u _ { \mathrm { g a } } - R i _ { \mathrm { g a } } - e _ { \mathrm { a } } } } \\ { { \displaystyle { \cal L } \frac { \mathrm { d } i _ { \mathrm { g \beta } } } { \mathrm { d } t } = u _ { \mathrm { g \beta } } - R i _ { \mathrm { g \beta } } - e _ { \mathrm { \beta } } } } \end{array} \right.
$$

网侧变流器的控制系统如图4所示。

![](images/1eb0038ec3df6e80e8f7bc75a997538c9a96a0001ad62f93846c3d884be49709.jpg)  
图4网侧变流器PR控制系统

由图4与图3对比可以看出，网侧变流器PR控制方式减少了电流及电压控制指令的坐标旋转变换，无需考虑耦合项 $\omega L i _ { \mathrm { g d } }$ ， $\omega L i _ { \mathrm { g q } }$ 和电网电压扰动项 $u _ { \mathrm { d } }$ ，从而消除电路参数和电网电压对系统控制的影响。

# 5 仿真分析

# 5.1系统参数和仿真工况

在Matlab/Simulink中建立图1所示并网系统的仿真模型，网侧变流器采取图4所示控制系统。系统参数如下：对于风力机，额定风速为 $1 2 \mathrm { m / s }$ ，桨叶半径为 $3 1 \mathrm { m }$ ，额定转速为 $2 0 \mathrm { r / m i n }$ ，最佳叶尖速度比为5.6，风能利用系数0.33；永磁同步电机，额定功率1MW，发电机端线电压 $6 9 0 \mathrm { V }$ ，永磁体磁链 $6 . 2 7 \mathrm { W b }$ ，极对数48，定子d、q轴电感 $L _ { \mathrm { d } } = L _ { \mathrm { q } } =$ $2 \mathrm { m H }$ ，转动惯量为 $2 . 5 \times 1 0 ^ { 4 } \mathrm { k g \cdot m } ^ { 2 }$ 。

根据澳大利亚并网导则，分析在两种不同工况下HVRT效果。

工况1：电网电压在0.5s时骤升至 $1 . 3 \mathrm { p u }$ ，持续$6 0 \mathrm { m s }$ 至0.56s，恢复至正常电压；

工况2：电网电压在0.5s时骤升至 $1 . 2 \mathrm { p u }$ ，持续$4 0 0 \mathrm { { m s } }$ 至0.9s，恢复至正常电压。

# 5.2 HVRT仿真分析

图5为工况1时电网端故障电压。图6、图7和图8分别为采用及未采用HVRT控制策略时，直流母线电压、网侧变流器输出功率及网侧相电流波形图。

![](images/b6f23f50f5799eb7ea19abdd0d036830b09cbb52a6de51ba8cb00af8a7b7d2e5.jpg)  
Fig.3PI control system for grid converters   
图5电网故障电压

![](images/fa8bd0f2e353ecc793403241079899f9b0a3676b20356b4c8744cb2e0b745d58.jpg)  
Fig.4PR control system for grid converters   
Fig.5 Grid fault voltage   
图6直流母线侧电压  
Fig.6DC bus side voltage

由图6可知，采用高电压穿越控制策略后，直流母线电压在故障期间由骤升至 $1 . 3 \mathrm { p u }$ ，随后降至

![](images/25761b23d02dd6106cbf9ae72103df13a4adb6e5ea27e78750eedc9f5365e3b6.jpg)  
图7变流器有功功率和无功功率波形

![](images/017f38c17003e71191f8aad35cdc02f7782fc99bf2b7532e61c2348035167217.jpg)  
Fig.7Active power and reactive power waveform of the converter

$1 . 1 8 \mathrm { p u }$ 变为保持在 $1 . 0 1 \mathrm { { p u } }$ 稳定运行。由图7可知，有功功率由骤升至 $1 . 6 \mathrm { p u }$ 变为在骤升后降至 $0 . 8 \mathrm { p u }$ 后变为 $1 . 0 \mathrm { p u }$ 稳定并网；网侧变流器向电网提供的无功功率由 $0 . 0 5 \mathrm { { p u } }$ 变为 $0 . 2 5 \mathrm { p u }$ 。由图8可知，采用本文所提控制策略，故障期间电流波动有了明显降低。

![](images/f691421157c5fc0a8c5390faf06cefa62017e53ffc53484675753d9b58427f68.jpg)  
图8网侧相电流波形  
图9为工况2时电网端故障电压。图10、图  
图9电网故障电压Fig.9 Grid fault voltage

11和图12分别为采用及未采用HVRT控制策略时，直流母线电压、网侧变流器输出功率及网侧相电流的仿真波形。

由图10可知，采用高电压穿越控制策略后，直流母线电压在故障期间由骤升至 $1 . 3 \mathrm { p u }$ 变为 $1 . 0 3 \mathrm { p u }$ 稳定运行。由图11可知，有功功率由骤升至 $1 . 3 \mathrm { p u }$ 随后降至 $1 . 1 5 \mathrm { p u }$ 变为降至 $0 . 9 \mathrm { p u }$ 后变为 $1 . 0 \mathrm { p u }$ 稳定并网；网侧变流器向电网提供的无功功率由 $0 . 0 5 \mathrm { { p u } }$ 变为 $0 . 1 \mathrm { p u }$ 。由图12可知，采用本文所提控制策略，故障期间电流波动有了明显降低。

![](images/2a5e87c603dfc0f3f764ff64cdf266e61d5f779b32851a71fb1e2775dcdaf6af.jpg)  
图10直流母线侧电压

![](images/ba84156e5bf7f0c790ae76402308c2d70edccfc671d19ba315acc0b29a58d08f.jpg)  
Fig.10DC bus side voltage   
图11变流器有功功率和无功功率波形

![](images/98029e74c02ba4f88b5af2eec9fff7ea44bed4a3cd86bc2d61e77a26cb26d703.jpg)  
Fig.8Phase current of grid side   
Fig.11Active power and reactive power waveform of   
图12网侧相电流波形  
Fig.12Phase current of grid side

仿真结果表明，在电网电压骤升期间，改变网侧变流器控制模式，结合超级电容储能电路储存直流侧积累的多余能量，可以避免直流母线过电压，保证风力发电机组正常运行，提高风力发电机组高电压穿越能力。

# 6 结论

本文主要研究了高电压故障期间永磁同步风电机组网侧变流器的控制策略，对网侧变流器PI控制系统及PR控制系统分别进行了分析。详细分析了网侧变流器故障前后的不同控制方法，利用模式选择器进行有功电流及无功电流的参考值的设定。当直流母线电压超出限值时，该控制策略利用超级电容能够维持直流母线电压的稳定。仿真结果也表明，本文所提出的控制策略能够实现高电压穿越，为未来直驱式风力发电的并网研究提供了一定的理论价值。

# 参考文献

[1] 郜亚秋，肖鹏，张建，等，直驱变流器高压穿越 控制策略研究[J]．现代电子技术，2015，38(9)： 117-124. Gao Yaqiu,Xiao Peng, Zhang Jian.et al. Study on high-voltage ride through control strategy of direct drive converter[J].Modern Electronic Technique, 2015,38(9): 117-124.   
[2] 洪芦诚，魏应冬，姜齐荣，等．基于动态电压调 节器的风电机组低电压穿越策略[J]．电力系统自 动化，2011，35(16)：32-37. Hong Lucheng,Wei Yingdong, Jiang Qirong,et al. Low voltage ride through strategy for wind turbine systems using dynamic voltage restorers[J]. Automation of Electric Power Systems,2011,35(16): 32-37.   
[3] Rini Ann Jerin A,Palanisamy Kaliannan, Umashankar Subramaniam.Improved fault ride through capability in DFIG based wind turbines using dynamic voltage restorer with combined feedforward and feed-back control[C]. IEEE Access, 2017(99): 1-9.   
[4] Gkavanoudis SI,Demoulias C S.FRT capability of a DFIG in isolated grids with dynamic voltage restorer and energy[C]. IEEE International Symposium on Power Electronics for Distributed Generation Systems,2014: 1-8.   
[5] 赵晶晶，胡晓光，吕雪，等．含 STATCOM的双 馈电机风电场无功电压协调控制策略[J]．电工电 能新技术，2016，35(10)：17-22. Zhao Jingjing, Hu Xiaoguang, Lv Xue,et al. Research on coordination control strategy of DFIG wind farm with crowbar circuit[J].Advanced Technology of Electrical Engineering and Energy, 2016,35(10): 17-22.   
[6] 叶盛峰，王维庆，王海云．基于STATCOM风 电机组高电压穿越技术[J]．高压电器，2017, 53(5): 35-40. Ye Shengfeng,Wang Weiqing,Wang Haiyun.High voltage ride-through technology of wind generators based on STATCOM[J]. High Voltage Apparatus, 2017, 53(5): 35-40.   
[7] 郑重，耿华，杨耕．新能源发电系统并网逆变器 的高电压穿越控制策略[J]．中国电机工程学报, 2015，35(6):1463-1472. Zheng Zhong,Geng Hua, Yang Geng.High voltage ride-through control strategy of gridconnected inverter for renewable energy systems[J]. Proceedings of CSEE,2015,35(6): 1463-1472.   
[8] 马伟娜，白恺，宋鹏，等．基于双模控制的永磁直 驱型风力发电机组高电压穿越控制策略的研究[J]. 现代电力，2015，32(3)：13-18. Ma Weina, Bai Kai, Song Peng, et al. The research on control strategy of high voltage ride through for PMSG based on dual-modes control[J]. Mordern Electric Power, 2015,32(3):13-18.   
[9] 艾斯卡尔，朱永利，王海龙．永磁直驱风电机 组HVRT功能开发及检验[J]．电力自动化设备， 2016，36(12):18-23. Aisikaer, Zhu Yongli,Wang Hailong. Development and test of HVRT function for PMSG[J]. Electric Power Automation Equipment, 2016, 36(12): 18-23.   
[10]边晓燕，田春笋，符杨．提升直驱型永磁风电机 组故障穿越能力的改进控制策研究[J]．电力系统 保护与控制，2016，44(9)：69-74. Bian Xiaoyan, Tian Chunsun, Fu Yang. A coordinated control strategy for fault ride-though capacity of direct-drive permanent magnet wind power generating units[J].Power System Protection and Control,2016,44(9): 69-74.   
[11]陈思哲，章云，吴捷，等．双馈风力发电系统的比 例谐振直接电压控制[J]．电力自动化设备，2012, 32(2):104-113. Chen Sizhe, Zhang Yun, Wu Jie, et al. Proportionalresonant direct voltage control of DFIG wind power generation system[J]. Electric Power Automation Equipment, 2012,32(2):104-113.   
[12]刘邓，刘军，陶忠正，等．比例积分与比例谐振 对单项逆变器控制的研究与仿真[J]．电气工程学 报，2015，10(10)：64-68. Liu Deng,Liu Jun, Tao Zhongzheng,et al. Proportional integral and proportional resonant on the research and simulation of single-phase inverter control[[J]. Journal of Electrical Engineering,2015, 10(10): 64-68.   
[13]陈炜，陈成，宋战锋，等．双馈风力发电系统双 PWM变换器比例谐振控制[J]．中国电机工程学 报，2009，29(15)：1-7. Chen Wei,Chen Cheng,Song Zhanfeng,et al. Proportional-resonant control for dual PWM converter in doubly fed wind generation system[J]. Proceedings of CSEE,2009,29(15): 1-7.   
[14]张明锐，黎娜，王之馨．新型永磁风电系统的低 电压穿越性能研究[J]．电力自动化设备，2014, 34(1): 128-134. Zhang Mingrui, Li Na, Wang Zhixin. LVRT ability of PMSG wind power system[J]. Electric Power Automation Equipment,2014, 34(1): 128-134.   
[15]张明锐，林承鑫，徐瑞新．一种基于固态变压器 的光伏发电并网技术[J]．电力系统保护与控制, 2012,40(19): 133-138. Zhang Mingrui, Lin Chengxin,Xu Ruixin. Gridconnected photovoltaic power generation technology based on SST[J]. Power System Protection and Control,2012,40(19):133-138.   
[16]张明锐，陈洁，王之馨，等．一种新型的永磁同 步风力发电机并网系统[J]．电力系统保护与控制, 2013，41(14)：141-148. Zhang Mingrui,Chen Jie,Wang Zhixin,et al.A new permanent magnet synchronous wind-power generation grid-connected system[J]. Power System Protection and Control, 2013,41(14): 141-148.   
[17]杨勇，赵春江．分布式发电系统中并网逆变器比 例谐振控制[J]．电力自动化设备，2011，31(11)： 51-55. Yang Yong, Zhao Chunjiang. Proportional resonance controller of grid-connected inverter for distributed generation system[J].Electric Power Automation Equipment,2011,31(11): 51-55.   
[18]赵清林，郭小强，邬伟扬．单相逆变器并网控制 技术研究[J]．中国电机工程学报，2007，27(16)： 60-64. Zhao Qinglin, Guo Xiaoqiang, Wu Weiyang. Research on control strategy for single-phase gridconnected inverter[J].Proceedings of CSEE,2007, 27(16): 60-64.   
[19]孙强，魏克新，王莎莎，等．PWM变换器在矢量 旋转坐标系下比例谐振控制策略及其鲁棒性设计 [J]．中国电机工程学报，2016，36(5)：1344-1356. Sun Qiang,Wei Kexin, Wang Shasha, et al. A novel proportional resonant control strategy and robust design in rotary vector frames for PWM converters[J]. Proceedings of CSEE,2016,36(5): 1344-1356.