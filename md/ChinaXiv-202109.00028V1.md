# 基于多源遥感数据的温度-土壤湿度-降水干旱指数(TMPDI)的构建与应用

满元伟，李净，邢立亭(西北师范大学地理与环境科学学院，甘肃 兰州730070)

摘要：干旱在全球范围内产生了深远的社会和经济影响,可靠的干旱监测对防旱抗旱工作具有重要指导意义。由于在植被覆盖度和农作物种植率较低区域使用植被状态或单因子进行干旱监测时精度较低,故本文采用地表温度(LST）、降水量 $( P )$ 和土壤湿度(SM)数据，基于三维欧氏几何空间中欧氏距离方法构建了一种新的干旱指数：温度-土壤湿度-降水干旱指数(TMPDI)用于干旱监测。并以甘肃省为研究区,利用SPI、SPEI、遥感数据以及小麦单位面积单产对TMPDI进行验证。结果表明：TMPDI与SPI、SPEI高度相关( $R ^ { 2 } { > } 0 . 6 4 \rangle$ ,且在干旱监测中兼顾降水量与气温影响的同时,降低了使用降水量或地表温度进行干旱监测的不确定性,提高了土壤湿度在农业干旱监测中的准确性与有效性,能准确地描述干旱事件的时空演变特征,同时也能较好地反映出干旱强度与干旱面积率的变化对小麦产量造成的影响,说明TMPDI在农业干旱监测中具有较高的有效性和可靠性。

关键词：干旱指数；干旱监测；遥感；MODIS；TRMM；GLEAM

干旱是陆地生态系统的自然灾害之一，具有覆盖范围广、发生频率高、影响严重等特点，因此，干旱监测和旱灾损失评价已成为亟待解决的科学问题[]。由于遥感技术能提供时空连续的数据,因此被广泛应用于干旱监测。目前国内外学者应用于干旱监测的遥感卫星数据主要有降水数据、地表温度数据、蒸发/蒸散发数据、植被数据和土壤湿度数据。其中TRMM降水数据、土壤湿度数据和植被指数已在国内外干旱监测中得到了广泛应用[2-6]。蒸发/蒸散发也可以通过遥感技术估算[7]。

十旱程度主要采用十旱指标进行量化。国内外学者在建立干旱监测指标方面做了大量研究，早期的干旱指标主要通过气象站数据计算的干旱指数，如标准化降水指数(SPI)[8]，标准化降水蒸散指数(SPEI)[9]和帕梅尔干旱指数(PDSI)[10]等,这些指数精度较高，但无法进行空间连续的干旱监测。因而基于遥感数据的干旱指标开始被广泛研究，例如,温度条件指数(TCI)["]、植被状况指数(VCI)[12]和降水条件指数(PCI)[13]等。然而，国内外学者认识到，使用多个变量或参数可以提高干旱监测的准确性，因此，综合降水量、土壤湿度、地表温度和植被指数，开发了植被健康指数(VHI)[4]、温度植被干旱指数(TVDI)[15]和微波合成干旱指数(MIDI)[16]等指标。

干旱是造成全球农业生产损失的主要因素[17]例如,甘肃省每年均有不同程度的农业旱情发生[18]仅2004年就有 $9 2 . 5 { \times } 1 0 ^ { 4 } ~ \mathrm { h m } ^ { 2 }$ 农作物因干旱受灾，其中 $7 . 6 { \times } 1 0 ^ { 4 } \mathrm { h m } ^ { 2 }$ 绝收，直接经济损失 $9 . 5 { \times } 1 0 ^ { 8 }$ 元[19]。由于植被指数在植被覆盖度和农作物种植率较低的地区干旱监测效果较差，且现有的多变量干旱指数在其计算过程中存在一定的主观性和复杂性[20]因此，本文选取地表温度(LST）、降水量(P)和土壤湿度(SM)3个参数，采用欧氏距离方法构建了新的干旱指数：温度-土壤湿度-降水干旱指数(TMPDI)。以甘肃省为研究区，验证TMPDI在农业干旱监测中的精度，同时研究干旱对小麦产量的影响。

# 1数据与方法

# 1.1 研究区概况

甘肃省位于我国西北地区，地理位置位于$9 2 ^ { \circ } 1 3 ^ { \prime } { \sim } 1 0 8 ^ { \circ } 4 6 ^ { \prime } \mathrm { E } , 3 2 ^ { \circ } 1 1 ^ { \prime } { \sim } 4 2 ^ { \circ } 5 7 ^ { \prime } \mathrm { N }$ （图1)。省内气候类型多样，从南向北包括了亚热带季风气候、温带季风气候、温带大陆性气候和高原高寒气候等气候类型，全年降水量少，气候干燥，以黄河为界，河西为内陆干旱区，主要以灌溉农业为主，河东为雨养农业区[21]。本文依据小麦种植类型与种植方式将研究区划分为春小麦灌溉农业区、冬小麦雨养农业区和春、冬小麦混合农业区。

![](images/44dd3c89bbe94994dcf1379441083ab5f01ed5ce745e03e88056233a2dfe9249.jpg)  
图1研究区示意图  
Fig.1 Schematic diagram of the study area

# 1.2数据来源

1.2.1 气象数据选取甘肃省境内2000—2018年25个有完整数据的气象站的月平均降水量数据和月平均气温数据，来源于中国气象数据网(http://da-ta.cma.cn/）。采用气象数据计算标准化降水指数(SPI)和标准化降水蒸散指数(SPEI)。SPI与 SPEI是干旱研究中应用广泛，具有较高可信度，常用于干旱指数的准确性检验

1.2.2 遥感卫星数据2000—2018年降水与地表温度数据从美国航天航空局NASA(http://www.nasa.gov/)获取。其中,降水数据来源于TRMM_3B43V7数据产品，空间分辨率为 $0 . 2 5 ^ { \circ }$ ,地表温度数据来源于MOD11B3数据产品，空间分辨率为 $6 \mathrm { k m }$ ○

2000—2018年土壤湿度数据来源于英国布里斯托大学地理科学学院的GLEAM数据产品(http:geoservices.falw.vu.nl.）,空间分辨率为 $0 . 2 5 ^ { \circ }$ ,时间分辨率为1d,该数据已经过站点实测数据进行验证，在国内干旱-半干旱区具有较高的准确性[22]

1.2.3小麦产量数据甘肃省2000—2018年春、冬小麦产量数据来源于《甘肃农业年鉴》，其中春小麦最早播种时间为3月下旬，最晚收割时间为7月下旬；冬小麦最早播种时间为9月下旬，最晚收割时间为7月中旬。

作物产量通常受气候变化和人类活动的影响，如作物品种的改良和农业技术的发展[1]。为精确分析小麦产量与干旱之间的关系，需消除人类活动影响，仅获取气候因素造成的作物产量变化，即气候产量。因此，将农作物产量分为气候产量、趋势产量和随机误差3部分，其中随机误差具有不确定性，通常忽略不计，农作物实际产量可以用气候产量与趋势产量之和表示，公式如下：

$$
Y _ { _ i } = Y _ { _ c } + Y _ { _ t }
$$

式中： $Y _ { _ i }$ 为第 $i$ 县区的农作物实际产量， $Y _ { c }$ 和 $Y _ { _ t }$ 为 该县区的气候产量和趋势产量，

# 1.3 研究方法

1.3.1农业干旱成灾机理区域内持续的低降水量和高温导致该区域降水亏缺和高蒸散量进而引发气象干旱，降水亏缺和高蒸散量又导致土壤湿度降低进而引发农业干旱[23]。因此，可以通过降水量、温度、植被和土壤湿度等影响因子进行农业干旱监测。由于中国西北部人口稀少，受土壤肥力和气候条件的影响，植被覆盖度和粮食种植率均较低，不适合使用植被指数进行干旱监测[24]。为提高农业干旱监测的准确性，本文选取地表温度、土壤湿度和降水量对甘肃省进行干旱监测

1.3.2 温度-土壤湿度-降水干旱指数(TMPDI)构建欧氏距离可以度量多维空间中各点之间的绝对距离，在最简单的形式中，它可以被定义为连接两个点A和B之间的直线[25]。欧氏距离具有客观性、科学性和普遍性的特点，已用于国内外的干旱监测中[20.26]。欧氏距离计算公式如下：

$$
D ( x , y ) = { \sqrt { \sum _ { i = 1 } ^ { n } ( x _ { i } - y _ { i } ) ^ { 2 } } }
$$

式中： $D ( x , y )$ 是点 $x \ ( \ x _ { 1 } , \ x _ { 2 } , \ x _ { 3 } \ \cdots , \ x _ { n } \ )$ 与点 $y$ $( \mathbf { \Phi } _ { y _ { 1 } } , \mathbf { \Phi } _ { y _ { 2 } } , \mathbf { \Phi } _ { y _ { 3 } } \cdots , \mathbf { \Phi } _ { y _ { n } } )$ 之间的欧氏距离； $n$ 为欧式几何空间的维度。

温度-土壤湿度-降水干旱指数(TMPDI)的计算分为如下几个步骤：首先，在三维空间中设定一个参照点，该点表示每个维度中干旱最严重的状态点，然后计算三维空间中该点到每个点的欧氏距离，且距离越短,干旱程度越严重。由于降水量、土壤湿度和地表温度的单位不同，因此需要进行标准化处理为无量纲的量，计算方法如下：

$$
\mathrm { N o r m a l i z e d \ L S T ( N L S T ) = \frac { \Delta L S T _ { \it i } - L S T _ { \mathrm { m i n } } } { L S T _ { \mathrm { m a x } } - L S T _ { \mathrm { m i n } } } }
$$

$$
\mathrm { N o r m a l i z e d S M ( N S M ) } = \frac { \mathrm { S M } _ { i } - \mathrm { S M } _ { \mathrm { m i n } } } { \mathrm { S M } _ { \mathrm { m a x } } - \mathrm { S M } _ { \mathrm { m i n } } }
$$

$$
\mathrm { N o r m a l i z e d P ( N P ) } = \frac { P _ { \it \Pi } - P _ { \mathrm { m i n } } } { P _ { \mathrm { m a x } } - P _ { \mathrm { m i n } } }
$$

式中： $\mathrm { L S T } _ { i }$ ， $\mathrm { S M } _ { i }$ ， ${ \boldsymbol { P } } _ { i }$ 分别为第 $i$ 月的地表温度、土壤湿度和降水量，max和 $\operatorname* { m i n }$ 表示历年该月的最大值与最小值;NLST，NSM，NP分别为标准化的地表温度、土壤湿度和降水量。

最后，根据三维空间中欧氏距离的定义，整合标准化后的降水量、土壤湿度和地表温度，计算得出TMPDI。为便于应用，将TMPDI的值压缩到0\~1之间，公式如下：

$$
\sqrt { \frac { ( \mathrm { N L S T } _ { \mathrm { m a x } } - \mathrm { N L S T } _ { i } ) ^ { 2 } + ( \mathrm { N S M } _ { \mathrm { m a x } } - \mathrm { N S M } _ { i } ) ^ { 2 } + ( \mathrm { N P } _ { \mathrm { m a x } } - \mathrm { N P } _ { i } ) ^ { 2 } } { 3 } }
$$

式中： $\mathrm { N L S T } _ { i }$ 人 $\mathrm { N S M } _ { i }$ 、 $ { \mathbf { N P } } _ { i }$ 分别为标准化的第 $i$ 月的地表温度、土壤湿度和降水量的值，（ $\mathrm { N L S T _ { \mathrm { m a x } } }$ ， $\mathrm { { N S M } _ { \operatorname* { m a x } } }$ ， $\mathrm { N P } _ { \operatorname* { m a x } }$ )的值为(1,0,0)，表示三维空间中理论上干旱最严重的点。

1.3.3其他遥感干旱指数PCI、TCI和SMCI是常用的时序型单变量干旱指数，广泛应用于干旱监测，同时在多变量干旱指数构建中也具有普适性[27]。因此,本文选取PCI、TCI和SMCI3种遥感干旱指数共同验证TMPDI的有效性与可靠性，具体计算公式如下：

$$
\mathrm { P C I } = \frac { \mathrm { T R M M } _ { i } - \mathrm { T R M M } _ { \operatorname* { m i n } } } { \mathrm { T R M M } _ { \operatorname* { m a x } } - \mathrm { T R M M } _ { \operatorname* { m i n } } }
$$

$$
\mathrm { T C I } = \frac { \mathrm { L S T } _ { \mathrm { m a x } } - \mathrm { L S T } _ { i } } { \mathrm { L S T } _ { \mathrm { m a x } } - \mathrm { L S T } _ { \mathrm { m i n } } }
$$

$$
{ \mathrm { S M C I } } = { \frac { { \mathrm { S M } } _ { i } - { \mathrm { S M } } _ { \operatorname* { m i n } } } { { \mathrm { S M } } _ { \operatorname* { m a x } } - { \mathrm { S M } } _ { \operatorname* { m i n } } } }
$$

# 2结果与分析

# 2.1TMPDI在干旱监测中的精度评价

2.1.1遥感干旱指数与气象干旱指数的相关分析选取甘肃省境内25个气象站点降水和气温数据计算月值SPI与SPEI,对遥感干旱指数与气象干旱指数进行相关分析，结果如表1所示，遥感干旱指数与气象干旱指数总体呈正相关关系，其中PCI与SPI和SPEI相关性最高，其原因为SPI、SPEI均考虑降水量为主要因子进行计算。同时，PCI与SPI和SPEI的相关系数差值最大，为0.081,TCI与SPI和SPEI的相关系数差值为-0.072,其原因为SPEI在SPI的基础上进一步考虑了气温对干旱的影响，说明单独考虑降水量或气温进行干旱监测的不确定性较大。受降水量和气温影响的SMCI与SPI、SPEI的相关系数差值为正数，且小于0.081,说明降水量对土壤湿度影响较大的同时，气温也对土壤湿度产生一定的影响。TMPDI与SP和SPEI的相关系数远高于SMCI,且差值较小，仅为0.021，证明TMPDI在干旱监测中兼顾降水量与气温影响的同时，降低了使用降水量或地表温度进行干旱监测的不确定性，提高了土壤湿度在农业干旱监测中的准确性与有效性。

# 表1遥感干旱指数与SPI、SPEI的相关系数

Tab.1 Correlation coefficients between remote sensing drought indexandSPI,SPEI   

<html><body><table><tr><td>遥感干旱指数</td><td>SPI</td><td>SPEI</td></tr><tr><td>SMCI</td><td>0.426</td><td>0.375</td></tr><tr><td>TCI</td><td>0.375</td><td>0.447</td></tr><tr><td>PCI</td><td>0.696</td><td>0.615</td></tr><tr><td>TMPDI</td><td>0.632</td><td>0.611</td></tr></table></body></html>

注：表中数据均通过0.01的显著性检验。

2.1.2TMPDI与实际干旱事件的时空一致性分析2000一2018年TMPDI与SPI和SPEI的时间变化如图2所示，其中SPI和SPEI监测到的干旱发生率分别为 $4 6 \%$ 和 $5 3 \%$ ，说明甘肃省干旱事件频发。同时，TMPDI与SPI和SPEI的时间变化具有高度一致性，且TMPDI对2000年、2004年、2008年和2013年发生的严重干旱事件有很好的响应关系，说明TMPDI在月尺度上对甘肃省进行干旱监测的可信度较高。

为验证TMPDI监测干旱时空分布与实际干旱事件的一致性，按照《气象干旱等级》划分的标准化降水指数和标准化降水蒸散指数干旱等级[27],结合TMPDI与SPI和SPEI的相关性以及各干旱等级出现的频率，对TMPDI进行干旱等级划分。干旱等级划分结果如表2所示。

由2008年5—7月TMPDI的时空分布可知（图3a\~图3c），5月重旱区分布在陇南、陇西及陇中北部，6月陇南、陇西旱情缓解，陇中北部部分地区旱情有所缓解，庆阳市中北部出现旱情，7月旱情集中

![](images/91cc7f388845861e117d13f0c74fdfd80c4bef696e6b227cae982c474aaa6169.jpg)  
图22000—2018年甘肃省TMPDI与SPI、SPEI变化特征Fig.2Variation characteristics of TMPDI, SPI and SPEI inGansu Province from 2000 to 2018

# 表2TMPDI的干旱等级划分

Tab.2 Drought classification of TMPDI   

<html><body><table><tr><td>干旱等级</td><td>SPI</td><td>SPEI TMPDI</td></tr><tr><td>无旱</td><td>-0.5<SPI -0.5<SPEI</td><td>0.45<TMPDI</td></tr><tr><td>轻旱</td><td>-1.0<SPI≤-0.5 -1.0<SPEI≤-0.5</td><td>0.35<TMPDI≤0.45</td></tr><tr><td>中旱</td><td>-1.5<SPI≤-1.0</td><td>-1.5<SPEI≤-1.0 0.25<TMPDI≤0.35</td></tr><tr><td>重旱</td><td>-2.0<SPI≤-1.5</td><td>-2.0<SPEI≤-1.5 0.15<TMPDI≤0.25</td></tr><tr><td>特旱</td><td>SPI≤-2.0 SPEI≤-2.0</td><td>TMPDI≤0.15</td></tr></table></body></html>

在甘肃中部及庆阳中北部。由2008年11月至2009年1月的TMPDI时空分布可知（图3d\~图3f)，11月冬小麦雨养农业区出现旱情，12月冬小麦雨养农业区大范围出现重旱，2009年1月旱情有所缓解。由2013年3—5月的TMPDI时空分布可知（图 $3 \mathrm { g } \sim$ 图3i)，3月重旱出现在甘肃中部、东部及南部，4—5月旱情逐步缓解，5月仅甘肃中部存在重旱。这与《中国气象灾害年鉴》中记载的干旱事件时空分布一致[19]。说明TMPDI监测到的干旱事件符合历史灾情的描述，能真实反应干旱情况，在干旱监测中具有较高的可信度。

![](images/7408a5ffee0aec242640420653847c23948680a56b389d831c86246529aee686.jpg)  
图3甘肃省TMPDI干旱监测分布  
Fig.3Distribution of drought monitored by TMPDI in Gansu Province

本文选取2004年进行研究，以验证TMPDI与实际旱情的时空变化一致性。如图4所示，2004年1—3月小部分地区有轻到中旱;4月份干旱面积迅速扩大,河西东西部、陇东、陇中、天水和陇南市均监测到重旱和特旱，甘南州大部分为轻旱;5月全省旱情有所缓解;6月河西旱情进一步缓解，但仍然存在有重旱区，白银、兰州、天水和陇南市旱情加重；7月除陇南南部出现小面积重旱外，河东旱情基本缓解；8月甘肃省小部分地区有轻到中旱，河西旱情基本平复;9月在河西中部监测到重旱，而河东旱情较8月进一步缓解；10—11月在河东监测到重旱。可以看出，TMPDI与2004年实际干旱事件的时空分布完全一致，说明TMPDI能真实地反映出干旱事件在月尺度上的时空变化特征。

# 2.2TMPDI与小麦产量的相关分析

小麦是甘肃省主要粮食作物之一，2018年全省小麦种植面积占粮食作物种植面积的 $2 1 \% ^ { [ 2 8 ] }$ 。因此，分析干旱对小麦产量的影响意义重大。由于气候产量消除了人类活动对产量的影响，故分析春小麦种植区和冬小麦种植区内50个县区的干旱强度与干旱面积对小麦气候单产(以下称小麦单产)的影响。

2.2.1干旱强度与冬小麦单产的相关分析冬小麦雨养农业区内的小麦单产与TMPDI的相关性时空分布如图5所示，从时间分布上看，冬小麦生长期内的TMPDI与小麦单产呈现正相关关系，即干旱强度越高，小麦单产越低。其中，10一12月的相关系数相对较高，平均值高于0.25，最高值出现在12月的庄浪县，为0.75;1—6月相关系数较低，平均值低于0.15。说明TMPDI可以反映出冬小麦生育期内干旱强度变化引起的小麦单产波动情况，且10—12月的旱情对冬小麦单产影响较大。从空间分布上看，自东北向西南，相关系数有降低的趋势。其原因为西南部的陇南市下辖各县小麦受条锈病影响严重，2008年 $1 . 7 3 \times 1 0 ^ { 4 } \mathrm { h m } ^ { 2 }$ 小麦遭受条锈病害，到2018年遭受高感条锈病小麦种植面积仍占一半左右。

![](images/d92557037d7ce78d917b11cd6eda48a960738e1ee5d79845c1fcf52292f6cc82.jpg)  
图4甘肃省TMPDI干旱监测分布  
Fig.4Distribution of drought monitored by TMPDI in Gansu Province

![](images/028e878a5a54e70beefb9b482070eb8df1447871081fa1fdbb085806f825521b.jpg)  
注：1—6月为冬小麦收割年，10—12月为冬小麦种植年。  
图52000—2018年冬小麦单产与TMPDI的相关性分布  
Fig.5Distribution of correlation coefficient between winter wheat yield and TMPDI from 20o0 to 2018

2.2.2干旱面积率与冬小麦单产的相关分析为对比各县区干旱面积对小麦单产的影响，计算各县干旱面积占县区面积的比例,即得到干旱面积率。如图6所示，冬小麦生育期内基于TMPDI的干旱面积率与冬小麦产量总体呈负相关关系，即干旱面积越大，小麦单产越低;10一12月的相关性相对较高，其中，相关性最高出现在12月的庄浪县;1一6月相关性较低。说明基于TMPDI的干旱面积率可以反映出十旱面积导致的冬小麦单产波动情况，且10—12月的干旱面积对冬小麦单产影响较大。

2.2.3干旱强度和干旱面积率与春小麦单产的相关分析春小麦灌溉农业区主要位于甘肃省河西地区，以灌溉农业为主，且春小麦种植面积较小。由表3可知，春小麦单产与TMPD呈正相关关系，与十旱面积率呈负相关关系。其中，春小麦单产与干旱强度和干旱面积率相关系数民乐县最高出现在6月，分别为0.624和-0.546。说明TMPDI和基于TMPDI的干旱面积率可以反映生育期内干旱强度和干旱面积对春小麦单产波动的影响，且4一6月的影响较大。同时发现,春小麦单产与干旱强度和干旱面积率的相关性低于冬小麦。其原因为春小麦种植区以灌溉农业为主，因此，小麦产量受干旱事件影响较小，与干旱强度和干旱面积率相关性较差。

![](images/6f85bfcd2ce3ef6f4c6cbe22bb35116651dbec799725e8bf6d2caea66b8b0ad8.jpg)  
注：1—6月为冬小麦收割年，10—12月为冬小麦种植年。  
图62000—2018年冬小麦单产与干旱面积率的相关性分布  
Fig.6Distribution of correlation coefficient between winter wheat yield and drought area rate from 2Oo0 to 2018

# 3讨论

在过去几十年气候变化导致频繁的干旱事件引起了科学界的关注[29]。目前，国内外学者引入了大量干旱指数来监测干旱事件[8-16]。由于我国西部地区受土壤肥力和气候条件影响，植被覆盖度和粮食种植率低，使用植被状态进行干旱监测效果较差[20.24]。因此,本文从农业干旱的成灾机理和实际地理因素出发，选取地表温度、降水量和土壤湿度3个主要影响因子，采用欧氏距离方法避免计算过程中存在的主观性与复杂性，构建了温度-土壤湿度-降水干旱指数(TMPDI)进行干旱监测。经验证发现TMPDI与SPI、SPEI高度相关，且监测到的干旱事件与记载的几次干旱事件具有完全一致的时空分布特征，TMPDI和干旱面积率与小麦单产相关系数整体比使用植被状态进行干旱监测时的相关性有显著的提升。说明TMPDI考虑了气候变化和人类活动(如灌溉管理)的影响，一定程度上提高了干旱监测能力，使其在植被覆盖度和粮食种植率低的地区使用土壤水分能更有效地监测干旱

表3春小麦主要种植县区的小麦单产与干旱强度和干旱面积率相关性  
Tab.3 Correlation between wheat yield per unit area and drought intensity and area ratio of spring wheat in main planting counties   

<html><body><table><tr><td colspan="2"></td><td>3月</td><td>4月</td><td>5月</td><td>6月</td><td>7月</td></tr><tr><td rowspan="2">民乐县</td><td>TMPDI</td><td>0.135</td><td>0.059</td><td>0.437</td><td>0.624**</td><td>0.231</td></tr><tr><td>干旱面积率</td><td>-0.105</td><td>-0.062</td><td>-0.407</td><td>-0.546*</td><td>-0.313</td></tr><tr><td rowspan="2">山丹县</td><td>TMPDI</td><td>0.315</td><td>0.099</td><td>0.383</td><td>0.543*</td><td>0.248</td></tr><tr><td>干旱面积率</td><td>-0.275</td><td>-0.052</td><td>-0.405</td><td>-0.425</td><td>-0.318</td></tr><tr><td rowspan="2">天祝县</td><td>TMPDI</td><td>0.177</td><td>0.399*</td><td>0.403</td><td>0.136</td><td>0.013</td></tr><tr><td>干旱面积率</td><td>0</td><td>-0.350*</td><td>-0.368</td><td>-0.086</td><td>0.009</td></tr><tr><td rowspan="2">民勤县</td><td>TMPDI</td><td>0.182</td><td>-0.283</td><td>-0.004</td><td>-0.275</td><td>0.084</td></tr><tr><td>干旱面积率</td><td>0.121</td><td>-0.340</td><td>0.050</td><td>-0.216</td><td>0.174</td></tr><tr><td rowspan="2">永昌县</td><td>TMPDI</td><td>-0.046</td><td>-0.064</td><td>0.252</td><td>0.493*</td><td>0.085</td></tr><tr><td>干旱面积率</td><td>0.022</td><td>-0.011</td><td>-0.152</td><td>-0.451*</td><td>-0.289</td></tr><tr><td rowspan="2">靖远县</td><td>TMPDI</td><td>0.178</td><td>0</td><td>-0.232</td><td>0.024</td><td>-0.102</td></tr><tr><td>干旱面积率</td><td>0.004</td><td>0.077</td><td>0.174</td><td>0.003</td><td>0.096</td></tr><tr><td rowspan="2">景泰县</td><td>TMPDI</td><td>0.049</td><td>-0.177</td><td>0.299</td><td>0.041</td><td>0.165</td></tr><tr><td>干旱面积率</td><td>-0.120</td><td>0.144</td><td>-0.392</td><td>-0.109</td><td>0.031</td></tr></table></body></html>

注：\*\*通过了0.01的显著性检验，\*表示通过了0.05的显著性检验。

干旱对农业生产造成了日益严重的损失[30]为研究干旱对农业生产力的影响，利用TMPDI和干旱面积率与小麦单产进行相关分析，发现相关系数在不同月份间有所波动。与冬小麦产量的相关系数在10一12月较高，与春小麦产量的相关系数在5—6月较高。说明干旱发生在小麦不同生长期对小麦产量造成的影响不同，这与前人的研究结果一致[30-32]。研究发现在春小麦灌溉农业区,TMPDI和干旱面积率与小麦单产的相关系数略有下降，降水量是造成这一现象的主要因素，冬小麦种植区年降水量在 $4 0 0 ~ \mathrm { m m }$ 以上，春小麦种植区年降水量则在$2 0 0 \mathrm { m m }$ 以下。由于土壤层中储存充足的降水量，可满足作物生长期的需水量[33]。因此，降水量的剧烈变化使TMPDI在灌溉为主的农业区监测能力受到一些影响。

Anyamba等[34发现水分亏缺相关的叶片结构变化发生在3\~7d,故本文在月尺度上建立的TMPDI的时间分辨率无法完全满足农业干旱监测的需求。降水、气温和土壤湿度虽是干旱的主要影响因子，但影响干旱的因素还包括区域气候和地质、植被覆盖和类型、土壤、地形和人类活动[35。因此,

TMPDI的时空分辨率和准确性有待进一步提高，

# 4结论

根据MODIS、TRMM和GLEAM数据集分别获取了地表温度(LST）、降水量 $( P )$ 和土壤湿度(SM)数据，基于三维欧氏几何空间中欧氏距离计算方法构建了一种新的干旱指数：温度-土壤湿度-降水干旱指数(TMPDI)。以甘肃省为研究区验证该干旱指数在干旱监测中的精度，分析了甘肃省干旱事件时空分布及其对小麦单产的影响，主要得出如下结论：

（1）2000—2018年TMPDI与SPI和SPEI的相关系数分别为0.632和0.611，相关性较高，同时比PCI、TCI和SMCI与SPI和SPEI的相关系数差值较小，说明TMPDI在干旱监测中兼顾降水量与气温影响的同时，降低了使用降水量或地表温度进行干旱监测的不确定性，提高了土壤湿度在农业干旱监测中的准确性与有效性。

（2）2000—2018年TMPDI与SPI、SPEI的时间变化具有高度一致性，对比2004年、2008年、2013年甘肃省的几次严重干旱事件以及2004年整年的干旱时空变化，发现TMPDI能够很好地反映几次干旱事件且与记载的干旱事件的时空变化一致，说明TMPDI在干旱监测中能够很好地监测干旱的时空分布特征，具有较高的可信度。

(3）在与小麦的气象单产数据对比中发现TMPDI和基于TMPDI的干旱面积率与春、冬小麦气候产量相关性均较高，与冬小麦气候产量相关性最高分别为0.75和-0.74，与春小麦气候产量相关性最高分别为0.624和-0.546。说明TMPDI可以较好地反映出干旱强度与干旱面积率的变化引起的小麦单产波动，且在雨养农业区和灌溉农业区内均具有适用性。

# 参考文献(References):

[1]Liu X, Zhu X,Pan Y,et al. Agricultural drought monitoring: Progress,challenges,and prospects[J]. Journal of Geographical Sciences,2016,26(6): 750-767.   
[2]Du L,Tian Q,Yu T,etal.A comprehensive drought monitoring method integrating MODIS and TRMM data[J]. International Journal of Applied Earth Observation & Geoinformation,2013,23: 245-253.   
[3]YuF,Price KP,Elis J, et al.Response of seasonal vegetation development to climatic variations in eastern central Asia[J].Remote Sensing of Environment, 2003,87(1): 42-54.   
[4]孙博,钱静,陈曦,等.常见遥感干旱监测指标在哈萨克斯坦的 一致性分析[J].干旱区研究,2020,37(3):663-670.[Sun Bo, Qian Jing, Chen Xi, et al. Consistency and comparison among re mote sensing drought indices and SMAP soil moisture in Kazakhstan[J]. Arid Zorn Research,2020,37(3): 663-670.]   
[5]Potopova V,Trnka M,Hamouz P,et al. Statistical modelling of drought-related yield losses using soil moisture-vegetation remote sensing and multiscalar indices in the south-eastern Europe[J]. Agricultural Water Management,2020,236: 1-18.   
[6]Hwang T,Gholizadeh H, Sims D A,et al. Capturing species-level drought responses in a temperate deciduous forest using ratios of photochemical reflectance indices between sunlit and shaded canopies[J]. Remote Sensing of Environment, 2017,199: 350-359.   
[7]程文举,席海洋,司建华,等.河西内陆河浅山区流域蒸散发估 算及干旱特性研究[J].干旱区研究,2020,37(5):1105-1115. [Cheng Wenju, Xi Haiyang,Si Jianhua, et al. Study of evapotranspiration estimation and drought characteristics of watershed in low coteau area of Hexi inland river[J].Arid Zone Research,2020, 37 (5): 1105-1115.]   
[8]McKee TB, Doesken NJ, Kleist J. The relationship of drought frequency and duration to time scales[J]. Eighth Conference on Applied Climatology,Anaheim,1993:17-24.   
[9]Vicente-Serrano S M, Santiago B,Lopez-Moreno JI. A multiscalar drought index sensitive to global warming: The standardized precipitation evapotranspiration index[J]. Journal of Climate,2010,23 (7): 1696-1718.   
[10]Palmer W C.Meteorological Drought (Research Paper No.45) [R]. Washington: USDepartment of Commerce,Weather Bureau, 1965: 45-58.   
[11]Bhuiyan C, Singh R P,Kogan F N. Monitoring drought dynamics in the Aravalli region (India) using diferent indices based on ground and remote sensing data[J].International Journal of Applied Earth Observation & Geoinformation,2006,8(4): 289-302.   
[12]Kogan FN.Application of vegetation index and brightness temperature for drought detection[J]. Advances in Space Research,1995, 15(11): 91-100.   
[13]Du L, Tian Q,Yu T,et al.A comprehensive drought monitoring method integrating MODIS and TRMM data[J]. International Journal of Applied Earth Observation & Geoinformation,2013,23: 245-253.   
[14]Kogan F N, Stark R, Gitelson A,et al. Derivation of pasture biomass in Mongolia from AVHRR-based vegetation health indices [J].International Journal of Remote Sensing,2004,25(14),2889- 2896.   
[15]Sandholt I, Rasmussen K,Andersen J.A simple interpretation of the surface temperature/vegetation index space for assessment of surface moisture status[J]. Remote Sensing of Environment, 2002, 79 (2-3): 213-224.   
[16] Zhang A,Jia G. Monitoring meteorological drought in semiarid regions using multi- sensor microwave remote sensing data[J]. Remote Sensing of Environment, 2013,134: 12-23.   
[17]Campbell B M,Vermeulen S J,Aggarwal P K,et al.Reducing risks to food security from climate change[J]. Global Food Security, 2016, 11: 34-43.   
[18] 韩兰英,张强,赵红岩,等.甘肃省农业干旱灾害损失特征及其 对气候变暖的响应[J].中国沙漠,2016,36(3):767-776.[Han Lanying, Zhang Qiang, Zhao Hongyan,et al. The characteristics of agricultural droughtdisasterloss andresponsetoclimate warming in Gansu, China[J]. Journal of Desert Research,2016,36(3): 767- 776.]   
[19]中国气象局.中国气象灾害年鉴(2004)[M].北京:气象出版社, 2005.[China Meteorological Administration.Yearbook of Meteorological Disasters in China 2O04[M].Beijing: China Meteorological Press, 2005.]   
[20]Wei W,Pang S, Wang X,et al. Temperature Vegetation Precipitation Dryness Index (TVPD)-based dryness-wetness monitoring in China[J]. Remote Sensing of Environment,2020,248:1-18.   
[21] 刘德祥,白虎志,宁惠芳,等.气候变暖对甘肃干旱气象灾害的 影响[J].冰川冻土,2006,28(5): 707-712.[Liu Dexiang,Bai Huzhi,Ning Huifang,et al.Response of arid meteorological disaster to climatic warming in Gansu Province[J].Journal of Glaciology and Geocryology,2006,28(5): 707-712.]   
[22]Ye L,Fang L, Shi Z, et al. Spatio-temporal dynamics of soil mois ture driven by‘Grain for Green’program on the Loess Plateau, China[J]. Agriculture Ecosystems & Environment, 2019,269: 204- 214.   
[23]Loon A V.Hydrological drought explained[J]. WIREs Water, 2015,2: 359-392.   
[24]Qi L A, Sha Z A,Hz C,et al. Monitoring drought using composite drought indices based on remote sensing[J]. Science of The Total Environment,2020,711:1-10.   
[25]Mesquita D,Gomes J, Junior A S,et al.Euclidean distance estimation in incomplete datasets[J].Neurocomputing,2O17,248:11-18.   
[26]Amani M, Salehi B,Mahdavi S,et al. Temperature-Vegetation-soil Moisture Dryness Index (TVMDI)[J].Remote Sensing of Environment, 2017,197: 1-14.   
[27]张强,邹旭恺,肖风劲,等.气象干旱等级(GB/T20481-2006) [S].北京:中国标准出版社,2006:12-17.[Zhang Qiang,Zou Xukai,Xiao Fengjin,et al.Classification of Meteorological Drought Category (GB/T20481-2006)[S]. Beijing: Standards Press of China,2006: 12-17.]   
[28] 甘肃省地方史志办公室.甘肃年鉴(2019)[M].兰州:甘肃民族出 版社,2019.[Office of Local Chronicles of Gansu Province.Gansu Yearbook 2O19[M]. Lanzhou: Gansu Nationalities Publishing House,2019.]   
[29]Mishra A K,Singh VP.A review of drought concepts[J].Journal of Hydrology,2010,391(1-2): 202-216.   
[30]Daryanto S,Wang L, JacinthePA.Global synthesis of drought effects on cereal,legume,tuber and root crops production:A review [J].Agricultural Water Management,2016,179:18-33.   
[31]余慧倩,张强,孙鹏,等.干旱强度及发生时间对华北平原五省 冬小麦产量影响[J].地理学报,2019,74(1):87-102.[Yu Huiqian,Zhang Qiang, Sun Peng,et al. Impacts of drought intensity and drought duration on winter wheat yield in five provinces of north China plain[J].Acta Geographica Sinica,2019,74(1): 87-102.]   
[32]Cakir R.Effect of water stress at different development stages on vegetative and reproductive growth of corn[J].Field Crops Research,2004,89(1): 1-16.   
[33]Wang S,Mo X,Liu S,etal.Validation and trend analysis of ECV soil moisture data on cropland in North China Plain during 1981- 2010[J].International Journal of Applied Earth Observation and Geoinformation, 2015,48:110-121.   
[34]Anyamba A,Tucker C J.Historical perspectives on AVHRR NDVI and vegetation drought monitoring[J].NASA Publications, 2012,217. http://digitalcommons.unl.edu/nasapub/217.   
[35]Loon A V,Laaha G.Hydrological drought severity explained by climate and catchment characteristics[J].Journal of Hydrology, 2015,526:3-14.

# Development and application of the temperature soil moisture precipitation drought index (TMPDI) based on multi-source remote sensing data

MAN Yuanwei， LI Jing, XING Liting (College of GeographyandEnvironmental Science,NorthwestNormal University,Lanzhou 73o070,Gansu,China)

Abstract: Drought has a profound social and economic impact on the whole world.Reliable drought monitoring is of grat significance to drought prevention and drought relief.In the areas with low vegetation coverage and crop planting rate,the accuracy of using vegetation status or single factor for drought monitoring is low,based on the simple and objective Euclidean distance method in three-dimensional Euclidean geometry space,a new drought index,temperature soil moisture precipitation drought index (TMPDI)，wasconstructed for drought monitoring.Taking Gansu Provinceas the research area,the TMPDI was verified by using SPI, SPEI,other remote sensing data and wheat yield per unit area.The results showed that: TMPDI was highly correlated with SPI and SPEI( $R ^ { 2 } { > } 0 . 6 4 )$ ，which reduced the uncertainty of drought monitoring using precipitation or surface temperature,improved the accuracy and effectiveness of soil moisture in agricultural drought monitoring,and accurately describe the temporal and spatial evolution characteristics of drought events.At the same time,it can also better reflect the impact of drought intensity and drought area rates on wheat yield,which proves that TMPDI its high effectiveness and reliability in agricultural drought monitoring.

Keywords: drought index; drought monitoring; remote sensing; MODIS； TRMM; GLEAM