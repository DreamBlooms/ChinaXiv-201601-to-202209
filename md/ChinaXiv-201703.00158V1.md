# 网络拓扑结构知识发现及其应用

以互联网为例

# 张国清

摘要：本文首先说明了网络拓扑结构的定义，指出了发现网络拓扑结构知识的分析方法与传统学科的不同，并以互联网为例，综述了互联网拓扑结构分析的主要结论，并给出了应用互联网拓扑知识的实例，最后从实用性和学科发展两个方面说明了通过网络拓扑结构分析获得新知识的重要意义。

关键词：网络结构、互联网拓扑、拓扑分析、网络科学

# 1引言

在自然界和人类社会中存在各种各样的网络，像作为基础设施的铁路、公路、航空等各种交通网、电力网，近年来广泛应用的技术网络万维网（WWW）、对等传输（P2P）网络、互联网等。一个典型的网络由许多节点和连接节点的边组成，通常，节点代表真实世界中的个体或组织，而它们间的关系用边来表示。例如，在互联网中，可以用点来表示自治系统（Autonomous System，AS)，边来表示其间的连接关系，即形成自治系统级的网络拓扑；如果把互联网中的路由器看成节点，而路由器间的连接关系看成边，这样就形成了路由器级的互联网拓扑。

数学家和物理学家在研究网络的时候，为了抓住本质，通常进行一定的抽象，表现在既不关心节点的特定物理位置、大小，也不在意边的长短、曲直、相交与否，只关心节点和节点间是否相连。例如，欧拉在解决哥尼斯堡七桥问题的时候，虽然当时（1736年）讨论长短大小的几何学是主流，而不考虑长短大小、不牵涉量计算的情形几乎没人研究，但他却撇开研究对象的长短、大小、面积、体积等度量性质和数量关系，把两座小岛和河的两岸分别抽象成四个点，而把七座桥抽象这四个点之间的连线。开创了拓扑研究的先河。当人们把网络抽象成这种不依赖于节点的位置、大小和边的具体形态，所得到的性质就成为网络的拓扑性质，相应的结构称作网络的拓扑结构。

网络结构和功能是网络理论研究的核心内容。其中网络结构通常用网络的统计特征（如度分布、聚集系数、平均最短路径、度—度关联性等）来刻画，网络功能由网络上的动态变化过程来反映。这两者并非相互独立，而是存在必然的本质联系。通常结构决定功能，功能反过来影响网络结构的演化。例如，交通网中不同的结构决定了网络的容量有很大的不同，而交通量的增加也可能引起人们去增加路径，从而影响网络的演化。

# 2大规模复杂网络拓扑结构分析与其它学科的关系

网络拓扑结构知识需要通过拓扑结构分析获得。当前网络科学关心的主要对象是大规模复杂网络，如互联网。而网络拓扑结构分析方法是网络科学的核心内容。从学科角度看，这方面的研究要以传统统计学、图论等学科为基础。因为复杂网络规模巨大，网络结构又具有多样性、动态性、复杂性，必须经过统计处理；而图论提供了简洁精确的方法来描述网络，已成为研究人员的共同语言和必要工具。

但是网络拓扑结构分析方法与传统学科中的方法还是有很大不同。传统的统计学侧重于对属性数据的分析，网络结构的分析方法则通常侧重于对关系数据的分析。属性数据是指节点或一组节点自身拥有的数据。关系数据则是指节点间关系、社团（community）间关系、整体层次、块层次间的关系，是两个或更多节点共同拥有的。关系数据与属性数据是不同的分析对象，其分析方法也有很大的差异。

经典图论的研究对象通常只有几个或几十个节点，数学家们可以对其做精确的网络优化，而复杂网络结构分析方法处理的节点数目常常为数千、数方、数亿、甚至更大规模，因此，需要从不同尺度作抽象。而过分抽象可能导致所得结论与实际情况相差甚远，从而引发各种争论，这就要求研究者需要根据实际情况从不同尺度来看问题。常常可以发现，一个尺度上发现的结论在另个一尺度上并不一定成立。如互联网自治系统级拓扑的度分布满足幂律[1,2]1，而在互联网路由器级拓扑中，由于路由器接口数目的限制，度分布显然不会满足幂律。由于不同学科的研究者看问题的尺度不同，最近就引起了激烈的争论，计算机网络领域的研究人员对网络科学领域的研究结论产生异议就是一例[3]。这好比拿《庖丁解牛》中的庖丁与普通厨师的工作做比较，庖丁是在反复实践的基础上，掌握牛的结构（即事物的规律，现在的说法就是一个“科学问题”)，再去指导实践（“解牛")，而普通厨师则不必做庖丁的工作，只要把牛肉做成牛排、做成菜就可以直接满足用户需要了，更多的是一个“技术问题”。也就是说，两者是两个层面的工作，但都是有益的工作。

网络结构分析在社会网、技术网、生物网的研究和实践中都已发挥了重要作用，互联网就是一个典型的例子。作为一个真实网络，互联网从最初的四个节点，发展成为当今世界的信息基础设施，其应用的深入发展和无处不在的广泛性深刻地改变了人们的工作、生活和学习方式，已成为一个名副其实的具有复杂结构的巨大系统。对互联网拓扑结构研究所蕴含的科学意义和应用价值正受到学术界、应用部门和军事部门的普遍重视。下面主要对互联网拓扑结构分析的成果及其应用作比较详细的说明。

# 3 互联网拓扑结构特征

千差万别的网络都可以通过图来描述，邻接矩阵和邻接表包含了网络的所有信息，是两种传统的图表示方法，但都不能直观地告诉人们给定网络的特征。由于网络规模常常很大且结构复杂，为了刻画网络的性质，需要通过一些概念、统计的特征量和度量方法来直观地表征一个网络的主要结构特点。常用的刻画一个网络特征的指标有：节点度分布、平均路径长度、聚集系数、度——度关联性系数、介数、核数等。近年来，人们通过对互联网拓扑结构的分析，发现了多项互联网的拓扑结构特征：

# (1)．幂律的发现

在互联网拓扑研究中，1999年，法鲁托斯（Faloutsos）等人对美国应用网络研究国家实验室（NLANR，National Lab for Applied Network Research）1997到 1998 年间的三份 BGP²数据以及1995 年的一份 traceroute探测数据进行分析，发现了互联网拓扑中存在四条幂律。论文发表在 SIGCOMM'99 和《计算机通信评论（Computer Communication Review）》[1]上。

这是一个实验结论，所指的幂律是近似幂律。这一结论最重要的是在本质上揭示了节点间的差异，表明与原先占主导地位的随机网络[4根本不同的是，在自治系统级拓扑中，少数节点有大度值，而多数节点的度值小。这个发现引起了广泛的关注，掀起了一股研究热潮。需要特别说明的是，自治系统级拓扑上度分布满足幂律并不意味着互联网在其它尺度（如路由器级拓扑）上也满足幂律。

事实上，我们平常所见的构成互联网底层网络的各种子网常常是星型、树型等结构，并不遵从幂律，但把这些子网互联之后，从宏观的自治系统层面看，就出现了幂律特征，这是一种“涌现”现象。这类似于社会科学领域中人类个体间的相互作用会产生经济制度，神经元间相互作用会产生智力。

# (2)．小世界网络

文献[5]给出了具体的实验数据，说明了互联网自治系统级拓扑有小的平均距离和较大的平均聚集系数，是一个“小世界”4网络。

文献[6]从网络演化的角度看，在 2001年12至2006 年12月期间，互联网自治系统拓扑中节点数目、边的数目翻一番的情况下，平均距离为3.62——3.82，平均聚集系数为0.2420.296，也验证了互联网自治系统级拓扑具有小世界网络的特征。

# (3).同配性与异配性

纽曼（M.E.J.Newman）从节点度的角度考察多种网络的度——度关联性[7,8]，发现互联网自治系统级拓扑的连接存在异配性，即网络中的大度节点倾向于与小度的节点连接。

文献[9]从 $\mathbf { k }$ -shell分解的角度考察多种网络的层次关联性，发现互联网自治系统级拓扑的连接存在层次异配性，即拓扑图按 $\mathbf { k }$ -shell分解后，外层倾向于和内层的连接，而互联网路由器级的拓扑结构呈现层次同配性。作为对比，互联网自治系统拓扑和路由器级拓扑的度一度关联性却均呈现异配性。

# (4)．高度节点间连接呈富人俱乐部结构

文献[10]中指出，在互联网自治系统拓扑中，拥有大量边的少数节点间更倾向于相互连接，并比拟地称之为“富人俱乐部现象”，可以用富人俱乐部连通性系数 $\phi { \left( r / N \right) }$ 来刻画：

$$
\phi \big ( r / N \big ) = \frac { L } { r ( r - 1 ) / 2 }
$$

该系数表示网络中最大的前 $r$ 个度的节点之间，实际存在的边数 $L$ 与这 $\boldsymbol { r }$ 个节点之间可能存在的最多连接边数 $r ( r - 1 ) / 2$ 的比值。如果 $\phi ( r / N ) = 1$ ，说明最大的前 $r$ 个度的节点组成的网络为一个完全连通的子图。

该文作者对互联网自治系统拓扑与一些常见的网络模型的富人俱乐部系数作了比较，在自治系统图中极小比例的高度节点有大的连接数，而且其富人俱乐部系数大于常见的网络模型的富人俱乐部系数。作者还在按度值大小排列的基础上将所有节点划分为20等份，比较了各区段间的连接边数情况，也可以得出高度节点间有较多连接的结论。文章在以上两个比较中认为：在自治系统拓扑中具有“富人俱乐部现象”。

文献[11]对存在富人俱乐部现象提出了异议，他们认为一个简单的富人俱乐部系数用于区别是否存在富人俱乐部现象是一个误导，应该将该度量建立在同样度分布的随机网络基础上，并提出了一种判定方法：

定义富人俱乐部系数与相同度序列随机网络的富人俱乐部系数的平均值之比$\rho _ { r a n } ( k ) = \phi ( k ) / \phi _ { r a n } ( k )$ ，如果该值大于1，则说明该网络存在富人俱乐部现象，否则不存在富人俱乐部现象。

文献[12]对判定富人俱乐部现象提出了自己的看法，他们从统计的角度上提出了另一种判定方法：即对文献[11]所提出的相对富人俱乐部系数计算 $\mathfrak { n }$ 次，然后统计在这 $\mathfrak { n }$ 次中，相对富人俱乐部系数值小于等于1的概率，如果该概率值小于 $\alpha$ （文中设 $\alpha = 5 \%$ )，则说明该网络存在富人俱乐部现象。然而，文中最后举了一个反例，说明这种方法在某些情况下也不适用。

至此，针对网络中富人俱乐部现象的判定方法不断进步，但仍不完美。不同领域研究者从自己的学科特点给出了相应的定义，从中也可看出工程技术背景的研究者与物理学研究者的思维方式的不同。

# (5)．共生效应

通过对多种真实网络的分析，文献[13]发现了互联网自治系统级拓扑中基于两种不同中心性（度、介数）都呈现富人俱乐部结构（两者的富人俱乐部系数趋于一致)，这种现象称作富人俱乐部结构的共生效应。实证表明，许多真实网络如互联网路由器级拓扑、蛋白质交互网络、科学家合作网络都没有这种效应，而广泛应用的BA模型[14]及其变种 $\mathrm { E S F } ^ { 7 [ 1 5 ] }$ 、GLP&[16]、PFP[17]都有这种效应。这种效应可以通过区别网络的宏观结构来选择是否采用 BA模型及其变种，作为网络建模的一个准则。

# (6)．自相似结构

我们研究了中国互联网的拓扑特征。中国互联网在网络建设和规划中要考虑已经存在的许多中国特色，如社会制度不同、运营商的特点不同、用户众多等，但研究表明，作为世界互联网的一部分，中国互联网自治系统级拓扑与世界互联网自治系统级拓扑的主要宏观特征可以用同一个PFP 模型模拟出来，表明作为互联网局部的中国互联网的拓扑结构与全球整体的互联网拓扑结构是自相似的[2]。传统的自相似结构通过分形的概念来刻画[18]，文献[19]提出了互联网结构的一种概念模型美杜莎（Medusa）1o：约占 $70 \%$ 的节点构成一个极大连通子图。这个子图可以不经过核（nucleus）而构成一个连通图。这个子图存在自相似结构，并可用分形的方法来刻画。

# (7)．局部聚集现象

文献[20]在局部聚集系数和节点度的关联性、三角形的分布、连通子图的冗余性三个方面研究了互联网自治系统级拓扑中的局部聚集特性。虽然表面上自治系统之间的连接大多数是自由选择的，但在地区和国家区域划分的现实环境下存在相当强的局部聚集现象。说明互联网的连接不是随机建立的，节点倾向于和局域的节点连接。另外，低度节点间存在连接冗余性。这些冗余连接可以丰富网络的路由选择并增强网络的健壮性。网络的局部聚集特性会对网络的性能产生很大的影响。根据互联网中观察到的局部聚集现象[20]，文献[21]改进了PFP 模型，提出了LDPFPl模型。

# (8)．向心性结构

文献[9把网络经 k-core 分解12后各层节点与最深核(nucleus)节点倾向于连接的结构称作为向心性结构，并指出互联网自治系统级拓扑具有明显的向心性结构，这种结构可以降低网络的平均距离，提高路由效率。

# (9)．层次结构

互联网自治系统级拓扑的层次结构有多种表述，如 Jellyfish（水母）模型[22以节点度为基础，把自治系统级拓扑形象地表示为水母形状；美杜莎模型[19以核数为基础，把自治系统拓扑分成了三个部分：由所有最大核数节点构成最深核、剩余部分存在一个极大连通子图以及其它孤立的连通块；文献[6]提出了核心—边缘模型，指出了核心与边缘不同的演化规律，文献[9]还提出了层次关联性、向心性结构等都从不同角度体现了互联网的层次结构。

# (10).健壮而又脆弱（robustyetfragile)

互联网拓扑结构具有“健壮而又脆弱”的双重特性，在不同尺度上，其形成机理不同。在自治系统级层面上同时表现出[43]：对节点随机失效的健壮性和在有意攻击情况下，只要移除少数重要节点，全网就会招致瘫痪，即表现为十分脆弱。这种脆弱性，也被称作阿基琉斯之踵(Achilles'heel3)。其根源在于度分布的不均匀性。

但在路由器级拓扑上，表现为互联网可以有效容忍在设计时考虑到的不确定因素，具有健壮性，而对设计时未被考虑的不确定因素（如IP前缀劫持、分布式拒绝服务）变得非常脆弱[44]。其双重特性是由于是否考虑到网络设计与优化等因素形成的，根源不在网络的度分布。

# 4 互联网结构知识的应用

网络结构知识无疑有广泛的用处。利用结构知识可以解决一些网络性能、抗毁、安全传输、节能等问题，如文献[23]利用节点的度作为OSPF14路由协议中连接权值的一个因素，使得路径更多样化，流量更均衡；文献[24]利用自治系统拓扑中边割集的宏观动态变化来检测网络中前缀劫持的发生；文献[25-26]把结构知识应用于可扩展路由。近年来，本文作者与同事利用互联网拓扑结构知识在流量优化、网络抗毁路由、服务器部署、路由算法设计等应用方面做了探索，部分已逐渐应用到多项实际工作中。具体的例子有：

(1)．在流量优化方面，利用互联网拓扑知识降低骨干网流量、优化网络性能，提出了PPM(P2PMatcher)技术，使上层对等连接(P2P)网络与承载网络的拓扑相匹配[27-30]，主要思想是根据节点的IP 前缀和自治系统号来优化对等连接应用的邻居选择和数据调度，提高对等连接流量的本地化程度，比国际上具有类似思想的 $\mathrm { P 4 P } ^ { [ 3 1 ] }$ 出现早了三年。

2009 年，还提出利用网络编码数据调度算法并结合位置感知技术来优化对等连接应用流量的方法[32]。该方法与此前的最好方法相比能将类似 BT 的服务的流量降低一半，几乎接近理论极限，从而可以实现ISP、对等连接内容提供商和终端用户三赢的完美局面。部分工作正成为国家通信行业标准[29的主要内容，国内所有网络运营商和主要设备制造商都参与了该标准的制定。另外，还针对互联网中大量 $\mathrm { N A T } ^ { 1 5 }$ 的客观存在,进行对等连接流量优化，提出了穿越私网的解决方案[33-34]，旨在充分地利用接入网络的资源，进一步提高对等连接流量的本地化程度，减轻域间和骨干网络上的流量。  
(2)．在网络抗毁方面，为了在覆盖（Overlay）网络中可以构建更多样化的网络路径以及使构造的备用路径的平均长度较短、转发效率更高，我们利用介数和核数刻画网络的特征，提出了一种在覆盖网络中可以实现高效选择转发节点的算法[35]。另外，利用核数和度的一些特点，结合转发节点位置信息及链路性能测量结果，达到所生成的备用路径的可靠性更高、实用性更强[3]，这些工作为抗毁路由的实施提供了技术保障。  
(3)．文献[37]从网络结构特征的角度对覆盖网络研究领域中覆盖中继服务器部署低效问题进行研究，利用互联网异配特性和富人俱乐部结构的特点（即度大的节点既倾向于与度小的节点连接同时又与度大的节点连接比较密集)，提出一种基于度等级的覆盖中继放置（Degree Rank based Overlay relays Placement，DROP）的启发式方案。该方案可以有效地选取一组用来放置覆盖中继节点的位置集合，使用很少的物理拓扑信息便可以优化整个中国互联网的冗余性和通信可靠性。  
(4)．文献[38]为了提高网络服务的性能,有效利用自治系统粒度上拓扑结构信息相对稳定且信息量适度的特征，使多路径覆盖路由的效率最大化，设计了分布式启发式路由选择算法 BFSQ。仿真结果表明 BFSQ 算法可以为终端节点有效选取多条覆盖路径，并可在实际的覆盖系统构建中部署实施。  
(5)．文献[39]提出了利用网络的无标度和强聚集特征来设计可扩展的路由算法,将网络看成由一个骨干树和许多捷径组成。由于无标度网络上的长捷径很少，因此使用骨干树和少数长捷径构造的生成树可以在路由表规模和拉伸系数上获得较低的上限，通过实验验证了该方法的有效性。文献[40]提出了一系列基于最大度地标的紧凑路由算法—HDLR、HDLR+、NIHDLR+，具有比通用的紧凑路由算法更优的基本性能，仿真验证了这些方法的有效性。  
(6)．把网络结构知识用于扩大网络容量，在最短路径路由占主导地位的情况下，提出了删边扩容的方法[41和在节点能力总和不变条件下，基于节点度的最优节点能力分配方法[42]。  
(7)．文献[45]通过设计对能耗敏感的网络拓扑,利用聚合和休眠方法实现网络中处于工作状态的设备数与网络负载正相关，当负载减轻时，更多设备会休眠，从而实现节能。另外，通过上述提到的对等传输（P2P）流量优化、服务器部署等方法大幅降低交通量以及在 NAT环境下私网穿透方案[33-34]中增加感知代理等技术，达到节能目的。  
(8)．文献[46]以网络体系结构为汇合点，将拓扑结构研究同制度经济学研究结合起来，对体系结构衍生的契约进行分析。重点研究向用户开放末端网络的技术，提高自治度从而丰富契约关系，并进一步产生促进网络经济发展的作用。这种研究不仅帮助我们理解互联网体系结构及其系统在微观经济学层面上的意义，同时从经济学层面提出了衡量网络体系结构实用性的评价方法。

# 5 总结与展望

正如弄清事物的结构是人类认识一个事物和对其进行改造首先面临的基本问题一样，对网络结构的掌握也是认识和改进网络的基础。互联网拓扑结构是互联网信息基础设施的最基本的内在属性。对互联网拓扑特征和知识的发现及其应用正在快速发展中。当前热点的信息系统工程领域（如云计算、三网融合、智慧地球、社会计算、物联网等）都离不开互联网这个信息基础设施。对互联网结构的揭示及其知识的深入理解，可以为人们有效利用网络、合理构建以互联网为基础的信息系统工程提供科学依据，为网络建设、升级改造、上层应用的优化、设计新一代网络体系结构和协议提供理论指导。

互联网是网络科学领域的一个典型的网络实例，对其拓扑结构知识的深入研究与应用可以丰富网络科学的内涵，推动网络科学这个新兴学科的发展。网络科学具有广泛的交叉性和复杂性，涉及数学、物理、计算机、系统科学等众多学科，在数学中，又常常涉及图论、统计学、随机过程、拓扑学等知识。网络科学对复杂系统的一般性描述和总结出的规律也为深入研究互联网拓扑结构或其它具体网络提供新的视角和指导。

期待在不久的将来，在网络结构分析领域能有更多朴素优雅的科学发现，为技术的进步提供方法论指导，进而产生简洁高效的技术方法服务于社会。

# 参考文献：

[1] MFaloutsos,PFaloutsos,C Faloutsos，On power-law relationships of the Intermet topology,ACM SIGCOMM Computer Communication Review,1999,29(4):251-262   
[2] S Zhou, G Zhang,G Zhang. Chinese Internet AS-level topology. IET Communications,vol.1, no. 2, Pp.209-214,2007.   
[3] Network Science and Engineering (NetSE) Research Agenda,A Report of the Network Science and Engineering Council Release Version1.1,Sep.2009   
[4] PErdos,A Rényi .On the evolution of random graphs.Pubi.Math. Inst. Hung. Acad. Sci ,1960,5   
[5] Reka Albertand Albert-Laszló Barabasi,Statistical mechanics of complex networks,Reviews of Modern Physics,vol.74,47 -97 (Jan,2002)   
[6] Guo-Qing Zhang,Guo-Qiang Zhang,Qing-Feng Yang,Su-Qi Cheng,Tao Zhou.Evolution of the Internet and its cores.New Journal of Physics 10，123027（2008）   
[7] ME J. Newman,Assortative Mixing in Networks .Phys. Rev. Lett.,2002, 89(2O):208701   
[8] ME J.Newman,Mixing paterns in networks .Phys. Rev.E67,026126 (2003)   
[9] 张国清，网络大尺度结构研究，中国科学院研究生院博士学位论文，2009   
[10] S Zhou,R JMondragon. The rich-club phenomenon in the Internet topology. IEEE Communications Letters,2004,8(3):180\~182.   
[11] V Colizza,A Flammini,M A Serrano,A Vespignani. Detection rich-club ordering in complex networks.Nature Phys.2006,2:110-115.   
[12] Zhi-Qiang Jiang,Wei-Xing Zhou.Statistical significance of the rich-club phenomenon in complex network. New Journal of Physics.10 (4), 043002 (2008)   
[13] Guo-Qing Zhang, Guo-Qiang Zhang, Su-Qi Cheng and Tao Zhou,“Symbiotic effect: A guideline for network modeling",EPL 87,68002,2009   
[14] A.L.Barabasi and R.Albert, Emergence of Scaling in Random Networks, Science, Oct,1999,509-512   
[15] R.Albert and A.L.Barabasi，“Topology of Evolving Networks:Local events and universality”, Physical Review Letter, 2000, 85(24):5234   
[16] Tian Bu，Towsley D，“On distinguishing between Internet power law topology generators” INFOCOM 2002   
[17]S. Zhou and R.J. Mondragon, Accurately modeling the internet topology. Phys.Rev. E 70,066108, 2004   
[18]C Song,S Havlin,HA Makse, Self-similarity of complex networks.Nature,2005,433:392-395   
[19]Shai Carmi, Shlomo Havlin, Scott Kirkpatrick, Yuval Shavittand Eran Shir.A model of Internet topology using k -shell decomposition,Proceedings of the National Academy of Sciences,2007 104:11150-11154   
[20]张国强，张国清，“互联网AS 级拓扑的局部聚团现象研究”，复杂系统与复杂性科学，3（3), 2006   
[21]Guoqiang Zhang and Guoqing Zhang, Exploring the Local Connectivity Preference in Internet AS Level Topology. IEEE International Conference on Communications 2Oo7, Scotland   
[22]G. Siganos,S.L. Tauro,and M. Faloutsos,“Jellyfish: A Conceptual Model for the AS Internet Topology. Journal of Communications and Networks", 8(3), 2006   
[23]Murtaza Motiwala， Megan Elmore, Nick Feamster and Santosh Vempala, "Path Splicing", SIGCOMM 2008.   
[24]Zheng Zhang, Ying Zhang, Y.Charlie Hu, Z.Morley Mao,Randy Bush, "iSPY: Detecting IP Prefix Hijacking on My Own", SIGCOMM 2008   
[25]A.Brady and L.Cowen. Compact routing on power-law graphs with additive stretch.In ALENEX,2006.   
[26]S. Carmi,R. Cohen,and D.Dolev. Searching complex networks efficiently with minimal information. Europhysics Letters,74:1102-1108, 2006.   
[27]张国强 张国清 基于全局Internet 拓扑知识的P2P 应用构建方法专利号 ZL200510086903.7   
[28] 周志勇 张国清等，一种 P2P 视频直播系统数据调度中的链路选择方法，专利申请号： 200810111656.5   
[29] 张国清、唐明董等 基于承载网的P2P流量优化技术框架 通信行业标准 2009H103   
[30] Guoqiang Zhang,Guoqing Zhang. Agent Selection and P2P Overlay Construction Using Global Locality Knowledge,ICNSC, April, 2007,London   
[31]Haiyong Xie, Y. Richard Yang,Arvind Krishnamurthy, Yanbin Liu, Avi Silberschatz,“P4P: Provider portal for applications",ACM SIGCOMM 2008.   
[32] 张国强 程苏琦 张国清，P2P流量优化方法及其系统，专利申请号：200910242797.5   
[33] 傅川 王迪 张国清等，一种系统终端设备建立 NAT 穿越通道的方法，专利申请号： 200810104586.0   
[34]傅川,张国清.一种通信网络系统及通信方法、通信设备,专利申请号 200810115782.8   
[35] 杨清峰张国清李彦君，转发节点选取方法和装置，专利申请号：200910085467.X   
[36] 杨清峰李彦君张国清，覆盖网备用路径生成方法和装置，专利申请号：200910085466.5   
[37]Bin Yuan, Guoqiang Zhang, Yanjun Li, Guoqing Zhang, Zhongcheng Li,“Improving Chinese Internet's Resilience through Degree Rank Based Overlay Relays Placement”,IEEE International Conference on Communications 2008（ICC 2008）.   
[38]Bin Yuan, Guoqiang Zhang, Yanjun Li, Guoqing Zhang, Zhongcheng Li,“Measuring the Impacts of Multipath Overlays on the Performance of Inter-Domain Routing", IEEE International Conference on Communication 2009（ICC 2009）   
[39]唐明董，张国清，杨景，张国强，针对无标度网络的紧凑路由方法，软件学报，已录用。   
[40]Mingdong Tang, Guoqing Zhang, Guoqiang Zhang, Jing Yang, Compact Routing in Internet-Like Graphs with Improved Space-Stretch Tradeoff IEEE International Conference on Communications 2010(ICC 2010)   
[41]Guo-Qing Zhang,Di Wang, Guo-Jie Li. Enhancing the transmission efficiency by edge deletion in scale-free networks,Physical Review E 76, 017101 (2007).   
[42]Guo-Qing Zhang， Shi Zhou，Di Wang，Gang Yan，Guo-Qiang Zhang，Enhancing network transmission capacity by efficiently allocating node capability,arXiv:0910.2285(2009)   
[43]R.Albert, H. Jeong,A-L Barabasi.Error and attack tolerance of complex networks.Nature, 2000, 406:

378-382

[44]J. C. Doyle,D.L. Alderson,L.Li,et al. The "robust yet fragile" nature of the Internet.PNAS, 2005,102(41)14497-14502   
[45] Guoqiang Zhang and Guoqing Zhang，“Adaptive link power management for energy-efficient routing in core networks"， submitted to IEEE Communications Letters.   
[46] 傅川 张国清 杨景 互联网络体系结构的契约特征研究 信息技术快报 2010.3

作者简介：

张国清： 中国科学院计算技术研究所硕士生导师，博士，Email:gqzhang@ict.ac.cn

（上接第72页）

# 参考文献

[1] http://www.youtube.com   
[2] http://www.tudou.com   
[3] Huang，Yan and Fu, Tom Z.J.and Chiu,Dah-Ming and Lui, John C.S.and Huang,Cheng, "Challenges,Design and Analysis of a Large-scale P2P-VoD System,” ACM SIGCOMM,Aug. 2008.   
[4] http://www.uusee.com   
[5] http://www.ppstream.com/   
[6] L. Gomes,“Will All of Us Get Our 15 Minutes On a YouTube Video?” Wall Street Journal, Aug.30, 2006.   
[7] 程学旗，余智华，等．P2P技术与信息安全．信息技术快报，2004，10(3);   
[8] Xinyan Zhang,Jiangchuan Liuy,Bo Liz,and Tak-Shing Peter Yum,“CoolStreaming/DONet: A Data-Driven Overlay Network for Efficient Live Media Streaming",INFOCOM,2005   
[9] Apache Portable Runtime Library, htp://apr.apache.org;   
[10] http://www.apache.org;

作者简介：

李哲中：中国科学院计算技术研究所 网络重点实验室 硕士生  
张铁贏：中国科学院计算技术研究所网络重点实验室 博士生  
刘悦：中国科学院计算技术研究所 网络重点实验室 副研究员，Email:liuyue@ict.ac.cn  
程学旗：中国科学院计算技术研究所网络重点实验室研究员