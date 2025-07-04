# 新一代融合通信协议栈系统

# 王园园 钱蔓藜 石晶林

摘要：在异构网络不断发展的今天，如何融合不同无线接入技术，为用户提供更多样化的业务形式和更好的用户质量体验成了亟待解决的问题。本文从接入层面对新一代融合通信网络中空中接口协议栈系统进行分析，阐述设计过程中的技术难点并提出对应解决方案。最后，提出面向新一代融合通信的协议栈系统架构。

关键词：融合通信 异构网络 空中接口 协议栈

# 1背景

随着第3代移动通信（3G）网络技术在全球范围内开始商用、LTE技术的发展以及后3G时代的到来，越来越多的研究学者和厂商开始认识到，未来的无线网络不可能是像第3代移动通信网络研究之初人们所设想的那样由某一种特别先进的无线技术所组成的单一技术、统一管理的网络，而只能是多种技术、多种网络互相融合所形成的具有多种接入方式、提供多种传输速率和多种服务质量要求的多种业务的异构网络的联合体。

针对未来异构网络多种接入技术融合的特点，大量能够同时支持多种接入技术的多模终端设备进入了商用化阶段，如多模手机、多模PDA²、多模笔记本等，另外，NEMO（NetworkMobilitySupport）也提出了能够支持多种接入技术的，应用在车

![](images/61e8b7c51ad0a8739891825e22a10e5caed2a035a8e13f6578cb86faba7eff89.jpg)  
图1．异构网络融合通信系统

船等交通工具上的无线路由器设备，以满足大量车载用户的移动性和通信服务质量要求。伴随着无线通信技术的发展和无线传输带宽的增加，异构系统与现有通信系统相比，将支持更加多样的业务，而且业务本身的形式也越来越复杂。语音、视频等多媒体实时业务对时延、时延抖动非常敏感，具有更高的服务质量要求，而且在一种应用中往往包含多种具有服务质量（QoS）参数的数据流。以上这些异构网络出现的新特点将极大地丰富人们的生活需求，促进无线产业的发展。但是现有的通用协议栈还无法满足异构无线网络环境下的无缝切换、实时接入、业务流选择等要求，因此研究如何真正利用异构网络融合多种接入技术的特点，为用户提供更多样化的业务形式和更好的用户质量体验，具有十分重要的现实意义。

未来移动通信网络是多接入技术并存、协同工作，支持终端移动性的，可信任有保障的全 $\mathrm { I P ^ { 4 } }$ 的异构融合网络，具有在多种无线接入技术中进行无缝切换和漫游的能力。这对新一代的面向融合的通信协议栈提出了更高的要求。在协议栈的各个层次，异构接入网络都存在网络间差异。网络融合必须解决网络各个层次的差异性问题。当多种接入网共存时，通过统一的承载协议完成各种接入网络之间的信息共享、终端漫游和无线资源协商的联合管理，从而使用户能够享受到异构网络环境下的高速率、高服务质量和高稳定性的服务。

# 2新一代融合通信网络概述

在异构网络不断演化的今天，如何融合不同无线接入技术，为用户提供更多样化的业务形式和更好的用户质量体验成了亟待解决的问题。网络融合涉及到移动通信系统的多个层面，包括业务层面、控制层面、接入层面、传送层面。

在业务层面，手机视频、数字化音乐、手机网游等新业务形式层出不穷，未来这些多样化的业务形式在不同终端上不能互通的瓶颈必将打破，全新的数字化娱乐模式将会得到更快的发展。

在控制层面，会以基于网络层移动性管理等关键技术提供无缝切换和漫游，不同制式网络之间不能互相切换的情形将得到改变，用户可以手持终端在不同的网络间（比如2G/3G/4G）进行无缝切换。通过接入层和非接入层的控制，实现用户移动性和对移动性的自主管理。

在接入层面，将通过联合的无线资源管理和服务质量保障技术来为用户提供业务间的平滑过渡，实现异构网络的融合，以便更有效地利用各种无线网络的资源为用户提供高带宽、高质量的业务。

在传送层面，基于IPv6和下一代互联网等关键技术将保障传输的质量。先进的无线技术使用户得以在移动中享用视频、音乐、上网等服务，想要随时随地移动上网，就必须为每一个移动终端分配一个独立的 IP地址。传统的 IPv4 远远满足不了地址容量的要求，而 IPv6解决了地址规模的问题，并且在安全性、服务质量等方面有了较大的改进，使互联网能承载更多的业务。

在整体技术方面，各种业务可以以IP为基础实现互联互通，从用户驻地网到接入网，再到核心网，整个网络以TCP/IP协议实现统一，各种终端可以实现可靠的连接。IP业务及其相关的标准、技术和基础设施等已经相当成熟而且非常普及，所以融合的移动通信网络将以IP作为统一的接口标准和连接手段，即成为全IP移动通信网。

在此大背景下，在融合的通信网络中，所有网络实体应当运行同样的协议栈，一个基于全IP 异构网络融合的新一代通信协议栈是实现提供融合通信能力产品的关键。在融合不同的处理技术的过程中，协议栈还面临很多挑战，有许多关键问题需要解决。本文将从接入层面，对未来融合通信网络协议栈系统进行详细分析。

# 3 技术挑战及设计思路

新一代面向融合的通信协议栈软件系统设计实现中需要从两大方向考虑：一是协议栈软件的设计与实现；二是与协议栈控制相关算法的设计与实现，从而最大限度体现融合通信技术的优势。设计任务包括：

# 3.1高数据传输速率

针对用户不断增长的通信业务范围和业务速率要求，下一代移动通信系统即4G系统中数据业务比例会大大增加，业务种类可能包括 IP-PCM，VoIP，MPEG4，H.263，交互游戏，互联网接入、电子邮件等多种实时或非实时的业务。在通信设备有限的处理能力限制下，如何进行协议栈的整体架构设计，如何在保证软件系统“高内聚，低耦合”的前提下有效地进行各个功能模块的交互，缩短数据处理时间，是在软件设计阶段需要着重考虑的。

未来通信系统高速数据处理及低时延需求对协议栈系统的工程实现提出了更高要求，无法采用传统的通信协议栈软件系统的复杂设计。软件系统设计应遵循简单、高效和一致的原则。协议栈每一层次功能应使用状态机进行驱动和执行控制以有效地保证整个系统运行的及时性和正确性，且通过有效的接口设计使得硬件能力得到最大程度的利用，从而保证整个协议栈软件系统的高效运行及实时性。在设计时，需要考虑各协议层次协同处理，以提高系统数据处理效率。为此需采用以下方法：

# 3.1.1优化数据结构

在不同协议层处理过程中，将各层所共用的信息（如LTE 中的无线承载、逻辑信道信息等)存储在核心数据结构中，提供统一的存取接口管理这些信息，减少系统数据索引时间。

# 3.1.2精简线程模型

未来通信协议栈对数据处理时间的严格要求（如LTE 系统上行需要在1ms 的时间内完成数据调度）需要不同协议层次在数据处理过程中有一定程度的并行执行，但并行处理过程中不同线程间的切换会增加系统处理开销。因此，在系统设计过程中需要考虑二者的平衡，通过精简的线程模型，提高数据处理效率。

# 3.1.3减少数据拷贝

在工程实现上，IP数据包在协议栈不同协议层处理过程中的多次拷贝将增加系统处理开销，增加数据处理时延。因此，IP数据包在协议栈不同协议层处理过程中，可以采用纯指针操作或者其他多种不同的索引方式，使得数据处理过程中不进行拷贝或者仅进行一次拷贝，从而有效降低系统数据处理开销，减小数据处理时延。

上述方法的综合应用可以从整体上优化空中接口部分协议处理过程，提高系统反应速度，从而满足未来高层协议栈软件系统对数据处理的高性能需求。

# 3.2系统灵活可移植性

在通信软件技术快速发展的今天，协议栈软件研发呈现出组件化、专业化的发展趋势。不同通信设备制造商将根据"关注点"的不同进行专业化分工，研发不同的"零部件”，在不同的市场需求及设计理念的驱动下，选择使用不同的协议栈组件、不同的实时系统、不同的硬件平台等，通过零部件的组装形成各种高性能的通信设备。如何设计一套灵活的、易移植的协议栈软件系统，减少高层协议栈软件对操作系统、物理层实现及硬件平台的依赖，在保证系统性能的同时，缩减系统集成以及升级过程的投入，在未来通信设备研发过程中将显得越来越重要。本文在对现有通信协议栈（如TD-SCDMA,WiMAX,3GPPLTE等）深入分析的基础上，主要从以下几个方面对未来融合通信协议栈系统的灵活性和易移植性需求进行分析。

# 3.2.1灵活性

# 1．核心数据库

为了实现灵活性，通信协议栈软件需要使用核心数据库存储不同协议层的所有重要信息，包括业务管理信息、收发的协议数据单元、统计信息等。它是系统各个功能模通信的重要桥梁。同时，我们在核心数据库之上建立了一套“信息共享、多级索引、交叉访问"的灵活数据组织方式，在保存一份数据的前提下，根据不同的功能需求建立特定的索引方式，在节省嵌入式系统存储空间的前提下达到快速准确索引。

# 2. 动态算法库

为了方便在系统集成和开发升级过程中添加新的功能或者进行核心算法替换，增强系统的灵活性和可扩展性，需要定义一套动态算法库接口和算法库实现，通过低耦合的方式将系统的核心算法及关键机制封装在动态算法库中。在系统升级的过程中，只需要按照库接口设计并替换算法库中原有实现，便能在协议栈软件系统中对该算法进行评估验证，而无需了解协议栈软件其它部分的实现细节。

# 3.2.2易移植性

为了提高协议栈软件系统的可移植性，可通过操作系统抽象层和物理平台管理子系统将协议栈软件中的调度子系统、数据收发子系统等核心部分独立于特定操作系统、物理层实现和硬件平台。如图2所示。

协议栈软件 操作系统抽象层 Linux任务 0 操作系统1  
物理层管理子系统 软件封装器同步器  
物理平台1 物理平台2 内存直接访存 1 操作系统2 VxWorks软件封装器  
适配器 适配器 流水线 1 操作系统n 其他： ↑ 软件封装器 操作系统物理平台1特定 物理平台2特定 物理平台3特定应用程序接口 应用程序接口 应用程序接口物理平台1 物理平台2 物理平台3

# 1．操作系统抽象层

操作系统抽象层采用不同的操作系统封装器屏蔽操

作系统特定数据结构和函数接口，使通信协议栈核心部分可以透明地访问操作系统的接口。只要在操作系统抽象层中封装目标操作系统的特定操作，高层协议栈软件就能够很容易地移植到该操作系统上。同时，通信协议栈可针对不同操作系统特性分别进行优化，提高协议栈软件在该操作系统上运行的性能。

# 2．物理平台管理子系统

物理平台管理子系统使用物理层适配器屏蔽底层硬件平台和物理层实现的细节，使高层通信协议栈核心部分能透明地使用硬件平台和物理层所提供的服务。只要在该子系统中封装目标物理平台的服务接口，高层协议栈软件就能够容易地移植到该硬件平台或物理层实体上。同时，针对不同的物理层适配器，高层协议栈可根据硬件平台和物理层特性进行数据通信机制、同步机制、原语交互等优化，在保证系统可移植性的同时提高系统的数据吞吐量。

# 3.3智能无线资源管理算法

在任何的协议栈系统中，无线资源管理都是空中接口协议的重要组成部分，直接影响到整个系统的性能及资源利用效率。融合移动通信系统中，由于移动用户数量的急剧增加、用户不断增长的通信业务范围和业务速率要求，数据业务比例会大大增加，也对协议栈软件提出了更高的数据处理要求。如何进行无线资源的管理，更好地实现不同的通信接入技术的融合，高效地利用有限的通信资源，在此基础上保证多业务服务质量、提升用户体验，是融合通信协议栈中最主要和最需要研究的问题。

针对日益增长的移动用户数量以及高速业务需求，未来通信协议栈需要提供更高的频谱效率与系统容量。新一代融合通信协议栈中的无线资源管理算法需要能够根据当前小区状态动态分配频谱资源、调整系统参数、协调不同网络间以及同一网络中不同小区间的资源分配，从而在已有无线资源条件下为用户提供最优服务。

# 3.4绿色无线通信网络

近年来，移动互联网流量和无线空中接口资源间的增长差距日益明显。有数据显示，目前移动互联网流量的年度复合增长率在 $13 1 \%$ ，而空中接口资源的年度复合增长仅为 $5 5 \%$ 。为此，中国移动基站数量不断增长，目前总数已达50万。但由此带来的负面效应是，电力消耗近5年内翻番，仅2009年的电力成本消耗就超过100亿元人民币。信息和通信技术产业已成为能源消耗的大户，占据了全球能源消耗的 $2 \% - 6 \%$ ，且该比重近几年增长迅速。因此，如何降低功耗成为未来通信协议栈系统首先要解决的问题。

融合通信提出的一个重要意义在于提供更绿色的通信服务，实现节能减排的目标，在减少电磁干扰和辐射污染的同时，能够提供更好的无线通信服务和应用，保障移动通信产业的可持续发展。与之前通信系统关注于物理层降低能耗技术研究相比，在融合通信系统中，采用合适机制在完成通信功能时实现最大限度的能量控制，是值得关注的问题。

# 4新一代融合通信协议栈体系架构

融合通信系统中，融合的协议栈软件系统需要在包容异构性的基础上发挥各个无线接入技术的优势，实现不同网络资源的协同配置和高效利用，以支持新兴的现代服务业应用。协议栈系统设计采用开放的分层式架构。不同协议层次实现不同的功能，不同的移动通信设备在同一个协议层次可以使用不同的功能实体执行不同的功能。图 3给出了融合通信协议栈的基本架构。为适应新一代通信高速数据处理的需求及多种通信接入技术并存所带来的控制多样性及复杂性要求，协议栈设计的数据处理功能与控制功能分离。数据处理功能的整个分层架构自底向上由网络通信能

语音 视频 网络电视 会议传输层网络层  
F 连接管理 QoS管理 联合无线资源管理移动性管理 安全认证  
网络通信能力层 链路1 链路1 链路1 链路1MAC1 MAC1 MAC1 MAC1操作系统适配层Linux、VxWorks、Nuceus物理平台1 物理平台1 物理平台1 物理平台1

力层、网络通信驱动层、网络层、传输层、应用层组成。协议栈内部采用高内聚、松耦合的模块化设计。控制平面的功能需要使用多层次的信息来执行。

网络通信能力层是融合协议栈的最底层，体现了移动设备对不同通信网络接入能力的多样性。该层融合了多种接入技术的物理层、数据链路层及媒体接入层，可以为高层数据传输提供更好的服务，使得移动设备可以接入到多个通信网络。网络通信能力层保持不同通信接入技术运行的独立性，以根据业务的需求提供不同的服务级别，根据网络的使用情况提供负载均衡的服务。

网络通信驱动层作为上层协议与下层具体接入技术之间的通信接口，提供数据包一点对多点的传输，是融合通信协议栈中最具复杂性的功能层次。网络通信驱动层对底层不同的接入技术进行开放、统一的标准化封装，为上层提供统一的接口，根据不同网络的业务提供能力决定上层网络层使用哪种通信方式发送数据。

联合无线资源管理是网络通信驱动层决策的信息来源。未来无线网络是一种基于全 IP技术的无缝融合异构系统。在融合的通信网络中，IP技术的使用将会给移动通信系统带来非常大的统计复用增益，同时给系统的应用带来更大的灵活性。所有的业务将在一个统一的平台中传输，服务质量特性分布较为分散，这样就使得4G系统的无线资源管理的复杂度大大提高。未来移动通信系统无线资源管理技术需要有革命性的改变：

-服务质量管理未来融合的通信网络需要支持由互联的异构网络承载的具有各种各样服务质量要求的宽带综合业务。服务质量管理应根据不同业务的不同服务质量要求，实现跨越不同通信网络的服务质量保证。

-连接管理融合的通信网络，其异构性主要体现在不同的通信网络接入技术在物理层技术实现上的差异性。因此，连接管理的功能就是根据移动设备业务需求及网络情况使终端选择合适的接入网络进行通信。

-移动管理用户移动性是移动通信网络中的一个典型行为，在融合多种无线接入能力的异构网络环境中，移动管理要保障用户跨越基于不同结构和协议的网络时的业务性能，为用户提供泛在的网络接入服务。

-资源管理融合的网络环境中，需要协同不同网络的资源，对有限的资源进行合理配置。融合的无线资源管理会根据网络资源使用情况进行接入控制、调度、干扰抑制、负载均衡等操作，实现资源共享、性能共赢，保证多种网络的业务传输质量，实现多种通信技术的和谐共存和发展。

# 5 结束语

融合通信是一种将计算机技术与多种通信技术融合为一体，在一个统一的网络化平台提供众多的应用服务的新的通信模式。多技术的发展促进了融合通信的发展。其中，软件技术的发展使得各种通信设备通过软件的变更，最终可以支持各种用户所需的特性、功能和业务。在融合通信时代，通信软件对于通信设备的功能发挥起着至关重要的作用。本文基于对融合通信的研究现状和技术分析，针对融合通信系统中的核心软件——融合通信协议栈，提出了在软件系统开发中的几大关键技术提升点；从软件开发，资源管理等多个方面进行了分析，并给出了相应的解决思路和方法；最后提出了融合通信协议栈的体系架构，使得融合通信协议栈在包容异构性的基础上实现统一、高效的通信服务，以节省开支并充分利用现有的网络资源。

融合通信是对传统通信的一次革新，推动了平台开发的多样化，使新技术、新应用得以迅速、方便地部署，凸显了融合的平台优势。在竞争激烈的融合通信协议栈及产品开发过程中，有多种不同的产品发展方式。为了促进融合通信的发展，针对融合通信业务对网络、终端及接口的要求，需要在多平台多终端的兼容性上展开标准化的研究，以达到不同产品及系统之间的互通，为融合通信提供一个更广阔的平台，提供更好的解决方案，实现融合通信的更迅速的部署和实现。

# 参考文献：

[1] N.Himayat, et al.,“Interference management for 4G cellular standards[WIMAX/LTE UPDATE]," Communications Magazine,IEEE,vol.48,pp.86-92,2010.   
[2] L.Haiyan, et al.,“Quality-driven cross-layer optimized video delivery over LTE,” Communications Magazine,IEEE,vol.48,pp.102-109,2010.   
[3] J.T.Aguiar and L.M. Correia,“A framework for the evaluation of converged mobile and wireless communication systems,”in Personal, Indoor and Mobile Radio Communications,2O04.PIMRC 2004. $1 5 ^ { \mathrm { t h } }$ IEEE International Symposium on,2004, pp.752-756 Vol.2.   
[4] CTI 论坛，融合通信专栏，http://www.ctiforum.com/train/intel/intel.htm   
[5] Klaus Ingemann Pedersen, et al,“An overview of downlink radio resource management for UTRAN Long-Term Evolution",Communications Magazine, IEEE,vol. 47, pp.86-93,2009.   
[6] May El Barachi,et,al.“The design and implementation of architectural components for the integration of the IP multimedia subsystem and wireless sensor networks”. Communications Magazine,IEEE,vol.48,pp.梁朝霞，王发光，凌颖，“融合通信关键业务及在现网中的应用实 现”，电信科学，2008 年第7期，pp.26-31.   
[7] 凌颖，梁朝霞，“融合通信相关标准进展及其业务实现的关键技术”，电信科学，2008 年第 7 期，pp.7-11.42-50,2010.   
[8] 刘芳，“异构网络中移动性管理关键技术研究”，CNKI:CDMD:2.2010.222181   
[9] 胡杰，“中间件技术在融合通信型设备开发中的应用”，数据通信，2009 年04期，pp.34-36

作者简介：

王园园： 中国科学院计算技术研究所无线通信技术研究中心，博士研究生wangyuanyuan@ict.ac.cn钱蔓藜： 中国科学院计算技术研究所无线通信技术研究中心，博士研究生石晶林： 中国科学院计算技术研究所无线通信技术研究中心，博士，研究员