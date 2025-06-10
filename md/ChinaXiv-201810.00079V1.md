# 移动群智感知中支持隐私保护的动态激励机制

梁艳1,²，安健2，胡先智³，司海峰1

(1．西安思源学院 理工学院，西安 710038;2.西安交通大学深圳研究院，广东 深圳 518057;3．西安理工大学网络信息管理中心，西安 710048)

摘要：针对移动群智感知中高质量感知数据与参与用户隐私之间的矛盾，提出一种支持隐私保护的动态激励机制。首先，采用轻量级隐私保护方法，利用安全加密哈希函数为竞标用户生成不少于256位的可变地址序列，并结合随机数对候选用户节点的效用报价进行隐匿和约束；其次，通过定义区域热度、时间热度、数据完整率和数据质量等多维参数，实现任务价值与用户效用报价的动态平衡；最后，依据用户提交的效用报价和任务预算，并利用逆向拍卖思想，完成对任务参与节点的最优选择和动态激励。在群智感知系统模拟平台上进行仿真实验，结果表明所提机制不仅增强了隐私保护度和数据精确度，同时提升了时间效率和激励效果。

关键词：移动群智感知；隐私保护；激励机制；逆向拍卖；效用报价 中图分类号：TP309.2 doi:10.3969/j.issn.1001-3695.2018.07.0431

# Dynamic incentive mechanism with privacy-preserving in mobile crowd sensing

Liang Yan1, ²,An Jian²†,Hu Xianzhi³, Si Haifeng1 (1.Schoolof Technology,Xi'an Siyuan University,Xi'an710o38,China;2.Shenzhen Research Instituteof Xi'an Jiaotong University,Shenzhen Guangdong 518057,China;3.Centerof Network Information&Management,Xi'an Universityof Technology,Xi'an 710048,China)

Abstract: Aimingat thecontradiction between high-quality perception dataand user privacy in mobile crowd sensing system, this paper proposedadynamic incentive mechanism with privacy-preserving.Firstly,iused thelightweightprivacy-preserving methodand a secure encryption hash function to generatea variable address sequence ofnotlessthan 256bits forthe biding user,and integrated arandomnumber toconcealand constraintthedatautilitypriceofthecandidateuser node.Secondly,by definingmulti-dimensionalparameterssuchasregionalheat,timeheat,dataintegrityrateanddataquality,itrealized the dynamic balancebetween task valueand datautility price.Finaly,basedonthedatautility priceoftheuserand task budget, and using thereverse auction,itcompleted the optimal selectionand dynamic incentive for the task participation nodes. Simulation experiments on the mobile crowd sensing system simulation platform showthatthe proposed mechanism notonly enhances the privacy-preserving and data accuracy,but also improves the time eficiencyand incentive effect. Key words: mobile crowd sensing; privacy-preserving; incentive mechanism; reverse auction; data utility price

# 0 引言

近年来，随着移动互联网、传感网络、社交网络的快速发展，移动群智感知（mobile crowd sensing,MCS）成为普适计算领域的前沿研究问题[I]。移动群智感知[2]是以普通用户的移动终端设备作为基本感知单元，通过移动互联网进行有意识或无意识的协作，实现感知任务分发与感知数据收集，完成大规模复杂的社会感知任务。移动群智感知应用依赖大量普通用户参与，而用户在参与感知时会消耗自身设备的电量、计算、存储、通信等资源并且存在个人隐私泄露的风险[3]。而隐私泄漏又是阻碍用户参与感知的一个重要因素。因此，设计合理的激励机制并能够有效保护用户个人隐私，对促进移动群智感知系统平台的长期稳定发展具有重要意义。

目前研究人员对群智感知各阶段的隐私保护问题做了许多研究，如分组统计，位置混淆，k-匿名，差分隐私等，但这些解决方案通常是引入注册机构/可信第三方或聚合服务器，以实现对感知数据、用户或用户位置的隐私保护。然而，大多数没有考虑竞标参与者报价隐私的泄露。因此，本文希望在更一般的环境中通过保护参与者的身份和报价隐私来补充现有的隐私方案，以实现更好的匿名性和隐私保护。

本文提出一种支持隐私保护的动态激励机制，利用安全加密哈希函数为竞标参与者生成不少于256位的可变地址序列作为注册编号，以此标识参与者竞标身份，实现匿名参与，并结合随机数对参与者的效用报价进行隐匿和约束，实现竞标中效用报价的隐私保护。效用报价由参与者的数据完整率、数据质量以及理想报价等多维参数确定。平台根据效用报价和任务预算对参与节点进行最优选择并支付，对竞标失败者按照任务预算剩余额度给予一定补偿。机制采用轻量级隐私保护方法和数据加密技术，结合合理的报酬支付方式，实现其激励作用。

# 1 相关工作

针对群智感知激励方式问题，近几年逐渐涌现出许多有价值的研究。现行的报酬支付激励是基于博弈论的方法，以微支付形式回报参与者的感知数据，是目前最常用的激励方式，其中逆向拍卖模型应用较广。文献[4]首次将经济领域中的逆向拍卖应用在群智感知激励机制研究中，在最小化支付代价的同时保证较高的参与率。该文提出逆向拍卖动态价格-虚拟参与积分机制(RADP-VPC)，选取参与者中报价最低的作为胜出者并支付，同时引入虚拟参与积分的概念，避免在竞标中屡次失败的参与者退出。文献[5]在RADP-VPC的基础上提出了基于位置的激励模型，在固定预算约束下选择区域覆盖率最大的参与者集合，但是以用户为中心的区域覆盖并不能适应用户位置的动态可变性和多样性。文献[6]采用逆向拍卖中的多属性拍卖机制不仅考虑参与率问题，还考虑感知数据质量问题。服务器平台能够通过拍卖过程影响数据质量，同时，参与者能够通过拍卖结果的反馈提高自身感知数据的质量，从而提高竞标价格。然而，以上这些激励机制都不考虑参与者的隐私保护。

针对群智感知隐私保护问题，学者们研究了多种隐私保护技术，主要分为四类：分组统计、第三方验证、K-匿名、数字加密。文献[7]提出了PriSense 隐私保护方案，过程包括切分重组和二分查找两部分，它能够支持各种非增量型数据聚集和快速获取聚集值，并对参与者的隐私保护强度和能耗进行均衡处理。文献[8]利用可信第三方为参与者提供匿名服务，参与者在可信第三方处注册自己的感知设备并安装参与感知的软件，验证通过后，可信第三方将参与者的个人信息映射到新用户空间，然后以新用户身份向服务器请求数据，参与者的数据传输由可信第三方负责。文献[9]提出一种连续LBS(Location -basedService)请求下的需求感知位置隐私保护模型DALP，通过删除最远足迹和缩小匿名区边界，最小化共同用户的历史足迹所形成的匿名区，以减小查询时延以及服务器的负载，来进一步提高用户请求服务质量。文献[10]采用基于身份加密的参与者数据隐私保护方法，它不依赖于传统公钥基础设施PKI和认证中心来向参与者绑定公钥，参与者的身份信息（如电话号码、身份证号码、邮件地址等）可以直接作为参与者的公钥，私钥则由受信任的私钥生成器PKG管理和颁发，该方法能为移动节点和请求者提供有效安全的通信。虽然这些隐私保护方案用不同技术对参与者的数据进行保护，但都没有考虑如何激励参与者提交高质量感知数据问题。为此，本文提出既支持参与者数据隐私保护又能激励参与者提交高质量感知数据的动态激励机制。

# 2 系统模型与问题分析

# 2.1系统模型

本研究基于一个通用的移动群智感知系统，该系统包含三种角色，分别是：任务发布者，任务参与者（工作者或用户)，拍卖基础设施。对这三种角色阐述如下。

a）任务发布者（taskpublisher)。对感知数据感兴趣或有一定需求的组织或个人，并对感知数据指定了时间有效期、位置或区域以及愿意为获得感知数据所希望支付的报酬等需求。

b）任务参与者（participant）。是使用智能手机等各种移动感知设备，按照任务发布者的需求进行感知数据采集的人员，也称工作者（taskworker）或用户（user）。

c）拍卖基础设施（auction infrastructure)。由三种不同的服务器组成，它们同属于一个移动群智感知平台。三种服务器分别是任务服务器（taskserver,TS）、拍卖服务器（auction server,AS）和报表服务器（report server,RS）。任务服务器负责发布感知任务；拍卖服务器负责运行拍卖过程，此过程中参与者可以向拍卖服务器发起竞标；报表服务器负责收集胜出者（winner）的感知数据，并将数据转发给任务发布者。

图1描述了通用移动群智感知系统的三个工作阶段。首先，TS 发布来自任务发布者的感知任务（ $\textcircled{1}$ )，参与者的移动设备定期访问TS，搜索是否有适合自身的任务并有选择性地下载（ $\textcircled{2}$ )；然后，参与者按照任务发布者给出的任务属性等信息，到达目的地去完成感知任务（ $\textcircled{3}$ )，完成任务的工作者在拍卖阶段可以向AS进行注册并发起竞标，所提机制为参与者提供注册信息和效用报价的加密保护，以实现匿名参与（ $\textcircled{4}$ )，当拍卖结束后，AS根据参与者的效用报价和发布者的任务预算选择胜出者（ $\textcircled{5}$ )；最后，胜出者将感知数据提交给RS( $\textcircled{6}$ )，RS 验证后，AS再将任务报酬支付给胜出者（ $\textcircled{7}$ ）。

![](images/2f013782b949f95e313cadeb07ddd8249e356edb25c5d4363621034c0902d9ff.jpg)  
图1移动群智感知系统的工作流程

# 2.2问题分析

# 2.2.1隐私和公平需求

1）参与者的隐私

在竞标结束之前，参与者需要匿名，所有报价需要保秘，意味着参与者的身份信息不能以任何方式与其提交的报价联系在一起。这要求隐私保护措施要确保参与者在不泄露身份或设备标识的情况下完成竞标，其他人也不能推断有关参与者的任何信息。本文隐私保护方法采用安全加密哈希函数对参与者的身份和报价进行加密隐匿，和前人研究的重量级密码操作和原语（如秘密共享技术、多方计算、同态加密等）方案[11不同，是一个轻量级且安全的方法，能支持参与者匿名参与。

# 2）公平和公正性

竞标过程中要求参与者不能根据其他人的竞标信息确定自己的报价，并且一旦提交效用报价，就不能否认或修改，以此保证竞标的公平性。竞标结束后进入开放阶段，竞标过程应经得起任何参与者验证，确保竞标的有效性和胜出者选择的公正性。因此，需要具有承诺措施，能够约束参与者的竞标行为，从而为所有参与者提供公平和公正的拍卖环境。方案包含承诺措施，通过哈希函数和随机数的使用可以确保参与者在竞标中对其效用报价的承诺。

# 2.2.2胜出者选择和报酬支付

由于感知任务形式各异，加之采集环境的多变性，在缺少客观评价标准的情况下，任务发布者和参与者很难凭主观评估任务价值，可能导致发布者给出的任务预算难以让参与者满意，而参与者在竞标时也很难给出一个合理报价。因此，有必要设置一个能够客观评估任务价值的模块，为发布者和参与者提供参考依据。本机制为移动群智感知平台提供了任务价值评估策略，通过拍卖服务器在消息窗口发布任务价值，为任务发布者设置合适的任务预算和参与者设置合理报价提供参考。

选择胜出者时，如果仅考虑最低报价的参与者，可能导致参与者提交低质量的感知数据，不能满足任务发布者的需求。因此，平台在选择胜出者时，不能只关注报价，还要考虑参与者的数据质量，应对提供高质量数据且报价合理的参与者优先选择。因此，机制依据参与者的效用报价和发布者的任务预算来选择胜出者，而效用报价是由参与者的数据效用值（由数据完整率和数据质量决定）和参考任务价值后所提报价得出。为了保持较高的参与率，对竞标失败者也发放一定额度的报酬，将支付胜出者后的剩余预算平均分发给每个失败者，以此来避免在竞标中屡次失败的参与者退出。

# 3 支持隐私保护的动态激励方案设计

# 3.1任务价值

在评估任务价值时，通过基于位置的社交网络LBSN（location-based social networks）应用得到参与者签到数据[12]，利用该签到数据分析参与者的时空特性规律，再结合任务的时空特性计算任务价值。影响任务价值的评估有两个因素：

区域热度和时间热度。区域热度是对任务所在区域中参与者访问频度的度量，时间热度是对任务有效时间内参与者访问频度的度量。这两个因素根据信息空间中参与者签到数据和物理空间中感知任务的时空特性计算得到。

区域热度 $L ( O )$ 由分析LBSN线上数据中参与者对应的签到地点计算得出，如式(1)所示。

$$
\begin{array} { r } { L ( O ) = \frac { \sum _ { x \in U , j \in O } N _ { x , j } } { \sum _ { x \in U , j \in \tau } N _ { x , j } } \times E ( X ) } \end{array}
$$

$$
\begin{array} { r } { E ( X ) = - \sum _ { x _ { i } \in X } ( p ( x _ { i } ) \times l o g _ { 2 } p ( x _ { i } ) ) } \end{array}
$$

其中： $o$ 表示发布者指定的任务区域， $N _ { x , j }$ 表示参与者 $x$ 在地点$j$ 的签到次数， $U$ 表示所有参与者的集合， $\tau$ 表示所有签到地点的集合。式(1)中的 $E ( X )$ 由式(2)计算得到。 $E ( X )$ 表示区域 $o$ 中访问参与者的多样性，通过计算区域信息熵得到。 $X$ 表示在区域 $o$ 签到的参与者集合， $X = \ \{ x \imath , x \imath , . . . , x \imath \}$ 。 $p ( x _ { i } )$ 表示参与者 $x _ { i }$ 在区域 $o$ 签到的概率，即参与者 $x _ { i }$ 在区域 $o$ 签到次数占在所有区域签到次数的比值。

如果区域信息熵越大，则在该区域签到的参与者提供的信息量越大，即该区域签到的参与者多样性程度越高。将区域热度归一化到 $0 ^ { \sim } 1$ 之间，取值越大意味着该区域的访问人数越多，签到频率越高。

时间热度 $T ( Z )$ 由分析LBSN线上数据中参与者的签到时间分布计算得出，取值在 $0 ^ { \sim } 1$ 之间，如式(3)所示。

$$
\begin{array} { r } { T ( Z ) = \sum _ { z \in Z } P V _ { z } } \end{array}
$$

$$
\begin{array} { r } { P V _ { z } = \frac { \sum _ { x \in U , j \in O } N _ { x , z , j } } { \sum _ { x \in U , k \in A , j \in O } N _ { x , k , j } } } \end{array}
$$

由于参与者签到时间具有一定的弹性，为了任务评估的准确性，所以用一个小时为单位将一天分为24个时间段。式(4)中 $A$ 表示24个时间段， $A = \{ 1 , 2 , \cdots , 2 4 \}$ 。 $P V _ { z }$ 表示在第 $z$ 个时间段内所有参与者访问区域 $o$ 的概率。 $N _ { x , z , j }$ 表示参与者 $x$ 在第$z$ 个时间段内访问地点 $j$ 的次数。式(3)中 $Z$ 表示任务覆盖的时间段集合， $Z \subseteq A$ 。

基于区域热度和时间热度，对于任意一个任务，可由式(5)计算得到任务价值 $V$ 。

$$
\begin{array} { r } { V = \frac { L A } { L ( O ) } \times \frac { T A } { T ( Z ) } } \end{array}
$$

$L A$ 表示可由式(1)得到的参与者签到数据中所有区域矩形块的区域热度平均值， $T A$ 表示可由式(3)、(4)得到的所有参与者签到的时间热度的平均值。定义当区域热度为 $L A$ ，时间热度为 $T A$ 时任务价值为基准值1，该基准值是任务的单位价值。式(5)表示任务价值与所在区域热度和时间热度成负相关。也就是说，对于一个任务，参与者采集数据的时间和区域热度越高，在该区域和该时间段的任务就越容易完成，相应该任务的价值就较低，反之，任务价值就越高。

一个任务的价值一旦被平台评估确定后，就及时公布于消息窗口，以便所有参与者参考，同时，也便于任务发布者对任务预算进行动态调整。

# 3.2 数据效用值

任务工作者的表现对数据质量有很大影响。本文用数据效用值作为数据质量的衡量指标。而数据质量测量基于两个主要因素：数据完整率和质量指标。

1）数据完整率（ $\scriptstyle C R .$ ）

数据完整率定义为已完成任务量占所需完成任务总量的比值。 $C R$ 是对任务工作者完成任务量的度量。对于具有预定义点集合 $P$ 的任务，可以对任务工作者所采集的感应点采用基于感应点与 $P$ 中每个点的最短距离方式进行分组。如果最短距离超过阈值 $\boldsymbol { r }$ ，则感应点将被视为与任务无关。否则，此感应点将被分组到 $P$ 中的关联点。然后，可根据一个任务工作者的数据覆盖点数TWP来计算此工作者对于集合 $P$ 的 $C R$ 值，如式(6)所示。

$$
\begin{array} { r } { C R _ { w } = \frac { | T W P | } { | P | } } \end{array}
$$

2）质量指标（QI)

衡量数据质量是一个较难的问题。本文仅讨论数字数据的质量测量。对于每个数据组 $G$ 可以计算一个成员到其所在组中心的距离。对于每个数据，用1减去平均距离与其组的最大距离的比率来表示单个 $\varrho I _ { \because }$ ，则一个任务工作者所有数据的平均值即为此工作者的数据质量指标 $\varrho I$ $( 0 < Q I \le 1 )$ ，计算如式(7)所示。假设一个工作者的所有数据集合为 $D _ { w } { = } \{ d _ { I } { , } d _ { 2 } { , } { \ldots } { , } d _ { n } \}$ 。

$$
\begin{array} { r } { Q I _ { w } = \frac { \sum _ { i = 1 } ^ { | D _ { w } | } \left( 1 - \frac { d _ { i } - G \left( d _ { i } \right) . c e n t e r } { M a x D i s \left( G \left( d _ { i } \right) \right) } \right) } { | D _ { w } | } } \end{array}
$$

3）数据效用值（ $. D U .$ ）

基于数据的完整率 $C R$ 和质量指标 $\varrho I$ 两个因素，可得出一个任务工作者的数据效用值 $D U _ { w }$ ，如式(8)所示。

$$
D U _ { w } = C R _ { w } \times Q I _ { w }
$$

# 3.3效用报价

参与者要想在竞标中获胜，需要给出合理报价，因此，需结合自身的数据效用值和平台给出的任务价值进行报价，才能保证较大胜出率。参与者参考平台任务价值 $V$ 提出理想报价 $B V$ 再计算出自身效用报价作为竞价。效用报价 $B U _ { w }$ 由式(9)计算得到。

$$
B U _ { w } = B V \times ( 1 - D U _ { w } )
$$

# 3.4拍卖

拍卖过程包括三个主要阶段：注册、竞标和开放。在注册阶段，每个参与者进行匿名注册来保护自己的身份隐私。在竞标阶段，确保每个参与者的效用报价对于其他参与者不可见。在开放阶段，拍卖服务器公开每个参与者的效用报价，但仍保持参与者身份信息隐匿，拍卖服务器根据效用报价确定匿名胜出者。一旦胜出者上传了其感知数据，经报表服务器验证通过后，就会得到相应的报酬。

假定在拍卖服务器上存在用于服务器和参与者进行信息交换的“合约消息窗口”。一旦消息发布到消息窗口，任何参与者都可以阅读，但不能删除或更改。因此，合约消息窗口是一个广播程序模块，任何参与者都可以接收广播消息，而且消息可以被任何参与者验证。拍卖服务器的公钥 $k$ 通过发布于消息窗□来告知每个参与者，参与者可以使用此公钥 $k$ 将信息加密发送给拍卖服务器并验证由服务器签名的消息。用Hash(表示一个具有不少于256位输出的安全加密哈希函数。“安全”意味着Hash(是单向的和抗冲突的。因此，反转哈希函数或者寻找满足Hash（ $\mathbf { \Phi } _ { \cdot x } \mathbf { \dot { \sigma } }$ ） $\ l =$ Hash $( y )$ 的 $x$ 和 $y$ 在计算上是不可行的。

3.4.1注册

竞标开始之前拍卖服务器向消息窗口发布其公钥以及拍卖的各种参数，如拍卖 $I D$ 、拍卖各阶段开始/结束时间等。一旦注册开始，每个参与者在规定注册时间内，向AS发送一个匿名编号BidderID来标识其在竞标中的身份信息。BidderID由参与者随机选取的一次性临时公钥 $k ^ { e }$ 的哈希值 $H a s h ( k ^ { e } )$ 生成。AS收到后将此信息发布到消息窗口，每个参与者就可以核实自己的BidderID对于本次竞标是否已被成功注册。

定义1如果 $( k , ~ k ^ { I } )$ 是实体 $A$ 的一对密钥，则 $S i g _ { A , k } – I \left( m \right)$ 表示实体 $A$ 用私钥 $k ^ { - I }$ 对信息 $\mathbf { \nabla } _ { m }$ 创建的数字签名，用 $\sigma$ 表示，即 $\sigma { = } S i g _ { A , k } { ^ { - 1 } } ( m ) \circ S i g . \nu e r i f y _ { A , k } ( m , \sigma )$ 则表示用 $A$ 的公钥 $k$ 对信息$m$ 的数字签名 $\sigma$ 解密验证的结果（真或假)。

算法1.参与者匿名注册（AnonymousRegistration）

输入：参与者 $b$ 的一次性临时公钥 $k ^ { e }$ 0输出：参与者 $b$ 的经过拍卖服务器 $A$ 签名授权的匿名注册编号BidderID。

$1 . \mathrm { h { = } H a s h { \left( k ^ { e } \right) } }$ ，h是 $\boldsymbol { \mathbf { b } }$ 的匿名注册编号BidderID;$2 . \mathrm { h } ^ { \ast } { = } r ^ { e _ { A } \ast } \mathrm { h }$ mod $\mathrm { \Delta N _ { A } }$ ，r：新随机数，eA：A的公钥，NA：加密算法模量， $\boldsymbol { \mathrm { h } } ^ { * }$ ：加密后的BidderID;$3 . { \mathsf { b } } {  } { \mathsf { A } }$ $\boldsymbol { \mathrm { \acute { h } } } ^ { * }$ and $\sigma { ^ { = } } \mathrm { S i g _ { b , k } } ^ { \mathrm { e - 1 } } ( \mathrm { h } ^ { \ast } )$ 4. if Sig.verifyb ${ \mathrm { , k } } ^ { \mathrm { e } } ( { \mathrm { h } } ^ { \ast } , \sigma )$ =true then5． $\mathbf { A { \to } b }$ ： $\pmb { \sigma } ^ { * } \mathrm { = } \mathrm { S i g } _ { \mathrm { A , \mathrm { d A } } } ( \mathbf { h } ^ { * } )$ ， $\mathrm { \ d _ { A } }$ 是A的私钥,6. end if$7 . \sigma ^ { \prime } { = } \mathrm { r \ ^ { - 1 } \ ^ { * } } \sigma ^ { * } { \bmod { N } } \mathrm { a }$ ，b得到A关于h的数字签名 $\sigma ^ { \prime }$ 。

算法1不但支持参与者匿名注册，而且最终也为参与者生成了一个授权的临时公钥 $k ^ { e }$ 。在感知数据提交阶段只要参与者提供了这样的凭证，就被认为是授权用户。因此这种方式也是一种验证临时密钥的方法。

# 3.4.2竞标

注册结束后进入竞标阶段，参与者用隐匿的效用报价进行竞标，而且必须遵守竞标承诺。承诺方案是在提交者和接收方之间执行一对算法（Commit，Open）。提交报价时，参与者执行算法Commit，同时需要输入消息 $m$ 和辅助信息 $r m$ （一个不可预知的随机数）来产生一次提交 $C _ { m } { = } C o m m i t ( m , \ r m ) ,$ 。承诺方案应具有较强的约束力和隐匿性，确保接收方在开放阶段之前不能获得关于 $\mathbf { \nabla } _ { m }$ 的任何信息，也保证恶意提交者无法找到一组替代值 $( m ^ { \prime } , \ r m ^ { \prime } )$ ，能使开放算法Open $\left( C _ { m } , m ^ { \prime } , r m ^ { \prime } \right) { = } O p e n \ \left( \ C _ { m } \right.$ $m , r m )$ 。

本文隐私保护采用简单方法即哈希函数 $H$ ，为提交算法Commit生成承诺报价 $C B U _ { w }$ ，如式(10)所示。

$$
C B U _ { w } = C o m m i t ( B U _ { w } , r _ { w } ) = H ( r _ { w } | | B U _ { w } )
$$

其中： $r _ { w }$ 为用来隐匿 $B U _ { w }$ 的随机数。

参与者需向拍卖服务器发送一个用自身私钥 $k ^ { I }$ 签名的消息 $\sigma _ { b }$ ，如式(11)所示。

$\sigma _ { b } = S i g _ { b , k ^ { - 1 } } ( A c t i o n I D | | B i d d e r I D ^ { \prime } | | C B U _ { w } )$ (11)其中，ActionID为本次竞标编号，BidderID'为加密后参与者注册编号。

采用轻量级隐私保护方法既能确保竞价的隐匿，又能约束参与者不能随意否认或更改报价。此外，报价在消息窗口公布，以便任何参与者都可以验证其报价已被正确提交给拍卖服务器。当拍卖服务器接收到 $\dot { \sigma } _ { b }$ 时，它能够确定是来自平台的合法参与者，因为是用带有其签名的公钥完成验证。因此，临时密钥充当授权凭证，允许服务器隐式验证参与者但却不能识别参与者。

# 3.4.3开放

当拍卖服务器公告竞标结束时，每个参与者的效用报价$B U _ { w }$ 真值就显现出来。在接收到 $B U _ { w }$ 和 $r _ { w }$ 后，拍卖服务器评估Commit $( B U _ { w } , r _ { w } ) = H ( r _ { w } | | B U _ { w } )$ 并继续使用与参与者相关联的临时密钥来验证签名 $\sigma _ { b }$ 。拍卖服务器对报价验证后，会根据任务预算选择前 $\boldsymbol { n }$ 个 $B U _ { w }$ 值最低的参与者作为胜出者。然后，在消息窗口广播一个已签名的消息，包含胜出者的匿名编号BidderID、临时公钥以及效用报价 $B U _ { w }$ 。因此，任何参与者都可以通过计算 $H ( r _ { w } | | \boldsymbol { B } U _ { w } )$ 来验证本次竞标的正确性，确保了拍卖过程的公平公正。

算法2.竞标—开放（Bidding-Opening）

输入：参与者 $b$ 的效用报价 $B U _ { w }$ 和一个新随机数 $\boldsymbol { r } _ { w }$ 输出：拍卖服务器签名的 $n$ 个胜出者节点消息。

竞标阶段

1. Commit $= H ( r _ { w } | | B U _ { w } )$ ， $b$ 得到 $C B U _ { w }$ $2 . b ~  ~ A S \colon ~ \sigma _ { b } = S i g _ { b , k ^ { e - 1 } } ( A c t i o n I D | | B i d d e r I D ^ { \prime } | | C B U _ { w } ) ;$ （20开放阶段3.初始化集合 $s = \emptyset$ 4. for $b _ { i }$ from $b _ { I }$ to $b _ { n }$ do5. $m _ { i } = ( A c t i o n I D | | B i d d e r I D ^ { \prime } | | H ( r _ { w } | | B U _ { w } ) ) ;$ 6. if Sig.verifyb, ${ \bf \nabla } _ { k } { \bf \Pi } ^ { e } ( m _ { i } , \sigma _ { b } ) { = } t r u e$ then7. $S { = } S { + } \left\{ m _ { i } \right\}$ 8. end if9.end for10.对集合 $s$ 按照 $B U _ { w }$ 值升序排序，得到新集合 $S ^ { \prime }$ ，并将 $S ^ { \prime }$ 内容发布  
于消息窗口;11.初始化：胜出者集合 $W { = } 0$ ， $W$ 中当前节点个数 $\scriptstyle n = 0$ ，胜出者节点  
总数为 $N$ 12. $\scriptstyle x = S ^ { \prime } .$ FirstElement();13.while Total $B { > } 0$ and $n { < } N$ do14. $\scriptstyle { W = W + \{ x \} }$ 15. $n { = } n { + } 1$ 16. TotalB=TotalB-TotalBx;17.x=S'.NextElement();  
18.end while  
19. return $W$ ，胜出者节点发布于消息窗口，即  
$A S ~  ~ ^ { * } \colon S i g _ { A S } ~ ( A u c t i o n I D , ( B i d d e r I D _ { 1 } , ~ k _ { 1 } ^ { e } , B U _ { w 1 } , r _ { w 1 } ) , . . . ) _ { \circ }$

# 3.5支付措施

选出的胜出者可以向报表服务器传送感知数据，报表服务器对收到的数据进行验证，如果合格，便依据胜出者的效用报价对其进行支付。对所有上传了合格数据的胜出者支付完成后，若任务预算有剩余，则平均发放给竞标失败者，以此给失败者一定补偿。

# 4 性能分析

对方案从隐私保密性、正确性、不可否认性、不可链接性和激励有效性等方面进行性能分析。

# 1）隐私保密性

由于参与者注册时，采用安全加密哈希函数Hash(对参与者的一次性临时公钥生成一个不少于256位的哈希值来标识参与者竞标身份，且HashO具有抗冲突性，能够确保任何参与者的注册编号唯一，因此，参与者的身份隐私信息能够被较好地保护。又因为效用报价以 $H ( r _ { w } | | \boldsymbol { B } U _ { w } )$ 形式在竞标中出现，哈希函数 $H$ 的单向性和随机数 $r _ { w }$ 的使用能够确保效用报价保持隐匿且不能被其他参与者推断，同时也消除了合谋的可能性，因此方案对于参与者的竞价具备隐私保密性。

2）正确性

由于竞标结束后所有参与者的效用报价 $B U _ { w }$ 和所用随机数$r _ { w }$ 都公布于消息窗口，所以任何参与者都可以验证竞标的正确性。因此，不可能有假报价出现或已发生的报价被改变（由于散列函数H的抗碰撞性)，能够保证竞标的正确性和公正性。

# 3）不可否认性

由于每一次报价都携带着参与者的数字签名，并且哈希函数的抗冲突性能确保不可能找到一个 $( \boldsymbol { r } ^ { \prime } , \ \boldsymbol { B } \boldsymbol { U } ^ { \prime } )$ 集合，使得 $H$ $\left( \boldsymbol { r ^ { \prime } } | | \boldsymbol { B } \boldsymbol { U } ^ { \prime } \right) \ = H \ \left( \boldsymbol { r } | | \boldsymbol { B } \boldsymbol { U } \right)$ ，所以一旦开始竞标，参与者就不能否认或修改其报价。此外，如果竞标出现争议，竞标承诺可用于解决争议，承诺值 $( r , B U )$ 和参与者的数字签名可用于证明竞标的真实性。所以，能够对参与者的竞标行为进行很好地约束。

# 4）竞标的不可链接性

此属性与参与者身份隐私有关。为确保不能将同一参与者在不同竞标中提交的两个报价联系起来，因此，本方案支持参与者每次竞标采用不同的匿名编号和公钥，保证了参与者和报价之间的不可链接性。

# 5）激励的有效性

由于胜出者选择是考虑了参与者的数据效用值、参考任务价值所提理想报价等多维参数，不是只单方面考虑最低报价，并且对竞标失败者也给予一定的补偿。因此，方案做到了胜出者最优化选择，对胜出者而言奖励报酬能够满足其需求，最终对胜出者和失败者都起到较好的激励作用。

# 5 实验验证

为评估方案的有效性，从隐私保护度、数据精确度、时间效率和激励效果等方面进行验证。

# 5.1实验数据和环境

实验过程采用仿真实验，仿真数据由群智感知系统模拟平台产生。模拟平台于三个月内陆续发布 50个校园内不同位置的感知任务，并招募一定数量的学生参与完成，对于每一个感知任务，注册人数范围为 $1 0 0 ^ { \sim } 1 0 0 0$ 人。经过50次任务发布、拍卖和支付，平台积累了大量的仿真数据。

实验环境为Intel i5-7200U $2 . 5 \mathrm { G H z }$ CPU、4GB内存、Windows7操作系统，算法采用Objective-C实现。

# 5.2测评指标

# 1）隐私保护度

参与者的隐私泄露概率 $P _ { - }$ reveal定义为竞标隐私泄露量与需要保护的竞标隐私总量的比值，如式(12)所示。

$$
\begin{array} { r } { P _ { - } r e v e a l = \frac { n _ { - } r e v e a l } { N _ { - } p r o t e c t } } \end{array}
$$

其中， $n$ _reveal为被泄露的竞标隐私量， $N _ { _ - }$ protect为需要保护的竞标隐私总量。

隐私保护度Privacy_Degree定义为：

$$
P r i v a c y _ { - } D e g r e e = 1 - P _ { - } r e v e a l
$$

隐私保护度越高，对隐私数据的保护水平越强。

# 2）数据精确度

由于隐私保护问题，会对参与者提交的匿名身份数据、加密的报价数据的精确度有一定影响。数据精确度是指匿名数据集和原始数据集之间的差异，通常用 SSE(sum of squared errors)进行度量。 $S S E$ 表示了匿名数据集和原始数据集中所有记录的属性距离的平方和，如式(14)所示。

$$
\begin{array} { r } { S S E = \sum _ { x _ { i } \in X } \sum _ { a _ { i } ^ { n } \in x _ { i } } \Bigl ( d i s t \bigl ( a _ { i } ^ { n } , ( a _ { i } ^ { n } ) ^ { \prime } \bigr ) \Bigr ) ^ { 2 } } \end{array}
$$

其中， $a _ { i } ^ { n }$ 是原始数据集中第 $i$ 个记录的第 $n$ 个属性， $( a _ { i } ^ { n } ) ^ { \prime }$ 是匿名数据集中第 $i$ 个记录的第 $n$ 个属性。distO是距离函数。 $S S E$ 的值越小，数据精确度越高，数据的可用性越好。

3）时间效率

拍卖时间 $T _ { i }$ 定义为从开始注册到选出胜出者所经历的运行时间，如式(15)所示。

$$
\begin{array} { r } { T _ { i } = t _ { w i n } - t _ { r e g } ( 1 \leq i \leq n ) } \end{array}
$$

其中， $t _ { w i n }$ 表示选出胜出者的时刻， $t _ { r e g }$ 表示开始注册的时刻， $n$ 表示拍卖总次数， $i$ 表示第 $i$ 次拍卖。

算法时间效率用 $T ( n )$ 来度量， $T ( n )$ 为 $n$ 次拍卖时间的平均值，如式(16)所示。 $T ( n )$ 的值越小，算法的时间效率越高。

$$
\begin{array} { r } { T ( n ) = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } ( T _ { i } ) } \end{array}
$$

# 4）激励效果

用户参与率和满意度能够反映方案的激励效果。用户参与率 $P _ { - }$ work定义为参与竞标人数与注册人数的比值，如式(17)

所示。

$$
\begin{array} { r } { P _ { - } w o r k = \frac { n _ { - } b i d } { N _ { - } r e g } } \end{array}
$$

其中， $n _ { - } b i d$ 表示参与竞标人数， $N _ { - } r e g$ 表示注册人数。

参与感知任务的用户在完成任务并获得相应报酬后对平台做出评价，评价结果 $e$ 设定两个等级，如式(18)所示。

$$
e = \left\{ \begin{array} { l l } { { 1 } } & { { \mathrm { i f } } \overrightarrow { { \overrightarrow { p } } + 1 } \overrightarrow { { \overrightarrow { \mathrm { E } } } } } \\ { { 0 } } & { { \mathrm { \mathcal { T } } } { \cdot } { \mathrm { i f } } \overrightarrow { { \overrightarrow { p } } + 1 } \overrightarrow { { \mathrm { E } } } } \end{array} \right.
$$

用户满意度 $s$ 定义为给出评价结果为“1”的用户人数与参与评价总人数的比值，如式(19)所示。

$$
\begin{array} { r } { S = \frac { n _ { ( e = 1 ) } } { N _ { - } e v a l u a t e } } \end{array}
$$

其中， $n _ { ( e = I ) }$ 表示给出评价结果为“ $1 ^ { \prime \prime }$ 的用户人数， $N$ evaluate表示参与评价的总人数。

# 5.3 实验结果与分析

对于隐私保护度、数据精确度、时间效率的测试，在相同仿真数据和实验环境下，将本文算法与PRIDE、TTP两种隐私保护方案进行对比。PRIDE[13]是认知无线电网络中的一种隐私保护和频谱拍卖方案，它利用了复杂密码技术（如安全多方计算，保序加密以及不经意传输协议）以获得最低报价并保护报价隐私。TTP（TrustedThirdParty）[8是可信第三方群组机制，该机制引入一个完全可信的第三方来执行群组竞标，有关参与者的所有信息，如报价，ID和时空矩阵，对于TTP都是透明的，参与者的隐私完全依赖于TTP。

通过设置隐私阈值为 $[ 0 . 1 ^ { \sim } 1 . 0 ]$ ，测试得到三种算法的隐私保护度对比，如图2所示。

![](images/04aac3a3a71d172d97195ecad4a9f2fa9219c75cf95265f6da1783a01d35f8c0.jpg)  
图2三种算法隐私保护度对比

由图2可知，随着隐私阈值的增大，三种算法的隐私保护度均呈上升趋势。因为隐私阈值设置的越高，算法对参与者隐私数据的保护水平越强。在相同的隐私阈值条件下，本文算法的隐私保护度比PRIDE 和TTP 都高。由于本文算法借助参与者的临时公钥用具有抗冲突性的安全加密哈希函数生成多于256位的可变地址序列来保护参与者身份，并结合随机数对候选参与节点的效用报价进行隐匿，而PRIDE和TTP 算法都不具有抗冲突性和生成可变地址序列的特性，所以本文算法的隐私保护水平更强，隐私保护度优于以上两种算法。

图3为三种算法的数据精确度对比，同样设置隐私阈值为$[ 0 . 1 \widetilde { \phantom { . } } 1 . 0 ]$ 。

![](images/e636b2eebed0ac6db474df8f6aa15e7aadac58d8673f3cd66e18765aa15719ee.jpg)  
图3三种算法数据精确度对比

由图3可知，随着隐私阈值的增大，PRIDE 和TTP算法的数据精确度都呈下降趋势，而本文算法的数据精确度一直趋近于 $1 0 0 \%$ 。因为PRIDE算法采用复杂密码技术进行报价隐私保护，隐私阈值越大，其对报价数据加密的复杂度越高，对报价数据隐匿的程度也越高，从而导致数据的精度下降越大。TTP算法采用可信第三方来保护参与者的所有隐私，随着隐私阈值的增大，可信第三方对参与者隐私的保护级别也越高，通过群组竞标来隐匿真实参与者身份等信息的混淆度越高，导致数据精确度下降较大。本文算法采用轻量级数据加密技术，不必进行复杂的加密运算，就能对参与者身份和报价数据进行隐私保护，数据的精确度受隐私阈值影响较小。

![](images/a76e951e702b05eb88ed5a04973c60c0c9b8344013772f30f4bf9ee7e2c7798b.jpg)  
图4为三种算法的时间效率对比。  
图4三种算法时间效率对比

由图4可知，随着注册人数的增加，三种算法的 $T ( n )$ 都随之增大。因为算法的运行时间会随着人数规模的增大而增加。但本文算法在注册人数增加情况下 $T ( n )$ 仅有小幅增加，而PRIDE和TTP算法都高于本文算法，尤其是PRIDE 算法， $T ( n )$ 增加的幅度最大。可见，在相同的测试条件下，本文算法在时间效率方面更有优势。

对于激励效果的测试，将本机制与Lee等人[13]提出的动态价格逆向拍卖机制RADP、固定价格随机选择机制RSFP两种激励机制进行对比。RADP和RSFP机制采用只对胜出者支付报酬，且都未考虑参与者隐私保护问题。用相同的仿真数据（即50个校园感知任务的发布、拍卖和支付)，注册人数为 $1 0 0 ^ { \sim } 1 0 0 0$ 人的情况下，对三种机制进行测试，得到用户参与率和用户满意度对比分别如图5、6所示。

![](images/36e310b50fd976c29e31689d0b55df6df0933c5f1210003f9f3edf2fba9d4afe.jpg)  
图5三种机制用户参与率对比

由图5可知，随着注册人数的增加，本机制的用户参与率一直保持在 $9 5 \%$ 以上，而RADP和 RSFP 两种机制均呈下降趋势，当注册人数达到1000人时，两者的用户参与率都降到$9 0 \%$ 以下。因为本机制不但考虑了参与者的数据完整率和数据质量，而且是依据效用报价进行胜出者最优选择，对失败者也支付一定的报酬，同时在整个拍卖过程中对参与者身份和报价隐私进行保护。可见，本机制的用户参与率更高，说明它在激励用户参与执行感知任务方面具有更好效果。

![](images/cf562af1e64c9fbb59a50a23bbdc48a8902cc0a6d6df99f1c8e115b96159db21.jpg)  
图6三种机制用户满意度对比

由图6可知，在参与评价人数分别为 $2 0 0 , 4 0 0 , 6 0 0 , 8 0 0 .$ 1000时，本机制的用户满意度都比RADP和RSFP高，平均满意度为 $9 5 . 2 2 \%$ ，而RADP 的平均满意度为 $8 5 . 1 6 \%$ ，RSFP的平均满意度为 $8 1 . 8 4 \%$ 。可见，参与者对该机制的激励方式非常肯定。

从图 $2 ^ { \sim } 6$ 所示的实验结果得出结论，该机制在隐私保护度、数据精确度、时间效率和激励效果等方面比现有激励机制更具优势，说明该机制有效。

# 6 结束语

本文提出一种支持隐私保护的动态激励机制，旨在解决用户隐私泄露等原因导致的群智感知激励机制效果不佳的问题。该机制利用轻量级隐私保护方法，结合数据加密技术，支持参与者匿名注册，并在竞标阶段为参与者的效用报价提供隐私保护，效用报价由参与者的数据完整率、数据质量以及理想报价等多维参数决定。最后依据效用报价对胜出者进行优选并支付，对竞标失败者也有一定补偿，以此发挥激励作用。仿真实验证明机制在隐私保护度、数据精确度、时间效率和激励效果等方面相比同类方案均有较优表现。在后续的研究中，尝试将报酬支付环节数据的隐私保护纳入机制的保护范畴，使机制更加完善。

# 参考文献：

[1]Guo Bin, Chen Huihui,Yu Zhiwen,et al.Fliermeet: a mobile crowdsensing system for cross-space public information reposting,tagging,and sharing [J].IEEE Trans on Mobile Computing,2015,14(10):2020-2033.   
[2]Ganti R K,Ye Fan,Lei Hui.Mobile crowdsensing: Current state and future challenges [J].IEEE Communications Magazine,2011,49 (11): 32-39.   
[3]Wang Yu,Xu Dingbang,Li Fan.Providing location-aware location privacy protection for mobile location-based services [J].Tsinghua Science and Technology,2016,21(3): 243-259.   
[4]Lee JS,Hoh B.Sell your experiences:A market mechanism based incentive for participatory sensing [C]//Proc of IEEE International Conference on Pervasive Computing and Communications.201o: 60-68.   
[5]JaimesLG,Vergara-LaurensI,LabradorMA.Alocation-based incentive mechanism for participatory sensing systems with budget constraints [C]/ Proc of IEEE International Conference on Pervasive Computing and Communications.2012:103-108.   
[6]Krontiris I,Albers A.Monetary incentives in participatory sensing using multi-attributive auctions [J].ParallelAlgorithms & Applications,2012,27 (4): 317-336.   
[7]Shi Jing,Zhang Rui,Liu Yunzhong,et al.PriSense: privacy-preserving data aggregation in people-centric urban sensing systems $[ \mathrm { C } ] / \AA$ Proc of IEEE INFOCOM.2010: 758-766.   
[8]Cristofaro E D,Soriente C.Participatoty privacy:enabling privacy in participatoty sensing [J].IEEE Network,2013,27(1):32-36.   
[9]Li Xinghua,Wang Ermeng,Yang Weidong,et al.DALP:a demand-aware location privacy protection scheme in continuous location-based services [J]. Concurrency & Computation Practice & Experience,2016,28(4):1219- 1236.   
[10] Cristofaro E D,Soriente C.Extended capabilities for a privacy-enhanced participatory sensing infrastructure (PEPSI)[J].IEEE Trans on Information Forensics and Security,2013,8(12): 2021-2033.   
[11] Nojoumian M, Stinson D R.Efficient sealed-bid auction protocols using verifiable secret sharing [C]// Proc of International Conference on Information Security Practice & Experience.2014:302-317.   
[12]南文倩，郭斌，陈荟慧，等．基于跨空间多元交互的群智感知动态激励 模型[J].计算机学报,2015,38(12):2412-2425.(Nan Wenqian,Guo Bin, Chen Huihui，et al.A cross-space,multi-interaction-based dynamic incentive mechanism for mobile crowd sensing [J].Chinese Journal of Computers,2015,38 (12): 2412-2425.)   
[13]Wu Fan,Huang Qianyi,Tao Yixin,et al.Towards privacy preservation in strategy-proof spectrum auction mechanisms for noncooperative wireless networks [J].IEEE//ACM Trans on Networking,2015,23 (4):1271-1285.   
[14]沈楠，袁科，贾春福．一种增强的位置分享隐私保护方案[J].计算机 应用研究,2017,34 (3):862-866,887.(Shen Nan,Yuan Ke,Jia Chunfu. Enhanced privacy-preserving location sharing mechanism [J].Application Research of Computers,2017,34 (3): 862-866,887.)