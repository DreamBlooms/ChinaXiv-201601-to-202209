# 基于GIS的宁夏路网空间特征研究

高玉祥¹，董晓峰²，梁颖²

(1.北京交通大学土木建筑工程学院,北京100044；2.北京交通大学建筑与艺术学院,北京100044)

摘要：宁夏回族自治区作为我国唯一的省级回族集聚地区，是一个很独特的地理-人口-交通单元,也是连接华北和西北的重要节点。以宁夏的交通路网数据为基础，通过设置阻抗改进网络分析法，并结合成本距离算法和GIS空间分析计算2011、2017年和2023年的县（区)可达性,研究全区路网的空间结构特征，并提出路网发展的决策建议。研究表明：宁夏已经构建路网的主骨架,但路网发展不均衡，北部的路网建设优于南部；县(区)的平均可达性由2011年的 $4 . 0 2 \mathrm { h }$ 缩短为2017年的 $3 . 7 5 \mathrm { h }$ ，路网可达性迅速提升，时空收敛效应显著;县(区)可达性的差异不断减小，全区路网空间结构的均衡性逐步增强。宁夏应重点建设以银川为中心的运输通道，通过加快南部地区的铁路建设来进一步优化全区路网布局，为全区的经济社会发展和“一带一路"建设提供运输支撑。

关键 词：路网；空间特征；GIS；改进网络分析法；宁夏文章编号：

路网是交通基础设施的重要组成部分，缩短了区域之间的时空距离，能够为地区发展提供运输支撑,影响着发展的速度和质量[]。可达性是路网的重要属性，各层级的路网规划也将其作为一个指标着重考虑。特别是高铁和高速公路，最显著的特点就是大幅度缩短了地区间的可达时间，提升了沿线区域的通达程度，从而促进经济社会发展。学者们对于可达性的研究，主要是通过分析景点便捷程度来为旅游规划提供决策建议[2-6],潘竟虎等[7]以全国A级景点为研究对象，运用栅格成本距离加权算法计算了A级景点的空间可达性。韩艳红等以南京都市圈为例，分析了多个时间断面南京都市圈空间联系的格局演变，黄晓燕等°运用复杂网络理论构建了广州市公共交通网络模型，根据定量分析的结果得到了地铁网络建设对公共交通可达性的影响。高玉祥、魏伟等[10-12]研究了甘肃省铁路网、公路网的扩张规律，并探讨路网建设与区域发展的耦合关系，其中杨晓敏分析了青海省主要节点城镇的公路网可达性及县域经济联系格局的演化规律。

已有的路网研究主要针对长三角、珠三角、京津冀等经济发达地区[13-17],关注点集中在可达性提升对区域和城市发展的促进作用，并未利用可达性对路网空间特征进行研究。通过文献调查可知，关于宁夏回族自治区路网结构及空间特征的研究较少，不利于今后该地区路网的合理建设。

学者们在可达性计算时广泛采用了网络分析法，该方法未考虑各种交通方式的换乘时间。为此，本文在矢量化路网的过程中通过设置阻抗来考虑交通方式转换需耗费的时间，计算结果更符合实际情况。利用改进的网络分析法和成本距离算法计算县（区)可达性，研究宁夏路网的空间特征，明晰路网建设的优势与不足，并提出未来路网建设的决策建议，使全区路网布局逐步趋于合理，更好地服务于宁夏的经济社会发展和“一带一路"建设。

# 1研究区概况

宁夏是我国5个少数民族自治区之一，东邻陕西、山西，北接内蒙古，南连甘肃，位于新亚欧大陆桥国内段的中间位置，具有对内连接东西部地区和对外通往中亚、西亚的特殊陆空优势，已成为我国向西开放的空中门户[18]。包兰铁路、宝中铁路和太中银铁路构成了全区的铁路网主骨架(图1)，定武高速、京藏高速、青银高速等贯穿南北，连接了主要的节点城市。

回族人口约占宁夏总人数的 $1 / 3 ^ { [ 1 9 ] }$ ,由于地理、历史和文化原因，回族在全自治区的分布呈现出“南多北少”的不均匀空间特征(图2)，这与全区人口的分布规律正好相反。

![](images/a7aaae1cfdf83328cb62d2a818a262936dfc0998da62b58ae26210f7ced9a9bc.jpg)  
Fig.1Road and railway network of Ningxia in 2017

注：该图基于国家测绘地理信息局标准地图服务网站下载的审图号为 $\mathrm { G S } ( 2 0 2 0 ) 4 6 3 2$ 号的标准地图制作，底图无修改，下同。

# 2 研究方法

# 2.1 可达性

平均可达性指某节点到研究区内其他节点所耗费时间的平均值，能体现该节点在区域内的交通区位优势，值越小表示可达性越好，与其他城市的空间联系越紧密，计算公式为[20-22]：

$$
A _ { i } = \sum _ { i = 1 } ^ { n } T _ { i j } \Big / { n }
$$

式中： $A _ { i }$ 为节点 $i$ 的平均可达性； $T _ { i j }$ 为研究区域内 $i$ 节点到 $j$ 节点的最短通行时间； $n$ 为路网中除选定节点外的其他节点总数。

# 2.2改进的网络分析

OD（Origin-destination）成本矩阵主要是利用研究区域的网络数据集来测算路网中多个起点到多个目标点的最小通行成本，通过ArcGIS的网络分析模块和OD矩阵原理可计算各节点由路网联系所耗费的时间。

![](images/9578f5310042d739f627aba7982e426cfef6e63b3190673d5454c0eb3154d7e9.jpg)  
图22017年宁夏回族人口分布Fig.2 Population distribution of Hui nationality ofNingxia in 2017

先前的研究在使用网络分析计算可达性时，没有考虑不同交通工具的换乘时间，为使计算值更符合实际情况,本文对网络分析法做了改进。构建网络数据集时，在需要换乘线路的两端设置一段阻抗来添加交通换乘需要的时间(图3)。

![](images/ccef647d93e58edb79b1f494ec57119820b98e29c39448abad3e5f966d92782a.jpg)  
图12017年宁夏路网  
图3换乘时间设置示意  
Fig.3Indication of transfer time setting

当位于铁路上的乘客由火车转换为汽车时，会经过铁路阻抗A和公路阻抗C，此时必须要等待汽车，所以公路阻抗C产生作用，将转换时间添加到阻抗C的成本属性中即可。由于设置的阻抗时间属性是分方向的，阻A的作用方向与目标方向相反，其不产生作用。若前进方向与图3所示方向相反，为公路转换铁路，此时换乘成本是等火车的时间，将其

# 干吴区地理

添加到阻抗A的成本属性中。利用上述方法在路网矢量化的过程中添加矢量阻抗及其属性。通过学者们关于铁路、公路的换乘时间及出行附加时间研究成果[23-24],结合宁夏路网的实际状况,将铁路与铁路、铁路与公路的换乘时间分别设置为 $1 . 0 \mathrm { { h } } , 0 . 7 \mathrm { { h } }$ 并对各种道路的速度赋值25(表1)。

Tab.1 Speed of roads and railways   

<html><body><table><tr><td>类型</td><td>铁路</td><td>高速</td><td>国道</td><td>省道</td><td>县道</td></tr><tr><td>速度/km·h-1</td><td>100</td><td>100</td><td>60</td><td>50</td><td>30</td></tr></table></body></html>

# 2.3成本距离

运用成本距离算法计算可达性时，根据不同类型道路的红线宽度，通过设置缓冲区将其转化为面要素(表2)，由于铁路在车站才与地方相互作用，高速公路只在出入口与其他道路相连接。根据相关研究成果[26-28],在铁路和高速公路两侧设置范围为$1 0 \mathrm { m }$ 的缓冲区，对非车站和出口处的缓冲区赋予很大的时间成本值，表示不允许通过。利用GIS的面转栅格功能转化为 $1 0 \mathrm { m } { \times } 1 0 \mathrm { m }$ 的栅格数据，并添加通行cost值，同样方法设置水系、坡度、起伏度等成本值，创建总成本阻力面。通行成本值采用某一像元移动 $1 \mathrm { k m }$ 所需的分钟数，按下式计算：

$$
s = \frac { 1 } { v } \times 6 0
$$

式中： $s$ 表示某一节点到其他任一节点移动 $1 ~ \mathrm { k m }$ 耗费的时间； $\boldsymbol { v }$ 表示设定的铁路、公路通行速度(表2)。

# 表2道路栅格时间成本及缓冲宽度

表1道路与铁路通行速度  
Tab.2 Cost time and buffer width of road grid   

<html><body><table><tr><td>类型</td><td>铁路</td><td>高速</td><td>国道</td><td>省道</td><td>县道</td><td>其他</td></tr><tr><td>时间成本/min</td><td>0.6</td><td>0.6</td><td>1.0</td><td>1.2</td><td>2.0</td><td>3.0</td></tr><tr><td>缓冲宽/m</td><td>20</td><td>60</td><td>30</td><td>24</td><td>18</td><td>14</td></tr></table></body></html>

利用栅格数据计算每个网格到目的网格的时间成本距离，其计算公式为[29]：

$$
K _ { i } = \left\{ \begin{array} { l l } { \displaystyle \frac { 1 } { 2 } \sum _ { i = 1 } ^ { n } \big ( c _ { i } + c _ { i + 1 } \big ) } \\ { \displaystyle \frac { \sqrt { 2 } } { 2 } \sum _ { i = 1 } ^ { n } \big ( c _ { i } + c _ { i + 1 } \big ) } \end{array} \right.
$$

式中： $c _ { i }$ 代表第 $i$ 个栅格单元的时间成本； $c _ { i + 1 }$ 指运动方向上第 $i { + } 1$ 个栅格单元的时间成本; $n$ 为栅格单元的总数目； $K _ { i }$ 为第 $i$ 个栅格单元的路网可达性。

# 3路网的空间特征分析

# 3.12011年全区路网特征

2011年宁夏的铁路、公路通车总里程分别为$1 0 2 9 \ \mathrm { k m } \ 、 2 4 5 0 6 \ \mathrm { k m }$ ,全区北部路网发达，包兰铁路、京藏高速连接了银川、吴忠、石嘴山3个地级市，各等级道路分布相对合理。南部地区铁路和高速公路基本为“一线牵"的格局，由宝中铁路、福银高速串联了同心、海原和原州3县(区），固原市其余县铁路、高速公路通达不畅，路网对地区经济发展的促进作用不强。

利用改进网络分析法和路网数据，计算2011年各县(区)相互间的通达时间(图4)。大部分县级节点间的可达时间为 $3 . 0 0 { \sim } 5 . 0 0 \mathrm { h }$ ,南、北部县(区)间的可达时间都大于 $7 . 0 0 \mathrm { { h } }$ ,泾源一惠农的时空距离最大，可达时间为 $9 . 4 7 \mathrm { ~ h ~ }$ ,可达时间最短的是金凤一兴庆。银川、吴忠到其他区域的可达时间最短，主要是由于其作为重要的交通枢纽，多条道路在此交汇，路网发展相对较好。

![](images/0bb1a2672b8c24a8b67bc863f2b7b6e548d1f6db6ee121f2a63b147dd975ea59.jpg)  
图42011年县(区)间的可达时间  
Fig.4 Reachable time between counties in 2011

根据建立的成本栅格图层，分别选取县级中心和部分重要城镇建立point对象图层，利用GIS的成本距离方法计算各节点的时间成本距离，然后通过重采样提取可达性文件中的积累成本值，并利用反距离权重方法空间化，得到宁夏2011年的空间可达

性(图5)。

银川、吴忠的可达性最好，可达性等时圈以其为中心向外围逐渐扩散，全区大部分区域的可达性都大于 $3 . 5 0 \mathrm { h }$ 。固原市的彭阳、泾源和隆德的可达性最差，全市近一半区域的可达性大于 $4 . 4 0 \mathrm { h }$ 。主要原因是固原与周围区域的主十交通方式只有福银高速公路和宝中铁路，但宝中线为低速度的单线铁路，对沿线地区的带动和辐射作用不足。东部的盐池县作为一个较独立的城市节点，距离其他节点远，区域内没有铁路通达，可达性也较弱。

![](images/150404af1980ea25c488e820271471341d031b435af6db5c39a2237a4360a4d3.jpg)  
图52011年宁夏空间可达性  
Fig.5Spatial accessibility ofNingxia in 2011

# 3.22017年全区路网特征

经过6a的路网建设，2017年的公路总里程比2011年增加了 $1 0 0 5 5 ~ \mathrm { k m }$ ，公路网密度为 $5 2 . 0 5 ~ \mathrm { k m }$ $( 1 0 0 \mathrm { k m } ^ { 2 } ) ^ { - 1 }$ ,增幅超过原来的 $4 0 \%$ 。2016年固原一西吉高速公路、李家庄一泾河源高速公路分别通车，固原市实现了“四县一区"的 $^ { \textrm { 1 h } }$ 交通圈，宁夏也跨入县县通达高速公路的省区行列，高速公路成为连接区域内城市的快速交通。高等级路所占比重显著提高，但铁路里程未增加。

全区县级节点间的可达时间都有不同程度的缩短， $3 . 5 0 \mathrm { h }$ 内能够互达的县(区)数目显著增多，北部县(区)间的可达时间在 $3 . 5 0 \mathrm { h }$ 以内(图6)。南部地区的部分县可在 $6 . 0 0 \mathrm { { h } }$ 内到达北部，固原至银川的通达时间缩短了 $0 . 9 4 \mathrm { ~ h ~ }$ ，南北地区之间的路网结构得到优化，空间联系增强(表3)。

![](images/713052b41e5e2ee87e862f585e7e774050e462d35912d5fa2858b3e46ee612aa.jpg)  
图62017年县(区)间的通达时间  
Fig.6 Reachable time between counties in 2017

高速公路建设明显改善了宁夏的可达性（图7)，固原市的弱可达性区域范围进一步减小，但全区南部可达性的提升幅度快于北部地区，高速公路布局已由线状向网状转变，不同等级道路网布局逐步完善，但快速运输通道单一。地级节点中，银川作为全区的交通枢纽，其空间可达性为 $2 . 6 8 \mathrm { ~ h ~ }$ ，固原的可达性为 $3 . 5 6 \mathrm { h }$ ,路网建设最薄弱。

路网作为各景点的联系纽带，是旅游业发展的重要支撑。宁夏的地理景观和人文资源荟萃，旅游业已成为地区经济的重要组成。但主要景点呈现南北各自聚集的特点，通过研究2017年景点间的通达情况来分析路网对旅游业发展的支撑作用(图8)。

南北景点间的可达时间基本大于 $7 . 0 0 \mathrm { { h } }$ ,空间联系作用弱，不利于全区旅游业的整体协调发展。固原为传统的农业地区，经济发展落后限制了路网的建设。借助丰富的旅游资源来发展第三产业，对固原今后的发展具有重要意义。应进一步加快固原对内互通、对外连接的运输网络，更好服务于当地经济社会建设。

# 3.32023年全区路网特征

根据宁夏在建的铁路、公路项目，2023年将有银西高铁、中兰客专、银中城际等线路通车，运营总里程突破 $2 0 0 0 { \mathrm { k m } }$ ,其中高速铁路超过 $8 0 0 \mathrm { k m }$ ，大部分区域将进入高铁时代

# 干旱区地理

# 表3主要城市间的可达时间

Tab.3 Access time between major cities   
/h   

<html><body><table><tr><td>城市</td><td>金凤</td><td>利通</td><td>大武口</td><td>沙坡头</td><td>原州</td><td>灵武</td><td>红寺堡</td><td>青铜峡</td><td>盐池</td><td>同心</td><td>海原</td></tr><tr><td>金凤</td><td>1</td><td>1.55</td><td>1.79</td><td>3.34</td><td>5.17</td><td>1.46</td><td>3.11</td><td>1.35</td><td>3.03</td><td>3.27</td><td>5.11</td></tr><tr><td>利通</td><td>1.29</td><td>1</td><td>3.04</td><td>2.59</td><td>4.03</td><td>0.69</td><td>1.46</td><td>0.65</td><td>2.53</td><td>2.43</td><td>4.07</td></tr><tr><td>大武口</td><td>1.46</td><td>2.24</td><td>1</td><td>5.03</td><td>7.26</td><td>3.09</td><td>4.12</td><td>3.03</td><td>4.52</td><td>5.66</td><td>7.30</td></tr><tr><td>沙坡头</td><td>3.02</td><td>2.38</td><td>3.92</td><td>1</td><td>3.32</td><td>3.55</td><td>1.98</td><td>2.49</td><td>3.69</td><td>1.92</td><td>3.16</td></tr><tr><td>原州</td><td>4.23</td><td>3.70</td><td>6.06</td><td>2.91</td><td>1</td><td>4.59</td><td>2.77</td><td>4.12</td><td>4.61</td><td>1.60</td><td>1.97</td></tr><tr><td>灵武</td><td>1.39</td><td>0.67</td><td>2.46</td><td>3.11</td><td>4.20</td><td>1</td><td>1.82</td><td>1.06</td><td>1.98</td><td>2.99</td><td>4.13</td></tr><tr><td>红寺堡</td><td>2.11</td><td>1.32</td><td>3.69</td><td>1.94</td><td>2.63</td><td>1.57</td><td>1</td><td>1.76</td><td>1.84</td><td>1.17</td><td>2.81</td></tr><tr><td>青铜峡</td><td>1.25</td><td>0.64</td><td>2.36</td><td>2.34</td><td>3.94</td><td>0.93</td><td>1.60</td><td>1</td><td>2.63</td><td>2.52</td><td>4.16</td></tr><tr><td>盐池</td><td>2.17</td><td>2.31</td><td>3.93</td><td>3.19</td><td>4.30</td><td>1.75</td><td>1.69</td><td>2.37</td><td>1</td><td>3.01</td><td>4.65</td></tr><tr><td>同心</td><td>3.18</td><td>2.25</td><td>4.17</td><td>1.83</td><td>1.50</td><td>2.49</td><td>1.10</td><td>2.14</td><td>2.97</td><td>1</td><td>1.64</td></tr><tr><td>海原</td><td>3.89</td><td>3.27</td><td>5.46</td><td>2.51</td><td>1.53</td><td>3.21</td><td>2.30</td><td>3.52</td><td>4.11</td><td>1.24</td><td>二</td></tr></table></body></html>

注：右上角、左下角分别是2011年和2017年城市相互间的通达时间。

![](images/827f0a6fe3bb7e8c967de707ee29dfd5e98d2b9f3f11fab3bc15c1b96da6bd66.jpg)  
图72017年宁夏空间可达性  
Fig.7Spatial accessibility ofNingxia in 2017

假设研究期内其他交通未发生变化，在路网数据库中添加拟通车铁路、公路项目，届时除固原外，其余4个地级市都有高铁通达，相互间的通达时间值均在 $1 . 5 0 \mathrm { h }$ 内(图9)。银川到固原的时间也由原来的 $6 . 5 0 \mathrm { h }$ 缩短为 $2 . 5 0 \mathrm { h }$ ,对促进固原地区与首府之间的人员往来和经济交流具有重要意义。

高速铁路建设极大改善了全区的路网可达性，5个地级市的可达性都小于 $3 . 0 0 \mathrm { { h } }$ （图10)，在西北部形成了一个条带状的可达性优质区，是全区空间联系最强的区域。由于宝中线扩能改造和公路网建设优化，宁夏南部的可达性也明显提升，但通达便捷程度仍然落后于北部地区。

![](images/b5aabb2c7e3c2daeedad1887fe621d8d6fb39fd4619bdfc9bfc0ab909ffd48fd.jpg)  
图82017年主要景点间的通达时间  
Fig.8 Reachable time between major attractions in 2017

从2011年到2023年各县(区)的可达性都在增强，平均可达性由2011年的 $4 . 0 2 \mathrm { h }$ 缩短为2017年的$3 . 4 2 \mathrm { ~ h ~ }$ （图11)，节点的可达性差异不断减小。可达性改善最明显的是彭阳、泾源、隆德和原州等，提升的幅度值大小与其初始值有关。到2023年，县(区）的预测可达性均值为 $2 . 7 2 \mathrm { h }$ ,约为2011年的2/3。固原的县(区)的可达性均小于 $3 . 7 0 \mathrm { h }$ ,可达性提升能够推动固原地区的旅游业积极发展，促进全自治区

![](images/7174a5802e6177bab900c34f930c070016b60dba1370d71e9f79f2a5d2ac34f7.jpg)  
图92023年县(区)间的可达时间

![](images/469a42cc43b17809d08feb57c913a4974287aa4e9127b1b2d98a852cb7baefe1.jpg)  
Fig.9 Reachable time between counties in 2023   
图102023年宁夏空间可达性  
Fig.10 Spatial accessibility ofNingxia in 2023

经济社会协调发展。

# 3.4宁夏路网发展的建议

2019年8月国家发展和改革委员会印发了《西部陆海新通道总体规划》,明确提出“强化主通道与西北地区综合运输通道的衔接，连通兰州、西宁、银川等重要城市，提升通道对西北地区的辐射和联动作用”，这是推进西部大开发形成新格局的重要举措，宁夏经济社会建设将迎来新的发展机遇。

![](images/482a0395b1bbc8f91cce4babcdda12bcae2664b0e13881869a2d6568a096507b.jpg)  
图11 县(区)可达性变化比较  
Fig.11 Comparison of accessibility among counties

基于上述研究及西部陆海新通道总体规划，对未来宁夏的路网建设提出以下建议：

（1）重点强化综合运输通道功能，对外逐步建立以普速铁路为主的货运通道和以高速铁路为主的客运通道，不断加强银川与周边省会的联系能力，提升银川的综合交通枢纽作用。

（2）全区应重点建设以铁路为主轴、以高速公路为支撑的区域路网主骨架，进一步连通骨架影响范围外的城市节点来提升其可达程度。通过路网建设来带动经济发展，实现全区的均衡发展。

(3）固原市始终是宁夏路网建设比较薄弱的地区，快速通道仅有宝中铁路和福银高速公路对外连接，与区内及周边省区的联系不紧密，要加快建设固原与银川、平凉、庆阳的路网联系通道。

# 4结论

本研究以路网数据为基础，改进了网络分析法，并结合成本距离、可达性、GIS空间分析对宁夏路网的空间特征进行研究，结论如下：

（1）全区路网形成了“十字型"的路网主骨架，空间上总体呈现为“北强南弱"的特征，路网分布不均衡。从路网结构来看，宁夏北部地区已建设成为网状结构，南北部县(区)的空间联系作用不强，固原仍是今后路网建设的重点区域。

(2）县(区)平均可达性由2011年的 $4 . 0 2 \mathrm { h }$ 缩短为2017年的 $3 . 7 5 \mathrm { ~ h ~ }$ ，到2023年预计为 $2 . 7 2 \mathrm { ~ h ~ }$ 。整体可达性明显提升但具有差异性，南部地区节点的可

# 干吴区地理

达性改善较明显。相较于2011年，节点间的可达性差异不断减小，全区路网空间结构的均衡性逐步增强。

（3）宁夏路网空间结构的形成受经济因素和自然因素的共同作用，北部地区由于经济发展好、地形平坦，路网布局较为合理，而南部的路网建设薄弱。“一带一路"战略和"西部陆海新通道"建设会给宁夏带来重要的发展机遇，通过不断优化全区的路网结构来推动地区发展

# 参考文献(References)

[1]Givoni M.The development and impact of the modern High Speed Train[J]. Transport Reviews,2014,26(5): 593-612. [2]潘稼佳.交通可达性与旅游经济联系的空间关系分析[D].乌鲁 木齐:新疆大学,2019.[Pan Jiajia.Analysis of the spatial relationship between traffic accessibility and tourism economic relationship:Taking 15 prefectures in Xinjiang asan example[D]. Urumqi: Xinjiang University,2019.] [3]钟业喜,陆玉麒.江苏省城镇可达性格局演变[J].长江流域资源 与环境,2011,20(8): 903-910.[Zhong Yexi,Lu Yuqi. Urban accessibility and its structure evolution in Jiangsu Province[J].Resources and Environment in the Yangtze Basin,2011,20(8): 903-910.] [4]高玉祥,韩峰,李泽宇,等.基于GIS的轨道交通与旅游热点可 达性耦合关系—以天水市为例[J].测绘工程,2019,28(3):   
57-60,65.[Gao Yuxiang,Han Feng,Li Zeyu, et al. Study on coupling relations of the important tourism attractions and rail transit based on GIS: A case studyof Tianshui[J]. Engineering of Surveying and Mapping,2019,28(3): 57-60, 65.] [5]周恺,刘冲.可视化交通可达性时空压缩格局的新方法—以 京津冀城市群为例[J].经济地理,2016,36(7):62-69.[Zhou Kai, Liu Chong.A new method to visualise the time-space compression effct in road network: A case study of Beijing-TianjingHebei region[J]. Economic Geography,2016,36(7): 62-69.] [6]Mostafa M,Lei Z.Incorporating spatial equity into interurban road network design[J]. Journal of Transport Geography,2O14,39(1):   
156-164. [7]潘竞虎,李俊峰.中国A级旅游景点空间分布特征与可达性[J]. 自然资源学报,2014,29(1): 55-66.[Pan Jinghu,LI Junfeng. Spatial distribution characteristics and accessibility of A-grade tourist attractions in China[J].Journal of Natural Resources,2O14,29(1):   
55-66.] [8]韩艳红,陆玉麒.南京都市圈可达性与经济联系格局演化研究 [J].长江流域资源与环境,2014,23(12):1641-1648.[Han Yanhong,Lu Yuqi. Analysis of accessibility and economic linkage spatial patern evolution of Nanjing metroplitan area[J].Resources and Environment in the Yangtze Basin,2014,23(12):1641-   
1648.]   
[9]黄晓燕,张爽,曹小曙.广州市地铁可达性时空演化及其对公交 可达性的影响[J].地理科学进展,2014,33(8):1078-1089. [Huang Xiaoyan, Zhang Shuang, Cao Xiaoshu. Spatial-temporal evolution of Guangzhou subway accessibility and its effects on the acessibilityof public transportationservices[J]. Progress inGeography,2014,33(8): 1078-1089.]   
[10]高玉祥,韩峰,袁锋.“一带一路"节点省份铁路路网扩张时空关 系研究——以甘肃省为例[J].铁道科学与工程学报,2018,15 (8): 2172-2178.[Gao Yuxiang,Han Feng,Yuan Feng. Study on temporal-spatial relations of railway network expansion in“the Belt and Road”node province: A case study of Gansu Province[J]. Journal of Railway Science and Engineering,2018,15(8): 2172- 2178.]   
[11] 魏伟,石培基,脱敏雍,等.基于GIS的甘肃省道路网密度分布 特征及空间依赖度分析[J].地理科学,2012,32(11):1297- 1303.[WeiWei,Shi Peiji,Tuo Minyong,etal. The road network density and its spatial dependence in Gansu Province based on GIS[J].Scientia Geographica Sinica,2012,32(11): 1297-1303.]   
[12] 杨晓敏,李玲琴,付建新,等.30a青海省公路可达性及县域经 济联系格局演化[J].干旱区地理,2018,41(6):1376-1387. [Yang Xiaomin,Li Lingqin, Fu Jianxin,et al. Pattern variation of accessibility and economic linkage at county scale in Qinghai Province from 1986 to 2016[J].Arid Land Geography,2018,41 (6): 1376-1387.]   
[13] 姚兆钊,曹卫东,岳洋,等.高铁对泛长三角地区可达性格局影 响[J].长江流域资源与环境,2018,27(10):2182-2193.[Yao Zhaozhao,Cao Weidong,Yue Yang,et al. Study on the influence of high-speed railway on the accessibility pattern in Pan-Yangtze river delta region[J]. Resources and Environment in the Yangtze Basin,2018,27(10): 2182-2193.]   
[14] 王雪,白永平,汪凡,等.基于街道尺度的西安市基础教育资源 空间分布特征研究[J].干旱区地理,2019,42(6):1470-1477. [Wang Xue,Bai Yongping,Wang Fan,et al. Characteristicsof spatial distribution of basic education resources in Xi’an on street scale[J]. Arid Land Geography,2019,42(6): 1470-1477.]   
[15] 鲍超,邹建军.中国西北地区城镇化质量的时空变化分析[J].干 旱区地理,2019,42(5): 1141-1152.[Bao Chao,Zou Jianjun. Spatiotemporal variations of urbanization quality in northwest China [J]. Arid Land Geography,2019,42(5): 1141-1152.]   
[16]卢茜.长三角地区高速公路网可达性变化与城市区位分析[D]. 上海：上海师范大学,2011.[Lu Qian.Analysis of accessibility change and urban location of expressway network in Yangtze River Delta[D]. Shanghai: Shanghai Normal University,2011.]   
[17]薛冰洁.珠三角公路运输网络规模的合理性和发展规律研究 [D].西安:长安大学,2011.[Xue Bingjie.Research on the rationalityand development law of the scale of the road transportation network inthePearlRiverDelta[D].Xi'an: Chang'an Univeriy 2011.]   
[18]周瑞瑞.宁夏沿黄城市群城镇化质量及时空格局演变特征研究 [D].银川:宁夏大学,2017.[Zhou Ruirui.Study on urbanization quality and spatial-temporal pattern evolution characteristics of Ningxia Urban Agglomeration along the Yellow River[D]. Yinchuan: Ningxia University,2017.]   
[19]宁夏回族自治区统计局.宁夏统计年鉴2018[M].北京:中国统 计出版社,2018: 26-28.[Statistics Bureau of Ningxia Hui Autonomous Region.Ningxia statistical yearbook 2O18[M]. Beijing: China Statistical Publishing House,2018: 26-28.]   
[20]Yin C,HeQ, Liu Y,et al. Inequality of public health and its role in spatial accessibility to medical facilities in China[J].Applied Geography,2018,92(6): 50-62.   
[21]Williams S,Wang FH.Disparities in accessibility of public high schools,in Metropolitan Baton Rouge,Louisiana 199O—2010[J]. Urban Geography,2014,35(7):1066-1083.   
[22]肖冀星,王振报.基于GIS的邯郸市医疗服务设施可达性分析 [J].测绘与空间地理信息,2020,43(1):137-140,144.[Xiao Jixing,Wang Zhenbao.Accessibility analysis of medical service facilities in Handan based on GIS[J].Geomatics & Spatial Information Technology,2020,43(1): 137-140,144.]   
[23]马红伟.新建包海通道西安至安康高速铁路速度目标值研究 [J].铁道标准设计,2019,63(3):7-11.[Ma Hongwei.Research on targeted speed of Xi’an: Ankang high-speed railway on newly built Baotou-Haikou Corridor[J]. Railway Standard Design, 2019, 63(3): 7-11.]   
[24]王辉.佳木斯至沈阳铁路客运专线速度目标值选择研究[J].铁 道标准设计,2017,61(9):1-5.[Wang Hui. Study on selection of target speed value for Jiamusi-Shenyang dedicated passenger railway[J]. Railway Standard Design,2017,61(9): 1-5.]   
[25] 曹小曙,李涛,杨文越,等.基于陆路交通的丝绸之路经济带可 达性与城市空间联系[J].地理科学进展,2015,34(6):657-664. [Cao Xiaoshu,Li Tao,Yang Wenyue,et al.Accessibility and urban spatial connections of cities in the Silk Road Economic Belt based on land transportation[J].Progress in Geography,2015,34 (6): 657-664.]   
[26] 朱杰,管卫华,蒋志欣,等.江苏省城市经济影响区格局变化[J]. 地理学报,2007(10):1023-1033.[Zhu Jie,Guan Weihua, Jiang Zhixin,et al. The evolution of urban economic effect regions in Jiangsu Province[J]. Acta Geographica Sinica,2007(1O): 1023- 1033.]   
[27]于策,李远富,林芳,等.基于GIS的津保铁路对沿线城市可达 性影响分析[J].铁道运输与经济,2017,39(5):18-22.[Yu Ce,Li Yuanfu,Lin Fang,et al.Analysis on Influence of Tianjin-Baoding Railway on accessibility of adjacent cities based on GIS[J]. Railway Transport and Economy,2017,39(5): 18-22.]   
[28] 高玉祥,韩峰,任洁,等.“一带一路"沿线甘肃省铁路网与区域 发展的耦合关系研究[J].铁道标准设计，2019,63(8):46-52. [Gao Yuxiang,Han Feng,Ren Jie,et al. Study on the coupling relationship of Gansu railway network and regional development along“the Belt and Road”areas[J]. Railway Standard Design, 2019, 63(8): 46-52.]   
[29]牟乃夏,刘文宝,王海银,等.ArcGIS地理信息系统教程—从 初学到精通[M].北京:测绘出版社,2012:281-289.[Mu Naixia, Liu Wenbao,Wang Haiyin, et al.ArcGIS geographic information system course: From beginning to proficiency[M]. Beijing: Surveying and Mapping Publishing House,2012: 281-289.]

# 干旱区地理

# Spatial features of road networks in Ningxia based on GIS

GAO Yuxiang'， DONG Xiaofeng²， LIANG Ying² (1.College of Civil Engineering,Beijing Jiaotong University,Beijing 1Ooo44,China; .College of Architecture and Design,Beijing Jiaotong University,Beijing 1OOO44,China)

Abstract: Ningxia Hui Autonomous Region is an important transportation node connecting northern and northwestern China,where a purpose-built road network can accelerate regional development.The accessibility of counties in 2011,2017,and 2023 (projected) was calculated based on the road network of Ningxia,by using an improved network analysis method,cost distance algorithm,and ArcGIS spatial analysis.The road network in the wholeregion was analyzed for the spatial distribution of accessbility characteristics,and suggestions for future road construction are put forward. The results are as follws: (1) The road network in Ningxia forms a cross, which is generally characterized as strong in the north and weak in the south,because the layout is unbalanced. The spatial structure ofthe road network in Ningxia is affected by both economic and natural factors.(2)Access time between northern counties is shorter than that of southern counties.The road network in the south is the key area forroad construction in the future.(3）A traditional network analysis method is optimized using the consideration of transfer time,by setting impedance,which makes the accessibility calculation more scientific and reasonable.(4) The average accessibility of counties was reduced from 4.O2 h in 2011 to $3 . 7 5 \mathrm { ~ h ~ }$ in 2017 and is expected to be $2 . 7 2 \mathrm { ~ h ~ }$ in 2023. The accessbility of the road network in the whole region is constantly improving.There are diferences in the range of improvement,and the accessibility of southern nodes is obviously improved. (5) Compared with 20l1,the accessibility diference between counties is decreasing,so the balance in the spatial patern of road networks in the whole region is gradually increasing.(6) Ningxia should shift its atention to build both inner and outer transportation channels centered on Yinchuan,and road construction in the south should be accelerated to optimize the road network layout of the whole region.

Key words: road network; spatial feature; GIS; improved network analysis; Ningxia