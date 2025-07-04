# 面向实体的知识面板推荐模式分析

高广尚² 张智雄1(1.中国科学院文献情报中心，北京100190；2.中国科学院大学，北京100190)

【摘要】为系统理解基于实体的知识面板这一信息推荐模式及其工作原理，借助知识图谱和实体搜索技术的基本思想对其开展研究。首先，分析知识面板的数据源。接着，分析知识面板中知识模块的设计与规划。最后，对知识面板的工作流程进行分析与探讨。通过研究发现，为实现在知识面板中推荐相关领域知识这一目的，这不仅涉及用户的需求模式和知识模块的设计与规则，而且还涉及概念数据库的构建和各种与实体相关的因素等。

【关键词】知识面板；知识图谱；实体搜索中图分类号：TP393

# Analysis of Knowledge Panel Recommended Mode for Entity

Gao Guang-shang1,2² Zhang Zhi-xiong (1.National Science Library of CAS, Beijing 100190 2.University of Chinese Academy of Sciences,Beijing 100190 )

Abstract: In order to systematically understand information recommendation mode of entitybased knowledge panel and its operating principle,this paper studies how it works on the basis of the basic ideas of knowledge graph technology and entity search technology. First, this paper analysed the data sources of knowledge panel. Then， analysed the designs and plannings knowledge module of knowledge panel. Finally, analysed the work flows of knowledge panel. This study suggests that knowledge panel technology not only needs to consider user demand patterns and designs of the knowledge module, but also consider the construction of concept database and various related factors etc. to show relevant domain knowledges in a knowledge panel.

Key words:Knowledge Panel； Knowledge Graph； Entity Search

# 1 引言

随着语义Web的发展，互联网正从仅包含网页和网页间超链接的文档万维网（DocumentWeb）转变为包含各种实体和实体间丰富关系的数据万维网（DataWeb）。在此背景下，各大搜索引擎公司正以数据万维网为基础构建知识图谱（如Google的知识图谱）以期改进现有的搜索质量，并进一步实现从实体搜索（语义搜索）角度来满足用户更深层次的潜在信息需求。知识面板（Knowledge Panel）中显示的内容是搜索引擎在知识图谱上执行实体搜索后返回的结果[]。更具体地说，其内容是与某一特定实体最相关的结构化摘要信息，例如显示与奥巴马总统相关的孩子、夫人、生日、教育以及其他实体等信息。这里，奥巴马总统被看作是一个实体，教育和生日等信息被看作该实体的属性。其中，实体可能是那些来自用户查询语句中识别的实体、Web文档中识别出的实体2或某一话题被当作一个实体等[3]。

本质上，知识面板中的内容是特定于某实体的知识图谱表示，是实体搜索的一种具体展示形式。与传统上基于关键词的搜索过程相比，实体搜索能更有效、更直接地从知识图谱中找出与实体最相关的结构化摘要信息，因为实体搜索关注的重点不是“关键词”级别的信息，而是知识图谱中“实体”级别的信息。这些结构化摘要信息不仅能很好地被用来面向用户动态、智能地推荐信息资源，而且在不需要用户去执行额外查询操作的情况下就能“智能地”显示给用户。此外，知识面板在为用户提供精准信息资源的同时，同样也为用户节省了大量宝贵的时间。

从表面上来看，知识面板中显示的内容不会使用户的世界产生很大的不同，因为用户同样可以通过访问奥巴马总统的维基百科页面来获得大致相同的信息。但从更深层次上来看，知识面板显示内容的机制代表了搜索引擎公司在工程领域中的重大变革，因为它似乎能像人一样去思考并挖掘出最相关的数据信息[4。鉴于此，本文通过分析知识面板的实现机制一一搜索引擎如何借助知识图谱和实体搜索技术来识别查询中涉及到的实体（概念）及其属性，并根据实体的重要性展现相应的知识面板—一来深入理解知识面板这一信息推荐模式，从而为日后设计、开发类似的知识面板推荐模式提供切实可行的参考。

# 2 相关研究

“OneBox”技术作为知识面板技术的雏形，其最初的简单应用是用来显示天气（如输入“天气 地名”）、某个词语的定义（如输入“define:XXX”或“what is XXX”）、音乐（如输入一个乐队的名字）和书籍（输入一个书名）等一些信息[5]。随着信息海量般的逐渐增多，这种信息展示技术不能很好地提供满足用户搜索背后广泛意图的信息，因为它未能很好地结合用户当下的行为数据。为更好地结合这些用户行为数据以最大程度地满足用户的信息需求，谷歌于2007年发布一个专利并对此进行了详细的研究论述。该研究指出，要实现在单一知识面板中灵活显示相关信息，搜索引擎就需要知道如何以及什么时候显示结果，这不仅涉及到众多的用户行为数据，而且还涉及到底层的众多信息资源库。其中与用户相关的行为数据包括：用户所在的国家、使用的语言、能确定用户身份的Cookie信息、查询语句所使用的语言、发送查询的时间、以往的访问日志数据、查询语句中的词项和信息资源库中文档或对象的词项等信息。信息资源库包括：图像资源库、网页资源库、新闻资源库和产品资源库等。基于上述信息，该研究提出了针对行为数据进行建模的方法，以期通过模型来预测并决定是否要搜索一个特定的信息资源库，并从中显示抽出的结果。

尽管前面的研究在结合用户行为数据的基础上很好地满足了用户的信息需求，但在内容显示粒度上仍不够精简，比如显示的内容是相对“粗糙”的文档或对象汇聚结果，而且彼此间缺乏某种语义关联，并且没有充分考虑到查询语句中包含的其他信息，如实体及其关联信息等。另外，值得指出的是，后台信息资源库的设计并未很好地将知识及其关联信息以分类的形式组织并进行保存，从而导致其提供的信息未能很好地帮助用户理清知识体系这一重要目的。

随着知识图谱技术[和实体搜索技术[8,9的出现，以实体为研究对象的知识面板技术逐渐引起了业界的关注[110]。这些研究指出，为了能在知识面板中展示丰富的语义相关信息，需要从3个方面来对知识面板技术进行规划：一是挖掘出用户查询语句中引用的实体；二是识别出与该实体相关的内容项，并提供针对该实体的一系列用于显示的知识模块；三是知识面板本身可集成在现有的搜索结果页面中或其他弹出窗口中。尽管这些研究深刻揭示了知识领域的动态变化规律：（1）知识面板中的内容是与某个实体最相关的数据，而不是文档或对象；（2）这些数据是由在知识图谱上对该实体执行搜索而得到的最相关信息;（3）这二者的实现都要按相关性、重要性进行动态排序。但这些研究还存在不足，比如未能很好地结合知识图谱和实体搜索技术来深刻阐述知识面板技术的实现机制或工作原理，因为知识面板的工作机制是基于这两项技术。

此外，在另一项研究中，作者设计了一个名为“SidePoint”的、嵌入隐性搜索技术的外围知识面板[]。在实际应用中，该知识面板显著降低了用户信息发现成本，并且满足了用户的两种信息需求：主动需求（用户尝试通过主动的Web 搜索来满足其信息需求）和潜在需求（用户原先没有预料到，但当浏览时，信息需求却通常被同时得到识别和满足）。为此，作者认为在每单位时间的用户关注成本情况下，获得有价值的信息与用户使用的信息环境有很大关联，比如使用知识面板。

# 3 知识面板的应用现状及重要意义

# 3.1应用现状

借助知识图谱和实体搜索技术，搜索引擎公司正在搜索领域发起一个新的转变。这种转变是：更少关注关键字匹配，更多关注概念匹配和理解实体以及在知识面板中向用户提供与实体相关的更多丰富知识，而不仅仅是链接[12]。由于知识面板具有提供摘要信息这一特性，因此各大搜索引擎公司正日益加大针对知识面板技术的应用研究力度，以期能为用户提供多样性的创新服务。为对这些已经上线的应用有一定的了解，笔者收集和整理了一些基于知识面板技术实现的重要应用。

$\bullet$ 回答比较问题，展示比较的事物。比如，如果用户想比较橄榄油和黄油的营养价值，知识面板中能显示拥有众多细节的对比图[13]。  
$\bullet$ 帮助用户快速找到自己喜爱的电影，音乐和汽车等服务的合法来源。谷歌新推出的“Listen Now"模块用来显示与某位音乐艺术家相关的音乐列表，除了提供能获得这些音乐免费版本的链接外，它还提供能获得这些音乐的其他服务链接，这些服务包括：Spotify、Rhapsody、BeastsMusic 和GooglePlay等。除了音乐外，谷歌也在知识面板中测试“书本”，“社交网络”，“电影”和“汽车”等相关内容的显示，这涉及销售、租赁价格等信息[14,15]。  
$\bullet$ 帮助用户找到免费的、按学科分类的在线课程资源。此外，帮助用户获得有关可在线购买的书籍、可在当地图书馆借阅的书籍或可在线完全访问的书籍等信息[16]。  
$\bullet$ 显示针对某一实体（如某商品、政治人物等）的来自不同用户的完整评论。这些评论信息来自不同的信息源，比如多个网站上针对相同的实体所进行的不同评论[17]。显示针对学校的评价、学校的排名和学校的学术指标等信息。用于显示的学校包括从小学到高中，再到高等教育。此外，还提供排名细节（如在国内，州内和 STEM教育内）、该地区的附近学校以及如何与这些学校进行比较等信息[18]。  
$\bullet$ 以弹出窗口的形式来展示相应的内容。当用户移动光标到页面中包含的某实体时，与之相关的信息被自动智能地显示在弹出的知识面板窗口中[2]。  
$\bullet$ 显示与食品和药品相关的内容。提供极其详尽的可供浏览的分类信息或一些建议信息[19]。

通过对这些正在运行的服务的分析可以知道，知识面板正被用来向用户展示越来越有用的信息。并且相信随着知识图谱中包含的知识越全面、越细化，或者说包含的知识体系更加完善，搜索引擎也就越“聪明”。从而，显示在知识面板中的信息就有可能越精确，并最终涌现出更多服务用户的创新服务模式。

# 3.2重要意义

通过自动在后台驱动一个信息发现会话，知识面板技术可将发现的信息展示给用户，这不仅可向用户提供那些用户从来没有想过、但要在线搜索才能获取到的信息，而且还满足了向用户提供潜在信息需求的目标。换言之，知识面板技术的集成性和智能性意味着它对未来诸多创新服务模式的应用有着非常重要的意义。为此，笔者总结出其中的6大重要意义。

# （1）提供相关数据

仅提供与特定实体相关的重要数据。知识面板技术利用相关性来深度“理解”用户的行为，并由此执行下一步搜索以显示具体的内容，并按重要性排序这些相关内容。这种应用仅在与实体（或用户）直接相关的事物中进行分析、搜索并给出答案，并实现将搜索由“搜索信息”向“理解搜索”转变。这与传统搜索提供类似信息中转站的方式截然不同，即传统搜索能够向用户提供丰富的搜索结果，但却无法直接回答相关问题。

# （2）减少访问次数

减少用户必须通过访问页面来获得相关事实信息所需的访问次数。知识面板技术不仅没有分散用户的注意力，而且还“践行”了这样一种搜索理念，即“搜索的未来，就是不需要搜索”。这种应用将依靠其掌握的数据来为用户智能匹配信息—一你不必去搜索，更别说去点击第二页、第三页的操作。更进一步来说，这种应用将使每个人的信息入口日益个性化、精准化和集中化。

# （3）减少时间开销

减少用户为满足其信息需求而必须花费的时间开销。知识面板技术从根本上减少了传统上所需的费时检索操作，即当希望在互联网上搜索结果时，不管结果列表如何呈现和组织，用户仍然需要自己挑选。随着知识图谱中的数据日益完善，以及实体搜索引擎日益“聪明”，这种应用将结合用户的上下文环境等信息主动推送信息到用户面前，从而减少用户的查找时间，并有可能催生新的“匹配 $+$ 推送”模式。

# （4）改善用户的信息推荐体验

展示收集并梳理过的信息。知识面板技术将与实体相关的信息收集起来并进行梳理，并用统一的形式展示给用户。这种应用不仅方便地帮助用户了解简明扼要的结构化摘要信息，而且还帮助用户从多个角度详细了解某方面的知识体系。从而使推荐的信息更加符合用户的心意。

（5）辅助导航

提供指向其他相关主题的链接。知识面板技术让用户容易地以一种“无缝和自然”的方式选择该链接作为当前实体的跟进查询，从而实现对某资源进行一定程度上的挖掘目的。这种应用以通过展示包含链接的且满足用户潜在需求的信息组合的方式，来实现用户浏览信息时的辅助导航。并有可能催生多样化的业务服务模式。

# （6）提供新的内容

展示那些通过其他方式不易发现的信息。知识面板技术不再局限于以传统的方式组织、展示和排序信息。这种应用能在理解用户搜索意图的基础上，提供字面上完全无关，但意思相关的信息，甚至有可能提供那些用户从来没有想过要在线搜索的信息。

# 4 知识面板的实现机制

# 4.1数据源

知识面板技术是一种在面向特定任务的知识库上实现特定目标信息发现和识别的智能知识服务。尽管知识面板的显示过程看作是搜索引擎如何决定为哪些查询显示相应知识面板的过程，但其中整合来的信息需要利用多个单独的数据源，而且这些数据源包含的数据是整理的以实体为单位组织的结构化数据，形如实体-属性-值和实体-关系-实体。以谷歌于2012年发布的知识图谱为例，它是一个基于实体（概念）的知识库。据不完全统计，到目前为止它包含有5亿个实体和35亿条事实]。由于有知识图谱和实体搜索技术作为后端支撑，因此知识面板中显示的内容不是文本的简单堆砌，而是要点的回答。而且，这个实现过程不是一个简单的信息检索过程，更多地是一个数据验证过程（通过实体间的关系）。这部分解决了信息精准推送的问题。

图1所示是一个知识面板。当用户在Google搜索引擎中输入“Barack Obama”查询语句后，结果页面的右上角位置就会自动显示出一个知识面板。其显示的内容是搜索引擎返回的“BarackObama”实体的最相关摘要信息。可以看出，其中所展示的信息具有条理清晰、简单明了和关联性强等特性。显然，这些信息来自许多单独的数据源。本质上，知识面板中的内容由2类关联信息组成：实体的属性信息和与实体相关的其他实体信息。其中，图1中的属性信息包括出生日期、子女、实体图片和婚姻等基本信息，以及社交信息等非基本信息。这些非基本信息就是同时与其他实体存在着关联的信息，它们是构成内容丰富的知识面板的重要组成部分之一。相关的其他实体信息则显示在“People alse search for”下面的列表中，这些实体以链接的形式提供，方便用户点击以再次执行实体搜索。

# Barack Obama

4,582,631 followers on Google+Follow 社交信息

![](images/319cb430b0ca1a0d809ceceedc7343fb437c245e906a9c1fe1c15290f14ccdd3.jpg)

Barack Hussein Obama II is the 44th and current President of the United States, and the first African American to hold the office. Wikipedia

Born: August 4, 1961 (age 53), Honolulu, Hawaii, United State Full name: Barack Hussein Obama II Spouse: Michelle Obama (m. 1992) 基本事实信息 Parents: Ann Dunham,Barack Obama,Sr. Siblings: Maya Soetoro-Ng,Malik Abongo Obama, More Children: Natasha Obama, Malia Ann Obama

# Recent posts

# 社交信息

![](images/87d35ebdcc43ecb4232b8b6afe70a7893e7eb1880cc6cbea2cb08d818e83a4f9.jpg)

Good things are happening in the economybut there's still more to do. http://ofa.bo/p0n3 16 hours ago

![](images/447e502c294fec56c72a5f63098a42ffb13dc0fad199bf4c1cfa2ced6a6b8cba.jpg)  
图1显示实体“BarackObama"的知识面板

# 4.2知识模块的设计与规划

考虑到知识面板中的信息可能来自多个数据源，比如图像、视频、音频、新闻文章、产品和评价等，因此在显示这些信息时需要采用不同的内容组织形式以规范这些信息源的显示方式，这个内容组织形式就是知识模块。同时它也是让知识面板能“智能”显示内容的前提条件[20]，鉴于此，笔者从真实世界中存在的各种实体或概念出发，并在结合知识图谱和实体搜索技术的基础上分析了知识模块与实体类别的关联、知识模块在知识图谱中的体现以及其知识模块间的相关性。

（1）知识模块与实体类别的关联

众所周知，不同行业、不同领域中包含有不同的知识模块（与知识图谱中的实体类别相对应），在知识模块下又有不同的知识点（与知识图谱中的实体相对应），在各个知识点下还有不同的内容项（与知识图谱中的属性相对应）。它们在知识图谱中的展示形式可用图2来表示。对图中的每个实体来说，除了与实体关联的基本属性外，还有与实体关联的众多实体类别，正是这些实体类别让实体的语义关联信息得以丰富，因为实体搜索技术可在这些关联的实体类别上执行搜索[21]。为让这些实体类别及其相关信息能在知识面板上显示，因此需要预先设计不同的知识模块以匹配知识图谱中相应的实体类别。这些模块可能包含有“人物”、“地方”、“地点”、“电影”、“产品”、“图像”和“书籍”等。当然，在实际应用中，将依照实际业务中的需要来细化、设计相应的知识模块。

另外需要考虑的是，对一个知识模块来说，可能还存在有多个与其相关联的子模块，对于这些细化的子模块，同样需要建立起相应的特定知识模块。例如，针对一个“人物”知识模块，可能有一个用于“演员”知识模块，有一个用于“歌手”知识模块，还有另一个用于“政治人物”知识模块等。同样，这些子模块的设计仍然依照实际业务中的需求而定。

（2）知识模块在知识图谱中的体现

图2中给出了一个实体、实体类别及其关系网络子图，它是对知识图谱中所包含信息的一个形象描述，其主要由点和边组成。其中，实体网络可能包含3类结点：

$\bullet$ 实体：如前文所述，实体可以是任何事物。图2中的实体包括 $\mathrm { E } _ { \mathrm { l } }$ ， $\mathrm { E } _ { 2 }$ 和 $\mathrm { E } _ { 3 }$ 。  
$\bullet$ 语义类（实体类别、知识模块）：一种类型的实体或一些实体的集合，如“国家”、“城市”、“学校”、“人物”和“政治人物”等。图2中 $\mathrm { C } _ { 1 } , \mathrm { C } _ { 2 } , \mathrm { C } _ { 3 }$ 和 $\mathrm { C } _ { 4 }$ 为语义类。  
$\bullet$ 文本：通常作为实体和语义类的名字、描述等，或者说是属性值，如图2中的$\mathrm { T } _ { 1 } { \sim } \mathrm { T } _ { 5 }$ 。

此外，该网络中结点之间的边的类型分为3种：

$\bullet$ 实体一语义类：从一个实体指向它所属的语义类。此类型的边在图2中标记为“类”。  
$\bullet$ 子类（实体类别、知识模块）一父类（实体类别、知识模块）：从一个语义类指向其父类，在图1中用“超类”来标识。值得说明的是，在实际应用中可能存在很多这样的关联，而且关联错综复杂。  
$\bullet$ 属性：从一个实体指向它的属性值。不同的属性类型对应于不同类型的边，如图2中“出生地”，“妻子”和“出生”是3种不同的属性。所有实体和语义类都拥有一个特殊的属性“名字”，它指向文本类型的结点，表示此实体或语义类的名字或自然语言表达（如中文名、英文名等）。

![](images/1159c76f26ec6739bd4452392a8d2ccec5952e204e606545dd80f464978676a9.jpg)  
图2实体、实体类别及其关系网络子图

（3）知识模块间的相关性

从图2中可以看到，一个实体不仅关联到多个属性，而且关联到多个实体类别。在知识面板中显示与该实体相关信息的过程就是，按相关性在如图2所示的网络图中选出那些与实体最相关、最具价值的内容项的过程。整个选取过程的实现通过实体搜索技术来完成[22]。除了网络图中已有的实体间、实体类别间的相关性外，实体搜索技术还要借助与实体相关的一些其他重要相关性信息来匹配出知识图谱中的重要内容项，比如上下文环境、新颖度、重要度、用户当前的地理位置、访问日志和最近的用户会话信息等。当然，不管是哪种相关性，它们都通过某一权值大小来表示其与实体的相关性大小，拥有较大权值的内容项就有可能被选择作为候选项[23]。如此一来，搜索出来的内容就可能越准确，越符合用户的搜索需求。

# 4.3工作流程的分析与探讨

知识面板的核心思想是：显示与某个特定实体最相关的结构化摘要信息而不是一类文档，以更好地满足用户的信息需求。本质上，这个显示过程就是实体搜索算法在理解用户意图的基础上，在知识图谱中实施搜索并给出最直接结果的过程。其中包含2类核心检索子任务：一是利用相关性在知识图谱中找到相应的实体；二是在前一步的基础上再利用实体类别和实体关系等信息找到关联的实体[24]。为对知识面板的内容显示过程有一个系统的理解，或者说为对其工作原理有一个较系统的理解，笔者归纳总结出一个由10个部分组成的工作流程，并在此基础上进行详细阐述。

图3所示的工作流程始于一个实体，在经过一连串复杂的内部运算操作后，最后展示出面向用户的知识面板。从图2的实体网络子图中可以看出，对某个实体来说，除了有与其相连的特定基本属性外，还存在有与其相连的其他实体，它们同样被理解为该实体的属性。为更合理地描述，这里将实体的一个个属性称为一个个内容项。依照知识面板中内容的显示顺序，笔者逐一对工作流程中的每个组件所提供的功能进行详细分析。

![](images/4408ff1eb2b0520ddb7178c9f0fa319c0a215e04632b8c6e6a01f4aa66fa4b8e.jpg)  
图3知识面板的工作流程

（1）实体

知识面板中的内容显示与用户的查询语句相关联，具体来说，与查询语句中的实体相关联。但是，查询语句中的实体的表现形式可能并不规范，为此需要对它进行各种处理以形成一个规范的实体，比如利用查询语句的上下文环境等信息来对该实体进行去歧操作等。经过规范处理后，系统便获得与实体关联的实体类别、关系和上下文环境等信息。

# （2）识别实体的标准内容项

对每个实体来说，其标准内容项包括标题、典型图像、描述信息等与实体相关的、最基本的事实信息。这些信息就是图2中所示的基本属性信息。考虑到实体可能拥有多达几十个、甚至更多的属性，因此，系统需要依据实体的上下文环境等信息对每个标准内容项分配一个动态产生的排序分值，该值被用来表示与实体的相关度、流行度大小，从而确保那些具有较高分值的标准内容项有可能被选择作为候选内容项。

# （3）识别实体的附加内容项

实体的附加内容项是那些被识别出的且与当前实体存在关联的其他实体或信息。这些被识别出的其他实体或信息同样可能多达几十个、甚至更多。为此，系统需要依据实体的上下文环境等信息对每个附加内容项分配一个动态产生的排序分值，该值被用来表示与实当前体的相关度、流行度大小。比如某个附加内容项的排序分值可能比另一个附加内容项的排序分值要大，那么和另一个附加内容项相比它可能被认为与当前实体更相关。此外，具有较高排序分值的附加内容项可能被选择作为实体的候选内容项。

# （4）识别每个内容项的内容类别

为每个识别的内容项确定其内容类别。同一个词（实体）在不同的语境下会有完全不同的意义，为让计算机理解该词的涵义，系统需要充分利用实体的上下文环境等信息。在知识图谱中，一个实体与多个实体类别存在关联，因此，确定内容类别的过程就是充分利用实体的上下文环境等信息，来计算内容项与每个内容类别间的相似性大小的过程。如果计算结果的值较大，那么表示该内容项与内容类别有着某种程度的高度关联，从而确定其可作为候选内容类别。通常可以利用的方法有：基于集合、基于内容、基于词汇级类别标签相似性和基于层次结构的距离测量等。此外，内容类别还可被用来对与相同或相似实体类别有着直接关联的内容项进行分类。最后，内容类别也可能表示一种内容类型，例如，一个图像内容的类别能被用来识别图像文件的内容项。

（5）识别内容类别的首选模块类型

给每个内容项或内容项的类别指定一个首选模块类型。例如，系统可能给“电影”类别中分类的内容项指定“图像”模块作为它们的首选模块类型。在这个例子中，被识别为“演员”的“电影”类别中的内容项，将通常以“图像”模块中的图像形式来呈现。其中，首选模块类型的选择操作是基于那种适合呈现有关内容项信息的内容类别的表示来进行。正是这首选模块类型丰富了知识面板中显示的内容，因为在显示实体的相关信息时，有可能仅希望显示的内容是相应的图片、表格或可比较的内容等信息，而不是其它不那么相关的信息。

（6）基于首选模块类型、识别的内容项的排序分值和知识面板的面板约束条件来选择将被提供在知识面板中的知识模块

系统至少在某种程度上基于被识别内容项的排序分值和被识别内容的类别来选择知识模块。同时，它也“考虑”到知识面板的显示空间有限等诸多因素以决定显示哪个知识模块

（7）给选定的知识模块分配识别的内容项

给每个识别的内容项或部分识别的内容项分配选定的知识模块。其中，分配过程基于内容项的内容类别来进行。例如，给每个内容类别指定一个知识模块，接着给每个内容类别分配部分识别的内容项。如果知识模块对内容项有限定数目的占位符，例如，只允许一排5个图像的图像模块，那么系统可能分配具有最高排序分值的内容项给知识模块。另外，具有较低排序分值的内容有可能被排除在知识模块外或有可能作为对用户额外请求的响应而被包含在知识模块内（如将上下文环境等信息考虑在内的请求）。

（8）给知识面板中的位置分配选定的知识模块

系统基于被识别内容项的排序分值或基于知识面板的显示约束来给知识面板中的相应位置分配知识模块。其中，显示约束为每个知识模块类型指定一个顺序，从而根据这个指定的顺序，知识模块可被分配到各自的知识面板中的位置。例如，约束可能指定图像模块显示在知识面板的底部位置。如果有多个知识模块被选择，例如两个或更多图像模块，那么基于分配给知识模块的被识别的内容项的排序分值，多个知识模块可能被分配到知识面板中的相应位置。

在实现过程中，系统可定期使用离线处理的方式为实体选择知识模块和内容项。或者在用户的查询时间内执行该操作，通过在查询时间内选择知识模块和内容项，知识面板能呈现最新的内容项，并且内容项在时间上也更关联。例如，与即将到来的事件相关的内容项。

（9）用选择的知识模块和识别的内容项填充知识面板

一是使用标准内容项填充知识面板模板，二是使用已识别的并分配给知识模块的内容填充该知识模块。

# （10）提供知识面板

知识面板可以显示在页面中的某个适当位置，或在与用户互动时以弹出窗口形式呈现，从而可作为某一实体的结构化信息推荐框。其中这些收集来并整理过的信息将以统一的形式展示给用户，为的是简明扼要地让用户了解实体（关键词）的主要信息，进而缩短用户查找信息时所花的时间。此外，知识面板还可以在多种设备上显示，如智能手机和平板电脑等。

# 5 结论

知识面板作为一种新颖的信息推荐模式正逐渐受到业界关注。由于知识面板具备让用户可以自动获得信息而不用主动寻找信息这一特性，因此，它能很好地满足用户的信息需求，同时它也代表了计算和搜索的未来。本文对知识面板技术的实现机制及其相关内容进行了深入分析研究，尤其是对数据源、知识模块的设计与规划和工作流程进行了详细分析。从研究中了解到，为将与实体相关的诸多信息有条件地显示在知识面板中是一项巨大的挑战，因为它不仅需要充分利用组织好的结构化数据及其关系（知识图谱），而且还需要一种全新的搜索技术（实体搜索）。

分析研究表明，为将知识面板作为一种新的信息推荐模式来推荐相关领域知识，首先，需要充分挖掘用户的需求模式，并预先规划、设计好待展示的相关内容点。其次，需要将现有的知识按形如“实体-属性-值”和“实体-关系-实体”的结构来重新组织，并组织成一个可更新的实体数据库。最后，需要对不同类型的实体、实体类别和关系等信息预先设计不同的知识模块，以适应不同的显示需要。此外，在具体实现时还要将用户当下的各种相关性因素考虑在内，比如将这些信息设计成一个可统一调度的模型。总的来说，对于知识面板中的内容能否很好地满足用户的需求，主要由基于多种相关性的综合决策过程来决定。在未来的研究中，笔者将对实体搜索技术进行研究，以期能更好地满足用户对知识获取的需求，或者说更好地满足用户对搜索服务新的需求。当然，为实现全面、高效的信息推荐服务，唯一的办法是创造一个开放的生态系统。

# 6 参考文献

[1]GOEL KJ， THAKUR SA，LEVY JL， et al. Knowledge panel [EB/OL].[2014-10-09]. https:// www.go0gle.com/patents/WO2013173099A3?cl=en&dq $\vDash$ Knowledge+panel&hl $\circleddash$ en&sa $\downharpoonright$ X&ei=JKRE VOSiM8WaygO-04G4DA&ved=0CCcQ6AEwAQ.   
[2]SANTOS J， MARTINS B， BATISTA D S. Document Analytics through Entity Resolution[M]. / / Web Information Systems Engineering-WISE 2013.Berlin Heidelberg: Springer, 2013: 531-534. [3]WANG Y，LI H，WANG H，et al. Toward Topic Search on the Web [C].// International Confer ence on Conceptual Modeling. Berlin: Springer, 2012: 421-431.   
[4]The Web Gets Smarter[EB/OL].[2014-10-09].http://www.newyorker.com/culture/culture-desk/th e-web-gets-smarter#ixzzlvl0xk2lI.   
[5]Google's OneBox Patent Application [EB/OL]. [2014-08-11].http://searchengineland.com/google s-onebox-patent-application-10325.   
[6]ANGELO M，BRAGINSKY D，GINSBERG J，et al. Determination of a desired repository [E B/OL]. [2014-7-01].https://www.google.com/patents/US7584177?dq $\risingdotseq$ Determination+of+a+desired+re pository&hl=en&sa $\circleddash$ X&ei=0aNEVJveOaG8mAXW84KQDw&ved=0CB8Q6AEwAA.   
[7]Official Google Blog: Introducing the Knowledge Graph: things, not strings[EB/OL]. [2014-7-01]. http://googleblog.blogspot.com/2012/05/introducing-knowledge-graph-things-not.html.   
[8]Future SEO: Understanding Entity Search[EB/OL].[ 2014-07-01]. htp://searchengineland.com/fut ure-seo-understanding-entity-search-172997.   
[9]Entity Search And Its Affect On SEO & Search Listings[EB/OL].[2014-07-01].htp://www.selesti. com/blog/entity-search-end-of-seo/.   
[10] HENRY JW. Providing Knowledge Panels With Search Results [EB/OL]. [2014-10-11].https://w ww.google.com/patents/WO2013020084A1?cl=en&dq $\circleddash$ Providing+Knowledge+Panels+With+Search+ Results&hl=en&sa $\circleddash$ X&ei=iqNEVJDrMcTXmAXFg4KoAQ&ved=0CB8Q6AEwAA   
[11] LIU Y， EDGE D， YATANI K. SidePoint: a peripheral knowledge panel for presentation slide au thoring [C]. Proceedings of the SIGCHI Conference on Human Factors in Computing Systems. Paris, F rance:ACM,2013: 681-684.   
[12] Introducing the Knowledge Graph: things, not strings[EB/OL]. [2014-08-11].http:/insidesearch.bl ogspot.com/2012/05/introducing-knowledge-graph-things-not.html.   
[13] Google Improves Knowledge Graph With Comparisons And Filters, Brings Cards & Cross-Platfor m Notifications To Mobile[EB/OL]. [2014-08-11].http://techcrunch.com/2013/09/26/google-improvesknowledge-graph-with-comparisons-and-filters-brings-cards-to-mobile-search-adds-cross-platform-not ifications/.   
[14] Music Is Google's Latest Ad Test In The Knowledge Panel[EB/OL].[ 2014-08-11]. http://searchen gineland.com/music-googles-latest-ad-test-knowledge-panel-200137.   
[15] Google Testing More Ads On Knowledge Graph Panels: Google Play Gets The Spotlight[EB/OL]. [2014-08-11].htp:/searchengineland.com/google-testing-ads-knowledge-graph-panels-184584. [16] Bing Adds Khan Academy Courses & Book Finding Results[EB/OL]. [2014-08-11].htp://searche ngineland.com/bing-adds-khan-academy-courses-book-finding-results-195589.   
[17] Google Now Displaying Full Review Snippets in the Knowledge Panel[EB/OL]. [2014-07-01].htt p:/lumenthals.com/blog/2014/04/23/google-now-displaying-ful-review-snippets-in-the-knowledge-p anel/.   
[18] Bing Adds School Ratings To Search Results[EB/OL].[ 2014-08-11]. htp:/searchengineland.com /bing-adds-school-ratings-search-results-196989.   
[19] Bing Expands Snapshot With New Food & Drug Entities[EB/OL].[ 2014-08-11]. htp://searchengi neland.com/bing-expands-snapshot-new-food-drug-entities-191742.   
[20] I Am an Entity: Hacking the Knowledge Graph[EB/OL]. [2014-07-01].http://moz.com/blog/i-aman-entity-hacking-the-knowledge-graph.   
[21] ZHANG J，QUY，TIAN S.A Novel Entity Type Filtering Model for Related Entity Finding [J]. International Journal of Computers Communications & Control， 2014，9（1） ： 113-124. [22] BRON M， BALOG K，DE RIJKE M. Example based entity search in the web of data[C]. / Ad vances in Information Retrieval. Berlin Heidelberg: Springer-Verlag,2013: 392-403.   
[23] HECK L， HUANG H. Deep Learning of Knowledge Graph Embeddings for Semantic Parsing of Twitter Dialogs [C]. /IEEE Institute of Electrical and Electronics Engineers. Berlin Heidelberg: Spring er-Verlag,2014: 291-299.   
[24] BLANCO R， CAMBAZOGLU B B，MIKA P， et al. Entity Recommendations in Web Search [C]. / The Semantic Web-ISWC 2013. City: Springer, 2013: 33-48.   
[25] CONSTANTIN B R， MARIUS PA. Disambiguation of named entities [EB/OL].[ 2014-10-01]. https://www.go0gle.com/patents/CA2647738A1?cl=en&dg $\vDash$ Disambiguation+of+named+entities&hl=e n&sa $\downharpoonright$ X&ei=n6JEVLz4GIHgyQO184LQBg&ved=0CC0Q6AEwAg.   
[26] VALLET D, ZARAGOZA H. Inferring the most important types of a query: a semantic approach [C]. Proceedings of the 31st annual international ACM SIGIR conference on Research and developmen t in information retrieval. Singapore:ACM, 20o8: 857-858.   
[27]Microsoft Has Big Plans For Bing's Entity Engine[EB/OL].[ 2014-07-01]. htp:/techcrunch.com/ 2014/03/30/microsoft-has-big-plans-for-bings-entity-engine/.