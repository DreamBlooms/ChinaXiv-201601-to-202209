# 通信网络中基于协作中继重传策略\*

徐光宪a，昝阳ʰ

(1.辽宁工程技术大学 a.电子与信息工程学院;b.研究生院，辽宁 葫芦岛 125105)

摘要：针对信息包在通信网络中多播传输进行了研究，提出通信网络中基于协作中继重传策略。当信息包直传失败时，源节点协作多个中继节点对多个丢失的信息包进行编码重传。在重传阶段根据反馈机制结果采取随机接入方式优先对有机会编码的丢失信息包进行组合，然后通过牺牲之前重传过程中传输失败的节点为信息提供空间分集增益，从而减低重传次数。最后在不同信道环境下，该策略与未协作NCARQ和传统ARQ进行MonteCarlo仿真。仿真结果表明，在多中继信道条件优于源-目的信道的情况下，利用协作网络编码进行重传有效地提高网络吞吐量，且该策略利用协作空间分集降低了由于相干性而导致性能不佳的状况。

关键词：通信网络；协作中继；重传；空间分集；吞吐量 中图分类号：TN914 doi:10.3969/j.issn.1001-3695.2017.07.0689

# Re-transmission strategy based on cooperative relay in communication networks

Xu Guangxiana, Zan Yangb (a.SchoolofElectrics&InformationEngineering,b.SchoolofGraduate StudiesLiaoningTechnicalUniversityHuludao Liaoning 125100,China ）

Abstract:This paper studiedthe information packets multicast incommunication networks,itproposed there-transmision strategybasedoncooperativerelay incommunicationnetworks(CRRS).When thepacketfails to transmit directly,theource node,coordinated with therelaying nodes can encodeandthenre-transmit lost packets.During re-transmision,those lost packets acessbletoencoding willassemblebywayofrandom access accordingtoteresults derivedfromthefedback system. Subsequently,there willprovide morespacialdiversitygainforinformationrestorationbyobsoleting thenodes previouslyfailed totransmitsoastoreducethefrequencyofthere-transmisson.Finally,troughdiverseinformationchanels,thisstrategycan simulate with non-coordinated NCARQand traditional ARQin Monte Carlo.The simulationresults have shownthat,on the conditionthat multiplerelaying channels providebeter conditions than source-destination channels,theuseofcoordinationbased network encoding forthe purposeofre-transmision would notonly effectively promote network throughput capability, but alsolargelyreduce the posibilities ofpoor performances duetocoherence issuesbywayofcoordinated spacial diversity. Key Words: communication networks; cooperative relay; retransmission; spacial diversity; throughput capability

# 0 引言

自动重复请求(ARQ)是通信网络中提高系统可靠性的一种差错控制机制[11。由于无线信道的衰落特性和高斯白噪声的干扰2，信息包在传输过程中可能存在丢包或者不能解码的现象。在这种情况下，ARQ性能可能会大幅度降低，同时吞吐量减少。为了解决这个问题，利用空间分集和对抗信道的相干性将协作方式融合到ARQ中。此策略中，覆盖区域中的中继节点监听信道并在传输阶段对任何成功解码的信息包进行队列缓冲，由于无线信道的广播特性[3]，没有产生额外带宽。当目的节点未能接收到来自源节点的信息包时，源节点将选择最优中继节点以最小化信道传输过程的中断概率和各个节点的功率为目标进行协作传输，降低信息包成功传输到目的节点的重传次数，有效地提高网络吞吐量，最大限度的改变了由中继节点带来的中断性能差问题[4]。

在多播传输过程中，重传包在源节点处仅通过单个节点编码，不增加额外的协作节点。在协作通信过程中，网络编码也可以应用于中继节点，这类方法称作协作网络编码[5]6]。早期提出的协作传输MAC协议如CoopMAC[7]、rDCF[8]和CD-MAC[9]等均是在传输过程中中继节点协作源节点进行发送信息包。Ding等人[10]提出一种在MSMR协作通信网络中低复杂度的策略，虽然有效的降低了复杂度但是忽略了中继节点过多产生的功率损耗问题。Duy等人[1提出了基于信噪比中继选择的混合译码放大转发方式研究，通过实验论证了提出方式的优势，但是存在一定的局限性。Huang[12]提出了中继协作无线广播传输的优化和启发式调度算法具有较低的频谱效率，尤其当中继节点未成功解码时会带来时频资源的空闲。Antonopoulos 等人[13]提出的方式是在确定性网络中协作MAC网络编码协议对能量效率的影响。Wang 等人[14]提出了在QoS约束下的PU与SU间的协作资源分配和功率控制策略。由上述问题可知，在协作传输过程中选择合理有效的协作方式是至关重要的。

本文提出通信网络中基于协作中继重传策略。该算法在多播通信网络中，信息包直传传输失败后，源节点将选取多个最优中继节点组成优化集合。当中断概率一定时，由信噪比的阈值判断中继节点的协作方式，此时可用节点使用反馈机制访问随机接入信道。在不同信道设置条件下，信道相干性被建模为有限状态马尔可夫过程，此时通过改变不同的参数来比较CRRS、NCARQ和传统ARQ算法的平均吞吐量。实验结果表明该协作中继重传策略可以有效提高多播网络的系统性能。

# 1 系统模型

假设在通信网络中的系统模型包含一个源节点 $s$ 、多个干扰节点 $P _ { \scriptscriptstyle { l } }$ 、多个目的节点 $D _ { _ n }$ 和多个中继节点 $R _ { \ * }$ ,其中中继节点协作源节点发送信息包。图1中箭头表示两个节点间信息包的传输方向，所有节点工作模式为半双工，时间被划分为多个时隙。通信信道被假定为平坦衰落信道且信道系数在单个传输周期内保持不变，但在周期之间相互独立变化。

![](images/97a57d633917cbedcbd4c210592bea7709e7c78912d6c11cb89ae279bd8fa6a2.jpg)  
图1协作广播网络

通信过程结构包括从源节点 $s$ 到目的节点 $D _ { i } ( i = 1 , 2 , 3 )$ 的N个子帧。每个子帧都有1个信息包作为负载在目的节点通过冗余校验码验证传输数据的完整性。在帧传输时，当源节点发送一个信息包到目的节点时，若此时目的节点成功解码，则目的节点反馈一个ACK信号，该信息包退出发送队列；若目的节点未能成功解码信息包，但是协作的中继节点成功解码，则中继节点收到该信息包同时向源节点发送ACK信号，该信息包退出发送队列；若目的节点和中继节点均没有成功解码，则信息包缓存在发送队列等待重传。假设每个信息包单次传输需要1个时隙。由于广播特性，ACK/NACK反馈的传输时间可以忽略不计。

假定信道 $h _ { _ x } ( k )$ 为马尔可夫链，每个 $h _ { _ x } ( k )$ 可以由有限状态数表示，可知链路 $S \ – R _ { \ k } \setminus R _ { k } \ – D _ { \ n } \setminus S \ – D _ { n } \setminus S \ – P _ { l } \setminus R _ { k } \ – P _ { l }$ 的信道系数可以表示为 $h _ { _ { s , r } } \setminus h _ { _ { r , d } } \setminus h _ { _ { s , d } } \setminus h _ { _ { s , p } } \setminus h _ { _ { r , p } }$ ，其相应的信道增益为$| h _ { \scriptscriptstyle s , r } | ^ { \scriptscriptstyle 2 } \cdot | h _ { \scriptscriptstyle r , d } | ^ { \scriptscriptstyle 2 } \cdot | h _ { \scriptscriptstyle s , d } | ^ { \scriptscriptstyle 2 } \cdot | h _ { \scriptscriptstyle s , p } | ^ { \scriptscriptstyle 2 } \cdot | h _ { \scriptscriptstyle r , p } | ^ { \scriptscriptstyle 2 } \circ P _ { \scriptscriptstyle s } , P _ { \scriptscriptstyle k }$ 是源节点和目的节点的发送信息包功率；w是额外的高斯噪声，其功率为σ。

$$
P _ { \it  s } = \operatorname* { m i n } ( P ^ { \operatorname* { m a x } } , \frac { R _ { \it 0 } } { \operatorname* { m a x } _ { \imath = 1 , 2 , \ldots L } \mid h _ { \it s , p } \mid ^ { 2 } } )
$$

$$
P _ { r } = \operatorname* { m i n } ( P ^ { \mathrm { m a x } } , \frac { R _ { \mathrm { 0 } } } { \operatorname* { m a x } _ { \scriptscriptstyle { l = 1 , 2 , \ldots L } } \big | h _ { \scriptscriptstyle { r , p } } \big | ^ { 2 } } )
$$

$P ^ { \operatorname* { m a x } }$ 表示源节点和目的节点的发送信息包功率最大值， $R _ { \mathrm { o } }$ 为干扰阈值。假设在第 $\mathbf { k }$ 时隙源节点 $s$ 发送信息包 $\mathit { \Pi } _ { \overline { { x } } }$ ,目的节点和中继节点可能收到的信号表示为

$$
y _ { s , d } ( k ) = \sqrt { p _ { s } } h _ { s , d } \overline { { x } } + w _ { d }
$$

$$
y _ { s , r } ( k ) = \sqrt { p _ { s } } h _ { s , r } \overline { { x } } + w _ { r }
$$

在第一帧传输完成后，其中单个子帧可能在目的节点发生信息包传输失败的情况。如果信息包不能正确解码，那么中继节点协作丢失信息包进行重传。此时目的节点可能收到的信号表示为

$$
y _ { r , d } ( k ) = h _ { _ { r , d } } \varpi ( y _ { _ { s , r } } ) + w _ { _ { d } } ^ { ^ { \prime } }
$$

其中： $\varpi ( y _ { s , r } )$ 表示中继节点的协作方式， $S { \ – R _ { k } } \setminus R _ { \ k } { - } D _ { \ n } \qquad $ （${ \mathbf { } } S { \mathbf { - } } D _ { \mathbf { \eta } _ { n } }$ 的瞬时接收信噪比为

$$
\mu _ { _ { S , r } } = \frac { \mid h _ { _ { S , r } } \mid ^ { 2 } P _ { _ { S } } } { \sigma _ { _ { 0 } } ^ { 2 } } = \operatorname* { m i n } ( \mu _ { _ { p } } , \frac { \mu _ { _ { I } } } { \operatorname* { m a x } _ { _ { _ { l = 1 , 2 , . . . L } } } \mid h _ { _ { s , r } } \mid ^ { 2 } } ) \mid h _ { _ { s , r } } | ^ { 2 }
$$

$$
\mu _ { s , d } = \frac { \mid h _ { s , d } \mid ^ { 2 } P _ { s } } { \sigma _ { \circ } ^ { 2 } } = \operatorname* { m i n } ( \mu _ { , } , \frac { \mu _ { \iota } } { \operatorname* { m a x } _ { \iota = 1 , 2 \ldots L } \mid h _ { s , r } \mid ^ { 2 } } ) \mid h _ { s , d } \mid ^ { 2 }
$$

$$
\mu _ { r , d } = \frac { \mid h _ { r , d } \mid ^ { 2 } P _ { \varepsilon } } { \sigma _ { \circ } ^ { 2 } } = \operatorname* { m i n } ( \mu _ { \rho } , \frac { \mu _ { r } } { \operatorname* { m a x } _ { \scriptscriptstyle { l = 1 , 2 , \ldots } } \mid h _ { r , d } \mid ^ { 2 } } ) \mid h _ { r , d } \mid ^ { 2 }
$$

其中： $\mu _ { _ { p } } \cong \frac { P _ { _ { \mathrm { m a x } } } } { \sigma _ { _ { 0 } } ^ { ^ 2 } } ~ , ~ \mu _ { _ { I } } \cong \frac { R _ { _ { 0 } } } { \sigma _ { _ { 0 } } ^ { ^ 2 } }$

# 2 CRRS 算法

# 2.1 CRRS 策略实现机制描述

在新一周期的网络传输阶段，源节点 $s$ 发送一帧到目的节点 $D _ { \mathfrak { n } }$ ，如果在帧持续时间（N个连续信息包的持续时间）中不存在源-目的信道的中断状态，则目的节点成功地接收帧，同时完成一个周期的传输。当一个周期的传输完成后，下一个周期开始进行传输时，如果帧中的任何一个信息包没有被任何目的节点接收，则进入重传阶段，在重传阶段将持续到帧中的所有信息包被目的节点接收结束。在重传阶段时，如果中继节点可以正确解码至少一个信息包或丢失结合包，它将协作源节点重传。

在重传阶段没有信号节点的中心控制，由于目的节点的

ACK/NACK反馈，重传阶段将包含中继节点。随机接入机制用来选择重传节点，在重传开始阶段，存在一个竞争时间，此时所有节点均试图通过信道重传信息包，每个候选节点尝试从计时器值向下计数后重传信息包，其中随机计时器值由有限集(0.1.,..W)构成。在第i次重传中， $W _ { _ i }$ 被称作反馈窗口。反馈窗□对于所有节点在第一次重传过程中初值设置为 $W _ { \mathrm { m i n } }$ 。在重传失败的情况下，扩大反馈窗口是一种惩罚机制。下面是造成重传失败的两种情况：

a)当源节点和中继节点同时试图通过信道时发生碰撞;  
b)一个重传节点发送由于信道中断丢失的信息包。

在第一种情况下，重传节点的反馈窗口引发的碰撞扩大 2倍，即 $W _ { \scriptscriptstyle i } \to 2 W _ { \scriptscriptstyle i }$ 。在第二种情况下，一个重传节点通过信道时由于信道中断，导致重传信息包丢失。在这种情况下，反馈窗□被扩大2倍。另外还存在一个导致反馈窗口增加的实例。候选重传节点没有机会使用网络编码结合丢失信息包且放弃自身的同时给其他节点机会去执行网络编码操作，这种情况下，候选节点也以2倍的速度扩大反馈窗口，即 $W _ { \scriptscriptstyle i } \to 2 W _ { \scriptscriptstyle i }$ 。对于以上情况来说，反馈窗口直到达到自身的最大值时被扩大： $W _ { \mathrm { m a x } }$ 。

考虑一个带有1个源节点，2个中继节点，3个目的节点，2 个干扰节点的模型。此时信息包状态矩阵 $\boldsymbol { S } _ { \boldsymbol { d } }$ 表示在第 $k$ 时隙结束时，目的节点接收信息包成功或失败的状态。矩阵 $\boldsymbol { S } _ { \boldsymbol { d } }$ 有3行N列，其中每一行表示目的节点接收相应信息包的状态。如：矩阵 $S _ { \scriptscriptstyle d } ( k )$ 的元素 $( i , j )$ 表示目的节点 $D _ { _ i }$ 接收信息包 $q _ { j }$ 的状态,其中 ${ } ^ { \mathfrak { a } } 0 ^ { \mathfrak { , } }$ 表示失败、“1”表示成功。信息包成功/失败状态取决于在该特定时隙中信息包传输的信道是否处于良好状态。矩阵$S _ { \scriptscriptstyle d } ( k )$ 由每个候选重传节点构成（源节点和可用中继节点)。每个候选重传节点根据 ${ \cal S } _ { d } ( k )$ 确定信息包是否正确接收。候选重传节点选择自身信息包重传时，需考虑所有目的节点对可能选择的信息包。因此， $S _ { \scriptscriptstyle d } ( k )$ 的子矩阵被认为与相应的目的节点对相关。根据上述描述的规则搜索这些子矩阵中可能重传的信息包，每个中继节点根据从终端的ACK/NACK反馈获得的信噪比选择目的节点。对于每个中继节点，选择两个带有高信噪比的目的节点，由此可能形成一种考虑所有目的节点共同去确定可能重传信息包的方式，其算法的流程图如图2所示。

# 2.2候选转发节点传输选取

给出矩阵 $S _ { \scriptscriptstyle d } ( k )$ ,对于每个可能的 $i j$ 对，由包含的节点形成$S _ { \scriptscriptstyle d , i j } ( k )$ 矩阵。其目的是让矩阵 $S _ { \scriptscriptstyle d , i j } ( k )$ 中尽可能多的 ${ } ^ { \mathfrak { a } } 0 ^ { \mathfrak { , } }$ 转换为的“1”。为此，在矩阵 $S _ { { \scriptscriptstyle d } , i j } ( k )$ 查找全零对角线和列。全零列表示一个公共信息包 $q _ { _ p }$ 没有被任何目的节点接收；全零对角线代表两个不同的信息包 $q _ { m } , q _ { n } , q _ { m }$ 被目的节点 $D _ { _ i }$ 接收但未被 $D _ { j }$ 接收, $q _ { n }$ 信息包恰好相反。第一种情况下公共信息包 $q _ { \mathnormal { p } }$ 选择重传，第二种情况选择网络编码包 $q _ { \scriptscriptstyle m } \oplus q _ { \scriptscriptstyle n }$ 进行重传。如果存在至少一个信息包满足上述条件，那么选择是随机进行的。另外，如果不存在这类信息包，则选择单行子矩阵 ${ \cal S } _ { d } ( k )$ 中带有最高信噪比的目的节点。正如以上叙述，候选重传节点通过扩大反馈窗□而惩罚自身。

![](images/23bea9686730870d36fe2b728b4210471b93a2306db94719c5c8be38cc4ad563.jpg)  
图2算法流程图

# 2.3 协作传输方式

这个选择将基于目的节点优先原则。对于每个中继节点，目的节点均优先。这将通过检测中继节点和目的节点之间信道的信噪比，并选择具有最高信噪比的两个目的节点。对于此策略或者说意味着在一段时间内对信噪比的测量，或者利用目的节点的最后接收的ACK/NACK反馈测量的瞬时信噪比。给定最优目的节点，对于被选取的目的节点采取纠正编码包的操作。在第一次传输过程中，没有正确接收某些信息包的中继节点可能在重传阶段正确接收。假设这种情况发生，中继节点将会在相应矩阵 $S _ { \scriptscriptstyle d } ( k )$ 中更新 $\mathrm { \Delta _ { X } }$ 。成功解码的中继节点下标集合f={𝑘|μ,≥μ}，μ'=2-1表示目的节点成功解码信噪比的阈值。根据目的节点的接收情况相应选择中继节点进行协作传输，其选择过程如下：

a)源节点 $s$ 通过计数器统计中继节点或者目的节点成功解码信息包的数量，源节点发送信息包到目的节点，如果传输失败，但此时中继节点成功接收信息包且成功解码，则向源节点$s$ 反馈信息接收状态，此时计数器加1操作，若失败，计数器不做任何操作。

b)传输k个子帧后，如果计数器显示为0，表示所有中继节点解码失败，即 $\pounds = \emptyset$ 。然后源节点 $s$ 在第 $\mathbf { k } { + } \mathbf { l }$ 个子帧时发送解码信号，同时停止子帧 $\mathbf { k } { + } \mathbf { l }$ 之后的全部子帧及中继阶段的传输过程，开始新一周期的多播发送，目的节点及中继节点试图成功解码前一阶段接收的信息包，若源-目的信道的信噪比μ ≥μ'，则目的或者中继节点可成功解码信息包。

c)如果计数器显示不为0，表示部分中继节点解码成功，即（204号 $\pounds \neq \emptyset$ 。源节点 $s$ 在第 $\mathbf { k } { + } \mathbf { l }$ 个子帧时发送中继选择信号，此时中继节点根据目的节点的信息状态反馈，目的节点由源节点直传时收到的源-目的的信道功率和其中包含的噪声功率，计算得到信噪比μs.d

d)在下一时隙时，目的节点根据接收到源节点信息包状态向模型中中继节点反馈 $S { - } D _ { _ n }$ 信道的信噪比 $\mu _ { s , d } ^ { \quad \prime }$ ，此时中继节点解码成功的信息包下标存储在 $R _ { \boldsymbol { k } } \in \Sigma$ ，最后中继节点根据接收的反馈计算出链路 $R _ { \ * } { - } D _ { \ * }$ 的信道增益值 $\mid h _ { { } _ { r , d } } ^ { \mathrm { ~ ~ } \mathrm { ~ } ^ { \mathrm { ~ } } } \mid ^ { 2 }$ ，并由(10)计算其相应的信噪比 $\mu _ { r , d }$ 。为了表示方便，将 $\Im \cong \left\{ 1 , 2 , . . . N \right\}$ ，$\Re \cong \left\{ 1 , 2 , . . . K \right\}$ ， $\aleph \cong \left\{ 1 , 2 , . . . L \right\}$ ，此时子帧中成功解码的中继节点$R _ { \iota } ( k \in \mathfrak { L } )$ 的初值设置为

$$
\Psi _ { _ { k } } = t _ { 0 } \exp \left( - \left[ \operatorname* { m i n } _ { d \in \Im } \left[ \operatorname* { m a x } \left( \mu _ { _ { s , d } } , \mu _ { _ { r , d } } \right) \right] \right] \right)
$$

其中

$$
k ^ { * } = \arg \operatorname* { m a x } _ { k \in \mathfrak { X } } \left( \operatorname* { m i n } _ { d \in \mathfrak { I } } \Bigl [ \operatorname* { m a x } ( \mu _ { s , d } , \mu _ { r , d } ) \Bigr ] \right)
$$

若中继节点 $k ^ { * }$ 满足上式时，首要将其计时器设置为0值，由选择的最优中继进行信息传输，同时剩余成功解码的中继节点的计数器值保持不变状态，与源节点 $s$ 在最优中继的传输时不进行任何操作。

# 3 性能分析

# 3.1信道转移概率

假定在衰落信道中，每个信息包的持续时间保持不变且两者之间的持续传输仅略微浮动。利用有限状态马尔可夫模型分析信道相干性对 ARQ吞吐量性能的影响。其中定义 $T _ { \rho } = M T _ { s }$ 为信息包持续时间， $T _ { s }$ 表示信号持续时间， $T _ { c }$ 表示相干时间参数。信道模型通过两个信道状态来描述，其中差状态A表示信道中断造成的信息包丢失，好状态B代表成功传输。马尔可夫链具有以下转移概率矩阵：

$$
\dot { U } { = } \left[ \begin{array} { l l } { W _ { _ { A B } } } & { W _ { _ { A B } } } \\ { W _ { _ { B A } } } & { W _ { _ { B B } } } \end{array} \right]
$$

$W _ { _ { i j } }$ 表示在第 $\mathbf { k }$ 时隙是i状态、第 $\mathbf { k } { + } \mathbf { l }$ 时隙是j状态的概率,对于循环对称复高斯分布的信道转移概率的过程如下

$$
W _ { A B } = \frac { Q ( \theta , \rho \theta ) - Q ( \rho \theta , \theta ) } { P _ { o \nu e r } }
$$

$$
W _ { _ { B A } } = \frac { P _ { _ { o v e r } } W _ { _ { A B } } } { 1 - P _ { _ { o v e r } } }
$$

其中:参数 $\theta { = } \sqrt { \frac { 2 \mu } { 1 { - } \rho ^ { 2 } } } , \mu$ 表示信道的信噪比： $\scriptstyle \rho = Z _ { _ 0 } ( 2 \pi f _ { _ m } T _ { p } )$ 表示持续传输信道相干系数； $f _ { _ m }$ 表示Doppler 频率； $Z _ { _ { 0 } }$ 表示第一类零阶的Bessel函数； $\boldsymbol { \mathscr { Q } }$ 表示 MarcumQ函数。

# 3.2 两种接入方式

a)随机接入。如果在进行传输过程中源节点和中继节点没有正交时隙分发，那么源节点和中继节点采用随机方式接入信道。在发送的过程中存在源节点和中继节点同时向目的节点发送信息包的情况，这种情况本文定义为信息包碰撞且发送的信息包不能成功解码，因此信息包传输失败。此时传输队列的吞吐量区间取值为

$$
\Xi = \left\{ \left( \vartheta _ { s } , \vartheta _ { r } \right) \left( \sqrt { \frac { \left( 1 - B _ { s , d } \right) \vartheta _ { s } B _ { s , r } } { B _ { r , d } \left( B _ { s , r } + B _ { s , d } - B _ { s , r } B _ { s , d } \right) } + \frac { \vartheta _ { r } } { B _ { r , d } } } + \right) \right. \sqrt { \left. \frac { \left( 1 - B _ { s , d } \right) \vartheta _ { s } B _ { s , r } } { B _ { s , r } + B _ { s , d } } + 1 \right| }
$$

其中: $\mathcal { A } _ { s }$ 和 $\vartheta _ { _ { r } }$ 表示源节点和中继节点的信息包传输速率， $B _ { { } _ { s , r } }$ 、$B _ { s , d }$ 和 $B _ { r , d }$ 表示源-中继、源-目的、中继-目的信道的信息包成功发送率。

b)正交接入。源节点和中继节点以正交的方式接入信道，此时传输队列的吞吐量区间取值为

$$
\Xi = \{ ( { \vartheta _ { s } , \vartheta _ { r } } ) | \frac { { ( { B _ { s , r } + B _ { r , d } - B _ { s , r } B _ { s , d } } ) \vartheta _ { s } } } { { B _ { r , d } ( B _ { s , r } + B _ { s , d } - B _ { s , r } B _ { s , d } ) } } + \frac { \vartheta _ { r } } { { B _ { r , d } } } < 1 \}
$$

若传输过程中信息包的到达率在吞吐量区间取值范围内，则通信过程中所有传输队列呈稳定状态。

# 3.3中继节点协作的中断概率

对于Rayleigh衰落信道，如果存在强持续的信道编码，信息包的误码率可以近似认为是交互信息的中断概率，每个时隙的时间长度 $t _ { \scriptscriptstyle 0 }$ ，在这种情况下所需的比特率是 $R _ { _ b }$ bit 丨 symbol 。其中 $F _ { _ { s , d } } = \frac { \overline { { \mu } } _ { s , d } } { \mu ^ { \prime } } \vdots F _ { s , d }$ 表示中断发生前信道允许低于平均值的量,称作信道衰落边缘量。目的节点的接收信噪比为

$$
\Gamma _ { _ d } = \left\{ \begin{array} { l } { \mu _ { _ s , d } } & { \mathbf { \Delta } \mathbf { \mathscr { t } } = \boldsymbol { \otimes } } \\ { \operatorname* { m a x } ( \mu _ { _ s , d } , \mu _ { _ { \boldsymbol { k } ^ { \cdot } , d } } ) \ \mathbf { \Delta } \mathbf { \mathscr { k } } \neq \boldsymbol { \otimes } } \end{array} \right.
$$

当 $\Gamma _ { \it d } < \mu ^ { \prime }$ 时，目的节点 $D _ { _ n }$ 解码失败，其中断概率为

$$
\begin{array} { r l } & { P _ { o u r } = \mathrm { P r } \Big ( \underset { d \in \Im } { \mathrm { m i n } } \Gamma _ { d } < \mu ^ { \prime } \Big ) { = } \mathrm { P r } \Bigg ( \underset { d \in \Im } { \mathrm { m i n } } \mu _ { s , d } < \mu ^ { \prime } , \pounds = \emptyset \Bigg ) } \\ & { \quad \quad \quad + \mathrm { P r } \Big ( \underset { d \in \Im } { \mathrm { m i n } } \Big [ \underset { d \in \Im } { \mathrm { m a x } } \Big ( \mu _ { s , d } , \mu _ { \iota \cdot , d } \Big ) \Big ] < \mu ^ { \prime } , \pounds \neq \emptyset \Big ) } \end{array}
$$

因此中继节点成功解码的情况下，中断概率定义为

$$
\begin{array} { l } { { \displaystyle P _ { o v e r } = \mathrm { P r } \Big ( \operatorname* { m i n } _ { i \in \mathfrak { I } } \mu _ { s , d } < \mu ^ { \prime } , \pounds = \emptyset \Big ) + \sum _ { m = 1 } ^ { K } \sum _ { ( k _ { 1 } , k _ { 2 } \ldots k _ { m } \subset \mathfrak { R } ) } } } \\ { { \displaystyle + \mathrm { P r } \Big ( \operatorname* { m a x } _ { k \in \mathfrak { L } } \Big ( \operatorname* { m i n } _ { d \in \mathfrak { I } } \Big [ \operatorname* { m a x } \big ( \mu _ { s , d } , \mu _ { r , d } \big ) \Big ] < \mu ^ { \prime } , S = \big \{ k _ { 1 } , k _ { 2 } \ldots k _ { m } \big \} \Big ) \Big ) } }  \end{array}
$$

令

$$
\wp ( \emptyset ) = \operatorname* { P r } \left( \operatorname* { m i n } _ { d \in \Im } \mu _ { s , d } < \mu ^ { \prime } , \pounds = \emptyset \right)
$$

$$
\begin{array} { l } { \displaystyle \{ \theta ( \{ \mathbf { k } _ { \scriptscriptstyle { 1 } } , \mathbf { k } _ { \scriptscriptstyle { 2 } } \ldots \mathbf { k } _ { \scriptscriptstyle { m } } \} ) } \\ { \displaystyle = \operatorname* { P r } \biggl ( \operatorname* { m a x } _ { \scriptscriptstyle { k \in \boldsymbol { \xi } } } \Bigl ( \operatorname* { m i n } _ { \scriptscriptstyle { d \in \Im } } \Bigl [ \operatorname* { m a x } \left( \mu _ { s , d } , \mu _ { r , d } \right) \Bigr ] < \mu ^ { \prime } , \pounds = \left\{ k _ { \scriptscriptstyle { 1 } } , k _ { \scriptscriptstyle { 2 } } \ldots k _ { \scriptscriptstyle { m } } \right\} \biggr ) \biggr ) } \end{array}
$$

得出 $\wp ( \emptyset )$ 和 $\wp ( \{ \mathbf { k } _ { 1 } , \mathbf { k } _ { 2 } . . . \mathbf { k } _ { \mathrm { m } } \} )$ 的条件概率的积分为

$$
\begin{array} { c } { { \wp ( \emptyset ) { = } { \int _ { \circ } ^ { \infty } } \biggl ( \underset { { d \in \Im } } { \operatorname* { m i n } } \biggl [ \operatorname* { m i n } ( \mu _ { _ { p } } , \frac { \mu _ { _ { I } } } { x } ) \mid h _ { _ { s , d } } \mid ^ { 2 } \biggr ] { < } \mu ^ { \prime } \biggr ) } } \\ { { \times \operatorname* { P r } \bigl ( \pounds _ { \mathbf { \Psi } } = \emptyset \mid x \bigr ) P _ { { x } } ( x ) d x } } \end{array}
$$

$$
\begin{array} { r l } & { \wp ( \{ \mathbf { k } _ { 1 } , \mathbf { k } _ { 2 } . . . \mathbf { k } _ { \mathrm { m } } \} ) } \\ & { = \displaystyle \int _ { 0 } ^ { \infty } \operatorname* { P r } \left( \operatorname* { m a x } _ { k \in \mathbb { S } } \left( \operatorname* { m i n } _ { d \in \mathbb { S } } \left[ \operatorname* { m a x } \left[ \operatorname* { m i n } ( \mu _ { p } , \frac { \mu _ { r } } { x } ) | \ : h _ { s , d } | ^ { 2 } , \ : \mu _ { r , d } \right] \right] \right) < \mu ^ { \prime } \right) } \\ & { \quad \times \operatorname* { P r } \left( \pounds \in \left\{ k _ { 1 } , k _ { 2 } . . . k _ { m } \right\} | x \right) P _ { x } ( x ) d x } \end{array}
$$

可知 $P _ { x } ( x )$ 为随机变量 $\mathrm { \Delta } \mathrm { X }$ 的概率密度函数，得分布函数为

$$
{ \begin{array} { r l } & { F _ { x } ( x ) = \operatorname* { P r } \left( X = \operatorname* { m a x } \left| h _ { , \ \varepsilon , \varepsilon } \right| < x \right) } \\ & { \qquad = \prod _ { i \neq s } \operatorname* { P r } \left( \left| h _ { , \ \varepsilon , \varepsilon } \right| ^ { 2 } < x \right) } \\ & { \qquad = \prod _ { i \neq s } \left[ 1 - \exp \left( - { \frac { x } { \Omega _ { , , \varepsilon , \varepsilon } } } \right) \right] } \\ & { \qquad = 1 + \sum _ { s = 1 } ^ { L } \sum _ { \varepsilon , \varepsilon , \varepsilon , \varepsilon , \in \mathbb { N } } \left( - { \frac { \displaystyle x } { \displaystyle \sum _ { j \neq s } \frac { x } { \Omega _ { , , \varepsilon , \varepsilon } } } } \right) } \end{array} }
$$

其中 $\mu ( y _ { \boldsymbol { \imath } } ) \equiv \operatorname* { m i n } ( \mu _ { \boldsymbol { \jmath } } , \frac { \mu _ { \boldsymbol { \imath } } } { y _ { \boldsymbol { \imath } } } )$ ，由此本文可知随机变量 Y 的概率密度函数为

$$
P _ { { { r } _ { k } } } ( y _ { { { k } } } ) = \sum _ { \nu _ { k } = 1 } ^ { L } \sum _ { { { l } _ { 1 } } , { { l } _ { 2 } } \ldots { { l } _ { \nu _ { k } } } \subset \aleph } ( - 1 ) ^ { { { \nu } _ { k } } + 1 } U ^ { \scriptscriptstyle { { { \nu } _ { P } } } } \exp ( - U ^ { \scriptscriptstyle { { { \cal R } } _ { P } } } y _ { \lambda } )
$$

人 $U ^ { ^ { R P } } \cong \sum _ { j = 1 } ^ { \nu _ { k } } \frac { 1 } { \Omega _ { \nu , p _ { j } } }$ ，将式(28)代入式(27)得

$$
\mathcal { G } _ { _ { i , n _ { 1 } \cdots n _ { q } } } = 1 - \sum _ { \nu _ { k i } = 1 } ^ { L } \sum _ { l _ { 1 } , l _ { 2 } \cdots l _ { \nu _ { k i } } \subset \mathbb { N } } ( - 1 ) ^ { \nu _ { k } + 1 } \xi ( U ^ { \scriptscriptstyle ^ { R P } } , \mu ^ { \prime } U ^ { \scriptscriptstyle ^ { R D } } )
$$

其中 $U _ { { \scriptscriptstyle i , q } } ^ { \scriptscriptstyle R D } = \sum _ { { \scriptscriptstyle r = 1 } } ^ { q } \frac { 1 } { \Omega _ { { \scriptscriptstyle r , d } _ { r } } }$ ，此外，变量 $\textit { \textbf { \textsf { k } } } _ { d }$ 服从指数分布，其概率密度为

其中 $U ^ { s P } \cong \sum _ { j = 1 } ^ { u } \frac { 1 } { \Omega _ { s , p _ { j } } }$ ,对(23)求导，得到

$$
P _ { _ { X } } ( x ) { = } { \sum _ { u = 1 } ^ { L } } \sum _ { l _ { 1 } , l _ { 2 } \ldots l _ { u } { \in } \mathbb { N } } \left( - 1 \right) ^ { u + 1 } U ^ { ^ { _ { S P } } } \exp \left( { - U ^ { ^ { S P } } } x \right)
$$

将(24）代入(21)得

$$
\begin{array} { r l } & { \kappa ( 2 ) \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { k } \left( \kappa ( \frac { 1 } { n } ) \left[ \hat { a } ( x ) \hat { b } _ { i } \right] \right) ^ { \top } \hat { \omega } \varepsilon ^ { \prime } \Big \} } \\ & { \quad \times \exp \left\{ \underset { i = 1 } { \overset { n + 1 } { \prod } } \left( \varepsilon ( x ) \hat { b } _ { i } \varepsilon \right) \right\} = \int _ { 0 } ^ { \infty } \sum _ { i = 1 } ^ { k } \left( - \nu \right) ^ { 1 / k } \hat { \omega } \varepsilon ^ { \prime } \exp \left\{ \hat { \mathcal { M } } ^ { \star } x \right\} d x } \\ & { \quad - \displaystyle \sum _ { j = 1 } ^ { k } \sum _ { i = 1 } ^ { k } \left( - \nu \right) ^ { 1 / k } \sum _ { j = 1 } ^ { k } \Bigg \| \mathrm { L } \big \| \hat { a } ( x ) \hat { a } _ { i } \left\| _ { \mathcal { M } } \left\{ \hat { \mathcal { M } } ^ { \star } x \right\} \right) } \\ & { \quad \times \displaystyle \sum _ { j = 1 } ^ { k } \left( \mathrm { L } \big | \hat { a } ( x ) \hat { b } _ { i } \big | _ { \mathcal { M } } \int _ { 0 } ^ { x } \hat { \mathcal { M } } \varepsilon ^ { \prime } \big \} \right) \exp \left( - \nu \right) d x } \\ & { \quad - \displaystyle \sum _ { j = 1 } ^ { k } \sum _ { i = 1 } ^ { k } \left( - \nu \right) ^ { 1 / k } \sum _ { j = 1 } ^ { k } \left( - \frac { \hat { \mathcal { M } } \varepsilon } { \hat { \mathcal { M } } ^ { \star } x } \right) \Bigg \| } \\ & { \quad \quad \times \displaystyle \sum _ { j = 1 } ^ { k } \sum _ { i = 1 } ^ { k } \sum _ { j = 1 } ^ { k } \left( - \nu \right) ^ { 1 / k } \sum _ { j = 1 } ^ { k } \left( - \nu \right) ^ { 1 / k } \sum _ { i = 1 } ^ { k } \nu \left( - \nu ^ { \prime } x ^ { \prime } \right) \right) \Delta x \left( \hat { \mathcal { M } } \varepsilon ^ { \prime } \right) \Delta x \left( \hat { \mathcal { M } } \varepsilon \right) } \\ & { \quad \quad - \displaystyle \sum _ { j = 1 } ^ { k } \sum _ { i = 1 } ^ { k } \sum _ { j = 1 } ^ { k } \nu \int _ { 0 } ^ { x } \exp \left\{ \frac { \hat { \mathcal { M } } ^ { \star } x ^ { \prime } } { \hat { \mathcal { M } } ^ { \star } x ^ { \prime } } \right\} \times } \\ &  \quad \times \displaystyle \sum _ { j = 1 } ^ { k } \sum _ { j = 1 } ^ { k } \nu \displaystyle \sum _ { j = 1 } ^ { k } \left( \hat { \mathcal { M } } \end{array}
$$

其中令 $\mu ( x ) \cong \operatorname * { m i n } ( \mu _ { _ { p } } , \frac { \mu _ { _ { I } } } { x } ) \ ; U ^ { s o } \cong \sum _ { d \in \Im } \frac { 1 } { \Omega _ { _ { s , d } } } ; U ^ { s s } \cong \sum _ { i = 1 } ^ { p } \frac { 1 } { \Omega _ { _ { s , r _ { i } } } } \ ;$ （204号

$$
\xi ( \alpha , \beta ) \cong \exp \left( - \frac { \beta } { \mu _ { p } } \right) - \frac { \frac { \beta } { \mu _ { r } } } { \alpha + \displaystyle \frac { \beta } { \mu _ { r } } } \exp \left( - \frac { \beta + \alpha \mu _ { r } } { \mu _ { p } } \right)
$$

设 $\nmid \boldsymbol { \mathscr { E } } _ { \textit { d } _ { d } } = \mid h _ { _ { s , d } } \mid ^ { 2 }$ ，则存在

$$
\begin{array} { r l } & { \mathrm { P r } \Bigg ( \underset { \mathrm { i } \infty \times \pm } { \operatorname* { m a x } } \Bigg ( \underset { \mathrm { d } ^ { ( \alpha ) } } { \operatorname* { m i n } } \Bigg [ \operatorname* { m a x } \Bigg [ \operatorname* { m i n } ( \mu _ { v } , \frac { \mu _ { i } } { \lambda } ) \boldsymbol { \mathscr { E } } _ { \lambda } , \ \mu _ { v , \lambda } \Bigg ] \Bigg ] \Bigg ) < \mu ^ { \prime } \Bigg ) } \\ & { = \underset { \mathrm { c } ^ { - 1 } \neq \lambda } { \overset { N } { \sum } } \underset { \mathrm { i } \neq \infty } { \sum } \underset { \mathrm { p } ^ { \prime } \neq \infty } { \sum } \underset { \mathrm { p } ^ { \prime } \neq \infty } { \sum } \Bigg [ \underset { \mathrm { i } \neq \infty } { \sum } \int _ { \mu ( v ) } ^ { \mu ^ { \prime } } \int _ { 0 } ^ { \mu \alpha } \cdots \Bigg ] \underset { \mathrm { f } ^ { \prime } = \lambda } { \overset { \mu ^ { \prime } } { \sum } } } \\ & { \times \Bigg [ \underset { \mathrm { i } \neq 1 } { \overset { N } { \prod } } \int _ { 0 } ^ { \infty } \mathrm { P r } \Bigg ( \underset { \mathrm { i } \neq 1 } { \\operatorname* { m i n } } \left| \boldsymbol { h } _ { v , u _ { \lambda } } \right| < \frac { \mu ^ { \prime } } { \mu ( v _ { \lambda } ) } \Bigg ) f Y _ { v } ( y _ { v } ) d y _ { v } \Bigg ] } \\ & { \times \underset { \mathrm { d } ^ { - 1 } } { \overset { N } { \prod } } f _ { z _ { i } } ( z _ { i } ) d z _ { z _ { i } } \cdots d z _ { z _ { i } } d z _ { z _ { i } } \cdots d z _ { z _ { i } , n } d z _ { z _ { i } + 1 } \cdots d z _ { z _ { i } + 1 } . } \end{array}
$$

$$
P _ {  { \varepsilon } _ { d } } ( z _ { d } ) = \frac { 1 } { \Omega _ { s , d } } \exp ( - \frac { z _ { d } } { \Omega _ { s , d } } )
$$

将式(29)和(30)代入式(27)中可得

$$
\begin{array} { r l } & { \mathrm { P r } \Bigg ( \underset { k \in \mathcal { E } } { \operatorname* { m a x } } \left( \underset { d \in \mathcal { S } } { \operatorname* { m i n } } \Bigg [ \operatorname* { m a x } \{ \operatorname* { m a x } \right]} \{ \operatorname* { m a x } \{ \operatorname* { m i n } ( \mu _ { \nu } , \frac { \mu _ { l } } { x } ) \notin \ , \ \mu _ { r , d } \} \}  \Bigg ) < \mu ^ { \prime } \Bigg )  \\ & { = \underset { q = 1 } { \overset { N } { \sum } } \underset { n _ { 1 } , n _ { 2 } , n _ { \varepsilon } \leq 3 } { \sum } \underset { i = 1 } { \overset { n } { \prod } } { \mathcal { I } } _ { i , n _ { 1 } , . . . , n _ { i } } \prod _ { t = 0 } ^ { q } \underset { ( n _ { 1 } , n _ { 2 } , . . . n _ { i } ) \leq ( n _ { 1 } , n _ { 2 } , . . . n _ { i } ) } { \sum } ( - 1 ) ^ { t } } \\ & { \times \exp \Bigg ( \frac { \mu ^ { \prime } } { \mu ( x ) } \big ( U _ { \varepsilon } ^ { s D } + U _ { \scriptscriptstyle { N - q } } ^ { s D } \big ) \Bigg ) } \end{array}
$$

其中： $U _ { _ t } ^ { s o } \cong \sum _ { { \boldsymbol { w } } = 1 } ^ { t } \frac { 1 } { \Omega _ { _ s , d _ { \boldsymbol { w } } } }$ ， ${ U _ { { \scriptscriptstyle N } - q } ^ { { \scriptscriptstyle S D } } } \cong \sum _ { \substack { n = 1 , n \ne n _ { 1 } , n _ { 2 } \ldots n _ { q } } } ^ { N } \frac { 1 } { \Omega _ { { \scriptscriptstyle s } , d } }$ 。此时令成功解码的中继下标集合 $\mathbf { \mathcal { L } = } \{ \mathbf { k } _ { \mathrm { _ 1 } } , \mathbf { k } _ { \mathrm { _ 2 } } . . . \mathbf { k } _ { \mathrm { _ m } } \}$ ，其条件概率如下：

$$
\begin{array} { l } { { \displaystyle \operatorname* { P r } \Big ( \pounds = \big \{ k _ { 1 } , k _ { 2 } \ldots k _ { m } \big \} \vert x \Big ) } \ ~ } \\ { { \displaystyle = \prod _ { i = 1 } ^ { m } \operatorname* { P r } \left( \big \vert h _ { s , r _ { i } } \vert ^ { 2 } \geq \frac { \mu ^ { \prime } } { \mu ( x ) } \right) \prod _ { k = 1 , k \neq k _ { 1 } , k _ { 2 } \ldots k _ { n } } ^ { \kappa } \operatorname* { P r } \left( \big \vert h _ { s , r } \vert ^ { 2 } < \frac { \mu ^ { \prime } } { \mu ( x ) } \right) } \ ~ } \\ { { \displaystyle = \sum _ { p = 0 } ^ { \kappa - m } \sum _ { \iota _ { k = 1 } , k _ { m + 2 } \ldots k _ { m - p } \vert \diamondsuit } ( - 1 ) ^ { p } ~ \exp \left( - \frac { \mu ^ { \prime } } { \mu ( x ) } U ^ { s \kappa } \right) } \ ~ } \end{array}
$$

其中： $U ^ { s R } \cong \sum _ { i = 1 } ^ { m = p } \frac { 1 } { \Omega _ { s , r _ { i } } }$ 。将式(26)、(31)和(32)代入(24)，可得：

$$
\begin{array} { r l } { \left. { \wp ( \{ \mathbf { k } _ { 1 } , \mathbf { k } _ { 2 } , \ldots \mathbf { k } _ { m } \} ) = \sum _ { \stackrel { \scriptstyle \beta } { \scriptstyle \varphi = 1 } } ^ { N } \sum _ { \iota , \eta _ { 1 } , \ldots , \eta _ { \ell } = 3 } ^ { m } \prod _ { \iota = 0 } ^ { q } \sum _ { \iota , \eta _ { 1 } , \ldots , \eta _ { \iota } = 1 , \atop \infty } } } \\ & { \times \sum _ { \stackrel { \scriptstyle \beta = 0 } { \scriptstyle ( \mathbf { k } _ { m } , \mathbf { k } _ { m - 1 } , \ldots , \mathbf { k } _ { m - 1 } ) = 1 } } ^ { \ell - m } \sum _ { \iota , \iota , \eta _ { 1 } , \ldots , \tau _ { \iota } \leq \mathbf { k } } ^ { \ell } } \\ & { \times \prod _ { i = 1 } ^ { m } \left( 1 - \sum _ { \iota , \tau _ { i } , \tau _ { i - \tau _ { i , \tau } , \zeta , \tau _ { i , \tau } } \in \mathbb { N } } ^ { \ell } - 1 \right) ^ { \ell } ( U ^ { \kappa , \tau } , \mu ^ { \prime } U ^ { \kappa D } ) \right) } \\ & { \times ( - 1 ) ^ { \ell + p \cdots + \ell } \left( U ^ { \kappa , \tau } , \mu ^ { \prime } \big ( U _ { \iota } ^ { \infty } + U _ { \kappa - \tau } ^ { \infty } + U ^ { \kappa } \big ) \right) } \end{array}
$$

最后将式(17)和(25)得到的结果代入式(10)中，可以得到存在中继节点协作情况下的信道中断概率：

$$
\begin{array} { r l } { P _ { \mathrm { e r f } } } & { = \displaystyle \sum _ { x = 1 } ^ { N } \displaystyle \sum _ { y = x , y = \infty } \sum _ { u = 1 , u = y , u = u , v = u } ^ { N } ( - 1 ) ^ { \mathrm { e r f } - 1 } } \\ & { \times ( \xi ( U ^ { y \top } , u U ^ { w } ) - \xi ( U ^ { y \top } , u U ^ { \prime } ( U ^ { w } + U ^ { w } ) ) ) } \\ & { + \displaystyle \sum _ { u = 1 , u = x , w < w } ^ { N } \displaystyle \sum _ { u = 1 } ^ { N } \sum _ { u = x , v = x } \sum _ { v = w } ^ { N } \prod _ { \substack { v = x , v > w , u = y , v = w , v = w } } } \\ & { \times \displaystyle \sum _ { v = 0 } ^ { N } \displaystyle \sum _ { ( u , u , u = x , w ) \times \operatorname* { m a x } } \sum _ { u = 1 , u = x , v = u } ^ { N } } \\ & { \times \displaystyle \prod _ { u = 1 } ^ { N } ( 1 - \sum _ { u = x , u = x , w = x } ^ { N } ( - 1 ) ^ { u } \xi ( U ^ { w } , u U ^ { w } ) ) } \\ & { \times ( 1 - 1 ) ^ { \mathrm { e r f } - 1 } \xi ( U ^ { w } , u ^ { w } ) \xi ( U ^ { w } + U _ { w } ^ { w } + U ^ { w } ) ) } \end{array}
$$

# 4 仿真结果

本文仿真环境为DellPC 机，处理器为 Intel(R)Core(TM)

i5-4210U CPU $ @ 1 . 7 0 \mathrm { G H z }$ ， $2 . 4 0 \mathrm { G H z }$ ，内存为8.00GB,操作系统为64位Win10系统。

通过使用MonteCarlo仿真对不同信道条件下提出的CRRS方式的性能进行比较。假设通信网络中包含的节点数量为8个，系统中目的节点成功解码信息包的阈值 $\mu { ' } { = } 2$ ，噪声功率为$\sigma _ { _ 0 } ^ { 2 } { = } 1$ ，干扰阈值 $R _ { _ { 0 } } { = } 2 0 d B W$ ，所有链路的信道增益值1，即$\mid h _ { _ { s , r } } | ^ { _ { 2 } } = \mid h _ { _ { r , d } } | ^ { _ { 2 } } = h _ { _ { s , d } } | ^ { _ { 2 } } = \mid h _ { _ { s , p } } | ^ { _ { 2 } } = \mid h _ { _ { r , p } } | ^ { _ { 2 } } = 1$ 。同时分析信道相干性对吞吐量结果的影响。且对CRRS、未协作NCARQ、传统ARQ 在衰落信道随机生成的吞吐量进行比较。

图3显示了在不相干信道()情况下，中断概率函数不同时平均吞吐量变化情况。在此情况下，存在中继节点的信道性能优于源-目的信道的衰落边缘量：，，当中继节点存在比源节点更优的信道条件时，可以被看做与中继节点协作的结果。

![](images/332387c531f0309d39177e87e7bb2f1515176131fb69a934bf68125ceac73190.jpg)  
图3中断概率不同时平均吞吐量变化情况

当 $P _ { _ { o v e r } } < 0 . 5$ 的情况下，NCARQ和CRRS性能变得比较接近。当 $P _ { o v e r }$ 值超过0.5时，CRRS方法利用具有更好的信道条件下与中继节点协作，因此该方法优于传统ARQ和NCARQ。它可以被理解为随着 $P _ { o v e r }$ 值的增大,源-目的信道条件逐渐减弱。此时，随着连续传输成功概率的降低，协作传输需求增多。

![](images/4a2ddb83f17d53db3eb4b37cc221c3ed35db31c98799e8f716f7ff0fb434fb4c.jpg)  
图4信道相干系数不同时平均吞吐量变化情况

换句话说，当 $\lambda \to 1$ 时，中继节点越趋近于目的节点，意味着中继-源信道逐渐提高。当 $\lambda \to 0$ 时，中继节点越趋近于源节点，但是情况恰好相反。在这种情况下，假设中继节点信道条件优于源-目的信道条件，当 $F _ { _ { s , d } } { = } 0 d B$ 时，结果是随着 $\lambda$ 增加，中继-目的信道的衰落边缘量也增大，中继节点协作对吞吐量有较大的影响。另外，对于 $\lambda > 0 . 8$ 的情况，随着吞吐量 $\lambda$ 增加吞吐量降低，因为源-中继信道频繁中断且协作机会减少。因此，与 $\lambda < 0 . 8$ 的情况相比，协作条件有较小影响。此时，CRRS 和NCARQ之间的主要差异是协作条件和源-中继和中继-目的信道条件。

![](images/1a1ce2f5bb1a9a2c738057fff4a3677260af36306078261d11cddfe948038362.jpg)  
图5相对位置不同时平均吞吐量变化情况

图4显示信道相干系数不同时平均吞吐量变化情况。当信道相干性增强时，所有方式的性能都有明显降低趋势，尤其当源-目的信道衰落边缘量很低时(F =0dB)。当 ${ \frac { F _ { r } } { F _ { s } } } = 1 0 d B$ 时，CRRS方式的性能衰退量最小，这是由于中继节点协作为长时间的中断提供空间分集优势。

图5显示在不相干信道( $\scriptstyle \rho = 0$ )情况下,源节点和目的节点相对于中继节点相对位置的吞吐量的变化情况。相对位置在衰落边缘率 $\frac { F _ { r , d } } { F _ { s , d } }$ 愛和機 $\frac { F _ { s , r } } { F _ { s , d } }$ 中反映。其中 $F _ { s , d }$ 保持不变， $F _ { r , d }$ 愛和機 $F _ { s , r }$ 随看源节点和目的节点相对中继节点位置变化，此时相对位置参数 $\lambda$ （204为

$$
\frac { F _ { _ { r , d } } } { F _ { _ { s , d } } } = \frac { 1 } { \left( 1 - \lambda \right) ^ { 2 } } \qquad \frac { F _ { _ { s , r } } } { F _ { _ { s , d } } } = \frac { 1 } { \lambda ^ { 2 } }
$$

# 5 结束语

本文提出了通信网络中基于协作中继重传策略，该策略在源节点直传信息包失败时，通过选取最优中继节点协作传输，充分利用空间分集和网络编码技术使目的节点接收到的信息包成功解码。当中继信道的条件优于源-目的信道，中继节点的协作传输将提供一定优势使网络性能达到最优。在下一步的工作中，本文将结合网络的安全性进一步探究如何在信息包进行广播重传阶段提高网络传输的安全。

# 参考文献：

[1]Sundararajan JK,Shah D,Medard M.ARQ for network coding [C]//Proc

ofIEEE International Symposium on Information Theory. Toronto.2008: 1651-1655.   
[2] 谭哲.认知无线电网络中动态合作中继选择算法的研究[D].北京：北 京交通大学,2016.   
[3]赵国锋，陈婧，韩远兵，等.5G 移动通信网络关键技术综述[J].重庆 邮电大学学报：自然科学版,2015,27(4):441-452.   
[4]Mo Z,Su W,Batalama S,etal. Cooperative communication protocol designs based on optimum power and time allocation [J].IEEE Trans on Wireless Communications,2014,13(8):4283-4296.   
[5]Tran T,Nguyen T,Bose B,et al.A hybrid network coding technique for single-hop wireless networks [J].IEEE Journal on Selected Areas in Communications,2009,27(5): 685-698.   
[6]Dong N,Tran T, Nguyen T, et al. Wireless broadcast using network coding [J].IEEE Trans on Vehicular Technology,2009,58 (2): 914-925.   
[7]Chang H H,Wang P Y,et al.Afractional spurfree adpll with loop gain calibration and phase noise cancellation for GSM//GPRS//EDGE [C]//Proc of Solid-State Circuits Conference.,20o8:200-606.   
[8]Abdulaziz M,Shakir M,LuP,et al.A2.7GHz divider-less all digital phaselocked loop with $6 2 5 \mathrm { H z }$ frequency resolution in 90nm CMOS [C]// Proc of Norchip.2011:1-4.   
[9]Kuo FW,Chen R,YenK,et al.A $1 2 \mathrm { m W }$ all-digital PLL based on class-F DCO for 4G phones in $2 8 \mathrm { n m }$ CMOS[C]//Proc of Symposium on VLSI Circuits Digest of Technical Papers.2014:1-2.   
[10] Ding Haiyang,Ge Jianhua,et al.A new efficient low complexity sch eme for multi-source multi-relay cooperative networks [J]. IEEE Trans on Vehicular Technology,2011,60 (20): 716-722.   
[11]Duy TT,Kong HY.Performance analysis ofhybrid decode amplify forward incremental relaying cooperative diversity protocol using SNR-based relay selection [J].Journal of Communications& Networks,2013,14(6):703- 709.   
[12]HuangL,Chi WS.Scheduling and network coding for relay aided wireless broadcast: optimality and heuristic [J].IEEE Trans on Vehicular Technology, 2014,63 (2):674-687.   
[13] Antonopoulos A,Renzo M D,Verikoukis C.Effect of realistic channel conditions on the energy efficiency of network coding-aided cooperative MAC protocols [J].IEEE Wireless Communications,2014,20 (5): 76-84.   
[14] Wang Y,Liu KJR.Statistical delay QoS protection for primary users in cooperative cognitive radio networks [J].IEEE Communications Letters, 2015,19(5): 835-838.