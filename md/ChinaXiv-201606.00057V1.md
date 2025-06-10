# 开放知识元库研究 \*

# 顾立平

（中国科学院国家科学图书馆北京100190）

【摘要】描述开放情境感知系统的需求和瓶颈,简要介绍目前开放链接、链接解析器、知识元库和数据库平台的交互运行机制,着重开放知识元库的元数据、协作方式与数据可能性。最后讨论开放知识元库的延伸应用。

【关键词】知识起点知识标的知识标的服务知识对象对象配置知识组织分层缝合无缝链接【分类号】G255.75

# Research on the Open Knowledge Base

Ku Liping

(National Science Library，Chinese Academy of Sciences，Beijing 1OO190，China）

PAbstract】The articledescribes the needsand the botlenecksof theopencontext-sensitive system，and briefly introduces the currnt interoperation between the OpenURL,the link resolver，the knowledgebaseand the database platforms. The studyfocuses on theopen knowledgebase's metadata，cooperationand opportunityFinally，it discusses the extended application of the open knowledgebase.

Keywords】Knowledge sourceKnowledge targetKnowledge target serviceKnowledge objectKnowledge portfolio nowledge organization levelsLink - to inbound linking

# 开放情境感知系统的需求和瓶颈

G5000757570:51155011

面对各种类型的数据库系统,处理电子资源,特别是电子期刊文献资源的方式很多,整合众多系统而提供一系统的系统（Systemof systems，SoS)是数字图书馆的主要发展轴心，其主要方式有：

（1)在图书馆自动化系统（Automative Library System，ALS）或者图书馆集成系统（Integrated Library System，ILS)上管理,例如 856 字段上加入若干期刊出版商的网址;（2）建立电子资源管理系统（E－Resource Management System，ERMS）,独立但是配合ILS 而存在;(3)建立一个较大的索引,其中包括各个数据库的位置、账号密码和检索路径,即传统的整合查询系统;(4)通过链接解析器,建立动态数据库网络体系,即情景感知系统（Context-Sensitive System，CSS）或者智慧链接系统（SmartLinkingSystem，SLS）；（5）提供包括各个数据库元数据内容的超大型索引,即知识发现平台（Knowledge Discovery Platform，KDP）或者广域书目系统（Meta－Bibliography System，MBS）[1]等。

其共性是解决不同数字资源系统互操作以进行资源整合与传递。

其中,情景感知系统包括三个主体,即开放网址（OpenURL）、链接解析器（Linking Resolver，LR）和知识元库(Knowledge Base，KB）。这种模式可以协助电子期刊供应链改进其工作效能,有效地与其他数据库交互,改进用户的访问体验和访问时间[2]。其开创性研究是 Van de Sompel[3-5]在根特大学的博士论文及其1999 年发表的三

篇论文，一反过去数据库只能够以静态方式呈现双向链接的做法，采取动态更新链接并且能够执行多方链接的功能[]。在2001年Beit－Arie[7]解决“适当副本（AppropriateCopy）”问题（例如，图书馆支付认购使得用户有权访问各种版本，然而用户不一定能够知道他能够访问的多个版本，或者各自独立的系统无法集中呈现各种版本以供用户比较和选择)之后，该技术愈加成熟并且影响美国国家信息标准协会在2004年所发布的OpenURL1.0 规范[8],以格式化统一资源标识符（UniformResourceLocator，URL)使用标准。

情景感知系统有4个优势：充分应用订购的元数据，增进文献使用率；协助馆员管理不同架构下的异质数据库；支持有限人力下的文献传递服务；协助读者  
筛选“有权"(图书馆订购)使用的资源，方便检索和利  
用。对此,国内已有许多研究,例如介绍 SFX系统[0]绍如何整合网络资源["]、介绍封闭、静态和开放动态链接系统[12]、基于OpenURL 的开放链接框架[13]、  
服  
的产品比OPC作  
流程[21]、OpenURL的历史发展[22]、比较 Z39.50和OpenURL 协议和协作[23.24]、SFX 与 GoogleScholar 的协[27-34]、SFX的特点介绍[35]、数字资源的参考链接模  
型[3-38]、数字资源导航研究[39,40]数字图书馆的门户  
与统一检索[41-45]、知识服务应用[46]、电子期刊数据导入自动化系统书目[47]、用户使用数据分析[48]以及根据用户使用数据评价开放获取期刊[49,50]等。

然而，对于情景感知系统，上述研究除了文献[47]以外，均环绕开放网址（OpenURL)和链接解析器描述，缺乏知识元库的探讨。近年来，正是因为知识元库引发的种种问题而导致开放知识元库的兴起。

# 2 当前情境感知系统的机制和问题

情境感知系统的信息流程是：用户在知识起点(S)看见一篇文献，选择S上的情景感知系统(CS)启动无缝链接弥合（LS），调动无缝链接机制（IL），其元数据(M)依据开放链接语法(OpenURL)传输到链接解析器（LR），链接解析器分析语法后，查询知识元库（KB），如果知识元库中存有这篇文章，则提供文章级别链接（ALL），反之提供标题级别链接（TLL），到达知识目的(T)。此外，在知识元库之后的动作可以根据定制（C）而有不同的途径。参考KBART（KnowledgeBase And Related Tools)工作报告[51]的定义,描述此流程的相关组件如下：

（1）知识起点（Source，S）：创建一个能够被链接  
解析器链接的资源,可以理解为整个网站（数据库、出  
版商平台等)或者一个具体引用源。（2）情景感知系统（Context Sensitive，CS）：情景敏  
感意味着通过用户情景决定的链接目标。（3)无缝链接缝合（Link-to Syntax，LS）：链接到  
一个能够被URL 结构化以及具有识别符字串的网站  
的特殊网页公式,必须依靠内容供应商遵循OpenURL  
语法，才能开启无缝链接。（4）无缝链接(Inbound Linking，IL）:从其他在线资  
源到一个网站的链接。内容提供商启用无缝链接，公开  
自己网站的多个层级的网页网址（如期刊主页、内容列  
表或者具体文章),让其他人可以使用无缝链接集合。（5)元数据（Metadata，M)：描述数据的数据。对  
一篇文章而言，是指它的标题、作者姓名、期刊刊名以  
及卷期、刊期、文章或者页面的页码等。（6)开放链接语法（OpenURL）：特指从信息资源  
（知识起点)到一个机构解析器，然后到图书馆服务  
(知识目的)传输元数据的语法。（7）链接解析器（LinkResolver，LR）：链接解析器  
或者链接服务器（Link Server)是一套解析OpenURL 的  
软件,能够分离出描述用户所提问（Request)文章的元  
素，并且创建一条通过用户的图书馆定义的适当服务  
（Appropriate Service（s））的可预见链接。（8）知识元库（KnowledgeBase，KB）：受到知识元  
库开发者所编译、分发、维护的庞大数据库，其有关电  
子资源的信息例如标题列表、覆盖日期、无缝链接等;  
知识元库能够依据个别机构所反映的所在地典藏而定  
制，例如能够被访问的电子资源的标题以及图书馆所  
拥有的纸本资源等,通常与本地知识元库相对应。（9）文章级别链接（Article-LevelLink，ALL）：用  
户直接指向他们所寻求的文章网址，而不是发表文章  
的出版物、卷期或者刊期。（10）标题级别链接（Title-LevelLink，TLL）：用

户直接指向他们所寻求的出版物的网址，而不是特定的卷期、期刊或者文章的网址。

（11)知识标的（Target，T）：连接到链接解析器的资源，包括出版平台和机构目录的内容或者机构知识库和内容网关（一个开辟用户访问全文而不持有全文的网站，例如对用户进行验证并引导他们到出版商网站获得全文的订阅代理网站）。

（12）定制（Customization，C）：为对照链接解析器的全球知识元库与本地典藏和服务，由机构定制信息所设定的过程，包括：馆藏限制、服务类型、部门或者组别的访问设定等，通常也称“客制化”或者“本地化（Localization）”。

如果在整个信息流程中出现某个环节错误，则整个服务就会停止或者效果大打折扣。那么，最容易出见的关键问题是什么？

这个问题涉及到情境感知系统的设计理念，为了解决不同数字资源系统互操作问题，5种主流方式中：图书馆自动化系统只涉及标题级别链接，而不涉及文章级别链接,服务范围小而能够控制;电子资源管理系充提供资源清单而不涉及动态链接;传统的整合查询系统基本上是一种静态开放系统,不提供多向链接;广或书目系统收割所有元数据内容，其目的是提供完整索引;情景感知系统的目的是走向多方（多个平台参与戎为S和T）、开放（S遵循OpenURL语法而其M能被R分析）动态（KB元数据更新）。所以，早期主要是和T的参与数量，而后期问题就出现在KB。

# 3 开放知识元库的建设

当初VandeSompel为解决数据库孤岛的问题，就静态与动态的连接以及封闭与开放的连接框架进行研究，解决“适当复制的问题（AppropriateCopy Prob-lem)”。然而正如他所言，“对用户而言，它链接的是二级资源、目录、一级资源的逻辑关系（Logically Relat-ed）,而不是功能链接（Funcationally Linked）”[3]。10年前所发展的OpenURL链接解析器具有开放、情景敏感、适当索引以及资源和服务的抽象联动等特性，因此，图书馆读者比以往任何时候都更能获得更为全面的学术信息。然而，依赖OpenURL的链接解析器技术后,读者仍然感到挫败[50]

这是因为20世纪90年代末从静态的、双边的动态参考链接转移为动态、多边的链接解析器已经日益超载。目前OpenURL1.0是一阶问题解决方案，解决二阶OpenURL模型中的固有问题是完善OpenURL元数据发送的链接解析器的质量以及提高馆藏信息的知识元库的质量。至于OpenURL模型中的第三个问题即需要处理链接语法和用户继续使用行为的内容平台元数据描述，则是存在于OpenURL模型中的固有问题，即链接总是逾期而且如同10年前一样，每个供应商维护一个映射的重复登录的专有语法，厂商往往在没有警告的情况下改变语法，即使链接解析器和知识元库的厂商争相跟踪知识目的，供应商也不改变，一些链接实际上会失效，这是因为不可预知的链接在知识目的中是复杂而千变万化的。对此，英国商业信息主题委员会（TheBusinessInformationTopicCommittee）在2009年12月8日批准NISO工作组"改进OpenURL提高参考链接系统的输入准确度 Improving OpenURLs Through Analytics（IOTA）”的建议，至2012年已经完成相关工作，其工作组制定了一套工具,可以看到什么被内容平台发送给客户以及其他厂商发送给他们客户的比较。为此NISO工作组预处理几十个不同OpenURL供应商所提供的900 多万条OpenURL的日志文件,每个文件都记载着被链接解析器收到季度的时间,根据时间维度监测质量变化[51]。研究发现,由于集成商（Aggregator）、全文持有者（Full-textHost）、内容供应商(ContentProvider)和链接解析器供应商（LinkResolverProvider)的相互竞争，一个特定机构的用户有哪些权利访问哪些资源对象（ResourceObject，RO),如期刊论文的知识元库,其内容往往是不稳定和经常延迟的。

开放知识元库在整个期刊文献的科研数据管理流程如图1所示[52]：

![](images/0da091ef9edf2563562ddd067e1e8697557b4b629ccb867fcf533efecf95aa87.jpg)  
图1期刊科研数据流程①

其流程为[52]：(1)作者提供手稿给出版商；(2)出版商发出文章全文的最终版本和相关元数据到一个或多个网上服务（内容持有者、全文数据库集成商、典藏网站等);(3)内容持有者经常反馈，传递文章元数据给发现工具（DiscoveryTools），如文摘和索引数据库、订阅代理网关、搜索引擎等;(4)内容持有者以及全文数据库也传递典藏信息和MARC记录给知识元库开发者或者直接传给机构；(5)以告知系统延伸传递平台的内容，有些知识  
元库服务传递馆藏数据给机构的资源清单（A-to-Z  
Lists）与链接解析器（Link Resolvers）;(6)有时发送MARC记录，以表示这些系统有关  
的内容交付到平台上的程度。一些知识基础服务将馆藏数据,发送到机构列表A-Z和链接解析器；(7)机构使用此信息来配置自己的收藏,知识元  
库开发者也可发送MARC记录到有OPAC 的单位；(8)在此情况下，该机构必须提供其知识元库开  
发者关于典藏的细节,如电子期刊等。  
2目前,知识元库的供应链是由一系列复杂的角色  
所组成,即出版商、其他内容持有者、订阅代理者、链接  
解析器供应商、图书馆等。其主要特点是[53]：(1)链接解析器的知识元库，多数是为供应商自  
已的专有系统所创建,因为知识元库的数据准确性、全  
面性和及时性是供应商彼此之间的一个竞争手段。(2)根据内容提供商所提供的数据来填充自己的知识元库，其数据质量参差不齐,有可能不经过处理而交付给图书馆。(3)图书馆建设的知识元库，依赖他们从内容提供商和认购代理那里得到的数据的准确性和可靠性。由此可见，问题不仅是技术，还有商业模式和市场

结构的制约，尽管2001年以来就存在商业链接解析器的服务，进一步改善图书馆和用户利益的主要障碍是缺乏利益相关者的理解和他们之间的密切合作[54]

大部分的链接解析器供应商投入大量时间和人力在数据来源上，而不是(或者无法)从源头上解决问题（统一完整的知识元库规范），因此在供应链各组织之间的竞争有时会阻碍合作和数据共享。此外，不是所有的出版商都有足够的合作能力和水平：一方面是缺乏开放的链接解析器供应商的参与，另一方面是知识元库的透明度不够，这会逐渐形成由大型集成商或者内容供应商组成的寡头市场。

KBART为此设计一套简洁的知识元库数据结构，如表 $1 ^ { [ 5 5 ] }$ 所示，其目的在于保障知识元库的清晰度和透明度，即数据格式的标准、预计数据更新的频率、建造的入站链接的语法以及如何支持OpenURL等。

表1KBART的知识元库[55]   

<html><body><table><tr><td>标识语法</td><td>含义</td></tr><tr><td>publication_title</td><td>出版物的标题</td></tr><tr><td>print_identifier</td><td>印本格式标识符(即 ISSN 和ISBN 等)</td></tr><tr><td>online_identifier</td><td>网络格式标识符(即eISSN和eISBN等)</td></tr><tr><td>date_first_issue_online</td><td>能够上线的创刊刊期日期</td></tr><tr><td>num_first_vol_online</td><td>能够上线的创刊卷期号码</td></tr><tr><td>num_first_issue_online</td><td>能够上线的创刊刊期号码</td></tr><tr><td>date_last_issue_online</td><td>能够上线的末刊刊期日期（如果还在发布，则 空白)</td></tr><tr><td>num_last_vol_online</td><td>能够上线的末刊卷期号码（如果还在发布，则 空白)</td></tr><tr><td>num_last_issue_online</td><td>能够上线的末刊刊期号码（如果还在发布，则</td></tr><tr><td>title_url</td><td>空白) 标题层次的URL</td></tr><tr><td>first_author</td><td>第一作者(专着)</td></tr><tr><td>title_id</td><td>标题编号</td></tr><tr><td>embargo_info</td><td>禁止访问的信息</td></tr><tr><td>coverage_depth</td><td>覆盖长度(例如，摘要或全文)</td></tr><tr><td>coverage_notes</td><td>覆盖的注释</td></tr><tr><td>publisher_name</td><td>出版者的名称(如不在文件标题)</td></tr></table></body></html>

知识元库主要包括来自全球内容提供商的期刊元数据内容以及来自本地图书馆所建立的购买馆藏的元数据内容等两部分，因此，对图书馆而言，如果按照知识元库的标准，还需要能够上传更新馆藏的元数据内容。而UKSG 为此提供一套范本,可供下载参考[56]如图2所示：

A B C E 6 H J KLMNOPQ 1pubfcatinte pisas fsti 2Pstirs16 1655 1 167812 h ultest 3Pisotics 1633 1 1775 65 ht: rst ultet 1776 6 1886177 h rst fultest Pof 1637 178 1695166 h tultert 6Pohicf 1596 187 1934-01-01233 h:/sae rsta ultet 1934-11-09 234 731990-06-30331 1 rsta tuitet Poicf6 1990-07-16 332 16231395-12-15 353 1 rsta utet tfteest6555 1800 1 1843 4 ht:/ rspl ultet 10AsctsofePapesC365055 1843 5 1854 6 hp: ultet 11rocehc 1854 7 1905-01-0175 1e5 1905-04-22 76 5071934-10-15146 5 fultet 1Peof 193-11-01 147 E601938-02-18154 : tultet 146 1938-03-16 165 S20 1969-01-26 308 14ht fultet 15Procegfhec4 1969-02-18 309 14961990-06-08 429 1 rspa tultet 16 1990-07-09 430 1E78 1355-12-0E 451 1s:/ ultet 四

以上即是目前发展中的开放知识元库。然而必须注意的是，知识元库的条目越多，可发展利用的空间越大，但是这涉及到技术本身以外的议题。因此，现在

KBART所呈现的是最为简洁的元数据，有鉴于情境感知系统的多种应用途径，日后应当发展为多项的开放知识元库。

# 4开放知识元库的延伸应用

情景感知系统的最大用途是图书馆不需要在每一种管道上去维护每一种期刊，只需在一处进行期刊维护即可，因为链接解析器可以建构一个自动链接到适当文献的论文引文的元数据整合并且提供服务。但是OpenURL的链接有效与否，在于图书馆必须维护一个完整、新颖及正确的知识元库。另一方面，对供应链而言，提供正确与及时的元数据仍是一大问题，这也促使知识元库及其相关工具(KBRAT)计划应运而生[51]，该计划是英国UKSG与美国NISO链接携手成立，采用一全球认，并且促供货商上的电子可运的供应更为正确、实时及完整。

2012 年6月13日,Kuali OLE（Kuali Open LibraryEnvironment）和 JISC（Joint Information Systems Commit-tee)宣布一项“全球开放知识库（GlobalOpenKnowl-edgebase）"项目，该项目由安德鲁·梅隆大学与北卡罗来纳州立大学成立一个基金会，已募集到499000美元的赠款[57]。由于 KnowledgeBase 是支撑 OpenURL 链接解析器的重要“大脑”,所以一旦形成开放机制,图书馆可以直接获得出版社对电子期刊（以及日后可能的电子图书)的刊名、卷期、页码、文章标题、文章作者、所属数据库、所属数据库集成商等信息。这有可能只是一场小规模实验，但也可能促使图书馆从此绕过内容集成商、内容供应商、链接解析器供应商等直接面向出版社，取得单一文献的电子流通渠道的信息。若是如此，则大大改变整个行业在系统和内容的供应链，继而影响图书馆的电子资源服务模式。

开放知识元库的发展主要在保障数据供应链的稳定性，而不至于因为供应链的不稳定而限制链接解析器系统的发展。目前人们对于开放知识元库的评价，主要有三点[58]：

(1)KBART的链接解析器和知识元库的某些数据元素优于ERMI（EnvironmentalRelativeMoldiness In-dex）的处理,而IOTA（Improving OpenURL Through Analytics)也有价值，但是不适合数据元素映射。

# 30 现代图书情报技术

(2）NISO核心即资源交换成本（CostofResourceExchange)是一种考虑到成本和使用数据的倡议，应积极开发相关系统。至于COUNTER已成为一个ERM（EnterpriseRiskManagement）风险管理的主体模块，而SUSHI （Standardized Usage Statistics Harvesting Proto-col)继续细化，显示了类似的有限范围内的协议发展的潜力。

(3)ONIX -PL(ONIX for Publications Licenses）比ERMI更好地设计许可条款的许可证编码和表达，但尚未得到广泛实施，NISO应该促进一个简单但可扩展性的“第三条道路”。

目前开放知识元库的内容主要环绕在电子期刊和电子图书的链接服务与统计分析上。然而，图书馆的文献并不仅仅是图书和期刊，在新时代图书情报机构中，还包括大量非传统资源文献如新闻、网页、博客、播客、微客等，这些非正式信息交流的内容正在成为主流信息交流内容，目前既有的知识元库显然不足以满足对这类信息和知识的利用。

另一方面，至今所讨论的“开放”系列集中在元数据层面上的增值运用，未讨论数据层面上的管理和加值运用。换言之，目前只到数字利用的阶段，尚未讨论到数字典藏的阶段。其关键问题不仅是计算机技术能否保障这种新一代信息组织能力的稳定性，而且涉及许可证等著作权管理方面，直接相关的文献并不多见。

许可证是内容提供商和图书馆或者采购联盟之间的合约，具体条款通常包括网上访问的内容范围、访问期间、访问方式等，不同机构有不同条款，但是它们会反映在本地图书馆的知识元库的元数据内容中。因此开放知识元库的延伸，其主要目的除了技术应用，更应重视用户权利和图书馆充分利用所购买的元数据内容等。本文在实作经验的基础上，系统梳理有关图书馆电子资源管理和外接网络资源的核心技术和当前主要面临的问题。相关议题在日后进一步解释。

(致谢：感谢评委的评审和编辑部的校勘。)

# 参考文献：

[1」顾敏，郑宝梅，曾堃贤，等.广域书目系统学：图书馆事业与知 识管理的基础[M].台湾：新加坡圣智学习亚洲私人有限公司 台湾分公司,2O11.（Gu Min,Zheng Baomei,Zeng Kunxian,et al. Bibliography Complex：Fundamentals ofLibrarianship and Knowl

edge Management[M]． Taiwan:Cengage Learning,2011.）  
[2]Glasser S. Broken Links and Failed Access How KBART,IOTA,and PIE-JCan Help[J]． Library Resources and Technical Serv-ices,2012,56(1) :14-23.  
[3]Van de Sompel H,Hochstenbach P.Reference Linking in a HybridLibrary Environment-Part 3：Generalizing the SFX Solution in the" SFX $@$ Ghent& SFX $@$ LANL"Experiment[J/OL]．D - LibMagazine,1999,5(10).[2012-08-17]. http://www. dlib.org/dlib/october99/van_de_sompel/10van_de_sompel. html.  
[4]Van de Sompel H,Hochstenbach P.Reference Linking in a HybridLibrary Environment-Part 2：SFX,a Generic Linking Solution[J/OL].D-Lib Magazine，1999,5（4)．[2012-08-17]．ht-tp://www.dlib.org/dlib/april99/van_de_sompel/04van_de_som-pel - pt2. html.  
5]Vande Sompel H,Hochstenbach P.ReferenceLinkinginaHybridLibrary Environment -Part 1：Frameworks for Linking[J/OL].D-Lib Magazine，1999,5（4)．[2012-08-17].http://dx.doi.org/10.1045/april99-van_de_sompel -pt1.  
L6]Van de Sompel H,Beit-ArieO.Open Linking in the ScholarlyInformation Environment Using OpenURL Framework[J/OL].D-Lib Magazine,2001,7(3)．[2012-08-17].www.dlib.org/dlib/march01/vandesompel/03vandesompel. html.  
D7] Beit -ArieO,Blake M,Caplan P,et al.Linking to the Appropri-ate Copy：Report of a DOI-Based Prototype[J/OL]．D- LibMagazine,2001,7（9)．[2011-05-30].http://www.dlib.org/dlib/september01/caplan/09caplan.html.  
8]National Information Standards Organization.ANSI/NISO Z39.88- 2004（R2010），The OpenURL Framework for Context- Sensi-tive Services[S].  
D9] Boyd M,Williams S C. What We Have Learned in Two Years:SFX at Illinois State University’s Milner Library[EB/OL].[2006-11-04]. https://netfiles.uiuc.edu/scwillms/www/CV.../SFXatISU. ppt.  
[10]李富玲，卢振波．SFX-信息资源整合新工具[J].现代图书情报技术,2002(6）:69-71.（LiFuling，Lu Zhenbo.SFX-NewProduct in Integration of Scholarly Information Sources[J]．NewTechnology of Library and Information Service，2002（6）:69-71.）  
[11］黄镝.SFXContext-Sensitive 电子信息资源整合的利器[J].图书馆杂志，2002，21（3）:49-50.（Huang Di.SFX Context-Sensitive：The Important Tool of Integrating Electronic InformationResources[J]． Library Journal,2002,21(3）:49-50.）  
[12］何立民，万跃华，李平．电子文献正文引文跨越学术领域的链接[J].大学图书馆学报，2003，21（2）:36-39.（He Limin,Wan Yuehua,Li Ping.CrossRef：A Collaborative Linking of Elec-tronic Document Between Content and Reference AcrosstheScholarly Realm[J]．Journal of Academic Libraries，2003，21(2):36-39.)  
[13］马建霞.数字图书馆环境下基于OpenURL的开放式链接框架研究[J].图书情报工作，2003,47（12）：65-71.（Ma Jianxia.Open Linking Framework Based on OpenURL in the Digital Library[J].Library and Information Service,2003,47(12）:65-71.）  
[14］李爱国，汪社教．学术信息资源整合工具——SFX及其启示[J].现代图书情报技术，2003（1）:48-50.（Li Aiguo，WangShejiao.Tool of Academic Information Integration-SFX and ItsEnlightenment[J].New Technology of Library and InformationService,2003（1) :48-50.）  
[15］沈艺.OpenURL及其运用[J]．现代图书情报技术，2004（1）：30-32.（Shen Yi.OpenURL and Its Application[J]．New Tech-nology of Library and Information Service,2004（1）:30-32.）  
[16］李红雨，赵乃瑄，彭蕾．OpenURL 框架和 SFX 技术在异构数据整合中的应用[J]．南京工业大学学报：自然科学版,2004,26(5）:95-97.（Li Hongyu,Zhao Naixuan,Peng Lei. Applica-tion of OpenURL and SFX in Intergration of Heterogeneous Data-bases[J]． Journal of Nanjing University of Technology：NaturalScience Edition,2004,26(5）:95-97.)  
[17］李欣荣．SFX技术在资源整合利用中的应用[J].情报科学,2005，23(3）:371-373.（Li Xinrong.Application in the Integra-tion of the Resources is Utilized of SFX Technology[J]．Informa-tion Science，2005，23(3）:371-373.）  
[18］杨思洛.基于OpenURL的参考链接系统［J].情报科学，2005,23（11）:1696-1699.（Yang Siluo．The Reference Linking Sys-tem Based on OpenURL[J]. Information Science,2005,23（11):1696 -1699. )  
[19］吕艳丽.基于Web 站点的图书馆检索系统研究[J].贵图学刊，2005（4）：43-45.（Lv Yanli.Studies on Retrieval SystemsBased on Library Websites[J].Gui Tu Xue Kan,2005(4）：43-45.）  
[20]邵燕，宋文．图书馆数字资源整合浅谈［J].图书馆论坛，2005,25(6）:187-189.（Shao Yan，Song Wen.A Brief Analy-sis of the Integration of Library Digital Resources[J].Library Trib-une,2005,25(6):187 -189.）  
[21］黄美君，姜爱蓉．合适的链接最佳的服务—SFX与Cross-Ref/DOI交互作用探讨[J].图书情报工作,2006,50（3）:91-94.（Huang Meijun，Jiang Airong.Appropriate Linking for BestService-——Interaction of SFX and CrossRef/DOI[J]. Library andInformation Service，2006,50(3）:91-94.）  
[22］孟凡静．基于OpenURL 的开放式参考链接[J].图书馆学刊,2006,28(4）:131-132.（Meng Fanjing.Open Reference Link-ing Based on OpenURL[J]. Journal of Library Science,2006,28(4):131-132.)  
[23］茆意宏，张俊，黄水清．异构数据库互操作协议 Z39．50 和OpenURL的比较研究［J].图书馆理论与实践，2006（4）：101-104．（Mao Yihong，Zhang Jun，Huang Shuiqing.The Hetero-geneous Databases Interactive Operation Protocol：Z39.5O andOpenURL[J]．Library Theory and Practice，2006（4）：101-104.）  
[24］窦天芳，姜爱蓉，林容．利用 Z39.50 扩展 SFX应用的实例[J]．现代图书情报技术,2008（4）：86-89．（Dou Tianfang,Jiang Airong，Lin Rong. A Case on Extending SFX Service Basedon Z39.50 Protocol[J].New Technology of Library and Informa-tion Service,2008（4）:86-89.）  
[25］孙博阳.Google 学术搜索工具及其在我馆的应用[J].大学图书馆学报，2007,25(2）：79-82.（Sun Boyang.Google Scholarand Its Implementation in BNU Library[J]．Journal of AcademicLibraries,2007,25(2):79-82.)  
[26］郑淑芬．ScholarSFX与Google Scholar 的本地化[J].现代情报，2007,27（9）：177-179．（Zheng Shufen．The Localization ofScholarSFX and Gogle Scholar[J].Modern Information，2007,27(9) : 177 -179. )  
27］姜爱蓉，王平，郑小惠.分布异构资源整合管理系统的技术特点和应用趋势—MetaLib& SFX综述[J].现代图书情报技术，2004（4）:1-5,62.（Jiang Airong，Wang Ping，Zheng Xiao-hui.The Technical Features and Development Trends of the Inte-grated Management Systems for Distributing Heterogeneous DigitalResources- -Summary about MetaLib& SFX System[J].NewTechnology ofLibrary and Information Service，2004（4）:1-5,62.）  
[28］龚亦农．TPI、TRS 和 Metalib/SFX 三种数字图书馆软件系统的资源整合功能比较分析［J]．新世纪图书馆，2007（3）：66-68.（Gong Yinong. Comparative Analysis of the Resources Integra-tion Functions in Three Digital Library Software Systems[J]．NewCentury Library,2007(3):66-68.)  
[29］窦天芳，姜爱蓉，陈武．以 Exlibris Metalib 为例谈整合检索的几个关键技术及应用[J]．情报科学,2007，25（8)：1235-1239.（Dou Tianfang，Jiang Airong，Chen Wu.Application ofKey Technologies of Metasearch——Metalib as a Case Study[J].Information Science,2007,25(8）:1235-1239.)  
[30］许萍华．Metalib/SFX的增值服务——以南京师范大学图书馆为例[J].贵图学刊,2010(3）:42-43.（XuPinghua.Value-added Services of Metalib/SFX a Case Study of Nanjing NormalUniversity Library[J].Gui Tu Xue Kan,2010(3):42-43.）  
[31］胡新颖．Metalib/SFX统一检索平台系统的应用[J]．科技情报开发与经济,2009（18）:123-124.（Hu Xinying.The Applica-tion of the Unified Retrieval Platform System MetaLib/SFX[J].Sci-Tech Information Development & Economy，2009（18）:123-124.）

[32］廖剑岚.MetaLib/SFX系统与电子期刊导航一从电子期刊管理

# 32 现代图书情报技术

的角度分析[J]．现代情报，2009，29（1）：178－180，183.(Liao Jianlan.MetaLib/SFX System and Electronic Journal Navi-gation System—From the Perspect of Electronic Journal Manage-ment[J].Modern Information,2009,29(1):178-180,183.)

[33］许萍华．Metalib/SFX 遇见Web2.0后产生的图书馆新服务[J]．图书馆学刊,2010,32（7）：85-87．（Xu Pinghua.Emer-ging Some New Library Services When Metalib/SFX MeetingWeb2.0[J]．Journal of Library Science，2010，32（7）：85-87.）  
[34］钱庆，方安，孙海霞，等．MetaLib/SFX本地化开发应用探析[J]．医学信息学杂志，2009，30（1）：14－19．（Qian Qing，Fang An,Sun Haixia,et al.The Local Development and Applica-tion of MetaLib/SFX[J]．Journal of Medical Informatics，2009,30(1) :14 -19. )  
[35］黄敏．基于 SFX框架的开放参考链接:原理与特点[J].图书馆理论与实践，2007（3）：90-93．（Huang Min.Open ReferenceLinking on SFX Framework:Principles and Characteristics[J].Li-brary Theory and Practice,2007(3): 90-93.）  
[36］窦天芳，张喜来，张成昱，等．利用 SFXCitation Linker实现电子图书的跨平台应用[J].现代图书情报技术,2008（9)：83-86.（Dou Tianfang，Zhang Xilai, Zhang Chengyu，et al. Cross-platform E-book Application Using SFX Citation Linker[J].NewTechnologyof Library and Information Service，2008（9）: 83-86.）  
[37］张茵，李娟，樊红侠．WebBridge 参考引文链接系统及其在资源整合中的应用[J].情报杂志，2008，27（9）：39－41.(Zhang Yin，Li Juan，Fan Hongxia.The Application of Web-Bridge Link Resolver System in Xi'an Jiaotong University LibraryResources Integration[J].Journal of Information，2008,27(9）:39 -41.)  
[38］刘胜，陈定权，莫秀娟．基于开放式参考链接的数字资源整合研究[J]．图书馆学研究，2008（5）：16－20．（Liu Sheng，Chen Dingquan，Mo Xiujuan. Research on Digital Resources Inte-gration Based on Open Reference Linking[J]．Researches in Li-brary Science,2008(5）:16 -20.)  
[39］郭向勇，李勇，夏东升．多载体信息资源整合平台构建及关键技术应用[J].深圳职业技术学院学报，2010（1）：44－49.（Guo Xiangyong,Li Yong，Xia Dongsheng.Integrated InformationSystem of Multimedia Resource and Key Technologies[J].Journalof Shenzhen Polytechnic,2010（1）:44-49.）  
[40］窦天芳，姜爱蓉，张成昱，等．Web 环境下多源数据的集成服务——以清华大学新期刊导航为例[J].大学图书馆学报,2010,28（3）: 80－84．（Dou Tianfang，Jiang Airong，ZhangChengyu,et al.A New Integrated Service Using Multiple SourceData in the Web Environment：Taking Tsinghua E-Journal Navi-gation System as a Case Study[J]．Journal of Academic Libraries,2010,28(3):80-84.)  
[41］孙博阳．浏览器扩展组件在图书馆的应用[J].大学图书馆学报,2010,28（1）：24-29．（Sun Boyang.Application of WebBrowser Extensions to Enhance Library Access[J]. Journal of Aca-demic Libraries,2010,28(1):24-29.)  
[42］吴雷.数字图书馆门户研究——以上海交通大学学术信息资源检索系统为例[J]．图书馆研究与工作，2010（1)：29-31.(Wu Lei.The Research of Digital Library Portal—Taking theAcademic Information Retrieval System of Shanghai Jiaotong Uni-versity asan Example[J]．Library Science Research and Work,2010 (1) : 29 -31.)  
[43］胡新颖．数字资源统一检索系统现状分析[J]．情报探索，2010(6）:107-109.（Hu Xinying.The Analysis on Digital Re-sources Unified Retrieval System[J].Information Research,2010(6):107-109.)  
[44］赵民君，张精理，刘小谦．SFX 技术在数字图书馆中的应用[J]．医学信息学杂志，2011，32（2）：72-75．（Zhao Minjun，Zhang Jingli,Liu Xiaoqian.The Application of SFX Technology inDigital Libraries[J]．Journal of Medical Informatics，2011，32(2):72 -75.)  
145］张敏．图书馆数字信息资源动态链接整合技术研究现状分析[J]．现代情报，2008（7）:12－14．（ZhangMin.The Analysisof Dynamic Connection Integration Technology in Libraries[J].Modern Information,2008(7）:12-14.）  
[46］周晓英．知识网络、知识链接和知识服务研究[J]．情报资料工作，2010(2）:5-10.（Zhou Xiaoying.Research of KnowledgeNetwork，Knowledge Linking and Knowledge Service[J].Informa-tion and Documentation Services,2010(2）:5-10.)  
[47］贾延霞，吕肖华，杨慧，等．电子期刊编目方法新尝试——以清华大学图书馆的实践为例[J]．图书馆建设,2011（4）：43-46,50.（Jia Yanxia,Lv Xiaohua，Yang Hui,et al.New Attemptto E-Journals Catalogue —Taking Tsinghua University Libraryas an Example[J].Library Development,2011(4):43-46,50.)  
[48］施晓华，曲建峰，宋海艳．基于用户使用数据分析的图书馆学术推荐服务[J]．图书馆杂志，2011，30(9):21-25．（Shi Xi-aohua，Qu Jianfeng，Song Haiyan．Academic RecommendationServices for Libraries Based on Usage Data Analysis[J]．LibraryJournal,2011,30(9):21-25.）  
[49］孙博阳，金丽萍．开放获取期刊用户利用数据分析[J]．图书馆杂志，2011,30(2）：41-45．（Sun Boyang，Jin Liping.Us-age Study of Open Access Journals in BNU Library[J].LibraryJournal,2011,30(2):41-45.）  
[50］孙波，黄颖．国内外开放获取期刊现状调查研究[J]．图书馆学研究,2010（8）：98-100.（Sun Bo，Huang Ying.Investiga-tion on Open Access Journals at Home and Abroad[J]．Researcheson Library Science,2010(8）:98-100.）  
[51]NISO/UKSG KBART Working Group.KBART: Knowledge Basesand Related Tools：A Recommended Practice of the National Infor-mation Standards Organization（NISO）and UKSG,NISO-RP-9-2010（Baltimore，Md.：NISO,2010)[EB/OL].[2011-09-22].http://www.uksg.org/sites/uksg.org/files/KBART_Phase_I_Recommended_Practice. pdf.)  
[52]Chandler A，Wiley G,LeBlanc J.Towards Transparent and Scala-ble OpenURL Quality Metrics[J/OL]．D- Lib Magazine,2011,17(3-4）.[2012-09 -22]．http://www.dlib.org/dlib/march11/chandler/O3chandler. html.  
[53]Chandler A.NISO IOTA：Improving OpenURLs Through Analyt-ics,in Context[EB/OL].[2012-09-22].http://ecommons.cornell.edu/bitstream/1813/19495/2/ATG% 20NISO%20IOTA% 20in% 20context. pdf.  
[54]Culling J.Link Resolvers and the Serials Supply Chain[EB/OL].[2012-09-14].http://www.uksg.org/projects/linkfinal.  
[55]UKSG，KBART.Data Fields and Labels[EB/OL].[2011-09 -22].htp://www.uksg.org/kbart/s5/guidelines/data $^ -$ field_la-bels.  
[56]UKSG.Data Exchange Sample[EB/OL].[2011 -03-08]. ht-tp://www.uksg.org/kbart/s5/guidelines/data_field_labels.  
[57］JISC.International Collaboration to Help Transform Way LibrariesManage Their Resources[EB/OL].[2012-06-14].http://www.jisc.ac.uk/news/stories/2012/06/data.aspx.  
[58］Jewell T,Aipperspach J,Anderson I,et al．Making Good on thePromise of ERM:A Standards and Best Practices Discussion Paper[EB/OL].[2012 -03-08].htp://www.niso.org/apps/group-public/download.php/7946/Making_Good_on_the_Promise_of_ERM. pdf.（作者E-mail:gulp@ mail.las.ac.cn）