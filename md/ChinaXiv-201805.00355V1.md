# 毫米波5G网络中一种D2D通信的资源分配方案

文凯1,²，陈永丽1，郑文倩1，颜飙1(1.重庆邮电大学 通信新技术应用研究中心，重庆 400065;2.重庆信科设计有限公司，重庆 401121)

摘要：在5G系统中，毫米波（mmWave）与终端直通技术（device-to-device，D2D）有利于提升系统容量和频谱利用率。针对 $7 3 \mathrm { G H z }$ 下underlay蜂窝网络中的D2D资源分配进行了研究。为了降低彼此间的干扰，首先提出对基站和D2D 用户接收机进行区域限制；其次利用线性相关的方法选出可复用的蜂窝用户；最后在满足蜂窝通信和D2D通信服务质量（QoS）的要求下提出一种基于干扰控制的资源分配，以提升系统的吞吐量。仿真结果表明所提算法的性能优于参考算法。该算法能够有效提升系统吞吐量和频谱效率。

关键词：毫米波；终端直通技术；资源分配；吞吐量；干扰中图分类号：TN929.5 doi:10.3969/j.issn.1001-3695.2017.10.0953

# Resource allocation scheme for D2D communication in mmWave 5G networks

Wen Kai1,², Chen Yongli1, Zheng Wenqian1, Yan Biaol (1.Research CenterofNewTelecommunicationTechnologyAppications,Chongqing UniversityofPosts&Telecommunications, Chongqng 400065,China;2 Chongqing Information Technology Designing Co.Ltd,Chongqing 401121,China)

Abstract: In the5G system,milimeter wave (mmWave)and device to device(D2D)communication is beneficial to improve thesystem capacityand spectrumutilization.This paper studiedtheresource alocation forD2D in underlaycelular networks at $7 3 ~ \mathrm { G H z }$ . In order to reduce the interference between each other,firstly,this paper proposed the regional restrictions on the basestationandD2Dreceiver.Then,itused themethodoflinearcorelationtoselectreusablecellularusers.Finalyinorder to improve thesystemthroughput,itproposedaresourcealocationbasedoninterferencecontrolundermetingtherequirements of quality ofservice (QoS)of celular communication and D2D communication.The simulation results show that the proposed algorithmoutperforms thereference algorithm.The algorithmcan effectivelyimprove the system throughput and spectrum efficiency.

Key Words:millimeter wave; D2D; resource allocation; throughput; interference

# 0 引言

近些年来，随着智能终端如手机、平板电脑等的盛行，促使移动数据流量快速的上升，目前的可用频段日渐紧张，因此，为了满足人们日益增长的终端多样化的业务需求，无线网络的频谱利用率和吞吐量则需要大幅度提高，而目前能够大幅度提高数据传输速率的5G通信技术成为研究的热点，其中引起业界最为关注的5G 技术为毫米波和D2D 通信等[1]。

毫米波属于甚高频段！ $( 3 0 { \sim } 3 0 0 \mathrm { G H z }$ ），此波段频谱资源十分丰富，有大量连续的频谱，如 $2 8 ~ \mathrm { G H z }$ 、 $6 0 ~ \mathrm { G H z }$ 、 $3 8 ~ \mathrm { G H z }$ 和E带宽（ $, 7 1 { \sim } 7 6 ~ \mathrm { G H z }$ 和 $7 7 { \sim } 8 1 ~ \mathrm { G H z }$ ）等，可以有效缓解频谱资源紧张的现实状况[2]。毫米波具有单跳通信距离较短、干扰源少、可提供千兆位的通信服务、能够大幅提升系统容量和传输速率等优点。但是大的路径损耗、大气吸收和雨水衰减等不利的信道特性使得服务范围减少，但是最近大量研究结果表明毫米波可以应用于街道，车站等室外场景[3,4]。

D2D（device-to-device）通信技术又称终端直通技术，它可以在基站的控制下，对设备与设备之间进行直接通信，并且不需要基站来转发[5]。将D2D通信技术应用于蜂窝网络中有以下优势：可以增加通信系统容量，提高系统频谱效率，提升数据传输速率，降低基站负载等。在基站的控制下，D2D通信技术可以以正交模式使用小区资源或者以非正交模式(复用模式)复用小区资源进行通信，目前多是在复用模式下进行D2D通信的研究[。复用模式下会产生严重的干扰从而影响系统性能，那么在保证蜂窝用户和D2D用户的服务质量的情况下，如何进行资源分配才能使干扰减少成为D2D通信的研究重点，因此，大量的研究已经专注于此并进行了讨论和研究。

为了降低D2D通信给蜂窝通信带来的干扰，资源复用方案显得尤为重要。文献[7]对D2D用户接收机进行干扰限制以保证D2D用户的通信质量，并提出一种基于D2D和基站距离的功率控制策略。文献[8]提出一种基于干扰控制的D2D 通信联合资源分配方案，能够提升系统吞吐量，但是一个蜂窝用户资源只能被一个D2D用户复用，不能使频谱资源得到很好地利用。文献[9]研究了基于干扰受限区域的功率控制方案来缓解混合蜂窝网络中所带来的干扰，提出了一种基于“DT最大/最小功率”标准的干扰控制机制的新的资源分配方案，但是D2D用户的QoS不能得到很好的保证，且只是根据距离对蜂窝用户进行简单的选择，干扰水平降低有限。

为了保证用户的QoS，一些文献对其进行了研究。文献[10]将信道分配问题作为一个混合整数非线性规划，并提出了基于贪婪的启发式算法，在保证所有的用户信干扰比（SINR）的要求下最大可能地提高总吞吐量。文献[11]根据蜂窝用户和D2D用户的信噪比（SNR）阈值，以及用户设备的最大发射功率求出D2D用户发射端的发射功率。文献[12]首先在确保蜂窝用户和D2D用户的QoS的条件下，根据线性规划选择出D2D对的接入集，以确保D2D通信的干扰不会影响到蜂窝通信；其次提出一种信道分配方案以最大化系统吞吐量。文献[10,11]虽然在一定程度上使QoS得到了保证，但是对系统吞吐量提升有限，而文献[12]虽能在QoS和系统吞吐量满足要求，但是没有进行干扰控制。

5G 网络中采用毫米波技术和D2D通信集成将获得高带宽和频谱效率的优势，使得D2D通信应用于毫米波蜂窝网络中也越来越受到关注[13]。文献[14]在 $2 8 ~ \mathrm { G H z }$ 带宽下进行资源分配，通过对干扰值的限制来提高系统吞吐量，但是不能很好的降低干扰。文献[15]主要研究在满足D2D用户的最小QoS条件下，使得优先最大化能效，提出一种基于蜂窝用户干扰阈值的自适应功率控制，但是此方法不能保证干扰问题得以解决。

本文主要研究在 $7 3 ~ \mathrm { G H z }$ 毫米波蜂窝网络中，解决如何对D2D用户分配蜂窝用户资源才能使系统吞吐量最大化的问题。具体方法是首先通过对基站和D2D用户接收机进行区域限制找出D2D用户集合；然后再利用线性相关的方法选出可复用的蜂窝用户；最后为了提升蜂窝系统的性能，在满足蜂窝通信和D2D 通信服务质量（QoS）的要求下提出一种基于干扰控制的资源分配，以提升系统的吞吐量。

# 1 系统模型

# 1.1场景描述

本文假设在D2D用户和蜂窝用户共存的5G城市蜂窝网络场景下，研究一个 $7 3 ~ \mathrm { G H z }$ 毫米波蜂窝网络中以复用的方式进行多对D2D用户对一个蜂窝用户资源进行复用的情况。在这种场景下，D2D用户和蜂窝用户之间会产生干扰，并且D2D 对之间的干扰也是不可忽略的。假设每个蜂窝用户被分配一个相互正交的RB，那么资源块的数量就是蜂窝用户的数量，记为$\mathsf { C } = \{ c = 1 , 2 , 3 . . . , N \}$ ，D2D对的数量记为 $\mathrm { D } / = \{ d = 1 , 2 , 3 . . . , M \}$ 。如图1所示，D2D用户DT1和DT2复用同一个蜂窝用户UT1时产生的干扰示意图。

![](images/e05454b2f8b077550ee00253ed0dc5f8371dacf1481e29a43e221e7bcb19cf9e.jpg)  
图1上行链路的underlay 单蜂窝网络模型

# 1.2传输模型

在毫米波中研究最多的带宽是28、38、60、71\~76和81\~86$\mathrm { G H z }$ ，结果表明这些带宽提供了高吞吐量、无线链路的高质量、大规模天线的调度和清晰的网络设计。

在 $7 3 \mathrm { G H z }$ 毫米波实际的户外传输条件下，文献[16]中收集了在纽约市实施的大规模的测量，并获得了详细的信道空间统计模型。在这种用户和障碍物密集的条件下视距传输是不切实际的。由于有角度信号加上不同的延迟等特点，路径损耗模型将视距（LOS）和非视距（NLOS）分离开，并结合每一部分相应的阴影衰落。故路径损耗PL模型的计算为$P L = P L _ { \mathit { L O S } } + P L _ { \mathit { N L O S } }$ 。对于距离 $d$ 有

$$
P L _ { \chi } ( d ) [ d B ] = \mu + 1 0 \alpha \log 1 0 [ d ( m ) ] + \varepsilon
$$

其中： $\varepsilon$ 为响应对数正态阴影，服从 $\mathrm { ~ { ~ N ~ } ~ } ( 0 , \sigma ^ { 2 } )$ ； $\mu$ 为路径损耗系数； $\alpha$ 为路径损耗指数。

则有D2D 链路的PL 模型为

$$
P L _ { 1 } = p _ { 1 } P L _ { L O S } + ( 1 - p _ { 1 } ) P L _ { N L O S }
$$

其他链路的PL模型为

$$
P L _ { 2 } = p _ { 2 } P L _ { L O S } + ( 1 - p _ { 2 } ) P L _ { N L O S }
$$

# 1.3问题描述

在毫米波户外网络设计中，目标是在满足蜂窝用户和D2D用户的SINR条件下使得蜂窝用户和D2D用户的总的数速率最大化。在本文中，蜂窝用户和D2D用户的 SINR， $r _ { c } , r _ { d }$ 分别为

$$
r _ { c } = \frac { p _ { c } H _ { c , B } } { \displaystyle \sum _ { d = 1 } ^ { M } \lambda _ { c , d } p _ { d } H _ { d , B } + N _ { c } } \ge r _ { c } ^ { t h } , c = 1 , 2 , . . . , N
$$

$$
r _ { d } = \frac { p _ { d } H _ { d , d } } { \displaystyle { \sum _ { c = 1 } ^ { N } \lambda _ { c , d } p _ { c } H _ { c , d } + \sum _ { c = 1 } ^ { N } \sum _ { d \in D \backslash \{ d \} } ^ { M } \lambda _ { c , d } p _ { d } H _ { d , d } + N _ { d } } } \ge r _ { d } ^ { t h } , d = 1 , 2 , . . . , M \left( 5 \right)
$$

其中： $p _ { c }$ 和 $p _ { d }$ 是蜂窝用户，D2D 对发射机的发送功率； $H _ { i , j }$ 是链路 $i \mathrm { - } j$ 的信道增益； $ { N _ { c } }$ 和 $N _ { d }$ 是高斯白噪声，都为 $N _ { 0 }$ ：$r _ { c } ^ { t h } , r _ { d } ^ { t h }$ 为蜂窝用户和 D2D 用户的 SINR 阈值； $\lambda _ { c , d } \ : , \ : \lambda _ { c , d } :$ 表示第 $d$ ， $\boldsymbol { d } ^ { \prime }$ 个D2D 对是否复用第 $\mid c \mid$ 个蜂窝用户资源， $\lambda _ { c , d } { = } 1$ 则表示复用， $\mathscr { \lambda } _ { c , d } = 0$ 则表示不复用。

由香农公式 $R = B \log _ { 2 } ( 1 + S I N R )$ 可得

$$
R _ { c } = B \log _ { 2 } ( 1 + r _ { c } )
$$

$$
R _ { d } = B \log _ { 2 } ( 1 + r _ { d } )
$$

其中： $B$ 为蜂窝用户信道资源的带宽。

则最大化问题可以表示为

$$
R = \operatorname* { m a x } \{ \sum _ { c = 1 } ^ { N } R _ { c } + \sum _ { d = 1 } ^ { M } R _ { d } \}
$$

s.t.

$$
r _ { c } > r _ { c } ^ { t h } \subset = 1 , 2 , . . . , \mathrm { N }
$$

$$
r _ { d } > r _ { d } ^ { t h } \ d \substack { = } 1 , 2 , . . . , \mathrm { M }
$$

$$
p _ { c } < p _ { c } ^ { \mathrm { m a x } } c { = } 1 , 2 , . . . , \mathrm { N }
$$

$$
p _ { d } < p _ { d } ^ { \mathrm { m a x } } d \substack { = } 1 , 2 , . . . , \mathrm { M }
$$

$$
\sum _ { c \in C } \lambda _ { c , d } \leq 1 , \forall d \in D
$$

$$
\sum _ { d \in D } \lambda _ { c , d } \leq q _ { c } , \forall c \in C
$$

其中： $p _ { c } ^ { \mathrm { m a x } }$ ， $p _ { d } ^ { \operatorname* { m a x } }$ 为蜂窝用户和 D2D 用户的最大发射功率。（8a）（8b）表示满足蜂窝用户和D2D用户的SINR要求的限制条件；（8c）（8d）限制蜂窝用户和D2D用户的发射功率；(8e)表示一个D2D用户只能和一个蜂窝用户共享资源；（8f)表示蜂窝用户 $\mathbf { \Psi } _ { c }$ 的资源可以被多个D2D用户复用，并且D2D用户个数最多为 $q _ { c }$ 个。

# 2 资源分配

# 2.1限制区域

由于D2D用户复用蜂窝用户的上行资源，所以一方面D2D用户的发射端D2Dtx离基站越近，对基站接收蜂窝用户UT的信号的干扰就越大；另一方面D2D用户和蜂窝用户使用同一资源时，蜂窝用户离D2D用户的接收端 D2Drx 越近，对其的干扰就越大。为了降低蜂窝通信和D2D通信之间互相的干扰，对D2D用户和蜂窝用户进行区域限制。如图2所示，D2D通信限制区域为以基站为圆心， $r _ { \mathrm { { l } } }$ 为半径的圆形区域。当基站根据D2D用户的位置判定其在D2D 通信限制区域内，则禁止D2D链路的建立。以D2D 接收机D2Drx为圆心， $r _ { 2 }$ 为半径的圆是蜂窝用户被限制复用区域。若蜂窝用户在此区域内，则其资源将不被复用。

![](images/efc5828c5ed9cc2a2412c63b6a64decea2848af9457c03062d01bed00049c94b.jpg)  
图2区域限制示意图

# 2.1.1D2D通信的限制区域

为了保证D2D用户对蜂窝通信的干扰在可接受的范围内，

对 D2D通信区域进行限制， $I _ { \mathrm { B } } ^ { \mathrm { t h } }$ 表示 BS 的干扰门限值，其应满足

$$
I _ { d , \mathrm { B } } \leq I _ { \mathrm { B } } ^ { \mathrm { t h } }
$$

其中： $I _ { d , { \mathbf { B } } }$ 为D2D发射端对BS 的干扰，可以表示为

$$
I _ { d , \mathrm { B } } = p _ { d } \times H _ { d , \mathrm { B } } = p _ { _ d } ^ { \operatorname* { m a x } } \times \mathrm { P L } _ { 0 } \times ( r _ { 1 } ) ^ { - \alpha }
$$

式（10)考虑干扰最大时的情况，其中： $H _ { i , j } = \operatorname { P L } _ { 0 } \times ( d ) ^ { - \alpha }$

$d$ 为 $i$ 到 $j$ 的距离； $\mathrm { P L } _ { 0 }$ 为路径损耗常数； $\alpha$ 为路径损耗指数；

$p _ { d } ^ { \operatorname* { m a x } }$ 为D2D用户的最大发射功率。将（10）代入式（9）可得D2D通信限制区域半径 $r _ { \mathrm { { i } } }$ ：

$$
r _ { 1 } = ( \frac { p _ { _ d } ^ { \operatorname* { m a x } } \times \mathrm { P L } _ { 0 } } { I _ { \mathrm { B } } ^ { \mathrm { t h } } } ) ^ { \frac { 1 } { \alpha } }
$$

2.1.2蜂窝用户的限制复用区域

为了保证D2D用户的通信质量，则需控制蜂窝用户对D2Drx 的干扰，并且D2Drx 的SINR必须大于门限 $r _ { d } ^ { \mathrm { t h } }$ ，出于D2D 通信采用最大发射功率 $p _ { d } ^ { \operatorname* { m a x } }$ ，所以 D2D 链路的 SINR 主要取决于来自蜂窝用户的干扰，还应限制D2Drx 的干扰值低于干扰门限 $\boldsymbol { I } _ { d } ^ { \mathrm { t h } }$ 。

首先，D2Drx 的 SINR 应大于门限值 $r _ { d } ^ { \mathrm { t h } }$ ，即

$$
r _ { d } = \frac { p _ { d } H _ { d , d } } { I _ { c , d } + N _ { 0 } } \ge r _ { d } ^ { \mathrm { { \ t h } } }
$$

其次，假如D2Drx正处于干扰最严重的情况，此时，所有使用相同上行资源的UT都出于以 $r _ { 2 }$ 为半径的圆周上，则有

$$
I _ { c , d } \leq I _ { d } ^ { \mathrm { t h } }
$$

其中： $I _ { c , d }$ 是蜂窝用户对D2Drx 的干扰。假设蜂窝用户UT 使用最大发射功率 $p _ { c } ^ { \mathrm { m a x } }$ ，则蜂窝用户对 D2Drx 的最大干扰 $I _ { { } _ { c , d } } ^ { \operatorname* { m a x } }$ 可以表示为

$$
I _ { c , d } ^ { \operatorname* { m a x } } = p _ { _ c } ^ { \operatorname* { m a x } } \times G _ { { c } , d } = p _ { _ c } ^ { \operatorname* { m a x } } \times \mathbf { P } \mathbf { L } _ { 0 } \times ( r _ { 2 } ) ^ { - \alpha }
$$

由式（12）可得

$$
I _ { d } ^ { \mathrm { t h } } = \frac { p _ { d } ^ { \operatorname* { m a x } } \times H _ { d , d } } { r _ { d } ^ { t h } } - N _ { 0 }
$$

将式（14）（15）代入式（13）可得

$$
r _ { 2 } = \left( \frac { r _ { d } ^ { \mathrm { t h } } \times \mathrm { P L } _ { 0 } \times p _ { c } ^ { \mathrm { m a x } } } { p _ { d } ^ { \mathrm { m a x } } \times H _ { d , d } - r _ { d } ^ { \mathrm { t h } } \times N _ { 0 } } \right) ^ { \frac { 1 } { \alpha } }
$$

# 2.2D2D用户可复用蜂窝用户集合

为了进一步提高频谱利用率，本文根据线性规划的相关方法来为D2D用户选择潜在的蜂窝用户。

如图2所示，引用文献[12]使用的线性规划的方法，在确保蜂窝用户和D2D用户QoS的情况下，确定D2D用户可复用的蜂窝用户集合。如果蜂窝用户 $\mathbf { \Psi } _ { c }$ 属于集合 $\Pi _ { d }$ ，则蜂窝用户和D2D用户应满足限制条件（8a）和（8b）。则限制条件可以写为

![](images/1a43ab076e8d082749424f73c672a09d621bd894c03eea5c4712a8b7285f693f.jpg)  
图3潜在复用对象的选择

由式（17）两个不等式可以求出图3中A，B两点的值：

$$
{ \bf A } = \{ x _ { A } ; y _ { A } \} = \left\{ \begin{array} { l } { { \displaystyle N _ { 0 } \frac { H _ { d , d } r _ { c } ^ { t h } + H _ { d , B } r _ { c } ^ { t h } r _ { d } ^ { t h } } { H _ { d , d } H _ { c , B } - r _ { c } ^ { t h } r _ { d } ^ { t h } H _ { c , d } H _ { d , B } } ; } } \\ { { \displaystyle \frac { H _ { c , d } r _ { c } ^ { t h } r _ { d } ^ { t h } + H _ { c , B } r _ { d } ^ { t h } } { H _ { d , d } H _ { c , B } - r _ { c } ^ { t h } r _ { d } ^ { t h } H _ { c , d } H _ { d , B } } } } \end{array} \right\}
$$

只有当存在交点A时D2D用户才有可复用的蜂窝用户资源。并且交点A要在图3中虚线和坐标所围成的区域内时，才能保证蜂窝用户和D2D用户的QoS。图3中的阴影区域为 $p _ { c }$ 和 $p _ { d }$ 的可行域。

只要蜂窝用户的信道增益满足式（18）蜂窝用户资源才可以被D2D用户共享。

$$
\{ x _ { A } ; y _ { A } \} \le ( p _ { c } ^ { \operatorname* { m a x } } ; p _ { d } ^ { \operatorname* { m a x } } )
$$

式（18）用来表明所有终端用户可用的传输功率，并且基站不大于最大值。

# 2.3基于干扰控制的资源分配

为了提高蜂窝系统的公平性，可以根据用户数据速率的大小，在可复用的蜂窝用户集合中来选择出D2D用户该复用哪个蜂窝用户资源，然后可以得出每个蜂窝用户的候选D2D用户的集合 $\Omega _ { c }$ 。

定义 $\lambda = [ N , M ]$ 是资源分配指示矩阵，也可表示为优化分配集合： $\lambda = \{ \lambda _ { 1 } , \lambda _ { 2 } , . . . , \lambda _ { N } \} \ \lambda _ { c } = \emptyset , c = 1 , 2 , . . . , \mathrm { N }$ 0

针对每一个在 $D$ 中的D2D对，计算 $R _ { c } + R _ { d }$ 。假设 $\boldsymbol { d } ^ { \prime } = \boldsymbol { \mathcal { O } }$ ，$\forall d ^ { ' } \neq d$ 。与蜂窝用户 $\mid c \mid$ 复用资源的 D2D 对中能达到 $\mathrm { H } =$ argmax $\{ R _ { c } + R _ { d } \}$ 的 D2D对则加入到集合 $\Omega _ { c }$ 中。由于多个D2D对复用同一个资源时，D2D对之间也会产生相互的干扰，并且D2D对基站总的干扰也要小于干扰阈值 $I _ { B } ^ { t h }$ ，所以 $\Omega _ { c }$ 确定以后，要确定一下蜂窝用户的SINR是否符合要求。

首先判断 $\sum _ { d \in \Omega _ { c } } I _ { d , B } \leq I _ { B } ^ { t h }$ 是否成立，若不成立，则将 $\Omega _ { c }$ 中对（204号基站的干扰影响最大的 D2D 对去掉，直到满足 $\sum _ { d \in \Omega _ { c } } I _ { d , B } \leq I _ { B } ^ { t h }$ ，并将去除的D2D对放入集合 $D ^ { * }$ 。其次确定 $\lambda$ 值，假如D2D对$d$ 可以复用蜂窝用户 $\mid c \mid$ 的资源，则 $\lambda _ { c , d } { = } 1$ ，否则 $\lambda _ { c , d } { = } 0$ 。 $\lambda$ 即是优化问题的解决方案。最后判断 $D ^ { * }$ 是否为空，若为空则结束分配，否则对 $D ^ { * }$ 中的所有D2D用户重复上述步骤。以此迭代，直到蜂窝用户资源为空。

综上所述，本文提出的一种为D2D用户分配资源的方案流程如下：

Step1 假设基站知道小区中蜂窝用户的坐标，故可知蜂窝用户集合为 $\mathsf { C } = \{ c = 1 , 2 , 3 . . . , N \}$ 。

Step2判断D2D发射机是否在以基站为圆心， $r _ { \mathrm { { l } } }$ 为半径的圆形区域内，若不在则建立D2D通信，否则两用户使用蜂窝模式通信。最终可得D2D用户集合 $\mathrm { D } / = \{ d = 1 , 2 , 3 . . . , M \}$ 。

Step3判断蜂窝用户 $\scriptstyle { \mathbf { \alpha } } _ { c }$ 是否在以D2D用户 $d$ 的接收机为圆心， $r _ { 2 }$ 为半径的圆内，若在，则 $\mathbf { \Psi } _ { c }$ 不是 $d$ 的潜在复用蜂窝用户，若不在，则计算由式（17）中得到的交点A并判断其是否满足式（18）要求，若满足则 $\boldsymbol { \mathbf { \mathit { c } } }$ 是 $d$ 的潜在复用蜂窝用户，遍历蜂窝用户集合中所有的蜂窝用户，直到找到 $d$ 所有的潜在复用用户，并存于集合 $\Pi _ { d }$ 。并将不属于 $\Pi _ { d }$ 的蜂窝用户相应的 $\mathscr { \lambda } _ { c , d } = 0$ u对于集合D中所有的D2D用户重复此步骤，可以找到各自的潜在复用集合 $\Pi _ { d }$ 。

Step4根据 $\mathrm { ~ H ~ }$ 找出最大化每个蜂窝用户 $\mathbf { \Psi } _ { c }$ 资源吐吞量的D2D集合 $\Omega _ { c }$ 。

Step5判断 $\Omega _ { c }$ 中所有 D2D 用户是否满足 $\sum _ { d \in \Omega _ { c } } I _ { d , B } \leq I _ { B } ^ { t h }$ ，若不满足则将 $\Omega _ { c }$ 中对基站形成干扰最大的D2D对去掉并存入集合 $D ^ { * }$ ，直到满足 ΣId.B≤IB，然后更新其对应的λ值。

Step6更新蜂窝用户集合为 $C ^ { * }$ ， ${ \boldsymbol { C } } ^ { * } { = } { \boldsymbol { C } } - { \boldsymbol { c } }$ ，D2D用户集合记为 $D ^ { * }$ ，并判断 $D ^ { * }$ 是否为空，若为空则结束，否则执行下一步。

Step7对集合 $D ^ { * }$ 中的所有D2D用户返回 Step4，直到蜂窝用户集合为空。

# 3 仿真验证

# 3.1仿真参数

为了验证本文所提的资源分配算法的有效性，在mmWave5G 蜂窝网络场景下，使用MATLAB进行仿真，主要的仿真参数如表1所示。

# 3.2仿真结果

图4描述的是不同频段下系统吞吐量的累积分布函数（CDF）。在D2D数量为20、D2D用户的距离为 $1 0 \mathrm { m }$ 时对73GHz 和 $2 . 4 \ : \mathrm { G H z }$ 下蜂窝系统吞吐量作了比较。从图4中可以看出， $7 3 ~ \mathrm { G H z }$ 的系统吞吐量的累积分布函数（CDF）要优于2.4$\mathrm { G H z }$ ，并且可说明高频段的性能若是采用恰当的干扰控制则优于低频段。

表1主要的仿真参数  

<html><body><table><tr><td>参数</td><td>参数值</td></tr><tr><td>小区半径</td><td>500m</td></tr><tr><td>RB带宽</td><td>180KHz</td></tr><tr><td>蜂窝用户数</td><td>10</td></tr><tr><td>D2D对数</td><td>5,8,11，..，20</td></tr><tr><td>蜂窝用户发射功率</td><td>25dBm</td></tr><tr><td>D2D 发射功率</td><td>21dBm</td></tr><tr><td>预定义有效 SINR</td><td>0dB</td></tr><tr><td>噪声功率密度</td><td>-174dBm/Hz</td></tr><tr><td>路损参数 LOS(μ，α，σ)</td><td>(69.8,2,5.8)</td></tr><tr><td>路损参数 NLOS(μ，α，σ)</td><td>(86.6,2.45,8.0)</td></tr><tr><td>D2D 链路路损概率</td><td>P1=0.8</td></tr><tr><td>非 D2D 链路的路损概率</td><td>P2=0.2</td></tr><tr><td>莱斯信道K参数</td><td>5</td></tr></table></body></html>

![](images/cc1e3b880d97dd1f2dcb288a26d8f80d568f38f572eca6309462fb7f22fb24d6.jpg)  
图4不同频段下系统吞吐量的CDF

图5描述的是在D2D用户数量为20时的系统总吞吐量和D2D用户距离之间的关系。将本文所提算法与随机分配算法和启发式算法进行比较。从图5中可以看出，当 $d { < } 3 0 \mathrm { m }$ 时，系统总吞吐量随着D2D 对之间的距离的增大减少的程度大；当$d { > } 3 0 \mathrm { m }$ 时，系统总吞吐量随着D2D对之间的距离的增大则变化甚微。这主要是因为当 $d$ 较小时，D2D链路质量比较好，所以对系统总吞吐量的影响很大，但是当 $d$ 较大时，D2D 链路质量会变的很差，所以几乎对系统总吞吐量没有什么影响。并且从图5中可以看出本文所提算法优于其他两种算法，很显然，本文所提出的方案能使小区总吞吐量得到有效提高。

![](images/e6abf1133a9c700269b13b7ade2dea3908b4ca5233954ccd41ae5f41f1c6cba8.jpg)  
图5系统总吞吐量和D2D用户距离之间的关系

图6描述的是D2D用户间的距离为 $1 0 \mathrm { ~ m ~ }$ 时的系统总吞吐量与D2D对数之间的关系曲线。从图6中可以看出，在蜂窝用户数量是定值时，系统总吞吐量会先随着D2D对数量的增加而增加，但是增加的速度越来越趋于平缓，这是因为随着D2D 对的增加，D2D 通信对蜂窝通信的干扰也会增加，并且D2D 对之间的干扰也会增加。除此之外，随机分配算法曲线有下降趋势，这是因为其干扰问题没有得到很好的解决。并且可以从图6中看出，本文所提算法优于其他两种算法。

![](images/28a69d953fe9270552de92939197cb19f78019a33ffe2c122a54bd53b72d4b80.jpg)  
图6系统总吞吐量与D2D对数之间的关系

# 4 结束语

D2D 通信技术和毫米波技术的结合，不仅能够提高数据传输速率，而且能提升系统吞吐量和频谱效率，但是D2D通信也会给蜂窝系统带来干扰。为了解决这个问题，本文提出一种联合区域限制和干扰控制的资源分配方案，并能提高系统吞吐量。仿真结果表明，本文所提算法能在保证蜂窝用户和D2D用户服务质量的条件下提升系统的性能。

# 参考文献：

[1]Gupta A,Jha R K.A survey of 5G network:architecture and emerging technologies [J].Access IEEE,2015,3:1206-1232.   
[2]Karjalainen J, Nekovee M,Benn H,et al. Challenges and opportunities of mm-wave communication in 5G networks [C]//Proc of the 9th International Conference on Cognitive Radio Oriented Wireless Networksand Communications.2014: 372-376.   
[3]Roh W, Seol JY,Park J,et al.Millimeter-wave beamforming as an enabling technology for 5G cellular communications:theoretical feasibility and prototype results [J]. IEEE Communications Magazine,2014,52 (2):106- 113.   
[4]Misra G,Misra S,Agarwal A,et al.Device to device millimeter wave communication in 5G wireless cellular networks (a next generation promising wireless cellular technology）[C]// Proc of International Conference on Signal Processing,Communication,Power and Embedded System.2016.   
[5]3GPP TR 36.877 V0.0.4(2014-08) 3rd generation partnership project; technical specification group radio access networks;LTE device to device

proximity services;user equipment (UE) radio transmission and reception;

(release 12) [R].   
[6]王俊义，巩志帅，符杰林，等.D2D通信技术综述[J].桂林电子科技大 学学报,2014(2):114-119.   
[7]Ali S，Rajatheva N，Latva-Aho M.Full duplex device-to-device communication in cellular networks [C]// Proc of IEEE European Conference on Networks and Communications.2014:1-5.   
[8]李扬波，郭祖华，徐立新.蜂窝网络中基于干扰控制的 D2D 通信联合 资源分配方案[J].火力与指挥控制,2016,41(1):169-173.   
[9]Sun J,Zhang T,Liang X,et al. Uplink resource allocation in interference limited area for D2D-based underlaying cellular networks [C]//Proc of IEEE Vehicular Technology Conference.2O16:1-6.   
[10] Zulhasnine M,Huang C,Srinivasan A.Efficient resource allocation for device-to-device communication underlaying LTE network [C]// Proc of IEEE International Conference on Wireless and Mobile Computing, NETWORKING and Communications.2010:368-375.   
[11] Oduola W O,Li X,Qian L,et al.Power control for device-to-device communications as an underlay to cellular system [Cl// Proc of IEEE International Conference on Communications.2014:5257-5262.   
[12] Huynh T, Onuma T,Kuroda K,et al.Joint downlink and uplink interference management for device to device communication underlaying cellular networks [J].IEEE Access,2016,4: 4420-4430.   
[13] Shen X.Device-to-device communication in 5G cellular networks[J].IEEE Network,2015,29(2): 2-3.   
[14] Guizani Z,Hamdi N. Spectrum resource management and interference mitigation for D2D communication with awareness of BER constraint in mmWave 5G underlay network [C]// Proc of IEEE Symposium on Computers and Communication.2016:855-860.   
[15] Naqvi SAR,Hassan SA,Pervaiz H,etal. Self-adaptive power control mechanism in D2D enabled hybrid cellular network with mmWave small cells:an Optimization Approach [C]//Proc of IEEE Globecom Workshops. 2016.   
[16] Akdeniz MR,Liu Y, Samimi MK,et al. Millimeter wave channel modeling and cellular capacity evaluation [J].IEEE Journal on Selected Areas in Communications,2013,32(6):1164-1179.