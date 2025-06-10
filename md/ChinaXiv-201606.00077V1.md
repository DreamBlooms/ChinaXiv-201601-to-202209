# 个性化交互设计的研究综述

# 顾立平

（国立台湾大学图书资讯系台北100671)

【摘要】实践“用户驱动服务”的信息服务系统,包括三个部分：用户模型、信息技术和服务设计。通过梳理个性化交互设计,探讨以人物角色和生活实验室来实现用户驱动个性化数字图书馆系统的设计。

【关键词】交互性交互界面 互操作用户需求用户功能用户配置文件

【分类号】G250.76

# Review of Personalized Interaction Design

Ku Liping

(Department of Library and Information Science，National Taiwan University，Taipei 1Oo671,China)

Abstract】The information service system that practice the user driven services has three parts：user model,information echnologies and servicedesign.The articlereviews literatures of personalized interaction design，then discusses using lersonas and living laboratory to archive the design of user driven personalized digital library system.

Keywords】 Interactivity Interface Interoperability User need User performance User profile

# 前言

个性化交互设计建立在用户心理与行为的理解基础之上,是一种让用户更方便、更有效、更愿意接受信息服的技术。换言之，使服务更准确地符合用户需要的性能。

P//711:707710:7/11511)

个性化交互设计具有两个相互影响的组成部分：使用性能和计算性能。交互设计向来以多学科整合的结果来描述使用性能,例如Waler(2009)整合信息系统、人机交互、生态心理学和社会学,建立一个支持日常生活与工作场所活动的信息系统设计。另一方面,交互设计也考虑从计算性能去考量设计规模、互动方式和资源配置，有研究指出：系统响应时间(例如网络延迟或者后台进程延误)的拖延,会恶化使用性能,对工作效率、工作满意度、健康和安全等产生负面影响[2]。可以说,使用性能和计算性能不仅相互制约,而且共同制约个性化交互设计。

随着技术和社会脉络的变迁，人机交互研究近20年有两个现象：相关知识的增长，以及逐渐关注人类而非计算机的角色[3]。这些现象导致了三方面的研究转型：从多数人可接受的功能取向,转变为关注少数人的最佳经验(Peak Experience）;从实现需求的实践性,转变为系统种类和内容的多样性;以及从规格化的统整性,转变为潜在的零散性（Potential Fragmentation）[3]。上述问题其实反映出一个共通难题,即:如何更好地满足用户心理与行为;以及一个潜在(或许是更为深刻)的问题,即:如何理解用户行为与特征,并运用在信息服务系统的设计中。

本文从交互性（Interactivity）、交互界面（Interface）、互操作性（Interoperability）、用户需求（User Need）和用户功能（User Performance）,系统地梳理个性化交互设计的进展,探讨个性化数字图书馆系统设计，并对上述问题提出雏议（Proposal）。

# 10 现代图书情报技术

# 2个性化交互设计

# 2.1 交互性

交互性是交互设计的核心，但并非全部。交互性体现在人们与信息系统的对话过程，交互性研究着重在研究过程而非人类感知或系统架构。例如，O'Brien等(2010)通过两次大样本研究，分析网络购物环境的用户参与度（UserEngagement）；从可靠性分析与探索性因素分析，判断6类评量要素：知觉可用性、美感、吸引力、参与感、新颖性和耐久性;继而从结构方程模型，建立用户与系统的交互模型[4]。目前,这些研究已经逐渐独立于信息系统领域，而跨越用户建模和信息技术，成为新型研究。

个性化交互设计中的交互性，更着重从大众行为统计来判断单一用户行为，而非致力于一个通用模型架构。例如Lin等(2009)提出一个利用模糊逻辑聚类技术的模型，计算眼球运动中的注意力分配，尝试区别用户是否处于任务工作中[5]。此外,个性化交互设计更着重在平衡使用性能和计算性能的差距。

(1)从使用性能来说，在现实生活中复杂系统设计需要先进的软件工程模型、方法和工具，以满足诸如可靠性、稳定性、安全性或韧性的能力。Navarr等(2009)介绍了一个用户界面描述语言（ICOs)的用例，支持原型阶段（应用程序模型和互动来极大地满足用户需求），以及运作阶段（在有限资源中的系统部署）中的交互系统和架构描述[6。通过用例,可以将使用性能极大化，再考虑计算性能，删除不必要的使用性能后，获得两者的平衡。

(2)从计算性能来说，公共服务系统必需满足三个基本条件，即容忍人为错误、保持计算无错，以及适应大量人潮等；以台湾高铁的交互设计为例，Sandnes等（2010)以高速铁路售票机的用户体验评估来帮助设计者避免常见的人机交互设计错误[7]。通过评估方法，可以将使用性能极小化，再考虑计算性能，将失误率建立在最小发生概率，以获得两者平衡。

目前，个性化交互设计也朝向智能化发展。智能互动系统的分析设计（Intelligent System for InteractionsAnalysisinDesign)是基于互动特性的协同和分布式设计过程;以时间为基准的代理器相互作用，允许研究人员开发更丰富的设计模式，例如：自组织、自适应、动态和自我相似性等微观群体的相互作用[8]。可见,未来个性化交互设计中的交互性研究，将与用户建模和信息技术更紧密结合。

# 2.2 交互界面

交互界面是最直接体现交互性的“物件”。目前个性化用户交互图形（GUI)的研究认为：通过删选视觉要素，如：清单和工具栏等，能减少视觉复杂性和改善交互效果[9]。交互界面虽然以视觉美感为主要研究取向，但是近年也逐渐朝向用户心理与行为的方向发展，比如：作为虚拟实境的交互界面。

人们对于使用交互界面来模拟产品以进行交互设计有不同的观点：VanRijnsoever等（2010)认为在网页上采取用户产品交互（User－ProducerInteraction,UPI)是冒险的（ARiskyProcess），因为很难定义目标用户和他们的实际需求[10]。另一方面,Park 等（2009)则认为让用户对产品原型进行有形互动和功能行为模拟，可以获取系统原型所需要的设计评价和用户反馈[1];而 Bruno 等(2010)通过比较用户和产品的实际交互（User-RealProduct）和虚拟交互（User-VirtualProduct）,重新设计家电产品的用户界面[12]。这些正反意见来自不同对象、方法和结果，关键在于：交互界面作为交互设计的一个结果、过程，或是开端的适用性。此外，从使用性能和计算性能的角度来看，若要改进性能，势必要开拓更多新的研究方向，而这些取向又更多地与用户心理与行为相关。

(1)从使用性能来说，手持型用户界面（HandheldMotion-basedUIs)的新方向是：以手势识别和视导滚动作为主要的互动方式；最佳化用户性能是指随系统参数、规模和目标而改变;让没有学习过操作方式的用户能够很快上手[13]。个性化界面过多的可选性会分散用户注意力，但过少的可选性会降低用户实现任务的能力，个性化交互设计的交互界面，其当务之急是关于性能结合的量化指标。

(2)从计算性能来说，面向非传统控制性能的用户界面设计更具有挑战性。人脑和计算机系统的神经活动实时解码的能力，使人们可以直接用思想控制计算机应用程序，这是一种与多数传统互动装置完全不同的信号特性。这种实验可以被用来考虑不确定性和控制动态输入[14]。交互设计作为交互界面的一个重要部分，若要实现以复杂网络为基础的人机界面设计，需要对网络服务的规范和监管、服务导向的架构、支持多样设备的网络服务等进行整体设计[15]。在复杂的工业组织中的移动性、合作性和信息获取，是人机界面的最新课题。

目前，交互界面从视觉美术，逐渐朝向视觉心理学发展。例如Tuch等(2009)从认知与情感的心理生理研究和美学理论，发展出一套研究视觉复杂性（VisualComplexity)的实验框架；实验说明：视觉复杂度增加，将消耗更多精神、降低心跳、增加面部肌肉张力，而网站的视觉复杂性影响着用户的认知和情感，包括：高兴和兴奋的经验、面部表情、自主神经系统的激活、任务绩效和记忆等[16]。由此可知,用户界面的可用性是一个工业产品的关键环节，个性化交互设计中的用户界面则更偏向用户行为与特征所推导的交互设计。

# 2.3 互操作

互操作是指分布式系统通过数据交换而达成任务目标的一种能力。个性化交互设计中的互操作细节是一个庞大课题。本文集中探讨使用性能、计算性能和交互设计的问题。

就信息服务系统或数字图书馆而言，目前存在各种不同设备的平台和控制方法，如果想对一个指定设备做具有远程控制能力的功能，必须写人该设备的许多复杂的程序或方案。即使只是添加或修改一个新的功能，人们也必须反复研究最初的源方案和运作程序，花费建设成本、耗费时间，而且效率低下。如果可以区分使用性能、计算性能和交互设计，则实现互操作的思路就会大不相同。

(1)从使用性能来说，最优化资源配置的设计是在一个完整框架下实现最小功能的设计，反过来，如果新增或修改的部分功能是原先已被考虑而未实现的内容，则新增或局部修正并不会影响整体框架、程序或方案。例如Brinkman等（2009）提出一个对WebTV、MP3、手机、温控器等9个易于使用的个人互动组件的可用性测试（Usability Measure）理论框架[17]。又如Jiang 等（2010）以代理进化算法（AgentEvolution Algorithm，AEA)作为门户网站服务商（PortalAccessServ-iceProvider，PASP）、产品服务提供商（Product ServiceProvider，PSP）,以及移动服务供应商（MobileServiceProvider，MSP)的多元代理系统的整合框架[18]。可以说，从实际用户行为推导系统框架会比从技术实现难

# 12 现代图书情报技术

易来推导系统框架更具有完整性，从而在实践过程中更具有弹性（Flexibility）。

(2)从计算性能来说，占用愈多资源的系统往往是功能越复杂的系统，反过来，如果确定使用性能极小化，则可以节省计算性能。例如，Chen 等（2010)构建一个远程控制接口，由设计人员指定在桌上型计算机的Java应用系统中的控制按钮和标签控制对象，产生进人手机远程控制接口的自动对象[19]。未来,这项技术可以让人们只使用手机或PDA就能远程控制在个人电脑或数字电视上的多媒体。换言之，从用户特征与行为的角度来看，人们不需要重新设计，而是将新增的功能独立于原有系统，再在原有基础上加入接口进行新功能的设计。

目前，个性化交互设计中的互操作朝向通用软件体系的方向发展。一方面，模拟不同行业的结构系统的功能，例如Uygun等（2009)提出分布式制造系统的模拟、高级模拟架构（HLA）及其对象模型模板（OMT)，包括：对象的类结构、交互类结构、属性、参数和数据类型表等[20]。另一方面,让不同的系统互通和交流信息，以更好地支持交互界面和用户需求。

# 2.4 用户需求

用户需求是指当计算机使用者（ComputerEnd-user)使用系统功能、与信息系统进行交互，并且使用信息时，其所处的环境（State）、所执行的任务（Task）、所操纵的步骤（Step），也就是计算机使用者行为，因此用户需求是一个信息技术开发的基础

然而，每一个互动系统是由一组核心功能和用户界面所组成，但是软件工程(SE)和人机交互(HCI)往往没有相同的方法、模型或工具。Godet－Bar 等(2010)对此提出一个整合方案，从规格到设计的应用案例进行质化研究,以提供一个更好的用户功能[21]。这样，用户需求被考虑到软件工程中，而个性化交互设计能够通过满足用户期望，以预防错误并且提高互动效率。当前，个性化交互设计中的用户需求研究，为了规避使用性能和计算性能的双向制约，正朝向区分用户群组和改变交互设计流程两个方向发展。

(1)区分不同的用户特征与行为。例如Roth等(2010)调查发现互联网用户对不同的网页类型（网上商店、新闻门户网站、公司网页)有不同的心智模型；用户普遍认同相对较多但不包括所有网址的导航和主页[22]。从特殊族群来看,通过自我陈述的调查报告、用户点击次数和视觉跟踪(Eye Tracking)研究,Djamasbi等(2010)发现Y世代感兴趣的网页，集中在大量图像、少量文字和具有搜索功能的页面上[23]；而 Spink 等(2010)调查发现学前幼儿能在复杂的网络中通过Google搜索视频和音频，包括关键字搜索和浏览、查询和重新定义、判断相关物、连续搜索、分散和协作等行为[24]。这些研究显示了更为细致和精确的用户行为模型及其交互设计要求。

(2)随用户兴趣迁移而改动交互方式。信息系统开发的传统方法是自上而下设计，经过精心策划的编程，未考虑不断发展的用户需求。先进的软件工程和人机交互则着重主事者的即兴（Improvisation)需求，以满足开发者临时转变想法(服务策略)的情况，而非不断增加新的系统功能[25]。由于用户提出批评和反馈,能让系统改善用户偏好设定和预测用户真正想要什么[26],所以若要推荐近似用户感兴趣的产品,则更依赖对用户特征与行为的理解，以及适应主管和用户的各种不同需要。更重要的是，这使得设计者考虑动态的(变化中的)而不是静态的用户行为。

目前，个性化交互设计中的用户需求研究，持续朝向“洞察(Insight)客户的真实感受”发展。一项有趣的研究指出：有时强调给用户最好的选择，不见得是理想的系统设计。VanVugt等（2009）在实验室和网络上进行电子健康顾问的研究，分为“告诉用户达成理想体重的建议”和“告诉用户减重的建议（实际上并不理想）”，研究发现用户更信赖非理想的电子健康顾问[27]。如果从机械理性主义来看人类时不时的非理性和懒惰，这项研究结论看似荒谬，但是如果从用户心理与行为的服务角度，它却表明如何能让人们主动地加入健康计划而不是排斥它。此外，Bedny 等(2010)基于系统结构行为理论（Systemic－ structural ActivityTheory）进行形态分析（MorphologicalAnalysisofActivi-ty），提出认知与行为活动和人类用户作为主要分析单元的模型[28]。这类研究反映了一定程度上的“用户驱动个性化数字图书馆系统”原始模型，即：更贴近于真实世界人类心理与行为模式的虚拟世界用户模型。

# 2.5 用户功能

用户功能是指当计算机内部运行众多程序和指令时，代表用户所进行系统执行命令的那个信息或符号，因此用户功能是一个信息技术开发的依据。目前，个性化交互设计主要面临在环境智能（AmbientIntelli-gence，AmI)里考虑“如何在动态脉络中实现技术以满足不同人的需要”的用户功能细节。这个目标可以从不同层面理解：

(1)技术问题，如：互动装置、各种用户使用的技术、连续交互、隐式交互设计等;(2)工程问题，如：适合非常复杂的互动环境的互动机制和设计方法；(3)非功能的特征，例如：可访问性、隐私、保密和安全（Accessibility，Privacy，Security，andSafety）等[29]。

如果在交互性、交互界面、互操作、用户需求都十分清楚的情况下，用户功能体现了最大化计算性能和使用性能的作用，即：简化实践步骤，以及细化实践内容。针对前者，作为一个软件开发自然和可执行的设计和发展理论，理念导向设计（COD)有助于设计师和开发人员陈述自己的思想而非描述机械功能[30]；针对后者，UCL核心概念的构想，如领域、任务、结构和行为等，能系统地研究不同种类的服务，并提供更丰富的描述，特别是用户为中心的观念和技巧，以及适用于了解服务性质的概念和框架[31]。简言之,实践用户功能并不是难题，人们甚至发展了上述工具来简化流程、缩短时间和顿节成本；难点是决定用户功能的过程如何协助设计者对交互性、交互界面、互操作、用户需求的厘清。

（知识/信息/讯息）生产率在很大程度上因用户的个人特点而定，这意味着它会随用户而异；然而，因为很难识别每个用户，所以有些用户被最后的设计方案排除，而这些被排除的方案或许可从决定用户功能的过程中恢复。例如，Recabarren等（2010）设定窗体（Webform）自动适应个人用户，首先确定个人的文化特征指数和窗体之间的关系，然后验证这些规则(Rules)是否作为一个窗体可调整的项目，以减少开发时间[32]。总之,过快进入用户功能的规划阶段,往往不是最佳的个性化交互设计，用户功能不仅是准确地实践设计蓝图，更重要的是检查、弥补和完善交互设计。

# 3个性化数字图书馆的交互设计

个性化数字图书馆的交互设计需要关注用户行为，例如，在新的搜索环境中，新手往往需要数字图书馆协助他们执行：信息搜寻开始、确定相关的数字馆藏、信息浏览、组织搜索语句，精炼搜索、检查搜索和评估结果等信息行为[33]。为了更好地支援用户信息行为，目前可见的网络用户服务模式下的个性化交互界面,有三种可资借鉴的取向：

(1)用户的社交行为可以作为个性化数字图书馆的交互设计之一。目前，用户可以通过社会网络工具，进行正式和非正式的沟通，以及在Web2.0上互动、有组织的协作和知识交流,实现个人知识管理（PKM）[34]。同时，社会媒体和社会标签已越来越成为一种信息搜寻行为的模式。Shiri（2009）比较了6个社会书签和4个社会媒体的标签系统的交互界面特性和功能（在网页上发送、探索、浏览和使用标签等），讨论其用户标记功能、探索搜寻功能、标签浏览功能和界面布局等[35]在数字图书馆服务用户进行非正式信息交流行为的过程中，为个别用户进行个性化社会网络的知识传递功能，既是一种新形态的个性化知识管理服务，也是一种新式样的个性化交互设计。

(2)用户的娱乐行为可以作为个性化数字图书馆的交互设计之一。如同社交行为，在角色扮演游戏（RolePlayingGames，RPGs）中，自主行为者（Autono-mousCharacters)往往与用户在同一个群组中，发展他们的社会交往能力有可能推动用户在虚拟环境中的社会参与，提高他们的互动经验。这样，就需要对团体（他们与用户)的组成、范围和结构进行行为模型的探索[36]。因为数字图书馆不仅能够利用这种方式建立参与者、指导者和跟随者，也能将交互设计转向互动设计，扩大个性化交互设计的范围与功能。

(3)用户的情绪变化可以作为个性化数字图书馆的交互设计之一。Beale等(2009)对情绪仿真代理器（Emotional SimulationinAgents）进行综述,梳理了目前利用代理技术与情感能力影响用户态度、感知和行为的各种人机交互研究[37]。传统的数字图书馆交互设计绝少考虑用户的情绪反应，然而，从认知心理学的角度来看，情绪往往是学习的动力，而信息结构只是辅助讯息进入人脑中建立知识结构的一种工具，并不是思考活动的主体和动能;在进入和输出的控制过程中，情绪是主要的动能，对有意义的讯息（Meaningful Mes-sage)起到开关控制的作用。换言之，如果人类情感影

# 14 现代图书情报技术

响用户的信息行为，那么数字图书馆应当发展具有情感能力的交互设计。

综上所述，用户在不同的搜寻环境中，依然有许多值得探索的心理、行为、特征、目的、任务和需求。个性化数字图书馆的交互设计，正朝向越来越多变的技术应用、技术开发，甚至是技术探索发展。

以技术探索而言，若要实现用户驱动个性化数字图书馆系统的设计，需要不断探索个性化交互设计的技术，这个过程可以综合两种研究方法论（Methodology）：

(1)创建与使用型人。例如Loke等(2009)运用传统以用户为中心的型人（Personas）和情境（Scenarios）方法，对一个多用户、交互、身临其境的艺术品视频,进行动作感应技术的开发设计，构建了一套直观的多元用户空间和社会互动模型[38]。作为软件工程的一种优化系统设计的方式，型人不仅提供更为详细的用户行为与特征描述,也提供一种结合工业设计、技术应用、市场行销和开发工程的事前模拟与事后修正的可操作模型。

（2）建立生活实验室（LivingLaboratory）。例如Jeng(2009）提出一个整合泛在智能空间（UbiquitousSmart Spaces)的设计框架，以支持物理空间下的计算基盘（ComputingInfrastructure）和互动性能的映射，方便研究团队在生活实验室测试智能生活（SmartLiv-ing）[39]。作为根据人类感知开发新型产品的生活实验室，则可为数字图书馆提供一种全新的用户行为与信息服务的实验环境。过去，研究者以社会调查等观察法进行用户行为推理，继而推论信息服务的方式，间接结合用户行为与数字图书馆服务；如今，通过生活实验室，则可以从实验法直接验证用户行为与数字图书馆服务的关系，更紧密地完善用户驱动个性化数字图书馆系统的设计。

型人（Personas)提供一种交互设计的可操作模型，而生活实验室则可以验证这个模型对于数字图书馆服务用户行为的直接效果，从而优化计算性能和使用性能，使得技术应用、技术开发以及技术探索更有效率。

# 4结语

在个性化数字图书馆中，系统设计不是以实现所有新颖技术为主要目的，而是以不限制系统功能为目的。设立用户配置文件（UserProfile)时，可以将用户行为的活动范围极大化，而将技术条件的实现能力极小化，在此“极大”和“极小”之间，取得一定平衡，这个平衡过程，或者说是用户配置文件的完善化，是一种随着技术和社会脉络变化而进行系统设计优化的途径。

优化（Optimization）有三种含义：使之更有效率（更快）、使之更多功能、使之平衡资源与使用（供给与需求）。本文从使用性能和计算性能的相互制约与共同制约交互设计的角度，探讨交互设计所需要考虑的交互性、互操作和交互界面、用户需求和用户功能等要素。综上所述，新型的、更为深入的、尚待进一步研究的个性化交互设计，具有5个发展趋势：智能化服务设计、视觉心理实验、通用软件体系、用户行为洞察，以及决定用户功能的过程对检查交互设计的作用等。

目前，用户已从在图书馆内检索（Retrivel）、搜寻（Seeking）、获取（Access）、使用（Usage）、借阅归还等多媒体使用行为（Multi-mediaBehavior），转向在图书馆以外的数字图书馆内进行搜索（Search）点击（Click）、下载上传等多任务信息行为（Multi-taskBehavior）；并朝向凭借可移动设备在图书馆和数字图书馆之间来回穿梭，进行广泛而多元的交流行为（MultipleCommuni-cationBehavior）。由此将带来三个主要研究方向：如何理解用户行为与特征；如何根据用户特征来支持和管理用户行为;如何进行信息服务系统的迁移、重构与开发。

本文建议结合创建与使用型人，以及生活实验室两种思路，致力发展个性化数字图书馆的互动功能（符合用户社交行为的人际网络支援能力）、知觉唤起功能（符合用户娱乐行为与心理的学习刺激-反应机制），以及情绪感知功能（符合用户情绪变化的辅助学习流程)等，以更多元化的方式激活数字图书馆的个性化交互设计。而这依赖永不放弃对用户行为的探索和对他们的关怀。

# 参考文献：

[1]Waller V.Information Systems‘in the Wild’：Supporting Activity intheWorld[J].Behaviour& Information Technology，2009,28 (6):577 -588.   
[2］Szameitat AJ,Rummel J,Szameltat DP，et al.Behavioral and Emotional Consequences of Brief Delays in Human- computer Interaction[J].International Journal of Human-computer Studies, 2009, 67(7) :561 -570.   
[3]Dix A.Human - computer Interaction：A Stable Discipline，A Nascent Science，and the Growth of the Long Tail[J]．Interacting with Computers，2010,22(1）:13-27.   
[4]O'Brien HL,Toms E G. The Development and Evaluation of a Survey to Measure User Engagement[J]. Journal of the American Society for Information Science and Technology，2010,61（1）:50 -59.   
[5]Lin Y，Zhang W J，Wu C,et al.A Fuzzy Logics Clustering Approach to Computing Human Attention Allocation Using Eyegaze Movement Cue[J]. International Journal of Human-computer Studies,2009,67(5）:455-463.   
[6]Navarre D,Palanque P,Ladry JF,et al.ICOs：A Model-based User Interface Description Technique Dedicated to Interactive Systems Addressing Usability，Reliability and Scalability[J]．ACM Transactions on Computer- human Interaction,2009,16(4）:1- 56.   
[7] Sandnes FE,Jian HL, Huang Y P,et al. User Interface Design forPublic Kiosks：An Evaluation of the Taiwan High Speed Rail Ticket Vending Machine[J].Journal of Information Science and Engineering,2010,26(1）:307-321.   
[8]Movahed-Khah R，Ostrosi E，Garro O.Analysis of Interaction Dynamics in Collaborative and Distributed Design Process [J]. Computers in Industry,2010,61(1) : -14.   
[9]Findlater L，McGrenere J.Beyond Performance：Feature Awareness in Personalized Interfaces[J]. International Journal of Human - computer Studies,2010,68(3）:121 -137.   
[10]Van RijnsoeverFJ,Faber J,Brinkman MLJ,et al.User -Producer Interaction in Web Site Development：Motives，Modes，and Misfits[J].Journal of the American Society for Information Science and Technology,2010,61(3）:495-504.   
[11]Park H,Moon H C,Lee JY. Tangible Augmented Prototyping of Digital Handheld Products[J]．Computers in Industry，2009，60 (2) :114 -125.   
[12]Bruno F, Muzzupappa M.Product Interface Design: A Participatory Approach Based on Virtual Reality[J]． International Journal of Human -computer Studies,2010,68(5）:254 -269.   
[13]Oakley I，Park J.Motion Marking Menus：An Eyes- free Approach to Motion Input for Handheld Devices[J]．International Journal of Human-computer Studies,2009,67(6）:515-532.   
[14]Williamson J,Murray-Smith R,Blankertz B,et al.Designing for Uncertain，Asymmetric Control：Interaction Design for Braincomputer Interfaces[J].International Journal of Human-computer Studies，2009,67(10）:827-841.   
[15]Idoughi D,Kerkar M,Kolski C.Towards New Web Services Based Supervisory Systems in Complex Industrial Organizations：Basic Principles and Case Study[J]．Computers in Industry,2010,61 (3) :235 -249.   
[16] Tuch AN,Bargas-Avila JA,Opwis K,et al.Visual Complexity of Websites:Effcts on Users’Experience,Physiology，Performance，and Memory[J]. International Journal of Human-computer Studies,2009,67(9):703 -715.   
[17] Brinkman WP,Haakma R,Bouwhuis DG.The Theoretical Foundation and Validity of a Component -based Usability Questionnaire [J].Behaviour & Information Technology，2009,28（2）:121- 137.   
[18］JiangGY,Hu B，Wang YT.Agent-based Simulation of Competitive and Collaborative Mechanisms for Mobile Service Chains [J]．Information Sciences,2010,180(2）:225 -240.   
[19] Chen D J,Peng S J,Ong C E.Generating Remote Control Interface Automatically into Cellular Phone for Controlling Applications Running on PC[J]．Journal of Information Scienceand Engineering,2010,26(2） :549-563.   
[20]Uygun O,Oztemel E,Kubat C.Scenario Based Distributed Manufacturing Simulation Using HLA Technologies[J]. Information Sciences，2009，179（10）:1533-1541.   
[21]Godet - Bar G，Rieu D,Dupuy - Chessa S.HCI and Business Practices in a Collaborative Method for Augmented Reality Systems [J].Information and Software Technology,2010,52(2）:492- 505.   
[22]Roth SP,Schmutz P,Pauwels SL,etal.Mental Models for Web Objects：Where do Users Expect to Find the Most Frequent Objects in Online Shops，News Portals，and Company Web Pages?［J]. Interacting with Computers,2010,22(2）:140 -152.   
[23]Djamasbi S,Siegel M,Tulis T.Generation Y，Web Design，and Eye Tracking[J].International Journal of Human-computer Studies,2010,68(5) :307 -323.   
[24] Spink A,Danby S，Mallan K,et al.Exploring Young Children’s Web Searching and Technoliteracy[J].Journal of Documentation, 2010,66(2):191-206.   
[25]Magni M,Provera B，Proserpio L. Individual Atitude Toward Improvisation in Information Systems Development[J]． Behaviour & Information Technology,2010,29(3）:245 -255.   
[26]Chen L,Pu P.Interaction Design Guidelines on Critiquing-based Recommender Systems[J]．User Modeling and User- adapted Interaction,2009,19(3）:167 -206.   
[27]Van Vugt HC,Konijn EA,Hoorn JF,et al.When Too Heavy is Just Fine：Creating Trustworthy E-health Advisors[J]. Interna583.   
[28]Bedny IS,KarwowskiW,Bedny G Z.A Method of Human Reliability Assessment Based on Systemic - Structural Activity Theory [J]． International Journal of Human - computer Interaction, 2010,26(4) :377 -402.   
[29] Stephanidis C.Designing for All in Ambient Intelligence Environments：The Interplay of User,Context，and Technology[J]. International Journal of Human-computer Interaction，2009,25（5）： 441 -454.   
[30]Wingrave C A,Laviola JJ,Bowman DA．A Natural,Tiered and Executable UIDL for3D User Interfaces Based on Concept - Oriented Design[J]．ACM Transactions on Computer-human Interaction,2009，16(4):1-36.   
[31]Wild PJ.Longing for Service：Bringing the UCL Conception Towards Services Research[J]. Interacting with Computers,2010, 22(1) :28 -42.   
[32]Recabarren M，Nussbaum M. Exploring the Feasibility of Web Form Adaptation to Users’Cultural Dimension Scores[J].User Modeling and User-adapted Interaction,2010,20(1）:87 -108.   
[33]Xie I,Cool C.Understanding Help Seeking Within the Context of Searching Digital Libraries[J].Journal of the American Society for Information Science and Technology，2009,60(3）:477-494.   
[34]RazmeritaL,Kirchner K,Sudzina F.Personal Knowledge Management The role of Web 2.O Tools for Managing Knowledge at Individual and Organisational Levels[J].Online Information Review, 2009,33(6):1021-1039.   
[35]Shiri A.An Examination of Social Tagging Interface Features and Functionalities-An Analytical Comparison[J].Online Information Review,2009,33(5）:901-919.   
[36]Prada R,Paiva A.Teaming up Humans with Autonomous Synthetic Characters[J]．Artificial Intelligence,2009,173（1）:80-103.   
[37]Beale R，Creed C.Affective Interaction：How Emotional Agents Affect Users[J].International Journal of Human-computer Studies,2009,67(9):755-776.   
[38]Loke L,Robertson T.Design Representations of Moving Bodies for Interactive,Motion- Sensing Spaces[J]. International Journal of Human-computer Studies,2009,67(4） :394-410.   
[39]Jeng T S. Toward a Ubiquitous Smart Space Design Framework [J]．Journal of Information Science and Engineering，2009，25 (3) :675 -686. （作者F -mail .kulining@ ntu.edu. tw）