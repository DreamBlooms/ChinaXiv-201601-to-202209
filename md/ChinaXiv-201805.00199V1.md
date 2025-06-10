# 一种支持业务优先级的卫星网络信道动态接入策略

张振浩，梁俊，肖楠，叶向阳，陈威龙，靳博(空军工程大学 信息与导航学院，西安 710077)

摘要：针对远程作战飞机接入卫星信道的业务具有优先级且高优先级业务存在突发性影响信道利用率与吞吐量的问题，提出了一种支持业务优先级的卫星网络信道动态接入策略。该接入策略通过引入认知无线电技术构建频谱池以共享信道，设置高优先级业务透明接入信道的同时通过预留信道保证低优先级业务成功接入信道，未接入信道的业务采用排队模型等待接入。仿真结果表明，该策略能够高效地保证高优先级业务接入信道的成功率，有效降低接入时延；同时较好地减小高优先级业务的突发性对低优先级业务接入的影响，有效地提升了卫星信道的综合利用率，降低了低优先级业务的接入时延，保证了低优先级业务接入卫星网络的吞吐效率。

关键词：卫星网络；信道接入；优先级；Markov过程；排队论 中图分类号：TN927 doi: 10.3969/j.issn.1001-3695.2017.06.0646

# Dynamic channel access strategy supporting service with priority for satellite communication network

Zhang Zhenhao, Liang Jun, Xiao Nan, Ye Xiangyang, Chen Weilong, Jin Bo (Information and Navigation College,Air Force Engineering University,Xian 71oo77,China

Abstract:Inorder to solvethe problemoflowchannelutilizationand throughputbecauseofburstines onhigh-priorityservice accessingthesatelitechannelonaccountoflong-rangecombataircraft transmitingdiferentpriorityservicewhen itccesses satelitechannel,the paper proposed a dynamicchannel accss strategysupporting service with priority forsatelite communication network.Theaccesstrategy constructedthe spectrumpool to sharechannel through introducingthecognitive radio technology.Itsettheigh-prioritysrviceaccessingchannelfreelymeanwile,itensuredlowproritybusinesscssthe channelsuccessfully through reserving spare channel. When there is some service not accessing channel,the service uses the queuing modelforaccess.The simulationresultsshowthatthis strategycan efectively guarantee thesuccessfulratioofhighpriorityserviceacessingchannel,meanile,iteffectivelyeducestheaccesdelay.Wentecstrategyisid,itan efectivelyreduce theimpactofburstinessonhigh-priorityserviceacessng thesatelltechannel,，hichleadstoimprovingthe comprehensive utilizationrateofthesatelite chanel,reducing theaccessdelayoflow-priorityserviceand guaranteeing the throughput on low-priority service accessing the satelite network.

Key Words: satellite network; channel access; priority; Markov process; queuing theory

# 0 引言

随着当前国家利益保障需求的不断增强，作战范围的不断拓展，战斗机、轰炸机、预警机等飞行平台远程作战成为必不可少的作战样式。执行远程作战任务的飞行平台对战场信息的实时回传分发、作战指令的高效准确传输的需求较大，原有覆盖范围有限的地面无线网络已无法满足作战需求，因而必须依赖卫星通信系统进行信息保障。

卫星网络的接入策略是决定信道利用率与保障业务QoS的关键技术之一[1]，接入策略对于网络的可靠性、吞吐量等性能有重要的影响。因而，建立一种高效、快速、稳定以及低阻塞的接入策略具有重要的意义。文献[2]提出了一种带有优先级的随机预约/按需分相相结合的RRDAMA-P接入协议，对高优先级节点在时延性能方面进行了有效保证，但是对低优先级业务的低碰撞、低信道切换性能提升不明显。文献[3]提出了一种根据信道负载和业务QoS保障需求自适应接入的APRMA机制，提升了不同类型业务接入卫星网络时网络资源综合利用率，但是由此引入了较高的系统开销，同时该机制没有充分考虑不同业务优先级的需求，只对不同类型的业务进行QoS区分保障，没有区分不同业务接入的优先级高低。文献[4]提出了一种MAC层应对业务PTT竞争时采用随机回退策略进行信道接入的方法，该策略较好地保证了传输高优先级业务的用户在发生冲突时的竞争成功率，但是在减小冲突的产生、提升低优先级用户的接入成功率与提升网络总体吞吐率性能上改善不明显。文献[5]提出了一种随机接入和按需分配的混合信道接入方法，较好地提升了系统总体吞吐量。但是所采用的信道接入策略仅对带宽需求不同的业务进行区分，使得业务在采用随机接入策略接入信道时数据碰撞率降低不明显，同时接入策略的设计基于理想假设，对于门限值的设定与选取要求较高。

针对上述文献中存在的问题，结合文献[1,6-8]等对认知无线电技术应用于卫星网络中有效地提高网络信道利用率，降低冲突发生概率，提升网络吞吐量的分析验证。本文通过引入认知无线电技术并借鉴认知无线电频谱池概念，提出了一种支持业务优先级的卫星网络信道动态接入策略，该策略能够有效地保证高优先级业务进行信道接入时的成功率，同时尽量减小高优先级业务的突发性对低优先级业务传输的影响，从而有效地提升卫星网络的信道利用率并且保证低优先级业务的网络吞吐效率。

# 1 系统模型

参与远程作战任务的飞行用户平台在远距离、跨地域作战过程中需要卫星通信网络保障正常的通信需求。在图1所示网络模型中，不同区域范围内大型空中骨干平台(如预警机等)处于非视距范围内，不同区域范围内所属小型作战单元也处于非视距范围；小型飞行平台可直接接入卫星网络，或通过接入大型飞行平台后再接入卫星网络实现远距离、跨域通信；多类型飞行平台均可以接入卫星网络实现超视距通信，而且传输的业务类型具有多样化特点。

![](images/74d05ee904634dd4e903e0871d5781c1f1a3003f59373227d12f0c3891d934ba.jpg)  
图1网络模型

不同类型的飞行用户平台（如战斗机等）在不同的时隙内可传输不同类型的业务。平台自身不具有优先级区分，仅根据作战任务的需求，对不同类型的业务进行优先级区分，可以划分为两类，即高优先级业务和低优先级业务。高优先级业务（highprioritytraffic，HPT）为与作战指令直接相关的指令消息业务和短时间话音业务，低优先级业务（lowprioritytraffic，LPT）为与作战指令间接相关的态势信息等业务。由于战场环境与作战通信指挥需求，高优先级业务相比低优先级业务而言存在突发性，因而在保证高优先级业务高效准确接入卫星信道的同时，所设计的接入策略应减少对低优先级业务接入信道的影响。

# 2 接入策略分析

# 2.1问题假设

为简化分析用户接入卫星信道过程同时不失通用性，对用户接入卫星信道过程作出如下假设：

a)每个接入卫星网络的用户的优先级与传输业务的优先级一致，同一时刻用户只能传输一种优先级的业务并且用户的优先级随传输的业务类型变化。

b)在各飞行用户平台中均引入了认知无线电技术，各个平台均具有完美的认知能力，能够较好地感知卫星网络中未被高优先级用户占用的空闲频谱。

c)传输低优先级业务的用户一旦检测到信道中有高优先业务的用户传输高优先级业务时，低优先级业务进入等待队列，直到传输低优先级业务的用户检测到空闲频谱才能再次传输。

d)用户接入卫星信道时传输的业务互相不存在干扰，且各优先级用户仅可以用单一频带来传输数据。

# 2.2接入策略设计

卫星通信网络中共有 $n$ 个等宽信道 $\{ c _ { 1 } , c _ { 2 } , L , c _ { n } \}$ 可以提供给用户。由于任务需要，与作战指令直接相关的指令消息业务和短话音业务等高优先级业务传输频率相对较低。在保证高优先级业务传输的同时提高低优先级业务的传输效率，提升带宽受限的卫星通信网络的信道资源利用率。

为此，本文借鉴认知无线电技术中频谱池的概念，实现信道资源的共享，本文基于两个用户采用多信道ALOHA竞争接入卫星通信网络，采用为高优先级用户预留适当数量信道的方式保证高优先级业务的传输，预留信道数为 $m ( m { < } n )$ 即预留信道为 $\{ c _ { 1 } , c _ { 2 } , L \ c _ { m } \}$ 。

当需要传输高优先级业务的飞行平台需要接入卫星网络时，用户从 $\mathbf { \Psi } _ { c 1 }$ 到 $c _ { \mathrm { n } }$ 按照信道标号从小到大依次接入，优先选择预留的 $\{ c _ { 1 } , c _ { 2 } , L \ c _ { m } \}$ 共 $\mathbf { \nabla } m$ 个信道中空闲的信道标号小的信道进行接入。当 $\mathbf { \nabla } m$ 个空闲信道均被占用时，则在 $\left. n - m \right.$ 个非预留信道$\{ c _ { _ m } , c _ { _ m + 1 } , L \ c _ { _ n } \}$ 中按照编号由小至大选取一个空闲信道进行接入。其中，高优先级的传输系统被描述为 $\mathbf { M } / \mathbf { M } / \mathbf { n }$ 排队模型，低优先级业务的传输系统被描述为基于强占优先级的 $\mathrm { { M } / \mathrm { { M } / n - m } }$ 排队模型[9]。从而，传输低优先级业务的用户最多可以接入的信道数为 $_ { n - m }$ 个。传输不同优先级业务的用户在同一时间无法接入相同信道，可以将该接入策略用图2所示接入模型表示。

在图2所示接入模型中，高优先级用户可以接入任意一个信道，即对于高优先级用户接入信道时不考虑低优先级业务的存在，低优先级用户是否占用信道资源对于高优先级用户完全透明。但是为保证低优先级用户低接入阻塞率和低信道切换率，高优先级用户优先接入预留空闲信道，仅当预留信道被全部占用后，才可以占用低优先级用户的信道。低优先级用户只能在感知频谱空穴后选择剩余空闲信道接入[10]，对于等待接入的大数据量高优先级业务和其余低优先级业务均采用相应的排队模型在相应的高优先级队列或低优先级队列中排队等待空闲信道。

![](images/92a394e2453d2ce9e121a4717c8af4aace31d231902030e35def3933b2f2ed6e.jpg)  
图2接入策略模型

# 3 模型建立与分析

# 3.1问题分析

用户接入卫星网络的高优先级业务的到达服从参数为 $\lambda _ { { } _ { H } }$ 的泊松分布，低优先级业务的到达服从参数为 $\lambda _ { _ L }$ 泊松分布。对高优先级业务的服务时间服从参数为 $\textstyle \mu _ { _ { H } }$ 的负指数分布，对低优先级业务的服务时间服从参数为 $\boldsymbol { \mu } _ { \scriptscriptstyle L }$ 的负指数分布。

由于高优先级业务接入信道时，所有可用信道资源对其透明。因而，定义低优先级业务被迫接入掉线状态为低优先级业务占用的信道被高优先级业务征用导致当前接入失败；低优先级业务接入阻塞状态为低优先级业务可以接入的信道被高优先级业务或低优先级业务完全占用。当低优先级业务接入卫星网络时产生的掉线率为 $P _ { f - d r o p }$ ，产生的接入阻塞率为 $P _ { b l o c k }$ 。

为了将不同优先级的业务接入信道时产生的状态以及可能发生的状态转移表示出来，本文引入马尔可夫模型[对不同优先级的业务接入频谱池时的状态进行说明。

# 3.2Markov模型建立

根据所提出的接入策略，需要接入卫星网络的不同优先级业务接入状态可分为三种：接入无碰撞状态，被迫接入掉线状态和接入阻塞状态[12]。由此可建立如图3所示Markov模型。

在马尔可夫模型中，任一状态用 $( i , j , k )$ 表示，其中，i和$j$ 分别表示等待接入卫星网络的传输高优先级业务的用户和传输低优先级业务的用户的数量， $k$ 表示接入卫星网络的状态。

用 $k { = } 0 , 1 , 2$ 分别表示接入无碰撞状态，被迫接入掉线状态和接入阻塞状态。

![](images/076cec9ae088ac4d665e1a98b2004457d2065deb8229f79b4f15e66a14ecbc7c.jpg)  
图3Markov状态转移模型

# 3.3稳态方程的确定

根据Markov过程相关理论，定义 $P ( i , j , k )$ 表示状态 $( i , j , k )$ 的稳态概率，由此可以分类建立图3中Markov过程对应的稳态方程式。

a）当 $i = 0 , 0 \leq j < n - m , k = 0$ 时,

$$
\begin{array} { l } { { P ( 0 , ~ j , 0 ) \left[ j \mu _ { _ { L } } + \lambda _ { _ { H } } ~ + \lambda _ { _ { L } } \right] = \mu _ { _ { H } } P ( 1 , ~ j , 0 ) + ( j + 1 ) \mu _ { _ { L } } P ( 0 , ~ j + 1 , 0 ) } } \\ { { + \lambda _ { _ { L } } \delta ( j ) P ( 0 , ~ j - 1 , 0 ) } } \end{array}
$$

其中， $\delta ( j ) = { \left\{ \begin{array} { l l } { 0 , j = 0 } \\ { 1 , j \neq 0 } \end{array} \right. } .$

b）当 $\mathit { \Pi } : = 0 , j = n - m , k = 0$ 时，$\begin{array} { l } { { P ( 0 , n - m , 0 ) \left[ ( n - m ) \mu _ { L } + \lambda _ { H } + \lambda _ { L } \right] = \lambda _ { L } P ( 0 , n - m - 1 , 0 ) } } \\ { { + \mu _ { H } P ( 1 , n - m , 0 ) + P ( 0 , n - m , 2 ) } } \end{array}$

c）当 $0 < i \leq m , j = 0 , k = 0$ 时，

$$
\begin{array} { r l } & { P ( i , 0 , 0 ) \left[ \lambda _ { { \scriptscriptstyle H } } + \lambda _ { { \scriptscriptstyle L } } + i \mu _ { { \scriptscriptstyle H } } \right] = \lambda _ { { \scriptscriptstyle H } } P ( i - 1 , 0 , 0 ) + \mu _ { { \scriptscriptstyle L } } P ( i , 1 , 0 ) } \\ & { + ( i + 1 ) \mu _ { { \scriptscriptstyle H } } P ( i + 1 , 0 , 0 ) } \end{array}
$$

d）当 $0 < i \leq m , 1 \leq j < n - m , k = 0$ 时,

$$
\begin{array} { l } { { P ( i , j , 0 ) \left[ j \mu _ { _ { L } } + \lambda _ { _ { H } } + \lambda _ { _ { L } } + i \mu _ { _ { H } } \right] = \lambda _ { _ { L } } P ( i , j - 1 , 0 ) + \lambda _ { _ { H } } P ( i - 1 , j , 0 ) } } \\ { { + ( i + 1 ) \mu _ { _ { H } } P ( i + 1 , j , 0 ) + ( j + 1 ) \mu _ { _ { L } } P ( i , j + 1 , 0 ) } } \end{array}
$$

e）当 $1 \leq i < m , j = n - m , k = 0$ 时，

$$
\begin{array} { r l } & { P ( i , n - m , 0 ) \left[ ( n - m ) \mu _ { L } + \lambda _ { H } + \lambda _ { L } + i \mu _ { H } \right] = \lambda _ { L } P ( i , n - m - 1 , 0 ) } \\ & { + ( i + 1 ) \mu _ { H } P ( i + 1 , n - m , 0 ) + P ( i , n - m , 2 ) + \lambda _ { H } P ( i - 1 , n - m , 0 ) } \end{array}
$$

f）当 $i = m , j = n - m , k = 0$ 时，

$$
\begin{array} { l } { { P ( m , n - m , 0 ) \left[ ( n - m ) \mu _ { { } _ { L } } + \lambda _ { { \scriptscriptstyle H } } + \lambda _ { { \scriptscriptstyle L } } + m \mu _ { { \scriptscriptstyle H } } \right] = P ( m , n - m , 2 ) } } \\ { { + \lambda _ { { \scriptscriptstyle L } } P ( m , n - m - 1 , 0 ) + \lambda _ { { \scriptscriptstyle H } } P ( m - 1 , n - m , 0 ) } } \end{array}
$$

g）当 $m + 1 \leq i \leq n - 1 , j = 0 , k = 0$ 时,

$$
\begin{array} { l } { { P ( i , 0 , 0 ) \left[ \lambda _ { { \scriptscriptstyle H } } + i \mu _ { { \scriptscriptstyle H } } + \lambda _ { { \scriptscriptstyle L } } \right] = ( i + 1 ) \mu _ { { \scriptscriptstyle H } } P ( i + 1 , 0 , 0 ) } } \\ { { + \mu _ { { \scriptscriptstyle H } } P ( i - 1 , 0 , 0 ) + \mu _ { { \scriptscriptstyle L } } P ( i , 1 , 0 ) } } \end{array}
$$

h）当 $m < i < n - 1 , 1 \leq j < n - m - 1 , k = 0$ ，并且 $i + j < n$ 时，

$$
\begin{array} { l } { { P ( i , j , 0 ) \left[ j \mu _ { _ L } + \lambda _ { _ L } + \lambda _ { _ H } + i \mu _ { _ H } \right] = \lambda _ { _ L } P ( i , j - 1 , 0 ) + ( i + 1 ) \mu _ { _ H } P ( i , j - 1 , 0 ) + } } \\ { { P ( i , j , 1 ) + ( j + 1 ) \mu _ { _ L } P ( i , j + 1 , 0 ) + \displaystyle { \frac { n - i - j } { n - i } } \lambda _ { _ H } P ( i - 1 , j , 0 ) } } \end{array}
$$

i）当 $m + 1 \leq i \leq n - 1 , i + j = n , k = 0$ 时，

$$
\begin{array} { l } { { P ( i , \ j , 0 ) \left[ \ j \mu _ { _ L } + \lambda _ { _ H } + \lambda _ { _ L } + i \mu _ { _ H } \right] = P ( i , \ j , 2 ) + } } \\ { { { \frac { n - i - j } { n - i } \lambda _ { _ H } P ( i - 1 , \ j , 0 ) + \lambda _ { _ L } P ( i , \ j - 1 , 0 ) + P ( i , \ j , 1 ) } } } \end{array}
$$

j）当 $i = n , j = 0 , k = 0$ 时,

$$
P ( n , 0 , 0 ) \left[ \lambda _ { { \scriptscriptstyle L } } + n \mu _ { { \scriptscriptstyle H } } \right] = P ( n , 0 , 2 ) + \lambda _ { { \scriptscriptstyle H } } ( n - 1 , 0 , 0 ) + P ( n , 0 , 1 )
$$

在马尔可夫过程中，当 $m + 1 \leq i \leq n , 0 \leq j \leq n - m - 1$ 并且满足 $i + j = n , k = 1$ 时，出现切换掉线状态，此时满足：

$$
P ( i , j , 1 ) = \lambda _ { _ H } P ( i - 1 , j + 1 , 0 )
$$

当低优先级业务接入卫星网络发生拥塞的状态时[13]，根据预留信道被占用情况可以分为 $m + 1 \leq i \leq n , j < n - m , k = 2$ ，$i + j = n$ 与 $0 \leq i \leq m , j = n - m , k = 2$ 两种情况，此时满足：

$$
P ( i , j , 2 ) = \lambda _ { \scriptscriptstyle L } P ( i , j , 0 )
$$

由所有概率的状态之和为1，可以计算得出各状态的状态概率。

从而，可以得到在低优先级业务接入卫星网络过程中，出现接入掉线状态和接入阻塞状态的概率为

$$
P _ { _ { f - d r o p } } = \sum _ { i = m + 1 } ^ { n } P ( i , n - i , 1 )
$$

$$
p _ { b l o c k } \ = \ \sum _ { i = m + 1 } ^ { n } P ( i , n - i , 2 ) \ + \sum _ { i = 0 } ^ { m } P ( i , n - m , 2 )
$$

# 3.4最优预留信道的确定

根据所提出的接入策略，需要传输高优先级业务的用户接入信道相对传输低优先级业务的用户是透明的[13]，因而传输高优先级业务的用户接入卫星信道时可以保证最大容量传输。为此，当低优先级业务的传输达到最大容量时用户接入卫星信道达到最大容量，此时低优先级用户接入信道的最大容量为 $V ^ { [ { 1 4 } ] }$ 。

$$
V ~ = ~ \operatorname* { m a x } _ { m = 0 , 1 , L , n } ~ \{ \operatorname* { m i n } \left\{ \lambda _ { H } ^ { m } \ : \Big | P _ { b l o c k } ~ < ~ P _ { b - t h } ~ , ~ \lambda _ { H } ^ { m } \ : \Big | P _ { f - d r o p } ~ < ~ P _ { f d - t h } \right\} \}
$$

其中： $P _ { \mathrm { b - t h } }$ 和 $P _ { \mathrm { f d - t h } }$ 表示阻塞概率和掉线率的门限值。其中，$\lambda _ { H } ^ { m } \ : \big | P _ { b l o c k } \ : \prec \ : P _ { b - t h }$ 和 $\lambda _ { \scriptscriptstyle H } ^ { \scriptscriptstyle m } \big | P _ { \scriptscriptstyle f - d r o p } < P _ { \scriptscriptstyle f d - t h }$ 分别表示满足阻塞率和掉线率约束时低优先级业务的到达率。从而，最优的预留信道数为实现低优先级用户最大信道接入容量时的预留信道数目。

# 4 性能度量指标分析

高优先级和低优先级类型的业务接入成功与否对业务传输的直接影响主要表现在传输时延是否增加，信道吞吐量与吞吐率是否下降。为此，本文选取业务传输时延、吞吐率与吞吐量作为衡量指标。

# 4.1时延性能分析

系统的传输时延作为衡量卫星网络对不同优先级业务的服务质量性能的重要参考指标。高优先级业务在接入信道时相对于低优先级业务是不受约束，因而对高优先级业务而言信道是否被低优先级用户占用是透明的，本文提出的支持业务优先级的卫星网络信道接入策略可建模为排队论中抢占优先权排队问题，针对提出的接入策略将模型建立为预留排队和打断服务综合模型，所产生的时延主要包括数据在无线信道中的传输时延、排队等待时延。

由于预留信道只能接入高优先级业务，因而对不同优先级业务接入信道的情况进行分类。

# 4.1.1高优先级业务接入时延

高优先级业务接入卫星网络时，信道是否被低优先级业务占用对高优先级业务是透明的。高优先级业务需要接入卫星网络时除需要在同等高优先级业务占用信道的情况下排队等待，其余情况均可直接接入卫星信道接受服务。因而，对高优先级业务接入卫星网络产生的时延（即高优先级业务的平均排队等待时间，包含排队时间和业务服务时间）可以等效为 $\mathbf { M } / \mathbf { M } / n$ 排队系统中只有一类顾客等待接受服务，由此可以计算得出高优先级业务接入卫星信道的时延[15]为

$$
t _ { { \scriptscriptstyle H } - d e l } = \frac { \lambda _ { { \scriptscriptstyle H } } ^ { n } } { n \mu _ { { \scriptscriptstyle H } } ^ { n + 1 } n ! ( 1 - \frac { \lambda _ { { \scriptscriptstyle H } } } { n \mu _ { { \scriptscriptstyle H } } } ) ^ { 2 } } P _ { 0 } + \frac { 1 } { \mu _ { { \scriptscriptstyle H } } }
$$

其中： $P _ { \mathrm { 0 } }$ 表示 $\mathbf { M } / \mathbf { M } / n$ 排队系统的平稳分布，可以用式（17）表示。

$$
P _ { \scriptscriptstyle 0 } = [ \sum _ { k = 0 } ^ { n - 1 } \frac { \rho _ { \scriptscriptstyle 1 } ^ { k } } { k ! } + \frac { \rho _ { \scriptscriptstyle 1 } ^ { n } } { n ! ( 1 - \rho ) } ] ^ { \scriptscriptstyle - 1 }
$$

其中：=+ $\rho _ { 1 } = \frac { 1 } { n } ( \frac { \mu _ { H } } { \lambda _ { H } } + \frac { \mu _ { L } } { \lambda _ { L } } ) \ , \quad \rho = \frac { 1 } { n ^ { 2 } } ( \frac { \mu _ { H } } { \lambda _ { H } } + \frac { \mu _ { L } } { \lambda _ { L } } ) \ _$

# 4.1.2低优先级业务接入时延

低优先级业务可以使用无高优先级业务接入的 $_ { n - m }$ 个空闲信道中任何一个。因而，对低优先级业务而言，信道接入模型可建立为抢占优先权的 $\mathbf { M } / \mathbf { M } / n { - } m$ 排队模型，即新到达的高优先级业务在无预留信道接入时，抢占正在接入的低优先级业务的信道实现自身可以顺利接入卫星网络。

卫星网络中的 $_ { n - m }$ 个空闲信道等效为排队模型中的n-m 个服务台，所有高优先级业务和低优先级业务作为待接受服务的顾客，高优先级类型的业务具有最高的卫星信道接入优先权。

根据排队论模型，低优先级业务在接入卫星网络时的时延（即低优先级业务接入卫星网络的平均逗留时间，由业务接入需要排队等待的排队时间和业务服务时间构成）可以表示为

$$
\begin{array} { c } { { t _ { L - D e l } = ( 1 + { \displaystyle \frac { \lambda _ { H } } { \lambda _ { L } } } ) \displaystyle { [ \frac { \rho _ { 1 } ^ { n - m } P _ { 1 } } { ( n - m ) \mu _ { L } \cdot ( n - m ) ! ( 1 - \rho ) ^ { 2 } } + { \displaystyle \overline { { { s } } } } ] } } } \\ { { - { \displaystyle { \frac { \lambda _ { H } } { \lambda _ { L } } } } } } \end{array}
$$

其中： $P _ { \mathrm { 1 } }$ 表示 $\mathbf { M } / \mathbf { M } / n { - } m$ 排队系统的平稳分布，可用式（19）表示； $\mathbf { \Pi } _ { s } ^ { - }$ 表示 $\mathbf { M } / \mathbf { M } / n { - } m$ 排队系统的平均服务时间，可用式（20）表示。

$$
P _ { \mathrm { 1 } } = [ \sum _ { \alpha = 0 } ^ { n - m - 1 } \frac { \rho _ { \mathrm { 1 } } ^ { \alpha } } { \alpha ! } + \frac { \rho _ { \mathrm { 1 } } ^ { n - m } } { \left( n - m \right) ! \left( 1 - \rho \right) } ] ^ { \mathrm { - 1 } }
$$

$$
\overline { { s } } = \frac { 1 } { \left( n - m \right) \left( \lambda _ { { \scriptscriptstyle H } } \mathrm { ~ + ~ } \lambda _ { { \scriptscriptstyle L } } \right) } ( \frac { \lambda _ { { \scriptscriptstyle H } } } { \mu _ { { \scriptscriptstyle H } } } + \frac { \lambda _ { { \scriptscriptstyle L } } } { \mu _ { { \scriptscriptstyle L } } } )
$$

# 4.2 吞吐量性能分析

由于在本文设计的信道动态接入策略中高优先级业务接入卫星信道时是透明的，同时高优先级业务的多为突发的数据类业务或话音类业务，对吞吐量性能要求不高。即只要存在未被高优先级业务接入的信道时，高优先级业务到来时均可以实现最大程度地信道接入保障，同时吞吐量性能对高优先级业务的影响较小。为此，着重研究低优先级业务在接入信道时的业务吞吐量。

本文基于输入/输出平衡的信道研究信道接入策略的性能，吞吐量作为衡量网络性能优劣的重要指标用以比较不同接入策略的接入效率。网络的吞吐量表示的是单位时间内不同优先级的业务成功接入卫星网络的数量，从而可以得到数据吞吐量Th的表达式为

$$
T h = ( 1 - P _ { _ { f - d r o p } } ) ( 1 - P _ { _ { b l o c k } } ) \lambda _ { _ L } ( \frac { \mu _ { _ L } } { 1 - P _ { _ { f - d r o p } } } ) ^ { - 1 }
$$

# 5 仿真与分析

# 5.1不同优先级业务到达率对网络接入性能的影响

为比较不同优先级业务的业务到达率对低优先级业务接入卫星网络时接入性能的影响并确定最优预留信道数，同时考虑到较小计算量，本文选取信道总数 $n$ 为4，分别比较预留信道数 $\mathbf { \nabla } _ { m }$ 为0、1和2时阻塞概率和被迫切换掉线率随不同优先级业务到达率的关系。

# 5.1.1高优先级业务到达率对网络接入性能的影响

仿真选取低优先级业务到达率 $\lambda _ { _ L }$ 为0.3，服务率 $\boldsymbol { \mu } _ { \scriptscriptstyle L }$ 取值为0.6，高优先级业务服务率 $\textstyle \mu _ { _ { H } }$ 为0.4，通过仿真可以得到图4所示高优先级业务到达率对低优先级业务接入卫星网络接入性能影响的仿真结果。

![](images/82c7e029cde30d28d99328a0bf6dc64ce6f90b61db4d41cb04902f0eeadb1d69.jpg)  
图4高优先级业务到达率与不同预留信道下接入性能的关系

图4所示仿真结果表明，在不同预留信道数目约束下，随着高优先级业务到达率的增加，低优先级业务的被迫掉线率和阻塞概率均不断提高。这是因为随着高优先级业务到达率的增加，高优先级业务占用了非预留信道，从而导致接入信道的低优先级业务产生阻塞和掉线。在预留信道数为2且高优先级业务到达率高时，高优先级业务接入卫星网络对低优先级业务产生较低的掉线率，但是阻塞概率相比其他预留信道增加较多；预留信道数为1时相比无预留时接入阻塞率和掉线率均有所降低。这是因为在预留信道数目为1时，高优先级业务到达的随机性对低优先级业务接入卫星网络影响较小，同时非预留信道可以较好地保证低优先级业务对信道接入的需求，因而此时阻塞率和被迫掉线率均较低。

# 5.1.2低优先级业务到达率对网络接入性能的影响

仿真选取高优先级业务到达率 $\lambda _ { { \scriptscriptstyle H } }$ 为0.4，服务率 $\textstyle \mu _ { _ { H } }$ 取值为0.4，低优先级业务服务率 $\mu _ { { } _ { L } }$ 为0.6，通过仿真可以得到图5所示低优先级业务到达率对其接入卫星网络接入性能影响的仿真结果。

![](images/79e2ccc1b3c5d43cefc5d0f5f0532d0dc54845b1eecf1038a067d4390c44bec9.jpg)  
图5低优先级业务到达率与不同预留信道下接入性能的关系

图5所示仿真结果表明，随着低优先级业务到达率不断增大，阻塞概率增加率不断提升，掉线概率增加速度缓慢；预留信道数增加时，低优先级业务接入卫星网络信道的阻塞率不断增加，掉线率不断降低。这是因为在高优先级业务保持稳定的到达率时低优先级业务到达率的增加使得新到达的低优先级业务被阻塞，但是由于高优先级业务到达率较稳定，不会因为占用非预留信道导致低优先级业务掉线。随着预留信道数量的增加，高优先级业务的到达对正在接入卫星信道的低优先级业务的影响不断减小，由此掉线率不断降低；低优先级业务可接入的信道数不断减少，由此阻塞概率不断增加。

# 5.1.3最优预留信道数的确定

为确定最优的预留信道数，仿真设置用户接入卫星网络过程中，低优先级业务允许的阻塞率阈值为0.03，被迫掉线率阈值为0.02。由此，可以得出在不同的预留信道数目约束下，允许接入的低优先级业务的最大业务到达率。

图6给出了不同预留信道数与允许接入的最大低优先级业务的到达率之间的关系。根据图4与图5所得仿真结果，当信道总数为4时，可以得到不同预留信道满足系统阻塞率和被迫切换掉线率阈值要求的传输低优先级业务的用户接入卫星信道达到最大容量。显然，在信道总数为4时，选取预留信道数为1,此时可以保证在高优先级业务以最大数据量接入卫星网络的同时低优先级业务接入卫星信道时所产生的被迫掉线率和阻塞概率较小。由此，两种业务在接入卫星信道时均可以实现高效接入，有效地保证了系统总体服务率。

![](images/148d881a98e3e97fa27f18e37bc0b6f86374c3c7e4ec3e418b1b6be50aa00d6f.jpg)  
图6预留信道数与最大LP业务到达率的关系

# 5.2不同接入策略性能对比

经过4.1比较分析得到，在信道总数 $n$ 为4，预留信道数为1时，可以在保证高优先级业务高效接入的同时有效实现低优先级业务接入过程的低阻塞率和低被迫掉线率。设置在低优先级业务的到达率发生变化时，高优先级业务到达率 $\lambda _ { { } _ { H } }$ 取值为0.4，服务率 $\mu _ { { } _ { H } }$ 取值为0.5，低优先级业务服务率 $\mu _ { _ L }$ 为0.6；在高优先级业务的到达率发生变化时，低优先级业务到达率 $\lambda _ { { \scriptscriptstyle H } }$ 取值为0.3，服务率 $\textstyle \mu _ { _ { H } }$ 取值为0.6，高优先级业务服务率 $\boldsymbol { \mu } _ { \scriptscriptstyle L }$ 为0.4,通过仿真可以得到图7所示不同接入策略下时延性能的关系。设置高优先级业务的到达率 $\lambda _ { { \scriptscriptstyle H } }$ 为0.6，高优先级业务的服务率$\textstyle \mu _ { _ { H } }$ 为0.4，低优先级业务的服务率 $\boldsymbol { \mu } _ { \scriptscriptstyle L }$ 为0.8，通过仿真比较不同接入策略影响下，低优先级业务的到达率与低优先级业务吞吐量之间的关系，可以得到图8所示仿真结果。

图7所示仿真结果表明，本文提出的动态接入卫星信道策略相比Aloha随机竞争接入和CSMA-CD接入方式均有较小的接入时延。这是因为本文所设计的动态接入策略通过引入认知无线电技术保证对信道空闲频谱的准确感知，建立的频谱池能够较好地实现频谱资源的高效共享，对信道的预留能够在有效保证高优先级业务高效接入卫星信道的同时有效实现低优先级业务的信道接入。从而本文设计的动态接入策略较好地保证高优先级业务与低优先级业务接入时延的低时延特性。但是由于高优先级业务接入信道相对低优先级业务是透明的，因而高优先级业务的接入时延相比低优先级业务稍低。

![](images/6e899261c8dd17f6ddbbb5852396985796a4347e1679217c5b9abdc300066427.jpg)  
图7不同接入策略下业务到达率与接入时延的对比关系

图8所示仿真结果表明，低优先级业务的到达率增加时，采用Aloha竞争接入卫星信道时吞吐量先增加后缓慢降低；采用CSMA-CD接入策略接入时吞吐量不断增加；采用本文设计的接入策略接入卫星信道时吞吐量不断增加，同时相比CSMA-CD 接入策略吞吐量略有提升。这是因为，本文所设计的接入策略在有效保证高优先级业务透明接入卫星信道的同时，引入认知无线电实现对频谱占用的有效感知和共享利用实现了最低碰撞概率与最高信道资源利用。由此，保证高优先级业务透明接入卫星信道实现高优先级业务接入过程最大吞吐量的同时，通过预留信道资源减少高优先级业务到达的突发性对低优先级业务接入信道的影响，实现了低优先级业务接入卫星信道时较高的吞吐量。

![](images/7844cb0ff3b5bf160c1433ec440a3d873b711ec2bce0a634086ccbb99114f8e7.jpg)  
图8不同接入策略下业务到达率与业务吞吐量的对比关系

# 6 结束语

本文针对远程作战飞机在接入卫星信道时传输的业务具有优先级且高优先级业务存在突发性影响信道占用率与吞吐量的问题，借鉴认知无线电技术，提出了一种支持业务优先级的卫星网络信道动态接入策略。该接入策略设置高优先级业务可以透明接入信道的同时通过预留信道保证低优先级业务接入信道的低阻塞率与低掉线率，未接入信道的业务采用排队模型等待接入。该策略能够高效地保证高优先级业务进行信道接入时的成功率，同时尽量减小高优先级业务的突发性对低优先级业务传输的影响，从而有效地提升卫星网络的信道利用率并且保证低优先级业务接入卫星网络的吞吐效率。

# 参考文献：

[1]肖楠，梁俊，张衡阳，等．一种基于认知无线电的卫星网络信道接入策 略[J].宇航学报,2015,36(5):589-595.   
[2]贾伟，梁俊，赵尚弘，等．一种具有优先级的MAC协议性能分析[J]. 现代防御技术,2012,40(4):93-97.   
[3]Guan M,Wang Y,Guo Q.A novel MAC protocol for mixed traffics in LEO satellite networks [C]// Proc of International ICST Conferenceon Communications and NETWORKING in China.Washington DC:IEEE Computer Society,2011: 299-303.   
[4]陈国伟，徐子平，夏雷.卫星通信组呼业务MAC层研究[J].通信技术， 2015,48 (1): 111-117.   
[5]Chang R,He Y, Cui G,et al.An allocation scheme between random access and DAMAchannels for satellite networks [C]//Proc of IEEE International Conference on Communication Systems.2016: 1-6.   
[6]Sharma S K,Chatzinotas S,Ottersten B.Cognitive radio techniques for satellite communication systems [C]//Proc of the 78th IEEE Vehicular Technology Conference.2013:1-5.   
[7]Jia M,Gu X,Guo Q，et al.Broadband hybrid satelite-terrestrial communication systems based on cognitive radio toward 5G [J]. IEEE Wireless Communications,2017,23 (6): 96-106.   
[8] Hoyhtya M,Kyrolainen J,Hulkkonen A,etal.Application of cognitive radio techniques to satellite communication [C]// Proc of IEEE International Symposium on Dynamic Spectrum Access Networks.IEEE,2012:540-551.   
[9]朱广萍．优先权排队问题的分析[J]．西南民族大学学报：自然科学版, 2004,30 (2): 134-137.   
[10] TangPK,Yong HC,Ling C O,et al.Performance of secondary radios in spectrumsharing with prioritized primary access [C]//Proc ofIEEE Military Communications Conference.2006:1-7.   
[11]李晓辉，张金钊，黑永强．基于Markov 模型的分布式队列稳定频谱接 入算法[J].通信学报,2014,35(3):22-29.   
[12]肖楠，梁俊，刘玉磊.基于动态多频谱感知的认知无线网络信道接入策 略[J].上海交通大学学报,2016,50(5):788-795.   
[13]王培雅，张朝阳，余官定．一种基于信道感知和预测的多址接入方法 [J]．解放军理工大学学报：自然科学版,2008,9(6):595-598.   
[14] Kim B,Lee G,Choi G, et al. Effective bandwidth based capacity request for real-time voice in GEO satellite system [C]//Proc of Military Communications Conference.2016:379-384.   
[15] Zhang C,Wang X,Li J. Cooperative cognitive radio with priority queueing analysis [C]//Proc of IEEE International Conference on Communications. 2009: 1-5