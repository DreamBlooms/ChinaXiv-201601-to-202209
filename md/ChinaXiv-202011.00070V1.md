# 基于SEBAL模型的疏勒河流域蒸散发估算与灌溉效率评价

宁亚洲¹，张福平1，冯起²，魏永芬³，李玲'，刘洁遥¹，曾攀儒（1陕西师范大学地理科学与旅游学院,陕西西安 710119;2中国科学院西北生态环境资源研究院,甘肃兰州 730000;3日本国立岐阜大学流域圈科学研究中心，日本 岐阜 501—1193)

摘要：我国西北干旱区内陆河流域水资源匮乏，水资源利用主要用于农业生产,准确估算内陆河流域蒸散发与农业灌溉效率，对研究内陆河流域气候变化和水资源合理利用具有重要作用。利用基于地表能量平衡方程的SEBAL模型,对2017—2018年疏勒河流域蒸散量进行定量估算与时空分布特征分析，并结合降水量与净灌溉水量数据，对疏勒河流域昌马灌区的年内灌溉水有效利用系数进行估算。结果表明：(1)疏勒河流域2017—2018年日均 $E T$ 呈单峰变化趋势，最大值为6月的 $5 . 0 3 \mathrm { m m }$ $\mathrm { d } ^ { - 1 }$ ，最小值为12月的 $0 . 5 5 \mathrm { \ m m ^ { \bullet } d ^ { - 1 } }$ ，并存在明显的空间分布差异。(2)疏勒河流域四季ET差异显著，夏季ET达到最高的 $2 0 1 . 8 3 \ : \mathrm { m m }$ ，春秋次之，冬季最低为 $5 3 . 9 2 \mathrm { m m }$ $E T$ 由东南向西北逐渐减小，流域上游ET明显高于中下游地区。(3）昌马灌区各灌溉时段不同的灌溉水量造成了各灌季蒸散量的差异，灌区 $E T$ 高值区主要分布在中部与东南部，低值区主要分布在西北部和灌区边缘。(4）昌马灌区年内灌溉水有效利用系数呈下降趋势，其中春灌、夏灌、秋灌和冬灌分别为0.76、0.71、0.69和0.55，年均灌溉水有效利用系数为0.67。

关键词：蒸散发；SEBAL模型；疏勒河流域；灌溉水有效利用系数；昌马灌区文章编号： $1 0 0 0 - 6 0 6 0 \lfloor 2 0 2 0 \rfloor 0 4 - 0 9 2 8 - 1 1 \lfloor 0 9 2 8 \sim 0 9 3 8 \rfloor$

蒸散发 $( E T )$ 是流域水文循环和水量平衡的主要环节，作为区域能量平衡的重要组成部分，它反映了在大气、土壤和植被变化的条件下，水和能量通量之间的相互作用[1-2]。因此,通过蒸散发的研究可深人了解水资源的形成过程与变化规律，对水资源评价与干旱监测具有重要作用[3-4],尤其是在西北干旱区，蒸散发的准确估算和监测对于区域水资源管理与利用意义重大。

蒸散量的传统测算方法有蒸渗仪法、波文比一能量平衡法、涡度相关仪法和闪烁通量仪法等[5-6],但均存在工作量大、数据获取的有限性以及不能以合理的成本对大尺度区域进行全面观测等局限性。不断发展的遥感技术手段为定量估算大尺度区域的地表蒸散量提供了方法，结合遥感数据和模型对区域蒸散发的反演与应用也成为国内外研究的重要方向。目前广泛使用的计算模型有陆面地表能量平衡方程（SEBAL）、地表能量平衡系统（SEBS）、基于地表温度和植被指数的梯形空间模型、双源能量平衡模型（TSEB）、METRIC方法等[7-"]。其中,SEBAL模型具有明确的物理基础，具有适应性广、精度高的特点，可用于大尺度区域的长时间地表蒸散量计算，因而在国内外得到了广泛的应用,如国外学者RAHIMI[12]、SANTOS[13]、ELNMER等[14]利用不同数据源结合SEBAL模型进行蒸散发反演，并在流域尺度上取得较好的反演结果；国内学者李宝富[15]、刘春雨[16]、周彦昭[17]、CHANG等[18]分别以中国西北干旱区为研究区，利用SEBAL模型进行蒸散发反演研究，结果表明SE-BAL模型能够有效实现对干旱区ET的模拟。因此，本文将采用SEBAL模型探究疏勒河流域的蒸散发特征。

国内外众多学者对灌溉效率的评价指标与内涵开展了很多研究，针对灌溉水有效利用系数也做了相应的探讨[19]。借助遥感手段可快速获得灌区蒸散发，将灌溉地消耗的水量作为灌溉水有效利用量并用于灌溉效率的估算，避免了传统灌溉效率测算的复杂性和存在的监测困难，为农业水资源高效利用提供了技术支撑[20]。国内外学者利用遥感蒸散发模型实现了对灌区的耗水分析与灌溉评价，结果表明基于遥感蒸散发的灌溉水利用效率评价方法可快速准确的实现灌溉效率评价，具有较强的可操作性[2I-23]。疏勒河流域内水资源匮乏，主要存在有限的水资源与急剧增加的人口、土地以及与流域内农业生态用水的矛盾[24-25],使得流域内水资源的合理配置显得尤为重要。农业用水约占疏勒河流域每年水资源量的 $89 \%$ ,用水方式主要依赖于水利工程的灌溉[26],对流域内农业用水效率的快速准确评价与提高也显得尤为迫切。因此明确流域实际蒸散发的时空格局和灌溉用水效率，对于该区水资源可持续利用具有重要作用。

目前对疏勒河流域蒸散发研究主要为利用传统方法的测定和基于遥感模型的短时间尺度反演[27-28],对疏勒河灌区研究集中在灌溉制度和灌溉技术等方面[29-31],鲜有对年内蒸散发的变化特征以及对灌区灌溉效率在不同灌溉季节的分析评价研究。本文利用MODIS数据和气象观测数据，采用SEBAL模型定量估算了疏勒河流域2017一2018年内的地表蒸散发，明确疏勒河流域年度ET变化特征。结合流域昌马灌区各灌溉季节的灌溉水量数据，对昌马灌区年内灌溉水有效利用系数进行了估算，以便更为真实地反映区域内实际的灌溉效率，为疏勒河流域水资源管理和分配等提供参考。

# 1数据与方法

# 1. 1 研究区概况

疏勒河流域地处我国西北干旱区，介于 $3 8 ^ { \circ } 0 0 ^ { \prime }$ $\sim 4 2 ^ { \circ } 4 8 ^ { \prime } \mathrm { ~ N } , 9 2 ^ { \circ } 1 1 ^ { \prime } \sim 9 8 ^ { \circ } 3 0 ^ { \prime } \mathrm { ~ E ~ }$ 之间。流域面积约为1. $2 5 \times 1 0 ^ { 5 } ~ \mathrm { k m } ^ { 2 }$ ，是河西走廊三大内陆河流域之一。疏勒河流域上游为高海拔山区，发育有典型大陆性冰川,并分布有多年冻土;流域中下游地势低平，荒漠分布广泛，土地沙化严重[32]。疏勒河流域内土地利用类型主要为低覆盖度草地、沙地和荒漠，植被分布稀少，生态环境脆弱。疏勒河流域属典型的干旱荒漠性气候，具有降水稀少、蒸发强烈的气候特点。疏勒河流域年均降雨量低于 $6 0 ~ \mathrm { m m }$ ，多年平均气温 $6 . 9 \sim 8 . 8 { \ } ^ { \circ } \mathrm { C }$ ,年蒸发量最高可达 $3 ~ 0 0 0 ~ \mathrm { { m m } }$ ，属于严重干旱地区[33]。疏勒河流域内辖昌马、双塔、花海三大灌区，疏勒河灌区历经多年的水利建设与生态保护综合规划项目的实施，灌溉效率显著提升，并被指定为甘肃省灌溉用水有效利用的样地灌溉区[30]

# 1.2 数据来源

研究所用数据主要有遥感数据、DEM数据、气象数据、土地利用覆被数据和灌溉统计数据。ET反演模型输入的各地表参数由美国NASA网站(https://ladsweb.nascom.nasa.gov/search/)中的 MO-DIS系列产品获得。本文根据晴天条件和云量、影像质量选择疏勒河流域2017年3月 $\sim 2 0 1 8$ 年2月对应的MODIS遥感影像。气象数据来源于中国气象科学数据共享服务网(http://cdc.cma gov.cn/home.do)，选用卫星过境时对应地面观测数据，包括气温、风速、相对湿度、气压等地表常规气象数据。DEM数据为空间分辨率为 $3 0 \mathrm { ~ m ~ }$ 的ASTERGDEMV2产品,来源于地理空间数据云(http://www.gscloud.$\mathrm { c n / }$ )。土地利用覆被数据来源于中国科学院资源环境科学数据中心(http://www.resdc.cn/)。用于计算灌溉效率的灌区灌溉数据来源于甘肃省疏勒河流域水资源管理局(http://slt.gansu.gov.cn/slhglj/）中提供的灌溉管理数据。

![](images/36f35734de6a82b64fc35aa47a99c7acefd48674a9c0d724557562b48162d170.jpg)  
图1疏勒河流域土地利用及昌马灌区示意图 Fig.1Land use of Shule River Basin and the location of Changma irrigated area

# 1.3SEBAL模型计算原理

SEBAL模型是基于遥感的陆面能量平衡模型，通过遥感数据与气象参数对各能量分量进行估算，得到区域的实际蒸散发[34]。区域的陆面能量平衡方程为：

$$
\lambda E T { = } R _ { n } - G - H
$$

式中： $\lambda E T$ 是潜热通量 $\left( \mathbb { W } \cdot \mathbf { m } ^ { - 2 } \right)$ ； ${ \cal R } _ { n }$ 是净辐射通量 $\mathrm { W } \cdot \mathrm { m } ^ { - 2 } .$ ）； $G$ 是土壤热通量（ $\mathrm { W } \cdot \mathrm { m } ^ { - 2 }$ ； $H$ 是感热通量 $\left( \mathbb { W } \cdot \mathbf { m } ^ { - 2 } \right)$ $\lambda$ 是潜热蒸发系数 $\left( \mathbb { W } \cdot \mathbf { m } ^ { - 2 } \bullet \mathbf { m } \mathbf { m } ^ { - 1 } \right)$ ）

# 1.3.1 地表净辐射通量 $\pmb { R _ { n } }$

$$
R _ { n } = ( 1 - \alpha ) R _ { s } + R _ { L } - R _ { g } - ( 1 - \varepsilon ) R _ { L }
$$

式中： $\scriptstyle a$ 是地表反照率; $R _ { s }$ 是太阳短波总辐射; $R _ { \ L }$ 是大气长波辐射； $R _ { g }$ 是地面长波辐射； $\boldsymbol { \varepsilon }$ 是地表比辐射率。

# 1.3.2土壤热通量 $G$

$$
G = T _ { s } \times R _ { n } \ : / \frac { \biggl [ \alpha \times \Bigl ( 0 . 0 0 3 ~ 8 \alpha + 0 . 0 0 7 ~ 4 \alpha ^ { 2 } \Bigr ) \times \biggr ] } { \biggl [ \left( 1 - 0 . 9 8 \times N D V I ^ { 4 } \right) }
$$

式中： $T _ { s }$ 为地表温度； $N D W$ 为归一化植被指数。

# 1.3.3 感热通量 $\pmb { H }$

$$
H = \frac { \rho _ { _ { a i r } } C _ { p } d T } { r _ { _ { a h } } }
$$

式中： $\rho _ { a i r }$ 是空气密度 $\left( \mathrm { k g } \cdot \mathrm { m } ^ { - 3 } \right)$ ； $C _ { p }$ 是空气定压比热容（取 $1 ~ 0 0 4 ~ \mathrm { J } \cdot \mathrm { k g } ^ { - 1 } \cdot \mathrm { K } ^ { - 1 } \rangle$ ； $d T$ 是不同高度之间的温度差; $r _ { a h }$ 是空气动力学阻抗 $\left( \mathbf { s } \cdot \mathbf { m } ^ { - 1 } \right)$ 。其中 $r _ { a h }$ 和 $d T$ 通过选取冷热像元进行循环迭代计算取得。

1.3.4蒸发比与日蒸散发由于卫星过境所观测的为地面瞬时数据，通过蒸发比不变的方法将瞬时蒸散量扩展到日蒸散量[35],计算公式如下：

$$
\varphi = { \frac { \lambda E T } { R _ { n } - G } }
$$

$$
E T _ { 2 4 } = \frac { R _ { n 2 4 } \times \varphi \times 8 6 4 0 0 } { \left[ 2 . 5 0 1 - 0 . 0 0 2 3 6 1 \times \left( T _ { s } - 2 7 3 . 1 5 \right) \right] \times 1 0 ^ { 6 } }
$$

式中： $\varphi$ 为蒸发比; $E T _ { 2 4 }$ 为日蒸散量; ${ \cal R } _ { n 2 4 }$ 为日净辐射通量 $\left( \mathbb { W } \cdot \mathbf { m } ^ { - 2 } \right)$ ； $T _ { s }$ 为地表温度(K)。

# 1.4蒸散发时间尺度扩展及验证

1.4.1 参考作物蒸散量 ${ E T _ { 0 } }$ 本文基于地面气象观测数据，利用联合国粮农组织(FAO)推荐的Pen-man-Monteith公式计算得到参考作物蒸散量，对模拟 $E T$ 进行长时间的尺度扩展，计算公式如下：

$$
E T _ { 0 } = \frac { 0 . 4 0 8 \triangle \big ( R _ { n } - G \big ) + \gamma \frac { 9 0 0 } { T + 2 7 3 } u _ { 2 } \big ( e _ { s } - e _ { a } \big ) } { \triangle + \gamma \big ( 1 + 0 . 3 4 u _ { 2 } \big ) }
$$

式中： $\mathbf { \nabla } _ { E T _ { 0 } }$ 为参考作物蒸散量 ${ \bf \chi } _ { \mathrm { m m } } \cdot \mathrm { d } ^ { - 1 } ,$ ； $\bigtriangleup$ 为饱和水气压曲线斜率 $\left( \mathrm { k P a } \cdot \mathrm { ^ { \circ } C ^ { - 1 } } \right)$ ; $R _ { n }$ 为地表净辐射（MJ·$\mathbf { m } ^ { - 2 } { \boldsymbol { \cdot } } \mathbf { d } ^ { - 1 } .$ ； $G$ 为土壤热通量 $( \mathrm { M J } \cdot \mathrm { m } ^ { - 2 } \cdot \mathrm { d } ^ { - 1 } )$ ; $\gamma$ 为干湿表常数 $\left( \mathbf { k } \mathbf { P a } \cdot \mathbf { \mathcal { C } } ^ { - 1 } \right)$ ; $T$ 为日平均气温 $( \mathcal { C } )$ ; $u _ { 2 }$ 为 $2 \mathrm { m }$ 高处风速 $\left( \mathbf { m } \cdot \mathbf { s } ^ { - 1 } \right)$ ; $\boldsymbol { e } _ { s }$ 为饱和水气压 $\left( \mathrm { { k P a } } \right)$ ； $\boldsymbol { e } _ { a _ { } }$ 为实际水气压 $\left( \mathrm { { k P a } } \right)$ 。

1.4.2月蒸散量 结合SEBAL模型和参考作物蒸散量计算方法对月实际蒸散量进行计算：

$$
E T _ { \mathrm { { c } } } { = } E T _ { \mathrm { { 0 } } } F { \times } E T _ { \mathrm { { 0 } } }
$$

式中： $E T _ { c }$ 为实际蒸散量 $( \mathbf { \bar { \rho } } _ { \mathrm { m m } } )$ ； $E T _ { 0 } F$ 为参考蒸散比，由卫星过境天数SEBAL模型计算所得实际蒸散量和参考蒸散量之比得到，非卫星过境天数的$E T _ { 0 } F$ 可由时间序列插值方法得到。在获得连续日实际蒸散量后，进行累加即可得到相应月蒸散量。

1.4.3精度评价本文利用均方根误差(RMSE）、决定系数 $\left( R ^ { 2 } \right)$ 和相对误差(MRE)等定量指标对模型反演进行精度验证。计算公式分别为：

$$
R M S E = \sqrt { \frac { \sum _ { i = 1 } ^ { n } \bigl ( E T _ { { \scriptscriptstyle m } _ { - } i } - E T _ { { \scriptscriptstyle S E B A L } _ { - } i } \bigr ) ^ { 2 } } { n } }
$$

$$
R ^ { 2 } = 1 - \frac { \sum _ { i = 1 } ^ { n } \bigl ( E T _ { m _ { - } i } - E T _ { _ { S E B A L _ { - } i } } \bigr ) ^ { 2 } } { \sum _ { i = 1 } ^ { n } \bigl ( E T _ { m _ { - } i } \bigr ) ^ { 2 } }
$$

$$
M R E = \frac { \sum _ { i = 1 } ^ { n } \bigl ( | E T _ { m _ { - } i } - E T _ { _ { S E B A L _ { - } } i } | / E T _ { m _ { - } i } \bigr ) } { n } \times 1 0 0 \%
$$

式中： $n$ 为观测样本个数; $E T _ { m \_ i }$ 和 $E T _ { S E B A L \_ i }$ 分别为 用于验证计算所得 $E T$ 和SEBAL模型计算所得 $E T$

# 1.5水量平衡及灌溉水有效利用系数的计算

本文通过对疏勒河流域昌马灌区ET的估算，结合灌区实际灌溉数据和降水数据，进而估算得到灌区在不同灌溉时段的灌溉水有效利用系数。在土壤水量平衡的基础上，规避了由于水势梯度作用引起的水分渗漏和补给量，针对灌区建立如下水量平衡方程[36]：

$$
\begin{array} { r } { \Delta w = \big ( P _ { _ n } + P _ { _ i } + I \big ) - \big ( E T _ { _ n } + E T _ { _ i } + R \big ) } \end{array}
$$

式中： $\Delta w$ 为时段内土壤含水量的变化量 $\left( \mathbf { m } ^ { 3 } \right)$ ; $\boldsymbol { P } _ { n }$ 、 $P _ { i }$ 分别为时段内非灌溉地、灌溉地降水量 $( \mathrm { m } ^ { 3 } ) ; I$ 为 时段内的净灌溉量 $\left( \mathbf { m } ^ { 3 } \right)$ ; $E T _ { n }$ 、 $E T _ { i }$ 分别为时段内非 灌溉地、灌溉地蒸发量 $( \mathbf { m } ^ { 3 } )$ ； $R$ 为时段内灌区地表 径流量 $\left( \mathbf { m } ^ { 3 } \right)$ ○

昌马灌区地处干旱的平原区域，由于年内降水量小，因此忽略降水所产生的地表径流；研究时段内土壤层含水量变化较小，本研究中不予考虑，则可对灌区内的水量平衡方程进行简化，如公式（13）所示。通常将灌溉地消耗的灌溉水量作为灌溉水的有效利用量，则将灌溉水有效利用量$\left( E T _ { i } - P _ { i } \right)$ 与灌区净灌溉量 $I$ 的比值定义为灌溉水有效利用系数 $\eta$ ，见公式（14）。

$$
I { = } \left( E T _ { { i } } { - } P _ { { i } } \right) + \left( E T _ { { n } } { - } P _ { { n } } \right)
$$

$$
\eta = \left( E T _ { \mathrm { { i } } } - P _ { \mathrm { { i } } } \right) / { \cal I }
$$

式中：（ $E T _ { i } - P _ { i }$ ）为灌溉地消耗的灌溉水量 $( \mathbf { m } ^ { 3 } )$ ;$\left( E T _ { n } - P _ { n } \right)$ 非灌溉地消耗的灌溉水量 $( \mathbf { m } ^ { 3 } ) ; \eta$ 为灌溉水有效利用系数。

# 2 结果分析

# 2.1 模型验证

本文采用两种方法验证ET模拟结果。第一种是采用流域内4个气象站(敦煌站、玉门站、马鬃山站、瓜州站)的气象观测资料，利用FAOP-M公式计算得到各站点 $4 \sim 1 0$ 月的日参考作物蒸散量，结合生长季作物系数所得作物实际蒸散量对ET模拟值进行验证[37]。第二种方法是利用蒸发皿系数对流域内各站点蒸发皿实测值进行折算[38],进而与ET模拟结果进行对比验证。

上述两种方法的验证结果分别如图2a、2b所示。在提取站点反演的蒸散量时，提取以站点为中心的 $3 \times 3$ 个像元范围内的平均值用于模型验证。从图2可知，两种验证方法的 $R ^ { 2 }$ 均大于0.8,表明模型反演值与P-M计算值、实测值之间具有良好的相关关系和变化趋势；两种方法的均方根误差相对较小，且 $0 . 4 9 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 表明P-M计算值与反演值更为接近；两种方法的相对误差均为 $8 . 4 \%$ ,表明模拟值接近实际情况，模拟结果可信。上述验证方法的结果表明，SEBAL模型能够有效模拟疏勒河流域的实际蒸散发情况。

# 2.2 蒸散发模拟结果

2.2.1日蒸散量变化特征图3分别为模拟得到的疏勒河流域2017年3月 $\sim 2 0 1 8$ 年2的日蒸散量空间分布(图中均以儒略日DOY表示日期)，(a）～(1)分别代表日序数为DOY009、DOY049、DOY089、DOY113、DOY129、DOY161、DOY193、DOY225、DOY265、DOY289、DOY305、DOY337的日蒸散空间分布。

图3中，模拟得到的1月和2月的日蒸散量低，分别为 $0 . 5 8 \ \mathrm { m m \cdot d ^ { - 1 } } , 1 . 2 1 \ \mathrm { m m \cdot d ^ { - 1 } }$ ，区域整体蒸散量以低值为主； $3 \sim 5$ 月的日蒸散量逐渐增大，分别达到 $3 . \ 0 0 \ \mathrm { m m \cdot d ^ { - 1 } } , 3 . \ 5 2 \ \mathrm { m m \cdot d ^ { - 1 } } , 4 . \ 4 2 \ \mathrm { m m \cdot d ^ { - 1 } }$ ，上游区域蒸散量增大明显，高值区即红色区域明显增多；6月的日蒸散量达到最大的 $5 . 0 3 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ ,蒸散量高值区主要集中于上游地区，且中下游增幅较大； $7 \sim 1 0$ 月的日均蒸散量开始下降，但7、8月的日均蒸散量仍然保持一个较高的蒸发水平，分别为$4 . 8 5 \ \mathrm { m m \cdot d ^ { - 1 } } \ . 4 . 6 2 \ \mathrm { m m \cdot d ^ { - 1 } }$ ，其中9、10月的日均蒸散量下降明显，日均蒸散量分别为 $2 . 7 0 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ ）$1 . 6 2 \ : \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ ,其中上游地区蒸散高值区降幅较大，区域内蒸散较大区域面积明显缩小; $1 1 \sim 1 2$ 月的日蒸散量到达年内最低值，分别为 $1 . \ 1 \ \mathrm { m m \cdot d } ^ { - 1 } \setminus 0 . \ 5 5$ $\mathrm { m } \mathrm { m } \cdot \mathrm { d } ^ { - 1 }$ ,区域内大部分蒸散量主要分布在 $0 \sim 1$ $\mathrm { m m \cdot d ^ { - 1 } }$ 。总体来说,研究区年内日均蒸散量呈先增后减的变化趋势，最大值出现在6月中旬，最小值出现在12月下旬，年内日均蒸散量在 $0 . \ 5 5 \sim 5 . \ 0 3$ $\mathrm { m m \cdot d ^ { - 1 } }$ 内变化,并存在明显的空间分布差异。

![](images/5109ddceb7adbc00f03bee43f4d0ff05c1507f999164b7dc0e46628190fe9b15.jpg)  
图2ET模拟结果的对比验证  
Fig.2Comparison and validation for simulated $E T$ results

![](images/d3a6c32c237219a817fc3f9d2de5d0b7526f6ce111720cbe24d18e95be9d8c6b.jpg)  
图3研究区日蒸散量空间分布图  
Fig.3Distribution of daily evapotranspiration from 2O17 to 2O18 in the study area

2.2.2季节蒸散量特征根据对2017—2018年的年内各月蒸散量估算，获得年内四季的蒸散量如图4所示，图中(a）\~（d)分别代表春季(3\~5月）夏季（ $6 \sim 8$ 月）秋季( $9 \sim 1 1$ 月）冬季( $1 2 \sim$ 次年2月）四季蒸散空间分布状况。

从图4可得，疏勒河流域不同季节蒸散量差异显著，其空间分布特征较为相似，整体表现为从东南部向西北部逐渐减少。春季蒸散量空间差异较为明显，上游蒸散量高于中下游地区，平均蒸散量为 $1 6 5 . 5 1 ~ \mathrm { m m }$ 。这是由于春季太阳辐射和气温的逐渐加强，植被在生长初期的蒸腾作用有所增强。进入夏季后，由于辐射和温度达到年内最大，使得夏季蒸散量达到年内最大的 $2 0 1 . 8 3 ~ \mathrm { m m }$ ，从而使得蒸散量的空间差异最为显著。秋季气温、降水量和太阳辐射的逐渐减少，使得蒸散量相对夏季呈现明显的下降，流域内各区域的蒸散量差距有所减小，且中下游地区的蒸散量主要处于 $2 0 0 \mathrm { m m }$ 以下，使得秋季平均蒸散量减少至 $1 0 0 . 5 1 \mathrm { m m }$ 。冬季平均蒸散量为四季内最小，仅为 $5 3 . 9 2 \mathrm { m m }$ ，冬季蒸散量的空间差异最小，仅上游部分山区蒸散量稍高，其余区域均为小于 $5 0 ~ \mathrm { m m }$ 的低值区即蓝色部分。因此，年内季节蒸散量变化为：夏季 $>$ 春季 $>$ 秋季 $>$ 冬季。

结合图5的研究区土地利用状况可以看出，四季的蒸散量高值区域主要集中在上游地区，分布在紧邻山区的草地、林地、河流沿岸和部分水体区域;中下游地区蒸散量处于整个流域的较低水平，蒸散主要集中于中下游地区中的低覆盖度草地，蒸散量较小；流域西部地区是整个流域蒸散量最小的区域，主要与中游地区大面积分布的沙地、戈壁和未利用土地相关，具有极低的蒸散量，则研究区蒸散量大小在空间上呈现上游明显大于中下游地区。

# 2.3水量平衡及灌溉水有效利用系数计算结果

本文对疏勒河流域内面积最大的昌马灌区采用遥感蒸散发模型，进行灌溉水有效利用系数估算与灌溉效率评价。昌马灌区位于流域中游地区，主要分布有耕地和部分林地(图1)，其年内灌溉时段划分为：春灌 $( 3 \sim 4$ 月）夏灌 $( 5 \sim 7$ 月）秋灌( $8 \sim 9$ 月）、冬灌( $1 0 \sim 1 1$ 月）。昌马灌区春灌、夏灌、秋灌和冬灌的ET结果如图5中（a）～（d）所示。灌区中由于各灌季的灌溉用水量和种植情况的不同，使得各灌季的蒸散量存在明显的时空差异，其中 $5 \sim 7$ 月的夏灌阶段ET最大，其次为秋灌和春灌阶段，冬灌阶段的ET最小；从ET空间分布可以看出，不同灌溉时段内的ET高值区主要分布在中部与东南部，低值区主要分布在边缘区域

![](images/1c2188335efb014d0093e8f1e5f5294413f1e0009e36d3846fcae6281680efd3.jpg)  
Fig.4Distribution of seasonal evapotranspiration from 2O17 to 2O18 in the study area

![](images/8a2a111defc7f37046cc3924843867c082554e0281120da3e8d6a60649f1731a.jpg)  
图4研究区四季蒸散量空间分布图  
图5昌马灌区各灌季蒸散量分布图  
Fig.5Distribution of seasonal evapotranspiration in Changma irrigated area

结合实际灌区内降水数据、灌溉面积和净灌溉量数据计算水量平衡所需分量，其中灌区 $3 \sim 1 1$ 月ET及降水量变化如图6所示。ET变化呈先增后减的变化趋势， $3 \sim 6$ 月逐渐增大，并在6月达到最大的$1 2 9 ~ \mathrm { m m } ; 6 \sim 1 1$ 月逐渐下降，并在11月达到最小的$2 0 \mathrm { m m }$ 。 $3 \sim 1 1$ 月的各月降水量变化幅度较大，其中6、7月降水量最高，均大于 $3 0 \ \mathrm { m m } ; 4$ 月和8月的降水量较大，均在 $1 5 \mathrm { m m }$ 左右;其余月份的降水量均处于较低水平,均小于 $7 \mathrm { m m }$ 。上述的各月蒸散量和降水量作为水量平衡的重要分量，将对不同灌季的灌溉效率产生较大的影响。

通过对灌溉水有效利用量的计算，结合各灌季

![](images/2911b733eb9dd627b1589c16aaba7202560f39d696518c554572c0028b0300ef.jpg)  
图6昌马灌区月蒸散量与月降水量变化 Fig.6Variation of monthly evapotranspiration and precipitation in Changma irrigated area   
图7昌马灌区各灌季参数变化 Fig.7Variation of monthly parameters in Changma irrigated area

净灌溉量 / 200 灌溉水有效利用量 0.9 30101401010 一灌溉水有效利用系数 0.8 706 0.5 860 0.4 0.3 4020 2 0 0.0 春灌 夏灌 秋灌 冬灌 灌季

的灌溉面积和净灌溉量，求得灌区内各灌季的灌溉水有效利用系数，结果如图7所示。计算所得的春灌、夏灌、秋灌和冬灌的灌溉水有效利用系数分别为0.76、0.71、0.69、0.55，年内平均灌溉水有效利用系数为0.67，其中冬灌的灌溉水有效利用系数低于年平均水平；灌溉水有效利用系数在年内呈逐渐减少的趋势，其中春灌的灌溉水有效利用系数最大，其次为夏灌和秋灌，冬灌最低。年内净灌溉量和灌溉水有效利用量差异显著，其中春灌用水量最小，夏灌最大，其次为秋灌和冬灌，这与年内不同季节的作物种植面积及作物生长阶段的需水量关系密切。

# 3讨论

# 3.1 蒸散发模型反演

本文利用MODIS遥感数据和SEBAL模型，对疏勒河流域2017一2018年内的蒸散量进行定量估算并分析其空间分布特征。结果表明，疏勒河流域年内日均蒸散量呈单峰变化趋势，并在 $0 . 5 5 \sim 5 . \ 0 3$ $\mathrm { m } \mathrm { m } \cdot \mathrm { d } ^ { - 1 }$ 内变化，四季中夏季的蒸散量最大，春秋次之，冬季最小。CHANG等[I8]利用SEBAL模型分别反演得到疏勒河上游6月的日蒸散量介于 $3 \sim 5$ $\mathrm { m } \mathrm { m } \cdot \mathrm { d } ^ { - 1 }$ ，周妍妍等[2]通过SEBAL模型反演得到疏勒河流域8月多年平均日蒸散量为 $0 \sim 8 . 5 2 \ \mathrm { m m }$ $\mathbf { d } ^ { - 1 }$ ，上述结论与本文所得相应时段结果相近，证明本文计算结果合理。年内蒸散量的变化由于气温、降水、太阳辐射、植被生长态势和土壤含水量等因素的共同影响，并表现出季节性变化。如夏季时段是植被生长旺季阶段，充足的水分和强辐射使得水体和植被的蒸发和蒸腾作用达到最强，而冬季蒸散由于气温和辐射低，降水少，地表植被和土壤水分蒸发量较小，造成冬季蒸散量低。

从反演结果上看，蒸散发的空间分布与土地覆被类型具有高度一致性。蒸散发高值区主要分布在疏勒河上游地区高覆盖度草地以及水域周围等区域，这是由于上游地区草地有来自于山区季节性降水的水源补充，土壤湿润，利于蒸发。疏勒河流域中下游的沙地与荒漠分布广泛，并有小面积绿洲交错分布，为流域ET低值的主要分布区域。这是由于荒漠区草地和林地的地下水资源极其稀缺，补给水源主要依赖于地下水和降水的补给，加之沙地、戈壁区域水资源匮乏、地表裸露，共同导致了该区域的蒸散量低。这与金学杰等3对干旱区黑河流域的蒸散发估算结果中水体和草地蒸散发量大，而沙地和裸地的蒸散量最小的结论一致。

# 3.2灌溉水有效利用系数计算

本文利用遥感蒸散模型对疏勒河流域昌马灌区的灌溉水有效利用系数进行了估算，用于计算的降水量、实际灌溉面积和净灌溉量均为获取的实测统计数据，因此所得灌溉水有效利用系数具有一定的精度。本文计算得到2017年平均灌溉水有效利用系数为0.67，不同灌溉时段的灌溉水有效利用系数存在一定差异。春灌由于处于作物生长初期，其灌溉用水量较小，蒸发量较大，使得灌溉水有效利用系数较大；夏灌和秋灌的灌溉水有效利用系数相对减少，这是由于夏季和秋季阶段为满足作物生长旺盛期的需水量，净灌溉量达到最大，但过度灌溉会导致灌溉水在运输过程中经过渠道及田间的水量损失和渗漏，且该时段的降水量较大，从而使得该阶段的灌溉水有效利用系数下降，因此可通过减少灌溉过程中水量输送的损失来提高灌溉效率；冬灌的灌溉水有效利用系数相对较低，主要是因为灌区内 $1 0 \sim 1 1$ 月处于作物生长末期，灌溉地的蒸散量迅速减少，使得该阶段灌溉水有效利用系数有所下降。

灌溉水有效利用系数同时受到净灌溉水量、降水量和ET的影响，也与灌溉技术和输水系统相关。因此可根据不同季节的蒸散特征和灌溉水利用情况，采取不同的节水灌溉措施和合理的灌溉水量来提高作物的灌溉效率。ET作为灌溉耗水和灌溉水有效利用系数计算的重要组成，ET的准确估算对认识作物蒸散特征和耗水情况具有重要影响。因此，在今后的研究中应根据实际情况改善模型参数，同时结合高分辨率影像将有效提高流域及灌区ET的反演精度，进而更加准确估算灌区的灌溉水利用情况。

# 4结论

（1）疏勒河流域2017一2018年年内平均日蒸散量总体呈单峰变化趋势，年内日均蒸散量在 $0 . 5 5 \sim 5 . 0 3 ~ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 内波动变化。日蒸散量从3月开始波动上升，并在6月达到最大值 $5 . 0 3 ~ \mathrm { m m }$ $\mathbf { d } ^ { - 1 }$ ，之后的7月 $\sim$ 次年的2月的日蒸散量呈波动下降趋势，其中日蒸散量最小值 $0 . 5 5 \mathrm { \ m m ^ { \bullet } d ^ { - 1 } }$ 出现在12月至次年1月之间。

（2）疏勒河流域四季 $E T$ 变化显著，四季 $E T$ 值从大到小排列为：夏季 $( 2 0 1 . 8 3 \mathrm { m m } ) >$ 春季(165.51$\mathbf { m m } ) >$ 秋季 $\mathrm { 1 0 0 . 5 1 \ m m } ) >$ 冬季 $\left( 5 3 . 9 2 \mathrm { m m } \right)$ 。四季 $E T$ 的时空分布异质性显著，时间上，夏季和秋季的ET差异较春季和冬季明显；空间上，疏勒河流域ET由东南向西北逐渐减小，上游地区 $E T$ 明显高于中下游地区，蒸散发的空间分布与土地覆被类型具有高度一致性。

(3）疏勒河流域昌马灌区由于各灌季的灌溉用水量和种植情况的不同，不同灌溉时段的灌溉地蒸散量存在明显的空间分布差异与空间变化，灌区内各灌季的ET高值区主要分布在中部与东南部，低值区主要分布在西北部和灌区边缘。

（4）根据水量平衡对昌马灌区灌溉水有效利用系数进行估算，降水量与蒸散量在灌季内呈先增后减的波动变化。昌马灌区年内灌溉水有效利用系数呈下降趋势，计算所得的春灌、夏灌、秋灌和冬灌各灌季的灌溉水有效利用系数分别为0.76、0.71、0.69、0.55，年内平均灌溉水有效利用系数为0.67。

# 参考文献(References)

[1］ZHAO Lingling,XIA Jun,XU Chongyu,et al. Evapotranspiration estimation methods in hydrological models［J]. Journal of Geographical Sciences,2013,23(2):359-369.   
[2] ZENG Z,WANG T,ZHOUF,et al.A worldwide analysis of spatiotemporal changes in water balance-based evapotranspiration from 1982 to 2009[J].Journal of Geophysical Research: Atmospheres,2014,119(3):1186-1202.   
[3] 高瑜莲，柳锦宝，柳维扬，等.近14a新疆南疆绿洲地区地表 蒸散与干旱的时空变化特征研究[J].干旱区地理,2019,42 (4）:830-837.[GAO Yulian,LIU Jinbao,LIU Weiyang,et al. Spatial-temporal variation characteristics of surface evapotranspiration and drought at the oasis of the southern Xinjiang in recent 14 years[J].Arid Land Geography,2019,42（4）:830 - 837.]   
[4] 钟巧,焦黎,李稚,等.博斯腾湖流域潜在蒸散发时空演变及归 因分析[J].干旱区地理，2019,42(1)：103-112.[ZHONG Qiao,JIAO Li,LI Zhi,et al. Spatial and temporal changes of potential evapotranspiration and its attribution in the Bosten Lake Basin[J].Arid Land Geography,2019,42(1):103-112.]   
[5] YASSINMA,ALAZBAA,MATTARMA.Artificial neural networks versus gene expression programming for estimating reference evapotranspiration in arid climate[J].Agricultural Water Management,2016,163(1):110-124.

# 干旱区地理

[6］姜艳阳,王文,周正昊.MODIS MOD16蒸散发产品在中国流 域的质量评估[J].自然资源学报,2017,32(3):517-528.[JIANG Yanyang, WANG Wen, ZHOU Zhenghao. Evaluation of MODIS MOD16 evapotranspiration product in Chinese river basins[J].Journal of Natural Resources,2017,32(3):517-528.]   
[7]杨秀芹,王国杰,潘欣,等.基于GLEAM遥感模型的中国 1980—2011年地表蒸散发时空变化[J].农业工程学报,2015, 31（21） :140 - 149.[YANG Xiuqin,WANG Guojie,PAN Xin, et al.Spatial-temporal variability of terrestrial evapotranspiration in China from 1980 to 2011 based on GLEAM data［J]. Transactions of the Chinese Society of Agricultural Engineering, 2015,31(21):140-149.]   
[8］张晓玉,范亚云,热孜宛古丽·麦麦提依明,等.基于SEBS模型 的干旱区流域蒸散发估算探究[J].干旱区地理,2018,41(3)： 76 - 85.[ZHANG Xiaoyu,FAN Yayun,MAIMAITIYIMING Reziwanguli,et al. Evapotranspiration estimation of watershed in arid area based on SEBS model[J].Arid Land Geography, 2018,41(3):76- 85.]   
[9]田国珍,武永利,梁亚春,等.基于蒸散发的干旱监测及时效性 分析[J].干旱区地理,2016,39（4):721－729.[TIAN GuoZhen,WU Yongli,LIANG Yachun,et al. Drought monitoring and timeliness based on evapotranspiration model[J].Arid Land Geography,2016,39(4):721- 729.]   
[10] LONG D,SINGH V P. A two-source trapezoid model for evapotranspiration（TTME） from satellite imagery[J]. Remote Sensing of Environment,2012,121:370 - 388.   
[11］张圣微,张鹏,张睿,等.科尔沁沙地典型区生长季蒸散发估算 及其变化特征[J].水科学进展，2018,29(6)：12－ 22. [ZHANG Shengwei,ZHANG Peng,ZHANG Rui,et al. Estimation of growing season evapotranspiration and its variation in a typical area of Horqin Sandy Land[J].Advances in Water Science,2018,29(6):12- 22.]   
[12]RAHIMI S,GHOLAMI SEFIDKOUHI MA,RAEINI-SARJAZ M,et al. Estimation of actual evapotranspiration by using MODIS images（a case study:Tajan catchment）[J].Archives of Agronomy and Soil Science,2015,61(5):695- 709.   
[13] SANTOS C AG,SILVA R M D,SILVA A M,et al. Estimation of evapotranspiration for different land covers in a Brazilian semi-arid region:A case study of the Brigida River Basin,Brazil [J]. Journal of South American Earth Sciences,2017,74: 54 66.   
[14]ELNMER A,KHADR M, KANAE S,et al. Mapping daily and seasonally evapotranspiration using remote sensing techniques over the Nile delta[J].Agricultural Water Management,2019, 213:682 - 692.   
[15］李宝富,陈亚宁,李卫红,等.基于遥感和 SEBAL模型的塔里 木河干流区蒸散发估算[J].地理学报，2011,66(9)：1230- 1238.[LI Baofu,CHEN Yaning,LI Weihong,et al. Remote sensing and the SEBAL model for estimating evapotranspiration in the Tarim River[J].Acta Geographica Sinica,2011,66（9）： 1230 - 1238.]   
[16］刘春雨,赵军,刘英英,等.石羊河流域蒸散发量遥感估算及时 空格局分析[J].国土资源遥感,2011,23(3):117-122.[LIU Chunyu, ZHAO Jun,LIU Yingying,et al. Remote sensing estimation of evapotranspiration quantity and analysis of space-time structure over Shiyang River Basin [J].Remote Sensing for Land & Resources,2011,23(3):117-122.]   
[17］周彦昭,周剑,李妍,等.利用SEBAL和改进的 SEBAL模型估 算黑河中游戈壁、绿洲的蒸散发[J].冰川冻土,2014,36(6): 1526-1537.[ZHOU Yanzhao,ZHOU Jian,LI Yan,etal.Simulating the evapotranspiration with SEBAL and Modified SEBAL (M-SEBAL）models over the desert and oasis of the middle reaches of the Heihe River[J]. Journal of Glaciology and Geocryology,2014,36(6):1526-1537.]   
[18] CHANG Y,DING Y,ZHAO Q,et al. Remote estimation of terrestrial evapotranspiration by Landsat 5 TM and the SEBAL model in cold and high-altitude regions:A case study of the upper reach of the Shule River Basin,China[J].Hydrological Processes,2016,31(3):514-524.   
[19］崔远来,熊佳.灌溉水利用效率指标研究进展[J].水科学进 展,2009,20(4):590-598.[CUI Yuanlai,XIONG Jia.Advances in assessment indicators of irigation water use eficiency[J]. Advances in Water Science,2009,20(4):590- 598.]   
[20］尚松浩,蒋磊,杨雨亭.基于遥感的农业用水效率评价方法研 究进展[J].农业机械学报,2015,46(10)：86-97.[SHANG Songhao,JIANG Lei,YANG Yuting.Review of remote sensing-based assessment method for irrigation and crop water use effciency[J].Transactions of the Chinese Society for Agricultural Machinery,2015,46(10):86-97.]   
[21］周剑,吴雪娇,李红星,等.改进SEBS 模型评价黑河中游灌溉 水资源利用效率[J].水利学报，2014,45(12)：1387－1398. [ZHOU Jian,WU Xuejiao,LI Hongxing,et al. Improved SEBS model for evaluating irrigation water use eficiency in the middle reaches of the Heihe River[J]. Journal of Hydraulic Engineering,2014,45(12):1387-1398.]   
[22]YANG Y,SHANG S,JIANG L. Remote sensing temporal and spatial patterns of evapotranspiration and the responses to water management in a large irigation district of north China[J].Agricultural and Forest Meteorology,2012,164:112-122.   
[23]LIAQATUW,CHOI M,AWANUK. Spatial-temporal distribution of actual evapotranspiration in the Indus Basin Irrigation System[J].Hydrological Processes,2015,29(11):2613- 2627.   
[24］常跟应,张文侠.基于生态文明的疏勒河流域大规模移民反思 [J].兰州大学学报（自然科学版）,2014,50(3):405－409. [CHANG Genying，ZHANG Wenxia.Ecological civilization-based rethinking of large-scale immigration and land development along Shule River［J]. Journal of Lanzhou University (Natural Sciences）,2014,50(3):405-409.]   
[25］孙栋元,胡想全,金彦兆,等.疏勒河中游绿洲天然植被生态需 水量估算与预测研究[J].干旱区地理,2016,39(1):154-161. [SUN Dongyuan,HU Xiangquan,JIN Yanzhao,et al. Prediction and evaluation of ecological water requirement of natural vegetation in the middle reach oasis of Shule River Basin［J].Arid Land Geography,2016,39(1):154-161.]

[26］刘建军.疏勒河灌区严格水资源管理促进水生态文明建设 [J].农业科技与信息,2018,1:47-49.[LIUJianjun.Strictwater resources management in Shule River irrigation area to promote the construction of water ecological civilization[J].Agricultural Science-Technology and Information,2018,1：47 - 49.]

[27］周妍妍,郭晓娟,郭建军,等.基于SEBAL模型的疏勒河流域 蒸散量时空动态[J].水土保持研究,2019,26(1)：168－177. [ZHOU Yanyan,GUO Xiaojuan,GUO Jianjun,et al. Spatiotemporal dynamics of evapotranspiration in Shule River Basin based on SEBAL model[J].Research of Soil and Water Conservation, 2019,26(1):168-177.]   
[28］吴锦奎,陈军武,吴灏,等.疏勒河上游高寒草甸蒸散对比研究 [J].地理科学,2013,33(1):97-103.[WU Jinkui,CHEN Junwu,WU Hao,et al. Comparative study of evapotranspiration in an alpine meadow in the upper reach of Shule River Basin[J]. Scientia Geographica Sinica,2013,33(1):97-103.]   
[29］蒋光昱,王忠静,尚松浩,等.基于观测与模拟结合的疏勒河流 域辣椒灌溉制度优化[J].农业工程学报,2018,34(增刊1)： 207- 213.[JIANG Guangyu,WANG Zhongjing,SHANG Songhao,et al. Irrigation optimization of pepper in Shule River Basin based on observation and simulation[J].Transactions of the Chinese Society of Agricultural Engineering,2018,34（Sup 1）: 207-213.]   
[30］曾国雄,杨占荣,张伟等.疏勒河流域高效灌溉系统集成技术 [J].水利规划与设计,2017,8:34－37.[ZENG Guoxiong, YANG Zhanrong,ZHANG Wei,et al. Integrated technology of high efficiency irrigation system in Shule River Basin[J].Water Resources Planning and Design,2017,8:34-37.]   
[31］张建新.基于WEAP模型的疏勒河流域昌马灌区节水灌溉研 究[D].北京:清华大学,2015.[ZHANG Jianxin. Study on water-saving irrigation in changma irrigation area of Shule River Basin based on WEAP Model[D]. Beijing: Tsinghua University,2015.]   
[32］黄珊,冯起,齐敬辉,等.河西走廊疏勒河流域水资源管理问题 分析[J].冰川冻土,2018,40(4):846－852.[HUANG Shan, FENG Qi,QI Jinghui,et al. Analyzing and discussing the water resources management in Shule River Basin in Hexi Corridor [J].Journal of Glaciology and Geocryology,2018,40(4):846-

852.]

[33］严宇红,黄维东.疏勒河流域泥沙分布规律及水沙关系研究 [J].干旱区地理,2019,42（1）:47－55.[YAN Yuhong, HUANG Weidong. Sediment distribution and runoff-sediment relationship in the Shule River Basin[J].Arid Land Geography,   
2019,42(1):47- 55.] [34］BASTIAANSSEN WG M.SEBAL-based sensible and latent heat fluxes in the irrigated Gediz Basin，Turkey[J]. Journal of Hydrology,2000,229(1):87-100. [35]刘素华,田静,米素娟.遥感估算蒸散发量的日尺度扩展方法 综述[J].国土资源遥感,2016,28(4)：10-17.[LIU Suhua, TIAN Jing,MI Sujuan.Review of methods on estimation of daily evapotranspiration from one time-of-day remotely sensed transient evapotranspiration［J].Remote Sensing for Land & Resources,2016,28(4):10-17.] [36］蒋磊,杨雨亭,尚松浩.基于遥感蒸发模型的干旱区灌区灌溉 效率评价[J].农业工程学报,2013,29(20)：95-101.[JIANG Lei,YANG Yuting,SHANG Songhao.Evaluation on irrigation efficiency of irrigation district in arid region based on evapotranspiration estimated from remote sensing data[J].Transactions of the Chinese Society for Agricultural Machinery,2013,29 (20):95-101.] [37］盛彩红.疏勒河流域典型作物需水量及作物系数研究[D].北 京:清华大学,2017.[SHENG Caihong.Study on water requirement and crop coefficient of typical crops in Shule River Basin [D].Beijing:Tsinghua University,2017.] [38］阳勇,陈仁升,宋耀选,等.黑河上游山区草地蒸散发观测与估 算[J].应用生态学报,2013,24(4):1055-1062.[YANG Yong， CHEN Rensheng,SONG Yaoxuan,et al. Measurement and estimation of grassland evapotranspiration in a mountainous region at the upper reach of Heihe River Basin,China[J].Chinese Journal of Applied Ecology,2013,24(4):1055-1062.] [39］金学杰,周剑.基于SEBS模型和Landsat 8数据的黑河下游蒸 散发时空特性分析[J].冰川冻土,2017,39(3)：572－582. [JIN Xuejie,ZHOU Jian.Analysis of spatial-temporal characteristics of evapotranspiration in the lower reaches of Heihe River based on surface energy balance system model and Landsat 8 data[J].Journal of Glaciology and Geocryology,2017,39（3）:   
572 - 582.]

# Estimation of evapotranspiration in Shule River Basin based on SEBAL model and evaluation on irrigation efficiency

NING Ya-zhou'， ZHANG Fu-ping'， FENG Qi²， WEI Yong-fen³,LI Ling'， LIU Jie-yao'， ZENG Pan-ru'(1SchoolofGeography and Tourism,Shaanxi Normal University,Xi'an71o119,Shaanxi,China;2NorthwestInstituteofEco-EnvironmentandResources,ChineseAcademyofSciences,anzhou30oo,Gansu,Cina;3River Basin Research Center,Gifu University,Gifu 501-1193,Japan)

Abstract:Water resources are scarce forinland river basins inarid regions of northwestern China,where water consumption is mainly for agriculture.Especially in arid regions,evapotranspiration $( E T )$ is the main link to the water cycleand has an important impact on environmentalchanges.Itis therefore important to accurately estimate ET and irigation eficiencyfor predicting climate change and forrationallallocating waterresources in inland riverbasins.The Shule River Basin isoneof three inland river basins inthe Hexi Corridor,and itsecological environment is fragile given its large annual average $E T$ .Water use accounts for a large proportion ,and the utilization rate of agricultural irrgation water is high in this region.In this study,we estimated the daily evapotranspiration ( $( E T )$ of the Shule River Basin （SRB） based on the Surface Energy Balance Algorithms for Land（SEBAL） model with satelite data （from the moderate-resolution imaging spectroradiometer known as MODIS）and meteorological data from March in 2017 through February in 2018.Then we applied a time-scale extension to obtain monthly and seasonal $E T$ by using daily $E T$ and meteorological data. We also analyzed the spatiotemporal distribution characteristics of $E T$ to derive daily and seasonal $E T$ .Then,combining the $E T$ results from the SEBAL simulation and data collected on irrigation and precipitation for the Changma irigation district（CM） during 2017- 2018, we calculated the coefficient of irrigation-water effective utilization $( ^ { \ast } \eta ^ { \ast } )$ for the CM on the basis of the water-balance equation,which was used for irrigation-efficiency assessment for the CM.

The main conclusions are as follows:（1） The variation range of average daily $E T$ values was 0.55 - 5.03 mm across the SRB during 2017-2018,which showed a single peak change and obvious diference in spatial distribution.（2） There were significant differences in seasonal $E T$ in the SRB; summer $E T$ was the highest （201.83 $\mathrm { m m }$ ）,followed by spring and autumn,and the winter $E T$ was the lowest ( $5 3 . 9 2 ~ \mathrm { m m }$ ). The spatial pattern of seasonal $E T$ shows that $E T$ in the upper reaches of SRB was significantly higher than that in the middle and lower reaches,and $E T$ decreased from the southeast to the northwest in the SRB.（3） The quantity of irigation water in different irrigation periods resulted in the $E T$ differences in the CM. The high $. E T$ area was mainly in the middle and southeastern parts of the irigation district,and the low-ETarea was mainly in the northwestern part and along the margins of the district.（4） The“ $\eta$ ” of CM showed a downward trend during the irrigation period,in which the values of “ $\cdot _ { \eta ^ { \dag } }$ for the spring,summer,autumn,and winter irrigation periods were $0 . 7 6 , 0 . 7 1 , 0 . 6 9$ ,and 0.55,respectively. The CM had a higher irrigation efficiency,with the annual “ $\cdot \eta ^ { \dag }$ of 0.67.

Through simulation of monthly $E T$ in the SRB for the period 2017 - 2018,the annual $E T$ spatial distributions and fluctuations were more detailed and clearer. We found that $E T$ of irrigation land could be accurately estimated by remote-sensing and meteorological data. The “ $\cdot _ { \eta ^ { \dag } }$ of the irrigation district could easily be obtained from $E T$ and measured irrigation data in each irrigation period,which can reflect CM irrigation efficiency during the year in the SRB.

Key words:evapotranspiration； SEBAL model； Shule River Basin；coefficient of irigation water effectiveutilization； Changma irrigation district