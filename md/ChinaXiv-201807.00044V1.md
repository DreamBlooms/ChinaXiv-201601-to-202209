# 车联网仿真测试评价技术研究综述

王润民，邓晓峰，徐志刚，赵祥模(长安大学 车联网教育部一中国移动联合实验室，西安 710064)

摘要：车联网的大规模部署及其在智能网联汽车领域的广泛应用前需要对其性能及功能进行全面、深入的测试评价，其中通过仿真技术对其进行评价分析是当前的主流测试评价手段。从车联网研究及应用过程中的测试评价需求出发，总结了主流的网络仿真器和交通仿真器，对现有车联网仿真平台进行了分类，研究并对比分析了典型的车联网仿真平台；针对车联网的应用特性，研究并归纳了影响车联网仿真性能的车辆移动模型、信道传播模型及驾驶员行为等；从网络仿真指标、车联网应用相关指标归纳了车联网功能及性能测试的典型评价指标；最后探讨了车联网仿真测试的发展方向。

关键词：智能网联汽车；车联网；测试评价；交通仿真；网络仿真；评价指标中图分类号：TP391.9 doi:10.3969/j.issn.1001-3695.2018.05.0260

# Survey on simulation testing and evaluation of internet of vehicles

Wang Runmin, Deng Xiaofeng, Xu Zhigang, Zhao Xiangmo (JointLaboratory for Internetof Vehicles,Ministryof Education&China MobileCommunications Corporation,Chang'an University,Xi,an710064,China)

Abstract:Large-scale deploymentofIoVsand itsextensiveapplication inthefieldof inteligentconnectedvehiclerequire comprehensiveand in-depth testingand evaluationoftheir performance and functionality.However,testing and evaluation in real environments presents high costand dificult problems.Therefore,simulation has currently become amainstreamtesting tool.This article first summarized the mainstream network simulators and traffc simulators，clasified theexistingIoVs simulation platforms,studiedand comparativelyanalyzed typical IoVs platforms,andthensummarized vehicle mobility models，channel propagation modelsand driver behaviors that affectthe simulation performance of IoVs based on the application characteristics.The typical metrics of the functions and performance tests of IoVs were summarized form the network simulation indicatorsandrelevant indicatorsfor theapplicationofIoVs.Finally,we discussedthedeveloingtrendof the simulation test of IoVs.

Keywords:Intelligentand Connected Vehicles；Internetof Vehicles;TestingandEvaluation;Traffc simulation;Network simulation;Metrics

# 0 引言

随着以互联网与人工智能为核心的新一代技术革命的迅猛发展，自动驾驶技术不断取得突破性进展，智能化和网联化成为汽车发展的重要方向，“中国制造2025”已将智能网联汽车产业作为重点领域之一。其中车联网（Internetofvehicles,IoV）技术是传统汽车向智能化、网联化转变的关键技术之一，也是智能网联汽车体系架构的重要组成部分，近年来得到了业界的广泛关注和深入研究。目前最受推崇的车联网技术有以IEEE802.11p为主的DSRC协议和基于蜂窝技术的C-V2X协议（含LTE-V与演进的5G-V2X两种)，具有车-车通信（V2V）、车-路通信（V2I）、车-人通信（V2H）及车与公共网络之间的通信（V2N）等四种方式，涵盖了交通信息收集、实时交通路况监测、紧急信息发布、辅助驾驶、车-车协同驾驶、编队行驶、车辆远程驾驶、高精度地图下载、娱乐多媒体等多种应用场景。

为了保证智能网联汽车在各种道路交通状况、气象环境和使用场景下都能够安全、可靠、高效的运行，需要进行大量的测试验证，经历复杂的演进过程。因此测试评价是开展智能网联汽车技术研发和应用不可或缺的重要环节，是车联网基础设施及装备进行大规模部署，并开展及其在智能汽车领域的广泛应用的重要手段[1]。车联网本质上是一种特殊的移动自组织网络（mobile Adhoc networks,MANET)，一方面，它继承了传统MANET中节点高速运动、网络拓扑结构变化频繁的特性；另一方面，它又拥有区别于传统MANET的特性[2.3]，主要包括车辆节点受道路静态形状的限制；车辆节点的运动受到实时交通状态（拥塞程度、交通灯状态、交通管制等）及驾驶员行为的影响；无线网络信道质量受车辆相对速度、路边建筑物遮挡、多径效应等多种因素影响等。正是因为这些特性，使得研究开发人员在实际道路环境下对车联网协议或基于车联网实现的自动驾驶应用的功能及性能测试时，需要在道路及车辆上进行车联网基础设施及车联网终端设备的大规模部署；此外在研究车联网技术与交通要素、网络信道传输间的相互作用相互影响时，需要在城市、高速、乡村等各种不同的道路环境下构造各种各样的测试场景。因此虽然在真实环境下进行车联网的研究与测试是最直接、最有效的方法，但受测试成本、场地、人员的规模，测试场景高度重现难度及测试安全性等因素影响，基于仿真技术开展车联网的测试评价及研究开发依然是一种主要技术手段。

文献[2]在国内首次对车联网仿真器进行了分类，并对车联网仿真的发展历程、研究现状及问题进行了综述，但仅限于对车联网仿真工具的阐述和介绍，未对影响车联网仿真的要素进行研究总结，且涵盖的仿真器种类较少；文献[3]不仅对常见车联网仿真平台进行了比较研究与综述，且提出道路拓扑、多径衰落、障碍物、交通流模型、车辆移动性对车联网的仿真有重要影响，但没有详述各因素的具体影响水平，也没有对如何对车联网的性能进行评价作出论述；文献[4]对车联网仿真中的车辆移动模型和信道模型及其对交通环境的适应性优化进行了研究，但也未对如何对车联网的性能进行评价作出论述；此外部分文献如[5.6]从车辆跟驰模型、事故预警等具体交通情景的角度利用仿真工具对车联网性能及功能进行了仿真测试，但仅涉及从其各自的应用角度对车联网的仿真测试评价。文献研究表明，目前还没有文献从车联网仿真平台、影响车联网仿真测试结果的因素及测试评价指标等各方面全方位的对车联网的仿真测试及评价技术进行阐述。基于上述背景，本文从车联网仿真测试评价技术出发，在总结目前主流的网络仿真器和交通仿真器的基础上，首先对现有车联网仿真平台进行了分类；然后研究了目前典型的车联网仿真平台，并对各平台进行对比分析；最后针对车联网的应用特性，系统地归纳了影响车联网仿真测试性能的交通场景、通信模型及车联网仿真评价指标。

# 1 车联网仿真平台分类

车联网仿真平台的构建离不开两大基本组件，一是网络仿真器，针对车联网节点之间的交通数据传输、接收以及后台负载、路由、链路和信道进行报文级别的仿真[7；另一个是交通仿真器，主要用于生成逼真的车辆运行轨迹，并将其用于网络仿真器的输入。车联网的仿真涉及到交通仿真和网络仿真两个方面，但并不是交通仿真和网络仿真的简单叠加。目前主流的车联网仿真平台一般都是基于这两种仿真器的深度耦合，从而达到使仿真环境更趋于真实环境的目的。具体是根据不同的车辆移动模型在交通仿真器中生成逼真的车辆运行轨迹，并输入到网络仿真器中，通过二者的交互能够验证不同的网络协议在不同的车辆移动模型下的表现。

目前多种网络仿真器可以应用于车辆通信节点之间的通信性能测试，例如NS2[8]、NS3[9]、JiST/SWANS[10]、OMNeT $+ + ^ { [ 1 1 ] }$ 、QualNet[12]、OPNET[13]、GTNetS[14]等，它们都支持多种无线网络通信协议，包含或者能够拓展支持节点移动模型。此外，目前也已经存在许多较为成熟的交通仿真器，例如 SUMO[15]、VISSIM[16]、PARAMICS[17]、TransModeler[18]、TRANSIM[19]、CORSIM[20]。目前很多流行的车联网仿真平台都是基于上述仿真器开发的，但这些仿真平台却对如何将两种仿真器进行深度耦合有着不同解决方案，根据耦合思路的差异，本文将目前常见的车联网仿真平台分为分离式、嵌入式、联合式、集成式四类。

# 1.1分离式车联网仿真平台

分离式车联网仿真平台是指将交通仿真器与网络仿真器进行简单的单向链接，将交通仿真器生成的车辆运行轨迹文件，输入网络仿真器中进行节点之间无线网络通信的仿真，如图1所示。如CARLINK/CMU[21]、CORSIM/QuelNet[22]、MITSIMLAB/NS2[23]。这种方式的优点在于操作简单，易于实现，但缺点也很明显，因为车辆运行轨迹一旦在交通仿真器中确定，在网络仿真器中就是不可修改的，这明显与实际情况不同，在实际环境下，车辆运行轨迹一定会受到网络通信结果的影响而有所改变。在这种方式下，割裂了两者之间的关系，实际上是单独运行两种仿真，只能进行简单的车联网仿真工作，目前已经很少使用。

![](images/69c75c3171653b1e6f6c4a5f7eeba100ff33eb754860a86d83463ab0e5472a64.jpg)  
图1分离式车联网仿真平台

# 1.2嵌入式车联网仿真平台

嵌入式车联网仿真平台是指利用现有的网络仿真器、交通仿真器或者中间件，嵌入所需要的相应模块以构建完整的车联网仿真平台，主要有三种嵌入方案，如图2所示。

![](images/cfd3c255321316a5e93c13a6d777d3d53c1cb1c6ce01dbf53277a24e287d0466.jpg)  
图2嵌入式车联网仿真平台

a)在网络仿真器中嵌入交通仿真模块，这也是在嵌入式中应用最多的方案，如前文所述，现有网络模拟器中已经集成了简单的节点移动模型，只需要在此基础上添加更加复杂、逼近真实情况的车辆移动模型就可以实现。如：STRAW/SWANS[24]、ASH[25]、NS3 extension[26]。相较于在交通仿真器中嵌入各种复杂的网络协议与通信模式，这种方案代价更小，更加易于实现。

b）在交通仿真器中嵌入无线网络仿真模块，如TSM[27]。这种方案在具体应用中并不常见，主要原因在于操作难度比较大，要依靠自己开发大量复杂的网络协议与通信模式，无线网络通信的稳定性得不到保证。

c）利用可扩展的仿真中间件（如ARTiS)，嵌入交通仿真模块与无线网络仿真模块，如 MoVES[28]。这样做的好处在于两个模块的编程能在一个程序中实现，有利于更加及时的信息交互与反馈，但会耗费大量的人力与时间。

# 1.3联合式车联网仿真平台

联合式车联网仿真平台是指充分利用现有的网络仿真器与交通仿真器，将其进行双向链接，利用中间件进行信息的交互，如图3所示。CARISMA/NS2[29]、TraNS[30]、Veins[31]、MobiREAL[32]、iTETRIS[33]、SimIVC[34]等都是采用这种方式,与分离式仿真平台不同，该类仿真平台中车辆运行轨迹在仿真过程中是实时变化的，在仿真过程中，如果当前车辆节点接收到了来自其他车辆节点的消息，且这个消息需要改变当前车辆节点的运行状态（例如收到来自前方车辆节点紧急制动的消息)，那么网络仿真器就会给交通仿真器提出一个请求（网络反馈)，交通仿真器在接收到请求之后调整车辆节点的运行状态，然后将车辆节点的最新位置与速度等信息发给网络仿真器（交通反馈),这种方式最大的优点就是实现了网络仿真器与交通仿真器的实时信息交互。虽然在仿真速度与效率上不及嵌入式与集成式方案，但由于使用的都是成熟的网络仿真器与交通仿真器，因此能够支持大量的无线网络通信协议以及复杂的车辆移动模型，仿真精度高，在目前的车联网仿真领域应用广泛。

![](images/72ae4cbed75bdcbdd003813352a4c01a7a0b3f5c341e899cf34f3747dee9eda4.jpg)  
图3联合式车联网仿真平台

# 1.4集成式车联网仿真平台

集成式车联网仿真平台是指独立的车联网仿真平台，集成仿真所需的交通仿真模块与无线网络仿真模块，如NCTUns[35]、Gorgorin[36]、GrooveNET[37]、AutoMesh[38]、VSimRT[[39]。这种仿真平台的交通仿真模块与无线网络仿真模块耦合的紧密度最高，因此在仿真速度与效率上更快更高，缺点在于难度较大、开发周期较长，且由于自行独立开发，因此仿真的精确度难以与成熟的网络仿真器和交通仿真器比较。

# 2 典型车联网仿真平台

# 1）TraNS

TraNS通过NS2网络仿真器和SUMO交通仿真器的组合，构建更加真实的仿真环境，通过IEEE802.11p协议栈支持车载通信技术，其框架结构如图4所示。TraNS是开源的车联网仿真平台，提供两种操作模式，第一种是以网络程序为中心的模式，主要用于不影响车辆节点的实时移动性的网络程序，如数据交换和音乐下载等；第二种模式是以应用程序为中心的模式，专门用于在交通仿真运行期间影响车辆行为的应用，如紧急警报和防撞应用。TraNS使用Java和 $C + +$ 开发，可以在Linux和Windows平台下工作。在以应用程序为中心的模式中，车辆移动轨迹不是在交通仿真器中预先生成的，而是在两个仿真器同时运行中动态生成的。同时利用TraCI（TraficControlInterface）实现了这种耦合仿真。为了控制车辆节点的移动，TraCI接口使用原子移动性命令，例如停止、改变车道、改变速度（增加/减少）等等。应用程序模块与驾驶员行为模型交互，并且在必要时调整实例化车辆的移动性属性。

![](images/605c2a1384c2709097e9537ebf7e53a0f262736f8873da7346f9b5c9cf54bc15.jpg)  
图4TraNS 框架结构示意图

2）Veins

Veins是一种用于车载移动环境下无线通信仿真的开源框架，其框架结构如图5所示。它支持并扩展了两个非常成熟的仿真器：基于事件的网络仿真器 $\mathrm { O M N e T + + }$ 和交通仿真器SUMO，为车联网仿真提供了一套全面的模型。Veins也使用了TraCI接口，两个仿真器通过TCP套接字连接，允许道路交通和网络交通的双向耦合模拟。车辆在SUMO中的移动被映射为OMNeT $^ { + + }$ 仿真中节点的移动。Veins的特征主要包括：可科学仿真多种车辆移动模式；支持 IEEE 802.11p 和IEEE 1609.4DSRC/WAVE网络层的详细模型，包括多信道操作、QoS信道接入噪声和干扰效应；支持用于蜂窝网络的模型，例如LTE;可以从OpenStreetMap导入整个场景，包括建筑物、速度限制、车道数、交通灯、访问和转弯限制；支持模拟由建筑物或车辆造成的阴影模型。

![](images/179a7196eb22dc334eb0906cf6cc3b6e0a0f5e05e730bba6437b0c81203f1877.jpg)  
图5Veins 框架结构示意图

# 3）iTETRIS

iTETRIS由欧洲FP7计划开发，是一个标准兼容的开源车联网仿真平台，符合ETSI标准，其框架结构如图6所示。iTETRIS集成并扩展了SUMO和NS3这两个被广泛引用的用于车辆移动性和无线通信仿真的开源平台，支持尾气排放、噪声以及ADAS模型，支持IEEE802.1lp、WiMAX等无线网络通信协议。iTETRIS架构是高度模块化的，通过开放的 API,它能集成各种网络仿真器与交通仿真器，并通过iCS模块管理两种仿真器的运行，其开源特性和模块化架构有助于平台未来的扩展。

![](images/40fd785a4565f0784c90ef6fc5d397f801498752c1ff5661cdc0479b4b7a4eec.jpg)  
图6iTETRIS 框架结构示意图

4）NCTUns

NCTUns是一个混合车联网仿真平台，主要由图形用户界面、仿真引擎（SimulationEngine）、车辆代理（CarAgent）和信号代理（SignalAgent）组成。它集成了车辆移动仿真模块和无线网络通信仿真模块，采用隧道网络接口（TunnelNetworkInterface，TNI）为两个模块提供了快速反馈回路。它支持多核处理器和并行编程。NCTUns支持无线网络通信的各种协议，包括IEEE802.11b/e无线局域网，IEEE802.16d/eWiMAX无线网络，用于异构无线网络的多接口移动节点以及IEEE802.11p/1609WAVE无线车载网络。

# 5）VSimRTI

VSimRTI是用于评估协同智能交通系统新解决方案的综合框架。可以对车辆运动、V2X通信、蜂窝网络等复杂的通信技术进行详细的建模。VSimRTI结合了不同的仿真器，与现有的固定仿真器耦合相比，VSimRTI仿真基础框架使仿真器易于集成和交互，根据仿真场景的具体要求，VSimRTI的高度灵活性使得最合适的仿真器可以耦合到车辆交通、排放、无线通信（蜂窝和ad-hoc）、驾驶员行为以及移动应用建模等方面。

根据影响车联网仿真结果的重要因素，对上述典型车联网仿真平台进行分析比较，如表1所示。

表1典型车联网仿真平台比较  

<html><body><table><tr><td>车联网仿真平台</td><td>TraNS</td><td>Veins</td><td>iTETRIS</td><td>NCTUns</td><td>VSimRTI</td></tr><tr><td>开源</td><td>是</td><td>是</td><td>是</td><td>是</td><td>是</td></tr><tr><td>真实地图</td><td>支持</td><td>支持</td><td>支持</td><td>支持</td><td>支持</td></tr><tr><td>遮蔽模型</td><td>不支持</td><td>支持</td><td>支持</td><td>支持</td><td>支持</td></tr><tr><td>排放模型</td><td>不支持</td><td>不支持</td><td>支持</td><td>不支持</td><td>支持</td></tr><tr><td>可靠的驾驶员模型</td><td>不支持</td><td>支持</td><td>不支持</td><td>不支持</td><td>支持</td></tr><tr><td rowspan="2">无线网络通信协议</td><td></td><td>LTE</td><td>WiMAX</td><td>WiMAX</td><td>LTE</td></tr><tr><td>IEEE 802.11p</td><td>DSRC/WAVE IEEE 802.11p</td><td>IEEE 802.11p</td><td>DSRC/WAVE IEEE 802.11p</td><td>IEEE 802.11p</td></tr><tr><td>用户界面</td><td>有</td><td>有</td><td>有</td><td>有</td><td>有</td></tr><tr><td>大规模仿真</td><td>不支持</td><td>支持</td><td>支持</td><td>支持</td><td>支持</td></tr></table></body></html>

# 3 影响车联网仿真测试结果的因素

# 3.1车辆移动模型

车联网环境下，因车辆的移动会对网络的拓扑结构产生显著影响，因此在实际仿真测试中，根据实际测试场景选择能够反映车辆移动特性的车辆移动模型至关重要。一般根据移动模型覆盖的范围及其功能特性，可以将其分为三类[40]：

a）随机运动模型。该模型将车辆描述为随机移动的节点，车辆的运动方向、运动速度等参数随机取样。该模型由于实现简单，经常被应用于MANETs的仿真。文献[41]对随机运动模型对旁路AODV车联网路由协议的性能进行了仿真测试，认为随机运动模型并不能真实反映车辆节点在我们真实道路上的移动模式。所以研究人员目前很少采用随机节点运动模型作为车联网环境下车辆移动的模拟

b）实际轨迹模型。与使用随机节点移动模型相比，基于预先记录的实际运动轨迹的节点运动模型是向实现真实车辆仿真迈出的重要一步。在基于事件的仿真中，每个车辆GPS位置更新，都被反映在仿真中，作为一个在其被记录时刻发生的单独事件。文献[42]利用西班牙马德里附近的三条高速公路上多个工作日不同时间段内的似稳态交通数据构建实际轨迹模型，仿真研究了实际交通轨迹对网络拓扑的影响。这种基于轨迹的运动模型在网络仿真中产生了最为真实的车辆运动过程，然而，因为可利用的轨迹很少，而且它们也并不能反映路上所有车辆的轨迹，因此在实际应用中受到了限制。

c）车流模型。该模型主要从微观、宏观、宏-微观三个方面考虑了真实道路环境下影响车辆移动的多方面因素，将车辆的移动性建模成车流。微观车流模型以单个车辆为基本单位，主要反映车与车之间的交互影响。宏观车流模型则是反映车辆移动的总体特征，通过借助流体动力学的理论，能够极大地减少计算量。宏-微车流模型同时考虑了宏观和微观特性。目前在车联网仿真中应用最广泛的是微观车流模型。文献[43]针对网联环境下的无人驾驶车辆形成的车流模型构建问题，研究建立了车联网环境下爱的车流模型，并在此基础研究车联网环境下可实现的高速公路拥堵控制问题。

# 3.2信道模型

在实际的道路网络中，无线网络信道质量会受到车辆相对速度、路边建筑物遮挡、多径效应等多种因素影响，因此针对车辆节点之间无线电传播的特性进行建模对于车联网仿真来说具有很重要的意义。常用的车联网信道模型有以下三种：

a）自由空间传播模型[44]。自由空间是指无任何衰减、无任何阻挡、无任何多径的传播空间，是理想传播条件。电波在自由空间传播时，其能量既不会被障碍物所吸收，也不会产生反射或散射，传播路径上没有障碍物阻挡，到达接收天线的地面反射信号场强也可以忽略不计。自由空间模型是在车联网仿真领域应用最广泛且最简单的信道传播模型，无线电波的损耗只与传播距离以及波长有关，通过引入一个附加的与环境相关的路径损耗指数来考虑非理想信道条件。但通过文献[45]的仿真分析表明，自由空间传播模型使用有助于简化车联网仿真测试的难度，但无法真实的描述真实车联网环境中的网络传播机制。

b）双射线地面反射模型。双射线地面反射模型是一种无线电传播模型，它可以预测发射天线与接收天线（通常两个天线各自具有不同的高度）在视距传播（line-of-sight propagation,LOSpropagation）时的路径损耗。双射线地面反射模型是一个更为实际的路径损耗处理方式，它考虑了无线信号存在的地面反射，接收信号具有两个分量：LOS分量以及主要由单个地面反射波形成的多径分量。文献[46]证明了在多车辆场景下能够观测到双射线地面反射模型，并使用该模型拟合射线追踪数据。

c）遮蔽模型。在实际道路网络中，建筑物或阻碍直接视线的障碍物等会引起车辆之间无线信号的衰减，在这种情况下提出了遮蔽模型，用于在网络仿真中再现这种影响。文献[47]提出将车辆视为三维障碍物并考虑它们对视距传播的接收信号功率和分组接收率的影响，并通过实验测量证明了该影响的重要性。构造遮蔽模型主要有两种方法，一种是通过构造随机模型尤其是使用对数正态分布的随机模型来实现，另一种则是通过构造具体的几何模型来实现。后一种方法需要对仿真场景有粗略的几何描述，现在成熟的仿真器已经能够提供定义几何形状的方法，也可以直接导入现实世界的地图。

# 3.3 驾驶员行为

在大多数情况下，仅考虑车辆移动模型及信道模型等因素还不足全面描述具体的车联网应用，因为“驾驶员的行为"也会影响到车联网的仿真测试结果。尽管这个因素是准确和真实评估车联网联应用性能的基础，但目前大部分车联网仿真平台只是简单的假设驾驶员的行为与所期望的或者由技术系统所建议的行为完全一样。随着车联网仿真研究的深入，考虑驾驶员行为已经被认为是一个非常重要的方面，至少在完全进入无人驾驶阶段之前，驾驶员行为会对驾驶决定产生很大的影响，比如驾驶员并不一定会采取系统提出的技术上的最优解。实际上，驾驶员的行为不仅在微观层面上影响一个系统（如理想的车辆跟驰模型的研究)，而且也会在宏观层面上产生影响（影响路线规划和路线变更)。

针对驾驶员的研究表明，驾驶员主要分为以下四类：

a）路线改变者，愿意根据交通信息而改变时间和行程路线的驾驶员；

b）出行前改变者，愿意在出发前改变路线的驾驶员；

c）行程中改变者，只有在进入可能拥堵的路段前才会愿意改变路线的驾驶员；

d）不改变者，完全不愿意改变路线的驾驶员。

针对驾驶员对技术系统提供的最优解反应行为的不同，可以将驾驶员行为分为以下几类：

a)始终遵循。这一类代表了所有完全按照预期而行动的驾驶员们，他们按照技术系统的建议而采取必要的行动，这通常是大部分车联网应用研究中的理想条件；

b）提前改变。这一类代表了所有认为提前改变（ $ { \mathrm { ~ d ~ } } >  { \mathrm { ~ D ~ } }$ ）是规避交通事件的最佳方案的驾驶员们，这里d表示与事件的距离，D表示定义的阈值距离。即距离超过阈值D的事件也被他们认为是与自己相关的。例如对于远处的障碍或拥堵，这类驾驶员总是认为在他们到达之前不会有显著的改善而选择提前绕道，这有助于防止在短时间通知的情况下由于所有驾驶员都试图绕道而造成的二次拥堵的发生。

c）不提前改变。这一类代表了所有认为在一个确定的距离内（ $\mathrm { ~ \ i ~ } \mathrm { ~ \boldsymbol ~ { ~ d ~ } ~ } < \mathrm { ~ D ~ }$ ）的交通事件才是与自己相关的驾驶员们，所有距离超过阈值D的事件都被他们认为是不相关的。例如对于远处的障碍或拥堵，这类驾驶员总是简单地假设在他们到达之前会有足够的时间处理完毕而不选择提前改变；

d)永不改变。属于这一类的所有驾驶员十分坚持自己的日常行为习惯，而完全忽略建议和意见，这一类驾驶员必须明确地作为一个指标并与经常用到的普及率区分开来，因为尽管这些驾驶员不遵守任何建议，但是他们的车肯定会参与到分布式车辆网联应用中。

# 4车联网仿真测试结果评价指标

# 4.1 网络仿真指标

在车联网仿真中，经常会采用不同的指标来评价网络的性能，经典的网络仿真指标有[48-50]：

a）网络容量（networkcapacity，NC）。网络容量是描述无线网络性能的最重要的指标之一，该指标使得人们在给定无线信道的基本容量限制的条件下，能够确定一些应用在理论上是否可行。网络容量通常指理论上可以传输多少数据，通常以Mbit/s为单位。

b）吞吐量（throughput，TH)，吞吐量是单位时间内从源到目标传输的数据量，可分为节点吞吐量和网络吞吐量，其中节点吞吐量为目标节点单位时间内接收到的数据包，网络吞吐量为单位时间内网络中所有节点接收到的数据包总和的平均值。

c）延迟（delay，DE)，延迟是数据包从源节点正确传输到目标节点所需要的时间，其平均值为平均延迟。在车联网环境下车辆跟驰速度快且跟驰间距小，这就要求车辆之间的通信延迟必须保持在极低的范围以内，因此这个指标对于安全关键型应用具有特别重要的意义。

d）路由代价（routingoverhead，RO）。RO为路由消息（协议包）占网络中总通信数据（协议包和数据包）的比值，该度量能反映路由协议对网络通信的影响。其计算公式为：

$$
{ \bf R O } = \frac { R s f } { R s f + P s f }
$$

式中： $R s f$ 为所有节点发送和转发的协议包； $P s f$ 为所有节点发送和转发的数据包。

e）归一化路由代价（normalized routingoverhead，NRO）。NRO为发送一个数据包（包括源发送和中间转发）到目标节点需要的路由包的数量，即发送和转发的协议包与数据包的比值，该度量反映了网络路由的稳定性。其计算公式为

$$
\mathrm { N R O } = \frac { R s f } { P s f }
$$

f）数据包投递率（packetdeliveryratio，PDR)，PDR为目标节点接收到的数据包与源节点应用层发送的数据包的比值关系，即正确传输数据包的统计度量，主要体现了车联网的两个主要特性：网络可靠性；网络拥塞/通信状况。其计算公式为

$$
\mathrm { P D R } { = } \frac { P r } { P s }
$$

其中： $P r$ 为目标节点接收到的数据包； $P s$ 为源节点应用层发送的数据包。

g）接收信号强度指示符（received signal strength indicator,RSSI)，是指接收到的无线电信号中包含的功率测量值，是无线发送层的可选部分，用来判定链接质量，以及是否应该增大广播发送强度。RSSI数越高，信号越强；当以负形式（如-100)表示RSSI值时，该值越接近0，接收信号越强。

h）可靠性，可靠性描述了数据传输是否以及在何种程度上有望取得成功。在许多情况下，对于可靠的通信协议的需求与低时延高吞吐量的需求存在固定的冲突，所以协议需要经过仔细地调整，以满足所有或大多数应用的需求。可靠性可以在仿真中通过评估失败次数来估计，然后建立一个可靠性指标。

# 4.2 应用相关指标

除了使用较为经典的网络相关指标以外，很多车联网应用和协议的性能和质量可以通过使用更多面向应用型的指标来进行评估。对于许多应用来说，信道是如何加载的或者延迟是否在确定值之间变化实际上与其并不相关（除非超出实时通信阈值)。下文将讨论依赖于具体应用的三个指标：

a）车辆碰撞概率。该指标定义了一个情况的严重程度，允许人们将消息按优先级排序甚至自动处理以防止碰撞，经常被作为安全性相关应用的描述性指标，揭示了相关应用处理突发状况（例如前车突然进行紧急制动）的能力[51]。重点在于对情况危急程度的精准分类、降低错误报警的概率以及通过研究为车联网提供完整的安全增强性系统。

b）旅行时间、有效平均速度和方差[52]。在研究车联网通行效率相关的应用中，经常会使用车辆的旅行时间、有效平均速度和方差作为主要的描述性指标，旅行时间和有效平均速度揭示了相关应用在车辆拥堵条件下重新规划车辆路线的能力；方差表示车辆旅行时间样本的离散程度，反映了车辆队列的串稳定性。

c）排放和燃料消耗[53]。在研究车联网环境友好型相关的应用中，经常会使用排放和燃料消耗作为车辆或车队行驶平顺性及车辆合作通行效率的主要描述指标。

# 5 结束语

车联网测试是开展智能网联汽车技术研发和应用不可或缺的重要环节，是车联网基础设施及装备进行大规模部署，并开展及其在智能汽车领域的广泛应用的重要手段。虽然在真实环境下进行车联网的研究与测试是最直接、最有效的方法，但受测试成本、场地、人员的规模的限制，目前在仿真环境下对车联网协议及基于车联网协议构建的各种车联网应用进行测试评估仍然是一种重要的车联网测试技术。本文系统地对当前国内外车联网仿真测试技术进行的总结，首先针对当前对车联网仿真测试评价的实际需求，在总结分析了目前国外主流的网络仿真器和交通仿真器的基础上，将现有车联网仿真平台分为了分离式、嵌入式、联合式、集成式四类；然后分析了目前典型的五种车联网仿真平台：TraNS、Veins、iTETRIS、NCTUns、VSimRTI，并对各平台从仿真规模等多个方面进行对比分析；其次针对车联网的应用特性，系统地归纳了影响车联网仿真测试性能的三个因素，包括车辆移动模型、信道模型及驾驶员行为；最后从网络仿真指标、车联网应用相关指标两个方面总结分析了车联网仿真测试结果典型评价指标。本文对于从事开展车联网技术及其应用的仿真测试评估的研究具有重要的指导意义。随着网联环境下合作式自动驾驶技术的不断发展，车联网技术将逐步从理论推向应用，但仿真依然是对车辆网联技术进行规模化测试评价的重要手段，可以预见的是大量网联车辆的示范应用将为车联网仿真测试提供更为全面的实际交通及网络数据支撑，从而促进车联网仿真测试结果的准确性；此外大量智能网联汽车封闭测试场地的构建，将促进车联网实车测试的规模，进而作为仿真测试的重要印证手段促进仿真测试平台的测试准确度及效率。下一步应着重从影响车联网仿真测试性能的因素着手，以真实交通数据为基础，研究目前提出的各种车辆移动模型及信道模型的优缺点及适用性。

参考文献：   
[1]程刚，郭达．车联网现状与发展研究[J].移动通信，2011，35(17): 23-26.(Cheng Gang，Guo Da.Research on the current situation and development of IoVs [J]. Mobile Communication,2011,35 (17): 23-26.)   
[2]肖玲，李仁发，罗娟．车载自组网的仿真研究综述[J].系统仿真学报， 2009,21 (17): $5 3 3 0  – 5 3 3 5 { + } 5 3 5 6$ (Xiao Ling，Li Renfa,Luo Juan. Simulation of vehicular ad hoc networks: a survey[J]. Journal of System Simulation,2009,21(17): 5330-5335+5356.)   
[3]霍梅梅，郑增威，周晓伟．车辆自组织网仿真研究[J].计算机应用研 究,2010,27(5):1614-1620.(Huo Meimei, Zheng Zengwei, Zhou Xiaowei. Research overview of simulation of vehicular Ad hoc networks [J]. Application Research of Computers,2010,27(05):1614-1620)   
[4] Akhtar N, Ergen S C, Ozkasap O. Vehicle mobility and communication channel models for realistic and eficient highway VANET simulation [J] IEEE Trans on Vehicular Technology,2015,64(1): 248-262.   
[5]顾海燕．车联网环境下高速公路车辆跟驰模型及仿真研究[D]．南京： 东南大学,2017. (Gu Haiyan. Research on freewaycar-following modeling and simulation in connected vehicle environment [D]. Nanjing: Southeast University,2017.)   
[6] 刘占文，王润民，赵祥模．基于车联网的交叉口行车事故预警方案及仿 真[J].计算机仿真,2016,33(6):132-137.(Liu Zhanwen,Wang Runmin, Zhao Xiangmo. Simulation of intersection accident warning scheme based on Internet of vehicles [J].Computer Simulation,2016,33 (06): 132-137.)   
[7]Martinez FJ,Toh CK,Cano JC,et al.A survey and comparative study of simulatorsforvehicularad hocnetworks(VANETs）[J].Wireless Communications & Mobile Computing,2011,11(7): 813-828.   
[8]Issariyakul T, Hossain E. Introduction to network simulator NS2 [M]. New York: Springer, 2009.   
[9]RileyGF,Henderson TR.The ns-3 network simulator[M]//Modeling and Tools for Network Simulation. Berlin: Springer,2010:15-34.   
[10] Weber M. Simulation of Ad Hoc Networks: ns-2 compared to JiST//SWANS[J]. Journal of Hospital Infection,2007,66 (4):395-6.   
[11] VargaA.OMNeT $^ +$ [M]// Modeling and Tools for Network Simulation. Berlin: Springer,2010:35-59.   
[12] Raju S R, Runkana K, Mungara J. Performance measurement and analysis of ZRP for MANETs using network simulator-QualNet [C]//Proc of IEEE International Conference on Wireless Information Technology and Systems. New York: IEEE,2010:1-4.   
[13] Chang Xinjie. Network simulations with OPNET[C]// Proc of the Winter Simulation Conference.New York: IEEE,1999: 307-314.   
[14] Riley GF Large-scale network simulations with GTNetS [C]/ Procof the Winter Simulation Conference.New York: IEEE,2003: 676-684.   
[15]BehrischM,KrajzewiczD,WeberM.Simulationof Urban Mobility [M]. Berlin: Springer, 2014.   
[16]Fellendorf M,Vortisch P.Microscopic traffic flow simulator VISSIM[M]// Fundamentals of Traffic Simulation. New York: Springer,2O10: 63-93.   
[17] SykesP.Traffic simulation with paramics[M]//Fundamentalsof Traffic Simulation. New York: Springer,2010:131-171.   
[18]Lu Lu,Yun Tianlong,Li Li,et al.A comparison of phase transitions produced by PARAMICS,TransModeler,and VISSIM[J]. IEEE Intelligent Transportation Systems Magazine,2010,2(3):19-24.   
[19] Mcmichael D L, Orleans B S.TRANSIM: a general purpose problem solving tool[J].Naval Engineers Journal,2010,85(5):79-92.   
[20] Owen LE, Zhang Yunlong,Rao Lei,et al. Trafc flow simulation using CORSIM[Cl// Proc of the Winter Simulation Conference.New York: IEEE,2000: 1143-1147.   
[21]AlbaE,LunaS，Toutouh J.AccuracyandEfficencyinSimulating VANETs [M]// Modelling,Computation and Optimization in Information Systems and Management Sciences.Berlin: Springer,2008: 568-578.   
[22] Wu Hao,LeeJ,Hunter M,etal.Efficiencyof simulatedvehicle-to-vehicle message propagation in atlanta,georgia,i-75 corridor [J]. Journal of the Transportation Research Board,2005,1910(1): 82-89.   
[23]RehunathanDB,SeetBC,LuongTT.Federating of MITSIMLab and ns-2 forrealistic vehicular network simulation [C]/ Proc of the 4th International Conferenceon Mobile Technology，Applications，and Systems& the 1st International Symposium on Computer Human InteractioninMobile Technology.New York: ACMPress,2007: 62-67.   
[24] ChoffnesDR.An integrated mobilityand trafic model for vehicular wireless networks [C]//Proc of the 2nd ACM International Workshop on Vehicular Ad hoc Networks.New York:ACMPress,2005: 69-78.   
[25] IbrahimK,WeigleMC.ASH:Application-aware SWANSwith highway mobility [C]// Proc of INFOCOM. New York: IEEE,2008: 1-6.   
[26] Arbabi H,Weigle MC. Highway mobilityand vehicular Ad hoc networks inns-3[C]// Procof Simulation Conference.New York:IEEE,2010: 2991-3003.   
[27]周斌．基于车联网仿真平台的城市交通信号控制[D].杭州：浙江大学, 2016.(Zhou Bin. Urban traffic signal control based on connected vehicles simulationplatform [D]. Hangzhou: Zhejiang University,2016.)   
[28] BononiL,Di Felice M,D'Angelo G,etal.MoVES:a framework for parallel and distributed simulation of wireless vehicular ad hoc networks [J]. Computer Networks,2008,52(1): 155-179.   
[29] Schroth C,Dotzer F,Kosch T,et al.Simulating the traffic effects of vehicle-to-vehicle messaging systems[C]//Procof the 5th International Conference on ITS Telecommunications. 2005: 63-68.   
[30]Pi6rkowski M,RayaM,LugoAL,etal. TraNS:realistic joint trafficand network simulator for VANETs [J]. ACM SIGMOBILE Mobile Computing & Communications Review,2008,12 (1): 31-33.   
[31] Eckhof D,Protsenko M,German R.Toward an open source location privacy evaluation framework for vehicular networks [C]//Proc of the 80th IEEE Vehicular Technology Conference.2014:1-2.   
[32] Konishi K,Maeda K,Sato K,et al.MobiREAL simulator-evaluating MANET applications in real environments [C]// Proc of the 13th IEEE International Symposium on Modeling，Analysis，and Simulation of Computer and Telecommunication Systems.New York:IEEE，2005: 499-502.   
[33]Rondinone M,Maneros J,Krajzewicz D,et al.iTETRIS:a modular simulation platform for the large scale evaluation of cooperative ITS applications [J]. Simulation Modelling Practice & Theory,2O13,34(5): 99-125.   
[34]徐小维．基于VISSIM与OMNeT+的车联网仿真平台及其应用研究 [D].武汉：华中科技大学,2014.(Xu Xiaowei.A simulation platform for connected vehicle systems based on Vissim and Omnet+and preliminary studies [D]. Wuhan: Huazhong University of Science and Technology, 2014.)   
[35] Wang SY,Lin CC.NCTUns 6.O:a simulator for advanced wireless vehicular network research [C]//Proc of Vehicular Technology Conference. New York: IEEE,2010: 1-2.   
[36] Gorgorin C,Gradinescu V,Diaconescu R,et al.An integrated vehicular and network simulator for vehicular ad-hoc networks [C]//Proc of the 20th European Simulation and Modelling Conference.2oo6: 31-38.   
[37] MangharamR,WelerD,Rajkumar R,et al. GrooveNet: a hybrid simulator for vehicle-to-vehicle networks [C]//Proc of the 3rd Annual International Conference on Mobile and Ubiquitous Systems.New York:IEEE,2006: 6-8.   
[38] Vuyyuru R,Oguchi K,Collier C,et al.Automesh: flexible simulation framework for vehicular communication [C]// Proc of the 3rd Annual International Conference on Mobile and Ubiquitous Systems.New York: IEEE,2006: 1-6.   
[39] Schyunemann B. V2X simulation runtime infrastructure VSimRTI: an assessment tool to design smart trafic management systems [J]. Computer Networks,2011,55 (14): 3189-3198.   
[40]魏达，王沿锡，王健，等．车载自组网移动模型综述[J].计算机学报, 2013,36 (4): 677-700.(Wei da,Wang Yanxi,Wang Jian,et al.Asurvey on mobility models of vehicular ad hoc networks [J].Chinese Journal of Computers,2013,36 (4): 677-700.)   
[41] Ahed A, Uthman B.A simulation study: the impact of random and realistic mobility models on the performance of bypass-AODV in ad hoc wireless networks[J].EURASIP Journal on Wireless Communicationsand Networking,2010,2010 (1): 1-10.   
[42] Gramaglia M,Trullols-CrucesO,Naboulsi D，et al.Mobility and connectivity in highway vehicular networks:a case study in Madrid [J].   
Computer Communications,2016,78(C):28-44.   
[43]房雅灵．车联网环境下道路交通流建模与控制[D].西安：西北工业大 学,2016.(Fang Yanling.Road traffic flow modeling and control in internet of vehivles [D].Xi’an: Northwestern Polytechnical University,2016.)   
[44]刘花璐，刘霞．一种无遮挡场景下的无线信道模型的建立[J].湖北理 工学院学报,2015,31(01): 30-34.(Liu Hualu,Liu Xia.Establishment of wireless channel model for unblocked scene [J]. Journal of Hubei Polytechnic University,2015,31(01):30-34.)   
[45] Angeles W,Borin V P,Munaretto A,et al. The impact of propagation models in the performance of ad hoc routing protocols for urban VANET [C]//Proc of the 84th IEEE Vehicular Technology Conference.New York: IEEE,2017: 1-5.   
[46] Zochmann E,Guan Ke，Rupp M. Two-ray models in mmWave communications [C]// Proc of International Workshop on Signal Processing Advances in Wireless Communications. New York: IEEE,2017: 1-5.   
[47]Boban M,Vinhoza TTV,FerreiraM,et al.Impact of vehicles as obstacles in vehicular ad hoc networks [J]. IEEE Journal on Selected Areas in Communications,2011,29 (1):15-28.   
[48] Sommer C, Dressler F. Vehicular networking [M]. Cambridge: Cambridge University Press, 2015.   
[49]胡锦超，赵祥模，王润民，等．车联网环境下 IEEE802.11p移动性支持 仿真研究[J].计算机工程,2017,43(05):23-27,34.(HuJinchao,Zhao Xiangmo,Wang Runmin,et al. Simulation research on mobility support of IEEE 802.1lp in intermet of vehicles [J]. Computer Engineering,2017,43 (05): 23-27, 34. )   
[50] Silva C,Nogueira M, Kim D,et al. Cognitive radio based connectivity management for resilient end-to-end communications in VANETs [J]. Computer Communications,2016,79 (C): 1-8.   
[51] Joerer S,Segata M, Bloessl B,et al. A vehicular networking perspective on estimating vehicle collision probability at intersections [J].IEEE Trans on Vehicular Technology,2014,63 (4):1802-1812.   
[52] Dressler F,Sommer C,Eckhoff D,et al.Toward realistic simulation of intervehiclecommunication [J]. IEEE Vehicular Technology Magazine, 2011,6 (3): 43-51.   
[53] Talavera E,Diaz-Alvarez A, Jimenez F,et al. Impact on congestion and fuel consumption of a cooperative adaptive cruise control system with lane-level position estimation [J]. Energies,2018,11 (1): 194.