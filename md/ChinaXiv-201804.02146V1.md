# 基于节点社会性的无线网络编码传输策略研究

张晓军，李领治，朱艳琴(苏州大学 计算机科学与技术学院，江苏 苏州 215006)

摘要：延迟容忍网络是一种缺乏持续连接的新型网络体系结构，选择合适的转发节点是实现延迟容忍网络高效的转发和投递消息的关键问题。由于节点移动性和网络拓扑动态变化等会对延迟容忍网络的传输效率产生影响，提出了一种基于节点社会性和利用随机线性网络编码的DTN 网络模型NSNC-DTN。NSNC-DTN网络模型利用网络中的社团结构、社团紧密度以及节点活跃度，选择出最合适的转发节点。离线计算节点的社会性，对源节点和Center节点进行随机线性网络编码，在线完成转发，从而达到高效转发和投递的目的。仿真结果表明NSNC-DTN网络能够有效地提高信息投递成功率，减小端对端的网络延迟和网络开销。

关键词：延迟容忍网络；社团发现；网络编码；数据转发中图分类号：TP393 doi:10.3969/j.issn.1001-3695.2018.01.0044

# Wireless network coding transmission strategy based on nodal sociality

Zhang Xiaojun, Li Lingzhi, Zhu Yanqin (School ofComputer Science & Technology， Soochow University， Suzhou Jiangsu 215006，China)

Abstract: Delay Tolerant Network(DTN) isa new network architecture which lacks continuous connectivity,choosing the appropriate forwarding node is a keyof eficient forwarding and delivery.Due tothedynamicchange of node mobilityand network topologyaffect the transmisson effciencyofDTN,thispaperproposesanewDTNnetwork modelNSNC-DTbased on nodal sociality andrandom linear network coding.NSNC-DTN network model chooses the most appropriate forwarding node bythecommunity structure,the similarityofcommunityand activityofthe nodes in the network.Itcalculates nodal socialityin ofline mode and uses random linear network coding for Source nodes and Center nodes,implements messges forwardingonline toreach the goalofeficient forwardinganddelivery.The simulationresult shows thatNSNC-DTNnetwork modelcan efectively improve the success rate of information delivery and reduce network delay and network overhead.

ey words: delay-tolerant network; community detection; network coding; data forwarding

# 0 引言

延迟容忍网络（delay tolerant networks,DTN）[1,2] 是一种非连续性连接结构的网络，源节点到目标节点间不需要存在完整路径，利用移动节点的特性，采取“存储-携带-转发”的路由机制[3]来实现网络通信的网络。DTN网络虽然建立简单、迅速，但却存在各节点不断移动和连接间断导致通信链路无法持续的问题，因此传统无线网络以及移动自组织网络（mobilead-hocnetwork，MANET)[4]中的路由机制并不适用于延迟容忍网络。所以选择合适的转发节点使得数据可以更高效的投递到目的节点成为了DTN网络通信的关键问题。目前针对DTN网络的路由机制方案已经提出了许多，从最初的基于副本路由协议和基于上下文路由协议为主，随着面向副本协议的路由技术的研究的越来越完善，更多的研究人员转向对节点关系、节点运动性对于路由协议的影响[5]。

在经典的路由算法中，文献[6]提出了Bubble路由算法，该路由算法基于人类社会关系，根据社团结构和节点分布情况综合来选择合适的转发节点。由于总是寻找节点分布密度高的节点来进行消息转发，节点分布密度低的节点无法获得转发消息的机会，从而造成了节点资源的浪费。此外，对于大规模的网络，此路由算法的副本保存过多问题也会造成较大的开销。文献[7]提出的Clustering路由算法，将具有相似性移动模式的节点分解成一个集群，然后可以交换共享资源，从而达到降低开销和减少端到端传输延迟的目标；文献[8]提出消息转发算法SANE路由算法，把相似兴趣的用户归类到一起，从而得到无状态的转发策略。

上述的这些经典路由算法大多有低交付率和高网络传输延迟的缺点，为了解决这些缺点，近两年DTN网络相关研究人员又提出了一些新颖的路由算法。文献[9]提出了GTSP路由算法，该算法基于时空和社会性，根据节点之间经常以大概率相遇的时间段和地理区域确定每个节点以及节点之间在特定时间段和地理区域上的相遇概率较大的几个节点组成的表和共同朋友节点表，然后进行移动和转发数据包。文献[10]提出了基于感知节点移动状态的路由算法，建立半马尔可夫模型，在传统的DTN 节点移动特性的研究基础上优化路由策略。文献[11]提出了SACRA路由算法，该算法基于社会性和副本限制，相较于传统的多副本路由算法有较小的网络资源开销。现如今对社会性DTN网络的研究很多，但同时引入网络编码的研究很少，所以提出一个把基于节点社会性选择转发节点和利用随机线性网络编码（random linear networkcoding，RLNC）转发编码包相结合的DTN网络模型一NSNC-DTN网络模型。NSNC-DTN网络模型将节点划分成到不同的社团中，对划分好的社团的进行社团间紧密度的计算以及各个节点在全网中的活跃度的计算。通过结合社团紧密度和节点活跃度综合来选择合适的节点进行消息的转发。NSNC-DTN采用RLNC，把同一目的节点的消息全都编码在一起，从而达到增大网络吞吐量和降低数据包转发开销的效果。

# 1 NSNC-DTN网络模型路由协议

# 1.1NSNC-DTN模型概述

NSNC-DTN 模型是一种把基于节点社会性选择转发节点和利用RLNC转发编译好的数据包相结合的DTN数据转发路由。NSNC-DTN网络模型分为两大部分：1）基于节点的社会性来选择转发节点的DTN网络路由；2)引入RLNC。在NSNC-DTN模型网络中，先对DTN网络中的节点进行所属社团的划分。利用社团发现算法来去除介数最大边从而将DTN网络划分成多个子社团。定义社团间紧密度来表示社团之间的关联程度，定义节点中心度来表示节点在DTN网络中的活跃程度，NSNC-DTN模型中，节点所在社团选择与其紧密度最高的社团进行社团间的数据转发，转发节点选择节点活跃度更高的节点作为转发节点。NSNC-DTN模型引入RLNC，对源节点进行RLNC，把同一目的节点的消息全都编码在一起，从而达到增大网络吞吐量和降低数据包转发开销的效果。为了进一步提高网络的数据转发效率，引入Center节点，将其数据包再次编码和转发。图1表示NSNC-DTN网络模型的数据转发过程。

![](images/76f1f7424504735521f00c9bc0c5e9f6fbfb2a5a58fedf647743b01755d70243.jpg)  
图1NSNC-DTN网络模型

从图1中可以发现，源节点和目的节点不在同一个社团，源节点与其他社团不存在连边，此时利用RLNC先对多条目的地址相同的数据包编码，然后再转发编码包。根据节点活跃度选择合适的相遇节点作为转发节点，在发送数据包之前需要判断该节点是否为Center节点，如果是，将目的地址相同的数据包再次编码发送，如果不是，则直接转发数据包，如此反复下去直到目的节点收到完整消息或者收到新的编码包能够解码出完整消息，利用泛洪机制通知各转发节点将转发次数重置为0且清除缓存信息。

为了方便理解NSNC-DTN网络模型，对本文中提到的相关概念进行说明：

a)社团。节点构成的集群结构，用club符号表示，集群内的节点连接度较高，集群之间的节点连接度较低。

b)节点间距离。节点间连接的最短距离，详细说明见1.3节。

c)Center节点。在数据转发的过程中，设定一个合适的节点活跃度阈值，当选择的转发节点大于设定的阈值时，将此节点定义为Center节点。

同时为了理解NSNC-DTN网络模型，还需要作几点假设：

a)所有的节点都具有同样的传输数据和缓存数据能力。b)网络中各个节点最少属于一个社团，一个社团只包含单个节点的特殊情况允许存在。c)社团间存在不同的社团紧密度，可以进行量化计算。d)节点在全网中的活跃度各不相同，各个节点在全网中都有一个活跃度排名。

# 1.2社团划分

由于网络的社团结构在传输数据时可以减少网络开销，因此社团发现算法得到了越来越多的研究[12]。传统社团结构划分算法[13]在小型网络结构中可以获得较明显的效果，但是对节点稀疏的大型的网络结构效果却非常不好。Radicchi算法[14]是一种图结构分析方法。该算法计算边 $( \mathrm { i } , \mathrm { j } )$ 的边聚集系数来量化节点i 和节点j间的近似度。边 $( \mathrm { i } , \mathrm { j } )$ 的聚集系数 $c _ { ( i , j ) }$ 主要是依托包括了边 $( \mathrm { i } , \mathrm { j } )$ 的三角环所占的比例，计算公式如下：

$$
\begin{array} { r c l } { \displaystyle \mathtt { C } _ { ( i , \ j ) } } & { = } & { \displaystyle \frac { \mathrm { Z } _ { i , \ j } + \mathrm { \small ~ 1 ~ } } { \mathrm { M i n } \mathrm { \small ~ ( ~ \displaystyle ~ k ~ } _ { i } - 1 , \mathrm {  ~ \lambda ~ k ~ } _ { j } - 1 ) } } \end{array}
$$

其中: $\mathsf { C } _ { ( i , \ j ) }$ 是边(i,j)的聚合系数， $z _ { i , j }$ 是图中包含了边 $( \mathrm { i } , \mathrm { j } )$ 的三角形个数， $k _ { i }$ 是i的度， $k _ { j }$ 是j的度。 $M i n ( k _ { i } \ \textrm { -- } \ 1 , \ k _ { j } \ \textrm { -- } \ 1 )$ 表示节点间连边最多可能属于的三角形结构数。

当存在一些节点同时属于多个社团时，便构成了重叠社团结构[15]。Radicchi算法对于重叠社团结无法进行有效的节点社团划分，针对Radicchi算法这方面的不足，提出了一种改进版的Radicchi算法—LORadicchi算法。算法步骤如下：

a)计算出网络中所有连边的聚集系数 $c _ { ( i , j ) }$ ，删除掉最小 的边。

b)判断去除的连边的两个节点是不是属于多个社团，将同时属于多个社团的节点划分到某个社团中。如果节点属于社团{cluba'clubb'clubc，..}，计算节点与所属社团的紧密度为

$$
\begin{array} { r c l } { \displaystyle _ { c t ( i , \mathrm { \ c l u b } _ { a } ) } } & { = } & { \displaystyle \frac { \sqrt { i , j \in _ { \mathrm { c l u b } _ { a } } ^ { \star } } \ d ( i , \ j ) } { N _ { \mathrm { c l u b } _ { a } } - 1 } } \end{array}
$$

c)计算得到使 $\cot ( i , \mathrm { \ c l u b } _ { a } )$ 值最大的社团，将节点i划分到该社团，去除其余社团中的节点i和相关的连边。

d)对未划分到社团的节点执行Radicchi算法，再次计算受到重叠社团结构影响的节点的边聚系数，根据边聚系数来对节点划分社团。

算法采用局部度量的方式，从而大大加快了计算的速度。对于节点数为 $\mathfrak { n }$ ，连边数为 $\mathbf { m }$ 的网络，LORadicchi算法根据步骤1）计算所有连边的聚集系数的时间复杂度为 $o ( m )$ 。假设社团数为s，则步骤b)c)的复杂度为 $o ( \mathrm { s } )$ ，最后一步需要进行迭代对局部连边计算，复杂度为 $o ( m ^ { 2 } \mathrm { ~ / ~ } n ^ { 2 } )$ ，所以整个算法的时间复杂度为 $\textit { o } ( m \ + \ s \ + \ m ^ { 2 } \ / \ n ^ { 2 } )$ 。

# 1.3社团紧密度计算

社团紧密度衡量两个社团间的数据包发送频繁度的大小，用符号CTa.b来表示。CTa,b的大小主要由两个因素来决定的：社团a游走到社团b的概率；社团a与社团 $\boldsymbol { \mathbf { b } }$ 间的平均距离。DTN网络中的t时刻社团紧密度集合：

$$
\begin{array} { r l r } { C ^ { ( t ) } } & { { } = } &  \{ \mathrm { C T a , b , C T a , c , C T a , d . . . \} } \end{array}
$$

由于社团之间并非是完全独立的，而是具有一定程度的社团紧密度，社团紧密度高的节点间有更高的几率发生数据包传输。因此，计算量化社团紧密度是非常需要的，把社团紧密度更高的节点作为转发节点，更有利于数据包的传输。

社团紧密度度量考虑到局部随机游走（LRW)[16]的思想。LRW的基本思想是：节点进行有限的随机游走，节点列能够形成基于概率的马尔科夫链[17]。在此基础上，计算两个社团进行有限随机游走后形成连接的概率。假设无向DTN 网络G(V,E)的社团数为s，C为网络包含的社团集合，对于任意两个社团a、b，用符号Pa,b代表社团a下一步游走到社团b的概率，计算公式如下：

$$
{ { \cal P } _ { a , b } } ^ { \mathrm { ~ ~ } } = \left. \frac { m a , b } { \left| { E _ { a } } \right| } \right.
$$

$\left| _ { E _ { a } } \right|$ 为社团a与网络中其他社团间的总连边数，计算公式为：

$$
\left| \operatorname { E } _ { a } \right| = \sum _ { \stackrel { X = 1 } { X \neq a } } ^ { S } \left| E _ { a , X } \right|
$$

$\mathbf { \Omega } _ { m _ { a , b } }$ 代表社团a与社团b的连接情况，是邻接矩阵M的一个子元素。 $\mathbf { w }$ 为与社团a直接相连的社团个数，由于DTN 网络是一个社团间双向连接的网络，可以得到 $\mathbf { M }$ 是个 $( \mathbf { w } { + } 1 ) ^ { * } ( \mathbf { w } { + } 1 )$ 的对称矩阵，用 $\mathbf { \Phi } _ { l a , b }$ 来表示社团a和b之间的连边数，则

$$
\begin{array} { r l r } { \pi _ { a , b } } & { = } & { \left\{ \begin{array} { l l } { \mathcal { l } _ { a , b } \quad } & { \quad \ddag \pm { | \mathcal { X } | } { \mathrm { a } } , \ b \dot { \mathcal { Z } } | \boxplus \middle / \ddag \mathcal { F } \dag \exists \ddag \mathcal { Z } } \right.} \\ { 0 \quad } & { \quad \widehat { \Xi } \bot \emptyset \bigcup } \end{array}   \end{array}
$$

根据图1，可以计算得到 $\operatorname { c l u b } _ { a }$ 与其他社团的连接状态矩阵如下：

$$
\begin{array} { r l r } { M _ { a } } & { { } = } & { \left[ \begin{array} { l l l } { 0 } & { 1 } & { 3 } \\ { 1 } & { 0 } & { 0 } \\ { 3 } & { 0 } & { 0 } \end{array} \right] } \end{array}
$$

假设数据包从 $\mathrm { c l u b } _ { a }$ 经过t步随机游走后到 $\mathrm { c l u b } _ { b }$ 的概率为na,b(t)，则

$$
\begin{array} { r l r } { \eta _ { a , b } ( t ) } & { { } = } & { P ^ { T } . \eta _ { a , b } ( t \mathrm { ~ - ~ } 1 ) } \end{array}
$$

其中： $P ^ { T }$ 表示概率矩阵的转置。

社团紧密度还与社团之间的平均距离有关。假设 $\mathrm { c l u b } _ { a }$ 和$\mathrm { c l u b } _ { b }$ 分别有节点数 $n _ { a } \cdot n _ { b }$ ，那么社团a、b间的两个节点的最短距离为一个 ${ n _ { a } } ^ { * } { n _ { b } }$ 的矩阵 $D ( C _ { a } , C _ { b } )$ ，则 $\mathrm { c l u b } _ { a }$ 和 $\mathrm { c l u b } _ { b }$ 的平均距离为

$$
\begin{array} { c c } { { \displaystyle \sum _ { j = 1 } ^ { n _ { a } } } } & { { \sum _ { j = 1 } ^ { n _ { b } } } } \\ { { \overline { { { D ( \ c \mathrm { 1 } \mathrm { u b } _ { a } , \ c \mathrm { 1 } \mathrm { u b } _ { b } ) } } } } } & { { = } } & { { \displaystyle \frac { i \in \mathrm { c l u b } _ { d } \ f \in \mathrm { c l u b } _ { b } } { n _ { a } * n _ { b } } } } \end{array}
$$

所以 $\mathrm { c l u b } _ { a }$ 与 $\mathrm { c l u b } _ { b }$ 在t时刻的社团紧密度为

$$
\begin{array} { r c l } { { C T _ { a , b } ^ { \phantom { b } } ( t ) } } & { { = } } & { { ( \eta _ { a b } ^ { \phantom { a } } ( t ) . \displaystyle \frac { \left| E _ { a } \right| } { 2 \left| E \right| } \ + \ \eta _ { b a } ^ { \phantom { a } } ( t ) . \displaystyle \frac { \left| E _ { a } \right| } { 2 \left| E \right| } ) . \overline { { { D } } } ( \mathrm { c l u b } _ { a } ^ { \phantom { \dagger } } , \ \mathrm { c l u b } _ { b } ^ { \phantom { \dagger } } ) } } \end{array}
$$

当DTN中增加新的节点、去除旧的节点或者社团连边数有改变时，只需要进行局部重新计算社团紧密度，所以计算速度会很快。

# 1.4社团中节点活跃度计算

节点活跃度指的是节点在DTN中活跃程度，即是节点在DTN 中节点发送数据包能力的体现，用 $\mathbf { \Psi } _ { V \dot { \mathcal { I } } \dot { t } a \mathcal { I } \dot { \mathcal { I } } \dot { t } y } _ { \dot { \mathcal { I } } }$ 表示。DTN从三个方面量化节点活跃度，即节点转发数据包的频率、外部社

团连边数和所连接到的社团数。用G代表DTN中所有节点的活跃度，定义为

$$
G ~ = ~ \{ { \nu } i t a l i t y _ { 1 } ^ { ~ ( t ) } , { \nu } i t a l i t y _ { 2 } ^ { ~ ( t ) } , { \nu } i t a l i t y _ { 3 } ^ { ~ ( t ) } , \ldots \}
$$

在DTN中，用 $c o u n t _ { i } . ^ { e d g e s }$ 表示节点i所属社团与外部社团的连边个数， $\boldsymbol { c l } _ { j }$ 表示与节点i相连接的外部社团数， $\mathrm { f r } _ { j }$ 表示节点i的转发数据包的频率。则节点活跃度的计算如下：

$$
\begin{array} { r c l } { { { \it \Psi } _ { V i } t a l i t y } _ { i } } & { { = } } & { { ( \alpha c o u n t _ { i } \mathrm { \it { ^ { e d g e s } } } + \beta c l _ { i } ) . e ^ { \lambda f r _ { i } } } } \end{array}
$$

其中： $\alpha$ 、 $\beta$ 、 $\lambda$ 都是可以调节的参数， $\alpha + \beta = 1$ 得到满足，可以通过修改这两个参数的值来修改节点连边数及节点连接的社团数的相对重要性。假设DTN网络有 $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 个节点，则计算各个节点中心度的时间复杂度为 $o ( n )$ 。选择节点活跃度高且活跃度低于自的节点的节点作为转发节点，可以保证更高的数据包传输率。在NSNC-DTN模型中，节点活跃度在每次完成数据包发送后重新计算，这样每个活跃度低于目的节点的节点都有机会成为转发节点，从而可以有效的减小转发节点的缓存压力。

# 1.5网络编码

NSNC-DTN模型采用RLNC，把同一目的节点的消息全都编码在一起，从而达到增大网络吞吐量和降低数据包转发开销的效果。为了降低转发节点的缓存压力，尽可能确保更多的消息传输到目的节点，引入Center节点，将其数据包再次编码和转发。这样网络编码过程也就可以分为两个过程：源节点编码和Center节点编码。

a)源节点编码。令源节点产生 $\mathfrak { n }$ 个同一目的地址的数据包dp,dp2，dp，.，,dpn，对其执行线性网络编码，得到m个编码包ec，其中 $\mathrm { { \ m } > n }$ ， $\begin{array} { c c l } { { e c } } & { { = } } & { { \displaystyle \sum _ { k = 1 } ^ { n } e _ { k } d p _ { k } } } \end{array}$ ékdpk ，其中éκ是从有限域中随机产生的系数，每个编码计算都需要在有限域范围内进行。在编码包的头部存储编码向量 $\textbf { \textit { e } } = \ \left| e _ { 1 } . . . e _ { n } \right|$ ，跟随编码包一起发出去。目的节点在收到 $\mathfrak { n }$ 个编码向量线性无关的编码包时，就可以计算解出原始发送的 $\mathfrak { n }$ 个数据包 $d p _ { 1 } , d p _ { 2 } , d p _ { 3 } , . . . , d p _ { n } ,$ 设编码向量矩阵 $\begin{array} { r l r } { E ^ { T } } & { { } = } & { \left| e _ { 1 } ^ { \ T } . . . e _ { n } ^ { \ T } \right| } \end{array}$ ，原始数据包$\begin{array} { r l r } { D P ^ { T } } & { { } = } & { \left| d \boldsymbol { p } _ { 1 } ^ { \ T } \cdot \cdot \cdot d { \boldsymbol { p } _ { n } } ^ { \ T } \right| } \end{array}$ ，编码包 $\begin{array} { r c l } { E C ^ { T } } & { = } & { \displaystyle \left| e c _ { 1 } ^ { \phantom { \dagger } } T \ldots e c _ { n } ^ { \phantom { \dagger } } T \right| } \end{array}$ ，T表示的是转置操作，则解码结果 $\begin{array} { r } { P \ = \ E ^ { - 1 } . E C } \end{array}$ 。

b)Center节点编码。当节点的活跃度大于设定的阈值时，将此节点设置为Center节点，将其数据包再次编码和转发。二次编码可以减轻源节点的编码压力，增强编码数据包的线性无关性，从而减少冗余信息的转发，改善转发节点缓存增大的问

题。Center节点使用递归编码，即对编码后的数据包再次执行RLNC，计算的过程与上述编码计算过程相似，就不赘述了。如果Center节点碰到转发节点j时，比较Center节点与转发节点j的节点活跃度，如果 $\mathbf { \Sigma } _ { V i } t a l i t y \mathbf { \Sigma } _ { j } < \mathbf { \Sigma } _ { V i } t a l i t y \mathbf { \Sigma } _ { j }$ 且 $\mathbf { \Omega } _ { V i t a l i t y } \mathbf { \Omega } _ { j }$ Vvitality(目的节点的节点活跃度)，那么把相同目的节点的消息执行线性编码，并转发编码后的数据包。

# 2 NSNC-DTN模型的数据转发策略

在NSNC-DTN网络模型中，节点与社团间不是网络上的上下层级关系，而是结合社团紧密度和节点活跃度综合决定转发节点，利用RLNC，对源节点编码和Center节点再次编码从而把同一目的节点的消息全都编码在一块，通过转发节点逐步转发直至到达目的节点或数据包在网络中过期。NSNC-DTN模型的具体转发过程如下：

a)对节点进行初始设置，每个节点对应写入一个线性动态链表，链表结构信息如下：

<html><body><table><tr><td>节点i</td><td>连边数edge；</td><td>节点活跃度vitalityi</td></tr><tr><td>社团标号cluba</td><td>节点距离 d(i，j)</td><td>转发次数transformi</td></tr></table></body></html>

节点每做一次转发节点则其transform；值加1；设置合适的节点转发次数阈值为threshold，其中threshold $\in ( 0 , \mathrm { s u m } )$ ，sum为需要发送的数据包数。设置节点活跃度 $\mathbf { \Sigma } _ { V i t a l i t y } \mathbf { \Sigma } _ { j }$ 的阈值为max $V _ { j }$ ，如果 ${ \ o { \nu } } i \ t a l i t y _ { i } > \operatorname* { m a x } _ { i } \ V _ { i }$ ，则将此节点定义为Center 节点。b)节点社团划分。比较转发节点与目的节点是否属于同一社团，如果是，执行步骤f)。c)判断转发节点的外部连边数是否为0，如果是，执行步骤 $\mathbf { g }$ 。

d)社团紧密度比较。比较转发节点与属于不同社团的相遇节点的社团紧密度，找出最大社团紧密度的节点作为转发节点。若存在多个相同的的最大社团紧密度的节点，随机选择一个节点作为转发节点，若transform,>threshold，则选择其他相同最大紧密度的节点作转发节点，如果转发节点是Center节点，则对其进行再次的随机线性编码，将这个编码后的新编码包转发给节点j，否则直接进行消息转发，执行步骤b)。

e)节点活跃度的比较。当前节点i与相遇节点j进行比较，如果 $N C A _ { j } < N C A _ { j }$ ，且 ${ N C A } _ { j }$ 小于目的节点活跃度时，节点i将数据包转发给节点j。

f)判断目的节点。比较当前节点j与目的节点是否相同，

如果不是，执行步骤e)。

g)执行步骤f）c)。

h)判断目的节点所接收到的数据包是否为编码包，如果不是，直接投递数据，否则判断编码包是否携带新的信息，如果没有携带新的消息就直接丢弃，如果有携带新的消息则将编码包加入编码矩阵缓存起来，当编码矩阵满秩时即可解码，即消息发送成功，泛洪ACK通知各转发节点将转发次数重置为0且删除缓存中保存的信息。

此转发过程实际经验相一致，为了将所需数据包传递给目标用户，通常都会选择活跃度更高或紧密度更高的群体中的用户代传递。

# NSNC-DTN网络模型的数据包转发算法伪代码

1: begin   
2: for each ForwardNode_i do   
3: if(SourceNode(CurrentNode))   
4: then   
5: RLNC(CurrentNode)   
6: ForwardNode_i.addMessageToBuffer(encoding pack)   
7: else   
8: if(Clubof(CurrentNode) $\scriptstyle  \begin{array} { l } { \scriptstyle  \begin{array} { r l } \end{array} | = = } \\ { \scriptstyle  \begin{array} { r l } \end{array}  } \end{array}$ Clubof(DestinationNode))   
9: then   
10: C:if(Clubof(CurrentNode) $\scriptstyle =$ Clubof(DestinationNode)) and   
11: (NCAof(ForwardNode)>NCAof(CurrentNode)) and   
12: (NCAof(ForwardNode)<NCAof(DestinationNode))   
13: then   
14: if(!CenterNode(CurrentNode))   
15: then   
16: ForwardNode_i.addMessageToBuffer(message)   
17: else   
18: RLNC(CurrentNode)   
19: ForwardNode_i.addMessageToBuffer(encodingpack)   
20:else if (edgei(CurrentNode) $\ ! { = } 0$ ）   
21: CTmax(CurrentNode,ForwardNode)   
22: ForwardNode_i.addMessageToBuffer(message)   
23: else   
24: goto C   
25:end

# 3 实验及结果

对NSNC-DTN网络模型在真实网络中的性能表现进行评估。通过与经典路由转发算法在麻省理工大学 Reality MiningLab 提供的Reality 数据集[18]上进行比较，从而证明NSNC-DTN的可行性和有效性。

# 3.1对比指标参数

从以下三个参数维度来衡量NSNC-DTN 网络模型的性能表现：

a)数据交付成功率，投递到目的节点的数据包数目占总的发送的数据包数目的比例。NSNC-DTN网络模型的目标是使数据交付率尽可能接近洪泛法。

b)端到端网络传输延迟，成功投递到目的节点的数据包从源节点出发到达目的节点所需要的时间。长的延迟意味着数据包会长时间占据缓存，延迟越短性能表现越好。

c)网络代价，量化成数据包在DTN网络中缓存的副本数目。NSNC-DTN网络沿着一个路径发送，洪泛机制则是所有节点都

会保留一个副本，所以洪泛法在传输数量和节点缓存大小上都是一个网络代价的上限值。

# 3.2实验结果

为了方便计算，将计算节点活跃度的所需参数 $\alpha$ 、 $\beta$ 以及λ都等于0.5,即让节点连边数和节点连接的社团数在节点活跃度计算中所占权重相同。NSNC-DTN将真实数据集划分成8个社团，与现实情况相一致，在此情况下，考察NSNC-DTN的性能表现。

如图2所示，洪泛法拥有最高的数据投递成功率，NSNC-DTN网络模型与SANE方法和Clustering方法相比，拥有更高的数据投递成功率。在数据投递成功率上，NSNC-DTN网络模型相较于Clustering方法提高了 $1 8 . 2 \%$ ，相较于 SANE 方法提高了 $9 . 1 \%$ 。随着时间的推移，NSNC-DTN网络模型的节点负载均衡的优势就会体现出来，NSNC-DTN网络模型的数据投递成功率与SANE方法和Clustering方法相比的优势会越来越大。

![](images/6a23850f484a979563a0be8e2b7eeb9d3ae7aab30f2b3dda982f8e9bf257213c.jpg)  
图2交付成功率

如图3所示，洪泛法拥有最低的端到端延迟，由于NSNC-DTN网络模型中加入了社团紧密度和节点活跃度计算重新计算，使得每个节点都有机会成为转发节点，同时还引入了节点转发次数阈值，让每个节点不会因为缓存过大而影响数据传输。此外，网络模型对节点进行离线处理，根据转发节点次数阈值有针对的选择转发节点，从而缩短网络传输的延迟。

![](images/18419a3c4b6f69936e28de229d619830ad57fcd98732f2a3d4d069a2503c4b61.jpg)  
图3端到端延迟

如图4所示，洪泛法最容易产生丢包情况，所以网络代价随着时间推移而一直增加，洪泛法的平均网络代价约为Clustering 法的3.1倍，约为SANE算法的5.4倍，约为NSNC-DTN 网络模型开销的4倍。由于三种方法都仅仅保留一个消息副本，所以网络代价相较于洪泛法会小很多。

![](images/432b3a8d3cc094162ee8e80d8dc912219a94006160823d03cfd4930bd754044d.jpg)  
图4平均网络代价

# 4 结束语

DTN的研究主要针对非连续性连接和节点资源有时效性的一种网络数据传输方案，对军事领域、航天通信、应急抢险等领域的消息交互提供有效的技术支持。针对DTN网络的特殊性，提出一种基于节点社会性的网络模型，对社团划分算法做出改进，通社团紧密度和节点活跃度的计算比较选择出合适的转发节点，结合网络编码的技术进行消息的编码转发。仿真实验结果也证明了该网络模型对消息传输的可靠性和有效性。在实际网络环境中，DTN网络传输更为复杂，消息传输还会受到其他因素的影响，如节点本身的意愿。对综合因素的考虑和改进将是下一步研究的重点方向。

# 参考文献：

[1]Khabbaz M J,Assi C M,Fawaz WF.Disruption-tolernt networking:a comprehensive survey on recent developments and persisting challenges [J]. IEEE Communications Surveys& Tutorials,2012,14(2): 607-640.   
[2]Voyiatzis A G.A survey of delay-and disruption-tolerant networking applications [J].Journal of Internent Engineering,2012,5(1):331-344.   
[3]朱铁英，崔艳茹，李童，等．基于社会性的DTN网络路由算法研究[J]. 计算机工程,2012,38(14): 96-98.(Zhu Tieying,Cui Yanru,Li Tong,et al. Research of DTN routing algorithm based on sociality [J]. Computer Engineering,2012,38(14): 96-98.)   
[4]刘唐，彭舰，杨进．异构延迟容忍传感器网络中基于转发概率的数据传 输[J]．软件学报,2013,24(2):215-229.(Liu Tang,Peng Jian,Yang Jin. Data delivery for heterogeneous delay tolerant mobile sensor networks based on forwarding probability[J].Journal of Software,2013,24(2): 215- 229.)   
[5] 张振京，金志刚，舒炎泰．基于节点运动预测的社会性 DTN 高效路由 [J].计算机学报,2013,36(3):626-635.(Zhang Zhenjing,Jin Zhigang,Shu Yantai.Efcientrouting in social DTNbasedon nodes'movement prediction [J]. Chinese Journal of Computers,2013,36 (3): 626-635.)   
[6]Pan Hui, Crowcroft J, Yoneki E. Bubble rap: social-based forwarding in delay-tolerant networks [J]. Mobile Computing,2011,10 (11):1576-1589.   
[7]Dang H,Wu Hongyi.Clustering and cluster-based routing protocol for delay-tolerant mobile networks.IEEE Trans on Wireless Communications, 2010,9(6): 1874-1881.   
[8]Mei A,Morabito G,Santi P,et al. Social-aware stateless forwarding in pocket switched networks [C]//Proc of IEEE INFOCOM. 2011.   
[9] 贾建鑫，刘广忠，徐明.DTN 中基于时空和社会性的概率路由算法[J]. 计算机科学,2016,43(6∧):295-309.(Jia Jianxin,Liu Guangzhong,Xu Ming.Probability routing algorithm in DTN based on time and space and sociality[J]. Computer Science,2016,43 (6A): 295-309.)   
[10]黄宏程，熊忠阳，胡敏，等．节点移动状态感知的社会化延迟容忍网络 路由策略[J].计算机应用研究，2017,34(6):1826-1829.(Huang Hongcheng, Xiong Zhongyang,Hu Min,et al.Routing strategy based on change perception of node mobility characteristic in DTN[J]. Application Research of Computers,2017,34(6): 1826-189.)   
[11]郭稳涛，李兵，何怡刚．基于社会活性和副本限制的DTN路由算法 [J]. 电子测量与仪器学报,2017,31(7):1047-1052.(Guo Wentao,Li Bing,He Yigang.Social activity and copy-limited based DTN routing algorithm [J]. JournalofElectroiceasurementandIstrumentatio7,()4 1052.)   
[12] Newman M E J. Detecting community structure in networks [J]. The EuropeanPhysical JournalB,2004,38(2):321-330.   
[13] Girvan M,Newman ME J. Community structure in social and biological networks [J]. National Academy of Sciences,2002,99 (12): 7821-7826.   
[14] Radicchi F,Castellano C,Cecconi F,etal.Defining and identifying communities in networks [J].Proceedings of the National Academy of Science of the USA,2004,101(9): 2658-2663.   
[15] Wang Xiaofeng，Liu Gongshen，Pan Li,et al.Uncovering fuzzy communities in networks with structural similarity [J]. Neurocomputing, 2016,210 (1): 26-33.   
[16] Liu Weiping,Lu Linyuan.Link prediction based on local random walk [J]. EurophysicsLetters,2010,89 (5):58007-58012.   
[17] Meyn SP,TweedieRL.Markov chains and stochastic stability [M].Berlin: Springer-Verlag,1993.   
[18]Eagle N,Pentland A,Lazer D.Inferring social network structure using mobile phone data [J].National Academy of Sciences,2009,106 (36): 15274-15278.