# 基于安全信任的网络切片部署策略研究

牛犇，游伟，汤红波(国家数字交换系统工程技术研究中心，郑州 450002)

摘要：5G移动通信网虚拟化场景下，如何安全部署网络切片是未来5G大规模商用的前提。针对5G网络切片部署的安全性，提出一种基于安全信任的网络切片部署策略。该部署策略通过提出安全信任值概念，来有效量化分析VNF和网络资源的安全性，并以此为基础，利用0-1整数线性规划方法构建网络切片部署的数学模型，利用启发式算法进行求解，找到网络切片部署成本最小的部署方案。仿真实验表明，该部署策略在保证部署安全的前提下，减少了部署成本，同时获得较好的安全收益和部署收益率。

关键词：5G；网络切片；安全信任；部署中图分类号：TN915.81 doi:10.3969/j.issn.1001-3695.2017.08.0728

# Research on network slicing deployment strategy based on security trust

Niu Ben, You Wei, Tang Hongbo (National Digital Switching System Engineering & Technological R&D Center, Zhengzhou 45o002, China)

Abstract:Inthe5Gmobilecommunicationnetworkvrtualizationscenario,howtodeploynetwork slicessafelyisaprerequisite forfuturelarge-scalecommercialuse.Aimingatthesecurityof5G network slicedeployment,this paper proposedastrategyfor network slicingdeploymentbasedonsecuritytrust.Thedeploymentstrategycouldeffectivelyquantifyandanalyzedthsecurity ofVNFandnetworkresources by proposing theconceptofsecuritytrustvalue,andonthisbasis,constructed the mathematical model fnetwork slicedeployment using O0-1integer inear programming method.The strategyused heuristic algorithmto find the minimumcost of network slice deployment.Simulationresults show thatthe deploymentstrategyreduces thedeployment cost and achieves better security revenue and deployment rate ofreturn under the premiseof ensuring the deployment security.

KeyWords:5G;network slicing; security trust;deployment

# 0 引言

随着物联网、车联网、工业控制以及垂直行业的兴起与发展，第五代移动通信（5G）技术将在多领域、多场景下满足用户定制化移动业务需求，实现"万物互联"的愿景[1]。5G网络切片作为5G网络的关键技术，是在虚拟化技术的基础上，将多个虚拟网络功能（virtual network function,VNF）进行动态裁剪、编排并部署，形成相互独立的虚拟网络，每个虚拟网络可根据用户需求提供定制化的网络服务[2]。在5G架构下，网络切片部署能够有效增强网络的灵活性和弹性，促进基础设施资源的高效利用，大幅降低资本支出和运营成本，同时满足用户定制化的安全和服务需求，实现按需组网。

未来5G网络将采用软件定义网络(software defined network,SDN)和网络功能虚拟化(networkfunctionvirtualization,NFV)技术，导致网络切片部署由于引进虚拟化技术而产生安全问题。在底层资源上部署网络切片时，可能存在一系列安全问题，例如受安全威胁的底层网络攻击虚拟网络（如嗅探攻击、恶意修改虚拟机信息等)，受攻击的虚拟机影响VNF正常运行(如DOS攻击等)，由于共享底层资源导致虚拟网络之间相互攻击（如跨虚拟机旁路攻击、侧信道攻击等）或者由于VNF软件中的安全漏洞而导致安全威胁等[3.4]。这些安全问题导致网络切片无法正常工作，破坏了网络切片的机密性和完整性；同时网络切片的安全性难以满足用户需求，阻碍了5G网络切片的大规模的部署和商用。因此，亟待新的安全机制和部署方法来满足网络切片部署的安全性。

网络切片部署难点主要是对切片中 VNF 进行部署，现有文献针对VNF部署问题，主要在互联网或演进分组核心网(evolvedpacketcore,EPC)等网络场景和架构下，根据不同优化目标设计VNF 部署策略，例如通过业务流量感知和节点分割算法对vEPC网络中池组化虚拟网络功能进行部署，可有效降低虚拟网络资源开销，提高网络接受率[5]；针对移动核心网网元（PGW、SGW、MME 等）形成的服务功能链(service functionchain,SFC)进行网元功能部署和网络拓扑优化[]；利用遗传算法对VNF进行动态部署，有效解决由于动态请求或请求变更而导致的VNF静态部署不适应的问题[7]；通过设计多种遗传算法，对链路最大利用率以及带宽消耗进行优化[8]；利用近似优化算法部署VNF[9]；利用整数线性规划和启发式算法对SFC 进行部署[10]；建立部署模型对SFC进行部署和评价[11]；针对SFC的大规模部署问题，将变邻域搜索和元启发式算法相结合，能够找到可行的设计方案[12]；针对运营成本设计一种弹性的VNF部署策略[13]。综上所述，目前VNF部署策略，主要以降低VNF部署成本，提高资源利用率和平衡网络拓扑负载等作为优化目标进行设计，针对VNF安全尤其是在5G网络架构下的VNF部署安全可参考的文献和方法较少，因此本文提出一种网络切片安全部署算法，以应对网络切片部署时的安全性需求。

针对上述网络切片安全部署方法的不足，本文利用0-1整数线性规划方法建立数学模型，以最小部署成本作为部署目标，提出一种基于安全信任的网络切片部署策略。在部署过程中利用安全信任值来有效量化分析VNF和网络资源的安全性，通过对VNF安全等级进行排序，实现在部署中将高安全等级的VNF 进行优先部署和重点保护。仿真实验表明，该部署策略通过考虑全局的资源和安全属性，所获得的部署方案在保证安全的前提下，在部署成本，安全收益和部署收益率等方面都获得良好的性能。

# 1 问题描述与数学模型

# 1.1安全部署问题描述

5G网络在SDN/NVF技术的基础上，网络功能与原有EPC架构中的网元功能相区分，网络功能细粒度化，提高了网络的灵活性；同时将原本价格昂贵的专属硬件设备以软件化形式迁移到通用的服务器上，大大降低了运维成本。经过SDN控制器统一编排后的网络切片，在对其进行部署后，能组成一套完整的虚拟网络为用户提供业务服务[14,15]。

对网络切片进行部署时，根据VNF和请求链路的需求，在底层通用资源上进行部署进而实现用户所需的网络服务[16]。图1为网络切片部署示意图。本文在不是一般性的前提下，为了简化求解的复杂度，有效屏蔽复杂的物理底层细节，将实际部署中通用的物理硬件设备资源和通用的分布式云平台虚拟网络资源统一抽象为图1模型中的网络资源。

![](images/93d35610be949665cb43381cb9dc02d4255cb2086986addffcde68fc018fb699.jpg)  
图1VNF 部署模型示意图

信任概念源于社会科学的人际关系网络，后被引入计算机科学中，信任安全作为网络安全中的"软安全"技术相较于传统安全技术（如加密技术、防火墙）具有更高的灵活性以及前瞻性[17]。为保证网络切片部署的安全性，本文提出安全信任值来量化网络资源和VNF的安全可信程度[18]。安全信任值在0\~1之间，值越大，表明越安全可信。网络资源在具有越安全的资源链接管理、越高水平的安全映射机制、越多的安全保护机制等安全条件下，其安全信任值就越高；VNF的安全信任值与其软件的编写水平相关（漏洞、后门出现的可能性越小，安全信任值就越高)。

图2为简化的VNF安全部署示例，左侧为VNF部署请求，$( x , y , z )$ 分别表示VNF的CPU 资源请求，VNF对网络资源的安全信任值需求，VNF自身的安全信任值；右侧为网络资源拓扑， $( x , y , z )$ 分别代表网络资源节点可提供的CPU资源能力，资源节点的安全信任需求和其相应的安全信任值。根据图3描述，对于一个网络切片的部署请求，其在网络资源拓扑上的部署方案为 $\{ \mathrm { V N F 1 } \to \mathrm { E }$ ${ \bf V N F } 2  { \bf B }$ ${ \bf V N F } 3  { \bf G }$ 】。

![](images/f9e9da3c00531e1cd22dc0ff34533353b657a0de9f2ab2cf90857f26142a69e8.jpg)  
图2VNF安全部署示例

为保证VNF部署的安全性，在部署时应满足以下安全约束条件：

a)网络资源节点的安全信任值不能低于部署在其上的VNF安全信任值需求，防止VNF部署在安全性较低的资源节点上；

b)VNF自身的安全信任值不能低于部属在其上的网络资源节点的安全信任需求，防止VNF可能携带的安全漏洞影响网络资源的安全性；

c)在已部署VNF的网络资源节点上部署新的VNF，新VNF自身的安全信任值不得低于已部署VNF的安全信任值，防止不安全的VNF利用共享的网络资源对其他VNF进行攻击；

d)对安全等级最高的VNF进行优先部署，同时不共享底层网络资源节点。

安全约束条件 $\mathbf { a } ) { \sim } \mathbf { c } ,$ 是保证VNF被安全的部署在底层网络资源的节点上，安全约束条件d)是保证安全等级高的VNF不受同驻攻击的影响，降低安全风险，实现对高安全等级VNF 的重点保护。

# 1.2数学模型

网络资源表示为一个由网络节点和节点间链路组成的无向图 $\boldsymbol { G } ^ { P } = ( N ^ { p } , E ^ { P } )$ ，其中 $N ^ { \dprime }$ 和 $E ^ { P }$ 分别代表网络资源中的节点和链路集合。对于网络资源节点 ${ n } _ { i } ^ { P } \in \boldsymbol { N } ^ { P }$ ，$n _ { i } ^ { P } = ( C _ { i } ^ { P } , M _ { i } ^ { P } , R _ { i } ^ { P } , S _ { i } ^ { P } )$ ， $\boldsymbol { C } _ { i } ^ { P }$ 、 $\boldsymbol { M } _ { i } ^ { P }$ 、 $R _ { i } ^ { P }$ 和 $S _ { i } ^ { \phantom { \dagger } }$ 分别表示底层资源节点 $n _ { i } ^ { P }$ 上的CPU资源能力值，存储能力值，资源节点的安全信任需求和资源节点的安全信任值； $e _ { i j } ^ { P } \left( e _ { i j } ^ { P } \in \boldsymbol { E } ^ { P } \right)$ 表示为网络资源节点 $n _ { i } ^ { P }$ 和 $n _ { j } ^ { P }$ 之间的网络资源链路， $e _ { i j } ^ { P } = ( S _ { i j } ^ { P } , B _ { i j } ^ { P } )$ 其中 $S _ { i j } ^ { P }$ 表示为网络资源链路 $e _ { i j } ^ { P }$ 的安全性， $S _ { i j } ^ { P }$ 由节点 $n _ { i } ^ { P }$ 到节点 $n _ { j } ^ { P }$ 之间经过节点的最低安全信任值所决定， $B _ { i j } ^ { P }$ 表示为网络资源链路$e _ { i j } ^ { P }$ 的所具有的带宽资源。 $H o p ( e _ { i j } ^ { P } )$ 表示网络资源链路 $e _ { l \nu } ^ { P }$ 经过节点的跳数

网络切片的部署请求拓扑图由无向图 $\boldsymbol { Q } ^ { V } = ( \boldsymbol { F } ^ { V } , \boldsymbol { E } ^ { V } )$ 来表示， $F ^ { V }$ 为所需部署的VNF集合， $E ^ { v }$ 为请求链路集合。对于一个 VNF $f _ { i } ^ { V } \in F ^ { V }$ ， $f _ { i } ^ { V } = ( C _ { i } ^ { V } , M _ { i } ^ { V } , R _ { i } ^ { V } , S _ { i } ^ { V } )$ ，其中 $C _ { i } ^ { V }$ 、 $\boldsymbol { M } _ { i } ^ { V }$ 、 $R _ { i } ^ { V }$ 和 $S _ { i } ^ { V }$ 分别表示 $\boldsymbol { f } _ { i } ^ { V }$ 的CPU资源需求值，存储资源需求值，VNF对网络资源的安全信任需求以及VNF自身的安全信任值；对于拓扑图中的虚拟网络请求链路 $e _ { s t } ^ { V } \big ( e _ { s t } ^ { V } \in E ^ { V }$ 表示 $\boldsymbol { f } _ { s } ^ { V }$ 和 $\boldsymbol { f } _ { t } ^ { V }$ 之间的虚拟网络链路， $e _ { s t } ^ { V } = ( B _ { s t } ^ { V } , R _ { s t } ^ { V } )$ 其中 $\boldsymbol { B } _ { s t } ^ { V }$ 表示链路 $e _ { s t } ^ { V }$ 的带宽资源需求， $R _ { s t } ^ { V }$ 表示链路 $e _ { s t } ^ { V }$ 所需要的安全信任值。 $f _ { i , j } ^ { V }$ 表示 $\boldsymbol { f } _ { i } ^ { V }$ 部署在底层网络资源节点 $n _ { j } ^ { P }$ 上， $e _ { s t , l \nu } ^ { V }$ 表示请求链路 $e _ { s t } ^ { V }$ 部署在底层网络资源链路 $e _ { l \nu } ^ { P }$ 上。

# 2 VNF安全等级研究

网络切片部署时，针对网络切片不同的应用场景，不同的用户需求，不同的业务范围和不同的风险因素，网络切片中的VNF应具有不同的安全等级。对高安全等级的VNF进行重点保护，可以有效提升网络切片整体的安全性；反之，攻击者对高安全等级的VNF进行攻击，会达到事半功倍的效果，体现出高安全等级VNF的脆弱性和易攻击性。因此针对VNF安全等级研究，对提高整个网络切片部署的安全性有着重要的作用。本章提出多种安全等级评价指标，通过TOPSIS分析法对VNF的安全等级进行合理排序。

# 2.1安全等级评价指标

指标1根据VNF类型。图3是3GPP提出的基于服务5G网络架构，通过SDN技术将控制与承载分离，使得组成网络切片的VNF可分为控制平面VNF和用户平面VNF。控制平面VNF负责会话管理、移动性管理、认证授权、协议管理等控制功能，用户平面VNF（UPF为用户平面功能集合）负责相对简单的路由转发功能。该评价指标计算时，将控制平面VNF安全等级指标设定为1，用户平面VNF安全等级指标设定为0。

指标2根据与VNF相连的所有邻接链路的通信量需求和。用 $T _ { i }$ 表示流经 $\boldsymbol { f } _ { i } ^ { V }$ 的通信量，如式(1)所示。

$$
T _ { i } = T _ { i } ^ { i n } + T _ { i } ^ { o u t }
$$

流量指标 $T _ { i }$ 由VNF流入和流出的通信量决定。不同场景和业务下的网络切片，不同VNF的通信量需求有所不同。例如在mMTC场景下，大量物联网设备接入切片，切片中具有认证功能的VNF 通信量需求较大；而在eMBB场景下，具有传输功能的VNF通信量需求较大；在自动驾驶的网络切片中，具有移动性管理功能的VNF，其数据通信量需求将会较大。由于5G开放性的特点，频繁进行信息流交互的VNF易受到有害流的威胁和攻击。

![](images/56725d1d16bca844093d8b849969d81b17fdbf98a0a281e22954631a346f1cd7.jpg)  
图3基于服务的5G网络架构

指标3根据VNF的度中心性。VNF的度中心性是指网络拓扑中一个VNF 与其他VNF直接相连接的数量。在$\boldsymbol { Q } ^ { \nu } = ( \boldsymbol { F } ^ { \nu } , \boldsymbol { E } ^ { \nu } )$ 中，设VNF 数量为 $\mathrm { \bf ~ g }$ 个， $\boldsymbol { f } _ { i } ^ { V }$ 的度中心性计算为

$$
C _ { D } ( f _ { i } ^ { V } ) = \sum _ { j = 1 } ^ { g } x _ { i j } ( i \neq j )
$$

其中: $\sum _ { j = 1 } ^ { g } x _ { i j }$ 表示为 $\boldsymbol { f } _ { i } ^ { V }$ 与其他 $g - 1$ 个 VNF 直接连接的数量[19]。由于用户不同的业务需求而使用不同的网络切片模板，导致网络切片内VNF的连接关系也有所不同，而VNF的度中心性能够直接反映网络切片内的VNF之间的连接关系。从受攻击后对整个网络的危害程度以及受攻击后恢复的难易程度上来说，度中心性越大的VNF，其受攻击后对网络的影响更大且恢复也更为困难复杂。

指标4 根据VNF 资源需求。 $\boldsymbol { f } _ { i } ^ { V }$ 的资源需求表示为

$$
R e ( f _ { i } ^ { V } ) { = } { \alpha } \cdot { C _ { i } ^ { V } } { + } { \beta } \cdot { M _ { i } ^ { V } }
$$

VNF的资源需求是自身的能力因子，同时资源需求越高，其部署就越困难，因此资源需求高的VNF更加的重要，需要设定较高的安全等级来进行优先部署。 $\alpha , \beta \ ( \alpha , \beta \in ( 0 , 1 ] , \alpha + \beta = 1 )$ 是为消除由于量纲不同而导致的数值差异而设定的参数

指标5 根据VNF的安全需求。VNF的安全需求越高，表示对承载VNF的网络资源节点的安全信任值要求也越高，应考虑对其优先部署，防止由于和低安全VNF 共享节点而可能导致的同驻攻击。

# 2.2安全等级排序

在对网络切片中VNF安全等级进行分析排序时，若仅依靠某个计算指标来判断VNF的安全等级较为片面，若考虑多个指标，由于上述五种安全等级计算指标是从不同角度出发进行计算，指标结果可能会出现不一致的情况。为了综合多个计算指标，本文利用TOPSIS分析法将多个VNF安全等级计算指标转换为多属性决策排序。

TOPSIS(technique for order preference by similarity to idealsolution)分析法是一种逼近理想解的排序方法。TOPSIS通过借助多属性问题中的理想解与负理想解，根据对评价对象的多个属性与理想目标的接近程度进行排序。TOPSIS排序方案的步骤如下：

步骤1建立安全等级决策矩阵 $\boldsymbol { X } _ { n \times m }$ ，如式(4)所示，假定网络切片中有 $n$ 个VNF,每个VNF有 $m$ 个安全等级评价指标，$x _ { i j }$ 表示第 $i$ 个VNF的 $j$ 个安全等级评价指标。

$$
X _ { n \times m } = { \left[ \begin{array} { l l l l l } { x _ { 1 1 } } & { \dots } & { x _ { 1 j } } & { \dots } & { x _ { 1 m } } \\ { \dots } & { } & { \dots } & { } & { \dots } \\ { x _ { i 1 } } & { \dots } & { x _ { i j } } & { \dots } & { x _ { i m } } \\ { \dots } & { } & { \dots } & { } & { \dots } \\ { x _ { n 1 } } & { \dots } & { x _ { n j } } & { \dots } & { x _ { n m } } \end{array} \right] }
$$

步骤2为消除量纲和量纲单位不同所带来的不可公度性，对决策矩阵进行规范化得到规范矩阵 $Z = \{ z _ { i j } \}$ ，其中$z _ { i j } = x _ { i j } / \sqrt { \sum _ { i = 1 } ^ { n } x _ { i j } ^ { 2 } }$ ；同时设定加权矩阵 $\omega = ( \omega _ { 1 } , \omega _ { 2 } , \dots , \omega _ { m } ) ^ { T }$ 且$\sum _ { j = 1 } ^ { m } \omega _ { j } = 1$ ，得到加权规范矩阵 $Y = \{ y _ { i j } \}$ ，其$y _ { i j } = z _ { i j } \cdot \omega _ { j } , i = 1 , 2 , . . . , n ; j = 1 , 2 , . . . , m _ { \mathrm { ~ o ~ } }$ （204号

步骤3对于加权规范矩阵确定属性的理想解 $\boldsymbol { y } ^ { * }$ 和负理想解 $y ^ { o }$ 。

对于第 $j$ 个属性的理想解为

$$
y _ { j } ^ { * } = \left\{ \begin{array} { l l } { \underset { i } { \operatorname* { m a x } } y _ { i j } } \\ { \underset { i } { \operatorname* { m i n } } y _ { i j } } \end{array} \right. { i = 1 , 2 , . . . , n , j = 1 , 2 , . . . , m }
$$

对于第 $j$ 个属性的负理想解为

$$
y _ { j } ^ { o } = \{ \begin{array} { l l } { \displaystyle \operatorname* { m a x } _ { i } y _ { i j } } \\ { \displaystyle \operatorname* { m i n } _ { i } y _ { i j } } \end{array} _ { i } = 1 , 2 , . . . , n , j = 1 , 2 , . . . , m
$$

步骤4计算各个安全等级评价指标与理想解和负理想解的欧氏距离。

对于第 $i$ 个VNF，其决策属性 $y _ { i j }$ 到理想解的欧氏距离 $\boldsymbol d _ { i } ^ { * }$ 为

$$
\mathcal { d } _ { i } ^ { * } = \sqrt { \sum _ { j = 1 } ^ { m } ( y _ { i j } - y _ { j } ^ { * } ) ^ { 2 } } , i = 1 , 2 , . . . , n
$$

对于第 $i$ 个VNF，其决策属性 $y _ { i j }$ 到负理想解的欧氏距离 $d _ { i } ^ { o }$ 为

$$
d _ { i } ^ { o } = \sqrt { \sum _ { j = 1 } ^ { m } ( y _ { i j } - y _ { j } ^ { o } ) ^ { 2 } } , i = 1 , 2 , . . . , n
$$

步骤5对各个VNF计算综合评价指数 $c ^ { * }$ ，第 $i$ 个VNF的综合评价指数 $\boldsymbol { C } _ { i } ^ { * }$ 为

$$
C _ { i } ^ { * } = \frac { d _ { i } ^ { o } } { d _ { i } ^ { * } + d _ { i } ^ { o } } , i = 1 , 2 , . . . , n
$$

步骤6对的综合评价指数 $\boldsymbol { C } _ { i } ^ { * }$ 的大小进行排序， $\boldsymbol { C } _ { i } ^ { * }$ 越大，说明该VNF的安全等级越高。

# 3 网络切片部署算法设计

# 3.1网络切片部署的数学模型

在对VNF部署方案进行分析评价时，主要以部署成本，安全收益和部署收益率作为部署方案的评价指标。

a)对于一个网络切片部署请求 $\varrho$ ，其部署成本定义如下：

$$
\begin{array} { r l } & { C o s t ( \boldsymbol { Q } ) = \displaystyle \sum _ { f _ { i } ^ { V } \in N ^ { V } } \displaystyle \sum _ { n _ { j } ^ { P } \in N ^ { P } } \rho ( f _ { i , j } ^ { V } ) \bullet S _ { j } ^ { P } \bullet ( \alpha \cdot C _ { i } ^ { V } + \beta \cdot M _ { i } ^ { V } ) + } \\ & { \qquad \quad \displaystyle \sum _ { e _ { s t } ^ { V } \in E ^ { V } } \displaystyle \sum _ { e _ { i \nu } ^ { P } \in E ^ { P } } \rho ( e _ { s t , l \nu } ^ { V } ) \bullet S _ { l \nu } ^ { P } \bullet B _ { s t } ^ { V } \bullet H o p ( e _ { l \nu } ^ { P } ) } \end{array}
$$

其中：二元数值 $\rho \in \{ 0 , 1 \}$ 作为决策变量来描述VNF和虚拟链路与底层网络资源之间的部署关系， $\scriptstyle \rho = 1$ 表示成功部署， $\scriptstyle \rho = 0$ 表示未部署成功。式(8)中第1项表示VNF 部署成本，当VNF 需要的CPU和存储资源越多，所部署的网络资源节点安全信任值越高，则VNF部署成本越高；第2项表示请求链路部署成本，当请求链路需要的带宽资源越多，部署的底层链路安全信任值越高，跳数越多，则请求链路部署成本越高。

b)对于一个网络切片部署请求 $\varrho$ ，其安全收益定义如下：

$$
\begin{array} { l } { { \displaystyle R e \nu e n u e ( Q ) = \sum _ { f _ { i } ^ { V } \in N ^ { V } } \sum _ { n _ { j } ^ { P } \in N ^ { P } } \rho ( f _ { i , j } ^ { V } ) { \bullet S _ { j } } { \bullet ( \alpha \cdot C _ { i } ^ { V } + \beta \cdot M _ { i } ^ { V } ) } } } \\ { { \displaystyle \qquad + \sum _ { e _ { s t } ^ { V } \in E ^ { V } } \sum _ { e _ { b } ^ { P } \in E ^ { P } } \rho ( e _ { s t , l \nu } ^ { V } ) { \bullet S _ { l \nu } ^ { P } } { \bullet B _ { s t } ^ { V } } } } \end{array}
$$

安全收益由部署占有的资源和整体的安全性所决定。由式(9)可知，网络切片部署时，所使用的底层网络资源越多，网络切片的整体安全性越高，安全收益也就越大。式(9)中第1项为VNF安全部署收益， $S _ { j }$ 表示承载VNF 的网络资源节点 $S _ { j } ^ { P }$ 的综合安全性，由VNF安全和底层网络资源安全两部分组成，若只有一个VNF 部署在 $S _ { j } ^ { P }$ 上， $S _ { j } = S _ { i } ^ { V } + S _ { j } ^ { P }$ ；若有 $\boldsymbol { r }$ 个VNF部署在 $S _ { j } ^ { P }$ 上， $S _ { j } = \operatorname* { m i n } \{ S _ { 1 } ^ { V } , . . . , S _ { r } ^ { V } \} / r + S _ { j } ^ { P }$ ，这是由于多个VNF 部署在一个节点使得VNF相互攻击的安全风险成倍增加。第2项为请求链路部署的安全收益，其与所部署的底层链路的安全信任值以及所需链路带宽有关。

c）对于一个网络切片部署请求 $\varrho$ ，其部署收益率定义如下：

$$
\lambda = \frac { R e \nu e n u e \left( Q \right) } { C o s t \left( Q \right) }
$$

部署收益率是对部署成本投入和安全收益产出的估算与衡量，由部署收益和部署成本所组成。由式(8)(9)可知，部署收益提高的同时会增大部署成本，在部署过程中，为追求部署效用的最大化，应尽可能控制部署成本并提高部署收益，而部署收益率越高，表明部署方案的效果越好。

# 3.2优化目标和约束条件

优化目标：

$$
\begin{array} { l } { \operatorname* { m i n } \displaystyle \sum _ { f _ { i } ^ { V } \in N ^ { V } } \displaystyle \sum _ { n _ { j } ^ { P } \in N ^ { P } } \rho ( f _ { i , j } ^ { V } ) \bullet S _ { j } ^ { P } \bullet ( \alpha \cdot C _ { i } ^ { V } + \beta \cdot M _ { i } ^ { V } ) + } \\ { \qquad \quad \displaystyle \sum _ { e _ { s t } ^ { V } \in E ^ { V } } \displaystyle \sum _ { e _ { i \nu } ^ { P } \in E ^ { P } } \rho ( e _ { s t , l \nu } ^ { V } ) \bullet S _ { l \nu } ^ { P } \bullet B _ { s t } ^ { V } \bullet H o p ( e _ { l \nu } ^ { P } ) } \end{array}
$$

约束条件：

对于 $\forall f _ { i } ^ { V } , f _ { k } ^ { V } , f _ { s } ^ { V } , f _ { t } ^ { V } \in F ^ { V } ~ , ~ \forall n _ { j } ^ { P } , n _ { l } ^ { P } , n _ { \nu } ^ { P } \in N ^ { P } ~ , ~ \forall e _ { \mathrm { s t } } ^ { V } \in E ^ { V } ~ ,$ $\forall e _ { l \nu } ^ { P } \in E ^ { P } \ , \quad \rho \in \{ 0 , 1 \}$ 有

$$
\left\{ \begin{array} { l l } { \rho ( f _ { i , j } ^ { V } ) \bullet R _ { i } ^ { V } \leq S _ { j } ^ { P } } \\ { \rho ( f _ { i , j } ^ { V } ) \bullet S _ { i } ^ { V } \geq R _ { i } ^ { P } } \\ { \rho ( f _ { i , j } ^ { V } ) \bullet S _ { i } ^ { V } \leq \rho ( f _ { k , j } ^ { V } ) \bullet S _ { k } ^ { V } , \ f _ { i } ^ { V } \ 种 \index { \sharp \sharp } } \end{array} \right.
$$

$$
\rho ( e _ { s t , l \nu } ^ { V } ) R _ { s t } ^ { V } \leq S _ { l \nu } ^ { P } \ ( S _ { l \nu } ^ { P } = \operatorname* { m i n } _ { \{ \mathrm { e } _ { l o } ^ { P } , . . . \mathrm { e } _ { r \nu } ^ { P } \} \in \mathrm { e } _ { l \nu } ^ { P } } \{ S _ { l } ^ { P } , . . . , S _ { \nu } ^ { P } \} )
$$

$$
\sum _ { u = 1 } ^ { \sigma } \rho ( f _ { u , j } ^ { V } ) { \bullet } C _ { u } ^ { V } \leq C _ { j } ^ { P }
$$

$$
\sum _ { u = 1 } ^ { \sigma } \rho ( f _ { u , j } ^ { V } ) { \bullet } M _ { u } ^ { V } \leq M _ { j } ^ { P }
$$

$$
\sum _ { u w = 1 } ^ { \sigma } \rho ( f _ { u w , l \nu } ^ { V } ) { \bullet B _ { u w } ^ { V } } \leq B _ { l \nu } ^ { P }
$$

$$
\sum _ { f _ { i } ^ { V } \in F ^ { V } } \rho ( f _ { i } ^ { V } ) = 1
$$

式(12)为上文提出的 VNF 部署时的安全约束条件 $\mathrm { \mathsf { a } } ) { \sim } \mathrm { \mathsf { c } } ,$ ，式(13)为链路部署的安全约束条件，式(14)\~(16)是部署时对底层网络资源的约束条件。当网络切片部署时，式(14)(15)表示部署在同一底层网络资源节点的VNF，其CPU和存储资源的需求和不能超过底层网络资源节点所能提供的资源能力，式(16)表示多条请求链路部署在同一条底层网络资源链路上，其带宽需求和不得超过底层网络带宽能力，式(17)表示一个VNF只能部署在一个底层网络资源节点上，不得拆分。

# 3.3算法描述

本文提出一种启发式的安全部署算法命名为NS-SD(network slice security deployment)，算法分为两个阶段：第1阶段对部署请求 $Q ^ { V }$ 中每个VNF的安全等级评价指标进行计算并利用TOPSIS分析法对其安全等级进行排序；第2阶段针对优化目标进行求解。由于网络切片的部署策略模型是一个NP难问题，在底层网络资源无向图中运行隐枚举算法进行求解[20-22]，获取安全部署方案。

NS-SD算法描述如下：

输入：网络切片部署请求无向图 $\boldsymbol { Q } ^ { \nu }$ ；底层网络资源无向图 $G ^ { \scriptscriptstyle P }$ 。  
输出：网络切片安全部署方案 $N S _ { s d }$ 。  
for 每一个 $\boldsymbol { f } ^ { V } \in { \boldsymbol { F } } ^ { V }$ do计算 $f ^ { V }$ 的安全等级评价指标  
end for  
对于 $\boldsymbol { n }$ 个VNF 建立安全等级决策矩阵 $X _ { n \times 5 }$ ，利用TOPSIS分析法对VNF  
的安全等级进行排序，排序结果存入链表SPList 中  
forSPList中的每一个VNF和请求链路do构建候选部署集合 $\Theta ( f ^ { V } )$ 以及 $\Theta ( e ^ { V } )$   
end for  
for $f _ { i } ^ { V } \in \Theta ( f ^ { V } )$ and $\boldsymbol { C } _ { i } ^ { * } \geq \forall \boldsymbol { C } _ { x } ^ { * } ( i \neq x )$ if $n _ { j } ^ { P }$ 未占用and $\rho ( f _ { i , j } ^ { V } ) = 1$ then$n _ { j } ^ { \dprime }$ 不再部署其他VNF and 部署结果放入 $N S _ { s d }$ else $\boldsymbol { f } _ { i } ^ { V }$ 部署失败  
end if  
end for  
for $\Theta ( f ^ { V } ) { = } \{ \Theta ( f ^ { V } ) \vert f _ { i } ^ { V } \notin \Theta ( f ^ { V } ) \}$ and $\Theta ( e ^ { V } )$ do隐枚举算法if 算法执行成功 then

对底层网络资源进行更新 and 部署结果放入 $N S _ { s d }$ else拒绝 $\Theta ( f ^ { V }$ ）and $\Theta ( e ^ { V } )$ （20

end if end for

算法(1)\~(4)为算法的第1阶段，对 $\boldsymbol { Q } ^ { \nu }$ 中VNF的安全等级进行排序；(5)-(7)为部署准备，生成节点和链路集合；(8)\~(20)为算法的第二阶段，其中(8)\~(13)对安全等级最高的VNF 进行优先部署，同时不共用底层节点， (14)\~(20)表示对其他节点和链路利用整数线性规划算法进行部署，如果算法执行成功将输出部署方案 $N S _ { s d }$ 否则将拒绝部署。

# 4 仿真实验与分析

为了评价部署模型的可行性和NS-SD算法的有效性，本文根据部署成本、安全收益和成本收益率等方面进行仿真实验，并与其他算法进行比较并分析结果。

# 4.1实验环境

针对底层网络资源拓扑图，为了保证拓扑图的随机性和不失一般性，本文利用机器学习中的K均值聚类算法生成无向图$\boldsymbol { G } ^ { \scriptscriptstyle P }$ ，共部署80个资源节点和相关链路[23]，如图3所示。

针对图4所生成的网络资源无向图，每个节点设置CPU能力 $C _ { x } ^ { P } \in [ 5 , 3 0 ]$ ，存储能力 $M _ { x } ^ { P } \in [ 1 0 , 1 0 0 ]$ ，安全信任值需求$R _ { x } ^ { P } \in ( 0 , 1 ]$ 和自身的安全信任值 $S _ { x } ^ { P } \in ( 0 , 1 ]$ 等多个属性，每条链路设置带宽能力属性 $B _ { x y } ^ { P } \in [ 1 , 2 0 ]$ 0

![](images/72c1f6ddef768076abf4f233ecbd32c01611e25e752f25658e20963bf5d7d8dd.jpg)  
图4网络资源拓扑图

根据 3GPP在 2017年最新提出的技术规范 $\mathrm { T S } 2 3 . 5 0 1 ^ { [ 2 4 ] }$ 提到的5G网络架构，设计生成一个包含15个VNF的网络切片部署请求拓扑图，如图5所示。生成的拓扑图中，每个VNF 随机设置CPU需求 $C _ { x } ^ { V } \in [ 5 , 1 0 ]$ ，存储需求 $M _ { x } ^ { V } \in [ 1 0 , 3 0 ]$ ，安全信任值需求 $R _ { x } ^ { V } \in ( 0 , 1 ]$ 和自身的安全信任值 $S _ { x } ^ { V } \in ( 0 , 1 ]$ 等多个属性：每条链路设置带宽需求属性 $B _ { x y } ^ { V } \in [ 1 , 1 0 ]$ ，设定 $\alpha { = } 0 . 7 , \beta { = } 0 . 3$ 。随机设置9个控制平面VNF，6个用户平面VNF，同时对每个VNF 随机设置一个流量指标 $T _ { i }$ ，TOPSIS分析法中设置加权矩阵 $\omega$ 的元素均为0.2。

![](images/f7536011e0280704c581a6e004b9df9a30235e42e5cc44df8db6e08da8d2e892.jpg)  
图5网络切片请求拓扑图

实验中，NS-SD算法与其他三种算法进行比较，Greedy 算法是在切片部署阶段，根据VNF和请求链路的资源需求而采用的一种贪心部署策略[25]；MST算法是基于最小生成树算法，通过考虑链路带宽资源需求和最小权重路径而采用的一种部署策略[26]；NNS-SD 是将 NS-SD 算法中的(8)\~(13)步省略后的一种简化算法，在未考虑部分安全约束条件下来比较部署方案的收益与成本。为了使结果便于比较，Greedy 和MST 算法在部署时加入新的安全部署约束。为避免随机性带来的影响，实验结果为多次实验后的平均值。

# 4.2 仿真结果分析

实验中以部署的成本，收益和收益率作为算法性能的评价指标，实验结果如下。

# 1）网络切片部署成本

图6为网络切片部署成本的变化情况。由图6可知,Greedy算法在部署一开始，依靠选取最优的底层网络资源节点进行部署，实现VNF部署成本最小，但由于所选取的部署节点位置导致部分链路跳数过多而增大链路部署成本。MST算法保证了链路部署成本最小，但VNF部署时由于选取部分底层网络资源节点的安全性过高而导致部署成本的增加。NS-SD算法由于优先对高安全等级的VNF和链路进行部署，导致一开始部署成本增长较快，但隐枚举算法既考虑了链路跳数又尽可能在全局搜寻合适的网络资源节点和链路进行部署（节点和链路的安全信任值不会过高)，随着VNF和请求链路部署的增加，使总的部署成本较低。NNS-SD 算法相比于NS-SD 算法，其部署成本更低，主要是由于未考虑部分安全约束，使得部分VNF可以与最高安全等级的VNF共享底层资源，导致部署时降低了部分链路部署成本，但NNS-SD算法使得高安全等级的VNF受到同驻攻击的安全风险增大。实验表明，利用NS-SD算法，能够有效降低网络切片部署成本同时提高整个网络切片部署的安全性。

# 2）网络切片部署收益

图7为网络切片部署收益的变化情况。由图7可知，NS-SD 算法由于考虑了节点和链路全局的拓扑属性，在安全约束的前提下，在全局选取最合理的节点和链路进行部署，获得的部署总收益最高。Greedy算法根据资源需求进行部署，对底层网络资源节点的安全性考虑较为局部，同时部署的节点和链路协调性较差，部署收益较低。MST 算法在部署一开始，根据其计算方法，使VNF能够部署在不同的网络资源节点上，尽可能减少VNF的网络资源节点共享情况，提高VNF的部署收益，但部署较为局部，全局考虑不足，导致整体的收益较低。NNS-SD 算法由于减少了安全约束条件，导致部分VNF资源共享，使部分VNF的安全部署收益相较于NS-SD算法较低。实验表明，NS-SD算法在考虑安全约束下，有效提高了网络切片的部署收益。

![](images/5d0bb90c4616492b4e13f73c73ceb06c814eeee5a4e27c867640dcc6d134b977.jpg)  
图6网络切片部署成本

![](images/8dba003bcece46a818f026221f7a72f5c6af58b503c2c9044d00336ca4ed80bb.jpg)  
图7网络切片安全收益

# 3）网络切片部署成本收益率

图8为网络切片部署成本收益率的变化情况。如图8所示，NS-SD和NNS-SD算法在部署一开始对高安全等级的VNF和请求链路进行部署，成本收益率较低，但部署过程中通过考虑全局的安全和资源属性，协调节点和链路部署，最终获得较好的部署成本收益率。Greedy和MST算法在部署中对节点和链路协调较差，同时部署考虑较为局部，虽然在部署开始时可以获得较好的成本收益率，但整体部署方案的成本收益率随着VNF和请求链路部署增加而降低。实验表明，NS-SD算法得到的部署方案，在保证安全性的前提下，通过分析底层网络资源的全局属性，协调节点和链路进行部署，有效提高整体的成本收益率。

# 5 结束语

5G网络切片由于采用虚拟化技术而引入了新的安全问题，本文主要研究了在虚拟化环境下的网络切片部署问题，针对现有网络切片部署方法的不足和网络切片高安全性需求，提出一种基于安全信任的网络切片部署策略，并通过仿真实验验证了部署模型的可行性和算法的有效性。该方法通过对VNF以及网络资源安全性的量化和对VNF安全等级的排序，实现对网络切片中高安全等级的VNF进行重点保护。仿真实验结果表明，本文提出的部署策略，在保证安全的前提下，能够选取合适的节点和链路进行网络切片的部署，有效降低部署成本，同时获得较好的安全收益和部署收益率。在后续研究中，针对网络切片商用运行过程中可能出现的安全问题进行研究，以保证网络切片的高安全性需求。

![](images/41f3fea982e7b2710f4193865c818fdbc57f93d955d5835da1d46d7ee33e6b9e.jpg)  
图8网络切片部署成本收益率

# 参考文献：

[1]China Mobile Communications Corporation. 5G service-guaranteed network slicing new white paper [EB/OL].(2017-03-01) [2017-05-20]. http://www.huawei.com/ch-en/news/ch/2016/5G.   
[2]陈山枝．发展5G的分析与建议[J]．电信科学,2016,32(7):1-10.   
[3]Fischer A,De Meer H.Position paper: secure virtual network embedding [J]. Praxis der Informationsverarbeitung und Kommunikation,2011,34 (4): 190-193.   
[4]Aljuhani A,Alharbi T.Virtualized network functions security attacks and vulnerabilities [C]//Proc of the 7th Annual Computing and Communication Workshop and Conference.2017:1-4.   
[5] 汤红波，袁泉，卢干强，等．一种支持节点分割的 VEPC 虚拟网络功能 部署模型[J]．电子与信息学报,2017,39(3):546-553.   
[6]Baumgartner A,Reddy VS,Bauschert T.Mobile core network virtualization: a model for combined virtual core network function placement and topology optimization [C]//Proc of IEEE Network Softwarization.2015:1-9.   
[7]Otokura M,Leibnitz K,Koizumi Y,et al.Application of evolutionary mechanism to dynamic Virtual Network Function Placement [Cl// Proc of IEEE Workshop Coolsdn.2016:1-6.   
[8]Cao J, Zhang Y,Wei A,et al. VNF-FG design and VNF placement for 5G mobile networks [J]. Science China Information Sciences,2017,60 (4): 040302.   
[9]Cohen R,Lewin-Eytan L,Naor JS,et al.Near optimal placement of virtual network functions [C]//Proc of IEEE Computer Communications,2015: 1346-1354.   
[10] Luizelli M C,Bays L R,Buriol L S,et al.Piecing together the NFV

provisioning puzzle:efficient placement and chaining of virtual network functions[C]//Proc of IFIP//IEEE International Symposium on Integrated INCIWUIK ivIaIageIIent.∠UIJ. y0-1UU.

[11] Moens H, Turck FD. VNF-P: a model for efficient placement of virtualized network functions[C]//Proc of IEEE International Conference on Network and Service Management. 2014: 418-423.   
[12] Luizelli M C, Cordeiro WL D C,Buriol L S,et al. A fix-and-optimize approach for efficient and large scale virtual network function placement and chaining [J]. Computer Communications,2016,10 (2): 67-77.   
[13] Ghaznavi M,Khan A,Shahriar N,et al. Elastic virtual network function placement [C]// Proc of the 4th International Conference on Cloud Networking.2015: 255-260.   
[14] Ravindran R, Chakraborti A,Amin S O,et al. 5G-ICN: delivering ICN services over 5G using network slicing [J]. IEEE Communications Magazine,2017,55 (5): 101-107.   
[15] Zhou X,Li R,Chen T,et al. Network slicing as a service: enabling enterprises'ownsoftware-definedcellularnetworks[J].IEEE Communications Magazine,2016,54(7): 146-153.   
[16] Nikaein N, Schiller E,Favraud R,et al. Network store: exploring slicing in future 5G networks [C]/ Proc of International Workshop on Mobility in the Evolving Internet Architecture. 2015: 8-13.   
[17]汪京培，孙斌，钮心忻，等．基于可信建模过程的信任模型评估算法 [J].清华大学学报：自然科学版,2013,53(12):1699-1707.   
[18]孟顺梅.云计算环境下可信服务组合及其关键技术研究[D]．南京：南 京大学,2016.   
[19] Stanley W, Katherine F. Social network analysis: methods and applications [M]. Beijing: China People's University Press,2012: 42-64.   
[20] Shao W,Hu W, Huang X.A new implicit enumeration method for linear 0- 1 programming[C]//Proc of IEEE International Workshop on Modeling, Simulation and Optimization. 20o8: 298-301.   
[21] Geoffrion A M.An improved implicit enumeration approach for integer programming [J]. Operations Research,1969,17 (3): 437-454.   
[22] Wang Jun,Li Duan.A new implicit enumeration method for polynomial 0 1 programming and applications [J]. System Engineering Theory and Practice,2007,27(3): 21-27.   
[23] Harrington P.Machine learning in action [M].Beijing: The People's Posts and Telecommunications Press,2013:15-31.   
[24] 3GPP.TR23.501,3rd generation partnership project; technical specification group services and system aspects; procedures for the 5G system; rel. 15 [EB/OL]. (2017-04)[2017-05-20]. htp://www.3gpp.org/ftp/Specs/latestdrafts/.   
[25]Yu M,Yi Y,Rexford J,et al.Rethinking virtual network embedding: substrate support for path splitting and migration [J].ACM Sigcomm Computer Communication Review,2008,38 (2): 17-29.   
[26]彭利民．基于最小代价的跨域虚拟网络映射算法[J].华南理工大学学 报：自然科学版,2015,43(9):67-73.