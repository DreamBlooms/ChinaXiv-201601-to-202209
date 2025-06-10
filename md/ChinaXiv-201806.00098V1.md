# 软件定义空基骨干网中的编码感知机会路由方案

丁然，梁俊，肖楠，孙伟超(空军工程大学 信息与导航学院，西安 710077)

摘要：为保障空基通信任务的高效实施，针对软件定义空基骨干网中路由信息交互时存在的时延、开销以及可靠性方面的不足，提出一种改进的兼具软件定义与网络编码优势的CAOR-SD方案。该方案在沿用编码感知机会路由基本思想的前提下，将节点距离与编码收益综合考虑构造转发消耗函数进行候选转发节点优先级的分配，从而提高网络传输效率；同时对控制报文的反馈机制和节点的流表结构进行设计，控制开销有效降低。仿真结果表明，该路由方案可较好地适应空基通信场景，能够降低传输时延和路由开销，提高网络吞吐量和数据成功传输率。

关键词：软件定义网络；空基骨干网；网络编码；机会路由；优先级分配中图分类号：TP393 doi:10.3969/j.issn.1001-3695.2018.03.0227

# Coding aware opportunistic routing scheme for software-defined airborne backbone networks

Ding Ran,Liang Jun, Xiao Nan, Sun Weichao (Information&Navigation College,Air Force Engineering University,Xi'an71oo77,China)

Abstract:To safeguard the eficient implementation of airborne communications misions,this paper developed acoding awareopportunistic routing scheme which hadadvantages of both SDNand network coding,aiming atthe insuficientof timeliness,reliabilityandoverheadintheinteractionofrouting informationfortheairborebackbonenetworks.Following the basic ideaof coding aware opportunisticrouting,this routing scheme structured a forwarding consumption function combining thedistance of nodesand the coding gains to asign priorities ofcandidate nodes,thus itcould improve the network transmission eficiency.Besides,this routing scheme designed the feedback mechanism of thecontrol messge and the structure offlow table,thus itcould reduce the control overhead.The simulationresults show that this routing scheme can adaptto airbormecommunication,inadition,itcanreduce thetransmisiondelayandroutingoverheadwhileitcangreatly improve the network throughput and transmission rate.

Key words:softwaredefined network；airborne backbone networks；network coding；opportunisticrouting；priority assignment

# 0 引言

空基骨干网络是拓扑相对稳定的高速骨干承载网络[1]，自20世纪90年代末美国国防部提出全球信息栅格(GIG)以来，它已成为美军实施信息化战争的关键信息基础设施，是国防部信息交换的一个重要空中网络设施，为GIG提供空中连通性。对于我国来说，空基骨干网络也将成为支撑未来远程远海作战通信的关键力量。近年来，由于传统骨干网存在的异构网络互操作能力差、灵活性低、部署周期大等问题，转发能力与应用需求之间的矛盾日趋明显，网络控制管理愈发复杂，SDN(softwaredefined network，软件定义网络)错误!未找到引用源。错误!未找到引用源。的发展为空基骨干网的设计提供了新思路，越来越多的专家提出解除控制面与转发面间的紧耦合关系，将具有灵活性、开放性、可编程性的 SDN 思想引入到空基骨干网中错误!未找到引用源。\~1错误!未找到引用源。软件定义空基骨干网是指基于SDN架构的更加灵活高效的网络，控制与转发分离的模式能够逻辑集中式地进行资源分配，提高链路利用率，同时能够缩短网络部署周期，有效提高网络面向任务的弹性应变能力。而为保证空基骨干网通信传输功能的高效实现，如何设计高效的路由策略是直接影响其网络效能的关键问题错误!未找到引用源。错误！未找到引用源。，近年来结合网络编码与机会路由的路由方案在提高这些网络性能方面表现出巨大的潜力和优势错误！未找到引用源。。2006年，Kat 等人错误！未找到引用源。首次提出了在协议层面上实现的网络编码传输方案COPE，大大提高了网络的通信吞吐性能；2007年，文献[15]中提出流内网络编码机会路由MORE (MAC-independent opportunistic and encodingprotocol，MAC层无关的机会路由与编码协议)，降低了重复投递的概率，显著提高网络吞吐量；2012年，文献[16]中提出应用于无线 Mesh 网络的 CAOR(coding aware opportunisticrouting，编码感知机会路由)，在COPE的基础上主动创造编码机会，将网络编码的判断融入候选节点选择与优先级分配中，更大程度地获得路由增益。

考虑到CAOR 协议在提高无线网络性能方面的优势错误!未找到引用源。\~错误!未找到引用源。，本文拟采用编码感知机会路由思想实现软件定义空基骨干网控制层面的路由功能。然而，由于软件定义空基骨干网是采用逻辑集中式的方式仅由控制节点进行路由的计算，控制节点开销尤其大，相比于传统空基骨干网在时效性、传输可靠性、网络吞吐量以及路由开销方面具有更高的要求，为此，本文提出改进的在软件定义空基网络中具有更好性能的CAOR-SD（coding aware opportunistic routing for softwaredefinednetwork，软件定义网络的编码感知机会路由）协议方案。

# 1 系统模型与基本思想

空基骨干网络是指由动态轨迹可预测的大型空中平台（如指挥通信飞机、预警机、电子侦察机、高空无人机和重型直升机等）通过稳定、高带宽链路连接的一种为其他节点或网络提供服务的高速骨干承载网络。本文引入软件定义网络思想，构建一种逻辑集中式、物理分布式的空基骨干网，使空基平台能够充分发挥大范围快速部署、灵活高效组网的优势。如图1所示，空基骨干节点为控制节点，每个控制节点既要获取所在子网的拓扑、管控子网内交换机，还要与相邻的控制节点交换拓扑信息以获取全局的拓扑结构，从而每个控制节点都能根据全局视图计算转发路径；接入子网内的非骨干节点为普通节点，将自身拓扑信息发送给控制节点，控制节点计算转发路径后通过下发流表对其下发路由指令。

![](images/f1b6ca1e92c3a0b4909364c2f98cda41a788027449e09e1ae93545b991306610.jpg)  
图1空基骨干网系统示意图

CAOR的基本思想可用图2举例阐述。假设包 $\mathbf { P } _ { 1 }$ 、 ${ \bf P } _ { 2 }$ 分别由源节点 $\mathbf { S } _ { 1 }$ 、 $S _ { 8 }$ 发送至目的节点 $S _ { 3 }$ 和 $S _ { 6 }$ ，据传统路由策略可能得到转发路径分别为 $\mathbf { S } _ { 1 } { - } \mathbf { S } _ { 2 } { - } \mathbf { S } _ { 3 }$ 和 $S _ { 8 - S 7 - S 6 }$ 。而此时，邻居节点$\mathrm { S } _ { 4 }$ 、 $S _ { 5 }$ 、 $S _ { 6 }$ 都能侦听到包 $\mathbf { P } _ { 1 }$ ，同理 ${ \bf S } _ { 3 }$ 、 $\mathrm { \Delta } \mathrm { S } _ { 4 }$ 、 $S _ { 5 }$ 都能侦听到包 ${ \bf P } _ { 2 }$ 。

在CAOR中，源节点发送数据包时会选择根据某种度量计算的节点作为候选转发节点集合，集合中的节点会将侦听到的包进行逻辑编码并依据某种机制确定的节点优先级进行转发。假定图中 $S _ { 5 }$ 转发优先级最高，则它将 $\mathbf { P } _ { 1 } \oplus \mathbf { P } _ { 2 }$ 发送给节点 $S _ { 6 }$ 后， $S _ { 6 }$ 便可将其与侦听到的 $\mathbf { P } _ { 1 }$ 解/编码得到 ${ \bf P } _ { 2 }$ ，其他同理。由此可见，CAOR充分利用无线信道的广播特性，增加了与其他流进行编码组合的机会，尤其在有损的网络中，每一批数据包很可能不能完整到达目的节点，这种机制通过编码转发降低传输次数，增加编码机会，提高网络吞吐率。

![](images/271e9c79bcf56cdde7aa8ae6162c581c48f8226afcf30d4548be545d60276a07.jpg)  
图2编码感知机会路由基本思想

在软件定义空基骨干网中引入编码感知机会路由方案具有很大潜能。为进一步提高网络性能，降低路由开销，本文提出改进的CAOR-SD方案，通过控制节点对定义的转发消耗函数的计算结果选取候选转发节点集中转发效能最大的节点优先发送，同时控制报文采用逐跳反馈机制，降低分组转发次数，提高链路利用率。整个路由决策过程全部由控制节点计算完成，控制节点间交换全局拓扑信息，并通过OpenFlow 协议下发流表实现对接入子网中数据包传输路径的弹性控制，从而实现一个逻辑集中式、物理分布式的大型空基网络，集中式的控制方式能够有效弥补网络路由调整的滞后性。

# 2 CAOR-SD 实现机制

# 2.1工作流程描述

a)网络拓扑信息的发现和管理是控制节点路由计算的前提。控制节点广播探测报文，邻居节点存储报文中的邻居信息并继续转发；普通节点将收集的拓扑信息通过邻居节点定期连续地转发给控制节点，同时获取到其对应控制节点的路径。控制节点通过普通节点发送的报文与控制节点之间的信息共享，实时掌握全网拓扑状态，进而计算路由下发流表给普通节点。

b)当普通节点发送数据时，首先查询流表项，若有匹配的流表项，则按照其对应的转发规则进行转发；若无即为新流加入，则需向其控制节点请求该报文的转发规则。

c)控制节点接收到请求报文时，从报文中获取源节点与目  
的节点的IP地址，根据候选转发节点选取与优先级排序方法进  
行路由的计算，并通过响应报文将其转发规则下发到对应节点。d)目的节点接收到一定数量的编码报文后解码为源数据

包，源节点收到ACK报文后切换至下一批次报文传输，源节点发送退出报文告知控制节点，控制节点不再为其计算和更新转发规则，普通节点通过流表项的超时机制删除该流表项。至此，一个批次的数据报文成功转发。

本文CAOR-SD实现过程中控制节点与普通节点的主要模块如图3所示。

路由生成需求API  
控制节点 拓扑信息 收集模块 候选转发节 点选取与优 先级分配 流表计算 模块 信息共享 模块  
主要模块报文处理模块OpenFlow协议  
普转发 拓信 流表 流表管理 控制器选模块报文处理模块

# 2.2候选转发节点选取与优先级分配

CAOR-SD中节点通过广播给候选转发节点集转发数据包。候选转发节点选取应满足的前提有：节点间能相互侦听到；是发送节点的一跳邻居节点；比发送节点距离目的节点更小。本文采用路由协议中经常采用的ETX(expected transmissioncount期望传输次数）作为路由度量参数来进行“距离大小”的判断。若用 $\mathsf { N } _ { ( \mathbb { S } , \mathrm { D } ) }$ 表示一个数据包从源节点S到目的节点D路径上节点r的下一跳候选转发节点集， $\mathrm { \ n ( s , D ) i }$ 表示集合中第i个节点，在路由发现阶段可通过目的节点向源节点的迭代求得节点的ETX值，将链路 $\mathbf { r } { \cdot } \mathbf { n } ( \mathbf { S } , \mathbf { D } ) \mathrm { i }$ 与节点 $\mathbf { n } ( \mathbf { s } , \mathbf { D } ) \mathrm { i }$ 的ETX值之和记为Wi，$\mathbf { W } _ { 1 }$ ， $\mathbf { W } _ { 2 }$ ， $\cdots \mathrm { W _ { n } }$ 的期望则为节点r的ETX值。数据报头中都会携带下一跳候选转发节点集信息。当某节点收到数据包时，首先根据数据报头中信息判断自己是否属于候选转发节点集，若属于则缓存该数据包并寻找编码机会继续转发；若不属于则丢弃该数据包。

编码收益是表征网络编码参与路由效能的重要参数，编码收益可用一个报文与其他报文编码发送时能捎带其他报文获得的报文的前进距离来表示。设Z表示数据包的ETX前进距离，其含义为转发节点的ETX值与下一跳候选转发节点的ETX值期望的差值。则定义节点r将源数据包P和 $\mathbf { m }$ 个数据包进行编码转发的编码收益NCGr如式（1）所示。

$$
N C G _ { _ { \mathrm { r } } } { = } Z _ { \mathrm { s } } { + } \sum _ { \mathrm { k } = 1 } ^ { \mathrm { m } } Z _ { \mathrm { k } }
$$

其中： $Z _ { \mathrm { S } }$ 为源数据包的ETX前进距离； （204号 $\sum _ { \mathrm { k = 1 } } ^ { \mathrm { m } } Z _ { \mathrm { k } }$ 为数据包携带的其他 $\mathbf { m }$ 个数据包的ETX前进距离。

本文定义转发消耗函数COST(r)对转发节点效能进行评估，如式（2）所示。

$$
C O S T ( \mathrm { r } ) { = } E T X _ { \mathrm { _ { r } } } { - } \alpha N C G _ { \mathrm { _ { r } } }
$$

其中： $E T X _ { \mathrm { r } }$ 表示节点 $\mathrm { ~ \bf ~ r ~ }$ 的期望传输次数； $N C G _ { \mathrm { _ { r } } }$ 表示该节点的网络编码收益； $\alpha$ 是网络编码的属性因子，若报文具有编码机会则 $\scriptstyle { \alpha = 1 }$ ，否则 $\scriptstyle { \alpha = 0 }$ 。通过对节点的转发消耗函数的计算对具有编码机会的候选转发节点进行优先级分配。据以上定义分析易得，本文定义的转发消耗函数是同时将节点距离与编码收益的判断融入转发节点的优先级排序中，此消耗函数越小转发性能越高，故分配其优先级越高。用 $\boldsymbol { \mathrm { ~ n ~ } } _ { ( S , D ) } ^ { \mathrm { K } }$ 表示候选转发节点中优先级为K的节点，K越小表示优先级越高，则可将根据优先级排序的候选转发节点集表示为$N _ { _ { ( S , D ) } } = [ { \boldsymbol { \mathrm { n } } } _ { _ { ( S , D ) } } ^ { 1 } , ~ { \boldsymbol { \mathrm { n } } } _ { _ { ( S , D ) } } ^ { 2 } , . . . , { \boldsymbol { \mathrm { n } } } _ { _ { ( S , D ) } } ^ { \mathrm { K } } ] _ { \circ }$ （

候选转发节点的优先级分配算法如下所示：

输入：节点r  
输出：节点r按优先级排序的下一跳候选转发节点集合result  
begin  
1 result=NULL  
2 for 节点r的一个邻居 $\mathbf { n } _ { \mathrm { i } }$ ， $\mathrm { i } {  } 1$ to M//节点 $\mathrm { ~ \bf ~ r ~ }$ 有M个邻居  
3 if $\mathfrak { n } _ { \mathrm { i } }$ can satisfy the conditions of candidates  
4 then $\mathbf { n } _ { \mathrm { i } }$ canbeaddedtoresult/从节点 $\mathrm { ~ \bf ~ r ~ }$ 的邻居节点中选取了  
下一跳候选转发集节点K个  
5 end if  
6 end for  
7 for $\mathrm { i } {  } 1$ toK  
8 do forj $\mathrm {  } \mathrm { K }$ down to $\mathrm { i } { + } 1$   
9 do if $\mathrm { { C O S T } ( n _ { i } ) { > } C O S T ( n _ { j } ) }$ //比较候选转发节点的转发消耗  
函数  
10 then exchange $\mathrm { { n } i \overleftrightarrow { \mathrm { { n } j } } }$   
11 else $\mathrm { \ n ^ { i } \mathrm {  { n } _ { i } / / } }$ 通过比较消耗函数进行节点优先级排序，消  
耗函数越小，优先级越高  
12 end if  
13 end for  
14 end for  
15 return result=[ nl, n²..... nK]  
end

# 2.3控制报文的逐跳反馈机制

普通数据报文通过在候选转发节点间广播，直到目的节点收到后通过ACK报文反馈至源节点进行确认；而本文软件定义空基网中的控制报文通过不断选择候选转发节点集中的最高优先级转发节点发送。由于端到端ACK反馈耗时较长，且空基骨干网存在一定的时变性、丢包率等，若使用普通端到端ACK反馈机制，将会因节点的丢包而导致大量的重传，不仅会影响数据传输的实时性，而且会增加整个网络的开销，造成网络吞吐量的降低。故本文考虑采用逐跳反馈机制，即每一跳节点接收到控制报文时便依照流表中的转发规则向上一跳节点发送ACK确认报文，发送节点通过超时重发机制保证下一跳对控制报文的接收。控制报文的逐跳反馈机制在保证数据传输可靠性、降低延迟的同时，避免了因大量重传导致控制开销大幅增加，一定程度上降低了整个网络的路由开销。

# 3 流表结构设计

传统CAOR协议中的转发节点选取和优先级排序都封装在数据报文中，占据数据报文大小的同时降低了有效吞吐量，一定程度上影响了节点的转发效能。在软件定义空基骨干网的架构下，流表的引入为此带来新的契机。控制节点通过下发流表的方式将流的候选转发节点选取、优先级排序、ACK反馈路径等广播给普通节点，普通节点将其存储在流表里。接入子网中的节点转发数据时，首先匹配流表项执行相应的转发规则。借鉴 OpenFlow v1.3 的流表结构错误:未找到引用源。，本文将节点的流表结构改进如图4所示。从图中流表结构可以看出，它比传统报文封装占据字节少，需要维护的控制信息更为简捷，在这样的模式下控制开销得以降低。

<html><body><table><tr><td>匹配 域</td><td>流优 先级</td><td>转发优 先级</td><td>ACK报 文下一 跳地址</td><td>计数器」指令</td><td></td><td>超时定 时器</td></tr></table></body></html>

a）匹配域：对数据包匹配，即匹配流号。b）流优先级：流表项的匹配次序。c）转发优先级：若节点在对应流的候选转发节点集中，则为优先级高低；反之，则为零。d)ACK报文下一跳地址：若节点在ACK报文反馈路径上，则为ACK报文的下一跳IP地址；反之，则为0。e）计数器：更新匹配数据包的计数。f）指令：修改对数据包的动作集或处理，若转发优先级为零则丢弃该报文。g）超时定时器：一个流的最长有效时间或最大空闲时间，若一段时间内该流表项没有被匹配，则该流表项将被删除。

# 4 仿真与分析

空基骨干网络稳定性较高，在一定时间内各骨干节点相对位置基本保持不变，故本文将空基节点的运动抽象为质点匀速运动模型。在MATLAB 仿真环境下，假设网络存在6个骨干控制节点、30个普通接入节点的场景下，比较AODV（adhocon-demand distance-vector,Adhoc 按需距离矢量路由)[21]、CAOR(codingaware opportunistic routing，编码感知机会路由)[l6]与本文改进的CAOR-SD三种路由协议的性能。结合大型空中平台飞行速度等因素，设置仿真随机分布区域为 $2 5 k m \times 2 5 k m$ 的正方形范围，节点移动速度为 $3 0 0 \mathrm { m / s }$ ，通信半径为 $5 0 \mathrm { k m }$ ，仿真时间为 $3 0 ~ \mathrm { m i n }$ ，并以不同的数据发送速率模拟不同网络负载的情况。由于软件定义空基骨干网对时效性、可靠性与低开销等性能要求较高，故选取传输时延、网络吞吐量、路由开销与成功传输率作为网络性能评价指标进行仿真和分析。

![](images/1c2f5b758fc84841e796add46b5cfb41f62d98eac2c1e8eb36f90cdaab241ddf.jpg)  
图4流表结构

# 4.1传输时延与网络吞吐量

传输时延是指数据分组从源节点发出，直至到达目的节点所经历的时长；网络吞吐量是指单位时间内所有数据流的聚合吞吐量。图5和6显示了随着数据发送速率的变化在不同网络负载下的三种路由方案的传输时延与网络吞吐量的变化。通过图5和6可以看到，由于通过采用候选转发节点的方式代替AODV中固定的转发节点能够有效缓解网络拥塞，改进的CAOR-SD方案与CAOR方案的时延与吞吐量性能一直优于不采用网络编码的AODV，在数据发送速率为40kbps以下时，这种差距还并不明显；随着网络负载不断增大、冲突增多，此时结合编码机会大小决定转发优先级的CAOR-SD方案在三条仿真曲线中的优势逐渐体现。这是因为本文改进的方案能够主动感知编码机会，而且将节点距离与编码效率的判断同时融入转发节点的选择与优先级排序中，从而降低了数据转发时延，提高了网络吞吐量。但当数据发送速率超过180kbps 时，由于网络严重拥塞抵消了编码收益，改进方案对时延和吞吐量性能的提升不再明显。

![](images/e8250cd08de3db36e0a702955cae6db557898330e92b4978633503ea27aff6e5.jpg)  
图5不同数据发送速率下的传输时延  
图6不同数据发送速率下的网络吞吐量

# 4.2路由开销与成功传输率

路由开销定义为统计时间内控制分组数占总通信数据量的比值；成功传输率定义为节点成功接收的数据分组数与源节点发送的数据分组数的比值。图7和8为不同网络负载下的三种路由方案的路由开销与成功传输率的仿真结果。通过图7可以看出，负载很小时，AODV方案相比于CAOR和CAOR-SD方案更具有优势，这是因为此时AODV在数据发送时才进行路由发现，故路由开销较小；随着网络负载增大，数据发送速率超过60 kbps 时，AODV方案维护路由信息所需的控制分组数大大增加，开销迅速增大，对比而言CAOR-SD方案的路由开销不仅较小而且稳定。原因在于CAOR-SD方案只需要控制节点计算和维护全网的路由信息，所需的控制分组数比在全网内维护路由信息减少了很多，而流表的引入使报文封装占据字节减少，所以大大减少了整个网络的控制开销；同时由于本文控制报文采用逐跳反馈的机制，在减少重传的同时降低了路由开销。通过图8可以看到，本文CAOR-SD方案的成功传输率性能总体上优于其他两种方案，随着网络负载的增大其优势越来越明显，尤其是AODV协议的传输率性能降低幅度达到 $40 \%$ ，而CAOR与CAOR-SD方案的传输率能较好地维持，由此可见通过网络编码数据传输的可靠性得到很大提高；同时，本文CAOR-SD方案中控制报文的逐跳反馈机制也进一步保证了数据传输的可靠性。

![](images/dfd1c020cac7958031d8de09ea751c685ac10aeca57fdd1259a00c37a28efddb.jpg)  
图7不同数据发送速率下的路由开销

![](images/29c979415bf1d2d90652a1fdbda14de47f68c7c1f765131129aa356125a096cf.jpg)  
图8不同数据发送速率下的成功传输率

# 5 结束语

软件定义空基骨干网是近年来随着空基通信需求蓬勃发展正兴起的一种新型网络，相较于传统空基网络该网络部署周期缩短，面向任务的灵活通信能力提高，同时其路由能够解决传统网络节点对网络认知不一致、路由调整滞后等问题，网络整体性能大大提高。为满足该网络对时效性、可靠性以及低开销等网络性能的更高要求，针对这种新型的逻辑集中式、物理分布式的空基骨干承载网络特点，本文提出一种更适用于该场景的编码感知机会路由方案CAOR-SD。该方案将节点距离与编码收益综合考虑，定义了一个转发消耗函数来进行候选转发节点优先级的分配，同时对控制报文的逐跳反馈机制和节点的流表结构进行了设计。仿真结果表明，本文提出的CAOR-SD方案相对于传统无线路由能够在一定程度上减小传输时延、提高网络吞吐量、增大数据成功传输率，同时降低路由开销，具有更好的网络整体性能。

# 参考文献： 乡兮义

[1]梁俊，胡猛，管桦，等．空间骨干网络体系架构与关键技术研究[J]. 空军工程大学学报：自然科学版，2016,17(4):52-58.(Liang Jun,Hu Meng,Guan Hua,et al.Research on space backbone network architecture and key technologies [J].Journal of Air Force Engineering University: Natural Science Edition,2016,17 (4): 52-58.)   
[2] Xia Wenfeng，Wen Yonggang，Foh C H,et al.A surveyon software-defined networking [J]. Communications Surveys&Tutorials IEEE,2015,17(1): 27-51.   
[3] Bernardos C J,De L O A, Serrano P,et al. An architecture for software defined wireless networking [J]. Wireless Communications IEEE,2014,21 (3): 52-61.   
[4]Open Networking Foundation. SDN architecture overview [R]. 2013.   
[5] 黄韬，刘江，魏亮，等．软件定义网络核心原理与应用实践[M].2nd ed. 北京：人民邮电出版社,2016.(Huang Tao,Liu Jiang,Wei Liang,et al. SDN core principles and application practice [M]. Beijing: People’s Posts and Telecommunications Press,2016.)   
[6] 张卫峰.深度解析 SDN:利益、战略、技术、实践 [M].北京：电子工业 出版社，2O14.(Zhang Weifeng.The depth resolution for SDN:profit, strategy，technology，practice[M].Beijing:Publishing Houseof Electronics Industry, 2014.）   
[7]Cheng Bownan,Block FJ,Hamilton B R,et al.Design considerations for next-generation airborne tactical networks [J]. IEEE Communications Magazine,2014,52 (5): 138-145.   
[8]Sampigethaya K. Software-defined networking in aviation: opportunities and challenges [C]// Proc of IEEE Integrated Communication, Navigation, and Surveillance Conference.2Ol5:1-21.   
[9]Elmasry G, Mcclatchy D,Heinrich R,et al. A software defined networking framework for future airborne connectivity [Cl// Proc of IEEE Integrated Communications， Navigationand SurveillanceConference. 2017: 2C2-1-2C2-9.   
[10]王俊，陈志辉，田永春，等．软件定义网络技术在战术通信网中的应用 研究[J].通信技术,2014,47(12):1392-1399.(Wang Jun,Chen Zhihui, Tian Yongchun,et al. Application of software-defined network technology in tactical communication network [J]. Communication Technology,2014, 47 (12): 1392-1399.)   
[11] Ramirez R.Link management in the air force airborne network [C]// Proc

of IEEE Military Communications Conference.2005.   
[12] Tiwari A,Ganguli A, Sampath A.Mobility aware routing for the airborne network backbone[C]// Procof IEEE MilitaryCommunications Conference.2008:1-7.   
[13] PahlevaniP,Lucani DE,Pedersen M V,et al.PlayNCool: opportunistic network coding for local optimization of routing in wireless mesh networks [C]//Proc of IEEE GLOBECOMWorkshops.2013:812-817.   
[14]Katti S,Rahul H,Hu Wenjun,et al.XORs in the air:practical wireless network coding[C]//Proc of Conference on Applications,Technologies, Architectures,and Protocols for Computer Communications ACM.2006: 243-254.   
[15] Chachulski S,Jennings M, Katti S,et al. Trading structure for randomness in wireless opportunistic routing [C]// Proc of ACM SIGCOMM 2007. New York:ACMPress,2007:169-180.   
[16] Chung Kuncheng,Chou Yichun,Liao Wanjiun.CAOR:coding-aware opportunistic routing in wireless Ad hoc networks [C]// Proc of IEEE International Conference on Communications.2012:136-140.   
[17]Katti S,Rahul H,Hu Wenjun,et al.XORs in the air: practical wireless network coding [J].IEEE//ACM Trans on Networking，2OO8，16(3): 487-510.   
[18] Guo Bin,Li Hongkun, Zhou Chi,et al. Analysis of general network coding conditions and design of a free-ride-oriented routing metric [J].IEEE Trans on Vehicular Technology,2011,60 (4):1714-1727.   
[19] Yan Yan,Zhang Baoxian，Zheng Jun，et al.CORE:a coding-aware opportunistic routing mechanism for wireless mesh networks [J].Wireless Communications IEEE,2010,17(3):96-103.   
[20]樊勇兵，陈楠，黄志兰，等．解惑 SDN[M].北京：人民邮电出版社, 2015.(Fan Yongbing,Chen Nan,Huang Zhilan,et al. Guide for SDN [M]. Beijing:People’s Posts and Telecommunications Press,2015.)   
[21] Glabbeek R,Portmann M,Tan WL,et al.Modelling and verifying:the AODV routing protocol [J]. Distributed Computing,2016,29 (4): 279-315.