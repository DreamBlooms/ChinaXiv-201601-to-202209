# 考虑运行状态的新能源电力系统广义短路比：广义运行短路比

刘晨曦1，辛焕海」，周瑀涵」，王冠中」，袁辉1(1．浙江大学电气工程学院，浙江省 杭州市 310027)

摘要：新能源多馈入系统存在由于锁相环带宽与电网强度不匹配导致的次/超同步振荡问题，需要准确量化电网强度以保障系统稳定运行。为此，该文考虑新能源系统在实际运行场景中设备出力或端口电压偏离额定值的影响，提出适用于非额定工况下新能源系统电网强度的量化方法，并提出了广义运行短路比指标。本文首先分析了新能源系统运行方式变化时设备的外特性变化规律，近似解耦设备动态特性与端口电气量的相互作用关系；其次，研究了考虑电气量变化时的网络侧导纳矩阵的可解耦性，提出了考虑运行方式的广义运行短路比指标和相应实用化计算方法，据此拓展了广义短路比理论的应用范围。最后，基于算例说明所提方法的有效性。

关键词：次/超同步振荡；非额定工况；广义运行短路比；可解耦性

# 0 引言

高比例新能源、高比例电力电子设备接入电网导致“双高系统”强度相对变弱[1]-[3]，可能引起由于锁相环带宽与电网强度不匹配导致的次/超同步振荡问题[4]-[5]。此外，由于新能源实际出力的随机性[6和交流电网开停机或故障等导致的系统网络架构改变带来的电压扰动，使得实际系统中新能源并网端口特性复杂多变，影响系统的小干扰同步稳定性。

为保证电力系统安全稳定运行，准确度量多馈入系统的电网强度和稳定裕度至关重要。目前工程上主要采用基于短路比(Short CircuitRatio,SCR)的方法[7]-[II]。根据不同适用场景，多馈入短路比可以分为两大类。

第一类指标适用于系统规划阶段，如CIGRE组织基于母线等值思想，通过引入多直流交互因子(multi-infeedinteractionfactor，MIIF)提出的多馈入短路比(multi-infeed short circuit ratio,MISCR)指标[12]-[14]，该指标定义简单，缺乏严格的理论基础；文献[15]-[16]基于模态解耦思想提出的广义短路比（generalized Short CircuitRatio,gSCR）和临界广义短路比(Critical generalized Short Circuit Ratio)指标通过严格的数学变换，将符合条件的多馈入系统近似解耦为若干个单馈入系统，从而将多馈入系统的稳定性分析聚焦于最弱单馈入系统，便于将单馈入系统中短路比的经验移至于多馈入系统，应用十分方便。

另一类适用于实际运行阶段，它考虑了系统非额定运行方式对电网强度的影响，如文献[17]提出的适用于MMC系统的临界运行短路比(CriticalOperatingShortCircuitRatio，COSCR)指标，将交流母线电压约束条件下最小的临界短路比作为COSCR，然而在实际系统存在电压波动时，利用该指标进行稳定性分析可能出现误判的情况；文献[18]提出了适用于多直流馈入系统静态电压稳定性分析的等效运行短路比(equivalentoperatingshortcircuitratio，EOSCR)指标，但该指标未考虑电力电子设备间的相互作用，评估可能过于乐观；文献[19]提出的等价多馈入有效短路比指标(equivalent multi-infeed effective short circuit ratio,EMESCR)综合考虑了阻抗、多馈入相互作用因子、无功功率和节点电压变化等实际因素对系统稳定性的影响，但该指标定义复杂，且未提出对应临界指标，难以量化系统稳定裕度。

为准确度量系统在实际运行阶段的电网强度和稳定裕度，针对锁相环主导的小干扰稳定问题，本文拓展了经过严格数学推导的广义短路比理论的应用范围，提出广义运行短路比(generalizedOperation ShortCircuitRatio,gOSCR)和临界广义运行短 路比(Critical generalized Operation ShortCircuit Ratio, $\operatorname { C g O S C R } )$ ，近似解耦设备动态特性与端口电气量的相互作用关系，并基于摄动理论研究了非额定运行方式下电网强度的量化机理、方法，提出了指标的解析和实用化计算方法，实现了多馈入系统实际运行阶段电网强度和稳定裕度的准确量化评估。最后，分别基于MATLAB/Simulink平台的仿真模型和CloudPSS平台的哈密新能源场站等比例缩小电磁仿真模型说明了所提指标的有效性。

# 1单馈入系统运行阶段小干扰稳定性

# 1.1单馈入系统短路比

考虑变流器接入一个无穷大系统，其控制框图见附录A图A1。目前新能源小干扰稳定问题主要为变流器锁相环(phase locked loop，PLL)控制环节主导的次/超同步振荡，其频段大致在中低频段（204号 $( 1 0 { \sim } 1 0 0 \mathrm { H z } ) ^ { [ 2 0 } \$ 1，此外，根据《光伏发电站接入电力系统技术规定》（GB/T19964-2012）、《风电场接入电力系统技术规定》(GB/T19963)中分别对其无功容量的要求，系统稳定运行时，风电、光伏等新能源功率因数约为1。因此，基于文献[20]-[21]中对变流器内部控制系统多时间尺度特性的描述，在中低频段下，变流器采用开关平均模型，主要考虑电流内环、锁相环和传输网络的动态，功率因数为1。

下面分析新能源设备端口动态外特性。

在全局同步坐标系下，得到变流器在中低频段下以端口电压增量和端口注入电流增量构成的导纳传递函数矩阵动态模型：（详细推导过程见文献[20]):

$$
\boxed { \begin{array} { c } { \left[ \Delta I _ { x } \right] = \underbrace { \left[ Y _ { g 1 1 } \quad Y _ { g 1 2 } \right] } _ { Y _ { g 2 1 } } \left[ \Delta U _ { x } \right] } \\ { \left[ \Delta I _ { y } \right] } \end{array} }
$$

式中：

$$
\left\{ \begin{array} { c } { \displaystyle Y _ { _ { g 1 1 } } = \frac { - \left( 1 - G _ { _ { F F } } \right) } { \left( H _ { \mathrm { i } } + s L _ { \mathrm { f } } \right) } } \\ { \displaystyle Y _ { _ { g 1 2 } } = Y _ { _ { g 2 1 } } = 0 } \\ { \displaystyle Y _ { _ { g 2 2 } } = \frac { - U \left( 1 - G _ { _ { F F } } \right) + P H _ { _ { p l l } } H _ { \mathrm { i } } } { U \left( H _ { \mathrm { i } } + s L _ { \mathrm { f } } \right) \left( 1 + U H _ { _ { p l l } } \right) } } \end{array} \right.
$$

其中， $I _ { x } , I _ { y }$ 分别为设备输出电流在全局同步坐标系下的分量； $U _ { x } , \ U _ { y }$ 分别为并网点（pointofcommoncoupling，PCC）电压在全局同步坐标系下的分量；$\ Y _ { V S C } ( s )$ 为变流器导纳传递函数矩阵; $G _ { F F } { = } 1 / ( 1 { + } \mathrm { T } _ { \mathrm { F F } } s )$ 为电压前馈低通滤波传递函数； $s$ 表示拉普拉斯算子； ${ H _ { i } } \mathrm { { = } } { K _ { i p } } \mathrm { { + } } { K _ { i i } } / \mathrm { { s } }$ ， $K _ { i p }$ 、 $K _ { i i }$ 分别为内环传递函数的PI控制参数； $H _ { p l l } { = } ( K _ { p l l p } { + } K _ { p l l i } / \mathrm { s } ) / \mathrm { s }$ ， $K _ { p l l p }$ 、 $K _ { p l l i }$ 分别为PLL的PI控制参数； $U$ 为并网点电压实际值； $P$ 为设备实际输出有功功率。

在中低频段下，可忽略电压前馈动态[20]，式可转换为：

$$
\left[ \boldsymbol { \Delta } { I _ { x } } \right] = \underbrace { \left[ Y _ { g 1 1 } \quad Y _ { g 1 2 } \right] } _ { Y _ { g 2 1 } } \left[ \boldsymbol { \Delta } { U _ { y } } \right]
$$

式中：

$$
\left\{ \begin{array} { c } { { Y _ { g 1 1 } = Y _ { g 1 2 } = Y _ { g 2 1 } = 0 } } \\ { { { } } } \\ { { Y _ { g 2 2 } = \displaystyle \frac { P H _ { p l l } H _ { \mathrm { i } } } { U \left( H _ { \mathrm { i } } + s L _ { \mathrm { f } } \right) \left( 1 + U H _ { p l l } \right) } } } \end{array} \right.
$$

下面分析传输网络的动态。

交流电网的动态模型为（端口电流以流出节点为正方向):

$$
\begin{array}{c} [ \begin{array} { l } { \Delta I _ { x } } \\ { \Delta I _ { y } } \end{array} ] = \underbrace { \frac { 1 } { Z } F ( s ) } _ { Y _ { n e t } ( s ) } \biggl [ \Delta U _ { y }  \\ { \Delta U _ { y } } \end{array} ]
$$

式中：

$$
{ Z = \omega _ { \mathrm { 0 } } L _ { \mathrm { g } } }
$$

$$
F ( s ) = { \left[ \begin{array} { l l } { \beta ( s ) } & { \alpha ( s ) } \\ { - \alpha ( s ) } & { \beta ( s ) } \end{array} \right] }
$$

其中， $Y _ { n e t } ( s )$ 为交流电网端口导纳矩阵； $Z$ 为交流电网的等效阻抗， $\omega _ { \scriptscriptstyle 0 }$ 为同步旋转速度；$\begin{array} { r } { \beta ( s ) = s \omega _ { 0 } \big / \big ( s ^ { 2 } + \omega _ { 0 } ^ { 2 } \big ) \ , \quad \alpha ( s ) = \omega _ { 0 } ^ { 2 } \big / \big ( s ^ { 2 } + \omega _ { 0 } ^ { 2 } \big ) \ } \end{array}$ 。

基于多变量频率域反馈控制理论[23]，建立新能源并网系统的闭环特征方程：

$$
\operatorname * { d e t } \left\{ \left[ 0 \ \begin{array} { c c } { { 0 } } \\ { { 0 } } \end{array} \right] + \frac { 1 } { Z } F ( s ) \right\} = 0
$$

根据式与短路比之间存在的解析关系，在系统规划阶段，可利用传统短路比指标量化系统的电网强度，短路比定义式为[1].

$$
S C R = \frac { S _ { a c } } { S _ { B } } = \frac { U ^ { 2 } } { Z } \frac { 1 } { S _ { B } } \approx \frac { 1 } { S _ { B } Z }
$$

式中： $S _ { a c }$ 为交流短路容量， $S _ { B }$ 为变流器自身的额定容量。在规划阶段可认为 $U$ 的额定值是1，故$S C R \approx 1 / S _ { _ B } Z$ 。

然而，当设备运行在非额定运行方式时，式表明设备端口电气量，即输出有功功率和端口电压会影响设备的动态特性，从而影响系统的小干扰稳定性。因此，在实际运行阶段，仅利用式定义的短路比指标来量化系统电网强度是不准确的。

# 1.2单馈入系统运行短路比

为解耦设备动态特性与端口电压和输出有功功率的相互作用关系，用运行短路比(OperationShortCircuitRatio,OSCR)完全表征系统非额定运行方式对系统小干扰稳定性的影响，本节基于变流器导纳传递函数矩阵中 $Y _ { g 2 2 }$ 的结构特性，对其进行简化、变换。 $Y _ { g 2 2 }$ 分子、分母同时乘以 $U _ { : }$ ，提出 $P / U ^ { 2 }$ .

式可变换为：

$$
Y _ { _ { V S C } } ( s ) = \underbrace { P } _ { U ^ { 2 } } \left[ 0 \underbrace { H _ { \mathrm { i } } } _ { \left( H _ { \mathrm { i } } + s L _ { f } \right) } \underbrace { U H _ { p l l } } _ { \left( 1 + U H _ { p l l } \right) } \right]
$$

其中， $\hat { Y } _ { V S C } ( s )$ 为提取 $P / U ^ { 2 }$ 后的变流器导纳传递函数矩阵。

此时，变流器单机无穷大系统的闭环特征方程可重新写为：

$$
\operatorname * { d e t } \left\{ \hat { Y } _ { V S C } ( s ) + \frac { U ^ { 2 } } { P } S C R \cdot F ( s ) \right\} = 0
$$

式反映了系统的小干扰稳定性与 $S C R \times U ^ { 2 } / P$ 的显式关系，因此可以将运行短路比定义为：

$$
O S C R = \frac { U ^ { 2 } } { P } B
$$

其中， $B$ 为交流电网的等效导纳。

上式表明，相比于传统单馈入SCR，OSCR考虑了实际运行阶段中变流器的非额定运行方式(实际出力偏离额定功率以及外部电网电压偏离额定值)对系统小干扰稳定性的影响，因此能较为准确地度量运行阶段下单馈入系统的电网强度。

# 1.3单馈入系统临界运行短路比

单馈入系统稳定运行时需满足其OSCR数值大于临界运行 短路比(Critical Operation ShortCircuitRatio,COSCR)。与文献[16]对 $\operatorname { C g S C R }$ 的定义类似，系统COSCR为单馈入系统主导特征值实部为0时的OSCR，如下式所示：

$$
C O S C R = \underset { O S C R } { \arg \left\{ \operatorname* { d e t } \left( \hat { Y } _ { _ { V S C } } ( j \omega ) + O S C R \cdot F ( j \omega ) \right) = 0 \right\} }
$$

式中： $a r g \{ \cdot \}$ 表示求方程的根， $\omega$ 为控制器旋转的角频率。

图1(a)、(b)分别描绘了临界稳定下单馈入系统在不同端口电压和输出有功功率的SCR、COSCR变化曲线。可以看出，端口电压和输出有功功率变化时，系统在临界稳定下的SCR相对变化较大，CSCR无法准确地刻画实际运行系统的稳定边界；相较于SCR，考虑非额定运行方式对系统小干扰稳定性影响的COSCR指标由于 $\hat { Y } _ { _ { V S C } } ( s )$ 仍含有电压项，因此仅随端口电压的改变而改变，不受系统其它电气量变化的影响，验证了COSCR指标在刻画系统稳定边界的有效性。

![](images/d61b87400f0af34d15744a4ff2f54d3f416073ea2c76141cdff4dc632c3f4bce.jpg)  
图1临界稳定下单馈入系统SCR、OSCR变化曲线 Fig.1SCR and OSCR change curve of SIPES under critical stability with various voltage or active power.

# 2多馈入系统运行阶段小干扰稳定性

文献[15]基于模态解耦的思想，提出了适用于规划阶段多馈入系统电网强度评估的广义短路比指标。类比该思想，本节将上述指标推广至考虑设备出力或端口电压偏离额定值的运行场景，并提出一套实用化的指标计算方法。

考虑图2所示由 $n$ 台电力电子设备馈入的交流系统，其中 $U _ { i \setminus } \ \theta _ { i } \ ( \ O _ { i } { = } 1 , \dots , n )$ 为第 $i$ 个电力电子设备馈入节点的电压模和相角， $E$ 、 $\varphi$ 为外网等值电压幅值和相角。

![](images/72e6edd4c50037e49ccc4a93948c6a14c1d7897bd85cc3a56906d6c630f631bd.jpg)  
图2多馈入电力系统  
Fig2Multiple-infeed power electronic system 图2所示多馈入系统的闭环特征方程为：

$$
\operatorname * { d e t } \left\{ \left[ \begin{array} { c c c } { Y _ { { \scriptscriptstyle V S C } 1 } ( s ) } & { 0 } & { 0 } \\ { 0 } & { \ddots } & { 0 } \\ { 0 } & { 0 } & { Y _ { { \scriptscriptstyle V S C n } } ( s ) } \end{array} \right] + B \otimes { \cal F } ( s ) \right\} = 0
$$

其中， $\pmb { B } \in \mathbb { R } ^ { n \times n }$ 表示仅包含设备节点的网络降阶导纳矩阵； $Y _ { V S C i } ( s )$ 为第 $i$ 台电力电子设备的导纳传递函数矩阵； $\otimes$ 表示Kronecker积。

类比式，分别提取 $Y _ { V S C i } ( s )$ 的 $P _ { i } / U _ { i } ^ { 2 }$ ，以解耦设备动态特性与端口电气量，式可变换为：

$$
\operatorname * { l e t } \left\{ \left[ \begin{array} { c c c } { \hat { Y } _ { V S C 1 } } & { 0 } & { 0 } \\ { 0 } & { \ddots } & { 0 } \\ { 0 } & { 0 } & { \hat { Y } _ { V S C n } } \end{array} \right] + d i a g ( \frac { U _ { i } ^ { 2 } } { P _ { i } } ) { \cal B } \otimes { \cal F } ( s ) \right\} = 0
$$

式中： $P _ { i }$ 、 $U _ { i }$ 为第 $i$ 台电力电子设备的输出有功功率和端口电压（ $n$ 台电力电子设备使用统一基准值进行标么）； $\hat { Y } _ { V S C i }$ 为第 $i$ 台电力电子设备的 $\hat { Y } _ { _ { V S C } } ( s )$ 。

# 2.1多馈入系统广义运行短路比

当多馈入系统中 $n$ 台电力电子设备动态外特性相似（后文简称“同构系统")，其 $\hat { Y } _ { V S C i }$ 差异性仅来自于不同设备端口电压的差异性。

按照《光伏发电站接入电力系统技术规定》（GB/T19964-2012）、《风电场接入电力系统技术规定》(GB/T19963)对稳态下系统电压控制的要求，考虑节点电压仅在 $0 . 9 \mathrm { \sim } 1 . 1 \mathrm { p . u }$ 的安全范围内变化，并且在变流器锁相环控制主导的小干扰稳定问题中，系统主导模态在锁相环带宽内，则在系统主导模态下有 $\left| U H _ { p l l } \right| \gg 1$ ，使系统满足：

$$
\frac { U H _ { p l l } } { \left( 1 + U H _ { p l l } \right) } \approx 1
$$

式表明， $\hat { Y } _ { V S C i }$ 间差异性较小，因此可类比文献[16]在系统规划阶段的加权思想构造等效同构系统，以逼近原系统的稳定性。等效同构系统的闭环特征方程为：

$$
\operatorname* { d e t } \left\{ { \cal I } _ { n } \otimes \overline { { { \Lambda } } } ( s ) + d i a g ( \frac { U _ { i } ^ { 2 } } { P _ { i } } ) { \cal B } \otimes { \cal I } _ { 2 } \right\} = 0
$$

$$
\overline { { \mathbf { A } } } ( s ) = \overline { { \mathbf { G } } } ( s ) F ^ { - 1 } ( s )
$$

$$
\begin{array} { r } { \overline { { \mathbf { G } } } ( s ) = \sum _ { i = 1 } ^ { n } p _ { 1 i } \hat { Y } _ { V S C i } ( s ) } \end{array}
$$

$$
p _ { 1 i } = u _ { i 1 } \nu _ { i 1 }
$$

其中, $I _ { n }$ 为 $n$ 阶单位阵； $u _ { 1 } ^ { T }$ 和 $\nu _ { 1 }$ 分别为 $d i a g ( U _ { i } ^ { 2 } / P _ { i } ) { \pmb B }$ 关于最小特征值 $\lambda _ { 1 }$ 的左右特征向量， $u _ { i I }$ 和 $\nu _ { i I }$ 分别为 $u _ { 1 } ^ { T }$ 和 $\nu _ { 1 }$ 的第一个元素，归一化后满足 $\sum ^ { n } p _ { 1 i } = 1$ 。

与广义短路比的推导过程类似，对$d i a g ( U _ { i } ^ { 2 } / P _ { i } ) { \pmb B }$ 进行特征值分解，式可看作 $n$ 个单馈入系统特征方程的积，即[15]:

$$
\prod _ { i = 1 } ^ { n } \operatorname * { d e t } \left\{ \overline { { \Lambda } } ( s ) + \lambda _ { i } I _ { 2 } \right\} = 0
$$

式中： $\lambda _ { i }$ 为 $d i a g ( U _ { i } ^ { 2 } / P _ { i } ) { \pmb B }$ 的特征值， $0 < \lambda _ { 1 } \leq \cdots \leq \lambda _ { n }$ 。

引理1:在多馈入系统中，U²/P,>0，diag(U²/P)和 $d i a g ( U _ { i } ^ { 2 } / P _ { i } ) ^ { 1 / 2 }$ 是正定矩阵；同时， $\textbf {  { B } }$ 是对角元均为正数的Hermitian 矩阵，是正定矩阵。因此，根据文献[22][26]对 $S _ { B } ^ { - 1 } { \pmb B }$ 特征值的分析可知，$d i a g ( U _ { i } ^ { 2 } / P _ { i } ) { \pmb B }$ 是可对角化的，且特征值都是正的。

式表明，多馈入系统的稳定性可通过分析解耦后的单馈入系统得到，即多馈入系统的电网强度取决于最弱的等效单馈入系统[15]。因此，可将最弱单馈入系统的OSCR，即 $d i a g ( U _ { i } ^ { 2 } / P _ { i } ) { \pmb B }$ 的最小特征值 $\lambda _ { 1 }$ 定义为多馈入系统的广义运行短路比，即：

$$
g O S C R = \operatorname* { m i n } \lambda \left\{ d i a g ( \frac { U _ { i } ^ { 2 } } { P _ { i } } ) { \pmb B } \right\}
$$

式中： $\lambda \{ \bullet \}$ 表示求解矩阵特征值。

本文侧重考虑运行方式对系统小干扰稳定性的影响，故简化设备建模，采用“同构系统”分析非额定运行方式下电网强度的量化机理。当多馈入系统中 $n$ 台电力电子设备动态外特性存在差异（后文简称“异构系统")，其 $\hat { Y } _ { F S C i }$ 差异性来自于端口电压和设备控制结构、参数等，分析方法与“同构系统”类似，这里不再赘述。

# 2.2多馈入系统临界广义运行短路比

多馈入系统稳定运行时，其gOSCR应大于$\operatorname { C g O S C R }$ 。文献[16]中 $\operatorname { C g S C R }$ 能够通过分析多馈入系统对应等效同构系统来解析或仿真计算得到。同理，当考虑非额定运行方式下设备出力或电压偏离额定值时，同样可通过分析等效同构系统来解析或仿真计算多馈入系统的临界广义运行短路比，其定义式为：

$$
\mathit { C g O S C R } = \operatorname * { a r g } _ { \mathit { g O S C R } } \left\{ \operatorname* { d e t } \left( \overline { { \Lambda } } ( \mathit { j } \omega ) + \mathit { g O S C R } \right) = 0 \right\}
$$

“同构系统”需构造等效同构系统来逼近原系统的稳定性，其所需 $d i a g ( U _ { i } ^ { 2 } / P _ { i } ) { \pmb B }$ 的左右特征向量与电力电子设备输出有功功率、端口电压和系统网架结构相关，因此，系统的 $\operatorname { C g O S C R }$ 随系统运行工况的变化而变化。

# 2.2.1临界广义运行短路比解析算法

实际工程中，在设备外特性已知情况下，能够通过解析计算 $\operatorname { g o s c R }$ 和 $\operatorname { C g O S C R }$ 实现系统电网强度和稳定裕度地准确度量，分析流程图见附录A图A2，具体步骤为：

1）根据网络参数和实际系统中各电力电子设备输出有功功率、端口电压，得到diag(U²/P)B；

2）根据式计算得到系统gOSCR;3）根据系统中各电力电子设备的外特性和式-构造等效同构系统;4）根据等效同构系统的等效单馈入系统，利用式解析计算CgOSCR;5）计算 gOSCR与 $\operatorname { C g O S C R }$ 的差值，根据该差值度量该工况下多馈入系统的电网强度和稳定裕度。

# 2.2.2 临界广义运行短路比仿真计算

当多馈入系统中设备参数未知或者解析计算较复杂，无法利用解析计算方法分析系统稳定裕度，但存在数值仿真模型时，也可利用半实物仿真或者数字仿真，即在仿真系统中搭建等效单机系统，调节线路电感和端口电压，并结合设备输出有功功率以计算系统在不同端口电压下的临界运行短路比，即为多馈入系统的临界广义运行短路比。

本节将详细说明如何构造考虑节点间电压存在差异的“同构系统”的等效同构系统仿真模型，以通过仿真计算原“同构系统”的临界广义运行短路比。

已知变流器锁相环控制环节主导的次/超同步振荡频段大致在中低频段，基于文献[20]、[21]中对变流器内部控制系统多时间尺度特性的描述，内环控制环节的响应速度远大于锁相环，则在中低频段内，系统满足：

$$
\frac { H _ { \mathrm { i } } } { \left( H _ { \mathrm { i } } + s L _ { f } \right) } \frac { U H _ { p l l } } { \left( 1 + U H _ { p l l } \right) } \approx \frac { U H _ { p l l } } { \left( 1 + U H _ { p l l } \right) }
$$

同时，根据Neumam级数的性质可知，如果矩阵 $A$ （ $\pmb { A } \in C ^ { n }$ ， $\mathrm { ~ \varsigma ~ } _ { \mathrm { ~ \ / ~ C ~ } }$ 代表复数域）的所有特征值满足$\lambda _ { { \scriptscriptstyle i } } < 1$ ， $\left( I + A \right) ^ { - 1 }$ 的一阶近似满足[26][27]：

$$
\left( I + A \right) ^ { - 1 } \approx I - A
$$

其中， $I$ 为单位阵，维数与 $A$ 相同。

则联立式和，设备 $\hat { Y } _ { \scriptscriptstyle V S C }$ 可简化为：

$$
\begin{array} { r } { \overline { { Y _ { v c C } } } ( s ) \approx \left[ \begin{array} { l l } { 0 } & { 0 } \\ { 0 } & { \frac { 1 } { \left( 1 + \frac { 1 } { U H _ { p l } } \right) } } \\ { 0 } & { \frac { \left( 0 \right) } { \left( 0 - 1 - \frac { 1 } { U H _ { p l } } \right) } } \end{array} \right] } \\ { \approx \left[ \begin{array} { l l } { 0 } & { 0 } \\ { 0 } & { 1 - \frac { 1 } { U H _ { p l } } } \end{array} \right] } \end{array}
$$

其中， $\overline { { Y } } _ { _ { V S C } } ( s )$ 为简化后的设备 $\hat { Y } _ { _ { V S C } }$ 。

因此，当系统为“同构系统”时，联立、和，等效同构系统可变换为：

$$
\begin{array} { l } { { \overline { { \Lambda } } ( s ) = F ^ { - 1 } ( s ) \sum _ { i = 1 } ^ { n } p _ { \mathfrak { u } } \overline { { Y } } _ { v \wedge \mathrm { C C } } ( s ) } } \\ { { \quad \ \ : = F ^ { - 1 } ( s ) \left[ 0 \begin{array} { c c } { { 0 } } & { { 0 } } \\ { { 1 - { \frac { 1 } { H _ { p \ell } } } \sum _ { i = 1 } ^ { n } p _ { \mathfrak { u } } { \frac { 1 } { U _ { i } } } } } \end{array} \right] } } \\ { { \quad \ = F ^ { - 1 } ( s ) \left[ 0 \begin{array} { c c } { { 0 } } & { { 0 } } \\ { { 1 - { \frac { 1 } { H _ { p \ell } U _ { e } } } } } \end{array} \right] } } \end{array}
$$

其中， $U _ { e q }$ 为等效同构系统的等效端口电压。

因此，在单机并网仿真系统中，调节线路电感等使系统在设备端口电压为等效端口电压的情况下达到临界稳定，得到的系统临界运行短路比，即为原“同构系统”的临界广义运行短路比。

综上所述，gOSCR和 $\operatorname { C g O S C R }$ 指标考虑了系统非额定运行方式(最大出力偏离额定功率以及外部电网电压偏离额定值)对系统电网强度的影响，因此用两者的差值能够更准确地度量多馈入系统的电网强度和稳定裕度。

# 3算例分析及验证

为验证所提 $\operatorname { g o s c R }$ 指标的有效性，在Matlab/Simulink平台中搭建单馈入和八馈入系统时域仿真模型，其中变流器采用平均模型，控制器的采样及控制频率为 $1 0 ~ \mathrm { k H z }$ 。单馈入和八馈入系统如附录A图A3(a)、(b)所示，变流器控制和网络拓扑参数见附录A表A1。此外，本节在Cloudpss平台上搭建哈密等比例缩小系统的电磁仿真模型，系统结构如附录A图A3(c)所示，变流器控制参数和网络拓扑参数见附录A表A2。

# 3.1单馈入系统时域分析

本节首先基于单馈入系统，通过仿真分析阐述节点电压、设备输出有功功率变化对系统稳定性的影响，为后文的理论验证做铺垫。

![](images/01794c0656d5688e14aafa5d27e75d637c022e985608d2471e78f630e8d851f7.jpg)

![](images/39847aa62cdc43a660c20f1392457341737e86e89b518a324d6800b9288a4888.jpg)  
图3端口电压、有功功率振荡曲线 Fig.3Terminal voltage and active power oscillation curse with various voltage or active power

设置单馈入系统中Line ${ \mathrm { : = } } 0 . 5 { \mathrm { p . u } }$ ，即系统的短路比为2，已知临界短路比为2.17，则从短路比的角度可知系统是不稳定的。然而，在 $\scriptstyle { \mathrm { t } } = 2 { \mathrm { s } }$ 时，在外电网施加 $0 . 0 2 5 \mathrm { p u }$ 的电压阶跃，并在 $\displaystyle \mathrm { t } { = } 5 \mathrm { s }$ 时在外电网再次施加 $0 . 0 3 \mathrm { p u }$ 的电压阶跃，设备的端口电压振荡曲线如图3(a)所示，单馈入系统从发散失稳到临界稳定，最后到收敛稳定。由此可知，设备端口电压变化时，利用SCR指标量化系统稳定性和刻画系统稳定边界存在较大误差，可能会导致系统稳定性误判。

进一步设置 $_ { \mathrm { L i n e = } 0 . 4 5 \mathrm { p . u } }$ ，系统的短路比为2.22，已知临界短路比为2.17，从短路比的角度可知系统是稳定的。然而，在 $\scriptstyle { \mathrm { t } } = 2 { \mathrm { s } }$ 时在外电网施加-0.05pu的功率跌落，并在 $\scriptstyle \mathrm { t = } 5 \mathrm { s }$ 时在外电网再次施加 ${ \cdot 0 . 1 \mathrm { p u } }$ 的功率跌落，设备的输出有功功率振荡曲线如图 3(b)所示，单馈入系统从发散失稳到临界稳定，最后到收敛稳定。由此可知，设备有功功率变化时，利用SCR指标量化系统稳定性和刻画系统稳定边界也存在较大误差，可能会导致系统稳定性误判。

# 3.2八馈入系统频域、时域分析

八馈入系统结构示意图参考附录A图A3(b)，变流器控制参数和网络参数见附录A表A1。本节基于八馈入系统，验证等效同构系统和单机COSCR在“同构系统”中的有效性。其中，VSC1\~VSC4节点电压相近，VSC5\~VSC8节点电压相近。因此，为节省表格空间，后文算例中的节点电压分别为两个代表节点电压值，以反映节点电压间的差异。

# 3.2.1 等效同构系统主导模态近似效果

由上文可知，等效同构系统的稳定性由最弱单馈入系统决定，故比较等效同构系统的最弱单馈入系统和原系统主导模态之间的误差，可以说明近似效果。

通过等比例增大所有线路电抗，分别计算系统的 $\operatorname { g S C R }$ 和gOSCR以及原系统的主导特征根轨迹（记为“ ${ \bf \chi } _ { S _ { 1 } } ^ { \prime \prime } )$ 、gOSCR对应等效同构系统的最弱单馈入系统的主导特征根轨迹（记为‘ $^ { \epsilon } { } _ { S 2 } ^ { , \dag } )$ 、 $\mathrm { g s c R }$ 对应最弱等效单馈入系统主导特征根轨迹（记为$^ { 6 6 } { } _ { S 3 } \mathrm { } ^ { 3 5 } )$ ，并分别计算 $s _ { 2 } , \ s _ { 3 }$ 与 $s _ { 1 }$ 的相对误差，误差公式分别为：

$$
\delta _ { 1 } = \frac { \left| s _ { 2 } - s _ { 1 } \right| } { \left| s _ { 1 } \right| } \times 1 0 0 \%
$$

$$
\delta _ { 2 } = \frac { \left| s _ { 3 } - s _ { 1 } \right| } { \left| s _ { 1 } \right| } \times 1 0 0 \%
$$

表1gOSCR对应等效同构系统的最弱单馈入系统的主导特征根对比  

<html><body><table><tr><td>gOSCR</td><td>S1</td><td>S2</td><td>8</td></tr><tr><td>2.68</td><td>-1.05±81.25i</td><td>-1.45±81.73i</td><td>0.76%</td></tr><tr><td>3.01</td><td>-1.60±81.67i</td><td>-1.93±82.10i</td><td>0.67%</td></tr><tr><td>3.42</td><td>-2.13±82.01i</td><td>-2.40±82.40i</td><td>0.58%</td></tr><tr><td>3.93</td><td>-2.64±82.29i</td><td>-2.86±82.64i</td><td>0.50%</td></tr></table></body></html>

表2gSCR对应最弱等效单馈入系统主导特征根对比

Table1 Comparison of dominant characteristic roots of the weakest equivalent SIPES considering gOSCR   
Table 2Comparison of dominant characteristic roots of the weakest equivalent SIPES considering gSCR   

<html><body><table><tr><td>gSCR</td><td>U/pu</td><td>S3</td><td>82</td></tr><tr><td>2.92</td><td>0.9031;0.9462</td><td>-1.72±85.22i</td><td>4.96%</td></tr><tr><td>3.24</td><td>0.9144;0.9527</td><td>-2.18±85.17i</td><td>4.35%</td></tr><tr><td>3.65</td><td>0.9241;0.9578</td><td>-2.62±85.12i</td><td>3.83%</td></tr><tr><td>4.17</td><td>0.9324;0.9614</td><td>-3.06±85.07i</td><td>3.41%</td></tr></table></body></html>

由表1、表2可知，四个算例都说明gOSCR对应等效同构系统的最弱单馈入系统与原系统主导特征根轨迹的误差都较小，相对误差最大为$0 . 7 6 \%$ ，是满足工程精度需要的；而 $\operatorname { g s c R }$ 对应最弱等效单馈入系统与原系统主导特征根轨迹的误差较大，最大相对误差为 $4 . 9 6 \%$ ，会对系统稳定性分析造成一定误差。因此，在系统实际运行阶段，利用gOSCR对应等效同构系统的最弱单馈入系统的主导特征轨迹近似原系统的主导特征轨迹是有效的，用 $\operatorname { g s c R }$ 则无法准确度量系统电网强度。

# 3.2.2 临界广义运行短路比解析计算

为了分析解析计算 $\operatorname { C g O S C R }$ 的有效性，考虑

如下算例情况。

改变外部电网电压，并增加线路电抗Line910，直至八馈入系统临界稳定，计算不同电压下系统的gOSCR（记为“CgOSCR真实值")；同时，根据式计算相应 $\operatorname { C g O S C R }$ （记为“ $\operatorname { C g O S C R }$ 解析值")。图4描绘了八馈入系统运行在端口电压为0.98、$1 . 0 5 \mathrm { p u }$ 的临界稳定下，八台电力电子设备端口电压的等幅振荡曲线。

![](images/b5f9cca425665388ff5baac40918d35757320c6e26d2d45c28282ef9bad67bc7.jpg)  
图4八馈入系统节点电压振荡曲线 Fig.4Terminal voltage oscillation curse of MIPES with eight power electronic devices.

表3系统 $\operatorname { C g O S C R }$ 真实值、解析值

Table 3True value and calculated value of $\mathbf { C g O S C R }$   

<html><body><table><tr><td>U/pu</td><td>CgOSCR真实值</td><td>CgOSCR 解析值</td><td>相对误差</td></tr><tr><td>0.92;0.99</td><td>2.01</td><td>2.02</td><td>0.50%</td></tr><tr><td>0.98;1.05</td><td>2.07</td><td>2.03</td><td>1.46%</td></tr><tr><td>1.02;1.09</td><td>2.06</td><td>2.04</td><td>0.97%</td></tr></table></body></html>

表3给出不同临界电压下 $\operatorname { C g O S C R }$ 真实值和解析值结果。可以看出，最大出力及外部电网电压变化时，系统 $\operatorname { C g O S C R }$ 真实值与解析值的误差均较小，最大相对误差仅为 $1 . 4 6 \%$ ，满足工程精度需要，验证了解析计算 $\operatorname { C g O S C R }$ 方法的有效性。

# 3.3哈密等比例缩小系统电磁仿真分析

Cloudpss是一个基于云计算的开放平台，用于各种功能，包括能源互联网全过程建模和仿真、异构并行计算加速等[24][25]。

为利用电磁仿真模型验证仿真计算系统$\operatorname { C g O S C R }$ 方法和等效单机系统的COSCR在“同构系统”中的有效性，在Cloudpss 平台中搭建哈密等比例缩小同构系统（网络拓扑与实际哈密系统相同，变流器控制结构、参数、容量和网络参数不同）和相应等效同构系统的单馈入系统，为方便分析，上述系统折算至 $2 2 0 \mathrm { k V }$ 电压等级。系统拓扑如附录A图A3(c)所示，每片区中地名下标数字代表该地区中等效变流器编号；其中，节点1-54为变流器设备馈入节点，节点55-93为无源中间节点，节点94等效为无穷大电源节点；变流器参数和网络参数见附录A表A2。

调节线路电感Line93,94和外电网电压使哈密等比例缩小同构系统在不同端口电压达到临界稳定，计算不同电压下系统的gOSCR（记为“CgOSCR真实值"）和 $\operatorname { g s c R }$ （记为“ $\operatorname { C g S C R }$ 真实值")；同时，对应调节等效同构系统，使其在对应等效端口电压下达到临界稳定，计算其gOSCR（记为“CgOSCR仿真值")。

下面进一步以哈密等比例缩小同构系统如何在额定工况下达到临界稳定状态为例，描述算例调节过程。首先系统稳定运行，在0.25s时，对外电网施加-0.05pu的电压跌落，系统在等效端口电压为1时达到了临界稳定状态。图5(a)描绘了该过程中系统中第17台电力电子设备端口三相电压的振荡波形；图5(b)描绘了对端口电压进行快速傅里叶变换的分析，可以看出，系统振荡频率大致在$5 0 \pm 2 6 \mathrm { H z }$ 左右；图 5(c)、(d)分别描绘了系统中所有电力电子设备输出有功功率、无功功率的振荡波形。

![](images/268a473c18da8fa7db7220368b00826f998c7fa4331b1b327c82eb2d4a4fa3de.jpg)

![](images/d2dd9f365d6dde50fbc18afaff67ff009ffc05a187a3c752e6535d510b9d74de.jpg)  
图5哈密等比例缩小同构系统电压、有功功率、无功功率振荡波形、FFT分析  
Fig.5Voltage, active power, reactive power oscillation waveformandFFTanalysisofHamiscalesdown homogeneous systems.

表4CgOSCR真实值、仿真值

Table 4True value and simulation calculated value of   

<html><body><table><tr><td colspan="4">CgOSCR</td></tr><tr><td>Ueq/pu</td><td>仿真值</td><td>真实值</td><td>相对误差</td></tr></table></body></html>

<html><body><table><tr><td>0.9022</td><td>1.6320</td><td>1.6800</td><td>2.86%</td></tr><tr><td>0.9525</td><td>1.7298</td><td>1.7625</td><td>1.86%</td></tr><tr><td>1.0051</td><td>1.8312</td><td>1.8663</td><td>1.88%</td></tr><tr><td>1.0559</td><td>1.9239</td><td>1.9560</td><td>1.64%</td></tr><tr><td>1.0977</td><td>2.0150</td><td>2.0443</td><td>1.43%</td></tr></table></body></html>

表5CgSCR真实值

Table 5True value of CgSCR   

<html><body><table><tr><td>Ueq/pu</td><td>0.90</td><td>0.96</td><td>1.01</td><td>1.06</td><td>1.10</td></tr><tr><td>真实值</td><td>2.0924</td><td>1.9696</td><td>1.8727</td><td>1.7786</td><td>1.7202</td></tr><tr><td>误差</td><td colspan="3">17.79%</td><td></td><td></td></tr></table></body></html>

表 4给出不同临界电压下 $\operatorname { C g O S C R }$ 真实值和仿真值结果。可以看出，外部电网电压变化时，系统 $\operatorname { C g O S C R }$ 真实值与仿真值的误差均较小，最大相对误差仅为 $2 . 8 6 \%$ ，满足工程精度需要，验证了仿真计算 $\operatorname { C g O S C R }$ 方法的有效性，以及利用单馈入系统的临界运行短路比能够近似刻画"同构系统的运行稳定边界。

表5给出不同临界电压下 $\operatorname { C g S C R }$ 真实值及其最大相对误差（不同临界电压下 $\operatorname { C g S C R }$ 真实值之间的最大误差除以等效端口电压为1.01的 $\operatorname { C g S C R }$ 真实值)。可以看出，外部电网电压变化时，系统$\operatorname { C g S C R }$ 真实值随之发生较大变化，最大相对误差为 $1 7 . 7 9 \%$ ，不满足工程精度需要，说明在系统实际运行阶段，利用 $\operatorname { C g S C R }$ 刻画多馈入系统的稳定边界存在较大误差。

综上所述，时域、频域仿真结果和广义运行短路比的解析分析结果是相一致的，验证了广义运行短路比指标及其临界值的有效性。

# 4结论

为考虑系统非额定运行方式(实际出力偏离额定功率以及外部电网电压偏离额定值)对系统电网强度的影响，本文近似解耦了“同构系统”中设备动态特性与端口电气量的相互作用关系，通过构造等效同构系统以逼近原系统的稳定性，提出了广义运行短路比和临界广义运行短路比指标及其实用化算法，两者的距离能够更准确地量化非额定运行方式下系统的电网强度和稳定裕度。广义运行短路比指标同样适用于度量“异构系统”的电网强度和稳定裕度，分析方法与“同构系统”类似。

# 参考文献

[1]姜齐荣,王玉芝.电力电子设备高占比电力系统电磁振荡分析与抑制综述[J].中国电机工程学报,2020,40(22):7185-7120.JIANG Qirong，WANG Yuzhi.Overview of the Analysis andMitigation Methods of Electromagnetic Oscillations in Power

[2]袁小明,程时杰,胡家兵.电力电子化电力系统多尺度电压功角动态 稳定问题[J].中国电机工程学报,2016,36(19):5145-5154. YUAN Xiaoming，CHENG Shijie，HU Jiabing，Multi-time Scale Voltage and Power Angle Dynamics in Power Electronics Dominated Large Power Systems[J]. Proceedings of the CSEE，36(19）: 5145-5154.   
[3]周孝信,鲁宗相,刘应梅,等.中国未来电网的发展模式和关键技术[J]. 中国电机工程学报,2014,34(29):4999-5008. Zhou Xiaoxin,Lu Zongxiang,Liu Yingmei，etal. Development models and key technologies of future grid in China[J]. Proceedings of the CSEE,2014,34(29): 4999-5008.   
[4] 董晓亮，田旭，张勇，等．沽源风电场串补输电系统次同步谐振典 型事件及影响因素分析[J]．高电压技术,2017,43(1):321-328. DONG Xiaoliang,TIAN Xu, ZHANG Yong,et al. Practical SSR Incidenceand Influencing FactorAnalysisof DFIG-based Series-compensated Transmission System in Guyuan Farms[J]. High Voltage Engineering,2017,43(1): 321-328.   
[5]陈国平，李明节，许涛，等．关于新能源发展的技术瓶颈研究[J]. 中国电机工程学报,2017,37(1):20-26. CHEN Guoping,LI Mingjie,XU Tao,et al. Study on Technical Bottleneck of New Energy Development [J]. Proceedings of the CSEE,2017,37(1): 20-26.   
[6] 曾博,杨雍琦,段金辉,等.新能源电力系统中需求侧响应关键问题及 未来研究展望[J].电力系统自动化,2015,39(17):10-18. Zeng Bo,Yang Yongqi, Duan Jihui,et al.Key Issues and Research Prospects for Demand-side Response in Alternate Electrical[J]. Automation of Electric Power Systems,2015,39(17):10-18.   
[7] Zhou J Z,Ding H,Fan S,Zhang Y,Gole A M. Impact of Short Circuit Ratio and Phase-Locked-Loop Parameters on the Small-Signal Behavior of a VSC-HVDC Converter[J]. IEEE Transactions on Power Delivery,2014,29 (5): 2287-2296.   
[8]Ding H,Fan S, Zhou JZ,et al.Parametric analysis of the stability of VSC-HVDC converters[C].11th IET International Conference on AC and DC Power Transmission.IET,Birmingham,2015:1-6.   
[9]Zhou J Z, Gole A M. VSC transmission limitations imposed by AC system strength and AC impedance characteristics[C]. 10th IET International Conference on AC and DC Power Transmission (ACDC 2012),IET,Birmingham,2012:1-6.   
[10] Wang S,Hu JB,Yuan X M.Virtual Synchronous Control for Grid-Connected DFIG-Based Wind Turbines[J].IEEE Journal of Emerging and Selected Topics in Power Electronics,2015,3(4): 932-944   
[11] 徐政.联于弱交流系统的直流输电特性研究之一—直流输电的输 送能力[J].电网技术,1997,21(1):12-16. Xu Zheng.CHARACTERISTICS OF HVDC CONNECTED TO WEAK AC SYSTEMSPRATI:HVDCTRANSMISSION CAPABILITY[J]. Power System Technology,1997,21(1): 12-16.   
[12] CIGRE Working Group B4.41. Systems with multiple DC infeed[R]. CIGRE,2008.   
[13] Paulo Fde T,Bergdahl B，Asplund; G.Multiple infeed short circuit ratio-aspects related to multiple HVDC into one AC network[C] //Transmission and Distribution.   
[14] Denis L H A. Voltage and power interactions in multi-infeed HVDC systems (draft), 2007[R]. 2007. http://www.eeh.ee.ethz.ch/uploads/tx_ethpublications/Voltage_and_ Power_Interaction_Report.pdf.   
[15] 辛焕海，董炜，袁小明,等.电力电子多馈入电力系统的广义短路比 [J].中国电机工程学报,2016,22(20):6013-6027. XIN Huanhai,DONG Wei,YUAN Xiaoming,et al. Generalized Short Circuit Ratio for Multi Power Electronic Based Devices Infeed to Power Systems[J]. Proceedings of the CSEE，2016,22(20): 6013-6027.   
[16]辛焕海，甘德强，鞠平．多馈入电力系统广义短路比：多样化新 能源场景[J]．中国电机工程学报,2020,40(17):5516-5526. XIN Huanhai,GAN Deqiang,JU Ping. Generalized Short Circuit Ratio of Power Systems With Multiple Power Electronic Devices: Analysis for Various Renewable Power Generations[J].Proceedings of the CSEE,2020,40(17): 5516-5526.   
[17]王烨,郭春义,赵成勇．基于小干扰稳定性和运行约束条件的 MMC 系统临界运行短路比评估方法[J].中国电机工程学 报,2019,39(10):2853-2863. WANG Ye， ZHAO Chengyong，GUO Chunyi. A Quantitative Evaluation Approach for Critical Operating SCR of MMC System Based on Small-signal Stability and Operating Constraints[J]. Proceedings of the CSEE,2019,39(10): 2853-2863.   
[18] 李东东,孙梦显,赵耀,等．基于等效运行短路比的多直流馈入系统 静态电压稳定分析[J].中国电机工程学报,2020,40(12):3847-3857. LI Dongdong,SUN Mengxian, ZHAO Yao, et al. The Steady-State Voltage Stability Analysis of Multi-infeed LCC-HVDC System Based on Equivalent Operating Short Circuit Ratio[J]. Proceedings of the CSEE,2020,40(12): 3847-3857.   
[19]考虑运行情况的多馈入系统短路比指标研究[A]．雷前．浙江省 电力学会 2019 年度优秀论文集[C].2020.   
[20] 辛焕海,李子恒,,董炜,等.三相变流器并网系统的广义阻抗及稳定 判据[J].中国电机工程学报,2017,37(5):1277-1292. XIN Huanhai,LI Ziheng,DONG Wei, et al. Generalized-impedance andStabilityCriterionforGrid-connectedConverters[J]. Proceedings of the CSEE,2017,37(5): 1277-1292.   
[21] Zhao Mingquan，Yuan Xiaoming，Hu Jiabing，et al.Voltage dynamics of current control time-scale in a VSC-connected weak grid[J]．IEEE Transactions on Power Systems，2016,31(4): 2925-2937.   
[22] Dong Wei,Xin Huanhai,Wu Di,Huang Linbin.Small signal stability analysis of multi-infeed power electronic systems based on grid strength assessment[J]. IEEE Trans.on Power Systems,2019, 34(2): 1393-1403.   
[23]高黛陵.多变量频率域控制理论[M].北京：清华大学出版社,1998.   
[24] Y. Song,Y.Chen,S.Huang,Y.Xu,Z. Yu and J.R.Marti. Fully GPU-basedelectromagnetictransientsimulationconsidering large-scalecontrolsystemsforsystem-level studies[J]. IET Generation,Transmission & Distribution,2017,11(11): 2840-2851.   
[25] Y.Song,Y. Chen,S. Huang, Y. Xu, Z. Yu and W. Xue.Efficient GPU-Based Electromagnetic Transient Simulation for Power Systems with Thread-Oriented Transformation and Automatic Code Generation[J]. IEEE Access,2018,6: 25724-25736.   
[26]R.Horn and C.Johnson，Matrix Analysis.Cambridge，U.K: Cambridge Univ.Press,1985.   
[27]袁辉．考虑振荡稳定约束的新能源承载能力分析及提升技术[D]. 浙江杭州：浙江大学,2021. Yuan Hui. Analysis and Enhanced of the Maximum Accomodable Capacities of Renewables in Power System with the Constraints of Oscillation Stability[D].Zhejang Hangzhou, Zhejiang University, 2021. 主要研究方向：新能源并网稳定分析与控制。E-mail： 1055102475@qq.com   
作者简介：辛焕海(1981—)，男，博士，教授，博士生导 师，主要研究方向：交直流系统稳定分析与控制、新能源 并网稳定分析与控制。   
作者简介：周璃涵(1996—)，男，硕士，高级工程师，主

要研究方向：新能源并网稳定分析与控制。作者简介：王冠中(1990—)，男，博士研究生，主要研究方向：新能源并网稳定分析与控制。

# Generalized Short Circuit Ratio of New Energy Power System Considering Operating State: Generalized Operation Short Circuit Ratio

LIU Chenxi1, XIN Huanhai1, ZHOU Yuhan1,WANG Guanzhong1,YUAN Hui1 (1. College of Electrical Engineering, Zhejiang University, Hangzhou 310027, China)

Abstract: The new energy multiple-infeed power electronic system has the issues of sub-/super-synchronous Oscillation caused by the mismatch between the phase-locked loop bandwidth and the grid strength. It is necessry to accurately quantify the grid strength to ensure the stable operation of the system.To this end,this paper considers the impact of active power output or terminal voltage deviation from the rated value on the grid strength of the system in the operating scenario. Meanwhile,generalized operation short circuit ratio index is proposed under non-rated operating conditions.This paper firstly analyzes the change law of the terminal characteristics of the devices when the operating mode of the new energy system changes,and approximately decouples the interaction between dynamic characteristics of devices and terminal electrical quantities. Secondly,the decoupling property of the network-side admitance matrix is studied when considering the electrical quantities changing. Considering the operation mode,the generalized operation short circuit ratio index and the corresponding practical calculation method are proposed, which expands the application range of the generalized short circuit ratio theory.Finally,simulation results verify the effectiveness of the proposed index

Key words: sub-/super-synchronous oscillation; generalized operation short circuit ratio; non-rated operating conditions; decoupling property

# 附录A

![](images/5bb03387c080d63a395e9ca1cf1f801751685161944e2a278712180e1ef83fe4.jpg)  
图A1并网变流器框图

![](images/935b7ad6b999595f120a255bba1c37474712a3d73fde41f2946c6914c5899b9f.jpg)  
Fig A1 Diagram of three-phase grid-connected converter   
图A2系统稳定裕度度量流程图

Fig.A2Flow chart of system stability margin measurement

VSC Infinite Bus +丨+② (a)

![](images/430cca1a407d863c75e11380983980b92a7b8661cbaa8f9844775ad295ab305e.jpg)  
图A3单馈入、八馈入和哈密等比例缩小系统仿真模型

Fig.A3 The test system with the VSC、eight VSCs and Hami scales down homogeneous systems.

表A1时域仿真模型参数  
Table A1 Parameters of time domain simulation   

<html><body><table><tr><td colspan="8">变流器控制参数</td></tr><tr><td>Sb/kVA</td><td>1500</td><td>Ub/V</td><td>690</td><td>Lf/pu</td><td>0.05</td><td>Cf/pu</td><td>0.05</td></tr><tr><td>Kip</td><td>0.2</td><td>Kii</td><td>10</td><td>Pref/pu</td><td>1</td><td>Qref/pu</td><td>0</td></tr><tr><td>Tff</td><td>0.0001</td><td>Kplp1</td><td>12</td><td>Kplil</td><td>7200</td><td></td><td></td></tr><tr><td colspan="8">网络参数</td></tr><tr><td>Line 12/pu</td><td>0.1</td><td>Line 23/pu</td><td>0.05</td><td>Line 34/pu</td><td>0.035</td><td>Line 49/pu</td><td>0.02</td></tr><tr><td>Line 56/pu</td><td>0.2</td><td>Line 67/pu</td><td>0.15</td><td>Line 78/pu</td><td>0.018</td><td>Line 89/pu</td><td>0.135</td></tr></table></body></html>

表A2Cloudpss 电磁仿真模型参数  
Table A2Parameters of electromagnetic simulation model on Cloudpss   

<html><body><table><tr><td colspan="8">1 变流器控制参数</td></tr><tr><td>Sb/kVA</td><td>1000</td><td>Ub/V</td><td>620</td><td>Lf/pu</td><td>0.1225</td><td>Cr/pu</td><td>0.0604</td></tr><tr><td>Kdep</td><td>5</td><td>Kdei</td><td>20</td><td>Kip</td><td>0.5</td><td>Kii</td><td>50</td></tr><tr><td>Pref/pu</td><td>1</td><td>Qref/pu</td><td>0</td><td>Kplp2</td><td>25</td><td>Kpli2</td><td>18000</td></tr><tr><td>Cde/pu</td><td>0.1089</td><td>Udeo/V</td><td>1100</td><td></td><td></td><td></td><td></td></tr><tr><td colspan="8">网络参数</td></tr><tr><td>Line1,5s/pu</td><td>0.067</td><td>Line2,5s/pu</td><td>0.067</td><td>Line3,55/pu</td><td>0.067</td><td>Line4,55/pu</td><td>0.067</td></tr><tr><td>Line5,56/pu</td><td>0.067</td><td>Line6,56/pu</td><td>0.067</td><td>Line7,57/pu</td><td>0.067</td><td>Line8,58/pu</td><td>0.067</td></tr><tr><td>Line9,58/pu</td><td>0.067</td><td>Line10.59/pu</td><td>0.067</td><td>Line1,6/pu </td><td>0.067</td><td>Line 12,60/pu</td><td>0.067</td></tr><tr><td>Line13.61/pu</td><td>0.067</td><td>Line14,6/pu</td><td>0.067</td><td>Line 15.62/pu</td><td>0.067</td><td>Line16.63/pu</td><td>0.067</td></tr><tr><td>Line17.64/pu</td><td>0.067</td><td>Line18.6s/pu</td><td>0.067</td><td>Line 19,65/pu</td><td>0.067</td><td>Line0.66-pu</td><td>0.067</td></tr><tr><td>Line21,6/pu</td><td>0.067</td><td>Line22.68/pu</td><td>0.067</td><td>Line23,68pu</td><td>0.067</td><td>Line24,68/pu</td><td>0.067</td></tr><tr><td>Line25.68/pu</td><td>0.067</td><td>Line26,69/pu</td><td>0.067</td><td>Line27,69/pu</td><td>0.067</td><td>Line28.70/pu</td><td>0.067</td></tr><tr><td>Line29,70/pu</td><td>0.067</td><td>Line30,7/pu</td><td>0.067</td><td>Line31,71/pu</td><td>0.067</td><td>Line32.72/pu</td><td>0.067</td></tr><tr><td>Line33,73/pu</td><td>0.067</td><td>Line34,73/pu</td><td>0.067</td><td>Line35,74/pu</td><td>0.067</td><td>Line36,75/pu</td><td>0.067</td></tr><tr><td>Line37,76/pu</td><td>0.067</td><td>Line38,77/pu</td><td>0.067</td><td>Line39,78/pu</td><td>0.067</td><td>Line40,78/pu</td><td>0.067</td></tr><tr><td>Line41,78/pu</td><td>0.067</td><td>Line42,78/pu</td><td>0.067</td><td>Line43,79/pu</td><td>0.067</td><td>Line44.80/pu</td><td>0.067</td></tr><tr><td>Line45,80/pu</td><td>0.067</td><td>Line46.80/pu</td><td>0.067</td><td>Line47,80/pu</td><td>0.067</td><td>Line48,81/pu</td><td>0.067</td></tr><tr><td>Line49,82/pu</td><td>0.067</td><td>Line50,82/pu</td><td>0.067</td><td>Lines51,83/pu</td><td>0.067</td><td>Line 52.84/pu</td><td>0.067</td></tr><tr><td>Line53.84/pu</td><td>0.067</td><td>Line54,85/pu</td><td>0.067</td><td>Lines55,86/pu</td><td>0.00018282</td><td>Line56,86/pu</td><td>0.00076013</td></tr><tr><td>Line57,86/pu</td><td>0.0017608</td><td>Lines8,86/pu</td><td>0.0024632</td><td>Line59,86/pu</td><td>0.0021264</td><td>Line60,86/pu</td><td>0.0014818</td></tr><tr><td>Line61,86/pu</td><td>0.0012701</td><td>Line2,.86*pu</td><td>0.00066391</td><td>Line63,87/pu</td><td>0.000789</td><td>Line64,87/pu</td><td>0.0023381</td></tr><tr><td>Line65,87/pu</td><td>0.0017416</td><td>Line66.87/pu</td><td>0.0014048</td><td>Line67,87/pu</td><td>0.0010777</td><td>Line68,87/pu</td><td>0.00025979</td></tr><tr><td>Line69,87/pu</td><td>0.00011546</td><td>Line70,87/pu</td><td>0.00037526</td><td>Line71,88pu</td><td>0.0018948</td><td>Line72.88/pu</td><td>0.0016357</td></tr><tr><td>Line73,88/pu</td><td>0.0011398</td><td>Line74,88/pu</td><td>0.000977</td><td>Line75.88/pu</td><td>0.00060692</td><td>Line76.88/pu</td><td>0.000977</td></tr><tr><td>Line77,8/-pu</td><td>0.00060692</td><td>Line78.90/pu</td><td>0.00014063</td><td>Line79.90/pu</td><td>0.0016357</td><td>Lines0,89/pu</td><td>0.00014063</td></tr><tr><td>Lines1,89/pu</td><td>0.0016357</td><td>Line82,91/pu</td><td>0.0011398</td><td>Line83.91/pu</td><td>0.000977</td><td>Lineg4.91/pu</td><td>0.0011398</td></tr><tr><td>Line85,91/pu</td><td>0.000977</td><td>Line86,87/pu</td><td>0.005181</td><td>Lineg9,90/pu</td><td>0.005181</td><td>Lineg7,92/pu</td><td>0.0077891</td></tr><tr><td>Line8,92/pu</td><td>0.0032454</td><td>Line90.92/pu</td><td>0.0058418</td><td>Line91,92pu</td><td>0.00064909</td><td>Line92.93/pu</td><td>0.0025173</td></tr><tr><td>Line93.94/pu</td><td>0.003</td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>