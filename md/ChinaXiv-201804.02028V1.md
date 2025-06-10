# 基于SDN的WLAN负载感知切换方案实现

赵国锋1,²，黎军，王新恒」，陈攀」，葛长威1(1．重庆邮电大学 电子信息与网络研究院，重庆 400065;2.重庆市光通信与网络高校重点实验室，重庆 400065)

摘要：基于软件定义网络将网络的控制平面与转发平面分离，并提供开放的可编程接口等特点，提出一种基于 SDN的 AP 负载感知的切换算法，去减少网络中频繁切换和使AP间负载相对均衡。该方法利用 SDN集中控制功能，实时监控 AP 的网络状态信息，并由控制器判断 AP负载状态和预测终端运动状态来辅助切换过程。实验结果表明该切换方法可以减少切换次数和平衡AP间的负载，保证用户网络服务质量。

关键词：软件定义网络；可编程接口；负载均衡；信息状态中图分类号：TN915.07 doi:10.3969/j.issn.1001-3695.2017.12.0767

# Implementation of WLAN load aware handover method based on SDN

Zhao Guofeng1,²,Li Jun1,Wang Xinheng1, Chen Pan], Ge Changweil (1.InstituteofElectricalInformation&NetworkEngineering,ChongqingUniversityofPosts&Telecommunication,Chongqing 40065,China; 2. Optical Communication& Network Key Laboratory ofChongqing, Chongqing 40065,China)

Abstract: Basedonthe software-defined network thatseparates thecontrol planeofte network from theforwarding plane and provides anopen and programmable interface,this paper proposes ahandover algorithm based on SDN forAPload sensing to reduce frequentswitching inthe network and make the load betweenAPs relatively balanced.The methoduses thecentralized controlfunctionofSDNto monitorthe network status informationoftheAPinreal timeandthecontrollerasststeload status of the APand predicts the terminal movement status to asistthe handover process.The experimental results show that this method can reduce the switching times and balance the load between APs to ensure the quality ofservice of users.

Key words: software-defined networking; programmable interface; load balance; information status

# 0 引言

基于IEEE802.11协议标准的无线局域网（WirelessLocalAreaNetworks，WLAN)凭借可以为移动用户提供高吞吐量和支持大量用户接入等特点已经被广泛地应用在无线互联网的接入中。但是随着网络规模和用户数的日益扩大，同时用户网络服务需求越来越复杂化[1]。为保证移动用户的网络服务质量，必须实现在网络中的快速切换，而传统WLAN中，采用基于接收信号强度 RSS(Received Signal Strength)传统切换方法会造成AP间负载不均衡和产生不必要的切换[2]，即乒乓效应，最终降低网络整体性能。如何在切换时保证用户的服务质量成为研究热点。

针对WLAN中的需求，已经有学者展开了这方面的研究。RSSH 算法[通过引入迟滞余量 H可以一定程度上减少乒乓效应。由于仅当AP的信号质量足够好才触发切换，所以该算法很可能导致业务中断。基于RSS预测的驻留时间算法4其中心思想是设置一个时间阈值TTH 和RSS切换阈值。当RSS大于阈值，开始计时，若时间大于TTH后，大小关系依然满足，则发生切换。否则，保持当前关联。该算法可以减少切换次数，却增加了切换时延。双门限算法[5]，该算法中设置两个阈值 TI和T2，且 $\mathrm { T I } { > } \mathrm { T } 2$ 。设置双门限，相当于给了RSSI波动空间，可以一定程度上缓解在密集部署AP环境下，AP切换带来的乒乓效应。以上算法可以减少乒乓效应，但是并没有缓解AP间的负载均衡问题。

为此，本文提出一种基于SDN的WLAN负载感知切换算法来平衡AP间负载和缓解乒乓效应的影响。为验证所提方法的有效性，搭建了原型系统并作算法验证。下面主要对切换中存在的问题做详细分析。

1)WLAN中乒乓效应分析。

乒乓效应是指用户在AP间的重叠区域因切换触发条件设置单一、固定引起的不必要的频繁切换过程，这种切换会造成网络资源的过度浪费和占用。如下图2中STA处于 三个

AP 的重叠区域，如果 $R S S _ { p r e s e n t }$ 与 $R S S _ { t a r g e t }$ 大小关系在短时间内不确定，就会造成 STA1会在3个AP之间来回关联，即乒乓效应。

![](images/97be59386ec6156fef5562e31c900b157c975388673bdb3b221926f69d2572d1.jpg)  
图1乒乓效应场景图

2）WLAN中AP负载不均衡分析。

AP间负载不均衡指在切换发生后 STA(Station)不能选择合适的AP作为新的目标接入点，而导致用户速率下降和降低网络整体性能的一种现象。如传统WLAN中，STA采用RSS值最大的方法选择目标AP，这种方式会让多个STA集中关联在某个AP或某些AP。在密集部署的场景中，多个AP覆盖范围相互交叠，如下图2所示。根据文献[，当多个STA接入同时接入一个AP 后，每个 STA 获得的带宽大小是一样的。文献[7]给出了每个STA的传输速率计算方法，公式如下：

$$
\mathbf { R } = { \frac { 1 } { \sum _ { i = 1 } ^ { N } { \frac { 1 } { R _ { i } } } } } ;
$$

其中： $R _ { i }$ 表示对应 STA 对于AP的传输速率。假设在图1部署场景中部署8个AP，覆盖区域相互重叠，实线表示当前连接，虚线代表可能的链接,线上的数字代表传输速率，单位为Mbps。STA1、STA2、STA3和STA4分别与AP1、AP2和AP3关联。STA1、STA2、STA3 和 STA4 的速率分别为 22Mbps、9Mbps、13Mbps、7Mbps，系统吞吐为51Mbps。当STA2从右往左移动，由于AP1的RSS大于AP2和AP3，STA2重新与AP1关联，此时 STA1与 STA2 速率相等且为7.2Mbps，系统吞吐为34.4Mbps。前后对比，系统吞吐下降16.6Mbps，系统资源利用率为 $32 . 5 \%$ 。这是由于STA2关联 AP1后共享了STA1的网络带宽，不仅拉低自身速率，也会拉低系统整体吞吐量。

![](images/5fa54d37015ad899e45cba8f212185e539a33d786da454152a0667d3e74c7dd9.jpg)  
图2AP负载不均衡场景

# 1基于SDN的负载感知切换方法设计

对于传统的WLAN切换过程中，终端采用RSS作为切换触发条件和STA接入AP的标准。结果会导致AP间负载偏差较大，无法充分利用资源。软件定义无线网络(Software-DefinedWirelessLocalNetwork,SDWN)作为SDN[8]在无线网络中的应用扩展，其主要思想是将无线网络设备的控制和转发进行分离[9]，将控制功能转移到 SDN控制器，物理AP只需处理数据转发。SDN 集中控制的特点为解决WLAN中传统切换带来了新方向。

![](images/fab4d45b56c1bf760792c083c4786f14636569c7e92181c6d3864711c265b4de.jpg)  
图3基于Odin 的 SDWN切换子系统架构图

目前比较主流的SDWN系统架构为Odin[10]和CloudMAC[II]，两者都利用VAP的概念都能实现快速切换来减少切换时延，并保证用户的服务质量，但是均采用的RSS切换方法容易导致AP间的负载不均衡。其中VAP是指将物理AP的控制功能进行抽象，转移功能到其他设备上完成，物理AP只负责数据的转发和交付从而简化网络设备的管理。两者同之处在于前者的LVAP由SDN控制器创建和跟踪，其维护在物理AP上，而后者的VAP则驻留在云端服务器。

综合上述分析和考虑到Odin比较小巧、容易实现且比较适合开发上层应用来满足不同网络需求，本文将以Odin为基础构建 SDWN 切换系统，其系统架构如上图3所示。Floodlight[12]控制器通过 OpenFlow[13]协议与安装 OpenVswitch的 AP建立通信连接，借此获取全网的网络拓扑信息，最后实现对全网设备的管理；利用控制平面提供的开放API应用编程接口，服务提供商可完成多种应用需求，包括负载均衡、移动管理等。本文主要是做应用层的切换子系统管理开发，如上图所示，应用层中的切换子系统与Click组件中的agent代理之间创建 socket连接获取终端信息来综合决策切换，在agent模块中维护用户STA的LVAP，LVAP中包括用户的认证关联等信息。子系统包括3个模块，其中切换决定模块，主要是为STA选择合适的目标AP，通过采用AP负载感知方法实现。切换执行模块是将STA重关联到新接入点。基于该平台提出一种基于SDN的WLAN 负载感知切换方案(SoftwareDefinedWirelessNetworksLoad-aware Handover, SLAH)。

![](images/53edb68972de7814dc6104a9531f6569d6ddd7a19a3e237f622d3eaaab3d009f.jpg)  
图4STA切换过程  
图5AP状态信息格式

本文采取RSS预测终端运动状态并结合AP负载状态来辅助切换决策。SDN控制器(SDNcontroller,SC)通过订阅AP 消息(图中标号1所示)如信号强度，然后开始检测每个AP的信号，如果大于设置的阈值则触发切换过程。如上图4所示，此时STA2向AP2移动且AP2的信号强度大于AP1，接着切换过程开始(图中标号2)，然后SDN控制器 SC开始选择目标 AP。本文所提SLAH思想是当切换发生后，SC实时提取物理AP负载信息分析并为每个可视AP(STA探测到的AP)计算一个权值(可接入AP权值)。对于关联 STA少，信道利用率低，RSS大的 AP2为其设置较大的权值，因为此时AP2空闲；否则设置较小的权值。权值的计算在SC中完成，SC按照计算结果大小将 AP状态分为满负荷、空闲两个等级，其中空闲对应的AP 被加入到列表中生成可接入列表，从可接入列表中选择最大的权值作为STA的目标AP。最后，SC下发控制信息，命令AP1删除其为STA维护的VAP1(图中标号3所示)，同时在AP2上增加VAP1(图中标号5所示)，从而实现无缝切换。通过SLAH可以使AP间负载相对均衡，保证用户网络服务质量。

为实现SLAH，需将AP收集的信息上传至控制器，这里本文在数据包中加入一个新字段，消息具体格式见下图5。其头部为UPDATE_AP_LEVEL，数据部分为 AP 状态信息AP_LOAD_INFO,这部分信息将在Agent中LVAP中进行封装，然后通过Agent代理模块与控制器中的Master 建立Socket连接最后传至控制器处理。

Headroom Packet Content Tailroom   
28By tes 42By tes 0Bytes   
Message Header Message Date   
UPDATE_AP_LEVEL AP_LOAD_INFO

# 2 基于AP负载感知的切换方法

研究发现切换过程一般包括切换触发、AP选择、切换执行等三个阶段，切换触发主要关注乒乓效应问题，AP选择则是AP 间负载均衡，切换执行则是要求STA在尽可能短的时间内关联到目标AP上，保证切换时延。本文基于Odin构建切换原型系统，通过引入虚拟VAP，保证切换时延在 $3 0 \mathrm { m s }$ 内。本文主要解决前两个阶段中存在的问题，即乒乓效应和 AP间负载均衡。本节将主要介绍影响切换性能的参数、终端STA运动状态估计、可接入AP权值计算、SLAH切换流程及伪代码分析。

# 2.1影响WLAN切换性能的参数及计算

针对负载均衡问题，采用的切换方法需要综合考虑多个切换因素。本文选取的参数主要包括信号接收强度RSS值、AP关联STA数目、AP信道可用率。其中RSS的大小可以直接反映接入点AP 的优劣；STA个数越多，AP可用带宽越小，特别当利用RSS作为AP接入标准时，多数STA容易关联到某一部分AP上；信道可用率越大，AP下可挂载 STA的能力越强。因此，SC可以根据RSS和AP的负载状态来综合决策，相关计算公式如下：

AP 无线信道负载利用率[14] $L o a d _ { c h }$ 和 AP上 STA数量 ${ N } _ { k }$ 作为AP负载状态估计。根据文献IEEE802.11k标准，信道负载为信道在一定时间内的繁忙时间 $T _ { { C B T } }$ (Channel Busy Time)与时间周期 $T$ 之间的百分比。 $L o a d _ { c h }$ 和 AP 负载状态计算公式如下：

$$
\sum _ { j = 1 } ^ { N - 1 } p > P _ { T H R }
$$

$$
L _ { k } = \left\{ \underbrace { \sum _ { i = 1 } ^ { i = N _ { k } } { \frac { \textstyle \strut } { T h r o u g h p u t _ { i } } } _ { \textstyle N e g o t i a t i o n R a r e _ { i , k } } } _ { \textstyle N _ { k } } \right. _ { \textstyle N _ { k } > 0 }
$$

$$
L o a d _ { \boldsymbol { k } } = L o a d _ { c h } { ^ { * } } 0 . 8 + L _ { \boldsymbol { k } } { ^ { * } } 0 . 2
$$

式(2)为时间周期 $\mathrm { ~ T ~ }$ 内，信道的利用率；式(3)中 $L _ { \boldsymbol { k } }$ 表示 $A P _ { k }$ (j 为第j个AP)在一段时间内信道的平均利用率，它反映了关联在当前 AP上所有 STA 对信道的占用情况，且Throughput 为STA的平均吞吐速率，NegotiationRarei,k为 $S T A _ { i }$ 与 $A P _ { k }$ 之间理想的平均速率。当没有 STA接入 $A P _ { k }$ 时， $L _ { i , k }$ 取为 $0$ ；当有STA接入时， $\boldsymbol { L } _ { i , k }$ 的取值为式(3)。

式(4)计算 $A P _ { k }$ 的利用率，其值为 $L o a d _ { c h }$ 和 $\boldsymbol { L } _ { i , k }$ 权值之和。其中权值 $L o a d _ { c h }$ 为0.8， $L _ { i , k }$ 为0.2。

接收信号强度值RSS由于环境等因素，其值会在同一地点不同时间发生波动，为了减少这种变化造成的影响，对接收到的RSS做如下平滑处理。在较短周期T内，对接收到的RSS进行从大到小排序,取前K个RSS,再对其取平均值，得到 $\overline { { R S S } }$ 。为了更加准确计算RSS，考虑上一周期内平均RSS对其影响，最后计算公式如下：

$$
\mathrm { R S S } = w ^ { * } \overline { { R S S } } _ { T - 1 } + \big ( w - 1 \big ) ^ { * } \overline { { R S S } } _ { T }
$$

# 2.2 可接入AP 权值计算

由于信号强度可以直接反映当前无线信道的通信质量，当移动终端STA距离关联AP远，则信号强度较强；相反，则信号强度较弱。基于以上分析，可以利用信号强度值的前后变化量来对移动终端的运动状态进行估计。

![](images/26e4cbdcc89462e575cc80235038d702a3e4c732801b23d4f328a89ee35f5853.jpg)  
图5终端STA与接入点AP运动模型

如图5所示，利用式(4)计算信号强度的大小，并将P2 与P1 处的信号值之差 $\Delta \mathrm { r s s }$ 作为 STA 运动状态估计，如果差大于0，表示STA向AP靠近，应该保持当前连接状态；如果小于0，则表示STA远离当前AP,应该触发切换过程为终端选择服务质量更好的AP，来保证用户的网络服务。但是，为了保证预测的准确性，对每个点在一段时间NT内，统计信号强度值之差，并将结果做累加，最后将计算结果与设定的阈值做比较。相关计算公式如下：

$$
p \big ( \Delta r s s \big ) = \left\{ \begin{array} { l l } { 1 } & { \Delta r s s > 0 } \\ { 0 } & { \Delta r s s < 0 } \end{array} \right.
$$

$$
\sum _ { j = 1 } ^ { N - 1 } p > P _ { T H R }
$$

函数 $\mathfrak { p }$ 表示，STA运动结果估计，如果信号值之差大于0,则函数值为1，否则，为0。式(6)为一段时间NT内的计算结果，以该值与阈值 $P _ { \mathit { T H R } }$ 作差，如果该公式大小关系成立，则表示 STA正在靠近当前关联 AP。

# 2.3 可接入AP 权值计算

研究发现切换过程一般包括：切换触发、AP选择、切换执行等三个阶段，本文主要解决后两个阶段中存在的问题，即 AP间负载均衡和保证切换时延在 $3 0 ~ \mathrm { m s }$ 内。STA如何选择合适的AP作为新的接入点，关系到AP间负载是否均衡。比如，AP的RSS很大，但是负载很重，这种情况下发生切换只会导致网络整体性能下降，而采用RSS加AP负载综合决策可以避免这种切换。为此，本文将 AP的接入用户终端数，信道负载和接收信号强度综合考虑，引入一个新的接入评价标准，权值 $W _ { i , k }$ ，其计算公式如下：

$$
W _ { i . k } = \frac { R S S _ { i . k } { ^ { * } } \big ( 1 - L o a d _ { k } \big ) } { N _ { k } + 1 }
$$

其中 $W _ { i . k }$ 表示 $S T A _ { i }$ 关联到 $A P _ { k }$ 的权值，值越大，表示 AP上可利用资源越多，STA越应接入该 $\mathbf { A P }$ 。

为了说明式(5),构建了如图1所示的实验场景，STA2处在AP1、AP2、AP3三个物理AP的覆盖范围内，会接受来自三者的信号强度值。依据上述公式并计算 STA可视AP的接入值，如表1所示。

从表1中可知，AP2的STA数量最少，带宽可用率最大，计算的权值也最大，即SC将AP2作为STA的目标AP并进行关联。AP3的RSS虽然大于AP2，但是其STA数目大于AP2且带宽可用率比较低，计算的权值W也比AP2小。所以综合考虑以上两种因素计算W，以W的大小综合选择目标AP。这样能有效避免因为STA依靠RSS选择接入点而导致的负载不均衡和在AP交叠区域的频繁切换。

表1AP可接入权值统计表  

<html><body><table><tr><td>AP</td><td>AP可用带宽</td><td>信号强度</td><td>STA数目N</td><td>接入点权值W</td></tr><tr><td>AP1</td><td>43.11</td><td>38</td><td>1</td><td>8.17</td></tr><tr><td>AP2</td><td>79.5</td><td>23</td><td>1</td><td>9.14</td></tr><tr><td>AP3</td><td>27.33</td><td>50</td><td>2</td><td>4.56</td></tr></table></body></html>

# 2.4 SLAH切换流程

WLAN中AP负责多个终端接入，若某AP承担的业务已经饱和，终端仍接入该AP以享受网络服务，那么服务质量难以保证。SLAH中的AP权主要用于AP的选择阶段，其主要解决 AP选择性问题。但是为了减少不必要的切换过程，采用一段时间内RSS前后变化之差的累加和来判断当前终端 STA 的运动状态，具体见图5所示的切换流程图。

![](images/b90a99243c2b0fcea01ad1120afe434283934be11ddadd2a3fc8ff043a45e1e5.jpg)  
图5STA切换流程

如果 $\sum _ { j = 1 } ^ { N - 1 } p > P _ { T H R }$ 成立，则表示 STA将远离当前 AP，则触发切换过程，然后控制器SC计算权值W；否则，表示终端STA靠近当前关联AP，此时不需要触发切换过程并保持当前关联状态，之后进入下一个运动状态估计周期。

切换过程被触发后，SC 计算可视 APs 的负载 $L o a d _ { k }$ ，SC通过比较 $L o a d _ { k }$ 与负载阈值 $L o a d _ { T H R }$ 的大小关系，将 AP状态分为满负荷和空闲两类，空闲 $A P _ { k }$ 为 STA 的可能接入点。SC 计算 $A P _ { k }$ 的权值 $W _ { i . k }$ ，生成当前 STA 可接入候选AP 列表 $L i g h t A P$ ，通过轮询从LightAP中选择权值最大的 $W _ { i . m }$ 的AP作为STA切换后新的接入点。SC根据切换后STA关联AP状态重新计算W并更新列表。由于更新后列表中AP的权值能反映对应AP实时负载状态，使切换可以依据负载状态选择合适的AP作为目标AP。

SLAH算法伪代码如下：

SLAH算法   
INPUT:STA's visible AP list: $A P _ { l i s t }$ 、visible AP weightage   
list : VisibleWeig $h _ { \mathit { l i s t } }$ 、RSS 、Loadch、 $N _ { \boldsymbol { k } }$ （204号   
OUTPUT:handover or not   
1:SC sends initial handoversubscription message to   
visible APs in WLAN system   
2:SC updated $A P _ { l i s t }$ and $L i g h t A P _ { l i s t }$ periodically   
3:Initialization: $L i g h t A P _ { l i s t }$ and $A P _ { C a n d i d a t e s }  \mathcal { O }$ （204号   
4:if $\sum _ { j = 1 } ^ { N - 1 } p > P _ { T H R }$ then   
5: for each $A P _ { k } \left( A P _ { k } \in A P _ { l i s t } \right)$ in $s T A _ { i } ^ { , } s$ visible AP list do   
6: $W _ { i . k } = R S S _ { i . k } { ^ { * } } \big ( 1 - L o a d _ { k } \big ) / \left( N _ { k } + 1 \right)$   
7： if ( $L o a d _ { k } > L o a d _ { \scriptscriptstyle T H R } :$ then   
8: $\begin{array} { r l } & { V i s i b l e W e i g h _ { l i s t }  V i s i b l e W e i g h _ { l i s t } \cup \{ \begin{array} { r l } { W _ { i . k } } \end{array} \} } \\ & { A P _ { C a n d i d a t e s }  A P _ { C a n d i d a t e s } \cup \{ A P _ { k } \} } \end{array}$   
9:   
10: else   
11: AP level is overloaded   
12: end if   
13: end for   
14: for each APk ∈ APcandidtes in Candidate AP list do   
15: if( $\because W _ { i . m } < W _ { i . k }$ ）then   
16: $\mathbf { m } = \mathbf { k }$   
17: end $\mathbf { i } \mathsf { f }$ （20   
18: end for   
19: Handover the $S T A _ { i }$ to the $A P _ { m }$   
20: $A P _ { c a n d i d a t e s }  A P _ { c a n d i d a t e s } \downarrow \{ A P _ { m } \}$   
21:end if

# 3 实验结果及性能测试

# 3.1 SDWN系统部署

为验证方法的有效性，搭建了SDN-WLAN实验平台并对提出的 SLAH算法进行性能验证。原型系统由 floodlight控制器，无线接入点 AP组成，并通过SDN 交换机组成一个WLAN。通过对重庆邮电大学逸夫实验楼三楼地形、线路、交换机位置等因素进行勘查，明确部署环境，并进行了网络规划，设计了如图6所示的实验平台部署平面分布图。

# 3.2 SDWN 切换性能测试

图7只是系统拓扑的部分，以此图来说明。为了验证本文所提方法的有效性，采用图4的拓扑结构来验证分析，采用2个物理AP和两个测试手机。初始状态，测试手机STA1和STA2都与AP1关联，在STA2中运行iprefI5]来测试下行TCP吞吐。为了说明所提方法，建立了两个实验，两个实验的运行时间为$6 0 ~ \mathrm { s }$ ，重复5次，结果取均值。

![](images/4b74e18d2e796a013326d5f7f1ce9c914432a559962e514dba808578585c2f0d.jpg)  
图6SDWN实验平台实际部署平面分布图

![](images/611998c305c15604f01c237df4a0d911e2d92ce3f29feea0b93b23e0bf803514.jpg)  
图7SDWN切换测试场景1  
图8实验1TCP下行吞吐测试

图8为实验1测试结果。测试过程中，初始STA1和STA2与AP1关联，并且STA2开始向AP2持续移动，当STA2处于AP1与AP2的重叠区域停止移动。此时，AP1与AP2的RSS大小相近不足以触发切换，所以在传统WLAN中STA2继续与当前AP1保持连接，STA2共享STA1的网络带宽。而利用SLAH方法，由于此AP2的负载低，可用带宽大，在22s后，STA2切换到AP2。从图7可知，相比WLAN，采用负载自适应算法，TCP下行速率可以提高大约17Mbps。

无线下行TCP吞吐量（SDWNvsWLAN）40一本文方案35WLAN传统方案n WwwAww0 10 20 30 40 50 60时间（s）

图9是实验2结果。初始STA1和 STA2分别与AP1和AP2关联且STA2向AP1移动。在WLAN中，在重叠区域由于AP1的RSS值比AP2的大，导致STA2执行切换过程并重新与AP1关联。此时STA2共享 STA1的带宽，导致 STA2的速率从26Mbps下降到12Mbps。而采用SLAH方法，控制器发现AP1的负载较重，不发生切换过程，即STA2继续保持与AP2的关联。从上面分析可知，本文提出的SLAH方法，可以使APs间的负载达到相对均衡，提高用户下行速率，同时也可以避免不必要的切换过程，提高网络资源利用率。

无线下行TCP吞吐量（SDWNvsWLAN)  
40本文方案  
35 WLAN传统方案  
MAvww  
20  
1510  
5  
0 10 20 30 40 50 60时间(s)

图12是本文SDWN系统网络时延测试，终端ping网络中的AP，并记录其往返时间(round-trip,RTT),测试结果如下图所示。发生切换时，在WLAN中STA与AP的传输时延开始增大，在46s-48s左右会产生中断，时延增大至无限，然后与新接入点关联后，时延开始下降。在SDWN中，控制器将当前LVAP迁移至目标接入点，因此并没出现明显的中断，保证用户的上网服务质量。

![](images/6c9a562b065dfef5e1b9f54dfe130239d482ce281cb5403421e2549d4f9346db.jpg)  
图12传输时延测试

图10为SDWN切换测试场景2，在AP密集部署下，测实验证本文所提方法对减少乒乓效应的有效性，记录实验结果，并与传统方法作对比分析。

![](images/69ebfd5267ae5aa0be60c1c7b8977dea17f3f16854074f1c02ed503242deab90.jpg)  
图9实验2TCP下行吞吐测试  
图10SDWN切换测试场景2  
图11切换次数统计图

图11为切换统计结果，初始状态，只有STA2与AP1关联，终端从图中所示的箭头向AP4以不同的速度进行移动，重复实验10次，并记录STA的关联状态，最后统计平均切换次数。从下图可知，采用本文方案相比传统方法在切换次数方面有明显的减少，且随着速度的增大，切换次数逐渐减小。

基于WLAN的切换方法  
12 本文移动预测切换方法  
10  
0  
6  
4  
2  
00.25 0.5 1.0 3.0运动速度m/s

# 4 结束语

本文提出了一种负载感知的SLAH算法来改善系统切换性能，通过构建SDWN测试实验来检验该方法的有效性。实验结果表明，相比于WLAN中传统RSS切换方式采用SLAH方法可以有效平衡APs间负载和减少频繁切换并能有效提高用户速率和网络资源的利用率。

# 参考文献：

[1]Keshav S,Shui Y,Yong X,Software-defined wireless networking opportunities and challenges for internet-of-things:a review [J].IEEE Internet Things,2016,3 (4): 453-463.   
[2]Lee D,Won D,Piran M,et al.Reducing handover delays for seamless multimedia service in ieee 802.11 networks [J].Electronics Letters,2014, 50 (15): 1100-1102.   
[3]Zhang Ning,Holtzman JM.Analysis of handoff algorithms using both absolute and relative measurements [J].IEEE Trans on Vehicular Technology,1996,45 (1): 174-179.   
[4]Kunarak S,Sulessathira R,Dutkiewicz E.Vertical handoff with predictive RSS and dwell time [C]//Proc of IEEE Region 10 Conference.2013.   
[5]Zou Deyue,Meng Weixiao,Han Shuai.Euclidean distance based handoff algorithm for fingerprint positioning of WLAN system [C]// Proc of Wireless Communications and Networking Conference.2013.   
[6]Bejerano Y,Han S J,Li L E.Fairness and load balancing in wireless lans using association control [C]// Proc of ACMMobiCom.2004.   
[7]Chen X, Qiao D.HaND: Fast handoff with null dwell time for IEEE 802.11 networks [C]//Proc of INFOCOM.2010:1-9.   
[8]Sood K,Yu S,Xiang Y.Software-defined wireless networking opportunities and challenges for internet-of-things: a review [J]. IEEE Internet Things, 2016,3 (4): 453-463.   
[9]Xu Chuan, Jin Wenglang,Zhao Guofeng.A novel multipath-transmission supported software defined wireless network architecture [J]. IEEE Access, 2017,5: 2111-2125.   
[10]SureshL,Schulz-Zander J,MerzR,etal.Towards programmable enterprise wlans with odin[C]//Proc of the 1st Workshop on Hot Topics in Software Defined Networks.New York:IEEE Press,2012:115-120.   
[11]Vestin J,Dely P,KasslerA,et al.CloudMAC: towards software defined WLANs [J].ACM SIGMOBILE Mobile Computing& Communications Review,2013,16 (4): 42-45.   
[12]Floodlight OpenFlow controller [EB/OL].http://www.projectfloodlight.

org.   
[13]Lara A,Kolasani A,RamamurthyB.Network innovation using OpenFlow: a survey[J].IEEE Communications Surveys& Tutorials,2014,16(1):493- 512.   
[14] IEEE standard 802.11k-20o8,part11:wireless LAN medium access control (MAC）and physical layer (PHY）specifications amendment 1:radio resource measurement of wireless LANs [S].2008.   
[15]TirumalaA,QinF,Dugan J,et al.The TCP/UDP bandwidth measurement too [EB/OL].(2005-08-06)[2015-08-29]. http://dast.Nlanr. net/Projects.