# 基于ZeroMQ的新一代望远镜自动控制系统的通信框架设计

邓辉1²，钟文杰¹，付映雪²，王锋1²，卫守林²1广州大学物理与电子工程学院，广东广州5100062昆明理工大学云南省计算机技术应用重点实验室，云南昆明650500

摘要：随着天文技术的进步，天文望远镜系统组件日趋于复杂化，望远镜自动控制系统已成为望远镜进行常规观测的核心组成部分。通常执行一个完整的观测计划需要不同设备之间相互配合，协同工作，因此，具有一个高效的底层通信框架是望远镜自动控制系统成功的关键。ZeroMQ是一个高性能的网络通信程序库，提供了多种基础的通信模型，可用于构建复杂的分布式程序，非常适合天文望远镜观测控制这样的分布式、多种通信模式并存和低延迟要求的场合。回顾了在望远镜控制系统中广泛使用的CORBA，DCOM，原生Socket等网络技术，给出了基于ZeroMQ的新一代望远镜自动控制系统通信框架的总体设计，讨论了套接字设计、消息模型设计、序列化等关键技术的解决方案。

关键词：观测控制系统；消息通信；自主观测；模块化设计；系统框架中图分类号：P111.2；TP393.1 文献标识码：A 文章编号：1672-7673

天文望远镜伴随着观测手段的多样化和制造工艺的提升，以及高精度观测，大视场观测的需求，望远镜的结构正朝着巨型化、智能化的趋势发展，观测设备的功能越来越强，控制也越来越复杂。基于人工来实现操作与控制进行观测越来越困难，自动控制系统已成为望远镜系统中不可缺少的重要部分。

望远镜观测控制系统需要同时对多种类型的设备进行控制，这些不同的设备通常都需要一个前置的计算机连接驱动，由前置计算机向各个观测设备发送指令完成控制，而完成一个观测计划需要这些不同设备之间相互配合，彼此之间需要通信。在这个过程中就涉及多种网络通信模型，如望远镜基座移动操作的点对点的通信，多台CCD同时曝光的点对多点通信。与此同时，在望远镜运行期间，各种设备的增加与升级也是常见的现象，进而导致一系列设备控制、数据采集处理系统升级改造的问题。在系统设计的初始阶段需要考虑多个未知型号终端设备同时工作，并且能随着技术进步和观测要求的变化随时升级更换终端设备的情况。新增的设备又是一个新的网络节点，会涉及设备的注册、同步等通信问题。因此，良好的网络通信架构设计是整个望远镜自动控制系统设计的核心。

本文针对大型望远镜自动控制系统中的数据通信技术需求，讨论使用在分布式计算中广泛应用的 ZeroMQ网络通信库，设计实现高性能、易扩展的望远镜自动控制系统的通信框架。

# 1通信技术

望远镜系统中的各种设备物理上分散部署的特点决定了观测控制系统需要具备分布式控制的能力，目前不管是开源的RTS2，还是国内外大型望远镜的控制系统都采用了分布式的控制原理，主要用到的通信协议包括裸套接（Socket），HTTP，CORBA，DCOM等。这些通信技术在不同阶段发挥了重要作用，但随着通信技术的发展，又都表现出不同的局限性。

RTS2是开源领域中应用广泛的远程望远镜控制系统，支持多种设备的接入和控制，但在大型望远镜控制系统中较少使用。RTS2使用TCP的原始套接字编程，在望远镜系统中，有多种设备，多种服务，通信的终端数目就有多个，同时也支持多客户端的连接，这就需要每个终端要维持它所有的通信关系。每个参与通信的客户端所需维持的连接数量非常庞大，这非常不利于程序的开发和实现。此外，望远镜控制系统中，经常需要同步操作多种设备。比如，多CCD的顺序观测，组合观测，同步曝光。RTS2中一个客户端是同时建立和多个设备的独立的网络连接，这种情况下，只能通过循环的方式，依次向多个设备发送命令。尽管纯文本协议设计小巧，同时通常控制系统中，终端不多，网络负载小，但仍不是严格意义上的广播数据通信方式，不能较好地解决协同控制的问题。

CORBA作为较早的分布式计算和远程对象调用的标准，在天文望远镜控制系统中也广泛使用。ALMA控制系统(ALMA Control System,ACS)就是其中的代表[2]，ACS 支持组建和容器模型的开发。使用CORBA 技术的好处是可以集成不同的开发技术，如JAVA用于控制系统的高层开发， $\mathrm { C } { + } { + }$ 用于底层时间关键开发，Python则用于天文学家查询和分析数据。国内郭守敬望远镜控制系统的底层通信也是基于CORBA开发[3]。

ASCOM是Windows平台下的望远镜观测控制系统，采用微软COM组件编程模式，具有较好的可扩展性。由于其开发周期短、部署容易等特点，ASCOM适合应用在选址望远镜的远程控制系统开发中。丽江的2.4米望远镜基于ASCOM实现了CCD滤光片和圆顶的控制[45]。天文望远镜中的很多设备的驱动及后续的数据处理程序包大都在Linux环境下使用，而ASCOM需要运行在Windows 平台下，这给设备的接入和数据处理系统的带来很大的不便。

消息中间件的迅速发展，为分布式异构环境中信息交互和控制提供了良好的技术支持，其中以 ActiveMQ 和RabbitMQ为代表，面向消息的低耦合特性非常适合分布式设备控制。ActiveMQ需要运行在Java环境中，但客户端可以使用多种语言编写，TNG（Telescopio Nazionale Galileo）的OCS（Observation Control System）网络通信就是基于ActiveMQ实现，支持并发、异步通信模式控制设备，利用 ActiveMQ本身提供的主备模式提高消息中枢系统的高可用性。但在这种架构中，引入了第三方系统，消息中间件的稳定性是系统稳定运行的前提。

计算机软硬件和自动化技术的快速发展，这些协议和技术都体现出不同层面的局限性，不能完全适应观测控制系统的需求。近年来，云计算和分布式计算技术取得长足发展，新的通信技术不断涌现，ZeroMQ因其开源、跨平台、高性能的特点，被广泛应用在分布式数据处理框架中，如流式计算框架 Storm[2，分布式计算框架DALiuGE]。ZeroMQ同样适合在测控系统中使用，如智能楼宇监控]。相对于消息中间件 ActiveMQ和RabbitMQ在部署时需要专门的一个服务器，ZeroMQ只需要在应用程序引用 ZeroMQ程序库，就可完成通信，更重要的是ZeroMQ支持请求回应模型（Request-Reply）、发布订阅模型（Publish-Subscribe）、推拉模型（Push-Pull）、路由分发模型（Router-Dealer）等，并可灵活组合使用这些基础模型构建更复杂的分布式网络通信框架，满足望远镜控制系统通信中多种通信模型的需求。此外，ZeroMQ提供了C， $\mathrm { C } + +$ ，Java，.NET，Python 等多种语言绑定和多种主流操作系统平台的支持，这为望远镜系统中协同控制多种异构设备提供了技术支撑。

# 2系统体系结构

参考ATST的体系结构设计[l]，将望远镜远程控制系统分为观测控制系统（Observation Control System，OCS）、望远镜控制系统（Telescope Control System，TCS）、设备控制系统（Instrument ControlSystem，ICS）、数据处理系统（Data Handling System，DHS）和操作界面（UI），系统结构如图1。

![](images/d0c0561a5ed585b27d390675bd1e1f1af7a630bd950c081e0198ced6bf976bbc.jpg)  
图1望远镜控制系统体系结构图  
Fig.1 The architecture diagram of telescope control system.

观测控制系统是整个系统的核心，包含了观测目标维护、观测计划维护、观测脚本的解析和执行调度等。设备控制系统和望远镜控制系统接收观测控制系统的执行命令，负责对望远镜和望远镜系统中的其他设备（如CCD，DOME）进行直接控制。观测设备产生数据后，向数据处理系统发送数据准备好的信息，数据处理系统启动实时数据处理程序，实时数据处理的结果将能支持观测调度的决策，选择最优的观测目标。各个子系统之间的交互都是采用 ZeroMQ。需要特别说明的是，在观测控制系统中增加了WebServer组件，提供基于HTTP 协议的REST服务和WebSocket，使用WebSocket为用户操作界面（UI）提供实时通信协议。使用通用平台无关的HTTP协议，目的是构建跨平台的页面，支持多种类型的前端编程技术。

# 3关键技术

在早期版本的 ZeroMQ中，应用程序编程接口基于AMQP的交换和队列模型，作者于2009 重写了应用程序编程接口，改用BSD Socket API，降低了应用程序编程接口的学习曲线，方便 ZeroMQ与现有技术的集成。ZeroMQ对象被暴露为“套接字”，因此使用 ZeroMQ编程，首先是套接字的设计；而套接字传输的消息只能是指定长度的二进制数据块，需要定义具体的分布式组件程序能够互相理解的消息模型。ZeroMQ被设计成侧重于消息传输的轻量级消息中间件，缺少消息服务器存储和转发消息，所以不支持消息持久化及崩溃恢复，因此还需要考虑设计相应的高可用机制。

# 3.1套接字设计

ZeroMQ不同程序间通信使用所谓的“套接字”进行交互，这里的套接字与TCP套接字非常相似，主要区别在于 ZeroMQ的套接字可以处理与多个对等点的通信，有点像未绑定的UDP套接字。望远镜控制系统实际上也是对设备的控制，因此设备控制系统和望远镜控制系统的设备都可以抽象到设备层，这里引入了管理组件（Steward），设备和组件之间存在点到点、点到多点、多点对应多点的数据事件驱动的控制与处理需求。同时需要考虑终端实时状态、异常恢复、统一时序控制及可用性探测。观测控制系统接收用户的观测计划，最终将操作指令发送给设备，可将观测控制系统看作望远镜控制系统和设备控制系统的客户端。客户端（Client）需要能够操作设备，接收设备广播的更新信息，但客户端不是直接连接到设备上，而是通过管理组件，因此管理组件需要为客户端创建一个接收请求命令的套接字和广播信息的套接字。对于设备来说，也需要接收来自客户端的命令，以及客户端的广播信息，管理组件也需要为设备创建一个接收请求命令的套接字和广播信息的套接字。如图2为望远镜控制系统和设备控制系统内部的ZeroMQ通信套接字设计。

![](images/2ba0f0764b0bc27dcfbaa12c7e7c1f981f74409169db9e3dad0f8597cb0822da.jpg)  
图2.望远镜控制系统和设备控制系统内部的ZeroMQ通信套接字设计  
Figure 2.The definition of sockets for TCS and ICS based on ZeroMQ.

客户端（Client）使用DEALER类型套接字连接到管理组件（Steward）的专为客户端通信的ROUTER类型的套接字后，会接收来自 Steward的PUB接口的连接信息，再使用 SUB接口订阅广播消息。设备连接到

Steward 专为设备连接的ROUTER类型的套接字，上报设备参数值，定时发送心跳，并获得管理组件的PUB地址和端口，并连接到PUB端接受广播消息。对单个设备的操作，客户端连接到管理组件，查到设备的地址信息，进而发送操作命令，对于多个设备的并发控制，可以通过管理组件的PUB接口广播信息。

# 3.2消息模型

ZMQ支持多帧消息，即在一条消息中保存多个消息帧，这里利用多帧消息，格式化消息实现控制。在ZeroMQ中，套接字默认是瞬时的，它所连接的套接字（如ROUTER）会生成一个UUID标识消息的来源，与之相关联。ROUTER套接字在所有收到的消息前添加消息来源的地址，为了客户端能操作特定的设备，需要一个固定标识。每个设备都有一个固定的名称，在启动时可以通过参数指定，这个名称也作为设备的ROUTER套接字的标识。客户端发送特定命令到设备的消息模型定义如图3。

Figure 3.The message model of commands sent by Client and commands received by Device.

图3中Client_Id为自动生成的唯一标识符，Device_Id为[deviceType] $^ +$ deviceName的组合，如[CCD]Cameral；FromClient和ToDevice表示来源于客户端的命令和发送到设备的命令；Devices 为操作的设备列表，多个设备名使用逗号连接；Command_Group 是对命令进行分类，以便进行对消息的后续处理，详细说明如表1。Steward接收到消息后，解析消息，如果Devices为多个设备，则使用PUB套接字广播消息。

表1.命令消息分类   

<html><body><table><tr><td>命令类别 说明</td><td></td></tr><tr><td>READY</td><td>设备启动，准备工作完成</td></tr><tr><td>REQUEST</td><td>客户端的请求消息</td></tr><tr><td>REPLY</td><td>回复消息</td></tr><tr><td>HEARTBEAT</td><td>心跳信息</td></tr><tr><td>DISCONNECT</td><td>断开</td></tr><tr><td>STEWARD_PORT</td><td>Steward的PUB端口信息</td></tr><tr><td>PUB</td><td>广播消息</td></tr></table></body></html>

设备启动后，向 Steward 发送设备的注册信息（Command_Group 为READY）；接收到客户端的操作指令，执行操作后，向客户端发送执行结果消息（Command_Group 为REPLY）。此外定时向 Steward 发送心跳消息（Command_Group为HEARTBEAT），发送广播信息（Command_Group为PUB），消息模型如图4。

Figure 4. The message model of commands sent by Device and commands received by Client.

# 3.3压缩与序列化

网络通信时，对数据进行压缩，以减少带宽需求，特别是天文台址通常在高海拔，网络带宽资源特别珍贵的情况尤为重要。使用LZ4压缩算法，在发送前对数据进行压缩，在接收端进行解压缩。LZ4属于无损压缩算法，主要特点是高速解压缩，同时支持多种语言的编程接口。ZeroMQ被设计成侧重于消息传输的轻量级消息中间件，缺少消息服务器存储和转发消息，所以不支持消息持久化及崩溃恢复，在编写网络应用程序的时候往往需要将程序的某些数据存储在内存中，然后将其传输到网络中的另一台计算机上以实现通讯。这个将程序数据转化成能被存储并传输的格式的过程被称为“序列化”（Serialization），而它的逆过程则可被称为“反序列化”（Deserialization）。ZeroMQ仅解决网络通路的问题，并不提供序列化的方法，可以将对象强制转换为char\*或者void\*类型的数据，然后进行数据的传输，那么对于每一个类的对象，都要编写不同的代码，工作量很大，通用性不高，同时还注意CPU字节序的问题。因此需要选择合适的序列化库，同时能最小化侵入编程。使用 MsgPack，MsgPack是一个基于二进制的对象序列化库，具有跨语言的特性，同样非常容易使用。操作命令和更新消息通过 MsgPack进行压包，然后写入ZeroMQ的消息结构体（zmq:message_t），通过 ZeroMQ传递，最后接收者利用MsgPack进行解包，从而分析命令，获得数据。

# 4高可用性

从系统的结构可以看出管理组件是整个系统的核心部件，为避免在管理组件上的单点故障，采用了主从热备的机制。设备在失去和管理组件主节点的心跳连接时，转向从节点，任一时间，某个节点会充当主节点，接收所有客户端和设备的连接请求，另一个则作为一种备机存在。主管理组件会定时将设备的连接信息通过PUB套接字广播到其他从管理组件，这样一旦主管理组件失效，客户端连接到从管理组件后依然可以立即获得设备信息。

望远镜系统中的各种设备是控制的核心，因此设备的可用性检测是望远镜控制系统中的关键一环。可用性检测是通过固定时间的检测，判断各终端的可用性，自动移除不能工作的设备，在分布式系统中叫作心跳机制。只在设备和管理组件之间使用了心跳机制，客户端由于只是在操作时进行连接，不需要保持连接，没有使用心跳机制。采用 ZeroMQ编程，在客户端、管理组件和设备中都需要读取多个套接字，主循环中都使用 zmq_poll(非阻塞的读取方式，使用另一个计时器触发心跳。不使用主循环来控制心跳的发送，主要是因为这导致过量地发送心跳（阻塞网络），或是发送得太少（导致节点断开，产生虚假故障）。心跳信息异步的在组件之间传递，任一组件都可以通过它判断对方已经死亡，并中止通信。心跳频率是可以在文件中或启动参数中配置的，并在各个节点上维持一致的频率。

# 5结束语

望远镜观测控制系统是天文望远镜系统的重要组成部分。望远镜实际观测运行中，面临着观测终端设备更新和观测过程逐步复杂的需求。因此研制一套具有高效、良好扩展性的望远镜自动控制系统，以最小的代价快速完成新设备集成与系统升级，能有效地降低观测人员工作难度，提高观测效率。望远镜系统的正常运转离不开多种设备、组件之间相互配合，因此网络通信是观测控制系统的重要底层支撑。本文分析比较了传统天文控制软件中的通信机制如CORBA，DCOM和裸套接(Socket)等技术，研究使用 ZeroMQ实现点到点、点到多点的数据事件驱动的通信，介绍了ZeroMQ的套接字设计，消息模型的设计和压缩与序列化技术，并研究高可用性保障在网络受限和设备故障时系统的正常运行，接下来的工作将以驱动望远镜和实际观测控制为目标，实现观测计划和操作指令的转换和终端设备控制的通信，以及实现基于HTTP协议的观测控制系统和用户界面的接口。

# 参考文献：

[1] Kubanek P, Jelinek M,French J, et al. The RTS2 protocol[C]// Proceedings of SPIE.2008.   
[2]Farris A,Marson R,Kern J.The ALMA telescope control system[C]//10th ICALEPCS Intermational Conferenceon Accelerator & Large Expt.Physics Control Systems.2005.   
[3]王坚,金革,黄鲲,等.LAMOST观测控制系统消息总线的设计和实现 [J].核电子学与探测技术,2006,26(3): 268-271.   
Wang Jian, Jin Ge,Huang Kun, et al. Design and implementation of LAMOST OCS message bus [J]. Nuclear Electronics & Detection Technology, 2006,26(3): 268-271   
[4]和寿圣,范玉峰,王传军.基于 ASCOM标准的CCD 自动观测系统 [J].天文研究与技术一国家天文台台刊, 2013,10(4): 386-391.   
He Shousheng,Fan Yufeng, Wang Chuanjun. An automatic CCD observation system based on the ASCOM standard [J].Astronomical Research&Techonolgy—PublicationsofNational AstronomicalObservatoriesofChina,2013,10(4):386- 391   
[5]和寿圣,辛玉新,伦宝利,等.基于ASCOM和Modbus/TCP 协议的天文圆顶控制系统 [J].天文研究与技术, 2017,14(3): 356-362.   
He Shousheng, Xin Yuxin,Lun Baoli,etal. Astronomical dome control system based on ASCOM and Modbus/TCP standard [J].Astronomical Research & Techonolgy,2017,14(3): 356-362.   
[6] Guerra J,San Juan J,Lodi M,et al. OCS: towards a more effcient telescope[C]// Proceedings of SPIE.2014. [7] Toshniwal A, Taneja S, Shukla A,et al. Storm $@$ twitter[C]//Proceedings of the 2014 ACM SIGMOD International Conference on Management of Data. 2014: 147-156. [8] Wu C,Tobar R, Vinsen K,etal. DALiuGE: a graph execution framework forharnesing the astronomical data deluge [J].Astronomy and Computing, 2017, 20: 1-15.   
[9]叶崧,姚健东.基于 ZeroMQ&JSON 的分布式测控系统消息通信架构设计 [J].现代电子技术,2014(2):105- 109.   
Ye Song, Yao Jiangdong. Design for message communication architecture of distributed measurement and control system [J]. Modern Electronics Technique,2014(2): 105-109.   
[10] Goodrich BD,Wampler SB.Software controls for the ATST Solar Telescope[C]// Proceedings of SPIE.2004: 518-527.

# The Design of Communication Framework for a New Generation of Telescope Autonomous Control System Based on ZeroMQ

Deng Hui1,², Zhong Wenjie',Fu Yingxue²,Wang Feng1,², Wei Shoulin² 1 Center for Astrophysics, Guangzhou University, Guangzhou 510006, China 2 Computer Technology Application Key Lab of Yunnan Province, Kunming University of Science and Technology, Kunming 650500, China

Abstract: With the progress of astronomy and technology, components of astronomical telescope system are becoming more complicated, telescope automatic control system has played acore role in telescope for routine observation. Generally,acomplete observational plan requires different equipment to work coordinately and harmoniously.Therefore,an efficient underlying communication framework is the key to the success of the telescope automatic control system. ZeroMQ is a high-performance network communication library that provides a variety of basic communication models for building complex distributed programs. It ideally meets the requirements for distributed, multi-communication modes and low latency in telescope observation and control system.This paper reviews the network technologies such as CORBA, DCOM and native Socket that were widely used in the telescope control system,and gives the overall design of communication framework for a new generation of telescope automatic control system based on ZeroMQ. We also discusses the design of socket,message model, serialization and other key technology solutions.

Key Words: Observation Control System; Message-based Communication; Autonomous Observation; Modular Design; Framework