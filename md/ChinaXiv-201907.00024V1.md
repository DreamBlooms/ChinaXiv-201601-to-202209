# 中国虚拟天文台的核心功能需求调查分析

许允飞1、2，樊东卫1，崔辰州1，何勃亮1，李长华1，于策，肖健4，李珊珊1，米琳莹1，韩军1，陶一寒1，王传军5、6、2，张海龙7，刘梁8，李正1，韩叙1，杨丝丝1，杨涵溪1，和兰1，张磊1、2，崔顺9、1，王川中9、1，苏丽颖9，陈力10，乔翠兰11，许谦7，李乡儒12，杨海峰13，曹子皇1、2，王俊峰14，强振平15，白春海7，周卫红16，袁国武17，柏正尧17，李冀18，郑子鹏19，和寿圣5，屈彩霞13，孙继先20，淥登荣20，赵永恒1

（1.中国科学院国家天文台，北京100101；  
2.中国科学院大学，北京100049；  
3.天津大学 软件学院，天津 300350；  
4.天津大学计算机科学与技术学院，天津300350；  
5.中国科学院云南天文台，云南 昆明650216；  
6．中国科学院天体结构与演化重点实验室，云南昆明650216；  
7.中国科学院新疆天文台，新疆乌鲁木齐 830011；  
8.中国科学院紫金山天文台，江苏 南京 210008；  
9．北京工业大学机械工程与应用电子技术学院北京 100124;  
10.中国科学院上海天文台，上海200030；  
11.华中师范大学，湖北 武汉 430079；  
12．华南师范大学，广东广州 510631；  
13．太原科技大学，山西 太原 030024；  
14．厦门大学，福建 厦门361005；  
15．西南林业大学，云南昆明 650224；  
16．云南民族大学，昆明云南650500；  
17．云南大学 云南 昆明 650500；  
18．河北师范大学，河北石家庄050024；  
19．河北工业大学，天津300401；

20．中国科学院紫金山天文台青海观测站，青海 德令哈 817000）

摘要：经过十余年的不断建设和发展，中国虚拟天文台（China-VO）已成为支撑天文学观测、研究、教学的重要技术和资源平台。随着多信使天文学和时域天文学时代的到来，虚拟天文台也需要升级自身的核心能力，以给天文工作者提供更精准的服务和技术支撑。为此，中国虚拟天文台团队结合天文学的发展方向和信息技术发展趋势梳理了一份核心技术需求清单，并以问卷的形式针对领域内专家和用户开展了调研。通过对调研结果的统计和分析，中国虚拟天文台明确了未来一段时期的主要努力方向和目标，计划采用平台化的开发模式，并开放第三方开发接口，以吸引更多感兴趣的开发者基于虚拟天文台资源做出实用的工具，更好地实现资源与技术向服务的快速转换。

关键词：虚拟天文台；功能需求；多信使天文学；时域天文学；

中图分类号： 文献标识码：A 文章编号：

# 0虚拟天文台现状

随着天文学的不断发展,科研协作日益广泛，传统的研究模式也必须改变。2000年前后，为了实现对天文数据所有访问过程的标准化，天文学家提出了一个跨天文学科、计算机学科、信息学科的概念——虚拟天文台（Virtual Observatory，VO）。VO是通过先进的信息技术将全球范围内的天文研究资源无缝透明地连结在一起形成的环境，用于数据密集型网络化天文研究和科普教育]。V0通过利用最先进的计算机和信息技术将各种天文研究资源，包括观测数据、天文文献、计算资源、存储资源、软件服务，甚至天文观测设备，以统一的服务模式无缝地汇集在一个物理上分散、逻辑上统一的系统。经过近二十年的发展，V0统一了各个数据服务系统的访问标准，已经成为天文学研究重要的信息化支撑平台。

2002年，以中国科学院国家天文台为首的中国天文学界提出了中国虚拟天文台（China-VO）的设想。China-VO的重点研发领域包括中国虚拟天文台系统平台的开发、国内外天文研究资源的统一访问、基于V0的天文研究示范和天文科普教育等几个方面[2]。China-VO的目标是在天文学和信息技术之间起到桥梁和纽带的作用，促进先进的信息技术能够服务于天文学的研究。

2013年，China-VO基于CloudStack云计算中间件开始了公共服务平台的研发，在国内多个地方部署了云节点。自2016年下半年开始，以国家天文台-阿里云建立战略合作为切入点，China-VO全面探索“公共云 $+$ 专有云”的混合架构方案。China-VO云服务平台充分利用了各台站和中科院现有的网络、存储、计算等基础设施，借助信息领域和VO领域的先进关键技术，以天文观测数据汇交、共享和使用及国内核心天文观测设备的时间申请、审批为线索，融合天文观测和科研活动所需计算、存储、软件等资源，形成一个物理上分散、逻辑上统一的网络化科学研究平台。

现阶段，China-VO公共服务平台已经发展出国家天文台（北京）、紫金山天文台（南京）、上海天文台（上海）、云南天文台（昆明）、新疆天文台（乌鲁木齐）、南京大学（南京）和阿里云（杭州）等7个节点；为兴隆LAM0ST、13.7米毫米波望远镜、佘山1.56米、丽江2.4米、南山25米等10多套观测设备提供数据管理和开放共享服务；为丽江2.4米、兴隆2.16米等望远镜提供时间申请服务；为中国科学院大学、南京大学等提供云教学环境；为上千位科研用户提供虚拟机等服务；基于国内业余天文观测数据发现了19颗超新星和新星；注册用户超过21000人。2015年初，China-VO入选“中国科学院科研信息化十大优秀案例”。在“互联网+"大数据时代，China-VO正在为天文学的发展发挥着越来越大的信息化支撑服务作用。

# 1新的需求和挑战

随着双中子星并合引力波事件GW170817及其电磁对应体的发现[3]，以及IceCube-170922A 高能中微子的BL 型耀变体的证认和表征[4]，天文学进入了多信使科学发现的新时代。与此同时，以LSST和SKA为代表的时域概要式巡天项目开启了时域天文学的探索和发现新时代，同时也带来了巨大挑战。多信使天文学和时域天文学的开展强烈地依赖信息技术，需要一个非常强大的网络系统架构，包括数据处理流水线，归档，事件自动检测、分类和发布，以及数据的高效融合等。天文学正在从发现驱动的科学转化为数据驱动、科学引导的科学，即数据密集型科学。而VO的目标正是要把天文学从老的数据贫乏的研究体制变革到新的数据极大丰富的研究体制，充分利用信息技术来解决数据密集型的多信使天文发现时代的挑战。

新时代带来的挑战对于VO 的技术支撑能力提出了更高的要求。China-VO 虽然已经有了相当的资源和技术积累，但距离时域天文学和多信使天文学所需研究的能力和技术需求还存在很大的差距。新一代观测设备产生的PB级的数据流给数据的处理和挖掘带来了全新挑战，其中关键的一个方面是实时的大数据流处理分析[5J6]。由于大量的多信使观测和时域观测的事件是暂现的，事件的检测以及及时恰当的随动观测非常重要。这需要从望远镜获取数据的同时就进行数据处理，自动可靠地检测、分析暂现事件，并根据优先级安排及时的随动观测。此外，还需要程控望远镜替代人工来编排并执行时域观测，并自动完成时域事件的发现和分类。以上过程中的需求可以概括为“多波段、多信使海量数据的高效融合”。数据融合与互操作是VO的核心科学目标和技术能力，以往的数据融合研究主要集中在多波段方面，多信使数据的融合研究才刚刚起步。同时，传统的数据融合与互操作研究大多是为满足传统科研课题的需要，而不是时域天文学科学计划甚至科学工程的需要，对于完成时限等性能方面的问题没有严肃的考虑。因此，目前China-VO尚不完全具备“多波段、多信使海量数据的高效融合”条件，亟需对自己的核心能力进行提升。

# 2核心能力调研

基于以上认知，China-VO 团队针对时域天文学和多信使天文学涉及的主要关键技术需求进行了梳理，并以调查问卷的形式向China-VO学术委员会的专家和广大用户公开征求意见，希望通过这样的调查确定未来一段时期的主要努力方向和目标。调研问卷包含了China-VO 团队所提供的服务内容的各个方面，涉及文件存储服务、数据检索服务、数据可视化、交叉证认服务、在线计算服务、远程天文台自动化控制、自动化数据分类方法、平台拓展建设共8个部分。每个部分包含若干具体关键技术点，共计23条具体需求。问卷中描述了每条关键技术的应用范围和技术特征，具体如表1。

# 表1中国虚拟天文台核心功能调研明细

Table 1 Contents of China-VO Core Functions Survey   

<html><body><table><tr><td>需求分类</td><td>细分</td><td>简要说明</td><td>应用方向</td></tr><tr><td rowspan="4">文件存取</td><td>本地大容量 高速文件存</td><td>通过分布式存储、平行扩展等方式实现大量文件的高速存取、查 找本地文件</td><td>超大文件的存取</td></tr><tr><td>取 异地数据存 取</td><td>了解数据存储情况，快速取得所需远程数据</td><td>台站数据获取、远程数据同 步、数据异地备份等</td></tr><tr><td>分级节能存</td><td>热数据、温数据、冷数据的分级存储，达到节省资源的目的</td><td>机房数据存储实践</td></tr><tr><td>储 大星表检索</td><td>切分大数据至多个节点并分别检索，再合并检索结果</td><td></td></tr><tr><td rowspan="2">数据检索</td><td>异地数据检</td><td>同一平台上访问多地数据</td><td></td></tr><tr><td>索</td><td>在线调用数据，并使用服务器资源进行在线处理、计算。结果保</td><td>大规模数据在线处理</td></tr><tr><td rowspan="3"></td><td>CasJobs深度</td><td>存于在线存储中 将CasJobs合并到虚拟天文台体系</td><td></td></tr><tr><td>整合 Jupyter Hub</td><td>在线编写Python 程序，使用服务器计算资源进行计算，结果保</td><td></td></tr><tr><td>在线计算、画 图 多波段数据</td><td>存在服务器上 光学、射电等多波段数据，以及点源、展源交叉证认方法</td><td>查找观测目标在多波段的</td></tr><tr><td rowspan="3"></td><td>高性能交叉 证认方法 多信使数据</td><td>引力波与多波段数据交叉证认</td><td>对应体 引力波电磁对应体候选体</td></tr><tr><td>交叉证认方 法</td><td></td><td>列表</td></tr><tr><td>交叉证认方</td><td>提供交叉证认方法的置信度</td><td>取得数据可信度</td></tr></table></body></html>

<html><body><table><tr><td></td><td>法的置信度 估计</td><td></td><td></td></tr><tr><td rowspan="4">自动化数据 分类方法</td><td>图像数据特 征自动提取</td><td>通过卷积神经网络的卷积层自动提取图像数据中的特征</td><td>帮助更深入了解数据，并为 数据分类提供思路</td></tr><tr><td>暂现源自动 分类</td><td>通过深度学习等方法对图像数据、光变曲线数据进行训练和学 习，实现暂现源自动分类</td><td>基于时域天文学的需求，暂 现源高效自动化分类是重 要一环</td></tr><tr><td>光谱数据特 征自动提取</td><td>使用聚类、降维等方法对光谱数据实现特征提取，并通过是深度 学习方法实现自动分类</td><td>面向时域天文学的需求，提 高光谱数据的分析处理效</td></tr><tr><td>与分类 图像拼接及</td><td>对观测图像进行拼接并重新分割，实现类似地图的在线放大、缩</td><td>率 全天星图展示</td></tr><tr><td rowspan="2"></td><td>分层可视化</td><td>小展示</td><td></td></tr><tr><td>星表分层可 视化 文件存取接</td><td>根据亮度或其他条件逐步展示星表数据 可通过编程接口来使用虚拟天文台中的各个功能</td><td>查看全天星表分布 第三方软件开发</td></tr><tr><td></td><td>接口、在线计 算接口等功 能的编程接 □</td><td></td><td></td></tr><tr><td></td><td>索、在线计算 等功能的权 限限制</td><td></td><td></td></tr><tr><td>云平台实现 实用工具整</td><td>在线latex撰</td><td>基于专有云或阿里云等公有云平台对以上系统进行实现 类似www.overleaf.com 的工具，可在线编写论文、共享编辑</td><td>系统的多地部署</td></tr><tr><td rowspan="2">合</td><td>写</td><td>类似在线网盘，提供第三方工具访问接口</td><td></td></tr><tr><td>在线文件分 享</td><td></td><td></td></tr><tr><td rowspan="3">远程天文台 自动化控制</td><td>多种应用场 景</td><td>嵌入式技术、标准通讯协议使系统功能多样</td><td>满足不同用户的控制需求</td></tr><tr><td>系统智能化</td><td>程控自主、基于机器学习使观测更加智能化</td><td>观测自动化与智能化</td></tr><tr><td>权限管理</td><td>登陆权限、控制权限、资源访问权限</td><td>权限管理</td></tr></table></body></html>

本文分别对这8个部分的需求进行了前沿技术的调研。如何实现高效的文件存储服务和数据检索服务一直是VO领域的研究热点。除了本地大数据的高速读写，随着多节点数据中心的不断建设，异地数据检索和分级存储也是当前研究的重点。天文数据的存储格式是比较多元化的，主流数据格式包括FITS、CASA和HDF5，大量碎片化的数据带来了极高的IO消耗，因而迫切需要实现海量数据的并行读写策略、分布存储策略,并提供无缝的数据访问服务。现阶段业界较为流行的分布式并行存储系统包括Lustre、Haystack、HDFS、TFS 等，它们设计思路基本相似，主要包含一个底层的文件存储系统及一个目录服务，通过高效的目录检索进行底层文件的存取。除了分布式文件存储系统外，高效数据存储和检索还依赖于高效的索引技术。天体的赤经赤纬是二维向量，通过将二维向量映射为一维数据可以实现对天体坐标的索引。可行的方法是将天球面划分为多个子区域，并给予子区域以唯一编号，实现对空间的索引。较为常用的方法包括球面三角网格划分HTM、HEALPix以及Zones 等，这些方法在 SDSS、MUSER、LSST 等项目中分别得到使用。

数据可视化包括了图像分层可视化和星表分层可视化，主要用于全天星图的展示和全天星表分布的展示。这里主要强调了分层的可视化，是指对于海量数据采用基于分辨率、星等亮度等条件渐进式的可视化。常用的方法为层次细节技术（LOD，LevelofDetails），主要实现包括四叉树、八叉树算法等。美国 MAST的 Skyview 系统，法国CDS 的Aladin 系统均实现了大数据条件下的全天图像的拼接。

交叉证认的核心方法是计算两个目标之间的距离，如果小于阈值则认为两个目标为同一天体。在国内外，交叉证认的研究已经取得了一系列的成果，如基于HTM索引分区与kd-tree的最近邻算法[7、基于 MapReduce 的分布式交叉证认方法[8]、基于 HEALPix 与 ZonesAlgorithm的GPU集群算法等。但是在多波段、多信使数据交叉证认及置信度估计方面还有许多关键技术需要突破。

自动化数据分类方法主要面向时域天文领域的海量数据分析。随着新一代观测设备的不断投入使用，将会获取到海量的不同波段的暂现源观测数据，现有的数据分类的方法已不能满足大数据时代的处理要求。借助人工智能方法尤其是深度学习方法将是一条可行之路。在图像数据分类上，深度学习方法已经发展出一系列经过实际应用检验的网络，如卷积神经网络中的ResNet、Alexnet、VGG 等,均可以应用到不同波段图像数据甚至光谱数据的分类中。

在线计算服务的主要目标是方便科研人员便捷高效的进行数据处理，无需将大量的数据从线上存储下载到本地，也无需在本地计算机上部署复杂的数据处理环境，直接通过在线平台进行数据的预处理、计算、分析等操作。CasJobs 就是这样的一个大型科学数据库的在线工作平台，以网络应用的形式提供强大的数据库检索和操作功能，它最初用于SDSS 的数据在线处理，现已由China-VO 团队集成至LAMOST 的巡天星表数据的处理系统中。JupyterHub 也被广泛用于天文数据的在线处理。它的使用方法类似于 Jupyter notebook，提供了一个在线的Python 编写与运行的平台，它可以提供多用户的登录使用，后台可以是算力强大的计算集群，且可扩展能力强，是实现在线计算服务的良好平台。

远程天文台凭借连续观测、快速反应等方面的独特优势，近些年得到迅速发展，国内外已开展了一系列基于远程天文台的时序巡天计划，如ROBONET、ROTSE-III、BOOTES 等，在伽玛暴余辉和其它暂现源的光学观测研究上都有了良好的应用。远程天文台由望远镜、赤道仪、圆顶、计算机、气象站、全天相机等设备构成，具有多个自动化的软件与硬件子系统，它们之间通过相互协调控制实现程控观测的功能。China-VO 经过多年的调研与研究，已经提出并设计了一套基于嵌入式的硬件集成系统，作为用户与天文台设备间连接的桥梁，以便于各子系统的集成控制和扩展移植[°，未来将在此基础上进一步优化，重点开展智能化观测的应用研究。

平台拓展建设主要涵盖了China-VO平台自身服务能力的完善，包括更灵活的用户权限，实用科研工具的整合，便捷的第三方应用程序开发接口，以及基于专有云或公有云的平台实现。这些基于基础设施的功能拓展能够为用户提供更好的服务体验，进一步提升用户粘性。

# 3调研结果分析

本次调研通过邮件问卷和在线问卷两种方式进行，共收到12份China-VO学术委员会专家的反馈，65份China-VO邮件列表和网络用户反馈。用户群体主要包括天文领域科研工作者和研究生，均具有China-VO公共服务平台使用经验。

# 3.1统计方法

在做反馈统计时给予专家反馈以3倍的权重进行加权，共视为101份问卷。根据问卷分值\*分值数占总数比例，分别计算出问卷中8个大类、23条具体需求的分值。

# 3.2调研结果

图1为8个大类的具体反馈结果，按分值高低依次排序（分值为0-5分，分值越高，表示该需求越重要)。其中得分最高项为文件存储服务（3.89 分）、其次分别为数据检索服务（3.87分）、数据可视化（3.68分）、交叉证认服务（3.52分）、在线计算服务（3.39分）、远程天文台自动化控制（3.36分）、自动化数据分类方法（3.21分）、平台拓展建设（3.11分)。图2为23条具体需求的得分情况。

图1各项需求大类别的反馈结果  
![](images/5cbe48f3462ebe14cce150bb0db1c01426fb00620fbc60b4b5f0a1db950bfa2a.jpg)  
Fig.1 Feedback Results for Main Categories of Requirements

# ChinaXiv合作期刊

Online LaTeX Service 2.445 Online file sharing 2.942 Platform Permission Control 3.208 China-VO Service on the Cloud 3.387 China-VO Application Programming Interface 3.564 Transients Automatic Classification 3.09   
Multi-band Observation Data Feature Extraction & Classification 3.336 Multi-application Scenario of Remote Observatory 3.298 Remote Observatory Permission Management 3.376 Intelligent Remote Observatory System 3.393 Integration with SDSS CasJobs 3.208 Jupyter Hub Service 3.376 Large-scale Data Online Processing 3.595 Multi-messenger Data Cross-Matching Method 3.276 Confidence Estimation of Cross-Matching Method 3.425   
High Performance Cross-Matching Method for Multi-band Data 3.854 Catalogue Hierarchical Visualization 3.596 Image Stitching & Hierarchical Visualization 3.764 Offsite Data Retrieval 3.85 Big Catalogue Retrieval 3.89 Hierarchical Energy Saving Storage 3.425 Local Bulk File High-speed Access 4.098 Offsite Data Access 4.142 0 0.5 1 1.5 2 2.5 3 3.5 4 4.5

此外，本文将China-VO学术委员会专家的答复单独进行了统计。专家打分与问卷总体分值相差不大，具体为文件存储服务（4.11分）、其次分别为数据检索服务（3.96分）、数据可视化（3.92分）、自动化数据分类方法（3.59分）、交叉证认服务（3.47分）、在线计算服务（3.44分）、平台拓展建设（3.03分）、远程天文台自动化控制（2.86分)，专家打分与总体打分之间的区别如图3所示。专家给出的各项分值均比总体打分的分值略高，可见专家对VO团队的需求梳理有较高认可。此外，专家打分中自动化数据分类方法与远程天文台自动控制的得分与总体打分差异较大，可见专家与用户对这两类需求持不同意见。

![](images/acd2b89b865819149ec33ce12832c10c5fe2005486b9c38edf94e8bbbcf07898.jpg)  
图3总体打分与专家打分之间的对比  
Fig.3 Comparison between overall scoring and expert scoring

# 3.3分析与思考

从反馈结果中可以看出,数据的可获取性、数据操作的便捷性，仍是对VO的核心需求。天文学家所关注的始终是如何更方便地分析、处理数据。现阶段，China-VO 维护的中国天文数据中心提供21个数据集的归档和查询服务，用户可直接在线进行数据检索和下载。公共服务门户提供了虚拟计算资源和存储资源服务，通过云平台的在线控制台，用户可以自行定制需要的计算资源和存储资源；同时，基于国家天文台与阿里云的战略合作，用户也可以使用阿里云的计算资源。但是，VO的数据在线检索和处理还未能实现一体化服务，提高服务的易用性、便捷性将是今后工作的一个重点。

数据可视化、交叉证认服务、在线计算服务，这些需求是数据处理需求的延伸，也是VO 提供便捷服务的突破点。China-VO 团队前期已经开展了一些工作，包括面向天文科普教育所研发的天文数据可视化平台"万维望远镜"；以云平台虚拟机模板的形式发布了常用数据处理环境，如为中国科学院大学多波段数据处理课程所研发的虚拟机处理模板，其中包含了CFITSIO、Graphviz、GSL 等科学数据处理程序库，用户基于它生成虚拟机即可方便的使用。未来将在提高服务的易用性、便捷性的同时，进一步加强相关资源和服务的宣传，使用户更好的了解China-VO已有的功能，从而提供更优质的服务。

致力实现数据存取、查询、处理的一体化在线服务始终是China-VO的目标。但是，当前实现VO核心需求仍存在相当的困难，主要体现在需求的高难度、大体量和VO研发人员不足之间的矛盾。将China-VO积累的数据、存储、计算资源转换为高效便捷服务，需要大量的研发人员，但在现有体制下，进一步增加研究人员编制是不现实的。为此，China-VO计划采用平台化的开发模式，通过开放VO第三方开发接口，吸引更多感兴趣的开发者基于VO 资源做出实用的工具，实现资源与技术向服务的快速转换。

图4展示的是下一阶段China-VO平台的体系架构设计，最底层是资源层，既包括存储服务器和计算服务器等硬件资源，也包括了China-VO 归档的各类数据集。在资源层之上是关键技术层，该层向下连接，通过虚拟化技术调用资源层的硬件资源，并通过数据检索算法和数据库工具调用数据资源，同时将VO涉及的各项关键技术进行封装形成类库，实现基于硬件资源和数据资源的按需计算。这些封装的关键技术包括数据检索方法、不同星表间的交叉证认方法、各类天文数据的可视化方法、基于机器学习的数据分类方法等，并且可以随着研发的不断深入逐步扩展。

# ChinaXiv合作期刊

![](images/8234ac15e89729875ae38197a9d3c87d9ab069f55b764e2815ecb898313899b9.jpg)  
图4中国虚拟天文台平台体系架构  
Fig.4China-VO platform architecture

关键技术层之上是接口层，也是China-VO下一阶段将着力建设的部分，通过将VO 的软硬件资源、关键技术封装为应用程序接口（Application Program Interface，API)，发布给广大的天文工作者，辅以完善的文档参考和培训支持，使他们能够根据自己的科研需求建立新的应用。依据本次调研的结果，文件存取、数据检索、数据可视化、交叉证认相关的 API将优先开放，相应的文档资料和应用示例代码将会通过China-VO网站向用户发布。

研究人员通过China-VOAPI构建的应用，可以注册在China-VO平台上，提供给更多的用户使用。这些应用将构成China-VO平台的应用与服务层。基于统一的应用开发标准和应用程序框架，这些应用可以跨平台的运行在移动端和桌面的浏览器中，并且在统一用户账户的管理下，用户可以无缝衔接的访问不同平台的应用和数据。

# 4总结展望

综上所述，通过本次核心功能需求调研，China-VO明确了下一阶段的建设重点和目标。China-VO 团队将重点提高数据的可获取性和数据操作的便捷性，并努力完善数据可视化、交叉证认、在线计算等在线服务。但是，当前VO的高需求与研发人员不足的矛盾也日益突出。为此，将采用平台化的开发模式，通过开放VO接口，吸引开发者基于VO的资源和关键技术做出更多实用的服务和工具，并通过China-VO平台实现共享。通过这种方式不断提升VO的核心能力，使之形成一个面向科研需求的应用生态系统，从而更好地应对时域天文学时代和多信使天文学时代带来的挑战。

# 致谢

本论文感谢国家天文科学数据中心提供的数据资源和技术支持。感谢所有参与本次调研

及分析讨论的所有专家和用户，感谢国家天文台-阿里云天文大数据联合研究中心对本项工作的支持。

# 参考文献

[1]赵永恒，崔辰洲."从虚拟天文台到天文信息学.”科研信息化技术与应用 2.3 (2011):3-12. [2]崔辰州，薛艳杰，李建，等."虚拟天文台——天文学研究的科研信息化环境."中国科学 院院刊， 2013， 28(4):511-518.   
[3] Abbott， B.P.， et al. "Multi-messenger observations of a binary neutron star merger." Astrophysical Journal Letters 848.2 (2017): L12.   
[4] IceCube，Fermi-LAT， et al."17B-403 collaborations." Multimessenger observations of a flaring blazar coincident with high-energy neutrino IceCube-170922A， Science 361 (2018): 1378.   
[5] Graham，Matthew J.， et al. "Data challenges of time domain astronomy." Distributed and Parallel Databases 30.5-6 (2012): 371-384.   
[6] Bloom，Joshua S."Technical and Observational Chalenges for Future Time-Domain Surveys." Proceedings of the International Astronomical Union 7.S285 (2011): 165-170.   
[7] 高丹,张彦霞,赵永恒．海量多波段星表数据的交叉证认的实现．天文研究与技术,2005,3 [8] X. Jia, Q. Luo and D. Fan, "Cross-Matching Large Astronomical Catalogs on Heterogeneous Clusters,"2O15 IEEE 21st International Conference on Parallel and Distributed Systems (ICPADS), Melbourne,VIC,2015, pp. 617-624.   
[9] Fan, D., Budavari,T., Szalay, A. S., Cui, C.,& Zhao, Y. 2O13. Efficient Catalog Matching with Dropout Detection, pasp, 125,218   
[10] J. Han, C. Wang, D. Fan ，C. Cui ,S. Li,L. Mi,Z. Li,Y. Xu，B. He,C. Li ，S. Yang .Amateur public observatory I: The observatory and hardware integration system. Astronomy and Computing,25 (2018) 89-93   
[11]崔辰州，于策，肖健"大数据时代的天文学研究.”科学通报 5(2015):445-449.   
[12]李长华，崔辰州，赵永恒."虚拟天文台的理念，设计与应用.”中国教育网络6(2012): 22-24

# Investigation and analysis of core functional requirements of China VO

Yunfei ${ \mathrm { X u } } ^ { 1 \cdot 2 }$ ,Dongwei Fan’,Chenzhou $\mathrm { { C u i } } ^ { 1 }$ ，Boliang $\mathrm { H e } ^ { 1 }$ ，Changhua $\mathrm { L i } ^ { 1 }$ ，CeYu³，Jian Xiao4，Shanshan $\mathrm { L i } ^ { 1 }$ ，linying $\mathbf { M } \mathbf { i } ^ { 1 }$ ， Jun Han1,   
Yihan Tao¹,Chuanjun Wang5、6.2,Hailong Zhang7, Liang Liu8，Zheng $\mathrm { L i } ^ { 1 }$ ， $\mathrm { { X u } \ : \mathrm { { H a n } ^ { 1 } } }$ ，Sisi Yang¹，Hanxi Yang’，Lan $\mathrm { H e } ^ { 1 }$ ,Lei Zhang1   
2，Shun Cui9\*1,Chuanzhong Wang91，Liyin $\mathrm { \Delta S u ^ { 9 } }$ ,Li Chen10，Cuilan Qiaol1，Qian $\mathrm { \Delta X u ^ { \mathrm { 7 } } }$ ， Xiangru $\mathrm { L i } ^ { 1 2 }$ ，Haifeng Yang13， Zihuang Caol   
2，Junfeng Wang14，Zhenping Qiang15，Chunhai Bai7，Weihong Zhou16，Guowu Yuan17，Zhengyao Bai17，JiLi $^ { 1 8 }$ ， Zipeng Zheng19, Shousheng He5，Caixia ${ \mathrm { Q u } } ^ { 1 3 }$ ， Jixian Sun2o，Dengrong Lu20，Yongheng Zhaol 1.National Astronomical Observatories,Chinese Academy of Sciences,Beijing 100101; 2. University of Chinese Academy of Sciences,Beijing 1Ooo49,China; 3.School of Software,Tianjin University,Tianjin 3Oo350,China; 4.School of Computer Science and Technology,Tianjin University,Tianjin 30o350,China;   
5.Yunnan Astronomical Observatory,Chinese Academy of Sciences,Kunming Yunnan 65O216, China;   
5.KeyLaboratoryof Astronomical Structure andEvolution,Chinese Academyof Sciences,Kunming Yunnan 65o216,China:   
7. Xinjiang Observatory,Chinese Academy of Sciences, Urumqi Xinjiang 830011, China;   
8.Purple Mountain Observatory, Chinese Academy of Sciences,Jiangsu Nanjing 21Ooo8,China;   
9.Schoolof MechanicalEngineeringandAppliedElectronics,Beijing UniversityofTechnology,Beijing1Ol24,China;   
10.Shanghai Astronomical Observatory, Chinese Academy of Sciences,Shanghai 2Ooo3o,China;   
11.Huazhong Normal University,Wuhan Hubei 43O079,China;   
12. South China Normal University, Guangzhou Guangdong 510631, China;   
13.Taiyuan University of Science and Technology,Taiyuan Shanxi O3oo24,China;   
14.Xiamen University, Xiamen Fujian 3610o05,China;   
15.Southwest Forestry University,Kunming Yunnan 65O224, China;   
16.Yunnan Nationalities University,Kunming Yunnan 65o5oo,China;   
17.Yunnan University,Kunming Yunnan 65o5oo,China;   
18.Hebei Normal University, Shijiazhuang Hebei O5oo24, China;   
19.Hebei University of Technology,Tianjin 30O4O1,China;

20.Qinghai Observatory,Purple MountainObservatory,ChineseAcademyof Sciences,QinghaiDelingha 817ooo,China)

Abstract: After more than ten years of construction and development, China Virtual Observatory (China-VO) has become an important technology and resource platform to support astronomical observation,research and teaching. With the advent of multi-message astronomy and time-domain astronomy,the VO also needs to upgrade its core capabilities to provide astronomers with more precise service and technical support. To this end, based on the development direction of astronomy and the development trend of information technology,the China VO team combed a list of core technology requirements of VO,and conducted a survey on VO experts and users of China VO platform. Through the statistics and analysis of the survey results, China VO has defined the main efforts and goals for the next period of time, plans to adopt a platform-based development model，and open third-party development interfaces to atract more interested developers，who can make more practical tools based on VO resources,to better realize the transition of resources and technology to services.

Key Words: Virtual observatory; Functional requirements; Multi-messenger astronomy; Time domain astronomy;