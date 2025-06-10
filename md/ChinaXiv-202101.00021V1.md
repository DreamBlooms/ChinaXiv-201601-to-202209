# 基于MODIS数据的吐鲁番盆地2001—2017年植被变化及水热组合影响分析

庞冉，王文

（河海大学水文水资源与水利工程国家重点实验室，江苏 南京210098）

摘要：中国西北干旱地区的气候变化及其对植被的影响一直备受关注。以地形特殊的吐鲁番盆地为研究对象，利用实测气象站点数据、再分析气象格点数据以及MODIS卫星遥感植被指数，采用趋势检验、线性回归、偏相关分析等方法，探究了该地区2001—2017年间的植被变化及其与水热组合特征之间的关系。结果表明：(1)吐鲁番盆地降水量整体没有显著变化，但北部山区降水增长较多,气温总体呈显著上升趋势，尤其是盆地底部中心区域增温较大。(2)全区域植被指数(NDVI)总体呈极显著上升趋势，山区及中心区域NDVI增长率较大。(3)受水汽来源和日照时长的影响，吐鲁番盆地周边山区高程 $3 0 0 0 \mathrm { m }$ 左右NDVI值最高，山区植被最好的坡向是西北坡。(4)吐鲁番盆地水热组合复杂，水分条件是大部分地区植被生长的主要限制因素，降水与NDVI有较好的正相关，在山区和荒漠区热量增加不利于植被生长，但中心区域受地下水和人类活动影响，水分的供给相对稳定，热量增加利于植被生长。

关键词：水热组合；植被变化；气候变化；NDVI;地形；MODIS 文章编号：

自20世纪80年代起，我国西北干旱地区的植被覆盖变化一直备受瞩目。施雅风等指出新疆部分地区自20世纪80年代中期开始就发出了气候趋于暖湿化的信号[1]。此后的许多研究成果也进一步证实了西北部分地区的暖湿化现象[2-3]。这意味着干旱地区水热组合关系有所改善，但受各方面复杂因素的影响，不同地区的植被响应是有所差异的，有些半干旱地区NDVI受年平均降水量控制的同时也受防沙治沙退耕还林等人类活动影响[4]。北疆植被覆盖较好且对水热条件变化的响应较为敏感和及时，而南疆植被较差，对水热条件变化的响应有明显滞后，植被生长的主要限制因素是气温[5],冬季降水的增加和其他三季气温的升高是新疆1982—2011年间植被变好的原因之一[6]。DUZQ等还指出沙漠和灌木NDVI对夜间变暖有显著响应[7]。此外，新疆地区植被对气候变暖的响应具有显著的高程上的差异，中海拔地区植被与平原区相比更加敏感[8]。张斯琦等[9]利用植被覆盖度(FVC)与降水、日照时数等6个环境因子做相关分析来探讨植被与环境因子的关系。可见现有研究多关注于较大空间尺度上植被生长与各种影响因子间的相关性和响应关系，对综合讨论干旱地区不同水热组合关系下的植被响应机制还不够深入，尤其是对小尺度特殊地形和人类活动在区域水热组合分布上的影响关注度还不够。本文选择地形特征显著的吐鲁番盆地，利用气象站实测降水和气温数据、GLDAS-2.1再分析降水和气温数据、MODIS遥感观测植被指数NDVI,采用趋势检验、线性回归、偏相关分析等方法，探究了吐鲁番盆地2001—2017年间的植被指数变化及其与气候因子、地形因子及人类活动间的关系，深入讨论不同水热组合对植被生长的影响机制在特殊地形区的适用性，为干旱地区小尺度特殊地形区植被变化研究提供新思路。

# 数据来源及研究方法

# 1.1 研究区概况

吐鲁番盆地位于新疆东部，深处内陆，三面环山，中部凹陷，总面积约 $5 . 8 5 { \times } 1 0 ^ { 4 } \mathrm { k m } ^ { 2 }$ 。盆地边缘海拔最高处为天山山脉的博格达峰 $5 4 4 5 \mathrm { m }$ ,海拔最低处为中部的艾丁湖 $- 1 5 4 \mathrm { m }$ ，是我国海拔最低的地方(图1)。由于远离海洋，又有高山阻挡，因此东部海洋水汽几乎无法到达，水汽输送主要依靠盛行西风，盆地内部气候干旱。其地貌结构具有明显的环带性特征，最外围为山地（高程 $> 1 5 0 0 \mathrm { ~ m ~ } ,$ ，物理风化强烈，是盆地物源的主要供应区；第二环带为洪积砾质戈壁(高程约 $3 0 0 \sim 1 ~ 5 0 0 ~ \mathrm { m } )$ ,地表物质粗大，地表水剧烈渗漏，地下水埋藏深，汇向盆地绿洲区；中心区为洪积一冲积平原(高程 $< 3 0 0 \mathrm { ~ m ~ }$ )，地面平坦，地下水埋藏深度大多在 $1 0 \sim 5 0 ~ \mathrm { m }$ ,有灌溉条件的区域成为灌溉农业区，在盆地底部最低处有盐沼。

# 1.2数据来源

本文分析中所用数据类型及来源见表1。

# 1.3研究方法

# (1)趋势性检验

采用非参数Mann-Kendall趋势性检验方法（以下简称MK检验）[10-11]对数据序列进行趋势性检验。MK检验的原假设 $\left( H _ { 0 } \right)$ 为没有单调趋势。其检验统计量 $Z$ 计算如下：

$$
Z = \left\{ \begin{array} { l l } { \displaystyle { { S - 1 } } } & { \displaystyle { { S > 0 } } } \\ { \displaystyle { { [ V a r ( S ) ] ^ { 1 / 2 } } } } & { \displaystyle { { S = 0 } } } \\ { \displaystyle { { { } } } } & { \displaystyle { { S < 1 } } } \end{array} \right.
$$

其中：

$$
V a r ( S ) = \left[ n ( n - 1 ) ( 2 n + 5 ) - \sum _ { t } t ( t - 1 ) ( 2 t + 5 ) \right] / \ 1 8 ,
$$

$$
S = \sum _ { i = 1 } ^ { n - 1 } \sum _ { j = i + 1 } ^ { n } s n g ( x _ { j } - x _ { i } ) ,
$$

$$
\begin{array} { r } { s n g \Big ( x _ { j } - x _ { i } \Big ) = \left\{ \begin{array} { l l } { + 1 } & { x _ { j } > x _ { i } } \\ { 0 } & { x _ { j } = x _ { i } , } \\ { - 1 } & { x _ { j } < x _ { i } } \end{array} \right. } \end{array}
$$

式中： $x _ { j }$ 和 $x _ { i }$ 是时间序列中 $j$ 和 $i$ 时间点的数据值。

$Z$ 值呈标准正态分布，根据 $Z$ 值可以得到统计检验的概率 $p$ 值，设定 $\alpha = 0 . 0 1 , 0 . 0 5$ 和0.1三个显著性水平，根据 $Z$ 值的正负与 $p$ 值大小将趋势类型分为7个等级，见表2。

# (2)一元线性回归

采用一元线性回归方法进行NDVI及气候因子随时间的线性变化率分析，即 $\scriptstyle Y = a X + b$ ,其中自变量$X$ 为时间，因变量Y为待分析的植被指数或气候因子，斜率 $\boldsymbol { a }$ 就是所分析的因子随时间的变化率。

# (3)偏相关分析

在控制其他变量线性影响的条件下分析两变量间的线性相关性，采用偏相关系数 $r$ 来表征两个因子之间的相关程度。本文在偏相关系数计算中仅考虑NDVI、降水、气温三个要素，因此只使用三变量偏相关分析方法。剔除 $z$ 变量影响下的 $x$ 与 $y$ 的偏相关系数 $r _ { x y - z }$ 计算如下：

$$
r _ { x y - z } = \frac { r _ { x y } - r _ { x z } r _ { y z } } { \sqrt { ( 1 - r _ { x z } ^ { 2 } ) ( 1 - r _ { y z } ^ { 2 } ) } }
$$

式中： $r _ { x y } \mathrm { , } r _ { x z } \mathrm { , }$ $r _ { y z }$ 为 $x , y , z$ 变量两两之间的相关系

![](images/49a511fbcfad41cf46bbdfef23ece47c480690ce8f9354e5c9ea6992b2a1a4b7.jpg)  
图1研究区示意图  
Fig.1Study area of Turpan basin

# 干半区地理

表1研究数据Tab.1 Research data  

<html><body><table><tr><td>数据类型</td><td>来源</td><td>数据长度(时间)</td><td>时间尺度</td><td>空间分辨率</td></tr><tr><td>遥感数据</td><td>MODISMOD13A1 NDVI</td><td>2001—2017</td><td>16d</td><td>500 m</td></tr><tr><td rowspan="3">降水/气温数据</td><td>MODISMOD13C2NDVI</td><td>2001—2017</td><td>逐月</td><td>0.05°</td></tr><tr><td>地面站点数据</td><td>2001—2017</td><td>逐日</td><td>站点</td></tr><tr><td>全球陆面数据同化系统(GLDAS-2.1)</td><td>2001—2017</td><td>逐月</td><td>0.25°</td></tr><tr><td>地形数据</td><td>SRTMDEM数据</td><td>1</td><td>一</td><td>250 m</td></tr><tr><td>土地覆盖数据</td><td>GlobeLand30遥感解译</td><td>2010</td><td>年</td><td>30m</td></tr><tr><td>社会经济数据</td><td>吐鲁番统计年鉴</td><td>2001—2017</td><td>年</td><td>二</td></tr></table></body></html>

表2MK检验趋势结果分级  
Tab.2 Classification of trend results ofMK test   

<html><body><table><tr><td>Z</td><td>p值</td><td>类别</td><td>趋势性</td></tr><tr><td>Z > 2.32</td><td>p<0.01</td><td>3</td><td>极显著上升趋势</td></tr><tr><td>2.32≤Z <1.64</td><td>0.01≤p <0.05</td><td>2</td><td>显著上升趋势</td></tr><tr><td>1.64≤Z<1.28</td><td>0.05≤p <0.1</td><td>1</td><td>轻微上升趋势</td></tr><tr><td>-1.28≤Z≤1.28</td><td>0.1≤p</td><td>0</td><td>无变化趋势</td></tr><tr><td>-1.64≤Z<-1.28</td><td>0.05≤p <0.1</td><td>-1</td><td>轻微下降趋势</td></tr><tr><td>-2.32≤Z<-1.64</td><td>0.01≤p <0.05</td><td>-2</td><td>显著下降趋势</td></tr><tr><td>Z<-2.32</td><td>p<0.01</td><td>-3</td><td>极显著下降趋势</td></tr></table></body></html>

数。偏相关系数取值在 $- 1 \sim 1$ ,绝对值越大表示相关性越大。

# 2结果与分析

# 2.1吐鲁番盆地气候变化

2.1.1 降水变化受西风急流和高山抬升作用，吐鲁番盆地降水相对较多的地方集中在北部及西部的天山余脉，北部山区最高可达 $4 0 0 \mathrm { m m }$ ,西南部山区降水量约 $2 5 0 \sim 3 0 0 \mathrm { m m }$ ,盆地内部则降水稀少，小于 $2 0 \mathrm { m m }$ （以吐鲁番市为例，1956—2000年的年平均降水量为 $1 5 . 8 ~ \mathrm { m m }$ ),并且自西北向东南递减。吐鲁番盆地有2个国家基准气象站，即吐鲁番站和达坂城站，图2a、2b是这2个站2001—2017年的逐年降

3530252 (a) 160 (b)  
ww/ w/ 1402015 盘 10010 605 400 202230 4 5 6 1 10 20 0 421 4012年份 年份  
18.0 0.78  
17.5 (c) 0.76 (d)  
17.0 0.74  
16. 票 0.70  
15.5 0.66  
15.0 0.64  
14.5 0.621415162020 20 20 421 20 20 20 20 00年份 年份87E 88E 89E 90E 91E 87E 88E 89E 90°E 91E(a) 达坂城 N (b) ? 达坂城 N了  
104 托克逊县 吐鲁番鄯善县 4304 2 托克逊县吐鲁番鄯善县 400▲ 艾丁湖 1 艾丁湖图例 图例 M趋势分级 变化率mm·a-1  
4 2 4 4 40 440 ▲城市 20 ▲城市湖泊 0 120 km 0 ▲湖泊 0 120 km87E 88E 89°E 90°E 91E 87E 88E 89E 90E 91E87E 88E 89°E 90°E 91E 87E 88E 89E 90°E 91E(c） 广达坂城 N (d) 广达坂城 N? ?  
404 L 托克逊县吐鲁番善县 4304 20 托克逊县 吐鲁番鄯善县 4艾丁湖图例 W M 图例  
N 趋势分级 0 城市 4 4 变化率℃·a- 0.2 城市 1 423 湖泊 0 120 km 0.1 湖泊 0 120km87E 88E 89°E 90°E 91E 87E 88E 89E 90°E 91E

图22001—2017年逐年降水量(吐鲁番站(a)达坂城站(b))与逐年平均气温(吐鲁番站(c)达坂城站(d)变化 Fig.2Changes of precipitation(Turpan station (a)and Dabancheng station (b))and temperature(Turpan station(c) and Dabancheng station (d)) from 2001 to 2017

水量变化过程。从图2中可以看出，吐鲁番站作为中心区的代表站，21世纪以来的多年平均降水量为$1 4 . 8 ~ \mathrm { m m }$ ,年降水量在 $0 \sim 3 0 ~ \mathrm { m m }$ 间波动并有轻微的下降；而达坂城站作为山区的代表站，相应时间段内多年平均降水量为 $7 7 . 1 \ \mathrm { m m } , 2 1$ 世纪初期年平均降水量不断减少，进入20年代后稍有缓解

图3a、3b是根据GLDAS-2.1再分析数据计算的吐鲁番盆地2001—2017年年降水量变化趋势及变化率的空间分布情况，可以看出吐鲁番盆地降水量整体没有显著的变化趋势，但北部及西部山区年降水量都有明显的增加，增长率可达 $4 0 \ \mathrm { m m \cdot a ^ { - 1 } }$ ,北部山区年降水量上升趋势更加显著；南部荒漠区也有显著的上升趋势，但增长率非常小；西北角山区则有较显著的减少趋势；中心区无显著变化趋势，但降水量有所减少。

2.1.2气温变化吐鲁番盆地多年平均气温在 $- 3 \sim$ $1 7 \ \mathrm { { ^ { \circ } C } }$ 之间，中心区气温最高(1956—2000年吐鲁番市年平均气温为 $1 4 . 3 \mathrm { ~ \textdegree C }$ ），海拔越高气温越低(1957一2000年达板城年平均气温为 $0 . 6 5 ~ \mathrm { ^ { \circ } C }$ )。多年月平均气温差达 $4 2 \mathrm { { ^ \circ C } }$ ,极端最高和最低气温相差近 $7 5 ~ \mathrm { { ^ { \circ } C } }$ 。图2c、2d展示了2001—2017年吐鲁番站和达坂城站的年平均气温变化过程。吐鲁番站年平均气温略呈上升趋势，多年平均气温 $1 6 . 0 ~ \mathrm { ^ { q } C }$ ，与1956—2000年相比上升了 $1 . 7 \ \mathrm { ^ { \circ } C } , 2 0 1 6 { \mathrm { - } 2 0 1 7 }$ 年上升尤其显著;达坂城站的年平均气温基本稳定，多年平均气温为 $0 . 7 2 ^ { \circ } \mathrm { C }$ ,与1957—2000年平均气温相比上升了 $0 . 0 7 ^ { \circ } \mathrm { C }$ 。图3c、3d展示了根据GLDAS-2.1再分析数据计算的吐鲁番盆地2001—2017年气温变化趋势及变化率的空间分布情况。从变化趋势看出，北部山区和西部山前地带呈轻微增温趋势，其他大部分地区均呈极显著增温趋势。从增温幅度来看，大部分地区的增长率为 $0 . 2 \sim 0 . 3 \ \mathrm { ^ { \circ } C \cdot a ^ { - 1 } }$ ，只有西部山区的变化率较低,为 $0 \sim 0 . 1 5 ^ { \circ } \mathrm { C } \cdot \mathrm { a } ^ { - 1 }$ 。

# 2.2植被空间分布与年际变化特征

吐鲁番盆地土地覆盖类型以裸地为主，山区和山前地带多为草地，有零星森林(图4a)。山区降水在山前入渗并以地下水的形式汇集到盆地中心地区，形成绿洲，同时地下水也为艾丁湖提供了主要补给来源。中心绿洲区有耕地分布，艾丁湖区分布有少量水体和湿地吐鲁番盆地2001一2017年多年平均NDVI(归一化植被指数)分布情况见图4b，全区NDVI都在0.4以下，荒漠区则普遍在0.05以下；中心绿洲区尤其是3个城市(吐鲁番、托克逊、鄯善)附近的植被指数较高，在0.3左右；北部山区植被指数0.2左右，西部山区略高(约 $0 . 2 \sim 0 . 3 \$ )。

对2001—2017年吐鲁番盆地NDVI年均值变化趋势及变化率见图 $\mathrm { 5 a } \mathrm { , 5 b }$ ，几乎全区域NDVI值都有极显著增长。北部山区的NDVI增长率最大，约$0 . 0 0 5 \mathrm { a } ^ { - 1 }$ ，其次是中心绿洲区，西部山区山前地带也呈现增长态势。可见，吐鲁番盆地的植被覆盖总体逐渐变好。

分别将全区域和中心区域的逐年NDVI值进行

87E 88E 89E 90°E 91E 87E 88E 89E 90°E 91E (a) N (b) N ·达坂城 达坂城   
434 托克逊县吐鲁番 鄯善县 40 404 托克逊县吐鲁番 鄯善县 423 艾丁湖 艾丁湖 图例 图例 覆盖类型 NDVI值   
444 耕地 水体 44 2 4 草地 人造地表 0.3 灌木地 冰川和永久积雪 0.2 ▲城市 地 城市 0 120 km 1 01 ▲湖泊 0 120km 87E 88E 89°E 90E 91E 87E 88E 89E 90°E 91E

![](images/e3f4e4062255c9f9a69e385def9d08c979ed0265f9bf895ac81ad7f35eed2f47.jpg)  
干旱区地理  
图4吐鲁番盆地土地覆盖类型及多年平均NDVI  
Fig.4Land cover type (a) and average NDVI (b) in Turpan basin   
图5吐鲁番盆地2001—2017年平均NDVI变化趋势(a)及变化率(b)  
Fig.5Trend results (a) and gradient (b) of NDVI in Turpan basin from 2OO1 to 2017   
图6吐鲁番盆地年平均NDVI逐年变化过程线 Fig.6NDVI changes in the whole region (a) and central region (b) of Turpan basin from 20O1 to 2017   
图7吐鲁番盆地中心区夏季不同区间植被覆盖度占百分比逐年变化(2001—2017)  
Fig.7Changes of vegetation coverage in central region of Turpan basin in summer from 20O1 to 2017

面平均(图6)，可以看出，中心区NDVI高于全区域平均水平。2001—2017年间全区域NDVI整体呈现上升趋势,增长率为 $0 . 0 0 0 7 6 \mathrm { a } ^ { - 1 }$ ,增长现象突出表现在2011年之后。结合图2可以看出，NDVI的波动与达坂城的降水变化有较好的一致性，说明山区降水量的变化对全区域的植被状况有很大关系。中心区NDVI则是在波动过程中不断上升，增长率为$0 . 0 0 0 8 6 \mathrm { a } ^ { - 1 }$ 。

进一步选取植被生长最好的6～8月NDVI值对吐鲁番中心地区探究不同植被覆盖度区域的面积百分比变化情况。根据上文对荒漠区NDVI值范围

0.1100.1050.1000.09 o0.0850.080 3 全区域一中心区00.07510120 2205 4000 2005 9007 2007 8000 20030 1 1055 4421 2455 100年份

的分析， $N D V I < 0 . 0 5$ 时可以看作裸土区。因此利用像元二分模型计算植被覆盖度：

$$
F V C = \frac { N D V I - N D V I _ { s o i l } } { N D V I _ { v e g } - N D V I _ { s o i l } }
$$

式中： $N D V I _ { s o i l }$ 取0.05, $N D V I _ { v e g }$ 取每年夏季 $6 \sim 8$ 月最大值合成后的中心区NDVI最大值（约0.7），$F V C > 6 0 \%$ 为高覆盖度， $3 0 \% < F V C { \leqslant } 6 0 \%$ 为中覆盖度， $0 < F V C { \leqslant } 3 0 \%$ 为低覆盖度。

由图7可以看出吐鲁番中心地区以低植被覆盖度为主，植被覆盖度总体都处于逐年波动上升中，

8 →覆盖度一\*高覆盖度 76 78 %/  
74  
72  
70  
68  
4001 2200 1000 4000 2005 2000 4207 8000 6000 2010 011 2022 055 4001 2055 1020  
年份

低植被覆盖度占比的增加说明在荒漠与绿洲的混合过渡带存在着荒漠向绿洲转变的趋势，植被覆盖情况逐年变好。绿洲、荒漠以及交错带之间的这种互相转换在新疆和田地区塔里木盆地克里雅河流域等地也有体现[12]

# 2.3NDVI时空变化影响因子

2.3.1NDVI空间分布与地形因子的关系NDVI时空分布主要取决于水热条件，而地形对地表水热条件有很大影响，如高程[13]、坡向[14]等。在北侧天山南坡与西侧天山东坡各选取一个跨越不同高程范围的矩形样本区，即 $8 9 ^ { \circ } \sim 8 9 . 5 ^ { \circ } \mathrm { E } , 4 2 . 5 ^ { \circ } \sim 4 3 . 5 ^ { \circ } \mathrm { N }$ ，以及 $8 7 ^ { \circ } \sim 8 8 ^ { \circ } \mathrm { E } , 4 2 . 5 ^ { \circ } \sim 4 3 ^ { \circ } \mathrm { N }$ 区间，对这二个区间ND-$\boldsymbol { { W } }$ 与高程、坡向的关系分别进行分析。

图8是样本区内历年7月份（NDVI最大值月份）的NDVI与高程散点图。由图可知，北侧天山南坡样本区海拔 $2 0 0 \mathrm { ~ m ~ }$ 以下区域为绿洲区，由于地表覆盖类型复杂（有农田、荒漠），NDVI波动范围很大（约$0 . 1 \sim 0 . 6 )$ ,峰值(约0.6)出现在海拔约 $2 9 0 0 \mathrm { m }$ 左右，在 $4 0 0 0 \mathrm { m }$ 以上区域NDVI降至O附近，地表覆盖为常年积雪；西侧天山东坡的NDVI值在 $5 0 0 \mathrm { m }$ 左右处约0.05，反映地表覆盖为荒漠，随海拔升高NDVI值逐渐增加，峰值(约0.65)出现在 $3 ~ 1 0 0 \mathrm { m }$ 左右，之后逐渐下降，但在 $4 0 0 0 \mathrm { m }$ 左右区域仍有一定的植被覆盖。可以看出，虽然吐鲁番盆地北侧天山与西侧天山的两个样本区纬度相近，太阳辐射条件基本相同，但西侧天山植被条件优于北侧天山。这反映出在热量条件相同情况下，由于吐鲁番盆地周边天山地区的水汽主要来源是西风环流，西侧天山的水汽条件略优于北侧天山[15],从而西侧天山的植被生长也略优。

进一步在样本区中选取北侧与西侧天山坡度大于0.3的栅格 $( 2 5 0 \mathrm { m } \times 2 5 0 \mathrm { m } )$ ,分析坡向与NDVI均值的关系。不同坡向NDVI情况见图9，北侧天山西北坡向(约 $3 1 0 ^ { \circ } \sim 3 3 0 ^ { \circ }$ )植被最好，其次是东面和东南坡向，北面坡向植被最差;西侧天山北面、西北、西面坡向植被最好，东南坡向(约 $1 4 0 ^ { \circ }$ 左右)相对较

![](images/603d567f687de711298448cf4deb4fb2452928d2ed498450b3bcfc9dc13d85b5.jpg)  
图8吐鲁番北侧(a)与西侧(b)天山样本区高程与NDVI的关系

Fig.8RelationshipbetweenelevationandNDVIoftheTanshan Mountainsampleareainthenorth (a)andwest(b)ofTurpanbasin

![](images/80575a1b39accf7138552dd416413b7ea08aa1bae7a94a917dee7c9b75518922.jpg)  
图9吐鲁番北侧(a)与西侧(b)天山样本区NDVI在各个坡向变化图

Fig.9Relationship between aspect and $N D W$ of the Tianshan Mountain sample area in the north (a) and west (b) of Turpan basin

# 干旱区地理

差。由此可见，不论是北侧天山还是西侧天山，植被条件最好的都是西北坡向，其原因在于，西侧坡向是水汽条件最好的坡向（因为水汽来源主要来自西风环流），而西北一侧的半荫蔽山坡在满足了植物生长对阳光需求的同时，直射时间又比朝南坡向相对较短、蒸散发量较小。也就是说，在吐鲁番盆地周边山地，对植物生长而言，西北坡向是水份条件与热量条件的组合最优的坡向。

# 2.3.2不同地貌区NDVI与气候因子的偏相关性

利用吐鲁番盆地2001—2017年 $6 \sim 8$ 月NDVI与同期气候因子序列（包括累积降水量和平均气温)进行偏相关分析，偏相关系数分布如图10所示。可以看出，全区域夏季平均NDVI与降水都有一定的正相关关系，尤其是北部海拔 $3 0 0 0 \mathrm { m }$ 以上的山区和山前戈壁(海拔 $1 \ 0 0 0 \sim 2 \ 0 0 0 \ \mathrm { m } ,$ ，相关系数达到0.6以上。但在盆地中部的洪积一冲积平原带，由于水分来源不仅来自于降水，还有相当重要的来源是地下水，因此NDVI与降水的相关性相对较弱。

NDVI与气温的偏相关关系有明显的区域特点，北部海拔 $3 0 0 0 \mathrm { m }$ 以上的山区和东南荒漠地区NDVI与气温总体呈一定的负相关，这反映出当气温增高时，蒸散发量会有所增加，使植物可利用水量减少，因而NDVI与气温呈现一定的负相关。但在海拔$1 0 0 0 \mathrm { m }$ 以下的中心区域，NDVI与降水的相关性较弱，与气温的正相关性则很强，相关系数达到0.7以上，推测其原因是这里的地下水提供了相对稳定的水分供给来源，在这种情况下夏季气温的适当增高有助于植被的生长。总体来看，由于不同地貌条件下水份蓄存情况不同，从而植物生长对气温、降水条件变化的响应特征也有所不同。

# 3关于水热组合关系对植被时空变化的影响机理讨论

# 3.1自然因素对植被时空变化的影响

植被变化受控于气候变化，特别是气温和降水的变化[16]。适宜的水热组合是植被生长的重要保证，但是在不同干湿环境下影响植被生长状况的主导因素有所差别。除了高寒地区，水资源可利用量是植被生长共同的控制因素[17]。干旱地区植被对降水的敏感度高于气温，湿润地区植被对气温的敏感度高于干旱地区。当受单气候因素影响较大时，植被生长往往会受到一定的抑制，如我国黄土高原西北部和西部干旱地区，降水量或气温分别远低于全区域平均水平,植被生长受到遏制[18]。在以水分为主要限制因素的北纬 $3 0 ^ { \circ } \sim 6 0 ^ { \circ }$ 的温带，降水丰富的地区植被生产力与气温通常呈强烈正相关，而降水逐年减少的地区，干旱加剧，植被指数NDVI与气温的负相关性越发显著[19]。比如在中国西北地区干旱区植被覆盖变化的驱动因子主要是降水，NDVI与降水总体呈现正相关关系，而气温的上升会加速地表蒸发,加剧植被水分流失,遏制植被的生长[20-21]。另一方面，植被对降水与气温的响应关系会随降水或气温的变化而发生一定程度的变化。热量积累的增加又往往伴随着植被生长对降水敏感性的增强[2]

受水汽来源多样、地形组合复杂的影响，新疆地区水热条件组合复杂，并且不同的植被覆盖类型对水热条件的要求不同，因而水热组合条件对植被的影响也就更加复杂。刘洋等发现新疆以林地为主要植被覆盖类型的山区水分相对充足，辐射增强和光照时长增加导致气温的上升的同时也延长了植被的生长期，而在以小灌木等耐盐碱植被为主要

87E 88E 89E 90°E 91E 87E 88E 89E 90°E 91E (a) 达坂城 2 (b) 达坂城 N   
2004 托克逊县吐鲁番 鄯善县 40 4234 托克逊县吐鲁番 鄯善县 433 艾丁湖 二 艾丁湖 图例 图例 相关系数 相关系数   
2 1.0 44 44 1.0 2 8 ▲城市 8 城市 1.5 湖泊 0 120 km 5 ▲湖泊 0 120km 87E 88E 89E 90E 91E 87E 88E 89E 90°E 91E

植被类型的绿洲和荒漠交错带，水分条件则是影响植被生长的主要因素[23]。不同季节里植被生长的主要影响因子不同，杜加强等发现新疆植被受水热条件共同控制且季节差异显著，春、秋季时植被覆盖与气温的相关性大于降水量，夏季时则相反[24]地理位置不同带来的水热条件差异使得植被对气候的响应各不相同，慈晖等指出北疆植被覆盖最好且对水热条件变化的响应较为敏感，而南疆植被较差，对水热条件变化的响应有明显滞后，植被生长的主要限制因素是气温[5]

作为干旱地区的一部分，吐鲁番盆地全区域降水稀少，植被生长的限制因素是水分条件，因此总体上降水与NDVI呈正相关，也就是说降水的增加有利于植被的生长。但热量条件对植被生长的影响则较为复杂，对大部分区域来说辐射增强和光照时长增加引发的气温上升会导致蒸散发量增加，加重缺水程度，不利于植被的生长，但由于特殊地形的作用，全区域降水几乎都汇集至海拔 $1 0 0 0 \mathrm { m }$ 以下的中心区域,形成丰富的地下水，尤其是在绿洲区人类抽取地下水对耕地、果园进行灌溉使得此区域水分条件较好，因而植被生长对降水的依赖性小于周边区域，气温的上升反而使得热量条件更好，利于植被生长。水热组合的不同还体现在坡向上，湿润地区水分条件好，阳坡由于光照充足，植被生长通常优于阴坡，但在干旱半干旱地区，阳坡的蒸散发能力强于阴坡，反而限制了植物的生长。如，祁连山荫蔽(朝北)或半荫蔽(朝东)山坡阳光直射时间相对较短，蒸散发量较小，土壤的水分胁迫较小，更加适宜植被生长25。吐鲁番盆地西北角的地形缺口是中纬度盛行西风带来大西洋水汽的入口，东西走向的北侧天山水汽条件在各个坡向相对均匀，因此热量条件较合适的西北及东南坡向的植被指数较高；西侧天山则是近似南北走向，水汽条件在各个坡向差异较大，作为迎风坡的西北坡向水汽充沛，光照适宜,植被指数最高，背风坡的东南坡向一带水汽条件差，且光照时间相对较长，不利于植被生长。可见吐鲁番盆地面积小高差大、三面高中心低的特殊地形使得该地区水热组合情况复杂，植被与地形、气象因子之间的关系也表现得比较复杂。

# 3.2人类活动对植被时空变化的影响

中心区域人类农耕活动引起的水热组合再分配对NDVI有很大的影响。图11是中心区域2001—

2017年夏季NDVI以及同期耕地及果园地等主要作物种植面积逐年变化过程线，可以看出中心区夏季NDVI和主要作物种植面积逐年变化基本一致。受气象因素影响，个别年份(如2014年)由于降水不足，气温偏低，热量条件较差，其NDVI变化不同步。实际上，人类活动对热量条件的改善十分有限，但却能使水量的时空分配得到一定程度的调节，从而改变区域水热条件的组合关系。如2006年，中心区降水量极低，但热量条件相对可观，农业水利设施的改善和农药化肥的使用，使得农作物生长条件改善，由此带来的对植被覆盖的影响时常会大于降水等气象要素[26-27]。吐鲁番盆地中心区域位于整个地区的最底部，虽然降水量极少，但周边山区的降水以地下径流形式汇集至此，人们通过取用地下水满足作物生长的耗水需求，因而降水的波动变化对植被生长的影响相对较弱，植被生长会受到地下水埋深或外来水分输入量的较大影响，农业灌溉为中心区域农耕作物提供了较好的水分条件，水分供给充足时，热量条件就会成为植被生长的主要影响因素。

![](images/19e3b54b204319f4ef066f089ec0e11a8344f48a21106a21fafc90adb2234154.jpg)  
图11吐鲁番盆地中心区2001—2017年夏季平均NDVI与主要作物种植面积变化  
Fig.11 Changes of average NDVI in summer and planting area of main crops in Turpan basin from 2OO1 to 2017

# 4结论

本文着眼于吐鲁番盆地2001—2017年降水、气温等气候因子的变化，结合该地区面积小高差大、三面高中心低的特殊地形和人类活动影响，深入分析了自然及人类活动因素在干旱地区水热组合分配中的作用，突出了干旱地区小尺度区域水热组合关系的特殊性和复杂性。结果表明：

(1)吐鲁番盆地降水量整体没有显著变化，但

# 干半区地理

北部山区降水增长较多，气温总体呈显著上升趋势，尤其是盆地底部中心区域增温较大。

(2)全区域植被指数(NDVI)总体呈极显著上升趋势，山区及中心区域NDVI增长率较大。(3)受水汽来源和日照时长的影响，吐鲁番盆地山区高程 $3 0 0 0 \mathrm { m }$ 左右NDVI值最高，山区植被最好的坡向是西北坡。(4)吐鲁番盆地水热组合复杂，水分条件是大部分地区植被生长的主要限制因素，降水与NDVI有较好的正相关，在山区和荒漠区热量增加不利于植被生长，但中心区域受地下水和人类活动影响，水分的供给相对稳定，热量增加利于植被生长。

# 参考文献(References)

[1]施雅风,沈永平,胡汝骥.西北气候由暖干向暖湿转型的信号、 影响和前景初步探讨[J].冰川冻土,2002,24(3):219-226.[SHI Yafeng,SHEN Yongping,HU Ruji. Preliminary study on signal, impact and foreground of climatic shift from warm-dry to warmhumid in Northwest China [J]. Journal of Glaciologyand Geocryology,2002,24(3): 219-226.]   
[2]贺晋云,张明军,王鹏,等.新疆气候变化研究进展[J].干旱区研 究,2011,28(3): 499-508.[HE Jinyun, ZHANG Mingjun,WANG Peng,et al.New progress of the study on climate change in Xinjiang[J].Arid Zone Research,2011,28(3): 499-508.]   
[3]热孜宛古丽·麦麦提依明,杨建军,刘永强,等.新疆近54年气 温和降水变化特征[J].水土保持研究,2016,23(2):128-133. [Reziwanguli $\cdot \cdot$ Maimaitiyiming,YANG Jianjun,LIU Yongqiang. Characteristics of changes in temperature and precipitation in Xinjiang in recent 54 years[J]. Research of Soil and Water Conservation,2016,23(2): 128-133.]   
[4]岳辉,刘英.近15a陕西省植被时空变化与影响因素分析[J].干 旱区地理,2019,42(2): 314-323.[YUE Hui,LIU Ying.Vegetation spatiotemporal variation and its driving factors of Shaanxi province in recent 15 years [J].Arid Land Geography,2019,42(2): 314-323.]   
[5]慈晖,张强.新疆NDVI时空特征及气候变化影响研究[J].地球 信息科学学报,2017,19(5): 662-670.[CI Hui, ZHANG Qiang. Spatio- temporal patterns of NDVI variations and possible relations with climate changes in Xinjiang province[J]. Journal of Geoinformation Science,2017,19(5): 662-670.]   
[6]ZHANG R, OUYANG Z, XIE X,et al. Impact of climate change on vegetation growth in arid northwest of China from 1982 to 2011 [J]. Remote Sensing,2016, 8(5): 364.   
[7]DU ZQ, ZHAO J,PAN HH,et al. Responses of vegetation activity to the daytime and nighttime warming in northwest China[J]. Environ Monit Assess,2019,191(12): 1100-1109. [8]马勇刚,张弛,塔西甫拉提·特依拜.中亚及中国新疆干旱区植 被物候时空变化[J].气候变化研究进展,2014,10(2):95-102. [MA Yonggang,ZHANG Chi, Tiyip Tashpolat. Spatial- temporal change of vegetation phenology in arid zone of central Asia and Xinjiang,China[J]. Climate Change Research,2014,10(2): 95-   
102.] [9] 张斯琦,陈辉,宋明华,等.2000—2015年柴达木盆地植被覆盖 度时空变化及其与环境因子的关系[J].干旱区地理,2019,42 (5): 1124-1132.[ ZHANG Siqi, CHEN Hui, SONG Minghua,et al.Spatial and temporal variation of fractional vegetation cover and its relationship with environmental factors in the Qaidam Basin during 2000—2015[J].Arid Land Geography，2019,42(5):   
1124-1132.] [10]Mann HB.Non-parametric tests against trend[J]. Econometrica,   
1945, 13(3): 245-259. [11]Kendall, M.G..Rank Correlation Methods[M]. Griffin.London.   
1975. [12] 胡江玲,刘传胜.新疆典型绿洲土地覆盖动态变化研究[J].新疆 师范大学学报(自然科学版),2007,26(1):78-82.[HU Jiangling, LIU Chuansheng. The study on typical oasis land cover dynamic changes in Xinjiang[J].Journalof Xinjiang Normal University(Natural Sciences Edition),2007,26(1): 78-82.] [13] 王钊,彭艳,权文婷,等.秦岭森林物候时空分布特征及对水热 条件的响应[J].干旱区地理,2019,42(5):1048-1058.[WANG Zhao,PENG Yan, QUAN Wenting,et al. Characteristic of plant phenologyand its response to the hydrothermal conditions over Qinling Mountains[J].AridLandGeography,2019,42(5):1048-   
1058.] [14] 王玉,安沙舟,董乙强,等.坡向对新疆天山北坡山地草原植被 多样性的影响[J].新疆农业科学,2018,55(1):156-163. [WANG Yu,AN Shazhou,DONG Yiqiang,et al.Efects of slope aspect on the vegetation diversity of mountain steppe in the northern slopeof Tianshan Mountain, Xinjiang[J]. Xinjiang Agricultural Sciences,2018,55(1): 156-163.] [15] 王可丽,江灏,赵红岩.西风带与季风对中国西北地区的水汽输 送[J].水科学进展,2005,16(3):432-438.[WANGKeli,JIANG Hao,ZHAO Hongyan.Atmospheric watervaportransport from westerlyand monsoon over the northwest China[J].Advances in Water Science,2005,16(3): 432-438.] [16]DE BEURS K M, HENEBRY G M. Land surface phenology and temperature variation in the International Geosphere- Biosphere Program high-latitude transects[J]. Global Change Biology,2005,   
11(5): 779-790. [17]FORKEL M,MIGLIAVACCA M, THONICKE K,et al. Codominant water control on global interannual variability and trends in landsurface phenologyand grenness[J]. Global Change Biology,   
2015, 21(9): 3414-3435. [18] 张,任志远,韦振锋.近12年来黄土高原植被覆盖对年内水 热条件的响应[J].资源科学,2013,35(10):2017-2023.[ZHANG Chong,REN Zhiyuan,WEI Zhenfeng.Vegetation responses to intra-annual hydrothermal conditions on the Loess Plateau[J]. Resources Science,2013,35(10): 2017-2023.]   
[19]PIAO SL,NAN H,HUNTINGFORD C,etal. Evidence for a weakening relationship between interannual temperature variability and northern vegetation activity[J]. Nature Communications, 2O14,5(1).   
[20] 李震,阎福礼,范湘涛.中国西北地区NDVI变化及其与温度和 降水的关系[J].遥感学报,2005,9(3):308-313.[LI Zhen,YAN Fuli,FAN Xiangtao.The variability of NDVI over northwest China and its relation to temperature and precipitation[J]. Journal of Remote Sensing,2005,9(3): 308-313.]   
[21] 杨光华,包安明,陈曦,等.1998—2007年新疆植被覆盖变化及 驱动因素分析[J].冰川冻土，2009,31(3):436-445.[YANG Guanghua,BAO Anming,CHEN Xi. Study of the vegetation cover change and its driving factors over Xinjiang during 1998—2007 [J]. Journal of Glaciology and Geocryology,2009,31(3): 436-445.]   
[22]DU J,HE B,PIATEK K B,et al.Interacting effects of temperature and precipitation on climatic sensitivity of spring vegetation green-up in arid mountains of China[J]. Agricultural and Forest Meteorology,2019,269-270: 71-77.   
[23] 刘洋,李诚志,刘志辉,等.1982—2013年基于GIMMS-NDVI的 新疆植被覆盖时空变化[J].生态学报,2016,36(19):6198- 6208.[LIU Yang,LI Chengzhi,LIU Zhihui, Assessment of spatiotemporal variations in vegetation cover in Xinjiang from 1982 to 2013 based on GIMMS-NDV/[J],Acta Ecologica Sinica,2016,36 (19): 6198-6208.]   
[24]杜加强,贾尔恒·阿哈提,赵晨曦，等.1982-2012年新疆植被 NDVI的动态变化及其对气候变化和人类活动的响应[J].应用 生态学报,2015,26(12):3567-3578.[DU Jiaqiang,JIAERHENG Ahati,ZHAO Chenxi.Dynamic changes in vegetation NDVI from 1982 to 2O12 and its responses to climate change and human activities in Xinjiang,China[J]. Chinese Journal of Applied Ecology, 2015,26(12): 3567-3578.]   
[25]JIN X,WANL,ZHANGYK,etal. Quantification of spatial distribution of vegetation in the Qilian Mountain area with MODIS NDVI[J].International Journal of Remote Sensing,2Oo9,30(21): 5751-5766.   
[26] 信忠保,许炯心,郑伟.气候变化和人类活动对黄土高原植被覆 盖变化的影响[J].中国科学(地球科学):2007,(11):1504-1514. [XIN Zhongbao,XU Jiongxin,ZHENG Wei.Effects of climate change and human activities on vegetation cover on the Loess Plateau [J]. Scientia Sinica (Terrae),2015,26(12): 3567-3578.]   
[27] 孙艳玲,郭鹏,延晓冬,等.内蒙古植被覆盖变化及其与气候、人 类活动的关系[J].自然资源学报，2010,25(3):407-414.[SUN Yanling,GUO Peng,YAN Xiaodong,etal.Dynamics of Vegetation Cover and Its Relationship with Climate Change and Human Activities in Inner Mongolia[J]. Journal of Natural Resources, 2010,25(3): 407-414.]

# Analysis of vegetation index changes and the influence of hydrothermal combination in the Turpan Basin from 2001 to 2017 based on MODIS Data

PANG Ran, WANG Wen (State KeyLaboratory of Hydrology-Water Resources and Hydraulic Engineering, Hohai University;Nanjing,Jiangsu,China,210098)

Abstract: Climatechange and its efects on vegetation in thearid areas of northwest China have been a major concern in the geosciences community.The case study area,the Turpan Basin, is an area of approximately $5 . 8 5 \times 1 0 4$ （204号 km2 in the eastern part of Xinjiang Province in northwest China.The Turpan Basin's topography consists of a low flatarea in thecenter with high mountains surrounding it,yielding alarge elevation diference in a small distance. Water vapor broughtby prevailing westerly winds is the main sourceof moisture in this area.The basin’s climate is verydry and hotand the hydrothermal combination is complicated.In this paper,ground-based meteorological observation data, GLDAS-2.1 reanalysis meteorological data,and satelite-based MODIS normalized difference vegetation index (NDVl) data are used to investigate the impacts of climate change,terrain,and human activities on spatiotemporal changes of vegetation in the Turpan Basin from 200l to 2O17.The analysis uses the methods of trend test,linearregression,and partialcorrelationanalysis.Theresultsof thisanalysis indicate thatthe following.(1) There was no significant change in precipitation in the Turpan Basin overall;however,the rate of increase in the northern mountains is large.Additionally,the temperature increased significantly overthe whole region,especially

# 干旱区地理

in the centralarea at the bottomof Turpan Basin,with aremarkable growth rate.(2)The NDVIof the whole region exhibited a very significant upward trend,andthe NDVI growth rates in the mountains and the central region were relativelylarge.(3)Affcted bytheavailabilityof water vaporandsunlight duration,the NDVI value is the highest in the mountains around the Turpan Basin at an elevation of approximately $3 , 0 0 0 \mathrm { m }$ . In the northern Tianshan Mountains,which extendfromeast to west,andthecombinationof waterand heatconditions isthe bestinthe northwestfacing slopes,which is beneficial to vegetation growth.Incontrast,the north-facing and south-facingslopes have either too litle or too much solar radiation.In the western Tianshan Mountains,which generally extend generally south to north,the northwest-facing slopes also have the best combination of water and heat,whereas the southeastfacing slopes have the smalest NDVI. (4) Becauseof the special terrain,the hydrothermal combination inthe Turpan Basin is complex.Although water is the major limiting factor for vegetation growth in most regions,as indicated by the positive correlation between precipitation and NDVI, the effects of temperature change on $N D V I$ are complicated. In the mountainsand desert areas,temperature is generally negatively related to NDVI,but inthecentral area at the bottom of the Turpan Basin,the relationship is positive because of the accumulation of groundwater from the surrounding mountains which provides a comparatively stable water supply.

Key Words: Hydrothermal Combination; Vegetation Change; Climate Change;NDVI; Terrain; MODIS

# 中国持续为咸海生态修复提供科研支撑

[新华社客户端]乌鲁木齐2020年11月23日电(记者于涛、董博婷)近10a间,我国科研人员积极与中亚国家研究机构开展合作，合力解决咸海生态修复难题。本月24～25日，北京、乌鲁木齐及乌兹别克斯坦塔什干三地将视频连线，各国百余位学者共同研讨咸海生态治理,加强区域合作，达成咸海生态新平衡。

主办方之一的中国科学院新疆生态与地理研究所所长张元明表示，多年来，我国与乌兹别克斯坦科研人员广泛合作，已在多类生态研究领域取得成果，咸海生态问题影响中亚水资源安全，也与中国息息相关，解决这一问题需国家间协调合作，专家研讨目的在于推动区域间实质性合作，会上计划发布“绿色咸海国际科学倡议”。

致力于土壤改良、植物营养与绿洲农业生态研究的新疆生态与地理研究所研究员田长彦介绍，新疆科研团队已在咸海有关区域进行了模拟实验，目前筛选出3～5组长势喜人的耐盐碱植物，为解决当地生态问题带来希望。

咸海位于乌兹别克斯坦与哈萨克斯坦之间，曾是世界第四大内陆湖。近50a来，咸海水域面积和水量大幅减少，目前咸海面积仅剩1960年的 $10 \%$ ,水量仅剩1960年的 $4 \%$ 。干涸的咸海区域每年产生1.5亿吨盐尘，严重影响中亚区域生态环境和民众身体健康。多年来，咸海“危机”受到全球生态环境领域科学家持续关注。