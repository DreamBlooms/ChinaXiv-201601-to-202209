# 基于InVEST模型的1999—2016年麻塔流域碳储量变化及空间格局研究

刘冠¹²，李国庆2，李洁²，张艳如³，鲁奇²，杜盛23(1.西北农林科技大学林学院,陕西 杨凌712100；2.西北农林科技大学黄土高原土壤侵蚀与旱地农业国家重点实验室,陕西 杨凌712100；3.中国科学院水利部水土保持研究所,陕西 杨凌712100)

摘要：区域碳储量是生态系统功能的重要度量指标,探索土地改造对区域碳储量变化的影响,对于协调区域生态建设和生态产业发展具有重要意义。基于InVEST模型和地理信息系统技术,研究了陕西省延安南部麻塔流域1999—2016年土地结构改造过程中区域碳储量变化，并探讨坡度、坡向、坡位对碳储量空间分布的影响。结果表明：麻塔流域18a的土地改造使得区域碳储量增加 $1 6 8 8 . 3 6 ~ \mathrm { M g }$ （碳密度增加 $6 . 9 2 ~ \mathrm { M g \cdot h m } ^ { 2 }$ ，总固碳功能提升约$7 . 6 3 \%$ 。森林、草地和果园土地类型面积的增加是植被转换后流域景观碳储量提升的主要贡献者。碳储量增加的空间位置主要分布在半阴坡、中上坡位以及坡度 $1 0 ^ { \circ } { \sim } 3 0 ^ { \circ }$ 。本研究认为林草植被建设和经济果林建设两者都有利于增强麻塔流域景观固碳能力。麻塔流域土地转换模式能够协调区域生态建设和生态产业的发展,在黄土丘陵区具有较好的推广价值。

关键词：碳储量；空间格局；InVEST模型；生态系统服务；麻塔流域

生态系统固碳作为最重要的生态系统服务功能之一，对于降低大气中 $\mathrm { C O } _ { 2 }$ 等温室气体浓度、调节区域小气候、减缓全球气候变化以及维持生态平衡具有至关重要的作用[1-3]。近年来，对于生态系统碳储量及空间格局的研究，成为各国政府与国内外专家关注的焦点。因此，研究区域碳储量及其时空格局的变化对于自然资源管理和生态决策具有重要的参考价值与指导意义。

目前，碳储量估算方法多种多样，且具有尺度差异性[4]。对于中小尺度碳储量估算大多采用野外调查、仪器测量、数理统计等方法[5-6。但这类方法仅适用于中小尺度碳储量估算，费时费力，且研究结果呈静态，无法准确反映研究区碳储量的动态变化及空间格局[。大尺度的碳储量估算，一般基于RS 和GIS技术建立模型来研究[8]。InVEST模型是一种可量化多种生态系统服务功能的综合评估模型[9-10],已广泛用于多个地区,如美国[1],亚洲印度尼西亚[12]和非洲坦桑尼亚[13]等，及中国汶川地震灾区[14]、长江中下游平原[15]、北京山区[16]、祁连山保护区[等区域。因此，将ArcGIS与InVEST模型相结合，可更快速、简便、准确地估算区域碳储量及空间动态变化，并以地图形式直观展现出来。

黄土丘陵区是我国水土流失严重的区域，也是生态环境脆弱的区域之一。20世纪70年代以来的水土保持工程与1999年以来的退耕还林工程，极大地提升了该地区的植被覆盖度。国内外学者对黄土丘陵区植被固碳功能及其变化进行了大量研究，这些研究多数是聚焦于水土保持工程以及退耕还林工程的固碳效益[18]。然而,在当前新农村建设与生态农业等政策的驱动下，黄土丘陵区土地利用政策发生了明显的变化，过去种植的水土保持林正在被苹果(Maluspumila)等经济林替代,这种现象在延安周边地区尤其突出[19]。因此,探索如何量化经济果林建设对区域固碳能力的影响是当前亟待解决的一个科学问题。

本文以黄土丘陵区典型代表——延安麻塔流域为例，该流域从1999—2016年，苹果种植面积持续增加，在当前土地利用政策驱动下，为植被恢复方式的转变对区域固碳功能影响的研究提供了一个理想的对象。因此，本文试图通过InVEST模型研究该流域1999—2016年生态系统固碳能力及其在空间上的分配特征，探索流域生态系统固碳能力变化及其分布格局，以期为黄土丘陵区植被建设和生态产业的可持续发展提供科学依据

# 1研究区概况与研究方法

# 1.1 研究区概况

麻塔流域（ $( 1 0 9 . 5 2 6 8 ^ { \circ } \mathrm { N } , 3 6 . 4 6 9 5 ^ { \circ } \mathrm { E } )$ 位于陕西省延安市宝塔区南部(图1)，为典型的黄土丘陵地带。流域面积 $2 . 4 ~ \mathrm { k m } ^ { 2 }$ ,海拔 $1 1 8 5 { \sim } 1 3 7 9 \ \mathrm { m }$ ,夏季炎热,冬季寒冷干燥,为干旱半干旱气候,潜在蒸散为$5 4 4 ~ \mathrm { m m }$ ,年均气温在 $8 . 8 ~ \mathrm { { ^ { 8 } C } }$ 左右，年均降雨量523$\mathbf { m } \mathbf { m }$ ,全年降水主要集中在6—9月[20]。该流域土壤类型为黄绵土，主导产业为旱地苹果，为当地居民支柱产业。

![](images/c164ef55bac922d3d5befa715f437d6d0c49367d513ac1bbc66f350345dad0ed.jpg)  
图1麻塔流域位置及1999年和2016年土地利用类型Fig.1 Location of Mata Watershed and its land use types

# 1.2土地利用数据来源

麻塔流域土地利用图(1999年和2016年)是通过解译美国陆地卫星1999年8月Landsat7和2016年9月Landsat8影像的遥感数据获得。遥感影像选择Landsat7影像的1\~6波段；选择Landsat8影像的2\~7波段。获取的遥感波段经过地形校正、辐射定标、辐射校正，将它们的灰度值转换为地表反射率数值。2016年的土地利用图是通过野外调查195个地面点数据和处理后Landsat8影像的2\~7波段进行监督分类(随机森林算法)完成的，最终的预测准确率为 $7 4 \%$ (Kappa值为0.68)。1999年土地利用图是将上述训练的随机森林分类模型应用到1999年Landsat7影像1\~6波段上得到的预测结果。土地类型包括6类：林地、灌木、草地、果园、农田、其他(道路 $^ +$ 房屋 $+$ 裸地）。

由表1结果显示，森林主要转化为灌木、草地和果园;灌木主要转化为草地和果园;草地、农田及其他主要转化为果园。在6种土地利用类型中，森林、草地、果园的转入面积大于转出面积。而灌木、农田、其他的转入面积小于转出面积。1999年和2016年,整个流域6种土地利用类型中均为果园面积最大，1999年占总体面积的 $3 4 . 7 \%$ ,2016年占总体面积的 $4 7 . 4 \%$ 。

# 1.3流域碳储量及其估算

陆地生态系统碳储量主要包括地上生物碳储量（ $\dot { \left( { { C _ { \mathrm { a b o v e } } } } \right. }$ ）、地下生物碳储量（ $\scriptstyle \left( C _ { \mathrm { b e l o w } } \right)$ 、土壤碳储量（ $C _ { \mathrm { s o i l } , }$ ）、死亡有机碳储量( $\cdot  { C _ { \mathrm { d e a d } } } )$ 四部分。其中 $C _ { \mathrm { a b o v e } }$ 指地上所有存活植被，树枝、树干、树叶等中的碳储量； $C _ { \mathrm { b e l o w } }$ 指植物活性根系中的碳储量; $C _ { \mathrm { s o i l } }$ 指矿质土壤和有机土壤中的碳储量; $C _ { \mathrm { d e a d } }$ 包括死亡植被或凋落物中的碳储量。碳储量计算公式为：

表11999—2016年麻塔流域土地利用类型面积转移矩阵  
Tab.1 Area transfer matrix of land use types in Mata Watershed from1999 to 201   
/hm²   

<html><body><table><tr><td rowspan="2">1999年</td><td colspan="7">2016年</td></tr><tr><td>森林</td><td>灌木</td><td>草地</td><td>果园</td><td>农田</td><td>其他</td><td>合计</td></tr><tr><td>森林</td><td>5.21</td><td>2.07</td><td>1.96</td><td>1.94</td><td>0.27</td><td>0.15</td><td>11.60</td></tr><tr><td>灌木</td><td>7.53</td><td>15.23</td><td>17.96</td><td>26.32</td><td>3.08</td><td>6.66</td><td>76.78</td></tr><tr><td>草地</td><td>0.83</td><td>1.06</td><td>4.99</td><td>10.37</td><td>1.55</td><td>2.66</td><td>21.46</td></tr><tr><td>果园</td><td>6.10</td><td>8.59</td><td>20.43</td><td>43.07</td><td>2.68</td><td>3.27</td><td>84.14</td></tr><tr><td>农田</td><td>0.11</td><td>0.53</td><td>3.38</td><td>12.01</td><td>1.28</td><td>1.85</td><td>19.16</td></tr><tr><td>其他</td><td>0.15</td><td>0.35</td><td>5.86</td><td>21.26</td><td>1.05</td><td>0.67</td><td>29.34</td></tr><tr><td>合计</td><td>19.93</td><td>27.83</td><td>54.58</td><td>114.97</td><td>9.91</td><td>15.26</td><td>242.48</td></tr></table></body></html>

$$
C _ { _ { \mathrm { \scriptsize { t o t a l } } } } = C _ { _ { \mathrm { \scriptsize { a b o v e } } } } + C _ { _ { \mathrm { \scriptsize { b e l o w } } } } + C _ { _ { \mathrm { \scriptsize { s o i l } } } } + C _ { _ { \mathrm { \scriptsize { d e a d } } } }
$$

式中： $C _ { \mathrm { t o t a l } }$ 表示总碳储量（ $\mathrm { \langle M g \rangle }$ ; $C _ { \mathrm { a b o v e } }$ 表示地上生物碳储量 $( \mathrm { M g } ) ; C _ { \mathrm { b e l o w } }$ 表示地下生物碳储量 $( \mathrm { M g } ) { \ ; } C _ { \mathrm { s o i l } }$ 表示土壤碳储量 $\left( \mathrm { M g } \right)$ ； $C _ { \mathrm { d e a d } }$ 表示死亡有机碳储量 $( \mathbf { M } \mathbf { g } )$ 。各种参数通过不同文献搜集获取[21-29],具体结果如表2。

本研究采用InVEST3.4软件（TheIntegrateVal-uationofEcosystem ServicesandTradeoffs Tool)进行碳储量的估算，它是由美国斯坦福大学、大自然保护协会和世界自然基金会联合开发的开源式生态系统服务功能评估模型，是一种整合自然资本作为决策依据的先进工具[30-31]

# 1.4不同地形因子对碳储量的影响

坡度、坡向和坡位通常是表述地形因子的3个主要指标。麻塔流域坡度范围为 $0 ^ { \circ } \sim 3 6 . 6 3 ^ { \circ }$ ,为分析不同坡度范围碳储量及其变化,将坡度分为 $0 ^ { \circ } { \sim } 5 ^ { \circ }$ 、

$5 ^ { \circ } \sim 1 0 ^ { \circ } \ , 1 0 ^ { \circ } \sim 1 5 ^ { \circ } \ , 1 5 ^ { \circ } \sim 2 0 ^ { \circ } \ , 2 0 ^ { \circ } \sim 2 5 ^ { \circ } \ , 2 5 ^ { \circ } \sim 3 0 ^ { \circ } \ , > 3 0 ^ { \circ } \$ 等级；为分析不同坡向碳储量及其变化，将坡向按照光照由弱到强分为阴坡、半阴坡、半阳坡、阳坡，即流域按照自正北方向 $0 ^ { \circ }$ ，顺时针旋转到正南方为$1 8 0 ^ { \circ }$ ,总体1周为 $0 ^ { \circ } \sim 3 6 0 ^ { \circ }$ ,其中 $0 ^ { \circ } { \sim } 4 5 ^ { \circ }$ 与 $3 1 5 ^ { \circ } { \sim } 3 6 0 ^ { \circ }$ 合称为阴坡， $4 5 ^ { \circ } { \sim } 9 0 ^ { \circ }$ 与 $2 7 0 ^ { \circ } { \sim } 3 1 5 ^ { \circ }$ 合称为半阴坡，$9 0 ^ { \circ } \sim 1 3 5 ^ { \circ }$ 与 $2 2 5 ^ { \circ } { \sim } 2 7 0 ^ { \circ }$ 合称为半阳坡， $1 3 5 ^ { \circ } { \sim } 2 2 5 ^ { \circ }$ 合称为阳坡;整个流域海拔范围为 $1 1 8 5 { \sim } 1 3 7 9 \ \mathrm { m }$ ,为分析不同坡位的碳储量及其变化，依据海拔范围等间距的将坡位划分为3个梯度，其中海拔 $1 1 8 5 { \sim } 1 2 5 0 \mathrm { m }$ 称为下坡位、海拔 $1 2 5 0 { \sim } 1 3 1 5 \ \mathrm { m }$ 称为中坡位、海拔 $1 3 1 5 \sim$ $1 3 7 9 \mathrm { ~ m ~ }$ 称为上坡位。用ArcMap10.6绘制麻塔流域碳储量空间格局图，用R软件中raster包分析不同地形因子对碳储量的影响，并进行相关的统计作图。

# 2结果与分析

# 2.1不同时期流域碳储量格局及其变化特征

由图2可知，1999年生态系统总碳储量为

表2麻塔流域土地利用固碳参数(碳密度)  
Tab.2 Carbon parameter for land use type in the Mata Watershed (carbon density   

<html><body><table><tr><td>土地利用类型</td><td>编码</td><td>地上生物碳密度 /(Mg·hm2)</td><td>地下生物碳密度 /(Mg·hm2)</td><td>土壤碳密度 /(Mg·hm²)</td><td>死亡有机碳密度 /(Mg·hm2)</td></tr><tr><td>森林</td><td>1</td><td>44.60</td><td>11.10</td><td>106.10</td><td>1.90</td></tr><tr><td>灌木</td><td>2</td><td>7.59</td><td>4.00</td><td>80.50</td><td>0.80</td></tr><tr><td>草地</td><td>3</td><td>1.34</td><td>10.07</td><td>85.40</td><td>0.45</td></tr><tr><td>果园</td><td>4</td><td>14.10</td><td>5.60</td><td>76.00</td><td>0.03</td></tr><tr><td>农田</td><td>5</td><td>3.00</td><td>0.68</td><td>76.83</td><td>0.07</td></tr><tr><td>其他</td><td>6</td><td>0.00</td><td>0.00</td><td>40.90</td><td>0.00</td></tr></table></body></html>

![](images/4b085f993c95d1b8a8dc0086528f5a736b8a61b01cb0b3b497cf670848e04327.jpg)  
图21999年和2016年碳储量空间格局及1999—2016年碳储量变化  
Fig.2Spatial pattern of carbon storage in Mata Watershed in the year of 1999 and 2O16 and carbon storage change between 1999 and 2016

$2 2 1 2 0 . 2 5 ~ \mathrm { M g }$ （碳密度为 $9 0 . 6 6 ~ \mathrm { M g \cdot h m } ^ { 2 } ,$ 。2016年生态系统总碳储量为 $2 3 8 0 8 . 6 1 ~ \mathrm { M g }$ （碳密度为97.58$\mathbf { M g } \cdot \mathbf { h m } ^ { 2 } .$ )。总体来看，1999—2016年，麻塔流域总碳储量增加 $1 6 8 8 . 3 6 \mathrm { M g }$ （碳密度增加 $6 . 9 2 ~ \mathrm { M g \cdot h m ^ { 2 } }$ ，总固碳功能提升约 $7 . 6 3 \%$ 。流域生态系统碳储量的增加主要位于流域的南部地区。

# 2.2不同土地利用类型的碳储量及其变化特征

1999一2016年间，麻塔流域土地利用类型的转换导致各土地利用的碳储量变化较为剧烈(图3）。其中，森林、草地、果园碳储量有增加的趋势，这3种土地利用类型的碳储量总体提升约 $7 4 8 4 . 6 2 ~ \mathrm { M g }$ ,其中森林占总提升的 $1 7 . 7 2 \%$ ，草地占总提升的$4 2 . 5 7 \%$ ,果园提升占总体提升的 $3 9 . 7 1 \%$ ;而灌木、农田和其他土地利用从1999—2016年的碳储量减少了 $5 7 9 6 . 2 7 ~ \mathrm { M g }$ ,其中灌木减少最多，占总体减少的$7 6 . 0 1 \%$ 。这表明森林、草地和果园土地利用类型是1999一2016年麻塔流域土地利用转换后流域景观碳储量提升的主要贡献者。

![](images/e380b25d2927aed3daabce7f636befde719c83fed2e6745cbcba77f8940f7450.jpg)  
图31999年和2016年麻塔流域不同土地利用类型碳储量Fig.3Carbon storage of different land use types in 1999 and2016in Mata Watershed  
图4麻塔流域地形因子对碳储量的影响Fig.4Influence of topography factors on carbon storage inMataWatershed

# 2.3地形因子对碳储量及其变化的影响

麻塔流域7个坡度等级梯度碳储量及其变化的结果表明(图4a)，1999—2016年该流域碳储量呈先增加后减小的趋势，且碳储量主要位于坡度 $0 ^ { \circ } { \sim } 2 5 ^ { \circ }$ 之间（占整个流域总碳储量的 $9 0 \%$ 左右)，其中 $1 0 ^ { \circ } \sim$ $1 5 ^ { \circ }$ 坡度范围内总碳储量最高。从1999—2016年间，碳储量增加较大的区域主要位于 $1 0 ^ { \circ } { \sim } 3 0 ^ { \circ }$ ,该坡度范围内占据总体碳储量提升比例的 $9 6 . 7 8 \%$ ，其他坡度在过去提升不明显或略微降低（如 $0 ^ { \circ } { \sim } 5 ^ { \circ }$ )，这表明坡度 $1 0 ^ { \circ } { \sim } 3 0 ^ { \circ }$ 是土地利用结构改造和固碳功能提升的主要地形位置。

麻塔流域不同坡位的碳储量分布格局及其变

(a)坡度 :1999年  
8000 :2016年  
400000\~5° 5\~10°10\~15°15\~20°20\~25°25\~30°>30°坡度(b)坡位 12000 (c)坡向 201年  
8000 8000  
4000 40000 0下坡位 中坡位 上坡位 阴坡 半阴坡 半阳坡 阳坡坡位 坡向

化的结果显示(图4b)，无论在1999年还是2016年，流域生态系统碳储量主要分布在下坡位和中坡位，上坡位占有比例较小。在不同坡位上，1999—2016年碳储量提升主要在中坡位和上坡位（提升了$2 3 5 4 . 0 7 ~ \mathrm { M g }$ ），而下坡位碳储量降低（下降了665.71$\mathbf { M } \mathbf { g } ^ { \mathbf { \sigma } }$ ),这说明麻塔流域在18a的土地利用结构改造过程中，中坡位和上坡位是碳储量增长的主要贡献地形部位。

1999—2016年麻塔流域总碳储量在不同坡向的分布格局表明（图 $4 \mathrm { c }$ ),碳储量的提升主要处于半阴坡，而其他坡向对碳储量提升较小或基本保持稳定（如阳坡）。1999—2016年，麻塔流域半阴坡提升碳储量的比例占总体提升的比例的 $7 0 . 7 1 \%$ ,表明半阴坡是土地利用转换和固碳功能提升的主要地形位置。

# 3讨论

# 3.11999—2016年麻塔流域碳储量的变化及其政策解释

本研究基于RS和GIS的手段，利用InVEST模型评估了1999—2016年麻塔流域土地利用转换后流域整体固碳能力及其变化。研究表明：经过18a的土地利用改造，流域整体固碳功能提升约$7 . 6 3 \%$ 。在此期间，将农田、灌丛和裸地土地利用类型改造为森林、草地和果园土地利用类型是流域景观碳储量提升的主要直接原因，尤其是流域上游地区(南部)的森林面积增加和流域中下游果园面积

的增加(图1)。

森林、草地和果园的面积增加主要发生在坡度$1 0 ^ { \circ } { \sim } 3 0 ^ { \circ }$ 、中上坡位的半阴坡，从而直接导致了流域整体碳储量的增加。驱动麻塔流域土地利用变化的社会原因主要是当地的退耕还林(1999年开始）政策和近年来的生态农业政策。在植被建设过程中，大量的农田、灌丛和裸地被改造为林地、草地和果园[32]。本研究说明了退耕还林工程过程中将农田、灌木和裸地等土地转换为林地有利于麻塔流域生态系统的固碳，更重要的是本文发现果园也是麻塔流域景观碳储量提升主要植被类型，这在之前大量的关于该地区退耕还林工程的固碳效益方面研究很少涉及[33]。近年来，在当前新农村建设与生态农业等政策的驱动下，将延安周边地区的水土保持林地和耕地改造为果园地的工作逐渐展开。本研究以麻塔流域为案例，证明了退耕还果政策与退耕还林政策相似，也有利于增强该地区流域景观的固碳效益。

虽然退耕还林(草)和退耕还果政策能够驱动麻塔流域景观碳储量的提升，但提升的幅度并不是很高，这主要的因为以麻塔流域为代表的黄土丘陵区为干旱、半干旱区，生态系统潜在固碳能力相对于其他湿润地区较低。例如麻塔流域2016年的平均碳密度为 $9 7 . 5 8 ~ \mathrm { M g \cdot h m } ^ { 2 }$ （根据流域面积和碳储量计算得到),低于广西西江流域 $^ { [ 3 4 ] } ( 1 8 6 . 9 9 \mathrm { M g } \cdot \mathrm { h m } ^ { 2 } )$ ）贵州晴隆[35] $( 1 7 3 . 1 ~ \mathrm { M g } \cdot \mathrm { h m } ^ { 2 } )$ 、太行山淇河流域[36]（ $1 4 1 . 9 ~ \mathrm { M g \cdot h m ^ { 2 } } ,$ ）、河北黄驿[28] $( 1 1 2 . 3 4 ~ \mathrm { M g } \cdot \mathrm { h m } ^ { 2 } )$ 等地区。

# 3.2不确定性分析及其实践意义

本研究是基于InVEST模型来评估1999—2016年麻塔流域碳储量及其变化。该模型内在的假设认为生态系统的各组分的碳密度在时间尺度上是保持不变的[9。随着植被的生长，生态系统各组分的碳密度可能会持续增加。同时，InVEST模型也没有考虑人对农田和果园的管理措施可能会提高生态系统的固碳潜力。因此，评估中采用固定不变的碳密度值可能会低估麻塔流域碳储量的潜力。

虽然，本研究并不能准确的估算麻塔流域碳储量的变化，但我们认为本研究能够反映麻塔流域过去18a土地利用转换后碳储量的变化趋势，并能够帮助我们在空间尺度上寻找碳储量增加的区域，并获得有效的土地利用转换策略信息。例如流域碳储量在坡度、坡向和坡位梯度上的分析表明，坡度$1 0 ^ { \circ } { \sim } 3 0 ^ { \circ }$ 、半阴坡和中上坡位是麻塔流域碳储量增长的主要贡献地形部位。这意味着麻塔流域在这些地形部位的土地利用转换策略(转换为林地或果园地)有利于生态固碳效益的提升，适合于广泛的推广。

2016年的麻塔流域土地利用图显示这些地形部位主要种植了果园(以苹果为主），经济果园林与水土保持林相比，经济果园林固碳能力虽弱于水土保持林地，但强于农田、草地和灌木地。过去的农田、草地和灌木地被转换为果园是麻塔流域整体碳储量提升的主要原因。

除了考虑其生态固碳效益之外，经济果园林带来的经济效益不容忽视，只有保障农民经济收益，才能使水土保持与生态修复工程更加长远和持久。近20a来，旱地苹果为麻塔流域居民的支柱产业，近年来扶贫政策的提出，政府对麻塔流域苹果产业的重视,形成一系列完善的制度和政策，使该流域果园面积不断增加。经济果林面积的持续增加及其综合优化配置，将是未来黄土丘陵区水土保持及经济发展的趋势，也必将成为黄土高原未来发展的一大特色。增强该地区经济果林的固碳效益，使其能够达到水土保持林的水平，使生态与经济效益最大化，未来还有更多的研究要做。

# 4结论

（1）麻塔流域过去18a的植被结构改造中（主要是苹果林建设），区域植被总体碳储量提升了$7 . 6 3 \%$ ，森林、草地和果园面积的急剧增加是碳储量增加的直接原因(其中果园贡献 $3 9 . 7 1 \%$ )。

(2）退耕还果与退耕还林政策对麻塔流域的固碳功能的影响具有相似的效益，有利于增强该地区流域景观的固碳能力。

（3）麻塔流域碳储量提升主要位于半阴坡、中上坡位以及坡度 $1 0 ^ { \circ } { \sim } 3 0 ^ { \circ }$ ，说明了麻塔流域在该地形部位的土地利用转换模式(转换为林地或果园地)具有较好的推广价值。

(4）经济果林面积的持续增加及其综合优化配置，将是未来黄土丘陵区水土保持及经济发展的趋势，增强该地区经济果林的固碳效益，使其能够达到水土保持林的水平，将能够使该地区的生态与经济效益最大化。

# 参考文献(References):

[1]Piao SL,Fang JY,Ciais P,etal.The carbon balance of terrestrial ecosystems in China[J]. Nature,2009,458(7241): 1009-1013.   
[2]方精云,于贵瑞,任小波,等.中国陆地生态系统固碳效应：中国 科学院战略性先导科技专项"应对气候变化的碳收支认证及 相关问题"之生态系统固碳任务群研究进展[J].中国科学院院 刊,2015,30(6): 848-857,875.[Fang Jingyun, Yu Guirui, Ren Xiaobo,et al. Carbon sequestration in China's terrestrial ecosystems under climatechange: Progress on ecosystem carbon sequestration from the CAS strategic priority research program[J]. Buletin of the Chinese Academy of Sciences,2015,30(6): 848-857,875.]   
[3]戴尔阜,黄宇,吴卓,等.内蒙古草地生态系统碳源/汇时空格局 及其与气候因子的关系[J].地理学报,2016,71(1):21-34.[Dai Erfu,Huang Yu,Wu Zhuo,et al. Spatial-temporal features of carbon source-sink and its relationship with climate factors in Inner Mongolia grassland ecosystem[J]. Acta Geographica Sinica, 2016, 71(1): 21-34.]   
[4]Han Y W, Zhang S, Yin L H. Quantifying the carbon storage capacity and its spatial distribution patterns of green spaces in a metropolitan area: A case studyof Seoul,South Korea[J]. Landscape Architecture Frontiers,2019,7(2): 55-65.   
[5]Oubrahim H,Boulmane M,Bakker MR,et al.Carbon storage in degraded cork oak (Quercus suber) forests on flat lowlands in Morocco[J]. Forest-Biogeosciences and Forestry,2015,9(1): 125-137.   
[6]张景群,苏印泉,康永祥,等.黄土高原刺槐人工林幼林生态系 统碳吸存[J].应用生态学,2009,20(12):2911-2916.[Zhang Jingqun,Su Yinquan,Kang Yongxiang,et al. Carbon sequestration of young Robinia pseudoacacia plantation in Loess Plateau[J]. Chinese Journal of Applied Ecology,2009,20(12): 2911-2916.]   
[7]LiFC,Zhang JH,Su ZG,et al. Simulation and $^ { 1 3 7 }$ Cs tracer show tillage erosion translocating soil organic carbon,phosphorus,and potassium[J]. Journal of Plant Nutrition and Soil Science,2013, 176:647-654. DOI: 10.1002/jpln.201200341.   
[8]张云倩,张晓祥,陈振杰,等.基于InVEST模型的江苏海岸带生 态系统碳储量时空变化研究[J].水土保持研究,2016,23(3): 100-105.[Zhang Yunqian, Zhang Xiaoxiang, Chen Zhenjie, et al. Research on the spatiotemporal variation of carbon storage in coastal zone ecosystem of Jiangsu based on InVEST model[J]. Research of Soil and Water Conservation,2016,23(3): 100-105.]   
[9]Richard S,Rebecca C K, Spencer W,et al. InVEST 3.2.0 User's Guide[M].Stanford: Natural Capital Project,Stanford University, University Nature Conservancy,World Wildlife Fund,2015.   
[10]Rebecca C K, Sharp RP,Mandle L,et al. Spatial patterns of agricultural expansion determine impacts on biodiversity and carbon storage[J]. Proceedings of the National Academy of Sciences of the United States of America,2015,112(24): 7402-7407.   
[11]Goldstein JH, Caldarone G,Duarte T K,et al. Integrating ecosystem-service tradeoffs into land-use decisions[J].Proceedings of the National Academy of Sciences of the United States of America, 2012,109(19): 7565-7570.   
[12]Bhagabati NK,Rickets T,Sulistyawan TB S,etal. Ecosystem services reinforce Sumatran tiger conservation in land use plans [J].Biological Conservation,2014,169(387): 147-156.   
[13]Fisher B,Turner R K, Burgess N D,et al. Measuring, modeling and mapping ecosystem services in the Eastern Arc Mountains of Tanzania[J]. Progressin Physical Geography2011,35(5):595- 611.   
[14]彭怡.InVEST模型在生态系统服务功能评估中的应用研究 -以四川汶川地震灾区为例[D].成都:中国科学院水利部山 地灾害与环境研究所,2010.[Peng Yi.Application of InVEST Model in Ecosystem Services Assessment: A Case Study from Wenchuan Earthquake Area A bstract[D]. Chengdu: Institute of Mountain Hazards and Environment Chinese Academy of Sciences & Ministry Water Conservancy,2010.]   
[15]吕一河,胡健,孙飞翔,等.水源涵养与水文调节:和而不同的陆 地生态系统水文服务[J].生态学报,2015,35(15):5191-5196. [Lyu Yihe,Hu Jian,Sun Feixiang,etal.Water retention and hydrological regulation: Harmony but not the same in terrestrial hydrological ecosystem services[J].Acta Ecologica Sinica, 2015,35 (15): 5191-5196.]   
[16] 杨芝歌,周彬,余新晓,等.北京山区生物多样性分析与碳储量 评估[J].水土保持通报,2012,32(3):42-46.[Yang Zhige,Zhou Bin, Yu Xinxiao, et al. Biodiversity analysis and carbon storage assessments in Beijing mountainous areas[J].Bulletin of Soil and Water Conservation,2012,32(3): 42-46.]   
[17] 陈童尧,贾燕锋,王佳楠,等.基于InVEST模型的祁连山国家级 自然保护区土壤保持现状与功能[J].干旱区研究,2020,37(1): 150-159.[Chen Tongyao,Jia Yanfeng,Wang Jianan,et al. Current situation and function of soil conservation in national nature reserves in the Qilian Mountains based on InVEST model[J]. Arid Zone Research, 2020,37(1): 150-159.]   
[18] Spencer C N, Matzner SL, Smalley J,et al. Forest expansion and soil carbon changes in the Loess Hills of Eastern South Dakota[J]. American Midland Naturalist,2009,161(2): 273-285.]   
[19] 李泽,郭胜利,张芳,等.退耕还果对黄土高原沟壑区坡地土壤 和植被碳、氮储量的影响[J].植物营养与肥料学报,2011,17 (4): 919-924.[LiZe,Guo Shengl,ZhangFang,etalEfectsofaple orchard converted from cropland on C and N storages in terrestrial system of slopping cultivated land in the Loess Gully Regions [J].Plant Nutrition and Fertilizer Science,2011,17(4): 919-924.]   
[20] 李国庆,温仲明,杜盛.延安麻塔流域植被对土壤侵蚀的控制效 率研究[J].国土与自然资源研究,2019(6): 64-68.[Li Guoqing, Wen Zhongming,Du Sheng.Study on the control efficiency of vegetation on soil erosion in Mata Watershed of Yanan City[J].Territory & Natural Resources Study,2019(6): 64-68.]   
[21] 刘涛.宁南黄土丘陵 26年生主要人工灌木林碳密度及其分配

特征[J].安徽农业科学,2018,46(4):103-105.[Liu Tao.Carbon density and its allocation characteristics of 26-year- old major shrub plantations in Hilly Loess Plateau,South Ningxia[J]. Journal of Anhui Agricultural Sciences,2018,46(4): 103-105.]   
[22] 张娜,梁一民.黄土丘陵区天然草地地下/地上生物量的研究 [J].草业学报,2002,11(2): 72-78.[Zhang Na,Liang Yimin. Studies on the below-ground/above-ground biomass ratio of natural grassland in Loess Hilly region[J]. Acta Prataculturae Sinica, 2002,11 (2): 72-78.]   
[23] 艾泽民,陈云明,曹扬.黄土丘陵区不同林龄刺槐人工林碳、氮 储量及分配格局[J].应用生态学报,2014,25(2):333-341.[Ai Zemin, Chen Yunming,Cao Yang. Storage and allocation of carbon and nitrogen in Robinia pseudoacacia plantation at different ages in the Loess Hilly region, China[J]. Chinese Journal of Applied Ecology,2014,25(2): 333-341.]   
[24]程积民,程杰,杨晓梅,等 黄土高原草地植被碳密度的空间分 布特征[J].生态学报,2012,32(1):226-237.[Cheng Jimin, Cheng Jie,Yang Xiaomei,et al.Spatial distributionof carbon density in grassland vegetation of the Loess Plateau of China[J].Acta Ecologica Sinica, 2012,32(1): 226-237.]   
[25] 高阳,马虎,程积民,等.黄土高原半干旱区不同封育年限草地 生态系统碳密度[J].草地学报,2016,24(1):28-34.[Gao Yang, Ma Hu,Cheng Jimin,et al. Ecosvstem carbon density of grasslands under diferent grazing exclusion ages in semiarid region of the Loess Plateau[J]. Acta Agrestia Sinica, 2016,24(1): 28-34.]   
[26] 杨晓梅,程积民,孟蕾.黄土高原天然柴松林碳储量与碳密度特 征[J].中国水土保持科学,2010,8(2):41-45,58.[Yang Xiaomei, Cheng Jimin,Meng Lei. Carbon storage and density features of natural forest of Pinus tabulaeformis fshekannesis in Loess Plateau[J]. Soil and Water Conservationu,2010,8(2): 41-45,58.]   
[27] 李克让,王绍强,曹明奎.中国植被和土壤碳贮量[J].中国科学: 地球科学,2003,33(1): 72-80.[Li Kerang,Wang Shaoqiang,Cao Mingkui. Vegetation and soil carbon storage in China[J]. Science China Earth Sciences,2003,33(1): 72-80.]   
[28] 刘建华,许,王耀,等.基于土地利用格局变化的生态风险与 固碳功能评价——以河北省黄骅市为例[J].中国生态农业学 报,2018,26(8): 1217-1226.[Liu Jianhua, Xu Hao,Wang Yao,et al.Evaluation of ecological risk and carbon fixation from land use change: A case study of Huanghua City,Hebei Province[J]. Chinese Journal of Eco-Agriculture,2018,26(8): 1217-1226.]   
[29]Tang XL, Zhao X,Bai YF,et al. Carbon pools in China's terrestrial ecosystems:New estimates based on an intensive field survey [J].Proceedings of the National Academy of Sciences of the United States of America,2018,115(16). DOI: 10.1073/pnas.1700291115. [30] Cozarab A,Ferratic R,Garciaa C M,et al.Human-threatened ecosystem: New signs of groundwater connection between Yacyreta reservoir and Ibera wetland (South America)[J]. Science of the Total Environment,2005,337(1): 281-286. [31] 李双成,张才玉,刘金龙,等.生态系统服务权衡与协同研究进 展及地理学研究议题[J].地理研究,2013,32(8):1379-1390. [Li Shuangcheng,Zhang Caiyu,Liu Jinlong,et al. The tradeoffs and synergies of ecosystem services: Research progress,development trend,and themes of geography[J]. Geographical Research,   
2013,32(8): 1379-1390.] [32] 王森,王海燕,谢永生,等.延安市退耕还林前后土壤保持生态 服务功能评价[J].水土保持研究,2019,26(1):280-286.[Wang Sen,Wang Haiyan, Xie Yongsheng, etal. Evaluation of ecological service function of soil conservation before and after grain for green project in Yan'an City[J].Research of Soil and Water Conservation,2019,26(1): 280-286.] [33] 邓元杰,姚顺波,侯孟阳,等.退耕还林还草工程对生态系统碳 储存服务的影响——以黄土高原丘陵沟壑区子长县为例[J]. 自然资源学报,2020,35(4):826-844.[Deng Yuanjie,Yao Shunbo,Hou Mengyang,et al. Assessing the effects of the green for grain program on ecosystem carbon storage service by linking the InVEST and FLUS models: A case study of Zichang county in hilly and gully region of LoessPlateau[J]. Journal of Natural Resources,2020,35(4): 826-844.] [34]荣检.基于InVEST模型的广西西江流域生态系统产水与固碳 服务功能研究[D].南宁:广西师范学院,2017.[Rong Jian.Water Yield and Carbon Storage Ecosystem Services Evaluation of Xijiang River Basin in Guangxi based on InVEST model[D]. Nanning: Teachers Education University,2017.] [35] 张斯屿,白晓永,王世杰,等.基于InVEST模型的典型石漠化地 区生态系统服务评估——以晴隆县为例[J].地球环境学报,   
2014,5(5): 328-338.[Zhang Siyu,Bai Xiaoyong,Wang Shijie,et al.Ecosystem services evaluation of typical rocky desertification areas based on InVEST model: A case study at Qinglong Country, Guizhou Provice[J]. Journal of Earth Environment,2014,5(5):   
328-338.] [36] 朱文博,张静静,崔耀平,等.基于土地利用变化情景的生态系 统碳储量评估——以太行山淇河流域为例[J].地理学报,   
2019,74(3): 40-53.[Zhu Wenbo,Zhang Jingjing, Cui Yaoping,et al.Assessment of territorial ecosystem carbon storage based on land use change scenario: A case study in Qihe River Basin[J]. Acta Geographica Sinica,2019,74(3): 40-53.]

# Study on change in carbon storage and its spatial pattern in Mata Watershed from 1999 to 2016 based on InVEST model

LIU Guan'²，LI Guoqing2³，LI Jie²，ZHANG Yanru³，LUQi'²，DU Sheng²,3   
(1.College ofForestry,NorthwestA&FUniversityYangling7121Oo,Shaanxi,China;2.StateKeyLaboratoryof   
SoilErosion andDryland Farmingon the Loess Plateau,Northwest A&F University,Yangling 7121o,Shaanxi, China; 2.Institute of Soil and Water Conservation,Chinese Academy of Sciences and Ministry of Water Resources,Yangling 7121Oo, Shaanxi, China)

Abstract: The soil and water conservation forests in the areas surrounding Yan'an city are being replaced by economic forests such as orchard,which willdefinitely have an impact on the regionalcarbon storage.Therefore, it is necessry to determine a method to quantify the impact of orchard construction on the regional carbon storage capacity.Based on the InVEST model and ArcGIS platform,this study evaluated the change in carbon storage in the Mata Watershed in southern Yan'an from 1999 to 2016,and explored the influence of slope,slope aspect,and slope position on the spatial distribution of change in carbon storage.The results showed that the carbon storageofforest,grassland,and orchard has increased,whereas thatof shrub,cropland,and other lands has declined during the18 years of vegetationand reconstruction in the Mata Watershed (mainly orchard construction). The regional total carbon storage has increased by $7 . 6 3 \%$ , of which $3 9 . 7 1 \%$ has been contributed by orchard.The increase in spatial position of carbon storage was mainly located in half-shaded-slopes, midle, and top of slopes; as well as slopes with range of $1 0 ^ { \circ } - 3 0 ^ { \circ }$ . This study provides a methodological case study for quantifying the impact of economic forest construction on regional carbon storage function in the loesshilly region.

Keywords: carbon storage; spatial pattern; InVEST model; ecosystem services； Mata Watershed