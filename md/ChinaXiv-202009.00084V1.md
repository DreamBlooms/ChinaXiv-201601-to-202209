# 双向携能通信网络中子载波和功率联合分配

薛亮1，李娜1，赵辉1,²，王燕龙³，徐哲壮4(1.河北工程大学 信息与电气工程学院，河北 邯郸 056038;2.凯迪雷拉大学 教育学院，菲律宾 碧瑶 2600;3．北京邮电大学 可信分布式计算与服务教育部重点实验室，北京 100876;4.福州大学 电气工程与自动化学院，福州350000)

摘要：在正交频分复用技术和双向通信下，研究了携能通信网络中的资源分配问题。提出了一种面向子载波和传输功率的联合分配算法，该算法不依赖于现有的功率分割或时隙切换机制，可以在不同的子载波上分别传输信息和能量，简化了携能机制设计。此外，考虑到实际能量收集电路的饱和特性，该联合算法基于非线性能量采集模型，采用拉格朗日对偶和次梯度方法，研究了在满足用户传输速率阈值的前提下，使系统的总能耗最小化的问题，降低网络能量开销。数值仿真实验证实了此联合分配算法的有效性和能量高效性。

关键词：携能通信；正交频分复用；非线性能量采集模型；子载波分配；功率分配 中图分类号：TN915 doi:10.19734/j.issn.1001-3695.2020.03.0064

Joint subcarrier and power allocation in ofdm swipt based two-way communication networks

Xue Liang1,Li $\mathrm { { N a ^ { 1 \dagger } } }$ , Zhao Hui1,2, Wang Yanlong³, Xu Zhezhuang4 (1.SchoolofInformation&Electrical Engineering,Hebei Universityof Enginering,HeBei Handan O56o38,China;2. CollgeofTeacherEducation,UniversityoftheCordileras,BaguioCity6o,Phippnes;3.KeyLaboratoryofTrustworthy DistributedComputing&Service,Beijing UniversityofPosts&Telecommunications,MinistryofEducation,Beijing087, China;4.SchoolofElectrical Engineering&Automation,Fuzhou University,Fuzhou35ooo0,China)

Abstract:This paperinvestigatedtheresourceallocationproblemofthe synchronous wireless informationand powertransfer (SWIPT)two-waycommunicationnetworksbased onorthogonal frequencydivisionmultiplexing.This paper proposes ajoint subcarierand powerallocation (JSPA)algorithm,which is neitherdependent uponthe powersplitingnorthe timeswitching schemesand simplifies thedesignof SWIPT principles,transfers informationand energyusing diferent subcarriers. Consideringthesaturationcharacteristicofactual energy harvesting circuit,thejointdesignalgorithm,whichisdevelopedby usingLagrange dualand subgradient methods and thus is basedonthe nonlinear energyharvesting model,isformulated to minimize the energy consumption of networks under condition thatthe required rateof the destination is satisfied.The numericalsimulationresultsvalidateboth the JSPA'sefectiveness inthejointallocationofnetworkresourcesand itshigh energy efficiency.

Key words:simultaneous wirelessinformationand powertransfer (swipt);orthogonal fequencydivisionmultiplexing (ofdm); non-linear energy harvesting model; subcarrier allocation; power allocation

# 0 引言

携能通信(simultaneous wireless information and powertransfer,SWIPT)技术通过能量收集(energy harvesting,EH)电路将周围环境中的射频(radiofrequency，RF)信号转换为可用的直流(directcurrent,DC)电源[1]，为能量受限的传感器、移动设备、低功耗计算机等终端设备供电，在传输信息的同时解决无线通信网络中设备的能量供应问题[2]。据测算，在与工作于GSM频段( $1 8 0 5 { \sim } 1 8 8 0 ~ \mathrm { M H z } )$ 的射频源距离50米处的射频功率密度约为 $\mathsf { l m } \mathsf { W } / \mathsf { m } ^ { 2 }$ ，那么以 $1 0 0 \mathrm { c m } ^ { 2 }$ 大小的携能设备为例，它将最多收集到数十微瓦的可用功率[3]。这对于超低功率需求的无线设备而言，已具备维持其间歇应用的基本要求。所以，在无线传感器网络、物联网等5G低功耗受限网络中，SWIPT能够为移动用户提供了极大的便利，已引起相关学者的关注[1\~5]。在无线携能通信网络中，能量效率是用于评价该类型网络性能的指标之一。在满足服务质量的前提下，最小化网络整体能量开销是提升能量效率的有效途径。为此，需要从算法层面着手，高效地管理与分配网络可用资源。

Varshney[3]于2008年首次提出了信息与能量同时传输的策略，该策略分析了网络性能的上限，但由于射频能量收集过程会破坏射频信号所包含的数据信息，因此该策略未能实现。之后，Zhou $\mathrm { X u n } ^ { [ 6 ] }$ 提出了一种实际的信息与能量接收机结构，据此衍生了功率分割(power splitting,PS)和时隙切换(time switching，TS)两种通信机制[7.8]，为携能通信的实际应用奠定了基础。

基于PS通信机制，文献[9]研究了OFDM携能通信中继网络中的自适应传输模式转换协议。该协议根据源端节点与终端节点不同的通信方式，提出了传输模式转换策略。该策略使用拉格朗日对偶方法，求解具有模式转换特点的非凸资源分配问题。基于TS通信机制，文献[10]在SWIPTNOMA网络中，以最大化能量效率为目标，利用Dinkelbach方法，提出了面向传输功率和TS因子的双层资源分配联合优化算法。

为简化接收机的设计复杂度，进一步提升网络性能，一些新型的携能通信策略被提出，开辟出信息与能量同传的新途径。文献[11]提出了新型的接收机模式切换策略，其中多天线发射机采用传统的随机波束成形技术发送公共信息。每个单天线接收机在未知信道状态信息条件下，根据无线信道的时间波动性自主切换信道，从而实现回收能量的最大化。文献[12]针对5G无线携能通信网络研究能量效率最大化问题，并提出基于OFDM的信息与能量传输策略，对网络资源进行联合优化，有效简化了接收机的设计复杂度。文献[13]在衰落信道下提出了动态模式切换的携能通信方案，以最大化用户收集能量为目标，自适应调节最优传输功率分配方案。

正交频分复用(orthogonal frequency division multiplexingOFDM)技术能够提高网络频谱效率和抗多径干扰能力，有效利用子载波的传输状态，进而适配传输功率，能够显著降低网络能耗，提升能量效率。文献[14]在不完美信道状态信息条件下，研究了OFDM携能通信系统中的资源分配与功率控制问题。文献[15]在下行正交频分多址网络中，为满足用户可靠、低时延的通信需求，提出了一种基于逐次凸优化的次优资源分配算法，提高了网络吞吐量。文献[16]研究了基于OFDM技术的多用户携能通信系统，该系统以最大化“和速率"为目标，使用贪婪算法实现网域资源的初始分配。虽然它通过任意交换两个用户的子载波，提高了中断性能，但随着子载波数量的增加，算法复杂度也将大大增加。因此，与传统OFDM通信网络不同，基于OFDM的携能通信网络，其性能将同时受到用户数量、子载波峰值功率，以及信息和能量传输功率水平的影响[17,18]。在现有功率分配方式中,平均功率分配算法虽然计算复杂度低，但它忽视了信道质量，因此当子载波的质量较差时，降低了网络的吞吐量。

上述相关工作大多是基于线性EH模型来分析网络性能指标。然而近期研表明[19,20]，基于二极管的EH电路的RF-DC转换效率是非线性的，而不是线性的，即当接收功率接近或达到饱和阈值时，可收集的射频能量不随射频功率的增大而增加，具有饱和特性。因此，使用传统的线性EH模型对系统性能进行分析和设计，可能会导致输出不准确和系统性能的损失。文献[21]提出的符合EH电路实际工作特性的非线性EH模型，考虑了射频能量采集过程中的饱和特性，使得网络性能的评价将更准确，具有更好的性能。文献[22]提出了一种简化的非线性EH模型，在可操作性和准确性之间取得折中。

本文所研究的场景为基于ODFM技术的双向携能通信网络。在下行链路上，源端将可用的OFDM子载波划分为两种类型，分别用于射频能量传输和信息传输。因此，终端接收机无须额外设计功率分割或时隙切换机制，简化了携能机制设计。由于射频EH电路存在饱和特性，基于非线性EH模型，本文提出了子载波和传输功率的联合分配(joint subcarrierand powerallocation,JSPA)算法。数值实验结果证实，在满足用户数据速率需求的前提下，JSPA算法能够得出子载波集合的最优划分方案，揭示子载波与功率、传输速率和能量回收之间的内在联系，有效减少网络能量开销。

# 1 网络模型和问题描述

# 1.1网络模型

考虑如图1所示的OFDM携能双向通信网络，该网络由具备单天线的源端S和具有能量收集能力的终端D组成。终端节点的全部能量来源于收集源端发射的RF信号，其将接收到的射频信号用于能量收集和信息解码，并使用回收的射

频能量向源端反馈信息。

![](images/db5ec54a0115a33b5514f22a8fb1435b901acfc84143834467e81e3f7c7ab765.jpg)  
图1OFDM双向携能通信系统模型  
Fig.1 OFDM SWIPT based tow-way communication system model

在源端到终端的单跳通信阶段，通信时隙为 $T _ { \mathrm { l } }$ ，系统带宽集合 $\mathcal { N }$ 被均等划分为 $N$ 个正交子载波 $\mathcal { N } = \{ 1 , . . . , n , . . . , N \}$ ，其中，第 $n$ 个子载波的信道增益为 $h _ { n }$ ，源端为子载波 $n$ 分配的发射功率为 $p _ { n }$ 。在终端到源端的单跳阶段，通信时隙为 $T _ { 2 }$ ，可用带宽集合 $\mathcal { M }$ 被均等划分为 $\mathcal { M } = \{ 1 , . . . , m , . . . , M \}$ ，其中， $g _ { \scriptscriptstyle m }$ 为第 $\mathbf { \lambda } _ { m }$ 个子载波的信道增益， $q _ { m }$ 为终端发射功率。 $\sigma _ { n } ^ { 2 }$ 和 $n _ { m } ^ { 2 }$ 分别表示源端与终端均服从正态分布的加性高斯白噪声。源端与终端均采用基于OFDMA接收机的带通滤波器，并已知信道状态信息，可以实现在不同的子载波上分别传输信息和功率[23]。此外，由混频器、滤波器和数模转换器等模块消耗的电路功率与发射功率相比非常微小，本文忽略不计。

# 1.2问题描述

源端S通过OFDM子载波集 $\mathcal { N }$ 传输信息和能量到终端D，载波集合 $\mathcal { N }$ 被划分为两个子集,即 $\mathscr { C } _ { I }$ 和 $\mathcal { C } _ { E }$ $\big ( \mathscr { C } _ { I } , \mathscr { C } _ { E } \subset \mathscr { N }$ ，$\mathcal { C } _ { I } \cup \mathcal { C } _ { E } = \mathcal { N }$ ， $\mathcal { C } _ { I } \cap \mathcal { C } _ { E } = \emptyset$ )。如图1所示，子集 $\mathscr { C } _ { I }$ 中的子载波用于信息传输，其子载波 $i$ 上的传输功率记为 $p _ { i } ^ { I } \left( i \in \mathcal { C } _ { I } \right.$ )。子集 $\mathcal { C } _ { E }$ 中的子载波用于能量收集，其子载波 $j$ 上的传输功率记为 $p _ { j } ^ { E }$ （ $j \in \mathcal { C } _ { E }$ )下行通信链路上可实现的数据传输速率为

$$
R _ { S , D } = \sum _ { i \in \mathcal { C } _ { I } } \log \left( 1 + \frac { p _ { i } ^ { I } h _ { i } } { \sigma _ { i } ^ { 2 } } \right)
$$

源端因传输能量和信息到终端而产生的能耗为

$$
W _ { S } = T _ { 1 } \sum _ { n = 1 } ^ { N } P _ { n }
$$

终端采集到的能量表示为

$$
E = T _ { 1 } \sum _ { j \in \mathcal { C } _ { E } } f _ { N L } ( P _ { i n } )
$$

其中， $f _ { _ { N L } } ( \cdot )$ 为文献非线性能量转换模型， $P _ { i n } = p _ { j } ^ { E } h _ { j } + \sigma _ { j } ^ { 2 } , j \in \mathcal { C } _ { E }$ 。

在能量采集电路的输入射频功率范围内，能量转换效率通常先随输入功率的增大而增加，到达阈值后的转换效率随着输入功率的增加而下降。根据能量采集过程中转换效率的非线性，能量采集模型可近似为[22]：：

$$
f _ { _ { N L } } ( P _ { i n } ) { = } { \alpha } _ { 1 } P _ { i n } ^ { 2 } + { \alpha } _ { 2 } P _ { i n } + { \alpha } _ { 3 }
$$

其中， $\alpha _ { 1 }$ 、 $\alpha _ { 2 }$ 和 $\alpha _ { 3 }$ 为与能量采集过程有关的参数，由终端天线和能量采集电路的设计而定。

在终端到源端的上行链路上，OFDM子载波均用于信息传输，上行链路的可达速率 $R _ { D , S }$ 为

$$
R _ { D , S } = \sum _ { m \in \mathcal { M } } \log \left( 1 + \frac { q _ { m } g _ { m } } { n _ { m } ^ { 2 } } \right)
$$

终端因传输信息到源端而产生的能耗为

$$
W _ { D } = T _ { 2 } \sum _ { m = 1 } ^ { M } q _ { m }
$$

在该双向携能通信网络中，源端消耗能量维持了网络的运行。以最小化源端能耗为目标，采用非线性能量采集模型，将源端和终端的速率需求和能量收集门限纳入约束，联合优化子载波和传输功率，得到如下优化问题P1：

$$
\operatorname* { m i n } _ { \{ p _ { n } , q _ { m } , \mathcal { C } _ { I } , \mathcal { C } _ { E } \} } T _ { 1 } \sum _ { n = 1 } ^ { N } P _ { n }
$$

$$
s . t . \sum _ { i \in \mathcal { C } _ { I } } \log \left( 1 + \frac { p _ { i } ^ { I } h _ { i } } { \sigma _ { i } ^ { 2 } } \right) - R _ { s } \geq 0 ,
$$

$$
T _ { 1 } \sum _ { j \in \mathcal { C } _ { E } } f _ { N L } ( p _ { j } ^ { E } h _ { j } + \sigma _ { j } ^ { 2 } ) - W _ { D } \geq 0 ,
$$

$$
\sum _ { m = 1 } ^ { M } \log \left( 1 + \frac { q _ { m } g _ { m } } { n _ { m } ^ { 2 } } \right) - R _ { D } \geq 0 ,
$$

$$
p _ { i n } \ge p _ { l o w } , p _ { i n } \le p _ { u p } ,
$$

$$
p _ { n } \geq 0 , n \in \mathcal { N }
$$

$$
q _ { m } \geq 0 , m \in \mathcal { M }
$$

其中，约束条件(7b)和(7d)分别为源端和终端用户的最小数据传输速率阈值要求，约束条件(7c)表示源端发射的传输功率应满足能量收集门限，即提供给终端进行数据传输所需的能量。约束条件(7e)表示能量收集电路可接受的的输入功率范围，约束条件(7f)和 $( 7 \mathrm { g ) }$ 要求源端和终端的发射功率为非负值。

# 2 子载波和功率联合分配算法

上述优化问题P1中，目标函数(7a)和约束条件(7b)\~(7d)均为凸函数，(7e)\~(7g)为线性约束条件，且存在多个待确定的集合变量： $\mathcal { P } = \{ ( p _ { i } ^ { I } , p _ { j } ^ { E } ) \vert i \in \mathcal { C } _ { I } , j \in \mathcal { C } _ { E } \}$ ， $Q = \{ q _ { m } \ : | \ : m \in \mathcal { M } \}$ ，$\mathcal { L } = \{ ( \mathcal { C } _ { I } , \mathcal { C } _ { E } ) | \mathcal { C } _ { I } \cup \mathcal { C } _ { E } = \mathcal { N } ; \mathcal { C } _ { I } \cap \mathcal { C } _ { E } = \emptyset ; \mathcal { C } _ { I } , \mathcal { C } _ { E } \not = \emptyset \}$ 0

若利用穷举搜索法根据优化问题P1寻找子载波的最优分配方案，其算法复杂度会随着子载波数量的增加呈几何级数式大大增加。通过观察双向通信网络的特点和问题结构，原优化问题P1中与优化变量 $\boldsymbol { \mathscr { Q } }$ 相关的约束条件只有(7d)和(7g)，而且该约束条件决定了终端进行数据传输所需的功率，与优化问题中的其他约束条件和目标函数无耦合。因此，为了降低算法复杂度，原优化问题P1可分解为两个独立的子优化问题P2和P3。子优化问题P2以最小化终端能耗为目标，沿用原问题中的(7d)和(7g)作为约束条件，其表达式为

$$
\operatorname* { m i n } _ { q _ { m } } T _ { 2 } \sum _ { m = 1 } ^ { M } q _ { m }
$$

$$
s . t . \sum _ { m = 1 } ^ { M } \log \left( 1 + \frac { q _ { m } g _ { m } } { n _ { m } ^ { 2 } } \right) - R _ { D } \geq 0 ,
$$

$$
q _ { m } \geq 0 , m \in \mathcal { M } .
$$

该双向携能通信网络中，终端可用的能量来源于从源端收集到的射频能量。子优化问题P2以最小化终端能耗为目标，当终端能耗最小时，源端能耗也降至最低。因此，求解P2问题所得到的最优解集，是原问题P1解集的子集。P1经剥离子问题P2后得到的新问题，可记为优化问题P3：

$$
\begin{array} { c } { \displaystyle \operatorname* { m i n } _ { \stackrel { N } { \left( \varepsilon \right) , c \left( 1 \right) } } T _ { 1 } ^ { \prime } p _ { n } } \\ { \displaystyle s . t . \sum _ { i \in \mathcal { C } _ { I } } \log \left( 1 + \frac { p _ { i } ^ { l } h _ { i } } { \sigma _ { i } ^ { 2 } } \right) - R _ { s } \geq 0 , } \\ { T _ { 2 } \displaystyle \sum _ { j \in \mathcal { C } _ { I } } f _ { N I } ( p _ { j } ^ { k } h _ { j } + \sigma _ { j } ^ { 2 } ) - W _ { D } \geq 0 , } \\ { p _ { i } ^ { l } \geq 0 , i \in \mathcal { C } _ { I } ^ { \prime } , } \\ { p _ { i n } \geq p _ { l o w } , p _ { i n } \leq p _ { w } . } \end{array}
$$

# 2.1网络模型优化终端功率分配

针对子优化问题P2，设定时隙，为使终端能量消耗最小化，需要求解终端的最优功率分配方案。为此，构建子问题P2的拉格朗日函数：

$$
\begin{array} { c } { { \displaystyle { \mathcal { L } } ( q _ { m } , \kappa _ { m } , \lambda ) = \sum _ { m = 1 } ^ { M } q _ { m } - \sum _ { m = 1 } ^ { M } \kappa _ { m } q _ { m } + } } \\ { { \displaystyle { \phantom { \frac { 1 } { \sum _ { m = 1 } ^ { M } \kappa _ { m } \kappa _ { m } \kappa _ { m } \lambda } } \lambda \Bigg ( R _ { D } - \sum _ { m = 1 } ^ { M } \log \left( 1 + \frac { q _ { m } g _ { m } } { n _ { m } ^ { 2 } } \right) \Bigg ) } } } \end{array}
$$

其中， $\kappa _ { m }$ （20 $( \kappa _ { m } \ge 0 , m \in \mathcal { M } )$ 和 $\lambda$ $( \lambda \geq 0 )$ 为拉格朗日乘子。

结合子问题P2的约束，Karush-Kuhn-Tucker条件可表示为

$$
1 - \frac { \lambda g _ { m } } { n _ { m } ^ { 2 } + q _ { m } g _ { m } } - \kappa _ { m } = 0 , \forall m
$$

$$
\lambda \Biggl ( R _ { D } - \sum _ { m = 1 } ^ { M } \log \Biggl ( 1 + \frac { q _ { m } g _ { m } } { n _ { m } ^ { 2 } } \Biggr ) \Biggr ) = 0
$$

$$
\kappa _ { m } q _ { m } = 0 , m \in \mathcal { M }
$$

得到 $q _ { m }$ 解的表达式为

$$
q _ { m } = \left( \lambda - \frac { n _ { m } ^ { 2 } } { g _ { m } } \right) ^ { + } , m \in \mathcal { M }
$$

其中， $x ^ { + } \doteq \operatorname* { m a x } ( 0 , x )$ 0

将式(14)代入式(10)，重写子优化问题P2的拉格朗日函数为

$$
\mathcal { L } ( \lambda ) = \lambda ( M + R _ { D } - \sum _ { m = 1 } ^ { M } \log \frac { g _ { m } } { n _ { m } ^ { 2 } } ) - M \lambda \log \lambda - \sum _ { m = 1 } ^ { M } \frac { n _ { m } ^ { 2 } } { g _ { m } }
$$

此时，式(15)为关于 $\lambda$ 的凹函数，令其一阶导数为零，得到对偶变量 $\lambda$ 的最优值为

$$
\lambda ^ { * } = e ^ { ( R _ { D } - \sum _ { m = 1 } ^ { M } \frac { g _ { m } } { n _ { m } ^ { 2 } } ) / M }
$$

将最优乘子 $\lambda ^ { * }$ 代入式(14)，可得终端发送功率的最优值为

$$
q _ { m } ^ { * } = ( e ^ { ( R _ { D } - \sum _ { m = 1 } ^ { M } \frac { g _ { m } } { n _ { m } ^ { 2 } } ) / M } - \frac { n _ { m } ^ { 2 } } { g _ { m } } ) ^ { + } , m \in \mathcal { M }
$$

子优化问题P2最小化的终端能耗 $W _ { D } = \mathcal { L } ( \lambda ^ { * } )$ 是源端的能量收集门限，代入子问题P3的能量采集约束条件T∑fNt(phj+σ³)-WD≥0后更新子优化问题P3。

# 2.2优化拉格朗日对偶变量

通过求解子优化问题P2，得到终端能耗最小化的最优值$W _ { D }$ 。子优化问题P3以最小化源端能耗为目标，以源端最小数据传输速率需求和最小能量采集门限为约束条件，设定时隙 $T _ { 1 } = 1$ 。利用拉格朗日乘子法，得到子优化问题P3的拉格朗日函数如下：

$$
\begin{array} { c } { { { \displaystyle { \cal L } ( { \mathcal P } , { \mathcal C } ) = \sum _ { n = 1 } ^ { N } p _ { n } + \beta _ { 1 } \Biggl ( R _ { S } - \sum _ { i \in \mathcal C _ { l } } \log \biggl ( 1 + \frac { p _ { i } ^ { I } h _ { i } } { \sigma _ { i } ^ { 2 } } \biggr ) \biggr ) + } } } \\ { { { \displaystyle { \beta _ { 2 } \Biggl ( W _ { D } - \sum _ { j \in \mathcal C _ { E } } \bigl ( \alpha _ { 1 } ( p _ { j } ^ { E } ) ^ { 2 } h _ { j } ^ { 2 } + \alpha _ { 2 } p _ { j } ^ { E } h _ { j } + \alpha _ { 3 } \bigr ) \Biggr ) } } } } \end{array}
$$

其中， $\beta _ { \imath }$ 和 $\beta _ { 2 } \left( \beta _ { 1 } \ge 0 \ , \beta _ { 1 } \ge 0 \right.$ )为拉格朗日乘子。

子优化问题P3的拉格朗日对偶函数为

$$
g ( \pmb { \beta } ) = \operatorname* { m i n } _ { ( \mathcal { P } , \mathcal { C } ) } L ( \mathcal { P } , \mathcal { C } )
$$

其中， $\pmb { \beta } = ( \beta _ { 1 } , \beta _ { 2 } )$ 。得到子问题P3的对偶优化问题为

$$
\displaystyle \operatorname* { m a x } _ { \beta } g ( \beta )
$$

使用次梯度算法求解对偶问题中的对偶变量 $\beta$ ，次梯度表达式为

$$
\begin{array} { c } { { \Delta \beta _ { 1 } = R _ { s } - \displaystyle \sum _ { i \in \mathcal { C } _ { l } } \log \left( 1 + \frac { p _ { i } ^ { I } h _ { i } } { \sigma _ { i } ^ { 2 } } \right) } } \\ { { \Delta \beta _ { 2 } = W _ { D } - \displaystyle \sum _ { j \in \mathcal { C } _ { E } } ( \alpha _ { 1 } ( p _ { j } ^ { E } ) ^ { 2 } h _ { j } ^ { 2 } + \alpha _ { 2 } p _ { j } ^ { E } h _ { j } + \alpha _ { 3 } ) } } \end{array}
$$

其中， $\Delta \pmb { \beta } = ( \beta _ { 1 } , \beta _ { 2 } )$ ， $\beta$ 根据 $\pmb { \beta } ^ { \iota + 1 } = \pmb { \beta } ^ { \iota } + \nu ^ { \iota } \Delta \pmb { \beta }$ 逐渐更新。根据减小步长方法，迭代步长 $\nu ^ { t } = \omega / t$ 。其中， $\omega$ 为常数，次梯度方法可保证对偶变量收敛于最优解 $\pmb { \beta } ^ { * } = ( \beta _ { _ 1 } ^ { * } , \beta _ { _ 2 } ^ { * } )$ [24]。

# 2.3源端功率分配

根据对偶函数式(19)，在确定的对偶变量 $\pmb { \beta } = ( \beta _ { 1 } , \beta _ { 2 } )$ 下，求解源端发射功率分配最优解 $\mathcal { P } ^ { * } = \{ p _ { i } ^ { I ^ { * } } , p _ { j } ^ { E ^ { * } } \}$ 。对于给定的子载波分配 $\boldsymbol { \mathcal { C } } = \{ \boldsymbol { \mathcal { C } } _ { I } , \boldsymbol { \mathcal { C } } _ { E } \}$ ，可对式(18)所示的拉格朗日函数其优化变量 $\boldsymbol { p } _ { n }$ 求偏导，得(22)式：

$$
\begin{array} { c } { \displaystyle \frac { \hat { \alpha } L ( \mathcal { C } , p _ { i } ^ { I } ) } { \hat { \sigma } p _ { i } ^ { I } } { = } 1 - \frac { \beta _ { 1 } h _ { i } } { \sigma _ { i } ^ { 2 } + p _ { i } ^ { I } h _ { i } } } \\ { \displaystyle \frac { \hat { \alpha } L ( \mathcal { C } , p _ { j } ^ { E } ) } { \hat { \sigma } p _ { j } ^ { E } } { = } 1 - 2 \alpha _ { 1 } \beta _ { 2 } p _ { j } ^ { E } h _ { j } ^ { 2 } - \alpha _ { 2 } \beta _ { 2 } h _ { j } } \end{array}
$$

根据Karush-Kuhn-Tucker条件，拉格朗日函数的偏导数在最优解处为零。因此，源端功率最优解 $\mathcal { P } ^ { * }$ 为

$$
p _ { i } ^ { I ^ { * } } = \left( \beta _ { 1 } - \frac { \sigma _ { i } ^ { 2 } } { h _ { i } } \right) ^ { + }
$$

$$
\begin{array}{c} p _ { j } ^ { E ^ { * } } = \left\{ \begin{array} { l l } { p _ { \operatorname* { m i n } } , p _ { j } ^ { E } h _ { j } + \sigma _ { j } ^ { 2 } \leq p _ { l o w } } \\ { \displaystyle - \alpha _ { 2 } \beta _ { 2 } h _ { j } } \\ { \displaystyle - \alpha _ { 1 } \beta _ { 2 } h _ { j } ^ { 2 } } \end{array} \right. +  \\ { p _ { \operatorname* { m a x } } , p _ { j } ^ { E } h _ { j } + \sigma _ { j } ^ { 2 } \geq p _ { u p } } \end{array}
$$

其中， $p _ { \mathrm { m i n } } = 0$ ， $p _ { \operatorname* { m a x } } = ( p _ { \ast p } - \sigma _ { j } ^ { 2 } ) / h _ { j }$ 。

# 2.4优化子载波分配

根据对偶函数式(19)，在确定的对偶变量 $\pmb { \beta } = ( \beta _ { 1 } , \beta _ { 2 } )$ 下，将求得的源端最优发射功率 $\mathcal { P } ^ { * } = \{ p _ { I } ^ { * } , p _ { E } ^ { * } \}$ 代入(18)式所示的拉格朗日函数，对其整理并化简为(25)(26)式，求解子载波分配最优解 $\mathcal { C } ^ { * } = \{ \mathcal { C } _ { I } ^ { * } , \mathcal { C } _ { E } ^ { * } \}$ □

$$
\begin{array} { c } { { { \displaystyle { \cal L } ( \mathcal { C } ) = \beta _ { 1 } R _ { s } + \beta _ { 2 } \gamma + \sum _ { \ell \ell \ell } \left( p _ { i } ^ { \prime \prime } - \beta _ { 1 } \log ( 1 + \frac { p _ { i } ^ { \prime \prime } h _ { i } } { \sigma _ { i } ^ { 2 } } ) \right) + } } } \\ { { { \displaystyle { \sum _ { j \ell \ell } \left( p _ { j } ^ { \ell \mathrm { s } } - \beta _ { 2 } \left( \alpha _ { 1 } ( p _ { j } ^ { \ell \mathrm { s } } / h _ { j } + \sigma _ { j } ^ { 2 } ) ^ { 2 } \right) + \alpha _ { 2 } ( p _ { j } ^ { \ell \mathrm { s } } / h _ { j } + \sigma _ { j } ^ { 2 } ) + \alpha _ { 3 } \right) } \right) = } } } \\  { { \displaystyle { \beta _ { 1 } R _ { s } + \sum _ { j \ell \ell } \left( p _ { j } ^ { \ell \mathrm { s } } - \beta _ { 2 } ( \alpha _ { 1 } ( p _ { j } ^ { \ell \mathrm { s } } h _ { j } + \sigma _ { j } ^ { 2 } ) ^ { 2 } + \alpha _ { 2 } ( p _ { j } ^ { \ell \mathrm { s } } h _ { j } + \sigma _ { j } ^ { 2 } ) + \alpha _ { 3 } ) - \right. } } } \\  { { \displaystyle { \left. p _ { j } ^ { \prime \mathrm { s } } + \beta _ { 1 } \log ( 1 + \frac { p _ { j } ^ { \prime \prime } h _ { i } } { \sigma _ { i } ^ { 2 } } ) ) + \beta _ { 2 } \gamma + \sum _ { n = 1 } ^ { N } \biggl ( p _ { n } ^ { \prime \mathrm { s } } - \beta _ { 1 } \log ( 1 + \frac { p _ { n } ^ { \prime \prime } h _ { n } } { \sigma _ { n } ^ { 2 } } ) \biggr ) = } } } \\  { { \displaystyle { \sum _ { j \ell \ell } G _ { j } ^ { \prime } + \beta _ { 1 } R _ { s } + \beta _ { 2 } \gamma + \sum _ { n = 1 } ^ { N } \biggl ( p _ { n } ^ { \prime \mathrm { s } } - \beta _ { 1 } \log ( 1 + \frac { p _ { n } ^ { \prime \prime } h _ { n } } { \sigma _ { n } ^ { 2 } } ) \biggr ) } } } \end{array}
$$

其中， $\pmb { \beta } = ( \beta _ { 1 } , \beta _ { 2 } )$ 。得到子问题P3的对偶优化问题为

$$
\begin{array} { c } { { G _ { j } ^ { * } = p _ { j } ^ { E ^ { * } } - \alpha _ { 1 } \beta _ { 2 } ( p _ { j } ^ { E ^ { * } } h _ { j } + \sigma _ { j } ^ { 2 } ) ^ { 2 } - } } \\ { { { } } } \\ { { \alpha _ { 2 } \beta _ { 2 } ( p _ { j } ^ { E ^ { * } } h _ { j } + \sigma _ { j } ^ { 2 } ) - \alpha _ { 3 } \beta _ { 2 } - p _ { j } ^ { I ^ { * } } + \beta _ { 1 } \log ( 1 + \displaystyle \frac { p _ { j } ^ { I ^ { * } } h _ { j } } { \sigma _ { j } ^ { 2 } } ) } } \end{array}
$$

其中， $p _ { j } ^ { I ^ { * } } = \left( \beta _ { 1 } - \frac { \sigma _ { j } ^ { 2 } } { h _ { j } } \right) ^ { + }$ （20 $j \in \mathcal { C } _ { E }$ 。同时，为简化计算，令$p _ { n } ^ { I ^ { * } } = \left( \beta _ { 1 } - \frac { \sigma _ { n } ^ { 2 } } { h _ { n } } \right) ^ { + } , \forall n \in \mathcal { N } \mathrm { ~ \Omega ~ } _ { \circ }$

在式(25)中，只有第一项 $G _ { j } ^ { * }$ 受载波集合 $\mathcal { N }$ 划分结果的影响，其他项均为常数。因此，根据仅包含优化变量 $\mathcal { C } _ { E }$ 的式(26),可得到集合 $\mathcal { C } _ { E }$ 的最优解 $\mathcal { C } _ { E } ^ { * }$ ，

$$
\mathcal { C } _ { E } ^ { * } = \arg \operatorname* { m i n } _ { \mathcal { C } _ { E } } \sum _ { j \in \mathcal { C } _ { E } } G _ { j } ^ { * } .
$$

在载波集合 $\mathcal { N }$ 的划分结果(即 $\mathscr { C } _ { I }$ 和 $\mathcal { C } _ { E }$ )未知条件下，为使子问题P3的拉格朗日对偶函数最小，应当将子载波 $j$ 在集合 $\mathcal { N }$ 中遍历，即将功率的最优值 $p _ { j } ^ { I ^ { * } }$ 和 $p _ { j } ^ { E ^ { * } }$ 代入式(26)。若式(26)的函数值为负，则将该子载波 $j$ 划分到集合 $\mathcal { C } _ { E } ^ { * }$ 中。最终，所有能使(26)式函数值为负的子载波 $j$ 所构成的集合，即为用于能量传输子载波的最优解 $\mathcal { C } _ { E } ^ { * }$ 。根据 $\mathcal { C } _ { I } ^ { \ast } \cup \mathcal { C } _ { E } ^ { \ast } = \mathcal { N }$ ，可得到用于信息传输的最优载波集合 $\boldsymbol { \mathcal { C } } _ { I } ^ { * }$ 为

$$
\begin{array} { r } { \mathcal { C } _ { I } ^ { * } = \overline { { \mathcal { C } _ { E } ^ { * } } } . } \end{array}
$$

初始化对偶变量 ${ \pmb \beta } ( 0 )$ ，迭代次数 $k = 0$ ，可得到子载波和功率联合分配的最优解 $\mathcal { P } ^ { * } = \{ p _ { i } ^ { I ^ { * } } , p _ { j } ^ { E ^ { * } } \}$ 和 $\mathcal { C } ^ { * } = \{ \mathcal { C } _ { E } ^ { * } , \mathcal { C } _ { I } ^ { * } \}$ 。将 ${ { \mathcal P } ^ { * } }$ 和$\boldsymbol { \mathscr { C } } ^ { * }$ 代入式(21)，可得P3对偶优化问题的次梯度 $\Delta \beta$ ，更新$k = k + 1$ ，进而根据次提梯度下降方法得到 $\beta ( k )$ 。当$\pmb { \beta } ( k ) - \pmb { \beta } ( k - 1 )$ 不满足收敛条件时，根据 $\beta ( k )$ 重新计算 ${ { \mathcal { P } } ^ { * } }$ 和 $\boldsymbol { \mathcal { C } } ^ { * }$ ，否则，算法结束，输出P3目标函数的最优值。初始优化问题P1的求解方法可归纳为联合子载波和功率分配(jointsubcarrierand powerallocation,JSPA)算法，算法流程图如图2所示。

算法1联合子载波和功率分配算法a）设置迭代次数 $k = 0$ ，初始化 $R _ { s } , R _ { D } , d , T _ { 1 } , T _ { 2 } , M , N$ ：b）根据式(16)计算 $\lambda ^ { * }$ ，根据式(17)计算 $\{ q _ { m } ^ { * } , W _ { D } \}$ c）初始化 $\beta _ { 1 } ( 0 ) = 1 , \beta _ { 2 } ( 0 ) = 1$

d）根据式(23)和(24)，计算功率分配最优解 $p _ { i } ^ { { t } ^ { * } }$ 和 $p _ { j } ^ { E ^ { * } }$ e）根据式(27)和(28)，得到子载波分配最优解 $\mathcal { C } _ { E } ^ { * }$ 和 $\boldsymbol { \mathcal { L } } _ { I } ^ { * }$ f)更新 $k = k + 1$ ，根据式(21)更新对偶变量 $\{ \beta _ { 1 } ( k ) , \beta _ { 2 } ( k ) \}$ g）如果 $\mid \beta _ { 1 } ( k ) - \beta _ { 1 } ( k - 1 ) \mid < \varepsilon , \mid \beta _ { 2 } ( k ) - \beta _ { 2 } ( k - 1 ) \mid < \varepsilon$ ,结束循环，输出 $\{ \beta _ { 1 } ( k ) , \beta _ { 2 } ( k ) \}$ 和 $\{ ( \mathcal { C } _ { I } ^ { * } , \mathcal { C } _ { E } ^ { * } ) , ( p _ { i } ^ { I ^ { * } } , p _ { j } ^ { E ^ { * } } ) , q _ { m } ^ { * } \}$ ；否则，返回步驟d)继续循环。

提出的JSPA 算法输入量包括源端和终端的最小数据传输速率阈值 $R _ { s }$ 和 $R _ { D }$ ，源端与终端之间的传输距离 $^ d$ ，上行和下行链路划分的子载波数量 $M$ 和 $N$ ，以及上下行链路的传输时隙 $T _ { \mathrm { l } }$ 和 $T _ { 2 }$ 。算法输出结果包括下行链路分别用于信息传输和能量传输的子载波分配方式 $\boldsymbol { \mathcal { C } } _ { I } ^ { * }$ 和 $\mathcal { C } _ { E } ^ { * }$ ，以及上下行链路各子载波上的功率分配方案 $q _ { m } ^ { * } , m \in M$ 和 $p _ { n } ^ { * } , n \in N$ 。

优化问题P1通过分解等价转换为P2和P3两个子优化问题问题。其中，子优化问题P2为凸优化问题，通过拉格朗日乘子法可得到其最优解，而子优化问题P3约束条件中存在优化变量的相互耦合，为非凸优化问题，为了得到其最优解，需要先将P3转换为凸优化问题。根据凸优化理论，无论原优化问题是否为凸优化问题，其拉格朗日对偶问题一定为凸优化问题[25]，将非凸的P3优化问题转换为凸的对偶优化问题式(20)，式(20)的优化变量满足time-sharing条件[24]，则式(20)与P3优化问题之间为强对偶关系，因此式(20)的最优解就是P3的最优解，P2和P3的最优解保证了提出的JSPA算法求得的最优解为原优化问题P1的最优解。

开始步骤1 初始化 $R _ { D } \sqrt { s }$ 、MN、d等相关参数采用拉格朗日乘子法，解决子优化问题P2，利用KKT条件和步 求导公式求得对偶变量最优解入骤2根据式(17)计算终端传输功率最优值 $\boldsymbol { q } _ { m } ^ { * }$ 和终端最小能耗 $W _ { p }$   
步骤3 初始化非负对偶变量值 $\overline { { \{ \beta _ { 1 } , \beta _ { 2 } \} } }$ 针对子优化问题P3，采用拉格朗日对偶方法，得到其对偶优化问题  
步  
骤  
4 利用KKT条件，在确定的对偶变量β下，根据式(23)和(24)计算功率分配最优值 $p _ { i } ^ { I ^ { : } }$ 和 $p _ { j } ^ { E ^ { * } }$ 在已知的对偶变量 $\beta$ 和优化变量 $\{ p _ { i } ^ { I } , p _ { j } ^ { E } \}$   
步 下，采用换元法重写子优化问题P3的  
骤5 拉格朗日函数，并根据式(27)和(28)计否算子载波分配最优值 $\boldsymbol { \mathcal { C } } _ { E } ^ { * }$ 和 $\boldsymbol { \mathcal { C } } _ { I } ^ { * }$ 采用次梯度方法根据式  
步骤6(21)更新对偶变量{β,β}判断对偶变量是否收敛步骤 是7输出子优化问题P3的最优解结束

本算法在拉格朗日对偶变量求解步骤中采用的次梯度算法，其算法复杂度为 $O ( L ^ { \kappa } )$ [26]，其中 $\boldsymbol { L }$ 为对偶变量个数， $\kappa$ 为非负整数。由于本算法只涉 $\beta _ { \mathrm { { l } } }$ 和 $\beta _ { 2 }$ 两个对偶变量，因此，该步骤的算法复杂度为 $O ( 2 ^ { \kappa } ) { = } O ( 1 )$ 。在子载波分配求解步骤中算法复杂度和子载波数量 $N$ 成正比，该步骤的算法复杂度为$O ( N )$ ，因此算法整体计算复杂度为 $O ( 1 \times N ) { = } O ( N )$ 0

# 3 数值仿真

本节分析和验证子载波和传输功率联合分配算法的有效性。在微波功率传输可行环境中，源端发射功率与终端接收功率间的关系满足式(29)[27],

$$
\frac { P _ { r } } { P _ { R } } { = } \frac { A _ { t } A _ { r } } { { \lambda _ { c } } ^ { 2 } d ^ { 2 } } | Z | ^ { 2 }
$$

其中， $\lambda _ { c }$ 是波长， $\textit { d }$ 是源端到终端的传输距离，A和 $A _ { r }$ 分别是发射天线阵列和接收天线阵列的总孔径， $z$ 为复高斯随机变量， $Z \sim \mathcal { L N } ( 1 , 0 . 2 )$ 。本文中， $f = \mathbf { v } _ { c } / \lambda _ { c } = 2 . 4 \mathrm { G H z }$ ， $\nu _ { c } = 3 { \times } 1 0 ^ { 8 } m / s$ ，$d = 2 m$ ， $A _ { t } = 0 . 1 m ^ { 2 }$ ， $A _ { r } = 0 . 0 5 m ^ { 2 }$ [28]，子载波数量 $N = M = 4$ ，满足源端和终端服务质量需求的数据传输速率为$R _ { S } = R _ { D } = 1 6 \mathrm { { i t / s e c / H z } }$ ，源端用于信息传输信道上的噪声$\sigma _ { i } ^ { 2 } = 0 . 0 0 1$ （ $i \in \mathcal { C } _ { I }$ )，用于能量传输信道上的噪声 $\sigma _ { j } ^ { 2 } = 0 \big ( j \in \mathcal { C } _ { E } \big )$ ，终端受到的噪声干扰 $n _ { m } ^ { 2 } = 0 . 0 0 1 \left( \begin{array} { l } { m \in \mathcal { M } } \end{array} \right)$ 。能量收集电路所允许的输入功率范围为 $P _ { l o w } = 1 0 ^ { - 3 } \mu W$ ， $P _ { u p } = 3 2 0 0 \mu W$ [22]。

图3给出了在线性EH模型和非线性EH模型下，源端最小能耗与能量收集门限的关系。当线性能量收集(LinearEH.LEH)模型运用于子载波和功率联合分配算法时，终端将根据线性能量转换效率获得可用能量。由图3可知，当LEH模型中转换效率 $\xi$ 为0.2和0.4时，源端最小能耗高于使用非线性能量收集(Non-LinearEH,NLEH)模型时的最小能耗。在LEH算法中，仿真结果显示终端实际采集到的能量高于其能量收集门限，说明功率与子载波在分配机制设计上不合理，加剧了源端能量消耗。当LEH模型中转换效率 $\xi$ 为0.6时，源端最小能耗值低于采用NLEH模型时的源端能耗。这表明LEH模型设置过高的能量转换效率值 $\xi$ 会导致分析结果过于理想偏离了实际，如果采用该方案分配网络资源，网络能耗虽少但由于未考虑EH电路的饱和特性，其实际收集能量并达不到用户能量收集门限。综上所述，采用LEH模型分析携能通信网络性能时，无论转换效率 $\xi$ 设置为何值，其分析结果终会与实际网络性能有所偏差，而基于NLEH模型的子载波和功率联合分配算法能够根据实际EH电路的非线性特性，合理有效地分配子载波和传输功率等网络资源，满足双向携能网络对数据传输速率的需求，分析结果更符合实际。

![](images/28076157b581484acb6be9c3417e23153a0798442c2730d231d3bc2fdb92db07.jpg)  
图3源端最小能耗随能量收集门限的变化

图4显示了子载波和功率联合分配(jointsubcarrier andpower allocation,JSPA)算法与基准算法的性能对比。基准算法包括：分别基于PS、TS 机制的功率分配算法、固定子载波分配(fixedsubcarrierallocation,FSA)和固定功率分割(fixedpower splitting,FPS)。在基于PS机制的功率分配算法中，系统接收器采用功率分割结构设计，各个子载波上的传输功率通过PS因子 $\kappa$ 将分为两个部分， $\kappa$ 部分功率用于传输信息，$1 - \kappa$ 部分功率用于传输能量。在基于TS 机制的功率分配算法中，系统接收器采用时隙切换结构设计，终端将信号传输的单位时隙通过TS因子 $\omega$ 分为两个阶段：时隙的第一个阶段oT用于能量收集，时隙第二个阶段 $( 1 - \omega ) T _ { \scriptscriptstyle 1 }$ 用于信息解码。在FSA算法的下行链路上，两个子载波用于信息传输，另两子载波用于射频能量传输，而源端与终端的传输功率则通过注水法加以分配。在FPS算法中，源端与终端分别根据子载波的质量为其分配传输功率，以使得每个子载波上的数据速率等于速率阈值。

由图4可知，本文所提出的JSPA联合优化算法，在源端最小能耗方面，整体优于其他对比算法。首先，基于PS 和TS 机制的功率分配算法未考虑网络信道的可分配性，因此不能根据子信道间的差异特性灵活分配传输功率。随着源端数据速率阈值的增加，相比其他考虑信道分配的算法，该两算法的功率分配方案大大增加了源端的能耗。其次，FSA算法忽略了信息传输与能量传输的不同特性，其固定不变的信道划分和使用方式，浪费了源端能量。然后，FPS算法根据速率阈值为子载波分配功率，这种方式无法实现功率与子载波质量间的最佳匹配，过度消耗了源端能量。可预见的是，当选用频率选择性衰落信道时，子载波质量的差异性将明显增强，FPS算法中的源端能耗也将增大。最后，JSPA算法中，子载波按照功能(信息传输、能量传输)实现了最优角色划分，而且每条载波上的传输功率值也最佳匹配于载波质量和载波角色。因此，JSPA算法能够在满足数据速率阈值的前提下，降低源端能量开销。

![](images/cbde576301e04b1f66211543128a64b2e3c2e58e2c3719b3467f5869984c23d6.jpg)  
图4源端最小能耗随源端数据速率阈值的变化  
Fig.4Minimal energy consumption of source vs.threshold ol required rate at destination

子载波和功率联合分配算法的收敛行为如图5和6所示。可以看出当距离 $d$ 为 $2 \mathrm { m }$ ，能量收集门限 $W _ { D }$ 为 $0 . 9 \mathrm { m w }$ ，最小数据传输速率阈值 $R _ { S } = { { I b i t } / { s e c } } / { { H z } }$ 时，随着迭代次数t的增加，图5中拉格朗日乘子 $\beta _ { 1 }$ 收敛到最优解0.0025、 $\beta _ { 2 }$ 收敛到最优解18.15，图6得到最小化源端能耗优化问题的最优值。联合观察图5和6，在迭代次数为20左右，源端总能耗数值基本收敛，体现了提出的子载波和功率联合分配算法的有效的收敛性。

![](images/a0d77acf63d1dfc86e1e04745e8fcef8d2cc8de59c39ee1e290d9cb00d570f2f.jpg)  
Fig.3Minimal energy consumption of the source Vs.threshold of energy harvested at destination   
图5拉格朗日乘子 $\beta _ { 1 }$ 和 $\beta _ { 2 }$ 的收敛行为  
Fig.5Convergence behavior of Lagrange multipliers $\beta _ { 1 }$ and $\beta _ { 2 }$

![](images/062bee78a63e36b8b75c145490653733c2c485694eadb772f17ae7c969ca7cb3.jpg)  
图6子载波和功率联合分配算法收敛行为

终端最小能耗(源端能量收集门限)与数据速率阈值和传输距离 $^ d$ 的关系如图7所示。由图7可知，随着数据速率阈值的增大，终端最小能耗随之增加。当传输距离固定时，速率阈值增大迫使终端消耗更多功率提高可达数据速率。当固定速率阈值时，传输距离的增加降低了信道传输质量，此时，终端需要消耗更多的能量满足不断上升的传输速率要求。

源端最小能耗与能量收集门限(终端最小能耗)和传输距离d之间的关系如图8所示。由图8可知，当数据传输速率阈值和能量收集门限固定时，随着传输距离的增大，链路质量下降，源端发射更多的功率用于信息传输导致总能耗增加。当数据传输速率阈值和传输距离不变时，能量收集门限越大，源端需要消耗更多能量用于能量传输，这导致总能耗增大。

![](images/6c72798f43e806ff7d5bc6351cb430d7285d524ee68b61f683698559717ca9d1.jpg)

![](images/050e385ffaf8bbe2f6d3301c62ee1d1441428ac1391b8747f7d07743667786ee.jpg)  
图7终端最小能耗随数据速率阈值和传输距离的变化  
图8源端最小能耗随能量收集门限和传输距离的变化 Fig.8Minimal energy consumption of the source vs.threshold of energy harvested at destination and transmission distance

当源端数据速率阈值 $R _ { s }$ 为0.5、1.0和 $1 . 5 ~ \mathrm { b i t / s e c / H z }$ 时，使用JSPA联合优化算法得到的子载波和功率联合分配方案如图9所示。由图9可知，在固定的传输距离和能量收集门限下，源端数据速率阈值越大，迫使源端向子载波分配更多功率，以满足升高的速率要求。当源端通过增大数据载波上的传输功率不能达成能耗最小化的目标时，JSPA算法将动态调整子载波角色，划分更多的子载波用于数据传输。

在源端能量收集门限(终端最小能耗） $W _ { D }$ 为 $5 0 0 \mu W$ 、$1 5 0 0 \mu W$ 和 $2 5 0 0 \mu W$ 时，JSPA联合优化算法得到的资源分配方案如图10所示。由图10可知，当固定传输距离和数据速率阈值时，随着能量收集门限的增大，为维持终端增大的能量需求，源端需要分配更多数量的子载波用于射频能量传输，导致用于传输数据的子载波的数目减少。综合观察图9和图10,源端为子载波分配的功率主要用于能量收集。这是因为：a)射频能量的转换效率较低，需要更多的传输功率才能达到能量收集门限；b)设定的数据速率阈值小，源端消耗少量功率即可满足速率需求。

![](images/eb355402d1b0fd1e9389d8ddc55e8e7b44991030055be10a907c0ad18dd2f3e8.jpg)  
Fig.6Convergence behavior of joint subcarrier and power allocation algorithm   
图9子载波和功率分配随源端数据速率阈值的变化Fig.9Allocation of subcarriers and power vs.

![](images/7b56afd5958b592722192fd3f28c89cb6d5bb5759e062da137cb619a1aeb0b14.jpg)  
Fig.7Minimal energy consumption of the destination vs.threshold of required rate at destination and transmission distance   
图10子载波和功率分配随能量收集门限的变化 Fig.10Allocation of subcarriers and power vs. threshold of energy harvested at destination

# 4 结束语

针对双向携能通信网络，本文提出了一种面向子载波和功率的联合分配算法。源端将可用的OFDM子载波划分为两组，分别用于信息传输和射频能量传输。JSPA算法以源端能量开销最小为目标，根据能量采集电路的饱和特性，采用非线性能量采集模型，在满足速率阈值要求的前提下，得出子载波最优划分和功率匹配结果。与传统携能通信机制不同的是无须功率分流器和时隙切换器，JSPA简化了携能机制设计

下一阶段工作欲将人工噪声引入多输入多输出的双工SWIPT网络，着重提升用户信息安全性，最大化网络能量效率。

# 参考文献：

[1]Perera T,Jayakody D,Sharma S,et al.Simultaneous wireless information and power transfer (SWIPT):recent advances and future challenge[J].IEEE Communications Surveys and Tutorials,2018,20(1): 264-302.   
[2]Xiong Ke,Chen Chen,Qu Gang,et al.Group cooperation with optimal resource allocation in wireless powered communication networks [J]. LEEI Jojo   
[3]Varshney LR. Transporting information and energy simultaneously [C]// Proc of IEEE International Symposium on Information Theory.Toronto: IEEE Press,2008:1612-1616.   
[4] 徐勇军，胡圆，李国权，等．异构携能通信网络顽健资源分配算法 [J].通信学报,2019(7):186-196.(Xu Yongjun,Hu Yuan,Li Guoquan, et al.Robust resource allocation algorithm for heterogeneous wireless networkwith SWIPT[J].Journal on Communications,2019(7):186-196.)   
[5] 王伟，李鑫睿，殷柳国，等．联合能量收集中继与全双工目的节点的 安全资源分配方案 [J]．通信学报,2019,40(1):110-118.(WANG Wei. Secure resource allocation in hybrid energy-harvesting relay and fullduplex receiver [J]. Journal on Communications,2019,40 (1): 110-118.)   
[6]Zhou Xun, Zhang Rui,Ho C K.Wireless information and power transfer: architecture design and rate-energy tradeoff [J]. IEEE Transactions on Communications,2012,61 (11): 4754-4767.   
[7]Liu L,Zhang R,Chua K C.Wireless information transfer with opportunistic energy harvesting [J]. IEEE Transactions on Wireless Communications,2013,12(1):288-300.   
[8] Liu Liang, Zhang Rui, Chua K C.Wireless information and power transfer: a dynamic power splitting approach [J]. IEEE Transactions on Communications,2013,61 (9): 3990-4001.   
[9]Liu Yuan,Wang Xiaodong. Information and energy cooperation in OFDM relaying:protocols and optimization [J]. IEEE Transactions on Vehicular Technology,2016,65 (7): 5088-5098.   
[10] Tang Jie,Luo Jingci,Liu Mingqian,et al. Energy eficiency optimization for NOMA with SWIPT[J].IEEE Journal of Selected Topics in Signal Processing,2019,13 (3): 452-466.   
[11] Ju H, Zhang Rui.A novel mode switching scheme utilizing random beamforming for opportunistic energy harvesting [J]. IEEE Transactions on Wireless Communications,2014,13 (4): 2150-2162.   
[12] Lu Weidang，Fang Shanzhen，Hu Su，et al.Energy efficiency optimization for OFDM based 5G wireless networks with simultaneous wireless information and power transfer [J].IEEE Access,2018(6): 75937-75946.   
[13] Kang J,Kim I,Kim D I. Joint optimal mode switching and power adaptation for nonlinear energy harvesting SWIPT system over fading channe [J].IEEE Transactions on Communications,2018,66 (4):1817- 1832.   
[14] Gao Xiaozheng, Yang Kai,Wu Jinsong,et al. Energy efficient resource allocation and power Control for downlink multicell OFDMA networks [C]//Proc of IEEE Global Communications Conference (GLOBECOM) . Singapore: IEEE Press,2017: 1-6.   
[15] Ghanem WR, Jamali V, Sun Yang,et al. Resource allocation for multiuserdownlink URLLC-OFDMA systems[C]//Proc of IEEE Workshops) .Shanghai, China: IEEE Press,2019:76-83.   
[16] Yin Sixing,Qu Zhaowei.Resource allocation in multiuser OFDM systems with wireless information and power transfer [J].IEEE Communications Letters,2016,20 (3): 594-597.   
[17] Na Zhenyu,Wang Yuyao,Li Xiaotong,et al. Subcarrier allocation based simultaneous wireless information and power transfer algorithm in 5G cooperativeOFDMcommunicationsystems [J] Physical Communication,2018,29:164-170.   
[18] Li Qun, Xu Ding. Outage minimized joint power splitting and resource allocation optimization for multiuser OFDM systems with SWIPT[C]// Proc of IEEE International Conference on Communications in China (ICCC). Changchun, China: IEEE Press,2019:717-725.   
[19] Kang J,Kim I,Kim DI.Wireless information and power transfer: rateenergy tradeoff for nonlinear energy harvesting[J]. IEEE Transactions on Wireless Communications,2018,17(3): 1966-1981.   
[20] Lu Yang,Xiong Ke,Fan Pingyi, et al. Robust transmit beamforming with artificial redundant signals for secure SWIPT system under non-linear EH model[J].IEEE Transactions on Wireless Communications,2018,17 (4): 2218-2232.   
[21] Boshkovska E,Ng DW K,Zlatanov N,et al.Practical non-linear energy harvesting model and resource allocation for SWIPT systems [J]. IEEE Communications Letters,2015,19 (12):2082-2085.   
[22] Xu X,Ayca Ozcelikkale,Mckelvey T,et al. Simultaneous information and power transfer under a non-linear RF energy harvesting model [C]// Proc of IEEE International Conference on Communications Workshops (ICCWorkshops) .Paris,France: IEEE,2017: 1-18.   
[23] Konstantinos M,Adamis A, Constantinou P.Receiver architectures for OFDMA systems with subband carrier allocation [C]/ Proc of European Wireless Conference. Prague, Czech: IEEE Press,2008: 1-7.   
[24] Yu Wei,Lui R. Dual methods for nonconvex spectrum optimization of multicarrier systems [J].IEEE Transactions on Communications,2006, 54 (7): 1310-1322.   
[25] Boyd S,Vandenberghe L.Convex Optimization [M].U.K.:Cambridge University Press,2004.   
[26] Dang Wenbin,Tao Meixia,Mu Hua,et al. Subcarrierpair based resource allocation for cooperative AF multirelay OFDM systems [J].IEEE Transactions on Wireless Communications,2010,9 (5): 1640-1649.   
[27] Brown W C,Eves EE.Beamed microwave power transmission and its application to space [J].IEEE Transactions on Microwave Theory and Techniques,1992,40 (6):1239-1250.   
[28] Huang Kaibin,Larsson E. Simultaneous information and power transfer for broadband wirelesssystems [J]. IEEE Transactions on Signal Processing,2013,61(23): 5972-5986.