# 针对科技路线图的文本挖掘研究：集成分析及可视化 \*

谢秀芳1,²张晓林」  
1(中国科学院文献情报中心 北京 100190)  
2(首都医科大学卫生管理与教育学院/首都医科大学图书馆北京100069)

摘要：【目的】实现针对科技路线图内容的知识发现研究，预测未来科技长期发展趋势。【方法】基于采用"抽取-同步-分类"的文本挖掘方法构建的科技路线图信息库，集成分析全球科技发展需求和趋势，对比分析各国发展路线和措施，并以可再生能源领域为案例进行实证研究。【结果】利用开源工具Timeflow、Gephi等对实证研究结果进行可视化，按时间序列从多个角度呈现了可再生能源领域到2050年的发展态势及各国的战略规划。

【局限】综合利用了多种方法工具，自动化程度有待提高，个性化功能有待完善。【结论】该研究方案能够快速获取科技路线图中的核心信息，提高情报获取效率。

关键词:科技路线图战略情报文本挖掘知识发现集成分析信息可视化

分类号：G356.4

# 1引言

科技路线图是关于世界各国未来科技发展规划最直接的战略情报载体，蕴涵着各国科技发展现状、方向、相关技术发展进程、愿景、阶段性目标、战略措施等多方面信息，是一种密集型战略情报资源。利用文本挖掘技术实现对科技路线图的信息抽取、分类组织和集成分析，对把握未来科技发展方向，制定长期发展规划具有重要战略意义[1]。

然而科技路线图在情报学领域更多属于情报研究的产物[2-4]，较少作为情报挖掘的数据资源[5-6]。比较常见的是对某个具体的路线图报告进行人工解读[7-8]，鲜有针对大量科技路线图报告进行文本挖掘研究。因此本研究提出针对科技路线图的文本挖掘研究方案，通过分析科技路线图的内容组织和表达特征，探索科技路线图信息自动抽取方法，建立科技路线图知识库，进而可以基于该特征知识库实现对大量科技路线图的集成分析、对比分析、趋势分析等，实现对科技路线图的文本挖掘和知识发现[9]。

本文基于文献[10]提出的信息抽取方法构建的科技路线图信息库，集成分析全球各国在各个领域的战略规划信息，分析每个领域在世界范围内的发展现状，并预测未来发展趋势，从而实现针对科技路线图文本内容的知识发现过程，为决策者制定相关领域发展计划提供战略情报服务。

# 2科技路线图集成对比分析功能框架

本研究前期调研分析了全球21个国家或组织发布的166份科技路线图，构建了科技路线图内容描述框架和信息分类体系[9，并在此基础上探索了针对科技路线图文本内容的信息抽取方法[10]，依次进行文本清洗、信息抽取、数据清洗、同步匹配、信息分类等步骤，形成了包含文本基础信息、语义分类信息、内容核心信息、句子原始信息4类，共计19个字段的科技路线图信息库(见图1)。其中语义分类信息的取值源自信息分类体系[9中的分类项，如图2所示。

科技路线图信息库 文本基础信息 语义分类信息 内容核心信息 句子原始信息 · ID_doc · Classification_1 · Keyword · ID_sentence · Title · Classification_2 · Value · Sentence · Issue_year · Classification_3 · Time · Location · Issuer · Classification_4 ·Relative_terms · Weight · Object · Relative_entities · Area

Classification_1 · today · vision · pathway ·action Classification_2 ·need·target ·trend ·potential ·opportunity·challenge ·enabler ·barrier Classification_3 · policy ·economy · technology ·market · social ·environment Classification_4 policy economy technology market social environment · plan · investment ·performance·production ·education ·resource · regulation ·tax ·maturity ·consumption ·employment·emission ·evaluation ·finance ·cost ·operation · health · climate ·support ·other ·other ·other ·other · pollution ·other ·other

基于该科技路线图信息库，依赖领域(Area)、时间(Time)、关注对象(Object)、语义分类等信息，可以分别从全球和国家两个层面进行如下分析：

(1）需求分析：集成全球各国对同一领域的发展现状综述，分析该领域在世界范围内的发展需求，以便找准发展定位。

(2)趋势分析：集成全球各国对同一领域的发展趋势、潜力、机遇的分析论述，预测该领域在世界范围内的长期发展趋势，及时把握发展机遇。

(3）路线分析：集成对比分析全球各国在同一领域的技术发展路线，为制定符合国情的发展路线提供参考服务，如:

$\textcircled{1}$ 技术发展态势分析：集成全球各国在同一领域不同时段的技术选择信息，分析该领域的技术发展态势;

$\textcircled{2}$ 技术发展方向分析：集成全球各国在同一领域不同时段的技术目标信息，预测该领域的未来技术发展方向;$\textcircled{3}$ 技术发展路径分析：集成同一技术在全球各国的发展目标，对比各国针对相同技术的不同发展路径规划。(4）战略分析：集成对比分析全球各国在同一领域采取的战略措施，为决策者适时适当的战略布局提供战略情报服务，如：$\textcircled{1}$ 不同国家的发展愿景分析：在相同时间区间，对比分析不同国家在同一领域的不同发展愿景目标;$\textcircled{2}$ 不同国家的发展路线分析：在相同时间区间，对比分析不同国家在同一领域的不同发展路线规划;$\textcircled{3}$ 不同国家的发展措施分析：在相同时间区间，对比分析不同国家在同一领域采取的不同发展战略措施。

因为科技路线图通常是由权威机构或部门针对相关领域发布的未来发展计划，所以具有一定的权威性和前瞻性，通过上述分析，可以比较全面地了解相关领域在世界范围内的发展现状和趋势，该领域未来发展的关键技术，以及各国在该领域的技术选择和战略布局，因此对把握发展机遇、制定发展战略具有重要的情报价值和参考意义。

# 3科技路线图集成分析实现方法

# 3.1 需求分析

为了分析某个领域在世界范围内的发展需求，集成全球各国对该领域发展现状的调查结果，本研究使用开源工具Timeflow[11]进行可视化呈现，将属于同一领域的现状(Classification_1 $\scriptstyle = { \frac { \ d } { \ d } }$ today"）及需求(Classification_ $2 { \it \Delta \phi } = { \it \Delta \Psi }$ need")信息在时间(Time)轴上分类(Classification3)呈现，并用权重(W)标识关键词节点大小，用不同颜色标识分类指标(Classification_4)。为了实现上述功能，需对已有数据进行如下预处理:

(1）关键词与时间词的关联匹配

由于同一个句子中可能包含多个关键词和时间词，所以需要将每个关键词和时间词关联匹配，本研究使用Python 编码，遍历同一个句子内的每个关键词和时间词，借助值词和二者的个数关系实现一对一匹配，详情可以参考文献[10]的核心信息同步匹配部分。

# (2）时间词的赋值计算

为了将各类信息在时间轴上呈现，针对以"today/year/decade/century等"方式表达的时间词，统一映射为数字表达方式，同时为"Time"字段为空的数据记录根据Classification1字段结果赋予时间信息。设报告发布年份等于t，以t为分界点，对包含"year/decade/century等"的时间词按表1中规则分别取计算符号和数值，计算出对应的时间信息“t $+ / - { \boldsymbol { \mathrm { n } } } ^ { \prime }$ 。对其他不涉及计算的时间词按表2中规则直接进行赋值。

表1时间词计算规则  

<html><body><table><tr><td>规则</td><td>描述</td><td>操作</td></tr><tr><td rowspan="2">计算符号(+/-)的判定规则(决定在时间t 的基础上执行"加"或"减"操作)</td><td>过去时间</td><td>over/past/previous/recent/preceding/last 等，符号取"-"</td></tr><tr><td>将来时间</td><td>next/following/coming/later 等，符号取"+"</td></tr><tr><td rowspan="3">计算加数或减数的取值规则(在时间t 的基础上执行加减的数值n)</td><td>单数</td><td>year: n=1; decade: n=10; century: n=100 years:取相应数字，即n=2/3/10/20 等</td></tr><tr><td>two/three/ten/20 等后接复数</td><td>decades:取相应数字乘以10，即n=10×(2/3/10/20)等 centuries:取相应数字乘以100，即n=100×(2/3/10/20)等</td></tr><tr><td>few/several/some等后接复数</td><td>years: n=5;decades: n=50;centuries: n=500</td></tr></table></body></html>

表2时间词赋值规则  

<html><body><table><tr><td colspan="2">条件</td><td>赋值</td></tr><tr><td colspan="2">当前时间(如 today/present/current/now)</td><td>赋值为发表年份t</td></tr><tr><td colspan="2">beginning/early/dawn/start of century/decade</td><td>赋值为该10年或世纪开始的年份</td></tr><tr><td colspan="2">end/late of decade/century</td><td>赋值为该10年或世纪结束的年份</td></tr><tr><td rowspan="4">时间词为空(不 包含且未能继承 时间信息)</td><td>Classification_1="today"</td><td>即属于现状，赋予发表年份t</td></tr><tr><td>Classification_1="vision”</td><td>即属于愿景，赋予最后一个规划节点年份</td></tr><tr><td>Classification_1="pathway"/"action"</td><td>即属于路线或措施，赋予整个规划区间</td></tr><tr><td>Classification_1="other”</td><td>即属于其它，赋予t-1，作为其它背景信息</td></tr></table></body></html>

虽然Timeflow可以呈现时间区间，为了使呈现结果更加清晰可辨，本研究中将时间区间分解为多个时间规划节点，如区间(2015,2050)分解为"2015、2020、2030、2050"，(2011,2030)分解为"2011、2020、2030”。然后使所在句子的关键词一一与每个时间节点关联

匹配。

# (3）关键词权重计算

根据关键词在每篇文档中所处位置(Location)、词频(TF，在某篇文档内出现的次数)和文档频次(DF，在语料库中出现该关键词的文档数)赋予不同的权重。

$\textcircled{1}$ 位置权重 $( w _ { p } )$ ：根据位置重要性从高到低赋予其不同的权重值[9,12],Whead=7、Wtile=6、Witem=5、Wbegin=4、Wlead=3、$w _ { e n d } = 2$ 、 $w _ { p l a i n } { = } 1$ ·

$\textcircled{2}$ 词频权重 $( w _ { t } )$ ：取关键词词频的自然对数 $w _ { t } { = } \ln T F$

$\textcircled{3}$ 文档频次权重 $( w _ { d } )$ ：取关键词文档频次的自然对数$w _ { d } = \ln D F _ { \circ }$

关键词总权重 $W = w _ { p } + w _ { t } + w _ { d } ,$ 其中 $w _ { p }$ 和 $w _ { t }$ 反映关键词在所属文档中的局部重要性, $w _ { d }$ 反映该关键词在语料库中的全局重要性，综合权重 $W$ 反映了该关键词在整个领域发展规划中的重要性。

# 3.2 趋势分析

集成全球各国对未来某个领域发展趋势、潜力、机遇的判断分析，可以预测该领域在世界范围内的总体长期发展趋势，本研究使用开源工具Timeflow进行可视化呈现，将属于同一领域的愿景(Classification_1$\scriptstyle =$ “vision")及趋势(Classification $2 { \ : } = { \ : }$ “trend& potential&opportunity"）信息在时间（Time)轴上分类(Classification_3)呈现，并用权重标识关键词节点大小，用不同颜色标识分类指标(Classification_4)。其中时间和权重计算方法同需求分析。

# 3.3 路线分析

为了预判某个领域的技术发展走向，集成全球各国在该领域的未来发展路线规划信息，本研究使用Gephi[13]，将各国在同一领域的技术选择及其目标按时间规划节点呈现，关键词作为节点标签，关键词之间的句内共现关系作为边。因为内容核心信息中的关联术语词是所在句子包含的全部术语关键词，因此可以利用同一句子编码的关键词和关联术语词两个字段构建边关系，本研究采用Python编程实现关键词网络的构建，主要算法步骤如下。

# (1)技术发展态势分析

$\textcircled{1}$ 筛选某个领域(Area)，集成分析各国路线(Classification_ $\scriptstyle 1 = { \dot { } }$ “pathway")规划中各时间阶段(Time)的技术(Classification $3 { = }$ “technology")发展趋势、潜力、机遇(Classification_ $2 { = } ^ { \circ }$ 'trend $\&$ potential&opportunity")的关键词$( k w _ { i } )$ 、权重 $( w _ { i } )$ 和关联术语 $( r t _ { j } )$ 信息；

$\textcircled{2}$ 构建关键词网络，遍历每个关键词 $k w _ { i }$ if已存在节点Nodekwi $N o d e _ { k w _ { i } }$ 的权重 $w _ { k w _ { i } } = w _ { k w _ { i } } + w _ { i }$ else 新增节点 $N o d e _ { k w _ { i } }$ ，权重 $w _ { k w _ { i } } = w _ { i }$ 遍历每个关联术语词rtj if已存在kwi到rtj的边Edgekwi,rj

$E d g e _ { k w _ { i } , r t _ { j } }$ 的权重 $w _ { k w _ { i } , r t _ { j } } = \ w _ { k w _ { i } , r t _ { j } } + 1$ else

新增 $E d g e _ { k w _ { i } , r t _ { j } }$ 的权重 $w _ { k w _ { i } , r t _ { j } } = 1$

$\textcircled{3}$ 输出每个节点 $N o d e _ { k w _ { i } }$ 及其对应的权重 $w _ { k w _ { i } }$ 到文件node_trend.txt，输出每条边 $E d g e _ { k w _ { i } , r t _ { j } }$ 及其权重 $w _ { k w _ { i } , r t _ { j } }$ 到文件 edge_trend.txt;

$\textcircled{4}$ 将node_trend.txt和edge_trend.txt导入Gephi，用节点权重 $w _ { k w }$ 标识节点标签大小和颜色深浅，边权重 $w _ { k w , \ r t }$ 标识边的粗细和颜色深浅。

# (2）技术发展方向分析

$\textcircled{1}$ 筛选某个领域(Area)，集成分析各国路线(Classification_l $\scriptstyle 1 = ^ { \circ }$ ‘pathway")规划中的技术(Classification_ $3 \mathrm { = }$ "technology")发展目标(Classification_ $2 { = }$ “need&target")的关键词、权重(Weight)和关联术语(Relative_terms)信息;

$\textcircled{2}$ 构建关键词网络文件并导入Gephi可视化，方法与态势分析相同。

# (3）技术发展路径分析

筛选某个技术关键词(Keyword)，对比分析全球各国针对该项技术发展路径(Classification $1 =$ “pathway")的不同目标(Classification_ $2 { = }$ "target")规划,使用Timeflow按时间轴("Time")呈现不同国家("Object")的发展路径。

# 3.4 战略分析

为对比分析全球各国在同一领域的战略规划，如发展愿景、路线和采取的相应措施，使用开源工具Timeflow对所关注国家在特定领域的相关战略信息进行全面可视化分析，并按时间序列(以"time"为横轴)分类(以"Classification_3"为纵轴)呈现，用权重(W)标识关键词节点大小，用不同颜色标识分类指标(Classification_4)。选择某个领域(Area)和关注对象(Object)，集成其在政策、经济、技术、市场等各方面(Classification_3)的信息，分析关注对象在该领域的发展愿景、路线及措施，具体分析目标及其实现配置如表3所示。

表3针对关注对象在某个领域的战略分析参数设置  

<html><body><table><tr><td>功能目标</td><td>参数设置</td><td>公共配置</td></tr><tr><td>发展愿景 分析</td><td>Classification_1="vision”; Classification_2="target";</td><td>x轴:time; y轴:Classification_3;</td></tr><tr><td>发展路线 分析</td><td>Classification_1="pathway"；权重:Weight; Classification_2="target";</td><td>颜色：Classification_4;</td></tr><tr><td>发展战略 分析</td><td>Classification_1="action”; Classification_2="target & need&barrier&enabler";</td><td>节点：Keyword; 详情：鼠标悬停节点显 示原句及所属全部信息 字段;</td></tr></table></body></html>

# 4科技路线图集成分析结果可视化

本研究以可再生能源领域(Renewable Energy)为例，集成全球针对该领域发布的科技路线图信息，分析可再生能源领域的发展现状和趋势，未来发展的关键技术，以及不同国家在该领域的技术选择和拟采取的战略措施。

# 4.1 需求分析示例

集成各国在可再生能源领域的现状需求信息，并利用Timeflow进行可视化，如图3所示，可以看出该领域的发展需求包含技术(Technology)、市场(Market)、政策(Policy)、环境(Environment)和经济(Economy)方面，且主要是技术、市场和政策需求。

(1）技术方面：主要是性能(performance，橙色)和成熟度(maturity，品红色)，如：提高太阳能集热器的性能、先进生物燃料的商业化等;(2）市场方面：主要是生产(production，红色)和消费(consumption，深红色)，如：增加发电量、可再生能源份额、能源需求量等;(3）政策方面：主要是规划(plan，绿色)和支撑(support，蓝色)，如加强光伏研究、制定国家能源计划、增加水电站项目等。

![](images/b64fc4961fb88b238fc11f18455b369309476af794c78f7f7efe34b06fcfac0f.jpg)  
图3可再生能源领域的发展需求  
(注：参数设置Classification_1 $\scriptstyle = { \mathfrak { e } }$ “today”,Classification_ $\ ? = \ "$ ‘need",Year $\scriptstyle \geqslant 2 0 1 5$ ）

# 4.2 趋势分析示例

集成各国在可再生能源领域的发展愿景趋势信息，利用Timeflow可视化如图4所示，可以看出该领域的发展趋势包含市场(Market)、技术(Technology)、环境(Environment)、政策(Policy)、经济(Economy)、社会(Social)等方面，且主要是技术、市场和环境趋势。

(1）市场方面：主要是生产(production，红色)和消费(consumption，深红色)，如：增加可再生能源份额、发电量，降低价格、增量成本等;

(2）技术方面：主要是性能(performance，橙色)和成本(cost，黄褐色)，如：内置热存储、光伏发电、发电厂效率、降低投资成本等;

(3）环境方面：主要是排放(emission，青色)和资源(resource，紫色)，如减少温室气体排放、扩大可再生资源的开发等。

# 4.3 路线分析示例

# (1）技术发展态势

集成全球可再生能源领域的技术(Technology)发展趋势(Trend)、潜力(Potential)、机遇(Opportunity)等信息，利用Gephi进行可视化，如图5所示，呈现了2015至2050年可再生能源领域的技术发展态势。从图中可以看出该领域的发展态势主要围绕聚焦式太阳能(CSP)、生物质能(biomass)、光伏(PV)、风能(windpower)等技术，包括技术成本(cost)、碳排放 $\left( \mathrm { C O } _ { 2 } \right)$ 、发电量(power)等方面的性能提升。

![](images/3242a412e443a51350478ef00d6a35a95b0b122067733ff4856ca74fe3d12135.jpg)  
图4可再生能源领域的发展趋势  
图5可再生能源领域的技术发展态势

(注：参数设置Classification_ $1 = ^ { \circ }$ ‘vision”,Classification_ $2 = ^ { \circ }$ "trend& potential&opportunity",Year ${ \geqslant } 2 0 1 5$ ）

2015 2020 solarradiatio@measurement UAV PV baseloads CO2eapes systems wholesale eleotricityprices OBM CSP 0D2   
BLUE MaScenario GBG ossfuels Luegas CSP nergy FITs soheme intkeyrenewable electrcty OBP bloels newcapacityeeraiots renewable ene@y tech ogies wind@ower offshorewind BisystemOffshore Wind power Referee Case ngs commerc scale renewable electricity LCOE biomass bioeglergy ubec@ naturalgas @oling easo residentiasystems hydropower   
2030 new-built@paftop PV biodelsgeothemal heat liqui@fuelfossi fuel 2050 cost reductionnd @nergy transport fuel CSP solar dist@ct heating CSP@lants fuel-power baekup capacity utility-alePV low-carbon al HVDCrenewable electicity generation CSPplants heatingourposes bioeneyheat transpartLCO OSOAP CSP feeilities solarlituct natural gas renewableenergy solarectricity power REmapSplon ndustrisenergy ieespaceetintts talstoc turnover ouil ReferenceCase heatumbuitdingsectorwee Pofepeplan transpoitsector nerguprices performaceratiosaverageVLCOE solar themlt etativeemissistnreprects windturbi@ecapacity biomass airpoution new-bult planteE TEEC002 newablergyptetleg fossilfuelplants windlarms enhanced geotiermalsystems total@apital pesys Rbusinsssenario themiietrsti renewallepiwaerindowaowerco-produchotwater biofuelpoductiodvancedbiofuelsers d water gaswindapacity larger-scaleRyapplications transmisSoncostiquid@ofuels northe China electric@ehicles biofels

(2)技术发展方向

集成全球各国可再生能源领域的技术(Technology)发展目标(Target)信息，利用Gephi进行可视化，如图6所示，呈现了2015至2050年可再生能源领域的技术发展方向。从图中可以看出该领域的技术发展方向主要集中在聚焦式太阳能发电(CSP)、光伏(PV)、水电(hydropower)、风电(wind power)、生物质能(biomass)、生物燃料(biofuel)等技术在交通(transport)、建筑(building)、热力(heating)等方面的应用。

# (3）技术发展路径

选则某个技术关键词，对比分析全球各国针对该项技术发展路径(pathway)的不同目标(target)规划，用Timeflow进行可视化。图7呈现了可再生能源领域4种主要技术：聚焦式太阳能发电技术(CSP)、碳捕获与储存技术(CCS)、风电技术(wind power)和光伏技术(PV)，在不同国家的发展路径规划。以CSP为例，鼠标悬停在每个节点，可以了解该技术在该时间点的相关发展状态信息，对比各国该项技术的发展路径。

2015 2020 hydrapower reasonable s@ar irradiation new cpacity residenti@systems near steil biomass scalerenewle-electricity solar radiatio@ leep biocgergy advanced bio@el-production spacants offshole wind FITssBhemecommercial-scal@advanced biofuel land-us@change ityfactor ygrk hydropower 营 plants e S   
solarr@diation wind Durce atstoe RES 邮 poworeystems windooweric riverasin SPgian capaity hydropowhelopment PA oal storage land-basedBvind power fossifuejs UAE baseoads C02 base-ldpower nevPsp PSP globa ergy rage@pacities intermediate loads water qualy impact 中 UBV Lo CSP Referere Case CSPpr sunniest Bountries clea@ke 中 solarrBourceso renewabeenergy E solarts bulkeower C02 cheaposgsystems RefereeCeRD Beating hid solaer hydropo@er plants natuel gas solar thermi collectors solareleagicity-cost keyrenewalle electricity DECCnalysis LGDE electricity gegeration costs   
2030 renewa@powe 2050 renewable @ergyplants RD transpet fuol solalheat avaiabr@hotrock biorewabeyaty Cocedaneofu VLCOE wind@owe 业 F bioDels onnat sys ansmi end-us@sectors sinangpiants OSP solardis LODE 中 002 solart 电 total@pital   
solar thecacitypion solar PYndustsector PSP CSP fities coal-ng pants csPotr wiwindgocinoignag renewableenergybasss bioedergy scaleapp 中 OPP solargoals additiolcosts enewalenergy hh@OLM fossfuel powersector Pptionsranport mass @ductisolarating p@spectives REmap totalrenv@bleenergy IndistrLO buildinesector naturatgas grid hil-Ren@enario Strent Cs electyrid OS ialaa total pd atuesgas ne ung gas solarc dustralplitionsCostedtions 心 sector transpatsector transportBonsector wptergb alscenario solartwater vestm@ntcosts hotGater fossil-plants solarglants electric@ehicles RBD spaceBeatinghating wator rt powedpl space.heio solar spa heating solaheat 会 gest e@rgyuser

![](images/b471be89a4ef60cfcea17c7e5dd6e6cd2a73dec4a09003572bec96f168207005.jpg)  
图6可再生能源领域的技术发展方向  
图7可再生能源领域的技术发展路径

$\textcircled{1}$ 南非(South Africa):太阳能装机容量 2012年$1 0 0 \mathrm { M W } {  } 2 0 1 5$ 年 $5 0 0 \mathrm { M W } {  } 2 0 2 0$ 年 $1 . 2 \mathrm { G W } {  } 2 0 2 5$ 年1.5GW${  } 2 0 3 0$ 年2.6GW;

$\textcircled{2}$ 全球(World)：2050年太阳能装机容量650GW，发电量达到 $2 2 0 0 \mathrm { T W h }$ ,CO2排放减少 $50 \%$ $\textcircled{3}$ 阿联首(UAE):2030年降低CSP成本;

# 4.4 战略分析示例

对比分析美国和中国在可再生能源领域的发展愿景、路线和措施，使用Timeflow对两国在该领域的相关战略信息进行全面可视化分析，如图8所示。

![](images/92bd2b838781810185b33edecde6de02002eec3817e0c9b2f0fe886d7516faf2.jpg)  
图8中美可再生能源领域的发展战略对比

(1）发展愿景对比

$\textcircled{1}$ 美国在可再生能源领域的发展愿景，包含市场、政策、技术、环境、经济等方面，且主要是市场、政策和技术目标。

1)市场方面：主要是生产(production，红色)，如：增加可再生能源发电量、扩大可再生能源份额等;

2)政策方面：主要是规划(plan，绿色)，如：可持续发展能源计划、修建可再生能源发电厂等;

3)技术方面：主要是性能(performance，橙色)，如提高太阳能、风能效率等。

$\textcircled{2}$ 中国在可再生能源领域的发展愿景，包含市场、政策、技术、经济、社会、环境等方面，且主要也是市场、政策和技术目标。

1)市场方面：主要是生产(production，红色)和消费(consumption，深红色)，如：增加可再生能源发电量、装机容量，风电价格低于煤电价格，降低风力发电成本等;

2)政策方面：主要是规划(plan，绿色)和支持(support，蓝色)，如：制定风力发展战略、激励电网公司购买再生电力等;

3)技术方面：主要是成熟度(maturity，品红色)，如提高风力发电技术、大型风电场、海上风电场技术等。

# (2）发展路线对比

$\textcircled{1}$ 美国在可再生能源领域的发展路线，包含技术、环境、政策和市场。

1)技术方面：主要是性能(performance，橙色)，如提高风能、太阳能效率；

2)环境方面：主要是排放(emission，青色)，如相比2005年，减少 CO2 排放 $\lvert \lvert \lvert \xrightarrow { } 2 0 2 0$ 年 $( 1 7 \% ) {  } 2 0 2 5$ 年 $( 2 6 \% { \sim } 2 8 \% ) {  }$ 2030年 $( 3 3 \% ) {  } 2 0 5 0$ 年 $( 8 0 \% )$

3)政策方面：主要是规划(plan，绿色)，如制定加速可再生能源发展的路线;

4)市场方面：主要是生产(production，红色)，如：增加可再生能源份额2010年 ${ \sim } 2 0 3 0$ 年 $ 2 6 \%$ ，增加向岸风能装机容量2014年 $( 6 3 \mathrm { G W } ) {  } 2 0 3 0$ 年(314GW)。

$\textcircled{2}$ 中国在可再生能源领域的发展路线，包含技术、市场、政策、社会、环境等方面，且主要是技术、市场和政策。

1)技术方面：主要是性能(performance，橙色)和成熟度(maturity，品红色)，如2010年 ${ \sim } 2 0 1 5$ 年风电容量 $1 5 \mathrm { G W } $ 2020年风电容量 $2 0 0 \mathrm { G W } {  } 2 0 3 0$ 年风电容量 $4 0 0 \mathrm { G W } {  } 2 0 5 0$ 年风电容量1TW,2010年 ${ \sim } 2 0 2 0$ 年陆地风电 ${  } 2 0 2 0$ 年 ${ \sim } 2 0 3 0$ 年近海风电 $ 2 0 3 0$ 年 $\mathord { \sim } 2 0 5 0$ 年远海风电和微观选址技术;

2)市场方面：主要是生产(production，红色)和消费(consumption，深红色)，如：2020年风电替代130mtce(百万吨煤当量） $\phantom { - } \lvert \to 2 0 3 0$ 年风电可替代 $2 6 0 \mathrm { m t c e } {  } 2 0 5 0$ 年风电可替代 660mtce;

3)政策方面：主要是规划(plan，绿色)，如制定可再生能源发展战略。

# (3）发展措施对比

$\textcircled{1}$ 美国在可再生能源领域的发展措施，包含政策、经济、技术、环境、市场等方面，且主要是政策、经济和技术措施。

1)政策方面：主要是支撑(support，蓝色)，如：支持可再生能源技术的研发;

2)经济方面：主要是投资(investment，棕色)，如：每年为可再生能源技术投入860 亿美元;

3)技术方面：主要是性能(performance，橙色)，如：提高能源载体、太阳能光伏性能。

$\textcircled{2}$ 中国在可再生能源领域的发展措施，包含政策、市场、技术、社会、环境、经济、合作等方面，且主要是政策、市场措施。

1)政策方面：包括规划(plan，绿色)、管理(regulation，蓝绿色)、评价(evaluation，深蓝色)、支撑(support，蓝色)，如:制定可再生能源工业发展规划、电价管理法规等，提高风电技术标准、测试和认证体系，提供技术咨询、战略研究等服务;

2)市场方面：主要是市场机制，加快电力市场改革、建立风电管理和市场规则、电力定价市场化等。

# 5结语

本研究采用前期提出的文本挖掘研究方案及信息抽取方法，基于已构建科技路线图信息库，以可再生能源领域为案例集成分析世界范围内该领域的发展需求和长期发展趋势，对比分析各国技术发展路线、战略发展措施等，并利用Timeflow、Gephi等开源工具进行可视化呈现。实验结果表明，本研究方法切实可行，能够较快速地把握全球发展现状和趋势，较全面地掌握世界各国未来的长期发展路线和措施，为决策者制定符合国情的发展规划提供较全面、快速的战略情报服务。

研究尚处于方法探索阶段，仍存在不足有待改进：综合利用了多种编程语言和软件工具，受限于笔者的时间和精力，暂未实现所有工具的整合，因而自动化程度有待进一步提高；可视化均选择了开源工具的已有功能，在未来的研究中可以根据具体需求灵活订制功能，例如目前仅能实现鼠标悬停在关键词节点显示相关信息，可以增加点击关键词进人关联段落、篇章等详情页面，更多功能有待完善。

# 参考文献：

[1] 刘细文，柯春晓.技术路线图的应用研究及其对战略情报研 究的启示[J]．图书情报工作，2007,51(6):37-40,112.(Liu Xiwen，Ke Chunxiao．The Applications of Technology Roadmap and Its Enlightenment to Strategic Intelligence Research [J].Library and Information Service,20o7,51(6): 37-40, 112.)   
[2] Zhang Y,Zhang G,Chen H,et al. Topic Analysis and Forecasting forScience, Technology and Innovation:

Methodology with a Case Study Focusing on Big Data Research [J]. Technological Forecasting and Social Change, 2016,105: 179-191. [3]Amer M,Daim T U,Jetter A.Technology Roadmap Through Fuzzy Cognitive Map-Based Scenarios: The Case of Wind Energy Sector of a Developing Country [J]. Technology Analysis & Strategic Management,2016,28(2): 131-155. [4]Jin G, Jeong Y, Yoon B. Technology-driven Roadmaps for Identifying New Product/Market Opportunities:Use of Text Mining and Quality Function Deployment [J]．Advanced Engineering Informatics,2015,29(1): 126-138. [5]叶春蕾，冷伏海．技术路线图中未来技术词表构建方法研 究[J]．现代图书情报技术，2013(5):59-63.(Ye Chunlei, LengFuhai. Building the Future—Oriented Technology Thesaurus of Technology Roadmap[J]. New Technology of Library and Information Service,2013(5): 59-63.) [6]叶春蕾，冷伏海．基于词汇链的路线图关键词抽取方法研 究[J]．现代图书情报技术，2013(1):50-56.(Ye Chunlei, Leng Fuhai. Study on the Keyword Extraction from Roadmap Based on the Lexical Chains [J].New Technology of Library and Information Service,2013(1): 50-56.) [7]Amer M, Daim T U.Application of Technology Roadmaps for Renewable Energy Sector[J]. Technological Forecasting and Social Change,2010,77(8): 1355-1370. [8]Bader B,Richardson C,Tsuriya M. Technology Roadmap Overviewsand Future Direction through Technology Gaps[C]// Proceedings of the 2015 International Conference on Electronics Packaging.2015. [9]谢秀芳，张晓林．针对科技路线图的文本挖掘研究框架及 特征分析[J]．情报科学．（待发).(Xie Xiufang，Zhang Xiaolin. Text-mining Framework and Feature Analysis on Science and Technology Roadmap [J]. Information Science. In Press.) [10] 谢秀芳，张晓林．针对科技路线图的文本挖掘研究：信息 抽取方法[J].情报理论与实践.(待发).(Xie Xiufang,Zhang Xiaolin．The Research on Text-mining of Science and Technology Roadmap: Method of Information Extraction[J]. Information Studies: Theory & Application.In Press.) [11]Timeflow [EB/OL].[2016-07-22]. htps:/github.com/FlowingMedia/ TimeFlow/wiki. [12] 史磊，王永成．英文文献自动摘要系统的研制与开发[J]. 高技术通讯,199,9(11): 22-26.(Shi Lei, Wang Yongcheng. Research and Development of an Automatic Abstracting System for English Documents [J]. Chinese High Technology Letters,1999,9(11): 22-26.) [13]Gephi [EB/OL].[2016-07-22]. htps://gephi.org/.

# 作者贡献声明：

谢秀芳：设计研究方案，采集、清洗和分析数据，撰写论文;  
张晓林：确定研究方向，提出研究思路，修改论文。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

[1]谢秀芳，张晓林.Keywords-network.py.关键词网络构建代码.[2]谢秀芳，张晓林．data-20160608-timesplit.csv．需求分析(图3)、趋势分析(图4)、路径分析(图7)、战略分析(图8)支撑数据集.[3]谢秀芳，张晓林．Keywords_trend.rar、node_trend.rar、edge_trend.rar.技术发展态势分析支撑数据(图5).[4]谢秀芳，张晓林．Keywords_VsTg.rar、node_VsTg.rar、edge_VsTg.rar.技术发展方向分析支撑数据(图6).

# 支撑数据：

支撑数据由作者自存储,E-mail:xiexiufang@mail.las.ac.cn。

收稿日期:2016-09-30  
收修改稿日期:2016-11-02

# Integrated Analysis and Visualization of Sci-Tech Roadmaps: Case Study of Renewable Energy

Xie Xiufang1,²Zhang Xiaolin1 1(National Science Library, Chinese Academy of Sciences, Beijing 100190, China) ²(School of Health Management and Education, Capital Medical University/ Library of Capital Medical University，Beijing 10o069, China)

Abstract:[Objective] This study aims to predict the development trends of science and technology (S&T） with knowledge extracted from S&Troadmaps (STR).[Methods]First,we constructed anSTR information database based on the“extraction-synchronization-classification”method of text mining.Second,we analysed the demands and trends of global S&T progres.Finally,we compared and analyzed different countries’S&T strategies in the field of renewableenergy.[Results] We used open source tools,such as Timeflow,Gephi to visualize the results of this case study,such as the globle development trends and nationalstrategic planning in the field of renewable energy by 2050. [Limitations] The automationand personalization features of this study need to be improved.[Conclusions] The proposed method could retrieve strategic intelligence from the STRs effectively.

Keywords: Science and Technology RoadmapStrategic IntelligenceText Mining Knowledge Discovery Integrated AnalysisInformation Visualization