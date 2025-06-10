# 用户需求感知的D2D视频分发机制

寇兰，刘彪，黄宏程(重庆邮电大学 通信与信息工程学院，重庆 400065)

摘要：针对目前的D2D多播内容分发机制因冗余传输过高而导致簇头节点能量效率以及系统频谱效率低的问题，提出了一种基于用户需求感知的D2D视频分发机制。通过对用户视频服务请求进行预测，在为服务请求用户分发视频的同时将视频推送给潜在服务用户。首先，根据用户的兴趣、视频的流行度以及用户设备的剩余能量等估算出潜在服务用户接受视频推送的意愿；其次，提出视频分发服务效用值度量来衡量视频分发服务的价值，并对最优化簇头能量效率问题进行建模；最后，提出最优化簇头能量效率的D2D视频分发机制。实验结果表明所提出的D2D视频分发机制相较于传统分发机制其簇头的能量效率及系统吞吐量有着明显的优势。

关键词：终端直通通信；内容分发；需求感知；能量效率；吞吐量 中图分类号：TN929.5 doi: 10.3969/j.issn.1001-3695.2018.01.0011

# Demand-aware D2D video distribution mechanism

Kou Lan, Liu Biao, Huang Hongcheng† (School ofCommunication& Information Engineering,Chongqing Universityof Posts & Telecommunications，Chongqing 400065, China)

Abstract: In viewof the current D2D multicast content delivery mechanism hasa large amount of transmission redundancy, lead to lowenergy eficiencyandlow spectrumeficiency.This paperproposedanovel demand-aware D2Dvideo distribution mechanism.By predicting users’video servicerequests,thevideo is pushed to potential service users while distributing video forservicerequestusers.Firstly,te willngnessofpotentialserviceusers toaceptvideopushisestimatedbasedontheusers' interests,the popularityof thevideoandtheresidual-energyof the users’devices.Secondly,theutilitymeasureof video distribution service was proposed to measure thevalue of video distribution service,and theissue on energy eficiencyof the optimalcluster heads was modeled.Finally,this paper proposedaD2D videodistribution mechanismthatoptimizes the energy efciencyofcluster heads.Simulationresults show that the proposed mechanismis superiortothe traditional ones withregard to the energy efficiency of the cluster head and system throughput.

Key words:D2D; content distribution; demand-aware; energy efficiency; throughput

# 0 引言

随着移动互联网的迅速发展，预计从2016一2021年移动数据流量将增加约7倍，其中 $78 \%$ 的移动数据流量都是移动视频服务所产生的[1]。爆炸性增长的数据流量将会给现有的移动通信系统造成巨大的压力，D2D通信被视为解决这一问题的关键技术。D2D通信允许邻近的终端之间无须基站的协助直接进行数据通信，对于缓解基站压力、提高系统容量、增强网络覆盖和提高数据传输速率有着巨大的潜力[2.3]。而类似于视频和音乐的多媒体数据，在移动通信系统中存在大量的冗余传输，这严重降低了资源的利用效率。为了减少数据的冗余传输，提高系统容量和系统资源的利用效率，采用D2D多播通信技术为用户提供多媒体内容分发近年来受到了广泛的关注与研究[4-6]。

具有相同服务需求的用户构成一个簇，然后由簇头在簇内采用D2D多播的方式进行内容分发，这可以极大地减少多媒体数据的冗余传输，提高系统的资源利用效率。但D2D多播通信的信道容量受限于多播接收用户中的最差信道，分簇及簇头选择策略对D2D多播通信质量有着重要的影响[7]。

已有许多研究在分簇及簇头选择时考虑了信道质量的影响[8.9],文献[8]针对信道质量的差异提出了基于 SINR 约束的 D2D多播重传算法，文献[9]则根据节点与簇内各节点的稳定链接数量选出使簇内成员数量最大化的簇头节点，进而提高D2D多播总吞吐量。然而上述研究都未考虑到节点间社会关系强度对D2D 链路稳定性的影响，为此文献[10]在分簇及簇头选择时考虑节点的社会地位及与其他节点的信任度因素，其所提出的方案增强了链路的稳定性，提升了传输速率。文献[11]则在建立D2D内容分发簇时考虑了用户的兴趣因素，提出的基于余弦相似度的分簇贪婪缓存方案实现了较高的延迟性能。之前的研究都假设簇头节点是无私的，事实上簇头节点在协助其他节点进行数据分发时会大量消耗簇头节点的能量，而终端设备的可用能量是有限的，节点可能会因此不愿意参与协助数据的分发。为了提高系统的能量效率，文献[12]将能量收集技术和社交网络特性集成到D2D通信中，同时考虑了物理域、能源域和社会域的作用，在D2D 本地数据传输中显著提升了频谱及能量效率。文献[13]则提出联合功率和资源分配方案以最大化接入的D2D组的数量，同时最小化D2D多播通信的总终端传输功率，极大地提高了协助节点能量效率。

为了提升D2D多播数据分发的吞吐量和能量效率，上述研究都提出了各自的优化方案。但由于用户请求视频内容的时间不尽相同，受限于用户服务请求离散地分布在时间线上，上述的 D2D多播分发方案中同一个视频内容在同一地区内要在不同的时刻传输多次，系统中仍存在大量的冗余传输。为了进一步减少数据的冗余传输，进而提高D2D多播通信系统的资源利用效率，本文通过对用户服务请求进行预测，同时向现在与未来有相同服务请求的用户分发数据，通过增加多播簇内成员的方式提高D2D多播通信簇的吞吐量，进而提高簇头的能量效率及系统的频谱效率。

# 1 问题描述

在一个蜂窝小区内，向基站请求同一视频的用户组成一个簇，并通过合适的多播簇头选择方法选出了簇头用户。基站通过蜂窝链路向簇头用户传输该簇所请求的视频文件，然后簇头用户在簇内利用D2D多播的方式将视频分件分发给其他成员。通过D2D多播的方式可以减少同一个视频的反复传输次数，可以提高频谱的利用率，减轻基站的流量负担。由于每个用户请求视频服务的时刻不同，系统中存在许多有相同视频内容需求但发出请求时刻不同的用户，因此传统的D2D多播内容分发系统中同一个视频文件仍然会被多次传输。本文将当前时刻请求视频内容的用户称为服务请求用户，把有相同视频内容需求但此刻未发起服务请求的用户称为潜在服务用户。

如图1所示，假设系统中已经存在一个由服务请求用户构成的 D2D多播视频分发簇，簇内有一个簇头用户 $\boldsymbol { u } _ { h }$ 和 $m$ 个服务请求用户 $U _ { s } = \{ u _ { s 1 } , u _ { s 2 } , . . . , u _ { s m } \}$ 。此外，小区内还分布着 $n$ 个潜在服务用户 $U _ { _ P } = \{ u _ { _ { p 1 } } , u _ { _ { p 2 } } , . . . , u _ { _ { p n } } \}$ ，以及一个蜂窝用户 $u _ { c }$ 。其中D2D 多播通信复用蜂窝用户 $u _ { c }$ 的上行信道资源。假设 $P _ { h }$ 是簇头用户发射信号的发射功率，又因为D2D多播通信信道容量受到最差信道质量用户的限制，因此根据香农公式可得D2D多播通信的信道容量为

$$
C _ { t o t a l } = N B \log _ { 2 } ( 1 + \frac { P _ { h } g _ { h m } } { n _ { 0 } + I _ { c m } } )
$$

其中： $N$ 为该 D2D多播簇的簇内成员数量， $B$ 为信道带宽，$n _ { 0 }$ 为高斯噪声， $I _ { c m }$ 为所复用的蜂窝用户对最差信道质量用户接收数据的干扰， $g _ { \ d _ { h m } }$ 为簇头用户与最差信道用户间的信道增益。从上式可以看出，在一定的条件下通过增加D2D多播簇内成员数量可以极大地提高D2D多播簇的吞吐量，进而可以提高簇头的能量效率和系统的频谱效率。

![](images/1f94a05663b070882d5b479e6d185b7787f89a2be9378ec9753596e7ce20e039.jpg)  
图1D2D多播通信系统

在图1所示的系统中存在大量的潜在服务用户，若将这部分潜在服务用户纳入到现有的D2D多播簇内进行视频分发，一方面系统的吞吐量及簇头的能量效率都会得到提高，另一方面合适的视频推送服务也会提升被推送用户的服务体验质量。但由于各个用户对视频兴趣的差异、用户设备能量及闲忙状态的限制，各个潜在服务用户对于接收视频推送表现出不同程度的意愿。本文所要解决的问题便是准确感知潜在服务用户的服务请求，并据此在为服务请求用户分发视频的同时向潜在服务用户推送视频，以实现系统吞吐量、簇头能量效率及系统频谱效率的提升。

# 2 用户需求感知

由于潜在服务用户接受视频内容推送会消耗用户设备的能量，占用设备的带宽，若用户设备的剩余能量不足或用户正在使用无线网络，则用户可能会不愿意接受系统为其推送视频。除了用户设备的状态信息，用户的主观意愿也是影响用户接受视频推送的重要因素，若用户对推送的视频内容不感兴趣，推送服务也就失去了意义，反而会严重降低用户体验质量。为了准确的感知用户的服务请求，提高用户的体验质量，这部分将根据以上要素对潜在服务用户接受视频推送的意愿进行分析和度量。

# 2.1视频请求概率

用户请求某个视频的概率主要由用户对该视频的兴趣度和该视频的流行度相关，以它们为参考要素计算用户的视频请求概率同时兼顾了视频的共性和用户的个性。

# 2.1.1用户兴趣度

用户访问视频内容的累计时长信息在一定程度上可以反映出用户的兴趣，用户对于某类视频内容越感兴趣其所累积的访

问时长就越长，因此用户对视频的感兴趣程度可以表示为

$$
p _ { i , k } = \frac { t _ { k } } { t _ { t o t a l } }
$$

$p _ { i , k }$ 是用户 $u _ { i }$ 对第 $k$ 类视频内容的兴趣度， $t _ { k }$ 是用户 $u _ { i }$ 访问第 $k$ 类视频内容的时长， $t _ { t o t a l }$ 是用户 $u _ { i }$ 访问所有视频内容的总时长。事实上，在网络中接受用户点播的视频有着不同的时长，有长达两三个小时的电影，也有几分钟的小视频。用户观看一次电影累计的访问时长可能比观看几十次小视频累计的时长都长，因此简单的使用访问时长所占总时长的比例来表征用户的兴趣度存在较大的误差。用户对于某类视频的请求次数占总的视频请求次数的比例可以在一定程度上反映用户请求该类视频的概率。在过去的一段时间 $T$ 内用户 $u _ { i }$ 请求第 $k$ 类视频内容的频次比率 $f _ { i , k }$ 为

$$
f _ { i , k } = \frac { s _ { k } } { S }
$$

其中： $s _ { k }$ 是用户 $u _ { i }$ 请求第 $k$ 类视频内容的次数， $s$ 是用户 $u _ { i }$ 请求所有视频内容的总次数。请求视频内容的频次信息在一定程度上反映了用户请求该类视频内容的概率，而访问时长信息则反映了用户对该类视频的兴趣深度。此外，由于用户在上网的过程中可能会发生误触，这些误触所累计的历史信息会对兴趣度计算产生误导，因此在计算时需要滤除这部分信息。因此，用户 $u _ { i }$ 对于第 $k$ 类视频内容的兴趣度 $P _ { i , k } ^ { \mathrm { i n t e r e s t } }$ 可以表示为

$$
P _ { i , k } ^ { \mathrm { i n t e r e s t } } = \delta \frac { s _ { k } } { S } + ( 1 - \delta ) \frac { \sum _ { j = 1 } ^ { s _ { k } } t _ { i , k } ^ { j } } { t _ { t o t a l } }
$$

其中： $\boldsymbol { \delta }$ 是权重系数， $t _ { i , k } ^ { j }$ 是用户 $i$ 第 $j$ 次访问视频内容 $k$ 的时长，式(4)中的每一条访问记录都应满足条件 $t _ { i , k } ^ { j } > t _ { t h }$ ， $t _ { { t } _ { t h } }$ 是误触判断阈值。即当某次访问视频内容的时长小于或者等于该阈值时视该次访问是用户误触引起的，该次访问信息将不会考虑进兴趣度计算中。

# 2.1.2视频流行度

文献[14]通过追踪YouTube网站在不同地区的视频观看排名发现，虽然在不同地区视频的流行度有所不同，但在特定的区域内视频的流行度非常符合Zipf分布。假设 $F$ 是在过去一段时间 $T$ 内该小区请求的所有视频的集合， $\mid F \mid$ 是视频的数量，因此排名为 $l$ 的视频 $f _ { l }$ 的流行度可以表示为

$$
P _ { l } ^ { p o p } = \frac { l ^ { - \gamma } } { \sum _ { c = 1 } ^ { | F | } c ^ { - \gamma } } , 1 \le l \le \mid F \mid
$$

其中： $P _ { l } ^ { p o p }$ 即排名为 $\mathbf { \xi } _ { l }$ 视频的流行度， $\gamma$ 是该区域内的Zipf分布指数。对于用户来说，其请求某个视频内容的概率主要由用户对该视频的兴趣度和该视频的流行度所决定。对于服务请求用户请求的视频 $f _ { l }$ ，假设其所属的分类为 $k$ ，则潜在服务用户$u _ { p i }$ 对视频 $f _ { l }$ 的兴趣度 $P _ { p i , l } ^ { i n t e r e s t }$ 可以根据其所属分类由式(4)计算得出。因此潜在服务用户 $u _ { p i }$ 在未来会请求视频 $f _ { l }$ 的概率可以表示为

$$
\begin{array} { l } { \displaystyle P _ { p i , l } ^ { r e q u e s t } = \alpha P _ { l } ^ { p o p } + \beta P _ { p i , l } ^ { i n t e r e s t } } \\ { = \alpha \frac { l ^ { - \gamma } } { \sum _ { c = 1 } ^ { | F | } c ^ { - \gamma } } + \beta \left[ \delta \frac { S _ { k } } { S } + ( 1 - \delta ) \frac { \sum _ { j = 1 } ^ { s _ { k } } t _ { p i , k } ^ { j } } { t _ { t o t a l } } \right] } \end{array}
$$

其中： $\alpha$ 和 $\beta$ 分别为视频流行度和用户兴趣度的权重系数， $k$ （204号为视频 $f _ { l }$ 的分类序号， $P _ { p i , l } ^ { i n t e r e s t } \in [ 0 , 1 ]$ ，且上式需满足条件$t _ { p i , k } ^ { j } > t _ { t h }$ 和 $1 \leq l \leq \mid F \mid$ 。

# 2.2用户接受视频推送的意愿

在终端接收视频文件的过程中设备需要消耗一定的能量，不同于发射端，接收端的能量消耗主要源自于自身的电路损耗。根据文献[15]提出的无线信道能量模型，接收 $n$ 位数据接收端所需要消耗的能量为

$$
E _ { r } ( n ) = n E _ { e l e c }
$$

其中： $E _ { e l e c }$ 是电路损耗常量。设潜在服务用户 $\boldsymbol { u } _ { p i }$ 设备可存储的总能量为 $E _ { p i }$ ，设备目前的剩余能量为 $E _ { p i } ^ { s }$ ，需要接收的视频 $f _ { l }$ （204号的文件大小为 $n _ { \scriptscriptstyle { l } }$ bit，为了保障用户的QoE，完成视频接收之后潜在服务用户 $u _ { p i }$ 设备的剩余能量比值 $\varphi _ { p i }$ 应大于阈值 $\varphi _ { t h }$ ，即

$$
\varphi _ { p i } = \frac { E _ { p i } ^ { s } - n _ { l } E _ { e l e c } } { E _ { p i } } > \varphi _ { t h }
$$

若潜在服务用户接收视频推送后其剩余能量比值低于最低阈值，则潜在用户会不愿意接受视频推送服务。因此定义最低剩余能量系数 $\mathbf { \Psi } _ { c }$ 为

$$
c = \left\{ { \begin{array} { l l } { 1 } & { \varphi _ { p i } > \varphi _ { t h } } \\ { 0 } & { \varphi _ { p i } \le \varphi _ { t h } } \end{array} } \right.
$$

综上所述，当簇头节点试图通过向潜在服务用户 $u _ { p i }$ 推送视频 $f _ { l }$ 来增加吞吐量时，用户 $u _ { p i }$ 接受推送视频的意愿 $P _ { p i , l } ^ { a c c e p t }$ 可以表示为如下形式：

$$
P _ { p i , l } ^ { a c c e p t } = c P _ { p i , l } ^ { r e q u e s t } = \left\{ \begin{array} { l l } { \alpha P _ { l } ^ { p o p } + \beta P _ { p i , l } ^ { i n t e r e s t } } & { \varphi _ { p i } > \varphi _ { t h } } \\ { 0 } & { \varphi _ { p i } \le \varphi _ { t h } } \end{array} \right.
$$

# 3 最优化簇头能量效率问题建模

在这部分将会提出视频分发服务效用值度量对视频分发服务的价值进行衡量，该度量的计算中考虑了系统中D2D通信的信道质量信息及潜在服务用户接受视频推送的意愿信息。然后为了优化簇头的能量效率，将会对最优化簇头能量效率问题进行建模分析。

# 3.1视频分发服务效用

如第一部分所述，假设系统中存在 $\mathbf { \Sigma } _ { m }$ 个服务请求用户（204号 $U _ { s } = \{ u _ { s 1 } , u _ { s 2 } , . . . , u _ { s m } \}$ ， $n$ 个潜在服务用户 $U _ { _ P } = \{ u _ { _ { p 1 } } , u _ { _ { p 2 } } , . . . , u _ { _ { p n } } \}$ ，以及与该 D2D 多播簇复用相同频谱资源的蜂窝用户 $u _ { c }$ 。D2D链路复用蜂窝上行链路，因此当蜂窝用户 $u _ { c }$ 向基站发射信号时会对D2D多播通信造成同频干扰。信道模型考虑路径衰落和瑞利衰落，每条信道都服从独立的瑞利衰落，且均值为 $1 ^ { [ 1 6 ] }$ 。当簇头和蜂窝用户分别以功率 $P _ { h }$ 和 $P _ { c }$ 发射信号时，D2D多播接收用户 $u _ { i }$ 的接收信号干扰噪声比为

$$
S I N R _ { i } = \frac { P _ { h } d _ { h , i } ^ { - \alpha } h _ { 0 } } { P _ { c } ^ { d } d _ { c , i } ^ { - \alpha } h _ { 0 } + \sigma ^ { 2 } }
$$

其中： $\boldsymbol { d } _ { h , i }$ 和 $d _ { c , i }$ 分别是簇头 $\boldsymbol { u } _ { h }$ 和蜂窝用户 $u _ { c }$ 与D2D 接收用户$u _ { i }$ 间的距离， $\alpha$ 是路径衰落因子， $h _ { 0 }$ 是高斯信道系数常数， $\sigma ^ { 2 }$ 是均值为0的高斯白噪声。设 $\mathbf { \Omega } _ { L }$ 是D2D多播簇纳入潜在服务用户之后的簇内成员列表，即

$$
L = U _ { s } \cup U _ { P S }
$$

其中： $U _ { \scriptscriptstyle P S } \subset U _ { \scriptscriptstyle P }$ ， $U _ { \scriptscriptstyle P S }$ 是被纳入簇内的潜在服务用户的集合，$\vert U _ { P S } \vert$ 是集合的成员数量。设 $S I N R _ { \operatorname* { m i n } }$ 是集合 $\mathbf { \Omega } _ { L }$ 中所有用户中信道质量最差的用户的接收信号干扰噪声比，信道带宽为 $B$ ，由于D2D多播通信信道容量受到最差信道用户限制，因此根据式（1）可知，D2D多播簇总的信道容量为

$$
C _ { t o t a l } = B \big ( m + | U _ { P S } | \big ) \log _ { 2 } ( 1 + S I N R _ { \operatorname* { m i n } } )
$$

由于潜在服务用户接受视频推送的意愿各不相同，系统难以保证推送的内容一定是潜在服务用户所期望的。D2D多播簇总的信道容量就是该簇簇头所能达到的最大吞吐量，而潜在服务用户只会以一定的概率对所传输的信息有接收意愿，即对于潜在服务用户来说视频推送内容有一定的概率是做的无用功。针对这个问题，视频分发服务效用值度量 $C _ { t o t a l } ^ { e }$ 被提出来对视频分发服务的价值进行衡量，其值与潜在服务用户对视频内容 $f _ { l }$ （204号接受意愿和簇内信道最差信号干扰噪声比 $S I N R _ { \operatorname* { m i n } }$ 有关，计量单位为Mbps。对于服务请求用户来说接受意愿为1，而潜在服务用户的接受意愿为 $P _ { p i , l } ^ { a c c e p t }$ ，因此根据式（13）视频分发服务效用值可以表示为

$$
C _ { t o t a l } ^ { e } = B \bigg ( m + \sum _ { u _ { p i } \in U _ { P S } } P _ { p i , l } ^ { a c c e p t } \bigg ) \mathrm { l o g } _ { 2 } \left( 1 + S I N R _ { \mathrm { m i n } } \right)
$$

其中 $B$ 是所分配的信道带宽。

# 3.2簇头的能量效率

在3.1中推算出了D2D多播簇的视频分发服务效用值的表达式，因此簇头的能量效率 $\eta$ 可以表示为

$$
\eta = \frac { C _ { t o t a l } ^ { e } } { P _ { h } } = \frac { B \bigg ( m + \sum _ { { \boldsymbol u } _ { p i } \in U _ { P S } } P _ { p i , l } ^ { a c c e p t } \bigg ) \log _ { 2 } \big ( 1 + S I N R _ { \operatorname* { m i n } } \big ) } { P _ { h } }
$$

对于由服务请求用户构成的D2D多播簇来说，纳入潜在服务用户进行视频内容分发，其数据传输速率将会受簇头与潜在服务用户的信道质量影响。而在该内容分发系统中，服务请求用户的优先级高于潜在服务用户的优先级。因此，为了保障服务请求用户的QoE，纳入潜在服务用户后的多播传输速率应大于服务请求用户可容忍最低传输速率。换句话说，潜在服务用户 $u _ { p i }$ 与簇头间信道质量应不小于最低信道质量阈值，即$S I N R _ { _ { p i } } \geq S I N R _ { _ { t h } }$ 。另一方面，为了保障潜在服务用户的QoE，纳入簇内的潜在服务用户 $\boldsymbol { u } _ { { p i } }$ 其接受视频 $f _ { l }$ 推送的意愿也应大于最低意愿阈值，即 $P _ { p i , l } ^ { a c c e p t } \geq P _ { t h } ^ { a c c e p t }$ 。

潜在服务用户集合 $U _ { \scriptscriptstyle P S }$ 的选择会直接影响多播簇内信道的$S I N R _ { \operatorname* { m i n } }$ 以及D2D多播接收用户数量，进而影响簇头的能量效率 $\eta$ 。因此，为了最优化簇头的能量效率，建立问题

$$
\boxed { \begin{array} { r l } & { \operatorname* { m a x } \ \eta = \overline { { B \Bigl ( m + \sum _ { u _ { p } \in U _ { N } } P _ { p _ { i } , i } ^ { a c e q u } \Bigr ) \log _ { 2 } \bigl ( 1 + S I N R _ { \mathrm { m i n } } \bigr ) } } } \\ & { S t . \ U _ { P S } \subset U _ { P } } \\ & { \ S I N R _ { p i } \geq S I N R _ { t i } , \ \forall u _ { p i } \in U _ { P S } } \\ & { \ P _ { p i , i } ^ { a c e q u } \geq P _ { i h } ^ { a c e q u } , \forall u _ { p i } \in U _ { P S } } \\ & { S I N R _ { \mathrm { m i n } } = \operatorname* { m i n } _ { u _ { e } \in L } \left\{ S I N R _ { i } \right\} } \end{array} }
$$

其中： $L = U _ { s } \cup U _ { P S }$ ， $S I N R _ { \operatorname* { m i n } }$ 是纳入潜在服务用户后D2D多播簇内信道质量最差的用户的接收信号干扰噪声比。

# 4 用户需求感知的D2D内容分发机制

在潜在服务用户纳入D2D多播簇内之前，簇内成员全部都是服务请求用户，服务请求用户集为 $U _ { s }$ ，待选择的潜在服务用户集为 $U _ { \scriptscriptstyle P }$ 。簇头向其D2D 可达传输半径内所有的潜在服务用户广播视频 $f _ { l }$ 的属性信息，潜在服务用户设备根据设备能量、视频相关信息和用户的历史浏览信息计算出接收视频推送的意愿，然后将意愿信息及接收信号干扰噪声比反馈给簇头，以便于簇头根据潜在服务用户意愿及信道质量信息制定合适的视频分发方案。

从式（13）（14）不难看出，对于一个确定的系统来说，其吞吐量的大小主要由所选的潜在服务用户集合中成员数量$| U _ { P S } |$ 和所有D2D 多播接收用户中最差信号干扰噪声比$S I N R _ { \operatorname* { m i n } }$ 所决定。扩大集合 $U _ { \scriptscriptstyle P S }$ 可以使多播接收用户数量上升，但也可能导致 $S I N R _ { \operatorname* { m i n } }$ 下降。因此，最优化簇头能量效率的关键问题便是选择一个合适的潜在服务用户集合Ups。

待选择集合 $\boldsymbol { U } _ { P }$ 中所有的潜在服务用户可以分为三类。第一类是信道质量优于服务请求用户中信道质量最差者，并且意愿满足最低阈值要求的潜在服务用户，用集合 $\smash { \boldsymbol { U } _ { P _ { P } } ^ { 1 } }$ 表示；第二类是信道质量差于服务请求用户中信道质量最差者，但接受视频推送的意愿和信道质量均满足最低阈值要求的潜在服务用户，用集合 $\boldsymbol { U } _ { P } ^ { 2 }$ 表示；余下的用户为第三类，用集合 $\smash { U _ { P } ^ { 3 } }$ 表示。由于服务请求用户的优先级高于潜在服务用户，第一类潜在服务用户纳入D2D多播簇内只会给系统带来增益，而不会对系统传输速率和吞吐量产生减益影响。第三类潜在服务用户加入D2D多播簇会严重损害服务请求用户的体验，因此不予考虑第三类用户。

综上所述，为了选出合适的潜在服务用户集合 $U _ { P S }$ ，本文提出了最优化簇头能效的潜在服务用户选择算法，算法的具体实现步骤如下。

a)遍历待选择潜在服务用户集 $\boldsymbol { U } _ { P }$ ， $\forall u _ { p i } \in U _ { p }$ ，若满足（204 $P _ { p i , l } ^ { a c c e p t } \geq P _ { t h } ^ { a c c e p t }$ 且 $S I N R _ { p i } \geq \operatorname* { m i n } _ { u _ { s i } \in U _ { S } } \left\{ S I N R _ { s i } \right\}$ ，则将该用户纳入集合（204号 $\boldsymbol { U } _ { \ P } ^ { 1 }$ ；若满足 $P _ { p i , l } ^ { a c c e p t } \geq P _ { t h } ^ { a c c e p t }$ ， $S I N R _ { p i } < \operatorname* { m i n } _ { u _ { s i } \in U _ { S } } \left\{ S I N R _ { s i } \right\}$ 且$S I N R _ { _ { p i } } \geq S I N R _ { _ { t h } }$ ，则将该用户纳入集合 $\smash { U _ { P } ^ { 2 } }$ ；若以上条件均不满足，则将该用户纳入集合 $\smash { U _ { P } ^ { 3 } }$ 。

b)根据用户的接受信号干扰噪声比 $S I N R _ { p i }$ ，对集合 $\smash { U _ { P } ^ { 2 } }$ 中的用户按从大到小的顺序排序。

c)初始化循环变量 $x = 1$ ，最大能量效率 $\eta _ { { } _ { m } } = 0$ ，用户集合$\begin{array} { r } { U _ { P } ^ { m } = \emptyset } \end{array}$ 。

d)将集合 $\smash { U _ { P } ^ { 2 } }$ 中的前 $x$ 个用户选出并构成用户集合 $U _ { p } ^ { 2 x }$ ,根据式(17)计算该方案的簇头能量效率nx。

$$
\begin{array} { r } { \eta _ { x } = \frac { B \Big ( m + \sum _ { u _ { p i } \in U _ { p } ^ { 1 } } P _ { p i , l } ^ { a c e p t } \Big ) \log _ { 2 } \left( 1 + \underset { u _ { p i } \in U _ { p } ^ { 2 s } } { \operatorname* { m i n } } \left\{ S I N R _ { p i } \right\} \right) } { P _ { h } } } \\ { + \frac { B \Big ( \sum _ { u _ { p i } \in U _ { p } ^ { 2 s } } P _ { p i , l } ^ { a c e p t } \Big ) \log _ { 2 } \left( 1 + \underset { u _ { p i } \in U _ { p } ^ { 2 s } } { \operatorname* { m i n } } \left\{ S I N R _ { p i } \right\} \right) } { P _ { h } } } \end{array}
$$

e)若 $\eta _ { x } > \eta _ { m }$ ，则 $\eta _ { { \scriptscriptstyle m } } = \eta _ { { \scriptscriptstyle x } }$ ， $\boldsymbol { U } _ { P } ^ { m } = \boldsymbol { U } _ { P } ^ { 2 x }$ 。

f)循环变量 $x$ 的值加1。若 $x > \mid U _ { P } ^ { 2 } \mid$ ，进入下一步；否则， 跳至步骤d)继续执行。

g)使得簇头能量效率最大化的潜在服务用户选择方案为$U _ { P S } = U _ { P } ^ { 1 } \bigcup U _ { P } ^ { m }$ ，簇头最优的能量效率即 $\eta _ { { \scriptscriptstyle m } }$ 。

利用D2D多播吞吐量与多播接收用户数量在一定情况下成正比的特征，本文所提出的用户需求感知的D2D多播视频分发机制通过增大D2D多播接收用户数量的方式提升簇头的能量效率及系统的资源利用效率。通过对潜在服务用户的需求进行感知，在获得了潜在服务用户的接受视频推送服务的意愿之后，利用上述算法可以选出使簇头能量效率最优化的潜在服务用户选择方案 $U _ { \scriptscriptstyle P S }$ 。将所选出的集合 $U _ { \scriptscriptstyle P S }$ 中的潜在服务用户纳入 D2D 多播簇后，簇内的多播接收用户集合为L=UsUUps，此时簇头通过D2D多播分发视频内容可以使簇头的能量效率最大化，相应地系统的频谱效率也得以优化。

# 5 仿真分析

本部分通过MATLAB对本文所提出的D2D多播视频分发机制的传输速率及视频分发服务效用值性能进行仿真分析，主要对比了三种分发方案。方案1即文献[10]所提出的社会关系感知的D2D文件共享机制，该方案分簇及簇头选择时考虑了用户之间的社会关系强度的影响；方案2是文献[9]所提出的考虑干扰感知的D2D文件分发机制，该方案主要考虑了信道质量的影响；方案3即本文所提出的用户需求感知的D2D多播视频分发机制。

主要的仿真参数设置如表1所示。

现有的研究中主要考虑两类信息：用户属性信息，如用户兴趣、社交关系和用户行为等信息；通信系统物理信息，如信道质量、设备存储空间和剩余能量等。方案1和方案2分别属于上述两类中的典型方案，而本文所提的方案3为了在提升吞吐量等性能的同时保障用户体验质量，同时考虑了上述两类信息，如用户需求和接收信干噪比等。此外，从本质上讲三种方案提升系统吞吐量等性能的基本原理相同，都是以增大簇内接收成员数量的方式来实现。因此，本文选择方案1和2作为本文所提出的方案3的对比实验方案。

表1主要仿真参数  

<html><body><table><tr><td>参数</td><td>取值</td></tr><tr><td>小区半径</td><td>500m</td></tr><tr><td>信道带宽</td><td>180KHz</td></tr><tr><td>路径损耗系数α</td><td>4</td></tr><tr><td>高斯白噪声</td><td>-174dBm/Hz</td></tr><tr><td>电路损耗常量Eelec</td><td>50nJ/bit</td></tr><tr><td>D2D多播簇头传输功率Ph</td><td>23dBm</td></tr><tr><td>蜂窝用户传输功率Pc</td><td>46dBm</td></tr><tr><td>服务请求用户可接受最差 SINR 阈值</td><td>18dB</td></tr><tr><td>服务请求用户占总用户的数量比例</td><td>[0.1,0.5]</td></tr><tr><td>总用户数量</td><td>[100,200]</td></tr></table></body></html>

本文所提的用户需求感知的D2D多播视频分发机制，通过对潜在服务用户接受视频推送的意愿进行估算，在为服务请求用户分发视频的同时向潜在服务用户推送视频，通过增加D2D多播接收用户的方式提高系统的吞吐量，进而提高簇头的能量效率及系统资源的利用效率。如图2和3所示，本文所提的视频分发机制其视频分发服务效用值和传输速率的表现远远优于对比方案。换句话说，本文所提出的视频分发机制相较于对比方案传输速率、系统吞吐量及簇头的能量效率都有很大的提升。

从图2可以看出，随着用户总数的不断增加，三种方案的视频分发服务效用值都在不断上升，其中用户需求感知的分发机制的增幅较为明显。考虑用户需求感知的分发机制性能上的优势主要来源于潜在服务用户，这也是服务请求用户占总用户数量比值上升时没有考虑用户需求感知的对比方案的视频分发服务效用值开始慢慢逼近用户需求感知的分发机制的原因。此外，由于干扰感知的分发机制和用户需求感知的分发机制都受到SINR阈值的影响，当SINR阈值上升时两种方案的多播接收用户数量下降，视频分发服务效用值也相应的开始出现不同程度的下滑。但总的来说，本文所提的用户需求感知的D2D多播视频分发机制在视频分发服务效用值性能上始终要优于对比方案。

从图3可以看出，干扰感知的分发机制和用户需求感知的分发机制的传输速率要远高于社会关系感知的分发机制。这是因为社会关系感知的分发机制只考虑了传输链路的稳定性但忽视了最差链路对多播传输速率的影响，而干扰感知的分发机制和用户需求感知的分发机制都有SINR 阈值的约束，使得它们能在变化的环境中保证链路的传输速率。由于D2D多播通信的传输速率受到链路质量最差用户的影响，因此当用户数量上升时多播接收用户最差链路质量逐渐变差，三种方案的传输速率于是也不断下降。由于干扰感知的分发机制和用户需求感知的分发机制使用了同样的SINR约束条件，因此两种机制的传输速率几乎相等，后者略低于前者。随着 SINR阈值的提升，干扰感知的分发机制和用户需求感知的分发机制的传输速率迅速提升。

(1) (2) 3  
80 社会关系感知 L 45 社会关系感知l 用感知 40F 用感知△20中 中 中 中 中  
3015 0中中 ee 0  
10100110120130 140 150160170180190200 0. 1 0.15 0.2 0.25 0.3 0.35 0. 4 0. 45 0.5 18 20 22 24 26 28 30 32 34总用户数量(个) 服务请求用户数量与总用户数量的比值 SINR阈值(dB)

![](images/bc6666e4d833de85dc21fb4dd480f57a932ae40fc72793b9e77823eccbee6906.jpg)  
图2视频分发服务效用值随环境的变化

图3传输速率随环境的变化

综上所述，由于D2D多播传输速率受限于信道质量最差的用户，扩大多播接收用户集合可能会导致传输速率迅速下降。相较于传统的D2D多播内容分发机制，本文所提的用户需求感知的D2D视频分发机制在保证传输速率的前提下，视频分发服务效用值性能有着明显的提高，簇头的能量效率和系统的资源利用效率有着明显的改善。

# 6 结束语

本文提出了一种新的D2D多播视频分发机制，在为服务请求用户分发视频的同时将视频推送给附近在未来有相似需求的用户，通过增加多播接收用户数量的方式提高系统的吞吐量，进而提高簇头的能量效率和系统的资源利用效率。为了衡量潜在服务用户接受视频推送服务的意愿，本文充分考虑了推送视频的流行度、用户的兴趣度以及用户设备的剩余能量等因素，并提出了视频分发服务效用值度量来衡量视频分发服务的价值。然后本文根据潜在服务用户接受视频推送的意愿和视频分发服务效用值度量，提出了最优化簇头能量效率的潜在服务用户选择算法。仿真结果表明，本文提出的D2D多播视频分发机制相较于传统的D2D多播分发机制在吞吐量和簇头能量效率上有着明显的优势。本文只考虑了服务请求用户优先级高于潜在服务用户的场景，未来将研究将服务请求用户与潜在服务用户作为同一优先级进行分簇及簇头选择问题，系统吞吐量及资源利用效率还有进一步提升的空间。

# 参考文献：

[1]Cisco.Cisco visual networking index:global mobile data traffic forecas'

update，2016-2021．[EB/OL].(2017-02-07）．htps://www.cisco. com/c/en/us/solutions/collateral/service-provider/visual-networking-indexvni/mobile-white-paper-c11-520862.html.   
[2]Shen Xuemin.Device-to-device communication in 5G celllar networks [J]. IEEE Network,2015,29(2): 2-3.   
[3]Lin Xingqin,Andrews JG,Ghosh A,et al.An overview of 3GPP device-todevice proximity services [J].IEEE Communications Magazine,2013,52 (4): 40-48.   
[4]Peng Bo,Peng Tao,Liu Ziyang,et al. Cluster-based multicast transmission for device-to-device (D2D) communication [C]//Proc of IEEE Vehicular Technology Conference.2014:1-5.   
[5]Wu Dapeng,Yan Junjie,Wang Honggang,et al. Social attribute aware incentive mechanism for device-to-device video distribution[J].IEEE Trans on Multimedia,2017,19(8):1908-1920.   
[6]Cao Yang,Jiang Tao,Chen Xu,et al. Social-aware video multicast based on device-to-device communications [J]. IEEE Trans on Mobile Computing, 2016,15 (6): 1528-1539.   
[7] 江帆，申斌艳，李晨碧，等.提高 D2D 多播能效的一种方案[J].西安 邮电大学学报,2017,22(1):12-17.   
[8] Zhang Zufan,Luo Lisha,Wang Lisha.D2D multicast retransmission algorithm in mobile cloud based on SINR constraint [J].China Communications,2016,13 (8): 41-52.   
[9]Kitagawa K,Homma H, Suegara Y,et al.A user selection algorithm for D2D multicast communication underlaying cellular systems $[ \mathrm { C } ] / \hbar$ Proc of IEEE Wireless Communications and Networking Conference.2017:1-6.

[10] Wang Lei,Gao Lulu,Zhang Aiqing，et al.Social-aware file-sharing

mechanism for device-to-device communications $[ \mathrm { C } ] / \AA$ Proc of International Conference on Wireless Communications & Signal Processing.2O15:1-5.   
[11] Zhang Xiangyang,WangYing,Sun Ruijin,et al.Clustered device-to-device caching based on file preferences [C]//Proc of IEEE,International Symposium on Personal, Indoor,and Mobile Radio Communications.2016: 1-6.   
[12] JiangLi,Tian Hui,Xing Zi,et al. Social-aware energy harvesting device-todevice communications in 5G networks [J].IEEE Wireless Communications, 2016,23 (4):20-27.   
[13] Zhao Pan,Feng Lei,Yu Peng,et al.Resource allocation for energy-efficient device-to-device multicast communication [C]// Proc of International Symposium on Wireless Personal Multimedia Communications.2016:518- 213.   
[14]Wang Yali,Li Yujin,Wang Wenye,et al.A locality-based mobile caching policy for D2D-based content sharing network[C]//Proc of IEEE Global Communications Conference.2016:1-6.   
[15]Heinzelman W B,Chandrakasan A P,Balakrishnan H.An applicationspecific protocol architecture for wireless microsensor networks [J].IEEE Trans on Wireless Communications,2002,1(4):660-670.   
[16]王汝言；缪懿；闫俊杰．一种结合威望的 D2D 通信中继选择算法[J]. 西安电子科技大学学报,2018,45(1):76-82.