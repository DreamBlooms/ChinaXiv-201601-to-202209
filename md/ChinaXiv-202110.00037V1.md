# 基于地理探测器模型的疏勒河流域景观生态风险评价及驱动因素分析

小丽蓉1，周冬梅¹，岑国璋，马静1，党锐²，倪帆¹，张军1.3（1.甘肃农业大学资源与环境学院,甘肃 兰州730070；2.甘肃农业大学管理学院,甘肃 兰州730070;3.甘肃省节水农业工程技术研究中心,甘肃 兰州730070)

摘要：疏勒河流域地处河西走廊最西端，是典型的干旱内陆河流域，生态环境极其脆弱,也是我国重要的生态屏障之一。借助Fragstats软件从斑块和景观2个尺度，结合2000—2018年土地利用数据，评价分析疏勒河流域景观生态风险时空变化特征，利用地理探测器定量分析了该流域景观生态风险驱动因素。结果表明：(1)疏勒河流域主要景观类型为未利用地和草地，其斑块个数(NP)、景观形状指数(LSI)、最大斑块指数(LPI)和聚集度指数(AI)值均较高;2000—2018年蔓延度指数(CONTAG)值下降、香农多样性指数(SHDI)和香农均匀度指数(SHEI)值缓慢上升，流域景观破碎度严重。(2)疏勒河流域景观生态风险空间分布呈现北高南低，2000—2018年呈现流域景观生态风险逐渐下降趋势，其中较高风险和高风险地区面积下降明显。（3）人为干扰度是影响景观生态风险空间分布的主要因子,归一化植被指数(NDVI)次之，人口密度影响最小;景观生态风险的影响均为双因子增强或非线性增强，无显著差异大多表现在自然和自然因子间，自然和人为因子之间存在显著性差异。因此，对流域进行景观生态风险指数评价和驱动因素分析至关重要。

关键词：景观生态风险；景观格局；地理探测器；疏勒河流域

# 文章编号：

景观生态风险是景观格局和生态过程相互作用产生不利的影响，主要表现在人类活动或自然灾害对景观的组成、结构、功能等影响[1-2]。流域是连接地表水、土地植被覆盖和自然-社会的重要综合生态地理区域[3-4],也是最为重要的地理景观,是受到人类活动强烈作用的区域，流域保护是实现区域社会经济可持续发展的必然选择[5]。自然因素和人类活动已经对景观格局产生了深远的影响，流域尺度上的景观生态风险分析评价是对流域进行生态环境保护的重要研究内容，也成为生态风险评价的热点之一[6-7]。国内外学者分别在国家[8-9]、区域[10-11]、乡镇[12]、流域[13-15]等不同尺度上对景观生态风险评价的理论与方法进行了广泛探讨，已初步形成了研究框架[16]。Yang等[17]在改进TOPSIS模型基础上，选取了24个指标从农业、工业和城市化3个方面分析评价渭河流域生态风险，认为通过改善水质和保持生物完整性可以调控该流域生态风险。李青圃等[18]采用最小积累阻力模型和空间主成分分析对宁江进行景观生态风险评价，研究发现人类社会活动和景观格局对景观生态风险影响较大，模拟发现通过优化景观格局使得景观连通度显著增加，可以改善景观生态风险程度。郑杰等[19]利用遥感影像研究2009—2017年草海流域景观生态风险演变特征，结果表明在草海流域高生态风险、较高生态风险和中生态风险面积均呈不同程度增加态势，且景观生态风险存在显著的空间自相关性。整体来看，当前所用研究的景观因子大多集中在对景观格局的量化和分析，利用研究结果直接或间接的反映景观生态风险。对景观生态风险驱动力研究多从定性方面入手，缺乏定量研究手段。地理探测器[20-21]是一种基于统计学原理,通过分析层内方差与层间方差的差异定量表达研究对象空间分异性的研究方法，该方法不仅可以探测数据型数据和类型数据，也可以定量探测驱动因子之间交互作用以及判断每2个因子对景观生态风险空间分布的影响是否具有显著差异，与其他空间异质性探测工具相比地理探测器具有更高的解释效率。目前地理探测器广泛应用于定量研究气候变化[22-23]、 $\mathrm { C O } _ { 2 }$ 减排[24]、植被变化[25-27]、居民点分布[28]乃至新冠(COVID-19)疫情散布[29-30]的驱动因素，然而在分析景观生态风险驱动因子中尚不多见，本文拟在疏勒河流域景观生态风险评价基础上，利用地理探测器对其景观生态风险驱动因素开展定量分析。

疏勒河流域是典型干旱内陆河流域，生态环境脆弱，近年来受到气候变化和人类活动影响，疏勒河流域景观趋于破碎化[31],导致景观生态风险进一步加剧，深人研究该流域景观生态风险时空演变特征，识别不同驱动因子对景观生态风险的贡献量，以期为控制疏勒河流域景观生态风险升级，以及流域优化管理和协调可持续发展提供科学依据。

# 1研究区概况

疏勒河流域位于我国西北干旱区，是我国唯一一条由东向西的内陆河,处于河西走廊最西端,介于 $9 2 ^ { \circ } 2 2 ^ { \prime } { \sim } 9 8 ^ { \circ } 3 5 ^ { \prime } \mathrm { E } , 3 8 ^ { \circ } 0 5 ^ { \prime } { \sim } 4 2 ^ { \circ } 4 5 ^ { \prime } \mathrm { N }$ 之间，流域总面积约 $1 . 1 2 \times 1 0 ^ { 5 } ~ \mathrm { k m } ^ { 2 }$ (图1)。疏勒河发源于祁连山脉的岗格尔肖合力岭，流经肃北蒙古族自治县、敦煌市、玉门市以及瓜州县。流域地势北低南高，海拔介于 $8 0 2 { \sim } 5 5 0 4 \ \mathrm { m }$ 。流域内降水量少，蒸发量大，东西2侧临近沙漠，水源补给主要为冰川融水和降水。上游地区海拔高，地势陡峭，存在永久性冰川雪地，中下游地势平坦,绿洲与荒漠并存,其中未利用地面积占 $7 0 \%$ 以上，土地沙漠化问题严重。根据《2019年甘肃省水资源公报》,2019年疏勒河流域有人口 $5 . 3 6 \times 1 0 ^ { 5 }$ 人，GDP为 $3 . 6 7 \times 1 0 ^ { 1 0 }$ 元，耕地面积为$1 4 . 7 9 \times 1 0 ^ { 4 } \mathrm { h m } ^ { 2 }$ 。

![](images/56f22b730ef4a9a51c042787e2a650e3cbd596a58b12ab31ed8d211aaf64c1b4.jpg)  
图1疏勒河流域空间位置  
Fig.1 Spatial location of the Shule River Basin

# 2数据与方法

# 2.1数据来源及处理

2000、2010、2018年土地利用数据以及县级行政区划矢量数据来源于中国科学院地理科学与资源研究所资源环境数据云平台(http://www.resdc.cn/Default.aspx），空间分辨率为 $1 ~ \mathrm { k m }$ ，投影坐标系均为Krasovsky_1940_Albers。其中，耕地城市及农村居名点的数据采集，正确率不低于 $9 5 \%$ ,草地、林地、水域等正确率不低于 $9 0 \%$ ,未利用土地正确率不低于 $8 5 \%$ 。参考国家土地利用现状分类标准，适当合并后确定耕地、林地、草地、水域、居民地和未利用土地6类为本次研究的景观类型。选取的驱动因子为3个气候因素(年降水量、年最高气温、年最低气温）、3个地表因素[高程(DEM)坡度、归一化植被指数(NDVI)和2个人为因子(人口密度和人为干扰度）。其中人口密度来源于Worldpop 网站(http://www.worldpop.org/);年降水量、气温数据来源于国家地球系统科学数据中心;NDVI和DEM来源于中国科学院地理科学与资源研究所资源环境数据云平台，坡度数据则由DEM数据在GIS中提取。

年降水量、高程、NDVI、气温、人为干扰度在ArcGIS中用自然断点法分为10类，人口密度用等数量间距法分为10类，坡度按水土保持综合治理规划通则(GB/T15772—2008)分为6类 $( 0 { \sim } 3 ^ { \circ } , 3 ^ { \circ } { \sim } 8 ^ { \circ } , 8 ^ { \circ } \sim$ $1 5 ^ { \circ } , 1 5 ^ { \circ } { \sim } 2 5 ^ { \circ } , 2 5 ^ { \circ } { \sim } 3 5 ^ { \circ }$ 和 $1 { > } 3 5 ^ { \circ }$ ）。

# 干吴区地理

# 2.2 研究方法

2.2.1景观格局指数景观格局指数能够从无序的景观斑块中发现潜在的规律及意义，即用定量化的指标来反映景观斑块在景观组成结构和空间上的特征[32]。本文参考国内外已有研究并结合疏勒河流域景观要素分布状况[33-35],分别从景观要素水平上针对个数、边长和分布聚集性和连接性、多样性等方面，利用Fragstats选取斑块个数(NP）、最大斑块指数(LPI)、聚集度指数(AI)、景观形状指数(LSI）、香农多样性指数（SHDI）、香农均匀度指数(SHEI)以及蔓延度指数(CONTAG)7个指数(表1)

作为评价指标，并利用Fragstats软件计算指标值。

2.2.2景观生态风险指数构建采用等间距的方式将疏勒河流域划分了共1212个 $1 0 \ \mathrm { k m } { \times } 1 0 \ \mathrm { k m }$ 的正方形网格评价单元。分别计算每一个评价单元的生态风险指数，依次作为评价单元中心点的景观生态风险，并用克里金法进行疏勒河流域景观生态风险的空间插值。

借鉴相关学者研究[36-38],用景观分离度、景观破碎度以及景观分维数来建立景观干扰度指数，分别将景观破碎度、分离度和分维数权重赋值为0.5、0.3、0.2，进而可计算出疏勒河流域景观生态风险指数，其公式及生态学意义见表2。

# 表1景观格局指数公式

Tab.1 Formulas of landscape pattern indices   

<html><body><table><tr><td>景观格局指数</td><td>公式</td><td>意义</td></tr><tr><td>斑块个数(NP)</td><td>NP =ni</td><td>ni为景观要素i的斑块指数，反映景观中某一斑块类型的斑块总个数。其值越 大表明景观破碎度越高。</td></tr><tr><td>聚集度指数(AI)</td><td>AI=(gu/maxg)×100</td><td>gi和maxg"为基于单倍法的斑块类型i各像元之间节点数和最大节点数。AI约 接近0时，斑块类型破碎度最大，凝聚程度越低;AI约接近100时，斑块类型越 紧实。</td></tr><tr><td>最大斑块指数(LPI)</td><td>LPI= max(aaa.."an)/A</td><td>max为景观中最大斑块的面积(km);A为景观总面积(km);a"为第n个斑块。 LPI反映最大斑块在景观中的优势比例。</td></tr><tr><td>景观形状指数(LSI)</td><td>E min(E) LSI=-</td><td>Ei为第i种土地利用类型斑块边界的总长度(km)，反映整体景观的形状复杂程 度。LSI越接近于1,整体景观越简单;LSI越大，则斑块形状越不规则,越离散。</td></tr><tr><td>香农多样性指数(SHDI)</td><td>SHDI=-∑ln P 𝑖 = 1</td><td>Pi为每一种斑块类型所占景观总面积的比例(%);n为景观中斑块类型的总 数。SHDI反映斑块类型多样性，多样性指数越高表明景观中斑块类型越多。</td></tr><tr><td>香农均匀度指数(SHEI)</td><td>SHEI=-∑(pi×lnp:)/ln(m)</td><td>m为土地利用类型数;pi为每一种斑块类型所占景观总面积的比例(%)。SHEI 值较小时，反映景观受一种或几种优势斑块类型所支配;当SHEI趋于1时，说 明景观中没有明显的优势类型且斑块类型在景观中均匀分布。</td></tr><tr><td>蔓延度指数(CONTAG)</td><td>CONTAG=1+ 2 ln(m) ∑∑p,In(P)</td><td>m为土地利用类型数;n为斑块数目;pij为随机选择的2个相邻栅格细胞是属于 i和j的概率;CONTAG反映景观中不同类型斑块的团聚程度或延展趋势。</td></tr></table></body></html>

# 表2景观生态风险指数公式

Tab.2 Formulas ofLandscape ecological risk indices   

<html><body><table><tr><td>指数名称</td><td>公式</td><td>意义</td></tr><tr><td>景观生态风险指数(ERk）</td><td>ER=∑（×LL） 台A</td><td>ER为景观生态风险评价k的景观风险指数，值越大表示该评价单元的生态风 险值越高，反之，值越低；Ai为景观生态风险评价单元k中第i类景观的面积 (km);A为评价单元k的总面积(km);LL为第i类景观的生态损失指数；m为 景观类型的数量。</td></tr><tr><td>景观损失度指数(LL)</td><td>LL = C× Ui</td><td>LL为景观损失度指数；C为破碎度指数;U为干扰度指数。</td></tr><tr><td>景观破碎度指数(C:)</td><td>C=</td><td>Ci为破碎度指数;ni为景观i的斑块数;Ai为景观i的总面积(km)。</td></tr><tr><td>景观分离度指数(F)</td><td>会</td><td>Fi为景观分离度指数;A为景观总面积(km);Ai为景观i的总面积(km)；ni为 景观i的斑块数。</td></tr><tr><td>景观分维数(D)</td><td>2 ln Q ln A D=</td><td>Di为景观分维数;Qi为景观i的周长(km);Ai为景观i的总面积(km）。</td></tr><tr><td>景观干扰度指数(U)</td><td>U=axC+bxF+c×Di</td><td>Ui为景观干扰度指数；Ci为破碎度指数;F为景观分离度指数;Di为景观分维 数;ab、c分别为景观破碎度、分离度和分维数权重，对其赋值为0.5、0.3、0.2。</td></tr></table></body></html>

2.2.3景观生态风险等级划分在ArcGIS中，根据自然断点法将流域景观生态风险等级划分低景观生态风险、较低景观生态风险、中景观生态风险、较高景观生态风险和高景观生态风险5个等级。

2.2.4人为干扰度为分析疏勒河流域人为干扰度对景观生态风险的影响,参考前人的研究成果[39-40]，结合研究区的景观类型和实际情况，对研究区进行人为干扰度计算，公式为：

$$
\mathrm { { H D } = \frac { \displaystyle \sum _ { i = 1 } ^ { m } [ \mathrm { { U I } } _ { i } S _ { i } } { S } }
$$

式中：HD为某个网格的人为干扰度; $\mathrm { U I } _ { i }$ 为第 $i$ 类景观类型的干扰度指数； $S _ { i }$ 为第 $i$ 类景观类型的面积$\left( \mathrm { k m } ^ { 2 } \right)$ ；S为网格单元的总面积 $\left( \mathrm { k m } ^ { 2 } \right) ; m$ 为景观类型的数量。

2.2.5地理探测器地理探测器具有因子探测、交互探测、生态探测和风险探测4种功能，是由王劲峰等2提出的一门新的统计学方法，相比其他统计学方法，地理探测器具有处理各类别变量的优势。目前，地理探测器应用于多学科领域。本文使用前3个探测器。地理探测器的原理是：把1个区域划分为若干个小区域，如果这些小区域的方差之和小于这个区域整体的方差，那么这个区域具有差异性;如果2个变量的空间分布相同，那么这2个变量具有一定的关联性。其中用 $q$ 值来表达因子探测、空间差异和因子之间的关系。

因子探测器主要探究了因变量 $( Y )$ 的空间分布异质性及其自变量 $( \boldsymbol { \chi } )$ 在多大程度上解释了这种分异。其公式为：

$$
\scriptstyle q = 1 - { \frac { \displaystyle \sum _ { h = 1 } ^ { L } N _ { h } \sigma _ { h } ^ { 2 } } { N \sigma ^ { 2 } } } = 1 - { \frac { \mathrm { S S W } } { \mathrm { S S T } } }
$$

式中： $h$ 为自变量的分区序号； $L$ 为分区总数； $N _ { h }$ 和 $N$ 分别为每个分区和区域内总共的栅格数目； $\sigma _ { h } ^ { 2 }$ 和$\sigma ^ { 2 }$ 为每个分区方差和区域内景观生态风险的方差。SSW和SST分别是层内方差之和及全区总方差。 $q$ 的值域为[0,1」,值越大说明 $Y$ 的空间差异越明显。

交互作用探测主要在地理探测器进行空间叠加，旨在判定不同因子之间的交互力大小，可以定量表示交互后的因子对景观生态风险的影响力程度。生态探测则通过两两因子进行比较，判断疏勒河流域景观生态风险的空间分布是否具有显著性差异。

# 3结果与分析

# 3.1景观格局分析

由表3可知，除草地景观以外，其他景观斑块个数(NP)介于100\~300,而草地的NP大于1700。其原因是草地分布范围较广，从平原到高海拔地区均出现，具有点-面状相结合分布现象，破碎化程度大；其他景观要素面积较小且分布较集中，未利用地面积虽最大，但分布集中，因此NP值较小。最大斑块指数(LPI)中，未利用地LPI在7O以上，草地LPI在2.6左右，其余土地利用LPI在0.03\~0.44之间波动，这是因为未利用地和草地为流域的主要景观类型，面积较大且分布较广。景观形状指数(LSI)

表32000—2018年疏勒河流域斑块类型景观格局指数统计  
Tab.3Statistics of landscape pattern indices of patch types in the Shule River Basin from 2oo0 to 2018   

<html><body><table><tr><td>景观格局指数</td><td>年份</td><td>耕地</td><td>林地</td><td>草地</td><td>水域</td><td>建设用地</td><td>未利用地</td></tr><tr><td rowspan="3">斑块个数(NP)</td><td>2000</td><td>127</td><td>273</td><td>1736</td><td>138</td><td>85</td><td>281</td></tr><tr><td>2010</td><td>130</td><td>276</td><td>1775</td><td>146</td><td>84</td><td>293</td></tr><tr><td>2018</td><td>126</td><td>261</td><td>1770</td><td>159</td><td>164</td><td>331</td></tr><tr><td rowspan="3">最大斑块指数(LPI)</td><td>2000</td><td>0.3014</td><td>0.0916</td><td>2.6584</td><td>0.1058</td><td>0.0373</td><td>78.1309</td></tr><tr><td>2010</td><td>0.3370</td><td>0.0916</td><td>2.6602</td><td>0.1058</td><td>0.0373</td><td>77.7646</td></tr><tr><td>2018</td><td>0.4360</td><td>0.0810</td><td>2.7369</td><td>0.0997</td><td>0.0391</td><td>77.3710</td></tr><tr><td rowspan="3">景观形状指数(LSI)</td><td>2000</td><td>16.9571</td><td>17.549</td><td>58.4394</td><td>14.5510</td><td>10.4194</td><td>30.4054</td></tr><tr><td>2010</td><td>17.6835</td><td>18.0000</td><td>58.9516</td><td>14.7000</td><td>10.3548</td><td>30.7383</td></tr><tr><td>2018</td><td>17.4118</td><td>17.6863</td><td>58.4410</td><td>15.2500</td><td>12.9730</td><td>31.1059</td></tr><tr><td rowspan="3">聚集度指数(AI)</td><td>2000</td><td>52.1012</td><td>30.1902</td><td>59.7878</td><td>41.2909</td><td>31.6159</td><td>90.1088</td></tr><tr><td>2010</td><td>56.1398</td><td>29.1667</td><td>59.5156</td><td>40.9483</td><td>32.4009</td><td>89.9689</td></tr><tr><td>2018</td><td>59.8792</td><td>30.5306</td><td>59.6768</td><td>41.0032</td><td>31.5301</td><td>89.8246</td></tr></table></body></html>

# 干旱区地理

中，草地 $>$ 未利用地 ${ \bf \Phi } > \mathrm { \bar { \Phi } }$ 林地 $>$ 耕地 $>$ 水域 $>$ 建设用地，由于草地生长范围广，多分布在未利用地周围，而其他景观要素(如建设用地和水域)存在人为干涉进行规划等限制手段，因此草地、未利用地斑块形状不规则，建设用地等斑块形状较规则。从聚集度指数(AI)看出，未利用地AI在90左右，表明未利用地斑块聚集程度高，其余景观要素AI介于29.17\~59.88。

由表4可知，疏勒河流域景观类型蔓延度指数在2000—2018年呈下降趋势，说明这些年内，随着人口不断增加以及土地开垦、畧荒等土地利用变化，景观破碎程度不断增加；而香农多样性指数和香农均匀度指数在2000—2018年呈缓慢上升趋势，但值偏小，说明斑块分布仍不均匀。

# 表42000—2018年疏勒河流域景观类型景观格局指数统计

Tab.4 Statistics of landscape pattern indices of landscape types in the Shule River Basin from 2ooo to 2018   

<html><body><table><tr><td>年份</td><td>蔓C延NT指数</td><td>香农多H</td><td>香农（均HE度</td></tr><tr><td>2000</td><td>69.9751</td><td>0.6147</td><td>0.3431</td></tr><tr><td>2010</td><td>69.3664</td><td>0.6284</td><td>0.3507</td></tr><tr><td>2018</td><td>68.6688</td><td>0.6434</td><td>0.3591</td></tr></table></body></html>

# 3.2景观生态风险分析

从空间上看，2000—2018年疏勒河流域景观生态风险等级(图2),分布规律趋势一致，高景观生态风险等级主要分布在流域北部，低景观生态风险等级分布在流域南部。原因是流域北部景观类型主要为未利用地，景观类型单一且对外界的抵抗能力差，从而生态环境相对脆弱，而流域南部由于靠近祁连山脉，水资源丰富、景观类型多样，主要有草地、水域及林地，草地及林地水源涵养能力强，南部海拔较高，人类干扰少，因此景观生态风险等级低。

由表5可知，2000—2010年整体景观生态风险等级变化不大，主要在较高和高景观生态风险等级之间转换。这一时段内，未利用地和林地面积减少,耕地、草地、建设用地面积增加,其中，耕地面积增加 $3 5 1 . 5 1 ~ \mathrm { k m } ^ { 2 }$ ,这是由于移民工程导致的耕地扩张，人类对土地开垦现象严重，导致景观生态风险向高值转移。

2010—2018年，较高和高景观生态风险等级面积减少，其中较高景观生态风险等级面积减少

![](images/189ca87b730955e97e020c6ba8b6c3dd6f8b9bad887ef753963a625f5725e8b5.jpg)  
图22000—2018年疏勒河流域景观生态风险等级分布Fig.2Distributions of landscape ecological risk levels in theShule River Basin from 20o0 to 2018

表52000—2018年疏勒河流域景观生态风险等级面积及比例统计  
Tab.5Statisticsoftheareaand proportionof landscapeecologicalrisk grades inthe ShuleRiverBasin from2000 to201   

<html><body><table><tr><td rowspan="2">景观生态 风险等级</td><td colspan="2">2000- -2010年</td><td colspan="2">2010- -2018年</td><td colspan="2">2000- -2018年</td></tr><tr><td>面积/km²</td><td>比例/%</td><td>面积/km²</td><td>比例/%</td><td>面积/km²</td><td>比例/%</td></tr><tr><td>低</td><td>-23.51</td><td>-0.02</td><td>1154.71</td><td>1.03</td><td>1131.19</td><td>1.01</td></tr><tr><td>较低</td><td>-37.16</td><td>-0.03</td><td>1071.26</td><td>0.95</td><td>1034.10</td><td>0.92</td></tr><tr><td>中</td><td>-5.03</td><td>-0.01</td><td>2231.55</td><td>1.99</td><td>2226.52</td><td>1.98</td></tr><tr><td>较高</td><td>-482.94</td><td>-0.43</td><td>-3230.81</td><td>-2.88</td><td>-3713.75</td><td>-3.30</td></tr><tr><td>高</td><td>545.51</td><td>0.49</td><td>-1228.21</td><td>-1.09</td><td>-682.71</td><td>-0.61</td></tr></table></body></html>

$2 . 8 8 \%$ ，主要在玉门市西南部，高景观生态风险等级面积减少 $1 . 0 9 \%$ ,主要在肃北(南)中部一带，而低、较低及中景观生态风险等级比例在瓜州县中部及肃北(南)中部等地开始上升。由于流域南部主要为高海拔地区，水域、草地、林地景观面积增加，说明该区域景观生态风险有所降低，其主要原因是加强了对祁连山生态环境保护，下游地区开始实施节水战略，如根据《敦煌水资源合理利用与生态保护综合规划》，敦煌实施了灌区节水改造、种植结构调整等措施，遏制了敦煌盆地地下水下降趋势，使得高景观生态风险等级逐渐向中、较低甚至低等级转移。瓜州县中部为疏勒河谷地，景观生态风险等级降低。近 $1 8 \mathrm { ~ a ~ }$ ，较高景观生态风险等级面积下降$3 . 3 0 \%$ ，高景观生态风险面积下降 $0 . 6 1 \%$ ，低、较低和中景观生态风险等级面积分别上升 $1 . 0 1 \% . 0 . 9 2 \%$ 和$1 . 9 8 \%$ 。

2000一2010年，疏勒河流域处于高景观生态风险等级区的面积有所增加，增加了 $5 4 5 . 5 1 ~ \mathrm { k m } ^ { 2 }$ ，占流域比为 $0 . 4 9 \%$ ，低、较低、中等和较高景观生态风险等级区的面积均有所下降，分别减少 $2 3 . 5 1 ~ \mathrm { k m } ^ { 2 }$ 、$3 7 . 1 6 ~ \mathrm { k m } ^ { 2 } \cdot 5 . 0 3 ~ \mathrm { k m } ^ { 2 }$ 和 $4 8 2 . 9 4 ~ \mathrm { k m } ^ { 2 }$ ，占流域面积的比例分别减少了 $0 . 0 2 \% . 0 . 0 3 \% . 0 . 0 1 \%$ 和 $0 . 4 3 \%$ 。从空间分布(图3)来看，景观生态风险增加的区域零星分布在流域各处，景观生态风险等级下降的区域则主要集中在敦煌市和玉门市，由《中国县域统计年鉴》统计得出，敦煌市人口由2000年的 $1 . 7 \times 1 0 ^ { 5 }$ 人减少到2010年的 $1 . 4 \times 1 0 ^ { 5 }$ 人，玉门市由 $1 . 9 \times 1 0 ^ { 5 }$ 人减少为 $1 . 5 \times 1 0 ^ { 5 }$ 人，由于人口减少导致的人类干扰下降，加上政府对玉门资源开采的控制，导致景观生态风险等级下降。

2010一2018年，流域低景观生态风险面积增加$1 1 5 4 . 7 1 ~ \mathrm { k m } ^ { 2 }$ ，较低景观生态风险面积增加1071.26$\mathrm { k m } ^ { 2 }$ ，中景观生态风险等级面积增加 $2 2 3 1 . 5 5 \mathrm { k m } ^ { 2 }$ ，较高和高景观生态风险等级面积共减少 $4 4 5 9 . 0 2 \mathrm { k m } ^ { 2 }$ 整个流域景观生态风险等级逐渐下降，且降低区域相对集中，具体分布在肃北(北)中部及西部、敦煌市中部、瓜州县东部及玉门市西部。在此期间，玉门市规模以上工业企业数由50个减少为44个，敦煌市由46个减少为23个，肃北由24个减少为14个，瓜州县由32个增加到41个，但除瓜州县人口减少 $1 \times 1 0 ^ { 4 }$ 人外，其他县市人口均稳定，人类干扰强度减弱，流域整体景观生态风险等级下降。

总体来说，2000—2018年流域低景观生态风险面积增加 $1 1 3 1 . 1 9 \mathrm { k m } ^ { 2 }$ ，较低景观生态风险面积增加$1 0 3 4 . 1 0 \ \mathrm { k m } ^ { 2 }$ ，中景观生态风险等级面积增加$2 2 2 6 . 5 2 \mathrm { k m } ^ { 2 }$ ，较高和高景观生态风险等级面积共减少 $4 3 9 6 . 4 6 \mathrm { k m } ^ { 2 }$ 。

# 3.3景观生态风险空间差异驱动因子分析

因子探测器既能探测疏勒河流域景观生态风险的空间分异性，也能探测影响因子在多大程度上解释景观生态风险空间分异性。为方便计算， $\mathbf { X } _ { 1 }$ ）$\mathrm { X } _ { 2 } \ 、 \mathrm { X } _ { 3 } \ 、 \mathrm { X } _ { 4 } \ 、 \mathrm { X } _ { 5 } \ 、 \mathrm { X } _ { 6 } \ 、 \mathrm { X } _ { 7 }$ 和 $\mathrm { X } _ { 8 }$ 分别代表高程、坡度、降水、NDVI、最高气温、最低气温、人口密度和人为干扰度。

由图4可知，2000年决定力 $q$ 值从大到小依次为 $N _ { 8 } { > } \mathrm { X } _ { 4 } { > } \mathrm { X } _ { 5 } { > } \mathrm { X } _ { 3 } { > } \mathrm { X } _ { 1 } { > } \mathrm { X } _ { 6 } { > } \mathrm { X } _ { 2 } { > } \mathrm { X } _ { 7 }$ ，人为干扰度在影响景观生态风险变化的贡献量中排在首位，说明人为干扰度是疏勒河流域景观生态风险变化的主要控制因素，第二主导因素是NDVI,贡献率为0.2566，其次主导因素为高程、降水、最高和最低气温，人口密度是解释力最弱的一个因素，贡献率仅为0.0142。2010年的 $q$ 值排列变化与2000年一致。2018年与前2个时期的排列顺序稍有不同， $\mathrm { X } _ { 1 }$ 由前2个时期的第五排到第三, $\mathrm { X } _ { 5 }$ 则由第三降到第五。3个时期 $q$ 值对比可知，不同因子在不同年份变化不同， $\mathrm { X } _ { 1 } { \sim } \mathrm { X } _ { 6 }$ 的 $q$ 值在2000—2018年均呈现"V"型变化，即6类因子在2010年 $q$ 值最小，2018年 $q$ 值最高。 $X _ { 7 } { \sim } X _ { 8 }$ 则呈现"∧"型变化，2010年 $q$ 值最高。整体上，2000—2010年各因子决定力 $q$ 值接近,在2010—2018年 $q$ 值变化波动大，这与3个时期景观生态风险等级分布图变化一致。

![](images/c1251c8df32d8a5a2b72d45d8065f246138ee72d1ccd9031de42c7a1f7ecd5cf.jpg)  
干吴区地理  
图32000—2018年疏勒河流域景观生态风险空间变化 Fig.3Spatial changes of landscape ecological risk in the Shule River Basin from 20oO to 2018

![](images/e2a88183b238da75b3f4e6a2d33d7595383708d68c4e55b720a3b97690a1a48f.jpg)  
注 $: X _ { 1 } \setminus X _ { 2 } \setminus X _ { 3 } \setminus X _ { 4 } \setminus X _ { 5 } \setminus X _ { 6 } \setminus X _ { 7 }$ 和 $X _ { 8 }$ 分别代表高程、坡度、降水、NDVI、最高气温、最低气温、人口密度和人为干扰度。下同。图42000—2018年疏勒河流域景观生态风险因子解释力Fig.4Explanatory power of landscape ecological riskfactorsintheShuleRiverBasinfrom20oOto 2018

疏勒河流域景观生态风险空间分异的驱动因子交互探测结果显示(表6)，所选因子中任意2个因子的交互作用均大于单个因子，交互类型主要为双因子增强和非线性增强2种，说明疏勒河流域景观生态风险空间分异的结果不是由单一影响因子造成的，而是由多影响因素共同作用的结果。其中，2000年 $X _ { 8 }$ 与 $X _ { 3 }$ 交互作用的影响最强， $q$ 值最高为0.6848；交互影响程度达到0.6以上的还有： $X _ { 8 } \cap X _ { 1 }$ /$X _ { 2 } , X _ { 4 } , X _ { 5 }$ 和 $X _ { 6 }$ 。其他因子交互 $q$ 值虽然小于0.6，但也显示了双因子比单因子对于景观生态风险影响程度更高。2010年， $X _ { 8 }$ 与 $X _ { 5 }$ 交互作用最强， $q$ 值为0.7178，其他因子与 $X _ { 8 }$ 交互时， $\textit { q }$ 值均在0.6以上。2018年， $X _ { 8 }$ 与 $X _ { 4 }$ 交互时， $q$ 值最高，值为0.5757，自然因子之间交互作用增强，但贡献率均在0.45以下，只有自然因子和人类活动因子共同作用时，对景观生态风险的解释更强， $X _ { 8 }$ 作为主导因子影响疏勒河流域景观生态风险，同时与气候及地表因素的共同作用下，对景观生态风险分布影响最大。

疏勒河流域景观生态风险空间分析驱动因子之间的交互作用均大于单因子对景观生态风险的作用程度，不同因子之间的作用所形成的增强效应共同影响了流域景观生态风险在空间上分异效果。其中，3个时期人为十扰度与其他因子的交互作用均最高，明显表现出多因子作用增强的效果。

表62000—2018年疏勒河流域景观生态风险驱动因子交互影响  
Tab.6Interaction of driving factors of landscape ecological risk in the Shule River Basin from 2oo0 to 201   

<html><body><table><tr><td colspan="4">2000年</td><td colspan="4">2010年</td><td colspan="4">2018年</td></tr><tr><td>交互项</td><td>交互值</td><td>交互项</td><td>交互值</td><td>交互项</td><td>交互值</td><td>交互项</td><td>交互值</td><td>交互项</td><td>交互值</td><td>交互项</td><td>交互值</td></tr><tr><td>X∩X2</td><td>0.2474</td><td>X3∩X5</td><td>0.3824</td><td>XNX2</td><td>0.2421</td><td>X3∩X5</td><td>0.3576</td><td>X.∩X2</td><td>0.2554</td><td>X3∩X5</td><td>0.2962</td></tr><tr><td>X∩X3</td><td>0.3492</td><td>X∩X6</td><td>0.3247*</td><td>X∩X3</td><td>0.3327</td><td>X3∩X6</td><td>0.3221*</td><td>X∩X3</td><td>0.3163</td><td>X3∩X6</td><td>0.2993</td></tr><tr><td>Xi∩X4</td><td>0.3760</td><td>X3nX7</td><td>0.2074*</td><td>Xi∩X4</td><td>0.3692</td><td>X3nX7</td><td>0.2072*</td><td>X.NX4</td><td>0.4459</td><td>X3NX7</td><td>0.2621*</td></tr><tr><td>X∩X5</td><td>0.2479</td><td>X3nXs</td><td>0.6848</td><td>XNX5</td><td>0.2334</td><td>X3NXs</td><td>0.7024</td><td>X∩X5</td><td>0.2909</td><td>X3∩X8</td><td>0.5011</td></tr><tr><td>X.∩X6</td><td>0.2364</td><td>X4NX5</td><td>0.3960</td><td>XiNX6</td><td>0.2327</td><td>X4NX5</td><td>0.3769</td><td>X.∩X6</td><td>0.3028</td><td>X4NX5</td><td>0.4315</td></tr><tr><td>X.nX7</td><td>0.2092°</td><td>X4NX6</td><td>0.3791*</td><td>XnX7</td><td>0.2082*</td><td>X4NX6</td><td>0.3661*</td><td>X.nX7</td><td>0.2713°</td><td>X4NX6</td><td>0.4248</td></tr><tr><td>X.nXs</td><td>0.6456</td><td>X4∩X7</td><td>0.2770*</td><td>XnX8</td><td>0.6934</td><td>X4NX7</td><td>0.2974*</td><td>Xi∩X8</td><td>0.5239</td><td>X4∩X7</td><td>0.2735</td></tr><tr><td>X2∩X3</td><td>0.2423</td><td>X4NX8</td><td>0.6449</td><td>X2NX3</td><td>0.2464</td><td>X4NX8</td><td>0.6491</td><td>X2∩X3</td><td>0.2613</td><td>X4NX8</td><td>0.5757</td></tr><tr><td>X2NX4</td><td>0.3166</td><td>X5∩X6</td><td>0.2684</td><td>X∩X4</td><td>0.3249</td><td>X5NX6</td><td>0.2513</td><td>X2NX4</td><td>0.3276</td><td>X5NX6</td><td>0.2825</td></tr><tr><td>X2NX5</td><td>0.2680</td><td>X5nX7</td><td>0.2319*</td><td>XnX5</td><td>0.2535</td><td>X5nX7</td><td>0.2126*</td><td>X2NX5</td><td>0.2499</td><td>X5NX7</td><td>0.2686*</td></tr><tr><td>X2∩X6</td><td>0.2352°</td><td>X5∩X8</td><td>0.6845</td><td>X2∩X6</td><td>0.2227*</td><td>X5NXs</td><td>0.7178</td><td>X∩X6</td><td>0.2489</td><td>X5∩X8</td><td>0.5178</td></tr><tr><td>X2∩X7</td><td>0.1136°</td><td>X6NX7</td><td>0.1504*</td><td>X∩X7</td><td>0.1064</td><td>X6nX7</td><td>0.1250*</td><td>X2∩X7</td><td>0.1663°</td><td>X6nX7</td><td>0.2014*</td></tr><tr><td>X2NXs</td><td>0.6507</td><td>X6nX8</td><td>0.6665</td><td>X2∩X8</td><td>0.6794</td><td>X6nXs</td><td>0.6972</td><td>X2∩X8</td><td>0.4608</td><td>X6NXs</td><td>0.5333</td></tr><tr><td>XxOX4</td><td>0.4148</td><td>XnXs</td><td>0.5998</td><td>X3∩X4</td><td>0.4221</td><td>XnXs</td><td>0.6337</td><td>X3∩X4</td><td>0.4325</td><td>XnX8</td><td>0.4483*</td></tr></table></body></html>

注： $: \mathrm { X } _ { 1 } \ 、 \mathrm { X } _ { 2 } 、 \mathrm { X } _ { 3 } 、 \mathrm { X } _ { 4 } 、 \mathrm { X } _ { 5 } 、 \mathrm { X } _ { 6 } 、 2$ X和Xs分别代表高程、坡度、降水、NDVI、最高气温、最低气温、人口密度和人为干扰度;\*代表双因子t

从交互结果来看，人类活动因子与自然因子作用明显强于自然因子之间交互。

生态探测反映每2个因子对景观生态风险空间分布的影响是否具有显著差异，可以进一步验证主导的影响因子，并评价其作用机理的差异性。2000年生态探测图显示 $\mathrm { X _ { 1 } \cap X _ { 3 } \setminus X _ { 1 } \cap X _ { 5 } \setminus X _ { 1 } \cap X _ { 6 } \setminus X _ { 2 } \cap X _ { 6 } \setminus X _ { 3 } \cap }$ $\mathrm { X } _ { 5 } , \mathrm { X } _ { 4 } \cap \mathrm { X } _ { 5 }$ 为无显著差异；2010年生态探测图显示$\mathrm { X _ { 1 } } \cap \mathrm { X _ { 3 } } \setminus \mathrm { X _ { 1 } } \cap \mathrm { X _ { 5 } } \setminus \mathrm { X _ { 2 } } \cap \mathrm { X _ { 6 } } \setminus \mathrm { X _ { 2 } } \cap \mathrm { X _ { 7 } } \setminus \mathrm { X _ { 3 } } \cap \mathrm { X _ { 5 } } \setminus \mathrm { X _ { 6 } } \cap \mathrm { X _ { 7 } }$ 为无显著差异；2018年生态探测图显示 $\mathrm { X _ { 1 } } \cap \mathrm { X _ { 3 } } \setminus \mathrm { X _ { 1 } } \cap \mathrm { X _ { 4 } } \setminus \mathrm { X _ { 1 } } \cap \mathrm { X } _ { 5 } .$ $\mathrm { X } _ { 2 } \cap \mathrm { X } _ { 6 } \ 、 \mathrm { X } _ { 3 } \cap \mathrm { X } _ { 4 } \ 、 \mathrm { X } _ { 3 } \cap \mathrm { X } _ { 5 } \ 、 \mathrm { X } _ { 4 } \cap \mathrm { X } _ { 5 }$ 为无显著差异(图5）。从3个时期的显著性差异可以看出， $\mathrm { X } _ { 8 }$ 与其他因子均存在显著性差异，不存在显著性差异主要表现在自然因子内部。

# 4讨论

# 4.1景观生态风险时空分异特征

疏勒河流域景观生态风险空间分布北高南低，与潘竟虎等4研究结果一致，流域从北向南，海拔逐渐升高，温度逐渐降低，降水逐渐增加，景观类型从未利用地、荒漠、耕地、林地过渡到草地、冰川,景观生态风险随之降低。2000—2010年，整体景观生

![](images/f379985c8b0bf890e7c4afba42e2bb2e0173d59d859358eb2d7602b399f42237.jpg)  
注：Y为存在显著性差异;N为不存在显著性差异。  
图52000—2018年疏勒河流域景观生态风险驱动因子显著性差异

Fig.5Significant diferences in driving factors oflandscapeecological risk in the Shule River Basin from 20o0 to 2018

# 干吴区地理

态风险等级变化不大，主要在较高风险等级和高景观生态风险等级之间转换，景观生态风险增加的区域零星散状分布，景观生态风险等级下降的区域则主要集中在敦煌市和玉门市。2010—2018年，较高和高景观生态风险等级面积减少 $3 . 9 7 \%$ ,表明流域生态环境在整体上呈现好转趋势。康紫薇等[42]在同样处于干旱内陆区的玛纳斯河流域研究发现类似结果。造成景观生态风险高或者较高主要是受未利用地和城建用地影响，而景观生态风险等级较低和低的景观类型主要受林地、草地及园地影响，这与在博斯腾湖流域[43]、白龙江流域[44]、红河流域[45]和巢湖流域[46]等不同生态条件的研究结果一致;而与细河流域[47]不同,其主要是该流域北部工矿建设用地面积相对集中，受到人类干扰后的损失度低，因此景观生态风险低。划分景观生态风险网格，构建景观生态风险指数揭示了疏勒河流域景观生态风险时空特征，与研究区生态环境相吻合，说明在较短时间景观生态风险能够反映人类活动对其影响，但流域是一个复杂的综合体，虽通过景观生态风险网格客观反映景观生态风险，但网格划分是以等间距划分，对考虑流域内干湿、农牧交替区[48]等变化缺乏考察，须在日后研究中进行完善。

# 4.2驱动因素

驱动因子分析表明人为干扰度是影响景观生态风险空间分异的主要控制因子，人口密度影响最弱，与奚世军49对喀斯特山区流域综合生态风险驱动力分析结果相同。因子交互作用结果均为双因子增强和非线性增强，说明因子间两两交互作用比单因子作用对景观生态风险的影响更强，尤其表现在人为干扰度与其他因子交互。人为干扰度与其他因子均存在显著性差异，不存在显著性差异主要表现在自然因子。郑续等5研究该区域产水量时空特征时也发现人为干扰强度与其他因子之间的交互作用显著相关。由此可见，对于疏勒河流域景观生态风险调控来说主要是控制人类干扰度。鉴于人为活动因子包括一些政策性因素等由于数据获取和定量化具有一定难度，因此本研究并未过多考虑，实际上不同区域经济调控、生态保护政策的差异对景观生态风险的影响是巨大的，这也是未来研究的重点问题之一。

# 5结论

本文以疏勒河流域为研究对象，构建景观生态风险指数和利用地理探测器分析影响疏勒河流域景观生态风险的驱动因素，得出以下主要结论：

（1）通过对2000—2018年疏勒河流域斑块类型景观格局指数的分析，可以得到草地的斑块个数(NP)和景观形状指数(LSI)最高，未利用地的最大斑块指数(LPI)和聚集度指数(AI)最高，主要原因是草地和未利用地作为流域的主要景观类型，面积较大且分布较广。2000—2018年疏勒河流域景观蔓延度指数(CONTAG)呈下降趋势，而多样性指数(SHDI)和均匀度指数(SHEI)呈缓慢上升趋势，说明景观破碎程度不断上升

(2）2000—2018年疏勒河流域景观生态风险空间呈现北高南低分布特征。其中，较高景观生态风险等级下降 $3 . 3 0 \%$ ，高景观生态风险下降 $0 . 6 1 \%$ ，低、较低和中景观生态风险等级分别上升 $1 . 0 1 \% . 0 . 9 2 \%$ 和 $1 . 9 8 \%$ 。

（3）人为干扰度是影响景观生态风险空间分布的主要因子，NDVI次之，而人口密度影响最小。影响因子对景观生态风险的影响不是独立的，而是因子共同作用的结果。不同影响因子之间存在交互作用，且任意2种影响因子的作用值都大于任意一类单因子的值，其中人为干扰因子与其他因子交互作用显著，对景观生态风险的影响均为双因子增强或非线性增强。

# 参考文献(References)

[1]Cao Q, Zhang X,Lei D,et al. Multi-scenario simulation of landscape ecological risk probability to facilitate different decisionmaking preferences[J]. Journal of Cleaner Production,2O19,227: 325-335.   
[2] Turner M G.Landscape ecology:The effect of pattern on process [J].Annual Review of Ecology & Systematics,2003,2O(1):171- 197.   
[3] 谢小平,陈芝聪,王芳,等.基于景观格局的太湖流域生态风险 评估[J].应用生态学报,2017,28(10):3369-3377.[Xie Xiaoping,Chen Zhicong,Wang Fang,et al.Ecological risk assessment of Taihu Lake Basin based on landscape pattern[J]. Chinese Journal of Applied Ecology,2017,28(10): 3369-3377.]   
[4]卢远,苏文静,华璀,等.左江上游流域景观生态风险评价[J].热 带地理,2010(5):38-44.[Lu Yuan,Su Wenjing,Hua Cui,et al. Landscape ecologicalriskasessmentforupper Zuojiang River Basin[J]. Tropical Geography, 2010(5): 38-44.]   
[5]江恩慧,王远见,田世民,等.流域系统科学初探[J].水利学报, 2020,51(9): 1026-1037.[Jiang Enhui,Wang Yuanjian,Tian Shiming,et al. Exploration of watershed system science[J]. Journal of Hydraulic Enginering,2020,51(9): 1026-1037.]   
[6]曹祺文,张曦文,马洪坤,等.景观生态风险研究进展及基于生 态系统服务的评价框架:ESRISK[J].地理学报,2018,73(5): 843-855.[Cao Qiwen, Zhang Xiwen,Ma Hongkun,et al. Review of landscape ecological risk and an assessment framework based onecological services: ESRISK[J]. Acta Geographica Sinica, 2018, 73(5): 843-855.]   
[7]Wang H, Liu X M, Zhao C Y,et al.Spatial-temporal patern analysis of landscape ecological risk assessment based on land use/land cover change in Baishuijiang National Nature Reserve in Gansu Province,China[J]. Ecological Indicators,2021,124:107454,doi: 10.1016/j.ecolind.2021.107454.   
[8]Vinod K,Anket S,Shevita P,et al.A review of ecological risk assessment and associated health risks with heavy metals in sediment from India[J]. International Journal of Sediment Research, 2020,35(5): 516-526.   
[9]陈峰,李红波,张安录.基于生态系统服务的中国陆地生态风险 评价[J].地理学报,2019,74(3): 432-445.[Chen Feng,Li Hongbo,Zhang Anlu.Ecological risk assessment based on terrestrial ecosystem services in China[J]. Acta Geographica Sinica,2019,74 (3): 432-445.]   
[10] 张月,张飞,周梅,等.干旱区内陆艾比湖区域景观生态风险评 价及时空分异[J].应用生态学报,2016,27(1):233-242.[Zhang Yue, Zhang Fei, Zhou Mei, etal.Landscape ecological risk assessment and its spatio-temporal variations in Ebinur Lake region of inland arid area[J]. Chinese Journal of Applied Ecology,2016,27 (1): 233-242.]   
[11] Xing L, Hu M S,Wang Y. Integrating ecosystem services value and uncertainty into regional ecological risk assessment:A case study of Hubei Province, Central China[J]. Science of the Total Environment,2020,740:140126,doi: 10.1016/j.scitotenv.2020.1401 26.   
[12] 马胜,梁小英,刘迪,等.生态脆弱区多尺度景观生态风险评价 -以陕西省米脂县高渠乡为例[J].生态学杂志,2018,37 (10): 3171-3178.[Ma Sheng,Liang Xiaoying,Liu Di, et al. Multiscale landscape ecological risk assessment in ecologically fragile regions: A case study in Gaoqu Town in Mizhi County,Shaanxi Province[J]. Chinese Journal of Ecology，2018,37(10):3171- 3178.]   
[13]Arenas-Sánchez A, Rico A, Rivas-Tabares D,et al. Identification of contaminants of concern in the upper Tagus River Basin (central Spain). Part 2: Spatio-temporal analysis and ecological risk assessment[J]. Scienceof the Total Environment,2019,667: 222-233.   
[14]Ayre K K,Landis W G.A Bayesian approach to landscape ecological risk assessment applied to the Upper Grande Ronde Watershed,Oregon[J]. Human and Ecological Risk Assessment: An International Journal,2012,18(5): 946-970.   
[15] Chow TE,Gaines KF, Hodgson M E.et al. Habitat and exposure modelling for ecological risk assessment: A case study for the raccoon on the Savannah River site[J]. Ecological Modelling,2005, 189(1-2): 151-167.   
[16] 彭建,党威雄,刘焱序,等.景观生态风险评价研究进展与展望 [J].地理学报,2015,70(4):664-677.[Peng Jian,Dang Weixiong, Liu Yanxu, et al. Review on landscape ecological risk assessment [J].Acta Geographica Sinica, 2015,70(4): 664-677.]   
[17]Yang T, Zhang Q,Wan X B,et al. Comprehensive ecological risk assessment for semi-arid basin based on conceptual model of risk response and improved TOPSIS model: A case study of Wei River Basin,China[J]. Science of the Total Environment,2020,719: 137502,doi: 10.1016/j.scitotenv.2020.137502.   
[18] 李青圃,张正栋,万露文,等.基于景观生态风险评价的宁江流 域景观格局优化[J].地理学报,2019,74(7):1420-1437.[Li Qingpu, Zhang Zhengdong, Wan Luwen,et al. Landscape pattern optimization in Ningjiang River Basin based on landscape ecological risk assessment[J].Acta Geographica Sinica,2019,74(7):1420- 1437.]   
[19] 郑杰,王志杰,喻理飞,等.基于景观格局的草海流域生态风险 评价[J].环境化学,2019,38(4):784-792.[Zheng Jie,Wang Zhijie,Yu Lifei,et al.Ecological risk assessment of Caohai Watershedbasedonlandscapepatern[J].Environmental Chemistry, 2019,38(4): 784-792.]   
[20]王劲峰,徐成东.地理探测器:原理与展望[J].地理学报,2017, 72(1):116-134.[Wang Jinfeng,Xu Chengdong.Geodetector: Principle and prospective[J].Acta Geographica Sinica,2017,7(1): 116-134.]   
[21]Wang JF,LiX H,Christakos G,etal.Geographical detectorsbased health risk assessment and its application in the neural tube defects study of the Heshun Region,China[J]. International Journal of Geographical Information Science,2010,24(1): 107-127.   
[22] Tian F,Liu L Z, Yang JH,etal. Vegetation greening in more than 94% of the Yellow River Basin (YRB) region in China during the $2 1 ^ { \mathrm { s t } }$ century caused jointly by warming and anthropogenic activities [J].Ecological Indicators，2021，125:107479,doi:10.1016/j. ecolind.2021.107479.   
[23] 罗瑶,彭文甫,董永波,等.基于地理探测器下的川西高原地表 温度空间格局及影响因子分析——以西昌市为例[J].干旱区 地理,2020,43(3): 738-749.[Luo Yao,Peng Wenfu,Dong Yongbo,et al. Geographical exploration of the spatial patern of the surface temperature and its influencing factors in western Sichuan Plateau: A case of Xichang City[J].Arid Land Geography,2020,43 (3): 738-749.]   
[24] Xu L,Du HR, Zhang X L.Driving forces of carbon dioxide emissions in China's cities:An empirical analysis based on the geodetector method[J].Journal of Cleaner Production，2O21,287: 125169,doi: 10.1016/j.jclepro.2020.125169.

# 干吴区地理

[25] 潘洪义,黄佩,徐婕.基于地理探测器的岷江中下游地区植被 NPP时空格局演变及其驱动力研究[J].生态学报,2019,39(20): 7621-7631.[Pan Hongyi,Huang Pei, Xu Jie.The spatial and temporal pattern evolution of vegetation NPP and its driving forces in middle-lower areas of the Min River based on geographical detector analyses[J]. Acta Ecologica Sinica,2019,39(20): 7621-7631.]   
[26] Yuan L H, Chen X Q,Wang X Y,et al. Spatial associations between NDVI and environmental factors in the Heihe River Basin [J]. Journal of Geographical Sciences,2019,29(9): 1548-1564.   
[27] 张思源,聂莹,张海燕,等.基于地理探测器的内蒙古植被NDVI 时空变化与驱动力分析[J].草地学报,2020,28(5):1460-1472. [Zhang Siyuan, Nie Ying, Zhang Haiyan, etal. Spatiotemporal variation of vegetation NDVI and its driving forces in Inner Mongolia based on geodetector[J]. Acta Grasslandica,2020,28(5):1460- 1472.]   
[28] 孙道亮,洪步庭,任平.都江堰市农村居民点时空演变与驱动因 素研究[J].长江流域资源与环境，2020,29(10):2167-2176. [Sun Daoliang, Hong Buting,Ren Ping.Study on the spatiotemporal evolution and driving factors ofruralsettlements in Dujiangyan City[J].Resources and Environment in the Yangtze Basin,2020, 29(10): 2167-2176.]   
[29]Xie Z X, Qin YC,LiY,et al. Spatial and temporal differentiation of COVID-19 epidemic spread in mainland China and its influencing factors[J]. Science of the Total Environment,2020,744: 140929,doi: 10.1016/j.scitotenv.2020.140929.   
[30] 王琳,赵俊三.城市群新冠疫情时空分布格局与分异机制的地 理探测[J].生态学报,2020,40(19): 6788-6800.[Wang Lin,Zhao Junsan. Spatiotemporal distribution pattern of the COVID-19 epidemic and geographical detection[J].Acta Ecologica Sinica, 2020, 40(19): 6788-6800.]   
[31] 潘竟虎,胡艳兴.疏勒河中下游近35年土地利用与景观格局动 态[J].土壤,2014,46(4): 742-748.[Pan Jinghu,Hu Yanxing. Dynamic change of land use & landscape pattern in middle and lower reaches of Shule River during recent 35 years[J]. Soils,2014,46 (4): 742-748.]   
[32] 吴金华,房世峰,刘宝军,等.乌裕尔河-双阳河流域湿地景观 格局演变及其驱动机制[J].生态学报,2020,40(13):4279- 4290.[Wu Jinhua,Fang Shifeng,Liu Baojun,etal.Landscape pattern evolution of wetland and its driving mechanism in Wuyuer-Shuangyang River Basin[J].Acta Ecologica Sinica,2020,40(13): 4279-4290. ]   
[33] 贾艳艳,唐晓岚,刘振威,等.1995—2016年长江沿岸芜湖区段 景观格局梯度分析[J].地域研究与开发,2020,39(4):115-121. [Jia Yanyan,Tang Xiaolan, Liu Zhenwei,et al. Gradient analysis of landscape pattern in Wuhu Section along the Yangtze River from 1995 to 2016[J].Areal Research and Development,2020,39 (4): 115-121.]   
[34] 徐启渝,王鹏,王涛,等.土地利用结构与景观格局对鄱阳湖流 域赣江水质的影响[J].湖泊科学,2020,32(4):1008-1019.[Xu Qiyu,Wang Peng,Wang Tao,etal.Investigation of the impacts of land use structure and landscape pattern on water quality in the Ganjiang River,Poyang Basin[J]. Journal of Lake Science, 2020, 32(4): 1008-1019.]   
[35] 秦艳丽,时鹏,何文虹,等.西安市城市化对景观格局及生态系 统服务价值的影响[J].生态学报,2020,40(22):1-12.[Qin Yanli, Shi Peng,He Wenhong,et al.Influence of urbanization onlandscape pattern and ecosystem service value in Xi'an City[J]. Acta Ecologica Sinica, 2020,40(22): 1-12.]   
[36] 娄妮,王志杰,何嵩涛.基于景观格局的阿哈湖国家湿地公园景 观生态风险评价[J].水土保持研究,2020,27(1):233-239.[Lou Ni,Wang Zhijie,He Songtao.Assessment on ecological risk of Aha Lake National Wetland Park based on landscape patern[J]. Research of Soil and Water Conservation,2020,27(1): 233-239.]   
[37] 王涛,肖彩霞,刘娇,等.杞麓湖流域景观时空格局演变及其对 景观生态风险的影响[J].水土保持研究,2019,26(6):219-225. [Wang Tao,Xiao Caixia,Liu Jiao,etal.Evolution of spatial and temporal paterns of landscape and its impact on landscape ecological risk in Qilu Lake Basin[J]. Research of Soil and Water Conser vation,2019,26(6): 219-225.]   
[38] Zhang C Q,Dong B,Liu LP,etal. Studyon ecological risk assesment for land-use of wetland based on different scale[J]. Journal of the Indian Society of Remote Sensing,2015,44(5): 1-8.   
[39] 陈鹏,傅世锋,文超祥,等.1989—2010年间厦门湾滨海湿地人 为干扰影响评价及景观响应[J].应用海洋学学报,2014,33(2): 167-174.[Chen Peng,Fu Shifeng,Wen Chaoxiang,et al.Assessment of the impact on coastal wetland of Xiamen Bay and response of landscape pattern from human disturbance from 1989 to 2010[J]. Journal of Applied Oceanography，2014,33(2):167- 174.]   
[40] 孙永光,赵冬至,吴涛,等.河口湿地人为干扰度时空动态及景 观响应——以大洋河口为例[J].生态学报,2012,32(12):3645- 3655.[Sun Yongguang, Zhao Dongzhi,Wu Tao,et al. Temporal and spatial dynamic changes and landscape patern response of hemeroby in Dayang estuary of Liaoning Province,China[J].Acta Ecologica Sinica, 2012,32(12): 3645-3655.]   
[41] 潘竞虎,刘晓.疏勒河流域景观生态风险评价与生态安全格局 优化构建[J].生态学杂志,2016,35(3):791-799.[Pan Jinghu, Liu Xiao.Landscape ecological risk assessment and landscape security pattern optimization in Shule River Basin[J].Journal of Ecology,2016,35(3): 791-799.]   
[42] 康紫薇,张正勇,位宏,等.基于土地利用变化的玛纳斯河流域 景观生态风险评价[J].生态学报,2020,40(18):6472-6485. [Kang Ziwei, Zhang Zhengyong,Wei Hong,et al. Landscape ecological risk assessment in Manas River Basin based on land use change[J]. Acta Ecologica Sinica, 2020,40(18): 6472-6485.]   
[43] 位宏,徐丽萍,李晓蕾,等.博斯腾湖流域景观生态风险评价与 时空变化[J].环境科学与技术,2018,41(增刊1):345-351.[Wei Hong,Xu Liping,Li Xiaolei, et al.Landscape ecological risk as sessment and its spatiotemporal changes of the Bosten Lake Basin [J]. Environmental Science & Technology,2018,41(Suppl.1): 345-

# 351.]

[44]巩杰,谢余初,赵彩霞,等.甘肃白龙江流域景观生态风险评价 及其时空分异[J].中国环境科学，2014,34(8):2153-2160. [Gong Jie,Xie Yuchu,Zhao Caixia,etal.Landscape ecological risk assessment and its spatiotemporal variation of Bailong Watershed,Gansu[J]. China Environmental Science,2O14,34(8):2153- 2160.]

[45]刘世梁,刘琦,张兆苓,等.云南省红河流域景观生态风险及驱 动力分析[J].生态学报,2014,34(13):3728-3734.[Liu Shiliang, Liu Qi, Zhang Zhaoling,et al. Landscape ecological risk and driving force analysis in Red River Basin[J].Acta Ecologica Sinica, 2014,34(13): 3728-3734.]

[46] 黄木易,何翔.近20年来巢湖流域景观生态风险评估与时空演 化机制[J].湖泊科学,2016,28(4):785-793.[Huang Muyi,He Xiang.Landscape ecological risk assessment and its mechanism in Chaohu Basin during the past almost 2O years[J].Lake Science, 2016,28(4): 785-793.]

[47]吕乐婷,张杰,孙才志,等.基于土地利用变化的细河流域景观 生态风险评估[J].生态学报,2018,38(16):5952-5960.[Lu Leting, Zhang Jie, Sun Caizhi, etal. Landscape ecological risk assessment of Xi River Basin based on land-use change[J].Acta Ecologica Sinica,2018,38(16): 5952-5960.]

[48]张学斌,石培基,罗君,等.基于景观格局的干旱内陆河流域生 态风险分析—以石羊河流域为例[J].自然资源学报,2014, 29(3):41O-419.[Zhang Xuebin,Shi Peiji,Luo Jun,etal. The ecological risk analysis of arid inland river basin at the landscape scale:A case study on Shiyang River Basin[J]. Journal of Natural Resources,2014,29(3): 410-419.]

[49]奚世军.喀斯特山区流域综合生态风险评估及其驱动力分析 一以贵州乌江流域为例[D].贵阳:贵州师范大学,2020.[Xi Shijun. Comprehensive ecological risk assessment and driving force analysis of karst mountain basin: A case study of Wujiang River Basin,Guizhou Province[D]. Guiyang:Guizhou Normal University,2020.]

[50] 郑续,魏乐民,郭建军,等.基于地理探测器的干旱区内陆河流 域产水量驱动力分析——以疏勒河流域为例[J].干旱区地理， 2020,43(6): 1477-1485.[Zheng Xu,Wei Lemin,Guo Jianjun,et al.Driving force analysis of water yield in inland river basins of arid areas based on geo-detectors:A case of the Shule River[J].Arid Land Geography,2020,43(6): 1477-1485.]

# Landscape ecological risk assessment and driving factors of the Shule River Basin based on the geographic detector model

SUN Lirong'， ZHOU Dongmei'， CEN Guozhang'， MA Jing',DANG Rui²， NI Fan'， ZHANG Jun1³(1.College of Resources andEnvironmental Science,Gansu Agricultural University,Lanzhou 73oo7o,Gansu,China;2.School of Management,Gansu Agricultural University,Lanzhou 73OO70, Gansu, China;3.GansuProvincial Water-Saving AgriculturalEngineering TechnologyResearch Center,Lanzhou73OO70,Gansu,China)

Abstract:The Shule River Basin isa typical arid inland river basin with an extremely fragile ecological environment. It is alsooneof the most important ecologicalbariers of northwest China.This study analyzes the spatial and temporal variation characteristics of the landscape ecological risk in the Shule River Basin with land use data from 20o0 to 2018 using Fragstats software.First,the results show thatthe main landscape types in the Shule River Basin are unused land and grassland with high number of patches (NP),landscape shape index (LSI), largest patch index (LPI),and aggregation index (AI) values. The contagion (CONTAG) value dramatically declined,while the Shannon’s diversity index (SHDI) and Shannon's evenness index (SHEI) values slowly increased during the period from 2000 to 2018.This indicates that the landscape fragmentation is serious in the basin.Second,the landscape ecological risk in the Shule River Basin in the north was higher than that in the south,and a gradual downward trend was observed from 20o0 to 2O18,especially for the high-risk area.Third, human disturbance is the main factor affecting the spatial distribution of the landscape ecological risk,followed by NDVI and population density.The impact of the landscape ecological risk was double factor or nonlinear enhancement.No significant differences were found between natural and natural factors，while significant differences were determined between natural and anthropogenic factors.

Key words: landscape ecological risk; landscape pattern; geodetector; Shule River Basin