# 基于改进型TVDI在干旱区旱情监测中的应用研究

陈丙寅¹²，杨辽，陈曦¹,，王伟胜¹（1中国科学院新疆生态与地理研究所,新疆乌鲁木齐830011；2中国科学院大学,北京100049;3中国科学院中亚生态与环境研究中心,新疆乌鲁木齐830011)

摘要：干旱是全球范围内影响最为广泛的自然灾害之一，其所导致的土壤沙漠化、荒漠化和盐碱化给生态环境造成不可逆的危害。通过对 MODIS 数据进行投影转换、去云等预处理的基础上，利用地形校正对TVDI模型进行改进,构建了改进型的温度植被干旱指数(mTVDI)用于新疆干旱区旱情监测。利用土壤实测数据对 $m T V D I$ 及传统的TVDI模型进行对比验证。研究结果表明：（1）利用EVI与校正后的 $L S T$ 构建的 $m T V D I _ { E }$ 对干旱区旱情的敏感度最高，与实测土壤水分数据的相关性 $R ^ { 2 }$ 为0.74。（2）从空间上看，新疆2015年旱情分布以塔里木盆地和准噶尔盆地为两个干旱中心,旱情状况由严重逐步向周围山区递减至湿润状态。从时间上看，新疆6月、7月和8月旱情最为严重。（3）研究利用TRMM降水数据对基于 $m T V D I _ { E }$ 反演的新疆旱情时空分布特征进行对比分析，结果表明二者所表现出的旱情时空分布较为一致，不同时间段内的降水量与 $m T V D I _ { E }$ 之间具有一定的相关性，且均通过了 $P < 0 . 0 1$ 显著性检验。综上，基于TVDI所提出的 $m T V D I _ { E }$ 能够有效开展新疆干旱区旱情监测，且精度较高，从而为今后定量化开展大区域尺度旱情监测研究提供参考。

关键词：干旱区；旱情监测；TVDI；TRMM文章编号： $1 0 0 0 - 6 0 6 0 \lfloor 2 0 1 9 \rfloor 0 4 - 0 9 0 2 - 1 2 \lfloor 0 9 0 2 \sim 0 9 1 3 \rfloor$

干旱是全球范围内最常见、最复杂的自然灾害之一，具有影响范围大、持续时间长、破坏性大等特点，不仅造成巨大的经济社会损失，同时对生态环境产生重大威胁。近年来，受全球气候变化的影响，干旱区旱情状况更加复杂，因此定量化开展大区域尺度旱情监测研究对于把握全球干旱区气候变化规律、保障生态安全、预防旱灾的发生发展具有重要的现实意义[1-6]。传统旱情监测以现场监测方式为主，包括：探针测量、时域反射测量等诸多方法，但是这些方法消耗巨大的人力物力且效率低，尤其是山区和偏远地区采样困难，使得大范围监测难以实现遥感技术因其具有监测范围广、光谱特征丰富等优势,有效弥补了地面站点监测的不足，已成为目前旱情监测的重要手段[7-10]。当前以 TVDI(TemperatureVegetationDrynessIndex）为代表的植被指数遥感旱情监测方法，通过利用植被冠层温度和植被指数的变化特征，构造出地表温度一植被指数的特征空间，耦合温度植被干旱指数，能够对不同下垫面实现大范围长时序监测，已在旱情监测方面得到广泛应用[11-14]。SCHIRMBECK 等[15]比较了两种 TVDI模型用于巴西大豆种植区的旱情监测，结果表明基于作物参数化构建的TVDI模型能够确定作物旱情发生的时间和频率。ZHU Wenbin 等[16]提出了一种改进型TVDI，采用连续干旱监测的方法突破了传统依靠空间分辨率主导方法的限制。YANGRuowen等人对TVDI干边拟合方程进行改进，利用二次方程来表示干边拟合方程,对2010—2012年云南旱情状况进行监测[17]。国内众多学者利用TVDI模型对我国旱情状况也做了不少工作。刘艳伟等利用Land-sat数据构建了由归一化植被指数和地表温度数据建立的二维特征空间，拟合了干、湿边方程，进而计算了TVDI,对朝阳县旱情状况进行了分析和评价[18]。葛少青等利用三种干旱监测方法对干旱区沼泽湿地土壤水分进行监测，指出三种干旱指数与土壤实测数据之间存在明显的负相关关系[19]。然而这些工作都侧重于小区域短时效的研究，针对十旱区大区域尺度植被生长季旱情状况的研究较为少见。

鉴于此，本文以MODIS（ModerateResolutionIm-agingSpectroradiometer)光谱数据为数据源，对传统的TVDI旱情监测模型进行改进，将改进过后的温度植被干旱指数（modified TemperatureVegetationDryness Index, $m T V D I )$ 用于我国新疆干旱区植被生长季旱情监测研究，以期为今后进一步开展干旱区旱情监测提供新思路，

# 1研究区概况及数据源

# 1.1 研究区概况

新疆干旱区介于 $7 3 ^ { \circ } 2 0 ^ { \prime } \sim 9 6 ^ { \circ } 2 5 ^ { \circ } \mathrm { E }$ $3 4 ^ { \circ } 1 5 ^ { \prime } \sim$ $4 9 ^ { \circ } 1 0 ^ { \prime } \mathrm { N }$ 之间，深居亚欧大陆中心，温带大陆性气候。由于特殊的地理位置，主要依靠大西洋湿润气团带来降水，南疆年降雨量 $2 0 \sim 1 0 0 ~ \mathrm { m m }$ ,北疆年降雨量 $1 0 0 \sim 5 0 0 ~ \mathrm { m m }$ ,气温年、日较差大，光照充足，蒸发强烈，是全球典型的干旱半干旱气候区。新疆地形轮廓为“三山夹两盆”，北部阿尔泰山脉，南部昆仑山脉，天山山脉横贯中部，塔里木盆地和准格尔盆地夹在其中。全国第一第二大沙漠塔克拉玛干沙漠和古尔班通古特沙漠分布于此，自然环境复杂多样。根据新疆植被物候时空变化特征[20]及新疆2015 年植被生长实际情况，2015新疆植被生长季为 $4 \sim 1 0$ 月份即第97天～第305天。

# 1.2 数据源与预处理

1.2.1遥感数据遥感数据主要采用MODIS数据产品、SRTM高程数据以及TRMM降水数据。MO-DIS 数据产品具有覆盖范围广、时间分辨率高等特点，能够满足时序研究的需要。本文选取的MODIS数据产品包括16d合成植被指数（VegetationIndex，VI)产品MODIS13A2和8d合成地表温度（Land

Surface Temperature,LST）产品 MODIS11A2[21]。其中，MODIS13A2 包括 NDVI（Normalized DifferenceVegetation Index)和EVI(EnhancedVegetation Index)两种数据产品。MODIS11A2产品为8d合成产品,需要对其进行进一步处理,合成为16d产品，以确保与植被指数产品时序相一致。数字高程模型数据（DigitalElevationModel,DEM）选取SRTM（ShuttleRadarTopographyMission)高程数据，具有覆盖范围广、精度高、应用广泛等特点，经重采样后分辨率为$1 ~ \mathrm { k m } ^ { [ 2 2 ] }$ 。降水数据采用 TRMM（Tropical RainfallMeasuringMission）卫星数据TRMM3B43，是由TRMM3B42 数据、NOAA（National Oceanic and At-mosphericAdministration）气候预测中心气候异常系统的全球格点雨量测量器资料和全球降水气候中心的全球降水资料合成的全球网格降水数据，单位为整月平均每小时降水量( $\mathbf { \chi } _ { \mathrm { m m } } \cdot \mathbf { h } ^ { - 1 }$ ),空间分辨率为$0 . 2 5 ^ { \circ } \times 0 . 2 5 ^ { \circ }$ ,经重采样后分辨率为 $1 ~ \mathrm { k m } ^ { [ 2 3 ] }$ 。所需遥感数据详细信息如表1所示。

1.2.2实测数据实测土壤含水量数据来源于2015年6月野外实测采样工作，共计50个样点，采样点位置是根据新疆不同类型植被分布情况统计抽样确定，具体位置如图1。采样时间要求与卫星过境时间一致,天气要求晴朗且风力较小。采用土钻法采集 $0 \sim 1 0 ~ \mathrm { c m }$ 土层样本并取三次重复,用铝盒封装。将土壤样本带回实验室用烘十法烘十称重得到土壤含水量数据。具体公式如下：

$$
W = \frac { w _ { 1 } - w _ { 2 } } { w _ { 2 } } \times 1 0 0 \
$$

式中： $w$ 为土壤含水量 $( \% ) \ , w _ { 1 }$ 为湿土质量 $\mathbf { \Psi } ( \mathbf { \Psi } _ { \mathbf { g } } ) \mathbf { \Psi } , w _ { 2 }$ 为烘干后土的质量 $\mathbf { \tau } ( \mathbf { g } )$ 。

1.2.3数据预处理MODIS 数据产品需要利用MRT（MODISReproject Tool）工具对其进行几何校正、投影转换、格式转换、数据抽取等前期处理，再利用ArcGIS对研究区进行裁剪、波段运算合成等工作。SRTM数据需要利用ArcGIS进行裁剪、投影转换和重采样工作。TRMM数据需要进行裁剪、重采样和波段运算。

表1遥感数据详细参数信息  
Tab.1 Detailed parameter information of remote sensing data  

<html><body><table><tr><td>数据类型</td><td>数据名称</td><td>数据选取时间</td><td>时间分 辨率</td><td>空间分辨率</td><td>数据来源</td></tr><tr><td>地表温度数据</td><td>MODIS11A2</td><td>2015 年第97~305d</td><td>8d</td><td>1 km ×1km</td><td>美国国家航空航天局 htps://modis.gsfc.nasa.gov</td></tr><tr><td>植被指数数据</td><td>MODIS13A2</td><td>2015年第97~305d</td><td>16 d</td><td>1 km ×1km</td><td>美国国家航空航天局 https://modis.gsfc.nasa.gov</td></tr><tr><td>高程数据</td><td>SRTM</td><td></td><td></td><td>30 m×30m</td><td>美国太空总署、美国国防部国家测绘局、德国与意大 利航天机构htp://srtm.csi.cgiar.org</td></tr><tr><td>降水数据</td><td>TRMM3B43</td><td>2015 年第97~305d</td><td>1 h</td><td>0.25°×0.25°</td><td>美国气候预测中心https://mirador.gsfc.nasa.gov</td></tr></table></body></html>

![](images/4127a27a759bb527730c61f41edfe09aacd4a088e237c2d039b3b71e56e550aa.jpg)  
图1 研究区示意图  
Fig.1Sketch Map of Study Area

# 2 研究方法

# 2.1 植被指数

为精确反映植被信息，建立植被指数与温度之间的关系，本文选取归一化植被指数NDVI和增强型植被指数EVI用来表示植被生长状况信息。NDVI,即归一化植被指数，用以表现植物生长状态、植被空间分布密度及植被冠层的背景影响等，在利用遥感图像进行植被研究中得到广泛应用。 $E W I$ ,增强型植被指数，增加了冠层背景调整因子，使得EVI对大多数冠层背景不敏感，提高植被信息的反映精度。具体公式如下：

$$
N D V I = ( { \ \rho } 2 - \rho 1 ) / ( \rho 2 + \rho 1 )
$$

$$
E V I = G \big [ ( \rho 2 - \rho 1 ) / ( \rho 2 + C 1 \times \rho 1 - C 2 \times \rho 3 ) + L \big ]
$$

式中： $_ { | \rho 1 , \rho 2 , \rho 3 }$ 分别对应MODIS的第1波段( $6 2 0 \sim$ $6 7 0 \ \mathrm { n m }$ ），第2波段（ $\mathrm { 8 4 1 } \sim 8 7 6 \ \mathrm { n m }$ )和第3波段（ $4 5 9 \sim 4 7 9 ~ \mathrm { n m }$ )反射率。系数 $L$ 为冠层背景调整参数， $^ { C 1 , C 2 }$ 为气溶胶电阻项系数, $G$ 为增益因子[24]。

# 2.2 TVDI原理

土壤水分的多寡影响着地表温度的高低。当土壤水分充足，植被的蒸散作用增强，使得地表温度下降。相反，土壤水分较少时，植被蒸散作用降低，地表温度升高。土壤湿度状况与地表温度之间存在明显的负相关性。PRICE等[25]发现遥感影像所表现出的温度一植被指数特征空间的散点图为三角形。SANDBOIT等[1]对简化的 $T _ { \mathrm { s } } / N D V I$ 三角形空间进行了研究，提出表示土壤湿度的温度植被干旱指数TVDI的概念，定义为：

$$
T V D I = \frac { T _ { s } - T _ { s } ( V I ) _ { \mathrm { \scriptsize ~ m i n } } } { T _ { s } ( V I ) _ { \mathrm { \scriptsize ~ - ~ } } T _ { s } ( V I ) _ { \mathrm { \scriptsize ~ m i n } } }
$$

$$
\begin{array} { r } { T _ { s } ( \boldsymbol { V } ) _ { \mathrm { m a x } } = a _ { \mathrm { m a x } } + b _ { \mathrm { m a x } } \times \boldsymbol { V } I } \\ { \quad } \\ { T _ { s } ( \boldsymbol { V } ) _ { \mathrm { m i n } } = a _ { \mathrm { m i n } } + b _ { \mathrm { m i n } } \times \boldsymbol { V } I } \end{array}
$$

式中： $T _ { s }$ 代表任意一点像元的地表温度值， $T _ { s }$ $( W ) _ { \operatorname* { m a x } }$ 为干边拟合方程， $T _ { s } \left( \boldsymbol { W } \right) _ { \mathrm { m i n } }$ 为湿边拟合方程， $a _ { \mathrm { m a x } }$ 和 $b _ { \mathrm { m a x } }$ 为干边线性拟合参数， $a _ { \mathrm { m i n } }$ 和 $b _ { \mathrm { m i n } }$ 为湿边线性拟合参数。 $\boldsymbol { \mathit { W I } }$ 在本文中表示NDVI和 $E W _ { \circ }$

# 2.3 改进型TVDI的构建

2.3.1mTVDI模型构建过程TVDI作为一种水分胁迫指标,通过 $L S T$ 和 $\boldsymbol { \mathit { W } }$ 之间建立 $T _ { s } / W$ 特征空间来提取干湿边方程，进而评估研究区的旱情状况。对TVDI模型进行改进需要考虑数据本身以及研究区特有的地理环境。就数据源本身而言，遥感数据源会受到云的影响使得模型精度大大降低，因此需要去除云的干扰;其次新疆干旱区面积广大，地势起伏较大，地表温度数据与实际地表温度之间易产生偏差，也会降低模型精度。因此本文对TVDI模型的改进主要有两个方面：（1）对遥感影像进行去云处理。（2）对地表温度数据进行地形校正。改进后的TVDI模型即为 $m T V D I$ 。具体工作包括：（1）利用MOD13A2数据提取不同时相NDVI和 $E W I$ ,将相同时相的 $L S T$ 数据和 $N D V I , E V I$ 数据按照时序一一对应。（2）对遥感影像进行去云处理。（3）对 $L S T$ 数据进行地形校正。（4）计算 $T _ { s }$ 及校正后 $T _ { s }$ 与 $\boldsymbol { { W } }$ 的特征空间并提取干湿边方程。（5）利用不同干湿边方程分别计算 ${ \mathit { T V D I } } _ { \mathit { N } }$ ， $T V D I _ { E }$ ， $m T V D I _ { N }$ ， $m T V D I _ { E }$ 具体构建流程如图2。

2.3.2去云处理由于气候、天气的原因，大部分影像在获取时或多或少都会受到云的影响，尤其是大范围、长时序光谱数据。云的存在使得遥感影像在某些区域存在数据缺失，大气背景条件存在明显差异，同时，也会影响到地表温度的反演精度。为了保证TVDI模型反演精度，需要对影像进行去云处理。现有的处理方式有两种：一种是将受云覆盖的区域进行数据恢复，消除云的影响；另一种是检测云的存在，利用掩膜进行去除，不参与模型计算。为了保证反演精度，本文将有云的区域进行掩膜计算，去除云对TVDI模型精度的影响。

![](images/f0d71f96e31e16197bc1530610d5f91f0d0c9a7798b6f129e454740e1ae81b85.jpg)  
图2mTVDI模型构建 Fig.2mTVDI model construction

2.3.3地形校正利用TVDI模型进行旱情监测，除了受到地表温度、植被覆盖度的影响外，还受到地表起伏状况、土壤质地及其所造成的大气辐射不均衡等多方面的影响。因此本文利用数字高程数据对地表温度进行校正，以消除地形对大区域太阳辐射差异的影响。公式如下：

$$
T _ { 2 } = T _ { 1 } + m \times H
$$

式中： $T _ { 2 }$ 代表校正后的地表温度， $T _ { 1 }$ 代表原始地表温度， $H$ 为高程值， $m$ 为高程修正系数。

2.3.4干湿边提取干湿边的提取是模型构建的重要内容。干湿边提取即利用植被指数数据与最大最小地表温度数据进行线性拟合，获取干湿边方程。本文提取干湿边的方法： $\boldsymbol { W }$ 值范围： $0 \sim 1$ ，以 $0 . 0 1 +$ $0 . 0 2 n ( n = 1 , 2 , \cdots , 9 9 )$ 为中心,将相同 $\boldsymbol { { W } }$ 与所对应的改进后的 $T _ { \mathrm { s } }$ 的最大值和最小值对应，最后采用最小二乘法拟合干边和湿边。利用R语言编程，自动提取干湿边。植被生长季(第 $9 7 \sim 3 0 5 \mathrm { ~ d } _ { , }$ )干湿边方程的结果如表2所示。

由表2可以看出，改进 $T _ { s } / W$ 干湿边方程拟合效果总体优于原始 $T _ { s } / W$ 干湿边方程拟合效果。$T _ { s } / E V I$ 和改进 $T _ { s } / E V I$ 拟合效果优于 $T _ { s } / N D V I$ 和改进 $T _ { s } / N D V I$ 拟合效果。改进 $T _ { s } / E V I$ 干边拟合方程$\textstyle R ^ { 2 }$ 在0.8以上,湿边拟合方程 $R ^ { 2 }$ 在0.5以上，拟合效果最好，表现出了一定的优势。

# 3结果与分析

# 3.1 模型计算与分析

3.1.1TVDI计算结果对比分析TVDI的取值范围为0\~1,当 $T V D I$ 趋于1时颜色越深,表示旱情愈加严重，当TVDI趋于0时颜色越浅，表示该地较为湿润。图3利用 $T V D I _ { \scriptscriptstyle N } , T V D I _ { \scriptscriptstyle E } , m T V D I _ { \scriptscriptstyle N } , m T V D I _ { \scriptscriptstyle E }$ 四种模型计算出的2015年第177d研究区旱情空间分布情况。据图可以看出，研究区TVDI值较大区域主要集中在盆地地区，盆地地形使得大气不易散热、蒸发旺盛、且植被丰富，水分需求量巨大，因此干旱程度较为严重。TVDI值较小的区域主要分布在阿尔泰山脉、天山山脉和昆仑山脉及其周围。这是由于这些区域在这个时期冰雪融水补给较为充足，所以表现出湿润的状态。四种模型均表现出了一致的旱情分布特征。

3.1.2 TVDI与土壤湿度相关性比较利用 $T V _ { \overline { { \mathbf { \Gamma } } } }$ （204号$D I _ { \scriptscriptstyle { N } } , T V D I _ { \scriptscriptstyle { E } } , m T V D I _ { \scriptscriptstyle { N } } , m T V D I _ { \scriptscriptstyle { E } }$ 模型计算结果与6月份土壤实测数据进行相关性分析。由图4可以看出， $m T V D I _ { E }$ 与实测数据相关性最高， $R ^ { 2 } = 0 . 7 4$ 。相比其它模型表现出了一定的优越性。因此本文选取$m T V D I _ { E }$ 作为研究区旱情监测模型,对2015年干旱区植被生长季旱情进行监测。

# 3.2 $\mathbf { \Omega } _ { m T V D I _ { E } }$ 时空分布

图5为2015年新疆植被生长季 $m T V D I _ { E }$ 旱情监测结果。从空间上看：(1)旱情最严重的地方主要分布在吐鲁番盆地及哈密盆地西部。在整个生长季当中，吐鲁番盆地及哈密盆地西部都处于极度干旱状态。主要原因是该地区海拔较低,盆地地形使得热气流无法向外扩散，蒸发强烈，旱情最为严重。(2)旱情较为严重的地区分布在塔里木盆地，该地区沙漠广布，地表蒸发旺盛，且四周有山脉阻挡，水汽难以到达形成降水，致使该地旱情较为严重。(3)旱情较为严重的另一地区为准噶尔盆地，但其旱情状况波动较大。在第129d,161d和177d旱情较为严重，而其他时间旱情有所缓解甚至表现出正常的状态。这是由于该地区为新疆重要的农业种植区，人为灌溉活动较为频繁，使得该区域旱情状况不稳定。（4)旱情不明显的区域即正常状态下的区域主要分布在天山山脉、阿尔泰山山脉和昆仑山脉附近，这些地方在植被生长季时期既有雨水补给又有高山冰雪融水补给，因此并不会出现明显的干旱状况。（5)旱情不明显的区域还有塔里木河周围，在植被生长季时期，河流对周围农田和树林等绿洲区起到了补给灌溉的作用。（6)较为湿润的区域分布在天山山脉、阿尔泰山山脉和昆仑山脉。由于植被生长季阶段温度较高，冰雪融水丰富，因此表现出较为湿润的状态。

从时间分布上看：（1）第161，177，193,209，225，241天旱情较为严重，这是由于2015年伊朗副高正在新疆上空稳定停留且不断增强所致。（2)其他时间段新疆整体相对湿润。由于处于换季时期，研究区整体降水增多， $m T V D I _ { E }$ 值较小,全疆旱情有所减缓。

# 3.3TRMM降水数据与 $\mathbf { \nabla } _ { m T V D I } _ { E }$ 相关性分析

图6利用每月平均每小时降水数据乘以24解算得到平均每月每天降水量数据。根据各月平均每天降水分布来看：6，7，8月降水分布区域较小，9，10月份降水量分布区域较大。与 $m T V D I _ { E }$ 时空分布图相比较可以看出：（1）6，7，8月份全疆降水偏少，对应的 $m T V D I _ { E }$ 值也偏高，全疆呈现出严重干旱态势（2）9,10月份全疆降水偏多，对应的 $m T V D I _ { E }$ 值偏低，全疆旱情有所缓解。

为进一步探究新疆旱情与降水的关系，本文对4\~10月 $m T V D I _ { E }$ 结果与降水数据进行相关性分析。结果如图7：4月 $R ^ { 2 } = 0 . 4 4 9 \ 4 , 5$ 月 $R ^ { 2 } = 0 . 4 1 5 \ 9 , 6$ 月 $R ^ { 2 } = 0 . 4 0 9 6 { , } 7$ 月 $R ^ { 2 } = 0 . 4 3 1 4 { , } 8$ 月 $R ^ { 2 } = 0 . 4 3 , 9$ 月 $R ^ { 2 } = 0 . \ 4 4 4 \ 2 , 1 0$ 月 $R ^ { 2 } = 0 . { \ 4 6 1 \ 3 }$ 。由此可以看出，生长季各月TVDI与降水之间存在负相关关系，其结果均通过了 $P < 0 . 0 1$ 显著性检验。综上，新疆旱情与降水表现出一定的相关性，降水的多少影响着新疆植被生长季旱情的广度及严重程度。

# 4结论

为了提高TVDI模型对植被生长季旱情监测的敏感性，提高TVDI模型旱情监测精度，本文利用植被指数与改进后的地表温度数据构建了改进型的旱情监测模型 $m T V D I$ ,对比分析 $T V D I _ { N } , T V D I _ { E } , m T V -$ $D I _ { \scriptscriptstyle { N } } , m T V D I _ { \scriptscriptstyle { E } }$ 四个模型指示旱情的优劣，选取最佳模型对2015年新疆干旱区植被生长季旱情进行时空分析并利用TRMM降水数据对其进行验证。得到

表2干湿边方程拟合方程  
Tab.2Dry and wet edge fitting equation   

<html><body><table><tr><td>原始Ts/NDVI</td><td>干边方程</td><td>R²</td><td>湿边方程</td><td>R</td></tr><tr><td>第97天</td><td>y = -102.389x +322.43</td><td>0.813 7</td><td>y =54.989x + 223.620 5</td><td>0.463 8</td></tr><tr><td>第116天</td><td>y= -72.316x +332.909</td><td>0.894 7</td><td>y = 70.537 2x + 225.267 3</td><td>0. 633 9</td></tr><tr><td>第129天</td><td>y= - 64.800 1x +337.700 2</td><td>0.923 8</td><td>y=68.915 2x+225.878 4</td><td>0.813 4</td></tr><tr><td>第145天</td><td>y = -62.147 8x +338.749 4</td><td>0.907 8</td><td>y=62.822 1x +220.172 2</td><td>0.863 6</td></tr><tr><td>第161天</td><td>y = -61.905x +344.246 3</td><td>0.854 2</td><td>y = 51.684 6x +225.582 4</td><td>0.808 5</td></tr><tr><td>第177天</td><td>y = -49.183x +339.811</td><td>0.863 1</td><td>y = 51.178 6x +229.148 4</td><td>0.868 7</td></tr><tr><td>第193天</td><td>y = -51.961 7x +342.553 4</td><td>0.846 3</td><td>y =40. 735 7x + 240.95</td><td>0. 675 3</td></tr><tr><td>第209天</td><td>y = -49.987 9x +345.148 3</td><td>0.960 6</td><td>y = 59.178 6x +234.631 1</td><td>0.855</td></tr><tr><td>第225天</td><td>y = -40.713 8x +336.680 8</td><td>0.961 5</td><td>y = 73.300 5x + 230.373</td><td>0.849 3</td></tr><tr><td>第241天</td><td>y = -38.135 5x +330.078 9</td><td>0.931 1</td><td>y = 85.971x + 227.824 8</td><td>0.776</td></tr><tr><td>第257天</td><td>y = -51.897 2x +328.308 3</td><td>0. 758 5</td><td>y = 75.330 9x +230.586</td><td>0.554 8</td></tr><tr><td>第273天</td><td>y = -52.392 6x +320.093 6</td><td>0.801 8</td><td>y=72.284 9x +233.311 1</td><td>0.883 6</td></tr><tr><td>第289天</td><td>y = -55.619 6x +311.206 2</td><td>0.761 9</td><td>y = 29.586 4x +241.466</td><td>0.470 9</td></tr><tr><td>第305天</td><td>y = -90.498 6x +308.063 7</td><td>0.857 9</td><td>y =41.236 4x +234.459 2</td><td>0.577 2</td></tr><tr><td>第97天</td><td>y = -67.532 7x +322.143 6</td><td>0.845 4</td><td>y=31.684x+230.736 4</td><td>0.501 9</td></tr><tr><td>第116天</td><td>y = -51.926 1x +332.059 9</td><td>0.902 1</td><td>y =51.342x +231.032 9</td><td>0. 749 5</td></tr></table></body></html>

(续表)   

<html><body><table><tr><td>原始Ts/EVI</td><td>干边方程</td><td>R²</td><td>湿边方程</td><td>R²</td></tr><tr><td>第129天</td><td>y = -49. 945 4x +337. 841 7</td><td>0.898 7</td><td>y =43.921x + 233.230 6</td><td>0. 737 1</td></tr><tr><td>第145天</td><td>y = -48.998x +338.821 7</td><td>0.889</td><td>y =51. 904x + 226.430 2</td><td>0.895</td></tr><tr><td>第161天</td><td>y = -48. 621 4x +343. 684 8</td><td>0.835 9</td><td>y =44.334x + 229.115 8</td><td>0.818 2</td></tr><tr><td>第177天</td><td>y = -44.289 7x +341.072 7</td><td>0. 877 1</td><td>y = 42.477 3x +230.954 4</td><td>0.842 3</td></tr><tr><td>第193天</td><td>y = -49.176 4x +344. 857 5</td><td>0.807 2</td><td>y =31. 538 2x + 240.222 2</td><td>0. 533 4</td></tr><tr><td>第209天</td><td>y = -46.452 5x +347.528 5</td><td>0.909 2</td><td>y =45. 192x + 234. 918 8</td><td>0. 795 4</td></tr><tr><td>第225天</td><td>y = -43.085 8x +340.691 9</td><td>0. 823 6</td><td>y = 46.081 1x + 234.484 8</td><td>0.898 8</td></tr><tr><td>第241天</td><td>y = -42.144 1x + 334.251 2</td><td>0. 795 8</td><td>y = 43. 795 4x + 234. 134 4</td><td>0. 734 1</td></tr><tr><td>第257天</td><td>y = -48. 654 4 + 331. 199 1</td><td>0. 802 6</td><td>y =39.712 3x +235.501 9</td><td>0.743 9</td></tr><tr><td>第273天</td><td>y = -40.861 3x + 320.981 1</td><td>0. 869</td><td>y =32. 771 2x + 236.918 3</td><td>0.714 2</td></tr><tr><td>第289天</td><td>y = - 45.007 1x +315.936 8</td><td>0.862</td><td>y = 25. 699 7x + 237. 21</td><td>0.582 2</td></tr><tr><td>第305天</td><td>y = -40.190 9x +303.949</td><td>0.864</td><td>y =23.866 2x + 235.035 7</td><td>0.541 6</td></tr><tr><td>改进Ts/NDVI</td><td>干边方程</td><td>R</td><td>湿边方程</td><td>R</td></tr><tr><td>第97天</td><td>y = -68.395 2x +318.961 5</td><td>0.837 4</td><td>y =27. 023x + 259.405 5</td><td>0.543 4</td></tr><tr><td>第116天</td><td>y = -63.326 3x +331.267 1</td><td>0.880 4</td><td>y =21.723 8x +264.795 3</td><td>0.404 9</td></tr><tr><td>第129天</td><td>y = -48.732 1x + 333. 657</td><td>0.954 5</td><td>y = 36. 784 3x + 262.161 6</td><td>0.855 8</td></tr><tr><td>第145天</td><td>y = -51.031 2x +336.224</td><td>0.951 2</td><td>y = 30.026 8x +260.674 7</td><td>0.831 7</td></tr><tr><td>第161天</td><td>y = -47.429 8x +340.361 5</td><td>0.891 7</td><td>y =25.780 8x + 264.100 9</td><td>0. 779 3</td></tr><tr><td>第177天</td><td>y = - 39.578 2x +337. 462 1</td><td>0. 927 1</td><td>y = 28. 548 1x +265.721 7</td><td>0. 883 7</td></tr><tr><td>第193天</td><td>y = -42.392 2x + 339.938</td><td>0.932</td><td>y = 20. 184 1x +275. 549 8</td><td>0. 609 4</td></tr><tr><td>第209天</td><td>y = -45.355 6x +344. 354 5</td><td>0. 946 4</td><td>y = 30. 756 6x + 270. 765 9</td><td>0.789 6</td></tr><tr><td>第225天</td><td>y = - 35.881 6x +335.860 4</td><td>0.951 9</td><td>y =41.071 2x + 267.526 5</td><td>0.863 6</td></tr><tr><td>第241天</td><td>y = -32.271 8x +329.047 1</td><td>0. 928 8</td><td>y =42. 672 8x + 267. 673 7</td><td>0. 733 1</td></tr><tr><td>第257天</td><td>y = -38.248 4x +325.321 8</td><td>0. 851</td><td>y =37.585 5x +267. 561 4</td><td>0.531 5</td></tr><tr><td>第273天</td><td>y = -47.003 8x + 319.31</td><td>0. 903 1</td><td>y = 38. 444x + 260. 642 9</td><td>0. 865 5</td></tr><tr><td>第289天</td><td>y = -37.150 9x +310.513 7</td><td>0.851 9</td><td>y = 12. 360 1x + 271. 839 6</td><td>0.434 1</td></tr><tr><td>第305天</td><td>y = -52.514 7x +306.694 3</td><td>0.89</td><td>y =33.452 1x + 259.4716</td><td>0. 799 1</td></tr><tr><td>改进Ts/EVI</td><td>干边方程</td><td>R</td><td>湿边方程</td><td>R</td></tr><tr><td>第97天</td><td>y = -45.028 6x +318.463 1</td><td>0.862 9</td><td>y = 16.761 4x + 261. 889</td><td>0. 676 4</td></tr><tr><td>第116天</td><td>y = -42.915 5x +329.723 1</td><td>0.940 9</td><td>y = 16.843 1x + 265.364 3</td><td>0.586 3</td></tr><tr><td>第129天</td><td>y = -42.304 3x +335.525</td><td>0. 885 4</td><td>y =14.537 8x +267.895 5</td><td>0. 658 5</td></tr><tr><td>第145天</td><td>y = -42.798 8x +337. 232 1</td><td>0.908 1</td><td>y = 22. 244 9x + 263.886 6</td><td>0. 853 5</td></tr><tr><td>第161天</td><td>y = -40.736 8x + 341.42</td><td>0. 852 6</td><td>y =21. 567x + 265.940 4</td><td>0. 852 6</td></tr><tr><td>第177天</td><td>y= - 38.307 2x +339.618 2</td><td>0.906 7</td><td>y =21.667x + 267.122 8</td><td>0.860 2</td></tr><tr><td>第193天</td><td>y = -41.691 9x + 342.495 1</td><td>0.878 2</td><td>y =15.127x + 275.271 8</td><td>0.578 4</td></tr><tr><td>第209天</td><td>y = -42.335 3x +346.511 8</td><td>0. 895 7</td><td>y = 26.109 9x + 269.747 7</td><td>0.833 6</td></tr><tr><td>第225天</td><td>y = - 37.106 6x + 338.991</td><td>0.862</td><td>y = 25.366 4x + 269. 655 3</td><td>0.880 9</td></tr><tr><td>第241天</td><td>y = -36.148 8x +332. 78 5</td><td>0. 836 9</td><td>y =19.820 3x + 271.411 3</td><td>0. 709 4</td></tr><tr><td>第257天</td><td>y = -37.859 4x +328.175 5</td><td>0.901 5</td><td>y =17.960 1x + 270.775 2</td><td>0. 643 8</td></tr><tr><td>第273天</td><td>y = - 34.499 9x +319.424 1</td><td>0.930 9</td><td>y = 22.418 6x +260.981 6</td><td>0.857 9</td></tr><tr><td>第289天</td><td>y = - 33.404 9x +314.214 9</td><td>0.966</td><td>y =12.524 1x + 269.129 6</td><td>0. 642 4</td></tr><tr><td>第305天</td><td>y = -28.788 4x +304.9766</td><td>0.9409</td><td>y = 18.467 7x +259.854</td><td>0. 877 4</td></tr></table></body></html>

![](images/2116fc7f3e42c7cb00f3a711362858491eec45266d51311e807d09cddc2bb77d.jpg)  
图3第177天研究区TVDI模型计算结果

![](images/840406b9b598a80600dd8153a8da2acd93902a7fd9f0cf151b11e27a4928a02f.jpg)  
Fig.3Results of TVDI calculations in the study area on the $1 7 7 ^ { \mathrm { t h } }$ day   
图4TVDI与实测土壤水分相关性比较  
Fig.4Correlation between the TVDI and measured soil moisture

![](images/af7ef3c7fb3047af26ee906168599e5fb02ed78c2c37638190dde07a5838320d.jpg)  
图5研究区2015年植被生长季 $m T V D I _ { E }$ 时空分布

Fig.5Temporal and spatial distribution of $m T V D I _ { E }$ in the growing season of 2O15 in the study area以下结论：（1）经过地形校正后的 $m T V D I _ { E }$ 对干旱区旱情监测效果最好，与土壤实测数据相关性最高，$R ^ { 2 } = 0 . 7 4$ 。（2）新疆2015 年旱情分布以塔里木盆地和准噶尔盆地为两个干旱中心，旱情状况由严重逐步向周围山区递减至湿润状态。（3）从时间上看，6，7，8月份全疆旱情较为严重，所受干旱影响面积较大。（4）降水与新疆旱情具有一定的相关性，6,7，8月份全疆降水偏少，9，10月份全疆降水偏多，与对应的 $m T V D I _ { E }$ 结果表现出一致的变化特征，由此可见降水多寡影响着新疆干旱区旱情状况。（5)$m T V D I _ { E }$ 与TRMM具有一定的相关性， $m T V D I _ { E }$ 对研究区旱情状况具有一定的指示作用。

![](images/5fd49860774a615440bb5408b406bebdae0763f3725196d22a7b1cda68b878f2.jpg)  
图6研究区2015年4\~10各月平均每天TRMM降水分布图

![](images/c5bf7ad751a41f510335f7ff2a5a5e40eb629ed7b4004a22dd5bad12048f5ed4.jpg)  
Fig.6DistributionofaveragedailyTRMMprecipitation in the study area from April to October in 2015

![](images/c27bb00407cc193fbe6a9289a52981280524b3608151161d38e49928919b30bf.jpg)

综上,基于增强型植被指数与经过地形校正后的地表温度数据所构建的 $m T V D I _ { _ E }$ 模型能够满足干旱区植被生长季旱情监测的目的。 $m T V D I _ { E }$ 模型所表现出的旱情状况与土壤水分之间显示出较强的相关性，对全球干旱区旱情研究具有很强的参考意义。

# 5讨论

$m T V D I _ { E }$ 模型能够方便高效的反映大区域旱情状况，但还存在以下不足之处，主要表现在：(1)遥感影像质量依然是影响TVDI模型精度的重要因素。（2）新疆地区面积广大，土壤质地、土地利用类型的不同所表现出的旱情状况也不尽相同。因此接下来的工作将从以上两个方面进行研究。

# 参考文献(References)

[1] ZORMAND S,JAFARIR,KOUPAEI S S.Assessment of PDI,MP

DI and TVDI drought indices derived from MODIS Aqua/Terra Level1B data in natural lands[J].Natural Hazards,2O17，86 (2):757 -77   
[2]XU Yaping,WANG Lei,ROSS KEMTON W,et al. Standardized soil moisture index for drought monitoring based on soil moisture active passive observations and 36 years of north american land data assimilation system data:A case study in the southeast United States[J]. Remote Sensing,2018,10(2）:301.   
[3］高涛涛,殷淑燕,王水霞.基于 SPEI指数的秦岭南北地区干旱 时空变化特征[J].干旱区地理,2018,41(4）：761-770.[GAO Taotao,YIN Shuyan,WANG Shuixia.Temporal and spatial variation characteristicsof drought in North and South Qinling Mountains based on SPEI index[J].Arid Land Geography,2018, 41(4) :761 -770.]   
[4］薛海丽,张钦,唐海萍.近60 a内蒙古不同草原类型区极端气 候和干旱时间特征分析[J].干旱区地理,2018,41（4)：701- 711.[XUE Haili,ZHANG Qin,TANG Haiping. Extreme temperature and drought events in four diferent grassland areas of Inner Mongolia in recent 6O years[J].Arid Land Geography,2018,41 (4) :701 -711]   
[5]REZZA S,ISLAM N,RAHMAN M M. Meteorlogical drought monitoring using satellite imagery:A case study on Rajshahi,Naogaon and Jaipurhat of Bangladesh[C].National Conference on Water Resources Engineering,2018.   
[6］王俊霞,朱秀芳,刘宪锋,等.基于多源数据的河南省农业干旱 监测方法研究[J].国土资源遥感,2018,30（1)：180－186. [WANG Junxia,ZHU Xiufang,LIU Xianfeng,et al. Research on agriculture drought monitoring method of Henan Province with multi-sources data[J]. Remote Sensing for Land& Resources, 2018,30(1) :180 -186.]   
[7］蒋慧敏,刘春云,贾健,等.乌鲁木齐地区夏季气象干旱的变化 特征及成因分析[J].干旱区地理,2018,41（4）:693－700 [JIANG Huimin,LIU Chunyun,JIA Jian,et al.Characteristics and causes of meteorological drought in summer in Urumqi[J].Arid Land Geography,2018,41（4） :693- 700]   
[8］谢培,顾艳玲,张玉虎,等.1961—2015 年新疆降水及干旱特征 分析[J].干旱区地理,2017,40(2）:332-339[XIE Pei,GU Yanling ZHANG Yuhu,et al. Characteristics of precipitation and drought in Xinjiang during the past 1961—2015 years[J].Arid Land Geography,2017,40(2）:332-339]   
[9]DU Lingtong,SONG Naiping,LIU Ke,et al. Comparison of two simulation methods of the temperature vegetation dryness Index （TVDI）for drought monitoring in semi-arid regions of China[J]. Remote Sensing,2017,9(2）:19.   
[10]LIU Ying,YUE Hui.The temperature vegetation dryness index （TVDI）based on bi-parabolic NDVI-Ts space and gradient-based structural similarity（GSSIM）for long-term drought assessment across Shaanxi Province,China（2000—2016）[J]. Remote Sensing,2018,10(6) :959.   
[11]SANDHOLTI,RASMUSSEN K,ANDERSEN J.A simple interpretation of the surface temperature/vegetation index space for assessment of surface moisture status[J].Remote Sensing of Environment,2002,79(2）:213 - 224.   
[12]TAGESSON T,HORISON S,NIETO H,et al. Disagegation of SMOS soil moisture over West Africa using the temperature and vegetation drynessindex based on SEVIRI land surface parameters [J]. Remote Sensing of Environment,2018,206:424 -441.   
[13]HE Dong,YI Guihua,ZHANG Tingbin,et al.Temporal and spatial characteristics of EVIand its response to climatic factors in recent 16 years based on grey relational analysis in inner mongolia autonomous region,China[J]. Remote Sensing,2018,10(6） :961.   
[14]ZHAO Shuhe,CONG Dianmin,HE Kexun,et al. Spatial-temporal variation of drought in China from 1982 to 2010 based ona modified Temperature Vegetation Drought Index（mTVDI）[J]. Scientific Reports,2017,7(1) :17473.   
[15] SCHIRMBECK LW,FONTANA DC,SCHIMBECK J. Two approaches to calculate TVDI in humid subtropical climate of southern Brazil[J]. Scientia Agricola,2018,75(2）:111-120.   
[16]ZHU Wenbin,JIA Shaofeng,LVAifeng.A time domainsolutionof the Modified Temperature Vegetation Dryness Index（MTVDI） for continuous soil moisture monitoring[J].Remote Sensing of Environment,2017,200:1 -17.   
[17]YANG Ruowen,WANG Hai,HU Jinming,et al.An improved temperature vegetation dryness index（iTVDI）and itsapplicability to drought monitoring[J].Journal of Mountain Science,2017,14 (11) :2284 -2294.   
[18］刘艳伟,王淑莹,焦忠帅,等.基于温度植被干旱指数法（TVDI)的朝阳县干旱监测[J].浙江农业学报,2018,30（1)：129- 136.[LIU Yanwei, WANG Shuying,JIAO Zhongshuai,et al. Monitoring drought in Chaoyang County of Liaoning Province using temperature vegetation drought index（TVDI）[J].Acta Agriculturae Zhejiangensis,2018,30(1） :129-136.]   
[19］葛少青,张剑,孙文,等.三种干旱指数在干旱区沼泽湿地土壤 水分遥感反演中的应用[J].生态学报,2018,38（7）:2299 - 2307.[GE Shaoqing,ZHANG Jian,SUN Wen,et al.Application of three drought indexes in soil moisture inversion using remote sensing in marsh wetlands of arid area[J].Acta Ecologica Sinica, 2018,38(7) :2299 -2307. ]   
[20］何宝忠,丁建丽,李焕等.新疆植被物候时空变化特征[J].生 态学报,2018,38(6）:2139-2155.[HE Baozhong,DING Jianli, LI Huan,et al.Spatiotemporal variationof vegetation phenology in Xinjiang[J].Acta Ecologica Sinica,2018,38(6）:2139-2155.]   
[21] TESTA S,SOUDANI K,BOSCHENI K,et al. MODIS-derived EVI, NDVI and WDRVI time series to estimate phenological metrics in French deciduous forests[J].International Journal of Applied Earth Observation & Geoinformation,2018,64:132-144.   
[22]ZHAO Xiaoqian,SU Yanjun,HU Tianyu,et al.A global corrected SRTMDEM product for vegetated areas[J].Remote Sensing Letters,2018,9(4) :393 -402.   
[23]CAO Yueqian,ZHANG Wu,WANG Wenjing. Evaluation of TRMM

3B43 data over the Yangtze River Delta of China[J].Scientific Reports,2018,8(1） :5290. [24]HUETE A,DIDANK,MIURAT,etal.Overview of the radiometric and biophysical performance of the MODIS vegetation indices[J].

Remote Sensing of Environment,2002,83（1):195-213. [25]PRICE JC. Using spatial context in satellite data to infer regional scale evapotranspiration[J].IEEE Transactions on Geoscience & Remote Sensing,1990,28(5）:940-948.

# Application of modified TVDI in drought monitoring in arid areas

CHEN Bing-yin $^ { 1 , 2 }$ ，YANG Liao¹，CHEN X $^ { 1 , 3 }$ ， WANG Wei-shengl (1XinjiangIstituteofologndGeograpytateKeLaboratoryofesertandOsis EologyUumqi8ol1,injangChina; 2UniversityofChineseAcademyofSciences,Beijing10o49,China；3ResearchCenterfor Ecologyand Environmentof Central Asia,Chinese Academy of Sciences,Urumqi 83oo11,Xinjiang,China)

Abstract：Thedrought isoneof themost influential natural disastersona global scale.Thesoildesertification and salinization from drought can cause irreversible damage to the ecological environment.On basis of the preprocesing and cloud removal of MODIS data,this paper modifies the TVDI model through terrain correction and constructed an modified Temperature Vegetation Dryness Index ( $m T V D I )$ ）for drought monitoring in arid regions of Xinjiang,China,andcompared it with the traditional TVDIand verified itusing soil measureddata.The results showed as follows: (1) $m T V D I _ { E }$ constructed by $E W I$ (Enhanced Vegetation Index) and corrected $L S T$ ( Land Surface Temperature)has the highestsensitivityto drought monitoring inarid area，and thecorrelation with measured soil moisture data is $R ^ { 2 }$ :0.74；(2）In 2O15,the drought in Xinjiang was centered in the Tarim Basin and the Junggar Basin，and the situation was gradually decreased fromthe serious drought in thecenters toa humid state in the mountainous areas.From the time point of view,the drought in Xinjiang was the most serious in June,Julyand August；（3）The spatial and temporal distribution characteristics of drought in Xinjiang based on $m T W D I _ { E }$ were compared and analyzed with TRMM precipitation data.Theresult shows that the spatial and temporal distributionof drought was consistent between the two methods. The correlation between precipitation and $m T W D I _ { E }$ in different time periods was high，and passed the $P < 0 . 0 1$ significance test. Above all, $m T V D I _ { E }$ based on TVDI can effectively carry out drought monitoring inarid regions of Xinjiang with high precision.Therefore,this willprovide reference for thequantitative research on drought monitoring at large regional scale in the future.

Key words:arid area；drought monitoring；TVDI； TRMM