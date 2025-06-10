# 用户行为模型驱动信息系统设计的研究

# 顾立平

（国立台湾大学图书资讯系台北市10617)

【摘要】在全面了解用户主导、用户驱动、以用户为中心的数字图书馆的基础上，系统地介绍用户模型指导系统功能、流程、交互方式等设计的多项细节。提出“用户心理与行为-数字服务－信息系统－市场调查-改进系统”的方式，优化数字图书馆服务系统。

【关键词】用户建模用户生成多元用户个性化服务人机交互

【分类号】G250.76

# Research on that User Behaviour Model Driven Information System Design

Ku Liping

(Department of Library and Information Science，National Taiwan University，Taipei lO617,China)

Abstract】Basedonafullinvestigationofuser-led，user-drivenanduser-centred digital library,thearticle introlucesdetails of user model that guides the informationsystem functions，processes and interaction.Therecommendationis Lconcisemethod as“user psychologyand behavior-digital service-information system-market research-improve nformation systems”in order to optimiz digital library service system.

Keywords】User modelingUser generatedMulti-userPersonalized serviceHuman -computer interaction

# 引言

8/111107010:7110111

数字图书馆面临的挑战来自许多方面：信息技术不断改变,新的信息技术会创造新的信息环境;用户在新的言息环境中,会产生新的信息行为;当新的信息环境和新的用户行为交叠出现时,信息服务就需要不断调整来适应这些越来越复杂的不可预测性。

面对这些挑战,数字图书馆逐渐发展出用户中心、用户驱动、用户主导等实践策略,尽其所能满足用户需求。相关研究归纳如表1所示：

表1用户中心型、用户驱动型、用户主导型数字图书馆  

<html><body><table><tr><td>类型</td><td>相关概念(节录重点)</td><td>定义</td></tr><tr><td>用户 中心型</td><td>信息系统、数据安全、互联网、隐私权、用户研究、设计、学习、学习型组织、社区、门户网站、网络、电子 市场、用户行为、分类、智能代理、评估、模拟、数字政府、技术接受程度、易用性评估</td><td>类似门户网站与交易平台的E化学习 服务型数字图书馆</td></tr><tr><td>用户 驱动型</td><td>网络搜索、信息检索、业绩衡量、评价、比较、移动电话、移动计算、手持式装置、社会网络、YouTube、 MySpace、信息服务、用户界面、互联网、设计、客户满意度、信息素养、用户建模、个性化、自适应服务</td><td>类似搜索引擎或社会媒体的社会网络 服务型数字图书馆</td></tr><tr><td>用户 主导型</td><td>通信、传递架构、概念的定义、读码、术语、分类、编码系统、知识表示、计算管理、信息系统管理、用户 参与、用户代表、用户满意度</td><td>类似检索系统与管理系统的用户参与 服务型数字图书馆</td></tr></table></body></html>

表1中的相关概念为从SCI与 SSCI数据库内进行主题检索,利用Java程序提取关键词、题名和摘要内的词汇,人工过滤重复主题词汇(如图书馆、服务等)以及无关词汇(如中国文化、南非等)而得到。

(1)在用户中心型数字图书馆方面，Lin等介绍中国政府数字化系统的评价，并且阐明政府机构如何能设计出适宜的管理措施，以促进技术的接受程度和使用情况[1]。Bapna 等指出较好的信息系统会密切联系用户的喜好、行为、个性和最佳化他们的经济福利[2]。Martin等认为建立一个标准化和最佳化的做法是人们访问的方维网经验以及据此做出信息系统设计的界面；一个线上目录系统应该向提高分类、获取、图像和数据有关的历史数据分析功能上发展[3]。Williamson认为通过用户选择的配置、资源描述、元数据存储库，以及联结具体配置的信息资源，可达到“以用户为中心”的实践过程[4]。Barmard 等强调以用户为中心的诸多信息资源问题，能提供信息搜寻行为与需求有益的参考借鉴[5]。Zhang 等说明电子化政府以用户为中心的评价模型,包括：有用性、易用性和合适性[。Som-erville 等说明邀请用户、校园图书馆、利益相关者和受益者共同学习参与图书馆设计的案例，指出“学习他们的方式”（而不是图书馆的方式)的必要性[7]。Maler研究不同类型的认证识别技术[8]。Deng 等设计一个身份管理机制以确保不同授权下的语义数据交换[9]

(2)在用户驱动型数字图书馆方面，Frias-Martinez等认为改善数字服务的一个趋势是通过个性化服务，最常见的数字图书馆个性化方法是用户驱动，也就是提出自适应的数字图书馆，可以自动学习用户的喜好和目标,以完善个性化交互的不足[10]。Curran 等认为图书馆1.0和2.0的区别在于图书馆1.0只允许单向的信息流，而2.0是一个面向用户的读写数据库，旨在保存每个在图书馆用户检索信息的时间，使图书馆用户有权利来决定他们得到的服务[11]。Spiteri 认为随着标示有用的外部参考资源，大众分类法（Folksonomies）可以增加公共图书馆目录的用户友好性和交互性，也可促进其他服务，例如读者和用户的非正式网上社区行为，以及图书馆对读者的参考咨询服务等[12]Wareham等综述移动设备和服务的开发模式：采用设计思维、生活实验室及其他形式的民族志（Ethnogra-phy），包括运气、好玩、错误等以前被正统技术设计忽视的人类行为，以探索性地开发产品，使得消费者一如既往地支付费用[13]。Seng 等提出一个用户驱动的工作流，以制定工作量要求、转型和作为通用结构的基准;该模型描述网页结构、查询定义的逻辑以及控制变量[14]。

# 46 现代图书情报技术

(3)在用户主导型数字图书馆方面，Lawrence等定义用户主导的发展是希望提高用户的参与和控制，以提高网站知名度;通常会先从一小部分用户测试、培训、实施制度后,才确定用户社群的需求和要求[15]。Flynn等认为信息系统应该构建用户需求，让用户建立自己的需求模型[16]。Rowley 从数据库涵盖范围、及时性或当前性、成本、创造和维护用户接口的机制等方面展开讨论，包括：内容页面服务、文摘和索引服务、以及综合在线产品的信息服务[17]。Wessels等强调电子社会的科学研究，包括：确定新的研究重点、适应研究过程、制定并发展与网格相关的研究工具[18]。Myhill 等认为使用 $\mathrm { { W e b } } 2 . 0$ 工具可以创造虚拟研究环境的基础，因为Web 2.0有适合用户探索知识的特征[9]

发展数字图书馆有三种思路：从已有的信息服务来观察用户行为，应用新的信息技术以更好地完善已有的信息服务；跟踪新的信息技术，使得新一代的数字图书馆接近于用户所处的新的信息环境，从而应用新的信息技术开展新的信息服务；研究用户在新的信息环境中的信息行为，据此应用、改造、开发或淘汰信息技术，从而实现新的信息服务。

利用用户模型指导系统功能、流程、交互方式等设计的系统性论述和探索还相对较少，本文针对第三种发展思路，进行相关案例和研究的梳理，并提出“用户心理与行为-数字服务-信息系统-市场调查-改进系统”的方式，以优化数字图书馆服务系统。

# 2用户模型驱动系统设计的发展

创建与使用型人是其中一种实践数字图书馆系统优化的方式。Lamberts认为以用户为中心而设计的型人，结合市场细分、实地研究和市场研究，可以从中获知谁是我们的用户、他们的目标和核心任务是什么，以及他们如何工作等问题[20]。

2000年，Coney等宣称通过型人可以使网站设计者和用户交流，而且网站的成功就取决于这些型人如何完整地说明网站设计和网站评价的关系[21]。而 Sil-verman等则利用型人做出了一个通用的工具集模拟器概述，并且说明了如何通过从事训练和教学，来支持创作和学习行为的游戏运行[22」；作为早期使用Personas的系统，不仅仅是设计，更指出了TrainingGame和Personas 整合的概念。

8 年前，Greaney等发布人为计算过程,通过主成分分析，对社会资本和学院/邻里集中度两个方面分析,创建型人来设计移动服务[23]；这应该是较早脱离单一系统走向多种媒体载具（Device）的研究。后来，从载具又向软件发展，形成具有不同的设计阶段的多元型人。

5年前开始，用户情境通常配合使用型人来表现与系统交互而设计的主题[24]。然而,因为缺乏行为计算，效果并不明显，例如Haikara的案例表明，使用型人的过程中往往因为客户不熟悉型人而没有在实践阶段（TheReleaseDays）成功，而且开发团队更重视型人的各项指示条目（ReferentItems）而不是虚构人物的姓名、性别或年龄[25]；至此，型人又从多元向动态型人（DynamicPersona）的概念发展。

随着Web2.0影响力的逐步扩大，近期Silva等通过建立文档识别型人，建立并开发了线上社群网站的行销策略和工具[26]。用户模型驱动系统设计开始拓展到各个不同的层面，Zimmermann等指出：运用型人可以确立系统的最终实践用途，在适当时机用有效方式实施修补程序，避免了研发团队过度追求技术的复杂性而忽视技术的适用性[27]。在设计流程研发上,Hussain等在实践中体会到：型人应该在规划、发展或进行任何决策过程中，有意或无意地进人到团队成员的思考中去[28] 。

用户模型驱动系统设计的模式已日渐成熟，下面分别叙述各种不同模式的内容、案例、起因和应用于数字图书馆的思路。

# 3用户模型驱动系统的设计方式

# 3.1作为交互界面的一种辅助方式

多数信息系统的元数据与数据、计算公式与程序、使用功能与操作步骤等，在制作的前期规划、中期测试、后期验收过程中，均不考虑用户行为模型。涉及的用户需求(UserNeed)是根据系统功能而描述的，可以直接从用户需求转化为用户输人指令的用户要求（UserRequire），因而“用户行为”等于“用户操作步骤”，其必须按照系统流程所定义的用户要求的步骤来执行。

用户行为模型的意义和可发挥的范围，被明显局限在交互界面的设计上。用户行为的调查和用户行为驱动系统设计的方式，在于区分不同的用户群组，以表明通过不同的系统界面，能够促使用户快速地和方便地适应输入指令进行系统运算，例如，经过界面设计后Lindgren等表明利用型人的方法论，可以清楚认识个体差异性和驱动团体差异性等[29],从而有益于日后的系统设计。即用户模型驱动系统设计的方式属于被动性质。

产生这类设计的原因是，软件设计往往需要依靠硬件设备的要求来制定，当硬件要求或者机构组织较为强势（例如，手机制造商分包业务给软件设计公司，或者图书馆高级职员要求程序员编写软件等)时，软件设计往往必需优先考虑如何符合合约书或规划书上的要求，完成基本系统功能后，才开始“定义”用户行为。

# 3.2作为决定系统功能的一种辅助方式

与大多数习惯“定义”用户行为的设计者相反，终端用户认为用户行为“不是被定义的”，而是“有待了解和认识的”。如果设计者不了解也不认识真实世界的用户行为，那么，信息服务系统至少应该设计为“可以调整和改变的系统”，以适应各种类型的终端用户。

部分信息系统，在众多的技术可选性和实践方式差异性上，既要节省时间和人力资源，又要能满足系统设计的目标。其信息系统的元数据与数据虽然是相对固定不变的，但是计算公式与程序，以及使用功能与操作步骤等设计，可以有较大弹性。在制作的前期规划就需要考虑到哪些功能需要、哪些功能不需要，哪些功能要保留以便日后附加，哪些功能要能够可扩展等。

用户行为模型的意义和范畴，拓展到了前期规划上，特别是选择和决定系统功能这一方面。例如，Booth设计型人来描述社交网站上的文本（Text）与脉络（Context）[30]。因为社交网站无需考虑用户的上网设备，只需要考虑用户接触的信息和信息所呈现的方式，以及用户和用户之间交流的方式，所以一些系统功能（如分类目录)可以省去，而一些系统功能（如及时通信)需要强化，甚至需要特别研究用户行为后仔细设计。即用户模型驱动系统设计的方式属于主动性质。

产生这类设计的原因是，软件设计与硬件设备是同一组人员；或者硬件设备的规格单一，软件设计的发挥空间大；或者主要以软件设计为主，硬件设备的规格影响不大，甚至不构成影响。例如，出售商品或服务的网站设计者，所出售的商品或服务，基本上和网站设备无关，只是和网站所呈现的信息以及和呈现信息的方式有关；早期考虑双绞线的信息传输量来决定网站设计的流量问题，在光纤通信的时代几乎不被网站开发者、管理者和使用者所考虑。

# 3.3作为设计系统流程的一种辅助方式

在某些“特殊”情况下，设计者需要先深入了解和认识用户行为，才能够开展信息系统的设计。这种少见的信息系统，其硬件设备和软件设计是密不可分的，而且用户具有独特性和不可迁移性。这类信息系统的元数据与数据、计算公式与程序、使用功能与操作步骤等，可以分阶段完成，然后再组装成一套信息系统。但是该信息系统的各个组成部分在制作的前期规划、中期测试、后期验收过程中，都需要反复参照用户行为模型。

用户行为模型的意义和可发挥的范围，就不只在前期规划上，而是贯穿所有信息系统的工作流程中。在网站设计中Casas等尝试结合创建型人、使用型人、环境智能（AmI）、以用户为中心的设计，来开发新一代用户建模（UserModeling）[31],以开发作为辅助设计系统流程的一种方式。即用户模型驱动系统设计的方式属于必要性质。

产生这类设计的原因是软件设计主导硬件设备的制作，例如机械手臂的设计不仅取决于用户的工作或生活需求，也取决于用户的习惯、资金、个别体质等的差异。在软件设计主导硬体设备、材料和工序的情况下，所谓“用户需求”、“用户行为”、“用户模型”等术语的定义和内涵，与情境中的交互设计完全不同。这里的用户行为不但是前期规划、中期测试、后期验收中的决定因素，也决定着元数据、数据、计算公式、程序、使用功能、操作步骤等每一项信息系统的组成要素。从面向大众用户（MassUser)和高端用户的角度来看，这种设计仅仅是少数情报战略的分析系统可以借鉴的模式；但是，如果从服务个人（Individual)的数字图书馆角度来看，未尝不是个性化服务系统可资借鉴的设计思路。

# 3.4作为整体服务规划的一种辅助方式

有别于前三种模式，作为整体服务规划的一种辅助方式，不考虑软件和硬件，而是考虑更为抽象的服务。先考虑"服务什么”的概念、策略和流程，再考虑支撑这种服务所需要的信息系统。这种设计往往产生于：

(1)需要持续不断产生创意的团队;

# 48 现代图书情报技术

(2)跨语言、跨文化或跨专业且需要加速沟通效率的团队;

(3)人员流动率快的团队。

因为这种团队不仅外在竞争环境复杂多变，若要参与快速竞争，则要采用用户模型驱动系统设计的方式，而且团队组成复杂多变，难以快速磨合。

例如，在设计创意研发上，Okamoto等证实：情境可以有效地支持参与者。他们区分开发小组和用户小组来共同创造具有生活方式和文化背景的型人[32]。区分设计团队（D-team）发展创意和假设，而用户团队(U-team)描述情境和需求，有助于日本和台湾地区之间的跨文化沟通，以及更为确切地解决跨语言的交流障碍。而在跨专业团队中，Goodall等则认为型人有利于团队逻辑地、连贯地设计实际的用户需求，通过一个难忘的故事而让所有团队成员对项目目标和优先事项有共同理解[33],对用户需求、用户要求、用户行为、用户模型等术语，产生一致的定义和认识。

# 3.5 研究困境与新的方式

综上所述，用户模型驱动系统设计是未来数字图书馆的发展趋势。总结用户模型驱动系统设计的案例所提出的“研究限制”，可以发现目前存在三种研究困境：

(1)依靠问卷调查、结构与非结构访谈或追踪观察等社会科学建立的型人模型对于改善交互设计的实际作用仍然难以用数量方式客观评量；

(2)依赖网络日志进行的频次计算、社会网络分析、非线性回归模型等，仍然只能在有限样本中进行推论，对于解决实际交互设计的影响不大；

(3)社会科学法与日志分析法的结果只能相互“补充"而不能相互验证或佐证，因此种种相互补充的结果也只是理论构建，对实际应用的帮助有限。

根据这些研究困境，本文建议新的方式应该采用直接而且持续发展的方案：

(1)以社会及行为科学（SocialandBehavioral Sci-ence)研究方法建立模型；

(2)根据模型设计日志分析（LogAnalysis）、社会标签（SocialTag）和自然语言检索（Retrieval-basedNaturalLanguage）的混合模式识别（PatternRecognition）机制；

(3)对用户行为预测（UserBehaviorPrediction）进行实验，以用户测试来验证型人模型；

(4)根据结果，建立符合学习认知及研究行为规  
律的人机交互（Human-ComputerInteraction）模型;(5)建立嵌人不同载体（EmbedDifferentVehicles）  
的信息系统;(6)建立集成不同工作流程的系统(Workflow Inte-  
gration System） ;(7)从社会及行为科学研究中，修正模型和系统。

# 4讨论

系统设计必须在实证研究的基础之上，当非正式信息行为成为学习与研究的重要活动时，数字图书馆系统与技术就不应该、也不能够再从用户中心、用户导向、用户驱动等概念直接跳到建立系统。最根本的解决办法，就是在不影响用户正常使用数字图书馆的情况下，通过密集的观察与实验，不断完善现有系统的服务能力。

# 4.1数字资源使用者

从数字资源使用者的角度来说，如果数字图书馆认识到用户并不是单一性质，而是具有不同行为与心理取向的差异化用户，则将在原有实践基础上，大大提升图书馆服务的功能与作用。由于用户信息环境和信息行为超越传统的图书馆和传统的数字图书馆服务范围，例如他们不只从事文献信息的检索，也进行工作经验的交流；不仅仅利用搜索引擎或仅仅在图书馆中找资料，也会进入学会网站、门户网站论坛、电子公告栏和博客等进行信息搜寻和交换。因此，如果不了解用户新的行为趋向与模式，仅仅停留在不断完善自己现有系统的功能与效率上，则有可能出现事实（用户行为)与愿望(满足用户)相背的现象。换言之，信息服务系统，应该打破“图书馆”的约束（包括物理空间、网络位置、思考模式），从更一般的信息服务来考虑，由于用户经常使用也比较信赖那些网络交流模式，因此如何让图书馆的服务更多地以这些形式出现、如何嵌入到用户的交流模式和过程中等，是更为重要的课题。

# 4.2数字资源管理者

从数字资源管理者的角度来说，与其花费大量时间、人力和经费，使所有用户的基本操作行为保持一致,达到"投人少，产量多”的规模经济效益，不如花费少量时间、人力和经费，创造一套模式，使每个人能够发挥特长，图书馆则可从失败和成功的经验中，不断提升改进的空间，能够达到规模经济效益。

数字图书馆系统与技术，除了追踪网络环境的变化，以掌握信息技术为手段，将信息技术整合在数字图书馆系统上，形成新的服务模式和方法；还可以考虑通过型人模型积极了解不同用户的不同行为与特征，从中发现潜在需求，以预测未来信息市场为手段，规划并设计更具竞争力的信息服务（更有传输效率、更节省用户时间、更多信息分析、更准确的用户查询目的和需要、更节省经费成本、更早为用户准备好其所需要的信息等)，再投资目前没有但是未来具有市场的信息技术。

# 5结语

数字图书馆是本地化（Localization）的信息系统，由于用户组成不同、信息资源不同、财力和人力结构不同等，难以完全仿照Firefox或Google全球化（Global-ization)的信息系统。不过，数字图书馆一方面可与大型信息供应商和服务商共同发展全球化策略，以“借力使力”服务用户；另一方面也可以通过回答用户的网上信息行为如何被准确定义、如何不断地更新、如何有效率地计算等问题，深入理解服务对象，然后推进服务。

# 参考文献：

[1］Lin CT,Hu PJH,Chen HC.Technology Implementation Management in Law Enforcement COPLINK System Usability and User Acceptance Evaluations[J]．Social Science Computer Review, 2004，22(1) :24-36.   
[2]Bapna R，GoesP，Gupta A，et al.User Heterogeneity and Its Impact on Electronic Auction Market Design：An Empirical Exploration[J]．MIS Quarterly,2004,28(1) :21-43.   
[3］Martin K,Lin X,Lunin L.User Centric Design and Implementation of a Digital Historic Costume Collection[J].Proceedings of the American Society for Information Science and Technology,2O03,40 (1):280-290.   
[4]Williamson K.Where One Size Does Not Fit All：Understanding the Needs of Potential Users of a Portal to Breast Cancer Knowledge Online [J]．Journal of Health Communication,2005,10(6):567-580.   
[5]Barnard Z,Rensleigh C.Investigating Online Community Portals for Enhanced Alumni Networking[J]．The Electronic Library,2008, 26(4):433 -445.   
[6]Zhang N,Guo XH,Chen GQ,etal.Impact of Perceived Fit on E-Government User Evaluation：A Study with a Chinese Cultural Context[J].Journal of Global Information Management,2009,17 (1) :49 -69.   
[7]SomervilleM M, Collns L. Collaborative Design: A Learner-cen tered Library Planing Approach[J]．The Electronic Library, 2008,26(6):803-820.   
[8]Maler E.The Design of Everyday Identity[J].Online Information Review，2009,33(3）:443-457.   
[9]Deng M,De Cock D,Preneel B. Towards a Cross-context Identity Management Framework ine-Health[J].Online Information Review，2009,33(3) :422 -442.   
[10]Frias- Martinez E，Magoulas G,Chen S,et al.Automated User Modeling for Personalized Digital Libraries[J].International Journal of Information Management,2006,26(3）:234-248.   
[11]Curran K，Murray M,Christian M.Taking the Information to the Public Through Library 2.O[J]．Library Hi Tech,2007,25（2）： 288 -297.   
[12］Spiteri L F.The Structure and Form of Folksonomy Tags：The Road to the Public Library Catalog[J]． Information Technology and Libraries,2007,26(3）:13-24.   
[13]Wareham JD，Busquets X，Austin R D.Creative，Convergent, and Social:Prospects for Mobile Computing[J]．Journal of Information Technology，2009,24(2）:139-143.   
[14]Seng JL,Ko IF,Lin B．A Generic Construct Based Workload Model for Web Search[J].Information Processing& Management, 2009,45(5) :529 -554.   
[15]Lawrence M,Low G.Exploring Individual User Satisfaction Within User- led Development[J].Management Information Systems Quarterly，1993，17(2):195-208.   
[16]Flynn D J,Jazi M D.Constructing User Requirements：A Social Processfor a Social Context[J].Information Systems Journal, 1998,8(1) :53 -83.   
[17]Rowley J. The Changing Face of Current Awareness Services[J]. Journal of Librarianship and Information Science，1998,30（3）: 177 - 183.   
[18]Wessels B,Craglia M. Situated Innovation of e- Social Science: Integrating Infrastructure,Collaboration，and Knowledge in Developing e-Social Science [J]. Journal of Computer- Mediated Communication,2007,12(2):692-711.   
[19]Myhill M,Shoebridge M,Snook L.Virtual Research Environments -A Web 2.0 Cookbook？[J].Library Hi Tech,2009,27（2）： 228 -238.   
[20]Lamberts H. Case Study:A PDA Example of User Centered Design [M].Berlin:Springer-Verlag,2002:329 -333.   
[21]Coney MB,Steehouder M.Role Playing on the Web:Guidelines for Designing and Evaluating Personas Online[J].Technical Communication,2000,47(3） :327 -340.   
[22]Silverman BG,Holmes J,Kimmel S,et al. Modeling Emotion and Behavior in Animated Personas to Facilitate Human Behavior Change：The Case of the HEART- SENSE Game［J]．Health Care Management Science,2001,4(3）: 213 -228.   
[23]Greaney J,Riordan M. The Use of Statistically Derived Personas in Modeling Mobile User Populations［A].//Human - Computer Interaction with Mobile Devices and Services[M].Berlin：Spriger - Verlag,2003:476-480.   
[24]Dong J,Kelkar K,Braum K. Geting the Most out of Personas for Product Usability Enhancements[C]. In:Procedings of the 2nd International Conference on Usability and Internationalization.Berlin:Springer-Verlag,2007:291-296.   
[25]Haikara J.Usability in Agile Software Development：Extending the Interaction Design Process with Personas Approach[A].//Agile Processes in Software Engineering and Extreme Programming[ M]. Berlin: Springer-Verlag,2007:153-156.   
[26]Silva E J,Sallaume S. Online Communities Administration：Defining Tools for Different Profiles[C].In:Proceedings of the 11th IFIPTC13 International Conference on Human-Computer Interaction，Brazil.2007:353 -356.   
[27] Zimmermann G, Vanderheiden G. Accessible Design and Testing in the Application Development Process：Considerations for an Integrated Approach[J].Universal Access in the Information Society,2008(7) :117 -128.   
[28]Hussain Z,Milchrahm H,Shahzad S,et al.Integration of Extreme Programming and User - centered Design：Lessons Learned [A].// Agile Processes in Software Enginering and Extreme Programming[M].Berlin：Springer- Verlag，2009:174-179.   
[29]Lindgren A,Chen F,Amdahl P,et al.Using Personas and Scenarios asan Interface Design Tool for Advanced Driver Assistance Systems [A].//Universal Access in Human -Computer Interaction.Ambient Interaction[M].Berlin：Springer- Verlag,2007:460-469.   
[30]Booth P.Rereading Fandom：MySpace Character Personas and Narrative Identification[J].Critical Studies in Media Communication,2008,25(5):514-539.   
[31]Casas R,Marin RB,Robinet A,et al.User Modeling in Ambient Intelligence forElderlyand Disabled People[A].//Computers Helping People with Special Needs[M]．Berlin：Springer -Ver lag，2008:114 -122.   
[32]Okamoto M，Komatsu H，Gyobu I，et al.Participatory Design Using Scenarios in Different Cultures[A].// Human - Computer Interaction.Interaction Design and Usability[M].Berlin：Spriger- Verlag，2007:223 -231.   
[33] GoodallJR,Conti G,Ma Kwan-Liu. Adapting Personas for Use in Security Visualization Design[A]．//VizSEC 2007[M].Berlin：Springer- Verlag，2008:39-52. （作者E-mail; kuliping@ ntu.edu.tw）