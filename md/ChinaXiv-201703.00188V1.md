# 大数据的核心问题与研究体系

靳小龙 王元卓 程学旗

# 1引言

# 1.1研究背景

近年来，大数据迅速发展成为科技界和企业界甚至世界各国政府关注的热点。《自然（Nature)》和《科学（Science）》等杂志相继出版专刊来探讨大数据带来的挑战和机遇。著名管理咨询公司麦肯锡声称，“数据已经渗透到当今每一个行业和业务职能领域，成为重要的生产因素。人们对于大数据的挖掘和运用，预示着新一波生产力增长和消费者盈余浪潮的到来”。在这样的背景下，美国政府2012年宣布投资2亿美元启动"大数据研究和发展计划”，这是继1993年美国宣布"信息高速公路"计划后的又一次重大科技发展部署。美国政府认为大数据是“未来的新石油”，一个国家拥有数据的规模和运用数据的能力将成为综合国力的重要组成部分，对数据的占有和控制将成为国家间和企业间新的争夺焦点。大数据已成为社会各界关注的新焦点，“大数据时代"已然来临。

一般意义上，大数据是指无法在可容忍的时间内用现有IT 技术和软硬件工具对其进行感知、获取、管理、处理和服务的数据集合。以数据为中心的传统学科（如基因组学、天体物理学和脑科学等）的研究工作产生了越来越多的数据。例如，用电子显微镜重建大脑中的突触网络，1立方毫米大脑的图像数据就超过 $\mathbf { 1 } \mathbf { P B } ^ { 2 }$ 。但近年来大数据数量的飙升主要来自人们的日常生活，特别是互联网公司的服务。据著名咨询公司IDC 的统计，2011年全球被创建和复制的数据总量为 $1 . 8 Z \mathbf { B } ^ { 3 }$ ，其中 $7 5 \%$ 来自于个人（主要是图片、视频和音乐)，远远超过人类有史以来所有印刷材料的数据总量（200PB)。谷歌（Google）公司每月处理的数据量超过400PB；百度每天大约要处理几十PB数据；Facebook（脸书）注册用户超过10亿，每月上传的照片超过10亿张，每天生成 $3 0 0 \mathrm { T B } ^ { 4 }$ 以上的日志数据。总之，随着互联网、物联网、云计算等技术的迅猛发展，网络空间中各类应用的层出不穷引发了数据规模的爆炸式增长。

与传统规模的数据工程相比，大数据具有几个显著的特征：（1）数据集合的规模不断扩大，已经从GB、TB 再到 PB，甚至已经开始以 $\mathrm { E B } ^ { 5 }$ 和 ZB 来计数。IDC 的研究报告称，未来十年全球大数据将增加50倍，管理数据仓库的服务器的数量将增加10倍以便这一增长；（2）大数据类型繁多，包括结构化数据、半结构化数据和非结构化数据。现代互联网应用呈现出非结构化数据大幅增长的特点，至2012年末非结构化数据占有比例会达到整个数据量的 $7 5 \%$ 以上；（3)产生速度快，处理能力要求高。根据 IDC 的"数字宇宙（DigitalUniverse）”报告，预计到2020年，全球数据使用量将达到35.2ZB；在如此海量的数据面前，处理数据的效率就是企业的生命。大数据往往以数据流的形式动态、快速地产生和演变，具有很强的时效性，只有把握好对数据流的掌控才能有效利用这些数据；（4）数据真伪难辨，可靠性要求更严格。大数据的集合和高密度的测量将令"错误发现"的风险增长。斯坦福大学的统计学教授特来沃尔-哈斯迪(TrevorHastie)称，如果想要在庞大的数据"干草垛"中找到一根有意义的"针”，那么所将面临的问题就是"许多稻草看起来就像是针一样”；（5）数据价值大，但密度低，挖掘难度大。价值密度的高低与数据总量的大小成反比。如何通过强大的机器算法更迅速地完成数据的价值"提取"成为目前大数据背景下亟待解决的难题。

# 1.2研究意义

大数据研究与应用是国家安全和经济发展的战略性需求，是国民经济核心产业信息化升级的重要推动力量，同时正在引发科研范式的变革。

# 1.2.1大数据的研究与应用是国家发展的战略需求

当前全球已全面进入信息时代。互联网、物联网与云计算等新兴IT技术的广泛应用，使得全球数据正以前所未有的速度剧增，数据类型也变得越来越复杂。数据的深度分析和利用将对推动经济持续增长、提升国家的竞争力起到重要的作用。大数据时代对海量数据的积累、加工和利用能力将成为国力的新标志。一个国家在网络空间的数据主权更将是继海、陆、空、天四个空间之后另一个大国博弈的空间。“十八大"报告中明确提出网络空间与深海、深空是我们国家核心利益的关键领域。在大数据领域的落后，意味着产业战略制高点失守，更意味着国家安全将在网络空间出现漏洞。美国2012年3月发布的《大数据研究和发展计划》不仅是一个推动美国在高技术领域继续领先的战略计划，更是一个保护美国国家安全、推动社会经济发展的计划。以美国为代表的西方国家在国家顶层推动下，正在通过增强大数据领域竞争能力进一步提高自己的综合国力。可以预见未来国家之间的经济与政治竞争将是大数据引领的竞争。

# 1.2.2大数据研究是国民经济核心产业信息化升级的重要推动力量

大数据带来的问题和困难是当下国民经济中许多行业面临的共同挑战，是这些行业数字化与信息化的障碍和发展瓶颈。对大数据共性问题的研究，特别是核心技术的突破，将使产业界能够理清数据关联产生的复杂性，掌握数据冗余与缺失双重特征引起的不确定性，进而能够根据实际需求从大数据中挖掘出所蕴含的信息、知识甚至是智慧，最终达到充分利用大数据价值的目的。因此，大数据已不再是产业环节上产生的副产品，反而成为联系社会经济活动各个环节的关键纽带。在这个意义上，对大数据共性问题与核心技术的研究将是新一代信息技术融合应用的新焦点，是信息产业持续高速增长的新引擎，也是行业用户提升竞争能力的新动力。面向未来,大数据将成为新的经济增长点,企业将向分析即服务（AaaS,Analyticsas a Service）升级转型，从而改变行业的生态。在这样的背景下，全球IT界的巨头（如 IBM、Oracle（甲骨文）、谷歌、微软等）都已经开始了大数据时代的技术布局。大数据和云计算被看作是一个硬币的正反两面，大数据是云计算的一个杀手级应用，云计算为大数据提供IT 基础。大数据和云计算的紧密耦合必将改变互联网生态，甚至影响整个产业的格局。

# 1.2.3大数据的基础研究将引发科学研究思维与方法的变革

大数据的出现引起了科技界对科学研究方法论的重新审视，正在引发科学研究思维与方法的一场革命。最早的科学研究只有实验科学，随后出现了以研究各种定律和定理为特征的理论科学。而由于理论分析方法在许多问题上过于复杂以致难以解决实际问题，人们开始寻求模拟的方法，这又产生了计算科学。大数据的出现催生了一种新的科研模式，即面对大数据，科研人员可以从数据中直接查找或挖掘所需要的信息、知识和智慧，甚至无需直接接触研究的对象。2007年，已故的图灵奖得主吉姆·格雷（JimGray）在他最后一次演讲中描绘了面对大数据的数据密集型科学研究的“第四范式（TheFourth Paradigm)”，把数据密集型科学从计算科学中单独区分开来。格雷认为，要解决我们面临的某些最棘手的全球性挑战，“第四范式"可能是唯一具有系统性的方法。其实，“第四范式"不仅是科研方式的变化，也是人们思维方式的大转变。

# 2 国内外研究现状

当前对大数据的研究和应用大致可以分为大数据的复杂性和计算模型、大数据的感知与表示、内容建模与语义理解、大数据计算的架构体系等几个方面。下面分别对其具体的研究现状进行阐述。

# 2.1大数据的复杂性和计算模型

针对大数据的复杂性，前期的研究主要是对网络上多种来源的数据进行性质分析和规律探索，很多学者尝试运用图论和统计分析等方法对数据进行定量分析。特别值得注意的是，人们已经发现了复杂的网络大数据之中存在一些统计规律性。譬如，巴拉巴西（Barabasi)等人通过对大量电子邮件数据的分析，证明人类行为中的通信、娱乐和工作模式并不遵循泊松过程，而是基于决策排队过程的结果，即由于存在优先次序导致任务执行时间具有重尾效应[2]。克莱因伯格（Kleinberg）等人通过分散方法等随机图算法发现大规模社会网络的小世界网络规律，利用理论模型解释了六度分割等现象[。美国卡内基梅隆大学法魯托斯（Faloutsos）等人通过对博客数据的分析，发现博客中的时序行为是非均匀且突发的，具有自相似的特性[3]。莱斯科韦茨（Leskovec）等通过对等借贷系统的数据来研究网络借贷的竞标机制，发现类似数据中带有群羊效应74]。面对大数据的复杂性，还有一些学者尝试使用统计方法和复杂网络方法来研究如何对大数据进行按需约简。相关数据约简的方法多数集中在对样本属性的约简上，其目的是在保持分类能力不变的情况下，删除其中不重要的和冗余的属性，同时提取出重要的属性信息。例如，塞万提斯（Cervantes）等人使用最小封闭球聚类，提出基于支持向量机的数据约简方法[10]。但这类基于统计的方法在处理大数据时其时效性难以保证。

针对大数据的计算理论和算法的研究目前主要集中在大数据机器学习的基础理论、参数估计方法、优化算法等方面，形成的一系列成果为大数据高效计算提供了理论支持。普林斯顿大学的布莱（Blei）等人针对大规模网络文本数据的主题建模，提出了在线学习算法，为大数据下的非参数模型的高效估计奠定基础9]。斯坦福大学的马哈尼（Mahoney）提出了随机算法实现快速矩阵近似分解，并给出了近似值和真实值差距的理论边界8]。法魯托斯等人提出了大规模张量分析方法，可以比原算法速度提高两个数量级。美国加州大学伯克利分校乔丹（Jordan）等人开展了大数据分析的理论基础研究，目前已有的成果包括分布式优化算法[5]和大数据非参数估计方法等。

# 2.2大数据的感知与表示

爬虫（crawler）是当前大数据感知和获取的基本技术，已得到了迅速发展和广泛应用，但仍不能有效应对被称为Web 2.0的新一代互联网数据[14]。为了有效利用网络大数据，需要将异构、低质量的网络数据转化为结构统一的高质量数据。因此业界提出了一系列数据抽取算法以应对大数据的异构性[15] [27]，应用经过扩展的传统数据集成技术从多个异构数据源集成数据[16]，并开始将过去一些数据清洗和数据质量控制方面的研究应用于网络数据质量控制[23,24]。但总的来说，将这些技术直接用于大数据处理，在数据处理的规模和得到的数据质量方面还不能令人满意。另一方面，人们很早就认识到了动态性和时效性是大数据的重要特性[16]，数据流（data stream）[21][13]和时间序列（time series）[19]是表示和处理数据动态性和时效性的主要技术。同样，从数据的可处理规模和功能上，传统数据流和时间序列技术还无法满足大数据处理的需求。

对大数据的表示主要有图模型与张量两大类方法。陈晨（Chen）等人于2008年首次提出了图上在线分析过程（Graph OLAP，Online Analytical Processing on Graphs）的概念模型，根据边属性和结点属性，将Graph OLAP中的维度划分成信息维和拓扑维[17]。并进一步将信息维上的聚集操作定义为信息在线分析过程（I-OLAP，Information OLAP）,将拓扑维上的聚集操作定义为拓扑在线分析过程(T-OLAP，Topology OLAP)。田媛媛（Tian）等人提出了能够为网络提供不同粒度的概要信息的两个操作符 SNAP 和 $\mathbf { k }$ -SNAP[26]。波尔蒂（Boldi）等研究了图的压缩方法[12]，但是只关注了如何有效地存储网页的链接信息来对Web 图进行压缩，以方便网页排序（Page-Rank）和权威向量的计算，并没有涉及图的结构问题。除了图之外，张量是另一个广泛关注的大数据表示方案。由于没有破坏数据的领域、局部和全局结构，与向量比较，数据的张量形式表达能最大限度地保持原始数据的固有信息。瓦西列斯库（Vasilescu）等人用张量形式成功地表达了光照、视角、类别等几个模态的人脸数据库[25]。自此，张量表示在图像、视频、文档等领域中得到了深入研究。辛顿（Hinton）等革命性地提出了通过深度信念网（Deep Belief Networks DBNs）的非监督贪心逐层训练的深度学习（Deep Learming）算法，使得研究在统一的平台上进行特征提取的方法变为可能[20]。阿卡（Acar）等认为，高维大数据可以用张量来表达，而基于张量计算的方法可以从高维大数据中提取有用信息[1]。潘（音译，Phan）等提出用张量表示图像、纹理、音乐谱的方法[22]。针对大数据下的张量数据(Big Tensor Data)，2013 年斯蒂若帕洛斯（Sidiropoulos）提出了基于压缩感知的核张量计算方法[33]。

# 2.3大数据的内容建模与语义理解

由于大数据的规模巨大、高维、异构、多源等特性，当前在大数据内容建模方面的工作主要集中在数据的实体、类别和属性的提取与分析等方面。在大数据中实体的属性学习方面，鲁萨科夫斯基（Russakovsky）等提出了利用 ImageNet 进行属性学习的方法[31]。派端克（Parikh）等进一步提出了相对属性的学习方法[32]。2012年，斯坦福大学和谷歌的研究人员构建了一个多达10亿个连接的深度学习网络。该网络通过对来自YouTube（优兔）的1000万幅视频帧的自主学习，学会了识别猫的面孔[28]。他们还对 2.2万个类别进行了图像分类，准确率达到了 $1 5 . 8 \%$ ，比当前最先进的方法提高了 $70 \%$ 。而传统的方法需要通过对图像加标签、提取特征、训练分类器等步骤才能够实现对概念的识别。针对大数据内容理解的另一个重要进展是基于数据驱动（Data-Driven）方法的提出。2008年，托拉尔巴（Torralba）等人利用网络中的图像构建了一个包含八千万幅图像的数据，并利用该数据库完成了基于搜索和词汇树相结合的图像中物体、人物、位置等信息的理解[29]；王心敬（音译，Wang）等人构建了一个包含20亿幅图像的数据库，利用该数据库实现了一种基于近似图像搜索的图像标注方法[30]。总体而言，目前针对大数据内容建模的研究主要针对大数据的某一特性展开，全面考虑大数据关键特征的研究工作还很少。

在语义理解方面，语义网作为语义的核心载体，已经得到了实际应用，利用语义网研究语义理解，也开始得到学术界的关注。克里斯蒂安（Christian）等人提出了利用关联开放数据（LOD，Linked OpenData）的思想在Web上不同数据源之间创建语义关联[34]，促进异构数据源之间的互操作；武汉大学何克清等人提出元模型与本体相融合的建模体系[35]，通过本体到元模型、模型、元数据的语义标注，在元级上屏蔽模型的差异性，以及实现语义网上异构信息模型间的语义互操作，达到无歧义语义理解。由于大众的广泛参与，群体智能（Collective Intelligence）被视为是一种从人类大规模交互中所涌现出来的社区知识库（如维基百科（Wikipedia)）[36]，基于此提出的交互式通信模式更便于网络内容的理解与共享，从而解决一些图灵机智能难以解决的语义理解问题。因此，可以通过众包（Crowdsourcing）的方式，借助群体智能，来分析和理解互联网上的各种信息。例如，使用社会化标注来促进语义浮现。这些系统（如del.icio.us）中尽管没有集中统一的控制，但是描述资源的标签分布仍随时间推移呈现出一种稳定的幂律分布[37]，可以被有效地用于大众分类法（Folksonomy）的构建等[38]，以辅助不同的利益攸关方对模型内容进行理解。但是，现有方法难以满足大数据特征的复杂性、动态性和隐蔽性等特点，需要进一步研究新的技术方法和互操作机制来加以改进。

# 2.4大数据的存储与架构体系

大数据的架构体系研究首先需要关注的问题就是大数据如何存储。在数据存储的基础上，为了应对大数据的快速以及高效可靠处理，需要建立大数据计算的编程模式以及相关的优化方法。大数据存储的形式包括分布式的文件系统、分布式的键值对存储以及分布式数据库存储。当前的研究也集中在这三个方面，并依据应用的需求进行相关的优化。在分布式文件系统研究方面，传统的分布式文件系统 NFS 应用最为广泛[39]。为了应对搜索引擎数据，谷歌在 2003 年公布了其能够用于存储网页数据的分布式文件系统技术GFS[40]。开源社区据此开发了适合部署在廉价的机器上的 Hadoop 分布式文件系统 HDFS[41]。微软自行开发的Cosmos[42支撑着其搜索、广告等业务。2010 年 Facebook 推出了专门针对海量小文件的文件系统Haystack[43],以降低对磁盘寻道速度的要求,类似的还有淘宝推出的文件系统 TFS[44]。键值对存储也是一大类重要的存储系统。2007年亚马逊（Amazon）提出的Dynamo 以键值为模式，是一个真正意义上的去中心化的完全分布式存储系统，具有高可靠性、高可用性且具有良好的容错机制[46]。由于模型的简单性，键值对存储在应用模型不是很复杂的情况下能够获得更好的性能。当然，数据库模型还是一大类非常重要的存储模型。Bigtable 是谷歌开发的基于GFS 和Chubby的非关系数据库，是一个稀疏的、分布式的、持久化存储的多维度排序映射表[45]。为克服其缺乏一致性支持的缺点，2011 年谷歌将其改进为 Megastore 系统[47]，但是改进后的系统性能不是很高。2012年谷歌进一步开发了 Spanner 系统，能够进一步加强一致性，将数据分布到了全球的规模，性能有了一定提高[48]。Spanner 是第一个可以实现全球规模扩展并且支持外部一致的事务的数据库。

从编程模式上看，实时数据处理是大数据分析的一个核心需求。各个大公司都有相关的研究，例如 Twitter 的 Storm[49]、Yahoo 的 $\mathbf { S 4 } ^ { [ 5 0 ] }$ 以及Linkedin 的Kafka[51]。流式大数据需要进行线速处理，程序的复杂程度不能太高，或者需要进行数据的采样操作。而批处理则不然，要求能够对大规模的数据进行细致的分析与处理，所需时间较实时流处理为长。谷歌公司在2004 年提出的 MapReduce[52编程模型是最具代表性的批处理模式。在此基础上，为支持增量计算，谷歌提出增量处理系统 Percolator[53]。微软则提出了 Nectar[54]和 DryadInc[55]。为了和 MapReduce 兼容，Incoop[56和 IncMR[57实现了 MapReduce 框架下的增量计算。雅虎（Yahoo）的 Nova[58]则支持有状态的增量数据计算模式。HOP[59]在 MapReduce 处理的过程中引入管道(pipeline)的概念。人民大学WAMDM 实验室在HOP 基础上开发的COLA 系统[在HOP 系统的基础上增加了数据采样、结果估计、置信区间计算等功能模块，在一定程度上提高了HOP 的实时性。在模型混合方面主要工作都围绕着MapReduce 展开：文献[61]着重探讨了将 MapReduce 模型应用到流处理这种单遍分析(one-pass analytics)的应用时，在架构上应当进行怎样的调整。StreamMapReduce[62]结合事件流处理(Event Stream Processing)的特点，对 MapReduce 中的 Mapper 和Reducer 进行重新定义，增加了持续的、低延迟的数据处理能力。

# 3 大数据研究的核心问题

尽管大数据的涌现为人们提供了前所未有的宝贵机遇，但同时也提出了重大的挑战。首先，大数据规模巨大、分布广泛、动态演变、模态多样、关联复杂、真伪难辨等一系列特性带来了数据复杂性的挑战。特别是大数据模式多样，内容难于理解；关联关系复杂，数据难以有效识别；质量良莠不齐，真伪难以判定。因此，需要揭示、度量并刻画数据复杂性，并厘清其中的内在关联机理。其次，大数据的数据复杂性又不可避免地带来了关于大数据是否可以计算以及计算复杂性的挑战。即便大数据可以计算，当前处理有限规模数据的计算体系已然失效，因此需要寻找大数据计算的稳定内核及计算边界，在此基础上提出新型的适应不同数据规模的计算范式。最后，大数据种种特性的综合呈现还造成大数据处理在系统层面系统复杂性的挑战。因此，又需要提出面向不同大数据模式（如离线历史数据与在线流式数据等）的新型处理系统架构以及相应的评价体系与优化策略。

# 3.1大数据复杂性的内在机理

由于大数据的出现，人们处理计算问题时获得了前所未有的大规模样本，但同时也不得不面对更加复杂的数据对象。其典型的特性是类型和模式多样、关联关系繁杂、质量良莠不齐。大数据内在的复杂性使得数据的感知、表达、理解和计算等多个环节面临着巨大的挑战，导致了传统全量数据计算模式下时空维度上计算复杂度的激增。很多传统的数据分析与挖掘任务，如检索、主题发现、语义和情感分析等，变得异常困难。然而目前，人们对大数据复杂性的内在机理及其背后的物理意义缺乏理解，对大数据的分布与协作关联等规律认识不足，对大数据的复杂性和计算复杂性的内在联系还不能完全揭示，加上缺少面向领域的大数据处理知识，凡此种种极大地制约了人们对大数据高效计算模型和方法的设计能力。有鉴于此，如何量化定义大数据复杂性的本质特征及其外在度量指标，进而研究数据复杂性的内在机理是个基础问题，需要建立多模态关联关系下的数据分布理论和模型，厘清数据复杂度和时空计算复杂度之间的内在联系，通过对数据复杂性内在机理的建模和解析，阐明大数据按需约简、降低复杂度的原理与机制，从而奠定大数据计算的理论基石。

# 3.2大数据的可计算性及新型计算范式

大数据规模巨大等特性使得传统的计算方法已经不能有效地支持大数据计算和处理。在求解大数据的问题时，需要重新审视和研究它的可计算性、计算复杂性和求解算法。特别是大数据计算不能像小样本数据集那样依赖于对全局数据的统计分析和迭代计算，所以需要突破传统计算对数据的"独立同分布"和"采样充分性"的假设。因此，研究面向大数据计算的高效新型范式，改变人们对数据计算的本质看法，提供处理和分析大数据的基本方法，支持价值驱动的特定领域应用，是大数据研究的一个核心问题。而大数据样本量充分，内在关联关系密切而复杂，价值密度分布极不均衡，这些特征对研究大数据的可计算性及建立新型计算范式提供了机遇，同时也提出了挑战。这就要求我们研究大数据的获取和表达，研究数据空间中各种关联关系及其语义特征与表示，基于数据内在结构、关联关系、产生规律及演化特点，发现针对大数据的稳定计算模型，特别是针对计算问题的大数据稳定内核和计算边界，建立局部近似整体的非确定性增量学习理论和方法，进而提出不以样本规模为变量的新型计算范式。

# 3.3大数据处理系统的效能评价与优化

大数据处理系统是支持大数据科学研究的基础平台。对于规模巨大、价值稀疏、结构复杂、变化迅速的大数据，其处理亦面临计算复杂度高、任务周期长、实时性强等难题。大数据及其处理的这些难点不仅对大数据处理系统的系统架构、计算框架、处理方法提出了新的挑战，更对大数据处理系统的运行效率及单位能耗提出了苛刻要求。对于以高效能为目标的大数据处理系统的系统架构设计、计算框架设计、处理方法设计和测试基准设计研究，其基础是大数据处理系统的效能评价与优化问题研究。这一研究具有极大的挑战性，不但要求厘清大数据的复杂性、可计算性与系统处理效率、能耗间的关系，还要综合度量系统中如系统吞吐率、并行处理能力、作业计算精度、作业单位能耗等多种效能因素，更需要考虑实际负载及资源分散重复等情况。大数据处理系统的效能评价与优化问题的解决可奠定大数据处理系统设计、实现、测试与优化的基本准则，是构建能效优化的分布式存储和处理的硬件及软件系统架构的重要依据和基础，因此是大数据科学研究必须解决的关键问题。

# 4 大数据的研究体系

为了解决大数据研究的上述核心问题，需要从基础理论、核心方法与关键技术以及应用系统三个层面展开具体研究。在基础理论层面，需要研究大数据复杂性的解析与大数据计算模型；在核心方法与技术层面，需要研究多源异构大数据感知、融合与表示，大数据内容建模与语义理解，以及感知、存储与计算融合的大数据计算系统架构体系；在应用系统层面，需要研究大数据处理的软硬一体化引擎系统。

# 4.1大数据复杂性的解析及大数据计算模型

大数据规模庞大、类型多样、关联复杂的特点导致传统全量数据计算模式不再适用，大数据计算面临基本模式的挑战。如何对大数据的复杂性深入解析，并在此基础上构建高效的大数据计算模型，成为大数据处理的核心问题。因此，在基础理论层面，需要围绕大数据复杂性的内在机理、大数据的可计算性和新型计算范式两个核心问题，研究大数据复杂性规律发现、大数据复杂特征度量与大数据的计算模型。

# (1)．大数据复杂性规律发现

对大数据复杂性规律的研究有助于理解大数据复杂模式的本质特征和生成机理，简化大数据的表征，获取更好的知识抽象，指导大数据计算模型和算法的设计。具体则需要研究针对大数据的新型统计分析技术，解决传统统计与实证分析技术在处理极大规模网络数据时的可扩展性。同时对大数据中多模态关联的数据对象之间多维、异构、隐性的关联关系进行研究，基于统计猜想和大数据驱动相结合的方式，探索大数据复杂模式的生成机理及其背后的物理意义。最后，分析大数据在时空维度上的数据分布、内在结构和协作关联的复杂性规律，形成对大数据采样降维、抽象表达和优化计算的方法论。

# (2)．大数据复杂特征度量

大数据导致了时空维度上计算复杂度的激增，传统全量数据计算模式在面对大数据时基本不可行，亟需建立面向大数据计算的数据复杂度理论，探索不依赖于样本规模的大数据高效计算模型和方法。为此目的，需要研究异构关联的大数据中复杂特征的基本因素，分析这些因素的内在联系、外在指标和度量方法。进而研究面向计算的数据复杂性度量模型，定性和定量地衡量大数据的复杂程度，厘清数据复杂度和计算复杂度的理论联系。此外，还需研究基于数据复杂度的近似计算理论和优化算法框架，以此指导人们寻找面向计算的数据内核或者数据边界的基本方法，形成大数据高效计算模型和方法设计的理论基石。

# (3).大数据的计算模型

由于大数据往往呈现出异构多模态、复杂关联、动态涌现等特点，传统的科学假设以及模型理论已经无法有效分析和预测大数据内在的规律及其蕴含的真实价值。因此，需要重新定义和度量数据的可计算性，发展以数据为中心的大数据的计算理论，设计可靠的计算算法。具体而言，需要研究面对大数据的非确定性算法理论，突破传统统计学习中的"独立同分布”假设，研究非确定化、局部增量的学习理论，提出不依赖于全量数据的新型算法理论基础；研究大数据下以数据为中心的计算模式，突破传统的“数据围绕机器"式计算，构建"以数据为中心"的推送式计算模式，探索弱 $\mathrm { C A P } ^ { 8 }$ 约束的系统架构模型及其代数计算理论，研究分布化、流式计算算法，形成通讯、存储、计算融合优化的大数据计算框架。

# 4.2多源异构大数据的感知、融合与表示

大数据应用关键的第一步是感知和融合数据并对其进行有效的表示。传统数据管理技术擅长处理结构统一、语义清楚、质量可靠的结构化数据，而大数据多源异构、良莠不齐、动态变化的特点使得感知、获取高质量数据并对其进行融合表示是一个非常具有挑战性的课题。因此，需要在核心方法与技术层面围绕大数据的可计算性和新型计算范式这一核心问题，在多源异构大数据的感知和获取、大数据的融合与质量控制、以及大数据的图与张量表示等方面展开研究，以建立大数据准确高效的感知、融合与表示方法。

# (1)．多源异构大数据的感知和获取

由于大数据的无边界分布和自组织特性，高质量数据的感知和获取是大数据处理非常重要的第一步。然而传统的基于爬虫的通用数据感知和获取技术在应对规模更大、数据类型更为复杂、更新速度更快的大数据上越来越力不从心。同时，传统信息抽取技术主要被用于小规模的文本数据处理，无法应对大数据的动态变化和多源异构所带来的挑战。因此，我们需要研究多源异构大数据的精确感知和高效获取算法，突破已有的针对小规模和静态的数据设计的爬虫架构和算法，建立实时智能收集主题相关的大数据的感知和获取框架。同时，还要研究兼顾精度和性能的大数据获取算法，分析数据获取算法的精度、稳定性与数据规模的关系，实现对非结构化异构数据的高效结构化方法，克服传统复杂抽取模型在处理大规模数据时的低性能瓶颈。

# (2)．大数据的融合与质量控制

大数据的生命力很大程度上来自于它的开放性。而这种开放性的一个负面效果就是造成了大数据质量的良莠不齐，很多数据包含了大量的噪音、冗余和错误。“大而低质量"的数据往往不能有效支撑大数据分析和应用。简单地认为数据越多越好而不关心数据的质量会使得分析的结果变得难以预料。另一方面，属于同一个实体或概念的数据往往在多个数据源中以不同的形式表示，数据集成和融合技术被用于将这些不同形式的数据进行统一和集成。传统的数据融合和质量控制技术主要针对规模较小且语义清楚的结构化数据，而面向大数据的数据融合和质量控制仍然是一个需要深入研究的问题。具体而言，需要在现有的数据集成与融合技术的基础上，结合大数据的异构性、冗余性和相关性等特性，研究大数据的数据融合和集成方法，以有效地解决大数据获取的全面性和一致性问题。另外，还需与众包、概率推理等技术结合，研究大数据的质量判定方法和去噪、去冗、清洗等质量控制方法，从而得到"大而高质量"的大数据。

# (3)．大数据的图与张量表示

大数据中的数据实体之间不是彼此独立的，往往具有一些错综复杂的关联关系。这类复杂的关联关系通常可以图结构和张量的形式来表示。一方面，如何对复杂的图结构数据进行在线分析处理，成为近年来学术界和工业界广泛关注的一个关键问题。如何为大规模图结构产生小规模且可以理解的概要信息，如何对关联关系进行压缩以便于图数据的存储和维护，都是非常重要的研究课题。因此，需要针对图数据的大规模异构动态特征，深入研究基于图数据的模型表示以及基于图数据的联机分析处理技术。另一方面，同样十分重要的是针对大数据的突出特点，充分利用张量的强大表达能力，研究大数据的一体化张量表达原理，建立从原始多源、高维数据集中选择最合适的张量表达数据模型，进而研究大数据所蕴含的各类异质特征如何在高阶张量形式下得到统一表达。

# 4.3大数据的内容建模与语义理解

传统的基于静态、浅层特征对数据建模的方法，已经无法适应当前越来越多的对数据内容深层理解和计算应用的需求。大数据的出现提供了对数据内容深层建模和语义理解的契机，然而大数据的种种特性又对其内容建模和语义理解的深度、关联性与准确性提出了挑战。因此，需要在核心方法与技术层面结合大数据的特征就大数据的特征模型、内容建模和语义理解三个方面展开研究，实现对大数据的内容理解及演变规律的把握。

# (1)．带时序的特征层次模型

针对大数据复杂、动态和隐蔽等基本特性，我们需要研究大数据的特征层次模型。具体而言，需要在范式理论的基础上，研究特征的表达范式，从特征的表达性、排他性和相似性的角度定义特征的描述规范，给出低级范式向高级范式转换的方法。同时，在特征范式的规约下，从特征结构及其索引结构两方面研究特征结构模型，以解决大数据环境下，特征的组织与管理问题。进一步研究特征结构模型上的语义操作问题，通过扩展本体代数的逻辑运算、集合运算，定义特征语义获取、特征语义更新和特征语义查询算子，探索大数据语义计算的新型范式。

# (2)．大数据特征感知与内容建模

大数据的规模与多源异构特性使得对其内容,特别是多媒体内容特征的识别成为一项十分具有挑战性的问题。因此需要探索有别于传统方法的新的解决思路，需要研究基于大数据特征的内容建模技术，以便及时准确地感知大数据的特征。具体而言，需要研究张量空间下的基于深度学习的特征提取方法，获取数据的深层语义特征；研究基于大数据的属性学习理论和方法，以及面向多源异构大数据的跨域多任务学习；最后，研究基于数据驱动的大数据内容分析与建模。

# (3)．基于知识图谱的大数据特征语义理解

大数据环境下的语义理解是基于语义的新型计算范式的核心。因此，我们需要基于知识图谱展开对大数据特征语义理解的研究。具体来说，我们需要研究面向知识图谱的领域知识迭代式获取方法，实现对特定领域中特定主题及其情境的抽取；研究基于本体和大众分类的语义标注、链接本体的协作关联推理和语义浮现技术，结合社交网络探索新型的数据链接方法，促进人-人、人-机、机-机对大数据的语义增强型内容的理解；研究面向异构大数据之间协作关联关系的内容语义互操作管理方法，解决大数据环境下内容语义如何计算的问题。

# 4.4感知、存储与计算融合的大数据计算系统架构体系

大数据对相应的计算系统提出了高性能、可扩展、高可靠和低能耗等要求。为此，我们需要围绕"大数据处理系统的效能评价与优化"这一核心问题，结合大数据的价值稀疏性和访问弱局部性的特点，研究针对能效优化的大数据分布存储和处理的系统架构。以"大数据感知、存储与计算融合"为指导思想，在性能评价体系、分布式系统架构、流式数据计算框架、在线数据处理方法等方面展开基础性研究，并对作为重要验证工具的基准测试程序及系统性能预测方法进行研究，通过设计、实现与验证的迭代完善，最终实现大数据计算系统的数据获取高吞吐、数据存储低能耗和数据计算高效率。

# (1).大数据计算基准测试程序及性能预测方法

与高性能计算不同，大数据计算的性能不仅与计算算法密切相关，而且与数据规模、数据分布和用户访问行为密切相关。当前，以数据为中心的新型计算系统缺乏有效的效能评价模型和基准测试方法，这是制约大数据处理系统体系架构优化和统一评价的主要因素。为了解决这个问题，需要研究大数据计算基准测试程序的构造方法，探索应用负载的特征表达及状态约简方法，并从数据规模、数据分布、用户行为和程序算法等多个角度建立代表性大数据计算基准测试程序集合。进一步，要分析大数据计算系统多个部件之间在缓存、副本、一致性策略等方面的相互影响，建立各种复杂条件下大数据计算系统运行时的性能行为模型，提出以小规模情况下的性能行为预测真实大系统环境性能的性能推演方法。最终，建立考虑数据质量、服务质量和运维成本等多方面因素的综合评价体系，为大数据处理系统的体系结构、系统软件和应用软件的研究提供依据。

# (2)．感知、存储与计算融合的分布式系统架构

传统的海量数据处理系统没有将数据的感知获取、存储和计算融为一体，难以同时实现数据的快速获取和高效处理，而这对大数据处理来说是至关重要的。为此需要研究存储与处理耦合的大数据计算分布式系统架构，实现处理单元和存储单元耦合部署的协同工作模式；研究利用专有硬件设备与大数据处理系统的层接方法和实现技术，解决专用硬件与通用软件的对接问题；研究软硬件协同的数据和计算双向流动理论，克服单一数据流动造成的网络延迟高和单一计算流动难以避免的负载不均衡的困难；分析大数据计算范畴的线性或非线性的流式、实时、或离线等典型数据密集型的负载特征，以及包括通用处理器在内的多种硬件对不同特征负载的计算效能，研究充分利用专用硬件分流通用处理器负载的方法和技术，并提出感知、存储与计算融合的大数据分布策略与约简方法，实现大数据规模效应下的数据可靠存储和计算持续容错。

# (3)．弱数据访问局部性的在线大数据处理方法

数据访问局部性是现代高性能计算机设计获得成功的基础。而大数据具有价值稀疏、访问局部性差的特点，所以迫切需要研究突破数据访问局部性的在线大数据处理方法。具体包括以下几个方面：研究大数据应用的数据访问特征，透过数据访问的弱局部性挖掘数据访问的关联规则；研究面向数据访问弱局部性的处理器缓存（Cache）调度算法，根据数据访问的关联规律来实现数据预取与数据缓存的双重优化；研究基于存储级内存等新型存储器件的大数据布局策略，实现海量弱访问局部性数据的内存级访问性能；研究基于访问关联性的大数据存储策略，实现方便缓存或预取的访问关联数据的集中就近存储。研究基于领域语义的大数据高效压缩理论，依据时间维度上的数据演化与溯源信息，去除重复数据、衍生数据和领域无关数据。

# 4.5大数据处理的软硬一体化引擎系统

软硬件一体化引擎系统旨在利用基础理论和核心方法与关键技术两个层面的研究成果，在感知、存储与计算相融合的大数据计算系统架构体系中把对多源异构大数据的感知、表示、建模、理解与分析等一系列核心方法和关键技术系统性地整合起来，形成大数据综合处理的有形系统。

# (1)．无栈式运行时软硬件一体化系统体系结构

体系结构的设计是实现高性能、高可靠和低能耗的一体化系统的关键。为此，需要研究体现大数据应用共性访问特征的富语义编程模型，降低大数据应用编程难度，并方便底层子系统针对多个大数据应用进行统一优化设计；研究基于数据流的多源异构大数据计算框架，使用户只需进行基于有向无环图的应用编程，而无需掌握分布式集群计算的细节；研究旁路传统操作系统的机制及方法，实现"无栈式"的系统运行时结构，并分析如何在大规模异构机群中为混合负载合理分配资源；针对资源碎片，混合负载并存以及调度算法量化评估等问题，提出大规模分布式机群自反馈式资源调度算法，从生产环境取得实际采样数据并迭代优化资源调度算法。

# (2)．大数据处理软硬一体化引擎系统

在大数据计算系统性能行为模型的指导下，面向大数据生产的实际应用需求，研究数据获取、存储、处理、交换到服务的全生命周期实现技术，研究大数据计算系统组成部分的最小共性集合，研究系统各组成部分之间的逻辑关系和接口模式，实现可同时支持多种数据计算场景的软件包—大数据处理引擎，包括数据分析和挖掘的算法。为了适应多用户在线和离线数据计算等不同的应用场景，支持数据安全性，研究多租户资源隔离、性能隔离和安全隔离机制和技术。最后集成相关技术和研究成果，在大数据计算引擎的支撑下，充分利用专用加速硬件，形成集大数据的搜索、挖掘、统计与分析于一身的软硬件一体化数据计算系统。

# 5 结束语

近几年，大数据迅速地发展成为各行各业都共同面对的问题。与传统规模的数据工程相比，大数据具有规模大、类型多、速度快、可靠性低、价值密度低等显著特征。这些特性引起了大数据在三个不同层面的复杂性，即，数据复杂性、计算复杂性与系统复杂性，同时也造成了大数据的感知、获取、存储、表示、理解、处理和分析等一系列的巨大挑战。面对上述复杂性与挑战，本文分析并提出大数据复杂性的内在机理、大数据的可计算性及新型计算范式和大数据处理系统的效能评价及优化是大数据研究的三个核心问题。在此基础上，从基础理论、核心方法与关键技术以及应用系统三个层面对由大数据复杂性的解析与大数据计算模型，多源异构大数据感知、融合与表示，大数据内容建模与语义理解，大数据计算系统架构体系，以及大数据处理的软硬一体化引擎系统所构成的研究体系进行了分析。

# 参考文献：

[1] J.Kleinberg. Complex Networks and Decentralized Search Algorithms.Proceedings of the International Congress of Mathematicians (ICM), 2006. [2] A.-L. Barabasi,The origin of bursts and heavy tails in humans dynamics,Nature 435,2O7 (2005).

[3] Mary McGlohon,Jure Leskovec,Christos Faloutsos,Mathew Hurst and Natalie Glance Finding patterns in blog shapes and blog evolution Int. Conf.on Weblogs and Social Media Boulder, CO, USA,March 26-28,2007.   
[4] S. Ceyhan, X. Shi, J. Leskovec，Dynamics of Bidding in a P2P Lending Service: Effects of Herding and Predicting Loan Success, ACM WWW International Conference on World Wide Web (WWW), 2011.   
[5] Stephen P.Boyd,Neal Parikh,Eric Chu,Borja Peleato,Jonathan Eckstein,Distributed Optimization and Statistical Learning via the Alternating Direction Method of Multipliers,Foundations and Trends in Machine Learning 3(1): 1-122, 2011.   
[6] U.Kang,Evangelos E. Papalexakis,Abhay Harpale,Christos Faloutsos,GigaTensor: scaling tensor analysis up by 100 times - algorithms and discoveries,KDD 2012:316-3241.   
[7] Ariel Kleiner，Ameet Talwalkar,Purnamrita Sarkar，Michael I. Jordan,The Big Data Bootstrap, ICML 2012.   
[8] M.W.Mahoney，“Randomized Algorithms for Matrices and Data,”Foundations and Trends in Machine Learning, NOW Publishers, Volume 3, Issue 2, 2011   
[9] Chong Wang,John William Paisley,David M. Blei,Online Variational Inference for the Hierarchical Dirichlet Process, Journal of Machine Learning Research - Proceedings Track (JMLR） 15:752-760, 2011.   
[10] Cervantes J, Li X, Yu W,Li K. Support vector machine clasification for large data sets via minimum enclosing ball clustering. Neurocomputing,71(4-6): 611-619,2008.   
[11]E. Acar,R. Harrison,and C.Loan,“Future Directions in Tensor-Based Computation and Modeling," NSF Workshop,May,2009.   
[12]Boldi P, Vigna S (2004） The WebGraph framework I: Compression techniques.In: WWW, pp 595-602.   
[13]Yixin Chen, Guozhu Dong,Jiawei Han,Benjamin W.Wah, Jianyong Wang. Multi-dimensional regression analysis of time-series data streams.VLDB 2002: 323 - 334.   
[14] Junghoo Cho,Hector Garcia-Molina,Lawrence Page.Efficient crawling through url ordering.WWW 1998.   
[15] Valter Crescenzi,Giansalvatore Mecca,Paolo Merialdo.RoadRunner: Towards Automatic Data Extraction from Large Web Sites.VLDB 2001: 109-118.   
[16]Dennis Fetterly, Mark Manasse,Marc Najork,Janet L. Wiener. A large-scale study of the evolution of Web pages. Software: Practice and Experience,Special Issue: Web Technologies, Volume 34, Issue 2, 213-237,2004.   
[17] Chen Chen, Xifeng Yan,Feida Zhu, Jiawei Han,Philip S.Yu: Graph OLAP: Towards Online Analytical Processing on Graphs. ICDM 2008: 103-112.   
[18] Alon Y. Halevy,Anand Rajaraman, Joann J. Ordille: Data Integration: The Teenage Years. VLDB 2006: 9-16.   
[19]James D. Hamilton. Time Series Analysis.Princeton University Press,1994   
[20] G. E. Hinton,S. Osindero,and Y.-W. Teh,“A fast learning algorithm for deep belief nets,” Neural computation, vol. 18, no.7, pp.1527-1554,2006.   
[21]R. Motwani, J. Widom, A. Arasu, B. Babcock, S.Babu, M. Datar, G Manku, C. Olston,J.Rosenstein and R.Varma. Query Processing,Resource Management,and Approximation in a Data Stream Management System. CIDR 2003.   
[22]Anh Huy Phan,Andrzej Cichocki, Petr Tichavsky,Danilo Mandic,and Kiyotoshi Matsuoka,“On Revealing Replicating Structures In Multiway Data: A Novel Tensor Decomposition Approach," Lecture Notes in Computer Science, vol. 7191, pp. 297-305, 2012.   
[23]Leo L. Pipino, Yang W.Lee,Richard Y. Wang. Data quality assessment. Communications of the ACM,Volume 45 Issue 4, 211-218,2002.   
[24]Erhard Rahm, Hong Hai Do.Data Cleaning: Problems and Current Approaches. IEEE Data Eng.Bull. 23(4): 3-13 (2000).   
[25]M. Alex O. Vasilescu and Demetri Terzopoulos,“Multilinear subspace analysis of image ensembles,” IEEE International Conference on Computer Vision and Pattern Recognition, 2003.   
[26]Yuanyuan Tian，Richard A.Hankins，Jignesh M.Patel，Efficient Aggregation for Graph Summarization,SIGMOD'08,2008.   
[27]Jun Zhu, Zaiqing Nie, Ji-Rong Wen, Bo Zhang,Wei-Ying Ma. Simultaneous record detection and attribute labeling in web data extraction. KDD 2006: 494-503.   
[28]Le Q, Ranzato M, Monga R, et al, Building High-level Features Using Large Scale Unsupervised Learning. In: Proceedings of 29th International Conference on Machine Learning, 81-88, 2012.   
[29]Torralba A,Fergus R,Freeman T, 8O milion tiny images: a large dataset for non-parametric object and scene recognition. IEEE Transactions on Patern Analysis and Machine Intelligence,v 30,n 11, p 1958-1970, 2008   
[30]Xin-Jing Wang，Lei Zhang，Wei-Ying Ma: Duplicate-Search-Based Image Annotation Using Web-Scale Data.Proceedings of the IEEE 10(9): 2705-2721 (2012)   
[31]Olga Russakovsky and Fei-FeiLi,“Atribute learning in large-scale datasets,” in Proc.ECCV,2010.   
[32]Parikh and Kristen Grauman,“Relative attributes,”in Proc.ICCV, 2011.   
[33]Nikos Sidiropoulos，“Big Tensor Data， Compressd Sensing，and Preference Measurement,” Scientific and Statistical Computing Seminar, 2013.   
[34]Bizer C,Tom H, Tim B-L.Linked Data—The Story So Far. International Journal on Semantic Web and Information Systems, 5(3): 1-22,2009.   
[35]何克清，何扬帆，王翀，等．本体元建模理论与方法及其应用．北京：科学出版社,2008.   
[36]Schneider J. Building a standpoints web to support decision-making in Wikipedia. In Proceedings of the ACM 2012 conference on Computer Supported Cooperative Work Companion, New York: ACM, 2012, pp. 335-338.   
[37]Halpin H, Robu V,and Shepherd H. The Complex Dynamics of Collaborative Tagging.In Proceedings of the 2O07 International Conference on World Wide Web,Alberta, Canada,May 8-12, 2007, pp. 211-220.   
[38]Robu V,Halpin H,and Shepherd H.Emergence of Consensus and Shared Vocabularies in Collaborative Tagging Systems. ACM Transactions on the Web,3(4): Article 14,2009.   
[39]Shepler S,Callghan B, Robinson D,et al. NFSv4. Request for Comments. 2003,3530.   
[40]Sanjay Ghemawat,Howard Gobioff,and Shun-Tak Leung,The Google File System,19th ACM Symposium on Operating Systems Principles, Lake George,NY, October, 2003.   
[41]HDFS Architecture Guide [EB/OL]. htp://adoop.apache.org/docs/r1.0.4/hdfs_design.html   
[42]Ronnie Chaiken, Bob Jenkins,Per-AKe Larson, et al. SCOPE: easy and eficient paralel processing of massive data sets[J].PVLDB,2008,1(2):1265-1276   
[43]Doug Beaver, Sanjeev Kumar, Harry C.Li, et al. Finding a Needle in Haystack: Facebook's Photo Storage[C] in Proc of OSDI 2010 .CA:USENIX Association Berkeley,2010:47-60   
[44]http://code.taobao.org/p/tfs/wiki/index/   
[45]Fay Chang,Jeffrey Dean, Sanjay Ghemawat,Wilson C.Hsieh, Deborah A. Wallach, Mike Burrows, Tushar Chandra,Andrew Fikes,and Robert E.Gruber, Bigtable: A Distributed Storage System for Structured Data, OSDro6: Seventh Symposium on Operating System Design and Implementation, Seattle, WA, November, 2006.   
[46]Giuseppe DeCandia,Deniz Hastorun,Madan Jampani,et al.Dynamo:amazon's highly available key-value store[C] in Proc of SOSP 2007 .New York:ACM,2007:205-220   
[47]Jason Baker,Chris Bond, James Corbett, et al. Megastore: Providing Scalable,Highly Available Storage for Interactive Services[C] in Proc of CIDR 2011:223-234   
[48]James C.Corbett， Jeffrey Dean，Michael Epstein，et al. Spanner: Google's Globally-Distributed Database[C] in Proc of OSDI 2012.CA:USENIX Association Berkeley,2012   
[49][Twitter2011] Storm [EB/OL]. https://github.com/nathanmarz/storm   
[50][Leonardo2O10] Leonardo Neumeyer,Bruce Robbins，Anish Nair, et al.S4: Distributed Stream Computing Platform[C] in Proc of ICDM Workshops 2010. Piscataway,NJ: IEEE,2010:170-177   
[51]Ken Goodhope,Joel Koshy，Jay Kreps，et al. Building LinkedIn's Real-time Activity Data Pipeline [J]. Data Engineering,2012,35(2):33-45   
[52]Jeffrey Dean, Sanjay Ghemawat. MapReduce: Simplified Data Processing on Large Clusters[C] in Proc of OSDI 2004 .CA:USENIX Association Berkeley,2004:137-150   
[53][Daniel2O1O] Daniel Peng，Frank Dabek.Large-scale incremental processing using distributed transactions and notifications[C] in Proc of OSDI 2010.CAUSENIX Association Berkeley,2010:1-15.   
[54]Pradeep Kumar Gunda,Lenin Ravindranath, Chandramohan A. Thekkath,et al.Nectar: Automatic Management of Data and Computation in Datacenters[C] in Proc of OSDI 2010 .CA:USENIX Association Berkeley,2010:75-88   
[55]POPA,L.，BUDIU, M.,et al. DryadInc: Reusing work in large-scale computations[C] in Proc of HotCloud 2009.CA:USENIX Association Berkeley,2009   
[56]Pramod Bhatotia, Alexander Wieder, Rodrigo Rodrigues,et al. Incoop: MapReduce for incremental computations[C] in Proc of SOCC 2011 .New York:ACM,2011   
[57]Cairong Yan, Xin Yang, Ze Yu, et al. IncMR: Incremental Data Processing Based on MapReduce[C] in Proc of Cloud 2012 Piscataway, NJ: IEEE,2012:534-541   
[58]Christopher Olston, Greg Chiou,Laukik Chitnis,et al. Nova: continuous Pig/Hadoop workflows[C] in Proc of SIGMOD 2011.New York: ACM,2011:1081-1090   
[59]Tyson Condie，Neil Conway，Peter Alvaro，et al.MapReduce Online[C] in Proc of NSDI 2010 .CA:USENIX Association Berkeley,2010:313-328   
[60]Yingjie Shi， Xiaofeng Meng,Fusheng Wang,et al. You Can Stop Early with COLA: Online Processing of Aggregate Queries in the Cloud[C] in Proc of CIKM 2012 .New York:ACM,2012   
[61]Edward Mazur，Boduo Li， Yanlei Diao,et al.Towards Scalable One-Pass Analytics Using MapReduce[C] in Proc of IPDPS Workshops 2011 .Piscataway,NJ: IEEE,2011:1102-1111   
[62]Andrey Brito, Andre Martin, Thomas Knauth,et al. Scalable and Low-Latency Data Processing with Stream MapReduce[C] in Proc of CloudCom 2011 .Piscataway,NJ: IEEE,2011:48-58

作者简介：

靳小龙： 中国科学院计算技术研究所网络数据科学与工程研究中心，副研究员、博士生导师jinxiaolong@ict.ac.cn王元卓： 中国科学院计算技术研究所网络数据科学与工程研究中心，副研究员程学旗： 中国科学院计算技术研究所网络数据科学与工程研究中心，主任、研究员、博士生导师