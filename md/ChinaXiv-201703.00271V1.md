# 基于文献计量的卫星组网路由协议研究

李强强12，姚秀娟‘，章岑2.3

（1.中国科学院国家空间科学中心100190；2.中国科学院大学100049;

3.中国科学院文献情报中心100190)

[摘要]由于卫星网络拓扑的动态性，传统网络的路由协议不再适用于卫星网络。使用文献计量方法分析了国内外空间卫星网络路由的研究现状，总结归纳为基于虚拟节点的路由协议和基于虚拟拓扑的路由协议，并对SGRP路由协议提出了一种改进方法。

[关键词] 卫星网络；路由协议；卫星星座；文献计量

[中图分类法]TN915 文献标识码：A

# Research on Routing in Satellite Network Based on Bibliometrics

LI Qiang-qiang1,²， YAO Xiu-juan1， ZHANG Cen2.3 (1.National Space Science Center, the Chinese Academy of Sciences, Beijing 1OO190, China; 2.University of Chinese Academy of Sciences, Beijing 1Oo19o, China; 3.National Science Library, Chinese Academy of Sciences,Beijing 1OO190, China)

Abstract: Because of the dynamic topology in the satelite network, the traditional Internet routing protocols are no longer applicable to satellite networks. Analyzing the current research on space satellite network routing by bibliometric method and the routing protocols are summarized as two aspects,the one is routing protocols based on virtual node,another is routing protocols based on virtual node virtual topology, and an improved method is proposed for SGRP.

Key words: satellite network； routing protocols； satellite constellation； bibliometrics1．引言

#

2016 年6月30日，美国"Union of Concerned Scientists”公布的卫星数据库[1]显示，在轨绕地球运行的卫星一共有1419颗，其中美国占据将近总数的一半，而我国只有181颗，在空间信息网络整体的规模和实际应用效果上，我国与发达国家还有比较大的差距。因此我国亟需重视空间信息网络的建立，根据我国的"十三五"规划纲要草案，“天地一体化信息网络”被列为未来五年中国计划实施的百个重大工程及项目之一[2-3]，而卫星组网是实现天地一体化信息网络的关键所在。

本文旨在通过分析国内外卫星空间卫星网络路由研究的内容，进行空间组网路由协议研究，具有较强的理论意义和实用价值。虽然国内有不少学者此前进行过综述研究，如卢勇、赵友健4等著作的《卫星网络路由技术》是根据卫星网络路由技术的发展脉络，从分类的角度重点阐述了一些关键路由技术的核心机制、特点，最后针对应用需求，提出了卫星网络路由技术的发展趋势；再比如戴国梁、赵尚宏[5等著作的《卫星网络路由技术概述》是从卫星星座组网方式即单层、双层、多层卫星网络路由三方面综述了多种路由算法，并对其进行分析和比较。但是少有利用文献计量的方法，本文便是基于文献计量的方法来分析国内外卫星网络路由技术，这样能够更加明确的显示出相关研究内容，利于后文更好地分析。

# 2．数据来源和研究方法

国内以CNKI为数据源，以"卫星"并"路由"为检索词，“主题"为字段，“信息科技"领域内，共检索到711篇文献；国外以Web of Science 为数据源，“satellite"并"routing"为检索词，共检索到 2178篇文献。采用共词分析方法7，将关键词进行聚类，对一组词两两统计它们在同一篇文献中出现的次数，以此为基础将这些词进行聚类分析，反映出这些词之间的亲疏关系，进而分析这些词所代表的学科和主题的结构变化。

# 2.1国内卫星网络路由研究热点分析

# 2.1.1 关键词频次分析

为了既概括领域内发展情况，又能减少低频词汇的干扰，本文抽取国内711篇文献中关键词频次 $^ { \cdot \geq 8 }$ 的 30个高频个高频词汇进行研究。

表1国内文献关键词top30（频次 $\geq 8$ ））  

<html><body><table><tr><td>卫星网络</td><td>路由算法</td><td>路由</td><td>路由协议</td><td>卫星通信</td><td>星际链路</td></tr><tr><td>星间链路</td><td>服务质量</td><td>仿真</td><td>无线传感器网络</td><td>LEO卫星网络</td><td>切换</td></tr><tr><td>负载均衡</td><td>QoS</td><td>OPNET</td><td>卫星通信系统</td><td>路由策略</td><td>Ad</td></tr><tr><td>LEO</td><td>卫星网</td><td>拥塞控制</td><td>VSAT</td><td>路由选择</td><td>动态路由</td></tr><tr><td>路由技术</td><td>卫星星座</td><td>蚁群算法</td><td>网络仿真</td><td>多层卫星网络</td><td>卫星光网络</td></tr></table></body></html>

通过 Sati软件将关键词两两配对，形成 $3 0 ^ { * } 3 0$ 相似矩阵，利用社会网络分析软件Ucinet绘制关键词的关联图谱，节点大小代表关键词的中心度，节点越大说明中心度越高。可以看出，“卫星网络”、“路由协议”、“卫星通信”、“星际链路"几个节点明显，一定程度上可以视为研究热点。通过聚类，关键词之间相关性较强，形成了复杂的相互交错的研究网络。

表2国内高频关键词相似矩阵（部分）  

<html><body><table><tr><td></td><td>卫星网络</td><td>路由算法</td><td>路由</td><td>路由协议</td><td>卫星通信</td><td>星际链路</td><td>星间链路</td></tr><tr><td>卫星网络</td><td>1</td><td>0.0612</td><td>0.0208</td><td>0.0303</td><td>0</td><td>0.0365</td><td>0.0103</td></tr><tr><td>路由算法</td><td>0.0612</td><td>1</td><td>0</td><td>0.0044</td><td>0.0047</td><td>0.0164</td><td>0.0186</td></tr><tr><td>路由</td><td>0.0208</td><td>0</td><td>1</td><td>0</td><td>0.0132</td><td>0.0105</td><td>0.0019</td></tr><tr><td>路由协议</td><td>0.0303</td><td>0.0044</td><td>0</td><td>1</td><td>0</td><td>0.0115</td><td>0.0033</td></tr><tr><td>卫星通信</td><td>0</td><td>0.0047</td><td>0.0132</td><td>0</td><td>1</td><td>0.0068</td><td>0.0009</td></tr><tr><td>星际链路</td><td>0.0365</td><td>0.0164</td><td>0.0105</td><td>0.0115</td><td>0.0068</td><td>1</td><td>0</td></tr><tr><td>星间链路</td><td>0.0103</td><td>0.0186</td><td>0.0019</td><td>0.0033</td><td>0.0009</td><td>0</td><td>1</td></tr></table></body></html>

![](images/283faf336d8ae3f09503f45d39cc70632a154b748b5b5cb9d063cc548cbc53c1.jpg)  
图1.国内"卫星"路由"关键词聚类分析

# 2.1.2 关键词聚类分析

利用SPSS软件对相似矩阵进行聚类分析如图2，可以将研究分为两个方向。第一，关于卫星网络的研究，以卫星星座、无线传感器、卫星通信等为代表的关键词；第二，关于路由技术的研究，以动态路由、路由协议、网络仿真等为代表的关键词。

![](images/1777d8e834934da5a4bd9d84978218e5c94e786e851982698a29fc7f8b0d6031.jpg)  
图2.国内高频关键词多维尺度分析

# 2.2国外卫星网络路由研究热点分析

# 2.2.1关键词分析

同样选取国外关键词频次超过8次的词语，共49个。通过关键词频次，研究发现除了“satellite”、“routing"的检索词出现频次最高之外，“migration”、“satelite Network”、“QoS”等也相对研究较多。

表3国外文献关键词top51（频次 $\geq 8$ ））  

<html><body><table><tr><td>Migration</td><td>Routing</td><td>connectivity</td><td>GIS</td><td>simulation</td><td>tracking</td><td>networks</td></tr><tr><td>QoS</td><td>conservation</td><td>Optimization</td><td>telemetry</td><td>navigation</td><td>bird migration</td><td>network</td></tr><tr><td>Satellite</td><td>satellite</td><td>telemetry</td><td>Remote</td><td>Satellites</td><td>climate</td><td>Satellite</td></tr><tr><td>Network</td><td>satellite</td><td>communication</td><td>sensing</td><td>tracking</td><td>change</td><td>networks</td></tr><tr><td>Osprey</td><td>movements</td><td>Low Earth Orbit</td><td>Multicast</td><td> Satellite</td><td>sea ice</td><td>Arctic</td></tr><tr><td>Orientation</td><td>Alaska</td><td>communications</td><td>Hydrology</td><td>stopover</td><td>LEO satellite</td><td>GPS</td></tr><tr><td>Satellite-tra</td><td>satellite</td><td> satellite</td><td>Vehicle</td><td>adaptive</td><td>multicast</td><td>Migration</td></tr><tr><td>cking</td><td>navigation</td><td>communications</td><td>Routing</td><td>routing</td><td>routing</td><td>routes</td></tr><tr><td>Satellites</td><td>load balancing</td><td>Communication</td><td>Route</td><td>GNSS</td><td>Multimedia</td><td>LEO</td></tr></table></body></html>

Alaska QoS birdmigration osprey stopover LEO LEOsatellitenetworks movements X Orientation Route networks Satellitenetwork migrationroutes Satellite-tracking multicastrouting connectivity LowEarthOrbit（LEO) satellitetelemetry migration satellite adaptiverouting Satellitenetworks Satellitetracking telemetry V M Multimedia loadbalancing climatechange conservation、 Routing itracking dispersal Arctic network 办 inter-satellite links Remotesensing Multicast navigation seaice tcommunications GPS Simulation eiaeisu GIS HydrologyOptimization Communication GNSS satellites satellitenavigation VehicleRouting

# 2.2.2关键词聚类分析

歐幾里德距離模型   
2 satellitetelemetry 。 Satellitetracking QoS stopoveghulticastrouting 。 。 satellite se 1 dispersal Orientation   
7 dloadbalancinStelirakin 。 。 Ointersatellitelinks GIS GPS OptimizationO o commumicationsO Snetworks 。 Arctic OCommunication Satellitenetwork Omovements satellitenavigation 。 osprey   
0 connectivity seaiceb network   
8 climatechangeSatellitenetwotks Hydrology Multicast LEOsatellitenetworks -1 migration AlaskaO g vei trackingoO telemetry migrationroutes QOsatelitecommunication navigationRemotesensing -2 -2 F1 0 11 12

根据SPSS聚类分析，可以将国外相关研究的关键词分为四大类如图4所示。一类是关于卫星网络中路由和QoS 技术的研究，以 Route、adaptiverouting、QoS等关键词为代表；第二类是关于卫星网络星座和路由技术的研究，以 satellite networks、routing等关键词为代表；第三类是关于移动卫星通信跟踪和仿真技术的研究，以migration、tracking、migration等关键词为代表；第四类则是以GIS、GPS 等技术为研究热点。

# 2.3研究内容分析

基于以上分析，当前研究热点主要分为两大类，一类是以卫星网络为基础的路由协议的研究，是关于星间链路的路由协议的研究；另一类是以移动卫星为基础的卫星通信的研究，是关于星地链路通信的研究。由于当前卫星通信星地链路的发展比较成熟，而空间卫星网络研究处于刚起步阶段[8-9]，所以本文着重分析了以卫星网络为基础的路由协议的研究。

# 3 卫星网络路由技术

路由技术是卫星组网技术的难点和重点所在，为了寻找从源卫星到目的卫星的符合一定要求的路径，必须首先解决卫星网络的拓扑时变问题。以寻径为目的解决卫星网络中拓扑时变问题被称为网络路由策略，卫星网络路由策略是卫星网络路由算法的基础。所以卫星组网路由算法分为基于虚拟节点策略的路由算法和基于虚拟拓扑策略的路由算法。

# 3.1基于虚拟节点的路由策略

Hashimoto ${ \mathrm { Y } } ^ { [ 1 0 ] }$ 提出了一种基于覆盖域划分的路由框架，被认为是虚拟节点路由的雏形。该框架采用IP分层编址和移动IP思想，根据卫星的覆盖区域将地球的表面划分为若干个边长为 $1 6 0 \mathrm { k m }$ 的方形区域，称之为 supercell，每个 supercell内再划分9个子cell，将各区域赋予固定的逻辑地址，并计算该区域到其他各区域的路由表。在系统运行过程中，根据就近原则将逻辑地址分配于网络中的各个卫星节点。卫星在运行过程获得了逻辑地址也就获得了路由表信息。该算法需要在轨卫星、地面网关、地面终端联合操作，共同完成路由过程。这种机制的优点是利用了网络的拓扑结构的对称性和周期性，避免动态的计算路由，具有较高的适应性。缺点就是在全球区域建造地面网关站是极为困难的。

Henderson[11]提出了 DGRA(Distributed Geographic Routing Algorithm)，算法首先提到了分布式路由的概念。与文献不同的是，DGRA分两步转发卫星分组，在卫星分组距出口卫星的距离大于一个阈值时，卫星节点依据全局路由信息转发分组，当卫星分组接近出口卫星时，卫星节点依据本地路由信息转发分组。

虚拟节点路由虽然实现简单，协议开销小，但是只对拓扑结构规则的卫星星座有效，可扩展性较差，算法鲁棒性较差。几乎所有基于虚拟节点的路由方法都是一极轨道LEO 星座为模型，因为极轨LEO 星座模型拓扑规则，计算简单。虚拟节点路由方法如需扩展到倾斜轨道卫星星座中需要进行较大的改进，从而增加算法的计算复杂性和协议开销。多层卫星星座由于存在卫星的重复覆盖，地面逻辑区域无法与唯一的星座卫星绑定，故不使用虚拟节点路由方法。

# 3.2基于虚拟拓扑的路由策略

基于虚拟拓扑的路由思想是卫星路由算法中应用相对较为广泛，虚拟拓扑的概念最初由Werner[2]等人提出，随后作者又对这种路由算法进行了大量深入的探讨和延伸。该类算法的主要思想是利用卫星轨道的周期特性以及星座结构的可预测特性,在卫星运转的周期T内，将时间T离散化为 $\mathfrak { n }$ 个时间片段 $[ \mathbf { t } _ { 0 } , \mathbf { t } _ { 1 } ] [ \mathbf { t } _ { 1 } , \mathbf { t } _ { 2 } ] . . . [ \mathbf { t } _ { \mathrm { n - 1 } } , \mathbf { t } _ { \mathrm { n } } ]$ 。而在某个时间片 $[ \mathrm { t } _ { \mathrm { i - 1 } } , \mathrm { t } _ { \mathrm { i } } ]$ 内，卫星的拓扑结构可虚拟化为一个连接图 $\mathrm { G _ { i } }$ 。当 $\mathbf { n }$ 足够大时，也就是时间片 $[ \mathfrak { t } _ { \mathrm { i - 1 } } , \mathfrak { t } _ { \mathrm { i } } ]$ ，足够小，可将此时的卫星拓扑连接图 $\mathbf { G } _ { \mathrm { i } }$ 视为静态的。在获取静态在获取静态拓扑连接图 $\mathbf { G } _ { \mathrm { i } }$ 后，利用经典的DijkstraSPF（shortestPathFirst）算法，计算图 $\mathbf { G } _ { \mathrm { i } }$ 中每一对节点的连接路径。值得注意的是，上述操作是在卫星系统设计之初即完成的，然后将每个时间片内的路由计算结果保存于卫星设备当中。卫星在轨运行时，只需要知道当前处于哪个时间片内，读取该时间片所对应的路由表，即可得到路由信息。

基于Wermer的研究，Chen Chao 等提出了LEO/MEO 双层卫星网络的分组路由策略[13],首次将虚拟拓扑策略扩展到了双层卫星网络。文中将所有LEO/MEO 组成员关系相同的时刻定义为一个快照，在每一个快照内由于LEO 卫星和 MEO卫星的隶属关系相同，可视为网络拓扑不变。由此，LEO/MEO 双层卫星网络连续变化的拓扑结构就被固化为一系列离散的快照。在每个拓扑快照内，使用 SPF 算法为没对OD节点寻找最短路径，由于拓扑快照可以预先计算，每对OD节点之间的最短路径由地面网关预先计算并上传至卫星节点。其所提出的虚拟拓扑分组策略虽然解决了多层卫星网络的拓扑固化问题，却存在着一个系统周期内快照过多的缺点，使得快找切换频繁，协议开销较大。类似的还有多层卫星路由算法（Multi-Layered Satellite Routing，MLSR)。MLSR[4]适用于LEO/MEO/GEO 卫星组成的三层卫星网络，该协议首次将虚拟拓扑策略的路由应用到了三层卫星网络，同样依据高层卫星的足印对低层卫星进行分组，进行分层的网络拓扑收集，并在组成员关系变化的时候由高层卫星为低层卫星计算路由表。MLSR由于依赖定期的路由表计算来处理链路拥塞问题，对拥塞缺乏快速反应机制。

继 MLSR 之后，Chen 等人又提出了卫星分组路由协议 SGRP[15](satellte Grouping andRouting Protocol)。SGRP 继承了MLSR的分组思想，应用在LEO/MEO 双层卫星星座上，充分利用了LEO层和MEO 层的协作关系，由MEO 层卫星为LEO层的管理者。SGRP 的主要思想是沿最短时延路径传输数据包，并将先前由LEO层卫星承担的路由表计算任务转交给MEO层卫星。同MLSR一样，SGRP也将LEO卫星划分为若干个组，在同一颗MEO卫星足印区（footprint area）的LEO卫星被划为一组。LEO 卫星某一颗MEO卫星的足印区时，分组关系发生变化。在SGRP中将LEO分组关系的变化视为网络拓扑的变化，每次分组关系变化会产生一个新的快照，每个快照内卫星网络拓扑可视为不变。每颗MEO卫星都是其足印区内LEO卫星分组的组长，组长负责收集和交换LEO层卫星的链路时延信息并为LEO 卫星计算路由表。LEO卫星从MEO卫星接收路由表，并按照此路由表转发数据包。SGRP 最大的优点在于将路由计算任务交给了功能更为强大的MEO卫星，平衡了LEO 和MEO 卫星的资源消耗，延长了系统的使用寿命。SGRP将信号留了和数据流量物理分离，这样链路拥塞就不能影响延时报告和路由计算的相应时间。

# 3.3SGRP的改进

基于上文，SGRP虽然解决了MLSR对于拥塞处理低效的问题，完善了MLSR提出的LEO层卫星分组路由机制，减轻了LEO层卫星路由计算的负担，但是存在着以下问题有待解决。

(1）否定了地面网关在路由计算中的作用,将所有路由计算和管理任务交给MEO卫星，增加了MEO卫星的负担，降低了整个系统的寿命、鲁棒性和抗毁性。  
(2）将LEO 分组的变化与LEO 逻辑位置变化绑定，增加了一个系统周期内快照个数，导致协议开销过大，系统负担过重。  
(3）由于LEO卫星频繁离开/进入MEO卫星的足印区，使得一个系统周期内的快照数量过多，不利于路由算法的应用。

基于以上分析，本文提出了一种新的卫星分组路由协议 NSGRP（New Satellite Groupingand Routing Protocol)。该协议改进虚拟拓扑路由策略，使得一个系统周期内快照数量大大减少，提出了快照合并方法，消除了过短的快照；综合虚拟节点路由策略和虚拟拓扑路由策略，应用到LEO/MEO/GEO三层卫星网络中。

为了减少一个系统周期内的快照数量，有两个常见的思路：重新划分拓扑快照和在已有的快照划分基础上合并一些快照。在LEO/MEO 虚拟拓扑分组策略框架下，以LEO 分组变化为快照划分依据，重新划分拓扑快照难以实现。故考虑第二种思路，以快照合并的方法减少快照的数量。

假设基于快照划分方法分化出的切换时刻为 $[ \mathrm { t } _ { 1 } , . . . \mathrm { t } _ { \mathrm { i } } , . . . , \mathrm { t } _ { \mathrm { n } } ] , \mathrm { t } _ { \mathrm { i } }$ 时刻发生分组切换的LEO 卫星 $\mathrm { L } _ { \mathrm { i } }$ ，且 $\mathrm { L } _ { \mathrm { i } }$ 被 $\mathbf { M } _ { \mathrm { i } }$ ， $\mathbf { M } _ { \mathrm { i } + 1 }$ 同时覆盖。首先从第一个快照划分时刻 $\mathbf { t } _ { 1 }$ 开始考虑，如果这个划分时刻在卫星 $\mathbf { L } _ { 2 }$ 的自由时段内，则 $\mathbf { L } _ { 2 }$ 可以在 $\mathbf { t } _ { 1 }$ 时刻切换，如此便合并一个快照。依次类推，可以合并所有可以合并的快照最终得到一个新的切换时间表。快照合并的原理如图5所示。

![](images/f1cfe027346792ead28984866b4ef82ac33a3083c3661f871e14b152a8d3fe79.jpg)

# 4结语

空间卫星组网是实现“天地一体化信息网络”的关键一环，而实现空间卫星组网的关键技术之一为组网的路由策略。本文分析了基于虚拟节点的路由策略和基于虚拟拓扑的路由策略,分析了两种路由策略的主要特点和存在的问题，并提出了对SGRP的改进，减少了快照，提高了SGRP路由协议的性能。

# 5参考文献

http://m.spacemagazines.org/nd.jsp?mid=15&id $\scriptstyle - 9 0 2$ &searchword

[10]Hashimoto Y,Sarikaya B.Design of IP-based routing in a LEO satelite network[C]/Proceedings of Third International Workshop on Satellite-Based Information Services.2O12:81-88.   
[11]Henderson T R，Katz R H.On distributed，geographic-based packet routing for LEO satelite networks[C]//Global Telecommunications Conference.2011:1119-1123.   
[12] Werner M.A dynamic routing concept for ATM-based satelite personal communication networks[J].Selected Areas in Communications,2013,15(8):1636-1648.   
[13] Chen C.Ekici E,Akyildiz I F.Satelite grouping and routing protocol for LEO/MEO satelite IP networks[Cl//Proceedings of the 5th ACM international workshopon Wireless mobile multimedia.2013:109-116. [14] Nishiyama H,Kudoh D,Kato N,etal. Load balancing and QoS provisioning based on congestion prediction for GEO/LEO hybrid satellite networks[J]. Proceedings of the IEEE,2011,99(11): 1998-2007.   
[15] Chen C.Advanced Routing Protocols for Satellte and Space Networks[D]. Georgia Institute of Technology, 2013.

李强强（1991年-)，男，江苏连云港人，中国科学院国家空间科学中心在读硕士研究生，研究方向：卫星组网路由协议；姚秀娟（1977年-)，女，中国科学院国家空间科学中心硕士生导师；章岑（1991年-)，女，中国科学院文献情报中心在读硕士研究生。