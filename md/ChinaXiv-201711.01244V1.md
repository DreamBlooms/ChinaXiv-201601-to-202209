# 利用开放语义资源丰富个人名称规范数据基于FOAF的方案设计

# 郝嘉树

(国家图书馆 北京 100081)

摘要：【目的】我国规范数据质量差且维护效率低下，需探索低成本高效率的信息源获取模式，丰富个人名称规范数据。【方法】分别从语义资源数量和类型的有效性，高效维护的评价指标易获取、自动化程度、维护速度和开放资源可信度三个方面论证用语义资源维护名称规范的可行性，同时以FOAF为例设计实现方案。【结果】制定了获取语义资源的限制条件、接口方式和收割规则策略，给出发现、整合资源的RDF谓词以及开发包和软件两种实现技术，设计丰富名称规范数据的自动多重匹配算法和映射表。【局限】只提供实现流程及方案，没有付诸实施；语义资源获取后的存储方式、提取处理方法只是框架设计，没有给出详细的实现技术。【结论】可以将与个人相关的开放语义资源自动匹配，丰富本地名称规范数据。

关键词：个人名称规范开放语义资源自动发现聚合 RDF URI FOAF自动匹配丰富分类号:G254TP393.4

# 1引言

我国个人名称规范数据因不完整数据量大、重名严重及同名标目形式多样化等问题导致标目间区分度低，在维护规范数据和规范书目责任者时给编目员甄别和选择带来较大障碍，需要人工逐条分析、比对和辨别。编目员在个人名称规范维护和控制工作中花费的时间、精力与名称规范发挥的作用形成较大反差。

截至2014年底，国家图书馆名称规范数据量已高达140万条,7年时间增长 $62 \%$ ，因此当前名称规范工作重点不应该是盲目扩张规范库规模，而是要靠高效获取和完善数据提升名称规范数据的维护效率和质量，从而真正发挥名称规范的区分、汇聚等功能。

探索低成本高效率的信息源获取模式是关键所在。目前，维护规范数据的信息来源有受编文献、工具书、期刊、网络、电话、邮件和交友软件等渠道，这些渠道大多是被动获取信息，可获得内容取决于是否提供和提供哪些信息；电话、邮件和交友软件虽然能得到指定信息，但沟通成本高不利于大规模开展。因此需探索新的信息源获取模式，在获得所需信息的同时，能快速大规模开展个人名称规范数据维护工作并降低人力物力成本。

国内外已有学者从开放关联数据的角度论述发布名称规范数据可以发现、整合信息，其中有些完成了数据的语义化发布，但并未给出如何实现规范数据的丰富和具体实施方案[1-2]；Elliott提出利用FOAF 帮助名称规范消歧，但只论述了潜在可能性，并提出相关疑问[3]。考虑到机构对自身数据不愿公开以及开放关联数据操作、管理的复杂性，本文提出不发布为开放关联数据，而是收割语义资源丰富本地名称规范的方法，并论述该方法可行的相关依据，同时以FOAF为例，制定语义资源获取策略、分析发现整合技术以及给出自动丰富名称规范数据的具体算法和方案。

# 2开放语义资源：高效信息源获取模式

开放语义资源是发布在Web中以机器可理解可处理的资源描述框架(Resource Description Framework,RDF)模型和统一资源标识符(Uniform ResourceIdentifier,URI)表示的可分享、链接的数据集合[4]。语义数据通过"主体-谓词-客体"三元组(Triple)形式描述不同对象和它们之间的关系，资源用URI标识并用RDF模型表示后，经过发布，任何人都可以使用HTTPURI参引(Dereference，查找和获取)该数据。

开放语义资源是有效的名称规范信息源。目前互联网上发布的RDF三元组数量已是百亿级别，在这些开放语义资源中，包含了由网络用户发布的“自我申明”，它们通过用户创造内容(User Generated Content,UGC)5形式整合存在人头脑里有关人的事实信息，例如FOAF(Friend-Of-A-Friend)[6]、BibApp[7]和 VIVO[8],这些资源描述个人的兴趣爱好、开展的工作及项目、发表的著作及认识的朋友同事等，可用来补充、完善个人名称规范数据相关信息项；除此之外，开放语义资源中还有权威机构发布的名称规范档、人名表和叙词表等，如德国国家图书馆联合权威档(GemeinsameNormdate，GND)及国际虚拟规范文档(VirtualInternational Authority File,VIAF)[10等基于RDF/XML描述的名称规范档，英国档案叙词表(UK ArchivalThesaurus，UKAT)[1]及美国国会图书馆标题表(LibraryofCongress Subject Headings,LCSH)[l2]等用简单知识组织系统 (Simple Knowledge Organization System, SKOS)[13]表示的个人主题词，这些词汇表包含了权威的个人信息，其本身就可用来丰富名称规范附加成分、单纯参照和相关参照等，提高个人名称规范数据质量。

利用开放语义资源维护名称规范数据的高效性体现在易获取性、自动化程度和维护速度三个方面。目前国内外维护名称规范数据的主要方式是由编目员通过受编文献、工具书、期刊、网络和邮件等渠道查找责任者相关信息，并进行手工维护。利用开放语义资源的自动维护较之基于传统信息源的手工维护：

(1）易获取性方面，前者的RDF三元组描述方式及URI技术容易在数据集之间跳转，将不同数据集合以各种关系形式连接起来，从而能极大程度上发现和获取资源，并且准确性高；而后者需人工逐一在各信息源中查找，并需辨识同名异人的情况。

(2）自动化程度方面，前者结构化的数据可将RDF谓词和规范数据MARC字段建立映射，计算机程序能自动将语义资源收割到规范记录对应的字段中去；而后者需人工查找、辨识各字段对应的内容并手工输入。

(3）维护速度方面，前者大部分流程都可以根据相关算法和RDF机制由机器自动、定向和批量地获取资源和维护规范数据，对于超出本地规范库范畴外的资源可快速新建记录扩张本地规范库规模；而后者在各环节主要靠人工来逐条比对、判断和维护，影响维护的速度。

从以上三个评价指标可以得出，利用开放语义资源的自动维护较之基于传统信息源的手工维护效率高，有利于个人名称规范数据质量及规模的提升。

开放语义资源可信度高。语义数据的技术架构提供可追踪来源的RDF语义描述方案，通过数据来源判断数据的可靠性，还有通过计算网络可信度推断来源名誉[14]；语义网为各类实体和所涉及的大量概念、术语提供了规范控制，使得提及某一实体或概念术语时，系统能自动给予归并或参照，这种规范控制的结果就使信息在一定程度上更加可信[15];开放的语义资源中,网络用户发布的“自我申明"是个人对自我的真实反映，排除恶意欺诈，该种模式下申明的内容是客观的;发布的规范文档和叙词表等是由权威机构编制，内容准确真实。

调查发现 FOAF 是最受欢迎的本体之一[16]，为方便理解，本文即以FOAF为例，设计用语义资源丰富个人名称规范数据的方案，探究如何识别和获取开放语义资源进行个人信息的自动发现及聚合，并自动匹配和丰富名称规范数据。

# 3 FOAF

FOAF是网络用户用已定义好的RDF词汇表形式化描述个人信息和其相关的社会网络，其本质为描述个人的简单本体。它由Brickley 等于2000 年创建，遵循W3C体系，最初只描述个人，后扩展到各类群体，如机构、公司和地点，FOAF描述词汇随之历经10次更新，于2014年最终确定下来[17]

计算机对FOAF文档可读可理解，文档经发布便可搜索和处理。FOAF命名空间用RDFSchema定义的词汇(标签)描述个人及相关属性(信息项)，计算机通过这些标签理解和处理FOAF文档;FOAF文档可使用"FOAF-a-Matic $2 . 0 ^ { \ \mathrm { { > } [ 1 8 ] } }$ 、“Quatuo"[19]等在线工具生成,也可参考RDF/XML语法和FOAF词汇手工创建。获取有关人的信息并不容易，FOAF通过UGC形式整合存在人头脑里有关人的事实信息，并通过URI分散的协同形成社会网络。本文所使用的 foaf:Person(个人)类包含的属性如表1所示：

表1foaf:Person 包含的属性标签及说明  

<html><body><table><tr><td>属性标签</td><td>说明</td></tr><tr><td>foaf:pastProject</td><td>曾做过的项目</td></tr><tr><td>foaf:currentProject</td><td>正在进行的项目</td></tr><tr><td>foaf:publications</td><td>发表的文章</td></tr><tr><td>foaf:knows</td><td>认识的人</td></tr><tr><td>foaf:workplaceHomepage</td><td>工作单位网站</td></tr><tr><td>foaf:workInfoHomepage</td><td>从事工作的相关信息</td></tr><tr><td>foaf:schoolHomepage</td><td>学校信息</td></tr><tr><td>foaf:firstName</td><td>名</td></tr><tr><td>foaf:surname</td><td>姓氏</td></tr><tr><td>foaf:lastName</td><td>姓</td></tr><tr><td>foaf:gender</td><td>性别</td></tr><tr><td>foaf:birthday</td><td>出生日期</td></tr><tr><td>foaf:mbox</td><td>邮箱URI</td></tr><tr><td>foaf:mbox_shalsum</td><td>加密的邮箱URI</td></tr><tr><td>foaf:interest</td><td>兴趣</td></tr><tr><td>foaf:geekcode</td><td>网络个性签名</td></tr><tr><td>foaf:img</td><td>图片</td></tr><tr><td>foaf:plan</td><td>工作、个人生活计划</td></tr><tr><td>foaf:jabberID、foaf:aimChatID、</td><td>各种网络账号</td></tr><tr><td>foaf:yahooChatID、foaf:icqChatID</td><td>迈尔斯布里格斯类型指</td></tr><tr><td>foaf:myersBriggs</td><td>标(表征人的性格)</td></tr></table></body></html>

其中，用 foaf:mbox 或 foaf:mbox_shalsum 作为识别个人的URI，名字等不具唯一标识性，而不同人使用不同的邮箱，FOAF用邮箱代表背后使用的人[20]。foaf:knows表示认识的人，通过该标签可以很容易把相关人员和实体关联起来形成社会网络，从而丰富个人规范数据相关参照。

# 4基于FOAF丰富个人名称规范数据的方案设计

利用FOAF丰富名称规范数据流程如图1所示。

![](images/49e27473520a26356e4d38b4733957c5b6e4ec7c36c9d08da2a73c5a45487d08.jpg)  
图1利用FOAF丰富个人名称规范数据的方案设计

使用语义爬虫软件根据限制条件获取FOAF文档集合，采用相关算法和名称规范数据进行匹配，匹配成功则利用URI自动发现聚合个人信息，并根据FOAF标签与规范数据MARC字段的映射自动完善规范数据，匹配失败则对FOAF文档进行筛选用于名称规范数据的新建，从而扩大规范库种类和数量，具体实施方案如下。

# 4.1 识别和获取FOAF文档

选用开放语义资源作为信息源的一个重要原因是可由计算机自动批处理大量数据，而人只是制定规则。在获取资源之前，要制定限制条件、类型和规则，保证获取资源的有效性，具体方案如下：

(1）识别限制条件

数据集满足下面条件即视为FOAF文档：

$\textcircled{1}$ 是有效的 RDF文档;

$\textcircled{2}$ 文档使用FOAF命名空间;

$\textcircled { 3 } \mathrm { X }$ 是rdf:Property的实例并且来自FOAF命名空间;

$\textcircled{4}$ 在主体位置只能有一个类型为foaf:Person的实例并且不能作为文档中任何三元组的客体。另外，文档中出现的其他 foaf:Person 实例必须作为客体，不能出现在主体位置。

其中涉及的 FOAF RDF 模型如图 $2 ^ { [ 1 6 ] }$ 所示。

![](images/f7c86330617a4b9105c9f4a5c8622bdeb9d90df9844441b03d44b417553de8c0.jpg)  
图2 FOAF文档模型  
图3FOAF资源的自动发现及整合

在具体实施时,RDF 的有效性使用RDF 解析器验证；命名空间通过检索是否包含"http://xmlns.com/foaf/0.1/"判断；条件 $\textcircled{3}$ 可以具化为判断foaf:X的rdfs:domain(定义域)是否为foaf:Person；条件 $\textcircled{4}$ 是理想的FOAF文档，在实际中过于严苛，可以将其简化，排除没有揭示实例的情况就是符合定义的FOAF文档[16]。

# (2)获取接口的选择

关联数据的获取方式有5类：SPARQL查询准确率高，但需掌握相关语法及获取的资源少；WebServiceAPI可长期、批量获取数据，但需熟悉API背后的各种协议；批量下载简单直接，但不适用于大规模、更新频率高的数据源；动态网页抽取和语义搜索引擎/爬虫能同时获取多个数据源资源，但受自身算法、策略影响大[21]。结合以上5种获取方式的优势和劣势，本文选用语义爬虫方式，如 LDSpider[22]，目的是发现更多未知、可能存在的语义数据集。

# (3）收割规则

为不引起版权纠纷，在搜索数据集时要注意数据规定的访问权限，选择访问方式为免费和可开放获取的关联数据集；对于有限制的数据集获取其公开部分的元数据内容。

获取FOAF文档是迭代的过程。将前述规则转化为语义爬虫中有效提问，相继搜索包含FOAF命名空间、foaf:Person及文件类型为.foaf的文档和后缀为.rdf、.xrdf、.owl的RDF文档，从而收集FOAF文档和URIs集合。并再次在语义爬虫中利用已搜集的URIs和FOAF词汇，如 foaf:knows 和 rdfs:seeAlso，发现新的FOAF文档。通过在爬虫中搜索发现,FOAF文档主要来自于博客，常用标签排名为foaf:mbox_shalsum、foaf:nick、foaf:name、foaf:homepage、foaf:knows、foaf:birthday、foaf:interest 和 rdfs:seeAlso 等[16]

# 4.2 FOAF个人信息的自动发现及聚合

RDF具有开放性和互联性，实体经RDF描述、发布后可被计算机检索和处理，并可将网络上离散的数据片段自动关联起来发现新内容。数据之间的链接主要依靠三元组中谓词和URI的使用，其中谓词只要根据应用领域选择相应的RDF 属性即可[23]。

如在FOAF中，从个人发布的FOAF文档中获取信息，还通过唯一标识 foaf:mbox 或foaf:mbox_shalsum或 foaf:homepage 游历到另外的FOAF 文档,从而自动发现和整合文档集合中有关此人的所有信息，也因此可用来完善规范数据的附加成分、单纯参照和注释，提高个人名称规范数据质量；FOAF通过foaf:knows将自己的朋友、同事或认识的人关联起来,再通过唯一标识匹配FOAF文档集中不同个体的owl:sameIndividualAs(个体相同)关系[24]，这样分散的文档集合就能形成社会网络，可帮助构建、完善个人名称规范数据的相关参照。

通过分析语义数据集的谓词和获取URI集合，就可以使用开发包或已有的语义搜索软件发现和整合语义资源。其中，对RDF数据有处理能力的开发包有Jena[25]、Sesame[26]和 $\mathrm { P H P } ^ { [ 2 7 ] }$ 等,已有的语义搜索软件有Sindice[28]、Swoogle[29]等。图3是利用FOAF搜索器 NetEstate[30]对上海图书馆刘炜自动发现和整合的结果。

Keven iuakaKeven   
Klick on the question mark behind a particular ple of information to explore it's origin. Type: Person ?   
Titlei Dr ?   
Name:Keven Liu 2, kevenlw 2, 刘炜 ？   
Phone: tel:86-21-64455555-8358 ?   
Nicks: Keven ?   
Homepage: http://www.kevenlw.name ?   
Workplace Homepage: http://www.library.sh.cn ?   
Depictions: http://pic.yupoo.com/keven/2b3692c0a036/medium.jpq ?   
mbox_sha1sum:79b0d1f43f08470a8a261cfe707b7d1a3c100803 2   
uri: http://www.kevenlw.name/kevenfoaf.rdf#me ?   
Knows:   
Dan Brickley aka danbri ?   
Eric_Miller ?   
Haiqing uin ?   
LeonZhao?   
Marcia ZengakaMarcia ?   
Qldhuai ?   
Is known by:   
HUANG Tianqing aka_Beefsteak ?   
Qing Zou aka caveman ?   
晓亮陈akasogq？

通过URI (foaf_shalsum)排除同名异人，聚合同人异名，检索结果都为上海图书馆刘炜的相关信息;通过相关谓词，即FOAF标签自动发现、聚合同一信息项，如"刘炜"本人发布的FOAF文档姓名为"KevenLiu"，通过foafshalsum及foaf:name可自动发现文档集合中他人描述"刘炜"使用的名字"KevenLiu"和"刘炜”，并通过 foaf:name 标签整合显示；另外 foaf:knows将文档集中所有认识此人和此人认识的人自动聚合在一起，即用嵌套在 foaf:knows 中描述的结构进行关联,

最终形成个人社会网络。

# 4.3 FOAF与名称规范数据的自动匹配及丰富

为高效开展规范数据的丰富，需开发自动匹配算法识别规范记录对应的FOAF唯一标识。“姓名/生卒年/著作”、“姓名/生卒年"和"姓名/著作"组合对个人的识别度依次降低，可根据信息完整程度和是否匹配成功，逐一采用这三种组合进行自动识别；另外姓名作为匹配的主要内容，要充分利用名称规范数据的变异名称和FOAF昵称，使同一人的不同名称形式都参与比较提高匹配率。规范数据匹配FOAF唯一标识的算法如下:

(1）分别抽取名称规范记录200字段名称及其400字段变异形式、200\$f和挂接书目数据 $2 0 0 \$ 45 e$ ，建立集合 $\mathrm { N _ { i j } }$ 、Bi和 $\mathrm { { W _ { i } ( N _ { i j } } }$ 为规范记录i的第j个名称, $\mathbf { B } _ { \mathrm { i } }$ 和 $\mathrm { \Delta W _ { i } }$ 分别为规范记录i的生卒年和著作);

(2）分别抽取FOAF 文档 foaf:lastName+foaf:first  
Name 及 foaf:nick、foaf:birthday 和 foaf: publications  
建立集合 $\mathrm { F _ { m n } }$ 、 $\mathrm { B } _ { \mathrm { m } }$ 和 $\mathrm { W _ { m } ( F _ { m n } }$ 为 FOAF文档 $\mathbf { m }$ 的第 $\mathfrak { n }$   
个名称, $\mathrm { B } _ { \mathrm { m } }$ 和 $\mathrm { W _ { m } }$ 分别为FOAF文档 $\mathbf { m }$ 的生卒年和著  
作)；(3）将 $^ { 6 4 } \mathrm { F _ { n m } / B _ { n } / W _ { n } }$ 与 $\mathrm { \tilde { \ v } _ { i j } / B _ { i } / W _ { i } } ^ { \mathrm { 3 } }$ 匹配，即采用“姓  
名/生卒年/著作"模式并将名称的各种变异形式都与生  
卒年、著作组合进行比对;(4)根据匹配结果再逐一用"姓名/生卒年"和"姓  
名/著作"进行比对;(5）识别成功的建立规范记录对应的FOAF唯一  
标识(foaf:mbox 或 foaf:mbox_shalsum 或 foaf:homepage),  
以便名称规范数据的完善和定期抓取、更新数据;(6)未识别成功的，筛选“姓名/生卒年”模式中

生卒年信息完整的FOAF文档作为新记录，用来丰富名称规范数据种类和数量(著作是否完整无法判断，因此不包括另外两种模式)。

另外，在匹配过程中要对数据进行相关处理、算法进行调整以提高匹配率：

(1）对于姓名，中、日、韩名称直接抽取规范数据200和400字段的\$a与FOAF中foaf:lastName+foaf:firstName、foaf:nick匹配；而外国人的拉丁文名称则选取200字段\$c(去除其中逗号)、400字段 $\mathbb { S } \mathrm { a } + \mathbb { S } \mathrm { b } |$ （去除之间逗号)与foaf:lastName+foaf:firstName、foaf:nick匹配,如果比对未成功，则对姓名进行缩写以提高匹配率。

(2)对于生卒年，有些规范数据因著录错误将生卒年著入 $\mathbb { S } \mathrm { a }$ 和 $\$ 1$ 中，可通过判断是否为日期数据获取该信息；对于完整生卒年信息未匹配成功的情况，可逐一去除生卒年末尾数、卒年或生年以提高匹配率[31]

(3）对于题名，对书目数据中不规范、错误著录进行处理，如检验是否为题名和删除当中的姓名；去除两类集合中题名的标点符，如破折号、方括号、冒号等；对于拉丁文要去掉前后空格、去除开头冠词和助词和不区分大小写等[32]

计算机可以解析RDF数据含义，通过语义标签定向找到相关信息，因此只要将个人RDF资源语义标签和规范记录MARC字段建立映射，计算机程序就能自动将RDF数据收割到规范记录对应的字段中去，用于完善名称规范数据。在FOAF中，根据名称规范记录揭示的个人信息项寻找与之对应的FOAF属性，并将属性对应的标签和名称规范MARC字段及子字段建立映射，如表2所示：

表2FOAF标签与个人规范数据CNMARC字段的映射  

<html><body><table><tr><td>CNMARC</td><td>字段解释</td><td>FOAF 词汇</td><td>说明</td><td>重复与否</td></tr><tr><td>091$aFOAF $bURI</td><td>开放数据类型FOAF 及URI</td><td>foaf:mbox或 foaf:mbox_shalsum 方便数据定期维护</td><td></td><td>可重复</td></tr><tr><td>091$aSKOS $bURI</td><td>与FOAF对应的SKOS 及URI</td><td>foaf:focus</td><td>与 SKOS搭配使用，帮助指明不同 SKOS体系中的个人和团体</td><td>可重复</td></tr><tr><td>120$a</td><td>编码数据字段</td><td>foaf:gender</td><td>区分于200$c职业行业</td><td>唯一</td></tr><tr><td>200$c</td><td>附加成分</td><td>foaf:interest</td><td>职业、行业</td><td>可重复</td></tr><tr><td>200$f</td><td>生卒年</td><td>foaf:birthday</td><td></td><td>唯一</td></tr><tr><td>391$a</td><td>发表著作</td><td>foaf:publications</td><td></td><td>可重复</td></tr><tr><td>391$b</td><td>开展项目</td><td>foaf:pastProject、foaf:currentProject</td><td></td><td>可重复</td></tr><tr><td>391$c</td><td>工作计划</td><td>foaf:plan</td><td></td><td>可重复</td></tr></table></body></html>

(续表)   

<html><body><table><tr><td>CNMARC</td><td>字段解释</td><td>FOAF词汇</td><td>说明</td><td>重复与否</td></tr><tr><td>392$a</td><td>性格</td><td>foaf:myersBriggs、foaf:geekcode</td><td></td><td>可重复</td></tr><tr><td>392$b</td><td>博客</td><td>foaf:weblog</td><td></td><td>可重复</td></tr><tr><td>392$c</td><td>人物肖像</td><td>foaf:image</td><td>指向图片库</td><td>可重复</td></tr><tr><td>393$a</td><td>工作单位</td><td>foaf:workInfoHomepage、 foaf:workplaceHomepage</td><td></td><td>可重复</td></tr><tr><td>393$b</td><td>学校</td><td>foaf:schoolHomepage</td><td></td><td>可重复</td></tr><tr><td>400$a</td><td>单纯参照</td><td>foaf:name 或 foaf:lastName+ foaf:firstName、foaf:nick、 foaf:yahooChatID、foaf:skypeID</td><td>其他形式的名字、昵称及网络账号</td><td>可重复</td></tr><tr><td>500$a</td><td>相关参照</td><td>foaf:icqChatID foaf:knows</td><td>相关的人与机构</td><td>可重复</td></tr><tr><td>810$a</td><td>参考数据源</td><td>URI</td><td>发布的URI地址</td><td>可重复</td></tr></table></body></html>

启用和扩展新字段对个人名称规范数据中信息进行结构化处理。我国名称规范格式中，200字段附加成分\$c、300字段个人相关信息并没有进行区分，为符合当下编目主流趋势，适应RDA规则及新修订的UNIMARC规范格式，也方便名称规范库后续开发利用，建议启用和扩展新字段对个人信息进行结构化处理。其中，启用120字段用于区分200字段附加成分性别与职业；因FOAF多个属性与 $3 0 0 \mathbb { S } \mathrm { a }$ 对应，新增391、392、393字段分别著录个人工作科研情况、兴趣性格和相关团体信息，其中包含的子字段揭示更具体的信息项；新增091字段记录对应语义数据的唯一标识，开放数据处于动态变化中，通过唯一标识可定期完善数据。

# 5结语

本文针对名称规范数据质量差且维护效率低下的情况，提出收割开放语义资源丰富本地名称规范数据的方法，在论述其可行性的基础上以FOAF为例设计实现流程，并制定识别获取语义资源的限制条件、接口方式和收割规则策略，给出发现、整合资源的RDF谓词以及两种实现技术开发包和软件，设计自动丰富名称规范数据的多重匹配算法和映射表。FOAF只是开放语义资源的一个典型应用，只要是与个人相关的开放语义资源，如VIAF、GN、CNO(CSHL NameOntology，冷泉港实验室姓名本体)和SKOS表示的个人主题数据等，都可用于自动发现和收割语义信息，丰富本地个人名称规范数据。

下一步将开展试验工作，重点关注匹配算法的效果，根据结果调整匹配策略和相关参数；另外语义资源与一般资源不同，带有语法和格式，因此要研究数据存储方式和提取、处理的实现技术。

# 参考文献：

[1]Myntti J，Cothran N.Authority Control in a Digital Repository:Preparing forLinked Data [J].Journal of Library Metadata,2013,13(2-3):95-113.   
[2] 刘炜，张春景，夏翠娟．万维网时代的规范控制[J]．中国 图书馆学报,2015,41(3):22-33.(Liu Wei, Zhang Chunjing, Xia Cuijuan.Authority Control for the Web [J].Journal of Library Science in China,2015,41(3):22-33.)   
[3] Elliott S.Survey of Author Name Disambiguation:20o4 to 2010 [J/OL].Library Philosophy & Practice.http://digitalcommons. unl.edu/cgi/viewcontent.cgi?article=1459&context=libphilprac.   
[4] Schreiber G, Raimond Y.PDF 1.1 Primer [EB/OL].(2014- 06-24).[2015-06-07].http://www.w3.org/TR/rdf11-primer/.   
[5] UGC [EB/OL]. [2015-10-21]. http://baike.baidu.com/subview/ 713949/9961909.htm.   
[6] FOAF $2 0 0 0 { - } 2 0 1 5 { + } ^ { \cdot }$ ）[EB/OL].[2015-08-07].http://www. foaf-project.org/.   
[7] BibApp [EB/OL].[2015-10-21].http://bibapp.org/.   
[8] VIVO [EB/OL]. [2015-10-10]. htp://www.vivoweb.org/.   
[9] Gemeinsame Normdate [EB/OL].[2015-06-15].http://d-nb. info/standards/elementset/gnd.   
[10]Virtual International Authority File [EB/OL].[2015-06-15]. http://www.viaf.org/.   
[11]UK Archival Thesaurus [EB/OL].[2015-06-15].http://www. ukat.org.uk/.   
[12]Library of Congress Subject Headings [EB/OL].[2015-06- 15].http://id.loc.gov/authorities/subjects.html.   
[13]Simple Knowledge Organization System [EB/OL]. (2012- 12-13).[2015-06-15].http:/www.w3.org/2004/02/skos/.   
[14]Golbeck J,Parsia B.Trust Network-Based Filtering of Aggregated Claims [J]. International Journal of Metadata, Semantic and Ontologies,2006,1(1): 58-65.   
[15]刘炜．关联数据：概念、技术及应用展望[J].大学图书馆学 报,2011,29(2):5-12.(Liu Wei. Overview on Linked Data: Concept,Technology and Implementation [J]. Journal of Academic Libraries,2011,29(2):5-12.)   
[16]Ding L,Zhou L,Finin T,et al.How the Semantic Web is Being Used: An Analysis of FOAF Documents [C].In: Proceedings of the 38th Annual Hawaii International Conference on System Sciences.IEEE,2005:113-121.   
[17]FOAF Vocabulary Specification 0.99[EB/OL].[2015-07-11]. http://xmlns.com/foaf/spec/.   
[18]FOAF-a-Matic [EB/OL]. [2015-07-31]. http://www.ldodds. com/foaf/foaf-a-matic.en.html.   
[19]Quatuo [EB/OL].[2015-07-31]. http://www.quatuo.com/.   
[20]Dumbill E.XML 观察：使用 XML 和 RDF 找到朋友[EB/ OL].[2015-08-18].http://www.ibm.com/developerworks/cn/ $\bf { x m l / x }$ -watch/part3/index.html.(Dumbill E.Finding Friends with XML and RDF[EB/OL].[2015-08-18].http://www.ibm. com/developerworks/cn/xml/x-watch/part3/index.html.)   
[21]王思丽，马建玲，李慧佳，等．关联数据集中开放资源的 自动获取研究[J]．图书馆学研究，2015(18):49-54.（Wang Sili,Ma Jianling,Li Huijia,et al. Research on Obtaining Open Resource in the Linked Data Automatically [J]. Research on Library Science,2015(18): 49-54.)   
[22]LDSpider [EB/OL]. [2015-07-31].https://github.com/ldspider/ ldspider.   
[23]Graves M,Constabaris A,Brickeley D.FOAF:Connecting People on the Semantic Web [J].Cataloging& Classification Quarterly,2009,43(3-4):191-202.   
[24] Motik B，Parsia B.OWL 2 Web Ontology Language Structural Specification and Functional-Style Syntax (2nd Edition) [EB/OL].(2012-12-11).[2015-08-12].http://www. w3.org/TR/2012/REC-owl2-syntax-20121211/#Symmetric_O bject_Properties.   
[25]Apache Jena [EB/OL].[2015-10-21].http://jena.apache.org/.   
[26]Sesame [EB/OL].[2015-10-21]. http://rdf4j.org/.   
[27] PHP[EB/OL].[2015-10-21]. http://php.net/.   
[28]Sindice:Disambiguation Page [EB/OL].[2015-10-21]. http:// www.sindice.com/.   
[29]Semantic Web Search-Swoogle [EB/OL].[2015-10-21].http:// swoogle.umbc.edu/.   
[30]NetEstate.Friend of A Friend (FOAF）Search Engine [EB/OL].[2015-10-21].http://www.foaf-search.net/.   
[31]FRBR Work-Set Algorithm Version 2.0[EB/OL].[2015-10- 11].http://www.oclc.org/content/dam/research/activities/frbralgorithm/2009-08.pdf.   
[32]FRBR Work-Set Algorithm [EB/OL].[2015-10-11].http://www. oclc.org/content/dam/research/activities/frbralgorithm/2005-04. pdf

# 利益冲突声明：

作者声明不存在利益冲突关系。

收稿日期:2015-08-23   
收修改稿日期:2015-10-23

# Enriching Personal Name Authority with Open Semantic Resources: FOAF for Schema Design

Hao Jiashu (National Library of China, Beijing 1Ooo81, China)

Abstract: [Objective] This study ctreated a new model to improve the qualityand maintenance efficiency of the personal name authoritydata in China.[Methods] To prove the feasibilityof using open semantic resources to enrich the name authoritydata,this study analyzed the numberand types ofsemantic resources,evaluation metrics,automation and maintenance speed,as wellas the credibilityof the open resource.TheFOAF was used as anexample to implement the schema.[Results]This studyset restriction conditions,interface mode and harvest rules forobtaining the semantic resources.It created RDF predicate and two realizing techniques,like SDK and software to discover and integrate resources.This study designed automatic multi-matching algorithm and mapping table to automatically enrich name authority data.[Limitations]Only creates the schema, which was not putinto practice.The semantic resource's storage model and theextraction procesing methods are alsoatthe initial framework stage.No detailed implementation technology was discussed.[Conclusions] The proposed method could be automatically matched with open semantic resources of the individual names to enrich local personal name authority data.

Keywords: Personal name authority Open semantic resourcesAutomatic discovering and aggregating RDFURI FOAFAutomatic matching and enriching

# 耶鲁大学图书馆加入人文科学开放图书馆合作资助系统

耶鲁大学图书馆加人了人文科学开放图书馆(OLH)的图书馆合作资助系统。此次合作将为耶鲁大学和世界各地的学者提供数量更多、质量更高的人文科学开放获取出版物。

OLH的创始人和学术项目主管Martin Paul Eve指出：“我很高兴耶鲁大学能够加入我们。很显然，每个人都将受益于开放研究，但我们必须找到一种方法促进人文学科发展符合经济规律。在耶鲁这样的机构帮助下，我们将实现这一目标。人文科学开放图书馆是一个学术主导、无需作者支付费用的金色开放获取出版平台。该平台的启动资金来自于Andrew W.Mellon基金会，并且该平台的其他费用均由国际化的图书馆联盟支付，而不收取任何形式的作者费用。

耶鲁大学馆藏建设主任DanielDolar补充说:“学术交流新的资助模式仍然是一个重要的试验领域。耶鲁大学图书馆很高兴能够支持学术资源的公共获取，正如人文科学开放图书馆所预想的那样。”在这种情况下，Arcadia 基金的慷慨资助使得本次合作成为了可能。

(编译自:htp://web.library.yale.edu/news/2015/06/yale-university-library-joins-open-library-humanities-library)

(本刊讯)