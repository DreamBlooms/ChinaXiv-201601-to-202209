# 无线mesh网中QoS流量均衡策略研究

周创明，于明秋，邢瑞康(空军工程大学 防空反导学院，西安 710051)

摘要：由于现有的无线 mesh 网路由研究多寻求当前时刻的最优路径，缺少流量均衡机制，影响了网络资源的使用效益。针对这一问题，提出基于QoS 的流量均衡策略。通过研究蚁群算法的基础之上，重新定义启发信息和信息素更新规则，将节点和链路负载加入到路径选择的权衡因素中；同时，考虑到 mesh 节点到骨干网的通信，提出针对网关节点的流量均衡机制。改进算法以业务QoS要求作为约束条件，使路径规划倾向于负载度低链路和节点，为后续业务的路由选择提供良好的网络环境。实验结果表明，随着数据量的增多，该算法始终可以保证业务QoS，实现了严格的QoS 约束，并且能有效提高链路利用率，在路由质量方面优于中心节点法和改进信息素法。

关键词：无线mesh网；QoS；流量均衡；改进蚁群算法 中图分类号：TP393.07 doi:10.3969/j.issn.1001-3695.2018.04.0386

# Research on QoS flow equilibrium strategy of wireless mesh network

Yu Mingqiu, Zhou Chuangming, Xing Ruikang (CollegeofAir&Missile Defence,Air-force Engineering University,Xi'an71oo51,China)

Abstract: The existing research on QoSof wirelessmesh network always seeks the optimal path ofthecurrent moment and lackstraffc equilibrium scheme，which affects theuse benefit of network resource.Concerning this issue,the traffic equilibrium strategy basedon QoS isproposed.On the basisofantcolonyalgorithm,heuristicinformationandrules of pheromone updatingare redefined,and the load factor isaddedtoweighing factor.Atthe same time，considering the communication between Mesh node and backbone network,the trafc equilibrium mechanism of gateway node is proposed. Theimprovedalgorithmtakes QoSrequirements astheconstraintcondition,sothat path planning tends tolowerloadlink and node.Therouting decision of subsequent business willgooffin a good network environment.With the increase of data amount,experiments showthis algorithmcan guarantee QoS services allalong,and implement strict QoSconstraint.Bythis algorithm,the linkutilizationis improvedandqualityofrouting is better thancentralnodealgorithmandimprovedpheromone algorithm.

Key words: wireless mesh network; QoS; traffic equilibrium; improved ant colony optimization

# 0 引言

QoS(qualityofservice,服务质量)[1,2]指为指定的网络通信提供服务的能力。由于现实网络不可能为每个通信业务提供最优的服务，像无限大的带宽、趋于0的传输时延等，因此以有限的网络资源实现通信业务服务的最优化是网络研究的重要课题[3-6]。QoS 的主要思想是尽可能为每个业务提供更优的传输条件，同时尽可能为更多业务提供服务。无线mesh网(wirelessmeshnetwork)[7是一种多跳、自组织的带宽无线网络，与有线网相比，无线mesh网的网络容量和转发功能相对有限。因此实现无线mesh网QoS有着十分重要的意义。

在现有的研究中，文献[8.9]从路由度量指标出发，通过为链路设计更加细粒度的衡量标准，使路径选择更加符合业务需求。其路由度量的改进在AODV、HWMP等无线Mesh 网路由协议上开展，一定程度上改善了路由规划的质量。但这类方法的本质仍然是将链路量化成一个值，无区别地面向各个通信业务，无法满足业务QoS要求。因此实现无线Mesh网QoS的关键不仅仅是路由度量，而且还要关注在此基础上的路径规划。传统路由协议多使用最短路径算法，达不到保证QoS的目的。

从路径规划角度，许多研究将无线mesh网QoS问题视作多约束的目标优化问题，利用遗传、量子进化、粒子群等算法求解[10-12]。这样存在的问题是，初始化搜索种群以及每次迭代更新时都需要对粒子进行规范，即粒子必须是源节点和目的节点间一条可达路径的编码。文献[10\~12]的解决方法是，在初始化和算法迭代中加入路径搜索过程，这严重影响了算法的效率。

蚁群算法在解决路径搜索问题方面有着独特的优势，其原理是利用信息素反馈作用，引导蚂蚁走向较优的路径，整个过程无需对路径进行编码。现今已经有大量基于蚁群算法的网络QoS研究。文献[13]定义了领域最优位置，该位置即为中心节点。在搜索过程中，首先从当前节点转到其所属的中心节点处，由中心节点进行下一步选择。文献[14]将网络QoS问题转化为满足约束条件的路径最优化问题，通过改进信息素更新规则，提高了算法的收敛速度。

在以往的研究中，路径规划的目的多是寻找当前时刻的最优路径。但是，最优路径往往大于业务传输所需的基本条件，即过量占用了网络资源。由于网络中会不断有新的业务产生，后期的业务将难以获取可靠链路。就这一问题，本文提出满足业务QoS的流量均衡方案，目的是在保证业务QoS的同时，将流量均衡到整个网络中，为后续业务的路径规划提供更广泛的选择，同时有效防止网络拥塞。

# 1 问题模型

网络可以描述为一个无向赋权图 $G = ( V , E )$ ， $V$ 为网络节点的集合， $E$ 为网络链路的集合。本文研究的问题是：在$G = ( V , E )$ 寻找源节点 $s \in V$ 到目的节点 $d \in V$ 的一条路径$l ( s , d )$ 。路径 $l ( s , d )$ 要满足业务传输的条件。网络QoS 指标一般分为累加性指标、乘积性指标和瓶颈性指标[10]三类。为便于操作，本文以时延代表累加性指标，以丢包率代表乘积性指标。则时延表示为

$$
d e l a y ( l ( s , d ) ) = \sum _ { e \in l ( s , d ) } d e l a y ( e ) + \sum _ { \nu \in l ( s , d ) } d e l a y ( \nu )
$$

delay $( e )$ 为链路上的时延，delay(v)为节点上的时延。丢包率表示为

$$
p a c k e t \_ l o s s ( l ( s , d _ { n } ) ) = 1 - \prod _ { i = 1 } ^ { n - 1 } ( 1 - p a c k e t \_ l o s s ( l ( s , d _ { i } ) ) )
$$

设业务所能允许的最大时延为delay_max，所能允许的最大丢包率为packet_loss_max。定义链路负载度为 $\mu _ { e } ( i j )$ ，表示链路已占用带宽与总带宽的比值。节点负载度为$\mu _ { \nu } ( j ) = ( \rho _ { r } - \rho _ { s } ) / \rho _ { r } + \theta / \Phi$ ，其中 $\rho _ { s }$ 表示节点转发速率， $\rho _ { r }$ （204号表示节点接收速率， $\theta$ 为节点缓存队列剩余容量， $\Phi$ 为队列总长度。当 $\rho _ { s } < \rho _ { r }$ 时，一定时间后，队列将会溢出。

综上，本文的问题模型为

在未完成路径 $l ( s , d _ { n } )$ 的基础上，选择下一跳节点 $d _ { n + 1 }$ ，满足约束条件：

$$
d e l a y ( l ( s , d _ { n + 1 } ) ) \leq d e l a y \_ \operatorname* { m a x }
$$

$$
\begin{array} { r } { p a c k e t \_ l o s s ( l ( s , d _ { n + 1 } ) ) \leq p a c k e t \_ l o s s \_ \mathrm { m a x } } \end{array}
$$

使下一跳节点的 $\operatorname* { m a x } ( \mu _ { e } ( d _ { n } d _ { n + 1 } ) , \mu _ { \nu } ( d _ { n + 1 } ) )$ 最小，即在路径规划中倾向于负载度小的节点和链路。

# 2 算法研究

# 2.1基本蚁群算法简介

蚂蚁在爬行过程中会释放信息素，该物质可以引导蚂蚁爬行的方向，信息素浓度高的路径会被优先选择。最短路径在单位时间内通过的蚂蚁较多，会积累浓度较高的信息素，从而吸引更多的蚂蚁经过，形成一种正反馈机制，最终使蚂蚁都选择最短路径[15-19]

设蚂蚁数量为 $m$ ，点 $i$ 和点 $j$ 之间的距离为 $d _ { i j }$ ，启发信息$\eta _ { i j } = 1 / d _ { i j }$ ， $\tau _ { i j }$ 表示边 $i j$ 的信息素量， $p _ { i j } ^ { k } ( t )$ 是 $t$ 时刻位于城市 $i$ （204号的第 $k$ 只蚂蚁到城市 $j$ 的概率，则

$$
p _ { i j } ^ { k } ( t ) = \left\{ \begin{array} { l l }  \displaystyle { { \frac { [ \tau _ { i j } ( t ) ] ^ { \alpha } [ \eta _ { i j } ( t ) ] ^ { \beta } } { \displaystyle { \sum _ { s \in a l l o w e d _ { k } } ^ { \alpha } [ \tau _ { i s } ( t ) ] ^ { \alpha } [ \eta _ { i s } ( t ) ] ^ { \beta } } j \in a l l o w e d _ { k } } } } \end{array} \right.
$$

其中：allowed $\boldsymbol { \mathbf { \mathit { \Pi } } } _ { k } ^ { l }$ 为蚂蚁 $k$ 可以选择的下一个城市的集合。禁忌表 $t a b u _ { k } ( k = 1 , 2 , . . . , m )$ 用于记录蚂蚁 $k$ 已走过的城市，在选择下一个城市时，已列入禁忌表的城市将不做考虑。 $\alpha$ 和 $\beta$ 为权重值。当所有蚂蚁走完路线时，信息素会被更新，更新规则为

$$
\tau _ { i j } ( t + 1 ) = ( 1 - \rho ) \tau _ { i j } ( t ) + \sum _ { k = 1 } ^ { m } \Delta \tau _ { i j } ^ { k } ( t )
$$

其中： $\rho$ 表示信息素挥发因子， $\Delta \tau _ { i j } ^ { k } ( t )$ 表示第 $k$ 只蚂蚁在 $t$ 时刻通过路径 $i j$ 时释放的信息素。

$$
\Delta \tau _ { i j } ^ { k } ( t ) = \left\{ \begin{array} { r r } { \underline { { Q } } } & { \quad \iiint _ { k } \quad \overleftrightarrow { \bigoplus } \underline { { k } } \in k / \underline { { u } } \underline { { u } } _ { j } \underline { { \oplus } } \chi \chi \chi \chi \langle \rangle \langle \rangle \langle | \overline { { \sharp } } \rangle | \overline { { \chi } } \rangle \| \leq | \underline { { \xi } } \underline { { \chi } } _ { i } \rangle | \leq | \underline { { \xi } } \rangle } \\ { 0 } & { \quad o t h e r w i s e } \end{array} \right.
$$

其中： $\boldsymbol { \mathcal { Q } }$ 表示蚂蚁遍历一次在路径上释放的信息素的总量； $L _ { \nu }$ 为第 $k$ 只蚂蚁在本次循环中走过的路径长度。信息素浓度与路径长度成反比，即较短的路径上信息素浓度高，有更高的概率被选择。

# 2.2蚁群算法改进

由式(1)可以看出，选择概率 $p _ { i j } ^ { k }$ 与启发因子 $\eta _ { i j }$ 和信息素 $\tau _ { i j }$ 有关， $\eta _ { i j }$ 和 $\tau _ { i j }$ 的值越大，在点 $i$ 处选择点 $j$ 的概率越高。因此，蚁群算法的改进往往从启发因子和信息素更新规则两个方面进行。

# 2.2.1改进启发信息

在基本蚁群算法中，启发信息 $\eta$ 定义为两点之间距离的倒数，其目的是搜索最短路径。对于无线Mesh网来说，节点之间的距离对信息传输有一定影响，但这种影响具体体现在时延等其他QoS指标上。由于时延和丢包率可以由更加精确的方法获得，因此在该问题中无需重点考虑距离因素。

结合本文流量均衡的目的，对启发信息进行改进。本文建立的求解目标是选择负载度较小的节点和链路。因此定义启发信息：

$$
\eta _ { i j } = \frac { 1 } { \operatorname* { m a x } ( \mu _ { e } ( i j ) , \mu _ { \nu } ( j ) ) }
$$

其中：将链路负载与节点负载综合考虑，以负载度最大的值代表链路 $i j$ 的负载状况，负载较轻的链路，启发信息越大。2.2.2改进信息素更新规则

从式(2)中可以看出， $\Delta \tau _ { i j } ^ { k } ( t )$ 为第 $k$ 只蚂蚁分布于经过路径上的信息素浓度。路径的信息素更新包含两部分：原信息素挥发后的浓度以及经过链路 $i j$ 的蚂蚁所留下的信息素浓度之和。不同于一般的最短路径问题，在网络中，蚂蚁从源节点出发至停止搜索会遇到以下三种情况：

a)到达目的节点，结束搜索，且搜索的路径满足业务QoS要求，称此路径为合格路径。合格路径在之后的选择中有较高的优先级，所以增加其信息素浓度，更新规则表示为：

$$
\tau _ { i j } ( t + 1 ) = \tau _ { i j } ( t ) + \Delta \tau _ { i j } ( t )
$$

为加快算法的收敛速度，在式(5)中不考虑原信息素的挥发。信息素增量表示为

$$
\Delta \tau _ { i j } ( t ) = \left\{ \begin{array} { l l } { \displaystyle \eta _ { i j } } & { \mathrm { f l } \overrightarrow { \mathrm { H } } _ { j } \mathrm { f l } \backslash \sum _ { \overrightarrow { \mathrm { H } } } ^ { \overrightarrow { \mathrm { H } } } t \Bigg \} \backslash \mathrm { ~ \overrightarrow { / H } \overrightarrow { \mathrm { H } } \overrightarrow { \mathrm { H } } \mathrm { \overrightarrow { ~ \large ~ \cdot ~ } } \mathrm { ~ \large ~ \cdot ~ } } \mathrm { ~ \large ~ \cdot ~ } \mathrm { ~ \large ~ \sum ~ } \mathrm { f l } \mathrm { f i f } \mathrm { f i g } \mathrm { i } j } \\ { \displaystyle 0 } & { o t h e r w i s e } \end{array} \right.
$$

其中： $L _ { k }$ 为蚂蚁第 $t$ 次搜索的路径跳数，用以限制搜索路径长度，避免路径过于复杂。由 $\eta _ { i j }$ 决定信息素增量大小，目的是使路径选择逐渐倾向于负载较轻的链路。

b)未到达目的节点，但走过的路径已不满足业务QoS要求，结束搜索，称此路径为不合格路径。不合格路径中的链路时延或丢包率普遍偏大，需限制后续搜索的进入，量化到信息素更新规则上为

$$
\tau _ { i j } ( t + 1 ) = \tau _ { i j } ( t ) \times [ 1 - \frac { 1 } { L ( t ) } ]
$$

其中： $L ( t )$ 为蚂蚁第 $t$ 次搜索经过的跳数， $L ( t )$ 越小说明链路的平均QoS指标越差，此时信息素浓度下降幅度越大，从而有效限制后续搜索的进入。

c)到达目的节点，但已没有可选择的下一跳节点，结束搜索，称此路径为失效路径。失效路径主要是由算法的随机性造成的，与链路质量关联不大。对于失效路径的各个链路，保持其原有的信息素浓度；同时，为防止此路径再次被搜索到，只减小最后一跳链路的信息素浓度。更新规则为

$$
\tau _ { i j } ( t + 1 ) = \left\{ \begin{array} { l l } { \lambda ^ { L ( t ) } \tau _ { i j } ( t ) } & { i j \mathcal { \dot { J } } \mathbb { H } \mathbb { \Xi } \longmapsto \mathbb { H } \mathbb { V } \mathbb { \dot { H } } \mathbb { \dot { H } } \mathbb { \dot { H } } \mathbb { \Xi } } \\ { \tau _ { i j } ( t ) } & { \mathrm { o t h e r w i s e } } \end{array} \right.
$$

其中： $\lambda \in ( 0 , 1 )$ 定义为衰减因子， $L ( t )$ 为搜索路径的长度， $L ( t )$ 值较大的搜索结果，最后一跳链路信息素的衰减越大，通过这种方法限制路径搜索的复杂度。

# 2.2.3网关节点流量均衡

以WMN构建的接入网中，网关节点附近是流量的汇集区域，容易发生拥塞。因此，文献[20\~22]进行了mesh网关节点流量均衡的研究，为高流量的网关节点分流。但分流是一种被动的调节方式，且执行过程较为复杂，需要做进一步改进。

对于需要接入有线骨干网的业务，其目的节点在有线网络端，但没有严格限制具体通过哪个网关节点。因而可以将网关节点流量均衡与路由规划相结合，在路由规划时，优先考虑负载轻的网关节点。本章采取的方法是：执行算法前，在网络中加入虚拟节点，假设该节点到每个Mesh网关节点都是一跳的距离，且链路状态相同，如图1所示。

网关节点的选择问题可以转变为源节点到虚拟节点的路径选择，为使网关节点负载状况在路径选择中起主要作用，对式(6)作特别规定：

$$
\Delta \tau _ { i j } ( t ) = \left\{ \begin{array} { c c } { \displaystyle \frac { \eta _ { i j } + 1 / \mu _ { g } } { L ( t ) } } & { \mathrm { f i r } \underline { { \vec { u } } } _ { j } \mathrm { t j } \boldsymbol { \check { \check { \check { \mathbf { f } } } } } \boldsymbol { t } \langle \dot { \check { \mathbf { \xi } } } \rangle \langle \dot { \check { \mathbf { f } } } \rangle \mathrm { \overline { { { \check { \mathbf { H } } } } } } \boldsymbol { \pm } \mathbf { \mathcal { X } } _ { \mathbf { i } } \mathrm { \overline { { \xi } } } \mathrm { \overline { { { \check { \mathbf { f } } } } } \tilde { \pm } \mathbf { \check { \xi } } } \mathrm { \overline { { { \check { \mathbf { f } } } } } \tilde { \pm } \mathbf { \check { \xi } } } \mathrm { \dot { \check { \mathbf { H } } } } \boldsymbol { \xi } \mathrm { \check { \xi } } \mathrm { \dot { \xi } } i j } \\ { \displaystyle 0 } & { o t h e r w i s e } \end{array} \right.
$$

其中： $\mu _ { g }$ 表示网关节点的负载度。网关节点负载状况会影响整个路径信息素的更新，负载度小的网关节点对应的路径有更高的概率被选择。

![](images/c4a0a61f4a16697e92339e1a0771be3f5c25a1f790939a07450e72cb24ceabee.jpg)  
图1虚拟节点设置方式

# 3 算法执行过程

算法执行过程如图2所示。

![](images/78f24fb7e60a630e87bcc6ad20f24e4a390e00f06154d07fb3f8b865ba764f2e.jpg)  
图2算法执行过程

首先判断通信类型，若需要接入有线骨干网，则采用网关节点流量均衡机制进行路径搜索，选择负载度低的网关节点。若目的节点在Mesh网络中，则进行点到点的路径搜索。

# 4 实验验证

# 4.1实验设计

本文改进蚁群算法，着眼于路径规划上，关注的是路径的质量。因此本文实验从路径规划方面验证改进算法的效果，不涉及数据包产生过程、数据包传输过程以及路由表的更新等过程。

在 Matlab 中建立网络拓扑，用邻接矩阵表示 $X = ( x _ { i j } ) _ { N \times N }$ ，设定：

$$
\begin{array}{c} x _ { i j } = \{ 1 \atop 0  & { { \stackrel { \scriptscriptstyle + \scriptscriptstyle + } { \scriptscriptstyle \equiv } } } \end{array} { \stackrel { \scriptscriptstyle \mp \mp } { \scriptscriptstyle \boxed { \div } } } { \stackrel { \scriptscriptstyle  } { \scriptscriptstyle \equiv } } { \stackrel { \scriptscriptstyle \dag \ - } { \scriptscriptstyle \bigr - } } { \stackrel { \scriptscriptstyle \dag \ - } { \scriptscriptstyle \geq } } { \stackrel { \scriptscriptstyle \dag \ - } { \scriptscriptstyle \boxed { \operatorname { H } } } } { \stackrel { \scriptscriptstyle \dag \pm } { \scriptscriptstyle \not \equiv } } { \stackrel { \scriptscriptstyle \pm \pm } { \scriptscriptstyle \not \equiv } }
$$

相应的链路状态矩阵 $\ d { Z X } = \ d { ( z x _ { i j } ) } _ { N \times N }$ ，其中：

$$
z x _ { i j } = \{ \begin{array} { l l } { { \nVDash } } & { { \stackrel { \scriptscriptstyle + + } { \ ! } } { \underset {  } { \mathrm { \scriptscriptstyle \boxplus } } } { \mathrm { \scriptscriptstyle \sharp } } { \mathrm { \scriptscriptstyle \sharp } } { \mathrm { \sharp } } { \mathrm { \scriptscriptstyle \sharp } } { \mathrm { \sharp } } { \mathrm { \scriptscriptstyle \sharp } } { \mathrm { \emptyset } } { \mathrm { \smallskip } } \mathrm { \mathit { \emptyset } } } \\ { \infty } & { { \stackrel { \scriptscriptstyle + + } { \mathrm { \scriptscriptstyle \sharp } } } { \mathrm { \scriptscriptstyle \sharp } } { \mathrm { \scriptscriptstyle \sharp } } { \mathrm { \scriptscriptstyle \sharp } } { \mathrm { \scriptscriptstyle \sharp } } { \mathrm { \small j } } { \mathrm { \displaystyle \sharp } } { \mathrm { \ � } } { \mathrm { \scriptscriptstyle \ j } } { \mathrm { \scriptscriptstyle \sharp } } { \mathrm { \scriptscriptstyle \sharp } } { \mathrm { \scriptscriptstyle \sharp } } { \mathrm { \scriptscriptstyle \sharp } } { \mathrm { \scriptscriptstyle \sharp } } } \end{array} \}
$$

实验中，链路状态包括时延、丢包率和可用带宽。节点主要参数为缓存队列长度以及收发速率，节点位置的传输时延可以表示为

$$
T n = \left\{ \begin{array} { c c } { 0 } & { , \rho _ { r } < \rho _ { s } } \\ { \displaystyle \frac { \Phi + \rho _ { r } - \rho _ { s } } { \rho _ { s } } } & { , \rho _ { r } > \rho _ { s } } \end{array} \right.
$$

节点位置的丢包率由缓存队列溢出的数据量占比表示。

![](images/0170d98298a60ce995bcbc74176c0b65fa276adabfff4f126a8087f5ef84f07f.jpg)  
图3网络拓扑

构建如图3所示的网络拓扑图，配置30个网络节点，其中节点4、11、14、23、26为网关节点，网络初始状态的链路参数随机选取，具体参数如表1所示。

表1网络参数  

<html><body><table><tr><td>参数名称</td><td>参数值</td></tr><tr><td>链路带宽</td><td>均设为 30Kbps</td></tr><tr><td>节点转发速率</td><td>网关节点1.2Mbps，其他节 60Kbps</td></tr><tr><td>链路时延</td><td>随机取0.3ms-0.5ms之间</td></tr><tr><td>链路丢包率</td><td>随机取0-10%之间</td></tr></table></body></html>

定义 $\pi$ 为通信类型标记：

$\scriptstyle \pi = { \left\{ \begin{array} { l l } { 1 } \\ { 2 } \end{array} \right. }$ Mesh网内的点到点通信接入有线骨干网的通信

通信的源目节点随机生成，若判断 $\pi = 2$ ，则只生成源节点。数据包大小、通信允许最大时延和最大丢包率设为定值，具体参数见表2。

表2数据包参数  

<html><body><table><tr><td>参数名称</td><td>参数值</td></tr><tr><td>通信类型</td><td>1或2</td></tr><tr><td>数据分组大小</td><td>512bit</td></tr><tr><td>通信允许最大时延</td><td>4ms</td></tr><tr><td>通信允许最大丢包率</td><td>40%</td></tr></table></body></html>

为验证本文算法的流量均衡机制，采用持续向网络中注入数据包的方式，即逐个加入数据包，通过更新链路节点的状态信息反映加入数据包对网络的影响。衡量指标为网络中所有通

信路径质量的平均值。

# 4.2实验分析

首先研究衰减因子取值对本文算法的影响。实验在网络初始状态下进行，依次向网络中加入50个数据业务。λ从0.1取值到0.9，取值间隔为0.1，记录业务平均时延和平均丢包率。结果如图4所示。

![](images/661318e77408aa6f520d3009d877c37f63d4bba3fe4b7e02a572fc32a65e917f.jpg)  
图4衰减因子对算法的影响

由式(8)可以看出，衰减因子作用于失效路径，受衰减的是失效路径的最后一跳链路，从而反向迫使路径选择转向其他链路。失效路径是由算法随机性造成的，并不能说明链路的优劣程度。若衰减过大，受衰减链路会近似于断路，造成链路资源的浪费；若衰减过小，则仍然有很高的几率搜索到失效路径。从图(3)可以看出，当 $\lambda = 0 . 8$ 时，业务的平均时延和平均丢包率相对较小，之后的实验中将取 $\lambda = 0 . 8$ 0

为验证本文算法的性能，以文献[8]中心节点法和文献[9]改进信息素法为对比。持续向网络中加入100个数据包，定义链路资源占用率为网络中数据量与已用通信链路数量的比值，图5显示的是随着网络中数据量的增加链路资源占用率的变化。

![](images/36ecb61b6ec58e138fca8b5cef4dc330cae12c8de8bce2273882226f5237dcf4.jpg)  
图5链路资源占用率变化

虽然注入数据包业务的源目节点不同，但本文算法所做的路由规划，随着数据量的增加链路资源占用率稳定提高，并且维持在较低水平。而中心节点法和改进信息素法链路资源占用率较高，主要原因是这两种算法没有严格的QoS限制，也没有约束路径长度。从获取的业务平均时延和平均丢包率也可以看出这一点，如图6和7所示。

从图6、7中可以看出，本文算法的性能指标最优。一方面流量均衡为后续业务的规划提供了较好的网络环境，同时路径跳数在算法中作为一项重要的指标，可以有效限制路径长度，降低算法随机性的影响。而中心节点法和改进信息素法获得的指标较差。其原因是，这两种算法在路由度量方面都采用了加权求和的方法。这种方法存在的问题是，某项突出指标会影响其他指标的作用力；另外，加权和的最优不能保证某一项指标符合要求，因此在图6、图7中两种算法获取的平均时延和平均丢包率起伏较大。其中，改进信息素法采用控制函数对各项指标进行处理，控制函数只设定了满足和不满足业务QoS两种值，无法反映网络的真实情况，因而相较之下算法性能更差。

![](images/5f65074047503565d03baf927f6c392f2db1164f0ff3ae26a3081ccd593b8762.jpg)  
图6平均丢包率变化

![](images/d62e28f90d99d63c4378d546870f1ba6d5e43af39fe9abbbfe9d57a75a1ccf7e.jpg)  
图7平均时延变化

# 5 结束语

本文分析现有的无线Mesh网QoS研究，针对普遍缺少流量均衡的问题，提出满足业务QoS需求的流量均衡方案。通过改进基本蚁群算法，将链路和节点的负载加入到路由衡量的因素中，使路由规划倾向于负载较轻的链路。实验结果表明，本文提出的方案能保证稳定可靠的QoS指标，实现网络的流量均衡。

# 参考文献：

[1]刘永广．基于Grover 搜索的无线 mesh 网流量均衡路由算法[J].计算 机应用，2014，34（7):1956-1959.(Liu Yongguang.Traffic balancing routing algorithm for wireless mesh network based on Grover search [J]. Journal of Computer Applications,2014,34(7): 1956-1959.   
[2]张月华，孙学梅，张明伟，等．基于文化算法的无线 Mesh 网QoS 路由 算法[J]．计算机应用与软件，2012,29(11):264-268.(Zhang Yuehua, Sun Xuemei, Zhang Mingwei,et al.A QoS routing algorithm based on culture algorithm in wireless mesh networks [J].Computer Applications andSoftware,2012,29(11):264-268.   
[3]万智萍，吕志民．一种自适应物种寻优的无线Mesh网络QoS路由算法

[J]．山东大学学报：理学版，2013，48(9):10-16.(Wan Zhiping，Lv

Zhimin.A kind of adaptive species optimization of wireless mesh network QoSroung aIgorinm [J]. Journal oI Snanaong University: Natural Science,2013,48(9):10-16.

[4] 陈暄，万志平，许方恒，等．基于改进信息素的蚁群算法在QoS 组播路 由中的研究[J].计算机应用研究，2012，29(11):4296-4299.(Chen Xuan,Fang Zhiping,Xu Fangyuan,et al. Research on QoS multicast routing based on improved pheromone based ant colony algorithm [J]. Application Research of Computer, 2012, 29 (11): 4296-4299. )   
[5]Dorigo M,Maniezzo V, Colorni A. The ant system: optimization by a colony of cooperating agents [J]. IEEE Trans on Systems,1996,26(1): 1-26.   
[6]Utjahr W J. A graph-based ant system and its convergence [J]. Future Generation Computer Systems,2000,16 (8): 873-888.   
[7]Bonabeau E,Dorigo M, Theraulaz G. Inspiration for optimization from social insect behavior [J]. Nature,2000,406 (6): 39-42.   
[8] Dorigo M,Maniezo V,Colorni A. The ant system: optimization bya colony of cooperating agents [J].IEEE Transon Systems，Man，and Cybernetic,Part B,1996,26(1): 29-41.   
[9]Gambardella L M, Dorigo M. Ant-Q: a reinforcement learning approach to the traveling salesman problem [Cl// Proc of the 12th International Conference on Machine Learning.1995,252-260.   
[10]黄书强，周继鹏．基于聚类的无线 Mesh 网关选择及 AP 分组算法[J] 华南理工大学学报：自然科学报,2011,39 (4):38-43.(Huang Shuqiang, Zhou Jipeng. Wireless mesh gateway selecting and ap clustering algorithm based onclustering[J].JournalofSouth China Universityof Technology: Natural Science Edition,2011,39 (4):38-43.)   
[1]乔宏，张大方，谢鲲，等．分布式多网关无线 mesh 网公平协作路由算 法[J].通信学报，2015，36(2):201504601-201504611.(Qiao Hong, ZhangDafang，Xie Kun,et al.Distributed fair cooperative routing in multi-gates wireless mesh network [J].Journal on Communications,2015, 36 (2): 201504601-201504611. )   
[12]廖勇，杨士中，杨力生，等．无线 Mesh 多网关接入链路调度时间下限 计算方法[J].北京邮电大学学报,2011,34(2):50-55. (Liao Yong,Yang Shizhong,Yang Lisheng,et al.A calculation method of minimum link scheduling time lower limit for wireless mesh multi-gateway access [J]. Journal of Beijing University of Postsand Telecommunication,2011,34 (2): 50-55.)   
[13] Bell.Failure to thrive: QoSand the culture of operational networking [C]// Proc of ACM SIGCOMM Workshop on Revisiting IP QoS. New York, ACMPress,2003:115-120.   
[14] Mohapatra P,Li J,Gui C.QoS in mobilead hoc networks[J].IEEE Wireless Communications,2003,10 (3): 44-52.   
[15] Intra-vehicular sensor networks [C]//Proc of IEEE INFOCOM. Phoenix: IEEE Communications Society,2008:121-126.   
[16] Akyildiz IF, Wang XD, Wang WL. Wireless mesh networks: a survey [J]. Computer Networks,2005,47(4): 445-487.   
[17]Hsiao PH,Hwang A,KungHT,etal.Load-balance routing for wireless access networks [C]// Proc of the 2Oth Joint Conference of the IEEE Computer & Communications Societies.2002:986-995 vol.2.   
[18] Bodas S，Shakkottai S,Ying L，et al.Low-complexity scheduling algorithms for multichannel downlink wireless networks [J].Proceedings IEEE INFOCOM,2010,20 (5):1-9   
[19]Braden R,Clark D,Shenker S.RFC1633,Integrated services in the Internet architecture:an overview [R].1994.   
[20]Heinzelman WB,Chandrakasan A P,Balakrishnan H.An application specific protocol architecture for wireless microsensor networks [J].IEEE Trans on Wireless Communications,2002,1(4):660-670.   
[21]Ruscelli AL,Cecchetti G,Alifano A,et al.Enhancement of QoS support of HCCA schedulers using EDCA function in IEEE 802.11e networks [J].Ad hoc Networks,2012,10 (2): 147-161.   
[22] Kim S,Huang R,Fang Y.Deterministic priority channel access scheme for QoS support in IEEE 8O2.1le wireless LANs[J].IEEE Trans on Vehicular Technol0gy,2009,58 (2): 855-864.   
[23] Deng Qianhua,Cai A.A TXOP-based scheduling algorithm for video transmission in IEEE 8O2.11e networks [C]//Proc of the 6th International Conference on ITS Telecommunications.20o6: 573-576.