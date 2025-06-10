# FlexRay静态段消息调度优化研究

陈珊，尚丽辉，张凤登(上海理工大学 光电信息与计算机工程学院，上海 200093)

摘要：为提高FlexRay 网络的静态段带宽利用率，对基于时隙复用的FlexRay静态段进行优化研究。将传输的信号编码成消息帧，把编码问题转换为数学意义上的带约束装箱问题，将发送周期呈倍数关系的信号封装成一个消息帧，并运用BFD算法求解。之后基于封装的消息帧，提出一种调度方法使静态段带宽利用率最大化和帧ID数目最小化。最后在FlexRay底盘综合控制系统上验证该方法。结果证明，该算法使带宽利用率提升了 $1 8 . 7 \%$ ，将每个通信周期内所占的FID个数降低了 $9 0 . 4 7 \%$ ，并且把循环周期内静态时隙利用率提升了 $4 1 . 5 2 \%$ 。

关键词：FlexRay；带宽利用率；调度；时隙复用 中图分类号：TP336 doi:10.19734/j.issn.1001-3695.2018.06.0494

# Research on scheduling optimization of FlexRay static segment messages

Chen Shan, Shang Lihui, Zhang Fengdeng (SchoolofOptical-Electrical&ComputerEngineering,UniversityofShanghaiforScience&Technologyhanghai200093, China)

Abstract:Inordertoimprove the bandwidthutilization,this paper is basedon slot multiplexing.It encoded the transmited signalinto amessage frame,andtransformed the problem intoaconstrainedpacking problem.Itencapsulatedthe signal with multiple relationships intoamessge frameandsolveditbyBFDalgorithm.Basedonthis,itputforwarda method thatcan maximize thebandwidthand minimizethenumberofframeID.Finaly,theverificationojectis theFlexRaychasissynthesis control and safety system.Experimentally,the proposed algorithm increases the bandwidth utilization by $1 8 . 7 \%$ ,reduces the proportion of FIDs in each communication cycle by $9 0 . 4 7 \%$ ,and increases the static time slot utilization in the cycle by $41 . 5 2 \%$ Key words: FlexRay; bandwidth utilization; scheduling; timeslot multiplexing

# 0 引言

随着数据通信量的增加，传统的车载总线已经不能满足汽车网络传输对于可靠性、确定性的需求。为了适应这些需要，人们研究开发了FlexRay多路实时传输网络，它具有高吞吐量、确定性、容错性和灵活性等特点[I]，将成为继CAN之后未来车载网络发展的主流[2]。在实时系统中，调度的目的是尽可能地保证每个任务都满足其时间约束，并及时对外部请求作出及时准确的响应[3]。调度算法对网络性能有着至关重要的作用，在分析与总结现有网络调度算法的基础上进行相应优化，从而加快FlexRay总线在实时故障安全通信方面的进程。

目前对FlexRay调度算法的研究主要集中在带宽优化，而对网络安全性和可靠性的研究较少，同时也忽略了系统的可扩展性和通信实时性等关键方面的研究[4]。文献[5]分析了静态段消息的传输规则，给出了计算消息帧长度和静态时隙的方法；文献[6]将消息调度问题划分为信号打包和消息时隙分配，分别以最大化网络带宽利用率和最小化时隙个数为优化目标，并采用整数线性规划方法进行建模和求解；文献[7]提出一种消息调度策略，在满足可调度的情况下使所需的帧ID最小。本文针对静态段的调度，在满足实时性要求的时间参数配置和提高静态段带宽利用率的基础上，进行基于时隙复用机制的静态段消息调度方案的优化研究，同时还考虑系统的可扩展性。并在FlexRay底盘综合控制和安全系统中进行验证，优化其配置系统中的相关参数，得出并分析调度优化结果，进行实时性评估。

# 1 FlexRay通信协议

车内的高级通信技术由FlexRay 提供，其最大数据速率可达10Mbps，总数据速率可以达20Mbps。当采用冗余通道通信时，提供了传输容错，当采用非冗余通道通信时，提高了带宽。整个协议是基于时间触发架构的，实现了确定性通信[8\~10]。FlexRay 节点主要由五个部分组成，分别是主机(HOST)、电源、总线监控器(BG)、总线驱动器(BD)、通信控制器(CC)。

# 1.1 帧格式与编码

静态段消息帧由头段(head segment)、负载段(payloadsegment)、尾段(trailer segment)三部分组成，其帧格式如图1所示。在传输的过程中，节点按照图1所示从左向右的顺序传输数据。

![](images/a38b5c1fc6bc45ff416888dee7c2756e27930e959ab949cc6837189632227430.jpg)  
图1FlexRay 静态段消息帧格式

头段的前五位依次为保留位、有效负载预指示位、空帧指示位、同步帧指示位与启动帧指示位。11位帧 ID(frame ID):帧ID用于定义消息帧的发送时隙，定义该帧在每个通信周期的哪个时隙传输。7位负载段长度(payload length)。11 位头段CRC 校验(header CRC)：头段 CRC 用于判断传输数据的正确性。6位周期计数值(cyclecount)。负载段的长度是可以进行配置的，但是负载段的长度必须在0\~254个字节间。尾端包含3个字节的CRC 校验位。

静态帧负载段的数据 $0 \sim 1 2$ 这13个字节可以作为网络管理向量，其他数据在剩余字节发送，如图2所示。

![](images/f810091732feda5852dd26d46ea81739a0102f4a1a8548d3cc6b52bc19ef7773.jpg)  
Fig.1FlexRay static segment message frame format   
图2静态帧负载段

静态帧的编码规则如图3所示。编码时会额外加上传输起始位(TSS)、帧起始位(FSS)、字节起始位(BSS)、帧结束位(FES)。

![](images/4e0a9acf17ec6cb8dc845e576c70136382820e6b87712e1f804b7c9fd5f36a3b.jpg)  
Fig.2Static frame load segment   
图3经过编码后的静态帧配置  
Fig.3 Encoded static frame configuration

# 1.2静态段通信机制

FlexRay 的每个通信循环包括静态段(static segment，SS)、动态段(dynamic segment，DS)、符号窗口(symbolwindow，SW)和网络空闲时间(network idle time，NIT)。其静态段是基于时分多址(time division multiple access，TDMA)的访问机制，以通信周期循环为基础进行消息传输。静态段被分成若干个大小相等的静态时隙且具有唯一的帧ID。帧标示符连同其他数据一同发送，通过与时隙计数器比较确定该消息帧是否在当前时隙传输。

# 1.3静态段传输特性

由于异步系统可以实现软件复用，本文的研究对象是针对异步系统进行消息和任务的调度，且在时隙复用的机制上进行消息调度优化。由帧格式可得，每个负载段数据都需要进行相应地添加头部和尾部，进行编码后，在总线上实时传输数据。静态段是由1\~cSlotIDMax个静态时隙构成的，静态时隙是由若干宏个节拍组成，网络中各个节点的静态时隙长度都是相同的。

在进行调度优化时，以负载段讨论，如果消息帧的负载段需要传输 $i$ 个字节，则所需要的最小时隙时间长度 $T _ { s T S } ^ { i }$ 为

$$
T _ { S T S } ^ { i } = \Bigg \lceil \frac { ( 1 0 9 + 1 0 \times i + 2 \times T _ { A P O } ) \times g d B i t } { T u r } \Bigg \rceil \cdot T u r
$$

其中：取传输起始序列为15 位； $g d B i t$ 表示一个比特位所占用的时间，即存在 $g d B i t { = } I / C$ ， $C$ 为 FlexRay 的带宽，一般可取$C { = } 1 , 2 . 5 , 5 , 1 0 \ \mathrm { M b p s }$ 。

取网络中最长消息帧的长度为静态时隙的长度，即存在：

$$
g d S t a t i c S l o t = \operatorname* { m a x } \left\{ \forall T _ { S T S } ^ { i m } \right\}
$$

其中： $i _ { m }$ 表示消息 $m$ 的负载段度。

由于各个消息帧负载段的长度之间存在一些差异，为了避免造成较大的带宽浪费及后续消息帧发送延迟，所以必须对静态时隙的长度进行优化配置。

如果有 $n$ 个周期性的消息帧 $( m _ { 1 } , m _ { 2 } , . . . , m _ { \mathrm { n } } )$ 对应的负载段有 $( i _ { 1 } , i _ { 2 } , . . . , i _ { \mathrm { n } } )$ 个字节，那么传输这些消息帧对应的最小长度为(Ts,Ts..,Ts)）。由式(2)可知，静态段的带宽损失为L，其表达式为

$$
L = \sum _ { k = 1 } ^ { n } ( g d S t a t i c S l o t - T _ { S T S } ^ { i k } ) \cdot f _ { k }
$$

其中： $f _ { k }$ 为每一个消息帧在循环周期内的的传输频率。

网络利用率[5]可以表示为

$$
U = 1 - { \frac { L } { g d S t a t i c S l o t \times \displaystyle \sum _ { k = 1 } ^ { n } f _ { k } } }
$$

从式(4)分析可知，对静态时隙进行合理配置对消息的有效调度至关重要。在上述消息帧的基础上引入带宽利用率的概念，带宽利用率表征了分配的带宽有多少用于传输有效的周期性数据，此处的有效数据是指构成消息帧负载段的信号数据，由此引入了信号封装成帧的概念[11\~13]，其中信号数据是每个节点主机实际处理的数据。

设一个网络中存在 $N$ 个节点，满足 $N { = } \{ 1 , { \ldots } , N \}$ ，对于每个节点 $n \in N$ ，存在的信号数据集合为 $\boldsymbol { S } ^ { n } = \left\{ \boldsymbol { S } _ { 1 } ^ { n } , . . . , \boldsymbol { S } _ { k ^ { n } } ^ { n } \right\}$ ，对于集合中的每一个信号 $S _ { b } ^ { n } \in S ^ { n }$ ，都具有信号周期 $p s _ { b } ^ { n }$ 、信号截止时间$d { s } _ { b } ^ { n }$ 、信号数据长度 $b s _ { b } ^ { n }$ (以位为单位）三个属性。因为所有的信号都需要在通信周期 $T _ { c }$ 的整数倍内被调度，在不考虑动态段信号以及忽略符号窗口和网络空闲时间的前提条件下，选择信号周期 $T _ { c }$ 为所有信号周期的最大公因数或者是它的整除数，记为$T _ { c , S T S \circ }$ 在理论分析时，假定存在 $p s _ { b } ^ { n } = d s _ { b } ^ { n }$ ，也即存在 $p s _ { b } ^ { n } \geq T _ { c }$ 。

如果 $S _ { s } ^ { n } , S _ { t } ^ { n } \in p a c k ^ { n } ( M _ { m } ^ { n } )$ ，则有 $p s _ { s } ^ { n } = p s _ { t } ^ { n }$ ，这说明只有周期相同的信号才能被封装到一个消息中，同时对消息存在$p m _ { m } ^ { n } = p s _ { b } ^ { n } , d m _ { m } ^ { n } = d s _ { b } ^ { n } , b m _ { m } ^ { n } = \sum _ { S _ { b } ^ { n } \in p a c k ^ { n } ( M _ { m } ^ { n } ) } b s _ { b } ^ { n } \ 。$

对于某个节点 $n \in N$ 中的任意一个信号 $S _ { b } ^ { n } \in S ^ { n }$ ，则信号所需要的带宽占用率为

$$
D _ { b } ^ { n } = { \frac { b s _ { b } ^ { n } } { p s _ { b } ^ { n } \cdot T _ { c } \cdot C } }
$$

那么对于网络中的所有节点的信号数据的带宽占用率为

$$
D = \sum _ { n = 1 } ^ { N } \sum _ { b = 1 } ^ { k ^ { n } } D _ { b } ^ { n }
$$

同理，对于一个消息 $M _ { { \mathfrak { m } } } ^ { n } \in M ^ { n }$ ，则消息所需要的带宽占用率为

$$
A _ { _ m } ^ { n } = { \frac { ( T _ { S T S } \cdot C ) } { p m _ { _ m } ^ { n } \cdot T _ { c } \cdot C } } = { \frac { T _ { S T S } } { p m _ { _ m } ^ { n } \cdot T _ { c } } }
$$

网络中的所有节点的消息的带宽占用率为

$$
A = \sum _ { n = 1 } ^ { N } \sum _ { m = 1 } ^ { l ^ { n } } A _ { m } ^ { n }
$$

静态段的带宽利用率 $U$ ，可以表示为

$$
U = { \frac { D } { A } }
$$

影响FlexRay网络带宽利用率的因素主要有协议的要求、网络配置的静态时隙长度固定两个方面，在第二个因素中涉及到信号的封装优化算法。

静态段的带宽利用率的表达式为

$$
U _ { s T S } = \frac { D } { A } = \frac { \displaystyle \sum _ { i = 1 } ^ { N } \sum _ { b = 1 } ^ { k ^ { n } } \frac { b s _ { b } ^ { n } } { p s _ { b } ^ { n } \cdot T _ { c } \cdot C } } { \displaystyle \sum _ { i = 1 } ^ { N } \sum _ { m = 1 } ^ { l ^ { n } } \frac { T _ { s T S } } { p m _ { m } ^ { n } \cdot T _ { c } } }
$$

优化的目标是使静态时隙长度 $T _ { S T S }$ 最小。对于特定的网络数据，如果一味减小静态时隙长度，编码过程中会增加额外的比特位，这使得带宽未充分地用于发送有效信号数据，同时也会使得消息帧数量增多，从而需要更多的静态时隙FID来传输这些消息帧。协议规定，静态时隙的数目是有一定的限制，最大可以取得1023。为了未来的扩展需求，需要尽可能地最小化所需的FID的个数，调度优化的目的就是在两者的约束下，找到一个合适的平衡点。

在进行调度之前要先对网络进行如下限定：

a)在FlexRay的通信系统内不存在消息发送错误和失败；

b)网络中所有需要进行传输的信号的周期、截止时间和信号数据长度是已知的，并且假设信号的截止时间等于其周期，这将有利于信号的封装；

c)通信周期 $T _ { c }$ 取为网络中所有信号的最大公约数。

在同一节点内，允许将不同周期的信号封装为一帧，这可能会增加静态时隙的长度，但是另一方面它会使所用时隙的个数减少，有利于以后的网络扩展需求。同时针对静态段的时隙分配问题，采用新版本提出的时隙复用的机制来进行合理的FID 分配。因此对静态段的优化研究主要转换为信号封装的优化和FID分配的优化。

# 2 静态段消息调度的优化

# 2.1信号封装的优化

信号封装优化的目的就是为了最大化带宽利用率，即求解最小化消息的带宽占用率。假定一个FlexRay 网络中存在 $N$ 个节点，对于任意一个节点存在 $n \in N$ ，该节点包含的信号的周期集合为 $P ^ { n } = \left\{ { p _ { 1 } ^ { n } , \cdots , p _ { r } ^ { n } } \right\}$ ，周期为 $p _ { j } ^ { n } \in P ^ { n }$ 的信号的集合为$S _ { p _ { j } ^ { n } } ^ { n } = \left\{ s _ { p _ { j } ^ { n } , 1 } ^ { n } , \cdots , s _ { p _ { j } ^ { n } , r ( p _ { j } ^ { n } ) } ^ { n } \right\}$ 并且对于集合内的任意一个信号$S _ { p _ { j } ^ { n } , i } ^ { n } \in S _ { p _ { j } ^ { n } } ^ { n }$ ，包含有三个特性，即信号周期 $p _ { j } ^ { n }$ 、数据长度 $b _ { p _ { j } , i } ^ { n }$ ，截止时间 $d _ { p _ { j } , i } ^ { n }$ ，在理想情况下假定信号的信号周期等于其截至时间，信号数据经过特定的编码和优化处理后得到的消息帧的周期的集合 $P M ^ { n } = \left\{ p m _ { 1 } ^ { n } , \cdots , p m _ { R } ^ { n } \right\}$ ，存在 $P M ^ { n } \subseteq P ^ { n }$ ，以pm ∈PM" 为周期的消息的集合为$M _ { p m _ { k } ^ { n } } ^ { n } = \left\{ m _ { p m _ { k } ^ { n } , 1 } ^ { n } , \cdots , m _ { p m _ { k } ^ { n } , R ( p m _ { k } ^ { n } ) } ^ { n } \right\}$ 其中 $m _ { p m _ { k } ^ { n } , l } ^ { n } \in M _ { p m _ { k } ^ { n } } ^ { n }$   
（204号

借鉴典型FID分配调度算法里的 $x$ -group的概念，提出在同一个节点内允许将呈整数倍关系的信号封装到一个消息帧中，封装后的消息的周期为各个信号周期的最大公倍数。则信号封装处理的数学表述如下：

定义两个二进制变量 $X _ { p _ { j } ^ { n } , i , p m _ { k } ^ { n } , l }$ 和 $Y _ { p m _ { k } ^ { n } , l }$ ，当信号的周期 $p _ { j } ^ { n }$ （204与消息的周期 $p m _ { k } ^ { n }$ 的最大公倍数为 $p m _ { k } ^ { n }$ ，且信号 $s _ { p _ { j } ^ { n } , i } ^ { n }$ 被封装到了消息 $m _ { p m _ { k } ^ { n } , l } ^ { n }$ 中，则存在 p,i,pm, =1,若不满足其条件则为0,其表达式如式(11)所示；当以 $p m _ { k } ^ { n }$ 为周期的消息 $m _ { p m _ { k } ^ { n } , l } ^ { n }$ 中至少存在一个信号时则存在 $Y _ { { _ { p m _ { k } ^ { n } } } , l } = 1$ ，反之则取 $\mathbf { \mathrm { ~ 0 ~ } }$ ，其表达式如式(12)所示。对上述封装方式进行数学化描述可以表示为

$$
X _ { { p _ { j } ^ { n } } , i , p { m _ { k } ^ { n } } , l } \in \{ 0 , 1 \} \quad \forall i = 1 , \cdots , r ( { p _ { j } ^ { n } } ) , \forall l = 1 , \cdots , R ( p { m _ { k } ^ { n } } )
$$

$$
Y _ { _ { p m _ { k } ^ { n } , l } } \in \{ 0 , 1 \} \quad \forall l = 1 , \cdots , R ( p m _ { k } ^ { n } )
$$

$$
\sum _ { k = 1 } ^ { R } \sum _ { l = 1 } ^ { R ( p m _ { k } ^ { n } ) } X _ { p _ { j } ^ { n } , i , p m _ { k } ^ { n } , l } = 1 \quad \forall j = 1 , \cdots , r , \forall i = 1 , \cdots , r ( p _ { j } ^ { n } )
$$

$$
b m _ { p m _ { k } ^ { n } , l } ^ { n } = \sum _ { j = 1 } ^ { r } \sum _ { i = 1 } ^ { r ( p _ { j } ^ { n } ) } X _ { p _ { j } ^ { n } , i , p m _ { k } ^ { n } , l } = 1 \quad \forall k = 1 , \cdots , R , \forall l = 1 , \cdots , R ( p m _ { k } ^ { n } )
$$

$$
( 1 0 \times \left[ { \frac { b m _ { p m _ { k } ^ { n } , l } ^ { n } } { 8 } } \right] ) \cdot g d B i t \leq Y _ { p m _ { k } ^ { n } , l } \cdot ( T _ { S T S } ^ { b } - ( 1 0 9 + 2 * T _ { A P O } ) \cdot g d B i t )
$$

$$
T _ { S T S } ^ { 2 } \leq T _ { S T S } ^ { L } \leq T _ { S T S } ^ { b } \leq T _ { S T S } ^ { U } \leq T _ { S T S } ^ { 2 5 4 }
$$

$$
T _ { S T S } ^ { L } = T _ { S T S } ^ { l } , l = \operatorname* { m a x } \left\{ \forall b _ { p _ { j } , i } ^ { n } \right\}
$$

$$
T _ { S T S } ^ { U } = \operatorname* { m a x } \Big \{ T _ { S T S } ^ { u } \Big \} , u = \sum _ { k = 1 } ^ { R } \sum _ { j = 1 } ^ { r } \sum _ { i = 1 } ^ { r ( p _ { j } ^ { n } ) } \mathrm { \Huge ~ } _ { \mathrm { g c d } ( p _ { j } ^ { n } , p m _ { k } ^ { n } ) = p m _ { k } ^ { n } } ^ { b _ { p _ { j } ^ { n } , i } ^ { n } }
$$

在式(13)表示周期为 $p _ { j } ^ { n }$ 的第 $i$ 个信号只能封装到唯一一个消息 $m _ { p m _ { k } ^ { n } , l } ^ { n }$ 中，式(14)表示封装到消息 $m _ { p m _ { k } ^ { n } , l } ^ { n }$ 中的所有信号的总和（负载段长度值)，式(15)表示封装后的消息的总的长度值必须小于静态时隙的长度值，式(16表示对可取的静态时隙长度根据协议规定以及相应的封装方式作了一定的限定，有利于减少迭代的次数。在上述的约束条件下，整个网络的优化目标表示为

$$
s . t . \sum _ { j = 1 } ^ { n } l ( a _ { i } ) \cdot x _ { i j } \leq y _ { i } , f o r ( i = 1 , 2 , \cdots , n )
$$

$$
\operatorname* { m i n } \sum _ { n = 1 } ^ { N } \sum _ { k = 1 } ^ { R } \sum _ { l = 1 } ^ { R ( { p m _ { k } ^ { n } } ) } \frac { { Y _ { p m _ { k } ^ { n } , l } } \cdot { T _ { S T S } ^ { b } } } { { p m _ { k } ^ { n } \cdot T _ { c } } }
$$

$$
\sum _ { i = 1 } ^ { n } x _ { i j } = 1 , f o r ( j = 1 , 2 , \cdots , n )
$$

在上述数学模型的基础上，分析得出相应的信号封装优化的算法步骤：

a)针对每一个节点 $n$ ，先按周期对各个信号进行分类，并从小到大排列，各个周期下的信号按照长度值由大到小排列。

$$
\operatorname* { m i n } z = \sum _ { i = 1 } ^ { n } y _ { i }
$$

b)确定静态时隙的上、下限。下限 $T _ { L } ^ { S T S }$ 如式(17)所示，它表示不存在信号封装，取值为所有信号中所需的发送时间最长的时间长度值；上限 $T _ { U } ^ { S T S }$ 如式(18)所示，它表示为将所有呈整数倍关系的消息都封装到一个消息帧中，取所有消息帧中所需的发送时间最长的时间长度值。

c)通过迭代对每一个静态时隙 $\boldsymbol { T } _ { b } ^ { s T S }$ ，每次增加2个字节长度，进行上述封装处理，并计算出带宽利用率值。

d)从得出的所有带宽利用率值中取最大值，取出其对应的最优的静态时隙长度和封装方式。

在基于允许呈整数倍关系的信号封装在同一个消息帧的思想下,以及建立了静态段信号封装的数学模型的基础上，求解最优的静态时隙长度以及相应的信号封装方式的问题可以相应地转换为装箱问题。

一维装箱问题的描述：设给定箱子的容积为一正数 $\mid c \mid$ 和一组物品的序列 $L { = } \{ a _ { 1 } , a _ { 2 } , . . . , a _ { \mathrm { n } } \}$ ,其中物品的大小 $\mathbf 0 < l ( a _ { i } ) < c , \forall i$ ，装箱问题就是要寻求一种装载方式 $A$ 将 $L$ 分成一些互不相交的子集 $B _ { j }$ ，满足 $L = B _ { 1 } \bigcup B _ { 2 } \bigcup \cdots \bigcup B _ { m }$ ，以及 $\sum l ( a _ { i } ) \leq c , \forall j$ ，并使得所使用的箱子总数为 $m$ 满足这一要求的最小整数[14]。

装箱问题的线性规划的数学描述为

由于装箱问题是一个离散的组合优化问题，它也是一个典型的 NP 完全问题(non-deterministic polynomial)[15\~18]。目前为止相继提出了针对装箱问题的各种近似算法，本设计中主要采用降序最佳适应算法(best fitdecreasing，BFD),来完成对FlexRay网络的周期信号的封装处理。

BFD算法适用于静态段的离线调度，即在设计阶段就完全确定各个信号的发送时序，它的最坏情况渐进性能比为11/9。结合上述对装箱问题的描述，可知信号的数据长度视为物体的体积，静态时隙长度为箱子的容积。针对FlexRay 网络的各个节点，在离散的静态时隙长度，优先将相同周期的信号封装到一个消息帧以及允许将与它呈整数倍的信号封装到同一帧内的条件下进行BFD算法的封装处理。

# 2.2 FID分配的优化

在上述的信号封装完成的基础上，即已知所有的消息的集合以及静态时隙的长度，之后引入时隙复用的机制，即同一个时隙编号可以在不同的周期将其分配给不同节点，这将更有利于静态时隙的有效运用，避免时隙的浪费。大多数的研究未给出切实可用的静态调度表，本设计将针对这一些不足，并研究各消息的循环周期 $r _ { m }$ 不再局限于 $2 ^ { q } ( 0 \leq q \leq 6 )$ ，即满足 $\forall r _ { m } \leq 6 4$ 设计合理有效的静态调度表来实现对静态段的消息调度的优化

对于封装后的所有消息，将其表示为 $m ( n _ { i } , p _ { j } , c )$ ，其中$n _ { i } ( i { = } 1 , . . . . , N )$ 表示所属的节点编号， $P _ { j }$ 表示该消息的周期，$c ( c { = } 1 , { \ldots } , r ( p _ { j } ) )$ 表示某个节点下某个周期的消息编号，同时引入一个四元变量 $( n _ { i } , f _ { m } , r _ { m } , b _ { m } )$ 来唯一确定特定的时隙由哪一个节点来发送哪个周期的信号。

在时隙复用的前提下的FID的优化分配是对整个网络所用的FID个数的优化，从消息周期的角度来进行合理的时隙分配，更加高效地来利用各个时隙。假设FlexRay网络存在两个节点$n _ { 1 } , ~ n _ { 2 }$ ，消息的集合依次为 $m ( n _ { 1 } , 1 , 1 )$ ， $m ( n _ { 1 } , 2 , 1 )$ ， $m ( n _ { 1 } , 3 , 1 )$ ，$m ( n _ { 2 } , 1 , 1 ) , m ( n _ { 2 } , 2 , 1 ) , m ( n _ { 2 } , 6 , 1 )$ ，如果按照经典的优化调度方式，则需要5个静态时隙，按周期从小到大来安排调度，并将时隙复用运用于上述的静态调度，可得所需的时隙数目为4，其中周期为1的消息不能与其同周期的消息共用一个时隙，而其他的消息的周期只要与基周期呈倍数关系，不论其是否属于同一个节点，都可以采用时隙复用，即可以使用同一个时隙在不同的通信周期发送，则其对应的静态调度表如表1所示。

<html><body><table><tr><td></td><td>FID=1</td><td>FID=2</td><td>FID=3</td><td>FID=4</td></tr><tr><td>cc=0</td><td>m(n1,1,1)</td><td>m(n2,1,1)</td><td>m(n1,2,1)</td><td>m(n1,3,1)</td></tr><tr><td>cc=1</td><td>m(n1,1,1)</td><td>m(n2,1,1)</td><td>m(n2,2,1)</td><td>m(n2,6,1)</td></tr><tr><td>cc=2</td><td>m(n1,1,1)</td><td>m(n2,1,1)</td><td>m(n1,2,1)</td><td></td></tr><tr><td>cc=3</td><td>m(n1,1,1)</td><td>m(n2,1,1)</td><td>m(n2,2,1)</td><td>m(n1,3,1)</td></tr><tr><td>cc=4</td><td>m(n1,1,1)</td><td>m(n2,1,1)</td><td>m(n1,2,1)</td><td></td></tr><tr><td>cc=5</td><td>m(n1,1,1)</td><td>m(n2,1,1)</td><td>m(n2,2,1)</td><td></td></tr></table></body></html>

本文从互质周期的角度对网络中的消息进行分类，如果某个周期能被多个质周期整除，则规定能被质周期中的某个 $x$ 整除且商最小的归为一类。

假设FlexRay 网络中含有 $x _ { c }$ 个group，每个类下的所有消息构成相应的集合 $L _ { x }$ ，每个消息 $m \in L _ { x }$ 的循环周期取整均满足$r _ { m } = \frac { p _ { j } } { T } \leq 6 4$ ，则此网络所需的最少的FID 的个数为

$$
F A = \sum _ { x = 1 } ^ { x _ { c } } \Biggl [ \sum _ { m \in L _ { x } } { \frac { 1 } { r _ { m } } } \Biggr ]
$$

无前置约束的FID优化算法的具体步骤如下：

a)计算 $T _ { c }$ （所有消息周期的最大公约数）及 $N _ { T C }$ （所有消息周期的最小公倍数除以所有消息周期的最大公约数）。

b)找出消息集合中的质数周期，对各个消息进行如上所述的分类，针对每一个 $x$ -group下的消息集合 $L _ { x }$ 中的各个元素按周期和节点序号升序排列。

c)运用相应算法合理分配各个消息的 $f _ { m }$ 及 $b _ { m }$ ，从而为每个消息分配特定的位置变量 $( n _ { i } , f _ { m } , r _ { m } , b _ { m } )$ 。假设 $\boldsymbol { u }$ 表示对特定一个时隙编号在 $N _ { T C }$ 下的时隙利用率，周期编号为cc={0,1,,Nrc-1≤63}，当前的时隙编号为fe，将u和fe初始化为0。

假设存在一个FlexRay网络，有两个节点 $n _ { 1 } , n _ { 2 }$ 包含相同的消息，消息的集合如表2所示。

表2消息集合（ $\scriptstyle { i = 1 , 2 }$ ）  
Table 2Message collection $( i { = } 1 , 2 )$   

<html><body><table><tr><td>m(ni,1,1)</td><td>m(ni,1,2)</td><td>m(ni,2,1)</td><td>m(ni,2,2)</td><td>m(ni,2,3)</td><td>m(ni,3,1)</td></tr><tr><td>m(ni,3,2)</td><td>m(ni,3,3)</td><td>m(ni,3,4)</td><td>m(ni,4,1)</td><td>m(ni,4,2)</td><td>m(ni,4,3)</td></tr><tr><td>m(ni,4,4)</td><td>m(ni,4,5)</td><td>m(ni,4,6)</td><td>m(ni,4,7)</td><td>m(ni,6,1)</td><td>m(ni,4,2)</td></tr></table></body></html>

从表2分析可知 $T _ { c } { = } 1 m s$ ， $\scriptstyle N _ { T C } = 1 2$ ，如果按照经典文献的方式进行调度则需要16个静态时隙，且在不同的通信周期内有很多时隙是浪费的，如果采用本文的优化调度方案所使用的时隙个数是15，所以本文提出的优化方案具有可行性，能够提高静态段的时隙利用率，用较少的时隙个数来调度所有消息，有利于以后网络的扩展，如节点的增加或者各个节点的消息的数量的增加。

# 3 仿真分析

在分析FlexRay 传输规则的基础之上，提出了FlexRay 网络静态段带宽利用率的优化方法。由于文中所提的方法对数据量和节点较多的网络优化性能更好，所以将在实际的汽车底盘综合控制系统中来验证所提出的优化方案。底盘综合控制系统由电子稳定控制系统(ESC)、车辆自适应系统(ACC)、FlexRay-CAN网关系统(GW)、电动助力转向系统(EPS)、连续减震控制系统(CDC)、空气悬挂系统(ASC)组成。该系统的总线布置结构如图4所示。

每个子系统分别对应于不同的节点，该系统的静态消息集合[19]如表3所示。

![](images/d6e8529d625484516d34537e4f882aa4fdf3171088da174fbc66ca500706fc6e.jpg)  
图4底盘综合控制系统结构图  
Fig.4Chassis integrated control system structure

表3周期性静态消息集合  
Table 3Periodic static message collection   

<html><body><table><tr><td>节点名称</td><td>信号名称</td><td>周期/ms</td><td>长度/byte</td><td>信号表示</td></tr><tr><td rowspan="3">ESC</td><td>ESC-Status</td><td>4</td><td>6</td><td>S</td></tr><tr><td>ESC-WheelRot</td><td>4</td><td>8</td><td>S.2</td></tr><tr><td>ESC-WheelSpeed</td><td>4</td><td>4</td><td>S</td></tr><tr><td rowspan="3">ACC</td><td>ESC-DampReq</td><td>4</td><td>2</td><td>s</td></tr><tr><td>ACC-Status</td><td>6</td><td>10</td><td>S</td></tr><tr><td>ACC-ESCReq</td><td>6</td><td>8</td><td>S2</td></tr><tr><td rowspan="8">GW</td><td>GW-Status</td><td>16</td><td>40</td><td></td></tr><tr><td>EMS-AirConStatus</td><td>8</td><td>8</td><td>S</td></tr><tr><td>EMS-Status</td><td>8</td><td>8</td><td>S</td></tr><tr><td>EMS-IdleSpeed</td><td>8</td><td>6</td><td>S</td></tr><tr><td>EMS-AccpeDaRos</td><td>8</td><td>9</td><td>S</td></tr><tr><td>EMS-Temp</td><td>16</td><td>3</td><td>S62</td></tr><tr><td>EMS-Torq</td><td>16</td><td>8</td><td>S6.3</td></tr><tr><td>TCU-Status</td><td>16</td><td>8</td><td>SG</td></tr></table></body></html>

<html><body><table><tr><td colspan="2">TCU-Temp</td><td>8</td><td>8</td><td>S</td></tr><tr><td colspan="2">TCU-TurSpeed</td><td>8</td><td>9</td><td>S</td></tr><tr><td rowspan="3">EPS</td><td>TCU-TorqReq</td><td>8</td><td>5</td><td>S</td></tr><tr><td>EPS-Status</td><td>6</td><td>7</td><td>S</td></tr><tr><td>EPS-StrAng</td><td>6</td><td>5</td><td>S</td></tr><tr><td>CDC</td><td>CDC-Status</td><td>8</td><td>8</td><td>s</td></tr><tr><td>ASC</td><td>ASC-Status</td><td>12</td><td>4</td><td>S2</td></tr></table></body></html>

用于分析验证的系统采用单信道进行节点间的信号传输，首先根据相应的配置规则设定 $T _ { A P O } { = } 1 \cdot T _ { M T } , T _ { M T } { = } 1 { \mathrm { ~ } } \mu \mathrm { s } , C { = } 1 0 \mathrm { ~ M b p s } _ { \mathrm { ~ c } }$ （20通信周期必须是所有静态消息的公约数，否则静态消息将无法循环传输，根据表3可知，通信周期可以设置为 $1 \mathrm { m s }$ ，一个通信周期可以没有符号窗，但是肯定要存在网络空闲时间，配置为 $1 0 0 ~ \mathrm { M T }$ 。采用三种不同的调度方式来对网络中的信号数据进行调度，也即完成相应的封装处理，在相同的传输速率下进行对比研究。

a)未进行任何优化处理的原始的协议所规定的按最长的消息长度来确定静态时隙的长度配置，而且各个节点的参数配置完全相同，计算静态段的带宽利用率；

b)在经典调度的条件下去完成该实例的调度[1I]，即在每一个节点下，只有相同周期的信号数据才能封装到一个消息帧当中进行处理，得到一个封装方案，并求解带宽利用率；

c)在文中所允许的时隙复用的基础上，以及同一个节点下的允许呈整数倍的信号数据可被封装至一个消息帧中，将其在一个静态时隙内发送，得出相应的封装方案，并求解带宽利用率。

在特定的时间，对独立的各个节点将相应的信号利用文中的封装方式转换为消息帧，之后在完成信号封装的基础上进行基于时隙复用下的FID的分配优化验证。

将该实际的汽车底盘综合控制系统的各个节点信号数据集合用于以上提出的三种不同的封装方式，可以得出相应的最佳静态时隙长度和带宽利用率；同时，对于一个具体的网络，可以求得其信号的带宽是 $\scriptstyle D = 0 . 0 1 7 3$ ，，其具体的结果如表4所示。

表4不同信号封装方式下的静态时隙参数和带宽利用率

Table 4Static slot parameters and bandwidth utilization in different signal encapsulation modes   
表5信号封装优化后需传输的消息帧集合  

<html><body><table><tr><td>传输速率</td><td>封装方式</td><td>静态时隙参数TsTs/μs</td><td>带宽利用率U/%</td><td>消息帧个数</td></tr><tr><td rowspan="2">10 Mbit/s</td><td>未进行信号封装</td><td>53</td><td>10.89</td><td>21</td></tr><tr><td>经典信号封装</td><td>53</td><td>28.01</td><td>9</td></tr></table></body></html>

<html><body><table><tr><td>信号封装优化</td><td>53</td><td>29.59 8</td></tr></table></body></html>

通过分析表4可知，采用本文所提出的信号封装优化方式，可以相应地提高静态段的网络带宽利用率。在该方式下的最优的信号封装的消息帧集合如表5所示。相对于经典信号封装来说，提高了 $5 . 6 6 \%$ ，这将更有利于未来汽车功能节点的增加以及信号量增多的数据传输情况。同时由于网关内的GW-Status信号数据长度比其他情况大很多，所以三种调度方式下的静态时隙参数没有变化。如果系统的节点数越多，即用于传输的信号数据量越多，同时各个信号数据的周期种类更多，信号长度更加不均匀的情况下的话，本文提出的信号封装优化将会对带宽利用率的提高有更加显著的效果。

Table 5Collection of message frames to be transmitted after signal encapsulation optimization   

<html><body><table><tr><td>节点名称</td><td>周期/ms</td><td>消息帧表示</td><td>信号数据组合</td></tr><tr><td>ESC</td><td>4</td><td>M(1,4,1)</td><td>S+S+S4+S44</td></tr><tr><td>ACC</td><td>6</td><td>M(2,6,1)</td><td>S.2</td></tr><tr><td rowspan="3">GW</td><td>16</td><td>M(3,16,1)</td><td>S</td></tr><tr><td>8</td><td>M(3,8,1)</td><td>2+S+S4+S 3 +S</td></tr><tr><td>8</td><td>M(3,8,2)</td><td>S6.2</td></tr><tr><td>EPS</td><td>6</td><td>M(4,6,1)</td><td>S 6,2 +S4</td></tr><tr><td>CDC</td><td>8</td><td>M(5,8,1)</td><td>s</td></tr><tr><td>ASC</td><td>12</td><td>M(6,12,1)</td><td></td></tr></table></body></html>

如果相应地扩大节点数目和信号数据的数目，那么随着网络节点以及周期性信号越多，采用本文的封装方式来求解对应的带宽利用率，其值将大于等于其他两种封装方式，所以，本文提出的信号封装优化方案具有一定的可行性。

本文采用时隙复用的机制下设计相应的算法，确立每个信号帧在各个循环周期里的特定调度位置，通过该方案可以尽可能地减少每个通信周期内的静态时隙个数，使每个静态时隙能够做到利用最大化，这样可以为未来系统的节点扩展预留更多的带宽；同时，在该方案下，可以不改变系统的配置，只需要对新加入的节点按照本系统的参数进行相应地配置就可以使用所以该调度方案对网络具有极大的可扩展性。

在已完成了信号封装优化的基础上，对需要用于在网络进行传输的消息帧安排它们在循环周期内的各个调度位置，得出相应的静态消息调度表。基于之前的分析可以得出该FlexRay的循环周期包含 $\scriptstyle N _ { T C } = 4 8$ 个通信周期，对上述三种封装下进行不复用的FID和信号封装优化方式下的时隙复用的FID分配，得出四种方式下超周期下用于传输消息帧的FID的个数与总线分配总的FID个数之比（循环周期内静态时隙利用率）作相应地统计并进行对比，其结果如表6所示。

表6不同FID分配方式下的静态时隙利用率对比  

<html><body><table><tr><td>封装方式</td><td>每个通信周期所占FID个数/FA</td><td>循环周期内静态时隙利用率/%</td></tr><tr><td>未进行信号封装时隙不复用</td><td>21</td><td>13.69</td></tr><tr><td>经典信号封装时隙不复用</td><td>9</td><td>12.96</td></tr><tr><td>信号封装优化时隙不复用</td><td>8</td><td>12.24</td></tr><tr><td>信号封装优化时隙复用</td><td>2</td><td>55.21</td></tr></table></body></html>

通过分析表6可知，在前述的三种封装完成的基础上，进行时隙不复用的分配调度方式会使得循环周期内静态时隙利用率较低，所以，在特定的循环周期下，会造成许多静态时隙并未用于传输任何静态消息帧。本文在基于时隙复用机制的基础上，提出相应算法来确定各个消息帧在特定循环周期内的位置，最小化每个周期的FID的个数，并且最大化的提高循环周期内静态时隙利用率，从而在一定程度上减少了系统所需要的FID的个数，便于未来的扩展。同时，该验证系统在本文提出的静态段消息调度优化算法下得出的调度表如表7所示。

表7将循环周期分成两个部分来给出，其中第一、四列表示通信周期的编号，其余几列表示在每个周期下的时隙编号下所传输的消息帧。通过结合表7的结果可知，本文提出的FID优化方式能很好地利用静态段的时隙，每个通信周期所需的FA个数已达到最小值，使得剩余的静态时隙便于未来网络的扩展，而不用更改已配置的其他节点。

基于上述的验证和分析可知，在以最大化静态段带宽利用率为目标，并尽可能地减少每个通信周期所需的静态时隙个数的约束下，本文所提出的消息调度方案具有一定的可行性。

# 4 结束语

对于FlexRay总线静态段的消息调度，本文提出信号封装优化和基于时隙复用的FID分配算法，得出静态时隙的最佳长度，以及对应的静态段消息调度表，有效提高静态段带宽利用率以及减少通信周期所需要的FID个数，这为车载网络新功能的扩展提供了有效保障。仿真结果表明，本文提出的信号封装优化算法可使带宽利用率达到 $2 9 . 5 9 \%$ ，且消息帧的个数减少为8。文中提出的FID分配法可将每个通信周期所占的FID个数减少为2，将循环周期内的时隙利用率提升至 $5 5 . 2 1 \%$ 。

本文在研究FlexRay静态段消息调度的优化时，未考虑到网络通信中可能会出现的传输故障和汽车内部存在的抖动问题，在今后的研究中，将深入分析静态时隙配置问题对通信可靠性和实时性的影响，以及将该调度算法用于实际的汽车系统中进行调试，进一步优化FlexRay的消息调度方案。

表7FID分配优化静态调度表

Table 6Comparison of static time slot utilization under different FID allocation modes   
Table 7FID allocation optimization static schedule   

<html><body><table><tr><td>CC</td><td>fm=1</td><td>fm=2</td><td>Cc</td><td>fm=1</td><td>fm=2</td></tr><tr><td>0</td><td>M(1,4,1)</td><td>M(2.6,1)</td><td>24</td><td>M(1,4,1)</td><td>M(2,6,1)</td></tr><tr><td>1</td><td>M(3,8,1)</td><td>M(4,6,1)</td><td>25</td><td>M(3,8,1)</td><td>M(4,6,1)</td></tr><tr><td>2</td><td>M(3,8,2)</td><td>M(6,12,1)</td><td>26</td><td>M(3,8,2)</td><td>M(6,12,1)</td></tr><tr><td>3</td><td>M(5,8,1)</td><td></td><td>27</td><td>M(5,8,1)</td><td></td></tr><tr><td>4</td><td>M(1,4,1)</td><td></td><td>28</td><td>M(1,4,1)</td><td></td></tr><tr><td>5</td><td>M(6,16,1)</td><td></td><td>29</td><td></td><td></td></tr><tr><td>6</td><td></td><td>M(2,6,1)</td><td>30</td><td></td><td>M(2,6,1)</td></tr><tr><td>7</td><td></td><td>M(4,6,1)</td><td>31</td><td></td><td>M(4,6,1)</td></tr><tr><td>8</td><td>M(1,4,1)</td><td></td><td>32</td><td>M(1,4,1)</td><td></td></tr><tr><td>9</td><td>M(3,8,1)</td><td></td><td>33</td><td>M(3,8,1)</td><td></td></tr><tr><td>10</td><td>M(3,8,2)</td><td></td><td>34</td><td>M(3,8,2)</td><td></td></tr><tr><td>11</td><td>M(5,8,1)</td><td></td><td>35</td><td>M(5,8,1)</td><td></td></tr><tr><td>12</td><td>M(1,4,1)</td><td>M(2,6,1)</td><td>36</td><td>M(1,4,1)</td><td>M(2,6,1)</td></tr><tr><td>13</td><td></td><td>M(4,6,1)</td><td>37</td><td>M(6,16,1)</td><td>M(4,6,1)</td></tr><tr><td>14</td><td></td><td>M(6,12,1)</td><td>38</td><td></td><td>M(6,12,1)</td></tr><tr><td>15</td><td></td><td></td><td>39</td><td></td><td></td></tr><tr><td>16</td><td>M(1,4,1)</td><td></td><td>40</td><td>M(1,4,1)</td><td></td></tr><tr><td>17</td><td>M(3,8,1)</td><td></td><td>41</td><td>M(3,8,1)</td><td></td></tr><tr><td>18</td><td>M(3,8,2)</td><td>M(2,6,1)</td><td>42</td><td>M(3,8,2)</td><td>M(2,6,1)</td></tr><tr><td>19</td><td>M(5,8,1)</td><td>M(4,6,1)</td><td>43</td><td>M(5,8,1)</td><td>M(4,6,1)</td></tr><tr><td>20</td><td>M(1,4,1)</td><td></td><td>44</td><td>M(1,4,1)</td><td></td></tr><tr><td>21</td><td>M(6,16,1)</td><td></td><td>45</td><td></td><td></td></tr><tr><td>22</td><td></td><td></td><td>46</td><td></td><td></td></tr><tr><td>23</td><td></td><td></td><td>47</td><td></td><td></td></tr></table></body></html>

# 参考文献：

[1]Bill Chilcott.FlexRay end its application real time multiplexed network [M]. UK:Wiley& Son,Ltd,Publication,2012:19-23.   
[2]郭雪剑.现代汽车车载网络技术应用[J].电子技术与软件工程,2014 (18): 41.(Guo Xuejian.Modern automotive vehicle network technology application [J].Electronic Technology and Software Engineering,2014 (18): 41.)   
[3]张凤登．分布式实时系统[M]．北京：科学出版社，2014.(Zhang Fengdeng. Distribution real-time systems [M].Beijing:Science Press, 2014.)   
[4]巍叶华，颜碧云．车载FlexRay 网络调度算法综述[J].传感器与微系 统,2014,33(1):5-10.(Wei Yehua,Yan Biyun. Survey of vehicle FlexRay network schedulingalgorithms[J]. Transducerand Microsystem Technologies,2014,33(1): 5-10.)   
[5]Kang M,Park K,Kim B. Determining the size of a static segment and analyzing the utilization of in-vehicle FlexRay network [C]// Proc of International Conference on Convergence and Hybrid Information Technology.2008:50-53.   
[6]Cena G,Valenzano A.On the properties of the flexible time division multiple access technique [J].IEEE Trans on Industrial Informatics,2006,2 (2): 86-94.   
[7]郑文学．车载网络FlexRay 调度方案优化设计研究[D].杭州：浙江大 学,2013.(Zheng Wenxue.Research on optimization design of FlexRay scheduling scheme for vehicle network [D]. Hangzhou: Zhejiang University, 2013.)   
[8]梁杰申，王虹．新型总网 FlexRay 网络通信设计实现[J].微处理机, 2011，32 (2):20-23．(Liang Jieshen,Wang Hong.Design and implementation of new total network FlexRay network communication [J]. Microprocessors,2011,32 (2): 20-23.)   
[9]王跃飞，曹三峰，毕翔，等．一种基于时隙动态分配的 FlexRay 系统通 信机制[J].电子测量与仪器学报,2015(2):179-186.(Wang Yuefei,Cao Sanfeng,Bi Xiang,et al.A communication mechanism of FlexRay system based on time slot dynamic allocation [J]. Journal of Electronic Measurement and Instrument, 2015 (2): 179-186.)   
[10] JuanRO S,Kim H S.Reconfiguration of an FPGA-based time-triggered FlexRay network controller using EEDC[J].Journal of Circuits Systems & Computers, 2017: 1850096.   
[11] Schmidt K, Schmidt E G.Message scheduling for the FlexRay protocol: the static segment [J].IEEE Trans on Vehicular Technology,20o9,58(5): 2160- 2169.   
[12]Kang M,Park K, Jeong MK.Frame packing for minimizing the bandwidth consumption of the FlexRay static segment [J]. IEEE Trans on Industrial Electronics,2013,60(9): 4001-4008.   
[13]胡游，李仁发，吴武飞．车载异构网络网关数据封装方法[J].计算机 工程，2017,43 (2):1-5.(Hu You,Li Renfa,Wu Wufei.Vehicle heterogeneous network gateway data encapsulation method [J]. Computer Engineering,2017,43 (2):1-5.)   
[14]董一鸿，赵杰煜．带约束的一维装箱问题近似算法的研究[J].计算机 与工程应用,2003,39(18):41-44.(Dong Yihong,Zhao Jieyu.Research on approximation algorithm for constrained one-dimensional packing problem [J].Computer and Engineering and Applications,2003,39 (18): 41-44.)   
[15]张明会，韩鑫.物品大小不超过1//2 的一维在线装箱模型研究[J]．系 统科学与数学,2017,37(3):781-791.(Zhang Minghui,Han Xin.Research on one-dimensional online packing model with item size not exceeding 1//2 [J].Journal of Systems Science and Mathematical Sciences,2017,37 (3): 781-791. )   
[16]刘明明，童小娇，戴或虹．装箱问题的算法及最新进展[J].计算数学, 2016,38 (3):257-280.(Liu Mingming，Tong Xiaojiao,Dai Yuhong. Algorithm and latest development of packing problem [J]. Mathematica Numerica Sinica,2016,38(3): 257-280.)   
[17]朱智林，时晨，韩俊刚，等．周期性任务调度的装箱算法[J].计算机 应用,2006,26 (3): 679-691.(Zhu Zhilin,Shi Chen,Han Jungang,et al. Packing algorithm for periodic task scheduling [J]. Journal of Computer Applications,2006,26 (3): 679-691.)   
[18] Zheng F,Luo L,Zhang E.NF-based algorithms for online bin packing with buffer and bounded item size [J]. Journal of Combinatorial Optimization, 2013,30 (2): 1-10.   
[19] Park I, Sunwoo M.FlexRay network parameter optimization method for automotive applications [J].IEEE Trans on Industrial Electronics,2011,58 (4): 1449-1459.