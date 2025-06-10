# 安全服务链中虚拟网络功能分配与调度算法研究

黄睿，张红旗(解放军信息工程大学，郑州 450001)

摘要：安全服务链中的虚拟网络功能（virtualnetwork function，VNF）将传统网络安全功能与硬件设备解耦，使得服务功能的部署更具动态性和可扩展性。然而，VNF向节点的合理分配以及节点上VNF的高效调度问题仍亟待解决。为此，基于软件定义网络（softwaredefined network，SDN）和网络功能虚拟化（network function virtualization，NFV）环境，提出基于优化算法的解决方案。首先，对资源分配与调度问题进行举例并形式化定义问题的优化目标；其次，提出基于贪心算法的资源分配方案和基于混合蜂群算法的资源调度方案，统一协调解决VNF的资源分配与调度问题。最后，设计仿真实验，验证所提算法的时间复杂性和在总资源成本和总服务收益方面的提升；同时，对比混合蜂群算法和传统蜂群算法，结果显示前者具有更快的收敛速度。

关键词：安全服务链；虚拟网络功能；软件定义网络；网络功能虚拟化；贪心算法；混合蜂群算法中图分类号：TP393 doi: 10.3969/j.issn.1001-3695.2017.09.0949

# Research on algorithm of VNF allocation and scheduling problems in security service chain

Huang Rui, Zhang Hongqi (People's Liberation Army Information Engineering University,Zhengzhou 45ooo1,China)

Abstract:The virtual network functionin thesecurityservicechain decouples the traditional network securityfunctions from thehardwaredevices,makingthedeploymentofservicefunctions moredynamicandextensible.However,therationalalocation of the VNFtothe nodeandtheeficient schedulingof the VNFonthe node stillneedtobesolvedurgently.Tothis nd,this paper presented a solution using optimization algorithm based on the software defined network and network function virtualizationenvironment.First,this paper madeanexampleofresource allcationandscheduling problemand formalizes the objective. Then,this paper proposed aresource alocation scheme based on greedy algorithmand aresource scheduling scheme basedonhybridbeecolonyalgorithmtosolvetheproblemcoordinately.Finaly,thesimulationexperiment isdesignedtoverify thetime complexityand theimprovementoftotalresourcecostandtotal serviceincomeoftheproposedalgorithm.Meanwhile, it comparedthe hybrid beecolonyalgorithmwith thetraditional beecolonyalgorithm,indicating thatthe formerhas better convergence rate.

Key Words:securityservicechain; virtualnetwork function;softwaredefined network;network functionvirtualization;gredy algorithm; hybrid bee colony algorithm

# 0 引言

当前网络安全服务依赖于网络运营商为其提供专用的硬件设备，加剧了网络安全功能与硬件设备的紧耦合关系，造成网络安全服务模式静态僵化，难以满足未来多样化的网络业务需求[1,2]。表现为：一方面现有安全功能（防火墙、IDS(intrusiondetection system)、IPS(intrusion protection system)）的硬件化,导致安全功能封闭固化、灵活性差；另一方面安全功能的静态部署难以满足业务需求的动态变化，造成网络资源的浪费。因此，软件定义网络（software defined network,SDN）[3,4]下的安全服务链动态组合机制应运而生[56]。作为安全服务链构建部署过程中的重要组成部分，服务链中虚拟网络功能（virtualnetworkfunction,VNF）[7]的分配与调度算法研究迫在眉睫。

当前，SDN的迅猛发展催生了网络功能虚拟化（networkfunction virtualization,NFV）[8,9]技术的蓬勃兴起。SDN 将控制功能从传统的分布式网络设备中解耦出来，并使其直接可编程，实现了网络的集中管控；NFV通过虚拟化方式将以专有硬件形式部署的网络功能转变为在通用服务器上运行的VNF，为上层网络功能创新提供了条件。两者结合为探索网络安全服务新模式提供了有力的支撑。

针对VNF资源分配与调度问题，现有相关研究较少且不全面。Riera等人在文献[10,11]中首次对VNF资源调度问题进行了形式化的定义，将最小化完成时间作为某可行方案的优化目标，但并未给出具体的解决方法。Mijumbi等人在文献[12]中基于禁忌搜索算法解决了VNF 中的资源分配/映射问题，但并未针对资源调度问题给出合理化的解决方案。因此，本文通过借鉴这些新的研究思路，完善不足，创新性地提出了基于贪心算法的资源分配方案和基于混合蜂群算法的资源调度方案，将资源调度过程抽象建模为柔性作业车间调度问题（flexibleJob-Shop schedulingproblem,FJSP)，并采用混合蜂群算法（hybridbee colony,HBC）求解此问题，确保了资源调度过程的高效性和资源分配与调度过程的协调性。

# 1 问题描述

如图1所示，安全服务链中VNF物理资源配置问题可以分为两类：（1）虚拟网络嵌入（virtualnetworkembedding,VNE）。VNE 是指虚拟设备嵌入到物理设备，主要涉及不同网络状态下物理节点的选择、可用物理资源的计算以及两类节点间的关联映射问题[13,14]。相关研究已经较为成熟，因此不在本文的探讨范围之内。（2）虚拟网络功能分配与调度（virtualnetworkfunctionallocationand scheduling,VNF-AS)。VNF-AS 是指根据不同安全服务需求对虚拟节点上的多个VNF 进行合理分配与调度，优化执行顺序，降低资源损耗，力求产生最大能效。相关研究较少且不完善，因此成为本文关注的重点。

![](images/d7da0c42cb8920bbae0dfbb9ad4d754eb748d9b58da3ccfc6e74d4a77278b285.jpg)  
图1虚拟网络功能嵌入与调度问题

对于VNF-AS问题，存在许多资源共享的可能性。一种情况是，每一个VNF嵌入一个特定的虚拟设备，该虚拟设备的所有资源由其独享。例如，安全服务链SSC1:Firewall $- > I D S - > P r o x y - > I P S - > N A T$ 是由5个不同种类的VNF组成，这就意味着对于不同用户的安全服务请求，需要5个特定的虚拟设备为其提供服务。这不仅会对物理资源产生巨大的损耗，同时，也不宜于满足大规模网络中用户复杂的安全服务请求。本文采用基于容器技术实现的网络功能节点。如图2所示，高性能服务器（highvolume server,HVS）作为提供安全服务的物理节点，HVS中装配有容器集群，由编排器进行统一编排和管理。每个容器中，可开启多个VNF，使得安全服务链中VNF的合理分配与优化调度成为可能。

![](images/9a9ee920ef6676f7b10c00576df9b5767b41b749c105bd08c1f6c1eb804be3b6.jpg)  
图2基于容器技术实现的网络功能节点

# 1.1资源分配与调度举例

图 $3 { \sim } 5$ 分别展示了两条不同的安全服务链 $S _ { \mathrm { 1 } }$ 、 $S _ { 2 }$ 中VNF资源分配与调度情况。图7中 $n _ { \scriptscriptstyle 1 } - n _ { \scriptscriptstyle 7 }$ 分别代表具有不同处理能力的7个网络节点， $f _ { 1 } - f _ { 8 }$ 分别代表8个不同的VNF。

a） $T _ { \scriptscriptstyle 1 }$ 时刻，安全服务请求 ${ \cal S } _ { 1 } = \{ \mathrm { f } _ { 8 } , \mathrm { f } _ { 2 } , \mathrm { f } _ { 3 } , \mathrm { f } _ { 6 } , \mathrm { f } _ { 5 } \}$ 到达，图3展示了一种可能的资源分配情况。节点 $n _ { \mathrm { { \scriptscriptstyle 1 } } }$ 同时为虚拟网络功能 $f _ { 3 }$ 和 $f _ { 8 }$ 提供资源支持。同样地，假设在一段时间后，安全服务请求 ${ \cal S } _ { 2 } = \{ { \bf f } _ { 6 } , { \bf f } _ { 8 } , { \bf f } _ { 4 } \}$ 到达，其资源分配情况如图4所示。此时，两条安全服务链由虚拟节点同时进行处理。从图中可以观察到，$S _ { \mathrm { 1 } }$ 和 $S _ { 2 }$ 的处理序列中都包含虚拟网络功能 $f _ { 6 }$ 和 $f _ { 8 }$ 。对于 $f _ { 8 }$ 来说，分别交由节点 $n _ { \mathrm { { 1 } } }$ 和 $n _ { 7 }$ 处理，无须等待，快速高效，而 $f _ { 6 }$ 则积压在节点 $n _ { 3 }$ 上，排队等待，造成不必要的处理时延。这就涉及VNF的资源优化分配问题，后文中将设计基于贪心算法的求解策略应对此问题。

![](images/e72dbb251001a27215c26aecd7c00d3276ea3f2f607ba7c9bdd75a2f17b38534.jpg)  
图3安全服务请求S1的资源分配

![](images/0c1643b4fd58263540e6daacf2a007aeca9daf2f59458e80c064f1aea9195302.jpg)  
图4安全服务请求S2的资源分配

b）图5展示了安全服务链S1和S2的资源调度时间表。其中的每一个功能 $f$ 必须按序处理，并且每一个节点在某一时段内只能处理一个特定的功能。定义符号 $P _ { i , j }$ 代表 $f _ { i }$ 在虚拟节点 $j$ 上的处理时延，其中 $1 \leq i \leq m$ ， $1 \leq j \leq n$ ， $m$ 和 $n$ 分别代表$f$ 的个数和虚拟节点的个数。本文采用假设的处理时间，表示每个节点上 $f$ 的调度情况。在 $T _ { \mathrm { l } }$ 时刻，安全服务请求 $S _ { \mathrm { 1 } }$ 到达并立刻交由 $n _ { \mathrm { { 1 } } }$ 节点进行处理。每一个后续功能需等到前序功能处理完成后才可以进行。在 $T _ { \mathfrak { z } }$ 时刻， $S _ { 1 }$ 处理完成。因此， $S _ { \mathrm { 1 } }$ 处理时间为 $T _ { s _ { 1 } } = ( T _ { 8 } - T _ { 1 } )$ ，等价于链上各个 $f$ 处理时间之合。为了阐明问题，假设安全服务请求 $S _ { 2 }$ 在 $T _ { 4 }$ 时刻到达。 $S _ { 2 }$ 中的第一个$f$ 分配在节点 $n _ { 3 }$ ，而此时节点 $n _ { 3 }$ 上已经分配了 $S _ { 1 }$ 的某个 $f$ 。因此， $S _ { 2 }$ 必须等到 $T _ { 6 }$ 时刻才可以开始工作。等待时间间隔$( T _ { 6 } - T _ { 4 } )$ 不仅增加了 $S _ { 2 }$ 的处理时间，还可能因 $S _ { 2 }$ 的其他 $f$ 长时间空闲造成资源利用率的下降。这是由上一步资源分配导致的直接后果。假设将 $S _ { 2 }$ 中的 $f _ { 6 }$ 映射到节点 $n _ { 5 }$ ，则可以有效避免资源调度过程中额外的时间开销。因此，统一协调资源分配与调度过程才能为安全服务提供保证。VNF资源调度有三种可能的情况：(a）在处理完一个功能后，立即处理下一个功能（图5中在 $T _ { 2 }$ 时刻， $S _ { 1 }$ 上的 $f _ { 2 }$ 紧接着 $f _ { 8 }$ 进行处理)；(b）一个功能需等待上一个功能处理完之后才可进行处理（图5中 $S _ { 2 }$ 在 $T _ { _ 4 }$ 时刻到达，但需等待到 $T _ { 6 }$ 时刻， $n _ { 3 }$ 才能解除占用并为其提供服务);(c）一个功能需持续等待到一个链中所有功能处理完之后才能进行处理（图5中的 $n _ { 2 }$ 节点，需等待 $( T _ { 9 } - T _ { 4 } )$ 的时间间隔才能完成处理)。后文中将资源调度问题抽象建模为FJSP并基于混合蜂群算法求解此问题。

![](images/31806cfb3d4c7ce5f307deea5b130b8db313b3de85fe7358bd11241e83bdfe9e.jpg)  
图5S1和S2的资源调度时间表

# 1.2资源分配与调度优化目标

在资源分配与调度问题中，有很多不同的优化目标。本文选取处理时间，资源成本和服务收益作为代表性指标进行分析。

1）处理时间处理时间是指某一安全服务请求的最后一个功能处理完成到服务到达的时间间隔（式（1)， $t _ { e }$ 代表完成时间， $t _ { a }$ 代表到达时间)。处理时间是两项参数的衡量指标：a)资源利用率（过高的处理时间说明服务长时间占据网络，造成较高的网络负载和资源消耗，资源利用率低下)；b）服务质量（处理时间越短，意味着服务的平均处理速度越快，服务质量越高)。

$$
{ \cal T } = t _ { e } - t _ { a }
$$

2)资源成本资源成本是指对于某一特定的安全服务请求，物理网络资源的空间存储和时间处理开销。式（2）中， $\sum _ { i = 1 } ^ { m } \delta _ { i }$ 是指某一服务链 $s$ 中所有功能 $f$ 所耗费的空间存储资源之合，$( \mathbf { t } _ { e } - \mathbf { t } _ { a } )$ 代表时间处理开销，不仅包括节点的实际处理时间，也包括节点的等待时延，常量 $\alpha$ 和 $\beta$ 分别代表两者的权重。

$$
C = \alpha \sum _ { i = 1 } ^ { m } \delta _ { i } + \beta { \left( t _ { e } - t _ { a } \right) }
$$

3）服务收益服务收益是指物理网络资源为某一特定的安全服务请求提供服务的综合收益。式（3）中，布尔变量 $\gamma _ { i , j }$ 值为1代表功能 $f _ { i }$ 分配在了节点 $j$ 上，为0反之。变量 $\rho _ { i , j }$ 则代表某一特定功能分配带来的服务收益。

$$
R { = } \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } \gamma _ { i , j } \times \rho _ { i , j }
$$

考虑到三项指标具有不同的函数优化方向，定义效用函数$U$ 作为其综合性能反映，取值为所有性能参数指标经效用函数转换后的函数值。第 $k$ 个方案的效用值计算如式（4）所示。

$$
\boldsymbol { U } _ { k } = \omega _ { k } \Big [ Y ^ { + } \left( \boldsymbol { \mathrm { r } } _ { + } ^ { k } \right) + Y ^ { - } \left( \boldsymbol { \mathrm { r } } _ { - } ^ { k } \right) + Y ^ { s } \left( \boldsymbol { \mathrm { r } } _ { s } ^ { k } \right) \Big ] , \mathrm { k } = 1 , 2 , . . . , \kappa
$$

其中： $\omega _ { \boldsymbol { k } } \ge 0$ 是缩放系数，用于调整各性能参数的影响因子；$Y$ 为转换函数； $\boldsymbol { r }$ 是转换函数 $Y$ 的自变量。第一个参数定义关于 $\boldsymbol { r }$ 的单增函数 $Y ^ { + }$ ，第二个参数定义关于 $\boldsymbol { r }$ 的单减函数 $Y ^ { - }$ ，对于时间性能参数，单独定义关于 $\boldsymbol { r }$ 的减函数 $Y ^ { s }$ 。此处，对性能参数进行归一化处理，得到取值在[0,1]之间的归一化参数 $\tilde { r } ^ { k }$ （式（5））。

$$
\widetilde { r } ^ { k } = \frac { r ^ { k } } { \operatorname* { m a x } { ( \mathrm { r } ^ { k } ) } } , \widetilde { r } ^ { k } \in [ 0 , 1 ] , \mathrm { k } = 1 , 2 , . . . , \kappa
$$

参考效用函数理论，给出效用转换函数如式（6）所示。

$$
\begin{array} { r l } & { T = \sqrt { T ^ { + } = e ^ { - ( 1 - t ^ { k } ) t ^ { k } } , 0 < r ^ { k } < 1 , k = 1 , 2 , . . . , K } } \\ & { T = \{ T ^ { - } = \{ \begin{array} { l l } { e ^ { - \operatorname { r } ^ { k } / ( 1 - t ^ { k } ) } , 0 < r ^ { k } < 1 } \\ { 0 , r ^ { k } = 1 } \\ { 0 , r ^ { k } = 1 } \end{array} , k = 1 , 2 , . . . , K  } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \end{array}
$$

# 2 基于贪心算法的资源分配方案

# 2.1 算法动机分析

本文提出一种针对VNF 资源分配的贪心求解算法。根据不同安全服务请求，将算法中贪婪因子变量 $H$ 划分为三种类型：a）最短处理时间（greedy least processing time,GLPT)；b）最快可用时间（greedy fast availability time,GFAT)；c）最大存储空间（greedy maximum memory space,GMMS）。其中，GLPT 是指将VNF分配至可提供最短处理时间的节点，该分配策略可满足基于处理时间计费的安全服务类型；GFAT是指将VNF分配至可最快提供服务，等待队列最短的节点，该分配策略可满足迫切的用户安全服务需求；GMMS是指将VNF分配至拥有最大可用存储空间的节点，该分配策略可以平衡网络的实际负载，提升网络综合性能。

# 2.2算法流程及算法描述

算法1给出了该算法的具体过程。可以看出该算法分为以下几步：

a）备份物理网络状态及函数初始化。为降低资源分配过程中因差错造成的损失，算法首先对物理网络状态进行备份并对安全服务链S、节点 $N$ 和贪婪因子变量 $H$ 进行初始化赋值。

b)扫描节点并分配资源。对于 $N$ 中的任意一个节点 $j$ ，利用式（9）计算其处理结束时间，若节点空间存储和时间处理均满足约束条件(式(10))，则将该节点加入可用节点集合 $N ^ { ' }$ ，否则，扫描下一节点。待扫描完成后，判断集合 $N ^ { ' }$ ，如果恒为空，说明资源分配失败，重置备份的物理网络状态。

c）按贪婪因子排序。对不同的贪婪因子 $H$ ，进行节点排序，依次挑选序首节点进行资源分配，至此，算法结束。

算法1VNF 资源分配贪心求解算法 算法：贪心求解算法 输入： S,N,H。

输出: [fi,ni]。   
(1) Start   
(2) Backup Substrate Network State   
(3) for VNF $f _ { i } \in S$ do   
(4) Initialize: Capable Node Set $N ^ { ' } = \phi$ Ⅱ初始化 (5) （20 $I f ( i = = I ,$ then   
（204 $t _ { i - 1 } = t _ { a }$ （204号   
(6) end $i f$ （20   
(7) for Node $j \in N$ do   
(8) $t _ { e } = p _ { i , j } + \operatorname* { m a x } ( \pi _ { j } , \mathbf { t } _ { i - 1 } )$ Ⅱ计算结束时间 (9) $i f ( ( \gamma _ { i , j } = 1 ) \land ( \rho _ { \operatorname* { m a x } } \geq \rho _ { i , j } ) \land ( \mathrm { t } _ { e } \leq \mathrm { t } _ { l } ) )$ then N=NUnj   
(10) $e n d i f$ （204号   
(11) end for   
(12) if $N ^ { ' } \equiv \phi$ then   
(13)   
(14)   
(15) return   
(16) end if   
(17) Sort $N ^ { ' }$ according to $H$ Ⅱ按贪婪因子排序 (18) Select the top node ${ n } _ { j } ^ { * }$ from $N ^ { ' }$ （204   
(19) Allocation the function $f _ { i }$ onto $n _ { j } ^ { * }$ （204号   
(20) $\mathrm { S } e t ~ t _ { i } = \operatorname* { m a x } ( \pi _ { j } , \mathbf { t } _ { i - 1 } )$ （204号   
(21) Update $\pi _ { j }$ and $\mathbf { t } _ { i - 1 }$   
(22) end for   
(23) ResourceAllocation Completed End

# 3 基于混合蜂群算法的资源调度方案

# 3.1 算法动机分析

FJSP是经典作业车间调度问题的扩展，是复杂的组合优化问题。FJSP可描述为：加工系统有 $n$ 个工件在 $m$ 台设备上加工,每个工件包含 $n _ { i }$ 个预先确定加工顺序的工序，每个工序可在多台设备上加工，且加工时间随着设备性能的差别而不同。调度目标是在设备能力约束和工序约束下，将工序分配到设备，并确定在每台设备上工序的加工顺序。经对比分析，本文中VNF资源调度问题可以抽象建模为FJSP，其数学模型涉及参数定义如下：

$M = \{ \mathbf { M } _ { k } \ | 1 \leq k \leq m \}$ ,表示节点集;$J = \{ \boldsymbol { \mathrm { j } } _ { i } | 1 \leq i \leq n \}$ ,表示安全服务链集;$O _ { i } = \{ { \bf O } _ { i j } | 1 \leq j \leq n _ { i } \}$ ,表示安全服务链 $J _ { { _ i } }$ 的服务功能集;$M _ { _ { i j } } = \{ \mathbf { M } _ { _ k } \ : | \ : \mathbf { X } _ { i j k } = 1 \}$ ,表示安全服务链 $J _ { i }$ 的服务功能 $O _ { i j }$ 的可用节点集;$M _ { \mathit { i j k } }$ 表示服务功能 $O _ { i j }$ 在节点 $\boldsymbol { M } _ { \boldsymbol { k } }$ 上的加工时间;$S _ { i j k }$ 表示服务功能 $O _ { i j }$ 在节点 $\boldsymbol { M } _ { \boldsymbol { k } }$ 上的开始加工时间;$E _ { i j k }$ 表示服务功能 $O _ { i j }$ 在节点 $\boldsymbol { M } _ { \boldsymbol { k } }$ 上的完工时间;$F M _ { k }$ 表示所有安全服务链在节点 $\boldsymbol { M } _ { \boldsymbol { k } }$ 上的完工时间;$F M$ 表示所有安全服务链的最后完工时间;$X _ { i j k } = \left\{ { 1 \atop 0 } \right.$ 服务功能 $O _ { i j }$ 由节点 $M _ { k }$ 处理其他 =$R _ { i j e g k } = \left\{ \begin{array} { l l } { 1 } \\ { 0 } \end{array} \right.$ $O _ { i j }$ 与 $O _ { e g }$ 同由节点 $M _ { k }$ 处理， $O _ { i j }$ 先处理其他

以最大化效用函数值 $U _ { \boldsymbol { k } }$ (式(4))为目标：

$$
\mathfrak { m a x } \sum _ { k = 1 } ^ { \kappa } U _ { { \scriptscriptstyle K } }
$$

对以上问题作以下约束：

a)互斥性约束

$$
\left\{ \begin{array} { l } { { E _ { i j k } - E _ { e g k } \geq M _ { e g k } } } \\ { { R _ { i j e g k } = 1 , X _ { i j k } = X _ { e g k } = 1 } } \end{array} \right.
$$

表示某个节点同一时间只能处理一个服务功能。

b)连续性约束

$$
\left\{ \begin{array} { l l } { E _ { i j k } - S _ { i j k } = M _ { i j k } } \\ { X _ { i j k } = 1 } \end{array} \right.
$$

表示服务功能的处理过程不可中断。

c)次序性约束

$$
\left\{ \begin{array} { l } { { \ S _ { i j k } - E _ { i ( j - 1 ) \mathrm { h } } \geq 0 } } \\ { { X _ { i j k } = X _ { i ( j - 1 ) \mathrm { h } } = 1 } } \end{array} \right.
$$

(10)

表示同一安全服务链的服务功能间有顺序约束，不同安全服务

链间不存在服务功能顺序约束。

# 3.2算法架构

HBC的蜂群行为模型来自于KARABOGA建立的蜂群觅食行为的最小化模型[15]，包括食物源、雇佣蜂、观察蜂和侦察蜂四个组件。模型中，食物源代表问题的不同解，食物源的收益率（花蜜的数量）代表解得质量；雇佣蜂负责在一定时间内持续访问某个食物源及其附近区域；观察蜂负责收集雇佣蜂带来的食物源信息，以一定概率接纳对方并互相评估，保留优秀个体；侦察蜂负责随机搜索新的食物源，三类蜂群通过协作实现寻优。

图6为混合蜂群算法的主体框架。主算法分为种群初始化算法、雇佣蜂算法、观察蜂算法和侦察蜂算法四个部分，包括种群规模SN、迭代次数mcycle、调节参数rf和领域规模nscale四个参数。种群规模SN包含雇佣蜂和观察蜂两类，各占种群数量的一半；迭代次数mcycle控制算法结束条件；调节参数用于协调算法的局部和全局搜索能力，初始值较小，算法过程中，随迭代次数的增加逐渐变大，以保证算法收敛性；领域规模nscale控制领域解得产生范围，初始值较大，是为提高蜂群的解空间遍历能力，随迭代次数增加逐渐变小，目的是缩小搜索范围，对较优解进行精细搜索。

![](images/560e15265c17ae4c3619f32f31cc8413447f55ac9620fcb1b729768127ea32bf.jpg)  
图6混合蜂群算法的主体框架

# 3.3算法详细设计

# 3.3.1种群初始化

应用于生产调度问题中的传统蜂群算法，多通过逐点遍历形成完整的调度方案，并进行全过程循环操作[16,17]。该方法计算量大，受种群规模影响严重，且逐点寻优易使算法早熟，陷入局部最优。因此，本文采用蜂群优化（bee colony optimization,BCO）[18]结合随机方法的方式，分别产生雇佣蜂和观察蜂初始种群，既提高了搜索效率，又增强了算法的全局搜索能力。

1）蜂群优化算法

BCO算法主要包括前移和回顾两类操作。前移操作更新每个雇佣蜂编码，回顾操作根据概率丢弃部分雇佣蜂，并选择其他雇佣蜂替代。图7所示为BCO算法流程。其中step的取值范围为1\~SN/2，当前雇佣蜂丢弃概率 $P _ { d _ { c } }$ 取值如式(11)所示。

$$
P _ { _ { d _ { c } } } = e ^ { - ( \mathrm { \ddot { \mathrm { H } t } } _ { c } - \mathrm { \ddot { \mathrm { H } t } } _ { b e t } ) }
$$

其中： $f { { \ddot { \imath } } _ { c } }$ 为当前雇佣蜂适应度； $\it { f i t } _ { \it { b e s t } }$ 为当前种群的最好适应度。最后生成雇佣蜂群 $E S \{ \mathrm { X } _ { i } \} ( \mathrm { i } = 1 , 2 , . . . , \mathrm { S N } / 2 )$ ，并为 $E S$ 初始化数组arraylO，记录 $X _ { i }$ 未更新的代数。

![](images/505c7af30717b11c1ecdc59c7249c190c7cf84c44f81df723de1ed03130a4cd7.jpg)  
图7BCO 算法流程

2）随机方法

随机方法以随机数组和随机数组合的方式直接生成整段编  
码，步骤如下：a)对每个观察蜂，将随机生成长度为服务功能数的数组作  
为服务功能段编码；b)对于上述每一个服务功能，随机选择处理节点，组成节  
点段编码;c)遍历观察蜂，建立种群 $O L S \{ \mathrm { O L } _ { i } \} ( \mathrm { i } = 1 , 2 , . . . , \mathrm { S N } / 2 )$ ：d)为OLS初始化数组array2O，记录 $O L _ { i }$ 未更新的代数。

3.3.2雇佣蜂觅食算法

雇佣蜂通过在领域内觅食产生新解。针对FJSP问题，本文采用改进领域解生成方法更新种群，建立雇佣蜂觅食算法ForagingO,步骤如下：

a) $\forall X _ { i } ( \mathrm { i } = 1 , 2 , . . . , \mathrm { S N } / \ : 2 )$ ，Neighbor $\cdot ( \mathbf { X } _ { i } )$ )生成领域解 $X _ { j }$ ;b $\scriptstyle , \forall X _ { j } ( \mathfrak { j } = 1 , 2 , \dotsc , \mathrm { S N } / 2 )$ ，比较 $X _ { i }$ 和 $X _ { j }$ 的适应度值，进行贪婪选择；

c)更新arraylO，若满足调节参数rf，则执行侦察蜂算法Scout $( \mathbf { X } _ { i } )$ 。

领域解更新算法Neighbor()根据领域规模nscale，随机选取 $X _ { i }$ 上两对服务功能码位进行交换，将互换后的服务功能重新选择分配节点，并重复上述过程nscale次。

# 3.3.3观察蜂算法

采用观察蜂算法，在两种蜂群中进行信息交换。对交互后的观察蜂群采用领域更新算法Neighbor()，不断缩小领域范围，提高算法精度。建立观察蜂算法Observer()，步骤如下：

a) $\forall O L _ { i } ( \mathrm { i } = 1 , 2 , . . . , \mathrm { S N } / 2 )$ ，根据适应度轮盘赌选择 $X _ { i }$ 。

b)如果 $X _ { i }$ 较优，则以 $X _ { i }$ 替换 $O L _ { i }$ 。

c)如果 $O L _ { i }$ 较优，则根据式（11）计算的概率选择是否保留$X _ { i }$ ，其中 $\mathcal { \displaystyle f l } _ { b e s t }$ 为 $O L _ { i }$ 适应度， $f { { \ddot { u } } _ { c } }$ 为 $X _ { i }$ 适应度。

d)更新 arrayl(和array2(。

e)如果arrayl满足 $r f$ 条件，则对 $X _ { i }$ 进行侦察蜂操作Scout $( \mathbf { X } _ { i } )$ ；如果array2满足 $r f$ 条件，则对 $O L _ { i }$ 进行侦察蜂操作$S c o u t ( \mathbf { O L } _ { i } )$ 。

f)对 $O L _ { i }$ 执行领域更新算法Neighbor $\left( \mathbf { O L } _ { i } \right)$ ），生成领域解$O L _ { i } ^ { * } = N e i g h b o r ( \mathrm { O L } _ { i } ) \ _ { \circ }$ （2号

g)评估领域解，判断是否更新 $O L _ { i }$ 。

# 3.3.4侦察蜂算法

侦察蜂算法Scout(）由调节参数 $\boldsymbol { r f }$ 触发，当雇佣蜂 $X _ { i }$ 或观察蜂 $O L _ { i }$ 对应的array值等于 $r f$ 时，产生随机解替代原解。随机解采用随机种群的初始化方法生成。

# 4 仿真实验与结果分析

# 4.1实验环境

为验证算法效果，利用Java语言开发独立事件模拟器，通过 MATLAB 软件评估本文所提算法。每次资源分配和调度事件均服从泊松分布。本文定义10 个不同的网络功能并将其编号为1-10，每一个安全服务请求都由其中的一个或多个功能组成。设定每5个时间单元到达一项安全服务，且每项服务功能独占一个节点的资源直至处理完成。除非特殊说明，实验中的参数均在满足均匀分布的条件下从最大最小值之间随机抽取（表1)。每个独立的实验过程涉及安全服务链到达、资源分配和调度以及处理结束后服务离开三个步骤。

表1实验参数范围  

<html><body><table><tr><td>参数（单位）</td><td>最小值</td><td>最大值</td></tr><tr><td>节点数（个)</td><td>10</td><td>50</td></tr><tr><td>节点存储空间 (兆)</td><td>10</td><td>20</td></tr><tr><td>单个节点处理功能数（个)</td><td>1</td><td>7</td></tr><tr><td>单个功能处理时间 (毫秒)</td><td>100</td><td>500</td></tr><tr><td>单个功能存储空间需求 (兆)</td><td>1</td><td>2</td></tr><tr><td>安全服务链长度（个）</td><td>3</td><td>10</td></tr><tr><td>安全服务处理时间（毫秒)</td><td>1000</td><td>5000</td></tr></table></body></html>

# 4.2算法测试及结果分析

考虑到VNF资源分配与调度是一个连续的过程，资源分配的结果将直接影响资源调度的性能。因此，本文对贪心算法（GLPT、GFAT和GMMS）和混合蜂群算法（HBC）进行组合测试。同时，为验证种群初始化方法对本文所提混合蜂群算法性能方面的提升，将其与传统蜂群算法对比进行验证。实验结果如图 $8 \sim 1 2$ 所示。

1）平均等待时间和平均处理时间实验结果分析图8和9分别展示了由独立事件模拟器产生的1000条安全服务链的平均等待时间和平均处理时间。等待时间是指某一服务功能到达直到其开始进行处理的这一段时间间隔，平均等待时间是对某一安全服务的所有服务功能的等待时间加合求均值。完成时间是由所有服务功能处理时间和服务等待时间共同决定的。从图8中可以观察到，GLPT-HBC 算法相较于其他算法平均等待时间较长，这是因为GLPT算法倾向于将服务功能分配在能够最快处理的节点上，这将导致拥有最短处理时间的节点过载，易出现排队等候，从而造成较高的平均等待时间。GMMS-HBC 算法倾向于将服务功能分配在拥有最低负载的节点上，降低了服务执行和等待时间。GFAT-HBC 算法相较于其他算法具有最佳的时间性能表现，是因为GFAT-HBC算法的优化目标就是最小化处理完成时间，而等待时间恰是处理时间中的一部分。因此，图9中的实验结果与图8具有相似性和一致性。

2）总资源成本和总服务收益实验结果分析图10和11分别展示了资源分配和调度的总资源成本和总服务收益。可以看出图中的数值是不断累积的，这是因为每经过一次成功的资源分配与调度，都会计算一次资源成本（式（2)）和服务收益（式(3))，并累加在先前的数值之上。从图10中可以观察到，GLPT-HBC算法资源成本最高，GFAT-HBC算法资源成本最低，并且三种算法增长速率几乎相同。造成三者之间轻微差异的原因在于三种算法的平均等待时间不同。从图11中可以观察到，随着安全服务请求的增长，GFAT-HBC算法的服务收益不断增加且高出另外两种算法约 $40 \%$ ，而GMMS-HBC和GLPT-HBC算法的增长速率几乎相同。从长远角度来看，GFAT-HBC算法可为服务供应商提供更大的收益。

3）蜂群算法比较分析图12对比了仅采用随机方法生成初始种群的传统蜂群算法和采用种群初始化方法生成种群的混合蜂群算法。算法均在种群规模50、迭代次数50、其他参数一致的情况下进行求解，且均求解出最优解7。经对比分析，本文所提混合蜂群算法在提高初始解的质量的同时提高了算法的收敛速度。

# 5 结束语

针对安全服务链中VNF 资源分配与调度问题，本文分别基于贪心算法和混合蜂群算法提出解决方案，设计了三种不同应用场景下的贪心算法以应对用户多样化的安全服务需求，仿真实验结果验证了三种算法不同的处理能力，创新性地提出了基于种群初始化方法的混合蜂群算法解决VNF调度问题。实验结果表明，该算法相较于传统蜂群算法具有更快的收敛速度，适于满足大规模的网络需求。目前，安全服务链中虚拟网络功能的相关研究正不断兴起，下一步将继续完善本文研究，并深入开展服务链实验验证。

![](images/75d301e1ba278afbd5e93418d369f43456e5afe81c4eaf21e330dcc94137e192.jpg)  
图8平均等待时间

![](images/17177af1fa0a4fd9e35da64140a6826870057a8142df0e5f8511ef5b888d8efd.jpg)  
图9平均处理时间

![](images/75c6e252a6e84f03e5e7402e9ae4e7ec2f3d4d99c54f942b5a4ccda436412a43.jpg)  
图10总资源成本

![](images/330880e1328d75018067cbcfece470a1e05c9e234889195fd1daaffea9b3f27a.jpg)  
图11总服务收益

![](images/76cc781d5c8363ca9c8fbda5a2ba09ef666fdd59337324a77f313cde8943eb76.jpg)  
图12蜂群算法比较

# 参考文献：

[1]黄韬，刘江，霍如，等．未来网络体系架构研究综述[J].通信学报, 2014,35 (8): 184-197.   
[2]兰巨龙，程东年，胡宇翔.可重构信息通信基础网络体系研究[J].通 信学报,2014(1): 128-139.   
[3]Dave T.OpenFlow:enabling innovation in campus networks [J].ACM Sigcomm Computer Communication Review,2008,38 (2): 69-74.   
[4]左青云，陈鸣，赵广松，等．基于OpenFlow的 SDN技术研究[J]．软件 学报,2013 (5):1078-1097.   
[5] 熊钢，胡宇翔，段通，等．一种软件定义网络的安全服务链动态组合机 制[J]．电子与信息学报,2016,38(5):1234-1241.   
[6]Liu J,Li Y,Wang H,et al. Leveraging software-defined networking for security policy enforcement [J]. Information Sciences An International Journal,2016,327 (C): 288-299.   
[7] Clayman S,Maini E,Galis A,et al. The dynamic placement of virtual network functions [C]//Proc of IEEE Network Operations and Management Symposium.2014:1-9.   
[8]CHIOSI M, CLARKE D, WILLIS P, et al. Network functions virtualizationintroductory white paper [C]// Proc of SDN and OpenFlow World Congress. 2012. : 1-5.   
[9]Herrera JG,Botero JF. Resource allocation in NFV: a comprehensive survey[J]. IEEE Trans on Network & Service Management,2017,13 (3): 518-532.   
[10] Riera JF, Hesselbach X,Escalona E,et al.On the complex scheduling formulation of virtual network functions over optical networks [C]// Proc of IEEE International Conference on Transparent Optical Networks.2014: 1-5.   
[11] Ferrer Riera,J,Escalona,E,Batalle,J,et al.Virtual network function scheduling:concept and challenges [C]// Proc of IEEE International Conference on Smart Communications in Network Technologies.2014: 1-5.   
[12] MijumbiR, Serrat J, Gorricho JL,et al. Design and evaluation of algorithms for mapping and scheduling of virtual network functions [C]//Proc of IEEE Network Softwarization. 2015: 1-9.   
[13] Fischer A,Botero JF,Beck M T, et al. Virtual network embedding: a survey [J].IEEE Communications Surveys & Tutorials,2013,15(4):1888-1906.   
[14]RabbaniMG,PereiraER,PodlesnyM, etal.On tackling virtual data center embedding problem [C]//Proc of IFIP//IEEE International Symposium on Integrated Network Management.2013:177-184.   
[15] Karaboga D.An idea based on honey bee swarm for numerical optimization, Technical Report-TR06 [R].2005.   
[16] Chong C S,Low MYH, SivakumarAI, et al. Using a Bee colony algorithm for neighborhood search in Job-Shop scheduling problems [C]// Proc of European Conference on Modelling& Simulation:Simulations in United

Europe. 2008.

[17] WongLP,ChiYP,Low MYH,et al.Bee colony optimization algorithm with big valley landscape exploitation for Job-Shop scheduling problems [C]//Proc of Conference on Winter Simulation．Winter Simulation Conference.2008:2050-2058.   
[18] Teodorovic D,Lucic P,Markovic G,et al.Bee colony optimization: principles and applications [C]//Proc ofIEEE Seminar on Neural Network Applications in Electrical Engineering.20o7:151-156.