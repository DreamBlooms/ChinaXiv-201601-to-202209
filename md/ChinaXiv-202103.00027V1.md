# 2001—2018年黄土高原植被覆盖人为影响时空演变及归因分析

张翀}，白子怡²，李学梅³，冉祺祺'，韦振锋4，雷田旺′，王娜ó(1.宝鸡文理学院,陕西省灾害监测与机理模拟重点实验室,陕西 宝鸡721013；2.陕西师范大学,地理科学与旅游学院,陕西 西安710119；3.重庆师范大学,地理与旅游学院/GIS应用研究重庆市高校重点实验室,重庆400047；4.广西易城蓝图科技有限公司,广西 南宁530007；5.西安交通工程学院,土木工程学院,陕西 西安710065；6.陕西省气候中心,陕西 西安710015)

摘要：基于2001—2018年的MODIS-NDVI和MODIS-LST以及土地利用、交通、人口等多种人文社会数据，通过温度植被干旱指数反映黄土高原土壤水分状况，利用残差法剔除土壤水分得到植被覆盖变化的人为影响,辅以趋势分析、Hurst指数、地理探测器等方法探讨了黄土高原植被覆盖的人为影响变化特征、未来变化趋势以及人为影响的归因。结果表明：(1)黄土高原2001—2018年植被覆盖人为影响变化趋势为 $0 . 3 6 \times 1 0 ^ { - 2 } \mathrm { a } ^ { - 1 }$ ，人为对植被覆盖的影响向正作用方向发展。(2）黄土高原植被覆盖人为影响的未来变化趋势由正作用转为向负作用方向发展，值得注意的是退耕还林重点实施区植被覆盖的人为正作用未来变化呈减弱趋势。(3)综合相关分析与地理探测器结果，确定影响植被覆盖变化的人为主导因子主要包括高级别旅游景点、城市分布、交通和土地利用。(4）未来退耕还林工程的实施以及生态建设工程的维持，应在注重城市经济发展的同时重视生态建设，减缓交通业对生态环境所带来的危害，加强绿色旅游业发展以及减缓土地变化等人为活动的影响。

关键词：植被覆盖人为影响；温度植被干旱指数；残差法；地理探测器；黄土高原

# 文章编号：

2000年以来中国社会经济发生着天翻地覆的变化，而经济迅猛发展的同时生态环境也面临着巨大的危险。近年来，强烈的人类活动如大规模的人□城市化、轨道交通的多向延伸、各地旅游景区的兴起、土地资源的变更等等都对生态环境造成某种程度的负面影响[1-5],使得人与自然环境的关系处于紧平衡状态，加剧了气候变化异常及地质灾害等不良现象的发生。为此，加强区域生态环境人为影响定量分析将不仅促进生态精准修复，而且为区域可持续发展提供定量依据，具有重要的理论和现实意义。

植被覆盖变化是衡量区域生态环境状况的重要指标[6-8],同时人为影响也深刻地烙印在植被覆盖变化中[9]。国内外学者常利用归一化植被指数（Normalized difference vegetation index,NDVI)分析植被覆盖变化及其人为影响[10-12],以维护区域生态安全。在植被覆盖变化人为影响评价中所用到的方法主要包括定性-半定量的评价方法和定量评价[13],其中定量评价主要有残差趋势法[14-16]、回归模型法[17-19]、基于生物物理过程的模型方法[20-22]等。各种评价方法均具有优缺点，而残差趋势法却在近年来被广泛使用，且公认为是评价植被覆盖变化人为因素的较好模型[23]。因此，本文选用残差趋势法对植被覆盖变化的人为影响进行评价[13]。前人往往利用残差趋势法从植被覆盖变化中剔除气候因子(气温、降水等)获取人为影响的大小[24-26],在实际情况下土壤水分才是植被生长的直接影响因子，它是降水、气温与蒸散发等地表参数共同作用下的综合因子，其对植被的影响作用远大于单因子气温或降水[27]。另外，在进行人为影响分析时以往研究多采用定性法或比较法进行探讨，缺乏定量挖掘具体影响植被覆盖变化的人为因素的正负作用方向[28-30],因此，难以为区域生态环境保护提供精准有效的依据。

退耕还林草工程实施以来，黄土高原的植被覆盖以及生态环境发生了明显变化，退耕还林等措施的生态效应不言而喻。然而，黄土高原植被覆盖变化的人为影响因素及其影响规律仍缺少大量的定量论证。为此，本文构建了温度植被干旱指数(Temperature vegetation dryness index,TVDI)用以反映黄土高原土壤水分的高低[31-34],通过残差法剔除土壤水分来表示植被覆盖的人为影响，并分析了植被覆盖人为影响的时空演变格局，利用地理探测器及相关分析法探究黄土高原多种人为因素对植被覆盖影响的程度、正负作用方向以及其时间变化规律，以期确定影响黄土高原植被覆盖变化的人为主导因子，并为前期的生态建设工程的维持与未来退耕还林工程的实施提供坚实的依据，有助于黄土高原生态环境健康、良性与可持续发展。

# 1 研究方法

# 1.1数据来源

本文数据主要包括黄土高原植被覆盖、地表温度、生态区划以及农业生产总值、城市分布、城市化率、GDP、人口、交通、土地利用、高级别旅游景点等人文社会数据。植被覆盖来自2001—2018年MO-DIS产品的MOD13A2数据集，经重投影获取16d的NDVI时序数据；地表温度(Land surface tempera-ture,LST)来自2001—2018年的MOD11A2数据集，获取8d的LST时序数据。生态区划数据来源于中国生态系统评估与生态安全格局数据库(www.eco-system.csdb.cn/index.jsp）。

人文社会数据中的农业生产总值、城市化率、GDP、人口均来源于黄土高原各个县区2001—2018年统计年鉴，并利用经验贝叶斯克里金法将其进行面插值得到其空间分布；城市数据是各地市市级行政区所在地，对其进行欧氏距离分析得到城市分布；交通数据来自全国地理信息资源目录服务系统的1:1000000全国基础地理数据库，经提取分别获取铁路、国道、省道和县道，分别对其进行线密度分析并加权得到交通分布；土地利用数据来自中国科学院资源环境科学数据中心(http://www.resdc.cn/)中国2000、2005、2010、2015、2018年土地利用数据，经过重分类得到土地利用一级类别，采用邻域分析并结合地类分级指数[32]获取5个年份的土地利用程度，最后通过3次样条函数插值得到2001—2018年各个年份的土地利用程度；高级别旅游景点来自黄土高原覆盖的各个省份旅游政务网，主要包括4A和5A级景点，并通过百度坐标拾取器逐个查询得到各个景点的经纬度坐标，分别对4A和5A级景点进行核密度分析并加权得到高级别旅游景点分布。

# 1.2土壤湿度估算

由于研究区内LST具有无效数据导致其时序不连续，因此利用Whittaker平滑器[35]将8d的LST时序数据进行重构，并间隔提取得到16d的LST时序数据。本文采用TVDI来表征土壤湿度[36],基于每16d的NDVI和LST梯形特征空间估算得到每16d的TVDI数据，进而采用平均值合成法合成TVDI和NDVI的年际数据。TVDI原理如下：

$$
\mathrm { T V D I } { = } \frac { \mathrm { T s } - \mathrm { T s } _ { \mathrm { m i n } } } { \mathrm { T s } _ { \mathrm { m a x } } - \mathrm { T s } _ { \mathrm { m i n } } }
$$

式中：Ts为每个像元的 $\mathrm { L S T } ; \mathrm { T s } _ { \mathrm { m i n } }$ 为对应像元湿边的LST; $\mathrm { T s } _ { \mathrm { m a x } }$ 为对应像元干边的LST。

# 1.3植被覆盖人为影响

本文通过提取逐像元的NDVI和TVDI年际时序来建立回归方程估算NDVI预测值，NDVI的真实值与回归方程估算的预测值之差即为残差序列，用以分析植被覆盖人为影响的时空演变，其原理如下[37]：

$$
\widehat { \boldsymbol { y } } _ { i } = \boldsymbol { \beta } _ { 0 } + \boldsymbol { \beta } _ { 1 } \boldsymbol { x } _ { i } + \boldsymbol { \zeta }
$$

$$
e _ { i } = y _ { i } - \hat { y } _ { i }
$$

式中： $y _ { i }$ 为 NDVI的真实值; $\widehat { \boldsymbol { y } } _ { i }$ 为回归方程估算的NDVI预测值； $x _ { i }$ 为TVDI; $e _ { i }$ 为NDVI真实值与预测值之差(残差）； $i$ 为时间，本文中则为年份。

# 1.4未来演变分析

本文利用Theil-Sen趋势对植被覆盖人为影响进行趋势分析[38],经过Mann-Kendall检验以表示变化趋势的显著性，将显著性划分为4个级别，分别为

# 干吴区地理

极显著 $\left( P < 0 . 0 1 \right)$ 、显著 $( 0 . 0 1 { \leqslant } P < 0 . 0 5 )$ 、弱显著$( 0 . 0 5 { \leqslant } P < 0 . 1 )$ 和不显著 $( P { \geqslant } 0 . 1 )$ ;利用Hurst指数[39]反映植被覆盖人为影响变化的持续性特征，将Hurst指数划分为3个级别，分别表示反持续性( $\left( < 0 . 3 5 \right)$ 、弱持续性(0.35\~0.65)和持续性 $( > 0 . 6 5 )$ 。对趋势分析和Hurst指数重分类结果进行叠加分析，用以反映黄土高原植被覆盖人为影响未来演变趋势。

# 1.5地理探测器

本文运用地理探测器中的因子探测分析黄土高原植被覆盖人为影响归因及其变化特征。因子探测器用来探测各因子对植被覆盖人为影响空间分异的解释程度，用 $q$ 值来衡量， $q$ 值越大，表示因子$X$ 对植被覆盖人为影响空间分异的解释力越强;反之则越弱。 $q$ 值表示因子 $X$ 解释了 $1 0 0 \times q \%$ 的植被覆盖人为影响空间分异。具体方法过程详见文献[40]。

# 2结果与分析

# 2.1黄土高原植被覆盖人为影响变化趋势

黄土高原2001—2018年植被覆盖人为影响变化趋势为 $0 . 3 6 { \times } 1 0 ^ { - 2 } \mathrm { a } ^ { - 1 }$ ，人为活动对植被覆盖的影响向正作用方向发展。植被覆盖人为影响变化趋势空间分异明显(图1a)，正作用发展区分布面积很广，占研究区的比重为 $8 4 . 8 5 \%$ ，主要分布于陕北高原一陇中高原及其之间的区域;负作用发展区集中于汾渭盆地、湟水谷地、前套平原与研究区南部的秦岭山地。从不同生态区来看，秦岭山地落叶与常绿阔叶林生态区植被覆盖人为影响向负作用方向发展 $\left( - 7 . 5 1 \times 1 0 ^ { - 5 } \mathrm { ~ a } ^ { - 1 } \right)$ ，其余生态区均向正作用方向发展，其中：黄土高原农业与草原生态区植被覆盖人为影响正作用较强，残差趋势为 $5 . 2 8 \times 1 0 ^ { - 3 } \mathrm { ~ a } ^ { - 1 }$ ;其次为内蒙古高原中东部典型草原生态区与内蒙古高原中部一陇中荒漠草原生态区，残差趋势约为$4 . 0 0 { \times } 1 0 ^ { - 3 } \mathrm { a } ^ { - 1 }$ ;燕山一太行山山地落叶阔叶林生态区与江河源区一甘南高寒草甸草原生态区残差趋势约为 $2 . 0 0 { \times } 1 0 ^ { - 3 } \mathrm { a } ^ { - 1 }$ ;祁连山森林与高寒草原生态区与汾渭盆地农业生态区植被覆盖人为影响正作用发展趋势缓慢，尤其是汾渭盆地农业生态区，残差趋势仅为 $2 . 1 4 \times 1 0 ^ { - 7 } \mathrm { a } ^ { - 1 }$ 。

综上，黄土高原农业与草原生态区植被覆盖人为影响向正作用方向的发展趋势很强，而汾渭盆地农业生态区的人为影响趋势很弱；森林生态区植被覆盖人为影响发展方向具有明显的空间差异性，其中南北走向的太行山、吕梁山等山地区植被覆盖的人为影响向正作用方向发展，值得注意的是东西走向的秦岭山区植被覆盖的人为影响向负作用方向发展；典型草原和荒漠草原植被覆盖人为影响向正作用发展的趋势较高，而高寒草甸草原次之。

以植被覆盖人为影响均值为基准，将均值正负、变化趋势的正负及其显著性进行空间叠加（图1b)。从空间分布来看，“负负"影响区表示人为影

![](images/4eca938b5e130cfbbeee2ac920dcd01c40e7a85cce58cf0f48db2877a435d8d5.jpg)  
图1黄土高原植被覆盖人为影响变化趋势及其显著性

注：生态区代码I-10,燕山—太行山山地落叶阔叶林生态区;I-11,汾渭盆地农业生态区;I-12,黄土高原农业与草原生态区;I-15,秦巴山地落叶与常绿阔叶林生态区;II-1,内蒙古高原中东部典型草原生态区;II-2,内蒙古高原中部—陇中荒漠草原生态区;I-3,内蒙古高原中部草原化荒漠生态区;II-1,祁连山森林与高寒草原生态区;II-4,江河源区—甘南高寒草甸草原生态区。图b图例中代码表示变化趋势的显著性,1表示极显著，2表示显著，3表示弱显著，4表示不显著。

Fig.1 Trend and its significance of anthropogenic effects on vegetation cover on the Loess Plateau响的负作用在 $1 8 \mathrm { ~ a ~ }$ 间呈增强趋势，其面积仅占研究区的 $0 . 7 6 \%$ ，主要分布于汾渭盆地和豫西南一崤山以东区域；“负正"影响区表示人为影响的负作用呈减小趋势，面积比重为 $6 . 3 4 \%$ ,显著区占 $6 . 3 4 \%$ ，分布于研究区西北部陇中一宁中、鄂尔多斯高原的荒漠草原区；“正负"影响区表示人为影响的正作用呈减小趋势，面积占比为 $2 . 7 2 \%$ ,但其显著区仅为 $2 . 7 2 \%$ ，集中分布于研究区各个农业区，其中包括汾渭盆地、太行山一太岳山间丘陵地带、宁夏平原与湟水谷地，其次研究区南部的秦巴山区、北部的阴山山地以及东部的太行山山地区也有分布；“正正"影响区表示人为影响的正作用呈增强趋势，其面积分布最广，遍布整个研究区，占研究区总面积的 $4 2 . 9 4 \%$ ，其中显著区占 $4 2 . 9 4 \%$ ,极显著区主要分布于鄂尔多斯高原东部典型草原区与陕北中北部的丘陵沟壑区。

# 2.2黄土高原植被覆盖人为影响未来演变趋势

经统计得到整个黄土高原逐年植被覆盖人为影响均值序列，其Hurst指数为0.47，人为影响呈现出反持续性特征，结合18a间人为影响向正作用方向发展，反映出黄土高原未来变化趋势由正作用转为向负作用方向发展。植被覆盖人为影响的弱持续性区域比重高达 $8 6 . 4 1 \%$ ;其次为反持续性区，面积占 $1 0 . 4 2 \%$ ,持续性区面积比例仅为 $3 . 1 7 \%$ ，反映出植被覆盖人为影响18a间变化随机性较强（图 $2 \mathrm { a }$ 。

将植被覆盖人为影响均值正负、变化趋势的正负以及序列持续性进行空间叠加(图2b)，并结合统计值以反映人为影响的未来变化。“正正-反"表示植被覆盖人为正作用未来变化由增强转为减弱趋势，分布面积最广，面积比重达 $4 9 . 4 2 \%$ ，分布区遍布整个研究区，其中东部主要分布于太行山、太岳山、吕梁山、中条山山地等落叶阔叶林，中部分布于陕北一晋西丘陵沟壑区，西南部分布于陕中黄土塬梁农业区、陇东南丘陵残塬农业/草原区以及黄土高原西部农业区，其次分布在西北部的荒漠草原区；“正正-持"表示植被覆盖人为正作用未来变化持续增强，面积比重为 $2 4 . 4 9 \%$ ,其分布区域基本上与“正正-反"区域毗邻，集中分布于晋北山地丘陵干旱草原区；“正负-反"与"负正-反"分布面积比重分别为$7 . 3 0 \%$ 和 $7 . 2 5 \%$ ，两者空间分布具有明显的地域分异，其中“正负-反”主要分布于研究区东南部的农业区，其次西部的湟水谷地和前套平原农业区也有分布，而“负正-反”主要分布于研究区西北部的荒漠草原区 $( 7 . 2 5 \%$ );其余4种未来变化区面积仅占总面积的 $1 1 . 5 6 \%$ ,且分布较为零散。

值得关注的是8种类型中面积占比最大的“正正-反”，该区域为退耕还林重点实施区，但其人为正作用未来变化呈减弱趋势，因此有必要对该区域植被覆盖的人为影响进行深入分析，以便为黄土高原生态环境的健康发展提供有力的依据。

# 2.3黄土高原植被覆盖人为影响归因及其变化特征

查阅相关文献资料进行总结以及根据实际情况获取的数据可靠性，本研究选取8种与植被覆盖人为影响有关的因子作为人为因素的主要方面(农业生产总值、城市分布、城市化率、GDP、人口、交通、土地利用和高级别景区）。以逐年植被覆盖人为影响空间分布为因变量 $( Y )$ ,8种影响因素空间分布为自变量 $( \boldsymbol { \cal { X } } )$ ，分别运用等间隔和自然断点法对8种影响因素进行离散化，分别通过地理探测器得到逐年

![](images/7abaa6aea0f4e97c2ef13c61067e450109c5474d421c7bec6ea06085618bf1a3.jpg)  
图2黄土高原植被覆盖人为影响未来演变趋势  
Fig.2 Future evolution of anthropogenic effects on vegetation cover on the Loess Plateau

# 干旱区地理

植被覆盖人为影响空间分异与8种因素之间的 $q$ 统计值，发现自然断点法探测的 $q$ 值均大于等间隔离散化，反映出影响因素的自然断点法离散结果与人为影响空间分异具有更高的一致性。因此，最终选用自然断点法离散化结果输入地理探测器,并将 $q$ 值可视化在色阶图中，反映多种人为因素对植被覆盖影响的时间变化规律(表1)。

从18a(2001—2018年)的人为因子 $q$ 统计值来看，城市分布和高级别旅游景点对植被覆盖影响较高，其次为土地利用分布，其余因子影响力相对较弱，且依次为人口、交通、城市化率、农业生产总值和GDP。究其主要原因：城市分布区域是资源、信息、人口汇集的中心，城市的大范围快速扩张，对原有生态环境造成损害，因而表现为城市分布对植被覆盖影响较大。高级别旅游景点的旅游活动相对较为活跃，景区的基础设施建设以及密集的游客活动容易对景区的生态环境产生十扰，引起植被退化，从而表现为高级别旅游景点对植被覆盖影响较大。土地利用是人类按一定的经济、社会目的对土地进行治理与改造,其过程对植被生态产生影响，因而土地利用也是重要的影响植被覆盖变化的人为因素。

通过相关分析得到黄土高原逐年植被覆盖人为影响空间分异与8种因素之间的相关系数，并将其可视化在色阶图中，以反映多个人为因素对植被覆盖影响的方向及其时间变化规律(表2)。从表2相关系数明显可知，人为影响与高级别旅游景点、城市、土地利用及交通的相关性较高，其与地理探测器结果基本吻合，差异性体现于交通，近年来轨道交通的迅猛发展以及其对生态环境造成的影响不容忽视，因此相关分析结合地理探测器,影响植被覆盖变化的人为主导因子主要包括高级别旅游景点、城市分布、土地利用和交通。从相关性的时间变化来看，2001一2018年人为影响与各个因素相关性呈现出明显的时间变化特征，且相关系数呈“负正负"的变化特征;1999年退耕还林工程开始，该工程的起始阶段(2001一2002年)各个主导因素对黄土高原植被覆盖呈负作用影响;2003—2011年各主导因素对黄土高原植被覆盖表现出明显的正作用影响，这主要是退耕还林工程改善生态环境引起的，但是该阶段正作用具有明显的下降趋势；从2012年起始，各个因素对黄土高原植被覆盖影响表现为负作用，且这种负作用呈明显的增加趋势，其中2016—2018年负作用影响变化尤为强烈。

表1黄土高原植被覆盖人为影响因素q统计值  

<html><body><table><tr><td colspan="8">Tab.1 q statistical value of human influence factors of vegetation cover on the Loess Plateau</td></tr><tr><td>年份</td><td>农业生产总值</td><td>城市分布</td><td>城市化率</td><td>GDP</td><td>人口</td><td>交通</td><td>土地利用 高级别旅游景点</td></tr><tr><td>2001</td><td>0.144</td><td>0.099</td><td>0.014</td><td>0.004</td><td>0.055</td><td>0.092</td><td>0.316 0.034</td></tr><tr><td>2002</td><td>0.049</td><td>0.141</td><td>0.175</td><td>0.059 0.079</td><td>0.028</td><td>0.184</td><td>0.222</td></tr><tr><td>2003</td><td>0.252</td><td>0.116</td><td>0.077</td><td>0.081</td><td>0.298 0.163</td><td>0.270</td><td>0.169</td></tr><tr><td>2004</td><td>0.080</td><td>0.419</td><td>0.075</td><td>0.037</td><td>0.074</td><td>0.323 0.294</td><td>0.444</td></tr><tr><td>2005</td><td>0.109</td><td>0.478</td><td>0.054</td><td>0.129</td><td>0.144</td><td>0.094 0.075</td><td>0.387</td></tr><tr><td>2006</td><td>0.102</td><td>0.259</td><td>0.081</td><td>0.061</td><td>0.191</td><td>0.179 0.226</td><td>0.274</td></tr><tr><td>2007</td><td>0.114</td><td>0.286</td><td>0.106</td><td>0.073</td><td>0.263</td><td>0.196 0.204</td><td>0.318</td></tr><tr><td>2008</td><td>0.086</td><td>0.230</td><td>0.142</td><td>0.193</td><td>0.049</td><td>0.041 0.128</td><td>0.085</td></tr><tr><td>2009</td><td>0.133</td><td>0.192</td><td>0.112</td><td>0.009</td><td>0.261 0.017</td><td>0.176</td><td>0.104</td></tr><tr><td>2010</td><td>0.209</td><td>0.144</td><td>0.025</td><td>0.031</td><td>0.131</td><td>0.101 0.108</td><td>0.233</td></tr><tr><td>2011</td><td>0.015</td><td>0.218</td><td>0.234</td><td>0.358</td><td>0.005 0.010</td><td>0.101</td><td>0.307</td></tr><tr><td>2012</td><td>0.075</td><td>0.186</td><td>0.040</td><td>0.035</td><td>0.073</td><td>0.082 0.111</td><td>0.141</td></tr><tr><td>2013</td><td>0.177</td><td>0.212</td><td>0.298</td><td>0.172</td><td>0.127 0.062</td><td>0.288</td><td>0.147</td></tr><tr><td>2014</td><td>0.041</td><td>0.154</td><td>0.020</td><td>0.062</td><td>0.164</td><td>0.086 0.051</td><td>0.159</td></tr><tr><td>2015</td><td>0.026</td><td>0.101</td><td>0.211</td><td>0.102</td><td>0.027</td><td>0.100 0.083</td><td>0.018</td></tr><tr><td>2016</td><td>0.072</td><td>0.187</td><td>0.347</td><td>0.217</td><td>0.268</td><td>0.042 0.133</td><td>0.216</td></tr><tr><td>2017</td><td>0.193</td><td>0.312</td><td>0.048</td><td>0.079</td><td>0.421</td><td>0.370</td><td>0.486 0.405</td></tr><tr><td>2018</td><td>0.293</td><td>0.767</td><td>0.132</td><td>0.051</td><td>0.335</td><td>0.371</td><td>0.465 0.838</td></tr></table></body></html>

注：逐年各因子 $q$ 值的 $P$ 检验值均小于0.01。

表2黄土高原植被覆盖人为影响与各影响因素的相关系数  
Tab.2 Correlation coefficient between the anthropogenic and various influencing factors of vegetation cover on the Loess Plateau   

<html><body><table><tr><td>年份</td><td>农业生产总值</td><td>城市分布</td><td>城市化率</td><td>GDP</td><td>人口</td><td>交通</td><td>土地利用</td><td>高级别旅游景点</td></tr><tr><td>2001</td><td>-0.0916</td><td>-0.0325</td><td>-0.0916</td><td>-0.0018</td><td>-0.0019</td><td>-0.0433</td><td>-0.3393</td><td>0.0399</td></tr><tr><td>2002</td><td>-0.0301</td><td>-0.3178</td><td>-0.0301</td><td>-0.0019</td><td>-0.0019</td><td>0.0124</td><td>-0.1663</td><td>-0.2053</td></tr><tr><td>2003</td><td>-0.0282</td><td>0.2096</td><td>-0.0282</td><td>0.0048</td><td>0.0047</td><td>0.6090</td><td>0.4208</td><td>0.4938</td></tr><tr><td>2004</td><td>-0.0043</td><td>0.8979</td><td>-0.0043</td><td>0.0019</td><td>0.0019</td><td>0.8984</td><td>0.6714</td><td>0.9546</td></tr><tr><td>2005</td><td>-0.0220</td><td>0.9328</td><td>-0.0220</td><td>0.0020</td><td>0.0020</td><td>0.5165</td><td>0.1535</td><td>0.8712</td></tr><tr><td>2006</td><td>-0.0391</td><td>0.4924</td><td>-0.0391</td><td>-0.0004</td><td>-0.0004</td><td>0.4684</td><td>0.3600</td><td>0.7261</td></tr><tr><td>2007</td><td>0.0348</td><td>0.5941</td><td>0.0348</td><td>0.0057</td><td>0.0057</td><td>0.7261</td><td>0.4853</td><td>0.7926</td></tr><tr><td>2008</td><td>0.0445</td><td>0.0980</td><td>0.0445</td><td>0.0000</td><td>0.0000</td><td>0.3772</td><td>-0.0543</td><td>0.3395</td></tr><tr><td>2009</td><td>0.0559</td><td>0.2770</td><td>0.0559</td><td>0.0000</td><td>0.0000</td><td>-0.0830</td><td>0.0809</td><td>0.2743</td></tr><tr><td>2010</td><td>-0.0519</td><td>0.4562</td><td>-0.0519</td><td>0.0015</td><td>0.0015</td><td>0.4878</td><td>0.1628</td><td>0.5610</td></tr><tr><td>2011</td><td>0.0195</td><td>0.7441</td><td>-0.0195</td><td>-0.0011</td><td>-0.0011</td><td>0.0713</td><td>0.4982</td><td>0.4707</td></tr><tr><td>2012</td><td>0.0638</td><td>-0.3472</td><td>0.0638</td><td>0.0051</td><td>0.0051</td><td>v0.2916</td><td>-0.1162</td><td>-0.3403</td></tr><tr><td>2013</td><td>0.0903</td><td>-0.1513</td><td>0.0903</td><td>0.0026</td><td>0.0027</td><td>-0.2406</td><td>0.2518</td><td>-0.3454</td></tr><tr><td>2014</td><td>0.0513</td><td>-0.2500</td><td>0.0513</td><td>-0.0022</td><td>-0.0021</td><td>-0.2631</td><td>-0.1474</td><td>-0.2518</td></tr><tr><td>2015</td><td>-0.0122</td><td>0.1400</td><td>-0.0122</td><td>-0.0087</td><td>-0.0087</td><td>-0.1198</td><td>-0.0199</td><td>0.0218</td></tr><tr><td>2016</td><td>0.0277</td><td>-0.3796</td><td>0.0277</td><td>0.0073</td><td>0.0073</td><td>-0.1733</td><td>-0.2952</td><td>-0.4002</td></tr><tr><td>2017</td><td>0.0300</td><td>-0.3784</td><td>0.0300</td><td>-0.0027</td><td>-0.0027</td><td>-0.4805</td><td>-0.2563</td><td>-0.5774</td></tr><tr><td>2018</td><td>0.0498</td><td>-0.8808</td><td>0.0498</td><td>-0.0022</td><td>-0.0022</td><td>-0.6251</td><td>-0.3718</td><td>-0.9327</td></tr></table></body></html>

注：相关系数的 $P$ 检验值均小于 $0 . 0 5$ 0

因此，根据近18a人为影响与各个因子之间的相关性，前期的生态建设工程的维持，应该着重发展绿色旅游业，以保护环境、保护生态平衡为前提提升旅游业产值；其次随着城市化不断扩张，城市分布对植被覆盖变化的影响力也将不断提升;另外值得注意的是迅猛发展的交通业以及快速变化的土地利用，其对植被覆盖变化的影响力也在逐渐增加。根据近3a人为主导因子的负作用增幅变化特征，未来退耕还林工程的实施，应该着重减缓交通业对生态环境所带来的危害，其次加强绿色旅游业发展以及减缓土地变化等人为活动的影响。

# 3结论

本文的主要结论为：

（1）黄土高原2001—2018年植被覆盖人为影响变化趋势为 $0 . 3 6 \times 1 0 ^ { - 2 } \mathrm { a } ^ { - 1 }$ ，人为活动对植被覆盖的影响向正作用方向发展。植被覆盖人为影响变化趋势空间分异明显，正作用发展区分布面积很广，主要分布于陕北高原一陇中高原及其之间的区域;负作用发展区集中于汾渭盆地、湟水谷地、前套平原与研究区南部的秦岭山地。

（2）黄土高原2001—2018年植被覆盖人为影响Hurst指数为0.47，人为影响呈现出反持续性特征，结合18a间人为影响向正作用方向发展，反映出黄土高原未来变化趋势由正作用转为向负作用方向发展，值的关注的是退耕还林重点实施区，该区域植被覆盖的人为正作用未来变化呈减弱趋势，应注重人为正作用返恶化问题。

（3）经地理探测器筛选出对植被覆盖影响较高的人为因子为城市分布、高级别旅游景点、土地利用。经相关分析筛选出对植被覆盖影响较高的人为因子依次为高级别旅游景点、城市分布、交通分布和土地利用。综合相关分析与地理探测器结果，确定影响植被覆盖变化的人为主导因子主要包括高级别旅游景点、城市分布、交通和土地利用。

(4）随着城市规模的不断扩大，城市分布对植被覆盖变化的影响力也将不断提高，迅猛发展的旅游业、交通业以及快速变化的土地利用，其对植被覆盖变化的影响力也在逐渐增加。未来退耕还林工程的实施以及生态建设工程的维持，应注重在城市经济发展的同时重视生态建设，减缓交通业对生态环境所带来的危害，加强绿色旅游业发展以及减

# 干旱区地理

缓土地变化等人为活动的影响。

参考文献(References)   
[1]成德宁.城市化与经济发展:理论、模式与政策[M].北京:科学 出版社,2OO4.[Cheng Dening.Urbanization and economic development: Theory，model and policy[M].Beijing:Science Press, 2004.]   
[2]段禄峰,田宇轩,魏明.我国城镇化发展快慢问题研究[J].理论 探索,2016(5): 102-108.[Duan Lufeng,Tian Yuxuan,Wei Ming. Research on the speed of urbanization in China[J]. Theoretical Exploration,2016(5): 102-108.]   
[3]徐秋艳,房胜飞,马琳琳.新型城镇化、产业结构升级与中国经 济增长:基于空间溢出及门槛效应的实证研究[J].系统工程理 论与实践,2019,39(6): 1407-1418.[Xu Qiuyan,Fang Shengfei, Ma Linlin.New urbanization, upgrading of industrial structure and China’s economic growth: Empirical research based on spatial spillover and threshold effect[J]. Systems Engineering-Theory& Practice,2019,39(6): 1407-1418.]   
[4]吕志强,卿姗姗,邓睿.中国人口城市化与土地城市化协调性分 析[J].城市问题,2016(6):33-38.[Lu Zhiqiang, Qing Shanshan, Deng Rui.Analysis on the coordination between population urbanization and land urbanization in China[J].Urban Problems,2016 (6): 33-38.]   
[5]陈凤桂,张虹鸥,吴旗韬.我国人口城镇化与土地城镇化协调发 展研究[J].人文地理,2010,115(5):53-58.[Chen Fenggui, Zhang Hong'ou,Wu Qitao.A study on coordinate development between population urbanization and land urbanization in China[J]. Human Geography,2010,115(5): 53-58.]   
[6]张戈丽,徐兴良,周才平.近30年来呼伦贝尔地区草地植被变 化对气候变化的响应[J].地理学报,2011,66(1):47-58.[Zhang Geli, Xu Xingliang, Zhou Caiping. Responses of vegetation changes to climatic variations in Hulun Buir grassland in past 3O years [J].Acta Geographica Sinica,2011, 66(1): 47-58.]   
[7]刘宪锋,潘耀忠,朱秀芳.2000—2014年秦巴山区植被覆盖时 空变化特征及其归因[J].地理学报,2015,70(5):705-716.[Liu Xianfeng,Pan Yaozhong,Zhu Xiufang.Spatiotemporal variation of vegetation coverage in Qinling-Daba Mountains in relation to environmental factors[J].Acta Geographica Sinica,2015,70(5):705- 716.]   
[8]杨思遥,孟丹,李小娟.华北地区2001—2014年植被变化对 SPEI气象干旱指数多尺度的响应[J].生态学报,2018,38(3): 1028-1039.[Yang Siyao,Meng Dan,Li Xiaojuan. Multi-scale responses of vegetation changes relative to the SPEI meteorological drought index in north China in 2001—2014[J].Acta Ecologica Sinica,2018,38(3): 1028-1039.]   
[9]王强,张勃,戴声佩.三北防护林工程区植被覆盖变化与影响因 子分析[J].中国环境科学,2012,32(7):1302-1308.[Wang Qiang,Zhang Bo,Dai Shengpei. Analysis of the vegetation cover change and its relationship with factors in the Three-North Shelter Forest Program[J]. China Environmental Science,2012,32(7): 1302-1308.]   
[10] 魏彦强,芦海燕,王金牛,等.近35年青藏高原植被带变化对气 候变化及人类活动的响应[J].草业科学,2019,36(4):1163- 1176.[Wei Yanqiang, Lu Haiyan, Wang Jinniu. Responses of vegetation zones,in the Qinghai-Tibetan Plateau,to climate change and anthropogenic influences over the last 35 years[J].Pratacultural Science,2019,36(4): 1163-1176.]   
[11] 王建邦,赵军,李传华.2001—2015年中国植被覆盖人为影响 的时空格局[J].地理学报,2019,74(3):504-519.[Wang Jianbang, Zhao Jun,Li Chuanhua. The spatial-temporal patterns of the impact of human activities on vegetation coverage in China from 2001 to 2015[J]. Acta Geographica Sinica,2019,74(3): 504-519.]   
[12] 张照男,祁应军,张杨.基于残差趋势法的赤峰市植被变化的人 为影响研究[J].生态经济,2018,34(9):206-211.[Zhang Zhaonan, Qi Yingjun, Zhang Yang. Study of human influence on Chifeng vegetation change based on residual trend method[J]. Ecological Economy,2018,34(9): 206-211.]   
[13]马启民,贾晓鹏,王海兵.气候和人为因素对植被变化影响的评 价方法综述[J].中国沙漠,2019,39(6):1-8.[Ma Qimin,Jia Xiaopeng,Wang Haibing. Recent advances in driving mechanisms of climate and anthropogenic factors on vegetation change[J]. Journal of Desert Research, 2019,39(6): 1-8.]   
[14]Evans J, Geerken R. Discrimination between climate and human induced dryland degradation[J]. Journal of Arid Environments, 2004, 57(4): 535-554.   
[15]Wessels K,Prince S,Malherbe J. Can human-induced land degradation be distinguished from the effectsof rainfall variability: A case study in South Africa[J].Journal of Arid Environments,2007, 68(2): 271-297.   
[16] 李晓光,刘华民,王立新.鄂尔多斯高原植被覆盖变化及其与气 候和人类活动的关系[J].中国农业气象,2014,35(4):470-476. [Li Xiaoguang, Liu Huamin, Wang Lixin. Vegetation cover change and its relationship between climate and human activities in Ordos Plateau[J]. Chinese Journal of Agrometeorology,2014,35(4): 470-476.]   
[17]Mueller T, Dressler G,Tucker C. Human land-use practices lead to global long-term increases in photosynthetic capacity[J]. Remote Sensing,2014, 6(6): 5717-5731.   
[18] Liu Y,Li Y,Li S C.Spatial and temporal paterns of global NDVI trends: Correlations with climate and human factors[J]. Remote Sensing,2015,7(10): 13233-13250.   
[19] Sanderson E,Levy M,Redford K.The human footprint and the last of the wild[J]. Bioscience,2002,52(10): 891-904.   
[20]Chen A F,LiR Y,Wang HL. Quantitative assessment of human appropriation of aboveground net primary production in China[J]. Ecological Modelling,2015,312(24): 54-60.   
[21]Andersen C,Donovan R,QuinnJ. Human appropriationofnet primary production (HANPP) in an agriculturally-dominated watershed, southeastern USA[J]. Land,2015,4(2): 513-540.   
[22]Plutzar C, Kroisleitner C,Haberl H. Changes in the spatial patterns of human appropriation of net primary production in Europe 1990——2006[J]. Regional Environmental Change,2016,16(5): 125- 1238.   
[23]白子怡,薛亮,薛东前.关中-天水经济区人类活动对植被覆盖 变化的影响[J].中国农业大学学报,2020,25(2):151-159.[Bai Ziyi, Xue Liang,Xue Dongqian.Impact of human activities on the vegetation cover change in Guanzhong- Tianshui economic zone[J]. Journal of China Agricultural University,2020,25(2):151-159.]   
[24] 邓晨晖,白红英,高山.秦岭植被覆盖时空变化及其对气候变化 与人类活动的双重响应[J].自然资源学报,2018,33(3):425- 438.[Deng Chenhui,Bai Hongying,Gao Shan.Spatial-temporal variation of the vegetation coverage in Qinling Mountains and its dual response to climate change and human activities[J]. Journal of Natural Resources,2018,33(3): 425-438.]   
[25]于璐,武志涛,杜自强,等.气候变化背景下京津风沙源区人类 活动对植被影响的量化分析[J].应用生态学报,2020,31(6): 2007—2014.[Yu Lu, Wu Zhitao,Du Ziqiang.Quantitative analysis of the effects of human activities on vegetation in the BeijingTianjin sandstorm source region under the climate change[J]. Chinese Journal of Applied Ecology,2020,31(6): 2007-2014.]   
[26]王巨.基于时序NDVI植被变化检测与驱动因素量化方法研究 [D].兰州:兰州大学,2020.[Wang Ju.Methods fordetecting vegetation changes and quantifying the driving factors using NDVI time series by taking Hexi as a case area[D]. Lanzhou: Lanzhou University,2020.]   
[27]白天路.基于遥感和地面实测水分数据的小流域土壤水分模拟 [D].西安:西北大学,2010.[Bai Tianlu.Soil moisture simulation based on remote sensing and ground data in watershed[D]. Xi'an: Northwest University,2010.]   
[28] 郭继凯,吴秀芹,董贵华.基于MODIS/NDVI的塔里木河流域植 被覆盖变化驱动因素相对作用分析[J].干旱区研究,2017,34 (3): 621-629.[Guo Jikai,Wu Xiuqin,Dong Guihua.Vegetation coverage change and relative effcts of driving factors based on MODIS/NDVI in the Tarim River Basin[J].Arid Zone Research, 2017, 34(3): 621-629.]   
[29] 阿荣,毕其格,董振华.基于MODIS/NDVI的锡林郭勒草原植被 变化及其归因[J].资源科学,2019,41(7):1374-1386.[A Rong, Bi Qige, Dong Zhenhua. Change of grassand vegetation and driving factors based on MODIS/NDVI in Xilingol, China[J]. Resources Science,2019,41(7): 1374-1386.]   
[30] 易浪,任志远,张.黄土高原植被覆盖变化与气候和人类活动 的关系[J].资源科学,2014,36(1):166-174.[Yi Lang,Ren Zhiyuan, Zhang Chong.Vegetation cover,climate and human activities on the Loess Plateau[J]. Resources Science,2014,36(1): 166-174.]   
[31] 刘立文,张吴平,段永红.TVDI模型的农业旱情时空变化遥感 应用[J].生态学报,2014,34(13): 3704-3711.[Liu Liwen,Zhang Wuping,Duan Yonghong. Terrain corrected TVDI for agricultural drought monitoring using MODIS data[J]. Acta Ecologica Sinica, 2014,34(13): 3704-3711.]   
[32]Patel N R,Anapashsha R, Kumar S,et al. Assessing potential of MODIS derived temperature/vegetation condition index (TVDI) to infer soil moisture status[J]. International Journal of Remote Sensing,2009,30(1): 23-39.   
[33] 宋春桥,游松财,刘高焕.基于TVDI的藏北地区土壤湿度空间 格局[J].地理科学进展,2011,30(5): 570-576.[Song Chunqiao, You Songcai,Liu Gaohuan. The spatial pattern of soil moisture in northern Tibet based on TVDI method[J].Progress in Geography, 2011,30(5): 570-576.]   
[34] 邸兰杰,王卫,成贺玺.基于ATI和TVDI模型的河北平原土壤 湿度遥感反演[J].中国生态农业学报,2014,22(6):737-743. [Di Lanjie,Wang Wei, Cheng Hexi. Remote sensing inversion of soil moisture in Hebei Plain based on ATI and TVDI models[J]. Chinese Journal of Eco-Agriculture,2014,22(6): 737-743.]   
[35] 杨桂燕,李路,陈和.基于广义Whittaker平滑器的拉曼光谱基 线校正方法[J].中国激光,2015,42(9):360-368.[Yang Guiyan, Li Lu, Chen He. Baseline correction method for Raman spectra based on generalized Whittaker smoother[J]. Chinese Journal of Lasers,2015,42(9): 360-368.]   
[36] Sandholt I, Rasmussen K,Andersen J.A simple interpretation of the surface temperature/vegetation index space for assessment of surface moisture status[J]. Remote Sensing of Environment. 2002, 79(2-3),213-224.   
[37］ 黄森旺.三北防护林工程区土地退化的时空变化和驱动力分析 [D].阜新:辽宁工程技术大学,2012.[Huang Senwang.The distribution and drixer anlysis ofland degradation in the Three-North Shelter Forest region of China[D].Fuxin: Liaoning Technical University,2012.]   
[38] 王佃来,刘文萍,黄心渊.基于Sen+Mann-Kendall的北京植被变 化趋势分析[J].计算机工程与应用,2013,49(5):13-17.[Wang Dianlai, Liu Wenping,Huang Xinyuan. Trend analysis in vegetation cover in Beijing based on Sen $^ +$ Mann-Kendall method[J]. Computer Engineering and Applications,2013,49(5): 13-17.]   
[39]Feng D R,Wang JM,Fu M C,et al. Spatiotemporal variation and influencing factors of vegetation cover in the ecologically fragile areas of China from 200O to 2015: A case study in Shaanxi Province [J]. Environmental Science and Polution Research,2O19,26(28): 977-992.   
[40]王劲峰,徐成东.地理探测器:原理与展望[J].地理学报,2017, 72(1): 116-134.[Wang Jinfeng, Xu Chengdong. Geodetector: Principle and prospective[J].Acta Geographica Sinica, 2017,72(1): 116-134.]

# Spatio-temporal evolution and attribution analysis of human effects of vegetation cover on the Loess Plateau from 2oo1 to 2018

ZHANG Chong'， BAI Ziyi², LI Xuemei³， RAN Qiqi',WEI Zhenfeng4， LEI Tianwang， WANG Na6

(1.ShaaxiKeyLaboratoryofDisasterMonitoringand MechanismModeling,Baoji UniversityofArtsandSiences,Baoji721013, Shaanxi,China；2.cholofGeogapyandTourism,ShaaniNoralUiversityXi'anOl19,aani,China;3.Collgeof GeographyandTourism,ChongqingKeyLaboratoryofGISApplication,ChongqingNormalUnversity,Chongqing447,Cina; 4.GuangxiYicheng BlueprintTechnologyCo.Ltd.,Nanning530o7,uangxi,China;5.SchoolofcivilEnginering,ian InstitutefTasprtatioEgig,Xi'n5,ani,na.anilateeter,Xi'a5aia)

Abstract: The Loess Plateau is one of the four major plateaus in China. It is the most concentrated and largest Loess area on earth, but fragile ecology, which feds $8 . 5 \%$ of China's population with $6 . 7 \%$ of the land. The longterm population and economic development pressure have caused severe regional ecosystem degradation. Since the implementation of the project of returning farmland to forest and grassland in 1999，the vegetation construction acceleration has led to significant improvements in the ecological environment. However, the manmade factors and the influence rules of vegetation cover changes on the Loess Plateau still lack several quantitative demonstrations.Therefore，strengthening the quantitative analysis of the human impact on the regional ecological environment will not only promote accurate ecological restoration,but also promotes the construction of human stability，harmony，and happy life,which has important theoretical and practical significance. Based on the MODIS-NDVI and MODIS-LST from 200l to 2018,as wel as various humanistic and social data,such as land use,transportation,and population,this paper constructs the Temperature Vegetation Dryness Index (TVDI) to reflect the soil moisture status of the Loess Plateau.The residual method is used to remove soil moisture to express the manmade influence of vegetation cover.The spatiotemporal evolution pattern of the man-made influence is analyzed with trend analysis and the Hurst index.We tend to explore the effect degree of various human factors,influence direction,and their temporal changes on vegetation coverage with geographic detectors and correlation analysis methods on the Loess Plateau. It is hoped to determine the manmade leading factors afecting the vegetation cover changes on the Loess Plateau,and provide a solid basis for the maintenance of the early ecological construction project and the future implementation of farmland to forest project,which willcontribute to the healthy and sustainable development of the ecological environment of the Loess Plateau. The results are as follows: (1） The anthropogenic influence of vegetation cover on the Loess Plateau from 2001 to 2018 has a trend of $0 . 3 6 \times 1 0 ^ { - 2 } \mathrm { ~ a ~ } ^ { - 1 }$ ，and the impact of human activities on vegetation cover was positive.(2)The future trend of human impact on vegetation cover will change from positive to negative on the Loess Plateau.It is worth noting that the positive effct of vegetation cover will weaken in the key implementation areas of returning farmland to forest. (3）)According to the results of correlation analysis and geographical detector,the main human factors affecting vegetation cover change include high-level tourist attractions,urban distribution,transportation,and land use.(4)The future implementation and maintenance of the returning farmland to forest project should pay attention to reinforce ecological construction at the same time as urban economic development,reduce the harm of trafic industry to the ecological environment, strengthen the development of green tourism and slow down the impact of human activities, such as land change.

Key words: human efects of vegetation cover； temperature vegetation dryness index； residual method;geode-tector; Loess Plateau