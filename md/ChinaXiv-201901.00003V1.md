# 边缘计算网络中面向负载均衡的调度机制

董谦1,2,3，马宇翔1,²，李俊1†

(1．中国科学院 计算机网络信息中心，北京 100190;2.中国科学院大学，北京 100049;3．佛山科学技术学院，广东佛山 528000)

摘要：在边缘计算的应用场景中，资源的部署和分配是重要问题。针对边缘计算网络中的负载均衡需求，提出一种基于集中控制的调度机制。首先决定在哪些网络节点部署边缘计算功能，再针对用户的数据和请求，在满足相关负载均衡约束的前提下通过调度尽量降低流量的平均端到端延迟。评估结果表明，边缘计算节点的数量、计算资源和网络资源的负载均衡程度均可能影响流量的平均端到端延迟。只需选择少量合适的节点作为边缘计算节点，再将计算资源和网络资源的负载均衡调配到合适程度即可有效降低平均端到端延迟。

关键词：边缘计算；集中控制；负载均衡；分段路由 中图分类号：TP393 doi:10.19734/j.issn.1001-3695.2018.10.0673

Load balancing oriented scheduling scheme in edge computing network

Dong Qian1,2,3, Ma Yuxiang1,2,Li Jun1† (1.Computer Network Information Center,ChineseAcademyof Sciences,Beijing100l90,China; 2.Universityof Chinese Academy of Sciences,Beijing 100049,China; 3.Foshan University,FoshanGuangdong 528000, China)

Abstract: In the application scenarioof edge computing,resource deployment and alocation are important issues.Inorder to adress the load balancing needs in edge computing network,this paper propose a scheduling scheme based on centralized control.This scheme decides which nodes todeployedgecomputing module firstly,thenconsideringusers'data andrequests,minimizes the average end-to-end delayof traffc through scheduling while meting the load balancing constraints.The evaluation results indicate that the number of edge computing nodes and the load balancing level of computing and network resources may affect the average end-to-end delayof trafic.Selecting asmallnumberof suitable nodes as edge computing nodes and making the load balancing level of computing and network resources appropriate can effectively reduce the average end-to-end delay.

Key words: edge computing; centralized control; load balancing; segment routing

# 0 引言

随着用户需求的日益多样化和网络流量的不断增长，边缘计算作为云计算及5G的一项关键技术将发挥重要作用。边缘计算是为了满足云计算及物联网、移动网络场景的需求，在终端以及云数据中心之间的网络节点部署计算功能，能降低数据中心的负担，节约能耗，还能提高数据处理的实时性[1]。边缘计算网络结构示意图如图1所示。

其中，网络主要划分为接入层和核心层2]；接入层用于连接用户设备，部署边缘计算节点，在图1中以云表示，且图1中省略了接入层网络节点之间、接入层网络节点与用户设备之间、用户设备之间（如果有）的互联链路；核心层用于连接接入层以及数据中心，在图1中以椭圆表示，实线表示核心层网络节点与接入层网络节点以及数据中心之间的互联链路。每个边缘计算节点都有计算、存储等能力；通常，来自用户的数据和请求经过边缘计算节点预处理后，需要转发到数据中心的流量相对来说会少得多[1]。

因此，在哪些网络节点部署边缘计算功能，如何在均衡这些节点的负载的前提下合理调度用户的数据和请求，便成为边缘计算网络所需考虑的重要问题。软件定义网络主要使用集中控制机制，具有全局视角，具备控制网络节点动作的能力。软件定义网络即集中控制机制用于边缘计算网络有突出优势[3]，本文基于集中控制提出了一种边缘计算网络中面向负载均衡的调度机制，具体来说，本文的主要贡献如下：

a)分析了边缘计算网络中的调度模型，提出了一种基于集中控制、面向负载均衡的调度机制；

b)提出了方法以决定具体在哪些网络节点部署边缘计算功能；

c)提出了方法以决定如何调度用户的数据和请求，在满足相关负载均衡约束的前提下尽量降低流量的平均端到端延迟。

# 1 相关工作

近年来，边缘计算得到了广泛关注，越来越多的研究致力于解决边缘计算在移动网络、物联网、车联网等领域的应用，以及边缘计算中计算、网络等资源的调度问题[4-6]。软件定义网络、分段路由（segmentrouting）等新兴网络技术逐渐应用于边缘计算领域[3.7.8]。

Shi等人[1总结了边缘计算的概念和原理，介绍了有代表性的应用实例，并展望了存在的主要挑战。Mao等人[主要关注移动边缘计算，讨论了系统部署、缓存机制、移动性管理、节能和隐私等方面的研究进展和挑战，还介绍了标准化方面的努力以及一些典型的应用场景。Mach等人[0]主要关注移动边缘计算中的计算卸载（offloading）用例，重点总结了完全卸载和部分卸载这两种情况的研究现状；完全卸载的主要目标是最小化执行延迟（delay)，或是在满足执行延迟约束的情况下最小化能耗，或是取得执行延迟与能耗间的平衡；部分卸载的主要目标是在满足执行延迟约束的情况下最小化能耗，或是取得执行延迟与能耗间的平衡；考虑如何进行合适的计算资源分配，并区分将计算分配到单个节点和分配到多个节点这两种类别。Sun等人[1I提出PRIMAL，考虑用户与计算节点的端到端延迟，以及计算和存储资源的迁移成本，以取得端到端延迟与迁移成本间的平衡。Wang等人[12]研究了边缘计算中的负载放置问题，以决定如何在边缘计算节点上放置应用。以上工作表明，在边缘计算的应用场景中，资源的部署和分配是重要问题，用户设备到边缘计算节点的端到端延迟是主要优化目标之一；然而，较少有工作关注计算资源和网络资源的负载均衡需求对端到端延迟的影响。

![](images/2bad4e6e1d731f2a2f05d1e00d5a68aa0920c16a9fc4811d8bf2728ff0eb5d9f.jpg)  
图1边缘计算网络结构示意图

另一方面，Baktir等人[3]提出将软件定义网络与边缘计算相结合，由控制器来管理数据流，完成服务编排和其他管理任务，通常包含服务发现、服务调试与迁移、性能调优与优化、用户切换等模块；其中，性能调优和优化模块主要关注网络和计算资源的使用情况，管理边缘计算节点上的负载。Filsfils等人[13]提出分段路由，可在灵活配置数据流转发路径的同时减轻控制器下发转发规则的负担；Hartert等人[14]提出集中式优化器DEFO，DEFO用于控制转发路径，而分段路由的灵活性以及可扩展性在其中发挥了重要作用；Desmouceaux等人[15]提出6LB，采用基于IPv6的分段路由技术引导数据包，设计负载均衡器。以上工作表明，集中控制机制与边缘计算相结合能优化负载均衡与网络性能；分段路由则支持对路径的灵活控制，增强了控制器的可扩展性。

因此，本文将负载均衡需求视作约束，在满足这些约束的前提下，基于集中控制和分段路由技术，通过调度尽量降低流量的平均端到端延迟。

# 2 整体架构和问题分析

基于对实际场景的抽象，结合本机制的设计思路，设图1中核心层以下的所有网络节点都支持分段路由技术，分段路由转发规则只需在源节点配置，增强了集中控制器的可扩展性；再将这些网络节点分为以下三类：

a)用户设备，除具备网络节点的基本功能外，还向边缘计算节点发送数据和请求；

b)边缘计算节点，除具备网络节点的基本功能外，还处理用户设备发送的数据和请求，具备计算和存储等资源，处理完毕后，将处理后的数据和对请求的响应返回到用户设备，或是发送到数据中心；

c)既非用户设备也无边缘计算能力的节点，即中间节点，只具备网络节点的基本功能。

本机制中除了网络节点外还有集中控制器，以一个常见的网络拓扑为例，包括6个用户设备、3个边缘计算节点和3个中间节点，整体架构和控制器功能示意图如图2所示。控制器只需接入边缘计算网络即可使用 NETCONF[16]等南向接□协议获取网络和各类资源的使用情况，配置设备，图2中未将此功能表示出来；带单向箭头的实线表示控制器根据要求选择合适的网络节点部署边缘计算功能；带箭头的虚线表示控制器接收用户设备的调度需求，下发分段路由转发规则给用户设备及边缘计算节点；网络节点间的实线表示它们之间的互联链路。

![](images/f24dc6261788c14a958d804cc995d2ff3926e5d0f75a4cadac55820f64119592.jpg)  
图2整体架构和控制器功能示意图

![](images/83e9b1b2b2dc645013b4f514df97e471885d86eb4125d53f8b911b61bce70156.jpg)  
Fig.1The structure of edge computing network   
Fig.2System architecture and the controller's function   
图3用户设备的调度需求处理步骤示意图  
Fig.3Processing steps of user equipment's scheduling demands

当边缘计算节点确定后，一旦用户设备有数据和请求产生，处理步骤如下：a)用户设备将数据和请求的流量信息发送给控制器；b)控制器根据当前网络和各类资源的使用情况，计算得出应将这些流量转发到哪些边缘计算节点，应通过哪些路径转发，将分段路由转发规则下发给用户设备，通知相关的边缘计算节点预留资源；如果处理后的数据和对请求的响应还需要发送给用户设备，控制器同样应根据当前网络和各类资源的使用情况，计算得出应通过哪些路径转发，将分段路由转发规则下发给边缘计算节点；c)用户设备收到控制器的响应后，按照控制器下发的规则发送流量；d)边缘计算节点接收流量后进行处理，收到控制器的响应后，按照控制器下发的规则发送流量，最终用户设备收到边缘计算节点发送的处理后的数据和对请求的响应。用户设备的调度需求处理步骤示意图如图3所示。

其中，用户设备与控制器间带单向箭头的虚线对应图2中带双向箭头的虚线，表示用户设备发送调度需求，控制器向用户设备下发转发规则；控制器与边缘计算节点间带单向箭头的虚线对应图2中带单向箭头的虚线，表示控制器向边缘计算节点下发转发规则；单向粗箭头表示用户设备与边缘计算节点间互相发送流量；图3中省略了中间节点，因其支持分段路由技术，故控制器无须向其下发转发规则。

网络拓扑通常表示为有向图，网络节点用 $i$ 表示，所有核心层以下的网络节点的集合用 $N$ 表示，链路是有向的，用$e$ 表示， $\boldsymbol { \mathscr { e } }$ 的集合用 $E$ 表示；任意某个 $i$ 只属于上述三类网络节点中的某一类，为便于说明节点所属的类别，可将用户设备、边缘计算节点分别再用 $s , t$ 表示， $s , t$ 的集合分别用 $s , T$ 表示；设 $t$ 上计算资源的处理能力为 $\nu _ { t }$ ，为方便计算，其单位与用户设备的发送速率一致，都为bps。设网络拓扑信息已知， $s$ 也已知， $T$ 通过3.1节中的方法得出；将 $T$ 中元素的个数用|T表示。

为简化讨论，设某个 $s$ 只有某个应用（容易扩展到多个应用并存的情况）产生的待发送流量，其大小即发送速率为$d _ { s }$ ，且 $d _ { s } { > } 0$ ，其中发送给某个 $t$ 的部分大小为 $d _ { s } ( t )$ ，最大计算资源利用率设置为 $\lambda$ ，且 $0 { \leqslant } \lambda { \leqslant } 1$ ，有

$d _ { s } ( t ) \geq 0$ （204 当允许将计算分配到多个节点时，$\left\lfloor d _ { s } ( t ) \in \{ 0 , d _ { s } \} \right.$ 当只允许将计算分配到单个节点时，

$$
\forall s \in S , t \in T
$$

$$
d _ { s } = \sum _ { t \in T } d _ { s } ( t ) , \forall s \in S
$$

$$
\sum _ { s \in S } d _ { s } ( t ) \leq \lambda \nu _ { t } , \forall t \in T
$$

$$
\sum _ { s \in S } d _ { s } \leq \nu _ { t } , \forall t \in T
$$

式(1)表明了当允许将计算分配到多个节点时及只允许将计算分配到单个节点时 $d _ { s } ( t )$ 的取值要求；式(2)表明 $d _ { s }$ 全部发送；式(3)表明每个 $t$ 接收的流量能被其实际允许使用的计算资源处理，显然，在满足式(1)(2)的前提下， $\lambda$ 越小则表明所有 $t$ 上的计算资源利用率可能的范围越小，故本文用 $\lambda$ 来衡量所允许的计算资源的负载均衡程度；式(4)表明即使只有一个边缘计算节点，当 $\lambda$ 为1时也能处理所有 $s$ 的待发送流量，即T最小可为1，保证了网络的健壮性。

另外， $t$ 接收 $d _ { s } ( t )$ 并处理后，再返回 $r _ { t } ( s )$ 到 $s$ ，为简化讨论，本文设所有 $s$ 的待发送流量的类型相同（容易扩展到多种类型并存的情况)， $s$ 的待发送流量的类型决定了系数 $a , a$ $\geqslant 0$ ，使

$$
r _ { t } ( s ) = \alpha d _ { s } ( t ) , \forall s \in S , t \in T
$$

一般来说， $\alpha$ 较小乃至为0表示 $s$ 的待发送流量主要是需要处理的数据； $\alpha$ 较大表示 $s$ 的待发送流量主要是需要处理的请求。

若已知网络拓扑信息则容易根据预设条件及分段路由的转发规则预先计算两节点间无环路的候选转发路径。将某条候选转发路径表示为 $p$ ，用 $p _ { e }$ 表示链路 $\boldsymbol { \mathscr { e } }$ 是否在路径 $p$ 上，若在则 $p _ { e }$ 为1，否则为0；考虑 $s$ 到 $i \in N \backslash S$ 和 $i \in N \backslash S$ 到 $s$ 的候选转发路径集合，分别用 $P _ { s i }$ 和 $P _ { i s }$ 表示，“\”是相对补集符号；用 $p$ 的跳数 $h _ { p }$ 衡量流量转发路径采用 $p$ 时的端到端延迟，对于每一对 $s , i$ ， $P _ { s i }$ 中的路径和 $P _ { i s }$ 中的路径一一对应且方向相反，故 $P _ { s i }$ 和 $P _ { i s }$ 中路径的跳数的最小值相同，用 $h _ { s i }$ 表示 $\operatorname* { m i n } _ { p \in P _ { s i } } \{ h _ { p } \}$ ， $w _ { p }$ 表示 $p$ 的路由代价即权重， $w _ { s i }$ 表示$\operatorname* { m i n } _ { \substack { p \in P _ { s i } \mathrm { H } _ { p } = h _ { s i } } } \{ w _ { p } \}$ ；对于节点 $i \in T$ ，由于其通常再用 $t$ 表示，相应的 $P _ { s i }$ 、 $P _ { i s }$ 、 $h _ { s i }$ 、 $w _ { s i }$ 也可用 $P _ { s t }$ 、 $\boldsymbol { P } _ { t s }$ 、 $h _ { s t }$ 、 $w _ { s t }$ 表示。再设路径

$p$ 上承载的流量大小为 $x _ { p }$ ，有

$$
d _ { s } ( t ) = \sum _ { p \in P _ { s t } } x _ { p } , \forall s \in S , t \in T
$$

$$
r _ { t } ( s ) = \sum _ { p \in P _ { t s } } x _ { p } , \forall t \in T , s \in S
$$

式(6)(7)表明 $d _ { s } ( t )$ 及 $r _ { t } ( s )$ 已分配转发路径。值得说明的是，在本文中，只允许将计算分配到单个节点时通常还要求转发路径只用某一条，以避免出现数据包重排[17]，由式(1)\~(2)(5)\~(7)，有

$$
x _ { p } \in \{ 0 , d _ { s } \} , \forall s \in S , t \in T , p \in P _ { s t }
$$

$$
x _ { p } \in \{ 0 , \alpha d _ { s } \} , \forall t \in T , s \in S , p \in P _ { t s }
$$

允许将计算分配到多个节点则无此限制，有

$$
x _ { p } \ : \geq 0 , \forall s \in S , t \in T , p \in P _ { s t } \cup P _ { t s }
$$

最后，定义流量的平均跳数 $H$ 为

$$
H = \frac { \displaystyle \sum _ { s \in S } \displaystyle \sum _ { t \in T } \sum _ { p \in P _ { s t } } x _ { p } h _ { p } + \displaystyle \sum _ { t \in T } \sum _ { s \in S } \sum _ { p \in P _ { t s } } x _ { p } h _ { p } } { \displaystyle \sum _ { s \in S } d _ { s } ( 1 + \alpha ) }
$$

由式(11)计算得到的 $H$ 用于衡量流量的平均端到端延迟。若还考虑网络资源，以链路容量为例，链路容量用 $c _ { e }$ 表示，最大链路利用率设置为 $\theta$ ，且 $0 \leqslant \theta \leqslant 1$ ，与 $\lambda$ 类似，本文用 $\theta$ 来衡量所允许的网络资源的负载均衡程度，有

$$
\sum _ { s \in S } \sum _ { t \in T } \sum _ { p \in P _ { s t } } x _ { p } p _ { e } + \sum _ { t \in T } \sum _ { s \in S } \sum _ { p \in P _ { s s } } x _ { p } p _ { e } \leq \theta c _ { e } , \forall e \in E
$$

式(12)表明实际允许使用的网络资源可能制约转发路径的选择，进而影响求得的 $H$ 。通常，在 $\scriptstyle a$ 、、 $\theta$ 等条件相同的情况下，求得的 $H$ 应尽量小，此时优化任务写为minimize$H$ 。特别的，若不考虑网络资源负载均衡约束，当优化任务为 minimize $H$ 时， $s$ 到 $t$ 和 $t$ 到 $s$ 所选择的转发路径的 $h _ { p }$ 应等于 $h _ { s t }$ ，此时只需考虑式(1)\~(3)，式(11)可化简为

$$
H = \frac { \displaystyle \sum _ { s \in S } \sum _ { t \in T } d _ { s } ( t ) h _ { s t } } { \displaystyle \sum _ { s \in S } d _ { s } }
$$

式(13)表明此时 $\alpha$ 不影响求得的 $H$ 0

# 3 机制设计

# 3.1边缘计算节点选择

选择边缘计算节点前，已知的信息包括网络拓扑信息，S及相应的 $d _ { s }$ ，所有 $s$ 到所有 $\scriptstyle { i \in M S }$ 的 $h _ { s i \setminus \ W { s i \cdot } }$ 。选择边缘计算节点时，不考虑计算资源和网络资源负载均衡约束，优化任务为minimize $H$ ；由于 $T$ 未知，应先设置最后得到的T等于$k _ { \circ }$

用 $u _ { i }$ 表示节点 $i \in N S$ 是否被选作 $t$ ，若 $i$ 被选作 $t$ 则 $u _ { i }$ 为1，否则为0；设某个 $s$ 产生的待发送流量中发送给某个 $i$ 的部分大小为 $d _ { s } ( i )$ ；设置一个足够大的数 $\mid m$ ，忽略单位只取数值，通常应使 $\operatorname* { m i n } _ { s \in S } \{ \operatorname* { m i n } _ { i \in N \backslash S } \{ m d _ { s } h _ { s i } \} \} \gg \operatorname* { m a x } _ { s \in S } \{ \operatorname* { m a x } _ { i \in N \backslash S } \{ d _ { s } w _ { s i } \} \}$ ，有

$$
\mathrm { m i n i m i z e } \ \sum _ { s \in S } \sum _ { i \in N \backslash S } d _ { s } ( i ) m h _ { s i } + \sum _ { s \in S } \sum _ { i \in N \backslash S } d _ { s } ( i ) w _ { s i }
$$

$$
0 \leq d _ { s } ( i ) \leq u _ { i } d _ { s } , \forall s \in S , i \in N \backslash S
$$

$$
d _ { s } = \sum _ { i \in N \backslash S } d _ { s } ( i ) , \forall s \in S
$$

$$
| T | = \sum _ { i \in N \backslash S } u _ { i } = k
$$

式(14)是优化求解器进行边缘计算节点选择时的优化任务，实际意义是在minimize $H$ 的前提下，借由 $m$ 来确保当有多个解使得 $H$ 最小时再根据路由代价在这些解中选择一个解作为最终解；式(15)由 $d _ { s } ( i )$ 的定义得到，还表明当 $i$ 未被选作$t$ 时 $d _ { s } ( i )$ 为0；式(16)由式(2)改写得到；式(17)表明最后得到的T等于 $k$ 。求解可使用Gurobi[18]等优化求解器，优化任务为式(14)，只需考虑式(15)\~(17)；求得 $T$ 后，对于 $i \in T$ ，由于其通常再用 $t$ 表示，相应的 $d _ { s } ( i )$ 、 $h _ { s i }$ 也可用 $d _ { s } ( t )$ 、 $h _ { s t }$ 表示，$H$ 由式(13)计算得到。

也可对 $s$ 设置待定集合 $\boldsymbol { s } ^ { \prime }$ ，设置两个临时变量 $o$ 和 $o$ ；，再使用下列算法

算法1边缘计算节点选择

1）输入网络拓扑信息， $s$ 及相应的 $d _ { s } , \ k , \ m$ ，所有 $s$ 到所有 $i \in N \backslash S$ 的 $h _ { s i }$ 、 $w _ { s i }$ （204

2) $T$ 初始化为空集， $s ^ { \th }$ 初始化为 $s$   
3) for $t e m p = 1$ 0 $k$ do   
4) $\omega ^ { \prime }  + \infty$   
5) 候选边缘计算节点初始化为空；   
6 for each $i \in M ( S \cup T )$ do   
7) $O ^ { \prime \prime }  m \sum _ { s \in S ^ { \prime } } d _ { s } h _ { s i } + \sum _ { s \in S ^ { \prime } } d _ { s } w _ { s i } \ \mathrm { ~ ; ~ }$   
8) if $\sigma { } ^ { \prime } { < } O ^ { ' }$ then   
9) $\omega ^ { \prime } {  } O ^ { \prime \prime }$   
10) 候选边缘计算节点 $ i$   
11) else   
12) end if   
13) end for   
14) 将候选边缘计算节点添加到 $T$   
15) for each $s \in S ^ { \prime }$ do   
16) if $\operatorname* { m i n } _ { t \in T } \{ h _ { s t } \} = \operatorname* { m i n } _ { i \in N \backslash S } \{ h _ { s i } \}$ then   
17) 在 $s ^ { \prime }$ 中去除 $s$   
18) else   
19) end if   
20) end for   
21) if $S ^ { ' }$ 为空集then   
22) Break;   
23) else   
24) end if   
25) end for   
26) $H \gets \frac { \displaystyle \sum _ { s \in S } d _ { s } \operatorname* { m i n } _ { t \in T } \{ h _ { s t } \} } { \displaystyle \sum _ { s \in S } d _ { s } } \ ;$   
27)if $\vert T \vert < k$ then   
28） 在 $N ( S \cup T )$ 中随机选择(k-T)个节点添加到 $T$   
29) else   
30)end if   
边缘计算节点选择算法的输出为 $T , \ H$ ，且   
$\nu _ { t }$ 配置边缘计算节点上的计算资源。

$\scriptstyle | T | = k$ ；根据 $T$ 及相应的

# 3.2调度计算

然后，控制器可进行调度计算。每次计算前，应设置 $\scriptstyle a$ ，$\lambda$ 和 $\theta$ 的值，通常调度计算时的条件越多则计算难度越大。

如果不考虑网络资源负载均衡约束，优化任务为minimize $H$ ，只需考虑式(1)\~(3)， $H$ 由式(13)计算得到。求解可使用优化求解器，也可使用下列算法

算法2调度计算

a)输入S及相应的 $d _ { s }$ ， $T$ 及相应的 $\nu _ { t }$ ，， $\mid m$ ，所有 $s$ 到所有 $t$ 的 $h _ { s t }$ 、 $w _ { s t }$

b)将所有 $s$ 的 $d _ { s } ( t )$ 初始化为0，对所有 $s$ 按照 $d _ { s }$ 从大到小的顺序依次计算，每次求当前 $s$ 的 $d _ { s } ( t )$ 时，不考虑还未计算过的 $s$ ，只考虑已计算过的 $s$ 和当前 $s$ ，在满足式(1)\~(3)的前提下使当前 $s$ 的 $m \sum _ { t \in T } d _ { s } ( t ) h _ { s t } + \sum _ { t \in T } d _ { s } ( t ) w _ { s t }$ 最小，后续计算中保持已计算过的 $s$ 的 $d _ { s } ( t )$ 不变，所有 $s$ 计算完成后，有解则暂存为解1;

c)将所有 $s$ 的 $d _ { s } ( t )$ 初始化为0，对所有 $s$ 按照 $d _ { s }$ 从小到大的顺序依次计算，每次求当前 $s$ 的 $d _ { s } ( t )$ 时，不考虑还未计算过的 $s$ ，只考虑已计算过的 $s$ 和当前 $s$ ，在满足式(1)\~(3)的前提下使当前 $s$ 的 $m \sum _ { t \in T } d _ { s } ( t ) h _ { s t } + \sum _ { t \in T } d _ { s } ( t ) w _ { s t }$ 最小，后续计算中保持已计算过的 $s$ 的 $d _ { s } ( t )$ 不变，所有 $s$ 计算完成后，有解则暂存为解2;

d)若第2、3行都有解则比较解1和解2，根据式(13)分别得出它们的 $H$ ，取相对较小者作为最终解及 $H$ ，若第2、3行只有一个有解则直接选择这个解及 $H$

调度计算算法的输出为所有 $s$ 的 $d _ { s } ( t )$ 、 $H$ ；控制器对每个不为0的 $d _ { s } ( t )$ 选择一条满足 $p \in P _ { s t }$ 及 $h _ { { p } } = h _ { { s t } }$ 条件的转发路径 $p$ ，使 ${ \boldsymbol { x } } _ { p } { = } { \boldsymbol { d } } _ { s } ( t )$ ；由 $d _ { s } ( t )$ 计算得到 $r _ { t } ( s )$ ，同样对每个不为0的 $r _ { t } ( s )$ 选择一条满足 $\boldsymbol { p } \in P _ { t s }$ 及 $h _ { p } = h _ { s t }$ 条件的转发路径 $p$ ，使$\scriptstyle { x _ { p } = r _ { t } ( s ) }$ ；根据 $x _ { p }$ 向用户设备及边缘计算节点下发相关配置。

如果还考虑网络资源负载均衡约束，优化任务为minimize $H$ ，考虑式(1)\~(3)(5)\~(10)(12)， $H$ 由式(11)计算得到，求解使用优化求解器，输出为所有 $x _ { p }$ ，只根据大于0的 $\scriptstyle x _ { p }$ 向用户设备及边缘计算节点下发相关配置。

# 4 实验评估与分析

本文从公开数据集SNDLib[19]获取实验网络拓扑信息，此拓扑中共有22个节点，预设的 $s$ 包含其中10个节点；链路容量均为 40000Mbps。再从SNDLib 的流量矩阵（trafficmatrix,TM）数据集中取出3个TM，对每个TM分别统计这10个 $s$ 的出流量之和作为各自的 $d _ { s }$ ，由这3个TM得到的 $s$ 及相应的 $d _ { s }$ 作为场景1、2、3；将 $\nu _ { t }$ 均设为40000Mbps。

先求得所有 $s$ 与所有 $\scriptstyle { i \in N \backslash S }$ 间的 $P _ { s i }$ 、 $P _ { i s }$ ，每一对 $s , i$ 的$P _ { s i }$ 、 $P _ { i s }$ 中有它们间满足 $\mathrm { S L D } ^ { [ 2 0 ] }$ （segment list depth）不大于2及无环路条件的路径[21]，继而得到所有 $s$ 到所有 $i \in N \backslash S$ 的$h _ { s i }$ 、 $w _ { s i }$ ，用于后续计算。进行边缘计算节点选择，不考虑计算资源和网络资源负载均衡约束，对于场景1，改变 $k$ 的值，对比使用优化求解器求得的结果与算法1求得的结果如图4所示。

![](images/f7ed04c1e9d328a9acff7e2aa8e93f27eae77d19d88bba2a65b45170520e115e.jpg)  
图4场景1下不同 $k$ 与求得的 $H$   
Fig.4 $K$ and corresponding $H$ in scenario 1

图4表明，当 $k$ 相同时，使用优化求解器求得的 $H$ 与算法1求得的 $H$ 相同，由于优化求解器求得的 $H$ 是相应条件下的最小值，因此使用算法1求得的 $H$ 也是相应条件下的最小值； $k$ 小于等于4时， $k$ 越大，求得的 $H$ 越小，而 $k$ 大于等于4时，求得的 $H$ 相同，原因在于当 $k$ 小于4时，有部分 $s$ 的 $\operatorname* { m i n } _ { t \in T } \{ h _ { s t } \} > \operatorname* { m i n } _ { i \in N \backslash S } \{ h _ { s i } \}$ ，而当 $k$ 增大到4以后，所有 $s$ 的$\operatorname* { m i n } _ { t \in T } \{ h _ { s t } \} = \operatorname* { m i n } _ { i \in N \backslash S } \{ h _ { s i } \}$ ，即使再增加t，也不可能求得更小的 $H$ 。另外，当 $k$ 分别取1、2、3、4时，使用优化求解器与算法1求得的 $T$ 也相同，而算法1是相对更为简单的贪心算法。上述结果表明，使用算法1选择少量合适的节点作为边缘计算节点，不仅可有效降低平均跳数，还简化了计算过程。

然后，将 $k$ 设置为4，基于场景1由算法1计算得出T,因此有所有 $s$ 到所有 $\mathbf { \Psi } _ { t }$ 的 $h _ { s t }$ 、 $w _ { s t }$ ；只允许将计算分配到单个节点用SN表示，允许将计算分配到多个节点用MN表示；进行调度计算，先不考虑网络资源负载均衡约束，对于场景1、2、3，改变λ的值，对比使用优化求解器求得的结果与算法2求得的结果如图5所示。

![](images/6b46533fc9b25f6b34bf28b151cd0e2ba08666c49fa29215e07ab2398db01f95.jpg)  
图5不考虑网络资源负载均衡约束时各场景下不同λ与求得的 $H$

Fig.5Aand corresponding $H$ in various scenarios without considering network resource load balancing constraints

图5表明，若λ较小，允许将计算分配到多个节点时使用优化求解器求得的 $H$ 比算法2求得的 $H$ 略小，只允许将计算分配到单个节点时使用优化求解器求得的 $H$ 比算法2求得的 $H$ 更小或与之相同；若 $\lambda$ 较大，使用优化求解器求得的 $H$ 与算法2求得的 $H$ 相同；通常，在λ增加到一定程度以前，当λ相同时，允许将计算分配到多个节点时求得的 $H$ 小于等于只允许将计算分配到单个节点时求得的 $H$ ；当 $\lambda$ 增加到一定程度后，继续增加也不会改变此时求得的 $H$ ，这说明所有 $s$ 的 $\operatorname* { m i n } _ { \substack { t \in T \boxplus d _ { s } ( t ) > 0 } } \{ h _ { s t } \} = \operatorname* { m a x } _ { t \in T \boxplus d _ { s } ( t ) > 0 } \{ h _ { s t } \} = \operatorname* { m i n } _ { t \in T } \{ h _ { s t } \}$ 。上述结果表明，所允许的计算资源的负载均衡程度对平均跳数可能有较大影响，特别是只允许将计算分配到单个节点时， $\lambda$ 越小则平均跳数可能会有较大增加，而允许将计算分配到多个节点则平均跳数可能增加的幅度相对较小；当λ较大时，算法2也能取得较好效果。

最后，仍将 $k$ 设置为4,基于场景1由算法1计算得出 $T$ 因此也有所有 $s$ 与所有 $t$ 间的 $P _ { s t }$ 、 $\boldsymbol { P } _ { t s }$ ；只考虑允许将计算分配到多个节点的情况，且取 $\lambda$ 为1；进行调度计算，考虑网络资源负载均衡约束，分别取 $\alpha$ 为0、0.5、1，对于场景1、2、3，改变 $\theta$ 的值，使用优化求解器求得的结果如图6所示。图6表明，在 $\theta$ 增加到一定程度以前， $\theta$ 越小，求得的$H$ 越大；当 $\theta$ 增加到一定程度后， $\theta$ 继续增加也不会改变此时求得的 $H$ ；当 $\theta$ 相同时， $\scriptstyle a$ 为0或1时求得的 $H$ 相同，这是由于 $s$ 发送和接收的流量方向相反，接收流量大小为0或等于发送流量大小则求得的 $H$ 实际上只取决于发送流量；在$\theta$ 增加到一定程度以前且当 $\theta$ 相同时， $\scriptstyle a$ 为0或1时求得的 $H$ 大于 $\alpha$ 为0.5时求得的 $H$ ，这是由于 $s$ 发送和接收的流量不相等且接收的流量不为0时，两者中较大者受网络资源负载均衡约束的限制相对较小者有更大比例的流量使用跳数更多的路径转发。上述结果表明，所允许的网络资源的负载均衡程度也有可能影响平均跳数， $\theta$ 越小则平均跳数可能增加。

# 5 结束语

本文针对边缘计算网络中的负载均衡需求，提出了一种基于集中控制的调度机制，在满足相关负载均衡约束的前提下通过调度尽量降低流量的平均端到端延迟，基于模型进行分析，提出了算法以决定具体在哪些网络节点部署边缘计算功能和如何调度用户的数据和请求。评估结果表明，边缘计算节点的数量、计算资源和网络资源的负载均衡程度均可能影响流量的平均端到端延迟；只需选择少量合适的节点作为边缘计算节点，再将计算资源和网络资源的负载均衡调配到合适程度，即可有效降低平均端到端延迟。下一步工作计划在已有基础上，考虑如何在链路、风险共享链路组（shared risklinkgroup）、节点等出现故障的情况进行合理调度，且兼顾集中控制器的可扩展性以及边缘计算网络的节能需求。

![](images/23567495ec9cb6cd5178b848c489d63c5f1bd0b48b13a7160b6f9da374ab82cb.jpg)  
图6各场景下不同 $\theta$ 与求得的 $H$   
Fig.6 $\boldsymbol { \Theta }$ and corresponding $H$ in various scenarios

# 参考文献：

[1]Shi Weisong,Cao Jie,Zhang Quan,et al.Edge computing:vision and challenges [J].IEEE Internet of Things Journal,2016,3 (5): 637-646.   
[2]Byers C C.Architectural imperatives for fog computing:use cases, requirements，and architectural techniques for FOG-enabled IoT networks [J].IEEE Communications Magazine,2017,55 (8):14-20.   
[3]Baktir A C,Ozgovde A,Ersoy C.How can edge computing benefit from software-defined networking:a survey，use cases,and future directions [J].IEEE Communications Surveys & Tutorials,2017,19 (4): 2359-2391.   
[4] Zhao Zhiwei,Min Geyong，Gao Weifeng，et al.Deploying edge computing nodes for large-scale IoT:a diversity aware approach [J]. IEEE Internet of Things Journal,2018,5(5): 3606-3614.   
[5]Zuo Yuan,Wu Yulei,Min Geyong,et al.Learning-based network path planning for traffic engineering [J].Future Generation Computer Systems,2019,92: 59-67.   
[6]Ma Yuxiang，Wu Yulei,Ge Jingguo,et al.An architecture for accountable anonymous access in the Internet-of-Things network [J]. IEEE Access,2018,6:14451-14461.   
[7]Cheng Xiangle,Wu Yulei,Min Geyong，et al.Network function virtualization in dynamic networks:a stochastic perspective [J].IEEE Journal on Selected Areas in Communications,2018.   
[8]Li Jianhua, Jin Jiong,Yuan Dong,et al. EHOPES:data-centered fog platformforsmart living [C]//ProcofIEEE International Telecommunication Networks and Applications Conference.2015: 308-313.   
[9]Mao Yuyi, You Changsheng,Zhang Jun,et al.A survey on mobile edge computing: the communication perspective [J].IEEE Communications Surveys & Tutorials,2017,19(4):2322-2358.   
[10] Mach P,Becvar Z.Mobile edge computing:a survey on architecture and computation offloading [J]. IEEE Communications Surveys & Tutorials,2017,19 (3):1628-1656.   
[11] Sun Xiang,Ansari N.PRIMAL:profit maximization avatar placement for mobile edge computing[C]//Proc of IEEE International Conference on Communications.2016:1-6.   
[12] Wang Shiqiang，Zafer M,Leung K K.Online placement of multi-component applications in edge computing environments [J]. IEEEAccess,2017,5:2514-2533.   
[13] Filsfils C,Nainar N K,Pignataro C,et al. The segment routing architecture [C]// Proc of IEEE Global Communications Conference. 2015: 1-6.   
[14]Hartert R,Vissicchio S,Schaus P,et al.A declarative and expressive approach to control forwarding paths in carrier-grade networks [J]. ACM SIGCOMM Computer Communication Review,2015,45 (4): 15-28.   
[15] Desmouceaux Y,Pfister P,Tollet J,et al.6LB: scalable and application-aware load balancing with segment routing [J].IEEE/ACM Transactions on Networking,2018,26 (2):819-834   
[16] Enns R,Bjorklund M,Schoenwaelder J,et al.RFC 6241,Network configuration protocol (NETCONF) [S]. IETF 2011.   
[17] Kandula S,Katabi D,Sinha S,et al.Dynamic load balancing without packet reordering [J].ACM SIGCOMM Computer Communication Review,2007,37 (2):51-62.   
[18] Gurobi Optimization，LLC.Gurobi optimizer referencemanual [EB/OL].[2018-11-23]. http://www. gurobi. com.   
[19] Orlowski S,WessälyR,Pi6ro M,et al.SNDlib 1. O-survivable network design library [J].Networks,2010,55 (3):276-286.   
[20] Moreno E,Beghelli A,Cugini F. Traffic engineering in segment routing networks [J].Computer Networks,2017,114: 23-31.   
[21]董谦，李俊，马宇翔，等．软件定义网络中基于分段路由的流量调度 方法[J].通信学报，2018 39(11):23-35.(Dong Qian,Li Jun，Ma Yuxiang,et al. Traffic scheduling method based on segment routing in software-defined networking [J]. Journal on Communications,2018 39 (11): 23-35.)