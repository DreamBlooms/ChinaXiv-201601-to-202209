# 软件定义车联网中缓存辅助的NOMA功率分配方案研究

顾金媛12，章国安²，张鸿来1

(1．南京医科大学康达学院，江苏 连云港 222000;2．南通大学 信息科学技术学院，江苏 南通 226019)

摘要：由于对丰富多媒体服务的需求日益增长，车联网需要提供海量的设备连接以满足高频谱效率和低延迟的需求。软件定义网络(Software DefinedNetwork,SDN)、缓存和非正交多址接入(Non-Orthogonal Multiple Access,NOMA)被认为是有效解决这些关键挑战的潜在技术。因此，针对软件定义车联网提出了一种缓存辅助的 NOMA 功率分配方案。首先，针对车联网中车辆总是处于高速运动状态的特点，提出了一种新的簇头选择算法，到达的道路交通将借助 SDN进行预测，实现自适应车辆分簇。其次，引入了缓存辅助的NOMA方案，每个车辆在文件缓存阶段使用NOMA 原理缓存和请求文件。再次，针对双Nakagami-m衰落条件下的两个簇头车辆通信场景，提出了一种最优功率分配策略，将优化问题公式化为找到每辆车的最佳功率曲线，从而最大化的在每辆车上成功解码目标文件的概率。最后，数值仿真和理论分析表明，所提出的缓存辅助NOMA功率分配方案，性能明显优于传统的NOMA和缓存辅助的 OMA(Orthogonal Multiple Access)。

关键词：车联网；非正交多址接入；缓存；软件定义网络 中图分类号：TN929. doi:10.19734/j.issn.1001-3695.2022.01.0008

Research on cache aided NOMA power allocation scheme in software defined vehicular network

Gu Jinyuan1,2, Zhang Guo'an², Zhang Honglai1† (1.Kangda Coege,NanjingedicalUniversityJangsuLianyungang2oo,China;2.hoolofInformationcience& Technology,Nantong University,Jiangsu Nantong 226019,China)

Abstract:Duetothe increasingdemandforrichmultimediaservices,Iternetofvehicles needs toprovide massiveequipment conections to meet theneeds of high spectrum eficiencyand low delay.Software Defined Network (SDN),caching and Non-Orthogonal Multiple Access (NOMA)technologies areconsidered as potential solutions to efectively solve these key challnges.Therefore,this paper proposed a cache aided NOMA power allcation scheme for software defined vehicular network.Firstly,according tothecharacteristicsofvehiclesalways movingathigh speed inInternetofvehicles,thescheme proposedanew cluster head selection algorithm.The arrving road traffic willbe predicted with the helpof SDN torealize adaptive vehicle clustering.Secondly,the scheme introduced acache aided NOMA strategy.Each vehicleuses NOMA principletocacheandrequest filesinthefilecache stage.Thirdly,forthe twoclusterheadvehiclecommunicationsenarios under the condition of double Nakagami-m fading,the scheme proposed an optimal power allocation strategy.The optimization problemis formulated as findingtheoptimal power curve ofeach vehicle,soas to maximize the probabilityof successfullydecoding the targetfleoneach vehicle.Finally,numerical simulationand theoretical analysis showthatthe performance ofthe proposed cache aided NOMA power allocation scheme is significantly better than theconventional NOMA and cache aided Orthogonal Multiple Access (OMA) .

Key words:Internet of Vehicles;NOMA;cache; SDN

# 0 引言

随着信息和计算机技术的爆炸式发展，5G无线通信引入了新的技术和应用，如小蜂窝网络、可靠的车联网和毫米波通信，这包括了前所未有的超密集和异构网络环境[1,2]。车联网在5G无线系统中起着举足轻重的作用，保证了车辆的可靠性和安全性。车联网的潜在应用是多样和普遍的，例如，可以通过道路和交通信息的快速传播以及在关键点(如高速公路入口和其他十字路口)协调车辆来改善交通。此外，可以实现许多令人感兴趣的并具有挑战性的新应用，例如高速互联网接入、合作下载、相邻车辆乘客之间的网络游戏以及不同车辆中同事之间的虚拟视频会议。

作为一种专用的短距离通信技术[3]，用于车辆环境的无线接入。DSRC由物理层标准IEEE802.11p 和网络层标准IEEE1609构成。尽管DSRC技术具有可靠性高、传输实时性强等特点，但由于DSRC的物理层技术主要基于WiFi技术，覆盖范围小，实际应用中需要针对路边设施进行大规模改造和投入。针对这一问题，3GPP最近发布了基于LTE作为底层技术的V2X规范。然而，在最近提出的车联网生态系统中，车辆被设想为从云中快速共享和访问大量数据，并被期望能够以高性能和边际开销处理它们。此外，由于高移动性场景，网络拓扑可能快速改变，并且不同基站和车辆之间的切换变得更加频繁。这对在基于广域网和长期演进的车联网中有效实现低延迟的可靠通信提出了一些挑战。因此，5G

收稿日期：2022-01-17；修回日期：202-03-01基金项目：国家自然科学基金资助项目(61971245)；江苏省第十六批“六大人才高峰”高层次人才选拔培养资助项目(XYDXX-245);连云港市第六期"521高层次人才培养工程"培养对象资助项目;江苏高校哲学社会科学研究资助项目(2021SJA2492);教育部产学合作协同育人项目(202102311004)；南京医科大学康达学院科研人才培养计划资助项目

作者简介：顾金媛(1986-)，女，江苏连云港人，副教授，博士研究生，主要研究方向为车联网通信技术；章国安(1965-)，男，江苏如皋人，教授，博导，博士，主要研究方向为无线通信网络、车联网等；张鸿来(1972-)，男(通信作者)，江苏连云港人，副研究员，硕士，主要研究方向为计算机技术(kdntdbtg@163.com).

移动通信网络将融合大规模天线阵列(MassiveMIMO)、超密集组网、终端直通、SDN等先进技术[4]，以更加灵活的体系结构解决多样化应用场景中差异化性能指标带来的挑战。

随着车载应用和物联网的快速发展，开发处理车联网大数据的高效架构已成为未来智慧城市关注的重要问题。然而，当前车载网架构复杂且欠缺灵活，面临高移动性、间歇性连接、应用程序的异构性等挑战。在此背景下，SDN可编程和灵活的网络架构，在有线网络管理和异构无线通信中受到学术界和工业界的广泛关注。在车联网中应用SDN 可以提高灵活性、可靠性和可扩展性，增强车联网提供应用和服务的能力，提高用户服务质量。在文献[5\~8]中，研究人员针对车载网动态变化的拓扑结构、通信链路间歇性连接和应用程序的异构性等特点，设计了深度可编程的集中式软件定义车载网架构。然而，由于车载网络的车辆和基础设施节点在地理上分布稀疏和广泛，尤其当网络规模增加时，集中式的单个SDN 控制器管理动态变化的控制层请求将变得十分困难。在文献[9，10]中，研究人员设计了分布式软件定义车载网架构。其中，文献[9]将车载自组织网络(Vehicularadhoc Network,VANET)进行分区管理，并在每个区域内部署支持SDN的控制器，以有效管理高速公路场景中的大规模车辆流量，并利用软件定义车载网的控制中心平面将网络智能分发到各个小区，以提高网络的可伸缩性，降低网络控制开销。在文献[10]中，研究人员利用聚类算法设计了一种新的路由协议(称为HSDV)，选择簇头和簇首分别作为本地SDN控制器对中央SDN控制器进行分层访问，当中央SDN控制器无法访问或者无响应时，本地SDN控制器可以暂时控制本地网络，避免网络瘫痪。

与上述方案相关的一个主要挑战是，这些技术需要大量的回程开销。最近已经表明，缓存技术已经可以减少回程流量，通过将流行的文件先验地存储在车辆上来实现。缓存的基本思想是在非高峰时间将热门内容存储在不同的地理位置。这种本地存储布置使得流行文件的复制传输成为可能，从而增加了车辆网络的频谱效率，并随后减少了等待时间。此外，在最近的文献中已经广泛研究了缓存对于蜂窝系统的优势和应用。文献[11]中强调，与增加回程开销相比，在用户端安装内存单元具有显著的成本效益。在此基础上，对几种缓存技术的集成进行了大量研究，例如异构网络[12\~14]、端到端通信[15,16],以及车-边-云协同架构[7等技术。在这种情况下，相关文献已经提出了用几个度量来表征缓存算法的性能，例如命中率[18]、中断/覆盖概率[19]、区域频谱效率[20]和平均吞吐量[15]。类似地，在文献[21]中讨论了车辆自组织网络中的协作缓存，认为车辆自组织网络中的协作缓存依赖于三个主要组件，即发现、管理和一致性。发现组件中的主要任务是搜索网络中车辆请求的文件的存在，使用例如广播技术来实现，如分割缓存[22]和共享缓存[23]。下一个任务是通过管理组件来执行的，该组件决定是否缓存所请求的文件以及在哪里缓存它，以实现更平滑的复制传输。最后，一致性组件驱动的任务是决定缓存的内容应该在网络中保留多长时间。

然而，将大量的车载通信链路引入到超密集和异构的5G车联网中是一个挑战。随着现有的OMA网络中频谱资源的日益稀缺，近年来人们对车联网中的NOMA进行了研究，以提高频谱利用率。与OMA不同，NOMA允许多个用户同时占用一个频率信道，这在频谱效率和蜂窝覆盖方面都显示出优势[24,25]。因此，可以预见，NOMA 使能的V2X 通信将是未来的一个趋势，因为它具有提高频谱效率和改善用户接入的潜在能力[26]。值得注意的是，可以通过根据不同用户的信道条件将不同的功率水平分配给不同的用户来实现NOMA。这种功率分配方案能够有效实现SIC，这通常被认为是消除多用户检测系统中的多用户干扰。在这种情况下，在具有最佳信道条件的用户处执行SIC，并且以信道的降序执行SIC。此外，由于NOMA技术与其他技术的融合，如多输入多输出通信[27,28]、毫米波通信和空间调制[27]，车辆网络的性能得到了显著提高。NOMA已经被证实是5G无线网络满足低延迟、高可靠性、大规模连接和高吞吐量等异构需求的一项重要支持技术[29.30]。然而，NOMA在车辆网络中的使用直到最近才受到关注，在车辆网络中，它被证明明显优于传统的基于正交多址的系统[31]。基于此，基于NOMA的V2X系统的频谱效率和资源分配已经在文献[32]中进行了研究。文献[33]中讨论了用于基于NOMA的V2X通信系统中基于图论的编码器和使用置信传播算法的可靠解码器，以及相应的中断容量分析。在文献[34]中，在分析用于加权和速率最大化的小区关联和功率控制的联合优化的背景下，研究了构成车与基础设施(VehicletoInfrastructure，V2I)的特殊情况的支持车辆到小型基地台的性能。在文献[27]中，NOMA效应和空间调制技术被提出用于车与车(VehicletoVehicle，V2V)多输入多输出通信，并给出了可实现的吞吐量和相应的最优功率分配策略。

以上研究表明，车辆可以利用自己的高速缓存内容来减少来自其他车辆信号的干扰。也就是说，对于特定的车辆，如果一个文件出现在它自己的高速缓存中并被另一个车辆请求，那么它可以在请求阶段利用它来减少接收的叠加NOMA信号中的干扰。因此，高速缓存辅助的NOMA系统的性能通过利用其高速缓存内容来提高。此外，缓存带来的干扰降低也有助于降低SIC的计算复杂度。在文献[35，36]中，尽管蜂窝网络的缓存辅助NOMA受到关注，但是可用的框架并不直接适用于车辆网络。由于车辆的高移动性和天线的低仰角，本文考虑级联(双)Nakagami-m衰落信道模型，该模型提供了车辆间信道的现实描述[37]。与流行的瑞利/Nakagami-m衰落假设相比，双Nakagami-m衰落模型有助于从整体上研究由于衰落引起的现像。

综上，本文针对上述问题提出了一种缓存辅助的NOMA功率分配方案，主要贡献总结如下：

a)提出的基于SDN自适应分簇方案中，到达的道路交通将借助SDN进行预测，实现自适应车辆分簇。针对车联网中车辆总是处于动态运动状态的特点，提出了一种新的簇头选择算法。

b)为了解决支持5G的车载网络中的频谱效率要求，提出了高速缓存辅助的NOMA方案。根据每辆车成功解码文件的概率，分析描述了所提出的缓存辅助的NOMA系统在真实双Nakagami-m衰落条件下的性能。

c)本文考虑了文件缓存的情况，在缓存阶段，每辆车都可以缓存请求的文件。将优化问题公式化为找到每辆车的最佳功率曲线，从而最大化在每辆车上成功解码目标文件的概率。在双Nakagami-m衰落条件下，本文进一步证明了这个优化问题的代价函数是凹的。

d)与传统的NOMA和缓存辅助的OMA相比，所提出的缓存辅助的NOMA性能大大提升，还给出了双Nakagami-m分布衰落效应对性能的影响。

# 1 系统模型

# 1.1 网络架构

车辆分簇已被用于降低V2X通信的复杂性，从而最终提高道路交通效率。图1是本文提出的一种基于分簇的软件定义异构车载网架构，一方面，利用聚类方法建立了车辆网络的层次拓扑结构；另一方面，簇头车辆作为一个本地控制器，支持簇成员和簇之间的数据传播，降低了车载网络端到端通信的复杂性，从而降低了车辆网络拓扑结构的通信复杂度。

通过整合大规模部署的蜂窝网络和丰富的云计算资源和功能来扩展传统的车载网；通过聚类技术实现网络分区来减少干扰和开销，同时增强网络的可伸缩性和流动性；通过使用新兴的 SDN 概念与分层分布式部署的控制器管理异构网络，提高网络的灵活性和可扩展性；采用聚类算法构建网络拓扑，在簇头车辆上部署本地 SDN 控制器，在蜂窝基站上部署区域 SDN控制器，在C-RAN部署全局 SDN控制器，实现网络控制功能的分层分布式部署，各级SDN 控制器协作管理整个系统，如图2所示。

![](images/91a957b9dd445562a7481ff0dd2ee44f4712c38e4ebe55da929af81152af9676.jpg)  
图1基于分簇的软件定义异构车载网络

![](images/17db4785080ca03ffc9aa796b1367fe1e56a4d4d6b7245a634a86731d3877622.jpg)  
Fig.1Software defined heterogeneous internet of vehicles based on clustering   
图2分层分布式控制模式

如图3所示，不失一般性，假设一个BS分别服务于由CHV1和CHV2表示的两个簇头车辆(ClusterHeadVehicles,CHV)。两个簇头车辆模式不仅代表了用户之间的权限域差异，而且有助于协同NOMA分析和部署。因此，两辆CHV的功率分配足以说明车辆之间功率分配的关键方面，同时避免不必要的复杂化。虽然研究限制在两个CHV之间，但是所提出的方案可以扩展到多个CHV。

![](images/8746a75d05dad09455220506c6edba2f9b4d558ce248668261a2aa8f0367932f.jpg)  
Fig.2Hierarchical distributed control mode   
图3一个基站服务两个簇头车辆  
Fig.3One base station serves two cluster head vehicles

# 1.2缓存辅助的NOMA模型

假设CHV1和CHV2配备了大小为 $k$ 的有限容量缓存。$F \triangleq \{ F _ { 1 } , F _ { 2 } , . . . , F _ { T } \}$ 表示基站可用的有限文件集。然后用流行的

Zipf分布[1]建模 $F$ 上的受欢迎程度，并带有偏斜度控制参数$\lambda > 0$ 。特别是，文件 $F _ { t } \in F$ 的受欢迎程度由概率给出:

$$
D _ { t } = \frac { 1 } { t ^ { \lambda } { \displaystyle \sum _ { i = 1 } ^ { T } } \frac { 1 } { i ^ { \lambda } } } , t = 1 , 2 , . . . T
$$

其中 $D _ { 1 } { > } D _ { 2 } { > } . . . { > } D _ { \mathrm { T } } { > } 0 , \quad \sum _ { t = 1 } ^ { T } D _ { t } = 1$ 。在缓存阶段CHV1和CHV2在非高峰时间从 $F$ 中获取并存储一组文件，表示为 $F _ { C H V 1 } \subset F$ ，$F _ { C H V 2 } \subset F$ 。考虑到上面的流行度配置文件，最佳缓存策略是从最流行的文件缓存到最不流行的文件。在请求阶段，不失一般性，假设CHV1和CHV2分别请求文件 $F _ { 1 } \in F$ 和 $F _ { 2 } \in F$ 。此外，假设基站完全了解 $F _ { C H V I }$ 和 $F _ { C H V 2 }$ ，CHV1 和 CHV2了解基站的功率分配方案。对于前一个假设，信息可以在请求阶段在基站获得，即当CHV1和CHV2共享它们的缓存状态时。对于后者，基站可以在传送文件之前将信息广播给CHV1和CHV2。

假设 $x _ { I }$ 和 $x _ { 2 }$ 是对应于 $F _ { I }$ 和 $F _ { 2 }$ 的信号。该基站使用NOMA向CHV1和CHV2发送叠加信号，

$$
S = \sqrt { a _ { 1 } P _ { B } } x _ { 1 } + \sqrt { a _ { 2 } P _ { B } } x _ { 2 }
$$

其中， $P _ { B }$ 是基站的平均发射功率， $a _ { i }$ ， ${ \mathrm { i } } \in \{ 1 , 2 \}$ ，是功率分配系数，满足 $\stackrel { } { a } _ { I } + a _ { 2 } = 1$ 并且 $a _ { l } { > } 0$ ， $a _ { 2 } { > } 0$ 。 $x _ { i }$ 表示在BS处传输的NOMA信息满足 $E [ | x _ { i } | ^ { 2 } ] = 1$ 。同时使用 SIC 技术解码各自的信号。设 $s _ { 1 }$ 和 $^ { s _ { 2 } }$ 分别是在CHV1和CHV2处的接收信号，给出如下：

$$
s _ { 1 } = h _ { B 1 } S + n _ { 1 }
$$

和

$$
s _ { 2 } = h _ { B 2 } S + n _ { 2 }
$$

假设 $h _ { B I }$ 和 $h _ { B 2 }$ 分别表示BS和CHV1、BS和CHV2之间的复信道系数。在车联网中，信道增益 $\left| h _ { B 1 } \right|$ 和 $\left| h _ { B 2 } \right|$ 由两个独立的级联Nakagami $\cdot \mathbf { m }$ 分布的乘积精确建模，例如，$\big | h _ { B 1 } \big | \sim \mathrm { N } ^ { 2 } ( ( m _ { 1 } ^ { ( 1 ) } , \Omega _ { 1 } ^ { ( 1 ) } ) , ( m _ { 2 } ^ { ( 1 ) } , \Omega _ { 2 } ^ { ( 1 ) } ) , ~ \big | h _ { B 2 } \big | \sim \mathrm { N } ^ { 2 } ( ( m _ { 1 } ^ { ( 2 ) } , \Omega _ { 1 } ^ { ( 2 ) } ) , ( m _ { 2 } ^ { ( 2 ) } , \Omega _ { 2 } ^ { ( 2 ) } )$ ，[37]

双Nakagami- $\cdot \mathbf { m }$ 分布是一个级联衰落模型，它是双瑞利分布的推广，是一种特殊情况[38]。 $n _ { 1 }$ 和 $n _ { 2 }$ 分别为在CHV1和CHV2处独立的圆对称复高斯分布，均值为0,方差为 $\sigma _ { B 1 } ^ { 2 }$ 和 $\sigma _ { B 2 } ^ { 2 }$ 。

值得注意的是，在车联网中考虑的基于缓存的NOMA中每个用户可以通过使用在缓存期间获得的内容，通过减少或消除由于另一用户的信号引起的干扰来解码其自己的信号。这增加了成功解码每个用户的信号的概率。假设当接收的信噪比满足 $\mathrm { S I N R } > \gamma _ { 1 } > 0$ ， $\mathrm { S I N R } > \gamma _ { 2 } > 0$ 时，文件 $F _ { I }$ 和 $F _ { 2 }$ 可以被CHV1或CHV2成功解码。那么CHV1和CHV2在缓存阶段缓存文件成功的情况可以描述如下：CHV1缓存了 $F _ { 2 }$ CHV2 也缓存了 $F _ { I }$ 。从数学上讲，上述场景可以表示为：$F _ { 2 } \in F _ { C H V 1 }$ 和 $F _ { 1 } \in F _ { C H V 2 }$ 。为此，本文打算找到最优功率分配策略，使得它们在CHV1和CHV2处各自成功解码文件 $F _ { I }$ 和 $F _ { 2 }$ 的概率最大化。

# 2 基于SDN的车联网自适应分簇

由于车辆的高移动性和有限的运动范围，车辆分簇被认为是一种很有前途的解决方案，可以减少蜂窝网络开销，在较低的相对速度下提供更好的通信质量。在本节中，首先利用车辆间距离来聚集道路上的车辆。然后，结合车辆相对速度、CHV与BS之间的信道质量来选择CHV。针对车联网中车辆总是处于动态运动状态的特点，提出了一种新的簇头选择算法。

在车联网中应用SDN，控制器对全局视图和道路交通拓扑的及时更新为应对上述挑战提供了一个可行的解决方案。由于车辆通常移动速度很快，且BS的覆盖范围有限，本文认为BS只提供相关车辆的最新信息，簇成员车辆将通过选定的车辆(即簇头(CHV)与BS通信。具体方案流程如下：

1)基站初始化分组

由于移动速度和行驶车辆方向的一致性，SDN控制器将能够使用不同的定位和数据分析技术来监测和预测到达车辆的位置，然后提前通知相关BS，以保证自适应和高效的分簇。由于SDN控制器能提供道路交通拓扑，BS知道到达的交通并提前做好准备直到小区过载并满足簇条件。

# 2)车辆簇的形成

移动网关候选在接收到基站的车辆分组列表后，利用车辆间距离对分组进行细化，形成最终的簇。假设有 $n ( i { = } 1$ ，2，...n)辆车在一个单车道上靠近BS。车辆聚类的准则是相邻车辆之间的距离不超过最小安全距离，车辆聚类的覆盖范围在通信半径内(例如，IEEE802.11p的传输范围约为 $2 5 0 m ^ { \cdot }$ ）

由于BS测量或预测的车辆位置信息可能不准确，移动网关候选者使用类似于AODV中的路由请求(RREQ)广播消息来验证相邻车辆并更新组成员列表。

# 3)簇头选择

簇形成后，在每个簇中选择一个CHV，以有效地将车辆相关业务中继到蜂窝网络。CHV选择可以由线性优化问题定义[39]。CHV 选择的目的是在车辆的信道质量和移动速度的约束下最大限度地提高主干链路的吞吐率。

具体来说，车辆速度越接近平均簇速度，该CHV候选者在该簇中停留的时间越长，其作为CHV的性能越好。同样，CHV和BS之间的信道质量越好，链接的平均生存时间越长，中继链路传输越可靠。

为了定量评价，本文提出了一个链路稳定系数(CV)来评价不同车辆链路的稳定性。CV的公式如下所示：式(5)(6)考虑了链路的相对速度和节点数，式(7)引用数学中的方差系数，确保不同节点数的不同路段的CV可以立即进行比较。

$$
a \nu = { \frac { \sum _ { i = 1 } ^ { n } V _ { i } } { n } }
$$

$$
s d = \sqrt { \frac { 1 } { n } \sum _ { i = 1 } ^ { n } ( V _ { i } - a \nu ) ^ { 2 } }
$$

$$
C V = \frac { s d } { a \nu } * 1 0 0 \%
$$

其中， $n$ 是源、目的车辆之间链路的跳数， $s d$ 是链路上车速的标准方差， $a \nu$ 是簇中所有车辆的平均速度， $V _ { i }$ 是车辆 $i$ 的速度。

车辆之间的链路生存时间定义为两个车辆保持通信以传输数据包的最短持续时间。为了避免频繁的网络分裂，采用CV 估计车速差。由于车辆的高速移动性，边界车辆在转发过程中驶出通信范围的概率较高。因此，考虑了车辆的行驶速度。簇中的车辆存储在一个列表中，该列表根据它们与源车辆的速度差进行排序，顶部的速度差较小。然后，车辆 $V _ { i }$ 和BS之间的链路有效时间为

$$
L _ { V _ { i } , B S } ( t ) = \frac { R - \sqrt { ( x _ { V i } - x _ { B S } ) ^ { 2 } + ( y _ { V i } - y _ { B S } ) ^ { 2 } } } { C V }
$$

其中， $R$ 是通信范围。

在一个簇内的车辆 $V _ { i } { = } \{ V _ { 1 } , V _ { 2 } , \cdots \}$ 过CHV与BS通信,对于每个 $V _ { i }$ ，计算链路寿命值 $L _ { V _ { i } , B S } ( t )$ ，并选择具有次最佳链路寿命的 $V _ { i }$ ，记录为备份CHV。如果CHV离开，备份CHV作为新的CHV工作。

# 3 最佳功率分配方案

在簇头车辆确定好后，本节提供了上述在1.2节缓存阶段缓存文件成功情况下 $a _ { 1 }$ 的最佳值的数学细节，使得它们在CHV1和CHV2处各自成功解码文件 $F _ { I }$ 和 $F _ { 2 }$ 的概率最大化。为此，本节首先推导出该情况下成功解码文件的概率表达式。

# 3.1成功解码的概率

当CHV1和CHV2的缓存中都有彼此的文件时，不管 $\boldsymbol { a } _ { 1 }$ 的值是多少，CHV1和CHV2都能够通过分别抵消 $F _ { 2 }$ 和 $F _ { 1 }$

的信号来解码 $F _ { 1 }$ 和 $F _ { 2 }$ 。

因此，在CHV1和CHV2 处成功解码 $F _ { 1 }$ 和 $F _ { 2 }$ 的概率分别由下式给出

$$
P _ { V 1 } ^ { ( A ) } = P \left\{ \frac { a _ { 1 } P _ { B } \left| h _ { B 1 } \right| ^ { 2 } } { \sigma _ { B 1 } ^ { 2 } } > \gamma _ { 1 } \right\}
$$

和

$$
P _ { V 2 } ^ { ( A ) } = P \left\{ \frac { a _ { 2 } P _ { B } \left| h _ { B 2 } \right| ^ { 2 } } { \sigma _ { B 2 } ^ { 2 } } > \gamma _ { 2 } \right\}
$$

$\gamma _ { 1 }$ 和 $\gamma _ { 2 }$ 分别表示在CHV1和CHV2 处成功解码F1和F2的SINR 阈值。

# 3.2功率分配

如前所述，成功解码 $F _ { 1 }$ 和 $F _ { 2 }$ 的概率是个体成功概率的乘积，即成功解码的概率取决于 $a _ { 1 }$ 。因此，上述情况的优化问题是

$$
{ \mathrm { O p t i m i z e } } _ { A } : { \mathrm { m a x } } P _ { V 1 } { } ^ { ( A ) } P _ { V 2 } { } ^ { ( A ) }
$$

接下来，本节通过以下命题证明上式中的代价函数在$0 { \leq } a 1 { \leq } 1$ 时是凹的。

引理1函数 $P ^ { ( A ) } \triangleq P _ { V 1 } ^ { ( A ) } P _ { V 2 } ^ { ( A ) }$ 在 $0 { \leq } a _ { 1 } { \leq } 1$ 时是凹的。

证明要证明 $P ^ { ( A ) }$ 相对于 $\mathbf { \Delta } _ { a _ { 1 } }$ 的二阶导数在 $0 \leq a _ { 1 } { \leq } 1$ 时是负的，首先，它们的概率密度函数 $f _ { | h _ { B 1 } | } ( \left| h _ { B 1 } \right| )$ 和 $f _ { | h _ { B 2 } | } ( | h _ { B 2 } | )$ [37]可以表示为

$$
f _ { | h _ { B i } | } ( | h _ { B i } | ) = \frac { 2 G _ { 0 , 2 } ^ { 2 . 0 } ( \frac { m _ { 1 } ^ { ( i ) } m _ { 2 } ^ { ( i ) } | h _ { B i } | ^ { 2 } } { \Omega _ { 1 } ^ { ( i ) } \Omega _ { 2 } ^ { ( i ) } } | _ { m _ { 1 } ^ { ( i ) } , m _ { 2 } ^ { ( i ) } } ) } { | h _ { B i } | \Gamma ( m _ { 1 } ^ { ( i ) } ) \Gamma ( m _ { 2 } ^ { ( i ) } ) }
$$

其中 $i { = } 1 , 2$ ， $\Gamma ( \bullet )$ 和 $G _ { m , n } ^ { p , q } \left( \bullet \right)$ 分别表示 Euler's gamma 和Meijer-G函数。此外，双Nakagami- $\cdot \mathbf { m }$ 分布式随机变量，也就是说， $\big | h _ { B 1 } \big | ^ { 2 }$ 和 ${ \left| h _ { B 2 } \right| } ^ { 2 }$ 具有双Gamma分布，它们各自的密度由随机变量的标准变换给出如下：

$$
\begin{array} { r } { f _ { \left| h _ { B i } \right| ^ { 2 } } ( \left| h _ { B i } \right| ) = \frac { 2 \left| h _ { B i } \right| ^ { \frac { m _ { 1 } ( i ) - m _ { 2 } ( i ) } { 2 } - 1 } } { \Gamma \left( m _ { 1 } ^ { ( i ) } \right) \Gamma \left( m _ { 2 } ^ { ( i ) } \right) \left( \displaystyle \frac { \Omega _ { 1 } ^ { ( i ) } \Omega _ { 2 } ^ { ( i ) } } { m _ { 1 } ^ { ( i ) } m _ { 2 } ^ { ( i ) } } \right) ^ { \frac { m _ { 1 } ^ { ( i ) } + m _ { 2 } ( i ) } { 2 } } } } \\ { \times \kappa _ { m _ { 1 } ^ { ( i ) } - m _ { 2 } ^ { ( i ) } } \left( 2 \sqrt { \displaystyle \frac { m _ { 1 } ^ { ( i ) } m _ { 2 } ^ { ( i ) } \left| h _ { B i } \right| } { \Omega _ { 1 } ^ { ( i ) } \Omega _ { 2 } ^ { ( i ) } } } \right) } \end{array}
$$

其中 $i { = } 1 , 2 , \kappa _ { n } ( \bullet )$ 是第二类修正的 Bessel 函数，具有 ${ \boldsymbol { n } } \in \mathbb { R }$ 阶 $\cdot [ 4 0 ]$ 。基于此，相应的CDF由下式给出

$$
f _ { \vert h _ { B i } \vert ^ { 2 } } ( \vert h _ { B i } \vert ) = \frac { G _ { 1 , 3 } ^ { 2 , 1 } ( \frac { m _ { 1 } ^ { ( i ) } m _ { 2 } ^ { ( i ) }  h _ { B i }  } { \Omega _ { 1 } ^ { ( i ) } \Omega _ { 2 } ^ { ( i ) } }  _ { m ^ { ( i ) } , m _ { 2 } ^ { ( i ) } , 0 } ) } { \Gamma ( m _ { 1 } ^ { ( i ) } ) \Gamma ( m _ { 2 } ^ { ( i ) } ) }
$$

其中 $_ { i = 1 , 2 }$ 。

$\left| h _ { B 1 } \right| = \frac { \gamma _ { 1 } \sigma _ { B 1 } ^ { 2 } } { a _ { 1 } P _ { B } }$ 和 $\left| h _ { B 2 } \right| = \frac { \gamma _ { 2 } \sigma _ { B 2 } ^ { 2 } } { a _ { 2 } P _ { B } }$ $P _ { V 1 } ^ { ( A ) }$ 和 $P _ { V 2 } ^ { ( A ) }$ 由式(14)给出，同时

$$
\begin{array} { c } { { \displaystyle { \frac { d ^ { u } } { d z ^ { u } } } G _ { p , q } ^ { m , n } \left( \frac 1 z \Big | _ { k _ { 1 } , \cdots , k _ { m } , k _ { m + 1 } , \cdots , k q } ^ { j _ { 1 } , \cdots , j _ { n } } \right) = \left( - 1 \right) ^ { u } z ^ { u } } } \\ { { G _ { p + 1 , q + 1 } ^ { m , n + 1 } \left( \displaystyle { \frac { 1 } { z } } \Big | _ { k _ { 1 } , \cdots , k _ { m } , 1 , k _ { m + 1 } , \cdots , k q } ^ { 1 - u , j _ { n } , j _ { n + 1 } , \cdots , j _ { p } } \right) , u = 1 , 2 , \cdots } } \end{array}
$$

基于此， $P _ { V 1 } ^ { ( A ) }$ 的一阶导数可以表示为

$$
\begin{array} { r l } & { \frac { d } { d a _ { 1 } } \left[ \frac { \displaystyle C _ { 1 , 3 } \left( m _ { 2 } ^ { ( 1 ) } m _ { 2 } ^ { ( 1 ) } \frac { \gamma _ { 1 } \sigma _ { B _ { 1 } } ^ { 2 } } { { \varOmega } _ { 1 } ^ { ( 1 ) } { \varOmega } _ { 2 } ^ { ( 1 ) } } \left| _ { n _ { 1 } ^ { ( 1 ) } , m _ { 2 } ^ { ( 1 ) } , 0 } \right. \right) } { \displaystyle \Gamma \left( m _ { 1 } ^ { ( 1 ) } \right) \Gamma \left( m _ { 2 } ^ { ( 1 ) } \right) } \right] } \\ & { \quad \quad - \frac { \displaystyle \sum _ { i = 1 } ^ { 0 } \sum _ { 2 } ^ { ( 1 ) } a _ { 1 } P _ { B } } { \displaystyle \frac { m _ { i } ^ { ( 1 ) } m _ { 2 } ^ { ( 1 ) } \gamma _ { 1 } \sigma _ { B _ { 1 } } ^ { 2 } } { \Gamma \left( m _ { 1 } ^ { ( 1 ) } \right) \Gamma \left( m _ { 2 } ^ { ( 1 ) } \right) } \times { \cal G } _ { 2 , 4 } ^ { 2 , 2 } \left( \frac { m _ { 1 } ^ { ( 1 ) } m _ { 2 } ^ { ( 1 ) } \frac { \gamma _ { 1 } \sigma _ { B _ { 1 } } ^ { 2 } } { a _ { 1 } P _ { B } } } { \displaystyle \Omega _ { 1 } ^ { ( 1 ) } { \varOmega } _ { 2 } ^ { ( 1 ) } } \left| _ { n _ { 1 } ^ { ( 1 ) } , m _ { 2 } ^ { ( 1 ) } , 0 } \right. \right) } } \end{array}
$$

接下来，定义

$$
\beta _ { 1 } \triangleq \frac { m _ { 1 } ^ { ( 1 ) } m _ { 2 } ^ { ( 1 ) } \frac { \gamma _ { 1 } \sigma _ { B 1 } ^ { 2 } } { P _ { B } } } { \Omega _ { 1 } ^ { ( 1 ) } \Omega _ { 2 } ^ { ( 1 ) } } > 0
$$

同时，由于 $m _ { l } { > } 0 , m _ { 2 } { > } 0$ 它遵循

$$
G _ { 2 , 4 } ^ { 2 , 2 } \left( \frac { \beta _ { 1 } } { a _ { 1 } } \bigg | _ { m _ { 1 } ^ { ( 1 ) } , m _ { 2 } ^ { ( 1 ) } , 1 , 0 } ^ { 0 , 1 } \right) = 2 \left( \frac { \beta _ { 1 } } { a _ { 1 } } \right) ^ { \frac { m _ { 1 } ^ { ( 1 ) } + m _ { 2 } ^ { ( 1 ) } } { 2 } } \times \kappa _ { m _ { 2 } ^ { ( 1 ) } - m _ { 1 } ^ { ( 1 ) } } \left( 2 \sqrt { \frac { \beta _ { 1 } } { a _ { 1 } } } \right)
$$

显然，通过简化式(17)，代入式(19)并求二阶导数，可以得到一个可以简化的项，如下所示。

$$
\begin{array} { r l } & { \cfrac { d ^ { 2 } } { d a _ { 1 } ^ { 2 } } \bigg [ a _ { 1 } G _ { 2 , 4 } ^ { 2 , 2 } \bigg ( \cfrac { \beta _ { 1 } } { a _ { 1 } } | _ { n _ { n } ^ { ( 1 ) } , n _ { 2 } ^ { ( 1 ) } , 1 , 0 } \bigg ) \bigg ] = } \\ & { \kappa _ { m _ { n } ^ { ( 1 ) } - m _ { n } ^ { ( 1 ) } } \left( 2 \sqrt { \cfrac { \beta _ { 1 } } { a _ { 1 } } } \right) \Bigg \{ 2 \bigg ( \cfrac { \beta _ { 1 } } { a _ { 1 } } \bigg ) ^ { m _ { n } ^ { ( 1 ) } + m _ { 2 } ^ { ( 1 ) } } - \cfrac { \beta _ { 1 } ( m _ { 1 } ^ { ( 1 ) } + m _ { 2 } ^ { ( 1 ) } ) } { a _ { 1 } } \bigg ( \cfrac { \beta _ { 1 } } { a _ { 1 } } \bigg ) ^ { m _ { n } ^ { ( 1 ) } + m _ { 2 } ^ { ( 1 ) } - 1 } \Bigg \} - } \\ & { \bigg ( \cfrac { \beta _ { 1 } } { a _ { 1 } } \bigg ) ^ { \frac { m _ { n } ^ { ( 1 ) } + m _ { 2 } ^ { ( 1 ) } } { 2 } - 1 } \left[ - \kappa _ { m _ { n } ^ { ( 1 ) } - m _ { n } ^ { ( 1 ) } - 1 } \left( 2 \sqrt { \cfrac { \beta _ { 1 } } { a _ { 1 } } } \right) - \kappa _ { m _ { n } ^ { ( 1 ) } - m _ { n } ^ { ( 1 ) } + 1 } \left( 2 \sqrt { \cfrac { \beta _ { 1 } } { a _ { 1 } } } \right) \right] } \end{array}
$$

$P _ { V 2 } ^ { ( A ) }$ 的一阶和二阶导数也可以得到类似的表达式。此外，利用Bessel函数恒等式：

$$
\kappa _ { - \nu } ( x ) = \kappa _ { \nu } ( x ) , \nu = 0 , 1 , \cdots
$$

有助于简化 $\kappa _ { m _ { 2 } ^ { ( 1 ) } - m _ { 1 } ^ { ( 1 ) } }$ ()，无论 ${ m _ { 1 } } ^ { ( 1 ) }$ 是大于还是小于 ${ m _ { 2 } } ^ { ( 1 ) }$ 。还要注意的是，以下不等式成立：

$$
\kappa _ { u } ( x ) \geq \kappa _ { \nu } ( x ) , u , \nu = 0 , 1 , \cdot \cdot \cdot x \in \mathbb { R } ^ { + }
$$

使用上述结果简化 $P _ { V 1 } ^ { ( A ) }$ 和 $P _ { V 2 } ^ { ( A ) }$ 两者的一阶和二阶导数，可以证明 $P ^ { ( A ) }$ 的二阶导数是负的，在极限情况下 $ { \boldsymbol { a } } _ { 1 } {  } 0$ 和 $\displaystyle a _ { 1 } \to 1$ 时，它们各自的一阶导数可以显示为具有正值和负值。在此基础上，通过一些代数运算，即可证明 $P ^ { ( A ) }$ 在 $0 \leq a 1 \leq 1$ 时是凹的。

# 4 仿真结果与分析

在本节中，使用MATLAB仿真软件验证了所提出的基于 SDN的车联网中缓存辅助NOMA的性能，并将其性能与传统的NOMA和缓存辅助OMA系统进行了比较。仿真参数如表1所示。其中， $m _ { 1 } { } ^ { ( 1 ) } = m _ { 2 } { } ^ { ( 1 ) } = m _ { 1 } { } ^ { ( 2 ) } = m _ { 2 } { } ^ { ( 2 ) } = 1$ ， $\Omega _ { 1 } { } ^ { ( 1 ) } = \Omega _ { 2 } { } ^ { ( 1 ) } = \Omega _ { 1 } { } ^ { ( 2 ) } =$ $\Omega _ { 2 } { } ^ { ( 2 ) } = 2$ ，噪声方差 $\sigma _ { B 1 } ^ { 2 } = \sigma _ { B 2 } ^ { 2 } = 1$ ，SINR门限 $\gamma _ { 1 } = \gamma _ { 2 } = 1$ ，Zipf 参数 $\lambda = 0 . 5$ 。因为受欢迎文件由Zipf分步建模，最佳缓存策略是缓存最受欢迎的文件，具体取决于CHV1和CHV2的缓存大小。

表1仿真参数  
Tab.1Simulation parameters   

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>路段长度/m</td><td>200</td></tr><tr><td>路段宽度/m</td><td>2×5</td></tr><tr><td>车辆空间密度/veh·m2</td><td>0.01~0.04</td></tr><tr><td>车辆平均速度/km·h1</td><td>60</td></tr><tr><td>路径损耗指数</td><td>2</td></tr><tr><td>在BS的文件数,T</td><td>5</td></tr><tr><td>在CHV1和CHV2 的缓存大小</td><td>1</td></tr></table></body></html>

从图4可以看出，将SDN使能的自适应分簇与现有机制进行比较，并在仿真中考虑了三种情况：SDN使能的方案，使用车辆之间的链路生存时间来选择CHV；传统方法，选择中心车辆作为CHV；以及没有分簇的场景(车辆通过自己的链接与BS通信)。图4显示了三种不同场景下误码率与信噪比的仿真结果。可以看出，通常分簇为车辆提供更好的通信质量，这是合理的，因为车辆分簇方案使用IEEE802.11p网络来减轻蜂窝网络的负担，从而保证蜂窝无线链路连接质量。同样，所提出的簇头选择方案具有最低的中继链路误码率，尤其是在较高信噪比的情况下，这是因为所提出的簇头选择方案在选择簇头时同时考虑了车辆的信道质量和移动速度，因此最终得到具有更好的无线链路质量并且在簇中服务更长时间(更少的信道切换)的最佳信道。显而易见，SDN使能的车载网在满足5G中的关键技术要求方面具有更好的性能，同时保持了SDN对于5G网络的灵活性、可编程性。

![](images/1b062a166dfbd3d60738dde030527bbec44df7bd29fa9360c1f62cc89f739885.jpg)  
图4三种不同的车辆分簇和CHV选择方法对比Fig.4Comparison of three different vehicle clustering and CHVselection methods

图5比较了缓存辅助的NOMA系统和缓存辅助的OMA系统在Nakagami-m和双Nakagami-m衰落条件下的性能，它们被认为适用于车对车通信。为此，考虑了不同的 $\lambda$ 值，信噪比为10dB。在这两种情况下,NOMA的性能都优于OMA。尽管对于NOMA和OMA来说，在双Nakagami-m衰落条件下的性能比在统的Nakagami-m衰落下差一点，这是可以预期的，是由于Nakagami-m模型的级联特性造成的。然而，与NOMA相比，OMA的退化程度是严重的，特别是在 $\lambda \to 0$ 的区域，这具有实际意义。

![](images/2023715e012147e79a9dd8efb664088baf34e4c2764ae7eb94d339ca5b48224b.jpg)  
图5不同分布下缓存辅助的NOMA和缓存辅助的OMA成功解码概率随变化的性能对比  
Fig.5Performance comparison of caching aided NOMA and caching aided OMA,in terms of variation of probability of successful decoding with different values of,under Nakagami and double Nakagami distributions.

图6比较了缓存辅助的NOMA和缓存辅助的OMA系统对于不同λ值和可在CHV1和CHV2获得的缓存大小的性能。接收信噪比固定在10dB，观察到随着CHV1和CHV2的缓存增大提高了NOMA和OMA的性能，因为缓存另一辆车请求的文件的概率随着缓存大小而增加。同样，对于较低的λ值，观察到与OMA对应系统相比，NOMA系统提供了显著的性能增益，而随着λ的增加，它也表现出较慢的性能下降。

图7描述了所提出的方案的性能，并针对不同的Zipf参数λ值将其与缓存辅助OMA进行了比较。如预期的那样，所提出的缓存辅助NOMA为所有λ值提供了更好的性能。此外，由于较高的λ值使得流行度曲线更偏向第一个文件，所以NOMA和OMA的性能都随着的增大而提升。这是因为缓存文件成功发生的概率随着而增加，支配着平均性能。与OMA相比，高速缓存辅助NOMA对低λ值的性能提升非常显著。

图8比较了缓存辅助的NOMA和传统的NOMA对于在CHV1和CHV2的不同数量的高速缓存文件的性能。同样，缓存辅助的NOMA实现的性能优于传统的NOMA，并且如预期的那样，随着缓存文件数量的增加而提升，缓存辅助的

NOMA 双Nakagami-m而获得的性能优于传统NOMANakagami- $\cdot \mathbf { m }$ 的性能。

![](images/55695592e8468fed757cf5048a5e9122daf026e2ac411729a14a808f5a27ed62.jpg)  
图6可在车辆处获得的不同缓存大小数量的缓存辅助的NOMA和 缓存辅助的OMA成功解码概率随λ变化的性能对比 Fig.6Performance comparison of caching aided NOMA and caching aided OMA,in terms of variation of probability of successful decoding with λ,fordifferentvalues of cache sizesavailable at CHV1 and CHV2.

![](images/629b7a626a9d447509770bf1ed5511e0f08846c147c5c2b43174aa7bc7ef14e2.jpg)

![](images/f34338fdfbba2890122e376dc943ab13e227c46e74784ee8cef049707e70f9fa.jpg)  
图7在不同的λ值下缓存辅助的NOMA和缓存辅助的OMA成功 解码概率随信噪比变化的性能对比 Fig. 7Performance comparison of caching aided NOMA and caching aided OMA,in terms of variation of probability of successful decoding with SNR,for different values of $\lambda$   
图8在Nakagami-m 和双Nakagami-m分布下缓存辅助的NOMA和 传统的NOMA成功解码概率随不同数量的缓存文件变化的性能对比 Fig.8Performance comparison of caching aided NOMA and conventional NOMA,in terms of variation of probability of successful decoding for different numberof cached files,under Nakagami-m and double Nakagami-m distributions

图9显示了由于缓存引起的干扰消除对所提出的NOMA系统的影响。可以看出，与传统的NOMA系统相比，所提出的缓存辅助的NOMA系统随着CHV1和CHV2处的高速缓存大小的增加而提供了更好的性能。此外，对于基站可用的总文件T的较低值，性能也有所提高。这是因为较小的总文件数T和较大的缓存大小提高了在缓存阶段缓存所请求文件的概率。此外，当CHV1和CHV2的缓存大小为零时，即当CHV1和CHV2在缓存阶段不缓存任何文件时，传统NOMA和缓存辅助NOMA的性能是相等的。

![](images/76368f36e219b9aa581793cc0eb645ddb49bb90bc4d2b02e111dc546a6e18bb4.jpg)  
图9对于BS可用的不同文件数量缓存辅助的NOMA和传统的 NOMA成功解码概率随在每辆车上不同缓存大小变化的性能对比 Fig.9Performance comparison of successful decoding probability of cache aided NOMA and conventional NOMA,in terms of variation of probability of successful decoding with different cache sizes at each vehicle,fordifferent numberoffilesavailableat theBS.

# 5 结束语

针对车联网中频谱资源稀缺、海量数据传输产生的大量回程开销以及使用NOMA技术引起的SIC计算复杂度高等问题，在已有研究工作的基础上，本文提出了一种软件定义车联网缓存辅助的NOMA功率分配方案。首先，在车联网中借助SDN进行预测到达的道路交通，实现自适应车辆分簇。其次，引入了缓存辅助的NOMA方案，考虑了文件缓存的情况，每个车辆缓存并请求整个文件。针对在双Nakagami-m衰落信道上两簇头车辆无线传输的情况下实现的提出了一种最佳功率分配策略，使每辆车成功解码文件的总体概率最大化。同时，证明了相关的代价函数在功率分配变量中是凹的。最后，数值仿真和理论分析表明，与传统的NOMA和缓存辅助的OMA相比，所提出的缓存辅助的NOMA性能大大提升。作为未来工作的一部分，将进一步研究分割文件的缓存情况。例如，可以考虑将每个文件分割成两部分，研究车辆和缓存的分割文件之间的联合功率分配优化问题。

# 参考文献：

[1]Guo Shengjie,Zhou Xiangwei. Robust Resource Allocation with Imperfect Channel Estimation in NOMA-based Heterogeneous Vehicular Networks [J].IEEE Transactions on Communications,2019,67 (3): 2321-2332.   
[2]Sepulcre M, Gozalvez J.Heterogeneous V2V Communications in MultiLink and Multi-RAT Vehicular Networks [J].IEEE Transactions on Mobile Computing,2021,20(1):162-173.   
[3]Vinel A.3GPP LTE versus IEEE 802.11p/WAVE:Which technology is able to support cooperative vehicular safety applications? [J].IEEE Wireless Communications Letters,2012,1(2):125-128.   
[4]Wang Chengxiang,Haider F,Gao Xiqi,et al.Cellular architecture and key technologies for 5G wireless communication networks [J]. IEEE Communications Magazine,2014,52 (2):122-130.   
[5]Salahuddin MA,Alfuqaha A,Guizani M. Software-defined networking forRSU clouds in support of the internet of vehicles [J]. IEEE Internet of Things Journal,2015,2 (2): 133-144.   
[6]He Zongjian,Cao Jiannong，Liu Xuefeng.SDVN:enabling rapid network innovation for heterogeneous vehicular communication [J]. IEEE Network,2016,30 (4):10-15.   
[7]Nkenyereye L,Nkenyereye L,Islam S MR,et al.Software Defined Network-Based Multi-Access Edge Framework for Vehicular Networks [J].IEEE Access,2020,8:4220-4234.   
[8]Ge Xiaohu,Li Zipeng,Li Shikuan.5G software defined vehicular networks [J].IEEE Communications Magazine,2017,55(7): 87-93.   
[9]Kazmi A, Khan M,Akram M. DeVANET: Decentralized softwaredefined VANET architecture [C]. IEEE International Conference on Cloud Engineering Workshop,Berlin,Germany,2016: 04-08.   
[10] Correia S,Boukerche A, Meneguette R I. An architecture for hierarchical software-defined vehicular networks [J]. IEEE Communications Magazine,2017,55(7): 80-86.   
[11] Li Liying, Zhao Guodong, Blum R S.A survey of caching techniques in cellular networks: Research issues and challenges in content placement and delivery strategies [J]. IEEE Communications Surveys & Tutorials, 2018,20 (3): 1710-1732.   
[12] Maddah-AliMA,Niesen U.Coding for caching: Fundamental limits and practical challenges [J].IEEE Communications Magazine, 2016,54 (8): 23-29.   
[13] Yao Yang, Chenchen, Chen Zhiyong,et al. Analysis on cache-enabled wireless heterogeneous networks [J].IEEE Transactions Wireless Communications,2016,15 (1): 131-145.   
[14] Cui Ying,Jiang Dongdong.Analysis and optimization of caching and multicasting in large-scale cache-enabled heterogeneous wireless networks [J]. IEEE Transactions on Wireless Communications,2017,16 (1): 250-264.   
[15] Ji Mingyue,Caire G,Molisch A F.Fundamental limits of caching in wireless D2D networks [J]. IEEE Transactions on Information Theory, 2016,62 (2): 849-869.   
[16] Gregori M, Gómez-Vilardeb J,Matamoros J,et al.Wireless content caching for small cell and D2D networks [J]. IEEE Journal on Selected Areas in Communications,2016,34 (5): 1222-1234.   
[17]刘可欣，陈桂芬．基于移动边缘计算的车联网缓存策略研究[J].计 算机应用研究，2021,38(03):851-854.(Liu Kexin,Chen Guifen. Rearch on caching strategy of Internet of Vehicles based on mobile edge computing [J].Application Research of Computers,2021,38 (03): 851- 854.)   
[18] Zaidi S A R,Ghogho M,McLernon D C,et al.Information centric modeling for two-tier cache enabled cellular networks [C].Proceedings of IEEE International Conference on Communication Workshop,London, United Kingdom,2015: 80-86.   
[19] Bastug E,Bennis M, Debbah M. Cache-enabled small cell net-works: Modeling and tradeoffs [C].Proceedings of 1lth International Symposium on Wireless Communication Systems,Barcelona, Spain, 2014: 649-653.   
[20] Zhang Lei,Yang Hongchuan,Hasna M O.Generalized area spectral efficiency: An efective performance metric for green wireless communications [J]. IEEE Transactions on Communications,2014,62 (2): 747-757.   
[21] Glass S,Mahgoub I, Rathod M.Leveraging MANET-based cooperative cache discovery techniques in VANETs: Asurvey and analysis [J]. IEEE Communications Surveys & Tutorials,2017,19 (4): 2640-2661.   
[22]Majd NE,Misra S,TouraniR.Split-cache:A holistic caching framework for improved network performance in wireless ad hoc networks [C]. Proceedings of IEEE Global Communications Conference, Austin, USA, 2014: 137-142.   
[23] Zhang Xi, Wang Jingqing. Heterogeneous Statistical QoS-Driven Power Allcatin for Collaborative D2D Caching Over Edge-Computing Networks [C]. Proceedings of IEEE 39th Intermational Conference on Distributed Computing Systems, Dallas, USA,2019: 944-953.   
[24] Mounchili S,Hamouda S.Pairing Distance Resolution and Power Control for Massive Connectivity Improvement in NOMA Systems [J]. IEEE Transactions on Vehicular Technology,2020,69 (4): 4080-4090.   
[25] Ji Yancheng，Duan Wei,Wen Miaowen，et al.Spectral eficiency enhanced cooperative device-to-device systems with NOMA [J]. IEEE Transactions on Intelligent Transportation Systems,2021,2(7):4040- 4050.   
[26] Liu Yuanwei, Qin Zhijin,Elkashlan M,et al. Non-orthogonal multiple access in large-scale heterogeneous networks [J]. IEEE Journal on Selected Areas in Communications,2017,35 (12): 2667-2680.   
[27] Chen Yingyang,Wang Li, Ai Yutong,et al.Performance analysis of NOMA-SM in vehicle-to-vehicle massive MIMO channels [J]. IEEE Journal on Selected Areas in Communications,2017,35 (12): 2653-2666.   
[28] Zeng Ming,Yadav A,Dobre O A,et al. On the sum rate of MIMONOMA and MIMO-OMA systems [J]. IEEE Wireless Communications Letters,2017,6(4): 534-537.   
[29] Dai Linglong,Wang Bichai, Yuan Yifei,et al.Non-orthogonal multiple acessfor 5G: Slutions,challenges,opportunities,and futurersarch trends [J].IEEE Communications Magazine,2015,53 (9): 74-81.   
[30] Han Tao,Gong Jie,Liu Xiong，et al.On downlink NOMA in heterogeneous networks with non-uniform small cell deployment [J]. IEEE Access,2018,6: 31099-31109.   
[31] Di Boya,Song Lingyang,Li Yonghui,et al. NOMA-based low-latency and high-reliable broadcast communications for 5G V2X services [C]. Proceedings of IEEE Global Communications Conference,Marina Sands Bay, Singapore,2017: 1-6.   
[32] Tanwar S,Tyagi S,Budhiraja I,et al. Tactile Internet for Autonomous Vehicles:Latencyand Reliability Analysis[J]. IEEE Wireless Communications,2019,26 (4): 66-72.   
[33] Khoueiry B W,Soleymani M R.An efficient NOMA V2X communication scheme in the Internet of Vehicles [C].Proceedings of IEEE 85th Vehicular Technology Conference,Sydney,NSW,2017: 1-7.   
[34] Qian LiPing,Wu Yuan,Zhou Haibo,et al.Dynamic cell association for non-orthogonal multiple-access V2S networks [J]. IEEE Journal on Selected Areas in Communications,2017,35 (10): 2342-2356.   
[35] Doan KN,Shin W, Vaezi M,etal. Optimal power allocation in cacheaided non-orthogonal multiple access systems [C].Proceedings of IEEE International Conference on Communications Workshops,Kansas, USA, 2018: 1-6.   
[36] Ding Zhiguo,Fan Pingzhi, Karagiannidis G K,et al. NOMA assisted wireless caching:Strategies and performance analysis [J]. IEEE Transactions on Communications,2018,66 (10): 4854-4876.   
[37] Karagiannidis GK, Sagias NC,Mathiopoulos PT. N\*Nakagami: A novel stochastic model for cascaded fading channels [J].IEEE Transactions on Communications,2007,55 (8): 1453-1458.   
[38] Salo J,El-Sallabi HM,Vainikainen P.The distribution of the product of independent Rayleigh random variables [J].IEEE Transactions on Antennas and Propagation,2006,54 (2): 639-643.   
[39] Duan Xiaoyu,Wang Xianbin,Liu Yanan.SDN Enabled Dual Cluster Head Selection and Adaptive Clustering in 5G-VANET[C].Proceedings ofIEEE 84th Vehicular Technology Conference,Montreal,Canada,2016: 6-12.   
[40] Gradshteyn I,Ryzhik I. Tables of Integrals,Series and Products,7 thed. [M]. Academic Press,2007.