# 基于LOD的注释服务技术研究\*

于倩倩1,²李春旺」」（中国科学院国家科学图书馆，北京 100190）²（中国科学院研究生院，北京100049）[摘要]本文对基于关联开放数据(LOD)进行的文本、图像和视频等Web 资源注释服务的相关技术方法进行了梳理和总结，介绍了注释流程中的关联数据查询技术、语义消歧技术、关联扩展技术、关联数据过滤技术和关联模型技术，并提出注释服务应用面临的问题。

[关键词]LOD注释服务 关联数据[分类号]G250.7

# Study on Technologies of Annotation Service Based on LOD

Yu Qianqian1,2 Li Chunwang

1(National Science Library， Chinese Academy of Sciences，Beijing l00l90，China) ²(Graduate University of Chinese Academy of Sciences， Bei jing l00049, China) [Abstract] The annotation service technologies of Web resources such as text， image, video and so on based on LOD are analyzed and summarized, including linked data querying technology， semantic disambiguation technology， relevance expansion technology，linked data filtering technology and relevance model technology， then challenges of annotation service are proposed.

[Keywords] LOD Annotation service Linked data

# 1背景

注释是附加到其它信息片段的信息。为Web 资源内容主题如人名、机构名等实体对象或某一领域的主题概念做注释，提供帮助人们理解web 资源内容的解释、补充片段或元数据信息等即为注释服务。Web资源种类繁多，包括文本、图像和视频等，对Web 资源进行注释，一方面可以帮助用户更好地理解知识，另一方面便于用户更准确地搜索到自己所需要的内容。

W3C 启动的关联开放数据(LOD)项目近年来发展极为迅速，截止2011年9月，LOD已收录295个数据集，提供大约310亿个RDF三元组以及大约5.04亿个RDF链接。关联数据的发布与应用为注释服务的发展带来了新的契机，目前越来越多的组织和机构利用关联数据为Web资源提供注释服务，其基本原理是针对Web资源中的主题，从LOD数据集中发现并获取与该主题相关的关联数据信息，帮助用户理解Web资源内容以及扩展相关知识。

注释服务是关联参考服务的一种，根据Web资源类型的不同，可以将注释服务分为文本注释服务、图像注释服务和视频注释服务等。其中，文本注释服务的相关研究如GarciaEO等利用关联数据资源对教学文档中的名词、术语做注释，帮助学生在课程中理解和扩展相关主题的知识；Rusu D等利用 LOD 中 DBpedia、OpenCyc 和WordNet数据集对web文本中的主题进行注释，帮助用户理解文本内容等。图像注释服务相关研究如 SonntagD等利用LOD 中DrugBank、Diseasome和DBpedia三个数据集中的信息为医学图像提供注释功能，支持医生利用扩展信息推断可能的疾病并根据病症给出相关的药物信息；BeckerC等利用DBpedia、GeoNames和Freebase等关联数据集对地图信息做注释，提供用户当前地理位置的背景信息及相关信息，为用户旅行提供导航等。视频注释服务的相关研究如HaslhoferB等利用关联数据为视频注释信息做扩展，当用户添加注释信息后，系统自动显示注释信息的相关信息，帮助用户理解视频内容；KoHG等利用关联数据对多媒体内容做注释，针对用户观看多媒体内容时输入的关键词，系统自动显示关联数据相关信息，帮助用户消除关键词存在的歧义问题等。

根据资源链接方式的不同，可以将注释服务分为URI链接服务、语义扩展服务和元数据添加服务等。其中，URI 链接服务如 Mendes PN 等构建的 DBpediaSpotlight系统利用DBpedia URIs自动注释用户提供的文本片段主题，通过URI链接可以发现文本主题的相关信息；ChoudhuryS等"利用关联数据对YouTube视频标签(tag)、用户评论信息做注释，建立视频标签或评论信息到关联数据源中 URI的链接，通过URI链接发现更多的相关信息。语义扩展服务如 Klebeck A等l2构建的Ontos Feeder利用DBpedia、Freebase 等关联数据集对网络博客实体对象进行注释，高亮注释实体并通过悬浮窗显示从关联数据集中获取的相关信息；HalbW等创建的在线内容编辑工具Link2Wod 关联编辑内容中的术语到关联数据中相关的多媒体信息等，使编辑能更好地控制他们发布的内容等。元数据添加服务的相关研究如SimonR等对关联数据为地图提供的注释信息进行保存，在检索时以元数据形式出现，提高检索效果；VirgilioRD 等15将识别出的 web页面实体对象与关联数据相关信息进行链接，以RDFa标签形式存储，对web 页面进行自动注释。

本文对基于LOD的Web 资源注释服务技术方法进行梳理和总结，并对关联数据查询、语义消歧、关联扩展、关联数据过滤、关联模型等注释服务技术进行分析，以便为相关研究提供借鉴。

# 2关联数据查询技术

利用关联数据提供注释服务，首先需要将web资源主题转换为关联数据的描述形式。关联数据查询即是从LOD数据集中获取与web资源主题相匹配的关联数据资源的过程。分析已有的注释服务可以发现，关联数据查询技术主要包括SPARQL查询、语义网搜索引擎查询和资源匹配等技术方法。

# 2.1 SPARQL查询

SPARQL 是一种基于图模式匹配的RDF 数据查询语言，使用 SPARQL查询，能够快速获取指定数据源中的相关数据。典型的应用项目如LatifA等对计算机科学期刊的作者信息提供的注释服务。

想要获得作者 Arnold Schwarzenegger 的相关信息，首先需要找到与其相匹配的关联数据 URI 如 http://dbpedia.org/resource/Arnold_Schwarzenegger。LatifA等将DBpedia中的Persondata数据集通过RDFDump方式下载到本地，获取作者信息，使用ARC 存储工具构建提供 SPARQL 查询接口的本地三元组存储库。对于用户输入的查询字符串，使用 SPARQL 查询在本地三元组存储库中查找作者的相关信息。SPARQL查询准确率高，但需要数据源提供 SPARQL查询端点。此外，SPARQL查询还可以用来进行关联数据资源遍历和对遍历结果进行过滤。

# 2.2语义网搜索引擎查询

语义网搜索引擎如 Sindicel、Falcons18和 Swoogle'等关联数据应用都提供API支持搜索关键词。典型的应用项目如KoHG等"对多媒体内容如网络电视(IPTV)

进行的注释服务。

Ko HG等°使用SindiceAPI查询用户输入的关键词，选取返回结果中的前n个 RDF 结点作为最具代表性的结点。然后通过 SKOS 中的关系属性 skos:broader和 skos:narrower比较代表性结点相对的概念层级，选取其中的上位类结点作为匹配结果。语义网搜索引擎可以在整个LOD空间中对关联数据进行查询，但是返回的数据质量参差不齐，准确率相对较低。在数据源未知的情况下，可以使用这种方法进行查询。

# 2.3资源匹配

资源匹配通过关联数据URI解析或关联数据属性信息，获取Web资源主题的关联数据描述形式。如将Web 资源主题词项与DBpedia资源的URIs匹配或将词项与 DBpedia 资源的 Label 值匹配2。

首先，将词项转化为DBpedia URI后缀形式（首字母大写或复合词间使用下划线)，URI 后缀是去除‘http://dbpedia.org/resource/’之后的字符串；其次将词项与DBpedia的rdf:label进行匹配，DBpedia的labels 是从Wikipedia页面的题名创建而来，几乎所有的DBpedia 资源都提供rdf:label；然后使用DBpedia 重定向属性（‘http://dbpedia.org/property/redirect’）获取同义词或字母缩写资源；最后使用DBpedia消歧属性（‘http://dbpedia.org/property/disambiguates’）获取多义词资源；如果以上匹配均失败，则将匹配所有以词项作为子串的资源。资源匹配简单、直接，但需要了解数据源使用的词汇表及其表达形式。

# 3语义消歧技术

将web 资源主题与关联数据资源匹配的过程中，由于web 资源主题本身存在的歧义性，会导致一个web 资源主题与若干个关联数据资源相匹配。如Washington 可以指美国第一任总统George Washington，也可以指城市名Washington,D.C.则Washington可能与DBpedia资源如dbpedia:George_Washington, dbpedia:Washington,_D.C. 和dbpedia:Washington_(U.S._state)等相匹配。语义消歧就是从关联数据查询得到的关联数据资源中选择最符合Web 资源主题上下文的关联数据信息的过程。典型的应用项目如 Mendes PN 等"构建的 DBpedia Spotlight 系统使用上下文相似度实现语义消歧;RusuD等使用基于LOD数据集内容的上下文相似度和基于LOD数据集结构的PageRank 算法实现语义消歧。

# 3.1上下文相似度

DBpedia Spotlight是使用DBpediaURIs自动注释文本文档的系统。用户提供文本片段(文档、段落、句子),DBpedia Spotlight 注释文本中提及的DBpedia资源。首先识别出文本主题上下文即文本片段中该词汇周围的词，如来自同一个段落的词。然后将文本主题与DBpedia 资源相匹配，找出文本主题在DBpedia 中的描述形式，对于产生的匹配候选项，将其表示为由来自Wikipedia上下文的词项组成的向量，上下文类型有Wikipedia页面、消歧页面等，如Lennon 来自Wikipedia 文本的词项组成向量{Beatles,McCartney,rock,guitar,...}。权重计算公式为 $\mathrm { T F } { * } \mathrm { I C F }$ ，TF是指词项在上下文中出现的次数，ICF是逆候选项频率（Inverse Candidate Frequency）。如果Rs 是文本主题在关联数据中的匹配候选项， $\mathrm { ~ n ~ } ( \mathrm { w } _ { \mathrm { j } } )$ 是Rs中与词项 $\mathrm { w _ { j } }$ 相关的候选项个数，则

$$
\mathrm { I C F ~ } ( \mathrm {  ~ w ~ } _ { j } ) = \log \frac { \mid R _ { s } \mid } { n ( w _ { j } ) } = \log \mid R _ { s } \mid - \log n ( w _ { j } )
$$

最后使用余弦相似度计算文本主题上下文与 DBpedia 中匹配候选项的Wikipedia上下文相似度，选择相似度值最大的候选项作为语义消歧项。DBpediaSpotlight在语义消歧方面取得了较好的应用效果，但目前只能识别DBpedia数据集资源，具有一定的局限性。

RusuD等°使用LOD数据集中资源的文本定义，如在DBpedia中，符合人们阅读习惯的资源描述定义为rdfs:comment，对资源的描述类似于摘要。如果文本主题上下文与关联数据候选资源的描述重叠程度越高，则认为两个资源的相近程度越高。将文本主题上下文和候选资源的描述分别定义为A和B两个词袋模型，使用余弦相似度计算这两个词袋模型的重叠程度，最后选择余弦相似度值最高的候选资源作为语义消歧项。很多LOD 数据集如 DBpedia、Freebase、OpenCyc 和WordNet等都具有资源的文本定义，使用这些数据集进行注释服务时，可以参考这种方法进行语义消歧。

# 3.2基于关联数据的PageRank算法

PageRank是对网页结构图顶点进行排序的算法，用来标识网页的重要性。LOD数据集也存在图结构，通过资源之间的关联关系如实例和类之间通过rdf:type连接、类和其父类之间通过rdfs:subclassOf连接等构成图结构。将PageRank 算法应用于LOD数据集，首先构建LOD数据集图G(V,E)，V代表数据集的资源，E代表资源之间的关系，然后识别文本片段中待注释词汇集与关联数据匹配的所有候选资源，即在数据集中，待注释词汇是其rdfs:label值的资源。如果图顶点V不是候选资源，则将其初始化为0，否则将其初始化为 $1 / \mathrm { R }$ ，R是待注释词汇集与关联数据匹配的所有候选资源数量。关联数据资源 $\mathrm { i }$ 的PageRank值计算公式为，

$$
\mathrm { P R } [ V _ { i } ] = \frac { 1 - D } { N } + D \bullet \sum _ { V _ { j } \in I n E d g e s ( V _ { i } ) } \frac { P R [ V _ { j } ] } { O u t E d g e s ( V _ { j } ) }
$$

其中N代表图中所有顶点数，调节因子 ${ \mathrm { D } } { = } 0 . 8 5$ 。迭代计算各结点的PageRank值，直到图中同一结点两次计算的PageRank 值相差小于 ${ 1 0 } ^ { - 1 5 }$ 。最后选择每个待注释词汇的关联数据候选资源中PageRank 值最高的资源作为其语义消歧项。将PageRank算法引入到关联数据中，充分利用了关联数据集的结构信息。对于资源间关联关系较丰富的数据集可以使用这种方式进行语义消歧。

此外，LudwigN等2结合标签上下文和关联数据中候选资源上下文的共现分析以及实体间关系的链接图分析对用户添加的视频标签进行消歧，Garcia-SilvaA等使用DBpedia基于上下文相似度对web 资源如文本、图像和视频等用户添加的标签进行词义消歧。

# 4关联扩展技术

关联扩展是通过Web资源主题在关联数据中的描述形式，进一步获取与Web资源主题相关的关联数据信息的过程。关联扩展是注释服务过程中的重要环节，是关联数据资源发现获取的重要途径。从已有的注释服务可以看出，选择LOD数据集中的相关属性获取关联数据资源是关联扩展的一种方式，还可以在遍历属性的基础上通过结点间的相似性计算选取相关的关联数据资源进行注释。

# 4.1关联数据属性选择

关联数据依据RDF模型的“资源-属性-属性值”的形式进行表达，通过关联数据中的属性，可以直接获取相关的关联数据资源。但关联数据中的属性繁多，如在DBpedia本体中，描述人物的相关属性就有350多个24，因此，需要选择合适的关联数据属性，以提高注释服务的精准性。典型的研究项目如Waitelonis J等202526选择关联数据中的重要属性并对其进行排序，依据这些属性搜索相关资源对Yovisto学术视频元数据进行注释；StanJ等"使用关联数据中的三种关联关系进行语义扩展，对社交论坛用户发布信息中的关键词和实体对象进行注释。

WaitelonisJ等202526认为相关资源的重要程度可以根据属性的重要程度进行衡量，提出启发法对DBpedia中的重要属性进行排序。相关属性排序如下：（1)RDF 属性频次。具有rdf:type 或 skos:subject 的实体的属性频次越高，属性越重要。如果一个实体属于几个分类，则相同属性发生次数加和。（2）具有相同rdf:type 资源的属性。如果两个资源的rdf:type资源是相同的，则连接这两个资源的属性是重要的。（3）预定义类型的属性。如dbpedia:Event和dbpedia:Place，且dbpedia:Event 重要度高于dbpedia:Place。（4）双重链接属性。资源间链接属性不同，却是互相指向。（5）dbpedia:disambiguates 属性。（6）dbpedia:wikilink 属性。具有双向wikilinks链接的资源比只有单向wikilinks 链接的资源重要度更高。（7）Wikilinks入链。（8）List属性。指那些URI后缀以List_of_结尾的资源,如dbpedia:List_of_Nobel_laureates。（9)skos:subject 属性。（10）rdf:type 属性。（11）label子串。实体映射到关联数据时作为子串匹配的资源。

StanJ等使用的关联关系如下：首先是层次链接（hierarchicallinks），关联到上位类概念，以属性subject表示；其次是有相同上位类的邻结点，以属性isbroaderof(subject(c))表示；最后是与起始概念直接关联的概念，如 ClintEastwood 是Gran Torino 的导演。

综上，基于属性进行资源遍历，需要对关联数据集使用的本体及词汇表等比较了解，选取的属性不同，获取的关联数据资源也不尽相同。使用关联数据属性进行资源遍历简单快捷，获取的资源准确率高，但需要对重要属性进行筛选。

# 4.2结点相似性计算

在遍历关联数据属性的基础上，通过计算结点间的相似性选择相关的关联数据资源。典型的应用项目如MirizziR等28293031开发的 SWOC、Not Only Tag 和LEO系统，使用关联数据和外部数据源对IT 领域的词汇概念做注释，这三个系统的后台都是 DBpediaRanker 系统，其主要功能是计算DBpedia 结点间的相似度;Stankovic M等使用hyProximity 计算 DBpedia中概念间的邻近关系。

两个研究项目都是首先选择种子概念作为概念扩展的起点，如DBpediaRanker由领域专家挑选的数据库和编程语言领域的代表性结点为 PHP、Java、MySQL、Oracle、Lisp、C#和 SQLite.然后使用 skos:sub ject 和 skos:broader属性遍历数据集资源，skos:sub ject 表示某个概念属于某个类，skos:broader表示某个类属于某个上位类。根据研究领域的不同，遍历深度也不同，如DBpediaRanker中遍历深度设为2。

两个项目的不同之处在于对结点的相似度计算方式不同，DBpediaRanker系统使用任意两个结点在不同数据源中的相似度权重和作为最终的相似度计算结果，hyProximity基于遍历结点与种子结点的距离进行计算。

在 DBpediaRanker 系统 28293031中，对于搜索到的任意两个 DBpedia 资源结点，使用网络搜索引擎（谷歌、雅虎和必应）、社交标签系统（Delicious）和DBpedia数据源，计算其相似度。选择不同的搜索引擎，可以不局限于一种搜索引擎的算法，使用社交标签系统，除了考虑词汇在网页中的流行度，还考虑了词汇在用户间的流行度。在搜索引擎和社交标签系统中，对于搜索到的两个DBpedia 资源uri和 $\mathrm { u r i } _ { 2 }$ ，相似度计算公式如下：

$$
s i m ( u r i _ { 1 } , u r i _ { 2 } , i s ) = ( \frac { P u r i _ { 1 } , u r i _ { 2 } } { P u r i _ { 1 } } + \frac { P u r i _ { 1 } , u r i _ { 2 } } { P u r i _ { 2 } } ) _ { i s } 
$$

其中，is 代表数据源， $\mathrm { \ p } _ { \mathrm { u r i } 1 }$ 和 $\mathrm { { p } _ { \mathrm { { u r i } 2 } } }$ 分别代表数据源中包含 $\mathrm { \ u r i } _ { 1 }$ 的 rdfs:label集词汇和 $\mathrm { \ u r i _ { 2 } }$ 的rdfs:label集词汇的网页数， $\mathrm { \Delta P _ { u r i 1 , \ u r i 2 } }$ 代表数据源中同时包含两者rdfs:label集词汇的网页数。

在 DBpedia中，对于资源 $\mathrm { \ u r i } _ { 1 }$ 和 $\mathrm { \ u r i _ { 2 } }$ ，一方面考虑Wikipedia到DBpedia的超文本链接wikilink属性。如果资源 $\mathrm { \ u r i } _ { 1 }$ 到 $\mathrm { \ u r i _ { 2 } }$ 有wikilink属性，资源 $\mathrm { \ u r i _ { 2 } }$ 到urii也有wikilink属性，则wikiS( $\mathrm { \chi ( \ u r i _ { 1 } }$ ，uri2)值为2；如果只有资源 $\mathrm { \ u r i _ { 1 } }$ 到uriz的wikilink属性,或只有 $\mathrm { \ u r i _ { 2 } }$ 到 $\mathrm { \ u r i _ { 1 } }$ 的wikilink属性,则wikiS(urii，uriz)值为1；如果资源 $\mathrm { \ u r i } _ { 1 }$ 和 $\mathrm { \ u r i _ { 2 } }$ 之间没有wikilink属性，则wikiS $\mathrm { \langle u r i _ { 1 } }$ ， $\mathrm { u r i } _ { 2 } )$ 值为0。另一方面，检查 $\mathrm { \ u r i } _ { 1 }$ 的rdfs:label是否包含在uri2的dbpprop:abstract中，反之亦然，假设 $\mathfrak { n }$ 是资源label 的个数， $\mathfrak { m }$ 是abstract 中包含资源label的个数，则abstract $\mathrm { { s } ( u r i _ { 1 } , u r i _ { 2 } ) \ = m / n }$ ，其值在[0,1]间浮动。

资源uri和 $\mathrm { \ u r i _ { 2 } }$ 之间的相似度是上述计算的权重和，公式为： similarity $\cdot ( u r i _ { 1 } , u r i _ { 2 } ) = w _ { g o o g l e } * s i m ( u r i _ { 1 } , u r i _ { 2 } , g o o g l e ) + w _ { y a h o o } * s i m ( u r i _ { 1 } , u r i _ { 2 } , y a h o o ) +$ $w _ { b i n g } * s i m ( u r i _ { 1 } , u r i _ { 2 } , b i n g ) + w _ { d e l i c i e n s } * s i m ( u r i _ { 1 } , u r i _ { 2 } , d e l i c i o u s ) + w _ { w i k i S } * w i k i S ( u r i _ { 1 } , u r i _ { 2 } ) + \left| \begin{array} { l l l } { \bar { u } } & { \bar { u } } & { \bar { u } } \\ { \bar { u } } & { \bar { u } } & { \bar { u } } \end{array} \right| _ { 0 }$ $w _ { a b s t r a c t } * a b s t r a c t S ( u r i , u r i _ { 2 } )$

其中权重 $\mathrm { ~ w ~ }$ 均设为1。与单独使用外部资源、单独使用关联数据文本和链接资源、同时使用这两种资源但外部资源中相似度计算使用共现分析等算法相比，本系统资源间相似度计算方法更能反映两个资源之间的关系，具有明显的优势。在关联数据集资源描述较丰富的情况下，注释服务可以借鉴这种方法进行结点相似度计算。

StankovicM等基于DBpedia 结构图的两个主要特征：（1）与起始概念距离越短的概念越相关（2）与若干起始概念邻近的概念比与一个起始概念邻近的概念要更相关，计算结点间的相似性。概念c到起始概念集IC 的 hyProximity计算公式为：

$$
h y P ( c , I C ) = \sum _ { c _ { i } \in I C } \frac { p ( c , c _ { i } ) } { d ( c , c _ { i } ) } ; p ( c , c _ { i } ) = e ^ { - \lambda d ( c , c _ { i } ) }
$$

其中， $\mathrm { d } \left( \mathrm { c } , \mathrm { c } _ { \mathrm { i } } \right)$ 是 $\mathrm { ~ c ~ }$ 与 $\mathrm { \Phi _ { c _ { i } } }$ 的距离，是c与 $\mathrm { \Phi _ { c _ { i } } }$ 共享祖先的最短路径， $\mathrm { { p } ( \mathrm { { c } , \mathrm { { c } _ { i } ) } } }$ 对不同的距离赋予不同的权重，以指数形式在距离上减少概念重要性， $\lambda { = } 0 . 3$ 。使用算法完成hyProximity的计算并进行排序，选择计算结果较高的值作为相近概念，算法限于第3层。该方法利用了关联数据集的结构信息，在关联数据集结构较丰富的情况下，注释服务可以借鉴这种方法进行结点相似度计算。

# 5关联数据过滤技术

从LOD数据集中获取的数据资源通常是比较多的，为了保证获取资源的质量，需要对不相关的资源进行过滤。数据过滤可以在资源发现过程中执行，典型研究项目如Lama M等 4334、Ko HG 等°、Stan J等²和 DBpediaRanker 系统2对新遍历结点的处理过程；也可以在资源发现获取后执行，如 Stankovic M 等2、DBpediaSpotlight系统1°和DBpedia Mobile应用‘等对已获取资源的处理方法。

# 5.1资源发现过程中的数据过滤

Lama M等43334利用关联数据为教育资源添加注释。首先识别出教育资源的主题词，然后搜索 DBpedia 找到相关主题的资源，使用深度优先算法对 DBpedia 资源进行遍历。对遍历的DBpedia属性赋予一定的权重值，如属性 skos:broader的权重值 $\mathrm { w r } _ { \mathrm { s B } }$ 设为0.6、属性rdf:type 的权重值 $\mathrm { w r } _ { \mathrm { R T } }$ 设为0.9等，可以人工赋予，也可以自动获得。如果遍历资源为叶子结点，即三元组宾语为文字，则通过如下公式计算叶子结点与主题词的关系，

$$
\mu ( x ) = a \times \sum _ { i = 1 } ^ { K } ( w t _ { i } \times f t _ { i } ) + b \times \frac { S _ { x } } { K }
$$

其中，K是相关的教育资源主题词数目，i是第i个相关的主题词， $\mathrm { w t _ { i } }$ 是第i个主题词的权重， $\mathrm { f t } _ { \mathrm { i } }$ 是第i个主题词在结点 $\mathrm { ~ x ~ }$ 中的频次， $ { \mathrm { S } } _ { \mathrm { x } }$ 是教育资源与结点x共有的主题词数。如果遍历资源为分支结点，即三元组宾语为URI，则通过如下公式计算分支结点与主题词的关系，

$$
\mu ( x ) = \sum _ { i = 1 } ^ { N _ { x } } w r _ { i } \times \mu ( t _ { i } )
$$

其中， $\mathrm { N _ { x } }$ 是结点 $\mathrm { ~ x ~ }$ 的属性数目，i是第i个属性， $\mathrm { w r } _ { \mathrm { i } }$ 是属性的权重， $\mathrm { \Delta t _ { i } }$ 是第i个属性关联的结点。

Ko HG等°使用语义网搜索引擎的查询响应次数计算结点间的相似度，通过相似度的计算过滤掉不相关的结点。StanJ等计算扩展集中的每个概念与关联数据中的起始概念摘要的相似度，摘要中含有很多与起始概念相关的关键词，这些关键词可作为起始概念的上下文过滤掉扩展集中不相关的概念。在DBpediaRanker系统²中，将新遍历的结点与该领域流行度最高的 DBpedia 分类进行相似度计算，计算方法为关联扩展技术中介绍的不同数据源中结点的相似度计算权重和，如果相似度值高于给定阈值，则认为新遍历结点属于给定领域上下文，如果相似度值低于给定阈值，则将其过滤掉。由此可以看出，资源发现过程中的数据过滤方法主要是结点间的相似度计算，与关联扩展中的结点相似度计算方法通用，但应用场景不同，主要取决于不同应用对相似度计算阈值的选择。

# 5.2资源获取后的数据过滤

StankovicM等对主题概念进行注释，基于DBpedia中的概念类型，过滤掉人、公司和书籍等不相关的概念。DBpediaSpotlight 系统‘基于 DBpedia、Freebase和 Schema.org的本体分类层级概念类型或通过 SPARQL语句对获取的关联数据资源进行过滤。DBpediaMobile应用‘构建基于资源类型、评价等的简单过滤或构建 SPARQL 语句过滤掉不相关的资源。资源获取后的数据过滤主要使用关联数据集资源类型和SPARQL语句进行过滤，对于需要注释特定类型主题的资源，可以使用这种方法对获取到的关联数据进行过滤。

# 6结语

通过分析基于关联数据进行注释服务的已有研究可以发现，其对Web资源的注释主要是对实体对象或主题概念的注释，如Yovisto项目注释的视频元数据包括与视频相关的关键词（从题名、演讲者和描述信息等抽取）以及与视频时间相关的关键词（如使用OCR方法从视频中抽取）和用户对视频所做的标签，极少涉及对某个段落主题或整篇文章主题的注释服务。通过关联数据查询技术、语义消歧技术、关联扩展技术和关联数据过滤技术，可以获取与注释对象相关的关联数据资源。此外，关联模型可以对数字文献中实体对象的相关属性及关联关系进行描述，以指导关联信息发现、融合与可视化呈现等操作’。如LatifA等设计了CAF-SIAL概念集成框架，支持不同人物类型如科学家、艺术家等相关信息的集成融汇；刘媛媛等基于已有的本体（如DBpedia本体）描述方案设计了数字文献中科研人员、科研机构、研究项目等典型实体对象的关联模型。首先根据关联数据源中已有的本体描述结合用户潜在的信息需求对实体对象的相关属性以及与其它实体的关联关系属性进行遴选，构建关联模型；然后依据预先定义的实体间关联关系对注释服务的检索结果进行查询扩展，从而能获取更多的关联数据资源。使用关联模型技术，可以扩展与优化关联数据的检索结果，但是目前关联模型主要是针对数字文献中的实体对象，具有一定的局限性。笔者将继续对注释服务相关环节的技术方法进行研究，同时关注段落主题或整篇文章主题的注释服务，以期在已有方法的基础上尝试构建基于LOD的文献主题注释服务应用，在实践中发现问题和解决问题。错误!未找到引用源。错误!未找到引用源。参考文献：

1 Linked Data and multimedia: the state of affairs   
² http://www.w3.org/wiki/SweoIG/TaskForces/CommunityProjects/LinkingOpenData   
3刘媛媛,李春旺,黄永文．基于LOD 的关联参考服务构建研究［J]．现代图书情报技术,2011，(06):66-71. 4 Garcia E O, Vidal J， Lama M, et al. Semantic Annotaion of Education Resources through Linked Data[C]． In: Proceedings of ICWL. 2010:311-320.   
’ Rusu D, Fortuna B, Mladenic D. Automatically Annotating Text with Linked Open DataC]. In: Proceedings of LDow 2011，Hyderabad，India.2011.   
6 Sonntag D,Wennerberg P.Applications of an Ontology Engineerging Methodology Accessing Linked Data for Medical Image Retrieval[C].In :Proceedings of Linked AI,Califonia,USA.2010:120-125. 7 Becker C, Bizer C. Exploring the Geospatial Semantic Web with DBpedia Mobile[J]. Web Semantics: Science， Services and Agents on the World Wide Web. 2009,7(4):278-286.   
8 Haslhofer B,Momeni E.Augmenting Europeana Content with Linked Data ResourcesC].In :Proceedings of I-semantics 201o,Craz,Austria.   
9 Ko HG, Ko I Y. Generation of Semantic Clouds Based on Linked Data for Efficient Multimedia Semantic Annotation[C].In:Proceedings of ICWE 2011， Paphos，Cyprus. 2011:127-134.   
10 Mendes P N， Jakob M, Garcia-Silva A，et al. DBpedia Spotlight:Shedding Light on the Web of Documents[C]. In: Proceedings of the 7th International Conference on Semantic Systems (I-Semantics)，Graz，Austria. 2011.   
I Choudhury S,Breslin JG,Passant A.Erichment and Ranking of the YouTube Tag Space and Integration with the Linked Data Cloud[C].In:Proceedings of ISWC,Berlin Heidelberg. 2009:747-762. 1² Klebeck A, Hellmann S,Ehrlich C,et al. OntosFeeder - A Versatile Semantic Context Provider for Web Content Authoring[C].In:Proceedings of ESwC 2011   
13 Halb W,Stocker A,Mayer Het al.Towards Commercial Adoption of Linked Open Data for Online Content Providers[C].In:Proceedings of I-Semantics,Graz,Austria,2010.   
14 Rainer Simon， Bernhard Haslhofer，Joachim Jung.Annotations，Tags & Linked Data- Metadata Enrichment in Online Map Collections through Volunteer- Contributed Information.   
15 RDFa Based Annotation of Web Pages through Keyphrases Extraction OTM 2011   
16 Latif A, Afzal M T, Ussaeed A, et al. Turning keywords into URIs: simplified user interfaces for exploring linked data[C]. In: Proceedings of the 2nd International Conference on Interaction Sciences: Information Technology， Culture and Human， Seoul， Korea. 2009:76-81.   
17 Sindice-The semantic web index[EB/OL]. [2012-05-08]． http://sindice.com/.   
18 Cheng G,Ge W,Qu Y Z. Falcons: Searching and Browsing Entities on the Semantic Web[C]. In Proceedings of the Www，Beijing，China.2008. 19 Cheng G, Ge W, Qu Y Z. Falcons: Searching and Browsing Entities on the Semantic Web[C].In Proceedings of the www，Beijing，China.2008.   
20 Waitelonis J，Sack H.Towards exploratory video search using linked datalC]. In:Procedings of the 11th IEEE International Symposium on Multimedia,Washington，DC，USA. 2009:540-545. 21 Brin S, Page M. Anatomy of a large-scale hypertextual Web search engine[C]. In: Proceedings of the 7th Conference on World Wide Web (www)，Brisbane，Australia.1998.   
2² Ludwig N, Sack H. Named Entity Recognition for User-Generated Tags[C]. In: Proceedings of the 22nd International Workshop on Database and Expert Systems Applications (DEXA).2011:177-181. 23 Garcia-Silva A， Szomszor M, Alani H, et al. Preliminary Results in Tag Disambiguation using DBpedia[C].In: Proceedings of the 1st International Workshop on Collective Knowledge Capturing and Representation at K-CAP 2009，Redondo Beach，California， USA. 2009.   
24 DBpedia ontology class Scientist [EB/OL].   
[2011-10-08].http://mappings.dbpedia.org/server/ontology/classes/Person.   
25 Waitelonis J， Sack H, Kramer Z, et al. Semantically enabled exploratory video search[C]. In: Proceedings of the 19th World Wide Web Conference (www2010)，Raleigh，NC，USA. 2010. 26 Waitelonis J， Sack H. Towards exploratory video search using linked data[J]. Multimedia Tools and Applications， 2012,59(2) :645-672.   
27 StanJ,Do VH, Maret P. Semantic User Interaction Profiles for Better People Recommendation[C]. In:Proceedings of ASONAM 2011，Taiwan， China. 2011.   
28 Mirizzi R,Ragone A, Di Noia T， et al. Ranking the linked data: the case of dbpedia[C]. In: Proceedings of ICWE 2010. 2010:337-354.   
29 Mirizzi R, Ragone A, Di Noia T,et al. Semantic wonder cloud: exploratory search in dbpedia[C]. In:Proceedings of the 2th International Workshop on Semantic Web Information Management (SWIM 2010)． 2010:138-149.   
3 Mirizzi R, Ragone A, Di Noia T,et al. Semantic tags generation and retrieval for online advertisingC].In:Proceedings of the 19th ACM International Conference on Information and Knowledge Management (CIKM2010)，Toronto，Ontario， Canada.2010.   
31 Mirizzi R, Ragone A, Di Noia T, et al. What if exploratory search and web search meet?[C]. In: Proceedings of the Fourth Ph.D. Workshop in CIKM,PIKM 2010，Toronto，Canada.2010.   
32 Stankovic M, Breitfuss W， Laublet P. Linked-Data Based Suggestion of Relevant Topics[J]. In: Proceedings of the 7th International Conference on Semantic Systems9(I-SEMANTICS 2011)，Graz, Austria. 2011:49-55.   
3 Lama M, Vidal JC, Otero-Garcia E, et al. Semantic Linking of a Learning Object Repository to DBpedia[C]. In: Proceedings of the 11th IEEE International Conference on Advanced Learning Technologies (ICALT 2011)． 2011 :460-464.   
34 Vidal JC, Lama M, Otero-Garcia Eet al. An evolutionary approach for learning the weight of relations in linked data[C].In: Proceedings of the 11th International Conference on Intelligent Systems Design and Applications (ISDA 2011)． 2011:1002-1007.   
35 Waitelonis J, Nadine L, Sack H. Use What You Have: Yovisto Video Search Engine Takes a Semantic Turn[C]. In: Proceedings of the 5th International Conference on Semantic and Digital Media Technologies (SAMT2010)，Saarbrucken， Germany. 2010.   
36 Latif A,Afzal MT,Saeed A U,Hoefler P,Tochtermann K.CAF-SIAL:Concept Aggregation Framework for Structuring Information Aspects of Linked Open DataC].In:Proceedings of International Conference on Networked Digital Technologies,Ostrava,Czech Repblic.2009:100-105.   
37刘媛媛.基于 LOD 的关联参考服务构建研究[D].北京：中国科学院国家科学图书馆，2011.