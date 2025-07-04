# 基于移动边缘计算的车联网缓存策略研究

刘可欣，陈桂芬

(长春理工大学 电子信息工程学院，长春 130022)

摘要：针对车联网中数据流量爆炸式增长而引起的业务响应时延过高的问题，提出了一种基于移动边缘计算的蚁群模拟退火算法缓存策略(ACSAM)。首先，在基于5G的“车-边-云”协同系统架构下，以最小化内容下载时延为目标，建立了通信计算模型；其次，采用蚁群算法构造了使内容下载时延最小的局部最优解；最后，使用模拟退火算法对局部最小下载时延进行扰动，并以一定概率接受新解，从而得到全局最小下载时延，即保证了内容被预缓存在最佳的位置。仿真结果表明，在车边云协同架构下，ACSAM缓存策略可显著减少传输冗余，降低下载时延。

关键词：车联网；移动边缘计算；缓存策略 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2019.12.0700

Research on caching strategy of Internet of vehicles based on mobile edge computing

Liu Kexin, Chen Guifen† (SchoolofElectronics&Information Enginering,Changchun UniversityofScience&Technology,Changchun130022, China)

Abstract: To solve the problem ofhigh service response delaycaused byexplosive growth of data traffic in the Internetof vehicles，this paper proposed an Ant Colony Simulated Annealing algorithm cache strategy basedon Mobile edge computing(ACSAM).Firstly,under the 5G based "vehicle-edge-cloud "collaborative systemarchitecture,established a communication computing model to minimize thecontent download delay;secondly,used the Ant Colony Optimization to constructalocal optimal solution to minimize thecontent download delay; finally,usedthe search abilityofthe Simulated Annealingalgorithmtodisturbthelocaloptimalsolutionandaccepthenewsolutionwithacertainprobabilitytherebyobtainedthe global optimal solutionand improvedcachehitrate.Simulationresultsshowthatunderthevehicle-edge-cloudcollaborative architecture,te ACSAMcache strategy can significantly reduce transmision redundancyand reduce download latency.

Key words: Internet of vehicles; mobile edge computing; caching strategy

# 0 引言

车联网作为5G的主要应用场景之一，是2015年由国务院发布的“中国制造2025”战略的焦点[1]。随着车联网用户对各种服务需求的增加，使得网络中的业务流量大幅度增长，通过观察移动流量[2.3]可以发现，大多数的流量请求是由少数内容产生的，即流行内容被重复请求的概率大。随着2021年的到来，每月的全球移动流量将有极大的可能性超出35艾字节。为了解决数据流量大幅度增长所导致的响应时延过高的问题，移动边缘计算(mobile edge computing，MEC)[4]以其特有的优势被引入到了5G超密集部署的车联网中。通过在流量非高峰时段，将流行内容预先缓存在部署于路侧单元或基站的MEC服务器，可以有效减少网络流量损耗和内容传输冗余，同时降低业务响应时延，提供用户高质量的服务体验。

MEC由移动云计算演化而来，首次出现是在2013年。欧洲电信标准协会(ETSI)于2014年正式将MEC定义为一种既可以提供信息技术服务环境又具有云计算能力的体系架构。目前，作为5G的关键技术之一，MEC可以动态地获取无线接入网络内的实时信息，促进缓存技术朝着更加智能化的方向发展。通过将MEC和缓存进行整合，可实现服务响应的高效性，为此已有大量学者对其开展了研究。文献[5]中，作者在多个cloudlet协作的分布式系统框架下，制定了内容分配优化模型，提出了以状态为前提的内容分发算法，显著提高了内容缓存命中率。文献[6]提出了一个联合的协作式缓存和处理框架，该框架支持MEC网络中的自适应比特率(ABR)视频流，可有效降低内容交付延迟。文献[7]提出了一种基于深度学习的缓存方案，通过准确地预测内容流行度并确定将哪些内容存储在基站，保证了缓存决策的有效性。文献[8]提出了一种新的基于移动感知概率边缘缓存方案(mobility-aware probabilistic edgecaching strategy，MAP)，该方案充分利用了无线接入网上下文数据，可最大限度提高缓存命中率并最小化内容检索延迟。文献[9]将车辆层和路侧单元层缓存相结合，提出了基于云的双层缓存放置策略(doublelayercache placement strategy，DLC)，可实现内容在最佳节点的缓存，保证任务快速响应。

虽然研究人员已对缓存方案进行了大量研究，但大多没有考虑移动性对缓存过程造成的影响，同时也没有考虑移动终端、MEC及云的相互协作。因此，本文以车联网为背景，在“车一边一云”协同的系统架构下，建立了基于时延的通信模型，并提出了一种基于MEC的蚁群模拟退火算法缓存策略(ant colony and simulated annealing algorithm cache strategybased on Mobile edge computing，ACSAM)。仿真结果表明,在“车-边-云”协同架构下，该缓存策略可有效降低业务响应延迟。

# 1 系统架构及场景分析

# 1.1系统架构

为了保证车辆与其他实体信息交换(V2X)的实时性，5G使能技术与车联网结合是大势所趋，具体的协同系统架构如图1所示。

![](images/72d60bfbd9c8182b506ef1e047f45cdc69678e9f5bd98ee566e72f659fea6834.jpg)  
图1基于5G的“车-边-云”协同系统架构 Fig.15G-based "vehicle-edge-cloud" collaborative system architecture

在该架构中融入了多种新兴技术，其中，软件定义网络(SoftwareDefinedNetwork,SDN)可以对多个MEC服务器进行控制，并且统一配置MEC与云平台的资源；网络功能虚拟化(NetworkFunctionVirtualization，NFV)以整合网络设备类型为目标，可以管理多种不同架构的设备[10]，使网络的可扩展性及灵活性得到改善；网络切片能够保证车联网业务运行的独立性，并实现相应的功能定制；MEC可以将第三方应用及业务部署在网络边缘，实现基站与业务的深度融合，将其与车、云协同可减少数据传输冗余，获得比“边-云”协同更低的数据投递时延。

# 1.2场景分析

在5G超密集部署的车联网场景中，车辆移动带来了通信的不稳定，同时也一定程度上增加了车辆通信的机会。在车-边-云架构中包括一个中央云、多个MEC服务器及车辆，可进行协作式缓存并且允许车与车之间直接通信(V2V。MEC服务器与车辆都具有一定的缓存能力，当有车辆发出某一请求时，主要通过以下四种方式获取请求内容:

a)如果车辆恰好存储该内容，那么就可以直接从源车辆获取，此时响应时延为零；b)向一定通信范围内的V2V车辆发出请求，若V2V车辆中已存储该车辆所请求的内容，则将该内容通过V2V链路直接传送给该车辆；c）向在路侧单元等位置部署的MEC服务器发出请求，若在本地的MEC服务器未缓存该请求内容，则通过其他协作的MEC服务器获取，之后，再经由本地MEC服务器传送给请求车辆；d）由中央云通过核心网将请求内容传到本地MEC服务器，再经本地MEC服务器将该内容传输给请求车辆。

由于请求内容从核心网传输到发出请求的车辆会增加成本和时延，通过将流行内容预先缓存在车辆和MEC服务器中，可大大减少下载时延，节省带宽资源。因此，本文在“车-边-云”协同架构下，以最小化内容的下载时延为目标，提出了ACSAM缓存策略。

# 2 通信计算模型

假设一个缓存域内有M个MEC 服务器和N个车辆，用集合表示为 $V = E \bigcup U = \{ \nu _ { 1 } , \nu _ { 2 } , . . . , \nu _ { M + N } \}$ ，其中 $E = \{ e _ { 1 } , e _ { 2 } , . . . , e _ { M } \}$ 表示MEC设备的集合， $U = \{ u _ { 1 } , u _ { 2 } , . . . , u _ { N } \}$ 表示车辆的集合。 $N ( i ) \subset V$ 是由能够与车辆进行通信的V2V车辆和能够为车辆提供服务的 MEC 服务器所组成的集合。 $u ( i ) = N ( i ) \cap U$ 表示车辆 $u _ { i }$ 的V2V邻居集合， $m ( i ) = N ( i ) \cap E$ 表示为车辆 $u _ { i }$ 提供服务的 MEC集合。假设数据中心将L个不同的内容文件 $O = \{ o _ { 1 } , o _ { 2 } , . . . , o _ { L } \}$ 提供给车联网，每个内容的长度归一化为 $s$ 。

定义内容流行度服从Zipf分布，则内容 $o _ { f }$ 被请求的概率为

$$
p _ { f } = { \frac { f ^ { - \theta } } { \sum _ { j } ^ { L } j ^ { - \theta } } }
$$

其中， $\theta$ 为Zipf分布的影响因子。假设车辆发出的请求服从期望为 $\theta _ { i }$ 的泊松分布，则在 $\Delta t$ 内请求内容 $o _ { f }$ 的概率为$p _ { i f } = p _ { f } \cdot \theta _ { i }$ 0

定义内容缓存矩阵 $X = \{ x _ { m , f } \mid e _ { m } \in E , o _ { f } \in O \}$ 和$Y = \{ y _ { i , f } \mid u _ { i } \in U , o _ { f } \in O \}$ ，具体如下：

1）在MEC缓存

$$
x _ { m , f } = \{  1 , \atop { \not { D } \} } { \stackrel { \ p / } { \Esc } } o _ { f } { \vec { \uparrow } } { \stackrel { \ p / } { \underbrace { \dot { \downarrow } } { \ 2 } } } { \overleftrightarrow { \tilde { \chi } } } { \overline { { \tilde { \mp } } } } { \big \langle } \Sigma { \not { D } \Sigma } { \tilde { \mp } } { \tilde { \pm } } { \tilde {  } }
$$

2）在车辆缓存

$$
y _ { i , f } = \left\{ { 1 , \atop { \| \hat { \mathcal { H } } \cap \mathcal { S } _ { f } \| \hat { \mathcal { H } } \cap \mathcal { Z } \mathcal { Z } \| \hat { \mathcal { H } } \setminus \mathcal { Z } \mathcal { Z } \mathcal { Y } \mathcal { Z } , \mathrm { ~ M E C ~ } \| \check { \mathcal { H } } \mathcal { H } _ { i } } } u _ { i } \right.
$$

定义系统缓存命中率为在MEC和车辆获取的内容请求数与总请求数之比，如式(4)所示。

$$
R = { \frac { Q } { Z } }
$$

其中， $z$ 表示缓存域内车辆发出的总请求数， $\boldsymbol { \mathscr { Q } }$ 表示在车辆和MEC缓存命中的请求数。

针对车的移动性，这里将MEC 服务器和车辆协同缓存问题转换为最小化下载时延问题。

# 1)V2V通信时延

设 $R _ { V 2 V }$ 为车与车间可进行通信的最大距离，不同V2V对的通信是互不干扰的。车辆 $u _ { i }$ 和车辆 $\boldsymbol { u } _ { j }$ （204号 $( u _ { i } \in U , u _ { j } \in U ( i ) )$ 的信息交换时间 $\gamma _ { i j } ( f o r \forall u _ { i } \in U , u _ { j } \in U ( i ) )$ 服从期望值为 $1 / \lambda _ { i j } ( \lambda _ { i j } > 0 )$ 的指数分布，其概率密度可表示为

$$
f _ { i j } ( t ) = \lambda _ { i j } \cdot e ^ { - \lambda _ { i j } t } , t \geq 0
$$

其中， $1 / \lambda _ { i j }$ 表示 $u _ { i }$ 和 $u _ { j }$ 的平均通信时长， $\lambda _ { i j }$ 越大，表示车辆移动强度越大。若在 $\gamma _ { i j }$ 内，两车间传输的数据比特数不小于请求内容 $o _ { f }$ 的大小，便可以保证内容传输的连续性。

定义 $u _ { i }$ 通过V2V通信链路成功获取到请求内容 $o _ { f }$ 的概率为 $P _ { i , f } ^ { \nu 2 \nu }$ ，那么：

$$
\begin{array} { r } { P _ { i , f } ^ { \nu 2 \nu } = 1 - \prod _ { \mathbf { u } _ { j } \in U ( i ) } ( 1 - y _ { j , f } \cdot e ^ { - y _ { j , f } \cdot \lambda _ { i j } \cdot t _ { i , \alpha _ { j } } } ) } \end{array}
$$

设定车与车采用DSRC通信方式中的IEEE802.11p协议[1]在独立同分布信道中进行通信，路径损耗[12]可以定义为

$$
L _ { \nu 2 \nu } ^ { d B } = 6 3 . 3 + 1 7 . 7 \log _ { 1 0 } ( d _ { i , u _ { j } } )
$$

其中， $d _ { i , u _ { j } }$ 表示车辆 $u _ { i }$ 与 $u _ { j }$ 之间的通信距离，式(7)的单位为dB，转换为数值形式为

$$
L _ { \nu 2 \nu } = 1 0 ^ { - \frac { L _ { \nu 2 \nu } ^ { d B } } { 1 0 } }
$$

因此， $u _ { i }$ 从V2V车辆 $\boldsymbol { u } _ { j }$ 获取内容的下载速度 $w _ { i , u _ { j } }$ 为

$$
w _ { i , u _ { j } } = B _ { i , u _ { j } } \cdot \log _ { 2 } ( 1 + \frac { p _ { \nu } L _ { \nu 2 \nu } \kappa } { n _ { 0 } } )
$$

其中， $P _ { \nu }$ 表示车辆的发射功率， $n _ { 0 }$ 表示高斯白噪声功率， $B _ { i , { \mu } _ { j } }$ 是车与车通信链路的带宽， $\kappa$ 表示路径损耗常数。

则 $u _ { i }$ 从V2V车辆 $\boldsymbol { u } _ { j }$ 获取内容的下载时延 $t _ { i , u _ { j } }$ 为

$$
t _ { i , u _ { j } } = s / w _ { i , u _ { j } }
$$

2)V2M通信时延

设定车辆和MEC(RSU)间的通信链路为频率平坦型块衰落的瑞利信道，则 $u _ { i }$ 从MEC服务器获取内容的下载速度 $\boldsymbol { w _ { i , e _ { j } } }$ 为

$$
w _ { i , e _ { j } } = B _ { i , e _ { j } } \cdot \log _ { 2 } ( 1 + \frac { p _ { m } d _ { i , e _ { j } } ^ { - \varepsilon } \kappa } { n _ { 0 } } )
$$

其中， $\boldsymbol { P _ { m } }$ 表示MEC发射功率， $d _ { i , e _ { j } }$ 表示MEC服务器与接收车辆间的距离， $\kappa$ 表示路径损耗常数， $B _ { i , e _ { j } }$ 是MEC到车的通信链路带宽， $\varepsilon$ 为路径损耗指数。

则 $u _ { i }$ 从MEC服务器获取内容的下载时延 $t _ { i , e _ { j } }$ 为

$$
t _ { i , e _ { j } } = s / w _ { i , e _ { j } }
$$

一般而言，内容从云平台到本地MEC、MEC到MEC的传输时延均可视为常量，这里分别用 $t _ { 0 } \setminus t _ { 1 }$ 表示，则车辆 $u _ { i }$ 以MEC服务器为媒介获取某一内容的下载时延为

$$
t _ { m } = \alpha _ { m ( i ) , ~ f } ( t _ { i , e _ { j } } + t _ { 1 } ) + x _ { m ( i ) , f } \cdot t _ { i , e _ { j } } + \beta _ { f } ( t _ { 0 } + t _ { i , e _ { j } } )
$$

$$
s . t . ~ x _ { m , f } , y _ { i , f } \in \{ 0 , 1 \} , \forall e _ { m } \in E , u _ { i } \in U , o _ { f } \in O
$$

$$
\alpha _ { m ( i ) f } = ( 1 - x _ { m ( i ) , f } ) \cdot ( 1 - \prod _ { m = 1 } ^ { M } ( 1 - x _ { m , f } ) ) , \forall \sigma _ { f } \in O
$$

$$
\beta _ { f } = \prod _ { m = 1 } ^ { M } ( 1 - x _ { m , f } ) , \forall o _ { f } \in O
$$

其中，式(13-a)表示 $x$ ， $y$ 取值，式(13-b)表示仅当 $o _ { f }$ 被缓存在除本地MEC外的其他协作MEC中时， $\alpha _ { m ( i ) , f }$ 的值为1；式(13-c)表示内容 $o _ { f }$ 仅在云服务器缓存时， $\beta _ { f }$ 的值为1。

综上，请求内容被各车辆获取的总下载时延 $t ( L )$ 为

$$
\begin{array} { r } { t ( L { \bf \Pi } ) = \sum _ { i = 1 } ^ { N } \sum _ { f = 1 } ^ { L } p _ { i f } ( 1 - y _ { i , f } ) \Big \{ { p _ { i , f } ^ { \nu 2 \nu } } \cdot t _ { i , u _ { j } } + ( 1 - p _ { i , f } ^ { \nu 2 \nu } ) \cdot t _ { m } \Big \} } \end{array}
$$

为保证缓存位置最佳，响应时延最小，MEC与车间的协作缓存优化问题可以表示为

$$
\operatorname* { m i n } \{ t ( L ) \}
$$

# 3 ACSAM内容缓存策略

蚁群算法(antcolony optimization，ACO)是受蚂蚁觅食过程中产生的一系列行为的启迪，以信息素浓度为依据选择行进路线的一种算法。当某一路径上有较高的信息素浓度存留时，该路径就有极大的可能性被选中。基本的ACO算法具有并行性等其他算法无法比拟的优势，但在求解如上述所示的缓存优化这类NP-hard问题时，存在明显的不足，即收敛速度较缓慢，难以跳出某一局部区域的最优解。

模拟退火算法(simulated annealingalgorithm，SA)是一种随机优化算法，该算法只与初始温度、最小温度和退火次数有关，其优点是能够有效解决NP-hard问题，并在解空间找到符合条件的全局最佳结果，即能够避免问题的解在一定区域内最优，缺点是随机性较重。

考虑到蚁群和模拟退火算法自身的优缺点，将这两种算法相结合既可以提高退火的速度，又可以避免陷入局部最优。因此，本文提出了ACSAM内容缓存策略，通过将流行内容预先缓存在MEC服务器和车辆中，可显著降低传输造成的时间及成本损耗，保证响应速度。

# 3.1启发函数设置

假设车从某一MEC服务器或车辆下载内容的时延为

$$
t _ { i , \nu _ { j } } = \frac { O _ { - } t o t a l l e n g t h } { w _ { i , \nu _ { j } } }
$$

其中， $o$ _totallength为车从 $V _ { j }$ 下载的内容总长度， $w _ { i , \nu _ { j } }$ 为下载速度。定义启发式函数 $\eta _ { j } ( t )$ 为

$$
\eta _ { j } ( t ) = \left( 1 - \frac { t _ { i , \nu _ { j } } - t _ { a \nu e } } { t _ { i , \nu _ { j } } + t _ { a \nu e } } \right) ^ { 2 }
$$

其中， $t _ { a v e }$ 表示在当前解最佳的情况下从各个设备下载内容的平均时延。 $\eta _ { j } ( t )$ 越大， $V _ { j }$ 被选中概率越大。

# 3.2状态转移概率

利用蚂蚁搜寻路径，每一步的行进方向都由路径上存留的信息素浓度 $\tau _ { j } ( t )$ 判定，并且每步转移的可能性都按照式(18)进行计算，重复该过程直到到达(或找不到)目的地退出。

$$
p _ { j } ( t ) = \left\{ \begin{array} { l l } { \underline { { [ \tau _ { j } ( t ) ] ^ { \alpha } \cdot [ \eta _ { j } ( t ) ] ^ { \beta } } } ~ , } & { \underline { { \forall } } ~ j } \\ { \sum _ { \varepsilon \in V _ { k } } [ \tau _ { \varepsilon } ( t ) ] ^ { \alpha } \cdot [ \eta _ { s } ] ^ { \beta } } & { \underline { { \forall } } ~ j } \\ { 0 , } & { \underline { { \forall } } } \end{array} \right.
$$

其中， $t a b u _ { k }$ 为蚂蚁走过的地点集合， $V _ { k } = \{ 1 , 2 , \cdots , \mathbf { M } + \mathbf { N } \} - t a b u _ { k }$ 表示蚂蚁前进过程中即将选取的车辆和MEC设备的集合， $\alpha$ 、

$\beta$ 分别表示信息素和启发式因子的相对重要程度。

# 3.3信息素更新规则

a)当某一蚁群执行任务结束时，对该蚁群所访问过的节点的信息素浓度进行更新(局部信息素更新)。

$$
\tau _ { j } ( t + n ) = ( 1 - \rho ) \cdot \tau _ { j } ( t ) + \Delta \tau _ { j } ( t )
$$

其中， $\rho ( 0 < \rho < 1 )$ 表示信息素的蒸发系数， $\Delta \tau _ { j } ( t ) = 1 / t _ { j }$ ， $t _ { j }$ 表示某次迭代时发出请求的车辆从 $V _ { j }$ 上下载内容所用的时间。

b）当所有蚁群都完成任务时，更新全局信息素。

$$
\tau _ { j } ( t + n ) = ( 1 - \rho ) \cdot \tau _ { j } ( t ) + \Delta \tau _ { j } ^ { \prime } ( t )
$$

其中 $\Delta \tau _ { j } ^ { \prime } ( t ) = 1 / t _ { b e s t j }$ ， $t _ { b e s t j }$ 表示在取得全局最优解后，车从 $V _ { j }$ 完成内容下载的时间。

# 3.4Metropolis 准则

比较当前温度T与前一时刻温度下的解(指用ACO优化得到的解)，利用SA，将当前区域内的最优解通过置换规则扰动，即任意挑选两个内容文件，若二者交换下载地点后响应时间缩短，则接受新解。在以Metropolis准则为基本依据的前提下，新解将以式(20)的概率被接受。

$$
p = \left\{ \begin{array} { c c } { \exp ( - \displaystyle \frac { t ( L ) - \overline { { t ( L ) } } } { T } ) } & { t ( L ) - \overline { { t ( L ) } } > 0 } \\ { 1 } & { \mathrm { ~ \exists ~ \# ~ } \oiiint } \end{array} \right.
$$

其中， $t ( L )$ 表示在当前温度 $T$ 下，交换地点后获取内容的总下载时延； $\overline { { t ( L ) } }$ 表示通过蚁群算法所得到的局部最短下载时间。

# 3.5ACSAM策略的基本流程

a）初始化参数，包括迭代次数、信息素浓度、初始温度和终止温度等。b)利用蚂蚁搜寻路径，并按照式(18)构造候选解。c）按照所有内容下载完成时间最短的原则计算出局部最优解，并根据式(19)更新局部信息素。d)利用SA，将当前区域内的最优解通过置换规则扰动以构造新解，并通过Metropolis 规则决定新解被接受的概率。e）判断当前 $T$ 下得到的局部最优解是否符合抽样稳定准则(即在同一温度下，经过连续干扰，局部最优解都固定)，满足继续，否则返回步骤d）。f）根据式(20)更新全局信息素浓度。g）当回火次数达到或当前温度低于最小回火温度，则输出最优解，否则回到步骤b）。

# 3.6ACSAM算法伪代码

输入：参与的车辆和MEC设备。  
输出：保证内容缓存在最佳位置的最小下载时延。  
a）初始化参数，包括 $\alpha$ ， $\beta$ ， $\mathbf { \Delta } \rho$ ， $T _ { \mathrm { m i n } }$ ， $T _ { 0 }$ 等。  
b）While $T > T _ { \mathrm { m i n } }$ for each ant随机选择一个初始位置j；for $\scriptstyle { \dot { \mathsf { J } } } = 1$ to $M + N$ 按照式(18)的概率选择下一缓存位置；end forend for计算第 $\boldsymbol { \mathsf { k } }$ 次迭代所用时间；for each edge按照式(19)更新局部信息素值；根据模拟退火的置换准则构造新解，按照式(21)接受新解；按照式(20)更新全局信息素；end forend while  
c）输出最小内容下载时延。

# 4 仿真实验

为了验证在“车-边-云”协同架构中ACSAM缓存策略

在降低时延方面的优越性，将其与ACO、MAP[8]、DLC[9]及随机缓存策略(random-based caching strategy，RC)[13]的缓存性能进行了对比。

# 4.1仿真环境

在仿真实验中，设置发布的内容数量为1000个，车与车间最大通信距离为 $1 5 0 \mathrm { m }$ ，内容流行度服从参数为0.56的Zipf分布[14],每个车辆发出的请求服从期望为0.3的泊松分布[15]。具体参数设置如表1所示。

表1相关仿真参数  
Tab.1Relevant simulation parameters   

<html><body><table><tr><td>参数</td><td>取值</td></tr><tr><td>内容数量</td><td>1000</td></tr><tr><td>V2V最大通信范围/m</td><td>150</td></tr><tr><td>MEC(RSU)覆盖半径/m</td><td>350</td></tr><tr><td>MEC设备发射功率/W</td><td>40</td></tr><tr><td>车载发射功率/W</td><td>1.3</td></tr><tr><td>高斯白噪声W</td><td>3×10-13</td></tr><tr><td>总带宽/MHz</td><td>30</td></tr><tr><td>路径损耗常数</td><td>10²</td></tr><tr><td>路径损耗指数</td><td>4</td></tr><tr><td>Zipf分布影响因子</td><td>0.56</td></tr><tr><td>泊松分布参数</td><td>0.3</td></tr><tr><td>指数分布参数</td><td>Γ(2,0.1)</td></tr><tr><td>α</td><td>0.3</td></tr><tr><td>β</td><td>1</td></tr><tr><td>p</td><td>0.4</td></tr><tr><td>T</td><td>1000</td></tr><tr><td>Tmin</td><td>10</td></tr></table></body></html>

# 4.2 仿真结果分析

图2仿真对比了在迭代次数影响下ACSAM、ACO的时延性能。假定Zipf分布的影响因子为0.56，协作缓存域内的MEC和车辆数分别为10和20，服务内容数量为1000。由图2可知，两者的下载时延都随着迭代次数的增加而降低，并且相比于ACO，ACSAM的收敛速度更快，下载时延更低，从中可看出ACSAM在降低时延方面有着明显优势。

![](images/b2e2aec434e30bd6e74234231784c9a5839e3545363dffce795d02acf561de56.jpg)  
图2迭代次数影响下的时延性能比较

图3仿真对比了在Zipf分布影响因子下ACSAM、MAP、DLC及RC的缓存性能。假定服务内容数为1000，MEC和车辆数分别为10和20，从中可以看出，除RC缓存策略外，其他三种缓存策略的延迟都随着影响因子的增大而降低。这是由于在RC中，每个缓存节点随机地确定其缓存项，不受流行度或其他参数影响，性能相当不稳定，而其他三种策略受流行度影响，当被重复请求的内容较少时，请求内容在车辆、MEC服务器等接近用户边缘的地方缓存的概率增加，从而提高了缓存性能，降低了时间消耗。综上，随着Zipf分布影响因子的变化，ACSAM的缓存策略在降低时延性能方面优于其他缓存策略。

![](images/fa3358f7320498a052f9bcba27c9b67dbb9c170607eb7ba3d7a3384f830b8e65.jpg)  
图3Zipf影响因子下的时延性能比较

图4、5描述了在MEC服务器数量影响下ACSAM、MAP、DLC和RC四种缓存方案的性能差异。假定有1000个服务内容，并且内容流行度服从影响因子为0.56的Zipf分布。从图4、5中可以看出，随着MEC设备数量的增多，四种缓存策略的缓存命中率皆升高，用户平均下载时延都降低。这是因为越来越多的请求内容可以直接从多个MEC协作的缓存域中获取，从而在提高缓存命中率的同时减少了从远程云下载的传输冗余，并且由于ACSAM算法能有效避免局部最优，因此相比于其他三种缓存方案可保证内容被缓存在最佳的节点，故而有着更高的缓存命中率和更低的下载时延。具体地，当MEC服务器数量为30时，ACSAM缓存策略的缓存命中率比DLC、MAP和RC分别高约 $7 . 9 \%$ 、 $1 8 . 9 \%$ 、$2 7 . 8 \%$ ，在时延上分别低约 $3 8 . 9 \%$ 、 $4 7 . 4 \%$ 、 $7 6 . 2 \%$ 。

![](images/b5c91cab24f44c3b0c4bce94a3e2b39e6b700a22240d4faaca1561cb604dcc2f.jpg)  
Fig.3Comparison of delay performance under Zipf impact factor   
图4MEC 服务器数量变化下的缓存命中率比较

![](images/b6788a61867e8de7440761bac3b5fe4ee9f9beff719f0578911ac9137477b8d9.jpg)  
Fig.2Comparison of delay performance under the influence of the number of iterations   
Fig.4Comparison of cache hit rates under changes in the number ofMECS   
图5MEC服务器数量变化下的时延性能比较

Fig.5Comparison of delay performance under changes in the number ofMECS图6、7仿真对比了当服务内容数量不同时，ACSAM、MAP、DLC和RC四种缓存策略的性能。假定MEC的数量为10，车辆数为20,Zipf分布影响因子的值为0.56。由图6、

7可以看出，随着服务内容数量的增加，所有缓存策略的缓存命中率均保持下降趋势，这是因为车辆和MEC服务器的存储空间都是有限的，当发布的内容数量累积到一定程度时，仅依靠车辆、MEC无法满足用户的需求，越来越多的内容需要从核心网进行下载。并且通过仿真结果可得，ACSAM 缓存策略要优于DLC、MAP和RC。具体地，当服务内容数量为1000时，ACSAM缓存策略的缓存命中率比DLC、MAP和RC分别高出了大约 $9 . 4 \%$ 、 $2 2 . 5 \%$ 、 $3 6 . 3 \%$ ，平均下载时延比DLC、MAP和RC分别低约 $10 . 9 \%$ 、 $1 4 . 6 \%$ 、 $4 0 . 6 \%$ 。

![](images/cf0ceb8d23e72b0905750972fd6e0bf9953d6ad5c9594bbe36d8e5d60d022f27.jpg)  
图6服务内容数量变化下的缓存命中率比较

![](images/fb5b47e074589e7d0d4e3b0b400af05b97bc1878cde08646ceedb13ecb9bac9b.jpg)  
Fig.6Comparison of cache hit ratios with changes in service content   
图7服务内容数量变化下的时延性能比较Fig.7Comparison of latency performance withchanges in service content

# 5 结束语

车联网面临着海量数据流量的冲击，为了实现车联网业务的实时响应，本文在基于5G的“车-边-云”协同系统架构下，建立了基于时延的通信模型，实现了对车、MEC设备、云三方面资源的调度，同时提出了ACSAM缓存策略，通过该策略可获得最小内容下载时延，从而保证各内容被缓存在最佳的节点。仿真结果证明，在“车-边-云"协同系统架构下，ACSAM缓存策略能有效减少内容的下载时延，提高响应速度。但由于本文仅假设了车辆资源共享的理想情况，不符合实际情形，因此，后续的研究会将车的自利性考虑在内，通过设立奖励机制实现车联网中各参与者的利益最大化。

参考文献：   
[1]Cheng X, Zhang R,Chen S,et al.5G enabled vehicular communications and networking [J]. China Communications,2018,15 (7): 3-6.   
[2]Bastug E,Bennis M,Debbah, Mérouane.Living on the edge: The role of proactive caching in 5G wireless networks [J]. IEEE Communications Magazine,2014,52 (8): 82-89.   
[3]An Liu, Vincent K. N.Lau. Cache-Enabled Opportunistic Cooperative MIMO for Video Streaming in Wireless Systems [J]. IEEE Transactions on Signal Processing:A publication of the IEEE Signal Processing Society,2014,62 (2):390-402.   
[4]左超，武继刚，史雯隽．移动边缘计算中的端到端任务分配算法[J]. 计算机应用研究,2019,37(7):1001-3695.(Zuo Chao,Wu Jigang,Shi Wenji. End-to-end task assignment algorithm in mobile edge computing [J]. Journal of Computer Applications,2019,37 (7): 1001-3695.)   
[5]Jiang L,Feng G, Qin S. Cooperative content distribution for 5G systems based on distributed cloud service network [C]// IEEE International Conference on Communication Workshop,2015:1125-1130.   
[6]Tran TX,Pompili D.Adaptive Bitrate Video Caching and Processing in Mobile-Edge Computing Networks [J]. IEEE Transactions on Mobile Computing,2019,18 (9): 1965-1978.   
[7]Thar K,Tran NH,OoT Z,et al. DeepMEC: Mobile Edge Caching Using Deep Learning [J]. IEEE Access,2018: 78260-78275.   
[8]Mahmood A, Casetti C,Chiasserini C,et al. Mobility-aware edge caching for connected cars [C]. wireless on demand network systems and service,2016:1-8.   
[9]Ma J,Wang J,Liu G,et al.Low Latency Caching Placement Policy for Cloud-Based VANET with Both Vehicle Caches and RSU Caches [C]. global communications conference,2017: 1-6.   
[10]徐灿辉.5G 网络架构对车联网发展影响的研究[J]．广东通信技术， 2018,38 (01): 76-79.(Xu Canhui.Research on the Influence of 5G Network Architecture on the Development of Telematics [J]. Guangdong Communication Technology,2018,38 (01): 76-79.)   
[11] Zheng K,Liu F, Zheng Q,et al. A graph-based cooperative scheduling scheme for vehicular networks [J]. IEEE transactions on vehicular technology,2013,62 (4): 1450-1458.   
[12] Luoto P,Bennis M,Pirinen P,et al. Vehicle clustering for improving enhanced LTE-V2X network performance [C]//European Conference on Networks & Communications.IEEE,2017: 1-5.   
[13] Tao M,Chen E,Zhou H,et al.Content-Centric Sparse Multicast Beamforming for Cache-Enabled Cloud RAN [J]. IEEE Transactions on Wireless Communications,2016,15(9):6118-6131.   
[14]侯停停．移动边缘计算（MEC）架构中高效内容分发技术[D]．四 川：电子科技大学,2018.(Hou Tingting.Efficient content distribution technology in mobile edge computing (MEC) architecture [D]. Sichuan: University of Electronic Science and technology,2018.)   
[15] Saichanma S,Chulsomlee S,Thangrua N,et al.Exact algorithms for the joint object placement and request routing problem in content distribution networks [J].Computers & Operations Research,2008,35 (12): 3860-3884.