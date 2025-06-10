# 基于SDN与NDN的卫星网络多约束路由算法

刘治国1,2，姚巧雨1,²，潘成胜

(1．大连大学 信息工程学院，辽宁大连116600;2.通信与网络重点实验室，辽宁 大连116600;3．南京信息工程大学电子与信息工程学院，南京 211800)

摘要：针对NDN卫星网络内容传输时延高、丢包率高且请求命中率低的问题，提出了一种基于 SDN与NDN的卫星网络多约束路由算法并命名为 SNMcRA(Satelite Networks Multi-constraint Routing Algorithm)。基于 SDN 的集中控制与全局视图，通过建立多约束路由模型，将链路多约束信息与蚁群算法相结合以求解满足时延、带宽、丢包率多约束的代价最小路径，由节点在包转发的过程中动态完成转发表FIB(ForwardingInformation Base)和待定请求表PIT(PendingInterestTable)的构建。实验结果表明,该算法与DSP算法相比时延降低了 $3 5 \%$ ，带宽利用率提升了 $2 9 \%$ ，丢包率降低了 $1 7 \%$ ，并且在请求命中率方面也具有显著优势。

关键词：SDN；NDN；卫星网络；路由算法 中图分类号：TP doi:10.19734/j.issn.1001-3695.2021.12.0692

Satellite network multi-constraint routing algorithm based on SDN and NDN

Liu Zhiguo1, 2t, Yao Qiaoyu1,2, Pan Chengsheng3 (1.School of Information Engineering，Dalian University，Dalian Liaoning l16600，China;2.Key Laboratoryof Communication& Network,Dalian Liaoning 166o0,China;3.SchoolofElectronics & Information Engineeing,Nanjing University of Information Science & Technology,Nanjing 211800, China)

Abstract: Aimingattheproblems ofhigh content transmissondelay,high packetlossrate and lowrequest hitrate in NDN satellte network,a multi-constraintrouting algorithmforsatelite network basedon SDNandNDN was proposedand named SNMcRA(Satelite Networks Multi-constraint Routing Algorithm).Based on SDN's centralized control and global view, by establishing a multi-constraint routing model,the multi-constraint information of linkswas combined with antcolony algorithm tosolvetheleast-costpath thatmets themulti-constraintsofdelay,bandwidthandpacketlossrate,andthenodes dynamicallycomplete theconstructionofforwarding table FIB(Forwarding Information Base)and pending request table PIT(Pending Interest Table)in the process of packet forwarding.Experimental results showed that compared with DSP algorithm,this algorithm reduces the time delay by $3 5 \%$ ,improves the bandwidth utilization by $2 9 \%$ ,reduces the packet loss rate by $1 7 \%$ ,and has significant advantages in the request hit rate.

Key words:SDN; NDN; satellite network; routing algorithm

# 0 引言

随着空间技术的飞速发展，卫星网络已成为全球通信的重要组成部分[1]。路由协议作为卫星网络通信协议的核心，在提高卫星网络数据传输效率和可靠性方面意义重大[2]。同时，用户对视频、语音等多媒体内容的需求飞速增长[3,4]，而基于IP的卫星网络在内容传输上存在固有缺陷，即"身份-位置"的绑定使网内重复传输大量相同内容，极大浪费星上带宽资源。因此，在卫星网络环境中，需要一种新型的网络架构来克服上述问题。

命名数据网络(NDN，named data networking)作为以数据为中心的未来网络架构，将内容与位置解耦，并支持网络内缓存，缓解了传统TCP/IP网络传输效率低的问题[5\~7]。NDN采用接收者驱动的通信模式，包含兴趣包(interestpacket)和数据包(DataPacket)两种包结构，并通过内容缓存表(CS，Content Store)、待定请求表(PIT，pending interest table)和转发信息表(FIB，forwarding information base)进行包的转发[8\~l0]。

NDN 现有的转发方法在拓扑结构稳定的场景下具有一定优势。WangL等人提出基于OSPF的命名数据网络路由协议，通过洪泛来分发路由消息，实现内容分发[1I]。ZhangL通过周期性广播链路状态信息创建网络拓扑并进行包的分发，利用逐跳转发代替基于OSPF的周期性前缀公告泛洪[12]。但在卫星网络拓扑高动态变化的环境下，已有的静态映射和泛洪路由或基于链路状态广播的路由机制都难以适用，存在以下问题：1)兴趣包的频繁广播或多播将导致多个数据源重复回应请求，造成数据的冗余传输。2)卫星链路频繁中断导致数据包可能无法按照兴趣包的传输路径反向回传。

针对上述问题，HasanMAIslam等人针对NDN在频繁中断环境下数据包无法及时得到回复而重发的问题，将NDN与DTN相结合以解决NDN无法适应频繁中断的问题[13]。刘迪等人根据可预知的卫星链路切换状态，以时变图的方式进行建模，动态计算时间相关的最快路径实现包的传输，但其只考虑单个目标优化，而且联络拓扑时变性大使得路由效率较低[14]。ZhouY等人根据卫星间连接计划采用连接图路由计算方法制定数据包转发路径，并采用最优及次优两条路径同时转发，但其动态性差且对卫星节点要求较高[15]。

针对上述算法的不足，本文提出了一种基于SDN 与NDN的卫星网络多约束路由算法并命名为SNMcRA(satellitenetworksmulti-constraint routingalgorithm)，相较于传统的洪泛路由和基于连接图的单一目标优化的路由方法，此方法基于SDN集中控制并利用改进的蚁群算法获取满足时延、带宽和丢包率多约束的代价最小路径，实现包的高效传输。

# 1 基于SDN的卫星网络系统架构

SDN(SoftwareDefinedNetwork)架构将网络的控制层与转发层分离，有效改善了网络管理、控制以及数据处理[16,17]。本文设计了基于SDN的多层卫星网络架构MsnSDN(multi-layer satellite networkbased onSDN)，如图1所示。三颗GEO卫星作为局部控制器，负责获取LEO卫星的实时状态信息，并对网络进行路由计算与管理；转发层由LEO卫星节点组成，负责根据GEO卫星下发的流表进行数据传输；地面控制中心作为全局控制器负责集中控制和管理整个卫星网络。

根据卫星网络拓扑的周期性和可预测性，本文采用虚拟节点策略[18]“屏蔽”卫星的高动态性。根据地面站在地球表面划分的区域位置，某区域上方的虚拟卫星节点保持不变，实际的卫星持续运动并根据区域位置不断改变其逻辑地址，从而构成一个覆盖全球的虚拟固定拓扑网络。

# 2 基于SNMcRA的转发机制

NDN 中兴趣包和数据包通过FIB 表和PIT表进行兴趣查找和内容返回，因此，要实现基于NDN的卫星网络高效路由首先需要进行FIB表和PIT表的构建。本文通过建立多约束路由模型，根据GEO卫星控制器获取全局网络状态信息，执行SNMcRA算法求得满足时延、带宽和丢包率多约束的代价最小路径，并在包转发的过程中实现FIB和PIT的构建。

# 2.1基于SNMcRA的FIB 构建流程

在卫星网络场景下，兴趣包的广播式转发将导致多个数据源重复回应请求，造成数据冗余传输，浪费星上带宽资源。因此，本文通过将兴趣包转发到GEO卫星控制器获取内容源卫星节点，并执行多约束路由计算得到兴趣包的最优转发路径，由此更新/修改FIB表，如图2所示。

![](images/fdc893b348b9fddd654480cc4df6bb3ff829b84a7fd7b702b55318eb5ffe6775.jpg)  
图1基于SDN的多层卫星网络架构图  
Fig.1SDN-based multilayer satellite network architecture diagram   
图2基于SNMcRA的FIB 构建流程图 Fig.2Flow chart ofFIB construction based on snmcra   
图3基于SNMcRA的PIT构建流程图  
Fig.3Flow chart of PIT construction based on snmcra

当卫星节点收到兴趣包后，首先查找CS，若在CS中命中内容，则包含内容的数据包按原路返回，用户请求得到满足；否则，查找PIT，若有此内容的PIT条目，则添加进入接口信息到相应条目；否则，继续查找FIB，若找到此内容转发接口信息，则按照接口信息进行转发；否则，将兴趣包转发到GEO卫星控制器，控制器根据解析出的内容名获取内容源卫星节点，并根据当前全局网络状态信息执行多约束路由计算兴趣包的最优转发路径，下发流表给相应的LEO卫星完成转发；否则，将兴趣包回溯或者丢弃。

兴趣包 CS内容 × PIT × FIB缓存表 待定兴趣表 转发表 转发兴趣包  
返回数据包 √ < ×  
↑ 添加接口信息更新/修改 T控制器执行 转发到转发兴趣包 SNMcRA路由计算 GEO控制器X回溯或丢弃：命中 ×：未命中

# 2.2基于 SNMcRA 的 PIT 构建流程

在网络拓扑稳定的场景下，数据包按照兴趣包传输路径反向回传。但卫星网络拓扑动态变化，数据包在返回之前兴趣包转发路径的反向路径可能已经不存在。因此，需要动态构建PIT表。由于NDN本地支持内容级别的重路由，因此当PIT表需要更新时，仅需通过GEO卫星控制器执行SNMcRA路由计算即可，如图3所示。

转发数据包 √ PIT待定 × CS内容兴趣表 缓存表 数据包CS表 ×缓存 控制器执行 ×SNMcRA路由计算 NACK√：命中 ×：未命中

当卫星节点收到数据包后，首先查看CS中是否有此数据包，若存在，则丢弃该数据包；否则，查找PIT。若PIT中记录的兴趣包传输链路存在，则按照PIT完成数据包的转发与缓存；否则，向GEO卫星控制器请求执行多约束路由计算数据包最优转发路径；若计算成功，则LEO卫星节点按照流表转发数据包，并按照相应的缓存策略进行缓存；否则，节点返回NACK。

# 3 基于SNMcRA的路由计算

为保证兴趣包和数据包的高效可靠传输，本节提出一种多约束路由计算方法。在建立卫星网络多约束模型的基础上，结合链路多约束信息对基本蚁群算法的状态转移规则以及信息素更新方式进行改进，进而基于改进的蚁群算法计算出满足时延、带宽和丢包率多约束的代价最小路径。

# 3.1多约束模型

将LEO卫星系统建模为图 $G = \left( V , E \right)$ ， $\boldsymbol { V }$ 为卫星节点集合，$E$ 为星间链路集合。 $( k , l )$ 表示节点 $k$ 和节点 $l$ 之间的链路，$p ( s , d )$ 表示从源节点 $s$ 到目的节点 $\textit { d }$ 的一条路径， $k , l , s , d \in V$ 。本文选择最重要的多个路径约束表示如下：

1)通信时延

通信时延 $d e a l y ( p ( s , d ) )$ 为路径传输时延与节点排队时延之和[19]。

$$
d e a l y \big ( p ( s , d ) \big ) = \sum _ { \forall ( k , l ) \in p ( s , d ) } d e a l y _ { t r a } \big ( k , l \big ) + \sum _ { \forall v \in p ( s , d ) } d e a l y _ { q u e } \big ( \nu \big )
$$

其中： $d e a l y _ { t r a } ( k , l )$ 为路径的传输时延， $d e a l y _ { q u e } \left( \nu \right)$ 为路径中节点排队时延。

2)剩余可用带宽

剩余可用带宽 $b a n ( k , l )$ 为链路总带宽与已用带宽之差，属于凹性参数。

$$
b a n ( k , l ) = B ( k , l ) - B _ { u s e d } ( k , l )
$$

其中： $B ( k , l )$ 表示链路总带宽， $B _ { u s e d } \left( k , l \right)$ 表示链路已用带宽。

3)丢包率

丢包率 $l o s s ( p ( s , d ) )$ 为传输数据包中丢失的数量占总数量的比值，属于可乘性参数[20]。

$$
l o s s \big ( p ( s , d ) \big ) = 1 - \prod _ { \forall ( k , l ) \in p ( s , d ) } \left( 1 - l o s s \big ( k , l \big ) \right)
$$

其中： $l o s s ( k , l )$ 是单位时间内路径 $p ( s , d )$ 中链路 $( k , l )$ 的丢包率。

本文定义最优路径的评判指标为路径代价 $\cos t ( k , l )$ ，为通信时延、可用带宽、丢包率的加权之和，计算公式如下：

$$
\cos t ( k , l ) = \omega _ { \mathrm { l } } \frac { d e l a y ( k , l ) } { D _ { \mathrm { m i n } } } + \omega _ { \mathrm { 2 } } \frac { b a n _ { \mathrm { m a x } } } { b a n ( k , l ) } + \omega _ { \mathrm { 3 } } \frac { l o s s ( k , l ) } { L _ { \mathrm { m i n } } }
$$

其中： $d e l a y ( k , l )$ 为链路(k,)的通信时延， $D _ { \mathrm { m i n } }$ 为当前卫星网络中的最小通信时延； $b a n _ { \operatorname* { m a x } }$ 为当前卫星网络链路中可用带宽的最大值，$b a n ( k , l )$ 为链路 $( k , l )$ 的剩余可用带宽； $l o s s ( k , l )$ 为链路(k,l)的丢包率， $L _ { \mathrm { m i n } }$ 为当前卫星网络中的最小丢包率； $\omega _ { i } ( i = 1 , 2 , 3 )$ 分别表示时延、可用带宽、丢包率的相对权重，且 $\sum \omega _ { i } = 1$ 0

本文算法的目标是为每个内容请求找到一条路径代价最小且满足时延、带宽、丢包率要求的路径，因此建立多约束路由模型如下：

$$
\operatorname* { m i n } \cos t \big ( p ( s , d ) \big ) = \operatorname* { m i n } \left\{ \sum _ { \forall ( k , l ) \in p ( s , d ) } \cos t ( k , l ) \right\}
$$

$$
s . t . \left\{ \begin{array} { l l } { d e a l y \left( p \left( s , d \right) \right) \leq D _ { \operatorname* { m a x } } } \\ { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \mathrm { m i n } \quad } \\ { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ { l o s s \left( p \left( s , d \right) \right) \leq L _ { \operatorname* { m a x } } } \end{array} \right.
$$

其中： $D _ { \mathrm { m a x } }$ 、 $B _ { \mathrm { m i n } }$ 、 $L _ { \mathrm { m a x } }$ 分别表示传输业务对通信时延、可用带宽、丢包率的约束阈值。

# 3.2基于改进的蚁群算法的模型求解

蚁群算法模拟蚂蚁觅食时在其经过的路径上释放信息素，路径越短，蚂蚁在此路径上来回次数越多，信息素浓度越大，选择该路径的蚂蚁也越多，最后找到觅食最短路径[2I]。但基本的蚁群算法以寻找最短路径为目标，并且容易陷入局部最优解。本文将多约束条件与蚁群算法相结合，在寻路过程中充分考虑链路多约束信息以高效求解满足时延、带宽、丢包率多约束的最优路径。

# 3.2.1基于先验知识与概率驱动的状态转移规则

基本的蚂蚁状态转移公式为

$$
P _ { ( k , l ) } ^ { q } \left( t \right) = \left\{ \begin{array} { l r } { \displaystyle \frac { \left[ \tau _ { \left( k , l \right) } \left( t \right) \right] ^ { \alpha } \left[ \eta _ { \left( k , l \right) } \left( t \right) \right] ^ { \beta } } { \displaystyle \sum _ { s ^ { \prime } \in p r e c _ { q } } \left[ \tau _ { \left( k , s ^ { \prime } \right) } \left( t \right) \right] ^ { \alpha } \left[ \eta _ { \left( k , s ^ { \prime } \right) } \left( t \right) \right] ^ { \beta } } , s ^ { \prime } \in p r e c _ { q } } \\ { 0 , \quad } & { s ^ { \prime } \notin p r e c _ { q } } \end{array} \right.
$$

其中： $P _ { ( k , l ) } ^ { q } \left( t \right)$ 为蚂蚁 $q$ 从卫星 $k$ 转移到卫星 $l$ 的概率； $p r e c _ { q }$ 为蚂蚁 $q$ 等待访问节点集合； $\tau _ { ( k , l ) } \left( t \right)$ 为 $t$ 时刻链路 $( k , l )$ 上的信息素浓度； $\alpha$ 为信息素启发因子，反映转移规则受到信息素浓度的影响程度； $\eta _ { ( k , l ) } ( t )$ 为 $t$ 时刻节点 $k$ 到节点 $l$ 链路上的启发度，一般 $\eta _ { ( k , l ) } \left( t \right) = 1 / d _ { ( k , l ) } \left( t \right)$ ， $d _ { ( k , l ) } \left( t \right)$ 表示 $t$ 时刻节点 $k$ 与节点l之间的距离；本文定义 $\eta _ { ( k , l ) } \left( t \right) = 1 / c o s t _ { ( k , l ) } \left( t \right)$ ，即路径代价越小对蚂蚁的启发作用越大； $\beta$ 为启发函数因子，反映启发信息对转移规则的影响程度。

基本的蚂蚁状态转移规则仅按照概率来选择下一跳节点，算法随机性高，收敛速度慢。因此，本文采用先验知识选择与概率驱动方式来确定蚂蚁的下一跳移动方向，比基本蚁群算法更好的利用蚂蚁正反馈机制。改进后的蚂蚁状态转移规则如式(8):

$$
l = \left\{ \begin{array} { c c } { \underset { l \in p r e c _ { q } } { \arg \operatorname* { m a x } } \left\{ \left[ \tau _ { \left( k , l \right) } \left( t \right) \right] ^ { \alpha } \left[ \eta _ { \left( k , l \right) } \left( t \right) \right] ^ { \beta } \right\} , } & { p \leq p _ { 0 } } \\ { P _ { \left( k , l \right) } ^ { q } \left( t \right) , } & { p > p _ { 0 } } \end{array} \right.
$$

$$
p _ { \mathrm { 0 } } = \frac { N _ { \mathrm { m a x } } - N _ { c } } { N _ { \mathrm { m a x } } }
$$

其中: $p$ 为[0.1]内均匀分布的随机数； $p _ { \mathrm { 0 } }$ 为状态转移因子，如式(9)， $N _ { \mathrm { m a x } }$ 为最大迭代次数， $ { N _ { c } }$ 为当前迭代次数。当 $p \leq p _ { 0 }$ 时，利用先验知识采用非随机的搜索方式，即按照信息素与启发式函数乘积最大的节点进行状态转移；当 $p > p _ { 0 }$ 时，按照式(7)计算满足约束条件的所有节点的随机转移概率 $P _ { ( k , l ) } ^ { q } \left( t \right)$ ，按照概率大的节点进行状态转移。

在算法迭代初期， $p _ { \mathrm { 0 } }$ 取值较大，使得节点以大概率选择确定转移，加快了局部最优路径搜索；迭代后期， $p _ { \mathrm { 0 } }$ 取值较小，以增大随机转移概率，防止陷入局部最优。因此，改进的状态转移规则通过动态调整状态转移因子，使蚂蚁按照不同方式选择下一跳节点，丰富了下一跳节点的可选择性，并防止算法陷入局部最优。

3.2.2基于多约束链路代价的信息素更新规则基本的信息素更新方式为

$$
\tau _ { \left( k , l \right) } \left( t + 1 \right) = \left( 1 - \rho \right) \tau _ { \left( k , l \right) } \left( t \right) + \Delta \tau _ { \left( k , l \right) } \left( t \right)
$$

$$
\begin{array} { r } { \Delta \tau _ { ( k , l ) } \left( t \right) = \sum _ { q = 1 } ^ { m } \Delta \tau _ { ( k , l ) } ^ { q } \left( t \right) } \end{array}
$$

其中: $\rho$ 为信息素挥发因子，且 $0 < \rho < 1$ ； $\Delta \tau _ { ( k , l ) } ( t )$ 为链路(k,l)上信息素量； $\Delta \tau _ { ( k , l ) } ^ { q } ( t )$ 为蚂蚁 $\boldsymbol { q }$ 在链路 $( k , l )$ 上留下的信息素增量，如式(12):

$$
\Delta \tau _ { ( k , l ) } ^ { q } \left( t \right) = \left\{ \begin{array} { c c } { { Q / L _ { q } } , } & { { \overleftrightarrow { \mathcal { H } } q \overleftrightarrow { \mathcal { H } } \underline { { { \mathbb { H } } } } \underline { { { \mathbb { H } } } } \underline { { { \mathbb { H } } } } \chi \ll \chi \chi \equiv \underline { { { \Pi } } } \underline { { { \mathbb { H } } } } \underline { { { \zeta } } } \underline { { { \mathbb { X } } } } \left( k , l \right) } } \\ { { 0 , } } & { { \overleftrightarrow { \mathcal { H } } \cdot \overleftrightarrow { \mathcal { C } } } } \end{array} \right.
$$

其中： $\varrho$ 为常数，表示信息素强度； $L _ { q }$ 为蚂蚁 $q$ 在本次循环中所走的路径长度。

基本的信息素更新方式仅考虑单一的路径长度因素，不适用于求解多约束路由路径，因此，本文将多约束条件与信息素更新方式相结合，使蚁群实时感知路径的时延、带宽和丢包率等参数，指导蚁群及时调整路径搜索策略。因此，改进的信息素更新规则如式(13)所示。

$$
\tau _ { ( k , l ) } \left( t + 1 \right) = \left( 1 - \rho \right) \tau _ { ( k , l ) } \left( t \right) + \Delta \tau _ { ( k , l ) } \left( t \right)
$$

$$
\begin{array}{c} \Delta \tau _ { ( k , l ) } ( t ) =  { \rho \cdot { [ { 1 / c o s t _ { ( k , l ) } ( t ) } ] } , ( k , l ) \in p ( { s , d } ) }   \\ { 0 , \qquad ( k , l ) \notin p ( { s , d } ) } \end{array} 
$$

其中: $c o s t _ { ( k , l ) } \left( t \right)$ 为当代最优解蚂蚁的路径代价值，如式(4)。当所选路径代价越小时，该路径上的信息素浓度增加越多，从而启发更多的蚂蚁选择该条路径。同时，为避免信息素浓度过高或过低导致算法过早陷入局部最优或停滞搜索，本文将各条寻优路径上的信息素量限制在 $[ \tau _ { \mathrm { m i n } } , \tau _ { \mathrm { m a x } } ]$ 范围内，当超出这个范围时，信息素量被强制限定为 $\tau _ { \operatorname* { m i n } }$ 或 $\tau _ { \operatorname* { m a x } }$ ，如式(15)所示。

$$
\begin{array}{c} \begin{array} { r } { \tau _ { \left( k , l \right) } \left( t + 1 \right) = \left\{ \left( 1 - \rho \right) \tau _ { \left( k , l \right) } \left( t \right) + \Delta \tau _ { \left( k , l \right) } \left( t \right) , \tau _ { \left. { \left( k , l \right) } \right.} < \tau _ { \left( k , l \right) } \left( t \right) < \tau _ { \operatorname* { m a x } }  \right.} \\ { \tau _ { \operatorname* { m a x } } , \tau _ { \left( k , l \right) } \left( t \right) \geq \tau _ { \operatorname* { m a x } } } \end{array}   \end{array}
$$

综上，利用改进的蚁群算法求解卫星网络多约束的最优路径的步骤描述如下：

Step1：初始化网络中节点和链路的多约束条件参数以及蚁群算法中的基本参数。

Step2：根据多约束条件删除网络中不满足条件的链路，得到一个新的网络拓扑，然后基于新的网络拓扑 $G ( V , E ) ^ { \prime }$ 开始搜索。

Step3：将源节点 $s$ 设置为蚂蚁的当前节点，并加入禁忌表中，设置迭代次数 $N _ { c } = N _ { c } + 1$ 0

Step4：蚂蚁根据状态转移规则(式(8))和多约束条件选择下一跳节点，并将选择的节点加入禁忌表中。

Step5：蚂蚁判断当前节点是否为目的节点，若是，则宣布寻路成功，跳到 Step7；否则，执行 Step6。

Step6：蚂蚁判断当前节点的 $p r e c _ { q }$ 集合是否为空，若为空，则宣布寻路失败；否则，执行 Step4。

Step7：目的节点 $d$ 根据路径代价 $c o s t ( p ( s , d ) )$ 选择一条最

优路径，将蚂蚁按原路返回，并按照式(13)更新信息素。

Step8：若 $N _ { c } = N _ { \operatorname* { m a x } }$ ，则算法循环结束，输出最优解；否则，返回 Step3。

# 4仿真实验与结果分析

# 4.1仿真场景与参数设置

仿真过程中卫星网络通过3颗GEO卫星作为控制器来实时控制整个网络，LEO卫星采用铱星星座模拟转发层。仿真场景中，由GEO卫星控制器收集LEO网络中的节点链路信息，具体参数如表1。

表1卫星网络轨道参数  
Tab.1Satellite network orbit parameters   

<html><body><table><tr><td>卫星网络轨道参数</td><td>GEO层</td><td>LEO层</td></tr><tr><td>卫星数目</td><td>3</td><td>66</td></tr><tr><td>轨道数</td><td>1</td><td>6</td></tr><tr><td>每个轨道卫星数</td><td>3</td><td>11</td></tr><tr><td>轨道高度/km</td><td>35786</td><td>780</td></tr><tr><td>轨道倾角/(°)</td><td>0</td><td>86</td></tr><tr><td>最小仰角/(°)</td><td>8</td><td>8</td></tr></table></body></html>

在仿真中，考虑传输业务的通信时延、剩余带宽和丢包率等约束条件，本文设置时延、带宽、丢包率的阈值分别为$D _ { \mathrm { m a x } } = 1 0 0 m s$ ， $B _ { \mathrm { m i n } } = 1 0 \sim 3 0 M b p s$ ， $L _ { \mathrm { m a x } } = 3 \%$ 。根据本征向量法计算出代价函数中时延、可用带宽、丢包率的权值为$\boldsymbol { \omega } _ { i } = \left( 0 . 5 5 , 0 . 2 5 , 0 . 2 \right) ^ { T }$ ，并据此计算得一致性比率 $C R = 0 . 0 4 < 0 . 1$ ，即该权向量估计可被接受。

蚁群算法中参数的取值很大程度上影响算法性能。针对蚂蚁数量参数，当蚂蚁数量过大(接近问题规模)时，虽然提高了搜索的稳定性和全局性，但算法的收敛速度减慢。一般选择最优蚂蚁数为节点数量的三分之二，故本文选定蚂蚁数 $m = 4 5$ 。参考文献[22]，考虑到信息素浓度初始值过低使得算法循环次数增大因此设置 $\tau _ { 0 } = 2 0$ ；为避免信息素浓度过低而导致算法提早停止搜索因此设置$\tau _ { \mathrm { m i n } } = 1 0$ ；当信息素值在100以内时，问题规模对于信息素值的选择影响较小，因此本文选定 $\tau _ { \mathrm { m a x } } = 1 0 0$ ；为保证算法运行性能最优因此设置最大迭代次数 $N _ { \mathrm { m a x } } = 5 0$ 。 $\alpha$ 、 $\beta$ 和 $\rho$ （204号的取值由实验确定，分别测量当固定其余参数时， $\alpha$ 、 $\beta$ 和 $\rho$ 对算法收敛到最优解的迭代次数的影响，实验结果如图4、图5所示。

![](images/a3b6b9c0c21f40f7f2789645d0de7c52facae5c3449f922d0d8cdc35e011ca60.jpg)  
图4 $\alpha$ 和 $\beta$ 对迭代次数的影响  
Fig.4The influence of $\alpha$ and $\beta$ on the number of iterations

由上述实验可知，随着 $\alpha$ 取值的增大，算法迭代次数逐渐增大；因此，本文选取 $\alpha = 1$ ，此时，当 $\beta = 2$ 时算法收敛到最优解的迭代次数最少，因此，选取 $\alpha = 1$ ， $\beta = 2$ 。在确定 $\alpha$ 和 $\beta$ 的值后，对 $\rho$ 的取值实验结果如图5所示。

![](images/1295def5f0fe5f08c0cc4584e7ad86cf5ddbebaf11b0bc0dbc3fc3fb23f6d00b.jpg)  
图5参数 $\rho$ 对迭代次数的影响

# 4.2 仿真结果分析

将本文提出的SNMcRA算法与基本蚁群优化算法(AntColony Optimization，ACO)与进行算法收敛性能比较。

图6为算法收敛性比较。随着蚂蚁数的增加，本文算法达到最优解时的迭代次数均少于ACO算法。当蚂蚁数为45时，本文算法迭代6次左右就收敛到最优解。这是由于本文算法改进了基本蚁群优化算法，根据先验知识与概率选择相结合的方式选择下一跳节点，加快了局部最优解的搜索；同时，结合链路多约束信息优化了信息素更新方式，并设置了信息素浓度的上下界，避免算法陷入局部最优或停止搜索。因此，算法的收敛速度较快。

![](images/8d0c072974327d11f04c27c7be6d73559966fb1900e1e1205bb0c387e6f6b7cf.jpg)  
Fig.5The influence of parameter $\rho$ on the number of iterations由上图结果可知，当 $\rho = 0 . 5$ 时，算法收敛到最优解时的迭代次数最少，因此选取 ${ \rho = 0 . 5 }$ 。  
图6算法收敛性  
Fig.6Algorithm convergence

同时，本文还在相同场景下仿真了ACO 算法和DSP算法(Dijkstra Shortest Path，迪杰斯特拉最短路径)以及 SDN-SPA[23]算法(SDN-based ShortestPath Algorithm，基于 SDN 的最短路径算法)，并针对网络传输时延、链路带宽利用率和丢包率等指标进行了详细的分析与对比。

本文结合虚拟拓扑策略，仿真模拟了100个静态网络拓扑下的不同路由算法的传输时延，如图7所示。可以看出，本文算法的传输时延始小于另外4种算法。具体来说，ACO算法、DSP算法及SDN-SPA 算法的平均传输时延分别为0.10s、0.12s及0.11s，本文算法的平均传输时延为0.076s，相比于其他算法最大降低了 $3 5 \%$ 。当网络负载增大时，由于其他算法仅根据路径距离进行路径选择，容易导致链路拥塞，因此时延较大。而本文算法将时延作为优化目标，更倾向于选择较低时延的链路，因此路径时延性能较好。

![](images/2f08f8f961f528f2175cb6cccb7aa2355323ce6a1b9e1505571d346c322bb413.jpg)  
图7网络传输时延对比

图8为带宽利用率的对比仿真图。当业务请求数小于250时，4种算法的带宽利用率相差不大。当业务请求数超过250之后，SDN-SPA算法和DSP算法的带宽利用率增大趋势变小，这是由于SDN-SPA算法和DSP算法均为基于最短路径算法，优先将数据流路由到一条最短路径。相比之下，ACO算法和本文SNMcRA算法综合考虑了链路带宽因素，在计算路径时绕过了拥塞的链路，将更多的链路作为路径选择，因此带宽利用率性能较好。但传统ACO 算法易陷入局部最优解使得其求解效果略差。本文算法结合链路信息对蚁群算法进行了改进，从而更快求得最优解。当业务请求数达到最大时，本文算法的带宽利用率相比其他算法最大提高了 $2 9 \%$ 。

![](images/39e18daa80dc3f8263869417a59aebf22e0adc01af75db8241b64eed9fa81386.jpg)  
Fig.7Network transmission delay comparison   
图8带宽利用率对比  
Fig.8Bandwidth utilization comparison

图9为平均丢包率随网络负载的变化趋势。随着网络负载的增大，4种路由算法的丢包率均逐渐增大；在网络负载较轻时，4种路由算法的丢包率相差不大；随着网络负载的增大，与其他算法相比，本文SNMcRA算法的丢包率最低，并且最大降低了 $2 6 \%$ 。这是由于ACO算法、DSP算法及SDN-SPA算法在搜索最短路径时，不考虑链路丢包率条件，只选择一条距离最短的路径，而这些最短路径上很容易产生网络拥塞，丢包率增大；本文算法综合考虑了链路的丢包率，在进行路径选择时更倾向于选择较低丢包率的非阻塞路径，因此丢包率比较小。

图10为本文MsnSDN架构、SWIMNDN架构、SDN卫星网络架构下在网络环境稳定的情况下的请求命中率的对比图。在SDN卫星网络架构下，由于转发节点不具备缓存功能，并且请求内容的提供者由源节点指定，因此该架构下请求在卫星网络中被命中的概率比较低；而在SWIMNDN架构下，转发节点引入缓存功能后充分利用网内节点缓存，有效提高了卫星网络中请求的命中率。但本文MsnSDN架构中控制器的全局视图与集中控制，能够更好的利用内容缓存实现内容查找与回传，因此请求的命中率更高。

![](images/1c1941703bb94aa425fbef605fc28d6d95d57382a7dbf7e5d285235e7196483b.jpg)  
图9网络平均丢包率对比

![](images/3a211dd2bbf0dfac3c108efa9b8e9304e87389c0ac1f943089ca7eb68d008989.jpg)  
Fig.9Comparison of network average packet loss rate   
图10请求命中率对比  
Fig.10 Request hit rate comparison

为了分析本文SNMcRA算法的时间复杂度，本文将算法运行步骤进行细分并逐步分析其时间复杂度，如表2所示。其中， $n$ 为LEO卫星节点数量， $\mid m$ 为蚂蚁数量。

表2 SNMcRA算法时间复杂度  
Tab.2Snmcra algorithm time complexity   

<html><body><table><tr><td>步骤</td><td>具体内容</td><td>时间复杂度</td></tr><tr><td>1</td><td>初始化相关参数</td><td>O(n² +m)</td></tr><tr><td>2</td><td>设置蚂蚁禁忌表</td><td>0(m)</td></tr><tr><td>3</td><td>每只蚂蚁单独构造解</td><td>0(n²m)</td></tr><tr><td>4</td><td>所有蚂蚁循环完毕并计算路径代价</td><td>O(m·n)</td></tr><tr><td>5</td><td>更新链路信息素浓度</td><td>0(n2)</td></tr><tr><td>6</td><td>保存最优解设置</td><td>0(m·n)</td></tr><tr><td>7</td><td>输出结果</td><td>0(1)</td></tr></table></body></html>

由上表可得，当算法运行结束时蚂蚁遍历的循环数为 $N _ { c }$ 时，则整个算法运行的时间复杂度为 $O ( N _ { c } \cdot n ^ { 2 } \cdot m )$ 。根据算法的理论与实际要求，SNMcRA算法在改进了传统蚁群算法的状态转移概率规则及信息素更新方式后，其时间复杂度是可以接受的。

# 5 结束语

本文提出一种基于SDN与NDN的卫星网络多约束路由算法并命名为SNMcRA。通过建立多约束路由模型，将多约束信息与蚁群算法相结合，优化了基本的蚁群算法中蚂蚁状态转移规则以及信息素更新方式，提高了算法的收敛速度和寻优能力，高效求解满足时延、带宽、丢包率多约束的代价最小路径。仿真实验表明，本文算法具有更快的收敛速度。同时，与ACO 算法和DSP算法相比，本文算法在传输时延、带宽利用率、丢包率和请求命中率等方面均具有显著优势。下一步工作将针对内容请求聚合展开研究，更好的发挥NDN内容分发的优势。

# 参考文献：

[1]Feng Xuan,Tan Qiang,Liang Zongchuang.The development of satellite mobile communication system [C]//Proc of the 2011 6th International ICST Conference on Communications and Networking in China. Piscataway: IEEE Computer Society,2011: 1110-1114.   
[2]Kodheli O,Andrenacci S,Maturo N,et al. Resource allocation approach for differential doppler reduction in NB-IoT over LEO satellite [C]// 2018 9th Advanced Satellite Multimedia Systems Conference and the 15th Signal Processing for Space CommunicationsWorkshop. Piscataway: Institute of Electrical and Electronics Engineers Inc,2018: 1-8.   
[3]Du J, Jiang C,Wang J,et al.Resource allocation in space multi-access systems [J]. IEEE Transactions on Aerospace and Electronic Systems, 2017,53 (2): 598-618.   
[4]Din I U,Hassan S,Khan MK,et al. Caching in Information Centric Networking: strategies,challenges,and future research directions [J]. IEEE Communications Surveys & Tutorials,2018,20 (2):1443-1474.   
[5] 刘迪，黄传河，陈希，等．基于 NDN 的多层卫星网络分布式动态路 由方法[J].电子学报，2017,45(11):2769-2778.(Liu Di,Huang Chuanhe,Chen Xi，et al.Distributed dynamic routing method of multilayer satelite network based on NDN[J].Acta Electronic Journal, 2017,45 (11): 2769-2778.)   
[6]KIM S Y,LEE JW.Content allocation in Information Centric Network [C]//IEEE International Conference on Information Networking.Korean: IEEE Computer Society,2016:135-140.   
[7]胡晓艳，龚俭．命名数据网络 NDN 的域间多路径路由机制[J]．通 信学报,2015,36 (10): 211-223.(Hu Xiaoyan,Gong Jian.Inter-domain multi-path routing mechanism of named data network NDN [J]. Journal of Communications,2015,36 (10): 211-223.)   
[8]Zhang L,Afanasyev A,Burke J,et al. Named data networking [J].Acm Sigcomm Computer Communication Review,2014,44 (4): 66-73.   
[9]Yi C,Afanasyev A,Wang L,et al.Adaptive forwarding in named data networking [J].Acm Sigcomm Computer Communication Review,2012, 42 (3): 62-67.   
[10] Yuan H, Crowley P. Scalable pending interest table design: From principles to practice [Cl// IEEE Conference on Computer Communications.Piscataway: IEEE,2014:2049-2057.   
[11] Guo Xian, Yang Shengya,Cao Laicheng,et al.A Novel Routing Based on OLSR for NDN-MANET[C]//Advances in Intelligent Systems and Computing.Berlin: Springer,2020: 698-714.   
[12] Hoque A K M,Amin S O,Alyyan A.NLSR:Named-data link state routing protocol [C]// ACM SIGCOMM Workshop on InformationCentric Networking. Hong Kong: ACM,2013:15-20.   
[13] Islam H MA,Lukyanenko A,Tarkoma S,et al.Towards disruption tolerant ICN [C]// 2015 IEEE Symposium on Computersand Communication (ISCC).Piscataway: IEEE.2015: 212-219.   
[14] Liu Di,Huang Chuanhe,Chen Xi,et al. Supporting producer mobility via named data networking in space terrestrial integrated networks [J]. Lecture Notes in Computer Science,2017,10251: 829-841.   
[15] Zhou Yongqi,Li Wenfeng，Zhao Kanglian．Information Centric Networking for Future Deep Space Networks [C]// Lecture Notes of the Institute for Computer Sciences,Social Informatics and Telecommunications Engineering.Berlin: Springer Verlag 2019: 437-448.   
[16] Xia Wenfeng,Wen Yonggang, Heng F C,et al. Asurvey onsoftware defined networking [J]. IEEE Communications Surveys and Tutorials, 2015,17 (1): 27-51.   
[17] Bu C,Wang X,Huang M,et al. SDNFV-based Dynamic Network Function Deployment: Model and Mechanism [J]. IEEE Communications Letters,2018,22(1): 93-96.   
[18]齐小刚，马久龙，刘立芳．基于拓扑控制的卫星网络路由优化[J]. 通信学报,2018,39 (02):11-20.(Qi Xiaogang,Ma Jiulong,Liu Lifang. Routing Optimization of Satelite Network Based on Topology Control [J].Journal of communication,2018,39 (02): 11-20.)   
[19] LIU Z,LI J,WANG Y,etal.A Hybrid Global-local load balancing Routing Scheme for the Internet of Things through Satellite Networks [J]. International Journal of Distributed Sensor Networks,2017,13 (3): 69- 72.   
[20]魏德宾，刘健，潘成胜，等．卫星网络中基于多QoS约束的蚁群优化 路由算法 [J].计算机工程,2019,45(07):114-120.(Wei Debin,Liu Jian，Pan Chengsheng，et al.Ant Colony Optimization Routing Algorithm Based on Multiple QoS Constraints in Satellite Networks [J]. Computer Engineering,2019,45 (07): 114-120.)   
[21] Li Sicong,Cai Saihua,LiLi, et al. CAAS: a novel collective action-bsed ant system algorithm for solving TSP problem [J]. SOFT COMPUTING, 2020,24 (12): 9257-9278.   
[22]陈颖杰，高茂庭．基于信息素初始分配和动态更新的蚁群算法[J]. 计算机工程与应用,2022,58(02):95-101.(Chen Yingjie,Gao Maoting. Ant Colony Algorithm Based on Pheromone Initial Distribution and Dynamic Update [J]. Computer Engineering and Applications,2022,58 (02): 95-101.)   
[23] GUO A,ZHAO C,XU F,et al.LEO satellite routing algorithm in software defined space terrestrial integrated network [Cl//2017 17th International Symposiumon Communicationsand Information Technologies (ISCIT).Institute of Electrical and Electronics Engineers Inc, 2017: 1-6.