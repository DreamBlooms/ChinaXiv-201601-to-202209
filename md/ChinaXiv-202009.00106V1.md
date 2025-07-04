# 基于公交轨迹和定位信息的地域群播算法研究

林苗苗，樊秀梅

(西安理工大学 自动化与信息工程学院，陕西 710048)

摘要：在车联网的应用中，地域群播可形成区域广播来传送和地理位置相关的商业信息、广告等，或发送紧急消息到指定区域等实际应用。传统的地域群播算法大多数在WSN中使用，没有考虑到道路路网和车辆轨迹信息，没有很好的适用于车联网中的群播需求。基于目前的一些商业需求，引入了公交车的轨迹信息，提出了一种基于公交轨迹的地域群播算法。第一阶段先建立公交节点的的轨迹树以及相遇模型，再根据相遇图计算公交节点对目标区域的消息转发能力，选择具有更高消息转发能力的节点转发消息到目的区域。第二阶段使用稳定性指数来估计两辆车的稳定性，在目的区域的每条街道上建立一个车辆集，通过建立和维护车辆集达到群播的目的。在联合仿真平台SUMO和OMNET $^ { + + }$ 下仿真，其实验结果分析表明：随着车辆数目增加，该算法在维持高的数据包投递率情况下可以将整网的传输开销降低，达到预期的目标。

关键词：车联网；地域群播；公交轨迹；相遇模型 中图分类号：TP339 doi:10.19734/j.issn.1001-3695.2020.02.0042

Research on geocasting algorithm based on bus trajectory and positioning information

Lin Miaomiao, Fan Xiumeit (Xi'an UniversityofTechnology,SchoolofAutomation&Information Engineering Shanxi 710048,China)

Abstract:Intheapplicationofthe Internetof Vehicles,thegeocasting can formaregional broadcast totransmit business information and advertisements related to geographical location,or send emergence messges to specific areas and other parcticalappications.Mostofthetraditionalgeocastingalgorithmsareusedin WSN,whichdoes notconsider theroadnetwork andvehicle trajectory information,and is not wellsuitedfor theneedsofmulticastintheInternetofVehicles.Basedonsome current businessneeds,this paper introduces thetrajectory informationofbuses,and proposesageocastingalgorithmbased onthetrajectoryofbuses.Inthefirststage,this paper established thetrajectory treeofthebus node andtheencounter mode andthencalculatethe messageforwardingabilityofthebus node tothetargetareabasedontheencountergraph,andselecta node with a higher messge forwarding abilitytoforwardthe message tothe destinationarea.In the second stage,this paper use thestability indextoestimatethe stabilityof thetwo vehiclesandestablishavehiclesetoneach street inthedestination area,toachieve the purpose of group broadcasting by establishing and maintaining thevehicle set.The simulation on the experimental platform SUMO and OMNET $^ { + + }$ shows that the algorithm can reduce the transmission overhead of the entire network and achieve the expected goal while maintaining ahigh packet deliveryrate as the numberofvehicles increases.

Key words: Internet of vehicles; geocasting; bus trajectory ;encounter model

# 0 引言

车联网是以车内网、车际网和车载移动互联网为基础，按照约定的通信协议和数据交互标准，在车-X(X：车、路、行人及互联网等)之间，进行无线通信和信息交换的大系统网络，是能够实现智能化交通管理、智能动态信息服务和车辆智能化控制的一体化网络，是物联网技术在交通系统领域的典型应用。车联网是一种有很大挑战的技术，可支持很多安全信息和娱乐信息的应用程序，在V2X通信的发展下，车联网可以实现包括自动驾驶，交通信息共享，和车辆安全等多种功能。与5G等通信方式相比，车联网在硬件部署和费用方面具有巨大优势，车联网中还可以利用路边单元形成雾节点进行雾计算，减少云计算的负担，所以车联网可以成为智慧城市中数据交换平台，并在很多领域发挥巨大作用[]。

在车联网中，城市中公交车车辆和出租车辆具有重要地位，假设每个车辆都配备OBU设备，可以采集车辆的动态和静态信息，例如车辆速度、加速度和车辆位置，并进行实时交互和监控，为人们提供综合性服务。车联网的发展可以为未来智能车辆交通系统提供很大的机遇，例如在无人驾驶中，在极端天气例如暴风雨和雪天，路边的标示被遮盖无法识别，这时车辆可以利用车联网技术获得共享交通、道路信息和交通灯信息，使得驾驶员可以提前了解前方车辆道路情况，避免交通事故和交通拥堵。另外，车联网中的车辆节点不断与路边单元和基站不断交互通信，协助交通管制部门实时收集交通道路车辆信息，有助于交通部门进行交通管制和调度。在车联网内的乘客或用户如果有网络需求，可以实时接入车联网获得娱乐服务或紧急办公，提高了工作效率和娱乐性[2]。

在车联网中，地理广播[3]是一种特殊的地域群播(geocast)是从源点传递消息到一给定目标地理区域内的所有节点。这是针对多种车载网络应用程序的基本服务内容，地域群播可形成区域广播来传送和地理位置相关的商业信息、广告等，或发送紧急消息到指定区域等实际应用，为了降低发生车祸的风险并避免交通拥堵，车联网中的许多应用程序都设计为通过地域群播在特定地理区域中传输消息。地域群播有许多具有娱乐信息的应用。它可形成区域广播来传送和地理位置相关的商业广告等，例如为到达某一地理区域的交通工具发送该范围内的停车场位置和空闲车位等信息或基于位置的商业广告的分发(星巴克向周围发送优惠券)。另外发送紧急消息到指定区域也是一个重要应用，例如在发生交通事故时向周围区域的车辆发送警告信息[4]。

# 1地域群播算法已有研究成果

# 1.1已有的地域群播算法分类

地域群播在WSN中得到了很好的研究。WSN的地域群播算法可以分为基于数据传输的协议，基于路由创建的协议和基于地理位置的协议。

# 1.1.1基于数据传输的协议

基于数据传输的协议可分成基于位置的多播算法(LBM)[5]，当节点收到地理广播数据包时，如果它在转发区内，它会将数据包转发给它的邻居，否则，它将丢弃该数据包。因此，如何定义转发区成为该方案的关键点，覆盖源节点和地域群播区域的最小矩形定义了转发区域；基于voronor图的地域群播算法，基于Voronoi图的地理定位协议的目标是提高成功率并减少LBM的跳数和洪泛率；基于网格的GeoGrid算法，此协议称为GeoGRID，将MANET的地理区域划分为2D逻辑网格。每个网格是大小为 $\mathrm { d } \times \mathrm { d }$ 的正方形，在GeoGRID中，在每个网格中选择一个网关节点。转发区域由源和地理广播区域的位置定义[6]。

# 1.1.2 基于路由创建的协议

基于路由创建的地域群播算法分为GeoToRA和基于Mesh的地理定位路由。GeoTORA7使用单播路由协议TORA(Temporally Ordered Routing Algorithm)将地理广播数据包发送到地理广播区域。TORA是一种基于“链路反转”算法的分布式路由协议。基于Mesh的地理定位路由协议通过控制数据包创建冗余路由，而不是洪泛数据包。

# 1.1.3基于地理位置的协议

已经有几种基于位置的车辆自组织网络路由算法，贪婪周界无状态路由(GPSR)是一种典型的基于位置的贪心转发算法。节点将消息转发到其通信范围内距离目的地最近的邻居一些算法，例如GSR和GPCR，使用Dijkstra 算法确定一系列道路交叉点以连接源和目的地。基于位置的路由算法可以应用于地域群播，但是性能较差，因为它们不将目标区域视为整体。此外，这些算法的大多数需要高密度的车辆，本文提出的算法定位于在车联网中利用地理定位并利用轨迹来计算适当的参数进行度量[8]。

# 1.2基于车辆轨迹的的路由协议

上述这些地域群播算法大多数针对了传统的无线传感网络，并没有考虑到城市道路的复杂情况。JaehoonJeong提出了利用车辆轨迹信息来增强固定基站和移动车辆之间的路由性能。Y.Wu基于当前位置和历史轨迹预测未来轨迹并改善数据包传递。相比之下，本研究不需要完整的车辆轨迹，车辆轨迹通过车辆之间的相遇逐渐扩散到整个网络。文献[8]提出了一种基于公交车骨干网的改进区域路由协议，改进路由协议在传统区域路由协议的链路状态更新数据包中增加两个字段，用于存放簇头节点和目的节点的位置信息。在簇外路由发现阶段，依据簇头节点和目的节点的位置信息构建位置约束方程，用于选择合理的外围节点进行数据转发任务，剔除其他外围节点的冗余通信。

# 2 概念和定义

基于上述在车联网方面地域群播算法(Geocasting)的研究现状，发现传统的地域群播算法并未考虑城市车联网环境下的道路拓扑和车辆的移动轨迹，只是在定义转发区域时有不同的方式。Geocasting分为两个阶段，第一个路由阶段(从源到目的区域的消息转发)，第二个阶段在目的区域中持续广播信息。本文工作如下：

a)分析了城市交通中的重要群体公交车之间相遇的模式，利用公交车之间线路的重合及不同时间段之间的相遇概率，提出了基于公交车的地域群播技术，利用车辆的轨迹信息降低车辆移动性的不确定性来改善分组传递。

b)在Geocast的第一个阶段，提出一种节点消息转发能力的概念，可以根据车辆之间的局部相遇有效地使用车辆轨迹。通过地理相遇图，可以将数据包转发到具有更高传输能力的车辆，在第一阶段中，如果至少一个载有消息的车辆穿过目标区域中的任何路段，则认为消息的投递是成功的。

c)在Geocast的第二阶段，使用稳定性指数来估计两个车辆节点的稳定性，在目的区域的的每条街道上建立一个车辆集，使用车辆集的建立和维护机制，保障经过目的区域的车辆需要传递消息时可以通过一跳交付消息。

定义车辆节点向目标区域的消息转发能力 $C _ { P }$ 。量化车辆节点向目的区域的的消息转发能力，车辆轨迹对目的区域的到达情况可以分为直接到达和间接到达。直接到达是指车辆轨迹直接驶入目的区域，间接到达是指车辆通过与其他车辆的相遇，其他车辆的轨迹到达目标区域。车辆 $\nu _ { \mathrm { { l } } }$ 在目的区域上的消息转发能力被定义为其扩展的车辆轨迹的覆盖范围与目的区域重叠的概率。

$C _ { p } = \operatorname* { P r } \{ \phi _ { \mathrm { v } }$ overlaps $| d \}$ 其中 $\phi _ { \nu }$ 为车辆的扩展到达能力。若如果 $\phi _ { \nu }$ 仅包括 $\nu _ { 1 }$ 自己的到达情况，则可以表示为 $C _ { p } = 1$ 。如果$\phi _ { \nu }$ 进一步有间接到达的情况，则 $C _ { p }$ 的计算变得更加复杂，这取决于 $\nu _ { 1 }$ 与其他车辆之间的相遇的发生。

如图1所示，车辆 $\nu _ { 1 }$ 具有三个可能的扩展路径以到达其到目的区域的。分别用 $\beta _ { 1 } , \beta _ { 2 } , \beta _ { 3 }$ 表示目的区域内三条路径。是否将部分 $\beta _ { i }$ 包含在 $\nu _ { \mathrm { { l } } }$ 的到达范围内是概率性的。设该概率为$p ( \beta _ { i } )$ 。然后， $C _ { p }$ 可以计算为

$$
C _ { p } = 1 - \prod _ { i = 1 , 2 , 3 } ( 1 - P ( \beta _ { i } ) )
$$

![](images/7e5e08a4772d899f55677f10aca66ee5d5f1d91ddf49120f91052985eff8a222.jpg)  
图1节点转发能力的计算图  
Fig.1Calculation diagram of node forwarding capability

计算 $C _ { p }$ 需要得到所有可能到达目的区域的路径扩展集合 $\Omega _ { \nu } = \{ \eta _ { i } | i = 1 , 2 ^ { . . . n \} }$ ，其中 $\eta _ { i }$ 表示每条可以到达的扩展路径集合。通过路径 $\eta _ { i } \in \Omega _ { \nu }$ 将 $\beta _ { i }$ 包含在 $\nu _ { \mathrm { { l } } }$ 的覆盖范围内的概率，需要建立地理相遇图，它有助于计算 $p ( \beta _ { i } )$ 并找到所有扩展路径

# 2.1建立地理相遇图

由 $\nu$ 维持的地理相遇图，由 $G ( \nu ) = \{ X ( \nu ) , E ( \nu ) \}$ 表示，其中$X ( \nu )$ 表示顶点集合， $E ( \nu )$ 表示边集。它维护 $\nu$ 已知的所有轨迹以及这些轨迹上的地理位置之间可能的相遇。首先定义一个到达时间车辆 $\nu$ 在路径上的给定位置I处的到达时间(表示为 $t _ { \nu } ^ { I }$ )被定义为车辆 $\nu$ 到达位置I时的绝对时刻。假设 $\nu$ 已经获得一组车辆轨迹 $\varphi ( \nu )$ ，对于每个 $T _ { a } \in \varphi ( \nu ) , \forall r _ { k } ^ { a } \in T _ { a } , r _ { k } ^ { a } \in X ( \nu )$ ，每个顶点 $r _ { k } ^ { a }$ 都具有 $t _ { \nu } ^ { I }$ 的到达属性。 $E ( \nu )$ 含有两种边，单向边 $\vec { \mathbf { \sigma } } _ { e } ^ { \vec { \mathbf { \sigma } } }$ 和双向边 $\mathbf { \Psi } _ { e }$ ，单向边是车辆a在其轨迹上从 $r _ { i } ^ { a }$ 行驶到 $r _ { i + 1 } ^ { a }$ ，双向边代表 $\boldsymbol { \mathscr { e } }$ 在两个路段 $r _ { i } ^ { a } \in T _ { a } , r _ { j } ^ { b } \in T _ { b }$ 之间。如图2所示，B车的轨迹 $r _ { 3 }  r _ { 4 }$ 属于单向边。 $T _ { a }$ 顶点 $r _ { 2 }$ 和 $T _ { b }$ 顶点 $r _ { 2 }$ 之间存在双向边。E(v)中的每个边缘具有权重 $P ( e ) \leq 1$ 。相同轨迹的两个路段之间的每个单向边缘e具有权重 $P ( e ) = 1$ 。 $r _ { i } ^ { a } \in T _ { a }$ 和 $r _ { j } ^ { b } \in T _ { b }$ 之间的每个双向边e具有权重 $P ( e ) < 1$ ，表示当它们分别在道路$r _ { i } ^ { a }$ 和 $r _ { j } ^ { b }$ 上时a和b之间的相遇概率。

![](images/54cc2d7636838e4d1f7cd7e53c3e06c25d3915e7b22f278e7ec3cc7395a91815.jpg)  
图2车辆之间的相遇模式

# 2.2车辆之间的相遇模式和相遇模型

理想情况下，公交车运行路线统一，到达每个路口的时间一定，这样容易建立相遇模型，但实际情况道路交通复杂和受红绿灯的影响，公交车到达每个路口的时间有波动，所以建立一个具有波动时间的公交车相遇模型。本相遇模型可以分为两种时间阶段：周内模式和周天模式，在周内由于有早高峰阶段，所以考虑到公交车延迟，可以将公交车到达路段的时间波动范围调大，将所有可能引起公交车延迟的因素考虑进去。

由于驾驶员的习惯和其他因素的影响，每个轨迹记录交叉点的ID号以及车辆节点通过的时间。假设在 $< 7 { : 0 0 - 8 : 0 0 > }$ 之间，车辆v有3条轨迹，则可记录为$< \mathrm { T } 2 , \mathrm { T } 4 , \mathrm { T } 6 > , \mathrm { T } 2 = < ( \mathrm { I } 1 , 7 ; 0 0 ) , ( \mathrm { I } 2 , 7 ; 1 5 ) > , \mathrm { T } 4 = < ( \mathrm { I } 2 , 7 ; 1 5 ) , ( \mathrm { I } 3 , 7 ; 5 0 ) >$ （204号 $, \mathrm { T } 6 { = } { < } ( \mathrm { I } 3 , 7 { : } 5 0 ) , ( \mathrm { I } 4 , 8 { : } 0 0 ) >$ ，这样可以建立节点的轨迹树。

为了解决公交车运行的时间偏差问题，本文假定一辆公交车通过某一路口的时间在某个范围内上下波动，并且这个时间波动情况符合正态分布。假设公交车到达路口I的时间为t， $t$ 的上下限设为 $t _ { l } , t _ { h }$ ，所以 $t \in [ t _ { l } , t _ { h } ]$ ，一个变量服从正态分布，那么概率密度函数为

$$
f ( x ) = { \frac { 1 } { \sqrt { 2 \pi } \sigma } } \exp ( - { \frac { ( x - \mu ) ^ { 2 } } { 2 \sigma ^ { 2 } } } )
$$

对于轨迹彼此相交的两个车辆，相遇的概率由他们到达 轨迹交叉点的到达时刻的接近程度来判断，本文将公交车之 间的相遇分为3种情况。

第一种情况下，两辆车在同一路段上且行驶方向相同，如公交车A和公交车C在 $r _ { 2 }$ 路段上相遇，假设A到达路口服从 $[ \mu _ { A } ^ { 2 } , \sigma _ { A } ^ { 2 } ]$ ，C到达路口服从 $[ \mu _ { B } ^ { 2 } , \sigma _ { B } ^ { 2 } ]$ 。

$$
\begin{array} { r l } & { P = P \{ \Delta ( t _ { A } ^ { 2 } , t _ { C } ^ { 2 } ) < \delta \} } \\ & { = \displaystyle \int _ { 0 } \int _ { t - \delta } f _ { t _ { A } ^ { 2 } } ( t ) f _ { t _ { C } ^ { 2 } } ( t ) d t d t \cdot } \\ & { = \displaystyle \int _ { 0 } \int _ { t - \delta } \frac { 1 } { 2 \pi \sigma _ { A } ^ { 2 } \sigma _ { B } ^ { 2 } } \exp ( - \frac { ( t _ { A } ^ { 2 } - \mu _ { A } ^ { 2 } ) ^ { 2 } } { 2 \sigma _ { A } ^ { 2 } } ) \exp ( - \frac { ( t _ { B } ^ { 2 } - \mu _ { B } ^ { 2 } ) ^ { 2 } } { 2 \sigma _ { B } ^ { 2 } } ) } \end{array}
$$

第二种情况下，两辆车在同一路段上行驶方向不同，如公交车A和公交车 $\mathbf { B }$ 在 $r _ { 4 }$ 路段上相遇。

如图3所示公交车A到达1路口时刻为 $t _ { A } ^ { 1 }$ ，到达2路口

时刻为 $t _ { A } ^ { 2 }$ ，公交车B到达1路口时刻为 $t _ { B } ^ { 1 }$ ，到达2路口时刻为 $t _ { B } ^ { 2 }$ 。其中 $t _ { A } ^ { 1 } \sim N ( \mu _ { 1 } , \sigma _ { 1 } ) , t _ { B } ^ { 2 } \sim N ( \mu _ { 2 } , \sigma _ { 2 } )$ ，将另外两个时刻设置为到达的预期时刻。 $t _ { A } ^ { 1 } \mathcal { \bar { F } } [ \left| t _ { B } ^ { 2 } \right.$ 的密度函数为，

$$
\begin{array} { c } { { f ( t _ { A } ^ { 1 } ) { = } { \displaystyle { \frac { 1 } { \sqrt { 2 \pi } } } } { \sigma } _ { 1 } \displaystyle { \exp ( - { \frac { ( t _ { A } ^ { 1 } - \mu _ { 1 } ) } { 2 { \sigma } _ { 1 } ^ { 2 } } } ) } } } \\ { { f ( t _ { B } ^ { 2 } ) { = } { \displaystyle { \frac { 1 } { \sqrt { 2 \pi } } } } { \sigma } _ { 2 } \displaystyle { \exp ( - { \frac { ( t _ { B } ^ { 2 } - \mu _ { 2 } ) } { 2 { \sigma } _ { 2 } ^ { 2 } } } ) } } } \end{array}
$$

所以相遇概率为，

$$
\begin{array} { l } { P = P \{ t _ { A } ^ { 1 } \leq t _ { B } ^ { 1 } \cap t _ { B } ^ { 2 } \leq t _ { A } ^ { 2 } \} } \\ { = \displaystyle \int _ { - \infty } ^ { t _ { A } ^ { 2 } } \displaystyle \int _ { - \infty } ^ { 1 } \frac { 1 } { 2 \pi \sigma _ { 1 } \sigma _ { 2 } } \exp ( - \frac { ( t _ { A } ^ { 1 } - \mu _ { 1 } ) ^ { 2 } } { 2 { \sigma _ { 1 } } ^ { 2 } } ) \exp ( - \frac { ( t _ { B } ^ { 2 } - \mu _ { 2 } ) ^ { 2 } } { 2 { \sigma _ { 2 } } ^ { 2 } } ) } \end{array}
$$

![](images/03187bce964c2517a3914763214a6a4a9a1421c5c253a07f8242197535b978ad.jpg)  
Fig.2Encounter mode between vehicles   
图3公交车相遇图  
Fig.3Bus encounter map

第三种情况下，两辆不同方向上的车在交叉路口相遇，如公交车B和公交车C在交叉路口I2相遇。

$$
\begin{array} { r l } & { P = P \{ \Delta ( t _ { B } ^ { 2 } , t _ { C } ^ { 2 } ) < \delta \} } \\ & { = \displaystyle { \int _ { 0 } ^ { \infty } \int _ { t - \delta } f _ { t _ { B } ^ { 2 } } ( t ) f _ { t _ { C } ^ { 2 } } ( t ) d t d t } . } \\ & { = \displaystyle { \int _ { 0 } ^ { \infty } \int _ { t - \delta } ^ { t + \delta } \frac { 1 } { 2 \pi \sigma _ { c } ^ { 2 } \sigma _ { B } ^ { 2 } } \exp ( - \frac { ( t _ { C } ^ { 2 } - \mu _ { C } ^ { 2 } ) ^ { 2 } } { 2 \sigma _ { c } ^ { 2 } } ) \exp ( - \frac { ( t _ { B } ^ { 2 } - \mu _ { B } ^ { 2 } ) ^ { 2 } } { 2 \sigma _ { B } ^ { 2 } } ) } } \end{array}
$$

# 2.3定义稳定性指标

车辆节点稳定性指标用于测量两个车辆之间的链路稳定性，考虑链路的持续时间。假设车辆j是车辆i的邻居节点并且它们在同一条街道上，车辆 $\mathrm { j }$ 和 $\mathbf { k }$ 之间的稳定性估计指数可以如下计算：

$$
I ( i , j ) = \frac { D _ { i , j } } { \mid \stackrel {  } { \nu _ { i } } - \stackrel {  } { \nu _ { k } } \mid }
$$

其中R是车辆的通信范围，若车辆接近行驶，有两种情况，车辆i和j朝向彼此行驶；车辆i和 $\mathrm { j }$ 在相同方向上行驶，后方车辆速度更快。在这两种情况下，车辆之间链接中断的距离为

$$
D _ { i , j } = R + d _ { i , j }
$$

若车辆分离行驶，有两种情况，车辆i和j彼此远离；车辆i和j在相同方向上行驶，前方车辆速度更快。车辆之间链接中断的距离为

$$
D _ { i , j } = R - d _ { i , j }
$$

# 3 基于公交轨迹和定位信息的地域群播算法

# 3.1基于节点消息转发能力的车辆路由算法

本文提出的地域群播算法分为两个阶段，第一个阶段通过公交车节点之间的相遇将消息转发到目的区域，如图4所示。在这个阶段内，分为以下几步：

a）首先初始化地图和车辆轨迹，本次实验选择西安地区的地图，共计5736个路段，2722个道路交叉点。

b）判断源节点的邻居节点中是否有公交车节点，若有则建立地理相遇图，计算每个节点的消息转发能力，若无则依靠普通车辆转发消息。如果依靠普通节点则选择邻居车辆节点中离目的区域中心最近的普通车辆节点。

c）计算节点的消息转发能力，选择消息转发能力最强的

节点转发消息。

d)判断是否有节点到达目的区域，若有结束该过程，若无则执行步骤b）。

# 3.2基于稳定性指数的地域群播算法

在地域群播的第二个阶段，使用稳定性指数来估计两辆车的稳定性，在目的区域的的每条街道上建立一个车辆集。通过车辆集，经过目的区域的车辆需要传递消息时可以通过一跳交付消息，从而避免多跳广播产生的显著开销，若未接收到消息的车辆未能从刚经过的车辆中获得消息，它仍然可以从它将遇到的后续车辆集接收到消，因此提高了消息的接收率。

# 3.2.1车辆集合(vs)的设置

在车联网中，由于街道宽度的限制，广播只需要选择一个邻居节点作为沿广播方向的下一个的中继节点。假设 $\nu _ { i }$ 是在街道段中成功接收到广播消息的第一个车辆， $\nu _ { i }$ 计算每个邻居车辆的稳定性估计指数并选择具有最高稳定性估计指标的邻居车辆作为下一个车辆集车辆。然后 $\nu _ { i }$ 转发包含所选邻居节点ID和要发送的广播消息并设置等待计时器，如果所选择的邻居节点成功接收到该信息，则它重复该选择过程并将该消息转发给下一个选择的车辆集车辆。如果 $\nu _ { i }$ 未收到其选择邻居节点的消息，则表示该邻居未成功转发该消息，当$\nu _ { i }$ 的等待计时器到时后， $\nu _ { i }$ 重新计算稳定性估计指数，重新进行选择下一个车辆集车辆。图5为车辆集设置的流程图。

![](images/1fde92af450c1ed250409bb043f259aa740793ea06b0b154c85d3fd6ad158f3d.jpg)  
图4算法流程图  
图5车辆集合设置流程图  
Fig.4Algorithm flowchart 3.2.2车辆集的维护   
Fig.5Flowchart of vehicle setting

由于车辆网中的车辆具有高移动向，车辆载体集中的车辆位置不断变化，随着车辆的移动，车辆集中的车辆之间的链接可能会断开，此时需要在车辆集中加入新的车辆。在通常情况下，车辆集中的车辆在该组中存在两个邻居节点且在不同的方向上。如果车辆集中的一个车辆节点通过信标消息检测到该集合中的一个邻居节点已经离开其通信范围，则车辆在该方向上重新选择具有最高稳定性的车辆节点加入车辆集，然后发送消息通知新加入的车辆。如图6所示，开始时，$\nu _ { i }$ 和 $\boldsymbol { \nu } _ { j }$ 在同一个车辆集，随着时间的推移， $\nu _ { j }$ 远离 $\nu _ { i }$ 的通信范围，两个节点之间的链接断裂， $\nu _ { i }$ 重新计算其邻居节点的稳定性指标并选择新的车辆 $\nu _ { k }$ 作为车辆集车辆。

![](images/2e23b185949a4fa4861be460a7d2ec2d2e4ac401eec1b4d5a1c53a2866bb45cc.jpg)  
图6车辆集的维护  
Fig.6Maintenance of the vehicle set

# 4 仿真实验与结果分析

# 4.1环境及参数设置

本文通过OMNeT $^ { + + }$ 和SUMO仿真软件对所提出的方法的性能进行仿真和验证，SUMO软件是开源的便于路网导入，本次实验选择西安地区的地图，共计5736个路段，2722个道路交叉点，最多设置了1200个车辆节点，其他仿真参数如表1所示。

表1公交车辆节点移动轨迹参数  
Tab.1Parameters of trajectories of bus nodes   

<html><body><table><tr><td>内容</td><td>数值</td></tr><tr><td>仿真区域</td><td>4000*4000m</td></tr><tr><td>仿真时间</td><td>43200s</td></tr><tr><td>车辆节点类型</td><td>Car,Bus</td></tr><tr><td>车辆节点数量</td><td>200-1200</td></tr><tr><td>车辆运行速度</td><td>0 m/s~30m/s</td></tr><tr><td>场景更新时间</td><td>0.1s</td></tr><tr><td>节点缓存</td><td>300M</td></tr><tr><td>通信范围</td><td>200m</td></tr><tr><td>网络带宽</td><td>2M/s</td></tr></table></body></html>

在本次仿真中，每辆车辆具有消息生成能力，消息的目标区域区域为正方形，并且在整个道路网络上随机选择。对于每次参数配置执行100次仿真取平均值。在第一个阶段采用的对比算法是Epidemic 路由算法，每当遇到其他没有接受到消息的车辆时，车辆都会盲目转发消息，该算法的主要缺点是产生高的传输开销。NTR 算法[22],NTR首先根据每个车辆节点的轨迹数据建立其轨迹树。利用这种轨迹树，预测每辆车的未来位置，并得出其与所有其他车的接触可能性。还有文献[8]提出的IPBB算法；在第二个阶段采用的对比算法是LINGER[23]算法，它是在最小化协议开销的情况下在车辆网中分发消息。

# 4.2仿真结果

在该算法的第一个阶段，本文从两个方面来评价该算法，投递率：目的节点收到的数据包与源节点发送出的数据包数量的比值;传输开销：信息在网络传输过程中进行数据及交换和数据包转发所消耗的网络能量。

图7描述了随着车辆数从200增加到1200，四种不同算法的数据包投递率关系图，总体来说随着车辆数的增加，本文提出的算法BTGR呈现出较高的投递率，而Epidemic 路由算法由呈现降低的趋势，这是由于在车辆节点增多后，该算法盲目转发的节点增多，但是每个车辆的数据缓存为固定的 $3 0 0 ~ \mathrm { { M } }$ ，从而导致网络拥塞，数据包无法正常转发，导致数据包投递率下降。在400个节点以下的情况下，由于公交车节点过少，公交车之间的相遇变少，导致可到达的链路变少，所以投递率略小于NTR和IPBB 算法。其中普通车辆节点和公交车车辆节点数目为3:1，消息生成速率为每分钟2条

![](images/f58c05668f0d01508103daebb6af6d1ac4b772ae2b46f06a34dd09d376d1804f.jpg)  
图7不同车辆数对投递率的影响

Fig.7The impact of different vehicle numbers on the delivery rate图8描述了网络传输总的路由开销与车辆节点数关系图，该图中 Epidemic 由于感染方式使得开销爆炸式增长，相比于其他三个方法相差过多。本文提出的方法在节省路由开销方面效果良好，因为消息只在目标区域内进行广播所以减少了传输开销。

![](images/16e595758c6c3d277fbb9600af980fa94c831347dbb474301989854d7b08f03d.jpg)

图9描述了不同消息生成速率对投递率的影响(车辆数为800)，消息生成速率为每分钟生成1条到每分钟生成6条，可以发现，当消息生成速率大于每分钟两条消息时，BTGR优于其他方法。当网络流量相对较慢(每分钟少于两条消息)时，Epidemic具有最佳性能。这是因为Epidemic积极复制消息并充分利用网络容量，但是随着通信量的持续增加，由于网络容量始终有限，Epidemic传输效率急剧变差。

![](images/3ad2766f1cb82f075821ddd52730ed76fc4d43b5463910c051bcd49c52b10fad.jpg)  
图8不同车辆数对传输开销的影响  
图9不同消息生成速率对投递率的影响  
Fig.9Effect of different message generation rates on delivery rate

图10描述了不同的消息生成速率对传输开销的影响，可以发现，BTGR的传输开销始终比其他算法低。随着消息生成速率的增加，所有算法的传输开销都会变小。主要原因如下，在车辆数量稳定的情况下，总联系的节点也保持稳定。随着生成更多消息，它们争夺联系节点的有限资源。减少了不必要的传输，因此平均传输开销也减少了。

![](images/dde182e774c16d0d9c06d87bcdc6766b9e167cf1aa043e68b00bb13e1539f1f3.jpg)  
图10不同消息生成速率对传输开销的影响Fig.l0The impact of different message generation rates ontransmission overhead

图11描述了随着车辆数从200增加到1200，四种不同算法的平均端到端时延关系图，本文提出的算法BTGR在前期车辆数目少于800辆的时候，由于仿真区域过大，而投入的公交车节点少，无法充分利用公交车节点之间的相遇导致时延大，但车辆数目大于800辆的时候，投入公交车数量多，所以时延降低。Epidemic 算法是盲目的洪泛转发发消息，直到目的节点，所以时延变化不大。IGBB算法也是利用公交车作为簇首节点，前期车辆少，该算法无法发挥优势。NTR算法是利用车辆之间的轨迹来建立从源节点到目的接节点的链路，所以随着车辆密度的增大，可用链路增多，导致时延变小。

![](images/8d175115f380dba9700331df7b4b859814ae89822f1121e0ba21a57730b9944b.jpg)  
Fig.8The impact of different vehicle numbers on transmission overhead   
图11不同车辆数对平均端到端时延的影响  
Fig.11The impact of different vehicle numbers on end -to-end latancy

图12描述了不同消息生成速率对平均端到端时延的影响(车辆数为800)，当消息生成速率大于每分钟两条消息时，BTGR优于其他方法，但是随着消息生成速率的增加，四种算法的平均端到端时延都增加，这是因为在车辆数稳定的情况下，车辆节点在争夺有限的资源，所以算法性能变差。

在该算法的第二个阶段本文将数据包传输率作为主要性能指标。数据包传输率定义为一段时间内目标区域中接收到消息的车辆数与通过目标区域的车辆数的比值。

图13描述的是第二阶段不同车辆数对数据包传输率的影响，当车辆通过目的区域街道时，即使车辆集合中的第一个车辆成员未能及时发送消息，其他车辆集合的成员可以在其他车辆行驶在该街道时将消息传递给它，提高了数据包传输率。

![](images/babb3a7d1085b28583c6fde81eeb49fbcd89f382aacea89b573dca1f5d1e8f23.jpg)  
图12不同消息生成速率对平均端到端时延的影响

![](images/cb777cda4bbd4224fedaf0ab05901225e033545cb4838044e961c5f0a53bb055.jpg)  
Fig.12Effect of different message generation rates on end -to-end latancy   
图13不同车辆数对数据包传输率的影响  
Fig.13Effect of different vehicle numbers on packet transmission rate

# 5 结束语

本研究基于传统的地域群播算法并且考虑到公交车辆的轨迹信息和城市道路路网，提出了一种基于公交轨迹和定位信息的地域群播算法，该算法可以将消息从源节点通过每一跳选择最高传输能力的节点，将消息传输到目标区域，然后通过车辆集的建立和维护，使得其他车辆可以在一跳之内收到广播消息，所以该算法具有更高的分组投递率和较低的传输开销。

# 参考文献：

[1]Wang Xiaojing.Information distribution based on the game in VANET [D].Dalian:Dalian University of Technology,2013   
[2]Javadi M S,Habib S,Hannan M A.Survey on Inter-Vehicle Communication Applications: Current Trends and Challenges [J]. Information Technology Journal,2013,12(2).J.A.   
[3]S.Allal and S.Boudjit. Geocast routing protocols for VANETs: Survey and guidelines.in Proc.IEEE IMIS,Palermo,Italy,2012,pp.323-328.   
[4]Das S,Lobiyal DK.Intersection Area Based Geocasting Protocol (IBGP) for Vehicular Ad Hoc Networks [M],Advances in Computer Science and Information Technology. Computer Science and Information Technology. 2012.   
[5]M.Jerbi, S.Senouci,T.Rasheed,et al.Towards Efficient Geographic Routingin Urban VehicularNetworks．IEEE Trans.Vehicular Technology,vol.58,no.9,pp.5048-5059,Nov.2009   
[6]Ko YB,Vaidya NH.GeoTORA: a protocol for geocasting in mobile ad hoc networks [C],International Conference on Network Protocols.IEEE, 2000. Ad Hoc Networks [J]. Mobile Networks and Applications,2002,7(6): 471-480.   
[8] 万航，王学成，基于改进的公交车骨干网的改进区域路由算法[J]. 电子技术应用，2018,44（6)．：108-112,119.（Wan Hang，Wang Xuecheng.Improved zone routing protocol based on bus backbone networks [J].Application of Electronic Technique,2018,44(6): 108-112, 119.)   
[9]Meriem Houmer, Moulay Lahcen Hasnaoui.An Enhancement of Greedy Perimeter Stateless Routing Protocol in VANET[J]. Procedia Computer Science,2019,160.   
[10]彭雅丽，徐虹，尹红．周期性移动公交车载网络路由协议[J].计算 机应用.2015,35 (2):313-316,334.(Peng Yali,Xu Hong,Yi Hong. Routing protocol for bus vehicle network with cyclical movement. Journal of Computer Applications,2015,35 (2):313-316,334.)   
[11] Das S,LobiyalD K. Intersection Area Based Geocasting Protocol (IBGP) for VehicularAd Hoc Networks [M],Advances in Computer Science and Information Technology. Computer Science and Information Technology. 2012.   
[12]连蕊．基于节点移动预测的 AdHoc 网络地理路由算法研究 [D]. 2017.(Lian Rui. Research on geographic routing algorithm based on node mobility prediction in Ad Hoc networks [D]. 2017)   
[13] LiL,Liu Y,Li Z,etal.R2R:Data forwarding in large-scale bus-based delay tolerant sensor networks [C],International Conference on Wireless Sensor Network. IET,2010.   
[14]高鑫．面向车联网的地理辅助多播路由协议研究[D].2015.(Gao Xing. The Research about Geocast Routing Algorithm inVANET [D]. 2015)   
[15] Li P, Zhang T,Huang C,et al.RSU-Assisted Geocast in Vehicular Ad Hoc Networks [J]. IEEE Wireless Communications,2017,24(1): 53-59.   
[16] Zhang Y, Wang H M, Ding Z,et al. Non-Orthogonal Multiple Access Assisted Multi-Region Geocast [J]. IEEE Access,2018,6: 2340-2355.   
[17] Byungseok Kang and Hyunseung Choo.An energy-efficient routing scheme by using gps information for wireless sensor networks. International Journal of Sensor Networks,26 (2): 136-143,2018.   
[18] Ramin Yarinezhad. Reducing delay and prolonging the lifetime of wireless sensor network using eficient routing protocol based on mobile sink and virtual infrastructure.Ad Hoc Networks,84: 42-55,2019.   
[19] X.Cao and S. Madria.An Efficient Trajectory-Based Routing Using Virtual Coordinates forLow-Power WSNswith Mobile Sinks,2019 15th International Conference on Distributed Computing in Sensor Systems (DCOSS),Santorini Island,Greece,2019, pp.170-172.   
[20] S.Perkin,C.Hamon,R.Kristjansson,et al.Framework for trajectorybased probabilistic security assessment of power systems.in IET Generation,Transmisson & Distribution,vol.13,no.7,pp.1088-1094, 9 4 2019.   
[21]F.Liu,W. Zeng,C.Yuan,Q. Wang,et al. Trajectory-Based Hand Gesture Recognition Using Kinect via Deterministic Learning.2018 37th Chinese Control Conference (CCC),Wuhan,2018,pp. 9273-9278.   
[22] I. Chang, M. Hung,C. Chang, et al. NTR: An efficient trajectory-based routing protocol for the vehicular delay tolerant networks.2017 IEEE International Conference on Systems,Man,and Cybernetics (SMC）, Banff, AB,2017,pp.389-394.   
[23] M.Fiore,C.Caseti, C.Chiasserini and D.Borseti, "PersistentLocalized Broadcasting in VANETs,"in IEEE Journal on Selected Areas in Communications,vol.31,no.9,pp.480-490,September 2013.