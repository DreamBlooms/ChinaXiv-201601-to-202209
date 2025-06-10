# 多中继协作无线网络中基于随机线性网络编码的调度方案

王练，白佳洁，王萌，任治豪(重庆邮电大学 计算机科学与技术学院，重庆 400065)

摘要：为进一步提升多中继协作无线网络传输效率，提出一种基于随机线性网络编码的动态规划方案，以最小化重传次数为目标，综合考虑各中继节点的有效信息与链路传输可靠性，实现多中继协同转发，以提升传输有效性。在各转发链路相互独立的情况下，针对整个传输过程，自适应地选取状态转移路径，确定最优转发节点。仿真结果表明，本方案相比随机调度机制能显著提升平均吞吐量，减少重传次数。在降低对反馈信息依赖和减少反馈开销的同时，其性能皆逼近完全反馈下基于贪心算法的调度机制。

关键词：无线网络；随机线性网络编码；多中继；调度 中图分类号：TP393 doi:10.3969/j.issn.1001-3695.2018.01.0047

# Scheduling scheme for multi-relay cooperation based on random linear network coding in wireless network

Wang Lian,Bai Jiajie, Wang Meng,Ren Zhihao (InstituteofomputerSience&Techology,ChongqingUniversityofPosts&elecommunications,Chongqing4,Cina)

Abstract:To further improve the multi-relaycooperativetransmisioneficiency inwireless networks,this paperproposeda dynamic programming scheduling based on network coding with less feedback(DPNC-LF）.The DPNC-LF considered the efective informationofeachrelayandthe transmisionreliabilityofeach link,andimplemented themulti-relaycooperative forwardingto improve transmisson effectiveness with the minimum numberofretransmisions.Intheconditionof each link independent mutuallyand the state transitionpath selected adaptively,the DPNC-LFdetermined theoptimal forwarding node fortheentire transmissionprocess.The simulationresults showthatthealgorithmproposedinthis paperis more effective than randomselectionscheduling inaveragethroughputand the numberofretransmision.With the feedback informationdependence reducedandthe feedback overheaddecreased,the performanceofthis schemeiscloseto theperformanceof greedyalgorithm scheduling.

Key words: wireless network; random linear network coding; multiple-relay; scheduling

# 0 引言

随着移动智能设备数量的急剧增加，无线网络中多媒体应用受到广泛关注，多媒体业务对网络提出了更高的服务质量（qualityof service，QoS）要求。由于无线传输媒介的特殊性，数据包传输具有易失性，无线可靠传输技术已成为提升网络传输效率的关键。网络编码（network coding，NC）应用于无线网络已被证明能有效改善网络吞吐量[1]。其中，基于网络编码的传输方案为多播传输提供有效途径。而随机线性网络编码（randomlinearnetwork coding,RLNC）已被证明是一种能实现最优吞吐量的网络编码构造方法[2.3]，且被广泛应用。另一方面，中继协作的提出能有效克服无线衰落，特别在中继协作广播网络中可达速率等基本特征能得到显著提高[4]。在此基础上，文献[5]为在单信源单中继模型下基于随机线性网络编码实现，提出立即反馈的一步调度和减少反馈的多步调度方案。文献[6,7]以最小化重传次数为目标，在源节点广播数据包后提出一种确定性算法寻找再生编码向量，并利用稀疏编码向量缩小编码空间，降低了解码复杂度。文献[8]提出基站-中继竞争调度算法（BS-relay competive scheduling algorithm，BRCS），以最大化网络吞吐量。文献[9]基于机会式网络编码提出了一种加权数据包调度算法，该方法通过最大化传输增益来到达最小化完成时间的目的。在文献[10]中对该方法进行拓展，通过各接收节点之间相互协作，提出自适应协作随机网络编码调度

（cooperative and adaptive random network coding，CARNC）。文献[11]则分别针对完美反馈、受限反馈和无反馈三种反馈情况下的传输性能进行对比分析。上述单中继协作策略，提出了高性能的中继协作调度方案，为多中继协作传输的研究提供了相关方向和思路。因网络场景的差异，链路条件设置需进一步思考。文献[12,13]为多中继节点协作传输的调度方案。文献[12]针对无线网络基于随机线性网络编码的多中继协作传输提出自适应转发调度（adaptive forwarding with network coding，AF-NC）和自适应转发重传调度（adaptive forwarding with network coding and retransmision，AFR-NC）。AF-NC方案避免传输已有数据包，通过重传请求数据包，增加传输可靠性。AFR-NC 则在前者的基础上结合了ARQ（automatic repeatrequest），该方案不受丢失概率的影响，性能稳定。但该方案对给定的多源模型，依次单独执行各源节点的传输，传输效率不高。文献[13]则提出多源多中继协作传输中基于网络编码的优先级调度方案（priority scheduling based onnetwork coding，PSNC)，不同于传统基于单信源、随机或顺序调度的方案，该方案的思想是根据不同的转发链路状态，通过预算有效信息包的最优到达数实现调度，能有效提高网络吞吐量，减少重传次数。但PSNC 方案主要针对单接收节点进行考虑，接收节点获取信息的完全来源于中继节点，且每一次转发重传依赖更新的反馈信息，该方法每一步都执行所选性能指标的最优操作，同时也将带来资源开销和时间的延迟，即反馈开销。在系统规模小，接收节点较少时，反馈开销可忽略不计，当接收节点增长到一定数量时，反馈开销将不可忽视。

上述调度方案中，转发链路状态的条件设置偏理想化，与实际网络场景存在差异。基于顺序转发或随机转发的调度方案可能重复转发相同信息，造成资源浪费且传输性能依赖反馈信息。本文针对无线多跳广播模型，对不同链路状态下的中继协助传输方案进行分析研究，针对多中继协作网络环境提出使用更少反馈的基于网络编码的动态规划调度方案(dynamic programmingscheduling based on network coding with lessfeedback，DPNC-LF)，本方案将最小化重传次数的目标转换为方案中求最短路径问题，并综合考虑转发节点可提供的有效信息与各链路差异，选取提供最大预计信息量的状态转移路径，从而进行节点选取，以获取转发操作集。为验证DPNC-LF 方案的有效性，本文对系统吞吐量和重传次数进行了分析和仿真。参考典型调度方案的转发节点选取方法，结合本文网络模型，提出完全反馈下基于网络编码的贪心调度方案（greedy algorithm scheduling based on network codingwith complete fedback，GANC-CF）和完全反馈下基于网络编码的随机选择调度方案（random selectionschedulingbased onnetworkcoding with complete fedback，RSNC-CF），将其与DPNC-LF方案进行性能仿真对比。结果表明，DPNC-LF方案在降低对反馈信息依赖和减少反馈开销的同时，在一定条件下保持高吞吐量与可靠性。

# 1 系统模型

无线多跳网络模型包含一个源节点 $s$ ， $M$ 个中继节点 $R = \left\{ R _ { i } \ : | \ : i \in \left\{ 1 , 2 , \cdots , M \right\} \right\}$ 和 $N$ 个接收节点 $u = \left\{ u _ { j } \vert j \in \left\{ 1 , 2 , \cdots , N \right\} \right\}$ 。如图1所示中继协作网络模型，中继节点数 $M = 2$ ，接收节点数 $N = 3$ 。考虑到网络节点的移动性，接收节点 $\boldsymbol { u } _ { j }$ 的位置随机分布。系统以半双工方式实现信息传输，且单位时隙仅能传输一个数据包。源节点 $s$ 向中继节点 $R _ { i }$ 和接收节点 $\boldsymbol { u } _ { j }$ 广播 $L$ 个原始数据包$P { = } \{ P _ { 1 } , P _ { 2 } , { \cdots } , P _ { L } \}$ 。 $R _ { i }$ 接收来自 $s$ 的数据包，并协助 $s$ 传输数据包给 $\boldsymbol { u } _ { { } _ { j } }$ ，同时将接收情况反馈给S。由于中继节点仅用于协助源节点， $R _ { i }$ 不需要接收到所有的数据包。 $\boldsymbol { u } _ { { } _ { j } }$ 接收来自 $s$ 和 $R _ { i }$ 的信息，并将接收状态信息反馈给S和 $R _ { i }$ 。为避免冲突， $s$ 与 $R _ { i }$ 不允许同时进行传输信息。

![](images/3e2abec669484af288223a6f31f1215241081895359dbeaaa70a2566029d5823.jpg)  
图1 $M = 2$ ， $N { = } 3$ 中继协作系统模型

各传输链路相互独立，分别用 $P _ { s r _ { i } }$ ， $P _ { s u _ { j } }$ 和 $P _ { R _ { i } u _ { j } }$ 表示源节点 $s$ 到中继节点 $R _ { i }$ ，源节点 $s$ 到接收节点 $\boldsymbol { u } _ { { } _ { j } }$ 和中继节点 $R _ { i }$ 到接收节点$\boldsymbol { u } _ { j }$ 的链路丢包率，其大小受信道环境和传输距离等因素影响,且丢包信息通过反馈信号 ACK/NACK（acknowledgment/negativeacknowledgment）获取。

# 2 传输调度方案

# 2.1问题描述

本文在有限域 $G F ( q )$ 上采用随机线性网络编码，且确保 $q \geq N$ [14]。DPNC-LF 方案中将传输过程分为初始阶段和重传阶段。初始阶段，源节点广播数据包。源节点发送 $L$ 个 RLNC 包，使用 $C _ { i } = \sum _ { j = 1 } ^ { L } \alpha _ { i j } W _ { j }$ 表示源节点产生的第 $i$ 个编码数据包，其编码向量为$\pmb { \alpha } _ { i } = [ \alpha _ { i 1 } , \alpha _ { i 2 } , \cdots , \alpha _ { i L } ]$ 。重传阶段，利用编码矩阵之间的线性关系，进行数据包的重传。根据 RLNC 的特性，RLNC 在有限域 $G F ( q )$ 内随机选取编码系数，当有限域大小为 $2 ^ { 8 }$ 时，生成任意两个线性相关编码包的概率可以小到忽略不计[2]，生成两个相同编码包的可能性则更低。因此使用编码向量之间的线性关系作为新的反馈依据表示各节点接收到数据包的情况。

受传输链路丢包的影响，接收节点和中继节点可能仅能接收到部分信息，本文利用状态反馈矩阵 $E$ 表示接收与反馈情况。假定接收节点 $\boldsymbol { u } _ { { } _ { j } }$ 的状态反馈矩阵为 $E _ { u _ { j } }$ ，则 $R a n k \Big ( E _ { u _ { j } } \Big )$ 可表示 $\boldsymbol { u } _ { j }$ 收到的有效编码数据包数。当 $R a n k \left( E _ { u _ { j } } \right) < L$ ，则需转发节点重传缺失编码数据包。重传过程中，每成功接收一组线性无关编码向量，则 $R a n k \Big ( E _ { u _ { j } } \Big )$ 增加1，且对于所有接收节点，当满足条件$R a n k \Big ( E _ { u _ { j } } \Big ) = L$ ，则表示该接收节点收到所有编码数据包，传输完成。重传中，若存在多个转发节点能给接收节点提供有效信息包，则根据调度方案选取最优转发节点，使得接收节点能快速有效地解码信息。本文相关符号定义，如表1所示。

表1相关符号定义  

<html><body><table><tr><td>符号</td><td>含义</td></tr><tr><td>M</td><td>中继节点数</td></tr><tr><td>N</td><td>接收节点数</td></tr><tr><td>L</td><td>原始数据包数</td></tr><tr><td>R</td><td>第i个中继节点</td></tr><tr><td>uj</td><td>第j个接收节点</td></tr><tr><td>Psr</td><td>S到Ri的链路丢包率</td></tr><tr><td>Psuj</td><td>S到u的链路丢包率</td></tr><tr><td>PRiuj</td><td>Ri到uj的链路丢包率</td></tr><tr><td>Euj</td><td>uj的编码矩阵</td></tr><tr><td>Ea</td><td>采取a操作时转发节点的编码矩阵</td></tr><tr><td>a</td><td>选择转发节点的操作</td></tr><tr><td>A</td><td>转发操作a 的集合</td></tr><tr><td>rj</td><td>接收节点u；的秩</td></tr><tr><td>Fj</td><td>中继节点和接收节点的串联矩阵</td></tr><tr><td>h(t,a)</td><td>采取a操作的转发节点能给接收节点提供线性无关编码向量数</td></tr><tr><td>St</td><td>t时刻各接收节点收到有效信息包数</td></tr><tr><td>d</td><td>状态转移过程中可能存在的状态数</td></tr><tr><td>V</td><td>最小重传次数</td></tr><tr><td>W</td><td>最小重传次数下的状态转移路径数</td></tr><tr><td>X(st,a)</td><td></td></tr><tr><td>X(s|s,a)</td><td>即时预计信息量 经V次重传获得的预计信息量</td></tr></table></body></html>

# 2.2相关定义

定义1操作集 $A$ 。传输阶段，每个时隙将在源节点和中继节点中选择发送节点，进行信息的传输，存在以下 $i + 1$ 种操作：$a = 0$ ：由源节点 $s$ 传输数据包； $a = i$ ：由中继节点 $R = \left\{ R _ { i } | i \in \left\{ 1 , 2 , \cdots , M \right\} \right\}$ 传输数据包。

转发操作集 $A$ 为重传选取操作 $a$ 的集合，即选取的所有转发节点的集合。

定义2状态反馈矩阵 $E$ 。传输过程中中继节点和接收节点成功接收数据包后，在接收端或中继处将生成 $L { \times } L$ 的状态反馈矩阵 $E$ ，如式（1）所示，用以表示节点接收到编码数据包的情况。

$$
E = \left[ \begin{array} { c c c c c } { \alpha _ { _ { 1 1 } } } & { \alpha _ { { _ { 1 2 } } } } & { \cdots } & { \alpha _ { _ { 1 L } } } \\ { \alpha _ { _ { 2 1 } } } & { \alpha _ { _ { 2 2 } } } & { \cdots } & { \alpha _ { _ { 2 L } } } \\ { \vdots } & { \vdots } & { \vdots } & { \vdots } \\ { \alpha _ { _ { i 1 } } } & { \alpha _ { _ { i 2 } } } & { \cdots } & { \alpha _ { _ { i L } } } \\ { \vdots } & { \vdots } & { \vdots } & { \vdots } \\ { \alpha _ { _ { L 1 } } } & { \alpha _ { _ { L 2 } } } & { \cdots } & { \alpha _ { _ { L } } } \end{array} \right]
$$

定义3增益函数 $h _ { j } \left( t , a \right)$ 。定义在 $t$ 时刻采取 $a$ 操作，该转发节点能给接收节点 $\boldsymbol { u } _ { j }$ 提供有效信息量的大小，记做 $h _ { j } \left( t , a \right)$ 。

$$
h _ { j } \left( t , a \right) = R a n k \left( \left[ E _ { { u } _ { j } } ; E _ { a } \right] \right) - r _ { j }
$$

其中： $R a n k \Big ( \Big [ E _ { u _ { j } } , E _ { a } \Big ] \Big )$ 表示矩阵 $E _ { u _ { j } }$ 与矩阵 $E _ { a }$ 的串联矩阵 ${ \scriptstyle { \left[ { E _ { u _ { j } } } ; E _ { a } \right] } } = { \left[ { E _ { u _ { j } } } atop { E _ { a } } \right] }$ 的秩大小。

定义4状态向量 $s _ { t }$ 。状态向量 $\pmb { S } _ { t } = \left[ r _ { 1 } ~ r _ { 2 } ~ \cdots ~ r _ { N } \right]$ 表示所有接收节点当前的接收信息情况， $r _ { j }$ 为接收节点 $\boldsymbol { u } _ { { } _ { j } }$ 当前时刻状态反馈矩阵秩的大小。状态空间 $\pmb { S } = \left[ \pmb { S } _ { 1 } \ \pmb { S } _ { 2 } \ \cdots \ \pmb { S } _ { d } \right]$ 包含所有可能存在的状态向量，其中目标状态 $\pmb { S } _ { d } = \left[ L \pmb { L } \cdots L \right]$ 。

定义5状态转移概率 $P \big ( s _ { t + I } | s _ { t } , u _ { j } , a \big )$ 。定义由状态 $s _ { t }$ 到状态 $s _ { t + 1 }$ 采取 $\boldsymbol { a }$ 操作的各链路丢包概率， $r _ { t }$ 与 $r _ { t + l }$ 为状态 $s _ { t }$ 和状态 $s _ { t + 1 }$ 下接收节点 $\boldsymbol { u } _ { { } _ { j } }$ 反馈矩阵秩的大小。

$$
P \left( s _ { t + I } \middle | s _ { t } , u _ { j } , a \right) = \left\{ \begin{array} { l l } { 0 } & { , } \\ { 0 } & { , } \\ { P _ { e } \left( u _ { j } , a \right) } & { , } \\ { P _ { e } \left( u _ { j } , a \right) } & { r _ { t + I } = r _ { t } < N } \\ { 1 - P _ { e } \left( u _ { j } , a \right) } & { , r _ { t + I } - r _ { t } = 1 } \\ { 1 } & { , } \\ { 1 } & { r _ { t + I } = r _ { t } = N } \end{array} \right.
$$

其中： $P _ { e } \left( u _ { j } , a \right) = \left\{ \begin{array} { l l } { P _ { s u _ { j } } , } & { \mathrm { i f } \ a = 0 } \\ { P _ { R _ { i } u _ { j } } , } & { \mathrm { i f } \ a = i } \end{array} \right.$

# 2.3调度算法

无线多跳网络模型下，DPNC-LF方案以最小化重传次数为目标，综合考虑转发节点的有效信息与链路可靠性，选取最优转发节点。该方案考虑到同一重传信息被多个接收节点需求的情况，从整体角度出发，一次集中重传多个接收端所需信息，增加单位时间传输的预计信息量，具体步骤描述如下。

# 1）初始阶段

源节点广播 $L$ 个数据包，中继节点和接收节点接收源节点广播的数据包并反馈接收情况。经历 $L$ 个时隙，传输进入重传阶段。

# 2）源节点重传阶段

此时，中继节点和接收节点已接收到部分或者全部信息。此阶段保证任意转发节点包含各接收节点所缺少的数据包，以保障重传的可靠性。

串联中继节点和接收节点的状态矩阵，并验证此串联矩阵 $F _ { _ j }$ 是否存在 $L$ 个线性无关向量，即判断条件 $r _ { { r } _ { j } } = L$ 是否成立，其中$r _ { { { { { r } } _ { j } } } }$ 为串联矩阵 $F _ { j }$ 秩的大小。若成立，传输进入阶段3)，否则将执行操作 $a = 0$ 直至条件 $r _ { { { r } _ { j } } } = L$ 得到满足。

$$
r _ { F _ { j } } = R a n k \Big ( \Big [ E _ { u _ { j } } ; E _ { a } \Big ] \Big )
$$

# 3）选择重传阶段

此阶段中，在 $s$ 与 $R _ { i }$ 之间进行选择重传直至信息传输完毕。首先，确定最小化重传次数 $V$ 。然后，对最小重传次数下的W 种状态转移路径进行性能对比，选取最优转移路径。最后，通过计算获取转发操作集 $\boldsymbol { A } ^ { * }$ 。由于重传不可靠，每隔 $V$ 个时隙对信息接收情况进行一次反馈，验证传输是否完成。若未完成，则根据更新反馈信息继续重传。

a)确定最小化重传次数 $V$ 。由于每个时隙仅传输一个数据包，则由最大信息丢失节点的丢包数来确定最小化重传次数V。

$$
V = m a x { \left( L - r _ { j } \right) }
$$

b)将选取状态转移过程转换为最短路径问题求解，确定最短状态转移路径。

转移根据反馈信息，获取当前丢包情况。给定当前 $t$ 时刻状态 $\pmb { S } _ { t } = \pmb { S } _ { 1 }$ ，期望目标状态为 $s _ { d }$ (即各接收节点达到满秩状态)，则$t + 1$ 时刻可能到达的状态 $\pmb { S } _ { t + 1 } = \left\{ \pmb { S } _ { 1 } , \pmb { S } _ { 2 } , \cdots , \pmb { S } _ { d } \right\}$ 。总共存在 $d$ 种状态。重传过程即为从初始状态 $\pmb { s } _ { 1 }$ 至目标状态 $s _ { d }$ 的状态转移过程，传输中存在中间状态 $s _ { p } \left( p \in \left\{ 2 , 3 , \cdots , k - 1 , k , k + 1 , \cdots , l , l + 1 , \cdots , d - 1 \right\} \right) \circ$

$$
d = \prod _ { j = 1 } ^ { N } \left( L - r _ { j } + 1 \right)
$$

$$
W = \prod _ { j = 1 } ^ { N } { \binom { L - r _ { j } } { V } }
$$

将所有状态转换为状态节点，并将通过一次重传能到达的状态节点相连接，得到状态图，如图2所示。根据状态图计算由状态节点 $\pmb { S } _ { 1 }$ 到达 $s _ { d }$ 的最短路径，假定各状态节点之间为单位距离，则最短路径距离大小等于最小重传次数 $V$ 。此时，存在W 条路径通过 $V$ 次传输可由初始状态 $\pmb { s } _ { 1 }$ 至目标状态 $s _ { d }$ 。通过计算，若此时 $W { = } 1$ ，则该路径为最短状态转移路径，若 $W \not = 1$ ,则需综合考虑各链路状态等因素。

![](images/a9ca8ed811177f0e12f992eab5c44d4755d7f02bcb4c3bce6572c6f547105419.jpg)  
图2状态转移示意图

c)综合考虑转发节点可提供的有效信息量与各链路差异，通过计算获取最优路径与转发操作集。

当存在多条最短路径时，由已确定的状态转移路径，计算预计即时信息量 $X \left( s _ { t } , a \right)$ ,表示在状态 $s _ { t }$ 采取 $\boldsymbol { a }$ 操作时到达状态 $s _ { t + 1 }$ ，各接收节点预计能收到有效信息量的大小。将 $V$ 次重传的 $X \left( s _ { t } , a \right)$ 叠加，得到重传预计信息量 $X \left( s _ { d } \vert s _ { 1 } , a \right)$ 。通过对比预计信息量的大小，选取能带来最大预计信息量的转移路径，并根据式（11）获取最优转发节点，操作集 $\boldsymbol { A } ^ { * }$ 由单次最优转发节点 $\boldsymbol { a } ^ { * }$ 所构成。

$$
X \left( s _ { t } , a \right) = \sum _ { j = 1 } ^ { N } \Bigl [ P \left( s _ { t + l } \left| s _ { t } , u _ { j } , a \right. \right) \bullet h _ { j } \left( t , a \right) \Bigr ]
$$

$$
X \left( s _ { d } { \big | } s _ { 1 } , a \right) = \sum _ { t = 1 } ^ { t = V } X \left( s _ { t } , a \right)
$$

$$
a ^ { * } { = } \mathrm { a r g m a x } X \left( s _ { t } , a \right)
$$

由于重传不可靠，经历 $V$ 次重传后，仍可能存在信息包丢失，此时根据更新的反馈信息重复 Phase II，直至所有接收节点实现完全解码。

例当传输进入阶段Phase III，设 $M = 2$ ， $N = 2$ ， $L = 3$ ， $P _ { s u _ { 1 } } = 0 . 4 5$ ， $P _ { s u _ { 2 } } = 0 . 6$ ， $P _ { \eta u _ { 1 } } = 0 . 3 5$ ， $P _ { \eta u _ { 2 } } = 0 . 2 5$ ， $P _ { { _ { r 2 u _ { 1 } } } } = 0 . 1 5$ ，$P _ { _ { r _ { 2 } u _ { 2 } } } = 0 . 4$ 。根据中继节点和接收节点的接收状态反馈结果，当前接收状态 $s _ { t } = s _ { { } _ { 1 } } = \left[ r _ { { } _ { 1 } } r _ { { } _ { 2 } } \right] = \left[ 1 2 \right]$ 。

首先，确定最小化重传次数。有式（6）可知：

$$
V = m a x \big ( L - r _ { j } \big ) = 3 { \cdot } 1 { = } 2
$$

然后，确定最短状态转移路径。从初始状态 $\pmb { S } _ { 1 }$ 至目标状态 $s _ { d }$ ，一共可能存在六种状态: $\pmb { S } _ { 1 } = \left[ 1 2 \right]$ ， $\pmb { S } _ { 2 } = \left[ 2 2 \right]$ ， $\boldsymbol { s } _ { 3 } = \left[ 1 3 \right]$ ， $\pmb { S } _ { 4 } = \left[ 2 \ 3 \right]$ ，$\mathbf { \sigma } _ { s _ { 5 } } = \left[ 3 2 \right]$ ， $\mathbf { \boldsymbol { s } } _ { 6 } = \mathbf { \boldsymbol { s } } _ { d } = \left[ 3 \ 3 \right]$ 。由当前状态 $\pmb { S } _ { t } = \pmb { S } _ { 1 }$ ，通过一次转发重传，可以轻易的到达其他另外三个状态 $\pmb { S } _ { 2 }$ 、 $\pmb { S } _ { 3 }$ 与 $\pmb { S } _ { 4 }$ ，通过两次重传可由中间状态到达目标状态 $s _ { d }$ 。则最短路径为： ${ s } _ { 1 }  { s } _ { 4 }  { s } _ { 6 }$ 与 ${ \pmb S } _ { 1 }  { \pmb S } _ { 2 }  { \pmb S } _ { 6 }$ 。

最后，通过计算获取最优路径及转发操作集。通过式（9,10）计算预计即时信息量 $X \left( s _ { t } , a \right)$ 与重传预计信息量 $X \left( s _ { d } \vert s _ { 1 } , a \right)$ 。

最短路径 ${ \pmb S } _ { 1 }  { \pmb S } _ { 4 }  { \pmb S } _ { 6 }$ 的最大重传预计信息量计算如下：

$$
\begin{array} { c l } { { \displaystyle { X _ { \scriptscriptstyle 1 } \Big ( s _ { \scriptscriptstyle d } \Big | s _ { \scriptscriptstyle 1 } , a \Big ) = \sum _ { \scriptscriptstyle t = 1 } ^ { \scriptscriptstyle t = V } X _ { \scriptscriptstyle 1 } \big ( s _ { \scriptscriptstyle t } , a \big ) } } } \\ { { = X _ { \scriptscriptstyle 1 } \big ( s _ { \scriptscriptstyle 1 } , a \big ) + X _ { \scriptscriptstyle 1 } \big ( s _ { \scriptscriptstyle 4 } , a \big ) } } \end{array}
$$

其中:由状态 ${ \pmb s } _ { 1 }  { \pmb s } _ { 4 }$ ，当使用源节点进行转发重传的预计即时吞吐量为

$$
\begin{array} { l } { { \displaystyle X _ { \scriptscriptstyle 1 } \big ( s _ { \scriptscriptstyle 1 } , 0 \big ) = \sum _ { j = 1 } ^ { 2 } \biggl [ P \big ( s _ { \scriptscriptstyle 4 } \big | s _ { \scriptscriptstyle 1 } , u _ { \scriptscriptstyle j } , 0 \big ) { \bullet h _ { \scriptscriptstyle j } \big ( t , 0 \big ) } \biggr ] } } \\ { { \displaystyle ~ = 0 . 5 5 + 0 . 4 } } \\ { { \displaystyle ~ = 0 . 9 5 } } \end{array}
$$

分别地，可计算出各预计即时信息量如下：

$$
X _ { 1 } \left( s _ { 1 } , 1 \right) = 1 . 4 \ , \ X _ { 1 } \left( s _ { 1 } , 2 \right) = 1 . 4 5 \ , \ X _ { 1 } \left( s _ { 4 } , 0 \right) = 0 . 5 5 \ , \ X _ { 1 } \left( s _ { 4 } , 2 \right) = 0 . 6 5 \ , \ X _ { 1 } \left( s _ { 4 } , 2 \right) = 0 . 8 5 \ ,
$$

$$
\operatorname* { m a x } X _ { 1 } \Big ( s _ { d } \vert s _ { 1 } , a \Big ) = X _ { 1 } \big ( s _ { 1 } , 2 \big ) + X _ { 1 } \big ( s _ { 4 } , 2 \big ) = 2 . 3
$$

同理，计算最短路径的 $s _ { \scriptscriptstyle 1 } \to s _ { \scriptscriptstyle 2 } \to s _ { \scriptscriptstyle 6 }$ 最大重传预计信息量max $X _ { _ 2 } \left( s _ { _ d } | s _ { 1 } , a \right) = 2 . 3$ 此时，两路径最大重传预计信息量相等，选取任意最短路径进行重传转发，通过式(11)，获取转发操作集 $A ^ { * } = \{ 2 , 2 \}$ 。

$$
\boldsymbol { O u t p u t . } \quad \boldsymbol { A } ^ { * } = \left[ \boldsymbol { a } _ { 1 } ^ { * } , \cdots , \boldsymbol { a } _ { t } ^ { * } , \cdots , \boldsymbol { a } _ { T } ^ { * } \right]
$$

//初始阶段

$$
a _ { 0 } \gets a _ { t }
$$

while $\left( r _ { j } \ge L \right)$ //各接收节点不能实现解码

$$
\textit { i f } \ F _ { j } = R a n k \left( \left[ \ E _ { u _ { j } } , E _ { a } \right] \right) \geq L
$$

for $W$ //最小重传次数下可能的状态转移路径数

$$
W \gets \prod _ { j = 1 } ^ { N } { \binom { L - r _ { j } } { V } }
$$

$$
i f \ \left( P \Big ( s _ { t + I } \big | s _ { t } , u _ { j } , a \Big ) > 0 \right) \ E \left( h \big ( t , a \big ) \neq 0 \right)
$$

$$
\textit { d o } X \left( s _ { t } , a \right) \gets \sum _ { j = 1 } ^ { N } \Bigl [ P \left( s _ { t + I } \left| s _ { t } , u _ { j } , a \right. \right) \bullet h _ { j } \left( t , a \right) \Bigr ]
$$

V/计算预计即时信息量

$$
\begin{array} { r l } & { X \left( s _ { d } | s _ { 1 } , a \right) \gets X \left( s _ { t } , a \right) } \\ & { } \\ & { a ^ { * } \gets \mathrm { a r g m a x } X \left( s _ { t } , a \right) } \end{array}
$$

$A ^ { ^ { * } }  a ^ { ^ * }$ //获取最优转发操作集

# 2.4性能分析

# 2.4.1系统吞吐量

对整个系统，为量化调度算法的效率，定义系统吞吐量 $\eta$ ：

$$
\ \eta = { \frac { L } { T } }
$$

其中： $T$ 为收到所有丢包所需传输次数， $L$ 为传输数据包数。最大化系统网络吞吐量，即最大化单位时隙接收节点收到的信息量。由上述可知， $T$ 由初始广播时间 $T _ { \scriptscriptstyle { 1 } }$ 和重传时间 $T _ { 2 }$ 构成。假定所期望的系统完成时间为 $E \big ( T \big )$ ，其取值范围为：

$$
\begin{array} { r } { \left[ E \big ( T \big ) \right] _ { \mathrm { m i n } } \leq E \big ( T \big ) \leq \big [ E \big ( T \big ) \big ] _ { \mathrm { m a x } } } \end{array}
$$

$\left[ E ( T ) \right] _ { \mathrm { { m i n } } }$ 为理想的传输情况,即源节点广播后接收节点接收到所有编码数据包所需时间。

$$
{ \Big [ } E ( T ) { \Big ] } _ { \operatorname* { m i n } } = L
$$

为求最大期望值 $\big [ E ( T ) \big ] _ { \operatorname* { m a x } }$ ，Phase I假定各中继节点与接收节点未获取数据包。Phase I，中继节点接收到所有的数据包而接收节点未获取数据包。 $L$ 个数据包被 $M$ 个中继全部成功接收的时隙期望为 $M \Big / \big ( 1 - P _ { s r _ { i } } \big ) ^ { L }$ 。Phase II中，重传数据包由链路丢包率最大的节点进行信息传输，则最大期望值为

$$
\Big [ E \big ( T \big ) \Big ] _ { \operatorname* { m a x } } \leq L + M \Big / \Big ( 1 - P _ { s r _ { i } } \Big ) ^ { L } + \sum _ { j = 1 } ^ { N } \frac { L } { 1 - \operatorname* { m a x } P _ { e } \Big ( u _ { j } , a \Big ) }
$$

# 2.4.2重传次数

重传次数由系统传输过程的两部分组成:一为Phase I阶段各中继节点为满足条件 $r _ { { r } _ { j } } = L$ ，确保下一阶段任意转发节点重传可靠所需重传次数；二为Phase III阶段各接收节点达到满秩状态，各转发节点重传数据包的次数。

# 3 仿真实验与分析

本节与GANC-CF方案以及RSNC-CF方案进行性能仿真对比。各方案在初始阶段操作一致，重传阶段描述分别如下：RSNC-CF方案将随机选择转发节点进行转发重传且在重传后反馈接收情况。GANC-CF方案则在 $s$ 和 $R _ { i }$ 之间进行选择重传直至传输完成且每完成一次传输， $R _ { i }$ 和 $\boldsymbol { u } _ { j }$ 反馈接收情况。根据反馈信息，结合链路丢包情况与单位时间可传输信息量选取最优转发节点进行重传。

$$
X \left( s _ { t } , a \right) = \sum _ { j = 1 } ^ { N } \Bigl [ P \left( s _ { t + l } \left| s _ { t } , u _ { j } , a \right. \right) \bullet h _ { j } \left( t , a \right) \Bigr ]
$$

$$
a ^ { * } { = } \mathrm { a r g m a x } X \left( s _ { t + I } \middle | s _ { t } , a \right)
$$

GANC-CF方案与DPNC-LF方案转发节点的选取均考虑到有效信息量与链路传输可靠性，区别于GANC-CF方案，DPNC-LF方案在最小化重传次数条件下结合上述因素进行节点的选取，同时有效减少系统反馈，降低反馈开销。

针对数据包的平均重传次数和系统平均吞吐量进行性能对比。平均重传次数为单个接收节点成功接收所有编码数据包所需要的重传次数。系统平均吞吐量为多次实验所获取系统吞吐量的均值。为避免仿真结果的偶然性，多次实验取平均值确保仿真结果的有效性。实验参数设置 $M = 5$ ， $N = 3$ ,源节点到中继节点的链路丢包率 $P _ { s r _ { i } } = \left[ 0 . 3 5 , 0 . 5 5 , 0 . 3 , 0 . 2 , 0 . 4 \right]$ ，各中继节点到接收节点的链路丢包率分别为：

$$
\begin{array} { r l } { P _ { r \mu \nu _ { i } } = \left[ 0 . 3 5 , 0 . 3 5 , 0 . 2 5 \right] , P _ { \mu \nu _ { i } } = \left[ 0 . 7 , 0 . 7 , 0 . 3 5 \right] , P _ { \nu \mu \nu _ { i } } = \left[ 0 . 4 , 0 . 4 , 0 . 7 \right] \quad } & { , P _ { \mu \nu _ { i } } = \left[ 0 . 2 5 , 0 . 2 5 , 0 . 7 \right] , P _ { \nu \mu \nu _ { i } } = \left[ 0 . 4 5 , 0 . 6 , 0 . 3 5 \right] , } \end{array}
$$

其中， $i \in \left\{ 1 , 2 , \cdots , M \right\}$ ， $j \in \left\{ 1 , 2 , \cdots , N \right\}$ ，实验结果如图3-6所示。

如图3所示，数据包数由 $L = 1 0$ 变化至 $L = 6 0$ ，数据包的平均重传次数随传输包数的增加而增加。GANC-CF方案和DPNC-LF 方案的性能相接近且明显优于RSNC-CF 方案，所传输数据包数越多差异越明显。GANC-CF 方案每次重传前，根据接收节点和中继节点的信息接收反馈情况，结合转发节点提供信息和链路丢包率综合考虑进行转发节点的选取，增加传输可靠性，提高成功率。DPNC-LF方案通过最短路径的方法来确立该条件下的状态转移路径，并在此基础上计算最优转发节点，降低反馈开销的同时，选取能提供更多有效信息的节点进行重传，其性能与GANC-CF 方案相接近。RSNC-CF 方案为随机调度，其结果不稳定，与GANC-CF方案和DPNC-LF方案有一定差距，且 $L$ 的增加会导致同一数据包被反复传输而加剧与其他方案之间的差距。如图4所示，对比各方案的平均吞吐量受数据包数变化的影响。GANC-CF方案和DPNC-LF方案结果相接近，且随数据包数的增加平均吞吐量缓慢减少。RSNC-CF方案的平均吞吐量随传输包数的变化较为平缓，且明显低于其他两种方案。GANC-CF 方案和DPNC-LF方案根据接收情况选取可能带来最大信息量的节点作为转发节点，提升单位时间内接收节点收到的有效信息量。

![](images/813af885eaf8c638542837da40e535297d291e9ec7f76d71fba81169baa3a7d6.jpg)

![](images/8303c77125a5b34a25d07c011be6aabefeaf8e73ce5a0352934777fe5c2623f2.jpg)  
图3平均重传次数性能对比（数据包数变化情况下）

![](images/7cc52ae92ddbdc045379d6cc0fb711fe04aa3a376a2ff3c0ec3284de898a89ed.jpg)  
图4平均吞吐量性能对比(数据包数变化情况下）

![](images/1beef5125255b29ef1da43e765e2b180a3111891c13235cdce0ba76fb7d2b19f.jpg)  
图5平均重传次数性能对比（丢包率方差期望比变化）  
图6平均吞吐量性能对比(丢包率方差期望比变化)

如图5、6所示，数据包平均重传次数和系统平均吞吐量随转发链路状态差异变化而变化。由图可知，传输性能受接收节点的丢包率影响，为准确反映丢包率变化对传输性能的影响，选取方差与期望值的比值作为参数变量，表示转发链路之间的丢包差异。

如图5所示，其他条件不变，各转发链路之间的丢包差异增大，数据包的平均重传次数也逐渐增加。各方案的性能随转发链路之间的丢包差异的增加而越发明显，当丢包率方差期望比到达0.12后，RSNC-CF 方案的平均重传次数急剧上升。如图6所示，在其他条件不变，各转发链路之间的丢包差异增大，数据包的平均吞吐量整体呈急剧下降趋势，GANC-CF 方案和DPNC-LF方案的性能接近而整体优于RSNC-CF方案。由于重传不可靠，随着转发链路之间的丢包差异增大，RSNC-CF方案在重传的过程中，可能会选择到提供较少可靠信息量的转发节点，特别当链路集增大，这种差异将更加明显。

![](images/88e440c206249f3dca7ae17619fdb07dbe517480ee664d9d1ee3619bd1af299a.jpg)  
图7平均重传次数性能对比（中继节点数变化情况下）

![](images/047c2cd6fb42dce2a1259c50d9603970af080345471b8bfdbae4ea08d9e154f9.jpg)  
图8平均吞吐量性能对比（中继节点数变化情况下)

图7、8为数据包平均重传次数和系统平均吞吐量随中继节点数变化而变化的情况。如图7所示，其他条件不变随着中继节点数增加，数据包的平均重传次数在不断减少。如图8所示，在其他条件不变，中继节点数增加，数据包的平均吞吐量整体呈急剧上升趋势，GANC-CF方案略优于DPNC-LF方案的性能，GANC-CF方案与RSNC-CF方案性能整体优于RSNC-CF方案。随着中继数的增加，中继节点获取的信息全面，且可供选取的转发节点更多，GANC-CF方案与RSNC-CF方案通过计算选取更优转发节点。RSNC-CF方案在重传过程中，则可能会选择到提供可靠信息量较少的转发节点，使得重传次数和传输完成时间增加，从而造成平均吞吐量降低。

# 4 结束语

本文提出基于随机线性网络编码的动态规划调度方案。针对传统方案中存在的问题，本方案拓展了多中继协作传输网络场景，且优先调度能提供更多有效信息的节点。重传过程，从整体角度出发，将最小重传次数问题转换为求最短路径问题，得到最小重传次数的状态转移路径，进一步综合考虑能提供有效信息包数和链路可靠性高的转发节点进行信息的转发。在减少反馈次数的同时，提升单位时间接收节点能收到的有效信息量，减少重传次数。分析与仿真表明，DPNC-LF 能有效提升传输性能，具有高可靠性和高吞吐量，同时显著降低对反馈信息的依赖和减少反馈开销。特别在传输数据包足够大或者转发链路丢包差异比较大时，优势更加显著。

# 参考文献：

]Kee 1-6.   
[2]Hd   
[]ld (12): 5511-5524.   
[4]LiangngbineraaliCoopativeelarodcastaels[J]EEasofotioory5(3):998.   
[5]Lu Personal Indoor and Mobile Radio Communications.2011:1815-1819.   
[6]ai 63 (2): 674-687.   
[7]ChiW,Kosuestibcpeidrs Information Theory,2016,62(5):2493-2503.   
]L Proc of Wireless Communications and Networking Conference.2015,1548-1589.   
[9]Gouitb Communications Letter, 2016,20 (3): 434-437.   
[10]agosro Technology Conference.2016:1-5.   
[ Technology,2016,65 (10): 8739-8744.   
[2]DingLi University,2014,19(1): 59-64.   
[13]王练，梁申虎，彭代渊，等．多源多中继无线网络中基于随机线性网络编码的调度方案[J].电子与信息学报,2017,39(3):532（WangLian,Liang Shenhu， PengDaiuanosddelt technology,2017,39 (3):532)   
[4Do the IEEE Computer and Communications Societie.2005:1607-1617.