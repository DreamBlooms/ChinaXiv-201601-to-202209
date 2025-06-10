# 利用机器学习和BILP模型的异构云无线接入网络切换方法

龚卓，汤如金，何丽波(湖南农业大学，长沙 410128)

摘要：在异构云无线接入网络（H-CRAN）中，移动用户可能面临糟糕的切换（HO）性能。为了在 H-CRAN 网络中获得最优的切换性能，提出一种基于机器学习和二进制整数线性规划(binary integerlinear programming,BILP)的异构云无线接入网络切换方法（SDHDE)。在基带池中，利用一个无线控制器使用户在无线接入网络（RAN）中的南向 API通信中接收 HO 信息，控制器通过北向API将信息提供给 SDHDE，由 SDHDE 处理每一个用户的 HO决策。仿真结果表明，相比其他的较新方案，提出的方案可以有效降低HO失败的百分比，提高网络的吞吐量。

关键词：异构云无线接入网络；软件定义无线组网；切换决策；朴素贝叶斯；二进制整数线性规划 中图分类号：TP393 doi:10.19734/j.issn.1001-3695.2018.11.0838

# Heterogeneous cloud radio access network switching scheme based on machine learning and bilp model

Gong Zhuo,Tang Rujin, HeLibo (HunanAgriculturalUniversity,Changsha410128,China)

Abstract: In heterogeneous cloud radio accessnetwork,mobile users may face poor handover (HO)performance.In order to approach optimal HO performance in H-CRAN, this paper proposed a handover method (SDHDE)of heterogeneous cloud wireless access network based on machine learing and Binary integer linear programming (BILP） model. In the baseband pool, it used a wireless controler to receive HO information from the Southbound APIcommunicating with the end-users at theRAN.The controlers published this information to the SDHDE throughthe Northbound API,and SDHDE processed the HO decision for each user in an optimal manner.Simulation results demonstrate the improvements that proposed scheme can achieve mainly regarding smaller HO percentage failure and increased throughput comparing with other new schemes.

Keywords: heterogeneous cloudradio accss networks;software-defined wirelessnetworking;switching decision; naive bayes; binary integer linear programming

# 0 引言

异构云无线接入网络（heterogeneous cloud radio accessnetwork，H-CRAN）是一种用于下一代移动无线网络（5G）的新的候选架构[1]。H-CRAN 具有异构网络（heterogeneousnetwork，HetNet）和云无线接入网络（cloud-RAN，C-RAN）的所有优点，能够满足未来的数据传输需求[2]。H-CRAN结构使用集中化的基于云的负载处理技术部署密集HetNet，通过改进网络优化和层间干扰管理来提高频谱和能量效率。H-CRAN相对于传统的基于蜂窝单元的蜂窝网络在保证优先的数据传输速率下具有完整的无线覆盖率，用户设备（userequipment，UE）必须在H-CRAN中频繁的进行垂直切换（verticalhandover，VHO)，这种方法带来了一个问题：高速移动的用户可能触发大量的切换，从而需要在短时间内处理大量的请求，此时需要使用可伸缩的机制来减小对用户的服务质量的影响[3]。

为了避免不必要的切换，科研人员提出了软件定义网络（software-definednetworking，SDN）[4]的概念，它将网络的操作层转换为无线网络中的一个具有逻辑中心化控制的软件编码层，因此也被称作软件定义无线网络（software-definedwirelessnetworking，SDWN)。SDWN可以用于切换控制，从而实现一种软件切换优化（software-definedHO，SDHO）的方法，在高密度网络中具有较好的性能表现[5]。

文献[6]分析了在全IP网络中使用SDHO的挑战和可能性。文献[7]给出了中心化的SDHO控制器架构是如何在大尺度RAN网络中进行动态自适应和管理无线电资源的例子。但是，这些方案大多数都具有高延迟，错误的切换指示以及不适当的连接点选择的问题，不适用于H-CRAN网络[8]。本文提出了一种 SDHO 解决方案，其中控制器部署在接近于H-CRAN网络的BBU池的位置，从而能够中心化控制整个控制区域的决策。本文提出的这些控制器具有良好的可扩展，可以支持软件定义切换决策引擎（Software-DefinedHandoverDecision Engines，SDHDE）实现H-CRAN网络中的切换管理。SDHDE可以将传统的UCHO切换转换为一个网络中心化的无缝切换。每个UE的候选网络选择都是基于控制平面所提供的整个网络状态的集中决策，从将其转换为一个优化问题。

# 1 背景和相关工作

文献[9]展示了对于一般的VHO问题的研究成果。然而，

专门针对H-CRAN的研究却很少。因此，本文提出了两个不同的研究路线：切换标准；利用其他网络环境作为未来在H-CRAN中部署 SDHO的潜在解决方案。

# 1.1切换标准

蜂窝网络和IP网络已经接受多个切换标准来解决用户设备的垂直移动支持问题。例如，在IP网络中，IPv4和IPv6[10,11]移动互联网协议是标准通信协议，利用它们可以实现保持永久性用户设备IP地址的分组的位置无关路由。

媒介无关切换（media independent handover，MIH）[12]协议是在异构和第二层接入技术之间执行垂直切换的标准化机制。MIH将所有媒介的特定技术统一在一个抽象接口之下，从而实现无线接入技术（radioaccess technologies，RAT）之间的互操作性。但是，这种统一的定义仍然带来很多问题。由于存在大量RAT专用标准（例如，用于IEEE的MIH和用于基于3GPP的网络的LTEHO）必须被扩展以符合MIH协议，所以这种方法可能难以实现。此外，目前的MIH标准缺乏一个上下文感知模块来适应网络动态变化和在网络中均匀分配负载的机制，MIH受限于上下文无关的情况，无法保证网络的最优性来解决H-CRAN中SDHO的需求。

# 1.2基于 SDWN 的切换控制

最近，有大量应用于HetNet的切换控制方法被提出。文献[13]提出了一种基于SDN的小基站分流方法，这种方法基于不满意参数和终端用户分类，在控制区域处理异质性连接点的分流工作。文献[14]提出了一种 SDWN 间的无缝连接方法，运用一种切换控制算法降低丢包率和等待时间，使得用户体验质量（qualityof experience，QoE）最大化。文献[15]利用蚁群算法（antcolony algorithm，ACA）来实现基于蜂窝移动网络的移动鲁棒性优化（mobilityrobustnessoptimization，MRO）的目标。文章所提出的方法是通过采用考虑ACA的切换失败事件的数量的成本函数来最小化无线链路失败（radiolinkfailure，RLF）和不必要的切换的数量。文献[16]提出了一种在异构云小基站网络中的干扰抑制和切换管理的方法。基于基带池提供的集中式信号处理的协同发送/接收技术可以缓解边缘用户设备的小基站间的同频干扰，从而提高小基站的频谱效率。文献[17]提出了一种针对LTE蜂窝网络的梯度方法和基于成本函数的 MRO方案。第一种方法是检测RLF事件和不必要的切换，第二种方法是利用基于梯度的算法，对前面的算法进行迭代，其目标是收敛到最小化的成本函数。

上述工作均来自HetNets 或者传统的蜂窝网络，它们无法利用H-CRAN带来的全部新功能。本文提供了一种新的方法，它考虑了网络参数（如链路延迟、信噪比等）的归一化以使得异构系统参数可保证每个用户设备的公平的获得全局信息。而且，本文所提出的实时SDHDE 解决方案使得VHO问题在自组织化管理移动性的H-CRAN中变得可扩展。

# 2 H-CRAN 中的 SDHDE

在一个基于SDWN的H-CRAN中，用户设备通过不同的连接点与RAN进行通信。各个连接点都分别连接到信令处理、媒体访问控制（MAC）、无线电资源控制（RRC）、分组数据汇聚协议（PDCP）和无线电链路控制（RLC）等处理无线功能的BBU池。这些功能由控制平面中的SDWN 控制器使用南向API控制，控制器可以执行不同的控制功能，包括映射H-CRAN拓扑，从连接点检索无线资源信息，监视连接点等。所有的控制功能都可以通过北向API从应用程序平面的不同例程中调用。通过沿着不同的 H-CRAN 连接点移动，用户设备开始触发切换事件。这些事件必须由控制平面上的SDWN控制器来检测和协调。消息的处理根据在控制器处实施的逻辑而发生，所述逻辑可以由应用层的实例动态地调整或改变。在这个意义上，为了改变控制器逻辑，本文在应用平面设计了一个SDHDE 来执行一个新的决策技术，改变了SDWN控制器处理切换的方式。下面将介绍SDHDE技术以优化H-CRAN切换，整个过程分五个阶段进行构建。

# 2.1数据获取

SDHDE在执行切换决策时，必须要先从前向层获取信息，从而得到整个H-CRAN网络当前的运行状态。本文使用一种用户为中心的方式接收数据，利用算法1获得用户设备在整个H-CRAN 网络中其覆盖范围内的连接点。

算法1连接点检测和度量收集算法信道编号：channelNumber最大信道数量：maxChannelNumber源连接点的MAC 地址： $M A C _ { s o u r c e P o A }$ （204号

1 执行：   
2 channelNumber=1   
3 当1≤channelNumber≤maxChannelNumber时   
4 SendProbRequest(probRequest)   
5 probResponse=WaitProbeResponse()   
6 data=CollectData(probResponse)   
7 channelNumber $\cdot =$ channeLNumber+1   
8 结束   
9 SendAssociationRequest()   
10 SendToSource 连接点( $M A C _ { s o u r c e P o A }$ ,data)   
11 sleep( $x$ secs)

12结束

一个用户设备在执行算法1的过程时，需要当前使用的信道编号（channelNumber）、所扫描到的最大信道数量（maxChannelNumber）以及源连接点的MAC地址（ $M A C _ { s o u r c e P o A }$ ）作为输入参数。具体而言，由于连接点可以在不同的信道上工作，所以UE需要扫描每个信道上从1到maxChannelNumber的网络发送探测请求。当循环允许用户设备在其传输范围内从这些连接点周期性地收集网络信息时，首先，通过变量channelNumber将用户设备物理层的信道编号设置为1。为了收集诸如信号干扰噪声比（SINR）和分组差错率（PER）之类的网络度量，下一个循环允许用户设备发送探测请求(probeRequest)以主动搜索当前channelNumber覆盖区域中的网络设备直至直到满足条件。之后，用户设备准备接受来自连接点中WaitProbeResponse 函数接收到的传入探测响应（probeResponse）。一旦接收到探测请求，用户设备就可以检索诸如RSSI、SINR、PER、扫描的连接点的MAC地址以及所扫描的连接点的信道编号之类的网络度量。

# 2.2数据管理

仅仅简单的聚集用户设备的度量值并不能为以用户为中心的切换决策提供足够的信息。提升整体网络状态的最优切换决策需要考虑到大量的网络参数，这些信息并不能单靠一个用户设备获得。因此，本文考虑从控制层的多种网络相关参数（如：带宽、延迟和丢包率等）得到一个增强的全局视角。根据网络收集和接收到的信息建模，可以得到一个有向图 $G ( E , A )$ ，其中：

a） $E = \left[ l ^ { \cdots } n \right]$ 是节点的集合（也就是连接点、固定和移动的节点)。b） $\overset { \triangledown } { \mathcal { A } } = \left[ 1 \cdots { \widehat { \mu } } \right]$ 表示每对节点间的弧。c） $\mathscr { E } = ( i , j ) \in \mathcal { A } \cup ( j , i ) \in \mathcal { A }$ 是边的集合。

如图1所示为5个节点的有向图，共有8条边。

![](images/166f41dc46f429a71fd821017e8e61e9bbb17f3887bab3284f1f890ed29cb13c.jpg)  
图1有向图示例  
Fig.1Directed illustration

$\forall e \in \mathcal { E }$ 是双向边，且如果弧 $\mathbf { \Psi } _ { e }$ 是一个有线连接，则带宽是 $b _ { i , j }$ ，延迟是 $d _ { i , j }$ ，丢包率是 $p _ { i , j }$ ；如果弧 $e$ 是一个无线连接，对于连接点 $i$ （或者 $j$ ）覆盖范围内的每一个用户设备 $j$ （或者i），除了具有和有限连接相同的参数外，还具有：RSSI$r s s i _ { i , j }$ 、SINR $s i n r _ { i , j }$ 和PER $p e r _ { i , j }$ 。

一旦上面所提到的数据被SDWN控制器接收并存储，就需要开始对所有的原始的异构的参数进行标准化，并估计参数。在SDWN控制器中，每一个参数 $x$ 都可以调用函数 $\mathcal { N } ( \boldsymbol { x } )$ 对其标准化：

$$
x ^ { \prime } = \mathcal { N } ( x ) = \left\{ \begin{array} { l l } { \displaystyle \frac { x _ { m a x } - x } { x _ { m a x } - x _ { m i n } } } & { x _ { \operatorname* { m a x } } - x _ { \operatorname* { m i n } } \neq 0 } \\ { 1 } & { \ncong \nVDash 4 . 1 4 } \end{array} \right.
$$

其中： $x _ { m a x }$ 是目前所接收到的同类参数 $x$ 的最大值， $x _ { m i n }$ 是所接收到的同类参数 $x$ 的最小值， $x ^ { \prime }$ 是 $x$ 的标准化参数。在使用函数 $x ^ { \prime } = \mathcal { N } ( x )$ 标准化后，每个参数 $x$ 都被转换为了 $x ^ { \prime }$ ，且 $0 \leq x ^ { \prime } \leq 1$ 。因此，可以认为所有参数都已经被标准化。接下来，对于每一个连接 $( i , j )$ 可以定义代价函数 $c _ { i , j }$ ：

$$
\begin{array} { r } { c _ { i , j } = w _ { r s s i . } \big ( 1 - R S S I _ { i , j } \big ) + w _ { s i n r . } \big ( 1 - S I N R _ { i , j } \big ) + } \\ { w _ { p e r } { \cdot } P E R _ { i , j } + w _ { d } { \cdot } d _ { i , j } + w _ { p } { \cdot } p _ { i , j } \quad } \end{array}
$$

其中：

$$
w _ { r s s i } + w _ { s i n r } + w _ { p e r } + w _ { d } + w _ { p } = 1
$$

从整个网络状态的角度来看，控制器可以更好地以逻辑集中的方式来管理QoS，从而可以根据度量的重要性和业务类型来调整权重，灵活而且适应性强。例如，在典型的语音呼叫应用中，受到重传的影响，PER和SINR的权重将被控制器大大增加。此外，SDWN控制器构造了一个 $\# \mathcal { N } \times \# \mathcal { N }$ 的代价矩阵（CostMatrix），这个代价矩阵定义如下：

特别地，考虑到H-CRAN的异构性，对于有线连接，本文只考虑延迟和丢包度量，对于无线连接，本文考虑了RSSI、SINR、PER和延迟。在这一点上，由于所有的指标都被收集、存储和标准化，SDWN控制器已经准备好开始执行切换决策。

# 2.3切换优化问题建模

通过构建代价矩阵，SDWN控制器具有了将网络选择建模为二进制（0或1）整数线性规划（binaryintegerlinearprogramming,BILP）所需的所有必要信息。具体来说，将网络选择制定为二元最小成本多商品网络流问题（binaryminimum-cost multi-commoditynetwork flow, 0-1MCMCNF),其主要目标是找到在同一底层网络结构中，最好的并行运输货物的流程路径的集合。因此，由于最小费用流问题的算法隐含地解决了最短路径问题，并且需要将k个流程作为单个实体一起发运，所以本文将变量 $x _ { i , j } ^ { k }$ 视为二进制值。通过定义二进制整数规划问题，标准化的参数允许找到导致每个用户设备的最佳成本的最佳路径。本文假定网络中弧的容量就是网络连接的带宽，其相关的代价由代价矩阵中的 $c _ { i , j }$ 确定。另外，其他的约束包括流量保护和链路的可用带宽等。

令 $\kappa = [ 1 . . . k ]$ 表示网络中所需要传输的物品集合，其中$k \in \mathcal { K }$ 可以定义为三元组 $\left( { { s } _ { k } } , { { t } _ { k } } , { { f } _ { k } } \right)$ 的形式，其中： $s _ { k }$ 是第 $k$ 个物品的源节点； $t _ { k }$ 是第 $k$ 个物品的目的节点；而 $f _ { k }$ 是其的需求。此外， $B ^ { k }$ 表示第 $k$ 个物品从源节点 $s _ { k }$ 传输到目的节点 $t _ { k }$ 所需要占用的带宽。对于任意一组工作流 $( x , y )$ ，如果 $x \neq y$ ，那么 $s _ { x } = s _ { y } \land t _ { x } = t _ { y }$ 是不可能的。也就是说，具有相同源节点和目的节点的工作流是不可能存在的。因此，0-1MCMCNF问题可以表示为下面的0-1整数规划模型：

$$
\operatorname* { m i n } _ { ( i , j ) \in \mathcal { A } } \sum _ { k \in \mathcal { K } } c _ { i , j } x _ { i , j } ^ { k }
$$

$$
s . t . \quad \sum _ { ( i , j ) \in \mathcal { A } } x _ { i , j } ^ { k } - \sum _ { ( j , i ) \in \mathcal { A } } x _ { j , i } ^ { k } = \left\{ { 1 \atop 0 } \right. \quad i = s _ { k } , t _ { k }
$$

$$
\sum _ { k \in \mathcal { K } } B ^ { k } x _ { i , j } ^ { k } \leq b _ { i , j } , \forall ( i , j ) \in \mathcal { A }
$$

$$
x _ { i , j } ^ { k } \in \{ 0 , 1 \} , \forall \left( i , j \right) \in \mathcal { A } , \forall k \in \mathcal { K }
$$

其中： $x _ { i , j } ^ { k }$ 表示转发服务的决策变量， $c _ { i , j }$ 表示在链路 $( i , j ) \in \mathcal { A }$ 上传输物品 $k$ 的单位开销。因此有 $x _ { i j } ^ { k } = 0 \vee x _ { i j } ^ { k } = 1$ ：

考虑到问题的规模，变量的数量是 $| \kappa | \cdot | A |$ ，约束的数量是 $| \kappa | \cdot | \mathcal { N } | + | \mathcal { A } |$ ,其中 $| { \cal { A } } |$ 是弧的数量， $| \mathcal { N } |$ 是节点的数量， $| \kappa |$ 所运输货物的数量。显然，0-1整数规划问题是一个NP完全问题[18]。为了演示这一NP完全的0-1 整数规划算法，考虑一个布尔方程，具有常量 $X = \{ x _ { 1 } , ^ { \cdots } , x _ { n } , { \tilde { x } } _ { 1 } , ^ { \cdots } , { \tilde { x } } _ { n } \}$ 和条款 $C _ { i }$ ，$i = 1 , . . . , m$ ，假定不失一般性，有 $\big | C _ { i } \cap \{ x _ { j } , \tilde { x } _ { j } \} \big | \{ \leq 1$ ，对于所有$i = 1 , . . . , m$ 且 $j = 1 , . . . , n$ ，令 $\mathcal { A } \in \mathbb { Z } ^ { m \times n }$ 且 $b \in \mathbb { Z } ^ { m }$ ，则可以定义：

$$
a _ { i , j } = \left\{ { \begin{array} { l l } { 1 } & { x _ { j } \in C _ { i } } \\ { - 1 } & { { \tilde { x } } _ { j } \in C _ { i } } \\ { 0 } & { { \stackrel { } { \# } } { \mathrm { \# } } { \mathrm { \# } } { \mathrm { \# } } } \end{array} } \right.
$$

$$
\begin{array} { l } { b _ { i } = 1 - \vert \{ j : \tilde { x } _ { j } \in C _ { i } \} \vert } \\ { i = 1 , \cdots , m } \\ { j = 1 , \cdots , n } \end{array}
$$

这种整数线性规划用一个二进制变量表示每个布尔值，每个条款用一个需要其文字的约束来表示，其和至少为1。为此，如果相应的布尔变量出现，约束的左边包含 $x _ { j }$ 作为该条款中的一个正面的文字，如果出现了一个否定的文字，则为 $( 1 - x _ { j } )$ 。上面的形式是通过将所有常数移到等式右边来获得的。

# 2.4切换执行的时间策略

本文提出了一种基于所接收到的SINR值的新算法用于解决切换过程的计时问题，这种方法可以增强移动鲁棒性。事实上，在0-1整数规划问题求解之后，可以将所有任务划分为两种情况：

情况0没有用户设备需要切换。

情况1有至少一个用户设备需要切换。

在情况1下，触发切换之前需要考虑切换失败存在的可能性，并应该尽可能地限制这种现象的发生。特别是，SDHDE必须要对在触发切换后可能出现的以下情况作出执行切换的准备：

a）SDHDE决定发送一个特定的指令触发某个用户设备的切换，但是切换因为目标连接点的RSS级别过低而失败，也就是说，切换的过早了。在检测到切换失败后，用户设备重新连接到源连接点。可以把这种情况定义为 $H O _ { e a r l y }$ 。

b）SDHDE决定发送一个特定的指令触发某个用户设备的切换，但是切换因为设备的RSS级别过低，用户设备在接收到切换指令之前就与源连接点失去了连接，从而导致了切换失败，也就是说，切换的过晚了。在检测到切换失败后，用户设备重新连接到源连接点。可以把这种情况定义为HOlate

c）SDHDE决定发送一个特定的指令触发某个用户设备的切换，但是目标用户设备在短时间内（例如：大约4-6秒）刚刚经历了一次切换，用户设备又在此连接到了源连接点。这种切换失败是由于乒乓效应造成的，因此可以把这种切换失败的情况定义为 $H O _ { p i n g }$ pong。

本文将上述情况考虑为切换失败事件，用符号 $H O _ { f a i l u r e }$ 表示。由于用户设备切换需要消耗网络资源重发用户设备接入信息给新连接点，因此减少不必要的用户设备切换数量也可以最小化网络的开销。为此，本文引入了一种切换触发限制参数 $\varphi$ ，用于自适应切换操作，进而达到最优网络切换与网络性能之间的折中。

参数 $\varphi$ 表示执行切换过程之后的限制值。它可以是一个根据在SDWN部署前的H-CRAN特性估计得到的确定值，也可以是一个根据时间连续调整的值。SDWN控制器在求结果0-1MCMCNF问题之后必须检查 $S I N R _ { t a r g e t P o A } \left( \delta , \ \tau \right)$ 和$S I N R _ { s o u r c e P o A } \left( \delta , \ \tau \right)$ 之间的差异，其中 $\delta$ 表示用户设备， $\boldsymbol { \tau }$ 表示收集 SINR值时的瞬时时刻。这两个值的差值应该大于 $\varphi$ 。可以用下面的符号定义同一时刻 $\tau$ 的对于不同连接点和同一用户设备 $\delta$ 的 SINR 差值：

$$
\Omega ( \delta , \tau ) = { S I N R } _ { t a r g e t P o A } \left( \delta , \tau \right) - { S I N R } _ { s o u r c e P o A } \left( \delta , \tau \right)
$$

如果状态满足要求，那么目标连接点就会成为特定用户设备在当前H-CRAN 网络状态下的最佳候选。由于无线网络环境特性是动态变化的，网络状态可能以一种快速且不可预测的方式发生变化。因此，本文提出了下面的算法以最小化切换失败的百分比。

作为一个大致的规则，需要将 $\varphi$ 值设置的足够大以避免乒乓效应。但是，如果 $\varphi$ 增大到超过某一特定值，切换性能就会下降。这是因为切换速度不够快，使得用户设备不能及时建立与最优候选连接点之间的连接。因此，在SDHDE 部署时，如果希望以积极的方式平衡网络，可以假定 $\scriptstyle \varphi = 0$ 甚至$\varphi < 0$ 。并且，为了最小化切换百分比和增强H-CRAN网络的移动鲁棒性，本文拓展了算法2使得参数 $\varphi$ 的值可以根据不同的切换失败的原因自适应地调整。在SDHDE的生命周期内参数 $\varphi$ 的值是自动且连续更新的，其增加与减少根据事件的发生动态进行，直至切换失败的数量减少。假定变量$H O _ { f a i l u r e }$ 包含不必要或者失败的切换（也就是 $H O _ { e a r l y }$ 、 $H O _ { l a t e }$ 和$H O _ { p i n g - p o n g }$ )，参数 $\varphi$ 的自适应调整算法如算法2所示。

算法2 切换失败算法

目标连接点的SINR： $S I N R _ { t a r g e t P o A } \left( \delta , \ \tau \right)$   
源连接点的SINR： $S I N R _ { s o u r c e P o A } \left( \delta , \ \tau \right)$ （204   
切换触发限制参数： $\varphi$ （204号   
1 $\Omega ( \delta , \tau ) = S I N R _ { t a r g e t P o A } ( \delta , \tau ) - S I N R _ { s o u r c e P o A } ( \delta , \tau )$   
2 如果 $\Omega ( \delta , \tau ) \geq \varphi$   
3 执行HandoverExecution(   
4 否则   
5 保持当前状态   
6 结束   
算法3参数 $\varphi$ 自适应调整算法   
切换失败事件： $H O _ { f a i l u r e }$ （204号

切换触发限制参数： $\varphi$   
1 $H O _ { f a i l u r e } { = } f a l s e , \varphi { = } 0$   
2 执行：  
3 如果 $H O _ { f a i l u r e } = t r u e$   
4 如果 $H O _ { e a r l y } \lor H O _ { p i n g - p o n g }$ （20  
5 增加 $\varphi$ （204号  
6 如果 $H O _ { l a t e }$ （204号  
7 减小 $\varphi$ （204号  
8 结束  
9 结束  
10 结束

过早切换往往是由于用户设备的移动性较差或者没有很好地定义运动模型造成的；延迟切换往往由于用户设备具有高移动性模型的场景造成的。因此，对 $\varphi$ 进行适度的调整可以带来在非均匀场景中较好的切换时机。

# 2.5切换执行

利用机器学习的思想实现切换决策。机器学习模型主要由四个部分构成，分别是学习环境、学习单元、知识库以及学习执行单元，如图2所示。学习环境为学习过程提供有用的信息，这些信息经过学习单元的处理，为知识库的改进提供了条件，然后执行单元根据以上信息处理相应的任务，处理过程中将反馈信息传送给学习单元，或者作出改变去适应环境。

![](images/9c0d63014c69eeed931622ba0609ba20e580713fe6a05df0b370027808fc6469.jpg)  
图2机器学习模型  
Fig.2Machine learning model

系统在运行过程中利用异构云网络中的环境信息对已存在的示例不断进行学习改进，并调整相关应用程序，使学习系统不断完善，系统会积累丰富的异构网络切换知识。这样就可以依据该决策系统根据环境信息的变化和用户的需求变化自适应去完成切换和决策。

朴素贝叶斯是一种常用的机器学习算法。朴素贝叶斯公式为

$$
P ( C _ { k } | X ) = { \frac { P ( C _ { k } ) P ( X | C _ { k } ) } { P ( X ) } }
$$

其中: $C _ { k }$ 代表某个类； $k = 0 , 1$ （dp或 $\mathrm { \ n d p }$ ， $X = ( x _ { 1 } , x _ { 2 } , . . . , x _ { n } )$ 代表软件模块的指标值。

分类器把在测试数据集中具有 $\boldsymbol { \cal X }$ 指标值的模块标记为dp 或ndp，并把训练数据集中的分布考虑在内。根据具有更高的 $\mathrm { a r g } \operatorname* { m a x } _ { k }$ （ $P ( C _ { k } \vert X )$ ）概率值的类来完成标记。由于公式中的分母对于所有 $k$ 类都是相同的，因此不会影响最后的标记结果。因此，可以从公式中把它删除，并表示成如下表达式：

$$
P ( C _ { k } | X ) = P ( C _ { k } ) P ( X | C _ { k } )
$$

概率 $P ( C _ { k } )$ 和 $P ( X | C _ { k } )$ 必须从训练数据集中得到。然而，具有 $X = ( x _ { 1 } , x _ { 2 } , . . . , x _ { n } )$ 指标的软件模块不可能存在于训练数据集中。由于存在这个问题，因此，假设朴素贝叶斯中的特征具有独立性。分别计算每个指标的概率。在这种情况下，朴素贝叶斯公式变成

$$
P ( C _ { k } \left| X \right. ) = P ( C _ { k } ) { \prod _ { i = 1 } ^ { n } P ( x _ { i } \left| C _ { k } \right. ) }
$$

假设 $S = ( R S S , S , \nu , C . . . )$ 为所处环境状态，包含了接收端的信号强度、位置信息、速度等环境信息，当有网络切换发生时，就会产生一个对当前网络状态信息的描述 $s$ 。系统对这个描述进行处理，首先在知识库中查找相似的示例，并和状态描述 $s$ 进行匹配度的对比，若匹配成功的话，就将切换的示例添加到知识库中，否则就执行切换操作。具体流程如图3所示。

![](images/d7e3888b49eeff0db9f22d91ddcd3a257a304c51e652b7897c2f47fa36978b42.jpg)  
图3 切换模型  
Fig.3Switching model

# 3 仿真分析

# 3.1仿真设置

将SDHDE方案部署于一个H-CRAN场景中，H-CRAN的仿真场景由一个大小为 $3 0 0 0 m { \times } 1 0 0 0 m$ 的2D矩形网格区域组成。eNB和小基站随机布置在网格中，并与四个全联接的OpenFlow交换机相连。其中三个交换机与三个不同的服务器相连，这些服务器用于产生构成场景的数据流量。所有的H-CRAN网络参数设置如表1所示。

表1H-CRAN 场景参数设置  
Table 1 H-cran scene parameter settings   

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>用户设备类型[速度m/s]</td><td>行人[1] 小汽车[10]</td></tr><tr><td></td><td></td></tr><tr><td></td><td>火车[40]</td></tr><tr><td>用户设备数量</td><td>400</td></tr><tr><td>RRH数量 蜂窝单元数量</td><td>10</td></tr><tr><td>RRH最大传输功率</td><td>6</td></tr><tr><td>蜂窝单元最大传输功率</td><td>28dB</td></tr><tr><td>蜂窝单元覆盖范围</td><td>39dB</td></tr><tr><td>RRH平均覆盖范围</td><td>1km²</td></tr><tr><td></td><td>75m²</td></tr><tr><td>热噪声</td><td>-110±10dB</td></tr><tr><td>发送天线增益</td><td>-5dB</td></tr><tr><td>接收天线增益</td><td>-5dB</td></tr><tr><td>距离尺度传播模型</td><td>对数距离</td></tr><tr><td>延迟模式</td><td>恒速延迟模式</td></tr><tr><td>SINR</td><td>高斯干扰模型</td></tr></table></body></html>

针对实验中的每个连接点，设置了一个对数距离传播损失模型，用于预测所使用的无线信道的信号传播行为。此外，本文还使用了一个恒速传播延迟模型来表示信号从源到汇点所消耗的总时间。传播速度是常值，且等于光在真空中传播的速度。

使用对数距离传播损失作为无线信道模型，并使用恒速延迟作为传播延迟模型。属于集合 $N$ 的第 $i$ 个用户设备到集合 $M$ 的第 $j$ 个连接点的接收信号强度 $R S S I _ { i } ^ { d B }$ 可以表示为

$$
R S S I _ { i } ^ { d B } = t x P o w e r _ { i j } ^ { d B } - \left( L _ { 0 } + 1 0 n \bullet l o g _ { 1 0 } \left( \frac { d _ { i , j } } { d _ { 0 } } \right) \right)
$$

其中： $R S S I _ { i } ^ { d B }$ 的单位为 $d B \ , n$ 是路径损失距离指数， $d _ { 0 }$ 表示单位距离（也就是 $1 m$ ）， $L _ { \mathrm { 0 } }$ 表示单位距离的路径损失，单位为 $d B$ ， $d _ { i , j }$ 表示用户设备 $i$ 与连接点 $j$ 之间的距离，而$t x P o w e r _ { i , j } ^ { d B }$ 表示特定连接点的传输功率。 $R S S I _ { i } ^ { d B }$ 的值满足$- 1 2 0 d B \le R S S I _ { i } ^ { d B } \le 0 d B$ 。一般而言，数据传输应用要求$R S S I _ { i } ^ { d B } \geq - 8 0 d B$ ：

第 $i$ 个用户设备的信号与干扰加噪声比 $S I N R _ { i } ^ { d B }$ 使用高斯干扰模型计算得到， $S I N R _ { i } ^ { d B }$ 满足 $0 d B \leq S I N R _ { i } ^ { d B } \leq 1 2 0 d B$ 。此外，本文定义数据包错误百分比为接收到的错误的数据包的数量与总结收到的数据包的数量的比值，即

$$
P E R = \frac { p a c k e t E r r o r s } { r e c e i \nu e d P a c k e t s } = 1 - \left( 1 - B E R \right) ^ { L }
$$

其中：BER表示比特错误率， $\textbf { \em L }$ 表示数据包的长度。

所有的OpenFlow交换机都与SDN控制器相连。然而，BBU和所有的连接点则按照惯例与一个调整过的FloodlightSDWN控制器相连。因此，控制层可以收集有线或者无线的网络相关的统计数据。方案部署于OpenNet仿真网络中，这一网络是一种基于Mininet 和NS-3的软件定义无线局域网。此外，数据流量由iPerf 和VLC产生，其中，iPref用于产生一般数据流量，而VLC 用于产生数据流。网络吞吐量由bwm-ng工具收集。所有数据都被重复收集直至其置信度达到至少 $9 5 \%$ 。

# 3.2仿真结果

# 3.2.1切换失败的发生

随着切换失败事件的增加，用户设备的QoS 和QoE 被降级。用户过早或者过晚地执行切换操作，会造成时间的浪费，甚至可能失去连接。为了研究可能造成切换失败的情况，本文尝试通过在H-CRAN网络中随机部署300个用户设备用以评估切换失败事件的发生。特别的，关于切换失败事件（也就是 $H O _ { f a i l u r e }$ )，本文考虑使用一个更进一步的因素$H O _ { p i n g - p o n g }$ 。如果用户设备两次执行切换的时间间隔小于4至6 秒，这一因子就会增加。此外，SDHDE 还检测 $H O _ { e a r l y }$ 和 $H O _ { l a t e }$ 事件。如果目标连接点的SINR（针对 $H O _ { e a r l y }$ 的情况）或者源连接点的SINR（针对 $H O _ { l a t e }$ 的情况）小于5dB，这两种事件就会被触发。本文在 H-CRAN 场景中部署了 SDHDE，并将实验重复了20次，这些用户设备根据他们的移动速度的不同，被分为了3类，分别为行人 $\left[ 1 m / s \right]$ 、小汽车[10m/s]和火车 $\left[ 4 0 m / s \right]$ 。

如图4所示，慢速的用户设备 $\left[ 1 m / s \right]$ 如果具有非常低的$\varphi$ 值（小于3dB)，将会面临非常高的切换失败率。如果 $\varphi$ 继续下降并且最终为负值，天线功率的影响则可以忽略不计，而在其他条件下这可能是确定产生错误的切换的一个重要的因素。与之相反，高速的用户设备，例如小汽车 $\left[ 1 0 m / s \right.$ ]和火车 $\left[ 4 0 m / s \right]$ ，则对较低的 $\varphi$ 值有较强的鲁棒性，这主要因为他们只会在切换边界或基站的交叉点停留很短的时间。尽管这样，高速移动的用户设备仍然面临着较高的切换失败的可能性，即使 $\varphi$ 值很大，且这一比率往往是恒定的。切换失败率恒定的主要原因是发生了乒乓效应一因为小汽车或火车移动的速度过快，在未能完全建立连接以前就离开了小基站的控制区域，不能利用基站的能力。

# 3.2.2吞吐量评估

本文提出的 SDHDE方案集中于关注单一用户设备在其整个移动路径下的通信传输场景。实验中，用户设备与可用服务器进行通信，并接收一个视频流。与此同时，用户设备直线通过8个基站小区。为了验证本文所提方案的优越性，将其与文献[7]提出的方案进行对比，实验对不同类型的用户设备进行了评估，包括行人 $\big [ 1 m / s \big ]$ 、小汽车[10m/s]和火车$\left[ 4 0 m / s \right]$ ，3种不同类型用户设备上的比较结果如图5所示。

![](images/30bfc33fc90e9ea278015328d838c77ffacda9e312cc495290b3ade4cca01397.jpg)  
图4H-CRAN中不同类型的用户设备切换失败的百分比Fig.4Percentage of handover failures for different types of user

![](images/514fd164ef5607b954480cd6672dd642d370805bef390a099bd2757ea09534a6.jpg)  
(b)H-CRAN中小汽车的全局吞吐量

(b) Global throughput ofH-CRAN small and medium vehicles

600-本文提出的方案500 文献[7]提出的方案 心  
T 长区为电热包  
200 中100中00 50 100 150 200 250时间（s）(c)H-CRAN中火车的全局吞吐量(c)H-CRAN in the global throughput of trair

在仿真中，算法对 SDHDE 中的 $\varphi$ 参数进行了校准，校准的结果是：行人为3dB、小汽车为1dB、火车为-2dB。同样，对于每种不同的用户设备，图5中的 $x$ 轴表示实验中所经过的时间，单位为s； $y$ 轴表示所接收到的累积数据量。从图5中可知，对于行人(图5(a))SDHDE增加了约 $32 \%$ 的用户设备吞吐量；在图5(b)中可以看出，用户设备的吞吐量提高了约 $11 \%$ ；对于高速移动的火车，图5(c)的结果表明，SDHDE提升了约 $6 \%$ 吞吐量。事实上，高速移动的用户设备并不能持续的在小区域内获得较高的吞吐量，这导致了与其他类型的用户设备相比，该类设备的吞吐量增长明显较慢。

表2所示为两种方案的切换失败百分比。

表2切换失败百分比  
Table 2Percentage of handover failures /%   

<html><body><table><tr><td>方案</td><td>行人</td><td>小汽车</td><td>火车</td></tr><tr><td>文献[7]的方案</td><td>5.1</td><td>4.8</td><td>8.6</td></tr><tr><td>本文方案</td><td>3.0</td><td>3.3</td><td>4.4</td></tr></table></body></html>

从表2可以看出，相比文献[7]的方案，本文的SDHDE方案具有更小的切换失败百分比。其中，火车场景下，提出的方案切换失败百分比明显低于文献[7]的方案，但是由于火车速度过快，图5(c)展示的用户设备的吞吐量提升情况明显劣于其他场景，这也直接导致了相关实验的仿真时间的缩短。然而，尽管 SDHDE方案仅仅在短时间内（ $2 0 0 \mathrm { ~ s ~ }$ 内）带来了有限的吞吐量提升（约 $6 \%$ )，在长期使用的情况下，这种累积的提升也是十分明显的。

# 3.2.3高负载情况下的吞吐量比较

![](images/811517da3a7193b6c34fd2c17fb49aae90353ea1e0becb137101512f5dce7128.jpg)  
图5三种情况下的吞吐量  
Fig.5Throughput in three cases   
图6天线高负载情况下H-CRAN的全局吞吐量增加情况 Fig.6Global throughput increase of H-CRAN under high antenna load

SDHDE方案在设计时考虑了天线过载的情况，这些过载的天线并不能很好地承载新的用户设备。本文考虑在一些天线面临用户设备过载时，评估H-CRAN中的用户设备的吞吐量情况。除了移动路径中的8个天线中有几个可能被SDHDE评价为无线资源不足以外，吞吐量的测量方法与实验环境和前面实验中的方法和配置一致。此外，用户设备将以 $1 m / s$ 的速度沿着场景中的一条随机路径移动。

图6展示了在使用文献[7]的方案和本文提出的方案后用户设备的累计数据接收量。在这一实验中，设定参数 $\varphi$ 的阈值为-3dB作为负载均衡。之后，从一个服务器向当前连接到一个RRH的用户设备 $\nu$ 发送数据流。在45s后，从一个服务器产生数据流量到连接到与 $\nu$ 相同的 RRH 的用户设备。传送到的数据流持续 $3 0 \mathrm { ~ s ~ }$ ，因此在标记的45s后，该RRH的无线链路被阻塞。接下来，一旦从环境中收集到了数据，SDHDE 就会向 $\nu$ 发送一个恰当的指令触发切换操作：以切换到其他的代价最低的连接点。因此，在这种情况下，蜂窝单元将会是最好的切换选择。

一旦原始的RRH不再过载，标记为 $7 5 \mathrm { ~ s ~ }$ ，SDHDE求解0-1MCMCNF并向 $\nu$ 发送一个消息执行一个新的切换，切换回其原来的连接点，恢复原来的设置。与此同时，在文献[7]的方案中，用户设备 $\nu$ 无法感测到发生于无线链路中的阻塞，因此，即使吞吐量下降也不会触发切换。考虑到这两种情况下的百分比差异，相比文献[7]的方案，本文提出的SDHDE方案在仿真时间内提升了约 $1 7 . 6 4 \%$ 的数据接收量。

# 4 结束语

SDHDE使用SDN控制器所收集到的用户设备的切换信息和机器学习算法执行软件定义的决策。这一决策过程分为五个阶段：数据获取、数据管理、切换优化问题规划、切换时间策略、切换执行。这些阶段的目标是提升网络整体的性能。SDHDE决策通过执行一个0-1整数规划问题的求解来获得用户设备迁移的最优连接点。之后，用户设备根据SDHDE的决策迁移到相应的连接点。实验结果表明，SDHDE方案相比文献[7的方案具有更小的切换失败百分比。对于连接到过载的连接点时的用户设备，采用SDHDE方案的用户设备吞吐量相比文献[7]的方案提高了约 $1 7 . 6 4 \%$ 。

# 参考文献：

[1]杜秀丽，董泽龙，陈波，等．基于预判决和改进灰关联的异构网络切 换算法[J].计算机应用研究,2017,34(2):587-590.(Du Xiuli,Dong Zelong,Chen Bo,et al.Heterogeneous network handoff algorithm based on pre-judgment and improved grey correlation [J]. Computer application research,2017,34(2): 587-590.）   
[2]Beyene Y D,Jantti R，Tirkkonen O,et al.NB-IoT Technology Overview and Experience from Cloud-RAN Implementation [J]. IEEE Wireless Communications,2017,24(3): 26-32.   
[3]Ordonez-Lucena J,Ameigeiras P,Lopez D,et al.Network slicing for 5G with SDN/NFV:concepts,architectures,and challenges [J]. IEEE Communications Magazine,2017,55 (5): 80-87.   
[4]王蒙蒙,刘建伟,陈杰,等.软件定义网络:安全模型、机制及研究进展 [J].软件学报,2016,27(4):969-992.(Wang Mengmeng,Liu Jianwei, Chen Jie,et al.Software definition network: security model,mechanism and research progress [J].Journal of Software,2016,27(4):969-992.)   
[5]Thi MT,Huynh T,HasegawaM,etal.A rate allocation framework for multi-class services in software-defined networks [J]. Journal of Network& Systems Management,2017,25(1):1-20.   
[6]Yang Shunneng,Ho Shuwei,Lin Yibing,et al.A multi-RAT bandwidth aggregation mechanism with software-defined networking [J]. Journal of Network & Computer Applications,2016,61(C):189-198.   
[7]Ceylan O,Caglar A，Tugrel H B，et al.Small satellites rock a software-defined radio modem and ground station design for cube satellite communication [J].IEEE Microwave Magazine,2016,17 (3): 26-33.   
[8]Hobiger T,Haas R,Lofgren J. Software-defined radio direct correlation GNSS reflectometry by means of GLONASS [J].IEEE Journal of Selected Topics in Applied Earth Observations & Remote Sensing,2017, 9(10): 4834-4842.   
[9]Louta M,Bellavista P. Bringing always best connectivity vision a step closer: challenges and perspectives [J]. IEEE Communications Magazine,2013,51(2): 158-166.   
[10]耿道渠，朱大鹏，于彦平，等.6LoWPAN接入Internet中uNAT64机 制的研究与实现[J]．传感技术学报，2016,29(8)：1284-1289. (Gengdaoqu,ZhuDapeng,YuYanping,etal.Researchand implementation of uNAT64 mechanism for 6LoWPAN access to the Internet [J]. Journal of Sensing Technology,2016,29(8): 1284-1289.)   
[11]陆慧娟，刘亚卿，夏海霞，等.6LoWPAN网络中RPL路由协议的仿 真与研究[J].小型微型计算机系统,2016,37(1):83-87.(Lu Huijuan, Liu Yaqing, Xia Haixia,et al. Research and simulation of RPL routing protocol in 6LoWPAN[J]. Journal of Chinese Computer Systems,2016, 37(1): 83-87.)   
[12] Chiang Mengshu,Huang Chunming,Chau P B,et al.A forward fast media independent handover control scheme for proxy mobile IPv6 (FFMIH-PMIPv6) over heterogeneous wireless mobile network [J]. Telecommunication Systems,2017,65(4): 699-715.   
[13]Arslan Z,Erel M,Ozcevik Y,et al.SDoff:a software-defined offloading controller forheterogeneousnetworks[C]//Procof Wireless Communications and Networking Conference.Piscataway, NJ: IEEE Press,2014: 2827-2832.   
[14] Ferrus R,Koumaras H, Sallent O,et al. SDN//NFV-enabled satellite communications networks: opportunities,scenarios and challenges [J]. Physical Communication,2016,18 (P2):95-112.   
[15] Chen Shaipei，Yang Ji,Li Yong,et al.Multiconstrained network intensive vehicle routing adaptive ant colony algorithm in the context of neural network analysis [J].Complexity,2017,2017(1): 1-9.   
[16] Zhang Haijun, Jiang Chunxiao, Cheng Julian. Cooperative interference mitigation and handover management for heterogeneous cloud small cell networks [J].IEEE Wireless Communications,2015,22(3):92-99.   
[17] Huang Miaona,Chen Jun.A conflict avoidance scheme between mobility load balancing and mobility robustness optimization in self-organizing networks [J].Wireless Networks,2018,24(1):271-81.   
[18]张则强，胡扬，陈冲．求解拆卸线平衡问题的改进人工蜂群算法[J]. 西南交通大学学报,2016,51(5):910-917.(Zhang Zeqiang,Hu Yang, Chen Chong.An improved artificial bee colony algorithm for solving the disassembly line balance problem [J]. Journal of Southwest Jiaotong University,2016,51(5): 910-917.)