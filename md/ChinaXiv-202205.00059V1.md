# 基于网络终端支持的NDN移动性管理机制

李卓1,2,，毛亚春1,3†，罗蓬4，马天祥4，赵建利4(1．天津大学 微电子学院，天津 300072;2.鹏城实验室，广东 深圳 51800;3．天津市成像与感知微电子技术重点实验室，天津 300072;4．国网河北省电力有限公司电力科学研究院，石家庄 050021)

摘要：命名数据网(nameddatanetworking，NDN)作为一种新型的互联网架构，旨在应对日益增长的数据流量。基于其消费者驱动的内容检索模型，NDN 自然地支持消费者移动性。然而生产者移动性仍然是一个具有挑战性的问题，需要额外的机制来提高生产者移动期间的数据可用性。针对该问题，提出一种可扩展的移动管理机制来支持生产者移动性。该机制利用网络终端在基于名称的NDN 转发平面上建立了临时转发路径，并设计了缓存与重传机制支持时延容忍和时延敏感的应用数据流。最后在ndnSIM中建立了一个全面的仿真环境，对所提方案与现有的解决方案进行了评估和比较。仿真结果表明，该机制能够充分支持生产者移动性。当速度为 $3 0 \mathrm { m / s }$ 时，丢包率仅为 $3 . 0 \%$ 平均传输延时为352.1ms。此外，支持生产者移动性所需的额外消耗于对于方案相比降低了 $4 9 . 1 8 \%$ 。

关键词：命名数据网；移动性；转发策略；丢包率；传输延时 中图分类号：TP393.0 doi:10.19734/j.issn.1001-3695.2022.01.0048

Mobility management mechanism based on network terminal supporting in named data networking

Li Zhuo1,2,3,Mao Yachun1,3†, Luo Peng4, Ma Tianxiang4, Zhao Jianli4 (1.School of Microelectronics,Tianjin University，Tianjin30o072,China;2.The Peng Cheng Laboratory，Shenzhen Guangdong5180o,China;3.TheTianjinMicroelectronicsTechnologyKeyLaboratoryofImaging&Perception,ianjin 300072,China;4.ElectricPower Research Institute,HebeiElectricPowerCorporation,Shjizhuang HebeiO501China)

Abstract: Named data networking (NDN)isaband new Internetarchitecture,whichaims tocope withthe increasing growth ofdatatraffic.NDNbrings native support forconsumer mobilityduetoitsreceiver-driven content retrieval model. However, producermobilityis stillachalenging issue,which needsaditional mechanisms to improve thedata availabilityduring the producer's movement.Therefore,this paper proposedascalable mobility-management mechanism,which further extends the stateful forwarding plane ofNDN to support producer mobility.The mechanism builta temporary forwarding path on the name-based NDN forwarding plane through network terminals and designed a bufering and retransmission mechanism to supportbothdelay-tolerantanddelay-sensitive data traffc.Finally,tis papersetupacomprehensivesimulation environment in ndnSIMforthe proposed evaluationand comparisonagainst the existing classesof solutions.The simulationresults show that the proposed can fully support producer mobility in the wireless environment. When the speed is $3 0 ~ \mathrm { m / s }$ ,the packet loss rate is only $3 . 0 \%$ ,and the average transmisson delay is 352.1ms.Additionaly,the additional consumption required to support producer mobility is reduced by $4 9 . 1 8 \%$ compared to the comparison scheme.

Key words: named data networking; mobility; forwarding strategy; packet loss ratio; transmission delay

# 0 引言

随着移动设备数量的快速增长，连接到互联网的移动应用流量也迅速增加。诸如多媒体流量、语音和视频数据等移动数据对于互联网的需求日益增长[1]。移动性已经成为所有通信网络的基本要求。

命名数据网[2](named data networking，NDN)是一种以内容为中心的新型网络。在NDN中，用户更关注内容本身而非内容的位置，同时NDN的无状态连接和身份-位置分离特性潜在地促进了用户的移动性。在NDN中，用户的移动性可以分为消费者移动性和生产者移动性。前者因NDN的消费者驱动的模型可以快速满足需求。而由于路由定位器和内容标识符之间没有分离[3]，如何提升生产者移动性是一项重大挑战。

生产者需要在移动过程中动态更新路由来保持路由一致性，从而接收消费者请求。但是更新全局路由信息会消耗巨大的网络资源，也会导致消费者请求因无法到达生产者新位置而超时丢失，从而造成了长时间的通信中断[4]。此外，在分层命名机制上，许多生产者会使用特定的前缀，生产者的频繁移动会破坏转发信息表(forwarding information base，FIB)使用分层名称结构进行前缀聚合的优势，导致路由表的低聚合度和路由表表项暴增问题。因此需要设计合理的整体解决方案以应对上述问题和挑战。

为了支持命名数据网中消费者与移动生产者的正常通信：移动性管理机制需要解决两个关键问题：动态追踪生产者的位置并保持会话的连续性[1]。当前已经提出了许多技术来解决生产者移动性问题[5]，这些技术可以分为以下五类：基于路由的方法[依赖路由更新来转发NDN中的消费者请求。该

收稿日期：2022-01-27；修回日期：2022-03-25 基金项目：河北省省级科技计划项目(20314301D)；天津市科技计划项目(20JCQNJC01490)；鹏城实验室项目(PCL2021A02)

作者简介：李卓(1984-)，男，副教授，硕导，主要研究方向为未来互联网架构、高性能路由器架构、网络流量工程、命名数据网；毛亚春(996-)，男(通信作者)，河南安阳人，硕士研究生，主要研究方向为命名数据网用户移动性转发管理(ymao@tju.edu.cn)；罗蓬，(1984-)，男，高级工程师，主要研究方向为电力系统自动化、电力物联网技术；马天祥(1986-)，男，高级工程师，主要研究方向为配电网运行分析与配电自动化技术；赵建利(1980-)，女，高级工程师，主要研究方向为智能变电站通信系统、智能信息处理.

方案的潜在挑战是路由表的可扩展性和收敛时间。基于映射的方法[7采用位置-身份分割的思想来实现一个单独的映射。但该方法不适合生产者的频繁移动，同时也不适合延迟敏感的数据流。基于间接点的方法[8通过本地代理来转发兴趣包。缺点是容易造成单点故障和三角路由问题，同时因分组封装降低了内容仓库(Content Store，CS)的利用率。基于主动缓存的方案设计算法使生产者将内容推送到边缘路由器，从而可以降低生产者移动对网络的影响。但对于实时性内容而言，该方法可能引起较高的延迟。基于Trace的方法[9]扩展了NDN的有状态转发平面，在移动生产者和固定服务器(rendezvousserver，RV)之间建立了反向跟踪来维持通信。该方案需要假设生产者数据在一个稳定的RV前缀下发布，同时RV的位置对方案性能的影响至关重要。此外，该方案通过大量的动态信息交换来维护临时转发路径，需要在保持正常通信的同时尽量减小信令消耗。

上述方案虽然可以在一定程度上支持生产者移动性，但是也会带来一些额外的问题。如有些机制的复杂度较高可能会影响网络的可扩展性[10,11,12]或者违反了NDN 范例中的位置独立原则[13,14,15]。此外，有些方案不能很好地支持时延容忍和时延敏感两种数据流量[16,17]。一些方案对消费者请求被丢弃或快速重传的问题关注较少[18,19]。最后，生产者的移动状态的不确定性要求生产者与锚点的通信过程尽可能简化，减小通信复杂度[20.21]。因此，设计移动性管理机制的目标就是在各种系统约束下支持生产者移动性的同时使得成本最小化，减小网络延迟和信令消耗，提高网络通信质量。

针对上述问题，提出了一种基于网络终端支持的移动性管理机制NTMP，该机制利用网络终端在基于内容名称的NDN转发平面上建立了有效转发路径，并设计了CRM-NT机制支持时延容忍和时延敏感的应用数据流。首先，NTMP设计了实时切换通知机制，利用网络终端(Networkterminal，NT)对生产者进行动态跟踪，减小了移动生产者的切换延时和消耗，最小化锚点对方案性能的影响。该通知机制扩展了有状态转发平面，在NDN路由器中创建/更新临时转发表(TemporaryFIB，TeFIB)，建立了生产者新旧位置与网络终端的有效转发路径。最后，NTMP通过缓存与重传机制CRM-NT 实现了消费者请求的缓存与快速重传，使得消费者请求更快地从丢失中恢复。仿真结果表明，在用户性能(例如丢包率，切换延迟、检索时间)和网络成本(例如切换开销，路径延伸)等指标上，NTMP均满足其预先设定的目标，达到或优于现有的对比方案，可以充分支持生产者的移动性。

# 1 NTMP移动性支持方案

为了提高移动环境下命名数据网的通信质量，设计了一种基于网络终端(Networkterminal，NT)支持的移动性管理机制NTMP。NTMP利用网络终端在基于内容名称的NDN转发平面上创建有效转发路径来维持消费者与移动生产者的通信，并设计CRM-NT机制支持时延容忍和时延敏感的应用数据流。本章首先描述了NTMP机制的转发流程，然后对机制中设计模块展开详细叙述，最后证明了方案的合理性和有效性。

# 1.1NTMP模型和基本原理

如图1所示为NTMP机制分析模型，为了实现消费者与移动生产者的正常通信，NTMP机制的整体思路是：生产者在断开网络前和重新接入网络后分别向NT发送包含其内容名称的移动信息，NT则回复相应的数据包。网络路由器根据生产者与NT的信息交互更新自身转发状态，重新转发消费者请求。生产者移动期间，NTMP机制的转发流程如下：

步骤一：producer在移动前通过R1接入网络中，之后向R2 方向移动。producer 与R1 断开前会发送移动兴趣包(MobilityInterest,MI)给 $\mathbf { N T } _ { \circ } \mathbf { M I }$ 中包含了一个特殊标记"M",该标记代表了producer 的断开状态。

步骤二：R1收到MI后会根据MI的名称前缀查询FIB表，并按照FIB条目中匹配的信息将其转发给NT。

步骤三：NT收到MI后会开启缓存功能并回复移动数据包(MobilityData，MD)。MD包含了标记“M"，同时数据段中包含NT的专有名称前缀。

步骤四：R1识别MD中的标记“M”后会建立临时转发表TeFIB，并将MD转发到下游节点。NDN路由器最终将其转发给 producer。

步骤五：在 producer 断开期间，consumer 的兴趣包(interestpacket，Interest)沿着原始路径转发到R1后会根据其TeFIB转发到NT。NT会记录并缓存该Interest。

步骤六：producer 通过R2 重新接入网络后会立即发送一个包含特殊标记“H”的移动兴趣包(HandoverInterest，HI)给NT，标记“H”表示producer的连接状态。HI还用于请求在producer断开期间NT收到的consumer的Interest信息。

步骤七：R2收到HI后会根据HI的名称前缀查询FIB表并转发给NT。

步骤八：NT识别HI中的标记“H”后会释放缓存的Interest并回复移动数据包(HandoverData，HD)。HD 中包含了标记“H”。

步骤九:R1识别HD中的标记"H"后会创建/更新 TeFIB,并将HD 转发给 producer。此外,R1 收到consumer 的Interest后会查询TeFIB/FIB并转发。

步骤十：producer 收到HD 说明临时转发路径已经建立成功。producer 收到consumer 的Interest后会立即发送数据包(data packet，Data)。

步骤十一：R2收到Data后会查询PIT表的条目记录，然后根据匹配的接口信息将其转发到下游节点并最终返回到consumer。

步骤十二：在 producer 与 R2 连接期间，consumer 的Interest会通过新建的转发路径转发到producer的新网络位置，producer 则原路返回Data。

![](images/abdbb0d6fdd3424b8742b5d148390df978fb0679641878a1d4b5f83e0c44cab0.jpg)  
图1NTMP支持机制简单分析模型Fig.1Simple analysis model ofNTMP mechanism

# 1.2NTMP转发算法设计

NTMP以最小化生产者的移动性影响为目标，通过动态更新路由器的转发状态来解决生产者移动性问题。NTMP设计了完整的通知机制，即移动生产者主动向NT汇报自身的移动状态。NDN 路由器利用该机制创建/更新了关于生产者内容的TeFIB表项。此外，设计了缓存与重传机制来实现完整的生产者移动性支持机制。

# 1.2.1通知消息格式

生产者的通知机制使用了特殊的移动兴趣/数据包。他们分别是移动兴趣包MI、HI和他们所对应的移动数据包MD、HD。如图2所示，内容名称字段为消费者所请求数据的名称，该字段包含了/NTPrefix和/RoutingPrefix。/NTPrefix是NT向路由平面公告的自身名称前缀。生产者的移动兴趣包通过/NTPrefix被转发给NT。/RoutingPrefix是移动生产者的内容前缀，NDN路由器建立了该内容前缀的临时转发条目。Tab是所添加的额外字段，用来表示生产者不同的移动状态，该字段的作用将在下一段详细介绍。此外，该特殊兴趣包中设计了SignatureInformation名称组件，这个组件包含了验证生产者签名所必要的信息(例如生产者的ID、公钥的地址等)，使得NT可以验证数据的出处，确保/RoutingPrefix的可靠性。

![](images/078409c5573ae884ff7d81d69650cb0586722265d234377d0ff1e1c74b7ab31b.jpg)  
图2NTMP通知消息格式

生产者的通知消息格式中添加了一个额外字段Tab。根据生产者的移动状态，该字段填充了“M”和“H”两种标记。该字段不改变内容名称，也不会对原本路由产生作用，只会触发NT和NDN路由器的特殊操作：

NT 在收到携带标记“M”的Interest后会记录生产者的断开连接状态以及该Interest的序号，同时触发缓存机制以缓存请求生产者数据的Interest；NT在收到携带“H”标记的Interest后会记录生产者的接入网络状态以及该Interest的序号，并触发重传机制立即释放所缓存的对应名称的Interest。

NDN路由器会识别特殊标记并创建/更新TeFIB表项，根据不同标记，路由器在TeFIB条目中填充不同的接口。在收到携带标记“M”的Data后，路由器会提取Data的传入接口信息和Data中的/RoutingPrefix创建TeFIB条目；收到携带标记“H”的Data后，路由器会提取相应Interest的传入接口信息和Data中的/RoutingPrefix创建TeFIB条目。具体内容将在1.2.2节中详细描述。

# 1.2.2创建/更新临时转发表TeFIB

通过对NT回复的数据包MD/HD进行判断和操作，NDN路由器创建了临时转发表TeFIB。如图3所示，路由器在收到数据包后，首先将其作为一个常规数据包处理，将其与PIT条目进行匹配。如果找到匹配项，则将其转发到下游。接下来路由器会在Data中搜索Tab字段。如果找到标记，则路由器会提取生产者的内容前缀/RoutingPrefix，然后创建/更新TeFIB表项。根据不同的标签，路由器创建不同的TeFIB条目，即TeFIB条目中添加了不同的接口信息。如果Tab字段中是“M”标记，则路由器使用提取的/RoutingPrefix和MD的传入接口来建立TeFIB条目。如果是“H”标记，则使用HI 的传入接口建立TeFIB 条目，HI的传入接口信息记录在PIT表项中。

NDN路由器创建/更新的FIB表称为临时转发表(temporaryFIB,TeFIB)，该TeFIB与路由平面创建的正常FIB表项共存，但是其优先级要比FIB高，同时TeFIB可以随时刷新。TeFIB中设置了计时器，当TeFIB转发条目中的计时器到期后该条目就会被删除，或者通过更新来刷新该计时器。该举措防止了TeFIB中的转发表项急剧增加。

临时转发表的创建/更新过程依赖的是移动生产者和NT之间的经过身份验证的兴趣/数据包交换，即生产者的通知信息 MI、HI和身份验证成功后的数据包 MD、HD。NT会使用签名密钥来验证这类兴趣包的签名来确定生产者的身份，从而保证数据的真实性和可靠性。算法1描述了NTMP机制中TeFIB表的创建/更新过程。设 $p _ { c }$ 表示生产者的内容前缀，$p _ { d }$ 表示数据包的名称前缀。

![](images/e3172c3fa4b8829b391b1362530927e43b143619c67fac2566aaa9a05b5e4abb.jpg)  
Fig.2Notification message format of NTMP   
图3临时转发表的创建/更新  
Fig.3Creation/update of temporary forwarding table

算法1 Creating Temporary Forwarding Paths 输入：AData $D$ with the prefix $p _ { d }$ from interface $M$ 输出：The Data $D$ be sent from interface $N$ a) ifTab $\subset D$ then $/ /$ 检索数据包中的Tab 字段 b) Extract /Content Prefix $p _ { c }$ from $p _ { d }$ //提取生产者的内容名称 c) if $\mathrm { T a b } = { } ^ { \mathfrak { c } } M ^ { \mathfrak { p } }$ then $/ /$ 查询 Tab字段中的标记类型 d) Extract Interface $M / /$ 提取接口 $M$ e) if $\forall p _ { c } \in$ TeFIB then//查找TeFIB f) Update TeFIB Interface and Timer g else h) Create TeFIB entry i) else if $\mathrm { T a b } \mathrm { \Omega } = \mathrm { \Omega } ^ { \alpha } H ^ { \prime \prime }$ then g) Extract Interface $N / /$ 提取接口 $N$ k) if $\forall p _ { c } \in$ TeFIB then 1) Update TeFIB Interface and Timer m) else n) Create TeFIB entry

# 1.2.3缓存与重传机制

NTMP 设计网络终端(Network terminal，NT)来动态跟踪移动生产者[22]。NT 由处于网络边缘的固定节点组成，该节点是随机的用户节点，通过提供公共接口来支持生产者移动性。此外，NTMP设计的CRM-NT机制不会影响用户节点的正常使用，用户节点可以随时接入或断开网络，不影响主机的自主性。用户节点在断开网络前可将当前的服务转移到其他用户节点中。

1)记录与缓存机制

CRM-NT设计了NT的记录与缓存功能。通过移动生产者的动态通知协议，NT会记录生产者的切换状态并回复相应的数据包。NT还提供了数据缓存功能，该功能由生产者的通知协议触发是NT可以在生产者接入网络之前缓存消费者的兴趣包，避免其因超时而被丢弃。具体来说，当NT收到携带标记“M”的通知包MI后会触发以下操作：首先，记录生产者的断开状态；然后，提取生产者的内容名称/RoutingPrefix进行前缀公告；其次，开启缓存功能；最后，回复数据包MD。MD中包含了NT的专有名称前缀，用于区分不同的NT。当NT收到携带标记“H”的通知包HI后，会触发以下操作：首先，记录生产者的接入网络状态；然后，回复数据包HD；最后，NT提取HI中生产者的内容名称，并根据该名称查询是否缓存请求该内容的兴趣包。如果存在，则会释放请求该内容的兴趣包。

2)标记与重传机制

CRM-NT机制设计了一种新的特殊标记“C”来实现兴趣包的快速重传，该标记由NT 添加到其所缓存的消费者兴趣包中。该标记遵循1.2.1节中的设计原则，标记“C”添加到缓存兴趣包的Tab字段中，表明该兴趣包是由NT缓存释放。当NT收到移动生产者的HI，它会查询自身是否缓存了HI中内容前缀的兴趣包。如果存在，则在触发释放机制时会在兴趣包中添加标记"C”。NDN路由器在处理带有标记"C”的兴趣包时，会在PIT表项中记录兴趣包的传入接口并直接转发。具体检索过程如图4所示。

![](images/f2c8e806416da11bc473d4812e48af17bfd498f9329c27bb0df9fb6d371a171d.jpg)  
图4缓存兴趣包的检索过程  
Fig.4Retrieval process of cached interest package

标记“C”使得消费者的兴趣包在路由器中的检索过程与正常的检索过程不同。如图4所示，NDN路由器在收到一个兴趣包后，首先会根据其内容名称查询CS中是否存在匹配的数据。如果在CS中未找到则转发到下游，路由器继续查找PIT表。如果在PIT中发现了匹配项，路由器会把兴趣包的传入接口信息添加到PIT表项的接口列表中。然后，路由器会查询兴趣包中是否包含“C”标记。如果存在该标记，则按照名称匹配在TeFIB/FIB中进行查找并转发。

通过标记“C”，路由器可以实现缓存兴趣包的强制转发，解决了NT缓存的兴趣包在路由器中因存在PIT表项而丢弃的问题。算法2详细描述了NTMP机制中消费者请求的转发策略。设 $p _ { I }$ 表示消费者兴趣包的名称前缀，用于请求生产者的数据。

算法2Forwarding Strategy for Consumer Interests ( $\dot { I }$ withprefix $p _ { I }$ ）输入：An Interest $\boldsymbol { \tau }$ with the prefix $p _ { \bar { { \tau } } }$ from a neighbor $c$ 输出：A Data $D$ be sent back to $c$ （204a）if $\forall p _ { \tau } \in$ PIT then $/ /$ 查询 PTI中的 ${ \cal P } _ { \cal I }$ 前缀条目b) Add PITInterface M//添加接口 $\boldsymbol { \mathscr { M } }$ c） if(Tab $\neq \emptyset$ n( ${ \mathrm { 7 a b } } \ = \ { \cdots } { \mathrm { c } } ^ { , , } .$ ）then/／检索兴趣包的Tab字段d) TeFIB/FIB Longest Prefix Match // 查找TeFIB/FIBe) elsef) Drop Ig） Forwarding ( $\cdot \cdot ,$ Outface：N）//从接口 $N$ 转发兴趣包h) Forwarding（D，Outface：M）/／从接口M返回数据包i) elseg） Add PIT (Entry: $p _ { \bar { { \tau } } }$ ，Interface：M）// 添加PIT条目k) TeFIB/FIB Longest Prefix Match1) Forwarding (I，Outface:N)m） Forwarding (D，Outface:M)

# 1.3NTMP机制合理性分析

本节研究NTMP机制可以保证转发策略的有效性和正确性。首先证明了NTMP机制创建了一条到移动生产者的有效转发路径，然后证明1.2.3节中消费者请求最终会到达移动生产者。

假设 NDN 网络是包含 $V$ 个节点和 $E$ 个链接的图 $\mathrm { G } { = } ( \mathrm { V } ,$ E)。其中，有一个节点nNr作为NT，一个节点 $n _ { M P } ^ { }$ 作为移动生产者，任意一个节点 $n c$ 作为消费者，其余节点 $n \in V$ 作为路由节点。设 $p _ { N T }$ 是路由平面中 $n _ { { I V T } }$ 公告的路由前缀， $p _ { M P }$ 是移动生产者 $n _ { M P } ^ { }$ 的内容前缀。设节点 $n$ 中的FIB 表项的一组信息 $E { = } [ p , n \to h ]$ ， $p$ 表示为FIB表项中的名称前缀，与之对应的下一跳信息 $h$ 。对于两个节点 $m , n$ 以及一组名称前缀 $p$ 设 $f ( p , m  n )$ 表示为 $m , \ n$ 关于 $p$ 的一条转发路径。

定义1一条长度为 $l \left( l > 0 \right)$ 的有效转发路径 $f ( p , m  n )$ 由一系列的 FIB 转发条目 $[ e \imath , e \imath , . . . , e \imath ]$ 组成，其中 $e _ { i } { = } [ p _ { i } , n _ { i } \to$ $h _ { i } ]$ ， $( i { = } 1 , 2 , . . . , l )$ 。

假设 $\forall n \ \in \ V : \exists f ( p _ { N T } , n \longrightarrow n _ { N T } )$ ，且 $\forall n \in V \colon \exists f ( p _ { M P } , n \longrightarrow$ $n _ { M P } ) { = } [ e _ { I } , e _ { \it 2 } , . . . , e _ { p } ]$ 。生产者断开连接前发送移动信息MI，NT会回复数据包MD。生产者重新接入网络后发送移动信息 $\mathrm { H I }$ NT会回复数据包HD。

推论1当生产者收到数据包 $\mathrm { M D } , \exists f ( p _ { M P } , n _ { M P }  n _ { N T } ) .$ 0

证明已知生产者 $n _ { M P } $ 发送的 MI可以沿一条长度 $l _ { I }$ 的转发路径 $f ( p _ { N T } , n _ { M P }  n _ { N T } )$ 到达 $n _ { { N T } }$ 。中间路由器 $n$ 根据nNT返回的数据包MD创建了临时转发表TeFIB，即 $\forall e _ { i } { = } [ p _ { i } , n _ { i } \to$ $h _ { i } ] \ \in \ f ( p _ { N T } , n _ { M P } \to n _ { N T } )$ ， $( i { = } 1 , 2 , . . . , l _ { I } )$ ，都有 $t _ { I ( l - i + 1 ) } { = } [ p _ { M P } , n _ { i } \to$ hi]。因此可得 $f ( p _ { M P } , n _ { M P }  n _ { N T } ) = [ t _ { I } , t _ { 2 } , . . . , t _ { l l } ]$ 。

推论2当生产者收到数据包HD, $\exists f ( p _ { M P } , n _ { N T } \to n _ { M P } ) .$

证明已知生产者 $n _ { M P } ^ { }$ 发送的 HI可以沿一条长度 $l _ { 2 }$ 的转发路径 $f ( p _ { N T } , n _ { M P }  n _ { N T } )$ 到达 $n _ { N T }$ 。中间路由器 $n$ 根据nNT返回的数据包HD创建了临时转发表 TeFIB，即 $\forall e _ { i } { = } [ p _ { i } , n _ { i } \to$ $h _ { i } ] \ \in \ f ( p _ { N T } , n _ { M P } \to n _ { N T } )$ ， $( i { = } 1 , 2 , . . . , l 2 )$ ，都有 $t _ { 2 ( l - i + 1 ) } { = } [ p _ { M P } , h _ { i } \to$ $n _ { i } ]$ 。因此可得 $f ( p _ { M P } , n _ { N T }  n _ { M P } ) = [ t _ { I } , t _ { 2 } , . . . , t _ { l 2 } ]$ 0

命题1当生产者重新接入网络， $\forall n \in V \colon \exists f ( p _ { M P } , n \longrightarrow n _ { M P } ) _ { \circ }$

证明根据假设： $\forall n \in V .$ ，f (pMP, $n  n _ { M P } ) =$ $[ e _ { I } , e _ { 2 } , . . . , e _ { p } ]$ 、推论1： $\exists f ( p _ { M P } , n _ { M P } \longrightarrow n _ { N T } ) = [ t _ { l } , t _ { 2 } , . . . , t _ { l I } ]$ 和推论2： $f ( p _ { M P } , n _ { N T }  n _ { M P } ) = [ t _ { I } , t _ { 2 } , . . . , t _ { l 2 } ] ,$ 0

a)由缓存与重传机制释放的消费者请求，即首先$\exists e _ { p } { = } [ p _ { M P } , n _ { p } \to n _ { o l d } ]$ ， $\exists t _ { p } = [ p _ { M P } , n _ { p } \to n _ { n e w } ] ( e _ { p }$ 和 $t _ { p }$ 分别属于统一节点 $n _ { p }$ 中的 FIB 和 TeFIB 表项)，则f $( p _ { M P } , n _ { C }  n _ { M P } )$ （2$ = [ e _ { l } , e _ { 2 } , . . . , e _ { ( p - l ) } , t _ { l } , t _ { 2 } , . . . , t _ { l l } ]$ ，然后当生产者重新接入网络， $\exists f$ $( p _ { M P } , n _ { N T }  n _ { M P } ) = [ t _ { l } , t _ { 2 } , . . . , t _ { l 2 } ] { } _ { \ l }$ （204号

b)生产者重新接入网络后消费者发送请求，即 $\exists e _ { p } { = } [ p _ { M P }$ $n _ { p }  n _ { o l d } ]$ ， $\exists t _ { p } { = } [ p _ { M P } ,$ $n _ { p }  n _ { n e w } ] ( e _ { p }$ 和 $t _ { l }$ 分别属于统一节点 $n _ { p }$ 中的 FIB 和 TeFIB 表项)，则 $f ( p _ { M P } , n _ { C }  n _ { M P } ) = [ e _ { I } , e _ { 2 } , . . . , e _ { ( p - }$ $\begin{array} { r }  { \mathbf \Lambda } _ { I ) , t _ { I } , t _ { 2 } , . . . , t _ { m } , t _ { n } , t _ { 2 } , . . . , t _ { l 2 } ] ( \mathbf { m } \leq l _ { I } , \mathbf { n } \geq 1 } \end{array}$ 且 $\scriptstyle \mathrm { n = m + 1 }$ )。

# 2 仿真与性能分析

为了评估NTMP 移动性支持机制，通过ndnSIM模拟器[23]实现了完整机制，并对其进行了模拟和仿真。本节首先描述了仿真设置，最后对仿真结果进行了全面分析。

# 2.1仿真设置

如图5所示，用于仿真的基础网络拓扑由 $6 \times 6$ 的网格节点组成，并且使用点对点链路(P2P)相互连接。相邻节点之间的距离为 $1 0 0 \mathrm { m }$ 。其中，每个路由节点同时作为接入点和路由器，即路由节点既可以通过有线链路实现用户通信，也可以通过无线链路接收用户的数据包。在有线链路中，设置其传输速率和时延分别为100Mbps和 $1 0 \mathrm { m s }$ 。在无线链路中，其在5GHz频率上使用了IEEE802.11nWiFi，无线信道采用Minstrel速率自适应[24]和对数距离传播模型加瑞利衰落模型。无线节点(PointofAccess，AP)的传输范围设置为 $5 0 \mathrm { m }$ 。生产者通过AP节点连接到网络中并在不同的接入点间切换。网络各节点之间使用NDN 协议进行通信。最后，内容消费者连接节点6，生产者的初始位置位于节点1，RV或映射服务器与节点16连接，NT连接到节点1。具体仿真参数值如表1所示。

为了评估NTMP机制的性能，设计了一个模拟生产者移动的动态场景。生产者移动规律遵循随机游走移动模式[25]，即生产者会以恒定的速度移动固定的距离后随机改变方向。当进入某一路由节点的通信范围时，生产者会通过该路由节点接入网络。在模拟仿真中，生产者的移动200米后随机改变方向。此外，设置生产者的移动速度为 $3 { \sim } 3 0 ~ \mathrm { m / s }$ ，并针对不同系列速度的移动生产者执行200次仿真测试，分别记录每次运行的数据。最后设置模拟仿真时间为100 秒。在仿真过程中，消费者每秒发送一个兴趣包来检索移动生产者的数据。最后，将NTMP机制与RP[I2]和KITE[8]方案进行了对比，其中RP是基于间接点的方案，KITE是基于Trace的经典方案。

![](images/73f03d1d1b9e574dde918e8192d2e6394e0d7ba3f5dad3255dc007ada36ddb87.jpg)  
图5基础网络仿真拓扑图

表1仿真参数表  
Tab.1Simulation parameter table   

<html><body><table><tr><td>仿真参数项</td><td>仿真参数值</td></tr><tr><td>有线链路带宽/Mbit·s-1</td><td>100</td></tr><tr><td>有线链路时延/ms</td><td>10</td></tr><tr><td>链路层协议</td><td>IEEE 802.11n</td></tr><tr><td>无线速率</td><td>DssRate1Mbps</td></tr><tr><td>无线信号传输范围/m</td><td>50</td></tr><tr><td>传播损耗模型</td><td>瑞利衰落模型</td></tr><tr><td>移动模型</td><td>随机游走模型</td></tr><tr><td>固定移动距离/m</td><td>200</td></tr><tr><td>路由器缓存方式</td><td>Nocache</td></tr><tr><td>兴趣包的发送速率/个·s</td><td>1</td></tr><tr><td>生产者移动速度/m·s1</td><td>3~30</td></tr><tr><td>仿真时间/s</td><td>100</td></tr></table></body></html>

# 2.2性能分析

# 2.2.1丢包率分析

图6描述了各方案在用户发包率为lpps(Packets PerSeconds)时不同移速下的平均丢包率实验结果。从图中可以看出，在 $3 { - } 3 0 \mathrm { m / s }$ 的速度范围内，NTMP的平均丢包率逐渐减小，最后稳定在 $3 \%$ 左右。KITE的丢包率稳定在 $20 \%$ 左右，RP方案的丢包率则随着速度的增加不断上升。从原理上分析，在NTMP中，生产者断开连接后NT会开启缓存服务，用来缓存消费者的兴趣包。此外，当生产者的移动速度较低时，其切换时间较长导致缓存兴趣包的生存时间到期而被丢弃。而其速度较高时，在兴趣包的有效生存时间内，移动生产者已经切换完毕，被NT缓存的兴趣包可以正常转发给生产者，从而降低了丢包率。因此，随着移动生产者速度增加，NTMP的丢包率逐渐降低。对于KITE和RP，因其没有设置缓存功能，且生产者在切换期间不能及时更新其位置信息，使得消费者的兴趣包被转发到生产者的旧网络位置。因此，对比方案KITE 和RP的丢包率比NTMP方案高。综上，NTMP实现了更低的丢包率，相比于KITE和RP分别减小了 $14 . 2 4 \%$ 和 $2 5 . 8 1 \%$ 。

# 2.2.2传输延迟分析

图7展示了各方案在不同移速下的平均传输延时结果。在 $3 { - } 3 0 \mathrm { m / s }$ 速度范围内，随着移动速度增加，方案NTMP的平均传输延时逐渐减小，最后稳定在352.1ms 左右，方案KITE的平均传输延时在 $6 5 0 \mathrm { { m s } }$ ，RP的传输延时随着生产者移速的增加而增加。NTMP的平均传输延时相比于KITE和RP分别减小了 $4 6 . 1 9 \%$ 和 $56 . 1 1 \%$ 。从原理上分析，NTMP设计了CRM-NT机制：首先，通过缓存功能直接减少了消费者请求的重传次数；其次，重新设计了被缓存的兴趣包的转发规则，通过强制转发机制进一步降低了兴趣包的传输延时。在KITE中，消费者请求会被转发到生产者的旧位置而丢弃，消费者需要重传兴趣包来请求生产者数据。在RP中，生产者在高速状态下会进行频繁的切换，因此需要在每次切换向映射服务器更新自身位置信息。此外，消费者在其兴趣包过期后需要重新向映射服务器请求生产者的位置信息。该机制使得消费者获得的生产者移动信息与生产者的移动状态不同步。生产者的移动速度越快，消费者的获得的信息滞后性越大。因此，RP不适合生产者切换频率高的移动环境。综上，NTMP机制可以在生产者高速移动时维护其与消费者的正常通信。

![](images/8bb9b064b2114ccc0a7017833cbcf4dcbfebcff4bd8438fb231bc0a07ecf60fe.jpg)  
Fig.5Infrastructural network simulation topology   
图6平均丢包率实验结果

![](images/9438d1cca6772a63758121f88c3762a6a6d7f495ae34f024becdec16ad70c122.jpg)  
Fig.6Experimental results on average packet loss rate   
图7兴趣包的平均请求延时实验结果  
Fig.7Experimental results on average retrieval delay

为进一步探讨NTMP机制对于生产者移动切换的支持效果，图8和9分别展示了速度为 $1 5 \mathrm { m / s }$ 和 $3 0 \mathrm { m / s }$ 时，各个方案的消费者请求响应率的实验结果。从图8和9可以看出，在100s的仿真时间内，NTMP机制中消费者收到的Data的数量均高于对比方案KITE和RP。此外，从图8和9的局部放大图中可以看出，在移动生产者的单次切换过程中，NTMP机制恢复移动生产者与消费者的正常通信所需时间即消费者发送一个兴趣包到收到对应的数据包所消耗的时间最短，其次是KITE，时间最长的则是RP。综上，相比于方案KITE 和RP，NTMP机制更能支持生产者的移动性。

# 2.2.3切换消耗分析

图10展示了各方案在不同移速下平均切换消耗的结果。从图中可以看出，在 $3 { - } 3 0 \mathrm { m / s }$ 速度范围内，NTMP的切换消耗随着移动速度的增加而逐渐增长，KITE的切换消耗基本稳定在100左右，RP的切换消耗也随着速度的增加而增加，但是增长的幅度要大于NTMP。NTMP的切换消耗相比于KITE和RP分别减少了 $6 5 . 7 \ \%$ 和 $49 . 1 8 \%$ 。从原理上分析，在NTMP中，生产者在每次切换前后会发送两次移动信息来创建/更新路由器的TeFIB。该动态机制保证了转发路径的有效性，并且不需要在连接期间发送移动信息维护TeFIB，减少了额外的流量消耗。此外，更新TeFIB的移动信息中设置了一组序列号来防止陈旧的更新，可以保证TeFIB表项的新鲜度。在KITE中，生产者的内容由一个RV进行前缀公告，生产者与RV之间的“跟踪”需要定期维护，生产者需要定期发送移动信息保持转发路径的有效性。在RP中，除了生产者需要在每次切换时发送位置信息，消费者也需要在请求生产者内容前发送兴趣包到映射服务器，该兴趣包用来获取生产者的位置信息。因此，RP的流量消耗始终要高于NTMP。同时随着生产者切换频率增加，消费者的请求频率也变高。综上，相比于方案KITE和RP，NTMP机制具有更好的切换性能。

![](images/f9e1cd6c15b8393ffb1755ebe4130df71e18df3fd6b594073176d50e86869615.jpg)  
图8速度为15时兴趣包的响应率实验结果

![](images/1a9330e58b326bd2c46e9b689fed326b50d073b042cdd836f146eeee79f78c5d.jpg)  
Fig.8Experimental results of response rate of Interest at speed of15

![](images/76aa7aad2e9739f2b971152070a8d2cc4001b06b61a894a625d8d835c6534e37.jpg)  
图9速度为30时兴趣包的响应率实验结果  
Fig.9Experimental results of response rate of Interest at speed of 30   
图10切换消耗实验结果

Fig.10Experimental results of response rate of Interest at speed of 30 2.2.4路径延伸分析

如图11展示了在 $6 \times 6$ 基础网络拓扑下，消费者的兴趣包在转发过程所需要的平均跳数的实验结果。从图中可以看出，虽然不同速度下的平均跳数略有差异，但整体上NTMP的平均跳数比KITE方案低近 $1 5 . 6 \%$ 。其中，方案RP的平均跳数最低，原因在于RP中的消费者可直接获得生产者最新位置信息，并将请求沿着最短路径转发。NTMP的平均跳数为 7.68\~8.51，KITE 的平均跳数为 $9 . 2 9 \mathrm { \sim } 1 0 . 6 2$ 。从原理上分析，NTMP引入和设计了网络终端节点，利用终端节点的特性设计了移动生产者的切换通知机制。当生产者在网络终端附近移动时，其路径延伸的效果要低于利用RV作为锚点的机制，说明锚点的选择对路径延伸的影响至关重要。此外，NTMP和KITE的特性在于在一定情形下可以使用路径捷径以避免路径延伸的最坏情况。最后，NTMP方案还利用了NT处于网络边缘的优势，在小规模拓扑网络中最小化路径延伸对通信造成的影响。而在大规模网络中，移动生产者也可以选择处于不同网络拓扑位置的最佳NT来减小路径延伸比。

![](images/b6f30167654648383a157284f689e481b09cbdceb994756b3cc3db1e7caa3808.jpg)  
图11平均跳数实验结果  
Fig.l1Experimental results of response rate on average hops

从上述的仿真结果可以看出，随着速度的增加，方案NTMP的性能依然保持稳定，适合频繁的生产者移动切换操作。相比KITE和RP，NTMP机制显著降低了生产者移动引起的丢包、传输延时、切换消耗等性能指标，并优化了路径延伸效果。

# 3 结束语

NDN是未来互联网中很有前景的网络架构，研究NDN网络中的生产者移动性对于完善NDN架构具有极其重要的意义。首先，分析了NDN中生产者移动性存在的问题和挑战以及现存方案的局限性。随后，提出了基于网络终端支持的移动性管理机制NTMP，描述了NTMP机制的原理、架构和转发算法。NTMP机制引入网络终端节点代替传统的服务器节点，并设计切换通知机制来实时追踪生产者，提高了移动生产者的切换通知效率，有效降低网络中临时转发表TeFIB的更新次数，降低了移动切换造成的网络消耗。通过创建临时转发路径，减少了全局路由更新次数，提高了网络中移动内容的可用性。此外，CRM-NT机制改进了缓存兴趣包在路由器中的检索过程，降低了消费者兴趣包的平均传输延时。最后，仿真结果表明，NTMP能够充分支持无线网络环境下的生产者移动性，降低了移动生产者引起的丢包率、检索延迟，同时用于支持生产者移动性所需的额外消耗更少，并且有效降低了路径延伸指标。在性能指标方面均达到或优于对比方案。

# 参考文献：

[1]Fang Chao,Yao Haipeng,Wang Zhuwei,et al.A survey of mobile information-centric networking:Research issues and challenges [J]. IEEE Communications Surveys and Tutorials,2018,20 (3):2353-2371.   
[2]Zhang Lixia,Afanasyev A,Burke J,et al.Named data networking [J]. ACM SIGCOMM Computer Communication Review, 2014,44 (3): 66- 73.   
[3]Tyson G,Sastry N,Cuevas R,et al.A survey of mobility in informationcentric networks [J].Communications of the ACM,2013,56 (12): 90-98.   
[4]王学芹，李双远，史岚，等．自适应的 ICN 移动性机制[J].计算机 应用研究，2020,37(10):3139-3142，3152.(Wang Xueqin，Li Shuangyuan,Shi Lan,et al.Adaptive mechanism to address mobility in ICN[J]. Application Research ofComputers,2020,37(10): 3139-3142, 3152.)   
[5]Hussaini M,Naeem MA,Kim B S,et al. Efficient producer mobility management model in information-centric networking [J].IEEE Access, 2019,7: 42032-42051.   
[6]Meddeb M, Dhraief A,Belghith A,et al.AFIRM: Adaptive forwarding based link recovery for mobility support in NDN/IoT networks [J]. Future Generation Computer Systems,2018,87:351-363.   
[7]Hernandez D,Gameiro L,Senna C,et al.Handling producer and consumer mobility in IoT publish-subscribe named data networks [J]. IEEE Internet of Things Journal,2021,9 (2): 868-884.   
[8]Yan Zhiwei,ParkYJ,Leau YB,etal. Hybrid network mobility support in named data networking [C]//Proc of the International Conference on Information Networking.[S.1.]: IEEE Press,2020:16-19.   
[9]Zhang Yu,Xia Zhongda,Mastorakis S,et al.KITE:Producer mobility support in named data networking[C]//Proc of the 5th ACM Conference on Information-Centric Networking.New York:ACM Press,2018:125- 136.   
[10] Han D,Lee M,Cho K,et al.Publisher mobility support in content centric networks [C]// Proc of International Conference on Information Networking.[S.1.]: IEEE Press,2014: 214-219.   
[11] Kuai Meng,Hong Xiaoyan.Location-based deferred broadcast for adhoc named data networking [J]. Future Internet,2019,11 (6):139.   
[12] Gindogan C,KietzmannP,Schmidt T C,et al.A mobility-compliant publish-subscribe system for an information-centric Internet of Things [J].Computer Networks,2022,203:108656.   
[13] Kim D H,Kim JH,Kim Y S,et al. End-to-end mobility support in content centric networks [J]. International Journal of Communication Systems,2015,28 (6): 1151-1167.   
[14] QiXin,Su Yuwei,Yu Keping,et al.Design and performance evaluation of content-oriented communication system for IoT network: A case study of named node networking for real-time video streaming system [J]. IEEE Access.2019.7: 88138-88149.   
[15] Ahmed M Z,Hassan AM,Alkali AH,et al.Performance evaluation of scenario-aware protocol for producer mobility support in NDN[C]// Proc of the 7th International Conference on Mechatronics Engineering (ICOM).[S.1.]:IEEE Press,2019:1-6.   
[16] Araujo F,Sousa A D,Sampaio L N. SCaN-Mob:An opportunistic caching strategy to support producer mobility in named data wireless networking[J]. Computer Networks,2019,156 (19): 62-74.   
[17]赵光远，王雷，方盛宇．基于POF-ICN架构的新移动性体系[J].计 算机系统应用,2019,28(3):201-207.(Zhao Guangyuan,Wang Lei, Fang Shengyu. New mobility system based on POF-ICN architecture [J]. Computer System and Application,2019,28 (3):201-207.)   
[18] Ali I，Lim H.NameCent: Name centrality-based data broadcast mitigation in vehicular named data networks [J].IEEE Access,2021,9: 162438-162447.   
[19]王国卿.NDN数据提供者移动支持策略能耗建模与分析[J]．北京邮 电大学学报,2021,44(02): 75-80.(Wang Guoqin.Energy Consumption modeling and analysis of NDN data provider mobile support strategies [J].Journal ofBeijing University ofPosts and Telecommunications,2021, 44 (02): 75-80.)   
[20] Augé J, Carofiglio G, Grassi G,et al. Map-me: managing anchr-less producer mobility in content-centric networks [J].IEEE Trans on Network and Service Management,2018,15 (2): 596-610.   
[21] Choi JH,Cha JH,Han YH,et al.A Dual-Connectivity mobility link service for producer mobility in the named data networking [J]. Sensors, 2020,20(17):4859.   
[22] Pokrovskaya O,Fedorenko R,Khramtsova E.Modeling of a system for organization of traffic via a terminal network [C]//Proc of International Scientific Siberian Transport Forum.Switzerland: Springer,Cham,2019: 1162-1175.   
[23] Mastorakis S,Afanasyev A, Zhang Lixia. On the evolution of ndnSIM: An Open-Source simulator for NDN experimentation [J].ACM SIGCOMM Computer Communication Review,2017,47 (3): 19-33.   
[24] Zhang Liqiang,Cheng Y J, Zhou Xiaobo.Enhanced statistics-based rate adaptation for 8O2.11 wireless networks [J].Journal of Network and Computer Applications,2011,34 (5): 1695-1706.   
[25] Camp T,Boleng J,Davies V.A survey of mobility models for ad hoc network research [J]. Wireless Communications and Mobile Computing, 2002,2 (5): 483-502.