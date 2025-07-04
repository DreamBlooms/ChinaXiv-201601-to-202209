# 电力大数据驱动的新能源项目投资效益评价研究

# 以Y市电网公司SG-ERP系统为例

高骞」杨 旸²胡广伟³徐　超」沈高锋4赵健  
1(国网江苏省电力公司 南京 210024)  
2(南京大学商学院 南京 210093)  
3(南京大学信息管理学院南京 210093)  
4(国网江苏省电力公司电力经济技术研究院南京 210018)  
5(国网扬州供电公司 扬州 225008)

摘要：【目的】为满足电网公司针对新能源项目投资进行管控的需要，尝试基于电网公司内部大数据，建立面向新能源项目投资效益评价的数据抽取方法和评价指标体系。【方法】基于电网公司SG-ERP系统架构，构建面向大数据应用的数据管理体系，提出基于Golden Gate 的评价数据抽取方法，建立覆盖项目经济、社会、环境效益，及项目决策期、建设期和运营期的全过程评价指标体系，并辅以Delphi法进行验证。【结果】通过实证得到指标变异系数权重和Y市电网公司2015年新能源项目投资的经济、社会和环境效益得分。【局限】量化评价指标时采取的分类标准可进一步细化。【结论】本研究方案可实现电力新能源项目投资效益全过程的评价，数据抽取方法、评价指标体系和权重算法具有一定的推广价值。

关键词：电力大数据 数据抽取 新能源项目投资效益分类号:TM731 F426

# 1引言

随着国家对电力新能源项目投资额的不断增加和电网公司新能源发电项目固定资产规模的不断扩大，如何有效地安排电网公司的新能源项目投资，充分挖掘电力投资管理大数据信息，不断提高新能源项目的投资效益，成为电网公司资产管理的重大议题。在此背景下，国家对于电网公司新能源项目投资提出了更高的管控要求，电网公司需要合理使用电力信息系统长期积累的投资管理大数据信息，科学评价新能源项目的投资效益，以确切地反映电网公司新能源项目为国民经济、社会和环境发展所做出的贡献。

目前，随着电力系统集中式数据中心的陆续投运结构化和非结构化数据管理系统正逐步上线运行[1],电力新能源项目管理数据从总量和种类上都已初具规模，可开发利用的价值丰富2。电网公司内部管理信息系统中通常完整地存储着新能源项目在决策期和建设期的管理信息和数据[3]，为项目投资效益评价研究提供了鲜活的数据来源。应用电力信息系统内部大数据开展电力新能源项目投资效益评价，将有利于提高电力新能源项目投资质量、效益和效率，促进电力资源的优化配置和高效服务[4]。

以往对电力项目投资效益的评价研究主要集中于后评价环节，评价数据的获取方式是以统计项目运营期的经济效益数据为主，数据的全面性和规范性难以得到有效保障[5]，同时也缺乏对处于决策期、建设期新能源项目投资效益的评价[。其次，现有关于电力项目投资效益评价的研究主要集中于经济效益评价方面[，社会效益方面的评价较少，其导向作用难以彰显[8]。另外，由于电网公司大力推进的清洁替代能源发电项目，对节能减排、治理大气污染发挥了基础性作用，故电网公司项目投资效益的评价还应覆盖环境效益。一些文献将环境效益归结为社会效益的一部分[0-11],但随着环保问题日益受到人们的重视，并位列我国政府五大职能之一，学界逐渐将环境效益从社会效益中分离开展专项评价[12]。

基于此，本文在国家电网公司SG-ERP(State GridEnterprise Resource Planning)系统基础上引入大数据技术，尝试从4个层面提升新能源项目投资效益评价的数据管理框架，强化数据集成管理技术应用的广度和深度；构建覆盖项目经济、社会和环境效益，以及项目决策期、建设期和运营期的全过程评价指标体系；并以Y市电网公司2015年度的新能源项目实际案例开展投资效益评价的尝试。本研究的主要创新点在于:

(1）建立覆盖项目经济、社会、环境效益，及项目决策期、建设期和运营期的全过程评价指标体系;(2）提出基于电网公司SG-ERP系统的新能源项目投资效益评价数据的抽取方法，对电网公司推进项目投资精益化管理具有一定借鉴价值。

# 2电力新能源项目投资效益评价数据的抽取

# 2.1 电网公司SG-ERP系统架构与数据管理体系

电网公司SG-ERP系统是新能源项目投资效益评价的数据载体。该系统基本功能包括领导决策、职能管理、生产经营管理、财务管理等，同时为了支持系统的运行，系统中还包括相应的运行保障功能[13]。电网公司SG-ERP系统架构如图1所示。

决策支 经济运 经营决 财务管 电力知 决策持系统 行分析 策管理 理系统 识管理 支持  
信息安全系统 职能管 人力资 项目质 审计监 客户关 职理系统 源管理 量管理 察管理 系管理 能与经营管理支持层计 项 采 库 发 设 安 环ERP 划 目 购管 存管理 电管理 备管 全管 境管子系统 管 管  
+ 理 理 理 理 理 理 理  
运行保障系统 运营执 电力调 物资管 数据采 现场监行系统 度系统 理系统 集系统 控系统系统软件平台 (操作系统、数据库、中间件) 基础支撑支撑系统硬件平台(布线系统、网络通信系统、终端)

自从2002年实施SG-ERP系统项目管理子模块，Y市电网公司建立了覆盖项目决策期、建设期和运营期的新能源项目投资管理体系，并实现了项目管理与计划、财务管理的对接。在项目决策期，SG-ERP系统对新能源项目的可行性研究、项目预算、环保预估等内容进行全面跟踪；在项目建设期，为了对项目造价进行控制，系统将概算转化为原始预算并下达采购部门，对实际发生的成本进行比较和控制，自动汇总施工进度并估算项目工期；在项目运营期，系统对项目供应链、财务管理、设备管理及投资效益进行持续跟踪和数据导人。

为强化电力大数据的实际应用，电网公司通过引入大数据存储管理、集成管理、数据抽取、高性能计算、分析挖掘等技术，构建了覆盖大数据存储、整合、计算和应用的数据管理体系，如图2所示。

数据 前端可视化展现能力 (数据可理解、展现可定制)  
应用层图像识别 自然语言处理 数据挖掘 多维分析即席查询  
数据 新增  
计算层 并行数据处理(M/R) 批处理 流计算统一数据模型 完善  
数据 服务总线 流数据总线 批量数据传输 数据连接器  
整合层数据访问语言 NoSQL PIG Golden Gate 继承  
数据 关系数据库 列存储数据库 键值数据库 内存数据库  
存储层 分布式文件系统管理 传统磁盘管理

该数据管理体系能够处理更大的数据量，提供能快的数据处理速度，分析更多样化的数据类型,挖掘更深层次的数据价值，并更好地支撑电力大数据应用。

# 2.2 新能源项目投资效益评价数据的抽取方法

根据调研，Y市电网公司数据库是以传统商用软件Oracle为主，这种集中式数据库架构越来越不适应海量数据对计算能力的巨大需求。随着电网公司在开源数据库方面应用的不断拓展，如何能安全、高效地保证异构数据库之间的数据抽取和迁移，是亟待解决的问题。基于此，本研究尝试采用GoldenGate多源异构数据抽取方法[14]开展新能源项目投资效益评价。

GoldenGate提供了基于日志的数据复制方式，从电网公司SG-ERP系统实时抓取新能源项目投资效益评价数据，将变化的数据及其标识(可进行过滤)按特定格式存储到本地或远程Trail文件，通过复制进程对Trail文件进行实时解析。该方法具有实时性、异构性、模块化、高性能、灵活性和完整性等特点，占用系统资源少，数据处理过程中不影响源数据库的运行效率[15]

基于GoldenGate的数据抽取思路如下：将源数据库中的数据抽取出来并以中间格式导入到大数据平台后，再将其导人到NoSQL数据库中。对数据库中的评价数据进行挖掘，即可进行新能源项目投资效益评价，具体过程如图3所示。

![](images/6e9ba1fcea3468eb7328e311a700afabada1f5407eb478d497b0fbfb2d858ebe.jpg)  
图3新能源项目投资效益评价数据的抽取与应用

(1）建立索引。为源数据库中评价指标建立索引,在评价数据导入SG-ERP系统时即通过索引引擎实现对数据的动态提取，进而对新数据按域排序，根据排序结果将索引分段，构建多级立体式分段索引，并通过Join引擎建立评价指标与跨表数据的映射关系[16]。

(2）数据抽取。首先运用GoldenGate解析源数据库的日志文件，识别源数据库中的评价数据[17]。通过管理进程启动、监控、重启GoldenGate的其他进程，利用抽取进程从源数据库日志文件中捕获评价数据[14],将已提交的事务发送至远程的Trail用于同步。

(3）并行处理。利用Hadoop 的MapReduce 并行计算框架装载抽取出的数据[18]。MapReduce 计算框架将Golden Gate 抽取的数据分为多个数据块存储在多个计算节点上，这些计算节点并行处理数据。在每个节点计算完成之后，MapReduce 框架自动对数据进行汇聚和排序，并将最终结果输出到NoSQL数据库中。

# 3电力新能源项目投资效益评价指标体系构建

构建电力新能源项目投资效益评价指标体系是评价工作的重要基础[19]。借鉴以往研究的基础上，本文建立覆盖项目经济、社会、环境效益，及项目决策期、建设期和运营期的全过程评价指标体系，并基于专家意见?对指标体系进行筛选，最终保留54项指标，如表1所示。

表1电力新能源项目投资效益评价指标体系  

<html><body><table><tr><td>项目 所处周期</td><td>经济效益评价指标</td><td>社会效益评价指标</td><td>环境效益评价指标</td></tr><tr><td>决策期</td><td>(A1)决策的合规情况 (A2)决策与立项目标是否一致 (A3)是否提出决策优化与调整建议 (A4)可研报告是否以项目计划书为依据 (A5)可研报告是否经过详细的测算 (A6)可研报告是否做出风险提示</td><td>(B1)项目必要性是否充分 (B2)项目选址是否合适 (B3)项目建设条件是否有利 (B4)技术及备选方案是否合格 (B5)工程设计方案是否合理 (B6)是否重视降低能耗 (B7)是否注重劳动卫生安全及消防</td><td>(C1)是否对缓解沿线电磁辐射做出规划 (C2)是否对沿线噪声敏感保护区域做出规划 (C3)是否使用清洁能源发电 (C4)是否对项目污水处理进行规划 (C5)是否对施工废物处理进行规划 (C6)执行电磁辐射规划程度 (C7)满足施工期噪声控制要求程度</td></tr><tr><td>建设期</td><td>(A7)工程响应度 (A8)设计匹配率 (A9)验收合格率 (A10)投资匹配率 (A11)工期稳定率 (A12)工程决算误差率</td><td>(B8)新增就业人数 (B9)施工安全情况 (B10)耕地、拆迁补偿解决情况</td><td>(C8)采取环境保护和生态补偿措施的程度 (C9)执行污水处理规划的程度 (C10)执行废物处理规划的程度</td></tr><tr><td>运营期</td><td>(A13)净资产收益率 (A14)总投资报酬率 (A15)成本费用利润率 (A16)主营业务利润率 (A17)电费收入增长率 (A18)净利润增长率 (A19)总资产增长率 (A20)盈余现金保障倍数 (A21)资本保值增值率 (A22)资本收益率</td><td>(B11)单位投资增加的当地GDP (B12)单位当地GDP电耗变化率 (B13)单位投资直接增加就业人数 (B14)移民安置完成率 (B15)耕地补偿完成率 (B16)电压合格率 (B17)供电可靠率</td><td>(C11)由于新能源项目所减少的CO和污染 物排放量 (C12)由于负荷优化所减少的CO和污染物 排放量 (C13)由于电动汽车使用所减少的CO和污 染物排放量 (C14)由于电动汽车使用所减少的CO和污 染物排放量 (C15)由于新能源项目而减少的发电占地 面积</td></tr></table></body></html>

其中，项目决策期侧重于对立项的合规性和环保预案进行评估，对应的20项指标基于《国家电网公司科学技术项目可行性研究报告标准》和《国家电网公司“十三五"电网发展规划研究成果》提出；项目建设期主要评价工程建设效率和项目建设对社会、环境的影响，其中6项经济效益评价指标采用工程建设监理评价指标，具体计算方法参照南方电网公司《配电网公司固定资产投资项目实施准备工作评价参考指标集》(简称《参考指标集》)，其余6项社会效益和环境效益评价指标基于《国家电网公司小型基本建设项目管理办法》提出；对于项目运营期投资效益，则重点通过量化项目的运营效益及对民生和环境改善所做出的贡献进行评价，共包括 22项指标，主要从文献[5，7-8，11]中抽取。

通过GoldenGate抽取SG-ERP日志管理系统中有关项目决策期、建设期和运营期定性指标的标准化描述性摘要，定量指标则直接根据指标索引以及Join引擎建立的指标与跨表数据的映射关系进行抽取。进而，本文通过Delphi法制定定性指标和定量指标的得分标准。首先将定性指标的判定标准分5级，做法是先将5至10项规范性摘要作为描述该定性指标的备选项，再应用Delphi法向专家反复征求意见，缩小备选项的范围，随着专家意见逐步趋于集中，最后确定该定性指标的5项规范性摘要。如果通过GoldenGate抽取的实际标准化描述性摘要只涵盖其中的4项，那么该定性指标摘要相符比例为 $80 \%$ ，对应分值为70分；将定量指标的判定标准按优秀、良好、一般、较低和较差(分别对应I区间、Ⅱ区间、IⅢI区间、IV区间和V区间)分为5级，并将该指标实际数据值与对应区间进行归类，得到该指标的对应分值。评价指标判定标准及对

应分值如表2所示。

表2评价指标判定标准及对应分值  

<html><body><table><tr><td></td><td>定性指标摘要 相符比例</td><td>定量指标 数值区间</td><td>对应分值</td></tr><tr><td>优秀</td><td>80<x≤100</td><td>I区间</td><td>90</td></tr><tr><td>良好</td><td>60<x≤80</td><td>Ⅱ区间</td><td>70</td></tr><tr><td>一般</td><td>40<x≤60</td><td>Ⅲ区间</td><td>50</td></tr><tr><td>较低</td><td>20<x≤40</td><td>V区间</td><td>30</td></tr><tr><td>较差</td><td>X≤20</td><td>V区间</td><td>10</td></tr></table></body></html>

为评价各电力新能源项目的经济效益、社会效益和环境效益，需对评价指标进行赋权，本文采取变异系数法[20求得指标相应权重。若已知第i个项目第k个指标的得分 ${ \bf { x } } _ { \mathrm { { k i } } }$ ，则第 $\mathbf { k }$ 个指标的变异系数 $\mathbf { v } _ { \mathrm { k } }$ 定义为:

$$
\mathrm { v _ { k } = [ \sqrt { \frac { 1 } { n - 1 } } \sum _ { i = 1 } ^ { n } ( \mathbf { x } _ { k i } - \overline { { x } } ) ] \sqrt { \frac { \omega } { x } } }
$$

其中， $\overline { { \mathbf { X } } }$ 是第 $\mathbf { k }$ 个指标在所有项目中的得分均值。则第 $\mathbf { k }$ 个指标的变异系数权重 ${ \bf a } _ { \bf k }$ 为：

$$
{ \bf { a } } _ { \bf { k } } = { \bf { v } } _ { \bf { k } } \Bigg / \sum _ { \mathrm { { i } = 1 } } ^ { \mathrm { n } } { \bf { v } } _ { \mathrm { i } }
$$

# 4数据分析与结果讨论

基于Y市电网公司SG-ERP系统，提取2015年该公司30个电力新能源项目，其中决策期项目编号为1至10，建设期项目编号为11至20，运营期项目编号为21至30。基于变异系数赋予指标权重，计算电网公司各个新能源项目的经济、社会和环境效益，进而对新能源项目投资效益展开评价。

# 4.1 经济效益评价

在经济效益评价中，22项指标的变异系数与权重如表3所示，各项目社会效益评价得分如表4所示。

根据表4可知，2015年Y市电网公司多数新能源项目经济效益良好，其中，经济效益优秀的项目占比约为 $67 \%$ ，经济效益良好的项目占比约为 $23 \%$ ，另有约 $20 \%$ 的项目经济效益不佳，其中 $6 . 7 \%$ 的项目得分低于60分。新能源项目经济效益得分差异显著，说明电力新能源项目投资具有一定经济风险。究其原因：

(1）成本方面，风电发电成本约为0.5元/度，太阳能发电成本约为0.8元/度，而火力发电成本仅0.25元/度，与常规能源相比，新能源项目在发电成本上不具有优势;

表3经济效益评价指标均值与权重  

<html><body><table><tr><td>指标</td><td>平均值</td><td>标准差</td><td>变异系数</td><td>权重</td></tr><tr><td>A1</td><td>90.467</td><td>3.481</td><td>0.038</td><td>0.011</td></tr><tr><td>A2</td><td>89.700</td><td>3.053</td><td>0.034</td><td>0.010</td></tr><tr><td>A3</td><td>90.300</td><td>3.186</td><td>0.035</td><td>0.010</td></tr><tr><td>A4</td><td>91.167</td><td>3.270</td><td>0.036</td><td>0.010</td></tr><tr><td>A5</td><td>89.700</td><td>3.303</td><td>0.037</td><td>0.010</td></tr><tr><td>A6</td><td>90.133</td><td>3.104</td><td>0.034</td><td>0.010</td></tr><tr><td>A7</td><td>71.000</td><td>13.727</td><td>0.193</td><td>0.055</td></tr><tr><td>A8</td><td>75.500</td><td>18.489</td><td>0.245</td><td>0.070</td></tr><tr><td>A9</td><td>73.000</td><td>14.546</td><td>0.199</td><td>0.057</td></tr><tr><td>A10</td><td>66.667</td><td>15.294</td><td>0.229</td><td>0.065</td></tr><tr><td>A11</td><td>68.333</td><td>14.204</td><td>0.208</td><td>0.059</td></tr><tr><td>A12</td><td>71.500</td><td>19.541</td><td>0.273</td><td>0.078</td></tr><tr><td>A13</td><td>72.121</td><td>17.916</td><td>0.248</td><td>0.071</td></tr><tr><td>A14</td><td>78.438</td><td>16.117</td><td>0.205</td><td>0.059</td></tr><tr><td>A15</td><td>74.333</td><td>13.882</td><td>0.187</td><td>0.053</td></tr><tr><td>A16</td><td>77.245</td><td>15.698</td><td>0.203</td><td>0.058</td></tr><tr><td>A17</td><td>74.779</td><td>12.835</td><td>0.172</td><td>0.049</td></tr><tr><td>A18</td><td>74.779</td><td>12.477</td><td>0.167</td><td>0.048</td></tr><tr><td>A19</td><td>68.947</td><td>13.945</td><td>0.202</td><td>0.058</td></tr><tr><td>A20</td><td>66.667</td><td>11.413</td><td>0.171</td><td>0.049</td></tr><tr><td>A21</td><td>74.098</td><td>15.606</td><td>0.211</td><td>0.060</td></tr><tr><td>A22</td><td>78.421</td><td>13.955</td><td>0.178</td><td>0.051</td></tr></table></body></html>

表4经济效益评价结果  

<html><body><table><tr><td>项目</td><td>得分</td><td>项目</td><td>得分</td><td>项目</td><td>得分</td></tr><tr><td>1</td><td>92</td><td>11</td><td>80</td><td>21</td><td>79</td></tr><tr><td>2</td><td>93</td><td>12</td><td>85</td><td>22</td><td>94</td></tr><tr><td>3</td><td>92</td><td>13</td><td>84</td><td>23</td><td>57</td></tr><tr><td>4</td><td>91</td><td>14</td><td>82</td><td>24</td><td>67</td></tr><tr><td>5</td><td>90</td><td>15</td><td>83</td><td>25</td><td>60</td></tr><tr><td>6</td><td>90</td><td>16</td><td>91</td><td>26</td><td>70</td></tr><tr><td>7</td><td>90</td><td>17</td><td>79</td><td>27</td><td>87</td></tr><tr><td>8</td><td>90</td><td>18</td><td>84</td><td>28</td><td>55</td></tr><tr><td>9</td><td>91</td><td>19</td><td>92</td><td>29</td><td>80</td></tr><tr><td>10</td><td>91</td><td>20</td><td>81</td><td>30</td><td>61</td></tr></table></body></html>

(2）从政策角度来看，新能源项目当前主要依靠政府补贴实现盈利，但若主要终端市场补贴政策出现负面调整，会导致电站经营利润出现超预期下滑。

因此，本研究认为Y市电网公司应当在补贴政策出现负面调整前，通过项目决策、建设和运营方案的优化，严格控制新能源项目建设期和运营期成本，达

到预期的投资经济效益。

# 4.2 社会效益评价

在社会效益评价中，17项指标的变异系数与权重如表5所示，各项目社会效益评价得分如表6所示。

表5社会效益评价指标均值与权重  

<html><body><table><tr><td>指标</td><td>平均值</td><td>标准差</td><td>变异系数</td><td>权重</td></tr><tr><td>B1</td><td>73.020</td><td>13.956</td><td>0.190</td><td>0.102</td></tr><tr><td>B2</td><td>77.010</td><td>19.465</td><td>0.253</td><td>0.136</td></tr><tr><td>B3</td><td>79.103</td><td>15.430</td><td>0.196</td><td>0.106</td></tr><tr><td>B4</td><td>81.088</td><td>11.005</td><td>0.136</td><td>0.073</td></tr><tr><td>B5</td><td>72.070</td><td>18.567</td><td>0.260</td><td>0.140</td></tr><tr><td>B6</td><td>73.009</td><td>10.594</td><td>0.145</td><td>0.078</td></tr><tr><td>B7</td><td>78.422</td><td>14.577</td><td>0.188</td><td>0.101</td></tr><tr><td>B8</td><td>81.430</td><td>15.090</td><td>0.186</td><td>0.100</td></tr><tr><td>B9</td><td>90.100</td><td>3.002</td><td>0.033</td><td>0.018</td></tr><tr><td>B10</td><td>90.030</td><td>2.921</td><td>0.033</td><td>0.017</td></tr><tr><td>B11</td><td>90.010</td><td>3.014</td><td>0.034</td><td>0.018</td></tr><tr><td>B12</td><td>90.007</td><td>3.144</td><td>0.035</td><td>0.019</td></tr><tr><td>B13</td><td>90.045</td><td>3.030</td><td>0.034</td><td>0.018</td></tr><tr><td>B14</td><td>90.210</td><td>3.216</td><td>0.036</td><td>0.019</td></tr><tr><td>B15</td><td>90.400</td><td>2.988</td><td>0.033</td><td>0.018</td></tr><tr><td>B16</td><td>92.056</td><td>2.909</td><td>0.032</td><td>0.017</td></tr><tr><td>B17</td><td>90.020</td><td>3.401</td><td>0.038</td><td>0.020</td></tr></table></body></html>

表6社会效益评价结果  

<html><body><table><tr><td>项目</td><td>得分</td><td>项目</td><td>得分</td><td>项目</td><td>得分</td></tr><tr><td>1</td><td>91</td><td>11</td><td>91</td><td>21</td><td>87</td></tr><tr><td>2</td><td>91</td><td>12</td><td>89</td><td>22</td><td>83</td></tr><tr><td>3</td><td>91</td><td>13</td><td>90</td><td>23</td><td>83</td></tr><tr><td>4</td><td>88</td><td>14</td><td>90</td><td>24</td><td>87</td></tr><tr><td>5</td><td>89</td><td>15</td><td>88</td><td>25</td><td>85</td></tr><tr><td>6</td><td>90</td><td>16</td><td>91</td><td>26</td><td>84</td></tr><tr><td>7</td><td>91</td><td>17</td><td>88</td><td>27</td><td>88</td></tr><tr><td>8</td><td>93</td><td>18</td><td>90</td><td>28</td><td>86</td></tr><tr><td>9</td><td>90</td><td>19</td><td>89</td><td>29</td><td>86</td></tr><tr><td>10</td><td>91</td><td>20</td><td>89</td><td>30</td><td>84</td></tr></table></body></html>

根据表6可知，30个新能源项目的社会效益评分均高于 80 分，项目在运营期的社会效益评分均高于90分，说明项目投资的社会效益在2015年总体评价良好。电力新能源项目在项目规划、工程设计、安全施工、拆迁补偿、提高电网可靠度等社会效益方面表现良好，反映出Y市电网公司电力新能源基建等项目对民生改善和社会发展具有促进作用。此外，电网公司在新能源领域的发展也将有利提升公司品牌影响力，吸引人才，为社会提供更多的就业机会。由此可见，积极开发利用可再生能源，减轻能源对外依靠压力，促进新能源技术改进，带动相关产业发展，将为我国提升产业结构和走能源可持续发展的道路创造条件。

# 4.3 环境效益评价

在环境效益评价中，15项指标的变异系数与权重如表7所示，各项目环境效益评价得分如表8所示。

表7环境效益评价指标均值与权重  

<html><body><table><tr><td>指标</td><td>平均值</td><td>标准差</td><td>变异系数</td><td>权重</td></tr><tr><td>C1</td><td>90.433</td><td>3.002</td><td>0.033</td><td>0.055</td></tr><tr><td>C2</td><td>89.767</td><td>2.921</td><td>0.033</td><td>0.054</td></tr><tr><td>C3</td><td>89.767</td><td>3.014</td><td>0.034</td><td>0.055</td></tr><tr><td>C4</td><td>89.900</td><td>3.144</td><td>0.035</td><td>0.058</td></tr><tr><td>C5</td><td>90.167</td><td>3.030</td><td>0.034</td><td>0.055</td></tr><tr><td>C6</td><td>90.267</td><td>3.216</td><td>0.036</td><td>0.059</td></tr><tr><td>C7</td><td>90.367</td><td>2.988</td><td>0.033</td><td>0.054</td></tr><tr><td>C9</td><td>88.833</td><td>4.120</td><td>0.046</td><td>0.076</td></tr><tr><td>C10</td><td>88.267</td><td>4.934</td><td>0.056</td><td>0.092</td></tr><tr><td>C11</td><td>88.533</td><td>5.070</td><td>0.057</td><td>0.094</td></tr><tr><td>C12</td><td>88.267</td><td>4.899</td><td>0.056</td><td>0.091</td></tr><tr><td>C13</td><td>87.700</td><td>5.073</td><td>0.058</td><td>0.095</td></tr><tr><td>C14</td><td>87.900</td><td>4.113</td><td>0.047</td><td>0.077</td></tr><tr><td>C15</td><td>86.767</td><td>4.415</td><td>0.051</td><td>0.084</td></tr></table></body></html>

表8环境效益评价结果  

<html><body><table><tr><td>项目</td><td>得分</td><td>项目</td><td>得分</td><td>项目</td><td>得分</td></tr><tr><td>1</td><td>87</td><td>11</td><td>75</td><td>21</td><td>75</td></tr><tr><td>2</td><td>96</td><td>12</td><td>91</td><td>22</td><td>91</td></tr><tr><td>3</td><td>89</td><td>13</td><td>85</td><td>23</td><td>88</td></tr><tr><td>4</td><td>86</td><td>14</td><td>74</td><td>24</td><td>86</td></tr><tr><td>5</td><td>85</td><td>15</td><td>95</td><td>25</td><td>82</td></tr><tr><td>6</td><td>93</td><td>16</td><td>84</td><td>26</td><td>82</td></tr><tr><td>7</td><td>88</td><td>17</td><td>89</td><td>27</td><td>85</td></tr><tr><td>8</td><td>83</td><td>18</td><td>83</td><td>28</td><td>86</td></tr><tr><td>9</td><td>86</td><td>19</td><td>86</td><td>29</td><td>95</td></tr><tr><td>10</td><td>86</td><td>20</td><td>95</td><td>30</td><td>80</td></tr></table></body></html>

根据表8可知，电力新能源项目的环境效益多数评价良好，其中，得分高于90分的项目占比约为 $23 \%$ 得分居70分至80分之间的项目占比约为 $64 \%$ 。此外，还有约 $13 \%$ 的新能源项目的环境效益得分低于70分，可见电力新能源项目的环境效益仍具有提升空间，本区域内光伏发电项目建设工程亟待进一步批准和推进。光伏发电是我国鼓励与支持发展的可持续发展的新能源，光伏电站的推广建设将起到节约不可再生化石能源、减少污染及保护生态环境的作用，具有明显的环境效益。Y市电网公司应当重视提升新能源项目在运营期的管控能力，将节能减排与发展经济、促进就业相结合，通过发展本土新能源产业缓解资源环境约束，应对全球气候变化，为我国建设资源节约型、环境友好型社会提供可持续发展动力。

# 5结语

基于电网公司SG-ERP系统架构，构建面向大数据应用的数据管理框架，提出评价数据抽取方法，建立覆盖项目经济、社会、环境效益及项目决策期、建设期和运营期的全过程评价指标体系，以Delphi法对指标体系进行辅助验证，并通过Y市电网公司2015年度的新能源项目实际案例开展投资效益评价。研究结果表明电力新能源项目的经济效益差异显著，具有一定的经济风险；社会效益总体评价良好，电力新能源基建项目的对于民生改善和社会发展具有促进作用；环境效益仍具有一定提升空间，电网公司应当重视提升新能源项目在运营期的管理控制能力，将节能减排与发展经济、促进就业充分结合。本研究的不足在于对指标进行量化时采取的是5级分类标准，为了提高投资效益评价的准确性，该标准可进一步细分。本研究结果将进一步为Y市电网企业未来的新能源项目投资、建设与管理提出先验的信息，为合理选择新能源投资项目、把握项目建设时序、控制投资规模、推进电网公司项目投资精益化管理等提供科学的决策依据。

# 参考文献：

[1] 戚宇林，荆霜雁．我国电力通信网管理信息系统的现状及 发展[J]．电力情报，2000(3):15-18.(QiYulin，Jing Shuangyan. CurrentSituationandDevelopmentof Management Information System of Electric Power Communication Network in China [J].Information of Electric Power,2000(3):15-18.)

[2]郭晓利，曲朝阳，李晓栋,等.基于 SOM 聚类的电网可视 化数据挖掘模型[J]．情报科学,2012,30(2):206-209.(Guo Xiaoli, Qu Zhaoyang,Li Xiaodong,et al. Visual Data Mining Model in Power Grid Based on SOM Clustering [J]. Information Science,2012,30(2): 206-209.)   
[3]李鹏，吴江．电网情报平台的模糊层次平衡计分绩效评价 方法研究[J]．情报科学,2014,32(7):86-91.(Li Peng，Wu Jiang.Research on Performance Evaluation of Grid Information Platform Based on Fuzzy Hierarchy Balanced Scorecard Method [J]. Information Science,2014，32(7): 86-91.)   
[4]韦嵘晖．大型央企集团技术竞争情报系统一体化管理运维 研究[J]．图书情报知识，2012(1):18-21．(Wei Ronghui. Research onIntegrated Management， Operationand Maintenance of Competitive Technical Intelligence System forLarge Central State-owned Enterprise Groups [J]. Document Information & Knowledge,2012(1): 18-21.)   
[5]Davidson I E.Evaluation and Effective Management of Non-technical Losses in Power Systems [J]. The Transactions of the South African Institute of Electrical Engineers,2003, 94(3): 39-42.   
[6]Sun H. Integrated Modeling of Electric Power System Operations and Electricity Market Risks with Applications [J]. Dissertation Abstracts International, 2006,45(3): 35-52.   
[7]蔡光宗，尚珊珊．国家电网项目运营后评估研究[J]．科技 管理研究，2014,34(2):199-204.(Cai Guangzong，Shang Shanshan.Research on the Establishment of Post Evaluation System for the Operation Process of Power Grid Project [J]. Science and Technology Management Research,2014,34(2): 199-204.)   
[8]刘胜利，曹阳，冯跃亮，等．配电网投资效益评价与决策 模型研究及应用[J]．电力系统保护与控制，2015，43(2): 119-125.(Liu Shengli,Cao Yang，Feng Yueliang，et al. Research and Application of Distribution Grid Investment Effectiveness Evaluation and Decision-making Model [J]. Power System Protection and Control, 2015,43(2): 119-125.)   
[9]Albert R,Albert I, Nakarado G L. Structural Vulnerability of the North American Power Grid [J].Physical Review E,2004, 69(2): 025103.   
[10]Karki R,Hu P,Billinton R．A Simplified Wind Power Generation Model for Reliability Evaluation [J].IEEE Transactions on Energy Conversion,2006,21(2): 533-540.   
[11]唐永胜，王良，李晨，等．基于改进灰色关联度赋权方法 的电网投资效益评价模型[J]．水电能源科学，2013，31(5): 186-189.(Tang Yongsheng，Wang Liang,Li Chen,et al. Investment Benefit Evaluation Model of Grid Enterprise Based on Improved Gray Correlation Degree Method [J]. Water Resources & Power,2013,31(5):186-189.)   
[12]Karki R,Hu P,Billinton R.A Simplified Wind Power Generation Model for Reliability Evaluation [J].IEEE Transactions on Energy Conversion,2006,21(2):533-540.   
[13]郑称德，王全胜，陈曦．我国企业 ERP 系统实施的业务流 程绩效实证研究[J]．情报杂志，2010,29(1):68-72.(Zheng Chengde,Wang Quansheng，Chen Xi.Empirical Study on Business Process Performance of ERP System in Chinese Enterprises [J]. Journal of Intelligence,2010,29(1): 68-72.)   
[14]郑海雁，金农，季聪，等．电力用户用电数据分析技术及 典型场景应用[J]．电网技术，2015，39(11):3147-3152. (Zheng Haiyan，Jin Nong，Ji Cong，et al．Data Analysis Technology and Typical Application of Electric Power User [J].Power System Technology,2015,39(11): 3147-3152.)   
[15]Naumann F,Bilke A,Bleiholder J,etal.Data Fusion in Three Steps: Resolving Inconsistencies at Schema,Tuple,and Value-level [J].Bulletin of the Technical Committee on Data Engineering,2010(2):21-31.   
[16]Solano MA,Ekwaro-Osire S,Tanik MM.High-Level Fusion for Intelligence Applications Using Recombinant Cognition Synthesis [J].Information Fusion,2012,13(1):79-98.   
[17]Jagadish H V, Gehrke J,Labrinidis A,et al.Big Data and Its Technical Challenges [J]. Communications of the ACM, 2014,57(7): 86-94.   
[18]Lin G, Liang J,Qian Y.An Information Fusion Approach by Combining Multigranulation Rough Sets and Evidence Theory[J]. Information Sciences,2015,314:184-199.   
[19]杨华飞，李栋华，程明．电力大数据关键技术及建设思路 的分析和研究[J]．电力信息与通信技术,2015,13(1):7-10. (Yang Huafei，Li Donghua,Cheng Ming．Analysis and

Research on Key Technologies and Construction Ideas of Power Big Data [J].Power Information & Communication Technology,2015,13(1): 7-10.) [20]Gulhar M,Kibria GK,Albatineh AN,etal.A Comparison of Some Confidence Intervals for Estimating the Population Coefficient of Variation:A Simulation Study [J].Statistics and Operations Research Transactions,2012,36(1): 45-68.

# 作者贡献声明：

高骞：提出研究命题和研究思路，修改论文;  
杨肠：起草论文，构建模型，分析数据;  
胡广伟：设计研究方案，论文起草及最终版本修订;  
徐超：优化研究方案，采集数据;  
沈高锋：清洗、加工和分析数据;  
赵健：设计实验流程，起草论文。

# 利益冲突声明：

所有作者声明不存在利益冲突关系。

# 支撑数据：

支撑数据由作者自存储,E-mail: hugw@nju.edu.cn。  
[1]高骞，杨肠，胡广伟.NewEnergyProjectsData.rar.新能源项目投资效益评价实验数据.  
[2]高骞，杨肠，胡广伟.SG_ERP_DataExtraction.rar.SG-ERP系统数据提取程序包.  
[3]高骞，杨肠，胡广伟.Weight.xlsx.经济、社会和环境效益评价指标变异系数及权重.

收稿日期:2016-07-25  
收修改稿日期:2016-08-29

# Analyzing Return of Investment for New Energy Project with Big Data: Case Study of SG-ERP System in Y City

Gao Qian1Yang Yang²Hu Guangwei³Xu Chao1Shen Gaofeng4Zhao Jian5 1(State Grid Jiangsu Electric Power Company, Nanjing 210024, China) 2(School of Business,Nanjing University, Nanjing 210093, China)   
3(School of Information Management, Nanjing University, Nanjing 210093, China) 4(Electric Power Economic Technology Research Institute, State Grid Jiangsu Electric Power Company, Nanjing 21oo18, China) 5(State Grid Yangzhou Electric Power Company, Yangzhou 225008, China)

Abstract:[Objective] This paper establishes data extraction model and evaluation mechanism for the return of investment analysis on new energy projects.Alldata is from the State Grid Jiangsu Electric Power Company in China. [Methods] First, we proposed a new big data management framework based on the State Grid Jiangsu Electric Power Company SG-ERP system architecture.Second,we extracted evaluative data based on Golden Gate technology,and constructed an evaluation system covering the economic,social and environmental aspects of the target projects at different development stages (i.e. decision-making,construction and operation). Finaly,we examined the proposed system with the Delphi Law.[Results] We got the weight of variation coefficient and the economic,social and environmental benefits of new energy projects of Y Cityin 2015.[Limitations] Theclassification schemes for the evaluation criteria could be further refined.[Conclusions]The proposed system can evaluate the return of investments for new energy power grid projects.The data extraction method, evaluation system and weight algorithm could be used in other studies.

Keywords: Power big data Data extractionNew energy projectInvestment benefit