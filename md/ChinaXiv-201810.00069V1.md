# 基于蚁群算法的SDN数据中心网络大象流调度研究

李宏慧，杨光，路海亮，付学良，申志军(内蒙古农业大学 计算机与信息工程学院，呼和浩特 010010)

摘要：针对传统方法调度大象流时容易造成数据中心网络拥塞和负载不均衡等问题，提出一种基于蚁群算法的 SDN（software defined network）数据中心网络流量调度算法 ACO-SDN。对大象流调度问题建立整型线性规划ILP(integrallinear programing）模型，优化目标为最小化最大链路利用率。通过重定义蚁群算法的参数和操作求解 ILP模型，得到大象流重路由的最优路径。实验结果表明，与ECMP(equal-cost multi-path routing）和GFF（global firstfit）流量调度算法相比，ACO-SDN算法降低了网络最大链路利用率，有效地提高了网络对分带宽。

关键词：数据中心网络；软件定义网络；大象流调度；蚁群算法中图分类号：TP393.07 doi:10.3969/j.issn.1001-3695.2018.07.0430

# Flow scheduling of elephant flows in SDN data center network based on ant colony algorithm

Li Honghui, Yang Guang,Lu Hailiang,Fu Xueliang,Shen Zhijun (College ofComputer & Information Engineering Inner MongoliaAgricultural University,Hohhot Oloo18,China)

Abstract:The traditional methods maycause network congestionand load imbalance when scheduling the elephant flows in data center networks.Todeal withthese isuses,this paper proposed scheme ACO-SDN,which is based onACO(ant colony) algorithm in SDN(Software Defied Network)data center networks.Itbuiltan ILP（Integral Linear Programing）model according tothe flow scheduling problem,withtheobjectof minimizethemaximum linkutilization.Then,itemployedant colonyalgorithmtosolve the ILPmodel through redefining its parametersandoperations.Theoptimal route wasobtained for of rerouting elephant flows.The experimental results show that,in comparisons with ECMP(Equal-Cost multi-path Routing) and GFF(Global FirstFit)algorithms,ACO-SDNalgorithm lowers dow the maximum link utilizationrate,and efectively improves the network bisection bandwidth of networks.

Key words: data center network; SDN; elephant flow scheduling; ACO algorithm

# 0 引言

随着云计算、物联网和大数据技术的快速发展，数据中心已经成为现代计算基础设施的基石。数据中心内的通信量呈现以指数级增长的态势，对数据中心网络带宽的需求日益增加[1]。传统数据中心网络的树型结构存在着带宽受限、扩展性差等问题，无法满足数据中心内部通信量对网络带宽的需求[2]。为此，许多新型的数据中心网络体系结构[3\~6相继被提出，如Fat-Tree[3]、Monsoon[4]、BCube[5]、Helios[6]等。与传统数据中心网络架构相比，Fat-tree 拓扑结构相对比较简单，提供多条等价路径和更高的对分带宽7，便于实现网络负载均衡。

当今数据中心网络广泛利用等价多路径（ECMP）算法[8]进行流量调度。当到达一个目的节点有多条可用的等价路径时，ECMP对于到达同一目的地的多个数据流量，采用静态哈希散列将它们调度到多条等价路径上。由此ECMP可以实现网络的负载均衡以及数据流的快速转发。但是研究表明,数据中心内部的通信流量可以分为大象流和老鼠流[9i0]，其中，大象流是指传输的数据量超过链路带宽 $10 \%$ 的数据流。通过对数据中心评测，文献[9，10]发现， $90 \%$ 的数据流属于老鼠流，但是大象流传输了超过 $90 \%$ 的字节，绝大部分数据中心流量被携带在很小一部分数据流中。在实际应用中，这两种数据流的传输性能要求不同，大象流对网络吞吐量要求较高，而老鼠流对时延要求较高[II]。文献[2]研究表明，ECMP算法可以有效地调度大量的老鼠流，然而对于持续时间较长的大象流，ECMP可能会将多条大象流调度到同一条链路上，造成数据流碰撞、网络拥塞，使得网络负载不均衡，降低了数据中心网络的吞吐量。

作为一种新型的可编程网络技术，软件定义网络（SDN)[12]将控制平面从传统的网络设备中分离出来，通过在控制平面对流量的全局集中管控，可以方便灵活地调度网络流量和优化资源管理，为解决数据中心网络问题提供了新的机遇。

针对数据中心网络中ECMP调度大象流易于造成网络拥塞和负载不均衡等问题，在Fat-Tree 网络架构下，本文提出了一种基于蚁群算法的 SDN 数据中心网络动态的大象流调度机制（ACO-SDN）。首先建立流量调度问题优化数学模型（ILP），在满足所有大象流调度要求的前提下，优化目标为最小化网络的最大链路利用率；然后通过对蚁群算法参数和操作重定义来求解ILP，得到大象流的优化调度方案。ACO-SDN根据检测到大象流和网络链路利用率，从数据中心网络全局的角度对大象流进行重路由。仿真实验结果表明，与ECMP和GFF2算法相比，ACO-SDN 提高了数据中心网络的对分带宽，降低了最大链路利用率，实现了网络负载均衡。

# 1 相关工作

随着SDN技术的兴起，许多学者尝试利用SDN集中控制的方法对数据中心的流量进行管理，通过使用控制器实现对流量的实时调度。

文献[13]提出了一种动态的流量调度机制Hedera来最大化数据中心网络对分带宽，提出了全局首次适应（GFF）算法进行流量调度。对每一条大象流，GFF算法遍历所有可能的路径，根据路径上链路的剩余带宽找到第一条满足流带宽需要的路径。

但是文献[13]利用交换机监测大象流，造成交换机的额外开销比较大。针对该问题，文献[2]提出了低开销、有效的流量调度算法Mahout。该算法利用终端主机进行流量监测，一旦检测到大象流就会给控制器发信号，由控制器为大象流计算路径。

文献[14]研究了SDN数据中心的动态负载均衡调度（DLBS）问题。首先建立DLBS 问题的数学优化模型，目标是在保证动态负责均衡的条件下最大化网络吞吐量；然后提出了高效的启发式算法求解优化模型，实现各时间槽内的网络负载均衡。

文献[15]提出了无须大象流检测的多路径路由方案，使得数据流完成时间最小化。该方案基于超时阈值的数据流会被移除的特性，将大象流分成若干老鼠流，并路由到所有可能的路径上，由此实现数据中心网络的流量多路径路由。

文献[16]针对SDN数据中心网络的大象流调度问题，利用稳定匹配理论对给问题建模并求解该模型。目标是在避免网络拥塞的同时使得网络性能最优。文中提出了新的基于稳定匹配的大象流调度算法实现数据中心网络的高可用性和低时延。

文献[17]提出了一种SDN大数据中心网络的差异化地调度算法，依据检测到的数据流类别，利用加权多路径调度算法和基于封锁岛路径设置算法分别调度老鼠流和大象流。并设计了一种算法，根据当前链路利用率动态的重调度数据流来实现负载均衡。目标是获得高吞吐量、低延时和负载均衡。

针对Hedera 中的模拟退火算法未考虑当前网络链路带宽资源引起的流冲突等问题，文献[18]提出了基于模拟退火遗传算法的按需自适应（SAGA-AO）流量调度机制。该机制首先筛选出网络中需要调度的流；然后利用模拟退火遗传算法(SAGA)，根据当前链路带宽资源状况进行全局搜索，得到流调度路径，由此提高了数据中心网络的平均对分带宽。

针对现有的流量调度算法可能造成链路负载不均衡和核心交换机冲突加剧的问题，文献[19]提出了基于离散粒子群的流调度算法DPSOFS。该算法从全局角度进行流量调度，可以有效快速地减少流冲突，提高网络对分带宽。

文献[20]提出一种可扩展的基于SDN的数据中心网络分段路由流调度策略来解决大规模SDN 数据中心网络流量路由机制的可扩展性低引起的性能瓶颈问题。利用边缘交换机检查大象流，同时为满足其不同业务的QoS保证和网络可扩展性的要求，提出了在线最先适应算法。仿真结果表明该机制在降低了控制器总开销的同时提高了网络吞吐率。

文献[21]针对数据中心网络中大象流携带大量数据造成网络拥塞和负载不均衡的问题，提出基于SDN的大象流负载均衡机制EFLB。该机制以轮询方式监听网络，当负载超过阈值时，控制器将检测到的大象流拆分为多个老鼠流，并计算出负载最小的下一跳交换机，确保负载均衡。该机制提高网络吞吐量，降低了网络时延，更好地实现网络负载均衡。

# 2 蚁群流量调度算法

本章首先介绍基于蚁群算法的流量调度机制ACO-SDN，包括大象流检测和网络状态收集方法；然后建立流量调度问题的优化数学模型ILP；最后给出用于求解ILP模型的基于蚁群算法的流量调度方法。

# 2.1大象流流量调度机制ACO-SDN

本文提出的流量调度机制流程如图1所示。具体流量调度流程如下：

a)当数据中心网络收到来自主机的数据流以后，首先按ECMP 算法来调度数据流。同时，交换机中的 sflow代理采集网络状态信息，包括链路使用情况以及数据流信息，每隔2s将采集到的网络信息传输到控制器中的sflow收集器。

b)依据收到的信息，sflow收集器计算链路利用率以及识别大象流。如果一条数据流的带宽超过了链路容量的 $10 \%$ ，则被标记为大象流。

c)sflow收集器将大象流和链路利用率传给floodlight控制器。

d)控制器判断识别出的大象流途经链路利用率是否大于阈值 $6 0 \%$ 。如果是，转步骤e)，否则转步骤a)。

e)控制器根据当前链路使用状态，调用蚁群算法求解流量调度数学模型，为大象流计算出一条最优路径。将该路径转换为流表项下发给交换机。

f)交换机根据新的流表项重路由拥塞链路上的大象流。转步骤a)。

![](images/8c18a68b085ee8f035fbfe0596cd70a1f74810ae99c91422c33baf54f3d65450.jpg)  
图1大象流检测及调度流程

# 2.2流量调度问题数学模型

将数据中心网络拓扑表示为图 $G ( V , L )$ ，其中：$V = \{ \nu _ { 1 } , \nu _ { 2 } , . . . , \nu _ { n } \}$ 表示网络中所有节点的集合； $L$ 表示网络中所有链路的结合， $L _ { i }$ 为节点 $\nu _ { i }$ 的所有数据流流入链路集合， $L _ { i } ^ { \prime }$ 为节点 $\nu _ { i }$ 的所有数据流流出链路集合，链路 $l \in L$ 的容量为 $C _ { l }$ ，链路利用率为 $u _ { l }$ 。设当前网络需要调度的大象流集合为 $F$ ，大象流 $f \in F$ 的带宽为 $b _ { f }$ ,源点和终点分别为 $\mathbf { V } _ { s } ^ { f }$ 和 $\mathbf { V } _ { t } ^ { f }$ 。引入变量$x _ { l } ^ { f } \in \{ 0 , 1 \}$ 表示大象流 $f$ 的路由是否经过链路l。

链路利用率是指流经该链路的所有大象流带宽之和与链路容量的比值，如式（1）所示。

$$
u _ { l } = \frac { \underset { f \in F } { \sum } x _ { l } ^ { f } b _ { f } } { C _ { l } }
$$

最大链路利用率 $u ^ { \mathrm { m a x } }$ 是指网络中所有链路利用率的最大值，即

$$
u ^ { \mathrm { m a x } } = \operatorname* { m a x } \{ u _ { l } \} \qquad l \in L
$$

流量调度问题的数学模型如下所示：

$$
\operatorname* { m i n } \quad u ^ { \operatorname* { m a x } }
$$

s.t.

$$
\sum _ { f \in F } x _ { l } ^ { f } b _ { f } \leq C _ { l } \qquad l \in L
$$

$$
\sum _ { l \in { \cal L } _ { i } } x _ { l } ^ { f } b _ { f } - \sum _ { l \in { \cal L } _ { i } ^ { \prime } } x _ { l } ^ { f } b _ { f } = \left\{ \begin{array} { c c } { { - b _ { f } } } & { { \qquad \nu _ { i } = \nu _ { s } ^ { f } , f \in { \cal F } } } \\ { { b _ { f } } } & { { \qquad \nu _ { i } = \nu _ { d } ^ { f } , f \in { \cal F } } } \\ { { 0 } } & { { \qquad \nu _ { i } \in { \cal V } - \{ \nu _ { s } ^ { f } , \nu _ { d } ^ { f } \} } } \end{array} \right.
$$

$$
x _ { l } ^ { f } \in \{ 0 , 1 \} \qquad l \in L , f \in F
$$

其中：式（3）为流量调度问题的优化目标，即最小化网络的最大链路利用率；式 $( 4 ) \sim ( 6 )$ 为流量调度时应满足的约束条件。式（4）确保链路 $l$ 承载的数据流带宽总和不会超过该链路

的容量；式（5）为流守恒约束条件，确保数据流途经各中间结点时进入一个结点的流量等于离开该结点的流量；式（6）定义了变量的取值范围。

该数学模型属于整型线性规划（ILP）数学模型。为了得到大象流的路由调度方案，本文采用蚁群优化算法求解该模型。

# 2.3蚁群优化算法

为了求解上述ILP模型，蚁群算法和遗传算法都是强有力的工具。这两种算法的区别在于，蚁群算法利用信息素的积累及更新，最终得到最优解；而遗传算法具有快速进行全局解空间搜索能力，但由于没有利用反馈信息，导致冗余的迭代，求解效率较低[23]。

蚁群算法是由MarcoDorigo首先提出来的寻找最优路径的近似优化算法，其灵感来源于蚁群在觅食过程中发现最短路径的行为[24]。蚂蚁在其途经的路径上会释放信息素进行信息传递，蚁群内的其他蚂蚁会感知到信息素，并且会沿着信息素浓度较高路径行走，每只路过的蚂蚁又会释放信息素，从而形成了一种正反馈机制。经过一段时间以后，整个蚁群就会沿着最优路径到达食物源了。

利用蚁群算法求解上述ILP模型的基本思路就是，用蚂蚁觅食的行走路径表示大象流的可行路由解，整个蚂蚁群体的所有路径构成大象流可选路由的解空间。路径较短的蚂蚁释放的信息素量较多，随着时间的推进，较短的路径上累积的信息素浓度逐渐增高，选择该路径的蚂蚁个数也愈来愈多。最终，整个蚂蚁会在正反馈的作用下集中到最佳的路径上，此时对应的便是大象流路由的最优解。具体算法步骤如下所述：

a)初始化参数。参数分为网络状态参数，大象流参数和蚁群算法参数。其中：

(a)网络状态参数包括节点集合 $V$ 、链路集合 $L$ 、链路 $l \in L$ 的容量 $C _ { l }$ 和链路利用率为 $u _ { l }$ 。

(b)大象流参数包括需要调度的大象流 $f$ 的带宽 $b _ { f }$ 、源点 $\mathbf { V } _ { s } ^ { f }$ 和终点 $\mathbf { \nabla } \mathbf { v } _ { t } ^ { f }$ 、流的持续时间。

(c)蚁群算法参数包括蚂蚁个数 $m$ 、蚂蚁的初始位置 $V$ 、网络信息素总量 $\boldsymbol { Q }$ 、信息素启发式因子 $\alpha$ 、期望启发因子 $\beta$ 、信息素挥发系数 $\rho$ 、网络中各链路的初始信息素 $\tau$ 、蚂蚁途经的最多节点数 $N _ { \mathrm { m a x } }$ 和算法迭代次数 $I$ 、蚂蚁 $k$ 的禁忌链路表$T B _ { k }$ 。

b)用 $\tau _ { i j } ( t )$ 表示 $t$ 时间从节点 $i$ 到 $j$ 路径的信息素浓度，用$\eta _ { i j } ( t )$ 表示 $t$ 时间从节点 $i$ 到 $j$ 的启发式信息，即两节点间链路利用率的倒数， $\eta _ { i j } ( t ) = 1 / u _ { l }$ 。在遍历所有可行路径过程中，每只蚂蚁 $k$ 依据 $\tau _ { i j } ( t )$ 和 $\eta _ { i j } ( t )$ 按概率 $p _ { i j } ^ { k } ( t )$ 选择下一个节点 $j$ ，将蚂蚁 $k$ 经过的链路保存到禁忌链路表 $T B _ { k }$ 。其中：

$$
p _ { i j } ^ { k } ( t ) = \left\{ \begin{array} { l l } { \displaystyle \frac { \big [ \tau _ { i j } \big ( t \big ) \big ] ^ { \alpha } \big [ \eta _ { i j } \big ( t \big ) \big ] ^ { \beta } } { \sum _ { n \in V _ { k } ( i ) } \left[ \tau _ { i n } ( t ) \right] ^ { \alpha } \big [ \eta _ { i n } \big ( t \big ) \big ] ^ { \beta } } , \qquad } & { j \in V _ { k } ( i ) } \\ { 0 , \qquad } & { \sharp _ { 1 } ^ { \star } / \dag } \end{array} \right.
$$

$V _ { k } ( i )$ 表示蚂蚁 $k$ 下一步允许访问的节点集合，$V _ { k } \left( i \right) = V \cdot T B _ { k }$ 。

c)重复步骤b)，当所有蚂蚁途经的节点数达到 $N _ { \mathrm { m a x } }$ 后，停止本次迭代，迭代次数加1。

d)对于成功到达目的地的蚂蚁 $k$ ，依据其 $T B _ { k }$ 更新路径上的信息素浓度，更新公式为$\tau _ { i j } ( t + 1 ) = ( 1 - \rho ) \tau _ { i j } ( t ) + \rho \Delta \tau _ { i j } ( t )$ 。其中 $\Delta \tau _ { i j } ( t )$ 为路径上的信息素增量。对于蚂蚁 $k$ 没有经过的路径， $\Delta \tau _ { i j } ( t )$ 值为0,否则 $\Delta \tau _ { i j } ( t ) = Q / L _ { k }$ ， $L _ { k }$ 为第 $k$ 只蚂蚁在本次所走的路径长度。

e)完成规定的最大迭代次数 $I$ 后停止路径搜索，从所有到达目的地的蚂蚁禁忌表中按优化目标选出最优路径。

为了尽可能地避免蚁群算法陷入局部最优，本文采取以下两个措施：

a）差异化地对网络链路的信息素浓度进行初始化。将待调度大象流源点与终点之间的K-最短路径作为备选路径，对每条备选路径，将其途经链路的初始信息素浓度设置为信息素总量除以路径长度；而其他链路信息素浓度设置为0。

b）采用轮盘赌算法，增加蚁群算法的全局搜索能力，进一步优化解的质量[25]。

# 3 实验结果与分析

为了验证ACO-SDN优化算法的性能，本文利用Floodlight控制器和Mininet[22]仿真平台搭建Fat-tree 数据中心网络，采用平均对分带宽和最大链路利用率作为算法的性能评价指标。对分带宽指的是将一个网络中的所有主机分为对等两部分时，需要断开的最小链路数的带宽总和。对分带宽越大则网络的整体传输性能越强。通过与GFF算法和当前数据中心中普遍使用的ECMP算法进行比较，实验结果显示，ACO-SDN在平均对分带宽、最拥塞链路利用率等性能指标方面呈现优势。

# 3.1实验设置

在Mininet仿真平台上，本文搭建了 $\scriptstyle \mathbf { k = } 4$ 的Fat-tree 数据中心网络架构，如图2所示，所有的交换机均为OpenFlow交换机。各条链路的带宽均设定为 $1 0 0 \mathrm { M b / s }$ 。

![](images/9a26b5f7fb3f65f54c564c6adc0f94c41df6ff8ffebd02f41e371447f13f95b1.jpg)  
图2 $\scriptstyle \mathrm { K = 4 }$ Fat-Tree 拓扑结构

2）网络负载

目前，由于隐私和安全问题，无公开发表的数据中心网络负载数据可用。最近的有关数据中心网络流量特征的研究[9'26]表明，随着时空变化，通信量矩阵变化巨大。为了评估提出的大象流调度机制ACO-SDN，本文依据文献[3，13，18，19]确定所采用的通信模式。

本实验使用Iperf工具产生数据流量。每台主机产生的流长度不同，服从指数分布；流产生的时间遵从泊松分布；流的目的主机根据某种通信模式来确定，本文采用如下三种通信模式：

a）间隔模式Stride(i)。下标为 $x$ 的主机向下标为！ $( x + i )$ mod $n$ 的主机发送数据，其中 $n$ 为网络中主机数量。

b）交错模式Staggered (pEdge，pPod)。每台主机以概率EdgeP向同属于一个边缘交换机的主机发送数据，以概率pPod向同属于一个Pod 的主机发送数据，以概率1-EdgeP-pPod 向其他pod内主机发送数据。

c）随机模式Random。每台主机以相等概率随机向网络中其他的主机发送数据。

# 3）算法参数设置

如2.3节所述，蚁群优化算法的参数分为网络参数、大象流参数和蚁群算法参数。在进行模拟仿真实验时，这些参数的设置及依据如下：

a）网络参数。

网络状态参数中，节点集合 $V$ 为如图2所示的Fat-tree数据中心网络的所有节点，包括交换机和服务器节点。链路集合$L$ 为该网络的所有链路。每个链路的容量均为 $1 0 0 { \bf M } ^ { [ 2 1 ] }$ 。链路利用率 $u _ { l }$ 依据链路的当时负载情况，按式（1）计算。

b）大象流参数。

大象流 $f$ 的源点 $\mathbf { V } _ { s } ^ { f }$ 和终点 $\mathbf { v } _ { t } ^ { f }$ 均为服务器节点，根据采用的通信模式在生成大象流时进行设置。大象流定义为带宽超过链路容量 $10 \%$ 的数据流[2]，所以本文将大象流带宽 $b _ { f }$ 定义为10$\mathbf { M } { \sim } 2 0 \mathbf { M }$ 间的随机数。大象流的长度在大象流生成时设定。

c）蚁群算法参数。

蚁群算法参数的设置直接影响蚁群优化算法的性能。本文依据文献[27，28]的研究、流量调度问题的要求和多次仿真实验结果进行设置。

蚁群算法的主要参数设置及依据如表1所示。

表1蚁群算法主要参数值  

<html><body><table><tr><td>参数</td><td>设定值</td><td>建议值[1.2]</td></tr><tr><td>蚂蚁个数m</td><td>10</td><td>[0.6n,0.9n]</td></tr><tr><td>信息素启发式因子α</td><td>2</td><td>[1,5]</td></tr><tr><td>期望启发因子β</td><td>3</td><td>[1,5]</td></tr><tr><td>信息素挥发系数P</td><td>0.6</td><td>[0.5, 0.8]</td></tr><tr><td>信息素总量Q</td><td>100</td><td>100</td></tr></table></body></html>

蚂蚁的初始位置 $V$ 为待调度大象流的源点。蚂蚁 $k$ 的禁忌链路表 $T B _ { k }$ 设置为空值。通过多次实验测试，迭代次数在 $5 0 \sim$ 100间时，算法性能稳定，所以本算法将迭代次数 $I$ 设置为中间值75。在进行仿真实验时，两个节点之间的路径长度限定为11跳。相信在 $\scriptstyle \mathbf { k = } 4$ 的Fat-Tree网络拓扑中，超过11跳的路径是最优解的可能性非常小，所以将蚂蚁途经的最多节点数，即交换机数设定为10。各链路的初始信息素 $\tau$ 设置如第2.3节所

述。

# 3.2平均对分带宽比较

为了比较ECMP、GFF和ACO-SDN三种算法的平均对分带宽，本文采用上述三种通信模式分别进行了多次实验，每次实验持续约 $6 0 ~ \mathrm { s }$ ，取中间部分测量对分带宽。

# 1）Stride 通信模式

在Stride(i)间隔通信模式下，选取了 $i = 4$ 、 $i = 6$ 和 $i = 8$ 三种情况进行实验。在Stride(4)、Stride(6)和Stride(8)三种间隔模式下，图3展示了ECMP、GFF和ACO-SDN三种算法的平均对分带宽比较结果。从图3可以发现，在这三种间隔通信模式下，ACO-SDN 算法平均对分带宽均高于 ECMP 和 GFF 算法。ACO-SDN平均对分带宽与ECMP相比，提高了 $1 9 \% { \sim } 2 6 \%$ ，与GFF相比提高了 $8 \% { \sim } 1 7 \%$ 。

![](images/5271caa1551b2912b5594c003dd6432f2df7046d062865f670d8cfa36b08bb3d.jpg)  
图3Stride 模式下平均对分带宽比较

2）Staggered通信模式

在Staggered交错通信模式下，选取了Staggered（O，0.2）和Staggered（0.0.4）两种交错模式。每种交错模式选取两组实验。三种算法的平均对分带宽比较如图4所示。从图4可以看出，ACO-SDN算法在这两种通信模式下均优于ECMP和GFF流量调度算法。与ECMP相比，ACO-SDN算法平均对分带宽分别提高了 $8 \% { \sim } 2 1 \%$ ，与GFF相比，提高了 $5 \% { \sim } 1 5 \%$ 。

![](images/e0e783e3eb1f946b2f3d969fb423045d3913c0abf95824f8f83a2c17c4fd044c.jpg)  
图4Staggered模式下平均对分带宽比较

3）Random通信模式

在Random随机通信模式下，选取了三组实验Random1、Random2和Random3。三种算法的平均对分带宽比较结果如图5所示。从图5可以看出，ACO-SDN算法在平均对分带宽上均优于GFF和ECMP流量调度算法。与ECMP和GFF相比，ACO-SDN算法的平均对分带宽分别提高了 ${ \sim } 2 3 \%$ 和\~ $- 1 4 \%$ 。

![](images/80a8e9a0010ae025a4529c91be9884ebc3b56e3755b9405b5c5e4a547eeca1b7.jpg)  
图5Random 模式下平均对分带宽比较

综上所述，在三种不同的通信模式下，ACO-SDN 算法的平均对分带宽均高于ECMP和GFF算法。由于ECMP 随机将大象流调度到一条最短路径，未考虑当前链路状态，导致大象流冲突增多，所以在三种算法中平均对分带宽最低。GFF算法对于每个到达的大象流，根据当前链路利用率选取第一条满足条件的路径调度大象流，减少了数据流的冲突，与ECMP相比提高了网络的平均对分带宽。ACO-SDN 算法根据当前链路利用率计算出全局最优的路径来调度大象流，从而减少了大象流的冲突，提高了网络平均对分带宽。

# 3.3最大链路利用率比较

为了进一步验证算法性能，本文从最大链路利用率角度对ACO-SDN、ECMP和GFF算法进行了比较。最大链路利用率指的是全网范围内链路利用率的最大值，它反映了网络中链路带宽的使用情况。如果网络负载比较均衡，则数据流从源地址到目的地址的各条路径链路利用率应该比较均衡，才能充分利用网络中多路径的优势进行流量调度，减少数据流冲突，提高网络吞吐量。

实验选取了交错通信模式Staggered（0，0.3），以第一个Pod中的主机为数据源，向其他Pod中的主机发送数据流，流量带宽固定为 $2 0 \mathbf { M }$ ，持续时间为 $6 0 \mathrm { ~ s ~ }$ 。采用这种实验的目的是为了造成网络负载不均衡和较高的链路负载，从而可以更好地检测算法的最大链路利用率。在实验中，利用ECMP、GFF和ACO-SDN流量调度算法分别进行多次实验，直到得到比较稳定的结果。

![](images/3a180ce9e021fbf4994c966858876a29a1f24c744093bcb73ce8e63f04a4e9e0.jpg)  
图6Staggered 模式下最大链路利用率比较

三种算法的最大链路利用率的累计分布函数如图6所示。图中横轴为最大链路利用率（MLU），纵轴为MLU的累计分布函数（CDF），曲线表示不同算法下MLU的CDF。从图中可以看出，ACO-SDN算法最大链路利用率比GFF降低 $5 \%$ 左右，比ECMP降低 $8 \%$ 左右。ACO-SDN算法的MLU集中在$6 0 \% \sim 7 0 \%$ 间，而ECMP 算法的MLU集中在 $70 \% \mathrm { \sim } 8 0 \%$ 间。这主要是由于ACO-SDN 算法实时监测大象流路径上的链路，当发现某链路利用率超过阈值时，则启动ACO-SDN 算法根据当前网络链路状态计算出一条新路径来重路由大象流，降低了最大链路利用率，减少了大象流冲突。而ECMP算法是静态流量算法，在流量调度时随机将大象流调度到一条最短路径上，但是没有考虑当前的链路状态，增加了大象流冲突的可能性和最大链路利用率，所以ECMP的性能在这三种算法中性能最低。GFF 算法在路由大象流时考虑了网络的链路利用率，所以性能比ECMP有所提高；但是它根据大象流到达的先后顺序，将它们路由到第一条满足条件的路径上，所以最大链路利用率介于ACO-SDN和ECMP算法。

# 4 结束语

针对传统的流量调度方法易于造成大象流冲突，进而导致网络拥塞和性能下降的问题，本文提出了基于SDN的Fat-Tree数据中心网络大象流调度机制。首先对大象流调度问题建立整型线性规划(ILP)优化模型，并利用蚁群优化算法求解该ILP模型，得到大象流的近似最优调度方案。通过Floodlight 控制器和 Mininet 模拟平台进行了仿真实验。实验结果表明，本文提出的SDN数据中心网络大象流调度机制ACO-SDN优于ECMP和GFF算法，在Stride、Staggered 和Random三种通信模式下，与ECMP和GFF算法相比，ACO-SDN较大地提升了网络平均对分带宽，同时降低了最大链路利用率。

# 参考文献：

[1]蔡岳平，王昌平.软件定义数据中心网络混合路由机制[J].通信学报, 2016,37(4): 44-52.(Cai Yueping,Wang Changping. Software defined data center network with hybrid routing [J]. Journal on Communications,2016, 37 (4): 44-52.)   
[2]Curtis A R,Kim W,Yalagandula P.Mahout: low-overhead datacenter traffic management using end-host-based elephant detection [C]// Proc of IEEE INFOCOM. 2011: 1629-1637.   
[3]Al-Fares M,Loukissas A,Vahdat A.A scalable,commodity data center network architecture [C]// Proc of ACM SIGCOMM Conference on Applications,Technologies,Architectures,and Protocols for Computer Communications.20o8: 63-74.   
[4]Greenberg A,Lahiri P,Maltz D A,et al.Towards a next generation data center architecture:scalability and commoditization [C]// Proc of ACM Workshop on Programmable Routers for Extensible Services of Tomorrow. [S.1.] :ACM Press,2008: 57-62.   
[5]Guo Chuanxiong,Lu Guohan,Li Dan,et al.BCube:a high performance, server-centric network architecture for modular data centers [J].ACM

[6]Farrington N,Porter $\mathbf { G }$ Radhakrishnan S et al.Helios:a hybrid electrical//optical switch architecture for modular data centers [J].ACM SIGCOMMComputer Communication Review,2010,40 (4):339-350.

[7]Escudero-Sahuquillo J, Garcia PJ, QuilesFJ,et al.A new proposal to deal with congestion in InfiniBand-based fat-trees[J].Journal of Parallel & Distributed Computing,2014,74(1): 1802-1819.   
[8]Hopps C. Analysis of an equal-cost multi-path algorithm [S]. RFC 2992, 2000.   
[9]Kandula S,Sengupta S, Greenberg A,et al. The nature of data center traffc: measurements $\&$ analysis [C]//Proc of ACM SIGCOMM Conference on Internet Measurement.2009: 202-208.   
[10] Benson T,Akella A,Maltz DA.Network traffic characteristics of data centers in the wild [C]/ Proc of the 10th ACM SIGCOMM Conference on Internet Measurement.2010: 267-280.   
[11] Li Dan,Xu Mingwei, Zhao Hongze,et al. Building mega data center from heterogeneous containers[C]// Proc of IEEE International Conference on Network Protocols.[S.1.] : IEEE Press,2011: 256-265.   
[12]Mckeown N,Anderson T,Balakrishnan H,etal.OpenFlow:enabling innovationin campusnetworks [J]. ACM SIGCOMM Computer Communication Review,2008,38 (2): 69-74.   
[13]Al-FaresM,Radhakrishnan S,Raghavan B,et al.Hedera: dynamic flow scheduling for data center networks [C]//Proc of Usenix Symposium on Networked Systems Design and Implementation.2010: 281-296.   
[14] Tang Feilong,Yang LT, Tang Can,et al.A dynamical and load-balanced flow scheduling approach for big data centers in clouds [J]. IEEE Trans on Cloud Computing,2016,99(1),1-14.   
[15] Chakraborty Suchandra,Chen Chien.A low-latency multipath routing without elephant flow detection for data centers [C]// Proc of IEEE International Conference on High Performance Switching and Routing. Yokohama: IEEE Press,2016: 49-54.   
[16] Zhang Yuxiang,Cui Lin, Zhang Yuan. A stable matching based elephant flow scheduling algorithm in data center networks [J]. Computer Networks, 2017,120 (2017): 186-197.   
[17] Zhang Heteng，Tang Feilong，Barolli L.Efficient flow detection and scheduling for SDN-based big data centers [J/OL].Journal of Ambient Intelligence&Humanized Computing，2018，htps://doi.org/10. 1007/s12652-018-0783-6.   
[18]王文涛，郑芳，王玲霞，等．基于SDN的数据中心网络流量调度机制的 设计与实现[J].中南民族大学学报：自然科学版，2016，35(3): 135-140.(Wang Wentao, Zheng Fang，Wang Lingxia,et al. Design and implementation of flow scheduling mechanism based on SDN for data centernetwork [J].Journal of South-Central University for Nationalities: Nat. Sci.Edition,2016,35(3):135-140.)   
[19]林智华，高文，吴春明，等．基于离散粒子群算法的数据中心网络流量 调度研究[J].电子学报,2016,44(9):2197-2202.(Lin Zhihua,Gao Wen,

Wu Chunming,Li Yongyan.Data center network flow scheduling based on DPSO algorithm[J],Acta Electronica Sinica,2016,44(9): 2197-2202.)

[20]伊鹏，刘洪，胡宇翔.一种可扩展的软件定义数据中心网络流调度策略[J].电子与信息学报，2017,39(4):825-831.(Yi Peng,Liu Hong,HuYuxiang.A scalable traffic scheduling policy for software defined datacenter network [J]. Journal of Electronics & Information Technology, 2017,39 (4): 825-831.)

[21]金玲，束永安．数据中心网络中基于SDN的大象流负载均衡的研究[J/OL].计算机应用研究，2019(1):1-5.[2018-05-30].http://kns.cnki.net/kcms/detail/51.1196.TP.20180208.1714.094.html.(Jin Ling,ShuYongan.Research on load balancing of elephant flow based on SDN indata center network [J].Application Research of Computers,2O19 (1): 1-5.[2018-05-30]．http://kns.cnki.net/kcms/detail/51．1196.TP. 20180208.1714.094. html.)

[22] Lantz B,Heller B,Mckeown N.A network in a laptop: rapid prototyping for software-defined networks[C]//Proc of ACMWorkshop onHot Topics in Networks.2010:1-6.

[23]康岚兰，李康顺.蚁群算法在求解 TSP 问题上与遗传算法的对比研究[J].计算机系统应用,2008,17(10): 60-63.(Kang Fenglan,Li Kangshun.A comparison study of GA and ACA on TSP [J]. Computer Systems &Applications,2008,17(10):60-63.)

[24]段海滨，张祥银，徐春芳．仿生智能计算[M].北京：科学出版社 2011. (Duan Haipin, Zhang Xiangyin,Xu Chunfang. Bio-inspired computing [M]. Beijing: Science Press,2011.)

[25]马振.改进蚁群算法及其在TSP中的应用研究[D].青青岛：岛理工大 学,2016.(Ma Zhen.Research on the improvement of ant colony algorithm and its application in TSP[D]. Qingdao: Qingdao University of Technology, 2016.)

[26] Greenberg A,HamiltonJR,Jain N,et al.VL2:a scalable and flexible data center network [J].Communications of the Acm,20o9,54 (4): 95-104.

[27]詹士昌，徐婕，吴俊．蚁群算法中有关算法参数的最优选择[J].科技 通报,2003,19 (5):381-386.(Zhan Shichang,Xu Jie,Wu Jun.The optimal selection on the parameters of the ant colony algorithm [J].Bulletin of Science and Technology,2003,19(5): 381-386.)

[28]徐红梅，陈义保，刘加光，等．蚁群算法中参数设置的研究[J].山东 理工大学学报：自然科学版，2008，22(1):7-11.(Xu Hongmei,Chen Yibao,Liu Jiaguang，et al. The research on the parameters of the ant colonyalgorithm [J].Journal of Shandong University of Technology: Natural Science Edition,2008,22(1): 7-11.)