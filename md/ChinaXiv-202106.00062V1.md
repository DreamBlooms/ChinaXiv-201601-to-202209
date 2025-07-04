# 基于SWAT模型的开都河流域水文干旱变化特征及驱动因子分析

宋玉鑫¹，左其亭12.3，马军霞1,3（1.郑州大学水利科学与工程学院,河南 郑州450001；2.郑州大学水科学研究中心，河南 郑州 450001；3.郑州市水资源与水环境重点实验室,河南 郑州 450001)

摘要：以开都河流域为例,以SWAT(Soil and Water Assessment Tol)分布式水文模型和标准化降水蒸散指数(SPEI)为基础,对干旱变化特征进行识别。利用贝叶斯动态线性方程(BDL)模型研究南方涛动(SOI)等气候驱动因子对区域季节性干旱的影响。结果表明：1965—2016年开都河流域的干旱主要集中于冬、春季;在不同季节,流域干旱的变化趋势也有所不同,但趋势并不明显，仅在秋冬季可以检测出显著下降的趋势;不同季节的SPEI指数变化受降水、潜在蒸散发等气候因素的响应较快，多在0值上下波动，导致其变化周期较短,多集中在 $2 { \sim } 4 \mathrm { a }$ ；气候指数对流域干湿变化的影响随着时间的推移而转变，对不同季节的影响也有所不同。

关键词：SWAT模型；动态线性模型；标准化降水蒸散指数(SPEI)；开都河流域

近几十年，干旱的变化受到了各国学者们的广泛关注，干旱发生的频率和强度都呈现出上升的态势，总的来说，从1950—2008年间，全球干旱地区的百分比每10a增加 $1 . 7 4 \% ^ { [ 1 ] }$ 。我国是受干旱影响较大的国家之一，仅在2017年就造成直接经济损失约$8 . 8 2 \times 1 0 ^ { 1 0 }$ 元[2]。由于气候变化的影响,受干旱影响的程度日益增大。20世纪90年代末以来，我国干旱面积平均每10a增加 $3 . 7 2 \% ^ { [ 3 ] }$ ，例如华北地区在1997年遭受了严重的干旱，从而导致黄河下游地区断流长达 $2 2 6 { \mathrm { ~ d } } ^ { [ 4 ] }$

开都河是新疆的内陆河流，也是唯一常年补给博斯腾湖的河流，但是近年来由于全球气候变暖的影响,开都河流域的气温表现出了上升趋势[5],作为当地重要的农业灌溉、发电，生态环境建设以及排污和地下水补给的主要水源，气温引发的持续干旱将对开都河流域当地的经济社会发展产生不利影响。因此，研究该地区干旱特征及成因，对更好的适应和缓解干旱的影响，制定可持续发展的战略有重要的意义。

干旱是缓慢而反复发生的自然灾害，政府间气候变化专门委员会(IPCC)第五次评估报告(AR5)将干旱定义为“一段异常干燥的天气，在其持续时间内足以造成严重的水文失衡”6,作为一种极端现象，干旱可能持续数周、数月甚至数年。根据侧重领域的不同,将干旱划分为气象干旱、水文干旱、农业干旱以及社会经济干旱四大类，4种干旱常交叉发生"，作为水文、农业、经济社会干旱发生的前兆，本文主要研究气象干旱。

为了量化干旱持续的时间、严重程度、强度等特征，从而对干旱进行全面的描述，干旱指标获得了广泛的使用[8-10]。常用的气候指数包括:Palmer干旱指数(PDSI)[1]、标准化降水指数(SPI)[12]、标准化降水蒸散指数(SPEI)[13]。PDSI指数的计算过程复杂，所需资料繁琐，具有固定的时间尺度，并且其参数是基于美国中部地区得出的，可适用性较差[14]。与之相比，SPI仅需要使用降水数据便可求出区域的干旱情况，且可测量不同时间尺度的干旱情况。但是已有的研究除了降水外，其余气候因素，如温度、风速、水汽含量等均可导致干旱[15]。为了弥补PDSI和SPI指数的不足，选用SPEI指数来衡量区域的干旱变化，该指标引入潜在蒸散发的概念在计算过程中包含了温度信息，且适用于多尺度和不同的气候条件，因此成为了衡量全球和区域气候变化背景下干旱监测和分析的有力指标，

为了计算SPEI指数需要依赖气象站的降水、潜在蒸散发等时间序列数据，弥补中国气象站点分布不均匀，特别是在较小的研究区，气象站点分布较少，无法准确的表现出区域的干旱情况。利用SWAT模型可进行下垫面的土地利用、土壤条件等，对流域水文过程进行模拟，得到各个子流域的地表径流、降水、潜在蒸散发等计算所需要的时间序列[6]，从而提高流域SPEI的计算精度，更好的分析出干旱的变化特征及时空分布规律。

基于此，本文以开都河流域为例，主要研究目标为：（1）构建开都河流域的SWAT模型，模拟出开都河流域1965—2017年的降水及潜在蒸散发数据;（2）以上述序列为基础，计算开都河流域的SPEI指数，分析干旱时空演变等特征；（3）构建BDL方程，调查大规模气候驱动因素对开都河干旱的动态影响。

# 1研究区概况与研究方法

# 1.1 研究区概况

开都河流域 $( 4 2 ^ { \circ } 1 4 ^ { \prime } { \sim } 4 3 ^ { \circ } 2 1 ^ { \prime } \mathrm { N } , 8 2 ^ { \circ } 5 8 ^ { \prime } { \sim } 8 6 ^ { \circ } 0 5 ^ { \prime } \mathrm { E } )$ 位于塔里木河中下游，其主要来水方式为雪冰融水、降水、地下水补给3种方式，最终汇人中国最大的内陆淡水湖一一博斯腾湖(图1)。开都河流域整体地势呈现西北高、东南低的走势，流域底部较为平坦,四周高山环绕[17]。开都河流域位于我国西北部地区，该地区远离海洋，水汽输送受到青藏高原和天山山脉的阻隔，是我国气候变化较为敏感的地区，降水量稀少加之强烈的人类活动加剧了气候突变的可能性，干旱等极端事件发生的频率也增加，因此以该区域为研究对象，探究水文干旱的特点以及驱动因素，以期为开都河流域气象干旱预防和管理提供依据。

![](images/816fb2317b4db345c90048df49118f6f7578dfe6dbdb33118832690d5f76dac5.jpg)  
图1开都河流域位置示意图  
Fig.1Study area of Kaidu river basin

# 1.2 研究方法

1.2.1 SWAT模型SWAT模型是由美国农业部农业服务中心开发的一种基于物理过程、流域尺度及连续时段的分布式水文模型，不仅能够模拟出长时间序列的水文过程，而且在资料缺乏的区域同样也可建立起水文过程的模拟，模拟结果能清楚的展示出流域从降水到径流的每一个过程，因此得到了广泛的应用[18]

本文使用的数据主要有DEM数据、土壤数据、土地利用数据、气象数据等，数据来源见表1。基于以上的数据构建SWAT模型，从而模拟出开都河流域1965—2016年各子流域的参数。首先应建立土壤类型及土地利用数据库，对照HWSD(世界土壤数据库)索引表以及使用SPAW软件计算研究区中的所有土壤类型参数,并创建对应的土壤数据库。土地利用类型数据库则根据下载数据的格式，对比SWAT模型允许的土地利用类型参数，建立索引表，从而构建相应的土地利用数据库

由于开都河流域气象站点分布较少，带入SWAT模型中所构建出的气象数据库，无法完全的

# 表1数据资料

Tab.1 Data sources used in this manuscript   

<html><body><table><tr><td>数据类型</td><td>数据说明</td><td>数据来源</td></tr><tr><td>DEM数据</td><td>30m分辨率</td><td>地理空间数据云平台</td></tr><tr><td>土壤数据</td><td>1km分辨率</td><td>世界土壤数据库</td></tr><tr><td>土地利用数据</td><td>1 km分辨率</td><td>资源环境科学与数据中心</td></tr><tr><td>气象数据</td><td>世界天气数据库</td><td>国家环境预测中心(NECP)</td></tr></table></body></html>

模拟出当地的降水、气温等情况，因此本文使用美国国家环境预报中心(NECP)的气候预报系统再分析数据(Climate Forecast System Reanalysis,CFSR)来构建本模型的气象数据库。该数据是专门针对SWAT模型所提出的数据集，具有分辨率高、可利用性强、时间序列长、更新速度快等优点，已被证明最适合中小尺度的水文模拟[19]

笔者使用DEM数据进行汇流分析以及河网提取，自动计算出流域的面积，并通过设置最小集水面积阈值，将开都河流域划分为15个子流域，然后将土壤数据、土地利用数据进行叠置分析，设置土地利用、土壤和地表坡度的阈值，进行HRU的划分。1.2.2千旱指标 标准化降水蒸散指数(SPEI)是使用月降水量和潜在蒸散发量的差值描述干旱状态的指标，能客观地描述区域的干湿变化。SPEI具有多时间尺度的优点，不同时间尺度的SPEI可反应出不同的干旱现象，有研究表明3个月、6个月和12个月这3种时间尺度的SPEI可以分别代表气象干旱、生态干旱和水文干旱[20]。本文主要研究气象干旱的变化特征且3个月时间尺度可以反映季节的干湿变化状况[2I],选用3个月时间尺度的SPEI值来表征开都河流域四季的干旱变化情况，以3一5月表明春季、6—8月表明夏季、9—11月表明秋季、12月至次年2月为冬季，表2显示了基于SPEI值的不同干旱情况。SPEI的具体计算过程为：

$$
D _ { i } { = } P _ { i } { \mathrm { - } } \mathrm { P E T } _ { i }
$$

式中： $P _ { i }$ 为月降水量； $\mathrm { P E T } _ { i }$ 为月潜在蒸散发量，使用log-logistics概率分布函数拟合对降水蒸发差值$D _ { \ i }$ 数据序列进行标准化,得到累计概率函数 $F ( D )$ ○

$$
F ( D ) = \left[ 1 + \left( { \frac { \alpha } { D - \gamma } } \right) ^ { \beta } \right] ^ { - 1 }
$$

式中：参数 $\alpha , \beta , \gamma$ 分别为通过线性矩方法进行估计的尺度、形状和位置参数。

对累计概率密度函数 $F ( D )$ 进行正态标准化：

$$
P = 1 - F ( D )
$$

$$
W = { \sqrt { - 2 \ln ( P ) } }
$$

$$
\mathrm { S P E I } = \left\{ \begin{array} { l l } { \displaystyle W - \frac { c _ { 1 } + c _ { 2 } W + c _ { 3 } W ^ { 2 } } { 1 + t _ { 1 } W + t _ { 2 } W ^ { 2 } + t _ { 3 } W ^ { 3 } } \quad , \quad P \leqslant 0 . 5 } \\ { \displaystyle - \left( W - \frac { c _ { 1 } + c _ { 2 } W + c _ { 3 } W ^ { 2 } } { 1 + t _ { 1 } W + t _ { 2 } W ^ { 2 } + t _ { 3 } W ^ { 3 } } \right) \ : , \quad P > 0 . 5 } \end{array} \right.
$$

式中： $c _ { 1 } = 2 . 5 1 5 5 1 7$ 、 $c _ { 2 } = 0 . 8 0 2 8 5 3$ 、 $c _ { 3 } = 0 . 0 1 0 3 2 8$ 、

# 表2基于SPEI的干旱等级划分

Tab.2 Classification of drought grades based on SPEI   

<html><body><table><tr><td>干湿等级</td><td>SPEI</td></tr><tr><td>轻度干旱</td><td>(-1,-0.5)</td></tr><tr><td>中等干旱</td><td>[-1,-1.5)</td></tr><tr><td>重度干旱</td><td>[-1.5,-2]</td></tr><tr><td>极端干旱</td><td>≤-2</td></tr></table></body></html>

$t _ { 1 } = 1 . 4 3 2 7 8 8$ 、 $t _ { 2 } = 0 . 1 8 9 2 6 9$ 、 $t _ { 3 } = 0 . 0 0 1 3 0 8$ 0

1.2.3动态线性方程使用贝叶斯动态线性方程(BayesianDynamicLinearBDL)来评价大尺度气候驱动因素对十旱的时变影响。与只有一个回归系数的传统的线性模型不同，BDL能够对气候驱动因素与气候因子之间随时间的动态关系进行建模，因此其准确性高于传统线性模型，但是在干旱分析中的应用仍有限[22]。BDL的公式为：

$$
\left\{ \begin{array} { l l } { y _ { t } = \alpha _ { t } + x _ { t } \beta _ { t } + \nu _ { t } , \nu _ { t } - N \Big ( 0 , \sigma _ { v } ^ { 2 } \Big ) } \\ { \alpha _ { t } = \alpha _ { t - 1 } + \omega _ { \alpha , t } , \omega _ { \alpha , t } - N \Big ( 0 , \sigma _ { \alpha } ^ { 2 } \Big ) } \\ { \beta _ { t } = \beta _ { t - 1 } + \omega _ { \beta , t } , \omega _ { \beta , t } - N \Big ( 0 , \sigma _ { \beta } ^ { 2 } \Big ) } \end{array} \right.
$$

式中： $\boldsymbol { y _ { t } }$ 是响应变量(干湿系数)； $x _ { t }$ 是协变量(气候因素）; $\nu _ { { } _ { t } }$ 为观测误差； $\boldsymbol { \omega } _ { t }$ 为评价误差； $\alpha _ { { } _ { t } }$ 和 $\beta _ { t }$ 是在时间 $\mathbf { \Phi } _ { t }$ 上的动态截距和斜率系数。

1.2.4其他方法除了上述的方法外，使用采用Mann-Kendall非参数检验分析SPEI指数在四季的变化趋势，该方法不需要样本遵从特定的分布，且不受少数异常值的干扰，定量化程度高，在检验序列的变化趋势方面有很大的优势，得到了广泛的应用[23]。采用小波功率谱分析了季尺度下SPEI指数的周期变化特征，该方法具体步骤见参考文献[24]。

# 2结果分析

# 2.1季尺度SPEI时间变化

由图2可以看出，不同季节干湿变化波动较为明显，说明降水、蒸散发等因素对季尺度下的干旱情况影响较为明显。在春季共发生了41次干旱事件，其中36次为轻度干旱事件，其余5次均为中度干旱事件;在夏季共出现了33次干旱事件，有23次轻度干旱事件，7次中度十旱事件，3次重度干旱事件，其中最严重的干旱事件发生于2001年6月，其SPEI值为-1.67；秋季发生了35次干旱事件，有25次为轻度干旱事件，其余均为中度干旱事件，在1968年10月统计出了最为严重的干旱事件，其SPEI值为-1.47;在冬季，统计表明共发生了37次干旱事件，有22次为轻度干旱，15次为中度干旱。可见开都河流域干旱事件多发于冬、春季，且多以轻度与中度干旱为主，仅在夏季可以检测出重度干旱事件。

![](images/5c5439e093af43e62fc18cd0337329c519e9b67d30e624366aa456c00cc5ae12.jpg)  
图2不同季节SPEI时间序列Fig.2SPEI time series of different seasons

# 2.2季尺度SPEI空间变化

由图3可以看出，在春、夏季，SPEI指数的变化趋势均没有通过 $9 0 \%$ 的显著性检验。在春季，呈现上升趋势的地区主要分布在开都河流域的西北部地区，仅有1个子流域表现出下降趋势。而在东南部地区，以下降趋势为主，有2个子流域表现出上升趋势；夏季与春季相反，北部地区均表现出了下降的趋势，而在南部则以上升趋势为主，仅有2个子流域表现出下降趋势；秋季在流域的中部地区可以检测出显著的下降趋势，在西部与东部地区则主要表现出下降趋势，北部地区以上升趋势为主；冬季仅在西北与东南的部分地区可以检测出上升及显著下降的趋势，其余子流域则主要表现出下降趋势。

# 2.3季尺度SPEI周期变化

为了更好的揭示开都河流域不同季节SPEI年代际周期变化特征，使用小波功率谱分析其周期变化特征。图4为不同季节 SPEI的小波功率谱[25],春季的小波功率谱表明在1972—2010年间在整个研究期间存在着2\~4a的变化周期，4\~6a的变化周期则主要在1990—2000年间被发现；夏季SPEI在1972—1988年间存在着2\~4a的周期，在20世纪90年代后期其变化周期主要为2\~5a;秋季SPEI的周期变化较为分散，在整个研究期内没有明显的周期变化特征，2\~4a的周期变化仅在1990—2005年间发现，在1980—1985年间存在6a的变化周期，在21世纪后可检测到3\~6a的变化周期，但其大部分面积位于COI范围外；冬季SPEI在21世纪前具有明显的2\~3a变化周期，而在21世纪后期变化周期变换为 $3 { \sim } 5 \mathrm { a }$ 。

# 2.4干旱的气候驱动因素

为研究大气环流事件对开都河流域干湿变化的影响，我们选用南方涛动指数（SouthernOscilla-tionIndexSOI)衡量ENSO(厄尔尼诺与南方涛动)现象。ENSO通过影响东亚季风环流和太平洋副热带高压，对中国沿海及内陆产生影响，当SOI为正数时对应拉尼娜现象(LaNina)，反之则为厄尔尼诺现象(ElNino）,该指标从NOAA上下载(https://www.ncdc.noaa.gov/teleconnections/enso/indicators/soi)。已有的研究表明，ENSO对区域的干旱变化影响较大，因此更好的揭示ENSO对开都河流域干旱变化的影响，使用BDL方程量化1965—2016年之间两者的动态相关性。

图5a表明，在春季SPEI与SOI之间，经历了从

![](images/b3a4064fcef3e9f9ee7b11ef1d8e3d7f58404d16aff0f413dfb06f97d1534423.jpg)  
图3不同季节SPEI空间变化趋势

![](images/f47623ac2cdc9fdba2e30fcb830fbdf212fa1185fa32e4c4a31aea095f7b6dc7.jpg)  
Fig.3Spatial variation trends of SPEI in different seasons   
图4不同季节SPEI指数的小波功率谱  
Fig.4Wavelet power spectrum of SPEI in different seasons

注：U型线代表小波影响椎(COI),该范围内为有效谱值;粗黑线封闭区域表明通过了显著性水平 $5 \%$ 条件下的红噪声标准谱检验。

![](images/2740a27af813df095204cf5572360561f437e716c108d73f64e160927b7ae673.jpg)  
图5不同季节SPEI指数与SOI之间的动态关系

注：黑色实线为估计的相关系数，红色实线为 $9 5 \%$ 的置信区间。

Fig.5Variations intherelationshipbetweenregionalSPEIindifferentseasonsand large-scaleclimateoscilations

1976年之前的负相关，转变为1995年前的正相关，随后两者之间文呈现出了负相关一直持续到2015年，之后又表现出上升态势；夏季两者之间斜率系数的转变发生于1990年左右，随后又在2002年左右发生了由负到正的转变，波谷出现在1996年左右，波峰则出现在1983年左右，整体来看，SOI对夏季 SPEI的影响较弱；随着时间的演变秋季SPEI与气候指数的相关性波动较为明显且SOI对开都河流域秋季的干湿变化影响较为明显，在20世纪70年代相关性经历了第一次转变，在1976一2000年间SOI对SPEI的影响主要为正相关，而SOI在该时期主要以负相位为主，预计开都河流域的SPEI会下降，从而导致开都河流域的秋季气候更为干旱；图5d表明在冬季，SOI对SPEI的影响并不明显，两者相关性系数在 $- 0 . 1 { \sim } 0 . 1$ 之间，相关性仅在20世纪90年代发生了一次由正到负的转变。整体来看，SOI对开都河流域四季的影响其波峰主要出现在1980年左右，而波谷则主要出现在2000年左右，表明在该时段SOI对SPEI的影响较为明显。

本文的研究结果表明：在1965—2016年间ENSO对开都河的干旱变化具有动态的影响，ENSO分别在20世纪70年代、80年代、90年代经历了相变[22]，这也与ENSO对春、夏、秋季SPEI相关系数发生转变的点相近，且在21世纪后ENSO对3个季节干旱的影响主要为正相关。表明ENSO是驱动开都河流域干旱变化的主要因素，20世纪80年代后期以来SOI指数波动较为强烈，ElNino/LaNina事件波动加剧且ElNino事件发生强度大于LaNina事件[26],表明SOI在这一时段内多为负值，由于在这一时期内对SPEI具有正相关影响，表明开都河流域在春、夏、秋季气候更为干旱，而在冬季则ENSO对开都河有负相关影响，SPEI指数将上升，呈现出变湿的趋势。

脆弱敏感的生态系统以及过度的人为活动，使开都河流域气象干旱具有十分明显的区域性和复杂性，因此对开都河流域的干旱进行预测与防治对地区的经济社会发展具有重要的意义。而ENSO对气象干旱的演变具有不可忽视的作用,中国气候干湿变率年际和年代际变化都对应着强厄尔尼诺事件[27],在我国西北地区ENSO当年降水量减少,次年夏季降水强度也将下降28，因此探究ENSO事件强度、出现时间将预测该地区的干旱演变具有一定的意义。

# 3结论

（1）1965—2016年开都河流域的干旱多以轻度与中度干旱为主，仅在夏季出现了重度干旱事件，且干旱多发于冬、春季。

(2）不同季节，开都河流域的SPEI在空间分布上也有所不同，在春季主要表现为北部地区呈上升趋势，南部地区呈现出下降趋势，夏季空间分布则相反。秋、冬季SPEI主要表现出了下降趋势，并可检测出显著的下降趋势，表明在秋、冬季干旱事件将有所上升。

(3）在不同季节上的SPEI小波功率谱表明在季尺度下SPEI的变化周期较小，主要集中在2\~4a的变化周期，春、冬季在20世纪90年代后期表现出了4\~6a的变化周期，表明季尺度下开都河流域的干湿情况受降水等因素影响较大，年际变化明显。

(4）分析了大气环流指数在不同季节上对开都河流域干旱情况的动态影响，在不同季节上，SOI对干旱的影响有所不同，对秋季的影响较为显著，且波动较为明显。整体来看在1980以及2000年左右是影响最为强烈的两个时间段，

# 参考文献(References):

[1] Dai A.Characteristics and trends in various forms of the Palmer drought severity index during 19OO-2OO8[J]. Journal of Geophysical Research Atmospheres,2011,116(D12).Doi: 10.1029/2010 JD015541.   
[2] 吴桂炀,陈杰,陈启会,等.金沙江流域近50年气象水文干旱时 空变化特征[J].人民长江,2019,50(11):84-90.[Wu Guiyang, Chen Jie,Chen Qihui,et al. Spatiotemporal variation of hydro-meteorological drought in Jinsha River Basin in recent 5O years[J]. Yangtze River,2019,50(11): 84-90.]   
[3] Yu M,Li Q,Hayes M J,et al. Are droughts becoming more frequent or severe in China based on the Standardized Precipitation Evapotranspiration Index:1951-2O1O[J]. International Journal of Climatology,2014,34(3): 545-558.   
[4] Cong Z, Yang D,Gao B,et al.Hydrological trend analysis in the Yellow River basin using a distributed hydrological model[J].Water Resources Research,2009,45(7).https://doi.org//10.1029/ 2008WR006852.   
[5] 冯娟.开都河径流量对气候变化的响应分析[J].陕西水利，2019 (7): 67-69,72.[Feng Juan.Analysis on the response of Kaidu River runoff to climate change[J]. Shaanxi Water Resources,2019(7): 67-69,72.]   
[6] IPCC,2014. Climate Change 2O14: Synthesis Report. Contribution of Working Groups I, II and II to the Fifth Assessment Report of the Intergovernmental Panel on Climate Change(Geneva, Switzerland).   
[7]张洪波,顾磊,辛琛,等.泾河流域干旱特征时空变化研究[J].华 北水利水电大学学报(自然科学版),2016,37(3):1-10.[Zhang Hongbo,Gu Lei,Xin Chen,et al.Investigation on the spatial-temporal variation of drought characteristics in Jinghe River Basin [J]. Journal of North China University of Water Resources and Electric Power (Natural Science Edition),2016,37(3):1-10.]   
[8]邹磊,余江游,夏军,等.基于SPEI的渭河流域干旱时空变化特 征分析[J].干旱区地理,2020,43(2):329-338.[Zou Lei,Yu Jiangyou,Xia Jun,etal.Temporal-spatial variationcharacteristics of drought in the Weihe River Basin based on SPEI[J].Arid Land Geography,2020,43(2): 329-338.]   
[9]周帅,王义民,畅建霞,等.黄河流域干旱时空演变的空间格局 研究[J].水利学报,2019,50(10):1231-1241.[Zhou Shuai,Wang Yimin, Chang Jianxia,et al. Research on spatio-temporal evolution of drought patterns in the Yellow River Basin[J]. Journal of Hydraulic Engineering,2019,50(10): 1231-1241.]   
[10] 贺晓婧,荣艳淑.长江流域上游干旱特征分析[J].水电能源科 学,2020,38(1):1-4.[He Xiaojing,Rong Yanshu. Analysis of drought characteristics in upper reaches of the Yangze River Basin[J]. Water Resources and Power,2020,38(1): 1-4.]   
[11]Alley W M.The palmer drought severity index: Limitations and assumptions [J]. Journal of Climate and Applied Meteorology,1984, 23(7):1100-1109.   
[12] 朱圣男,刘卫林,万一帆,等.抚河流域干旱时空分布特征及其 与 ENSO 的相关性[J].水土保持研究,2020,27(6):131-138. [Zhu Shengnan,Liu Weilin,Wan Yifan,et al. Temporal and spatial distribution characteristics of drought and its correlation with ENSO in Fuhe river basin[J]. Research of Soil and Water Conservation,2020,27(6): 131-138.]   
[13]Vicente-serrano S M,Begueria, Santiago,et al.A multiscalar drought index sensitive to global warming: The standardized precipitation evapotranspiration index[J]. Journal of Climate,2010,23(7): 1696- 1718.   
[14] Guttman N B, Wallis JR,Hosking JR M.Spatial comparability of the palmer drought severity index[J]. Journal of the American Water Resources Association,1992,28: 1111-1119.   
[15]Wang W, Zhu Y, Xu R,et al. Drought severity change in China during 1961-2012 indicated by SPI and SPEI[J]. Natural Hazards, 2015, 75(3): 2437-2451.   
[16] 赵安周,刘宪锋,朱秀芳,等.基于SWAT模型的渭河流域干旱 时空分布[J].地理科学进展,2015,34(9):1156-1166.[Zhao Anzhou,Liu Xianfeng,Zhu Xiufang,et al. Spatiotemporal patterns of droughts based on SWAT model for the Weihe River Basin[J]. Progress in Geography,2015,34(9): 1156-1166.]   
[17] 刘斯文,刘海隆,王玲.开都河流域土地利用/覆被变化对径流 的影响[J].人民黄河,2018,40(7):22-26.[Liu Siwen,Liu Hailong,Wang Ling.Influence of LUCC on runoff in Kaidu River Basin [J]. Yellow River,2018,40(7): 22-26.] [18]Arnold JG,Srinivasan R,Muttiah RS.Large area hydrologic modeling and assessment parti: Model development[J]. Journal of the American Water Resources Association,1998,34(1):73-89. [19]胡胜,曹明明,邱海军,等.CFSR气象数据在流域水文模拟中的 适用性评价—以灞河流域为例[J].地理学报,2016,71(9):   
1571-1586.[Hu Sheng,Cao Mingming,Qiu Haijun, et al.Applicability evaluation of CFSR climate data for hydrologic simulation: A case study in the Bahe River Basin[J].Acta Geographica Sinca,   
2016,71(9): 1571-1586.] [20] 胡文峰,陈玲玲,姚俊强,等.近55年来新疆多时间尺度干旱格 局演变特征[J].人民珠江,2019,40(11):1-9,27.[Hu Wenfeng, Chen Lingling,Yao Junqiang,et al.Evolution characteristics of drought patterns at multiple timescales in Xinjiang for last 55 years [J].Pearl River,2019,40(11): 1-9,27.] [21]赵慧,姚俊强,李新国,等.新疆气候干湿变化特征分析[J].中山 大学学报(自然科学版),2020,59(5):126-133.[Zhao Hui,Yao Junqiang,Li Xinguo,et al. The characteristics of climate change in Xinjiang during 1961-2015[J].Acta Scientiarum Naturalium Universitatis Sunyats,2020,59(5): 126-133.] [22]Yang Y,Gan TY,Tan X. Spatiotemporal changes of drought characteristics and their dynamic drivers in Canada[J].Atmospheric research,2020,232: 104695.1-104695. 17. [23]Jiang R,Wang Y,Xie J,et al.Assessment of extreme precipitation events and their teleconnections to El Nino Southern Oscillation,a case study in the Wei River Basin of China[J].Atmospheric Research,2019,218:372-384.   
[24]Torrence C,WebsterPJ.Interdecadal Changes in the ENSO-Monsoon System [J].Journal of Climate,1999,12: 2679-2690.   
[25]Torrence C,Compo G P.A practical guide to wavelet analysis[J]. Bulletin of the American Meteorological Society,1998,79(1): 61-78.   
[26] 谢培,张玉虎,乔飞.新疆极端降水时空特征及其对ENSO影响 的响应研究[J].气象研究与应用,2019,40(3):5-12.[Xie Pei, Zhang Yuhu,Qiao Fei. Spatial and temporal characteristics of extreme precipitation in Xinjiang and its response to ENSO[J]. Journal of Meteorological Research and Application,2019,40(3): 5-12.]   
[27] 苏明峰,王会军.中国气候干湿变率与ENSO的关系及其稳定 性[J].中国科学D辑(地球科学),2006,36(10):951-958.[Su Mingfeng,Wang Huijun. The relationship between China's climate variability and ENSO and its stability[J].Science in China Ser.D (Earth Sciences),2006,36(10): 951-958.]   
[28] 张强,姚玉璧,李耀辉,等.中国西北地区干旱气象灾害监测预 警与减灾技术研究进展及其展望[J].地球科学进展,2015,30 (2):196-213.[Zhang Qiang,Yao Yubi,Li Yaohui,et al.Research progress and prospect on the monitoring and early warning and mitigation technology of meteorological drought disaster in northwest China[J].Advances in Earth Science,2015,30(2): 196-213.]

# Variation and dynamic drivers of drought in Kaidu River Basin based on the SWAT model

SONG Yuxin'， ZUO Qiting1,2,3， MA Junxia1,3 (1.School of Water Conservancy Engineering,Zhengzhou University,Zhengzhou 45Ooo1,Henan, China; 2.Center for Water Science Research, Zhengzhou University,Zhengzhou 45Ooo1,Hennan, China; 3. Zhengzhou Key Laboratory of Water Resource and Environment,Zhengzhou 45ooo1,Henan, China)

Abstract: This study used Kaidu River Basin as an example to construct a soil and water assessment tool (SWAT）distributed hydrological model and standardized precipitation evapotranspiration index (SPEI) as the basis to identify variation in drought. Subsequently,the Bayesian Dynamic Linear Equation (BDL)model was used to determine the impact of climate driving factors,such as the Southern Oscilation (SOl),on regional seasonal drought.The results showed that the drought in the Kaidu River Basin from 1965 to 2016 was primarily concentrated in winter and spring.In diffrent seasons,variation in the Kaidu basin was different,but most trends were not significant,and significant decreasing trends were only detected in autumn and winter. Changes in the SPEI index in different seasons were affected by climate factors，such as precipitation and potential evapotranspiration,and mostof them fluctuated around O,resulting in a shortchange cycle,mostly concentrated in 2-4 years.The impact of the climate index on drought variability changed over time,and the impact on different seasons was also different.

Keywords: SWAT model; dynamic linear model; standardized precipitation evapotranspiration index (SPEI); Kaidu River basin