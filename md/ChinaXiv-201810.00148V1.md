# 新疆地区蒸发血蒸发量变化及基于小波的周期分析

秦榕¹，李林超²，杨霰³，杨华，杨艳玲4，何亚平}（1新疆气象信息中心,新疆乌鲁木齐830002；2西北农林科技大学水建学院,陕西杨凌712100;3新疆气象服务中心,新疆乌鲁木齐830002；4 哈密地区气象局,新疆哈密839000)

摘要： $\Phi 2 0 ~ \mathrm { c m }$ 和 $E _ { 6 0 1 }$ 型蒸发皿在新疆均有使用，但两种数据序列自观测开始至今均不完整，尤其自2003年以后数据未进行整合和校正，使得对蒸发皿蒸发量数据的使用和深入分析受到限制。本研究基于 $\Phi 2 0 \ \mathrm { c m } ( { \cal E } _ { 2 0 } )$ 和 $E _ { 6 0 1 }$ 型蒸发血蒸发量( $\boxed { E _ { 6 0 1 } }$ )的共同观测期数据，选取新疆地区57个气象站，分析 $4 \sim 1 0$ 月 $E _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 的换算系数 $K$ 。以数据序列较长的喀什(隶属南疆)和塔城站(北疆)为例，分析了逐日和逐月尺度下 $K$ 的变化，并将各月 $K$ 值用于两个典型站2003—2016年期间4月1日 $\sim 9$ 月30日 $E _ { 2 0 }$ 的估算，得出1961—2016年完整的日 $E _ { 2 0 }$ 序列。进一步基于复Morlet小波函数对月及年尺度 $E _ { 2 0 }$ 的波谱特性和周期变化进行了分析，结果表明：(1)新疆地区 $E _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 的换算系数在 $4 \sim 1 0$ 月期间具有较大的空间差异，南疆 $K$ 值较北疆大。(2)喀什和塔城站插补后完整的1961—2016年期间日 $E _ { 2 0 }$ 序列具有以年为周期的典型变化，月 $E _ { 2 0 }$ 在7月最大，年 $E _ { 2 0 }$ 均具有明显的增加趋势；日、月及年尺度下喀什站 $E _ { 2 0 }$ 均高于塔城站。(3)两站点 $1 \sim 1 2$ 月 $E _ { 2 0 }$ 的主周期和准周期具有2\~16a的波动，年 $E _ { 2 0 }$ 的主周期均为7a,喀什站准周期为3a和 $6 \mathrm { ~ a ~ }$ ，塔城站准周期为2a和4a。本研究可为新疆地区蒸发量序列的插补及进一步应用提供参考。

关键词：蒸发皿蒸发量；换算系数；小波分析；新疆中图分类号：P426.2.2 文献标识码：A 文章编号：

蒸发皿蒸发量是大气蒸发能力的重要指标，可用于估算陆地蒸发、水文循环和作物需水[1]。蒸发皿蒸发量可通过不同方式获得，如基于气象观测数据建立估算模型[2-3]或采用仪器观测[4]等。国内外研究者采用蒸发血蒸发量进行分析，获得了非常多可借鉴的成果。如LINACRE[5]建立了Penpan 物理模型估算蒸发皿蒸发量,ROTSTAYN 等[耦合了LINACRE[5]和 THOM等[7]的空气动力学项建立了Penpan 模型。基于Penpan 模型,RODERICK 等[2]JOHNSON和SHARMA[8]分别证实该模型可成功估算澳大利亚不同站点的A型蒸发皿蒸发量。MA-LIK和KUMAR基于人工神经网络和协同神经模糊推理系统，采用多元线性回归模拟了印度喜马拉雅山脚某地的日蒸发皿蒸发量[9]。ZHANG 等对比了青藏高原1966—2003年期间蒸发血蒸发量、参考作物滕发量和实际蒸散发的趋势，发现蒸发血蒸发量和实际蒸发量具有相反的变化趋势，前者呈降低趋势,而后者呈增加趋势，表明青藏高原存在蒸发悖论[10]。YANG 等[11]基于蒸发皿蒸发量的观测数据对仪器更换导致的中国太阳辐射数据不一致性进行了分析。MCMAHON等[]分三部分给出了估算逐日和逐月实际蒸发、潜在腾发量、参考作物滕发量及蒸发皿蒸发量的指南。曾燕等[13]利用中国664 个气象站1960—2000年 $2 0 \ \mathrm { c m }$ 口径( $\Phi 2 0 \ \mathrm { c m } \stackrel { . } { \ }$ )蒸发皿资料进行分析，发现中国蒸发皿蒸发量呈明显减少趋势，认为其原因可能是日照百分率减少造成的太阳总辐射减少。祁添垚等[14]对1960—2005 年中国蒸发血蒸发量的分析则认为，相对湿度是影响中国蒸发皿蒸发量变化的关键因子。然而,刘敏等[15]基于671个气象站1955—2001年的 $\Phi 2 0 ~ \mathrm { c m }$ 蒸发皿蒸发量和气象要素月观测资料进行趋势分析，结果表明气温日较差和平均风速的减小是蒸发皿蒸发量减少的影响因子。其他学者则分别针对长江上游区域[16]黄河流域[17]、淮河流域[18]、东江流域[9]、澜沧江流域[20]、青海湖流域[21]、石羊河流域[22]等地区的蒸发皿蒸发量进行了研究。

国外常用的蒸发血蒸发量观测仪器是A型蒸发皿，而我国在近60a来先后使用了 $\Phi 2 0 \ \mathrm { c m } \ . \Phi 8 0$ cm和 $E _ { 6 0 1 }$ 型蒸发皿。2003年之前，国家基本气象站均采用 $\Phi 2 0 ~ \mathrm { c m }$ 蒸发皿进行观测，但考虑两种蒸发皿的优势及各自的局限性，2003年至今，在蒸发量较小的10月到次年3月采用 $\Phi 2 0 \ \mathrm { c m }$ 蒸发皿进行观测，而在年内其余时段采用 $E _ { 6 0 1 }$ 型蒸发血进行观测。由于 $\Phi 2 0 \ \mathrm { c m } ( { \cal E } _ { 2 0 } )$ 和 $E _ { 6 0 1 }$ 型 $\left( E _ { 6 0 1 } \right)$ )蒸发皿蒸发量并不完全一致，因此，近10余年来，蒸发皿蒸发量的资料不再是完整的连续序列。这导致蒸发皿蒸发量的资料利用率受到限制。为了得到 $E _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 之间的关系，部分学者采用线性关系或多元回归对两种蒸发皿蒸发量的关系进行转换[20.23],并分析转换关系的有效性。然而，目前还没有相关研究对新疆地区 $E _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 的关系、 $E _ { 2 0 }$ 完整序列的获取及其深入应用进行探讨。

本研究拟在逐日和逐月尺度下进行 $E _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 换算系数的分析，利用复Morlet小波函数对月及年尺度 $E _ { 2 0 }$ 的波谱特性和周期变化进行深入探讨，从而为基于 $E _ { 6 0 1 }$ 估算 $E _ { 2 0 }$ 提供可靠方法和依据。

# 数据与方法

# 1.1气象站点分布及数据年限

选择新疆地区蒸发皿蒸发量数据序列较长的57个气象站的数据进行分析，站点的经度和纬度变化范围分别为 $8 5 . 8 ^ { \circ } \sim 9 4 . 7 ^ { \circ } \mathrm { E }$ 和 $3 6 . 9 ^ { \circ } \sim 4 4 . 3 ^ { \circ } \mathrm { N }$ 海拔高度变化范围为 $3 0 \sim 3 ~ 0 9 5 ~ \mathrm { ~ m ~ }$ 。研究区多年平均气温、风速、相对湿度和日照时数变化范围分别为$0 . 7 \sim 1 4 . 5 \mathrm { ~ \% ~ } 0 . 8 \sim 4 . 0 \mathrm { ~ m ~ } \cdot \mathrm { ~ s ~ } ^ { - 1 } . 3 9 . 4 \% \sim 6 7 . 4 \%$ 和 $7 . 1 \sim 9 . 1 ~ \mathrm { h } ^ { [ 2 4 ] }$ 。各气象站的地理位置及DEM 如图1所示。

在选择的57个气象站中，40个站含有 $^ \textrm { \scriptsize 4 a , 1 5 }$ 站含有17a以上的 $E _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 共同观测数据（表1）。

# 1.2 ${ \cal E } _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 的换算系数

本文拟基于 $4 \sim 1 0$ 月的逐日 $E _ { 6 0 1 }$ 观测值估算$E _ { 2 0 }$ 值。因此换算系数定义为：

$$
K = E _ { 2 0 } / E _ { 6 0 1 }
$$

因此,基于 $E _ { 6 0 1 }$ 观测值和换算系数可估算 $E _ { 2 0 }$ 值：

$$
E _ { 2 0 } = K \cdot E _ { 6 0 1 }
$$

![](images/4c7f034c8c612dac60ad0d15a3b6303a10d46b16422740de21e9ea2e5f13b54c.jpg)  
图1新疆地区所选站点的地理位置及DEM  
Fig.1Geographical locations of the weather stations and digital elevation model（DEM） in Xinjiang

表1具有 $\scriptstyle { E _ { 2 0 } }$ 和 $E _ { 6 0 1 }$ 共同观测数据的年份  
Tab.1 Common periods for the $\scriptstyle { E _ { 2 0 } }$ 和 $E _ { 6 0 1 }$ measurement data   

<html><body><table><tr><td>站名</td><td>数据起止年限</td><td>站名</td><td>数据起止年限</td><td>站名</td><td>数据起止年限</td></tr><tr><td>阿合奇</td><td>1998—2001</td><td>哈密</td><td>1987—2001</td><td>莎车</td><td>1998—2001</td></tr><tr><td>阿克苏</td><td>1984—2001</td><td>和丰</td><td>1998—2001</td><td>十三间房</td><td>1999—2001</td></tr><tr><td>阿拉尔</td><td>1998—2001</td><td>和田</td><td>1985—2001</td><td>石河子</td><td>1998—2001</td></tr><tr><td>阿拉山口</td><td>1998—2001</td><td>红柳河</td><td>1998—2001</td><td>塔城</td><td>1985—2001</td></tr><tr><td>阿勒泰</td><td>1984—2001</td><td>吉木乃</td><td>1998—2001</td><td>塔什库尔干</td><td>1998—2001</td></tr><tr><td>阿图什</td><td>1985—2001</td><td>精河</td><td>1998—2001</td><td>铁干里克</td><td>1998—2001</td></tr><tr><td>巴楚</td><td>1998—2001</td><td>喀什</td><td>1984—2001</td><td>吐鲁番</td><td>1985—2001</td></tr><tr><td>巴里坤</td><td>1998—2001</td><td>柯坪</td><td>1998—2001</td><td>托里</td><td>1998—2001</td></tr><tr><td>巴仑台</td><td>1998—2001</td><td>克拉玛依</td><td>1993—2001</td><td>温泉</td><td>1998—2001</td></tr><tr><td>巴音布鲁克</td><td>1998—2001</td><td>库车</td><td>1998—2001</td><td>乌兰乌苏</td><td>2007—2011</td></tr><tr><td>拜城</td><td>1998-2001</td><td>库尔勒</td><td>1984—2001</td><td>乌鲁木齐</td><td>1984—2001</td></tr><tr><td>北塔山</td><td>1998—2001</td><td>库米什</td><td>1998—2001</td><td>乌恰</td><td>1998—2001</td></tr><tr><td>博乐</td><td>1985—2000</td><td>轮台</td><td>1998—2001</td><td>乌苏</td><td>1998—2001</td></tr><tr><td>蔡家湖</td><td>1998-2001</td><td>民丰</td><td>1998—2001</td><td>焉耆</td><td>1998-2001</td></tr><tr><td>昌吉</td><td>1985—1997</td><td>皮山</td><td>1998—2001</td><td>伊型</td><td>1984—2001</td></tr><tr><td>达坂城</td><td>1998—2001</td><td>奇台</td><td>1987—2001</td><td>伊吾</td><td>1998—2001</td></tr><tr><td>福海</td><td>1998-2001</td><td>且末</td><td>1998- -2001</td><td>于田</td><td>1998—2001</td></tr><tr><td>富蕴</td><td>1998—2001</td><td>青河</td><td>1998—2001</td><td>昭苏</td><td>1998—2001</td></tr><tr><td>哈巴河</td><td>1998—2001</td><td>若羌</td><td>1998—2001</td><td></td><td></td></tr></table></body></html>

式中： $\mathcal { f } _ { b }$ 是带宽参数; $f _ { c }$ 是小波中心频率。

式中： $E _ { 6 0 1 }$ 和 $E _ { 2 0 }$ 的单位均为 $\mathbf { m m }$ C

各站点换算系数 $K$ 的空间分布图在ArcGIS10.2中完成。由于新疆地区地形复杂，高山、盆地、沙漠地貌类型不同，南北疆气候类型也有显著差异，出于严谨性,本文未对 $K$ 值进行空间插值。

# 1.3 小波分析法

小波分析可较准确的检验信号波谱和方差变化，从而得出序列的主周期和准周期。小波函数有很多种，是小波分析的关键，它是指具有震荡性、能够迅速衰减到零的一类函数，即小波函数 $\boldsymbol { \varPsi } ( t ) \in \boldsymbol { L } ^ { 2 }$ $( R )$ 且满足：

$$
\int \limits _ { - \infty } ^ { + \infty } \psi ( t ) \mathrm { d } t = 0
$$

式中： $\psi ( t )$ 为基小波函数，它可通过尺度的伸缩和时间轴上的平移构成一簇函数系：

$$
\Psi _ { a , b } \big ( t \big ) = \mid a \mid ^ { - 1 / 2 } \Psi \Big ( \frac { t - b } { a } \Big )
$$

式中： ${ \mathrm { : } } a , b \in R , a \neq 0 ; \varPsi _ { a , b } \left( t \right)$ 为子小波; $\mathbf { \alpha } _ { a }$ 为尺度因子，反映小波的周期长度; $b$ 为平移因子，反应时间上的平移。

选取复Morlet小波作为小波函数，其表达式为：

$$
\varphi ( x ) = \sqrt { \pi f _ { b } } \mathrm { e } ^ { j \pi f _ { c } x } \mathrm { e } ^ { \frac { x } { f _ { b } } }
$$

# 2结果与分析

# 2.1逐日和逐月尺度下 $\pmb { { \cal E } } _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 的相关性

对新疆地区57站 $E _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 共同观测时段( $~ 4 \sim$ 10月)的日、月蒸发量进行分析发现，各月日 $E _ { 2 0 }$ 和$E _ { 6 0 1 }$ 的关系并不一致，因此两者之间的换算系数应区分不同月份。此外,逐日和逐月尺度的 $E _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 相关性也具有差异。以具有17a $E _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 共同观测数据的2个典型站点（北疆选塔城站、南疆选喀什站)为例,不同月份日 $E _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 及逐月 $E _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 的散点图及相关关系如图2所示。由该图可知，塔城 $5 \sim 1 0$ 月的逐日 $E _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 换算系数 $K$ 分别为$1 . 7 9 2 , 1 . 8 2 5 , 1 . 6 5 6 , 1 . 6 0 2 , 1 . 6 2 3 , 1 . 5 9 4$ 及1.623;而月尺度下两者换算系数为1.670。虽然日尺度下回归关系的决定系数 $R ^ { 2 }$ 变化范围为 $0 . 6 6 \sim 0 . 8 5$ ，月尺度下 $R ^ { 2 }$ 较高(0.934），但由于各月 $K$ 值差异较大，若以月尺度下的 $K$ 值统一代替日尺度下各月的$K$ 值,则用于估算日 $E _ { 2 0 }$ 会引起较大偏差。因此，对新疆地区57个站点分别进行日尺度下 $4 \sim 1 0$ 月 $K$ 值的分析。喀什站逐日尺度下，除4月之外，其他各月的 $E _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 线性相关关系都比塔城站的低（ $R ^ { 2 }$ 更小），表明更干旱的地区两者关系更具有不确定性；但逐月尺度相关性更好。

将各站点 $K$ 值在 $4 \sim 1 0$ 月期间的空间变化绘于图3（部分站点4月和10月无 $K$ 值）。图中，新疆地区 $K$ 值在 $4 \sim 1 0$ 月期间具有较大的空间差异。其中，4月份 $K$ 值在天山山区(巴音布鲁克)和南疆较大（沙漠边缘各站基本大于1.8），在北疆较小，10月 $K$ 值也基本具有此特征但 $K$ 值小于1.4的站更多、且多在北疆;5月 $K$ 值在空间上的差异比4月和10月的小，且均小于2.3；6月 $K$ 值多在 $1 . 5 6 \sim 1 . 9$ 范围变化,极值较少;7\~9月的 $K$ 值在空间上较相似，大多小于1.8。虽然出于严谨考虑，图3未对 $K$ 值进行空间插值，从而将点数据扩展为面数据，但未进行 $K$ 值率定的地区仍可参考图3已有的站点进行 $K$ 值的估算。

气象要素在近地层随高度变化剧烈，在同一段时间内，不同高度上同样的仪器所测得的蒸发量是不同的，这是风速的垂直分布起了主要作用，高度高，风速大，则蒸发也大。湿度随高度迅速减小，也影响蒸发随高度增大。小型蒸发器身全部暴露在外面，在阳光照射下水温不断升高，加大了蒸发。南疆风速大、温度高、降水少、湿度小，故小型蒸发比北疆大。故而造成南疆 $K$ 值大,北疆 $K$ 值小。

# 2.2塔城站日、月及年 $\scriptstyle { E _ { 2 0 } }$ 序列

得到各站 $K$ 值后,即可根 $4 \sim 1 0$ 月观测的 $E _ { 6 0 1 }$ 估算日尺度 $E _ { 2 0 }$ ，从而得出1961—2016年期间逐日$E _ { 2 0 }$ 序列。图4展示了塔城站1961—2016 年期间$E _ { 2 0 }$ 的日变化、多年平均月变化及年变化。

由图 $\mathrm { 4 a }$ 可见，喀什和塔城两站 $E _ { 2 0 }$ 的日变化具有典型的年内波动,其中塔城站最大值可达 $2 5 ~ \mathrm { m m }$ ，最小值为 $0 ~ \mathrm { m m }$ 。图4b中，塔城站月 $E _ { 2 0 }$ 在 $5 \sim 8$ 月较大，7月达到最大，变化范围 $1 7 \sim 2 8 7 ~ \mathrm { \ m m }$ 。图4c中，塔城站年 $E _ { 2 0 }$ 在 $1 \ 3 7 3 \sim 2 \ 1 9 1 \mathrm { m m }$ 范围变化，年

喀什站25 25 30 25(a)逐日尺度：4月 (b)逐日尺度：5月 (c)逐日尺度：6月 (d)逐日尺度：7月20 X x 20 x 25 交 2015 3 X 15 ++ 15 uu 15  
1 610 51 E2 1050X =10.6336 =1.8.69 =17537x x y=16403X 華L0 3 6 9 12 15 0 3 6 9 12 15 0 3 6 9 12 15 0 3 6 9 12 15E601/m E601/m E601/mm E601/mm25 20 15 4505 (e)逐日尺度：8月 115 (f)逐日尺度：9月 ￥ 10/ (g)逐日尺度：10月 X 30 (h)逐日尺度 中 新X3  
10 50 1502 y=.57041 5 +共 =15.935 180 90 书 =.7403X xx0 五0 3 6 9 12 15 0 3 6 9 12 0 3 6 9 050100150200 250 300E601/mm E601/mm E601/mm E601/mm塔城站20 25 25 25（a)逐日尺度：4月× (b）逐日尺度：5月x (c)逐日尺度：6月 (d)逐日尺度：7月11 # 205  
金 uu 15 10 5 0 =17927 10 50 X =18251 多 E 10 50 数 我 y=065672x xX 务 uu / 10 0 5 女 =160230 369 12 0 3 6912 15 0 36912 15 0 369 12 15E601/mm E601/mm E601/mm E601/mm25 (e)逐日尺度：8月 20 (f)逐日尺度：9月 城 20 (g)逐日尺度：10月 350 (h)逐日尺度20 xx 15 15 300uu 15 x 10 X 车 28 新  
51 我 =1238 E 5 X 15947 5 x y=1.6232x 100 501050 x 美 =1..70440区 0 X 0 00 3 6 9 12 15 0 3 6 9 12 0 3 6 9 12 0 50 100 150 200 250E601/mm E601/ mm E601/mm E601 /mm

![](images/d7ea60694fd8bfdaac6d315cc384ebe4b114b5cee783717f0d923af59ee84d07.jpg)  
图3新疆地区 $4 \sim 1 0$ 月换算系数 $K$ 的空间分布

![](images/834cca851373855cd4f1245d728ef94edf3dd08379b4acac2c77e889e3c65bf8.jpg)  
Fig.3Spatial distribution of conversion coefficient $K$ in Xinjiang   
图4喀什和塔城站完整 $E _ { 2 0 }$ 序列的时间变化  
Fig.4Temporal variations of $E _ { 2 0 }$ at Kashi and Tacheng stations

际变异较大，在近56a间具有整体上升的趋势，年增加率 $3 . 9 9 8 \ \mathrm { m m }$ 。南北疆两站直接对比表明，日、月、年尺度下喀什站 $E _ { 2 0 }$ 均明显高于塔城站，前者明显比后者具有更大的蒸发能力，气候更趋干旱

# 2.3南北疆代表站月及年 $\scriptstyle { E _ { 2 0 } }$ 的周期变化

基于塔城站月 $E _ { 2 0 }$ 序列，利用复Morlet小波分析得到其小波波谱的变化（图5）。图中粗实线所围的范围表示小波凝聚谱值通过了 $9 5 \%$ 显著性水平检验的区域，黑色圆弧线外表示受边界效应影响较大的区域。

从图5可以看出， $E _ { 2 0 }$ 在频域上有着不同显著性水平的周期震荡。由于不同月份 $E _ { 2 0 }$ 差异比较大，各月周期震荡规律差异较大，但各月 $E _ { 2 0 }$ 的震荡周期主要集中在3\~7a和 $1 0 \sim 1 2 \mathrm { ~ a ~ }$ 。

小波方差图反映了小波震荡强度随时间的变化特点，它的峰值即为 $E _ { 2 0 }$ 的变化周期。图6为喀什(左)和塔城站(右)年尺度的 $E _ { 2 0 }$ 小波波谱和方差图。图6中，喀什站相对于塔城站来说周期性较弱，但是仍具有7a的主周期，另外两个准周期为2a和$\mathrm { ~ 4 ~ a ~ }$ 。塔城站年尺度的 $E _ { 2 0 }$ 共有三个周期，其中主周期为7a,准周期为3a和16a;在1965—1975年期间，准周期3a震荡较明显，主周期7a的震荡在1975—1995年期间更明显，准周期16a的震荡在1995—2015年期间明显。

表2 详细列出了塔城站1～12月及年 $E _ { 2 0 }$ 主周期和准周期。各月和年 $E _ { 2 0 }$ 主周期和准周期有一定差异，就年值而言，主周期为7a,准周期为3a和16a。月 $E _ { 2 0 }$ 的主周期和准周期的变化范围为 $2 \sim 1 6 \mathrm { ~ a ~ }$ ，各月之间的差异很大。喀什站也具有一定的周期特性,其1\~12 月及年 $E _ { 2 0 }$ 主周期分别为 $1 6 \mathrm { ~ a ~ } , 7$ a $\cdot ^ { 7 }$ a、

![](images/ba9a9a71dc30b3aac75c0c43d26752ec436e410e9f7bf9525c29f08565f6b94d.jpg)  
Fig.5Waveletspectrum of $E _ { 2 0 }$ fromJanuary to December for Tacheng stations

![](images/42d443746eeae6b428917a81eece05381d74a62b476cfa255eaa0c5a23cc3399.jpg)  
图5塔城站 $1 \sim 1 2$ 月的 $E _ { 2 0 }$ 小波波谱图  
图6喀什和塔城站年尺度的 $E _ { 2 0 }$ 小波波谱和方差图

Fig.6Wavelet spectrum and variance plots of annual $E _ { 2 0 }$ for Kashi and Tacheng stations

表2塔城站1\~12月及全年 $\scriptstyle { E _ { 2 0 } }$ 的主周期和准周期  
Tab.2Main and quasi-periods of $\scriptstyle { E _ { 2 0 } }$ from January to December and the whole year for Tacheng station   

<html><body><table><tr><td>周期/时间</td><td>1月</td><td>2月</td><td>3月</td><td>4月</td><td>5月</td><td>6月</td><td>7月</td><td>8月</td><td>9月</td><td>10月</td><td>11月</td><td>12月</td><td>全年</td></tr><tr><td>主周期</td><td>6</td><td>2</td><td>6</td><td>7</td><td>16</td><td>7</td><td>12</td><td>12</td><td>7</td><td>7</td><td>3</td><td>2</td><td>7</td></tr><tr><td>准周期</td><td>2</td><td>4</td><td>3</td><td>2</td><td>2</td><td>3</td><td>3</td><td>2</td><td>2</td><td>3</td><td>10</td><td>4</td><td>3</td></tr><tr><td></td><td>4</td><td>7</td><td>4</td><td>3</td><td>5</td><td>8</td><td>5</td><td>4</td><td>5</td><td>11</td><td>15</td><td>7</td><td>16</td></tr><tr><td></td><td></td><td>11</td><td>10</td><td>12</td><td>8</td><td>16</td><td>17</td><td>7</td><td>10</td><td>15</td><td></td><td>11</td><td></td></tr></table></body></html>

![](images/63a2996d441a96771677ec34d25b1a58bd7de63e1e7f9e0aec6097bc88cfa613.jpg)  
图7喀什站(a)和塔城站(b)1961—2016 年 $E _ { 2 0 }$ 不同周期的时间波动  
Fig.7Temporal fluctuations of $E _ { 2 0 }$ with different periods at Kashi(a）and Tacheng(b）over 1961—201

4a $\cdot ^ { 8 }$ a $\cdot ^ { 8 }$ a、15a $\cdot ^ { 2 }$ a $\cdot ^ { 6 }$ a $\cdot ^ { 9 }$ a $\cdot ^ { 6 }$ a $\boldsymbol { \cdot } 1 0 \mathrm { ~ a ~ } , 7$ a,不再赘述。

为了进一步分析周期的时间变化，图7展示了喀什和塔城站1961—2016 年 $E _ { 2 0 }$ 年际和年代际周期震荡情况，其中小波系数实部大于0的表示蒸发量大，小波系数实部小于0的表示蒸发量小，图例代表周期(年)。

从图7可以看出，(1)喀什站周期为7a的曲线经历了7个完整的波动变化1962、1969、1976、1983、1990、1997、2005、2012年期间较高，1964、1972、1979、1987、1994、2001、2008年较低。以2a及4a为周期的曲线也在1961—2016期间具有高或低的变化，其高峰和低谷与7a周期的曲线不同。(2)塔城站周期为16a的曲线经历了4个完整的波动变化，1962、1978、1994、2010年期间较高，1968、1985、2001年及2016年较低。以3a及7a为周期的曲线也在1961—2016期间具有高或低的变化，但其波动的高峰和低谷与16a周期的曲线不同。这种不同周期的震荡展示了 $E _ { 2 0 }$ 年值变异的内在规律。

# 3结论

（1）新疆地区 $E _ { 2 0 }$ 和 $E _ { 6 0 1 }$ 在 $4 \sim 1 0$ 月共同观测时段的换算系数 $K$ 值具有典型的空间差异。南疆，尤其是沙漠边缘站点的 $K$ 值较大。得出的 $K$ 值可用于 2003—2016 年期间 $2 0 ~ \mathrm { c m }$ 蒸发皿蒸发量 $E _ { 2 0 }$ 序列的插补。

（2）喀什和塔城站1961—2016 年期间 $E _ { 2 0 }$ 的日值具有以年为周期的典型变化，月值在7月最大，年值具有明显的增加趋势；日、月及年尺度下喀什的$E _ { 2 0 }$ 均高于塔城。

（3）喀什和塔城站1961—2016年期间 $1 \sim 1 2$ 月 $E _ { 2 0 }$ 的主周期和准周期在 $2 \sim 1 6$ a 的范围内波动，两站年 $E _ { 2 0 }$ 的主周期均为 $7 \mathrm { ~ a ~ }$ ,喀什站(塔城站)准周期为2a和4a(3a和6a)。

# 参考文献（References)

[1] YANG Hanbo,YANG Dawen. Climatic factors influencing changing pan evaporation across China from 1961 to 2001［J].Journal of Hydrology,2012,414(2):184-193.   
[2] RODERICK ML,ROTSTAYNLD,FARQUHARGD,et al.On the attribution of changing pan evaporation[J].Geophysical Research Letters,2007,34(34） :251-270.   
[3] RODERICK ML,FARQUHAR G D.The cause of decreased pan evaporation over the past 5O years[J].Science（New York,N. Y),2002,298(5597):1410 -1411.   
[4] ALLAN RG,PEREIRAL L S,RAES D,et al. Crop evapotranspiration:Guidelines for computing crop water requirements[R].FAO Irrigation and Drainage Paper No.56.FAO,1998.   
[5] LINACRE E T.Estimating U.S.Class a pan evaporation from few climate data[J].Water International,1994,19(1）:5-14.   
[6] RROTSTAYNLD,RODERICKML,FARQUHARGD.A simple pan-evaporation model for analysis of climate simulations：Evaluation over Australia［J].Geophysical Research Letters,2O06,33 (17):165-173.   
[7] THOM A S,THONY JL,VAUCLIN M.On the proper employment of evaporation pans and atmometers in estimating potential transpiration[J]. Quarterly Journal of the Royal Meteorological Society, 1981,107(453）:711 - 736.   
[8] JOHNSON F,SHARMA A.A comparison of Australian open water body evaporation trends for current and future climates estimated from class a evaporation pans and general circulation models[J]. Journal of Hydrometeorology,2010,11（1):105-121.   
[9] MALIK A,KUMAR A.Pan evaporation simulation based on daily meteorological data using soft computing techniques and multiple linear regression[J].Water Resources Management,2015,29（6）:

1859 -1872.

[10] ZHANG Yongqiang,LIU Changming,TANG Yanhong,et al. Trends in pan evaporation and reference and actual evapotranspiration across the Tibetan Plateau[J].Journal of Geophysical Research : Atmospheres,2007,112,D12110,DOI:10.1029/2006JD008161.   
[11］YANG Hanbo,LI Zhe,LI Mingliang,et al. Inconsistency in Chinese solar radiation data caused by instrument replacement： Quantification based on pan evaporation observations[J]. Journal of Geophysical Research:Atmospheres,2015,120(8）:3191-3198.   
[12]MCMAHON T A,PEEL M C,LOWE L,et al. Estimating actual, potential,reference crop and pan evaporation using standard meteorological data:A pragmatic synthesis[J]. Hydrology and Earth System Sciences,2013,17(4） :1331.   
[13］曾燕,邱新法,刘昌明,等.1960—2000 年中国蒸发皿蒸发量的 气候变化特征[J].水科学进展,2007,（3）:311-318.［ZENG Yan,QIU Xinfa,LIU Changming,et al. Changes of pan evaporation in China in 1960—2000[J].Advances in Water Science,2007, (3):311-318.]   
[14］祁添垚,张强,王月,等.1960—2005 年中国蒸发皿蒸发量变化 趋势及其影响因素分析[J].地理科学,2015,35（12)：1599- 1606.[QI Tianyao,ZHANG Qiang,WANG Yue,et al. Spatiotemporal patterns of pan evaporation in 196O—2O05 in China:Changing properties and possible causes[J]. Progress In Geography, 2015,35(12):1599 -1606.]   
[15]刘敏,沈彦俊,曾燕,等.近50 年中国蒸发皿蒸发量变化趋势 及原因[J].地理学报,2009,64（3）:259－269.［LIU Min, SHEN Yanjun,ZENG Yan,et al. Changing trend of pan evaporation and its cause over the past 5O years in China[J].Acta Geographica Sinica,2009,64(3）:259-269.]   
[16］荣艳淑,张行南，姜海燕,等.长江上游区域蒸发皿蒸发量变化 及其对水分循环的影响[J].地球物理学报,2012,55（9）：2889 - 2897.[RONG Yanshu,ZHANG Xingnan,JIANG Haiyan,et al. Pan evaporation change and its impact on water cycle over the upper reach of Yangtze River[J]. Chinese Journal of Geophysics, 2012,55(9) :2889 -2897.]   
[17］邱新法,刘昌明,曾燕.黄河流域近40 年蒸发皿蒸发量的气候 变化特征［J].自然资源学报,2003,18（4）：437－442.［QIU Xinfa,LIU Changming,ZENG Yan. Changes of pan evaporation in the recent 4O years over the Yellow River Basin[J]. Journal of Natural Resources,2003,18(4) :437 -442.]

[18］荣艳淑，周云，王文.淮河流域蒸发皿蒸发量变化分析[J].水 科学进展,2011,22（1）:15-22.［RONG Yanshu,ZHOU Yun, WANG Wen.Analysis of pan evaporation changes in the Huaihe River Basin[J].Advances in Water Science,2011,22(1）:15- 22.]

[19］谢平,陈晓宏,王兆礼,等.东江流域实际蒸发量与蒸发皿蒸发 量的对比分析[J].地理学报,2009,64（3）：270-277.［XIE Ping,CHEN Xiaohong,WANG Zhaoli,et al.Comparison of actual evapotranspiration and pan evaporation[J].Acta Geographica Sinica,2009,64(3):270 -277.]   
[20］刘翠善，李海川，王国庆,等.澜沧江流域不同蒸发皿实测水面 蒸发之间的转换关系[J].华北水利水电大学学报（自然科学 版）,2017,38（6):72-77.[LIUCuishan,LIHaichuan,WANG Guoqing,et al. Conversional relationship between different pan evaporations for the Lancang River Basin[J]. Journal of North China University of Water Conservancy and Hydropower,2017,38 (6) :72 -77.]   
[21］李岳坦,李小雁,崔步礼,等.青海湖流域及周边地区蒸发Ⅲ蒸 发量变化（1961—2007 年）及趋势分析[J].湖泊科学,2010, 22(4）:616-624.[LI Yuetan,LI Xiaoyan,CUI Buli,et al. Trend of pan evaporation and its impact factors over Lake Qinghai Basin from 1961 to 2007[J]. Journal of Lake Sciences,2010,22（4）： 616 -624.]   
[22］李玲萍,李岩瑛,刘明春.石羊河流域1961—2005 年蒸发皿蒸 发量变化趋势及原因初探[J].中国沙漠,2012,32（3）：832－ 841.[LI Lingping,LI Yanying,LIU Mingchun. Change trend of pan evaporation and its causes in Shiyang River Basin during 1961—2005[J].Journal of Desert Research,2012,32(3）:832- 841.]   
[23］褚荣浩,申双和,李萌，等.小型与E-601型蒸发皿蒸发量对 比分析及其换算系数——以江苏省为例[J].气象科学，2018， 38(2）:247 -257.[CHU Ronghao,SHEN Shuanghe,LI Meng,et al.Comparative analysis of small and E-6Ol pan evaporation and its conversion coefficient: Taking Jiangsu Province as an example [J].Journal of the Meteorological Science,2018,38（2）:247 - 257.]   
[24］李毅,周牡丹.新疆地区棉花和甜菜需水量的统计降尺度预测 [J].农业工程学报,2014,30(22）:70-79.[LIYi,ZHOU Mudan.Projections of water requirements of cotton and sugar beet in Xinjiang based on a statistical downscaling method[J]. Transac

tions of the Chinese Society of Agricultural Engineering,2O14,30 (22):70-79.]

# Change of pan evaporation in Xinjiang and its periods based on wavelet analysis

QIN Rong’，LI Lin-chao²，YANG Xian³，YANG Hua’，YANG Yan-ling4，HE Ya-pingl (1Xinjiang Meteorology Information Center,Urumqi 830002,Xinjiang,China; 2Colege of Water Resources andArchitectureEngneering,NorthwestA&F University,Yangling210,Shaanxi,Cina; 3Xinjiang Meteorological Service Center,Urumqi 830oo2,Xinjiang，China; 4Hami Meteorological Bureau,Hami 8390oo,Xinjiang,China)

Abstract: The 2O cm-in-diameter and $E _ { 6 0 1 }$ type evaporation pans have been used in Xinjiang,China,but these two kindsof datasequences sofar are incomplete since the startof observation,especiallysince 2Oo3,the data have not been integratedand corrected,which restricted the useof pan evaporation dataand their further analysis.Based on the co-observation data of $2 0 ~ \mathrm { c m }$ -in-diameter ( $\phantom { } ^ { ' } E _ { 2 0 }$ ）and $E _ { 6 0 1 }$ pan evaporation ( $E _ { 6 0 1 }$ ）,the 57 meteorological stations in Xinjiang were selected and analyzed for the conversion coefficient $K$ between $E _ { 2 0 }$ and $E _ { 6 0 1 }$ from April to October.Taking the Kashi（in southern Xinjiang）and Tacheng stations（innorthern Xinjiang）（both had relatively long data sequences and are representative）as an example,the changes of $K$ at daily and monthly time scales were analyzed,and used later in the estimations of $E _ { 2 0 }$ values for the period from April 1 to September 3O in the span of 14 years （from 2O03 to 2016).Therefore,the complete data sequences of daily $E _ { 2 0 }$ for Kashi and Tacheng over the period from 1961 to 2O16 were obtained and could be further used in the spectral characteristics and periodic change analysis using thecomplex Morlet wavelet function.The results showed as folows:（1）The conversion coefficient of $E _ { 2 0 }$ and $E _ { 6 0 1 }$ in Xinjiang region had significant spatial differences from April to October,and $K$ values were larger in the southern Xinjiang than those in northern Xinjiang.（2）The complete daily $E _ { 2 0 }$ data series during the period from 1961 to 2O16 at Kashi and Tacheng station had typical periodical changes on yearly basis.The monthly $E _ { 2 0 }$ was the largest in July,and the annual $E _ { 2 0 }$ had an obvious increase trend.Daily,monthly and annual $E _ { 2 0 }$ values in Kashi were all larger than those in Tacheng.（3） The main period and quasi-period of $E _ { 2 0 }$ ranged within $2 - 1 6$ （204 years from January to December,and the main period were 7years for both stations.The quasi-periods at Kashi station were 2 and 4 years,but at Tacheng station they were 3 and6 years,respectively.This research could provide useful references for the interpolation and further application of pan evaporation in Xinjiang.

Key words:pan evaporation； conversion factors ； wavelet analysis ； Xinjiang