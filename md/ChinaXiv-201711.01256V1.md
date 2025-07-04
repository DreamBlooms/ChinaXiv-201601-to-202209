# 基于Drupal的项目网站建设以“开放资源建设”网站为例

# 董智鹏 刘静羽

(中国科学院文献情报中心 北京 100190)

摘要：【目的】利用Drupal快速搭建“开放资源建设"项目的成果管理和发布网站。【应用背景】“开放资源建设”项目需要在有限时间和技术条件下建立成果发布平台,Drupal因其灵活简易、具备强大模块支持等特点能够满足该需求。【方法】采用Drupal基本模块和扩展模块完成内容建设和页面布局，并对主题定制、网站升级中的难点问题进行处理。【结果】利用 Drupal 短时间、低成本完成"开放资源建设"网站搭建和内容建设。【结论】Drupal能够很好满足图书馆快速搭建中小型项目网站或专题服务平台的需要。

关键词：开源软件内容管理系统开放资源Drupal分类号：TP393G25

# 1引言

中国科学院文献情报中心自2013年起，以项目形式围绕开放资源的建设和再利用进行了一系列理论研究和实践探索，产生了多种类型的成果文档，积累了大量的开放资源。为了使项目成果得到及时传播，为图书馆同行提供参考，项目组需要建立专门的网站对上述内容进行有效管理和发布。但如何能在有限的时间和技术力量条件下，完成网站建设是网站建设者必须面对的问题。而目前流行的开源内容管理系统(ContentManagement System，CMS)——Drupal，以其操作简便、模块扩展功能强大等特点为此问题提供了解决方案。本文介绍了快速搭建"开放资源建设"项目网站(http://open-resources.las.ac.cn/)的方法，以及利用Drupal特色功能实现项目成果管理、内容展示等需求的过程，并验证了Drupal在支持图书馆中小型网站中的优势。

# 2Drupal在图书馆领域的应用

Drupal是基于PHP语言开放源码的内容管理系统框架，能够提供强大的模块支持，实现低成本、高效率建站和简易的系统操作[1]。Drupal 的发展与图书馆有着很深的渊源一它在2002年产生后，最早是在大型图书馆网站重建项目中得到应用。目前Drupal在图书馆中最主要的应用场景是门户网站的建设[2]。除了门户网站，Drupal还能很好支持移动图书馆的建设，如毕剑等尝试以Drupal为基础搭建云南大学图书馆移动门户网站，实现网站的响应式设计[3]；苏叶等利用Drupal+PhoneGap实现移动图书馆信息推送功能[4。从功能上,Drupal不仅能实现书目服务、用户互动等基本功能[5],还逐步向支持语义网迈进。从Drupal7 开始,RDF已成为其核心模块，能够将平台数据发布成关联数据[；夏翠娟等对基于Drupal 的关联数据发布进行了理论探讨和实践论证，任瑞娟等则探讨了如何基于Drupal实现多类型学术资源的语义化组织与关联发布[8]。值得关注的是，近年来Drupal在支持图书馆专题服务、中小型项目网站的建设方面正逐渐展现出优势，它很好地适应了图书馆员希望快速搭建网站、持续推出新服务的需要。如，刘伟针对性地提出了基于Drupal 的快速建站方案[9；加拿大西门菲莎大学利用Drupal 建立了学习共享空间预约网站[10]；牡丹江医学院图书馆基于Drupal开发了新生入馆教育网络互动学习平台[]

本次网站建设是利用Drupal建设图书馆项目网站的一次有益尝试。

# 3“开放资源建设"网站需求分析和建站思路

# 3.1 需求分析

“开放资源建设"网站的目标是集中展示项目成果，为同行提供参考。因此，从事相关工作的图书馆员是网站的主要服务对象；而项目组成员负责内容的后台发布和定期维护。这就要求网站既可以较好支持内容录入、组织和维护，又能支持用户快速定位所需资源。网站核心功能包括：文档类成果发布、11种开放资源的聚类与展示、项目动态的定期更新发布、图书馆员观点的发布等。网站核心功能如图1所示：

网站核心功能项目文档类 开放资源的 项目动态 图书馆员成果发布 聚类展示 更新 观点展示  
操作指南、学 关于开放资源11种开放资 开放资源建设  
术论文、调研 建设工作的观源的元数据 News项目进展  
报告、术语表. 点类文章

# 3.2 建站思路

本次实践充分利用Drupal"内容和页面展示分离(Model-View-Controller)"的优势，分以下三步进行：

(1）底层架构为 PHP 运行环境，启用自带基础模块和扩展模块。

(2)内容建设包括"录入"和"组织"两个环节。首先，管理员建立内容类型，采用扩展模块SmartImport或手工进行数据导入；之后借助 Taxonomy 模块建立术语表，为这些数据进行分类，或者通过手册页等对内容进行组织。

(3）通过选定主题(Theme)、Block、Views、Panels等模块进行页面布局的设计；使用SlideshowCreator模块丰富页面效果。建站思路如图2所示。

![](images/3fa2755eac4eeb49924db0233441fa3e8a2af9e46a77fffd45c97b78241719d8.jpg)  
图1“开放资源建设”网站核心功能  
图2“开放资源建设”网站建站流程

# 4“开放资源建设”网站的实现

# 4.1 底层架构搭建

开放资源建设网站采用目前稳定且应用广泛的Drupal7版本，将Drupal安装包下载解压至安装有PHP运行环境服务器中。根据需求，网站安装并启用了Drupal Core、Chaos Tool Suite、Views、Panels 等基础模块，并根据数据导人等特定需求从Drupal官方网站下载扩展模块。网站启用模块情况，如表1所示：

表1“开放资源建设"网站启用的基础模块列表  

<html><body><table><tr><td>类型(核心)</td><td>具体模块</td></tr><tr><td>Chaos Tool Auite</td><td>Chaos tools、Custom content panes、Page manager、Stylizer、Views content panes</td></tr><tr><td>Other</td><td>Entity API、Entity tokens、Libraries、PHPExcel、</td></tr><tr><td>Panels</td><td>Slideshow Creator、Vocabulary Index Mini panels、Panel nodes、Panels、Panels</td></tr><tr><td></td><td>In-Place Editor</td></tr><tr><td>Search Toolkit</td><td>Current Search Blocks、Facet API、highlight; UserLogin Bar,User Login</td></tr><tr><td>User Login</td><td></td></tr><tr><td>Bar</td><td>User Login Bar Eva、Views、Views OAI-PMH、Views</td></tr><tr><td>Views</td><td>Slideshow、Views Slideshow-Cycle、ViewUI</td></tr><tr><td>数据导入</td><td>Smart Import</td></tr><tr><td>搜索</td><td>Database search、Search API、Search facets、 Search sorts、Searchviews</td></tr><tr><td>用户界面</td><td>jQuery plugins、Superfish</td></tr></table></body></html>

# 4.2内容建设与页面展示

Drupal在网站建设方面有许多独特优势，例如,强大的模板系统能够将内容和表现分离，可以很方便地控制网站的外观；而内部结构以最简单的PHP特征实现丰富的钩子机制，使模块之间可以充分交互信息;

提供内建的新闻聚合工具RSS等。本次网站内容建设和页面设计实践充分利用了上述特色与优势。

(1）实现项目成果的有序存储和高效组织

Drupal提供按内容类型存储和组织资源的功能，因此“开放资源建设"网站根据项目成果的特点定义了内容类型，如表2所示：

表2网站内容类型及对应的项目成果  

<html><body><table><tr><td>内容类型</td><td>对应的项目成果</td><td>特点</td></tr><tr><td rowspan="2">基本页面</td><td>文档类成果(如开放资</td><td>可输入Plain Text/Full</td></tr><tr><td>源操作指南、调研报 告)、图书馆员观点</td><td>Html；可添加附件和图片</td></tr><tr><td>手册</td><td>开放资源建设News</td><td>所有内容自动按层级组织</td></tr><tr><td>开放期刊等 (共11种)</td><td>开放期刊、开放数据、 开放仓储、开放图书 等11种资源</td><td>可定义资源的元数据字段</td></tr></table></body></html>

$\textcircled{1}$ “基本页面”用来发布文本类资源，内容添加方式选用可自由编辑的FullHtml方式；同时该类型还设置了添加文件、图片等功能。

$\textcircled{2}$ “手册"可实现结构化的内容组织，展现父、子手册页间的关系。利用这一特性，本网站为每月更新的开放资源建设新闻创建一个手册页，并将它关联至上级页面"业界动态扫描”，通过这种方法实现内容的快速聚合。

$\textcircled { 3 } 1 1$ 种开放资源类型包含标题、语种、来源、学科等字段，如图3所示：

开放期刊 管理字段 管理显示 评论的字段 评论显示  
首页\*管理\*结构》内容类型》开放期刊显示行的权重标签 机读名称 字段类型 控件 操作Title title 节点模块元素+ Body body 长文本和摘要 带摘要的文本域 编辑 删除中替代名称 field_title_replace 文本 文字字段 编辑 删除中 0A方式 field_oa_fangshi 文本 文字字段 编辑 删除URL field_url 文本 文字字段 编辑 删餘出版商 field_publisher 文本 文字字段 编辑 删除中开始年份 field_startyear 整数 文字字段 编辑 删除

Drupal的重要特色之一是通过Taxonomy模块建立术语表(Terms)，为网站建立起完整的分类体系。“开放资源建设"网站以教育部的学科分类为基础，利用Taxonomy模块，11种类型的开放资源建立了包含18个一级类目和89个二级类目的“学科术语表”。该表可以直接与内容类型中的"学科"字段相关联，为资源赋予机器可读的学科属性，也为按学科生成Views提供基础。

(2）多种模块配合使用，实现页面生动展示在内容建设的基础上，开放资源建设网站使用

Panels、Views、Block以及SlideshowCreator，利用各自特点完成页面设计和内容展示。

通过Views以列表形式聚合展示具有某一特征的资源，生成的Views既可单独展示，也可成为Panel页面中的具体内容。例如，在集中展示数学类开放期刊时，新建View并为其创建页面路径，选择内容类型“开放期刊”、相应字段和筛选依据"Has taxonomyterm $\left( = \right.$ 数学)，图4所展示的即为在数学类下，RSSFeed部分代码及其生成界面。此外，在生成Views的基础上，通过添加Feed功能，开放资源建设网站为天文学、微生物学等5个学科，生成了开放期刊、开放数据的RSS，可供相关研究所图书馆员方便定制网站资源。

Displays <xnl version=“1.0"encoding=“utf-8” ?>rss version=“2.0” xnl:base="   
Page\* Feed \*添加 xmlns:content="http://parl.org/rss/1.O/modules/content/"xnlns:foaf= Content pane   
-Feed details EVA Field xnlns:sioe="http://rdfs.org/sioc/ns#"xmlns:sioct="http://rdfs.org/s Facets block <channel>   
Display name: Feed <title>数学</title> OAI-PMH Qink>http://open-resources.las.ac.cn/naths-oajournals</link>   
标题 上下文 <deseription>/deseription>   
标题：数学 区块 Qanguage>zh-hans</language)   
格式 附件 <item>   
格式：RSS Feed 页面 <title>elt;a href=aquot;/node/219aquot;agt;Abstract and Applied   
显示：Fields| 设置 Qink>http://www.hindari. con/journals/aaa</link>

通过Panels和Block快速完成页面布局设计和内容填充。Panels主要用来实现网页区域划分，定义每个区域展现的内容；Block则较为灵活，它内部可以填充内容、充当导航，同时还可自由地分布于页面的各个位置。两者配合能够达到很好的页面设计效果。在“图书馆员之我见"栏目中(如图5所示)，页面左侧导航为 Block组成，导航内容为HTML代码；右侧的上下两栏浏览界面，风格由Panels 定义，添加的内容为提前生成的"图书馆员观点”View。

图书馆 图书馆员之我见：我看开放资源建设  
·上海天文会留书馆  
国科花成都分馆 导言  
·中国科学院生物物理所 对于开放资源遮设工作，中国科学洗国家科学图书馆巴经进入研和实晚工作中，国向为科研人员服各的目标，中科洗研究所的  
图蛇员 对人个让所出的，以交融入  
·筑珠持  
·韩江  
·向桂林《推进0A新途径：放出跟光，白己去室》向挂林，中国科学洗生物物建研究所图书信息室室任，博士主要从事图书文献管理，信息情究2004年业于中国科学院文献墙报中心博士：2000年城业于石油大学（华东）计翼机科学系喷士：1900年苹业于石大学（华东）计算机科学系本科《开放资源与知识产权》韩，中国科学院成都文献管中心参与开放会认资课采与务系统研究建设，负责开放会议资课道选与数据审位，公开发实晚）2011年第34别： 《国内外着作权法驶子留事维实行开胶决职的主要理由及实

此外，网站首页还采用SlideshowCreator7.x-1.12版，实现开放获取图片的滚动播放，以增强网页展现效果。

# 4.3 技术难点的处理

(1）采用扩展模块构建新主题

Drupal系统安装完成后使用的是默认主题，但其页面风格、字体大小并不能完全满足“开放资源建设"网站的需求。因此利用Drupal的主题模块，对默认主题引擎PHPTemplate 的"filename.tpl.php"文件及代码进行改写，使之符合网站需求。

(2）采用Drush 模块简化Drupal系统升级

Drupal是由PHP语言编写的开源系统，存在安全漏洞，需定期升级。但Drupal官方文档中的升级方式都存在一定缺陷。比如，“下载最新版本并覆盖旧版”功能会造成旧代码位置更换从而导致文件混乱；再比如"下载最新版本，把自定义文件及sites目录复制至新版本并删除原有目录，整合后替换"功能会要求旧版本中配置文件需要备份，导致长时间更新后需要记录更新时要检查的文件列表，进而增加维护成本。为解决上述问题，笔者借助Drush 模块的 drushpm-update命令，对现有Drupal所有模块进行稳定版升级，大大简化了操作过程。

# 5网站建设效果分析

“开放资源建设"网站在有限的人力和技术条件下，三个月内完成网站建设。这种低成本、高效率、易操作的建站方式，帮助项目组实现了研究成果的快速传播，提升了服务的时效性。网站自投入运行以来，得到同行的广泛关注，成为展示中国科学院文献情报中心开放资源建设工作成果的窗口。网站首页如图6所示：

开放资源建设 Q search this siteA Guide for Open Resources Development  
首页开放资源建设指南|图书馆员之我见|最佳实践|开放资源建设News资源导航与指南|开放接口|关于我们|FAQ|English 退出  
导航项目最新动态  
·开放资源建设指南·开放资源建设操作指南 Hdawi与Go0A签署合作协议！（2015年9月1日） GoOA已经与五家国际开放获取出版商签署合作，开放资源评价、利用与技术 和医学 协议！指南 大部分领， 为了保障开放资源建设的可持续发展，“开放论，各类开放资源调研报告 Copemicus与Go0A签署合作协议！（2015年8月24日） 文发现和开放期刊投稿分析”平台（Go0A）项目组陆续，中国科学院开放资源问卷调 与开放取出版，得系，希望出版等查MECS与Go0A签合作协议（2015年8月14日） 的支持。目前已经有五家开放获取出版商与项目组签研究型图书馆0A服务与0A 现有ECS合作协并 订协议，为商分别作出版商、Copernicus·开放资源建设术语 eLIFE、Modern Education&Computer Science·开放资源与知识产权 页面，自时已收到该出版社所有在期数据，最新发表的交章实时推送到GoOA。 Publisher（MECS）、PsyOpen。以上出版商已为GoOA  
·开放资源 PsyehOpen与Go0A签署合作协议！（2015年7月21日） 上传超过200G数据。Psychope（TheEopeanOpeAccessPbsingPatomrPsychelegy）与GoOA签著合作协议，将为CoOA·开放期刊 定期提供期刊金文数据，日前已通过FTP上件部分渐试胶据。 GoOA系统的服务对象主要为中国科学院研究人员（包括4万名科研人员和4万名研究生），重点加强对·开放图书 高质里开放获取期刊的避选，制定了规范的开放获取期刊评价原则和方法，实现开放获取期刊和论文的集成、语义检索开放数据和统计，并提供针对作者投稿的开放获取期刊推荐。详情请登录Go0A查看。

但同时，在利用Drupal建站过程中也发现，网站功能和页面展示效果受到来自内容管理软件本身、模块功能、封装性较强等方面的限制，使得在网站样式和服务项目等方面的设计变得困难、缺乏灵活性。为了满足科研人员的需求，进一步提高网站的服务能力和价值，未来网站还需要在以下方面进行改进：

(1）提供资源定制服务。“一揽子"的资源提供方式已经不能满足科研人员的需要，因此，开放资源网站需要实现按学科向指定IP的科研人员推送相关资源，

实现个性化定制服务。

(2）开发标准化开放接口。目前网站的开放接口仅提供RSS方式，为了更好支持机器用户对资源的利用，需要考虑开发更多标准化接口，如OAI-PMH等。

(3）支持图书馆员交流。开放资源建设网站应更好地支持图书馆员在开放资源建设方面的交流以及实践案例的分享，需要加强用户交互方面的功能。目前Drupal自带的论坛模块Forum和Drupal社区中提供“表单填写"等方面的模块，都可以“为我所用”但应注意，启用这些模块会带来一定的安全风险，因此必须加强用户权限的设置与管理，对可能的风险提前防范。

此外，利用Drupal强大的模块支持，网站还将在检索功能优化、支持移动设备、页面展示丰富度等方面做出努力。

# 6结语

Drupal作为一个优秀的开源内容管理系统，与商业软件最大不同在于开源软件需要技术人员不断学习和研究软件应用方法。使用Drupal社区丰富的模块不断扩展系统功能，才能使Drupal发挥最大作用。“开放资源建设"网站体现了开源软件“自由、开放、共享"的理念，未来图书馆应进一步提升利用开源软件的技术能力，从而提升图书馆服务水平，共享学术信息，增强数字图书馆发展动力。

# 参考文献：

[1] Drupal is Open Source [EB/OL].[2015-08-24].https://www. drupal.org/about.   
[2] 王璞．利用Drupal建设Web2.0 教学参考信息管理系统[J]. 新世纪图书馆,2012(9):75-78.(Wang Pu.Construction of Software Teaching Reference System by Drupal [J]. New CenturyLibrary,2012(9):75-78.)   
[3] 毕剑，刘晓艳，张禹.使用响应式网页设计构建图书馆移动 门户网站——以云南大学图书馆为例[J].现代图书情报技 术,2015(2):97-102.(Bi Jian,Liu Xiaoyan, Zhang Yu.Using Responsive Web Design to Build a Library Mobile PortalTaking Yunnan University Library as an Example[J].New Technology of Library and Information Service,2015(2): 97-102.)   
[4] 苏叶，黄文，宋欣，等．利用Drupal+PhoneGap 实现移动图 书馆信息推送功能[J]．中华医学图书情报杂志，2014, 23(5): 76-80．(Su Ye,Huang Wen，Song Xin，et al. Implementation of Information Pushing Function in Mobile Library Using Drupal+PhoneGap [J].Chinese Journal of Medical Library and Information Science,2014,23(5): 76-80.)   
[5]秦鸿，钱国富，钟远薪．三种发现服务系统的比较研究[J]. 大学图书馆学报，2015,33(5):5-11，17.(Qin Hong，Qian Guofu,Zhong Yuanxin.Comparative Study on Three Kinds of Discovery Service System [J]. Journal of Academic Libraries, 2015,33(5): 5-11,17.)   
[6]RDF in Drupal 7 Code Sprint [EB/OL]. [2015-06-13]. https://www.drupal.org/node/443824.   
[7]夏翠娟，刘炜，赵亮，等．关联数据发布技术及其实现- Drupal为例[J].中国图书馆学报，2012,38(1):49-56.(Xia Cuijuan，Liu Wei,Zhao Liang，et al． TheCurrent Technologies and Tools for Linked Data:A Case of Drupal [J].Journal of Library Science in China,2012,38(1): 49-56.)   
[8]任瑞娟，濮德敏，王剑宏，等．基于 Drupal 实现多类型学 术资源的语义化组织与关联化聚合[J].情报科学，2015, 33(5):63-67.(Ren Ruijuan,Pu Demin,Wang Jianhong,et al. Realizing Semantic Organization and Linked Polymerization of Multi-type Academic Resources Based on Drupal [J]. Information Science,2015,33(5): 63-67.)   
[9]刘伟．基于 Drupal 的专题服务网站开发研究[J]．电脑知识 与技术，2014，10(14):3293-3296.(Liu Wei.A Study on Drupal-based Special Services Website Development [J]. Computer Knowledge and Technology, 2014，10(14): 3293-3296.)   
[10]Student Learning Commons [EB/OL]. [2015-10-30]. http:// www.lib.sfu.ca/about/branches-depts/slc.   
[11]王琳琳，张旭，宋欣，等．基于Drupal 的图书馆新生入馆 教育平台[J]．中华医学图书情报杂志，2013，22(7):70-71, 78.(Wang Linlin, Zhang Xu, Song Xin,et al.Drupal-based Library Entrance Education Platform for New Recruits [J]. Chinese Journal of Medical Library and Information Science, 2013,22(7): 70-71,78.)

# 作者贡献声明：

董智鹏：设计并实施研究方案，论文撰写及最终版本修订;  
刘静羽：参与实施研究方案和论文撰写。

收稿日期:2015-07-14   
收修改稿日期:2015-10-20

# Project Website's Construction Based on Drupal A Case Study of “Open Resources Development" Website

Dong ZhipengLiu Jingyu (National Science Library, Chinese Academy of Sciences,Beijing 10o190, China)

Abstract: [Objective] Construct the project website of the“Open Resources Development” to manage and distribute the project's fruits using Drupal.Context] The project of “Open Resources Development” needs to build upa project fruits distribution platform with the limited time and technical conditions.And,Drupal cansatisfy these needs for its flexibility and simplicity.[Methods]Using both the basicand extent models of Drupal,construct the website from two aspects ofdata layer and presentation layer.Also,solve technical key problems in theme design and websiteupgrade. [Results] Complete the website construction and content developmentusing Drupal in a short timeand with alow cost, timely releasing the project fruits.[Conclusions] Drupal can wellsatisfy the needs from librarians ofconstructing small websites of projects or the service platform.

Keywords: Open software CMS Open resources Drupal

# OCLC研究中心和ALISE公布2016年图书馆学情报学研究资助名单

OCLC研究中心和美国图书馆学情报学教育协会(Asociation for Library and Information Science Education,ALISE)已经资助由10个研究员主持的5个研究项目。这一资助名单是在2016年1月7日于波士顿举行的ALISE年会颁奖午宴上公布的。这5个研究项目分别是：

(1）威斯康星大学密尔沃基分校的Iris Xie和Rakesh Babu将调查研究数字图书馆的普遍利用问题，还会设计供盲人用户使用的帮助机制。该项目不仅提供帮助了解盲人用户的求助行为的理论研究成果，同时提供一个迭代设计可供盲人用户更好地进入和使用的实际应用成果。(2）利默里克大学的Abdulhussain Mahdi和Arash Jorabchi将开发一套算法，这一算法可以将FAST主题词自动映射到相应的维基百科文章或主题。这一映射算法采用多种文本挖掘技术，如字符串匹配、明确的语义分析和引文分析，以便为给定的FAST主题找到最好的匹配文章。(3）佛罗里达州立大学的Besiki Stvilia,德州农工大学的Dong Joon Lee和纽约市立大学皇后学院的Shuheng Wu将调查研究网上研究身份管理系统的社会方面参与情况。从这项研究结果中，可以得知研究身份数据/元数据模型的设计、数据质量保证措施、招募和聘请维护身份数据研究人员的机制。(4)北京大学的张鹏翼将调查研究在线知识群体的协作意义建构。这一研究试着解答这一问题：在线知识小组参与协作任务的人们如何协作构建知识结构？如何协作填充数据到知识结构中？拟议的研究将推动协作意义建构的理论认识和实证研究，以及为意义建构技能教育提供指导。(5）密苏里大学的Denice Adkins和Heather Moulaison Sandy将查明拉美裔人口如何利用移动技术进行信息搜索，如何使用社交媒体进行信息搜索，并且如何根据这些知识，打造针对各种拉丁裔社区(农村、城镇、建立社区、新人社区等)的可用于图书馆定制其社交媒体和移动信息活动的配置文件”。

全球范围内高校的图书馆和信息科学部门的全职学术研究人员(或相等职位的人员)都有资格申请高达15 000美元的研究经费。申请书是由OCLC和ALISE所遴选出的小组共同进行评估。所资助的项目预计在受资助之日起一年之内完成，作为资助条件之一，研究人员必须在资助期结束之后提供一份该项目的最终研究报告。更多的关于OCLC/ALISE图书馆和信息科学研究资助项目可以在http://ww.oclc.org/research/grants.tml中找到。之前资助的名单也可通过http://ww.oclc.org/research/grants/awarded.html访问。

(编译自:https://www.oclc.org/news/releases/2016/201603dublin.en.html)

(本刊讯)