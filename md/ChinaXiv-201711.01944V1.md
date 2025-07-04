# 基于论文合著网络的学术社区分析方法研究一 以《美国地理学家联合会会刊》为例

卿雅娴李锐1,2 吴华意1,21(武汉大学测绘遥感信息工程国家重点实验室武汉 430079)2(地球空间信息技术协同创新中心武汉 430079)

摘要：【目的】对论文合著网络进行分析，划分并分析学术社区，发现领域发展与变化规律。【方法】利用社区快速发现算法识别合著网络中的学术社区，建立学者论文影响力与合作影响力的综合指标，评价学术社区中学者的学术影响力，并以学术影响力最大的三个社区为例，从生命周期的角度分析和讨论学术社区的发展和演化。【结果】基于《美国地理学家联合会会刊》的数据分析表明：本文提出的综合指标能够有效地挖掘学术社区中的杰出学者；基于生命周期的合著网络中学术社区分析方法可以发现不同学术社区的研究趋势和热点变化。【局限】以单一期刊为例，可能导致学术社区的组成相对单薄，增加不同来源的期刊数据能够进一步提升研究结果的可信性。【结论】本文提出的学术社区分析方法，可以从不同角度发现与解释领域的发展方向和规律，为相关领域学者的研究工作提供更加科学的指导和认识。

关键词：《美国地理学家联合会会刊》学术社区生命周期分析学者评价

分类号:P208 TP311

# 1引言

随着科学技术的不断发展，科研合作逐渐成为科学研究的主流方式[1]。科研合作促进各学科领域的快速发展，学术期刊上共同署名发表的文章占比越来越大，论文合著网络成为当前学术合作网络的一种主流表达方式，学术合作网络的相关工作也成为当前学术的研究热点之一[2-4]。学术合作网络是描述学者合作关系的网络，通常将每个学者作为网络中的一个节点，若两个学者共著一篇科研论文，两个节点之间就连接一条边。学术合作网络是复杂网络的一种，网络中联系相对紧密的节点以及他们之间的连线构成学术社区结构，学术社区表现为学术合作网络中联系相对紧密的学者群体[5-7]。就目前的科研模式而言，学术社区的组成和演化，在一定程度上能反映研究领域热点的变化规律[8]。因此，学术社区分析是研究科研合作和领域发展的一种重要途径。

近年来，国内外大量学者对不同领域的学术合作网络分析方法进行了相关研究。李亮等利用社会网络分析法(量化社会网络中的行为者关系)的中心性分析、凝聚子群分析和核心-边缘结构分析，对国内情报学领域的学术合作网络进行实证研究[9]。李盛庆等以复杂网络研究领域1975年-2012年间的科研合著网络为例，按时间划分4个发展阶段来解释和说明复杂网络领域科研合著网络的演化和知识传播特点[10]。他们主要采用社会网络分析方法(SocialNetworkAnalysis,SNA)中的网络节点中心性、小世界效应等指标对合作网络节点或者网络总体分布情况进行分析，可能导致分析结果过于宏观，难以深度挖掘学术合作网络的演化规律。Sun 等从学术社区的角度分析地理信息科学领域，根据社区合作模式的规模大小对地理信息学科的发展进行分析和解释[11]。但是该研究主要侧重于社区规模和网络结构分布的变化，没有从单个社区的角度分析领域的演化规律，只能得到领域发展分布的宏观情况，不能发现学科发展的直接驱动因素和话题演变规律。

学术社区分析中学者的学术影响力至关重要。学者学术影响力的评价主要是关于学者引用影响力指标的相关研究，如H指数[12](一个学者发表了H篇被引频次不少于H次的论文数量)等。杜建等则通过整合引用影响力和合作影响力对学者进行评价。在引用影响力方面，他们根据论文中学者署名顺序确定学者权重，重新分配文章被引次数，构建调和引用影响力指标；在合作影响力方面，他们归一化网络结构中的 h 度指标(表示一个节点合作团队的规模)、r度指标(表示节点之间的合作频次)，以此衡量学者的合作影响力[13]。该研究的合作影响力指标主要对比不同合作团体中杰出节点的合作影响力，而学术社区网络一般由多个合作团队构成不适于评价同一个学术社区内部的节点。因此，通过构建一种学术社区中学者的论文影响力和合作影响力综合评价指标，能够对同一学术社区中的学者进行综合学术影响力的评价，并识别学术社区内的杰出学者。

本文基于文献数据建立学术合作网络并发现学术社区，提出一种从生命周期的角度分析合著网络中学术社区发展及演变的方法。学术合作网络中每个学术社区的兴起与衰落，一定程度上能够反映其对应领域的发展情况；学术社区中杰出学者的研究方向也能一定程度上反映该学术社区的研究方向及研究热点。结合论文数据的特点，综合学术社区中学者合作影响力指标与论文影响力指标评估学术社区中学者的影响力。与传统的H指数对比，发现本文提出的综合影响力高的学者节点在一定程度上更能代表学术社区的杰出学者，其研究方向对整个社区的发展起着至关重要的作用。

# 2学术合作网络模型

学术合作网络模型可以抽象为一个由点集 $V$ 和边集E组成的图 $G = ( V , E )$ 。节点数记为 $N { = } | V |$ ，边数记为 $M = \mid E \mid$ 。用点集 $V$ 的一个元素 $\nu _ { i }$ 表示发表论文的学者，论文中的学者 $\nu _ { i }$ 与 $\nu _ { j }$ 用边 $E _ { i , j }$ 来连接，文章的学者署名顺序决定边 $E _ { i , j }$ 的权重，如图1所示。

![](images/f5819591f6f3917621fb21417febf1263d8170ac280927c7cd0318610df80b2d.jpg)  
图1学术合作网络模型示例

# 2.1学者综合学术影响力

(1）学者论文影响力

学术合作网络模型中，学者 $\nu _ { i }$ 的论文影响力 $F C _ { i }$ 不仅与学者每篇文章的被引次数 $C$ 有关，还与其在论文中的排名 $\boldsymbol { r }$ 有关，因此本文采用调和引用影响力[13]评估学者的论文影响力，具体计算如公式(1)所示

$$
F C _ { i } = \sum _ { m = 0 } ^ { N } P _ { m } ^ { i } ( \boldsymbol { r } ) C _ { m } ^ { i }
$$

其中, $N$ 为 $\nu _ { i }$ 发表的论文总数， $C _ { m } ^ { i }$ 表示学者 $\nu _ { i }$ 论文 $\mathbf { \nabla } _ { m }$ 的被引次数， $P _ { m } ^ { i } ( r )$ 是关于排名的函数，表示学者 $\nu _ { i }$ 在论文 $m$ 中排名 $\boldsymbol { r }$ 时学者占总影响力的百分比。若一篇论文共有 $n$ 个学者，那么第 $\boldsymbol { r }$ 个学者关于排名的函数如公式(2)所示。

$$
P ( r ) = { \frac { 1 / r } { 1 + 1 / 2 + \cdots + 1 / n } }
$$

(2）学者合作影响力

大量研究采用社会网络分析方法中节点的度量指标评估学者的合作影响力[14-16]。Takeda 等以AIS(AutomaticIdentification System)电子图书馆会议的文献数据为例，建立学术合作网络，利用社会网络分析方法的中心度指标对学术网络中的学者节点进行评估[14]。中心度指标能反映学者在学术合作中与人交流、共享的能力，可以由多种指标表示，如度数中心度、介数中心度、特征向量中心度等[17]，其中特征向量中心度反映的是一个学者节点其相邻节点的中心程度[18]，即一个学者与一个合作影响力高的学者合作,其自身的合作影响力也会相应提高，这也符合人们对合作模式的认知，适合本文学术社区网络节点的度量。因此，本文采用网络节点特征向量中心度来衡量学者的合作影响力。笔者定义学者 $\nu _ { i }$ 的合作影响力$F C O _ { i }$ 如公式(3)所示。

$$
F C O _ { i } = \frac { 1 } { \lambda } \sum _ { \nu _ { j } \in A ( \nu _ { i } ) } F C O _ { j }
$$

其中, $A ( \nu _ { i } )$ 为学者 $\nu _ { i }$ 相邻的学者节点集合，入表示学者 $\nu _ { i }$ 邻接矩阵的最大特征值。学者合作影响力只有在互相连接的网络中才有意义，因此学者合作影响力需要在同一学术社区下进行对比和计算。

# (3）学者综合学术影响力计算

研究社区中学者的综合影响力(AcademicInfluenceofanAuthor)评价有助于有效地分析学术社区的结构和分布。一个学者的综合影响力不仅与其论文影响力有关，还与其合作者影响力有关，一般来说影响力较大的学者其论文影响力和合作影响力均较大。论文影响力和合作影响力没有量化的分类分级指标，由于两者量纲不同，且依赖程度不高，故采用逼近理想解排序法(Technique for Order Preference by Similarity toIdea Solution，TOPSIS)[19]综合论文影响力 $F C _ { i }$ 以及合作影响力 $F C O _ { i }$ 两个指标，最终得到一种综合的学者影响力评价指标 $F _ { i }$ 0

TOPSIS方法利用学者的合作影响力 $F C O _ { i }$ 以及论文影响力 $F C _ { i }$ 构建数据原始矩阵，对其进行归一化,找出论文影响力与合作影响力均最优的向量 $Z ^ { + }$ 以及论文影响力与合作影响力均最劣的向量 $Z ^ { - }$ ，分别计算各学者节点与最优向量 $D _ { i } ^ { + }$ 及其与最劣向量的距离$D _ { i } ^ { - }$ ，获得各学者节点与理论上最优节点的相对接近程度 $F _ { i \circ }$ 以此作为排序的依据，计算得出的相对接近程度 $F _ { i }$ 即为本文提出的学者影响力综合评价指标。

# 2.2 学术社区影响力

在学术合作网络模型中，某些学者之间的联系会相对紧密，而某些学者之间的联系相对松散。这些联系相对紧密的学者节点聚集成簇团，形成学术社区。同一个学术社区的学者，可能来自于同一所高校或者科研机构，也可能因为共同参加某些学术会议而建立合作关系。本文将直接或者间接有过合作关系的学者均划分到同一学术社区，从而保证学术社区的连通性。学术社区规模是学术社区影响力的一个重要研究因子，社区的形成是一个随时间累积的过程，本文的社区规模是指在一定时间阶段中社区中学者的个数。

学术社区的影响力主要来源于社区内部学者的学术影响力。一个社区的学术影响力 $F C M$ 是组成这个社区的学者的累积论文影响力 $F _ { i }$ 之和，具体如公式(4)所示。

$$
F C M = \sum _ { i = 0 } ^ { | C | } F _ { i }
$$

其中, $C$ 表示一个社区中的学者节点集合, $| C |$ 表示社区中学者的个数。

# 3学术社区分析方法研究

# 3.1 数据来源

《美国地理学家联合会会刊》(简称《会刊》)主要刊登地理学的理论、方法和实践相关的文章。《会刊》从1911-01-01到2014-12-31共计发表7033 篇学术文章。《会刊》作为美国地理界的权威期刊，是美国地理学界研究的风向标[20]。《会刊》不仅收录分布在世界各地的成员在地理学研究中的最新成果，而且还会收录每年相关会议中的一些优秀报告。《会刊》的内容能够反映世界地理学的新进展，其期刊学者参与度分布最为广泛。

本文分析的文献数据来自于《会刊》出版的所有文章，主要包括文献的作者、关键字、摘要、标题、出版年份、出版机构、通讯地址等信息。数据来源为社会科学引文索引数据库(Social Science Cited Index),其中合著记录为949条。

# 3.2 研究方法

选取1911年至2014年《会刊》中有合作关系的949 篇文章为数据源。以每一位学者为节点，学者之间的合作关系为边，形成一个 $N { = } 1 8 7 3$ ， $M { = } 1 5 0 1$ 的学术合作网络。

传统的社区分析主要针对网络节点度量、社区的识别、社区规模和结构等量化指标进行分析。本文基于学术合作网络，利用社区快速识别方法[21对学术网络进行学术社区探测，计算每个社区的学术影响力，选择学术影响力最大的三个社区进行社区生命周期分析。并分别以这三个社区为研究对象，计算每个社区中学者的综合学术影响力 $F _ { i } ,$ 找出每个社区中的杰出学者，并与经典的H指数进行比较，验证本文提出的综合学术影响力指标的可靠性。

# 3.3分析

# (1）学术社区发现

利用可视化软件Gephi，对《会刊》构造的学术合作网络进行社区探测，得到符合要求的学术社区462个。图2展示了该学术合作网络的整体情况，研究选择图中高亮的影响力最大的三个社区进行分析。学术合作网络中的学术社区具有一定的空间聚集性，具体表现为一个社区的大部分学者来自于同一所学校。研究分析的三个社区，每个社区的学者主要来自于某所学校。鉴于人们对社区认知倾向于地理空间的社区，以一个社区中学者最多的机构对网络拓扑社区进行命名。

![](images/47c739294a77b783ff769da2aec4aa911141f9144aac8330976a63c7aa87a0fc.jpg)  
图2学术合作网络社区的分布情况  
图4三大社区成长变化趋势

(2）社区影响力

从时间的角度对各个学术社区的学术影响力进行分析，分别统计不同时间段内社区的学术影响力及社区规模。如图3所示，加州大学圣芭芭拉分校社区的规模和影响力均最大，该社区的人数为89人，社区的学术影响 $F C M _ { 1 }$ 大于1200。影响力第二的社区是俄亥俄州立大学，它的社区规模是19人，影响力指数 $F C M _ { 2 }$ 约为621，影响力第三的亚利桑那州立大学社区成员数目为49人， $F C M _ { 3 }$ 约为618。本文以这三个社区为研究对象，从生命周期的角度对其成长和演化进行分析。

![](images/0f09f85967003bc6e400c586d71e858838e7427992bb17a1020cb2aa65ca028e.jpg)  
图3学术合作网络各社区累计影响力及大小分布

(3）社区生命周期分析

以加州大学圣芭芭拉分校社区、俄亥俄州立大学社区、亚利桑那州立大学社区为例，分析不同学术社区的生命周期。结合三大社区的数据特征，以4年为统计周期，从1978年到2014年的三大社区学术合作网络的结构发生了很大的变化。图4描述此时间段内的三大社区规模和影响力的变化，从总体趋势看，三个社区规模都是随时间缓慢增长，社区影响力增长与规模增长趋势基本一致。

100 89 140012008066 68福 5443 44 46 48 49 80036 34 600263 40019 16 2020 35 37 9 11 4 2000 01978198219861990199419982002200620102014年份加州大学圣芭芭拉分校 俄亥俄州立大学亚利桑那州立大学 一加州大学圣芭芭拉分校俄亥俄州立大学 亚利桑那州立大学

$\textcircled{1}$ 加州大学圣芭芭拉分校社区

加州大学圣芭芭拉分校社区是影响力最大的社区，该社区的研究热点随着时间的推移而变化。该社区研究重点从最开始的地图制图学到后来的与人地分布有关的区域地理学又向经济地理学、行为地理学、社会地理学、城市地理学等研究方向转变。根据社区规模和影响力的增长情况，可以把加州大学圣芭芭拉分校社区的生命周期分为4个阶段。

1）萌芽期(1978 年之前)。第二次世界大战以后，经过战争的需求和推进，地图制图学有了很大的发展。该社区的第一个合作始于1957年，威斯康星大学研究制图学的RobinsonA.H.和BrysonR.A.在《会刊》共同发表文章《AMethod forDescribingQuantitativelytheCorrespondenceofGeographicalDistributions》[22]是社区形成的开端。萌芽时期,Robinson A.H.在威斯康星大学、JenksG.F.在堪萨斯大学分别发展形成以研究地图制图学为主的小社区。这个时期，来自威斯康星大学的RobinsonA.H.和ClarkW.是社区的核心成员。

2）生长期(1978年-1986年)。这段时间是美国新地理学发展的黄金时期，很多地理学家试图通过效仿其他学科的方法将地理学变为科学。1978年，美国地理协会开始出现专业团体的划分，地理学划分成很多不同的小团体[23]。1982年,HartJ.F.在年会《会刊》上发表《PresidentialAddress:TheHighestFormoftheGeographer'sArt》[24]，批判地理学中的极端科学主义。由于他在地理学上的反科学理论，引起以RobinsonA.H.为核心的学术社区的GolledgeR.联合ChurchR.、ToblerW.等发表《CommentaryontheHighestFormof theGeographersArt》[25]共同反驳。HartJ.F.的文章在地理学界引起很大的争议，却促成GolledgeR.G.和ToblerW.R.的合作，以及JenksG.F.的社区和RobinsonA.H.的社区联合，使得以RobinsonA.H.为核心的社区规模和影响力飞速成长，加州大学圣芭芭拉分校的Golledge R.G.、Battersby S.E.在此阶段开始崭露头角。HartJ.F.与GolledgeR.G.的争论使得美国地理学的研究结构发生巨大变化，地理学由传统的自然科学划分为不同的研究方向，美国地理学进入百花齐放的时代[23]。与此同时，争论使得很多私立大学纷纷取消地理学专业，很多地理学家不得不加入公立大学继续研究，这也导致美国地理学发展较好的学校大多是公立大学。在这个时代，HartJ.F.引导的区域地理学成为此阶段研究重点之一，而以GolledgeR.G.为先驱的行为地理学也开始快速发展。

3）稳定期(1986年-1998年)。经过黄金发展期，社区结构初步形成。此阶段社区内新成员一般是杰出学者的学生，他们是社区的新兴力量，学术影响力刚刚起步，社区影响力和规模的增长相对比较稳定。这一阶段社区研究多是结合区域发展，实现特定区域中地理学的应用。

4）成熟期(1998年-2014年)。1998年-2002年，社区成员只增加6个，但是社区影响力上升1.39倍。21世纪初，在经济全球化的推动下，世界各城市之间联系变得愈发重要。2000年,BeaverstockJ.V.,SmithR.G.以及TaylorP.J.在美国地理学家协会年会上发表《WorldCityNetwork:ANewMetageography?》[26]。这篇文章的引用量达到156,使得社区影响力进一步提升；另一方面表明城市地理学是该社区的一个重要研究方向。在这个时期，稳定期的新晋学者厚积薄发，社区的小群体也逐步发展自己的规模和影响力。2002年以后，社区规模和影响力持续增长，ChurchR.L.在北卡罗莱纳州立大学发展了一批从事地理信息科学的学者，影响力不断扩大。2010年-2014年，社区的规模持续增长，但是影响力的增长速度却放缓，这意味着最大社区或将进入衰退期，可能会被其他正在增长的社区超越。

$\textcircled{2}$ 俄亥俄州立大学社区

俄亥俄州立大学社区只有19名成员，但是社区的总影响力却排名第二，社区主要研究领域是政治地理学与经济地理学。社区的生命周期分为三个不同的阶段。

1）萌芽期(1986年之前)。加州大学圣芭芭拉分校的影响力和规模基本处于一枝独秀的状态，俄亥俄州立大学社区以及其他机构在此阶段在《会刊》上发表的文章大多是个人发表，没有形成影响力较大的社区。

2）生长期(1986年-2002年)。此阶段社区的规模变化不显著，但是影响力却增长近2倍。1988年，CoxK.R.与MairA.合作的《Locality and Community in the Politics of LocalEconomicDevelopment》[27]在《会刊》上发表，综合被引次数达到219，使得此社区的影响力仅次于加州大学圣芭芭拉分校社区。此后社区影响力没有显著变化，直至1999年，俄玄俄州立大学的LobaoL.、RulliJ.与爱荷华大学的BrownL.A.在《会刊》上发表一篇颇具影响力的人文地理学论文《Macrolevel Theory and Local-level Inequality:IndustrialStructure, Institutional Arrangements, and the PoliticalEconomy ofRedistribution,1970 and1990》[28],促进该社区影响力的提升。人文地理学是《会刊》重要的研究方向，此社区学者发表的人文地理学论文在《会刊》上的有很高的引用影响力，促使此社区步入成熟期。

3）成熟期(2002年-2014年)。这个阶段社区的论文数量逐渐提升，规模与影响力增长速度稳定且放缓，社区开始步入成熟期。随着科技的发展，地理信息系统(GeographyInformation System,GIS)、遥感(Remote Sensing,RS)等在社会地理学、政治地理学的研究中发挥越来越重要的作用。以俄亥俄州立大学为核心，与爱荷华大学、华盛顿大学、多伦多大学合作，主要研究政治地理学、经济地理学等社会地理学的社区结构逐步形成。

$\textcircled{3}$ 亚利桑那州立大学社区

亚利桑那州立大学社区是《会刊》学术合作网络中一个新兴社区。主要研究方向为气候气象地理学。该社区生命周期划分与俄亥俄州立大学社区一致，主要包括三个阶段。

1）萌芽期(1986年之前)。密歇根州立大学的HarmanJ.R.、HarringtonJ.A.以及EltonW.M.等人在此时期组合成小学术社区，社区的主要研究方向是自然地理学中的降水模式。迈阿密大学的HehrJ.G.、伊利诺斯州大学的Charton F.L.在这个时期开始与HarmanJ.R.合作，逐渐形成该学术社区的萌芽。

2）生长期(1986年-2002年)。1990 年亚利桑那州立大学的BallingR.C.、WellS.G.共同在《会刊》上发表关于降水模式的论文《Historical RainfallPatterns and ArroyoActivity within the Zuni River Drainage Basin, New Mexico》[29],亚利桑那州立大学社区开始形成。1998年，亚利桑那州立大学的CervenyR.S.与密歇根州立大学的HarmanJ.R.就平衡环境和环境科学的价值观问题展开合作，为后来两个大学的社区联合奠定了基础。21世纪，随着气候变化问题日益突出，人与自然和谐相处的议题被高度重视，以BallingR.C.为核心的亚利桑那州立大学学者发表的关于降水、气候模式等文章，利用GIS空间分析方法分析解释环境问题，使得与之相关的气候GIS、环境地理等变成研究热点。

3）成熟期(2002年-2014年)。这个阶段亚利桑那州立大学的社区与密歇根州立大学社区正式联合。至2014年，社区已经成长为有49个成员的大社区，其中20名成员来自亚利桑那州立大学，形成研究气象地理学与人文地理学结合为主的学术社区。这个时期的社区无论是规模还是影响力，涨势明显。从增长速度看，此社区颇有后起之秀之势，加之21世纪气候问题、环境问题持续突出，社会对其关注度不断提升，社区后期或能超过俄亥俄州立大学社区，甚至加州大学圣芭芭拉分校社区。

(4）社区学者学术影响力评价

通过识别社区内的杰出学者以评价社区学者学术影响力。如图5-图7所示，综合影响力越大的学者，其节点半径越大，节点的不同颜色表示来自不同机构。分别对三个社区进行社区学者学术影响力评价。

mai, a cox kr chungOsu-yuel longbr@ke,db spaket silveyQachel lob@o. I laurienina ruj   
ig,Stephen lawson, va jarqsz,l   
jeffypjefy akinnen bondsanne jeffey， r

![](images/2a7ce5d67b9d6617d0b54acf053a94f71e41c38391892a5eb9814e5b29cc34d7.jpg)  
图5加州大学圣芭芭拉分校社区学者网络  
图6俄亥俄州立大学社区成员  
图7亚利桑那州立大学社区成员分布图

$\textcircled{1}$ 加州大学圣芭芭拉分校社区

表1比较综合评价指标 $F _ { i }$ 与H指数以及总被引次数。可以看出，H指数排名与综合影响力 $F _ { i }$ 排名相差较小。BattersbyS.E.在H指数下排在第9位，而选用本文指标 $F _ { i }$ 时，排名上升3位，原因是综合考虑学者的合作情况与著作署名顺序。RobinsonA.H.在《会刊》上发表的文章数目很

lest@huallachain,b ids@sb matthews,ra brazel, aj reid n deitrick,Stephanie graf, wl mings,rc   
1ua0g,yq mehugh,ke fancindy kirkwoodcrajgberatricia li,weDwen ellis,anessimberli arton ja chen,tDgyong wen2,ea lee,seung-jae eltowm data balling, rc harnan, jr charton,fl bridwelscotta cerveDy,r hel jg aidin mitler,QarveywellS,sg arbogest,afstahle. dv pace,matthewb neuteDediSersteven   
vangshujichenimin peterson,@townsend navarro-sigueenza,adolfo g liu, xiaoping li, xingong shiQun he, ji@qiang wang,dongmei onegatracy alford-teaster, jennifer

多，论文影响力也很大，若以H指数评价，其排名是第3位;而采用 $F _ { i }$ 时，考虑到RobinsonA.H.很多文章均为独立发表，合作影响力相对较弱，故其名次下降4位。个别学者的H指数排名与 $F _ { i }$ 排名差距很大，如BeaverstockJ.V.的 $F _ { i }$ 排名与H指数相比，上升10位。由于他在会刊上只发表一篇文章，使得H指数很低，但这篇文章的被引次数却很高，说明H指数对影响力较大的论文不敏感，而综合影响力指标 $F _ { i }$ 能综合考虑论文影响力和合作影响力，相对客观地评价学者影响力。本文利用综合影响力来评价和发现杰出学者，一定程度上能够弥补H 指数对论文数量与影响力不敏感的缺点。

# $\textcircled{2}$ 俄亥俄州立大学社区

俄亥俄州立大学社区成员相对较少，但是此社区的跨机构合作却最多，如表2所示，排名前17位的学者分别来自8所不同的学校。社区中综合影响力排名第一的CoxK.R.也来自俄亥俄州立大学，故此社区以俄亥俄州立大学为核心。社区成员较少造成社区的平均综合影响力远低于加州大学圣芭芭拉分校社区。此社区学者的综合影响力与H指数相比，除弗吉尼亚大学的MairA.排名差异较大以外，其余学者排名趋势基本吻合。MairA.在《会刊》上只发表2篇文章，导致他的H指数排名不高。但是，他与CoxK.R.教授有密切的合作关系，而且文章引用量很高，因此MairA.的综合影响力 $F _ { i }$ 排名相对靠前，这也说明H指数对少数引用量较高的论文敏感性不足。

$\textcircled{3}$ 亚利桑那州立大学社区

亚利桑那州立大学社区与加州大学圣芭芭拉分校社区相比，综合影响力总体相对较低，社区具体成员分布如表3所示。以亚利桑那州立大学为核心，犹他大学、达特茅斯学院为主要合作单位的社区结构特征非常明显。社区学者中，综合影响力超过0.5的只有3人，这可能是因为社区很多学者都是近几年才加入，故至2014年，社区影响力相对较小。社区整体的学者综合影响力也低于加州大学圣芭芭拉分校社区和俄亥俄州立大学社区。社区学者综合影响力 $F _ { i }$ 与H指数对比，总体趋势一致，但是WellSG和MingsRC的H指数排名21，综合影响力 $F _ { i }$ 却分别排名3和6，这也说明H指数对少数高质量论文学者不敏感。

表1加州大学圣芭芭拉分校社区综合影响力排名前17位社区成员基本情况表  

<html><body><table><tr><td>学者</td><td>FCvi</td><td>FCOvi</td><td>Fvi (R)</td><td>H(R)</td><td>NP</td><td>学者机构</td></tr><tr><td>Golledge R. G.</td><td>163.0808</td><td>1.0000</td><td>0.9556(1)</td><td>10(1)</td><td>14</td><td>加州大学圣芭芭拉分校</td></tr><tr><td>Tobler W. R.</td><td>123.7087</td><td>0.5866</td><td>0.6610(2)</td><td>6(5)</td><td>9</td><td>密歇根大学</td></tr><tr><td>Jenks G. F.</td><td>173.0912</td><td>0.0116</td><td>0.5548(3)</td><td>8(2)</td><td>16</td><td>堪萨斯大学</td></tr><tr><td>Rushton G.</td><td>144.9093</td><td>0.0458</td><td>0.5142(4)</td><td>5(6)</td><td>9</td><td>爱荷华大学</td></tr><tr><td>Clark W.</td><td>138.6066</td><td>0.0775</td><td>0.5090(5)</td><td>7(3)</td><td>12</td><td>加州大学洛杉矶分校</td></tr><tr><td>Battersby S. E.</td><td>10.6668</td><td>0.9087</td><td>0.4402(6)</td><td>3(9)</td><td>3</td><td>加州大学圣芭芭拉分校</td></tr><tr><td>Robinson A. H.</td><td>107.2730</td><td>0.0000</td><td>0.4087(7)</td><td>7(3)</td><td>14</td><td>威斯康星大学</td></tr><tr><td>Smith R. G.</td><td>43.0824</td><td>0.5866</td><td>0.3951(8)</td><td>3(9)</td><td>3</td><td>拉夫堡大学</td></tr><tr><td>Montello D. R.</td><td>48.4133</td><td>0.5030</td><td>0.3748(9)</td><td>2(14)</td><td>2</td><td>加州大学圣芭芭拉分校</td></tr><tr><td>Smith T. R.</td><td>7.4694</td><td>0.6748</td><td>0.3563(10)</td><td>3(9)</td><td>4</td><td>堪萨斯大学</td></tr><tr><td>Beaverstock J. V.</td><td>85.0918</td><td>0.0000</td><td>0.3391(11)</td><td>1(21)</td><td>1</td><td>拉夫堡大学</td></tr><tr><td>Simonett D. S.</td><td>15.9592</td><td>0.5866</td><td>0.3339(12)</td><td>4(7)</td><td>5</td><td>堪萨斯大学</td></tr><tr><td>Estes J. E.</td><td>15.8189</td><td>0.5866</td><td>0.3336(13)</td><td>4(7)</td><td>4</td><td>加州大学洛杉矶分校</td></tr><tr><td>Marsh M.</td><td>15.2729</td><td>0.5808</td><td>0.3302(14)</td><td>2(14)</td><td>2</td><td>加州大学圣芭芭拉分校</td></tr><tr><td>Gale N.</td><td>12.9067</td><td>0.5808</td><td>0.3262(15)</td><td>2(14)</td><td>2</td><td>加州大学圣芭芭拉分校</td></tr><tr><td>Dougherty V.</td><td>11.7274</td><td>0.5808</td><td>0.3243(16)</td><td>1(21)</td><td>1</td><td>加州大学圣芭芭拉分校</td></tr><tr><td>Bell S.</td><td>10.6983</td><td>0.5808</td><td>0.3227(17)</td><td>2(14)</td><td>2</td><td>萨斯喀彻温大学</td></tr></table></body></html>

(注： $F _ { i }$ (R)代表学者综合影响力在此社区的排名,H(R)是在本期刊中的H指数排名,NP 是学者发表的论文总数。)

表2综合影响力排名前17位社区成员基本情况表  

<html><body><table><tr><td>学者</td><td>FCvi</td><td>FCOvi</td><td>Fvi (R)</td><td>H(R)</td><td>NP</td><td>学者机构</td></tr><tr><td>Cox K. R.</td><td>211.6675</td><td>0.2113</td><td>0.6255(1)</td><td>4(3)</td><td>8</td><td>俄亥俄州立大学</td></tr><tr><td>Mair A.</td><td>97.6657</td><td>0.8160</td><td>0.5831(2)</td><td>2(5)</td><td>2</td><td>西弗吉尼亚大学</td></tr><tr><td>Brown L. A.</td><td>142.0612</td><td>0.0274</td><td>0.4511(3)</td><td>7(1)</td><td>9</td><td>爱荷华大学</td></tr><tr><td>Jarosz L.</td><td>2.4546</td><td>1</td><td>0.4376(4)</td><td>2(5)</td><td>5</td><td>华盛顿大学</td></tr><tr><td>Bonds A.</td><td>1.6364</td><td>1</td><td>0.4366(5)</td><td>2(5)</td><td>2</td><td>威斯康星大学</td></tr><tr><td>Lawson V. A.</td><td>37.9088</td><td>0.2387</td><td>0.2028(6)</td><td>7(1)</td><td>8</td><td>华盛顿大学</td></tr><tr><td>Silvey R.</td><td>47.3336</td><td>0</td><td>0.1699(7)</td><td>2(5)</td><td>5</td><td>多伦多大学</td></tr><tr><td>Longbrake D. B.</td><td>19.6665</td><td>0.2113</td><td>0.1464(8)</td><td>2(5)</td><td>2</td><td>爱荷华大学</td></tr><tr><td> Jeffery P.</td><td>6.5455</td><td>0.2113</td><td>0.1264(9)</td><td>1(11)</td><td>1</td><td>爱丁堡大学</td></tr><tr><td>Chung S.</td><td>5.3333</td><td>0.2113</td><td>0.1253(10)</td><td>1(11)</td><td>1</td><td>西伊利诺斯州大学</td></tr><tr><td>Jeffery R.</td><td>4.3637</td><td>0.2113</td><td>0.1245(11)</td><td>1(11)</td><td>1</td><td>爱丁堡大学</td></tr><tr><td>Young S.</td><td>0.3333</td><td>0.2113</td><td>0.1221(12)</td><td>1(11)</td><td>2</td><td>威斯康星大学</td></tr><tr><td>Lobao L.</td><td>20.1820</td><td>0</td><td>0.0743(13)</td><td>1(11)</td><td>1</td><td>俄亥俄州立大学</td></tr><tr><td>Jeffrey C.</td><td>13.7577</td><td>0.0274</td><td>0.0540(14)</td><td>2(5)</td><td>4</td><td>爱丁堡大学</td></tr><tr><td>Rulli J.</td><td>10.0910</td><td>0.0274</td><td>0.0413(15)</td><td>1(11)</td><td>1</td><td>俄亥俄州立大学</td></tr><tr><td>Sparke M.</td><td>0</td><td>0.0274</td><td>0.0168(16)</td><td>3(4)</td><td>5</td><td>华盛顿大学</td></tr><tr><td>Rankin K. N.</td><td>0</td><td>0.0274</td><td>0.0166(17)</td><td>1(11)</td><td>3</td><td>多伦多大学</td></tr></table></body></html>

表3综合影响力排名前17位社区成员基本情况表  

<html><body><table><tr><td>学者</td><td>FCvi</td><td>FCOvi</td><td>Fvi (R)</td><td>H(R)</td><td>NP</td><td>学者机构</td></tr><tr><td>Balling R. C.</td><td>54.2732</td><td>0.6957</td><td>0.5548(1)</td><td>5(3)</td><td>8</td><td>亚利桑那州立大学</td></tr><tr><td>Graf W. L.</td><td>119.0000</td><td>0.0000</td><td>0.5379(2)</td><td>6(2)</td><td>8</td><td>南卡罗莱纳州立大学</td></tr><tr><td>Wells S. G.</td><td>19.9998</td><td>1.0000</td><td>0.5128(3)</td><td>1(21)</td><td>1</td><td>亚利桑那州立大学</td></tr><tr><td>Mchugh K. E.</td><td>42.4548</td><td>0.3393</td><td>0.3494(4)</td><td>3（8)</td><td>4</td><td>亚利桑那州立大学</td></tr><tr><td>Miller H. J.</td><td>59.2803</td><td>0.0117</td><td>0.3356(5)</td><td>4(6)</td><td>4</td><td>犹他大学</td></tr><tr><td>Mings R. C.</td><td>19.9998</td><td>0.4586</td><td>0.3101(6)</td><td>1(21)</td><td>1</td><td>亚利桑那州立大学</td></tr><tr><td>Ellis A.W.</td><td>3.8322</td><td>0.5252</td><td>0.3011(7)</td><td>2(13)</td><td>2</td><td>亚利桑那州立大学</td></tr><tr><td>Ohuallachain B.</td><td>46.6669</td><td>0</td><td>0.2715(8)</td><td>5(3)</td><td>5</td><td>亚利桑那州立大学</td></tr><tr><td>Reid N.</td><td>16.9696</td><td>0.3510</td><td>0.2459(9)</td><td>2(13)</td><td>2</td><td>亚利桑那州立大学</td></tr><tr><td>Gober P.</td><td>30.3469</td><td>0.1822</td><td>0.2261(10)</td><td>7(1)</td><td>11</td><td>亚利桑那州立大学</td></tr><tr><td>Kirkwood C. W.</td><td>7.6643</td><td>0.3393</td><td>0.2143(11)</td><td>1(21)</td><td>1</td><td>亚利桑那州立大学</td></tr><tr><td>Deitrick S.</td><td>3.0657</td><td>0.3393</td><td>0.2061(12)</td><td>1(21)</td><td>1</td><td>亚利桑那州立大学</td></tr><tr><td>Wentz E. A.</td><td>30.0665</td><td>0.0634</td><td>0.1905(13)</td><td>3（8)</td><td>4</td><td>亚利桑那州立大学</td></tr><tr><td>Fan C. C.</td><td>28.0001</td><td>0.0117</td><td>0.1709(14)</td><td>4(6)</td><td>9</td><td>加州大学圣芭芭拉分校</td></tr><tr><td>Alford-Teaster J.</td><td>0.7200</td><td>0.2530</td><td>0.1552(15)</td><td>1(21)</td><td>1</td><td>达特茅斯学院</td></tr><tr><td>Onega T.</td><td>0.4800</td><td>0.2530</td><td>0.1550(16)</td><td>1(21)</td><td>1</td><td>达特茅斯学院</td></tr><tr><td>Wang D. M.</td><td>0.3600</td><td>0.2530</td><td>0.1549(17)</td><td>1(21)</td><td>1</td><td>达特茅斯学院</td></tr></table></body></html>

# 4结语

以《会刊》为例，基于合著论文关系建立学术合作网络，识别并评价学术社区。利用社区生命周期分析方法研究学术网络中的学术社区，分析学术社区成长演化的原因。采用学者论文影响力和合作影响力双重测度对社区中学者进行评价，挖掘出学术社区中的杰出学者，为社区的研究趋势分析奠定基础。

对三个影响力最大的学术社区分析发现：在美国地理学，尤其是人文地理学的发展过程中，加州大学圣芭芭拉分校社区的学者在美国地理学发展中起着巨大的推动作用；俄亥俄州立大学社区的学者在政治地理学、经济地理学领域占有一席之地；亚利桑那州立大学作为研究气象气候地理与人文地理相结合的一个新兴社区发展迅猛，反映了未来地理学的发展可能倾向于人们生活环境相关的研究，研究气候变化、地理关联在社会发展中的分析与应用可能是未来不错的选择。此外，分析结果表明本文提出的社区分析方法，能从社区学者角度分析解释社区研究热点变化，利用本文指标挖掘出综合影响力大的学者，在社区的生命周期中发挥着至关重要的作用。

由于《会刊》是美国的期刊，数据来源单一，社区的成员大多数来自美国、加拿大，研究范围多为欧美地区，因此收录的文章可能有一定的地域偏好，可能导致学术社区的组成相对单薄，增加不同来源的期刊数据能够进一步提升研究结果的可信性。目前的研究对内容分析相对较浅，生命周期的讨论重点在拐点和杰出学者的贡献上，未来将从不同社区文章的语义角度进行深度分析，并结合社区学者的研究方向，对社区成长进行更深层次的讨论，从各社区杰出学者的研究热点变化探讨美国地理学发展的潜在趋势。

# 参考文献：

[1]苗蕊，刘鲁．科学家合作网络中的社区发现[J].情报学报, 2011,30(12):1312-1318.(Miao Rui,Liu Lu.Community Detection in Scientific Collaboration Network[J]. Journal of the China Society for Scientific and Technical Information, 2011,30(12):1312-1318.)   
[2] 任妮，周建农．合著网络加权模式下科研团队的发现与评 价研究[J]．现代图书情报技术，2015(9)：68-75.(Ren Ni, Zhou Jiannong.The Discovery and Evaluation of Research Team Under the Mode of Weighted Co-Author Network[J]. New Technology of Library and Information Service, 2015(9):68-75.)   
[3] Newman ME.Scientific Collaboration Networks.I.Network Construction and Fundamental Results[J]. Physical Review E: Statistical Nonlinear & Soft Matter Physics,2001,64:Article No. 016131.   
[4]Barabasi AL,Jeong H, Néda Z,et al. Evolution of the Social Network ofScientificCollaborations[J]. PhysicaA: Statistical Mechanics & Its Applications,2002,311(3-4): 590-614.   
[5]Gibson D，Kleinberg J，Raghavan P. Inferring Web Communities from Link Topology[C]/Proceedings of ACM Conference on Hypertext and Hypermedia $\because$ Links, Objects, Time and Space—Structure in Hypermedia Systems: Links, Objects,Time and Space—Structure in Hypermedia Systems, Pittsburgh, USA. New York,USA: ACM,1998: 225-234.   
[6]Flake G W, Lawrence S,Giles C L,et al. Self-Organization and Identification of Web Communities[J]. Computer, 2002, 35(3): 66-71.   
[7]Adamic L A,Adar E.Friends and Neighbors on the Web[J]. Social Networks,2003,25(3): 211-230.   
[8]Van Raan A F J. Statistical Properties of Bibliometric Indicators: Research Group Indicator Distributionsand Correlations [J]. Journal of the American Society for Information Science and Technology,2006,57(3): 408-430.   
[9]李亮，朱庆华．社会网络分析方法在合著分析中的实证研 究[J]．情报科学，2008，26(4):549-555.(Li Liang，Zhu Qinghua.An Empirical Study of Coauthorship Analysis Using Social Network Analysis[J]. Information Science,2008, 26(4): 549-555.)   
[10] 李盛庆，蔡国永．复杂网络领域科研合著网络演化及知识 传播特点研究[J]．现代图书情报技术，2013(5)：64-72.(Li Shengqing,Cai Guoyong. Study on Network Evolution and KnowledgeDisseminationofScientificCollaboration Network in the Field of Complex Networks[J]. New Technology of Library and Information Service,2013(5): 64-72.)   
[11] Sun S，Manson S M. Social Network Analysis of the Academic GIScience Community[J]. Professional Geographer, 2011,63(1): 18-33.   
[12]金碧辉，Ronald R.科学家为自已设计了一项评价指标：h 指数[J]．科学观察,2006,1(1):8-9.(Jin Bihui，Ronald R. R-index and AR-index: Complementing Indicatorsto H-index[J]. Science Focus,2006,1(1): 8-9.)   
[13]杜建，张玢，唐小利．作者学术影响力双重测度探讨：引 用影响力与合作影响力之整合[J].情报学报，2014，33 (4): 388-395.(Du Jian,Zhang Bin,Tang Xiaoli. Two-dimensional Measurement for Academic Influence of Researchers: Integration of Citation Impact and Collaboration Impact[J]. Journal of the China Society for Scientific and Technical Information,2014,33 (4): 388-395.)   
[14]Takeda H,Truex D P,Cuellar M J.Evaluating Scholarly Influence Through Social Network Analysis: the Next Step in Evaluating Scholarly Influence[C]/Proceedings of the 16th AmericasConferenceon Information Systems，Lima, Peru.2011.   
[15]Truex D,Cuellar M,Takeda H,et al. The Scholarly Influence of Heinz Klein: Ideational and Social Measures of his Impact on IS Research and IS Scholars[J].European Journal of Information Systems,2011,20(4): 422-439.   
[16]李纲，刘先红．基于合作网络中心性指标的科研团队学术 带头人识别研究[J]．科技管理研究，2016，36(8): 127-132.(Li Gang， Liu Xianhong. Research onthe Identification of Academic Leaders in Research Teams Based on Centrality Indexes of Cooperation Network[J]. Science and Technology Management Research． 2016,36 (8): 127-132.)   
[17] BonacichP.TechniqueforAnalyzingOverlapping Memberships[J]. SociologicalMethodology，1972，4: 176-185.   
[18] Bonacich P. Factoring and Weighting Approaches to Status Scoresand Clique Identification[J]. The Journalof Mathematical Sociology,1972,2(1): 113-120.   
[19]Hwang C L,Yoon K P. Multiple Attribute Decision Making. Methods and Applications.A State-of-the-Art Survey[M]. Springer-Verlag,1981.   
[20] 吴巧新，吴殿廷，刘睿文，等．美国地理学百年发展脉络 分析——基于《Annals of the Association of American Geographers》学术论文的统计分析[J]．地球科学进展, 2007,22(11):1118-1128.(Wu Qiaoxin，Wu Dianting，Li Ruiwen,et al.The Development Venation of Geography in America during the Past Hundred Years—Based on the Statistical Analysis of Annals of the Association of American Geographers[J]. Advances in Earth Science,2007,22(11): 1118-1128.)   
[21] Blondel V D,Guillaume JL，Lambiotte R,et al.Fast Unfolding of Communities in Large Networks[J]. Journal of Statistical Mechanics: Theory and Experiment,2008(10): 155-168.   
[22] Robinson A H,Bryson R A.A Method for Describing QuantitativelytheCorrespondenceofGeographical Distributions [J].Annals of the Association of American Geographers,1957,47(4): 379-391.   
[23]Martin G J,James P E.All Possible Worlds:A History of Geographical Ideas[J].The Geographical Journal,1994,160 (3): 346-347.   
[24]Hart JF.Presidential Address:The Highest Form of the Geographer's Art[J].Annals of the Association of American Geographers,1982,72(1):1-29.   
[25]Golledge R G, Church R,Dozier J,et al. Commentary on “The Highest Form of the Geographer's Art"[J] Annals of the Association of American Geographers,1982,72(4):557-558.   
[26]Beaverstock JV, Smith RG, TaylorPJ.World-City Network: A New Metageography?[J].Annals of the Association of American Geographers,2000,90(1):123-134.   
[27]CoxKR,MairA.Locality and Community in the Politics of Local Economic Development[J].Annals of the Association of American Geographers,1988,78(2):307-325.   
[28]Labao L,Rulli J,Brown L A.Macro-Level Theory and Local-Level Inequality:Industrial Structure,Institutional Arrangements and the Political Economy of Redistribution, 1970 to 1990[J].Annals of the Association of American Geographers,1999,89(4):571-601.   
[29]Balling R C,Wells S G. Historical Rainfall Patterns and Arroyo Activity Within the ZuniRiverDrainage Basin,New Mexico[J]. Annalsof theAssociation of American

Geographers,1990,80(4):603-617.

# 作者贡献声明：

卿雅娴：采集、清洗和分析数据，进行实验与结果分析，论文起草;  
李锐：提出研究思路，设计研究方案，论文最终版本修订;  
吴华意：设计论文框架结构，修改论文。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail:qingyaxian@whu.edu.cn。[1]卿雅娴，李锐，吴华意.OriginalAAGPapers.csv.1911-2014年《美国地理学家联合会会刊》所有文献相关数据[2]卿雅娴，李锐，吴华意.Co_authorNetworkNodes.csv.《美国地理学家联合会会刊》学术合作网络的学者节点数据.[3]卿雅娴，李锐，吴华意.Co_authorNetworkEdges.csv.《美国地理学家联合会会刊》学术合作网络边数据.

收稿日期:2016-12-29   
收修改稿日期:2017-04-08

# Analyzing Academic Community Based on Co-author Network

Qing Yaxian'Li Rui1,²Wu Huayi1,2 1(State Key Laboratory of Surveying, Mapping and Remote Sensing, Wuhan University, Wuhan 430079,China) 2(Collaborative Innovation Center of Geospatial Technology, Wuhan 430079, China)

Abstract:[Objective] This paper aims to categorize and evaluate the academic communities and identify their development and changing rules by analyzing the co-author network.[Methods] First,we used the fastcommunity discovering algorithm to locate the academic communities from the co-author network.Then,we proposed an index to evaluate the academic impacts of scholars from the retrieved academic communities.Finally,we chose three most influential communities toexplore their lifecycles.[Results]Based onthe dataof the Journal of Annals of the Asociation of American Geographers,the proposed index could efectively identify leading researchers as wellas the changing trends of research topics.[Limitations] We only collcted data from one journal，which might yield in-complete results.[Conclusions] The proposed method could analyze the academic community from various aspects and provide scientific knowledge for scholars from different fields.

Keywords: The Journal of Annals of the Association of American GeographersAcademic Community Lifecycle AnalysisScholar Evaluation