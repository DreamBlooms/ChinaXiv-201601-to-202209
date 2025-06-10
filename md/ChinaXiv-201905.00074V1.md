# 丽江2.4米望远镜观测日志辅助系统的设计与研发

王传军1,2,3，王德清1,2,3，肖健4，尹树成‘，王锋1,5，范玉峰1,2  
（1．中国科学院云南天文台，云南 昆明 650216；2．中国科学院天体结构与演化重点实验  
室，云南昆明650216；3.中国科学院大学，北京100049；4．天津大学软件学院，天津300354；5.广州大学天体物理中心/物理与电子工程学院，广东广州 510006）

摘要：望远镜的观测日志在观测用户进行数据处理以及台站对观测数据进行存储、归档和发布的时候都非常重要,观测日志往往能提供很多观测信息以供用户判断观测数据的质量。在实际观测过程中，观测日志是通过观测助手或观测用户手工记录的，存在信息不全、笔误等多种可能，且纸质的日志也不利于后期观测数据的归档和发布。本文针对丽江2.4米望远镜YFOSC的观测数据，设计研发了一套自动记录观测日志的辅助系统，该系统可以自动记录观测数据的日志信息，并提供了修改错误信息的功能；系统中以观测用户的观测时间申请书编号为唯一代码对观测数据进行管理，从而实现了根据不同观测用户进行观测数据打包的功能。在保护观测数据权限的同时，降低了笔误带来的影响，提高了观测日志的准确性，最终提高观测效率。

关键词：观测日志，观测数据，观测时间中图分类号：xxxx 文献标识码：xxx 文章编号：xXXX

# 0引言

天文学从肉眼观星到通过望远镜观星，从"全波段天文学"到"多信使天文学”，人类认识宇宙的手段在逐渐丰富。2017年10月16日，全球多国科学家同步举行新闻发布会，宣布人类第一次直接探测到来自双中子星合并的引力波，并同时"看到"这一壮观宇宙事件发出的电磁信号'。引力波提供了一种与以往观测方式完全不同的手段，天文学研究现已进入大数据、多信使时代[1]。

在观测手段丰富的同时，大型望远镜的观测数据量也越来越大[2]，这些海量天文数据对存储、计算、网络、软件、算法乃至工作模式等方面都提出了新的需求和挑战[3]。天文学家需要将庞大的数据进行标准化的存储及传输，FITS（Flexible Image Transport System）文件格式则早已成为天文数据的通用标准[3[4]。FITS 文件包括文件头和数据矩阵两部分，文件可以扩展，但文件大小必须是2880个字节的整数倍。在对观测数据进行入库管理的时候，将FITS头关键词的值也进行入库归档，从而便于后续的检索访问[5。虽然在观测数据的FITS头中，已经记录了大部分的信息，但是这些FITS头信息的内容却由于不同的终端而千差万别，而且有些观测终端观测数据的FITS 头中包含的信息不完整，商品化终端设备的FITS头内容更是无法进行修改和补充。因此，在获取观测数据的过程中，往往需要观测日志对观测过程中的详细情况进行记录，以便对观测数据进行更好的分类管理。

光学望远镜的观测日志，是在使用光学望远镜及其观测终端进行观测的过程中用来记录相关观测信息的文档，其内容包括望远镜、选用的观测终端、观测目标、曝光时间、选用的滤光片或光栅、观测类型、狭缝、数据采集时刻等信息。对于观测用户而言，观测日志是处理数据所必须依赖的文档，观测日志中提供的信息往往能给观测数据的处理带来便利。对于各台望远镜的运维而言，观测日志为观测数据的存储、归档、预处理和后期发布提供了很好的依据，参照观测日志可以在预处理的时候剔除掉无用的观测数据，并根据实际观测条件对观测数据进行更好的预处理，对观测数据的分类管理也提供了便利。此外，对于做数据统计的用户而言，观测日志更加重要，通过多年的观测日志的查找，可以快速查询到同一目标不同时间观测过的数据，提高观测数据查找和统计的效率。

在丽江2.4米望远镜的实际观测过程中，首先由观测用户提供观测目标的坐标信息及观测需求给观测助手，观测助手将观测目标输入到望远镜控制系统中并驱动望远镜指向该目标，根据观测用户的需求对观测终端进行对应的配置；在望远镜和观测终端准备就绪之后，开始曝光，同时记录观测日志。在目前的观测模式下，观测日志的记录依赖于观测助手或者观测用户手工记录，在观测过程中时间有限，手工记录的观测日志难免存在笔误，有时甚至会影响到观测时间的充分利用，此外纸质版的日志也不利于保存和传播。为了保证观测日志记录的准确性、减少观测日志记录的时间、提高观测效率，本文作者及其合作者共同针对2.4 米望远镜的主力观测终端 YFOSC(Yunnan Faint Ob ject Spectrograph and Camera)[6]设计和研发了一套自动记录观测日志的辅助系统。本文第一部分介绍该辅助系统的功能及设计，第二部分介绍该辅助系统的具体实现，第三部分对目前的运行情况进行总结。

# 1．系统功能及设计

观测日志辅助系统旨在对观测日志进行自动化的记录，帮助望远镜观测人员摆脱琐碎的手写记录观测日志的工作，将望远镜观测日志的管理流程化、自动化，简化观测助手在观测中的操作，减少因人工疏忽而导致的失误。通过观测日志辅助系统，可以实现观测数据的自动录入、查询、打包下载及相关辅助功能，为观测日志的管理提供了高可靠性、高自适应性的服务。其研发目标是在不修改原始FITS 文件的基础上，集监听功能和查询功能于一体，对FITS头信息进行必要的修正，将FITS头信息与补充的信息整合成一条观测日志存入到数据库中，供后期观测数据处理过程中进行使用。

该系统需要实现的主要功能包括：

1）在曝光结束观测数据保存到硬盘之后，系统能够读取该观测数据文件的 FITS 头信息，并将信息写入到数据库中，同时在辅助系统的前台界面显示;  
2）在观测辅助系统的前台界面中，用户可以对采集到的记录进行检查，添加信息或修改出错的信息，并提交更新数据库；  
3） 在观测的时候可以选择不同观测用户的不同观测时间申请书的编号，使得观测数据与观测用户的编号联系在一起，便于观测数据的管理；  
4） 能根据观测用户的用户名或者观测时间申请书编号，对观测数据进行查询、打包和下载，同时可以生成规定格式的观测日志文件；  
5） 将常用的观测用户固定在前台界面上显示，方便观测期间的操作；  
6） 在前台界面显示系统运行状态及用户操作相关的运行情况，以确保该辅助系统的正常运行；  
7） 用户可以对观测日志记录进行批量的提交，如果没有修改，默认就使用从FITS 头中读取的信息，并保存到数据库中。

在进行系统研发的过程中，采用了分层式的系统架构方案，将系统的整体架构分为了四层，即：视图层、控制层、服务层和数据层（如图1所示)。其中：

1）视图层：主要负责显示监听到的观测数据FITS 头中对应的观测日志信息，接受用户的监听控制和对观测日志内容的修改操作，以及显示当前软件运行的状态信息和用户的操作记录。  
2）控制层：介于前台界面和后台数据库之间，主要负责接受视图层产生的用户请求并路由到服务层，调用服务层的处理程序，并将服务层处理的结果返回给视图层。  
3）服务层：主要完成系统软件与数据层之间的交互，并为控制层提供调用所有相关服务所需要的接口，各个服务之间也根据需要进行相互的调用。该层主要包含六类服务，即：文件监听服务、数据导出服务、FITS 服务、日志服务、Log文件服务、配置服务。  
4）数据层：对应于系统所涉及的所有相关的数据文件，包括望远镜的观测数据（原始FITS 文件）、系统运行的配置文件和保存在数据库中的结构化数据。主要负责响应服务层的请求，对请求进行处理，并返回结果。

结合系统的架构图可知，系统所需要实现的所有功能需要不同层次之间的程序进行配合才能完成，为了提高安全性，各层之间彼此相互独立，且不能跨层次进行调用。

![](images/88d752c01b567d225d4c4be110d8c0dc31015d9744ce50411cac2abcaaafa060.jpg)  
图1系统架构图  
Fig1The systemarchitecture

# 2．系统实现

在进行系统实现的过程中，采用了模块化的思想对系统的所有功能进行实现，根据主要功能将系统划分成了界面显示模块、数据监控模块、数据查询模块、数据导出模块、系统日志模块和系统配置模块这六个功能模块进行实现。

# 2.1系统研发和运行环境

该观测日志辅助系统是在Ubuntul3.10操作系统平台上进行研发和运行的，采用的编译环境是JDK 1.7（Java Development Kit1.7)，采用的编程语言是面向对象的Java 语言[7],后台使用的数据库是PostgreSQL 数据库系统[8。在系统中调用了几个开源的Java开发包：

$\bullet$ Commons-compress-1.8.jar²：apache 出品，主要实现对用户查询得到的原始观测数据进行打包的功能;Dom4 j-2.0.00-ALPHA-2.jar：是dom4j.org 出品的一个开源的 XML 解析包，性能优越、功能强大。jxl.jar4：来自Java Excel开源项目，用于实现读取 Excel文件的内容、创建新的Exce1文件和更新已经存在的Exce1文件。  
$\bullet$ postgresql-9.3-1101.jdbc4.jar：为 Java 语言提供与 postgreSQL 数据进行连接的数据库中间件。

# 2.2界面显示模块

界面显示模块是使用Java的图形界面库 Swing开发完成的,最终正常运行的效果如图2所示。如图所示在该用户界面中包含了不同的功能区，主要包括：

Log Tool   
YFCd240... 0000000 AG RemarksInstMode ObvervationlD CukRoSWR ObsType 15 D 15088 NeOs EsS 国 chk CukRBWN 门 158-388588 NOU OPn PG1022+..0.0 unknown 国 156.38033 51.67636 YFOSC YSU王建民 Open   
雕 Cuknown 电 158.38035517636 YFOSC open Cpen 美电国范通 1 非   
YFCd240... PG1022+. ① unknown W 156.38033 51.67636 YFOSC YSU王建民 2019-04-2.. 1200.0 open Open 饿 1 Pen   
VFC0240 PG1022+.80.0 unknown W 156.3803351.6766 YFOSC YSU王建民 2019-04-2 1200.0 Open   
VFCd248HD935218 国 0000000 山 unknown 口 中 162.0979637.5722VFSCYSU 肥 2019-04-2. 1:8 H COPn 麻   
VFCd240.. BD+75d3...0.0 unknown 122.7054674.96597 YF0SCYSU张居甲 2019-04-2 1.0 Open open Open   
4 add 王建民 钱声帮 张居甲 PINAME 停止 干始 观察者 ③ csv □EXCEL□TAR □SQL 王建国 卢开兴 顾盛宏 PID 全选 提交 截止 PID unlock 查询 导出   
[2019/04/2503:26:54]-室听开始.[PID=10022018010015:PINAME=UKox@ynao.ac.cn]   
[2019/04/25 03:36:54] 监听结束[PID=T0022018010015，PINAME=lul@ynao.ac.cn] $\textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \textcircled { < } \$   
[2019/04/2505:32:30]-当前选择观测Pid=00000   
[2019/04/2505:32:32]-监听开始.[PID=00000;PINAME=public]

$\textcircled{1}$ 观测日志显示区：当曝光结束有新数据文件产生之后，系统读取FITS 文件的 FITS头信息，并在该区域显示，用户可以对该区域的数据进行修改。

$\textcircled{2}$ 数据监控操作区：提供了选择观测用户的ProposalID，开始监听，停止监听，观测日志记录修改之后的提交，添加长期观测项目的用户及其proposalID 等功能。

$\textcircled{3}$ 数据查询、数据导出操作区：用于进行观测数据的查询和导出操作，输入起止时间和观察者然后点击‘查询’就可以进行查询；查询结束之后，用户可以勾选需要导出的文件(Excel是观测日志，TAR是观测数据)，然后点击‘导出’按钮进行打包和压缩，并导出到配置文件中配置的存储路径下。

$\textcircled{4}$ 软件状态显示区：用于显示系统软件运行的状态，用户的每一条操作及对应的反馈信息都会在这个区域进行显示，从而方便用户实时监控软件状态，一旦出错立即进行相应的处理。

# 2.3数据监控模块

观测数据的监听从用户在界面上选择观测项目并点击“开始”之后启动，程序后端会启动一个线程对观测数据的保存目录进行一次扫描，将扫描结果保存在哈希表中，然后每秒重新扫描该目录，比对当前文件是否已经存在哈希表中。如果没有存在则表示有新观测数据产生，则对该数据进行相应的处理，将处理的结果保存到数据库中，并以一条观测日志的模式显示在用户界面上。当该观测用户的观测结束之后，通过“停止”按钮可以停止此次监听，选择新的观测项目后再次启动监听，直到所有观测都结束。数据监控模块的处理流程如图3所示：

![](images/6b196e2c5520bde9f1268983500fe44f26d8c7427b309371c6c22ecc3cf97490.jpg)  
图3观测数据监听功能流程图  
Fig 3 Flow chart of observational data monitoring function

观测日志数据表的格式如表1所示，除常规的观测时间以及曝光时间信息外，还包含了与用户相关的字段，与望远镜相关的指向坐标（RA、DEC）、焦点等字段以及与观测终端相关的滤光片、光栅、狭缝等字段。

表1观测日志数据表格式  
Tab 1 Observational log table format   

<html><body><table><tr><td>名称</td><td>类型</td><td>对应FITS头</td><td>备注</td></tr><tr><td>filename</td><td>字符</td><td></td><td>主键，唯一，FITS文件名</td></tr><tr><td>object</td><td>字符</td><td>OBJECT</td><td>观测目标名</td></tr><tr><td>ra</td><td>浮点数</td><td>RA</td><td>观测目标赤经值</td></tr><tr><td>dec</td><td>浮点数</td><td>DEC</td><td>观测目标赤纬值</td></tr><tr><td>instrument</td><td>字符</td><td>INSTRUME</td><td>观测终端（YFOSC，PICCD，LiJET或HiRES）</td></tr><tr><td>Observer</td><td>字符</td><td>OBSERVER</td><td>关联 proposal表中的用户ID</td></tr></table></body></html>

<html><body><table><tr><td>ProposalID</td><td>字符</td><td>无</td><td>关联 Proposal 表中的申请书 ID</td></tr><tr><td>ObvervationID</td><td>字符</td><td>无</td><td>观测 ID，手动录入</td></tr><tr><td>StartUTC</td><td>时间</td><td>DATE-OBS</td><td>观测数据曝光开始时间</td></tr><tr><td>ExposureTime</td><td>整数(秒)</td><td>EXPTIME</td><td>观测数据曝光时间</td></tr><tr><td>Filter</td><td>字符</td><td>YFLTNM</td><td>所使用的滤光片名称</td></tr><tr><td>YFUA</td><td>字符</td><td>YAFLTNM</td><td>YFUA 转轮上对应的光学元件名</td></tr><tr><td>YFUB</td><td>字符</td><td>YBFLTNM</td><td>YFUB 转轮上对应的光学元件名</td></tr><tr><td>Slit</td><td>字符</td><td>YAPRTNM</td><td>狭缝转轮上的狭缝的名称</td></tr><tr><td>Grism</td><td>字符</td><td>YGRNM</td><td>光栅转轮上的光栅的名称</td></tr><tr><td>telFocus</td><td>浮点数</td><td>TELFOCUS</td><td>望远镜的焦点</td></tr><tr><td>instFocus</td><td>浮点数</td><td>YFOCUS</td><td>YFSOC的焦点</td></tr><tr><td>AG</td><td>浮点数</td><td>无</td><td>自动导星焦点</td></tr><tr><td>FWHM</td><td>浮点数</td><td>无</td><td>半高全宽值，手动输入</td></tr><tr><td>obsType</td><td>字符</td><td>无</td><td>观测类型（pho，spe 或 unk)</td></tr><tr><td>Remark</td><td>字符</td><td>无</td><td>备注信息，手动录入</td></tr><tr><td>archflag</td><td>布尔</td><td>无</td><td>是否已导出归档</td></tr><tr><td>filesize</td><td>整数</td><td>无</td><td>观测数据文件的大小</td></tr></table></body></html>

# 2.4数据查询模块

数据查询模块主要通过 JDBC（JavaDataBase Connectivity）对观测日志数据库进行查询操作。当观测日志记录入库之后，用户可以根据需求对历史的观测日志记录进行查询，如果在查询到的记录中发现错误，也可以对其进行必要的修改。

在查询的时候，用户需要提供观测数据覆盖的时间段和观测项目负责人的信息（负责人姓名，对应的数据库字段是：Observer）进行查询，查询的结果除了显示在用户界面上，也会保存在缓存中以便生成所需要的观测日志文件。

# 2.5数据导出模块

数据导出模块实现了对用户查询到的观测数据的结果进行导出的功能，该模块可以同时导出观测数据和对应的观测日志，从而直接将两部分的文件打包给观测用户，方便观测用户进行观测数据的处理。

观测数据通过后台的打包程序将检索到的结果进行打包，并压缩；观测日志则通过后台的 Excel处理软件生成与观测数据对应的观测日志文件；所有的文件最后都输出到配置文件中指定的目录中。

# 2.6系统日志模块

系统日志模块将所有的日志信息划分为软件状态日志、软件操作日志和错误信息日志这三种类型。其中：

软件状态日志：将日志的输入流接口重新定向到Swing的文本框组件中进行实时显示，从而显示软件运行的状态，该部分的日志不会以文件的形式保存。

软件操作日志：记录软件的主要运行状态，观测数据生成的时间以及用户操作软件的相关信息，该类日志信息可以在发现观测日志有误的时候对当时的情景进行复现。

错误信息日志：用于记录软件在运行过程中具体的出错信息，从而可以协助研发者更好地定位软件的错误位置。

软件操作日志和错误信息日志都按天生成一个新文件，系统中主要通过Log4jUtil类完成对系统日志的管理，通过一个独立的线程将必要的日志信息写入到日志文件中。

# 2.7系统配置模块

系统配置信息保存在xml文件中，系统软件正常运行需要两个相关的xml文件，用户可以通过修改这两个配置文件更新系统的配置，当再次打开软件运行的时候就可以使用更新后的配置。其中：

configure.xml：保存系统运行相关的配置信息，包括数据库连接地址、数据库账号、需要监听的目录、观测数据和观测日志输出目录。

longterm.xml：保存丽江2.4米望远镜长期观测项目的用户信息，包括观测用户的姓名和观测用户申请书的编号（ProposalID)，目前最多只能配置6个观测用户的信息。该功能还可以应用到机会源（Targetof opportunity，ToO）观测中，当有ToO 观测发生的时候，可以通过修改配置文件临时建立一个观测用户信息，并实时在软件的界面上显示，便于观测日志记录的准确性。

# 3．系统运行情况

在观测日志辅助系统开发完成之后，将其部署在丽江2.4米望远镜圆顶观测室内的一台计算机上，并在实际运行中验证了各部分的功能都能正常运行。如图2展示了系统正常运行时的情况，图中 $\textcircled{1}$ 和 $\textcircled{4}$ 两个部分分别表示监听到的数据信息和软件运行时的一些必要的日志信息。如图4展示了数据查询的情况，图5展示了数据导出的情况（其中tar文件是观测数据的压缩文件，Excel文件则是对应的观测日志文件)。

ToolVrteNa 14gt 8888 Remarks InstMode Obvervati Cunkcogn IS-Submit 二222.3937. 24808.YFCd280... 1449+1 unknown 222.3937.. 24808. YFOSOCd280... 1449+1 0.0 unknown 222.3937.. 25.0VFC020 Lukrovn 22 20.0 oenYFCd280.. J11517+.. unknown 229.4658. 25 VFO 5.0 OpenYyFCd280. 11517+\* 0 unknown 229.458. 9813 YFOSC YSU oenYFCd280.... J1151 17 unknown 229.4658.. 4 9813 VFOSC YSU OpenYFCd280. 11517+\* 0000000000 unkngwn 229.458. 9813 YFOSC YSU 208 Ceunknown 229.4658., 25 39813. YFOSC YSUC820 BD+3 UukR8eh 228.4658. 25.39813 VFOSC 201804 000 CR国酒 粥粥 鞋G王建民 钱声帮 张居甲 PI NAME 开始 开始 2019-04-28 观察者黄样 一 □csv EXCEL TAR SQLadd王建国 卢开兴 顾盛宏 PID 提交 截止 2019-04-29 PID ▼ unlo ck 查询 导出2019/04/29 05:36:3] 宣询条件PID-pupublic 目[2019/04/29 05:36:38] 进行宣询，宣询条件:startutc BETWEEN'2019-04-28' AND'2019-04-29' AND_observer='public' AND proposalid=00000'[2019/04/29 05:36:47]-导出EXCEL文件:/home/obs/YF0SCLogTool/FIts0ut/2m4publc20190428Pagel.xls[2019/04/29 05:36:47] 开始压缩，有60个its文件器要打包[2019/04/29 05:36:47]-已经完成：0%[2019/04/29 05:36:471 - 已经完成 ： 1%

obs@obs-HP-dx2355-MT-FH284PA:\~/YFOSCLogTool/FitsOut\$ 1s   
2m4public20140918Page1.xls 2m4王建民20190427Page1.xls public20160615.tar   
2m4public20150118Page1.xls 2m4黄样20190428Page1.xls public20190428.tar   
2m4public20160315Page1.xls obervlog张居甲20190425.sql 张居甲20190425.tar   
2m4public20160615Page1.xls obervlog王建民20190426.sql 王建民20190426.tar   
2m4public20190428Page1.xls obervlog王建民20190427.sql 王建民20190427.tar   
2m4.xls public20140918.tar 黄样20190428.tar   
2m4张居甲20190425Page1.xls public20150118.tar   
2m4王建民20190426Page1.xls public20160315.tar

# 4.总结

该系统已经在丽江2.4米望远镜上运行使用，能通过对观测数据的监听获取基本的观测日志信息，大大降低了手工记录日志的工作量及出错的概率。在观测结束之后，能针对观测用户进行观测数据的查询和导出，根据查询结果生成观测日志，简化了观测数据拷贝的过程，也保证了保护期内用户观测数据的安全性。此外，该系统还与天文领域云相关联，与天文领域云系统上的观测时间申请系统和数据管理系统进行协调工作，下一步可以实现从观测时间分配到观测数据获取的完整观测数据生产周期。但在使用中还是发现了一些问题：

1）每个观测季开始前，需要手动导入一次观测时间申请表，以便更新本系统内的观测用户和观测申请编号等相关信息；  
2）每年的观测申请数较多，观测过程中通过下拉菜单选择观测用户（PINAME）有点麻烦，需要简化该操作；  
3）系统的数据库中以观测数据的文件名为唯一主键，对观测数据的命名规则有一定要求，移植到其他观测终端需要重新进行二次开发；  
4）没有考虑未来可能的新增字段而设置保留字段，不利于系统在将来的扩展。

在接下来的工作中将逐步解决系统中存在的问题，对整个系统进行优化和完善，使其更具备通用性，从而可以推广到其他观测终端和其他望远镜中去。

# 参考文献：

[1」钟守波，韩波，张彦霞,等．天文大数据管理工具的设计与实现[J]．天文研究与技术，2015，12(4):510-517.  
[2]赵永恒．天文望远镜的自动观测技术[J]．科研信息化技术与应用，2012，3(4)：11-16.  
[3]崔辰州,于策，肖健,等，大数据时代的天文学研究[J].科学通报,2015，60(5-6)：445-449.  
[4]季凯帆,曹文达,宋谦.FITS、BMP和SCR图像格式及相互转换[J].云南天文台台刊,1996,2:60-64.  
[5]张海龙,冶鑫晨,李慧娟,等.天文数据检索与发布综述[J].天文研究与技术，2017,14(2)：212-228.  
[6]王传军,范玉峰,易卫敏.丽江2.4米望远镜 TCS Sequencer程序的设计与开发[J]．天文研究与技术,2013，10（4)：378-385.  
[7」Bruce Eckel．Java编程思想(第4版)[M].机械工业出版社,2013年.  
[8］彭智勇．POSTGRESQL.数据库内核分析[M]．机械工业出版社,2012年.  
[9］王鹏，何昀峰．Java Swing图形界面开发与案例详解[M]．清华大学出版社,2008年.

# Design and development of observation log tool for Lijiang 2.4-meter telescope

Wang Chuanjun123，Wang Deqing,23， Xiao Jian， Yin Shucheng²， Wang Feng15，FanYufeng

(1.Yunnan observatories,Chinese Academy of Sciences, Kunming 65o216,China,Email: wcj@ ynao.ac.cn; 2..KeyLaboratoryforthe StructureandEvolutionofCelestialObjects,ChineseAcademyofSciences,Kunming 650216,China; 3.University of Chinese Academy of Sciences,Beijing 10oo49,China; 4.Software College of Tianjin University,Tianjin 3Oo354,China; 5.Astrophysics Center/InstituteofPhysicsandElectronic Enginering,Guangzhou UniversityGuangzhou51oo6,China)

Abstract: The observation log of the telescope is very useful for the observers on data processing; it is also very useful for the observatory on data storage,archiving and publication. Observation log can provide all kinds of information of the observation for the observers to judge the quality of the observation data.During the observation, the observation log is always recorded by the observation assistant or the observer himself manually. On the one hand, the information in the log might be not specific enough, sometimes also have mistaken in writing. On the other hand, the papery observation log is also inconvenience for the data archiving and publication. Based on the observation data of YFOSC,we designed and developed an observation log tool to record the observation log automatically. This tool can record the observation log automatically by reading the fits header of the observation data. The users can also revise the errors they found in the records of the observation log. The observation log is also related to the observation time application system by using the unique proposal ID to manage the observation data, thus can package the observation data for the specified observer. In summary, by using the observation log tool, the observation data authority can be protected by the system during the data protection period; the influence of mistaken writing can be avoided; the accuracy of the observation log can be increased and can increase the observation efficiency finally.