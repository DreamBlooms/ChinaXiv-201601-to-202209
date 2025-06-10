# 次用户信道使用公平和QoS保障原则的FQMAC协议

苏凡军，张聪

(上海理工大学 光电信息与计算机工程学院，上海 200093)

摘要：针对异构认知无线电网络共存的情况，提出了FQMAC（fair and QoS guaranted MAC）协议。采用信标帧同步，将时间划分为信标周期，在信标周期内分别进行信道感知、信道协商和数据传输；将被其他异构网络的次用户占用的信道也作为可用信道。根据信道质量将所有可用信道划分等级，根据次用户业务特征将次用户划分等级。等级高的次用户优先预约等级高的信道。对信道协商阶段的合理时长通过建立马尔可夫链模型做了理论分析，得出其合理时长的理论值。仿真实验结果证明FQMAC 可以较好地提升网络的吞吐量，保障了用户的QoS（Qualityof Service），并实现了较好的公平性。

关键词：异构；认知无线电网络；划分等级；QoS保障；公平性 中图分类号：TN915.04 doi:10.3969/j.issn.1001-3695.2018.06.0457

# FQMAC:protocol of secondary user fair channel using and QoS guarantee

Su Fanjun, Zhang Cong (SchoolofOptical-Electrical&ComputerEnginering,UniversityofShanghaiforScience&Technology,Shanghai200093, China)

Abstract:This paper proposed FQMAC(fair and QoS guaranteed MAC)protocol used in the scenario of heterogeneous cognitiveradio networks coexisting.Time was divided into beacon periods using beacon frame synchronization.During one beaconperiod,channelsesing,channelegotiation,nddatatransmisionwereperformedrespectively.Thechanelsoupied bysecondaryusers of other heterogeneous networks were treatedas useful channels too.Useful channels were clasified into dierentlevelsaccordingtotheirqualityandsecondaryuserswereclassifiedintodiferentlevelsaccordingtotheirservice characteristics tooHighlevelusers prioritize highlevelchannels.Thereasonabledurationofthechannelnegotiationphasewas obtainedby establishing a Markov chain model.Simulation results show thatFQMACcan improve the throughput of the network, guarantee the users' QoS (Quality of Service),and achieve better fairness.

Key words: heterogeneous; cognitive radio networks; classify; QoS guaranteed; fairness

# 0 引言

无线通信领域现在广泛使用的还是固定频谱接入策略。然而这种策略使得授权频谱的利用率并不高，而另一方面，可用频谱资源已经基本划分完，一些没有授权频带的用户缺少可用的频谱资源。因此，认知无线电技术就被提了出来。认知无线电技术允许次用户（未授权用户）机会式地接入暂时未被使用的授权频谱，利用主用户的通信间歇期进行通信。这样就在不影响主用户的前提下，提高了频谱资源的利用率，较好的解决了上述问题。但是目前认知无线电领域还没有国际统一的标准通信协议，而且由于无线信道上通信的控制和协调发生在MAC（mediaaccess control，媒体访问控制）层，因此设计一个好的MAC协议对于CRN（cognitiveradionetwork,认知无线电网）

具有重要意义。认知无线网络的MAC协议研究目前是一个热点问题，大量的专家学者把精力集中在了这一领域，现在已经有各种类型的MAC协议设计被提了出来。例如文献[1]的作者提出了一种基于频谱预测技术的MAC协议，它采用一种统计的信道分配策略，这种策略可以提高吞吐量并减小对主用户的干扰。Manyi等人针对CRSN（cognitive radio sensor network，认知无线电传感器网络）提出了一种基于前导码采样的自适应MAC协议APS-MAC[2]'该协议支持机会频谱接入，同时解决了CRSN中的节能问题。Nafees等人提出了一种认知无线电ad hoc网络的跨层MAC协议RAPE[3]，RARE协议可以维持较少数量的簇和稳定数量的公共信道而达到较好的性能。Wu等人提出了用于CRAHN（cognitive radio ad hoc networks）的邻居感知距离估计MAC 协议-NMAC[4],在这项研究中，根据 SU(secondaryuser)通信对之间的邻居感知估计出的距离来控制发射机的功率，从而减轻了多通道CRAHN的隐藏和暴露的终端问题，并且增加了吞吐量，降低了PU(primaryuser)中断概率。还有一些MAC协议是基于信道协商机制设计的。此类MAC协议维护一个CCC（commoncontrolchannel，公共控制信道），预先通过CCC协商和预留数据信道。例如，文献[7]提出的用于CM2M网络的数据库驱动的MAC协议；文献[8]提出的动态控制信道MAC协议-DCC-MAC；文献[10]提出的使用CCC信道的同步式MAC协议OMC-MAC。但是上述MAC协议均没有考虑异构CRN共存的问题。所谓异构CRN，是指采用不同的网络接入技术或不同的通信协议的网络。目前CRN没有统一的通信标准，不同局域网采用不同的通信规则，CRN的硬件设备更是各种各样，这就导致了CRN的异构性[II]。而随着5G网络和物联网的发展，未来异构网络并存的情况会越来越多，这就给网络通信协议提出了更高的要求。而CRN以其独特的适应性和智能性优势，必将是下一代通信网络中的重要组成部分。因此，本文着重从异构CRN共存的情况进行研究，考虑在异构CRN共存的场景下，如何实现CRN的高效通信和公平性、QoS 支持的问题。

文献[11]第一次考虑到了不同CRN共存的情况。如文中所述，两个异构的CRN可能使用不同的传输波形，这使得一个CRN内的次用户无法识别另一个CRN内的波形，如果某一授权信道被占用，当前次用户只知道信道被占用了，但是并不知道占用信道的是主用户还是次用户。而现在大多数提出的MAC层协议都是采用的两状态信道模型，即把信道分为两种状态：忙和空闲。因此，次用户如果检测到信道忙，就只能认为信道被主用户占用了，然后单纯地放弃信道。但是实际上还有可能是另一个CRN内的次用户在占用，这就损害了SU之间的公平性。针对这种情况，文献[11]第一次提出了三状态信道模型，即把“忙”状态进一步划分为“主用户占用”和“次用户占用”两种状态。而且文中设计了一种感知算法：距离估计检测算法，用来检测当前信道具体处于三个状态中的哪一个。文献[12]正是基于这种三状态信道模型设计出了FMAC，遵循FMAC协议的SU节点对于信道忙的状态启用距离估计算法[1判断当前信道上是主用户的信号还是次用户的信号，如果是后者，就采用竞争机制竞争使用信道，改善了次用户之间的公平性。

虽然FMAC改善了公平性，但是SU之间频繁地竞争信道会一定程度上降低信道的吞吐量，同时FMAC太过强调竞争，忽略了空闲信道的充分利用。此外该算法没有QoS的感知与保障机制，不能满足一些用户时延等方面需求。因此，本文在引入三状态模型的基础上，使用信标帧同步的方式，设计了一种新的MAC协议：FQMAC。

本文设计的FQMAC考虑了在异构CRN共存的场景下，如何在保证公平性的前提下，适当地减少竞争，提高信道的吞吐量，同时可以充分地利用空闲信道，并且提供QoS支持的问题。

FQMAC借鉴了文献[10]的无竞争数据传输阶段的思想，将数据传输阶段设计为部分无竞争。并且在此基础上，提出了信道分级和用户分级机制，并为网络中的次用户提供了针对性的QoS 保障。同时本文建立了马尔可夫链模型，进行了理论分析，得出了信道协商与预留阶段的合理时长。经过实验仿真，证明本文的设计在一定程度上提高了信道的利用率，并维护了次用户之间的公平性，提高了网络的吞吐量，而且有效降低了高QoS需求的用户的信道接入延迟，保证了服务质量。

# 1 FQMAC协议设计

同大部分现有文献不同，本文考虑了多个异构CRN 共存的情况,这种异构性，在FMAC论文[12]中也提到了。在信道被异构网络次用户占用的情况下，FAMC让次用户去和占用信道的次用户竞争使用信道，这样就增加了次用户之间的公平性。但是该协议会使SU之间频繁地竞争信道，一定程度上降低了信道的吞吐量，而且FMAC单纯强调竞争，未提及如何有效利用空闲信道。因此本文通过将信道上的时间分为周期性的三个阶段（其中数据传输阶段是无竞争的)，对于异构CRN，设计了FQMAC协议，FQMAC协议可以在保证次用户之间的公平性的前提下，减少一部分竞争，同时为网络中不同的次用户提供不同的QoS 支持。

从可行性和经济性的角度考虑，本文假设每个SU节点都拥有一个半双工收发机。协议设计采用控制信息交换机制（RTS-CTS机制）和信标帧同步机制，这种机制采用的是先对信道进行预约，之后邻居节点各自设置NAV的方式，从而避免了隐藏终端的问题。本文假定在CRN内有一个全局CCC（common controlchannel)，用来交换控制信息。

# 1.1信标周期结构

时间帧被分成周期性的信标间隔BI（BeaconInterval)。SU由周期性的信标信号同步。每当有一个SU想要加入网络时，它首先收听CCC 上的至少一个信标帧的信号，以使其自身与网络的其余部分同步。如果一直没有收听到信标帧信号，它就自己开始发送周期性的信标帧信号，作为本CRN的第一个节点，让以后加入的节点和它保持同步[10]。BI分为三个阶段：感知阶段、竞争CCC信道阶段（信道协商阶段）、数据传输阶段。如图1所示是每一个信标周期的时间结构。

信标 Level1 Level2 Level3 有竞争传输（使用2 信标用户用户 天关关 用户 级信道） 7√ Y不 V 1 / V不 米 A一 感知阶段 1 信道协商与预 一 无竞争传输（使用1 一一 1 留 一 级信道) 1k 11 竞争CCC阶段 11 数据传输阶段 Y） 信标周期 A一 1

# 1.2信道感知

如图1所示，FQMAC协议规定在每一个信标间隔内的第一个阶段为信道感知阶段，在这个阶段SU节点检测可用信道，获取最新的信道信息。在感知阶段，FQMAC协议规定所有的SU用户都不可以进行传输，以便感知结果不受周围SU节点的干扰。每个SU独立地感知信道并在感应阶段结束后取得所有可用信道的列表，并把这个列表保存在当前SU节点。

假设有网络A和网络B，两个网络都是认知无线网络，都可以采用认知的方式使用授权频段。假设网络A中的节点采用本文提出的FQMAC算法，而网络B采用的是其他的认知网络协议。这两个网络为异构网络。

FQMAC采用信标帧同步的方式，将时间划分为信标周期，在信标周期内分别进行信道感知、信道协商和数据传输。因此在信道感知阶段，网络A中的用户都停止发送，进入信道感知状态。而由于网络B为异构网络，所以在网络A中节点进行信道感知的时候，网络B中很多节点可能仍处于通信发送状态，假设B中某对节点此时正使用某个授权信道 $\mathrm { H } _ { 5 }$ 进行数据收发。网络A中节点此时信道感知，可以感知到空闲的授权信道以及被次用户占用的授权频段 $\mathrm { H } _ { 5 }$ 。对于这种情况，普通的认知网络由于仅仅能区分授权频段空闲还是被占用，所以采用的策略就是仅仅使用空闲信道，而放弃对 $\mathrm { H } _ { 5 }$ 信道的使用。这样就授权信道 $\mathrm { H } _ { 5 }$ 而言，就存在一种不公平性，因为正在使用该信道的节点不是主用户。而公平的方式就是网络A中的用户与网络B中的次用户采用竞争的方式使用授权信道 $\mathrm { H } _ { 5 }$ 。因此，FQMAC协议也采用了距离估计算法[1来区分主用户和次用户。

# 1.2.1信道分级机制

FQMAC协议的主要特点便是其信道分级及用户分级机制。信道分级机制的主要思想是在感知阶段，FQMAC采用能量检测技术和距离估计检测算法[II]，检测出信道是处于什么状态，然后根据感知结果分别进行处理：a)把被主用户占用的信道过滤掉;b)把被异构CRN次用户占用的信道作为2级可用信道放入可用信道列表中;c）把空闲的信道作为1级可用信道放入可用信道列表中。这样，SU节点维护的可用信道列表就有了两种可用信道：1级可用信道和2级可用信道，从而允许MAC协议根据次用户的特点，有针对性地为次用户分配适合的信道。

# 1.2.2信道协商与预留

每个有数据帧要发送的SU为了参与信道协商和预留机制必须参与竞争公共控制信道CCC，这个过程发生在信标周期的第二个阶段，即信道协商阶段。竞争策略FQMAC协议放弃了经典的 IEEE802.11 中 DCF(Distributed Coordination Function,分布式协调功能)的二进制指数退避算法，而是采用固定窗口退避算法（取名为FWSB算法（fixedwindow sizebackoffalgorithm))，本文将在1.3.2节作详细介绍。竞争阶段在信标周期的位置如图1所示。

# 1.2.3次用户分级机制

为了满足不同QoS需求的用户，本文设计了用户分级机制，其主要思想是根据次用户节点对自身业务数据特征的认知，依据对时延和传输质量（丢包率）要求的高低，将次用户节点划分为三个等级：

a）level1：传输报警信息等时间敏感性数据，对时延要求较高的次用户。b)level2：传输一般性信息，对时延要求比较一般的用户。c）level3：传输视频、备份文件等对丢包率或时延要求较低的用户。

为了区分次用户，本文选择把次用户划分为三个等级。当然这个数字是可以根据具体情况进行调整的，假如具体网络所处的时域和空域不同，网络的环境和特征可能也不尽相同，对用户通信质量的要求苛刻度也不同，这种情况下可以作相应的调整。但是本文在这里根据大多数普通情况适用的场景，选择将次用户划分为三个等级。

# 1.2.4信道协商阶段的FWSB退避算法

要发送数据的次用户需要竞争CCC信道的使用权，竞争策略本文采用的是固定窗口退避机制，即FWSB算法。此算法为每一个等级的次用户分别设置不同的退避时间窗口。首先设置一个固定窗口值w,则level1用户的退避时间在[0,w-1]内随机产生，level2用户的退避时间在[w,2w-1]范围内随机产生，level3用户的退避时间在[2w,3w-1]之间随机产生。通过为三个等级的次用户设置完全不重叠的退避窗口，并且等级越高的次用户退避窗口越小，保证了等级高的次用户总是更早地接入CCC信道（公共控制信道)，低等级用户基本不会抢在高等级用户之前获得CCC信道的使用权。并且本协议规定，所有等级的次用户预约信道均优先从1级可用信道中选择，从而使得1级可用信道总是优先被更高等级的用户预约到，同时高等级用户数量较少的情况下，较低等级的次用户也可以预约到1级信道，保证了1级信道的充分利用。

本文没有采用二进制指数退避算法，而是规定次用户在每一个退避阶段的退避窗口均是固定的，均分别和第一个退避阶段的退避窗口相同。例如对level1用户来说，当其退避计时器为0后进行数据传输，但是发生了碰撞，传输失败，那么它要进入第二个退避阶段重新开始一次随机退避，但是其退避计时器取值依然是从[0,w-1]中随机选取一个，如果计时器为0后再次发生碰撞，依然是从[0,w-1]中随机选取一个值作为退避计时器的值。同样的，level2用户其退避窗口始终是[w,2w-1]，level3用户始终是[2w,3w-1]。对于二进制指数退避算法，文献[13]指出802.11网络由于采用了二进制指数退避算法导致公平性表现并不令人满意，文献[14]也提到不同竞争窗口大小（如（0,7)和（0,15)）的用户接入信道的概率不一样，会导致用户之间比较差的公平性。因此，从保障公平性的角度考虑，不适宜采用经典的二进制指数退避算法。另一方面，固定窗口退避严格保证了不同等级次用户的退避窗口在任何时候都和其他等级次用户的退避窗口是非重叠的，高等级用户的退避窗口是严格小于低等级用户的退避窗口的，这样使得三类次用户有较好的区分，保证了高等级次用户总是比低等级次用户优先获得CCC的使用权，并进而优先预约到1级信道。

同时，为了减小放弃二进制指数退避算法带来的碰撞概率增大的影响，可以把w的值设置的稍大一些，这样不同次用户每次选择到相同退避时间的概率可以得到相应地减小。

# 1.3.3信道协商阶段信道的预约过程

次用户首先通过FWSB 算法竞争CCC的使用权，取得使用权的次用户开始信道协商过程。Level1用户会优先选择等级1的可用信道（如果没有等级1的可用信道，就从等级2的可用信道中选择，在频谱资源紧缺的情况下，本协议此时更体现了它的优越性)，然后封装在RTS中发送给目的节点，目的节点收到RTS后，从自己信道列表中的1等级信道中选择与源节点的公共信道，然后封装在CTS中发送给源节点，源节点收到CTS后，再发送一个CRTS给目的节点，完成信道预约过程。对于level3节点，则一般预约到2等级信道。Level2用户的QoS需求属于较普通的水平，因此FQMAC规定它们的优先级处在level1用户和level3用户之间，相应的它们的退避窗口也处在两者中间。因此，level2用户既可能预约到1级可用信道，也可能预约到2级可用信道。同时，按照FQMAC的机制，如果1级信道资源紧缺的情况下，level1用户也可能预约到2级信道。同理，1级信道资源富裕的情况下，level3用户也可以预约到1级信道。这样就保证了1级可用信道不会被浪费，而不同QoS 需求的用户又分别获取到的是相对合适的信道，保证了网络资源的合理分配，并使网络的性能指标达到最大化。

# 1.3数据传输

在竞争阶段结束之后所有完成信道预留工作的节点对开始在各自的信道上独立且并行地发送数据。由于高等级用户通常预约到的是1级信道，因此数据传输阶段通常是无竞争的，这有效提高了信道的利用率。而低等级用户通常预约到的是2级信道，因此，低等级用户的数据传输阶段通常是有竞争的。数据传输阶段的竞争接入策略本文采用802.11网络DCF机制的CSMA/CA技术。而在数据传输阶段，次用户的数据传输是有竞争的还是无竞争的，从根本上取决于预约到的信道是1级还是2级。若是1级信道数据传输就是无竞争的，否则就是有竞争的。另外，如果还有节点对未在协商阶段完成信道预留，则只能等到下一个信标周期重新和所有的节点竞争CCC信道。数据传输阶段结束之后，所有节点清空NAV向量，又进入下一个信标周期，继续从感知阶段开始感知信道。

# 2 FQMAC协议建模及分析

如1.1节所述，每一个信标周期分为三个阶段，感知阶段、信道协商阶段、数据传输阶段。对于感知阶段，由于此阶段规定所有节点都不能进行数据传输，所有节点保持同步，统一进行频谱感知，而感知效率又和硬件性能有关（目前的认知无线电节点硬件性能还不足以在有限的感知时间内感知所有的频谱范围，只能感知部分频谱，而关于感知频带的选择又是另外一个研究领域，本文的假定是认知节点可以感知所有频带，关于部分感知的研究本文在这里不做赘述)，受其他因素影响不大，因此可以将感知阶段的时长固定为一个确定的值。同样的，数据传输阶段的时长主要和用户本身的业务数据量以及固定的信道传输速率有关，也可以定为一个固定值。基于上述原因，本文在此只讨论有意义的第二阶段的时长。本文假设一个网络域中有n个节点，其中 $\mathbf { n } _ { 1 }$ 个level1用户， ${ \bf n } _ { 2 }$ 个level2用户 ${ \bf n } _ { 3 }$ 个level3用户。假设每一个节点在上一次成功发送之后，立即有另外一个帧要发送。让f(t)代表在时隙t某一个节点的退避窗口大小。同时，本文还要定义一个特殊的随机过程 $\begin{array} { r } { \mathbf { g } ( \mathfrak { t } ) . } \end{array}$ 代表在时间t时节点所处的退避阶段，显然，退避阶段取值始终为0。在这种情况下，随机过程 $\{ \mathrm { g ( t ) , f ( t ) } \}$ 是一个离散时间的马尔可夫链。Level1用户、level2用户、level3用户的状态转移图分别如图2\~4所示。

![](images/5b051ce2b9b9914cf0a255610fa347bd48d3537151fb543537b78d1120a321fc.jpg)  
图2level1节点马尔可夫链的状态转移

![](images/15160adedd47372c50a4b92b26476346f18176401a19ad4c7615b42b305a8705.jpg)  
Fig.2State transition of levell node Markov chain   
图3level2节点马尔可夫链的状态转移

![](images/56235170e17b7027256ededc67955b7410fe70e4d3a38785e08cd98ae1787e43.jpg)  
Fig.3State transition of level2 node Markov chain   
图4level3节点的马尔可夫链状态转移  
Fig.4State transition of level3 node Markov chain

显然节点某一个状态所处的退避阶段皆为0，让s表示节点某一个状态当前的退避窗口实际大小。那么状态{0，s}可以表示图中的所有状态。另外令 $\mathfrak { p } _ { \mathtt { c } }$ 表示发送帧发生碰撞的概率，Po表示信道为忙的概率。如图中所示，各状态之间的转移概率如下：

a）当站点感知到信道空闲时，退避计时器减1，发生状态转移的概率。

$$
p \{ 0 , \mathrm { s } - 1 | 0 , s \} = 1 - p _ { o }
$$

b）当站点检测到信道忙，冻结退避计时器的转移概率。

$$
p \{ 0 , \mathrm { s } | 0 , s \} = p _ { o }
$$

c）根据CSMA/CA机制的规定，当站点的发送失败时，要开始重传，就要重新执行CSMA/CA，本文采用这一规定，而站点发送失败的概率为 $\mathfrak { p } _ { \mathtt { c } }$ （和信道状态无关，因为退避计时器为0时，信道必定处于空闲状态),因此level1站点状态转移到{0,s} $0 { \leqslant } \mathbf { s } { \leqslant } \mathbf { w } { - } 1 .$ 状态的某一个的概率为 $\mathrm { p } \mathrm { c } / \mathrm { w }$ ，level2节点转移到{0，s}( $\begin{array} { r } { \mathbf { w } \leqslant \mathbf { s } \leqslant 2 \mathbf { w } - \mathbf { l } \dot { } . } \end{array}$ 状态的某一个的概率也为 $\mathrm { p } _ { \mathrm { c } } / \mathrm { w }$ ，level3节点转移到{0，s}( $2 \mathrm { w } { \leqslant } \mathrm { s } { \leqslant } 3 \mathrm { w } - 1 \mathrm { \ r { I } } ,$ 状态的某一个的概率也为 $\mathrm { \ p c / w }$ 。根据CSMA/CA机制的规定，当一次成功的发送结束后，再接着发送第2个帧也要重新开始执行CSMA/CA，但是本文在此利用退避算法得到CCC信道使用权后，只要一次发送成功预约到信道就达到目的，不会再发送第二次，因此在这里不考虑发送成功后次用户节点的状态转移概率。因此，对于三类等级的次用户，从{0.0}状态转移到{0,s}状态的概率各为 $\mathrm { p } \mathrm { c } / \mathrm { w }$ 。

$$
\begin{array} { r l } { p \{ 0 , \mathrm { s } \mid 0 , 0 \} = \mathrm { p } _ { c } / \mathrm { w } \quad } & { \quad ( l e \nu e l 1 : 0 \leq s \leq w - 1 ) } \\ { p \{ 0 , \mathrm { s } \mid 0 , 0 \} = \mathrm { p } _ { c } / w \quad } & { \quad ( l e \nu e l 2 : w \leq s \leq 2 w - 1 ) } \\ { p \{ 0 , \mathrm { s } \mid 0 , 0 \} = \mathrm { p } _ { c } / \mathrm { w } \quad } & { \quad ( l e \nu e l 3 : 2 w \leq s \leq 3 w - 1 ) } \end{array}
$$

根据文献[15],本文让 $\nu _ { \scriptscriptstyle 0 , s } = \operatorname* { l i m } _ { t \to \infty } P \{ 0 , f ( t ) = s \} , s \in ( 0 , w - 1 )$ 作为马尔可夫链的平稳分布。根据马尔可夫链的规律，由文献[15]的结论可得，平稳状态下以下等式成立：

$$
\nu _ { 0 , s } = \frac { w - s } { w } \nu _ { 0 , 0 } \qquad \mathrm { ~ s \in ( 0 , \it w - 1 ) ~ }
$$

同理可得， $\nu _ { 0 , s } = \frac { 2 w - s } { 2 w } \nu _ { 0 , 0 } , ~ s \in ( 0 , 2 w - 1 )$ $\nu _ { 0 , s } = \frac { 3 w - s } { 3 w } \nu _ { 0 , 0 }$ Vo.o，s∈(0,3w-1）。另外根据概率守恒规律，可得以下等式：

$$
\sum _ { s = 0 } ^ { \mathrm { w } - 1 } \nu _ { 0 , s } = 1
$$

通过使用方程式（1）和（2)，可得对于level1节点：

$$
\nu _ { 0 , 0 ( \mathrm { l e v e l 1 } ) } = \frac { 2 } { w + 1 }
$$

同理可求对于level2节点：

$$
\nu _ { 0 , 0 ( \mathrm { l e v e l 2 } ) } = \frac { 2 } { 2 w + 1 }
$$

同理可求对于level3节点：

$$
\nu _ { 0 , 0 ( \mathrm { l e v e l 3 } ) } = \frac { 2 } { 3 w + 1 }
$$

当CCC信道空闲时，本文把时间划分为多个时隙，时隙长度为e。μ作为一个站点在一个时隙内开始发送信息的概率。可知当退避计时器等于0时，对于本文的马尔可夫链模型，也就是站点处在 $^ { \{ 0 , 0 \} }$ 状态时站点开始发送数据，因此 $\mu$ 可以表示为

$$
\scriptstyle \mu = \mathbf { b } _ { 0 , 0 }
$$

而对于三类等级次用户， $\mu$ 的值分别为 $\mu _ { 1 } { = } \frac { 2 } { \mathrm { w } { + } 1 }$

$\mu _ { 2 } { = } \frac { 2 } { 2 { \bf w } + 1 } \mathrm { ~  ~ \cdot ~ } \mu _ { 3 } { = } \frac { 2 } { 3 { \bf w } + 1 }$ 。同时，在一个时隙内，信道为忙的概率(假设主用户没有使用信道)，即 $\mathfrak { n }$ 个次用户节点至少进行一次数据传输的概率，可以用式(7)表示。

$$
{ \sf p } _ { \mathrm { { o } } } = 1 - ( 1 - \mu _ { \mathrm { { 1 } } } ) ^ { n _ { \mathrm { { 1 } } } } ( 1 \mathrm { - } \mu _ { \mathrm { { 2 } } } ) ^ { n _ { \mathrm { { 2 } } } } ( 1 \mathrm { - } \mu _ { \mathrm { { 3 } } } ) ^ { n _ { \mathrm { { 3 } } } }
$$

在至少有一个站点发送数据（即 ${ \mathfrak { p } } _ { 0 }$ ）的条件下，一次传输是成功的概率即为在信道上只有一个站点传输的概率，设在一个时隙内只有一个站点发送成功的概率为 $\mathfrak { p } _ { \mathrm { m } }$ ，则 $\mathfrak { p } _ { \mathrm { m } }$ 的值如式（8）所示。

那么在竞争CCC信道使用权阶段，让 $\mathfrak { p } _ { \mathtt { n } }$ 表示在一个时隙内信道为空的概率， $\mathsf { p } _ { \mathrm { u } }$ 表示在一个时隙内成功完成一次信息交换的概率，pd 表示未完成信息交换的概率，那么pn=1-P，Pu=PoPm’Pd=P(l-Pm），在竞争CCC 信道阶段成功预约到一条信道的平均时间 $\mathfrak { n }$ 为

$$
\begin{array} { c } { { ( 1 - \mu _ { 1 } ) ^ { n _ { 1 } - 1 } ( 1 - \mu _ { 2 } ) ^ { n _ { 2 } - 1 } ( 1 - \mu _ { 3 } ) ^ { n _ { 3 } - 1 } ( n _ { 1 } \mu _ { 1 } ( 1 - \mu _ { 2 } ) ( 1 - \mu _ { 3 } ) + } } \\ { { p _ { m } = \displaystyle \frac { n _ { 2 } \mu _ { 2 } ( 1 - \mu _ { 1 } ) ( 1 - \mu _ { 3 } ) + n _ { 3 } \mu _ { 3 } ( 1 - \mu _ { 2 } ) ( 1 - \mu _ { 1 } ) ) } { p _ { o } } } } \end{array}
$$

$$
\eta = \frac { p _ { n } e + p _ { u } t _ { u } + p _ { d } t _ { d } } { p _ { u } }
$$

$\mathbf { t } _ { \mathrm { u } }$ 是一次成功的信息交换占用信道的平均时间，tu是信道处于碰撞状态的平均时间，e是时隙的长度。其中t =RTS+σ+SIFS+CTS+O+SIFS+CRTS，σ是传播时延。因为如果RTS发送失败，信道经过一个DIFS（DistributedInter-frame Spacing,分布式帧间间隔)的时间就会重新变为空闲状态，所以 $\mathbf { t } _ { \mathrm { d } } = R T S + D I F S$ 。假设竞争CCC 信道阶段（信道协商与预留阶段）的时长为T，则根据上述结论可以得出信道协商与预留阶段的合理时长。其时长等于预约到一条信道的平均时间η与当前CRN 的可用信道数量的积，假设当前CRN共有 $\mathbf { n } _ { \mathrm { { c h } } }$ 条可用信道，那么可以保证成功预约到所有可用信道的信道协商与预留阶段的时长可近似为 $n _ { c h } \eta$ ，即

$$
T = \frac { \boldsymbol { \mathrm { n } } _ { c h } p _ { n } \boldsymbol { e } + \boldsymbol { n } _ { c h } p _ { u } t _ { u } + \boldsymbol { n } _ { c h } p _ { d } t _ { d } } { p _ { u } }
$$

# 3 实验仿真

本文考虑这样一个网络模型，在一个认知无线电网络A内所有的次用户节点均匀地分布在网络中，在这个网络域中有3个level1的次用户，2个level3的次用户。同时有一个共存的异构的认知无线电网络B，它有2个次用户。在当前区域内有固定可用的5个授权信道，主用户的到达概率为 ${ \mathfrak { p } } _ { \mathrm { u } }$ 。同时假定网络A中的次用户开始通信前，网络B中的2个次用户已经占用了2个授权信道。本文为了方便仿真，假设感知阶段次用户可以感知所有授权信道（通常在较短的时间内，次用户只能感知部分信道，关于部分感知的问题本文在这里不做展开)。并规定在数据传输阶段，每个预约到信道的次用户均有5个连续的帧发送，帧大小为256Byte。在这样的设置下，本文利用

OMNeT $^ { + + }$ 仿真工具进行了如下仿真实验。

本文以FQMAC分别和OMC-MAC[I0]（同样使用公共控制信道)，以及ACAP-MAC[1作比较。图5展示的是比较的仿真结果（纵坐标是归一化后的结果)。显然FQMAC的吞吐量性能要明显好于OMC-MAC和ACAP-MAC。随着PU（主用户）的到达概率逐渐变大，授权信道的可用性逐渐变小，三种通信协议的吞吐量都随之减小。但是很明显，无论信道可用性是怎样的，FQMAC 的吞吐量都比另外两种MAC 协议的吞吐量要好。这主要是因为FQMAC使得原来在OMC-MAC和ACAP-MAC下不能使用的另外异构网络的次用户占用的信道变为通过竞争可用，尽管使用这些信道进行数据传输是有竞争的，但是仍然增加了可用信道的数量。而图5所示的仿真结果从数据上较直观地展示了这一效果。

![](images/5399acc3c2e111183762ecf3ee796e7f8e222c628db2d5834a9a634e4af1a46b.jpg)  
图5不同PU到达概率下的饱和吞吐量

同样地，本文还是考虑的上述实验背景，在有2个异构网络次用户占用了2个授权信道的情况下，进行的本项实验。本文用OMC-MAC和FQMAC做比较（OMC-MAC也是考虑了QoS 需求的MAC协议)，仿真结果如图6所示，其中纵坐标的数值是归一化后的结果。

![](images/97c596a0dde8eb898a087cc5fa08f7bc45290417318987037d88d61a079ff5f5.jpg)  
Fig.5Saturation throughput under different PU arrival probabilities   
图6平均信道接入延时  
Fig.6Average access delay of channel   
图7从△1至 $ { \Delta } 2 0$ 的Jain指数Fig.7Jain index from△1 to △20

根据结果可以看出，QoS用户（在FQMAC中的level1用户）在OMC-MAC和FQMAC下的平均延时差不多，但是普通用户的情况两者差距较大。可以看到OMC-MAC下的普通用户延时远远高于FQMAC下普通用户的延时，而且OMC-MAC下普通用户的延时变化较小。这主要是因为在OMC-MAC下，所有用户都只能感知到3个空闲信道，当QoS用户存在的情况下，2个普通次用户基本上只能等到QoS用户不使用信道的时候才可以接入信道，而如果QoS用户一段时间内一直有数据要传输的情况下，每一个信标周期它们都会抢信道，普通次用户只能一直等待甚至被“饿死”。而FQMAC下2个普通用户可以和异构网络的次用户竞争使用信道，因此平均接入延时明显要好于OMC-MAC。而对于同一协议下的普通用户和高级别的QoS用户而言，QoS用户的平均接入延时均明显好于普通用户，这说明两种协议均较好地满足了QoS用户的需求，但是在满足QoS用户需求的前提下，FQMAC在普通用户的平均延时方面表现要好于OMC-MAC。

为了测试 FQMAC 协议的公平性，本文引入了文献[12]中提到的Jain指数(JainIndex）。假设有 $\mathrm { ~ N ~ }$ 个共存的CRN（CRN），让△表示一小段时间，称为一个cycle。记录下每一个CRN 在前 K个cycle 的传输时间，让向量 $\vec { T } ( k ) = [ T _ { 1 } ( k ) , . . . , T _ { N } ( k ) ]$ 表示 $\mathrm { ~ N ~ }$ 个 CRN在前k个cycle $( \mathbf { k } \Delta$ ）的传输时间，在 $1 { \le } \mathbf { k } \le K$ 的情况下，Jain指数可以表示为：

$$
J ( \vec { T } ( \mathbf { k } ) ) { = } \frac { \vec { ( 1 \cdot T } ^ { T } ( k ) ) ^ { 2 } } { N \left\| \vec { T } ( k ) \right\| ^ { 2 } }
$$

其中 $\stackrel { \triangledown } { \vec { 1 } } = [ 1 , 1 , . . . , 1 ]$ 是一个1行N列的行向量， $\Vec { T } ( \mathbf { k } )$ 的转置矩阵是一个N行1列的列向量。从而根据记录下的传输时间和 $\mathrm { ~ N ~ }$ 可求出Jain指数。Jain指数越大，表明公平性越好，理想情况下，Jain 指数为1。本文这里让 $\Delta$ 为连续发送5个帧所需要的时间，然后分别取N值为5和10（即分别为5个CRN共存的情况和10个CRN共存的情况）进行测试，仿真结果如图7所示。

1分 888888888888880.8 T 44444 00000000000000①区  
0.6 000  
u O 四口四四四四□四日口口□0A  
0.4 OMC-MAC-5CRNS1 FQMAC-5CRNS0.2 □ OMC-MAC-10 CRNS中 FQMAC-10 CRNS00 2 4 6 8 10 12 14 16 18 20时间段数量（△）

从图7中可以看出，在共存CRN数量相同的前提下，FQMAC的公平性指数明显比OMC-MAC要高，这说明FQMAC的公平性比OMC-MAC的公平性要好，这主要是因为FQMAC使当前网络次用户有了和异构网络的次用户竞争信道的能力。从图7中也可以看出，当CRN数目增加的情况下，OMC-MAC的公平性明显下降了许多，这说明共存CRN的数量对公平性的影响较大，而且共存CRN数越多，公平性越差。但是相对来说，随着CRN数的增加，FQMAC的公平性指数下降的不是很明显，这说明在共存的CRN数量变化的情况下，FQMAC的公平性表现也很好。

# 4 结束语

本文提出了一种考虑异构网络共存情况的认知无线电网络的MAC协议FQMAC，本协议确保了在异构网络共存情况下可用信道数量的最大化，使得次用户可以使用更多的信道进行传输。并在此基础上提出了信道分级和次用户分级机制，及基于此的QoS保障机制，根据可用信道的特性进行等级划分，使得次用户的信道选择更加合理，保障了对QoS要求比较高的次用户的需求。同时所有用户均按照等级从高到低预约信道，保证了优质信道的优先利用，使得信道资源的利用更高效，也进一步优化了网络的性能。并通过建立马尔可夫链模型进行理论分析，得出了信道协商与预留阶段的合理时长的理论值。通过仿真实验表明，同样的背景下，FQMAC的网络吞吐量比参照的MAC协议有了较大的提升。同时，FQMAC对普通用户的信道接入延时对比参考协议也有了较好的改善。由于采用了三状态信道模型，使次用户可以和异构网络次用户竞争使用授权信道，也很好地改善了网络中次用户的公平性。同时，本文所采用的控制信息交换机制（RTS-CTS机制)，避免了隐藏终端的问题，同时降低了感知错误导致次用户和主用户的冲突概率。另外，在数据传输阶段高等级次用户的传输通常是无竞争的，这也有效地提高了频谱空洞的利用率。

# 参考文献：

[1]Hsu A,Wei D,Kuo C.A cognitive MAC protocol using statistical channel allocation for wireless ad-hoc networks [C]//Proc of IEEE WCNC. Piscataway,NJ:IEEE Press,2007 :105-110.   
[2]Du Manyi, Zheng Meng,Song Min.An Adaptive Preamble Sampling Based MAC Protocol For Cognitive Radio Sensor Networks [J].IEEE Sensors Letters,2018,2(1): 10-15.   
[3]MansoorN,IslamA,Zareei M,et al.RARE:ASpectrum Aware Cross-Layer MAC Protocol for Cognitive Radio Ad-Hoc Networks [J]. IEEE Access, 2018 (6): 22210 -22227.   
[4]Cheng Wenchi, Zhang Xi, Zhang Hailin.Pilot-based full-duplex spectrumsensing and multichannel-MAC over non-time-slotted cognitive radio networks [C]//Proc of IEEE Conference on Computer Communications. Piscataway,NJ:IEEE Press,2017:1-9.   
[5]Kadam S,Raut C S,Kasbekar G S.Fast node cardinality estimation and cognitive MAC protocol design for heterogeneous M2M networks [C]//Proc of IEEE Global Communications Conference.Piscataway,NJ: IEEE Press, 2017: 1-7.   
[6] Chu T, Zepernick H, Phan H. MAC protocol for opportunistic spectrum access in multi-channel cognitive relay networks [C]//Proc ofthe 85th IEEE Vehicular Technology Conference.Piscataway,NJ: IEEE Press,2017: 1-7.   
[7]Liu Yi,Yu Rong,Pan Miao,et al. SD-MAC: spectrum database-driven MAC protocol for cognitive machine-to-machine networks [J]. IEEE Trans on Vehicular Technology,2017,66 (2): 1456-1467.   
[8]Luo Yu,Pu Lina,Peng Zheng,et al.Dynamic control channel MAC for underwater cognitive acoustic networks [C]// Proc of the 35th Annual IEEE International Conference on Computer Communications. Piscataway, NJ: IEEE Press,2016: 1-9.   
[9] Long L, Hossain E. A MAC protocol for opportunistic spectrum access in cognitive radio networks [C]//Proc of IEEE WCNC.Piscataway,NV, NJ: IEEE Press,2008: 1426-1430.   
[10] Jha S C,Phuyal U,M. Rashi M,et al. Design of OMC-MAC: an opportunistic multi-channel MAC with QoS provisioning for distributed cognitive radio networks [J].IEEE Trans on Wireless Communications, 2011,10 (1): 3414-3425.   
[11] Zhao Yanxiao,Song Min, Xin Chunsheng.Spectrum sensing based on three state model to accomplish al-level fairness for co-existing multiple cognitive radio networks [C]//Proc of IEEE International Conference on Computer Communications.Piscataway,NJ: IEEE Pres,2012:1782-1790.   
[12] Zhao Yanxiao,Song Min,Xin Chunsheng.FMAC: AFair MAC Protocol for Coexisting Cognitive Radio Networks [C]// Proc of IEEE International Conference on Computer Communications. Piscataway, NJ: IEEE Press, 2013: 1474-1482.   
[13] Berger-Sabbatel G,Duda A,Heusse M,et al. Short-term fairness of 802.11 networks with several hosts [J].Mobile and Wireless Communication Networks,2005,1 (1): 263-274.   
[14] Bianchi G.Performance analysis of the ieee 8O2.11 distributed coordination function [J]. IEEE Journal on Selected Areas in Communications,2000,18 (1): 535-547.   
[15] Ziouva E,Antonakopoulos T. CSMA//CA performance under high traffic conditions: throughput and delay analysis [J]. Computer Communications, 2002,25 (3):313-321.   
[16] Anany M, Sayed S G. Opportunistic multi-channel MAC protocol for cognitive radio networks [C]// Proc of IEEE Canadian Conference on Electrical and Computer Engineering Piscataway.,NJ: IEEE Press,2016: 1-6.