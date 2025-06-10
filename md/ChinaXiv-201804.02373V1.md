# VANET中基于公平性的多信道MAC协议\*

汤媛媛a,b，朱琦a,b

(南京邮电大学a.江苏省无线通信重点实验室;b.教育部宽带无线通信与传感网技术重点实验室，南京 21003)

摘要：随着车载无线通信需求的增加，车载自组织网络（VANET）将成为现代智能交通系统的一个重要组成部分。对VANET中多信道MAC层协议进行了研究，提出了一种提升网络公平性的退避算法。车辆通过比较自身已成功发送的业务量与平均业务量的大小，确定不同的退避方案，一定程度上实现网络中车辆的接入公平。考虑到该退避算法在提升公平性的同时，牺牲了一定的网络吞吐量，服务信道不饱和，进一步提出根据车辆密度调整服务预约时期长度的算法，提高服务信道的利用率，增大网络的吞吐量。仿真结果表明，提出的退避算法公平性指数相比于二进制退避算法，提升了约2.3倍，而相比于倍数增线性减退避算法，提升了约2.05倍，网络的吞吐量提高了约 $1 6 \%$ 。

关键词：VANET；公平性；多信道MAC层；退避算法 中图分类号：TP393.04 doi: 10.3969/j.issn.1001-3695.2018.02.0111

# Multichannel MAC protocol based on fairness in VANET

Tang Yuanyuana, b, Zhu Qia, b (a.JiangsuKeyLaboratoryofWirelessCommunications,b.KeyLaboratoryofWidebandWirelessCommunications&Sensor Network TechnologyofMinistryofEducation,NanjingUniversityfPosts&Tlecommunications,Nanjingoo,hina)

Abstract: With the increasing of vehicular wirelesscommunication,vehicle ad hoc networks (VANETs) have become an important partof the Inteligent Transportation System.Basedon the multi-channel MAC protocolin VANETs,this paper proposedabackoffagorithm for diferent nodes considering fairnessof network.Bycomparing the sucesful sending trafic throughputofthe nodeandtheaverage traffc throughputforits neighbors,the node determined backoff windows sothatto improve thefairnesinaccessng proces.Inodertoimprove thefimess ofnetwork,thealgorithsacrificedamountoftraffic throughput.Noticed that the service channels are notsaturated,this paper also proposedanalgorithm toadjust the length of servicereservation period based onnode density.Thealgorithmimproved theutilizationofservice channelsandthethroughput ofnetwork.Simulationresults indicatedthatcomparing withthe BEBalgorithmandthe MILDalgorithm,the proposedbackoff algorithmcan efectively improve fairness of network by2.3times and2.05times,respectively.Meanwhile,theadjusting algorithm can significantly improve the network throughput by $1 6 \%$ ，

Key words:VANETs; fairness of network;multi-channel MAC; backoff algorithm

# 0 引言

车载自组织网络（vehicularAdhocnetworks,VANET）是现代智能交通系统（intelligent transportation system）的一个重要组成部分。在车载自组织网络中，通信主要在车与车之间（vehicle-to-vehicle，V2V）和车与基础设施之间（vehicle-to-infrastructure）进行[1,2]，包括实时安全信息、辅助驾驶信息和娱乐业务信息等的传输，为实现车辆的安全驾驶提供了稳定的信息交互支持，在保障交通安全、避免交通拥堵等方面发挥重要的作用。

VANET的MAC协议对网络性能有很大影响，文献[3]提出的HER-MAC协议，将时分多址接入（time-divisionmultipleaccess，TDMA）与CSMA（carrier sense multiple access）多址接入方式相结合，采用VeMAC[4提出的TDMA的方式进行安全信息的广播。在此基础上，文献[5]通过分析车辆密度、CCH丢包率、SCH吞吐量和各个时期间隔长度的关系，提升了系统性能。文献[6]动态地调整CCHI与SCHI的长度，提高信道的占用率，增加接入信道的车辆数。文献[7,8]提出了业务提供车辆的服务信道选择方法，将可用的服务信道和时隙加在安全信息中广播，避免隐藏终端问题，提高网络的吞吐量。这些协议均根据车辆收到的邻居车辆广播的信息，决定自身的广播时隙和业务信道，但是由于存在碰撞导致接收的信道信息不准确，

造成信道资源的浪费，网络吞吐量低。因此本文考虑根据车辆密度与实时得到的信道占用情况进行各个时期长度的调整，提升系统性能。

文献[9]提出了多信道C-MAC协议，通过RSUs的协助实现车辆间无竞争的安全信息的广播。文献[10]提出通过RSUs的协助改进时隙的接入方式，RSUs接收车辆的广播信息，同时进行传播，降低传输碰撞率。文献[11,12]在RSUs的协助下进行时隙接入，广播安全信息，RSUs协助车辆通过握手的方式进行SCH预约，同时根据车辆成功预约概率和服务信道时长优化成功预约服务的车辆对数，最大化网络的吞吐量。

但是，通过RSUs协助进行信道分配的方式，对基础设施有一定的要求，在现实的车辆移动场景中不宜实现。因此文献[13]在车载自组织网络中，对HER-MAC协议进行了改进，调整了安全信息的结构，减少了不必要的控制开销，提高了控制信道上的吞吐量。但对于业务信道的预约方式仍然采用二进制指数退避算法[14]（binary exponentialbackoff，BEB)，容易造成退避时间长的车辆长时间无法接入信道，不能进行业务的传输，出现不公平的现象。

为了提升网络的公平性，本文提出了一种基于公平性的退避算法，该算法通过比较车辆自身已成功发送的业务量与平均业务量的大小，确定不同的退避方案，以提高车辆接入业务信道的公平性；根据车辆密度调整服务预约时期的长度，以提高业务信道的利用率，增大网络的吞吐量。仿真结果表明，提出的退避算法能有效的改善网络的公平性，同时提高了系统吞吐量。

# 1 基于公平性的服务信道接入算法

假设在一个车载网络中，每个车辆都装备有一个半双工无线收发器，可以发送或者接收数据，但不能同时进行，所有车辆都通过GPS（global positioning system）进行时间和位置同步。将时间按照帧进行分割，每帧(sync interval，SI)的持续时间为$1 0 0 \mathrm { { m s } }$ ，帧结构如图1所示。根据HTC-MAC协议，将SI分为CCHI和 SCHI两部分。将CCHI分为安全信息广播时期（safetybroadcastperiod,SBP）和服务预约时期（service reservationperiod，SRP）两个时期。在SBP 阶段，将时长分为多个等长的时隙（safetyslot)，车辆根据VeMAC协议接入其中一个时隙，广播安全信息以及自身的位置、速度等。在SRP阶段，有业务要发送的车辆先通过竞争的方式进行信道接入，与HTC-MAC协议采用的BEB退避算法不同的是，在该阶段车辆接入信道需要考虑网络公平性，从而调整竞争窗口大小，确定退避时间。成功接入信道的车辆再通过握手的方式进行服务信道的分配。在SCHI，成功预约服务信道的车辆将接收器调整到分配好的服务信道，在预定的时隙进行业务信息的传输。

![](images/5839b4e5ffb0015690cd6dae4d3cd866929afef543588ac5d6031d8915744ec3.jpg)  
图1时间帧结构图

# 1.1安全信息广播时期

在SBP阶段，车辆发送安全信息。未接入信道的车辆根据自身一跳范围内车辆占用的时隙情况，获得空闲的时隙列表，从中随机选择一个空闲时隙接入，如果在接下来的一帧时间内没有其它的两跳邻居车辆占用相同的时隙，则接入成功，且在接下来的帧内都占用相同的时隙进行安全信息的广播。因为车辆车速、方向等的变化，导致网络的拓扑结构变化迅速，占用相同时隙的车辆可能会进入彼此的两跳范围，这会造成安全信息的碰撞，此时这两个车辆都需要根据当前的邻居时隙占用信息重新选择空闲可用的时隙接入。安全信息的结构如图2所示，包含六部分的内容：

a）车辆的身份ID： $x$ ：b）该车辆占用的时隙序号： $t _ { x }$ ：

c）该车辆一跳邻居车辆占用的时隙情况的位图，标0表示该时隙空闲，标1表示该时隙已被占用： $I _ { x } ^ { ( 1 ) }$ ：d)该车辆两跳邻居车辆占用的时隙情况的位图，标0表示该时隙空闲，标1表示该时隙已被占用： $I _ { x } ^ { ( 2 ) }$ ；e）该车辆要广播的安全信息；f）该车辆在进入该网络后已成功发送的业务数量： $n$ 。其中， $t _ { x }$ 、 $I _ { x } ^ { ( 1 ) }$ 和 $I _ { x } ^ { ( 2 ) }$ 为网络中的车辆提供时隙占用信息，保证可用时隙信息的及时获取与更新，保证安全信息的可靠传播。车辆根据收到的安全信息，统计邻居车辆已成功发送的业务数量 $n$ 的总和，从而进行在SRP阶段的竞争窗口的调整，提高整个网络的公平性。

![](images/aa0bce5152cb4c7bfd986d830f830f8b8e1e7238025d7faa9849d36c7975479f.jpg)  
图2安全信息帧结构图

# 1.2 服务预约时期

1）竞争接入阶段

当SBP阶段结束后，有业务要发送的车辆进入竞争接入阶段，开始侦听信道。根据BEB算法，第i次尝试接入的退避窗口大小为

$$
C W _ { i } = \left\{ \begin{array} { l c } { { 2 \times C W _ { i - 1 } , } } & { { \quad 0 < i \leq m } } \\ { { C W _ { \mathrm { m i n } } , } } & { { \quad \stackrel { \mathrm { H } } { \mathrm { \ : \ : \vec { E } } } \stackrel { . } { } } } \end{array} \right.
$$

其中: $m$ 为车辆的最大退避次数， $C W _ { \mathrm { m i n } }$ 为最小竞争窗口。

BEB 算法实现了车辆的信道接入，但是不能准确的反映当前的车辆竞争情况，同时会带来不公平的现象。退避窗口小的车辆在接下来的竞争过程中获胜的概率大于退避窗口大的车辆，获胜的车辆更容易接入信道，而失败的车辆则可能因为退避窗□的增大长时间无法接入信道，导致信道接入的不公平。

倍数增线性减[15]（multiplicative increase linear decrease, MILD）算法是对BEB算法的改进。车辆第 $i$ 次尝试接入的退避 窗口大小为

$$
C W _ { i } = \left\{ { \cal M } i n ( \alpha \times C W _ { i - 1 } , C W _ { \operatorname* { m a x } } ) , \right.
$$

其中: $C W _ { \operatorname* { m a x } }$ 是退避窗口最大值，车辆发生冲突时，退避窗口扩大 $\alpha$ 倍，车辆接入成功，退避窗口减少 $\beta$ 0

当 $\alpha$ ， $\beta$ 取值合理时，退避窗口不会急剧增加或减少，一定程度上，改善了了各个车辆退避时间相差较大的问题。但是，对于接入失败的车辆，退避时间仍然较大，信道接入的不公平现象仍然存在。

为了能进一步提升竞争接入阶段的网络的公平性，本文提出了一种基于公平性的退避算法。首先，车辆根据在安全信息广播阶段收到的邻居车辆发送的安全信息，统计一跳范围内的邻居车辆在该网络中已成功发送的业务量，即在服务预约时期已成功预约的次数。定义 $\theta _ { x }$ 为自身成功预约次数与邻居车辆进入该网络后的成功预约次数之和的比值：

$$
\theta _ { x } = \mathtt { n } _ { x } / s _ { x }
$$

其中: $n _ { x }$ 表示车辆 $x$ 已成功预约次数， $s _ { x }$ 表示车辆 $x$ 的一跳邻居车辆总的成功预约次数。若车辆 $x$ 一跳范围内的邻居车辆数目为 $N _ { \mathnormal { x } }$ ，令

$$
\delta _ { x } { = } 1 / N _ { x }
$$

当 $\theta _ { x } { = } \delta _ { x }$ 时，说明车辆 $x$ 此时的成功预约次数与当前的一跳邻居车辆的平均成功预约次数相等，认为车辆 $x$ 的请求接入达到相对公平的状态。如果 $\theta _ { x } > \delta _ { x }$ ，则说明车辆 $x$ 的成功接入次数较大，需适当的增大退避窗口，降低竞争接入的可能性。如果 $\theta _ { x } < \delta _ { x }$ ，则说明车辆 $x$ 的成功接入次数较小，需适当的降低退避窗口，提高竞争接入的可能性。因此可以通过比较 $\theta _ { x }$ 和$\delta _ { x }$ ，动态调整网络中每一个车的退避窗口大小，改变每个车辆车预约信道的概率，最终实现整个网络的相对公平。

当车辆 $x$ 需要重新确定退避窗口时，比较车辆 $x$ 自身的 $\theta _ { x }$ 值与 $\delta _ { x }$ 值，判断当前的公平情况。如果 $\theta _ { x }$ 值偏大，车辆的成功预约次数相对较多，成功接入后，车辆 $x$ 的退避窗口值应线性降低；如果发生接入冲突，则按照比例因子 $\gamma _ { _ { 1 } }$ 倍数增大退避窗□。如果 $\theta _ { x }$ 值偏小，则表明车辆的成功预约次数相对较少，成功接入后退避窗口变为最小退避窗口 $C W _ { \mathrm { m i n } }$ ；如果发生接入冲突，则按照比例因子 $\gamma _ { _ 2 }$ 倍数增大退避窗口。车辆 $x$ 在竞争接入阶段的退避窗口调整方法可以表示如下：

当 $\theta _ { x } \geq \delta _ { x }$ 时，

$$
C W _ { i } = \left\{ \begin{array} { l l } { M i n ( C W _ { i - 1 } - \sigma , C W _ { \mathrm { m i n } } ) } \\ { M a x ( C W _ { i - 1 } \times \gamma _ { 1 } , C W _ { \mathrm { m a x } } ) } \end{array} \right.
$$

当 $\theta _ { x } < \delta _ { x }$ 时，

$$
C W _ { i } = \{ \begin{array} { c c } { { C W _ { \mathrm { m i n } } , } } & { { \quad \mathrm { H } \} } } \\ { { M a x ( C W _ { i - 1 } \times \gamma _ { 2 } , C W _ { \mathrm { m a x } } ) , } } & { { \quad \mathrm { K } \nonumber } } \end{array} 
$$

其中 $\sigma$ 为常数。

车辆 $x$ 的退避窗口确定后，车辆 $x$ 下一次进行竞争接入的退避时间BackoffTime $( x )$ 为

$B a c k o f f i m e ( x ) = R a n d o m [ 0 , C W _ { i } ] \times a S l o t t i m e$ 其中，aSlottime为退避时间的最小单位。

2）服务信道和时隙分配阶段

当车辆 $x$ 的退避时间递减到0且信道空闲时，车辆 $x$ 发送WSA（WAVE serviceannouncement）数据包，该数据包包含业务类型、业务内容及要占用的服务信道的序号和时隙等信息。车辆 $x$ 根据收到的邻居车辆信息获取服务信道占用情况，更新服务信道占用列表，得到可用的服务信道序号和时隙集合，并选择占用率最低的信道以及该信道的一个空闲时隙，如果多个信道占用率均最低，则随机选择一个信道作为业务传输信道。

邻居车辆收到WSA数据包后，通过发送CTS(cleartosend）确认接收该业务，同时根据自身的服务信道占用列表判断该服务信道和该时隙是否空闲，若不空闲，则从表中选择占用率最低的信道及其中的一个空闲时隙，将其加入CTS 数据包；若空闲，则确认使用该服务信道和该时隙。

提供业务的车辆收到CTS数据包后，确认该次业务传输要使用的服务信道序号和时隙，添加到ACK（acknowledgment）数据包中广播，保证发送与接收使用相同的信道和时隙；同时邻居车辆根据收到的ACK数据包，更新自身维持的服务信道占用列表及邻居车辆已成功预约的次数。

# 1.3协议流程

车辆在控制信道时隙时，将收发器调到控制信道，在控制信道上进行安全信息广播，同时业务发送车辆与接收车辆进行信息交换，来进行在服务信道时期进行业务信息传输。协议步骤如下：

a）在安全信息广播阶段，当车辆有安全信息要发送时，如果已接入控制信道时隙，则继续占用该时隙；如果尚未接入控制信道时隙或是由于车辆移动导致两跳内有其它车辆占用相同的时隙，则重新选择一个空闲时隙接入。

b）在竞争接入阶段，有业务要发送的车辆侦听信道，根据公平性原则调整退避窗口，确定退避时间，进行信道接入。

c）当接入成功后，车辆进入服务信道和时隙分配阶段，业务发送车辆发送WSA数据包，根据自身维持的服务信道占用情况列表决定自身要占用的服务信道和时隙。

d）接受业务的车辆收到WSA后，先确认其包含的服务信道和时隙是否可用，若空闲，则将服务信道和时隙信息加在CTS数据包中发出；若不可用，则根据自身维持的服务信道占用情况列表选择可用的服务信道和时隙加在CTS数据包中发出。

e）业务发送车辆收到CTS数据包后，确认与业务接收车辆传输业务所用的服务信道序号和时隙，加入ACK数据包中发出，告知接收车辆该次业务传输使用的信道和时隙，同时通知周围车辆，有相应的服务信道和时隙被占用，周围邻居车辆根据收到的ACK数据包更新自身维持的服务信道列表。

f）服务预约时期结束后，已分配到服务信道的车辆调整到对应的服务信道，等待发送业务的时隙间隔到来，业务发送车辆在分配到的时隙发送业务，接收车辆在该时隙接收业务，业务成功接收后，接收车辆发送ACK数据包，确认成功接收。

g）当服务信道时期结束后，发送车辆和接收车辆都调整到控制信道，进行安全信息传输和服务信道预约。

# 2 基于车辆密度的服务预约时期长度调整

上文提出的基于公平性的退避算法，在提高网络公平性的同时一定程度上影响了网络的吞吐量。为了提高网络的吞吐量，本文将进一步对服务预约时期的长度进行调整。假设网络中的所有车辆在每一帧都有业务要发送，在车辆密度不同的情况下，影响该网络吞吐量的主要因素是每帧成功接入的车辆总数及SCHI的长度。而固定的SRP长度不能保证所有车辆均成功预约服务信道，SCHI可能存在空闲，造成服务信道资源的浪费。为了使更多的车辆能预约成功，可适当增大SRP的长度，保证信道资源的充分利用，增大整个网络的吞吐量。

本文提出了一种根据车辆密度调整服务预约时期长度的算法，提高信道资源的利用率。车辆根据安全信息广播阶段接收到的信息统计邻居车辆的数量，可以得到一定范围内的车辆密度。而对于高速公路场景，在一定的范围内与一定的时间内，可以认为车辆密度保持相对稳定，也就是说，网络中不同车辆得到的车辆密度近似相等。

由于车辆密度不同，需要根据在SRP阶段成功预约的次数$S _ { S R P }$ 与在 SCHI时期可发送的总的业务量 $N _ { s c H I }$ 的值调整 SRP与 SCHI的长度。若车辆每一帧发送的业务长度为 $L$ ，服务信道数据传输速率为 $R$ ，则发送一个业务占用的服务信道时长为Tpac=L/R。给定SRP的长度TSRP，确定服务信道时期时长TscHI。再根据业务的时长 $T _ { p a c }$ 和服务信道数目 $N _ { s c H }$ ，计算服务信道的容量 $N _ { s c H I }$ 为

$$
 N _ { S C H I } { = } N _ { S C H } \times { \frac { { T } _ { S C H I } } { { T } _ { p a c } } }
$$

如果当前时刻已成功预约的业务次数 $S _ { S R P }$ 大于 $N _ { s c H I }$ ，则接下来还未预约的车辆，不再进行竞争接入；如果 $S _ { S R P }$ 小于$N _ { s c H I }$ ，未预约的车辆根据基于公平性的退避算法继续进行竞争接入。当服务预约时期 $T _ { s _ { R P } }$ 结束时，判断已成功预约的业务次数 $S _ { s R P }$ 是否小于车辆总数 $N$ ，如果小于 $N$ ，则增大 $T _ { s R P }$ ；如果等于 $N$ ，表明当前帧内所有车辆都预约成功，则 $T _ { s R P }$ 保持不变。通过比较每一帧得到的吞吐量，选择吞吐量最大时对应的$T _ { s _ { R P } }$ 时长为该车辆密度下的合适的服务预约时期长度。具体的确定 $T _ { s R P }$ 的长度的方法见算法1。

算法1根据车辆密度确定服务预约时期时长算法

1:初始化:两跳内的车辆数量N；服务预约阶段时长 $T _ { s R P }$ ；帧的数量  
（204 $T$ ；服务信道时期时长 $T _ { S C H I }$ ；车辆发送的业务的时长‘  
2:for $t _ { 0 } = 1 { : } T$ （204号  
3: 根据式（8）计算 $N _ { s c H I }$ ，  
4: for $t = 1 \colon T _ { S R P }$ / slot  
5: 车辆根据基于公平性的退避算法确定退避时间，接入信道进行  
服务信道的预约；  
6: if 到当前时刻 $t$ 已成功预约的数目 $S _ { S R P } < N _ { S C H I }$ （204  
7: 未成功预约的车辆继续进行竞争接入，成功接入的车辆进行  
服务信道预约，预约成功， $S _ { S R P } { = } S _ { S R P } { + } 1$ ，预约失败， $S _ { S R P }$ 不变；  
8: else  
9: 已竞争接入的车辆请求服务信道失败；  
10: end if  
11: end for  
12: if （20 $S _ { S R P }$ 小于 $N$ （204号  
13: $T _ { _ { S R P } } { = } T _ { _ { S R P } } { + } 1 ,$   
14: else  
15: （204 $T _ { s _ { R P } }$ 不变；  
16: end

# 17:end for

18：比较每个 $t _ { 0 }$ 内的 $S _ { S R P }$ ，选择 $S _ { S R P }$ 最大时所对应的 $T _ { s R P }$

根据算法1，随着车辆密度的变化，车辆可得到对应的预约时期长度 $T _ { s R P }$ ，且在一定范围内保持不变。车载网络中的各个车辆根据得到的 $T _ { s R P }$ 确定收发器的调整时间，进行业务的发送与接收。

# 3 仿真分析

本文通过仿真分析了提出的基于公平性的退避算法和根据车辆密度确定服务预约时期长度的算法的性能。假设一个总长$\scriptstyle L = 1 0 0 0 { \mathrm { m } }$ 的高速公路场景，通信半径 $R { = } 3 0 0 \mathrm { m }$ ，车辆服从均匀分布，具体的仿真参数如表1所示。

表1仿真参数  

<html><body><table><tr><td>参数</td><td>值</td><td>参数</td><td>值</td></tr><tr><td>公路长度L／m</td><td>1000</td><td>服务信道数</td><td>6</td></tr><tr><td>车道宽度/m</td><td>5</td><td>业务大小/bytes</td><td>1024</td></tr><tr><td>车道数量</td><td>4</td><td>SCH传输速率/Mbps</td><td>6</td></tr><tr><td>平均速度/km/h</td><td>100</td><td>aSlottime长度／μs</td><td>13</td></tr><tr><td>速度标准差/km/h</td><td>20</td><td>短帧间隔大小/μs</td><td>32</td></tr><tr><td>传输半径/m</td><td>300</td><td>仲裁帧间隔大小/μs</td><td>71</td></tr><tr><td>帧长/ms</td><td>100</td><td>WSA包长度/bits</td><td>360</td></tr><tr><td>仿真时间/s</td><td>100</td><td>CTS包长度/bits</td><td>320</td></tr><tr><td>SBP阶段时长／ms</td><td>25</td><td>ACK包长度/bits</td><td>304</td></tr><tr><td>αlβ</td><td>2/1</td><td>g1Y1Y2</td><td>5/1.5/1.2</td></tr></table></body></html>

首先，比较随着车辆数目的变化，不同的退避算法下，平均吞吐量的变化。计算该网络平均每帧的吞吐量 $\overline { { C } }$ 为

$$
\overline { { C } } = \frac { \displaystyle \sum _ { i = 1 } ^ { T _ { s } } C _ { i } } { T _ { s } }
$$

其中： $C _ { i }$ 为第 $i$ 帧内成功发送的业务量， $T _ { s }$ 为总的帧数，$\scriptstyle { T _ { s } = T } / { T _ { s } } _ { \scriptscriptstyle { I } }$ ， $T$ 为总的仿真时间， $T _ { s t }$ 为帧长。

![](images/459735ce551fdc3b867ecb0c607e3e55f5aba56685cb9eedf71b6e0e442c5d68.jpg)  
图3不同退避算法下的平均吞吐量

图3比较了在服务预约时期根据二进制指数退避算法、倍数增线性减退避算法和本文提出的基于公平性的退避算法得到的平均吞吐量。从图中可以看出，本文提出的退避算法相比于二进制指数退避算法在平均吞吐量上有所增加，且随着车辆数的增多，平均吞吐量的下降平缓。这是因为对于二进制指数退避算法，当车辆增加到一定数目时，在服务信道预约阶段 $T _ { s _ { R P } }$ 内，由于车辆碰撞导致退避时间过长，无法接入信道，造成平均吞吐量的下降。本文提出的退避算法，考虑了周围车辆的信道争用状况，一定程度上缓和了退避时间相差较大的情况，增加了平均吞吐量。与倍数增线性减退避算法相比，由于本文提出的退避算法考虑了车辆的公平性，随着车辆数的增多，接入碰撞概率增大，车辆的退避时间都较长，导致成功接入的车辆数降低，吞吐量较倍数增线性减退避算法有所下降。

考虑网络的公平性，文献[16]提出了能反映整个网络的信道争用状况的公平性指数的计算方法FIAL（fairnessindexofalllinks)，将其用到本文的车载网络模型中，计算该网络的公平性指数：

$$
F I A L = \frac { \sqrt { \sum _ { i = 1 } ^ { N } ( T h r o u g h p u t _ { i } - \overline { { T h r o u g h p u t } } ) ^ { 2 } } } { \overline { { T h r o u g h p u t } } }
$$

其中： $N$ 为整个网络的车辆数量，Throughputi为车辆i已成功发送的业务量，Throughput为整个网络总的已成功发送的业务量的平均值。 $F I A L$ 越接近0，说明网络中各个车辆已发送的业务量越接近于平均值，也就表明各个车辆接入信道越公平。当$F I A L$ 等于0时，认为整个网络达到绝对公平；当 $F L A L \neq 0$ 时，公平性指标 $K$ 的定义如下：

$$
K = { \frac { 1 } { F I A L } }
$$

![](images/5ba23c6da21fb76229de8cdf8daebf8b44d3ffd1b8e60624676f391d946a87f5.jpg)  
图4不同退避算法下的公平性比较

图4比较了随着车辆数的增加，在不同退避算法下公平性指标 $K$ 的变化。从图中可以看出，本文提出的基于公平性退避算法的公平性指标 $K$ 明显高于其它两种算法，而随着车辆的增多， $K$ 有所下降。这是由于服务预约阶段 $T _ { s R P }$ 时长固定，当车辆数目逐渐增加时，无法接入信道的车辆数逐渐增多，整个网络的公平性指数 $F I A L$ 逐渐增大，从而导致 $K$ 下降。其它两个退避算法没有考虑公平性，因此公平性指标 $K$ 较低。

为了提高本文提出的退避算法的平均吞吐量，将服务预约阶段 $T _ { s R P }$ 按照车辆的密度进行调整，提高网络的平均吞吐量。

![](images/5be3f53a5847ba92ef50abecd92299fd65443300ac1b20dc881b39e6eeedf090.jpg)  
图5不同服务预约时期下的平均吞吐量

图5比较了调整服务预约时期 $T _ { s _ { R P } }$ 和固定 $T _ { s R P }$ 两种不同方式下得到的平均吞吐量。其中固定的 $T _ { s R P }$ 长度为 $2 5 ~ m s$ 。从图中可以看出，随着车辆数量的逐渐增，调整 $T _ { s _ { R P } }$ 可以明显提高车载网络的平均吞吐量。当车辆数逐渐增大时，固定 $T _ { s R P }$ 内能成功预约到服务信道的车辆数趋于稳定，网络的平均吞吐量也趋于稳定。根据车辆密度选择合适的 $T _ { s R P }$ 长度，保证在 $T _ { s R P }$ 时期成功预约到服务信道的车辆都能成功传输数据，使服务信道时隙尽可能的被占满，达到信道资源的高效利用，提高网络的平均吞吐量。

# 4 结束语

本文考虑到车载网络移动性的特点，提出了一种基于公平性的退避算法，该算法能有效提高网络中每个车辆发送业务的公平性，改善部分车辆长期无法占用业务信道的现象。同时，为了提高网络的吞吐量，车辆根据周围车辆的密度选择合适的SRP时期长度，保证SCHI的高效利用。在未来的车载通信中，考虑公平性能有效的避免车辆间不合理的占用信道资源的现象，提高其在辅助驾驶、娱乐业务等方面的表现，满足每个用户对于车载通信的多种需求。

未来工作中，将考虑更加实际的车辆移动场景，如在城市交通或者十字路口等场景下，车辆行驶速度以及车辆密度对于退避算法和SRP时期长度选择的影响，使研究环境更加接近现实，提高算法的实用性。本文只考虑了车辆发送单一业务的情况，未来的工作还需要考虑车辆发送多种业务，同时考虑业务的大小、优先级等因素，优化具体的SRP时隙长度选择算法。

# 参考文献：

[1]Wang SY,Chou CL,Liu KC,et al. Improving the channel utilization of IEEE 802.1lp//1609 networks [C]//Proc of Wireless Communications and Networking Conference.[S.1.] : IEEE Press,2009:1-6.   
[2]Dang D N M,Dang HN,Do C T,et al.An enhanced multi-channel mac for vehicularad hoc networks[C]//Proc ofIEEEWireless Communications and Networking Conference.[S.1.]:IEEE Press,2013:351-355.   
[3]DangDNM,Dang HN,Nguyen V,et al.HER-MAC:a hybrid efficient and reliable MAC for vehicular Ad hoc networks [C]// Proc of IEEE International Conference on Advanced Information Networking and Applications. [S.1.]: IEEE Press,2014:186-193.   
[4]Omar HA, Zhuang Weihua,Li Li. VeMAC: A TDMA-based MAC protocol for reliable broadcast in VANETs[J]. IEEE Trans on Mobile Computing, 2013,12 (9): 1724-1736.   
[5] Xiong Kai, Chen Xi,Rao Lei,et al. Solving the performance puzzle of DSRC multi-channel operations[C]/ Procof IEEE International Conference on Communications.[S.1.] : IEEE Press,2015: 3843-3848.   
[6]Wang Qing,Leng Supeng,Fu Huirong,et al. An IEEE 802.1lp-based multichannel MAC scheme with channel coordination for vehicular Ad hoc networks[J].IEEE Transon Intelligent Transportation Systems,2012,13 (2): 449-458.   
[7]Lee D,Ahmed S H, Kim D,et al. An efficient SCH utilization scheme for IEEE1609.4 multi-channel environments in VANETs [C]//Proc of IEEE International Conference on Communications.[S.1.]: IEEE Press,2016:1- 6.   
[8]LeeD,Ahmed SH,KimD,etal.Distributed SCH selection for concurrent transmissions in IEEE 1609.4 multi-channel VANETs [C]//Proc of IEEE International Conference on Communications.[S.1.] : IEEE Press,2017:1 6.   
[9] Kim Yunmin,Lee Mingyu,Lee T J. Coordinated multichannel MAC protocol forvehicularAd hocnetworks[J].IEEE Transon Vehicular Technology,2016,65(8): 6508-6517)   
[10] Van NguyenD,KimOTT,Dang TN,et al. Improving time slot acquisition through RSU's coordination for TDMA-based MAC protocol in VANETs [Cl// Proc of International Conference on Information Networking.[S. 1.] : IEEE Press,2016: 406-411.   
[11] Li Xiaohuan,Hu Binjie,Chen Hongbin,et al.An RSU-coordinated synchronous multi-channel mac scheme for vehicularAd hoc networks [J] IEEEAccess,2015,3:2794-2802.   
[12] Mao Yiwei, Yan Feng,Shen Lianfeng.Multi-round elimination contentionbased multi-channel MAC scheme for vehicular ad hoc networks [J]. IET Communications,2017,11 (3): 421-427.   
[13]Van NguyenD,Oo TZ,ChuanP,etal.AnEfficient Time SlotAcquisition on the Hybrid TDMA//CSMA Multi-channel MAC in VANETs [J]. IEEE Communications Letters,2016,20 (5):970-973.   
[14] IEEE Std 802.11 part 11: wireless LAN medium access control (MAC) and physical layer (PHY) specifications [S]. IEEE Press,2003.   
[15]郑少仁.Ad Hoc 网络技术[M].北京：人民邮电出版社,2005.(Zheng Shaoren.Ad hoc network technology [M]. Beijing: Posts & Telecom Press, 2005.）   
[16]李广.Ad hoc 网络多信道 MAC 协议研究与实现[D].武汉：武汉理工 大学,20o9.(Li Guang.Research and realization of the multi-channel MAC protocol in Ad hoc network [D]. Wuhan: Wuhan Universityof Technology, 2009.）