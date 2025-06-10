# 移动校园平台支持下的高校移动图书馆建设研究

以微哨平台为例

# 孙荣

(江苏师范大学信息网络中心 徐州 221116)

摘要：【目的】创建基于移动校园平台的移动图书馆应用，使读者能够便捷地获取图书馆的信息和服务，进而拓展图书馆服务渠道。【应用背景】随着智慧校园建设的深入，各高校纷纷建设移动校园平台，为图书馆拓展服务渠道带来新的契机，然而却鲜有高校涉足此领域。【方法】通过对现有图书馆业务系统开放接口、接口扩展的方法，向移动图书馆用户提供相关业务的查询与办理，并借助微哨的平台化功能、API接口，提供完善的移动图书馆服务。【结果】开发基于微哨平台的移动图书馆微门户，实现用户身份验证、资源检索、我的图书馆、信息展示、信息推送等功能。【结论】基于微哨的移动校园平台构建移动图书馆，符合当前高校移动校园建设的趋势，可被广泛应用。

关键词：移动服务 移动图书馆 移动校园平台微哨分类号：G250.76

# 1引言

在移动互联网技术飞速发展，大屏智能终端逐步普及的背景下，我国高校移动图书馆发展势头迅猛，移动图书馆服务形式也日趋多元化[1]。

为了解目前国内高校移动图书馆服务现状，笔者选取39所"985"高校图书馆作为调查对象进行网络调研。调研数据显示：短信(SMS)、WAP、APP、微信公众号是目前高校图书馆提供移动服务的主要形式[2];高校非常重视移动图书馆的建设，仅有两所高校没有提供移动图书馆服务；微信公众号是最受欢迎的服务形式，占 $8 5 \%$ ；高校图书馆重视移动服务形式多元化，有15所高校图书馆同时采用三种形式为用户提供服务;目前没有高校图书馆基于移动校园平台提供服务。

笔者认为，图书馆服务创新不应受已有形式的限制。在高校移动校园平台建设初显成效的背景下，高校图书馆应积极融入校园移动生态圈，利用移动校园平台为用户提供服务，进一步拓展用户服务渠道。

# 2建设方案

# 2.1校园移动平台的优势

近些年，随着移动互联网的飞速发展，我国许多高校开始着手建设移动校园平台，打造移动校园生态圈。众多厂商也纷纷推出了相应的产品，其中代表性产品有锐捷网络公司的"微哨”、金智教育的"移动校园MCP”苏迪科技的"微迪"等。那么移动校园平台究竟在校园中能发挥什么重要作用呢？笔者认为：移动校园平台是校园用户获取校内各类移动服务的入口，校内用户只需要安装一个APP，便可获得校园内与工作、学习、生活相关的服务，避免用户每获取一类服务就需要安装一个APP的不便；移动校园平台上发布的各类应用,采用与第三方厂商系统对接的模式，轻松实现校园内各类应用系统的移动化改造。同时，由于平台的开放性，学校也可引入第三方软件，解决学校开发能力不足的问题[3]。

因此，笔者认为基于校园移动平台，建设移动图书馆，为用户提供服务，是未来高校移动图书馆服务模式的一个发展方向。这种模式基于现有的校园移动平台客户端，无需单独安装APP,推广难度较小。基于轻应用，与图书馆现有业务系统对接，开发难度相对较小。与微信公众平台相比，由于校园移动平台的私有特质，用户获取移动图书馆服务的优先级相对较高。基于这样的私有平台推送消息，不会和其他公众信息混杂，相对于微信模式也会有更高的信息到达率。

# 2.2 微哨平台的价值

微哨(Whistle)是一款具有通知系统、即时通讯、校园社交、平台化功能的校园移动平台。微哨采用私有云与公有云结合，实名制的部署方式，相比微信公众号等公有云应用，无需绑定学号、工号，更加安全与便捷[4]。基于微哨移动校园平台探索移动图书馆服务新模式，对于图书馆拓展用户服务渠道具有积极的意义和价值，主要体现在以下方面：

(1）强大的消息通知体系。微哨消息通知体系完全基于校园真实身份，安全可靠。在真实的组织架构体系之下，图书馆可以较为容易地给特定的群组或个人精准推送消息，避免信息到达率不高的问题。图书馆还可以基于微哨通知接口，使用程序自动发送提示信息，可用于图书到期提醒、订阅推送等场景。

(2）丰富的API接口。现在微哨平台已向用户开放的接口主要有单点登录、组织结构、轻应用、通知系统、二维码扫描等。图书馆可以利用API接口与现有业务系统对接，快速创建移动图书馆应用，为用户提供服务。

(3)较低的开发难度。微哨具有整合校园应用业务接口、数据接口的能力，大大降低了开发难度。用户只需懂得HTML5语言，再配合微哨JSSDK，就可以用最简单的方式开发出与Android、iOS一样功能强大的原生应用。

(4）清晰的运营数据。微哨云端的管理后台为各级别的管理者提供了详尽的运营数据，方便服务提供者了解运营状况，从而及时调整运营策略。这些数据包括应用订阅情况、应用访问情况、应用访问记录、通知阅读情况等。

# 2.3 建设思路

基于微哨平台的移动图书馆微门户(简称“图书馆微门户"是构建于数字图书馆现有系统、数据之上的，借助微哨平台的通知体系与开放接口，将传统桌面级服务有机地转换为移动服务。笔者给出的建设思路如图1所示：

![](images/1f54207c771a71d45aa5305ac2cc866a7842a064f37162aa8d59afebcb1c9734.jpg)  
图1基于微哨的移动图书馆建设思路

(1）数据层是数字图书馆的现有各种结构化、非  
结构化数据，传统数字图书馆门户和移动图书馆中  
向用户提供的服务与资源都源与同一个数据层。(2）软件平台层基于微哨移动校园平台搭建，包  
括图书馆微门户等各类校园移动应用运行于此平台。(3）服务层是以图书馆微门户的形式向读者提供  
服务，如我的图书馆空间、OPAC、消息推送、新闻公

告等。图书馆微门户中所提供的功能，并不需要单独开发，通过与现有数字图书馆业务系统开放接口或者接口扩展的方法，便可向读者提供相关业务的查询与办理[5]。

# 2.4 运营机制

以读者和管理者使用视角的移动图书馆运营机制如图2所示：

![](images/b0f760424f32954addb5784c988828459c6854234062d39a595d4c4e546fe3ef.jpg)  
图2基于微哨的移动图书馆运营机制

读者登录微哨客户端，自动获得身份验证，无需输入用户名和密码直接访问图书馆微门户，获取图书馆服务。图书馆员经过微哨平台管理员的授权，可以登录微哨管理后台，获得通知管理(包括图文消息)、群组管理、群聊管理、权限管理、运营管理等权限，进行运维管理。图书馆微门户程序也可调用微哨平台提供的通知API接口，将一些重要的提示信息(诸如图书超期提醒、图书预约到馆等信息)自动发送给用户。

服务器上。使用PHP语言，MySQL数据库以及HTML5、CSS3等技术开发程序。图书馆微门户UI采用扁平化的设计风格，色彩方案清新、活泼。结构上采用单栏式瀑布流设计，简洁明晰。页面布局按功能从上而下设置为搜索区、消息提示区、菜单导航区，整体效果如图3所示：

# 3具体实现

# 3.1 图书馆微门户搭建

图书馆微门户搭建开发工作需要在微哨云端管理后台与私有服务器上分别进行。

(1）在微哨云端管理后台，需要申请一个轻应用,获取唯一标识(App Key)和通讯秘钥(Secret Key)，将这两个Key数据应用在图书馆微门户程序之中。这样微哨平台才能够正确鉴别应用的合法身份，从而确保应用来源的可靠性，防止被伪造。

(2）图书馆微门户程序部署、运行在学校的私有

![](images/91cc206de978926abee45308c3ec573d30f3d874b72d3ec01bff0c5a8b3eb569.jpg)  
图3移动图书馆微门户页面

# 3.2 用户身份验证

微哨平台是移动校园的底层平台，在部署伊始就需要与数字校园统一身份认证系统进行对接，确保微哨平台上运行的各类校园应用都能获取用户的真实身份信息。实现方法是在微哨服务器和数字校园统一身份认证服务器之间建立通信机制，统一身份认证服务器开放可读权限，允许微哨平台读取用户信息。用户首次登录微哨时，提交自己的数字校园统一身份认证用户名和密码，微哨系统比对用户提交的信息与统一身份认证系统中获取的信息是否一致。如果信息一致，微哨系统认为用户通过验证，并从校园统一身份认证系统中获取用户合法身份信息[4]。这样用户在使用移动图书馆应用时就无需额外绑定身份信息，无需额外记忆用户名密码，轻松享用移动图书馆的各类功能应用，大大提升了用户体验。

# 3.3 资源检索

资源检索主要包括图书馆馆藏书目检索、电子书库检索、电子期刊检索等。在Web环境中实现各类资源检索比较简单，只需要利用图书馆各类查询系统提供的搜索接口，就可以实现查询的目的。但是对于移动终端用户来讲，无论从屏幕尺寸，还是从流量等角度考虑，将PC 端页面搜索出的内容字段全部显示出来，都是极不友好的[。因此，需要通过转码技术，将搜索结果通过程序进行筛选，有选择性地呈现必要字段，重新以适合移动端阅读的形式展示给用户。以OPAC为例，实现的方法与步骤如下：

$\textcircled{1}$ 利用程序，设定参数模拟登录图书馆OPAC系统，获取相应页面数据，以字符串的形式获取所有字段。

public string simulateLogon(string url,array arr){}

$\textcircled{2}$ 分析定位字段信息。

public int locateString(string sourceString string aimString, int order){}

以获取书本名称字段为例，人工分析书本名称所在的HTML 标签"<liclass $\vDash$ "book_list_info">人类简史》/li>"，然后通过“locateString( $\mathrm { ^ { \circ } { < } l i }$ class $\ c =$ "book_list_info">'，1)”定位"<li class $\ c =$ "book_list_info">"在页面中出现的位置。

$\textcircled{3}$ 获取所需字段信息，截取出必要字段，如图书名称、作者、出版社、索书号、馆藏地、图书状态等。

public string locateString(string sourceString,int start,int end,int order){}

$\textcircled{4}$ 将获得的字段信息以适合手机用户阅读的方式，在HTML中重新排版给用户，以此提升用户体验。

实现效果如图4所示。

![](images/378bd3b6b8b6e76036ad5a413191bd9898ece58c62757101b5452881604569de.jpg)  
图4馆藏资源搜索页面

# 3.4 我的图书馆

“我的图书馆"是数字图书馆业务系统所提供的基础服务，通过“我的图书馆"界面，用户可以查看证件相关信息，当前借阅与历史借阅情况，也可以办理图书续借、证件挂失等业务。目前大多数图书馆业务系统数据库出于数据安全以及商业上的原因，都不提供开放的接口，一般只提供简单的数据导入、导出功能。那么在移动图书馆中想为用户提供图书借阅查询、图书续借、证件挂失等服务，就必须对现有系统进行接口扩展，在不改变现有系统结构和功能的前提下，通过接口的扩展，达到与其他系统进行数据交换和应用整合的目的[7]。笔者采用Web Services 扩展的方式创建公用接口层，通过指定IP地址可访问的方式，向移动图书馆应用程序授权，使其能够对图书馆信息系统中的数据进行读写操作，系统扩展结构及原理如图5所示。

证件信息、借阅记录、续借、挂失等功能相对应的系统扩展接口实现方法如下：

$\textcircled{1}$ public array getUserInfo(string userid){}

根据用户的标识信息，进而获取用户身份信息，如姓名、学院、班级、性别等。

$\textcircled{2}$ public array getHistoryList(string userid){}

根据用户的标识信息，获取用户的图书借阅历史记录，返回数组。

$\textcircled{3}$ public bool renewBook(string userid, string bookid){}

根据用户以及所借阅图书的标识信息，续借固定时间，续借成功返回True，否则返回False。

$\textcircled{4}$ public bool lossCertificate(string userid){}挂失借书证件，成功返回True，否则返回False。

![](images/684bb59d317ba5517f24f7f66466d8b4aaf4748200e73993eeee749a7d796217.jpg)  
通过IP地址访问许可,获取扩展接口授权

我的图书馆页面效果如图6所示：

![](images/12ecb1d3dcfe6230e9cabf1fdc6588ab6a37b492c69f331c774e387461689b3b.jpg)  
图5图书馆业务系统扩展接口结构

$< / \mathrm { a } > < / \mathrm { l i } >$ $< \mathrm { l i > < a }$ href="#' $^ { 1 > }$ 本馆概况 $< / \mathrm { a } > < / \mathrm { l i } >$ $< \mathrm { l i > < a }$ href="#">读者导航 $< / \mathrm { a } > < / \mathrm { l i } >$ $< \operatorname* { l i } > < \operatorname { a }$ href="#">服务指南 $< / \mathrm { a } > < / \mathrm { l i } >$ </ul> <!--导航菜单，此处省略二级菜单 $\mathrm { . . } >$ </div> </div> </nav>

# 3.5 信息展示

信息展示模块主要用于向用户发布图书馆概况、新闻公告等信息。本文不再单独建设CMS系统，而是引入成熟的前端框架Bootstrap，对数字图书馆门户中的相应内容进行响应式布局改造，使之适应在手机等移动终端的显示。改造后的页面效果如图7所示。

$\textcircled{1}$ 可隐藏的折叠菜单。改造后的部分代码如下   
<navclass $\mathrel { \mathop : } \mathbf { \Gamma }$ 'navbar navbar-inverse navbar-fixed-top"> <divclass="container"> <divclass $\scriptstyle \mathbf { \mu } _ { \mathbf { \mu } _ { \mathbf { \lambda } } } = ^ { \prime }$ 'navbar-header"> <button class $\mathrm { ; } \mathbf { - }$ 'navbar-toggle"data-toggle= "collapse"data-target="#responsive-navbar"> <spanclass $\mathrel { \mathop : } = \mathrel { \mathop : }$ 'icon-bar"></span><spanclass $\ c =$ "icon-bar"></span><span class $\scriptstyle \mathbf { \mu } _ { \mathrm { { s } } } = \mathbf { \Lambda }$ 'icon-bar"> </span></button> <!--折叠菜单按钮--> </div> <divclass $\mathrel { \mathop : } \mathbf { \Gamma }$ collapse navbar-collapse" id="responsive-navbar"> <ul class $\mathrel { \mathop : } \mathbf { \overline { { \Gamma } } }$ 'nav navbar-nav"> <liclass $\mathrel { \mathop : } \mathbf { \Gamma }$ 'active' ${ \mathrm { > } } { < } \mathbf { a }$ href="#">移动图书馆

![](images/f91d98a1aca962b2065c47e46a16bf1a6a86ae4ea5fd124b2c522065a9438bf5.jpg)  
图6我的图书馆页面  
图7手机端呈现的页面

$\textcircled{2}$ 页面结构布局改造。具体做法是引入HTML5、CSS3.0媒介查询(MediaQueries)技术，设置手机等小屏幕智能终端0 $@$ media screen and (min-width: $3 2 0 \mathrm { p x } )$ )访问的信息内容div为单栏设计，百分比弹性布局，使手机等移动终端获得良好的访问效果[8]。

# 3.6 信息推送

图书馆微门户推送信息主要有两类：

(1）微哨客户端自带的消息发送功能，用户与用户之间可以通过消息功能进行线上交流。作为服务机构的图书馆也可以通过消息群发功能，将精心编辑的专题信息、重要信息通过图文消息的方式群发给特定用户群体，类似微信公众号推送的内容。

(2）数字图书馆系统程序所产生的提示信息，包括图书到期提醒、超期归还提醒、预约图书到馆提醒等。通过移动图书馆应用程序，调用微哨系统的消息推送接口，主动推送到微哨客户端。这样用户即使没有正在使用微哨，也可以收到系统的精确提醒。两类信息推送方式提高了消息到达率，确保用户能够及时看到重要信息。

读者接收到的推送信息效果如图8所示。当用户接收到消息后，也可以选择分享到QQ、微信等社交媒体。读者在社交媒体上看到其他读者分享的信息如图9所示。

![](images/c6a1489074a04ff5b8b3b2f0852864e27315ca15c49faf65d92f83a9f9be9064.jpg)  
图8通知在微哨客户端显示效果

![](images/eaa1d5312ed56e73ed0294bbf50eb5a6a15e89644a4a34388f05eb6b191f839a.jpg)  
图9分享到其他社交软件显示效果

经过两个月多月的试运行，图书馆微门户得到了

# 4试运行效果

师生读者的广泛关注。微哨云端管理后台的运营数据显示：总PV(使用次数)为4311，总UV(独立使用用户数)为3517。读者在应用中心给图书馆微门户的评价等级为4星，好评率 $8 1 . 6 \% _ { \odot }$ 同时读者也留言反馈使用感受，并提出意见与建议。笔者对读者的反馈进行梳理：大家普遍认为在校园移动门户上就能够办理图书馆业务，非常方便，特别是图书超期提醒等功能特别贴心。大多数建议集中在图书馆微门户所提供的功能与网页版图书馆门户类似，希望能够提供更为丰富的功能。这一点也印证了运营数据PV、UV值过于接近,用户使用频率不高的问题。图书馆微门户在功能上还有进一步提升与完善的空间。在以后会陆续增加一些功能，诸如自习室座位预约、馆情通报等，籍此提高应用的用户黏度。

# 5结语

目前，移动网站(WAP)、移动应用(APP)、微信公众号(WeChat)等多种方式并行是诸多高校图书馆采用的移动图书馆服务模式，可以适应不同目标人群的需要。本文探讨的基于微哨这样的移动校园平台构建移动图书馆，符合当前高校移动校园建设的趋势，为高校图书馆用户提供了新的选择，是对移动图书馆服务模式的拓展与补充，具有一定的实践意义。

# 参考文献：

[1]刘悦如，郭利敏．微信公众号互动功能新开发[J]．现代图 书情报技术,2015(11):104-109.(Liu Yueru,Guo Limin.The NewUtilizes of WeChat Platform with Interactive Functions [J].New Technology of Library and Information Service, 2015(11):104-109.)   
[2] 李臻，姜海峰.图书馆移动服务变迁与走向泛在服务解决 方案[J].图书情报工作,2013,57(4):32-38.(Li Zhen, Jiang Haifeng.ChangesofLibrary Mobile Service and Solutions of Building Ubiquitous Services [J].Library and Information Service,2013,57(4):32-38.)   
[3]王磊，张涛．基于“应用驱动，开放共赢"的高校移动校园 生态链的构建[J]．现代教育技术,2015,25(3):69-75.(Wang Lei，Zhang Tao.The Construction of Ecological Chain of Mobile Campus Based on“Application-driven,Open-win"[J]. Modern Educational Technology,2015,25(3): 69-75.)   
[4]孙荣，王正路．微哨支持下的高校实验室开放服务系统建 设[J]．实验室研究与探索，2015，34(12):233-237.(Sun

Rong， Wang Zhenglu. A Study of Constructionof Whistle-based University Open Lab Service System [J]. Research and Exploration in Laboratory，2015,34(12): 233-237.)

[5]林颖，孙魁明．基于WAP的图书馆移动信息服务体系及 WAP OPAC应用实例[J]．现代图书情报技术，2007(9): 80-83.(Lin Ying,Sun Kuiming. Infrastructure of a Library Mobile Information Service Based on WAP and the Prototype ofWAP OPAC System[J].New Technology ofLibrary and Information Service,2007(9): 80-83.)

[6] 罗涛，朱莹．基于WAP的移动图书馆的研究与实现——以 东南大学图书馆为例[J].图书馆杂志，2013，32(8):66-71. (Luo Tao,Zhu Ying．The Research and Construction of Mobile Library Based on WAP: Taking the Southeast University Library as an Example[J].Library Journal,2013, 32(8):66-71.)

[7]伍玉成，朱锦泉．基于 SOA 和Web Services 架构高校数字图书馆数据集成研究[J]．情报科学，2012，30(7):1030-1033.(Wu Yucheng，Zhu Jinquan.Research on DataIntegration Based on SOA and Web Services in the Digital

Library of University [J]. Information Science,2012,30(7): 1030-1033.)

[8] 毕剑，刘晓艳，张禹.使用响应式网页设计构建图书馆移动门 户网站——以云南大学图书馆为例[J].现代图书情报技术, 2015(2):97-102.(Bi Jian,Liu Xiaoyan,Zhang Yu.Using ResponsiveWebDesignto BuildaLibraryMobile Portal—Taking Yunnan University Library as an Example [J]. New Technology of Library and Information Service,2015(2): 97-102.)

# 利益冲突声明：

作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据见期刊网络版http://www.infotech.ac.cn。  
[1]孙荣.985lib.xlsx.985高校移动图书馆建设模式调查表.

收稿日期:2016-05-16  
收修改稿日期:2016-06-20

# Building Library APP with Mobile Platform on Campus Case Study of Whistle Platform

Sun Rong (Information & Network Center, Jiangsu Normal University, Xuzhou 221116, China)

Abstract:[Objective] This study develops an APP for the academic library based on the mobile campus platform, which helps patrons obtain library informationand services convenientlyand then expands the services remarkably. [Context] With the progressof smart-campus technologies,higher education institutes started tobuildtheirown mobile campus platforms.However,few libraries utilized this new platform to serve their readers.[Methods]The proposed APP opened interface and interface expansion of the existing library system to provide library services to the mobile patrons,with thehelpofthe Whistle platform.[Results]The proposed APP established amobile library for the users .It could authenticate library patrons,search/check-out librarycollection,build personalized library,postannouncements and send out information.[Conclusions] Developing library APPs based on the mobile campus platform (i.e.Whistle) mirrors the latest developments of higher education institutions.Academic libraries could become leading players in this field.

Keywords: Mobile serviceMobile libraryMobile campus platform Whistle