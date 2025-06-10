# 融合GPM降水数据的土壤干旱遥感监测

谭惠芝¹，尹倩¹，姬莉雯，芦倩²，卢晓宁¹，崔林林¹，夏志业¹，徐维新'，陈军1

(1.成都信息工程大学资源环境学院,四川 成都610225；2.陕西省神木市气象局,陕西 神木719300)

摘要：全球气候变暖导致干旱趋势加重,对西北干旱半干旱区农牧业生产造成严重威胁。考虑到陕西省神木市具有典型的黄土高原地貌特征,以及降水对复杂地貌背景区干旱的决定性作用,本研究应用高精度的GPM（GlobalPrecipitation Measurement)降水数据，建立土壤干旱遥感监测模型,开展能够揭示土壤相对湿度的应用分析研究。结果表明：结合GPM降水数据建立的综合植被、温度和降水的土壤干旱遥感监测模型,能准确的揭示神木市土壤表层 $1 0 \ \mathrm { c m }$ 相对湿度,模型中温度和降水的权重较高,体现出温度和降水对区域干旱的主导作用;神木市作物生长季旱情整体处于轻旱强度，平均发生频率为 $6 4 . 4 4 \%$ ，且中旱 $. >$ 轻旱 $. > ^ { \cdot }$ 重旱 $. >$ 特旱，干旱强度和发生频率均呈现出西北高东南低的空间分异特征;4—10月干旱强度整体由轻旱发展至重旱,最后干旱消失。季节上,神木市春旱现象严重，且以中旱发生频率最高。2001—2019年神木市旱情呈略微减轻趋势,但红碱淖湿地因年均气温和年蒸发量明显上升，干旱情况加剧。

关键词：GPM；MODIS；干旱；土壤相对湿度；神木市

干旱一般是由土壤水分不足引起的一种自然灾害，其特点为持续时间长、波及范围广、影响人口多、频发性高等[1-3]。我国是农业大国,亦是干旱频发的国家，每年因干旱造成的经济损失高达数千亿元[4。因此,极有必要加强对干旱的监测,尤其是大尺度面域的高时空连续性的干旱监测。遥感作为一种时效性强、覆盖面广的新技术，可弥补传统气象干旱监测以点代面的缺陷[5-6],在气象站点有限的复杂地貌区域更有优势[7]。当前多数的干旱遥感研究以可见光和近红外波段来表征植被变化，或基于热红外波段考虑地表温度和蒸散[8-10],而对降水的考虑较少。众所周知，干旱多是由降水异常偏少引起，某一时期的降水量与该地区的干旱强度有着至关重要的关系["],因此，在进行旱情遥感监测时更应考虑降水的作用。目前,已有卢晓宁等[12]、Cong等[13]学者对东北、西南等植被和降水较多的地区开展了考虑降水作用的干旱遥感监测，但对干旱严重的西北地区该类研究较少，且在降水数据源上主要应用TRMM（Tropical Rainfall Measuring Mission)数据,该数据精度不能满足高纬度地区的研究需求[14]，继之的GPM降水数据时空分辨率更高，在中高纬度及相对干旱地区的降水反演精度更高[15],但是当前针对GPM的干旱遥感监测研究鲜见。此外，现有干旱遥感监测多限于干旱的相对等级划分，无法满足农业干旱对土壤情的量化需求，这与农业干旱遥感监测的需求及目的是不吻合的。

陕西省神木市具有典型的黄土高原地貌地理特征，地貌类型复杂，包含风沙滩地区丘陵沟壑区和低山丘陵三类[1],海拔高度的显著差异引起降水空间分异大[,较低的植被覆盖和以砂土为主的土壤保水性差，区域遭受干旱胁迫严重。比重高达$14 \%$ 的耕地面积1，以及维系全国面积最大的沙漠淡水湖一一红碱淖，使得在该区域实现高精度、高时空分辨率的干旱遥感监测极为紧迫。因此，本文以陕西省神木市为研究区，构建综合考虑植被、温度和降水的土壤水分监测指数(SoilMoistureMoni-toringIndex,SMMI)，实现2001—2019年陕西省神木市作物生长季(4一10月)的干旱遥感监测，并从干旱强度、频率和趋势上全面揭示区域旱情演变规律。可在有效揭示区域干旱背景的基础之上，直接、快速和高效的为区域农业生产及发展的防旱抗旱提供理论参考依据。

# 研究区概况与方法

# 1.1 研究区概况

神木市位于陕西省榆林市，地处黄河中游，地理位置 $1 0 9 ^ { \circ } 4 0 ^ { \prime } 6 . 9 7 ^ { \prime \prime } { \sim } 1 1 0 ^ { \circ } 5 5 ^ { \prime } 8 . 3 3 ^ { \prime \prime } \mathrm { E } , 3 8 ^ { \circ } 1 2 ^ { \prime } 2 9 . 0 5 ^ { \prime \prime } { \sim }$ $3 9 ^ { \circ } 2 7 ^ { \prime } 1 6 . 7 0 ^ { \prime \prime } \mathrm { N }$ (图1)。南北长约 $1 4 0 \ \mathrm { k m }$ ,东西宽约$1 1 0 \mathrm { k m }$ ,总面积为 $7 6 7 0 \mathrm { k m } ^ { 2 }$ ,是陕西省面积最大的县级市。神木市地形西北高而东南低，海拔位于661\~$1 4 2 5 \mathrm { ~ m ~ }$ ,平均海拔 $1 1 5 0 \mathrm { m }$ 。区域大陆性气候显著，寒暑剧烈，气候干燥，灾害频发。降水量由南向北递减，年际变化大，多年平均降水 $3 9 2 . 5 ~ \mathrm { m m }$ ，主要集中在7一9月。该地区盛行偏西和西北风,全年大风日数14d,最大风速大于 $2 5 \mathrm { m \cdot s ^ { - 1 } }$ 。神木市4—10月平均地表温度为 $3 0 . 4 0 ~ \mathrm { ^ { \circ } C }$ ,其蒸发量大，且由西北向东南降低。

# 1.2数据与方法

# 1.2.1 数据来源

（1）遥感数据

GPM数据、陆地表面温度(Land Surface Temper-ature,LST)与归一化植被指数(NormalizedDifferentVegetationIndex,NDVI)数据均来源美国国家航空航天局（NASA）网站（https://www.nasa.gov）,时间周期为2001—2019年作物生长季（4—10月）。GPM采用逐日的空间分辨率为 $0 . 1 ^ { \circ } \times 0 . 1 ^ { \circ }$ 的GPM_IMERG产品数据集;LST数据采用 $8 \textup { d }$ 合成的空间分辨率为$1 ~ \mathrm { k m } { \times } 1 ~ \mathrm { k m }$ 的MOD11A2产品数据集；NDVI数据采用16d合成的空间分辨率为 $1 ~ \mathrm { k m } \times 1 ~ \mathrm { k m }$ 的MOD13A2产品数据集。

(2）土壤相对湿度数据与气象站点降水数据

土壤相对湿度数据来源于神木市国家基本气象站,位于 $1 1 0 ^ { \circ } 2 8 ^ { \prime } \mathrm { E } , 3 8 ^ { \circ } 4 9 ^ { \prime } \mathrm { N } , 2 0 1 8$ 年前位于 $1 1 0 ^ { \circ } 2 6 ^ { \prime } \mathrm { E }$ $3 8 ^ { \circ } 4 9 ^ { \prime } \mathrm { N } , 2 0 1 4 - 2 0 1 8$ 年4—10月土壤表层 $1 0 \ \mathrm { c m }$ 和$2 0 ~ \mathrm { c m }$ 的逐小时土壤平均相对湿度数据从该站获取。气象站点降水数据选取了神木市1个国家站与9个区域站的2001—2019年逐日降水数据,用于验证GPM_IMERG数据精度。

![](images/d3000e3560bd6c200e626dae5d81d00d2298497601ad819ad65cd46c5e81cfc6.jpg)  
图1研究区示意图  
Fig.1 Shenmu city regional overview map

# (3）土壤质地空间分布数据

土壤质地空间分布数据来源于中国科学院资源环境科学与数据中心（http://www.resdc.cn），比例尺为1:1000000。依据该数据得到神木市土壤质地组成,其中 $6 5 . 6 0 \%$ 为砂土， $2 2 . 5 5 \%$ 为粉砂土，其余为黏土。同时，自动土壤水分监测站点的土壤质地组成为 $6 2 \%$ 为砂土、 $2 1 \%$ 为粉砂土、 $1 7 \%$ 为黏土，两者土壤质地组成的一致性，体现出该土壤水分实测样点的代表性和典型性。

1.2.2数据预处理以NDVI数据的采样频率为基准，对GPM、LST数据进行同频率采样，即16d的均值合成处理;空间上，对 $1 0 ~ \mathrm { k m }$ 空间分辨率的GPM数据采用双线性内插法，重采样为与LST和NDVI数据相同的 $1 \mathrm { k m }$ 的空间分辨率，实现时空分辨率的一致性。

# 1.2.3数据处理

# （1）GPM数据精度检验

限于仅有10个气象站点，且主要分布在中部，无法很好地量化区域降水的异质性。利用2001—2019年(6354d)神木市国家站和2017—2019年(1005d)9个区域站的有效逐日实测降水量与相应

# 表1 神木市2001—2019年GPM数据与站点降水数据相关系数

<html><body><table><tr><td>气象站点</td><td>Pearson相关系数</td><td>气象站点</td><td>Pearson相关系数</td></tr><tr><td>神木国家站</td><td>0.702**</td><td>锦界</td><td>0.672**</td></tr><tr><td>大保当</td><td>0.685**</td><td>栏杆堡</td><td>0.611**</td></tr><tr><td>大柳塔</td><td>0.589**</td><td>乔岔滩</td><td>0.742**</td></tr><tr><td>店塔</td><td>0.562**</td><td>沙峁</td><td>0.747**</td></tr><tr><td>红碱淖</td><td>0.539**</td><td>万镇</td><td>0.685**</td></tr></table></body></html>

注：\*\*表示在0.01水平(双侧)上显著相关。

的 $\mathrm { G P M } \ 1 \ \mathrm { k m }$ 数据进行相关性分析(表1)，各站均通过了0.01水平的显著性检验，表明利用GPM降水数据代替有限的气象站点数据进行干旱监测具有可靠性和可行性。

# （2）各因子标准化处理

由于各因子量纲不同，需进行标准化处理，ND-VI原始数值为 $- 0 . 3 { \sim } 0$ 像元的地表覆被类型为云、水、雪等,该类型区不可能发生干旱,直接赋值为1;对LST进行最大值归一化，GPM降水数据进行最小值归一化，分别对处理后的NDVI、LST和GPM数据定义为植被状态指数(VCI）、温度状态指数(TCI)和降水状态指数(PCI)。

# 2土壤干旱遥感监测模型的建立

研究区仅有一个土壤熵情的实测站点，且数据集中在2014—2018年4—10月，有效数据共64期(16d为一期)。随机选取 $7 0 \%$ 的数据(45期)用于建模，其余 $3 0 \%$ (19期)用于模型验证。用于建模的站点数据时间分布如表2所示，兼顾了作物生长季內春夏秋三季。

# 2.1土壤干旱遥感监测模型因变量的确定

将土壤情站点对应的VCI、TCI和PCI,分别与土壤表层 $2 0 ~ \mathrm { c m }$ 和 $1 0 ~ \mathrm { c m }$ 的相对湿度数据进行Pearson相关分析。结果显示，土壤表层 $1 0 \ \mathrm { c m }$ 相对湿度与TCI通过了0.01水平显著性检验，与VCI和PCI通过了0.05水平显著性检验(表3)，而土壤表层$2 0 \mathrm { c m }$ 相对湿度仅与TCI呈显著相关，这与类似区域Wang等[19]的研究结论一致,因此本研究将土壤表层$1 0 \ \mathrm { c m }$ 相对湿度作为土壤干旱遥感监测模型的因变量。同时，神木市以砂土为主的土壤质地分布，其保水性能差，水分变化在表层极为显著，土壤更易干旱,这更进一步说明将土壤表层 $1 0 \ \mathrm { c m }$ 相对湿度

Tab.1 Correlation coefficients between GPM data and station precipitation data in Shenmu City from 2001 to 2019   
表2每期数据对应日序  
Tab.2 Number of days corresponding to each period of data   

<html><body><table><tr><td>期号</td><td>日序</td><td>对应季节</td><td>期号</td><td>日序</td><td>对应季节</td></tr><tr><td>1</td><td>第97~112 d</td><td>春季</td><td>8</td><td>第209~224 d</td><td>夏季</td></tr><tr><td>2</td><td>第113~128 d</td><td>春季</td><td>9</td><td>第225~240 d</td><td>夏季</td></tr><tr><td>3</td><td>第129~144 d</td><td>春季</td><td>10</td><td>第241~256d</td><td>秋季</td></tr><tr><td>4</td><td>第145~160 d</td><td>春季</td><td>11</td><td>第257~272 d</td><td>秋季</td></tr><tr><td>5</td><td>第161~176 d</td><td>夏季</td><td>12</td><td>第273~288 d</td><td>秋季</td></tr><tr><td>6</td><td>第177~192 d</td><td>夏季</td><td>13</td><td>第289~304 d</td><td>秋季</td></tr><tr><td>7</td><td>第193~208 d</td><td>夏季</td><td></td><td></td><td></td></tr></table></body></html>

# 表3各因子与土壤相对湿度相关系数

Tab.3 Correlationcoefficients of various factors and soil relative humidity   

<html><body><table><tr><td rowspan="2">土壤表层/cm</td><td colspan="3">植被状态指数</td></tr><tr><td>VCI</td><td>TCI</td><td>PCI</td></tr><tr><td>10</td><td>0.307°</td><td>0.510**</td><td>0.364°</td></tr><tr><td>20</td><td>0.155</td><td>0.469**</td><td>0.210</td></tr></table></body></html>

注：\*\*表示在0.01水平(双侧)上显著相关，\*在0.05水平(双侧)上显著相关。

数据作为模型因变量的科学性。

# 2.2土壤干旱遥感监测模型的建立及精度验证

依据 $7 0 \%$ 的样点数据，构建综合考虑植被、温度和降水因素的土壤水分监测指数(SMMI)，通过多元线性回归建立土壤干旱遥感监测模型，如下式所示：$\mathrm { S M M I } = 0 . 3 8 4 \mathrm { V C I } + 0 . 7 6 9 \mathrm { T C I } + 0 . 6 4 0 \mathrm { P C I } - 0 . 0 2 2$ (1)式中：VCI、TCI和PCI数值越小，越容易发生干旱；SMMI值越小，表征土壤干旱越严重。温度和降水在模型中的权重最高，说明土壤干旱在该区域由温度和降水共同主导。

将剩余 $3 0 \%$ 的植被、温度和降水数据代入模型中，用于验证模型精度(图2)。土壤表层 $1 0 \mathrm { c m }$ 的相对湿度模拟值与实测值的相关系数高达0.909，达到0.01水平的极显著相关，且均方根误差(RMSE)仅有0.068，足以说明模型的可靠性。

![](images/300b379f06a284b93881521ac49342dd656a3efeb4b6101721af2758e4c94e0b.jpg)  
图2土壤相对湿度SMMI散点图  
Fig.2Scatter plotof soil relative humidity SMMI   
图3神木市作物生长季(4—10月)SMMI空间分布 Fig.3Spatial distribution of SMMI during the crop growing season (April to October) in Shenmu City

# 3作物生长季旱情时空演变规律

# 3.1旱情强度时空演变规律

3.1.1旱情强度的空间分布根据砂土质地相对湿度干旱等级划分标准[20](表4)，得到陕西省神木市2001—2019年4—10月作物生长季土壤干旱强度的多年平均状态的空间分布情况(图3)。神木市作物生长季多年平均SMMI值为0.493，整体处于轻旱状

# 表4土壤水分监测指数的干旱等级划分

Tab.4 Classification of drought grades of soil moisture monitoring index   

<html><body><table><tr><td>干旱等级</td><td>简称</td><td>土壤相对湿度</td></tr><tr><td>特大干旱</td><td>特旱</td><td>0.00~0.25</td></tr><tr><td>严重干旱</td><td>重旱</td><td>0.25~0.35</td></tr><tr><td>中度干旱</td><td>中旱</td><td>0.35~0.45</td></tr><tr><td>轻度干旱</td><td>轻旱</td><td>0.45~0.55</td></tr><tr><td>无旱</td><td>无旱</td><td>0.55~1.00</td></tr></table></body></html>

109°40'E 1100'E 110°20'E 110°40'E   
3006M 大柳塔镇 330.3M 中鸡镇   
N0.60 尔林兔镇 纸 孙家岔镇 店塔镇 20.60 锦界镇 神木镇 栏杆堡镇   
300080 大保当镇 305.80 T 马镇 SMMI 高家堡镇 ws 沙镇 0.917 贺家川镇 花石崖镇   
30080 万镇 335.8M 0 20km 0.386   
109°40'E 110°0'E 110°20'E 110°40'E

态，西北部旱情明显强于东南部(图3)。各干旱等级的面积比重以轻旱最大 $( 7 5 . 1 5 \%$ ）、中旱次之0 $1 8 . 7 8 \%$ ）、无旱最小 $( 6 . 0 7 \% )$ 。红碱淖作为全国最大的沙漠淡水湖，其SMMI值均在0.55以上，属于无旱状态，占神木市总面积的 $0 . 5 6 \%$ 。区域东部的栏杆堡镇北部、神木镇东部、花石崖镇与贺家川镇交界处亦处于无旱状态。西部其余地区SMMI值普遍在0.45\~0.55之间，处于轻旱状态。只有中部的锦界镇、大保当镇、尔林兔镇大部分地区SMMI值小于0.45，处于中旱状态。总体看来，神木市干旱强度呈现出由西北向东南旱情递减趋势(图3)，与刘宇峰等[2对陕西省的干旱研究结论相一致。这是因为神木市西北部属于风沙滩地区，植被覆盖少，地表温度相对较高，在西北风的强烈侵蚀下，土壤水分减少加快,相较于其他地区旱情更为严重[16]。随着风向东南转移，风力减弱，地势起伏增大使地形雨增加，且植被覆盖度增加，地表温度降低，土壤水分减少较慢，最终形成了土壤湿度自西北向东南增长的空间特征，即由西北向东南土壤干旱减弱的空间变化。

3.1.2干旱强度的年内变化神木市作物生长季多年平均SMMI年内变化值在0.255\~0.979，最小值

0.348出现在第4期，最大值0.662则出现在第13期(表5)。神木市干旱强度主要表现为第4期为重旱，第2、3、5期和6期为中旱,1、7期和8期表现为轻旱，9\~13期为无旱。

表5神木市作物生长季(4—10月)每期SMMI平均值  
.5Average SMMI for each period of the crop growing season (April to October) in Shenmu Cit   

<html><body><table><tr><td>期号</td><td>SMMI</td><td>干旱等级</td><td>期号</td><td>SMMI</td><td>干旱等级</td></tr><tr><td>1</td><td>0.475</td><td>轻旱</td><td>8</td><td>0.513</td><td>轻旱</td></tr><tr><td>2</td><td>0.407</td><td>中旱</td><td>9</td><td>0.575</td><td>无旱</td></tr><tr><td>3</td><td>0.389</td><td>中旱</td><td>10</td><td>0.584</td><td>无旱</td></tr><tr><td>4</td><td>0.349</td><td>重旱</td><td>11</td><td>0.629</td><td>无旱</td></tr><tr><td>5</td><td>0.376</td><td>中旱</td><td>12</td><td>0.633</td><td>无旱</td></tr><tr><td>6</td><td>0.404</td><td>中旱</td><td>13</td><td>0.664</td><td>无旱</td></tr><tr><td>7</td><td>0.465</td><td>轻旱</td><td></td><td></td><td></td></tr></table></body></html>

神木市4月中旬(第1期)处于轻旱状态，范围占到 $7 1 . 1 2 \%$ (图4)，而中旱区域只占 $2 7 . 4 2 \%$ ，仅集中在神木市西北部的尔林兔镇、锦界镇、中鸡镇、大保当镇。4月下旬至5月上旬(第2期)，轻旱范围缩小至只占 $1 . 1 4 \%$ ,中旱影响范围比重陡升至 $9 7 . 4 9 \%$ ，几乎覆盖整个神木市。5月中旬至6月上旬(第3\~4期） $9 8 . 7 8 \% { \sim } 9 9 . 1 3 \%$ 的地区受重旱和中旱控制。其中5月下旬至6月上旬(第4期)旱情最为严重，重旱影响范围达到了 $4 9 . 9 8 \%$ ,突出体现在尔林兔镇、锦界镇、中鸡镇、大保当镇、孙家岔镇、大柳塔镇以及神木镇、高家堡镇部分区域(图5)。此时为春季，冬季风衰退，太平洋暖湿气流减弱，难以影响该地区，从而造成土壤干旱,春旱现象越来越严重[22]

随着进入夏季，高温炎热，雨水集中，神木市的干旱情况在很大程度上得到缓解，表现为重旱、中旱影响减弱，轻旱、无旱显著增强的特征，但总体上仍受干旱主导。重旱的影响范围比重从6月中旬(第5期)的 $3 1 . 2 0 \%$ ,每期以平均 $1 5 . 2 7 \%$ 的速率减少至7月中旬(第7期)的 $0 . 6 6 \%$ ,只有锦界镇和大保当镇的少许地方出现重旱，8月上旬(第8期)重旱完全消失。中旱影响则只在6月下旬至7月上旬(第6期)略有加强，此后直到8月上旬(第8期)呈持续减弱状态，减少到只占 $1 8 . 7 1 \%$ ,空间上仅影响到尔林兔镇、锦界镇和大保当镇。轻旱和无旱的影响越来越明显，这与胡鹏飞等23对黄土高原农业干旱监测的研究结果相一致。轻旱从6月中旬(第5期)仅有的 $4 . 2 6 \%$ ,持续增长至7月中旬(第7期)的 $6 0 . 8 6 \%$ ，并稳定影响到8月上旬(第8期)。无旱则从6月中旬(第5期)仅体现在红碱淖湿地的 $0 . 3 4 \%$ ，以平均每期 $8 . 0 6 \%$ 的速率增长至8月上旬(第8期）的$2 4 . 1 8 \%$ ，已经影响到神木市东部的栏杆堡镇、店塔镇南部、神木镇东部以及神木市南部的花石崖镇、贺家川镇西部、高家堡镇东部地区(图5）。

![](images/595c9351b5cbd90d357301b86756e6f95f6f5dd1a814725830c4cf80b6b863bc.jpg)  
图4神木市作物生长季(4—10月)各干旱等级面积占比 Fig.4 Proportion of the area of each drought grade during the crop growing season (April to October) in Shenmu City

8月中旬(第9期)开始,神木市进入无旱主导状态(图4)，呈现出由东南逐渐向西北方向扩张的态势,这与李菁[24]等的研究结果相吻合。干旱(轻旱和中旱)影响区域持续向西北萎缩，从8月中旬(第9期)的尔林兔镇、锦界镇、大保当镇等衰减至10月上旬(第12期)的锦界镇和大保当镇少许地区;影响范围的面积比重也由8月中旬(第9期)的 $3 1 . 7 2 \%$ 减至10月上旬(第12期)的 $1 . 4 7 \%$ ，直至10月底（第13期)干旱完全消失。这与以黄土高原或西北干旱大

(a)第1期 (b)第2期 (c)第3期 NA 大柳塔镇 大柳塔镇 大柳塔镇 中鸡镇 中鸡镇 中鸡镇 孙家岔镇店塔镇 ? 孙家岔镇店塔镇 孙家岔镇   
尔林兔镇 尔林兔镇 尔林兔镇 店塔镇 锦界镇 神木镇栏杆堡镇 锦界镇 神木镇栏杆堡镇 锦界镇 神木镇栏杆堡镇   
大保当镇 马镇 大保当镇 马镇 大保当镇 马镇 高家堡镇 沙镇 高家堡镇 沙镇 高家堡镇 沙镇 贺家川镇 贺家川镇 贺家川镇 花石崖镇 花石崖镇 花石崖镇 万镇 万镇 万镇   
(d)第4期 (e)第5期 (f)第6期 大柳塔镇 大柳塔镇 大柳塔镇 中鸡镇 中鸡镇 中鸡镇   
尔林兔镇 孙家岔镇店塔镇 尔林兔镇 孙家岔镇 店塔镇 尔林兔镇 孙家岔镇店塔镇 锦界镇 神木镇栏杆堡镇 锦界镇 神木镇栏杆堡镇 锦界镇 神木镇栏杆堡镇   
大保当镇 马镇 大保当镇 马镇 大保当镇 马镇 ? 高家堡镇 沙镇 高家堡镇 沙镇 ? 高家堡镇 沙镇 贺家川镇 贺家川镇 贺家川镇 花石崖镇 花石崖镇 花石崖镇 万镇 万镇 万镇   
(g)第7期 大柳塔镇 (h)第8期 大柳塔镇 (i)第9期 大柳塔镇 中鸡镇 中鸡镇 中鸡镇   
尔林兔镇 孙家岔镇店塔镇 尔林兔镇 孙家岔镇店塔镇 尔林兔镇 孙家岔镇店塔镇 锦界镇 神木镇栏杆堡镇 锦界镇 神木镇栏杆堡镇 锦界镇神木镇栏杆堡镇   
大保当镇\~ 马镇 大保当镇 马镇 大保当镇 马镇 9 高家堡镇 沙镇 2 高家堡镇 沙镇 高家堡镇 沙镇 贺家川镇 贺家川镇 贺家川镇 花石崖镇 花石崖镇 花石崖镇 万镇 万镇 万镇   
(i)第10期 大柳塔镇 (k)第11期 大柳塔镇 (1)第12期 大柳塔镇 一 中鸡镇 中鸡镇 中鸡镇 心 孙家岔镇 孙家岔镇店塔镇 镇家岔镇店塔镇   
尔林兔镇 店塔镇 尔林兔镇 尔林兔镇 锦界镇神木镇栏杆堡镇 锦界镇 神木镇栏杆堡镇 锦界镇神木镇栏杆堡镇 大保当镇家保镇 沙镇 天保当镇 沙镇 天保当镇 沙镇镇 贺家川镇 贺家川镇 贺家川镇 花石崖镇 花石崖镇 花石崖镇 万镇 万镇 万镇   
(m)第13期 大柳塔镇 中鸡镇   
尔林兔镇孙家岔镇店塔镇 锦界镇神木镇栏杆堡镇 0.98 0.86 0.74 0.62 0.50 0.38 0.26 大保当镇家保镇 0 70km L 贺家川镇 花石崖镇 万镇

区为研究区的10月份干旱规模再次增强的结论有所出入，可能与本研究区面积较小，地形复杂有关。

# 3.2旱情频率时空特征分析

3.2.1旱情频率的空间分布从干旱发生(达到轻旱及以上等级就视为干旱发生)频率来看(图6)，神木市发生土壤干旱的平均频率为 $6 4 . 4 4 \%$ ，并呈现出由东南向西北增大的变化，与干旱强度的空间分布特征一致，在一定程度上体现出该区域干旱时空特征的稳定性和长期的持续性，可针对性的指导不同区域的防旱抗旱。干旱发生频率最高的地区是西部的大保当镇，为 $8 9 . 8 8 \%$ ,尔林兔镇、锦界镇发生干旱的频率也较高，平均为 $7 0 . 3 0 \%$ 和 $7 6 . 4 3 \%$ 。高强度干旱和高频率干旱足以说明该区域是神木市抗旱的重点区域。栏杆堡镇的干旱发生频率最低，平均也达到 $5 2 . 3 2 \%$ ,花石崖镇和贺家川镇的干旱发生频率也较低，两镇平均达到 $5 4 . 3 1 \%$ 和 $56 . 2 7 \%$ 。整体看来，神木市在作物生长季内的防旱形势比较严峻。

109°40'E 1100'E 110°20'E 110°40'E   
20060 太柳塔镇 330.3M 中鸡镇 红 孙家岔镇   
10.60 3 店塔镇 10.60 尔林兔镇 锦界镇 神木镇 栏杆堡镇   
20580 ·大保当镇 305080 马镇 高家堡镇 沙镇 频率/%.88 贺家川镇   
20080 0 20km 花石 300.80 4.05 L   
109°40'E 110°0'E 11020'E 110°40'E

从不同等级干旱发生频率来看（图7)，中旱$( 2 4 . 9 8 \%$ ） $>$ 轻旱 $> ( 2 2 . 0 8 \% ) >$ 重旱（ $1 3 . 7 2 \%$ )>特旱（204号 $( 3 . 6 0 \%$ )。虽然特旱发生频率最低，但变异系数最大，达到0.593,体现出其显著的地理差异，呈现出西高东低的明显特征。神木市西部的大保当镇以及锦界镇的特旱发生频率明显高于其他地区，平均为$6 . 1 3 \%$ 和 $5 . 8 4 \%$ ，其中最大值出现在大保当镇，达到$1 5 . 3 8 \%$ ，说明大保当镇为该地防旱抗旱的重点区域。重旱发生频率比特旱高，但变异系数低于前者，为0.419,说明重旱的地理差异相比特旱较小（图7b)，主要集中在西部的大保当镇( $2 0 . 4 8 \%$ )和锦界镇 ${ \cdot } 1 9 . 6 3 \%$ )。发生频率最高的中旱，其高频区与特旱和重旱相同(图7c)，但其变异系数仅为0.142，地理差异较小，体现出中旱在时空上具有普遍性，说明神木市防御干旱的量级应达到抵御中等干旱胁迫的水平，高频区空间上主要集中在西部的大保当镇 $2 8 . 8 2 \%$ )和锦界镇 $( 2 7 . 7 3 \%$ )。轻旱发生频率在空间上略呈北高南低的特征，其变异系数最小，只有0.129，地理差异最不明显，西北部的尔林兔镇和北部大柳塔镇平均频率最高，分别为 $2 4 . 2 0 \%$ 和$2 4 . 0 3 \%$ 。神木市干旱发生频率高且干旱类型多样，是因为其位于我国西北地区东部，主要受东南季风及其特殊的地理位置影响，天气复杂多变，年内降水变化很大，时空分配不均，陆面感热通量强且蒸发强烈[25-26]

3.2.2旱情频率的年内变化 统计19a每一期各等级干旱的发生频率，进行了旬尺度和季尺度的旱情频率的年内变化分析，以4—5月为春季，6—8月为夏季，9—10月为秋季(表2)，具体分析结果如图8所示。2001—2019年神木市作物生长季季尺度干旱发生频率为：春旱 $>$ 伏旱 $\cdot >$ 秋旱，与王利娜等7对黄土高原的研究结果一致，这是因为黄土高原地区季风气候降雨多发生在夏、秋季，春季更易形成干旱。神木市春季植被覆盖度低(NDVI为0.21)，地表温度较高 $( 3 1 . 9 8 ~ \mathrm { ^ { \circ } C } )$ )，降水最少 $\left( 0 . 7 5 \mathrm { m m } \cdot \mathrm { d } ^ { - 1 } \right)$ ，春旱发生频率最高，平均达到 $9 6 . 8 9 \%$ ，且以中旱最高，平均频率为 $4 3 . 9 2 \%$ ,突出体现在4月下旬至5月上旬(第2期)，此时高达 $5 4 . 2 0 \%$ 。重旱和轻旱在春季发生频率相当，两者均达到 $2 4 . 2 0 \%$ 。虽然，特旱发生频率最少，但也有 $4 . 5 1 \%$ ,体现出春旱的严重性。进入夏季（7月，第6期），地表温度略有升高$( 3 4 . 9 1 ~ \mathrm { ^ { \circ } C } )$ )，北上的东南季风带来大量水汽，形成丰富降水 $( 2 . 9 \ \mathrm { m m \cdot d ^ { - 1 } }$ )，且植被覆盖度增大（NDVI为0.34)，伏旱发生频率明显低于春旱，平均下降了$2 2 . 6 4 \%$ ，亦以中旱发生频率最高 $( 2 7 . 4 8 \% )$ )，体现在7月中旬（第7期），此时，中旱发生频率达到了$3 6 . 6 8 \%$ ,其次为轻旱 $( 2 4 . 9 8 \%$ ),而重旱相对于春季发生频率明显降低，降低了 $8 . 2 6 \%$ 。但特旱发生频率却相对春季增高了 $1 . 2 6 \%$ ，其原因可能是6月（第5\~6期)降水开始增多(图 $9 \mathrm { c }$ ),地表温度还处于高值

10940'E 1100'E 110°20'E 11040'E 109°40'E 1100'E 110°20'E 110°40'E   
30030 (a)特大干旱 (b)严重干旱 大柳塔镇 300.30 大柳塔镇 中鸡镇 中鸡镇 孙家盆镇店塔镇 孙家岔镇   
N0.60 尔林兔镇 红碱淖 O 红兔镇 店塔镇 代 10.69 锦界镇 锦界镇 神木镇 栏杆堡镇 神木镇 栏杆堡镇   
30580 ? 大保当镇 马镇 大保当镇 D 马镇 304080 高家堡镇\~\~ 沙镇 高家堡镇 wS 沙镇 频率/% 贺家川镇 频率/% 贺家川镇   
33302M 35.22 0 20km 老石 35.22 0 20km 花石崖镇 300.80 0.00 L 1 0.00 L 1   
109°40'E 110°0'E 110°20'E 11040'E 109°40'E 110°0'E 110°20'E 110°40'E   
109°40'E 110°0'E 110°20'E 110°40'E 109°40'E 110°0'E 110°20'E 11040'E   
30030 (c)中度干旱 (d)轻度干旱 300.30 大柳塔镇 大柳塔镇 中鸡镇 中鸡镇   
N0.60 尔林免镇 孙家岔镇 店塔镇 尔林兔镇 红碱 孙家岔镇店塔镇 10.60 锦界镇 锦界镇 神木镇 栏杆堡镇 神木镇 栏杆堡镇   
30580 + 大保当镇 2 马镇 D 大保当镇 马镇 30580 高家堡镇 35 沙镇 高家堡镇 \~沙镇 频率/% 贺家川镇 频率/% 贺家川镇   
30080 35.22 0 20km 花石镇 35.22 0 20km 花石 35080 0.00 0.00   
109°40'E 110°0'E 110°20'E 110°40'E 109°40'E 110°0'E 110°20'E 110°40'E

![](images/15f5d796a758a9856aa6d27aed5a80bccf6f94c75a43b13e6fc0317d206a6cce.jpg)  
图7神木市作物生长季(4—10月)不同等级干旱频率分布  
Fig.7Frequency distributionof diffrent grades ofdrought inthecrop growing season (April to October)in Shenmu City   
图8不同时间尺度各等级干旱发生频率  
Fig.8Frequency of droughtsat different time scales and levels

状态(图9b)，因植被对气候的响应具有滞后性，在经历了春季长期的干旱胁迫后，短期的降水增多和温度下降无法逆转其受旱状态，具体体现在植被覆盖度的缓慢增加（图 $9 \mathrm { a }$ )。9月(第10期)东南季风南撤，降水减少 $( 1 . 7 5 \ \mathrm { m m ^ { . } d ^ { - 1 } } )$ ，植被覆盖度略微降低（NDVI为0.33），但入秋后地表迅速降温！ $( 2 3 . 1 9 { \mathrm { ~ } } ^ { \circ } \mathrm { C } )$ ，足以抵消因降水和植被减少导致的干旱胁迫，干旱强度整体上有所减弱，使得秋旱发生频率最小（ $1 9 . 5 5 \%$ )，区域整体上以轻旱较为频发( $1 6 . 3 1 \%$ ），中旱和重旱发生频率明显减少，只有 $2 . 9 1 \%$ 和

0.2 (a)植被 4033021050 (b)温度 y=-0.975x+37.229 nana28g (c)降水y=0.0132x+0.2032  
0.1 y=0.1035x+1.1609  
0.0  
1234567891011121314 1234567891011121314 1234567891011121314期号 期号 期号

$0 . 3 4 \%$ ，特旱消失。综上所述，神木市干旱防御应以春季为主，同时也不能忽略夏初的特旱高发期，因为该时期正是作物生长的关键期，更应积极采取有效的防旱抗旱措施。

# 3.3旱情变化趋势时空分析

3.3.1旱情变化趋势空间分布采用一元线性回归分析法，逐像元计算得到SMMI的变化趋势(slope）[28],用以分析神木市2001—2019年作物生长季土壤干旱的变化趋势。由图10可知,神木市 slope值在-0.245\~0.150之间，平均值为0.086，总体上旱情呈略微减轻趋势，这与岳辉[29]等对陕北黄土高原区域的研究结果一致，分析发现VCI、TCI和PCI的slope值平均分别为0.126、0.038和0.012，说明该区域旱情趋势是温度缓慢降低、降水缓慢增长、植被相对显著增长共同作用的结果(图11)。这是因为自1999年起，我国实施的退耕还林还草工程，陕北地区林地和草地覆盖率提升，土壤湿度增加，生态环境得到了有效改善[30-31],使得 2001—2019年神木市植被生长状况整体呈好转趋势，这与王涛等[2]对榆林的研究结果一致。加上植被增多对温度升高有较好的抑制作用[33],与神木市2001—2019年地表温度有所降低的结论一致。同时，区域降雨量略微增多(slope为1.884)，这与李双双等[34]对陕北地区的研究结果一致。全市仅有 $0 . 4 4 \%$ 的区域旱情略微有所加剧 $\scriptstyle ( s l o p e < 0 )$ )，主要集中在西北部尔林兔镇的红碱淖(slope为-0.098)，该地区相较于其他区域属于湿润地区，但19a间红碱淖湿地年均地表温度(slope为1.547)和年蒸发量明显增加，湖泊面积总体呈现萎缩趋势[35]，干旱情况加剧。

3.3.2旱情变化趋势年内变化在季节尺度上，神木市旱情均呈现出略微减轻变化趋势，但不显著（图12）。从旱情变化趋势来看，夏季（slope为$0 . 0 0 2 ) >$ 秋季(slope为 $0 . 0 0 5 ) \mathrm { > }$ 春季（slope为0.002）。夏季的旱情变化趋势略高于秋季和春季，是因为夏季降水(slope为0.020)的增长趋势明显，地表温度降低幅度大(slope为-4.890)，旱情得到显著缓解。

109°40'E 110°0'E 11020'E 110°40'E   
30030 太柳塔镇 3030.3M 中鸡镇   
N0.60 尔林兔镇 孙家岔镇店塔镇， 20.60 锦界镇 神木镇 栏杆堡镇   
30580 大保当镇 3058M 马镇 高家堡镇 S 沙镇 slope 贺家川镇   
33580 0.150 0 20km 花石 33080 0.245   
109°40'E 110°0'E 110°20'E 110°40'E

# 4结论

以具有典型黄土高原地貌地理特征的陕西省神木市为研究区，重点考虑降水在复杂地形旱情中的决定性作用，基于最新的GPM高精度雷达降水产品数据，构建综合考虑植被、温度和降水的土壤干旱遥感监测模型，并从干旱强度、频率和趋势3个层面上分析2001—2019年研究区作物生长季（4—10月)旱情的时空演变规律，主要结论如下：

（1）土壤干旱遥感监测模型： $\mathrm { S M M I { = } 0 . 3 8 4 V C I { + } }$ $0 . 7 6 9 \mathrm { T C I } + 0 . 6 4 0 \mathrm { P C I } - 0 . 0 2 2$ ，能很好地反映研究区的土壤相对湿度，是能有效揭示区域土壤干旱的最佳模型。温度和降水在该模型中的权重较高，说明区域旱情主要受温度和降水控制。

(a)VCI (b) TCI (c)PCI 柳塔镇 大柳塔镇 柳塔 中鸡镇 . 中鸡镇 中鸡镇 红 孙家岔镇 红稀 孙家岔镇 红碱 孙家岔镇   
尔林兔 店塔镇 尔林兔镇 店塔镇 尔林兔镇 店塔镇 锦界镇 锦界镇 锦界镇 神木镇栏杆堡镇 神木镇栏杆堡镇 神木镇 栏杆堡镇   
天保当 马镇 s 家保 马镇 天保当 5 沙镇 沙镇 0.271 石家川镇 0.102 花石家川镇 0.030 花石家州镇 0 20km 菲 0 20km 0 20km -0.031 0.064 -0.001   
(d) NDVI (e)LST (f) GPM 柳塔镇 柳塔镇 大柳塔镇 中鸡镇 鸡镇 红威 孙家岔镇 红 孙家岔镇 红碱 源 孙家岔镇   
尔林兔镇 尔林兔镇 店塔镇 林兔镇 店塔镇 锦界镇 神木镇 栏杆堡镇 锦界镇 神木镇 栏杆堡镇 锦界镇神木镇 栏杆堡镇 大保当镇 马镇 大保当镇 马镇 大保当镇\~ 马镇   
slope271 商家 slope 818 西蒙聚银石 贺家川镇 沙昴镇 slop2.423 福家生 -0.031 20km 4.571 0 20km 1.510 0 20km 镇   
(a)春季 (b)夏季 (c)秋季 柳塔镇 塔镇 大柳塔镇 中鸡镇 中鸡镇 中鸡镇 红 孙家盆镇店塔镇 红城 孙家岔镇 红 孙家岔镇   
尔林兔镇 尔林兔镇 店塔锁 尔林兔镇 店塔镇 锦界镇 锦界镇 锦界镇 神木镇栏杆堡镇 神木镇栏杆堡镇 神木镇栏杆堡镇 保当 贺家川镇 0.008 花石 0.008 花石岸 0.008 花石崖镇 -0.012 20km 泪 -0.012020km -0.012 20km

(2）神木市作物生长季多年平均干旱强度整体呈三种等级类型，分别为轻旱、中旱和无旱，且以轻旱为主。神木市干旱强度的年内变化呈现出6月上旬之前的旱情加剧变化，强度由轻旱逐渐发展为重旱，7月区域呈持续的旱情减缓变化，强度由重旱逐渐发展至中旱、轻旱，且8月中旬后进入无旱主导状态，直至10月底干旱完全消失。

（3）神木市干旱发生平均频率为 $6 4 . 4 4 \%$ ，呈现出由东南向西北增大的变化。不同等级干旱发生频率表现为：中旱 $>$ 轻旱 $>$ 重旱 $. >$ 特旱。特旱发生频率虽小，但地理差异显著；中旱发生频率最高，区域差异性较小。神木市春旱现象严重，且以中旱发生频率最高。伏旱发生频率有所减弱，但仍以中旱最为频发。人秋后，干旱强度整体上有所减弱，全年秋旱发生频率最低且多为轻旱

（4）2001—2019年间，神木市旱情呈略微减轻变化趋势，红碱淖湿地干旱情况加剧。季节尺度上，神木市旱情均呈现出不显著的略微减轻变化趋势，伏旱减缓趋势略大于秋旱，春旱减轻趋势最小。

致谢：本研究所用气象站点数据和土壤相对湿度数据由陕西省神木市气象局提供，在此表示衷心的感谢！

# 参考文献(References)：

[1]史本林,朱新玉,胡云川,等.基SPEI指数的近53a河南省干旱 时空变化特征[J].地理研究,2017,27(3):311-325.[Shi Benlin, Zhu Xinyu,Hu Yunchuan, et al. Spatial and temporal variations of drought in Henan Province over a 53 year period based on standardized precipitation evapotranspiration index[J]. Geographical Research,2017,27(3): 311-325.]   
[2]Chang Jianxia,Li Yunyun,Wang Yimin,et al.Copula-based drought risk assessment combined with an integrated index in the Wei River Basin, China[J]. Journal of Hydrology,2016,540: 824- 834.   
[3]Li Xiaolan,Lyu Xiang,Wang Xiaohong,et al.Biotic and abiotic stress-responsive genes are stimulated to resist drought stress in purple wheat[J]. Journal of Integrative Agriculture,2O20,19(1): 33-50.   
[4]高雅,王晓飞,高懋芳,等.基于温度植被干旱指数的曲靖市干 旱监测研究[J].中国农学通报,2020,36(9):37-45.[Gao Ya, Wang Xiaofei, Gao Maofang,et al. Drought monitoring in Qujing based on temperature vegetation drought index[J]. Chinese Agricultural Science Buletin,2020,36(9): 37-4.]   
[5]McKee TB,Doesken NJ,Kleist J.The relationship of drought frequency and duration to time scales:Proceedings of vulnerability [M]. Cambridge: Cambridge University Press,1993:100-184.   
[6]孙博,钱静,陈曦,等.常见遥感干旱监测指标在哈萨克斯坦的 一致性分析[J].干旱区研究,2020,37(3):663-670.[Sun Bo, Qian Jing,Chen Xi,et al. Consistency and comparison among remote sensing drought indices and SMAP soil moisture in Kazakhstan[J]. Arid Zone Research,2020,37(3): 663-670.]   
[7]卢晓宁,洪佳,王玲玲,等.复杂地形地貌背景区干旱风险评价 [J].农业工程学报,2015,31(1):162-169.[Lu Xiaoning,Hong Jia,Wang Lingling,et al.Drought risk assessment in complex landform area[J]. Transactions of the Chinese Society of Agricultural Engineering,2015,31(1): 162-169.]   
[8]Huete A,Didan K,Miura T,et al. Overview of the radiometric and biophysical performance of the MODIS vegetation indices[J]. Remote Sensing of Environment, 2002,83(1): 195-213.   
[9]Sandholt I, Rasmussen K, Andersen J. A simple interpretation of the surface temperature/vegetation index space for assessment of surface moisture status[J]. Remote Sensing of Environment, 2002, 79(2): 213-224.   
[10]Vicente-Serrano S M, Begueria S,Lopez-Moreno JI. Amultiscalar (7): 1696-1718.   
[11] 林妍,高伟,师晋平,等.基于MODIS 和FY-2D卫星降水数据的 遥感旱情监测研究[J].干旱区资源与环境,2014,28(12):51- 57.[Lin Yan,Gao Wei,Shi Jinping,et al.Remote sensing monitoring of drought based on MODIS and FY-2D satellite rainfall data [J].Journal of Arid Land Resources and Environment,2014,28 (12): 51-57.]   
[12]卢晓宁,张静怡,王玲玲,等.综合考虑植被、温度和降水的四川 省月尺度伏旱遥感监测[J].自然资源学报,2017,32(7):1145- 1157.[Lu Xiaoning,Zhang Jingyi,Wang Lingling,et al. Remote sensing monitoring of summer drought at monthly-scale considering vegetation, temperature and precipitation in Sichuan Province [J]. Journal of Natural Resources,2017,32(7): 1145-1157.]   
[13]Cong D, Zhao S, Chen C,et al. Characterization of droughts during 2001-2014 based on remote sensing:A case study of Northeast China[J]. Ecological Informatics,2017,39: 56-67.   
[14] Tang Guoqiang,Ma Yingzhao,DiL,et al.Evaluation of GPM Day1 IMERG and TMPA Version-7 legacy products over Mainland China at multiplespatiotemporal scales[J]. Journal of Hydrology, 2016,533: 152-167.   
[15]曾岁康,雍斌.全球降水计划IMERG 和GSMaP反演降水在四川 地区的精度评估[J].地理学报,2019,74(7):1305-1318.[Zeng Suikang,Yong Bin.Evaluation of the GPM-based IMERG and GSMaP precipitation estimates over the Sichuan region[J]. Acta Geographica Sinica,2019,74(7): 1305-1318.]   
[16] 陈鲁燕.基于MODIS数据的榆林土壤水分研究[D].西安:长安 大学,2015.[Chen Luyan. The Research Based on the MODIS Data of Soil Moisture in Yulin[D].Xi'an: Chang'an University, 2015.]   
[17]卢晓宁,曾德裕,黄玥,等.四川省伏旱及驱动因子多尺度分析 [J].农业工程学报,2019,35(9):138-146.[Lu Xiaoning, Zeng Deyu,Huang Yue,et al.Multi- scale analysis of drought and its driving factors in Sichuan[J]. Transactions of the Chinese Society of Agricultural Engineering,2019,35(9): 138-146.]   
[18] 卫新东,宋林韩,王筛妮,等.黄河西岸陕西各县市耕地质量时 空变化特征及其分异规律[J].水土保持研究,2021,28(2):326- 334.[Wei Xindong,Song Linhan,Wang Shaini,et al. Spatial and temporal changesand itsvariation of cultivated land quality of Counties and cities in Shaanxi on the west bank of the Yellow River[J].Research of Soil and Water Conservation,2021,28(2): 326- 334.]   
[19]Wang K,Li T,Wei J.Exploring drought conditions in the thre riv er headwaters region from 20O2 to 2011 using multiple drought indices[J].Water,2019,11(2): 190.htps://doi.org/10.3390/w11020 190.   
[20]中国国家标准化管理委员会.中华人民共和国国家标准:农业 干旱等级GB/T32136-2015[S].北京：中国标准出版社，2015.

[Standardization Administration of the P.R.C.National Standard

of the People’s Republic of China:Agricultural Drought Grade Standard GB/T 32136-2O15[S].Beijing:China Standard Press, 2015.]   
[21] 刘宇峰,原志华,封建民,等.基于地表湿润指数的1959-2014 年陕西省地表干湿时空变化特征[J].干旱区地理,2016,39(6): 1186-1196.[Liu Yufeng,Yuan Zhihua,Feng Jianmin,et al.Drywet condition of Shaanxi Province in recent 56 years based on surface humidity index[J].Arid Land Geography,2016,39(6):1186- 1196.]   
[22] 徐丽萍.黄土高原地区植被恢复对气候的影响及其互动效应 [D].西安:西北农林科技大学,2008.[Xu Liping.Influence and Reciprocal Efects of Vegetation Rehabilitation on Regional Climate in Loess Plateau[D].Xi'an: Northwest A&F University,2008.]   
[23] 胡鹏飞,李净,王丹,等.基于MODIS 和TRMM数据的黄土高原 农业干旱监测[J].干旱区地理,2019,42(1):172-179.[Hu Pengfei,Li Jing,Wang Dan,et al.Monitoring agricultural drought in the Loess Plateau using MODIS and TRMM data[J]. Arid Land Geography,2019,42(1): 172-179.]   
[24] 李菁,王连喜,沈澄,等.几种干旱遥感监测模型在陕北地区的 对比和应用[J].中国农业气象,2014,35(1):97-102.[Li Jing, Wang Lianxi, Shen Cheng,et al.Application and comparison of several drought monitoring models in northern Shaanxi[J]. Chinese Journal of Agrometeorology,2014,35(1): 97-102.]   
[25] 欧廷海,钱维宏.东亚季风边缘带上的植被变化[J].地球物理学 报,2006,49(3): 698-705.[Ou Tinghai, Qian Weihong.Vegetation variations along the monsoon boundary zone in Eas Asia[J]. Chinese Journal of Geophysics,2006,49(3): 698-705.]   
[26] 周连童,黄荣辉.中国西北干旱、半干旱区感热的年代际变化特 征及其与中国夏季降水的关系[J].大气科学,2008,32(6): 1276-1288.[Zhou Liantong,Huang Ronghui. Interdec-adal variability of sensible heat in aird and semi-arid and semi-arid regions of Northwest China and its relation to summer precipitation in China[J]. Chinese Journal of Atmospheric Sciences,2Oo8,32(6): 1276-1288.]   
[27] 王利娜,朱清科,翁白莎,等.1961—2012年黄土高原干旱时空 分布特征[J].水利水电技术,2018,49(2):15-22.[Wang Lina, Zhu Qingke,Weng Baisha,et al. Temporal and spatial distribution characteristics of drought in Loess Plateau from 196l to 2012[J]. Water Resources and Hydropower Engineering, 2018,49(2):15- 22.]   
[28]严恩萍,林辉,党永峰,等.2000—2012年京津风沙源治理区植 被覆盖时空演变特征[J].生态学报,2014,34(17):5007-5020. [Yan Enping,Lin Hui, Dang Yongfeng,et al. The spatiotemporal changes of vegetation cover in Beijing- Tianjin sandstorm source control region during 2000-2012[J]. Acta Ecologica Sinica, 2014, 34(17): 5007-5020.]   
[29] 岳辉,刘英.基于NDVI-Albedo特征空间的陕西省干旱与荒漠 化遥感监测[J].西北林学院学报,2019,34(1):198-205.[Yue Hui,Liu Ying.Monitoring of drought and desertification in Shaanxi Province based on NDVI- Albedo space [J]. Journal of Northwest Forestry University,2019,34(1):198-205.]   
[30] 邓元杰,侯孟阳,谢怡凡,等.退耕还林还草工程对陕北地区生 态系统服务价值时空演变的影响[J].生态学报,2020,40(18): 6597-6612.[Deng Yuanjie, Hou Mengyang,Xie Yifan, et al. Impact of the grain for green project on the temporal and spatial evolution of ecosystem service value in northern Shaanxi[J].Acta Ecologica Sinca,2020,40(18): 6597-6612.]   
[31] 成佩昆,胡守庚,孙涛,等.陕西省退耕还林工程对植被恢复的 效应——基于PCSE 修正的面板数据模型[J].干旱区研究, 2018,35(6): 1477-1486.[Cheng Peikun, Hu Shougeng, Sun Tao, et al.Effect of grainfor gren project on vegetationregeneration in Shaanxi Province: Based on PCSE panel data model[J].Arid Zone Research,2018,35(6): 1477-1486.]   
[32] 王涛,杨梅焕.榆林地区植被指数动态变化及其对气候和人类 活动的响应[J].干旱区研究,2017,34(5):1133-1140.[Wang Tao, Yang Meihuan. Dynamic change of NDVI and its response to climate change and human activities in Yulin, Shaanxi Province, China[J]. Arid Zone Research,2017,34(5): 1133-1140.]   
[33] 王圆圆,李贵才,郭徵,等.1979年-2014年三峡库区月平均气 温的时空变化分析[J].遥感学报,2018,22(3):487-496.[Wang Yuanyuan,Li Guicai, Guo Zheng,et al. Spatial-temporal analysis of monthly air temperature changes from 1979-2014 in the Three Gorges Dam region[J]. Journal of Remote Sensing,2O18,22(3): 487-496.]   
[34] 李双双,孔锋,韩鹭,等.陕北黄土高原区极端降水时空变化特 征及其影响因素[J].地理研究,2020,39(1):140-151.[Li Shuangshuang,Kong Feng, Han Lu, et al. Spatiotemporal variability of extreme precipitation and influencing factors on the Loess Plateau in northern Shaanxi province[J].Geographical Research, 2020,39(1): 140-151.]   
[35] 卓静,朱延年,王娟,等.红碱淖面积时空演变规律及保护措施 成效[J].中国沙漠,2019,39(4):195-203.[Zhuo Jing,Zhu Yannian,Wang Juan,et al. Spatio-temporal change of water area in Hongjiannao Lake and the effectiveness of protection measures[J]. Journal of Desert Research,2019,39(4): 195-203.]

# Remote sensing monitoring of soil drought in Shenmu City, Shaanxi Province integrating GPM precipitation data

TAN Huizhi'， YIN Qian'，JI Liwen'，LU Qian²，LU Xiaoning'，CUI Linlin',XIA Zhiye'， XU Weixin'， CHEN Jun'  
(1.College of Resources and Environment, Chengdu University of Information Technology,Chengdu 610225,Sichuan, China; 2.Shenmu Meteorological Bureau, Shenmu,7193Oo, Shaanxi, China)

Abstract: Global warming has aggravated the drought trend, producing a severe threat to agriculture and animal husbandry in the arid and semi-arid regions of northwest China.The existing remote sensing methods for monitoring drought mostly only consider vegetation and temperature,ignoring the role of precipitation.Additionally,most research is limited to the clasification of relative drought levels.Our research starts from the typical landform features of the LoessPlateau in Shenmu City，Shaanxi Province,and the severity of drought stress in the Hongjiannao wetland. Considering the decisive role of precipitation on drought，especially in complex geomorphic background areas, we apply higher-precision GPM precipitation data to conduct a comprehensive drought model, which can truly reveal the relative humidity of the soil.The results show that the soil drought remote sensing monitoring model $\mathrm { ( S M M I { = } 0 . 3 8 4 V C I + 0 . 7 6 9 T C I + 0 . 6 4 0 P C I { - } 0 . 0 2 2 ) }$ ，which comprehensively considers vegetation, temperature,and precipitation, can accurately predict the relative humidity within $1 0 \ \mathrm { c m }$ of the soil surface in Shenmu.The equal weights of temperature and precipitation in the model indicate that drought in this area is primarily determined by temperature-led evapotranspiration and the water supply of precipitation. The overall crop growth season in Shenmu is in a state of light drought,and the average frequency of drought occurrence is $6 4 . 4 4 \%$ (moderate drought $>$ mild drought $>$ severe drought $>$ extraordinary drought). The intensity and frequency of drought present a spatial diferentiation characteristic of being higher in northwest and lower in the southeast.Although the frequency of extreme drought is low,the geographical diference is significant. The frequency of mild drought is high,but with a less evident geographical diference.The weakening of the winter monsoon caused a decrease in precipitation.Therefore,the drought intensity of Shenmu gradually developed from alight drought in April to a severe drought between late May and early June.Afected by the southeast monsoon in July,the rainfall increases,and the severity of drought decreases.After mid-August, Shenmu enters into a state dominated bythe absence of drought,and intothe end of October,there is no drought at all.In terms of seasons,the spring drought is severe,and is characterized by the highest frequency of moderate drought. Although the frequency of summer drought is quite low,the frequency of extreme drought is higher than that of spring.The autumn drought was of the lowest frequency and a light drought dominated. Over 19 years,the drought trend in Shenmu showed a slight reduction,but thatof Hongjiannao wetland showed an increase due to the significant increase in annual evaporation.

Keywords: global precipitation measurement；moderate-resolution imaging spectroradiometer； drought； rela-tive soil humidity； Shenmu City