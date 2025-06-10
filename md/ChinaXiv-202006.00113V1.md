# 叶尔羌河流域土地生态脆弱性差异评价

乌宁巴特，刘新平，马相平(1新疆农业大学管理学院,新疆乌鲁木齐830052)

摘要：综合评估叶尔羌河流域土地生态脆弱性，为流域重点治理、恢复绿洲生机提供决策依据和理论支持。以叶尔羌河流域作为研究区,获取2008—2018年各时期不同指标层数据，利用ArcGIS10.5 的栅格计算功能与自然间断分类法,综合计算研究区生态脆弱性指数，并将其划分为5种脆弱等级并表征其时空分布。结果表明：在空间分布上，研究区以微度、轻度脆弱区为主，面积占比分别为 $3 5 . 6 7 \% . 3 3 . 6 3 \%$ ，主要分布在叶尔羌河中下游冲积扇平原；中、重度脆弱区比重次之，分别占比为 $1 4 . 8 9 \%$ $. 1 2 . 9 3 \%$ ，主要分布在叶尔羌河上游山地丘陵区；极度脆弱区面积占比最小，仅为2.$89 \%$ ，但面积亦有 $3 ~ 0 0 0 ~ \mathrm { k m } ^ { 2 }$ ，主要分布在叶尔羌河中下游人口密集区，对流域整体生态环境起着“木桶效应”。局部地区生态环境持续恶化，致使流域整体生态压力与生态“阈值”的平衡受到影响。在时间分布上,2008—2011年整体评价指数下降0.04324,2010—2014年整体评价指数下降0.00541,2014—2018年整体评价指数下降0.05686。虽然各时期土地生态脆弱指数不同程度降低,流域整体生态环境呈改善趋势，但中、重、极度脆弱区依旧分布广泛，亟需研究其分布规律，针对不同脆弱区提出具体调控对策。

# 关键 词：土地生态脆弱性；SRP 模型；叶尔羌河流域文章编号

生态脆弱性研究是全球环境变化与可持续发展研究的核心问题之一，它是生态系统在面对外部时空下的扰动所表现出来的自我恢复能力以及反应状态,是系统本身固有的内部自然属性[1]。20 世纪中期后，随着人口急剧增长和经济快速发展，人类过度与无序的对生态资源进行开发和利用，导致生态系统退化、能源短缺、土地荒漠化等一系列生态环境问题不断涌现[2]。伴随十九大报告生态文明建设三个创新的提出，人们对环境资源保护的意识更加强烈，开展生态环境脆弱性变化研究是社会经济发展与生态文明建设的迫切需求。由于，我国因地域辽阔，地形复杂多样，加之气候交替分布，导致我国是生态脆弱性表现最为显著的国家[3]。通过区域生态环境脆弱性评价研究，从宏观上了解区域脆弱性的现状和分布特征、揭示其时空分异的成因，对制定区域可持续发展规划具有十分重要的现实意义[4-5]。目前,国内外学者在土地生态脆弱性研究中多以矿业城市、喀斯特区域、高原区域等生态脆弱带作为对象，对涉及小流域单元及湿地生态系统的研究较为缺乏。主要评价方法包括综合指数法[6-7]、灰色关联度分析法[8]、景观生态学模型[9-10]、物元可拓模型[11]、集对分析法[12]等,但受限于评价对象存在差异，导致选取指标时侧重点不同,影响其学术统一认知。SRP模型作为研究者普遍认为能涵盖所有内容的评价模型，经过不断反复应用，该模型也趋于完善。

叶尔羌河是塔里木河的重要源流之一。该流域主要以农业经济为主，由于其光热条件充沛，自20世纪60年代开始，农业灌区面积快速扩大，生产用水增加导致下游末端几乎无水汇入塔里木河。因此叶河流域的生态状况不仅决定了本流域可持续发展水平，同时也影响塔河流域绿洲的生态安全。本文采用 SRP综合评价模型[13],并选取能表现生态脆弱性的13个变量来构建生态脆弱性评价体系，结合层次分析法[14-15]确定各指标权重,运用GIS 技术表征脆弱程度的时空差异[16],揭示其特征以及演化规律，旨在为叶河流域生态系统综合调控提出对策建议。

# 研究区概况与研究

# 1.1 研究区概况

叶尔羌河(以下简称“叶河”)流域位于新疆维吾尔自治区的西南部，塔里木盆地的西南面。由于流域绿洲裹夹在塔克拉玛干、布古里、托格拉克沙漠之间，年均大风及沙尘暴日数32d,冲积扇平原蒸发强烈，喀喇昆仑山作为屏障挡住暖湿气流，使得水汽资源极其贫乏，年均降水仅为 $6 1 . 5 \ \mathrm { m m }$ ，年均气温$1 2 \ \mathrm { { ^ circ C } }$ ,常年日照时数为 $2 ~ 8 0 0 ~ \mathrm { h }$ ,从而形成典型的干旱大陆性气候。叶河径流主要以冰雪融水补给为主，加之特定的气象条件，使叶河具有明显的丰枯规律，夏季常有融雪突发性洪水灾害发生，冬季常为枯水期，年内径流分布不均。受气候与地形影响，山区冰雪融水是干旱平原区唯一的水资源补给。随着绿洲人口不断增加，非法采砂挖玉活动频繁出现，流域农业灌区持续扩展，水土资源配置错位，下游生态用水不断被农业用水大量挤占，导致卜游植物覆盖度降低，荒漠面积不断增加，使得原本先天脆弱的流域生态环境日趋恶劣[17]。因此,研究流域生态脆弱性，对于开展区域生态空间用途管制、合理开发利用水土资源及区域可持续发展具有重要意义。

# 1.2 评价方法

1.2.1 SRP 模 型SRP 模型(sensitivity-resilience-pressure,SRP)全称为生态敏感性一生态恢复力一生态压力度模型，是典型生态脆弱性评价模型，已在渤海地区[18]、渭干河[19]、白龙江[20]等流域得到广泛应用[2I],能较全面、客观的展现研究区生态脆弱性的演化规律，该评价模型原理是鉴于某项封闭系统受到外部因素干扰所展现出的敏感性，但其内部因缺失部分功能造成系统发生不同程度改变，从而呈现出当系统面临外界干扰时逆向发展的恢复力[22]。本文选取13个变量[23-25]作为评价因子，各因子权重采用层次分析法确定，并运用yaahp软件进行一致性检验，进而得到最终结果，具体因子选取情况及权重见表1。

1.2.2指标标准化由于各个评价因子数据量纲存在差，故采用极差标准化方法对数据进行标准化

# 表1叶尔羌河土地生态脆弱性评价指标

Tab.1Evaluation index of ecological vulnerability of in Yarkant River land   

<html><body><table><tr><td>目标层</td><td>准则层</td><td>要素层</td><td>指标层(权重)</td></tr><tr><td>基于 SRP 的生 态脆</td><td>生态压力度A1</td><td>人口活动压力 因子B1 社会环境压力</td><td>人口密度 C1(0.113 96) GDP密度</td></tr><tr><td>弱性 评价</td><td>生态敏感性A2</td><td>因子B2 地形因子B3</td><td>C2(0.269 13) 坡度 C3(0.013 65)</td></tr><tr><td></td><td></td><td>地表因子B4</td><td>坡向 C4(0.013 65) 高程 C5(0.018 2)</td></tr><tr><td></td><td></td><td>气象因子B5</td><td>植物覆盖度 C6(0.0462) 年降水量 C7(0.007 57) 年均气温</td></tr><tr><td></td><td></td><td>土壤因子 B6</td><td>C8(0.007 57) 年均相对湿度 C9(0.007 57) 土壤侵蚀强度</td></tr><tr><td></td><td>生态恢复力 A3</td><td>功能B7</td><td>C10(0.120 75) 居民点干扰 C11(0.152 98)</td></tr><tr><td></td><td></td><td>景观结构B8</td><td>景观多样性指数</td></tr><tr><td></td><td></td><td>活力B9</td><td>C12(0.075 7) 生物丰度 C13(0.152 98)</td></tr></table></body></html>

处理。正向关系为评价因子指数越大，脆弱度越大；  
逆向关系为评价因子指数越大，脆弱度越小。

正向关系： $X _ { i } ^ { ' } = \frac { X _ { i } - X _ { \operatorname* { m i n } } } { X _ { \operatorname* { m a x } } - X _ { \operatorname* { m i n } } }$

式中： $X _ { i } ^ { ' }$ 为第 $i$ 个指标的标准化值； $X _ { i }$ 为第 $\mathbf { \chi } _ { i }$ 个指标的原始数据； $X _ { \mathrm { m a x } }$ 为第 $i$ 个指标的最大值； $X _ { \mathrm { m i n } }$ 为第 $\mathbf { \chi } _ { i }$ 个指标的最小值。

1.2.3评价单元的确定行政单元有利于评价数据获取，而栅格评价可以将地理空间数据精准代入到相应的点格，如高程、坡度、坡向等，相较于传统行政单元评价更加客观真实。在本研究中，因流域面积广阔，近 $1 1 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 的研究区采用分辨率( $2 ~ \mathrm { k m }$ $\times 2 \ \mathrm { k m } ,$ )网格可以满足基本评价分析单元所需要的精度，并以行政区作为综合评价分析单元。

生态脆弱性评价公式如下：

本文在ArcGIS10.5中进行相应指标层的叠加计算，得到相应栅格的环境脆弱指数Eeui，最后运用自然间断法分类出不同脆弱等级，从而衡量对应评价单元的生态脆弱情况。生态脆弱指数的计算方法：

$$
E e v i = \sum _ { i = 1 } ^ { n } { { { F } _ { i } } \times { { W } _ { i } } }
$$

式中： $E e v i$ 为生态脆弱性指数，数值越大，脆弱性程度越低， $E e v i$ 取值范围为 $( 0 \sim 1 ) ; F _ { i }$ 为第 $i$ 个指标指数； $\textstyle \mathbf { \big | } \mathbf { \big | } _ { \mathit { \Pi } _ { i } }$ 为第 $i$ 个指标对应权重。

(1)生态压力度因子计算：人口密度 $\mathbf { \sigma } = \mathbf { \sigma }$ 县总人口/县域面积GDP密度 $\mathbf { \Sigma } = \mathbf { \Sigma }$ 县国民生产总值/县域面积(2)生态敏感性因子计算：

地形因子中所需要的高程、坡度、坡向等数据，均来自比例尺为1:50000的新疆DEM数据，借助ArcGIS 的空间分析功能完成提取[26],年降水量、年均气温、相对湿度数据采用51814（叶城）、51716（巴楚）、51804（塔什库尔干）、51811（莎车）以及51815(泽普)5个气象站点观测值。

$\textcircled{1}$ 地表植物覆盖度：采用不同年度的归一化(NDVI)指数计算。

$$
F = { \frac { N D V I - N D V I _ { \operatorname* { m i n } } } { N D V I _ { \operatorname* { m a x } } - N D V I _ { \operatorname* { m i n } } } }
$$

式中： $F$ 为地表植物覆盖度； $N D V I _ { \operatorname* { m i n } } \setminus N D V I _ { \operatorname* { m a x } }$ 分别为当年份归一化指数的最小值与最大值。中国科学院数据云提供分辨率为 $2 5 0 \mathrm { ~ m ~ } , 2 0 0 8 { - 2 0 1 8 }$ 年四期的遥感影像，数据由HDF格式转化为TIFF格式，并通过有相同地理坐标系统的叶河流域范围对其进行裁剪，得到研究区NDVI数据。

$\textcircled{2}$ 土壤侵蚀强度采用土壤流失方程（RUSLE），具体为：

$$
A = R \cdot K \cdot L S \cdot C \cdot P
$$

式中： $R$ 为降雨侵蚀力因子； $K$ 为土壤可蚀因子; $L S$ 为坡度坡长因子； $C$ 为植物覆盖度因子； $P$ 为水土保持措施因子。

本文降雨侵蚀力因子 $R$ 采用降雨量计算：

$$
R = \sum _ { \mathrm { i } = 1 } ^ { 1 2 } 1 . 7 3 5 \times 1 0 ^ { \big [ \big ( 1 . 5 \times \mathrm { l g } \frac { P _ { \mathit { i } } ^ { 2 } } { P } \big ) ^ { - 0 . 8 1 8 8 } \big ] }
$$

式中： $\boldsymbol { P } _ { i }$ 为月降雨量; $P$ 为年降雨量。 $R$ 因子栅格图的计算方法是：计算气象站点 $R$ 值，采用逆距离加权插值。

土壤可蚀性因子是土壤面对侵蚀的敏感程度[27],具体计算模型如下：

$$
K _ { _ { E P I C } } = \left\{ 0 . 2 + 0 . 3 \exp \left[ 0 . 0 2 5 ~ 6 S _ { _ { S A N } } \left( 1 - { \frac { S _ { _ { S I L } } } { 1 0 0 } } \right) ~ \right] ~ \right\} ~ .
$$

$$
\left( \frac { S _ { _ { S A N } } } { C _ { _ { C L A } } + A _ { _ { A I L } } } \right) ^ { 0 . 3 } \left( 1 . \mathrm { 0 } - \frac { 0 . 2 5 C } { C + \exp ( 3 . 7 2 - 2 . 9 5 C ) } \right) \ .
$$

$$
\left( 1 . \ 0 - { \frac { 0 . 7 S _ { s \scriptscriptstyle N } 1 } { S _ { s \scriptscriptstyle N } 1 } } \ + \exp \big ( \ - 5 . \ 5 1 + 2 2 . \ 9 S _ { s \scriptscriptstyle N } 1 \big ) \ \right)
$$

$$
K = - 0 . 0 1 3 ~ 4 + 0 . 5 1 6 K _ { E P I C }
$$

式： $S _ { S A N }$ 为砂砾含量 $( \% ) { : } S _ { s I L }$ 为粉砂含量 $( \% ) { : } C _ { c L A }$ 为黏粒含量 $( \% ) { : } C$ 为有机碳含量 $( \% )$ · ${ \cal S } _ { S N } = 1 -$ $S _ { S A N } / 1 0 0$ 。土壤可蚀性 $K$ 因子采用 $1 : 1 0 \ 0 0 0 \ 0 0 0$ 土壤数据，可以涵盖土壤类型、土壤各物质含量等各种属性。

$$
L S = \left( { \frac { \lambda } { 2 2 . 1 } } \right) ^ { m } \cdot ( 6 5 . 4 1 \cdot \sin ^ { 2 } \gamma +
$$

$$
4 . 5 6 \cdot \mathrm { s i n } \gamma + 0 . 0 6 5 )
$$

式中： $L S$ 为坡度坡长因子； $\lambda$ 为坡长； $\gamma$ 为坡度; $m$ 为随坡度变化的量当 $\gamma \equiv 2 . 8 6$ °时， $m$ 为0.5;1. 72$\leq \gamma < 2 . 8 6$ 时， $m$ 为 $0 . 4 ; 0 . 5 7 \overset { \circ } {  } \gamma < 1 . 7 2$ °时，$m$ 为 $0 . 3 ; \gamma < 0 . 5 7$ °时， $m$ 为0.2。

$C$ 因子为植物覆盖程度对水土流失的抑制程度。本文选用蔡森法建立的相关公式计算因子值。公式如下：

$$
C = \left\{ \begin{array} { c c } { 1 } & { c = 0 } \\ { 0 . 6 5 0 \ 8 \ - 0 . 3 4 3 \ 6 l g c { 0 } < c \leqslant 7 8 . 3 \% } \\ { 0 } & { c > 7 8 . 3 \% } \end{array} \right.
$$

式中： $c$ 代表植被覆盖度。

水土方面的保持措施 $P$ 因子表达相应土壤流失量的比值，取值范围在 $0 \sim 1$ 之间。每一类型土地的 $P$ 因子值不尽相同，不同土地类型与对应的 $P$ 值如表2所示。

(3)生态恢复力因子计算

$\textcircled{1}$ 景观多样性指数主要体现不同景观数目和相应比例，即表达景观复杂性。公式如下：

$$
C = - \sum _ { i = 1 } ^ { n } ( P _ { i } \times \mathrm { l n } P _ { i }
$$

式中： $n$ 为景观类型数； $\boldsymbol { P } _ { i }$ 为 $\mathbf { \chi } _ { i }$ 类景观所占面积比。

Tab.2Relationship between land type and $P$ value   

<html><body><table><tr><td>土地 类型</td><td>耕地</td><td>林地</td><td>草地</td><td>住宅 用地</td><td>水域</td><td>内陆 滩涂</td><td>工矿仓 储用地</td><td>公路 用地</td></tr><tr><td>P</td><td>0.5</td><td>1</td><td>1</td><td>0</td><td>0</td><td>1</td><td>1</td><td>0</td></tr></table></body></html>

$\textcircled{2}$ 居民点干扰：将研究区土地利用数据进行二级分类,提取城镇、乡村居民用地，转为栅格数据乘以权重代入生态脆弱性指数计算公式计算。

$\textcircled{3}$ 生物丰度是衡量区域生物种类丰富的指标，  
表征其生态环境优劣程度，公式如下：  
丰度指数 ${ \bf \pi } = ( 0 . 1 1 \times$ 耕地面积 $+ 0 . 3 5 \times$ 林地面积 $^ +$ $0 . 2 1 \times$ 草地面积 $+ 0 . 2 8 \times$ 水域面积 $^ +$ $0 . 0 4 \times$ 建设用地 $+ 0 . 0 1 \times$ 未利用地)/区域面积。

# 2 结果分析

# 2.1流域生态脆弱性判断标准及结果

依据叶河流域生态环境特征选取13个评价因子，结合研究区4个时期的基础数据，将叶河流域不同时期评价结果通过ArcGIS10.2中naturalbreaks（自然间断法)进行划分，此方法是一种地图分级算法，可利用数据具有断点这一特性进行分级聚类。具体脆弱程度划分结果见表3。为各时期评价变化结果能更直观的展现，本文选用加权平均法计算各时点整体脆弱程度平均值。不同时期生态脆弱程度分布见图1，面积占比见表4。

# 2.2流域生态脆弱性时间变化特征

从流域角度来看，2008—2018年叶河流域土地生态脆弱程度总体呈改善趋势，重、极度脆弱区面积较2008 年下降 $3 8 6 . 5 1 ~ \mathrm { k m } ^ { 2 }$ 。其中 2014—2018 年改

# 表3自然间断法确定脆弱程度

表2土地类型与 $P$ 值的关系表  
Tab.3Determination of the degree of vulnerability by the method of natural discontinuity   

<html><body><table><tr><td>生态环境脆弱性程度</td><td>生态环境脆弱性指数(Eevi)</td></tr><tr><td>微度脆弱区</td><td><0.38</td></tr><tr><td>轻度脆弱区</td><td>0.38~0.44</td></tr><tr><td>中度脆弱区</td><td>0.45~0.50</td></tr><tr><td>重度脆弱区</td><td>0.51~0.57</td></tr><tr><td>极度脆弱区</td><td>>0.57</td></tr></table></body></html>

74°E 76°E 78E 80°E 74°E 76E 78E 80°E  
NOv (a)2008年 NoO (b)2011年NA 图木舒克市阿瓦提县 NOv NA 图木舒克市阿瓦提县 NoOv巴楚县 巴楚县莎车具麦盖提县 莎车县麦盖提县  
N88 圣普 N88 泽图例 图例塔克尔县 T 微度脆弱区 N88 塔 什库尔干 微度脆弱区 N.88开 轻度脆弱区 塔吉克自治县 轻度脆弱区叶城县 中度脆弱区 叶城县 中度脆弱区重度脆弱区 重度脆弱区1极度脆弱区 极度脆弱区  
N98 0 60120 240 360 480 N N.98 0 60120 240 360 480 N⊥ km 3 km 874°E 76°E 78E 80°E 74°E 76E 78°E 80°E74°E 76°E 78E 80°E 74°E 76°E 78E 80°E  
N0v (c)2014年 No0V (d)2018年N 图 克市阿瓦提县 N0 N 图木舒克市阿瓦提县 NOA 巴楚县 A 巴楚县麦盖提县 麦盖提县莎车县 莎车县泽普县 泽普县  
N88 县 图例微度脆弱区 N88 N88 技 图例微度脆弱区 N88叶城县 轻度脆弱区 叶城县 轻度脆弱区中度脆弱区 中度脆弱区重度脆弱区 重度脆弱区极度脆弱区 极度脆弱区  
N98 0 60120 240 360 480 N N.98 0 60120 240 360 480 Nkm km 874°E 76°E 78E 80°E 74°E 76°E 78E 80°E

表4各时期脆弱区面积与比重表  
Tab.4Area and proportion of vulnerable areas in various periods   

<html><body><table><tr><td>脆弱程度(脆弱性指数)</td><td>指标</td><td>2008年</td><td>2011年</td><td>2014年</td><td>2018年</td></tr><tr><td>微度脆弱区</td><td>面积／km²</td><td>33 430.50</td><td>32 462.03</td><td>35 742.50</td><td>36 877. 85</td></tr><tr><td rowspan="2">轻度脆弱区</td><td>占比／%</td><td>32.33</td><td>31.40</td><td>34.57</td><td>35.67</td></tr><tr><td>面积／km²</td><td>31 690.48</td><td>36 420.26</td><td>31 831.85</td><td>34 766.94</td></tr><tr><td rowspan="2">中度脆弱区</td><td>占比／%</td><td>30.65</td><td>35.23</td><td>30.79</td><td>33.63</td></tr><tr><td>面积／km²</td><td>21 536.00</td><td>19 359.00</td><td>19 082.29</td><td>15 398.71</td></tr><tr><td rowspan="2">重度脆弱区</td><td>占比／%</td><td>20.83</td><td>18.72</td><td>18.46</td><td>14.89</td></tr><tr><td>面积／km²</td><td>13 198.65</td><td>11 708.01</td><td>13 464.41</td><td>13 363.49</td></tr><tr><td rowspan="2">极度脆弱区</td><td>占比／%</td><td>12.77</td><td>11.32</td><td>13.02</td><td>12.93</td></tr><tr><td>面积／km²</td><td>3 536.89</td><td>3 443.21</td><td>3 271.49</td><td>2 985.55</td></tr><tr><td></td><td>占比／%</td><td>3.42</td><td>3.33</td><td>3.16</td><td>2.89</td></tr><tr><td>加权平均数</td><td>二</td><td>2.242 89</td><td>2.199 65</td><td>2.194 24</td><td>2.137 38</td></tr></table></body></html>

![](images/f505dab09c06c3758a32e749f4830b7e6f421456cc60dd9a2a5030a6bf969da6.jpg)  
图2县级评价单元各时期评价结果  
Fig.2County-level evaluation unit evaluation results in each period

善趋势最大，中度、重度、极度脆弱区由2014 年的$1 8 . 4 6 \%$ 、13. $02 \%$ 、3. $1 6 \%$ 分别下降至2018年的$1 4 . 8 9 \%$ 、12. $9 3 \%$ 、2. $89 \%$ ；微度、轻度脆弱区由2014年的 $3 4 . \ 5 7 \% , 3 0 . \ 7 9 \%$ 提升至2018年的$3 5 . 6 7 \%$ 、33. $6 3 \%$ ;2011—2014年总体呈显缓慢改善趋势，2008年微度、中度、重度、极度脆弱区由$3 2 . 3 3 \% . 2 0 . 8 3 \% . 1 2 . 7 7 \% . 3 . 4 2 \%$ 分别下降至

2011年的 $3 1 . 4 0 \% 1 8 . 7 2 \% 1 1 . 3 2 \% 3 . 3 3 \%$ ，轻度脆弱区由 $3 0 . 6 5 \%$ 提升至 $3 5 . 2 3 \%$ 。通过加权平均数计算，发现2008一2011年总体指数减少0.04324、2011—2014年整体指数仅减少0.00541、2014—2018年整体指数减少0.05686。

无论从脆弱区面积变化亦或加权平均数变化来看，流域整体土地生态环境得到进一步改善，一定程度上源于国家塔里木河综合治理工程与喀什地区援疆工作的开展。灌区节水、水库改造、河道治理等工程分批实施，致使流域地下水得以补给，慢慢恢复到植被正常生存的埋深水位。乔、灌、草面积渐渐扩张，“正向"影响了生物丰度、景观多样性、植物覆盖度等权重较高的评价指标值，拉低了部分地区生态脆弱性指数，使得流域整体环境压力得以缓解。

从县市角度来看，8个县级评价单元中，阿瓦提、叶城、麦盖提、巴楚县在2008一2018年生态脆弱等级发生不同程度降低。其中，巴楚县生态恢复程度最为明显，轻、微、中度脆弱区面积较2008年增加$1 ~ 0 2 0 . 8 6 ~ \mathrm { k m } ^ { 2 }$ 。主要得益于塔里木河生态恢复工程及流域水资源统一管控等措施，使得这4个县域平原区植物覆盖度、生物丰度提高，土壤侵蚀程度降低。而泽普、塔什库尔干、图木舒克市土地生态脆弱等级提升明显，尤其是塔什库尔干与图木舒克市环境恶化速度较为显著，其中，塔什库尔干因地处叶尔羌河上游，山地居多，本身生态环境属于脆弱区，生态恢复能力较平原区弱，极度脆弱面积较2008年增加 $9 2 . 5 1 ~ \mathrm { k m } ^ { 2 }$ 。图木舒克市随着经济快速发展,大型工厂进驻，城镇化率持续攀升，建设用地需求不断扩大，进而影响生物丰度等评价因素，生态压力远高于生态恢复能力，生态环境承载面临巨大压力。

# 2.3流域生态脆弱性空间差异

2.3.1微度、轻度脆弱区叶河流域以微度、轻度生态脆弱区为主，主要分布在研究区东部，冲积扇平原中下游流域，分别占研究区面积的 $3 5 . 6 7 \%$ 、$3 3 . 6 3 \%$ ，主导因素为土壤侵蚀程度、坡度、植物覆盖率。以种植农业为主的麦盖提、巴楚、阿瓦提县为主要分布区域,面积为 $4 0 \ 0 7 3 . 6 5 \ \mathrm { k m } ^ { 2 }$ 。由于冲积扇平原土壤主要以富铁土为主，土层深厚，光热条件充足,水资源丰富,耕地集中连片且平均坡度小于 $2 ^ { \circ }$ ，优异的光热条件使得此区域植被覆盖率高、植物种类丰富。并且人口密度与GDP密度相对较低，主要以第一产业为主，第二产业发展相对滞后，这些正向因子相互叠加作用使得生态脆弱程度低且呈良性循环。

2.3.2中度、重度脆弱区叶河流域中度、重度生态脆弱区分布在研究区西部，分别占流域面积的$1 4 . 8 9 \%$ 、 $. 1 2 . 9 3 \%$ ,主导因素为坡度、高程、土壤侵蚀

74°E 76°E 78°E 80°E 74°E 76E 78E 80°E  
No0V N(a)侵蚀程度 N 0 (b)高程归一化值 NON 图木舒克市 10 N 图木舒克市  
N68 A 阿瓦提县 N A 阿瓦提县县 麦盖提县 巴楚县 3 N 68 莎车县麦盖提县 巴楚县 N 168  
N88 普县 N 泽普县  
N 克 0-0 0.2\~0.30.7\~0.8 N.88 N 37 88N 0 0.2\~0.30.7\~0.8 8.88 N0.3\~0.40.8\~0.9 5 0.3\~0.40.8\~0.9 3  
N 0.4\~0.5 0.9\~1 N 0.4\~0.5 0.9\~1  
3 0 60120240 360480 N 3 060120 240 360480 Nkm 3 kmL 上74°E 76°E 78E 80°E 74°E 76°E 78E 80°E74°E 76°E 78E 80°E 74°E 76°E 78°E 80°E  
N0 (c)坡度归一化值 图木舒克市 NOV NoO (d)坡向归一化值 N00  
N68 A 阿瓦提县 N A 图木舒克市阿瓦提县莎车县麦盖提县 巴楚县 N.68 68 麦盖提县巴楚县 N68  
8888 N88N 288 E N8N  
N.98 0.4\~0.50.9-0.9 3 N 0.3-0.40.9-0.9 5060120 240 360 480 N 3 0 60120240 360 480 Nkm 8 km 3上74°E 76°E 78E 80°E 74°E 76°E 78E 80°E74E 76°E 78°E 80°E 74°E 76E 78°E 80°E  
No00 N.68 (a)植物覆盖度 A A 图木舒克市阿瓦提县 NO N No0 (b)居民点干扰归一化值 A NO莎车真麦盖提县楚县 N.68 68 N.68  
N.88 泽普县 N88 图例荅什库尔干 图例 N 居民点、矿区点干扰 N  
N8 塔吉自治城县 818 88360 28 8 88828  
N ■0.4\~0.50.9\~1 N 0.4\~0.50.9\~1.0  
98 060120 240 360 480km N 98 060120240360480km N3 875°E 77°E 79°E 81°E 75E 77°E 79°E 81°E74°E 76°E 78°E 80°E 74°E 76°E 78E 80°E  
N N  
0 (c)年均降水归一化值 NOV 00 -(d)人口密度归一化值 NN N 图本舒克市阿瓦提县 0  
N A N68 A  
.68N N68 莎车县废盖提县 巴楚县 N68N 泽普县  
188 图例 N 88 塔什库尔干 N88年均降水归一化 88 塔吉克自治县 图例  
N 5 0.0\~0.10.5\~0.6 0.1\~0.2-0.6\~0.7 N 7 N 叶城县 人口密度归一化植 □0.0000002610.066443287 N■0.2\~0.3-0.7\~0.8 3 0.0012452600.096997 783 3  
N ■0.3\~0.40.8\~0.9 N 0.010 082 643 10.098 942 347  
3 0 00120 N.98 3 0.061460240360 480km N.9875°E 77°E 79°E 81°E 75°E 77°E 79°E 81°E

程度。其主要分布在研究区上游塔什库尔干县及莎车县的部分区域,面积为 $2 8 \ 7 6 2 . 2 \ \mathrm { k m } ^ { 2 }$ 。脆弱区以山地地形为主,平均海拔为 $2 0 0 0 \mathrm { ~ m ~ }$ ,是喀喇昆仑山、阿赖山脉、兴都库什山脉三山交汇处,气候为高原干旱一半干旱，常年干旱寒冷，只有个别地区涵盖原始森林，平原与山地交错，受到风的剥蚀作用，使得缺少植被的山区坡地土壤侵蚀程度明显高于冲积平原区域，加之人们盲目开荒，取柴毁林，导致生态系统抗干扰能力偏差，生态脆弱性偏高。

2.3.3极度脆弱区叶河流域极度生态脆弱区占流域面积的 $2 . 8 9 \%$ ，主导因素是年降水量、居民干扰点以及人口、经济密度。极度脆弱区虽然分布在叶尔羌河中下游的冲积扇平原上，但气候属于温带极干旱气候，土壤为新成土，有机质含量极低，使得植物覆盖度极低，加之泽普县与图木舒克市人口密度与GDP密度等人类经济活动密度远高于冲积扇平原其他县市，使得人地水三者资源错配，发展与环境之间矛盾尤为突出，过度挤占生态用水，使得沿径流中下游区域土壤侵蚀因子提高，NDVI指数下降，土地荒漠化与盐渍化程度日趋严峻，极端天气事件偏多，生态系统极度脆弱，甚至退化。虽然极度脆弱区在流域面积占比逐年减少，但脆弱表现在空间上呈聚集状态，例如极度脆弱区主要所分布的两个县市：泽普县与图木舒克市土地生态状态逐年退化，面积占比分别由2008年的 $8 6 . 4 4 \%$ 与 $8 7 . 1 2 \%$ 增长到2018年 $9 5 . 7 6 \%$ 与 $9 3 . 5 6 \%$ 。面积较2008 年增长$4 6 2 . 5 5 ~ \mathrm { k m } ^ { 2 }$ 。

# 3讨论

# 3.1提高生态保护意识，树立生态经济发展新理念

在生态系统较为稳定的轻、微度脆弱区以加强土壤盐渍化基础防治工作作为生态环境不恶化的重要保障。发展农业循环经济，通过政策引导与市场调节，使政府、企业、农户三大要素相互协调，为形成完整的功能性循环经济提供支撑，实现农业资源充分利用，生态环境与农业协调发展，农业经济与生态系统实现“双赢”。同时农村企业需及时更新基础设施以及生产工艺，尽快摆脱对化石能源的依赖，加快向低耗能产业的转型。其次，要实现“绿水青山就是金山银山”的生态经济发展理念，需要居民提高生态保护意识，强化生态教育，培养人民生态价值观，为全面构建和谐的人地关系提供良好动力。

# 3.2发展生态旅游产业，促进资源高效集约利用

在生态系统抗干扰能力较差的中、重度脆弱区以恢复地表荒漠植被与山区蓄水工程作为重点生态建设工程。可以起到防风固沙，降低土壤侵蚀程度的作用，并保证中下游径流流量稳定，减少极端水文情况造成的灾害发生。适当发展生态旅游产业，由传统粮食作物向外向型林果业转型，促进果园、农居等乡村质朴生态旅游资源的可持续发展，使得农户收入提高与生态环境改善相互促进，以摆脱种植农业对经济发展的带动能力不足问题。鼓励居民绿色生产消费，尽快加大乡村清洁能源的普及，解决农村能源污染问题。按照上、中、下游制定生活用水以及农用水不同阶梯费用标准，来推动节水灌溉技术的普及，调整种植作物结构，以减轻流域灌区的次生盐渍化程度，同时缓解水土流失带来地力下降与土壤侵蚀的问题。并实施小流域综合治理为核心，合理开发与统一利用水资源。

# 3.3严格自然生态空间用途管制，部分区域实行生态移民

极度脆弱区通常难以应对人类生产活动扰动带来的自然灾害，如图木舒克市与泽普县经常遭受沙尘暴袭扰造成巨大经济损失。结合本次脆弱性评价结果，依据国土空间规划框架，严格划定生态空间与城镇空间的界限，限制新增建设用地、过度采水、过度垦殖带来的生态功能损坏。对于局部生态功能丧失区域，可以将生态移民作为调节人与生态环境关系的最后措施，可以在一定程度上缓解迁出地的人地矛盾，恢复、重建和保护当地土地生态系统，

# 4结论

（1）研究区从时间维度上表现为：微、轻度脆弱区面积占比较研究初期上升 $6 . 3 \%$ ;中度脆弱区面积占比较研究初期下降 $2 . 8 3 \%$ ;重、极度脆弱区面积占比较研究初期上升 $1 . 1 6 \%$ 。叶河平原绿洲在2008一2016年总体环境状态呈现改善趋势。这与麦丽开·艾麦提的研究结果相似。

（2）研究区从空间维度上表现为：微、轻度脆弱区主要分布在研究区的东部，冲积扇平原的中下游流域，分别占研究区面积 $3 5 . 6 7 \% . 3 3 . 6 3 \%$ ;中度、重度生态脆弱区分布在以山地为主的西部，分别占研究区面积 $1 4 . 8 9 \%$ ） $1 2 . 9 3 \%$ ;极度脆弱区集中分布在泽普县与图木舒克市域内，占研究区面积$2 . 8 9 \%$ 。可知此分布规律与地形因子或人口活动强度有着密切关系，这与李晓蕾的研究结论相印证。

本次评价研究参照了蔡海生所构建的动态评价指标体系，能客观反映人类活动于自然自身属性的相互作用对生态脆弱性带来的影响。但本次所有选取的评价指标是否能全面的反映生态环境状态需要进一步考证。其次，由于部分评价指标数据的获取来源于地区、县级统计年鉴，导致评价结果不可避免的受行政区界的影响，加之5个气象站点数据对面积较大的研究区数据支撑略显不足，因此，下一步研究要尽量加大指标数据获取力度。后期将动态综合评价与预警监测于一体来做深入研究。

# 参考文献(References）

[1］赵桂久,刘燕华,赵名茶.生态环境综合整治与恢复技术研究 [M].北京：科学技术出版社,1995:47-80.［ZHAOGuijiu,LIU Yanhua,ZhAO Mingcha.Research on comprehensive improvement and restoration technology of ecological environment[M].Beijing : Science and Technology Press,1995:47 -80.]   
[2]赵跃龙,张玲娟.脆弱生态环境定量评价方法的研究[J].地理 科学,1998,7（1）:73-78.[ZHAO Yuelong,ZHANG Lingjuan. Study on quantitative evaluation method of fragile ecological environment[J].Geographic Science,1998,7(1) :73-78.]   
[3]杨勤业,张镜锂,李国栋.中国的环境脆弱形势和危急区域 [J].地理研究,1992,11(4）:1-9.[YANGQinye,ZHANG Yili,LI Guodong. China's environmentally fragile situation and critical areas[J].Geographic Research,1992,11(4):1-9.]   
[4]钟晓娟，孙保平，赵岩,等.基于主成分分析的云南省生态脆弱 性评价［J].生态环境学报,2011,20（1）：109-113.［ZHONG Xiaojuan,SUN Baoping,ZHAO Yan,et al.Ecological vulnerability assessment of Yunnan province based on principal component analysis[J].Journal of Ecology and Environment,2011,20(1）:109 - 113.]   
[5］周嘉慧,黄晓霞．生态脆弱性评价方法评述[J].云南地理环 境研究,2008,20（1）:55-59,71.［ZHOUJiahui,HUANG Xiaoxia.Review on ecological vulnerability assessment methods[J]. Yunnan Geographical Environment Research,2008,20（1）:55- 59,71.]   
[6]YAN Feng,HE Daming.Transboundary water vulnerability and its drivers in China[J]. Journal of Geographical Sciences,2009,19 (2):189-199.   
[7]TURVEY R.Vulnerability assessment of developing countries:The case of small island developing states[J].Development Policy Review,2007,25(2) :243-264.

[8］何才华,熊康宁．贵州喀斯特生态环境脆弱性类型区及其开发治理研究[J].贵州师范大学学报，1996,14（1)：1-9.［HECaihua,XIONG Kangning.Guizhou karst ecological environmentvulnerability type area and its development and management[J].Journal of Guizhou Normal University,1996,14(1):1-9.]

[9]肖笃宁,李秀珍,高峻,等.景观生态学[M].北京;科学出版社,1990;141-156.[XIAO Duning,LI Xiuzhen,GAO Jun,et al.Landscape ecology[M].Beijing:Science Press,1990:141-156.][10］邱彭华，徐颂军，谢跟踪等.基于景观格局和生态敏感性的海南西部地区生态脆弱性分析[J].生态学报，2007，27（4)：1257-1264.[QIU Penghua,XU Songjun,XIE Genzong,et al.Analysisof ecological vulnerability in western Hainan based on landscapepattern and ecological sensitivity[J].Journal of Ecology,2O07,27(4):1257 -1264.]

[11］巫锡柱，晏路明.脆弱生态环境的综合评判物元模型研究[J].中国生态农业学报，2007，15（3）：138-141.［WUXizhu，YANLuming.Research on matter model of comprehensive evaluation offragile eco-environment[J].Chinese Journal of Eco-Agriculture,2007,15(3):138 -141.]

[12］陈群利，左太安，孟天友，等.基于SPA的毕节水土流失区生态 脆弱性评价[J].中国水土保持，2010，（12）：53-56.［CHEN Qunli,ZUO Taian,MENG Tianyou,etal.Evaluation of ecological vulnerability of Bijie soil and water loss area based on SPA[J]. China Soil and Water Conservation,2010,（12）:53-56.]

[13］乔青，高吉喜，王维.生态脆弱性综合评价方法与应用[J].环境科学研究,2008,21（5）：117-123.［QIAOQing,GAO Jixi,WANG Wei.Comprehensive evaluation method and application ofecological vulnerability［J].Environmental Science Research,2008,21(5):117-123.]

[14］韦晶，郭亚敏，孙林,等.三江源地区生态环境脆弱性评价[J].生态学杂志,2015,34（7）：1968-1975.[WEIJing，GUOYamin,SUNLin,et al.Evaluation of ecological environment vul-nerability in SanjiangyuanRegion[J]. Journal ofEcology,2015,34(7):1968 -1975.]

[15］HUANG Pi Hui,Tsai Jing Shyan,LIN Wen Tzu.Using multiplecriteria decision-making techniques for eco-environmental vulnerability assessment:A case study on the Chi-Jia-Wan Stream watershed,Taiwan[J].Environmental Monitoring and Assessment, 2010,168(1/4) :141 -158.

[16］Luis Martin Fernandez,Margarita Martinez Nunez.An empirical approach to estimate soil erosion risk in Spain[J].Science of the Total Environment,2011,（409）:3114-3123.

[17］陈钟望,杨汉波,陈东.叶尔羌河绿洲近20a来地下水埋深变 化及其原因分析[J].水力发电学报，2016,35（6）：58-66. [CHEN Zhongwang，YANG Hanbo,CHEN Dong.Analysisof groundwater depth change and its causes in the Yarkant River oasis in the past 2O Years[J]. Journal of Hydroelectric Engineering, 2016,35(6) :58 -66.]

[18］卢亚灵，颜磊，许学工.环渤海地区生态脆弱性评价及其空间自相关分析[J].资源科学，2010,32（2）：303-308.［LUYa-

ling,YAN Le1,XU Xuegong.Ecological vulnerability assessment and spatial autocorrelation analysis in the Bohai Rim Region[J]. Resource Science,2010,32(2）:303 -308.]   
[19］王雪梅,席瑞.基于GIS 的渭干河流域生态环境脆弱性评价 [J].生态科学,2016,35（4）:166-172.[WANG Xuemei,XI Rui.Evaluation of ecological environment vulnerability in the Weigan River basin based on GIS[J].Ecological Science,2016, 35(4) :166 -172.]   
[20］齐姗姗,巩杰,钱彩云,等.基于 SRP 模型的甘肃省白龙江流域 生态环境脆弱性评价[J].水土保持通报,2017,37（1）;224- 228.[QI Shanshan,GONG Jie,QIAN Caiyun,et al.Evaluation of ecological environment vulnerability in Bailong River basin of Gansu Province based on SRP model[J].Soil and Water Conservation Bulletin,2017,37(1） :224 -228.]   
[21]DE LA ROSA D,MORENO JA,MAYOL F,et al. Assessment of soil ero-sion vulnerability in western Europe and potential impact on crop productivity due to loss of soil depth using the Impel ERO model[J].Agriculture,Ecosystems and Environment,2Ooo,（81）: 179 - 190.   
[22]Rong hua Z,XIA L,GARY C H. Assessment of soil erosion sensitivity and analysis of factors in the Tongbai-Dabie mountainous area of China[J].Research Gate,2013,（101）:92-98.   
[23］裴欢,房世峰,覃志豪,等.干旱区绿洲生态脆弱性评价方法及 应用研究—以吐鲁番绿洲为例[J].武汉大学学报（信息科 学版）,2013,38(5）:528-532.[PEI Huan,FANG Shifeng,TAN Zhihao,et al.Evaluation method and application of oasis ecological vulnerability in arid area:Taking Turpan oasis as an example[J]. Journal of Wuhan University（Information Science Edition）,2013, 38(5) :528 -532.]   
[24］于伯华,吕昌河.青藏高原高寒区生态脆弱性评价[J].地理研 究,2011,30（12）:2289－2292.[YU Bohua,LU Changhe.Ecological vulnerability assessment of the alpine region in the QinghaiTibet Plateau[J].Geographic Research,2011,30（12）: 2289- 2292.]   
[25］田亚平,刘沛林,郑文武.南方丘陵区的生态脆弱度评估一 以衡阳盆地为例[J].地理研究,2005,24（6）:843－852. [TIAN Yaping,LIU Peilin,ZHENG Wenwu. Ecological vulnerability asessment in southern hilly areas: A case study of Hengyang basin[J]. Geographic Research,2005,24(6）:843 -852.]   
[26]JOSE M,RUIZ G,ESTELA N R,et al.Erosion in Mediterranean landscapes: Changesand future chalenges[J]. Geomorphology, 2013,(198) :20 -36.   
[27］周璟,张旭东,何丹,等.基于GIS与RUSLE 的武陵山区小流域 土壤侵蚀评价研究[J].长江流域资源与环境,2011,20（4）： 468-474.[ZHOU Jing,ZHANG Xudong,HE Dan,et al.Evaluation of soil erosion in small watershed of Wuling Mountain area based on GIS and RUSLE[J].Resources and Environment in the Yangtze River Basin,2011,20(4） :468 -474.]

# Evaluation on the difference of land ecological vulnerability in the Yarkant River Basin

WU Ningbart， LIU Xin-ping， MA Xiang-ping (School of Management,Xinjiang Agricultural University,Urumqi 83oo52,Xinjiang,China)

Abstract：Acomprehensiveevaluation of thecharacteristics of land ecological fragilityin the Yarkant River Basin,Xinjiang,China providesa decision-making basis and theoretical support for river basin key management and therestorationofoasis vitality.In this study,theYarkant River Basin is theresearch area.Byobtaining therelevant data of diffrent index layers in each period from 2O08 to 2O18,we used the grid computing function of ArcGIS10. 5andthe natural discontinuous clasification method to comprehensivelycalculate the ecological vulnerability index of the studyarea.Wedividedthe vulnerability into five levelsand presented its spatiotemporal distribution.Results showthat in the spatial distribution,thestudyareais dominated by microand lightly vulnerable areas,withan area ratio of $3 5 . 6 7 \%$ and $3 3 . 6 3 \%$ ,respectively,distributed in the alluvial fan plain in the middle and lower reaches of the Yarkant River.The proportion of moderately and severely vulnerable areas was secondary,accounting for 14. $89 \%$ and $1 2 . 9 3 \%$ ,respectively,distributed in the hilly areas of the upper reaches of the Yarkant River.Although the proportion of extremely vulnerable areas is only $2 . 8 9 \%$ ,which is $3 \ 0 0 0 \ \mathrm { k m } ^ { 2 }$ ,distributed in densely populated areas in the middleand lowerreaches ofthe YarkantRiver,it plays arole ofthecask efecton theoverall ecological environmentof the basin.The local ecological environment continues to deteriorate,resulting ina balance between theoverall ecological pressureof thebasinand theecological threshold.Regarding the time distribution,theoverall evaluation index decreasedby0.043 24 from 2008 to 2011,and the overall evaluation index decreased by0.005 41 from 2001 to2014.Theoverall evaluation index decreased by0.05686 from 2014 to 2018.Although the ecological vulnerability indexof each period decreased to varying degrees,the overall ecological environment of the basin improved.However,the moderately,heavily,and extremelyvulnerable areas are stillwidely distributed.Based on the representative SRP model and field survey,this study proposed some methods.In the micro and lightlyvulnerable areas,basic polution control is needed.In moderatelyand severely vulnerableareas,ecotourism should be developed,and food crops shouldbe converted to export-oriented forestryand fruit growing.The sustainable development of orchards,farmhouses,and other rural plain ecotourismresources should be promoted.In extremely vulnerable areas,strict control of space use and ecological immigration should be implemented.

Key words:land ecological vulnerability;SRP model; Yarkand River Basin