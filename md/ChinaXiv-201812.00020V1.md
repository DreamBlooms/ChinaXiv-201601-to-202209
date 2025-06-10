# 基于ZeroMQ的观测控制系统底层通信架构分析与测试

钱进1，邓辉1,2\*，梅盈2.3，石聪明'，卫守林1，戴伟'，王锋1,2,3(1 昆明理工大学云南省计算机技术应用重点实验室，云南 昆明 650500;2广州大学 天体物理中心，广东广州510006；3中国科学院云南天文台，云南 昆明650011)

摘要：观测控制系统(Observation Control System，OCS)是当前的一个研究热点，底层通信是OCS架构中重要的一个环节。但传统的OCS中一般采用裸套接技术实现，缺少统一的传输控制机制，在密集数据通信时经常存在延迟影响实时控制的需要；同时缺少广播与组播机制，限制了OCS系统的设计。本文针对OCS的要求，系统研究分析了基于ZeroMQ不同通信模型及所对应的天文控制模式，对不同的通信控制架构可用性进行了分析。在此基础上通过实验对相应的通信模型进行了测试，验证其在天文仪器分布控制中的可用性。测试结果进一步说明ZeroMQ构建OCS的底层通信架构是可行的，能够满足OCS对设备的各种控制需求。

中图分类号：TP393文献标识码：A 文章编号：1672-7673(2017)xX-XXXX-XX

# 1前言

随着当前天文观测技术的不断提升，观测设备功能的不断增强，对控制要求越来越高，传统基人工的观测模式变得日益困难，对观测控制系统(OCS)[的需求日显突出。参考国外先进望远镜自动化与智能化的建设经验，研究并实现一套高效、具有良好扩展性的OCS，无疑对下一代天文望远镜的研制具有十分重要的意义。

通常天文望远镜由多个系统构成，如圆顶、赤道仪(机架)、光谱仪和CCD 终端等。OCS需要同时对多种类型的设备进行协同控制，各设备间彼此保持通信。在整个观测过程中往往需要考虑时序控制、异常恢复等通信问题，良好的底层通信架构是整个望远镜控制系统设计的核心。

国内外目前的观测控制系统，无论是经典的ACS还是开源的RTS2[2-3]都采用分布式的控制原理。特别是运用广泛的RTS2，使用了原生Socket[4]套接字编程，每个客户端同时与多个终端维持通信关系，底层通信结构呈复杂的网状，非常不利于系统的开发和实现。此外，在实际观测中OCS 时常需要同步控制多种设备。比如，CCD 的组合观测和同步曝光等[5]。RTS2只能通过循环的方式，依次向多个设备发送命令，这会产生很大的通信延迟，且易出现消息丢失等情况。因此，基于裸套接技术开发观测控制系统太过于复杂，不利于系统的设计与维护。也有其它观测控制系统采用HTTP，CORBA，DCOM等相关协议，这些协议和技术都体现出不同层面的局限性[6，不能完全满足望远镜控制系统底层通信中多种通信模型的需求。

近年来消息中间件技术不断涌现，特别是以 ZeroMQ[7]为代表的消息中间件技术，能够为分布式环境中协同控制提供良好的技术支撑。更重要的是 ZMQ支持多种通信模式，并可通过灵活组合使用基础模式扩展应对不同控制场景，实现单点对单点(1:1)，单点对多点(1:N)的通信，满足OCS中多种通信模型的需求。是否可以在天文观测控制系统的设计与实现中采用 ZeroMQ等新技术成为一个共同关注的问题。

# 2ZeroMQ可用性分析

# 2.1通信模式分析

ZeroMQ有2个重要的通信模式，即请求应答模式与发布/订阅模式[8]，结合天文观测控制系统的需要，这两个模式在实现底层通信模式中，结合不同的控制需求，可以灵活地使用来满足天文设备的控制需求，具体讨论如下。

# 2.1.1请求应答模式

点对点控制模式是一种基于链路连接的模式。单个消息发送方直接与单个接收方相连，采用一问一答的方式建立通信。点对点的控制模式在实际观测中运用较广，例如圆顶(DOME)的开关控制、赤道仪移动操作等都是点对点的控制。

请求/应答是点对点直接通信的模式。消息发送方与接受方通过(Request-Reply)套接字对，采用一问一答的方式实现消息的收发。其主要特点有：1)面向连接的通信。发送方先要与接收方建立直接的通信，才能完成后续的消息传输。2)发送方和接收方紧密耦合。双方必须同时处于运行状态才能传递消息，在时间上是紧耦合；双方必须事先知道彼此地址信息，在空间上是紧耦合。该模式的最大优点就是实现简单且传输可靠，其缺点是系统通信灵活性受到较大限制，每当接收方发生变化，发送方的应用程序都必须做出相应改变[9]。

# 2.1.2发布/订阅模式

点对多点控制模式是一种广播或多播的通信模式。消息发送方与多个接收方建立通讯，单个发送方可以同时控制多个接收方。ZeroMQ中的发布/订阅是一对多的消息广播模式，适合望远镜观测中多台CCD同时曝光或组合观测的点对多点的控制场合。

该模式采用(Publish-Subscribe)套接字对实现，PUB 端只需要将消息封装到主题中发布，SUB端根据预约主题获取发布的内容。其主要特点：1)发布方和订阅方通过共同主题进行通信，双方不需要建立直接的链接通道。2)发布方与订阅方松耦合。双方不需要知道彼此的地址，所以在空间上是独立的；双方不需要都处于运行状态，因而在时间上是独立的；消息产生与消耗不发生阻塞，因此在流程上也是独立的；3)能够支持点对点、点对多点和多点对多点的通信方式。该模式的主要优点是实现了发布端和订阅端之间的松耦合，其致命的缺陷是发布端单向分发数据，且不关心是否把全部信息发送给订阅端，消息容易丢失。

# 2.2可靠性分析

在复杂多变的天文观测控制环境中，发送方与接收方的状态和行为是不可预测的。OCS在实际的运行过程中可能因网络中断或软硬件故障等问题，导致消息丢失，直接影响天文观测。为了进一步提高OCS消息传输的可靠性，需要从消息的发送方和接收方两个方面共同保障程序发生故障后顺利运行。

项目组针对可靠性问题进行了大量的实验，认为ZMQ为避免消息端发生单点故障，套接字设计将采用 ZMQ双子星模式[10]，任一时刻，某个节点会充当主机，接收所有客户端和设备端的连接请求，另一个节点则作为一种备用机存在。两个节点会互相维持心跳机制监测彼此，主机将通过PUB套接字定时将设备的连接信息发送到备用机，当主机从网络中消失，备用机则会立刻顶替其主机的位置。望远镜系统中设备终端是接收消息的核心部件，当设备出现通信异常中断或通信延迟超过最大峰值时，设备端将会首先采用ZMQ超时重传，逐条轮询的方式再次判读每个设备的在线情况。为了使消息不致丢失，设备端经短暂恢复后就需实现断点续传功能[]。断点续传就是当设备在消息传递过程中出现中断，待设备在短时间内恢复连接后能够继续完成传输任务，保障消息不丢失的模式[12]。该功能主要通过ZMQ克隆模式来实现，使用PUB-SUB套接字作为核心消息模式。当系统收到设备反馈的连接异常状态消息后，将调用ZMQ多帧消息类，将消息前加上时间戳标记暂存，设备从故障中恢复通信并立刻通过REQ套接字获取当前状态，根据暂存消息时间戳与当前状态比较，获取状态之前的所有消息，保障故障恢复后消息传输可靠性。

# 2.3效率分析

在网络通信时，带宽资源总是可能面临的一个问题，在低带宽情况下实现可靠通信是非常可能遇到的局面。在OCS设计中，消息传输的开销与延迟将直接影响系统的整体性能，而消息的长度又是影响通信效率的一个重要因素，特别是观测产生的图像数据，往往具有实时性强、数据量大的特点。从这个方面来看，ZMQ支持实时的数据压缩技术，采用LZ4无损压缩算法，在发送前对数据进行高速压缩，在接收端进行高速解压，最大程度无损的使传输的消息更加轻量化，减少带宽需求，这对于天文观测是非常有益的。

同时，具有一个高效的消息通信模式也是提高传输效率的重要保障，图像数据经 ZMQ请求应答套接字实现单点高效的传输，控制指令可采用单独端口的广播套接字实现对多个设备的有效控制，节点上可采用多线程技术，提高了消息传输与处理的并发度，降低了因点对点依次向不同设备转发控制命令所产生的传输延迟，基于以上方法能够有效保障OCS 底层通信消息传输的高效性。

# 30CS的控制模式与实测

# 3.10CS的基本架构

图1是项目组在开发新一代观测控制系统时采用的OCS体系架构，OCS处于控制的最顶层，分别由调度子系统、管理子系统、用户交互子系统以及状态记录系统四个部分组成。OCS 与其他子系统都采用接口调用的方式进行交互，通过指挥望远镜控制系统(TCS)，设备控制系统(ICS)和实时数据处理系统(DHS)等对下一级各终端设备进行控制，显然，要实现一套可靠的OCS，底层通信的可用性以及可靠性是成功的关键。

从底层通信模式来看，点对点和点对多点的模式已经可以满足OCS的设计要求。但关键的问题是，这两个模式在通信过程中的可靠性、传输时延、多任务传输性能能否适用实际通信要求就成为关键因素。

![](images/cdfd52b0340a981e5b63bd9b161af96e4bf734dabd953ebb41ab89452fb185da.jpg)  
图1OCS体系架构图  
Fig.1 The architecture diagram of observation control system

# 3.2ZeroMQ在控制中的可用性测试

# 3.2.1环境

实验环境使用5台服务器，每台服务器的配置相同，都配置了千兆网卡，其中一台服务器作为发送端，其他服务器作为接收端，服务器主要配置如表1所示，以下测试实验均在该环境下进行。

表1实验环境 Tab.1Experimental hardware environment   

<html><body><table><tr><td>参数</td><td>取值</td></tr><tr><td>操作系统</td><td>CentOS Linux release 7.3.1611</td></tr><tr><td>CPU</td><td>Intel(R)Xe0n(R)CPUE5-2620v2@2.10GHz</td></tr><tr><td>内存</td><td>64G</td></tr><tr><td>ZeroMQ版本</td><td>4.2.3</td></tr><tr><td>网卡</td><td>1.0 Gbps</td></tr></table></body></html>

# 3.2.2时延测试

各设备接收命令的通信时延是衡量系统通信性能的重要指标，因此我们对ZMQ在相同环境下传输不同长度消息的通信时延进行了对比测试。测试一：模拟OCS实现点对点的控制场景，发送方运行于一台服务器，接收方运行于另一台服务器。测试方法是使用REQ-REP套接字，发送一个特定大小的消息从一台服务器到另一台服务器。我们分别测试了一万条大小分别为256字节与1024字节的控制消息，比较了每一条消息发送与接收的时间差，测试结果如图4所示。由测试结果可见，连接初期传输延迟较高，而后趋于稳定，偶尔也会出现峰值的情况，且均在合理范围内。当数据大小由256字节增加到1024字节时，延迟也会相应增加，但通信延迟总体表现较小，能够适用于OCS控制圆顶或望远镜等设备点对点的控

制环境。

![](images/f4e91fa6c536739cc056fecb789fa3d8a6c0c0275a0cdf347ccf6143e9e705fd.jpg)  
图2REQ-REP模式消息传输延迟对比图   
Fig.2 Request-Reply mode message transmission delay comparison chart

# 3.2.3多点同步控制性能测试

模拟OCS实现点对多点的控制场景，发送方运行于一台服务器，接收方运行于另外5台服务器。测试方法是发布端使用PUB-SUB套接字发送一万条特定大小为256字节的控制消息，5个接收端根据主题订阅接收消息。我们分别测试了5个订阅端接收消息的延迟情况，测试产生最底层的通信时延结果如图3所示。因每条消息的通信延迟为离散数据，为了更好的掌握各设备的接收性能，我们分别从数据的集中趋势和离散程度两个方面分析各设备接收消息的同步性。如表2所示，Sub1-Sub5分别表示5个设备端，对比分析各组数据，可以得出各设备接收消息平均延迟均在10us以下，延迟波动程度相当，平均延迟远小于标准差。根据实验结果表明，当我们在做OCS高层开发与设计的时候，参考最底层的通信时延数据，需要考虑限制控制指令发送频率，进一步提高控制同步精度。在实际控制中，只要保证在平均延迟 $+ 3$ 倍标准差的时间范围内考虑控制设计，时延水平符合控制精度要求，就足以满足OCS对于多台CCD等设备点对多点的控制场景。

表2实验数据分析Tab.2Experimental data analysis  

<html><body><table><tr><td>Index</td><td>Sub1</td><td>Sub2</td><td>Sub3</td><td>Sub4</td><td>Sub5</td></tr><tr><td>Average Delay /us</td><td>8.0</td><td>6.8</td><td>5.5</td><td>8.8</td><td>7.3</td></tr><tr><td>Standard Deviation /us</td><td>114.8</td><td>101.7</td><td>89.6</td><td>127.0</td><td>97.8</td></tr></table></body></html>

![](images/88a9462ddee5cc887efb9540114ae8ae1eabf7c41dd4e31e09bcef480199f743.jpg)

![](images/56e05562363a678fff78090d32295f46827342ec8a84018341d806e7d6089385.jpg)  
图3PUB-SUB模式消息传输延迟对比图  
Fig.3Publish-Subscribe mode message transmission delay comparison chart

# 3.2.3多通道传输可用性测试

在天文观测中OCS 经常会出现与实时数据处理系统(DHS)之间的交互，DHS会将观测数据实时处理结果反馈给OCS 做观测调度决策，OCS 会将控制命令高速传递给DHS 或其他子系统，在RTS2中，通常是采用多套接字来实现的。

我们设计了一个实验来进一步探究OCS在密集数据通信环境下，实现点对点和点对多点控制的可用性。发送方将生成的单个图像大小为4MB的数据，先转换为二进制的数据流，再以消息的形式封装好，通过请求应答模式传递400MB大小的数据到接收端服务器，模拟OCS与DHS之间传输大量图像数据的密集通信环境。

测试方法如下：1）与传输图像程序同时运行，新建通信端口分别采用REQ-REP 和PUB-SUB套接字对将生成的单个控制消息大小为256字节的数据包，持续不断从一台服务器向其他服务器发送消息。2)当400M图像数据传输完成时，记录图像传输所需时间，并将传输控制消息的程序立即停止。3)记录在图像传输时间内两种不同模式，控制消息的通信时延，发送消息数与接收消息数。测试结果如表3所示。

表3多通道传输测试数据Tab.3 Multi-channel transmission test data  

<html><body><table><tr><td>模式</td><td>图像传输时间</td><td>发送消息数</td><td>接收消息数</td><td>控制消息时延均值</td></tr><tr><td>REQ-REP</td><td>7.3s</td><td>41243</td><td>41243</td><td>267.0us</td></tr><tr><td>PUB-SUB</td><td>7.3s</td><td>106689</td><td>106689</td><td>62.1us</td></tr></table></body></html>

由表3可知，400MB大小的图像数据可以在7.3s完成传输任务，55Mb/s的传输速率也足够满足大量图像数据的高速传输。同时，分别采用 ZMQ中REQ-REP和PUB-SUB 套接字对实现控制命令实时同传。结果表明，采用以上两种模式均能实现消息发送与接收的不丢包，能够保证控制命令传输的可靠性。对比单独发送传输控制命令的场景，两种模式虽受密集数据通信下网络带宽与通信延迟等影响，总体传输速率会有所降低，但传输性能较采用传统 Socket通信更高效稳定，足够满足控制命令实时稳定的传输。通过多次反复的测试，其结果表明采用ZMQ实现多任务多通道传输是可行的，其数据传输方式、传输速率、传输稳定性等都能满足OCS底层通信相关指标要求。不仅能够实现数据在OCS与DHS之间传输，还能够实现各终端之间信息交互和各子系统之间的互联互控，解决当前天文望远镜各终端与各子系统彼此独立，无法协调工作的关键问题。

# 4 讨论与结论

本文先后讨论了ZMQ现有通信模式的优缺点，分析了OCS主要天文控制模式，研究提出了基于ZeroMQ的不同通信控制架构，为解决通信延迟、异常恢复等通信问题提供了相关参考方法。经测试结果分析，使用ZMQ技术构建OCS底层通信架构是可行的，能够满足点对点、点对多点通信控制的需求，能够解决底层通信中普遍存在的开销大、延迟高等问题，非常适合天文望远镜观测控制这样分布式、低延迟要求的场合。

项目组将在后续工作中设计实现一套基于混合通信模式的观测控制系统为目标，以及实现驱动望远镜所有终端设备完成实际观测控制操作。

致谢：衷心感谢国家重点研发计划(2018YFA0404603，2016YFE0100300)，国家自然科学基金委员会-中国科学院天文联合基金资助重点项目(U1831204)，国家自然科学基金委员会-中国科学院天文联合基金资助项目(U1531132,U1631129)，国家自然科学基金资助项目(No.11403009，11463003，11773012)，广州大学“创新强校工程”项目(2017KZDXM062)，云南省应用基础研究项目(2017FB001)，赛尔网络下一代互联网技术创新项目(No.NGII20170204)的资助。感谢国家天文台-阿里云天文大数据联合研究中心对本项工作的支持。

# 参考文献：

[1]赵永恒．LAMOST观测控制系统[J]．天体物理学报，2000(B12):89-95.Zhao,Yongheng.The observation controlsystem of LAMOST[J].Acta Astrophysical Sinica,20o0,(B12):89-95  
[2]Kubanek P.RTS2 - the Remote Telescope System[J].Advances in Astronomy,2010,2010:9.  
[3]KubanekP,JelinekMFrenchJ,etal.The2protocolC/AdvancedSoftwareandControlforAstronoyIItetioal  
Society for Optics and Photonics,2008:70192S-70192S-12.  
[4]卫守林．分布式天文海量数据处理与控制研究[D]．中国科学院大学(中国科学院云南天文台)，2017.Wei,Shoulin.Rearchon theKey TechnologiesofDistributedComputing and Controlfor Astronomy[D].Universityof Chinese  
Academy of Sciences(Yunnan Observatory of Chinese Academy of Science),2017  
[5］罗阿理，田园，宋静,等.LAMOST观测控制系统设计与实现[J]．科研信息化技术与应用,2012,3(4):76-85.Luo A-li,Tian Yuan,Song Jing,etal.DesignandImplementationofLAMOSTObservatoryControl System[J].e-Science  
Technology & Application,20i2,3(4):76-85  
[6]邓辉，钟文杰，付映雪,等．基于 ZeroMQ的新一代望远镜自动控制系统的通信框架设计[J]．天文研究与技术，2018(3).Deng Hui,Zhong Wenjie,FuYingxueetal.Thedesignofcommunication frameworkforanewgenerationoftelescopeautonomous  
control system based on ZeroMQ[J].Astronomical Research & Technology,2018(3).  
[7]Hintjens P. ZeroMQ: Messaging for Many Applications[J]. Oreilly Media,2013.  
[8]蒲凤平，陈建政．基于 ZeroMQ 的分布式系统[J]．电子测试，2012(7):24-29.PuFengping,Chen Jianzheng.Distributed system based on ZeroMQ[J].Electronic Test,2012(7):24-29.  
[9］潘慧芳，周兴社，杨刚．基于混合通信模式的消息中间件设计与实现[J]．计算机工程，2006,32(3):116-118.PanHuifang,Zhou Xingshe,Yang Gang.Designand ImplementationofMessaging Middleware BasedonHybrid Communication  
Model[J]. Computer Engineering,2006,32(3):116-118  
[10]Hintjens P. ZeroMQ: Messaging for Many Applications[J]. Oreilly Media, 2013.  
[11]陈增强，郭嘉琳，刘忠信,等．具有断点续传功能的文件传输系统的设计与关键技术[J]．计算机工程，2002,28(12):14-16.Chen Zengqiang,GuoJialin,Liu Zhongxin,et,al.DesignandKeyTechnologyoftheFile-transferSystemwiththeFuctionof  
Broken-point Continuingly-transferring[J]. Computer Engineering,2002,28(12): 14-16  
[12]赵一凡．基于 ZeroMQ 消息通信库的空管数据共享交换平台的研究与应用[J]．中国新通信，2016,18(6):50-52.Zhao,Yifan.Traffc controldata sharing basedon ZeroMQmessagecommunicationlibrary exchange platform fortheresearchand  
application[J]. China New Telecommunications,2016,18(6): 50-52

# Analysis and Test of Underlying Communication Architecture of Observation Control System on the basis of ZeroMQ

Qian Jin1，Deng $\mathrm { H u i } ^ { 1 , 2 }$ ，Mei Ying2.3， Shi Congming1，Wei Shoulin1，Dai Wei1，Wang Feng1,2.3 (1 Computer Technology Application Key Lab of Yunnan Province, Kunming University of Science and Technology, Kunming 65o50o,China;2 Center for Astrophysics, Guangzhou University, Guangzhou 51ooo6,China;3 Yunnan Observatories of Chinese Academy of Sciences,Kunming 650011,China)

Abstract:Underlying Communication is an important part of Observation Control System (OCS)architecture,which is a research hotspot nowadays. Nevertheless, the traditional OCS is usually realized through bare connection technology,which lack of unified transmission control mechanism. It leads to delay of dense data communication, affecting the need of real-time control. Simultaneously, the lack of broadcast and multicast mechanism restricts the design of OCS system. According to the requirements of OCS， thispaper systematically analyzes different communication models and corresponding astronomical control modes on the basis of ZeroMQ, and analyzes the availability of different communication control architectures. Based on it, it then test corresponding communication models through a series of experiments， to verify its availability in the distributed control of astronomical instruments.The results further illustrate the feasibility of ZeroMQ in constructing the underlying communication architecture of OCS,which will satisfy various control requirements of OCS for devices.

Key words: Observation Control System (OCS); ZeroMQ; Communication Architecture