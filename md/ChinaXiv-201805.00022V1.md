# 5G网络切片中基于离散粒子群和Kruskal算法的 跨域虚拟网络映射\*

王晓雷，陈强，刘彩霞(国家数字交换系统工程技术研究中心，郑州 450001)

摘要：5G移动通信网将租用多个基础设施提供商的数据中心等资源共同合作构建网络切片，针对如何高效地进行跨域虚拟网络映射这一网络切片全生命周期管理中的关键问题，提出一种两阶段的跨域映射策略 DPSO-K。首先基于资源竞价统筹考虑节点资源和域间带宽资源，然后提出基于优化离散粒子群算法的跨域虚拟网络映射，可以有效提高寻优能力；对于开销相对较小的域内映射来说，提出一种基于 Kruskal最小生成树的快速算法，旨在缩短切片实例化时间，减小业务上线速度。相比于传统先进行虚拟网络映射划分请求再统一映射链路的方法，该策略在划分请求中考虑域间带宽开销，在映射链路中关注重点链路的映射，采用集中管理、分布控制的方式实现物理网络资源的有效利用。实验结果表明该算法能够以更小的额外开销、更短的划分时间实现更高的接受率。

关键词：5G；网络切片；虚拟网络映射；跨域映射中图分类号：TP393.03 doi:10.3969/j.issn.1001-3695.2017.10.1010

# Cross-domain virtual network mapping based on discrete particle swarm optimization and Kruskal algorithm in 5G network slicing

Wang Xiaolei, Chen Qiang†,Liu Caixia (National Digital Switching System Engineering&Technology Research Center,Zhengzhou 450o01,China)

Abstract:5Gmobilecommunicationnetwork hiremoredatacentersofinfrastructure provider tocooperate toconstructnetwork section,Aimigtheefcientlycrossdomainvirtualnetworkmapping whichisakeyprobleminnetworklifecyclemanagement in network slice,proposeda two stagecrossdomain mapping strategy,DPSO-K.Firstly，basedon theresource bidding, considered the resource of nodes and the bandwidth between domains,and proposed aoptimized discrete particle swarm optimization (PSO)algorithm for inter domain virtual network mapping,whichcan efectively improve the searching ability; then,proposedafastalgorithm basedonKruiseKarle minimum spanningtre toreduce thecostofintra domain mapping,which reduces the timeofragmentinstantiationand shortens theon-linespeedofservice.Thecomparingtothetraditionalmethodof thefirst virtual network mappingrequest divisionunified maping link,the strategyconsidered thebandwidthoverhead inthe requestdivision,ndpayedtentiontokeylinkinmapping mapinglink,modeofcentralizedmanagement,distributedontrol, to realize the efectiveuseof physicaland cyber source.Experimentalresults showthatthis algorithmcan achieve higher acceptance rate with less overhead and less partitioning time.

Key Words:5G; network slicing; virtual network embedding; Cross-domain mapping

# 0 引言

网络切片是5G时代的理想网络架构，被视为应对互联网OTT（OverTheTop）业务价值碾压、实现移动网价值提升的重要途径。网络切片可以让运营商在一个硬件基础设施中切分出多个虚拟的端到端网络，相互隔离地共享物理网络资源，也可以基于多个基础设施提供商的硬件设施构建一个逻辑上的端到端网络，联合地提供对用户透明的业务承载。对于一种业务服务，底层的基础设施可由多家设备商联合提供，且地理部署上不再集中于某一个机房，资源部署呈现异构性和分布性特点[1]。

虚拟网络映射（VirtualNetworkEmbedding，VNE）是网络切片生成过程中的一个重要步骤，其目的是在物理网络中分别为虚拟节点和虚拟链路找到满足其映射约束的物理节点和物理路径[2]。单一网络场景下的虚拟网络映射一般假定已知该网络中全部的底层资源信息，相关的映射策略已经较为成熟[3\~7]。但在5G场景下，一个端到端的网络切片贯穿接入网、核心网以及互联网，对于垂直行业的定制网络来说，服务提供商（ServiceProviders，SPs）由于资源类型、价格等限制原因，将不得不租用多个基础设施提供商（InfrastructureProviders,InPs）的网络基础设施，然后利用多个InPs的资源共同合作构建切片，不同InPs的子网构成多个不同的自治域。不同的自治域间由于商业利益等原因，相互之间信息不公开，这导致单域映射算法不适用于网络切片中虚拟网络的跨域映射。与单域虚拟网络映射相比，多域虚拟网络映射的难点在于：a)由于多域网络的规模可能很大，解决单域问题的算法会使得系统产生巨大的信令开销和内存开销;b)由于保密性等原因，本地控制器可能只选择性的提供部分域内信息，而全局控制器只能根据这些信息进行虚拟网络的映射。

对于跨域映射国内外学者进行诸多有益的研究，现有跨域虚拟网络映射主要有分布式和集中式两种方式。分布式跨域虚映射通过 SPs与InPs及InPs与 InPs 间的资源协商来实现，能够充分尊重SPs和InPs双方的意愿且有良好的可扩展性。但分布式方法在协商过程中会引起额外的网络传输代价，又由于缺乏对全局信息的掌握，所以并不能得到跨域VN映射的最优解；而集中式方法的特点是出现了虚拟网络提供商(VirtualNetwork Provider，VNP)[8]，主要功能是简化 SPs 与InPs 的消息交互和供需匹配过程，在搜集基础设施信息的基础上按照预定的规则和策略求解跨域映射方案。文献[9]根据多域网络中的边界节点和域间链路的价格情况，提出一种基于元启发式算法的虚拟网络请求划分策略。Dietrich 等人根据底层网络边界节点等信息为基础，提出一种确切式虚拟网络请求划分算法[10],该方法创新点在于提出了更精细的问题模型且并有效降低额外开销，但算法复杂度大大提升，因此难以适用于大规模的网络情况。以上这些集中式跨域 VN 映射一般分为两个阶段：a)虚拟网络划分阶段，InPs以最小化映射开销为目标，从其匹配的集合中为每个虚拟资源选择最适合的映射目标，选择结果会将虚拟网络划分为多个虚拟子网，并确定承载每个虚拟子网的InPs，至此，跨域虚拟网络映射已化归为多个单一自治域场景下的虚拟网络映射问题。Houidi等人[1]第一次从理论上证明了虚拟网络划分是NP-Hard问题，并基于边界节点间全连接的物理网络拓扑提出了一种虚拟网络划分的启发式算法;b）虚拟子网映射阶段，VNP将各虚拟子网请求转发给相应的InPs，各InPs可采用已有的单域映射方法求解虚拟子网映射，主要有整数线性规划、智能算法和启发式算法等解决策略。

现有研究的集中式跨域映射策略的假设前提是在不同数据中心，实例化虚拟网络功能所消耗的节点资源相同且InPs对这些资源的报价相同，并在虚拟网络划分问题简单抽象为一个装箱问题，将一个子域抽象为一个点。这种假设在5G网络场景中并非十分契合，从节点资源角度，实际情况下各个InPs给SPs的资源报价往往是不同的；从链路资源角度，每个子域一般有多个出口节点，选择不同的出口节点将影响资源开心，不能简单地将子域抽象为一个点。针对上述跨域映射存在的问题，本文提出一种统筹考虑节点资源和链路资源的跨域映射算法DPSO-K。该映射方案包括两部分：域间映射部分和域内映射部分。因为不同自治域之间的信息不公开，故先只考虑节点资源和域间链路资源的开销进行资源分配和功能部属，再采用分布式映射机制进行域内映射。这种两步走简化的合理性在于，该问题中域间链路开销是主要开销，而域内映射开销相对较小[12]所以域内部分映射可采取简洁的快速算法进行求解。本文的贡献主要包括:a）提出了一种基于粒子群算法的域间映射算法。该算法将VN划分方案以矩阵形式编码，从多个初始解开始进行迭代搜索，逐步逼近全局最优解;b）提出了一种基于kruskal最小生成树的域内近似算法。该算法在最小生成树基础上进行修正，快速得到符合虚拟网拓扑约束的映射结果。

# 1 网络切片跨域映射架构与模型

# 1.1问题描述

在传统的多域虚拟网络映射问题中，服务提供商在建立一个跨域的虚拟网络请求时，需要不断的与多个InPs进行商榷。5G 核心网络将采用SDN架构，因此在基于软件定义的5G 网络切片中，控制平面和数据平面将完全分离，网络架构的进步更有利于提高转发效率，实现资源统一管理。网络切片的集中式跨域映射网络架构如图1所示：

a)基础设施提供商InPs：包括接入网InPs、核心网InPs以及因特网InPs等。

b)管理与编排器（Managementand Orchestration，MANO）：接收各个自治域服务提供商的虚拟网络请求，并根据从各个自治域上传的网络信息以及底层物理资源状态，进行虚拟网络请求的划分和映射。

c)虚拟网络提供商VNP：由多个虚拟机(VirtualMachine,VM)以及虚拟设施管理器(VirtualInfrastructureMonitor,VIM)组成，一个本地的 VIM 管理一个自治域，计算出需要上传给MANO的信息，并且分配虚拟资源给虚拟网络请求。VNP和InPs合称为虚拟网络功能基础设施（virtualnetworkfunctioninfrastructure，NFVI)。

d)服务提供商SPs：由运营/业务支撑系统（OSS/BSS）向物理网络中的MANO发送虚拟网络请求。

为方便描述虚拟网络映射问题，现对图1进行简化和抽象。如图2所示，为三子域的跨域映射物理网络示意图。假定有三个InPs构建了三个网络域，其中N类节点为内部节点，其上可以构建虚拟机（或者容器）承载虚拟网络功能，B类节点是边界节点，不同网络域之间进行信息交互的网络关口。则跨域映射的目标是选择合适的N类节点承载虚拟网络功能，并选择合适的B类节点和链路承载虚拟网络链路，在满足虚拟网络请求的前提下，使物理网络的节点计算开销和链路带宽开销最小。

![](images/fe008403c1677af30721fcd97512c5c2a1509b17e7824a334c1080885781afad.jpg)  
图1集中式跨域映射网络架构示意图

![](images/2327a7831640904fb4712159aa32612eacd36566817c54e58ac5a338fd01c6df.jpg)  
图2三子域的跨域映射物理网络示意图

# 1.2模型建立

用一个有权无向图 $G _ { _ s } = ( N _ { _ s } , E _ { _ s } )$ 来表示底层物理资源网络，底层物理网络节点 $n _ { s } ^ { i } \in N _ { s }$ 上总的计算资源为 $c ( n _ { s } ^ { i } )$ ，底层物理节点 $n _ { s } ^ { i }$ 和 $n _ { s } ^ { j }$ 之间物理链路的可用带宽为 $b ( n _ { s } ^ { i } , n _ { s } ^ { j } )$ 。类似于底层物理资源网络，虚拟网络作为底层物理网络的一个子图，同样用一个有权无向图 $G _ { \nu } = ( N _ { \nu } , E _ { \nu } )$ 来表示，其中底层物理网络节点的集合表示为 $N _ { \nu } = \{ n _ { \nu } ^ { 1 } , n _ { \nu } ^ { 2 } , . . . , n _ { \nu } ^ { n } \}$ 。底层物理网络链路的集合表示为 $E _ { \nu }$ 。虚拟网络请求映射到底层物理资源网络上可以被表示为VNE:G=(N,E)→G =(N,E)

在映射算法执行过程中，剩余的可用CPU 资源表示为$R ( n ^ { s } ) = \sum _ { n _ { s } \in N _ { s } } c ( n _ { s } ) - \sum _ { n _ { \nu } \in M ^ { n } _ { \nu } } c ( n _ { \nu } )$ ，即全部CPU资源 （ $\sum _ { n _ { s } \in N _ { s } } c ( n _ { s } )$ 减去已被占用的CPU 资源 $\sum _ { n _ { \nu } \in M ^ { n _ { \nu } } } c ( n _ { \nu } )$ 。其中 ${ \mathbf { \Omega } } _ { M _ { \nu } }$ 表示当前映射的虚拟网络节点集合。类似地，剩余可用带宽资源$R ( e ^ { s } ) = \sum _ { e _ { s } \in E _ { s } } b ( e _ { s } ) - \sum _ { e _ { \nu } \in M ^ { e } _ { \nu } } b ( e _ { \nu } )$ ，即总链路带宽 $\sum _ { e _ { s } \in E _ { s } } b ( e _ { s } )$ 与已占用带宽 $\sum _ { \stackrel { \mathcal { P } _ { \nu } \in M ^ { e } } { \nu \in M ^ { e } \nu } } b ( e _ { \nu } )$ 的差值。虚拟网络的映射存在资源约束，即底层网络需要有足够的剩余资源承载虚拟网络，表征为：

$$
\begin{array} { c }  { { \displaystyle c ( n ^ { V } ) \leq R _ { _ N } ( M _ { _ N } ( { \bf n } ^ { V } ) )  \} } } \\  { { \displaystyle b ( { \bf e } ^ { V } ) \leq R _ { _ E } ( M _ { _ E } ( { \bf e } ^ { V } ) ) \} } } \end{array}
$$

由于数据中心中切片功能部署的现实需求，部分节点的映射除了资源约束之外约束表征为

$$
L o c ( n ^ { s } , n ^ { \nu } ) = \left\{ { 1 , \atop { \Big \{ 0 , } }  \right. \ \overline { { { \mathbb { H } } } } \frac { { \vec { \nu } } \cdot { \vec { \mu } } } { { \overbrace { { \mathbb { H } } } } } \big \} \frac { { \underset { \mathrm { H } \neq } { \arg } } } { { \overbrace { { \mathbb { H } } } } }
$$

如果嵌入满足约束条件，那么称之为一个有效的映射。对于一个虚拟请求可能存在多个有效映射，本文的优化目标是最小化整体开销，提高资源利用率。根据文献[13]中的模型，本文中将跨域虚拟网络映射的开销定义为：

$$
\mathrm { C o s t } ( G ^ { \nu } ) = \alpha \sum _ { n ^ { \nu } \in N ^ { \nu } } C ( n ^ { \nu } ) + ( 1 - \alpha ) \sum _ { e ^ { \nu } \in \mathrm { E } ^ { \nu } } B ( \mathrm { e } ^ { \nu } ) \bullet l e n g h ( e ^ { \nu } )
$$

# 2 DPSO-K算法描述

DPSO-K算法先进行域间映射，再进行域内映射。首先进行的域间映射是主要开销的来源，是DPSO-K算法主要的优化对象和工作重点。然后在域间映射的基础上对自治域内的资源进行映射，开销相对较小，采取近似算法进行快速求解，保证业务能够迅速上线。

# 2.1域间部分映射算法

域间部分算法主要为了解决虚拟网络划分问题。该部分算法基于优化离散粒子群算法(DiscreteParticleSwarmOptimization，DPSO)完成跨域虚拟网络映射的划分，统筹考虑域间链路资源和节点资源开销，实现全局资源综合最优化。算法的输入为物理网络 $G _ { s }$ ，虚拟网络请求 $G _ { \nu }$ ，输出为域间映射方案，包括节点映射和链路映射两部分，该优化方案将作为2.2节域内算法输入的一部分。

图3为MANO获取的网络全局视图，MANO不了解子域的具体网络拓扑，但可以根据节点竞价等方式了解子域类的资源类型和大致分布。跨域部分算法主要考虑域间链路资源和节点资源开销进行资源分配和功能部属。

对于域间链路开销部分，该问题已被证明是NP-hard问题[7]，因此对于这类问题通常采用元启发式算法，目标是在可接受的时间内找到问题的近似最优解。对于节点资源开销部分，节点竞价是一种InPs与 SPs进行商业博弈的方式，主要流程为：SP请求发送至MANO，MANO记录SP请求的节点以及链路需求信息。各个InPs中的控制器将本域所能提供的节点资源信息和节点资源单价发送给信息处理中心。例如InPs1向MANO 递交内容为：可提供物理节点v1、v2、v3，资源量分别为20、5、5，资源单价为12。处理中心对各InPs发送的信息和SP请求进行分析制定竞价结果表（BiddingResults Table,BRT)，MANO根据算法计算最优虚拟节点映射结果。

# 2.1.1编码方式

设置每个粒子为一个向量，每个分量代表一个虚拟节点映射到的物理节点，那么，对于某个虚拟网，虚拟节点的个数就决定了向量的长度，虚拟节点的编号决定了分量的位置，虚拟节点所映射到的物理节点序号决定了分量的值。这样，每个粒子就代表了一个虚拟网节点映射方案。有历史因素引导的情况下，是否对位置向量进行调整，由方向向量决定，方向向量中分量和位置向量的分量是一一对应的，其分量可取值0或1，为1代表对位置向量的该分量进行调整，为0，不调整；当进行扰动时，可以随机生成位置向量。

![](images/42c77f76492b45092cb9c3290c9720426d7bfa9c881b183f98cdc5cabb056c98.jpg)  
图3MANO全局视图下域间映射结果

# 2.1.2适应度函数

每次节点映射的好坏由适应度函数衡量，由下式作为适应度函数：

$$
f = \sum _ { ( u , \nu ) \in L _ { V } } L E N ( u , \nu ) \bullet B W ( u , \nu )
$$

即由节点映射方案所得到的链路映射结果决定适应度的值。其中 $L E N ( u , \nu )$ 是指虚拟链路 $( u , \nu )$ 所映射的物理路径长度（跳数)； $B W ( u , \nu )$ 是指虚拟链路的带宽。

# 2.1.3迭代优化

优化离散粒子群算法是个多解迭代的过程，基本思想是通过群体中个体之间的协作和信息共享来寻找最优解，具体迭代优化过程为：

a）初始化位置向量及其他变量，迭代次数 $\scriptstyle { \mathsf { z } } = 0$ 。b)根据方向调整操作得到方向向量，根据方向向量使用位  
置调整操作对位置向量进行调整，生成一套新的位置向量。c)根据K一最短路径算法计算每条虚拟链路对应物理节点  
对之间的所有可用最短路径。如果映射链路失败，且没超过最  
大回退次数，转入步骤（2)，如果达到最大回退次数，返回链  
路映射失败。d）根据式（1）得到此位置向量下的适应值。e）对适应值进行评估，判断是否小于当前的优势群体的某  
个个体，如果小于且新节点向量不在优势群体，则更新当前优  
势群体。f）比较新适应值与该粒子的前适应值，若新适应值较低，  
且在该方向飞行次数小于最大保持方向飞行次数Ns，转步骤  
g)；否则，进入下一次迭代，转步骤（2）。g）根据已确定的方向向量，调用位置调整操作。h)根据K一最短路径算法计算每条虚拟链路对应物理节点

对之间的可用最短路径。若映射物理链路成功，转步骤d)；如果映射链路失败，且没超过最大回退次数，转步骤g)。

i) $\scriptstyle z = z + 1$ ，判定是否达到迭代次数，如果否，转步骤b)。2.1.4参量操作

位置调整操作将重新改变粒子 $i$ 的位置，即重新确定各分量 $j$ 的取值，物理意义为虚拟节点 $j$ 重新选择物理节点进行匹配，位置调整操作通过多次方向调整操作来执行。方向调整操作即粒子 $i$ 的方向分量 $j$ 根据调整概率 $P _ { i j }$ 取值。 $P _ { i j }$ 值为$\operatorname* { m a x } ( r , h )$ ， $\boldsymbol { r }$ 是算法引入的随机调整因子以跳出局部最优，是值域为[0，1]的随机数； $h$ 的确定基于算法对历史数据的分析，分析历史最优的 $\mathrm { ~ m ~ }$ 个个体，在每个最优个体的分量j上与粒子i的分量 $j$ 比较，记相异的个数为 $n$ ，那么 $h = { \frac { n } { m } }$ 。再生成一个值域为[0，1]的随机数 $p$ ，如果 $P _ { i j } > p$ ，则调整该分量 $j$ 。方向调整操作受到扰动操作的影响，即分量 $j$ 的调整按扰动概率进行取反Pdis°

# 2.2域内部分映射算法

基于域间映射的结果，InPs对各自区域进行域内的虚拟网络映射，图4为各子域区域视图，区域控制器了解本域内的资源分布和网络拓扑，且边界节点已经选定。

![](images/483f26d56c61b357e429874146866834307061f5f6e799c13c5672cc1608ab53.jpg)  
图4各子域区域视图

本文提出的域内虚拟网络映射算法主要根据底层物理网络的资源状态，以最小代价为优化目标，基于克鲁斯卡尔最小生成树算法提出一种快速映射算法，主要流程如下：

a）根据域间映射结果，输入出口节点的位置信息和带宽信息。b)根据虚拟节点的资源、位置约束等计算每个虚拟节点的可用物理节点集合；c）根据跨域网络环境中的网络资源状态，采用最小权重路由算法计算底层物理网络中候选物理节点间的最小权重路径；d）基于Kruskal最小生成树算法，每一次迭代在最小权重路径集合中动态地选择最小权重物理路径，在获取最小生成树之后对虚拟节点进行映射，再对虚拟链路进行调整，输出最终的映射结果。

# 3 实现结果与仿真

# 3.1仿真环境

仿真实验使用配置为3GB内存，32位Win7操作系统，IntelCore2T9550处理器的计算机进行上述评估，使用MATLAB进行编程，实验中物理网络及虚拟网络拓扑都采用GT-ITM工具随机生成。

实验的预设变量信息如下：预设整个底层网络由5个不同的InPs组成，虚拟节点种类设置为 $\scriptstyle \mathbf { s } = 8$ ，VN请求数设为 $\mathsf { n } = 1$ 000。每个InPs 对于每种虚拟节点提供的资源r服从均匀分布[0\~max]，资源单价P服从［10,20］的均匀分布，每个InPs的控制资源信息集中于管理中心形成统一的资源表。VN请求虚拟节点数服从［1，s］上的均匀分布，其中每个节点需求资源r服从[0\~20]的均匀分布。优化目标为最小化式（3）定义的总体映射开销，节点资源开销权重 $\alpha$ 和跨域开销权重 $\beta$ 均设置为1。粒子群算法中主要参数设置如表1所示。

表1仿真参数表  

<html><body><table><tr><td>参数</td><td>取值</td></tr><tr><td>粒子个数 S</td><td>30</td></tr><tr><td>最大迭代次数Nz</td><td>200</td></tr><tr><td>粒子速度上限</td><td>3</td></tr><tr><td>粒子速度下限</td><td>-3</td></tr><tr><td>扰动操作概率 Pdis</td><td>0.15</td></tr><tr><td>优势群体个数BestN</td><td>6</td></tr><tr><td>学习因子</td><td>0.8</td></tr></table></body></html>

# 3.2 仿真结果及分析

将本文提出的 DPSO-K 算法和基于迭代搜索的匹配算法（简称HTF）以及基于二元整数规划的最小代价算法（简称MC-VNM）进行仿真对比[14,15]。

![](images/102abceed870451e1e1ae612ed084e3beea0d6572853e539463989f0efcae35b.jpg)  
图5各算法总体映射开销对比

图5为三种算法在不同节点数量情况下总体映射开销对比，可以看出DPSO-K算法通过统筹考虑节点资源和链路资源并利用离散粒子群算法寻优，一定程度上降低了总体映射开销，验证了算法的有效性。同时可以看出，随着虚拟请求节点数目的增加，虚拟网络映射的代价增加速率恒定。当问题规模更大时，比如大规模网络环境下，此方案仍然适用。

![](images/98d1d9fc86e64ba60096386e386b5b6f4908936d1fb4b112a94d76c9907134a6.jpg)  
图6不同数据域个数对总体映射开销的影响

图6为三种算法在不同数据域个数对总体映射开销的影响，此时物理网络和虚拟网络节点个数保持一致，但改变物理网络的数据域个数。可以看出随着数据域个数增多，域间映射会带来额外的带宽开销，且所提算法在不同数据域个数的情况下，均能保证总体开销较对比算法更小，验证了算法的稳定性。

表2各算法的平均映射时间/s  

<html><body><table><tr><td>算法</td><td>HTF</td><td>MC-VNM</td><td>DPSO-K</td></tr><tr><td>业务平均映射时间</td><td>10.32</td><td>18.33</td><td>23.5</td></tr></table></body></html>

从表2的实验数据可以看出，DPSO-K算法虽然能够降低开销，但是算法运算时间较长，这是因为基于粒子群的跨域映射部分引入了资源报价，导致算法复杂度上升。但运算时间的上升仍处于同一数量级，在实际应用中额外的时间开销是可以接受的。

# 4 结束语

通过分析现有跨域虚拟网络映射算法存在的不足，文中提出了一种跨域网络环境中的分层资源管理模式，用于动态地管理各个自治域内的网络资源；在充分考虑跨域网络环境、物理链路带宽存在差异化的前提下，为自治域内的链路带宽和自治域间的主干链路带宽设置不同的链路权重，然后根据所有自治域中的物理网络资源状态，基于最小代价的虚拟网络映射优化目标，实施跨域虚拟网络映射操作。在以主要考虑域间开销的情况下，以全局资源总体开销最小为目标，以资源限制为约束，建立虚拟网络映射的离散粒子群优化模型。理论分析和实验结果表明，文中提出的DPSO-K算法有效地降低了虚拟网络映射的资源代价，具有较好的网络性能，实现基础设施提供商的收益最大化。虚拟网络映射中还有很多问题需要研究与解决，目前相关研究工作主要是对静态网络资源需求的虚拟网络请求进行有效地映射，由于网络资源的稀缺性，5G网络中的服务功能链的动态迁移与调度是下一步工作中本文考虑的问题。

# 参考文献：

[1]Mano T, Inoue T, Ikarashi D.Efficient virtual network optimization across multiple domains without trevealing private information [C]//Proc of the 23rd International Conference on Computer Communication and Networks.

2014:1-8.   
[2]Shen Meng,Xu Ke,Yang Kun.Towards efficient virtual network embedding across multiple network domains $[ \mathrm { C } ] / \hbar$ Proc of the 22nd International Symposium of Quality of Service.2014: 61-70.   
[3]肖蔼玲，王颖，孟洛明，等．基于知识描述和遗传算法的跨域虚拟网络 映射[J]．软件学报,2014,25(10):2189-2205.   
[4]Ye Z,Cao X,Wang J.Joint topology design and mapping of service function chains for efficient,scalable,and reliable network functions virtualization [J].IEEE Network,2016,30 (3): 81-87.   
[5]YousafF Z,Taleb T.Fine-grained resource-aware virtual network function management for 5G carrier cloud[J].IEEE Network,2016,30(2): 110-115.   
[6]Garg S,Dwivedi RK,Chauhan H.Efficient utilization of virtual machines in cloud computing using synchronized throttled load balancing [C]// IEEE Next Generation Computing Technologies.2015:77-80.   
[7]Baumgartner A,Reddy VS,Bauschert T.Mobile core network virtualization: a model for combined virtual core network function placement and topology optimization [C]// Proc of IEEE Conference on Network Softwarization. 2015:1-9.   
[8]Gonzalez A, BarraA E,Begheli A.A sub-graph mapping-based algorithm for virtual network allocate on over flexible grid networks [C]// IEEE Transparent Optical Networks.2015:1-4.   
[9]Guo K,Wang Y, Qiu. Particle swarm optimization based multi-domain virtual network embedding [C]//Proc of International Federation for Information Processing (IFIP） /IEEE International Symposium on Integrated Network Management.2015:798-801.   
[10]贾伟，夏靖波，跨域虚拟网络映射问题研究[J]．电子与信息学报,2016, 38 (3): 728-734.   
[11] Gong S,Chen J,Yin X,et al. Survivable virtual network embedding across multiple domains [C] [C]// Proc of IEEE International Conference on Computer & Communications.2017:2391-2396.   
[12] Lv Bo,Wang Zhenkai,Huang Tao,et al. Virtual resource organization and virtual network embedding across multiple domains [C]// Proc of International Conference on Multimedia Information Networking& Security. 2010: 725-728.   
[13] Jia W,Xia J.Research on virtual network embedding across multiple domains [J].Journal ofElectronics & Information Technology,2016,38 (3): 728-734.   
[14] Shen M,Xu K,Yang K,Chen H. Towards efficient virtual network embedding across multiple network domains [J].Quality of Service,2014: 61-70.   
[15]Dahir M,Alizadeh H,Gozuipek D.Energy efficient virtual network embedding in federated software defined networks $[ \mathrm { C } ] / \AA$ Proc of Signal Processing & Communications Applications Conference.2017.