# FAST主动反射面健康监测系统数据处理方法研究及应用

王清梅1,²，朱明²，王启明²，何玲(1.贵州大学现代制造技术教育部重点实验室，贵州 贵阳 550025；2.中国科学院国家天文台，北京 100012）

摘要：基于FAST主动反射面健康监测系统的多传感器测点与海量监测数据，提出一种数据处理方法，对系统采集的温度、应力、风速及索力等数据进行处理；采用多项式回归分析数据相关性，辨识温度梯度对应力的影响。利用提出的数据处理方法对不同工况下圈梁结构应力、索力和温度之间的相关性进行分析。分析结果表明，圈梁结构应力与温度显著相关，且在索网未变位期间圈梁结构应力主要受温度影响，索网变位期间主要受索力影响。通过对数据的处理可识别影响结构内力的主要因素，并有效分离温度变化对应力的作用，为后期运行维护提供数据支持。

关键词：FAST工程；健康监测；数据处理；相关性分析中图分类号： $\mathrm { T P } 2 7 4 ^ { + } . 2$ ； P111.44 文献标识码：A 文章编号：1672-7673(2017)02-0164-08

$5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜（Five-hundred-meter Aperture Spherical Radio Telescope，FAST)是具有主动反射面的球冠状大型射电望远镜，是国家十一五重大科技基础设施项目，建成后将成为世界最大的单口径球面射电望远镜[1]。望远镜主动反射面系统由圈梁、索网、反射面单元、下拉索、促动器、地锚等组成。其中，主索网安装在格构柱支撑的环形圈梁上，在其2225个索网节点上装有约4450

块反射面单元，每个节点下方连有一个下拉索和促动器[2]，促动器再与地锚连接，通过控制促动器形成照明口径为 $3 0 0 \mathrm { ~ m ~ }$ 的瞬时抛物面，进行天文观测[3]

为保证望远镜在运行期间的安全性，主动反射面系统装有506组北京SOIL公司生产的传感器及配套数据采集设备，用于采集圈梁及索网的温度、应变、索力等信息，对系统进行长期监测，索网测点布置如图1，共计406个测点，圈梁及格构柱测点布置如图2、图3，共计100 个测点。

健康监测系统的长期运行使得监测数据不断累积，若不迅速处理数据，被测对象的状态不能被及时有效地识别、判断及预警。因此，研究一种数据处理方法，探寻监测数据的规律及相关性，对望远镜主动反射面健康监测系统的工程应用具有重要意义。

![](images/86486b3bfaa8bdc9e773c93d681b5e189bf7b64d84cb8faeb8ad12d63670de30.jpg)  
图1主索网监测测点布置 Fig.1Arrangement of monitoring points in main cable network

![](images/ee65b9ada764151d454676c2baadbfe82c1ec2f24894272b811ac6405a927d17.jpg)  
图21#、11#、21#、31#、41#格构柱对应圈梁健康监测测点布置Fig.2Arrangement of monitoring points in thecorresponding ring beam of 1#，11#,21#,31#，41# Latice column

![](images/bff26bdc2730df509db05a08669115f998186c9dbe1b00414606c528fa82b4ff.jpg)  
图36#、16#、26#、36#、46#格构柱对应圈梁健康监测测点布置Fig.3Arrangement of monitoring points in thecorresponding ring beam of 6#，16#,26#,36#，46# Lattice column

# 1FAST主动反射面健康监测系统构成

# 1. 1 监测内容

FAST主动反射面健康监测内容如图4，主要有4个监测部分[4]。其中，结构关键构件内力监测包括对格构柱应变、圈梁应变及主索索力的监测；结构整体变形参量监测包括圈梁变形和节点空间位置监测；环境监测包括风速、风向及温度监测；促动器监测包括促动器油温、油压及促动器位置信息监测。其中，格构柱应变测点布置

![](images/92d672813f79d3421d0670e79dfef0f1f554b55b34260bf5f997bf5fde04693b.jpg)  
图4FAST主动反射面健康监测内容 Fig.4Content of the health monitoring system for the main active reflector of FAST

在索网主肋区域及索网每个扇区的中心区域对应的格构柱圈梁支座处1根靠内侧的水平拉杆及落于基础的2根靠内侧的柱肢构件上；圈梁应变测点布置在索网主肋区域及索网每个扇区的中心区域对应格构柱相应圈梁段内外支座4根斜腹杆、1根下弦环向弦杆以及圈梁跨中的1根下弦环向弦杆上；索力测点布置在应力变化幅度较大、基准态应力和内力较大以及150 根边缘主索上。

# 2数据处理流程

健康监测系统采集的原始数据是在设定采样频率下按时间分布的数据序列，可在时域内分析数据，其数据处理流程如图5。

# (1)可靠性检验

在数据采集、转换及传输时，受环境噪声、仪器设备、随机干扰等因素影响，采集的数据可能出现异常，处理数据前，需检验原始数据的可靠性，有效识别异常值。对于望远镜主动反射面健康监测系统，采用 $3 \sigma$ 准则剔除异常，并用拉格朗日插值法插值替补。

# (2)统计分析

数据预处理后，可对监测数据进一步处理。对于单项数据，通常绘制数据时程图形，对数据进行趋势统计和特征值统计，分析该项监测数据在时间轴上的变化情况，并与设计阈值比较，若超过阈值则发出预警。

![](images/78205c3fccb21fbade2aa874eaa09cdca379628e96ed84e6c978ca1d259fa890.jpg)  
图5数据处理流程图Fig.5Flow chart of data processing

（3)相关性分析

统计分析后，需分析两项参数的相关程度，利用MATLAB数值软件对大量监测数据建立回归模型，定量描述两特征量的显式关系[5」。望远镜主动反射面系统中待分析的参量很多，如温度与圈梁受力状态的关系、温度与索受力状态的关系、温度与圈梁形态的关系、风荷载与圈梁受力状态的关系等均可进行此类分析。

# (4)数据存储

经过归纳、统计和相关性分析的数据，可保存在数据库中，异常数据可按工况另行存储，为以后的系统评估提供数据支持。

# 3数据处理方法

# 3.1 可靠性检验

望远镜主动反射面健康监测系统采集的数据量大，采用工程应用较广泛的 $3 \sigma$ 原则对异常值进行处理。 $3 \sigma$ 原则是建立在统计理论的基础上，其表达式为

$$
\mid x _ { i } - { \bar { x } } \mid > 3 \sigma ~ .
$$

当某个数据 $x _ { i }$ 符合上式时，即数据 $\boldsymbol { x } _ { i }$ 与测量数据的算数平均值 $\mathit { \Pi } _ { \overline { { x } } } ^ { - }$ 偏差的绝对值大于3倍标准差时，则判定其为异常点，应予以剔除。在一个数据列中，异常值可能不止一个，剔除一个异常值后，必须重新计算剩余数据的平均值和标准差，再重新判断直至没有异常值[6]。

# 3.2 统计分析

对原始数据预处理后，得到准确、可靠的监测数据，为分析这些数据在时间轴上的变化情况，对数据绘制时程图形。选取2016年4\~5月圈梁各方位代表性测点的实测数据，绘制曲线如图6、图7。

![](images/4d51f259e1badd9c6a224baf092785750b118af829e849c084a62639efea9456.jpg)  
图62016年4月16日（晴朗无云)圈梁外侧支座下弦环向弦杆各监测点温度时程Fig.6Temperature-Time curve of each point at thebottom chord bar of the outer bearing of ringbeam（April16,2016）（cloudless）

![](images/34fe476a30912e3952f2ea2f7dccfa1fe7865097b8f481f7359f2fa585ebd897.jpg)  
图72016年5月14日（阴转晴)圈梁外侧支座下弦环向弦杆各监测点温度时程Fig.7Temperature-Time curve of each point at thebottom chord bar of the outer bearing of ringbeam（May14，2016）（Warrington）

由分析结果可知，圈梁各截面位置温差在 $5 ~ \mathrm { { ^ circ C } } \sim 6 ~ \mathrm { { ^ { \circ C } } }$ ，温差较小，故在分析温度效应时可简化为仅考虑均匀升降温引起的应变，而不考虑圈梁截面之间温差引起的应力。

选取36#格构柱对应圈梁段1号测点(图8)为研究对象，绘制2016年5月11日（晴朗)圈梁横杆温度与应力的日变化曲线图(图9）。

从图9可以看出，应力的变化曲线趋势与温度的变化趋势大体相似，在 $0 \colon 0 0 \sim 0 6 \colon 0 0$ 时段，温度较低，应力较小，由于中午和下午温度回升，圈梁横杆应力逐渐变大，统计分析结果表明，圈梁横杆应力很大程度上受温度影响，同时应力也一定程度上受其他因素的影响。

![](images/6f20174484d1f36ce44900268b8d15e8b5d1a618cb9bb37b311e09e3ec5264c8.jpg)  
图836#格构柱对应圈梁段1号测点传感器Fig.8No.1 point sensor in correspondingring beam of 36# lattice column

![](images/9ef2a1c3f38b78e3a33a00da2e64e15dec2088fc5c019e82da967d0786f57d81.jpg)  
图936#-1测点温度与应力时程图 Fig.9Time curve of temperature and stress for the monitoring point 36#-1

# 3.3 相关性分析

# 3.3.1 相关系数

为了监测不同因素对结构应力的影响，望远镜主动反射面健康监测系统布置有多种类型传感器，研究各影响因素对结构应力的影响程度，需对它们进行相关性分析，假设两种传感器采集的数据序列分别为 $X = \left[ X _ { 1 } \right.$ ， $X _ { 2 }$ ， $X _ { 3 }$ ，…， $X _ { i }$ ）、 $Y { = } \left[ Y _ { 1 } , Y _ { 2 } , Y _ { 3 } , \cdots , Y _ { i } \right]$ ，在采样周期内，每个测点采样 $\mathbf { \Omega } _ { n }$ 次数据,则相关系数可定义如下[7]：

$$
r = \frac { \displaystyle \sum _ { i = 1 } ^ { n } \left( x _ { i } - \bar { x } \right) \left( y _ { i } - \bar { y } \right) } { \displaystyle \sqrt { \sum _ { i = 1 } ^ { n } \left( x _ { i } - \bar { x } \right) ^ { 2 } \sum _ { i = 1 } ^ { n } \left( y _ { i } - \bar { y } \right) ^ { 2 } } } \ ,
$$

其中， $- 1 \leqslant r \leqslant 1$ ; $\mathit { \Pi } _ { \overline { { x } } , \ \overline { { y } } } ^ { - }$ 分别为数据序列 $X$ 、 $Y$ 的均值。

上述 $\boldsymbol { r }$ 值表示线性相关系数，若要计算非线性相关系数，可采用Spearman 秩相关系数[8]，其公式定义如下：

$$
r _ { s } = 1 - \frac { 6 \sum d _ { i } ^ { 2 } } { n ( n ^ { 2 } - 1 ) } \ ,
$$

其中，n为样本数；di=𝑥i−yi。

# 3.3.2 回归分析

由上节统计分析可知，圈梁应力很大程度上受温度影响，为进一步找出温度与圈梁应力之间的相关关系，利用温度数据和应力数据作散点图，观察散点图的聚散程度及其接近的关系类型，建立回归模型，对数据进行拟合。图10 给出2016年5月11日36#格构柱对应圈梁段1号测点横杆温度与应力散点图。

由散点图可知，温度与结构应力之间存在较强的相关性，且温度与结构应力的关系曲线类型近似于二次曲线，可用二次多项式对数据进行拟合，即定义(4)式为描述温度 $x$ 和应力 $y$ 关系的回归模型：

$$
y = \beta _ { 0 } + \beta _ { 1 } x + \beta _ { 2 } x ^ { 2 } + \varepsilon .
$$

![](images/20f3e7d78bb164d91f0043054876a796e9975ffa2eefa24c40ce29f3b3d346b6.jpg)  
图1036#-1测点温度与应力散点图Fig.10Temperature-stress scatter diagramof the monitoring point 36#-1

利用温度与应力监测数据建立回归模型，结果为： $y = 0 . \ 0 7 8 x ^ { 2 } - 2 . \ 8 9 x - 1 2 . \ 5 6$ ，其中 $R ^ { 2 } = 0 . 9 1 2 ~ 4$ ，因此回归模型有效。

# 3.3.3 温度应力分离

望远镜主动反射面圈梁结构应力主要包括4部分：圈梁、反射面单元及索网的自重，索网变位时的工作载荷，温度载荷，风荷载。圈梁结构某一测点在某一时刻总应力可定义为

$$
\pmb { \sigma } _ { ( t ) } = \pmb { \sigma } _ { T ( t ) } \ + \ \pmb { \sigma } _ { D } \ + \ \pmb { \sigma } _ { L ( t ) } \ + \ \pmb { \sigma } _ { W } ,
$$

其中， $\sigma _ { ( t ) }$ 为总应力； $\sigma _ { T ( t ) }$ 为温度应力； $\sigma _ { D }$ 为恒载应力（主要考虑圈梁、反射面单元、索网自重）；  
$\sigma _ { L ( t ) }$ 为随机荷载应力（风荷载)； $\sigma _ { \scriptscriptstyle { W } }$ 为索网变位时的工作载荷。

由于结构应力受温度影响显著，为避免索网变位时引起的应力变化被覆盖，影响活载对反射面系统安全性的评估，需将温度影响从总应力中分离，以便后期分析活载对应力的作用。

根据钢拱肋材料特性，温度与应力近似为一次线性关系，假设温度应力的拟合函数形式为[9]

$$
\sigma _ { { T } ( t ) } = a _ { 0 } ( \overline { { { T } } } _ { ( t ) } \ - \ 2 0 \ \% ) \ + \ \sum _ { i = 1 } ^ { n } a _ { i } \Delta T _ { i ( t ) } ,
$$

其中， $\overline { { T } } _ { ( t ) } = \frac { 1 } { n } \sum _ { i \ : = 1 } ^ { n } T _ { i ( t ) }$ 为测点温度多次测量求平均值得到的时间序列数据； $n$ 为总测量次数； $\Delta T _ { i ( t ) } =$ （204号 $T _ { i ( t ) } \ - \ \overline { { T } } _ { ( t ) }$ 为各次测量值减去平均值得到的时间序列数据； $2 0 \ \mathrm { { ^ circ C } }$ 为圈梁设计温度; $a _ { 0 } = \sum _ { i = 1 } ^ { n } a _ { i } / n$ ; $\boldsymbol { a } _ { i }$ 为待定拟合系数。

由(4)式可知温度与总应力是二次曲线关系，由(6)式可知温度与温度应力为一次线性关系，可采用最小二乘法对应力数据序列进行回归计算得到 $a _ { i }$ ，算出 $a _ { 0 }$ ，再把 $a _ { 0 } \mathrm { ~ , ~ } a _ { i }$ 代入(6)式求出温度应力 $\sigma _ { T ( t ) }$ ，其次将 $\sigma _ { T ( t ) }$ 代入(5)式得到$\sigma _ { D } ^ { } + \sigma _ { L ( t ) } ^ { } + \sigma _ { _ { W } } ^ { }$ ；再次，对 $\sigma _ { D } + \sigma _ { L ( t ) } + \sigma _ { \mathit { \Pi } _ { V } }$ 数据序列移动平均得到σ+σwo

同样选取2016年5月11日36#圈梁格构柱1号测点外侧支座横杆进行应力分离，图11\~图13为应力分离过程及其分析结果。

从图11可以看出温度应力与总应力的关系，温度应力与总应力的相关系数达到了0.8120,关联程度较大，在分离温度应力后，采用移动平均计算消除随机荷载的作用，此时反射面未变位形成抛物面，即$\sigma _ { { \scriptscriptstyle W } } = 0$ ，最后得到 $\sigma _ { D }$ 。

![](images/ad41999acf59acda54f96ca33c893f8187e71801cd17c4f09f562effbf355be9.jpg)  
图1136#-1测点温度应力与总应力时程图 Fig.11Time curve of temperature stress and total stress for the monitoring point 36#-1

![](images/975df957d23d0337b5897c2bf8a42459718a4fce91df72ad0a523f25c0996545.jpg)  
图1236#-1测点分离温度应力后的应力图 Fig.12Time curve after separation of temperature stress for the monitoring point 36#-1

![](images/4d2fa1d25bfc2c6ddbb1843fc6e198bc2ba6f94a34187896430b8ad4acc738f1.jpg)  
图1336#-1测点应力移动平均后的应力图 Fig.13Curve of stress after moving average for the monitoring point 36#-1

# 4数据处理方法在监测系统中的应用

# 4.1索网张拉状态相关性分析

本文以望远镜主动反射面健康监测系统中的圈梁应力为研究对象，圈梁及格构柱的状态关乎整个索网的安全和反射面精度，圈梁应力及格构柱应力对整个反射面系统的健康状况起着关键作用。选取

2016年4月19日索网张拉状态36#格构柱对应圈梁段1号测点应力传感器为研究对象，利用（2）、（3)式计算出36#-1应力传感器与邻近传感器之间的关联度如表1。

从表1可以看出，在索网张拉状态，与36#-1应力传感器关联度最大的是索力传感器221-E379-E501，达到0.98304，而与温度传感器70-36#-1关联度为0.73525，说明在索网张拉时，索力是影响圈梁应力变化的主要因素。

# 4.2索网未张拉状态相关性分析

选取2016年5月11日球面未张拉状态36#格构柱对应圈梁段1号测点应力传感器为研究对象，利用（2）、(3)式计算出36#-1应力传感器与邻近传感器之间的关联度如表2。

表2的分析结果表明，圈梁应力与温度传感器70-36#-1关联度为0.914，而与索力传感器221-E379-E501d的相关系数为0.821，小于温度传感器。说明索网未张拉时，影响圈梁应力变化的主要因素是温度。

# 4.3圈梁高度平面风速数据实测及分析

表1关联系数 Table 1 Correlation coefficient   
表2关联系数  

<html><body><table><tr><td>传感器编号</td><td>关联度</td></tr><tr><td>索力221-E379-E501</td><td>0. 983 04</td></tr><tr><td>索力191-D379-D501</td><td>0. 977 31</td></tr><tr><td>索力161-C379-C501</td><td>0. 882 05</td></tr><tr><td>温度70-36#-1</td><td>0. 735 25</td></tr></table></body></html>

Table 2 Correlationcoefficient   

<html><body><table><tr><td>传感器编号</td><td>关联度</td></tr><tr><td>索力221-E379-E501</td><td>0.821</td></tr><tr><td>索力191-D379-D501</td><td>0.196</td></tr><tr><td>索力161-C379-C501</td><td>0. 001 4</td></tr><tr><td>温度70-36#-1</td><td>0.914</td></tr></table></body></html>

大型结构应力除受温度、工作载荷影响之外，还可能受其他环境因素干扰，如风荷载。研究结构风特性的有效方法之一是进行风数据现场实测，并对实测数据统计分析[10]。本文利用 HT-628 风速计对圈梁高度平面36#格构柱区域风速进行现场实测，并对采集数据初步分析。

选取2016年5月14日11：00\~17：50时段每 $5 \mathrm { m i n }$ 风速的平均值为样本进行分析，图14为36#格构柱区域平均风速图。

从图14可以看出，该区平均风速较为稳定，所选总时段内平均风速为 $2 . 2 7 ~ \mathrm { m / s }$ ，其中 $5 ~ \mathrm { m i n }$ 平均风速最大为 $4 . 4 ~ \mathrm { m / s }$ 。为分析风速与应力关系，作应力与风速散点图如图15。

6 5 (s·)/区 4 3 2 0 0 10 20 30 40 50 60 70 80 90 t/(5 min)

![](images/cfd9f769311e4031225d48cdd41dbb832febbba8ba1ae98935ceee96cee660aa.jpg)  
图1436#格构柱区域 $5 \mathrm { m i n }$ 平均风速 Fig.14Average wind speed within 5 minutes in the region of 36# lattice column   
图1536#格构柱区域 $5 \mathrm { m i n }$ 平均风速与应力散点图 Fig.15Average wind speed within 5 minutes and stress scatter plot in the region of $3 6 \#$ lattice column

由散点图聚散程度可知，风速与圈梁应力相关性微弱，利用MATLAB对应力和风速数据建立回归模型，得 $R ^ { 2 } = 0 . 1 0 2 4$ ，表明望远镜台址风载荷对圈梁结构应力影响不显著。

# 5结论

基于望远镜主动反射面健康监测系统的多传感器测点与海量监测数据，提出一种数据处理流程和处理方法，对系统采集的温度、应力、风及索力等数据进行处理，在对应力、应变统计分析的基础上，采用多项式回归对数据进行相关性分析，得到温度和应力之间的显式关系，并采用最小二乘法对数据序列进行回归分析，分离温度变化对应力的作用。最后，对温度、索力在索网张拉期间与圈梁结构应力的相关系数进行了计算，分析结果表明：

（1)FAST主动反射面圈梁结构应力与温度具有明显相关性。(2)在索网张拉期间，索力对圈梁结构应力影响较大，应重点监测并着重分析；在索网未张拉期间，温度是影响圈梁结构应力变化的最主要因素。(3)风荷载对圈梁结构应力影响较小。本文通过对 $5 0 0 \mathrm { ~ m ~ }$ 口径球面射电望远镜主动反射面监测系统提出一种数据处理流程及方法，对海量数据进行统计、归纳及相关性分析，得出的结论为望远镜主动反射面系统的运行和维护提供参考，同时，该数据处理方法对类似的结构健康监测系统的研究有一定的借鉴意义。

# 参考文献：

[1] Nan Rendong. Five hundred meter aperture spherical radio telescope（FAST）[J]. Science inChina Series G，2006，49(2):129-148.  
[2] 高原，王启明，薛建兴，等.FAST液压促动器仿真分析与试验研究［J].液压与气动，2015(12): 54-58.Gao Yuan，Wang Qiming，Xue Jianxing，et al. Simulation and experiment of FAST hydraulicactuator［J].Chinese Hydraulics& Pneumatics，2015(12）:54-58.  
[3] 周荣伟，朱丽春，胡金文，等.FAST单元面板面型检测算法研究［J]．天文研究与技术-国家天文台台刊，2012，9(1)：14-20.Zhou Rongwei, Zhu Lichun，Hu Jinwen，et al.Study of a measurement algorithm for the surfaceof a single panel of the reflector of the FAST[J]. Astronomical Research & TechnologyPublications of National Astronomical Observatories of China，2012，9(1) :14-20.  
[4] 孙晓.FAST主动反射面健康监测系统研究［D].北京：中国科学院大学，2015：11-16.  
[5] 丁月蓉.天文数据处理方法［M].江苏：南京大学出版社，1998：117-150.  
[6] 叶川，伍川辉，张嘉怡.计算测试中异常数据剔除方法比较［J].计量与测试技术，2007,34(7) : 26-27.Ye Chuan, ${ { \mathbb { W } } _ { \mathbf { u } } }$ Chuanhui，Zhang Jiayi. Comparision about how to get rid of abnormal data inmetrology & measurement [J]. Metrology & Measurement Technique，2007，34(7）:26-27.  
[7] 盛骤，谢式千，潘承毅.概率论与数理统计［M].北京：高等教育出版社，2008：106-109.  
[8] 万黎，毛炳启.Spearmam 秩相关系数的批量计算［J]．环境保护科学，2008，34（5）：53-$5 5 + 7 2$ ：Wan Li，Mao Bingqi.Batch calculation of Spearman rank correlation coefficient ［J].Environmental Protection Science，2008，34(5）: $5 3 - 5 5 + 7 2$ ：  
[9] 陶悦.新光大桥健康监测数据数理方法与应用研究［D].广州：华南理工大学，2012：59-60.  
[10] 吴明长，王启明，郭永卫，等．大射电望远镜FAST风环境数值模拟研究［J］．天文研究与技术——国家天文台台刊，2012,9(2)： $1 2 1 - 1 2 8 + 1 4 9$ ：Wu Mingchang，Wang Qiming，Guo Yongwei，et al.A numerical study on the wind environmentof the FAST[J]. Astronomical Research & Technology——Publications of National AstronomicalObservatories of China，2012，9（2）: $1 2 1 - 1 2 8 + 1 4 9$ ：

# Research and Application of Data Processing Method of the Health Monitoring System for the Main Active Reflector of FAST

Wang Qingmei1,²， Zhu Ming²，Wang Qiming²，He Ling' (1.KeyLaboratoryofAdvanced ManufacturingTechnology，MinistryofEducation，GuizhouUniversity，Guiyang 55o25,China； 2.National Astronomical Observatories，Chinese Academy of Sciences，Beijing 1Ooo12,China, Email：wangqingmei@nao.cas.cn)

Abstract: Considering the multiple sensor measurement points and the vast monitoring data of the health monitoring system for the main active reflector of FAST，a data processing flow and processing method is introduced.The data collcted by the system，such as temperature，stress，wind speed and the cable force is processed. Correlation analysis of the data is caried out by using polynomial regresson. Based on this method, the effct of temperature variationon the corresponding forces is identified.At the same time，the correlation between stressof the ring beam and cable force and temperature under different conditions is analyzed.The analysis results show that the beam structure stress and temperature are highly correlated，and in the condition when the cable net being unchanged the ring beam stress is mainly affcted by the temperature，while in the condition when the cable netbeing changed the ring beam stressis mainly affcted by cable force.Through the data processing we can identifythe main factors that affect the structureof the interal forces.And the effct of temperature changes on the stress of ring beam is separated effectively，to provide data support for later operation and maintenance.

Key words:FAST engineering；Health monitoring；Data processing；Correlation analysis