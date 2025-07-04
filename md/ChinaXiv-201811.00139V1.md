# 基于IEEE802.15.6的无线体域网自适应MAC协议

袁德颖1，郑国强1,²，马华红1，吴红海1，李济顺1,2,3(1.河南科技大学 信息工程学院，河南 洛阳 471023;2.河南科技大学 河南省机械设计及传动系统重点实验室，河南洛阳471003;3．矿山重型装备国家重点实验室，河南 洛阳471039)

摘要：针对无线体域网MAC协议自适应性不高且能效低的问题，提出一种基于IEEE802.15.6的无线体域网自适应MAC 协议（A-MAC）。协议对IEEE802.15.6的超帧结构进行改进，竞争接入阶段和非竞争接入阶段的长度根据产生各优先级数据的节点所占的比例进行调整。竞争接入阶段又被划分为三个子阶段，子阶段的长度根据数据优先级情况进行动态调整。所有节点在竞争接入阶段按照信道接入策略竞争接入信道。最后仿真结果表明，在吞吐量、能耗和网络时延方面，使用A-MAC协议的网络性能明显优于使用IEEE802.15.6MAC协议和CA-MAC 协议的网络性能。

关键词：无线体域网；IEEE802.15.6；自适应；MAC协议 中图分类号：TP393 doi: 10.19734/j.issn.1001-3695.2018.08.0472

# Adaptive MAC protocol based on IEEE 802.15.6 for wireless body area networks

Yuan Deying1, Zheng Guoqiang1,², Ma Huahong1,Wu Honghai1,Li Jishun1,2, 3 (1.SchoolofInformation EngineeringHenan UniversityofSience&Technology,Luoyang Henan 471023,China;2.Henan KeyLaboratoryfor Machinery Design &Transmission System Henan UniversityofScience&Technology,Luoyang Henan 471003, China; 3. State Key Laboratory of Mining Heavy Equipment, Luoyang Henan 471039, China)

Abstract: Aiming atthe problem oflow adaptability and low energy eficiencyof MAC protocol of the wirelessbody area network,this paper proposes an adaptive MAC protocol based on IEEE802.15.6 for wirelessbody area networks (A-MAC). The protocolimprovesthesuperframestructureofIEEE8O2.15.6,andthelengthsofthecontentionphaseand thenon-contention access phase are adjusted acording to the proportionof nodes generating each prioritydata.Thecontention access pase is furtherdivided intothreesub-phases,andthelengthofthesub-haseisdynamicalladjustedaccordingtothedatapriority.Al nodes compete foraccesschanels inaccordance withthechannelaccess policyduringthecontentionaccessphase.Fially,the simulationresultsshow that thenetwork performanceusing A-MAC protocol is significantly beter than the network performance using IEEE 802.15.6 MAC protocol and CA-MAC protocol in terms of throughput, power consumption and network delay.

Key words:wireless body area network; IEEE 802.15.6;adaptive; MAC protocol

# 0 引言

无线体域网（wireless body area network，WBAN）[1]是以人体为中心，由附着在人体表面或者植入人体内部的专用传感器和存在于人体周围的设备（如手机、PDA等）相互连接形成的通信网络。该网络能够连续监测人体的各种生理参数（如心率，体温，血压，脑电图（EEG），心电图（ECG）等）以及身体运动状态和周边环境信息[2]，这些监测信息可以由个人电子设备或者手机收集，并转发给远程监护中心，其广泛应用于远程医疗、娱乐活动、应急处理、体育训练和保健服务等方面[3，4]。

在无线体域网中，媒体访问控制（mediumaccesscontrol，MAC）协议决定了无线信道的使用方式，负责节点的冲突检测与处理、优先级控制、时隙分配以及节点的传递顺序，因此MAC协议的设计对于无线体域网的可靠性和能效性发挥着主要作用。MAC协议处于无线体域网的物理层和网络层之间，对无线体域网的性能有决定性的影响，是保证无线体域网有效通信的关键技术之一。无线体域网的性能，如网络吞吐量、传输时延、可靠性以及网络能耗等都与所采用的 MAC 协议密切相关[5]。

相对于传统的无线传感器网络，无线体域网有很多独特的特征：应用载体为人，节点尺寸很小；通信距离短，网络规模小；传感器节点能量有限；数据发送要求安全性和实时性等[6]。此外，在无线体域网中，主要是以人为载体，很多设备都是工作在人体表面或者身体内，由于人运动状态的改变，网络拓扑结构易发生变化，或者由于人身体健康等原因，网络业务流量波动比较大，需要网络有很强的自适应性。因此，传统无线传感器网络的MAC协议，已不能直接应用于无线体域网，必须设计新的满足无线体域网特征和需求的MAC协议。本文研究一种基于IEEE802.15.6的无线体域网自适应MAC协议。该协议将提高无线体域网在吞吐量、能耗以及延时等方面的性能。

# 1 相关工作

# 1.1 IEEE802.15.6协议概述

IEEE802.15.6是专为体域网制定的通信标准，其规定的接入模式主要有三种：带信标周期（超帧）的信标模式、带信标周期的非信标模式和无信标周期的非信标模式。本文主要研究带信标周期的信标模式，其超帧结构被划分为9个阶段，如图1所示，分别是信标阶段（B）、独占接入阶段1（EAP1）、随机接入阶段1（RAP1）、管理接入阶段1（MAP1）、独占接入阶段2（EAP2）、随机接入阶段2（EAP2）、管理接入阶段2（MAP2）、信标2阶段（B2）和竞争接入阶段（CAP）。

![](images/4c14f284490adc9734e1dae045a1433b36cee9f775023c93e0e6d5454fd9aa42.jpg)  
图1 IEEE802.15.6超帧结构  
Fig.1IEEE 802.15.6 superframe structure

在这9个阶段中，除信标期B和B2外，其他阶段主要采用两种接入机制：竞争机制和调度机制。EAP1、RAP1、EAP2、RAP2和CAP五个阶段采用的是竞争机制，节点主要使用CSMA/CA或时隙Aloha方法抢占信道并进行数据的传递；MAP1和MAP2采用的是调度机制，协调器根据传递需求和信道状态为节点分配传递时隙，节点只在所分配的时隙中传递数据，其他阶段进入睡眠状态。

IEEE802.15.6中还定义了用户优先级（UP）来降低冲突概率。在CSMA/CA竞争接入机制中，节点主要维护三个参数，即回退计数器（Bake-offCounter，BC），竞争窗口（ContentionWindow，CW）和重传次数R。当节点有数据要发送时，退避计数器取均匀分布于区间[1,CW]上随机一个整数作为其初始值。其中BC用于记录回退的次数，当BC为0时，节点发送数据。CW为当前竞争窗口的大小，即当节点检测到信道空闲后，为了避免碰撞，并不立即发送数据，而是等待一段随机时间。等待时间的长短由CW取值决定，其取值范围为[CWmin,CWmax]，不同优先级的节点对应不同的CWmin和CWmax，如表1表示。

表1不同优先级对应的竞争窗口值  
Table1Contention window values for different priorities   

<html><body><table><tr><td>用户优先级 (UP)</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td></tr><tr><td>CWmin</td><td>16</td><td>16</td><td>8</td><td>8</td><td>4</td><td>4</td><td>2</td><td>1</td></tr><tr><td>CWmax</td><td>64</td><td>32</td><td>32</td><td>16</td><td>16</td><td>8</td><td>8</td><td>4</td></tr></table></body></html>

从表1中可以看出，用户优先级越高，竞争窗口长度越小，接入信道的概率就越大。

# 1.2相关MAC协议

IEEE802.15.6标准的出现推动了无线体域网的快速发展，国内外也掀起了一股研究WBAN的热潮，很多企业和研究机构都积极投身于对无线体域网的研究。因此，近年来在无线体域网的MAC协议方面取得了不小的研究成果。

在文献[8]中，提出一种基于情景感知的MAC协议（CA-MAC），其采用混合超帧结构，根据流量感知进行时隙分配，根据信道感知进行接入策略分配，但在竞争接入阶段，没有考虑对不同的节点数据类型进行区别对待。文献[9]从优先级控制时隙分配等方面对IEEE802.15.6协议进行改进，研究一种高效节能的MAC层协议（HE-MAC），从而达到降低能耗、提高网络可靠性的目的。文献[10]中提出一种自适应MAC协议，其采用TDMA方法接入信道，同时定义合适的同步方案以避免碰撞。文献[11]中法国学者基于IEEE802.15.6的超帧结构提出了一种基于优先级的混合MAC协议（PMAC），其将信道分为数据信道和控制信道，优先考虑生命关键业务，同时使用睡眠模式以节省无线传感器的能量，延长网络寿命。该协议能够保证紧急业务的最小传输延时，但是忽略了体域网中业务量很大的周期数据的传递问题。文献[12]提出一种基于优先级的MAC 协议，其设计非紧急数据在竞争接入期内传递，在非竞争接入期内传递紧急数据，中心节点根据优先级为普通节点分配时隙，能够降低紧急数据的传输冲突率，减少碰撞概率，从而降低能耗，减少紧急数据的传输延时。医疗应急机构MAC协议（MEBMAC）平衡了能源效率和服务质量的矛盾要求，利用空闲时隙为紧急业务插入附加的监听窗口机会，而不影响网络吞吐量，通过为紧急数据访问提供长的超帧期来降低紧急数据访问延迟[13]。

根据以上研究背景，目前研究的无线体域网MAC协议主要存在以下问题：无线体域网的数据类型中，周期数据占据很大的业务量，周期数据的延时是影响网络延时的关键因素之一；MAC协议的各接入期的长度比例固定，当网络业务流量变化时，无法自适应调节；在竞争接入阶段，所有需要发送数据的节点都采用CSMA/CA机制竞争接入信道，没有区分优先级，导致碰撞概率大，网络时延比较长，且能耗严重；在非竞争接入阶段，如果时隙分配不足或分配过多，会导致时延增加或者时隙浪费。

为了解决以上问题，本文研究一种基于IEEE802.15.6的无线体域网自适应MAC协议（A-MAC）。该协议在IEEE802.15.6MAC协议的基础上调整超帧结构，将业务类型划分为不同的优先级，同时根据业务量变化进行动态时隙分配，从而减少网络时延，降低网络能耗，提高网络自适应性。

# 2 A-MAC协议设计

假设网络采用的是星形拓扑结构，包括1个协调器和N个传感器节点。由于身体距离有限，传感器节点都位于协调器的感知范围内。传感器节点一般由电池供电且位于人体体内或者体表，因此在使用过程中不方便充电或者更换电池。每个节点仅采集人体的一项生理信息，如血压、体温、心电、声音和图像等。协调器节点由手机充当，方便充电。每个传感器节点的初始能量相同，不考虑协调器的能耗问题。

基于以上网络模型与假设，本文研究一种基于IEEE802.15.6的无线体域网自适应MAC协议（A-MAC）。本节详细论述了A-MAC协议，主要讨论了优先级分配策略，超帧结构，MAC层协议工作过程以及信道接入过程等。

# 2.1 优先级分配策略

无线体域网在实际应用中，主要会产生三类数据，第一类是各个传感器节点周期性产生的数据。这些数据业务流量比较大，周期性地传递给协调器。第二类是紧急生理数据和用户命令、控制信息等。和第一类数据不同，这类数据只是随机发生的，因此被称为随机数据。这类数据具有比较低的业务量，但是对实时性和可靠性要求较高。第三类是音频视频数据等。这类数据业务流量不大，实时性要求也不高。

根据数据类别的不用特点，将其划分为三个优先级，如表2所示。

为了降低数据碰撞率，保证高优先级业务的实时性要求，针对三种优先级，协议中选择不同的退避窗口（CW）。本协议中的P1、P2和P3优先级的退避窗口分别对应于IEEE802.15.6中的优先级7、6和5。

表2不同数据的优先级  
Table2Priorities for different data   

<html><body><table><tr><td>优先级</td><td>业务类别</td></tr><tr><td>P1(最高）</td><td>随机数据(如:温度、紧急命令、控制等)</td></tr><tr><td>P2</td><td>周期数据（如：EEG,EMG）</td></tr><tr><td>P3（最低）</td><td>音频/视频等</td></tr></table></body></html>

# 2.2超帧结构

本协议为了简化控制难度，减少控制信息开销，对IEEE802.15.6的超帧结构进行改进，重组为四个阶段，分别是信标阶段（B）、竞争接入阶段（CAP）、非竞争接入阶段（CFP）和非活跃阶段，如图2所示。

# 2.2.1两种接入期长度的分配

在竞争接入阶段，节点通过CSMA/CA 的竞争机制接入信道。这种接入机制实现简单，传递灵活，但是由于随机接入会导致数据碰撞，从而导致数据包重传和丢失，将增加网络的延时，降低网络的可靠性。

![](images/5d08fd2c7a13c4a926135b0500839abc50812d31d04b62a21dffe9bb6bd6dcc3.jpg)  
图2A-MAC 超帧结构  
Fig.2A-MAC superframe structure

在非竞争接入阶段，节点只在所分配的时隙中传递数据，每个时隙只有一个节点传递数据，因此不会发生碰撞，具有高的可靠性和较小的延时。但是，协调器和传感器节点之间需要时间同步，造成额外能耗。

两种接入阶段的长度分配可由以下公式计算：

$$
L _ { \scriptscriptstyle C F P } = N _ { { \scriptscriptstyle 2 } } / ( N _ { { \scriptscriptstyle I } } + N _ { { \scriptscriptstyle 2 } } + N _ { { \scriptscriptstyle 3 } } ) \times L _ { \scriptscriptstyle s u m }
$$

$$
L _ { { \scriptscriptstyle C A P } } = L _ { { \scriptscriptstyle S u m } } - L _ { { \scriptscriptstyle C F P } }
$$

其中: $L _ { \scriptscriptstyle C A P }$ 表示竞争接入阶段的长度； $L _ { { \scriptscriptstyle C F P } }$ 表示非竞争接入阶段的长度； $L _ { s u m }$ 表示总长度； $N _ { 1 } \sim N _ { 3 }$ 表示各优先级的节点个数。

根据公式可知，非竞争接入阶段的长度与P2优先级业务的节点数占总节点数的比例有关，优先级P2业务的节点数量越多，非竞争接入阶段的长度越长。

# 2.2.2竞争接入阶段中子阶段长度的分配

在竞争接入阶段，节点采用CSMA/CA的机制竞争接入信道，为了减少节点发生碰撞的概率，本文按照每种数据业务优先级水平，将其划分为三个子阶段。

每个指定的接入阶段可以动态改变长度。当新超帧周期到来时，协调器感测当前超帧CAP中的每类的节点数量的变化，并且计算每个业务类别中的节点数量。

子阶段的长度可以利用等式（3）计算：

$$
l _ { i } = L _ { { \scriptscriptstyle C A P } } \ast ( N _ { i } / N _ { _ T } )
$$

其中: $l _ { i }$ 是子阶段 $i$ 的长度 $( \mathrm { i } { = } 1 , 2 , 3 )$ ， $L _ { \scriptscriptstyle C A P }$ 是 CAP 的长度， $N _ { \mathrm { i } }$ 是优先级为 $P _ { i }$ 的业务类别中的节点数， $N _ { { _ T } }$ 是节点总数，并且$l _ { \theta }$ 初始值为零。节点优先级的信息，通过IEEE802.15.6中UP（用户优先级）来控制。

为了最大化时隙利用率，本文设定优先级为P1的业务可以在所有子阶段访问信道；传送业务优先级为P3的节点仅可以使用子阶段3，P2优先级业务可以在子阶段2和3访问信道。

# 2.3 MAC协议工作过程

如图3所示为MAC协议一个信标周期中协调器的工作过程。在信标阶段，协调器向全网广播包含超帧持续时间、体域网时序和网络信息的信标帧，实现节点同步。网络实现同步后，需要发送数据的节点开始准备各自的发送请求帧，并将请求帧发送给协调器。对于不同的数据业务，请求帧也不同，主要分为两种：随机数据请求帧和周期数据请求帧。协调器可以通过帧类型域和帧子类型域的信息识别出请求帧的类型，判断数据优先级。节点采用相应的策略竞争接入信道。竞争成功后，如果是随机数据，协调器直接向节点反馈允许其发送数据的确认信息，节点立刻在竞争接入阶段中发送数据，协调器直接接收数据。如果是周期数据，协调器为其发送带保证时隙（GTS)的信标，节点在非竞争接入阶段的相应时隙中传递。协调器接收到数据后，给节点发送一个ACK 确认帧。节点数据传递完成后进入睡眠，直到信标周期结束。

![](images/6a37593987ddb5e050e0f00e54a628a2189b623f0cc24cfcd8424aaeb43504e1.jpg)  
图3协调器工作过程图  
Fig.5At the same time,two nodes generating random data send data to the coordinator

# 2.4信道接入过程

在信标阶段，协调器向全网所有节点广播信标帧，以实现节点时钟同步。在竞争接入阶段，根据数据优先级，需要发送数据的节点在相应子阶段向协调器发送请求帧。协调器根据接入信道策略，为其分配时隙进行数据的传递。在非竞争接入阶段，周期数据通过使用专用保证时隙（GTS）将其数据发送到协调器，而不与其他节点竞争。具体信道接入过程如下：假设节点A和节点B产生随机数据，节点C产生周期数据。一般情况下，产生不同类型数据的节点向协调器传递数据的过程如图4所示。

![](images/e1500025951eec88925603b4fa8342798d9354df6a68e806b51415892109a2f8.jpg)  
Fig.3Coordinator work process   
图4.一般情况（没有冲突）下，节点向协调器发送数据  
Fig.4In general (without conflict), the node sends data to the coordinator

在这种情况下，节点A产生随机数据，首先向协调器发送请求帧，协调器收到请求帧后，给节点反馈确认信息，允许其发送数据，节点A开始向协调器传递数据，当协调器成功接收数据后，向节点A发送ACK确认帧，这样节点A的数据传递就完成了。节点C产生的是周期数据，其向协调器发送请求帧以申请GTS分配，协调器成功接收到请求帧后，向节点发送一个包含GTS分配的信标信息。分配成功后该节点在CFP分配的相应时隙中传递数据。同样，协调器成功接收到数据后，向节点C反馈一个ACK确认。

![](images/3f10100b5edc3c5a569b835ff5c57464b3aee5865c32eab0507585914bb4ed00.jpg)  
图5同时有两个产生随机数据的节点向协调器发送数据

图5说明了同时有两个产生随机数据的节点向协调器发送数据的信道接入过程。节点A和节点B同时向协调器发送请求帧，发生冲突，根据CSMA/CA机制，节点会随机回退一段时间。假设节点A的回退计数器BC为1，节点B的回退计数器BC为2，节点A回退一个时隙后，执行空闲信道评估（CCA），检测可知信道此刻空闲，向协调器发送请求帧，在收到协调器的确认信息后传递数据。节点B在回退一个时隙后，检测到信道忙碌，锁定回退计数器直到节点A数据传递完成后，继续回退一个时隙，然后向协调器发送请求，待收到协调器的反馈确认后，进行数据传递。

# 3 A-MAC协议的仿真及性能评估

# 3.1仿真环境

本文构造了1个星型无线体域网络，包括1个协调器和N个节点。物理层参数是根据IEEE802.15.6标准定义的。传感器节点随机部署在 $2 \mathrm { m } ^ { \ast } 2 \mathrm { m }$ 的正方形区域内，并且假设都是单跳传递。分组到达近似为泊松分布。忽略小规模信道衰落，并且假设分组丢失只是因为发生碰撞。主要仿真参数设置如表3所示。

表3仿真参数设置  
Table 3Simulation parameter settings   

<html><body><table><tr><td>仿真参数</td><td>设置值</td></tr><tr><td>传递频段</td><td>2.4GHz</td></tr><tr><td>数据传递速率</td><td>250kbps</td></tr><tr><td>仿真时间</td><td>100s</td></tr><tr><td>数据包大小</td><td>1024byte</td></tr><tr><td>发送功率</td><td>414mW</td></tr><tr><td>接收功率</td><td>365mW</td></tr><tr><td>空闲功率</td><td>275mW</td></tr><tr><td>节点初始能量</td><td>0.5J</td></tr></table></body></html>

# 3.2 仿真结果及分析

时延是指数据包从产生到协调器成功接收的时间差。三种协议的平均时延随节点数量的变化情况如图6所示。从图中可以看出，三种MAC协议的平均时延都随节点数量的增加而增加，这是由于节点数量增多，网络流量增加，节点发生碰撞的概率增大，导致重传次数增多，时延增加。三种协议都采用了基于优先级的信道接入策略，能够有效降低延时。但是，随着节点数量增加，A-MAC和CA-MAC协议的性能明显优于IEEE802.15.6MAC协议，这是因为IEEE802.15.6MAC协议的超帧结构中时隙固定，随着节点数量增加，节点发生冲突概率明显增大，导致争用复杂度很高，延时增加。所提出的A-MAC协议充分考虑了节点优先级，结合动态时隙分配，将竞争接入阶段划分为三个子阶段，能够有效的解决节点碰撞问题，降低节点冲突概率，减少数据包重传次数，因而相对于其他两种MAC协议，表现出更好的时效性能。

![](images/17f2b52e6ca3c407e098621ceda2c875f7c6a3d4ec8f75ccb0b30456b9441f7a.jpg)  
图6协议平均时延对比图  
Fig.6Average delay comparison of the protocol

网络归一化吞吐量即单位时间内成功传递的数据包数与发送的数据包总数的比率。随着节点数量增加，网络归一化吞吐量的变化如图7所示。从图中可以看出，随着节点数量增加，三种协议的归一化网络吞吐量都在下降，这是因为随着节点数量的增加，发送的数据包数量增加，致使传感器节点的数据包丢失率逐渐增加，归一化吞吐量逐渐降低。但是，与IEEE802.15.6MAC协议和CA-MAC协议相比，所提出的A-MAC协议优化了节点优先级分类，将竞争接入阶段划分为三个子阶段，调整时隙分配策略，减少碰撞，对降低数据包丢失率具有显著的作用。

![](images/d60fb5d15b923506fcea55c190f4d2cd8e48c84ecf6bdd1453b2954c2c366f4f.jpg)  
图7.网络归一化吞吐量对比图  
Fig.7Network normalized throughput contrast diagram   
Fig.8Comparative diagram of average energy consumption of network with increasing number of nodes

![](images/019b66a9089d5deb3da17313301398bfc56d75802df25a96b9f2bd6319878a85.jpg)  
图8.随节点数量增加网络的平均能耗对比图

平均能耗是指网络中节点消耗能量的平均值。图8显示了网络的平均能耗和节点数量的关系。无线体域网中的网络能耗主要来源于数据碰撞和重发。从图中可以看出，随着节点数量增加，三种协议的平均能耗都随之增加。所提出的A-MAC 协议和IEEE802.15.6MAC协议都依据节点优先级调度接入信道，能够降低争用的复杂性，从而减少数据冲突和重传，降低能耗。所提出的A-MAC协议将数据类型根据优先级进行划分，同时依据业务量进行时隙分配，很大程度的降低了数据冲突率，减少碰撞重发。因此，本文提出的协议的网络平均能耗优于其他两种MAC协议。

# 4 结束语

本文研究一种基于IEEE802.15.6的无线体域网自适应MAC协议（A-MAC）。该协议在IEEE802.15.6MAC协议的基础上，改进超帧结构，解决了IEEE802.15.6各接入期交错分布、控制难度大的问题。将数据业务根据业务类型划分为三种优先级，安排周期数据在非竞争接入阶段传输，能够有效降低数据信道接入时的碰撞。根据业务流量情况动态调整时隙分配，能够适应网络中业务流量变化。通过仿真，对IEEE802.15.6协议、CA-MAC协议和A-MAC协议进行性能比较和分析，结果验证了A-MAC协议能够有效减少网络延时，提高网络时效性能，降低网络能耗，提高网络自适应性。

# 参考文献：

[1]Chen Min, Gonzalez S,Vasilakos A,et al. Body area networks: a survey [J]. Mobile Networks& Applications,2011,16 (2):171-193.   
[2]刘怡．无线体域网关键技术的研究[D].北京：北京邮电大学,2017. (Liu Yi.Rearch on the key technology for wireless body area network [D]. Beijing:Beijing University of Posts & Telecommunications,2017)   
[3]Gama O,Simoes R.A hybrid MAC scheme to improve the transmission performanceinbodysensornetworks[J].WirelessPersonal Communications,2014, 80 (3): 1-17.   
[4]Bedi R K.An improved energy efficient TDMA based MAC protocol for WBAN[J]. International Journal of Computerences & Engineering,2018,6

# (3):34-39

[5]卢先领，彭能明，陆胜男，等．无线体域网节能策略综述[J].计算机 应用研究，2013,30 (2):325-329.(Lu Xianling,Peng Nengming,Lu Shengnan,et al. Survey of energy-efficient strategy for wireless body area network [J].Application Research of Computers,2013,30 (2): 325-329.)   
[6]王杰，曾碧．基于优先级的无线体域网MAC协议研究[J]．自动化与 信息工程,2015(3):45-48.(Wang Jie,Zeng Bi.Research on Priority-based MAC Protocol for Wireless Body Area Network [J]．Automation and Information Engineering,2015 (3):45-48.)   
[7]IEEE B E.802.15.6-2012,IEEE Standard for local and metropolitan area networks,part 15.6: wireless body area networks [S].2012:1-271.   
[8]Liu Bin,Yan Zhisheng,Chen Changwen.MAC protocol in wireless body area networks for E-health:challenges and a context-aware design[J].IEEE Wireless Communications,2013,20 (4): 64-72.   
[9]谢语天，王珺，闵建民，等．一种高效节能的无线体域网 MAC 层协议 [J].计算机技术与发展,2015,25(12):91-96.(Xie Yutian,Wang Jun,Min Jianmin,et al.A Highly-efficient Energy-saving Wireless Body Area Network MAC Protocol [J]. Computer Technology & Development, 2015, 25 (12): 91-96.)   
[10] Motivation C,Section.Adaptive medium access control protocol for

wireless body area networks [J].International Journal of Distributed Sensor

Networks,2014,2014(1):156-160.   
[11] FouratiL C,Boudjit S,Kamoun L.New priority MAC protocol for wireless body area networks [C]//Proc of the 2nd ACM MOBIHOC Workshop on Pervasive Wireless Healthcare.New York:ACMPress,2013:1-6.   
[12] Zhou Jing,Guo Aihuang,Xu Juan，et al.A reliable medium access mechanism based on priorities for wireless body sensor networks.[C]//Proc of the 35th Annual International Conference of the IEEE Engineering in Medicine & Biology Society IEEE Engineering in Medicine & Biology Society.Piscataway,NJ:IEEE Press,2013:1855.   
[13]Huq MA,Dutkiewicz E,Fang Gengfa,et al.MEB MAC: improved channel access scheme for medical emergency traffic in WBAN[C]//Proc of the 12th Annual International Symposium on Communications and Information Technologies.Piscataway,NJ: IEEE Press,2012:371-376.   
[14]程宏斌，孙霞，王晓喃，等．基于单跳通信的 IEEE802.15.4WSNs数据 传输可靠性优化[J].计算机应用研究,2016,33(7):2110-2112.(Cheng Hongbin,Sun Ya,Wang Xiaonan,et al. Optimization of data transmission reliability for IEEE 802.15.4 WSNs based on single-hop communication [J].Application Research of Computers,2016,33(7):2110-2112.)   
[15]Prabh K S,Royo F,Tennina S,et al.A MAC protocol for reliable communication in low power body area networks [J]. Journal of Systems Architecture,2016,66-67(C): 1-13.