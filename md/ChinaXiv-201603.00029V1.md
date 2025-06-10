# 基于科技文献的研究设计指纹描述框架研究

□钱力 张晓林 王茜

摘要提出用于描述科技文献核心知识的“研究设计指纹"概念，综合研究分析了相关的科技文献规范描述框架,创建"基于科技文献的研究设计指纹描述框架”，以增强科技文献的机器计算可执行性、知识粒度性、知识关联性、结构的扩展性以及研究设计思路的可视性，为科研人员快速发现研究设计方法、研究设计工具等指纹提供了新的思路与方法。

关键词 科技文献研究设计指纹知识组织语义出版知识骨干

# 引言

科技文献是科学技术发展的重要战略资源，但随着信息技术的快速发展，数字出版速度加快，海量科技文献也带来一些现实问题：对某一具体研究领域或研究方向，无法快速追踪与了解相关的研究方法、研究设备等核心知识对象，也无法快速客观评估相关知识对象对研究问题的有效性。特别对一个刚刚踏入科研领域的工作者来说，会出现无从下手的局面。

针对上述问题，笔者在调研了科技文献描述规范以及相关写作指南之后，提出利用研究设计指纹对科技文献进行结构化描述，提升科技文献的计算机可识别性、可执行性[1]，帮助科研人员快速了解科技文献的研究方法、算法、工具及结论等，并为未来的科学出版(即语义化出版)提供相应的出版规范参照。论文结构如下：第二部分提出“研究设计指纹"的概念，第三部分就此展开相关研究分析，第四部分提出科技文献的“研究设计指纹描述框架”，第五部分探析其潜在应用。

# 2研究设计指纹概念的提出

科技文献从本质上看是科研人员开展科学研究思路的文本化，也是科研成果发布与传播的重要载体，还是掌握某一研究主题的研究概貌的核心资料。在面对海量科技文献的情况下，如何快速了解文献的研究框架、采用的研究方法以及讲述的研究内容成为图书情报领域关注与研究的主题。论文提出“研究设计指纹”概念，尝试从科学研究设计的视角去解决上述问题，通过对一篇科技文献的知识骨干网络进行结构化描述，揭示出相关研究方法、算法等研究设计指纹，帮助科研人员快速了解研究设计过程以及各个过程中的重要研究设计指纹对象。

目前，“研究设计指纹"没有一个明确的界定，但是“基于本体标引文献的工具"（AnOntologyBasedToolforPreparation of Articles)3」项目组在 2007年开展全文挖掘与标引工作中，抽象出“科技文献核心信息(CoreInformationScientificPapers，CISP)"概念，一定程度上也是对科技文献所包含的重要知识对象的揭示，其定义如下：CISP是来自于知识本体类的一个已定义好的集合，包含的关键类有：调研目标、调研对象、研究方法、结果以及结论等。另外，其他研究项目也提出“核心知识对象”、“科学知识组织体系”、“科技核心"等类似概念。

基于上述描述与概念，本文给出“研究设计指纹"的定义为：描述一个科学研究设计实现过程中拥有多个核心设计元素特征的知识对象。它具有三个主要特征：（1)精炼地“揭示科学研究的设计思路”;(2)结构化地“揭示科学研究方法、过程和结构”；（3)可视化地“揭示科学研究中的骨干知识及其关系”。设计指纹的类型方面，本文主要参考科技文献写作指南（如侯赛因教授[4设计的"研究文献写作指南与要求”、巴达沙利5设计的“写作与出版科技文献的指南"以及有机生物学实验室的“科技文献写作指南"等)，定义了11种设计指纹，即研究假说、研究场景、研究目的、研究背景、研究方法、研究数据、研究算法、研究设备、研究结果、研究结论和未来研究。

# 3相关研究综述

作为一种科研成果的传播载体，科技文献本身具有相应的描述规范，如最初的经典通用模型IM-RAD ( Introduction-Methods-Result-And-Discussion，介绍一方法一结果一结论）、模块化(Modular)模型、语义注解LaTeX（SemanticallyAnnotatedLaTeX，SALT)、W3C提出的科学篇章修辞块本体(OntologyofRhetoricalBlocks，ORB)标准结构模型、ABCDE 模型（Annotation-Background-Contri-bution-Discussion-Entity，注解一背景一贡献一讨论一实体）、科技文献核心信息（CoreInformation Sci-entificPapers，CISP）、关联科学核心词汇（LinkedScienceCoreVocabulary，LSC）、纳米出版物模式（Nanopublication）、面向模型的科学研究报告规范( Model-Oriented ScientificResearchReport,MOSRR)以及Elsevier的未来论文模式（ElsevierArticleoftheFuture)等，以实现科技文献或者资源信息的结构化描述，使文献或者资源具备自动识别执行性、自动理解性等语义特征。本文从组织灵活性、扩展性、粒度性(粗/细)、关系性、结构通用性、计算可执行性以及研究设计指纹特征等七个角度对上述描述规范或者模型进行比对分析，结果如下图1所示，具体描述规范的内容与特征如下。

4名称 组织灵 扩展性 粒度性 关系性 结构通用性 计算可执行性 研究设计指活性 纹特征性IMRAD × × × × √ X XModular X √ √ × √ X XSALT X × √ √ X X XORB √ √ √ √ √ √ XABCDE X X X X √ X XCISP √ √ √ √ √ √ XLSC √ X X √ × √ XNanopublication √ × ? L X √ XMOSRR. X X √ √ X X XElseviar Article - √ X X √ √ XoftheFuture

# 3.1 IMRAD经典模型

IMRAD[7][8]经典模式是在自然科学中基于科学实验报告的原型表示，即：要研究什么问题（Intro-duction)，如何研究上述问题（Methods)，通过研究发现了什么（Results），上述发现意味着什么（Dis-cussion）。IMRAD结构被许多科学杂志认可，并且是国际医学期刊编辑委员会（InternationalCommit-tee ofMedicalJournalEditors)[9]发布的生物医学类期刊的投稿统一要求，即生物医学出版物的写作与编辑中推荐的标准。IMRAD模型发展历程如下图2所示。

19世纪下半个时期， 由于路易斯·巴斯德（LouisPasteur）提早期以叙事为主 加入科学实验 出疾病的细菌理论，加入科学方法IMRAD仍然是文献结构IMRD逐步开始形成化发展的标尺

# 3.2电子文献的模块化模型

基于标准通用标记语言的理论，提出电子文献的模块化结构[10],用标签来识别。一个模块即是能够表达概念的信息单元，划分的依据是其包含信息的连续性与完整性。科技文献的结构本身可以划分模块，如：简介、方法、结果、讨论与结论，这种顺序代表着一篇科技叙述的规范流程。但是，这种叙述流程具有一个先决条件，即要对文献从头到尾进行顺序阅读。但是知识丰富的读者很少进行顺序阅读，而是通过浏览来发现有用的信息点或者信息片。所以作为能够独立用于阅读的模块，其独立性并不是指它能够充分叙述整个工作，而是能够让读者瞬间缩小关注点，快速获取知识。

# 3.3 ABCDE模型

从叙述式阅读到计算机理解的一种好方式是让作者在科研写作过程中，就按照一定的格式创造出具有丰富语义结构的研究文献，基于这一目标，沃德（AnitadeWaard)[11]提出了ABCDE模型，以便研究人员集成、挖掘与分析研究成果：A（Annotation），基于DC元数据标准的文献元数据描述，如标题、作者等；B(Background)，描述研究的定位，当前持续性的问题以及相关的研究问题；C(Contribution），描述作者已经做过的工作，包括调研、实现等；D（Dis-cussion)，描述已经开展过的研究的讨论结果，同时列出各个结果之间的对比分析;E(Entity)，描述一个实体对象，例如人名、工程名称、研究方法等。

# JL

# 3.4 SALT模型

SALT[12]是利用语义标注原理丰富科学出版的一个语义创作框架。SALT提供了用来识别出版物的修辞结构与论证内容的方法，实现核心是创建三种本体即文档本体、修辞本体与标注本体，它们之间的关系结构如图3所示。利用SALT支持科学出版的过程大致分为两个阶段：第一阶段是SALT过程，主要负责分析标引和将本体实例嵌入到最终的PDF文档中，分为综合分析与标引抽取、标引与本体创建和PDF文档编译三个步骤;第二阶段是出版过程，将第一阶段生成的语义PDF文档集作为输入集合，生成一系列对应且具有索引的HTML文件。目前SALT不仅支持LaTeX的创作环境，其模型还可被用于其他环境来丰富科学出版，出版过程如下图4所示。

![](images/a5cca7e1a29a522df3051b5275ab8b33c43860fc5950f79784aadfee04d2cc5f.jpg)  
图3SALT本体组成元素框架  
图4SALT支持科学出版的过程

documentclass(article) SALT   
Paper title:SALT   
SALdor Groza AuthorTudor Groza   
Date:10/12/2006   
begintabstract)   
Machine-understandable data [] Abstract   
lend(abstract) Machine-understandabledata sal   
lsection(introduction) [] Motivation   
begin(motivation} Also...   
Asoclamc1Kexisting support for   
metadata inPDF ispoor). RSTforMotivation   
Athough PDF definesa particular field   
forembedding metadata init[]   
xpanatione1Kdublin core isnot Evidence:   
sufficient)[] ·Claim:existing support for The current status of the field is metadata in PDFispoor represented by ashallow... ·Explanation:"dublin core is not motivaonyevidencep1]（c1:e1) sal-webpub enough"   
□   
section[Conclusion) Conclusion   
In this paper we have describeda In thispaper we have   
solution[]   
LaTeX HTML

# 3.5 ORB修辞模型

$\mathrm { O R B ^ { [ 1 3 ] } }$ 是W3C于2011年发布的文献修辞块结构描述标准，目标是提供一个规范化结构来表示科技文献中的所有描述知识项，从而推动科技文献结构表示的标准化、语义化及实用化。ORB不仅可以在新创作的科学文献结构中增加语义，也可以标引已经出版的科学文献。它类似于利用插件式操作方式实现对科技文献内容结构的灵活控制，主要有以下特征：融入修辞模块粗粒度集合，如表示摘要、研究背景等段落；文档内容提供了细粒度语义入口，如具体的某一句话或者某一句话的某一部分、某一个词等。ORB在内容结构的组织上分为头部、主体和尾部。

# 3.6 CISP结构模型

JISC于2007发布的大学研究报告介绍了科学文献核心信息描述的一种新模式 $\mathrm { C I S P ^ { [ 1 4 ] } }$ ，主要利用本体方法体系来开发与组织以科学实验为基础的科技文献的元数据，挖掘与揭示其内在的逻辑关系、语义关联关系以及各个组成元素的清晰定义，如定义了调研目的、调查动机、调查对象、研究方法、开展的实验、观察发现、结果与结论等本体类别。

# 3.7 纳米出版物计划项目

为了解决发现、关联与设计学术研究中特殊核心科学描述的困难，概念网络联盟启动了纳米出版物计划[15]。它利用计算机作为辅助工具，从文献和数据中抽取研究结论、研究事实或研究结果，以三元组的模式建立起语义关系，从而使文献结构的动态性、机器计算可执行性得到加强，更好地支持后期的大数据处理与挖掘。虽然目前此计划对于学科领域的依赖性、数据处理的针对性相对较强，但是对相关研究来说具有很好的借鉴意义。

# 3.8 MOSRR规范模型

虽然科学研究报告已经结构化了（比如上述的IMRD模型)，但是知识单元的粒度相对还较大，仍然以自由文本表示为主。而MOSRR 规范模型[16]在一定程度上改进了上述问题，能通过结构化使信息具有更小粒度角色，可以更灵活嵌入到科研工作流中，帮助改善与提升科学研究报告的结构化程度。同时此模型也可以支持数据密集型的科学研究以及灵活的研究工作流设计等活动。

# 3.9Elsevier发起的“未来论文”项目

Elsevier的未来论文项目[17是2009年开始发起，目前超过150位研究人员进行研发，其目标是使Elsevier期刊成为发现与探索科学研究最可能的地方，让重新设计描述的文献更具有可读性、无缝导航性。此项目的深度研发遵循三个指导原则：一是可读性，即让新出版的文献知识更容易在屏幕中得到有效揭示；二是可发现性，即实现引导式、工作流式的内容与功能发现；三是可扩展性，即在不牺牲可读性的基础上，具有一个通用的功能层来揭示丰富的特殊主题内容。这一项目的发展模式目前已经初具雏形，在未来的语义化出版中值得借鉴与期待。

# 3.10 LSC 描述框架

$\mathrm { L S C } ^ { [ 1 8 ] [ 1 9 ] }$ 作为一种轻量级词汇，由德国明斯特大学地理信息学院构建，其底层框架技术主要依赖W3C的资源描述框架规范，同时借鉴了牛津大学赵军编辑的开放源模型词汇表（OpenProvenanceModel Vocabulary)[20]描述规范。LSC 词汇为出版商和科研人员提供与时间、空间、主题相关的科学事件的术语词汇，能够结构化描述科学资源，最终达到以机器可以理解的方式来关联发现科学资源。此种以科学知识关联为目的的描述框架，也为科技文献中研究设计指纹之间的关联关系提供了很好的借鉴。

# 4研究设计指纹描述框架的设计

综上发现，各个规范描述框架都具有自身的研究环境与特殊目标，比如对理化领域知识的描述、对科学实验本体的创建、对开放科学资源的关联以及对未来语义出版的支持等。但是，面向海量科技文献的深度知识分析，使科技文献可自动计算执行、自动阅读理解以及自动创建知识之间的关联等语义特征，仍然是需要深入研究的问题。本研究提出的研究设计指纹描述框架，即是一种描述科技文献知识单元的标准规范，利用研究设计指纹将科技文献知识单元以一种结构化、语义化与关联化的标准进行组织，使科技文献转换成机器可计算与理解的智能文献。

研究设计指纹描述框架的设计思路本质依赖于科学研究方法，对于科技文献撰写者来说，它是规范与体现科研过程的一个流程框架，如下图5所示；而对于阅读科技文献的用户来说，它是帮助用户了解科研成果的导航工具。下面从分类体系、构建规则与框架结构三个方面对此框架进行介绍，并将在后续研究中对其应用效果进行验证与分析。

# 4.1分类体系

科技文献蕴藏着丰富的知识单元类型，为了更清晰合理地识别与组织各种研究设计指纹，参照文献修辞篇章结构，将研究设计指纹分为四种类型，如下图6所示：一是基础指纹，主要描述科学研究的知识基础，包括研究假设、研究背景和研究目标；二是技术指纹，主要描述实施解决研究问题的技术方案，包括研究方法、研究数据、研究算法、研究模型与研究设备；三是结论指纹，主要描述研究的成果或者效果，包括研究结果与研究结论；四是未来指纹，主要描述研究未来的研究方向或者重点。

![](images/afe5a2895a4cd18a78392e61dc1b5001558d34ca38d0bb9fa012d9060f1024a4.jpg)  
图5研究设计指纹描述流程图

![](images/68420f9d80cbe56c5259aff9ab146f7c9d23876242d665199244a793f83e033f.jpg)  
图6研究设计指纹分类体系图

# 4.2构建准则

(1)将科技文献表示为计算机可以自动计算执行与阅读理解的智能载体；

(2)勾画出一篇科技文献或者一个研究主题的研究设计指纹的知识骨干网络图，帮助科研人员快速了解文献的中心主题或者核心研究思路与内容；(3)关联发现科技文献的研究设计指纹之间的证据链，通过关键主题或者知识对象来支持相关的研究设计指纹，表明它的唯一性或者效率性能等；(4)支持实现技术创新，通过发现较好的研究方法、研究设备、研究模型等研究设计指纹以及组合、扩展等模式，实现科学研究设计的再创造，更好地解决研究问题。

# 4.3框架结构

研究设计指纹框架结构是将研究设计指纹按照一种标准规范进行结构化组织，支持科技文献的机器计算执行性、语义计算与知识标引等知识组织相

# JL

关的研究活动。下面从指纹类型与整体框架、指纹类设计和指纹的划分粒度三个视角进行研究与实现，具体如下：

# 4.3.1指纹类型与整体框架

研究设计指纹框架体系结构以研究设计指纹来表示科技文献研究成果，总体结构分为两个层次，第一个层次分为研究主题、研究方法、研究算法、研究结果、研究结论与未来研究六大部分，而第二个层次详细描述科技文献，主要分为研究假说、研究场景、研究目的、研究背景、研究方法、研究数据、研究算法、研究结果、研究结论、未来研究以及研究设备共11种设计指纹，两个层次之间相互关联、层次内部相互关联，很好地支持科技资源之间的关联计算与发行，具体框架描述如下图7。

cresults> 科技文献研究设计XML描述 cresult> <preferLabel/> <goodLevel/> -<causes> -<cause> <preferLabel/>   
<ml version=\*1.0”encoding=\*UTF-87> esearch> </cause>   
<ResearchDesigns> <preferLabel/> </causes>   
CResearchDesign> reD> <artideeiD/> <methods> </research> </articles>   
+<algorithms> +cesults> -<methods> <method> </results> </result>   
<discussions> cpreferLabel/> <discussions>   
<conclusions> ResearchDesign: cisNew/ <effectLevel/> <discussion> <goodLabel/> cbadababt/   
+<cenario> </articles> <articleID/>   
+<background> <method> </articles>   
+<method> </methods> <discussion>   
<data> <algorithms> <discussions>   
+<algorithm> -<algorithm> <conclusions>   
cesult> <preferLabel/> -<conclusion>   
+ccontnbution> cefficiency/> <preferLabel/>   
+<conclusion> cresultlevel/> -carticles>   
:tobpes <rarockto> </articeD/>   
</ResearchDesigns> </algorithm> </conclusion> </algorithms> </conclusions>

# 4.3.2 指纹类设计

从科技文献的知识结构性、可计算执行性设计，利用实体类与类属性两个角度来描述，如下表1所示，同时参考W3C发布的ORB即语义化组织的方式，将上述内容进行有机关联，一方面提升科技文献所包含研究设计元素的可分析评估性与可计算性，另一方面增强它们之间的知识关联性，同时也提高计算机处理效率。

表1研究设计指纹描述框架类与属性描述表  

<html><body><table><tr><td>类型</td><td>数值</td></tr><tr><td>实体类</td><td>假说，目标，背景，方法，数据，算法，模型，设备，结果， 贡献，结论，未来研究，实体对象</td></tr><tr><td>属性</td><td>殊条件，方法，新颖性，效果</td></tr></table></body></html>

# 4.3.3指纹的划分粒度

研究设计指纹的粒度方面，粗细结合，从科技文

献的物理修辞结构角度出发，分为四个层次，具体设计如下表2与下图8所示：

表2研究设计指纹描述框架设计粒度描述表  

<html><body><table><tr><td>类型</td><td>描述</td></tr><tr><td>第1层</td><td>科技文献主体修辞结构，即IMRD经典模式，同时参照 此模式扩展</td></tr><tr><td>第2层</td><td>科技文献论证区域，实现研究设计指纹跨多个主体修辞 结构</td></tr><tr><td>第3层</td><td>科技文献句子，实现识别与发现研究设计指纹的证据</td></tr><tr><td>第4层</td><td>科技文献核心知识事件，实现从微观层面上描述作者要 表达的知识内容，揭示作者对本领域或者研究方向所做 出的贡献</td></tr></table></body></html>

![](images/17c569a5ae6a21a4d580aab10f08f9f41c10574f34ad45358caa8a56133fc8f1.jpg)  
图7科技文献研究设计核心知识体系描述框架  
图8基于科技文献的研究设计指纹分析层次示意图

# 5应用研究探析

以上介绍了基于科技文献的研究设计指纹描述框架，但在科研成果数字化文本数量激增的信息环境下，如何应用此框架帮助科研人员快速发现科技文献中的重要知识以及相互之间的脉络关系？此框架能否对未来科技文献的出版提供标准规范的帮助？能否为科研人员提供一个写作思路上的标准语义框架以最终实现与语义出版的无缝集成？下面主要从挖掘科技文献中心主题、绘制科技文献知识骨干网络图和支持语义出版三个视角对“研究设计指纹描述框架"的应用优势进行分析与论证。

# 5.1挖掘科技文献中心主题

如何快速准确地识别出科技文献的中心主题、一般主题以及分析出主题间的结构关系，历来是文本挖掘中的重要研究课题。随着语言分析、信息抽取和社会网络分析等方法的发展，一些新的解决思路和方法正在涌现。而通过科技文献研究设计指纹描述规范框架，不仅可以将文献主题从指纹特征的粒度进行结构化组织，而且也揭示了相互之间的关系，进而快速创建科技文献的主题结构网络图，辅助科研人员快速了解所关注文献论述的中心主题。

# 5.2绘制科技文献知识骨干网络图

研究设计指纹描述框架从“研究设计”的视角组织与揭示一篇科技文献，即识别它的具体研究内容以及研究背景、方法、算法、工具、数据集、结果以及结论等研究设计指纹（如图5所示），形成科技文献的知识骨干网络图，从而帮助科研人员迅速掌握该领域最新或者最有效的研究方法、工具等。

# 5.3支持语义出版

语义出版 2009 年被首次提出，肖顿等[21]将其概念界定为：提升期刊文章的语义，以促进其自动获取为目的，通过构建语义相关的文章之间的链接，提供多种获取文章内数据的可行途径，也使文章之间的数据整合更容易实现。而肖顿又提出语义出版能够极大地提高科学交流效率，其提供的增值服务能获得合理的商业回报，在学术出版领域将得以推广实施[22]。徐昊[23]提到随着语义出版研究的推进，目前科学出版领域关注的重点在于改善知识对象在产生、传播、演进、发布和重用这一生命周期中的语义。在上述语义出版发生与发展的背景下，研究设计指纹描述框架将科技文献进行语义化、结构化组织，将以一种新的模式支持科技文献内核心知识内容的识别、提取与计算，科技文献之间知识关联、整合以及研究成果的传播，使科技文献成为计算机可以自动计算、自动阅读的智能产品。

# 6小结

随着现代信息技术的快速发展，科技文献的数字化规模势必继续扩大，从海量科技文献中了解某一研究问题的最新研究方法、最有效的研究设备与模型等，成为科研人员面临的巨大挑战。因此，设计一套规范化的科技文献描述框架指南，不但能够对已出版的科技文献进行知识的再创造，而且能对科技文献写作进行知识的研究设计组织与关联化组织，辅助科研人员快速了解研究进展，掌握研究方法，洞察研究动向。本课题将在下一阶段研究中，对研究设计指纹描述框架进行实验设计，进一步验证该框架对于科技文献知识挖掘与分析的作用。

# 参考文献

1Kauppinena M，Espindola G M D. Linked Open Science—Com

for Executable Papers.Procedia Computer Science，20l1(4):726 -731   
2张晓林．颠覆数字图书馆的大趋势．中国图书馆学报，2011,37 (5):4-5   
3Liakata M，Soldatova L. An Ontology Methodology and CISP. JISC，2007:2-5   
4Saiedian H. Guidelines and Requirements for Writing a Research Paper.[2014-01-26].http://people.eecs.ku.edu/ $\sim$ saiedian/ Teaching/Common/term-paper-guidelines. pdf   
5Baldassarre G A. Guidelines for Writing and Publishing Scientific Papers?.[2013-06-26]. http://www.aou.org/student/docs/ baldassarre. pdf   
6Guidelines for Writing Scientific Papers. $[ 2 0 1 3 - 0 6 - 2 6 ]$ .http://www. bms. bc. ca/resources/library/pdf/GuidelinesScientificPapers.pdf   
7Swales J M. Genre analysis: English in Academic And Research Settings. Cambridge：Cambridge University Press，1990：134 -137   
8Carmen Soler Monreal，Luz Gil Salom ，Maria Carbonell Olivares.A Study of Section Headings in Computing ,Robotics and Telecommunications Research Articles.ReceL，2006(5):1-26   
9International Committee of Medical Journal Editors（2013.12. 25).ICMJE：Uniform Requirements for Manuscripts Submitted to Biomedical Journals：Writing and Editing for Biomedical Publications. $[ 2 0 1 4 - 0 1 - 2 5 ]$ .http://www.icmje. Org   
10Harmszl P,Van C,Kircz G. A Modular Structure for Electronic Scientific Articles. $[ 2 0 1 3 - 1 0 - 2 2 ]$ .http://www.science. uva.nl/projects/commphys/papers/infwet/infwet. html   
11Waard D,Gerard T. The ABCDE format - Enabling Semantic Conference Proceedings. SemWiki,? 2006，volume 206of CEUR Workshop Proceedings   
12Semantic Authoring Source . $[ 2 0 1 4 - 0 1 - 2 6 ]$ .http://salt. semanticauthoring.org/documentation. html.   
13W3C Interest Group. Ontology of Rhetorical Blocks(ORB). [2013—09-26].http://www.w3.org/TR/hcls-orb/   
14同3   
15Nanopub.org. What Is a Nanopublication. $[ 2 0 1 3 - 0 7 - 2 7 ]$ ： http://nanopub.org/wordpress/? page_id $= 6 5$   
16Robert B Allen. Model-Oriented Scientific Research Report. [2013－07－26]. http://www.dlib.org/dlib/may11/allen/ 05allen. html   
17Schemm Y.Experience the Article of the Future $[ 2 0 1 3 - 0 7 -$ 26]. http:/ /www. Elsevier.com/reviewers/reviewers-update/archive/issue-4/experience-the-article-of-the-future   
18Bartoschek T，Kray C. Gestural Interaction with Spatiotemporal Linked Open Data. OSGEO Journal,2013,13(9):60－67   
19Baglatzi A，Kauppinen T，Kebler T. Linked Science Core Vocabulary Specification.[2013-O5—26]. http://linkedscience.

# JL

org/lsc/ns/

20 Zhao J.Open Provenance Model Vocabulary Specification . [2014—10-26].http://open-biomed.sourceforge.net/opmv/ ns. html   
21 Shotton D,PortwinK，GrahamK，etal.Adventures in Semantic Publishing：Exemplar Semantic Enhancements of AResearch Article．PLoS Computational Biology,2009,5(4):1-17   
22 Shotton D. Semantic Publishing：The Coming Revolution in Scientific Journal Publishing.Learned Publishing,2oo9(22）：85-

94. 23Xu H. Managing Ubiquitous Scientific Knowledge on Semantic Web.In:AST/UCMA/ISA/CAN.LNCS 6059,2010:421- 430

作者单位：中国科学院文献情报中心，北京，100190中国科学院大学，北京，100049收稿日期：2014年9月14日

# Research Design Fingerprint Description Framework Based on Scientific Papers

Qian Li Zhang Xiaolin Wang Qian

Abstract:The paper proposes the concept of Research Design Fingerprint which can be used to describe the core knowledge of the scientific literature，and then analyzes relevant scientific literature description frameworks comprehensively，creates a Research Design Fingerprint Description Framework based on scientific literature，aiming to enhance the enforceability of scientific literature computing machines，knowledge granularity，knowledge relevance，structure scalability and visibility of research design ideas，then provides for researchers with new ideas and models to help them find design methods and research design tools quickly.

Keywords: Scientific Literature； Research Design Fingerprint； Knowledge Organization； SemanticPublishing；Knowledge Backbone

# (接第13页）

17肖珑，张洪元，钟建法，武桂云，李浩凌，李峰．建国后高校文科外文文献的发展状况与未来保障研究．大学图书馆学报，2013(2)：5-13  
18Suseela V J.Application of Usage Statistics for Assessing theUse of E-journals in University of Hyderabad：a Case Study.

The Electronic Library，2011，29(6):751—761作者单位：北京大学图书馆，北京，100871收稿日期：2014年9月10日

# The Development Trend， Price & Cost Strategy of Foreign Database Importation

Xiao Long Zhang Lin

Abstract:Based on the development trend of foreign database importation and price theory，taking some databases acquired by Digital Resource Acquisition Alliance of Chinese Academic Libraries (DRAA） for instance，this paper analyzes price and cost model of foreign database，gives the actual coping strategies as references for the construction of digital resources of academic libraries.

KeyWords:Imported Database；Price；Cost； Consortium Acquisition；Digital Resource Construction