# 乌鲁木齐市生态环境遥感评价及驱动因子分析

排日海·合力力¹²，昝梅²，阿里木江·卡斯木1.2(1.新疆师范大学地理科学与旅游学院,新疆乌鲁木齐830054；2.新疆师范大学丝绸之路经济带城市发展研究中心,新疆 乌鲁木齐830054)

摘要：生态环境质量评估对于区域社会经济的可持续发展至关重要。以新疆乌鲁木齐市为研究区,通过对2000年、2010年和2019年3期Landsat系列数据进行预处理,利用主成分分析法构建遥感生态指数(Remote Sensing Eco-logical Index,RSEI),使用地理探测器中单因子分析和多因子交互作用分析法对RSEI的8个影响因子（人口密度、土地利用类型、海拔高度、经济密度、绿度、湿度、热度和干度)进行影响程度的定量探测,进而揭示出影响研究区生态环境质量的主导因素。结果表明：(1)2000年、2010年和2019年乌鲁木齐市RSEI均值分别为 $0 . 2 1 , 0 . 2 1 , 0 . 2 3$ 呈增加趋势,研究期内乌鲁木齐市生态变好的面积大于变差的面积,说明乌鲁木齐市的生态环境质量处于转好的状态；(2）近20a研究区8个影响因子中单因子热度指标对RSEI的空间分异特征解释力最强；（3）研究区生态环境的空间分布特征是多种影响因子共同交互作用的结果,在考虑多因子交互作用情景下人口密度,绿度指标和干度指标是区域生态环境质量状况的主要影响因素和关键驱动力。评价区域生态环境质量，了解生态环境状况及掌握其变化规律,不仅有利于促进区域经济可持续发展,而且对于城市生态文明建设具有重要的现实意义和参考价值。

键词：乌鲁木齐市；生态环境；驱动因子；遥感生态指数；地理探测器

随着城市化进程的不断加快，使得人口，资源和环境三者的矛盾越来越显著，甚至导致了很多生态环境问题[1]。生态环境质量反映了生态环境的优劣程度，使用遥感技术进行研究，不但从不同时空尺度对生态环境变化进行研究，而且全面客观分析生态环境质量变化[2-3]。实现生态环境保护和经济社会可持续发展具有重要意义。

地理信息技术和遥感技术的深人发展，遥感数据因其数据源广泛，数据量庞大，不受地域限制等优点,在生态监测与评价中得到广泛应用[4-6]。当前的城市扩展、生态监测以及在对城市、湿地、沙漠和河流等地理单元的生态系统进行评估时都用到了这些技术[7-9]。但大多生态系统评价的研究仅仅使用单一的生态环境指标[],例如：使用植被指数评价森林群落生长情况[1],利用水体指数评价湖泊生态环境水质状况[12],利用地表温度评价城市热岛效应[13]。遥感技术还应用在区域植被覆盖度动态变化[14]和城市不透水面等方面来评估城市生态环境质量[15]。事实上，生态系统的形成与发展受多种因素影响，所以单一的生态因子在一定程度上不能全面的反映自然过程的真实情况。因此，从多个生态因子的综合作用来研究生态环境评价是很重要的。2013年徐涵秋[提出了遥感生态指数(RSEI)，该指数不仅实现了定量化评价区域生态环境质量，还能够在时空尺度上对评价结果进行可视化表达[17]。

地理探测器模型可通过探测地理现象的空间分层异质性，揭示其背后的驱动因子，刻画自变量对因变量空间分布的解释能力[18]。同时，地理探测器模型还能够探测两两变量之间，多种类型，真实发生的交互作用方式和影响，而非仅限于计量经济学预先设定的乘性交互作用类型[19]。该方法不仅在社会、经济、文化传播等领域有着广泛的应用，而且在生态环境领域的应用也逐渐兴起[20]。新疆作为典型的干旱地区，生态环境脆弱，城市化过程中引起环境变化的同时，生态环境也会反作用于城市化的发展，因此，及时准确了解城镇化背景下生态环境时空动态变化特征显得尤为重要。目前，已有大量研究分析探寻城市化与生态环境之间的关系[21]，然而基于遥感生态指数并利用多源数据从自然和人文角度选取代表性因子定量分析影响干旱区城市生态环境的驱动因子及因子间交互作用的研究较少。本文选取干旱区绿洲城市乌鲁木齐市为研究区，通过构建遥感生态指数模型，采用主成分分析、地理信息空间统计分析和地理探测器等方法，探究近 $2 0 \mathrm { a }$ 生态环境时空动态变化规律，厘清研究区生态环境质量主导因子的科学问题开展研究，进而为西北十旱区绿洲城市及其他区域生态环境质量评价的因子选择提供借鉴和参考依据。

# 1 研究区及数据源

# 1.1 研究区概况

乌鲁木齐市位于欧亚大陆腹地,地处 $8 6 ^ { \circ } 4 6 ^ { \prime } 1 0 ^ { \prime \prime } .$ ）$8 8 ^ { \circ } 5 9 ^ { \prime } 4 8 ^ { \prime \prime } \mathrm { E }$ $4 2 ^ { \circ } 5 4 ^ { \prime } 1 6 ^ { \prime } { \sim } 4 4 ^ { \circ } 5 8 ^ { \prime } 1 6 ^ { \prime } \mathrm { N }$ （图1)，土地面积为 $1 4 1 9 2 . 7 8 ~ \mathrm { k m } ^ { 2 }$ ，是我国西北地区重要的中心城市和面向中亚、西亚的国际商贸中心，全市常住人□ $3 . 5 1 \times 1 0 ^ { 6 }$ 人,2018年城镇化率为 $7 4 . 6 1 \% ^ { [ 2 2 ] }$ 。乌鲁木齐市山地面积占总面积的 $5 0 \%$ 以上，地势起伏大，南部、东北部高，中部和北部低。市区平均海拔$8 0 0 \mathrm { ~ m ~ }$ ,最高点天山博格达峰顶,海拔 $5 4 4 5 \mathrm { ~ m ~ }$ ，最低处在猛进水库的大渠南侧，海拔 $4 9 0 . 6 \mathrm { ~ m ~ }$ 。研究区属中温带大陆性干旱气候，常年干燥少雨，昼夜温差较大。

![](images/6ba78d151e97fee5b8e17637e54beccd92c3c23301ab6b78c9973ba0ddaef09f.jpg)  
图1研究区位置示意图  
Fig.1 Location map of the study area

# 1.2数据来源及处理

本研究获取的遥感数据和DEM数据来自地理空间数据云（http://www.gscloud.cn, $3 0 ~ \mathrm { m } \times 3 0 ~ \mathrm { m }$ ，选取研究区云量小于 $5 \%$ ，时间为2000年9月2日、2010年8月20日的Landsat5TM和2019年8月13日的Landsat8 OLI遥感影像数据(http://glovis.usgs.gov/)。在ENVI5.3软件中进行辐射定标和大气校正。其中2000年、2010年和2019年的土地利用遥感监测数据和人口空间分布公里网格数据集及2000年、2010年的GDP空间分布公里网格数据集(经济密度)都来源于中国科学院资源环境科学数据中心(http://www.resdc.cn/),空间分辨率均为 $1 \mathrm { k m } \times$ $1 \mathrm { k m }$ 。从中国经济社会大数据研究平台(http://data.cnki.net)的统计年鉴中获得2019年研究区总GDP数据，再结合2019年人口密度、土地利用类型和夜间灯光亮度数据采用多因子权重分配法将以行政区为统计单元的GDP数据空间化到栅格单元上[23-25]。根据分类标准对3期土地利用类型数据采用耕地、林地、草地、水域、建设用地和未利用地6个一级类型进行预处理[26]。2019年VIIRS卫星的夜间灯光数据来自于美国地质勘探局官网(http://glo-vis.usgs.gov/)。

# 2研究方法

# 2.1遥感生态指数

遥感生态指数RSEI(Remote Sensing Based Eco-logicalIndex)是徐涵秋[27]等学者从自然因素出发评价和监测城市生态环境而构建的新型遥感生态指数。该指数包含了植被覆盖度、湿度、温度、干度等4个自然因子，这些因子对人类生存有较大的影响，也是直接判断生态环境质量好坏的重要因素，因此RSEI可以综合体现研究区生态环境的质量[28]RSEI遥感生态指数函数表达式如下：

$\mathrm { R S E I } = \mathrm { f ( N D V I , W E T , L S T , N D B S I ) }$ (1)式中：NDVI是绿度指标;WET是湿度指标;LST是热度指标;NDBSI是建筑和裸土指标。

# （1）绿度指标

绿度指标可以直观反应研究区植被的生长情况与植被叶面积指数和生物量之间的关系。

$$
\mathrm { N D V I } { = } ( \mathrm { B } 4 - \mathrm { B } 3 ) / ( \mathrm { B } 4 + \mathrm { B } 3 )
$$

式中：B3和B4分别代表遥感数据的红外和近红外波段的反射率。

# (2）湿度指标

利用遥感缨帽变换来获取的湿度分量可以反应植被和土壤的湿度状况29，湿度指标是用WET来表示：

式中：B1\~B6分别代表遥感数据的蓝、绿、红、近红外、短波红外1和短波红外2波段的反射率。对于TM传感器C1\~C6分别为 $0 . 0 3 1 5 , 0 . 2 0 2 1 , 0 . 3 0 1 2$ $0 . 1 5 9 4 , - 0 . 6 8 0 6$ 和-0.6109；OLI传感器的C1\~C6分别为0.1511、0.1973、0.3283、0.3407、-0.7117和-$0 . 4 5 5 9 ^ { [ 3 0 ] }$

# （3）热度指标

代表热度指标的地表温度(LST)用经过比辐射率校正的温度来表示，利用Landsat数据中的热红外波段,计算亮度温度L入,并进行比辐射率ε校正。公式为：

$$
\mathrm { L } \lambda = \mathrm { g a i n } \times \mathrm { D N } + \mathrm { b i a s }
$$

$$
\mathrm { B ( T s ) } = \big [ \mathrm { L \lambda - L \ } \uparrow \ - \tau ( 1 - \varepsilon ) \mathrm { L \ } \downarrow \big ] / \tau \varepsilon
$$

式中：DN为像元灰度值;gain和bias分别为波段6的增益值与偏置值,可以从影像的头文件获得。B(Ts)为黑体辐射亮度;L↑和L」为大气向上和大气向下的辐射亮度； $\tau$ 为大气热红外波段的透过率； $\boldsymbol { \varepsilon }$ 为地表比辐射率，其取值见参考文献[31」。经过公式(5)计算的温度需要进行比辐射率纠正才能作为地表温度LST：

$$
\mathrm { L S T } = K 2 / \ln [ \frac { K 1 } { \mathrm { B ( T s ) } } + 1 ]
$$

式中：对于Landsat5影像, $K 1 = 6 0 7 . 7 6$ $K 2 \mathrm { = } 1 2 6 0 . 5 6$ 对于Landsat7影像， $K 1 = 6 6 6 . 0 9$ $K 2 \mathrm { = } 1 2 8 2 . 7 1$ ；对于 Landsat8影像， $K 1 = 7 7 4 . 8 9 , K 2 = 1 2 0 1 . 1 4$ □

# (4）干度指标

造成城市区域“干化"的主要原因是建筑用地的扩展以及大面积的裸地，为此选用裸地指数(SI)和建筑指数(IBI)合成作为干度指标,表示为(NDBSI)[30]。

$$
\mathrm { N D B S I } = ( \mathrm { I B I } + \mathrm { S I } ) / 2
$$

$$
\begin{array} { r } { \mathrm { I B I } = \{ \frac { 2 \mathrm { B } 5 } { \mathrm { B } 5 + \mathrm { B } 4 } - [ \frac { \mathrm { B } 4 } { \mathrm { B } 4 + \mathrm { B } 3 } + \frac { \mathrm { B } 2 } { \mathrm { B } 2 + \mathrm { B } 5 } ] \} \Bigg / } \\ { \{ \frac { 2 \mathrm { B } 5 } { \mathrm { B } 5 + \mathrm { B } 4 } + [ ( \frac { \mathrm { B } 4 } { \mathrm { B } 4 + \mathrm { B } 3 } + \frac { \mathrm { B } 2 } { \mathrm { B } 2 + \mathrm { B } 5 } ] \} \Bigg . } \end{array}
$$

$$
\mathrm { S I } = \big [ \big ( \mathrm { B } 5 + \mathrm { B } 3 \big ) - \big ( \mathrm { B } 4 + \mathrm { B } 1 \big ) \big ] \big / [ \big ( \mathrm { B } 5 + \mathrm { B } 3 \big ) + \big ( \mathrm { B } 4 + \mathrm { B } 1 \big ) ]
$$

（5）主成分分析

主成分分析(PCA)是多波段遥感图像变换增强常用的方法之一[32],是通过对所选取的多个指标进行主成分分析，以达到从这些指标中选用重要的且相对独立的综合指标来进行生态环境评价。

(6）遥感生态指数构建

本研究采用主成分分析方法来计算4个指标，即遥感生态指数由上述4个指标的第一主成分(PC1)所组成。由于以上指标数值范围不同，需要将4个指标归一化，具体公式如下：

$$
\mathrm { R S E I } = ( \mathrm { R S E I } _ { 0 } - \mathrm { R S E I } _ { 0 - \mathrm { m i n } } ) / ( \mathrm { R S E I } _ { 0 - \mathrm { m a x } } - \mathrm { R S E I } _ { 0 - \mathrm { m i n } } )
$$

公式中：RSEI为遥感生态指数，是4个指数归一化后转换为的主要成分。 $\mathrm { R S E I _ { 0 } }$ 为遥感生态指数初始值 $\mathrm { \Delta R S E I _ { 0 } { = } 1 { - } P C 1 } _ { , }$ ）。 $\mathrm { R S E I _ { \mathrm { 0 - m a x } } }$ 和 $\mathrm { R S E I _ { 0 - m i n } }$ 为初始值RSEI的最大值和最小值。遥感生态指数越接近1表明生态环境质量越好，越接近0表明生态环境质量越差。

# 2.2地理探测器模型

地理探测器是一种探测空间分异性揭示其背后驱动因子的统计学方法[18]。该模型主要是通过分析地理空间的各类型之间整体差异性来定量探测自变量对因变量的影响程度，该模型提出后在社会经济和生态环境领域得到了广泛的应用[33-35]。模型由4个探测器组成：因子探测器、交互探测器、风险探测器和生态探测器，本文使用因子探测器和交互探测器来分析驱动因子对生态环境的影响程度。

# （1）因子探测

因子探测主要用于识别造成空间分异性的驱动因子，公式如下：

$$
q = 1 - \frac { 1 } { N \sigma ^ { 2 } } \sum _ { h = 1 } ^ { L } N _ { h } \sigma _ { h } ^ { 2 }
$$

式中： $q$ 为影响因素对遥感生态指数的影响力，即解释力强度； $h { = } 1 , \cdots , L ; L$ 为因变量RSEI和自变量因子的分级或分类数； $N _ { h }$ 和 $N$ 分别为不同分级的区域和全区域内的样本数； $\sigma _ { h } ^ { 2 }$ 和 $\scriptstyle { \dot { \sigma } } ^ { 2 }$ 分别为不同分级的区域和全区域内RSEI的方差。 $q$ 的取值为 $[ 0 , 1 ] , q$ 值越大表明因子对遥感生态指数的影响越大。

(2）交互探测

交互探测器能够探测出不同影响因素对因变量的交互作用。2个因子相互作用后会出现5种情况,分别是：若 $\mathrm { P ( A \cap B ) } { \ < } \mathrm { m i n } \big [ \mathrm { P ( A ) } , \mathrm { P ( B ) } \big ]$ ,则因子A和B交互作用后影响作用非线性减弱；若 $\operatorname* { m i n } [ \mathrm { P ( A ) } , \mathrm { P }$ (B) $\scriptstyle \exists < \mathrm { P ( A \cap B ) } < \operatorname* { m a x } \left[ \mathrm { P ( A ) } , \mathrm { P ( B ) } \right]$ ,则单线性减弱；若P$\mathrm { ( A \cap B ) { > } m a x \big [ P ( A ) , P ( B ) \big ] }$ 或者 $\mathrm { P ( A \cap B ) { < } P ( A ) { + } P ( B ) }$ ，则双因子增强;若 $\mathrm { P ( A \cap B ) { > } P ( A ) { + } P ( B ) }$ ,则非线性增强；若$\mathrm { P ( A \cap B ) { = } P ( A ) { + } P ( B ) }$ ,则相互独立。

# 3 结果与分析

# 3.1生态环境指标主成分分析

由表1可以看出，2000年，2010年和2019年生态环境指标第一主成分的特征值分别为0.1475，0.0629，0.0622，特征值贡献率分别为 $8 2 . 6 9 \%$ ，$8 9 . 0 2 \%$ $8 8 . 7 1 \%$ ,3期影像的PC1的贡献率都超过了$8 0 \%$ ，说明PC1中包含了4个指标的大部分信息。

由表2可以看出，2000年，2010年和2019年研究区RSEI指数的平均值在近20a间变化幅度不大，分别为0.21，0.21和0.23呈现出增加的趋势。4个生态指标的变化趋势显示，3期绿度指标和湿度指标的均值都呈现出从2000—2010年略有减少，而2019年有增加的趋势。热度指标在前10a微增，而后$1 0 \mathrm { a }$ 有减少的特征。干度指标前10a基本保持不变而后 $1 0 \mathrm { a }$ 有减少的趋势。从各指标的均值来看绿度指标和热度指标的变化幅度比较大，说明这2个指标是乌鲁木齐市RSEI变化的主要影响因素。总体上乌鲁木齐市近20a的生态环境有所改善。

# 3.2RSEI时空变化分析

根据《生态环境评价技术规范》中的生态环境分级标准[3]，将遥感生态指数按照0.2的间隔划分为5个等级，生态差(0\~0.2）、生态较差(0.2\~0.4）、生态一般(0.4\~0.6）、生态良(0.6\~0.8)和生态优 $( 0 . 8 \sim$ 1.0)得到RSEI的空间分布(图2)，并分级统计得到图3。

从生态环境遥感指数的空间分布来看(图2)，环境质量等级较低区域主要集中在东北（达返城区)和西南(乌鲁木齐县)海拔较高的地区。2000—2010年的10a间生态环境质量有所下降，但2010—2019年生态环境质量有所改善。由图3可知，近20a间研究区不同生态环境质量等级所占面积的变化差异明显。其中，生态环境指数等级差和较差的区域所占总面积的百分比从2000—2010年分别增加到 $2 . 8 6 \%$ 和 $1 3 . 3 8 \%$ ，而到2019年这2个等级的面积百分比反而分别下降到 $0 . 1 9 \%$ 和 $3 . 6 9 \%$ 。生态环境指数等级为一般的区域所占总面积百分比变化差异不大，近20a间略有下降。生态环境指数等级为良的区域所占总面积百分比从2000年的 $7 5 . 9 1 \%$ 逐渐减少到2010年的 $6 4 . 0 9 \%$ ，而2019年又逐渐增加到 $7 5 . 2 8 \%$ 。生态环境指数优的区域在近20a里呈现逐渐增加的趋势。20a间生态环境指数一般和良的区域占总面积的百分比呈现先增加后减少的趋势，这2个等级的面积超过总面积的 $8 5 \%$ 。

表1遥感生态指数的主成分分析  
Tab.1 Principal component analysis of remote sensing ecological index   
表2乌鲁木齐市各年份指标和RSEI的变化  

<html><body><table><tr><td rowspan="2">主成分</td><td colspan="2">2000年</td><td colspan="2">2010年</td><td colspan="2">2019年</td></tr><tr><td>特征值</td><td>贡献率/%</td><td>特征值</td><td>贡献率/%</td><td>特征值</td><td>贡献率/%</td></tr><tr><td>PC1</td><td>0.1475</td><td>82.69</td><td>0.0629</td><td>89.02</td><td>0.0622</td><td>88.71</td></tr><tr><td>PC2</td><td>0.0276</td><td>11.68</td><td>0.0062</td><td>7.89</td><td>0.0057</td><td>5.47</td></tr><tr><td>PC3</td><td>0.0025</td><td>4.56</td><td>0.0013</td><td>2.61</td><td>0.0032</td><td>4.43</td></tr><tr><td>PC4</td><td>0.0008</td><td>1.13</td><td>0.0002</td><td>0.48</td><td>0.0004</td><td>1.13</td></tr></table></body></html>

Tab.2 Change of 4 indicators and RSEI in each year in Urumqi City   

<html><body><table><tr><td>年份</td><td>统计值</td><td>NDVI</td><td>WET</td><td>LST</td><td>NDBSI</td><td>RSEI</td></tr><tr><td rowspan="4">2000</td><td>最小值</td><td>-1.00</td><td>-0.02</td><td>-20.78</td><td>-0.90</td><td>0.00</td></tr><tr><td>最大值</td><td>1.00</td><td>0.02</td><td>63.64</td><td>0.37</td><td>1.00</td></tr><tr><td>均值</td><td>-0.02</td><td>0.01</td><td>8.93</td><td>0.02</td><td>0.21</td></tr><tr><td>标准差</td><td>0.06</td><td>0.00</td><td>13.86</td><td>0.09</td><td>0.30</td></tr><tr><td rowspan="4">2010</td><td>最小值</td><td>-0.76</td><td>-0.03</td><td>-18.48</td><td>-0.82</td><td>0.00</td></tr><tr><td>最大值</td><td>0.52</td><td>0.02</td><td>54.31</td><td>0.50</td><td>1.00</td></tr><tr><td>均值</td><td>-0.03</td><td>0.00</td><td>10.07</td><td>0.02</td><td>0.21</td></tr><tr><td>标准差</td><td>0.10</td><td>0.00</td><td>17.25</td><td>0.07</td><td>0.32</td></tr><tr><td rowspan="4">2019</td><td>最小值</td><td>-1.00</td><td>-0.03</td><td>-16.21</td><td>-0.81</td><td>0.00</td></tr><tr><td>最大值</td><td>0.60</td><td>0.02</td><td>54.24</td><td>0.72</td><td>1.00</td></tr><tr><td>均值</td><td>0.03</td><td>0.01</td><td>8.87</td><td>-0.11</td><td>0.23</td></tr><tr><td>标准差</td><td>0.06</td><td>0.09</td><td>15.20</td><td>0.18</td><td>0.33</td></tr></table></body></html>

![](images/7e55cd26cf4b85a566ed8492cadf1d6fe6f105c377ec76ce7b58b5b883b5f86d.jpg)  
Fig.2Spatial distribution remote sensing ecological index value classes in Urumqi City

![](images/8dd751534f7224e41b0576e8830b1700b4b33a4f02b53d434496ff9f44929ee2.jpg)  
图2乌鲁木齐市遥感生态指数的等级分布

为了进一步分析研究区在近30a中生态环境等级变化的程度，本文依据研究区实际情况并参考相关文献3用指数分级法将生态环境指数等级变化分为5类间隔为0.3，分别为恶化（RSEI指数值 $<$ $- 0 . 6 )$ ，变差 $_ { ( - 0 . 3 < \mathrm { R S E I } }$ 指数值 $< - 0 . 6 )$ ，不变（ $0 <$ RSEI指数值 $< - 0 . 3$ )，变好（ $( 0 . 3 { < } \mathrm { R S E I }$ 指数值 $_ { < 0 }$ )和优化（RSEI指数值 ${ > } 0 . 3 { \AA }$ 。由图4和表3可知，2000—2010年期间，生态环境质量变坏的面积占总面积的比例为 $1 . 1 4 \%$ ，生态变好的面积占总面积的比为

![](images/f1da263bc4b047277e19669b7525fc85b1ccd3cc8a7132ecb1fbb1eca1d42b58.jpg)  
图3各年份生态等级和面积比例统计 Fig.3 Statistical chart of ecological grades and area rations in each years   
图42000—2019年乌鲁木齐市RSEI变化监测  
Fig.4Change detection diagram of RSEI in Urumqi City from 20o0 to 2019

表32000—2019年乌鲁木齐市RSEI等级变化监测  
Tab.3Detection of the change of RSEIlevel in Urumqi City from 2ooO to 2019   

<html><body><table><tr><td rowspan="2">变化</td><td colspan="2">2000- -2010年</td><td colspan="2">2010- -2019年</td><td colspan="2">2000—2019年</td></tr><tr><td>面积/km²</td><td>占比/%</td><td>面积/km²</td><td>占比/%</td><td>面积/km²</td><td>占比/%</td></tr><tr><td>恶化</td><td>0.001</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0</td><td>0.00</td></tr><tr><td>变差</td><td>156.37</td><td>1.14</td><td>1104.65</td><td>8.03</td><td>56.91</td><td>0.41</td></tr><tr><td>不变</td><td>9058.09</td><td>65.75</td><td>7184.73</td><td>52.21</td><td>10621</td><td>77.10</td></tr><tr><td>变好</td><td>4435.82</td><td>32.20</td><td>5470.91</td><td>39.76</td><td>3097.87</td><td>22.49</td></tr><tr><td>优化</td><td>125.88</td><td>0.91</td><td>0.02</td><td>0.00</td><td>0.37</td><td>0.00</td></tr></table></body></html>

$3 2 . 2 0 \%$ ，说明生态环境质量变好的面积大于变坏的面积。2010—2019年期间生态环境质量变好的面积占总面积比例为 $3 9 . 7 6 \%$ ，变坏的面积占总面积的比例为 $8 . 0 3 \%$ 。近10a虽然生态环境质量变差的面积比例有所增加，但生态环境质量变好的面积比例增幅更大。从2000—2019年的20a间生态环境质量变好的面积占研究区总面积的百分比为 $2 2 . 4 9 \%$ .而变坏的面积占总面积的比例为 $0 . 4 1 \%$ 。说明整体上乌鲁木齐市近20a的生态环境质量是变好的趋势。

# 3.3生态环境质量影响因素探测分析

3.3.1单因子探测分析本研究用遥感生态环境指数作因变量，将研究区人口密度、土地利用类型、海拔高度、经济密度、绿度指标、湿度指标、热度指标和干度指标这8个因子作为自变量(图5)，由于因变量，自变量来源不同，导致分辨率，几何特征存在一定差异，建模之前必须进行数据整合，数据整合必须依靠空间单元。地理探测器常用的空间统计单元是格网。因此本研究采用自然断点法对自变量进行分级，并创建研究区范围内 $3 \ \mathrm { k m } \times 3 \ \mathrm { k m }$ 的格网，获取格网中心点作为样本点，共计1595个。然后再分别提取不同年份不同格网内因变量和自变量的值进行因子探测，得出各因子对生态环境质量的影响程度，表4为地理探测器的统计结果。

因子探测结果表明，所有探测因子的 $P$ 值均为0,表明所选的探测因子对RSEI的空间分异特征有显著影响,可作为影响因素对其分异性进行分析。 $q$ 值表示对RSEI的影响强度，也是对空间分异特征的解释力。2000年的解释力依次为：热度指标 $\mathrm { > }$ 湿度指标 $\mathrm { > }$ 经济密度 $\mathrm { \dot { > } }$ 干度指标>土地利用 $\mathrm { \dot { > } }$ 海拔 $>$ 绿度指标>人口密度。其中热度指标和湿度指标 $q { > } 0 . 5$ ，是2000年研究区遥感生态环境指数的主导因子；2010年的解释力依次为：热度指标 $>$ 干度指标 $>$ 绿度指标>海拔 $>$ 经济密度 $\mathrm { > }$ 湿度指标>土地利用 $>$ 人口密度。其中，热度指标( $\scriptstyle ( - 0 . 7 0 6 )$ 是2010年遥感生态环境指数的主导因子；2019年的解释力依次为：热度指标>海拔 $\mathrm { > }$ 湿度指标 $\mathrm { > }$ 人口密度 $\mathrm { \dot { > } }$ 绿度指标 $>$ 土地利用>经济密度 $>$ 干度指标。其中，热度指标( $\scriptstyle { \begin{array} { l } { q = } \\ { } \end{array} }$ 0.653)依然是影响生态环境质量指数的主导因子。综上所述，近20a来研究区的热度指标一直是生态环境指数的主导因子，其他因素对研究区生态环境指标的影响程度有所差异。

3.3.2多因子探测分析地理探测器属于非线性模型，本质上不存在多重共线性问题，不同自变量对模型结果的影响是独立的，两两自变量之间的交互作用计算出地理探测器模型的一个亮点[18]。为了进一步分析任意2个影响因子共同作用后对生态环境指数空间分布的解释程度，对各因子进行交互探测。交互探测一般包括5种情况，分别是：非线性减弱、单因子非线性减弱、双因子增强、独立、非线性增强。研究的探测结果如图6所示。

分别将乌鲁木齐市2000年、2010年和2019年生态环境指数与8个因子进行交互探测共产生28项交互作用结果。相比单因子，双因子的交互作用增强了对生态环境指数的解释力。本研究因子交互探测的结果表现出双因子增强型和非线性增强型的作用效果，不存在独立及减弱的关系，表明交互结果的决定力高于原有2个因子独立决定力，更能促进乌鲁木齐市的生态环境质量的变化。2000年和2019年双因子增强有16项，非线性增强有12项。2010年双因子增强有22项，非线性增强有6项。从图6可以看出，2000年和2010年对RSEI的影响最强的是LSTONDVI的交互作用，具体解释力的值分别为 $\scriptstyle q = 0 . 9 6 0$ 和 $\scriptstyle q = 0 . 7 5 7$ 。此外也可以看出，热度指标和其他指标因子之间的交互探测值都很高。2019年LST∩WET的交互作用对RSEI的影响

![](images/610e3835f686ed5ed9ab1b5d71987cc2450fec499848d7427047af7140a5a9e0.jpg)  
图5探测因子空间分布  
Fig.5 Risk detection and interactive detection matrix

# 表4单因子探测结果

Tab.4 Theresultsof single detection   

<html><body><table><tr><td rowspan="2">探测因子</td><td colspan="3">2000年</td><td colspan="3">2010年</td><td colspan="3">2019年</td></tr><tr><td>q值</td><td>P值</td><td>q排序</td><td>q值</td><td>P值</td><td>q排序</td><td>q值</td><td>P值</td><td>q排序</td></tr><tr><td>绿度指标</td><td>0.179</td><td>0</td><td>7</td><td>0.349</td><td>0</td><td>3</td><td>0.095</td><td>0</td><td>5</td></tr><tr><td>湿度指标</td><td>0.526</td><td>0</td><td>2</td><td>0.168</td><td>0</td><td>6</td><td>0.326</td><td>0</td><td>3</td></tr><tr><td>热度指标</td><td>0.857</td><td>0</td><td>1</td><td>0.706</td><td>0</td><td>1</td><td>0.653</td><td>0</td><td>1</td></tr><tr><td>干度指标</td><td>0.252</td><td>0</td><td>4</td><td>0.368</td><td>0</td><td>2</td><td>0.046</td><td>0</td><td>8</td></tr><tr><td>人口密度</td><td>0.07</td><td>1</td><td>8</td><td>0.067</td><td>0</td><td>8</td><td>0.166</td><td>0</td><td>4</td></tr><tr><td>土地利用</td><td>0.235</td><td>0</td><td>5</td><td>0.077</td><td>0</td><td>7</td><td>0.091</td><td>0</td><td>6</td></tr><tr><td>海拔</td><td>0.2</td><td>0</td><td>6</td><td>0.345</td><td>0</td><td>4</td><td>0.52</td><td>0</td><td>2</td></tr><tr><td>经济密度</td><td>0.263</td><td>0</td><td>3</td><td>0.199</td><td>0</td><td>5</td><td>0.072</td><td>0</td><td>7</td></tr></table></body></html>

最强，其中，热度指标和海拔分别与其他因子的交互作用的解释力值较高。

满足于 $q ( X 1 \cap X 2 ) > q ( X 1 ) + q ( X 2 )$ 的称为非线性增强。说明双因子交互结果 $q$ 对乌鲁木齐市的生态环境质量变化的影响大于2个单因子的影响力。

2000年非线性增强的因子作用按解释力值的大小排序为：人口密度NWET( $\scriptstyle q = 0 . 6 5 4 )$ 、NDVI∩NDBSI（ $\scriptstyle { \dot { q = 0 . 6 0 4 } } )$ 、人口密度ONDBSI $\scriptstyle { ( q = 0 . 4 8 2 ) }$ 、人口密度门经济密度( $\scriptstyle { \overline { { q ^ { = } 0 . 4 1 6 } } } )$ 、人口密度∩NDVI $\scriptstyle q = 0 . 3 6 9$ ）人口密度门土地利用( $\scriptstyle q = 0 . 3 3 6 { \mathrm { , } }$ )等；2010年非线性增强

0.960 (a)2000年 0.269 X8 0.2 0.576\* X7 0.804 0.235 0.422+ 0.512\*+ X6 0.7 0.336° 0.287° 0.416\* X5 0.647 0.2520.482\* 0.581\*+ 0.477\*+ 0.513+ X4 0.491 0.857 0.8820.874 0.901 0.888 0.907 X3 0.526 0.89 0.54 0.654\*0.664 0.666 0.67 X2 0.334 0.179 0.627 0.96 0.604\*0.369\* 0.369+ 0.5°+ 0.395 X1 0.178 X 双 8 4 5 8 X 8 0.758 (b)2010年 0.205 X8 0.345 0.458 X7 0.620 0.077 0.409 0.336\* X6 0.481 0.067 0.159\*+ 0.447\* 0.259 X5 0.3680.489\* 0.425 0.63+ 0.527 X4 0.343 0.7060.744 0.741 0.737 0.745 0.75 X3 0.168 0.718 0.381 0.265\*0.238 0.438 0.346+ X2 0.204 0.3490.4590.757 0.485+ 0.43° 0.426 0.583+ 0.52 X1 0.0660 X 2 B 4 5 1 X 8 0.788 (c)2019年 0.069 X8 0.520.552 X7 0.640 0.091 0.5470.267\*+ X6 0.491 0.166 0.23 0.547 0.247\* X5 0.0460.248\* 0.186\*+ 0.5390.131\*+ X4 0.343 0.6530.663 0.666 0.665 0.675 0.681 X3 0.326 0.788 0.360.499\* 0.384 0.741 0.452\* X2 0.194 0.095 0.439\* 0.675 0.16\*+ 0.324\* 0.195\*+ 0.6 0.297\*+ X1 0.0460 X 双 B 4 8 X 8

注： $\mathbf { \varLambda }$ 表示绿度指标， $X 2$ 表示湿度指标， $X 3$ 表示热度指标， $X 4$ 表示干度指标，X5表示人口密度， $X 6$ 表示土地利用， $X 7$ 表示海拔高度，X8表示经济密度；\*表示非线性增强，无标记的是双因子增强， $^ +$ 表示没有显著性差异，无标记是显著性差异；颜色越深代表双因子增强对生态环境指数的解释力越强。

的因子作用按解释力值的大小排序为：人口密度门NDBSI( $\scriptstyle { q = 0 . 4 8 9 }$ ）、人口密度∩DEM( $\scriptstyle { \dot { q } } = 0 . 4 4 7 { \mathrm { , } }$ 和人口密度∩NDVI( $\scriptstyle q = 0 . 4 3 0 .$ );2019年非线性增强的因子作用按解释力值的大小排序为：人口密度∩WET( $\scriptstyle { \cdot } q =$ 0.499）、经济密度∩WET( $\scriptstyle q = 0 . 4 5 2 ,$ ）、NDVI∩WET( $\scriptstyle { \cdot } q =$ 0.439)和人口密度∩NDVI( $\scriptstyle { q = 0 . 3 2 4 } ,$ 等。结果表明单因子探测结果解释力最小的因子在进行交互探测后与其他探测因子共同作用下影响力增强的效果非常明显。

# 4讨论

# 4.1LST结果的验证

本文利用Landsat数据反演得到的研究区2000年、2010年和2019年 $3 0 \mathrm { ~ m ~ }$ 分辨率地表温度是热度指标，也是模型分析的关键因子，因此需要进行精度验证。而MODIS数据的地表温度产品（MOD11A2)已被证明可以准确评价区域尺度热岛效应的特征[38]。MOD11A2数据空间分辨率为 $1 \mathrm { k m }$ ，时间分辨率为8d，同一地方1d可以获得4次观测数据。通过筛选找到与本文反演结果时间一致，质量较好的 MOD11A2数据，并对数据进行预处理。MOD11A2数据的1个像元可以包含本文反演的地表温度的1111个像元，对这1111个地表温度的像元进行加权平均，将该加权平均值记为重新采样后分辨率为 $1 ~ \mathrm { k m }$ 像元的地表温度。按这样的方法分别将研究区3期地表温度数据重新采用后分别与对应的MOD11A2数据进行比较分析，验证结果如图7所示。可以看出，本文LST结果与MOD11A2产品具有较好的一致性，可以满足本研究精度要求。其中研究区2000年、2010年和2019年本文LST结果与MOD11A2产品拟合的 $R ^ { 2 }$ 分别为0.7、0.7和0.8，斜率接近1。

# 4.2非线性增强溢出值分析

为了更深人分析各探测因子间交互作用后对RSEI空间分异特征的影响程度，本文还进一步计算了交互作用后的解释力和单因子解释力之和的非线性增强溢出 $C$ 值，具体表达式如下[39]：

$$
C = q { \bigl ( } X 1 \cap X 2 { \bigr ) } - [ q ( X 1 ) + ( X 2 ) ]
$$

式中： $q ( X 1 \cap X 2 )$ 为2种因子交互作用后的解释力，$q ( X 1 ) + ( X 2 )$ 为对应2种单因子解释力之和。

本研究选择非线性增强组合影响模式，并按每年 $C$ 值的大小排序，对排序前 $3 0 \%$ 的探测因子组合进行分析，具体结果如表5所示。

从2000年的溢出 $C$ 值来看，绿度指标、人口密度和海拔高程，这3个因子在单因子探测中解释力是最小的，而与干度指标和人口经济等因子交互作用后，明显增强了对RSEI空间分异特征的解释力。

![](images/ee79604ec7fe3f7b8483d5167c6c695b10688196f486528336162802b202f64c.jpg)  
MOD11A2产品的比较   
Fig.7 Comparison ofLST results with MODIS surface temperature products in 20o0、2010 and 2019

尤其是绿度和人口在与干度指标交互作用后溢出值大于其他因子组合。2010年,单因子探测里解释力最小的土地利用和人口密度分别与人口经济，十度指标和湿度指标等因子交互作用后解释力增强;2019年，单因子解释力较低的干度指标，绿度指标和人口经济分别与人口密度交互作用后对RSEI空间分异特征的解释力增强了。这一结果表明,研究区近20a间人口影响(人口密度和人口经济），植被覆盖度和城市建设的影响是生态环境质量的重要因素，但其影响效果在单因子探测中表现不明显，只是在多因子的交互作用后，才体现出很强的解释力。这可能是由于人类活动和社会发展直接影响了土地类型的改变(包括城市建设用地扩展和植被覆盖度变化），从而间接的影响了生态环境质量。这一结论与宋慧敏等[40]的相关研究结论一致，同时也表明，在利用地理探测器来对因变量的影响驱动因子进行定量归因时，仅仅依据单因子探测的结果，可能具有一定的片面性和局限性，只有将单因子分析与多因子交互作用探测相互协同配合，才能更完全地揭示因变量的主要影响因素。因此，乌鲁木齐市在未来生态环境规划和管理中应该重视城市土地利用和植被覆盖对生态环境的影响,科学规划城市空间格局，确保生态环境良性发展。遥感生态指数在时空尺度上能够细化生态环境变化的研究，相比景观格局分析具有一定优势，本文利用研究区3期遥感生态指数对比分析揭示了研究区生态环境时空动态变化规律，进一步分析了影响生态环境的主导因子，以上结果和分析较好的回答了本文提出的科学问题,在此基础上本文还深入挖掘出城市生态环境好转的影响因素，对研究区生态环境质量修复和改善提供了优化思路和建议。

# 4.3地理探测器精度分析

地理探测器模型数据整合的空间统计单元（格网)大小不是固定的，统计单元大小不同对模型结果有一定影响，会产生尺度效应。所以有必要对模型输入不同大小的统计单元进行模拟，通过对结果的分析选择研究区最佳的格网尺寸[41]。为保证地理探测器结果的准确性，本文还尝试对8种因子采用了不同的分级标准，并充分探究不同空间统计单元大小对地理探测器模型结果产生的尺度效应。通过对研究区驱动因素的影响反复对比和分析发现：对不同因子用分位数算法和自然间断点法进行

# 表5探测因子组合

Tab.5 Combination of detection factors   

<html><body><table><tr><td>年份</td><td>交互因子</td><td>q(X1∩X2)</td><td>q(X1)+q(X2)</td><td>C</td><td>影响模式</td></tr><tr><td rowspan="4">2000</td><td>NDVIONDBSI</td><td>0.604</td><td>0.431</td><td>0.173</td><td>非线性增强</td></tr><tr><td>人口密度ONDBSI</td><td>0.482</td><td>0.322</td><td>0.160</td><td>非线性增强</td></tr><tr><td>人口密度ONDVI</td><td>0.369</td><td>0.249</td><td>0.120</td><td>非线性增强</td></tr><tr><td>DEMN经济密度</td><td>0.576</td><td>0.463</td><td>0.113</td><td>非线性增强</td></tr><tr><td rowspan="3">2010</td><td>土地利用经济密度</td><td>0.336</td><td>0.276</td><td>0.060</td><td>非线性增强</td></tr><tr><td>人口密度ONDBSI</td><td>0.489</td><td>0.435</td><td>0.054</td><td>非线性增强</td></tr><tr><td>人口密度NWET</td><td>0.265</td><td>0.235</td><td>0.030</td><td>非线性增强</td></tr><tr><td rowspan="5">2019</td><td>人口密度∩NDVI</td><td>0.430</td><td>0.416</td><td>0.014</td><td>非线性增强</td></tr><tr><td>人口密度ONDVI</td><td>0.324</td><td>0.261</td><td>0.063</td><td>非线性增强</td></tr><tr><td>人口密度ONDBSI</td><td>0.248</td><td>0.212</td><td>0.036</td><td>非线性增强</td></tr><tr><td>NDVI∩WET</td><td>0.439</td><td>0.421</td><td>0.018</td><td>非线性增强</td></tr><tr><td>人口密度经济密度</td><td>0.247</td><td>0.238</td><td>0.009</td><td>非线性增强</td></tr></table></body></html>

分级时，由于分位数算法可能会将不同要素以同等数量分到一个等级中，导致得到的结果往往具有不合理性。而自然间断分级法是基于数据的自然分组，对相似值进行最恰当地分组，并且可使不同类别间的差异最大化。所以本研究选择了较为合理的自然间断点法对因子进行分级。

通过分析发现，对于空间统计格网大小和格网密度的选择，主要根据研究区面积和因子数据的空间分辨率来选择相应合适大小的格网，在某种程度上空间统计格网越小结果会相对准确，但也会造成因数据量过大，降低模型运行的效率。本文在研究过程中分别选取了 $3 \mathrm { k m } \times 3 \mathrm { k m }$ 的空间统计格网1595个和 $4 ~ \mathrm { k m } \times 4 ~ \mathrm { k m }$ 空间统计格网932个分别进行地理探测器分析，结果表明：2种方法的主要影响因子没有改变，但在对该地区生态环境质量影响较小的影响因子的探测结果中出现了差异，说明格网越小、采样点越多地理探测器的精确度相对有所提高，说明本研究选择的 $3 \ \mathrm { k m } \times 3 \ \mathrm { k m }$ 的空间统计格网，共计1595个采样点进行地理探测器分析，既保证了模型结果的准确性，又兼顾了模型的运行效率。

# 5结论

本研究利用主成分分析法耦合了绿度、湿度、热度和干度指标构建了乌鲁木齐市近20a的遥感生态环境指数，在此基础上，进一步应用地理探测器模型的因子探测器与交互探测器，分别探测了单因子以及多因子交互作用对研究区遥感生态环境指数空间分异特征的解释力。具体结论如下：

（1）通过主成分分析表明，近20a乌鲁木齐市绿度指标和湿度指标对遥感生态指数起正相关的作用，而热度指标和干度指标起负相关作用。其中绿度和干度对该区域的影响比较大，生态质量的改善主要来源于植被覆盖的增加和干度指标的降低。

(2）研究区生态环境质量不好的面积占总面积的比例从2000年的 $3 . 5 \%$ 增加到2010年的 $1 6 . 2 4 \%$ ，再降低到2019年的 $3 . 8 \%$ ;环境质量好的面积占总面积的百分比从2000年的 $7 5 . 9 2 \%$ 降低到2010年的$6 4 . 3 9 \%$ ,2019年增加到了 $7 8 . 2 \%$ ；近 $2 0 \mathrm { a }$ 生态环境变差的面积远小于变好的面积，其中，变差的面积占总面积的 $0 . 4 1 \%$ ，而变好的面积占总面积的 $2 2 . 4 9 \%$ ，说明乌鲁木齐市近 $2 0 \mathrm { ~ a ~ }$ 生态环境质量呈现变好的趋势。

（3）从单因子探测结果来看，近20a热度指标对RSEI的空间分异特征解释力最强，是区域生态环境质量最主要的影响因素，其他因素在不同时段有不同的解释力程度；从多因子交互作用探测结果来看，在交互作用下所有因子都表现出协同增强的效果，LST在NDVI、WET、NDBSI、GDP、经济密度、人口密度和土地利用类型的共同作用下对RSEI空间分异特征解释力最强。在非线性增强中单因子影响最小的人口密度和十度指标在交互作用下成为影响生态环境质量的重要因素，说明满足一定的人口密度并与其他因子共同作用，可能会对生态环境质量产生显著的影响。

参考文献(References):   
[1]王东升,王小磊,雷泽勇.基于遥感生态指数的阜新市生态质量 评估[J].生态科学,2020,39(3): 88-94.[Wang Dongsheng,Wang Xiaolei,Lei Zeyong. Ecological change assessment of Fuxin based onremote sensing ecological index[J].Ecological Science,2020, 39(3): 88-94.]   
[2]杨江燕,吴田,潘肖燕,等.基于遥感生态指数的雄安新区生态 质量评估[J].应用生态学报,2019,30(1):277-284.[Yang Jiangyan, Wu Tian,Pan Xiaoyan, et al.Ecological quality assessment of Xiongan New Area based onremote sensing ecological index[J]. Chinese Journal of Applied Ecology,2019,30(1) : 277-284.]   
[3]宋媛,石惠春,谢敏慧,等.2000—2017年甘肃省生态环境质量 时空演变格局及其影响因素[J].生态学杂志,2019,38(12): 3800-3808.[Song Yuan,Shi Huichun,Xie Minhui,et al.Spatiotemporal evolution pattern and influencing factors of eco-environmental quality in Gansu from 20O0 to 2017[J]. Chinese Journal of Ecology,2019,38(12): 3800-3808.]   
[4]杨胜天,刘昌明,杨志峰,等.南水北调西线调水工程区的自然 生态环境评价[J].地理学报,2002,57(1):11-18.[Yang Shengtian,Liu Changming,Yang Zhifeng,et al.Natural Eco-environmental evaluation of west route area of interbasin water transfer project[J]. Acta Geographic Sinica,2002,57(1): 11-18.]   
[5]任志远,李晶.陕南秦巴山区植被生态功能的价值测评[J].地理 学报,2003,58(4): 503-511.[Ren Zhiyuan,Li Jing.The valuation of ecological services from the vegetation ecosystems in the Qinling-Daba mountains[J].Acta Geographic Sinica,2003,58(4): 503- 511. ]   
[6]李晓文,方精云,朴世龙.近10年来长江下游土地利用变化及 其生态环境效应[J].地理学报,2003,58(5):659-667.[Li Xiaowen,Fang Jingyun,Piao Shilong.Landuse changes and its implication to the ecological consequences in lower Yangze region[J]. Acta Geographic Sinica,2003,58(5): 659-667.]   
[7]阿里木江·卡斯木.人口密度、夜间光数据及MODIS 的全球城 市分类[J].遥感信息,2018,33(1): 86-92.[Alimujiang Kasimu. Global urban characterization using population density,DMSP data and MODIS data[J]. Remote Sensing Information,2018,33(1): 86-92.]   
[8]高炜,安如,王喆.基于微波遥感技术的干旱监测指数及其应用 研究——以三江源区为例[J].干旱区研究,2017,34(3):541- 550.[Gao Wei,An Ru, Wang Zhe.Drought index and its application based on microwave remote sensing technology:A case study in the Three-River Headwaters Region[J]. Arid Zone Research,2017, 34(3): 541-550.]   
[9]Sullivan C A,Skeffington MS,Gormally MJ,et al. The ecological status of grasslands on lowland farmlands in western Ireland and implications for grassland classification and nature value assessment[J].Biological Conservation,2010,143:1529-1539.   
[10]Li Wangming,Wang Jianzheng,Ge Dandong.Analysis of ecological carrying capacity change and driving factors at urban fringe: A case of Hangzhou City[J]. Journal of Zhejiang University(Engineering Science),2008,42(1): 39-43.   
[11]Ochoa-Gaona S, Kampichler C,de Jong BHJ,et al. Amulti-criterion index for the evaluation of local tropical forest conditions in Mexico[J].Forest Ecology Management,2010,260: 618- 627.   
[12] 阿布都米吉提·阿布力克木,阿里木江·卡斯木,艾里西尔·库尔 班,等.近40年台特玛-康拉克湖泊群水域变化遥感监测[J].湖 泊科学,2014,26(1): 46-54.[Ablekim Abdimijit, Kasimu Alimujiang,Kurban Alishir,etal.Monitoringthe water area changes in Tetima-Kanglayka lakes region over the past four decades by remotely sensed data[J]. Journal of Lake Sciences,2014,26(1): 46- 54.]   
[13] 张瑞钢,莫兴国,林忠辉.滹沱河上游山区近50年蒸散变化及 主要影响因子分析[J].地理科学,2012,32(5):628-634.[Zhang Ruigang,Mo Xingguo,Lin Zhonghui. The trend and the principal influence factors of evapotranspiration in Hutuo River Basin during last 50 years[J]. Scientia Geographica Sinica, 2012,32(5): 628-634.]   
[14] 李佩武,李贵才,陈莉,等.深圳市植被径流调节及其生态效益 分析[J].自然资源学报,2009,24(7):1223-1233.[Li Peiwu,Li Guicai, Chen Li,et al.Analysis of Shenzhen's vegetation: Flood controlandecologicalbenefit[J].Journalof NaturalResources, 2009,24(7): 1223-1233.]   
[15] 崔秋洋,潘云,杨雪.基于Landsat 8遥感影像的北京市平原区 不透水层盖度估算[J]).首都师范大学学报(自然科学版),2015, 36(2): 89-92.[Cui Qiuyang,Pan Yun, Yang Xue. Estimation of the impermeable layer coverage in the plain area of Beijing based on Landsat 8 remote sensing image[J]. Journal of Capital Normal University(Natural Science Edition),2015,36(2): 89-92.]   
[16] 徐涵秋.区域生态环境变化的遥感评价指数[J].中国环境科学, 2013,33(5): 889-897.[Xu Hanqiu.A remote sensing index for assessment of regional ecological changes[J]. China Environmental Science,2013,33(5): 889-897.]   
[17] 张亚球,姜放,纪梦达,等.基于遥感指数的区县级生态环境评 价[J].干旱区研究,2020,37(6):1598-1605.[Zhang Yaqiu,Jiang Fang,Ji Mengda,et al.Assessment of the ecological environment at district and county level based on remote sensing index [J].Arid Zone Research, 2020,37(6): 1598-1605.]   
[18] 王劲峰,徐成东.地理探测器:原理与展望[J].地理学报,2017, 72(1):116-134.[Wang Jinfeng,Xu Chengdong.Geodetector: Principle and prospective[J].Acta Geographic Sinica,2017,72(1): 116-134.]   
[19] 郭泽呈,魏伟,庞素菲,等.基于 SPCA 和遥感指数的干旱内陆 河流域生态脆弱性时空演变及动因分析——以石羊河流域为 例[J].生态学报,2019,39(7):2558-2572.[Guo Zecheng，Wei Wei,Pang Sufei,et al. Spatio-temporal evolutionand motivation analysis of ecological vulnerability in Arid Inland River Basin based on SPCA and remote sensing index: A case study on the Shiyang River Basin[J].Acta Ecologica Sinica,2019,39(7):2558- 2572.]   
[20] 文广超,赵梅娟,谢洪波,等.伊犁河谷西部土地植被覆盖演化 及驱动力分析[J].干旱区研究,2021,38(3):843-854.[Wan Guangchao, Zhao Meijuan,Xie Hongbo,et al.Analysis of land vegetation cover evolution and driving forces in the western part of the li River Valley[J]. Arid Zone Research,2021,38(3): 843-854.]   
[21] 张亚如,张军民.城镇化与经济发展的时空相互作用机制研究 以新疆为例[J].干旱区地理,2020,43(3):839-848.[Zhang Yaru, Zhang Junmin.Spatio-temporal interaction mechanism of urbanization and economic development: A case of Xinjiang[J]. Arid Land Geography,2020,43(3): 839-848.]   
[22] 李世海.乌鲁木齐市大气环境质量现状及对策[J].区域治理, 2019(24): 54-57.[Li Shihai. Present situation and countermeasure of atmospheric environment quality in Urumqi[J]. Regional Governance,2019(24): 54-57.]   
[23] 魏伟,颉耀文,魏晓旭,等.基于CLUE-S模型和生态安全格局 的石羊河流域土地利用优化配置[J].武汉大学学报(信息科学 版),2017,42(9): 1306-1315.[Wei Wei,Xie Yaowen,Wei Xiaoxu, et al.Land use optimization based on CLUE-S model and ecological security scenario in Shiyang river basin[J]. Geomatics and Information Science of Wuhan University,2017,42(9):1306-1315.]   
[24]Liu H, Jiang D, Yang X,et al. Spatialization approach to 1 km grid GDP supported by remote sensing[J]. Geo-Information Science, 2005, 7(2): 120-123.   
[25] 易玲,熊利亚,杨小唤.基于GIS 技术的GDP空间化处理方法 [J].甘肃科学学报,2006,18(2): 54-58.[Yi Ling,Xiong Liya, Yang Xiaohuan.Method of Pixelizing GDP data based on the GIS [J]. Journal of Gansu Sciences,2006,18(2): 54-58.]   
[26] 王志杰,苏姬.南水北调中线汉中市水源地生态脆弱性评价与 特征分析[J].生态学报,2018,38(2):432-442.[Wang Zhijie,Su Yuan.Analysis of eco-environmental vulnerability characteristics of Hanzhong City,near the water source midway along the route of the south-to-north water transfer project, China[J].Acta Ecologica Sinica,2018,38(2): 432-442.]   
[27] 徐涵秋.城市遥感生态指数的创建及其应用[J].生态学报, 2013,33(24): 7853-7862. [Xu Hanqiu. A remote sensing urban ecological indexand itsapplication[J].Acta Ecologica Sinica, 2013,33(24): 7853-7862.]   
[28] 王丽春,焦黎,来风兵,等.基于遥感生态指数的新疆玛纳斯湖 湿地生态变化评价[J].生态学报,2019,39(8):2963-2972. [Wang Lichun,Jiao Li,Lai Fengbin,etal.Evaluation of ecological changes based on a remote sensing ecological index in a Manas Lakewetland,Xinjiang[J].Acta Ecologica Sinica,2O19,39(8): 2963-2972.]   
[29]Huang C,WylieB, Yang L,etal. Derivationof a tasselle cap transformation based on Landsat 7 at satelite reflectance[J]. International Journal of Remote Sensing,2002, 23(6): 1741-1748.   
[30] 徐涵秋.水土流失区生态变化的遥感评估[J].农业工程学报, 2013,29(7): 91-97,294. [Xu Hanqiu. Remote sensing assessment of ecological changes in soil and water loss areas[J]. Transactions of the Chinese Society of Agricultural Engineering,2Ol3,29(7): 91-97,294.]   
[31]Nichol J. Remote sensing of urban heat islands by day and night [J]. Photogrammetric Engineering and Remote Sensing, 2005,71 (6): 613- 621.   
[32] 蒋博文.基于PCA变换的多光谱图像降维方法研究[J].信息技 术,2012,36(8): 98-101.[Jiang Bowen.Method of multi-spectral images reduce-dimensions based on PCA[J]. Information Technology,2012,36(8): 98-101.]   
[33] 王静,姚顺波,刘天军.退耕还林(草)工程实施以来降水利用效 率演变格局及归因——以宝鸡地区为例[J].干旱区研究, 2020,37(5):1233-1245.[Wang Jing,Yao Shunbo,Liu Tianjun. The evolution pattern and atribution of rainfall use efficiency since the implementation of the project of returning farmland to forest (grass): A case study in Baoji[J].Arid Zone Research,2020, 37(5): 1233-1245.]   
[34] 朱增云,阿里木江·卡斯木.基于地理探测器的伊犁谷地生境质 量时空演变及其影响因素[J].生态学杂志,2020,39(10):3408- 3420.[Zhu Zengyun,Alimujiang Kasimu. Spatial-temporal evolution of habital qualityin Yili Valley basedongeographical detectorsand its influencing factors[J]. Chinese Journal of Ecology, 2020,39(10): 3408-3420.]   
[35] 高鹏文,阿里木江·卡斯木,图尔荪阿依·如孜,等.哈密市生态 环境效益时空分析[J].干旱区研究,2020,37(4):1057-1067. [Gao Pengwen,Alimujiang Kasimu, Tursunayi Ruzi, et al. Temporal and spatial analysis of ecological environment improvement in Hami City[J]. Arid Zone Research,2020,37(4): 1057-1067.]   
[36] 杨保华,杨清华,陈剑虹.关于《生态环境状况评价技术规范(试 行)》中土地退化指数的权重及计算方法的探讨[J].生态与农村 环境学报,2011,27(3):103-107.[Yang Baohua, Yang Qinghua, Chen Jianhong.Weight of land (soil) degradation indeces and optimization of their calculation in“echnical criteria or evaluation of ecological environment (Trial)”[J] Journal of Ecology and Rural environment,2011,27(3): 103-107.]   
[37] 蔡贤,杜晓初.基于遥感生态指数的鄂州市生态环境质量评估 [J].湖北大学学报(自然科学版),2020,42(3):233-239,246. [Cai Xian,Du Xiaochu. Eco-environment quality assessment of Ezhou City based on RSEI[J].Journal of Hubei University (Natural Science Edition),2020,42(3): 233-239,246.]   
[38] 孙灏,马立茹,蔡创创,等.干旱区地表温度和热岛效应演变研 究——以宁夏沿黄城市带为例[J].干旱区地理,2020,43(3): 694-705.[Sun Hao,Ma Liru, Cai Chuangchuang,et al. Evolution of surface temperature and heat island effect in arid areas: A case of city belt along the Yellow River in Ningxia[J].Arid Land Geography,2020,43(3): 694-705.]   
[39] 高焕霖,张廷龙,樊华烨,等.基于地理探测器的杨凌示范区生 态环境质量影响因素定量分析[J].西北林学院学报,2020,35 (5):185-194.[Gao Huanlin,Zhang Tinglong,Fan Huaye,et al. Quantitative analysis of the factors affecting ecological environ

ment quality in Yangling demonstration zone based on geograohical detector[J]. Journal of Northwest Forestry University,2020,35 (5): 185-194.]

[40]宋慧敏,薛亮.基于遥感生态指数模型的渭南市生态环境质量 动态监测与分析[J].应用生态学报，2016,27(12):3913-3919. [Song Huimin,Xue Liang.Dynamic monitoring and analysis of ecological environment in Weinan City,Northwest China based on

RSEI model[J]. Chinese Journal of Applied Ecology,2016,27(12): 3913-3919.] [41]Song Y,Wang J,Ge Y,et al.An optimal parameters-based geographical detector model enhances geographic characteristics of explanatory variables for spatial heterogeneity analysis: Cases with different types of spatial data[J] GIScience & Remote Sensing, 2020,5: 593-610.

# Remote sensing evaluation of ecological environment in Urumqi City and analysis of driving factors

Pariha Helili'²， ZAN Mei²， Alimjan Kasim1² (1. College of Geography and Tourism, Xinjiang Normal University,Urumqi 830054,Xinjiang, China; 2. Silk Road Economic Belt Urban Development Research Center, Xinjiang Normal University,Urumqi 830054, Xinjiang, China)

Abstract: The ecological environment quality assessment is essential to the sustainable development of the regional social economy.This paper takes Urumqi, Xinjiang,as the research area, preprocessed the Landsat series data of 2000,2010,and 2019.The principal component analysis method was used to construct the Remote Sensing Ecological Index (RSEI),and the single factor analysis and the multi-factor interaction analysis method were used in the geographic detector to influence the eight factors of RSEI (population density,land use type, altitude,economics densitygreen degree,humidity,heat,and dryness).Thequantitative detection of the degree of influence was conducted,after which the dominant factors affcting the ecological environment qualityof the study area were revealed.The results show that: (1) The average RSEI values ofUrumqi in2Ooo,2010,and 2019 were 0.21，0.21，and 0.23，respectively，showing an increasing trend.During the study period, Urumqi's ecological improvement area was greater than the area that deteriorated,indicating the ecological environment quality of Urumqi. In a state of improvement; (2)In the past 20 years,among the eight impact factors in the study area,the single factor heat index has the strongest explanatory power for the spatial diferentiation characteristics of RSEI; (3)The spatial distribution characteristics of the ecological environment in the study area are the result of the mutual interaction of multiple influencing factors. Considering the interaction of multiple factors, population density, greenness index,and dryness index are the main influencing factors and key driving forces of the quality of regional ecological environment.Evaluating the quality of the regional ecological environment, understanding the status of the ecological environment and mastering its changing laws do not only aid the promotion of sustainable development of the regional economy but also has important practical significance and reference value for constructing urban ecological civilization.

Keywords: Urumqi City； ecological environment； driving factors;remote sensing ecological index； geograph-ic detector