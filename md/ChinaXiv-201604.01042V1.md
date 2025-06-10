# 基于802.11的小卫星编队网络性能仿真

康海龙1²，姜秀杰」，熊蔚明1(1.中国科学院空间科学与应用研究中心北京100190；2.中国科学院大学北京 100049)

摘要：为了保证空间探测任务的顺利进行，小卫星编队需要可靠的星间通信。基于802.11,设计了小卫星编队网络协议架构。首先搭建了卫星飞行编队网络协议栈，针对星间通信距离大导致的高时延，对物理层、数据链路层进行了适应性修改，分析了网络层路由协议,然后对四种典型的卫星编队网络进行了模型分析。通过NS3网络仿真工具，对星间通信网络进行了性能仿真。仿真结果表明,基于802.11的网络架构，可以保证星间通信，不同编队网络性能差别较大，可根据任务进行调整。

关键词：星间通信；网络性能；仿真；NS3

中图分类号：TN927 文献标识码：A 文章编号 :1674-6236(2016)01-0082-04

# Protocol simulation of Inter-satellite communication for satellite formation network based on 802.11

KANG Hai-long1,2, JIANG Xiu-jie1,XIONG Wei-ming1 (1. Center for Space Science and Applied Research， Chinese Academy of Sciences，Beijing 100190, China; 2. University of Chinese Academy of Sciences，Beijing 10o049，China)

Abstract:Inorder toensure the success of space exploration mission,thesmallstelite formationrequiresreliable intersatelite communications.Basedon 8O2.11，smallsateliteformation network protocolarchitecturewasdesigned.Firstly, network protocolstack wasbuiltaccording theOSIstack layers,thekeyparameters of physicallayeranddatalink layerof was tuned tomeettherequirementofinter-satelitecommunication,the network layerouting protocolwasanalysed,andthenthe satelite networkformation modelwas madeandanalysed.WiththeaidofthenetworksimulationtoolNS3,performanceoffour typicalformationnetwork wassimulated.Simulationresultsshowthatthenetwork protocolarchitectureensures inter-satelite communicationsbasedon 8O2.11.Although network performance varies greatly in diferentflyning formations，itcanbe adjusted according to the task requirements.

Key words: inter-satelite communication；performance analysis；simulation ;NS3

DOI:10.14022/j.cnki.dzsjgc.2016.01.023

近年来，随着新能源、新材料和空间无线通信等关键科学技术的迅猛发展，以平台为中心的传统单个航天器模式正在向以网络为中心的多航天器协同控制模式转变，将功能不同的独立的小卫星放在太空中形成一个“卫星编队”或“虚拟卫星”，相互之间协同工作，成为一种潜力巨大的空间系统部署方式[1-3]。小卫星通过星间通信链路的互通互联构成卫星网络，对空间环境进行多角度、多时空探测已成为空间物理的探测一个重要的发展趋势。

文中基于802.11网络协议架构，针对星间链路距离大导致传播时延长等问题，对WiFi物理层和数据链路层进行适应性修改，使其适用于卫星网络，用NS-3网络仿真工具对常见的卫星编队构型(串珠形、环形、星行、网状形)网络进行了性能仿真。

# 1网络协议栈设计

参照地面OSI网络模型，基于802.11标准，将卫星编队

# 网络协议栈设计分为五层结构，如图1所示。

![](images/8bc399f4b89661fdb674aa2db13843ea25046da315f3c7bc342b878fa56c843a.jpg)  
图1卫星网络协议栈

# 1.1 物理层

物理层的性能决定卫星间通信的最大通信距离。802.11的物理层最初是为WiFi设计，通信距离大约为 $1 0 0 \mathrm { ~ m ~ }$ 。根据空间探测任务的不同，星间通信距离一般在几十公里到几千公里不等。因此卫星发射功率和天线增益必须增加来加大最大通信距离。目前在成熟的商业技术中，最大发射功率为

$3 0 ~ \mathrm { d b m }$ 。对于小卫星电源、尺寸等资源的限制，假设卫星发射功率为 $3 0 ~ \mathrm { d b m }$ ，有 $1 0 ~ \mathrm { d b i }$ 的天线增益。那么星间最大通信距离可通过下面公式得到：

$$
 { \mathrm { M a x ~ r a n g e { = } } } \frac { \lambda } { { 4 \pi } } \sqrt { - \frac { P _ { T X } { \times } G _ { T X } { \times } G _ { R X } } { { 2 9 0 { \times } { \kappa } { \times } { S P S } { \times } \log \left( { 2 } { \times } ( P S R _ { \mathrm { r e q } } ^ { \mathrm { 1 / 8 P P } } ) \right) } } }
$$

其中， $2 . 4 ~ \mathrm { G H z } ~ \mathrm { W i } .$ -FiISM波长 $\lambda$ 为 $0 . 1 2 5 ~ \mathrm { m } , P _ { \mathrm { r x } }$ 为发射功率， $G _ { \mathrm { T X } }$ 和 $G _ { \mathrm { { R X } } }$ 分别为天线增益，玻尔兹曼常量 $K$ 为 $1 . 3 8 1 0 ^ { - 2 3 }$ $\mathrm { J } / \mathrm { K }$ 。物理层选择802.11b1Mbps模式，每秒钟符号数为1Msps，每包比特数为16512，即每包2064bytes。因此，得到星间最大通信距离为 $5 0 0 ~ \mathrm { k m }$ 下，包成功发送率PSR为 $67 \%$ 。

# 1.2 数据链路层

802.11的MAC子层通过分布式协调功能(DCF)实现对共享媒介的接入，DCF建立在载波侦听多路访问/冲突避免(CSMA/CA,CarrierSenseMultipleAccesswith CollisionAvoidance)协议的基础上，该协议采用共享单信道的模式，通过RTS-CTS-DATA-ACK4次握手机制完成分布式数据业务的接入过程，并基本解决了隐藏终端和暴露终端问题。工作流程如图2所示。

![](images/b579e4a066e541f47095f89facb88b03bcd7b1447ccf2c18d1dae5369a16bbf4.jpg)  
图2CSMA/CA工作流程图Fig.2CSMA/CA flow chart  
图3四种典型卫星编队 Fig.3Four typical satellite flying formation

在IEEE802.11DCF中，连续的帧之间必须保持一定的间隔，以便留给相关的节点足够的处理时间并控制信道资源访问的优先级。在IEEE802.11中一共定义了4种帧间间隔(InterFrameSpace，IFS)，按占用时间从短到长分别是：SIFS$< \mathrm { P I F S } < \mathrm { D I F S } < \mathrm { E I F S }$ 。由于星间通信的长距离导致的高时延，相应的帧间间隔需要修改，以适应物理层参数的改变。

# 1.3 网络层

网络层提供路由选择，拥塞控制和网络互联。根据对网络拓扑结构变化的反应不同，移动Adhoc网络的路由协议主要分为先验式（Proactive）和按需式路由协议（ $\mathrm { O n - }$ demand)。

在先验式路由协议中，当检测到卫星网络拓扑结构发生变化时，节点发送路由更新消息，收到路由更新消息的节点将更新自己的路由表，以保证路由信息的一致性、及时性和准确性。

与先验式路由协议相对应地，按需路由协议是根据卫星发送节点的需要，按需进行路由发现过程，网络拓扑结构信息和路由表内容也是按需建立的，其内容可能仅仅是整个网络拓扑结构信息的一部分。

按需路由的优点是不需要周期性的广播路由信息，节省了一定的网络资源；缺点是在发送数据分组时，若没有到达自的节点的路由，要启动路由发现过程来寻找路由，所以数据分组需要等待一定时间的延时，并且路由发现过程通常采用在全网范围内的广播来完成，这在一定程度上也抵消了按需路由机制带来的好处。

因此，卫星飞行编队网络一旦形成后，先验式路由协议中的路由表可以准确地反映网络的拓扑结构，源节点一旦要发送数据分组，就可以立即获得到达自的节点的路由，提高了实时性。

# 2 卫星编队网络模型分析

根据空间探测任务的不同，需要构建不同的卫星网络编队，四种典型的卫星编队，包括串珠形编队、环形编队、星形编队和网状形编队，如图3所示。

名 保设仪设设仪仪 安 (a)串珠形编队 中环形 (a)lineformation (b)ring formation 福 净悠 武汉设议 灭中 收 （c）星形编队 （d）网状形编队 (c)star formation (d)mesh formation

串珠形编队可模型化为

$$
G _ { l i n e } { = } \{ S , L , f _ { \mathrm { l i n e } } \}
$$

其中 $S { = } [ s _ { 1 } , s _ { 2 } , \cdots , s _ { n } ]$ 代表编队中的卫星， $n$ 为卫星数量， $L$ 代表卫星网络中从源节点到目的节点所经过路由的跳数， $m =$ $\mathrm { s u m } ( l _ { i , j } )$ 代表卫星网络的总跳数 $, f _ { \mathrm { l i n e } }$ 代表 $N { \times } N$ 邻接矩阵。 $l _ { i , j } { = } 0$ 表示卫星 $s _ { i }$ 和 $s _ { j }$ 没有直连的星间链路， $l _ { i , j } { > } 0$ 代表 $s _ { i }$ 与 $s _ { j }$ 进行通信所经过的路由跳数。串珠形编队模型 $( N { = } 6 )$ 如下：

$$
f _ { \mathrm { i n e } } = [ l _ { i , j } ; s _ { i } , \cdots , s _ { j } ] = \left[ { \begin{array} { l l l l l } { 0 } & { 1 } & { 2 } & { 3 } & { 4 } & { 5 } \\ { 1 } & { 0 } & { 1 } & { 2 } & { 3 } & { 4 } \\ { 2 } & { 1 } & { 0 } & { 1 } & { 2 } & { 3 } \\ { 3 } & { 2 } & { 1 } & { 0 } & { 1 } & { 2 } \\ { 4 } & { 3 } & { 2 } & { 1 } & { 0 } & { 1 } \\ { 5 } & { 4 } & { 3 } & { 2 } & { 1 } & { 0 } \end{array} } \right] , i , j = 1 , 2 , 3 , 4 , 5 , 6
$$

同理，环形编队模型为：

星形编队：

网状形编队：

# 3卫星编队网络仿真

# 3.1 仿真设计

在Ubuntu14.04环境下，使用NS3对四种卫星编队网络性能进行仿真，评价网络性能采用吞吐量指标。仿真参数如表1。

表1仿真参数Tab.1Simulation parameters  

<html><body><table><tr><td>参数</td><td>值</td></tr><tr><td>网络仿真工具</td><td>NS-3(version 3.21)</td></tr><tr><td>操作系统</td><td>GNU/Linux(Ubuntu 14.04- 32 bit)</td></tr><tr><td>仿真时间</td><td>700 s</td></tr><tr><td>卫星数量</td><td>6</td></tr><tr><td>星间距离</td><td>500 km</td></tr><tr><td>SIFS</td><td>0.01 ms</td></tr><tr><td>DIFS</td><td>3.37 ms</td></tr><tr><td>路由协议</td><td>OLSR</td></tr><tr><td>无线频段</td><td>2.4 Ghz</td></tr><tr><td>带宽</td><td>20 MHz</td></tr></table></body></html>

# 3.2 仿真结果

图4为串珠形编队网络吞吐量随时间变化，在串珠形编队中，通过邻接矩阵计算，一共有70路由跳数，平均吞吐量在 $1 5 0 ~ \mathrm { { K b p s } }$ 。由于串珠形编队容易调整姿态，在编队中没有主星，易于维护编队构型。但是每颗星只能跟邻星通信，造成传输效率低，6颗星编队时，最大跳数达到5，鲁棒性差。

图5为环形编队吞吐量随时间变化，在环形编队中，邻接矩阵最多有54跳数，平均吞吐量在 $1 2 6 ~ \mathrm { { K b p s } }$ 。对于环形编队，每颗星与最远的星通信跳数在3跳以内。每颗星在网络中有同样的位置，比串珠形编队有较好的鲁棒性，一旦其中有颗星发生故障，可以很快进行调整新的环形，但是由于多跳特性，依然会造成传输效率偏低。

图6为星形编队编队吞吐量随时间变化，在星形编队中，与环形编队一样，有54跳数，平均吞吐量在 $1 0 0 ~ \mathrm { { K b p s } }$ 但是星间通信最大跳数在2跳以内。星形编队常常是主从结构。每颗从星通过主星与另一颗从星进行通信，灵活性较高，

![](images/60214a72edfb958f95cbfafc1a375321dc9217b4706564d6ac6f0cfe41ee22b9.jpg)  
图4串珠形编队吞吐量随时间变化 Fig.4Time vs throughput: line formation

![](images/989709c690b901d40f2dc356e8569d4de9bce99c28d726cc714975589aaef426.jpg)  
图5环形编队吞吐量随时间变化 Fig.5Time vs throughput: ring formation

![](images/61777f9796d4aa96e97467e25345ee3f8a02e35fb37dff999a2e837ed5036072.jpg)  
从星发生故障，对整个网络7-影响较低。但是，会造成主星通信拥堵。  
图6星形编队吞吐量随时间变化 Fig.6Time vs throughput: star formation

图7为网状形编队吞吐量随时间变化，在网状形编队中,星间通信跳数最多有30跳数,平均吞吐量在 $4 2 0 ~ \mathrm { k b p s }$ □这种编队，鲁棒性高，没有中心节点，每颗卫星地位相当，无论哪颗卫星损坏，对整个飞行编队网络影响小，每颗星可以互相直连通信，数据通信效率高，时延小。但是由于在天线设

![](images/cba5c3597cc6c0c4cb1c2593b76995ade1f8519354abf8e1b5ef059d21898939.jpg)  
计等资源限制下，这种编队实现起来难度很大。

# 4结论

基于802.11，设计了小卫星编队网络协议栈，分析了四种典型飞行编队网络，进行了性能仿真。方案满足了空间探测任务星间通信，提高了小卫星编队空间任务论证的准确度和可靠性，具有较高的工程参考价值。

# 参考文献：

[1]胡敏,曾国强.分离模块集群航天器发展概况[J].装备指挥技术学院学报，2011，22(4):61-66.

[2]苟亮，魏迎军，申振，等.分离模块航天器研究综述[J].飞行器测控学报，2012，31(2):7-12.  
[3]RashJ，Hogie K,Casasanta R.Internet technology for futurespace missions[J]. Computer Networks,2005,47(5):651-659.  
[4]IEEE Computer Society,Part 11:Wireless LAN MediumAccessControl(MAC）andPhysicalLayer(PHY)Specifications， IEEE Standard for Information technology -Telecommunicationsand information exchangebetweensystems，Local and metropolitan area networks -Specificrequirements[S]，IEEE Std 802.11 2012.  
[5]NakamuraY,FaberN,Mauro D,et al. HeterogeneousSpacecraft Networks:Performance analysis for low -costEarth Observation missions [C]//Aerospace Conference,2014IEEE.IEEE，2014:1-14.  
[6]陈林星，曾曦，曹毅.移动AdHoc网络:自组织分组无线网络技术[M].北京：电子工业出版社，2006.  
[7]祝莉妮.基于网络技术下计算机网络学习的研究[J].电子技术与软件工程，2015(5):20.  
[8]张国光.基于神经网络的有遮挡图像分割方法[J].电子科技,2015(5):132-135.  
[9]段立峰.基于虚拟仪器的网络测控技术的研究[J].电子设计工程,2015(18):144.

（上接第81页）

由表2可见，将本振功分移相90度调整为80度后，相位误差减小了9\~10度，从而使镜频抑制度提高了 $6 { \sim } 1 2 ~ \mathrm { d B }$ 在 $1 ~ \mathrm { G H z }$ 的频带内达到 $2 2 ~ \mathrm { d B }$ 以上。图8为优化后的镜频抑制混频器其他参数仿真结果。其中实线为变频损耗，长短虚线分别为本振和射频端口的驻波比。

![](images/b342f680bf4eebb439aa9cedca750439231404e27371ab6dde9544903b336b9f.jpg)  
图7网状形编队吞吐量随时间变化 Fig.7Time vs throughput: mesh formation   
图8变频损耗和驻波比仿真结果 Fig.8Simulation result of conversion loss and VSWR

# 4结束语

文中介绍了镜频抑制混频器在理想情况下的幅相关系，分析了镜像中频幅度差和相位差对镜频抑制度的影响。在一只 $\mathrm { K u }$ 波段镜频抑制混频器设计过程中，采取本振功分输出相差优化措施，在其他参数无明显恶化的前提下，使镜频抑制度的仿真结果在工作频带内提高了 $6 { \sim } 1 2 ~ \mathrm { d B }$ 。采用相位补偿，在镜频抑制混频器设计过程中，可实现镜频抑制度的指标优化。

参考文献：

[1]弋稳.雷达接收机技术[M].北京：电子工业出版社,2005.  
[2]魏福立.宽频带高镜像抑制度混频器[J].半导体技术，2001，26(2):37-40.  
[3]钱可伟.X波段镜像抑制混频器设计[J].中国测试技术，2007，33(1):122-124.  
[4]魏连成.具有镜频抑制功能的混频电路设计[J].国外电子测量技术，2007，26(6):23-25.  
[5]胡澹，国云川，徐锐敏.Ka波段基波镜像抑制混频器无源电路的设计[J].微波学报，2010(S1):285-287.  
[6]刘文报，刘宇，杨自强，等.Ku波段Wilkinson功分器仿真与设计[J].应用科技,2014,41(2):35-37.