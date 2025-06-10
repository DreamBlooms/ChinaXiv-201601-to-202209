# 高原复杂地理参数对雷电活动的影响分析

胡亚男}，陶世银}，龚梅竹²，马海玲}(1.青海省气候中心，青海 西宁810000；2.青海省气象服务中心，青海 西宁 810000)

摘要：雷电活动参数作为反映区域雷电活动特征的重要指标，地形对其影响不容忽视。利用2014—2018年青海省地闪数据、数字地形高程数据以及HWSD土壤数据集，定量分析海拔、坡度、坡向以及土壤电阻率对青海省地闪分布特征的影响。结果表明：(1)青海省地闪主要集中在海拔$3 1 5 0 { \sim } 4 8 5 0 \mathrm { m }$ 坡度 $0 { \sim } 3 5 ^ { \circ }$ 的地区，其中东北坡向地闪次数最多，东南坡向地闪次数最少，地闪对应的土壤电阻率主要集中于 $1 0 0 \Omega \cdot \mathrm { m } _ { \mathrm { o } } ( 2 )$ 地闪密度随海拔的升高先增大后减小，随坡度的增大而减小;地闪平均强度随海拔的升高先减小后增大，随坡度的增大而增大。(3)选取 $9 2 ^ { \circ } 2 7 ^ { \prime } 0 0 ^ { \prime \prime } { \sim } 9 7 ^ { \circ } 4 4 ^ { \prime } 2 4 ^ { \prime \prime } \mathrm { E } .$ $3 1 ^ { \circ } 4 0 ^ { \prime } 4 8 ^ { \prime \prime } { \sim } 3 4 ^ { \circ } 1 6 ^ { \prime } 4 8 ^ { \prime \prime } \mathrm { N }$ 地闪活跃区域，对其 $1 \ \mathrm { k m } { \times } 1 \ \mathrm { k m }$ 网格内地闪数据与地理参量平均值进行相关性分析，所选区域内地闪密度与平均海拔呈正相关关系，与平均坡度呈负相关关系;而地闪强度与平均海拔呈负相关关系，与平均坡度呈正相关关系。

关键词：雷电活动；海拔；坡度；坡向；土壤电阻率；青海高原

# 文章编号：

地闪强度、地闪密度等雷电活动参数是反映区域雷电活动规律的重要指标，其分布特征不仅与气候背景、天气条件有关，同时还与地域地形密切相关[1-3]。地形能直接或间接影响盛行风向,致使锋面抬升，直接对上升气流造成影响，导致局部不稳定性的增强，从而影响雷暴强度[4]。因此，开展区域雷电活动参数随地理参数的变化规律，是雷电科学研究的重要内容之一。

近年来，闪电定位系统已广泛运用于雷电活动监测中，利用闪电定位仪可以快速精确的获取研究区地闪数据，已成为雷电科学研究的主要数据来源。此外，随着遥感技术的发展，得到的陆地遥感数据空间分辨率极高，为雷电活动与地形相关性的定量分析提供了基础。申元等[5]、李家启[、范仲之等[7对雷电参数随海拔的变化情况进行了分析，得出了雷电参数随海拔变化的规律。而Bourscheidt等[8]、Wagner等[9]分别分析了巴西、美国等国家地形对闪电活动规律的影响，发现当地地形坡度与闪电活动分布特征的相关性较高。以上研究虽涉及了地形因素对雷电活动影响的定量化分析，但仅限于海拔、坡度等个别地理参数的研究，没有对多个地理参数对雷电活动特征的影响进行综合、深入研究。青海省位于青藏高原东部，境内地貌以山地为主，地势整体自西北、东南两侧分别向中部逐渐递减，海拔差异悬殊，相对高差可达 $5 2 1 0 \mathrm { ~ m ~ }$ 。省内对流天气空间分布不均，雷电活动环境参量复杂多样,是我国对流最为旺盛的地区之一[10-13]。因此,本文分析青海省海拔、坡度、坡向以及土壤电阻率等地理参数对雷电活动规律的影响，为该地区开展防雷减灾工作提供一定的基础支撑。

# 1资料与方法

# 1.1资料来源

1.1.1闪电定位资料本文采用2014—2018年青海省ADTD闪电监测网所取得的地闪数据。考虑到在云闪干扰下，ADTD闪电定位仪对 $1 0 \mathrm { k A }$ 以下的回击探测能力较差[14-15],故剔除资料中强度小于 $1 0 \mathrm { k A }$

的正地闪个例。

1.1.2地理高程数据本文采用的地理高程数据为SRTM数字高程产品，此数据产品2003年开始公开发布，经历多次修订，目前的数据修订版本为V4.1,分辨率为 $3 0 \mathrm { ~ m ~ }$ ，数据来源于美国国家航空航天局(https://www.nasa.gov/)。根据青海省矢量界限对其进行裁剪，得到青海省高程地图，再利用GIS软件进行数据处理、加工及提取，分别获得青海省海拔、坡度、坡向等地形参量数据。

1.1.3土壤电导率数据土壤电导率数据来自v1.1版本的世界土壤数据库(HWSD)，来源于国家青藏高原科学数据中心（https://data.tpdc.ac.cn/）。通过python软件编程建立青海省地图栅格像元值与土壤数据库制图单元的链接，实现对土壤电导率数据的提取。

# 1.2 研究方法

1.2.1 数据提取根据2014—2018年青海省地闪数据，利用GIS软件中的提取工具，根据地闪出现的地理位置，将海拔、坡度、坡向以及土壤电导率等地理参数值提取至每条地闪数据，并对青海省地闪次数、地闪密度以及地闪强度随不同地理参数的变化特征进行统计与分析。

1.2.2Spearman秩相关系数法本文基于不同坡度所提取的地闪数据并非等距连续，且类型和相关形式未知，而Spearman秩相关作为非参数统计，具有对异常值敏感度低、数据不须满足正态性假设等优点[16]。因此,采用 Spearman秩相关进行坡度与地闪密度间的相关性分析，其计算公式为：

$$
r _ { \mathrm { s } } = 1 - { \frac { 6 { \sum } d _ { i } ^ { 2 } } { n ( n ^ { 2 } - 1 ) } }
$$

式中： $r _ { \mathrm { s } }$ 为秩相关系数； $d _ { i }$ 为两变量每一对样本的等级差； $n$ 为样本容量。

1.2.3Pearson相关分析根据青海省地闪分布特征，选取地闪密集区，以 $1 \ \mathrm { k m } { \times } 1 \ \mathrm { k m }$ 网格为基础对该区域内的地闪密度与地闪强度进行格点统计，并在相同格点内分别对海拔与坡度进行均值计算。之后采用Pearson相关分析法分别对地闪密度、地闪强度与海拔、坡度平均值间的关系进行相关性分析，得到地闪活跃区域内雷电活动与地理参数间的相关关系。

# 2结果与分析

# 2.1青海省雷电活动空间分布

2014—2018年青海省共发生地闪 $4 0 . 0 2 \times 1 0 ^ { 4 }$ 次；其中负地闪次数为 $3 5 . 0 3 \times 1 0 ^ { 4 }$ 次，正地闪次数为$4 . 9 9 \times 1 0 ^ { 4 }$ 次。受地形分布的影响(图1a)，青海省地闪密度分布特征如图1b所示，地闪密度最高值主要出现在平均海拔 $4 5 0 0 \mathrm { ~ m ~ }$ 以上的青南牧区，其原因可能是由于青南牧区地面强热源以及复杂地形造成的非均匀性下垫面热力分布，导致该区域两侧边界低层干冷平流相互影响显著，形成低层强烈不稳定状态,更易发生强对流天气[17]。地闪密度次高值主要出现在平均海拔 $4 0 0 0 \mathrm { m }$ 以上的环青海湖区，影响该区域对流发展的天气系统以蒙古冷槽型为主，蒙古冷槽型以高空冷槽与低空湿舌的相互作用引发强对流天气，持续输出冷空气，干冷空气源源不断流向环青海湖区域，致使水汽含量较高的环青海湖区上干下湿，形成对流性不稳定层结，有利于强对流天气的形成[18-19]

图1青海省海拔与年平均地闪密度的空间分布  
![](images/f87afb0329591d4882c6637bf60ed21d25a07c7e516b9baa94d335881173d323.jpg)  
注：该图基于青海省自然资源厅标准地图服务网站下载的审图号为青S(2018)003号的标准地图制作，底图边界无修改。下同。

Fig.1Spatial distributions of altitude and annual mean cloud-to-ground lightning density in Qinghai Province

# 干吴区地理

# 2.2海拔对雷电活动空间分布特征的影响

由于海拔 $5 4 5 0 \mathrm { m }$ 以上无地闪活动发生，因此仅分析海拔 $1 6 5 0 { \sim } 5 4 5 0 \mathrm { ~ m }$ 范围内地闪活动随海拔的分布特征。根据逐条地闪提取的海拔数据，以 $1 0 0 \mathrm { m }$ 为海拔递增单位，对青海省2014—2018年地闪次数进行统计，并分析青海省海拔及不同海拔所对应的面积对地闪次数分布特征的影响。青海省地闪主要集中分布于海拔 $3 1 5 0 { \sim } 4 8 5 0 \mathrm { m }$ ，该区间地闪次数约占总次数的 $8 2 . 1 1 \%$ （图 $2 \mathrm { a }$ )。随海拔的升高，地闪次数的变化趋势为先增加后减少，呈现“四峰三谷”的波状分布，四峰分别出现在海拔 $2 4 5 0 { \sim } 2 5 5 0 \ \mathrm { m }$ 、$3 0 5 0 { \sim } 3 1 5 0 \ \mathrm { m } , 3 5 5 0 { \sim } 3 6 5 0 \ \mathrm { m }$ 以及 $4 3 5 0 { \sim } 4 4 5 0 \ \mathrm { m }$ 区间内，其中最高峰位于海拔 $3 5 5 0 { \sim } 3 6 5 0 \mathrm { m }$ 。此外，不同海拔区间面积的变化趋势与地闪次数大体一致，但两者的极高值与次高值异步，海拔 $4 4 0 0 \mathrm { ~ m ~ }$ 左右(地闪次高值点)为区间面积的极高值(图 $2 \mathrm { a }$ ）。

从不同海拔区间的地闪密度(图2b)可以看出，总地闪密度与负地闪密度随海拔的变化趋势一致，随海拔的升高均呈现先增大后减小的趋势，在海拔$3 5 5 0 { \sim } 3 6 5 0 \mathrm { ~ m }$ 达到峰值，其中总地闪密度为4.74次·$\mathrm { k m } ^ { - 2 } { \cdot } \mathrm { a } ^ { - 1 }$ ，负地闪密度为4.25次 $\cdot \mathrm { k m } ^ { - 2 } \cdot \mathrm { a } ^ { - 1 }$ ;而正地闪密度在海拔 $2 1 5 0 { \sim } 4 0 5 0 \ \mathrm { m }$ 区间维持在0.06次· $\mathrm { k m } ^ { - 2 } \cdot \mathrm { a } ^ { - 1 }$ 的平稳特征，在海拔 $4 2 5 0 \mathrm { m }$ 以上呈下降趋势。

地闪强度反映了研究区域雷电流幅值的大小，是衡量闪电破坏力的重要因素之一[20]。由于青海省地闪活动主要出现在海拔 $3 1 5 0 { \sim } 4 8 5 0 \ \mathrm { m }$ ，仅统计该海拔区间内总地闪及正、负地闪平均强度，分析其随海拔的变化特征。各海拔区间内的正地闪平均强度明显大于负地闪平均强度(图2c)，这可能与正电荷在雷暴云中的位置有关，一般雷暴云电荷呈现上正下负的分布结构，云层低部的负电荷距离地面较近，闪电通道更易快速形成，在强度偏弱的情况下就能产生放电过程[2I],为保持雷暴云中电荷平衡，云层上部只能输送更多的正电荷来达到平衡，因此正闪强度一般较负闪要大的多。此外，总地闪与负地闪平均强度随海拔的升高均呈现先递减再递增的变化趋势，且在 $3 0 \mathrm { k A }$ 附近趋于平稳(图2c），这与李政2对重庆地闪强度随海拔变化的研究结果基本一致。负地闪平均强度在海拔 ${ > } 3 6 5 0 \mathrm { ~ m ~ }$ 以上逐渐缓增的原因可能是高海拔地区地闪活动主要为辐射造成的局地强对流活动[23，随海拔的升高，水汽含量不断减少，雷暴云中的电荷累积至闪电通道形成所需的能量明显高于低海拔地区，且高海拔地区云底高偏低，更有利于云地放电，从而造成高海拔地区负地闪强度线性增强。

# 2.3坡度对雷电活动空间分布特征的影响

坡度是描述地表倾斜程度的地形因子之一，其对气流抬升和对流形成具有促进作用[24]。本文以$5 ^ { \circ }$ 为间隔，对不同坡度区间的面积以及地闪次数进行了统计(图3a)。2014—2018年青海省地闪活动主要集中在 $0 { \sim } 3 5 ^ { \circ }$ 坡度区间内，该区间地闪次数占总次数的 $9 6 . 9 1 \%$ ，且区间面积占全省面积的$9 7 . 4 7 \%$ 。其中， $0 { \sim } 1 0 ^ { \circ }$ 坡度区间内的地闪活动最为活跃，地闪次数高达 $1 9 . 1 2 \times 1 0 ^ { 4 }$ 次，占总地闪次数的$4 7 . 3 4 \%$ ，区间面积则占全省面积的 $5 9 . 2 6 \%$ 。 $3 0 ^ { \circ } \sim$ $6 0 ^ { \circ }$ 坡度区间内的地闪次数极少，仅为总次数的$3 . 1 1 \%$ ，因此在后续分析中对该区间的地闪次数不作考虑。

从 $0 { \sim } 3 5 ^ { \circ }$ 坡度区间内地闪密度的分布特征(3b）可以看出，正地闪密度在 $0 { \sim } 3 5 ^ { \circ }$ 坡度区间内呈阶梯状减小;而总地闪密度与负地闪密度在坡度 $0 { \sim } 5 ^ { \circ }$ 区间内达到最大，分别为5.32次· $\mathrm { k m } ^ { - 2 } \cdot \mathrm { a } ^ { - 1 }$ 与5.08次·

8 1 (a)地闪次数 7 e2 654 1 (b)地闪密度 + 总地闪 0.8 2 (c)地闪强度→总地闪   
76543210 区间面积占比 654 %/ 正地闪 + 正地闪   
地闪次数 / 负地闪 0.6 一负地闪 32 321 X 0402 W 1 上 0 0 A 0.0   
OSLI\~ 0517 \~3250 515 25 2554 OSzC 250 022 O55 0555 ost 214 52555 \~3250 05040 2040 \~4850   
\~0591 2150\~2250 22555 33530 £\~0co 12115 -0590 \~2511 10591 12215 \~Oso7 35530 33550 t\~Osu -4594 \~O555 3550\~ 10200 254 海拔/m 海拔/m 海拔/m   
12 − (a)地闪次数 40 e 6 (b)地闪密度 一总地闪 -0.15 2 6050 (c)地闪强度 地闪   
086 二面积占比 5 地 一负地闪 0.10 20 4 15 0.05 10 3 5   
0 0 2 0.00 -25   
T 2 0 C 330 3 8 如 s 0 Q 5 久 小 S 2公 双 3 ” 0\~5 01\~s 久 公 s D 2 3 3 3 坡度/() 坡度/() 坡度/()

$\mathrm { k m } ^ { - 2 } \cdot \mathrm { a } ^ { - 1 }$ ,之后随坡度增加呈减小特征。利用 Spear-man秩相关系数法计算坡度与坡度区间内地闪密度的相关系数，发现坡度与总地闪密度和负地闪密度均呈负相关关系( $r _ { \rho _ { \perp , \mathrm { f f } \mid \{ \} , \vert \mathcal { A } \vert } } = - 0 . 7 8$ ; $r _ { \wp , \hbar \hbar \hbar } = - 0 . 5 7$ ）

从 $0 { \sim } 3 5 ^ { \circ }$ 坡度区间内地闪平均强度的变化特征(3c)可以看出，负地闪平均强度随坡度呈线性增强变化，但其强度总体比正平均地闪强度偏小 $2 0 \mathrm { k A }$ 左右，原因可能是内陆高原雷暴云底部正电荷区与主负电荷区十分接近，促使两者之间形成了较大的场强，放电过程主要集中发生于它们之间，难以产生正地闪，从而导致正地闪回击次数明显少于负地闪回击次数，而多次地闪回击过程将造成电流强度在多次放电过程中迅速减小[25]。随着坡度的增加,正地闪平均强度呈缓慢增加趋势，但其变化斜率小于负地闪(图3c)，这可能与负地闪中心位于雷暴云底部有关，位于云层底部的负地闪受地形影响的变化程度较正地闪更大，因此其变率远大于正地闪。

# 2.4坡向对雷电活动空间分布特征的影响

根据中等尺度上常用的坡向分类方法[26]，以$4 5 ^ { \circ }$ 为间隔将坡向划分为8种，各坡向区间范围以及区间面积占比如表1所示，从表中可以看出不同坡向区间面积占比差异不大。统计各坡向区间的地闪次数(图4a)可以看出，青海省东北坡向上的地闪次数最多，东南坡向的地闪次数最小，这可能是由于青藏高原的雷电活动主要集中于夏季，而青藏高原夏季的主导风向为西南风[27],相对于东南坡向，东北方向的坡面为迎风坡，气流在迎风坡更易抬升，导致强对流天气产生，这同时也表明了风场辐合场对雷电活动也有着重要的影响。

从不同坡向分类区域内地闪平均强度与标准差(表2)可以看出，不同坡向上的地闪平均强度标

# 表1各坡向分类标准及面积占比

Tab.1 Classification standard and area ratio in each slope direction   

<html><body><table><tr><td>坡向分类</td><td>坡向区间/()</td><td>面积占比/%</td></tr><tr><td>北</td><td>337.5~22.5</td><td>12.93</td></tr><tr><td>东北</td><td>22.5~67.5</td><td>13.82</td></tr><tr><td>东</td><td>67.5~112.5</td><td>12.54</td></tr><tr><td>东南</td><td>112.5~157.5</td><td>11.70</td></tr><tr><td>南</td><td>157.5~202.5</td><td>11.96</td></tr><tr><td>西南</td><td>202.5~247.5</td><td>13.16</td></tr><tr><td>西</td><td>247.5~292.5</td><td>12.18</td></tr><tr><td>西北</td><td>292.5~337.5</td><td>11.72</td></tr><tr><td>合计</td><td></td><td>100.00</td></tr></table></body></html>

准差均较大，说明不同坡向分类上的地闪平均强度存在显著差异。由于电流幅值较大的地闪更易导致雷灾[28]，为研究强地闪的分布特征，本文根据青海省地方标准《气象灾害分级指标》，对青海省地闪强度 ${ > } 4 0 \mathrm { k A }$ 的地闪分布特征进行了进一步分析(图4b)可以看出，所有坡向上的强地闪占比差异不大，其中坡向分类为北的区域强闪电占比略高，为$2 1 . 1 8 \%$ ，与表2中地闪平均强度分布特征一致，说明强地闪占比越大的区域遭受雷电的威胁就越大。

# 2.5土壤电阻率对雷电活动空间分布特征的影响

雷电活动参数的分布特征不仅与地形有关，还与土壤电阻率密切相关，而土壤电阻率对雷电辐射场的影响程度主要取决于上层土壤[29]。因此,本文根据逐条地闪资料，以 $0 . 1 \mathrm { S } \cdot \mathrm { m } ^ { - 1 }$ 为间隔提取上层（ $0 { \sim } 3 0 ~ \mathrm { c m }$ 深度)土壤的电导率数据，再利用土攘电导率与电阻率互为倒数的关系[30，将土壤电导率换算为土壤电阻率，然后统计不同土壤电阻率对应的地闪次数、单位面积地闪次数以及地闪平均强度。考虑到 $1 \Omega \cdot \mathrm { m }$ 以下土壤电阻率对应的地闪次数极

![](images/efd530713c3681f6a94f55a305db1f13b880e199db868dee3ddfc139d41675ee.jpg)  
图4不同坡向区间内地闪活动的分布特征  
图5青海省地闪活动的电阻率分布特征

Fig.4Distribution characteristics of cloud-to-ground lightning activity in different slope direction intervals

# 表2各坡向地闪平均强度

Tab.2 Average cloud-to-ground lightning intensity in each slope direction   

<html><body><table><tr><td>坡向分类</td><td>地闪平均强度/kA</td><td>标准差</td></tr><tr><td>北</td><td>31.54</td><td>25.82</td></tr><tr><td>东北</td><td>30.74</td><td>24.19</td></tr><tr><td>东</td><td>30.64</td><td>24.25</td></tr><tr><td>东南</td><td>30.32</td><td>23.48</td></tr><tr><td>南</td><td>30.25</td><td>23.42</td></tr><tr><td>西南</td><td>30.38</td><td>24.53</td></tr><tr><td>西</td><td>30.46</td><td>23.66</td></tr><tr><td>西北</td><td>30.81</td><td>24.62</td></tr></table></body></html>

少，将电阻率数据分为100、50、33、25、20、1.7进行统计，结果如图5所示。

根据徐霞等[31]绘制的典型地区土壤电阻率空间分布可知青海省大部分地区土壤电阻率在 $1 0 0 \sim$ $2 0 0 \Omega \cdot \mathrm { m }$ 。因此，受面积的影响，青海省地闪对应的电阻率主要集中于 $1 0 0 \Omega \cdot \mathrm { m }$ ，其地闪次数约占总次数的 $8 8 . 0 6 \%$ 。为消除面积的影响，计算单位面积地闪次数对应的土壤电阻率，从图5b可以看出土壤电阻率小的区域对应的单位面积地闪次数总体上呈现偏多现象，说明电阻率低的土壤，更易遭受雷击。其原因可能是当雷电先导阶段，土壤电阻率低的区域更易聚集感应电荷，导致该区域电场强度增强，为雷电先导提供了良好的电场条件，促使雷电下行先导更易向该区域发展，发生雷击的概率更高[32]。此外，图5c所示地闪平均强度总体上随着电阻率的增大逐渐减小，其原因可能是土壤电阻率较大地区,发生较大雷电流幅值的概率较小[33]。此外，负地闪平均强度随土壤电阻率减小的增加趋势较正地闪更加明显，说明较小的土壤电阻率对负地闪强度的增强作用明显大于正地闪，这与王学良等[34]的研究结论基本一致。

# 2.6地闪活动频繁区域地闪活动与地形的关系

从上文分析可知，青海省地闪密集区主要出现在海拔 $3 1 5 0 { \sim } 4 8 5 0 \mathrm { m }$ 坡度 ${ < } 3 0 ^ { \circ }$ 的区域，其中青南牧区为地闪活动最活跃区域。因此，本文选取青南牧区 $9 2 ^ { \circ } 2 7 ^ { \prime } 0 0 ^ { \prime \prime } { \sim } 9 7 ^ { \circ } 4 4 ^ { \prime } 2 4 ^ { \prime \prime } \mathrm { E } \mathrm { ~ } . 3 1 ^ { \circ } 4 0 ^ { \prime } 4 8 ^ { \prime \prime } { \sim } 3 4 ^ { \circ } 1 6 ^ { \prime } 4 8 ^ { \prime \prime } \mathrm { N }$ 范围内 $1 ~ \mathrm { k m } { \times } 1 ~ \mathrm { k m }$ 网格为单位，对 $1 4 \times 1 0 ^ { 4 }$ 个格点内的

28292 (a)地闪次数 100807605040302010 (b)单位面积地闪次数 050540 (c)地闪强度 地 5 0.0 1 1.720253350 100 1.7 20253350 100 1.7 202533 50 100 土壤电阻率 $/ \Omega \cdot \mathbf { m }$ （20 土壤电阻率 $/ \Omega \cdot \mathrm { m }$ 土壤电阻率/Ω·m

Fig.5Distribution characteristics of cloud-to-ground lightning under diferent soil resistivity in Qinghai Province 地闪密度与地闪强度进行分析，探讨地闪活动与地 形特征间的相关性，结果如表3所示

# 表3研究区域内地闪活动与海拔、坡度的相关性

Tab.3 Correlation between cloud-to-ground lightning activity and altitude and slope in the study area   

<html><body><table><tr><td rowspan="3"></td><td colspan="2">相关系数(r)</td></tr><tr><td>平均海拔</td><td>平均坡度</td></tr><tr><td>地闪密度</td><td>0.54</td><td>-0.23</td></tr><tr><td>地闪强度</td><td>-0.35</td><td>0.44</td></tr></table></body></html>

所选区域内地闪密度与平均海拔呈正相关关系 $\scriptstyle ( - 0 . 5 4 )$ ，其原因可能是海拔高的地区山体较高、范围较大，为对流云团提供抬升动力更明显。此外，随海拔的升高，地表上的等位势面提升，加大云地电场强度,有利于地闪的触发[35]。因此,闪电活动与海拔的相关性实质上可能是海拔梯度对雷暴发展提供抬升动力的体现。区域内地闪密度与平均坡度的相关系数较小，呈弱的负相关关系( $\scriptstyle \left. r = \frac { } { } \right.$ $- 0 . 2 3 )$ ,与Bourscheidt等[8]的研究结果较为一致,其对地闪密度与坡度相关性的研究中发现，在局部山体区域地闪密度与坡度呈现相关关系。而地闪强度与平均海拔呈负相关( $\scriptstyle ( r = - 0 . 3 5 )$ ,与平均坡度呈正相关关系（ $_ { ( r = 0 . 4 4 ) }$ 。地闪强度与海拔呈现负相关，其原因是在雷暴云云底在高海拔地区的离地高度较低海拔地区偏小，雷暴云中的电荷与地面间的电场强度因距离的缩小更易达到临界击穿场强，而在达到临界击穿场强时雷暴云中大量电荷并未形成，因此随海拔的升高地闪强度反之下降[36]

# 3结论

本文利用ADTD闪电定位数据、数字地形数据以及HWSD土壤数据集，对青海省海拔、坡度、坡向以及土壤电阻率对地闪分布特征的影响进行了分析。主要结论如下：

（1）青海省地闪次数主要集中分布于海拔$3 1 5 0 { \sim } 4 8 5 0 \ \mathrm { m }$ 之间，随海拔的升高，地闪次数、地闪密度的变化趋势均为先增加后减少；总地闪、正地闪以及负地闪强度随海拔的升高均呈现先递减再递增的变化趋势。

(2）青海省地闪活动主要集中在 $0 { \sim } 3 5 ^ { \circ }$ 坡度区间内，不同坡度区间内的地闪次数与地闪密度随坡度增加呈减小特征；总地闪、正地闪以及负地闪强度随坡度增加呈增强趋势。

(3）青海省东北坡向上的地闪次数最多，东南坡向的地闪次数最少，其中坡向分类为北区域的强闪电占比最高。（4）青海省地闪对应的电阻率主要集中于100$\Omega \cdot \mathrm { m }$ ,地闪强度总体上均随着电阻率的增加呈现逐渐减小趋势。(5）青南牧区 $9 2 ^ { \circ } 2 7 ^ { \prime } 0 0 ^ { \prime \prime } { \sim } 9 7 ^ { \circ } 4 4 ^ { \prime } 2 4 ^ { \prime \prime } \mathrm { E } . 3 1 ^ { \circ } 4 0 ^ { \prime } 4 8 ^ { \prime \prime } { \sim }$ $3 4 ^ { \circ } 1 6 ^ { \prime } 4 8 ^ { \prime \prime } \mathrm { N }$ 范围内地闪密度与海拔呈正相关关系，与坡度呈负相关关系；而地闪强度与海波呈负相关，与坡度呈正相关关系。

# 参考文献(References)

[1]郄秀书,周筠珺,袁铁.卫星观测到的全球闪电活动及其地域差 异[J].地球物理学报,2003,46(3):743-750.[Qie Xiushu, Zhou Yunjun,Yuan Tie.Global lighting activities and their regional differences observed from the satellite[J]. Chinese Journal of Geophysics,2003,46(3): 743-750.]   
[2]刘兆旭,刘晶,范子昂.2005—2020年新疆雷电灾害特征分析 [J/OL].干旱区地理.[2021-06-22]. https://kns.cnki.net/kcms/detail/65.1103.X.20220124.2009.007.html.[Liu Zhaoxu,Liu Jing, Fan Zi'ang. Characteristics of lightning disaster in Xinjiang from 2005 to 2020[J/OL]. Arid Land Geography.[2021-06-22]. https:// kns.cnki.net/kcms/detail/65.1103.X.20220124.2009.007.html.]   
[3]William E R.Lightning and climate: A review[J]. Atmospheric Research,2005,76(1-4): 272-287.   
[4] Smith R B.The influence of mountains on the atmosphere[C]/ Saltzman B.Advances in Geophysics.New York: Academic Press Inc.,1970: 87-230.   
[5]申元,王磊,马御棠,等.海拔高度对云南某地雷电参数的影响 [J].电力建设,2012,33(4):35-37.[Shen Yuan,Wang Lei,Ma Yutang,et al.Effect of elevation on lighting parameters in Yunan Province[J]. Electric Power Construction,2012,33(4): 35-37.]   
[6]李家启.基于LLS的重庆地区雷电活动规律及其风险评估研究 [D].南京:南京信息工程大学,2012.[Li Jiaqi.Study on lighting activity regularity and risk assessment based on LLS in Chongqing [D].Nanjing: Nanjing University of Information Science and Technology, 2012.]   
[7]范仲之,付雅婷.山西省闪电活动时空特征及其与地形的相关 性分析[J].广东气象,2017,39(4): 69-72.[Fan Zhongzhi,Fu Yating. Temporal and spatial characteristics of lightning activity and its relation to topography in Shanxi Province correlation analysis [JJ. Guangdong Meteorology,2017,39(4): 69-72.]   
[8]Bourscheidt V,Pinto Junior O,Naccarato KP,et al.The influence of topography on the cloud-to-ground lightning density in south Brazil[J]. Atmospheric Research,2009, 91(2): 508-513.   
[9]Wagner G,Fuelberg HE,Kann D,et al.A GIS-based approach to

# 干吴区地理

lightning studies for West Texas and New Mexico[EB/OL].[2007- 9-26].htp://ibrary.cma.gov.cn:8080/ams_data/AMS2006_/103103. pdf.]   
[10] 黄鑫,刘建红,申克建,等.基于MODIS 的青海草地产草量变化 遥感分析[J].干旱区地理,2020,43(3):715-725.[Huang Xin, Liu Jianhong, Shen Kejian, et al. Grassand yield change in Qinghai ProvincebasedonMODIS data[J].Arid LandGeography, 2020,43(3): 715-725.]   
[11]胡玲,郭卫东,王振宇,等.青海高原雷暴气候特征及其变化分 析[J].气象,2009,35(11): 64-70.[HuLing,Guo Weidong, Wang Zhenyu,et al.Climate characteristics of thunderstorm and its change in Qinghai Plateau[J].Meteorological Monthly,2009,35 (11): 64-70.]   
[12] 朱平,俞小鼎,王振会,等.青海高原致灾性对流天气时空分布 特征[J].干旱气象,2019,37(3):377-383.[Zhu Ping,Yu Xiaoding,Wang Zhenhui,et al. Temporal and spatial distribution characteristics of disastrous convective weather over the Qinghai Plateau[J]. Journal of Arid Meteorology,2019,37(3): 377-383.]   
[13] 刘晓燕,王玉娟,王军,等.青海东部雷电活动环境特征及其预 报[J].干旱气象,2018,36(4):676-683.[Liu Xiaoyan,Wang Yujuan,Wang Jun,et al.Environment characteristics of lightning activity and its forecast in the eastern Qinghai[J]. Journal of Arid Meteorology,2018,36(4): 676-683.]   
[14]Carey L D,Rutledge S A,Petersen WA. The relationship between severe storm reports and cloud-to-ground lightning polarity in the contiguous United States from 1989 to 1998[J]. Monthly Weather Review,2003,131(7): 1211-1228.   
[15]王志超,庞文静,梁丽,等.ADTD闪电定位网在北京地区定位 效率的自评估[J]．气象科技,2018,46(4):638-643.[Wang Zhichao,Pang Wenjing,Liang Li,et al. Self-evaluation on detectionefciencyof ADTDlighting locationnetwork in Beijing[J]. Meteorological SienceandTechnolog,2018,46(4):638-643.]   
[16] Li W S, Xu S H, Zheng JM,et al. Target curvature driven fairing algorithm for planner cubic B-spline curves[J]. Computer Aided Geometric Design,2004,21(5): 499-513.   
[17] 徐祥德,卞林根,张光智,等.青藏高原地-气过程动力、热力结 构综合物理图像[J].中国科学:地球科学,2001(5):428-440. [Xu Xiangde, Bian Lingen, Zhang Guangzhi, etal. Integrated physical images of the dynamic and thermal structures of the earth-atmosphere processes in the Tibetan Plateau[J]. Scientia Sinica (Terrae),2001(5): 428-440.]   
[18] 潘多,侯正俊,靳世强,等.青藏高原东北部强冰雹天气特征分 析[J].西藏科技,2016(12): 67-70.[Pan Duo,Hou Zhengjun, Jin Shiqiang,et al.Analysis of weather characteristics of severe hail in northeastern Tibetan Plateau[J]. Xizang Science and Technology, 2016(12): 67-70.]   
[19] 苏永玲,马秀梅,马元仓,等.高空冷涡和副高背景下青海冰雹 特征对比分析[J].沙漠与绿洲气象,2018,12(4):22-29.[Su Yongling,Ma Xiumei, Ma Yuancang,et al. Comparative analysis on hail characteristics under cold vortex and subtropical high background in Qinghai[J]. Desert and Oasis Meteorology,2018,12 (4): 22-29.]   
[20] 刘平英,周清倩,胡颖,等.近12年云南省云地闪活动变化及雷 电灾害时空分布特征[J].气象研究与应用,2018,39(3):86-91. [Liu Pingying, Zhou Qingqian,Hu Ying,etal. Changes in cloud-toground flashes and spatial and temporal distribution characteristics of lightning disaster in Yunnan in recent 12 years[J]. Journal of Meteorological Research and Application,2018,39(3): 86-91.]   
[21] 张廷龙,郄秀书,言穆弘.中国内陆高原不同海拔地区雷暴电学 特征成因的初步分析[J].高原气象,2009,28(5):1006-1016. [Zhang Yanlong, Qie Xiushu, Yan Muhong. Preliminary analysis on formation of electrical characteristics of thunderstorm in differ ent altitude regions in Chinese inland plateau[J]. Plateau Meteorology,2009,28(5): 1006-1016.]   
[22] 李政.重庆地区雷电活动规律及下垫面状况分析[D].南京：南 京信息工程大学,2011.[Li Zheng.Characteristics of lighting activity in Chongqing affected by the analysis of underlying surface [D]. Nanjing: Nanjing University of Information Science and Technology, 2011.]   
[23] 尹丽云,王灏樾,金文杰,等.低纬高原复杂地形对闪电的影响 分析[C]/第35届中国气象学会年会S19雷电物理和防雷新技 术——第十六届防雷减灾论坛.安徽:中国气象学会,2018. [Yin Liyun,Wang Haoyue,Jin Wenjie,etal.Analysis of the impact of complex terrain on lightning in low latitude plateau[C]// The $3 5 ^ { \mathrm { u } }$ Annual Meting of The Chinese Meteorological Society S19 Lightning Physics and New Lightning Protection Technology: The $1 6 ^ { \mathrm { u } }$ Forum on Lightning Protection and Disaster Reduction. Anhui: Chinese Meteorological Society,2018.]   
[24] Jayaratne ER, Kuleshov Y. Geographical and seasonal characteristics of the relationship between lightning ground flash density and rainfall within the continent of Australia[J].Atmospheric Research,2006,79(4): 1-14.   
[25]Xie Y R,Xu K, Zhang TF.Five-year study of cloud-to-ground lightning activity in Yunnan Province,China[J].Atmospheric Research,2013,129-130:49-57.   
[26] 韩贵锋,叶林,孙忠伟.山地城市坡向对地表温度的影响——以 重庆市主城区为例[J].生态学报,2014,34(14):4017-4024. [Han Guifeng,Ye Lin, Sun Zhongwei. Influence of aspect on land surface temperature in mountainous city:A case study in central area of Chongqing City[J].Acta Ecologica Sinica,2014,34(14): 4017-4024.]   
[27] 李进梁.亚洲季风区雷暴和闪电活动特征研究[D].兰州:兰州 大学,2O2O.[Li Jinliang.Studies on characteristics of thunderstorm and lightning activity over the Asian monsoon region[D]. Lanzhou: Lanzhou Univercity,2020.]   
[28] 宋晓爽,郑栋,张义军,等.上海及周边地区地闪活动特征及海 陆差异[J].气象科技,2014,42(1):164-172.[Song Xiaoshuang, Zheng Dong, Zhang Yijun,et al. Characteristics of cloud-to-gound lightning in Shanghai and circumjacent regions and land-sea difference[J]. Meteorological Science and Technology,2014,42(1):

# 164-172.]

[29]宫翠凤,姜中民,周丹,等.威海市雷暴特征分析[J].气象与环境 科学,2010,33(3): 48-51.[Gong Cuifeng,Jiang Zhongmin, Zhou Dan,et al.Analysis of thunderstorm characteristic in Weihai[J]. Meteorological and Environmental Sciences,2010,33(3): 48-51.]   
[30]刘磊.土壤电阻率估算及影响因素研究[D].南京:南京信息工 程大学,2O11.[Liu Lei. Studies on the estimation and the influencing factors of soil resistivity[D].Nanjing:Nanjing University of Information Science and Technology,2011.]   
[31] 徐霞,刘熙,刘刚,等.典型地区土壤电阻率的时空特性研究[J]. 水电能源研究,2017,35(2): 204-207.[Xu Xia,Liu Xi,Liu Gang, et al.Study on spatiotemporal property of soil resistivity in typical regions[J].Water Resources and Power,2017,35(2):204-207.]   
[32]刘刚,唐军,孙雷雷,等.不同地形地貌的雷电流幅值概率分布 对输电线雷击跳闸的影响[J].高电压技术，2013,39(1):17-23. [Liu Gang,Tang Jun,SunLeilei,etal.Influence of the distribution of lightning current amplitude in different landforms on the transmission-line's tripping operation[J]. High Voltage Engineering,2013,39(1): 17-23.]   
[33]李锐.土壤电阻率与云地闪之间的关系研究[D].大连:大连理 工大学,2O12.[Li Rui. The study on the relationship between soil resistivity and lightning flash to earth[D].Dalian:Dalian University of Technology,2012.]   
[34]王学良,张科杰,余田野,等.湖北省山区与平原雷电分布及其 参数特征[J].气象科技,2019,47(2):337-347.[Wang Xueliang, Zhang Kejie,Yu Tianye,et al.Distribution of lightning and parameter characteristics for mountain and plain areas of Hubei Province [J].Meteorological Science and Technology，2019,47(2):337- 347.]   
[35]李瑞芳,曹晓斌,陈奎,等.地域及气候对雷电参数的影响分析 [J].高压电器,2016,52(3):63-68.[LiRuifang,Cao Xiaobin,Chen Kui,et al.Effects of geographical and climatic conditions on light ning parameters[J].High Voltage Apparatus,2016,52(3): 63-68.]   
[36]李永福,司马文霞,陈林,等.基于雷电定位数据的雷电流参数 随海拔变化规律[J].高电压技术,2011,37(7):1634-1641.[Li Yongfu, Sima Wenxia, Chen Lin,et al.Law between parameters of lightning current and elevation based on lightning detection data [J.High Voltage Engineering,2011,37(7): 1634-1641.]

# Influence analysis of geographic parameters on lightning in plateau

HU Yanan'， TAO Shiyin’， GONG Meizhu²， MA Hailing (1.Qinghai Climate Center,Xining 81OoOo, Qinghai, China; 2.Qinghai Meteorological Service Center,Xining 81Oooo,Qinghai, China)

Abstract: The influence of terrain on lightning current parameters cannot be ignored as a basis for lightning theory study and engineering protectionapplication.Thus,in this study,the impacts of altitude,slope,aspect,and soil conductivityon the characteristics of cloud-to-ground lightning distribution in Qinghai Province,China,were quantitatively analyzed using cloud-to-ground lightningdata from 2014 to 2018,digital terrain altitude data,and the HWSDdata set.As per the data,it was determined that (1) cloud-to-ground lightning mostly concentrated at the altitude of $3 1 5 0 { \mathrm { - } } 4 8 5 0 \ \mathrm { m }$ and a slope of $0 ^ { - 3 5 ^ { \circ } }$ . The number of slope to the northeast had the greatest cloud-toground lightning,whereas the one to the southeast had the least.The electrical conductivity corresponding to cloud-to-ground lightning is primarily concentrated at a distance of $1 0 0 \Omega \cdot \mathrm { m }$ .(2) For a given unit area,the cloudto-ground lightning frequency increased first and then decreased with altitude.The number of cloud-to-ground lightning strikes increases slowlyas the slope increases.Inaddition,theaverage cloud-to-ground lightning intensity decreases first and then increases as altitude increases.It showed a trend of gradual increase as the slope increased and an ncreasing trendas the conductivity increased.(3)A correlation analysis was performed between the cloud-toground lightning data and the mean value of the geographical parameters in a $1 ~ \mathrm { k m } \times 1 ~ \mathrm { k m }$ grid covering the active areas of $9 2 ^ { \circ } 2 7 ^ { \prime } 0 0 ^ { \prime \prime } – 9 7 ^ { \circ } 4 4 ^ { \prime } 2 4 ^ { \prime \prime } \mathrm { E }$ and $3 1 ^ { \circ } 4 0 ^ { \prime } 4 8 ^ { \prime \prime } { - } 3 4 ^ { \circ } 1 6 ^ { \prime } 4 8 ^ { \prime \prime } \mathrm { N }$ ，The cloud-to-ground lightning density in the selected areas was positively correlated with altitude and negatively correlated with the slope.A negative corelation was noted between cloud-to-ground lightning intensity and mean altitude, but a positive correlation with slope.

Key words: lightning activity； altitude； slope； slope direction； soil conductivity； Qinghai Plateau