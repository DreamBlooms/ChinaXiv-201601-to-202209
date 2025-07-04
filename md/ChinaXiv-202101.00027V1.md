# 多源降水数据的小流域水文模拟效用评估

冯克鹏1,3.5，洪阳²，田军仓1,3,5，唐国强4，阚光远4，罗翔宇²（1宁夏大学土木与水利工程学院,宁夏 银川750021；2 Schoolof Civil Engineering and EnvironmentalScience,UniversityofOklahoma,Norman,OK73072,USA；3宁夏节水灌溉与水资源调控工程技术研究中心,宁夏 银川750021；4 清华大学水沙科学与水利水电工程国家重点实验室北京100084;5旱区现代农业水资源高效利用教育部工程研究中心，宁夏 银川750021)

摘要：小流域是研究小微尺度水文水资源系统演变规律的理想对象，是用于计算河流产水产沙的最小单元，是水文及水土流失研究与管理的最佳地域尺度。通过遥感技术，气候模式获得降水数据，并驱动分布式水文模型,模拟和预测水文过程,是流域水文水资源研究的必然趋势。以NO-AA-CPC-US降水作为参照,在美国不同地区的9个小流域，评估卫星降水产品PERSIANN,PERSI-ANN-CDR,TRMM-3B42V7,GPM-IMERG,雷达降水StageIV以及气候模式ERA5降水产品的精度，并用这7种降水产品驱动CREST分布式水文模型，评估了7种降水产品的水文模拟效用。研究表明：各降水产品与NOAA-CPC-US降水吻合程度从高到低，依次是StageIV雷达降水,PERSIANN-CDR和GPM-IMERG次之，再次是PERSIANN和ERA5,最后是TRMM-3B42V7。各降水产品在美国北部高纬度地区和西部山地等区域的小流域降水估算精度略低，在美国中部，南部，东部的小流域有较好的降水精度。在水文模拟效用评估中，设定相同率定期,分别使用7种降水产品率定CREST模型参数，得到率定参数集后，在相同验证期对流域日径流过程进行模拟。结果表明：NO-AA-CPC-US和StageIV雷达降水在各小流域水文模拟中效果较好，在美国北部和西部地区，使用PERSIANN,PERSIANN-CDR,GPM-IMERG,ERA5降水进行水文模拟时需要谨慎。TRMM-3B42V7的小流域水文模拟效果不理想。

关键词：小流域；CREST水文模型；多源降水；水文模拟

# 文章编号：

降水是水文循环的主要环节之一，也是开展水文模型研究的主要数据输人。降水在气候，气象，水文预报，水文灾害等领域的研究，监测和预测中发挥着重要作用[。受气候因素和下垫面因素影响，降雨的形成和分配在时空分布不均匀，进而又影响了陆地径流、蒸散发、土壤水分、地下水等流域水循环过程。因此，对降水的准确估计和大范围快速获取高时空分辨率的连续降水观测数据，不仅能够促进我们对水循环的理解，而且对流域水文过程模拟以及预报也具有重要意义。目前，获得降水数据的方法有4种：地面雨量站观测，地面雷达探测降水，卫星遥感降水和气候系统模式数值模拟降水[2-3]。地面雨量站观测手段直接，精度较高，但受站点密度及其空间分布影响，难以给出复杂多变的降水空间分布；地面雷达测雨可以直接探测降水的空间分布，具有实时跟踪降水中心和空间变化的能力，但易受地形遮挡，雷达射线抬升等影响[4]。卫星遥感测雨虽然精度不如地面观测降水精度高，但它能够大范围，快速、便捷地获取具有一定时空精度的连续降水数据，一定程度上能弥补地面观测降水的不足，对无资料和少地面观测资料地区是一种有效的降水数据来源。气候系统模式可以模拟全球降水，然而受气候复杂性影响，其模拟结果在区域尺度仍存在较大不确定性[5-7]。一些气候模式的降水模拟

# 干旱区地理

数据还不能直接用于水文效用评估[8]。

近年来，随着上述4种降水数据获取技术的快速发展，以及机器学习算法在反演降水中的应用，涌现出大量不同时空分辨率的降水产品[9-]。同时，诸多学者针对不同降水产品，围绕降水精度评估、不同时空尺度降水变化，模拟水文效用等方面开展了大量研究[12-17],基于降水产品开发的全球或大中型区域尺度的径流模拟和实时预报系统，在多次水文灾害事件的预报和再现中得到了积极的评价[18-21]

然而，前人研究结论已发现降水产品目前尚存在明显的空间变异性，卫星，雷达等降水产品在不同维度地区的精度有差别，而且不同精度的降水产品又会导致径流模拟精度的差别，即多源降水产品在不同时空尺度的水文应用中仍存在明显的不确定性[22-28]。小流域是研究小微尺度水文水资源系统演变规律的理想对象，是水土流失治理，生态系统修复等研究工作的重要地理单元，也是用于计算河流产水产沙的最小单元，是水文及水土流失研究与管理的最佳地域尺度。近年来，学者在小流域尺度基于地面观测降水围绕产流系数，地表径流模拟，土壤水运动做了诸多研究工作[29-34],但就不同时空分辨率的降水产品在小流域尺度水文模拟和预报中的能力还有待深入研究。

鉴于此，本文选取分布在美国9个不同地理分区的小流域，以NOAA-CPC-US地面雨量站降水再分析数据作为参照，评估不同时空分辨率的卫星降水产品PERSIANN，PERSIANN-CDR，TRMM-3B42V7,GPM-IMERG,雷达降水StageIV以及气候模式降水产品ERA5的精度，并结合CREST分布式水文模型，模拟各小流域的日径流量过程，评估不同时空分辨率的多源降水产品在小流域尺度的水文模拟效用，从而为上述多源降水产品在水文行业中研究和应用提供参考。

# 2研究区域、数据和方法

# 2.1 研究区域

国内外对小流域的概念尚没有统一的定义。不同国家和组织，出于研究目的和角度的不同，划定小流域的标准也不同。本文所讨论的小流域，是依据美国能源部橡树岭国家实验室(OakRidgeNa-tionalLaboratory，USA）的河流分级系统（USSCE,TheU.S.Stream Classification System）。该系统将美国近260万条河流分为8级，从大到小分别为超大河流GreatRiver、大河LargeRiver、干流Main stem、中等河流 Medium River、小河 Small River、溪流Large Creek、小溪Creek、河源Headwater[35]。本文在美国大陆区域的不同地理分区，选取了9个闭合小流域。这些小流域中的河流在该河流分级系统中，属于河源Headwater或小溪Creek级别。这9个小流域的地理分区，流域面积，年均流量等信息见表1。

# 2.2研究数据

本文选用了NOAA-CPC-US，PERSIANN，PER-SIANN-CDR,TRMM-3B42V7,GPM-IMERG,Stage-IV和ERA5共7种降水数据。数据时间段为2002年1月1日 ${ \sim } 2 0 1 8$ 年6月30日。研究中设置时间分辨率为日尺度，空间分辨率为 $0 . 0 0 8 3 ^ { \circ } \times 0 . 0 0 8 3 ^ { \circ }$ （约$1 \mathrm { k m } ^ { 2 } .$ )。由于上述7种降水数据的时空分辨率不同，因此在数据预处理过程中，将时间分辨率小于日尺度的数据，通过累积转换为日尺度，空间分辨率则通过双线性插值统一到 $0 . 0 0 8 3 ^ { \circ } \times 0 . 0 0 8 3 ^ { \circ }$ 。

# 2.3方法

# 2.3.1NOAA-CPC-US降水该数据集是美国国家

表1选取的9个美国不同地理区域小流域的基本信息  
Tab.1 Nine small watersheds in different geographic regions of the United States   

<html><body><table><tr><td>序号</td><td>流域编码</td><td>流域名称</td><td>河流等级</td><td>面积/km²</td><td>地理分区</td><td>年均流量/m·Sec-</td></tr><tr><td>1</td><td>HUC0107000107</td><td>Smith River</td><td>Headwater</td><td>227.51</td><td>Northeast(NE)</td><td>4.18</td></tr><tr><td>2</td><td>HUC0312000306</td><td>Upper Telogia Creek</td><td>Headwater</td><td>348.89</td><td>Southeast(SE)</td><td>5.91</td></tr><tr><td>3</td><td>HUC0602000211</td><td>Oostanaula Creek</td><td>Headwater</td><td>182.00</td><td>Central</td><td>2.60</td></tr><tr><td>4</td><td>HUC0703000511</td><td>Kinnickinnic River</td><td>Headwater</td><td>444.00</td><td>East North Central(ENC)</td><td>3.16</td></tr><tr><td>5</td><td>HUC1012010909</td><td>Upper Spring Creek</td><td>Headwater</td><td>519.00</td><td>West North Central(WNC)</td><td>0.61</td></tr><tr><td>6</td><td>HUC1113030208</td><td>Little washita River</td><td>Headwater</td><td>625.85</td><td>South</td><td>1.48</td></tr><tr><td>7</td><td>HUC1506010304</td><td>Cherry Creek</td><td>Headwater</td><td>720.00</td><td>Southwest(SW)</td><td>0.91</td></tr><tr><td>8</td><td>HUC1710010104</td><td>Calawah River</td><td>Creek</td><td>351.88</td><td>Northwest(NW)</td><td>28.04</td></tr><tr><td>9</td><td>HUC1801021102</td><td>Trinity River</td><td>Creek</td><td>410.33</td><td>West</td><td>5.16</td></tr></table></body></html>

海洋和大气局气候预测中心（NOAAClimatePredictionCenter)基于地面观测降水的一个再分析降水产品。该数据集汇集上万个地面观测台站降水观测信息，并与雷达，卫星观测以及数值模型预测的降水进行比较，实施了质量控制。在考虑地形效应后，对数据进行优化插值，创建日降水场，最终形成具有更高定量准确性和一致性的降水产品。其空间分辨率为 $0 . 2 5 ^ { \circ }$ ,时间覆盖范围1979年1月1日至今，空间范围为 $2 0 . 0 { \sim } 5 0 . 0 ^ { \circ } \mathrm { N } , 2 3 0 . 0 { \sim } 3 0 5 . 0 ^ { \circ } \mathrm { E } .$ 覆盖了美国大陆地区。数据下载地址https://www.esrl.noaa.gov/psd/data/gridded/data.unified.html。

2.3.2NCEP-StageIV 雷达降水NCEP-StageIV是美国气象局国家环境预报中心的雷达定量估测降水产品，项目起始于2001年12月1日，数据分发起始于2002年1月1日。其数据结合全美大约150个多普勒新一代天气雷达的降水估计值和约5500个地面雨量计的测量值，由分布在美国大陆的12个河流预报中心按各自区域生产。数据采集开始于每小时的33分钟，并以1h和 $6 \mathrm { { h } }$ 为时间步长进行累积计算，迭代复核和人工质量控制，最后将各区域数据镶嵌合成美国大陆雷达降水定量估测数据[36]该数据空间分辨率 $4 ~ \mathrm { k m }$ ,时间分辨率 $1 \mathrm { h } , 6 \mathrm { h } , 2 4 \mathrm { h }$ 降水单位 $\mathbf { m } \mathbf { m }$ 。数据详细特性及下载链接可参考National Stage IV QPE Product 网站(www.emc.ncep.noaa.gov/mmb/ylin/pcpanl/stage4/）。本文选用Stage-IV时间分辨率6h降水估测数据。

2.3.3PERSIANN降水PERSIANN降水数据集由美国加州大学欧文分校(UniversityofCalifornia,Ir-vine）水文气象与遥感研究中心（TheCenter for Hy-drometeorology and Remote Sensing,CHRS)开发。它基于地球同步卫星（GOES-8,GOES-10,GMS-5,Metsat-6,Metsat-7)提供的红外亮温图像,使用人工神经网络估算30分钟降雨率，然后汇总到1,3,6小时和日尺度的累积降雨量，并使用低轨道卫星(TRMM,NOAA-15,-16,-17,DMSPF13,F14,F15)降水估算产品定期修正。该数据产品时间覆盖2000年3月至今，空间范围 $6 0 ~ ^ { \circ } \mathrm { S } \sim 6 0 ~ ^ { \circ } \mathrm { N }$ ，空间分辨率 $0 . 2 5 ^ { \circ }$ 。数据下载源 https://chrsdata.eng.uci.edu/

2.3.4PERSIANN-CDR降水该数据集提供了从1983年至今，纬度范围为 $6 0 \ { } ^ { \circ } { \mathrm { S } } \sim 6 0 \ { } ^ { \circ } { \mathrm { N } }$ ，空间分辨率为 $0 . 2 5 ^ { \mathrm { ~ o ~ } }$ ,时间尺度为日的降雨量估算值。它由美国加州大学欧文分校开发的一种基于卫星遥感数据的降水产品。它在GridSat-B1红外卫星数据上通过人工神经网络算法(PERSIANN)产生；人工神经网络算法的训练是用美国环境预报中心(NCEP)StageIV雷达降水数据完成;然后，使用全球降水气候学项目（GPCP)月降水产品(GPCPv2.2)进行调整，最终形成该数据产品。美国国家研究委员会(NRC)将该数据定义为一份气候数据记录(ClimateDataRecord)，拥有足够长度，一致性和连续性的时间序列，用以确定气候变率和变化。数据下载源与PERSIANN相同。

2.3.5TRMM-3B42V7卫星降水TRMM卫星2015年4月由于燃料耗尽，正式结束观测任务，并于同年6月重新进入地球大气层，坠入南印度洋。由于TMPA降水产品的成功，TRMM团队并没有因为卫星终止观测而马上停止TMPA降水数据产品。而是，运用多种方法来延续TMPA降水产品，计划一直更新到2019年中期[37]。本文选择TRMM-3B42v7降水产品也意在评估当前条件下，该数据集模拟水文效用的能力。TRMM-3B42V7数据空间分辨率为 $0 . 2 5 ^ { \circ }$ ，时间分辨率为 $3 \mathrm { h }$ ，降水单位为 $\mathrm { m } \mathrm { m } \cdot \mathrm { h } ^ { - 1 }$ ，该数据通过NASA的TRMM卫星数据网站下载(https://pmm.nasa.gov/trmm/)

2.3.6GPM-IMERG卫星降水GPM是美国国家航空航天局(National Aeronautics and Space Adminis-tration,NASA)主导的TRMM的后续全球卫星降水观测计划。GPM的核心观测平台于2014年2月28日发射，能够提供全球3h以内雨雪观测数据。相较TRMM,GPM覆盖范围大，延伸至地球两极；时空分辨率高，传感器性能更优，可精确的探测微量降水。有关该降水产品的其它特性可参考其门户网站提供的技术文档(https://pmm.gsfc.nasa.gov/GPM）,GPM数据的Level $\mathbf { \mathrm { ~ 1 ~ } } \sim \mathbf { \mathrm { ~ 3 ~ } }$ 产品也可通过该网站下载。本文选用GPM多卫星反演全球范围30分钟雨雪数据产品（Integrated Multi-satellitE Retrievals forGPM，IMERG),版本05B_Final。该降水数据通过最新GPROF2017算法制作，校准并融合了GPM星座全部微波、红外以及地面观测和其他可能的传感器数据[38]。其空间分辨率为 $0 . 1 ^ { \circ }$ ，时间分辨率为30分钟，降水单位为 $\mathrm { m } \mathrm { m } \cdot \mathrm { h } ^ { - 1 }$ 。

2.3.7ERA5再分析数据集降水ERA5是欧洲中期天气预报中心(ECMWF)发布的第五代再分析数据集。相较于ERA-Interim和ERA-40前代再分析

# 干旱区地理

资料，ERA5采用了改进的数据同化系统(IFSCycle41r2），四维变分同化分析(4D-Var)以及辐射变分偏差校正，系统性地提升了该数据集的质量。ERA5提供了全球每天每小时的估计值，而且每小时输出分辨率相对于ERA-Interim而言有相当大的改进。该数据包括蒸发，湿度，气温，水汽压，降水等265种变量，时间覆盖范围1979年至今，空间分辨率 $0 . 2 5 ^ { \circ }$ $\times 0 . 2 5 ^ { \circ }$ ，空间覆盖范围 $8 9 . 1 4 2 ^ { \circ } \mathrm { S } \sim 8 9 . 1 4 2 ^ { \circ } \mathrm { N } , 1 8 0 ^ { \circ } \mathrm { W } \sim$ $1 8 0 ^ { \circ } \mathrm { E }$ 。本文选用该数据集中的小时尺度降水数据,数据下载源 https://cds.climate.copernicus.eu

2.3.8 流域径流、地形及潜在蒸散发数据本文9个小流域的流域边界，数字地形DEM和径流资料，分别采用美国地质调查局(USGS)提供的流域边界数据集[39]（Watershed Boundary Dataset V2.2.1）,美国$1 0 \mathrm { m }$ 精度数字高程模型(DEM)以及美国国家水信息系统数据。在DEM数据的基础上，应用GIS空间分析工具，提取流域河网，河网流向，河网汇聚等信息。本文用分布式水文模型，评估各降水数据水文模拟效用时，需要的潜在蒸散发数据(PET)，来自USGS饥荒预警系统(Famine EarlyWarning System,FEWS)。其每日全球潜在蒸散量是根据每6小时从全球资料同化系统提取的气候数据,使用Penman-Monteith方程计算得出，然后求和获得每日总计。该数据空间分辨率 $1 . 0 ^ { \circ } \times 1 . 0 ^ { \circ }$ ，时间分辨率1d。数据下载源 https://earlywarning.usgs.gov/fews/datadown-loads/Global/PET。

# 2.4CREST分布式水文模型

CREST（Coupled Routing and Excess Storage）模型由美国俄克拉荷马大学水文气象与遥感实验室（HyDROS)和美国宇航局（NASA）SERVIR项目团队联合开发。它是一个分布式水文模型，将全流域划分为若干网格，使用可变渗透能力曲线逐网格进行产流计算，并利用多线性水库逐网格计算地表和地下水汇流，最后通过耦合产流要素和汇流结构，模拟再现径流过程[40]。该模型在全球尺度，大区域尺度，以及中小尺度都有出色的水文模拟和预报能力[41-44]。CREST模型运行时,需要输入的数据包括数据流域信息（如流域边界，DEM,流向等），降水，潜在蒸散发，流域出口流量，初始条件以及模型参数。模型输出结果包括土壤含水量，土壤湿度，地面径流等。为节省篇幅，有关模型数据预处理，模型参数取值范围等详细信息请参考美国俄克拉荷马大学HyDROS 实验室CREST模型网址(http://hy-dro.ou.edu/research/crest/)。

# 2.5统计评估指标

本文选择了相对偏差(Bias），均方根误差（RMSE），平均绝对误差（MAE），相关系数（Correla-tionCoefficient,CC），4种统计验证指标用于定量评估多源降水产品的精度。采用标准差（StandardDe-viation, $S D$ ),纳什效率系数(NSCE)，相对偏差 $( B i a s )$ 和相关系数 $( C C )$ 评估各降水产品的水文模拟效用。

$$
B i a s = \left[ \frac { \displaystyle { \sum _ { i = 1 } ^ { n } S i m _ { i } - \sum _ { i = 1 } ^ { n } O b s _ { i } } } { \displaystyle { \sum _ { i = 1 } ^ { n } O b s _ { i } } } \right] \cdot 1 0 0
$$

$$
R M S E = { \sqrt { \frac { \displaystyle \sum _ { i = 1 } ^ { n } ( O b s _ { i } - S i m _ { i } ) ^ { 2 } } { n } } }
$$

$$
\ M A E = \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \left| { S i m } _ { i } - { O b s } _ { i } \right|
$$

$$
S D = \sqrt { \frac { \displaystyle \sum _ { i = 1 } ^ { n } ( S i m _ { i } - \overline { { S i m } } ) ^ { 2 } } { n - 1 } }
$$

$$
C C = \frac { \displaystyle \sum _ { i = 1 } ^ { n } ( O b s _ { i } - \overline { { O b s } } ) ( S i m _ { i } - \overline { { S i m } } ) } { \displaystyle \sqrt { \sum _ { i = 1 } ^ { n } ( O b s _ { i } - \overline { { O b s } } ) ^ { 2 } \sum _ { i = 1 } ^ { n } ( S i m _ { i } - \overline { { S i m } } ) ^ { 2 } } }
$$

$$
N S C E = 1 - \frac { \displaystyle \sum _ { i = 1 } ^ { n } ( O b s _ { i } - S i m _ { i } ) ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { n } ( O b s _ { i } - \overline { { O b s } } ) ^ { 2 } }
$$

式中： $\sin$ 代表多源降水估测数据或CREST模型模拟出的径流数据， $O b s$ 代表参考降水数据或径流站流量观测数据； $n$ 为模拟值或观测值总数， $i$ 为第 $i$ 个模拟值或观测值。当4个评估指标 $B i a s { = } 0 \%$ ，$R M S E { = } 0 , C C { = } 1 , N S C E { = } 1$ 代表最好的评估结果。为了细致地定量评估各降水产品的水文模拟效用，根据Moriasi等人的工作[45],将NSCE值分为4个区间，代表4个级别水文模拟效用：较差 $( N S C E { \leqslant } 0 . 5 )$ ，适用 $0 . 5 0 < N S C E { \leqslant } 0 . 6 5 ,$ ，良好（ $0 . 6 5 < N S C E { \leqslant } 0 . 7 5$ ，优秀 $( 0 . 7 5 < N S C E { \leqslant } 1 . 0 0 )$ 。

# 3结果与分析

# 3.1降水精度评估

由于降水产品的降水估算精度对其水文模拟效用有较大影响。因此，首先对各降水产品的降水精度做出评估。因为NOAA-CPC-US降水数据集汇集了上万个地面观测台站降水观测信息，然后在考虑地形效应后，对数据进行优化插值，并实施质量控制。所以，本文以2014年6月1日 $\sim 2 0 1 8$ 年6月30日的NOAA-CPC-US降水产品作为参照，对同时期的其它降水产品StageIV,PERSIANN,PERSI-ANN-CDR,TRMM-3B42V7,GPM-IMERG,ERA5进行降水精度评估。

3.1.1 栅格尺度降水精度在各个小流域，以 $1 \mathrm { k m } ^ { 2 }$ 栅格尺度，计算得到待评估降水产品同NOAA-CPC-US降水的相关系数(图1，图2)。在6种降水产品中,StageIV与NOAA-CPC-US数据的相关系数最高，平均值达到0.73，相关系数在不同地区的小流域的变化为 $0 . 6 5 \sim 0 . 8 1$ ;在West和Southwest地区相关系数较低。其次是PERSIANN-CDR和GPM-IMERG产品，与NOAA-CPC-US数据的相关系数分别为 $0 . 5 1 \sim 0 . 6 9 , 0 . 5 3 \sim 0 . 7 3$ 。这2种降水产品均在Northwest和West地区相关系数较小。再次是PER-SIANN和ERA5产品，与NOAA-CPC-US数据的相关系数分别为 $0 . 4 9 \sim 0 . 6 6 , 0 . 4 9 \sim 0 . 6 2$ 。其中PERSI-ANN产品在EastNorthCentral,WestNorthCentral以及Northwest地区的相关系数较低。ERA5属于气候模式的降水产品，在9个小流域的平均相关系数为0.55，相关系数最低的地区是West，Northeast和WestNorthCentral地区。与NOAA-CPC-US数据的相关系数最低的降水产品是TRMM-3B42V7，相关系数在 $0 . 4 4 \sim 0 . 5 9$ ,在9个小流域的平均相关系数只

1.0   
中 703000511 1710010104 －最小值 1801021102   
0.2 StageIV PERSIANN PERSIANN-CDR TRMM GPM ERA5

Fig.1Corelatoncoficientsetweenmulti-sourceprecipitationproductsndNOAA-CPC-USprecipitatioineachsmallwaterd

1.0   
866 师 二 1 中   
0.4 StageIV TRMM -Max PERSIANN GPM ·Mean PERSIANN-CDR ERA5 Min   
0.2 Central ENC NE NW SE SW South WNC West

Fig.Correlationcoeffcientsbetwnmulti-soureprecipitationproducts indifferentregionsandNOAA-CPC-USprecipitatior

# 干旱区地理

有0.52,尤其在Northeast,West North Central,EastNorthCentral和Northwest地区相关系数最低。以上6种降水产品与NOAA-CPC-US降水的相关系数均通过0.05置信水平检验。

从各降水产品在各研究区域相对于与NOAA-CPC-US降水的均方根误差和绝对误差(表2)，也反映出降水精度的差异。各降水产品在9个小流域的均方根误差，绝对误差的平均值，StageIV降水RMSE为 $5 . 7 8 ~ \mathrm { m m }$ ,MAE为 $2 . 1 5 ~ \mathrm { m m }$ ;PERSIANN-CDR降水的RMSE为 $6 . 5 2 \ \mathrm { m m }$ ,MAE为 $6 . 3 9 ~ \mathrm { m m }$ ; PERSIANN降水的RMSE为 $1 2 . 1 4 ~ \mathrm { m m }$ ,MAE为 $6 . 9 0 ~ \mathrm { m m }$ GPM-IMERG卫星降水的RMSE为 $2 3 . 2 7 \ : \mathrm { m m }$ ,MAE为6.44mm;ERA5降水的RMSE为 $5 3 . 0 2 ~ \mathrm { m m }$ ,MAE为6.84mm；TRMM-3B42V7卫星降水的RMSE为65.92$\mathrm { m m }$ ,MAE为 $7 . 0 6 \mathrm { m m }$ 。

综上统计指标分析，表明6种降水产品与NO-AA-CPC-US降水的相关性有差异，这种差异具有地区特点，显示出降水产品的空间变异性。降水产品在美国高纬度(偏北)和西部山地等区域估算精度略低。各降水产品与NOAA-CPC-US降水吻合程度从高到低，依次是StageIV雷达降水，PERSI-ANN-CDR和GPM-IMERG次之，再次是PERSIANN和ERA5，最后是TRMM-3B42V7。

3.1.2不同降水强度级别精度本文采用国际气象组织(WMO)降水强度级别分类标准[46],在不同降水强度等级上，更精细地分析了各降水产品的降水精度。降水强度按每小时降水量划分为6个等级，分别是(1）无雨：降水 $< 1 \mathrm { m m }$ ;(2）微雨： $1 \mathrm { m m } \leqslant$ 降水 $<$ $2 ~ \mathrm { m m }$ ；(3）小雨： $2 \ \mathrm { m m } \leqslant$ 降水 $< 5 ~ \mathrm { m m }$ ;(4）中雨：5$\mathrm { m m } { \leqslant }$ 降水 $< 1 0 \ \mathrm { m m }$ ，(5）大雨： $1 0 \ \mathrm { m m } \leqslant$ 降水 $< 2 0$ $\mathrm { m m }$ ，(6)暴雨： $2 0 \mathrm { m m } \leqslant$ 降水 $< 5 0 \mathrm { m m }$ ，（7）大暴雨：降水 ${ \geqslant } 5 0 ~ \mathrm { m m }$ 。统计分析各降水强度等级的发生频率(图3)和各降水产品在不同降水强度级别的频率误差(图4)。

相 对 NOAA-CPC-US 降水，StageIV,PERSI-ANN，PERSIANN-CDR，TRMM-3B42V7，GPM-IMERG，ERA5降水产品在不同地区9个小流域不同降水强度的发生频率并不相同，有不同程度上的高估和低估，误差均未超过 $\pm 1 0 \%$ 。总体上，多数降水产品在无雨和微雨级别存在低估，对大雨和暴雨存在高估。StageIV雷达降水在各降水强度等级的估测精度都高于PERSIANN，PERSIANN-CDR,TRMM-3B42V7,GPM-IMERG,ERA5降水。

# 3.2水文模拟效用评估

对降水精度评估之后，本文用上述7种降水产品分别驱动分布式水文模型CREST，模拟美国不同地区9个小流域的径流过程，评估各降水产品的水文模拟效用。径流模拟情景设定2002年1月1日～2003年12月31日为模型预热期，2004年1月1日\~2014年6月30日为模型率定期，2014年7月1日 $\sim$ 2018年6月30日为模型验证期。在相同的率定期内，分别使用7种降水产品率定CREST分布式水文模型参数，基于各自降水产品率定的参数集，然后在相同的验证期对径流进行模拟。采用NSCE,Bi-as,SD和CC统计指标，评估水文模拟效用。这种情景设置有利于独立评估各降水数据的流域水文过程模拟效果。

由图5，图6，图7分别说明各降水产品在美国

表2多源降水产品在各研究区域相对于与NOAA-CPC-US降水的误差 $/ \mathbf { m } \mathbf { m }$   
Tab.2Errors of multi-source precipitation products relative to NOAA-CPC-US precipitation in each small   

<html><body><table><tr><td rowspan="2">流域</td><td colspan="2">StageIV</td><td colspan="2">PERSIANN</td><td colspan="2">PERSIANN-CDR</td><td colspan="2">TRMM-3B42V7</td><td colspan="2">GPM-IMERG</td><td colspan="2">ERA5</td></tr><tr><td>RMSE</td><td>MAE</td><td>RMSE</td><td>MAE</td><td>RMSE</td><td>MAE</td><td>RMSE</td><td>MAE</td><td>RMSE</td><td>MAE</td><td>RMSE</td><td>MAE</td></tr><tr><td>HUC0107000107</td><td>5.63</td><td>1.89</td><td>10.22</td><td>6.95</td><td>5.82</td><td>6.36</td><td>69.06</td><td>7.56</td><td>27.22</td><td>6.42</td><td>58.37</td><td>7.32</td></tr><tr><td>HUC0312000306</td><td>5.02</td><td>1.62</td><td>9.56</td><td>6.59</td><td>5.51</td><td>6.44</td><td>64.77</td><td>6.89</td><td>15.19</td><td>6.13</td><td>51.01</td><td>6.75</td></tr><tr><td>HUC0602000211</td><td>4.97</td><td>1.66</td><td>10.02</td><td>6.55</td><td>5.43</td><td>6.41</td><td>65.11</td><td>6.64</td><td>22.01</td><td>6.52</td><td>47.11</td><td>6.59</td></tr><tr><td>HUC0703000511</td><td>5.29</td><td>2.26</td><td>18.23</td><td>7.46</td><td>6.27</td><td>6.05</td><td>68.66</td><td>7.35</td><td>27.04</td><td>6.64</td><td>50.78</td><td>6.89</td></tr><tr><td>HUC1012010909</td><td>4.99</td><td>2.03</td><td>19.68</td><td>7.61</td><td>6.54</td><td>6.37</td><td>72.61</td><td>7.49</td><td>26.85</td><td>6.49</td><td>60.26</td><td>7.06</td></tr><tr><td>HUC1113030208</td><td>5.96</td><td>1.86</td><td>7.36</td><td>6.16</td><td>6.19</td><td>5.89</td><td>65.56</td><td>6.42</td><td>18.72</td><td>5.64</td><td>46.27</td><td>6.27</td></tr><tr><td>HUC1506010304</td><td>6.58</td><td>2.34</td><td>8.36</td><td>6.14</td><td>7.29</td><td>6.02</td><td>58.26</td><td>6.51</td><td>20.23</td><td>6.47</td><td>49.06</td><td>6.83</td></tr><tr><td>HUC1710010104</td><td>6.91</td><td>3.21</td><td>9.12</td><td>7.04</td><td>7.59</td><td>7.02</td><td>63.89</td><td>7.63</td><td>24.36</td><td>6.89</td><td>57.31</td><td>7.11</td></tr><tr><td>HUC1801021102</td><td>6.71</td><td>2.46</td><td>16.73</td><td>6.98</td><td>8.03</td><td>6.96</td><td>65.39</td><td>7.01</td><td>27.83</td><td>6.74</td><td>57.02</td><td>7.03</td></tr><tr><td>均值</td><td>5.78</td><td>2.15</td><td>12.14</td><td>6.83</td><td>6.52</td><td>6.39</td><td>65.92</td><td>7.06</td><td>23.27</td><td>6.44</td><td>53.02</td><td>6.87</td></tr></table></body></html>

0000400 %/率 80760504030201 80650220  
0 1 o m 0  
公 2 5 10 2 50 -50 公 2 5 10 3.50 -50 公 2 50 2.5501 2 5 6 20 1 Y 2 5 0 20 1 1 2 5 6 2 1降水/mm 降水/mm 降水/mmHUC0107000107 HUC0312000306 HUC0602000211  
08700820 :PRS ARAUS 28888 :AAS 987600 :ASPERSIANN-CDR ·GPM PERSIANN-CDR ·GPM 3020 10 PERSIANN-CDR ·GPMm.. 1 广」  
公 2 3 S 050 公 A 公 2 05降水/mm 降水/mm 降水/mmHUC0703000511 HUC1012010909 HUC1113030208  
08076504030200 ·NOAA-CPC-US 90 ·NOAA-CPC-US 8 ·NOAA-CPC-US  
%/率颤 PERSIANN ·ERA5 %/率 7060 50 PERSIANN ·ERA5 500 PRSIANN ·ERA5·StrageIV 40 ·StrageIV ·StrageIV  
100 PPMSIANN-CDR 302010 GPMIANN DR 20100 PPMIN-DR  
公 2 5 10 2 50 .50 公 2 5 10 20 50 .50 公 2 5 10 20 50 501 2 5 R 20 W 人 2 5 0 2 7 人 2 5 0 20 7降水/mm 降水/mm 降水/mmHUC1506010304 HUC1710010104 HUC1801021102<1/mm <1/mm <1/mm≥50/mm 1\~2/mm ≥50/mm 1\~2/mm ≥50/mm 1\~2/mm20\~50/mm 20\~50/mm  
20\~50/mm 2\~5/mm 2\~5/mm 2\~5/mm+StrageIV +StrageIV +StrageIVPERSIANN PERSIANN PERSIANNPERSIANN-CDR PERSIANN-CDR PERSIANN-CDR10\~20/mm 5\~10/mm TRMM 10\~20/mm 5\~10/mm TRMM 10\~20/mm 5\~10/mm TRMM←ERA5 +ERA5 ←ERA5HUC0107000107 HUC0312000306 HUC0602000211<1/mm <1/mm <1/mm≥50/mm 1\~2/mm ≥50/mm 1\~2/mm ≥50/mm 1\~2/mm20\~50/mm  
20\~50/mm 2\~5/mm 20\~50/m 2\~5/mm 2\~5/mm10\~20/mm 5\~10/mm 5\~10/mm PERSAIN.CDR 10\~20/mm 5\~10/mm PESIANEOR←ERA5 GPM GPM←ERA5 ←ERA5HUC0703000511 HUC1012010909 HUC1113030208<1/mm <1/mm <1/mm≥50/mm 1\~2/mm ≥50/mm 1\~2/mm ≥50/mm 1\~2/mm  
20\~50/mm 2\~5/mm 20\~50/mm 2\~5/mm 20\~50/mm10\~20/mm 5\~10/mm 5\~10/mm N 5\~10/mmHUC1506010304 ←ERA5 HUC1710010104 GRA5 HUC1801021102 GRA5

Fig.4Frequencyerrorofmulti-sourceprecipitatioproductsrelativetoNOAA-CPC-USprecipitationineachprecipitationintesit

红色表示率定期 红色表示率定期 红色表示率定期Correla 色U 黑色表示验U00.10.20.30.4 StageIV StageIV40 0.50.6 ation coe 40 PERSIANN 00.10.2 0.30.4 Correla lation PERSIANN 20 00.10.20.3 0.40.5 Correlation PERSIANNffici 0.5  
uoiralpprlret 30 30 0.7 0.8 ient oiaeep 30 30 0.60.7 coefficient nonertlp 15 15 0.60.7 coeffic cient0.8 0.820 20 0.9 praprett 20 20 0.9 prrprett 10 10 0.90.95 0.95 0.9510 10 10 50.99 S 0.99 0.990 0 1 0 1 0 1Obs 10 20 30 40 Obs 10 20 30 40 Obs5 10 15 20HUC0107000107 HUC0312000306 HUC0602000211红色表示率定期 色表示定期 红色表示期20 00.10.20.30.4 Correla on EGDR 黑色表证期 15 00.10.20.30.4 C 全 orrela +NOAA-CPC-US StageIV PERSIANN PRMM-3N4-CDR 15 00.10.20.30 0.4 0.86 Cor rrela +NOAA-CPC-US PERSIANN PRMIA-NN-CDR  
uonarrepprapretn 15 15 coefficier uonrapprleet 10ent 10 1010 10 0.9 0.90.95 5 2 0.958 RM5 5/MSE品 0.99 0.99 9 0.9900 1 J1 0 0 1Obs5 10 15 20 Obs 5 10 15 Obs5 10 15HUC0703000511 HUC1012010909 HUC1113030208红色表示率定期 红色表示率定期 红色表示率定期1510 00.10.20.30.40 Correla 1on GPM-IMERG 00.10.20.3 5 6040 00.10.20.30.4 4 500.6 correla N  
uorralpprtrtts coeffiticje 器.95 50 30 .955 S 20?ISE0.99 0.99 0 0.990 0 11 0 1 0 1 8 1Obs5 10 15 Obs50 100 Obs20 40 60HUC1506010304 HUC1710010104 HUC1801021102

不同地区9个小流域日径流量率定和模拟的结果，包括相对于实测径流量的标准差 $\mathit { S D }$ ,均方根误差RMSE，相关系数 $C C$ ，纳什效率系数NSCE以及相对偏差Biaso

各降水产品在率定期径流模拟性能好于验证期，验证期的各个统计指标均有衰减。7种降水产品在美国不同地理分区小流域的径流模拟性能不一，因篇幅有限，此处仅以NSCE指标对各降水产品在美国不同地理分区小流域水文模拟的效果展开说明，其它指标请参见对应图表。根据Moriasi等人的工作[40]，将NSCE值分为4个区间，代表4个级别水文模拟效用：较差 $( N S C E { \lesssim } 0 . 5 )$ ），适用（ $0 . 5 0 <$ $N S C E { \ = } \approx . 6 5 ,$ ，良好 $( 0 . 6 5 < N S C E { \lesssim } 0 . 7 5$ ，优秀（ $\phantom { - } 0 . 7 5 <$ $N S C E {  } 1 . 0 0 \$ 。整理7种降水产品在9个小流域率定期和验证期的水文模拟效用级别如表3所示。

整体上，NOAA-CPC-US和StageIV降水是7种降水产品中水文模拟效果最好的2种。在美国不同地理分区的小流域保持了较好的径流模拟特性的，

![](images/93a4acecb5a98e6e30ef163288d7cee29bd654c8a6388ec61efb1fa13e8454a1.jpg)  
图6多源降水产品在美国不同地区9个小流域水文模拟的纳什效率系数

![](images/535953a3980c134928ded0acbd223a5653881db684c819f551dc067399575894.jpg)  
Fig.6Nash efficiency coeficient of hydrological simulation of multi-source precipitation products in nine small watersheds in different regions of the United States   
图7多源降水产品在美国不同地区9个小流域水文模拟的相对偏差 Fig.7Relative deviations of multi-source precipitation products in hydrological simulations of nine small watersheds in different regions of the United States

# 干旱区地理

表3多源降水产品在各小流域径流模拟效用级别  
Tab.3Performance of multi-source precipitation products in the simulation of runoff ineach small watershed   

<html><body><table><tr><td rowspan="2">流域</td><td colspan="2">NOAA-CPC-US</td><td colspan="2">StageIV</td><td colspan="2">PERSIANN</td><td colspan="2">PERSIANN-CDR</td><td colspan="2">TRMM-3B42V7</td><td colspan="2">GPM-IMERG</td><td colspan="2">ERA5</td></tr><tr><td>率定</td><td>验证</td><td>率定</td><td>验证</td><td>率定</td><td>验证</td><td>率定</td><td>验证</td><td>率定</td><td>验证</td><td>率定</td><td>验证</td><td>率定</td><td>验证</td></tr><tr><td>HUC0107000107</td><td>优秀</td><td>良好</td><td>优秀</td><td>良好</td><td>较差</td><td>较差</td><td>良好</td><td>适用</td><td>较差</td><td>较差</td><td>良好</td><td>较差</td><td>较差</td><td>较差</td></tr><tr><td>HUC0312000306</td><td>优秀</td><td>适用</td><td>优秀</td><td>优秀</td><td>适用</td><td>适用</td><td>良好</td><td>适用</td><td>较差</td><td>较差</td><td>优秀</td><td>优秀</td><td>较差</td><td>较差</td></tr><tr><td>HUC0602000211</td><td>优秀</td><td>良好</td><td>优秀</td><td>优秀</td><td>适用</td><td>较差</td><td>优秀</td><td>适用</td><td>适用</td><td>较差</td><td>优秀</td><td>良好</td><td>较差</td><td>较差</td></tr><tr><td>HUC0703000511</td><td>良好</td><td>适用</td><td>适用</td><td>适用</td><td>较差</td><td>较差</td><td>适用</td><td>适用</td><td>较差</td><td>较差</td><td>适用</td><td>适用</td><td>较差</td><td>较差</td></tr><tr><td>HUC1012010909</td><td>良好</td><td>适用</td><td>优秀</td><td>良好</td><td>较差</td><td>较差</td><td>适用</td><td>适用</td><td>较差</td><td>较差</td><td>适用</td><td>适用</td><td>较差</td><td>较差</td></tr><tr><td>HUC1113030208</td><td>优秀</td><td>优秀</td><td>优秀</td><td>优秀</td><td>良好</td><td>良好</td><td>优秀</td><td>优秀</td><td>适用</td><td>较差</td><td>优秀</td><td>优秀</td><td>适用</td><td>适用</td></tr><tr><td>HUC1506010304</td><td>优秀</td><td>优秀</td><td>优秀</td><td>优秀</td><td>适用</td><td>较差</td><td>优秀</td><td>良好</td><td>较差</td><td>较差</td><td>优秀</td><td>适用</td><td>适用</td><td>较差</td></tr><tr><td>HUC1710010104</td><td>良好</td><td>适用</td><td>优秀</td><td>良好</td><td>较差</td><td>较差</td><td>较差</td><td>较差</td><td>较差</td><td>较差</td><td>适用</td><td>较差</td><td>较差</td><td>较差</td></tr><tr><td>HUC1801021102</td><td>良好</td><td>适用</td><td>优秀</td><td>适用</td><td>适用</td><td>较差</td><td>较差</td><td>较差</td><td>较差</td><td>较差</td><td>适用</td><td>较差</td><td>较差</td><td>较差</td></tr></table></body></html>

NSCE级别多数达到了良好以上，能够重现流域行洪期间的日径流量过程;GPM-IMERG卫星降水和PERSIANN-CDR次之，在美国中低维度地区的小流域表现尚可，在北部，西部地区模拟效果较差。PERSIANN，ERA5降水的径流模拟能力不及NO-AA-CPC-US和StageIV降水，对洪峰流量的模拟效果则存在明显波动，不够准确，在美国中部，南部模拟性能较好，但在北部高纬度地区和美国西部，西南部地区较差。TRMM-3B42V7可能由于传感器精度和分辨率的缘故，在多个小流域的径流模拟不理想。

# 4结论

通过遥感技术获得降水估测数据，进而驱动水文模型，模拟和预测不同尺度的水文过程，是流域水文水资源研究的主要趋势。这类数据对洪涝，飓风,滑坡等自然灾害的预测预报极为重要。同大尺度流域相比，小流域是研究小微尺度水文、水资源、水环境的理想对象，也是探明小微水文水资源系统演变规律，寻找水资源可持续利用方法的重要手段。

（1）近年来，国内外学者基于遥感降水产品开展了诸多全球尺度，洲际尺度，大流域尺度的与水文水资源相关内容的研究。但是，遥感降水估测数据在小流域的研究和应用仍不充分。因此，本研究以NOAA-CPC-US降水作为参照，对比分析了StageIV，PERSIANN，PERSIANN-CDR，GPM-IMERG，ERA5,TRMM3B42V7降水的精度，并用这7种降水产品驱动CREST分布式水文模型，评估了它们在小流域水文模拟的可行性。

(2）从降水精度评估结果来看，各降水产品在美国北部高纬度和西部山地等区域估算精度略低，在中部，南部，东部保持较好的精度。各降水产品与NOAA-CPC-US降水吻合程度从高到低，依次是StageIV雷达降水,PERSIANN-CDR和GPM-IMERG次之，再次是PERSIANN和ERA5，最后是TRMM-3B42V7。从对不同降水强度的捕捉能力来看，PER-SIANN，PERSIANN-CDR,GPM-IMERG和TRMM-3B42V7卫星降水产品在无雨、微雨存在不同程度的低估，大雨和暴雨存在高估。

（3）在水文模拟效用评估中，总体上NOAA-CPC-US和StageIV雷达降水在各小流域水文模拟中效果较好，PERSIANN-CDR,GPM-IMERG,PER-SIANN，ERA5降水的径流模拟能力次之，TRMM-3B42V7模拟效果不理想。基于本文设置的水文模拟情景。

上述结论说明在美国NOAA-CPC-US降水和StageIV雷达降水基本能满足小流域水文模拟的需求；而使用PERSIANN，PERSIANN-CDR，GPM-IMERG，降水进行小流域水文模拟时需要审慎，尤其在在美国北部，西部地区；ERA5，TRMM-3B42V7降水数据尚不足以支撑小流域水文模拟，

# 参考文献(References)

[1]陈书军,刘毅,姜惠明,等.湖北省降雨和洪涝特征时空变化规 律分析[J].排灌机械工程学报,2019,37(3):248-250.[CHEN Shujun,LIU Yi,JIANG Huiming,et al. Analysis of precipitation and drought-flood spatio-temporal variation characteristics in Hu

bei Province[J]. Journal of Drainage and Irrigation Machinery Engineering,2019,37(3): 248-250.]   
[2]TAPIADOR F J, TURK FJ,PETERSEN W,et al. Global precipitationmeasurement: Methods,datasetsand applications[J].Ato spheric Research,2012,104: 70-97.   
[3]江善虎,任立良,雍斌,等.TRMM卫星降水数据在深水流域径 流模拟中的应用[J].水科学进展,2014,25(5):641-649.[JIANG Shanhu,REN Liliang,YONG Bin,et al.Hydrological evaluation of the TRMM multi-satelite precipitation estimates over the Mishui Basin[J].Advances in Water Science,2014,25(5): 641-649.]   
[4]唐国强,李哲,薛显武,等.赣江流域 TRMM 遥感降水对地面站 点观测的可替代性[J].水科学进展,2015,26(3):340-346. [TANG Guoqiang,LI zhe,XUE Xianwu,et al.A study of substitutability of TRMM remote sensing precipitation for gauge-based observation in Ganjiang River basin[J].Advances in Water Science, 2015,26(3): 340-346.]   
[5]IPCC. Climate change 20l3: the physical science basis: Working Group Icontribution to the Fifth assessment report of the Intergovernmental Panel on Climate Change[M].London: Cambridge University Press,2014.   
[6]陈晓晨,徐影,许崇海,等.CMIP5 全球气候模式对中国地区降 水模拟能力的评估[J].气候变化研究进展,2014,10(3):217- 225. [CHEN Xiaochen, XU Ying, XU Chonghai, et al. Assessment of precipitation simulations in China by CMIP5 multi-models [J]. Climate Change Research, 2014,10(3): 217-225.]   
[7]孙侦,贾绍凤,吕爱锋,等.IPCC AR5 全球气候模式模拟的中国 地区日平均降水精度评价[J].地球信息科学学报,2016,18(2): 227-237.[SUN Zhen,JIA Shaofeng,LV Aifeng,et al. Precision estimation of theaverage daily precipitation simulated by IPCC AR5 GCMs in China[J].Journalof Geo-informationScience,2016, 18(2): 227-237.]   
[8]颜楚睿,刘浏,黄冠华.多模式多情景下西北内陆干旱区未来气 候变化预估[J].排灌机械工程学报,2018,36(11):1193-1199. [YAN Churui,LIU Liu,HUANG Guanhua.Prediction of future climate change in northwest inland arid areas of China under multimode and multiple scenarios[J]. Journal of Drainage and Irrigation Machinery Engineering,2018,36(11): 1193-1199.]   
[9]HOU A Y, KAKAR R K, NEECK S,et al. The global precipitation measurement mission[J]. Bulletin of the American Meteorological Society,2014,95(5): 701-722.   
[10] 唐国强,万玮,曾子悦,等.全球降水测量(GPM)计划及其最新进 展综述[J].遥感技术与应用,2015,30(4):607-615.[TANG Guoqiang,WAN Wei, ZENG Ziyue,et al. An overview of the Ggobal precipitation measurement (GPM)mission and it's latest development[J].Remote Sensing Technology and Application,2O15,30(4): 607-615.]   
[11]唐国强,龙笛,万玮,等.全球水遥感技术及其应用研究的综述 与展望[J].中国科学：技术科学,2015,45(10):1013-1023. [TANG Guoqiang,LONG Di, WAN Wei, et al. An overview and outlook of global water remote sensing technology and applications [J]. Scienentia Sinica Technologica,2015,45(10): 1013-1023.]   
[12] MALDONADO M E S. Remote sensing based hydrologic modeling in the Babahoyo River Sub-basin for water balance assessment[M]. Enschede: University of Twente Faculty of Geo-Information and Earth Observation (ITC),2011.   
[13] ALBERGEL C, DUTRA E, MUNIER S,et al. ERA-5 and ERAInterim driven ISBA land surface model simulations:Which one performs bettr?[J]. Hydrology and Earth System Sciences, 2018, 22(6): 3515-3532.   
[14]KUMAR D,PANDEY A,SHARMA N, et al. Evaluation of TRMMprecipitation with rain-gauge observation using hydrological model J200[J].JournalofHydrologicEngineering，2015，22(5): E5015007.   
[15] 陈晓宏,钟睿达,王兆礼,等.新一代GPM IMERG 卫星遥感降 水数据在中国南方地区的精度及水文效用评估[J].水利学报, 2017,48(10): 1147-1156.[CHEN Xiaohong, ZHONG Ruida1, WANG Zhaoli,et al. Evaluation on the accuracy and hydrological performance of the latest- generation GPM IMERG product over South China[J]. Journal of Hydraulic Enginering,2017,48(10): 1147-1156.]   
[16]ZHAO Y,XIEQ,LU Y,et al.Hydrologic evaluation of TRMM multisatellite precipitation analysis for Nanliu River Basin in humid southwestern China[J]. Scientific Reports,2017,7(1): 2470.   
[17] NELSON B R,PRAT OP, SEO D J, et al. Assessment and implications of NCEP stage IV quantitative precipitation estimates for product intercomparisons [J]. Weather and Forecasting,2016,31 (2): 371-394.   
[18] TIAN X, ZOU X. Capturing size and intensity changes of hurricanes Irma and Maria (2O17) from polar-orbiting satelite microwave radiometers[J]. Journal of the Atmospheric Sciences,2018, 75(8): 2509-2522.   
[19]OMRANIAN E, SHARIF H, TAVAKOLY A. How well can global precipitation measurement (GPM) capture hurricanes? Case study: Hurricane Harvey[J]. Remote Sensing,2018,10(7): 1150.   
[20]PASKA J,LAU A MS,TAN ML,et al.Evaluation of TRMM 3B42V7 product on extreme precipitation measurements over peninsular Malaysia[C]/Remote Sensing for Agriculture, Ecosystems, and Hydrology XIX.International Society for Optics and Photonics,2017,10421: 104210D.   
[21]YANG Y,DU J, CHENG L, et al.Applicability of TRMM satellite precipitation in driving hydrological model for identifying flood events: A case study in the Xiangjiang River Basin,China[J].Natural Hazards,2017, 87(3): 1489-1505.   
[22]JIANG S,REN L, HONG Y,et al. Comprehensive evaluation of multi-satellte precipitation products with a denseain gaugenet work and optimally merging their simulated hydrological flows using the Bayesian model averaging method[J]. Journal of Hydrology, 2012,452: 213-225.

# 干旱区地理

[23] JIANG S,REN L, HONG Y,et al.Improvement of multi-satelite real-time precipitation products for ensemble streamflow simulation in a middle latitude basin in South China[J].Water resources management, 2014,28(8): 2259-2278.   
[24]MEI Y,ANAGNOSTOU E N,NIKOLOPOULOS E I,et al. Error analysis of satellite precipitation products in mountainous basins [J]. Journal of Hydrometeorology,2014,15(5): 1778-1793.   
[25] SARACHI S,HSU K, SOROOSHIAN S.A statistical model for the uncertainty analysis of satellite precipitation products[J]. Journal of Hydrometeorology,2015,16(5): 2101-2117.   
[26]HONG Y,HSU K, MORADKHANI H,et al. Uncertainty quantification of satellite precipitation estimation and Monte Carlo assess ment of the error propagation into hydrologic response[J]. Water resources research, 2006, 42(8).   
[27]RICO-RAMIREZ M A, LIGUORI S, SCHELLART A N A. Quantifying radar-rainfall uncertainty in urban drainage flow modeling [J]. Journal of Hydrology,2015,528: 17-28.   
[28]KRAJEWSKI W F, VILLARINI G,Smith JA. Radar-rainfall uncertainties: Where are we after thirty yearsof effort?[J].Buletin of the American Meteorological Society,2010,91(1): 87-94.   
[29]TRIPATHI MP,PANDA R K,RAGHUWANSHI N S,et al. Hydrological modelling of a small watershed using generated rainfall in the soil and water assessment tool model[J].Hydrological processes,2004,18(10): 1811-1821.   
[30]DU J, XIE S,XU Y,et al. Development and testing of a simple physically-based distributed rainfall-runoff model for storm runoff simulation in humid forestedbasins[J].Journalof Hydrology, 2007,336(3-4): 334-346.   
[31]LIU X,LI J.Application of SCS model in estimation of runoff from small watershed in Loess Plateau of China[J]. Chinese Geographical Science,2008,18(3): 235.   
[32]LEVESQUE E,ANCTIL F,VAN GRIENSVEN AN N,et al. Evaluation of streamflow simulation by SWAT model for two small watersheds under snowmelt and rainfall[J].Hydrological sciences journal,2008,53(5): 961-976.   
[33] QIU L, ZHENG F, YIN R.SWAT-based runoff and sediment simulation in a small watershed, the loessial hilly-gullied region of China: Capabilities and challenges[J]. International Journal of Sediment Research,2012,27(2): 226-234.   
[34]HU W,SHE D,SHAO M,etal.Effects of initial soil water content and saturated hydraulic conductivity variability on small watershed runoff simulation using LISEM[J]. Hydrological Sciences Journal,2015,60(6): 1137-1154.   
[35] MCMANAMAY R A, DEROLPH C R.A stream classification system for the conterminous United States[R].Scientific Data 2018.   
[36]LIN Y. GCIP/EOP Surface: precipitation NCEP/EMC 4 km gridded data(GRIB) Stage IV Data,Version 1.0,UCAR/NCAR - Earth Observing Laboratory[J].2017.   
[37]HUFFMAN G J. The transition in multi-satellite products from TRMM to GPM(TMPA to IMERG)[R].National Aeronautics and Space Administration. Mission update, 2015.   
[38]HUFFMANGJ,Bolvin D T,Nelkin EJ. Integrated Multi-satellitE Retrievals for GPM (IMERG) technical documentation[J]. NASA/ GSFC Code,2015,612(2015): 47.   
[39]US Geological Survey and US Department of Agriculture,Natural Resources Conservation Service. Federal Standards and Procedures for the National Watershed Boundary Dataset (WBD)[J]. Techniques and Methods,2013,11: 63.   
[40]WANG J, HONG Y,LI L, et al. The coupled routing and excess storage (CREST) distributed hydrological model[J].Hydrological Sciences Journal,2011,56(1): 84-98.   
[41]XUE X, HONG Y,LIMAYE A S,et al. Statistical and hydrological evaluation of TRMM-based multi-satelite precipitation analysis over the Wangchu Basin of Bhutan: Are the latest satellite precipitation products 3B42V7 ready for use in ungauged basins?[J]. Journal of Hydrology,2013,499: 91-99.   
[42]KHAN S I, HONG Y, WANG J, et al. Satellite remote sensing and hydrologic modeling for flood inundation mapping in Lake Victoria basin: Implications for hydrologic prediction in ungauged basins[J].IEEE Transactions on Geoscience and Remote Sensing, 2011,49(1): 85-95.   
[43]MENG J,LIL,HAO Z,etal. Suitabilityof TRMM satelite rainfll in driving a distributed hydrological model in the source region of Yellow River[J]. Journal of Hydrology,2014,509:320-332.   
[44]SHEN X,HONG Y,ZHANG K,et al. Refining a distributed linear reservoir routing method to improve performance of the CREST model[J]. Journal of Hydrologic Engineering,2016,22 (3): 04016061.   
[45]MORIASI D N,ARNOLD JG, VAN LIEW MW,et al. Model evaluation guidelines for systematic quantification of accuracy in watershed simulations[J]. Transactions of the ASABE,2007,50(3): 885- 900.   
[46] TAN M,IBRAHIM A, DUAN Z,et al. Evaluation of six high-resolution satelite and ground-based precipitation products over Malaysia[J]. Remote Sensing,2015,7(2): 1504-1528.

# Evaluating runoff simulation of multi-source precipitation data in small watersheds

FENG Ke-peng1,3,5， HONG Yang ²， TIAN Jun-cang1,3.5， TANG Guo-qiang4,KAN Guang-yuan4, LUO Xiang-yu²

(1SchoolofCivilndHydraulicEngineering,ingxiaUniversitycan,ngxia,ina;2hfil EngineeringandEnvironmentalScience,UniversityofOklahoma,Norman,OK32,USA；3NingxiaResearcheterof TechnologyonWatersvingrgaiondWatersourcesgulation,nhn1ngiain；4teKey LaboratoryofHydrosiencendEngineering,singhaUniversityeijingo84China；5EngineeringResearcheror EfficientUtilizationofWaterResourcesinodernAgricultureinAridegionsinchuan5o1,Ningxia,Cina)

Abstract:Small watershedsare ideal objects for studying the evolution of small and microscale hydrology and water resources systems.A small watershed is the smallst unit for calculating river water and sediment production and is the best regional scale for hydrologyand soil erosion research and management.Through RS technology,a climate model obtains precipitation estimation dataand drives a distributed hydrological model to simulate and predict hydrological processs，which clarifies the inevitable trends of basin hydrology and water resources research. Using NOAA-CPC-US precipitation data as a reference,an analysis of the PERSIANN,PERSIANNCDR,TRMM-3B42V7, GPM-IMERG, StageIV,and ERA5 precipitation data products were compared for nine small watersheds in diferent regions of the United States.Theaccuracy of theseseven precipitation products allowed hem to drive the CRESTdistributed hydrological model,which evaluated the hydrological simulation effects of the precipitation products.The study shows that the NOAA-CPC-US precipitation data product is the highest,folowed in decreasing order by StageIV,PERSIANN-CDR,GPM-IMERG,PERSIANN,ERA5,and TRMM3B42V7.The precipitation estimation accuracy of each precipitation product in the small watersheds in the high latitudesand western mountains of the northern United States is lower;however,there is beter precipitation accuracy insmall watersheds inthecentral,southern,andeastern partsof the United States.Inthe hydrological simulation utility evaluation,the CREST model parameters were determined using seven kinds of precipitation products,respectively.After obtaining the set of parameters,thedaily runoff processof the basin was simulated for the same verification period.The comparison results show that NOAA-CPC-US and StageIV have beter fcts on the hydrological simulationof small watersheds.However,caution should be exercised in hydrological simulations in the northern and western parts of the United States using PERSIANN,PERSIANN-CDR,GPM-IMERG,and ERA5 precipitation data,and the TRMM-3B42V7 simulation effect is not ideal.

Key Words: Small Watersheds; CREST; Multi-source precipitation; Hydrological Simulation