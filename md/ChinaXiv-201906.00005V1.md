# 中国飞蝗(Locustamigratoria)灾害地理分布模拟及其生物气候因子分析

张杰，张旸²，赵振勇³，李敏(1 江西省科学院鄱阳湖研究中心,江西南昌330096；2 福建农林大学资源与环境学院,福建福州 350002;3中国科学院新疆生态与地理研究所荒漠与绿洲生态国家重点实验室，新疆乌鲁木齐830011；4江西省南昌市第一中等专业学校,江西南昌330013)

摘要：飞蝗Locustamigratoria（Linnaeus）系斑翅蝗科Oedipodidae飞蝗属 Locusta Linnaeus 洲际性农业重大害虫,在我国主要包括东亚飞蝗L.migratoriamanilensis（Meyen）、亚洲飞蝗L.migratoria(Linnaeus)和西藏飞蝗L.migratoria tibetensis Chen。掌控飞蝗灾害的地理空间分布并预测起潜在的适宜分布区，对于我国飞蝗灾害的综合防控具有重要意义。结合三种中国飞蝗灾害记录地理信息和生物环境环境因子参数，应用最大熵模型（MaxEnt）和地理信息技术（GIS），在 $3 \ \mathrm { k m } \times 3 \ \mathrm { k m }$ 尺度上对三种飞蝗灾害在中国的地理分布空间格局梯度、灾害风险概率和风险等级进行了模拟预测与分析，并对影响分布的关键生物气候环境因子进行了分析。结果显示，蝗灾害风险区的地理分布模拟结果与历史记录完全符合，ROC 检验表明MaxEnt模型预测可靠性极高。三种飞蝗东亚飞蝗、亚洲飞蝗和西藏飞蝗在中国的灾害风险区总面积依次分别为 $3 1 5 . 8 7 \times 1 0 ^ { 4 } \ \mathrm { k m } ^ { 2 } \cdot 3 9 5 . 8 0 \times 1 0 ^ { 4 } \ \mathrm { k m } ^ { 2 }$ 和 $1 2 5 . 0 0 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ，分别占国土面积的 $3 3 . 4 3 \% . 4 1 . 9 6 \%$ 和 $1 3 . 2 5 \%$ 。东亚飞蝗和亚洲飞蝗的灾害风险区存在 $7 5 . 8 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 的空间重叠，主要分布于我国农牧交错区及以南区域。三种飞蝗灾害风险区的地理梯度与分布格局与中国三大自然地理区高度吻合，其地理分布格局表现出显著的经度和纬度空间梯度异质性。刀切法检测(Jackknife test)表明，三种飞蝗灾害的主导生物一气候影响因子的不同导致了其地理分布格局的显著差异，表明蝗灾爆发概率同时受到各自不同飞蝗物种对气候环境的适应性与地理空间隔离作用的共同制约。研究结果可为我国飞蝗灾害的跨界联合全程防控、区域联网监测联控和综合治理提供参考依据。

关键 词：飞蝗；蝗灾；灾害风险；地理分布；适宜性；最大熵模型文章编号： 1000 -6060(2019)03-0590-09(0590\~0598)

飞蝗Locustamigratoria（Linnaeus）隶属于直翅目Orthoptera,蝗总科Acridoidea,斑翅蝗科Oedipodi-dae，飞蝗属LocustaLinnaeus，是一种洲际性农业重大害虫，其分布遍及欧、亚、非、澳等四大洲。全世界已知有1个种10个亚种，我国有3个亚种，即：东亚飞蝗L.migratoriamanilensis（Meyen）亚洲飞蝗L.migratoria（Linnaeus）和西藏飞蝗L.migratoria ti-betensis $\mathrm { C h e n } ^ { [ 1 - 3 ] }$ 。飞蝗是迁飞性、群居性、暴食性、暴发性和毁灭性害虫，不但分布广，而且数量多、发生频率高，危害极为严重。玉米、小麦、水稻等主要粮食作物以及草原植被均是其喜食植物，一旦暴发成灾，将给农牧业生产和生态环境造成巨大损失[2-3] 。

蝗虫灾害(简称“蝗灾")是严重影响农牧业生产安全和农村社会稳定的世界性和区域性重大生物灾害[4]。蝗灾与水灾、旱灾并称为世界“三大自然灾害”。以飞蝗为主的蝗害是我国历史上最为严重的农业灾害之一。在我国河南、河北、天津、新疆等地曾多次出现大面积、高密度灾情，严重影响和破坏了农业生产、粮食安全和国民经济的持续稳定发展[3,5]。历史上蝗虫暴发成灾,常常引发饥荒,造成社会动荡。近现代社会蝗虫暴发危害，不仅影响农牧业生产稳定发展和农牧民持续增收，还会对社会稳定造成负面影响[5]。据农业部办公厅2014 年颁布的《全国蝗虫灾害可持续治理规划（2014—2020年)》公布，我国飞蝗(东亚飞蝗、亚洲飞蝗、西藏飞蝗)常年发生 $3 ~ 0 0 0 \times 1 0 ^ { 4 }$ 亩次左右，总体发生平稳。中国在蝗灾治理取得了举世瞩目的成效，但蝗灾的威胁依然存在，蝗灾区域性爆发风险的可持续治理仍然是我国农牧业生产安全保障面临的主要任务。

国内外蝗虫及蝗灾研究工作者为防治蝗灾进行了大量的工作，积累了极为丰富的资料，主要研究了飞蝗种群结构变化、生长发育、形态学、组织学及蝗灾发生、预测预报和防治方面的内容[6-21]。我国大量学者开展了飞蝗三个亚种东亚飞蝗、亚洲飞蝗和西藏飞蝗的生活史、生活习性、行为、分布等研究，并对我国蝗灾的特点、成因及生态学理论作了大量研究[6-13]。近50a来我国蝗虫工作者在飞蝗种类与分布，东亚飞蝗形态学、组织学、数量预测、食性、生殖、迁飞、变型、蝗区等方面进行了广泛的研究[1-13]。但是,目前关于我国飞蝗灾害风险的宏观地理空间格局定量分布及其影响蝗灾地理分布的主导气一候环境因子的研究还尚未见报道，制约着对飞蝗灾害区域跨界联合全程防控、综合应急装备体系和监测预警与控制布设联网等重大安全保障能力的提升。

飞蝗灾害风险的产生主要由飞蝗孳生地和至灾气候环境所决定[13-14]。飞蝗擎生地和发生地即适宜蝗虫产卵、聚集或迁移的场所[15]。蝗区土壤理化性质、地形、植被覆盖度及气象因素等生态条件都是影响蝗虫产卵场所选择和发生的重要因子[16-17]蝗区冬季较高气温和春季适宜降水有利于蝗卵越冬和春季孵化,有助于种群数量快速增长[18-21]。因而,掌握蝗区生态气候特征是了解蝗虫孳生地时空分布的重要前提。由飞蝗规则的地理分布特点，可知季风、干旱、高寒三种不同的气候大背景较为严格地制约了飞蝗的区域分化，因此东亚飞蝗、亚洲飞蝗和西藏飞蝗这三个飞蝗亚种也可以被看作是昆虫对地理气候环境响应与适应的典型代表[1,4]。开展飞蝗灾害发生地与孳生地潜在分布区及其生物气候影响的研究，对于飞蝗灾害防控和管理、制定合理控制措施和蝗区孳生地生态改造规划具有重要意义。

物种分布模型（Species Distribution Modelling）

是利用物种的分布数据与环境数据，依据特定的算法估计物种的生态位，以概率的形式反映物种对生境的偏好程度[22]。国际上已经建立多种生态模型可以对物种的分布区进行预测,如GARP（the ge-netic algorithm for rule-set prediction）、Bioclim（thebioclimatic prediction system）和 MaxEnt（MaximumEntropy)等，有大量研究表明,MaxEnt最大熵模型在预测结果精确度上要优于其他模型，尤其是在物种分布数据不全的情况下[23]。MaxEnt 模型在病虫害扩散分布模拟、濒危动植物潜在生境质量评价、外来入侵物种风险评估、农作物种植适生区预测及气候变化适应性响应研究等研究中得到应用并取得了良好的模拟效果[22-24] ○

本研究以中国三种主要飞蝗灾害发生地理分布数据为基础，利用MaxEnt生态位模型对其在中国的空间地理分布、蝗灾爆发风险区进行预测，并分析影响其生物地理分布的主要气候环境因子，明确三种飞蝗灾害在中国的地理分布空间格局特征及其潜在风险分布区。本研究可为我国开展飞蝗灾害区域跨界联合全程防控、监测及早期监测预警和管理规划策略制定提供重要参考依据。

# 研究数据与方法

# 1.1 研究来源

1.1.1基础地理数据中国省级行政区划图（ $1 : 4 0 0$ 万），由国家基础地理信息中心提供。使用国家测绘地理信息局所提供的《中华人民共和国地图( ${ \mathrm { ~  ~ \ell ~ } } _ { 1 } : 4 0 0$ 万)》基本要素版参考底图为基准底图。使用AdobeIllustrator CS6 和CorelDRAWX5专业绘图软件，结合ESRIArcGIS9.1进行制图。

1.1.2标本分布数据三种飞蝗灾害的地理分布数据主要是通过检索国内外公开发表文献，收集整理出我国具有精确经纬度、地理范围或详细地名蝗灾记录信息。最终遴选获得近50a东亚飞蝗灾害记录192条、亚洲飞蝗61条和西藏飞蝗29条。

1.1.3生物一气候环境数据环境数据包括19 个生物气候变量和2个地形高程相关变量（高程DEM和坡向）。其中19个Bioclim生物气候变量（BIO01-BIO19）由气候数据衍生而来，详细定义及计算方法见参考文献[25]。环境变量数据均为1950—2000 年平均值，空间分辨率为2.5minute，来自世界气象数据库（http：//www.worldclim.org）。

$9 0 \mathrm { ~ m ~ }$ 分辨率DEM高程数据来自NASA发布的SRTM地形数据（http://srtm.csi.cgiar.org/）。所有生物一气候环境数据通过降尺度重采样形成 $3 ~ \mathrm { k m }$ $\times 3 \ \mathrm { k m }$ 分辨率数据集。

# 1.2 MaxEnt生态位模型

MaxEnt模型是美国普林斯顿大学StevenPhil-lips 等学者基于最大熵原理用JAVA语言编写的用于预测物种的潜在地理分布的预测软件[22]

# 1.3 灾害风险等级划分

利用ArcGIS空间分析工具的再分类功能对模拟获得的 $3 { \mathrm { ~ k m } } \times 3 { \mathrm { ~ k m } }$ 分辨率中国三种飞蝗灾害爆发风险概率 $( P )$ 图进行等级划分，将蝗灾风险等级划分为4级： ${ P < 0 . 1 }$ 为无风险区； $\ 0 . \ 1 \leqslant P < 0 . \ 3$ 低风险区： $. 0 . 3 \leqslant P < 0 . 5$ 为中风险区； $P { \geqslant } 0 . 5$ 为高风险区。合并后 $0 . \ 1 \leqslant P < 0 . 5$ 为中低风险区； $P { \geqslant } 0 . 1$ 为总风险区，即为中、低、高风险区的总和。

# 2结果与分析

# 2.1模拟结果准确性评价

为验证MaxEnt模型的适用性，将地理分布数据和环境数据导入模型，随机选取 $2 5 \%$ 的蝗灾记录分布点作为测试集,剩余 $7 5 \%$ 作为训练集等参数。模拟结果检验与评估采用ROC（ReceiverOperatingCharacteristic）曲线分析法，对风险分析结果进行精度检验。 $A U C$ （AreaUnderCurve）即受试者工作特征曲线下的面积。 $A U C < 0 . 7$ 表示模拟结果较差，$A U C > 0 . 9$ 表示模型预测较精确。本研究结果表明训练集和验证集 $A U C$ 值均大于0.92，高于随机概率值0.5（表1）。这说明所构建模型的预测准确性较好。

# 2.2 飞蝗灾害在中国的风险区空间分布

图1为使用MaxEnt模型模拟获得的 $3 \ \mathrm { k m } \ \times \$ $3 ~ \mathrm { k m }$ 分辨率三种飞蝗灾害在中国的潜在地理空间分布结果。东亚飞蝗、亚洲飞蝗和西藏飞蝗在中国

# 表1三种飞蝗灾害模型模拟的AUC预测精度

Tab.1 Accuracy assessment of modeling predictions byAUC for the outbreak of migratory locust disaster   

<html><body><table><tr><td>物种</td><td>训练集AUC (±SD)值</td><td>验证集AUC (±SD)值</td><td>随机预测 AUC值</td></tr><tr><td>东亚飞蝗</td><td>0.961 ±0.007</td><td>0.934 ±0.012</td><td>0.5</td></tr><tr><td>亚洲飞蝗</td><td>0.933 ±0.005</td><td>0.940 ±0.008</td><td>0.5</td></tr><tr><td>西藏飞蝗</td><td>0.987 ±0.005</td><td>0.924 ±0.010</td><td>0.5</td></tr></table></body></html>

![](images/4df854ce70f8c6834aeed05e5fe154a39cd5531e6c7f52a720fa6aa5970cb6fb.jpg)  
图1三种飞蝗灾害风险在中国的潜在空间分布 Fig.1Predicted potential geographic distribution of the migratory locust in China

的灾害风险区总面积分别为 $3 1 5 . \ 8 7 \times 1 0 ^ { 4 } \ \mathrm { k m } ^ { 2 }$ 、$3 ~ 9 5 . 8 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 和 $1 ~ 2 5 . 0 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,分别占国土面积的 $3 3 . 4 3 \% . 4 1 . 9 6 \%$ 和 $1 3 . 2 5 \%$ （表2）。三种蝗灾的地理分布格局空间分异显著，即黄淮海东亚飞

# 表2基于MaxEnt预测的三种飞蝗灾害在我国的风险区的面积统计

Tab.2Statistical analysis of risk areas of the migratorylocustbasedonMaxEnt   

<html><body><table><tr><td>物种</td><td>中低风险 区面积 /104km²</td><td>高风险 区面积 /104km²</td><td>总风险 区面积 /104km²</td><td>占全国 百分比 /%</td></tr><tr><td>东亚飞蝗</td><td>225.99</td><td>89.88</td><td>315.87</td><td>33.43</td></tr><tr><td>亚洲飞蝗</td><td>275.05</td><td>120.75</td><td>395.80</td><td>41.96</td></tr><tr><td>西藏飞蝗</td><td>94.60</td><td>30.40</td><td>125.00</td><td>13.25</td></tr></table></body></html>

![](images/b47680750ced55bd930eb83ccd7a7651b1330e08ab54a195e482c637263f603f.jpg)  
图2中国三种飞蝗灾害风险分区图 Fig.2Division map of plague risk for the three species of migratory locust disaster in China

蝗发生区、新疆和东北亚洲飞蝗发生区、川青藏西藏飞蝗发生区。东亚飞蝗和亚洲飞蝗的灾害风险区在 $1 0 3 . 7 1 ^ { \circ } \sim 1 2 3 . 5 6 ^ { \circ } \mathrm { ~ E ~ } , 3 2 . \ 1 6 ^ { \circ } \sim 4 2 . \ 2 1 ^ { \circ } \mathrm { ~ N ~ }$ 之间的区域存在 $7 5 . 8 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 的空间重叠，主要分布于我国农牧交错区及以南区域，主要覆盖河北、陕西和山西等临近省份（图2）。空间重叠区分别占东亚飞蝗和亚洲飞蝗灾害风险区面积的$2 3 . 9 9 \%$ 和 $1 9 . 1 5 \%$ ；西藏飞蝗灾害风险区均不与两者有任何空间重叠。三种飞蝗灾害风险区覆盖面积占我国国土面积的 $8 0 . 5 4 \%$ 。三种蝗灾的非风险区或安全区在中国的分布主要有四块：即东北大小兴安岭区、藏北区、藏南区和横断山区，面积分别为 $7 7 . 5 \times 1 0 ^ { 4 } \mathrm { ~ k m } ^ { 2 } \cdot 9 2 . 6 \times 1 0 ^ { 4 } \mathrm { ~ k m } ^ { 2 } \cdot 4 . 4 \times$ $1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 和 $1 1 . 2 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 。

东亚飞蝗灾害风险区主要分布于101. $0 8 ^ { \circ } \sim$ $1 2 2 . 4 6 ^ { \circ } \mathrm { ~ E ~ } , 1 8 . 2 5 ^ { \circ } \sim 4 2 . 0 9 ^ { \circ } \mathrm { ~ N ~ }$ 之间的东部季风区的黄淮海平原、平地或河谷低洼区。风险区主要在中国北部的河北省、山西省、山东省、陕西省和河南省；西部的四川省;南部的广州省、广西壮族自治区；中部的江西省、湖北省和河南省等。其中高风险区分布面积最多的省份是河南省和山东省，其高风险区分别为 $1 4 . 7 7 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 和 $1 4 . 7 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,占全国高风险区总面积的 $1 6 . 4 3 \%$ 和 $1 6 . 3 5 \%$ （表3）。

亚洲飞蝗灾害风险区主要分布于 $7 3 . 8 8 ^ { \circ }$ \~$1 3 2 . 9 1 ^ { \circ } \mathrm { E } , 3 2 . 8 6 ^ { \circ } \sim 4 9 . 2 2 ^ { \circ } \mathrm { N }$ 之间的西北十旱半十旱区和东北平原区。灾害风险区主要分布于新疆维吾尔自治区、内蒙古自治区、甘肃省、陕西、河北、山西、吉林和辽宁等省份。其中高风险区分布面积最多的省份是新疆和内蒙，其高风险区面积分别为$8 9 . 0 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 和 $1 9 . 0 \times 1 0 ^ { 4 } \ \mathrm { k m } ^ { 2 }$ ，占全国高风险区总面积的 $7 3 . 7 5 \%$ 和 $1 5 . 7 7 \%$ （表3）。

# 表3模拟预测的三种飞蝗灾害在我国分布的风险区的分省面积统计

Tab.3Statistic of risk areas of three species of migratory locust at province level in China   

<html><body><table><tr><td>物种</td><td>省份</td><td>中低风险 区面积 /104km²</td><td>高风险 区面积 /104km²</td><td>总风险 区面积 /104km²</td><td>高风险区 面积占全 国百分比 /%</td></tr><tr><td>东亚飞蝗</td><td>河北</td><td>2.66</td><td>9.60</td><td>12.26</td><td>10.68</td></tr><tr><td></td><td>山东</td><td>0.42</td><td>14.70</td><td>15.11</td><td>16.35</td></tr><tr><td></td><td>山西</td><td>8.96</td><td>4.22</td><td>13.18</td><td>4.69</td></tr><tr><td></td><td>河南</td><td>1.76</td><td>14.77</td><td>16.53</td><td>16.43</td></tr><tr><td></td><td>安徽</td><td>4.67</td><td>9.34</td><td>14.00</td><td>10.39</td></tr><tr><td></td><td>江苏</td><td>1. 65</td><td>8.17</td><td>9.82</td><td>9.09</td></tr><tr><td></td><td>陕西</td><td>16.42</td><td>1.74</td><td>18.16</td><td>1.93</td></tr><tr><td></td><td>湖北</td><td>12.01</td><td>6.52</td><td>18.52</td><td>7.25</td></tr><tr><td></td><td>湖南</td><td>18.91</td><td>2.07</td><td>20.98</td><td>2.30</td></tr><tr><td></td><td>江西</td><td>12.82</td><td>3.82</td><td>16.63</td><td>4.25</td></tr><tr><td></td><td>浙江</td><td>8.41</td><td>1.43</td><td>9.84</td><td>1.59</td></tr><tr><td></td><td>福建</td><td>11.29</td><td>0.70</td><td>11.99</td><td>0.78</td></tr><tr><td></td><td>四川</td><td>20.59</td><td>0.39</td><td>20.97</td><td>0.43</td></tr><tr><td></td><td>重庆</td><td>8.03</td><td>0.15</td><td>8.18</td><td>0.16</td></tr><tr><td></td><td>广州</td><td>15.29</td><td>1.90</td><td>17.20</td><td>2.12</td></tr><tr><td></td><td>广西</td><td>17.81</td><td>5.40</td><td>23.20</td><td>6.00</td></tr><tr><td>亚洲飞蝗</td><td>新疆</td><td>55.95</td><td>89.06</td><td>145.01</td><td>73.75</td></tr><tr><td></td><td>甘肃</td><td>27.39</td><td>8.47</td><td>35.86</td><td>7.01</td></tr><tr><td></td><td>内蒙古</td><td>70.93</td><td>19.04</td><td>89.96</td><td>15.77</td></tr><tr><td></td><td>宁夏</td><td>3.54</td><td>1.67</td><td>5.21</td><td>1.38</td></tr><tr><td></td><td>陕西</td><td>19.08</td><td>0.44</td><td>19.52</td><td>0.37</td></tr><tr><td></td><td>山西</td><td>15.50</td><td>0.15</td><td>15.64</td><td>0.12</td></tr><tr><td></td><td>河北</td><td>16.89</td><td>1.73</td><td>18.62</td><td>1.43</td></tr><tr><td></td><td>吉林</td><td>9.45</td><td>0.09</td><td>9.54</td><td>0.07</td></tr><tr><td></td><td>辽宁</td><td>9.81</td><td>0.06</td><td>9.86</td><td>0.05</td></tr><tr><td>西藏飞蝗</td><td>西藏</td><td>53.20</td><td>24.46</td><td>77.67</td><td>80.47</td></tr><tr><td></td><td>四川</td><td>21.10</td><td>5.48</td><td>26.58</td><td>18.03</td></tr><tr><td></td><td>云南</td><td>5.01</td><td>0.40</td><td>5.42</td><td>1.33</td></tr><tr><td></td><td>青海</td><td>12.52</td><td>0.05</td><td>12.57</td><td>0.18</td></tr></table></body></html>

西藏飞蝗灾害风险区主要分布于 $7 3 . 8 8 ^ { \circ }$ \~$1 3 2 . 9 1 ^ { \circ } \mathrm { ~ E ~ } , 3 2 . 8 6 ^ { \circ } \sim 4 9 . 2 2 ^ { \circ } \mathrm { ~ N ~ }$ 之间的川青藏高原区。灾害高风险区分布面积最多的省份是西藏和四川，高风险区分别为 $2 4 . 5 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 和 $5 . 5 \times 1 0 ^ { 4 }$ $ { \mathrm { k m } } ^ { 2 }$ ，占全国高风险区总面积的 $8 0 . 4 7 \%$ 和 $1 8 . 0 3 \%$ 0

# 2.3飞蝗灾害风险在中国的地理分布格局

三种飞蝗东亚飞蝗、亚洲飞蝗和西藏飞蝗在中国的灾害风险概率沿地理梯度的变化分布格局具有显著的地理空间分异特征(图3）。东亚飞蝗灾害在$9 3 . 3 6 ^ { \circ } \sim 1 1 6 . 5 6 ^ { \circ } \mathrm { E }$ 经向梯度上呈现显著经度梯度性，随经度增加风险概率增加并与纬度梯度呈现线性正相关( $\mathrm { \mathrm { ~  ~ } } R ^ { 2 } = 0 . 9 8 , P < 0 . 0 0 1 \mathrm { \mathrm { ~  ~ } }$ ,之后随经度增加风险概率衰减；在 $1 8 . 3 6 ^ { \circ } \sim 2 2 . 5 6 ^ { \circ } \mathrm { N }$ 纬向梯度上（江南丘陵区）风险概率变化离散，在 $2 2 . 5 6 ^ { \circ }$ \~$4 1 . 9 7 ^ { \circ } \mathrm { N }$ 随纬度增加出现规律性一峰两谷，表明东亚飞蝗灾害风险概率在黄淮海平原区具有显著纬度梯度性。亚洲飞蝗在在 $7 3 . 9 6 ^ { \circ } \sim 1 3 2 . 7 6 ^ { \circ } \mathrm { E }$ 经向梯度上，随经度递增风险概率呈现波动起伏特征，但总体上随经度增加风险概率递减并与纬度梯度呈现线性负相关( $R ^ { 2 } = 0 , 7 4$ ， $P < 0 . \ 0 1 \$ )；在 $3 2 . \ 3 6 ^ { \circ }$ \~$3 7 . 5 6 ^ { \circ } \mathrm { N }$ 纬向梯度上，风险概率呈现线性增长( $R ^ { 2 } =$ 0.92, $P < 0 . 0 1 \$ )，之后至 $4 7 . 1 6 ^ { \circ } \mathrm { N }$ 随纬度增加风险概率保持稳定。西藏飞蝗在 $7 8 . 7 6 ^ { \circ } \sim 1 0 4 . 7 6 ^ { \circ } \mathrm { N }$ 纬向梯度上，随纬度增加呈现规律双峰现象；在 $2 7 . 1 6 ^ { \circ }$ \~

![](images/3d6ab9f53b71515a68cdc3bb645c698096d72817767600478a5896ce35659ab1.jpg)  
图3中国飞蝗灾害风险概率沿经纬度的地理格局梯度变化

Fig.3Gradient changes in risk probability of the migratory locust disaster along longitude and latitude in China

$3 7 . 9 7 ^ { \circ } \mathrm { E }$ 纬向梯度上，风险概率呈现单峰特征，在$2 7 . 1 6 ^ { \circ } \sim 2 8 . 9 7 ^ { \circ } \mathrm { E }$ 随纬度增加风险概率逐渐递增，之后随纬度增加风险概率逐渐衰减呈线性正相关中 $\ ^ { \prime } R ^ { 2 } = 0 . 9 1 , P < 0 . 0 0 1 \rangle$ ,呈现出显著纬向梯度性。

# 2.4影响蝗害地理分布的主导环境因子

东亚飞蝗、亚洲飞蝗和西藏飞蝗三种飞蝗灾害几乎覆盖中国三大自然区（图2）。定量辨识影响三种飞蝗灾害地理分布的主导气候因子，重新构建其地理分布与气候环境的关系及其阈值，有助于提高飞蝗灾害风险的预测能力。基于MaxEnt模型的刀切法Jackknife模块给出的生物气候因子对三种飞蝗灾害风险地理分布影响的得分情况，以此反映各自主导生物环境因子的贡献率(表4）。

影响东亚飞蝗灾害风险地理分布的主要气候环境要素主要为最冷月的最低气温（BIO06）、最热季降水量（BIO18）、等温性（BIO03）、气温年较差（BIO07)和气温季节性变动系数（BIO04）等因子，这5个因子的累积贡献率达 $7 1 . 9 2 \%$ 。

影响亚洲飞蝗灾害风险地理分布的主要气候环境要素主要为最干季降水量（BIO16）、气温季节性变动系数（BIO04）、年降水量（BIO12）、最冷季降水量（BIO19)和最湿月降水量(BIO13)等因子，这5个因子的累积贡献率达 $7 2 . 7 3 \%$ 。

影响西藏飞蝗灾害风险地理分布的主要气候环境要素主要为海拔（ALT）、等温性（BIO03）、最干季平均气温（BIO09）、最热季降水量（BIO18）和坡向

# 表4潜在生物气候/环境因子对三种飞蝗灾害潜在分布影响的贡献百分率

Tab.4Contributions of the environmental variables for the species of migratory locust disaster   

<html><body><table><tr><td rowspan="2">排 序</td><td colspan="2">东亚飞蝗</td><td colspan="2">亚洲飞蝗</td><td colspan="2">西藏飞蝗</td></tr><tr><td>变量</td><td>贡献率 /%</td><td>变量</td><td>贡献率 /%</td><td>变量</td><td>贡献率 /%</td></tr><tr><td>1</td><td>BI006</td><td>27.5</td><td>BI016</td><td>21.0</td><td>ALT</td><td>57.6</td></tr><tr><td>2</td><td>BIO18</td><td>19.5</td><td>BI004</td><td>19.4</td><td>BIO03</td><td>23.9</td></tr><tr><td>3</td><td>BI003</td><td>10.2</td><td>BI012</td><td>13.0</td><td>BI009</td><td>3.8</td></tr><tr><td>4</td><td>BI007</td><td>7.5</td><td>BI019</td><td>11.8</td><td>BIO18</td><td>3.8</td></tr><tr><td>5</td><td>BI004</td><td>7.2</td><td>BI013</td><td>7.5</td><td>ASP</td><td>2.6</td></tr><tr><td>6</td><td>BI002</td><td>3.5</td><td>BIO06</td><td>6.8</td><td>BIO15</td><td>2.4</td></tr><tr><td>7</td><td>BI001</td><td>3.2</td><td>BI002</td><td>3.5</td><td>BI011</td><td>1.9</td></tr><tr><td>8</td><td>BIO14</td><td>3.0</td><td>BIO03</td><td>3.3</td><td>BI001</td><td>1.9</td></tr><tr><td>9</td><td>BIO11</td><td>2.9</td><td>BI011</td><td>3.0</td><td>BI019</td><td>1.2</td></tr><tr><td>10</td><td>BIO12</td><td>2.7</td><td>BI015</td><td>2.8</td><td>BI017</td><td>0.6</td></tr></table></body></html>

(ASP)等因子，这5个因子的累积贡献率高达$9 1 . 7 2 \%$ 。

# 3讨论

# 3.1中国飞蝗灾害地理分布格局及其分异

我国飞蝗蝗灾害风险区地理区域分化受到大尺度宏观纬向或经向地理格局与气候背景的制约，表现出对地理环境响应与适应的结果。空间地理隔离在飞蝗地理种群分化的过程中起比较重要的作用。本研究结果表明，东亚飞蝗灾害得益于优异的气候条件而爆发风险高度集中，而东亚飞蝗和亚洲飞蝗灾害风险区存在空间过渡区和重叠区，重叠区面积分别占各自面积的 $2 3 . 9 9 \%$ 和 $1 9 . 1 5 \%$ ，推测飞蝗种群的区域分化可能随地理分布呈现梯度变异的特点。张民照等[8认为黄淮平原种群间存在较广泛的基因交流，而与新疆和内蒙古种群间的基因交流则相对较少。我国蒙新区和东部季风区的飞蝗种群分化是明显。另外，黄淮平原种群基因交流的程度远远大于新疆和内蒙古的种群。张德兴等[10]认为东亚飞蝗基因遗传分化从南到北呈现连续和梯度变异。这与本研究蝗灾风险概率梯度变化和空间隔离离散分布规律相一致。

# 3.2飞蝗灾害空间分异的气候环境影响因素

本研究通过定量分析的结果与其相符合。亚洲飞蝗爆发风险主要受到最干季降水量因子的控制。而影响西藏飞蝗灾害风险爆发的主导因子为海拔和气候等温性等。跨境境外蝗虫迁飞进入通常被认为是我国新疆和东北亚洲飞蝗灾害发生致灾的原因[10,15]。而本研究通过主导气候因子分析,发现毗邻国家哈萨克斯坦、吉尔吉斯斯坦等亚洲飞蝗灾爆发区与我国爆发区具有相同气候环境特征。可见亚洲飞蝗迁飞至我国北方农牧业成灾，主要是从本地或擎生地迁入、过境或停留后规模化集聚致灾所致[16-17]。内陆河流域荒漠河岸和湖泊滨湖区一旦遭遇干旱气候，就可能成为飞蝗理想孳生地。孳生地具有蝗虫孳生繁殖的最适条件，高密度的蝗虫种群通常从擎生地向外扩散迁移[18-20]。飞蝗具有大区域跨境传播入侵农业的特征，其传入、扩散与成灾受到各自生物气候环境的控制与影响[21]。东亚飞蝗灾害爆发风险主要受到年极端温度和夏季降水量的控制。故东亚飞蝗在我国分布区的海拔高度一般在 $2 0 0 \mathrm { ~ m ~ }$ 以下，发生地多在 $5 0 \mathrm { ~ m ~ }$ 以下的平原、沿河、滨湖、内涝以及沿海的低洼地或滩地。陈永林等认为流域水旱灾害大旱交替发生是东亚飞蝗猖撅形成的诱因[1]。气候变化和异常天气增温、频发大旱的可能以及水热季节分配失调所引起的旱涝灾害，均可导致蝗虫的猖撅[26]。

# 3.3中国飞蝗灾害防治对策与建议

本文开展飞蝗灾害发生地与孳生地潜在分布区及其生物气候影响的研究，对于我国飞蝗灾害防控和管理、制定合理控制措施和蝗区擎生地生态改造规划具有重要参考意义。本研究通过定量模型模拟，发现东亚飞蝗、亚洲飞蝗和西藏飞蝗在中国的灾害风险概率沿地理梯度的变化分布格局具有显著的地理空间分异特征。尤其是发现东亚飞蝗灾害在华北平原形成高风险区，并在经向梯度上自北而南呈风险概率现呈现显著线性递减趋势，表明东亚飞蝗自华北平原向长三角地区迁移和扩散的空间态势。本研究证明亚洲飞蝗灾害风险横跨中国整个国土范围，蝗灾爆发概率并自西向东逐步衰减，并在新疆与邻国毗邻地区存在高风险多个飞蝗发生地和孳生地。表明我国蝗灾灾情应急防控设施或机构的设立应进行区域或跨国的合作，开展具有多层次、多等级的联合监测预警，并结合物联网、空间大数据、无人机及遥感等技术，构建起防控功能完整的飞蝗灾害联防联治的网络体系。

# 3.4模拟结果准确性及其不确定性

三种飞蝗灾害的主导气候环境影响因子的不同导致了其灾害风险区地理分布格局的显著差异。另外，除了气候因子以外，水文、土质、地形、植被、环境变化等因子都可能是影响飞蝗灾害爆发风险的不确定性环境因素[17-18],有待于进一步深入研究。

# 4结论

本文利用东亚飞蝗、亚洲飞蝗和西藏飞蝗三种中国飞蝗共282条历史蝗灾发生记录地理信息和生物环境因子参数，应用MaxEnt最大熵生态位模型和GIS 地理信息技术，对三种飞蝗灾害在中国的地理分布空间格局、灾害风险概率和风险等级进行了预测与分析，并对影响分布的关键生物气候环境因子进行了分析。

（1）通过模型模拟获得 $3 \ \mathrm { k m } \times 3 \ \mathrm { k m }$ 分辨率高精度中国飞蝗灾害风险地理空间分布图。三种飞蝗在中国的灾害风险区总面积分别占国土面积的

$3 3 . 4 3 \%$ （204号 $, 4 1 . 9 6 \%$ 和 $1 3 . 2 5 \%$ 。三种飞蝗灾害风险区覆盖面积占我国国土面积的 $8 0 . 5 4 \%$ ,其中亚洲飞蝗灾害风险区面积最大，覆盖范围最广，覆盖我国北方半干旱区及西北干旱区，并跨越邻近中亚国家。而东亚飞蝗几乎覆盖我国黄淮海平原区农业生产区，对国家的农业生产危害最为严重。

(2）通过中国飞蝗地理空间分布与生物气候环境分析，三种飞蝗灾害在我国的地理分布格局空间分异显著。并证明我国三种飞蝗灾害风险区的地理梯度与分布格局与中国三大自然地理区高度吻合。对三种飞蝗灾害的地理空间格局进行空间叠置分析，表明蝗灾爆发概率同时受到各自不同飞蝗物种对气候环境的适应性与地理空间隔离作用的共同制约。

(3）通过蝗灾地理空间梯度定量分析，发现亚洲飞蝗在在经向梯度上，总体上随经度递增风险概率呈现波动起伏递减特征。从而证明了亚洲飞蝗主要通过跨境并规模化迁移、扩散并侵入形成灾害的观点。

（4）本文开展了我国主要三种飞蝗灾害发生地与孳生地潜在地理分布研究，有助于定量识别我国飞蝗灾害的宏观地理空间格局及其影响蝗灾地理分布的主导气候因子，可为我国飞蝗灾害区域跨界联合全程防控、综合应急装备体系和监测预警与控制布设联网等重大安全保障管理与决策提供科学参考依据。

# 参考文献(References)

[1］陈永林.中国主要蝗虫及蝗灾的生态学治理[M].北京;科学 出版社,2OO7:1-35.［CHEN Yonglin.Main locusts and ecological management in China[M].Beijing: Science Press,2007:1- 35.]   
[2] 陈家祥.中国历代蝗灾之记录［M].杭州：浙江昆虫局年刊， 1935.［CHEN Jiaxiang.Locust records of Chinese dynasties[M]. Hangzhou;Annals of Zhejiang Bureau of Insects,1935.]   
[3] 吴福祯.中国的飞蝗［M].上海：永祥印书馆,1951.［WU Fuzhen.Migratory locusts in China［M].Shanghai:Yongxiang Printing House,1951.]   
[4] 陈永林.中国的飞蝗研究及其治理的主要成就[J].昆虫知识， 2000,37（1）:50-59.[CHEN Yonglin.Main achievements about the research and management of locust plague in China[J].EntomologicalKnowledge,2000,37（1）:50-59.]   
[5］李钢,王乃昂,李卓仑.中国历史蝗灾动态的社会影响及生态 环境意义[J].地理科学进展，2010，29（11）：1357-1366.［LI Gang,WANGNai'ang,LI Zhuolun.Studyonsocial influence,environmental significance and ecological explanation of the dynamics of locust plagues in China during the historical period[J].Progress in Geography,2010,29（11）:1375-1384.]   
[6］马世骏.东亚飞蝗蝗区的结构与转化[J].昆虫学报,1962,11 (1）:17-30.[MA Shijun.The structure and transformation of the oriental locust breeding areas[J].Acta Entomologica Sinica,1962, 11(1) :17 -30. ]   
[7］马世骏.中国东亚飞蝗蝗区的研究[M].北京:科学出版社, 1965.[MA Shijun.Research on the oriental locust breeding areas in China[M].Beijing:Science Press,1965.]   
[8］张民照,康乐.飞蝗(Locusta migratoria)地理种群在中国的遗 传分化[J].中国科学（生命科学）,2005,35（3）：220 －230. [ ZHANG Minzhao, KANG Le. Genetic divergence among geographical populations of the migratory locust in China[J].Scientia Sinica(Vitae）,2005,35(3）:220-230.]   
[9］李春选,马恩波,郑先云,等.中国东亚飞蝗四个地理种群遗传 结构的比较研究［J].昆虫学报.2004,47（1)：73-79.[LI Chunxuan,MA Enbo,ZHEN Xianyun,et al. Genetic structure of four geographic populations of Locusta migratoria manilensis in China[J].Acta Entomologica Sinica.2004,47(1）:73-79.]   
[10］张德兴,闫路娜,康乐,等.对中国飞蝗种下阶元划分和历史演 化过程的几点看法［J].动物学报，2003，49（5）：125－131. [ZHANG Dexing,YAN Luna,KANG Le,et al. Some unorthodox views on the classification and evolution of the migratory locusts in China prompted by molecular population genetic study[J]. Acta Zoologica Sinica,2003,49(5）:125-131.]   
[11］朱耿平,刘晨,李敏,等.基于Maxent 和GARP模型的日本双棘 长蠹在中国的潜在地理分布分析[J].昆虫学报,2014,57（5）： 581-586.[ZHU Gengping,LIU Chen,LI Min,et al.Potential geographical distribution of Sinoxylon japonicum（Coleoptera:Bostrichidae）in China based on Maxent and GARP models[J].Acta Entomologica Sinica,2014,57(5） :581-586.]   
[12]MA JW,HAN X Z,Hasibagan,et al. Monitoring East Asian migratory locust plagues using remote sensing data and field investigations[J].International Journal of Remote Sensing,2Oo5,26 629 - 634.   
[13］康乐,李鸿昌,陈永林.中国散居型飞蝗地理种群数量性状变 异的分析[J].昆虫学报,1989,32（4）:418-426.[KANG Le, LI Hongchang,CHEN Yonglin. Analysis of numerical character variations of geographical populations of Locusta migratoria phase solitaria in China[J].Acta Entomol Sinica,1989,32(4）:418- 426.]   
[14]KANG L,CHEN Y L. The analysis of numerical taxonomy to the interrelationship among different geographic populations of Locusta migratoria （L.）phase solitaria（Orthoptera:Acrididae）[J]. Sinozoologia,1991,8:71 -82.   
[15]SIVANPILLAI R,LATCHININSKY A V. Mapping locust habitats in the Amudarya River delta,Uzbekistan,using multi-temporal MODIS imagery[J].Environmental Management,2007,9（6）： 876-886.   
[16]MEYNARD C N,GAY P E,LECOQ M,et al. Climate-driven geographic distribution of the desert locust during recession periods : Subspecies’niche differentiation and relative risks under scenarios of climate change[J].Global Change Biology,2017,23（11）： 4739 -4749.   
[17]LAZAR M,ALIOU D,YANG JT,et al.Location and characterization of breeding sites of solitary desert locust using satellite images Landsat 7 ETM $^ +$ and Terra MODIS[J]. Advances in Entomology,， 2015,3(1) :6 -15.   
[18]LECOQ M.Recent progress in desert and migratory locust management in Africa:Are preventative actions possible?[J]. Journal of Orthoptera Research,2001,10(2）:277 -291.   
[19]MAGOR JI,LECOQ M,HUNTER D M.Preventive control and desert locust plagues[J]. Crop Protection,2008,27（12）:1527 - 1533.   
[20]PIOU C,LEBOURGEOIS V,BENAHI A S,et al. Coupling historical prospection data and a remotely-sensed vegetation index for the preventative control of desert locusts[J]. Basic and Applied Ecology,2013,14(7) 593-604.   
[21]LECOQ M. Desert locust threat to agricultural development and food security and FAO/International role in its control[J].Arab Journal of Plant Protection,2003,21(2）:188-193.   
[22] STEVEN JP,ROBERT P A,ROBERT E S. Maximum entropy modeling of species geographic distributions[J].Ecological Modeling,190(3-4):231-259,2006.   
[23]STEVEN JP,MIROSLAV D.Modeling of species distributions with MaxEnt: New extensionsand a comprehensive evaluation[J]. Ecography,2008,31(2）:161-175.   
[24]张杰,敖子强,吴永明,等.中华猕猴桃（Actinidia chinensis）在 中国的适生性及其潜在地理分布模拟预测[J].热带地理, 2017,37(2）:218 -225.[ZHANG Jie,AO Ziqiang,WU Yongming,et al.Prediction of potential geographic distribution of Actinidia chinensis in China based on Maximum Entropy Niche Model and ArcGIS[J]. Tropical Geography,2017,37(2）:218 -225.]   
[25]HIJMANS R J,CAMERON S E,PARRA JL,et al. Very high resolution interpolated climate surfaces for global land areas[J]. International Journal of Climatology,2005,25（15）:1965-197.   
[26] SWORD G A,LECOQ M,SIMPSON S J. Phase polyphenism and preventative locust managementJ]. Journal of Insect Physiology， 2010,56(8) :949 -957.

# Potential geographic distribution modeling and bioclimatic analysis of outbreak risk for the migratory locust plague in China

ZHANG Jie'， ZHANG Yang²， ZHAO Zhen-yong³，LI Min4 (1Poyang Lake Research Center， Jiangxi Academy of Sciences,Nanchang 330096,Jiangxi,China;   
2Collegeof Resource and Environment,FujianAgriculture andForestry University,Fuzhou 350o2,Fujian,China;   
3State KeyLaboratoryof Oasis Ecologyand Desert Environment,Xinjiang Instituteof Ecologyand Geography,CAS, Jrumqi 83011,Xinjiang,China；4.Nanchang First Specialized SecondarySchool,Nanchang330l3,Jiangxihina)

Abstract:One of the most persistent and damaging natural hazards is the migratory locust plague in China,which is the most widespread locust species,and posesa threat toagricultural productionand,subsequently,livelihoods and food security.In this study,based onthe dataon the history reported occurrence data of locust disasters,we applied MaxEnt niche models to predictand analyze the distribution areaof the locust outbreak risk for three main species of migratory locust in China.Itconsists of a geographical informationsystem,the spatial distributionof the locust outbreak risk for the Asian migratory locust(（Locusta migratoria migratoria（Linnaeus））,the Oriental Migratory Locust(Locusta migratoria manilensis （Meyen））and the Tibetan migratory locust （Locusta migratoria tibetensis Chen）were mapped at $3 \ \mathrm { k m } \times 3 \ \mathrm { k m }$ resolution ,and the degree of outbreak risk is evaluated.The results of the migratorylocust plague probability modeling displays a heterogeneous distribution of locust disasters risk probability in China.The area of low to high risk for three species of locust infestation is $3 \ 1 5 8 \ 6 6 7 \ \mathrm { k m } ^ { 2 }$ ,3 958 002 km² and $1 ~ 2 5 0 ~ 0 3 7 ~ \mathrm { k m } ^ { 2 }$ respectively,accounted for $3 3 . 4 3 \%$ · $4 1 . 9 6 \%$ and $1 3 . 2 5 \%$ of China's total land area respectively. The disaster risk areas of $L$ ，migratoria migratoria and $L$ ，migratoria manilensis have a spatial overlap of 757 890 （204号 $\mathrm { k m } ^ { 2 }$ ,mainly distributed in the farming-pastoral ecotone and the south region of China.The geographic paterns of the spatial distributionof the locustoutbreak for three speciesalong latitudinal and longitudinal gradientsare highly consistent with the three major natural geographical areas in China.The predicted results were then tested by ROC curves using suitability indexes ( $. A U C )$ ,the mean $A U C$ across eight different spatial scales is ranged from O.924 to 0.987.The Jackknife testanalysis reveals the linkages between locust infestation risk and mainenvironmental factors and theresults show thatthe diference ofthe dominant influencefactorsof the three species of migratorylocust disastersleads tothe significant diferences and heterogeneityof geographical distribution patern in China.The resultsshow thattheprobabilityof locust disasteroutbreak issimultaneouslyrestrictedbytheadaptabilityof difrent migratory locust species to the climate environment and their geographical space isolation.The study willprovide vital information to help manage and control the outbreak risk of the migratory locust disaster.

Key words:migratory locust plague；disaster outbreak risk ；geographical distribution； suitability； MaxEnt