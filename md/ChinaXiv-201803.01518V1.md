# 基于风险值自动计算一信息多维采集的农药残留大数据评估市售果蔬安全水平

庞国芳1\* 梁淑轩² 常巧英1 申世刚² 徐建中² 范春林李 慧² 白若镔

1中国检验检疫科学研究院北京1001762河北大学化学与环境科学学院保定0710023北京合众恒星检测科技有限公司北京 100176

摘要采用食品安全指数和风险系数模型，初步建立了农药残留膳食暴露风险和预警风险评估体系。开发“风险值自动计算—信息多维采集与分析”定制软件，基于2012—2015年我国市售果蔬农残检测大数据，从农药种类、限量标准、果蔬种类、地域等多个维度，分别对果蔬中残留农药之于人体的膳食暴露风险、预警风险进行了评估和解析。结果显示，气相色谱-四极杆-飞行时间质谱（GC-Q-TOF/MS）和液相色谱-四极杆-飞行时间质谱（LC-Q-TOF/MS）技术侦测的9823例和12551例市售果蔬，绝大多数膳食风险为可接受，但仍有 $0 . 5 6 \%$ 和 $0 . 5 4 \%$ 为风险不可接受。禁用农药膳食暴露风险不可接受比例是非禁用农药的20倍（GC-Q-TOF/MS组）和55倍（LC-Q-TOF/MS组）；禁用农药高度预警风险比例是非禁用农药的17倍（GC-Q-TOF/MS组）和23倍（LC-Q-TOF/MS组），可见农药残留风险亟需控制，尤其应严格监管“禁药禁用”。文章据以上评估给出了高风险排名前10的农药和果蔬。另外，还发现欧盟的农药最大残留限量标准（MRLs）明显严于我国，我国相关标准建立亟待加快。研究结果可作为果蔬等食品风险水平实时诊断和风险农药精准监管的重要依据，以减少食源性农药残留风险，保障食品安全。

关键词大数据融合技术，信息多维采集，农药残留，膳食暴露风险，预警风险 DOI 10.16418/j.issn.1000-3045.2018.03.012

农产品中的农药残留作为最突出的食品安全问题之一，对食品安全的影响一直是国内外共同关注的热点问题[1-3]。农药残留风险评估是农产品质量安全风险评估的重要组成部分，是食品质量安全管理的国际通行做法；同时，也被认为是继食品卫生质量管理体系和危害分析关键控制点（HACCP）技术之后，在食品安全管理领域掀起的第三次浪潮[4,5]。国外农药残留风险评估起步较早，20世纪30年代以来，美国出台了一系列法案开始对食品中的农药进行登记，并引入了“风险杯”概念，较早地开展了农药风险评估；1986年美国EPA发布了针对化学物质的风险准则[6]，并公布了风险评估过程和相关数据库[；1995年，联合国粮农组织（FAO）/世界卫生组织（WHO）农药残留联合专家会议（JMPR）就已制定了急性毒性物质的风险评估和急性毒性农药残留摄入量的预测[8]；2010年，WHO发布了《食品中化学物的风险评估原则和方法》[9。此外，欧盟、澳大利亚、韩国、巴西等国也分别开展了本国或本区域的农药残留风险评估计划[5]

我国污染物风险分析可以追溯到20世纪60年代六六六和滴滴涕等有机氯农药残留量标准的研究[10],2006年《农产品质量安全法》和2009年《食品安全法》颁布，明确要求开展食品安全风险监测与评估。2012年陈君石院士主审出版了《食品中化学物的风险评估原则和方法》WHO方法中文译本[],其中包括膳食暴露评估、急性毒性的评估等内容，推动了我国风险评估工作与国际接轨。

在风险评估中，风险指数（HI/HQ/RQ）是评价食品安全状态的方法，已应用于果蔬[12]、粮食[13]、坚果[4]中残留农药风险评估。2002年，我国研究人员在对国际公认的国际食品法典委员会（CAC）评价方法、全球环境监测系统/食品污染监测和评估规划（WHOGEMS/Food），以及FAO/WHO食品添加剂联合专家委员会（JECFA）和JMPR对食品安全风险评估工作研究的基础之上，结合残留监控和膳食暴露评估，提出了以食品安全指数（IFS）计算食品中各种化学污染物对消费者健康危害程度的方法[15]。食品安全指数（IFS）是表示食品安全状态的方法，可有效地评价某种农药的安全性，进而评价食品中各种农药类化学污染物对消费者健康的整体危害程度[16-18]，其优点在于使用默认的标准假设或者模型，操作简单且结果容易被接受和理解[19.20]。采用IFS值进行食品安全状态评估的基础是要取得准确的和有代表性的残留监测数据[21]、每日允许摄入量（ADI)

和急性参考剂量（ARfD）值以及食物消耗量等数据。JMPR、EFSA、EU、WHO农药数据库提供了农药化合物的 ADI 及ARfD 值[2-25]，EFSA、WHO/GEMS/FOODS 同时提供了食物消耗量的数据[26,27]。

2003年，我国研究人员根据WHO的有关原则和我国的具体规定，结合危害物本身的敏感性、超标率及其相应的施检频率，提出了食品中危害物风险系数（R）的概念[21]。 $R$ 表示一定时期内某一危害物超标率或阳性检出率的高低，是衡量危害物风险程度大小的最直观参数[28]。目前，我国已初步建立了农产品农药残留风险评估技术框架体系，但食品质量安全方面的研究仍相对薄弱。从已有文献来看，食品农药残留系统性风险评估报道不多。

为了系统、真实地反映我国百姓餐桌上水果、蔬菜的农药残留水平及其健康风险，笔者团队经过多年努力，研发了以高分辨精确质量数为电子识别标准的气相色谱-四极杆-飞行时间质谱（GC-Q-TOF/MS）和液相色谱-四极杆-飞行时间质谱（LC-Q-TOF/MS）高通量非靶向侦测1200 种农药化学污染物的高通量筛查技术，并对2012一2015年全国市售果蔬中的农药残留进行了全面侦测，得到我国市售果蔬农药残留水平大数据[29]。在农药残留大数据和IFS模型、风险系数模型基础上，本文编制了“风险值自动计算一信息多维采集分析”专业定制软件，融合大数据技术，开发了农药残留膳食暴露风险和预警风险评估体系。将其应用于全国果蔬农药残留的风险评估，以从农药种类、限量标准、果蔬种类、地域进行食用风险的系统评估，全面反映果蔬中农药残留产生风险的水平和规律，为推进农药监管的规范化、制度化提供支撑，同时为消费者膳食摄入提供科学指导。

# 1风险评估体系的构建

# 1.1风险评估模型

# 1.1.1果蔬农药残留膳食暴露风险评估模型

本文采用我国民众平均体重（bw） $6 0 ~ \mathrm { k g }$ ，每日摄入食品（ $F _ { i } ^ { \setminus }$ 1 $0 . 3 8 ~ \mathrm { k g / \Omega }$ （人·天），以及本研究组2012—

2015年对全国果蔬的农药残留侦测结果 $( \mathbf { \nabla } R _ { i } )$ ，计算农药c的食品安全指数 $\mathrm { I F S } _ { \mathrm { c } }$ ，并以此表征该果蔬的膳食风险程度：

$$
\mathrm { I F S c } = \frac { \mathrm { E D I } _ { \mathrm { c } } \times f } { \mathrm { S I } _ { \mathrm { c } } \times \mathrm { b w } } \mathrm { ~ } \mathrm { ~ c ~ }
$$

其中：EDI。为农药c的实际日摄入量估算值;$\scriptstyle \mathrm { E D I } _ { \mathrm { c } } = \sum ( R _ { i } \times F _ { i } \times E _ { i } \times P _ { i } )$ ， $i$ 为食品种类， $R _ { i }$ 为食品 $i$ 中农药c的残留水平（单位： $\mathrm { m g / k g }$ ）， $F _ { i }$ 为食品 $i$ 的日摄入量（单位：g/(人·天)）， $E _ { i }$ 为食品 $i$ 的可食用部分因子（ $\scriptstyle { E _ { i } = 1 }$ ），$P _ { i }$ 为食品 $i$ 的加工处理因子（ $P _ { i } { = } 1$ ）； $\mathrm { \ S I _ { c } }$ 为安全摄入量,采用《食品安全国家标准食品中农药最大残留限量》（GB 2763-2016）中的ADI值[3]，此时校正因子f=1。

值 $\mathrm { I F S } _ { \mathrm { c } } { \le } 0 . 1$ 、 $\in ( 0 . 1 , 1 ]$ 和 $^ { > 1 }$ 分别代表含农药c的果蔬的膳食暴露风险为：对人体没有影响、影响可接受和影响不可接受。当果蔬中存在多种农药时，使用 $\mathrm { I F S } _ { \mathrm { c } }$ 的平均值IFS评价果蔬安全情况，即该水果或蔬菜的膳食风险程度。值IFS ${ \underline { { \underline { { \mathbf { \Pi } } } } } } 0 . 1$ 、 $\in ( 0 . 1 , 1 ]$ 和 $^ { > 1 }$ ，分别代表某一果蔬样品对人体的膳食暴露风险程度为：没有影响、影响可接受和影响不可接受。

# 1.1.2果蔬农药残留超标预警风险评估模型

本研究进而计算了农药残留的预警风险系数 $R$

和欧盟标准，这一方面因为中国的MRLs值尚不健全必须引入欧盟标准才可全面计算，另一方面二者对比以期支撑我国已有MRLs标准的进一步优化。

# 1.2风险评估软件开发

# 1.2.1软件开发基本要求

（1）膳食暴露风险评估专业软件。软件应能分别计算 GC-Q-TOF/MS 和LC-Q-TOF/MS 方法侦测出的果蔬样品中每种农药的IFS.值，进而按 $\mathrm { I F S } _ { \mathrm { c } }$ 值大小排序，重点分析膳食暴露风险高的样本，并对风险程度进行多维度解析。

（2）超标预警风险评估专业软件。分别采用MRLs的中国国家标准和欧盟标准，逐个计算不同果蔬中不同农药的风险系数R，并将结果按照禁用农药和非禁用农药分别列表，对风险程度进行多维度解析。

# 1.2.2 软件开发方法

Python语言是兼具解释性、编译性、互动性和面向对象的脚本语言，本研究选用Python语言进行编程。风险评估专用程序主要功能包括：分别读入每例样品GC-QTOF/MS 和LC-Q-TOF/MS侦测的农药残留状况数据；根据风险评估工作要求，对不同农药种类、限量标准、果蔬种类、地域等的 $\mathrm { I F S } _ { \mathrm { c } }$ 值和 $R$ 值进行计算；与MRLs的中国国家标准和欧盟标准限值进行对比，筛选出超标农药，并单独分析；再分别按不同农药、不同果蔬种类分类处理，编写自动计算和排序的计算机代码；最后将生成的膳食暴露风险评估和超标预警风险评估结果列入设计好的各个表格中；定性判断风险对目标的影响程度。

$$
R = a P + \frac { b } { F } + S _ { \mathrm { ~ o ~ } }
$$

其中， $P$ 为该种危害物的超标率； $F$ 为对危害物的施检频率，本文涉及的侦测数据 $F { = } 1$ ; $s$ 为危害物的敏感因子;a、 $b$ 分别为相应的权重系数。据相关资料，本次评价中 $S { = } 1$ ， $a { = } 1 0 0$ ， $b { = } 0 . 1 ^ { [ 2 1 , 2 8 ] }$ 。 $R$ 值 $\leq 1 . 5$ 、 $\in ( 1 . 5 , 2 . 5 ]$ 和 $>$ 2.5分别表示该种危害物的预警风险程度为低度、中度和高度。

计算 $P$ 时，首先判断农药是否为禁用农药。若为禁用农药，检出即为超标，则 $P =$ 能检出的样品数/总样品数。若为非禁用农药，则 $P =$ 超标的样品数/总样品数。超标是指危害物含量高于最大残留限量标准值（MRLs），本研究中MRLs又分别采用中国国家标准[30]

将本研究开发出的上述定制软件命名为“风险值自动计算一信息多维采集分析”专业软件。该软件通过多维大数据融合技术，自动获得不同维度的果蔬膳食暴露风险和超标预警风险评估结果。

# 1.3果蔬农药残留侦测原始数据

采用GC-Q-TOF/MS 和LC-Q-TOF-MS 两种高效筛查技术，在2012—2015年对我国42个城市（27个省会城市、4个直辖市及11个果蔬主产区）的果蔬样品中农药化学污染物分别进行了非靶向筛查。GC-Q-TOF/MS侦测了来自471个采样点的9823例样品，涉及果蔬106种，共检出农药329种（禁用农药24种 $+$ 非禁用农药305种）20 412频次，样品的农药检出率为 $5 4 . 0 \% { \ - } 9 6 . 9 \%$ ，检出农药以杀虫剂、杀菌剂和除草剂最多，分别为137、98 和78种。LC-Q-TOF/MS侦测了来自635个采样点的12551例样品，涉及果蔬121种，检出农药174种（禁用农药12种 $+$ 非禁用农药162种）25486频次，样品的农药检出率为 $3 9 . 3 \% { - } 8 8 . 0 \%$ ，检出的农药种类也为杀虫剂、杀菌剂和除草剂最多，分别为72、58和33种。

# 2果蔬膳食暴露风险评价

# 2.1单种果蔬中单种农药的膳食暴露风险

利用本研究开发的“风险值自动计算一信息多维采集分析”软件计算果蔬中农药c的 $\mathrm { I F S } _ { \mathrm { c } }$ 值。按IFS.值区间范围（ $\underline { { \le } } 0 . 1$ 、 $\in ( 0 . 1 , 1 ]$ 和 ${ > } 1$ ）作图，得出全国果蔬中单频次农药残留膳食暴露风险的评估结果（图1）。由图1可知，利用GC-Q-TOF/MS 技术得到的20412频次侦测结果中，有114频次（ $0 . 5 6 \%$ ）风险为对人体不可接受，共涉及20种农药，其中出现频次最高的农药是氟虫腈和甲拌磷，两者均为禁用农药。利用LC-Q-TOF/MS 技术得到的25486频次侦测结果中，138频次（ $0 . 5 4 \%$ ）的风险为对人体不可接受，共涉及20种农药，出现频次最高的为克百威、甲拌磷和氧乐果，也均为禁用农药。

# 2.2禁用农药与非禁用农药的维度

根据单频次农药的膳食暴露风险评估结果，GC-Q-TOF/MS组果蔬中，共检出禁用农药1426次，占检出总频次（20412次）的 $6 . 9 9 \%$ 。禁用农药导致的不可接受风险共有68频次，占GC-Q-TOF/MS 组禁用农药检出总频次（1426次）的 $4 . 7 7 \%$ 。检出非禁用农药18986次，占该组检出总频次的 $9 3 . 0 1 \%$ 。非禁用农药导致的不可接受风险共46频次，占该组非禁用农药检出总频次的$0 . 2 4 \%$ 。由上述数据可见，禁用农药膳食暴露风险处于不可接受水平的比例（ $4 . 7 7 \%$ ）是非禁用农药（ $0 . 2 4 \%$ ）的20倍！禁用农药的有效禁用管理亟待加强。

图1a中GC-Q-TOF/MS 组114个不可接受频次实际涉及38个果蔬样本，其中17个样本（表1）为禁用农药导致。禁用农药中，出现频次最高的是氟虫晴，其次是甲拌磷，分别为8频次和5频次。表1中，苦瓜、油麦菜、菜藁出现频次最高，苦瓜中有甲拌磷、氟虫晴和氯唑磷3种农药，菜臺和油麦菜中均为氟虫腈和甲拌磷2种农药。单种果蔬中单种农药膳食暴露风险评价结果在禁用农药和非禁用农药维度又一次说明氟虫腈和甲拌磷2种禁用农药具有高风险，对人体健康潜在危害较大，应加强管制。

同样地，根据单频次农药的膳食暴露风险评估结果，LC-Q-TOF/MS 组果蔬中，共检出禁用农药854频次，占检出总频次（25486次）的 $3 . 3 5 \%$ 。禁用农药导致的不可接受风险共有90频次，占本组禁用农药检出总频次（854次）的 $10 . 5 4 \%$ 。检出非禁用农药24642频次，占本组总检出频次的 $9 6 . 6 9 \%$ 。非禁用农药导致不可接受风险共48频次，占本组非禁用农药检出总频次的(a）农药残留原始数据由GC-Q-TOF/MS侦测；（b）农药残留原始数据由LC-Q-TOF/MS侦测

![](images/de2dcc8524c5989e2763b7654c0cb939318caa16bfd05d2b9573ebe684afbe7d.jpg)  
图1农药残留对果蔬样品安全的影响程度频次分布图

$0 . 1 9 \%$ 。禁用农药膳食暴露风险处于不可接受水平的比例（ $10 . 5 4 \%$ ）是非禁用农药（ $0 . 1 9 \%$ ）的55倍。

图1b 中LC-Q-TOF/MS 组138个不可接受频次实际涉及30个果蔬样本，其中18个（表2）为禁用农药导致，出现频次最高的禁用农药为氧乐果。表2的果蔬中，芹菜和韭菜出现频次最高，芹菜中有灭线磷、氧乐果和涕灭威3种农药，韭菜中有氧乐果和甲拌磷2种农药。这说明氧乐果和甲拌磷膳食风险高，对人体健康潜在危害大，亟待加强对其在果蔬中的使用和持久残留性进行研究。

上述禁用农药与非禁用农药维度的果蔬膳食暴露风险对比，表明禁用农药在我国市售果蔬中仍有残留，且膳食风险水平远远高于非禁用农药。因此，为保障民众健康，相关部门十分必要加大对禁用农药的管控力度，以期做到“禁药禁用”。从另一个角度而言，非禁用农药对民众造成的膳食暴露风险绝大部分属于无影响或可接受范围。

# 2.3果蔬来源地域维度

为明确我国不同省市果蔬膳食风险水平，本研究继而对全国不同省市的果蔬中农药残留膳食风险进行了对比。基于GC-Q-TOF/MS 组侦测结果，多数果蔬来源地出现了农药残留导致的果蔬膳食暴露风险不可接受，排在前5位的果蔬来源城市为海口、济南、广州、成都和郑州，其不可接受出现频次分别占该组总频次的 $4 . 0 4 \%$ 、$2 . 1 8 \%$ 、 $1 . 3 3 \%$ 、 $1 . 2 4 \%$ 和 $1 . 1 5 \%$ 。基于LC-Q-TOF/MS组侦测结果，不可接受比例排在前5位的城市（或地区）为乌鲁木齐、南京、山东蔬菜产区、郑州和西宁，不可接受比例分别为 $2 . 3 7 \%$ 、 $1 . 8 9 \%$ 、 $1 . 4 6 \%$ 、 $1 . 2 8 \%$ 和 $0 . 9 5 \%$

表1GC-Q-TOF/MS单种果蔬中单种禁用农药膳食暴露风险不可接受的样本列表  

<html><body><table><tr><td>序号</td><td>果蔬样品</td><td>导致风险不可接受的禁用农药 该农药在该果蔬中的IFS值</td></tr><tr><td>1</td><td>油麦菜</td><td>氟虫腈 8.9476</td></tr><tr><td>2</td><td>芹菜</td><td>杀扑磷</td></tr><tr><td>3</td><td>春菜</td><td>氟虫腈 2.8892</td></tr><tr><td>4</td><td>菜豆</td><td>氟虫腈 2.6628</td></tr><tr><td>5</td><td>柠檬</td><td>克百威 2.2118</td></tr><tr><td>6</td><td>苦瓜</td><td>氯唑磷 1.9079</td></tr><tr><td>7</td><td>枸杞叶</td><td>克百威 1.8470</td></tr><tr><td>8</td><td>菜臺</td><td>甲拌磷 1.7480</td></tr><tr><td>9</td><td>苦瓜</td><td>甲拌磷 1.6738</td></tr><tr><td>10</td><td>菠菜</td><td>甲拌磷 1.6566</td></tr><tr><td>11</td><td>荔枝</td><td>氟虫腈 1.4693</td></tr><tr><td>12</td><td>苦瓜</td><td>氟虫腈 1.3933</td></tr><tr><td>13</td><td>菜</td><td>氟虫腈 1.1981</td></tr><tr><td>14</td><td>油麦菜</td><td>甲拌磷 1.1388</td></tr><tr><td>15</td><td>苘蒿</td><td>氟虫腈 1.1375</td></tr><tr><td>16</td><td>叶芥菜</td><td>氟虫腈 1.0737</td></tr><tr><td>17 萝卜</td><td></td><td>甲拌磷 1.0336</td></tr></table></body></html>

# 2.4果蔬种类维度

膳食暴露风险不可接受频次前10的果蔬列于表3。GC-Q-TOF/MS 组膳食暴露风险不可接受的频次中，位居前10位的果蔬不可接受出现频次共占该组不可接受总频次的 $6 2 . 3 \%$ 。LC-Q-TOF/MS 组膳食风险不可接受频次中，位居前10的果蔬占比 $6 9 . 6 \%$ ○

由上述结果可见，这些农产品大多为市场最常见、百姓食用量较大的果蔬，而评估结果为农药残留导致的膳食暴露风险处于不可接受状态的频次都较高。这将对人体健康构成潜在的慢性威胁。此外，膳食暴露风险不可接受的果蔬种类以蔬菜为主，可见蔬菜农药残留引起的危害更应引起关注，这可能与蔬菜喷施农药后采摘期短有关。

表2　LC-Q-TOF/MS单种果蔬中单种禁用农药膳食暴露风险不可接受的样本列表  

<html><body><table><tr><td>序号 果蔬样品</td><td>导致风险不可接受的禁用农药</td><td>该农药在该果蔬中的IFS值</td></tr><tr><td>1</td><td>韭菜</td><td>氧乐果 20.8294</td></tr><tr><td>2</td><td>番茄</td><td>灭线磷 6.0167</td></tr><tr><td>3</td><td>平菇 氧乐果</td><td>4.0808</td></tr><tr><td>4</td><td>菜豆</td><td>氧乐果 3.8983</td></tr><tr><td>5</td><td>西葫芦 氧乐果</td><td>3.5706</td></tr><tr><td>6</td><td>枸杞叶 克百威</td><td>2.7499</td></tr><tr><td>7</td><td>苹果 氧乐果</td><td>2.5544</td></tr><tr><td>8</td><td>芹菜 灭线磷</td><td>2.4874</td></tr><tr><td>9</td><td>葱 氧乐果</td><td>2.3222</td></tr><tr><td>10</td><td>蘑菇 氧乐果</td><td>2.2526</td></tr><tr><td>11</td><td>甜椒 氧乐果</td><td>2.1016</td></tr><tr><td>12</td><td>芹菜 氧乐果</td><td>2.0339</td></tr><tr><td>13</td><td>韭菜 甲拌磷</td><td>1.7648</td></tr><tr><td>14</td><td>叶芥菜 克百威</td><td>1.5320</td></tr><tr><td>15</td><td>草莓 氧乐果</td><td>1.4503</td></tr><tr><td>16</td><td>大白菜</td><td>氧乐果 1.3427</td></tr><tr><td>17</td><td>芹菜</td><td>涕灭威 1.2878</td></tr><tr><td>18</td><td>苘蒿</td><td>灭线磷 1.1479</td></tr></table></body></html>

表3膳食暴露风险不可接受频次前10的果蔬  

<html><body><table><tr><td rowspan="2">排名</td><td colspan="2">基于GC-Q-TOF/MS检测方法</td><td colspan="2">基于LC-Q-TOF/MS检测方法</td></tr><tr><td>果蔬种类</td><td>不可接受频次</td><td>果蔬种类</td><td>不可接受频次</td></tr><tr><td>1</td><td>芹菜</td><td>13</td><td>韭菜</td><td>18</td></tr><tr><td>2</td><td>菜豆</td><td>12</td><td>芹菜</td><td>18</td></tr><tr><td>3</td><td>油麦菜</td><td>8</td><td>菜豆</td><td>15</td></tr><tr><td>4</td><td>菜</td><td>7</td><td>生菜</td><td>9</td></tr><tr><td>5</td><td>苦瓜</td><td>7</td><td>桃</td><td>7</td></tr><tr><td>6</td><td>橘</td><td>6</td><td>甜椒</td><td>6</td></tr><tr><td>7</td><td>韭菜</td><td>5</td><td>茄子</td><td>6</td></tr><tr><td>8</td><td>生菜</td><td>5</td><td>苘蒿</td><td>6</td></tr><tr><td>9</td><td>叶芥菜</td><td>4</td><td>菠菜</td><td>6</td></tr><tr><td>10</td><td>苘蒿</td><td>4</td><td>小油菜/葡萄</td><td>4</td></tr></table></body></html>

# 3 超标预警风险评估

根据GC-Q-TOF/MS 和LC-Q-TOF/MS 侦测的果蔬农药残留数据，计算农药残留的预警风险系数R，用于表征该种果蔬或该种农药在已侦测背景情况下的预警风险，以查明风险程度较高的农药和果蔬，进而可对其进行重点监管和风险防控。

# 3.1农药残留MRL标准维度

农药最大残留限量标准值（MRLs）是进行果蔬中农药残留预警风险评估的对照标准。本次检出农药品种共涉及6739个MRLs标准，而我国仅规定了其中的1229个，缺失率达 $8 1 . 8 \%$ ，致使一些侦测出的农药残留数据无法计算对应预警风险 $R$ 值。欧盟已经规定了全部的6739个MRLs标准限值，因而本次风险评估采用MRLs的中国国家标准和欧盟标准分别计算。

将每种果蔬中侦测出的每种非禁用农药均作为1个单一调查样本，根据该农药相应的MRLs标准值，计算其超标率和预警风险。如本文1.3节所述，原始数据中，利用GC-Q-TOF/MS 技术从106 种果蔬中侦测出305种非禁用农药，这些果蔬和农药共形成3352个本部分所述的单一调查样本。同样地，利用LC-Q-TOFMS 技术从121种果蔬中侦测出162种非禁用农药，共形成2662个单一调查样本。

GC-Q-TOF/MS组各单一调查样本的预警风险评估结果见图2a和b。对应MRLs的中国国家标准计算R值得出，高度风险和中度风险样本分别为14和17。对应MRLs欧盟标准，高度风险、中度风险样本各为782和504，分别是中国国家标准评估结果的56和30倍！这种巨大差别，主要是中国现行MRLs标准值宽泛，甚至尚无标准（缺失率 $8 1 . 8 \%$ ）造成的。LC-Q-TOF/MS组风险程度的分布见图2c和d。对应MRLs的中国国家标准进行预警风险评价，结果显示高度风险和中度风险的频次分别为11和15。以MRLs的欧盟标准进行预警风险评价，则高度风险、中度风险频次各为363和246，分别是中国国家标准计算结果的33和16.4倍。

由此可见，在GC-Q-TOF/MS 组和LC-Q-TOF/MS 组，采用中、欧两种标准得到的预警风险评价结果均表现出显著差异。表明较之欧盟相关标准，中国的农药残留限量值国家标准还有较大差距，亟待全面制定相关标准，并严格已有标准。

![](images/b61841a8c8d3110d9a3ba1e21d9e43bea557e7b3d48fe43e766a2618d6a2212f.jpg)  
图2果蔬中非禁用农药预警风险程度分布

(a）GC-Q-TOF/MS组侦测结果，配合中国MRLs值计算的预警风 险；（b）GC-Q-TOF/MS组侦测结果，配合欧盟MRLs值计算的预 警风险；（c）LC-Q-TOF/MS组侦测结果，配合中国MRLs值计算 的预警风险；（d）LC-Q-TOF/MS组侦测结果，配合欧盟MRLs值 计算的预警风险

# 3.2禁用农药与非禁用农药维度

GC-Q-TOF/MS侦测出的24种禁用农药，分布在70种果蔬样品中；LC-Q-TOF/MS侦测出的12种禁用农药，分布在67种果蔬样品中。禁用农药检出即为超标，根据超标率得出预警风险系数（图3a和b），其中处于高度风险的为：GC-Q-TOF/MS 组16 种禁用农药（分布在61种果蔬中）142个样本处于高度风险，占总样本数245个的$5 7 . 9 6 \%$ ；LC-Q-TOF/MS组8种禁用农药（分布在57种果蔬中）89个样本，占总样本数179个的 $4 9 . 7 2 \%$ ○

GC-Q-TOF/MS组侦测非禁用农药组成3352个样本，有MRLs中国国家标准值的共414个样本，涉及74种水果蔬菜中的67种非禁用农药，结果显示 $3 . 3 8 \%$ 处于高度风险。LC-Q-TOF/MS组侦测非禁用农药组成2662个样本，有MRL中国国家标准值的共516个样本，涉及82种水果蔬菜中的72种非禁用农药， $2 . 1 3 \%$ 处于高度风险。基于MRL中国国家标准预警风险情况如图3c和d。

a 90 R≤1.5低度风险 72 1.5<R≤2.5中度风险 $R { > } 2 . 5$ 高度风险 54 创区 36 18 农药 R≤1.5低度风险 25 1.5<R≤2.5中度风险 R>2.5高度风险 20 Adt 5 5 酰胖 苯线磷

由图3可见，禁用农药检出种类多，且大多处于高度风险，禁用农药的预警风险为高度风险者占比为非禁用农药该值的17倍（GC-Q-TOF/MS）和23倍（LC-Q-TOF/MS），与在本文膳食暴露风险结果相似，禁用农药的风险同样大大高出非禁用农药。

# 3.3农药种类维度

通过计算，共有硫丹、克百威、氧乐果和氟虫腈4种禁用农药以及腐霉利、威杀灵、虫螨腈等12种非禁用农

药处于高度风险（表4）。对这些农药均应加强管理，重点控制，以降低其对人体的危害风险。

# 3.4果蔬种类维度

预警风险评估结果处于高度风险前10位的果蔬列于表5。

# 4结论与建议

本文基于风险值自动计算一信息多维采集与分析的对应的预警风险；（d）LC-Q-TOF/MS组侦测出非禁用药对应的预警风险大数据融合技术，创建了膳食暴露风险和预警风险评估体系。膳食暴露风险评估结果表明，全国果蔬样品大部分处于很好或可以接受的安全状态；膳食暴露风险不可接受的频次中共涉及20种农药，其中出现频次最高的为禁用农药氟虫腈、甲拌磷、克百威和氧乐果，主要残留在韭菜、芹菜、菜豆、生菜、筒蒿和菜藁等常见的、日常食用量较大的果蔬中，这将对人体健康构成潜在的风险。禁用农药在我国果蔬中仍有残留，且膳食风险水平远远高于非禁用农药，说明了我国的农药监管体系尚不完善。在预警风险评估过程中发现，中国的MRLs标准相当匮乏，且基于中国国家标准的高度风险和中度风险频次远远低于基于欧盟标准得到的预警风险评价结果，说明欧盟制定的农药残留标准完整且严格程度远高于中国国家标准。基于本次农药残留侦测数据的风险评估结果发现的问题，本文针对农药残留基础研究和市场监管等方面提出以下4点建议。

![](images/b76929d2ee1ed325834724d0cb24a488bab46d1824a58747294b6f5ee199dcfb.jpg)

（1）加快农药残留MRLs和ADI标准的制定步伐。中国规定的MRLs标准少于欧盟，且MRLs值普遍高于欧盟值，即监控之网既少且宽泛。因此，建议加快MRLs制定步伐，并加强对现有农药MRLs标准的研究，力争将农产品中的农药残留风险降低到零水平。风险评估过程中，需要大量的农药残留及毒理学数据，ADI是评价农药安全性的首要和最终依据。然而，目前我国食品标准中农药ADI的数据相当匮乏，在本次评价涉及的448种农药中，仅有220种农药具有ADI值，而 $50 . 9 \%$ 的农药尚未规定ADI值。欧盟、日本等其他国家和地区也普遍存在ADI数据不全的问题，这对于农药残留膳食风险评估具有严重制约作用。因此，世界各国均亟待完善现有农药的ADI数据。

表4所有果蔬中高度预警风险单种农药列表  

<html><body><table><tr><td>序号</td><td>中文名称</td><td>风险系数 (R）值</td><td>风险程度</td><td>检测方法</td><td>禁用农药 备注</td></tr><tr><td>1</td><td>硫丹</td><td>8.2</td><td>高度风险</td><td>GC-Q-TOF/MS</td><td>禁用</td></tr><tr><td>2</td><td>腐霉利</td><td>6</td><td>高度风险</td><td>GC-Q-TOF/MS</td><td></td></tr><tr><td>3</td><td>威杀灵</td><td>4.8</td><td>高度风险</td><td>GC-Q-TOF/MS</td><td></td></tr><tr><td>4</td><td>克百威</td><td>4</td><td>高度风险</td><td>LC-Q-TOF/MS</td><td>禁用</td></tr><tr><td>5</td><td>虫螨腈</td><td>3.4</td><td>高度风险</td><td>GC-Q-TOF/MS</td><td></td></tr><tr><td>6</td><td>克百威</td><td>3.1</td><td>高度风险</td><td>GC-Q-TOF/MS</td><td>禁用</td></tr><tr><td>7</td><td>生物苄呋菊酯</td><td>3.1</td><td>高度风险</td><td>GC-Q-TOF/MS</td><td></td></tr><tr><td>8</td><td>多菌灵</td><td>3.1</td><td>高度风险</td><td>LC-Q-TOF/MS</td><td></td></tr><tr><td>9</td><td>新燕灵</td><td>3</td><td>高度风险</td><td>GC-Q-TOF/MS</td><td></td></tr><tr><td>10</td><td>氧乐果</td><td>3</td><td>高度风险</td><td>LC-Q-TOF/MS</td><td>禁用</td></tr><tr><td>11</td><td>仲丁威</td><td>2.9</td><td>高度风险</td><td>GC-Q-TOF/MS</td><td></td></tr><tr><td>12</td><td>烯虫酯</td><td>2.9</td><td>高度风险</td><td>GC-Q-TOF/MS</td><td></td></tr><tr><td>13</td><td>啶虫胖</td><td>2.8</td><td>高度风险</td><td>LC-Q-TOF/MS</td><td></td></tr><tr><td>14</td><td>氟虫腈</td><td>2.7</td><td>高度风险</td><td>GC-Q-TOF/MS</td><td>禁用</td></tr><tr><td>15</td><td>杀螨特</td><td>2.7</td><td>高度风险</td><td>GC-Q-TOF/MS</td><td></td></tr><tr><td>16</td><td>氟硅唑</td><td>2.6</td><td>高度风险</td><td>GC-Q-TOF/MS</td><td></td></tr><tr><td>17</td><td>双苯基脲</td><td>2.6</td><td>高度风险</td><td>LC-Q-TOF/MS</td><td></td></tr></table></body></html>

(2）加强对高毒、剧毒和违禁农药的治理。我国国家《食品安全法》已严格规定禁用农药不得用于蔬菜、瓜果、茶叶和中药材，本文结果揭示出我国农业生产违规使用高剧毒和禁用农药依然的情况未真正得到控制，这些结果直接“拷问”着《农药生产质量管理规范》《良好农业规范》以及《危害分析及关键控制点》是如何执行的，也反应着我国食品安全“四个最严”标准落地无声。因而，加强高毒、剧毒和违禁农药治理，势在必行。

(3）加强农药的生物修复降解新技术研究。大量研究表明，在向作物直接喷施农药过程中，大部分农药会直接或间接进入土壤，尤其是根际穴施的农药会直接残留在土壤介质中。从我国全区域市售果蔬中的农药残留严重超标及禁用农药高频次检出这一现状，直接反映了我国的田间土壤已经受到严重的农药污染，而且随着农药的频繁、长期、不合理使用，土壤中长期积累的一些持久性或中等持久性农药会通过地表径流、淋溶等方式进入河流、湖泊、地下水层，破坏了我国的水生生态平衡。为此，建议加强土壤、水体中持久性或中等持久性农药的生物修复及降解新技术研究，着力解决突出的农药污染问题，加强生态文明建设，推进健康中国战略的深入实施。

表5预警风险频次前10位的果蔬  

<html><body><table><tr><td rowspan="2">排名</td><td colspan="2">基于GC-Q-TOF/MS检测方法</td><td colspan="2">基于LC-Q-TOF/MS检测方法</td></tr><tr><td>果蔬种类</td><td>高度风险频次</td><td>果蔬种类</td><td>不可接受频次</td></tr><tr><td>1</td><td>芹菜</td><td>13</td><td>芹菜</td><td>8</td></tr><tr><td>2</td><td>黄瓜</td><td>10</td><td>韭菜</td><td>7</td></tr><tr><td>3</td><td>韭菜</td><td>9</td><td>青菜</td><td>7</td></tr><tr><td>4</td><td>筒蒿</td><td>8</td><td>番茄</td><td>6</td></tr><tr><td>5</td><td>梨</td><td>8</td><td>黄瓜</td><td>6</td></tr><tr><td>6</td><td>生菜</td><td>7</td><td>生菜</td><td>6</td></tr><tr><td>7</td><td>菠菜</td><td>7</td><td>苘蒿</td><td>6號</td></tr><tr><td>8</td><td>蘑菇</td><td>7</td><td>茄子</td><td>5</td></tr><tr><td>9</td><td>苹果</td><td>7</td><td>桃</td><td>5</td></tr><tr><td>10</td><td>桃/苦瓜/茄子/油麦菜</td><td>6</td><td>大白菜/西瓜/葡萄</td><td>5</td></tr></table></body></html>

（4）推广农药残留非靶向电子化监测技术。目前,世界各国农药残留定性定量采用的均是以实物标准做参比的传统方法。比如，欧盟、美国和日本农药残留监控分别采用了15种、21种和10种传统色谱和质谱检测技术，累计监控的农药品种为839种、500种和832种。而作者团队研发的“高分辨质谱非靶向高通量农药残留筛查技术”，实现了一次样品制备，仅2种技术联用即可同时完成每一例样品1200多种农药残留的全面甄别确证。该研究构建的六类色谱-质谱数据库，为世界常用1200多种农药化学品建立了独特的电子识别标准（电子身份证），以电子标准替代实物标准，实现了农药残留由靶向检测向非靶向筛查的跨跃式发展，实现了电子化、信息化和智能化。同时，针对海量农药残留数据分析的挑战，研发了高分辨质谱 $^ { + }$ 互联网 $+$ 数据科学/地理信息系统（GIS）三元跨界融合技术，实现了农药残留大数据分析智能化，农药残留风险溯源可视化，其方法效能是任何传统色谱和质谱方法无以伦比的。2012—2017年的示范应用充分证明，这是农药残留分析领域供给侧改革的重大突破，是促进农药残留监管前移的有力武器。建议推广非靶向电子化、智能化监测技术，为风险评估提供精准可靠的基础数据。

# 参考文献

1Chen X X,Li X,Pang KJ,et al.Dissipation behavior and residue distribution of fluazaindolizine and its seven metabolites in tomato ecosystem based on SAX SPE procedure usingHPLC-QqQ-MS/MS technique.JournalofHazardousMaterials,2018,342:698-704. 2Diop A,Diop YM, Thiare DD,et al.Monitoring survey of the use patterns and pesticide residues on vegetables in the Niayes zone,

Senegal. Chemosphere,2016,144: 1715-1721.   
3 Sabera A N, Malhata F M, Badawy HMA, et al. Dissipation dynamic,residue distributionand processing factorof hexythiazox in strawberry fruits under open field condition. Food Chemistry, 2016,196: 1108-1116.   
4周妍，闻胜，刘溝，等.食品中化学污染物风险评估研究进展， 食品安全质量检测学报,2014,5(6):1868-1875.   
5 平华，马智宏，王纪华，等.农产品质量安全风险评估研究进 展.食品安全质量检测学报,2014,5(3):674-680.   
6 US EPA. Guidelines for estimating exposures.Federal Register, 1986.   
7 US EPA. Human Health Risk Assessment.[2017-08-29].https:// www.epa.gov/risk/human-health-risk-assessment.   
8 高仁君，王蔚，陈隆智，等.JMPR农药残留急性膳食摄入量计 算方法.中国农学通报,2006，22(4):101-104.   
9WHO.Guidelines for the health risk assessment of chemical mixtures. 2010.   
10 陈君石.食品中化学污染物的监测.中国卫生监督杂志,1994, (1): 28-31.   
11 联合国粮农组织，世界卫生组织.食品中化学物的风险评估原 则和方法.刘兆平，李凤琴，贾旭东,译.北京：人民卫生出版 社,2012.   
12 SzpyrkaE,KurdzielA,Matyaszek A,etal. Evaluation of pesticide residues in fruits and vegetables from the region of south-eastern Poland. Food Control,2015,48: 137-142.   
13Lozowicka B, Kaczynski P,Paritova A E,et al. Pesticide residues in grain from Kazakhstan and potential health risks associated with exposure to detected pesticides.Food & Chemical Toxicology, 2014, 64(2): 238-248.   
14 Liu Y, Shen D,Li S,et al. Residue levels and risk assessment of pesticides in nuts of China. Chemosphere,2016,144: 645.   
15 李聪,张艺兵,李朝伟,等.暴露评估在食品安全状态评价中的 应用.检验检疫学刊,2002,12(1):11-12.   
16 Liu Y, Li S,Ni Z, et al. Pesticides in persimmons, jujubes and

soil from China:Residue levels,risk assessment and relationship between fruits and soils. Science of the Total Environment, 2016, 542(A): 620-628.

17ClaeysWL,SchmitJFO,Bragard C,etal.Exposureof several Belgian consumer groups to pesticide residues through fresh fruit and vegetable consumption. Food Control, 2011,22(3): 508-516.

18 Quijano L,Yusa V,Font G,et al.Chronic cumulative risk assessment of the exposure to organophosphorus,carbamate and pyrethroid and pyrethrin pesticides through fruit and vegetables consumption in the region of Valencia(Spain).Food & Chemical Toxicology, 2016, 89:39-46.

19 FangL,Zhang S,Chen Z,et al.Risk assessment of pesticide residues in dietary intake of celery in China.Regulatory Toxicology& Pharmacology,2015,73(2):578-586.

20 Nuapia Y,ChimukaL,Cukrowska E.Assessment of organochlorine pesticide residues in raw food samples from open markets in two African cities.Chemosphere,2016,164: 480-487.

21秦燕，李辉，李聪.危害物的风险系数及其在食品检测中的应用.检验检疫科学，2003,13(5):13-14.

22JMPR农药数据库.[2017-08-29].http://apps.who.int/

pesticideresidues-jmpr-database.

23EFSA农药数据库.[2017-08-29].http://ec.europa.eu/sanco_ pesticides/public/index.cfm.

24EU农药数据库.[2017-08-29].htp://ec.europa.eu/food/plant/pesticides/ eu-pesticides-database/public/?event=homepage&language=EN.

25WHO农药数据库.[2017-08-29].http://www.codexalimentarius. net/pestres/data/commodities/details.html?id=320.

26 EFSA PRIMo model 数据库.[2018-02-12].http://www.efsa. europa.eu/en/applications/pesticides/tools.

27WHO/GEMS/FOODS数据库.[2017-08-29].http://www.who.int/ foodsafety/publications/chem/regional_diets/en/.

28 金征宇.食品安全导论.北京:化学工业出版社,2005.

29 庞国芳，陈谊，范春林，等.高分辨质谱-互联网-数据科学三元融合技术构建农药残留侦测技术平台．中国科学院院刊，2017,32(12): 1384-1396.

30 中华人民共和国国家卫生和计划生育委员会，中华人民共和国农业部，中华人民国家食品药品监督管理总局.食品安全国家标准—食品中农药最大残留限量（GB2763-2016）.[2017-02-09].http://www.nhfpc.gov.cn/sps/s7891/201702/ed7b47492d7a42359f839daf3f70eb4b.shtml.

# Assessment of Safety of Marketed Fruits and Vegetables in China Based on Large Data Fusion Technology of Risk Value Automatic Calculation-Multidimensional Information Collection

PANG Guofangl\*LIANG Shuxuan²CHANG Qiaoying2SHEN Shigang²XUJianzhong2FANChunlin’LIHui² BAI Ruobin³ (1 Chinese Academy of Inspection and Quarantine,Beijing l0o176,China;   
2 College of Chemistry and Environmental Science,Hebei University,Baoding O71002, China;   
3 Beijing Uni-Star Inspection Technology Co.Ltd.,Beijing 100176, China) AbstractTwosystemsofdietaryexposureandprewaingriskasessmentofpesticideresidueerecostructedusingmodelsoffoodsafety indexndrisktsectielyAstodwareofskvautoaticllatioulimesioaliftiols

developed.TherissofpesticideresiduesinthemarketedfruitandvegetablesmplesinChinafrom2O2to215wereaessedonthebasis ofdetectiodataultimesioalifotioaslteddaledidingfritdgetablsecissicidategio maximumresiduelimitstandards,andsoohessessmetrsultsofetaryexposureriskindicate tatthemajorityofrisseptable inthe marketedfruitsandvegetablesof9823(LC-Q-TOF/MS)and1251samples (LC-Q-TOF/MS),respectively,butthereaetil $0 . 5 6 \%$ （204号 and $0 . 5 4 \%$ ofthemunaceptable.Bythecomparisonof prohibited andnon-prohibited pesticides,the frequencyratios ofunacceptable dietary risks ntotalfrequencyarehkedat20(C-Q-TOF/MS)and55(LC-Q-TOF/MS)timeswhile teratiosofhighprewaingrisare7(GC-Q TOF/MS)and23(C-Q-TOF/M)timesrespetiely.Therissofthprobiedpesticidesaresigniicantlyghertantatofteobad pesticides.Strictsupervisionandregulationofbannedpesticidesshouldbestrengthened.Thetopfruitsandvegetableswithunacceptable dietaryexposurerissofhprewaingrisarlistedinissudy.Iadition,ouldbfoundtattemaximumresidualiitdars establishedbyEuropean Unionwereobviouslymore strictandcompletethanthatofChina,soChina mustspeeduptheestablishment ofrelevantstandards.Thisstudycouldprovideimportantbasisforraltimedagnosisndprecisesupervisionofriskleveloffruitsand vegetables,thus reduce the risk of food borne pesticide residues and ensure people's tongue safety.

Keywords largedatafusiontechnlogyultidimensionalinformationcollction,pesticideresdue,detaryexposurerisk,prewaingisk庞国芳中国工程院院士，中国检验检疫科学研究院研究员，中国食品安全国家标准审评委员会副主任，中国国家食品安全风险评估专家委员会副主任，美国分析化学家协会（AOAC)资深专家，国际AOAC 2014年度HarveyW.Wiley 奖获得者。30多年来始终工作在检验检疫第一线，致力于食品科学检测技术理论与实践的研究，在农药等化学污染物残留微量分析技术领域进行了开拓性的研究工作，在研究高灵敏度、高选择性、高分辨率的多残留快速检测新技术、新方法方面；在研究新型萃取、分离、富集等样品制备新技术、新方法方面多有创新。在检测技术标准化工程化方面颇有建树，研究建立了139项国家技术标准和3项国际AOAC标准。3次荣获国家科学技术进步奖二等奖，8次荣获国际AOAC科学技术奖。论著10部（2000万字），论文100多篇（其中40篇 SCI论文）。E-mail:ciqpang@163.com

![](images/afefcf88b8da8ae9136a757c93be54dcff0774d9563f894808afc52ca774802d.jpg)

PANGGuofangAcademicianofChineseAcademyofEnginering,thechiefscientistofCAIQ,DeputyDirectorofRiskEvaluationExpert CommiteeofChinaNationalFoodSafety,DeputyDirectorofReviewCommiteeofChinaNationalFoodSafetyStandards,ellowof AssociatioofOicialAalyticalCemists(AOAC)ecipietofthe4HareyWWileyAwardOvertepas3years,eaa workingatteforefrotofteispctionnduarantieorkvotighimselftoeeseachontetoydpracticeoffodsitific analysisadconductingthepioneringresearchworkinthefieldoftraceelementanalytical techiquesofpesticideandveterinarydrug residues.Hesadeanyiovatiosindyofewtquesofapidetectionofultiresidswitghsensitivityiglectiiy andhighresolutionsas wellasinthe studyofnewtechniquesandnew methodssuchassample preparation likeextraction,separation, enrichment,etc.Hasfocusedisstudyotegthrougputtechquesoftetaceelemetsofoveropesticidesadveteaydrug residuesandestablished139ChinaNational Standardsand3AOACoficialmethod.HewontheSecondPrizeoftheStateSientificand TechnicalProgressfor3timesandtheAwardofScienceandTechniqueofAACfor8times.Head1Oscientificandtechicalworks(0 million words)and over 10 papers published,of which 40 were SCI indexed papers.E-mail: ciqpang@163.com