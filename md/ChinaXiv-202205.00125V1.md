# 面向软件定义网络的可变粒度数字孪生构建技术

陈何雄」，吴佳平2,，韦云凯2,3，郭威¹，杭菲璐1，毛正雄」，杨宁(1.云南电网有限责任公司信息中心，昆明 65000;2.电子科技大学 长三角研究院(衢州)，衢州 324000;3．电子科技大学 信息与通信工程学院，成都 611731)

摘要：软件定义网络(software defined network，SDN)应用范围的扩大带来了应用需求多样化的挑战。利用数字孪生(digitaltwin，DT)增强 SDN的实时分析、推演和控制能力，能更好地满足各种应用场景需求。然而，当前 SDN的数字孪生构建面临着时延需求高、计算开销大、资源协调难的问题。因此，以应用需求为导向，在网络可用计算资源约束下，提出了一种新型的可变粒度数字孪生(variable granularity digital twin，VGDT)思想及其构建技术。VGDT结合网络可用计算资源分布特征，建立了保证数字孪生时延和完整度的多节点资源协同优化模型。在此基础上，利用混合编码遗传算法对该模型进行求解，获得最佳映射数据粒度和数字孪生部署方案，指导数字孪生的构建过程。仿真结果表明，与现有模式相比，在网络计算资源约束下，VGDT 具有更高的数字孪生模型完整度和模型有效性。关键词：软件定义网络；数字孪生；可变粒度；遗传算法；应用驱动  
中图分类号：TP393.0doi:10.19734/j.issn.1001-3695.2022.02.0106

Variable granularity digital twin construction technology for software defined network

Chen Hexiong1, Wu Jiaping2,3, Wei Yunkai2,3t, Guo Weil, Hang Feilu1, Mao Zhengxiong1, Yang Ning³ (1.InformationCenterofYunnanPowerGridCo.Ltd.,Kunming65oo,China;2.YangtzeDeltaRegionInstitute(Quzhou), UniversityofElectronicScience&TechnologyofChina,Quzhou3240o0,China;3.Schoolof Information&Communication Engineering, University of Electronic Science& Technology of China, Chengdu 611731, China)

Abstract: As Software Defined Network (SDN) is increasingly widelyused invarious scenarios,anew challenge for SDN to support dynamicrequirementsofvarious applications begin to emerge.DigitalTwin(DT)can enhance thecapabilitiesof SDN inaspectsofreal-time analysis,deduction,and network control,andconsequentlysatisfythednamicequirementsof various applications.Whereas,current DTconstructing schemes for SDN usuallysuffer from the challenges of strict delay constraint,heavycomputingoveread,andlowooperatingefciencyToadresstheaboveisse,tispaperproposesanovel Variable Granularity-DigitalTwin(VGDT)according totheapplication requirementandavailablecomputing resource.Based on the distribution characteristicof thecomputing resource in the network,VGDTbuilds acooperativelyoptimizing model to ensurethe delayand efectivenessoftheDTforSDN.Then,thispaperproposesahybridcoding genetic algorithmto solve this model,whichcanachieve thebest granularityandthe DTplacement policy.Thesimulationresults showthe performance ofVGDT.Compared with currnt DT, VGDThas higher integrityand validityof digital twin model under limitedcomputing resource.

Key Words: SDN; digital twin; variable granularity; genetic algorithm; application driven

# 0 引言

随着信息通信技术的发展，软件定义网络(softwaredefinednetwork,SDN)的应用领域变得越来越广泛，出现了如基于SDN的信息化工厂[I]、电力网络[2]和数字医疗[3]等各种新型应用场景。这些日益丰富的应用场景对SDN的需求也越来越多样化和复杂化，需要SDN更加有效地组织、管理和调度网络中的资源，以满足各种应用场景的动态需求[4]。数字孪生(digitaltwin,DT)技术恰好为高效满足这种需求提供了可能性。DT通过构建物理实体的实时数字镜像，可对物理实体进行监视、模拟和控制，制造业、医疗业和智慧城市等领域正对其进行广泛的研究应用[5]。DT 赋能的SDN 能够增强感知、分析和控制网络的能力，从而更加有效地组织、管理和调度网络资源，以满足各种应用场景中的动态需求。面向SDN 的DT构建是完成这种需求的前提和基础，也是当前的研究热点。

目前，面向SDN的DT构建方式可以分为两类：独立式构建与融入式构建。独立式构建方案将DT构建在完全独立的设施(服务器或网络)上，比如Zhao等人[6提出在集中的服务器或控制器上构建软件定义车联网(softwaredefined-vehicularnetwork,SDVN)的DT，Krishnan等人[7]在中央服务器上独立构建软件定义物联网(softwaredefined-internet ofthings,SD-IoT)的DT。独立式构建方案中，构建DT的设施与转发平面之间存在极大的通信开销，这将会加重DT和网络交互的通信时延；并且在DT分析SDN时，该设施要同时处理全网的数据，存在较重的计算负担，以及需要增加网络基础设施开销。因此，对时延具有严格要求的DT而言[8,9],这种构建方式的效果往往不够理想，且存在沉重的通信与计算等成本。在融入式构建方案中，主要利用SDN中的现有设施(如边缘服务器等)，协同构建该物理网络的DT，即将DT的构建融入到目标物理网络中。Khan 等人[10]提出了一种基于DT的6G网络架构，对比了基于云的独立式DT构建方案和基于边缘的DT构建方式的区别，其中后者具有更低的通信延迟以及更高的可伸缩性。Xu等人[通过在多个RSU(roadsideunit)上建立各个车辆的数字孪生体，实现了车联网边缘计算与数字孪生的结合；Zhang等人[12]在边缘服务器上构建了车辆边缘计算网络(vehicular edge computingnetworks,VECN)中各车辆的数字孪生体。在融入式构建方案中，由于边缘服务器分布在物理网络中，与物理网络设备的通信距离更短，能降低DT的通信时延；此外，在多个边缘服务器的协同下，DT的计算负担由各个边缘服务器负担，能够提高计算效率。在对数字孪生的构建时延和构建完整度等具有严格要求时，往往更加倾向采用这种方式。

但是，在现有的融入式DT构建方式中，通常是以建立物理网络的完全映射为目标，即在虚拟空间中建立的DT与物理网络尽量达到百分百的相同。但是，这种完全映射的构建方式往往带来较大的资源开销和系统压力。Lopez 等人[13]将DT用于对智能电网中的数据进行上下文感知和行为模拟时，也指出这种方式需要极大的通信与计算资源。实际上，在具体的应用场景及其需求特征下，并不一定需要完全映射的数字孪生。Yang等人[4]提出了一种基于DT的网络流量仿真框架，并通过流量采样的方式减少网络向DT传输的数据量，进而提高流量预测效率。这种方式在一定程度上减轻了DT 构建的压力，但是其应用模式相对固定、单一。

针对当前构建DT面临的问题，本文提出了一种可变粒度数字孪生(variable granularity-digital twin,VGDT)思想及其构建技术，在网络可用计算资源有限情况下，根据应用特征调整映射粒度，尽力提高DT模型的有效性，满足应用需求。本文主要贡献如下：

1）提出了一种面向SDN的可变粒度数字孪生思想及其构建架构，通过充分利用网络中的可用计算资源，构建出满足应用需求的数字孪生。2）建立了可变粒度数字孪生有效性优化模型，通过调整构建DT的映射粒度与数字孪生体布局，保障数字孪生的模型构建时延、完整度与有效性，提供满足应用需求的DT。3）通过仿真对VGDT的有效性进行了验证，结果表明在计算资源受限情况下，VGDT具有更高的数字孪生模型完整度和模型有效性，能更好地满足应用需求。

# 1 相关基础

本节简要介绍软件定义网络、数字孪生技术，为后续可变粒度数字孪生架构与技术的提出提供基础。

# 1.1软件定义网络

SDN作为近年来备受关注的一种新型网络架构，通过对网络进行可编程管理，能更灵活地部署网络功能，提高了网络的应用性能和管理效率。2016年，开放网络架构基金会发布的软件定义网络白皮书中，规定了SDN由应用平面、控制平面和数据平面组成。其中，控制平面通过北向接口向上连接网络应用平面、南向接口向下连接数据平面，实现根据应用平面的需求对网络进行可编程管理和利用全网数据统一控制数据平面的数据转发，进而使SDN可以根据应用需求对网络进行可编程管理，提高SDN的应用性能[15]。

SDN通过实时收集全网数据，为控制器制定网络管理策略、部署网络功能奠定了丰富多样的数据基础；并且，SDN通过分析、利用全网数据对网络进行集中控制，有利于SDN从全局角度管理、优化网络。但是，随着SDN应用场景的多样化和规模扩大，网络数据规模也逐渐提高，对控制平面充分收集、处理和利用网络数据的能力也提出了较高要求。

# 1.2数字孪生

数字孪生的概念最早出现在2003年，Grieves将其引入产品生命周期管理课程中；在2012年，美国空军研究实验室和美国国家航空航天局正式提出“Digitaltwin”的概念，并将DT用于航天飞行器的设计与维护。此后，随着计算机技术、多学科建模与仿真技术等的飞速发展，DT在制造业、医疗业与智慧城市等中得到了广泛应用[16]。当前的研究与应用表明，DT是一种智能的、不断进化的系统，通过在虚拟空间中建立物理世界实体的虚拟孪生体，并利用大数据、人工智能等技术建模和仿真分析物理实体的状态和行为，以及预测和控制物理实体的状态和行为[8,17]。这些物理实体可以是设备、机器人、车间或者通信网络等复杂的物理系统[18]，虚拟孪生体是物理实体的多级粒度映射。DT的主要目标是建立物理实体的高保真映射模型，在虚拟空间中真实反映物理实体的各项信息，通过分析虚拟孪生体的状态和行为，指导物理实体的运行，实现物理实体与虚拟孪生体的协同演进。

当前，已经有许多研究将DT运用于物理网络，如文献[7,10,12]等将应用DT于工业物联网、车联网和边缘网络等场景中，表明DT对于提高当前通信网络的应用性能具有强大的潜力。其中，为物理网络融入式构建DT通过在距离各网络设备较近的计算节点上构建各设备的数字孪生，具有交互时延小，网络成本低的特点。但是，这种方式由于需要整合网络中分散存在的计算资源，当物理网络中这些DT 构建节点的网络位置和计算资源变化时，会对构建物理网络的DT带来挑战。

# 2 问题分析与系统架构

本节首先针对在SDN 网络中进行融入式DT 构建所面临的资源有限问题进行分析，并由此提出了可变粒度数字孪生的概念。在此基础上，给出了SDN中构建可变粒度数字孪生的系统架构。

# 2.1问题分析

为 SDN 构建DT，能够增强 SDN对网络的感知、分析和控制能力，有助于提高面对应用场景中复杂网络数据的感知、处理能力；同时，在SDN中融入式构建DT时，SDN的全局视角和集中控制网络的特点有助于高效地利用网络中分散存在的计算资源构建DT。因此，为SDN融入式构建DT，既能够帮助SDN更高效地满足应用场景的需求，又能充分利用SDN网络的资源，以较低的时延提高构建DT时各计算设备之间资源协同能力。但是，在采用传统的DT构建方式时，其完整映射机制将对网络带来较大的计算开销。以如下两种场景为例：

1）当DT用于提高 SDN的网络安全防御能力时，在网络潜在风险较大的情况下，基于完整映射的DT可在精细的粒度上发现潜在风险，从而提前采取措施。然而，在网络攻击风险较小时，DT的完整映射与适当降低粒度的映射都可实现相同的安全防御能力[15,19]。此时可以在保证相同安全防御能力的前提下，适当降低DT的映射粒度，以减少DT 构建所带来的资源开销。

2)当DT用于协助SDN 进行网络资源调度时，若需要管理调度当下或短期内的网络资源，采用完整映射构建的DT能通过更精细的数据分析网络状态和调度网络资源。然而，在需要以较大的时间跨度管理网络资源时，构建DT采用完整映射方式和适当降低粒度的映射方式都可达到相同的资源调度效果，但后者带来的网络资源开销更低。

因此，在实际应用场景的需求下，并不一定需要构建出SDN的完整映射数字孪生。本文提出了可变粒度数字孪生思想，即基于应用场景的需求特征和网络中的可用计算资源，通过调整DT中物理网络的映射粒度与孪生体放置位置，构建出更有效的DT，以满足应用场景的需求。

为了实现DT的“可变粒度”，VGDT可通过调整数据的更新周期与每周期更新的数据量这两个维度上实现可变粒度如图1(a)所示，调整各设备上传数据的周期可以改变DT中各孪生体的数据更新周期，若DT需要计算分析网络的历史数据，如利用循环神经网络(Recurrent NeuralNetwork,RNN)分析网络流量时，当缩短输入的时序数据长度时，能够降低神经元的迭代次数，进而减少计算时间。如图1(b)所示，调整各设备孪生体每周期要更新的数据量，不仅可降低各设备每次上传数据时的通信量，也会改变DT分析处理数据的计算时间。如DT 需要利用主成分分析(PrincipalComponentAnalysis,PCA)对由网络数据组成的矩阵进行降维时，当减少每次输入矩阵的数据量，能够降低PCA的计算复杂度，从而节省DT处理数据的计算时间。

![](images/982be74f0bcadf51145c9b4b688b715161177efdb997272fa4f173aceb595cd0.jpg)  
图1映射粒度可变示例  
Fig.1Example of variable mapping granularity

以上两种调整粒度的方式，都达到了降低DT构建资源开销的目的。尽管这两种方式从形式上是有区别的，但是从本质上来讲，都降低了每个周期内DT构建中的数据更新需求。因此，本文所述的可变粒度，可以是周期的可变、也可以是固定周期下的数据粒度可变。为了便于叙述，本文将“可变粒度”统一表示为固定周期下的数据粒度调整。

# 2.2可变粒度数字孪生系统架构

图2展示了面向SDN的可变粒度数字孪生构建技术架构。该架构采用融入式构建方式，通过充分利用SDN中分散存在的可用计算资源(如，在完成固有业务后仍有富余计算资源的边缘服务器、用户设备等，为表述方便，本文将之统称为边缘服务器)，为 SDN 构建出可变粒度的数字孪生。在VGDT中，控制器或接入控制器的边缘服务器根据应用场景的需求信息与各边缘服务器上的可用计算资源量，分析各与元素的映射粒度和孪生体放置位置对构建DT的时延和模型完整性等的影响，为网络制定最优的DT构建方案。随后，控制器或接入控制器的边缘服务器将包含完成应用需求需要的元素、各映射元素的粒度和各设备孪生体的放置位置等构建DT的信息向全网广播。然后，各主机、交换机根据映射元素的粒度信息收集、处理和传输应用场景需要的映射数据至目标边缘服务器，从而在各边缘服务器上建立局部网络的DT。最后，控制器或接入控制器的边缘服务器通过与其他边缘服务器进行通信交互，获取和同步各局部网络DT的信息，连接各局部网络DT以建立整个网络的DT，从而实现在SDN中融入式构建出数字孪生。

假设 SDN 中有 $N ( N \in \mathbb { N } ^ { + } )$ 台交换机，这些交换机组成集合 ${ \cal S } = \{ s _ { 1 } , s _ { 2 } , \cdots , s _ { N } \}$ ；每台交换机 $s _ { i } ( 1 \leq i \leq N $ 且 $i \in \mathbb { N } ^ { + }$ ）所连接的主机数量为 $n _ { i } ( n _ { i } \in \mathbb { N } ^ { + } )$ ，这些主机 $h _ { i , j } ( 1 \leq j \leq n _ { i }$ ，且j $\dot { { \bf \varphi } } \in \mathbb { N } ^ { + } .$ 组成的集合为$H _ { i } = \{ h _ { i , 1 } , h _ { i , 2 } , \cdots , h _ { i , n _ { i } } \}$ 。网络中每个具有富余计算资源的边缘服务器记为 $e _ { k } ( 1 \leq k \leq L ,$ 且k $\in \mathbb { N } ^ { + }$ ），这些边缘服务器组成集合$E = \{ e _ { 1 } , e _ { 2 } , \cdots , e _ { L } \}$ ， $L ( L \in \mathbb { N } ^ { + } )$ 为边缘服务器的数量；记 $\boldsymbol { e } _ { k }$ 上的可用计算资源量为 $f _ { k } ( t )$ ， $f _ { k } ( t )$ 表示能用于构建DT的等效计算周期数，在SDN中所有可用计算资源组成集合$F ( t ) = \{ f _ { 1 } ( t ) , f _ { 2 } ( t ) , \cdots , f _ { L } ( t ) \}$ 。由于边缘服务器分散在网络中，若主机 $h _ { i , j }$ 在 $\boldsymbol { e } _ { k }$ 上建立其孪生体 $h _ { i , j } ^ { \cdot }$ ，则有 $l _ { i , j } ^ { k } = 1$ ，否则 $l _ { i , j } ^ { k } = 0$ ；同时为简化表示，若 $s _ { i }$ 在 $\boldsymbol { e } _ { k }$ 上建立其孪生体 $s _ { i } ^ { \prime }$ ，则有 $l _ { i , 0 } ^ { k } = 1$ ，否则$l _ { i , 0 } ^ { k } = 0$ 0

![](images/d2ebc8fea138f0caf663b79ba500c08efebde5da3700cd1bbeb2469a6dc36126.jpg)  
图2面向SDN的可变粒度数字孪生系统架构  
Fig.2Variable granularity-digital twin system architecture for SDN

在为SDN构建的DT中，交换机和主机的数字孪生体可统一表示为 $< D a t a ( t ) , S t a t e ( t ) , \Delta D a t a ( t + 1 ) >$ ，其中 $D a t a ( t )$ 表示网络设备根据应用需求向DT映射的历史数据，State(t)表示DT在完成应用需求时孪生体的运行状态， $\Delta D a t a ( t + 1 )$ 表示下一周期设备向其孪生体映射的数据。对于孪生体拥有的历史数据，Data(t)中拥有表征设备物理特征的静态数据，如 $s _ { i }$ 和 $h _ { i , j }$ 的CPU频率、内存大小和物理连接关系等；以及反映设备运行状态的动态数据，如 $s _ { i }$ 上控制器下发的转发流表、数据包转发日志和 $h _ { i , j }$ 的通信缓存大小，遭受网络攻击日志等。为完成应用需求，SDN中交换机向VGDT 映射的元素有 $N _ { s }$ 种，每种元素的映射粒度表示为 $\omega _ { i } ^ { s } ( 1 \leq i \leq N _ { s } , 0 < \omega _ { i } ^ { s } \leq 1 )$ ，这些映射粒度组成集合 $\Omega _ { s } = \{ \omega _ { 1 } ^ { s } , \omega _ { 2 } ^ { s } , \cdots , \omega _ { N _ { s } } ^ { s } \}$ ；同理，SDN 中主机向VGDT 映射的元素有 $\boldsymbol { N } _ { h }$ 种，这些元素的映射粒度为 $\omega _ { j } ^ { h } ( 1 \leq j \leq N _ { h } , 0 < \omega _ { j } ^ { h } \leq 1 )$ ，且主机元素的映射粒度组成集合 $\Omega _ { h } = \{ \omega _ { 1 } ^ { h } , \omega _ { 2 } ^ { h } , \cdots , \omega _ { N _ { h } } ^ { h } \}$ 。

# 3 可变粒度数字孪生优化模型

在基于可变粒度思想构建SDN的DT时，应用场景对于VGDT的需求表示为三元组 $< I _ { 0 } , D _ { 0 } , E _ { 0 } >$ ，其中 $I _ { 0 }$ 为构建DT的模型完整度，表示基于可变粒度思想构建的DT与基于完整映射构建的DT之间的比例关系； $D _ { 0 }$ 为数字孪生的模型构建时延，表示从网络产生更新数据到VGDT根据新的数据完成DT更新所需的时间； $\phantom { + } E _ { 0 }$ 为模型时效性和模型完整度两个指标的综合衡量，称为构建DT的模型有效性，表示在可用计算资源约束下，VGDT满足应用需求的程度。本节将基于对模型构建时延、模型完整度和模型有效性的分析，建立可变粒度数字孪生优化模型。

# 3.1粒度分析

在应用需求驱动下，VGDT将根据网络中的可用计算资源调整DT中各元素的映射粒度和各孪生体的放置位置，进而影响DT构建时的模型完整度 $I ( t )$ 和模型构建时延 $D ( t )$ 。其中， $I ( t )$ 主要与各元素的映射粒度相关，且映射粒度越大， $I ( t )$ 越高，本文用函数 $\psi ( \Omega _ { s } , \Omega _ { h } )$ 衡量当前的 $I ( t )$ ，并令

$$
\psi ( \Omega _ { s } , \Omega _ { h } ) = \sum _ { i } ^ { N _ { s } } \mathrm { l o g } _ { 2 } ( 1 + \omega _ { i } ^ { s } ) w _ { i } ^ { s } + \sum _ { j } ^ { N _ { h } } \mathrm { l o g } _ { 2 } ( 1 + \omega _ { j } ^ { h } ) w _ { j } ^ { h } .
$$

其中， $w _ { i } ^ { s } ( 0 < w _ { i } ^ { s } < 1 )$ 和 $w _ { j } ^ { h } ( 0 < w _ { j } ^ { h } < 1 )$ 分别是在构建DT时，DT 中交换机第 $i$ 项元素和主机第 $j$ 项元素对于DT 模型完整度的重要性权重，并有 $\sum _ { i = 1 } ^ { N _ { s } } w _ { i } ^ { s } + \sum _ { j = 1 } ^ { N _ { h } } w _ { i } ^ { h } = 1$ 。

由于SDN中可用计算资源分散存在，当VGDT调整映射粒度和主机、交换机的孪生体位置时，主机、交换机的映射数据量与目标边缘服务器的改变都会影响构建DT的通信与计算时延。本文令DT的模型构建时延 $D ( t )$ 为这些边缘服务器上模型构建时延的平均值，即

$$
D ( t ) = \frac { 1 } { L } \sum _ { k = 1 } ^ { L } [ D _ { k } ^ { C a l } ( t ) + D _ { k } ^ { C o m } ( t ) ] .
$$

其中， $D _ { k } ^ { C a l } ( t )$ 、 $D _ { k } ^ { C o m } ( t )$ 分别是 $\boldsymbol { e } _ { k }$ 用于构建DT的计算时延与通信时延。在完成应用需求时， $\boldsymbol { e } _ { k }$ 的计算时延 $D _ { k } ^ { c a l } ( t )$ 为构建每个孪生体的计算周期数之和，且构建一个孪生体需要的计算周期数与孪生体包含的元素数据量与映射粒度有关，本文用函数 $\varphi _ { i , j } ( t )$ 衡量构建每个孪生体需要的计算周期数，并令

$$
\varphi _ { i , j } \left( t \right) = \left\{ \begin{array} { l l } { \displaystyle \sum _ { k = 1 } ^ { N _ { s } } { s i z e _ { k } ^ { s } \theta ^ { \omega _ { k } ^ { s } } } , \quad j = 0 } \\ { \displaystyle \sum _ { k = 1 } ^ { N _ { h } } { s i z e _ { k } ^ { h } \theta ^ { \omega _ { k } ^ { h } } } , \quad j \ge 1 } \end{array} \right. .
$$

在上式中，size和 $s i z e _ { k } ^ { h }$ 分别表示对交换机和主机的第 $k$ 项元素进行完整映射时的数据量； $\theta$ 为完整映射每项元素时，构建 $s _ { i } ^ { \prime }$ 和 $h _ { i , j } ^ { \cdot }$ 需要的计算周期数与孪生体包含数据量的转换比例；当 $j = 0$ 时， $\varphi _ { i , 0 } ( t )$ 表示构建 $s _ { i } ^ { \dagger }$ 需要的计算周期数，当 $j { \geq } 1$ 时， $\varphi _ { i , j } ( t )$ 表示构建 $h _ { i , j } ^ { \prime }$ 需要的计算周期数。由此可得到 $\boldsymbol { e } _ { k }$ 上构建DT要消耗的计算时延 $D _ { k } ( t )$ 为[20]

$$
D _ { k } ^ { C a l } \left( t \right) = \frac { \displaystyle \sum _ { i = 1 } ^ { N } \sum _ { j = 0 } ^ { n _ { i } } l _ { i , j } ^ { k } \times \varphi _ { i , j } \left( t \right) } { f _ { k } \left( t \right) } .
$$

$\boldsymbol { e } _ { k }$ 上构建DT的通信时延主要包括主机、交换机和边缘服务器之间的通信时延，以及各边缘服务器协同构建DT的交互时延。其中，在主机、交换机会和目标边缘服务器实时交互过程中，由于主机、交换机主要向边缘服务器传输更新DT的数据，边缘服务器主要向主机、交换机传输一些如映射粒度、李生体构建位置或其他控制消息，且后者的通信量远小于前者，故本文考虑的主机、交换机和边缘服务器之间的通信时延主要映射数据更新时延。此外，由于本文所采用的边缘服务器协同方案和其他方案中协同方式相同[20]，构建DT 需要的交互时延并无明显区别，故本文主要将边缘服务器接收孪生体更新数据的时延作为通信时延。对于交换机、主机向 $\boldsymbol { e } _ { k }$ 发送更新数据的平均通信时延为

$$
D _ { k } ^ { C o m } ( t ) = \frac { \displaystyle \sum _ { i = 1 } ^ { N } [ l _ { i , 0 } ^ { k } D _ { s _ { i } , e _ { k } } ^ { C o m } ( t ) + \sum _ { j = 1 } ^ { n _ { i } } l _ { i , j } ^ { k } D _ { h _ { i , j } , e _ { k } } ^ { C o m } ( t ) ] } { \displaystyle \sum _ { i = 1 } ^ { M } \sum _ { j = 0 } ^ { n _ { i } } l _ { i , j } ^ { k } } .
$$

在式(5)中， $D _ { s _ { i } , e _ { k } } ^ { C o m } ( t )$ 和 $D _ { h _ { i , j } , e _ { k } } ^ { C o m } ( t )$ 分别是 $s _ { i }$ 和 $h _ { i , j }$ 向 $\boldsymbol { e } _ { k }$ 发送DT更新数据的时延。在 SDN中， $D _ { s _ { i } , e _ { k } } ^ { C o m } ( t )$ 和 $D _ { h _ { i , j } , e _ { k } } ^ { C o m } ( t )$ 的计算方式分别为

和

$$
\begin{array} { r } { D _ { s _ { i } , e _ { k } } ^ { C o m } ( t ) = m _ { s } [ t _ { q u } + t _ { p o } + t _ { t r } ( t ) ] + t _ { p g } \left( t \right) } \\ { D _ { h _ { i } , j , e _ { k } } ^ { C o m } ( t ) = m _ { h } [ t _ { q u } + t _ { p o } + t _ { t r } ( t ) ] + t _ { p g } \left( t \right) . } \end{array}
$$

其中， $m _ { s } \left( m _ { s } \ge 1 \right.$ 且 $m _ { s }$ 为整数)和 $m _ { h }$ （ $m _ { h } \ge 1$ 且 $m _ { h }$ 为整数)分别是$s _ { i }$ 和 $h _ { i , j }$ 到 $\boldsymbol { e } _ { k }$ 之间的通信跳数， $t _ { \boldsymbol { q } u } ~ , ~ t _ { \boldsymbol { p o } } ~ , ~ t _ { t r } ( t )$ 和 $t _ { p g } ( t )$ 分别是每一跳通信交换机上的排队时延、处理时延、发送时延和通信链路上的传播时延。在SDN中，两个设备通信过程的时延由排队时延、处理时延、发送时延和传播时延四部分组成；考虑到处理时延与排队时延通常与具体应用网络的特征有关，并且在同一个网络中它们的值相对比较确定，为简化分析并不失一般性，本文将 SDN中每一跳的处理时延采用均值 $t _ { p o }$ ，每一跳的排队时延采用均值 $t _ { q u }$ 。发送时延 $t _ { t r } ( t )$ 表示将报文从

$s _ { i }$ 发送出去的时间，即

$$
t _ { t r } \left( t \right) = \frac { s i z e } { B } .
$$

上式中， $B$ 为交换机的数据发送速率[12]，size为报文的数据量。在构建DT时， $s _ { i }$ 和 $h _ { i , j }$ 传输给目标 $\boldsymbol { e } _ { k }$ 进行DT更新的数据量分别为 $s i z e _ { i } ^ { * } = \sum _ { k = 1 } ^ { N _ { s } } s i z e _ { k } ^ { s } \omega _ { k } ^ { s }$ 和 $s i z e _ { i , j } ^ { \prime } = \sum _ { k = 1 } ^ { N _ { h } } s i z e _ { k } ^ { h } \omega _ { k } ^ { h }$ 。传播时延$t _ { p g } ( t )$ 表示通过电磁波传输数据的时间，有

$$
t _ { p g } \left( t \right) = \frac { d } { 2 c / 3 } .
$$

在式(9)中， $^ d$ 为两通信对象之间的通信距离， $s _ { i }$ 和 $h _ { i , j }$ 与目标 $\boldsymbol { e } _ { k }$ 之间的通信距离分别记为 $d ( s _ { i } , e _ { k } )$ 和 $d ( h _ { i , j } , e _ { k } )$ ， $2 c / 3$ 为光在介质中的传输速度[21]。

# 3.2优化模型

在应用需求下，VGDT根据可用计算资源分布情况调整各映射元素的粒度和各交换机、主机的数字孪生体放置位置，以减小交换机、主机向DT映射数据的通信量和边缘服务器上的平均计算量，从而降低DT的模型构建时延和提高各孪生体的模型完整度，实现通过充分利用网络可用计算资源，构建出更有效的DT。因此，为向应用提供更有效的DT，VGDT应根据现有网络计算资源，联合优化DT中各项特征的映射粒度和各孪生体的放置位置。本文对DT的模型有效性 $E ( t )$ 建模如下，

$$
\begin{array} { r l } & { \quad \underset { 0 , 0 , 1 , \ldots } { \mathrm { a r g } } \quad \operatorname* { m a x } E ( I ) = I ( I ) - \alpha \times D ( I ) , } \\ & { \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ &  \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \ \end{array}
$$

其中， $\alpha$ 为模型构建时延对模型有消息的影响因子， $L i n k$ 为由孪生体放置位置变量 $l _ { i , j } ^ { k }$ 组成的集合，表示为

$$
L i n k = \left[ \begin{array} { c c c } { l _ { 1 , 0 } ^ { 1 } } & { \cdots } & { l _ { 1 , 0 } ^ { L } } \\ { \vdots } & { \ddots } & { \vdots } \\ { l _ { N , n _ { N } } ^ { 1 } } & { \cdots } & { l _ { N , n _ { N } } ^ { L } } \end{array} \right] .
$$

在式(10)的约束项中， $\scriptstyle { C 1 \sim C 3 }$ 表示构建VGDT 时模型有效性、模型完整度和模型构建时延要满足应用需求， $C 4$ 和 $c 5$ 表示交换机、主机每项映射元素的数据量需达到构建DT 需要最低数据量msize（ $0 < m s i z e _ { i } ^ { s } \leq s i z e _ { i } ^ { s }$ ， $1 \leq i \leq N _ { s }$ ）和msizeh（ $0 < m _ { j } ^ { h } \le s i z e _ { j } ^ { h }$ ， $1 \leq j \leq N _ { h }$ )， $c 7$ 表示每个交换机、主机只能在一个边缘服务器上建立其孪生体。由于式(10)中要求解的变量$\omega _ { i } ^ { s }$ 、 $\omega _ { j } ^ { h }$ 为连续型变量， $l _ { i , j } ^ { k }$ 为离散变量，可知该优化模型为一个典型的混合整数规划(Mixed integer programming,MIP)问题，而MIP问题是一类NP-Hard问题[22]，式(1O)无法在多项式时间内求解。

# 4混合编码遗传算法

MIP常用于产能规划、资源分配等问题中，当前对于求解MIP问题有分支定界法、拉格朗日松弛算子和启发式算法等方法。其中，分支定界法常用于求解规模较小的数学问题，且能得到问题的最优解；拉格朗日松弛算子通过减少求解问题的约束，能够求解出原问题的近似解，但该方法的求解规模有限，并且不一定能够得到原问题的最优解；启发式算法是人们通过观察自然规律等提出的最优化求解方法，能够在多项式时间得到较优的可行解，且已在许多研究中得到了应用。遗传算法作为一种典型的启发式算法，通过模拟生物在自然环境中的遗传和进化过程，能对逐渐优化求解结果的全局自适应概率搜索算法，常用于求解一些NP-Hard和NP-Complete等计算困难的优化问题。在遗传算法中，种群中的每个个体都是一组候选解，通过多次的选择、交叉和变异迭代，最终能够得到满足收敛条件的最优解[23]。

由于式(10)中求解变量 $\omega _ { i } ^ { s }$ 和 $\omega _ { j } ^ { h }$ 是连续型变量， $l _ { i , j } ^ { k }$ 是离散变量，本文对遗传算法的染色体进行分段编码，第一段编码区域为实数编码区域，用于求解 $\Omega _ { s }$ 和 $\Omega _ { h }$ ，第二段编码为二进制编码区域，用于求解 $L i n k$ 。在遗传算法求解式(10)时，控制求解效率的参数主要包括种群规模 $\boldsymbol { N } _ { p }$ ，交叉概率 $P _ { c }$ 、变异概率 $\boldsymbol { P _ { m } }$ 和迭代次数 $N _ { d }$ ，并且令式(10)为遗传算法的适应度函数以下分别介绍利用混合编码遗传算法求解式(10)选择、交叉和变异步骤。

# 4.1选择算子

在遗传算法的父代个体选择策略中，轮盘赌选择是最常见的方法，其基本思想为：每个个体被选中的概率与其适应度值的大小正相关，并且该方法是基于概率的，结合最优个体保留策略，既能够保证当前适应度最优的个体能进化到下一代，又能改善遗传算法的局部最优问题。

在第 $\tau$ 代种群向第 $\boldsymbol { \tau } + \boldsymbol { 1 }$ 代个体进化时，假设 $\pi _ { 1 } ^ { \tau }$ 为种群中的最优个体，其余个体 $\pi _ { i } ^ { \tau } ( i \in [ 2 , N _ { s } ] )$ 进行遗传的概率为

$$
p _ { i } = \frac { E _ { i } ^ { \prime } ( t ) } { \displaystyle \sum _ { i = 2 } ^ { N _ { s } } E _ { i } ^ { \prime } ( t ) } ,
$$

$\pi _ { i } ^ { \tau }$ 经过交叉、变异操作后，生成 $\boldsymbol { N } _ { p }$ 个新个体，若存在适应度大于 $\pi _ { 1 } ^ { \tau }$ 的新个体，则舍弃 $\pi _ { 1 } ^ { \tau }$ ，选择新个体中适应度最高的个体作为最优个体 $\pi _ { 1 } ^ { \tau + 1 }$ ；否则，则用 $\pi _ { 1 } ^ { \tau }$ 替换适应度最差的新个体，且 $\pi _ { 1 } ^ { \tau + 1 } = \pi _ { 1 } ^ { \tau }$ 。

# 4.2交叉算子

在遗传算法中，交叉算子是进化新个体的主要算子，对遗传算法的搜索效率影响很大。为提高遗传算法的收敛速度，本文利用分段交叉算子对实数编码区域和符号编码区域进行并行求解。假设实数编码区域和二进制编码区域分别以交叉概率 $P _ { c } ^ { r }$ 、 $P _ { c } ^ { b }$ 做交叉操作，并且对交叉概率进行自适应调整，有

$$
P _ { c } ^ { r } = \left\{ \begin{array} { c c } { \displaystyle \frac { \eta _ { 1 } ^ { c } ( p _ { \mathrm { m a x } } - p ^ { \prime } ) } { p _ { m a x } - p _ { a v g } } } & { , } & { p _ { a v g } \leq p ^ { \prime } } \\ { \eta _ { 2 } ^ { c } } & { , } & { p _ { a v g } > p ^ { \prime } } \end{array} \right. ,
$$

$$
P _ { c } ^ { s } = \left\{ \begin{array} { c c } { \displaystyle \eta _ { 3 } ^ { c } ( p _ { \mathrm { m a x } } - p ^ { \prime } ) } & { , \quad p _ { a \nu g } \leq p ^ { \prime } } \\ { \displaystyle p _ { m a x } - p _ { a \nu g } } & { , \quad p _ { a \nu g } > p ^ { \prime } } \\ { \displaystyle \eta _ { 4 } ^ { c } } & { , \quad p _ { a \nu g } > p ^ { \prime } } \end{array} \right.
$$

其中， $p _ { m a x }$ 是最优个体的适应度， $p ^ { \prime }$ 是进行交叉操作的两个染色体中的最大适应度， $p _ { a \nu g }$ 为第 $\tau$ 代种群的平均适应度； $\eta _ { \mathrm { i } } ^ { c }$ ，$\eta _ { 2 } ^ { c }$ 、 $\eta _ { 3 } ^ { c }$ 、 $\eta _ { 4 } ^ { c }$ 均为(0,1之间设定的常数。混合编码交叉算子的执行流程如下：

a)对锦标赛算子选出的个体进行随机配对，计算该对染色体的自适应交叉概率；b)从配对成功的染色体上随机选取两个交叉点，且分别位于实数编码区域和二进制编码区域；c)对于两条染色体实数编码区域的交叉点按概率 $P _ { c } ^ { r }$ 判断是否需要交叉，若需要交叉，则交换两个基因；否则，不做改变。以概率 $P _ { c } ^ { b }$ 判断符号编码区域的交叉点是否需要交叉，若需要交叉，则交换两个基因；否则，不做改变。

# 4.3变异算子

经过多次的遗传进化后，种群各个体会逐渐趋于一致，变异算子的存在能够提高种群的多样性，缓解陷入局部最优。由于染色体上存在两种编码区域，本文提出分段变异算子。假设实数编码区域和二进制编码区域分别以变异概率 $P _ { m } ^ { r }$ 、 $P _ { m } ^ { b }$ 做变异运算，并且对变异概率进行自适应调整，有

$$
P _ { m } ^ { r } = \left\{ \begin{array} { c c c } { \displaystyle \eta _ { 1 } ^ { m } ( p _ { \mathrm { m a x } } - p ) } & { , } & { p _ { a v g } \leq p } \\ { p _ { m a x } - p _ { a v g } } & { , } & { p _ { a v g } > p } \\ { \displaystyle \eta _ { 2 } ^ { m } } & { , } & { p _ { a v g } > p } \end{array} \right. ,
$$

$$
P _ { c } ^ { s } = \left\{ \begin{array} { c c } { \displaystyle \eta _ { 3 } ^ { m } ( p _ { \mathrm { m a x } } - p ) } & { , \quad p _ { a v g } \leq p } \\ { p _ { m a x } - p _ { a v g } } & { , \quad p _ { a v g } > p } \\ { \displaystyle \eta _ { 4 } ^ { m } } & { , \quad p _ { a v g } > p } \end{array} \right. ,
$$

其中， $p$ 是进行变异操作染色体的适应度， $\eta _ { \mathrm { l } } ^ { m }$ 、 $\eta _ { 2 } ^ { m }$ 、 $\eta _ { 3 } ^ { m }$ 、 $\eta _ { 4 } ^ { m }$ 均为(0,1]之间的常数。混合编码变异算子的执行流程如下：

a)计算变异染色体的自适应变异概率，分别从实数编码区域、二进制编码区域中随机选取一个基因；

b)以概率 $P _ { m } ^ { r }$ 对判断实数编码区域的基因是否需要变异，若是，则用(01上的随机数代基因位的值；否则不作操作。以概率 $P _ { m } ^ { b }$ 对判断二进制编码区域的基因是否需要变异，若是，则用0或1替代基因位上的 $l _ { i , j } ^ { k }$ ；否则不作操作。

混合编码遗传算法求解式(10)需要的参数有 $F ( t )$ 、 $A$ 和$\boldsymbol { G }$ 。其中， $A$ 为在应用需求下，构建DT的参数集合，包括映射元素的完整数据量、完成应用需求的重要性权重和最少映射数据量，即

$$
A = \left[ \begin{array} { c c c c c c } { s i z e _ { 1 } ^ { s } } & { \cdots } & { s i z e _ { R _ { s } } ^ { s } } & { s i z e _ { 1 } ^ { h } } & { \cdots } & { s i z e _ { R _ { h } } ^ { h } } \\ { m s i z e _ { 1 } ^ { s } } & { \cdots } & { m s i z e _ { R _ { s } } } & { m s i z e _ { 1 } ^ { h } } & { \cdots } & { m s i z e _ { R _ { h } } ^ { h } } \\ { w _ { 1 } ^ { s } } & { \cdots } & { w _ { R _ { s } } ^ { s } } & { w _ { 1 } ^ { h } } & { \cdots } & { w _ { R _ { h } } ^ { h } } \end{array} \right] .
$$

$G$ 为包括SDN的网络拓扑、排队时延等与网络通信相关的信息集合。用混合编码遗传算法求解式(10)的流程见算法1。

算法1混合编码遗传算法输入： $F ( t ) \mathrm { ~ , ~ } A \mathrm { ~ , ~ } G \mathrm { ~ \quad ~ } / { * } F ( t )$ 为网络可用计算资源集合， $A$ 为构建DT的参数集合， $G$ 为网络信息集合； $^ { * } /$ 输出： $\Omega _ { s }$ ， $\Omega _ { h }$ ,Link $/ ^ { * } \Omega _ { s }$ 为交换机元素的映射粒度集合， $\Omega _ { h }$ 为主机元素的映射粒度集合；Link为交换机、主机的孪生体位置集合 $^ { * } /$ a）在满足约束条件下，随机初始化种群并根据适应度大小对个体排序得到 $\Pi ^ { 1 } = \{ \pi _ { 1 } ^ { 1 } , \pi _ { 2 } ^ { 1 } , \cdots \pi _ { N _ { s } } ^ { 1 } \}$ 。b)while 达到收敛条件 doc）while 生成 $\boldsymbol { N } _ { p }$ 个新个体 do $/ { * }$ 交叉生成新个体\*/d) 从 $\Pi ^ { \tau }$ 中随机选择出个体 $\pi _ { i } ^ { \tau }$ 和 $\pi _ { j } ^ { \tau }$ ：e) while $\boldsymbol { \pi } _ { i } ^ { \tau + 1 }$ 和 $\boldsymbol { \pi } _ { j } ^ { \tau + 1 }$ 满足约束条件 dof) $\pi _ { i } ^ { \tau }$ 和 $\pi _ { j } ^ { \tau }$ 进行交叉运算得到 $\pi _ { i } ^ { \tau + 1 }$ 和 $\pi _ { j } ^ { \tau + 1 }$ ·end whileend whileg）for $i \in [ 1 , N _ { s } ]$ do $/ { ^ * }$ 对种群个体进行变异\*/h) $\pi _ { i } ^ { \tau + 1 }$ 和 $\pi _ { j } ^ { \tau + 1 }$ 进行变异运算；i) while $\pi _ { i } ^ { { \tau + 1 } }$ 和 $\pi _ { j } ^ { \tau + 1 }$ 不满足约束条件 doj) $\pi _ { i } ^ { \tau + 1 }$ 和 $\pi _ { j } ^ { \tau + 1 }$ 进行变异运算；end whileend fork） $R a n k ( \Pi ^ { \tau + 1 } )$ //将 $\Pi ^ { \tau + 1 }$ 中的个体按适应度大小排序；1）if $p _ { 1 } ^ { \tau } > p _ { 1 } ^ { \tau + 1 }$ do $/ { ^ * }$ 最优个体保留策略，若 $\pi _ { 1 } ^ { \tau }$ 的适应度 $p _ { \mathrm { i } } ^ { \tau }$ 大于 $\pi _ { 1 } ^ { \tau + 1 }$ 的适应度 $p _ { 1 } ^ { \tau + 1 }$ ，将替换 $\pi _ { N _ { s } } ^ { \tau + 1 }$ ； $^ { * } /$ m) （20 $\pi _ { N _ { s } } ^ { \tau + 1 } = \pi _ { 1 } ^ { \tau }$ end ifend while

# 5 仿真与性能分析

为了验证VGDT的性能，本文基于PyCharm环境，针对VGDT的数字孪生构建时延、完整度、有效性及通信开销进行了仿真与比较，具体如下。

# 5.1仿真环境设置

为评估本文所提VGDT构建技术，选取了文献[14]的数字孪生构建算法和文献[24]中采用的对比算法作为本文对比算法。本节仿真选取的拓扑为由15个节点、17条边组成的数据中心网络拓扑Claranet[25]。如图3所示，交换机数量为15，边缘服务器数量为5，每台交换机下的主机数量服从[5,10]的均匀分布，数据传输速率为 $1 0 0 \mathrm { M b / s }$ ，交换机上排队时延和处理时延均为5ms。对于DT应用需求，交换机要映射的元素有5种，这些映射元素的数据量(字节)服从[0.01M,0.05M]的均匀分布，对于DT模型完整度的权重占比和为0.6;主机要映射的元素有10 种，这些元素的数据量服从[0.01M,0.05M]的均匀分布，它们对于DT模型完整度的总权重占比为0.4，完整映射时各元素的数据量与计算周期数转换比例 $\theta$ 为100。

![](images/aa6439c26f9386ec1b493d1d2376ad5caf3afdefea5b775d37a12f5e58896356.jpg)  
图3Claranet 拓扑 Fig.3Claranet topology

# 5.2仿真结果与性能分析

为了衡量可变粒度数字孪生的应用性能，本文分别针对模型构建时延、模型完整度、模型有效性和构建DT的通信开销四个指标，在不同的网络平均可用计算资源情况下，将VGDT算法与文献[14]提出的数据采样算法SAMPLING，以及传统的完整映射算法进行了对比。

图4表示不同网络计算资源与影响因子 $\alpha$ 对于构建DT的通信开销影响情况。当计算资源较少时，VGDT的通信开销更高，且随着计算资源量增加，VGDT和对比算法的通信开销都随之增加。当 $a$ 较小时，模型构建时延对于模型有效性的影响较小，因此 $a = 1$ 时三种构建模式的通信开销均比$a = 5$ 时的通信开销更大。为充分利用网络计算资源，VGDT将部分主机、交换机的孪生体建立在通信距离更远、计算资源更多的边缘服务器上，因此 $\alpha = 1$ 的VGDT通信开销在平均计算资源量为 $1 0 \mathrm { G H z }$ 左右时先上升再下降。此外，当计算资源量较充足时，VGDT通过将各主机、交换机的孪生体放置更合理的边缘服务器上，使 $a = 5$ 时的通信开销低于对比算法。

![](images/f6f715af153ccbcb5d3976bb74aec73f37228018f278e3ff8b9d32ae48034784.jpg)  
图4构建DT的通信开销  
Fig.4The communication cost of building DT

图5表示不同网络可用计算资源与影响因子 $\alpha$ 对DT的模型构建时延影响情况。当边缘服务器上的平均计算资源量较少时，VGDT和对比算法的模型构建时延都相对较高，且$\alpha = 1$ 曲线的模型构建时延比 $\alpha { = } 5$ 曲线更高。当 $a = 1$ 时，模型构建时延对于模型有效性的影响较小，随着网络计算资源增加，VGDT通过提高映射粒度以提高模型有效性，使模型构建时延保持在较高的水平；当 $a = 5$ 时，模型构建时延的影响较大，VGDT通过优化映射粒度和数字孪生体布局，减小了模型构建时延。此外，当网络计算资源充足时，三种方式的模型构建时延都逐渐减少。

![](images/2eda9be3ba4bbd897c57865e5fceeb3ae57a87d923392f8dccfc265b0cd1ec53.jpg)  
图5DT的模型构建时延

图6表示不同网络计算资源与影响因子 $\alpha$ 对DT的模型构建完整度影响情况。在计算资源量较少时，VGDT的构建完整度更高，但随着计算资源量增加，对比算法的构建完整度快速上升，并达到 $\scriptstyle \alpha = 1$ 时VGDT的水平。此外，由于模型构建时延对于模型有效性的影响，随着网络计算资源增加，VGDT在 $a = 5$ 时模型完整度增加速度较对比算法缓慢，但三种算法的模型完整度会逐渐达到相同水平。

图7表示不同网络计算资源与影响因子 $\alpha$ 对DT的模型构建有效性影响情况。在计算资源量较少时，VGDT相比于对比算法具有更高的模型有效性，但随着计算资源量增加，相同 $\alpha$ 情况下对比算法的模型有效性快速上升，最终接近VGDT曲线。同时，由于 $\boldsymbol { a }$ 的影响，三种算法在 $\scriptstyle \alpha = 1$ 时的模型构建有效性比 $\scriptstyle \alpha = 5$ 时的模型有效性更高。

![](images/891f090c61f7cf69d218931b015cef20ee26a738a634ce34256f710f62b4a587.jpg)  
图6DT的模型完整度

![](images/42a4e64d9baddf7f59ed0c997c4c833c2902b9fb04c09772fabcc372094e5afb.jpg)  
Fig.5The model building delay of DT   
Fig.6The model integrity of DT   
图7DT 的模型有效性  
Fig.7The model validity of DT

仿真结果表明，在不同网络计算资源情况下，VGDT通过最优化映射粒度和数字孪生体布局，对网络计算资源进行充分利用，从而构建出具有更高模型有效性的DT，以更好地

满足应用需求。

# 6 结束语

随着SDN应用场合与需求的多样化，数字孪生技术能够帮助SDN更精准地分析、预测和控制网络，以更好地满足应用需求。本文在SDN可用计算资源有限的情况下，基于应用场景的需求特征，提出了调整映射数据粒度和数字孪生体放置布局的可变粒度数字孪生构建技术；在此基础上，通过分析映射粒度、孪生体放置位置对于构建DT的模型完整性和时延影响，建立了可变粒度数字李生优化模型，并通过混合编码遗传算法求解出不同计算资源下的最优映射粒度和李生体放置位置。仿真结果表明，根据应用需求特征，VGDT能够充分利用网络可用计算资源，为SDN构建出更有效的DT,从而提高SDN适应各种应用场景动态需求的能力。在未来的工作中，可将VGDT用于工业互联网、物联网、下一代移动通信网、无人蜂群等网络环境，结合具体应用需求进一步构建具有针对性的、与应用环境深度耦合的优化模型与算法。

# 参考文献：

[1]PiedrahitaAF M, Gaur V,Giraldo J,et al.Leveraging software-defined networking for incident response in industrial control systems [J].IEEE Software,2017,35 (1): 44-50.   
[2]Al-Rubaye S,Kadhum E,Ni Q,et al. Industrial internet of things driven by SDN platform for smart grid resiliency[J].IEEE Internet of Things Journal,2017,6(1): 267-277.   
[3]Manickavasagam B,Amutha B,Priyanka S.Optimal packet routing for wireless body area network using software defined network to handle medical emergency [J]. International Journal of Electrical and Computer Engineering,2020,10(1):427.   
[4]李可欣，王兴伟，易波，等．智能软件定义网络[J]．软件学报,2021, 32(01):118-136.(Li Kexin,Wang Xingwei,Yi Bo,et al.Survey of intelligent software defined networking [J]. Journal of Software,2021, 32 (1): 118-136.)   
[5]Tao Fei,Zhang He,Liu Ang,et al.Digital twin in industry: State-of-theart[J].IEEE Trans on Industrial Informatics,2018,15 (4): 2405-2415.   
[6]Zhao Liang,Han Guangjie,Li Zhuhui,et al. Intelligent digital twinbased software-defined vehicular networks [J].IEEE Network,2020,34 (5): 178-184.   
[7]Krishnan P,Jain K,Buyya R,et al.MUD-based Behavioral Profiling Security Framework for Software-defined IoT Networks [J/OL].IEEE Intermet of Things Journal,2021.(2021-9-17) [2022-01-26]. http://doi. org/10.1109/JIOT.2021.3113577.   
[8]Wu, Yiwen,Ke Zhang,and Yan Zhang.Digital Twin Networks: a Survey [J].IEEE Internet of Things Journal.2021,8(18):13789-13804.   
[9]孙滔，周铖，段晓东，等．数字孪生网络 (DTN)：概念、架构及关键 技术[J]．自动化学报,2021,47(3):569-582.(Sun Tao,Zhou Cheng, Duan Xiaodong，et al.Digital twin network (DTN):concepts, architecture,and key technologies [J].Acta Automatica Sinica,2021,47 (3): 569-582.)   
[10] Khan L U,Saad W,Niyato D,et al.Digital-Twin-Enabled 6G:Vision, architectural trends,and future directions [J].IEEE Communications Magazine,2022,60(1): 74-80.   
[11] Xu Xiaolong,Shen Bowen,Ding Shengchao,et al. Service offloading with deep Q-network for digital twinning empowered Internet of Vehicles in edge computing [J]. IEEE Transon Industrial Informatics, 2020.18 (2): 1414-1423.   
[12] Zhang Ke, Cao Jiayu, Zhang Yan. Adaptive Digital Twin and Multi-agent Deep Reinforcement Learning for Vehicular Edge Computing and Networks[J].IEEE Trans on Industrial Informatics,2021,18 (2):1405- 1413.   
[13] LopezJ,Rubio JE,Alcaraz C.Digital Twins for Intelligent Authorization in the B5G-Enabled Smart Grid [J]. IEEE Wireless Communications, 2021,28 (2): 48-55.   
[14] Yang Hongwei,Li Yang, Yao Kehan, et al. A Systematic Network Traffic Emulation Framework for Digital Twin Network [C]// IEEE the 1st International Conference on Digital Twins and Parallel Intelligence (DTPI) .Beijing: IEEE Press,2021: 94-97.   
[15]董仕．软件定义网络安全问题研究综述[J].计算机科学,2021,48 (3): 295-306. (Dong Shi. Survey on software defined network security [J],Computer Science,2021,48 (3): 295-306)   
[16] TaoFei, Cheng Jiangfeng,Qi Qinglin,etal.Dgitaltwin-drivenproduct design,manufacturing and service with big data [J]. The International Journal of Advanced Manufacturing Technology,2018,94 (9-12): 3563- 3576.   
[17] Rathore M M, Shah SA,Shukla D,et al.The Role of AI, Machine Learning,and Big Data in Digital Twinning: A Systematic Literature Review, Challenges，and Opportunities [J]. IEEE Access，2021，9: 32030-32052.   
[18] Nguyen HX,Trestian R,To D,et al. Digital twin for 5Gand beyond [J]. IEEE Communications Magazine,2021,59 (2): 10-15.   
[19] Dong Shi, Sarem M. DDoS atack detection method based on improved KNN with the degree of DDoS atack in software-defined networks [J]. IEEE Access,2019,8: 5039-5048.   
[20] Hou Xiangwang，Ren Zhiyuan， Wang Jingjing，etal.Reliable computation offloading for edge-computing-enabled software-defined IoV[J].IEEE Internet of Things Journal,2020,7(8): 7097-7111.   
[21] Wu Yiwen,Zhou Sipei, Wei Yunkai,etal, Deep reinforcement learning for controller placement in software defined network [Cl// IEEE INFOCOM-IEEE Conference on Computer Communications Workshops (INFOCOMWKSHPS).Toronto:IEEE Press,2020:1254-1259.   
[22]刘俊梅，高岳林．非线性混合整数规划问题的改进差分进化算法 [J]．工程数学学报,2010,27(6):967-974.(Liu Junmei,GaoYuelin. Improved differential evolution algorithm for nonlinear mixed integer programmingproblems[J]，Chinese Journal of Enginering Mathematics.2010 27(6),967-974.)   
[23]马永杰，云文霞．遗传算法研究进展[J].计算机应用研究,2012,29 (4):1201-1206,1210.(Ma Yongjie,Yun Wenxia.Research progress of genetic algorithm [J].Application Research of Computers.2012,29 (4): 1201-1206,1210.)   
[24] Lu Yunlomg,Maharjan S,Zhang Yan.Adaptive edge association for wireless digital twin networks in 6g[J].IEEE Internet of Things Journal, 2021,8 (22): 16219-16230.   
[25]陈俊彦，李玥，梁楚欣，等.SDN 多控制器部署及流量均衡研究[J]. 计算机工程与科学,2021,43(5):830-835.(Chen Junyan,LiYue,Liang Chuxin，et al. SDN Multi-controller deployment and traffic load balancing [J]. Computer Science & Technology.2021,43 (5): 830-835.