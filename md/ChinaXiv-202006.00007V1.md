# 大西安地区土地利用类型时空演变分析

马新萍，韩申山'，王磊²，王建兴，许晓婷}（1咸阳师范学院资源环境与历史文化学院,陕西咸阳712000；2山东金田勘察设计有限公司,山东济南250000)

摘要：通过多种方法分析大西安地区土地利用类型演变特征、空间变化特征及其影响因素，旨在为大西安地区土地利用优化发展提供科学基础。在GIS 和RS技术的支持下,对区域1996年、2006年、2016年3期LANDSATTM(OLI)遥感影像进行解译，采用土地利用转移矩阵和土地利用变化模型对大西安1996年以来土地利用类型和土地覆被时空动态变化进行量化分析，结果表明：（1）大西安近20a来建设用地面积不断增加，耕地、林业用地面积总体减少，草地小幅增加,水域略有萎缩,各地类间相互转换频繁。（2）土地利用综合程度较高且不断加强，土地利用结构趋于均衡。(3）空间变化上，土地利用变化区域差异显著,建设用地、耕地、林业用地重心转移的速度呈现出先快后慢的阶段性特征。（4）综合相关文献，大西安地区土地利用变化的驱动因素主要为政策因素。论文从时空变化角度首次提出大西安地区的土地利用演变规律,该结果可为大西安地区发展过程中的土地优化提供科学基础。

关 键 词：大西安地区；土地利用类型；时空变化；土地利用变化模型文章编号：

中西部地区是我国经济区域发展战略的平衡点，西安则是西部地区经济发展的中心之一。在“一带一路"倡议背景下,西安市政府提出大西安规划，旨在将西安建成关天经济区核心城市、国家区域中心城市和现代化国际大都市，西安建设国际化大都市，对于西部的引领辐射作用具有重要意义，将形成整个国家经济区域协调化的带动点。大西安地区包括西安市行政区域、咸阳市城区和西咸新区，相应辐射到咸阳其他县区，该地区的土地利用覆被演变分析将为整个区域的发展规划调整提供重要数据基础。

由于大西安规划及其发展战略近几年开始实施，并且正处于快速发展建设阶段，因此关于大西安地区土地利用变化的研究较少，更多的是关中地区、西安市或者咸阳市的土地利用类型及其驱动力研究,例如,李凤霞等[1]基于多时相TM/ETM $^ +$ 数据，以RS和GIS技术为支撑,辅助土地利用动态度和土地利用耗减度等定量指标，分析了西安1995—

2010年的土地利用时空动态变化，结果表明，16a间西安市城区土地利用空间格局发生了较大变化，土地利用时空演变以速度加快、强度显著、建设用地急剧扩张，占用大量耕地、林地为主要特征；王晓峰等[2]以5期(1975年、1990 年、2000 年、2005年和2010 年)土地利用现状数据为基础，提取建设用地变化及空间分布信息，利用建设用地扩展指数和建设用地密度分析方法对近36a来(1975—2010 年）西安市建设用地扩展的时空特征进行分析，结果表明：西安市建设用地面积急剧增长，建筑密度不断加大，并且城乡空间差异较大，同时西安市建设用地扩展是多因素综合作用的结果。孙恺等[3]以2000 年和2009年2期TM遥感影像及2012年高分辨率ZY-3遥感影像为主要信息源，通过支持向量机的监督分类方法以及景观指数分析法，分别得到2000—2012年间西安市主要城区景观格局演变状况，结果表明，2000—2012年间西安市城市景观格局破碎化和同质化并行，建筑用地面积增加 $7 2 . 6 8 \%$ ,林地景观面积减少 $9 . 0 1 \%$ ,水体景观面积减少 $2 4 . 0 5 \%$ ,耕地面积减少 $5 3 . 9 6 \%$ ，人为活动影响显著。周自翔等4 通过研究关中土地利用变化对净第一性生产力的影响，提出关中经济区高速发展的同时，应以退耕还林、还草为宗旨，在适当的范围内控制好城镇用地的增长速度。李慧等[5]通过研究城市化对河流水文过程的影响发现西安市土地利用程度较高，土地利用变化表现为耕地及林地向建设用地转移。张乐勤等[对快速城镇化背景下建设用地扩展驱动力研究的总结发现，现阶段我国正处于城镇化、工业化加速发展时期，建设用地空间扩展特征十分明显，建设用地扩展不仅危及国家粮食安全，而且会涉及失地农民的补偿、安置和生态等一系列问题。本文结合大西安规划中的范围，对大西安地区的土地利用时空演变分析进行了具体分析，旨在揭示在大西安政策背景下，该区域的土地利用类型变化呈现怎样的特征？其为后续的大西安发展会产生怎样的影响？文章对大西安地区的土地利用结构、土地利用变化速率、土地利用程度及其空间上的变化差异和主要地类的空间转移情况进行了具体分析，主要总结大西安地区土地利用变化特征及其为后续规划发展的影响，对当前及未来大西安地区发展过程中的政策制定和规划修改具有参考意义。

# 1研究区概况与数据来源

# 1.1 研究区概况

大西安规划于2016年首次亮相，其初步规划城市建成面积 $8 0 0 ~ \mathrm { k m } ^ { 2 }$ 、人口1000万以上，旨在将西安建设成为引领关中、带动全省、辐射全国的现代化大都市。大西安地区位于陕西中部关中平原腹地，南依秦岭，北靠北山，包括西安市(11区2县）、咸阳市秦都区、渭城区、兴平市、武功县、泾阳县、三原县、礼泉县、乾县、杨凌农业高新技术产业示范园、渭南市、富平县，东西长约 $1 0 0 ~ \mathrm { k m }$ ，南北宽 $7 0 ~ \mathrm { k m }$ ，总面积$1 7 ~ 5 2 4 . 7 3 ~ \mathrm { k m } ^ { 2 [ 7 ] }$ （图1）。研究区内大部分属暖温带半湿润大陆性季风气候，光、热、水资源丰富。年平均气温 $1 3 \mathrm { ~ } \mathrm { { ~ ‰ ~ } }$ ,年降水量 $5 2 2 \sim 7 1 9 ~ \mathrm { m m }$ ,年日照时数可达 $1 \ 6 1 4 \sim 2 \ 1 1 4 \ \mathrm { h }$ 。

![](images/1e2da35b3bcd085516cce72a196b7bab0cb3c75137e4a8553c251c6e615ccbd5.jpg)  
图1研究区范围  
Fig.1Scope of study area

# 1.2 数据来源

1.2.1遥感影像数据文中用到的数据包括大西安地区1996年5月11日、2006年4月26日、2016年5月2日3期LANDSATTM（2016年为OLI）影像,研究区域需3景影像，条带号和行编号依此为126、36，126、37，127、37，空间分辨率为 $3 0 \mathrm { ~ m ~ } \times 3 0$ m,均来自地理空间数据云数据库（http：//www.gscloud.cn/）。

1.2.2其他数据用于解译结果验证的统计资料来源于陕西省统计年鉴（http：//www.shaanxitj.gov.cn/）、陕西省区域统计年鉴和实地调查，统计年鉴数据来自于统计年鉴分享平台（http：//www.year-bookchina.com/）。

# 2研究方法

# 2.1遥感影像预处理与分类解译

对大西安地区3期遥感影像分别进行几何校正、图像增强、镶嵌与裁剪等预处理工作。土地利用分类系统在参照中国土地利用现状分类国家标准（GB/T21010—2007）[8]的基础上，综合考虑遥感影像的解译能力、研究区域主要地类以及科学性、系统性、实用性原则，对大西安地区土地利用类型分为5个一级类、15个二级类(表1）。

采取监督分类与非监督分类相结合的方式，根据遥感数据的特征标志和判读的知识经验，对研究区域3期遥感影像进行分类。采用精度评估工具（AccuracyAssessment）对分类结果进行评价，可得到整体分类精度分别为 $8 5 . 8 \%$ ） $8 8 \%$ 、 $87 \%$ ,Kappa系数分别为 $0 . 8 4 1 2 . 0 . 8 5 6 3 . 0 . 8 4 9 1$ ，说明分类结果精度较高，符合精度要求。结合实际对解译图像的小图斑进行分类后处理，最终得到1996年、2006

# 表1土地利用分类体系

Tab.1 Land use classification system   

<html><body><table><tr><td>级类</td><td>二级类</td><td>含义</td><td>影像解译标志</td></tr><tr><td>耕地旱地、水浇地</td><td></td><td>休地</td><td>包括粮食作物用地、菜地、已有耕地、新垦地、轮深紫色或浅紫色,呈规则或不规则块状、连续成 片分布、内部单元格多为矩形</td></tr><tr><td>林地</td><td>乔木、灌木、其他林地</td><td>包括公园、沿河湖等较大面积人工林,不包括居翠绿色或绿色,均质、成片、大面积分布,形状不 民点、道路旁等小范围绿化林地</td><td>规则,无明显边界</td></tr><tr><td>草地</td><td>果园、天然草地、人工草地</td><td>以草本植物为主的土地、覆盖度在5%以上的较深绿色或绿色,不规则形状呈面状分布无较 各类草地</td><td>明显边界</td></tr><tr><td>建设 用地</td><td>其他建设用地</td><td>居民点、交通用地、工矿用地、包括其他各种建筑设施,不包括田间道路</td><td>紫色、粉紫色以及绿色夹杂，规则或不规则块状 分布；交通用地为明显的线形</td></tr><tr><td>水域</td><td>河流、湖泊、人工水库</td><td>不包括季节性流水冲沟、废弃河道</td><td>黑色、深棕色,线状、条带状、树枝状</td></tr></table></body></html>

![](images/987a4ddfee4077e0c5b92717920be76a8b079e708ee1732cea72e3dabb30277f.jpg)  
图2土地利用分类结果  
Fig.2Results of land use classification

年、2016年大西安地区土地利用类型图（图2）。

# 2.2土地利用类型转移矩阵

采用土地利用转移矩阵来反应每种土地利用类型的变化量和各土地利用类型间转化量，其公式原理参考文献[9]。将原公式中每个具体的单一值 $S _ { i j }$ $A _ { i j }$ 更改为矩阵 $\begin{array} { r l } { S _ { i j } = } & { { } V _ { i j } } \end{array}$ ，式中： $A _ { i j }$ 为原矩阵中 $S _ { i j } \colon V _ { i j }$ 为$R _ { i j }$ 研究期间 $i$ 转为 $j$ 地类占 $i$ 总转出的比重; $R _ { i j }$ 为研究期间 $i$ 转为 $j$ 地类占 $j$ 总转入的比重。这样,不仅能反映各种地利用类型研究期间的变化情况、各地类之间相互转化的数量关系，还能反应出各种土地利用类型转化的结构特征。

# 2.3 土地利用变化模型

本文采用的土地利用变化模型包括：土地利用变化速度模型、综合土地利用动态度模型、土地利用程度综合指数模型、土地利用相对变化率模型以及土地利用重心模型。土地利用变化速度模型是衡量土地利用类型覆被演变快慢的重要指标，其具体公式见参考文献[9-10]。

综合土地利用动态度模型[10]能够反映土地利用类型转化方向的差异以及人为改造土地覆被过程的速度。土地利用程度模型主要反映人类活动对土地改造利用的深度和广度[1]

$$
L = 1 0 0 \times \sum _ { t = 1 } ^ { n } \left( a _ { i } \times r _ { i } \right)
$$

式中： $L$ 代表土地利用程度综合指数; $a _ { i }$ 指第 $\mathbf { \chi } _ { i }$ 级土地利用类型分级指数； $r _ { i }$ 指第 $i$ 级地类面积比重； $n$ 是土地利用分级个数。

土地利用相对变化率[12 能较好地反应土地利用变化的区域差异，土地利用相对变化率数学模型为[13-14]：

$$
R = \frac { \left( \frac { s _ { a } } { s _ { b } } \right) } { \left( \frac { S _ { a } } { S _ { b } } \right) }
$$

式中： $s _ { a } \ldots s _ { b }$ 分别指某子区域单一地类研究期末和期初的数量； $S _ { a \setminus S _ { b } }$ 分别指兴趣区单一地类研究期末和期初的数量；若 $R > 1$ ,则该区域变化快于整个区域，否则，该区域落后于整个区域。

土地利用信息熵[15]反映了土地利用系统的有序程度，土地利用信息熵值越大，不同土地利用类型越多，面积相差越小，结构越均衡。具体公式见参考文献[12]。

# 3结果与分析

# 3.1土地利用/覆被数量结构变化分析

大西安地区土地类型主要以耕地、林地和建设用地为主（图3），1996—2006年，增加幅度最大的为建设用地，减少幅度最大的为草地，其次为水域和林地(表2、图4)；建设用地的主要转入类型为耕地、林地和水域，草地的主要转出类型为林地（表3）。2006—2016年，增加幅度最大的为草地，其次为建设用地(表2、图4)，草地和建设用地的主要转入类型均为耕地;减少幅度最大的为水域，其次为耕地，水域转出类型主要有耕地和建设用地，耕地的转出类型主要是建设用地和林地（表4）。

![](images/4bea222c0636a9ecbe1e284c5976d355ccfe2ab0e62de7ec7d064737cc2a45a8.jpg)  
图3土地利用类型面积图Fig.3Map of land use type area

1996一2016年，耕地面积呈现先增加后减少的趋势特征，耕地的主要转出类型为建设用地；增加幅度最大的为建设用地，其次为林地。总体上，近20a

# 表2土地利用变化幅度表

Tab.2Table of land use change range   

<html><body><table><tr><td rowspan="2">土地利用类型</td><td colspan="2">土地利用类型面积／km²</td></tr><tr><td>1996年</td><td>2006年 2016年</td></tr><tr><td>耕地</td><td>2 155.40</td><td>2 838.24 5 053.31</td></tr><tr><td>林地</td><td>6 907.86</td><td>6 223.58 6120.13</td></tr><tr><td>建设用地</td><td>7 998.86</td><td>8 171.97 5 936.67</td></tr><tr><td>水域</td><td>186.92</td><td>150.84 105.69</td></tr><tr><td>草地</td><td>275.69</td><td>140.11 308.94</td></tr><tr><td rowspan="2">土地利用类型</td><td></td><td>土地利用变化幅度／%</td></tr><tr><td>1996—2006 年</td><td>2006—2016 年 1996—2016年</td></tr><tr><td>耕地</td><td>2.16</td><td>- 27.35 -25.78</td></tr><tr><td>林地</td><td>-9.91</td><td>-1.66 -11.40</td></tr><tr><td>建设用地</td><td>31.68</td><td>78.04 134.45</td></tr><tr><td>水域</td><td>-19.30</td><td>-29.93 -43.46</td></tr><tr><td>草地</td><td>-49.18</td><td>120.50 12.06</td></tr></table></body></html>

![](images/fd5434c83654da8719ce9a1ff8b463c453620097df2193c1634abc6510c4e551.jpg)  
图4土地利用变化幅度图  
Fig.4Diagram of land use change amplitude

# 表31996—2006年土地利用转移矩阵／km²

Tab.3Land use transfer matrix from 1996 to $2 0 0 6 / \mathrm { ~ k m } ^ { 2 }$   

<html><body><table><tr><td colspan="3"></td><td colspan="6">2006年</td></tr><tr><td colspan="3"></td><td>建设用地</td><td>林地</td><td>耕地</td><td>水域</td><td>草地</td><td>总计</td></tr><tr><td rowspan="10">1996年</td><td>建设用地</td><td>转化面积／km²</td><td>1 851.70</td><td>77.90</td><td>217.60</td><td>7.60</td><td>0.60</td><td>2 155.40</td></tr><tr><td rowspan="3"></td><td>转出比重／%</td><td>1</td><td>25.65</td><td>71.66</td><td>2.51</td><td>0.18</td><td></td></tr><tr><td>转入比重／%</td><td>1</td><td>14.05</td><td>18.54</td><td>27.42</td><td>0.65</td><td></td></tr><tr><td>转化面积／km²</td><td>228.30</td><td>5 669.30</td><td>916.50</td><td>9.50</td><td>84.30</td><td>6 907.90</td></tr><tr><td rowspan="3"></td><td>转出比重／%</td><td>18.44</td><td>1</td><td>74.00</td><td>0.76</td><td>6.81</td><td></td></tr><tr><td>转入比重／%</td><td>23.15</td><td>1</td><td>78.10</td><td>33.96</td><td>97.59</td><td></td></tr><tr><td>转化面积／km²</td><td>720.30</td><td>268.60</td><td>6 998.40</td><td>10.40</td><td>1.30</td><td>7 999.00</td></tr><tr><td rowspan="3"></td><td>转出比重／%</td><td>71.99</td><td>26.84</td><td>1</td><td>1.04</td><td>0.12</td><td></td></tr><tr><td>转入比重／%</td><td>73.01</td><td>48.45</td><td>1</td><td>37.33</td><td>1.45</td><td></td></tr><tr><td>转化面积／km²</td><td>32.90</td><td>7.50</td><td>23.20</td><td>123.00</td><td>0.30</td><td>186.90</td></tr><tr><td rowspan="4"></td><td></td><td>转出比重／%</td><td>51.49</td><td>11.80</td><td>36.28</td><td>1</td><td>0.43</td><td></td></tr><tr><td>草地</td><td>转入比重／%</td><td>3.34 5.00</td><td>1.36</td><td>1.98</td><td>1</td><td>0.32</td><td></td></tr><tr><td>转化面积／km²</td><td></td><td>200.30</td><td></td><td>16.30</td><td>0.40</td><td>53.70</td><td>275.70</td></tr><tr><td>转出比重／%</td><td>2.26</td><td>90.25</td><td>7.33</td><td>0.16</td><td></td><td></td><td></td></tr><tr><td></td><td></td><td>转入比重／%</td><td>0.90</td><td>36.14</td><td>2.93</td><td>0.06</td><td>1</td><td></td></tr><tr><td>总计</td><td></td><td>转化面积／km²</td><td>2 838.20</td><td>6 223.60</td><td>8 172.00</td><td>150.80</td><td>140.10</td><td>17 524.80</td></tr></table></body></html>

# 表42006—2016年土地利用转移矩阵／ $\mathbf { k m } ^ { 2 }$

Tab.4Land use transfer matrix from 2006 to $2 0 1 6 / \mathrm { ~ k m } ^ { 2 }$   

<html><body><table><tr><td colspan="3"></td><td colspan="6">2016年</td></tr><tr><td></td><td></td><td></td><td>建设用地</td><td>林地</td><td>耕地</td><td>水域</td><td>草地</td><td>总计</td></tr><tr><td>2006年</td><td>建设用地</td><td>转化面积／km²</td><td>2 016.20</td><td>102.10</td><td>618.50</td><td>3.50</td><td>98.60</td><td>2 838.90</td></tr><tr><td></td><td></td><td>转出比重／%</td><td>1</td><td>12.42</td><td>75.17</td><td>0.42</td><td>11.99</td><td></td></tr><tr><td></td><td></td><td>转入比重／%</td><td>1</td><td>14.68</td><td>56.90</td><td>33.76</td><td>32.21</td><td></td></tr><tr><td></td><td>林地</td><td>转化面积／km²</td><td>317.20</td><td>5 424.50</td><td>451.60</td><td>2.20</td><td>29.20</td><td>6 224.70</td></tr><tr><td></td><td></td><td>转出比重／%</td><td>39.64</td><td>1</td><td>56.44</td><td>0.27</td><td>3.64</td><td></td></tr><tr><td></td><td>耕地</td><td>转入比重／%</td><td>10.44</td><td>1</td><td>41.58</td><td>21.15</td><td>9.52</td><td></td></tr><tr><td></td><td></td><td>转化面积／km²</td><td>2 672.50</td><td>469.40</td><td>4 850.40</td><td>4.60</td><td>175.20</td><td>8 172.10</td></tr><tr><td></td><td></td><td>转出比重／%</td><td>80.46</td><td>14.13</td><td>1</td><td>0.14</td><td>5.27</td><td></td></tr><tr><td></td><td>水域</td><td>转入比重／%</td><td>88.00</td><td>67.48</td><td>1</td><td>44.65</td><td>57.21</td><td></td></tr><tr><td></td><td></td><td>转化面积／km²</td><td>34.10</td><td>5.90</td><td>10.80</td><td>96.90</td><td>3.20</td><td>150.90</td></tr><tr><td></td><td></td><td>转出比重／%</td><td>63.11</td><td>10.97</td><td>19.97</td><td>1</td><td>5.96</td><td></td></tr><tr><td>草地</td><td></td><td>转入比重／%</td><td>1.12</td><td>0.85</td><td>0.99</td><td>1</td><td>1.05</td><td></td></tr><tr><td></td><td></td><td>转化面积／km²</td><td>13.30</td><td>118.20</td><td>5.80</td><td>0.10</td><td>2.80</td><td>140.20</td></tr><tr><td></td><td></td><td>转出比重／%</td><td>9.70</td><td>86.05</td><td>4.21</td><td>0.03</td><td>1</td><td></td></tr><tr><td></td><td></td><td>转入比重／%</td><td>0.44</td><td>17.00</td><td>0.53</td><td>0.44</td><td>1</td><td></td></tr><tr><td></td><td>总计</td><td>转化面积／km²</td><td>5053.30</td><td>6120.10</td><td>5 937.10</td><td>107.30</td><td>309.00</td><td>17 526.80</td></tr></table></body></html>

来大西安地区土地利用类型仍以耕地、林地和建设用地为主，三者面积占总面积的 $90 \%$ 以上,耕地一建设用地、林地一草地之间的转化较为频繁，水域面积减少较为迅速，建设用地呈现明显的逐年扩张的趋势。

表5显示了各土地利用类型从期初到期末的年均变化速率，正值表示该地类增加，负值表示该地类减少。从各地类变化率可以得出：1996一2006年建设用地增长速度较快,水域和草地减少速率较高，耕地和林地变化较小;2006—2016年建设用地和草地高速增长，涨幅分别高达 $7 . 8 0 \ \mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ 和12.05$\mathrm { k m } ^ { 2 } \cdot \mathrm { a } ^ { - 1 }$ ，。

# 3.2土地利用动态度及土地利用程度变化分析

为反映各地类之间的转化速率，引入综合土地利用动态度模型对大西安地区两个时段土地利用的动态度进行计算,计算结果为： $R _ { 1 9 9 6 - 2 0 0 6 } = 0 . 8 1 \%$ 、$R _ { 2 0 0 6 - 2 0 1 6 } = 1 . 4 7 \%$ ,结果再次验证大西安地区各地类间相互转化频度较高，综合土地利用动态度较高，且两个时段呈逐渐增长趋势。

Tab.5Land use change rate   

<html><body><table><tr><td>地类</td><td>建设 用地</td><td>林地</td><td>耕地</td><td>水域</td><td>草地</td></tr><tr><td>1996—2006 年平均变化 速率／km²·a-1</td><td>3.17</td><td>-0.99</td><td>0.22</td><td>-1.93</td><td>-4.92</td></tr><tr><td>2006—2016年平均变化</td><td>7.80</td><td>-0.17 -2.74</td><td></td><td>-2.99</td><td>12.05</td></tr></table></body></html>

此外,参考庄大方等[13]在中国土地利用区域分异研究中提出的分级指数（表6），利用土地利用程度变化综合指数模型计算大西安地区1996一2006年土地利用程度综合指数（表7），土地利用综合指数表明，1996年以来，大西安地区土地利用综合指数一直呈增长趋势，在土地利用分级指数中建设用地和林地位居前列。

由图5可知，1996—2016年大西安地区土地利用信息熵呈现不断增加的趋势，随着土地开发利用程度增加，土地利用信息熵1996一2006 年增加幅度不大，2006—2016年增幅明显，表明大西安地区土地利用系统有序化程度增加，各类土地利用面积差异程度也有所增减小，土地利用结构复杂性和多样性增加。

# 表6土地利用分级指数

表5土地利用变化速率  
表7土地利用程度综合指数  

<html><body><table><tr><td>土地利用 类型</td><td>林地、草地、 水域</td><td>耕地、园地</td><td>居民点、工矿业 用地、交通用地</td></tr><tr><td>分级指数</td><td>2</td><td>3</td><td>4</td></tr></table></body></html>

Tab.6Land use grading index   
Tab.7Comprehensive index of land use degree   

<html><body><table><tr><td>指数</td><td>1996年</td><td>2006年</td><td>2016年</td></tr><tr><td>土地利用程度综合指数</td><td>270.241 6</td><td>279.022 29</td><td>291.546 5</td></tr></table></body></html>

![](images/eee25c3485d5337bdd95b1f8f6ead9b79abbe2a08312304ee6492eac84f6a745.jpg)  
图5土地利用信息熵  
Fig.5Entropy of land use information

# 3.3土地利用空间变化特征

3.3.1土地利用变化区域差异分析图6、图7为大西安土地利用相对变化率空间分布图，1996—2006年，变化较明显的土地类型为耕地，主要分布在武功、咸阳、西安、渭南等地，基本处于大西安东西的中轴线上;2006—2016年变化最明显的是草地，主要是周至、富平、三原和渭南等地区。

3.3.2主要用地类型空间变化与重心转移通过前文研究，得出大西安地区主要用地类型为建设用地、耕地和林地，本节将利用土地利用重心坐标对3种土地利用类型空间变化与重心转移进行分析。根据土地利用重心坐标模型分别计算出3种土地利用类型3a的重心坐标如表8，并绘出重心移动轨迹（图8）。

结果显示：建设用地重心一直落在西安市，在整个区域内偏北，1996—2006 年小幅向东南方向（南偏东 $3 0 ^ { \circ }$ )移动，年均移动距离 $0 . 2 7 ~ \mathrm { k m }$ ,2006—2016年向东北方(东偏北 $3 7 ^ { \circ }$ )向快速移动，年均移动距离 $1 . 5 8 ~ \mathrm { k m }$ ;耕地重心也一直落在西安市，在整个区域内偏北，总体上呈现出先快后慢的南移趋势，1996—2006 年小幅向东南方向（南偏东 $6 0 ^ { \circ }$ )移动，年均移动距离 $0 . 0 6 ~ \mathrm { k m }$ ,2006—2016 年向西南方向（南偏西 $6 0 ^ { \circ }$ )快速移动,年均移动距离 $0 . 3 \ \mathrm { k m }$ ;林地重心一直落在渭南市，1996—2006 年小幅向东北方向(东偏北 $3 3 ^ { \circ }$ )移动,年均移动距离 $0 . 2 4 ~ \mathrm { k m }$ 2006—2016 年以较快速度向西南方向（南偏西 $6 0 ^ { \circ }$ ））移动,年均距离 $0 . 7 7 ~ \mathrm { k m }$ 。

# 3.4土地利用变化影响因素分析

土地利用变化的影响因素主要包括自然因素和人类活动。其中人类活动是短期内土地利用变化的主要影响因素。

3.4.1自然因素大西安地区地处关中平原中部,市域内山地、丘陵、平原、台源、河谷等地貌类型多样[14]。气候、地形、地貌等自然环境因子变化的时间尺度往往较长，对于土地利用类型变化的影响仅具有宏观尺度上的意义，对于短时期内的土地利用类型变化影响较小，因此综合其他研究结果，大西安地区土地利用变化影响主要因素主要是人类活动。

3.4.2人类活动影响因素综合相关文献[1,15-17],大西安地区土地利用变化的驱动因素可归结为政策、经济、交通因素。

# （1）政策因素

根据前文研究，大西安地区土地利用变化最显著的特征是建设用地面积增长迅速，土地利用综合指数一直呈较快增长趋势。这与自1999年来国家实施西部大开发建设战略息息相关，国家政策引导西安、咸阳、渭南等大中城市积极发展二三产业，建立大批产业园（如西安航空产业园、西安高新技术开发区）。土地利用类型重心的空间变化也明显受到政策影响，例如，建设用地重心变化先东南后东北，是因为20世纪末期西安市郭杜教育产业园、航天产业园，咸阳市渭河南岸建设工业、商品性建筑等的开发。城市化导致西安、咸阳人口呈线性增长，2002年12月28日西安咸阳经济一体化协议签订[18],西咸新区的设立以及大规模基础设施的建立导致建设用地大量增加，充分说明政策导向决定了建设用地的急剧扩张。

# （2）经济因素

经济对土地类型的影响主要体现在2个方面，一个是土地利用类型的多样化，各类型土地利用面积趋于平衡;另外一方面是建设用地急剧增加。农业内部结构调整，促使低效益的农用地向高效益的农用地转换，耕地转变为园地、养殖业等，产业结构的多样协调化发展，一方面导致经济提升，同时也促使用地类型向多样化发展，经济产业结构的协调发展促使经济水平大幅度提高，人均GDP也保持持续增长水平，1985—1990年，西安市人均GDP增长了22.3倍，建设用地以 $3 5 \%$ 的速率扩展。

# （3）交通因素

十几年来，西安、咸阳周边的西宝高速、西万公路、西铜公路、西临公路以及绕城高速公路的修建对土地利用变化产生巨大影响。密集的交通网有力的推进了城市化进程，使得城市规模有了很大发展，但同时也使得耕地等非建设用地大量流失。

![](images/828d5b20819ad4e1ae1483cfc05b001a1690f7eb1d8a351744e1cabe1a60a094.jpg)  
Fig.6Statistical chart of relative change rate between 1996 and 2006

![](images/2008fe08125862f03f7b07a1840cc4a3b8e52a0ff084af847acd54085952e61f.jpg)  
图61996—2006 年相对变化率统计图  
图72006—2016年相对变化率统计图  
Fig.7Statistical chart of relative change rate between 2OO6 and 2016

表8主要地类重心坐标  
Tab.8Barycenter coordinates of the main ground class   

<html><body><table><tr><td rowspan="2">地类</td><td colspan="2">1996年</td><td colspan="2">2006年</td><td colspan="2">2016年</td></tr><tr><td>x/E</td><td>y/N</td><td>x/E</td><td>y/N</td><td>x/E</td><td>y/N</td></tr><tr><td>建设用地</td><td>109.148 10</td><td>34.611 78</td><td>109.160 60</td><td>34.589 45</td><td>109.288 30</td><td>34.684 82</td></tr><tr><td>耕地</td><td>109.182 70</td><td>34.680 60</td><td>109.188 60</td><td>34.676 92</td><td>109.160 30</td><td>34.660 41</td></tr><tr><td>林地</td><td>109.503 60</td><td>34.657 95</td><td>109.524 20</td><td>34.671 64</td><td>109.454 80</td><td>34. 632 17</td></tr></table></body></html>

109°09'00"E 109°18'00"E 109°10'05"E 109°11'15"E 109°28'00"E 109°32'00"E富平县三原县 200000 1996年 200000 N  
8.00.6000 8.0.900 2006年 200.00 西安市 2006年 1.00.000 A三原县 西安市 渭南市1996年 图例1996年 西安市 2.00.9000 1002000 00200 ·移标点迹500.3000 2016年市县界2006年 (a)建设用地 2016年 (b)耕地 (c)林地西安市  
109°09'00"E 109°18'00"E 109°10'05"E 10928'00"E 109°32'00"E

# 4结论

（1）时间变化上，1996年以来，大西安地区建设用地面积快速增加，林业用地面积持续减少，耕地先增后减，变化幅度较大，水域呈缓慢萎缩趋势，各地类间相互转化频繁，土地利用综合程度较高，结构趋向均衡化。

(2）空间变化上，1996—2016年，大西安地区土地利用变化区域差异明显，建设用地和草地空间差异较大。研究区建设用地、耕地、林业用地重心转移速率上均呈现出阶段性特征。

(3）大西安地区土地利用变化的主导因素是人类活动，具体可归结为政策、经济和交通因素，其中最主要的为政策因素。

# 参考文献(References)

[1］李凤霞,石辉,冯晓刚,等.西安市土地利用格局动态演变及其 驱动力研究［J].测绘通报,2015,（12）：41-45.［LIFengxia, SHI Hui,FENG Xiaogang,et al. Study of land use dynamic evolution and driving factors in Xi'an[J].Bulletin of Surveying and Mapping,2015,（12）:41-45.]   
[2]王晓峰,傅伯杰,苏常红,等.西安市城乡建设用地时空扩展及 驱动因素［J].生态学报,2015,35（21）：7139-7149.［WANG Xiaofeng,FU Bojie,SU Changhong,et al.Spatio-temporal characteristics and& driving forces ofbuilt-up land in Xi'an,China[J]. ActaEcologica Sinica,2015,35(21）:7139-7149.]   
geoaetc center ol gravity   
[3]孙恺,杨延征,赵鹏祥,等.基于遥感技术的西安城市景观格局 时空演变及分析[J].西北林学院学报，2015,30（2）：180- 185.[SUN Kai,YANG Yanzheng,ZHAO Pengxiang,et al. Spatial temporal evolution of landscape pattern in Xi'an based on 3S technology[J].Journal of Northwest Forestry University,2O15,30(2）： 180 -185.]   
[4］周自翔,李晶,韩艳飞.关中一天水经济区土地利用变化对净 第一性生产力影响测评[J].干旱区地理,2013,36(6)：1058- 1066.［ZHOU Zixiang,LI Jing,HAN Yanfei. Evaluation and effect of LUCC on NPP in Guanzhong-Tianshui economic zone[J].Arid Land Geography,2013,36(6):1058-1066.]   
[5]李慧,周维博,马聪,等.城市化对西安市降水及河流水文过程 的影响［J].干旱区地理,2017,40（2)：322-331.［LIHui, ZHOU Weibo,MA Cong,et al.Effects of urbanization on regional precipitation and river hydrological process in Xi'an City[J]. 2017,40(2) :322 -331.]   
[6]张乐勤,陈素平,王文琴,等.快速城镇化背景下建设用地扩展 驱动力研究述评与展望[J].干旱区地理,2013,36(1)：164- 175.［ZHANG Leqin,CHEN Suping,WANG Wenqin,et al. Review and prospect on driving force research of construction land expansion in the context of rapid urbanization[J].Arid Land Geography,2013,36(1):164-175.]   
[7］西安市人民政府.大西安(西安市一西咸新区)国民经济和社 会发展规划（2017—2021）[EB/OL].http://www.xa.gov.cn/ ptl/def/def/index_1121_6774_ci_trid_2786338.html.[Xi'an Municipal People's Government.National economic and social development plan of Xi'an（Xi'an Xixian New Area）（2017- 2021）［EB/OL].htp://www.xa.gov.cn/ptl/def/def/index_ 1121_6774_ci_trid_2786338.html.]

[8］陈百明，周小萍.《土地利用现状分类》国家标准的解读[J].自

然资源学报,2007,22（6）:994-1003.［CHENBaiming,ZHOUXiaoping.Interpretation of the national standard of“classificationof land use status quo"[J]. Journal of Natural Resources,2007,22(6):994-1003.][9]唐华俊,吴文斌,杨鹏，等.土地利用/土地覆被变化(LUCC)模型研究进展［J].地理学报，2009,64（4）：456-468.［TANGHuajun,WU Wenbin,YANG Peng,etal.Recent progresses of landuse and land cover change(LUCC）models[J].Acta GeographicaSinica,2009,64（4) :456-468.][10］戴声佩,张勃.CLUE-S模型的黑河中游土地利用情景模拟研究——以张掖市甘州区为例[J].自然资源学报,2013,28（2）：  
21-27.[DAI Shengpei,ZHANG Bo.Land use change scenariossimulation in the middle reaches of the Heihe RiverBasinbased onCLUE-S model：A case of Ganzhou District of Zhangye City[J].Journal of Natural Resources,2013,28(2）:21-27.][11］张光凤.临朐县土地利用/覆被变化及其生态系统服务价值评价分析[D].济南：山东师范大学,2014.［ZHANG Guangfeng.Land use/cover change and its evaluation and analysis of ecosystemservice value[D]. Jinan:Shandong Normal University,2014.][12］邴广路，石培基，居玲华.生态脆弱区土地利用变化及驱动因素分析—以张掖市为例［J].干旱区研究,2010,27（2）：  
169-175.［BING Guanglu,SHI Peiji,JU Linghua.Analysis ofland use changes and driving factors in ecologically fragile areas:Acase studyof Zhangye City[J].Arid Zone Research,201O,27(2）:  
169 -175.][13］庄大方，刘纪远.中国土地利用程度的区域分异模型研究[J].自然资源学报,1997,12（2）：105-111.[ZHUANGDafang,LIUJiyuan.Study on the model of regional differentiation of land usedegree in China[J]. Journal of Natural Resources,1997,12（2）：105 -111.]  
[14］陶文芳.西安一咸阳地区土地覆被时空变化及驱动因子研究[D].杨凌：西北农林科技大学,2010.［TAOWenfang.Spatialpattern and driving factors of urbanization in the Xi'an-Xianyangregion,northwest China[D].Yangling:Northwest A&F Universi-ty,2010.]  
[15］杨晓娟，杨永春,张理茜，等.基于信息熵的兰州市用地结构动态演变及其驱动力[J].干旱区地理,2008，31（2)：291-297.[YANG Xiaojuan,YANG Yongchun,ZHANGLiqian,et al.Dy-namic evolution and driving force of the land use structure inLanzhou City based on the information entropy[J].Arid Land Ge-ography,2008,31(2）:291-297.]  
[16]杜国明,匡文慧,孟凡浩,等.巴西土地利用/覆盖变化时空格局及驱动因素[J].地理科学进展，2015,34（1)：73-82.［DUGuoming,KUANG Wenhui,MENG Fanhao,et al.Spatiotemporalpatterns and driving factors of land use/cover change in Brazil[J].Progress in Geography,2015,34（1) :73-82.]  
[17］杨勇.咸阳市土地利用变化与生态安全评价[D].西安：陕西师范大学,20O7.［YANG Yong.LUCC and ecological safety as-sessment in Xianyang City[D].Xi'an:Shaanxi Normal University,2007.]  
[18］杨李娜.咸阳市土地利用变化的动态分析及驱动力研究[D].西安：西北大学,20O9.［YANGLina.Study on the dynamics ofland-use change and driving force in Xianyang City[D].Xi'an:Northwest University,2009.]

# Spatial and temporal evolution of land use types in the greater Xi'an area

MA Xin-ping'，HAN Shen-shan’，WANG Lei²，WANG Jian-xing'， XU Xiao-ting' (1Collegefesourcs,Enronment,HstoryndCulture,ianangoalUniversity,ianyangO,aaniin; 2Jintian Survey and Design co.of Shandong,Jinan 25oooo,Shandong,China)

Abstract:The evolution,spatial variation,and influencing factors of land use types in the greater Xi'an area have been insuffciently quantified.Inorder to provideascientific basis for theoptimal useand development of land in the greater Xi'an area,we analyzed and interpreted regional remote sensing images fromthe Landsat Thematic Mapper and Operational Land Imager from 1996,2O06,and 2016.We adopted a land use transfer matrix and land use change model toconduct quantitative analysis of the spatial and temporal changes in land useand landcover since 1996.We supported these tools with GIS and RS technologies.We found that the area of developed land in the greater Xi'anarea,Shaanxi Province,China has increased over the past 2O years,while cultivatedand forested land has decreased.Grassand has increased slightly,while the water area hasshrunk slightly.We noted frequent classification changes.The comprehensive degree of land use was high and constantly strengthened over time,and the land use structure tended to bebalanced.We identified significant regional diferences in land usechange,and the transfer speeds ofthecenters of gravityof construction land,arable land,and forestryland showsthecharacteristics of the stages of speed before slowness.The driving factors of land use change in the greater Xi'an area were mainly policy factors.This paper proposes the land use revolutionruleof the Great Xi'an area forthefirst time from the angle of time and space change.Our results should provide ascientific basis for land use optimization as the greater Xi'an area continues to develop and grow.

Key words:greater Xi'an area; type of land use; time and space change; land use change model