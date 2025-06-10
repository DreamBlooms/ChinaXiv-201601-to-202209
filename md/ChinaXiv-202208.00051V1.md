# 阿拉尔垦区土壤盐渍化遥感监测及时空特征分析

代云豪'，管瑶'，张钦凯¹，孙峻杰¹，贺兴宏¹2（1.塔里木大学水利与建筑工程学院，新疆 阿拉尔843300;2.塔里木大学南疆岩土工程研究中心,新疆 阿拉尔843000)

摘要：及时准确掌握区域土壤盐渍化信息对盐渍土治理和土地利用可持续发展有着重要意义。以阿拉尔垦区Landsat $7 \ \mathrm { E T M + } / 8$ OLI影像为数据源，采用盐分指数(Salinityindex,SI)和归一化植被指数（Normalized difference vegetation index,NDVI)构建遥感盐分监测指数（Salinization detection in-dex,SDI)模型,对阿拉尔垦区土壤盐渍化进行反演，分析近10a垦区土壤盐渍化空间分布特征。结果表明：SDI模型与土壤实测电导率拟合度 $R ^ { 2 } { = } 0 . 7 5 7 9$ ，该模型可反演阿拉尔垦区土壤盐量；2011—2021年非盐渍土和轻度盐渍土面积分别增加 $3 1 8 . 2 2 \mathrm { k m } ^ { 2 }$ 和 $0 . 8 0 \mathrm { k m } ^ { 2 }$ ，中度、重度土壤盐渍化面积减少 $2 2 9 . 8 7 \mathrm { k m } ^ { 2 }$ ,盐土面积增加 $6 8 . 6 1 \mathrm { k m } ^ { 2 }$ ;阿拉尔垦区北部和南部地区的土壤盐渍化程度得到明显转好，中部和东部地区土壤盐渍化程度加重，垦区土壤盐渍化总体得到较好改善。SDI模型能较好反演阿拉尔垦区土壤盐渍化时空特征，可为阿拉尔垦区经济与社会发展提供一定的参考依据。

关键词：土壤盐渍化；盐渍土；遥感盐分监测指数(SDI)模型；SI-NDVI；阿拉尔垦区

# 文章编号：

土壤盐渍化问题不仅影响区域农业经济发展，也会对该区域的生态环境造成严重威胁。利用科学的技术手段及时准确掌握土壤盐渍化信息和预防次生盐渍土，对区域发展有着现实的科学意义[2-3]。遥感技术从多光谱到高光谱，再到微波遥感的发展，一直是国内外学者的研究热点，遥感技术凭借快速、及时、准确、高效的优势被广泛应用于土壤盐渍化研究[4-7]。国外早期以土壤盐分敏感波段研究为主，Dwivedi等[8提出蓝波段、红波段、中红外波段合成影像获取盐渍土信息量最佳。21世纪后，土壤盐渍化研究不在仅限于敏感波段研究，通过构建相应参数或模型对土壤盐渍化进行定性、定量研究也成为当下热点。Sidike等9将归一化植被指数(Nor-malizeddifferencevegetation index,NDVI)、土壤亮度指数等作为参数应用于土壤盐分反演模型以提高反演精度。El-Horiny[10]研究了电导率与光谱指数的关系性，表明盐度指标(SI-1和SI-2)与电导率的相关性最高，模型对研究区的预测准确率为 $7 7 \%$ 。我国土壤盐渍化多发生在干旱、半干旱和滨海等区域,研究的热点区域主要位于河套灌区[1I-12]、黄河三角洲[13-15]、新疆维吾尔自治区[16-19]等地，目前通常采用土壤光谱特征或是通过间接特征(植被长势、土壤要素、土地覆被类型等)对其进行研究[20]。研究中，多光谱遥感中光谱指数方便且易获取，成为土壤盐渍化研究热点之一，常以NDVI、修改型土壤调整植被指数(Modified soil-adjusted vegetation index,MSAVI）、盐分指数(Salinityindex,SI)等建立二维特征空间和构建遥感盐分监测指数(Salinizationdetec-tionindex,SDI)模型，该方法反演研究区土壤盐分信息是土壤盐渍化遥感监测的一种先进方法[21-23]。卢晶等[24]采用MSAVI-SI特征空间并构建改进型盐碱化监测指数（Modified salinization detectionindex,MS-DI)模型反演河套灌区盐度，其精度可靠性较高；王飞等[25]采用NDVI-SI特征空间构建SDI模型能准确反演塔里木南缘于田绿洲土壤地表盐量。其中SDI模型由NDVI和SI构建，而应用二维特征空间理论来发展盐渍化遥感监测的定量方法和指标有巨大的潜力，利用植被指数与SI构建SDI模型能有效对土壤盐渍化进行反演[26-28]

阿拉尔垦区是受土壤盐渍化侵害的典型绿洲农田，土壤盐渍化分布较为广泛[29]。垦区作为新疆重要的粮棉产地和兵团向南发展的重要部署地，有着其重要的核心地位，但多年来局限于垦区棉田或部分试验田土壤盐渍化研究，系统研究整个阿拉尔垦区土壤盐渍化时空分布较少。因此，为进一步掌握垦区土壤盐渍化分布状况，提高土壤盐渍化精准治理与防治，本研究选取SI和NDVI建立二维特征空间并构建SDI模型，利用该模型对阿拉尔垦区土壤盐渍化进行反演，反演结果可作为垦区土壤盐渍化治理的一种参考，对促进经济与社会发展具有一定的现实意义。

# 1材料与方法

# 1.1 研究区概况

阿拉尔垦区位于新疆南部 $( 8 0 ^ { \circ } 3 0 ^ { \prime } { \sim } 8 1 ^ { \circ } 5 8 ^ { \prime } \mathrm { E }$ $4 0 ^ { \circ } 2 2 ^ { \prime } { \sim } 4 0 ^ { \circ } 5 7 ^ { \prime } \mathrm { N } \rangle$ ,属塔里木河冲积细土平原，气候条件干燥，生态环境脆弱，傍依塔里木河，地势由西北向东南倾斜。垦区辖七团、八团、九团、十团、十一团、十二团、十三团、十四团8个团场，拥有3个人工水库，包括多浪水库、胜利水库、上游水库。垦区总面积 $4 1 9 7 . 5 8 \mathrm { k m } ^ { 2 }$ ，海拔高度 $9 9 7 { \sim } 1 3 4 0 \mathrm { m }$ ,年降雨量稀少，地表蒸发强烈，年均气温 $4 { \sim } 2 0 \ \mathrm { ‰ }$ ,年均降水量$4 0 . 1 { \sim } 8 2 . 5 ~ \mathrm { m m }$ ,年均蒸发量 $1 8 7 6 . 6 { \sim } 2 5 5 8 . 9 ~ \mathrm { m m } ^ { [ 3 0 - 3 1 ] }$ O垦区种植农作物以棉花为主，林果则以红枣、核桃、香梨为主，农业灌水方式以冬春漫灌洗盐结合膜下滴灌为主(图1)。

# 1.2数据来源

影像数据来源于地理空间数据云(http://www.gscloud.cn）,筛选云量小于 $1 0 \%$ 的阿拉尔垦区2011年8月20日Landsat $^ { 7 } \mathrm { E T M ^ { + } }$ 和2021年9月8日Land-sat8OLI影像数据，影像数据像元为 $3 0 \mathrm { m } { \times } 3 0 \mathrm { m }$ ，影像行列号为146/32。

野外土壤样品主要采集 $0 { \sim } 1 0 ~ \mathrm { c m }$ 表层土壤，采集时间为2021年3月8—14日、2021年8月23日—9月3日，其中：2次土壤采样点分别为42个和97个，共计139个(图1)。采样点随机均匀分布于垦区七团至十四团内，满足均匀布设原则。采样点地物类型为垦区典型种植农作物(棉花样点69个、玉米样点2个、辣椒样点6个）林果(枣树样点42个、梨树样点8个、核桃树样点2个)和裸地(10个)。为减小单一样品的不确定性，每个样点根据三角形采样法[24]相距 $1 2 { \sim } 1 5 \mathrm { m }$ ,利用土钻采集3份样品各装入铝盒，利用GPS在三角形中点处测定样点坐标，野外数据共采集土壤样品417份。

# 1.3 研究方法

1.3.1 数据处理原始遥感影像经几何校正、辐射定标、大气校正等预处理工作，裁剪得到研究区影像，其中2011年影像数据条带丢失，为解决这一问题,采用ENVI5.3软件中landsat_gapfill插件处理[32]

![](images/f6cf793df01efd9462aa361330b94352720b7b70d3a6d6c424123f72226a459a.jpg)  
图1阿拉尔垦区概况及采样点分布  
Fig.1Overview and distribution of sampling points in Aral Reclamation Area

野外土壤样品称重后放入 $1 0 5 ~ \mathrm { { ^ circ C } }$ 烘箱烘干 $8 \mathrm { ~ h ~ }$ ，将同一采样点的3份样品均匀混合磨碎成为1份样品，剔除植物根系、石块等杂物后过 $2 \mathrm { m m }$ 筛。取土$2 0 \ \mathrm { g }$ ,蒸馏水 $1 0 0 ~ \mathrm { { m L } }$ 充分混合搅动后静置过滤，制备得到的滤液用上海科佑DDS-11A电导仪测定溶液电导率。

# 1.3.2遥感光谱指数

(1）归一化植被指数(NDVI)

尽管植被覆盖会改变土壤的光谱响应，但植被生长状况在很大程度上受到盐分的影响和控制，可很好的反应土壤盐渍化程度。选取NDVI作为反应土壤盐渍化信息间接指标，其植被长势情况与土壤盐渍化程度成反比，土壤盐渍化程度越重，植被长势将受到抑制[33]。

$$
\mathrm { N D V I } { = } \frac { \rho _ { \mathrm { { n i r } } } - \rho _ { \mathrm { { r e d } } } } { \rho _ { \mathrm { { n i r } } } + \rho _ { \mathrm { { r e d } } } }
$$

式中： $: \rho _ { \mathrm { r e d } } \sqrt { \rho _ { \mathrm { n i r } } }$ 分别为landsat $\mathrm { E T M + / O L I }$ 影像中的红光波段、近红外光波段。

(2）盐分指数(SI)

SI由蓝光波段和红光波段计算得到,Khan 等[34]研究发现多光谱遥感中的蓝、红光波段对土壤盐分较为敏感，利用SI能较好反演盐分程度。

$$
\mathrm { S I } = \sqrt { \rho _ { \mathrm { b l u e } } \times \rho _ { \mathrm { r e d } } }
$$

式中： $\rho _ { \mathrm { b l u e } }$ 为landsat $\mathrm { E T M + / O L I }$ 影像中的蓝光波段。

1.3.3掩膜处理阿拉尔垦区紧邻塔克拉玛干沙漠，垦区内有多浪水库、胜利水库、上游水库和塔里木河等水域，为避免水体和沙地对土壤盐渍化信息提取产生干扰影响，故利用SWIR波段、NDVI和湿度指数(Normalizeddifference moisture index,NDMI)对水体和无植被沙地进行掩膜并去除(图2)[24]。

$$
\mathrm { N D M I } = { \frac { \rho _ { \mathrm { _ { \mathrm { n i r } } } } - \rho _ { \mathrm { _ { \mathrm { s w i r } 1 } } } } { \rho _ { \mathrm { _ { \mathrm { n i r } } } } + \rho _ { \mathrm { _ { \mathrm { s w i r } 1 } } } } }
$$

式中： $\rho _ { \mathrm { s w i r 1 } }$ 为landsat $\mathrm { E T M + / O L I }$ 影像中的短波红外1波段。

1.3.4归一化处理由于各指数的量纲不同，建立的模型需消除各指数之间的差异，故对各指数归一化处理[25]。

$$
\mathrm { S I } = \frac { \mathrm { S I } - \mathrm { S I } _ { \operatorname* { m i n } } } { \mathrm { S I } _ { \operatorname* { m a x } } - \mathrm { S I } _ { \operatorname* { m i n } } }
$$

$$
\mathrm { N D V I } { = } \frac { \mathrm { N D V I - N D V I } _ { \mathrm { m i n } } } { \mathrm { N D V I } _ { \mathrm { m a x } } - \mathrm { N D V I } _ { \mathrm { m i n } } }
$$

式中： $\mathrm { S I } _ { \mathrm { m a x } } , \mathrm { S I } _ { \mathrm { m i n } }$ 分别为盐分指数的最大值和最小值;$\mathrm { N D V I \rvert _ { \operatorname* { m a x } } } \setminus \mathrm { N D V I \rvert _ { \operatorname* { m i n } } }$ 分别为归一化植被指数的最大值和最小值。

# 2结果与分析

# 2.1遥感盐分监测指数模型

以阿拉尔垦区2021年9月遥感影像数据计算的归一化SI为坐标纵轴，NDVI为坐标横轴建立SI-NDVI二维散点图[15（图3)，并计算二维散点的拟合度(表1)。由表1可知，所有模型拟合度 $R ^ { 2 }$ 均大于0.8600,适合构建SDI模型[25],并能在宏观尺度上反演阿拉尔垦区土壤盐渍化信息。SDI模型计算公式如下：

$$
\mathrm { S D I } = \sqrt { \mathrm { S I } ^ { 2 } + ( \mathrm { N D V I } - 1 ) ^ { 2 } }
$$

2.2阿拉尔垦区土壤盐渍化时空动态变化

2.2.1土壤盐分遥感监测指数模型精度分析通过测定139个野外土壤样点数据的电导率，并对SDI模型进行精度验证(图4)。野外实测土壤电导率与SDI模型之间的拟合度 $R ^ { 2 } { = } 0 . 7 5 7 9$ ，拟合效果较好，表明SDI模型可以对阿拉尔垦区较大范围的土壤盐渍化信息进行反演。

![](images/6badd25425d7a7aa413ebc951e28243c24cb92bc8aa04f33c1c7435850359d11.jpg)  
图2水体及无植被沙地提取  
Fig.2Extraction of water bodies and unvegetated sandy land

![](images/0b095f2fda8b5ccff1b79298de15e86d5f515845b8a0696bccbcc8f529c9f87a.jpg)  
Fig.3SI-NDVI scatter diagram

注：NDVI为归一化植被指数;SI为盐分指数。

Tab.1 Fitting of two-dimensional scatter model   

<html><body><table><tr><td>模型</td><td>公式</td><td>拟合度R</td></tr><tr><td>线性模型</td><td>y=0.2863-0.2832x</td><td>0.8677</td></tr><tr><td>二次模型</td><td>y=0.3163-0.4948x+0.2251x²</td><td>0.8867</td></tr><tr><td>指数模型</td><td>y=0.3488x0.1816-0.0239</td><td>0.8881</td></tr><tr><td>几何模型</td><td>y=-0.3565x0.4846+0.3842</td><td>0.8877</td></tr><tr><td>双曲模型</td><td>y=1.0/(2.5226+12.022x)</td><td>0.8609</td></tr><tr><td>对数平方模型</td><td>y=0.0334-0.3386logx-0.1013logx²</td><td>0.8886</td></tr></table></body></html>

注：y为归一化后的盐分指数； $x$ 为归一化植被指数。

为便捷、直观了解垦区土壤盐渍化程度，查阅南疆地区遥感盐渍土相关研究[23.35],参考王亲遵等[36]土壤盐渍化等级划分与土壤盐渍化等级标准所对应的土壤电导率值，利用SDI模型与实测电导率构建的数学关系模型对阿拉尔垦区土壤盐渍化进行等级划分(表2)。

2.2.2阿拉尔垦区土壤盐渍化空间分布按标准电导率对应的SDI模型对土壤盐渍化进行分级，得到阿拉尔垦区土壤盐渍化分布图(图5)，计算分析得到2011—2021年土壤盐渍化面积(表3)。2011年阿拉尔垦区的非盐渍土面积达到 $9 7 2 . 9 8 ~ \mathrm { k m } ^ { 2 }$ ，占垦区研究土壤面积的 $2 9 . 3 7 \%$ ，主要分布在垦区西部和东部地区；轻度盐渍土面积 $2 5 1 . 0 9 \mathrm { k m } ^ { 2 }$ ,主要分布在西北、东北和西部地区，其分布呈零散化；中度盐渍土主要在南部塔里木河河床、水库附近;重度盐渍土和盐土主要分布在垦区东北地区和东南地区。2021年阿拉尔垦区非盐渍土区域分布明显扩大，面积达到 $1 2 9 1 . 2 0 \mathrm { k m } ^ { 2 }$ ,其分布范围在垦区西部、北部和东部地区;轻度盐渍土主要分布在西部和北部地区;中度盐渍土主要在垦区中部地区和东北地区;重度盐渍土主要分布在垦区东北地区，东南地区重度盐渍土分布面积减小;盐土的分布同2011年大致相同。

![](images/5e098b7fbd25dddfedbde92519bdeb01665ae690c2049af8c2fe910b2eaf11f5.jpg)  
图4实测电导值与SDI模型精度验证 Fig.4Verification of measured conductivity value and SDI model accuracy

由表3可知,2011—2021年阿拉尔垦区土壤盐渍化分布中非盐渍土、轻度盐渍土、中度盐渍土、重度盐渍土、盐土面积分别呈“上升、上升、下降、下降、上升"趋势,垦区非盐渍土面积增加 $3 1 8 . 2 2 \mathrm { k m } ^ { 2 }$ 增幅达到 $3 2 . 7 0 \%$ ，主要增加面积位于垦区北部和东部地区。轻度盐渍土增加 $0 . 8 0 \mathrm { k m } ^ { 2 }$ ,变化极小，主要呈零散化分散在垦区内。中度盐渍土和重度盐渍土分别减少 $7 6 . 8 4 \mathrm { k m } ^ { 2 } , 1 5 3 . 0 3 \mathrm { k m } ^ { 2 }$ ，面积明显减少区域主要在垦区西南、西北和东南地区。盐土面积增加了 $6 8 . 6 1 \mathrm { ~ k m } ^ { 2 }$ ,增加区域位于垦区东北地区。

表1二维散点模型拟合性  
表2土壤盐渍化等级标准划分  
Tab.2 Classification of soil salinization grade   

<html><body><table><tr><td>指标</td><td>非盐渍土</td><td>轻度盐渍土</td><td>中度盐渍土</td><td>重度盐渍土</td><td>盐土</td></tr><tr><td>土壤电导率/mS·cm-</td><td>0~2</td><td>2~4</td><td>4~8</td><td>8~16</td><td>>16</td></tr><tr><td>SDI模型</td><td>0.000~0.3119</td><td>0.3119~0.3877</td><td>0.3877~0.5393</td><td>0.5393~0.8425</td><td>>0.8425</td></tr></table></body></html>

注：SDI为遥感盐分监测指数。

![](images/e67e1561514d76f9aeb51de6a18aca875023b422d270fc3b6832764bb479ba84.jpg)  
干旱区地理  
图5阿拉尔垦区土壤盐渍化分布  
Fig.5Distribution of soil salinization in Aral Reclamation Area

Tab.3Statistics of soil salinization area in Aral Reclamation Area from 2Oll to 2021   

<html><body><table><tr><td>年份</td><td>非盐渍土</td><td>轻度盐渍土</td><td>中度盐渍土</td><td>重度盐渍土</td><td>盐土</td></tr><tr><td>2011</td><td>972.98</td><td>251.09</td><td>405.55</td><td>872.51</td><td>810.60</td></tr><tr><td>2021</td><td>1291.20</td><td>251.89</td><td>328.71</td><td>719.48</td><td>879.21</td></tr></table></body></html>

根据土壤实测数据可知，样品数量关系呈现为非盐渍土样品数量 $\mathrm { > }$ 轻度、中度盐渍土样品数量 $>$ 重度盐渍土、盐土样品数量，其中非盐渍土的样品数量占总样品数量的 $7 2 \%$ 。结合奥维地图分析2021年阿拉尔垦区土壤盐渍化空间格局分布，模型反演的非盐渍土以农田为主，轻度、中度盐渍土一部分零散分布于农田，一分部分布于塔河附近，重度盐渍土和盐土则多分布于沙漠附近。查询该区域相关土壤盐渍化研究，遥感解译与实际调查现状相符。因此，SDI模型能用于本研究区域土壤盐渍化研究。2.2.3阿拉尔垦区土壤盐渍化时空动态变化分析利用ArcGIS10.3，生成2011—2021年阿拉尔垦区土壤盐渍化面积转移矩阵(表4)和土壤盐渍化动态变化图(图6)。由表4和图6可知，土壤盐渍化自2011—2021年发生明显良好逆转的区域主要分布于垦区北部和南部等地区，其中非盐渍土主要由中度盐渍土转入 $1 5 5 . 8 9 \ \mathrm { k m } ^ { 2 }$ ,由重度盐渍土转入 $1 8 3 . 2 9 ~ \mathrm { k m } ^ { 2 }$ 轻度盐渍土主要由非盐渍土和中度盐渍土分别转入 $8 7 . 8 3 \ \mathrm { k m } ^ { 2 }$ 和 $6 0 . 4 0 \ \mathrm { k m } ^ { 2 }$ ,其分布呈零散化分布；中度盐渍土主要由非盐渍土和重度盐渍土转入58.94$ { \mathrm { k m } } ^ { 2 }$ 和 $1 0 5 . 1 9 \ \mathrm { k m } ^ { 2 }$ ，,其主要在垦区西部和东北方向。土壤盐渍化向严重趋势发展的区域主要位于垦区中部地区和东部地区,其中重度盐渍土主要由中度盐渍土和盐土分别转入 $7 0 . 4 2 \mathrm { k m } ^ { 2 }$ 和 $1 4 0 . 0 2 \ \mathrm { k m } ^ { 2 }$ ，盐土主要由重度盐渍土转入 $9 4 . 1 5 \mathrm { k m } ^ { 2 }$ O

# 3讨论

# 3.1模型选取

以NDVI和SI构建SDI模型反演阿拉尔垦区土壤盐渍化精度为 $8 2 . 7 3 \%$ ，与王飞等25采用此模型反演塔里木盆地南缘地区土壤盐分的精度基本一致，表明模型较适用于反演阿拉尔垦区土壤盐渍化。不同研究区自然条件、社会经济因素具有较大差异，南疆地区独特的气候条件和地位位置，致使SDI模型一定程度上反演内地土壤盐渍化精度有所不同[15]。SDI模型较多,但是否适用于反演阿拉尔垦区土壤盐分，其适用性还需进一步的实验验证。总之，应充分考虑不同研究区地理位置等情况选择最合适的光谱指数构建SDI模型，反演的土壤盐渍化信息也将会更加科学、合理。

表32011—2021年阿拉尔垦区土壤盐渍化面积统计  
表42011—2021年阿拉尔垦区土壤盐渍化面积转移矩阵  
Tab.4Transfer matrix of soil salinization area in Aral Reclamation Area from 2Oll to 2021 /km²   

<html><body><table><tr><td rowspan="3" colspan="2">土壤盐渍化等级</td><td colspan="5">2011年</td></tr><tr><td>非盐渍土</td><td>轻度盐渍土</td><td>中度盐渍土</td><td>重度盐渍土</td><td>盐土</td></tr><tr><td>2021年</td><td>非盐渍土</td><td>758.50</td><td>107.67</td><td>155.89</td><td>183.29</td><td>51.11</td></tr><tr><td></td><td>轻度盐渍土</td><td>87.83</td><td>39.14</td><td>60.40</td><td>51.07</td><td>8.65</td></tr><tr><td></td><td>中度盐渍土</td><td>58.94</td><td>40.45</td><td>99.71</td><td>105.19</td><td>15.31</td></tr><tr><td></td><td>重度盐渍土</td><td>43.58</td><td>20.56</td><td>70.42</td><td>392.91</td><td>140.02</td></tr><tr><td></td><td>盐土</td><td>19.10</td><td>3.35</td><td>7.12</td><td>94.15</td><td>506.45</td></tr></table></body></html>

![](images/2106c7e2e65e9cffa9ce063ee5c1928c86bf00002fddf154e98b08d81923429a.jpg)  
Fig.6 Dynamic changes of soil salinization in Aral Reclamation Area from 2Oll to 2021

# 3.2植被指数与土壤盐分

植物生长状况与土壤盐分有着密切相关性，土壤盐分含量超过一定阈值便会影响植被生理参数，植被中所对应的光谱反射率便会发生改变，鉴于此，诸多学者认同植被指数能间接反映土壤盐渍化程度[36]。研究区计算NDVI值与土壤盐渍化分布有着较强的相似性，NDVI值越高，SDI模型反演土壤盐渍化等级越低，NDVI与SI构建二维特征空间散点图便可以直观观察植被与盐分关系成反比，随着土壤盐分增加，NDVI值呈下降趋势，这与众多学者研究结果大致相同[13.15,24-25]。当然,植被指数种类繁多，NDVI仅为其中最常用的一种，其余植被指数对垦区土壤盐分反演的精度还有待进一步验证。同时，南疆干旱区的植被生长期主要集中于6一10月，其余时间研究土壤盐分便需要考虑其他光谱指数或直接测定土壤光谱信息。

# 3.3近10a土壤盐渍化变化及驱动因素分析

为合理解释与辅助分析2011—2021年阿拉尔垦区土壤盐渍化变化情况，由农业部规划设计研究院设施农业研究所温室数据共享平台(http://datasheshiyuanyi.com/)获取阿拉尔垦区近 $1 0 \mathrm { ~ a ~ }$ 气候数据(图7)，由兵团年鉴获取阿拉尔垦区近 $1 0 \mathrm { ~ a ~ }$ 有效灌溉面积(图8)。

分析阿拉尔垦区年均气温、年降水量和有效灌溉面积可知，年均气温波动范围在 $1 { \sim } 2 ~ \mathrm { \% }$ 之间，年降水量波动范围在 $2 0 { \sim } 1 0 0 ~ \mathrm { m m }$ ，有效灌溉面积波动范围在 $0 . 5 { \times } 1 0 ^ { 5 } \ \mathrm { h m } ^ { 2 }$ 。总体变化趋势为年均气温上升，年降水量降低，有效灌溉面积增加。结合SDI模型分析的2011—2021年非盐渍土、轻度盐渍土、中度盐渍土、重度盐渍土、盐土面积分别呈“上升、上升、下降、下降、上升"趋势，其中非盐渍土面积增长变化最为明显，盐土面积稍有增长。由上述分析得知，土壤盐渍化受自然因素和人为因素影响，阿拉尔垦区气候因素对土壤盐渍化变化影响较小，人为因素对土壤盐渍化变化影响较大，人为因素中灌溉面积则是造成垦区土壤盐渍化变化的主要驱动因素。

![](images/9d7038a490ae304c56ba774b337eb4a6c19569d761841374e1bc9935a3dec41e.jpg)  
图62011—2021年阿拉尔垦区土壤盐渍化动态变化  
图7近10a阿拉尔垦区年均气温及年降水量 Fig.7Average annual temperature and annual precipitation in Aral Reclamation Area in recent 1O years

![](images/5d559d5aecc1030026d4a29d7fac4b4e966672a76d6e8a4428f12d0e6fa99df0.jpg)  
图8近10a阿拉尔垦区有效灌溉面积 Fig.8Effective irigation area of Aral Reclamation Area inrecent10 years

# 3.4土壤盐渍化分布及其原因分析

土壤盐渍化分布受自然因素和人为因素影响[13],阿拉尔垦区位于新疆南部干旱区，降雨量少、日照时间久、光照强、蒸发量大。由土壤盐渍化分布可知垦区农田以非盐渍土和轻度盐渍土为主，分布情况同吴家林[29]研究垦区 $0 { \sim } 3 0 ~ \mathrm { c m }$ 棉田土壤盐渍化结果大致相同。垦区农田常年在春季或冬季采用漫灌洗盐，作物生长期常采用膜下滴灌控制水量和土壤盐分，随着种植年限增加，盐分快速向下淋洗，极大降低了农田表层土壤的盐分含量[38]。垦区农业灌水需求量大，塔里木河区域输入水量相对较少，灌溉后河床、草地等地区由于蒸发强烈，土壤表层水分快速蒸发，下层土壤水分携带着盐分向表层迁移聚集，造成表层盐分积累[39]，以中度盐渍土和重度盐渍土为主。土地荒漠化和紧邻塔克拉玛干沙漠区域附近，土壤因长期缺水，日照强烈，盐分多以盐斑集中呈现在土壤表层，此时表层土壤儿乎无植被生长。当然，垦区受水文地质单元、植被类型、灌水水质、滴灌带质量等影响，农田局部区域水量不一致，土壤表层盐分含量有所差异，导致同一农田有不同程度的盐渍土。

此外，SDI模型对阿拉尔垦区土壤盐渍化监测受Landsat8遥感影像分辨率影响，只能对大范围进行反演，得到一个近似区域，对小范围土壤盐渍化精准反演，可考虑分辨率更高的遥感影像数据，

# 4结论

(1）阿拉尔垦区农田以非盐渍土和轻度盐渍土为主，塔里木河河床、草地、林带等以中度盐渍土、重度盐渍土为主，土地荒漠化和沙漠附近以盐土为主。

(2）2011—2021年，阿拉尔垦区土壤盐渍化等级变化中非盐渍土、轻度盐渍土、中度盐渍土、重度盐渍土、盐土面积分别呈“上升、上升、下降、下降、上升"趋势，总体可知近10a阿拉尔垦区土壤盐渍化得到较好改善。

(3）阿拉尔垦区土壤盐渍化程度发生明显良好逆转区域主要位于垦区的北部和南部地区，非盐渍土主要由中度和重度盐渍土转人。垦区中部和东部地区土壤盐渍化程度加重，以重度盐渍土和盐土之间相互转化为主导。

# 参考文献(References)

[1] 姜红,玉素甫江·如素力,热伊莱·卡得尔,等.基于神经网络模 型的干旱区绿洲土壤盐渍化评价分析[J].地球信息科学学报, 2017,19(7): 983-993.[Jiang Hong,Rusuli Yusufujiang,Kadeer Reyilai,et al.Evaluation and analysis of soil salinization in the arid zones based on neural network model[J]. Journal of Geo-Information Science,2017,19(7): 983-993.]   
[2] Yu T,Jiapaer G, Bao A,et al. Using synthetic remote sensing indicators to monitor the land degradation in a salinized area[J].Remote Sensing,2021,13(15): 2851,doi: 10.3390/rs13152851.   
[3] 曹肖奕,丁建丽,葛翔宇,等.基于不同卫星光谱模拟的土壤电 导率估算研究[J].干旱区地理,2020,43(1):172-181.[Cao Xiaoyi, Ding Jianli,Ge Xiangyu,et al.Estimation of soil conductivity based on spectral simulation of different satellites[J].Arid Land Geography,2020,43(1): 172-181.]   
[4]冯娟,丁建丽,杨爱霞,等.干旱区土壤盐渍化信息遥感建模[J]. 干旱地区农业研究,2018,36(1):266-273.[Feng Juan,Ding Jianli,Yang Aixia,et al.Remote sensing modeling of soil salinization information in arid areas[J].Agricultural Research in the Arid Areas,2018,36(1): 266-273.]   
[5] MohamedES,Saleh AM,Belal AB,etal.Application of near-infrared reflectance for quantitative assessment of soil properties[J]. The Egyptian Journal of Remote Sensing and Space Science, 2018,21(1): 1-14.   
[6] 贾萍萍,尚天浩,张俊华,等.利用多源光谱信息反演宁夏银北 地区干湿季土壤含盐量[J].农业工程学报,2020,36(17):125- 134.[Jia Pingping, Shang Tianhao, Zhang Junhua,et al. Inversion of soil salinity in dry and wet seasons based on multi-source spectral data in Yinbei area of Ningxia, China[J]. Transactions of the Chinese Societyof Agricultural Enginering,2020,36(17): 125-134.]   
[7]张素铭,赵庚星,王卓然,等.滨海盐渍区土壤盐分遥感反演及 动态监测[J].农业资源与环境学报,2018,35(4):349-358. [Zhang Suming, Zhao Gengxing,Wang Zhuoran,et al. Remote sensing inversion and dynamic monitoring of soil salt in coastal saline area[J]. Journal of Agricultural ResourcesandEnvironment, 2018,35(4): 349-358.]   
[8]Dwivedi R S,Rao B R M.The selection of the best possible landsat TM band combination for delineating salt-affected soils[J]. International Journal of Remote Sensing,1992,13(11): 2051-2058.   
[9]Sidike A,Zhao S,Wen Y.Estimating soil salinityin Pingluo County of China using QuickBird data and soil reflectance spectra[J]. International Journal of Applied Earth Observation and Geoinformation, 2014,26: 156-175.   
[10]El-Horiny M M. Mapping and monitoring of soil salinization using remote sensing and regression techniques: A case study in the Bahariya depression，Western Desert，Egypt[C]/IGARSS2019— 2019 IEEE International Geoscience and Remote Sensing Symposium.Yokohama: IEEE,2019:1-4.   
[11] 孙亚楠,李仙岳,史海滨,等.基于多源数据融合的盐分遥感反 演与季节差异性研究[J].农业机械学报,2020,51(6):169-180. [Sun Ya'nan,Li Xianyue,Shi Haibin,etal. Remote sensing inversion of soil salinity and seasonal difference analysis based on multi-source data fusion[J]. Transactions of the Chinese Society for Agricultural Machinery,2020,51(6): 169-180.]   
[12] 黄权中,徐旭,吕玲娇,等.基于遥感反演河套灌区土壤盐分分 布及对作物生长的影响[J].农业工程学报,2018,34(1):102- 109.[Huang Quanzhong,Xu Xu,Lu Lingjiao,et al. Soil salinity distribution based on remote sensing and its efect on crop growth in Hetao irrigation district[J]. Transactions of the Chinese Society of Agricultural Engineering,2018,34(1): 102-109.]   
[13] 陈红艳,赵庚星,陈敬春,等.基于改进植被指数的黄河口区盐 渍土盐分遥感反演[J].农业工程学报,2015,31(5):107-114. [Chen Hongyan, Zhao Gengxing, Chen Jingchun, et al. Remote sensing inversion of saline soil salinity based on modified vegetation index in estuary area of Yellw River[J]. Transactions of the Chinese Society of Agricultural Engineering,2015,31(5): 107-114.]   
[14] 刘恩,王军涛,常步辉,等.小开河引黄灌区土壤盐渍化定量遥 感反演[J].中国农村水利水电,2019(12):20-24.[Liu En,Wang Juntao,Chang Buhui,et al. Quantitative remote sensing inversion of soil salinization in Xiaokaihe Yellow River irrigation district[J]. China Rural Water and Hydropower,2019(12): 20-24.]   
[15] 边玲玲,王卷乐,郭兵,等.基于特征空间的黄河三角洲垦利县 土壤盐分遥感提取[J].遥感技术与应用,2020,35(1):211-218. [Bian Lingling,Wang Juanle, Guo Bing, et al. Remote sensing extraction of soil salinity in Yellow River delta Kenli County based on feature space[J]. Remote Sensing Technology and Application, 2020,35(1): 211-218.]   
[16] 丁建丽,瞿娟,孙永猛,等.基于MSAVI-WI特征空间的新疆渭 干河一库车河流域绿洲土壤盐渍化研究[J].地理研究,2013, 32(2): 223-232. [Ding Jianli, Qu Juan, Sun Yongmeng,et al. The retrieval model of soil salinization information in arid region based on MSAVI-WI feature spacecase study of the delta oasis in WeiganKuqa watershed[J]. Geographical Research,2013,32(2): 223- 232.]   
[17] 陈实,高超,徐斌,等.新疆石河子农区土壤含盐量定量反演及 其空间格局分析[J].地理研究,2014,33(11):2135-2144.[Chen Shi, Gao Chao,Xu Bin,et al. Quantitative inversion of soil salinity and analysis of its spatial patern in agricultural area in Shihezi of Xinjiang[J]. Geographical Research,2014,33(11): 2135-2144.]   
[18]王爽,丁建丽,王璐,等.基于地表光谱建模的区域土壤盐渍化 遥感监测研究[J].干旱区地理,2016,39(1):190-198.[Wang Shuang,Ding Jianli,Wang Lu,et al.Remote sensing monitoring of soil salinization based on surface spectral modeling[J].Arid Land Geography,2016,39(1): 190-198.]   
[19] 王丹丹,于志同,程猛,等.渭干河绿洲不同土地利用类型土壤 盐分的变化特征分析[J].干旱区地理,2018,41(2):349-357. [Wang Dandan, Yu Zhitong, Cheng Meng, et al. Characteristics of soil salinity under diferent land use types in Weigan River Oasis [J]. Arid Land Geography,2018,41(2): 349-357.]   
[20] 麦麦提吐尔逊·艾则孜.绿洲土壤盐渍化及水盐调控[M].北京: 北京理工大学出版社,2016.[Azezi Maimaitituerxun. Assessment and monitoringofsoilslinizationusing remote sensing in arid area[M]. Beijing: Beijing Institute of Technology Pres,2016.]   
[21] 张添佑,王玲,曾攀丽,等.基于MSAVI-SI特征空间的玛纳斯河 流域灌区土壤盐渍化研究[J].干旱区研究,2016,33(3):499- 505. [Zhang Tianyou,Wang Ling, Zeng Panli, et al. Soil salinization in the irrigated area of the Manas River Basin based on MSAVI-SI feature space[J].Arid Zone Research,2016,3(3): 499-505.]   
[22] Liu J, Zhang L, Dong T,etal. Theapplicabilityof remote sensing models of soil salinization based on feature space[J]. Sustainability,2021,13(24): 13711,doi: 10.3390/su132413711.   
[23]王飞,丁建丽,魏阳,等.基于Landsat 系列数据的盐分指数和 植被指数对土壤盐度变异性的响应分析——以新疆天山南北 典型绿洲为例[J].生态学报,2017,37(15):5007-5022. [Wang Fei,Ding Jianli,Wei Yang,et al.Sensitivity analysisofsoilsalinity and vegetation indices todetectsoil salinityvariationbyusing Landsat series images: Applications in diffrent oases in Xinjiang, China[J]. Acta Ecologica Sinica,2017,37(15): 5007-5022.]   
[24] 卢晶,张绪教,叶培盛,等.基于 SI-MSAVI特征空间的河套灌

# 干旱区地理

区盐碱化遥感监测研究[J].国土资源遥感,2020,32(1):169- 175.[Lu Jing, Zhang Xujiao,Ye Peisheng, et al. Remote sensing monitoring of salinization in Hetao irrigation district based on SIMSAVI feature space[J]. Remote Sensing for Land & Resources, 2020,32(1): 169-175.]   
[25] 王飞,丁建丽,伍漫春.基于NDVI-SI特征空间的土壤盐渍化遥 感模型[J].农业工程学报,2010,26(8):168-173.[Wang Fei,Ding Jianli,Wu Manchun. Remote sensing monitoring models of soil salinization based in NDVI-SI feature space[J]. Transactions of the Chinese Society of Agricultural Engineering,2010,26(8):168- 173.]   
[26] 史晓艳,李维弟,余露,等.玛纳斯河流域农灌区土壤盐渍化遥 感定量评价[J].灌溉排水学报,2018,37(11):69-75,83.[Shi Xiaoyan,Li Weidi, Yu Lu,et al. Using remote sensing to evaluate soil salinization distribution over the irrigation areas in the Manas River Basin[J].Journal of Irigation and Drainage,2O18,37(11): 69-75, 83.]   
[27] 王雪梅,周晓红.渭干河—库车河三角洲绿洲棉田土壤盐分估 算及遥感反演[J].干旱地区农业研究,2018,36(6):250-254, 262.[Wang Xuemei, Zhou Xiaohong.Estimation and inversion modeling of salinity of cotton field soil using remote sensing in the Delta Oasis of Weigan and Kuqa Rivers[J].Agricultural Research in the Arid Areas,2018,36(6): 250-254,262.]   
[28] 杨小虎,罗艳琴,杨海昌,等.玛纳斯河流域绿洲农田土壤盐分 反演及空间分布特征[J].干旱区资源与环境,2021,35(2):156- 161.[Yang Xiaohu,Luo Yanqin, Yang Haichang,et al. Soil salinityretrieval and spatial distribution of oasis farmland in Manasi River Basin[J]. Journal of Arid Land Resources and Environment, 2021,35(2): 156-161.]   
[29] 吴家林.阿拉尔垦区棉田土壤盐渍化的遥感监测与植棉效益分 析[D].阿拉尔:塔里木大学,2021.[Wu Jialin.Remote sensing monitoring and cotton plantation benefit analysis of cotton field soil salinization in Aral Reclamation Area[D].Aral: Tarim University, 2021.]   
[30] 宋奇,冯春晖,高琪,等.阿拉尔垦区近30年耕地变化及其驱动 因子分析[J].国土资源遥感,2021,33(2):202-212.[Song Qi, Feng Chunhui,Gao Qi,et al. Change of cultivated land and its driving factors in Alar Reclamation Area in the past thirty years [J].Remote Sensing for Land & Resources,2021,33(2): 202-212.]

[31]新疆生产建设兵团年鉴编辑委员会.兵团年鉴[M].乌鲁木齐:

新疆生产建设兵团年鉴社,2020.[Editorial Commitee of Xinjiang Production and Construction Corps Yearbook.Production and Construction Corpsyearbook[M]. Urumqi: Xinjiang Production and Construction Corps Yearbook Society,2020.]   
[32] 卢晶.基于3S技术的土壤盐碱化时空分布规律及影响因素研 究[D].北京:中国地质大学,2019.[Lu Jing.Study on temporalspatial distribution and impact factors of soil salinization based on 3Stechnology[D]. Beijing:China University of Geosciences, 2019.]   
[33] 陈实,徐斌,金云翔,等.北疆农区土壤盐渍化遥感监测及其时 空特征分析[J].地理科学,2015,35(12):1607-1615.[Chen Shi, Xu Bin, Jin Yunxiang,et al.Remote sensing monitoring and spatial-temporal characteristics analysis of soil salinization in agricultural area of northern Xinjiang[J]. Scientia Geographica Sinica, 2015,35(12): 1607-1615.]   
[34]Khan N M,Sato Y. Monitoring hydro-salinity status and its impact in irrigated semi-arid areas using IRS-1B LISS-II data[J]. Asian Journal of Geoinform,2001,1(3): 63-73.   
[35] 李艳菊,丁建丽,米热古力·艾尼瓦尔.渭—库绿洲土壤剖面盐 分分布特征及驱动因子分析[J].灌溉排水学报,2019,38(6): 58-65.[Li Yanju,Ding Jianli,Ainiwaer Mireguli. Soil salt distribution and the factors affect it in Ogan Kucha River Oasis[J]. Journal of Irrigation and Drainage,2019,38(6): 58-65.]   
[36] 王遵亲,祝寿泉,尤文瑞,等.中国盐渍土[M].北京:科学出版 社,1993.[Wang Zunqin, Zhu Shouquan,You Wenrui,et al. Saline soil in China[M]. Beijing: Science Press,1993.]   
[37]Staff U S SL.Diagnosis and improvement of saline and alkali soils [J].Agriculture Handbook,1954,60: 83-100.   
[38] 王旭,田长彦,赵振勇,等.滴灌条件下盐地碱蓬 (Suaeda salsa) 种植年限对盐碱地土壤盐分离子分布的影响[J].干旱区地理, 2020,43(1): 211- 217.[Wang Xu,Tian Changyan,Zhao Zhenyong,et al. Effects of different planting years of Suaeda salsa on the soil ions distribution in saline-sodic soil under drip irrigation [J]. Arid Land Geography,2020,43(1): 211-217.]   
[39] 王世明,范敬龙,赵英,等.咸水灌溉条件下塔里木河下游沙漠 土壤水盐运移数值模拟[J].干旱区地理,2021,44(4):1104- 1113.[Wang Shiming,Fan Jinglong,Zhao Ying,et al. Numerical simulation of water and salt migration in desert soil in the lower reaches of Tarim River under salt-water irrigation[J].Arid Land Geography,2021,44(4): 1104-1113.]

# Remote sensing monitoring and temporal and spatial characteristics of soil salinization in Aral Reclamation Area

DAI Yunhao'， GUAN Yao'， ZHANG Qinkai'， SUN Junjie'， HE Xinghong12(1.CollgeofWaterConservancyandArchitectureEnginering,TarimUniversityAral8433o0,Xinjiang,China;2.SoutherGeotechnical Engineering Research Center,Tarim University,Aral 8433Oo,Xinjiang, China)

Abstract: This paper analyzes the distribution and spatial variation of saline soil of diferent degrees in the Aral Reclamation Area, Xinjiang, China and provides an important reference for effctively controling and preventing reclaimed saline soil in the reclamation area.Using Landsat $\mathrm { E T M ^ { + } }$ in 2011 and Landsat OLI in 2021, the remote salinization detection index (SDI) model of soil salinization was constructed using the salinity index and the normalized vegetation index to extract and analyze soil salinization information in the Aral Reclamation Area. Soil data were collected from l39 surface soil sample points ( $( 0 - 1 0 \ \mathrm { c m } )$ ）in the Aral Reclamation Area,and three samples per point were collected using the triangular sampling method. Soil extract with water and soil (5:1) was prepared，and soil conductivity was measured in the laboratory. According to the soil conductivity value corresponding to the soil salinization grade standard of the American Saline Alkali Soil Laboratory,the soil salinization grade in the Aral Reclamation Area is divided into five categories.According to the natural discontinuity method,the SDI is divided into five levels to verify its clasification accuracy and explore the temporal and spatial distribution characteristics of soil salinization in the study area in the recent 1O years.The fitting degree between the SDI model of soil salinization and the measured soil conductivity $R ^ { 2 } { = } 0 . 7 5 7 9$ . The farmland in the reclamation area comprises mainly nonsaline soil and light saline soil,the riverbed and grassland of the Tarim River are mainly moderately saline soil and heavy saline soil,and the land desertification and the area near the desert comprise mainly saline soil.From 201l to 2021,the area of nonsaline soil and mild saline soil in the Aral Reclamation Area increased by $3 1 8 . 2 2 ~ \mathrm { k m } ^ { 2 }$ and $0 . 8 0 \mathrm { k m } ^ { 2 }$ ，respectively; the area of moderate and severe soil salinization decreased by $2 2 9 . 8 7 \mathrm { k m } ^ { 2 }$ ； and the area of saline soil increased by $6 8 . 6 1 \mathrm { k m } ^ { 2 }$ .In the recent 10 years,the degree of soil salinization in the north and south of the Aral Reclamation Area has improved significantly,the degreeof soil salinization in the middle and eastern parts has increased,and the overall soil salinization in the reclamation area has improved.The SDI has a certain reference value for the study of soil salinization and provides ascientific basis for the real-time monitoring and accurate treatment of soil salinization in reclamation areas.

Key words: soil salinization；saline soil; salinization detection index (SDI)；salinity index-normalized diference vegetation index (SI-NDVI)； Aral Reclamation Area