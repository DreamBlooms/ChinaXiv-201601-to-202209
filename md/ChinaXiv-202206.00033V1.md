# 近25a来甘肃省耕地资源时空变化及其影响因子

侯青青¹，陈英¹²，裴婷婷²，吉珍霞³，谢保鹏²(1.甘肃农业大学草业学院,甘肃 兰州730070；2.甘肃农业大学管理学院,甘肃 兰州730070;3.甘肃农业大学资源与环境学院，甘肃 兰州 730070)

摘要：研究耕地资源时空变化及驱动因子,对于提高区域粮食安全,严守耕地保护红线,制定耕地保护政策和措施具有重要的实践意义。以甘肃省1995年、2005年、2015年和2020年4期土地利用数据为基础,在ArcGIS和Geo-Da等技术的支持下,从栅格、格网和县域尺度全面分析了甘肃省近25a耕地时空变化特征,并利用地理探测器对引起耕地变化的主要驱动因子进行了探测。结果表明：(1）甘肃省1995—2020年间耕地减少幅度达 $1 . 6 \%$ ,1995—2005年耕地面积增加,2005—2020年耕地面积递减，且耕地主要流向草地、林地和建设用地,而未利用地主要向耕地和草地转移。（2）耕地空间分布呈"东南多、西北少"的典型特征。耕地空间分布受自然因素和社会经济因素的共同作用,其中,人口和土地开发强度的交互作用是1995年、2005年和2015年甘肃省耕地空间分布差异性的主要原因,而2020年温度和降水的交互作用成为影响耕地的主导因素。研究结果可为甘肃省耕地保护管理提供科学依据。

关键词：土地利用；耕地；时空演变；驱动因子；甘肃省

耕地，是人类赖以生存和发展的重要物质资源和基础[1-2],不仅担负着为人类提供食物保障的重任，而且关系着国家粮食安全和国民经济的高质量发展[3-4]。随着我国社会经济发展和城市化进程的加快，有限的耕地资源与城镇建设用地扩张、生态用地扩张之间的矛盾日益突出[5-6],导致近年来耕地数量减少、质量下降、空间破碎、生态环境等问题频发，加之耕地后备资源的不断减少，耕地合理利用和保护以及占补平衡面临多重压力[8]。此外，新型冠状病毒肺炎疫情又使全球粮食供应链遭受了巨大冲击，给世界各国粮食安全带来了严重隐患，因此，基于数据资料探究耕地的时空演变特征，阐明耕地变化的驱动因子，对于区域耕地的可持续利用、粮食安全的保障以及国土空间局部的优化具有重要指导意义[6.8.10]

由于耕地变化与区域自然环境变化和经济社会发展紧密相关，关于耕地的时空变化特征及驱动因子研究一直是国内外学者关注的热点问题[8.1]如，Yao等[12]和张国平等[13]分别在全球和局地尺度上分析了耕地资源的时空变化特征。Liu等[14]和Wang等[15则发现中国耕地利用变化会对粮食生产潜力和水资源消耗造成影响。也有学者采用复种指数、面积变化量标准差、标准椭圆差和探索性空间数据分析等方法分析耕地的时空变化特征[16-17]耕地变化的驱动机制方面,张英男等[18]和刘旭华等[19]利用空间计量模型和人工神经网络探索了耕地利用变化的驱动力，均发现耕地变化是自然因素与社会经济因素综合作用的结果，前者指出人口和产业的转型对黄淮海平原耕地的变化起决定性作用，后者则发现社会经济因素是导致东部沿海地区耕地流失的主导原因。Omaid等[20]分析了2000—2010年阿富汗喀布尔河流域的土地利用变化特征，并运用二项逻辑回归(BLR)模型对耕地变化的驱动因素进行了统计检验。陶泽涪等[2运用转移矩阵、空间自相关分析、空间计量摸型等方法系统分析了2000一2020年中国北方农牧交错带耕地时空分异特征及影响因素。此外，还有学者借助主成分分析法、地理加权回归、地理探测器和土地利用变化模拟模型等方法对耕地变化的驱动因素进行揭示研究[22]。其中，地理探测器在驱动因子探测方面获得了广泛应用，不同于传统统计分析方法，该方法的优点在于方便易用，对类别变量的处理无需太多假设，且运用地理探测器建立的因变量与自变量之间的关系比经典回归更加可靠[23]。通过地理探测器可以识别影响耕地变化的主要因素，并判断不同因素同时影响耕地时，其作用是增强还是减弱，为探究耕地变化的驱动因素提供了有效的工具[23]。如,张扬等[8]和韩海青等[23]运用地理探测器分析了喀斯特山区和中亚五国的耕地驱动机制，均发现社会经济因素的影响力大于自然因素。综上所述，耕地资源的变化同时受到自然因素和社会经济因素的共同影响,但目前关于两者的定量研究尚且不足[8],且研究尺度多集中于中东部地区，关于西北地区的耕地时空演变分析及驱动因子研究较少。

甘肃省作为我国西北地区典型的山地高原地区，地形复杂，耕地条件差，土壤类型多，人均耕地相对不足，可供开发利用的后备资源相对稀缺，加之人多地少的矛盾日益突出[24-25],因此,深入分析甘肃省的耕地资源及影响因子，对于该地区更好的保护耕地资源,加强土地管理等工作具有重要意义[25]。以往对甘肃省耕地变化的研究多集中某一局部区域，或集中在某一时段，关于近年来整个甘肃省的耕地时空变化特征并不清晰，且缺乏长时间序列的驱动因子定量化探测。如武江民等[26分析了1990—2004年甘肃兰州市耕地动态变化及驱动力，贾艳红等[27]以甘肃省2009—2016年市域单元的年末耕地面积为基础,对甘肃省各个市域单元的耕地面积变化差异及其原因进行了探索和研究。鉴于此，本文基于1995年、2005年、2015年和2020年4期土地利用动态栅格数据，在ArcGIS和GeoDa等技术的支持下，采用土地利用转移矩阵、核密度分析、耕地变化动态度、空间分布关联性分析，从栅格、格网和县域尺度全面深入分析了甘肃省近25a的耕地时空变化特征，并利用地理探测器对引起耕地变化的主要驱动因子进行探测，以期为甘肃省耕地资源的合理规划与利用提供参考依据。

# 数据与方法

# 1.1 研究区概况

甘肃省位于中国西北地区，介于 $3 2 ^ { \circ } 1 1 ^ { \prime } { \sim } 4 2 ^ { \circ } 5 7 ^ { \prime } \mathrm { N }$

$9 2 ^ { \circ } 1 3 ^ { \prime } { \sim } 1 0 8 ^ { \circ } 4 6 ^ { \prime } \mathrm { E }$ 之间,地形狭长,东西长 $1 6 5 9 \ \mathrm { k m }$ ，南北宽 $5 3 0 \mathrm { k m }$ ，总面积 $4 . 2 6 { \times } 1 0 ^ { 5 } \mathrm { k m } ^ { 2 [ 2 8 - 2 9 ] }$ 。地处黄土高原、青藏高原和内蒙古高原三大高原的交汇地带，与宁夏、陕西、四川、青海、新疆和内蒙古6省邻接，西北端与蒙古接壤，地势自西南向东北倾斜，海拔为 $5 6 5 { \sim } 5 7 8 9 \mathrm { ~ m }$ ,境内地形复杂，山脉纵横交错，海拔相差悬殊，属于典型的山地型高原地貌（图1)[29-30]。其独特的地理位置使得气候类型相当复杂，年平均气温 $0 { \sim } 1 5 ~ \mathrm { ^ { \circ } C }$ ，大部分地区气候干燥，干旱、半干旱区占总面积的 $7 5 \%$ ,年降水量在 $3 6 . 6 \sim$ $7 3 4 . 9 ~ \mathrm { m m }$ ，大致从东南向西北递减，生态环境脆弱敏感[31-32]。全省森林面积 $5 . 1 0 { \times } 1 0 ^ { 6 } \mathrm { h m } ^ { 2 }$ ,森林覆盖率$1 1 . 3 3 \%$ ，耕地 $5 . 3 8 \times 1 0 ^ { 6 } \ \mathrm { h m } ^ { 2 }$ ，占土地总面积的$1 2 . 6 2 \%$ 。截至2020年11月1日24：00，甘肃省常住人口 $2 5 0 1 . 9 8 \times 1 0 ^ { 4 }$ 人，实现地区生产总值(GDP)$9 0 1 6 . 7 { \times } 1 0 ^ { 8 }$ 元。

# 1.2数据来源与预处理

甘肃省1995年、2005年、2015年和2020年土地利用数据和行政区划数据来源于中国科学院资源环境数据中心(http://www.resdc.cn）。土地利用数据在已有地类划分标准的基础上，结合本研究需要将土地利用类型重分类分为耕地、林地、草地、水域、建设用地和未利用地6类用地，空间分辨率均为$1 ~ \mathrm { k m }$ ,其中耕地和建设用地的平均分类精度达到$9 5 \%$ 以上，其他土地利用类型平均分类精度在 $9 0 \%$ 以上，满足本研究需求[22]。降水和温度数据来源于国家地球系统科学数据中心(http://www.geodatacn）,DEM数据来源于地理空间数据云(http://www.gscloud.cn），空间分辨率均为 $1 ~ \mathrm { k m }$ 。人口和GDP数据来源于《甘肃省统计年鉴》。

# 1.3研究方法

1.3.1土地利用转移矩阵土地利用转移矩阵可以用来描述一段时间内土地利用类型之间的转移情况，分析区域土地利用类型动态变化的数量与方向[8.33]。其数学模型为：

$$
S _ { i j } = \left[ { \begin{array} { c c c c c } { S _ { 1 1 } } & { S _ { 1 2 } } & { S _ { 1 3 } } & { \cdots } & { S _ { 1 n } } \\ { S _ { 2 1 } } & { S _ { 2 2 } } & { S _ { 2 3 } } & { \cdots } & { S _ { 2 n } } \\ { S _ { 3 1 } } & { S _ { 3 2 } } & { S _ { 3 3 } } & { \cdots } & { S _ { 3 n } } \\ { \vdots } & { \vdots } & { \vdots } & { \ddots } & { \vdots } \\ { S _ { n 1 } } & { S _ { n 2 } } & { S _ { n 3 } } & { \cdots } & { S _ { n n } } \end{array} } \right]
$$

式中：S为土地面积； $n$ 为土地利用类型数； $i$ 为研究初期土地利用类型； $j$ 为研究末期土地利用类型。

1.3.2土地开发强度土地开发强度(Land Develop-mentIntensity,LDI)是指建设用地面积占区域土地

注：底图采用自然资源部标准地图制图，审图号为GS(2019)3333号，对底图边界无修改。下同。

![](images/c76f0f15f6f519ec0098bf6bf0e7d751195f02b0b3027a7099397cf2eab33b9b.jpg)  
图1 甘肃省示意图  
Fig.1 Schematic diagram of Gansu Province

总面积的比例。计算公式如下：

$$
\mathrm { L D I } = { \frac { C } { S } }
$$

式中：S为区域土地总面积； $C$ 为建设用地面积。LDI值越大，代表土地开发强度越大。

1.3.3核密度分析核密度分析是一种用于表示数据分布密度函数估计值的非参数方法8，该方法通过计算点或线要素到参考位置的距离来建立其峰值并创建平滑的连续表面[8.34]。由于耕地分布空间离散，无法直观的表示其空间上的整体性和连续性，因此本文使用核密度分析来表征研究区耕地在空间位置上的差异性和连续性[34-35]

1.3.4耕地变化动态度耕地变化动态度可以用来表征研究区在某个时间段内的耕地变化数量分布与变化速度,定量评价某地区耕地变化程度[36-37]其数学计算公式为：

$$
K = \frac { \left| U _ { b } - U _ { a } \right| } { U _ { a } } \times \frac { 1 } { T } \times 1 0 0 \
$$

式中： $K$ 为研究时间段内的耕地变化动态度， $\% \cdot \mathrm { a } ^ { - 1 }$ $U _ { a }$ 为研究初期耕地面积, $ { \mathrm { k m } } ^ { 2 }$ $U _ { b }$ 为研究末期耕地面积， $\mathrm { k m } ^ { 2 } ; T$ 为时间间隔， $\mathrm { ~ a ~ }$ 。本文中 $T$ 的时段为年，故 $K$ 值代表甘肃省耕地变化的年变化率。

1.3.5空间分布关联性分析空间自相关分析作为一种空间统计方法，是检验某一变量是否与其相邻空间点上的变量相关联的重要指标，也可以用来反映某一变量或地理现象在某区域或邻近区域的空间聚集情况,常用的关联指标为Moran'sI指数[8,38]。本文通过GeoDa工具制作耕地面积LISA聚集图，划分为4种区域空间差异类型，分别为高-高集聚（区域自身和邻近地区的耕地面积均较多，两者的空间差异程度较小）、高-低集聚（区域自身耕地面积多，邻近地区的耕地面积少，两者的空间差异程度较大）、低-高集聚(区域自身耕地面积少，邻近地区的耕地面积多，两者的空间差异程度较大)和低-低集聚（区域自身和邻近地区的耕地面积均较少，两者的空间差异程度较小)[38-40]

1.3.6 地理探测器影响耕地变化的因素错综复杂，归结起来可分为自然因素和社会经济因素[8.41]。地理探测器是探讨空间分异并揭示其背后驱动力的统计学方法，包括了风险探测器、因子探测器、生态探测器和交互探测器4个部分[8.8.42-43],本文主要用因子探测器和交互探测器来分析耕地空间分布的影响因子以及识别两两因子交互作用对耕地空间分布的解释力。其中，影响因素的地理探测器值用 $q$ 值度量，其表达式为：

$$
q = 1 - \frac { \mathrm { S S W } } { \mathrm { S S T } } = 1 - \frac { 1 } { N \sigma ^ { 2 } } { \sum _ { h = 1 } ^ { L } } N _ { h } \sigma _ { h } ^ { 2 }
$$

式中： $q$ 为影响因素对耕地空间分布的影响程度,范围为[0,1]， $\scriptstyle q$ 值越大，影响因子对耕地空间分布的解释力越强[43];SSW和SST分别为层内方差之和与全区总方差； $N$ 为全区单元数； $\sigma ^ { 2 }$ 是全区 $Y$ 值的方差； $L$ 为变量Y或影响因子 $X$ 的分层; $\boldsymbol { N } _ { h }$ 为层 $h$ 的单元数； $\sigma _ { h } ^ { 2 }$ 为层 $h$ 的Y值的方差。

# 2结果与分析

# 2.1耕地利用现状及转移特征

为研究甘肃省1995—2020年间的土地利用状态转移情况，本文基于1995年、2005年、2015年和2020年4个时间节点的土地利用现状数据，通过ArcGIS10.2中Intersect工具和Excel工具对不同时间节点的土地利用类型进行空间叠加和统计分析，获得了研究区1995—2005年、2005—2020年2个时间段的土地利用转移矩阵(表1和表2)。总体来看，甘肃省土地利用结构除未利用地外，主要以草地和耕地为主，分别约占甘肃省总面积的 $34 \%$ 和 $1 5 \%$ 。研究区土地利用结构在1995—2020年间变化明显。耕地面积由1995年的 $6 5 0 4 3 . 7 5 \ \mathrm { k m } ^ { 2 }$ 减少到2020年的 $6 3 9 8 3 . 5 0 \mathrm { k m } ^ { 2 }$ ,减少了 $1 0 6 0 . 2 5 \mathrm { k m } ^ { 2 }$ ,减少幅度约为 $1 . 6 \%$ ,主要转向草地、林地和建设用地;未利用面积也由1995年的 $1 7 1 6 8 9 . 5 0 \mathrm { k m } ^ { 2 }$ 减少到2020年的 $1 6 9 2 1 3 . 2 5 ~ \mathrm { k m } ^ { 2 }$ ，减少了 $2 4 7 6 . 2 5 ~ \mathrm { k m } ^ { 2 }$ ，减少幅度约为 $1 . 4 \%$ ，主要转向耕地和草地;其他地类呈不同程度的增加状态，尤其是林地和建设用地，1995—2020年林地面积增加了 $8 0 8 . 7 5 ~ \mathrm { k m } ^ { 2 }$ ,1995—2020年建设用地面积增加了 $2 1 1 4 . 5 0 \mathrm { k m } ^ { 2 }$ ,增加幅度分别为$2 . 1 5 \%$ 和 $6 1 . 7 0 \%$ 。各地类间的转换特征在不同时间段内存在差异。

1995一2005年的土地利用转移矩阵如表1，6类土地利用类型中变化面积最大的是未利用地,其次是林地、耕地和建设用地，水域和草地的变化面积最小。其中，耕地和林地的年净增长面积分别为$3 9 . 2 5 ~ \mathrm { k m } ^ { 2 }$ 和 $6 1 . 4 5 ~ \mathrm { k m } ^ { 2 }$ ，而未利用地面积在1995—2005年的近10a间年净减少 $1 0 8 . 4 3 \mathrm { k m } ^ { 2 }$ 。与1995—2005年之间的土地利用转移所不同是，2005—2020年之间是以建设用地的转化面积最大，其次是耕地、未利用地和草地。其中，耕地和未利用地的面积均减少，年净减少面积分别为 $9 6 . 8 5 \mathrm { ~ k m } ^ { 2 }$ 和92.80$ { \mathrm { k m } } ^ { 2 }$ ,耕地主要流向林地和草地,未利用地主要流向耕地和草地，这主要与我国退耕还林还草、西部大开发和未利用地开发利用等政策密切有关。建设用地面积在1995—2005年和2005—2020年的2个时间段内年净增长面积呈增加趋势，由 $3 2 . 8 0 \mathrm { k m } ^ { 2 }$ 变为 $1 1 9 . 1 0 \mathrm { k m } ^ { 2 }$ ，这与我国快速城镇化以及经济发展的步伐密切相关。

Tab.1 Land use transfer matrix in GansuProvince from1995 to 2005   
/km²   

<html><body><table><tr><td>土地利用类型</td><td>耕地</td><td>林地</td><td>草地</td><td>水域</td><td>建设用地</td><td>未利用地</td><td>1995年总计</td><td>年净增长面积</td></tr><tr><td>耕地</td><td>36093.75</td><td>2865.50</td><td>22104.25</td><td>531.50</td><td>1915.00</td><td>1533.75</td><td>65043.75</td><td>39.25</td></tr><tr><td>林地</td><td>2731.00</td><td>22246.50</td><td>11534.25</td><td>114.75</td><td>133.75</td><td>804.25</td><td>37564.50</td><td>61.45</td></tr><tr><td>草地</td><td>22102.75</td><td>11949.50</td><td>92764.75</td><td>642.00</td><td>738.75</td><td>14749.50</td><td>142947.25</td><td>-20.03</td></tr><tr><td>水域</td><td>580.25</td><td>86.75</td><td>629.25</td><td>1205.75</td><td>59.75</td><td>832.00</td><td>3393.75</td><td>-5.05</td></tr><tr><td>建设用地</td><td>1705.75</td><td>108.75</td><td>703.50</td><td>54.50</td><td>741.00</td><td>113.50</td><td>3427.00</td><td>32.80</td></tr><tr><td>未利用地</td><td>2222.75</td><td>922.00</td><td>15011.00</td><td>794.75</td><td>166.75</td><td>152572.25</td><td>171689.50</td><td>-108.43</td></tr><tr><td>2005年总计</td><td>65436.25</td><td>38179.00</td><td>142747.00</td><td>3343.25</td><td>3755.00</td><td>170605.25</td><td>424065.75</td><td>0.00</td></tr></table></body></html>

表11995—2005年甘肃省土地利用转移矩阵  
表22005—2020年甘肃省土地利用转移矩阵  
Tab.2Land use transfer matrixin Gansu Province from 2oo5 to 2020   

<html><body><table><tr><td>土地利用类型</td><td>耕地</td><td>林地</td><td>草地</td><td>水域</td><td>建设用地</td><td>未利用地</td><td>2005年总计</td><td>年净增长面积</td></tr><tr><td>耕地</td><td>33352.25</td><td>3235.00</td><td>23833.25</td><td>604.00</td><td>2552.75</td><td>1864.75</td><td>65436.25</td><td>-96.85</td></tr><tr><td>林地</td><td>3025.25</td><td>20947.25</td><td>12967.75</td><td>142.00</td><td>220.50</td><td>922.75</td><td>38179.00</td><td>12.95</td></tr><tr><td>草地</td><td>22717.00</td><td>12926.50</td><td>88461.75</td><td>754.25</td><td>1330.50</td><td>16541.75</td><td>142747.00</td><td>30.67</td></tr><tr><td>水域</td><td>564.50</td><td>98.75</td><td>707.75</td><td>1092.75</td><td>81.75</td><td>800.50</td><td>3343.25</td><td>29.60</td></tr><tr><td>建设用地</td><td>1788.50</td><td>135.00</td><td>863.00</td><td>79.00</td><td>745.50</td><td>144.25</td><td>3755.00</td><td>119.10</td></tr><tr><td>未利用地</td><td>2536.00</td><td>1030.75</td><td>16373.50</td><td>1115.25</td><td>610.50</td><td>148939.25</td><td>170605.25</td><td>-92.80</td></tr><tr><td>2020年总计</td><td>63983.50</td><td>38373.25</td><td>143207.00</td><td>3787.25</td><td>5541.50</td><td>169213.25</td><td>424065.75</td><td>0.00</td></tr></table></body></html>

# 2.2耕地面积密度空间分布特征

使用ArcGIS核密度分析并用自然断点法将耕地密度和面积分级显示在空间上，如图2所示。甘肃省1995年、2005年、2015年和2020年耕地面积总量分别为 $6 5 0 4 3 . 7 5 \ \mathrm { k m } ^ { 2 } , 6 5 4 3 6 . 2 5 \ \mathrm { k m } ^ { 2 } , 6 4 9 9 2 . 7 5 \ \mathrm { k m } ^ { 2 }$ 和 $6 3 9 8 3 . 5 0 \ \mathrm { k m } ^ { 2 }$ 。空间分布总体呈“东南多、西北少”的典型分布特征，且1995—2020年耕地面积密度变化不大(图2)，空间分布格局基本一致，各年度间的变化仅发生在几个零星格网，且各级别的耕地面积总量变化不大。由于自然条件、经济发展水平及人口增长速度等的差异,造成甘肃省耕地的空间分布表现出明显的差异[25（图3)。耕地面积密度较高的区域集中在甘肃省中东部地区，包括定西市、天水市、平凉市、庆阳市和兰州市等地区，以及白银市和临夏回族自治州的部分地区，其中，以定西市的通渭县、天水市的秦安县、清水县和张家川回族自治县、平凉市的庄浪县和静宁县的耕地面积密度最大(图2)。

# 2.3耕地空间分布关联性分析

对2020年耕地面积使用GeoDa工具进行空间自相关分析，结果如图4。2020年甘肃省耕地面积的Moran'sI指数为0.75，显著性检验的Z值为88.21, $\scriptstyle P = 0 . 0 0 1$ ，呈现显著正相关，说明2020年甘肃省耕地面积的空间分布格局与相邻位置的区域单元具有相同的属性值。从局部空间自相关结果来看(图4)，除不显著区域外，耕地面积的低-低集聚数量最多，其次是高-高集聚，而高-低集聚、低-高集聚极少。低-低集聚类主要分布在甘肃省西北部的河西地区和甘南藏族自治州，土地利用类型主要是未利用地和草地，属于生态脆弱敏感区，耕地面积少、密度低;高-高集聚类主要分布甘肃省东南部区域,即定西市、天水市、平凉市、庆阳市、临夏回族自治州、陇南市和白银市的部分区域，如礼县、西和县、成县、会宁县和靖远县等县域，这些区域与相邻位置的自然条件比较相似，耕地面积均较高。

# 2.4耕地资源时空演变特征

2.4.1耕地变化动态度以县域作为耕地变化动态度空间分析的最小单元，来分析甘肃省各县域之间

![](images/1a9b8162af60331949110d78208a99ac65007523ced5b0e73f009beca8c31b1c.jpg)  
图21995—2020年甘肃省耕地核密度分布

Fig.2 Spatial distribution of cultivated land nuclear density in Gansu Province from l995 to 2020耕地变化的差异情况。由图5可以看出，耕地变化动态度在各县域间和不同时期间的空间差异性均较大，1995一2005年间甘肃省各县域的耕地变化动态度均较高，以河西地区的动态变化最为强烈，可能原因是河西地区地势平坦，资源丰富，人均GDP始终处于甘肃省的最前沿，人类活动强度较大[27]；

![](images/f9a23764ad937d787755d8c25322f410086c45025fe163b6461da00454f2c013.jpg)  
Fig.3Spatial distribution of cultivated land area in Gansu Province from 1995 to 2020

![](images/e946611a70a013e2b6191186d0ce39bfc2f25eac088f4eb3d28d7cbee8997f79.jpg)  
图31995—2020年甘肃省耕地面积空间分布  
注：括号内数字代表格网数量。  
图4甘肃省2020年耕地面积LISA聚集图和Moran散点图  
Fig.4LISA aggregation map and Moran scatter plot of arable land area in Gansu Province in 202

另一方面，有限的水资源是河西地区农业发展的最大障碍，因人类不合理利用水土资源导致的土壤次生盐渍化、荒漠化等生态问题也是引起耕地波动较大的主要原因[44]。2005—2015年间酒泉市大部分县域的耕地变化动态度有所减小，2015—2020年间甘肃省大部分地区的耕地变化动态度均有减小趋势。但值得一提的是，酒泉市各县域在1995—2005年、2005—2015年和2015—2020年间的耕地变化动态度出现了由大部分县域变化到局部变化，再到各县域耕地频繁变化的特征，主要原因是2005年酒泉市的土地利用结构、农业结构进行了大幅度调整同时大量未利用地开发整理为耕地等一系列土地政策均使耕地在空间上有了大幅度变化[45]

![](images/25e054b67f190a45136edd04f8c442328b6790897e864c784747eff16cf296ce.jpg)  
图51995—2020年甘肃省县域耕地变化动态度空间分布格局 Fig.5Spatial distribution pattern of the dynamic degree of cultivated land change at the county level in Gansu Province from 1995 to 2020

2.4.2耕地资源变化类型空间分布为了更好的揭示研究区耕地资源在空间上的增减情况，本文以格网作为统计单元,将耕地在各个时间段的变化情况划分为增加和减少2种类型，由此得到研究区3个时间段的耕地变化类型(图6)。

从空间分布上来看，甘肃省耕地变化类型的空间分布都较为均衡，各时间段之间的差异性较小。时间上来看，1995—2005年间耕地增加和减少类型的格网数量分别为1679个和276个，耕地以增加为主，而2005—2015年和2015—2020年间耕地以减少为主，耕地减少类型的格网数量分别为1014个和1001个，增加类型格网零散分布在其中。耕地面积的减少量在1995—2020年间的3个时间段出现了增加再减少的变化特征，2005一2015年间耕地减少类型的格网数量最大，2015—2020年间减少类型格网数量回升，但变化程度不大。耕地减少面积在2005年之后的2个时间段内均大于增加面积（图7)。2005年后，一方面受到退耕还林、快速城镇化、防护林建设等政策影响，另一方面随着社会经济发展，农村人口向城镇转移，使得耕地面积逐渐减少，由1995—2005年的耕地增加多，到2005—2020年的耕地减少多。但后期随着一系列政策的提出，使得部分劳动力向农村转移，出现了2015—2020年间耕地减少量相比于2005—2015年间的耕地减少量有降低的现象。

# 2.5耕地时空演变的驱动因子分析

本文选取3个自然驱动因子(降水、温度和坡度)和3个社会经济驱动因子（人口、GDP和土地开发强度），共计6个驱动因子，以 $1 0 \ \mathrm { k m } { \times } 1 0 \ \mathrm { k m }$ 为单元将研究区划分为3925个单元格，并将各影响因子划分为6个等级，经地理探测器计算后，各因子对耕

注：括号内数字代表格网数量。

![](images/5e1336e983425356237f640102f42e75d7bd307a1950311d7abfc9503d787d6d.jpg)  
图61995—2020年甘肃省县域耕地变化动态度空间分布格局 Fig.6 Spatial distribution pattern of the dynamic degree of cultivated land change at the county level in Gansu Province from 1995 to 2020   
图7甘肃省1995—2020年间3个时段耕地增减 Fig.7Increase and decrease of cultivated land in three time periods in Gansu Province from 1995 to 2020

$\Lleftarrow$ 耕地增加面积 $$ 耕地减少面积 一正增长格网数量 $\scriptstyle - \infty -$ 负增长格网数量   
180000 1800   
160000 1600   
140000 1400 /雪区   
120000 1200   
100000 1000   
80000 800   
60000 600   
40000 400   
20000 200 0 0 1995—2005 2005—2015 2015—2020 时段/年

地空间分布的贡献率如表3所示。从表3可以看出，不同时期各因子贡献率排序差别不大，起主导作用的地理探测因子具有一定的相似性。1995年各因子的贡献率排序为： $X 1 { > } X 3 { > } X 4 { > } X 2 { > } X 5 { > } X 6$ 2005年各因子的贡献率排序为： $X 3 { > } X 1 { > } X 2 { > } X 4 { > } X 5 { > }$ X6;2015年各因子的贡献率排序为： $X 1 { > } X 3 { > } X 2 { > } X 4 { > }$ $X 5 { > } X 6 ; 2 0 2 0$ 年各因子的贡献率排序为： $. X 1 { > } X 2 { > } X 4 { > }$ $X 5 { > } X 3 { > } X 6$ 。

为了探测两驱动因子间的交互作用，本文利用地理探测器对6个驱动因子进行两两交互检测（表4)。1995年 $X 1 \cap X 3 \setminus X 3 \cap X 4 \setminus X 4 \cap X 5$ 交互值最大，分别为0.61、0.58、0.54;2005年 $X 1 { \cap } X 3 \ 、 X 2 { \cap } X 3 \ 、 X 3 { \cap } X 4$ 交互值最大，分别为 $0 . 2 4 \cdot 0 . 2 4 \cdot 0 . 2 2 ; 2 0 1 5$ 年X1∩X3、X2∩X3、X4∩X5交互值最大，分别为0.57、0.58、0.52；2020年 $X 4 \cap X 5 \setminus X 1 \cap X 2 \setminus X 1 \cap X 4$ 交互值最大，分别为0.52、0.48、0.47。1995年、2005年和2015年交互值最大的均为 $X 1$ 和 $X 3$ ，各地理探测因子间的交互作用为双因子增强和非线性增强，即两驱动因子共同作用时均增加了对耕地空间分布的解释力。2020年交互值最大的为 $X 4$ 和 $X 5$ ,其次是 $X 1$ 和 $X 2$ ，温度和降水的共同作用对耕地空间分布的解释力最强。所有影响因子任意两者的交互作用对研究区耕地的影响都不是独立的，即便是解释力最弱的坡度因子，在与其他因子交互作用下，对耕地的影响力也增强。

总体来看，甘肃省耕地空间分异的结果不是由单一因子构成的，而是多种因子相互作用形成的。

Tab.3Variables and indicators of the Gansu Geographical Detector in1995,2005,2015,and 202(   

<html><body><table><tr><td rowspan="2">驱动因子</td><td rowspan="2">分级</td><td colspan="2">1995年</td><td colspan="2">2005年</td><td colspan="2">2015年</td><td colspan="2">2020年</td></tr><tr><td>q值</td><td>P值</td><td>q值</td><td>P值</td><td>q值</td><td>P值</td><td>q值</td><td>P值</td></tr><tr><td>人口(X1)</td><td>6</td><td>0.45</td><td>0</td><td>0.16</td><td>0</td><td>0.41</td><td>0</td><td>0.39</td><td>0</td></tr><tr><td>GDP(X2)</td><td>6</td><td>0.29</td><td>0</td><td>0.14</td><td>0</td><td>0.38</td><td>0</td><td>0.38</td><td>0</td></tr><tr><td>土地开发强度(X3)</td><td>6</td><td>0.42</td><td>0</td><td>0.17</td><td>0</td><td>0.40</td><td>0</td><td>0.07</td><td>0</td></tr><tr><td>降水(X4)</td><td>6</td><td>0.37</td><td>0</td><td>0.10</td><td>0</td><td>0.26</td><td>0</td><td>0.36</td><td>0</td></tr><tr><td>温度(X5)</td><td>6</td><td>0.14</td><td>0</td><td>0.05</td><td>0</td><td>0.12</td><td>0</td><td>0.13</td><td>0</td></tr><tr><td>坡度(X6)</td><td>6</td><td>0.01</td><td>0</td><td>0.01</td><td>0</td><td>0.01</td><td>0</td><td>0.01</td><td>0</td></tr></table></body></html>

注：q为影响因素对耕地空间分布的影响程度； $P$ 为显著性水平。

表31995年、2005年、2015年和2020年甘肃省地理探测器变量和指标  
表41995年、2005年、2015年和2020年甘肃省各因子交互作用  
Interactions of various factors in Gansu Province in 1995,20o5,2015,and 2020   

<html><body><table><tr><td></td><td></td><td>人口(X1)</td><td>GDP(X2)</td><td>土地开发强度(X3)</td><td>降水(X4)</td><td>温度(X5)</td><td>坡度(X6)</td></tr><tr><td>1995年</td><td>人口(X1)</td><td>0.45</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>GDP(X2)</td><td>0.51</td><td>0.29</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>土地开发强度(X3)</td><td>0.61</td><td>0.53</td><td>0.42</td><td></td><td></td><td></td></tr><tr><td></td><td>降水(X4)</td><td>0.52</td><td>0.46</td><td>0.58</td><td>0.37</td><td></td><td></td></tr><tr><td></td><td>温度(X5)</td><td>0.50</td><td>0.41</td><td>0.48</td><td>0.54</td><td>0.14</td><td></td></tr><tr><td></td><td>坡度(X6)</td><td>0.46</td><td>0.30</td><td>0.43</td><td>0.39</td><td>0.16</td><td>0.01</td></tr><tr><td>2005年</td><td>人口(X1)</td><td>0.16</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>GDP(X2)</td><td>0.21</td><td>0.14</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>土地开发强度(X3)</td><td>0.24</td><td>0.24</td><td>0.17</td><td></td><td></td><td></td></tr><tr><td></td><td>降水(X4)</td><td>0.19</td><td>0.18</td><td>0.22</td><td>0.10</td><td></td><td></td></tr><tr><td></td><td>温度(X5)</td><td>0.19</td><td>0.17</td><td>0.19</td><td>0.19</td><td>0.05</td><td></td></tr><tr><td></td><td>坡度(X6)</td><td>0.17</td><td>0.15</td><td>0.18</td><td>0.12</td><td>0.06</td><td>0.01</td></tr><tr><td>2015年</td><td>人口(X1)</td><td>0.40</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>GDP(X2)</td><td>0.49</td><td>0.38</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>土地开发强度(X3)</td><td>0.57</td><td>0.58</td><td>0.40</td><td></td><td></td><td></td></tr><tr><td></td><td>降水(X4)</td><td>0.47</td><td>0.48</td><td>0.51</td><td>0.26</td><td></td><td></td></tr><tr><td></td><td>温度(X5)</td><td>0.47</td><td>0.46</td><td>0.45</td><td>0.52</td><td>0.12</td><td></td></tr><tr><td></td><td>坡度(X6)</td><td>0.41</td><td>0.39</td><td>0.41</td><td>0.28</td><td>0.14</td><td>0.01</td></tr><tr><td>2020年</td><td>人口(X1)</td><td>0.39</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>GDP(X2)</td><td>0.48</td><td>0.38</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>土地开发强度(X3)</td><td>0.41</td><td>0.41</td><td>0.07</td><td></td><td></td><td></td></tr><tr><td></td><td>降水(X4)</td><td>0.47</td><td>0.46</td><td>0.38</td><td>0.36</td><td></td><td></td></tr><tr><td></td><td>温度(X5)</td><td>0.45</td><td>0.45</td><td>0.22</td><td>0.52</td><td>0.13</td><td></td></tr><tr><td></td><td>坡度(X6)</td><td>0.39</td><td>0.39</td><td>0.08</td><td>0.37</td><td>0.15</td><td>0.01</td></tr></table></body></html>

1995年、2005年和2015年，社会经济因素的影响大于自然因素，其中，人口 $( X 1 )$ 和土地开发强度 $( X 3 )$ 对甘肃省耕地空间分布的影响最大，即人口和土地开发强度是甘肃省耕地空间分布差异性的主要原因，温度(X5)和坡度( $( X 6 )$ 的 $q$ 统计值在0.01\~0.14之间，虽在一定程度上影响着耕地空间分布，但影响程度较小。到2020年，社会经济因素对耕地的驱动力减弱，自然因素对耕地的影响作用增强，其中，土地开发强度 $( X 3 )$ 对耕地空间分布的影响力明显减弱，人口 $( X 1 )$ 和 $\mathrm { G D P } ( X 2 )$ 的贡献率虽大于降水( ${ \left( \chi 4 \right) }$ 和温度（ $( \chi 5 )$ ，但温度和降水的共同作用对耕地空间分布的影响最大。且降水与其他因子的交互作用对耕地空间分异的影响大于温度和坡度与其他因子的交互作用，因此，降水量可能是影响甘肃耕地空间分异的主要自然因素。表明1995—2015年，人□增长速度加快和城镇化进程的快速推进促进人类活动对耕地的影响强度增大，建设用地持续扩张，人口和土地开发强度成为影响耕地时空分异的主要因素。但受粮食安全保障压力的驱动，耕地流失在一定程度上得到控制，高标准基本农田建设项目持续推进，使得甘肃省耕地空间分布格局基本稳定，再加上甘肃省降水主要集中在6一8月，降水量呈上升趋势[46],降水量增多又能够为农作物生长提供有力的条件。因此，经济发展水平对耕地的影响逐渐减弱，降水和温度的交互作用强于人口和GDP的交互作用 $( 0 . 5 2 { > } 0 . 4 8 )$ ，成为影响耕地的主导因素。

# 3结论

本文以甘肃省1995年、2005年、2015年和2020年4期土地利用数据为基础，借助ArcGIS空间分析功能、GeoDa空间分布关联性分析以及地理探测器技术等方法，分析了研究区土地利用转移情况，揭示了甘肃省耕地的时空变化特征，并探明了影响其空间分异的主要驱动因子。主要结论如下：

（1）甘肃省土地利用结构在1995—2020年间发生了明显变化。耕地减少幅度达 $1 . 6 \%$ ,1995—2005年耕地面积增加，2005—2020年耕地面积递减。从土地利用转移矩阵来看，耕地主要流向草地、林地和建设用地，未利用地主要流向耕地和草地。且不同地类间的转换特征在不同研究时间段内差异性明显。

(2）甘肃省耕地空间分布上，呈“东南多、西北少"的典型分布特征，且耕地面积的低-低集聚区数量最多，主要分布在甘肃省西北部的河西地区和甘南藏族自治州，属于生态脆弱敏感区，耕地面积少、密度低。

(3）甘肃省耕地空间分布受自然因素和社会经济因素的共同作用。1995年、2005年、2015年和2020年各期数据中各因子对耕地空间分布贡献率排序差别不大，起主导作用的地理探测因子具有一定的相似性。人口和土地开发强度的交互作用是1995年、2005年和2015年甘肃省耕地空间分布差异性的主要原因，而2020年温度和降水的交互作用成为影响耕地的主导因素。

参考文献(References):   
[1]陈百明,王秀芬.耕地质量建设的生态与环境理念[J].中国农业 资源与区划,2013,34(1):1-4.[Chen Baiming,Wang Xiufen. Ecological and environmental idea of cultivated land quality construction[J]. Chinese Journal of Agricultural Resources and Regional Planning,2013,34(1): 1-4.]   
[2]杨桂山.长江三角洲近50年耕地数量变化的过程与驱动机制 研究[J].自然资源学报,2001,16(2):121-127.[Yang Guishan. The process and driving forces of change in arable-land area in the Yangtze River Delta during the past 5O years[J]. Journal of Natural Resources,2001,16(2): 121-127.]   
[3]赵晓丽,张增祥,汪潇,等.中国近30 a耕地变化时空特征及其 主要原因分析[J].农业工程学报,2014,30(3):1-11.[Zhao Xiaoli,Zhang Zengxiang,Wang Xiao,et al. Analysis of Chinese cultivated land’sspatial-temporal changesand causes in recent 30 years[J]. Transactions of the Chinese Society of Agricultural Engineering,2014,30(3): 1-11.]   
[4]周润芳,孙建国,张卓.甘肃省榆中县地形对耕地分布影响[J]. 遥感信息,2020,35(4): 148-154.[Zhou Runfang,Sun Jianguo, Zhang Zhuo.Effects of topographic on cultivated land distribution in Yushong County of Gansu Province[J].Remote Sensing Information,2020,35(4): 148-154.]   
[5]关兴良,方创琳,鲁莎莎.中国耕地变化的空间格局与重心曲线 动态分析[J].自然资源学报,2010,25(12):1997-2006.[Guan Xingliang,Fang Chuanglin,Lu Shasha.Analysis of spatial distribution and gravity centers curve dynamic cultivated land changes in China[J]. Journal of Natural Resources,2010,25(12):1997- 2006.]   
[6]袁承程,张定祥,刘黎明,等.近10年中国耕地变化的区域特征 及演变态势[J].农业工程学报,2021,37(1):267-278.[Yuan Chengcheng, Zhang Dingxiang,LiuLiming, et al.Regionalcharacteristics and spatial-temporaldistributionof cultivated land change in China during 2O09-2018[J]. Transactions of the Chinese Society of Agricultural Engineering,2021,37(1): 267-278.]   
[7]陈正发,史东梅,何伟,等.基于“要素-需求-调控”的云南坡 耕地质量评价[J].农业工程学报,2020,36(12):236-246.[Chen Zhengfa,Shi Dongmei,He Wei,etal. Quality evaluationofslope farmland in Yunnan Province based on“element-demand-regulation” framework[J]. Transactions of the Chinese Society of Agricultural Engineering,2020,36(12): 236-246.]   
[8]张扬,周忠发,黄登红,等.喀斯特山区耕地时空演变与影响因 子分析[J].农业工程学报,2020,36(22:266-275.[Zhang Yang, Zhou Zhongfa,Huang Denghong, et al.Spatial-temporal evolution of cultivated land and analysis of influence factors in Karst moun tainous areas[J]. Transactions of the Chinese Society of Agricultural Engineering,2020,36(22): 266-275.]   
[9]宋莉莉,张琳,杨艳涛,等.新型冠状病毒肺炎疫情对我国粮食 产业的影响分析[J].中国农业科技导报,2020,22(6):12-16. [Song Lili, Zhang Lin,Yang Yantao,etal.lnfluence of COVID-19 Epidemic on China’s Grain Industry[J]. Journal of Agricultural Science and Technology,2020,22(6): 12-16.]   
[10] Liu Wenchao,Liu Jiyuan,Yan Changzhen,et al. Cropland dynamics and their influence on the productivity in northern Shaanxi, China,for thepast 2O years: Basedonremotely sensed data[J]. Journal of Resources and Ecology,2014,5(3): 272-279.   
[11] 赵倩石,潘佩佩,王晓旭,等.基于DEA-Malmquist指数的河北 省耕地利用效率及其影响因素研究[J].干旱区研究,2021,38 (4): 1162-1171.[Zhao Qianshi,Pan Peipei, Wang Xiaoxu,et al.A study of cultivated landutilization effciency and its influencing factors in Hebei Province based on DEA-Malmquist index[J].Arid Zone Research,2021, 38(4): 1162-1171.]   
[12]Yao Z Y,Zhang LJ, Tang SH,et al. The basic characteristics and spatial patterns of global cultivated land change since the 1980s [J].Journal of Geographical Sciences,2017,27(7): 771-785.   
[13] 张国平,刘纪远,张增祥.近10年来中国耕地资源的时空变化 分析[J].地理学报,2003,58(3): 323-332.[Zhang Guoping,Liu Jiyuan,Zhang Zengxiang.Analysis of and Spatial-temporal changes of cropland in China for the past 10 years based on remote sensing[J].Acta Geographica Sinica,2018,2003,58(3): 323-332.]   
[14]Liu L, Xu X L, Liu JY,et al. Impact of farmland changes on production potential in China during recent two decades[J]. Journal of Geographical Sciences,2015,25(1): 19-34.   
[15]Wang X,Xin L J,Tan MH,et al. Impact of spatiotemporal change of cultivated land on food-water relations in China during 1990- 2015[J]. Science of The Total Environment,2020,716: 1-11.   
[16]胡琼,吴文斌,项铭涛,等.全球耕地利用格局时空变化分析[J]. 中国农业科学,2018,51(6):1091-1105.[Hu Qiong,Wu Wenbin, Xiang Mingtao,etal.Spatio-temporal changes inglobal cultivated land over 2OOO-201O[J]. Scientia Agricultura Sinica,2018, 51(6): 1091-1105.]   
[17] 牛善栋,方斌,崔翠,等.乡村振兴视角下耕地利用转型的时空 格局及路径分析——以淮海经济区为例[J].自然资源学报, 2020,35(8): 1908-1925.[Niu Shandong,Fang Bin, Cui Cui,et al. The spatial-temporal pattern and path of cultivated land use transition from the perspective of rural revitalization: Taking Huaihai Economic Zone as an example[J]. Journal of Natural Resources, 2020,35(8): 1908-1925.]   
[18] 张英男,龙花楼,戈大专,等.黄淮海平原耕地功能演变的时空 特征及其驱动机制[J].地理学报,2018,73(3):518-534.[Zhang Yingnan,Long Hualou,Ge Dazhuan, et al. Spatial-temporal characteristics and dynamic mechanism of farmland functions evolution in Huang-Huai-Hai Plain[J].Acta Geographica Sinica,2018, 73(3): 518-534.]   
[19] 刘旭华.王劲峰.刘纪远.等.国家尺度耕地变化驱动力的定量

分析方法[J].农业工程学报,2005,21(4):56-60.[Liu Xuhua, Wang Jinfeng,Liu Jiyuan,et al. Quantitative analysis approaches to the driving forces of cultvated land changes on a national scale [J].Transactions of the Chinese Society of Agricultural Engineering,2005,21(4): 56-60.]   
[20] Omaid N, Xiang Zhengdeng, Ruchira B.The dynamics of land use/ cover and the statistical assessment of cropland change drivers in the Kabul River Basin,Afghanistan[J]. Sustainability,2018,10(2): 423.   
[21] 陶泽涪,王世清,孙丕苓,等.中国北方农牧交错带耕地时空分 异及驱动因素[J].干旱区地理,2022,45(1):153-163.[Tao Zefu, Wang Shiqing,Sun Piling,et al.Spatio-temporal diffrentiation and driving factors of cropland in the agro-pastoral ecotone of northern China[J].Arid Land Geography,2022,45(1): 153-163.]   
[22] 罗芳,潘安,陈忠升,等.四川省宜宾市耕地时空格局变化及驱 动力分析[J].水土保持通报,2021,46(6):336-344.[Luo Fang, Pan An, Chen Zhongsheng,et al. Spatiotemporal pattrn change of cultivated land and its driving forces in Yibin City,Sichuan Province[J].Bulletin of Soil and Water Conservation,2O21,46(6): 336- 344.]   
[23] 韩海青,王旭红,牛林芝,等.1992—2015年中亚五国LUCC 特 征及耕地驱动力研究[J].中国生态农业学报,2021,29(2):325- 339.[Han Haiqing,Wang Xuhong,Niu Linzhi, et al.The land-use and land-cover change characteristics and driving forces of cultivated land in Central Asian countries from 1992 to 2015[J]. Chinese Journal of Eco-Agriculture,2021,29(2): 325-339.]   
[24] 王凤娇,杨延征,上官周平.西北五省(区)耕地质量等别差异性 比较[J].干旱地区农业研究,2015,33(2):230-236.[Wang Fengjiao, Yang Yanzheng, Shangguan Zhouping. Comparisons on variation in qualities of arable lands in northwestern China[J]. Agricultural Research in the Arid Areas,2015,33(2): 230-236.]   
[25] 杨斐,肖玲,张玲,等.甘肃省耕地资源势态演变及驱动机制研 究[J].水土保持通报,2010,30(4): 214-218.[Yang Fei, Xiao Ling,Zhang Ling,et al. Situational development and dynamic mechanisms of cultivated land resources in Gansu Province[J]. Bulletin of Soil and Water Conservation,2010,30(4): 214-218.]   
[26] 武江民,赵学茂,党国锋.甘肃兰州市耕地动态变化与驱动力关 系定量研究[J].干旱区资源与环境,2010,24(12):33-38.[Wu Jiangmin, Zhao Xuemao,Dang Guofeng.Variation of cultivated land and its driving forces in Lanzhou City,Gansu[J]. Journal of Arid Land Resources and Environment, 2010, 24(12): 33-38.]   
[27] 贾艳红,晏忠凤.市域尺度下甘肃省耕地变化的区域差异研 究[J].测绘与空间地理信息,2021,44(8):7-11.[Jia Yanhong, Yan Zhongfeng. Study on the regional differences of cultivated land change in Gansu Province under the municipal scale[J]. Geomatics& Spatial Information Technology,2021,44(8): 7-11.]   
[28] 刘普幸,张红侠.甘肃张掖市耕地变化及驱动力研究[J].土壤, 2003,35(6): 485-489.[Liu Puxing, Zhang Hongxia. Variation of cultvated land and its driving forces in Zhangye city of Gansu[J]. Solis,2003,35(6): 485-489.]   
[29]仲兆隆,郭方忠.甘肃概况 $( { \stackrel { - } { - } } )$ [J].档案,1986(2): 46-49.[Zhong Zhaolong,Guo Fangzhong. Gansu Provisional(2)[J]. Archives,1986 (2): 46-49.]   
[30]白书明,任秀英,国芳,等.甘肃省环境天然放射性水平研究 [J].环境科学学报,1992,12(3):382-389.[Bai Shuming,Ren Xiuying,Zhao Guofang,et al. Natural radioactive level in environment of Gansu Province[J].Acta Scientiae Circumstantiae,1992, 12(3): 382-389.]   
[31] 赵鸿雁,陈英,谢保鹏,等.甘肃省违法占用耕地的生态服务价 值损失计量研究[J].草原与草坪,2020,40(5):83-90.[Zhao Hongyan, Chen Ying, Xie Baopeng, et al. Study on the estimation of ecological service value loss caused by illgal occupationof arable land in Gansu Province[J]. Grassand and Turf, 2020,40(5): 83-90.]   
[32] 赵鸿雁,陈英,裴婷婷,等.土地整治的生态系统服务价值评估 -参数优化与实证[J].干旱区研究,2020,37(2):514-522 [Zhao Hongyan,Chen Ying,Pei Tingting,etal.Evaluationof the ecosystem service value with land consolidation: Parameter optimization and empirical study[J]. Arid Zone Research, 2020,37(2): 514-522.]   
[33] 刘婉如,陈春波,罗格平,等.巴尔喀什湖流域土地利用/覆被变 化过程与趋势[J].干旱区研究,2021,38(5):1452-1463.[Liu Wanru, Cheng Chunbo,Luo Geping,e al. Change processes and trends of land use/cover in the Balkhash Lake Basin[J].Arid Zone Research,2021,38(5): 1452-1463.]   
[34] 张素丽,佟宝全,郝晶晶.牧区聚落时空特征及其形成机制— 以正蓝旗为例[J].干旱区研究,2018,35(1):227-234.[Zhang Suli,Tong Baoquan,Hao Jingjing. Spatiotemporal evolution and their formation mechanism of settlements in pastoral area: A case study in Zhenglan Banner[J]. Arid Zone Research,2018,35(1): 227-234.]   
[35] 韩春萌,刘慧平,张洋华,等.基于核密度函数的多尺度北京市 休闲农业空间分布分析[J].农业工程学报,2019,35(6):271- 278.[Han Chunmeng,Liu Huiping, Zhang Yanghua, et al. Multiscale spatial distribution analysisofleisure agriculture in Beijing based on kernel density estimation[J]. Transactions of the Chinese Society of Agricultural Engineering,2019,35(6): 271-278.]   
[36] 文广超,赵梅娟,谢洪波,等.伊犁河谷西部土地植被覆盖演化 及驱动力分析[J].干旱区研究,2021,38(3):843-854.[Wen Guangchao,Zhao Meijuan, Xie Hongbo,etal.Analysis of land vegetation cover evolution and driving forces in the western part of the li River Valley[J]. Arid Zone Research,2021,38(3): 843-854.]   
[37] 周亚军,刘廷玺,段利民,等.锡林河流域上游河谷湿地景观格 局演变及其驱动力[J].干旱区研究,2020,37(3):580-590. [Zhou Yajun,Liu Tingxi, Duan Limin, etal. Driving force analysis and landscape pattern evolution in the up stream valley of Xilin River Basin[J]. Arid Zone Research,2020,37(3): 580-590.]   
[38] 宋文,陈英.土地利用空间自相关分析中观测变量和衡量指标 的选择研究[J].干旱区资源与环境,2015,29(10):37-42.[Song Wen, Chen Ying.Selectionof observed variablesand measuring indicators for the land use spatial autocorrelation analysis[J]. Journal of Arid Land Resources and Environment,2O15,29(10): 37-42.]   
[39] 朱庆莹,陈银蓉,胡伟艳,等.中国土地集约利用与区域生态效 率耦合协调度时空格局[J].农业工程学报,2020,36(4):234- 243.[Zhu Qingying, Chen Yinrong,Hu Weiyan,et al. Spatiotemporal pattern of coupling coordination degree between land intensive use and regional ecological effciency in China[J]. Transactionsof the Chinese Societyof Agricultural Engineering,2020,36 (4): 234-243.]   
[40] 陈臻琦,张靖,张贻龙,等.基于VSD的近20 a来浑善达克沙地 生态脆弱性变化研究[J].干旱区研究,2021,38(5):1464-1473. [Chen Zhenqi, Zhang Jing,Zhang Yilong,et al. Spatio-temporal paternsvariation of ecological vulnerability in Otindag Sandy Land based on a vulnerability scoping diagram[J].Arid Zone Research,2021,38(5): 1464-1473.]   
[41]黄忠华,吴次芳,杜雪君.我国耕地变化与社会经济因素的实证 分析[J].自然资源学报,2009,24(2):192-199.[Huang Zhonghua,Wu Cifang,Du Xuejun.Empirical study of cultivated land change and social economic factors in China[J].Journal of Natural Resources,2009,24(2): 192-199.]   
[42] 王劲峰,徐成东.地理探测器:原理与展望[J].地理学报,2017, 72(1):116-134.[Wang Jinfeng,Xu Chengdong.Geographical detector: Principle and prospect[J]. Acta Geographica Sinica, 2017, 72(1): 116-134.]   
[43] 常梦迪,王新军,李娜,等.基于CSLE模型的天山北坡中段山 区水力侵蚀时空变化特征及影响因素研究[J].干旱区研究, 2021,38(4): 939-949.[Chang Mengdi, Wang Xinjun,Li Na, et al. Study on temporal and spatial variation characteristics and influencing factors of hydraulic erosion in the middle of the northern slope of Tianshan Mountains based on CSLE model[J].Arid Zone Research,2021,38(4): 939-949.]   
[44] 马亚兰,刘普幸,程英.甘肃省近30a来耕地空间动态变化与驱 动力分析[J].干旱区地理,2010,33(2):293-299.[Ma Yalan,Liu Puxing, Cheng Ying. Spatial dynamic variation and driving forces of cultivated land use in Gansu Province during the past 3O years [J]. Arid Land Geography,2010,33(2): 293-299.]   
[45] 齐鹏,王晓娇,陈英,等.甘肃河西地区耕地面积变化及利用效 益分析[J].甘肃农业大学学报,2015,50(3):132-137,149.[Qi Peng,Wang Xiaojiao, Chen Ying, et al. Comprehensive utilization benefit analysis on cultivated land change in Hexi Area[J]. Journal of Gansu Agricultural University,2015,50(3): 132-137,149.]   
[46] 丁海勇,丁昕玮.基于SPOT__NDVI的甘肃省植被覆盖变化及 其与气候、地形因子的关系[J].长江流域资源与环境,2020,29 (12): 2665-2678.[Ding Haiyong,Ding Xinwei. Vegetation cover change and its responses to climate and topography in Gansu Province based on SPOT NDVI[J]. Resources and Environment in the Yangtze Basin,2020,29(12): 2665-2678.]

# Analysis of cultivated land' s spatio-temporal changes and influencing factors in Gansu Province in recent 25 years

HOU Qingqing'， CHEN Ying1²， PEI Tingting²， JI Zhenxia³， XIE Baopeng² (1.College of Pratacultural Science,Gansu Agricultural University,Lanzhou 73Oo7o,Gansu,China;2.Collegeof Management,Gansu Agricultural University,Lanzhou 73oO7o,Gansu, China; 3.College of Resources and Environment, Gansu Agricultural University,Lanzhou 73oO7O,Gansu, China)

Abstract: Studying the temporal and spatial changes and driving factors of cultivated land resources have important practical significance for improving regional food security,strictly cultivated land protection red lines, and formulating cultivated land protection policies and measures.Based on the land use data of Gansu Province in 1995,2005,2015,and 2020, with the support of ArcGIS and GeoDa.This paper comprehensively analyzed the temporal and spatial evolution characteristics of cultivated land resources in Gansu Province in the recent 25 years from the grid,reseau,and county scale using geographic detectors to detect the main driving factors causing cultivated land changes.The results showed that (1) the cultivated land in Gansu Province was $1 . 6 \%$ from 1995 to 2020,increasing from 1995 to 2005 and decreasing from 2005 to 2020.The cultivated land mainly flowed to grassland,forest,andconstruction land,while the unused land mainly moved tocultivated land and grassland.(2) The spatial distribution of cultivated land showed the typical characteristics of“more in the southeast and less in the northwest.”(3)The spatial distribution of cultivated land was influenced by the interaction of natural and socio-economic factors.The interaction between population and land development intensity was the main reason for the difference in the spatial distribution of cultivated land in Gansu Province in 1995,2O05,and 2015. However,the interaction between temperature and precipitation has become the dominant factor affecting cultivated land in 2O20.Findings from this study can serve as a scientific basis for the protection and management of cultivated land in Gansu Province.

Keywords: land use； cultivated land; spatio-temporal evolution; driving factors； Gansu Province