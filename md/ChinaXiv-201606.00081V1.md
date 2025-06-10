# 数字图书馆的社会媒体系统技术研究

# 顾立平

(国立台湾大学图书资讯系台北10671）

【摘要】社会媒体系统主要包括播放系统、标记系统和搜索系统。在系统地介绍社会媒体的相关研究基础上,讨论已实现的技术和开发中的技术整合为用户驱动影音媒体服务的数字图书馆系统模型。

【关键词】社会书签社会标签播客闪客视频影片分享网站【分类号】G250.76

# ResearchonTechnologiesofSocialMediaSystemofDigitalLibrary

KuLiping (DepartmentofLibraryandInformationScience,NationalTaiwanUniversity，Taipei1O671,China）

[Abstract]Socialmediasystemmainlyincludesbroadcastsystem,tagingsystemandsearchsystem.Basedonthesystematicalintroductionoftherelevantstudiesofsocialmedia，therealizedtechnologyandthedevelopingtechnologiesare discussedandintegratedasthemodelofdigitallibrarysystemthatuser−drivenaudio–videomediaservices.

[Keywords] Social bookmarkSocial tagPodcast Flash wideoVideo sharing site

# 1前言:以用户生成为对象的数字化服务

社会媒体是一种用户生成内容(UserGeneratedContent)的机制,用户可以在社会蝶体上发表文字、图像、影视等内容;社会媒体也是一种用户参与(UserParticipation)的机制,用户可以在别人所发布的内容上,进行标注、评论、推荐和链接等活动;社会媒体是一种融合播放系统、标记系统和搜索系统等技术的信息服务系统,它按照用户体验(UserExperience)的思想来整合这些技术,并且不断地自我演变和开发新的技术。

对于社会媒体的正面观点认为:社会蝶体能强化社群力量,能过滤信息、加深关系、迅速组织、提高创新与综合知识,甚至发挥对医疗体系的活力和影响力[1]。反面观点则认为,虽然YouTube、Facebook,MySpace、Twitter和SecondLife等社会媒体由于成本低廉,可以普及保健信息,特别是青少年和青年,但是缺点在于缺乏作者信息、引用来源、事实根据等重要的判断内容依据[2]。

一般来说,在公共事务中的反面观点较强。研究YouTube和MySpace在2006年美国选举的影响,Gueorguieva(2008)认为,社会媒体的影响主要不是政党提供图影声像的正面影响,而是以反对和批评对手为目标的用户参与评论[3]。而在研究学习领域,则持比较正面的看法。例如，Agazio等(2009)认为教师可以使用YouTube的技术来激发学生讨论课程、分享信息与创建学习型社区[4]。而从旅游业的角度来看,社会媒体充满机会和挑战。因为旅游者使用搜索引擎查询到社会媒体,这些行为会影响其旅行计划,所以如何发展相应的市场策略成为一种挑战[5]。

不过,更多学者对社会媒体的“正当应用”持谨慎的态度。Kim等(2010)综述了发现朋友、分享自创内容等社会网站的特征,但并没有提出正面或反面的看法,只是认为社会媒体提供一种信息技术应用的机会[6]。而Cochrane等(2010)则认为多数学生使用和反馈交互式多媒体的情况,实际上已改变了教学过程,然而移动式Web2.0工具还需要进一步的教学效果评量[7]。

数字图书馆发展社会媒体系统应当持谨慎乐观的态度，一方面信息技术的应用可以丰富信息服务的能力和范围,另一方面,我国《荀子·王制篇》和《贞观政要·论政体》里,都提到“水能载舟,亦能覆舟”的道理,这里的“水”可以比喻用户,而“舟“可以比喻数字图书馆。

本文首先梳理以用户为中心的社会媒体机制,然后分析社会媒体系统中已实现技术和开发中的技术,最后讨论用户行为驱动社会媒体传播的数字图书馆系统。研究成果可以作为图书馆发展社会媒体的参考。

# 2进展：以用户为中心的社会媒体机制

在ISO13407的国际标准规范里,以人为中心的设计(HumanCenteredDesign)原则包括;了解井指定的使用背景(UnderstandandSpecifytheContextofUse）、指定的用户和组织要求(SpecifyUserandOrganizationalRequirements)产生多个候选设计方案（ProduceMorethanOneCandidateDesignSolution）、根据需求设计评估（EvaluateDesignsAgainstRequirements）等[8]。因此,设计系统之前,理解用户行为,并且考虑到用户所处的脉络( $\mathrm { c o n t e x t } { \mathrm { . } }$ ,是数字图书馆发展社会媒体系统的重要工作。

社会媒体的用户行为和信息检索系统的用户行为有很大不同。在信息检索系统中,用户的行为与其他用户无关。虽然新一代的搜索系统普遍采用统计所有人的查询词汇和使用结果,来作为排名结果的参数,但是输入查询公式或关键词的用户,并不受到其他用户的直接影响。例如,在新闻、消息和信息获取(News,Message,InformationAccess）上,用户的检索行为更多地是一种“获取”（Catch)行为,可是,社会媒体的用户则是一种“交流”（Communication）行为。用户在社会媒体上发布他的内容,这个行为需要经过组织、整理、上传和确认等动作,而且有可能遭受其他人对内容（甚至是对个人)的无情批判,这些特征与传统数字图书馆所认识的用户行为有很大的不同。

对这种行为的解释,Skageby(2010)探讨了在网络社会中的送礼理论(Gift−givingTheory）[9]。学者们认为:社会媒体(包括集体编辑的维基百科、P2P文件共享的Napster、多媒体的YouTube、非固定式评论的博客等)所形成的信息池是一项公共财产( $\mathbf { I n f o r m a t i o n \ P o o l s }$ thatCreateaPublicGood）,人们通过反馈活动能够给子内容贡献者更高的排名和声誉[10]。用户下载档案是一种从信息池获取公共财产的方式,他们不用付出物质(金钱),但是需要付出非物质(精力和时间)财产;同样地,用户上传档案获得积分、排名和声誉等非物质财产,也是一种从信息池获取公共财产的方式。

这种用户认知心理是以人为中心的系统设计所需要关注的用户行为脉络。

如果从结构主义和后结构主义的角度来看,在信息检索系统中的用户,是属于信息系统(结构中)的一部分，而社会媒体中的用户,则是属于信息系统的一个非解释部分(结构外),确切地说:“站在信息系统之后来监视信息系统的”那个部分,即它具有“用户依赖但是独立于系统”的关系。

社会网站是一个虚拟空间中,再现个人存在本质的机制[11]。 $\mathrm { S h a o } ( 2 0 0 9$ ）认为社会媒体用户具有消费信息、娱乐内容和情绪管理的需要,通过参与互动内容加强和虚拟社区其他用户的社会联系,以及自我表达和自我实现,建议加强易用性(EasytoUse)和控制性$_ \mathrm { L e t \ U s e r s \ C o n t r o l } ) ^ { ( 1 2 ) }$ 。针对用户行为，人们可以分析线上影视的标题、描述和意见的语法、句法和内容特点,判别用户生成内容的关键词语[13];人们也可跟踪用户行为以挖掘信任团体的反馈、信任关系的品质和评估用户信任[14]。然而，因为用户定义从思想上就根本不同,所以社会媒体以人为中心的系统设计就不能“比照”信息检索系统,而需要另一种根据用户行为所作的设计。

社会媒体系统的脉络和用户与信息检索系统不同,即便是运用了相同的工具(标记语言、查询语言、描述语言等),其设计理念依然有所不同。

# 3技术:符合用户体验的社会媒体系统设计

# 3.1播放系统

作为目前全球最大的影音媒体服务商,隶属于Google下的YouTube无疑是一个合适的参考范例。YouTubeAPIPlayerApplications最初用ActionScript2写成,现在为ActionScript3（AS3）,可以与ActionScript

3和Flex通用;其中混搭技术的TubeLoc采用Local­Connection类与SWF(播放程序)交互[15]。这种技术能够让终端用户的系统负载量减至最低,同时保持服务器端的储存、提取、传输等计算能力。其特点不是检索系统中的元数据信息呈现,而是影音媒体的传输。

例如,在MovieSprite.as中建立TubeLoc类集,然后创建一个实例MovieSprite类及其影片ID识别码,增添PlayerReadyEvent（含影片规格）,示例如下；

package//时装importflash,display.Sprite;//代入Flash播放器importcom.enefekt. tubeloc.MovieSprite;//代,入混搭TubeLoc规范importcom.enefekt.tubeloe.event.+↓//代,入TubeLoe下的事件public classMainChromed extends Sprite|//@建Chrom所延伸的类privatevaryoutubeMovie:MovieSprite;//代入YouTube的个功能publicfunctionMainChromed(）{//代入Chrom的通用功能…•∗youtubeMovie=newMovieSprite{"20080922\*）//建立.新的内容youtubeMovie，addEventListener(PlayerReadyEvent.PLAYER_READY,onPlayerReady）;//加载播放器并规定播放格式youtubeMovie. $\textbf { x } = 1 0 ;$ 1youtubeMovie.y ${ \mathit { \Omega } } = 1 0 ; { \mathit { \Omega } }$ addChild( youtubeMovie);  
1  
1一

有学者发现YouTube工作量具有类似齐普夫分布的情况（Zipf−likeBehavior）,若用代理缓存（ProxyCaching)可减少网络流量,并且提高系统的可扩展性[16]。对数字图书馆而言,在设备有限的情况下，采用AS3编写播放程序,同时考虑臧少与终端用户之间网络流量(资源消耗),是相对经济实惠的发展方式。

此外,有别于商业网站,数字图书馆可以选择部分用户有权限上传,所有用户有权欣赏的开放获取0 $\mathbf { O p e n \ A c c e s s }$ )模式。

# 3.2标记系统

播放系统是社会媒体有别于传统数字图书馆服务的一个表面特征,数字图书馆社会媒体的内在特征则是标记系统。这个标记系统既不同于信息检索系统中针对信息(如期刊文章的标题、关键词、作者、单位等)所描述的对象,也不同于社会网络系统中针对用户（如交友偏好、兴趣、年龄等)所描述的对象,而是针对用户所产生的内容,也就是他们自创的影音信息等进行描述。

例如,以FlashPlayer播放器为基础的社会媒体,可以在FlashDevelop,FlexIDE,Eclipsew/FDT,IntelliJIdea等平台上开发AS3所构建的应用程序界面。再如,在YouTube中的标准化视濒讯息（StandardVideo\~FeedEvent)参数(Parameter)是按照AS3的doVideosRe-ceived功能所设计,其包括:视频标题(theVideo’sTi-tle）、嵌入视频的SWF档的URL(theURLoftheSWFtoEmbedtheVideo）、观看数目（ $\mathrm { t h e \ V i e w \ C o u n t }$ 评论数目（theCommentCount）、视频持续时间（theVideoDu-ration)以及作者姓名(theAuthor’sName）等[17]。其代码示例如下：

fanctiandoVideosReoeived(evt:StandardVidenFeedEvent)//代入函数  
一varfeed;VideoFeed $\mathbf { \lambda } = \mathbf { \lambda }$ evt.feed；//获得包括视频的反馈vsrvideo;VideoData；//保存每部被检索影片的数据变量while(video=feed.next())//重复每次变量總果丨trace("\nvideotitle:”＋video.title）;//根据影片名称播绘新行trsce(°playerurl:”+video.swfUrl);//搖绘最入Flashplayer的视類播放网trace{“viewCount:”+video.viewCount）；//.赏次数trace{”eummentCount:"+video.commentCount）；//译论次数trace{”duration:”+video.duration）;//视類持续时间trace{“author:”+video.authors,first(）.name）;//影片上传者1  
1

在程序库中,除了ProfileEvent外,所有事件都有一个反馈属性(Property）,用来描述、记录和操作用户行为。例如:以first（)来检索第一条记录、以last（）来检索最后一条记录、以CounI（）来记录能够反馈的结果数量（不是所有的反馈结果)、以getAt（）来获得特定位置的结果、以next（）来检索下一条可用记录,以及用previous(）来检索反馈前一条记录等。

从社会媒体的标记系统所衍生的社会标签（SocialTag)机制,是发展中的关键技术;社会标签包括;出版、聚合、整合、重新标记数据等活动,其异构资源间的系统互操作性需要定义结构、语义和关联[18]。Shiri（2009）分析10个标注系统，比较搜索与浏览功能、服务和界面接口，建议对张贴标签、标签使用、标签浏览、标签列表和标签云进行整体设计[9]。 $3 4 ^ { \circ } = \sin \frac { \pi } { 2 }$ 等（2010）整合个人用户的标签记录以调整对个人偏好的信息推荐，认为个性化排名模型应该兼顾用户偏好和社群建议[20]。社会标签技术可以更好地补充社会媒体对元数据对象描述的不足，以及在社会媒体已有的元数据基础上，开发新的应用程序；如前所述，这是因为社会媒体必须考虑：减少与终端用户之间网络流量，也就是资源消耗过大的问题，从而对元数据及其应用程序采取轻便设计，而在对象元数据之外的数据应用方面，采用社会标签来分工。

因此，开发社会标签技术并不是来描述那些在信息检索系统中的元数据对象（不过图书馆可以应用这套技术来研究他们所熟悉的业务对象)，也不是用来描述社会网络中的元数据对象（其发展态势良好），其原始目的是用来解决在社会媒体中的对象元数据不足的问题。因此，随着既有交叉又有分歧的检索系统、社会网络和社会媒体的发展，社会标签技术会不断地被开发来解决新的问题。

# 3.2搜索系统

社会媒体的进一步发展，是在检索系统的基础之上，开展搜索系统。因为检索系统受制于层次、网状或关联数据库的内容、规格和设计，而搜索系统则适合对网络信息内容进行排名；因此，社会媒体既有其独立拥有的关联数据库，也开放给网络搜索引擎，其搜索系统保持对两者的兼容性。例如YouTube以jQuery开发基于PHP和JavaScript的社会媒体应用程序界面，是在PHP用户端程序库上，以jQuery建立社会媒体的“活动信息提供监视器应用程序”，通过JaveSeript与客户端网页浏览器进行交互[21]。在YouTube中，以getAc-tivityFeed函数来处理用户行动和朋友行动（Activity）的反馈信息。其代码范例如下：

ylAetivityApp- getActivityFeed $\mathbf { \lambda } = \mathbf { \lambda }$ fumction( usemame） L if ytActivityApp. CURRENT_USERNAME $\mathbf { \tau } = \mathbf { \tau }$ usemame; form [0]. ehecked $\mathbf { \lambda } = \mathbf { \lambda }$ false;.. form[6]. checked $\mathbf { \lambda } = \mathbf { \lambda }$ t// 一代入检查

else  
ytActivityApp， CURRENT_ USERNAME $\mathbf { \lambda } = \mathbf { \lambda }$ ytActivityApp.MYUSERNAME ; form[0]. checked $\mathbf { \delta } = \mathbf { \delta }$ true;…… form[ 6]. checkedfalse://-代入检  
s(users_string_input\*）. attr [|value:“|) ； \$. getJSON( ytActiv-ityApp, URl, | q: \*usecfeed"丨,ytActivityApp. processJ5ON) ;1

前者为特定用户截取活动记录，后者为当前已认证用户截取活动记录。此函数用来检查用户是否登人到PHP层。其中，上述以JavaScript写成的ytActiv-ityApP-processJSON（）函数协助数据从PHP层到HTML网页以进行交互。如果嵌入播放器被添加到一个网页，它可以使用JavaScript进行控制；或者如果在Flash应用程序中嵌入播放器，则可以使用ActionScript来代替JavaSeript进行如：开始视频、暂停视、静音、投票等点击的控件控制。

用户识别和用户权限控制已是成熟技术，它们间接区别（或兼容）了当前社会媒体系统处于信息检索系统或者搜索引擎的“状态"（State）；然而，社会媒体发展自两类系统却又不同，所以在既有交叉又有分歧的技术发展过程中，逐渐产生两类前沿研究。

(1）预测内容排名（Predicted Content Ranking）是一种改进系统的趋势。例如Clements等(2010）从线上图书目录建立一个社会注解图（SocialAnnotationGraph）,采用随机游走模型（RandomWalkModel）整合用户偏好和查询词语，讨论信息检索系统的改进[22]。为提高内容查询相关度，节省用户反复查询的时间，针对社会媒体的“非结构化"用户生成内容，预测内容排名技术不仅影响社会媒体的发展，也间接影响搜索引掌的发展。

(2）将社会标签、搜索引擎和本体结合，改进社会媒体搜索系统是一个趋势。例如：Kim等（2010）提出结构、语义和标签关联的语义网标签（SemanticTag）模型，使得跨异构资源使用相同标签元数据[23]。而Ding等（2010）则设计上标签本体（UpperTagOntology，UTO)来收集、整合、搜索和分析标签数据，进行标注行为的建模[24]。社会标签源自社会媒体的实际应用需求，而搜索引擎是目前网络信息检索的关键技术，本体则是一个成熟但是缺乏实现平台的技术，三者结合不仅可以解决社会媒体的跨异构资源问题，也为技术本

身提供发展思路。

总之，数字图书馆技术的发展意来愈朝向不同技术的交叉、分歧和融合，用单一技术路线和思路已不能解决目前网络社会所带来的信息组织、检索和获取问题，而社会媒体只是数字图书馆在新的信息环境，新的信息服务以及新的用户行为中的一个前置问题。

# 4结语：用户驱动社会媒体的数字图书馆系统

社会媒体（SocialMedia）系统鼓励终端用户参与互联网的内容生成储存和分享。社会标签（SocialTag）允许人们对用户生成内容进行评注，从而协助信息内容的检索。由于目前的检索（Retrieval）和搜索引擎(SearchEngine）技术主要支持结构化文本、以文本为内容或者按照元数据已转化为文本等，来进行提取关联数据库内容或者提取排名算法下的网页链接等信息查询（Query）、信息搜寻（Seeking）、信息过滤（Fil-ter)、信息获取（Access）的用户行为。然而，影音内容不同于文字内容，无法进行结构化文本和以文本为内容的检索和搜索，只能按照元数据转化为文本来进行相关的信息服务：并且，影音媒体的数量十分庞大而且不断成长，如何有效地按照元数据转化文本成为信息技术未完全解决的核心问题之一。

已有的研究思路中，一种是通过机械学习的方法完成特定领域下的特定数据集的特定文本，在此基础上发展各类机械学习的方法以及检索功能和排名算法：另一种则是发展社会书签（SocialBookmark）模式.即面向所有领域的所有用户生成内容的数据集。这两种技术线路的开拓和创新，都依赖于社会媒体的实践，也都具有前沿研究的性质。

社会媒体系统不断地自我演变，新的技术和技术应用不断出现，数字图书馆在发展类似服务系统时，需要关注它的用户和脉络与传统信息系统的差异性。终端用户是“水能载舟，亦能覆舟”的最佳诠释者，数字图书馆发展这种服务模式的核心竞争力是用户行为研究。本文所讨论的播放系统、标记系统和搜索系统都是环绕在用户行为模式的分析、理解和解释，在此所建立用户驱动影音媒体服务的数字图书馆系统模型，可以作为未来研究延续、修改和批判的一项参考。最重要的是，永不放弃用户行为探索和对他们的关注。

# 参考文献：

[ 1 ] Kanc G C, Fichman R G, Gallaugher J, et al. Community Relations 2. 0[J]. Harard Busines Ratiee, 2009, $\mathbf { s } \pi ( 1 1 ) = 4 5$   
[ 2] $V \equiv \sqrt { 1 2 } \equiv \sqrt { 2 }$ ,Howe W, Dellavalle R P.Soeial Intemet Sites as a Source af Public Health Information [ J].Dermafologie Clinies, 2009, $2 7 ( 2 ) = 1 3 3$   
[ 3 ] Gueorguieva V. Yoters, MySpace, and YouTube − The Impact of Altermative Communication Channels oo the 2O06 Election Cycle and Beyond[ J]. Social Science Computer Rerier, 2008, 26 (3) ; 288 − 300.   
[ 4 ] Agnrio J, Buelley K M. An Untnpped Reaouree Using YouTube in Nursing Education[J]. Nurse Edlucator, 2009, 34(1} :23 − 28.   
[ 5 ] Xinng Z, Gretzel U. Role of Social Media in Online Travel Information Search[ J]. Tourisre Management, 2010 , 31(2) ;179 − 188,   
[ 6 ] Kim W, Jeong O R, Lee S W. On Social Web Sitee[J]. Iyfowweation Systexs, 2010, 35(2) :215 −236.   
[ 7 ] Cochrane T, Bateman R. Smart Phones Give you Wings : Pedagogical Affordances of Mobile Web 2. 0[ J]. Australesian Journal of Edncationel Technology, 2010, $2 5 ( 1 ) : 1 - 1 4$   
[ 8 ]Intermational Organization for Standardixation.ISO 13407 ; 1999 Human - oentred Design Prooessea for Iriteractive Syateme [ EB/ OL]. [2010 = 10 - 27]. $\ln ( \operatorname { I p } _ { \mathbf { p } _ { \mathrm { p } } } { \mathrm { , } } ^ { \mathrm { * } } / ^ { \mathrm { * } } { \mathrm { u r w } \mathbf { \pi } \mathbf { \pi } \mathbf { \pi } \mathbf { \pi } \varepsilon } _ { \mathrm { : } }$ is0. org/iso/catalogue_de tail. htm? csnumber $\mathbf { \lambda } = \hat { 2 } \mathbf { 1 }$ 197.   
[ 9 ] Skageby J. Gift − giving as a Coneeptual Frarmework: Framing Social Behavior in Online Networks[J]. Journal αf [nformatir Techrolagy, 2010, 25(2) :170 – 177.   
[ 10] Cheshire C, Antin J. Tbe Social Paychological EEeetx of Feedback on the Production of Intemet Information Pools [ J]. Joumol gf Campater − mediated Comemusicarion, 2008, 13 (3) ;705 − 727.   
[ 11] Kreps D. My Soeial Networking Profile; Copy, Resemblance, or Simulecrum? A Poststnacturalist Interpretation od Social Irformation Systems[ J]. Eurapean Joumal gf Iformation Systams, 2010, 19 (1):104 –115.   
[ 12] Shao G S. Understanding tbe Appeal of User - genersted Media: A Uses and Gratification Perspective[ J]， Jeferme Research, 2009 , 19(1) :7 -25.   
[ 13] Huang C N, Fu T J, Chen H C. Text – Based Video Content Clat sification for Online Video − Sharing Sites[ J]. Journaf gf rhe American Society for Irformation Seience and Technology, 2010, 61 $( 5 ) 1 3 9 1 - 9 9 5$   
[ 14] Caverlee J, Liu L, Webb S. The Social Trust Frumework for Trusted Soeial Information Managemeet: Architeeture and Algorithms [ J]. Infarmation Sciences, 2010, 180(1 ) ;95 − 112.   
[ 15] Longoria B. TubeLoc; YouTube Player AS3 Library [ EB/OL ], Fmnin 1Lu Ld/L Tr/awin/ youtube/articles/tubeloc,html.   
[16]AbhuriA,SorayaM.WorkloadGenerationforYouTube[J].MaltimediaToofsandApplications,2010,46(1）;91–118.   
[17]LegrisM．YouTubeDataAPIforActionSeript3．0；FirstSteps [EB/OL],[2010–10–27].http://code,google.com/intl/zh− TW/apis/youtube/srticles/youtube_actiorscript3.html.   
[18]KimHL,DeckerS,BreslinJC.RepresentingandSharingFolksonomieswithSemantics[J]．JournalqfIxformationScierce, 2010,36（1）：57–72.   
[19]ShiriA．AnExaminationofSocialTaggingInterfaceFeaturesand Functioralities-AnAnalyticalComparison[J]．OnlineIrformatiomRexiew,2009,33(5）:901−919.   
[20]WangJ，ClementsM,YangJ，elal．PersonalizationofTagging Systems[J]．InformationProcessingandManagemem,2010,46 (1);58−70.   
[21]FiaherJ,HartmnannJ.CreatingtheYouTube AetivityViewerApplicationUsingthePHPClientLibrary,MemcacheandjQuery [EB/OL].[2010–10−27].htp;//codle,google.cum/intl/zh= TW/apis/youtube/articles/youtube_api_activity_php.html.   
[22]ClementsM,DeVriesAP,ReindersMJT.TheInfluenceofPersonalixationonTagQueryLengthinSocialMediaSearch[J]. IrformationProcessingandManagement,2010,46{4）：403− 412.   
[23]KimHL,DeckerS,BreslinJG.RepresentingandSharingFolksonomieswithSemantice[J]．JouralofInformationScience, 2010,36(1）:57–72.   
[24]DingY,JaeobEK,FriedM,etal.UpperTagOntologyfor IntegratingSocialTaggingData[J]．JournaloftheAmericanSociety forInformationSciencrandTechnology,2010,61(3）:505−521. (作者E−mail:kuliping@ntu.edu.tw)