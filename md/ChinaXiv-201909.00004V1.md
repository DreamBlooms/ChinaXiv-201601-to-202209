# 全新世以来青藏高原文化遗址时空演变及其驱动

金孙梅'，侯光良²，许长军³，兰措卓玛'，李生梅'（1.青海师范大学地理科学学院，青海 西宁810008；2.青海师范大学青海省自然地理与环境过程重点实验室,青海 西宁810008;3．青海省地理空间信息技术与应用重点实验室，青海 西宁810000)

摘要：青藏高原是全球地理环境最为特殊的区域之一,研究全新世以来青藏高原文化遗址时空演变及其原因,对于理解极端环境下的人类响应与适应具有重要意义。基于 ArcGIS 空间分析,运用核密度估计、平均最邻近指数和全局空间自相关等地理统计方法,研究了全新世以来青藏高原14 339 处文化遗址的时空演变。结果表明：各时期遗址最近邻指数均小于1,全局 Moran'sI的取值介于0\~1之间,遗址存在正的空间自相关,且属于集聚分布的模式;遗址分布重心经历了由高原腹地(旧石器时期)一东南边缘谷地(新石器时期)一东部地域(青铜器时期以来)的转变;遗址分布形态特征则经历了均匀广布型（旧石器时期）、边缘河谷型(新石器时期）、河谷集聚型（青铜器时期）、退化分散型(吐蕃部落时期)半月广布型(吐蕃王朝时期)、斑块广布型(元代)、连片集聚型(明清时期)的变化过程;青藏高原各时期遗址时空分布演变是海拔、气候变化、植被等自然环境，以及生产方式、技术、战争、人口迁移、政治政策等社会经济因素共同作用的结果。

关键词：全新世；文化遗址；时空演变；青藏高原

人地关系是地理学研究主题之一，以揭示人类社会和自然环境之间相互制约、联系、作用关系的实质为其主旨，文化遗址是古代人类在生产活动中留存的重要文化载体。文化遗址的分布演变研究不仅能揭示区域性社会组织关系演替过程，而且与周围生态环境变迁密切相关[1]。国内外学者从这一角度开展了诸多研究[2-6]。LGM(末次冰盛期)两极发育大冰盖，海岸线急剧下降，白令海峡成为路桥，东北亚地区的狩猎者跨越白令海峡路桥，进入了北美,成为人类拓殖新大陆的最早开发者[7]。在非洲东撒哈拉地区史前人类随着降水的改变，而不断迁移自己的居民点。在 $9 . 5 \sim 5 . 3 \mathrm { \ k a }$ BP时气候比较潮湿，沙漠面积缩小，定居点的数量随降雨的突然增加而增加;在晚期随着干旱从北向南迁移，沙漠扩大，人类活动纷纷退出撒哈拉，直到5300a前基本消失[8]。显然,人类活动遗迹的时空分布与环境变化等密切相关，遗址的时空变化是揭示复杂人地关系的一把钥匙。

青藏高原是史前人类活动较频繁的区域之一，其地貌单元复杂，自然环境空间差异明显。近年来，青藏高原周边地区史前人类活动与环境互动关系研究也取得明显进展[9-11],目前对青藏高原旧石器时期至近现代时期的长时间尺度人地关系的研究较少。本文拟基于遥感和GIS技术，从遗址时空分布角度，对青藏高原旧石器时代至近现代时期的遗址时空演变、人类活动与自然环境的关系等进行探讨，旨在揭示高原极端环境，人类社会对特殊环境的响应与适应过程。

# 研究区概况

青藏高原平均海拔超过 $4 ~ 0 0 0 ~ \mathrm { { m } }$ ,面积达 $2 . 5 \times$ $1 0 ^ { 6 } \mathrm { ~ k m } ^ { 2 [ 1 2 ] }$ ,有世界第三极之称,其四周为高山环绕，高亢的海拔成为人类定居青藏高原的天然屏障（图1）。高原全境气候和环境差异显著，自北向南依次为温带极端干旱区、中部的高山亚寒带及南部的高山温带，自西向东为高原山地气候与东南部亚热带气候。高原冬季寒冷干燥，夏季凉爽，年平均温度为 $7 \sim 8 \mathrm { ~ \textdegree C }$ 。北部边缘极端干旱区平均年降水量为 $1 0 \sim 3 0 ~ \mathrm { m m }$ ,南部和东南部的高原降雨量较为丰

注：I果洛那曲高原山地区;Ⅱ青海高原南部区;Ⅲ青海高原与羌塘高原区;V藏北高原北部阿里山地高原区;V藏南高山谷地区;V藏南高山谷地东段区;VI横断山脉高山峡谷区;V祁连青东高山盆地区;IX柴达木盆地与昆仑山北翼区;X昆仑山西段山地高原区。

![](images/e30bdc550f9a366bce1868d4893c3a168394d12ac22ed697bba3f04d3f6b8f7d.jpg)  
图1青藏高原自然区划示意图  
Fig.1Schematic diagram of natural division of the Tibetan Plateau

富,年均降水量为 $3 7 0 \sim 1 ~ 8 0 0 ~ \mathrm { \ m m } ^ { \left[ 1 3 \right] }$ 。高原面上山地和盆地交错分布，永久性冻土广布。除周边山地局部存在森林植被外，青藏高原主体为高山草甸、草原和荒漠植被,生物量低(14]。总体来讲,青藏高原动植物资源贫乏，气候寒冷干燥，紫外线辐射强烈，氧气稀薄，对多数生物(尤其是人类)而言，是特殊而严酷的生存环境[，也是人类学、考古学和遗传学研究人类生理与行为适应的重要区域[15-16]。本文为方便叙述,将青藏高原划分为10 个自然区[17]（图1），这种划分方法能准确识别出地域特征的差异和相似性，突出青藏高原呈外围一腹地式的结构，与青藏高原高耸的地形特征相符合。

# 2 数据来源与研究方法

# 2.1 数据来源

本文所使用的数据为：青藏高原范围与界线数据[12];中国科学院计算机网络信息中心国际科学数据镜像网站（http://www.gscloud.cn）中的 $9 0 \mathrm { ~ m ~ } \times \mathrm { ~ }$ $9 0 \mathrm { ~ m ~ }$ 空间分辨率的DEM数据产品；遗址数据主要基于全国第二次文物普查结果，并结合相关省份文物地图集(18-23],包括青藏高原范围所覆盖的西藏、青海，以及四川、云南、甘肃、新疆部分地区遗址点，青藏高原境内多数遗址虽缺乏绝对年龄数据，但根据已发布的年代数据、考古特征遴选出旧石器时代至近现代时期遗址共计14339处。遗址点数据是目前能够搜集到的，且来自于公开资料的最完善的数据，能够代表各文化时期遗址点的分布情况，有较高的可靠性。

在数据处理过程中，首先确定遗址的具体位置，经纬度不详的遗址结合谷歌卫星地图加以判读；其次，参考中国文物普查认定标准进行分类、确定年代（剔除年代不详的点），少量跨年代遗址重复计算，最后按照考古学、历史学、年代学体系的特点，将研究区遗址按文化类型和历史学的综合划分法统计[6,24-25]。划分结果为旧石器时代 $( 1 5 \sim 6 \ \mathrm { k a } \ \mathrm { B P } ) \$ ）（为描述方便,将细石器遗址也归入旧石器），新石器时代 $( 6 \sim 4 \ \mathrm { k a } \ \mathrm { B P } )$ )[涵盖仰韶中晚期文化（6～5ka BP）、马家窑文化 $( 5 . 3 \sim 4 \ \mathrm { k a \ B P }$ ）、卡若文化( $\left( 5 \sim \right)$ $4 \ \mathrm { k a }$ BP)和曲贡文化（ $( 4 \sim 3 . 5 \ \mathrm { k a } \ \mathrm { B P } )$ ],青铜器时代（ $4 \sim 2 \mathrm { \ k a \ B P }$ )[涵盖齐家文化 $( 4 . 2 \sim 3 . 6 \ \mathrm { k a \ B P } )$ ）、卡约文化 $( 3 . 6 \sim 2 . 7 \ \mathrm { k a \ B P } )$ ）、辛店文化 $( 3 . 6 \sim 2 . 6 \ \mathrm { k a }$ BP）、诺木洪文化 $( 3 \sim 2 . 2 \ \mathrm { k a } \ \mathrm { B P }$ )及夏—汉代]，吐蕃部落晚期 $( 2 ~ 0 0 0 \sim 1 ~ 3 1 7 ~ \$ a BP)（涵盖三国一南北朝），吐蕃王朝时期( $( 1 ~ 3 1 7 \sim 1 ~ 1 0 8 \mathrm { ~ a ~ B I ~ }$ )（涵盖隋一金代），元代（ $6 7 9 \sim 5 8 2$ aBP），明代（ $5 8 2 \sim 3 0 6$ aBP），清代（ $3 0 6 \sim 3 9$ aBP），近现代时期( $3 8 \sim 0$ a BP)（涵盖中华民国);需要提及本文年代均为日历年。

# 2.2 研究方法

GIS和RS等在聚落和区域考古研究的应用也渐趋成熟[26-28],并取得了较为突出的成效。有学者利用GIS方法中泰森多边形，分析了青藏高原东北缘河谷地带史前聚落空间分布模式[27],利用GIS 方法中最短路径模拟出青藏高原史前交通路线(28] 0本文首先对青藏高原 $9 0 ~ \mathrm { m }$ 分辨率DEM数据及各时期遗址点，在ArcGIS10.2下进行处理和矢量化，然后在青藏高原不同海拔分层地形图上设色，根据遗址分布情况分别制作各时期文化遗址分布图。

# （1）核密度估计

核密度估计(KDE)是一种非参数的表面密度计算方法，根据输入的要素数据集计算整个区域的数据聚集状况，从而产生一个连续的密度表面。能直观地表现研究对象的分布概率，核密度值的大小代表遗址点在空间分布上的集聚程度，核密度估计值越大,遗址点的分布密度越密[29]。本文结合核密度估计方法，对青藏高原文化遗址空间分布的集聚性进行可视化。其计算公式如下：

$$
f ( x , y ) = \frac { 1 } { n h ^ { 2 } } \sum _ { i = 1 } ^ { n } k \left( \frac { d _ { i } } { n } \right)
$$

式中 $\scriptstyle : f ( x , y )$ 为位于 $\displaystyle { \big ( } x , y { \big ) }$ 位置的密度估计值; $n$ 为观测数量； $h$ 为宽带，其取值影响点对象核密度空间分布的平滑程度； $k$ 为核函数; $d _ { i }$ 为位置距第 $i$ 个观测位置的距离。制作核密度图时，搜索半径 $h$ 的选择对于最终生成结果影响很大， $h$ 过小可能光滑效果不佳，而 $h$ 过大虽光滑效果较好，但却会影响密度结果的真实性。计算步骤：在ArcGIS软件的Arc-Toolbox,利用 Spatial Analyst工具中的Density Analy-sis进行KernelDensityAnalysis计算,本研究在参考前人成果的基础上，经过多次试验，确定 $1 4 ~ \mathrm { k m }$ 的搜索半径来进行遗址点空间分布的核密度估计，以期生成效果较好的遗址点核密度分布图，结果如图2所示。

# （2）平均最邻近指数

平均最邻近指数是通过测量每个要素的质心与其最近要素质心位置之间的距离，计算所有最邻近距离的平均值，并将其与假设随机分布中的平均距离进行比较，从而判断研究要素是否为聚集分布[29],并通过计算标准化 $Z$ 值,比较观测平均距离与期望平均距离的差异，并与标准误差来确定二者间聚集或分散的程度。计算公式如下：

$$
A N N = \frac { \overline { { D } } _ { \mathrm { { o } } } } { \overline { { D } } _ { \mathrm { { e } } } } = \frac { \sum _ { i = 1 } ^ { n } d _ { i } / n } { \sqrt { n / A / 2 } }
$$

$$
S E _ { \mathrm { { r } } } = { \frac { 0 . 2 0 1 \ 3 6 } { \sqrt { n ^ { 2 } / A } } }
$$

$$
Z = \frac { \overline { { D } } _ { \mathrm { { o } } } - \overline { { D } } _ { \mathrm { { e } } } } { S E _ { \mathrm { { r } } } }
$$

式中： $\overline { { D } } _ { \mathrm { o } }$ 是每个遗址点斑块质心与其最邻近斑块中心的观测平均距离； $\overline { { D } } _ { \mathrm { { e } } }$ 是假设随机模式下斑块质心的期望平均距离； $n$ 为斑块总数； $d$ 为距离； $A$ 为研究区面积； $S E _ { \mathrm { r } }$ 为最邻近点平均距离的标准误差。ANN是平均最邻近指数，如果 $A N N < 1$ 则观测模式比随机模式聚集；反之，则表明观测模式比随机模式分散。当显著性水平为 $\alpha$ 时， $Z$ 的置信区间为$- Z _ { \alpha } \leqslant Z \leqslant Z _ { \alpha }$ 。如果 ${ Z < - Z _ { \alpha } }$ 或 $Z > Z _ { \alpha }$ ，就可以认为在显著性水平 $\alpha$ 下，所计算出的观测模式与随机模式之间的差值具有统计显著性；反之，如果$- Z _ { \alpha } \leqslant Z \leqslant Z _ { \alpha }$ ,则认为尽管观测模式看上去更加聚集或更加分散，但显著性不高。计算步骤：ArcTool-box中利用Spatial Statistics Tool中的 Analysis Mod-ule 计算 Average Nearest Neighbor。

# （3）全局空间自相关

全局空间自相关是对属性在整个区域空间分布特征的描述，用于判断研究区域某一要素或现象在空间是否具有聚集特性存在[30]。本文采用全局Moran's $I$ 指数来测度青藏高原遗址点的全局空间自相关程度。其计算公式如下：

$$
I = \frac { n \underset { i = 1 } { \overset { n } { \sum } } \underset { j = 1 } { \overset { n } { \sum } } W _ { i j } { \overset { n } { \ } } { \left( x _ { i } - \overline { { x } } \right) } \left( x _ { j } - \overline { { x } } \right) } { \underset { i = 1 } { \overset { n } { \sum } } \underset { j = 1 } { \overset { n } { \sum } } W _ { i j } { \overset { n } { \sum } } { \left( x _ { i } - \overline { { x } } \right) } ^ { 2 } }
$$

式中： $n$ 为空间单元的总数； $x _ { i } \ : , x _ { j }$ 为分别表示遗址点在空间地域单元 $i$ 和 $j$ 上的观测值； $\overline { { x } }$ 为遗址点的均值； $\boldsymbol { W } _ { i j }$ 为空间权重矩阵。本文采用rook一阶权值矩阵,即空间单元 $\mathbf { \chi } _ { i }$ 与 $j$ 相邻时, ${ \boldsymbol { W } _ { i j } } = 1$ ;反之， ${ \boldsymbol { W } _ { i j } } = 0$ 。标准化 $Z$ 值常用于检验全局Moran's $I$ 指数的显著性水平，其计算公式如下：

$$
E ( I ) = \frac { - 1 } { n - 1 }
$$

$$
\operatorname { V a r } ( I ) = { \frac { n ^ { 2 } S _ { 1 } - n S _ { 2 } + 2 S _ { 0 } } { S _ { 0 } \left( n ^ { 2 } - 1 \right) } } - E ^ { 2 } ( I )
$$

$$
S _ { 1 } = \frac { 1 } { 2 } \sum _ { i } \sum _ { j } (  { W } _ { i j } ) ^ { 2 } , S _ { 2 } = \sum _ { i } (  { \mathrm { ~ \sum ~ } } { W } _ { i j } +  { \sum _ { j } }  { W _ { j i } } ) ^ { 2 }
$$

$$
Z _ { \mathrm { s c o r e } } = { \frac { I - E ( I ) } { \sqrt { \operatorname { V a r } ( I ) } } }
$$

式中： $E ( I ) \setminus \operatorname { V a r } ( I )$ 分别表示Moran's $I$ 的期望值和方差。以 $| Z | > 1 . 9 6$ 表示该区域的空间自相关是显著的。全局Moran's $I$ 的取值介于[-1,1]之间，在给定的显著性水平下,若Moran's $I > 0$ ,表明存在正的空间自相关，即在空间上显著集聚，值越接近于1,空间分布的差异性越小;若Moran's $I < 0$ ,则相反；当Moran's $I$ 接近或等于0时，表明各遗址点分布倾向于不具有特定相似性的随机模式，即不存在空间自相关。计算步骤：ArcToolbox中利用SpatialStatistics Tool 中的 Analysis Module 计算Global Spa-tial Autocorrelation。

# 3遗址时空演变特征

从遗址密度可以看出，青藏高原文化遗址总体呈现西疏东密的特征（图2），分布重心经历了由高原腹地(旧石器时期)一东南边缘谷地(新石器一青铜器时代)一东部地域(吐蕃部落时期以来）的转变。各时期平均最邻近指数均小于1，除旧石器时代与元代外，全局Moran's $I$ 的 $P$ 值均小于0.05，Z得分大于1.96，即遗址点整体上存在正的全局空间自相关，且分布态势具有集聚型（表1，表2）。根据各时期遗址数量与分布特征，现将青藏高原全新世以来遗址发展分以下几个阶段概述。

# 3.1 萌芽阶段(旧石器时期)

目前，青藏高原发现的旧石器遗址仅160处，平均海拔( $\left( 4 \ 0 9 7 . 8 \ \mathrm { ~ m ~ } \right)$ )处于全新世以来最高（图3）。平均观测距离远，平均最邻近指数与全局Moran'sI指数（0.149， $\ : P < 0 . 0 5 \ : , \ :$ )均为9个时段最低值（表2），说明在0.05显著性水平下，旧石器遗址空间分布聚集虽有显现，但仍趋于均匀分布态势。该时期人类以采集狩猎为主，频繁迁移，活动地域广泛，但区域的封闭性强，道路系统尚未形成。因此，文化遗址数量少，且文化遗址之间的自相关性较弱。从图

2中看出，遗址分散且未出现明显核心（图2,表1），广布于X区、Ⅲ区等高海拔区域，VI区与Ⅲ区较为集中，X区的河谷地带存在少量遗址点，高原东南部其他各区有少量遗址点零星分布。该时期遗址海拔最高，分布较均匀，地域广泛，几乎遍布全境，具有明显的均匀广布型特征。

# 3.2边缘积聚阶段(新石器时期一青铜器时期)

全新世中期末段，新石器文化在青藏高原东部陆续出现，遗址数量骤然增加，空间分布范围明显扩展，受黄土高原发达的仰韶文化影响，马家窑文化兴起，集中分布于高原东北部河湟谷地（图2）。其中$6 7 . 0 7 \%$ 的遗址主要集中在海拔 $2 ~ 5 0 0 \mathrm { ~ m ~ }$ 以下的河谷地带（图3），青铜器时代遗址数量骤增，核密度达最高值，海拔明显降低，平均观测距离及平均最邻近指数均处于全新世以来最低值(表1），表明遗址空间分布正相关且高度集中。该阶段X区未出现遗址，其中Ⅱ区、Ⅲ区及VI区人类活动显著增强，VI区遗址点沿河谷呈带状分布，柴达木盆地、青海湖盆地、祁连山地区的遗址集中度得到进一步强化，并且在河湟谷地形成显著的聚集核心。扩张阶段遗址分布向东部及东南部转移，平均海拔降低，高原腹地遗址明显减少，呈现显著的河谷集聚型特征。

# 3.3平稳阶段(吐蕃部落晚期一元代)

该阶段遗址数量呈波动变化，海拔显著上升，最邻近指数稳定，平均观测距离较史前阶段明显扩大。吐蕃部落晚期核密度较低，且未形成明显的集聚核，遗址规模的全局Moran'sI指数达到各时段最大值，表明遗址分布差异性减小，且聚集特征有所退化。吐蕃王朝时期遗址数量有所回升，全局Moran's $I$ 处于较高水平，元代高原上遗址数量降幅达 $7 2 . 4 6 \%$ （相比吐蕃王朝时期），其分散程度仅次于旧石器时期，表明当时的人类活动范围广布高原，流动性强，空间自相关程度高。遗址分布范围收缩，并在V区及V区成条带状分布，吐蕃王朝时期人类活动范围出现Ⅱ区向I区、IX区扩展的态势，在高原东南部形成半月型分布，至元代羌塘高原、藏北高原无人类活动遗迹，遗址在高原东南部呈现斑块状分布。

# 3.4 鼎盛阶段(明代一近现代)

该阶段遗址数量有所增加。明代，遗址海拔明显下降,其中 $5 9 . 5 4 \%$ 的遗址点位于海拔 $3 \ 0 0 0 \ \mathrm { m }$ 以下的河谷盆地，遗址全局Moran's $I$ 指数为0.439，呈空间正相关，且平均观测距离较前期缩短。清代，遗址数量显著增加的同时，遗址点之间的平均观测距

70E 80E 90°E 100°E 70°E 80°E 90°E 100°E(a) 一 喜 (b) 4N8 A  
3 图例省会城市 省会城市主要河流 西宁市。 主要河流  
N.08 然划范围 46m N08 划范围 46m石器时期 新石器时期遗址密度/（个·km 遗址密度/（个·km2）0.00370\~0.00464 0.12093\~0.148240.00289\~0.00369 0.09709\~0.12092  
N 1 2Z 0.0738-09708 0.0249-05465 0.01280\~0.024420.00524\~0.012790105210420630840km 0\~0.00116 0.00117\~0.005 23 480 720 960km  
70°E 80°E 90°E 100°E 70°E 80°E 90°E 100°E(c) 子 (d) N  
N8 ? N8 七  
No00 青铜器时期 区划范围 No08 然范围 部时期 宁市遗址密度/（个·km 遗址密度（个·km0.23532\~0.31091 0.01298\~0.016210.181 68\~0.23531 0.01005\~0.012970.14632\~0.18167 0.00745\~0.01004  
N 0.11706-0.146031 2 0.00516-0.0074H70°E 80°E 90°E 100°E 70°E 80°E 90°E 100°ET(e) N (f) N  
N T 十 N8 4图例市  
N.08 新 N08 区划范围 ?46m蕃王朝时期 元代遗址个 址个-000.00494\~0.006 38 0.00413\~0.00551  
NZ 0.003801-0.004908 2Z D 0.001 87\~0.0041210.002 27000 一 0.00143-0.0010510.00106\~0.00162 0.000 68\~0.0010010.00058\~0.00105 0.00037\~0.000 6710080.050450 580 870km 0.-00200 0145290 580 870km70°E 80°E 90°E 100E 70°E 80°E 90°E 100ET  
N 岛 L 美 (g) 十 N N8 舟 J (h) 一 N图例省城市主要河流区划范围 □然区划范围  
N.00 8752m 46m H N08 8752m 美密度/个·km 密度/（个·km10.02133\~0.02877 0.06501\~0.085430.01682\~0.02132 0.04960\~0.065000.01287\~0.01681 0.03787\~0.04959  
NZ 0.0071.0.0168 0.00475\~0.00711 2Z 0.027 82-03786 0.012 74\~0.019 430.002 72\~0.00474 1 0.00738\~0.012730.00125\~0.00271 0.00336\~0.0073710\~0.00034 0.00035\~0.00124 T 145290 580 870km 10\~0.00067 0.000 68\~0.00335 0162.5325 650 975km

Fig.2Spatiotemporal distribution densityof the ancient culturalrelicsonthe Tibetan Plateau since the Holocene离由明代的 $8 ~ 8 5 0 \mathrm { ~ m ~ }$ 降至 $6 7 4 4 \mathrm { ~ m ~ }$ ,平均最邻近指数变化甚微。从分布范围来看，自明代起遗址在河湟谷地、四川北部横断山谷地、雅鲁藏布江谷地形成明显的“核心区”，I区、Ⅲ区、V区、X区鲜有人类定居。清代，遗址扩张至IX区，海拔较前期有所降低，呈现东南部连片集聚型特征。近现代人类活动广泛延伸高原北部，由于时间跨度较短，遗址数量较前期有所减少，故对该时期遗址时空分布不做详尽分析。

Tab.1Maximum kernel density and average nearest neighbor index of spatiotemporal distribution of the ancient cultural relics on the Tibetan Plateau since the Holocene   
表2全新世以来青藏高原文化遗址时空分布自相关指数  

<html><body><table><tr><td></td><td>遗址数量/个</td><td>最大核密度/（个·km-²）</td><td>平均观测距离/m</td><td>预期平均距离/m</td><td>最邻近比率</td><td>z得分</td><td>P值</td></tr><tr><td>旧石器时期</td><td>160</td><td>0.004 64</td><td>29 106.001</td><td>68 025.775</td><td>0.428</td><td>- 13.845</td><td>0</td></tr><tr><td>新石器时期</td><td>1 469</td><td>0.148 24</td><td>4 087.342</td><td>20 499.977</td><td>0.199</td><td>- 58.704</td><td>0</td></tr><tr><td>青铜器时期</td><td>8 614</td><td>0.310 91</td><td>812.337</td><td>9 345.809</td><td>0.087</td><td>- 162.122</td><td>0</td></tr><tr><td>吐蕃部落时期</td><td>261</td><td>0.016 21</td><td>14 369.418</td><td>45 536.108</td><td>0.316</td><td>- 21.154</td><td>0</td></tr><tr><td>吐蕃王朝时期</td><td>512</td><td>0.008 61</td><td>10 720.252</td><td>32 003.036</td><td>0.335</td><td>-28.787</td><td>0</td></tr><tr><td>元代</td><td>141</td><td>0.007 09</td><td>26 464.503</td><td>53 050.387</td><td>0.499</td><td>- 11.384</td><td>0</td></tr><tr><td>明代</td><td>969</td><td>0.028 77</td><td>8 850.498</td><td>27 475.541</td><td>0.322</td><td>- 40.369</td><td>0</td></tr><tr><td>清代</td><td>1 642</td><td>0.085 43</td><td>6 744.732</td><td>20 144.657</td><td>0.335</td><td>-51.566</td><td>0</td></tr><tr><td>近现代时期</td><td>571</td><td>0.021 19</td><td>9 188.004</td><td>32 941. 169</td><td>0.279</td><td>-32.963</td><td>0</td></tr></table></body></html>

表1全新世以来青藏高原文化遗址时空分布最大核密度及平均最邻近指数  
Tab.2Global spatial autocorrelation index of spatiotemporal distributionof theancientcultural relics on the Tibetan Plateau since the Holocene   

<html><body><table><tr><td></td><td>平均海拔/m</td><td>Moran'I指数</td><td>预期指数</td><td>方差</td><td>z得分</td><td>P值</td></tr><tr><td>旧石器时期</td><td>4 097.800</td><td>0.149</td><td>-0.006</td><td>0.048</td><td>0.711</td><td>0.477</td></tr><tr><td>新石器时期</td><td>2 741.409</td><td>0.594</td><td>-0.001</td><td>0.010</td><td>5.965</td><td>0.000</td></tr><tr><td>青铜器时期</td><td>2 567.926</td><td>0.532</td><td>0.000</td><td>0.000</td><td>49.310</td><td>0.000</td></tr><tr><td>吐蕃部落时期</td><td>3 737.567</td><td>0.849</td><td>-0.004</td><td>0.019</td><td>6.1389</td><td>0.000</td></tr><tr><td>吐蕃王朝时期</td><td>3 569.908</td><td>0.715</td><td>-0.002</td><td>0.020</td><td>5.038</td><td>0.000</td></tr><tr><td>元代</td><td>3 676.035</td><td>0.485</td><td>-0.007</td><td>0.906</td><td>0.517</td><td>0.210</td></tr><tr><td>明代</td><td>3 060.630</td><td>0.439</td><td>-0.001</td><td>0.039</td><td>2.225</td><td>0.026</td></tr><tr><td>清代</td><td>2 958.229</td><td>0.238</td><td>-0.001</td><td>0.010</td><td>2.368</td><td>0.018</td></tr><tr><td>近现代时期</td><td>2 966.718</td><td>0.612</td><td>-0.002</td><td>0.031</td><td>3.483</td><td>0.000</td></tr></table></body></html>

![](images/fd9881292ade2e73e62c886ca6f8a16174b4bc7547541a9e32565659833dd048.jpg)  
图3全新世以来青藏高原文化遗址高程变化 Fig.3Change of the elevation of the ancient cultural relics on the Tibetan Plateau since the Holocene

# 4遗址时空演变的影响因素

目前，在青藏高原发现的大部分旧石器遗址处于全新世早中期 $1 1 . 5 \sim 6 \mathrm { \ k a \ B P ^ { [ 3 1 ] } }$ ,这一时期遗址分布均匀，范围广泛，多处于高海拔地域。早期人类占据高原的进程与环境密切相关（图4）[32-38],青海湖夏季风指数[37]、错鄂湖 TOC[33]、和 Tso Moriri 湖降水量记录[34]均显示,全新世早中期高原环境迅速改善，降水量较现代高出 $2 0 0 \ \mathrm { m m } ,$ 气温较现代高$3 \sim 5 ~ \mathrm { { ‰ } }$ ,青海湖较高含量的乔木花粉[3表明气候适宜,高原面上发育草原草甸，植物生物量较高，全新世大暖期优越的环境条件，极大地驱动了人类对高原的扩张;除此之外，细石器工具制作水平的进步,便携、高效，使狩猎采集者能力提高[39]；其长

![](images/879034b00c45c080c0af6a89f8cf0595a30ea2c17d5d89bd455ee3fb40c4dc8c.jpg)  
图4全新世以来青藏高原及其周边环境记录对比

注：（a)青藏高原200a温度(距1851—1950年平均)集成序列[32]);(b)错鄂湖TOC 含量[33);(c)青藏高原Tso Moriri湖泊百年平均降水量变化曲线[34);(d)董哥洞记录的季风强度曲线[35];(e)青海湖乔木孢粉百分比曲线(36]；(f)青海湖夏季风指数[37]； $\mathbf { \tau } ( \mathbf { g } )$ 定量重建的青海湖年平均降水变化曲线[38]。

Fig.4Comparedresultsof theenvironmentalrecordsbetweentheTibetanPlateauandtheperipheralregionssincethe Holocen

距离、大范围、频繁迁移的行为模式决定了旧石器时期遗址广泛，且均匀的分布在高海拔地域。环境改善、细石器技术及狩猎行为模式成为旧石器人类活动广布高原的主要因素，需要提及的是高原细石器技术与中国北方关系密切[14)

青藏高原新石器文化被认为是仰韶文化向西扩张的余脉(40]。该时期文化主体为仰韶与马家窑文化，其出现是受关中仰韶文化的辐射和影响，马家窑文化继承庙底沟类型风格，并逐渐发展出其自身地域特色的文化类型[41],集中分布于青藏高原东北部的河湟谷地，并向青藏高原东南部扩散。除中原文化的西扩和推动之外，适宜的气候与农业也推动了该时期文化的快速发展。全新世暖期 $( 8 \sim 6 ~ \mathrm { k a B P } )$ 号高原年平均气温较现代高 $3 \mathrm { ~ \textdegree C ^ { \left( 4 2 \right) } }$ ,降水量较现代高$2 0 0 ~ \mathrm { { m m } }$ 左右[43],在 $6 \sim 4 ~ \mathrm { { k a } }$ BP 粟黍农业由关中盆地一黄土高原向西扩散到青藏高原东北边缘河谷地带，新的生产方式推动了农业人群向水热条件相对良好的河湟谷地及雅鲁藏布江谷地集聚[14]。青藏高原新石器遗址中发现了大量的房址、炭化粟黍种子和家畜骨骼等[9],表明过去以狩猎采集经济开始向农业经济转变。受中原文化、气候条件与种植业发展的共同作用，人类活动明显形成了集聚于高原东北缘及东南部的低海拔水热条件良好的边缘河谷型模式。

$4 ~ \mathrm { { k a } }$ BP 源自黄土高原的齐家文化扩张至本区，标志着青藏高原进入青铜器时代，富有黄土高原龙山文化特质的大双耳陶、玉器的追求和崇拜，以及二里头文化中卜骨等文化现象，均普遍出现在齐家文化，表明其与中华早期文明的渊源关系。此外，4ka BP亚洲季风减弱[35.37],青藏高原气候趋于干冷，青海湖降水量及乔木花粉百分比出现明显降低[36.38]。恶化的气候环境和资源压力的增大,使高原人类需要探索新的生存与适应策略。同期，来自西方的羊、青铜器麦类作物等通过西亚廊道传入新疆与青藏高原东北部，因此，齐家是中国最早使用青铜器的史前文化之一，并将青铜技术向中原传播，推动了中原进入青铜器时代，铸就了辉煌灿烂的殷商青铜文明。因此，齐家文化对于推动东西方文化交流、中原青铜文明的兴盛意义重大(44]。另外,齐家文化继承了东亚定居农业文化传统，也吸收了中亚青铜游牧文化，进而形成了高海拔地区以畜牧为主、较低的河谷地带农牧兼营的产业格局。青铜器晚期驯养动物的引入以及麦类作物成为青藏高原海拔$2 ~ 5 0 0 ~ \mathrm { m }$ 以上地区的主要作物[45],演化发展为多个特点鲜明的地方性文化，包括辛店、寺洼、卡约和诺木洪等文化[41]。青铜器时代部分农牧混合经济人群活动范围进一步向高原扩张，并在高原东南部形成了河谷集聚型分布的模式，为青藏高原人口空间分布格局奠定了基础。

吐蕃部落时期，遗址范围缩小并向高原南部汇聚。青藏高原错鄂湖、Tso Moriri 湖环境指标(3-34)与都兰和天峻树轮年表[32记录了吐蕃部落时期为过去2000a来持续时间最长的冷期，藏北高原气候更为干旱,植被带南移，放牧业随之南移。此时期，高原部落之间频繁的兼并战争使人类活动范围进一步收缩，以雅袭河谷为中心的藏南地区是整个高原范围内除河湟谷地外，地理环境和自然条件最优越的地区之一。公元6世纪前后立足雅袭河谷农业的吐蕃部落迅速强盛和崛起，征服藏北象雄和苏毗并统一青藏高原[32]。在恶化的气候与频繁战争的共同作用下，遗址分布呈现集聚退化分散态势。

吐蕃王朝时期，遗址出现由低向高海拔，由边缘向高原主体与腹地迁移、扩散的过程，这与高原气候环境改善密切相关,重建结果[34,46-48]揭示了中世纪暖期年平均气温较今高 $0 . 5 ~ \mathrm { ^ { \circ } C }$ ，且持续时间较长，农牧交错带北界大幅度北移至 $3 9 ^ { \circ } \mathrm { N }$ 附近[47],这一时期高海拔地区畜牧业得到快速发展，人类活动范围有所扩张。同期，吐蕃王朝在青藏高原的势力范围日益扩大，据《青海通志》记载，唐时期“，廓（今青海化隆、贵德县)二州编户人口5万余人，城内常驻边防军数万人（开元后额设兵7.5万人）”。此时中央为加强统治，对今大通河流域、青海化隆一带、大夏河、洮河、白龙江地区采取了军队驻屯和移民。中世纪暖期适宜的气候条件刺激了畜牧业的进一步发展，同时军队驻屯和移民使高原人类活动得到进一步增强。暖湿的气候及强力的政治组织促使遗址分布面积进一步扩大，呈东南部半月广布型的特征。

元代中后期，遗址仍集中在高原东部及南部低海拔河谷地区，中西部高海拔地区无人类活动遗迹。此时，青藏高原气候由早期的温暖期转为干冷期，青海湖区降水减少,植被逐渐转变为疏林草原[47],干冷的气候条件使原本脆弱的环境进一步恶化，可利用的动植物资源减少，生计模式受到冲击。除此之外，元代初期实行人口外迁政策，《元史·地理志》记载蒙古军初入西宁州(辖西宁州、乐州、廓州)，曾将该州大批居民迁到了云京，人口外迁政策的实施导致高原人口较前期有所减少。气候恶化与人口政策共同作用下，人类在高原上的活动范围再度缩小，分散程度明显增大，呈现斑块型广布特征，局部集中在水热条件良好的河谷地带。

小冰期(1400一1850 年)遗址广泛连片分布在高原东南部,海拔降至历史时期最低。这一时期为过去2000 a中最寒冷的时期[32.46-48],青藏高原年平均气温较今低 $1 \ \mathrm { { ^ { \circ } C } }$ 左右，降水量由明初的湿润逐渐转干，这也得到了同期其他代用资料（错鄂湖TOC 含量(38]、定量重建的达连海和青海湖降水记录(42]等)的佐证。受寒冷气候影响,大部分遗址处于海拔 $3 \ 0 0 0 \ \mathrm { m }$ 以下的盆地河谷，为应对气候恶化，当时人们引种、推广玉米等外来耐旱、高产品种的农作物，集中在低海拔水热条件良好的地区耕作。同时，明王朝为加强统治，在前朝聚落的基础上大规模扩张建置，实行屯垦成边，致使明清小冰期人口较前不降反升。这一时期耐旱、高产的农作物引进，为人类对抗因气候而恶化的生存条件提供了保障，一些低海拔水热条件充足的地区成为人类集聚的理想场所，在生产结构及成边政策共同作用下，人类活动形成东南河谷地区连片集聚的现象，随着社会经济的发展与气候环境的改善，高原人口活动范围在近现代开始大规模向高原腹地扩张。

# 5结论

青藏高原遗址形态分析结果表明，全新世以来遗址最邻近指数均小于1，属于集聚分布模式，全局Moran's $I$ 的取值介于0～1之间，遗址存在正的空间自相关。分布特征为：旧石器时期，人类占据腹地广大区域，均匀分布，足迹遍布高原。新石器一青铜时期，遗址数量迅速增加，海拔逐渐降低，且高原东北部河谷地带形成稳定的集聚型分布模式，奠定了青藏高原现代人口分布格局。历史时期遗址的数量和集聚一分散模式呈现显著的波动演变趋势，人类活动重心由高原中、西部高海拔地区向东、南部河流谷地移动，小冰期时遗址数量达到又一高峰，为适宜寒冷的气候环境，并先后在河湟谷地、四川北部横断山谷地、雅鲁藏布江谷地集聚，形成明显的“核心区”，海拔达到全新世最低期。遗址形态特征主要经历了均匀广布型、河谷集聚型、半月广布型、斑块广布型、连片集聚型的发展变化。

遗址的时空演化受控于不同时段独特的自然因素(气候变化、资源分布、地形特征)与人文因素（生计模式、战争、人口增减、政治、屯垦成边等)的耦合关系。遗址空间分布形态主要受控于自然环境因素，而在演变过程中，史前阶段气候变化和生计模式的影响较大，历史时期人文因素起主导作用。文化遗址高涨时期(旧石器一青铜器时期、吐蕃王朝、隋唐、清)均与暖湿及凉湿的气候特征、生计模式转变、屯垦成边的高潮、生产技术的提高等方面相对应，而文化遗址的低谷时期（如吐蕃部落晚期、元、明)则与暖干及冷干的气候特征、地方性战争、人口政策、屯垦戍边的缓慢发展等相吻合，反映出人地关系组合良好的时期，文化遗址兴盛，反之，则衰落。

# 参考文献（References）：

[1]李开封,朱诚,王鑫浩,等.旧石器时代至商周时期贵州遗址空 间分布及其自然环境背景[J].地理学报,2013,68（1)：58- 68.[LiKaifeng,Zhu Cheng,Wang Xinhao,et al.The archaeological sites distribution and its relationship with physical environment fromaround $2 6 0 ~ \mathrm { { k a } }$ BPto 221 BC in Guizhou Province[J].Acta Geographica Sinica,2013,68(1):58-68.]   
[2]安成邦,王琳，吉笃学，等.甘青文化区新石器文化的时空变化 和可能的环境动力[J].第四纪研究，2006，26（6）：923-927. [An Chengbang,Wang Lin,Ji Duxue,et al. Temporal and spatial changes of Neolithic culture in Gansu -Qinghai region possible environmental forcing[J].Quaternary Research,2006,26(6）:923- 927.]   
[3]侯光良,许长军,曹广超,等.青藏高原末次冰消期一全新世中 期人类扩张的时空模拟[J].第四纪研究，2017，37（4）：709- 720.[Hou Guangliang,Xu Changjun,Cao Guangchao,et al.The spatial-temporal simulation of mankind's expansion on the Tibetan Plateau during Last Deglaciation-Middle Holocene[J].Quaternary Research,2017,37(4) :709-720.)   
[4］崔一付,刘雨嘉,马敏敏.青藏高原东北部官亭盆地新石器— 青铜时代聚落时空演变及其影响因素[J].中国科学：地球科 学,2018,48(2):152-164.[Cui Yifu,Liu Yujia,Ma Minmin. Spatiotemporal evolution of prehistoric Neolithic-Bronze Age settlements and influencing factors in the Guanting Basin,Northeast Tibetan Plateau[J].Science China Earth Sciences,2018,48（2）： 152 -164. ]   
[5]Dong Guanghui,Jia Xin,An Chengbang.Mid-Holocene climate change and its effect on prehistoric cultural evolution in Eastern Qinghai Province,China[J]. Quaternary Research,2012,77:23-30.   
[6]Chen Fahu,Wu Duo,Chen Jianhui,et al.Holocene moisture and East Asian summer monsoon evolution in the Northeastern Tibetan Plateau recorded by Lake Qinghai and itsenvirons:A review of conflicting proxies[J]. Quaternary Science Reviews,2016,5 (24):111 -129.   
[7］谢传礼,赵泉鸿.末次盛冰期中国海古地理轮廓及其气候效应 [J].第四纪研究,1996,16（1）:1-10.[Xie Chuanli,Zhao Quanhong.The paleogeographic configuration of China seas and its climatic influence during the last glacial maximum[J].Quaternary Research,1996,16(1):1-10.]   
[8]Rudolph K,Stefan K. Climate-controlled holocene occupation in the Sahara:Motor of Africa’s evolution[J].Science,2Oo6,313： 1 243 -1 247.   
[9]Chen Fahu,Dong Guanghui,Zhang Dongju,et al.Agriculture facilitated permanent human occupation of the Tibetan Plateau after 3 600 B.P.[J].Science,2015,347:248 -250.   
[10]马敏敏,董广辉,贾鑫,等.青海省化隆县新石器—青铜时代聚 落形态及其影响因素分析[J].第四纪研究,2012,32（3）：209 -218.[Ma Minmin,Dong Guanghui,Jia Xin,et al.Analysis of settlement patterns during Neolithic and Bronze period and its influencing factors in Hualong County,Qinghai Province,China[J]. Quaternary Research,2012,32(3）:209-218.]   
[11］黄春长,郭永强,张玉柱,等.青海官亭盆地喇家遗址全新世地 层序列与史前灾难研究[J].中国科学;地球科学,2018,49 （2）:434- 455.［Huang Chunchang，Guo Yongqiang,Zhang Yuzhu,et al.Holocene sedimentary stratigraphy and pre-historical catastrophes over the Lajia Ruins within the Guanting Basin in Qinghai Province of China[J].Scientia Sinica Terrae,2018,49 (2) :434 -455. ]   
[12］全球变化科学研究数据出版系统（http://www.geodoi.ac.cn/ doi. aspx？ doi $= 1 0$ 0.3974／geodb.2014.01.12.v1）[Global Change Science Research Data Publishing System(http://www geodoi.ac.cn/doi.aspx? doi $= 1 0$ .3974／geodb.2014.01.12. v1)]   
[13]Lu Houyuan,Wu Naiqin,Liu Kam-biu,etal.Modern pollen distributions in Qinghai -Tibetan Plateau and the development of transfer functions for reconstructing Holocene environmental changes [J].Quaternary Science Reviews,2011,30(12）:947-966.   
[14]张东菊,董广辉,王辉,等.史前人类向青藏高原扩散的历史过 程和可能驱动机制[J].中国科学：地球科学,2016,46（8）： 1 007 -1 023.[Zhang Dongju,Dong Guanghui,Wang Hui,et al. Historical process and possible driving mechanism of prehistoric human beings spreading to the Qinghai- Tibet Plateau[J]. Scientia Sinica Terrae,2016,46(8）:1 007 -1023.]   
[15]Yi Xie,Liang Yongye,Huerta-Sanchez E,et al. Sequencing of 50 human exomes reveals adaptation to high altitude[J]. Science, 2010,329(12) :75 -78.   
[16］汤惠生,周春林,李一全,等.青海昆仑山山口发现的细石器考 古新材料[J].科学通报,2013,58（3）:247-253.[Tang Huisheng,Zhou Chunlin,Li Yiquan,et al.A new discovery of microlithic information at the entrance to the Northern Qingzang Plateau of the Kunlun Mountains of Qinghai[J].Chinese Science Bulletin,2013, 58(3) :247 -253.]   
[17]黄姣,高阳,赵志强,等.基于GIS 与 SOFM网络的中国综合自 然区划[J].地理研究,2011,30（9）:1649-1653.[Huang Jiao,Gao Yang,Zhao Zhiqiang,et al. Comprehensive physiographic regionalization of China using GIS and SOFM neural network[J]. Geographic Research,2011,30(9）:1 649 -1 653.]   
[18]国家文物局.中国文物地图集:青海分册[M].北京:中国地图 出版社,1996.[National Cultural Relics Bureau. Chinese Cultural Relics Atlas:Qinghai Section[M].Beijing:China Map Publishing House,1996. ]   
[19]国家文物局.中国文物地图集:云南分册[M].昆明：云南科技 出版社,2Oo1.[National Cultural Relics Bureau. Chinese Cultural Relics Atlas: Yunnan Branch[M]. Kunming:Yunnan Science and Technology Press,2001.]   
[20]国家文物局.中国文物地图集:四川分册[M].北京：文物出版 社,2009.[National Cultural Relics Bureau.Chinese Cultural Relics Atlas:Sichuan Volume[M]. Beijing:Cultural Relics Publishing House,2009.]   
[21］国家文物局.中国文物地图集:西藏自治区分册[M].北京：文 物出版社,2O1o.［National Cultural Relics Bureau.Chinese Cultural Atlas: Tibet Autonomy Book[M].Beijing: Cultural Relics Publishing House,2010.]   
[22］国家文物局.中国文物地图集:新疆维吾尔自治区分册〔M]. 北京：文物出版社,2012.[National Cultural Relics Bureau.Chinese Cultural Relics Atlas: Xinjiang Uygur Autonomous Region [M].Beijing:Cultural Relics Publishing House,2012.]   
[23]谢端琚.甘青地区史前考古[M].北京：文物出版社,2002. [Xie Duanju.Prehistoric Archaeology in Ganqing Area[M]. Beijing:Cultural Relics Publishing House,2002.]   
[24］张德二,李红春,顾德隆,等.从降水的时空特征检证季风与中 国朝代更替之关联〔J].科学通报,2010,55（1):60 －67. [Zhang De'er,Li Hongchun,Gu Delong,et al.On linking climate to Chinese dynastic change:Spatial and temporal variations of monsoonal rain[J].Chinese Science Bulletin,2010,55(1）:60-67.]   
[25］侯光良,魏海成,鄂崇毅,等.青藏高原东北缘全新世人类活动 与环境变化——以青海湖江西沟2号遗迹为例[J].地理学 报,2013,68(3）:380-388.[Hou Guangliang,Wei Haicheng,E Chongyi,et al.Human activities and environmental change in Holocene in the northeastern margin of Qinghai -Tibet Plateau:A case study of JXG2 relic site in Qinghai Lake[J].Acta Geographica Sinica,2013,68（3):380 -388.]   
[26]毕硕本,万蕾,沈香,等.郑洛地区史前聚落分布特征的空间自 相关分析[J].测绘科学,2018,43（5）:88－93.[Bi Shuoben, Wan Lei,Shen Xiang,et al.The spatial autocorrelation analysis for spatial distributionofprehistoric settlementsin Zhengzhou-Luoyang area[J]. Surveying Science,2018,43(5） :88 -93.]   
[27]杨阳,侯光良,孙璐,等.青藏高原东北缘河谷地带史前聚落空 间分布模式[J].干旱区资源与环境,2016,30（5）：59－64. [Yang Yang,Hou Guangliang,Sun Lu,et al. The spatial distribution patterns of prehistoricsettlement of river valley in the Northeast of the Qinghai- Tibetan Plateau[J].Journal of Arid Land Resources and Environment,2016,30(5）:59 -64.]   
[28］朱燕,侯光良,兰措卓玛,等.基于GIS 的青藏高原史前交通路 线与分区分析[J].地理科学进展,2018,37（3）:438－499. [Zhu Yan,Hou Guangliang,Lancuo Zhuoma,et al. GIS-based analysis of trafic routes and regional division of the Qinghai- Tibetan Plateau in prehistoric period[J].Progress in Geography,2018, 37(3) :438 -449.]   
[29］冯佰香,李加林,何改丽,等.农村居民点时空变化特征及驱动 力分析——以宁波市北仑区为例[J].生态学杂志,2018,37 (2）:523-533.[Feng Baixiang,Li Jialin,He Gaili,etal.Spatialtemporal changes and driving forces of rural settlements: A case study of Beilun District,Ningbo[J]. Journal of Ecology,2018,37 (2) :523 -533.]   
[30］魏晓峰,吴健平.基于ArcGIS 的空间自相关分析模块的开发与 应用[J].测绘与空间地理信息,2005,28（6)：78-81.[Wei Xiaofeng,Wu Jianping.The development and application of spatial autocorrelation based on ArcGIS[J]. Geomatics & Spatial Information Technology,2005,28(6）:78-81.]   
[31]侯光良.青藏高原的史前人类活动[J].盐湖研究,2016,24 (2）:69-73.[Hou Guangliang.The prehistoric human activities on the Qinghai - Tibet Plateau[J].Salt Lake Research,2016,24 (2) :69 -73. ]   
[32］李潮流,康世昌.青藏高原不同时段气候变化的研究综述[J]. 地理学报,2006,61（3）:327-335.[Li Chaoliu,Kang Shichang. A summaryof studies on climate change in diferent periods of the Tibetan Plateau[J].Acta Geographica Sinica,2006,61(3）:327 - 335.]   
[33]Wu Yanhong,Andreas Lucke,Jin Zhangdong,et al. Holocene climate developmenton thecentral Tibetan Plateau: Asedimentary record from CuoELake[J].PalaeogeographyPalaeoclimatology Palaeoecol,2006,234(4） :328 -340.   
[34］高春亮,余俊清,闵秀云,等.末次冰消期以来中国湖泊沉积记 录的古气候演化及其驱动机制研究[J].盐湖研究,2017,25 (2）:77 -84.[Gao Chunliang,Yu Junqing,Yan Xiuyun,et al. The study on paleoclimatic evolution and driving mechanisms since the Last Deglaciation recorded by lacustrine sediments in China [J].Salt Lake Research,2017,25(2）:77-84.]   
[35]Carolyn A,Dykoski R Lawrence Edwards,Cheng Hai,et al.A highresolution,absolute-dated Holocene and deglacial Asian monsoon record from Dongge Cave,China[J].Earth and Planetary Science Letters,2005,233:71-86.   
[36]Shen Jianbo,Liu Xiqin.Palaeoclimatic changes in the Qinghai Lake area during thelast18Ooyears[J].Quaternary International, 2005,136:131-140.   
[37]An Zhisheng,Steven M Colman,Zhou Weijian,et al. Interplay between the Westerlies and Asian monsoon recorded in Lake Qinghai sediments since $3 2  { \mathrm { \ k a } } \left[  { \mathrm { J } } \right]$ .Scientific Report,2012,2:619.DOI: 10.1038/srep00619.   
[38]Li Jianyong,John Dodson,Yan Hong,et al. Quantitative precipitation estimates for the Northeastern Qinghai - Tibetan Plateau over thelast 8 O0O yearsJ]. Joural ofGeophysical Research:tmos pheres,2017,122(10):5132-5 143.

[39]仪明洁，高星，张晓凌，等.青藏高原边缘地区史前遗址2009年调查试掘报告[J].人类学学报，2011，30(2）：124-136.［YiMingjie,Gao Xing,Zhang Xiaoling,et al.A preliminary report oninvestigations in 2OO9 of some prehistoric sites in the Tibetan Plat-eau marginal region[J].Journal of Anthropology,2O11,30（2）：124 -136. ]

[40]谢端琚.甘青地区史前考古[M].北京：文物出版社,2002. [Xie Duanju.Prehistoric Archaeology in Ganqing Area[M].Beijing:Cultural Relics Publishing House,2002.]

[41］王辉.甘青地区新石器一青铜时代考古学文化的谱系与格局 [M].北京：文物出版社,2012.［Wang Hui.The Pedigree and Pattern of the Neolithic-Bronze Age Archaeological Culture in Gansu Area[M].Beijing:Cultural Relics Publishing House,2012.] [42]侯光良，方修琦.中国全新世分区气温序列集成重建及特征分 析[J].古地理学报,2012,14(2）:243-252.[Hou Guangliang, Fang Xiuqi. Characteristics analysis and synthetical reconstruction ofregional temperature series of the Holocene in China[J].Journal ofPalaeogeography,2012,14（2）:243-252.]

[43]吴海斌,李琴，于严严，等.全新世中期中国气候格局定量重建 [J].第四纪研究,2017,37(5）:982-998.[Wu Haibin,Li Qin, Yu Yanyan,et al. Quantitative climate reconstruction in China during the Mid-Holocene[J].Quaternary Research,2017,37（5）： 982 -998.]

[44]易华.齐家华夏说［M].兰州：甘肃人民出版社，2014.［Yi

Hua. Qijia Huaxia Legend[M].Lanzhou:Gansu People's Press,

∠U14.」  
[45]张山佳，董广辉.青藏高原东北部青铜时代中晚期人类对不同海拔环境的适应策略探讨[J].第四纪研究，2017，37（4)：696-703.[Zhang Shanjia,Dong Guanghui.Human adaptation strategiesto different altitude environment during mid-late bronze age in theNortheast Tibetan Plateau[J].Quaternary Research,2O17,37（4）：696 -703.]  
[46]杨周相.吐蕃王朝前西藏社会发展研究[J].黑龙江史志，2014,17（4）:188-190.[Yang Zhouxiang.Study on the socialdevelopment of Tibet before the Tubo Dynasty[J].HeilongjiangHistory,2014,17(4):188-190.]  
[47]葛全胜，刘健,方修琦，等.过去2000 年冷暖变化的基本特征与主要暖期[J].地理学报，2013,68（5）：579-592.[GeQuan-sheng,Liu Jian,Fang Xiuqi,et al.General characteristics of tem-perature change and centennial warm periods during the past 2 000years[J].Acta Geographica Sinica,2013,68(5）:579-592.]  
[48]侯光良，许长军.过去2000 年来青藏高原气温变化及对人类活动的影响[J].青海师范大学学报（自然科学版）,2016,3(12）:56-62.［Hou Guangliang,Xu Changjun.The temperaturechange and its influence for human movement of the Tibet Plateauover the past 2 OOO years[J].Journal of Qinghai Normal University（Natural Science Edition）,2016,3（12）:56-62.]

# Spatiotemporal Changes and Driving Factors of Cultural Relicts on the Tibetan Plateau Since the Holocene

JIN Sun-mei1， HOU Guang-liang²， XU Chang-jun³， Lancuo Zhuoma'， LI Sheng-mei $^ { 1 }$ （204号 (1.College of Geographical Science,Qinghai Normal University,Xining 81Ooo8,Qinghai,China;   
2.Qinghai Province KeyLaboratoryof Physical GeographyandEnvironmentalProcess,Qinghai NormalUniversity,Xining   
810008,Qinghai,China; .QinghaiProvinceKeyLaboratoryofGeospatialInformationTechnologyandItsApplication,Xining1o,Qinghai,hina)

Abstract：Based on the ArcGIS spatialanalysis,inthis paperthe geostatistical methods including the kernel density estimation,average nearest neighborindex and global spatialautocorelation wereused tostudythe spatiotemporal evolutionof14339 ancientcultural relicsand theafecting factors on the Tibetan Plateau since the Holocene.The results showedthat the nearest neighbor index of each ancient cultural relic was lessthan1.Thevalueof the global Mo ran's $I$ was between Oand1,there was a positive spatial autocorrelation of the ancient cultural relics,and the ancient cultural relics weredistributed inanagglomeration way.Thedistributioncoreof the ancientcultural relics experienced a transition from the plateau hinterland（the Paleolithic period）tothe southeasten marginal valley（the Neolithic period）and tothe eastern region（after the Bronze Age).The morphological characteristics ofthe ancientcultural relics experienced auniform distribution（the Paleolithic period）,the marginal valleytype（the Neolithic period）,the valey agglomeration type（bronze period）,the degraded dispersion type（the Tibetan regime tribe period）,and the halfmoon widespread type（the Tubo Dynasty period）,the plaque-type（the Yuan Dynasty）,and thecontiguous cluster (the Mingand Qingdynasties）changes.The spatiotemporal distribution of the ancient culturalrelics on the Tibetan Plateau was the result jointlyafected bythe altitude,climatechange,changes of vegetationand other natural conditions,and production mode,technology,war,population migration,political policies,etc.

Key words:Holocene；ancient cultural relic； spatiotemporal change；Tibetan Plateau