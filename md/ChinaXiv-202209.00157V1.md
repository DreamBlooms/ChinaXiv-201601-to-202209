# 基于PLUS-SD耦合模型的黑河流域中游甘临高地区土地利用研究

蒋小芳¹²，段翰晨¹，廖杰3，宋翔¹³，薛娴1,3

1.中国科学院西北生态环境资源研究院 沙漠与沙漠化重点实验室，甘肃 兰州73000；2.中国科学院大学，北京100049；3.中国科学院西北生态环境资源研究院干旱区盐渍化研究站，甘肃 兰州730000)

摘要：土地利用/覆被变化(Land Use and Cover Change,LUCC)是全球环境变化的重要组成部分。数量-空间耦合模型因能有效模拟土地利用斑块数量及其在空间上的快速变化，成为近年来土地利用研究的主要手段。本研究首先对比斑块生成土地利用变化模拟模型(Patch-Generating Land Use Simulation Model,PLUS）、未来土地利用模型(Future Land Use Simulation Model,FLUS)和小尺度土地利用变化及其空间效益模型(ConversionofLand Useand ItsEffects at Small Regional Extent,CLUE-S)模拟2015年黑河流域中游甘临高地区(张掖市甘州区、临泽县和高台县)土地利用结构,筛选出最适合研究区的空间模拟模型;然后将其与系统动力学模型(System Dynamics,SD)进行耦合，形成数量-空间耦合模型;最后利用耦合模型预测 2030年研究区在经济发展(Economic Development,ED）、生态保护(Ecological Protection,EP)和协调发展(Harmonious Development,HD)情景下的土地利用结构,并进行对比评价。研究结果表明:（1）在同一像元尺度下,PLUS模型的质量系数(Figureof Merit,FoM)高于FLUS和CLUE-S模型,且3个模型的数量Kappa系数 $\left( K _ { \mathrm { n o } } \right)$ 和位置Kappa系数 $\left( K _ { \mathrm { l o c a t i o n } } \right)$ 从高至低为:PLUS、CLUE-S和FLUS模型,说明PLUS模型在本研究区的空间拟合效果最优;（2)PLUS-SD耦合模型预测的不同情景表明,ED情景中建设用地和耕地迅速扩张但森林覆盖率较低,EP情景中的森林覆盖率明显提高，但经济发展水平偏低,HD情景中城市化水平提高的同时生态环境呈良性发展。本研究验证了PLUS-SD耦合模型的显著优势,凸显了PLUS模型有效的土地利用空间模拟能力与SD模型强大的数据处理功能。该结果可为土地规划政策的制定提供参考。

关键词：黑河流域中游；耦合模型；土地利用/覆被变化；情景预测

20世纪90年代土地利用结构变化问题开始受到关注，现已成为LUCC研究的热点。LUCC模型是研究土地利用动态变化的重要手段，根据各种模型的优势可以分为数量模拟模型、空间模拟模型及耦合模型[2-5]。数量模拟模型主要包括 SD(SystemDynamics）、GF(Gray Forecast)和MC(Markov Chain)等模型,这类模型能有效地模拟和预测土地利用类型的数量结构,但难以实现空间结构模拟[6-8]。空间模拟模型有CA（Cellular Automaton）、CLUE-S(Conversion of Land Use and Its Effects at Small Re-gional Extent）、FLUS（Future Land Use SimulationModel）、ABM（Agent-Based Model)和PLUS（Patch-

GeneratingLandUseSimulationModel)等模型,它们均可用于模拟地类的空间布局,但在数量模拟方面存在不足[9-]。耦合模型旨在集合多个模型的优势,提高了单一模型的模拟精度，为土地利用研究提供有力保障[12-14]

目前，用于土地利用/土地覆盖变化模拟的几种耦合模型主要是通过数量模型得到各地类的数量结构，然后用空间模型得到未来不同情景下的空间布局。He等[15以成都市为研究区，运用SD模型在宏观层面上对各地类进行了数值上的模拟，采用CLUE-S模型在微观层面上对该数值进行了空间上的分配，成功地探索了不同情景下的未来城市增长模式。Liang等[16]基于SD-CLUE-S和InVEST(Inter-grated Valuation of Environmental Services and Trad-eoffs)模型模拟和预测了2000—2018年张掖绿洲土地利用变化对像元尺度和区域尺度碳储量的影响。Ding等[1 建立了一个基于FLUS与InVEST模型的耦合模型，有效地模拟了东营市2030年不同情景的人居环境质量变化。

研究表明，在耦合模型中，空间模拟模型的性能尤为重要，而不同模型的适用区域存在差异。PLUS模型通过随机森林算法挖掘地类转化概率，善于处理高维数据[18]。CLUE-S模型来源于CLUE模型，解决了CLUE模型不适用于小区域模拟的局限性[4,19]。FLUS模型采用神经网络算法获得适宜性概率,有利于保证模拟精度的提升[20]。Peng等[1-2,4]将随机森林算法与CLUE-S模型结合，充分利用随机森林算法在处理高维共线性问题方面的优势。林丽等[23]选择LCM(Land Change Modeler）、FLUS、CA-Markov和CLUE-S模型对地形复杂的云南山区进行研究，最终发现不同土地利用类型的适用模型存在差异，FLUS模型更适于模拟建设用地，CLUE-S模型在园地存在过拟合现象。Liang等[18对武汉市进行研究，发现PLUS模型在该区域的模拟性能优于FLUS模型。由此可见，不同空间模拟模型在不同区域表现出不同的模拟结果。

位于中国西北干旱区的张掖市甘州区、临泽县和高台县(本文简称甘临高），处于河西走廊中部的黑河流域中游、青藏高原和蒙古高原的连接处，具有典型的区域代表性，加之该区生态环境和社会经济发展对土地利用变化较为敏感。因此，研究该区的土地利用变化具有重要意义。为深人探究PLUS、CLUE-S和FLUS空间模拟模型在该区的适用性，更好地预测土地利用变化，笔者选取甘临高地区为研究区，通过对比PLUS、FLUS和CLUE-S模型模拟结果，筛选最适于该区的空间模拟模型；然后将其与SD数量模拟模型耦合，预测2030年不同情景下研究区的土地利用格局，为区域社会经济可持续发展提供参考。

# 1研究区概况与方法

# 1.1 研究区概况

黑河是中国第二大内陆河，黑河流域中游的张掖市甘州区、临泽县和高台县的是本文的研究区。该区地理位置为 $9 8 ^ { \circ } 5 7 ^ { \prime } { \sim } 1 0 0 ^ { \circ } 5 2 ^ { \prime } \mathrm { E } \ . 3 8 ^ { \circ } 3 9 ^ { \prime } { \sim } 3 9 ^ { \circ } 5 9 ^ { \prime } \mathrm { N }$ (图1)。研究区的气候类型为温带大陆性气候，年均降水量约为 $1 0 0 { \sim } 1 5 0 \ \mathrm { m m }$ ，年均蒸发量高达$2 0 4 7 . 9 ~ \mathrm { m m }$ ,年均气温在 $8 { \sim } 9 \ \mathrm { \textdegree C }$ 区间波动。研究区地势南北高、中间低，主要的地表覆盖类型为耕地、草地、荒漠等[24]。该区位于干旱区，生态环境脆弱，草地的萎缩和耕地的不合理扩张加剧了荒漠化。

# 1.2数据来源及处理

土地利用数据、自然环境数据和社会经济数据均来源于中国科学院资源环境数据共享中心(http://www.resdc.cn）。除气温、降水、人口和GDP数据的空间分辨率为 $1 ~ \mathrm { k m }$ ,其余数据的空间分辨率为 $3 0 \mathrm { m }$ (表1)。本研究将所有数据的空间分辨率重采样为$3 0 \mathrm { ~ m ~ }$ 。不同像元与道路、河流、居民点的距离数据均是 $\mathrm { A r c G I S ~ } 1 0 . 2$ 软件中基于相应矢量数据计算欧氏距离的结果。

# 1.3模型与方法

1.3.1土地利用空间格局模拟及验证(1）3种空间模型介绍

PLUS模型包括基于土地扩张分析策略的转化规则挖掘框架和基于多类型随机斑块种子机制的CA模型两大模块[18（图2)。CLUE-S模型包括非空间土地需求模块和空间分配模块两大部分[4.19]。本研究采用线性插值法计算2000—2015年间不同地类的需求面积，不同地类与驱动因素之间的关系数据来源于Logistics回归方程。研究采用ROC(Rela-tive OperatingCharacteristics）方法检验Logistics回归的结果，当 $\mathrm { R O C } { > } 0 . 7$ ,说明回归方程能够较好地解释地类结构[25],然后采用空间分配模块进行空间结构模拟。FLUS模型由2个模块构成[20],第一个模块采用神经网络算法基于初始年份的土地利用数据与驱动因素栅格数据获得适宜性概率，第二个模块基于轮盘赌法则的自适应惯性竞争机制研究不同驱动因素影响下各地类的转化。

# （2）模型精度验证指标

主要采用3种模型精度验证方法。第一种方法是逐像元精度评价方法，评价指标为 $\mathrm { F o M } ^ { [ 2 6 - 2 7 ] }$ 。第二种方法是空间格局比较法，评价指标为景观格局相似度，本研究采用Fragstats4.2.1软件计算模拟与实际的土地利用结构图的景观指数，进而获得景观格局相似度 $S i m ^ { [ 2 8 ] }$ ,公式如下：

![](images/802eb4396021d935bc5b1e6b98c456884a55dfbb62824ba337fd3767c543e460.jpg)  
注：底图采用自然资源部标准地图制作，审图号GS(2019)3333号，对底图边界无修改。下同。图1研究区在甘肃省的地理位置(a)、高程(b)、地貌类型(c)和2015年土地利用空间分布(d)Fig.1GeograpicalocationofthestudyareainGansuProvince (a),elevation (b),landformtype(c)andthespatialdistributionmap of land use in 2015 (d)

表1研究数据源信息  
Tab.1 Data source information of the research   

<html><body><table><tr><td>类型</td><td>数据</td><td>分辨率</td><td>来源</td></tr><tr><td>土地利用数据</td><td>土地利用数据(2000年、2015年)</td><td>30m</td><td>http://www.resdc.cn</td></tr><tr><td rowspan="4">自然环境数据</td><td>年均气温(2015年)</td><td>1 km</td><td></td></tr><tr><td>年均降水(2015年)</td><td>1 km</td><td></td></tr><tr><td>高程</td><td>30m</td><td></td></tr><tr><td>坡度</td><td>30 m</td><td></td></tr><tr><td rowspan="6">社会经济数据</td><td>坡向</td><td>30m</td><td></td></tr><tr><td>人口(2015年)</td><td>1 km</td><td></td></tr><tr><td>GDP(2015年)</td><td>1 km</td><td></td></tr><tr><td>像元与道路的距离数据</td><td>30 m</td><td></td></tr><tr><td>像元与河流的距离数据</td><td>30 m</td><td></td></tr><tr><td>像元与居民点的距离数据</td><td>30m</td><td></td></tr></table></body></html>

$$
S i m = \left( 1 - \frac { 1 } { n } \sum _ { i = 1 } ^ { n } \frac { \left| \boldsymbol { l } _ { i , s } - \boldsymbol { l } _ { i , o } \right| } { l _ { i , o } } \right) \times 1 0 0 \%
$$

式中： $n$ 表示指标总数； $l _ { i , s }$ 表示模拟土地利用结构图的景观指数; $l _ { i , o }$ 表示实际土地利用结构图的景观指数。第三种方法是Kappa系数，该系数主要被用于验证空间模拟精度。本文使用PONTIUS发展的

Kappa系数量化位置错误和数量错误[29],采用IDRI-SI17.0软件计算数量Kappa系数 $\left( K _ { \mathrm { n o } } \right)$ 、位置Kappa系数 $( K _ { \mathrm { l o c a t i o n } } )$ 和标准Kappa系数 $\left( K _ { \mathrm { s t a n d a r d } } \right)$ 。

1.3.2 基于SD模型的未来情景预测

（1）SD模型介绍

SD模型于1956年建立，该模型是生态环境和经济发展复合系统的仿真模拟实验室，在数据模拟方面功能强大[10.30]。本研究使用的SD模型包括人口、经济、生产力和气候4个子系统(图3)。甘临高地区的各变量数据参考张掖地区，各系统变量的数值来源于《甘肃发展年鉴》《张掖统计年鉴》和《中国城市统计年鉴》等文献[31-34]。使用SPSS 23软件进行统计分析，获得不同变量间的数量关系，SD模型模拟的时间范围为2000—2030年，时间步长为1a。

![](images/99c793adc6f47309365a88af96d89398b77af914ab3bb259ef3ca41ef8421047.jpg)  
图2本研究流程  
Fig.2Flow chart of this study

(2）SD模型检验

SD模型历史仿真检验的相对误差计算公式为：

$$
= \frac { \left| \mathit { \hat { k } } _ { \mathrm { B } } ^ { \mathrm { H } } \ddag \mathrm { U } \lambda / \mathrm { \overleftrightarrow { E } } - \sqrt { \mathcal { H } } \mathfrak { L } / \mathrm { \overleftrightarrow { E } } \right| } { \iiint \mathfrak { H } \langle \vert \mathrm { \overleftrightarrow { E } } \vert } \times 1 0 0 \%
$$

为验证模型仿真效果，本文确定历史检验时间为2015年，历史检验的相对误差均低于 $5 \%$ ,这说明模型的模拟精度较高，能够正确预测土地系统结构(表2)。

# (3）情景选择

“十二五"规划期间张掖市GDP年均增速为$1 0 . 5 \%$ ,人口年均增长率为 $5 . 2 \% o$ ，“十三五"规划期间GDP年均增长率为 $8 . 5 \%$ ,综合考虑将HD、ED 和EP情景下的GDP增长率分别设置为 $12 \%$ 、 $14 \%$ 和

$9 \%$ (表3)；由于二孩政策的实施，本研究将HD、ED和EP情景下的人口增长率分别设置为 $6 \text{‰}$ ） $10 \text{‰}$ 和$4 \text{‰}$ 。甘肃省城镇体系规划(2013—2030年)中要求规划期末张掖绿洲生态城乡统筹发展区城镇化率应达到 $6 1 . 8 \%$ ，据此本研究将HD、ED和EP情景下的城镇化率分别设置为 $6 1 . 8 \%$ ） $6 5 \%$ 和 $6 0 \%$ 。IPCC报告指出2016—2035年全球气温和降水会逐年增加[35]。参考前人的研究[36],HD、ED和EP情景下的年均气温与降水变化量都设置为正值。根据统计年鉴中的技术研发投人数据确定技术参数。

# 2结果与分析

# 2.1PLUS模型与其他模型的模拟结果

为对比分析CLUE-S、PLUS和FLUS模型的模拟效果，通过重采样将研究像元尺度统一为 $5 0 \mathrm { m }$ 。当模拟尺度为 $5 0 \mathrm { m }$ 时，耕地、林地、农村建设用地和未利用地的ROC最高(表4)。由此可知，CLUE-S模型在本研究区的最佳研究尺度为 $5 0 \mathrm { m }$ 。PLUS模型在$3 0 \mathrm { ~ m ~ } . 5 0 \mathrm { ~ m ~ } . 1 0 0 \mathrm { ~ m ~ }$ 和 $2 0 0 \mathrm { ~ m ~ }$ 栅格尺度下的FoM分别

![](images/3b078b982a66e4c8f7d0dac545bb11d6be63388a63561877911327e5655cf9ee.jpg)  
图3SD模型结构框架  
Fig.3Flow chart of SD model

# 表2SD模型模拟结果的历史性检验

Tab.2 Historical testof SD model's simulation results   
/hm²   

<html><body><table><tr><td>检验</td><td>耕地</td><td>林地</td><td>草地</td><td>水域</td><td>城市建设用地</td><td>农村建设用地</td><td>未利用地</td></tr><tr><td>历史值(2015年)</td><td>217147</td><td>11625</td><td>149341</td><td>24752</td><td>6974</td><td>15450</td><td>642389</td></tr><tr><td>模拟值(2015年)</td><td>215784</td><td>11554</td><td>149322</td><td>24695</td><td>6938</td><td>14736</td><td>644650</td></tr><tr><td>相对误差/%</td><td>0.63</td><td>0.61</td><td>0.01</td><td>0.23</td><td>0.51</td><td>4.62</td><td>0.35</td></tr></table></body></html>

Tab.3 Parameter setting of different scenarios   

<html><body><table><tr><td>变量</td><td>人口增长率/%0</td><td>GDP增长率/%</td><td>年降雨变化/(mm·a-1)</td><td>年均温变化/(C·a-)</td><td>技术系数</td><td>城镇化率</td></tr><tr><td>HD情景</td><td>6</td><td>12</td><td>0.350</td><td>0.020</td><td>400</td><td>43%线性增至61.8%</td></tr><tr><td>ED情景</td><td>10</td><td>14</td><td>0.550</td><td>0.030</td><td>500</td><td>43%线性增至65%</td></tr><tr><td>EP情景</td><td>4</td><td>9</td><td>0.15</td><td>0.010</td><td>500</td><td>43%线性增至60%</td></tr></table></body></html>

表3不同情景的参数设定  
表4CLUE-S模型的ROC指数  
Tab.4 ROC index of CLUE-S model   

<html><body><table><tr><td>分辨率/m</td><td>耕地</td><td>林地</td><td>草地</td><td>水域</td><td>城市建设用地</td><td>农村建设用地</td><td>未利用地</td></tr><tr><td>30</td><td>0.731</td><td>0.566</td><td>0.57</td><td>0.509</td><td>0.569</td><td>0.684</td><td>0.758</td></tr><tr><td>50</td><td>0.935</td><td>0.696</td><td>0.737</td><td>0.722</td><td>0.915</td><td>0.834</td><td>0.893</td></tr><tr><td>100</td><td>0.935</td><td>0.698</td><td>0.729</td><td>0.728</td><td>0.867</td><td>0.832</td><td>0.892</td></tr><tr><td>200</td><td>0.935</td><td>0.68</td><td>0.738</td><td>0.72</td><td>0.928</td><td>0.833</td><td>0.892</td></tr></table></body></html>

度均为 $3 0 \mathrm { m }$ 。

为0.234、0.184、0.145和0.152，相同像元尺度下FLUS模型的模拟精度分别为 $0 . 1 4 7 , 0 . 1 3 3 , 0 . 1 2 8$ 和0.117。据此可得，PLUS和FLUS模型的最佳拟合尺

在 $5 0 \mathrm { ~ m ~ }$ 研究尺度下PLUS、FLUS和CLUE-S模型的FoM值分别为0.184、0.133和0.133，PLUS模型在模拟精度上优于FLUS和CLUE-S模型。PLUS、CLUE-S和FLUS模型的 $K _ { \mathrm { n o } }$ 分别为 $0 . 9 6 2 5 , 0 . 9 4 4 4$ 和$0 . 9 1 8 8 , K _ { \mathrm { l o c a t i o n } }$ 分别为 $0 . 9 4 5 6 \ 、 0 . 9 1 9 3$ 和 $0 . 8 8 1 8 , K _ { \mathrm { s t a n d a r d } }$ 分别为 $0 . 9 4 5 5 , 0 . 9 1 9 1$ 和0.8818。3个模型的Kappa系数值均大于0.8，且 $K _ { \mathrm { n o } }$ 高于 $K _ { \mathrm { l o c a t i o n } }$ ，说明3个模型的数量预测能力均优于位置预测能力。PLUS模型的3 种Kappa系数最高，且均大于0.95,说明模型模拟结果与实际情况基本一致。

本文采用15个景观指数比较3个模型在挖掘景观变化方面的能力。Fragstats 4.2.1软件计算的结果表明(表5)，PLUS模型有9个景观指数更贴近实际的景观指数：NP、PARA_MN、PARA_MD、PA-RA_RA、PARA_CV、ENN_MN、ENN_RA、ENN_MD和ENN_SD;CLUE-S模型有4个景观指数与实际的景观指数相符：PARA_AM、PLADJ、ENN_MD和ENN_CV;FLUS模型的LPI、PARA_SD和ENN_AM3个景观指数值与实际的景观指数相近。PLUS、FLUS和CLUE-S模型的景观相似度Sim分别为0.64、0.21和0.46，这说明PLUS模型在景观格局模拟方面优势明显。

总体上，PLUS模型的整体模拟效果明显优于

CLUE-S和FLUS模型，CLUE-S模型在地势平坦地区模拟准确度高于FLUS模型，而FLUS模型在地势起伏较大地区的模拟效果优于CLUE-S模型（图4）。（1）在临泽县、高台县和甘州区，CLUE-S模型模拟的地形平坦处的耕地范围略大于实际范围，但是准确度较高。在高台县南部海拔高处，CLUE-S模型模拟的草地范围大于实际范围;在临泽县和甘州区的北部海拔高处，CLUE-S模型模拟的草地范围小于实际范围；在地形平坦的中部地区，CLUE-S模型模拟的建设用地范围略小于实际范围，在海拔高处，该模型模拟的林地和建设用地范围大于实际范围。（2）在临泽县和甘州区，FLUS模型模拟的耕地范围显著大于实际范围，在高台县FLUS模型模拟的耕地范围小于实际范围；FLUS模型模拟的海拔高处的草地范围与实际情况较为接近，模拟精度较CLUE-S模型高，但略低于PLUS模型；FLUS模型模拟的林地和建设用地范围较实际范围略大。(3)PLUS模型的模拟准确度显著高于CLUE-S和FLUS模型，其模拟结果基本与实际范围相符。与FLUS模型相比，CLUE-S和PLUS模型模拟的农村建设用地范围与实际更相符。甘州区、临泽县和高台县的城市建设用

表5不同模型2015年模拟结果的景观指数  
Tab.5Landscape data of simulation results of different models in 2015   

<html><body><table><tr><td>景观指数</td><td>PLUS(50 m)</td><td>FLUS(50 m)</td><td>CLUE-S(50 m)</td><td>实际(50m)</td></tr><tr><td>NP（Number of patches)</td><td>7122.00a</td><td>20303.00c</td><td>11957.00b</td><td>4182.00</td></tr><tr><td>LPI(Largest patch index)/%</td><td>43.48c</td><td>52.71a</td><td>53.06b</td><td>50.89</td></tr><tr><td>PARA_MN（Mean perimeter-area ratio)</td><td>456.47a</td><td>613.45c</td><td>536.94b</td><td>231.18</td></tr><tr><td>PARA_AM(Area-weighted mean perimeter-area ratio)</td><td>36.94b</td><td>63.30c</td><td>36.17a</td><td>33.58</td></tr><tr><td>PARA_MD（Median perimeter-area ratio)</td><td>366.67a</td><td>640.00c</td><td>600.00b</td><td>222.22</td></tr><tr><td>PARA_RA（Perimeter-area ratio range)</td><td>790.01a</td><td>776.04c</td><td>790.70b</td><td>789.71</td></tr><tr><td>PARA_SD(Perimeter-area ratio standard deviation)</td><td>266.51c</td><td>206.07a</td><td>250.83b</td><td>123.03</td></tr><tr><td>PARA_CV（Perimeter-area ratio coefficient of variation)</td><td>58.38a</td><td>33.59c</td><td>46.72b</td><td>53.22</td></tr><tr><td>ENN_MN（Mean euclidean nearest neighbor distance)/m</td><td>276.76a</td><td>150.13c</td><td>233.80b</td><td>464.08</td></tr><tr><td>ENN_AM（Area- weighted mean euclidean nearest neigh- bor distance)/m</td><td>183.61b</td><td>146.66a</td><td>131.66c</td><td>159.72</td></tr><tr><td>ENN_MD（Median euclidean nearest neighbor distance)/m</td><td>141.42a</td><td>111.80c</td><td>141.42a</td><td>223.61</td></tr><tr><td>ENN_RA（Euclidean nearest neighbor distance range )/m</td><td>26382.45a</td><td>20753.12c</td><td>24047.88b</td><td>34894.36</td></tr><tr><td>ENN_SD (Euclidean nearest neighbor distance standard deviation)/m</td><td>751.54a</td><td>320.79c</td><td>516.44b</td><td>1087.47</td></tr><tr><td>ENN_CV（Euclidean nearest neighbor distance coefficient of variation )/m</td><td>271.55c</td><td>213.68b</td><td>220.89a</td><td>234.33</td></tr><tr><td>PLADJ(Percentage of like adjacencies )/%</td><td>95.38b</td><td>92.09c</td><td>95.48a</td><td>95.80</td></tr><tr><td>Sim</td><td>0.64</td><td>0.21</td><td>0.46</td><td></td></tr></table></body></html>

注：a指代模拟图像与实际图像的景观指数最相符;b次之;c表示最不相符。

100°20'E 10040'E 1010'E 100°0'E 100°20'E 990'E 99°20'E 99°40'E 1000E   
80030 (a1)PLUS模型 20060 20060 (b1)PLUS模型 300060 (c1) PLUS模型模拟-高台县 模拟-甘州区 模拟-临泽县 104060 104060   
N0.6 N0.69 30060 20030 30060 30060   
304080 30580 0 14 km N0.60 0 10 km N0.60 0L 17 km 100°20'E 100°40'E 101°'E 100°0'E 100°20'E 99°0'E 99°20'E 99°40'E 100°0'E   
3006M 模拟-甘州区 104060 100F10020 模拟-临泽县 305060 FL0 1 105060 204060   
10.69 10.69 30030 300030 300060 20060   
30480 0480 0 14 km 10.60 0 10km 10.60 0 17 km 100°20'E100°40'E101°0'E 100°0'E 100°20'E 99°0'E 99°20'E 99°40'E 100°0'E   
30030 模拟-甘州区 300060 100CLUE.0020 模拟-临泽县 205060 EUE2 105060 205060   
N0.60 N0.69 20060 30030 307060 30060   
204080 10480 0 14 km N0.60 0 10km N0.60 0 17 km 100°20'E 100°40'E101°0'E 100°0'E 100°20'E 99°0'E 99°20'E 99°40'E 100°0'E   
80030 利用-甘州区 204060 00100 利用-临泽县 10060 实际土地用商台 100°0'E 100060 205060   
N0.60 N0.69 30060 30030 30060 3000   
20480 30480 0 14 km N0.60 0 10km N0.60 0 17km 100°20'E 100°40'E 1010E 100°0'E 100°20'E 990'E 99°20'E 9940'E1000E 图例耕地 林地 0 草地 ■水域 □城市建设用地 □农村建设用地 □未利用地

地发展过程中均出现了“飞地式"扩张现象，3个模型在模拟这类建设用地时均失效，这或许是驱动因素与地类变化之间时间滞后的结果。

# 2.2PLUS-SD耦合模型的不同情景预测结果

甘州区、临泽县和高台县各地类变化的区域多位于地类边缘，以边缘式扩张为主（图5，表6\~表7)(1)基于 $3 0 \mathrm { ~ m ~ }$ 分辨率土地利用数据模拟的结果表明，EP和HD情景中2015—2030年期间耕地面积增加，其来源均有草地。EP情景下耕地面积减少，主要转化为林地和草地，说明政府采取退耕还林还草措施保护生态环境。(2)ED情景中城市化水平显著提高，技术发展迅速，2030年林地面积逐渐减少，主要转化为耕地。EP和HD情景林地面积增加,HD情景中部分未利用地转化为林地，EP情景增加的林地主要来自耕地。（3）2030年ED和HD情景的草地面积低于2015年，EP情景则相反。（4）城市发展导致热岛效应和雨岛效应，全球变暖促使降水增加，模拟结果显示3种情景的水域面积均增加。(5)

![](images/cc0141321155c4368e7f2bb5c28b1812ecb0f2aa4203569c32804b33814c116f.jpg)  
图5不同情景中的2030年土地利用结构  
Fig.5Land use structure in different scenarios in 2030

/hm²

Tab.6 Future prediction results of land use types under different scenarios   

<html><body><table><tr><td rowspan="2">类型</td><td rowspan="2">2015年</td><td colspan="3">SD模型(2030年)</td></tr><tr><td>ED情景</td><td>EP情景</td><td>HD情景</td></tr><tr><td>耕地</td><td>217147</td><td>261740</td><td>203469</td><td>225155</td></tr><tr><td>林地</td><td>11625</td><td>7958</td><td>14747</td><td>12165</td></tr><tr><td>草地</td><td>149341</td><td>137645</td><td>152568</td><td>146553</td></tr><tr><td>水域</td><td>24752</td><td>28097</td><td>25413</td><td>26704</td></tr><tr><td>城市建设用地</td><td>6974</td><td>14253</td><td>12070</td><td>13166</td></tr><tr><td>农村建设用地</td><td>15450</td><td>14732</td><td>14845</td><td>14690</td></tr><tr><td>未利用地</td><td>642389</td><td>603253</td><td>644568</td><td>629247</td></tr></table></body></html>

表6不同情景的未来各土地利用类型面积预测结果  
表7不同情景的未来各土地利用转移矩阵  
Tab.7 Future land use transition matrix under different scenarios   
/hm²   

<html><body><table><tr><td>情景</td><td>2015年/2030年</td><td>耕地</td><td>林地</td><td>草地</td><td>水域</td><td>城市建设用地 农村建设用地</td><td></td><td>未利用地</td><td>总计</td></tr><tr><td>ED情景</td><td>耕地</td><td>215340</td><td>18</td><td>272</td><td>239</td><td>292</td><td>0</td><td>987</td><td>217147</td></tr><tr><td></td><td>林地</td><td>2803</td><td>7648</td><td>421</td><td>112</td><td>68</td><td>0</td><td>573</td><td>11625</td></tr><tr><td></td><td>草地</td><td>6215</td><td>82</td><td>134401</td><td>435</td><td>283</td><td>0</td><td>7924</td><td>149341</td></tr><tr><td></td><td>水域</td><td>2825</td><td>27</td><td>718</td><td>17973</td><td>150</td><td>0</td><td>3059</td><td>24752</td></tr><tr><td></td><td>城市建设用地</td><td>414</td><td>7</td><td>16</td><td>5</td><td>6430</td><td>0</td><td>103</td><td>6974</td></tr><tr><td></td><td>农村建设用地</td><td>708</td><td>0</td><td>0</td><td>1</td><td>9</td><td>14732</td><td>0</td><td>15450</td></tr><tr><td></td><td>未利用地</td><td>33435</td><td>175</td><td>1818</td><td>9332</td><td>7022</td><td>0</td><td>590606</td><td>642389</td></tr><tr><td></td><td>总计</td><td>261740</td><td>7958</td><td>137645</td><td>28097</td><td>14253</td><td>14732</td><td>603253</td><td>1067678</td></tr><tr><td>EP情景</td><td>耕地</td><td>184921</td><td>6293</td><td>11703</td><td>2506</td><td>1943</td><td>26</td><td>9754</td><td>217147</td></tr><tr><td></td><td>林地</td><td>1341</td><td>6718</td><td>2020</td><td>150</td><td>106</td><td>0</td><td>1289</td><td>11625</td></tr><tr><td></td><td>草地</td><td>4176</td><td>730</td><td>121801</td><td>1467</td><td>747</td><td>0</td><td>20419</td><td>149341</td></tr><tr><td></td><td>水域</td><td>1271</td><td>112</td><td>1856</td><td>18428</td><td>99</td><td>1</td><td>2985</td><td>24752</td></tr><tr><td></td><td>城市建设用地</td><td>246</td><td>32</td><td>94</td><td>5</td><td>6354</td><td>1</td><td>242</td><td>6974</td></tr><tr><td></td><td>农村建设用地</td><td>491</td><td>9</td><td>19</td><td>5</td><td>50</td><td>14813</td><td>64</td><td>15450</td></tr><tr><td></td><td>未利用地</td><td>11022</td><td>854</td><td>15074</td><td>2851</td><td>2770</td><td>3</td><td>609815</td><td>642389</td></tr><tr><td></td><td>总计</td><td>203469</td><td>14747</td><td>152568</td><td>25413</td><td>12070</td><td>14845</td><td>644568</td><td>1067678</td></tr><tr><td>HD情景</td><td>耕地</td><td>217015</td><td>2</td><td>4</td><td>17</td><td>25</td><td>0</td><td>83</td><td>217147</td></tr><tr><td></td><td>林地</td><td>139</td><td>10715</td><td>11</td><td>133</td><td>54</td><td>0</td><td>572</td><td>11625</td></tr><tr><td></td><td>草地</td><td>2181</td><td>48</td><td>146489</td><td>188</td><td>94</td><td>0</td><td>341</td><td>149341</td></tr><tr><td></td><td>水域</td><td>176</td><td>60</td><td>17</td><td>21684</td><td>118</td><td>0</td><td>2697</td><td>24752</td></tr><tr><td></td><td>城市建设用地</td><td>22</td><td>6</td><td>1</td><td>1</td><td>6874</td><td>0</td><td>70</td><td>6974</td></tr><tr><td></td><td>农村建设用地</td><td>748</td><td>1</td><td>0</td><td>1</td><td>12</td><td>14690</td><td>0</td><td>15450</td></tr><tr><td></td><td>未利用地</td><td>4874</td><td>1334</td><td>31</td><td>4679</td><td>5989</td><td>0</td><td>625483</td><td>642389</td></tr><tr><td>总计</td><td></td><td>225155</td><td>12165</td><td>146553</td><td>26704</td><td>13166</td><td>14690</td><td>629247</td><td>1067678</td></tr></table></body></html>

2030年3种情景的城市建设用地面积均增加，主要来自于未利用地。ED、EP和HD情景的农村建设用地均呈不同程度下降，可能是大量农村人口向城市人口转变。(6)3种情景的未利用地主要向耕地和城市建设用地转化，ED情景转化面积最大，HD情景次之，EP情景转化面积最小。

# 3讨论

# 3.1PLUS-SD模型在甘临高地区的适用性分析

（1）通过PLUS、FLUS和CLUE-S模型在甘临高地区的模拟结果，可以发现PLUS模型在位置预测、数量预测和景观格局相似度方面均优于FLUS和CLUE-S模型，CLUE-S模型在地形较为平坦地区模拟精度较高，而FLUS模型在海拔高处模拟效果略优于CLUE-S模型。前人的研究得出了类似结论，Liang等的研究表明，PLUS模型在模拟历史土地利用变化过程方面优于FLUS模型;济南市区土地利用变化模拟结果显示FLUS模型模拟结果的 Kap-pa 系数略低于CLUE-S模型[37]。（2）本研究表明，FLUS与PLUS模型的研究格网愈密集，模拟结果愈优,而CLUE-S模型并未随着格网密度增加而得到更优的模拟结果。张永民等[38]基于Logistic回归模型采用 $1 0 0 \mathrm { m } . 2 5 0 \mathrm { m } . 5 0 0 \mathrm { m } . 7 5 0 \mathrm { m }$ 和 $1 0 0 0 \mathrm { m }$ 这5种栅格尺度研究土地利用与不同影响因子的关系，结果显示 $5 0 0 \mathrm { ~ m ~ }$ 尺度下二者的相关性最高。CLUE-S模型基于传统的二值逻辑斯蒂回归确定地类空间结构与影响因素之间的相关关系，其研究尺度不宜过度密集;而PLUS模型在模拟细尺度元胞变化方面能力较强;FLUS模型通过增强空间分配和需求模拟之间的相互映射以达到“紧耦合的目标”（3）SD模型适用于模拟土地结构中不同影响因素之间的数量关系，通过情景分析模拟政策变化的效果[39]。本研究将SD与PLUS模型耦合，获得了不同情景下的土地利用结构，有利于生态和经济的可持续发展。不少研究对未来不同情景下的土地利用格局进行预测[40-41]。Lu等[42]将 SD和CCDM(Coupling Co-ordinationDegree Model)结合,对武汉市经济-资源-环境系统的模拟结果进行了分析和评价，清晰地揭示了经济-资源-环境系统中各因素的耦合关系。Wu等[43]建立SD-CLUE-S耦合模型，发现综合性模型能够更好地模拟上海宝山地区景观生态系统价值的动态变化。

# 3.2不同情景模拟结果的对比分析

甘临高地区的地表环境较恶劣，沙漠和戈壁面积较大。本研究的ED情景和EP情景偏重于经济发展或环境保护，不利于生态和经济协调发展;HD情景兼具生态友好和经济建设的优点。前人研究表明，甘临高地区存在草地荒漠化现象，草地生态环境脆弱，耕地对水分和养分的需求量大，不合理地开垦耕地将加剧土地荒漠化进程[44]。2030年的HD情景中有少量草地和农村建设用地转化为耕地，耕地主要来自于未利用地；退耕还林的加大，对未利用地的开发力度促使林地面积增加，有利于发挥国土空间的生态功能。HD情景中城市扩张的主要方向也是未利用地，随着技术的发展，未利用地的利用率和转化率显著提升。近年来高台等地的绿洲扩张明显，且绿洲波动带多位于绿洲和荒漠交界处[45]随着城镇化进程的加快会导致建设用地扩展，2033年建设用地面积将高达 $4 9 4 8 . 9 0 \times 1 0 ^ { 4 } \mathrm { h m } ^ { 2 [ 4 6 ] }$ 。在HD情景中，政府需严格管控建设用地,防止建设用地过度占用耕地，保护永久性基本农田，要集约且合理地安排建设用地，形成科学有序的国土空间开发格局[47]。

# 4结论

本研究发现PLUS模型在景观格局、位置和数量模拟方面的精度均优于CLUE-S和FLUS模型，CLUE-S模型在研究区地势低平地区模拟精度较高，而FLUS模型在海拔高处模拟效果较CLUE-S优；对比分析PLUS-SD耦合模型模拟的甘临高地区2030年ED、EP和HD情景下的土地利用情况，发现3种情景在土地利用类型变化速率方面存在差异；ED情景中土地利用类型变化速率最快，经济迅猛发展，但是环境破坏严重，林地大面积减少，EP情景中土地利用类型变化速率偏慢，存在明显的退耕还林还草现象，但经济发展滞缓，HD情景中建设用地占用耕地的现象较少，经济平稳运行，有利于社会可持续发展。

# 参考文献(References):

[1] Turner B L. The sustainability principle in global agendas:Implications for understanding land use/cover change[J]. The Geographical Journal, 1997,163(2): 114-133.   
[2] Hyandye C.GIS and logit regression model applications in land use/land cover change and distribution in Usangu catchment[J]. American Journal of Remote Sensing,2015,3(1):6-16.   
[3] SinghSK,Mustak S,SrivastavaPK,etal.Predicting spatial and decadal LULC changes through cellular automata Markov chain models using earth observation datasets and geo-information[J].Environmental Processes,2015,2(1): 61-78.   
[4] VerburgPH,Soepboer W,Veldkamp A,etal.Modeling the spatial dynamics of regional land use: the CLUE-S model[J]. Environmental Management,2002,30(3): 391-405.   
[5] Filatova T,Verburg PH,Parker D C,et al.Spatial agent-based models for socio-ecological systems: Challenges and prospects[J]. Environmental Modelling& Software,2013,45:1-7.   
[6]严冬,李爱农,南希,等.基于Dyna-CLUE改进模型和SD模型耦

合的山区城镇用地情景模拟研究——以岷江上游地区为例 [J].地球信息科学学报,2016,18(4):514-525.[Yan Dong,Li Ainong,Nan Xi,et al. The study of urban land scenario simulation in mountain area based on modified Dyna-CLUE model and SD:A case study of the upper reaches of Minjiang River[J]. Journal of Geo-Information Science,2016,18(4): 514-525.]

[7]田贺,梁迅,黎夏,等.基于SD模型的中国2010-2050年土地利 用变化情景模拟[J].热带地理,2017,37(4): 547-561.[Tian He, Liang Xun,Li Xia,et al.Simulating multiple land use scenarios in China during 2010-2050 based on system dynamic model[J].Tropical Geography,2017,37(4): 547-561.]   
[8]何春阳,史培军,陈晋,等.基于系统动力学模型和元胞自动机 模型的土地利用情景模型研究[J].中国科学(D辑:地球科学), 2005,35(5): 464-473.[He Chunyang, Shi Peijun, Chen Jin, et al. Research on land use scenario model based on system dynamics model and celllar automata model[J]. Science in China Ser.D Earth Sciences,2005,35(5): 464-473.]   
[9]黎夏,刘小平.基于案例推理的元胞自动机及大区域城市演变 模拟[J].地理学报,2007,62(10): 1097-1109.[Li Xia,Liu Xiaoping. Case-based cellular automation for simulating urban development in a large complex region[J]. Acta Geographic Sinica, 2007, 62(10): 1097-1109.]   
[10] Luo G, Yin C, Chen X,et al. Combining system dynamic model and CLUE-S model to improve land use scenario analyses at regional scale: A case study of Sangong watershed[J]. Ecological Complexity,2010,7(2): 198-207.   
[11] Peter HV,Koen PO. Combining top-down and botom-up dynamics in land use modeling: Exploring the future of abandoned farmlands in Europe with the Dyna-CLUE model[J]. Landscape Ecology,2009,24(9): 1167-1181.   
[12]Olmedo M TC,Jr RGP,Paegelow M, et al.Comparison of simulation models in terms of quantityand allocation of land change[J]. Environmental Modelling & Software,2015,69: 214-221.   
[13] 戴尔阜,马良.土地变化模型方法综述[J].地理科学进展,2018, 37(1): 152-162.[Dai Erfu,Ma Liang.Review on land change modeling approaches[J].rogress inGeography2018,37(1):152-16.]   
[14] 余强毅,吴文斌,唐华俊,等.复杂系统理论与Agent模型在土 地变化科学中的研究进展[J].地理学报,2011,66(11):1518- 1530.[Yu Qiangyi, Wu Wenbin,Tang Huajun,et al. Complex system theory and agent-based modeling: Progresss in land change science[J]. Acta Geographic Sinica,2011,66(11): 1518-1530.]   
[15]He XD,Mai X M, Shen G Q.Delineation of urban growth boundaries with SD and CLUE-S models under multi-scenarios in Chengdu Metropolitan Area[J]. Sustainability,2019,11(21): 5919.   
[16]Liang Y,Liu L, Huang J. Integrating the SD-CLUE-S and InVEST models into assessment of oasis carbon storage in northwestern China[J].Plos One,2017,12(2): e0172494..   
[17]Ding Q,Chen Y,Bu L,et al. Multi-scenario analysis of habitat quality in the Yellow River Delta by coupling FLUS with InVEST model[J]. International Journal of Environmental Research and Public Health,2021,18(5): 2389.   
[18]Liang X,Guan Q, Clarke K C,et al. Understanding the drivers of sustainable land expansion using apatch-generating land use simulation (PLUS) model: A case study in Wuhan, China[J]. Computers,Environment and Urban Systems,2021,85: 1-14.   
[19]Verburg P H, Veldkamp T,Bouma J.Land use change under conditions of high population pressure: the case of Java[J]. Global Environmental Change,1999,9(4): 303-312.   
[20]Liu X, Liang X,Li X,et al.A future land use simulation model (FLUS) for simulating multiple land use scenarios by coupling human and natural effects[J]. Landscape Urban Plan,2O17,168: 94- 116.   
[21]Peng K, Jiang W,Deng Y,etal. Simulating wetland changes under different scenarios based on integrating the random forest and CLUE-S models: A case study of Wuhan Urban Agglomeration[J]. Ecological Indicators,2020,117: 1-13.   
[22] Moulds S, Buytaert W,Mijic A.An open and extensible framework for spatially explicit land use change modelling: The lulcc R package[J].Geoscientic ModelDevelopment,2015,8(10):3215-3229.   
[23] 林丽,樊辉,金缘.山区县域土地利用/覆被变化多尺度多模型 模拟对比——以云南省勐腊县为例[J].山地学报,2020,38(4): 630-642.[Lin Li,Fan Hui, Jin Yuan.Multi-scale and multi-model simulation of land use/land cover change in the mountainous county: A case study of Mengla County in Yunnan Province, China [J]. Mountain Research,2020,38(4): 630-642.]   
[24] 张勃,毛彦成,柳景峰.黑河中游土地利用/覆盖变化驱动力的 定量分析[J].干旱区地理,2006,29(5):726-730.[Zhang Bo,Mao Yancheng,Liu Jingfeng.Analysis driving forces of LUCC in Heihe midle reaches[J].AridLandGegrah,2006,29(5):7630.]   
[25] Pontius R G,Schneider L C.Land-cover change model validation by an ROC method for the Ipswich watershed, Massachusetts,USA [J].Agriculture,Ecosystems and Environment,2001,85(1-3): 239- 248.   
[26]Pontius R G,Boersma W,Castell J,et al.Comparing theiput, output,and validation maps for several modelsof landchange[J]. The Annals of Regional Science,2007,42(1): 11-37.   
[27]Pontius R G,Milones M. Death to Kappa: Birth of quantity disagreement and allocation disagreement for accuracyassessment [J]. International Journal of Remote Sensing,2011,32(15): 4407- 4429.   
[28]Chen Y,Li X,Liu X, etal. Capturing the varying effcts of driving forces over time for the simulation of urban growth by using survival analysis and cellular automata[J]. Landscape Urban Plan, 2016, 152: 59-71.   
[29] Pontius R G. Quantification error versus location error in comparison of categorical maps[J]. Photogrammetric Engineering and Remote Sensing,2000,66(8): 1011-1016.   
[30] 李秀霞,徐龙,江恩赐.基于系统动力学的土地利用结构多目标 优化[J].农业工程学报,2013,29(16):247-254.[Li Xiuxia, Xu Long,Jiang Enci. Multi-objective optimization of land use structure in western Jilin Province based on system dynamics[J]. Transactions of the Chinese Society of Agricultural Engineering,2013,   
29(16): 247-254.] [31]国家统计局.中国统计年鉴[M].北京:中国统计出版社,2000-   
2015.[National Bureau of Statistics.China Statistical Yearbook [M]. Beijing: China Statistics Press,2000-2015.] [32] 张掖年鉴编纂委员会.张掖年鉴[M].甘肃:敦煌文艺出版社,   
2000-2015.[Zhangye Yearbook Editorial Board. Zhangye yearbook[M]. Gansu: Dunhuang Literature and Art Publishing House,   
2000-2015.] [33] 甘肃年鉴编纂委员会.甘肃发展年鉴[M].北京:中国统计出版 社,2000-2015.[Gansu Development Yearbook Editorial Board. Gansu Development Yearbook[M]. Beijing: China Statistics Press,   
2000-2015.] [34]国家统计局城市社会经济调查司.中国城市发展年鉴[M].北 京：中国统计出版社,200-2015.[Department of Urban Society and Economic Statistics National Bureau of Statistics of China. China City Statistical Yearbook[M].Beijing:China Statistics Press,2000-2015.] [35] IPCC. Climate Change 2O13: The Physical Science Basis. Contribution of Working Group I to the Fifth Assessment Report of the Intergovernmental Panel on Climate Change[R]. Cambridge and New York: Cambridge University Press,2013:159-254. [36] 梁友嘉,徐中民,钟方雷.基于SD和CLUE-S模型的张掖市甘 州区土地利用情景分析[J].地理研究,2011,30(3):564-576. [Liang Youjia, Xu Zhongmin, Zhong Fanglei. Land use scenario analyses by based on system dynamic model and CLUE-S model at regional scale: A case study of Ganzhou district of Zhangye City [J]. Geographic Research, 2011,30(3): 564-576.] [37] 刘玉钢,王立宇.济南市土地利用变化模拟预测研究[J].国土与 自然资源研究,2021(1):47-50.[Liu Yugang,Wang Liyu. Research on simulation and prediction of land use change in Jinan City[J]. Territory & Natural Resources Study,2O21(1): 47-50.] [38] 张永民,周成虎,郑纯辉,等.沽源县土地利用格局的多尺度模 拟与分析[J].资源科学,2006,28(2):88-96.[Zhang Yongmin, Zhou Chenghu, Zheng Chunhui,et al.Spatial land use paterns in Guyuan County: Simulation and analysis at multi-scale levels[J]. Resources Science,2006, 28(2): 88-96.] [39]Saysel A K,Barlas Y, Yenigin O.Environmental sustainability in an agricultural development project: A system dynamics approach [J]. Journal of Environmental Management,2002,64(3): 247-260.   
[40] 苏迎庆,刘庚,赵景波,等.基于FLUS模型的汾河流域生态空 间多情景模拟预测[J].干旱区研究,2021,38(4):1152-1161. [Su Yingqing, Liu Geng, Zhao Jingbo,et al. Multi-scenario simulation prediction of ecological space in the Fenhe River Basin using the FLUS model[J]. Arid Zone Research,2021,38(4): 1152-1161.]   
[41] 金梦婷,徐丽萍,徐权.基于FLUS-Markov模型的多情景景观生 态风险评价与预测——以南疆克州为例[J].干旱区研究,2021, 38(6): 1793-1804.[Jin Mengting,Xu Liping,Xu Quan. FLUS-Markov model- based multiscenario evaluation and prediction of the landscape ecological risk in Kezhou, South Xinjiang[J].Arid Zone Research,2021,38(6): 1793-1804.]   
[42]Lu Xing, Xue M G, Hu M S.Dynamic simulation and assessment of the coupling coordination degree of the economy-resource-environment system: Case of Wuhan City in China[J].Journal of Environmental Management,2019,230: 474-487.   
[43] Wu M,Ren X,Che Y,et al.A coupled SD and CLUE-S model for exploring the impact of land use change on ecosystem service value:A case study in Baoshan District, Shanghai, China[J]. Environmental Management,2015,56(2): 402-419.   
[44] 傅颖秀,张金龙,陈英,等.黑河中游典型绿洲土地利用/覆盖变 化及生态环境效应——以甘州、临泽、高台绿洲为例[J].干旱 区资源与环境,2014,28(10):104-109.[Fu Yingxiu, Zhang Jinlong,Chen Ying,et al.LUCC and its environmental effects on the typical oases in the middle reaches of Heihe River Basin: Case of Linze and Gaotai Oases in Ganzhou[J]. Journal of Arid Land Resources and Environment,2014,28(10): 104-109.]   
[45]田文婷,颉耀文,陈云海.近50a高台县绿洲时空变化研究[J]. 干旱区研究,2013,30(6):1122-1128.[Tian Wenting,Xie Yaowen,Chen Yunhai. Spatiotemporal change of the oasis in Gaotai County in recent 50 years[J].Arid Zone Research,2013,30(6): 1122-1128.]   
[46]Wang J, Chen Y Q, Shao X M,et al.Land-use changes and policy dimension driving forces in China: Present,trend and future[J]. Land Use Policy,2012,29(4): 737-749.   
[47] 曹祺文,顾朝林,管卫华.基于土地利用的中国城镇化SD模型 与模拟[J].自然资源学报,2021,36(4):1062-1084.[Cao Qiwen, Gu Chaolin,Guan Weihua.China’s urbanization SD modelling and simulation based on land use[J]. Journal of Natural Resources, 2021,36(4): 1062-1084.]

# Land use in the Gan-Lin-Gao region of middle reaches of Heihe River Basin based on a PLUS-SD coupling model

JIANG Xiaofang¹²， DUAN Hanchen1,³，LIAO Jie1,³， SONG Xiang1³， XUE Xian1,3 (1.Key Laboratoryof DesertandDesertification,Northwest Institute of Eco-Environment and Resources,Chinese Academy of Sciences,Lanzhou 730ooo,Gansu, China; 2. University of Chinese Academy of Sciences,Beijing 100049,China;3.Drylands Salinization Research Station,Northwest Instituteof Eco-Environmentand Resources, Chinese Academy of Sciences,Lanzhou 73oooo, Gansu, China)

Abstract: A quantity-space coupling model can effectively simulate the number of land-use patches and their rapid spatial changes.Thus,this model has become the main method of land use research in recent years.This research first compared the simulated land-use structure of the patch-generating land-use simulation model (PLUS), future land-use simulation model (FLUS),and conversion of land use and its efects at small regional extent (CLUE-S) in the Gan-Lin-Gao region (Ganzhou District,Linze County and Gaotai County of Zhangye City)of the middle reaches of the Heihe River Basin in 2015.In addition,this research selected the suitable spatial simulation model for the study area; then,it was coupled with the system dynamics model (SD)to form a quantitative-spatial coupling model. Finally,the coupling model was used to predict the land-use structure of the economic development (ED), ecological protection (EP)，and harmonious development (HD） scenarios,and comparative evaluation was conducted.The research results showed that (1)at the same pixel scale,the figure of merit of the PLUS model was higher than that of the FLUS and CLUE-S models,and the $K _ { \mathfrak { n } \mathfrak { o } }$ and $K _ { \mathrm { l o c a t i o n } }$ of the three models were PLUS, CLUE-S,and FLUS from high to low,indicating that the PLUS model had the best spatial fiting effect in this studyarea. (2) Moreover,the different scenarios predicted by the PLUS-SD coupling model showed that the construction land and arable land in the ED scenario expanded rapidly,but the forest coverage rate was low. Furthermore,the forest coverage rate in the EP scenario increased significantly,but the level ofEDwas low,and theurbanization in the HD scenario improved when the ecological environment was gradually developing.This research determined the significant advantages of the PLUS-SD coupling model and highlighted the effective land-use spatial simulation capabilities of the PLUS model and powerful data processng capabilities of the SD model. The results can provide reference for the formulation of land planning policies.

Keywords: the middle reaches of the Heihe River Basin； coupling model; land use/cover change; scenario prediction