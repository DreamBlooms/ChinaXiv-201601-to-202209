# RFE2.0遥感降水数据在新疆的适用性评价

刘海军},²，陈亚宁²，徐长春'

（1新疆大学资源与环境科学学院,绿洲生态教育部重点实验室,新疆乌鲁木齐830046;2中国科学院新疆生态与地理研究所,荒漠与绿洲生态国家重点实验室,新疆乌鲁木齐830011)

摘要：结合新疆的65个气象观测站日降水数据，采用连续验证统计方法、分类验证统计方法对RFE2.0遥感降水数据在新疆的适用性进行了评估。结果表明：(1)通过连续验证统计分析，新疆地区平均偏差MBE(MeanBiasError)总体对日降水量高估，均值为 $0 . 4 ~ \mathrm { m m }$ ，在 $0 . 5 ~ \mathrm { m m }$ 内的站点超过 $70 \%$ 。RFE2.0遥感降水数据与地面观测站的日降水量之间相关系数 $R$ 的平均值为0.4,表现为较低的相关性。从偏离真实值情况来说，东疆模拟值和观测值最接近。（2)分类验证统计方法对降水事件FBI(Frequency Bias Index)有所高估。按片区来说，降水事件高估的小值区主要在北疆，高估程度低于全疆平均水平。北疆的正确率POD(Probabilityof Detection)大于南疆、东疆，同时北疆发生空报率 $F A R$ (FalseAlarmRate）的可能性也小于南疆、东疆。（3)通过实例验证了RFE2.0在北疆、南疆、东疆的可靠性。以上规律可为RFE2.0在新疆的应用提供科学依据。

关键词：降水；RFE2.0；适用性；新疆中图分类号：TP79 文献标识码：A 文章编号：

降水是地表水循环过程的基本组成部分，其时空分配直接影响着陆地水文过程，在内陆干旱区有着极为重要的意义[1-6]。新疆作为我国内陆典型干旱区，降水对当地生态环境和农业发展方面有着特殊的作用。新疆地域辽阔、地形复杂、气象站点稀少且分布不均，难以满足防洪、抗旱和水资源管理等方面的需要。卫星遥感数据产品为气象站稀少区域进行大面积的降水估算提供了有效、经济的方法[7]，并发挥了十分重要的作用。

RFE2.0遥感降水数据产品由XIE等改进算法产出[8-9],空间分辨率为 $0 . 1 ^ { \circ } \times 0 . 1 ^ { \circ }$ ,最初目的是在非洲国家用于洪水模型预报。EPHREMGe-bremariam Beyene 等[1o0]分析了RFE2.O在降雨观测站稀少、不均匀分布的非洲埃塞俄比亚的月降雨产品降水精度情况，表明能可靠模拟降雨强度、持续时间以及不同空间时间尺度上缺雨情况，在精度方面更加接近真实观测值。RASMUSFensholt等[1]分析了非洲荒漠草原使用RFE2.0 的趋势性分析。JOHNF.HERMANCE[12]利用RFE2.0 和观测站数据将东非荒漠草原2012 年极端风暴进行对比分析，发现RFE2.0对于季节性和每年的降水总量是合理的，但对于当地的区域性极端气象事件很难反映。BAJRACHARYASR[13]证实了在兴都库什一喜马拉雅区域的季风控制的区域卫星降雨产品的有效性[14]

因 RFE2.0主要覆盖非洲、南亚、中亚地区[12,15],国内研究相对较少,主要在西藏高原地区。王敏等[16]使用RFE2.0 模拟了2009 年西藏高原的区域降水，并结合该地区气象站降水观测资料分别从不同尺度评价了该模型在西藏高原降水估算中的适用性。除多等[1从西藏高原不同气候区选取11个典型气象站日降水量观测资料，验证了RFE2.0降水数据产品在西藏高原的应用效果。

RFE2.0在非洲、南亚、我国西藏高原地区已有一些研究和应用[10,12-14,16-20],在新疆地区尚未做过相关研究分析。新疆呈“三山夹两盆”地貌格局，地形条件复杂。本文结合新疆的65个气象站的观测数据，采用连续验证统计、分类验证统计方法和实例分析等评估了RFE2.0在新疆的适用性，为在新疆水资源管理方面提供科学依据

# 1研究区概况、数据资料与方法

# 1.1 研究区概况

![](images/6362fadc4a2f75799f4ae5ed377d3ca9107394b0ee0210faf87bf000eb725d17.jpg)  
图1研究区地理位置、气象站分布图  
Fig.1Geographical location and distribution of meteorological stations in the study area

新疆地处亚欧内陆，面积约为 $1 6 6 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 区域内地形复杂，概括为“三山夹两盆”的地貌轮廓,山脉与盆地相间排列[21]。天山以南是塔里木盆地，天山以北是伊犁河谷和准噶尔盆地，东部为吐哈盆地(图1)。由于特殊的地理位置，新疆属典型的干旱、半干旱地区，主要靠大西洋湿润气团带来降水[22]。根据全疆多年的实测资料的计算分析,新疆多年平均年降水深 $1 5 7 . 4 ~ \mathrm { m m } ^ { [ 2 3 ] }$ ,在西北及全国排位倒数第1。区域内水资源严重短缺，生态环境十分脆弱。

# 1.2 数据资料

本文基于中国气象数据网（http：/data.cma.$\mathrm { c n / }$ )下载得到2016年新疆65个气象站降水数据$^ { 1 2 \mathrm { ~ h ~ } }$ 值(即 $2 0 : 0 0 \sim 8 : 0 0$ 时和 $8 : 0 0 \sim 2 0 : 0 0$ 时两个时间段），数据的正确率均接近 $100 \%$ 。根据多年降水资料新疆雨季最早开始于3月份[23-24],全疆大部分地区雨季推迟到4月份，新疆年内降水主要集中在夏季。本文选择2016年3～10月作为研究时间段。65个气象站包括20个国际通信交换气象站GTS（Global Telecommunications System）站。我国降水量日值是指前一天20：00时至当天20：00时，而RFE2.0模型模拟的降水量日值时间是世界时，即当天8：00时至次日8：00时（北京时间），所以为与RFE2.0模拟值时间段一致，将下载的当日 $8 : 0 0 \sim$ 20：00时和当日20：00时至次日8：00时的降水量相加得到日降水量8：00时至次日8：00时数据。

# 1.3 研究方法

1.3.1RFE2.0模型RFE2.0遥感降水模型融合了3 种卫星遥感数据[27],包括：（1) DMSP（DefenseMeteorologicalSatelliteProgramme）上的SSM/I(Spe-cial SensorMicrowave/Imager）反演的降水量。（2）NOAA系列卫星上的AMSU-B（AdvancedMicrowaveSoundingUnit-B)反演的降水量。（3）欧洲气象卫星（Eumetsat'sMetesatSatellite）反演的GPI(GOESPre-cipitationIndex）,并结合GTS站 $2 4 ~ \mathrm { h } \left( 8 { : } 0 0 \sim\right.$ 次日8：00时）日降水量观测值模拟日降水量。RFE2.0模型范围已扩展到中亚地区。在中亚的覆盖范围为$1 0 ^ { \circ } \sim 6 0 ^ { \circ } \mathrm { N } , 2 0 ^ { \circ } \sim 9 5 ^ { \circ } \mathrm { E } _ { \circ }$

RFE2.0 从（ftp://ftp.cpc.ncep.noaa.gov/GIS/RFE/)网站上下载。NOAA网站上提供中亚一年时间范围的矢量和栅格数据，空间分辨率为 $0 . 1 ^ { \circ } \times$ $0 . 1 ^ { \circ }$ ,其它数据都以二进制格式存储的，需要转化为文本格式。通过ArcGIS10.2软件按照气象站点坐标提取RFE2.0日模拟值。日降水量值时间为世界时，即当日8：00时至次日8：00时的降水量（北京时间）。在2016年3月1日到10月31日时间范围内，除4dRFE2.0 缺失数据以外共有241个日数据。

1.3.2连续验证统计分析方法采用相关系数$( R )$ 、平均偏差（MBE）、平均绝对误差（MAE）和均方根误差(RMSE)统计指标分析评估其精度[13] O

$$
M B E = { \frac { \sum _ { i = 1 } ^ { n } \left( { x _ { i } - y _ { i } } \right) } { n } }
$$

$$
R = \frac { \sum _ { i = 1 } ^ { n } \left( x _ { i } - \bar { x } \right) \left( y _ { i } - \bar { y } \right) } { \sqrt { \sum _ { i = 1 } ^ { n } \left( x _ { i } - \bar { x } \right) ^ { 2 } \left( y _ { i } - \bar { y } \right) ^ { 2 } } }
$$

$$
\ M A E = { \frac { \sum _ { i = 1 } ^ { n } { \left| { \boldsymbol { x } } _ { i } - { \boldsymbol { y } } _ { i } \right| } } { n } }
$$

$$
R M S E = \sqrt { \frac { \sum _ { i = 1 } ^ { n } \left( x _ { i } - y _ { i } \right) ^ { 2 } } { n } }
$$

式中： $x _ { i } \setminus y _ { i }$ 分别表示某一格点的遥感降水产品模拟值和实际观测值； $n$ 为观测样本数。

1.3.3分类验证统计方法本文对RFE2.0和实测降水量进行对比，评价对降水事件的探测能力以及降水量估计的准确性。对降水事件的探测分为4种情况[13,25]：(1)模拟和实测都有降水;(2)模拟有降水，实测无降水；（3）模拟无降水，实测有降水；（4）模拟和实测都无降水。指标FBI（FrequencyBi-asIndex）、正确率POD（ProbabilityofDetection）、空报率 $F A R$ （FalseAlarmRatio）用来量化RFE2.0对降水事件的探测能力，其中 $F B I > ( \mathbf { \Sigma } < ) \ 1$ 表示RFE2.0高估（低估）了降水事件的发生， $P O D$ 表示正确探测降水事件的比例， $F A R$ 表示误测降水事件的比例。各项指标的最优度[13,25]分别为： $F B I = 1$ ，$P O D = 1$ . $F A R = 0$ ，计算公式如下：

$$
F B I = { \frac { a + b } { a + c } }
$$

$$
P O D = { \frac { a } { a + c } } 
$$

$$
F A R = \frac { b } { a + b }
$$

式中： $\mathbf { \alpha } _ { a }$ 为RFE2.0和实测都存在降水的出现次数； $b$ 为RFE2.0有降水而实测无降水的出现次数； $\boldsymbol { \mathbf { \mathit { c } } }$ 为 RFE2.0无降水而实测有降水的出现次数。

# 2 结果和分析

新疆不同区域间降水变化差异大，降水特征按水平方向划分为北疆、南疆、东疆[26],本文按以上三个片区对区域性降水进行分析。对应的气象站点分别28个、30个、7个。

# 2.1连续验证统计结果和分析

65个站点中超过 $8 5 \%$ 的站点RFE2.0遥感降水产品数据和观测数据相关系数 $R$ 通过了 $9 5 \%$ 显著性检验。未通过显著检验的站点中除一个为东疆站点，其余全为南疆站点。 $R$ 在 $- 0 . 0 2 \sim 0 . 8 3$ 之间，平均值为0.4。 $R < 0 . 3$ 的站点占 $3 5 \%$ ，在 $0 . 3 \sim$ 0.5之间站点占 $34 \%$ K $R { \geqslant } 0 . 5$ 的站点占 $31 \%$ （如图2a)。从北疆、南疆、东疆来看，北疆 $> 4 5 \%$ 的站点 $R$ 在 $0 . 3 \sim 0 . 5$ 之间， $> 3 5 \%$ 的站点 $R > 0 . 5$ ,平均值为0.47。南疆 $43 \%$ 的站点 $R > 0 . 3$ ，平均值为0.32。东疆区域超过 $5 5 \%$ 的站点 $R$ 大于0.5,平均值为0.46。总的来说，全疆RFE2.0数据和观测数据相关系数均值为0.4，相关性并不明显。分片区相关性大小顺序为北疆、东疆、南疆。

平均偏差MBE范围在 $- 0 . 8 2 \sim 4 . 4 5 ~ \mathrm { m m }$ 之间，均值为 $0 . 4 \ \mathrm { m m }$ 。超过 $8 5 \%$ 的站点MBE为正（高估），MBE在 $0 . 5 \ \mathrm { m m }$ 内的站点超过 $70 \%$ ，在 $1 ~ \mathrm { m m }$ 内的站点超过 $9 0 \%$ （图2b）。北疆超过 $7 5 \%$ 的站点$M B E > 0$ ,南疆超过 $9 5 \%$ 的站点 $M B E > 0$ ，东疆$100 \%$ 站点 $M B E > 0$ 。平均绝对误差 $M A E$ 范围在$0 . 2 3 \sim 4 . 7 ~ \mathrm { m m }$ 之间,均值为 $1 . 1 6 \ \mathrm { m m }$ . $M A E < 1 \ \mathrm { m m }$ 的测站超过 $5 0 \%$ 。北疆 $M A E$ 均值为 $1 . 4 2 \ \mathrm { m m }$ ，南疆$M A E$ 均值为 $1 . 0 5 \ \mathrm { m m }$ ,东疆 $M A E$ 为 $0 . 5 9 \ \mathrm { m m }$ $M A E$ 均值大小顺序为北疆、南疆、东疆。均方根误差RMSE 范围在 $1 . 0 3 \sim 9 . 7 ~ \mathrm { m m }$ 之间,均值 $3 . 3 2 \ \mathrm { m m }$ 。北疆RMSE均值为 $3 . 7 2 \ \mathrm { m m }$ ，南疆RMSE 均值为$3 . 2 3 ~ \mathrm { m m }$ ,东疆RMSE 均值为 $2 . 1 \ \mathrm { m m }$ 。 $R M S E$ 均值大小顺序为北疆、南疆、东疆。从以上分析总体来看，全疆平均偏差对日降水量高估。北疆相比南疆、东疆对降水量低估可能性大。从偏离真实值情况来说，东疆模拟值和真实值最接近。

# 2.2分类验证统计结果和分析

因RFE2.0在算法中将GTS站的日降水数据作为重要输入项,所以分类验证统计中，作为输入项GTS 站数据会被识别[13]。为提高分类验证统计的真实性，应该在GTS站之外的45个观测站选择验证。

45个站点的FBI值在0.82～3.71之间，其中

![](images/1bf1d29c5026d8ee55562603c7fe7564d402e20a956dca936cade9531552bc39.jpg)  
图2日降水量探测能力指标分布图  
Fig.2Index distribution of detective capacity of daily precipitation

41个站点的 $F B I > 1$ ，总体高估了降水事件的发生。4个 $F B I < 1$ 的站点全部分布在北疆地区，低估了降水事件的发生。低估、高估分别占到总数的 $9 \%$ 、$91 \%$ ,此外， $F B I < 1$ 的均值为0.91， $F B I > 1$ 的均值为1.94,低估均值更近于1，表明低估程度低于高估的程度(图3a）。北疆、南疆、东疆的FBI的平均值分别为1.42、2.1、2.53。全疆总体来说对降水事件高估，按片区FBI值由高到低分别为东疆、南疆、北疆。北疆对降水事件高估程度低于全疆高估的平均水平。

POD值的范围为 $0 . 1 2 \sim 0 . 9 5$ ,平均值为0.67。从图3b中可以看出， $P O D < 0 . 5$ 的站点占 $1 3 \%$ ，全部集中在天山以南； $69 \%$ 的站点 $P O D$ 值都在 $0 . 5 \sim$ 0.8之间，其中主要分布在天山以北; $18 \%$ 的站点$P O D > 0 . 8$ ,在南北疆都有分布。北疆、东疆、南疆$P O D$ 平均值分别为 $0 . 7 4 \ 、 0 . 6 1 \ 、 0 . 6 1$ 。说明RFE2.0对于北疆区域正确率高于东疆、南疆，南疆和东疆正确率一致。总体说, $P O D$ 均值 $> 0 . 5 , P O D > 0 . 5$ 的台站个数超过 $8 5 \%$ 。分片区从北、南、东疆来看，北疆地区 $P O D$ 高于南疆和东疆。

FAR值在 $0 . \ 1 8 \sim 0 . \ 9 2$ 之间，均值为0.58（图3c）。 $F A R < 0 . 5$ 的站点占 $3 3 \%$ ,其中超过 $90 \%$ 分布天山以北。 $F A R$ 介于 $0 . 5 \sim 0 . 8$ 之间共有23个，超过 $5 0 \%$ ,主要分布在南疆和东疆。 $F A R > 0 . 8$ 格点全部分布在南疆和东疆。北疆、东疆、南疆 $F A R$ 平均值分别为 $0 . 4 3 \ 、 0 . 7 4 、 0 . 6 9$ 。从北、南、东疆来看，北疆地区发生空报的可能性小于东疆和南疆。

从分类验证统计方法总的来说，RFE2.0对全疆降水事件高估，对降水事件的正确率大于0.5，同时空报的可能性也很大。按片区来说北疆对降水事件高估程度低于全疆高估的平均水平。对北疆的正确率估算的可能性大于南疆、东疆；北疆发生空报的可能性小于南疆、东疆。

# 2.3 实例分析

为了具体分析RFE2.0数据在不同区域情况，分片区从45个非GTS站中选择北疆、南疆、东疆的海拔最高和最低的观测站，分析评价RFE2.0在2016年 $3 \sim 1 0$ 月数据的可靠性（表1）。

![](images/37d7d7c62074566e8afb69f590f0f39ef6b9e62fb6416c4635fc58a3760013be.jpg)  
图3日降水事件探测能力指标分布图  
Fig.3Index distribution of detective capacity of daily precipitation occurrences

表1不同片区站点RFE2.0对降水的探测能力Tab.1Detective ability of RFE2.O in different area  

<html><body><table><tr><td>站名</td><td>纬度／N</td><td>经度／E</td><td>海拔／m</td><td>所属区域</td><td>R</td><td>MBE/mm</td><td>FBI</td><td>POD</td></tr><tr><td>昭苏</td><td>43.15</td><td>81.13</td><td>1 8510.00</td><td>北疆</td><td>0.50</td><td>-0.32</td><td>1.30</td><td>0.88</td></tr><tr><td>蔡家湖</td><td>44.20</td><td>87.53</td><td>440.50</td><td></td><td>0.44</td><td>0.32</td><td>1.60</td><td>0.67</td></tr><tr><td>吐尔尕特</td><td>40.52</td><td>75.40</td><td>3 504.40</td><td>南疆</td><td>0.03</td><td>2.72</td><td>1.83</td><td>0.90</td></tr><tr><td>尉犁</td><td>41.35</td><td>86.27</td><td>884.90</td><td></td><td>0.04</td><td>0.20</td><td>2.23</td><td>0.41</td></tr><tr><td>伊吾</td><td>43.27</td><td>94.70</td><td>1 728.60</td><td>东疆</td><td>0.70</td><td>0.02</td><td>1.95</td><td>0.65</td></tr><tr><td>鄯善</td><td>42.85</td><td>90.23</td><td>398.60</td><td></td><td>0.65</td><td>0.42</td><td>3.53</td><td>0.60</td></tr></table></body></html>

对于北疆两个站点，RFE2.0数据和观测数据相关系数都超过了0.4，通过 $9 5 \%$ 的显著性检验（图$\mathrm { 4 a , 4 b }$ )。RFE2.0对昭苏日降水量的平均偏差MBE为 $- 0 . 3 2 \ \mathrm { m m }$ ，表现为低估；RFE2.0对蔡家湖日降水量的平均偏差MBE为 $0 . 3 2 \mathrm { ~ m m }$ ，表现为高估。RFE2.0对降雨事件发生估计 $F B I$ 都大于1,且昭苏对降雨事件高估程度低于蔡家湖。RFE2.0能探测到昭苏 $8 8 \%$ 的降水日，蔡家湖 $67 \%$ 的降水日。在探测到的降水日中，昭苏有 $47 \%$ 的降水日高估了降水量，蔡家湖有 $54 \%$ 的降水日高估了降水量。

对于南疆两个站点，RFE2.0和观测数据的相关性 $R$ 未通过 $9 5 \%$ 的显著性检验，表现为较差的相关性（图5a、5b）。两个站点平均偏差MBE都为正，表现为对日降水量高估，对吐尔尕特高估程度大于尉犁。RFE2.0对降雨事件发生估计FBI都大于1,对尉犁的高估程度高于吐尔尕特。RFE2.0能探测到吐尔尕特 $90 \%$ 的降水日，尉犁 $41 \%$ 的降水日。在探测到的降水日中，尉犁有 $67 \%$ 的降水日高估了降水量，吐尔尕特有 $60 \%$ 的降水日高估了降水量。

对于东疆区域，RFE2.0和观测数据相关系数都超过了0.6，通过 $9 5 \%$ 的显著性检验（图6a、6b）。两个站点平均偏差MBE都为正，表现为对日降水量高估，对鄯善高估程度大于伊吾。RFE2.0数据对降雨事件发生估计FBI都大于1，且善善对降雨事件高估于伊吾。RFE2.0能探测到伊吾 $6 5 \%$ 的降水日，鄯善 $6 0 \%$ 的降水日。在探测到的降水日中，伊吾有 $3 8 \%$ 的降水日高估了降水量，鄯善有 $78 \%$ 的降水日高估了降水量。

![](images/a610259651f652d87e9cf4edaa4fd6a635e9ae5943c6bbd6d86480343a3a81a4.jpg)  
Fig.4Comparison of daily precipitation between RFE2.O and rain-gauge

![](images/1778d093567a9078ea6a6972032cfc217b994d0aacbc4b1164724521d034e9a0.jpg)  
图4北疆日降水量的观测值与模拟值对比  
图5南疆日降水量的观测值与模拟值对比  
Fig.5Comparison of daily precipitation between RFE2.O and rain-gauge

![](images/ccbc20d197d6604ec46b24c2a487299b654aeb7e652d3a6551a0ea401346dad4.jpg)  
图6东疆日降水量的观测值与模拟值对比  
Fig.6Comparison of daily precipitation between RFE2.O and rain-gauge

综上所述，用实例验证分析了RFE2.0在北疆、南疆、东疆的应用效果。表1中反映FBI值在高海拔较低海拔偏小， $P O D$ 值在高海拔较低海拔偏大，但通过结合连续验证统计、分类验证统计总体情况来看，海拔和 $R \ 、 M B E \ 、 F B I \ 、 P O D$ 没有必然关系。

# 3讨论

本文将RFE2.0与观测站降水量进行比较，并未将65个气象站降水量插值出新疆区域降水量，主要是因为新疆气象站密度小、分布不均匀，尤其是山区站点少，对空间内插效果具有重要影响，使内插结果存在很大的不可靠性和不确定性[25,28],因此,选择最简单、直接的方法进行模拟数据和观测数据的比较。

本文通过连续验证统计分析得出全疆RFE2.0和观测值相关系数平均值为0.4，低于GULEIDArtan 等[18]使用RFE2.0和观测数据对南亚湄公河的支流NamOu和SeDone支流的相关性，可能与南亚处于亚洲季风区域，模拟效果好于干旱区有关。本文分析得出全疆总体降水量估算值比实测值偏大，表明RFE2.0数据高估了干旱区的降水量，与SHRESTHA 等[15]和BAJRACHARYA SR等[13]得出的结论一致。北疆区域同时存在估算值比实测值偏小的情况，可能是特殊的地形、气候条件引起的。塔里木盆地、吐哈盆地盛行下行气流，受大西洋暖湿气流影响较为微弱。北疆区域受大西洋暖湿气流影响比南疆、东疆强烈。所以实测值可能会比模拟值大。

除多等[17]使用RFE2.0验证了在西藏高原的应用效果，表明RFE2.0估算的正确率 $P O D$ 一般大于 $7 3 \%$ ,而误报率 $F A R$ 为 $2 \% \sim 1 2 \%$ 。对于新疆RFE2.0估算的正确率的 $P O D$ 平均值在 $67 \%$ ; $F A R$ 平均值在 $5 9 \%$ ,说明新疆的RFE2.0估值的正确率低于青藏高原，而误报率高于西藏高原。可能与新疆复杂的干旱区地理环境有关。王敏等[16]验证了RFE2.0降水估算产品在西藏高原的应用效果,RFE2.0遥感降水数据与观测值的相关系数在0.4以上的测站占 $4 6 \%$ 。新疆RFE2.0数据的模拟值与观测值之间相关系数在0.4以上的站点占 $4 9 \%$ ，与西藏高原接近。

# 4结论

（1）通过连续验证统计分析，全疆RFE2.0估算与地面观测的日降水量之间相关系数的平均值为0.4,表现为较低的相关性。分片区来看，北疆、南疆、东疆相关系数平均值分别为 $0 . 4 7 , 0 . 3 2 , 0 . 4 6$ □平均偏差总体对日降水量高估,MBE 均值为0.4$\mathbf { m } \mathbf { m }$ ，在 $0 . 5 \ \mathrm { m m }$ 内的站点超过 $70 \%$ 。从偏离真实值情况来说，东疆模拟值和真实值最接近。

（2）从分类验证统计来说，全疆对降水事件FBI高估， $P O D$ 均值大于 $5 0 \%$ ， $F A R$ 均值大于 $5 0 \%$ 0按片区来说北疆降水事件高估程度低于全疆平均水平。对北疆的正确率估算的可能性大于南疆、东疆,同时北疆发生空报的可能性小于南疆、东疆。

（3）从45个非GTS站分别选取北疆、南疆、东疆三个片区的海拔最高站和最低站，通过连续验证和分类验证统计具体分析，验证了RFE2.0的可靠性。同时结合总体情况来看，海拔和相关系数 $R$ 、FBI、POD没有必然关系。

致谢：感谢NOAA网站提供的RFE2.0卫星降水数据;感谢中国气象数据网提供的气象数据。

参考文献（References）   
[1]刘元波,傅巧妮,宋平,等.卫星遥感反演降水研究综述[J].地 球科学进展,2011,26(11）:1162-1172.[LIU Yuanbo,FU Qiaoni,SONG Ping,et al. Satellite retrieval of precipitation:An overview［J].Advances in Earth Science,2011,26（11）:1162- 1172. ]   
[2］胡增运,倪勇勇,邵华,等.CFSR、ERA-Interim 和 MERRA 降水 资料在中亚地区的适用性[J].干旱区地理,2013,36(4）：700 - 708.[HU Zengyun,NI Yongyong,SHAO Hua,et al. Applicability study of CFSR,ERA-Interim and MERRA precipitation estimates in Central Asia[J].Arid Land Geography,2013,36（4）： 700 -708.]   
[3］陈亚宁,李稚,方功焕,等.气候变化对中亚天山山区水资源影 响研究[J].地理学报,2017,72（1）:18-26.[CHEN Yaning,LI Zhi,FANG Gonghuan,et al.Impact of climate change on water resources in the Tianshan Mountians,Central Asia[J].Acta Geographica Sinica,2017,72(1):18-26.]   
[4]CHEN Yaning,LI Baofu,LI Zhi,et al.Water resource formation and conversion and water security in arid region of northwest China [J]. Journal of Geographical Sciences,2016,26(7）:939 -952.   
[5］姚俊强,杨青,刘志辉,等.中国西北干旱区降水时空分布特征 [J].生态学报,2015,35（17):5846-5855.[YA0 Junqiang, YANG Qing,LIU Zhihui,et al. Spatio-temporal change of precipitation in arid region of the northwest China[J].Acta Ecologica Sinica,2015,35(17) :5846 -5855.]   
[6］沈彬,李新功.塔里木河流域 TRMM降水数据精度评估[J].干 旱区地理,2015,38(4）:703-712.[SHEN Bin,LI Xingong.Accuracy assessment of TRMM3 B43 data in Tarim River Basin[J]. Arid Land Geography,2015,38(4） :703-712.]   
[7]MANDIRA S S,ARTAN G A,BAJRACHARYA S R,et al. Using satellite-based rainfall estimates for streamflow modelling:Bagmati Basin[J].Journal of Flood Risk Management,2008,1（2）:89 - 99.   
[8]XIE Pingping,ARKIN Philip A.A 17-year monthly analysis based on gauge observations satelite estimates and numerical model outputs[J]. Buletin of the American Meteorological Society,1997,78 (11):2539 -2558.   
[9]XIE Pingping,ARKIN Phillip A.Analyses of global monthly precipitation using gauge observations,satelite estimates,and numerical model predictions[J]. Journal of Climate,1996,9（4）:840- 858.   
[10]EPHREM Gebremariam Beyene,BERND Meissner.Spatio-temporal analyses of correlation between NOAA satellite RFE and weather stations'rainfall record in Ethiopia［J].International Journal of Applied Earth Observation and Geoinformation,2010,(12S）: S69 - S75.   
[11]RASMUS Fensholt,KJELD Rasmussen. Analysis of trends in the Sahelian‘rain-use efficiency'using GIMMS NDVI,RFE and GPCP rainfall data[J].Remote Sensing of Environment,2011,（115）： 438 - 451.   
[12]JOHN F HERMANCE,HUSSEIN M Sulieman. Comparing satellite RFE data with surface gauges for 2O12 extreme storms in African East Sahel[J].Remote Sensing Letters,2013,4（7) :696-705.   
[13]BAHRACGARY S R,SHRESTHA M S,MOOL P K,et al. Validation of satellite rainfall estimation in the summer monsoon[C]// 10th international symposiumon high mountain remote sensing cartography,international centre for integrated mountain development （ICIMOD）,Kathmandu,Nepal,2010:281-290.   
[14]JOHN F Hermance,HUSSEIN M Sulieman. Assessing daily and seasonal satellite rainfall estimates using local gauges for the anomalous 2012 monsoon season in the African East Sahel[J].International Journal of Remote Sensing,2013,35(1):253-288.   
[15]SHRESTHAMS,ARTANGA,BAJRACHARYA SR,et al.Biasadjusted satellite-based rainfall estimates for predicting floods : Narayani Basin[J]. Journal of Flood Risk Management,2011,4 (4) :360 -373.   
[16］王敏,周才平,吴良,等.遥感估算降水在西藏高原中的应用研 究[J].高原气象,2012,31（5）：1215-1224.[WANG Min, ZHOU Caiping,WU Liang,et al.Applicaton of satelite-based rainfall estimate on the precipitation in Tibet Plateau[J].Plateau Meteorology,2012,31（5）:1215-1224.]   
[17］除多,罗布坚参,普布顿珠.NOAA RFE2.0在西藏高原的验证 [J].热带气象学报,2013,29（4）:581-589.[CHU Duo,NORBU Ghancan,PUBU Tundrop.The validation of NOAA RFE 2.0 rainfall product over major climate zones in TIBET[J]. Journal of Tropical Meteology,2013,29(4）:581-589.]   
[18]GULEIDArtan,HUSSEINGadain,JODIELSmith,etal.Adequacy of satellite derived rainfall data for stream flow modeling[J].Natural Hazards,2007,43(2) :167 -185.   
[19]SAGAR Ratna Bajracharya,WAHID Palash,MANDIRA Singh shrestha,etal. Systematic evaluationof satellite-based rainfall products over the Brahmaputra Basin for hydrological applications [J].Advances in Meteorology,2015,1-17.   
[20]BROWN M E,RACOVITEANU A E,TARBOTON D G,et al. An integrated modeling system for estimating glacier and snow melt driven streamflow from remote sensing and earth system data products in the Himalayas[J]. Journal of Hydrology,2014（519）： 1859 -1869.   
[21］陈春艳,赵克明,阿不力米提江·阿布力克木,等.暖湿背景下 新疆逐时降水变化特征研究[J].干旱区地理,2015,38（4)： 692-702.[CHEN Chunyan,ZHAO Keming,ABLIKIM Ablimitijan,et al.Temporal and spatial distributions of hourly rain intensity under the warm background in Xinjiang[J].Arid Land Geography,2015,38(4) :692-702.]   
[22］陈亚宁,王怀军,王志成,等.西北干旱区极端气候水文事件特 征分析[J].干旱区地理,2017,40（1):1-9.[CHEN Yaning, WANG Huaijun,WANG Zhicheng,et al. Characteristics of extreme climatic/hydrological events in the arid region of northwestern China[J]. Arid Land Geography,2017,40（1):1 -9.]   
[23］苏宏超,沈永平,韩萍,等.新疆降水特征及其对水资源和生态 环境的影响[J].冰川冻土,2007,29（3）：343－350.[SU Hongchao,SHEN Yongping,HAN Ping,et al.Precipitation and its

impact on water resources and ecological environment in Xinjiang region[J].Journal of Glaciology and Geocryology,2Oo7,29（3）： 343 -350.]

[24］史玉光，孙照渤，杨青.新疆区域面雨量分布特征及其变化规 律[J].应用气象学报,2008,19（3）:326-332.[SHI Yuguang, SUN Zhaobo,YANG Qing.Characteristics of area precipitation in Xinjiangregionwith its variationsJ」.Journal of AppliedMeteorologicalScience，2008，19(3):326-332.

[25］杨艳芬，罗毅.中国西北干旱区TRMM遥感降水探测能力初步评价[J].干旱区地理，2013，36（3）：371-382.[YANGYan-fen,LUO Yi.Evaluation on detective ability of TRMM remote sens-

ingprecipitation in arid region of northwest China[J].Arid Land Geography,2013,36(3）:371-382.]   
[26］徐贵青，魏文寿.新疆气候变化及其对生态环境的影响[J].干 旱区地理,2004,27（1）:14-18.[XUGuiqing,WEI Wenshou. Climate change of Xinjiang and its impact on eco-enviroment[J]. AridLand Geography,2004,27（1）:14-18.]   
[27]http:// www.cpc.ncep.noaa.gov/products/fews/RFE2.0_tech. pdf   
[28］JIN Li,ANDREW D Heap.A review of spatial interporalation methods for environmental scientists[M].Canberra：Geoscience Australia,2008:92-93.

# Evaluation of applicability of satellite-based RFE2.O rainfall data in Xinjiang

LIU Hai-jun1²，CHENYa-ning2， XU Chang-chun'   
(1CollegeofResourcesandEnvironment Science/KeyLaboratoryofOasisEcology,Xinjiang University,Urumqi830046,   
Xinjiang,China；2StateKeyLaboratoryofDesertandOasisEcology,Xinjiang InstituteofEcologyandGeography,Cinese Academy ofSciences,Urumqi 83o011,Xinjiang,China)

Abstract：With thedailyprecipitation data from 65meteorological stations in Xinjiang,China,the verification methods including continuous statistics and clasification statistics were used to evaluate the applicabilityofsatelitebased RFE2.O(Rainfallestimation2.0)data.The results showed that RFE2.O overestimated the daily precipitation in Xinjiang，with an average value of $0 . 4 \ \mathrm { m m } \ M B E$ （mean bias error）,more than $70 \%$ meteorological stations being among $0 . 5 \ \mathrm { m m }$ .The average value of correlation coefficient $R$ between RFE2.O and observation data was 0.4, indicating alow correlation with a descending order ofthecorrelation value from north Xinjiang to east Xinjiang and then to south Xinjiang.The MAE(mean absolute error） was $0 . 2 3 - 4 . 7 ~ \mathrm { m m }$ ,with $1 . 1 6 \ \mathrm { m m }$ average value. More than $50 \%$ meteorological stations with $M A E$ were smaller than $1 \mathrm { m m }$ . It was the northern,southern,eastern Xinjiang according to the order of relevance from big to small.The RMSE（root mean square error） was $1 . 0 3 - 9 . 7 ~ \mathrm { m m }$ ,with $3 . 3 2 ~ \mathrm { m m }$ average value.The descending order list was the north Xinjiang,south Xinjiang,east Xinjiang according to the $M A E$ value.From the perspective of deviation from the real value,the simulated values in east Xinjiang was close to the observed value.There were 45 non-GTS stations selected to verifythe possbilityof precipitation events through classification statistics.FBI(frequency bias index）in Xinjiang was O.82-3.71,the average value of FBI in northern,southernand eastern Xinjiang were1.42,2.1,2.53.It was eastern,southernand northern Xinjiang according to sizeof FBI.Ingenenal,RFE2.Oovervalued possibilityof rainfall events in Xinjiang,overestimationof precipitation events in northern Xinjiang is lower than theaverage of the whole Xinjiang.The POD value was 0.12 -0.95,with average value O.67. The average value of $P O D$ was 0.74,0.61,0.61,respectively from northern,eastern and southern Xinjiang.POD in northern Xinjiang was higher than that of east and southern Xinjiang. The FAR was 0.18 -0.92,with 0.58 average value and $3 3 \%$ stations FAR less than O.5.The average value of $F A R$ （20 in northern Xinjiang,eastern Xinjiang and southern Xinjiang was O.43,0.74,0.69,respectively.The value of FAR in northern Xinjiang was smaller than eastern and southern Xinjiang.Two stations were selected to analyze respectively,TuergateandYuli observation stations from the southern Xinjiang,Caijiahu and Zhaosu observation stations from the northern Xinjiang,Shanshan and Yiwu observation stations from east Xinjiang,toverifythe application of RFE2.O.The above rule can provide scientific basis for application of RFE2.O in Xinjiang.