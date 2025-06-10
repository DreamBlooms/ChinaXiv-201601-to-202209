# 网络模拟研究概述

# 郝志宇

摘要：本文首先介绍了网络模拟在网络行为研究方面的重要意义以及目前网络模拟研究工作面临的难题。然后重点介绍了网络模拟研究工作中最重要的两个研究方向：路由策略和流量模型抽象技术，分别介绍了其研究内容以及国内外最新研究进展。最后总结并展望了网络模拟研究工作的可能发展方向。

关键词：网络模拟；路由策略；流量模型抽象

# 1引言

互联网作为人类社会信息化标志，已经深入到社会生活的各个领域，成为极具战略意义的基础设施。对大规模网络环境进行研究，是了解网络的必然过程，是在更高层次上保障互联网稳定良好运行的基础。目前研究互联网的方法主要包括数学模型分析、网络测量、网络模拟、网络仿真、原型实验平台、实际网络测试等[1,2.3]。文献[3]分析了各种方法的优缺点，指出：数学模型分析方法的优点是灵活并且成本低，但有可能会由于建立的模型过于简化从而导致分析得到的结果不正确；网络测量所使用的测量方法难以做到十全十美，会导致测量结果不正确；实际网络测试由于实验环境不可控，实验不可重复，同时存在很大的风险，因此很少被采用；原型实验平台可以获得更实际的结果，但是成本高，运用不便，并不适用于大规模网络行为的研究，同时，该方法的实验可重复性差；网络仿真建立的模型抽象度较低，可以获得较高的真实性，但所能研究的网络规模小，为了能够与实际网络交互，网络仿真速度必须达到实际网络运行速度，因此仿真的规模受到限制。

文献[3]还指出：网络模拟是在对网络的行为特征进行抽象的基础上建立简化的模型（包括协议模型、流量模型、拓扑模型等)，特点在于：能够细致地刻画网络运行情况，具有很高的真实性；能够研究具有上万节点规模的网络，可对较大规模网络进行研究；模拟工具本身使用方便、运行成本低。

表1．各种互联网研究方法比较  

<html><body><table><tr><td></td><td>真实性</td><td>规模</td><td>成本</td></tr><tr><td>数学模型分析</td><td>低</td><td>高</td><td>低</td></tr><tr><td>网络测量</td><td>中</td><td>高</td><td>中</td></tr><tr><td>网络模拟</td><td>偏高</td><td>高</td><td>低</td></tr><tr><td>网络仿真</td><td>偏高</td><td>低</td><td>中</td></tr><tr><td>原型实验平台</td><td>高</td><td>低</td><td>高</td></tr><tr><td>实际网络测试</td><td>高</td><td>高</td><td>极高</td></tr></table></body></html>

表1进行了6种互联网研究方法在真实性、规模、成本等方面的比较。可以看出，各种方法实际上是这三个方面的折衷[3]。

由于网络模拟成本较低，实现简单，使用方便，具有一定的真实性，能用于研究尚未实施的网络机制，并能保证研究所需的规模，因此被广泛应用于网络研究的每一个角落一一业已成为测试网络协议、分析网络行为、维护网络的正常运行，以

表2.模拟方法在国际顶级会议上的应用比例  

<html><body><table><tr><td></td><td>1985-1989</td><td>2004</td><td>2004</td></tr><tr><td>SIGCOMM</td><td>13.8%</td><td>50%</td><td>36.7%</td></tr><tr><td>INFOCOM</td><td>10%</td><td>60%</td><td>二</td></tr></table></body></html>

及设计网络架构、评价新型网络机制的主要手段。文献[1]对网络研究领域的顶级会议SIGCOMM和INFOCOM中的文章进行统计的结果（表2所示）表明，模拟方法已成为一种互联网行为研究领域广泛应用的基础研究工具，被广泛应用于互联网行为研究的方方面面一一协议设计与分析验网证、络安全、网络行为预测、网络规划建设等。

# 2 网络模拟研究面临的问题

鉴于网络模拟在网络行为研究领域的重大应用价值，对网络模拟技术本身的研究也受到了研究者的广泛关注。研究人员致力于提高网络模拟工具的模拟规模、模拟结果的真实性、降低模拟过程中的计算开销和存储开销，以进一步降低网络模拟的开发和运行成本，提高应用价值。

然而，互联网与生俱来的复杂性、异构性、动态性以及庞大的规模都给网络模拟研究工作带来了巨大挑战。首先，作为整个网络体系结构核心的IP协议的目的是无缝地互连不同的网络技术和管理域。它对用户提供了一致的虚拟连接，使用户不必关心网络连通的细节。但网络的复杂性并非就此消失，底层网络大量不一致的行为，导致我们对网络分析和对其行为的理解存在着一定的困难。

其次，网络的变化非常快。这包括两方面：一是网络异构性和动态特性，如拓扑的变化、链路的多样、路由的动态特性、协议的复杂性等，使得对网络的建模和模拟变得十分困难。二是网络的应用发生变化，导致了流量模式的变化：从早期的电子邮件（Email)，文件传输(FTP)，到现在的万维网服务（WWW)，多媒体流等。另外，网络应用存在“灾难式成功"（Success Disaster）现象，即一种应用或协议可能在设计和实现方法还没有完善就在网络上广泛地应用了（如HTTP)，这也增加了网络模拟的困难。

最后，现今网络规模巨大。这又带来了两个问题：一是网络主机数目的增长异常迅速，近年来互联网主机数保持了高增长速度，互联网数据量则几乎保持了指数增长。对如此大量的网络对象进行模拟无疑是非常困难的；二是网络的扩展性。有的网络协议和机制在小规模的网络上运行良好，但当网络规模扩展到一定程度时就变得低效甚至不可用。

互联网的这些特点给网络模拟研究工作带来了模拟规模、模拟效率，以及模拟真实性等方面的困难。

从性能角度来说，网络模拟器面临着两个难题一一模拟规模和模拟效率。随着互联网的迅猛发展，网络的规模越来越大，对互联网模拟的要求越来越高；另一方面，由于硬件资源尤其是内存资源的限制，网络模拟器所能够模拟的网络规模有限，无法适应互联网模拟的要求；而网络规模的不断增大和网络行为的日益复杂多样，模拟性能低下也成为限制网络模拟器实际应用的瓶颈之一。根据文献[7]中的估算结果，对于一个 $\mathsf { 1 } \times \mathsf { 1 0 } ^ { \mathsf { 8 } }$ 个节点规模的网络来说，传统的数据包级离散事件模拟器（如NS-2）需要模拟的事件数约为 $2 . 9 \times 1 0 ^ { 1 1 }$ ，以每秒处理1,000.000个事件的处理能力，模拟网络一秒钟的运行 需要模拟器运行时间约为4天；保存模拟过程所必需的节点、链路、数据包等信息所需要的内存空间约为 $2 . 9 \times 1 0 ^ { 1 4 } \mathrm { B }$ （约3TB)；如果需要对网络行为模拟过程进行记录，保存1秒钟的网络行为所需要的存储空间约为 $1 . 4 \times 1 0 ^ { 1 3 } { \mathrm { B } }$ 。截至目前，根据相关资料和文献，已知的大规模网络模拟器只能够模拟最大 ${ 1 0 } ^ { 6 }$ 量级的节点规模，而且以拓扑连接关系和所模拟的应用均极为简单为前提。

从功能角度来说，网络模拟器应该能够足够真实地模拟出所要模拟的网络拓扑上的各种网络行为。比如各种协议，安全事件等，以满足对网络行为进行分析研究的应用需求。

从模拟真实性角度来说，互联网的异构性和动态性对网络模拟的真实性提出了巨大挑战。如何才能够抓住互联网的核心的、不变的特征，忽略次要属性，以建立正确的互联网模

拟模型也是网络模拟技术的关键。

# 3 国内外主要研究团队和项目

国外网络模拟技术的研究工作开始于二十世纪九十年代，目前具有代表性的科研组织机构和项目主要包括：

(1）由南加州大学/信息科学研究所（University of South California/Information ScienceInstitute,USC/ISI)、施乐帕克研究中心（XeroxPARC）、劳伦斯伯克利国家实验室（LBNL）和加州大学伯克利分校等美国大学和实验室合作，由美国国防部高等研究计划局（DARPA）资助的VINT(Virtual InterNet Tested)项目[8]。网络模拟研究领域最著名的 NS-2[9即出自该项目。  
(2）美国伊利诺大学香槟分校（UIUC）的戴维.尼克尔（DavidNicol）教授主持的安全和系统建模（MOUSE）课题组，是网络模拟方面的领军团队，开发了iSSF 模拟器[10]，在网络安全行为建模和模拟、网络流量建模、实时互联网行为模拟等方面研究成果卓著；  
(3) 佐治亚理工学院（GaTech）的藤本（Fujimoto）和瑞利（Riley）教授领导的团队，开发了PDNS[和GTNetS[12]并行网络模拟器。在网络模拟路由策略和模拟并行化技术方面研究深入。  
(4） 佛罗里达国际大学（FIU）的詹森.刘（音译，JasonLiu）领导的课题组，是上文（2）中所提项目的一个分支，但在流量模型抽象方面研究十分深入，目前已成为该方向的顶尖研究力量。  
(5）韩国电子通信研究院（ETRI）的金榮善（译音，Young SunKim）领导的网络研究项目组采用 SSFNet模拟器对互联网进行深入研究，并在多个国际会议、期刊上发表文章[13]。  
(6) 台湾国立交通大学的王协源（Shie-Yuan Wang）在 2003 年开发了NCTUns[14]，该模拟器采用对实际网络流量的抽样作为模拟输入，具有极高的真实性，连续在国际顶级会议Mobicom，Infocom 发表文章及受邀进行演示[15-17]。

国内网络模拟方向研究起步较晚，研究基础相对比较薄弱。从公开发表的文献来看，研究力量主要来自中科院计算所、哈尔滨工业大学、西安交通大学等科研机构。他们的工作都是从引入国外经典模拟器（NS-2）和模拟技术开始，逐步深入地开发和形成各自的研究兴趣和方向，并且于近几年来取得了长足的进步，在路由策略、并行化技术等方面达到了国际水平。

# 关键技术研究现状

提升网络模拟规模和性能的技术手段有很多，包括各类模型（拓扑模型、协议模型、流量模型、应用模型）的抽象技术，并行化技术，调度机制等。其中，各类模型的抽象技术是网络模拟技术的关键所在。事实上，模拟技术的本质就是对所模拟事物进行合理抽象，以准确地表述模拟对象。

在网络模拟技术所需的各类模型中，路由模型和流量模型是最为关键的两类，也是受研究人员关注度最高的。这是因为：（1）数据包的路由技术是互联网上各类应用的基础，而路由信息的计算、存储和查找方法，对于网络模拟工具的计算开销和存储开销都具有极大的影响；（2）网络行为通常的表现就是各种应用的数据包在互联网上的不断传输，而正是这些数据流量给网络模拟器带来了极大的模拟事件数量，也就意味着巨大的计算和存储开销。下面将分别介绍这两方面具有代表性的研究成果。

# 4.1路由抽象技术相关研究

# 4.1.1研究内容

随着网络模拟规模需求的不断扩大，路由抽象技术成为了网络模拟研究的关键问题之一。互联网由18.000 以上的自治系统（Autonomous System，AS）组成，每个自治系统通常会包含上百个负责自治系统间路由通讯的路由器节点，以及上千个负责自治系统内部路由的路由器节点。随着网络规模的不断增长，一个互联网服务提供商（ISP）核心路由器节点上的路由表的规模就达到了足以耗尽路由器内存空间的地步。可想而知，当需要保存所有这些路由器节点的全部路由信息，以完成互联网的行为模拟时，会对模拟器的存储空间提出多么严峻的考验。而在如此庞大的路由状态信息数据中，计算和查找模拟应用所需要的路由信息也将对处理器计算资源提出巨大挑战。

同时，路由模拟的真实性也是研究的重点内容之一。如果路由模拟与实际网络环境中的路由过程差异很大，则对网络行为模拟过程产生的流量、拥塞、丢包等模拟结果都将失去意义，从而严重影响网络行为模拟的可信性。研究具有高性能、高真实性的网络模拟路由抽象技术，是网络模拟研究领域的关注热点之一。

# 4.1.2相关研究进展

根据模拟器对动态路由是否存在需求，路由抽象技术可以分为静态路由模拟技术和动态路由模拟技术。前者是针对静态路由的处理，即在假设拓扑信息在全部模拟过程中是不变的前提下，研究如何完成单个模拟节点上以及各个模拟节点之间的路由计算，存储和查找策略。而后者是针对网络拓扑结构的动态性，研究如何真实地模拟拓扑信息变化带来的路由信息的变化。下面将分别介绍这两方面的相关研究进展。

# (1) 静态路由模拟技术

静态路由模拟技术是目前的研究工作重点。针对本地静态路由策略研究，当前模拟器大多采用集中计算并存储全局静态路由表的路由策略(Flat 策略)。该方法在模拟器初始化过程中根据全局拓扑连接关系计算全局路由表，并将其保存在内存中。在模拟数据包的路由过程时查找静态路由表，进行数据包的路由。该方法由于需要保存静态路由表，存储空间需求很大。对节点规模为 $\pmb { n }$ 的网络拓扑来说，空间复杂度为 $O ( n ^ { 2 } )$ ；而在查找路由时，根据源,目的节点地址信息，在 $ { \boldsymbol { o } } ( 1 )$ 时间内即可得到所需路由信息，路由查找时间最小。

黄（音译，Huang）等在文献[18]中提出了一种近似路由的计算和查找策略，用一棵最小生成树作为路由表，认为所有的路由信息都保存在这棵最小生成树上。该方法路由表所占用空间为 ${ \pmb O } ( { \pmb n } )$ ，而查找时间复杂度为 $\scriptstyle O ( \ln ( n ) )$ ，在存储空间和查找时间的平衡上效果很好;但由于一棵最小生成树所能覆盖的最短路径有限，因此只是一种近似路由策略。

廣森（Hiromori）等在文献[19]中提出了由一棵最小生成树结合一张部分静态路由表来保存路由信息的方法（称为 STree_Flat方法)。该方法采用一棵最小生成树来保存部分路由信息，而对不能被该树包含的最短路径路由信息则保存在一张静态路由表中。在查找路由时首先查找静态路由表，找到则使用该路由信息进行路由，否则就在最小生成树上查找。STree_Flat方法的时间和空间复杂度视最小生成树能够覆盖的最短路径路由信息数量一一即最小生成树的最短路径覆盖率(coverage percentage)一一而定。假设最小生成树的最短路径覆盖率为 $\pmb { p }$ ，则 STree_Flat方法所需内存空间为 $O ( n + ( 1 - p ) \times n ^ { 2 } )$ ；但在查找静态路由表时，必须遍历静态路由表，因而其最坏查找时间为 $\pmb { O } ( \ln ( \pmb { n } ) + ( 1 - \pmb { p } ) \times \pmb { n } ^ { 2 } )$ 。该方法在保证查询路由信息准确的前提下节省了大量空间，但由于部分路由表的遍历时间复杂度很高，查找时间的剧增，综合效果较差。

陈（音译，Chen）等在文献[20]中提出了以多棵最小生成树结合一张静态路由表来保存路由信息的方法（称为MTree_Flat方法)。采用多棵最小生成树来保存路由信息，从而提高了生成树的最短路径覆盖率，进一步节省存储空间。在查找路由时，仍然是先查找静态路由表部分，若找到则直接进行路由，否则就说明该路径被某一棵最小生成树覆盖，于是逐棵查找最小生成树上的路由信息，选择其中最短的路径作为路由信息返回，供数据包路由使用。该方法的时间和空间复杂度仍然由最小生成树的覆盖率决定。假设使用了 $\pmb { k }$ 棵最小生成树，覆盖率为 $\pmb { p }$ ，则其空间复杂度为 $O ( k n + ( 1 - p ) \times n ^ { 2 } )$ 。而查找路由所需时间最坏为$O ( k \times \ln ( { \pmb n } ) + ( 1 - { \pmb p } ) \times { \pmb n } ^ { 2 } )$ 。由于采用了多棵生成树，最短路径覆盖率必然比相同拓扑条件下的一棵最小生成树大得多，因此更加节省存储空间。在查找时虽然需要查找全部 $\pmb { k }$ 棵生成树以选择路径最短的路由，但是由于覆盖率高，静态路由表规模较小，查找静态路由表所需时间也更少，因此综合效果比STree_Flat方法更优。

除了上述预先计算并静态存储路由信息的方法以外，还有一种不保存任何路由信息，而是在模拟过程中实时计算的路由策略。瑞利等提出的 Nix-Vector方法[21,22]就是其中的代表。该方法在模拟初始化过程中不进行任何的路由信息计算和存储工作，而是在数据包生成时，根据源和目的地址信息实时计算路由，并将计算出的路由信息保存在数据包头中，在数据包传输过程中经过每一个路由器节点时，根据数据包头携带的信息解析出该数据包的路由。该方法不需要任何额外的存储空间来保存路由信息，空间复杂度最小。但每次模拟一个新的数据包传输过程都需要遍历全局拓扑以计算路由，其时间复杂度很大，以邻接表方式描述的拓扑结构，查找时间复杂度为 ${ \pmb O } ( { \pmb n } + { \pmb e } )$ ，其中 $\scriptstyle { e }$ 为边的数目。该方法能够有效地处理拓扑变化导致的路由变化，也提出了计算不同节点感知拓扑变化时间的方法，但由于计算和验证Nix-Vector向量引入了大量的额外事件和计算量，同时采用Nix-Vector 策略进行路由计算本身就需要消耗大量的处理器计算时间，因此其模拟效率很低，而且效率低下的问题会随着所模拟网络的规模增大而进一步放大。

基于以上路由策略研究的思想综合考虑，我们在前期的研究工作中提出了多树-邻索引向量技术(MTree_Nix)[23，24]。MTree_Nix 技术采用多棵最小生成树和 Nix-Vector 技术相结合的方法，在路由模拟技术的存储开销和计算开销之间达到了最优的平衡。

# (2) 动态路由模拟技术

互联网的动态性是互联网的基本属性之一。互联网上时刻可能发生的拓扑结构变化都会导致路由状态的动态更新。真实地反映互联网行为属性，就需要更真实的模拟路由状态信息的动态变化过程。这就是动态路由抽象模拟技术的研究内容。动态路由模拟技术的研究方法主要包括两种，动态路由协议模拟以及静态路由表重构。

动态路由协议模拟的研究工作主要是针对边界网关协议（Border Gateway Protocol,BGP）和开放式最短路径优先（Open ShortestPathFirst，OSPF）等动态路由协议的模拟，研究工作相对较多[25-28]。但这些工作的主要目标是对协议本身的研究，并不适用于作为网络

模拟器的基础路由模块来使用。

对路由表的重构是处理动态路由模拟的一种简单而有效的思路。对所有的静态路由策略算法都可以在发生了拓扑连接关系变化时进行路由表的重构，但由于采用的是集中存放的路由表，因此当拓扑变化发生以后，路由表的更新对所有节点来说都是同时完成的，这就严重损害了模拟的真实性。为解决这一问题，瑞利等提出了一种动态路由模拟的方法，在拓扑信息变化时对保存在缓存中的 Nix 向量进行验证，以确定其是否还能够满足最短路径的要求[29]。该方法能够有效地处理拓扑变化导致的路由变化，也提出了计算不同节点感知拓扑变化时间的方法。但由于计算和验证Nix-Vector向量引入了大量的额外事件和计算量，同时采用 Nix-Vector策略进行路由计算本身就需要消耗大量的处理器计算时间，因此其模拟效率很低，而且效率低下的问题会随着所模拟网络的规模增大而进一步放大。本课题组在文献[29]工作的基础上，完善了拓扑变化信息更新时间的计算模型，并基于MTree_Nix 技术提出了基于拓扑变化信息更新时间计算模型的动态 MTree_Nix 技术[30]，进一步降低了动态路由模拟技术的计算开销和存储开销，是已公开发表的最优化动态路由模拟技术。

# (3) 小结

从路由抽象模拟技术的研究现状来看，问题主要存在于动态路由模拟技术上。一方面，拓扑和路由的动态变化作为互联网的一个重要属性，为模拟动态路由提出了极为迫切的需求；另一方面，动态变化的拓扑和路由信息带给模拟器的是急剧增加的计算和存储开销，使得本就效率较低的网络模拟器面临更加严重的计算资源和存储资源竞争，更难以满足实时模拟的应用需求。根据最新实验结果，在采用文献[30]中的动态MTree_Nix技术的网络模拟系统，模拟类似蠕虫扩散这样的大规模网络安全事件时，其模拟效率仅为采用静态路由模拟技术时的约1/20，更谈不上满足实时模拟的需求。因此，研究如何降低动态路由模拟技术的计算开销和存储开销，以提高模拟性能，是路由抽象模拟技术研究的当务之急，也是影响网络模拟性能的重要因素。

# 4.2流量模型抽象技术相关研究

# 4.2.1研究内容

互联网上的网络流量由一个个数据包组成。对于离散事件模拟器来说，为了能够准确地描述网络行为，需要对每一个数据包的每一次行为（比如数据包在连接上的入队和出队、数据包被路由器和终端节点的处理等）都作为一个事件来进行模拟，这就是所谓包级别（packet-level）的模拟。目前包括NS-2在内的很多网络模拟器都采用的是基于包级别的模拟。虽然包级别的模拟能够保证较高的真实性，但是由于每一个数据包的每一次行为都需要由单独的事件来描述，这对于网络模拟器的计算开销来说是极大的挑战。为降低计算开销，需要对单个数据包以及由单一数据包组成的网络流量模型进行简化，这就是流量模型抽象技术所要研究的内容。

# 4.2.2相关研究进展

针对流量模型抽象技术，目前多数研究采用的是提高流量模型抽象粒度的方法，即采用所谓“流模拟（fluid-level)”方式。该方法将具有某些相同属性（如源、目的地址等）的数据包抽象为一个流，使用关于模拟时间的分段函数来表示流的关键属性（如丢包率、队列长度等)，在模拟过程中根据需要更新这些属性的值，以此来描述网络特征。通过这种流模拟方式，可以有效地降低单位时间内模拟器需要处理的事件数量，从而提高模拟效率。根据流模拟模型的调度机制不同，目前的研究主要分为两类：基于流的事件驱动模拟方法以及基于

流的时间驱动模拟方法。

基于流的事件驱动模拟方法是当某个数据流大小需要变化时（比如多个数据流汇聚在同一条链路上产生叠加)，就产生一个离散事件，用以触发此数据流相关属性的变化。代表性研究工作包括文献[31-33]等。在数据流变化不剧烈的时候，这种方法能够有效减少模拟所需处理的离散事件数目，降低计算开销；但在数据流变化比较剧烈的情况下，此方法性能受损严重，且易引发波及效应（ripple effect1)，甚至导致需处理的事件数超过数据包级的模拟[32]。

基于流的时间驱动模拟方法是在模拟过程中，模拟时间周期性的向前推进，每次推进一定大小的时间间隔（time-step)。每推进一个时间间隔，就产生一个离散事件。该事件会完成如下三步操作：（1）依靠流量模型产生新的数据流大小；（2）根据新产生的数据流大小以及前一时间周期内网络的状态，计算下一周期开始时的网络状态；（3）计算网络状态对流量模型的反馈并修改流量模型的参数。代表性工作包括文献[34-36]等。基于流的时间驱动模拟方法与基于流的事件驱动模拟相比在模拟效率上具有较大优势，同时在模拟真实性上相应的有一定损失。

另外，针对数据包级和流级模拟的各自优缺点，研究人员又提出了将二者有机地结合起来，根据不同应用需求，采用两者相结合的混合模拟（hybrid simulation）技术进行不同精度的网络行为模拟。例如采用基于流的模拟技术来模拟背景流量，而对于关注度较高的前景流量则采用包级别的模拟技术进行模拟。代表性工作包括文献[37-40]等。

从流量模型抽象技术的研究现状来看，数据包级一流级流量模型混合模拟因其模拟效率和真实性的高效结合而日益成为研究发展的趋势。但目前的研究成果仍然存在着较大的问题，主要体现如下：首先，基于流的模拟技术的两种方法各有优点，但又都存在难以解决的问题。基于流的事件驱动模拟方法很难消除波及效应带来的危害，在最新的研究工作中基本已被放弃；基于流的时间驱动模拟方法在计算性能方面优势较大，是流量模型抽象技术的发展趋势，但在模拟真实性方面存在先天缺陷，并且在时间步长（time step）选取策略上目前缺乏有效的解决方案。其次，在混合模拟技术中，数据包级流量和流级流量的交互技术是难点所在，而目前绝大多数研究中采用的基于流的时间驱动模拟方法，在与数据包级的流量交互时都是将数据包级的流量进行扁平化处理后纳入到基于流的时间驱动模型中，在每个时间步长的终点参与流量模型的更新计算，这就很难保证用户关注的单个数据包属性能够被精确模拟。

# 4.3我们的研究工作

近年来中科院计算所信息安全研究中心一直致力于网络模拟技术方面的研究，已经积累了深厚的技术储备。中心骨干研究人员近年来作为核心成员先后参与了多项网络行为模拟相关的国家级重点项目，主要包括：（1）国家973计划项目“虚拟计算环境实验床与仿真平台”，（2）国家863-917专项“分布式网络模拟技术”，（3）国家863计划重点项目“高性能大规模网络行为模拟系统”。针对该领域已发表10余篇高水平学术论文，在路由抽象技术、模拟并行化技术、流量模型抽象技术等方面进行了深入研究，积累了大量的特色技术、研究方法和实用工具。

基于以上工作积累，课题组于2010 年申请到流量模型抽象技术相关的国家自然基金项目“基于抽象流量模型的高性能网络模拟技术研究”。该项目针对4.2节中介绍的当前流量模型抽象技术研究工作的缺点，研究具有更高模拟性能和模拟真实性的流量模型抽象技术。

目前该项目研究工作正在进展中。

# 5 总结

网络模拟作为研究互联网行为属性的有效基础工具，日益受到科研工作者的重视。对网络模拟的研究也成为目前的研究热点之一。本文从网络模拟研究的两个重要方向：路由策略和流量模型抽象进行了深入介绍，分析了当前研究工作的进展情况，存在的主要问题以及可能的改进方向。

展望未来的网络模拟研究发展，除了本文详细介绍的路由策略和流量模型抽象技术以外，网络模拟的并行化技术、协议模型抽象技术等也将成为研究的热点方向。另外，随着计算和存储资源性能的日益提升，基于虚拟化技术的网络仿真技术与网络模拟技术相结合，形成具有多层次抽象粒度，兼具高性能与高真实性的网络实时模拟一仿真环境，也将称为未来网络行为研究工具的发展方向。

# 参考文献：

[1] Ammar M.Why we still don't know how to simulate networks.In Proceedings of 13th International Symposium on Modeling， Analysis， and Simulation of Computer and Telecommunication Systems(MASCOTS'05),Atlanta,GA,USA,2005:179\~182   
[2] 雷擎,王行刚.计算机网络模拟方法与工具．通信学报.2001,22(9):84-90   
[3] 王晓锋．提高大规模离散事件网络模拟性能方法的研究．哈尔滨工业大学博士学位论文. 2007,10.   
[4] Xia H.，Dail H., Casanova H.,et.al. The MicroGrid: Using Emulation to Predict Application Performance in Diverse Grid Network Environments.In Proceedings of the13th IEEE International Symposium on High-Performance Distributed Computing,Honolulu,Hawaii,2Oo4:52\~63.   
[5] Vahdat A., Yocum K., Walsh K., et.al. Scalability and Accuracy in a Large-scale Network Emulator. In Proceedings of the Fifth Symposium on Operating System Design and Implementation (OSDI 02), Boston,MA,2002:271\~284.   
[6] Chun B., Culler D.,Roscoe T.,et.al.Planetlab:an Overlay Testbed for Broad-coverage Services. ACM Computer Communications Review.2003,33(3):3\~12.   
[7] Riley G and Ammar M. Simulating Large Networks - How Big is Big Enough?. In Proceedings of the First International Conference on Grand Challenges for Modeling and Simulation,San Antonio, TX,2002:28\~31.   
[8] The VINTProject,http://www.isi.edu/nsnam/vint/, network simulator.   
[9] McCanne R.and Floyd S.The LBNL network simulator. Lawrence Berkeley Laboratory,1997.   
[10] Nicol D.，Liu J.，Liljenstam M.，et.al. Simulation of Large-scale Networks Using SSF. In Proceedings ofthe 2003 Winter Simulation Conference(WSC'03).New Orleans,LA,2003:650\~657.   
[11] Riley G.，Fujimoto R.，and Ammar M.A Generic Framework for Parallelization of Network Simulations. In Proceedings of Seventh International Symposium on Modeling，Analysis and Simulation of Computer and Telecommunication Systems (MASCOTS'99), October 1999.   
[12] Riley G. The Georgia Tech Network Simulator. In Proceedings of the ACM SIGCOMM workshop on Models,methods and tools for reproducible network research,ACMPress,20o3,5-12.   
[13] Yoon S.and Kim Y.A Design of Network Simulation Environment Using SSFNet.First International Conference on Advances in System Simulation,2oo9,73-78.   
[14] NCUTns. http://nsl.csie.nctu.edu.tw/nctuns.html   
[15] Wang S.and Chou C. NCTUns Tool for Wireless Vehicular Communication Network Researches. Simulation Modelling Practice and Theory.2009,17(7):1211-1226.   
[16] Wang S.and Kung H.A Simple Methodology for Constructing Extensible and High-Fidelity TCP/IP Network Simulators. IEEE INFOCOM'99,New York, USA,March 1999   
[17] Wang S.and Kung H. A New Methodology for Easily Constructing Extensible and High-Fidelity TCP/IP Network Simulators. Computer Networks. 2002,40(2): 257-278.   
[18] Huang P. and Heidemann J. Minimizing routing state for light-weight network simulation. In Proceedings of the IEEE International Symposium on Modeling，Analysis and Simulation of Computer and Telecommunication Systems(MASCOTs'O1), August 2001.   
[19] Hiromori A.，Yamaguchi H.，Yasumoto K.，et.al. Reducing the Size of Routing Tables for Large-scale Network Simulation. In Proceedings of the IEEE International Symposium on Modeling, Analysis and Simulation of Computer and Telecommunication Systems(MASCOTS'O3)， October 2003.   
[20] Chen J.,Gupta D.，Vishwanath K.，et.al. Routing in an Internet-Scale Network Emulator. In Proceedings of the IEEE International Symposium on Modeling， Analysis and Simulation of Computer and Telecommunication Systems(MASCOTS'04), October 2004.   
[21] Riley G,Ammar M. and Zegura E.. Effcient routing with Nix-Vectors. In Proceedings of IEEE Workshop on High Performance Switching and Routing(HPSR 'O1),2001.   
[22] Riley G., Fujimoto R. and Ammar M.. Stateless routing in network simulations. In Proceedings of the 8th International Symposium on Modeling，Analysis and Simulation of Computer and Telecommunication Systems(MASCOTS'0O),, May 2000.   
[23] Hao Z.，Yun X. and Zhang H. An Eficient Routing Mechanism in Network Simulation. In Proceedings of the 20th ACM/IEEE/SCS Workshop on Principles of Advanced and Distributed Simulation (PADs'06), May 2006.   
[24] Hao Z., Yun X. and Zhang H. An Efficient Routing Mechanism in Network Simulation. Simulation: Transactions of the Society for Modeling and Simulation International,2008,84(10-11):511-520.   
[25] Dimitropoulos X.Measuring and Modeling Internet Routing for Realistic Simulations. Georgia Institute of Technology,Ph. D. dissertation, 2006.   
[26] Liljenstam M.and Nicol D. On-demand computation of policy based routes for large-scale network simulation. In Proceedings of the 2004 Winter Simulation Conference (WSC'04),2004.   
[27] Hao F.and Koppol P.. An Internet scale simulation setup for BGP. Computer Communication Review,2003,33(3):43-57.   
[28] Yaun G., Bauer D., Bhutada H., et. al. Large-Scale Network Simulation Techniques: Examples of TCP and OSPF Models. ACM SIGCOMM Computer Communications Review, 2003.   
[29] Riley G. and Reddy D.. Simulating Realistic Packet Routing Without Routing Protocols.In Proceedings of the Workshop on Principles of Advanced and Distributed Simulation (PADS'05), 2005.   
[30] 郝志宇,翟健宏,云晓春,张宏莉．动态路由模拟策略研究．通信学报,2007,28(12):19-24.   
[31] Kumaran K.and Mitra D.. Performance and Fluid Simulations of a Novel Shared Buffer Management System. ACM Transactions on Modeling and Computer Simulation. 20o1,11(1):43\~75.   
[32] Nicol D. and Yan G. Discrete event fluid modeling of background TCP traffic. ACM Transactions on Modeling and Computer Simulation,14:1-39, July 2004.   
[33] Cole R., Riley G., Cansever D.,et.al. Stochastic process models for packet/analytic-based network simulations. In Proceedings of the Workshop on Principles of Advanced and Distributed Simulation (PADS'08), 2008.   
[34] Liu Y.,Presti F.,Misra V.,et.al. Scalable fluid models and simulations for large-scale IP networks. ACM Transactions on Modeling and Computer Simulation,Aug.2004.   
[35] Nicol D.and Yan G. Simulation of network traffic at coarse time-scales. In Proceedings of the Workshop on Principles ofAdvanced and Distributed Simulation (PADS'O5),2005.   
[36] Kumar S., Park S., Iyengar S.,et.al. Time-adaptive numerical simulation for high speed networks. In Proceedings of the International Conference on High Performance Computing，Networking and Communication Systems(HPCNCS'07),2007.   
[37] Liljenstam M.，Liu J.，Nicol D.，et.al.RINSE:the real-time immersive network simulation environment for network security exercises.Simulation: Transactions of the Society for Modeling and Simulation International,2006.   
[38] Liu J. Packet-level integration of fluid tcp models in real-time network simulation. In Proceedings of the 2006 Winter Simulation Conference(WSC'O6),2006.   
[39] Liu J.Parallel simulation of hybrid network traffic models.In Proceedings of the Workshop on PrinciplesofAdvanced and Distributed Simulation(PADS'O7),2007.   
[40] Liu J.and Li Y. On the performance of a hybrid network traffic model. Simulation Modelling Practice and Theory,2008,16(4): 656-669.

# 作者简介：

郝志宇： 中国科学院计算技术研究所信息安全研究中心助理研究员、博士haozhiyu $@$ software.ict.ac.cn