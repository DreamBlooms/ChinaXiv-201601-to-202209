# 时间敏感网络研究进展

曹志鹏，刘勤让，刘冬培，燕昺昊(战略支援部队信息工程大学，郑州 450003)

摘要：随着传输技术的发展以及应用场景的增加，时间敏感网络已被各界所广泛关注。首先介绍了时间敏感网络的发展历程、技术内容；然后介绍了时间敏感网络标准协议中的部分重要机制，并重点回顾了近年来国内外关于时间敏感网络的研究状况，分析了不同场景下应用特点；最后指出了时间敏感网络未来可能的发展方向。  
关键词：时间敏感网络；确定性网络；以太网；服务质量  
中图分类号：TP393.11doi:10.19734/j.issn.1001-3695.2020.02.0026

Survey of time-sensitive networking

Cao Zhipeng,Liu Qinrang, Liu Dongpei, Yan Binghao (PLA Strategic SupportForce Information Engineering University,Zhengzhou Henan 45ooo3,China)

Abstract:With the development of transmision technologyand the increaseof application scenarios,Time-Sensitive Networking hasbeen widelyconcered.Firstly,ititroducedthedevelopment historyandtechnicalcontentofTime-Sensitive Networking.Then it introduced some important mechanisms in standard protocols of Time-Sensitive Networking,and reviewedtheresearch statusofTime-SensitiveNetworkingathomeandabroad inrecentyears,alsoanalyzedtheapplication characteristics indiferentscenarios.Finally,itpointedoutthepossible future directionofTime-SensitiveNetworking.

Key words: time-sensitive networking; deterministic networking; ethernet; quality of service

随着时代的不断发展，新的信息技术层出不穷，例如5G、物联网、无人驾驶、新一代音视频传输、工业控制等。在这些应用场景中，某些数据流量需要进行确定性的传输，这对传统传输技术提出了巨大挑战[I。传统的数据传输技术有着设备复杂、协议众多、技术保密等问题，不同厂家和方案解决商之间的兼容性较差，这使得广泛部署与升级传输设备变得困难。为了满足各种应用场景对于数据传输的低时延、低抖动、不拥塞、不丢包、高鲁棒性等需求，时间敏感网络(time-sensitive networking,TSN)应运而生[2]。

如何高效准确地处理数据的确定性传输，一直是网络技术发展所关注的一个重要问题。时间敏感网络作为解决数据确定性传输的新方法，已经获得了学术界和工业界的广泛关注。时间敏感网络的核心是由IEEE提出的一系列针对802.1桥接网络的附加协议，支持尽力而为流量和时间敏感流量在同一物理介质上实现混合传输，即融合网络传输。在IEEE时间敏感网络的协议标准中，规定了时间同步、传输调度、路径控制、资源预留、可靠性等机制的基本框架。

时间敏感网络主要工作在数据链路层，其优势在于确立了融合网络中数据确定性传输的通用标准，使得新技术的发展具有了明确的方向，有利于提升各种基于以太网技术解决方案的兼容性。目前TSN 的产品正在逐步面世，例如支持TSN 标准协议的实验床、交换芯片等。本文主要介绍了时间敏感网络的相关工作，对其发展背景、重要机制、研究热点、应用现状等进行了总结归纳，并且分析论述了其未来的发展趋势。

# 1 时间敏感网络概述

# 1.1时间敏感网络的发展背景

现如今，人们对于确定性、低时延、高鲁棒性的数据传输需求越来越大，尤其在控制系统、工业互联网、5G前传、汽车内网等场景中，有些关键流量的传输对于时效性非常敏感，需要及时而又准确的送达。例如在工业控制领域，工业控制网络相较于传统互联网而言失效后果严重，稳定性和确定性要求高，常常传输长度相对较短的数据包，数据往返时间介于 $2 5 0 \mathrm { u s } { \sim } 1 0 \mathrm { m s } ^ { [ 3 ] }$ 。在5G 传输领域，也提出URLLC(ultra-reliable andlow latency)的使用场景。URLLC对稳定性、延迟和可靠性要求极高。例如，数据在用户平面内的延迟不高于1ms，在控制平面内的延迟不高于 $2 0 \mathrm { m s }$ ，并且要求在1ms 内传输32位的协议单元数据的成功率不低于 $9 9 . 9 9 9 \% ^ { [ 4 ] }$ 。

为了解决这类数据的传输问题，学术界和产业界提出了众多的解决方案，经历了从现场总线到工业以太网，再从工业以太网到实时工业以太网的发展。此外，开放互连、开源化、集成化、标准化、可软件定义化是当前技术发展的大趋势。通过相关组织机构制定标准，可以让更多的人参与技术讨论，有利于技术的快速发展，并且打破不同解决方案之间的技术壁垒。

# 1.2传统技术面临的挑战

关于数据的确定性传输解决方案，目前应用较广的有汽车领域的FlexRay[5]，航空电子领域的 $\mathrm { A R I N C 6 6 4 p 7 ^ { [ 6 ] } }$ ，和工业控制领域的PROFINET[7]、EtherCAT[8]和Powerlink[9]等，它们都是基于以太网的实时控制传输系统。

但是随着时代的发展，众多的新技术例如自动驾驶、工业自动化、ADAS(advanced driver assistance system)系统等不断出现，它们对于带宽和时延的要求非常高。例如在自动驾驶的设备中存在着众多的传感器，导致大量的数据需要在极短的时间内进行传输，系统的传输速率越高越好。一般而言，对于处理图像计算需要至少100Mbps 的传输速率，而CAN的传输速率不超过1Mbps，FlexRay的传输速率不超过10Mbps[10]，难以满足使用要求。

此外，跳出具体的技术细节，它们还存在以下共性的问题：首先，虽然它们都是基于现场总线或以太网的技术，但是各种解决方案从软件到硬件各个层次都不尽相同，并且部分技术是受保护的私有技术；其次，随着工业控制领域的不断发展，各种传感器、处理器、存储器、执行构件等设备需要相互兼容，实现彼此之间的通信并协同工作；最后，IT(information technology)技术和 OT(operational technology)技术的融合是未来的发展趋势，人们希望打通制造执行系统(在工业现场中)与运营管理系统(在办公室中)之间的数据链路，并将二者整合在一个统一的信息平台上，从而在生产管理、运营决策与制造执行等各方面实现协同，全面提升工作效率。

# 1.3新的解决方法一一时间敏感网络

为了解决上述问题，时间敏感网络应运而生。2006年，IEEE 802.1工作组成立了音视频桥接(audio video bridging,AVB)工作组，主要致力于解决音视频传输领域中的时间同步、低延迟和带宽预留等问题。AVB要求数据传输的延迟在7跳内不超过 $2 \mathrm { m s } ^ { [ 1 1 ] } \mathrm { . }$ ，音视频桥接技术的相关研究为TSN的发展提供了基础支持。事实上，TSN技术的前身就是AVB技术。然而由于其技术内涵有限，应用场景相对单一，AVB难以满足不同场景下的数据传输需求。

IEEE在AVB的基础上进行改进，将目光拓展至多种工业控制系统上，于2012年成立了TSN工作组。TSN是IEEE802.1标准的补充和增强，力图规定通用的确定性传输机制。表1列出了已经正式发布的TSN相关标准。TSN的应用场景是有限带宽的多节点复杂大型网络，并且网络中能够同时产生和传输多种不同QoS要求的流量。例如在IEC/IEEE60802的TSN工业自动化配置文件中规定，对于同步流量，最大包长为100字节，端到端延迟不超过2ms；对于循环流量，最大包长为1000字节，延迟在2到 $2 0 \mathrm { m s } ^ { [ 1 2 ] }$ 。最新的标准IEEE Std802.1Qcp-2018[13]由IEEE 在2018 年发布，主要增加了对于杨氏数据模型的支持。时间敏感网络的标准化工作仍在继续进行之中，表2列出了正在修订中的标准。

表1时间敏感网络相关标准  
Tab.1The related standards ofTSN   
表2进行中的时间敏感网络项目  

<html><body><table><tr><td>分类</td><td>名称</td><td>主要功能</td></tr><tr><td rowspan="7">补充或增强</td><td>IEEE Std 802.1Qav-2009[14]</td><td>时间敏感流量：</td></tr><tr><td>IEEE Std 802.1Qat-2010[15]</td><td>增强转发和队列功能 流预留协议</td></tr><tr><td>IEEE Std 802.1Qca-2015[16]</td><td>路径控制和预留</td></tr><tr><td>对 802.1Q 标准的 IEEE Std 802.1Qbv-2015[17]</td><td>增强调度流量</td></tr><tr><td>IEEE Std 802.1Qbu-2016[18]</td><td>帧抢占</td></tr><tr><td>IEEE Std 802.1Qch-2017[19]</td><td>循环队列和转发</td></tr><tr><td>IEEE Std 802.1Qci-2017[20]</td><td>按流进行滤波和监管</td></tr><tr><td rowspan="5">独立标准</td><td>IEEE Std 802.1Qcc-2018[21]</td><td>流预留协议增强</td></tr><tr><td>IEEE Std 802.1Qcp-2018[13]</td><td>杨式数据模型</td></tr><tr><td>IEEE Std 802.1BA-2011[22]</td><td>AVB系统</td></tr><tr><td>IEEE Std 802.1AS-2011[23]</td><td>时间同步</td></tr><tr><td>IEEE Std 802.1CB-2017[24]</td><td>帧的复制和消除 TSN应用在前传</td></tr></table></body></html>

# 2 时间敏感网络中的关键技术机制分析

TSN分别从时间同步、传输调度、路径控制、资源预留、可靠性等角度对传统以太网传输机制进行了增强，以保障时间敏感流的确定性传输和混合传输。

# 2.1 时间同步机制

在时间敏感网络中，用于时间同步的标准是802.1AS[23],其应用的前提是节点之间的传输延迟固定且对称，主要实现各个网络节点之间的时间同步，并且能够在增加、减少网络组件，或网络重新配置等场景下，完成节点之间同步状态信息的维护。

Tab.2On-going projects of TSN   

<html><body><table><tr><td>分类</td><td>名称</td><td>主要功能</td></tr><tr><td></td><td>P802.1Qcj</td><td>自动添加到提供商</td></tr><tr><td></td><td></td><td>骨干网桥接(PBB)服务</td></tr><tr><td></td><td>P802.1Qcr</td><td>异步流量整形</td></tr><tr><td>对802.1Q标准的补</td><td>P802.1Qcw</td><td>对于预定流量、帧抢占、按流</td></tr><tr><td>充或增强</td><td></td><td>进行滤波和监管的杨氏数据模型</td></tr><tr><td></td><td>P802.1Qcx</td><td>对连接错误管理的杨氏数据模型</td></tr><tr><td></td><td>P802.1Qcz</td><td>拥塞分离</td></tr><tr><td></td><td>P802.1Qdd</td><td>资源分配协议</td></tr><tr><td>对于802.1AB标准</td><td>P802.1Qdj</td><td>配置提升</td></tr><tr><td></td><td>P802.1ABcu</td><td>LLDP 的杨氏数据模型</td></tr><tr><td>的补充或增强</td><td>P802.1ABdh</td><td>对复帧协议数据单元的支持</td></tr><tr><td>对于802.1CB标准</td><td>P802.1CBcv</td><td>按流进行滤波和监管的杨氏数据模型与</td></tr><tr><td>的补充或增强</td><td></td><td>管理信息库</td></tr><tr><td></td><td>P802.1CBdb</td><td>按流进行滤波和</td></tr><tr><td>对于802.1CM标准</td><td>P802.1CMde</td><td>监管拓展流认证功能</td></tr><tr><td>的补充或增强</td><td></td><td>对前传配置文件的增强</td></tr><tr><td rowspan="7">独立标准</td><td>IEC/IEEE60802</td><td></td></tr><tr><td></td><td>TSN 对于工业自动化的配置文件</td></tr><tr><td>P802.1CS P802.1CQ</td><td>链路本地注册协议</td></tr><tr><td>P802.1DC</td><td>多播及本地地址分配</td></tr><tr><td>P802.1DF</td><td>网络系统的QoS提供</td></tr><tr><td></td><td>TSN 对于服务提供商的配置文件</td></tr><tr><td>P802.1DG</td><td>TSN 对于车载以太网通信的配置文件</td></tr><tr><td></td><td>P802.1AS-Rev</td><td>时间同步</td></tr><tr><td>标准修订</td><td>P802.1AX-Rev</td><td>链路聚合修订</td></tr></table></body></html>

802.1AS是IEEE1588协议[26在数据链路层的进一步发展和运用，其中的时钟同步域称为gPTP(generalized precisiontimeprotocol)域，域中的设备都是时间敏感的设备，包括桥(bridge)和端站(endstation)，并且能够支持多种异构网络。

在gPTP域中，任何包含时钟源的设备都可通过BMCA(bestmasterclockalgorithm)算法被选为超主(grandmaster，GM)。经过选举出的超主将时间同步所用到的相关信息向其他节点发送，其余节点则利用这些信息来调整自己的时间，以实现时间同步。802.1AS时间同步机制主要包括路径延迟测量、BMCA算法和同步时间调整三个部分。

# 2.1.1路径延迟测量原理

路径延迟测量的目的是测量相邻两个节点之间的延迟。在传输延迟的测量中，一方是发起者，另一方是响应者。如图1所示，两者通过PdelayReq、PdelayResp、PdelayRespFollowUp和时间戳等各种信息的互相传递来实现测量，传输时延可以通过式(1)进行计算。

$$
d = \frac { ( t _ { 4 } - t _ { 1 } ) - ( t _ { 3 } - t _ { 2 } ) } { 2 }
$$

# 2.1.2BMCA算法

BMCA算法是用于确定gPTP域中超主的算法。用于同步的时钟信息通过生成树结构传向每一个系统中的节点。最佳主时钟的选举是通过Announce 报文在系统中的传递实现的。对于Announce 报文而言，其中包含了各个节点的状态信息。系统在刚开始时，各节点及其端口的角色是不确定的，算法能够在有限的步骤内实现最佳主时钟的选取，并确定各个节点端口的状态[27]。

BMCA算法由众多状态机组成，它们之间相互协调配合，通过内部各种向量的传递来实现最佳主时钟的选择和端口角色的确认，如图2所示。

![](images/eafa853b5c3626421b30ef39fbf23a545077b6b759d251c05f2a43f04f04f5f0.jpg)  
图1路径延迟测量原理

![](images/6902d6e2b1e4194238fab27e2a910a08eb9bdedcae5934dfba0643c32701ca28.jpg)  
Fig.1Principle of path delay measurement

2.1.3时钟同步信息的传递

在gPTP域中，所有的设备都需要和主时钟进行同步。因此，各时钟需要发送出自身的同步信息，并根据其他时钟的信息来修改自身的参数。例如，假设有三个节点A、B和C，时间同步信息需要从A经由B传递到C，如图3所示，系统将会通过Sync 报文和FollowUp报文的传递，去不断更新其中时间修正域correctionField和频率比rateRatio[28]。

![](images/9e553bb069dd588ff4e1747c96e8c8ea996a317eb0dd369689b456bb99bee789.jpg)  
Fig.2State machines of BMCA algorithm   
图3同步信息传递原理  
Fig.3Principle of synchronous information transfer

其中，preciseOriginTimestamp 是主时钟在发起同步信息时的时间，在信息的传递过程中保持不变。rateRatio用于修正不同时钟频率的差异，其计算方法为(2)式

$$
r a t e R a t i o _ { B } = r a t e R a t i o _ { A } \times R a t i o _ { B A }
$$

correctionField用于实现在传输过程中对于传输时延和

节点处理时延的修正，距离主时钟越远的节点其修正值越大，反之越小，其计算方法为(3)式。这样，随着信息逐渐传递遍整个同步时间生成树，每个节点都与主时钟实现了同步。

$$
c o r r e c t i o n F i e l d _ { \scriptscriptstyle A } + L i n k D e l a y + ( t _ { s , B } - t _ { r , B } ) \times r a t e R a t i o _ { \scriptscriptstyle B }
$$

# 2.2传输调度机制

传输调度机制是时间敏感网络的核心技术之一，通过这些机制能够实现网络的融合传输，并且保障性能要求。其中较为重要的是CBS(credit based shaper)机制、TAS(timeawareshaper)机制和帧抢占机制。

# 2.2.1CBS机制

802.1Qav[14]为时间敏感、丢包敏感的实时音视频应用提供了性能保证。该标准规定了优先级的重新生成算法和受控带宽的队列枯竭算法，最主要的是定义了流量整形的CBS机制，用于解决高优先级流量的长时间占用带宽，而干扰到其他流传输的情况。CBS算法是针对特定队列而言的，给出了依据"信用值"来进行队列输出流量整形的方法。对于任意一个采用CBS机制的队列而言，只有其自身的credit值大于或等于0时，队列中的数据才可以进行输出，否则就不输出。

当数据传输时(即在credit值大于等于0时)，该队列的credit 值以 sendSlope 的速率减少；当数据不传输时(即在credit值小于0时，或者有优先级更高的队列正在传输时)，该队列的credit值以idleSlope 的速率增加。若credit为正值，且此时没有数据传输，则将 credit 立刻置零。sendSlope 和idleSlope的单位是比特/秒，对于credit值而言，其值是有限的，范围在hiCredit和loCredit之间。其中hiCredit表示credit能够增加到的最大值，loCredit表示credit能够减小到的最小值，如图4所示。

![](images/0f0a83d9769dd1dada82262aa28c54a642c039e93e3b245400594e4ef93158cb.jpg)  
图2BMCA 算法状态机  
图4 CBS机制示例  
Fig.4An example of CBS mechanism

2.2.2 TAS机制

在802.1Qbv[17]标准中，TSN 给出了一种类似于时分复用的融合传输解决方案，称为时间感知整形器TAS。TAS运行的基础是802.1AS中的时间同步。根据协议规定，最多可以有8个用于传输的不同优先级队列，每个队列的传输调度是独立运行的。802.1Qbv 增加了一种特殊的门控机制，每个队列都和一个传输门对应。传输门的状态决定队列是否能够传输数据帧，当传输门打开时数据能够传输，当传输门关闭时数据不能够传输。将所有的传输门组合在一起就形成了门控列表(gatecontrollist，GCL)，如图5所示(用状态0表示关闭，用状态1表示打开)。

设备的每个输出端口都有自己的门控列表，用于控制该端口中的输出队列。传输门具有最终的传输决定权，即使有数据帧被某些传输选择算法选定，且具有足够的传输时间，但是只要传输门为关闭状态，它就不能传输。为了防止在传输时数据间相互干扰，在状态切换的中间有“保护带”，即在一段时间范围内，除了已经开始传输的队列外，其余队列均不允许传输。只有在端口空闲的情况下，时间敏感数据才会传输，其传输质量能够得到保障。TAS机制是TSN最为核心的功能之一，实现了不同流量的混合传输与时间敏感流量的确定性传输。

![](images/1726709aee6fc3338d99a96dc4f922e3a6e819282ca7254c5f29eab0a23b3d58.jpg)  
图5时间感知整形器Fig.5Time-aware shaper

# 2.2.3帧抢占机制

802.1Qbu[18]和 $8 0 2 . 3 \mathrm { b r } ^ { [ 2 9 ] }$ 中规定了传输中的帧抢占机制。帧抢占主要用于网络中紧急帧的传输，并且只有在收端和发端设备都支持的情况下才能够使用。系统将会使用LLDP协议(linklayerdiscoveryprotocol)和Ethertype 值去判定当前链路是否支持帧抢占。

帧抢占机制允许用户用更高优先级的数据去一次或多次打断低优先级数据的传输，在高优先级数据传输完毕后，低优先级数据再恢复传输。帧抢占中的关键点在于抢占当前帧和防止被抢占的帧继续传输[30]。在802.3br协议中，规定了帧抢占发生在MAC聚合子层中，并将MAC层分成了eMAC(expressMAC)和 pMAC(preemptable MAC)。eMAC用于负责时间敏感流量的传输；pMAC用于负责普通流量的传输，且eMAC的优先级大于pMAC。

在可抢占帧在传输时，如果没有抢占发生，则直接通过pMAC传输；若发生抢占，把待传输的数据放在MAC聚合子层中进行缓存。如果发生了多次抢占，对于每个帧的分段，都有FCS(frame check sequence)校验。每个可抢占帧的帧结构[3如图6所示。帧抢占可以单独应用，也可以和其他机制一起配合使用，例如帧抢占常常和CBS与TAS机制联合使用。

首帧 前导码 首帧检测 目的MAC 源MAC 以太网类型 数据 FCS校验  
字节数 (7) (1) (6) (6) (2) (4)  
中间帧 前导码 后续帧检测 帧序号 数据 FCS校验  
字节数 (7) (1) (1) (4)  
尾帧 前导码 尾帧检测 帧序号 数据 FCS校验  
字节数 (7) (1) (1) (4)

# 2.3 路径控制机制

OSPF(open shortest path first)是为了TCP/IP设计的路由协议，类似的，IS-IS(intermediate system-to-intermediate system)协议是一种为OSI结构(非TCP/IP)设计的路由协议。IS-IS常用在大规模网络中(例如运营商和银行)，并且基于数据链路层进行报文传输。相较于OSPF协议，IS-IS协议更加简单和稳定，这就使得在巨大数据信息的条件下其处理效率比OSPF高[32]。

传统的IS-IS协议在传输时采用的是最短路径传输，而802.1Qca[16]允许建立显式树，可以把流量准确地安排到预定的传输路径上，用于增加网络的弹性和减少拥塞。相较于最短路径桥接 SPB(shortest path bridging)协议，802.1Qca 有更多的功能。新的功能针对传输中的数据流，提供了明确路径控制、带宽预留和冗余性改进。协议详细说明了对于单播帧和多播帧在显式路径上进行桥接的方法，也明确了用于确定多动态拓扑的协议。

协议提供了显式的路径控制，能够使用非最短路径。同时也集成了在转发路径上的用于带宽预留、流预留的工具。802.1Qca提供了冗余控制机制，支持用IS-IS协议携带控制信息去实现同步和调度功能。它是从RSTP(rapid spanning treeprotocol)、MSTP(multiple spanning tree protocol)、SPB 等生成树协议发展而来的，能够提供多动态拓扑，并且明确了数据转发的显式路径。协议自带有最短路径 SP(shortest path)，相同代价树 ECT(equal cost tree)，内部生成树 IST(internalspanning tree)，多生成树实例 MSTI(multiple spanning treeinstance)和显式树ET(explicit tree)等机制。

# 2.4 资源预留机制

流预留协议(stream reservation protocol，SRP)802.1Qat[15]基于资源的预留要求和可用网络资源，规定了用于接纳或拒绝流的准入控制框架，并且还规定了全双工以太网链路在分组交换网中保留网络资源和广播流的框架。流预留协议在通信链路上通过保留传输资源来满足实时传输的要求。协议根据不同种类的流来确定其所需要的带宽。对于符合AVB标准的AVB交换机，规定将 $7 5 \%$ 的带宽资源用于AVB数据的传输，将剩余的 $2 5 \%$ 用于尽力而为流量的传输。SRP利用到的协议有多 MAC 注册协议 MMRP(multiple MAC registrationprotocol)、多VLAN 注 册 协议 MVRP(multiple VLANregistration protocol)和多数据流预约协议MSRP(multiplestreamregistrationprotocol)三个协议的组合去实现桥接网络的流预留，其底层协议都是多注册协议MRP(multipleregistration protocol)。

在IEEE $8 0 2 . 1 \mathrm { Q c c } ^ { [ 2 1 ] }$ 中，实现了对流预留协议 SRP 的增强，主要通过改进机制，实现了支持更多的流，并且做到了可配置的SR(streamreservation)种类和流。此外，Qcc对于流特性的描述更好并且支持3层流，具有确定性的流预留汇聚，也有用于路由和预留的用户网络接口UNI。

# 2.5可靠性传输机制

$8 0 2 . 1 \mathrm { C B } ^ { [ 2 4 ] }$ 中所规定 的 FRER(frame replication andeliminationforreliability)的目的是增加特定数据包的传递概率，当其应用在固定拓扑和拥塞保护的路径上时，能够有效的降低由于设备故障导致的丢包现象。该标准的传输模式包括一个发起者对一个接收者的单播，和一个发起者对多个接收者的多播。802.1CB通过序列号和复制每个流的数据包，在数据的发送端发送多个副本，最后在一个或多个节点重新组合并消除重复数据，从而提高可靠性，降低丢包率，如图7所示。

802.1CB的部署十分灵活，在端站和中间节点都可以应用。通过对数据包的复制和消除实现冗余性，且对于单播多播都能用，并支持流的间歇传输和大量传输。对于传输路径的创建、流预留和数据包的顺序传输等均不在FRER的考虑范围之内，这些功能将由其他协议去实现。

![](images/93dcd642aa1a7dcc759a37210c4d6c14438248f5db813fda7ba558e7f0822aa0.jpg)  
图6可抢占帧帧结构  
Fig.6Structure of preemptive frame   
图7流的多种传输路径  
Fig.7Multiple transmission path of traffic

# 3 时间敏感网络的研究情况

随着技术的不断发展，作为解决网络数据确定性传输的新方法，时间敏感网络已经获得了学术界的广泛关注。近年来的研究热点主要集中在调度分析与实现、网络时延分析、冗余性与容错性网络、前传网络和时间敏感软件定义网络几个方面。其中有新型算法的探索，有现有机制的改良，也有仿真技术的研究。

# 3.1调度与路由的相关研究

传统的以太网传输机制缺少确定性，是由于在传输的过程中，交换机的发送端口队列中待发送的帧受到同优先级和高优先级帧的影响而不得不进行等待，因此产生了延迟和不确定性。而802.1Qbv定义了一种时间触发的通信模式TAS，发送端口的队列按照GCL的规定，严格按照时间进行帧的发送。实现TSN的一个关键点是流量的调度和路由问题。

# a)流量的调度计算

对于802.1Qbv中的TAS机制，标准中只对机制的框架进行了规定，并未给出具体的实现方法。Craciunas[33]等人提出了一种802.1Qbv调度的实现方法，该方法将802.1Qbv网络中的参数总结设备能力参数和队列配置参数两类，并且用有向图表示网络的拓扑结构。对于时间敏感的流量，在确定性以太网传输的约束之上，添加了TAS机制的约束。该方法将调度的核心总结为帧偏置值的计算和传输队列的分配。对于数据传输中的约束，作者将其分为确定性网络传输的基础约束和满足802.1Qbv的约束，把问题转换为求解对于未调度系统转换为可调度系统时所需的最小队列数目，并采用SMT(satisfiabilitymodulo theories，可满足性模块理论)的方法进行了求解。

Oliver[34]等人提出了一种针对 802.1Qbv 的GCL 计算问题的解决方案，详细分析了利用一阶数组理论将系统约束形式化的适合性，并讨论了其中的调度优化问题，采用基于SMT/OMT的求解器进行调度计算。结果表明，使用一阶数组理论是合适的，尤其对于小型和中型网络具有较好的效果。

# b)流量的路由计算

TSN的标准协议中建议使用带约束的最短路径路由(constrainedshortestpathfirst)作为路由方式，与传统的最短路径路由算法(shortestpathalgorithm)相类似，这种路由方式有可能导致拥塞从而影响时间敏感流的传输。Mubarak[35]等人提出了新型路由算法LB-DRR算法和CR-DRR算法，LB-DRR算法能够实现不同链路之间的负载均衡，并能够为复制流创造多条传输路径；CR-DRR算法能够在链路发生拥塞时为流重新计算传输路径。相较于传统的最短路径路由和负载均衡路由，二者均能够在一定程度上提升链路的负载。

# c）路由调度联合计算

对于门控列表的计算是NP完全问题，Pahlevan[36]等人认为现有的解决方法忽略了调度和路由的相互影响，大多数方法计算速度较慢，也不能进行规模上的拓展，并且均未考虑多播流、内部流的相关性和分布式系统等问题。作者提出了一种基于遗传算法的路由调度联合算法，并且与基于调度表的方法进行了对比。该方法同时考虑了路由和调度的约束，并减小保护带的数量，一定程度上提升了对时间触发流量的调度能力和传输效率。

TAS机制的一个优点是实现网络的融合传输，即同时传输时间敏感的流量和一般数据流量。为了实现这种特性，需要对不同的数据流量做时间上的分割或空间上的分割。Falk[37等人认为，若采用“定制化"的方法，则会导致正确性低、复杂度高等问题。而采用ILP(integer linear programming，整数线性规划)方法进行分析计算，具有方法成熟、计算速度快的优势。该方法利用ILP进行了路由调度联合算法的实现，并且探索了问题规模的可扩展性。实验表明，本方法的运行时间对流的数量、传输周期占用情况和网络拓扑结构较为敏感。

d）考虑到稳定性的路由调度联合计算

以太网的时间特性十分依赖于数据流的调度和路由，Mahfouzi[38]等人认为在进行路由和调度计算时，应该同时对稳定性加以考虑，即要考虑到系统所能容忍的最大延迟和抖动。作者使用SMT去对路由调度联合的问题进行建模，同时考虑到实时传输下的、控制数据传输下和最差情况下的稳定性。该方法基于路由子集和时间分片思想，利用启发式算法对问题进行求解，提升了综合计算效率。

e）考虑到AVB流量的路由调度联合计算

Gavrilut[39]等人针对常见的路由和调度算法在计算时仅考虑TT流量，而忽略AVB流量的问题进行了研究，提出了一种考虑AVB流量的调度算法，在同时保证时间触发流量的可调度性的情况下，减小了AVB流量在最差情况下的时延。该算法同时结合了KSP(K-shortest pathes，K最短路径)算法和 GRASP(greedy randomized adaptive search procedures，贪心随机自适应搜索算法)算法。通过三组实验，分别评估了TT流量的可调度性、考虑路由影响下的GCL计算情况、考虑AVB流量下的路由调度联合计算情况，结果表明只有在考虑AVB 流量的前提下，才能得到对于TT流量和AVB 流量的可调度结果。

# 3.2 网络时延分析的相关研究

时间敏感网络的一个核心特性是低延迟的数据传输。网络时延分析是指对各种条件下的时延进行计算，以确定时延的上界或下界，从而进行系统性能的评估或验证。

# a）最差情况下的时延分析

按照重要程度，TSN网络中的流量可以依次分为TT流量、AVB流量和BE流量。TT流量按照GCL进行调度，时延要求最严格，AVB 流量次之，BE 基本没有要求。Zhao[40]等人对网络中的AVB流量在最差情况下的时延进行了分析，分别讨论了抢占模式和非抢占模式下的不同情况，同时考虑了TT流量对于AVB流量的影响。该方法主要利用了网络演算(networkcalculus)的理论，导出了AVBA和AVBB 流量的服务曲线，并且证明了CBS机制中的AVBcredit值不会溢出。此方法相较于现有方法，能够提供更准确的最差情况时延。

Zhang[41]等人利用网络演算的方法，对工业自动化场景下的时间敏感流量的上界进行了分析。各种不同的流量类型通过CBS机制和严格优先级机制进行整型，通过计算最差情况下的时延上限，表明只要通过合理的参数配置，常见的工业自动化所需的延迟均可满足。

在网络中确定端到端时延的上界十分重要，Benammar[42]等人认为传统的分析方法如CPA(compositionalperformanceanalysis，组合性能分析)、FA(forwardend-to-enddelayanalysis转发端到端延迟分析)、TA(trajectory approach，轨迹法)等的分析结果的端到端延迟偏大，提出了一种将FA方法和CBS相结合的解决思路，并将E2E(endtoend)延迟分为固定部分和可变部分，通过分析线性拓扑和群集拓扑，有效减小了端到端延迟的估计范围。

# b）最佳情况下的时延分析

Rivera-Verduzco[43]等人认为在时间敏感网络的分析中，最差反映时间和最佳反映时间都很重要，最差反映时间被广泛研究过，而最佳的反映时间的研究比较少。该方法认为突发传输且使用CBS机制进行调度的帧，在遇到传输冲突时会提前进行调度，并给出了无冲突情况下的帧最佳传输时间的计算方法。

c）包含CDT流量的时延分析

在实际的应用场景中，TSN网络会同时传输CDT(controldata traffic，控制数据流量)数据、AVB数据和BE 数据，其中CDT数据类似于TT数据，对时间要求很高。Maxim[44]等人认为对于AVB流的时延分析已经相对成熟，但是包含有CDT(controldatatraffic，控制数据流量)的AVB时延分析的研究相对较少。该方法通过建立基于单保护窗和多保护窗的网络模型、流量模型，进行了AVB帧的本地分析，表明突发传输会被CBS机制所限制，而最差情况下的传输时延会被限定在一定范围内。

# d)TSN系统的可行性分析

随着TSN系统的逐渐发展成熟，对于TSN的可行性分析变得愈发重要。Zhang[45]等人提出了一种基于实时演算的TSN可行性分析方法，该方法将TSN系统分解为数据模型、资源模型和组件模型，同时考虑到了关键流量的时延界限、节点的存储界限和传输资源的利用率，并利用帧抢占机制解决了不同优先级之间的冲突。

# 3.3冗余性与容错性网络的相关研究

为了保证数据传输的成功率和链路的稳定性，需要进行冗余传输机制的设计。时间敏感网络中提出了802.1CB机制，规定了帧的无缝冗余传输的基本框架。

# a)无缝冗余传输的分析与仿真

Tan[46]等人在不同网络环境下，对数据流量进行了冗余路径的传输，采用 $\mathrm { O M N e T + + } ~ 5 . 0$ 中的Core4INET的模块进行仿真，分析了冗余性对时延的影响。通过实验表明，实施冗余性会在一定程度上增加数据的传输延迟，且传输路径较长的帧总会有一个传输周期的时延。

Qian[47等人在网络拓扑、冗余标记、序列生成函数、序列恢复函数、计时机制和潜在错误探测等方面对802.1CB机制进行了详细的分析。通过设置若干个测试点，进行了802.1CB 的功能测试，并采用Visual Studio 和CppUTest来进行仿真。实验表明，将802.1CB应用于特定网络拓扑时能够减少丢包率，且不依赖于更高层的传输协议。这种特性对于传输而言是透明的，能够增加网络的无缝冗余特性。

对于验证网络协议而言，仿真是一种低成本高效率的方式，而现在还没有较为成熟的用于实现TSN时间特性和非时间特性的仿真模型。在Riverbed仿真框架的基础上，Pahlevan[48]等人提出了一种用于实现时间特性和冗余管理的仿真模型，并且加入了错误注射机制去评估系统的稳定性。实验表明对于使用802.1CB的系统而言，能够消除瞬时性的链路故障，并能够在出现永久链路故障的情况下对数据包提供有界的端到端时延和零丢包率。

# b）冗余传输的优化

802.1CB机制中所提出的冗余传输的框架允许在传输网络中的任何交换节点和端节点进行，Smirnov[49]等人认为这样会导致冗余性的实施空间过大，于是需要对传输中的冗余性和网络负载、传输时序与硬件成本做折中考虑。作者提出了两种基于SAT解码的，用于生成可行冗余消息的路由算法，并对多目标路由优化进行了拓展。通过实验对比，表明所提出的优化方法具有显著的优势，能够自动进行系统稳定性的优化。

# c）容错拓扑与路由的计算

Gavrilut[50]等人针对于安全关键的实时系统，使用UBS(urgency-basedscheduler)流量类型，建立了一个包含有冗余链路的容错拓扑，以满足减小路由开销、容错和时序要求。Gavrilut等人对启发式算法、GRASP和基于约束规划的模型3 种方法进行了对比，发现其均能够显著减小开销。相比较而言，GRASP的效果比较好，能够在较为合理的运行时间内得出结果，且可拓展性良好。

# 3.4前传网络的相关研究

前传网络是整个5G承载网中带宽要求最高，时延要求最严苛的部分。前传网中所用到的通用公共射频数字接口(commonpublic radio interface，CPRI)是一种标准化协议[51],它定义了无线基础设施基站的射频设备控制(Radioequipment control，REC)和射频设备(radio equipment，RE)之间的数字接口。这实现了不同供应商设备的互操作性，相对减小了无线服务提供商的软件投入。传统的CPRI技术存在有造价昂贵，带宽消耗大和静态配置的缺点，而利用以太网的解决方案(CPRIonEthernet，CoE)成为了一种新的解决思路。

# a) CoE的抖动和延迟分析

Chitimalla[52]等人将CPRI数据封装在以太网帧，分析了不同情况下的抖动，并提出了消除抖动的算法，实现了微秒级的抖动。Chitimalla等对于所提出的算法进行了Verilog编程，在FPGA上进行了实现。在前传网络中，对于几公里以内的多跳传输，CoE的封装会带来可接受的微小延迟。实验结果表明封装固定大小的CoE数据帧需要约数十微秒的时间，并且采用冗余传输能够减小抖动，最大可以达到1us。

# b）前传网络中M2M延迟分析：

5G 网络中要求融合网络传输，即同时承载前传数据和M2M(machinetomachine，机器对机器)数据，这一点可以利用TAS机制去实现。然而，TAS对于低优先级带宽的利用率低并且延迟大，即使没有高优先级流通过，GCL也会运行。Hisano[53]等人针对此问题，提出了一种改进的TAS 算法GS-TAS，在前传流后附加一个GS-frame，当桥接收到GS-frame时，高优先级门控状态由打开变为关闭，低优先级反之。实验结果表明，GS-TAS算法能够实现网络的融合数据传输，使得M2M数据延迟减少 $50 \%$ ，并且前传数据的延迟基本保持不变。

c)IHON和TSN的对比分析：

5G的前传网对于延迟和抖动有着严格的要求，网络中的任何桥接都可能会引入额外的延迟，必须要通过一定的方法消除或减小延迟。Bjornstad[54]等人认为对于各种消除抖动、减小延迟的方法而言，其复杂性和适用性是最为重要的。过高的复杂性和过差的适用性都不利于在实际网络系统中进行机制实现。作者详细分析了IHON(integratedhybridopticalnetworks，集成混合光网络)和TSN中的传输机制，得出了IHON抖动最低且复杂度最小，且TSN延迟更低的结论。

# 3.5时间敏感软件定义网络的相关研究

软件定义网络(software defined network，SDN)是当今网络领域的研究热点，它催生了新型网络体系结构模式，其核心思想是通过硬件设备的标准化和网络层面的控制转发分离，从而对设备进行抽象封装，来增强网络可编程能力。TSN可以与SDN的集中控制与管理相结合，实现时间敏感软件定义网络(time sensitive software defined network，TSSDN)。

# a) SDN 和 TSN 相结合

Nayak[55]等人利用TSSDN的概念，在同一SDN网络上实现了时间触发流量和非时间触发流量的传输，采用逻辑上集中控制的控制器去计算全局的调度问题，并采用ILP的方法去求解路由和调度问题，使得终端能够以较高的精度执行用户平面的包处理框架。通过仿真发现在特定的拓扑下，TSSDN具有确定的传输时延，端到端的时延在14us以内，抖动在 7us 以内。

Hackel[56]等人认为TSN网络能够借助SDN中集中控制的优势，实现网络的弹性、安全性和适配性。作者结合了TSN的实时通信和SDN控制平面编程的能力，将TSN流在SDN控制器中进行映射和注册，并通过OpenFlow 进行了实现。经过分析，作者认为只要协议映射的合适，SDN的控制开销就不会造成额外的时延。在利用SDN网络的各种优势的同时，网络的实时性能够保持不变。

为了适配和维护TSN网络，技术人员需要对各种网络设备及数据流有清晰的认识，并且需要用到相关的配置和仿真工具，导致相关工作变得复杂。而BenH.S.[57等人利用 SDN网络集中化控制的特点，对802.1Qcc中提出的控制模型进行了初步的实例化，并且以802.1AS的配置为例讨论了如何使用SDN来加速网络的配置过程。

为了减小时间敏感软件定义网络中流量的排队延迟，Haur[58]等人提出了一种时间敏感型的流量调度算法，通过该算法能够有效的减小时间复杂度，并且同时保证调度的质量。该方法与无约束路由下的调度，最短路径路由下的调度和固定路径路由下的调度进行了对比，在调度性能上有了显著的提高。

# b)TSSDN 性能评估

SDN的集中化控制有利于实现网络中的许可控制和网络重置，然而在TSN使用场景中对时延要求较高，需要对时间开销进行评估。Thiele[59]等人对应用在时间敏感领域的SDN从开销、拓展性、时延等方面进行了评估，使用CPA(compositional performance analysis，组合性能分析)框架进行建模和分析，对不同协议进行了实验评估。经测试，在最差的情况下，系统的传输延迟不高于 $5 0 \mathrm { { m s } }$ ，表明SDN在以太网许可控制和网络重置的使用场景下是可用的。

# c）基于SDN的TSN时延测量

对于802.1Qbv中提出的TAS机制而言，获取相邻节点之间的时延是很重要的。Jia[60]等人定义了时间敏感网络延迟(time-sensitivenetworkdelay，TSND)，量化了时钟同步和数据包大小对于TSND测量的影响，并提出了一种基于SDN的TSN时延测量方案。实验表明TSND能够有效的预测接收时隙，并且TSND的最大测量误差能够被控制在两个时隙内。对于数据包长度变化较大的流，使用大时延计算得出的时隙去进行传输，能够获得较小的抖动。通过使用作者提出的TSND测量方法，能够有效建立相邻节点之间的延迟数据库。

# 3.6TSN交换机的相关研究

为了保证网络的吞吐量、时延、抖动和丢包率，在网络中的任何节点都应对时间敏感流量提供确定性的服务。而对于在高端口密度和高接口速度的设备上实施TSN 标准相对较为困难。Pruski[61]等人提出了针对ASIC或FPGA的一种实现结构，通过讨论缓存结构和存储带宽需求，设计了能够支持TSN特性的交换节点。该设计能够支持帧抢占、CBS机制和TAS机制，并且有效的减小了硬件开销。

由于TSN网络的高确定性、高可靠性和高带宽，可以将其用作工业物联网的核心网。然后这种核心网需要处理大量的实时数据，目前成熟的TSN交换机仅能确定性的调度不超过1024个实时流量。JIN[62]等人针对这一问题，提出了一种支持更多实时流量的方法。作者采用SMT去列写了包传输过程并对其进行了OMT优化，并且对于调度冲突问题设计了启发式算法，相较于现有的算法，此方法在调度相同的流时仅需要1/20的调度条目。

# 4 时间敏感网络的应用现状

# 4.1汽车领域的应用现状

近年来随着信息技术的不断进步和发展，智能交通、车联网、自动驾驶等先进技术逐渐映入人们眼帘。汽车中的车载电子系统的作用越来越重要。例如现在广受关注的ADAS系统需要进行大量的数据传输和处理[63]。ADAS系统通过各种各样安装在汽车上的传感器，不断分析车内外的驾驶环境，在汽车行驶时收集数据并对其进行分析，从而实现车辆的紧急制动，避免驾驶中发生意外碰撞、偏离车道等情况，也能够实现辅助倒车、自适应巡航和驾驶员疲劳探测等功能。这些功能对车载网络数据传输的质量有着严格的要求。

传统的车载网络技术有CAN总线、LIN、FlexRay、MOST等[64]。CAN总线主要用于汽车的刹车、引擎和悬挂等系统；LIN 用于灯光、车门和遥控等系统；FlexRay主要负责引擎控制、ABS、悬挂等；而MOST是车载多媒体的首选协议。随着汽车电子的发展，这些车载网络所存在的不兼容、带宽小、高延迟和抖动等缺点逐渐突显，而TSN作为基于以太网的一种互连技术有着灵活度高且拓展性强的特点，逐渐成为新的解决思路。使用时间敏感网络技术作为通用的车内网络，能够简化车内的不同网络架构，并实现性能、时延和带宽的保证，使得车内的控制信息、音视频信息和娱乐信息，均等得到较好的服务质量。

目前支持TSN的车载设备已经开始逐步面市，例如Marvell公司所推出的88Q5050车载以太网交换芯片，是一款8端口、高安全性车载千兆以太网交换芯片，完全符合IEEE802.3和 802.1 标准，支持 TSN协议中的 802.1Qav和Qbv 功能，并且能够对输入端口的AVB流进行监管和限流。博通也推出了BCM5316x系列交换芯片，支持802.1AS、802.1Qbv、802.1Qav、802.1Qci 等协议，主要的目标市场就是无人车、无人机、机器人和L3级别的无人驾驶。

# 4.2工业控制的应用现状

工业是一个国家发展的重中之重，美国在2011年就提出了先进制造伙伴计划(AMP计划)，德国在2013年的汉诺威工业博览会上提出工业4.0的概念，我国也在2015年提出了中国制造 2025 计划[65]。这些新的工业发展规划希望未来的工业制造能够更加智能、更加先进，在生产系统、物流管理、人机互动、质量监测等方面有所提高。随着网络技术的发展，现在已经步入了信息时代，将工业和互联网技术结合是大势所趋。

在工业控制方面，有许多应用场景对实时性、确定性、鲁棒性要求很高。基于以太网的TSN技术不仅能够满足上述要求，并且为工业以太网连接到数据中心提供了解决方案。TSN能够提供高效率的实时决策信息，而且相较于现有的工业以太网技术，TSN是开放的标准，能够使得设备易于升级，降低成本，并且实现更好的兼容性。传统的控制技术都是各厂家和设备提供商的专有技术，不同的控制系统之间可能无法实现兼容，升级改造也很困难。TSN凭借这一点在一定程度上解决了工业控制领域传输协议复杂的问题。

目前，众多业界知名的IT厂商和自动化厂商已经开始跟进TSN技术，成立了众多的合作组织。在2018年的德国汉诺威的工业博览会上，由Avnu联盟、工业互联网产业联盟AII、边缘计算产业联盟ECC、华为、施耐德电气、国家仪器公司、贝加莱、TTTech 等 20余家知名组合和厂商发布了TSN+OPCUA 的智能制造测试床。测试床融合了TSN 技术和OPCUA标准，能够实现包括预测性维护网络、马达同步、绘图运动控制、OPCUAoverTSN等场景。TSN能够使得IT和OT进行融合，提高工业设备的连接性和通用性，为工业的进一步发展创造了宽阔的道路。

# 4.3电信领域的应用现状

随着智能手机的普及和发展，人们对于移动数据的需求越来越大，要求越来越高。4G通信在很多场景下已经不能够满足人们的使用需求，5G网络逐渐登上历史舞台。5G网络传输速率高，能够满足大量数据传输的应用场景，并且有着延迟低、网络容量大、流量密度大、连接密度大等特点。第五代移动通信已然成为产业界和学术界关注的重点，2019 年被称为5G元年，2019年6月，工信部正式向中国联动、中国移动、中国电信和中国广电发放了5G商牌照，5G已经进入了商用部署的关键时刻。

在2018年末，IEEE发布了针对前传网络的TSN标准——IEEE802.1CM，这个标准主要解决了利用以太网建立前传网的问题。主要的应用场景有基于云的射频接入网络和 5G小蜂窝网络，实现蜂窝射频设备和远端控制器的连接。传统的前传解决方案是采用CPRI接口去完成设备之间的连接，但是CPRI的部署成本很高，消耗带宽量大，并且只能静态配置。而采用基于以太网的方案去构建前传网络将会降低成本，并且易于配置，这使得以太网承载CPRI成为一种新的方案。CoE方案结合时间敏感网络中的技术，能够满足CPRI接口中严格的延迟和抖动要求。

# 5 时间敏感网络的发展趋势

TSN作为现今极有发展潜力的技术之一，利用多种标准协议的组合，解决了传统以太网在确定性传输方面的不足，吸引了包括学术界和产业界在内的广泛关注。但是目前TSN的各项技术还在发展之中，新的标准也在起草和讨论中。本文主要针对目前已发布的TSN标准协议进行了分析和总结，并介绍了目前产业界的应用情况。现有的TSN技术在一定程度上解决了时间敏感流在网络上的传输问题，但是离全面部署应用还有许多问题需要解决，在TSN的相关研究还需要关注以下几个方面。

# 1)工程应用与实现

TSN的部分机制只给出了技术框架标准，对于具体的实现并未作出详细规定。如何进行这些标准的配置和实现是TSN 研究方向中最直接的一个。一方面需要分析使用场景，针对不同问题去明确所要用到的机制。另一方面，也需要寻找新方法去进行配置的拓展性研究。由于TSN是一种新兴的技术，刚刚进入市场，从理论层面到实践层面，对其实现方法、性能分析、仿真技术、产品原型技术等众多工作需要进一步跟进。

# 2)互连性的提升

随着技术的不断发展，计算技术、通信技术和控制技术将会在CPS(cyber-physical systems，物理信息系统)系统中实现融合。目前，TSN往往是在一些相对封闭的局域网场景下进行应用，缺少将封闭的TSN网络和外部网络进行连接的方法。而由国家数字交换系统工程研究中心所提出的软件定义互连技术[6能够实现体系结构和处理节点可软件定义，在高能效的前提下将刚性设备变成柔性设备，支持互联协议、端□类型、拓扑结构、带宽分配、互联模式等的可软件定义，可以作为未来 TSN 与同构或异构网络进行互连的一种解决方案。

# 3)安全可靠性的提升

在TSN的使用场景中，对于系统传输的安全稳定性要求极高，802.1的TSN工作组和802.1安全性工作组已经开始了相关研究，致力于提升TSN的安全性。随着TSN互连性的提升，开放网络会导致TSN系统直接面对常见的各种攻击。如果传输路径上的某节点失效，将有可能导致整体的端到端流控特性无法实现。因此，在TSN网络中需要进行威胁探测和节点迁移技术的研究。由郭江兴等人提出的网络空间拟态防御[67]思想通过拟态系统的动态异构冗余特性，能够将非传统的安全威胁变换或归一化为经典的可靠性和鲁棒性问题并解决之，为信息系统提供了内生安全机制，可以作为提升安全可靠性的一种解决思路。

# 6 结束语

随着信息技术的发展和物联网时代的到来，TSN技术在汽车内网、工业控制、专业A/V和通信网络中都得到了应用，在利用传统以太网高带宽、低成本的同时实现了数据流的确定性传输。TSN实现了时间敏感型的数据流与尽力而为数据流在同一介质上进行传输，简化了繁多的设备和接口，获得了业界的巨大关注。然而TSN是一项相对较新的技术，在许多方面仍需要继续改进和创新，需要学术界和产业界通力合作。本文介绍了TSN 技术的发展历程，重点介绍和分析了TSN中的各项关键技术，并阐述了现有的相关研究情况，最后对未来的发展趋势作出了展望。希望通过本文的总结和梳理，能够为相关领域的研究人员提供参考和帮助。

# 参考文献：

[1]黄韬，汪硕，黄玉栋，等．确定性网络研究综述[J].通信学报,2019, 40 (06):160-176.(Huang Tao,Wang Shuo,Huang Yudong,et al.Review of deterministic network research [J]. Journal on Communications,2019, 40 (06): 160-176.)   
[2]Farkas J,Bello L,Gunther C.Time-sensitive networking standards [J]. IEEE Communications Standards Magazine,2018,2(2): 20-21.   
[3]Galloway B,Hancke G P.Introduction to industrial control networks [J]. IEEE Communications Surveys and Tutorials,2013,15 (2): 860-880.   
[4]Shafi M,Molisch A F,Smith PJ,et al.5G:a tutorial overview of standards,trials,challenges,deployment,and practice [J].IEEE Journal on Selected Areas in Communications,2017,35 (6):1201-1221.   
[5] Makowitz R,Temple C.FlexRay-a communication network for automotive control systems [C]// Proc of 2006 IEEE International Workshop on Factory Communication Systems.Piscataway,NJ:IEEE Press,2006: 207-212.   
[6]Commitee A.ARINC specification 664P7: aircraft data network, part 7: AvionicsFull-Duplex Switched Ethernet (AFDX） network [J]. Aeronautical Radio Inc,2005.   
[7]Feld J. PROFINET-Scalable factory communication for allapplications [C]//Proc of 2004 IEEE International Workshop on Factory Communication Systems.Piscataway, NJ: IEEE Press,2004: 33-38.   
[8]Langlois K,Van Der Hoeven T,Cianca DR,et al.EtherCAT tutorial an introduction for real-time hardware communication on windows [J]. IEEE Robotics & Automation Magazine,2018,25(1): 22-122.   
[9]Cena G,Seno L,Valenzano A,et al.Performance analysis of Ethernet Powerlink networks for distributed control and automation systems [J]. Computer Standards & Interfaces,2009,31 (3): 566-572.   
[10] Alvarez I,Proenza J,Barranco M,et al. Towards a time redundancy mechanism for critical frames in time-sensitive networking [C]//Proc of 2017 IEEE International Conference on Emerging Technologies and Factory Automation. Piscataway,NJ: IEEE Press,2017: 1-4.   
[11]Alvarez I,Barranco M,Proenza J,et al. Towards a fault-tolerant architecture based on time sensitive networking [C]// Proc of 2018 IEEE International Conference on Emerging Technologies and Factory Automation.Piscataway,NJ: IEEE Press,2018:1113-1116.   
[12]Alvarez I,Almeida L,Proenza J,et al.A first qualitative comparison of the admission control in FTT-SE,HaRTES and AVB [C]//Proc of 2016 IEEE World Conference on Factory Communication Systems. Piscataway,NJ: IEEE Press,2016:1-4.   
[13] IEEE 802.1Qcp-2018．Standard for Local and metropolitan area networks-Bridges and Bridged Networks-Amendment 30:YANG Data Model [S]. Piscataway, NJ: IEEE Press, 2018.   
[14] IEEE 802.1Qav-2009．Standard for Local and metropolitan area networks-Virtual Bridged Local Area Networks Amendment 12: Forwarding and Queuing Enhancements for Time-Sensitive Streams [S]. Piscataway, NJ: IEEE Press,2009. Keservauon rrotocol(SKr)[SJ. PIscataWay, NJ: IEEE Press, ∠UIU.   
[16] IEEE 802．1Qca-2015.Standard for Local and metropolitan area networks-Bridges and Bridged Networks-Amendment 24: Path Control and Reservation [S].Piscataway,NJ: IEEE Press,2016.   
[17] IEEE 802.1Qbv-2015．Standard for Local and metropolitan area networks-Bridges and Bridged Networks-Amendment 25: Enhancements for Scheduled Traffic [S].Piscataway,NJ: IEEE Press,2016.   
[18] IEEE 802．1Qbu-2016.Standard for Local and metropolitan area networks-Bridges and Bridged Networks-Amendment 26: Frame Preemption [S].Piscataway,NJ: IEEE Press,2016.   
[19] IEEE 802.1Qch-2017．Standard for Local and metropolitan area networks-Bridgesand Bridged Networks-Amendment 29: Cyclic Queuing and Forwarding [S]. Piscataway,NJ: IEEE Press, 2017.   
[20] IEEE 8021Qci-2017.Standard for Local and metropolitan area networksBridges and Bridged Networks-Amendment 28: Per-Stream Filtering and Policing [S]. Piscataway,NJ: IEEE Press,2017.   
[21] IEEE 802.1Qcc-2018.Standard for Local and Metropolitan Area Networks-Bridges and Bridged Networks-Amendment 31: Stream ReservationProtocol(SRP）EnhancementsandPerformance Improvements [S].Piscataway,NJ: IEEE Press,2018.   
[22] IEEE 802.1BA-2011．Standard for Local and metropolitan area networks-Audio Video Bridging (AVB) Systems [S]. Piscataway, NJ: IEEE Press, 2011.   
[23] IEEE 802.1AS-2011. Standard for Local and Metropolitan Area Networks-Timing and Synchronization for Time-Sensitive Applications in Bridged Local Area Networks [S].Piscataway,NJ: IEEE Press,2011.   
[24] IEEE 802.1CB-2017．Standard for Local and metropolitan area networks-FrameReplicationand Elimination forReliability[S]. Piscataway,NJ: IEEE Press,2017.   
[25] IEEE 802.1CM-2018．Standard for Local and metropolitan area networks-Time-Sensitive Networking for Fronthaul [S].Piscataway, NJ: IEEE Press, 2018.   
[26] IEEE 1588-2008 (Revision of IEEE Std 1588-2002). Standard for a Precision Clock Synchronization Protocol for Networked Measurement and Control Systems [S].Piscataway,NJ: IEEE Press,2008.   
[27]郑昊．基于IEEE802.1AS的低延迟时间感知系统的设计与实现[D]. 西安：西安电子科技大学，2018.(Zheng Hao.Design and implementation of low latency time-aware system based on IEEE 802. 1AS [D]. Xi'an: Xidian University,2018.)   
[28] Garner G,Ryu H. Synchronization of audio/video bridging networks using IEEE 802.1AS [J]. IEEE Communications Magazine,2011,49 (2): 140-147.   
[29] IEEE 802.3br-2016.Standard for Ethernet Amendment 5:Specification and Management Parameters for Interspersing Express Traffic [S]. Piscataway, NJ: IEEE Press, 2016.   
[30] Lo Bello L, Steiner W.A perspective on IEEE time-sensitive networking for industrial communication and automation systems [J].Proceedings of the IEEE,2019,107(6):1094-1120.   
[31] Lee J,Park S.Time-Sensitive Network(TSN) Experiment in SensorBased Integrated Environment for Autonomous Driving [J]. Sensors, 2019,19 (5): 1111-1122.   
[32]李彦刚，邓文平，王宏，等．域内路由协议OSPF与 IS-IS 差异性的 研究与分析[J]．计算机科学,2015,42(S1):256-259.(Li Yangang, Deng Wenping,Wang Hong，et al.Research and analysis on the differences between intra-domain routing protocols OSPF and IS-IS [J]. Computer Science,2015,42 (S1): 256-259.) 2016 International Conference on Real-Time Networks and Systems. New York,NY: ACM,2016:183-192.   
[34] Oliver S,Craciunas S, Steiner W.IEEE 802.1Qbv gate control list synthesis using array theory encoding [C]// Proc of 2018 IEEE RealTime and Embedded Technology and Applications Symposium. Piscataway, NJ: IEEE Press,2018:13-24.   
[35] Ojewale M A,YOMSI P M. Routing heuristics for load-balanced transmission in TSN-based networks [J].ACM Sigbed Review,2020,16 (4): 20-25.   
[36] Pahlevan M,Obermaisser R.Genetic algorithm for scheduling timetriggered traffic in time-sensitive networks [C]// Proc of 2018 IEEE International Conference on Emerging Technologies and Factory Automation.Piscataway,NJ: IEEE Press,2018:337-344.   
[37] FalkJ,DurrF,RothermelK,et al.Exploring practical limitations of joint routing and scheduling for TSN with ILP [C]// Proc of 2018 IEEE International Conference on Embedded and Real-Time Computing Systems and Applications.Piscataway,NJ: IEEE Press,2018:136-146.   
[38] Mahfouzi R,Aminifar A,Samii S,et al. Stability-aware integrated routing and scheduling for control applications in ethernet networks [C]// Proc of 2018 IEEE Design,Automation & Test in Europe Conference & Exhibition.Piscataway, NJ: IEEE Press,2018: 682-687.   
[39] Gavrilut V, Zhao L，Raagaard M,et al. AVB-aware routing and scheduling of time-triggered traffic for TSN[J]. IEEE Access,2018,6: 75229-75243.   
[40] Zhao X,Pop P, Zheng Z,et al. Timing analysis of avb traffic in tsn networks using network calculus [C]/ Proc of 2018 IEEE Real-Time and Embedded Technology and Applications Symposium. Piscataway, NJ: IEEE Press,2018: 25-36.   
[41] Zhang J,Chen L，Wang T,et al.Analysis of TSN for industrial automation based on network calculus [C]/ Proc of 2019 IEEE International Conference on Emerging Technologiesand Factory Automation (ETFA).Piscataway, NJ: IEEE Press,2019: 240-247.   
[42] Benammar N,Bauer H,Ridouard F,et al. Timing analysis of AVB Ethernet network using the forward end-to-end delay analysis [C]/ Proc of 2018 International Conference on Real-Time Networks and Systems. New York,NY: ACM,2018: 223-233.   
[43] Rivera-Verduzco HJ,Cuijpers L,Cao JY,et al. Work in progress: bestcase response time analysis for Ethernet AVB [C]/ Proc of 2017 IEEE Real-Time Systems Symposium.Piscataway,NJ: IEEE Pres,2017: 37- 380.   
[44] Maxim D,Song YQ.Delay analysis of avb traffic in time-sensitive networks (TSN)[Cl//Proc of 2017 International Conference on RealTime Networks and Systems. New York,NY: ACM,2017: 18-27.   
[45] Zhang P,Liu Y,Shi JQ,et al.A feasibility analysis framework of time sensitive networking using real-time calculus [J].IEEE Access,2019,7: 90069-90081.   
[46] Tan TY,Park S K. Redundancy path implementation for schedule rafic [Cl// Proc of 2018 IEEE International Workshop on Advanced Image Technology. Piscataway, NJ: IEEE Press,2018: 1-3.   
[47] Qian S F,Luo F, Xu JP,et al. An Analysis of Frame Replication and Elimination for Time-Sensitive Networking [C]// Proc of 2017 International Conference on Network, Communication and Computing. New York,NY:ACM,2017: 166-170.   
[48] Pahlevan M, Obermaisser R.Redundancy management for safety-critical applications with time sensitive networking [C]// Proc of 2018 IEEE InternationalTelecommunicationNetworksandApplications Conference.Piscataway,NJ: IEEE Press,2018:1-7.   
[49] Smirnov F,Reimann F,Teich J,et al.Automatic optimization of redundant message routings in automotive networks [C]// Proc of the 2018 International Workshop on Software and Compilers for Embedded Systems.New York,NY:ACM,2018:90-99.   
[50] Gavrilut V, Zarrin B,Pop P,et al.Fault-tolerant topology and routing synthesis for IEEE time-sensitive networking $[ \mathrm { C } ] / \AA$ Proc of 2017 International Conference on Real-Time Networks and Systems.New York,NY:ACM,2017:267-276.   
[51] CPRI alliance V4．2.Common Public Radio Interface (CPRI) SPECIFICATION V4.2 [S].2010.   
[52] Chitimalla D,Kondepu K,ValcarenghiL,et al.5G fronthaul-latency and jitter studiesof CPRI over Ethernet [J].Journal of Optical Communications and Networking,2017,9 (2): 172-182.   
[53]Hisano D,Nakayama Y,Kubo T,et al. Gate-shrunk time aware shaper: low-latency converged network for $5 \mathrm { g }$ fronthaul and m2m services [C]// Proc of IEEE Global Telecommunications Conference(GLOBECOM) . Piscataway,NJ: IEEE Press,2017:1-6.   
[54] Bjornstad S,Chen D,Veisllari R,et al.Handling delay in $5 \mathrm { g }$ Ethernet mobile fronthaul networks [C]// Proc of the 2018 IEEE European Conference on Networks and Communications.Piscataway, NJ:IEEE Press,2018:1-9.   
[55] Nayak NG,Durr F,Rothermel K,et al. Time-sensitive software-defined network(TSSDN） for real-time applications [C]// Proc of 2016 International Conference on Real-Time Networks and Systems.New York,NY: ACM,2016:193-202.   
[56] Hackel T,Meyer P,Korf F,et al. Software-defined networks supporting time-sensitive in-vehicular communication [C]//Proc of the 2019 IEEE vehicular technology conference (VTC Spring) .Piscataway,NJ: IEEE Press,2019: 1-5.   
[57] Said S B H, Truong Q H,Boc M. SDN-based configuration solution for IEEE 802.1 time sensitive networking(TSN)[J].SIGBED Rev,2019, 16 (1): 27-32.   
[58] Haur N K,Chin T S. Time-sensitive-aware scheduling traffic (tsa-st) algorithm in software-defined networking $[ \mathrm { C } ] / \AA$ Proc of the 2019 International Conference on Internet and Distributed Computing Systems. Berlin,German: Springer,2019: 248-259   
[59] Thiele D,Ernst R.Formal analysis based evaluation of software defined networking for time-sensitive ethernet [Cl// Proc of the 2016 Design, Automation & Test in Europe Conference & Exhibition.New York,NY: ACM,2016: 31-36.   
[60] Jia ZY,WangJL,Chen X,et al.An SDN-based measurement scheme to build delay database for time-sensitive network scheduling [J]. International Journal of Innovative Computing Information and Control, 2019,15 (4): 1271-1286.   
[61] Pruski A,Berger M.Design considerations for high-performance Time sensitive networking switches [C]//Proc of the 2019 10th International Conference on Networks of the Future (NoF）.Piscataway,NJ: IEEE Press,2019:114-117.   
[62] Jin X,Xia C,Guan N,et al.Real-time scheduling of massive data in time sensitive networks with a limited number of schedule entries [J].IEEE Access,2020,8:6751-6767.   
[63] Ziebinski A,Cupek R,Grzechca D,et al.Review of advanced driver assistance systems (ADAS）[C]// Proc of the AIP Conference Proceedings,New York:AIP,2017:1-4.   
[64]提芳．车载时间敏感网络流预留协议研究[D]．西安：西安电子科 技大学,2018.(Ti Fang.The research of stream reservation protocol for in-vehicular time-sensitive network[D].Xi'an:Xidian University,2018.)   
[65] Liao Y,DeschampsF,Loures E,et al.Past,present and future of Industry 4.O-a systematic literature review and research agenda proposal [J]. International journal of production research,2017,55 (12): 3609-3629.   
[66]吕平，刘勤让，邬江兴，等．新一代软件定义体系结构[J].中国科 学：信息科学,2018,48(03):315-28.(Lyu Ping,Liu Qinrang,Wu Jiangxing,et al. Next-generation software-defined architecture [J]. SCIENTIA SINICA Informationis,2018,48 (03): 315-28.   
[67]邬江兴．网络空间拟态防御导论[M].北京：科学出版社,2016.(Wu Jiangxing.Introduction to cyberspace mimic defense [M].Beijing: Science Press,2016.)