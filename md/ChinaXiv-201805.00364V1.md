# 软件定义天地一体化网络接入认证架构与方法

胡志言1,²，杜学绘1,²，曹利峰1,2

(1．信息工程大学，郑州 450001;2.数学工程与先进计算国家重点实验室，郑州 450001)

摘要：天地一体化网络因结构复杂存在网络异构动态、间歇连通、节点高度暴露等特性，为了保证安全，需要研究专有的接入认证架构与方法。首先利用软件定义网络控制面与数据面分离的思想将它与天地一体化信息网络相结合提出一种新的接入认证架构，对认证架构与过程进行详细描述，可以实现对网络的安全防护与资源的优化控制。然后根据架构特点，提出7个影响接入点决策的属性，给出各个属性的计算公式，将层次分析法与逼近理想解的排序方法相结合提出一种接入点决策算法，实验仿真结果表明接入点决策准确，可以实现资源的合理利用。

关键词：天地一体化网络；软件定义网络；接入认证架构；决策属性；决策算法 中图分类号：TN927 doi:10.3969/j.issn.1001-3695.2017.09.0944

# Oneaccess authentication architecture and method for software defined space-ground integration network

Hu Zhiyan1,², Du Xuehui1,², Cao Lifeng1, 2 (1.InformationEngineering Unversity,Zhengzhou450o1,China;2.StateKeyLaboratoryofathematicalEngineeringnd Advanced Computing,Zhengzhou 450001, China)

Abstract: Duetothecomplex structureofspace-ground integrationnetwork,ithascharacteristicsofheterogeneous,dnamic, intermitentconnectivityandhighexposure,itisnecessrytostudythespecialaccessauthenticatioarchitectureandmethodin orderto nsuresecurity.The softwaredefined network adopts the ideaofseparating control surface fromdata surface,so this paper proposedanew accessauthenticationarchitecture whichcombined software defined network and space-groundintegration network torealizeflexibility.Itconsistedofdetaileddescriptionofthe authenticationarchitectureand process,and itcould realizesecurityprotectionandresoucesoptimizationcontrol.Thenaccordingtothecharacteristicsofthearchitecture,thispaper putforward7atributesofinfluencingaccess pointdecision,andpresentedthecalculatingformulaofeachatribute.Inadition, an access point decision algorithm was proposed based on Analytic Hierarchy Procesand Technique for Order Preference by SimilaritytoanIdealSolution.Simulationexperimentsshowthatthealgorithmcanselecthebestaccesspointanditcanachieve reasonable utilization of resources.

Key Words:space-ground integrationnetwork;softwaredefinednetwork;acessauthenticationarchitecture;decisionatribute; decision algorithm

# 0 引言

随着卫星网络的不断发展，网络空间需求的不断拓宽，多种战略信息任务由陆地、海面等单一维度向海、空、天等多维度扩展，传统的网络难以满足日益多样的需求，因此要求地面网络与天基网络结合构成天地一体化信息网络来提供多样化服务。但天地一体化信息网络因其复杂的结构，存在网络异构动态、间歇连通、节点高度暴露等特性[1]，需要研究安全技术保障该网络的正常运行，而接入认证工作是保证安全的有效手段之一，因此构建高效灵活的天地一体化信息网络接入认证架构能

够为用户提供安全的服务。

自软件定义网络（SDN）概念提出以来，其应用迅速扩大电信运营商网络、数据中心和互联网公司业务部署等，但基于SDN的天地一体化信息网络的研究处于起始阶段。王[2提出一种软件定义卫星网络体系架构，该架构采用分层结构，每层均设置一个集中控制器，每层的集中控制器受控于一个控制中心。陈等人[3]提出一种聚合SDN的天地一体化信息网络，将网络分为天基、空基和地基三层，天基网络以传统方式通信，空基与地基均部署 SDN 控制器协调空地网络的资源分配，实现优化灵活管控。Iqbal等人[4]提出了一个基于SDN的空间网络架构，它使用空中节点轨道的知识来预测未来的网络事件，特别是链路中断，通过基于SDN的优化来主动减轻网络事件的影响。李等人[5提出在空间网络的关键节点部署基于SDN的多功能载荷平台，并将SDN 架构和空间时延容忍网络协议结合搭建天基信息网络，采用资源虚拟化的方法来实现天基信息网络按需定制和高效共享等要求。现有的基于SDN 的天地一体化信息网络的研究大多处于理论阶段，实际部署实现难度大，仿真实现少，且对于结合SDN的天地一体化网络接入认证的研究也较少，急需研究易于部署、优化管控、安全高效的基于SDN的天地一体化网络接入认证方法。

# 1 预备知识

# 1.1天地一体化信息网络

天地一体化网络[6，其组成如图1所示，采用天地双平面的结构，以地面网络为依托，以天基网络为拓展，由天基骨干网、天基接入网、地基节点网互联，并融合地面互联网和移动通信网组成。天基骨干网由布设在地球同步轨道的若干骨干节点联网而成，主要包括执行多种不同任务的卫星；天基接入网由布设在高轨或者低轨的若干节点组成；地基节点网由多个地基骨干节点互联而成，主要包括舰艇、汽车等。

![](images/f20cf6a9d47fdd8895c8c65792b074e1c8293b5943a812f58ca658593e782225.jpg)  
图1天地一体化网络组成

# 1.2 软件定义网络

SDN最初源自斯坦福大学的项目研究CleanSlate[7]，之后于2009年，Mckeown[8在INFOCOM大会上正式提出SDN概念。SDN[9架构如图2所示，其主要创新是利用分层的思想将控制平面与数据平面相分离，数据平面只负责数据的转发，控制平面的控制器利用可编程的软件平台去集中控制底层的设备硬件，因此可以获取网络状态的全局视图，根据该信息优化控制网络，实现对网络的灵活控制和资源的按需管理。控制平面与数据平面之间采用开放接口（如OpenFlow）下发流表规则，控制应用只需要关心自身逻辑，却不用关心底层的细节实现。SDN 目前已经应用在无线网络[10][1][12]、网络功能虚拟化[11][13]、数据中心和云计算[14]等多个行业和领域。

![](images/13efb07f0015732252713d61059deafdafdea4731159d2d43e13a2ded003709f.jpg)  
图2SDN架构

# 2 基于SDN的天地一体化信息网络接入认证架构

# 2.1设计目标

本文设计的天地一体化信息网络架构应该达到以下目标：

a）网络灵活可控制：传统的空间信息网络呈现“烟肉”式发展，网元设备的功能与硬件耦合，因此网络难以实现灵活控制。本文基于SDN 实现的天地一体化信息网络将控制与数据分离，控制器根据全局视图实现对基础设施的控制，达到灵活可控的效果。

b)网络融合可演进：天地一体化网络包括地面和空间等多种异构网络，异构网络之间难以实现互联互通。本文基于SDN实现的一体化网络，控制器可以获取实时的网络状态信息，合理调度资源，使得异构网络间实现融合。

c）网络服务可定制：传统的网络难以实现针对用户提供按需服务，本文基于SDN实现接入认证可以根据不同的用户需求，灵活的为用户提供匿名、并发等不同的认证服务，制定不同的策略，实现服务可定制。

# 2.2基于SDN的天地一体化信息网络接入认证架构

借鉴SDN中控制面和数据面分离的思想，简化或完全剥离网络基础设施层面的控制功能，设计天地一体化信息网络统一安全接入认证架构如图3所示，该架构分为三层，认证层、控制层和设备层。认证层主要包括统一接入认证管理中心，统一负责整个天地一体化信息网络的接入认证管理工作，其主要由三个模块构成：策略管理模块根据控制层收集反馈的网络状态信息及请求信息进行多种策略的制定，包括资源管理策略、路由策略、安全策略及接入点选择策略等；查询模块主要负责根据用户的请求信息进行接入认证有关工作的查询，包括链路状态、认证功能等；认证模块主要负责多种接入认证服务的选择，包括普通接入认证服务、匿名接入认证服务、并发接入认证服务以及广播接入认证服务等。控制层主要包含地面控制器和空间控制器，其中地面控制器包括可以完成用户接入认证相关控制操作的用户控制器和网关控制器，空间控制器主要为卫星控制器，负责收集空间中网络状态信息及卫星状态信息，包括网络带宽、传输时延、数据丢包率、信号强度、在线时间、卫星存储及计算能力等。设备层包含地面转发设备和空间转发设备，地面转发设备包括交换机、路由器及网关等，负责转发及处理地面的数据信息，包括用户的请求、卫星响应信息等，空间转发设备包括中轨及低轨卫星、飞行器等，负责在空间中转发相关信息，包括接入请求信息、响应信息等。设备层收集相关数据信息，通过控制层向认证层传递数据信息，认证层根据控制器收集的信息制定相关策略，通过控制层实现策略的下发与实施。

![](images/bbd77b37c88d51015a747ad03ba7ca292b499b8d66c8b4c4f3473741d3033dc1.jpg)  
图3基于软件定义的天地一体化信息网络统一认证架构

![](images/01f4c68c8d4c3e9a85e1c993446c0386b44e38991274ae66f7a3d547d676904c.jpg)  
图4天地一体化信息网络认证架构拓扑示意图

根据天地一体化信息网络组成特点以及本文设计的基于SDN的天地一体化信息网络接入认证架构，设计架构拓扑如图4所示，管理层的实体为管理中心，由于卫星有限的星上处理能力，为降低卫星的计算及存储压力，将管理中心部署在地面，便于部署与维护；控制层实体包括两部分，第一部分是部署在地面的用户控制器、网关控制器等地面控制器，具有两个作用，第一收集并维护本控制器域内的网络状态、设备实体及认证请求信息，将信息传递给管理中心；第二按照管理中心制定的策略控制信息的转发。第二部分是部署在太空中的卫星控制器，作用与地面控制类似，收集维护本控制器域内网络及卫星信息，并且按照管理中心下发的规则控制卫星转发信息。设备层实体主要包括地面上的交换机、路由器和网关等，以及空间中的骨干卫星及接入卫星等，主要作用为转发认证请求、响应信息及其他数据信息。三个层次的实体相互合作，共同完成天地一体化信息网络的接入认证工作。

利用SDN中控制面与设备面分离的思想，将SDN与天地一体化信息网络结合实现用户统一接入认证工作，控制器集中收集网络与实体状态信息并控制信息的转发，匿名、并发等多种接入认证及策略管理统一于管理中心进行集中管控，SDN的引入使天地一体化信息网络的使用与控制更加灵活，实现网络自动化部署，降低网络故障概率，更重要的是实现了网络的计算和存储资源的整合利用，为用户按需提供服务。

# 2.3基于SDN的天地一体化信息网络接入认证过程

根据本文提出的基于SDN的天地一体化信息网络三层架构及其拓扑结构，其接入认证方法的对象分为有线用户与无线用户，过程如下：

a)普通用户将接入请求信息发送给相关交换机，若交换机中存在相关转发流表，则按照流表规则转发，否则将此请求信息转发给对应控制器，控制器再将此信息发送给管理中心，如图4中路线 $\textcircled{1}$ 一 $\textcircled{2}$ 一 $\textcircled{3}$ 。

b)管理中心收到此接入请求，根据卫星控制器发送的空间网络状态信息以及卫星状态信息制定合适的路由策略、安全策略以及接入点选择策略等，将策略下发到相应的卫星控制器、用户控制器和网关控制器。

c)各个控制器将策略下发至对应的转发设备，用户的请求信息按照管理中心制定的策略将接入请求信息以指定的路线通过交换机、路由器到达网关，网关完成地面协议到空间协议转换后将信息发送到指定的接入卫星，目的卫星收到请求信息后，进行接入认证工作，如图4中路线 $\textcircled{1}$ 一 $\textcircled{4}$ 一 $\textcircled{5}$ $\textcircled { 5 } - \textcircled { 6 } - \textcircled { 7 } -$ $\textcircled{8}$ 。

d)卫星认证通过后返回响应信息，按照指定路线（如图4中路线 $\textcircled{8}$ 一 $\textcircled{7}$ 一 $\textcircled{9}$ 一 $\textcircled{10}$ 一 $\textcircled{5}$ 一 $\textcircled{4}$ 一 $\textcircled{1}$ ）经由网关完成空间协议地面协议的转换后，经过路由器和交换机传送至用户，用户收到信息完成认证工作。

无线终端用户可以直接与卫星进行通信或者与上述普通用户认证过程一样，但当无线终端用户请求接入的卫星不在范围内时，可以将请求发送至管理中心，控制卫星根据管理中心的策略将控制信息下发到各个转发卫星，将接入请求信息按照流表转发到目的接入卫星，实现接入认证过程。

# 3 接入点决策算法

在认证层的策略管理模块，接入点选择策略对于用户的接入认证过程是及其重要的。选择最优的接入点能够高效安全的满足用户的接入需求，实现用户的快速安全认证。

本文将层次分析法与逼近理想解的排序方法[15]相结合提出一种面向天地一体化信息网络的接入点决策算法，实现用户的接入点决策。其主要思想为：选择卫星节点的计算资源、存储资源、信号强度、带宽、传输时延、丢包率、覆盖时间作为接入点决策的评价属性，管理中心收到控制器传送的相关信息后，首先采用逻辑乘法与逻辑和法相结合筛选初步方案，删除不满足条件的方案，然后利用层次分析法确定各个属性的权重，接着利用基于逼近理想解的排序方法TOPSIS确定理想解与负理想解，计算各个候选接入节点与理想解、负理想解的距离，从而判断各个方案的优劣，选择出最优的接入节点。

# 3.1基于逻辑乘法与逻辑和法相结合的节点初步筛选

定义卫星节点 $S N _ { i }$ 的决策属性集{计算资源，存储资源，信号强度，带宽，传输时延，丢包率，覆盖时间}用$A S _ { i } = \{ C R _ { i } , S R _ { i } , S I _ { i } , N B _ { i } , T D _ { i } , P L _ { i } , C T _ { i } \}$ 表示，同时定义一个卫星节点成为接入节点各个属性的切除值分别为 $a , b , c , d , e , f , g$ ，根据各属性对决策结果影响的正负可将其分为效益型与成本型属性，效益型属性数值越大则其评价结果越高，包括计算资源、存储资源、信号强度、带宽、覆盖时间，成本型属性数值越低评价越高，包括传输时延和丢包率。当效益型属性值均不低于相应的切除值，成本型属性不高于相应的切除值时，将其对应的卫星节点加入到候选集合SN'中，否则再次进行判断筛选，为每个属性重新设定一个阈值 $a ^ { \prime } , b ^ { \prime } , c ^ { \prime } , d ^ { \prime } , e ^ { \prime } , f ^ { \prime } , g ^ { \prime }$ ，只要某一个节点的属性值比该阈值更优，则将该节点加入到候选集合SN'中。该算法如下：

Select $S N _ { i } \in S N$   
if $S N _ { i }$ satisfy   
$C R _ { i } \geq a$ and $S R _ { i } \geq b$ and $S I _ { i } \geq c N B _ { i } \geq d$ （204号   
and $T D _ { i } \leq e$ and $P L _ { i } \leq f$ and $C T \geq g$ （204   
add $S N _ { i }$ to SN'   
else if SN;satisfy   
$C R _ { i } \geq a$ or $S R _ { i } \geq b$ or $S I _ { i } \geq c$ 'or $N B _ { i } \geq d$ =   
or $T D _ { i } \leq e$ 'or $P L _ { i } \leq f$ 'or $C T \geq g$ 1   
add $\mathbf { \nabla } S N _ { i }$ to SN'

# 3.2基于层次分析法的属性权重确定

基于逻辑乘法与逻辑和法确定接入节点的初步方案集后，利用层次分析法确定各个接入节点的属性的权重。

a)构造决策矩阵。为了方便将接入节点的各个决策属性的重要性进行排序，根据Saaty[16提出的属性间相对重要性等级表，建立属性的决策矩阵如式1所示。

$$
\pmb { \mathscr { A } } = \left[ \begin{array} { c c c c c c c c c } { \mathscr { C } R / \mathscr { C } R } & { \mathscr { C R } / \mathscr { S } R } & { \mathscr { C R } / \mathscr { S } / } & { \mathscr { C R } / \mathscr { N } } & { \mathscr { C R } / \mathscr { T } } & { \mathscr { C R } / \mathscr { P } } & { \mathscr { C R } / \mathscr { \ C R } } & { \mathscr { C T } } \\ { \mathscr { S R } / \mathscr { C R } } & { \mathscr { S R } / \mathscr { S } R } & { \mathscr { S R } / \mathscr { S } / } & { \mathscr { S R } / \mathscr { N } } & { \mathscr { S R } / \mathscr { T } } & { \mathscr { S R } / \mathscr { P } _ { L } } & { \mathscr { S R } / \mathscr { C T } } \\ { \mathscr { S I } / \mathscr { C R } } & { \mathscr { S I } / \mathscr { S } \mathscr { S } / } & { \mathscr { S I } / \mathscr { S } / \mathscr { N } } & { \mathscr { S I } / \mathscr { T } } & { \mathscr { S I } / \mathscr { P } } & { \mathscr { S I } / \mathscr { C T } } \\ { \mathscr { M B } / \mathscr { C R } } & { \mathscr { N B } / \mathscr { S R } } & { \mathscr { N B } / \mathscr { S } / } & { \mathscr { N B } / \mathscr { N B } } & { \mathscr { N B } / \mathscr { T } } & { \mathscr { N B } / \mathscr { P } _ { L } } & { \mathscr { N B } / \mathscr { C T } } \\ { \mathscr { T D } / \mathscr { C R } } & { \mathscr { T D } / \mathscr { S R } } & { \mathscr { D } / \mathscr { S } / } & { \mathscr { T D } / \mathscr { N B } } & { \mathscr { T D } / \mathscr { T D } } & { \mathscr { D } / \mathscr { P } } & { \mathscr { T D } / \mathscr { D } } & { \mathscr { C T } } \\ { \mathscr { P L } / \mathscr { C R } } & { \mathscr { P L } / \mathscr { S R } } & { \mathscr { P L } / \mathscr { S } / } & { \mathscr { P L } / \mathscr { N B } } & { \mathscr { P L } / \mathscr { T D } } & { \mathscr { P L } / \mathscr { P } _ { L } } & { \mathscr { P L } / \mathscr { C T } } \\ { \mathscr { C T } / \mathscr { C R } } & { \mathscr { C T } / \mathscr { S R } } & { \mathscr { C T } / \mathscr { S I } } & { \mathscr { C T } / \mathscr { N B } } & { \mathscr { C T } / \mathscr { T D } } & { \mathscr { C T } / \mathscr { P L } } & { \mathscr { C T } } \end{array} \right] .
$$

b)检验属性决策矩阵的一致性。为了判断决策矩阵是否合理，需要引入相关参数进行一致性检验。因此将一致性比率 $C R$ 作为检验属性决策矩阵一致性的指标， $C R$ 为一致性指标 $C I$ 与同阶矩阵的随机指标 $R I$ 之比，如式(2)(3)所示。

$$
C R = C I / R I
$$

$$
C I { = } ( \lambda _ { \operatorname* { m a x } } - n ) / \left( n - 1 \right)
$$

$\lambda _ { \operatorname* { m a x } }$ 为决策矩阵 $A$ 的最大本征值， $\mathfrak { n }$ 为矩阵 $A$ 的阶数，RI的值由文献[15]给出。根据 $C R$ 的值可以用作判断矩阵 $A$ 是否合格，若 $C R < 0 . 1$ ，则可以认为矩阵 $A$ 中元素基本一致，可以通过检验；若 $C R > 0 . 1$ ,则认为矩阵 $A$ 中元素一致性较差，不能通过检验，需要调整矩阵中元素值直至其通过检验。或者可以由$C R = 0 . 1$ 和 $R I$ 的值计算得出 $\lambda _ { \operatorname* { m a x } } ^ { \prime } = 0 . 1 \cdot ( n - 1 ) \cdot R I + n$ ，若 $\lambda _ { \operatorname* { m a x } } > \lambda _ { \operatorname* { m a x } } ^ { \cdot }$ ，则需要调整矩阵元素值，否则认为矩阵 $A$ 通过一致性检验。

c)利用本征向量法求解各属性权重。当决策矩阵 $A$ 通过一致性检验后，利用式(4)可以求得矩阵 $A$ 的本征向量 $\omega$ ，即各个属性的权重。

$$
A \omega = \lambda _ { \operatorname* { m a x } } \omega
$$

# 3.3基于TOPSIS 法选择接入节点

利用层析分析法确定接入节点各个属性的权重后，利用逼近理想解的排序方法对接入的节点进行排序，选择最优的节点进行接入。

a)将决策矩阵进行向量规范化处理。利用式(5)将决策矩阵中各个元素规范化够得到新矩阵 $B = \left[ b _ { i j } \right]$ 。

$$
b _ { i j } = a _ { i j } \mathrm { ~ / ~ } \sqrt { \sum _ { i = 1 } ^ { n } a _ { i j } ^ { 2 } } , i = 1 , 2 , \cdots , m , j = 1 , 2 , \cdots , n
$$

b)将规范化矩阵 $B$ 进行加权处理，形成加权规范化矩阵 $C$ 。利用层次化分析法得到的各属性的权重向量 $\omega = ( \omega _ { 1 } , \omega _ { 2 } , \cdots , \omega _ { n } ) ^ { T }$ ，利用式(6)得到新矩阵 $C = \left[ c _ { i j } \right]$ 。

$$
c _ { i j } = \omega _ { j } \cdot b _ { i j } , i = 1 , 2 , \cdots m , j = 1 , 2 , \cdots n
$$

c)根据决策矩阵的基数信息确立理想解 $x ^ { + }$ 和负理想解 $x ^ { - }$ 。根据式(7)确立矩阵的理想解，根据式(8)确立矩阵的负理想解。

$$
x _ { j } ^ { + } = \left\{ \begin{array} { l l } { \operatorname* { m a x } { c _ { i j } } , j = C R , S R , S I , N B , C T } \\ { \operatorname* { m i n } { c _ { i j } } , j = T D , P L } \end{array} \right.
$$

$$
\bar { x _ { j } ^ { - } } = \left\{ \begin{array} { l l } { \operatorname* { m a x } { c _ { i j } } , j = T D , P L } \\ { \operatorname* { m i n } { c _ { i j } } , j = C R , S R , S I , N B , C T } \end{array} \right.
$$

d)计算各个可选接入节点与理想解、负理想解的距离。接入节点与理想解的距离如式(9)所示，与负理想解的距离如式(10)所示。

$$
d _ { i } ^ { + } = \sqrt { \sum _ { j = 1 } ^ { n } ( c _ { i j } - x _ { j } ^ { + } ) ^ { 2 } } , i = 1 , 2 , \cdots m
$$

$$
\bar { d } _ { i } ^ { - } = \sqrt { \sum _ { j = 1 } ^ { n } ( c _ { i j } - x _ { j } ^ { - } ) ^ { 2 } } , i = 1 , 2 , \cdots m
$$

e)根据距离计算综合评价参数 $E I$ ，利用 $E I$ 进行接入节点排序。 $E I$ 的计算如式(11)所示， $E I$ 越大则表示其综合性能更优，更适于用户接入。

$$
E I _ { i } = d _ { i } ^ { - } / ( d _ { i } ^ { + } + d _ { i } ^ { - } ) , i = 1 , 2 , \cdots m
$$

# 3.4接入点选择切换流程

用户首次接入天地一体化信息网络时，接入信息通过交换机和控制器被发送至管理中心，管理中心利用收集到的各个卫星与网络的状态信息，运行本文提出的接入点选择算法，制定策略，并将相关策略下发至用户卫星，用户选择最优的接入点进行后续认证工作。当接入点发生变化时，请求信息重新经控制器发送至管理中心，其获取最新实时的网络状态信息后，重新制定策略并下发，具体过程如图5所示。

![](images/51f9d8905de128c5f779233f61ff773aa2f11328443717da5805e294e678d8ff.jpg)  
图5接入点选择切换流程

# 4 实验仿真

# 4.1接入节点决策属性数值计算方法

在进行实验仿真前需要获取实验数据，每个属性数值的获取需要根据相应的计算方法获取。利用OPNET仿真软件获得接入节点的属性信息，每个属性采取以下计算方法获得。

计算资源一般体现在内存、CPU等方面，剩余内存越多，访存速度越快，CPU的主频和字长越大，缓存越大，CPU空闲率越低，则计算资源越充足，因此其计算方法如式（12）所示。其中 $M$ 表示剩余内存， $\mathbf { \nabla } S _ { M }$ 表示访存速度，fcPu表示CPU的主频，WS 表示字长， $C _ { c P U }$ 表示CPU的缓存， $U _ { C P U }$ 表示CPU利用率。

$$
C R = M \bullet S _ { M } \bullet f _ { C P U } \bullet W S \bullet C _ { C P U } / U _ { C P U }
$$

存储资源一般体现在磁盘读写速度、剩余存储空间、磁盘缓存、硬盘转速、平均访问时间及队列长度，可以采用式（13)来体现，其中 $D i s k _ { r w s }$ 表示磁盘读写速度， $S s$ 表示剩余存储空间，$D _ { c a c h e }$ 表示磁盘缓存， $D _ { s }$ 表示磁盘转速， $D _ { u t }$ 表示平均访问时间，$\varrho _ { s }$ 表示磁盘队列长度。

$$
S R = D i s k _ { r w s } \bullet S s \bullet D _ { s } \bullet D _ { c a c h e } / Q s \bullet D _ { a t } 
$$

信号强度由于会随着环境干扰而变化，可以通过式（14)来反映一段时间内的信号强度值，其中 $S I _ { o l d }$ 为上一次控制器获

得的信号强度， $S I _ { n e w }$ 为当前获得的信号强度。

$$
S I = 0 . 2 \times S I _ { o l d } + 0 . 8 \times S I _ { n e w }
$$

带宽可以用一段时间的带宽空闲率来表示，如式（15）所示，其中 $B _ { \mathrm { m a x } }$ 表示最大带宽， $B _ { u s e }$ 表示已使用带宽，t表示时间间隔。

$$
N B = ( B _ { \operatorname* { m a x } } - B _ { u s e } ) / t \bullet B _ { \operatorname* { m a x } }
$$

传输时延可以利用式（16)计算得到，其中 $s$ 表示用户与接入节点间距离， $\nu$ 表示电磁波传输速度。

$$
T D = \%
$$

丢包率的计算方法如式（17）所示， $P _ { i n }$ 与 $P _ { o u t }$ 分别表示输入数据与输出数据，其意义是丢失的数据包占发送数据包的比率。

$$
P L = \left( P _ { i n } - P _ { o u t } \right) / { P _ { i n } }
$$

覆盖时间可以利用接入节点和用户的位置矢量信息计算卫星与用户间的夹角 $\varphi$ ，则可见函数为 $\phi = \varphi - 9 0 - \alpha$ ，其中 $\alpha$ 为用户对接入节点的仰角要求，当 $\phi$ 为正时用户与接入节点可通信，根据此可计算出最大通信角度，再利用接入节点运动速度与方向信息可计算出覆盖时间。

# 4.2基于SDN 的天地一体化信息网络接入点选择算法实验

根据4.1节计算方法得到各个节点的属性值，并根据4.1节初步筛选算法过滤掉不符合条件的接入节点集合。由于各个指标的意义不同，其数值差异较大，为了直观方便的进行接入点决策，利用TOPSIS 法将决策矩阵进行向量规范化处理，获得候选接入节点集合各个属性数值如表1所示。

表1候选接入节点属性值表  

<html><body><table><tr><td>名称 计算资源</td><td>存储资源</td><td>信号强度</td><td>带宽</td><td>传输时延</td><td>丢包率</td><td>覆盖时间</td></tr><tr><td>N1 0.2704</td><td>0.2938</td><td>0.5671</td><td>0.4883</td><td>0.1330</td><td>0.4059</td><td>0.4109</td></tr><tr><td>N2 0.3709</td><td>0.1959</td><td>0.4253</td><td>0.3255</td><td>0.5987</td><td>0.2647</td><td>0.4402</td></tr><tr><td>N3 0.3863</td><td>0.5509</td><td>0.2127</td><td>0.5697</td><td>0.5322</td><td>0.5647</td><td>0.4304</td></tr><tr><td>N4 0.4945</td><td>0.5631</td><td>0.3544</td><td>0.2441</td><td>0.2661</td><td>0.4412</td><td>0.3717</td></tr><tr><td>N5 0.4250</td><td>0.3183</td><td>0.4962</td><td>0.3255</td><td>0.3326</td><td>0.3882</td><td>0.4011</td></tr><tr><td>N6 0.4636</td><td>0.3917</td><td>0.2836</td><td>0.4069</td><td>0.3991</td><td>0.3177</td><td>0.3913</td></tr></table></body></html>

根据层次分析法构造决策矩阵如式（18）所示，利用MATLAB 计算出该矩阵的最大本征值 $\lambda _ { \mathrm { m a x } } { = } 7 . 1 8 2 5$ ，从而计算出一致性比率 $C R = 0 . 0 2 3 < 0 . 1$ ，通过一致性检验。利用本征向量法求解各属性权重 $\boldsymbol { \omega } = [ \ 0 . 2 4 8 3 , 0 . 0 6 8 6 , 0 . 1 7 4 0 , 0 . 0 4 2 7 , 0 . 1 3 5 1 , 0 . 0 8 3 1 , 0 . 2 4 8 3 ] ^ { T }$ u

$$
A = { \left[ \begin{array} { l l l l l l l } { 1 } & { 3 } & { 2 } & { 5 } & { 2 } & { 3 } & { 1 } \\ { 1 / 3 } & { 1 } & { 1 / 2 } & { 2 } & { 1 / 3 } & { 1 / 2 } & { 1 / 3 } \\ { 1 / 2 } & { 2 } & { 1 } & { 4 } & { 2 } & { 3 } & { 1 / 2 } \\ { 1 / 5 } & { 1 / 2 } & { 1 / 4 } & { 1 / 3 } & { 1 / 2 } & { 1 / 5 } \\ { 1 / 2 } & { 3 } & { 1 / 2 } & { 3 } & { 1 } & { 2 } & { 1 / 2 } \\ { 1 / 3 } & { 2 } & { 1 / 3 } & { 2 } & { 1 / 2 } & { 1 } & { 1 / 3 } \\ { 1 } & { 3 } & { 2 } & { 5 } & { 2 } & { 3 } & { 1 } \end{array} \right] }
$$

根据表1以及层次分析法得到的各属性权重，对数据进行 加权处理，形成加权规范化矩阵C如式（19）所示。然后，根 据矩阵 $C$ 计算地出理想解 x =(0.1228,0.0386,0.0987,0.0243,0.0180,0.0220,0.1093）和负 理想解 x =(0.0671,0.0134,0.0370,0.0104,0.0809,0.0469,0.0923）。

[0.0671 0.0202 0.0987 0.0209 0.0180 0.0337 0.1020]   
0.0921 0.0134 0.0740 0.0139 0.0809 0.0220 0.1093   
0.0959 0.0378 0.0370 0.0243 0.0719 0.0469 0.1069   
0.1228 0.0386 0.0617 0.0104 0.0360 0.0367 0.0923   
0.1055 0.0218 0.0863 0.0139 0.0449 0.0323 0.0996   
0.1151 0.0269 0.0493 0.0174 0.0539 0.0264 0.0972

计算各个可选接入节点与理想解的距离 $d ^ { + }$ 、负理想解的距离 $d ^ { - }$ ，根据距离计算综合评价参数EI，得到各项数值如表2所示，利用 $E I$ 可以得出接入节点排序为 $N _ { 5 } \succ N _ { 4 } \succ N _ { 1 } \succ N _ { 6 } \succ N _ { 2 } \succ N _ { 3 }$ ，可以看出节点 $N _ { 5 }$ 的综合评价指标最高，由此可以选择 $N _ { 5 }$ 节点进行接入。

表2接入节点与理想解距离及综合评价参数值  

<html><body><table><tr><td>名称</td><td>d+</td><td>d-</td><td>EI</td></tr><tr><td>N1</td><td>0.0603</td><td>0.0905</td><td>0.6000</td></tr><tr><td>N2</td><td>0.0791</td><td>0.0540</td><td>0.4056</td></tr><tr><td>N3</td><td>0.0898</td><td>0.0437</td><td>0.3272</td></tr><tr><td>N4</td><td>0.0489</td><td>0.0804</td><td>0.6218</td></tr><tr><td>N5</td><td>0.0420</td><td>0.0745</td><td>0.6395</td></tr><tr><td>N6</td><td>0.0643</td><td>0.0621</td><td>0.4912</td></tr></table></body></html>

# 5 结束语

本文基于软件定义提出了一种天地一体化信息网络接入认证架构与方法。首先介绍了天地一体化信息网络的基本组成和架构，然后在其基础上结合SDN提出一种新的接入认证架构，并详细介绍其接入认证的过程。接着，根据软件定义天地一体化信息网络的特性，将层次分析法与逼近理想解的排序方法相结合提出一种接入点选择算法，仿真实现后证明其效果良好，能够满足天地一体化网络接入认证的需求。在下一步工作中，可以将本文提出的基于软件定义的天地一体化网络接入认证架构与方法真正仿真部署实现。

# 参考文献：

[1]李凤华，殷丽华，吴巍，等．天地一体化信息网络安全保障技术研究进展及发展趋势[J].通信学报,2016,37(11):156-168.

[2]王春锋.软件定义可重构卫星网络系统研究[J].中国电子科学研究院 学报,2015,10(5):455-459.   
[3] 陈晨，谢珊珊，张潇潇，等．聚合SDN控制的新一代空天地一体化网络 架构[J].中国电子科学研究院学报,2015,10(5):450-454.   
[4]Iqbal H,Ma J, Stranc K,etal.A software-defined networking architecture for aerial network optimization [C/ Proc of IEEE Netsoft Conference and Workshops.2016: 151-155.   
[5]李婷，胡建平，徐会忠．天基信息网络的软件定义网络应用探析[J]. 电讯技术,2016,56(3):259-266.   
[6] 吴曼青，吴巍，周彬，等．天地一体化信息网络总体架构设想[J].卫 星与网络,2016,2016(3):30-36.   
[7]Stanford University. Clean slate program [EB/OL]. (2017-05-25)[2017-10- 09]. https://en. wikipedia.org/wiki/Clean_Slate_Program.   
[8]MCKEOWNN.Software-defined Networking[J].0 中国通信：英文版, 2009,11 (2): 1-2.   
[9]王蒙蒙，刘建伟，陈杰，等．软件定义网络：安全模型、机制及研究进展 [J]．软件学报,2016,27(4):969-992.   
[10] Wang K,Wang Y, Zeng D,et al.An SDN-based architecture for nextgeneration wireless networks [J].IEEE Wireless Communications,2017,24 (1): 25-31.   
[11] Costa-Perez X, Garcia-Saavedra A,LiX, et al.5G-crosshaul: an SDN//NFV integrated Fronthaul//Backhaul transport network architecture [J].IEEE Wireless Communications,2017,24 (1): 38-45.   
[12] Rahman M M, Despins C,Affes S.Design optimization of wireless access virtualization based on cost & QoS trade-offutility maximization [J]. IEEE Trans on Wireless Communications,2016,15 (9): 6146-6162.   
[13] Callegati F, Cerroni W,Contoli C,et al. SDN for dynamic NFV deployment [J]. IEEE Communications Magazine,2016,54 (10): 89-95.   
[14]ADAMID,MARTINIB,SGAMBELLIRI A, etal.An SDN orchestrator for cloud data center:System design and experimental evaluation [J]. Transactions on Emerging Telecommunications Technologies,2017,2017 (11): e3172.   
[15]岳超源．决策理论与方法[M].北京：科学出版社,2003.   
[16]闫冲冲，郝永生．基于层次分析法(AHP)的空中目标威胁度估计[J]. 计算技术与自动化,2011,30(2):118-121.