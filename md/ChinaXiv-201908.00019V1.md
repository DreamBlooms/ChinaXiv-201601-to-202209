# 基于多源数据的西藏东南部历史干旱监测与分析

熊俊楠¹²，李伟'，刘志奇³，程维明²，范春捆4，张昊

（1西南石油大学土木工程与建筑学院，四川成都610500；2中国科学院地理科学与资源研究所资源与环境信息系统国家重点实验室,北京100101;3四川省煤田测绘工程院,四川 成都610072；4 西藏自治区农牧科学院农业研究所,西藏拉萨 850000）

摘要：干旱作为频发的全球性自然灾害之一，造成了严重的社会、经济和生态环境问题。以西藏主要耕作区为研究区,2001—2015年MODIS、TRMM和 SRTM-DEM数据为数据源，利用植被状态指数（VCI)、温度条件指数(TCI)和降水状态指数(PCI)等模型参量，采用空间主成分分析方法构建区域干旱综合监测模型，对模型精度和可靠性进行检核验证，并以所建模型对研究区2001—2015 年逐月干旱进行识别,采用地理时空分析方法对研究区干旱变化特征及趋势进行研究。结果表明，干旱综合监测指数(DCMI)能够较好地反映区域土壤相对湿度与标准化降水蒸散指数(SPEI)的变化，干旱综合监测模型具有较好的适用性;研究区全年干旱频率在空间分布上呈现出西高东低的特征，大部分地区干旱频率小于 $20 \%$ ，约 $1 2 . 4 1 \%$ 的区域干旱频率超过 $20 \%$ ；从不同等级干旱发生频率来看，日喀则市为轻旱、中旱易发区，重旱易发区则集中于日喀则市和昌都市的中部及东部地区；区域月际干旱频率空间格局差异较大，全年干旱易发生于1、8、11月等月份，局部地区干旱易发月份存在差异；区域年内旱情变化趋势差异性较大，10月～次年9月，旱情加剧区域呈现出随月份变化由耕作区东部向西部逐渐转移的趋势。

关键 词：多源数据；干旱；监测；西藏文章编号： 1000-6060(2019)04-0735-10(0735\~0744)

干旱作为频发的全球性自然灾害之一，造成了严重的社会、经济和生态环境问题，对区域粮食安全和社会稳定构成严重威胁[1]。我国作为农业大国，长年以来饱受干旱影响。青藏高原地区农业生产及作物生长与区域复杂的气候环境、地形构造紧密相关。因此，针对高原地区独特的地理位置与气候环境，研究适合的旱情监测模型显得尤为必要。

由于干旱受到多种因素影响，单一要素往往难以表征全面的农业干旱信息。近年来，很多学者尝试利用多源遥感数据构建全面的干旱指数模型来进一步提高干旱监测精度。KOGAN 等[2]基于多年的植被指数数据，通过提出植被状态指数（VCI)，并结合VCI与温度条件指数(TCI)提出更具优势的植被健康指数（VHI)来进行旱情监测。TADESSE 等[3]利用分类回归树模型(CART)数据挖掘的方法结合遥感数据来进行干旱监测。RAJSEKHAR 等[4]综合考虑降水、蒸发以及土壤湿度等因素提出多变量干旱指数(MDI)用于气象干旱、农业干旱以及水文干旱的监测。ZHANG 等[5]研究发现与其他单一指数相比，降水状态指数(PCI)几乎与所有短期干旱的相关性更强。不少研究还发现，土地覆盖类型( $( L C )$ 是土壤水分空间变异的主要影响因子[6；使用TRMM、MODIS等数据结合气象站点干旱指数，利用数据挖掘算法可以较好地建立综合干旱监测模型[7-8]。此外,杜灵通等[9]结合降水、地表温度和植被指数数据构建出综合干旱监测指数（SDI)，并取得较好的监测效果。然而，目前国内针对区域干旱监测的研究大多集中于干旱监测指数、监测模型构建与验证、干旱发生过程及影响范围的探讨，而采用多源、长时序数据建立综合干旱监测模型，对研究区长时间周期内逐月干旱进行识别、分析其时空变化规律及趋势等方面的研究还相对较少。而历史干旱识别、时空格局及变化趋势分析，是区域干旱研究与应对的重要内容。

选取地处西藏自治区东南部的拉萨、日喀则等5市为研究区，以MODIS、TRMM和SRTM-DEM为数据源，综合分析研究区气象降水亏缺、地表蒸散、地形等因素，选取VCI、TCI和PCI等模型参量，采用空间主成分分析方法构建了研究区干旱综合监测模型，并对模型的精度和可靠性进行检核验证。在此基础上对研究区2001—2015年逐月干旱进行识别和重建。通过时空分析方法，分析研究区历史干旱时空格局及其演化趋势，旨在为青藏高原地区历史干旱时空规律与区域干旱监测预测的研究提供借鉴，为开展区域防旱抗旱工作提供科学参考。

# 研究区概况及数据源

# 1.1 研究区概况

研究区位于青藏高原的东南部、西藏自治区的藏南谷地和藏东峡谷地，主要包括拉萨、昌都、林芝、山南和日喀则5个市（图1）的56个区（县）,区域面积约 $5 1 . 6 9 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,平均海拔均在$3 \ 0 0 0 \ \mathrm { m }$ 以上，耕种土壤面积占全区耕种土壤面积的 $9 7 . 4 3 \%$ ，是西藏自治区最主要的农业区。研究区内气候分布多样，光照充足，年均气温 $3 . 6 ~ \mathrm { { ^ { c } } }$ ，年均降水量 $4 2 0 ~ \mathrm { { m m } }$ 左右，全年日照时间均在$2 \ 0 0 0 \ \mathrm { h }$ 以上，无霜期 $1 0 0 \sim 1 8 0 \mathrm { ~ d ~ }$ 。据不完全统计，1983—2013年间全区共发生大小旱灾350余次，其中拉萨市、昌都市等5市共计308 次，占全区旱灾总数的 $8 5 \%$ 以上。

# 1.2数据源与预处理

研究数据包括覆盖研究区的2001—2015年的植被指数数据（MOD13A3）、地表温度数据（MOD11A2）土地覆盖数据（MCD12Q1）、降水数据（TRMM3B43）、SRTM-DEM数据和气象站点数据，数据主要来源如表1所示。由于MCD12Q1土地覆盖数据只更新至2013年，故文中2014年、2015年地表覆盖数据以2013年替代。

研究过程中利用MRT（MODISReprojectionTool)软件对MODIS数据进行拼接、投影转换，应用ArcGIS10.2对影像数据进行裁剪。为保证数据的完整性，使用质量控制文件剔除MODIS影像中的无效值，并利用多年均值填充算法对同区域无效值进行补充。为统一数据时空尺度，将8d地表温度数据，利用最大值合成法生成地表温度月值数据，将地表覆盖产品重采样为 $1 ~ \mathrm { k m }$ 分辨率。利用ENVI5.1对TRMM3B43进行预处理，并结合增强型植被指数[1]（EVI)采用GWR模型对合成月降水数据进行降尺度处理。

![](images/0ab24914ed776a3056b99d97448ab740bca665baa140f624158da1cae8b1d960.jpg)  
图1研究区主要河流及高程分布  
Fig.1Major rivers and elevations in the study area

表1监测模型主要数据来源  
Tab.1 Monitoring model main data source   

<html><body><table><tr><td>数据名称</td><td>空间 分辨 率</td><td>时间 分辨 率</td><td>数据 量</td><td>数据来源</td></tr><tr><td>植被指数产品 （MOD13A3)</td><td>1 km</td><td>月值</td><td>5景/期× 12 https://mirador. 期/年×15a</td><td>gsfc. nasa. gov</td></tr><tr><td>地表温度产品 （MOD11A2）</td><td>1 km</td><td>8d</td><td>5景/期× 46 https://mirador. 期/年×15a</td><td>gsfc. nasa.gov</td></tr><tr><td>土地覆盖产品 (MCD12Q1)</td><td>500 m</td><td>年值</td><td>2001—2013年</td><td>https://lpdaac. usgs. gov</td></tr><tr><td>降水产品 （TRMM3B43)</td><td>0.25°</td><td>月值</td><td>12期/年×15a</td><td>https://mirador. gsfc. nasa. gov</td></tr><tr><td>数字高程模型 (SRTM-DEM)</td><td>1 km</td><td></td><td>1</td><td>http://www. cgiar-csi. org</td></tr><tr><td>气象站点</td><td></td><td></td><td>1</td><td>http://www. resdc. cn/</td></tr></table></body></html>

# 2干旱监测模型构建及验证

综合考虑研究区植被覆盖状况、地表温度、降水情况、土地覆盖以及高程分布5种影响因子，本文将选取 $V C I \ 、 T C I \ 、 P C I \ 、 L C \ 、 D E M$ 来构建高原地区干旱指数监测模型，模型参量如表2所示。

# 2.1 模型参量计算

2.1.1 VCI 指数植被通常对干旱有着明显的响应。当植被叶片枯萎、凋零和覆盖减少时均会引起植被敏感波段反射率的变化，从而可以利用遥感影像进行探测。增强型植被指数 $( E W I )$ 与归一化植被指数(NDVI)相比，具有比NDVI更高的稳定性，能更有效的反映植被覆盖与变化情况[11]。由于 EVI难以反映时间序列上植被的长势变化，因此本文选择由 $\mathrm { K O G A N } ^ { [ 1 2 ] }$ 提出的VCI来反映植被的生长状况,其计算公式为[10]：

Tab.2Monitoring model construction index selection   

<html><body><table><tr><td>干旱影指标 响因素</td><td>选取</td><td>指标含义</td></tr><tr><td>植被 覆盖</td><td>VCI</td><td>该指数是衡量植被受环境胁迫程度的指标，反 映短期天气信号对植被的影响，能有效监测干 旱及降水的时空分布特征</td></tr><tr><td>气候 状况</td><td>TCI</td><td>该指数强调温度条件与植被长势的关系，在植 被稀疏及作物播收期均可监测，视为旱情监测 的初始指标</td></tr><tr><td></td><td>PCI</td><td>干旱发生的直接原因大部分为降水异常，该指 数可有效监测干旱及降水的时空分布特征</td></tr><tr><td>地表 环境</td><td>LC</td><td>不同LC类型会改变土壤性质及土壤结构，影响 王壤的持水能力和水分调节能力，从而影响土 壤含水量</td></tr><tr><td>地势 影响</td><td>DEM</td><td>特殊的地形可形成独特局部的小气候，间接影 响土壤水分的含量和分布</td></tr></table></body></html>

$$
V C I _ { i } = \frac { E V I _ { i } - E V I _ { m i n } } { E V I _ { m a x } - E V I _ { m i n } }
$$

式中： $V C I _ { i }$ 为 $i$ 月的植被状态指数; $E V I _ { i }$ 为 $i$ 月的增强型植被指数值； $E V I _ { m a x }$ 为多年时间序列中 $i$ 月增强型植被指数的最大值； $E V I _ { \min }$ 为多年时间序列中 $i$ 月增强型植被指数的最小值。其值域范围在[0，1」之间,通常高值表示该月较为湿润,植被生长良好，反之亦然。

2.1.2TCI指数已有研究表明，干旱通常会伴随着明显的植被冠层温度异常[13]。TCI可通过遥感的热应力指标地表温度(LST)来确定相关的干旱现象。其原理是植被冠层或土壤表面温度随着水分胁迫的增加而增加，不受作物生长季节的限制，适用于长时间序列及大区域的相对干旱监测[14],即

$$
T C I _ { i } = \frac { L S T _ { m a x } - L S T _ { i } } { L S T _ { m a x } - L S T _ { m i n } }
$$

式中： $T C I _ { i }$ 为 $\mathbf { \chi } _ { i }$ 月的温度条件指数; $L S T _ { i }$ 为 $\mathbf { \chi } _ { i }$ 月的地表温度值; $L S T _ { m a x }$ 为多年时间序列中 $i$ 月地表温度的最大值; $L S T _ { m i n }$ 为多年时间序列中 $i$ 月地表温度的最小值。其值域范围在[0,1]之间,TCI越接近于0,该月越干旱，植被生长越差，反之亦然。

2.1.3PCI指数降水指标是干旱的内在表现，长时间无有效降水或降水量较历年同期明显偏少时通常会发生旱灾。降水的多少代表干湿的程度，干旱年份的降水量与正常年份的降水量往往差异较大。选取与VCI及TCI类似的基于降水时间序列变化的$P C I ^ { [ 1 5 ] }$ 作为模型参量,应用热带测雨任务卫星(TRMM)数据参与计算，即

$$
P C I _ { i } = \frac { T R M M _ { i } - T R M M _ { m i n } } { T R M M _ { m a x } - T R M M _ { m i n } }
$$

式中： $P C I _ { i }$ 为 $\mathbf { \chi } _ { i }$ 月的降水状态指数； $T R M M _ { i }$ 为 $\mathbf { \chi } _ { i }$ 月的降水量; $T R M M _ { m a x }$ 为多年时间序列中 $i$ 月降水量的最大值; $T R M M _ { \operatorname* { m i n } }$ 为多年时间序列中 $\mathbf { \chi } _ { i }$ 月降水量的最小值。在降水较历年同期均值明显偏少时， $P C I$ 接近或等于0,表明越干旱，反之亦然。

2.1.4 LC $L C$ 对干旱的发生也有一定的影响，通常不同的 $L C$ 类型土壤含水量会存在差异。与荒地相比,植被能够改善土壤结构，增强土壤的持水能力。森林和林地对土壤水分具有较高的保持力，草地和农田则只能利用表层土壤的水分，当出现长时间的降水短缺或高温蒸散，便会因土壤表层含水量下降、供水短缺发生干旱。本文依据不同 $L C$ 类型对于水分的保持能力和对干旱的响应程度，参考夏文韬等[16]对MCD12Q1数据的等级赋值法将土地重分类为荒地、农耕地等6类(表3）。由于 $L C$ 类型为年值数据，则每月的LC类型对应同年的重分类结果。

2.1.5DEM地形因素对土壤水分有着重要影响。高海拔地区的太阳辐射、能量交换和蒸散发过程与低海拔地区差异较大，会对干旱发生细节产生影响[9]。对于地形因素而言,研究区域内海拔较高的地区发生干旱灾害的几率较小，反之海拔相对较低的河谷地区则是旱灾的高发区。由于描述地形变化的数字高程模型（DEM）、 $L C$ 与VCI、TCI以及PCI的量纲不同，对计算结果影响较大，故对二者采用极差标准化处理，即

表2监测模型构建指标选取  
表3LC重分类Tab.3LC reclassification  

<html><body><table><tr><td>MCD12Q1IGBP分类编码</td><td>重分类结果</td></tr><tr><td>16荒漠或荒地</td><td>1荒地</td></tr><tr><td>12 农田、14农田自然植被的交错带</td><td>2农耕地</td></tr><tr><td>8木本稀树草原、9稀树草原、10草地</td><td>3草地</td></tr><tr><td>1 常绿针叶林、2 常绿阔叶林、3 落叶针叶林、</td><td>4林地</td></tr><tr><td>4 落叶阔叶林、5混生林、6郁闭灌丛、7稀疏灌丛</td><td></td></tr><tr><td>13城市和建筑区</td><td>5城镇建设用地</td></tr><tr><td>0水体、11永久湿地、15 冰雪</td><td>6水体</td></tr></table></body></html>

$$
{ x _ { i j } } ^ { \prime } = \frac { x _ { i j } - x _ { m i n } } { x _ { m a x } - x _ { m i n } }
$$

式中： $i , j$ 为经纬度； ${ x _ { i j } } ^ { \prime }$ 为 $( i , j )$ 处像元标准化后的像元值； $x _ { i j }$ 为 $( i , j )$ 处像元值； $x _ { m a x }$ 为同期影像像元最大值； $x _ { m i n }$ 为同期影像像元最小值。

# 2.2 模型构建

以2001—2015年逐月对应的VCI、TCI、PCI与同期标准化后的 $L C$ 类型和DEM数据为指标，利用ArcGIS 进行空间主成分分析（SPCA）[17],提取累计贡献率大于 $8 5 \%$ 的前 $n$ 个主成分，对主成分进行加权求和计算，得到研究区干旱综合监测指数（DC-MI)，权重系数为各主成分对应的贡献率（图2），即

$$
D C N I = \sum _ { i = 1 } ^ { n } \alpha _ { i } P C _ { i }
$$

式中： $P C _ { i }$ 为第 $i$ 个主成分; $\alpha _ { i }$ 为第 $i$ 个主成分对应的贡献率。

# 2.3模型验证及等级划分

2.3.1模型验证为了验证构建的干旱综合监测模型的实用性与准确性，采用土壤相对湿度与逐月标准化降水蒸散指数[18]（SPEI)作为验证指标，通过与模型计算结果的对比分析，实现对模型的定量评价，检测其监测效果。

土壤相对湿度验证，通过研究区内拉萨站等4个农业气象站点2001—2013年（数据截止至 2014年)数据，在剔除缺失值后，利用逐月平均 $1 0 \ \mathrm { c m }$ 土壤相对湿度对干旱综合监测模型进行验证。农业气象站点对应的DCMI取站点周边 $3 \times 3$ 区域内的像元均值，以此来消除个别像元值异常变化带来的误差，最后利用SPSS软件进行相关性的计算分析。研究区农业气象站点分布如图3所示，相关性验证结果如表4所示。

![](images/78926e4b2a6c85836cf6d5af761fcaf222465099016691b49b2c25cd89f43bc6.jpg)  
图2模型构建流程  
Fig.2Model building process   
Fig.3Meteorological site distribution in the study area

![](images/579a8001faf4d442dd5348d2d4a89a4517eb0b90330eb605262893a11924b5a8.jpg)  
图3 研究区气象站点分布

SPEI指数验证，通过研究区内28个气象站点2001—2015年逐月SPEI指数对模型结果进行验证。通过提取农业气象站点周边 $3 \times 3$ 区域内的DCMI像元均值与SPEI指数进行对比，应用SPSS软件对数据进行相关性的计算分析。1～12月相关性验证结果如表5所示。

结果表明DCMI与土壤相对湿度及SPEI存在一定的相关性，且相关性达到极显著的水平。农业气象站点土壤相对湿度与DCMI相关性均通过0.01的显著性检验，且相关系数均处于中等相关； $1 \sim 1 2$ 月逐月SPEI与DCMI相关性均通过0.01的显著性检验，且多数月份相关系数为中等相关。因此，DC-MI能够较好地反映区域土壤相对湿度与SPEI的变化，干旱综合监测模型具有较好的适用性。

2.3.2等级划分通过参考植被健康指数（VHI）、SPEI干旱等级划分方法[18-19]以及我国气象干旱等

# 表4DCMI与 $\mathbf { 1 0 ~ c m }$ 土壤相对湿度的相关性

Tab.4Correlation between DCMI and relative humidity of 10 cm soil   

<html><body><table><tr><td>站点</td><td>日喀则</td><td>拉萨</td><td>泽当</td><td>林芝</td></tr><tr><td>相关性</td><td>0.503 **</td><td>0.439 **</td><td>0.537 **</td><td>0.423 **</td></tr></table></body></html>

注： $* *$ 代表通过0.01(双侧)显著性检验

表5DCMI与SPEI的相关性  
Tab.5 Correlation betweenDCMI and SPEI   

<html><body><table><tr><td>月份</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td></tr><tr><td>相关性</td><td>0.333 **</td><td>0.321**</td><td>0.515 **</td><td>0.550 **</td><td>0.563 **</td><td>0.479 **</td></tr><tr><td>月份</td><td>7</td><td>8</td><td>9</td><td>10</td><td>11</td><td>12</td></tr><tr><td>相关性</td><td>0.552 **</td><td>0.599 **</td><td>0.511 **</td><td>0.503 **</td><td>0.363 **</td><td>0.202 **</td></tr></table></body></html>

注： $* *$ 代表通过0.01(双侧)显著性检验

# 表6干旱等级划分

Tab.6Drought classification   

<html><body><table><tr><td>序号</td><td>干旱等级</td><td>VHI</td><td>SPEI</td><td>DCMI</td><td>对应状况</td></tr><tr><td>1</td><td>极端干旱</td><td>VHI<10</td><td>SPEI≤-2.0</td><td>DCMI<0.2</td><td>土壤出现水分长时间严重不足，地表植物干枯、死亡，对农作物 和生态环境造成严重影响</td></tr><tr><td></td><td></td><td></td><td>2重度干旱 10≤VHI<20 -2.0<SPEI≤-1.5 0.2≤DCMI<0.3</td><td></td><td>土壤出现水分持续严重不足，出现较厚的干土层,植物萎蔫、叶 片干枯，果实脱落，对农作物和生态环境造成较严重影响</td></tr><tr><td>3</td><td></td><td></td><td></td><td>中度干旱 20≤VHI<30 -1.5<SPEI≤-1.0 0.3≤DCMI<0.4</td><td>降水持续较常年偏少，土壤表面干燥，土壤出现水分不足，地表 植物叶片白天有萎蔫现象，对农作物和生态环境造成一定影响</td></tr><tr><td></td><td></td><td></td><td></td><td>4轻度干旱 30≤VHI<40 -1.0<SPEI≤-0.5 0.4≤DCMI<0.5</td><td>降水较常年偏少,地表空气干燥,土壤出现水分轻度不足,对农 作物有轻微影响</td></tr><tr><td>5</td><td>正常无旱</td><td>VHI≥40</td><td>SPEI>-0.5</td><td>DCMI≥0.5</td><td>降水正常或较常年偏多，地表湿润,无干旱现象</td></tr></table></body></html>

级划分标准[20],对DCMI进行干旱等级划分，划分结果如表6所示。

# 3 西藏东南部历史干旱识别与时空格局分析

为了进一步研究拉萨、日喀则等5市的干旱时空变化特征及发展趋势，首先利用所构建的干旱综合监测模型，对2001—2015年逐月的DCMI进行识别计算，对研究区 $1 ~ \mathrm { k m }$ 空间分辨率干旱空间信息栅格数据集进行重建，并对DCMI计算结果进行干旱等级划分。通过统计分析各级干旱的发生频率，从时间和空间两个维度，对拉萨、日喀则等5市2001一2015年干旱时空演化特征进行分析，揭示气候变化背景下区域干旱的发生规律与发展趋势。

# 3.1干旱频率统计分析

干旱频率是指区域内发生干旱的频繁程度[21]文中基于GIS空间分析与历年逐月的干旱监测结果,对研究区干旱频率进行空间分析。其原理是当某像元达到干旱阈值后则认定此像元发生干旱过程，赋值为1，其余像元赋值为0，最终获得历年逐月的干旱统计数据。

3.1.1全年干旱频率分析全年干旱频率的统计结果(表7)表明，2001一2015年拉萨、日喀则等5市平均干旱频率为 $1 3 . 2 2 \%$ ， $8 7 . 5 9 \%$ 的区域干旱频率小于 $20 \%$ 。干旱频率在 $2 0 \% \sim 3 0 \%$ 间的区域面积达到 $1 1 . 9 8 \%$ ，约 $0 . 4 4 \%$ 的区域干旱频率大于$30 \%$ 。由图4可以看出，日喀则市全年干旱频率最高，且以轻度干旱为主，约 $1 / 3$ 的区域干旱频率大于$20 \%$ ，其中拉孜、谢通门、定日等县的部分区域干旱频率均超过 $30 \%$ ，部分地区干旱频率甚至超过$40 \%$ ;拉萨市干旱频率较高区域主要位于中部和西南部，东部和北部地区干旱频率相对较小;昌都市与林芝市大部分区域各级干旱频率均小于 $20 \%$ ，其

表7研究区2001—2015年干旱频率分布  
Tab.7Drought frequency distribution of cities in the study area from 2oo1 to 2015   

<html><body><table><tr><td rowspan="2">干旱等级</td><td rowspan="2">频率区间 /%</td><td colspan="2">拉萨市</td><td colspan="2">日喀则市</td><td colspan="2">林芝市</td><td colspan="2">昌都市</td><td colspan="2">山南市</td></tr><tr><td>面积/km²</td><td>比例/%</td><td>面积/km²</td><td>比例/%</td><td>面积/km²</td><td>比例/%</td><td>面积/km²</td><td>比例/%</td><td>面积/km²</td><td>比例/%</td></tr><tr><td>干旱总频率</td><td><10</td><td>6503</td><td>22.01</td><td>11 638</td><td>6.49</td><td>84 574</td><td>73.96</td><td>39 018</td><td>36.01</td><td>40 949</td><td>51.84</td></tr><tr><td></td><td>10~20</td><td>21 227</td><td>71.86</td><td>108 312</td><td>60.39</td><td>29 695</td><td>25.97</td><td>69 001</td><td>63.68</td><td>36 288</td><td>45.94</td></tr><tr><td></td><td>20~30</td><td>1 808</td><td>6.12</td><td>57 181</td><td>31.88</td><td>81</td><td>0.07</td><td>332</td><td>0.31</td><td>1743</td><td>2.21</td></tr><tr><td></td><td>30~40</td><td>1</td><td>0.00</td><td>2 199</td><td>1.23</td><td>1</td><td>0.00</td><td>1</td><td>0.00</td><td>5</td><td>0.01</td></tr><tr><td></td><td>>40</td><td>0</td><td>0.00</td><td>26</td><td>0.01</td><td>0</td><td>0.00</td><td>0</td><td>0.00</td><td>0</td><td>0.00</td></tr><tr><td>轻度干旱频率</td><td><10</td><td>15 677</td><td>53.07</td><td>40 423</td><td>22.54</td><td>104 924</td><td>91.76</td><td>83 692</td><td>77.24</td><td>57 964</td><td>73.39</td></tr><tr><td></td><td>10~20</td><td>13 840</td><td>46.85</td><td>136 257</td><td>75.97</td><td>9 421</td><td>8.24</td><td>24 658</td><td>22.76</td><td>20 965</td><td>26.54</td></tr><tr><td></td><td>20~30</td><td>22</td><td>0.07</td><td>2676</td><td>1.49</td><td>6</td><td>0.01</td><td>2</td><td>0.00</td><td>56</td><td>0.07</td></tr><tr><td>中度干旱频率</td><td><10</td><td>29 537</td><td>99.99</td><td>176 367</td><td>98.33</td><td>114 351</td><td>100</td><td>108 352</td><td>100</td><td>78 978</td><td>99.99</td></tr><tr><td></td><td>10~20</td><td>2</td><td>0.01</td><td>2 988</td><td>1.67</td><td>0</td><td>0.00</td><td>0</td><td>0.00</td><td>7</td><td>0.01</td></tr><tr><td></td><td>20~30</td><td>0</td><td>0.00</td><td>1</td><td>0.00</td><td>0</td><td>0.00</td><td>0</td><td>0.00</td><td>0</td><td>0.00</td></tr></table></body></html>

![](images/7689c1cf9c5b384a6bbc350f8a34aa817c5ab8510a2809f7e7b94c65e4b262a1.jpg)  
干吴区地理  
图4研究区2001—2015年干旱频率分布

![](images/3c0fc7ad96857397e0b86741ca24bab3d527d931b02f2f333dfd42fde73cdf7d.jpg)  
Fig.4Drought frequency distribution in the study area from 2OO1 to 2015   
图5研究区1\~12月不同干旱频率面积占比变化

Fig.5Changes in the proportionof diffrent drought frequency in the study area from January to December 中，林芝市大部分区域干旱频率小于 $10 \%$ ;山南市 中偏北部区域干旱发生频率明显高于南部区域，约 1/2 区域干旱频率小于 $10 \%$ 。

![](images/9c3dbb91e8527a37beab364e6ae856f39b037803b68972d104fc330b3c98cc9f.jpg)  
图61\~12月DCMI变化趋势空间分布  
Fig.6Spatial distribution of DCMI trends from January to December

从不同等级干旱频率来看，研究区内轻旱频率均在 $30 \%$ 以下，其中 $9 9 . 4 6 \%$ 的地区轻旱频率小于$20 \%$ ，日喀则市大部分区域为轻旱频发区；中旱频率则在 $2 5 \%$ 以下,其中 $9 9 . 4 1 \%$ 的区域中旱频率小于$10 \%$ ,易发区域集中在日喀则市的部分地区;2001—2015年全年重度及以上干旱频率相对较小，均在$10 \%$ 以下，主要集中于日喀则市和昌都市的中部及东部地区。

3.1.2月际干旱频率分析从图5可以看出，拉萨、日喀则等5市月际干旱频率差异较大。整体而言，全年干旱易发生于1月、8月以及11月等月份，局部地区干旱易发月份存在差异。其中，1月、11月干旱频率在 $2 0 \% \sim 3 0 \%$ 之间区域面积分别占全区的 $8 . 1 9 \%$ 与 $6 . 9 9 \%$ 。夏季7月、9月干旱频率在 $10 \%$ 以下的区域面积相对较大,表明7月和9月不易发生干旱灾害。8月虽然为雨季，但由于时常出现高温少雨天气导致干旱灾害的发生，这也是易发生干旱区域面积相对于7月、9月明显增大的原因。

从不同区域来看，日喀则市旱情易发生于每年的4月、6月、10月与11月，在这4个月中，全市$42 \%$ 以上区域干旱频率超过 $10 \%$ ;拉萨市旱情则易发生于每年的2月、3月，干旱频率 $10 \%$ 以上的区域达到全市面积的 $45 \%$ 以上;山南市除9月外,其余月份干旱频率均为均衡，全市 $20 \% \sim 3 9 \%$ 的区域干旱频率处于 $10 \%$ 以上;林芝市旱情易发月份则主要集中在1月、8月、11月与12月；昌都市旱情易发月份则主要集中在1月、5月与8月，在这3个月中，全市 $40 \%$ 以上区域干旱频率超过 $10 \%$ 。

# 3.2 旱情变化趋势分析

为了定量分析年内各月旱情的变化趋势，利用一元线性回归分析方法，对逐个像元的变化趋势进行模拟，以像元单元的变化特征来综合反映区域时空格局变化。对时间自变量及DCMI因变量数据，采用二乘法计算所有像元的DCMI与时间的回归斜率,即

$$
S l o p e \ = \ \frac { n \displaystyle { \sum _ { i = 1 } ^ { n } i \times D C M I _ { i } } - \sum _ { i = 1 } ^ { n } i \sum _ { i = 1 } ^ { n } D C M I _ { i } } { n \times \displaystyle { \sum _ { i = 1 } ^ { n } i ^ { 2 } - ( \sum _ { i = 1 } ^ { n } i ) ^ { 2 } } }
$$

式中：Slope为像元DCMI回归方程的斜率,i为月序号， $n$ 为月跨度。当 $S l o p e > 0$ 时,表示DCMI 随时间变化呈增加趋势;当 $S l o p e < 0$ 时，表示DCMI随时间变化呈下降趋势，且值越小，旱情增加趋势越明显。

结果表明，拉萨、日喀则等5市年内旱情变化趋势差异性较大（图6)。整体而言，10月 $\sim$ 次年9月，旱情加剧区域呈现出随月份变化由耕作区东部向西部逐渐转移的趋势。其中，10月～次年3月，山南、林芝、昌都3市旱情加剧趋势较为明显;4～5月旱情加剧区域面积达到 $6 5 \%$ 以上，加剧区域主要集中在日喀则、拉萨、山南的部分地区;6\~9月，拉萨、日喀则等5市则均出现不同程度的旱情加剧趋势，8月旱情减弱趋势区域占比则要明显高于其他月份。

# 4结论

本文以地处西藏自治区东南部的拉萨、日喀则等5市为研究区，以 2001—2015年MODIS、TRMM遥感数据和SRTM-DEM为数据源，利用VCI、TCI和PCI等模型参量，采用空间主成分分析方法构建了研究区干旱综合监测模型，对模型的精度和可靠性进行检核验证，在此基础上，对2001—2015年研究区逐月干旱进行识别和重建，分析了2001—2015年研究区干旱时空格局及变化趋势，得到结论如下：

（1）研究区域内，DCMI能够较好地反映区域土壤相对湿度与SPEI的变化，干旱综合监测模型具有较好的适用性。

（2）研究区全年干旱频率在空间分布上呈现出西高东低的特征。研究区平均十旱发生频率为$1 3 . 2 2 \%$ ， $8 7 . 5 9 \%$ 的区域干旱频率小于 $20 \%$ 。干旱频率在 $2 0 \sim 3 0 \%$ 间的区域面积占 $1 1 . 9 7 \%$ ，约$0 . 4 4 \%$ 的区域干旱频率大于 $30 \%$ 。从不同等级干旱发生频率来看，日喀则市为轻旱、中旱易发区，重旱易发区则集中于日喀则市和昌都市的中部及东部地区。

（3）研究区月际干旱频率空间格局差异较大。整体而言，全年干旱易发生于1月、8月以及11月等月份，局部地区干旱易发月份存在差异。

（4）研究区年内旱情变化趋势差异性较大。整体而言，10月～次年9月，旱情加剧趋势呈现出随月份变化由耕作区东部向西部逐渐转移的趋势。

参考文献（References） [1］王行汉,刘超群,丛沛桐,等.基于增强温度植被指数的农业旱 情遥感监测[J].干旱区资源与环境,2018,32（5）：165－170. [WANG Xinghan,LIU Chaoqun,CONG Peitong,et al. Agriculture drought monitoring using remote sensing based on enhanced temperature vegetation dryness index[J]. Journal of Arid Land Resources & Environment,2018,32(5）:165-170.] [2]KOGAN F N.Application of vegetation index and brightness temperature for drought detection[J].Advances in Space Research,   
1995,15(11) :91 -100. [3]TADESSE T,BROWN JF,HAYES M J. A new approach for predicting drought-related vegetation stress：Integrating satelite,climate,and biophysical data over the U. S.central plains[J].Isprs Journal of Photogrammetry & Remote Sensing,2005,59(4）:244 -   
253. [4]RAJSEKHAR D,SINGHV P,MISHRA A K. Multivariate drought index：An information theory based approach for integrated drought assessment[J]. Journal of Hydrology,2015,526(11/12）:164 -   
182. [5]ZHANG L,JIAO W,ZHANG H,et al. Studying drought phenomena in the Continental United States in 2011 and 2012 using various drought indices[J].Remote Sensing of Environment,2017,190:   
96-106. [6］郑杰,冯文兰,王凤杰,等.岷江上游干旱河谷范围的界定及其 变化分析[J].干旱区地理,2017,40（3）:541-548.[ZHENG Jie,FENG Wenlan,WANG Fengjie,etal.Spatial definition and its range variation of arid valley in the upper reaches of Minjiang River [J].Arid Land Geography,2017,40(3）:541-548.] [7］张婧娴.综合多源遥感数据的干旱监测模型研究[D].南京： 南京信息工程大学,2015.[ZHANG Jingxian.Study on drought monitoring modeling integrated multi-source remote sensing dateTaking Shanxi as an example[D]. Nanjing:Nanjing University of Information Science & Technology,2015.] [8］雷步云,赵书河,覃志豪,等.基于 SDI指数的南非共和国   
2001—2014年干旱监测时空分布[J].干旱区地理,2016,39 (2）:395-404.[LEI Buyun,ZHAO Shuhe,QIN Zhihao,et al. Drought temporal-spatial distribution of South Africa based on MODIS SDI index from 2001—2014[J].Arid Land Geography,2016,   
39(2) :395 -404. ] [9］杜灵通.基于多源空间信息的干旱监测模型构建及其应用研 究[D].南京：南京大学,2013.［DU Lingtong.Drought monitoring model basedonmulti-soure spatial informationanditsapplication[D].Nanjing：Nanjing University,2013.] [10］陈建军.基于EOS/MODIS 的江西省水稻长势遥感监测研究 [D].南京:南京信息工程大学,2012.[CHEN Jianjun.Study on monitoring of paddy rice growth based on EOS/MODIS in Jiangxi province[D].Nanjing：Nanjing University of Information Science & Technology ,2012.] [11］李红军,郑力,雷玉平,等.基于 EOS/MODIS 数据的 NDVI与 EVI比较研究[J].地理科学进展,2007,26（1）:26－32.［LI

Hongjun,ZHENG Li,LEI Yuping,et al.Comparison of NDVI and EVI based on EOS/MODIS data[J].Progress in Geography,2007, 26(1) :26 -32.]

[12]KOGAN F N. Remote sensing of weather impacts on vegetation in non-homogeneous areas[J]. International Journal of Remote Sensing,1990,11(8):1405-1419   
[13］张尧.基于遥感方法的2010 年西南干旱监测评价[D].杨凌： 西北农林科技大学,2014.[ZHANG Yao.Monitoring and estimating the 2010 drought impact in southwestern China based on remote sensing[D].Yangling:Northwest A&F University,2014.]   
[14］王俊霞,朱秀芳,刘宪锋,等.基于多源遥感数据的旱情评价研 究——以河南省为例[J].国土资源遥感,2018,30（1)：180- 186.[WANG Junxia,ZHU Xiufang,LIU Xianfeng,et al. Research on agriculture drought monitoring method of Henan Province with multi-sources data[J].Remote Sensing for Land & Resources,， 2018,30(1) :180 -186.]   
[15］曾波.湖南省农业干旱空间分布研究[D].长沙：中南林业科 技大学,2014.[ZENG Bo.Research on spatial distribution of agriculture droughtin Hunan[D].Changsha:Central SouthUniversity of Forestry and Technology,2014.]   
[16］夏文韬,王莺,冯琦胜,等.甘南地区 MODIS 土地覆盖产品精 度评价[J].草业科学,2010,27（9）:11-18.[XIA Wentao, WANG Ying,FENG Qisheng,et al. Accuracy assessment of MODIS land cover product of Gannan Prefecture[J].Pratacultural Science,2010,27(9):11 -18.]   
[17］王莺,王静,姚玉璧,等.基于主成分分析的中国南方干旱脆弱 性评价［J].生态环境学报,2014,23（12）：1897－1904. [WANG Ying,WANG Jing,YAO Yubi,et al.Evaluation of drought vulnerabilityin Southern China basedon principal component analysis[J].Ecology & Environmental Sciences,2014,23 （12):1897-1904.]   
[18]DU L,TIAN Q,YU T,et al.A comprehensive drought monitoring method integrating MODIS and TRMM data[J].International Journal of Applied Earth Observation & Geoinformation,2013,23（1）: 245 -253.   
[19]LI X,HE B,QUAN X,et al.Use of the standardized precipitation evapotranspiration index（SPEI）to characterize the drying trend in southwest China from 1982—2012[J]. Remote Sensing,2015,7 （8):10917-10937.   
[20］中华人民共和国国家质量监督检验检疫总局.中华人民共和 国国家标准：气象干旱等级GB/T20481-2017)[S].北京：中 国标准出版社,2017.[General Administration of Quality Supervision,Inspection and Quarantine of the People's Republic of China. Classification of meteorological drought（GB/T 20481 - 2017） [S].Beijing：Standards Press of China,2017.]   
[21］何鑫,吴吉东,李颖,等.基于 SPEI的辽西地区气象干旱时空 分布特征[J].干旱区地理,2017,40(2）:340-347.［HE Xin, WU Jidong,Li Ying,et al.Spatio-temporal distribution characteristics of meteorological drought in western region of Liaoning Province based on standardized precipitation evapotranspiration index [J]. Arid Land Geography,2017,40(2） :340 -347.]

# Monitoring and analysis of historical drought in southeast Tibet based on multi-source data

XIONG Jun-nan12，LIWei1，LIU Zhi-qi³，CHEN Wei-ming², FAN Chun-kun4， ZHANG Hao' (1School of Civil Engineering and Architecture,SWPU,Chengdu 6105Oo,Sichuan,China ;   
2State KeyLaboratoryof Resources and Environmental Information System，InstituteofGeographicand NaturalResources   
Research,Chinese Academy ofSciences,Beijing 10olo1,China；3Sichuan Provincial Coalfield Surveyingand Mapping   
EngineringIstitute,Chengdu6O72,ichuan,China；4AgricultureResearch Institute,betAcademyofAgricultured Animal Husbandry Sciences,Lhasa 85oooO,Tibet,China)

Abstract:Asone of the global natural disasters which take place frequently,drought has caused problems in society,economy,and ecological environment. Based on the MODIS,TRMMand SRTM-DEM data from 2001 to 2015as the data sources,this paper takes the main farming area of Tibet Province,China as the research areaand constructeda regional drought comprehensive monitoring model by using the spatial principal component analysis method and adopting the vegetation state index（VCI）,temperature condition index（TCI）and precipitation state index （204号 $\left( P C I \right) .$ The accuracy and reliability of the model is verified.The model was then used to identify the monthly drought in the studyarea from 2001 to 2O15,and the geospatial-temporal analysismethod wasused to study the characteristics and trendsof drought changes in the study area.The results show thatthe drought comprehensive monitoring index（DCMI）can beter reflectthe changesof regional soil relative humidityand standardized precipitation evapotranspiration index（SPEI）,and the comprehensive drought monitoring model hasgood applicability.The spatial distributionof annual drought frequencyinthe westofthe study area was higher than thatintheeast,and the drought frequency in most areas was less than $20 \%$ ,and about $1 2 . 4 1 \%$ of the regions had a drought frequency more than $20 \%$ .From the perspective of the frequency of droughts in diffrent grades,Shigatse City was a light drought and moderate drought area,whilethe severe drought areas were concentrated in the central and eastern parts of Shigatse City and Changdu City.The spatial patern of monthly drought frequency in the study area wasquite dierent. The drought inthe whole year was prone to occur in January,August and November,and there were diferences in the drought-prone months in some areas.The change trend of drought inthe study area was quite different during a year.From October to September,the drought-intensified area showed a trend of gradualy shifting from the east to the west of the cultivated area along the month.

Key words:multi-source data；drought；monitoring；Tibet