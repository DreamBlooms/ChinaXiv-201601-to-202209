# 利用多源数据估算黑河流域总初级生产力

童志辉，熊助国，孙睿²,³，刘向铜，王东东1（1东华理工大学测绘工程学院,江西南昌330013；2北京师范大学遥感科学国家重点实验室,北京100875；3北京市陆表遥感数据产品工程技术研究中心，北京100875)

摘要：总初级生产力(GPP)决定了进入陆地生态系统的初始物质与能量,但由MODISGPP产品获取的GPP在地表覆盖复杂的黑河流域却不足以准确的反映生态系统物质与能量的分布。因此，利用MODIS影像数据、ASTERGDEM数据 $\cdot 3 0 \mathrm { ~ m ~ }$ 分辨率土地利用覆被数据和中国区域地面气象要素驱动数据，驱动VPM模型模拟黑河流域2015年 $5 \sim 1 0$ 月的总初级生产力，并据此揭示黑河流域GPP在生长季的时空格局，时间分辨率为8d,空间分辨率为 $5 0 0 \mathrm { ~ m ~ }$ 。研究结果表明：VPM模型估算结果的精度高于MODISGPP产品，判定系数增长了 $4 5 . 5 \%$ ，总均方根误差降低了 $5 7 . 0 \%$ ；黑河流域生长季累积GPP 总体呈现出中游最高、上游其次、下游最低的显著空间分布梯度格局;全境与局部有植被覆盖区域的日GPP均呈先增加后减少倒U型变化规律,且前者在7月下旬达到最高值;植被覆盖率极低的地表区域生长季内的日GPP在基本稳定中上下波动，稳定值处于 $1 ~ \mathrm { g C } \cdot \mathrm { m } ^ { - 2 } \cdot \mathrm { d } ^ { - 1 }$ 附近。

关键词：VPM模型；多源数据；总初级生产力；时空格局；黑河流域文章编号：

植被总初级生产力（Gross Primary Production,GPP)是指在单位时间和单位面积上，绿色植被通过光合作用所产生的有机碳总量[1],在评估生态系统平衡和植被固碳能力的过程中起重要作用。传统GPP的测量方法主要有箱式法、基于涡度协方差技术的测定法以及稳定同位素测定方法等[2]。近几十年来，遥感技术得到了巨大的发展，其多时空尺度、低成本、高效率、高精度的特点，使区域和全球尺度上估算GPP成为可能[3]。目前，国内外学者开发了许多基于遥感技术的GPP估算模型，如GLO-PEM 模型[4]、VPM模型[5]和BEPS 模型[6]等。其中，光能利用率模型将GPP调控因子以相对简单的方法组合,可直接利用遥感数据[7]，已成为GPP估算的一个重要发展方向。

黑河流域地处一带一路沿线，位于干旱半干旱地区，是典型的内陆河流域，具有3个不同的环境单元,拥有极高的研究价值。近年来，国内外许多学者针对黑河流域的GPP估算展开了大量的研究：WANG等[8]利用EC和VPM模型对黑河流域上游高寒草甸和中游玉米的GPP动态进行了估算；LI等[9]采用REG-PEM模型对黑河流域临泽、盈科和大野口的GPP 进行了估算;闫敏等[10]利用改进的MOD17模型对黑河流域上游的植被GPP进行了估算。然而，目前这些研究多集中于黑河流域中上游，且研究区多为涡动站通量贡献区范围，对于黑河流域下游和流域整体的GPP估算研究则相对较少。因此，本文尝试对黑河流域全境的GPP进行逐像元的估算，并据此探索黑河流域物质与能量的空间分布与时间动态规律。

MOD17产品基于PSN模型与MODIS数据对全球的GPP进行了逐像元的估算，目前，国家、省和地区等大区域尺度的GPP研究多使用MOD17产品，但该产品的GPP估算精度并不高，因此，本文的研究旨在提供一种适用于复杂地表景观与气候情况的高精度大区域尺度GPP估算方法。本文以黑河流域为研究区，利用可公开访问与获取的多源数据驱动VPM模型，估算2015年植被生长季（ $( 5 \sim 1 0$ 月[1])的8d平均日 $G P P$ ,并据此揭示其时空格局,研究成果对于保护脆弱的黑河流域生态环境，指导黑河流域沿线的生态修复工程均具有重要意义。

# 1研究区概况

黑河流域是我国第二大内陆流域，总面积约为$1 . 2 8 9 \times 1 0 ^ { 5 } ~ \mathrm { k m } ^ { 2 }$ ,平均海拔超过 $1 \ 2 0 0 \ \mathrm { m }$ ，主流长度约为 $8 2 1 ~ \mathrm { { k m } ^ { [ 1 1 ] } }$ ,地处西部地区,位于河西走廊中部,其地理位置位于 $3 7 ^ { \circ } 4 1 ^ { \prime } \sim 4 2 ^ { \circ } 4 2 ^ { \prime } \mathrm { N }$ 和 $9 6 ^ { \circ } 4 2 ^ { \prime } \sim$ $1 0 2 ^ { \circ } 0 0 ^ { \prime } \mathrm { E }$ 之间(图1)。黑河流域地形从南到北显著不同，按照不同的自然，生态和气候特征可划分为上游、中游与下游3个区域。上游为祁连山脉至莺落峡峡谷，地貌为高寒草甸覆盖的山地地貌;中游为莺落峡峡谷至正义峡峡谷，地貌为灌溉农业的绿洲地貌；下游为正义峡峡谷至居延海，地貌为戈壁沙漠覆盖荒漠地貌[]。上游、中游和下游地区的年平均气温分别为 $- 3 . 1 \sim 3 . 6 \mathrm { ~ \% ~ } , 7 . 0 \sim 8 . 2 \mathrm { ~ \% ~ }$ 和 $8 . 0 \sim 1 0 . 0$ $\mathcal { \mathrm { C } }$ ,年平均降水量分别为 $3 5 0 \sim 4 5 0 ~ \mathrm { \ m m }$ ， $8 0 \sim 1 2 0 \$ mm 和40\~60 mm[11] ○

![](images/a42ac21c9a423a135d330edb6d5d030aa301cd38956e8636460ae804a7c11c4f.jpg)  
图1黑河流域的地理位置及地形与通量站的空间分布Fig.1Location of Heihe River Basin and the spatialdistribution of terrain and flux station

# 2 多源数据与预处理

# 2.1遥感数据

中分辨率成像光谱仪（MODIS)是NASA发射的Terra和Aqua两颗卫星上的中分辨率高光谱传感器[12]。本文使用的遥感数据为MOD09A1、MOD15A2H和MOD17A2H三种产品，数据获取网址为：http://www.ladsweb.nascom.nasa.gov/。其中，MOD09A1为MODIS前7个波段反射率的8d合成产品;MOD15A2H为8d的地表叶面积指数与光合有效辐射吸收比率产品；MOD17A2H是8d的总初级生产力产品，空间分辨率为 $5 0 0 \mathrm { ~ m ~ }$ ,时间分辨率为8d,涵盖时间为2015年 $5 \sim 1 0$ 月。应用蓝波段（ $4 5 9 \sim 4 7 9 \ \mathrm { n m }$ ）、红波段( $6 2 0 \sim 6 7 0 ~ \mathrm { n m }$ )、近红外波段 $( 8 4 1 \sim 8 7 5 \ \mathrm { n m }$ )和短波红外波段( $1 \ 6 2 8 \sim 1 \ 6 5 2$ nm)的反射率进行增强植被指数 $E W I$ 和陆地水分指数 $L S W I$ 的计算,如公式(1）\~（2)所示[12]

$$
E V I = \frac { 2 . 5 \times ( \rho _ { n i r } - \rho _ { r e d } ) } { \Big [ \rho _ { n i r } + ( 6 \times \rho _ { r e d } - 7 . 5 \times \rho _ { b l u e } ) + 1 \Big ] }
$$

$$
L S W I = \frac { ( \rho _ { n i r } - \rho _ { s w i r } ) } { ( \rho _ { n i r } + \rho _ { s w i r } ) }
$$

式中： $\rho _ { b l u e } \sqrt { \rho _ { r e d } \sqrt { \rho _ { n i r } } }$ 和 $\rho _ { s w i r }$ 分别是蓝波段、红波段、近红外波段和短波红外波段的反射率。本文利用EN-VI软件预处理生成黑河流域生长季的8d合成$E W , L S W I , L A I$ 和 $G P P$ 数据产品。

# 2.2 DEM数据

本文使用的DEM数据为黑河流域ASTERGDEM数据集,空间分辨率为 $3 0 \mathrm { ~ m ~ }$ 。数据获取网址为:http://westdc.westgis.ac. $\mathrm { c n / }$ 。ASTERGDEM是NASA 和METI联合发布的全球数字高程数据产品,覆盖全球99%陆地表面,高程精度为7～14 m[13] 。本文基于ASTERGDEM数据使用聚合法生成$4 8 0 \mathrm { ~ m ~ }$ 和 $0 . 1 ^ { \circ }$ 的DEM。

# 2.3土地利用覆被数据

本文使用的土地利用覆被数据来自黑河流域土地利用覆被数据集[14-16],空间分辨率为 $3 0 \mathrm { ~ m ~ }$ ,数据获取网址为：http：//westdc.westgis.ac. $\mathrm { c n / }$ 。黑河流域土地利用覆被数据集具有较高的总体精度，且细化了农作物信息，还更新了冰、雪等地类信息，时间分辨率为1月，时间跨度为2011—2015年。本文选用2015年7月的地表类型覆盖数据反映黑河流域生长季的土地利用覆被情况，并根据植被功能型对其进一步重分类。考虑到黑河流域的C4作物主要有玉米，而C4草类植物覆盖度很低，遥感分类结果难以识别，因此将农作物分为C3作物与C4作物，将草地统一划分为C3草地，如图2所示。

![](images/8a82fc7e8bb3450b397759c9bd6546b6018d6d714c3169df663208937b04b15a.jpg)  
图22015年7月黑河流域 $3 0 \mathrm { ~ m ~ }$ 空间分辨率土地利用覆被Fig.2Land use and cover with a spatial resolutionof $3 0 \mathrm { ~ m ~ }$ in Heihe River Basin on July 2015

# 2.4 气象数据

本文使用的气象数据来自中国区域地面气象素驱动数据集[17],数据下载地址为:http://westdc.west-gis. ac. $\mathrm { c n / }$ 。中国区域地面气象要素数据集是一套近地面气象与环境要素再分析数据集，由中国科学院青藏高原研究所开发，空间分辨率为 $0 . 1 ^ { \circ }$ ,时间分辨率分为 $^ 3 \mathrm { ~ h ~ }$ 与1d,包含气温、气压、空气比湿、全风速、地面向下短波辐射、地面向下长波辐射和地面降水率7个要素。本文选择 $^ 3 \mathrm { ~ h ~ }$ 分辨率瞬时近地面气温、日平均近地面气温和日平均地面向下短波辐射3个数据集，时间跨度为2015年 $5 \sim 1 0$ 月。

使用日最高和日平均近地面气温的平均值作为日间平均近地面气温，其中取每日 $^ 3 \mathrm { ~ h ~ }$ 分辨率瞬时近地面气温中的最大值作为日最高近地面气温。对于日平均地面向下短波辐射，使用双线性插值算法将空间分辨率从 $0 . 1 ^ { \circ }$ 转换为 $5 0 0 \mathrm { ~ m ~ }$ 。对于日间平均近地面气温，除使用双线性插值算法外，还需要考虑海拔的影响,假设温度的下降率为 $6 . 5 ^ { [ 1 8 ] }$ ,进行高程订正。

# 2.5 地面观测数据

“黑河实验”在2010—2011年完成总体设计与准备，自2012年起开始进入持续观测时期，2012年依次在中游、上游和下游进行了加强试验，全流域的持续观测从2013 年开始至2015 年结束[19]。本文的地面观测数据来自“黑河生态水文遥感试验（Hi-WATER)”，由8个观测站的涡动相关仪测量，测量时间为2015年全年，站点空间分布见图1。涡动相关仪的原始观测数据为 $1 0 ~ \mathrm { H z }$ ，发布的数据集时间步长为 $3 0 ~ \mathrm { m i n }$ ,下载地址为 http://westd-c.westgis.ac.cn。该数据集已经过野点值剔除、延迟时间校正、二次坐标旋转、频率响应修正、超声虚温修正和密度(WPL)修正等步骤的处理[20-21]。对通量数据进行处理与计算，即可获得站点通量贡献区的总初级生产力GPP[12]

# 3 VPM模型计算与评估方法

# 3.1 模型简介

VPM模型是以遥感数据为驱动变量的一种光能利用率模型，该模型基于MODIS遥感数据和涡度相关碳通量观测数据演变产生，考虑植被叶绿素所吸收的光能有效辐射，且FPAR通过 $E V I$ 估算，有效的提高了GPP估算的精确度。

在VPM模型中，模型利用光能利用率（LUE,$\varepsilon _ { \mathrm { g } }$ )和叶绿素吸收的光合有效辐射( $\cdot A P A R _ { \mathrm { c h l } }$ )的乘积来估算总初级生产力 $( G P P )$ ,如公式(3）所示[22]：

$$
G P P = \varepsilon _ { \mathrm { g } } \times A P A R _ { \mathrm { c h l } }
$$

模型利用叶绿素吸收的光合有效辐射比例$( F P A R _ { \mathrm { { c h l } } }$ )来估算 $A P A R _ { \mathrm { { c h l } } }$ 。 $F P A R _ { \mathrm { { c h l } } }$ 由 $E V I$ 的线性函数估计，其中系数 $\alpha$ 设为1.0，如公式（4）\~（5）所示[22] ○

$$
A P A R _ { \mathrm { c h l } } = F P A R _ { \mathrm { c h l } } \times P A R
$$

$$
F P A R = \alpha \times E V I
$$

模型利用最大光能利用率 $\varepsilon _ { \mathrm { m a x } }$ 、温度限制因子$T _ { \mathrm { s c a l a r } }$ 和水分胁迫因子 $\boldsymbol { W } _ { \mathrm { s c a l a r } }$ 的乘积来估算光能利用率,如公式(6)所示[22]：

$$
{ \varepsilon } _ { \mathrm { g } } = { \varepsilon } _ { \mathrm { m a x } } \times T _ { \mathrm { s c a l a r } } \times W _ { \mathrm { s c a l a r } }
$$

在VPM 模型中, $\varepsilon _ { \mathrm { m a x } }$ 是特定生物群落所特有的参数，一般利用土地利用覆被数据通过查找表获取。参考前人研究[22-23],黑河流域植被最大光能利用率$\varepsilon _ { \mathrm { m a x } }$ 如表1所示。

在VPM模型中，温度限制因子 $T _ { \mathrm { s c a l a r } }$ 由陆地生态系统模型(TEM)中使用的公式(7)估算[22]：

$$
T _ { \mathrm { s c a l a r } } = \frac { ( T - T _ { \mathrm { m i n } } ) \times ( T - T _ { \mathrm { m a x } } ) } { \left[ ( T - T _ { \mathrm { m i n } } ) \times ( T - T _ { \mathrm { m a x } } ) \right] - ( T - T _ { \mathrm { o p t } } ) ^ { 2 } }
$$

式中： $T$ 为日间平均近地表气温; $T _ { \mathrm { m i n } } \mathrm { ~ , ~ } T _ { \mathrm { m a x } }$ 和 $T _ { \mathrm { o p t } }$ 分别为植被光合作用最低、最高和最适气温，也可以利用土地利用覆被数据通过查找表获取。参考前人研究[22-23],黑河流域植被光合作用最低、最高和最适气温如表1所示。

# 表1各生物群系的VPM模型参数查找表

Tab.1Reference table of parameters in VPM model for different biomes   

<html><body><table><tr><td>植被类型</td><td>εmax /gC·（mol·APAR）-1</td><td>/C Tmin</td><td>Tmax /C</td><td>/C Topt</td></tr><tr><td>常绿针叶林</td><td>0.42</td><td>-1</td><td>40</td><td>20</td></tr><tr><td>落叶阔叶林</td><td>0.42</td><td>-1</td><td>40</td><td>20</td></tr><tr><td>稀疏灌丛</td><td>0.42</td><td>1</td><td>48</td><td>31</td></tr><tr><td>C3草地</td><td>0.42</td><td>0</td><td>48</td><td>27</td></tr><tr><td>湿地</td><td>0.42</td><td>-1</td><td>40</td><td>20</td></tr><tr><td>C3作物</td><td>0.42</td><td>-1</td><td>48</td><td>30</td></tr><tr><td>C4作物</td><td>0.63</td><td>-1</td><td>48</td><td>30</td></tr><tr><td>人造建筑</td><td>0.42</td><td>0</td><td>48</td><td>27</td></tr></table></body></html>

基于查找表与土地利用覆被数据，生成黑河流域最大光能利用率及光合作用最低、最高和最适气温的空间分布数据，使用聚合法实现空间分辨率由$3 0 \mathrm { ~ m ~ }$ 降低至 $4 8 0 \mathrm { ~ m ~ }$ 。

在VPM模型中,水分胁迫因子 $\boldsymbol { W } _ { \mathrm { s c a l a r } }$ 由 $L S W I$ 估算,如公式(8)所示[22]：

$$
 { W _ { \mathrm { s c a l a r } } } = \frac { 1 + L S W I } { 1 + L S W I _ { \mathrm { m a x } } }
$$

式中： $L S W I _ { \operatorname* { m a x } }$ 为植物生长季单个像元的最大陆地水分指数 $L S W I _ { \circ }$

# 3.2 模型评估

为了评估本文所使用的VPM模型的性能与总初级生产力GPP估算的精度，本文采用了2种方法：直接与地面测量 $G P P$ 相比,与 MODIS GPP产品(MOD17A2H)进行比较。判定系数 $( R ^ { 2 } )$ 和总均方根误差（RMSE）在本文中被用于量化模型估算结果[1]

# 4总初级生产力估算结果与时空格局

# 4.1模型估算结果评估

通常情况下，通量监测塔的测量范围有限，一般为监测塔高度的100 倍[24]。基于涡动相关仪高度,考虑像元和站点测量范围的共配准误差，提取VPM模型与MODISGPP产品估算的站点GPP值。VPM模型估算和地面实测GPP之间的散点图及MODISGPP产品和地面实测GPP之间的散点图如图3所示。

如图3a所示，VPM模型估算的GPP和地面实测 $G P P$ 之间存在较高的相关性，判定系数 $R ^ { 2 }$ 为0.84995，总均方根误差RMSE为 $1 . 8 9 9 \ : 4 \ : \ : \mathrm { g C }$ ：$\mathbf { m } ^ { - 2 } \cdot \mathbf { d } ^ { - 1 }$ ,拟合公式为 $y = 0 . \ 8 0 7 \ 1 1 x \mathrm { ~ - ~ } 0 . \ 1 7 4 \ 3 2$ 。但两者的拟合曲线依旧轻微偏离1:1参考线，这可能是地表植被的空间异质性和像元与站点的共配准误差导致的。单个像元 $3 0 \mathrm { ~ m ~ } \times 3 0 \mathrm { ~ m ~ }$ 范围内的土地利用覆被类别被默认为是单一均匀的，但地表实际情况是不均匀性且复杂的。同时，通量贡献区范围并不是稳定不变的，且像元和站点测量范围的共配准误差是无法完全消除的，这些因素也会对模型估算的精度造成影响。

如图3b所示，MODISGPP产品估算的 $G P P$ 和地面实测GPP之间相关性较弱，判定系数 $\textstyle R ^ { 2 }$ 为0.58396,总均方根误差RMSE为 $4 . 4 1 8 \ : 3 \ : \ : \mathrm { g C }$ ：$\mathbf { m } ^ { - 2 } \cdot \mathbf { d } ^ { - 1 }$ ,拟合公式为 $y = 0 . 2 5 2 \ 5 x + 0 . 2 9 2 \ 8 6$ 。与VPM模型估算的 $G P P$ 不同,MODIS GPP产品估算的 $G P P$ 远低于地面实测 $G P P$ ，拟合曲线显著偏离1:1参考线线，其原因可能有2种：其一，MODISGPP产品所使用的土地利用覆被类别的最大光能利用率 $\varepsilon _ { \mathrm { m a x } }$ 相对较低;其二，MODISGPP算法所使用的土地利用覆被数据MCD12Q1在复杂地表条件下的总体精度不高，存在错分的情况。

因此，本文使用VPM模型估算的总初级生产力精度要高于MODISGPP产品，所用的VPM模型要优于MODISGPP产品所用的MODISPSN模型。

# 4.2黑河流域总初级生产力空间分布

黑河流域生长季累积GPP存在着明显的空间分布格局。沿着上游，中游和下游，从南到北，GPP的分布具有明显的梯度，如图4所示。

GPP在上游的山区南部，中游的绿洲区域和下游的水体附近的河岸区域相对较高。其中，中游以农作物为主要植被覆盖的绿洲区域GPP最高，普遍大于 $8 0 0 \ \mathrm { g C } \cdot \mathrm { m } ^ { - 2 } \cdot \mathrm { d } ^ { - 1 }$ ,上游以草地为主要植被覆盖的山地区域 $G P P$ 次之,大多小于 $6 0 0 \ \mathrm { g C } \cdot \mathrm { m } ^ { - 2 }$ ：$\textrm { d } ^ { - 1 }$ ,下游以沙漠和戈壁为主要土地利用类型的地区最低,除河岸周边外大面积区域均为 $0 \mathrm { ~ g C ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ：$\mathrm { ~ d ~ } ^ { - 1 }$ 。这种空间分布格局主要受黑河流域的温度和

□四道桥站 。胡杨林站 混合林站 $\boldsymbol { \circ }$ 大满站 $0$ 大沙龙站 湿地站 花寨子站 （204 $\ntrianglelefteq$ 荒漠站 1:1参考线 一拟合线 17.00 (a)VPM 4 7.00 (b)MODIS 4 A - A -Pz0dd V -P·z-u. 4 V / 5.25 4 7 12.75 △ V 4A 4 V / 4 / A 品 A V 3.50 W 8.50 会 V △ /d 4 △ 4 8 口 8 4 4 公 △ △ △ 4.25 y=0.80711x-0.17432 1.75 2 y=0.252 5x+0.292 86 △ 8 R²=0.849 95 R2=0.583 96 □ 0.00 V RMES=1.899 4 0.00 A △ RMES=4.4183 0 3 6 9 12 15 1821 0 3 6 9 12 15 18 21 实测GPP/gC·m-2·d-1 实测GPP/gC·m-2·d-1

![](images/35797e532a95310dae7ff2166d4347ff6ea3fc29ed256b5a98a2df587a3a61d0.jpg)  
Fig.3Evaluation of estimated results from VPM model and MODIS GPP products   
图42015年黑河流域生长季累积GPP空间分布 Fig.4Spatial distribution of accumulated $G P P$ in Heihe River Basin during the growth season of 2015

水分条件驱动：上游山地地区，年平均温度为-3.1$\sim 3 . 6 ~ \mathrm { ^ { \circ } C }$ ,降水量为 $5 0 \sim 4 5 0 ~ \mathrm { m m } ^ { [ 1 1 ] }$ ,植被的光合作用主要受低温条件的抑制;中游地区，年平均气温为$7 \sim 8 . 2 ~ \mathrm { \textdegree C }$ ,人工灌溉为农作物生长提供了良好的水分条件[11],环境条件优越，有助于农作物的光合作用；下游地区，年平均降水量仅为 $4 0 \sim 6 0 ~ \mathrm { \ m m }$ ,但年平均潜在蒸发率却达到 $2 \ 3 0 0 \sim 3 \ 7 0 0 \ \mathrm { m m } ^ { [ 1 1 ] }$ ,植被的光合作用因缺水而受到抑制。另外，这种空间分布格局还受土地利用覆被情况的影响：由于中游绿洲区域种植有大量C4农作物（玉米），导致该区域最大光能利用率相对较高，因此总初级生产力远高于上游与下游地区。

# 4.3黑河流域总初级生产力时间动态

首先，研究黑河流域全境植被覆盖区域（不包括裸地、积雪与冰)的平均日GPP的时间动态规律。以植被叶面积指数表征植被生长特征，如图5所示。黑河流域全境植被覆盖区域的平均日GPP时间变化趋势与黑河流域植被生长特征基本一致。平均日GPP最初随着时间的推移而增加，并在7月20日\~7月27日 $( 2 0 1 \sim 2 0 9 \mathrm { ~ d } )$ 达到最大值后随着时间的推移而减少。该变化趋势主要是受气温、水分、太阳辐射和植被长势的影响而导致的。黑河流域的气温、降水量与河流径流量在7月与8月间达到一年中的最高值[25],植被叶面积在7月间达到巅峰值,与此同时，太阳辐射在6月达到最大值后开始逐渐降低，这些因素的综合影响最终导致了黑河流域全境植被覆盖区域的平均日GPP的倒U型变化规律。

![](images/f6c5473b3ff86d2f40fb368e9dc7d860ad5df152303fa1e44923c0b0793f8a74.jpg)  
图3VPM模型与MODISGPP产品的估算结果评估   
图5植被覆盖区域的平均日 $G P P$ 与8d合成LAI时间动态  
Fig.5Temporal dynamics of averaged daily $G P P$ and 8-day synthetic $L A I$ in vegetation covered areas

![](images/c648db814b1dba899236da8361a37005f43567bd7889f6abbdfba993afb4accb.jpg)  
图6黑河流域8站点的模拟和实测GPP时间动态  
Fig.6Temporal dynamics of simulated and measured GPP at 8 sites in Heihe River Basin

其次，揭示观测站站点GPP的时间动态规律，如图6所示。除花寨子站与荒漠站外，所有观测站的日GPP也呈倒U性变化规律，与黑河流域全境植被覆盖区域的变化规律与原因基本相同。而对于花寨子站与荒漠站，由于其下垫面为荒漠与沙漠，植被覆盖率极低，因此生长季的GPP总体趋势维持在 $1 \mathrm { \textrm { g C } } \cdot \mathrm { \textrm { m } } ^ { - 2 } \cdot \mathrm { \textrm { d } } ^ { - 1 }$ 上下波动,季节变化不大。然而，在VPM模型中，对于低植被覆盖的裸地,由于其最大光能利用率通常取值为 $0 ~ \mathrm { g C }$ ·0 $\mathrm { \bf \Phi } _ { \mathrm { m o l } } \cdot \mathrm { \bf \Phi } _ { \mathrm { A P A R } } ) \ ^ { - 1 }$ ，因此GPP的估算值也往往等于$0 \mathrm { \ g C \cdot \ m } ^ { - 2 } \mathrm { \ \cdot \ d } ^ { - 1 }$ ,故模拟结果不能反映低植被覆盖地表区域的 $G P P$ 时间动态变化规律。目前，针对低植被覆盖地表区域的最大光能利用率的研究依旧存在较大不足。WANG等[26]曾提出了利用最大光能利用率与增强植被指数的经验公式计算最大光能利用率的方法，但该方法估算的最大光能利用率误差较大，且普适性差。因此，今后对低植被覆盖地表区域的最大光能利用率展开进一步的深入研究是有必要且必须的。

# 5讨论

黑河流域地处西北农牧过渡区，气候类型为温带大陆性气候，植被生态系统复杂多变，常绿针叶林、落叶阔叶林、高寒草甸和温带草地等地表覆盖错落分布。研究表明，VPM在常绿针叶林、热带常绿林、落叶阔叶林、农田、高山草甸和温带草原等生产系统中均具有良好的模拟效果[24]（ $R ^ { 2 } = { }$ $0 . 6 4 \sim 0 . 9 4 \$ ），因此VPM模型在黑河流域具有较好的适用性。本文利用VPM模型模拟的 $G P P$ 与通量站的观测数据进行比较分析( $R ^ { 2 } = 0 . 8 5$ )，其结果也表明了VPM模型十分适合用于在黑河流域GPP模拟。

使用VPM模型进行全球与区域尺度的GPP模拟,前人多使用 MODIS 产品中的土地利用数据[23]与气象站点插值而成的气象数据[26],然而前者精度在具有复杂地表景观的区域内较差，后者精度受气象站点的分布密度影响较大。有研究表明，土地利用数据对地表情况的反映随着分辨率的提高而更加详细准确["],通过陆面融合资料可获取高质量与格点化的气象要素数据[17]。黑河流域地表覆盖类型复杂，且气象站点分布较东南沿海相对稀疏，使用高分辨率的土地利用数据和陆面融合资料可以大大提高GPP的估算精度。

# 6结论

本文以模拟黑河流域2015年植被生长季的GPP 为例,时间与空间分辨率分别设为8d与 $5 0 0 \mathrm { ~ m ~ }$ 使用MODIS影像数据、ASTERGDEM数据 $\ 、 3 0 \mathrm { ~ m ~ }$ 分辨率土地利用覆被数据和中国区域地面气象要素驱动数据，驱动VPM模型进行GPP估算，并以此方法为基础，揭示黑河流域GPP的空间分布与时间动态规律。研究结果表明：

（1）本文VPM模型估算的结果优于MODISGPP产品的预测精度，以大沙龙站、大满站、花寨子站、荒漠站、混合林站、胡杨林站、四道桥站和湿地站的实测通量数据验证，其中，后者的判定系数仅为0.58396,总均方根误差达 $4 . 4 1 8 3 \mathrm { \ g C \cdot m } ^ { - 2 } \cdot \mathrm { d } ^ { - 1 }$ 而前者的判断系数达0.84995，提高了 $4 5 . 5 \%$ ，总均方根误差仅达 $1 . 8 9 9 \ 4 \ \mathrm { g C } \cdot \mathrm { ~ m ~ } ^ { - 2 } \cdot \mathrm { ~ d ~ } ^ { - 1 }$ ，降低了$5 7 . 0 \%$ 0

(2)生长季内，黑河流域上游，中游和下游的GPP存在着明显的空间分布梯度，主要归因于黑河流域的土地利用覆被情况和温度与水分环境因素，其中，中游地区的水热条件最佳，光能利用率高，生长季 $G P P$ 最高,普遍大于 $8 0 0 \ \mathrm { g C } \cdot \mathrm { ~ m ~ } ^ { - 2 } \cdot \mathrm { ~ d ~ } ^ { - 1 }$ ;上游地区的光合作用受低温抑制，生长季 $G P P$ 相对较低,大多小于 $6 0 0 \ \mathrm { g C } \cdot \mathrm { ~ m ~ } ^ { - 2 } \cdot \mathrm { ~ d ~ } ^ { - 1 }$ ;下游地区因干旱影响而地表缺乏植被覆盖，生长季 $G P P$ 最低，除河岸周边外大面积区域均为 $0 \mathrm { \ g C } \cdot \mathrm { m } ^ { - 2 } \cdot \mathrm { d } ^ { - 1 }$ ○

(3)生长季内黑河流域全境与局部有植被覆盖的区域（不包括大片沙漠戈壁)的日 $G P P$ 呈现先增加后减少的倒U型变化趋势，该变化趋势主要是受植被长势、气温、水分和太阳辐射的影响而导致的，其中，全境植被覆盖区域的日GPP在7月下旬（7月20日\~7月27日）达到最高值，最高值约为 $5 . 6 5 ~ \mathrm { g C } \cdot \mathrm { ~ m ~ } ^ { - 2 } \cdot \mathrm { ~ d ~ } ^ { - 1 }$ ,与植被生长特征基本保持一致。

(4)生长季内黑河流域境内的沙漠、荒漠、裸地等植被覆盖率极低的土地日 $G P P$ 值在基本稳定中上下波动,稳定值大致处于 $1 \mathrm { \bf ~ g C } \cdot \mathrm { \bf ~ m } ^ { - 2 } \cdot \mathrm { \bf ~ d } ^ { - 1 }$ 附近。光能利用率模型在估算该类土地利用类型时，常常默认为 $0 ~ \mathrm { g C } \cdot \left( \mathrm { m o l } \cdot \mathrm { A P A R } \right) ^ { - 1 }$ ,不能反应其时间动态变化。

本文成功的估算了2015年黑河流域的总初级生产力，然而研究尚有不足之处存在：（1）研究时间段较短，不能全面的揭示研究区GPP的年际时空变化；（2）空间分辨率较低，空间异质性对估算精度的影响依旧较大；（3）仅对C3/C4植被的最大光能利用率进行区分，未能针对不同的生物群落采用不同的最大光能利用率。因此今后有必要进一步扩大研究时间段，提高空间分辨率，研究最大光能利用率与生物群落的联系，从而对研究方法作进一步改进。

参考文献（References）   
[1]高艳妮,于贵瑞,张黎,等.中国陆地生态系统净初级生产力变 化特征—基于过程模型和遥感模型的评估结果[J].地理科 学进展,2012,31（1）:109-117.[GAO Yanni,YU Guirui, ZHANG Li,et al.The changes of net primary productivity in Chinese terrestrial ecosystem:Based on process and parameter models [J].Progress in Geography,2012,31(1）:109 -117.]   
[2］严燕儿.基于遥感模型和地面观测的河口湿地碳通量研究 [D].上海:复旦大学,2009.[YAN Yan'er.Carbon flux in an enstuarine wetland estimated by remote sensing model and groundbased observations[D]. Shanghai;Fudan University,2009.]   
[3]TURNER D P,RITTE W D,COHEN W B,et al. Scaling gross primary production（GPP）over boreal and deciduous forest landscapes in support of MODAS GPP product validation[J].Remote Sensing of Environment,2003,88(3）:256-270.   
[4]PRINCE S D,GOWARD S N. Global primary production; A remote sensing approach[J]. Journal of Biogeography,1995,22:815- 835.   
[5]XIAO X M,ZHANG Q Y,BRASWELL B,et al. Modeling gross primary production of temperate deciduous broadleaf forest using satelite images and climate data[J].Remote Sensing of Environment,2004,91(2):256-270.   
[6]LIU J,CHEN JM,CIHLARJ,et al.A process-based boreal ecosystem productivity simulator using remote sensing inputs[J]. Remote Sensing of Environment,1997,62(2）:158 -175.   
[7］孙睿,朱启疆.陆地植被净第一性生产力的研究[J].应用生态 学报,1999,10(6）:757-760.[SUN Rui,ZHU Qijiang.Net primary productivity of terrestrial vegetation；A review on related rsearches[J].Chinese Journal of Applied Ecology,1999,10（6）: 757 -760.]   
[8]WANG X,MA M,HUANG G,et al.Vegetation primary production estimation at maize and alpine meadow over the Heihe River Basin,China[J].International Journal of Applied Earth Observation and Geoinformation,2012,17:94 -101.   
[9]LI S,XIAO J,XU W,et al. Modeling gross primary production in the Heihe River Basin and uncertainty analysis[J]. International Journal of Remote Sensing,2012,33(3）:836-847.   
[10］闫敏,李增元,田昕,等.黑河上游植被总初级生产力遥感估算 及其对气候变化的响应[J].植物生态学报,2016,40（1)：1- 12.[YAN Min,LI Zengyuan,TIAN Xin,et al. Remote sensing estimation of gross primary productivity and its response to climate change in the upstream of Heihe River Basin[J].Journal of Plant Ecology,2016,40(1):1 -12.]   
[11]CUI TX,WANG Y J,SUN R,et al.Estimating vegetation primary production in the Heihe River Basin of china with multi-source and multi-scale data[J].PloS One,2016,11（4）:e0153971,doi:10. 1371/journal. pone. 0153971.   
[12］王旭峰,马明国,李新,等.遥感GPP 模型在高寒草甸的应用比 较[J].遥感学报,2012,16(4）:751-763.[WANG Xufeng,MA Mingguo,LI Xin,et al. Comparison of remote sensing based GPP models at an alpine meadow site[J]. Journal of Remote Sensing, 2012,16(4):751 -763.]   
[13]HIRANO A,WELCH R,LANG H. Mapping from ASTER stereo image data：DEM validation and accuracy assessment[J]. ISPRS Journal of Photogrammetry and Remote Sensing,2003,57(5）:356 -370.   
[14]ZHONGB,YANG AX,NIE AH,etal.Finer resolution land-cover mapping using multiple classifiers and multisource remotely sensed data in the Heihe River Basin[J].IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing,2O15,8（10）: 4973 - 4992.   
[15］仲波，马鹏,聂爱华,等.基于时间序列HJ-1/CCD 数据的土地 覆盖分类方法[J].中国科学：地球科学,2014,44(5)：967- 977.[ZHONG Bo,MA Peng,NIE Aihua,et al.Land cover mapping using time series HJ-1/CCD data[J]. Science China：Earth Sciences,2014,44(5) :967 -977.]   
[16]LI X,LIU S M,XIAO Q,et al.A multiscale dataset for understanding complex ecohydrological processes in a heterogeneous oasis system[J].Scientific Data,2017,4:170083,doi:10.1038/ sdata. 2017.83.   
[17]CHEN Y Y,YANG K,HE J,et al. Improving land surface temperature modeling for dry land of China[J].Journal of Geophysical Research：Atmospheres，2011，116（D20）：doi：10．1029/ 2011JD015921.   
[18］翁笃鸣,孙治安.我国山地气温直减率的初步研究[J].地理研 究,1984,3（2）:24-34.[WENG Duming,SUN Zhian.A preliminary study of the lapse rate of surface air temperature over mountainous regions of China[J].Geographical Research,1984,3（2）: 24 -34.]   
[19]LI X,CHENG G D,LIU S M,et al.Heihe Watershed Allied Telemetry Experimental Research（HiWATER）:Scientific objectives and experimental design[J].Bulletin of the American Meteorlogical Society,2013,94(8）:1145-1160.   
[20]LIU S M,XU Z W,WANG W Z,et al. A comparison of eddy-covariance and large aperture scintilla meter measurements with respect to the energy balance closure problem[J].Hydrology and Earth System Sciences,2011,15(4) :1291-1306.   
[21］张蕾.张掖绿洲灌区不同下垫面碳通量研究[D].北京;北京 师范大学,2015.[ZHANG Lei. Study on carbon flux of different underlying surfaces in Zhangye oasis area[D]. Beijing: Beijing Normal University,2015.]   
[22] ZHANG Y,XIAO X M,JIN C,et al. Consistency between sun-induced chlorophyll fluorescence and gross primary production of vegetation in north America[J].Remote Sensing of Environment, 2016,183:154 -169.   
[23]ZHANG Y,XIAO X M,WU XC,et al.A global moderate resolution dataset of gross primary production of vegetation for 2000 - 2016[J].Scientific Data,2017,4:170165,doi:10.1038/sdata. 2017.165.   
[24］郭海强.长江河口湿地碳通量的地面监测及遥感模拟研究 [D].上海:复旦大学,2010.[GUO Haiqiang.Carbon fluxes over an estuarine wetland：In situ measurement and modeling[D]. Shanghai:Fudan University,2010.]   
[25］甄玉龙.黑河径流演变分析及探讨[J].甘肃科技,2017,33 (10）:49-50.[ZHEN Yulong.Analysis and discussion on evolution of Heihe River runof[J]. Gansu Science and Technology, 2017,33(10) :49 -50.]   
[26]WANG HS,JIAG S,FU CB,et al.Deriving maximal light use efficiency from coordinated flux measurements and satelite data for regional gross primary production modeling[J].Remote Sensing of Environment,2010,114(10）:2248-2258.

# Estimating gross primary production in the Heihe River Basin from multiple data sources

TONG Zhi-hui1， XIONG Zhu-guo’， SUN Rui23， LIU Xiang-tong'， WANG Dong-dong' (1College of Surveying and Mapping,East China University of Technology,Nanchang 330013,Jiangxi,China; 2State Key Laboratory of Remote Sensing Science,Beijing Normal University,Beijing 100875,China; 3Beijing Enginering Research Center ofGlobal Land Remote Sensing Product,Beijing 10o875,China）

Abstract：The initial mater and energy entering terrestrial ecosystem are determined by the gross primary productivity（GPP).Hovexer,the $G P P$ measurements acquired by the MODIS $G P P$ products are not sufficient to accuratelyreflectthedistribution of ecosystem materand energy inthe Heihe River Basin in Qinghai Province,Gansu Province and Inner Mongolia,China with complex surface coverage.Therefore,based on MODIS image data,ASTER GDEM data,land cover data with a spatial resolution of $3 0 \mathrm { ~ m ~ }$ ,and the China Meteorological Forcing Dataset,the VPM model was derived to simulate the grossprimary productivity of the Heihe River Basin from May to October 2015 with a spatial resolution of $5 0 0 \mathrm { ~ m ~ }$ and a temporal resolution of 8 days.Based on simulations using the VPM model,the spatial and temporal patterns of $G P P$ in the Heihe River Basin during the growing season were determined.The results of the study indicate that the accuracyof the results estimated using the VPM model was higher than that of the MODIS GPP products. The judgment coefficient increased by $4 5 . 5 \%$ ,while the total root mean square error reduced by $5 7 . 0 \%$ . The study results also demonstrate that the $G P P$ accumulation during the growing season inthe Heihe River Basin exhibited a significant spatial distribution gradient patern,whichcan be described as the highest in the middle reaches,the next highest in the upper reaches,and the lowest in the lower reaches.In addition,the daily $G P P$ of the whole and partial vegetation-covered areas in the Heihe River Basin first increased and then decreased in an inverted U-shape.The daily $G P P$ values of all vegetation-covered areas reached the maximum in late July. The daily $G P P$ values of those ground areas with very low vegetation coverage fluctuated up and down in their basic stability,while the stable value was approximately $1 ~ \mathrm { g C } \cdot \mathrm { m } ^ { - 1 } \cdot \mathrm { d } ^ { - 1 }$ ：

Key words:VPM model；multi-source data； gross primary productivity；spatial and temporal paterns；Heihe River Basin