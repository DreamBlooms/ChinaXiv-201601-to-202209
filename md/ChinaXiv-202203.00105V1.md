# 基于多源数据的干旱区盐渍化农田精准管理分区研究

白建铎¹，彭杰¹，史舟²，王玉珍¹，柳维扬¹，李洪义³(1.塔里木大学农学院,新疆 阿拉尔843300；2.浙江大学农业遥感与信息技术应用研究所,浙江 杭州310058；3.江西财经大学旅游与城市管理学院，江西 南昌330000)

摘要：根据土壤盐渍化空间异质性对南疆干旱区绿洲农田进行精准管理分区,对农业种植结构调整和精细化管理具有重要意义。以典型干旱区绿洲农田为研究对象,以电磁感应数据、地形数据和卫星遥感数据为数据源,通过地统计学方法分析研究区土壤盐渍化的空间异质性,利用相关分析筛选出不同时期的植被指数和盐分指数。以农田表层表观电导率( $\mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } }$ )为主变量，深层表观电导率 $( \mathrm { E C _ { h 0 . 7 5 \setminus } E C _ { v 0 . 7 5 \setminus } E C _ { v 1 . 5 } } )$ 、植被指数(RVI、GRVI、EVI)、土壤盐分指数(NDSI、S5、SI-T)为辅助变量,采用面向对象多尺度分割算法对研究区进行分区,并用分区内平均变异系数( $\cdot$ Coefficientof Variation)和莫兰指数（Moran'sI)对分区结果进行评价。结果表明：(1）研究区各土层表观电导率都存在明显空间异质性，且各辅助变量与主变量均存在极显著相关。（2)各分区的平均变异系数较整个研究区的变异系数下降了 $6 0 \%$ ,且基于多源数据分区的区间异质性均高于单一数据分区的区间异质性。（3）从农田耕作角度、分割效果及分区评价原则出发，综合利用表层和深层土壤盐渍化信息的管理分区效果最佳，该分区结果既符合当地农田管理又符合机械化作业要求。研究结果可为南疆干旱区绿洲农田的精准管理分区提供一定的技术和方法借鉴。

关键词：土壤盐渍化；多源数据；表观电导率；面向对象分割；精准管理分区；干旱区

土壤盐渍化不仅是全球面临的生态问题[]，同时也是影响全球灌溉农业最重要的因素之一[2],而且不同程度盐渍化土壤对不同植物和农作物生长发育影响也不尽相同。因此，掌握土壤盐渍化信息可在一定程度上指导农业合理灌溉和合理调整作物布局。近年来，随气候的变化，特别是全球气候变暖将显著影响全球水循环，导致农业用水量急剧减少[3]。在干旱区、半干旱区,土壤盐渍化问题和农业灌溉缺水问题尤为突出。因此在干旱区、半干旱区急需一种根据盐渍化程度进行变量灌溉和调整作物布局的技术，而精准管理分区是解决此类问题的根本途径，同时也是当前精准农业研究的热点之一[4]

精准管理分区是根据土壤中各种制约产量的影响因子，划分出具有相同均质的子区域，来调整农业投人品和作物布局的措施[5-6]。分区之间实施差异化管理措施有利于提高农业生产投入效率、节约生产成本、保护生态环境，从而实现农业的可持续发展。目前，在精准管理分区方面，国内外学者大多研究采用土壤养分数据和产量相关数据进行插值，再利用模糊聚类算法或自然断点法进行分区管理[7-9],但该方法在数据获取方面需要耗费大量的人力和物力，且不易大面积推广。近年来，随着遥感技术的发展，许多学者开始借助遥感影像数据，再利用面向对象多尺度分割算法或模糊聚类等算法进行分区管理[10-12],但此方法只能间接的通过光谱指数反映出土壤表层属性数据，而不能直接获取到深层土壤属性数据。同时也有部分学者使用土壤属性数据与遥感影像数据相结合的多源数据，利用面向对象多尺度分割算法进行分区管理13，但该方法在土壤属性数据的获取方面也存在费时又费力的缺点，只能在较小区域展开研究。上述研究均是针对土壤养分差异进行管理分区，基于土壤盐渍化差异进行管理分区的研究甚少。干旱区或半干旱区，特别是新疆的南部地区，土壤盐渍化是影响作物产量和品质的关键因子，需根据土壤盐渍化程度采取不同的管理措施，如作物种植结构的合理布局、冬灌或春灌的灌溉量定额。因此在这种土壤盐渍化问题突出且盐渍化变异强的南疆区域，应以土壤盐渍化差异作为分区关键因子进行精准管理分区，才能提高农业效益。传统的土壤盐渍化信息获取方法主要依靠田间调查结合室内分析，存在费时、费力、成本高等方面的不足，再考虑到盐渍化强烈的时空变异特征，该方法很难满足区域尺度土壤盐渍化的调查，而以电磁感应为原理的EM38-MK2大地电导率仪，可快速、高效地直接获取不同深度土壤的表观电导率数据，土壤表观电导率数据与土壤盐分含量具有高度正相关性[14],可有效反映土壤盐渍化程度，使用EM38-MK2大地电导率仪可显著提高土壤盐渍化信息的获取效率，特别是针对区域尺度的调查而言。自20世纪末以来，使用表观电导率来表征土壤盐渍化的方法在土壤盐渍化监测和评价中已得到了广泛应用[15-18],但直接应用表观电导率数据进行农田管理分区的报道鲜见。此外，目前关于农田管理分区的研究普遍只采用了土壤的基本信息，缺乏综合利用土攘信息和作物信息进行管理分区的报道，而卫星遥感技术可以快速获取大面积作物的动态信息，为这种研究思路的实施提供了有力条件。因此可使用土壤表观电导率和遥感影像数据进行土壤盐渍化的分区管理。

综上所述，本研究以南疆干旱区典型绿洲阿拉尔垦区农田为研究对象，以研究区不同深度土壤的表观电导率数据、地形数据和卫星遥感影像数据为数据源，以土壤表层的表观电导率数据为主变量，在分析土壤表观电导率的空间异质性和空间自相关性的基础上，通过相关分析筛选出与表观电导达到极显著相关的卫星遥感光谱指数，并将其作为辅助变量，再利用面向对象多尺度分割算法进行不同输入量下土壤盐渍化的分区，并对不同输入量下的管理分区结果进行评价对比，找到最优管理分区，并提取出研究区各田块的边界，从而根据田块所在的盐渍化分区指导农田的精准灌溉和作物的合理布局，以实现作物优质高产的目的。

# 1研究区概况

研究区位于新疆维吾尔族自治区一师阿拉尔市十二团境内(图1)，地理坐标为 $8 1 ^ { \circ } 1 9 ^ { \prime } 3 1 ^ { \prime \prime } \mathrm { E }$ P$4 0 ^ { \circ } 2 9 ^ { \prime } 5 2 ^ { \prime \prime } \mathrm { N }$ ,面积为 $1 1 4 4 \mathrm { h m } ^ { 2 }$ ,地处塔里木盆地西北部、塔克拉玛干沙漠北缘，天山南麓。境内主要有叶尔羌河、和田河、阿克苏河和塔里木河四大水系。冬季严寒，夏季炎热，日照时间长，降水稀少，蒸发强烈。该区多年平均降水量为 $4 8 . 5 \ \mathrm { m m }$ ,多年平均蒸发量为 $1 9 8 8 ~ \mathrm { m m }$ ，蒸降比高达40.99，系典型的暖温带极端大陆性干旱荒漠气候。研究区地势平坦，土壤质地以砂壤土为主，区域内农田主要种植棉花，棉花生育期内均采用膜下滴灌方式进行灌溉，而春灌和冬灌则采用大水漫灌的方式。大水漫灌旨在将整个棉花生育期内运移到土壤表层的盐分淋洗到耕层以下，以此降低下茬作物种植的盐害胁迫，其灌溉用水主要来自塔里木河。研究区土壤盐渍化程度差异较大，种植结构单一，冬春灌采用统一灌溉量进行灌溉，不仅易造成局部田块压盐不彻底导致盐害现象产生或过度淋洗浪费水资源，同时也造成研究区作物布局不合理导致作物经济效益下降，因此，研究区迫切需要根据不同盐渍化程度来进行变量灌溉和种植结构的调整

![](images/f6cc23fd57af44d2b19c32e2c5cd0b9ae3859a3f0fbef7552fd3eaf501a4f430.jpg)  
图1研究区位置及样点分布示意图  
Fig.1 Location of the study area and distribution of sample points

# 2数据的获取与研究方法

# 2.1多源数据的获取

2.1.1电磁感应数据的获取土壤表观电导率数据采集仪器为大地电导率仪(EM38-MK2)，在棉花收获后冬灌前的11月上旬进行土壤表观电导率数据的采集。每次采集表观电导率时，首先将大地电导率(EM38-MK2)设置为手动测定模式，并对仪器进行预热和归零校验，待仪器校验完毕后，进行表观电导率的获取；在每个样点采集时，仪器将自动记录每个样点的地理坐标，每个采样点同时采集垂直模式和水平模式两套数据；水平模式采集的为 $0 \sim$ $0 . 3 7 5 \mathrm { ~ m ~ }$ 和 $0 { \sim } 0 . 7 5 \mathrm { ~ m ~ }$ 的2个深度土层的表观电导率数据，即 $\mathrm { E C } _ { \mathrm { h 0 } . 3 7 5 }$ 和 $\mathrm { E C } _ { \mathrm { h 0 . 7 5 } }$ ,垂直模式则为 $0 { \sim } 0 . 7 5 \mathrm { ~ m ~ }$ 和$0 { \sim } 1 . 5 \mathrm { ~ m ~ }$ 的两个深度土层表观电导率数据,即 $\mathrm { E C } _ { \mathrm { v 0 . 7 5 } }$ 和 $\mathrm { E C } _ { \mathrm { v } 1 . 5 }$ ,相邻采样点间距小于 $3 0 0 \mathrm { ~ m ~ }$ 。研究区共随机均匀采集约1200组表观电导率数据(图1)，采集数据描述性统计见表1。

2.2.2 遥感影像数据和地形数据的获取研究采用来源于美国地质勘查局(USGS,http://glovis.usgs.

gov)的Landsat8遥感影像，卫星重访周期为16d,空间分辨率为 $3 0 \mathrm { m }$ 。本文选取2020年棉花生长旺盛期(9月5日)的影像和棉花收获冬灌前(11月4日)的裸土影像。影像经辐射定标、大气校正、图像裁剪等预处理后，使用ENVI5.3软件计算得出9月5日影像的9个植被指数(RVI、DVI、GDVI、GRVI、ND-VI、EVI、NNIR、NR、NG)和11月4日影像的13个土壤盐分指数(NDSI、S1、S2、S3、S5、S6、SI-T、SI、SI1、SI2、SI3、Int1、Int2）。同时通过地理空间数据云(http://www.gscloud.cn）下载空间分辨率为 $3 0 \mathrm { ~ m ~ }$ 的DEM数据，使用ArcGIS10.7软件完成洼地填充、影像裁剪、几何精度校正和高程数据提取。

# 2.2分割方法

2.2.1基于面向对象的多尺度分割面向对象多尺度分割是影像对象的一个两两合并的过程，合并从均匀分布在影像上的影像对象开始[19]。对于每个影像对象，找到一个使它们之间的异质性变化最小相邻影像对象，在异质性变化最小处，2个对象合并成1个更大的对象，每个对象在每个循环中处理1次，直到分割对象的异质性超过用户给定的阈值，合并过程停止[20]。本研究尝试基于多源数据的土壤盐渍化空间变异进行分区，在eCognition软件中首先确定合适的形状因子(Shape)和紧致度因子（Compactness），然后通过调节不同的分割尺度参数(Scaleparameter)，使分区之间表观电导率异质性最大，分区内部电导率同质性最大。

2.2.2确定最优管理分区由于面向对象分割的原则为尽量使分割对象之间的异质性高，同时使分割对象内部的同质性高21，所以为提高分区内部的同质性和分区之间的异质性需要寻找最优分区尺度；根据学者研究，可使用平均分割评价指数的变化来确定最优分割尺度，将平均分割评价指数和尺度参数绘制成曲线图，在平均分割评价指数开始产生明显变化时的前一个尺度参数为最优分割尺度参数[1]。通过在多尺度分割算法中调节分割尺度参数将研究区分为 $\mathbf { \Omega } _ { m }$ 个区域，并计算出不同分割尺度下各区域的标准差和各区域与邻域的平均差分绝对值，其同质性指数用标准差（8)来表示，异质性指数用平均差分绝对值( $\Delta C _ { L }$ )来表示，计算如公式(1）、（2)所示；同时构建对象的分割评价指数(SEI)和平均分割评价指标(ASEI)，计算如公式（3)和(4)所示[22]

表1不同深度表观电导率描述  
Tab.1 Descriptive statistics of apparent electrical conductivity at different depth   

<html><body><table><tr><td>表观电导率</td><td>最小值/(mS·m1)</td><td>最大值/(mS·m-1)</td><td>平均值/(mS·m1)</td><td>变异系数/%</td><td>峰度</td><td>偏度</td></tr><tr><td>EChb0.375</td><td>2.39</td><td>300.98</td><td>59.39</td><td>81.82</td><td>1.54</td><td>1.87</td></tr><tr><td>ECh0.75</td><td>3.23</td><td>287.15</td><td>55.58</td><td>71.95</td><td>1.32</td><td>1.83</td></tr><tr><td>ECv0.75</td><td>1.17</td><td>280.04</td><td>54.67</td><td>74.52</td><td>1.16</td><td>1.72</td></tr><tr><td>ECv1.5</td><td>2.24</td><td>290.43</td><td>54.19</td><td>78.97</td><td>2.82</td><td>1.02</td></tr></table></body></html>

$$
\delta = \sqrt { \frac { 1 } { n - 1 } \sum _ { i = 1 } ^ { n } \bigl ( C _ { L i } - C _ { L } \bigr ) ^ { 2 } }
$$

$$
\Delta C _ { _ L } { = } \frac { 1 } { L } { \sum _ { p = 1 } ^ { N } } L _ { i } \Big | C _ { _ L } { - } C _ { _ L p } \Big |
$$

$$
S E I = \frac { \Delta C _ { L } } { \delta }
$$

$$
A S E I = \frac { 1 } { A } { \sum } _ { i = 1 } ^ { m } A _ { i } { \cdot } S E I _ { i }
$$

式中： $n$ 为某区域内像元的个数； $C _ { L i }$ 为该区域内第$i$ 个像元的属性值; $\boldsymbol { C } _ { L }$ 为该区域的属性平均值; $\delta$ 表示该区域的标准差； $L$ 为该区域的周长； $N$ 表示与该区域相邻区域的个数； $L _ { i }$ 表示与第 $i$ 个相邻区域公共边的长度； $\boldsymbol { C } _ { L p }$ 为第 $p$ 个相邻区域的属性平均值； $\Delta C _ { _ L }$ 表示该区域与邻域的平均差分绝对值；SEI表示分割评价指数； $A$ 表示研究区的总面积， $A _ { i }$ 为 $i$ 个区域的面积; $\mathbf { \Omega } _ { m }$ 为被划分的区域个数； ${ S E I } _ { i }$ 为第 $i$ 个区域的分割评价指数；ASEI表示平均分割评价指数。

# 2.3精准管理分区的评价方法

2.3.1分区内部的同质性根据分区内像元属性值的标准差和平均值，分别计算出各个分区内的变异系数，并考虑到各分区面积大小不同而赋予相应的权重，从而用分区内部变异系数 $( C _ { \mathrm { v } } )$ 的平均值表示同质性，计算如公式(5)所示：

$$
C _ { \mathrm { v } } = \frac { \displaystyle \sum _ { i = 1 } ^ { m } a _ { i } C _ { \mathrm { v } _ { i } } } { \displaystyle \sum _ { i = 1 } ^ { m } a _ { i } } 1 0 0 \%
$$

式中： $C _ { \mathrm { v } _ { i } }$ 为第 $i$ 个分区的变异系数； $a _ { i }$ 为第 $i$ 个分区的面积； $\mathbf { \Omega } _ { m }$ 为被划分的区域个数。 $C _ { \mathrm { v } }$ 越小，分区内变异越小，代表分区内异质性较小，同质性较大。2.3.2分区之间的异质性采用全局莫兰指数 $\textbf { ( } I \textbf { ) }$ 判断空间相关性，根据莫兰指数大小判断分区间异质性高低，其计算如公式(6)所示：

$$
I = \frac { m \displaystyle \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { m } W _ { i j } \big ( y _ { i } - \bar { y } \big ) \big ( y _ { j } - \bar { y } \big ) } { \displaystyle \left( \sum _ { i = 1 } ^ { m } \big ( y _ { i } - \bar { y } \big ) ^ { 2 } \right) \left( \sum _ { i = 1 } ^ { m } \sum _ { i = 1 } ^ { m } W _ { i j } \right) }
$$

式中： $\mathbf { \Omega } _ { m }$ 为被划分的区域个数； $y _ { i }$ 为分区 $i$ 的属性平均值; $\bar { y }$ 为整个研究区的属性平均值; $\boldsymbol { W } _ { i j }$ 为 $i$ 和 $j$ 之间的空间权重，若 $i$ 与 $j$ 相邻,则 $W _ { i j } = 1$ ，否则${ \boldsymbol { W } _ { _ { i j } } } = 0$ 。 $I$ 表示空间相关程度， $I$ 越接近于0,表示分区之间相关程度越低，即分区之间异质性越高，而根据分区评价原则可知，分区之间异质性越高，分区结果越好。

# 3结果与分析

# 3.1土壤盐渍化的空间异质性

根据土壤盐渍化来划分管理分区，需证明该研究区土壤表观电导率具有空间异质性，因此需使用地统计学中半变异函数进行分析。在计算半变异函数时，数据需符合正态分布，否则会出现比例效应。经分析，原始数据呈偏态分布，经平方根转化后基本符合正态分布。通过 $\mathrm { G S ^ { + } }$ 软件获得变异函数的最优模型，其参数如表2所示。

由表2可知，各个土层表观电导率的最优模型均为指数模型，决定系数均大于0.93，且残差均小于1.27，说明该模型可较好地反映研究区土壤盐渍化的空间分布情况。块金值表示人为随机因素造成的空间异质性，各土层表观电导率的块金值在 $3 . 0 5 \sim$ 5.33之间，表明研究区表观电导率存在由人为随机因素所造成的空间异质性。基台值表示人为随机因素和自然结构因素造成的最大程度空间异质性，各土层表观电导率的基台值介于 $6 . 2 7 { \sim } 1 0 . 7 9$ 之间，表明各土层的表观电导率均存在着显著的空间变异。块金值与基台值之比表示随机因素引起的空间异质性占总空间异质性的大小，各土层表观电导率的块金值与基台值之比均接近于 $5 0 \%$ ，表明随机性因素和结构性因素共同影响研究区土壤表观电导率的空间异质性。变程表示空间自相关的最大距离，各土层表观电导率的变程介于 $1 3 8 3 { \sim } 2 5 7 9 \ \mathrm { m }$ 之间，并且采集数据时，各样点距离控制在 $3 0 0 \mathrm { ~ m ~ }$ 之内，均小于变程，表明合理的采样距离不仅可以提高插值的精度，还可以准确地揭示研究区土壤盐渍化的空间异质性。因此可根据土壤盐渍化空间异质性划分管理分区。

表2不同深度表观电导率空间异质性  
Tab.2Spatial heterogeneity analysis of apparent electrical conductivity at different depths   

<html><body><table><tr><td>表观电导率</td><td>模型</td><td>块金值</td><td>基台值</td><td>块金值/基台值/%</td><td>变程/m</td><td>决定系数</td><td>残差</td></tr><tr><td>ECh0.375</td><td>指数</td><td>5.33</td><td>10.79</td><td>49.38</td><td>2579.00</td><td>0.96</td><td>0.92</td></tr><tr><td>ECho.75</td><td>指数</td><td>3.59</td><td>7.18</td><td>49.99</td><td>2148.00</td><td>0.94</td><td>0.68</td></tr><tr><td>EC0.75</td><td>指数</td><td>4.82</td><td>9.64</td><td>49.99</td><td>2067.00</td><td>0.94</td><td>1.27</td></tr><tr><td>ECv1.5</td><td>指数</td><td>3.05</td><td>6.27</td><td>48.61</td><td>1383.00</td><td>0.93</td><td>0.52</td></tr></table></body></html>

# 3.2表观电导率与光谱指数和地形数据的相关性分析

为探究表层土壤表观电导率( $\mathrm { \cdot E C } _ { \mathrm { h 0 . 3 7 5 } }$ )与地形数据(DEM)及经不同时期遥感影像提取所得光谱指数之间的相关性，将DEM数据及所提取的22个光谱数据与表层土壤表观电导率数据在Excel中进行相关系数计算，结果如表3所示。通过分析棉花生长旺盛期9月的9个植被指数可知，DVI和GDVI与土壤表观电导率未达到显著相关，而RVI、GRVI和NDVI等7个植被指数与表观电导率达到极显著相关。对棉花收获后冬灌前11月裸土的13个土壤盐分指数分析可知，NDSI、S3和S5等8个土壤盐分指数与土壤表观电导率达到显著相关，其中NDSI、S5和SI-T与土壤表观电导率达到极显著正相关。此外，由表3可知，植被指数中除NG外其余均与表观电导率呈负相关，而土壤盐分指数却呈相反结果，除 S6外其余均与表观电导率呈正相关;这与彭杰[23]对多光谱波段和光谱指数与电导率的相关性关系研究结论相一致。从地形数据分析可知，DEM数据与表观电导率未达到显著性水平，这主要原因包括两方面，一是研究区地势平坦，削弱了地形条件对盐分空间分布的支配作用，二是灌溉、土壤改良等人类管理活动改变了地形条件控制下盐分空间分布的原始格局。本研究在相关性分析基础上筛选出相关性达到极显著，且相关系数 $r { \geqslant } 0 . 1 0$ 的植被指数和土壤盐分指数，将其作为精准管理分区的辅助变量，可有效提高分区内同质性和分区间异质性，

表3表观电导率与光谱指数和地形数据的相关性分析  
Tab.3 Correlation analysis table of apparent electrical conductivity with spectral index and DEMc   

<html><body><table><tr><td></td><td>光谱指数及地形数据</td><td>相关系数</td><td>计算公式</td></tr><tr><td>植被指数</td><td>比值植被指数(RVI)</td><td>-0.11**</td><td>NIR/R</td></tr><tr><td></td><td>差值植被指数(DVI)</td><td>-0.02</td><td>NIR-R</td></tr><tr><td></td><td>绿度差值植被指数(GDVI)</td><td>-0.02</td><td>NIR-G</td></tr><tr><td></td><td>绿度比值植被指数(GRVI)</td><td>-0.12**</td><td>NIR/G</td></tr><tr><td></td><td>归一化植被指数(NDVI)</td><td>-0.09**</td><td>(NIR-R)/(NIR+R)</td></tr><tr><td></td><td>增强植被指数(EVI)</td><td>-0.11**</td><td>2.5×(NIR-R)/(NIR+6XR-7.5×B+1)</td></tr><tr><td></td><td>近红外归一化(NNIR)</td><td>-0.09**</td><td>NIR/(NIR+R+G)</td></tr><tr><td></td><td>红光归一化指数(NR)</td><td>-0.09**</td><td>R/(NIR+R+G)</td></tr><tr><td></td><td>绿光归一化指数(NG)</td><td>0.09**</td><td>G/(NIR+R+G)</td></tr><tr><td>土壤盐分指数</td><td>归一化差值盐分指数(NDSI)</td><td>0.11**</td><td>(R-NIR)/(R+NIR)</td></tr><tr><td></td><td>盐渍化指数1(S1)</td><td>0.02</td><td>B/R</td></tr><tr><td></td><td>盐渍化指数2(S2)</td><td>0.03</td><td>(B-R)/(B+R)</td></tr><tr><td></td><td>盐渍化指数3(S3)</td><td>0.07*</td><td></td></tr><tr><td></td><td>盐渍化指数5(S5)</td><td>0.10**</td><td>(GxR)/B</td></tr><tr><td></td><td>盐渍化指数6(S6)</td><td>-0.03</td><td>(BxR)/G</td></tr><tr><td></td><td>盐渍化指数(SI-T)</td><td>0.10**</td><td>(R×NIR)/G</td></tr><tr><td></td><td>盐分指数(SI)</td><td></td><td>(R/NIR)×100</td></tr><tr><td></td><td>盐分指数1(SI1)</td><td>0.08*</td><td>SQRT(BXR)</td></tr><tr><td></td><td>盐分指数2(SI2)</td><td>0.07*</td><td>SQRT(GXR)</td></tr><tr><td></td><td></td><td>0.04</td><td>SQRT(G2+R2+NIR2)</td></tr><tr><td></td><td>盐分指数3(SI3)</td><td>0.07*</td><td>SQRT(G2+R2)</td></tr><tr><td></td><td>强度指数1(Int1)</td><td>0.07*</td><td>(G+R)/2</td></tr><tr><td>地形数据</td><td>强度指数2(Int2) 地形数据(DEM)</td><td>0.05 -0.01</td><td>(G+R+NIR)/2</td></tr></table></body></html>

注：\*\*表示通过0.01、0.05水平显著性检验。R、G、B、NIR均为Lantsat8波段反射率,R为红光波段,G为绿波段,B为蓝波段,NIR为近红外波段。

# 3.3基于表层表观电导率与不同变量下的精准管理分区

基于各土层表观电导率空间结构的分析，为了更加直观地揭示研究区土壤盐分的空间异质性特征，使用普通克里格插值法绘制出各土层的表观电导率分布图。因各变量间单位不同，需将筛选出的植被指数(RVI、GRVI、EVI）、土壤盐分指数(NDSI、S5、SI-T)及各土层土壤表观电导率插值图进行标准化处理，将变量控制在0\~1之间。然后将各土层表观电导率插值图重采样为 $3 0 \mathrm { m } { \times } 3 0 \mathrm { m }$ 的像元，保持与其他变量像元大小一致。在棉花收获后，土壤中大部分的盐分在生育期内会通过蒸发作用将深层盐分随水运移到表层土壤，因此本文选取表层表观电导率( $\mathrm { ( E C _ { \mathrm { h 0 . 3 7 5 } } ) }$ )为主变量，其他变量为辅助变量进行管理分区。同时，通过eCognition软件提取出农田边界，进而进行对农田精准管理分区。

通过多次多尺度分割试验确定最为合适的形状因子为0.3，紧致度因子为0.5。在控制形状因子与紧致度因子不变的条件下，通过最优分区评价指数曲线(图2)可知，基于 $\mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } }$ 的最优分割尺度为19，分区数为19；基于 $\mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } }$ 和深层表观电导率的最优分割尺度为19，分区数为16；基于 $\mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } }$ 和植被指数的最优分割尺度为14，分区数为17；基于$\mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } }$ 和土壤盐分指数的最优分割尺度为14,分区数为13。不同变量下的管理分区如图3所示。由图

3可知，不同变量下的分区结果，均可将不同程度电导率区域进行分区，表明基于多源数据的面向对象多尺度分割的管理分区具有可行性。

# 3.4不同输入量下管理分区对比与评价

由图3对比基于不同数据下的4种最优管理分区发现,由于辅助变量的差异，分区结果也存在明显差异。从农田的耕作角度出发,基于 $\mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } }$ 的分区结果,存在相对窄而长的分区，这种分区与实际机械化工作不相符；当引入辅助变量后，分区结果在每个分区中最少有2\~3个田块，与实际机械化工作条件相符合。从分割效果出发，基于 $\mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } }$ 的分割尺度与基于 $\mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } }$ 和深层表观电导率的分割尺度相同，但分区个数有差异，这可能是由深层土壤表观电导率与表层表观电导率分布格局不同引起的；基于 $\mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } }$ 和植被指数的分割尺度与基于 $\mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } }$ 和土壤指数的分割尺度相同,但分区个数不同。上述对比只是对不同分区结果进行了定性对比，而未进行定量评价。分区结果的定量评价，需本着分区内同质性最大，且分区间异质性最大原则展开评价，即分区内平均变异系数越小，分区间莫兰指数数值越接近于零，代表分区效果越好。由表4可知，不同数据下各分区内平均变异系数在 $1 3 . 6 0 \% { \sim } 1 8 . 6 5 \%$ 之间，根据刘宁[24]对不同土地利用方式下黄河三角洲土壤特性空间变异研究可知,变异系数在 $0 \sim 2 0 \%$ 之间属于弱变异,在 $20 \% { \sim } 5 0 \%$ 属于中等变异， $> 5 0 \%$ 属于强变异;说明各分区内均属于弱变异；且较整个研究区的变异系数下降了约 $6 0 \%$ ,说明分区内同质性较高。不同数据下各分区间莫兰指数均接近于0,表示各分区间相关性较低，说明各分区间异质性较高。综上从农田耕作角度、分割效果及分区评价原则出发，基于 $\mathrm { E C } _ { \mathrm { h 0 } . 3 7 5 }$ 和深层表观电导率的管理

(b)基于ECh0.375和深层 (c)基于ECh0.375和 (d)基于EC $_ { \mathtt { h 0 . 3 7 5 } }$ 和土壤(a)基于 $\mathbf { \cdot E C _ { \mathrm { h 0 . 3 7 5 } } }$ 分割尺度 表观电导率分割尺度 植被指数分割尺度 盐分指数分割尺度+分区数 180 +分区数 2.2 +分区数 +分区数160F 评价指数 2.2 160 评价指数 120 -评价指数 1.8 100 -评价指数 1.8区尔 4010108060 201816 本 区众 4010108060 1.4评 2 区 10806040 区 806040 1640200 1.4 40200 1.2 200 0.8 200 0.1.2 1.0 F 0.4 y 0.45 10152025 30 5101520 2530 48121620 4812 16 20分割尺度 分割尺度 分割尺度 分割尺度

![](images/872d021f1c41d89f20e318e569b7cf5b7ece0f270a415549a8b8c49243fe6d10.jpg)  
图3不同变量下的最优管理分区  
Fig.3Optimal management zones under different variables

表4基于不同数据集下的分区评价  
Tab.4 Partition evaluation based on different dataset   

<html><body><table><tr><td>分区信息</td><td>分区内变异系数/%</td><td>分区间莫兰指数</td></tr><tr><td>ECh0.375</td><td>13.60</td><td>0.1281</td></tr><tr><td>ECh0.375+深层表观电导率</td><td>15.84</td><td>0.0075</td></tr><tr><td>ECh0.375+植被指数</td><td>18.65</td><td>0.0184</td></tr><tr><td>ECh0.375+土壤盐分指数</td><td>16.30</td><td>0.0168</td></tr></table></body></html>

分区为最佳，因为该分区结果既符合当地农田的管理和机械化作业要求，又可以代表深层盐分的分区，且分区间异质性也最强。基于 $\mathrm { E C } _ { \mathrm { h 0 } . 3 7 5 }$ 和土壤盐分指数的管理分区次之。基于 $\mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } }$ 的管理分区最差，是由于其分区结果存在着窄而长的分区，与实际耕作和机械化作业不相符。

# 4讨论

新疆南疆地区是我国棉花主要生产基地，但该地区盐渍化造成的生态环境恶化、作物生产力下降、土壤肥力降低问题，是制约该地区作物高产的主要障碍因子，因此对该地区盐渍化分区具有重要意义。本研究选取了阿拉尔垦区棉花收获后冬灌前的农田为研究对象，此时期盐分聚集在土壤表层25，且研究区土壤质地以砂壤土为主，保水保肥能力差，土壤中水分，养分不稳定，受环境影响较大，因此在研究区进行盐渍化分区比进行水分，养分分区更有意义。在研究方法上，基于面向对象的多尺度分割算法是目前进行农田管理分区研究中最常用的方法之一，其分区数是由最优分割尺度所决定，不仅消除了人为因素的影响，还能够精准地划分管理分区，但最优分割尺度同时受形状因子、紧致度因子、影像空间分辨率、研究区面积大小等多个因素影响。本文通过与刘焕军等"利用遥感影像对黑土区田块尺度的精准管理分区对比发现，影像分辨率不同其最优分割尺度也不同，且最优分割尺度随着空间分辨率的增加而减小，即空间分辨率越高，分割尺度越小，这与许盼盼2基于高分辨率遥感数据的湿地精细信息提取相一致。但分辨率越高，分割结果可能较为破碎，其分区结果可能不适合新疆这种高度机械化的农事作业的开展。同时最优分割尺度与研究区面积大小也具有一定关系，根据黄万里2对不同面积的森林对象进行多尺度分割发现随着研究区面积的增大，最优分割尺度也随之变大。因此在使用面向对象多尺度分割时不仅要考虑研究区所占面积大小，更要选择合适的分辨率，从而确定最优分割尺度。经对比发现多源数据较单一数据可较好地划分管理分区，且在本质上更具有说服力[2]。本文基于辅助变量的多源数据管理分区消除了过于破碎化的分区，且分区间的异质性也有明显提高，但可能存在数据冗余和计算量增加等问题，因此在后期研究中需改善此类问题。在分区管理方面，接下来将根据盐渍化程度计算出各个分区压盐所需要的灌溉量，通过测量各个分区的土壤自然含水量、土壤容重，田间持水量等基础参数，采用列果斯塔也夫经验公式，进行各个分区灌溉量的计算[23]，从而达到精准灌溉的目标。

# 5结论

本研究运用以电磁感应原理为基础的EM38-MK2大地电导率仪，获取棉花收获后冬灌前表观电导率数据。用半变异函数进行分析，揭示土壤盐渍化的空间异质性。利用空间分辨率为 $3 0 \mathrm { m }$ 的Land-sat8影像不同波段信息，计算出22个光谱指数。将光谱指数和地形数据分别与表观电导率( $\mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } }$ 展开相关性分析，筛选得出3个植被指数和3个土壤盐分指数，并将其作为精准管理分区的辅助变量，最后进行多源数据的土壤盐渍化管理分区研究，所得结论如下：

（1）在半变异函数分析中，各土层表观电导率的基台值与块金值之比均在 $5 0 \%$ 左右，说明研究区土壤盐渍化存在空间变异，且是由随机性因素和结构性因素共同导致的变异，因而可以根据研究区土壤盐渍化程度进行分区。

（2）经相关分析和指数筛选后，9月植被指数(RVI、GRVI、EVI)和11月裸地的土壤盐分指数(NDSI、S5、SI-T)均与 $\mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } }$ 达到极显著水平，因此将其作为土壤盐渍化管理分区的辅助变量。

(3）分区后结果表明，各分区结果的变异系数均小于 $1 9 \%$ ，且较整个研究区的变异系数下降约$6 0 \%$ ，说明面向对象多尺度分割算法可有效地划分出均质性区域，从而指导农田的差异化管理，

(4）对比分区结果发现，基于单一数据的管理分区其分区间异质性较低，且部分分区不符合耕作单元，而基于多源数据的管理分区，不仅符合耕作单元，且分区间异质性较单一数据源的管理分区均有所提高。

（5）从农田的耕作角度、分割效果及分区评价原则出发可得，基于 $\mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } }$ 和深层表观电导率的管理分区为最佳，该分区结果既符合当地农田管理又符合机械化作业；而基于 $\mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } }$ 和土壤盐分指数的管理分区次之,效果最差的为仅基于 $\mathrm { E C } _ { \mathrm { h 0 } . 3 7 5 }$ 单一数据源的管理分区。

# 参考文献(References)：

[1] 杨劲松.中国盐渍土研究的发展历程与展望[J].土壤学报, 2008,45(5): 837-845.[Yang Jingsong. Development and prospect of the research on salt-affected soils in China[J].Acta Pedologica Sinica,2008,45(5): 837-845.]   
[2]Maas E V, Hoffman G J. Crop salt tolerance: Evaluation of existing data[C]//Managing Saline Water for Irrigation.Proceedings of the International Salinity Conference,1977.   
[3] Serrano J, Shahidian S,Marques da Silva J,et al.Mapping management zones based on soil apparent electrical conductivity and remote sensing for implementation of variable rate irrigation: Case study of corn under a center pivot[J]. Water,202O,12(12): 3427.   
[4]刘焕军,殷悦,鲍依临,等.黑土区田块尺度精准管理遥感分区 时空格局与成因分析[J].农业工程学报,2021,37(3):147-154. [Liu Huanjun,Yin Yue,Bao Yilin,et al. Spatial-temporal pattern and cause analysis for accurate management of remote sensing zoning at field scale in black soil areas[J]. Transactions of the Chinese Society of Agricultural Engineering,2021,37(3): 147-154.]   
[5] Haghverdi A,Leib BG,Washington-Allen RA,et al.Perspectives on delineating management zones for variable rate irrigation[J]. Computers and Electronics in Agriculture,2015,117: 154-167.   
[6] C6rdoba M, Bruno C,Costa J,et al. Subfield management class delineation using cluster analysis from spatial principal components of soil variables[J]. Computers and Electronics in Agriculture, 2013,97: 6-14.   
[7] 李茂娜,孙宇,严海军,等.基于土壤表观电导率的变量灌溉管 理分区方法[J].农业工程学报,2020,36(22):172-180.[Li Maona, Sun Yu,Yan Haijun,etal.Method for variable rate irrigation management zone delineation based on apparent soil electrical conductivity[J]. Transactions of the Chinese Society of Agricultural Engineering,2020,36(22): 172-180.]   
[8]朱昌达,高明秀,王文倩,等.基于GIS 的滨海盐渍化农田土壤 空间变异及其分区管理[J].生态学报,2020,40(19):6982- 6990.[Zhu Changda, Gao Mingxiu,Wang Wenqian, et al.Spatial variability and zoning management of coastal salinized farmland soil basedon GIS[J]. Acta Ecologica Sinica,2020,40(19): 6982- 6990.]   
[9]Zeraatpisheh M,Bakhshandeh E, Emadi M,et al. Integration of PCA and fuzzy clustering for delineation of soil management zones and cost-effciency analysis in a citrus plantation[J]. Sustainability,2020,12(14): 5809.   
[10]Karydas C, Iatrou M, Iatrou G,et al. Management zone delineation for site-specific fertilization in rice crop using multi-temporal rapidEye imagery[J]. Remote Sensing,2020,12(16): 2604.   
[11]刘焕军,邱政超,孟令华,等.黑土区田块尺度遥感精准管理分 区[J].遥感学报,2017,21(3):470-478.[Liu Huanjun, Qiu Zhengchao, Meng Linghua, et al. Site-specific management zone of field scale based on remote sensing image in a black soil area [J]. National Remote Sensing Bulletin,2017,21(3): 470-478.]   
[12]Damian JM,Pias OHC,Cherubin MR,et al.Applying the NDVI from satellte images in delimiting management zones for annual crops[J].Scientia Agricola,2020,77(1): 0055.doi.org/10.1590/ 1678-992X-2018-0055.   
[13] 刘焕军,鲍依临,徐梦园,等.基于SOM和NDVI的黑土区精准 管理分区对比[J].农业工程学报,2019,35(13):177-183.[Liu Huanjun,Bao Yilin, Xu Mengyuan,et al. Comparison of precision management zoning methods in black soil area based on SOM and NDVI[J]. Transactions of the Chinese Society of Agricultural Engineering,2019,35(13): 177-183.]   
[14] 周林虎,王昊宇,张秉来,等.硫酸盐渍土表观电导率与水分、盐 分及粒径关系研究[J].干旱区研究,2021,38(4):1020-1030. [Zhou Linhu,Wang Haoyu, Zhang Binglai, et al. The relationship between ECa of sulfate saline soil and moisture content, salt content,and particle size[J].Arid Zone Research,2021,38(4):1020- 1030.]   
[15]MoralFJ,Terrón JM, Da Silva JR M.Delineation of management zones using mobile measurements of soil apparent electrical conductivity and multivariate geostatistical techniques[J].Soil and Tillage Research,2010,106(2): 335-343.   
[16]Rhoades JD,van Schilfgaarde J.An electrical conductivity probe fordetermining soil salinity[J]. Soil Science Society of America Journal,1976,40(5): 647-651.   
[17]Rhoades JD,Lesch S M, LeMert R D,et al. Assessing irrigation/ drainage/salinity management using spatially referenced salinity measurements[J].Agricultural Water Management,1997,35(1-2): 147-165.   
[18]Yao R J,Yang JS,Liu G M. Calibration of soil electromagnetic conductivity in inverted salinity profiles with an integration method [J].Pedosphere,2007,17(2): 246-256.   
[19]Teteh G O, Gocht A, Conrad C. Optimal parameters for delineating agricultural parcels from satellite images based on supervised Bayesian optimization[J]. Computers and Electronics in Agriculture,2020,178: 105696.   
[20]Benz U C,Hofmann P,Willhauck G,et al. Multi-resolution,objectoriented fuzzy analysis of remote sensing data for GIS-ready information[J]. ISPRS Journal of Photogrammetryand Remote Sensing 2004,58(3-4): 239-258.   
[21] Chang D, Zhang J, Zhu L,et al. Delineation of management zones using an active canopy sensor for a tobacco field[J].Computers and Electronics in Agriculture,2014,109: 172-178.   
[22] 陈春雷,武刚.面向对象的遥感影像最优分割尺度评价[J].遥感 技术与应用,2011,26(1):96-102.[Chen Cunlei,Wu Gang.Evaluation of optimal segmentation scale with object-oriented method in remote sensing[J].Remote Sensing Technology and Application,2011,26(1): 96-102.]   
[23] 彭杰.荒漠土壤盐渍化遥感监测与开垦方案分析——以空台里 克冲积扇为例[D].杭州:浙江大学,2019.[Peng Jie.Salinzation Monitoring and Reclamation Strategy Analysis inof Desert Soil Using Remote Sensing: A Case Study in the Kongtailike Alluvial Fan [D]. Hangzhou: Zhejiang University, 2019.]   
[24] 刘宁.不同土地利用方式下黄河三角洲土壤特性空间变异研究 [D].泰安:山东农业大学,2007.[Liu Ning.Spatial Variability of Soil Characteristics on Different Land Use Types in the Yellow River Delta[D].Tai'an: Shandong Agricultural University,2007.]   
[25] 白建铎,彭杰,白子金,等.干旱区棉田表层土壤盐渍化时空变 异研究[J].土壤通报,2021,52(3): 527-534.[Bai Jianduo,Peng Jie,Bai Zijin,et al. Clarifying spatial-temporal variability of surface soil salinization in arid cotton fields[J]. Chinese Journal of Soil Science,2021,52(3): 527-534.]   
[26]许盼盼.基于高时空分辨率数据的湿地精细分类研究[D].北 京：中国科学院大学,2018.Xu Panpan.Study on Finer Mapping of Wetlands Basedon High Temporal and High Spatial Resolution Date[D]. Beijing: University of Chinese Academy of Sciences,2018.]   
[27] 黄万里.基于高分卫星数据多尺度图像分割方法的天山森林小 班边界提取研究[D].福州:福建师范大学,2015.[Huang Wanli. Study on Sub-compartment Division of Tiansan Forest Based on High Spatial Resolution Satelite Imagesand Multi-Scale Image Segmentation Methods[D].Fuzhou:Fujian Normal University, 2015.]

# Precise management zoning in arid soil croplands based on multi-source data

BAI Jianduo'，PENG Jie'， SHI Zhou²，WANG Yuzhen'，LIU Weiyang'，LI Hongyi   
(1.Collge of Agriculture,Tarim University,Alar8433Oo,Xinjiang,China;2.Instituteof Agricultural Remote   
Sensing and Information Technology Application, Zhejiang University,Hangzhou 31Oo58,Zhejiang, China; 3. College of Tourism and Urban Management, Jiangxi University of Finance and Economics, Nanchang 330000, Jiangxi, China)

Abstract: According to the spatial heterogeneity of soil salinization,the precise management precise Zoning of oasis farmland in the arid area of Southern Xinjiang is of great significance for the adjustment ofareas,based on spatial heterogeneity in soil salinization,is important for determining agricultural planting structure structures and fine-scale management.This study selected the topical oasis farmland in arid zone as the study object and used electromagnetic induction data,topographic date,and satelite remote sensing data as for oasis farmland in the data sources.We analyzed arid zone of Southern Xinjiang to analyze the spatial heterogeneity of soil salinization by geostatistical. Geostatistical methods and screened the were used to evaluate vegetation index and salt index in indices for diferent periods with correlation analysis.The surface apparent electrical conductivity （20 $\left( \mathrm { E C } _ { \mathrm { h 0 . 3 7 5 } } \right)$ of the farmland was used as the main variable,and the deep apparent electrical conductivity $\mathrm { ( E C _ { h 0 . 7 5 } , }$ （20 $\mathrm { E C } _ { \mathrm { V 0 . 7 5 } }$ ， $\mathrm { E C } _ { \mathrm { V } 1 . 5 }$ ), vegetation index (RVI, GRVI, EVI),and soil salinity index (NDSI, S5,SI-T) were used as the auxiliary variables. The study area was partitioned by using an object- oriented multi-scale segmentation algorithm,and the zoning results were evaluated by the mean Coefficient of variation $( C _ { \mathrm { v } } )$ and Moran's I. The results showed that there was obvious spatial heterogeneity in the apparent electrical conductivity of ach soil layers in the study area,and the auxiliary variables were significantly correlated with the main variable.The average coefficient of variation of each partition was reduced by $60 \%$ compared with that of the whole study area,and the.The interval heterogeneitybased on multi-source data zoning was higher than thatbasedon singlesource data zoning.From the perspective of farmland cultivation,segmentation effects,and zoning evaluation principles,the, management zoning effect that integrated the information of surface and deep soil salinization was the best.And the zoning results were not only consistent with both local farmland management but also met the mechanized operation requirements.The findings can provide certain a technical and methodological reference for precise management zoning of oasis farmland in arid areas of Southern Xinjiang.

Keywords: soil salinization;multi-source data；apparent electrical conductivity； object-oriented segmentation; precise management zoning; arid area