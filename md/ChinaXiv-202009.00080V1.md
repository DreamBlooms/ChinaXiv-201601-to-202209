# 基于SDN的智能交通架构

邸剑，徐英会，蔡震(华北电力大学 控制与计算机工程学院，河北 保定 071003)

摘要：软件定义网络(SDN)是近年来备受关注的网络问题，已有学者将其和智慧城市建设进行融合。针对当今交通分散治理现状进行了研究，结合 SDN 转控分离和集中控制等特性，将其引入智能交通系统(ITS)，提出了一个协同管理架构，旨在实现协同管理、改善交通。首先阐述了SDN的特点，利用其特性并结合ITS，提出了基于 SDN的智能交通架构；其次，结合动态限速、路径诱导及天气等因素构建了协同管理策略模型，并将其和单一控制策略对比；最后通过仿真实验，对提出的架构策略进行了验证分析。实验结果表明，该架构下的管理与单一控制策略相比，平滑了交通流，使交叉口的平均延误降低 $20 . 7 \%$ ，平均排队长度下降 $3 5 \%$ 。

关键词：SDN；转发与控制分离；协同管理；平滑交通流中图分类号：TP3 doi:10.19734/j.issn.1001-3695.2020.02.0068

# Traffic intelligence platform based on SDN architecture

Di Jian, Xu Yinghui†, Cai Zhen (SchoolofControl&ComputerEngineering,North China ElectricPower University,Baoding HebeiO710o3,China)

Abstract: Software Defined Networking (SDN)hasatracted muchatention inrecent years.Some scholars have integrated it with smartcityconstruction.In viewof thecurent situation ofdecentralized traffic management and combined with the characteristicsofSDNforwardingandcontrol separationandcentralizedcontrol,introduces itinto IntellgentTransport System (ITS),and proposes a collaborative management architecture to achieve collaborative managementand improve trafic.Firstly,thecharacteristicsofSDNareexpounded,andanintellgent traficarchitecturebasedonSDNisproposedby using ITS characteristicsand combining with ITS.Secondly,acolaborative management strategy model isbuiltcombining factors such asdynamic speed limit,path guidanceand weatherandcompared withasinglecontrolstrategy.Finally,through simulation experiments,the proposedarchitecture strategy was verifiedand analyzed.The experimentalresults show hat compared withthesinglecontrolstrategy,the managementunderthisarchitecturesmoothsthe traficflow,educes theaverage delay at the intersection by $20 . 7 \%$ , reduces the average queue length by $3 5 \%$ ：

Key words: SDN; separation of forwarding and control; collaborative management; smooth traffic flow

# 0 引言

智能交通系统[1](intelligent transportation system，简称ITS)通过对关键基础理论模型的研究，整合先进技术并应用于交通系统，建立起一种大范围、全方位发挥作用的实时、准确、高效的交通系统[2，并运用现代科技手段在车辆、车辆使用者、道路之间建立智能的联系，保障了车车、车路的和谐统一，使车辆在道路上安全、顺畅的行驶，其发展为解决城市交通拥堵提供了有效的支持。软件定义网络[3,4](softwaredefinednetwork，SDN)作为新兴的网络体系框架，它是由美国GENI项目资助的斯坦福大学CleanSlate课题组在2006年首次提出的，其核心思想是将传统紧密耦合的网络设备解耦合，实现控制层面和转发层面的分离。

SDN是基于集中控制、转控分离的架构实现对网络资源的全局集中管控[5.6]。利用 SDN 的特点，可以实现将分散的交通进行统一的管理，让数据的收集和分发得到有效利用。现存的交通管理系统现状多为分散管理，即各部门各司其职。而且随着当前车辆的逐渐增多，解决综合行程时间、道路损耗、车辆排队增多等现象已经成为当今交通系统中的重要问题。为了改善交通拥堵，有必要使当前收集到的交通信息和有关部门进行合理的统一管理。其关键需求就是如何使当前路径诱导、信号灯控制、动态限速等分散管理进行统一化，并制定统一的智能交通架构，使其可以有效平滑交通流并改善交通现状。所以本文设想将当前车辆系统和软件定义网络相结合，进行统一的管理。同时，满足良好的通用性、自适应性和可扩展性能，以达到适应不同的场景需求，亦能对当前的环境作出相应的改善。

随着SDN的普及以及迅速发展，将SDN和VANET(vehicular ad hoc networks)、QoS(quality of service)、IoT(InternetofThings)等进行结合，这也使得将SDN引入到ITS 中成为可能。金良等人将 SDN引入智慧城市建设，改变传统的运维模式，实现网络能力虚拟化。文献[7]将SDN应用于智慧城市边缘节点及智慧城市的传输链路和运维体系中，文献[8]提出了一种基于 SDN 的动态资源分配算法，文献[9]提出了将SDN 和人工智能进行融合，提出了一种新的交通网络系统的设计方法；文献[10]提出结合SDN和VANET的SDVN架构来有效的构建交通流，文献[11]引入中央控制器的概念，并将其应用于交叉口交通流控制模型等。近年来，越来越多的学者将SDN 和交通领域相结合，而设计一个统一管理的架构对于当前交通现状尤为重要。

# 1 SDN

软件定义网络，是一种网络架构，旨在试图通过一个集中的控制器，让网络管理员可以方便地定义基于网络流的安全策略，并将这些安全策略应用到各种网络设备中，从而实现对整个网络通信的安全控制。它的设计理念是将网络的控制平面和数据转发平面分离，从而通过集中的控制器中的软件平台实现可编程化控制底层硬件。在SDN网络中，网络设备只负责单纯的数据转发，可以采用通用的核心思想就是硬件，而原来负责控制的操作系统将转变为独立的操作系统，负责对不同业务特性进行适配，网络操作系统和业务特性以及硬件设备之间的通信都可以通过 SDN应用编程[12\~16]实现。选取SDN和ITS相结合，主要是由于SDN的优势：

a)转发与控制分离：SDN控制器实现网络拓扑的收集、路由的计算、网络的管理与控制等功能，而网络层设备仅负责流量的转发以及策略的执行。通过这种方式可使得网络系统的转发面和控制面独立运行，使设备的硬件通用化、简单化，设备的硬件成本也可大幅降低。

b)控制逻辑集中：控制面的集中化，使SDN控制器拥有网络的全局静态拓扑、全网的动态转发表信息等，可集中控制不同层次的网络，实现网络的多层多域协同与优化，更可依托全局的拓扑动态转发信息帮助实现快速的故障定位及排除，控制层上面承接应用，下面承接网络硬件设备，并提高运营效率。

c)网络能力开放化：通过集中的SDN控制器实现网络资源的统一管理、整合、虚拟化后，采用规范化的北向接口为上层应用提供按需分配的网络资源及服务，进而实现网络能力开放。这样的方式打破了现有网络对业务封闭的问题，是一种突破性的创新。

# 2 基于SDN的智能交通系统架构

文中提出的架构综合运用SDN、智慧交通等技术，以提升道路交通流量为目的，逐步实行一体化的管理方式，并且这也是信息化融入交通管理行业的发展趋势。其整个的基于SDN的智能交通架构以“集中管理、统一部署”为目标，旨在为现代交通管理提供帮助。总体架构如图1所示。

![](images/300d04ed3ac46f8452d6273dbdd475cfc898913a372c7c5da188c2e3c32b3d2b.jpg)  
图1基于 SDN 的智能交通架构图  
ig.1SDN-based intelligent transportation architecture diagram

路段信息的分发和信息的收集由SDN控制器控制。SDN由于对网络的集中控制，在有效管理资源方面起着重要的作用。该架构的目的是将收集到的信息进行统一的分发和负责对车辆的调度，然后达到缓解交通拥堵的效果。文中提出的框架主要分为三个层面：数据层、控制层、应用层。

a)数据层：该层是由一些智能终端设备组成，如：摄像头、信号灯、扬声器、显示牌、路侧单元RSU(road sideunit)、车载单元OBU(on boardunit)等，其用于捕捉收集车辆信息，并通过传感技术、射频识别技术、车辆定位、信号处理技术等，对车辆节点、道路状态、道路设施等进行实时的全方位监控，采集相应的基础数据，从而为系统应用提供全面、原始的终端信息服务。整个道路网络由多个RSU覆盖，这些RSU是启动OpenFlow[17]的交换机。每辆车都配有OBU，其可以接收和响应RSU的信息。所有的车辆和RSU都与一个具有高速无线、有线的SDN控制器相连。由于SDN控制器的集中控制[18]功能，它能够协调底层收集来的数据，并根据其进行最优路径[19,20]的分配及对车辆进行合理的调度。

b)控制层：该层包含SDN控制器和一个云平台数据库。SDN控制器通过高速网络与云存储技术相结合，将智能终端感知系统采集的信息、图片等，按照既定的存储要求进行大容量分布式存储，实现原始数据的长效存储，方便后期查询和使用。文中所提出的控制架构是层次控制框架，如图2所示。该框架在路边基础设施和车辆之间传输信息，上层控制器为下层控制器提供全网协调；路边控制器可以控制公路的一部分，其将自身提供的车辆位置、流量信息等交付给上层控制器，并为车辆提供动态路径诱导；车辆控制器接受来自上层控制器的命令，并能够设定速度等，将这些命令转换为车辆的刹车、转向等控制信号。

![](images/cab8bcb8b9f33b566f729289c87183116c9e2a586bd7c24ef40e646ce0875c0f.jpg)  
Fig.2Hierarchical control chart of SDN

同时，SDN控制器可根据各网口单元反馈的实时信息，对整个交通网络进行统筹调度，进行实时路径诱导，并下达最优的系统策略，使整个交通网络达到最优的通行效果。上层SDN控制器根据车辆车载单元以及路侧单元获得的实时数据，为车辆提供一个路线，该路线可使车直接行驶到目的地。上层控制器将这个信息反馈给车主，并发送给当前交叉□的引导模块或者设备。当有多个车辆到达交叉路口，使用交换机进行分支调度。控制器根据该车辆需要到达的目的地信息，查找其保存的引导最优路径，并指导该车辆的运行路线。整个工作过程如下图3所示。

![](images/998dbee90940bff8f58bde0a554b89f69207eddd130f5e65681fcc3a93e83e1a.jpg)  
图2 SDN 的层次控制图  
图3基于 SDN 的车辆引导控制系统结构示意图  
Fig.3SDN-based vehicle guidance control system structure

c)应用层：应用层可将获取的信息数据通过特定的服务接口，即控制器向上层业务应用开放的接口，直接为应用层业务服务。应用层有大量的应用或软件，负责加载与开展各类应用业务，并能允许第三方或用户自由选择应用。在此过程中无须对底层的设备进行技术细节的操作，而且不会影响物理设备的正常运行。应用层主要面向车辆拓展网络功能，实现智能交通管理、车辆安全控制、以及其他的安全应用，同时还为各种用户提供互联网信息查询、广播信息、流量整型、车辆基础信息、车载娱乐共享等服务。

# 3 基于SDN的智能交通系统架构的应用

# 3.1分散控制下的交通模型

针对现存的交通系统中存在的治理方式多为分散、单一的控制，如下图4所示。由于篇幅原因，文中只考虑路径诱导、动态限速以及信号灯协调等方面对于交通系统的影响。造成交通拥堵的原因有很多，例如：交叉信号的时机不合理、交叉口设施不完善、车辆行驶秩序混乱、交叉口管理单一等。交通拥堵发生的大部分时间是居民出行的高峰期，其发生过程通常从路网中的某个瓶颈交叉口开始。对于城市道路而言，交叉口是城市道路系统的重要组成部分，在道路的衔接中起着举足轻重的作用，其通行能力很大程度上决定或制约着整个城市路网通行能力的大小。城市交叉口往往是整个城市路网的瓶颈，成为路网规划、治理交通的重点。首先，交通瓶颈处车辆队列过长，导致交通拥堵范围较小。当地交通拥堵对整个道路网络通行能力影响不大，但如果你不及时采取控制措施，当积累到上游交叉口排队时，可能会阻碍其他正常运行交通车辆的方向，并逐渐影响到周围的交叉口，导致排队的连锁反应，造成大面积交通拥堵。

![](images/f29492675d27b6ef51d82bb143ae59620ad49183fe878a859ffec573d8bbfa65.jpg)  
图4单一控制示意图

目前，我国对这方面虽然进行了一定的研究，但是还没有较成熟的理论和方法。但是，当前这些交通管理中存在着下面的缺点是不得不将其考虑在内的。

a)非动态：有效采集的交通系统中的信息(车辆位置、行程时间等)，无法动态、准确的反映交通系统的准确状态。

b)非全局：现有的智能交通系统管理相对独立，各系统采集的信息不能互通。不同设备商的系统间或设备间接口不开放，导致交通状况分析和判断无法有效地利用独立系统间的交通信息协调影响，造成当前的交通管理结果不具有全局性，如诱导、限速、信号灯等之间都是分开控制的。

鉴于此，本文考虑结合 SDN[21,22]集中控制、转控分离、可编程的特性，将这些和交通有关的因素综合考虑，合理的利用收集到的信息，实时分发控制命令，有效地治理交通。

# 3.2统一控制下的交通模型

由于交通系统需要满足随机、动态、实时等特性，另外，考虑到不利的天气条件也是对当前交通的影响因素。它很可能会增加交通事故的发生，从而增加道路死亡率[23,24](Roadtrafficcasualties，RTC)的发生，因为它会影响人类(例如：行人能见度、交通需求、身心不适、车辆的性能、稳定性以及操控性)及交通环境(例如：路面情况、交通量等)。因此，本文在对整体架构模型的设计上，考虑将天气、司机在路径诱导中其自身对路段的熟悉度等定性因素、动态限速、信号灯控制以及路径诱导相结合。其整个工作过程如下：从车载定位系统(global positioning system，GPS)、路侧单元等获得的信息上传至上层管理器，并由其进行统一的调配，下发控制命令给车辆。出行者可以预设出行需求，比如需不需要路径诱导、动态限速等。在车辆进入上游交叉口时，根据RSU以及GPS获取到的信息，合理的根据队列长度调整红绿灯的时长并进行速度的调控。

针对上面提出的问题，文中采用SDN集中控制，实现物联网的数据聚合，得到由数据层、控制层、应用层组成的数据聚合体系结构。SDN控制器位于控制层，它可以实现对发送数据的聚合处理，并能根据发布的规则算法进行控制，以减少在网络中传送的数据量，达到减少能源消耗的目的。本文设想一个可以协同控制的交通模型，使其合理的利用收集到的信息，并能进行统一的调配。车辆的到达服从泊松分布，并可通过样本均值得到某一时间段内车辆到达的平均数量。在交通流中，衡量交通状况的一个表征就是交叉口处车辆的多少，而体现这一重要指标的是排队长度，等待排队行驶的车辆越少，可认为该交叉口交通状况相对良好。文中所用的部分参数如下表1所示。

表1关键参数及定义  
Tab.1Key parameters and definitions  

<html><body><table><tr><td>参数名</td><td>意义</td></tr><tr><td>Ls</td><td>两个相邻交叉口的长度</td></tr><tr><td>L1</td><td>调整之前的排队长度</td></tr><tr><td>Li</td><td>调整之后的排队长度</td></tr><tr><td>△L</td><td>调整过程中的排队长度变化量</td></tr><tr><td>Q</td><td>两个路段之间的车流量</td></tr><tr><td>p</td><td>车辆运动过程中的恒定密度</td></tr><tr><td>pj</td><td>道路的的阻塞密度</td></tr><tr><td>V</td><td>调整之后的速度</td></tr><tr><td>V</td><td>调整之前的速度</td></tr><tr><td>△V</td><td>调整过程中的速度的变化量</td></tr><tr><td>a</td><td>车辆在行驶过程中的加速度</td></tr><tr><td>QL</td><td>左转相位的进入的车流量</td></tr><tr><td>QR</td><td>右转相位的进入的车流量</td></tr><tr><td>Qs</td><td>直行相位的进入的车流量</td></tr><tr><td>DT</td><td>时间延误</td></tr><tr><td>dn(t)</td><td>两辆车的间距</td></tr><tr><td>T</td><td>信号周期时长</td></tr><tr><td>TL</td><td>左转相位的绿灯时长</td></tr><tr><td>TR</td><td>右转相位的绿灯时长</td></tr><tr><td>Ts</td><td>直行相位的绿灯时长</td></tr><tr><td>tq</td><td>车辆的启动损失时间</td></tr></table></body></html>

由于车辆到达是不平衡的，交叉口会出现拥堵情况。因此，本文考虑协同控制模型，让车辆分布更加均匀，使交叉□的排队长度得到有效的调整，从而改善整个交通系统状况。

![](images/4f155c53f8bb20dc2cfb8b647e552a19240e386aa7b52d75dca36fb7fe29c302.jpg)  
Fig.4Single control diagram   
图5相邻交叉口示意图  
Fig.5Adjacent intersection

在车辆通过相邻交叉口的过程中，车流量遵循守恒定律，满足 $\scriptstyle { \mathrm { I n } } ( \mathrm { Q } ) = { \mathrm { O u t } } ( \mathrm { Q } )$ ，即两个相邻交叉口路段内，流入的车流量和流出的车流量保持相等。对于匀速运动的恒定密度车流而言，交通流变量函数关系为

$$
Q = V \cdot \rho
$$

相邻交叉口的长度是由当前拥堵车段的长度 $\mathrm { L } _ { 1 }$ 和队尾部分的长度两部分组成，如上图5所示。根据车辆守恒定律，可以得到式(2)：

$$
L _ { 1 } \cdot \rho + ( L _ { s } - L _ { 1 } ) \frac { Q } { V } = L _ { 1 } ^ { ' } \rho + ( L _ { s } - L _ { 1 } ^ { ' } ) \frac { Q } { V ^ { ' } }
$$

等式左边第一部分表示未调整之前的排队长度的车辆，第二部分表示剩余部分的排队车辆数，等式右边表示调整之后的排队车辆的长度和排队之后剩余的车辆数总和。假设实验环境是在正常天气环境中：在本路段行驶时，当车辆无法以当前速度通过交叉口时；车辆进入引导区域后，信号状态为红色或信号为绿色，但交叉口处队列未消散；或车辆进入引导区域后，信号为绿色，车辆在绿灯结束前尝试通过交叉□，将对其进行速度引导。如果车辆可以通过引导，使其在当前绿灯间隔处能加速通过交叉口，则对车辆进行加速引导；另一方面，当车辆即使在当前的最大限速下也无法通过交叉口时，则对车辆进行减速引导，使车辆减速到合适的速度，能在下一个绿灯间隔时通过交叉口。引导速度计算如式(3)。

$$
\mathbf { V } = \left\{ \begin{array} { c c } { \mathbf { V } } & { \rho < \rho _ { j } , \mathbf { V } < \mathbf { V } _ { \mathrm { m a x } } } \\ { 0 } & { \rho \geq \rho _ { j } , \mathbf { V } < \mathbf { V } _ { \mathrm { m i n } } , \mathbf { V } ( t ) < d _ { n } ( t ) } \\ { \mathbf { V } _ { \mathrm { - a t _ { i } } } } & { \rho < \rho _ { j } , \mathbf { V } _ { \mathrm { m i n } } \leq \mathbf { V } , \mathbf { V } ( t ) > d _ { n } ( t ) } \\ { \mathbf { V } _ { \mathrm { + a t _ { i } } } } & { \rho < \rho _ { j } , \mathbf { V } \leq \mathbf { V } _ { \mathrm { m a x } } } \end{array} \right.
$$

根据现实情况考虑，雨雪天气也会对行车速度产生影响。有数据显示，在不同天气的同一路段行驶速度中，有3/4的路段在雨天速度会下降，有1/4的路段在雨天速度相对于晴天上升。这说明降雨对于城市路网中道路速度的影响并不是均质的。雨天车辆速度的变异系数反映了道路对降雨天气的敏感程度，变异系数越大反映道路在雨天时的速度越不稳定，该道路越容易受到外部环境的干扰，因此速度下降越明显；车流量大的道路发生拥堵的可能性更大，在降雨天车速下降程度更大。因此，有必要引入速度修正因子，降雨天的速度计算公式如下：

$$
V _ { r a i n } = V \left( 1 - G _ { m } \right)
$$

其中， $V _ { r a i n }$ 表示降雨天的速度， $\boldsymbol { V }$ 表示当月同时间正常天速度$G _ { { \scriptscriptstyle m } }$ 代表速度修正因子。在车辆行驶时，司机发现前方障碍物，紧急刹车自动至障碍物完全停车的最短距离为停车视距。车辆在制动时间内的行驶距离 $\mathrm { S } _ { \mathrm { l } }$ 、司机反应时间内车辆行驶距离 $\mathbf { S } _ { 2 }$ 及停车后的安全距离 $\mathbf { S } _ { 3 }$ 之和，要在司机可见度范围之内。而雨天环境下高速公路的最大车速不能超过停车视距的安全车速 $\mathrm { \Delta V }$ ，也不能超过路段最大限速值 $\mathrm { V _ { l i m } }$ 。需要满足下列约束：

s.t.

$$
S _ { 1 } + S _ { 2 } + S _ { 3 } \leq d
$$

$$
V _ { \mathrm { r a i n } } { = } \operatorname* { m i n } ( V , V _ { \mathrm { l i m } } )
$$

将式(2)中排队长度、速度的变化分别统一表示为$\Delta L = L _ { 1 } - L _ { 1 } ^ { ' }$ ， $\Delta V = V _ { 1 } - V _ { 1 } ^ { \cdot }$ 并将其代入式(1)，可以得到：

$$
\Delta L = \frac { V _ { 1 } \cdot \Delta V \cdot Q ( L _ { 1 } ^ { ' } - Q \cdot L _ { s } ) } { ( V _ { 1 } ^ { 2 } + V _ { 1 } \cdot \Delta V ) ( \rho \cdot V _ { 1 } - Q ) }
$$

在密度不变的情况下，排队长度的改变只和速度有关，故可以通过调节整个路段中的速度进行合理的控制排队长度。

交叉口处的进入车辆分为三个车流方向：左转、右转以及直行，分别表示出每个方向车流的时长，但整个过程中的车流情况仍遵循车辆总数守恒定律，得到式(8)，并且满足下列约束。

$$
Q _ { L } \cdot ( T _ { L } + \Delta T _ { L } ) + Q _ { S } \cdot ( T _ { S } + \Delta T _ { S } ) + Q _ { R } \cdot ( T _ { R } + \Delta T _ { R } ) = Q
$$

s.t.

$$
\Delta T _ { L } + \Delta T _ { S } + \Delta T _ { R } = \Delta T
$$

$$
\overline { { V } } = \frac { 1 } { n } \sum _ { i = 1 } ^ { m } ( V _ { i } + \Delta V )
$$

$$
\rho = \frac { L _ { 1 } ^ { ' } \rho + ( L _ { s } - L _ { 1 } ^ { ' } ) \frac { Q } { V ^ { ' } } } { L _ { s } }
$$

将式(1)(9)\~(11)代入式(8)得到：

$$
\Delta t = \frac { \rho ( L _ { 1 } - \Delta L ) + ( L _ { s } - L _ { 1 } ^ { ' } ) ( V _ { 1 } ^ { ' } + V _ { 2 } ^ { ' } + . . . V _ { m } ^ { ' } ) } { 2 n L _ { s } V ^ { ' } }
$$

整个过程可通过调整相位绿灯的时长，来达到调整排队长度的目的。根据各路口在过去一段时间内的车辆实际到达情况，检测使用协同调整之后的路口的车辆到达情况。在一个周期时间段内，使各个交通路口各方向的各车道，在绿灯结束之前的等待放行车辆最少、等待车辆的延误时间也最小，并优化各路口的各相位时间t1、t2、t3。在交叉路口处，考虑到行人过马路因素，每个相位的最短时间应该设置一个阈值c，每一相位的配时应满足：

$$
\left\{ \begin{array} { l l } { \mathfrak { t } _ { 1 } + \mathfrak { t } _ { 2 } + \mathfrak { t } _ { 3 } = \mathrm { T } } \\ { \mathfrak { c } \leq \mathfrak { t } _ { 1 } \leq \mathrm { T } - 3 \mathrm { c } } \\ { \mathfrak { c } \leq \mathfrak { t } _ { 2 } \leq \mathrm { T } - 3 \mathrm { c } } \\ { \mathfrak { c } \leq \mathfrak { t } _ { 3 } \leq \mathrm { T } - 3 \mathrm { c } } \end{array} \right.
$$

为了使整个过程中的车流密度更加平均化，在上面控制的方法上，进行路径诱导。传统的方法是在数据中心网络设计的传统网络体系结构，由于纯粹的传统网络的分布式控制特点，并不能指定包的整体路径。引入SDN后，可以使用OpenFlow交换机进行实时路径规划，对一些车辆进行诱导，来减缓当前道路上的压力。而大多数的诱导算法采用路网阻抗最小或者行驶距离最小的路径。当前的诱导手段过于单一，从而造成周边道路产生连锁反应。所以，在算法中需采用多种方式来替代不合理的路径，可以加入多种干扰因子。针对司机行驶过程中，对于“最优”路径的选择，即选取道路从使用者角度出发，搜索最实用、最符合出行者出行特点的最优路径。设定目标函数就是行程时间最少、油耗最低以及便于调整在行程途中路线的多目标函数。因此建立了以下道路综合路阻阻抗模型：

$\begin{array} { r } { \mathbf { C } ( \mathbf { k } ) = [ \xi _ { 1 } \mathbf { c } _ { 1 } ( \mathrm { t } ) + \xi _ { 2 } \mathbf { c } _ { 2 } ( \mathrm { k } ) + \xi _ { 3 } \mathbf { c } _ { 3 } ( \mathrm { k } ) + \xi _ { 4 } \mathbf { c } _ { 4 } ( \mathrm { k } ) + \xi _ { 5 } \mathbf { c } _ { 5 } ( \mathrm { k } ) + \xi _ { 6 } w _ { i k } ] } \end{array}$ (14)其中， $\begin{array} { r } { \mathrm { c } _ { 1 } ( t ) \geq 0 \quad \mathrm { ~ , ~ } \qquad \mathrm { c } _ { 2 } ( k ) \geq 0 , \mathrm { c } _ { 3 } ( k ) \geq 0 , \mathrm { c } _ { 4 } ( k ) \geq 0 , \mathrm { ~ } \mathrm { c } _ { 5 } ( k ) \geq 0 } \end{array}$ ，$\xi _ { 1 } + \xi _ { 2 } + \xi _ { 3 } + \xi _ { 4 } + \xi _ { 5 } + \xi _ { 6 } = 1$ 。 $\mathbf { C } ( \mathbf { k } )$ 是路段 $\mathbf { k }$ 在t时间的道路多目标路阻函数值， $\mathbf { c } _ { 1 } ( \mathbf { t } )$ 是路段 $\mathbf { k }$ 在t时间段内的车辆的通行时间，$\xi _ { \mathfrak { l } }$ 是路段 $\mathbf { k }$ 在t时间段内的车辆的通行时间对道路权重的影响因子， $\mathbf { c } _ { 2 } ( k )$ 是路段 $\mathbf { k }$ 的拥挤程度， $\mathbf { c } _ { 3 } ( k )$ 是路段 $\mathbf { k }$ 的道路质量， ${ \bf c } _ { 4 } ( k )$ 是路段 $\mathbf { k }$ 的油耗， $\mathrm { c } _ { 5 } ( k )$ 是路段 $\mathbf { k }$ 的停车次数， $\xi _ { 2 }$ 是道路的拥挤程度的权重系数， $\xi _ { 3 }$ 是道路的拥挤程度的权重系数， $\xi _ { 4 }$ 是道路距离产生的油耗的权重系数， $\xi _ { 5 }$ 是路段k产生的停车次数的权重系数， $\xi _ { 6 }$ 是司机选择路径 $\mathbf { k }$ 的权重系数。不同的驾驶员在实际路径选择中会采用不同的评价指标， $w _ { i k }$ 表示司机在路径诱导过程中的第i位驾驶员对于选取第 $\mathbf { k }$ 条路径的函数值。如式(15)所示。

$$
w _ { i k } = \sum _ { a } \tau _ { 1 } X _ { i k } + \sum _ { b } \tau _ { 2 } U ( Y _ { i k } ) + B _ { i k }
$$

其中，a、b是定量信息编号， $\tau _ { 1 } , \ \tau _ { 2 }$ 为权重系数， $X _ { i \mathbf { k } }$ 表示第i位驾驶员对第 $\mathbf { k }$ 条路径的评估， $U ( Y _ { i \mathrm { k } } )$ 表示将交通中的定性因素(如：天气、司机对于该路径的熟悉度、以往的出行经验等)通过模糊理论转变为定量因素。 $Y _ { i \mathrm { k } }$ 为第i位驾驶员对于第 $\mathbf { k }$ 条路径的定性变量。其中 $\mathbf { B } _ { \mathrm { i k } }$ 取值有两个， $\mathrm { B } _ { \mathrm { i k } } { = } 1$ 表示司机接受被诱导， $\mathrm { B } _ { \mathrm { i k } } { = } 0$ 表示司机不接受诱导。基于以上路阻函数考虑，提出了下面的的车辆路径诱导模型：

$$
\operatorname* { m i n } \mathrm { w _ { k } } ( \mathrm { t } ) { = } [ \omega _ { 1 } ( \frac { d _ { k } } { V ^ { ' } } ) { + } \omega _ { 2 } ( \frac { d _ { k } } { V } ) { + } \omega _ { 3 } ( \frac { T _ { K } } { \mathrm { N D } _ { K } } ) { + } \omega _ { 4 } ( \mathrm { P } _ { K } \mathrm { T } _ { K } ) ]
$$

其中， $\omega _ { 1 } + \omega _ { 2 } + \omega _ { 3 } + \omega _ { 4 } = 1$ ， $\omega _ { \mathrm { l } }$ 是路段的长度引起的时间损失对道路权重的影响因子， $\omega _ { 2 }$ 是路段在时间的车辆通行时间对道路权重的影响因子， $\omega _ { 3 }$ 是车辆在交叉口处避开拥堵路段的时间延误对道路权重的影响因子， $\omega _ { 4 }$ 是交通事故造成的时间延误对道路权重的影响因子， $\boldsymbol { d } _ { k }$ 为路段的长度， $\boldsymbol { V }$ 为车辆的期望行驶速度， $\boldsymbol { V }$ 为路段在时间的车辆通行速度， $T _ { \kappa }$ 为交通事故带来的平均时间延误， $\mathrm { N D } _ { \mathrm { K } }$ 为路段的终节点处连接其他路段的数量， $\mathsf { P } _ { K }$ 为路段发生交通事故的概率。

SDN第二层OpenFlow交换机根据流表执行相应操作，将流控制器信息向下发送。信号控制系统和SDN上层控制器通过数据处理模块中的数据分析，设置采集到的交通流数据所控制的交通灯的参数，并增加每个车流方向的车流量，得到式(17)。

$$
( Q _ { L } + \Delta Q _ { L } ) \cdot ( T _ { L } + \Delta T _ { L } ) + ( Q _ { s } + \Delta Q _ { s } ) \cdot ( T _ { s } + \Delta T _ { s } ) +
$$

$$
( Q _ { R } + \Delta Q _ { R } ) \cdot ( T _ { R } + \Delta T _ { R } ) = Q
$$

s.t.

$$
\Delta Q _ { L } + \Delta Q _ { S } + \Delta Q _ { R } = \Delta Q
$$

将式(1)(10)(11)(12)代入式(12)得到：

$$
\Delta Q = \frac { \rho ( L _ { 1 } - \Delta L ) + Q ( L _ { s } - L _ { 1 } ^ { ' } ) { \sum _ { i = 1 } ^ { m } ( V _ { i } + \Delta V ) } } { n \cdot L _ { s } \cdot V \cdot \Delta t }
$$

该架构下的协同管理以加权平均和函数作为优化准则，将动态限速、路径诱导、信号灯调节等进行统一管理。在调整的过程中，在保证各路段通行和可变速度控制的情况下，还需要保证对其他方向的车流控制到最小，所以应寻求一种控制措施，使对其他方向的目标影响函数最小。这里的目标函数可以选用车辆的最小行程延误或最短行程时间。相位绿灯时间的改变会相对影响对向车流的车流量及行程时间。在交叉口研究中，左转交通流是引起行车延误、引发交通事故的非常重要因素。因此，左转车道的延误是设计的关键所在。所以文中提出的方法以左转相位的对向车道为研究对象，计算该条车道上的延误时间。

$$
\operatorname* { m i n } D _ { T } = \operatorname* { m i n } \frac { 1 } { n } \sum _ { i = 1 } ^ { m } D _ { T i } = \frac { m } { n } ( \Delta t + t _ { q } ) \cdot \frac { Q _ { L } } { Q }
$$

通过计算并比较该过程中的原始车流量和经过调整之后的车流量，如果计算之后，目标函数在可允许接受的范围内，表示当前的调整措施对其他车道的影响是可接受的，也证明了协同控制架构的可行性。

# 4 仿真实验

# 4.1实验设计

实验以保定市七一西路和西二环路路网中心的两个十字路口为研究对象，采用微观交通仿真模拟软件VISSIM。该系统是一个离散的、随机的微观仿真软件，可作为许多交通问题分析的有力工具。基于该仿真平台提供的API接口在Python语言环境下进行实现，将基于该架构的协同控制方法编写成程序脚本。仿真软件向用户提供COM组件，便于用户对仿真模型和数据进行访问。通过COM接口函数vehicle.attvalue获取车辆的速度，vehicle.ID获取车辆的编号，通过signalgroup.attvalue获取信号的相位时间信息，并且可以通过signalgroup对象的Amber、Greened等属性对信号控制参数进行动态优化以及调整，从而实现协同环境下对车辆的控制。

对基于动态限速和信号灯控制的控制方法进行仿真实验，分析相邻交叉口状态以及限速、路径诱导等对于本路口车段的影响。VISSIM软件系统内部由交通仿真器和信号状态发生器两大程序组成，它们之间通过接口来交换检测器的信号状态。交通仿真器包括跟车模型和车道变换模型。信号状态发生器以仿真步长为基础不断从交通仿真器中获取监测信息，决定下一仿真时刻的信号状态，并将该信息传送给交通仿真器。

![](images/50b5529b15a61789976a37160a551ff42f66b98d143f05a451667d2e6f0fefb0.jpg)  
Fig.6VISSIM simulation road network diagram

车道宽度为 $3 . 5 \mathrm { m }$ ，人行横道宽度为 $3 \mathrm { m }$ ，平均车辆长度为 $5 \mathrm { m }$ 。在整个仿真过程中，设计原则如下：令进口道直行方向的车流量为Qs，左转方向的车流量为 $\mathrm { Q _ { L } }$ ，右转方向的车流量为 $\mathrm { Q } _ { \mathrm { R } }$ ，车道数量为n，并根据车流量比分配车道数。在同一相位内放行的两方向所分配的车道数，根据其车流流量比确定，左转和直行至少分配一条车道。信号灯配时分配如下：主路信号灯信号周期为60s，绿灯时间最短为20s，最长50s，黄灯时间为3s，两交叉口相位差为12s。仿真过程中以1/10s的时间间隔记录路网中每辆车的行驶速度、交叉口进口道的排队长度以及信号灯状态等信息。其具体仿真参数设置见下表2。

表2标定参数及取值  
Tab.2Calibration parameters and values  

<html><body><table><tr><td>参数名称</td><td>取值</td></tr><tr><td>仿真精度</td><td>1步/仿真秒</td></tr><tr><td>阻塞密度</td><td>pj=110pcu/h</td></tr><tr><td>仿真总时间</td><td>4600s</td></tr><tr><td>饱和流率</td><td>s=2000pcu/h</td></tr><tr><td>自由流车速</td><td>Vf=72km/h</td></tr><tr><td>加速度</td><td>a=3m/s²</td></tr><tr><td>进口流量</td><td>400-800pcu/h</td></tr><tr><td>其他仿真参数</td><td>VISSIM默认值</td></tr></table></body></html>

将各项参数输入到VISSIM软件中，对比单一控制下的交叉口与协同控制下的交叉口处的延误时间和车辆排队长度等指标，具体以及分析如下。

# 4.2结果分析

通过仿真获取动态限速和信号灯控制下的交通流参数数据，并和当前交通系统中单一控制进行对比，两种控制策略条件下通行交通量和排队长度情况如下。

![](images/f776d9bc4bc65391550f15986047cd81f52581c912c9f2fc0e2a5976a17bb1f1.jpg)  
图7不同交通负载下的车流密度和总延误对比

![](images/3ab2ceef99a8c1939f535393373768eb4b8394123d1e9f339b9bfbffb2ad9443.jpg)  
图6VISSIM仿真路网示意图  
Fig.7Comparison of traffic density and total delay under different traffic loads   
图8不同交通负载下的车流密度和总延误对比  
Fig.8Comparison of travel time under different traffic loads

![](images/f716b0207b15f632585817be9e14ae62b2748f0180898a2a16fe62d77341c59c.jpg)  
图9协同控制效能提升比例

图8显示，当输入车流量为 $3 0 0 \mathrm { v e h / h }$ 时，车辆平均总行程时间减少 $1 9 . 2 1 \%$ ，平均延误减少 $2 0 . 5 6 \%$ ；当输入车流量为 $5 0 0 \mathrm { v e h / h }$ 时，车辆平均总行程时间减少 $2 2 . 4 8 \%$ ，平均延误减少 $2 3 . 4 8 \%$ ；当输入车流量为 $7 0 0 \mathrm { v e h / h }$ 时，车辆平均总行程时间减少 $2 5 . 7 5 \%$ ，平均延误减少 $2 5 . 2 3 \%$ 。随着车流量的增加，车辆平均总行程时间较单一控制呈下降趋势，平均延误时间也比单一控制更低。可以明显看出，输入车流量越靠近中间值协同模型对总行程时间和延误时间的优化效果越明显。总的来说，实验结果表明文中提出的交通控制与交通诱导协同的动态综合系统对减少路网中车辆行程时间和延误时间效果明显。图9表明协同控制下的效能提升比例，在车流量是 $3 0 0 \mathrm { v e h / h }$ 时，平均密度提升 $1 1 . 9 8 \%$ 、总排队长度和总延迟保持一致；在车流量是 $5 0 0 \mathrm { v e h / h }$ 时，平均密度占比提升了 $2 . 0 1 \%$ ，总排队长度减少了 $2 . 4 3 \%$ ，总延迟时间减少了$4 . 3 2 \%$ 。由此可见，该架构相比传统方法，交叉口交通秩序得到较大改观，车辆延误减少，拥挤程度较之前也有了很明显降低。整个过程中的对比情况如表3。

表3交叉口对比参数  
Tab.3 Intersection contrast parameters   

<html><body><table><tr><td>控制方法</td><td>平均延误/s</td><td>平均排队长度/m</td><td>最大排队长度/m</td></tr><tr><td>单一控制</td><td>46.4</td><td>23.8</td><td>51.1</td></tr><tr><td>协同控制</td><td>36.76</td><td>15.45</td><td>39.6</td></tr></table></body></html>

由表3可见，延误情况有大幅改善，平均延误下降了$9 . 6 4 \mathrm { s } ( 2 0 . 7 \% )$ ，平均排队长度缩短了 $8 . 3 5 \mathrm { m } \ ( 3 5 \% )$ ，最大排队长度缩短了 $1 1 . 5 \mathrm { m } ( 2 2 . 5 \% )$ 。仿真结果显示与传统交叉口控制方法相比，车路协同下的交叉口控制系统在降低延误与减小排队长度的方面都有一定的提升，满足总延误最小的车路协同下的交叉口控制系统设计目标。总体情况显示协同控制比单一控制是有效的，又分别选取在瓶颈区的交通流、排队长度做观察，从图10中的数据表明，在模拟时间130s内，与单一控制相比，协同控制的平均交通流增加。当时间 $( \mathrm { t } \geqslant 1 1 5 \mathrm { s } )$ 排队长度最多减少了 $3 3 . 8 9 \%$ 。随着仿真时间的增加，协同控制下的排队长度逐渐既减少，可有效的缓解交通拥堵。

![](images/45f27bc816b68893fc77dd92003722c38f8062c9f7f0ca0cfd34ef7187f2e127.jpg)  
Fig.9Collaborative control efficiency increase proportion

协同控制下交通流量、排队长度、行程时间均随着仿真时间的增加逐渐趋于最优。图11显示，在仿真时间为70s时，交通流量和行程时间较为接近，但文中的协同控制在排队长度上比单一控制方法减少 $3 7 . 8 \%$ 。随着仿真时间和交通流的增加，两种控制方法的排队长度指标差异逐渐增大。当仿真时间增加到130s时，与单一控制方法相比，文中的协同控制的交通流量增加 $3 8 . 5 \%$ ，行程时间减少 $34 . 6 \%$ 。总体而言，SDN的协同控制相对于传统的交通管理，是很有效的。

# 5 结束语

分析了现有的交通控制系统存在的不足，并结合实际情况对交叉口路段的车辆的排队长度以及速度进行分析和计算，建立了基于 SDN的智能交通系统的控制方法和模型，并运用VISSIM软件进行了仿真实验。研究表明，该架构下的控制系统相较于单一的控制系统，可以使交叉口的平均延误降低 $20 . 7 \%$ ，平均排队长度下降 $3 5 \%$ ，最大排队长度缩短了$3 8 . 1 \%$ 。即采用文中的系统，在降低行车延误、排队长度、提高交叉路口服务水平方面均优于单一控制系统。但是，由于时间和研究水平的限制，也存在很多不足。对于该架构下的仿真实验，只选取了部分路口，没有对所存在问题的交叉口进行交通调查、微观仿真评价，未考虑紧急救援车辆的信号优先设置问题，这些将在下一步的工作中进行。

![](images/2ad467c92230923288b7eb5b39054c00ce570a83392a3f12a1ff9945ac40d5ae.jpg)  
图10两种控制策略下瓶颈区域通行交通量及排队长度的对比 Fig.10Comparison of traffic volume and queue length in botleneck area under two control strategies   
图11两种控制策略下瓶颈区行程时间对比  
Fig.11Comparison of travel time in botleneck area under two control strategies

# 参考文献：

[1]Ferdowsi A,Challita U,Saad W.Deep Learning for Reliable Mobile Edge Analytics in Intelligent Transportation Systems:An Overview [J]. IEEE Vehicular Technology Magazine,2019,14(1):62-70.   
[2]Rafiq G,Talha B,Patzold M,et al.What's New in Intelligent Transportation Systems?An Overview of European Projectsand Initiatives[J].IEEE Vehicular Technology Magazine,2013,8(4): 45-69.   
[3]Adel A,Ahmed.An effective handover management based on SINR and software-defined network over urban vehicular ad hoc networks [J]. Transactions on Emerging Telecommunications Technologies,2019,30 (12).   
[4]Muhammad Sohail,Liangmin Wang,Rashid Ali,et al.Efficient data handover and intelligent information assessment in software-defined vehicular social networks [J].IET Intelligent Transport Systems,2019, 13 (12).   
[5]Albert Rego,Sandra Sendra,Jaime Lloret,et al.Dynamic metric OSPFbased routing protocol for Software Defined Networks [J].Cluster Computing,2019,22(3).   
[6]Charalampou Paris,Sykas Efstathios D.An SDN Focused Approach for Energy Aware Traffic Engineering in Data Centers [J]. Sensors (Basel, Switzerland),2019,19 (18).   
[7]金良，周武，任冬冬.SDN 技术在智慧城市建设中的应用[J]．电子 技术与软件工程,2018 (21):8.(Jin Liang,Zhou Wu,Ren Dongdong. The application of SDN technology in the construction of smart cities [J]. Electronic Technology and Software Engineering,2018 (21): 8)   
[8]宫法明，李世宝，刘建航．基于 SDN的动态资源分配算法 [J]．吉林 大学学报（理学版），2015,53(06):1236-1240.(Gong Faming,Li Shibao,Liu Jianhang. Dynamic resource allcation algorithm based on SDN[J].Journal of Jilin University (Natural Science Edition),2015,53 (06): 1236-1240.)   
[9]刘惠文，姚海鹏，张培颖．基于软件定义网络技术实现人工智能网 络体系架构[J].信息技术与网络安全，2018,37(02):7-10.(Liu Huiwen，Yao Haipeng，Zhang Peiying.Realization of artificial intellgence network architecture based on software-defined network technology[J].Information Technology and Network Security,2018,37 (02): 7-10.)   
[10] Jitendra Bhatia,Ridham Dave,Heta Bhayani,et al. SDN-based real-time urbantrafficanalysis in VANET environment [J].Computer Communications,2019 (2):162-175.   
[11] Marzoug R,Tellez B C,Tellez M C,et al.Optimization of traffic intersection using connected vehicles [J]. International Journal of Modern Physics C,2019,30 (6).   
[12] ZHANG H,GUO X.SDN-based load balancing strategy for server cluster [Cl//IEEE the 3rd International Conference on Cloud Computing and Intelligence Systems (ICCIS) .2015: 662-667.   
[13] PANG J,XU G,FU X.SDN-based data center networking with collaboration of multipath TCP and segment routing [J].IEEE Access, 2017 (5): 9764-9773.   
[14] Raul Munoz,Ricard Vilalta,Ramon Casellas,et al. SDN orchestration and virtualization of heterogeneous multi-domain and multi-layer transport networks: The STRAUSS approach [C]// IEEE International Black Sea Conference on Communications & Networking.IEEE,2015.   
[15]刘文贵，卞宇翔，冯宝，等.SDN关键技术及其在电力通信网的应用 [J]．信息通信技术与政策，2019(12):35-40.(LiuWengui,Bian Yuxiang,Feng Bao,et al. SDN key technology and its application in power communication network [J]． Information Communication Technology and Policy,2019 (12): 35-40.)   
[16] ZHANG H,GUO X.SDN-based load balancing strategy for server cluster [C]/ IEEE the 3rd International Conference on Cloud Computing and Intelligence Systems (ICCIS) .2015: 662-667.   
[17] Goto Y,Masuyama H,Ng B,et al.Queueing Analysis of Software Defined Network with Realistic OpenFlow-Based Switch Model [C]// IEEE International Symposium on Modeling.IEEE,2016.   
[18] Gabriel,Rafael Marin,Fernando.Towards a standard SDN-based IPsec management framework [J].Computer Standards &amp;Interfaces, 2019,66.   
[19] Evgeni Magid,Roman Lavrenov,Ilya Afanasyev. Voronoi-based trajectory optimization for UGV path planning [C]// International Conference on Mechanical.IEEE,2017.   
[20] Latip N B A,Omar R,Debnath S K.Optimal Path Planning using Equilateral Spaces Oriented Visibility Graph Method [J].International Journal of Electrical & Computer Engineering,2017,7(6):3046-3051.   
[21] Kaur K,Garg S,Aujla G S,et al.Edge Computing in the Industrial Internet of Things Environment: Software-Defined-Networks-Based Edge-Cloud Interplay[J]. IEEE Communications Magazine,2018,56 (2): 44-51.   
[22] Yoonseon Han,Jian Li,Jae Yoon Chung,et al. SAVE:Energy-aware Virtual Data Center embedding and Trafic Engineering using SDN [C]// 1st IEEE Conference on Network Softwarization (NetSoft 2O15).IEEE, 2015.   
[23] Sun Li-Lu,Liu Dan,Chen Tian,et al.Analysis on the accident casualties influenced by several economic factors based on the traffic-related data in China from 2004 to 2016 [J]. Chinese journal of traumatology 2019, 22 (2): 75-79.   
[24] Murphy Evelyn.Leveraging the broad powers oflegislators to accelerate action to reduce road traffic casualties [J]. International journal of injury control and safety promotion,2019,26 (2):192-193.