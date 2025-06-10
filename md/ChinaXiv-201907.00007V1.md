# 多区域电力系统日前发输电计划方法 以中国南方电网为例

陈亦平¹，郑晓东²，陈皓勇²，张勇」，陈静鹏」，培正（中国南方电网电力调度控制中心；广东 广州 510623;2.华南理工大学 电力学院，广东广州 510640；3.南方电网科学研究院，广东广州510263）

摘要：多区域电力系统的优化调度存在与调度模式相适应和建模求解等方面的困难。本文基于我国网省两级调管模式和省间中长期电量协议的背景，提出以简化省级系统和优化净发电序列方差为基础的多区域日前发输电计划模型，模型能够非迭代地求取优化的交、直流联络线功率计划和直调电厂机组出力计划，并针对性地考虑了直流输电曲线阶梯化和网省间局部交流断面潮流限值等实用化约束。采用中国南方电网多省区交、直流互联系统的实际数据，验证了模型的有效性和可行性，证明模型能够利用较少的信息，在上级调度机构层面形成改进的且对省区安全可行的送受电计划，降低省区发电的峰谷差和标准差，缓解调峰压力，提高整体运行效益。所提方法适用于我国当前的调度体制及不同场景，已经在电网调度计划编制上取得应用。

关键词：多区域；发输电；日前计划；调峰；优化调度

# 0引言

在多区域互联电力系统中，合理安排送受电或进行电力市场化交易，能够提高系统运行的经济性。中国南方电网作为典型的多区域互联电力系统（在我国区域电网特指六大区域电网，其中每个区域电网由多个省区电网/控制区组成；本文的多区域电力系统则指代包含多个控制区的系统，相当于我国的区域电网)，各省区的发电资源和负荷特性存在互补性，通过协调省间送受电计划，能够有效减小系统的调峰压力，提高各区域的运行效益。

纵观国内外多区域电力系统，在计划体制中通常依赖系统运行人员的经验编制日前发输电计划，或者以公平、节能、经济等为目标优化计划；在市场化的机制中则以社会福利最大化为目标，求解交易出清模型形成发输电计划。在北美电力市场，各ISO（Independent System Operator）基于预先设置的代理节点协调优化区域间日前交易计划，而理论研究则多采用分布式SCUC（SecurityConstrainedUnitCommitment）来解决区域间输电计划问题[1]。在欧洲跨国界电力交易中，日前市场基于ATC（AvailableTransferCapacity）或FBMC（Flow-BasedMarketCoupling）的物理简化方法出清，从而得到跨国界输电计划的日前份额[2]。

我国的多区域互联电力系统，电网调度实行“统一调度，分级管理"模式。在分级管理的模式下，上级调度机构（网调/总调）直接编制日前的省间联络线计划和直调电厂的发电计划，省级调度机构（省调/中调）根据上级下发的联络线功率计划，编制省内发电计划[3]。如果网调下发的初始省间送受电计划造成省级电网明显的效益或安全性问题，则调整联络线计划。由于目前网省两级日前发输电计划编制主要依赖人工经验和排序方法，没有较为严格的数学模型作为决策依据，容易引发以下问题：跨区域输电计划与受端负荷需求不协调，如西部云南等区域的水电出力和外送的峰谷水平、峰谷时段、爬坡速率与东部受端广东的负荷特性不匹配，使得广东省内火电机组面临较大的调峰压力，且运行效益降低；其次，网省间交流断面功率容易越限，如云南异步互联系统的各回直流与配套水电厂功率的失配量过大使得邻近的交流断面临近或超过限值[4]。

为解决上述经济性和安全性问题，理论上可以求解多区域系统的全局SCUC模型来确定发输电计划，但是全局优化有悖于网省两级的调度管理模式，且多区域系统涉及大量的设备和参数，包括梯级水电、新能源等复杂电源和交、直流联络线，全局SCUC对建模、求解、参数维护都是严厉的挑战[5]。分布式SCUC方法的应用同样存在局限性，它要求各区域或者上下级调度机构之间交互求解信息进行多次迭代，并且因为各区域子问题的非凸性（存在离散变量)，目前并不存在可以达到全局最优的分布式算法。

受限于包括上述在内的多种因素，我国多区域互联电力系统的发输电计划仍以人工编排方式为主，同时各系统的运行机构根据系统的特征和需求建立优化模型实现调度计划的改进。文[6]用网络流法编制各区域的发输电计划，最小化各区的开机容量，但没有充分考虑联络线的约束。文[7]用二次规划解决多电网调峰的网调直调水火核电力系统省间出力分配问题，但缺乏对输电网络的建模。文[8]提出了直流跨区互联电网的发输电计划高效求解模型，以直流联络线功率为引导变量识别出跨区边际机组，综合优化各区边际机组的机组组合和区域间输电计划，但需要各个区域多次求解 SCUC 模型并且进行网省两级迭代。文[9]研究了通过特高压直流输电通道进行风火联合外送的特定背景下，优化直流输电功率改善受端系统调峰裕度的方法。文[10]通过网络等值和和构造省地间联络节点价格-功率曲线，进行省地协同发电计划优化，但难以适应并推广到网省两级发输电计划优化的场景。

现有研究和方法未能较好地处理多区域电力系统的网省分级管理决策、网省两级协调、网络化建模、输电线路和直调电厂建模等问题，且通用性和扩展性较差。本文以南方电网为例，建立了一个普遍适用于我国多区域电力系统日前发输电计划优化的模式，即由网调非迭代地求取省间联络线功率计划和网调直调电厂发电计划。同时建立了与该模式相适应的数学模型：模型考虑区域间联络线和网省间局部断面，简化各省区以内系统，以降低各区域净发电序列的方差为目标决策联络线功率。最后，以南方电网为例证明本文方法得到的输电计划既能够改善区域内发电的经济性，又满足必要的安全约束，同时具有较好的适应性和可扩展性。

# 1计划优化模式

南方电网下辖广东、广西、云南、贵州、海南五省区电网，每年从西部地区经交、直流输电线送至广东的电量超过1700亿千瓦时，大规模的"西电东送"电量交易是南方电网的显著特征。然而，编制"西电东送"日前计划的流程并没有严格数学模型可以依照，难以统筹兼顾运行效益和安全稳定要求。在实践中需要解决的问题是：如何在网调层面形成优化的区域间联络线计划和直调电厂发电计划，同时考虑调管或监视范围内电广、跨区联络线和网省间局部交流断面的运行约束。

本文首先提出适合于我国多区域电力系统日前发输电计划这一应用场景的优化模式和模型的总体框架。作为日前优化调度最成熟方法的SCUC模型是基于线性化潮流方程并考虑机组技术约束的优化模型，本文所提方法与SCUC的主要区别，同时也是模型的基本前提或假设，如

# 下所述：

1）从网调的角度，将各省区系统除境内网调直调电厂及对应交流断面外的部分聚合为一个等效节点，节点带该区域的负荷并具备与该区域等量的发电能力，即忽略区域内的拓扑结构、潮流约束和机组约束；  
2）网调的任务是在给定一天各省区负荷曲线、送受电量和直调电厂发电量信息的基础上，安排区域间联络线功率计划和直调电厂机组出力计划；  
3）模型的区域间联络线包括直流和交流联络线两种类型，实际系统的直流线路与模型的直流联络线一一对应，而将两区域间物理交流线路聚合为模型中的一回交流联络线，其输电容量约束由所包含的物理交流线路潮流限值的代数和表示。

条件1）与2）与“分级管理"的调度模式和"省为实体"的经济格局相适应，网调不需要管理全网模型，省调则根据网调下发的联络线计划，考虑内部约束进行“自调度"[11]。系统中直流联络线功率是可控的，而单条交流线路功率不可控（无调相机)，通过条件3）的处理，使得模型中每回联络线的功率均可作为决策变量。把联络线功率作为决策变量，也是本文模型与 SCUC 的主要区别之一。

基于以上前提和假设，本文提出解决我国多区域电力系统日前发输电计划模型（MADS,Multi-areaPower SystemDay-ahead Generation and Transmission Power Scheduling）,模型的数据需求和数据输出如图1所示，

![](images/3e9d9b309ed4fddebe7cf14e5c1934e2be445cc23264cd2ba118ff538704da17.jpg)  
图1多区域电力系统日前发输电计划决策框架 Fig.1Frameworkof the methodology for multi-area power system day-ahead generation and transmission power scheduling

MADS 是一个混合整数规划（MIP，Mixed IntegerProgram）问题，一般形式如下

$$
\operatorname* { m i n } f ( \mathbf { y } , z )
$$

$$
\pmb { H } z \leq \pmb { h }
$$

$$
\pmb { A } \pmb { y } + \pmb { B } z \leq \pmb { 0 }
$$

其中，连续变量y包括联络线功率、区域发电出力、直调电厂及机组出力等，二进制变量 $\pmb { z }$ 用于表示直流联络线功率阶梯化特性和火电机组启停。系统运行的约束条件都可以写成线性不等式；目标函数根据实际需要确定，一般是线性或者二次函数。

由于我国省区间电力交易将在较长一段时间内保持以“西电东送"中长期框架内协议计划为主体[12]，日前计划实质上是月度分日电量的曲线化过程。在网省分级决策且非迭代的模式下无法获得全局最优的调度计划，为了达到近似最优，理论上可以基于各省区等效发电成本曲线和直调电厂发电成本函数进行优化，但实际上难以构造准确反映区域内发电成本的曲线，而对于日发电量固定的直调水电厂，其短期成本则一般不考虑。

降低发电序列方差被[9]，[13]等多项应用与研究作为给定电量情况下优化输电曲线和改善系统调峰的方法。降低发电序列方差一方面可以降低峰谷差，另一方面能够减少发电的快速爬坡和反复调节，直观上对系统内的机组（尤其是调节性能较差的煤电机组）的改善效益是很充分的。为了验证该目标是否能改善系统实际发电成本，我们采用标准测试系统进行以下测试：选择火电机组为主的标准系统，取某省区典型负荷曲线，保持日负荷量不变且对负荷曲线进行不同程度伸缩使其方差逐渐增大，将得到的一族负荷曲线用于求解同一系统的SCUC模型（SCUC模型目标函数考虑机组的启停成本和二次型可变成本，详细模型参考文[15]附录部分，这里不再赘述)，记录目标函数值并分析结果。

图2（a）为IEEE118节点系统的负荷曲线输入和成本输出对比图，它直观地显示了负荷序列方差和系统运行成本的正相关性，且对多个系统的测试均表明了此正相关性，相关系数在0.9894到0.9996之间，如图2（b）所示。

实际上由于负荷电量是固定的，发生了成本的改变主要是因为启停成本项和可变成本的二次项。平稳的发电曲线相比波动较大的曲线更有益于避免机组的启停，并使机组运行在更为经济的出力水平，从而有效降低发电成本。文[14]将波动性小的负荷定义为高品质电能商品，也是这个原因。测试可以说明以降低系统发电序列方差为目标优化区域间送受电，能够改善系统运行的经济效益。另一方面，也说明了假设1）对省网进行简化的可行性。

![](images/139f0e6d3bad846fcf5ee2ebab4707080203097ebda8fce993624516856b7dff.jpg)

![](images/90f12bc1f973fe21ba9e5900523f6cf33662fff39e7ed296d80fb5a8895656bb.jpg)  
图2系统负荷方差与运行成本关系测试结果。（a）IEEE118节点系统负荷曲线与运行成本映射图；（b）多个系统运行成本演化图。

Fig.2Numeric resultsofexploring the relationship between system demand variance and generation cost. (a) Mapping from system load profiles to generation costs;(b) Evolutions of generation costs on multiple testing systems.

# 2数学模型

# 2.1目标函数

本文MADS模型以最小化各省区净发电序列的方差为目标函数，具体如式（1）所示，

$$
\operatorname* { m i n } { f ( p _ { \Game i , t } ) } = \sum _ { i \in \mathcal { A } } { \sum _ { t \in \mathcal { T } } { \omega _ { i } \left( \frac { p _ { \ G i , t } - \overline { { p } } _ { \ G i } } { \overline { { p } } _ { \ G i } } \right) ^ { 2 } } }
$$

其中， $\bigtriangledown$ 和 $\bigtriangledown$ 分别代表区域和调度时段的集合，本文$\scriptstyle \prod = \{ 1 , 2 , \ldots , 9 6 \}$ ，即采用 $1 5 ~ \mathrm { m i n }$ 的调度周期。 $p _ { \mathtt { G } i , t }$ 代表区域i时段 $t$ 的发电出力， $\bar { p } _ { \mathtt { G } i }$ 代表区域i当天的平均出力， $\bar { p } _ { \mathtt { G } i }$ 作为分母时起对各区域出力以平均出力为基准值标幺化的作用， $\omega _ { i }$ 为权系数，可根据各区域煤电装机比例取值。（本文符号系统说明：小写表示变量、可变下标、函数；大写表示常数、参数；非倾斜体表示说明类符号或说明类上下标；EuclidMathOne字体表示集合；粗体表示向量或矩阵。）

# 2.2 约束条件

区域功率平衡约束

$$
\pmb { p } _ { \mathrm { G } t } = \pmb { C } \pmb { p } _ { \mathrm { T } t } + \pmb { P } _ { \mathrm { L } t } \forall t \in \mathcal { T }
$$

其中向量 $\pmb { p } _ { \mathrm { G } t } , \pmb { p } _ { \mathrm { T } t }$ 和 $\pmb { P } _ { \mathrm { L } t }$ 分别为时段区域发电出力，联络线功率和负荷预测值，向量的长度分别文NA，NT和NA，其中 $N A$ 是模型中区域的个数， ${ _ { N T } }$ 是联络线的数量；关联矩阵C包含联络线和区域的连接拓扑信息，若区域 $m$ 和联络线$n$ 不相连，则 $c$ 的第 $m$ 行第 $\overset { \cdot } { n }$ 列元素 $C _ { m n }$ 为0，若相连且联络线潮流流出为正，则 $C _ { m n }$ 等于1，若相连且潮流流入为正，则 $C _ { m n }$ 等于-1。由于区域间远距离送电的网损率常高达 $5 \%$ 或以上，可以将网损因子叠加到关联矩阵中联络线和受端省区对应的元素上以考虑输电损耗，如区域 $m$ 通过联络线$n$ 受入功率的输电网损率为 $4 \%$ ，则将 $C _ { m n }$ 设为-0.96。

区域间送受电量约束

$$
( 1 \mp \varepsilon _ { \mathrm { A } } ) E _ { \mathrm { A } } ^ { \mathrm { N } } \leq \sum _ { t \in T } { C } { p } _ { \mathrm { T } t } \leq ( 1 \pm \varepsilon _ { \mathrm { A } } ) E _ { \mathrm { A } } ^ { \mathrm { N } }
$$

其中 $\pmb { { \cal E } } _ { \mathrm { A } } ^ { \mathrm { N } }$ 为区域送受电量的向量，送出为正， $\varepsilon _ { \mathrm { A } }$ 为日送受电量最大允许偏差系数，一般取 $2 \%$ 。

区域发电能力限值

$$
P _ { \mathrm { G } } ^ { \mathrm { m i n } } \leq p _ { \mathrm { G } t } \leq P _ { \mathrm { G } } ^ { \mathrm { m a x } } \forall t \in T
$$

其中，可以取 $P _ { \mathrm { ~ G ~ } } ^ { \mathrm { m a x } }$ 为区域发电装机容量， $P _ { \mathrm { ~ G ~ } } ^ { \mathrm { m i n } }$ 为系统最小技术出力。允许区域总出力在一个较大的区间内取值实际上并不会使最终优化结果偏离实际，因为目标函数（1）会将出力尽量限制在一个尽可能小的范围。

联络线传输极限

$$
P _ { \mathrm { T } } ^ { \mathrm { m i n } } \leq p _ { \mathrm { T } t } \leq P _ { \mathrm { T } } ^ { \mathrm { m a x } } \forall t \in T
$$

联络线传输功率范围必须根据当天线路检修情况取值。直流联络线非停运时取 $0 . 1 { \sim } 1$ 倍额定功率，交流联络线潮流限值取两区域间所有运行的物理交流线路潮流上下限值的代数和。

直流联络线功率曲线离散约束

与交流联络线不同，直流输电的功率曲线应该满足更多约束：为了保护换流器，不允许直流功率在相邻时段反向调节；直流功率的调节伴随着交流滤波器组的投切，交流滤波器退出后需要一定的放电时间才能重新投入运行，所以不允许直流功率频繁调节。文献[8],[9],[16],[17]以不同的形式构造了离散约束组用于控制直流联络线功率曲线的阶梯化形状，本文综合各类方法的优缺点，结合调度运行经验提出了一套既能充分发挥直流灵活调节特性，又满足阶梯化要求的混合整数线性约束组，具体如下，

$$
\left\{ \begin{array} { l l } { \pmb { x } _ { t } ^ { \mathrm { D N } ( 1 ) } . \times \Delta \pmb { P } _ { \mathrm { D C } } ^ { ( 1 ) } \le \pmb { p } _ { \mathrm { D C } ( t + 1 ) } - \pmb { p } _ { \mathrm { D C } t } \le \pmb { x } _ { t } ^ { \mathrm { U P } ( 1 ) } . \times \Delta \pmb { P } _ { \mathrm { D C } } ^ { ( 1 ) } \Bigg \} } & \\ { \pmb { x } _ { t } ^ { \mathrm { D N } ( 1 ) } + \pmb { x } _ { t } ^ { \mathrm { U P } ( 1 ) } \le \pmb { 1 } ^ { \mathrm { T } } } \\ { \displaystyle \sum _ { t \in T - \{ 9 6 \} } ( \pmb { x } _ { t } ^ { \mathrm { D N } ( 1 ) } + \pmb { x } _ { t } ^ { \mathrm { U P } ( 1 ) } ) \le \pmb { N } _ { \mathrm { m a x } } ^ { ( 1 ) } } \end{array} \right. \forall t \in \mathcal { T } - \left\{ 9 6 \right\}
$$

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { \pmb { x } _ { t } ^ { \mathrm { D N } ( 1 ) } + \pmb { x } _ { t + 1 } ^ { \mathrm { U P } ( 1 ) } \leq \pmb { 1 } ^ { \mathrm { T } } } \\ { \pmb { x } _ { t + 1 } ^ { \mathrm { D N } ( 1 ) } + \pmb { x } _ { t } ^ { \mathrm { U P } ( 1 ) } \leq \pmb { 1 } ^ { \mathrm { T } } } \end{array} \right. \qquad \forall t \in T - \left\{ 9 5 , 9 6 \right\} } \end{array}
$$

其中 $. \times$ 表示向量的数组乘法，即对应位置的数相乘；$\mathbf { 1 ^ { \mathrm { T } } }$ 表示长度为NDC的全1列向量，且NDC等于直流联络线的数量；向量 ${ \pmb x } _ { t } ^ { \mathrm { D N } ( 1 ) }$ ， $\pmb { x } _ { t } ^ { \mathrm { U P ( 1 ) } }$ 表示直流功率下调或上调的0-1变量； $\Delta P _ { \mathrm { D C } } ^ { ( 1 ) }$ 为直流功率调节速率限值; $\pmb { p } _ { \mathrm { D C } t }$ 为t时段直流功率向量; ${ N } _ { \mathrm { m a x } } ^ { ( 1 ) }$ 表示直流功率非平稳运行的最大允许时段数，一般控制在1/3倍NT以内。式（6b）避免了直流功率

在相邻时段反向调节。

$$
\left\{ \begin{array} { l l } { \displaystyle { y _ { t + 1 } ^ { \mathrm { O N } } \geq ( x _ { t + 1 } ^ { \mathrm { D N } ( 1 ) } + x _ { t + 1 } ^ { \mathrm { U P } ( 1 ) } ) - ( x _ { t } ^ { \mathrm { D N } ( 1 ) } + x _ { t } ^ { \mathrm { U P } ( 1 ) } ) } } \\ { \displaystyle { y _ { t + 1 } ^ { \mathrm { O F F } } \geq ( x _ { t } ^ { \mathrm { D N } ( 1 ) } + x _ { t } ^ { \mathrm { U P } ( 1 ) } ) - ( x _ { t + 1 } ^ { \mathrm { D N } ( 1 ) } + x _ { t + 1 } ^ { \mathrm { U P } ( 1 ) } ) } } \\ { \displaystyle { y _ { t + 1 } ^ { \mathrm { O N } } + y _ { t + 1 } ^ { \mathrm { O F F } } \leq 1 ^ { \mathrm { T } } } } \\ { \displaystyle { \sum _ { t \in T - \{ 9 5 , 9 6 \} } ( y _ { t + 1 } ^ { \mathrm { O N } } + y _ { t + 1 } ^ { \mathrm { O F F } } ) \leq N _ { \mathrm { m a x } } } } \end{array} \right\} \forall t \in { T - \left\{ 9 5 , 9 6 \right\} }
$$

其中， $\displaystyle y _ { t } ^ { 0 \ N }$ $\pmb { y } _ { t } ^ { 0 \mathrm { F F } }$ 分别表示直流功率在 $t + 1$ 时段从平稳转为上/下爬坡，或者从调节过程变为平稳运行； $N _ { \mathrm { m a x } } / 2$ 表示直流功率曲线的调整次数，也等于功率平稳运行在某一水平的阶段数量。实际系统的 $N _ { \mathrm { m a x } } / 2$ 一般不超过8。

$$
\begin{array} { r } { \left\{ \begin{array} { l } { \displaystyle \mathbf { x } _ { t } ^ { ( 2 ) } . \times \Delta \mathbf { P } _ { \mathrm { D C } } ^ { ( 2 ) } \leq \pmb { p } _ { \mathrm { D C } ( t + 2 ) } - 2 \pmb { p } _ { \mathrm { D C } ( t + 1 ) } + \pmb { p } _ { \mathrm { D C } t } \leq \pmb { x } _ { t } ^ { ( 2 ) } . \times \Delta \pmb { P } _ { \mathrm { D C } } ^ { ( 2 ) } } \\ { \displaystyle \qquad \forall t \in \mathcal { T } - \left\{ 9 5 , 9 6 \right\} } \\ { \displaystyle _ { t \in \mathcal { T } - \left\{ 9 5 , 9 6 \right\} } \pmb { x } _ { t } ^ { ( 2 ) } \leq \pmb { N } _ { \mathrm { m a x } } ^ { ( 2 ) } } \end{array} \right. } \end{array}
$$

其中，向量是 $\pmb { x } _ { t } ^ { ( 2 ) }$ 表征直流功率调整过程爬坡速率是否发生变化的 0-1 变量； $\Delta P _ { \mathrm { D C } } ^ { ( 2 ) }$ 可以取和 $\Delta P _ { \mathrm { D C } } ^ { ( 1 ) }$ 相同的值;${ N _ { \mathrm { m a x } } ^ { ( 2 ) } }$ 一般取稍大于 $N _ { \mathrm { m a x } }$ 的整数。式（6d）的直流功率二阶差分式是相关文献未提及的，它能够保证功率调整过程的平稳性。

直调电厂电量约束

与区域间送受电日电量约束类似，直调电厂的日发电量必须在给定的范围内。对于大容量水电厂，短期运行的水头近似不变，电量约束与水量约束等效。

$$
( 1 - \varepsilon _ { \mathrm { p } } ) E _ { \mathrm { p } } ^ { \mathrm { N } } \leq \sum _ { \varepsilon , \tau } I _ { \pmb { p } _ { \mathrm { P } } } \leq ( 1 + \varepsilon _ { \mathrm { p } } ) E _ { \mathrm { p } } ^ { \mathrm { N } }
$$

其中 $\pmb { { \cal E } } _ { \mathrm { P } } ^ { \mathrm { N } }$ 为电厂日发电量的向量， $\varepsilon _ { \mathrm { P } }$ 为日送受电量最大允许偏差系数， $\pmb { I }$ 为单位矩阵。

省区内直调电厂相关约束

“点对网"送电的直调电厂（直调电厂仅通过联络线与受电省区直接相连）不与省区电网耦合，所以只需要考虑电厂自身日发电量约束和机组运行约束；而省区境内直调电厂与外送通道和省内交流线路同时连接，所以还需要考虑这三者的协调关系以免出现省区内局部交流断面越限的情况。这类约束作用于省区内与直流外送通道配套的直调电厂上，形式如下，

$$
P _ { \mathrm { a c } } ^ { \mathrm { m i n } } \leq C _ { \mathrm { D C - a c } } p _ { \mathrm { D C } t } - C _ { \mathrm { P - a c } } p _ { \mathrm { P } t } \leq P _ { \mathrm { a c } } ^ { \mathrm { m a x } } \quad \forall t \in \mathcal { T }
$$

其中，向量 $\pmb { p } _ { \mathsf { P } t }$ ， $P _ { \mathrm { a c } } ^ { \mathrm { m i n } }$ 和 $P _ { \mathrm { a c } } ^ { \mathrm { m a x } }$ 分别表示t时段与直流配套直调电厂出力值和局部交流断面潮流限值。关联矩阵$c _ { \mathrm { { D C - a c } } }$ ， $c _ { \mathrm { p - a c } }$ 分别包含直流联络线和局部交流断面，直调电厂和局部交流断面的0-1连接信息，与约束（2）中的关联矩阵 $c$ 类似。约束（8）体现了网省的协调配合。

# 2.3模型的可扩展性

2.2节介绍了MADS模型的基本约束条件，实际上参与模型计算的直调电厂，还需要考虑电厂内机组的运行约束，包括火电机组的启停、爬坡、最小开停机时间、最小技术出力和备用等约束，水电厂水轮机振动区和梯级水电的水耦合约束[18]，以及抽水蓄能电站的运行约束等，此类约束条件可以通过引入机组出力和电厂出力的关联矩阵与现有模型耦合。另外，离线N-1计算所得到的诸如电厂最小开机台数、断面限值配合等复杂约束，也可扩展到MADS模型的约束组中。

MADS模型不仅适合目前以计划为主的的调度环境，在电力市场环境下也可作为跨省区日前交易（即区域现货市场）的出清模型，为此仅需要将目标函数置换为区域的供需曲线。采用MADS模型的优势是保持了区域内部电力交易过程的独立性，且计及了中长期交易电量，考虑了区域间联络线的物理约束。

# 3算例

为了验证所提方法的有效性和可行性，采用南方电网实际系统的数据进行测试。模型使用Cplex求解，测试环

境为IntelCorei7CPU $@$ 2.50GHz，8.00G 内存。

# 3.1系统及参数

在南方电网"西电东送"背景下，云南、贵州是送端，广东、广西是受端，海南电网与广东电网的联络线功率一般较小，这里不予考虑。模型将每个“点对网"送电的电厂和省网一样作为区域处理。表1给出了南方电网案例所涉及的主要模型对象，表中直调电厂一列"H"代表水电厂，“T代表火电厂。表1不包括各电厂内的机组对象，也不包含具体模型参数或数据。

MADS 模型是一个 MIQP（Mixed Integer QuadraticProgram）问题，采用Cplex的分段线性化函数将目标函数分为200段，处理后模型转化成易于求解的MILP（MixedIntegerLinearProgram）问题。算例模型考虑了2.3.1的所有约束条件，并考虑直调火电机组的机组组合相关约束，水电厂则仅考虑电厂总出力的爬坡约束和出力的平稳性约束；目标函数只计及省网类型的区域，权系数 $\omega _ { i }$ 根据各省装机容量煤电的比重取值。MADS模型在本文案例中含约束条件53428个，变量30316个，其中二进制变量 20326个，平均求解时间约为 $1 9 0 \mathrm { ~ s ~ }$ 。

Table 1 Details of the objectives in MADS model for the southern China power system case   

<html><body><table><tr><td colspan="2">区域</td><td colspan="2">直调电厂</td><td colspan="4">联络线</td><td>局部断面</td></tr><tr><td colspan="2">省网</td><td>小湾-H</td><td>盘南-T</td><td colspan="4">直流联络线</td><td rowspan="6">楚穗-小湾、金安桥 普侨-糯扎渡 牛从-溪洛渡</td></tr><tr><td rowspan="2">广东省 广西省</td><td rowspan="2">云南省 贵州省</td><td>金安桥-H</td><td>发耳-T</td><td>楚穗</td><td>永富</td><td>兴安</td><td>天广</td></tr><tr><td>糯扎渡-H 溪洛渡-H</td><td>兴义#2-T 天一-H</td><td>普侨 牛从</td><td>金中 鲁西</td><td>高肇</td><td>江城</td></tr><tr><td colspan="2">地区</td><td>观音岩-H</td><td>天二-H</td><td colspan="4">交流通道</td></tr><tr><td rowspan="3">天生桥 龙滩</td><td rowspan="3">兴义 三峡 湖南</td><td>梨园-H</td><td>龙滩-H</td><td colspan="3"></td><td>永富-观音岩</td></tr><tr><td>阿海-H</td><td>桥口-T</td><td rowspan="2">贵州送天生桥 天生桥送广西</td><td rowspan="2"></td><td rowspan="2">龙滩送广西 兴义送贵州</td><td rowspan="2">金中-梨园、阿海</td></tr><tr><td>光照-H 鲤鱼江-T 董箐-H</td></tr></table></body></html>

# 3.2计算结果分析

以2016年7月11日为例，从EMS(EnergyManagementSystem）获取图1所示的模型输入数据进行优化计算，并将MADS所得省区发电计划、联络线功率计划、直调电厂发电计划以及局部交流断面潮流优化结果与基于传统“人工 $. +$ 计算机辅助决策"的实际计划值对比。

# 3.2.1省区发电计划优化效果

由于本文MADS模型的目标函数是最小化省区净发电序列的方差，首先对比各省网发电计划的峰谷差和波动

性，具体如表2所示，

表1南方电网MADS模型对象明细  
表2各省煤电装机占比和优化前后发电峰谷差、标准差对比 Table 2Information of thermal generation capacity in each provincial power system,aswell as comparison of peak-to-valley difference and standard variance before and after optimization   

<html><body><table><tr><td>省区</td><td>广东</td><td>广西</td><td>云南</td><td>贵州</td></tr><tr><td>煤电装机比重</td><td>70.6%</td><td>49.7%</td><td>20.5%</td><td>62.6%</td></tr><tr><td>原始峰谷差</td><td>17963</td><td>915</td><td>13859</td><td>8271</td></tr><tr><td>/MW 优化峰谷差 /MW</td><td>14499</td><td>475</td><td>14540</td><td>7708</td></tr></table></body></html>

<html><body><table><tr><td>原始标准差 /MW</td><td>5044.5</td><td>159.3</td><td>5671.6</td><td>3137.6</td></tr><tr><td>优化标准差 /MW</td><td>4512.1</td><td>154.6</td><td>4762.9</td><td>2703.8</td></tr></table></body></html>

各省优化之后除云南电网峰谷差升高 $4 . 9 1 \%$ 外，各省区的净负荷峰谷差和发电序列标准差均明显下降，特别是燃煤发电比例较高的广东电网峰谷差和标准差分别下降了$1 9 . 2 8 \%$ 和 $10 . 5 6 \%$ ，这对于调节性能差的火电机组而言，能够极大地降低其调峰压力和调节负担，提升运行的经济性。

图3给出了系统内最大的受端系统广东的发电曲线和最大的送端系统云南的外送曲线，以及“点对网"送电地区中的天生桥水电厂和桥口火电厂的出力曲线。（备注：广东优化出力相比原计划存在接近 $2 \%$ 的电量正偏差，云南外送曲线是与云南电网相连的所有联络线功率的总和。)由图可见，优化方案使得云南在中午12点至1点期间和下午18点之后的低谷时段比原始计划压低了外送，缓解了广东火电系统的调峰压力；“点对网"送电电厂则减少夜间送电，以减少该时段广东火电机组启停调峰的需求。对于水电为主的云南电网和天生桥等水电厂，在约束范围内改变外送或出力的曲线形状并不影响其运行成本和售电收益，且参与受端调峰是中长期协议所协定的义务，所以模型的优化结果是切实可行的。对于桥口等火电厂，可根据需要将启停成本和煤耗成本附加到MADS模型的目标函数中，权衡参与受端调峰和火电厂本身运行效益。

![](images/d25678ab39a9dde94301a64e406a43b01eae62bffdda970beba5ab2df4c0c69e.jpg)

![](images/e6e57114f9d49c0109366e1536f0488b1b14cc83a48a42a91025fe57e07d7870.jpg)  
图3系统发输电计划优化结果。(a）广东发电曲线对比；（b) 云南外送曲线对比；（c）“点对网"送电电厂出力对比。 Fig.3 Optimization result of the generation and transmission scheduling. (a) Comparison of the generation profiles of Guangdong system; (b) Comparison of the transmission profiles of Yunnan system; (c) Comparison of independent power plants" production levels.

# 3.2.2联络线与断面优化结果

MADS模型的输出包含每回交、直流联络线的功率计划，直流联络线除了线路容量约束外，还应满足式（6）的离散化约束。图4（a）为普侨直流（云南送广东特高压直流，电压等级 $\pm 8 0 0 \mathrm { k V }$ ，容量 ${ 5 0 0 0 } \mathrm { M W }$ ）功率优化前后的对比，可以直观地看出优化后的直流功率曲线不仅满足物理约束，而且具有良好的阶梯化性质，有利于直流换流站高效可靠运行。此外，优化计划相比原计划更好地参与了峰谷段的调峰；而MADS 模型采用的 $1 5 ~ \mathrm { m i n }$ 调度计划时段，能够更精准地发挥直流灵活调节的特性，比如能够在第46个时段（中午11点30分）开始快速地调减输送功率辅助受端系统调峰。

图4（b）为普侨直流对应的局部交流断面潮流曲线，即直流功率与配套电厂出力的差值。按照原计划，直流与水电厂的功率差值约在400MW\~2700MW之间，这一偏差量需要通过电厂与省区电网间的交流线路来平衡。MADS模型优化结果则显示出直流和配套水电厂计划的良好匹配性，这方面的改善既保证了线路热稳和N-1稳定条件被更好地满足，也减少了直调电厂和云南省区电网之间不必要的潮流交换。

![](images/3b7f884999e91600b7b72c56aef6e8293dba031d9ca223427bea9b35a2d5d975.jpg)

![](images/756a51205f88e1d220bddb7f3469e4d4e435e5ad8de2262e564e62e53f8617fc.jpg)  
图4联络线与局部交流断面优化结果。（a）普侨直流功率计划 对比；（b）普侨-糯扎渡局部交流断面潮流对比。 Fig.4 Optimization results of the tie-line scheduling and local ac interface power flow. (a) Puqiao UHVDC power scheduling; (b) power flow of Puqiao UHVDC-Nuozhadu hydro plant interface.

# 3.2.2MADS模型的可行性和适用性

MADS模型旨在解决我国多区域电力系统日前发输电计划问题，模型基于第1节的三点假设与前提，其中最主要的一点是简化处理了由各省调/中调调管的省区电网。简化的初衷来自两个方面：全局优化调度既存在技术难度，也有悖于当前的调度模式；日前计划的分布式优化既增加通信负担，又无法获得全局最优。MADS模型考虑了各省区的总发输用电平衡、发电能力、网省关口等约束条件，在简化的基础上得到的联络线计划和直调电厂发电计划对于各区域而言是改进的和安全可行的，各省区以联络线计划为边界条件对内部系统进行“自调度"比较符合当前的调度模式。

因为简化了省区系统，无法准确获得其内部的运行成本信息，所以MADS以最小化省区净发电序列方差为目标函数。这虽然只能达到对系统运行成本的改善（次优)，但较好地适应我国"西电东送"背景下送端水电参与受端火电系统调峰的需求。事实上，当我们能够获取更适合反应系统运行效益的目标函数时，只要该目标函数具有凸性，将其替换式（1）之后并不影响模型的可行性和求解效率。

如果将模型中简化的省区视为可控的负荷节点，则MADS实际上是一个考虑电量约束和直流输电功率约束，并将线路潮流同时作为决策变量的水火电安全约束机组组合模型，该模型具有较好的适用性和可扩展性。

# 4结论

基于各区域电源、负荷的互补性优化送受电计划，能够有效促进各区域电网的经济运行。本文所建立的多区域电力系统日前发输电计划优化模型，考虑了上级调度层面的网络安全约束和电厂运行约束，兼顾了各省区的实际调峰需求并且有效协调网省两级调度，能够高效可靠地形成交、直流联络线和直调电厂的日前功率优化计划，改善火电系统调峰压力。

本文不仅以南方电网为例解决了多区域电力系统的日前发输电计划问题，所提模型对于我国其他网省两级多区域系统同样具有参考价值。本文对多区域系统优化调度的网络建模方法，在未来跨省区电力市场的交易出清和调度方案形成中具有一定的应用潜力。

# 参考文献

[1]JiY, Tong L.Multi-Area Interchange Scheduling under Uncertainty[J]. IEEE Transactions on Power Systems,2016,PP(99):1-1.   
[2]Bergh K VD,Boury J,Delarue E. The Flow-Based Market Coupling in Central Western Europe: Concepts and definitions[J]. Electricity Journal, 2016,29(1):24-29.   
[3]何超林，梁寿愚，宋兴光,等.南方电网节能发电调度计划编制思路、 实践及效果[J].南方电网技术,2012,6(2):58-61. HE Chaolin,LIANG Shouyu,SONG Xingguang,et al. The Thinking, Practice and Effect of Energy-Conservation Power Generation Scheduling in China Southern Power Grid[J].SOUTHERN POWER SYSTEM TECHNOLOGY,2012,6(2):58-61.   
[4]Zheng X,Chen Y, Chen H,et al. Loss-Minimizing Generation Unit and Tie-Line Scheduling for Asynchronous Interconnection[J]. IEEE Journal of Emerging & Selected Topics in Power Electronics,2017, PP(99):1-1.   
[5]Chen Y, Casto A,Wang F,et al. Improving Large Scale Day-Ahead Security Constrained Unit Commitment Performance[J]. IEEE Transactions on Power Systems,2016,31(6):4732-4743.   
[6]张显，周鑫,耿建,等.基于网络流的发输电计划协调优化方法[J]. 电力系统自动化,2013,37(19):55-60. ZHANG Xian, ZHOU Xin,GENG Jian,et al. A Coordination and Optimization Method for Generation and Transmission Scheduling of Power System Based on Network Flow[J].Automation of Electric Power Systems,2013,37(19):55-60.   
[7]申建建，程春田,李卫东,等.多电网调峰的水火核电力系统网间出 力分配方法[J]．中国电机工程学报,2014,34(7):1041-1051. SHEN Jianjian,CHENG Chuntian,LI Weidong,et al. Solutions to Power Generation Allocation among Multiple Power Gridsin PeakOperation of Hydro,Thermal and Nuclear Plants[J]. Proceedings of the CSEE,2014,34(7):1041-1051.   
[8]王斌,夏叶,夏清,等.直流跨区互联电网发输电计划模型与方法[J]. 电力系统自动化,2016(3):8-13. WANG Bin, XIA Ye,XIA Qing, et al． Model and methodsof generation and transmission scheduling of inter-regional power grid via HVDC tie-line[J]. Automation of Electric Power Systems,2016, 40(3): 8-13.   
[9]崔杨，赵玉，邱丽君,等.改善受端电网调峰裕度的特高压直流外送 风火协调调度[J]．电力系统自动化,2018,42(15):126-132. CUI Yang, ZHAO Yu, QIU Lijun, et al. Coordinated Scheduling Method of Wind-thermal Power Transmittd by UHVDC System for Improving Peak-shaving Margin of Receiving-end Power Grid[J].Automation of Electric Power Systems,2018,42(15):126-132.   
[10]朱泽磊，程鑫，杨桂钟,等.基于母线负荷预测改进的省地协同发电 计划优化方法[J]．中国电机工程学报,2018,37(03):665-676. ZHU Zelei，CHENG Xin，YANG Guizhong，et al.Collaborative Scheduling Optimization Method for Provincial Grid and Regional Grid Based on Refined Busload Forecast[J].Proceedings of the CSEE,2018, 37(03):665-676.   
[11]Elmaghraby W, Oren S S.The Efficiency of Multi-Unit Electricity Auctions[J].Energy Journal,1999,20(4):89-116.   
[12]梁志飞，陈玮，张志翔,等．南方区域电力现货市场建设模式及路径 探讨[J].电力系统自动化,2017,41(24):16-21. LIANG Zhifei, CHEN Wei, ZHANG Zhixiang,et al.Discussion on Pattern and Path of Electricity Spot Market Design in Southern Region of China[J].Automation of Electric Power System,2017,41(24):16-21.   
[13]申建建，程春田，曹瑞,等.大规模水电消纳和调峰调度关键问题及 研究进展[J]．电力系统自动化,2018,42(11):174-183. SHEN Jianjian,CHENG Chuntian, CAO Rui,et al.Key Issues and Development in Large-scale Hydropower Absorption and Peak Regulation[J].Automation ofElectric Power System,2018,42(11):174- 183.   
[14]陈皓勇，李立涅．电能商品品质衡量及定价机制[J].全球能源互联 网,2018,1(1):79-86. CHEN Haoyong,LI Licheng.Evaluation of Electricity Commodity Quality and the Related Pricing Mechanisms[J].Journal of Global Energy Interconnection,2018,1(1):79-86.   
[15]Bertsimas D,Litvinov E, Sun XA,et al.Adaptive Robust Optimization for the Security Constrained Unit Commitment Problem[J].IEEE Transactions on Power Systems,2013,28(1):52-63.   
[16]钟海旺，夏清，丁茂生,等.以直流联络线运行方式优化提升新能源 消纳能力的新模式[J]．电力系统自动化,2015,39(3):36-42. ZHONGHaiwang，XIAQing，DING Maosheng，etal．Anew mode ofHVDCtie-lineoperationoptimizationformaximizing renewable energy accommodation[J]．Automation of Electric Power Systems，2015，39(3):36-42.   
[17]周明，翟俊义，任建文，李庚银.含风电并网的直流互联电网分散 协调调度方法[J]．电网技术,2017,41(1):71-79. ZHOU Ming，ZHAI Junyi,REN Jianwen，LIGengyin.ADecentralized Coordinated Dispatch Approach for Interconnected Power Grid with Wind Power via HVDC Tie-line[J].Power System Technology, 017, 41(1):71-79.   
[18]Cheng C,Shen J,Wu X.Short-Term Scheduling for Large-Scale Cascaded Hydropower Systems with Multivibration Zones of High Head[J].Journal of Water Resources Planning & Management,2011, 138(3):257-267.

陈亦平 (1978-)，男，博士，教授级高工，主要研究方向：电网调度运行，E-mail:chenyiping@csg.cn;郑晓东(1993-)，男，博士研究生，目前研究方向：电力系统优化与控制，E-mail: z.xiaodong@mail.scut.edu.cn;陈皓勇(1975-)，男，教授，博士生导师，研究方向：电力系统优化与控制，电力市场，智能电网，E-mail：eehychen@scut.edu.cn;

# The Approach of Multi-area Power System Day-ahead Generation and Transmission Scheduling: A Case Study of Southern China Power System

CHEN Yiping', ZHENG Xiaodong=, CHEN Haoyong², ZHANG Yong', CHEN Jingpeng', XUAN Peizheng' (1.Powerspatdttridaaoa;trutha UniversitofTolagouagdogina;3triceReachitute,natoerGidangoado

510623 China)

Abstract:Thechallnges ofmulti-area power systemoptimal dispatch existon howtobe inline with certaindispatching mode as well as on the modeling/solution.Inthisarticle,amulti-area system dy-aheadscheduling,withaprovincial systems-reducing methodadagenerationvariances-minimizingobjective,isproposed,asedonthehierarchical dispatchingorganzationandthe long-termbilateral energycontract mode inChina.Non-iteratively,thesub-optimalschedulingofac/dctie-linesand independent generationunitscanbederivedfromsolving the model,whichalsoconsiderssomepracticalconstraints likediscreteconstraintsof dc powerprofilesandpowerflowlimitsoflocalac interface,etc.Casestudyiscarredoutbasedontherealisticdata fromthe multiareahybridac/dsouthe Chinapowersystem,toverifytheeffectivenessandfeasibityoftheproposedmodel.Itisdemostrated thatwith this metod,te upper-level dispatchinginstitutioncangenerateanoptimizedandreliable transmisson powerplan with limitedinformation,whichdecreases thepeak-vallydierenceandstandardvarianceofgenerationsries,relievesthebrdenof peakreglationofitssub-systems,andhenceimprovesteeconomiceficiency.Theaproachsuitsthedispatchingmodeofpower systems in China well,handles various operation scenarios,and thus has been implemented in the system operator.

Key words: multi-area; generation and transmission; day-ahead scheduling; peak regulation; optimal dispatch