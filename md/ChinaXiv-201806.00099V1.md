# 一种基于软件定义网络的服务功能链优化部署机制

刘益岑1，卢昱1，王 珊²，陈兴凯‘，乔文欣‘(1．陆军工程大学石家庄校区 装备模拟训练中心，石家庄 050003;2．解放军 66172部队，石家庄 050000)

摘要：针对软件定义网络环境下，现有服务链部署方法未能充分考虑全网资源利用率的问题，提出了一种基于高效启发式算法的服务链优化部署机制。首先，给出了服务链部署的总体结构，并引入了整数型线性规划模型对其进行数学建模；其次，提出了一种高效启发式的模型求解算法，该算法以先排序后贪心的方式，能够在满足资源和时延约束下有效利用网络资源和均衡负载。仿真结果表明，与其他部署算法相比，该算法降低了负载均衡度和时间复杂度的同时提高了请求接受率。

关键词：软件定义网络；服务链；优化部署；整数型线性规划；启发式算法 中图分类号：TP393 doi:10.3969/j.issn.1001-3695.2018.03.0226

# Dynamic deployment mechanism for service chaining oriented software-defined networking

Liu Yicen1, Lu $\mathrm { Y u ^ { 1 } }$ ,Wang Shan², Chen Xingkai1,Qiao Wenxin1 (1.Equipment Training Simulation Center,Army Engineering University，ShijiazhuangO50003，China;2.66712 Troop, Shijiazhuang 050000, China)

Abstract:For the software-defined networking(SDN)environment,theexisting service function chaining(SFC)deployment method failed tofullyconsider theresource utilizationoftheentire network,andthis paper proposedaservicechaining optimaldeployment mechanism basedontheeficientheuristic algorithm.Firstly,thispapergavetheoverallstructureof the service caining deployment,and introduced an integer linear programming(ILP)model. Secondly,this paper proposed an fficient heuristicalgorithm.Thatalgorithmrunin "firstsortafter greed"mannerand efectivelyused networkresourcesand balanced load,undertheconstraintsofresourceanddelay.Finally,theobtained simulationresultsshow thatourproposed algorithmreduces the load balancingand time complexitywhile improving therequest acceptancerate,compared to other deployment algorithms.

Keywords:software-defined networking(SDN)；service function chaining(SFC)；optimal deployment;integer linear programming(ILP); heuristic algorithm

# 0 引言

随着网络信息量迅猛增长（预计截至2018年，全球互联网数据流量将达到 $1 . 6 \times 1 0 ^ { 2 1 }$ 字节[I]），人们对互联网服务需求不断扩大，传统服务功能静态服务模式带来了诸多问题：一是传统网络中服务功能（如防火墙、入侵检测和网络地址转换等）与专属硬件设备紧耦合，导致其可扩展性差、网络维护成本高等弊端；二是服务功能静态僵化难以适应当前互联网多租户模式的动态需求，造成网络运行的不稳定性。为此，新型动态服务模式研究成为近来研究的热点[2-3]。

目前，软件定义网络[4]（software defined network，SDN）和网络功能虚拟化[5]（network function virtualization，NFV）技术不断发展，SDN架构采用可编程的逻辑集中控制的方式，可根据不同细粒度需求对服务功能进行编排；NFV技术改变传统服务功能的嵌入式部署方式，将网络控制功能与硬件设备解耦，为第三方公司开发服务功能提供了条件。两者的结合增强网络的灵活性和可拓展性，达到基础设施资源共享的效果，为动态服务功能链技术的发展提供了支撑。

当前基于软件定义网络的动态服务功能链技术研究还处于起步阶段，在应用中存在很多突出问题，其中服务功能链优化部署是亟待解决的问题之一[6-8]。现有的部署问题研究更多是概念上的验证，在部署策略研究中，现有方法更多是考虑全网资源利用的单一方面，例如文献[9]提出了一种基于禁忌搜索算法的服务功能部署方法，该方法通过设置禁忌表的方式在全局网络中搜索服务功能最优的部署位置，但该方法只考虑节点资源利用率。文献[10]提出了一种面向NFV环境下的服务功能管理机制，该机制主要通过维特比算法在候选节点中选择部署开销最小的服务功能，有效地降低了服务功能的部署成本，但其缺乏对链路部署开销的考虑。文献[11]提出了一种服务功能部署模型，该模型采用AFM启发式算法进行求解，但AFM仅以物理节点的计算资源容量作为选择策略，未从全局服务路径资源利用考虑。文献[12]通过Greedy 算法穷举全网满足资源约束及连通性的所有服务路径，并选用链路资源占用量最小的服务路径，但这种方法只侧重于链路的优化选择问题。文献[13]提出了SDN/NFV架构下的服务功能部署机制，该机制构建了分层图模型，将时延最小化作为服务路径选择依据，虽然降低了服务功能链的处理时间，但该机制缺少对节点资源的考虑。

上述部署方法从不同的角度进行了探索，其主要研究不足在于：上述部署方法都是单一关注节点资源利用问题，或者单一关注链路资源利用问题，缺乏对全局资源分配方案的研究。因此，本文从全局角度出发，同时关注节点和链路的资源利用率，充分利用虚拟资源灵活分配这一特性，选择合适的功能放置位置和服务路径，以满足资源和时延约束的条件下有效地利用资源、均衡负载。本文首先给出面向SDN的服务功能链部署总体结构，并将其建模成整数型线性规划数学模型。其次，针对当前方法未能同时关注节点和链路资源利用率这一难点，设计一种启发式搜索算法求解部署模型。最后，利用负载均衡度、请求接收率和时间复杂度等指标对所提算法评价，并验证所提算法的有效性。

# 1 网络模型与问题描述

# 1.1基于SDN的服务功能链部署模型

如图1所示，基于SDN的服务链部署模型分为编排平面、控制平面和数据平面。编排平面作为虚拟网络功能（virtualnetworkfunction，VNF）的开发环境，其主要作用是对网络中VNF进行集中化管理，并根据不同的业务需求和适用场景构建出SFC策略，组合相应的功能组件形成逻辑功能链来管控网络。控制平面根据服务功能资源需求和底层资源信息，并按照一定的部署策略将VNF和虚拟链路映射到底层，实现逻辑服务链的部署。数据平面主要包括通用型的硬件设备（如标准化转发设备和x86硬件资源设备等），其主要作用是接收控制平面下发的规则，承载实际的服务请求。

![](images/1722a907f78678f2b05746c7b7155dbdf32847fc3d00a8ad14b773fc932baf9d.jpg)  
图1基于SDN的服务功能链部署模型

# 1.2服务功能链部署问题描述

服务功能链部署过程可描述为在接收到用户的 SFC 服务请求后，SDN控制器中的资源管理和VNF编排模块根据服务链请求和底层资源状态，按照指定的部署策略找到VNF和虚拟链路的优化部署位置，并生成一条满足特定功能、性能的服务路径。为了对基于SDN的服务功能链部署问题进行抽象化的表述，可将其归约为两级模型，即SFC策略一逻辑功能链和逻辑功能链一具体服务路径，如图2所示。SFC策略一逻辑功能链过程是应用程序通过北向接口实现VNF的动态编排组合；逻辑功能链一具体服务路径过程是通过南向接口实现对底层资源的合理分配。

![](images/ba408ac3a1e5ebfd45567afcd747ef76b9350d53b71ea0f4718a1b877dd92b96.jpg)  
图2SFC策略一逻辑功能链一具体服务路径过程

定义1SFC策略。包含目标集合和服务功能集合，目标集合表示所需执行处理动作的目标，服务功能集合表示数据报文必须依次遍历的服务功能。SFC策略可以表示为集合$P = \{ \nu _ { _ { s } } , \nu _ { _ { t } } , ( c _ { 1 } , c _ { 2 } , . . . c _ { _ m } ) \}$ ，式中 $C = \{ c _ { 1 } , c _ { 2 } , . . . c _ { m } \}$ 表示从源端节点 $\nu _ { s }$ 到目的端节点 $\nu _ { { } _ { t } }$ 的数据报文所需经过的服务功能序列，其中 $m$ 表示服务请求的功能数量。

定义2 逻辑功能链。控制器根据 SFC 策略编排组合VNF功能模块形成的逻辑功能链，可用集合 $F = \{ f _ { 1 } , f _ { 2 } , . . . f _ { m } \}$ 表示VNF 逻辑功能链。采用赋权的有向图 $G ^ { \nu }$ 表示全部VNF 可部署节点及其上下文连接关系，记为 $G ^ { \nu } = ( N ^ { \nu } , L ^ { \nu } )$ ，式中 $N ^ { \nu }$ 表示VNF 的逻辑节点集合，即$N ^ { \nu } = \{ n _ { 1 } ^ { \nu } . . . , n _ { i - 1 } ^ { \nu } , n _ { i } ^ { \nu } , n _ { i + 1 } ^ { \nu } , . . . n _ { m } ^ { \nu } \mid 1 \leq i \leq m \} , L ^ { \nu }$ 表示逻辑节点之间的虚拟链路集合，即 $L ^ { \nu } = \{ ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) , . . . | 1 \leq i < j \leq m \}$ 。

定义3具体服务路径。根据指定的目标函数为逻辑功能链中的VNF和虚拟链路找到对应的最优放置位置，形成从源端节点到目的端节点的具体服务路径。底层网络由所有物理节点及连接链路组成，可以用赋权无向图 $G ^ { s } = ( N ^ { s } , L ^ { s } )$ 表示，其中$N ^ { s }$ 表示底层物理节点集合，即$N ^ { s } = \{ n _ { 1 } ^ { s } , . . . , n _ { j - 1 } ^ { s } , n _ { j } ^ { s } , n _ { j + 1 } ^ { s } . . . n _ { k } ^ { s } \mid 1 \leq j \leq k \}$ ， $L ^ { s }$ 表示物理节点之间的物理链路集合，即 $L ^ { s } = \{ ( n _ { i } ^ { s } , n _ { j } ^ { s } ) , \ldots | 1 \leq i < j \leq k \}$ 。

以图2的SFC策略一逻辑功能链一具体服务路径过程为例来描述从发起服务请求到成功实现业务部署并最终提供相应的功能服务的实例化流程。首先，编排平面根据租户请求，通过调用北向接口组合形成由4个VNF组成的逻辑功能链；其次，控制平面根据底层网络资源状况，通过南向协议控制设备转发，按照一定的部署策略将逻辑服务链映射到物理底层节点，若逻辑服务功能链映射成功，则分配相应的实例化资源，进而形成一条满足特定功能、性能的服务路径。在具体服务路径中，带有阴影的节点表示部署VNF的物理节点，未带有阴影的物理节点仅仅起到转发数据的作用。

# 1.3基于整数规划的优化部署模型

优化部署策略是综合考虑服务资源需求、网络节点资源等情况，按照指定目标函数找到VNF节点和虚拟链路部署的最优位置。本节以占据物理资源最小化为目标，建立整数规划模型（integerliner programming，ILP）。为形式化表述，本文使用的符号如表1所示。

表1主要的符号定义  

<html><body><table><tr><td>符号</td><td>含义</td></tr><tr><td>c(n")</td><td>VNF 节点n的计算资源需求量</td></tr><tr><td>r(nk)</td><td>物理节点n的剩余计算资源</td></tr><tr><td rowspan="2">c(n，n)</td><td>VNF节点n与n之间虚拟链路的</td></tr><tr><td>带宽资源需求</td></tr><tr><td>r(nk,n)</td><td>物理链路(n,n）的剩余带宽资源</td></tr><tr><td>DP</td><td>请求能够容忍最大时延</td></tr><tr><td>D(n,n)</td><td>两物理节点之间的最大传输时延</td></tr><tr><td rowspan="2">D(nk）</td><td>功能所在节点nk处理数据报文的时</td></tr><tr><td>延</td></tr></table></body></html>

1）变量

$x _ { n _ { i } ^ { \nu } } ^ { n _ { k } ^ { s } }$ 二进制变量。在映射过程中，如果物理节点 $n _ { k } ^ { s }$ 承载了VNF节点 $n _ { i } ^ { \nu }$ ，该变量取值为1，否则取值为0。$y _ { n _ { i } ^ { \nu } , n _ { j } ^ { \nu } } ^ { n _ { k } ^ { s } , n _ { l } ^ { s } }$ 二进制变量。在映射过程中，如果物理节点 $n _ { k } ^ { s }$ （204$n _ { l } ^ { s }$ 之间物理链路承载了VNF 节点 $n _ { i } ^ { \nu }$ 、 $n _ { j } ^ { \nu }$ 之间虚拟链路，该变量取值为1，否则取值为 $0$ 。

2）目标函数:

$$
\operatorname* { m i n } \sum _ { n _ { i } ^ { \nu } \in N ^ { \nu } } \frac { \alpha } { r ( n _ { k } ^ { s } ) + \delta } x _ { n _ { i } ^ { \nu } } ^ { n _ { k } ^ { s } } + \sum _ { ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) \in L ^ { \nu } } \frac { \beta } { r ( n _ { k } ^ { s } , n _ { l } ^ { s } ) + \delta } y _ { n _ { i } ^ { \nu } , n _ { j } ^ { \nu } } ^ { n _ { k } ^ { s } , n _ { l } ^ { s } }
$$

3）资源约束

$$
x _ { n _ { i } ^ { \nu } } ^ { n _ { k } ^ { s } } c ( n _ { i } ^ { \nu } ) \leq r ( n _ { k } ^ { s } ) , \forall n _ { i } ^ { \nu } \in N ^ { \nu } , n _ { k } ^ { s } \in N ^ { s }
$$

$$
\begin{array} { r l } & { y _ { n _ { i } ^ { \nu } , n _ { j } ^ { \nu } } ^ { n _ { k } ^ { s } , n _ { l } ^ { s } } c ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) \leq r ( n _ { k } ^ { s } , n _ { l } ^ { s } ) , } \\ & { \forall ( n _ { k } ^ { s } , n _ { l } ^ { s } ) \in L ^ { s } , ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) \in L ^ { \nu } } \end{array}
$$

4）连接性约束

$$
\begin{array} { l } { { \displaystyle \sum _ { ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) \in L ^ { s } , ( n _ { k } ^ { s } , n _ { l } ^ { s } ) \in L ^ { \nu } } y _ { n _ { i } ^ { \nu } , n _ { j } ^ { \nu } } ^ { n _ { k } ^ { s } , n _ { l } ^ { s } } - \sum _ { ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) \in L ^ { s } , ( n _ { k } ^ { s } , n _ { l } ^ { s } ) \in L ^ { \nu } } y _ { n _ { j } ^ { \nu } , n _ { i } ^ { \nu } } ^ { n _ { k } ^ { s } , n _ { l } ^ { s } } = } } \\ { { \displaystyle x _ { n _ { i } ^ { \nu } } ^ { n _ { k } ^ { s } } - x _ { n _ { i } ^ { \nu } } ^ { n _ { l } ^ { s } } , \forall n _ { i } ^ { \nu } \in N ^ { \nu } , n _ { k } ^ { s } \in N ^ { s } } } \end{array}
$$

5）时延约束

$$
\sum _ { ( n _ { k } ^ { s } , n _ { l } ^ { s } ) \in L ^ { s } , ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) \in L ^ { \nu } } y _ { n _ { i } ^ { \nu } , n _ { j } ^ { \nu } } ^ { n _ { k } ^ { s } , n _ { l } ^ { s } } D ( n _ { k } ^ { s } , n _ { l } ^ { s } ) + \sum _ { n _ { i } ^ { \nu } \in N ^ { \nu } , n _ { k } ^ { s } \in N ^ { s } } x _ { n _ { i } ^ { \nu } } ^ { n _ { k } ^ { s } } D ( n _ { k } ^ { s } ) \leq D ^ { P }
$$

6）变量约束

$$
\sum _ { n _ { i } ^ { \nu } \in N ^ { \nu } , n _ { k } ^ { s } \in N ^ { s } } x _ { n _ { i } ^ { \nu } } ^ { n _ { k } ^ { s } } = 1 , \sum _ { ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) \in L ^ { s } , ( n _ { k } ^ { s } , n _ { l } ^ { s } ) \in L ^ { \nu } } y _ { n _ { i } ^ { \nu } , n _ { j } ^ { \nu } } ^ { n _ { k } ^ { s } , n _ { l } ^ { s } } = 1
$$

$$
x _ { n _ { i } ^ { \nu } } ^ { n _ { k } ^ { s } } \in \{ 0 , 1 \} , y _ { n _ { i } ^ { \nu } , n _ { j } ^ { \nu } } ^ { n _ { k } ^ { s } , n _ { l } ^ { s } } \in \{ 0 , 1 \}
$$

式（1)为该部署模型的目标函数，即物理资源占用量最少，以实现服务功能链部署成本最小化，式中 $ { \boldsymbol { { \alpha } } }$ 和 $\beta$ 为两个缩放参数，用于调整VNF 映射和链路映射成本的影响因子。 $\delta$ 表示极小值，用于保证分母的非零性。为了提高底层物理资源的利用率，目标函数中通过将 $r ( n _ { k } ^ { s } )$ 和 $r ( n _ { k } ^ { s } , n _ { l } ^ { s } )$ 作为分母使得 VNF映射和链路映射策略更倾向于物理资源剩余多的节点或链路。

式（2）（3）给出了计算资源和带宽资源约束条件。在计算资源约束方面，表示底层物理节点剩余资源应满足VNF实例化所需的计算资源需求。在带宽资源约束方面，底层物理链路剩余资源应满足请求中链路带宽资源需求。

式（4）为连接性约束。若在VNF节点映射阶段，VNF节点 $n _ { i } ^ { \nu }$ 和 $n _ { j } ^ { \nu }$ 分别映射到底层节点 $n _ { k } ^ { s }$ 和 $n _ { l } ^ { s }$ ，那么在逻辑链路映射阶段，逻辑链路 $( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } )$ 将被映射到从节点 $n _ { k } ^ { s }$ 到节点 $n _ { l } ^ { s }$ 的一条底层路径上。在源节点 $n _ { k } ^ { s }$ 上，流出的流量为1，流入的流量为0，所以 $\sum _ { ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) \in L ^ { s } , ( n _ { k } ^ { s } , n _ { l } ^ { s } ) \in L ^ { \nu } } y _ { n _ { i } ^ { \nu } , n _ { j } ^ { \nu } } ^ { n _ { k } ^ { s } , n _ { l } ^ { s } } - \sum _ { ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) \in L ^ { s } , ( n _ { k } ^ { s } , n _ { l } ^ { s } ) \in L ^ { \nu } } y _ { n _ { j } ^ { \nu } , n _ { i } ^ { \nu } } ^ { n _ { k } ^ { s } , n _ { l } ^ { s } } = 1$ ；在源节点 $n _ { { l } } ^ { s }$ 上，流出的流量为 $\mathbf { \boldsymbol { 0 } }$ ，流入的流量为1，所以$\sum _ { ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) \in L ^ { s } , ( n _ { k } ^ { s } , n _ { l } ^ { s } ) \in L ^ { \nu } } y _ { n _ { i } ^ { \nu } , n _ { j } ^ { \nu } } ^ { n _ { k } ^ { s } , n _ { l } ^ { s } } - \sum _ { ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) \in L ^ { s } , ( n _ { k } ^ { s } , n _ { l } ^ { s } ) \in L ^ { \nu } } y _ { n _ { j } ^ { \nu } , n _ { i } ^ { \nu } } ^ { n _ { k } ^ { s } , n _ { l } ^ { s } } = - 1$ ；而在其它节点上，流入流 出 的 流量 均为1， 所以$\sum _ { ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) \in L ^ { s } , ( n _ { k } ^ { s } , n _ { l } ^ { s } ) \in L ^ { \nu } } y _ { n _ { i } ^ { \nu } , n _ { j } ^ { \nu } } ^ { n _ { k } ^ { s } , n _ { l } ^ { s } } - \sum _ { ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) \in L ^ { s } , ( n _ { k } ^ { s } , n _ { l } ^ { s } ) \in L ^ { \nu } } y _ { n _ { j } ^ { \nu } , n _ { i } ^ { \nu } } ^ { n _ { k } ^ { s } , n _ { l } ^ { s } } = 0 _ { \mathrm { ~ c ~ } }$

式（5）为服务路径的时延约束。服务提供商为租户成功将服务请求映射到底层物理网络过程中，构建出的一条端到端服务路径，时延表示数据流从源端节点发出到目的节点所耗费的时间，时延约束确保满足网络的服务等级协定（SLA）。

式（6）为逻辑功能链的映射约束，确保同一个服务请求中的服务只能映射到底层唯一的节点上。式（7）为 $x _ { n _ { i } ^ { \nu } } ^ { n _ { k } ^ { s } }$ 变量和y变量的二进制约束。

# 2 算法描述

针对上文提出的服务功能链部署模型，可利用优化理论将其归约为虚拟网络映射问题[14-16]。虚拟网络映射问题已被证明是NP-Hard问题[17]，因此服务功能链部署问题同样为NP-Hard问题，即在 $N P \neq P$ 条件下，不可能存在多项式时间算法来解决该问题，通常采用高效的搜索算法以求得问题的近似解。传统虚拟网络映射过程中的两步映射算法[18]将映射过程分为节点映射和链路映射，但服务链部署过程中的逻辑功能链映射和传统虚拟网络映射不同的是，需要综合考虑服务链的端系统、实例化资源分配和编排顺序等特性。本文根据服务功能链部署的特性，设计一种“先排序后贪心”的启发式搜索算法，以快速且高效地求解服务功能链部署模型。

# 2.1基于高效启发式算法的服务链部署

当前对服务功能链部署问题更多是单一关注节点资源利用问题，或者单一关注链路资源利用问题。针对这一难点，本文提出了一种高效启发式搜索算法（greedy node embeding withk-shortest path link embedingalgorithm，G-kSP），该算法综合考虑租户的服务资源需求、底层物理剩余资源和QoS等情况，在服务功能链部署过程中同时关注VNF放置和路径选择两阶段，从而得到全局最优的资源分配策略。

为了对逻辑功能链中VNF资源需求情况和底层物理节点资源剩余情况更为精确化的描述，本节在此给出VNF综合资源需求函数 $C ( n _ { i } ^ { \nu } )$ 和物理节点综合剩余资源函数 $R ( n _ { k } ^ { s } )$ 的概念。其定义分别如下：

$$
C ( n _ { i } ^ { \nu } ) = c ( n _ { i } ^ { \nu } ) \sum _ { e _ { i } ^ { \nu } \in E ( n _ { i } ^ { \nu } ) } c ( e _ { i } ^ { \nu } )
$$

其中： $E ( n _ { i } ^ { \nu } )$ 表示VNF节点 $n _ { i } ^ { \nu }$ 所有邻接虚拟链路集合， $c ( n _ { i } ^ { \nu } )$ 表示 VNF 节点 $n _ { i } ^ { \nu }$ 实例化所需的计算资源量， $\boldsymbol { r } ( e _ { i } ^ { \nu } )$ 表示虚拟链路实例化所需的带宽资源。

$$
R ( n _ { k } ^ { s } ) = r ( n _ { k } ^ { s } ) \sum _ { e _ { k } ^ { s } \in E ( n _ { k } ^ { s } ) } r ( e _ { k } ^ { s } )
$$

其中： $E ( n _ { k } ^ { s } )$ 表示底层物理节点 $n _ { k } ^ { s }$ 所有邻接物理链路集合，$r ( n _ { k } ^ { s } )$ 表示物理节点 $n _ { k } ^ { s }$ 当前剩余的计算资源， $r ( e _ { k } ^ { s } )$ 表示物理链路当前剩余的带宽资源。

为了简化传统启发式算法的搜索空间，提高求解全局资源分配策略的效率，针对式（1）～（7）所示的部署模型，本文设计的G-kSP算法是一种先排序后贪心高效搜索方法，其中采用排序的方式旨在简化算法的搜索空间，在不进行全局搜索的情况下就能得到最优服务路径，而在贪心选择过程中，将优先考虑资源剩余量最多的物理节点或链路作为贪心策略，贪心策略对每一子问题操作产生直接影响，得到每个子问题最优的资源分配策略，进而快速、高效地逼近模型目标函数。同时，在迭代过程中算法采用回溯的机制，即当前迭代的VNF或虚拟链路搜索不到满足资源约束条件的解时，应当回溯到上一阶段迭代可映射集合中的次优解。G-kSP算法的运行过程具体描述如

表2所示。

表2G-kSP算法具体过程

输入：SFC请求 $P = \{ \nu _ { _ { s } } , \nu _ { _ { t } } , ( c _ { _ { 1 } } , c _ { 2 } , . . . c _ { _ { m } } ) , \tau \}$ ，底层物理网络$G ^ { s } = ( N ^ { s } , L ^ { s } )$ 。

输出：VNF 映射集合 $\Big \{ M _ { N } ( n _ { i } ^ { s } ) \Big | \forall n _ { i } ^ { s } \in N ^ { s } \Big \}$ 、虚拟链路映射集合$\left\{ M _ { L } ( n _ { i } ^ { s } , n _ { j } ^ { s } ) \Big | \forall ( n _ { i } ^ { s } , n _ { j } ^ { s } ) \in L ^ { s } \right\} \circ$

a)构建VNF 队列 $\boldsymbol { \mathcal { Q } }$ 。根据在线到达的请求构建 SFC 策略，进而编排组合VNF形成具有链式结构的虚拟网络层 $G ^ { \nu }$ ，计算集合 $N ^ { \nu }$ 中每个VNF 节点的资源需求量 $C ( n _ { i } ^ { \nu } )$ ，按照 $C ( n _ { i } ^ { \nu } )$ 由大到小进行重新排列，并将其放入队列 $\boldsymbol { \mathcal { Q } }$ 中。

$\mathbf { b } )$ 构建可映射节点集合 $M$ 。根据底层物理节点 $r ( n _ { k } ^ { s } )$ 及 $\boldsymbol { r } ( \boldsymbol { e } _ { k } ^ { s } )$ 资源信息，计算可映射物理节点 $n _ { k } ^ { s }$ 的综合剩余资源量 $R ( n _ { k } ^ { s } )$ ，并利用式(2)\~（6）判断该物理节点的剩余资源是否满足资源约束，将满足约束条件的底层物理节点形成可映射集合 $M$ 。  
c)选择VNF节点最优位置 $M _ { N } ( n _ { i } ^ { s } )$ 。取出队列 $\boldsymbol { \mathcal { Q } }$ 中第一个需要部署的VNF，利用式（10）搜索可映射集合 $N ^ { s }$ 中的物理节点，将VNF 关联到物理节点 $n _ { k } ^ { s }$ 上，若成功将 VNF 映射到物理节点 $n _ { k } ^ { s }$ 上，则 $x _ { n _ { i } ^ { \nu } } ^ { n _ { k } ^ { s } } = 1$ ，并记录到集合 $M _ { N }$ 中；否则，回溯到上一步迭代可映射集合 $M$ 中的次优解。更新队列 $\boldsymbol { Q }$ 。

$$
n _ { k } ^ { s } = \left\{ \hat { n } _ { k } ^ { s } \left| \hat { n } _ { k } ^ { s } = \arg \operatorname* { m a x } { R ( n _ { k } ^ { s } ) } , \forall n _ { k } ^ { s } \in N ^ { s } \right. \right\}
$$

d)得到VNF 映射集合 $M _ { N }$ 。判断队列 $\boldsymbol { Q }$ 中是否还有VNF 没有完成映射，若是则转到步骤2，执行队列 $\boldsymbol { Q }$ 中下一个VNF节点；否则，完成VNF 映射，得到集合 $M _ { N }$ 。  
e)构建路径集合 $R$ 。完成VNF映射后，根据集合 $M _ { N }$ ，按照服务功能链顺序 $\varphi _ { P }$ ，以链路剩余带宽 $r ( n _ { k } ^ { s } , n _ { l } ^ { s } )$ 为权重，利用 $K$ -Dijkstra算法计算从源端节点 $\nu _ { s }$ 到目的端节点 $\nu _ { { } _ { t } }$ 的 $k$ 条最短路径集合 $R$ ，记为$R = \{ r _ { 1 } , r _ { 2 } , . . . , r _ { k } \} _ { \mathrm { ~ o ~ } }$ （204  
f)选择虚拟链路最优位置 $M _ { L } ( n _ { i } ^ { s } , n _ { j } ^ { s } )$ 。将集合 $R$ 按照带宽资源占用量c(n,n)进行由小到大的排序，并选取第一条路径，则y",=1,记录到集合 ${ { M } _ { L } }$ 中；否则，回溯到最短路径集合 $R$ 中的次优解。g)服务时间监控和资源分配。完成虚拟链路映射后，利用式（7）判断是否满足服务功能链QoS指标，若满足则底层资源池为其分配相应实例化资源，以完成SFC部署过程，并更新底层资源状态；否则，收回为其分配的资源，服务功能链部署失败。

# 2.2算法复杂性理论分析

在服务功能链部署过程中，假设存在 $n$ 个VNF 需要映射，底层网络中 $m$ 个物理节点和 $M$ 条物理链路。G-kSP算法在VNF映射过程中，首先将 $n$ 个VNF根据所需资源按照从大到小顺序进行排列，VNF映射过程的计算量主要在于资源需求量排序和底层剩余资源量的搜索，其复杂度为 $O ( n \log { n } )$ ，而在虚拟链路映射过程中，由于每条虚拟链路映射到底层物理网络中采用 $K$ -Dijkstra算法，其时间复杂度为 $O ( K + M )$ 。综上所述，G-kSP算法的时间复杂度为 $O ( K + n \log n + M )$ ，即可等价于$O ( n \log { n } )$ 。

# 3 实验评估与分析

为了验证本文所提出的部署算法（记为G-kSP）的有效性，本文选取其它两种典型的部署算法进行对比（如表3所示），选取负载均衡度，请求接受率和时间复杂度这三种重要部署评价指标来验证G-kSP算法的有效性，其中负载均衡度反映算法搜索的均衡程度，请求接受率反映算法在解空间的搜索性能，而请求处理时间反映算法在计算性能。

表3比较算法  

<html><body><table><tr><td>算法</td><td>描述</td></tr><tr><td>G-kSP</td><td>本文所提出的基于全局资源利用的高效启发式搜索算法</td></tr><tr><td rowspan="2">TS</td><td>基于文献所提出的通过设置禁忌表的方式在全局网络中搜索服务最</td></tr><tr><td>优的部署位置的算法，这是一种侧重于节点资源优化利用的方法</td></tr><tr><td>Greedy</td><td>基于文献[12]所提出的通过赋予考虑低时延链路较高优先级的算法，侧</td></tr><tr><td></td><td>重链路资源的优化利用</td></tr></table></body></html>

# 3.1实验环境和参数设置

本实验在配置为IntelCorei7-37703.60GHz、8GB内存的Linux 系统PC机上运行。网络拓扑结构是利用GT-ITM[19]工具生成，算法程序通过Matlab软件运行。与文献[20]类似，本文采用包含6个相同物理节点的网络拓扑结构的测试例子作为底层基础设施来进行实验，与一个轻量级的云数据中心网络环境类似。如图3所示，网络拓扑由6个节点和14条链路组成（节点上的数字代表节点标签号），以节点1为数据流量入口，节点6作为流量的出口。假设所有节点部署在云数据中心，并连接所有节点能够承载服务功能，物理节点资源和链路带宽剩余资源容量服从[1000,1500]的随机分布，链路和节点的单位映射成本均为1。每条SFC请求由不同类型的服务功能组成，其数量服从[2,5]的随机分布，每条SFC节点和链路的资源需求量均服从[0.5,1]的均匀分布，底层网络支持的服务类型数量设为10，每个节点随机提供其中的1-5种。

![](images/2d993837f5a0dac14b6c71fbd583d67c2e2e5f0ca1337bd7ffc897434774248d.jpg)  
图3仿真实验网络拓扑

# 3.2 算法性能对比

a)节点负载均衡度,表示物理节点的负载积累情况，反映出算法在节点资源利用率上的优劣程度，其取值越小越好，各物理节点上负载越均衡越好。记物理节点的负载均衡度计算式为

$$
L B _ { n _ { i } ^ { s } } = \sum _ { n _ { k } ^ { s } \in M _ { N } , n _ { i } ^ { \nu } \in N ^ { \nu } } \frac { c ( n _ { i } ^ { \nu } ) } { r ( n _ { k } ^ { s } ) }
$$

实验中生成 $1 0 \sim 1 0 0$ 次SFC请求强度，分别统计3种算法的节点负载均衡度，如图4所示。

![](images/2082a805061711593690766fc906ce82430118c3430392f37ddceb4f2db402c2.jpg)  
图4节点负载均衡度性能比较

由图4可知，基于TS的部署方法能在获得最大平均负载均衡度的同时，节点最大负载均衡度更小，表明该算法在均衡节点负载度的效果更好，反之Greedy算法的效果较差，G-kSP算法居中。原因在于TS算法以底层节点的计算资源容量作为选择策略，在反复迭代过程中能搜索到较好的节点选择方案，使得节点的资源能够得到有效利用，而Greedy算法优先考虑低时延链路上的节点，容易造成部分功能节点负载均衡效果不佳。

b)具体路径负载均衡度,表示整条服务功能链的负载累积情况。反映出算法在全网资源利用率上的优劣程度，其取值越小越好。记具体执行路径的负载均衡度计算式为

$$
\begin{array} { c } { { { \displaystyle L B _ { R S P } = \omega _ { N } \displaystyle \sum _ { n _ { k } ^ { s } \in M _ { N } , n _ { i } ^ { v } \in N ^ { \nu } } \displaystyle \frac { c ( n _ { i } ^ { \nu } ) } { r ( n _ { k } ^ { s } ) } + } } } \\ { { { \displaystyle \omega _ { L } \sum _ { ( n _ { k } ^ { s } , n _ { l } ^ { s } ) \in M _ { L } , ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) \in L ^ { \nu } } \displaystyle \frac { c ( n _ { i } ^ { \nu } , n _ { j } ^ { \nu } ) } { r ( n _ { k } ^ { s } , n _ { l } ^ { s } ) } } } } \end{array}
$$

式中缩放因子 $\omega _ { \scriptscriptstyle N }$ 和 $\omega _ { _ L }$ 用于调整节点负载和链路负载的侧重程度。

实验中生成 $1 0 \sim 1 0 0$ 次 SFC请求强度，分别统计3种算法的服务路径负载均衡度，如图5所示。由图5可知，随着请求到达强度的增加，可用的资源量减少，曲线逐渐趋近平缓。随着资源瓶颈的出现，请求接受率逐渐降低，服务路径构建失败的次数增多。随着请求到达强度增加，基于G-kSP算法的部署方法最能有效平衡服务路径的负载，由于TS 算法以及Greedy算法均未能从全局最优路径的角度进行资源分配，从而致使网络服务路径的负载相对不平衡，但Greedy算法赋予考虑低时延链路较高的部署优先级，容易导致部分链路频繁复用，由此过早陷入资源瓶颈，因此TS算法的服务路径负载均衡性能上优于Greedy 算法。

![](images/5cb92324a409fb486052c8e9e1ca60871cba6aaeff98ab46956468f75ad55c83.jpg)  
图5具体路径负载均衡度比较

c)请求接受率,表示满足资源、时延等约束的请求接受比例，其反映算法的在解空间中的搜索性能，取值越大越好。请求接受率可表示为成功部署到底层物理网络的SFC条数与SFC请求总条数之比，记请求接受率 $\eta$ 的计算公式为

$$
\eta = \operatorname* { l i m } _ { T \to \infty } \frac { \sum _ { t = 0 } ^ { T } S F C _ { a c c e p t e d } } { \sum _ { t = 0 } ^ { T } S F C _ { t o t a l } }
$$

其中 $\sum _ { t = 0 } ^ { T } S F C _ { a c c e p t e d }$ 表示从时刻 $t = 0$ 到时刻 $T$ 成功部署到底层物理网络的 SFC 条数； $\sum _ { t = 0 } ^ { T } S F C _ { t o t a l }$ 表示到达的 SFC 请求总条数。

实验中生成 $1 0 \sim 1 0 0$ 次 SFC请求强度，分别统计3种部署算法的请求接受率，如图6所示。由图6可知，在相同条件下，基于G-kSP算法的平均请求接受率约为 $9 5 . 4 \%$ ,TS部署算法平均请求接受率约为 $9 2 . 3 \%$ ，Greedy 部署算法平均请求接受率约为 $8 1 . 7 \%$ 。分析其原因是G-kSP算法主要从全局最优路径考虑，降低了整条服务功能链的负载均衡程度，提高了底层物理资源的利用率，占据更少的资源空间，从而尽最大限度为队列中其他请求完成部署留出实例化资源，增加了请求接受率；而Greedy算法主要考虑链路资源利用，增加了节点处理的排队时间和底层网络负载，从而降低了请求接受率。而TS 算法主要考虑了节点资源情况，能够通过反复迭代计算搜索最优的部署方案，相比于Greedy算法改善了服务请求接受率。

![](images/74661c33281954c2af83c4ca310703a3da7e2a6c89456adb022984ee58d4a13b.jpg)  
图6请求接受率比较

d）时间复杂度，表示从发出请求到完成部署过程的运行时间，时间复杂度反映算法在计算性能方面的优劣程度，运行时间的取值越小越好。实验中生成10\~100次SFC请求强度，分别统计3种算法的请求处理时延，如图7所示。

![](images/f42f9449e3461632126a1f316fb280deacf846f0d231fe7e12e09961af2a82fb.jpg)  
图7算法时间复杂度比较

由图7可知，随着请求到达强度增加，G-kSP算法的处理时延较小，能够更快地完成服务功能链的部署，反之Greedy算法的处理时延较大，其时间复杂度约为G-kSP算法的10\~12倍，TS算法居中。分析其原因是Greedy 算法实质是一种两步映射算法，即分为VNF节点映射和逻辑链路映射，在VNF 映射阶段过程中穷举出底层满足约束条件的节点，时间复杂度为$O ( m ^ { n } )$ ，在逻辑链路映射过程中通过最短路径选择节点之间带宽占用最少的路径，时间复杂度为 $O ( m ^ { 2 } )$ ，完成映射的VNF节点需要等待队列中下一个VNF节点完成映射后才能建立服务路径，因此Greedy算法不仅搜索空间度大，而且虚拟链路映射容易受到VNF映射的影响，导致队列中VNF等待的时间较长，算法运行效率低，则总的时间复杂度则为 $O ( m ^ { n } + m ^ { 2 } )$ 。

而 TS算法的处理时延受禁忌表长度 $\lambda$ 的影响，随着 $\lambda$ 增加会造成算法存储空间扩大，计算处理时延增加，TS算法的时间复杂度可表示为 $O ( m ^ { 2 } + m \lambda )$ 。结合3.2 节中G-kSP 算法复杂度的理论分析，图7中各曲线的变化趋势与理论分析基本一致。

# 4 结束语

本文提出的服务功能链部署方法能够同时关注部署过程中节点和链路的资源利用率问题。首先，针对服务功能链优化部署问题，给出面向SDN的服务功能链部署总体结构，将部署总体结构归约为 SFC 策略一逻辑功能链一具体服务路径两级模型，并建模成整型线性规划数学模型。此外，针对当前部署方法中未能完全考虑全局资源利用这一难点，设计了一种先排序后贪心的启发式搜索算法，与禁忌部署算法和贪婪启发式算法对比，本文方法在负载均衡度、请求接收率和时间复杂度等性能指标上有良好的性能，并能够更快速、更有效地得到最优资源分配方案。目前，业界对基于SDN的服务功能链研究不断深入，下一步将针对可靠性感知下的服务功能链部署研究，以满足网络服务链可靠性需求和电信级的网络服务质量。

# 参考文献：

[1]Cisco.Cisco visual networking index: forecast and methodology [R/OL]. https://www.cisco.com/c/en/us/solutions/collateral/service-provider/visualnetworking-index-vni/complete-white-paper-c11-481360.html   
[2]Bhamare D,Jain R,Samaka M,et al.A survey on service function chaining [J]. Journal of Network & Computer Applications,2016,75(C): 138-155.   
[3]Medhat AM,Taleb T,Elmangoush A,et al. Service function chaining in next generation networks: state of the art and research challenges [J].IEEE Communications Magazine,2017,55 (2):216-223.   
[4]Mckeown N,Anderson T,Balakrishnan H,et al.OpenFlow:enabling innovation in campus networks [J].ACM SIGCOMM Computer Communication Review,2008,38 (2): 69-74.   
[5]ETSI. Network functions virtualization [R]. NFV White Paper, 2012.   
[6]Takacs A,Green H, Shirazipour M,et al. Network function placement for NFV chaining in packet//optical datacenters [J].Journal of Lightwave Technology,2015,33 (8):1565-1570.   
[7]Huang Meitian,Liang Weifa,Xu Zichuan,et al. Throughput maximization in software-defined networks with consolidated middleboxes [C]//Local Computer Networks.2016:298-306.   
[8]Kim S,Park S,Kim Y,et al. VNF-EQ:dynamic placement of virtual network functions for energy efficiency and QoS guarantee in NFV [J]. Cluster Computing,2017,20 (3): 2107-2117.   
[9]Mijumbi R,Serrat J,Gorricho JL,et al.Design and evaluation of algorithms for mapping and scheduling of virtual network functions [C]// Network Softwarization. 2015: 1-9.   
[10]Bari MF,Chowdhury SR,Ahmed R,et al.On orchestrating virtual network functions [C]// Proc of International Conference on Network and Service Management. 2015: 50-56.   
[11] Zeng Menglu,Fang Wenjian, Zhu Zuqing.Orchestrating tree-type vnf forwarding graphs in inter-dc elastic optical networks [J]. Journal of Lightwave Technology,2016,34 (14): 3330-3341.   
[12]Lukovszki T,Rost M,Schmid S.It'sa match!: near-optimal and incremental middlebox deployment [J].ACM SIGCOMM Computer Communication Review,2016,46 (1): 30-36.   
[13]Dwaraki A,Wolf T.Adaptive service-chain routing for virtual network functions in software-defined networks [C]// Proc of Workshop on Hot Topics in Middleboxes and Network Function Virtualization.New York: ACM Press,2016: 32-37.   
[14]Even G,Rost M,Schmid S.An approximation algorithm forpath computation and function placement in SDNs [C]// Proc of International Colloquium on Structural Information and Communication Complexity. Cham: Springer,2016: 374-390.   
[15] Schmid S.Online Admission control and embedding of service chains [C]// Procof International Colloquium on Structural Informationand Communication Complexity. New York: Springer-Verlag,2015: 104-118.   
[16] Moens H,Turck F D.VNF-P:a model for efficient placement of virtualized network functions [Cl// Proc of International Conference on Network and Service Management. 2014: 418-423.   
[17] Chowdhury M,Rahman M R,Boutaba R.ViNEYard: virtual network embedding algorithms with coordinated node and link mapping [J]. IEEE//ACM Trans on Networking,2012,20(1): 206-219.   
[18] Yu Minlan,Yi Yung，Rexford J,et al.Rethinking virtual network embedding: substrate support for path splitting and migration [J].ACM SIGCOMM Computer Communication Review, 2008,38 (2):17-29.   
[19] Calvert KL,Bhattacharjee S.How to Model an Internetwork [C]//Proc of IEEE INFOCOM.1996:594.   
[20] Sahhaf S, Tavernier W,Rost M,et al. Network service chaining with optimized network function embedding supporting service decompositions [J].International Journal of Computer & Telecommunications Networking, 2015,93 (P3): 492-505.