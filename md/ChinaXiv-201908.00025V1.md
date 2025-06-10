# 近 $\mathbf { 1 4 \ a }$ 新疆南疆绿洲地区地表蒸散与干旱的时空变化特征研究

高瑜莲}，柳锦宝'，柳维扬²，于静},³，刘志红'（1成都信息工程大学,四川 成都610225；2 塔里木大学植物科学学院,新疆 阿拉尔 843300;3内蒙古自治区通辽市气象局,内蒙古通辽028000)

摘要：利用2001—2014年MOD16 蒸散产品数据、MOD13植被NDVI数据以及常规气象资料，基于植被指数、地表净辐射、气温优化改进混合型线性双源遥感蒸散模型，拟合地表蒸散分析实际蒸散(ET)、潜在蒸散(PET)时空动态变化特征,结合气象站实测蒸发血数据验证MOD16数据在绿洲地区的适用性。进一步定义蒸散干旱指数(EDI)并计算△EDI进行研究区干旱特征分析，为大面积特殊地形蒸散估算研究和干旱监测提供一定依据。结果表明：(1）MOD16产品数据与研究区实测蒸发皿数据的相关性很好，通过0.01显著性检验，基于MOD16数据估算南疆绿洲地区蒸散量检验可行。（2）2001—2014年均蒸散量总体变化不大，四季差异明显,ET与PET空间变化趋势相反;ET、PET年均差值较大，绿洲地区地表缺水情况严重。（3）EDI指数绿洲地区年均值总体偏大，△EDI对旱情的反映和干旱程度的判断比较可靠。

关键词：新疆南疆；绿洲；地表蒸散；蒸散干旱指数(EDI)；时空变化特征文章编号： 1000-6060(2019)04-0830-08(0830\~0837)

近年来全球的气候变化持续性的对自然界的循环系统产生影响，由于明显的气温升高趋势全球的水循环系统出现了明显的变化，水资源供需的不平衡变化显著，导致全球范围内的干湿状况以及水资源分布不均衡的趋势增加[1]。蒸散是干旱地区水资源消耗的主要方式[2],也是地表干旱信息的重要表征参量[3]。蒸散分为潜在蒸散和实际蒸散,蒸散的估算模拟过程十分复杂，需要多学科知识的参与才能够实现[4]。地表蒸散是联系多个循环过程的重要纽带，也是十分关键的陆面过程之一，在监测地表水分和模拟地表能量平衡方面有丰富的实用价值。结合气象相关因素对地表干湿状况的研究缺乏定量的探讨，因此，气象因素中的各个因子对于干湿状况的影响程度没有准确的把握[5]。有研究表明,用遥感资料计算地面水分蒸发和能量是十分重要的[6-12]。遥感数据具有多种时空分辨率,有许多研究通过选择不同尺度的遥感数据综合解决蒸散反演计算精度问题，另一方面利用卫星遥感数据针对大区域模拟计算地表蒸散，但这些研究的区域均为较大范围[13],针对性的小区域或者特殊地形的蒸散量估算少有涉及。由于地表蒸散受气候影响与气候密切相关，气候变化和人类活动影响着水循环过程进而改变着地表蒸散，地表蒸散同时反作用影响气候变化,对气候和环境进行反馈[7]。干旱受气候因素的影响比较强，其中降水的变化对干旱有直接的影响[1]。利用计算模型来估算蒸散量可以有效解决一些地区气象站点较少，气象资料序列较短的弊端[8]。结合研究区气象因子以及气象干旱指数时空分布特征并对其变化趋势进行合理估测,对于目前气候变化背景下的水资源管理以及水旱灾害研究有重要意义[9]

新疆地处亚欧大陆内部，垂直海拔高度落差较大，降水空间分布不均匀，植被覆盖空间异质性高[10]。由于复杂的地理环境、活跃的人类活动,定量准确地估算新疆地区的蒸散并不容易[2]。由于不确定性客观存在，加之干旱成因异常复杂，因此选择合适定量化指标来有效表征干旱的一系列特征是干旱研究的基础[1]。利用 MODIS 产品数据以及气象站点数据结合Hargreaves 公式、线性双源遥感蒸散模型和EDI干旱指数，研究新疆南疆绿洲地区干旱分布特点，为大面积特殊地形蒸散估算研究和干旱监测提供一定依据。

# 1资料与方法

# 1.1 研究区域与数据源

针对新疆南疆绿洲地区，使用的数据资料有：（1）遥感数据。蒸散量数据为2001—2014年期间的 $\mathrm { M O D } 1 6 - E T , P E T$ 数据，空间分辨率为 $1 ~ \mathrm { k m }$ 。根据数据说明进行异常值、无效值剔除，并通过Arc-GIS 提供的投影转换工具和拼接、裁剪工具,对遥感图像进行操作获得新疆南疆的 $E T$ 和PET遥感数据。（2）NDVI数据。即空间分辨率为 $1 ~ \mathrm { k m }$ 的MO-DIS $N D V I 6 \mathrm { ~ d ~ }$ 合成产品MOD13A2。新疆南疆地区需要多幅影像才能完全覆盖，通过ArcGIS拼接、裁剪和投影转换提取新疆南疆地区所需的NDVI数据。（3）气象资料。来自中国气象数据网地面气候资料月值数据集，使用新疆地区55个站点的气温、降雨、水汽压等月值资料作为计算南疆地区蒸散量的输入参数。

# 1.2 研究方法

# 1.2.1线性双源遥感蒸散模型的改进

（1）模型改进和优化思路

模拟新疆南疆绿洲地区地表蒸散的过程中，跟随 NISHIDA等[12]利用遥感数据构建蒸散模型的思路。在蒸散模型的影响因子中追加考虑植被覆盖度（NDVI)，利用植被覆盖度在研究区的表现形式，将地表蒸散考虑为裸土蒸发以及植被蒸腾的总和：

$$
f _ { v } = \frac { N D V I - N D V I _ { \operatorname* { m i n } } } { N D V I _ { \operatorname* { m a x } } - N D V I _ { \operatorname* { m i n } } }
$$

$$
E T _ { s } = \frac { a _ { 1 } R _ { n } } { T _ { \operatorname* { m a x } } - T _ { \operatorname* { m i n } } }
$$

式(2)中： $E T _ { s }$ 表示土壤蒸发 $\langle \textrm { W } \cdot \textrm { m } ^ { - 2 }$ ）， $N D V I _ { \operatorname* { m a x } }$ 是植被覆盖较完整情况下的值; $N D V I _ { \operatorname* { m i n } }$ 是地表为裸土情况下的值。

蒸散比（EvapotranspirationFraction, $E F )$ 能够直

观的体现研究区的水分消耗情况，在数值上等于（实际蒸散量有效能量）。

$$
E F = { \frac { E T } { Q } } = { \frac { E T } { E T + H } } + { \frac { E T } { R _ { n } - G } }
$$

$$
Q = E T + H = R _ { n } - G
$$

式（3）、（4)中： $E F$ 为蒸散比, $Q$ 为有效能量( $\propto \cdot$ $\mathrm { ~ m ~ } ^ { - 2 }$ ）， $H$ 为显热通量 $\left( \mathrm {  ~ W ~ } \cdot \mathrm {  ~ m ~ } ^ { - 2 } \mathrm {  ~ \Omega ~ } \right)$ ),地表净辐射为 $\boldsymbol { R } _ { n }$ $( \mathbf { M } \mathbf { J } \cdot \mathbf { m } ^ { - 2 }$ )，土壤向下热通量为 $G _ { \bullet }$ □

土壤向下热通量 $\textit { G }$ 一般情况下值比较小，本研究出于减少计算复杂程度的目的，规定 $G / R _ { n }$ 为常数 $\mathbf { \alpha } _ { a }$ ，公式(3)可表达为：

$$
E T = \left( 1 - a \right) \times E F \times R _ { n }
$$

同时，土壤和植被能够建立下式关联：

$$
E T _ { s } = Q _ { s } E F _ { s }
$$

$$
\mathit { E T } _ { \scriptscriptstyle V } = Q _ { \scriptscriptstyle V } E F _ { \scriptscriptstyle V }
$$

$$
Q = F _ { \scriptscriptstyle V } Q _ { \scriptscriptstyle V } + ( 1 - F _ { \scriptscriptstyle V } ) Q _ { s }
$$

式（6）、（7）、（8）中： $E T _ { _ V }$ 和 $E T _ { s }$ 分别是植被蒸腾（2号 $\left( \mathbb { W } \cdot \mathbf { m } ^ { - 2 } \right)$ )和土壤蒸发 $\left( \mathbb { W } \cdot \mathbf { m } ^ { - 2 } \right.$ ）， $Q _ { s }$ 和 $Q _ { \scriptscriptstyle V }$ 分别为为土壤有效能量(J)和植被有效能量（J）， ${ E F } _ { s }$ 和$E F _ { _ V }$ 分别为土壤蒸散比和植被蒸散比。

# (2）土壤蒸散模型的改进

NISHIDA等[12]通过一系列分析研究发现,土壤蒸发和温差呈现出反比例关系。结合(3)式能够进一步发现裸土地区的 $E T$ 与 $\textstyle { \mathcal { R } } _ { n }$ (净辐射)和早晚温度差关系密切。为了提高模型的适用性以及降低蒸散计算的复杂程度,利用 $\textstyle { \mathcal { R } } _ { n }$ 和早晚温度差( $T _ { \mathrm { m a x } } ~ \mathrm { - }$ $T _ { \mathrm { m i n } }$ )简化蒸散计算公式,并且增加经验性系数：

$$
E T _ { s } = \frac { a _ { 1 } R _ { n } } { T _ { \operatorname* { m a x } } - T _ { \operatorname* { m i n } } }
$$

式(9)中：温差数据是南疆地区昼夜空气温差。由于利用遥感数据获取陆表温度数据会受到云覆盖等观测方面的影响,导致陆地表面温度数据不够全面完整。故本研究选用较容易获取的气象站点空气温度数据代替陆表温度完成计算，进一步根据研究进行整理分析利用。

# （3）植被蒸散模型的改进

植被蒸腾是蒸散的重要组成部分，本研究对于植被蒸腾计算的简化主要是加入两个经验系数 $a _ { 2 }$ 和 $a _ { 3 }$ 。对植被蒸腾来说，地表净辐射是产生影响的

主要因素,而空气温度 $( T )$ 和空气早晚温差( $T _ { \mathrm { m a x } }$ 一$T _ { \mathrm { m i n } }$ )也是对植被蒸腾函数带来影响的重要参数。结合经验系数获得简化后方程如下：

$$
E T _ { \scriptscriptstyle V } = a _ { 2 } R _ { \scriptscriptstyle n } T + \frac { a _ { 3 } R _ { \scriptscriptstyle n } } { T _ { \scriptscriptstyle \operatorname* { m a x } } - T _ { \scriptscriptstyle \operatorname* { m i n } } }
$$

（4）混合型线性双源遥感蒸散模型在南疆绿洲地区的改进

将植被蒸腾和裸土地表蒸发进行结合时，考虑到地表净辐射 $\boldsymbol { R } _ { n }$ 对二者的蒸散量都有较大的影响，于是本研究对地表蒸散增加订正项 ${ a _ { 0 } R _ { n } }$ 加入模型，此时，结合公式(9)和(10)将蒸散方程整理为：

$$
\begin{array} { c } { E T = ( { 1 - f _ { V } } ) \frac { a _ { 2 } R _ { n } } { T _ { \mathrm { m a x } } - T _ { \mathrm { m i n } } } + } \\ { f _ { V } \left( \ a _ { 2 } R _ { n } T + \frac { a _ { 3 } R _ { n } } { T _ { \mathrm { m a x } } - T _ { \mathrm { m i n } } } \right) + a _ { 0 } R _ { n } } \end{array}
$$

在研究中，当 $N D W$ 植被覆盖为较完整覆盖情况时，$f _ { v } = 1$ ;反之，当NDVI植被覆盖度表示裸土地区植被覆盖情况时 $\mathcal { I } _ { v } = 0$ 。因此，利用植被覆盖情况（ $N D -$ $\smash { \boldsymbol { V } \boldsymbol { I } _ { \perp } ^ { \star } }$ )将遥感蒸散模型最终简化为以下形式：

$$
E T = R _ { \mathrm { { n } } } \left( { b } _ { \mathrm { { 0 } } } + { b } _ { \mathrm { { 1 } } } N D V I \times T + \right.
$$

$$
\frac { b _ { 2 } N D V I } { T _ { \operatorname* { m a x } } - T _ { \operatorname* { m i n } } } + \frac { b _ { 3 } } { T _ { \operatorname* { m a x } } - T _ { \operatorname* { m i n } } } \bigg )
$$

式中： $E T$ 表示地表蒸散 $\left( \mathrm { ~ W ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 } \right.$ ）， $\boldsymbol { R } _ { n }$ 是地表净辐射 $\mathrm { ( ~ W J ~ } \cdot \mathrm { ~ m ~ } ^ { - 2 }$ ） $N D V I$ 为归一化植被指数， $T _ { \mathrm { m a x } }$ 和 $T _ { \mathrm { m i n } }$ 分别为最高空气温度 $( \mathrm { ‰ }$ 和最低空气温度 $( \mathrm { ‰ }$ ，$b _ { 0 } \ 、 b _ { 1 } 、 b _ { 2 } 、 b _ { 3 }$ 均为回归系数。

1.2.2 潜在蒸散模型利用Hargreaves 公式来进行新疆南疆绿洲地区的潜在蒸散的估算，公式中涉及到的参数为地理纬度、空气温度、空气温差。Har-greaves公式表达形式如下：

$$
P E T = 0 . \ 0 0 2 \ 3 R _ { n } \left( { T _ { \mathrm { m e a n } } + 1 7 . 8 } \right) \sqrt { T _ { \mathrm { m a x } } - T _ { \mathrm { m i n } } }
$$

式中： ${ \mathit { P E T } }$ 表示地表潜在蒸散 $\left( \mathbb { W } \cdot \mathbf { m } ^ { - 2 } \right.$ ）， $T _ { \mathrm { m e a n } }$ 表示空气均温 $( \mathcal { C } ) , T _ { \mathrm { m a x } }$ 和 $T _ { \mathrm { m i n } }$ 表示空气最高温度 $( \mathrm { ‰ }$ 和空气最低温度 $( \mathrm { ‰ }$ ，表示太阳辐射 $( \mathbf { M } \mathbf { J } \cdot \mathbf { m } ^ { - 2 }$ ）。1.2.3定义干旱指数为了反映出土壤水分对南疆绿洲地区地表干湿程度的影响，定义蒸散干旱指数（Evaporative Drought Index, $E D I )$ ），公式如下：

$$
E D I = 1 \ - { \frac { E T } { P E T } }
$$

式中： $E T$ 和PET分别由式(12)和式(13)得到。理论上， $E D I$ 的取值范围在0\~1之间。地表干旱程度越重，地表水分缺失越严重，实际蒸散与潜在蒸散的比值越小，EDI值越大。反之，土壤水分越充足，EDI值越低。

# 2结果与分析

# 2.1蒸散量时间变化特征分析

新疆南疆绿洲地区在2001—2014年期间实际蒸散量 $E T$ 年均 $2 4 8 . 5 9 \ \mathrm { m m }$ ,潜在蒸散量PET年均$8 8 2 . 2 0 ~ \mathrm { m m }$ 。由图1a 可知,2001—2014 年间蒸散量变化波动较小，研究时限内 $E T$ 在 $2 0 1 . 9 2 \sim 2 8 8 . 7 5$ mm 范围内变化，总体呈现轻微上升趋势;PET在$8 5 0 . 2 9 \sim 9 7 1 . 6 4 ~ \mathrm { m m }$ 范围内变化，总体呈现轻微下降趋势。比较绿洲地区年蒸散量多年均值，实际蒸散量 $E T$ 在 2012 年最高,2007—2009 年间稍低；潜在蒸散量PET在 2004 年最高,2003 年、2010 年偏低。 $E T$ 和PET相差较大， $E T$ 是地表实际蒸散量，PET是水分供应充足情况下的蒸腾量，新疆南疆绿洲地区的ET和PET差距较大，说明地表整体缺水情况严重。

南疆绿洲地区年内 $E T$ 轻微波动变化，图1b反映出 $E T$ 在7月最高 $3 1 . 1 2 \ \mathrm { m m } , 1 \sim 4$ 月和 $7 \sim 1 0$ 月实际蒸散量下降缓慢， $4 \sim 7$ 月和 $1 0 \sim 1 2$ 月不断增加;年内 $P E T$ 呈单峰型变化,潜在蒸散量6月最大$1 1 6 . 6 6 ~ \mathrm { m m } , 1 \sim 6$ 月潜在蒸散量缓慢增加，6\~12月快速下降； $E T$ 和PET差值为先增大后减少的变化趋势，差值最大的月份是6月，说明新疆南疆绿洲地区多年内6月地表缺水情况最严重。从四季来看，南疆绿洲地区蒸散 $E T$ 和PET夏季(6\~8月）最高分别为 $8 2 . 7 6 \ \mathrm { \ m m }$ 和 $3 2 6 . 8 5 ~ \mathrm { \ m m }$ ,年内分别占比$3 3 \%$ 和 $3 7 \%$ ,由于气温较高、水汽充沛、光照充足辐射强烈，夏季的蒸散量在四季中最大；春季（3～5月） $_ { E T , P E T }$ 年内占比 $2 1 \%$ 、 $30 \%$ ,蒸散量分别为$5 2 . 8 0 ~ \mathrm { m m } \setminus 2 6 8 . 8 9 ~ \mathrm { m m }$ ，春天气温回升、植物蒸腾作用增强、日照时数变长辐射增加， $E T$ 和 ${ \cal P } { \cal E } T$ 在春季都呈增加趋势;秋季( $9 \sim 1 1$ 月） $_ { E T , P E T }$ 年内占比$2 1 \% . 2 0 \%$ ,蒸散量分别为 $5 3 . 6 0 ~ \mathrm { m m }$ 和 $1 7 8 . 3 2 \ \mathrm { m m }$ ，植物的蒸腾作用在秋季开始减弱，降雨和水汽都开始减少，致使秋季蒸散量呈下降趋势；冬季(12、1、2月)蒸散量最低， $_ { E T , P E T }$ 分别为 $6 2 . 9 5 ~ \mathrm { m m } . 1 0 8 . 1 4$ $\mathbf { m } \mathbf { m }$ ，年内占比 $2 5 \%$ ） $12 \%$ ,随着气温下降、植被蒸腾作用大幅减少、日照时数变少导致辐射降低，使得绿洲地区冬季的蒸散量在四季中最低。实际蒸散量ET和潜在蒸散量PET的差值在夏季最大，说明新疆南疆绿洲地区夏季地表缺水情况最严重。

![](images/78430a244afaa964e57a95d711aaec8174cab031fbc390066d8c8fb18a096b73.jpg)  
图1蒸散量时间变化图

# 2.2蒸散量空间变化特征分析

图2给出了新疆南疆绿洲地区2001—2014年平均蒸散量空间分布。可以看出，近14a蒸散量空间变化特征明显，由于越靠近绿洲北部与沙漠的距离越远，水分来源逐渐充足、植被覆盖度逐渐增加，绿洲地区的实际蒸散量 $E T$ 由东南向西北方向增加， $E T$ 在 $6 3 . 3 8 \sim 1 1 6 . 2 3 ~ \mathrm { m m }$ 内变化；南疆绿洲地区潜在蒸散量PET由东南向西北方向降低，PET在$7 5 7 . 2 1 \sim 9 4 9 . 8 8 ~ \mathrm { m m }$ 内变化，潜在蒸散受辐射影响较大，本文潜在蒸散模型Hargreaves 公式考虑温差因素，沙漠地区日照强烈、昼夜温差较大，因此图2反映的东南部绿洲地区PET偏大的特点符合事实特征。图3是南疆绿洲地区近14a实际平均蒸散量四季的空间分布情况，对比图3与图4发现，ET与PET在空间上呈现出相反的变化趋势。南疆地区绿洲围绕沙漠戈壁区呈环状分布，靠近沙漠戈壁的绿洲内环地区ET较小，PET较大;靠近西北方向的绿洲外环地区植被覆盖度升高、日照强度下降、气温降低，ET较大，PET较小。

绿洲地区蒸散量近14a四季空间变化在春、夏、秋三个季节都比较明显，冬季蒸散量低。春季由于气温回升、冰雪融化、水汽增多，绿洲地区的水分供应如要来源于融雪，所以绿洲地区春季实际蒸散ET在空间上普遍增大，高低值差异明显，实际蒸散ET高值区域集中在绿洲西北部，PET高值区在绿洲东南部。夏季南疆的气温奇高、日照强烈、水分消耗显著，蒸散量明显变大， ${ \mathit { P E T } }$ 空间上最高达371.24$\mathbf { m m } , E T$ 出现四季最高值 $4 7 . 1 0 \ \mathrm { m m }$ 。秋季蒸散量与春季相当，秋季气温迅速下降、植被蒸腾作用降低、水汽供应减少，蒸散量降低，实际蒸散量 $E T$ 空间分布介于 $1 4 . 9 1 \sim \ 3 7 . 9 2 \ \mathrm { m m }$ 间,潜在蒸散量PET空间变化介于 $2 0 7 . 5 5 \sim 2 7 4 . 5 1 \ \mathrm { m m }$ 。南疆绿洲地区冬季蒸散量非常低，地区气温急速下降、冰雪覆盖度高、日照时数减少、融雪量少等原因共同作用，冬季的实际蒸散量和潜在蒸散量在四季中贡献最低。

如果下垫面水分供应充足，实际蒸散ET与潜在蒸散PET理论上相等，由于气候、陆面循环的影响， $E T$ 在实际情况中大幅减少。比较ET和PET能够有效的反映地表水分情况，进而实现科学的干旱监测。

![](images/82253455bb72d71829880d207d0dada801f5bb5ca11f21fc200cfb0c07688fd2.jpg)  
Fig.1Temporal variation of evapotranspiration   
图2蒸散量年均值空间变化  
Fig.2Spatial variation of annual mean evapotranspiration

![](images/7c26a0174b2395d25b3a085e75aa386f00ea6126877523a1ec7f6b7061414108.jpg)  
Fig.3Spatial variation of four season mean actual evapotranspiration ET

![](images/368974b9ff402ac2bba0c357cb92d20b735c92995565f8f4871f4e5c2bb5c39d.jpg)  
图3实际蒸散量ET四季均值空间变化  
图4潜在蒸散量PET四季均值空间变化  
Fig.4Spatial variation of four season mean potential evapotranspiration in PET

# 2.3MOD16产品数据与实测值精度检验

将MOD16蒸散产品数据与新疆南疆绿洲地区的小型蒸发皿数据进行精度验证。选取南疆境内的23个气象站点的蒸发皿数据，与2006一2010年月尺度的MOD16ET、PET数据进行拟合。结果表明实测蒸发血数据与PET的拟合效果较好，从PET与蒸发血的散点图能够看出二者部分点比较离散，并且MOD16PET明显偏小。PET主要受太阳辐射的影响夜间没有潜在蒸散，而蒸发血数据是全天候监测数据，因此影响二者之间的相关性。

图5展示了实测蒸发皿数据与MOD16产品PET数据的关系，拟合结果在0.01水平（双侧）上显著相关。由此可见，MOD16蒸散产品数据在南疆地区有较高的适应性，表明了通过MOD16数据进行蒸散反演的可行度和可信度较高。

# 2.4基于EDI指数的新疆南疆绿洲地区干旱特征分析

单一的多年EDI均值不能准确表示地表的异常干湿状况，只能在一定程度上反映出研究时段内的平均干湿程度。图6绿洲地区EDI空间分布图，可以看出近14aEDI在绿洲地区大范围值较大，发现在河流密集、远离沙漠戈壁的绿洲地区EDI值稍小，干旱程度略轻。因此，本研究计算2001一2014年的EDI距平值( $\triangle E D I )$ 来描述新疆南疆绿洲地区的地表干旱程度，突出多年均值差异进行干旱特征分析。

图7是近14a南疆绿洲地区EDI、△EDI以及二者插值的时间变化情况，2001—2014年的EDI年均值在 $0 . 6 0 \ \sim 0 . 7 3$ 之间,绿洲地区干旱情况普遍比较严重。干旱指数EDI受蒸散量的影响，潜在蒸散PET与实际蒸散ET的差值越大,EDI值越高，地表缺水越严重，地区干旱情况越严重。最低值在

![](images/3a6f5819a4ef05a916c9413a5537bc381f953ec8d2899a526d14f03fd62506ae.jpg)  
图5实测蒸发皿数据与MOD16产品相关性 Fig.5Relevance between measured evaporating dish data and MOD16 products

![](images/9cc6ffefd939d58a19a24730753fd6025239cd4e036fe09b3c47b7098e9b4f58.jpg)  
图6EDI年均值空间分布图

![](images/9283c90a17b535b0f8b25a7bc264a61e3cc8779573d380a09f27b5782484746f.jpg)  
Fig.6EDI Annual Mean Spatial Distribution Map   
图7 EDI、△EDI年际均值变化图  
Fig.7Interannual mean change map of $E D I$ and delta EDI

2003年，2001和2007—2009 年EDI值均在0.7上下浮动。计算 $\triangle E D I$ 直观的判断干旱程度， $\triangle E D I$ 为正值的年份干旱情况更严重， $\triangle E D I$ 为负值的年份干旱情况稍轻。图7显示出 $\triangle E D I$ 在 2001、2007—2009、2014年为正值，说明这5a南疆绿洲地区地表严重缺水。EDI和△EDI同相位变化，即EDI越大，△EDI越大的地区干旱程度越严重。定义的干旱指数EDI综合考虑了植被覆盖、地表辐射和气象因素，比起利用单一因素分析地区干旱特点更有科学依据。

# 3讨论

随着遥感技术的发展，越来越多的研究能够通过卫星影像计算地表特征参数，估算大区域蒸散逐渐成为可能[14-15]。地表蒸散量的估算是一个十分复杂的过程，实际蒸散的计算比潜在蒸散繁琐

目前有许多学者根据不同的角度以及理论，提出了许多反演地表蒸散的方法。由于研究角度的不一致，导致每种模型都有其自身的适用性以及局限性，即使蒸散模型使用条件相同，估算蒸散的精度和模拟结果也相差很大[5,16]。本文对混合型线性双源遥感蒸散模型进行了改进，简化和优化了相关参数，使模型的通用性更强。不同的下垫面性质不同，进而蒸散估算结果和干旱监测模型也不相同[17]。因此，开展地面试验，提高模型对地形复杂地区的普适性是进一步研究的重点。

# 4结论

（1）MOD16产品PET数据与实测蒸发血数据的相关性很好，通过显著性检验。说明利用MOD16数据在南疆绿洲地区有较好的适用性，通过线性双源遥感蒸散模型模拟的蒸散量有较高的可信度。

（2）时间上，2001—2014 年新疆南疆绿洲地区年均蒸散量变化较小， $E T$ 总体轻微上升，PET轻微下降。蒸散量四季变化特征明显，其中夏季蒸散量最大，冬季最小。空间上，2001—2014年绿洲地区的ET和PET空间变化特征相反，实际蒸散量由东南向西北方向ET增加，PET减少。靠近沙漠戈壁的绿洲内环地区实际蒸散量ET较低，潜在蒸散量PET较高。干旱半干旱地区地表缺水严重,ET主要由水分和能量决定，ET与PET的差值很大程度上反映了地表缺水程度。

（3）2001—2014年绿洲地区EDI指数值普遍较高，EDI指数的空间分布特征与ET相反。通过△EDI直观的进行干旱特征分析，EDI越大，△EDI越大的地区干旱程度越严重。EDI指数不仅考虑了气象因素，还考虑了对大气产生影响的土壤和植被因素，反映地区干旱程度科学性更高。

# 参考文献(References)

[1］吴燕锋,巴特尔·巴克,罗那那.1961—2012 年北疆干旱时空变化［J].中国沙漠,2017,37（1）：158-166.[WUYanfeng,BAKE Batur,LUO Nana.Spatiotemporal pattern of drought inNorth Xinjiang,China in 1961—2012［J].Journal of Desert Re-search,2017,37(1) :158-166.]

[2］黄小涛,罗格平.天山北坡低山丘陵干草原生长季蒸散特征 [J].干旱区地理,2017,40(6）:1198-1206.[HUANG Xiaotao, LUO Geping.Evapotranspiration characteristics of the growing season in hilly dry steppe,the northern slope of Tianshan Mountains [J].AridLand Geography,2017,40(6):1198-1206.]

[3]尹云鹤,吴绍洪,赵东升，等.1981—2010 年气候变化对青藏高原实际蒸散的影响[J].地理学报，2012,67（11）：1471-1481.[YINYunhe,WU Shaohong,ZHAO Dongsheng,et al.Impact ofclimate change on actual evapotranspiration on the Tibetan Plateauduring 1981—2010[J].Acta Geographica Sinica,2012,67（11）：1471 - 1481. ]

[4]高歌,陈德亮,任国玉,等.1956—2000 年中国潜在蒸散量变化趋势[J].地理研究，2006，25（3）：378-387.［GAOGe，CHENDeliang,REN Guoyu,et al.Trend of potential evapotranspiration o-ver China during 1956 to 200o[J].Geographical Research,2006,25(3) :378 -387. ]

[5］田静,苏红波,陈少辉,等.近20 年来中国内陆地表蒸散的时空 变化[J].资源科学,2012,34（7）:1277-1286.[TIAN Jing,SU Hongbo,CHEN Shaohui,et al. Spatial-temporal variations of evapotranspiration in China mainland in recent 2O years[J].Resources Science,2012,34(7) :1277 -1286.] [6］辛晓洲,田国良,柳钦火.地表蒸散定量遥感的研究进展[J]. 遥感学报,2003,7（3）:233-240.[XIN Xiaozhou,TIAN Guoliang,LIU Qinhuo.A review of researches on remote sensing of land surface evapotranspiration[J]. Journal of Remote Sensing,   
2003,7(3) :233 -240.] [7］郭淑海,杨国靖,李清峰,等.新疆阿克苏河上游高寒草甸蒸散 发观测与估算[J].冰川冻土，2015，37（1）：241-248.［GUO Shuhai,YANG Guojing,LI Qingfeng,et al. Observation and estimationof the evapotranspiration of alpine meadow in the upper reachesof the Aksu River,Xinjiang[J]. Journal of Glaciology and Geocryology,2015,37（1） :241-248.] [8］王永东,李生宇,徐新文,等.Hargreaves 公式在塔克拉玛干沙漠 腹地的适用性[J].中国沙漠,2013,33（2）:367-372.［WANG Yongdong,LI Shengyu,XU Xinwen,et al. Applicabilityof Hargreaves formula in the hinterland of Taklimakan Desert[J]. Journal of Desert Research,2013,33(2）:367 -372.] [9］董婷,孟令奎,张文.1961—2012 年我国干旱演变特征[J].干旱 区研究,2018,35（1）:96-106.[DONG Ting,MENG Lingkui, ZHANG Wen.Evolution of drought in China during the period of   
1961——2012[J].Arid Zone Research,2018,35(1) :96 -106.] [10］李向婷,白洁,李光录,等.新疆荒漠稀疏植被覆盖度信息遥感 提取方法比较[J].干旱区地理,2013,36(3）：502－511.［LI Xiangting,BAI Jie,LI Guanglu,etal. Comparison of methods based on MODIS for estimating sparse vegetation fraction across desert in Xinjiang[J].Arid Land Geography,2013,36(3）:502-511.] [11］李丹.海流兔河流域地下水、NDVI和蒸散的组合关系研究 [D].北京:中国地质大学,2016.[LI Dan.The composite relationships among groundwater,NDVI and evapotranspiration in the Hailiutu River Catchment,China[D].Beijing:China University of Geosciences,2016.] [12]NISHIDA K,NEMANIRR,RUNNING SW,et al.An operational remote sensing algorithm of land surface evaporation[J]. Journal of Geophysical Research Atmospheres,2003,108（108）:469 -474. [13］刘雅妮,武建军,夏虹,等.地表蒸散遥感反演双层模型的研究 方法综述[J].干旱区地理,2005,28（1）:65-71.[LIU Yani, WU Jianjun,XIA Hong,etal.Summarization of research methods for surface evapotranspiration remote sensing inversion bi level model[J] Arid Land Geography,2005,28(1）:65-71.]

[14］阿迪来·乌甫,玉素甫江·如素力,热伊莱·卡得尔,等.基于 MODIS 数据的新疆地表蒸散量时空分布及变化趋势分析[J]. 地理研究,2017,36（7）:1245-1256.［WUFUAdilai,RUSULI Yusufujiang,KADEERReyilai,etal.Spatio-temporal distribution and evolution trend of evapotranspiration in Xinjiang based on MOD16 data[J].Geographical Research,2017,36（7）:1245 - 1256.]

[15」何慧娟，卓静，董金芳，等.基于MOD16监测陕西省地表蒸散 变化[J].干旱区地理,2015,38（5）:960-967.［HE Huijuan, ZHUO Jing,DONG Jinfang,et al.Surveying variations of evapotranspiration in Shaanxi Province Using MOD16 products[J].Arid

Land Geography,2015,38(5） :960 -967.][16］张方敏，居为民,陈镜明,等.基于BEPS生态模型对亚洲东部地区蒸散量的模拟[J].自然资源学报，2010，25（9)：1596-1606.［ZHANG Fangmin,JU Weiming,CHEN Jingming,et al.Study on evapotranspiration in east Asia using the BEPS ecologicalmodel[J]. Journal of Natural Resources,2010,25（9）:1598-1606.]

[17］李新.塔里木盆地绿洲蒸散量的日变化规律分析[J].干旱区 地理,1994,17(4）:23-29.[LI Xin.Anakysis on daily evaporationin Tarim Oasis[J].AridLandGeography,1994,17(4) :23- 29.]

# Spatio-temporal variation characteristics of surface evapotranspiration and drought at the oasis area of the southern Xinjiang in recent 14 years

GAO Yu-lian’，LIU Jin-bao’，LIU Wei-yang²，YU Jing13，LIU Zhi-hong1 (1Chengdu University of Information Technology,Chengdu 61O225,Sichuan,China; 2 Institute of Plant Science and Technology,Tarim University,Aral 8433oo,Xinjiang,China; 3 InnerMongolia Tongliao Meteorological Bureau,Tongliao O28OOO,Inner Mongolia,China)

Abstract：Evapotranspiration is estimated based on NDVI,surface net radiation,air temperature byusing China monthly meteorological data and MODIS remote sensing data which include evapotranspiration data(MOD16）and normalized diffrence vegetation index data(MOD13).Simplify and improve the parameters of mixed linear dual source remote sensing evapotranspiration model to estimate the surface evapotranspiration in oasis region of southern Xinjiang,China.Analysis of spatial and temporal variation characteristics of theactual-evapotranspiration(ET) and potential-evapotranspiration(PET）from 200l to 2O14.Besides,based on the correlation analysis of measured evaporation data from meteorological stations in southern Xinjiang,theapplicabilityof MOD16 products in oasis region is already credible by means of statistical test.According to theevapotranspiration drought index(EDl）,the distribution characteristics ofdrought inoasisof southern Xinjiang isanalyzed,andthedegreeof droughtis determined by the $E D I$ anomaly.The results reflect that the annual mean evapotranspiration from 2OO1 to 2O14 shows littlechange,and these are significant diference among the four seasons.The highest evapotranspiration is in summer and the lowest in winter.The spatial trend of $E T$ and ${ \cal P } { \cal E } T$ isin opposite situation.In addition,there is a huge disparity between the annual value of $E T$ and $P E T$ which means the surface water shortage is serious in oasis.Furthermore ,the average annual value of $E D I$ index in oasis area is fairly large,the response of EDI anomaly to drought and the judgment of drought degree are reliable.From the perspective of energyand water-balance,this research simplifies the model parameters and enhances the applicability of the model.It has certain guiding significance for large scale areas evapotranspiration estimation and drought monitoring.

Key words:southern Xinjiang；oasis；surface evapotranspiration；evapotranspiration drought index （EDI）；spatial and temporal variation characteristics