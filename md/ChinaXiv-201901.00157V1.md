# 具有高效确认机制的双层卫星网络多径路由协议

孙伟超，梁俊，肖楠，丁然(空军工程大学 信息与导航学院，西安 710077)

摘要：针对资源受限的LEO卫星网络中传统单路径路由协议数据传输速率较低的问题，基于GEO/LEO双层卫星网络模型，提出一种基于网络编码（NC）的双层卫星网络多径路由协议（N-NCMR）。首先，通过GEO卫星为LEO卫星网络计算路由减轻LEO卫星的负担,结合NC技术，动态地沿着多个不相交路径传输数据流的不同部分;其次，设计了一种高效的延迟确认机制加速数据传输，源节点在接收到前一组的确认（ACK）消息之前可以连续发送后续的组。仿真结果表明，该路由协议显著提高了LEO卫星网络的吞吐量和数据传输效率。

关键词：卫星网络；路由算法；网络编码；多径路由；吞吐量 中图分类号：TP393.04 doi:10.19734/j.issn.1001-3695.2018.10.0770

# Multipath routing protocol for two-layered satellite networks with efficient acknowledgement mechanism

Sun Weichao, Liang Jun, Xiao Nan, Ding Ran (SchoolofInformation&Navigation,AirForce EngineeringUniversity,Xi'an71oo77,China)

Abstract:Aiming at the problem of low data transmision rate of traditional single path routing protocol in resource-constrained LEO satelite network,based on GEO/LEO double-layer satelite network model,a new multi-path routing protocol (N-NCMR) for double-layer satelite network basedon network coding (NC) is proposed.Firstly,GEO satellite is used tocalculaterouting forLEOsatellte network,andNCtechnology isused to transmit diferent partsof data stream along multiple disjoint paths dynamically，thusreducing the burden of LEO satelite.Secondly，a delayed acknowledgment mechanism is designed to accelerate data transmision. Source nodes can send subsequent groups continuously before receiving the previous set of acknowledgment (ACK)messages.The simulation results show that the routing protocol significantly improves the throughput and data transmission efficiencyofLEO satelite network.

Key words: satellite network; routing algorithm; network coding; multipath routing; throughput

# 0 引言

LEO卫星网络具有良好的全球覆盖特性，正成为越来越重要的通信基础设施[1]。许多基于卫星网络的应用，如远程图像传输，需要较高传输速率和容量[2]。但卫星网络星上存储和处理能力有限，星间链路（ISLs）间断性连接、传输时延长，网络拓扑动态变化等特性使得LEO卫星网络难以提供可靠的信息传输服务[3]，传统的单路径路由协议不能满足高速率信息传输的要求。

多径路由同时在多条路径上传输数据包，不仅可以显著提高网络吞吐量，而且可以显著减少端到端（E2E）时延[4]。文献[5]提出了一种负载均衡多径路由算法，使得LEO卫星网络具有更强的实时传输海量数据的能力。文献[6]提出了一种基于多径的LEO卫星网络拥塞控制策略，具有良好的可扩展性。文献[7]提出了一种路径分段的LEO卫星网络多径路由协议，能较好地适应网络状态和业务需求。然而，以上文献都没考虑到在多个路径上对数据包进行协调带来的带宽和时间上的额外开销。

网络编码（NC）通过在中间节点对数据包进行编码来提高网络吞吐量[8]。基于NC的多径路由可以解决多径间复杂的协调问题，节省带宽，提高负载均衡。近年来国内外许多学者对基于NC的多径路由协议进行了研究。2007年，为了提高网络吞吐量，Chachulski等人[9]提出了MORE方法，首次将NC技术和路由技术相结合。文献[10]在MORE的基础上，提出了OMNC，通过综合考虑多径路由和速率控制提高了网络吞吐量。文献[11]提出了CCACK,使用来自下游节点的累积编码应答减少了冗余传输。文献[12]提出了ONCR，可以根据最小传输成本选择转发器。文献[13]将卫星网络与NC 结合，提出了一种基于网络编码LEO卫星网络多径路由协议NCMCR，显著提高了网络吞吐量。

然而，LEO卫星网路有限的存储和计算能力使其节点难以承担编码及路由计算带来巨大负担[14]。基于以上分析，基于GEO/LEO双层卫星网络架构[15]，提出了一种新的基于网络编码的多径路由协议（N-NCMR）。

# 1 系统模型和问题描述

# 1.1系统模型

双层卫星网络的GEO层由三个地球静止轨道卫星组成，LEO层由 $N$ 个不相交平面组成，每个平面由 $\mathbf { \nabla } _ { M }$ 个倾角为$2 \pi / M$ 的卫星组成，如图1所示。其中，此模型中存在三种类型的ISLs：层间ISLs，面内ISLs和面间ISLs。每颗LEO卫星最多具有5条ISLs，其中一条与GEO卫星相连，所以在LEO层最多具有4个相邻卫星，即 $Q \leq 4$ 0

在某一时刻，如果一个LEO卫星在某个GEO卫星的满足最小仰角的足印区内，则称这个LEO卫星下方的覆盖区域为该GEO卫星的一个组成员。GEO卫星的所有组成员组成的集合称为GEO卫星的组成员集，称该GEO卫星为其组成员的组管理者[15]。

![](images/9e56f2117f5599d5a513fd8624a04b3754c83e3cbf4d27a3f0a9a2410f6e723c.jpg)  
图1双层卫星网络模型  
Fig.1Double-Layer satellite network model

将LEO层用无向图 $G = ( V , E )$ 表示，其中 $V$ 是卫星集合，$E$ 是ISLs集合。LEO层网络的拓扑结构由于ISLs间断性连接而随时间周期性变化。因此采用基于虚拟拓扑的方法，将连续时间划分为一系列离散时隙，使网络拓扑在每个时隙内保持不变。

同时，在任意时隙内，如果存在链路状态变化，即出现断开或连通的情况，都假设在当前时隙内这些链路均为断开的，而在下一个时隙开始时才连通链路，这样就保证了在每个时隙内网络拓扑是固定不变的。

表1符号及含义 Tab.1 Symbols and meanings   

<html><body><table><tr><td>符号 含义</td><td></td></tr><tr><td>K</td><td>并行数据流的数量</td></tr><tr><td>f</td><td>第k个数据流𝑓k=（sk,d）（1≤k≤K），源节点为s，目的节 点为dk</td></tr><tr><td>tf</td><td>数据流fk的吞吐量</td></tr><tr><td>V(E𝑘)</td><td>数据流f经过的节点集</td></tr><tr><td>x(t)</td><td>时隙t内，f在链路li上的有效数据传输率</td></tr><tr><td>b(t)</td><td>f在时隙t，从卫星节点i到j的传输率</td></tr><tr><td></td><td>LEO卫星i和j之间的星间链路</td></tr><tr><td>Pij</td><td>链路的丢包率</td></tr><tr><td>i(t）</td><td>li的指示器：若lj(t)=0，表示LEO卫星节点i和j之间</td></tr><tr><td></td><td>可以直接通信；否则lj(t)=1</td></tr><tr><td>Bi</td><td>LEO卫星i的通信容量</td></tr><tr><td>Ni(t)</td><td>时隙t内，LEO卫星i的相邻节点</td></tr><tr><td>Pk</td><td>数据流f的路径集，具有|P条路径</td></tr><tr><td>Pi(p')</td><td>编码后的数据包(编码包）</td></tr></table></body></html>

# 1.2问题描述

将基于NC的多径路由问题定义为寻找LEO卫星网络的最优路径集，并以最大化系统吞吐量为目标[13]。所用符号见表1。

吞吐量最大值为

$$
\sum _ { k \in { \cal K } } t _ { f _ { k } }
$$

需满足以下约束条件：

$$
\sum _ { p \in P ^ { k } } \sum _ { l _ { i j } \in p } x _ { i j } ^ { k } ( t ) - \sum _ { p \in P ^ { k } } \sum _ { l _ { i j } \in p } x _ { j i } ^ { k } ( t ) = \pi ( i , k ) , \forall i \in V ^ { k }
$$

$$
\sum _ { k \in K } \sum _ { p \in P } \sum _ { l _ { i j } \in p } b _ { i j } ^ { k } \left( t \right) + \sum _ { k \in K } \sum _ { p \in P } \sum _ { l _ { i j } \in p } b _ { j i } ^ { k } \left( t \right) \leq B _ { i } , \forall i \in V , \forall j \in N ^ { i } \left( t \right)
$$

$$
\left| \mathbf { P } ^ { k } \right| \leq \mathbf { Q } , \ 1 \leq k \leq \mathbf { K }
$$

$$
\sum _ { 1 \le i \le \omega } { c _ { i } } ^ { ' } p _ { i } ^ { \prime } = \sum _ { 1 \le i \le \omega } { c _ { i } } p _ { i }
$$

$$
b _ { i j } ^ { k } ( t ) ( 1 - \rho _ { i j } ) \geq x _ { i j } ^ { k } ( t ) , \forall i \in V ^ { k } , \forall l _ { i j } \in E ^ { k }
$$

$$
\widetilde { l } _ { i j } ( t ) = \widetilde { l } _ { j i } ( t ) , \forall l _ { i j } \in E
$$

$$
x _ { i j } ^ { k } ( t ) \geq 0 , \forall i \in V ^ { k }
$$

$$
b _ { i j } ^ { k } ( t ) \geq 0 , \forall l _ { i j } \in E ^ { k }
$$

其中： $\pi ( \mathrm { i } , \mathrm { k } ) = \left\{ { \begin{array} { r } { t _ { f _ { k } } , \ i f i = s _ { k } } \\ { - t _ { f _ { k } } , \ i f i = d _ { k } } \\ { 0 , \ o t h e r w i s e } \end{array} } \right.$

式（1）表明，本文的目标是优化LEO卫星网络的吞吐量；式（2）为数据流守恒约束条件，对于每个中间节点，数据包的输出速率一定等于输入速率；式（3）表明数据流量应该受到每个LEO卫星节点容量的限制；式（4）表示多径数量受到ISLs的限制。在基于NC的路由中，一个组由 $\omega$ 个线性无关的编码包组成；式（5）可以保证一组原始数据包可以被路径中的任意节点从以不同系数编码的另一组数据包中解出，这里 $c = ( c _ { 1 } , c _ { 2 } , \cdots , c _ { \omega } )$ 和 $\boldsymbol { c } ^ { \prime } = ( c _ { 1 } ^ { \prime } , c _ { 2 } ^ { \prime } , \cdots c _ { \omega } ^ { \prime } )$ 是两个不同的系数向量；式(6)表示， $f _ { k }$ 从节点 $i$ 到 $j$ 的有效传输率不应低于 $x _ { i j } ^ { k } ( t )$ ：式（7）表示ISLs都是双向对称的；式（8）（9）保证数据传输率为非负值。由于上述问题具有多个复杂变量，且同时具有整数约束，如式（4）和非线性约束，如式（5），因此可以看成具有多个复杂变量的混合整数非线性规划问题（MINLP），根据具有相似工作的文献[16],一般为NP难问题。

# 2 基于NC的多径路由方案

LEO卫星数据最终通过多个路径传送到目的卫星 $d _ { k }$ 。由于LEO卫星不断绕地球运动，任何 $d _ { k }$ 的最大通信持续时间（即可用传输窗口）是有限的[17]。因此就要面临如下三个关键问题：a)如何在 $s _ { k }$ 和 $\boldsymbol { d } _ { k }$ 之间选择 $P ^ { k }$ ，即多径建立问题;b)在一个时隙内， $s _ { k }$ 应该向 $d _ { k }$ 发送多少数据，过多的数据会导致超过 $d _ { k }$ 的可用传输窗口而丢失，即期望传输数据包(ETP)。${ \mathrm { c } } ) s _ { k }$ 为每一组发送多少数据包才能保证 $d _ { k }$ 成功解码该组。

# 2.1N-NCMR协议中的网络编码方案

N-NCMR使用在有限域 $G F ( 2 5 6 )$ 上的随机线性网络编码来对组中的数据包进行编码。随机系数可以保证编码包与先前的数据包是线性无关的[18]。

一个组由 $\omega$ 个线性无关数据包 $\{ \mathrm { p i } | 1 \le \mathrm { i } \le \omega \}$ 组成。为了将一组数据包从 $s _ { k }$ 传输到 $\boldsymbol { d } _ { k }$ ， $s _ { k }$ 首先将 $\omega$ 个数据包 $p _ { 1 } , p _ { 2 } , \cdots p _ { \omega }$ 线性组合并且每次使用不同的系数向量 $c _ { i }$ 向其下游节点发送数据包 $\sum _ { 1 \le i \le \omega } c _ { i } p _ { i }$ 。中间节点使用具有不同随机系数的向量 $c _ { i } ^ { \prime }$ 独立地对 $\omega$ 个编码包再次进行编码。由于 $\sum _ { 1 \le i \le q } c _ { i } ^ { \prime } p _ { i } ^ { \prime } = \sum _ { 1 \le i \le \omega } c _ { i } p _ { i }$ ，发送的数据包也是原始数据包的线性组合。最后， $d _ { k }$ 采用高斯消元法来判别传入的数据包是否是线性无关的。当 $\boldsymbol { d } _ { k }$ 收集到 $\omega$ 个线性无关数据包时，将对这组数据包进行解码来恢复原始数据包，并将它们传输到上层。

# 2.2多路径建立

针对第一个问题，采用GEO卫星为LEO卫星计算路由，LEO卫星负责转发的模式。具体的路径建立过程分为以下几步:

a）在每一个时隙的开始时刻，每个LEO卫星不断测量其与相邻节点之间的时延信息，它是传输时延、传播时延和队列时延的总和，并在当前时隙内将此时延信息报告给它所在的组成员集的组管理者。

b)组管理者收到所有组成员报告来的时延信息后，为了获得LEO层的全部拓扑信息，会形成一个时延报表，准备和其他组管理者交换时延报表信息。

c)在GEO层，每个组管理者卫星与另外2个组管理者卫星交换各自收集到的LEO层信息。

d)每个组管理者卫星收集到全网的信息后按照多重Dijkstra 算法计算 $s _ { k }$ 和 $\boldsymbol { d } _ { k }$ 之间的路径，并将计算得到的路由表下发给 $s _ { k }$ 。

e) $s _ { k }$ 收到它的组管理者下发的路由表后，通过查找路由表将编码包转发至下一跳。可见，路由的计算是由上层的GEO卫星完成的，减轻了对LEO卫星的计算负担。

多重Dijkstra算法是在经典Dijkstra算法基础上改进而成的，能够根据网络拓扑计算出多条从 $s _ { k }$ 到 $\boldsymbol { d } _ { k }$ 的不相交路径集$P ^ { k }$ 。其基本思想是循环运行Dijkstra 算法来获得路径集。在每轮之后，在LEO卫星网络拓扑图的节点集 $V ^ { k } ( E ^ { k } )$ 中将该路径中包含的所有中间节点剔除，生成一个新的网络拓扑图。在新的网络拓扑中继续运行Dijkstra 算法，直到找不到新的路径，停止计算。这里，路径的数量也受式（4）的约束。

多径建立后，便是数据传输过程。在LEO卫星网络中，由于数据流到达的随机性以及编码包在多条路径上分配的随机性，已选路径上卫星的负载可能随时发生变化。因此，多径会导致负载的不均衡。采用了一种动态流量调节策略控制数据包的传输。

a）基于马尔可夫链的流量模型。与大多数网络负载相关工作一样，采用 $M / M / 1$ 排队模型来获取卫星中的业务量。将$p _ { k }$ 定义为排队进入稳定状态 $k$ 的概率为

$$
p _ { k } = \operatorname* { l i m } _ { k  \infty } P \{ N _ { k } = k \} = P \{ N ( t ) = k \}
$$

本文可以导出在LEO卫星 $i$ 的队列中数据包的期望数 $L _ { i }$ 。

$$
L _ { i } = \sum _ { k = 0 } ^ { \infty } ( k \times p _ { k } ) = \frac { \lambda _ { i } } { \mu _ { i } - \lambda _ { i } }
$$

其中： $\lambda _ { i }$ 和 $\mu _ { i }$ 分别是卫星 $i$ 中的数据包的到达率和离开率。请注意， $\lambda _ { i }$ 即包括来自相邻节点的数据包也包括由卫星 $i$ 自身生成的数据包。

根据Little 定理[19]，卫星中的平均排队时延 $d _ { i }$ 为

$$
d _ { i } = \frac { L _ { i } } { \lambda _ { i } } = \frac { 1 } { \mu _ { i } - \lambda _ { i } }
$$

给定离开率 $\mu _ { i }$ ，数据包到达率 $\lambda _ { i }$ 越大，平均排队时延 $d _ { i }$ 就越长。特别地，如果 $\mu _ { i } > \lambda _ { i }$ ，部分数据包将被丢弃。使用 $d _ { i }$ 来表示卫星 $i$ 的工作负载。因此，路径排队时延 $\vert d ^ { j }$ 可以用路径 $p ^ { j }$ 的工作负载表示

$$
d ^ { j } = \operatorname* { m i n } \{ d _ { i } | \forall _ { i } \in p ^ { j } \}
$$

b）动态流量调节策略。上式的路径排队时延 $d ^ { j }$ 代表了路径 $p ^ { j }$ 的实际传输能力。为了平衡多个路径之间的流量负载，根据它们的路径排队时延将数据包分配给不同的路径。基本原理是，排队延迟 $d ^ { j }$ 较小的路径将被分配更多的数据包。假设需要沿着 $\left| \mathbf { P } ^ { k } \right|$ 条路径传输具有 $N$ 个数据包的数据流 $f _ { k }$ 。使用 ${ N } _ { j }$ 来表示分配给路径 $p ^ { j }$ 的数据包的数量，如下所述。

$$
N _ { j } = \frac { 1 / d ^ { j } } { \displaystyle \sum _ { i = 1 } ^ { | P ^ { k } | } 1 / d ^ { i } } ( \sum _ { j = 1 } ^ { | P ^ { k } | } N _ { j } = N )
$$

在每个时隙的开始对 $\left| \mathbf { P } ^ { k } \right|$ 条路径上的负载进行均衡，如下所述。

a）更新式（13）中的 $d ^ { j } ( 1 \leq j \leq | P ^ { k } | )$ 。

b)在式（14）中调整每条路径 $d _ { j } ( 1 \leq j \leq \mid P ^ { k } \mid )$ 的 ${ N } _ { j }$ 。  
c)沿着路径 $p ^ { j }$ 发送 ${ N } _ { j }$ 个数据包。

# 2.3期望传输数据包

针对第二个问题，采用NCMCR协议中的协作能力模型来计算 $d _ { k }$ 的期望传输数据包（ETP）。可以得到：

$$
E T P = \operatorname* { m i n } \{ t _ { a } \times r _ { s } , \operatorname* { m a x } \{ x | g ( x ) \geq 0 \} \}
$$

其中： $t _ { a }$ 为 $d _ { k }$ 的最大可用传输时间(即，可用传输窗口)，该最大可用传输时间可以根据卫星相对于地球站的位置进行计算。$r _ { s }$ 为 $s _ { k }$ 的传输速率， $g ( x )$ 为接收 $x$ 个数据包后的可用传输时间

对于最后一个问题，需要一种更加高效的确认机制有效地传输数据包。考虑到长的ISLs时延，在NCMCR协议的非停等式ACK机制的基础上，提出了一种延迟确认机制来提高网络性能。这里，一个关键点就是为一组发送多少数据包。

这是对传输数据包的数量和解码率的综合考虑。特别地，当成功解码当前组后， $\boldsymbol { d } _ { k }$ 并不马上发送该组的ACK消息到$s _ { k }$ ，有关细节将在下一节进行描述。

# 3 延迟确认机制

在现有的基于NC的多径路由方案中，源节点会持续发送一组数据包直到它收到该组的ACK消息，这在LEO卫星网络中引入过多的冗余数据包和过长的端到端(E2E)时延[16]。NCMCR[13]协议提出了一种非停等式ACK机制，有效的提高了数据传输效率，在此基础上，对其做了进一步地改进。

为了达到约束条件式(1)\~(9)中定义的基于 NC 的多径路由问题的优化目标，提出了一种延迟确认机制来提高数据传输效率，具体实现方法如下：

a)源节点 $s _ { k }$ 为一个组发送足够多的编码包。

b)如果发送缓存器不是空的，则 $s _ { k }$ 继续发送后续组的数据包。

c)目的节点 $\boldsymbol { d } _ { k }$ 在成功解码一组之后并不会马上为 $s _ { k }$ 返回ACK或NACK消息，而是将这些消息存储到ACK缓存器，等到这些消息的条数达到一定阈值后，只需要一个ACK指令把它们全部确认。

d)如果 $s _ { k }$ 接收到一个组的NACK，则重新发送该组。

# 3.1延迟确认机制工作流程

为了采用延迟确认机制，每个卫星需要安装以下四种缓存器。a）发送缓存器（SDB）。它缓存正在发送的当前组的数据包。b）未确认缓存器（UAB）。它缓存在ACK计时器超时之前尚未接收到其ACK消息的组。c）未解码缓存器（UDB）。它缓存了ACK计时器已经超时的组。这些组要在下一个发送窗口中重发。d)ACK消息缓存器（ACB）。它缓存 $\boldsymbol { d } _ { k }$ 在成功解码一组数据后产生的ACK和NACK消息。

将延迟确认机制建模为确定型有限自动机（DFA）$\Gamma = ( Q , \sum , \delta , q _ { 0 } , F )$ ，其中 $\mathscr { Q } = \{ S _ { 1 } , S _ { 2 } , S _ { 3 } , S _ { 4 } , S _ { 5 } \}$ 是有限状态集；$\Sigma = \{ e _ { 1 } , e _ { 2 } , e _ { 3 } , e _ { 4 } , e _ { 5 } \}$ 是有限转换条件集； $\quad q _ { 0 } = S _ { 1 }$ 和 $F { = } \{ \operatorname { S } _ { 5 } \}$ 分别是初始状态和接受状态集； $\delta$ 表示状态转换。

图2是的状态图， $S _ { \mathrm { 1 } }$ 表示组 $n$ 处于发送缓存器时的发送状态； $S _ { 2 }$ 是组 $n$ 处未确认缓存器时的未确认状态； $S _ { 3 }$ 是组$n$ 处于未解码缓存器时的不可解码状态， $S _ { 4 }$ 是 ACK 消息处于ACB的状态， $S _ { 5 }$ 是结束状态。 $e _ { \mathrm { 1 } }$ 表示 $s _ { k }$ 已经发送了组 $n$ 中$t$ 个数据包。这里， $\textit { t }$ 是指为了成功解码组 $n$ 而必须发送该组的数据包的数量。在后面将分析如何估计 $t$ 。 $e _ { 2 }$ 表示 $d _ { k }$ 生成组 $n$ 的 ACK 消息并将它传到ACB。 $\boldsymbol { e } _ { 3 }$ 表示 $s _ { k }$ 接收到组 $n$ 的ACK消息。 $e _ { 4 }$ 表示组 $n$ 的计时器已经超时。 $e _ { 5 }$ 表示表示源从未解码缓冲器检索组以便重新传输。

![](images/8fce313a90891132a33e20b64c7042fdee0f003b940b65a795b4b6e8fce2b048.jpg)  
图2Γ的状态图  
Fig.2State diagram of Γ

# 3.2源节点的延迟确认机制

由于源节点中的延迟确认机制与NCMCR协议中的非停等式ACK类似。仅在下面对其工作流程做简要介绍。

当源节点 $s _ { k }$ 为一组发送了 $t$ 个编码包，它就将该组移动到未确认缓存器并启动它的计时器，N-NCMR协议的计时器不同于NCMCR协议，计时器长度与ACB缓存器阈值相关，阈值越大，计时器时间越长。如果 $s _ { k }$ 在超时之前接收到了该组的ACK，就从未应答缓存器中删除该组；否则，该组将被移动到未解码缓冲器。最后，在发送当前组的 $t$ 个数据包之后， $s _ { k }$ 将检查未解码缓存器是否为空。如果不是，则重传在未解码缓冲器中的组。

# 3.3目的节点的延迟确认机制

目的节点 $d _ { k }$ 负责对组中的数据包进行解码。与NCMCR协议不同的是， $\boldsymbol { d } _ { k }$ 在对一组编码包成功解码后，并不马上返回相应的ACK消息，而是将其移动到ACK消息缓存器，当缓存器中的消息达到一定阈值后，只需通过一条ACK消息将它们全部确认。

算法1描述了在目的卫星中延迟确认机制是如何工作的。第1-3行中， $d _ { k }$ 检查接收的组 $n$ 是否已经被解码，或者接收的数据包 $r p ( n )$ 是否与已经接收到的组 $n$ 的数据包线性相关。只要其中一个为真，则 $d _ { k }$ 丢弃数据包 $r p ( n )$ 。在第4行中， $d _ { k }$ 将新接收的数据包放入第 $n$ 组已接收数据包的集合中。在第5行， $\boldsymbol { d } _ { k }$ 检查组 $n$ 是否能被成功解码。第6行，NC层对数据包进行解码并传输到上一层。第7行，删除组 $n$ 的数据包。第8-11行，收集前面组的秩信息并更新缓存器 $D S$ 。第12-13行，更新缓存器 $S _ { u k }$ 并判断其是否达到阈值。第14-15行，向源节点发回 $S _ { u k }$ 中的消息。

算法1目的节点中的延迟确认机制输入：接收到的组 $n$ 的数据包 $r p ( n )$ ，已解码组的缓存器 $D S$ ，ACK消息缓存器 $S _ { u k }$ 及其阈值 $S _ { m }$ ，已接收的组 $n$ 的数据包集合 $R S _ { n }$ ，组量（一个组包含线性无关数据包的个数） $\omega$ ，组 $n$ 的ACK消息 $A _ { n }$ ， $\textstyle { A _ { n } }$ 携带的组 $m$ 的秩信息 $r _ { m }$ 。

1:if $n \in D S$ or与 $R S _ { n }$ 线性相关 then

2：丢弃 $r p ( \boldsymbol { n } )$

3:end if

$4 \colon R S _ { n } = \{ r p ( n ) \} \cup R S _ { n }$

5:if $r a n k ( R S _ { n } ) = \omega$ then

6： 解码并传输到上层

7: $R S = R S - \{ R S _ { n } \}$

8： for $m \in R S$ and $m \leq n$ do

9: （204号 $r _ { m } = r a n k ( R S _ { m } )$   
10: end for  
11: $D S { = } D S \cup \{ { \mathfrak { n } } \}$   
12: $S _ { u k } = \{ A _ { n } \} \cup S _ { u k }$   
13: if $S _ { u k } \ge S _ { { \scriptscriptstyle m } }$ then  
14: 将 $S _ { u k }$ 中消息打包发回源节点

15： end if

中间节点在同一机制下传输编码包和ACK消息。更具体地说，它们首先重编码数据包，然后将它们转发到下一跳直到 $\boldsymbol { d } _ { k }$ 。类似地，它们将 ACK 消息发回到前一跳，直到 $s _ { k }$ □

# 3.4每组发送的数据包数量

根据3.2节，确定 $t$ 的原则是 $\boldsymbol { d } _ { k }$ 可以解码这些数据包，如果发送太少， $\boldsymbol { d } _ { k }$ 将由于没有足够的线性无关数据包而无法解码。而且，在发送过程中，一些数据包可能由于不可靠的ISLs而丢失。

假设链路 $l _ { w }$ 的丢包率为 $\rho _ { w }$ 。因为数据包在每条链路$l _ { u \nu } \in p ^ { i }$ 上是独立编码和传输的，所以数据流 $f _ { k }$ 传输路径$p ^ { i } \in P ^ { k }$ 的可靠性为 $L _ { p ^ { i } } = \operatorname* { m i n } \{ 1 - \rho _ { u \nu } \mid \forall l _ { u \nu } \in p ^ { i } \}$ 。注意，任何编码包只传输一次。此外，由于路由协议中的所有路径都是独立且不相交的，因此路径集 $P ^ { k }$ 的可靠性是 $\sum _ { 1 \le i \le | P ^ { k } | } L _ { p ^ { i } }$ ，其中p'∈ P\*=U{p}。每当s通过|P|条路径发送t个数据包时，$d _ { k }$ 将接收到 $t \sum _ { 1 \leq i \leq | P ^ { k } | } L _ { p ^ { i } }$ 个数据包。为了使 $d _ { k }$ 能够解码一组数据包， $s _ { k }$ 应该发送的数据包数量可以通过下式估算：

$$
t \sum _ { 1 \leq i \leq | P ^ { k } | } L _ { p ^ { i } } \geq \omega
$$

如果源卫星发为一组发送 $t \geq \omega / \sum _ { 1 \leq i \leq | P ^ { k } | } L _ { p ^ { i } }$ 个数据包，将继续发送下一组。注意，的N-NCMR协议按照动态流量调整策略传输 $t$ 个数据包。具体地， $t$ 个数据包在路径 $p , p _ { 2 } , \cdots , p _ { _ { | p ^ { k } | } }$ 根据式（14）按比例进行分配。

# 3.5 复杂度分析

从时间和存储空间两方面分别表征N-NCMR协议的计算复杂度。N-NCMR协议的时间复杂度在初始化时为 $O ( d )$ ，d 是用路由跳数表示的网络直径。设网络节点数为 $N$ ,每个节点产生数据的速率为 $\nu$ ，网络运行时间为t。由于节点不会产生目的地为自己的数据分组，而且当遇到一个节点，虽然须转发的分组会增加，但可以发送并删除目的地为该节点的分组，因此空间复杂度为 $O ( ( N - 2 ) \nu t )$ 。

# 4 仿真与分析

构建了一个基于NS-3的仿真系统，并通过与MORE、CCACK、ONCR、NCMCR四个多径路由协议的比较，系统地评估了N-NCMR的性能。

采用的双层卫星网络的GEO层由三个地球静止轨道卫星组成，LEO层是类似铱星的卫星网络，使用STK仿真如图3所示。LEO卫星网络层由66颗卫星组成，它们均匀分布在6个轨道上。考虑层间ISLs，面内ISLs和面间ISLs,每个LEO卫星最多有五个ISLs。上行链路和下行链路容量设置为 $2 5 \ : M b p s$ 。系统中有五个并行数据流。GEO卫星的其他参数设置为：高度 $: = 3 5 7 8 6 k m$ ，倾角 $= 0 ^ { \circ }$ 。LEO卫星其他参数设置为：高度 $= 7 8 0 k m$ ，倾角 ${ = } 8 6 . 4 { ^ \circ }$ ，面间分离度 $= 3 1 . 6 ^ { \circ }$ ，接缝间分离度 $= 2 2 ^ { \circ }$ ，高度截止角 $= 8 . 2 ^ { \circ }$ ，纬度阈值 $\scriptstyle = 6 0 ^ { \circ }$ 。

![](images/4aad3d51eba69ddf5020f91f20d5eef80a09698c5909599f33381dd36e613c4c.jpg)  
图3双层卫星网络模型

# 4.1成功交付率

首先评估的方案在不稳定ISLs中的传输可靠性。一次成功交付意味着组被 $s _ { k }$ 只传输一次就被 $d _ { k }$ 成功解码。定义了一次解码率 $\zeta$ 和一次传输率 $\xi$ ，分别用来衡量N-NCMR的一次成功解码和交付能力。它们都会受到ISLs上丢包率的影响。

$$
\zeta = \frac { N _ { d e c o d a b l e } } { N _ { r e c e i \nu e d } } , \xi = 1 - \frac { N _ { r e s e n t } } { N _ { s e n t } }
$$

![](images/275528ae4dc0c590134128e7553f8f79456a9c59fecf5574fcdc1a4c04be8d1a.jpg)  
Fig.3Double-Layer satellite network model

其中： $N _ { r e c e i \nu e d }$ 是仅发送一次接收到的组的数量， $N _ { d e c o d a b l e }$ 是在一次传输后可以解码的组的数量， $N _ { s e n t }$ 是源节点发送的组的总数， $N _ { r e s e n t }$ 是重传一次以上的组的数量。

图4表明当ISLs变得更不稳定时，N-NCMR的 $\boldsymbol { \zeta }$ 和 $\xi$ 减小。然而，当链路 $l _ { u \nu }$ 的丢包率 $\rho _ { w }$ 达到 $10 \%$ 以上时， $\zeta$ 变得稳定。其原因是，根据式（16），N-NCMR中传输的数据包数量 $t$ 随着路径的丢包率而动态变化。特别地，当ISLs丢包率上升时，源节点会为组发送更多的编码包，使得N-NCMR即使在 $\rho _ { u v } > 4 0 \%$ 的情况下也能始终提供超过 $8 5 \%$ 的一次解码率。

通过比较，随着ISLs丢包率的增加， $\zeta$ 不断下降。原因是当ISLs变得更加不稳定时，更多的数据包和ACKs将丢失。这些结果表明，的N-NCMR可以动态地适应ISLs 的状态。

# 4.2传输速率与吞吐量的关系

图5表明了传输速率对吞吐量的影响。如图5所示，当CBR（固定码率）增加时，N-NCMR和NCMCR的吞吐量增加，但N-NCMR吐吞量增加更明显，其他协议的吞吐量保持稳定。结果表明，N-NCMR具有比其他协议更高的传输和负载均衡能力。其原因在于N-NCMR减轻了LEO卫星的计算负载，通过延迟确认机制节省了信道资源，提高了传输能力。

# 4.3延迟确认机制性能评估

测试了计时器长度在系统吞吐量和ACK数量方面对不同的确认机制（停等式逐跳确认机制，停等式E2E确认机制，非停等式E2E确认机制以及本文的延迟确认机制）的影响。将SDB、UAB和UDB大小设置为64MB，ACB的阈值设置为3。图6表明，延迟确认机制ACK数量最小，逐跳机制的ACK数量最多。如图7所示，随着计时器长度的增加，本文的延迟确认机制具有最高和最稳定的吞吐量，而停等式E2E确认机制具有最差吞吐量。

![](images/9f1782bc9582c3cf15990c3ec53aa1e2b9cbfe876247a370112505000a1963a9.jpg)  
图5吞吐量随CBR的变化

![](images/2822db4177a8eda732608e8b93b3949225a55435d7b8ab01e447e553a2a45815.jpg)  
Fig.4Relationship between $\boldsymbol { \zeta }$ ， $\xi$ and isls packet loss rate   
Fig.5Throughput changes with CBR   
图6计时器长度对ACK数量影响

![](images/c32d0a2abb17f4323b00bb5968aa3d213ee2053f9e6e2087dbf04f1962371b21.jpg)  
图4 $\boldsymbol { \zeta }$ ， $\xi$ 与ISLs丢包率的关系  
Fig.6Influence of the length of the timer on the number of ACK   
图7计时器长度对吞吐量的影响Fig.7Impact of timer length on throughput

# 5 结束语

考虑到ISLs较长和网络拓扑结构规则，提出了一种双层的GEO/LEO卫星网络模型，通过GEO卫星为LEO卫星网络计算路由，提高了LEO卫星的传输能力，提出了一种新的基于NC的多径路由协议（N-NCMR）。N-NCMR可以保证如果存在链路不相交的路径，可以选择尽可能多的链路不相交的路径，通过动态流量调节策略，可以显著减少端到端时延，提高吞吐量。此外，提出了一种延迟确认机制并从理论上分析了成功解码一组数据包需要发送的编码包数量，它能够确保 $100 \%$ 的传输率，显著地减少了应答的开销。仿真结果表明，N-NCMR协议显著提高了LEO卫星网络的数据传输效率和吞吐量。

# 参考文献：

[1]Wu Zhaofeng,Jin Fenglin,Luo Jianxin,et al.AGraph Based Satellite Handover Framework for LEO Satelite Communication Networks [J]. IEEE Communications Letters,2016,20 (8):1547-1550.   
[2]Wang Yupu,Lu Zhiping,Qu Yunying,et al.Improving prediction performance of GPS satellite clock bias based on wavelet neural network [J].GPS Solutions,2016,21 (2):1-12.   
[3]Ahlswede R,Cai Ning,Li S YR,et al.Network information flow [J]. IEEE Transactions on Information Theory,2000,46 (4):1204-1216.   
[4]Ostovari P,Wu Jie,Khreishah A.Network coding techniques for wireless and sensor networks [M]// The Art of Wireless Sensor Networks.Berlin: Springer,2014:129-162.   
[5]刘沛龙，陈宏宇，魏松杰，等.LEO卫星网络海量遥感数据下行的负 载均衡多径路由算法 [J].通信学报，2017,38(S1):135-142.(Liu Peilong,Chen Hongyu,Wei Songjie,et al.LEO satellite network load balancing multipath routing algorithm for mass remote sensing data downlink [J]. Journal of Communications,2017,38(S1):135-142.)   
[6] 焦媛媛，田丰，石神，等．基于多径的低轨卫星网络路由拥塞控制策 略[J]．电子设计工程,2018,26(18): $1 1 3 - 1 1 7 + 1 2 2$ .(Jiao Yuanyuan, Tian Toyo,Shi Shen,et al.Routing congestion control strategy for LEO satellite networks based onmulti-path [J].Electronic Design Engineering,2018,26 (18): $1 1 3 - 1 1 7 + 1 2 2 .$ ）   
[7]王阳．基于路径分段的卫星网络多径路由协议[D].沈阳：东北大 学，2011.(Wang Yang.Multi-path routing protocol for satellite networks based on path segmentation [D]. Shenyang: Northeast University,2011.)   
[8]Chen Lin, Zhang Qian,Li Minglu,et al.Joint topology control and routing in IEEE 802.11-based multiradio multichannel mesh networks [J].IEEE Trans on Vehicular Technology,2007,56(5):3123-3136.   
[9]Chachulski S,Jennings M,Katti S,et al. Trading Structure for Randomness in Wireless Opportunistic Routing [J].ACM SIGCOMM Computer Communication Review,2007,37 (4): 169-180.   
[10] Zhang Xinyu,Li Baochun.Optimized multipath network coding in lossy wireless networks [J].IEEE Journal on Selected Areas in Communications,2008,27 (5): 622-634.   
[11] Koutsonikolas D，Wang C C,Hu C Y.CCACK:efficient network coding based opportunistic routing through cumulative coded acknowledgments[C]//ProcofConferenceonInformation Communications.Piscataway,NJ:IEEE Press,2010:2919-2927.   
[12] Xiang Qiao,Zhang Hongwei，Wang Jianping，et al.On optimal diversity in network-coding-based routing in wireless networks [C]// Computer Communications.Piscataway,NJ:IEEE Press,2015: 765-773.   
[13] Tang Feilong,Zhang Heteng,Fu Luoyi,et al.Multipath cooperative routing with efficient acknowledgement for LEO satellite networks [J]. IEEE Trans on Mobile Computing,2018,PP(99):1-1.   
[14] Tang Feilong,Guo Minyi,Guo Song,et al.Mobility prediction based joint stable routing and channel assignment for mobile Ad hoc cognitive networks [J].IEEE Trans on Parallel& Distributed Systems,2016,27 (3): 789-802.   
[15]齐小刚，马久龙，刘立芳．基于拓扑控制的卫星网络路由优化[J]. 通信学报,2018,39 (02):11-20.(Qi Xiaogang,Ma Jiulong,Liu Lifang. Satellite network routing optimization based on topology control [J]. Journal of Communications,2018,39 (02):11-20.）   
[16] Chen Lin, Zhang Qian,Li Minglu,et al. Joint topology control and routing in IEEE 8O2.11-based multiradio multichannel mesh networks [J].IEEE Trans on Vehicular Technology,2007,56 (5): 3123-3136.   
[17] Firouzja SAN,Yousefnezhad M, Othman MF,et al.A wised routing protocols for LEO satellite networks [C]// Proc of the 10th Asian Control Conference.Piscataway,NJ: IEEE Press,2015:1-6.   
[18] Chen Xi,Wang Menglu,Zhang Lei．Analysis on the Performance Bound of Doppler Positioning Using One LEO Satellite [C]//Proc of IEEE,Vehicular Technology Conference.Piscataway,NJ: IEEE Press, 2016: 1-5.   
[19] He Liang,Pan Jianping，Xu Jingdong.A progressive approach to reducing data collection latency in wireless sensor networks with mobile elements [J].IEEE Trans on Mobile Computing,2013,12(7): 1308-1320.