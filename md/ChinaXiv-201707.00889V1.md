# DOI:10.5846/stxb201604080644

穆博,李华威,AudreyL.Mayer，何瑞珍,田国行.基于遥感和图论的绿地空间演变和连通性研究——以郑州为例.生态学报,2017,37（14)：4883-4895.  
MuB,LiHWudreLeHeRZanGcafsceoivitsedootesingdasedyin Zhengzhou，China.Acta Ecologica Sinica,2017,37(14） :4883-4895.

# 基于遥感和图论的绿地空间演变和连通性研究以郑州为例

穆博1,²,李华威¹,AudreyL.Mayer³，何瑞珍¹,田国行1,\*

1河南农业大学林学院，郑州450002  
2 河南农业大学资源与环境学院，郑州450002  
3密歇根理工大学森林资源和环境科学学院,霍顿，密歇根州,49931,美国

摘要：绿地空间是人类和自然生态环境的重要组成部分,其连通性是绿地有效发挥生态和社会服务功能的重点,对促进生物多样性保护、人类户外空间游憩和城乡空间的健康可持续发展具有重要意义。以郑州为例,基于图论的原理和算法,以4个时期$3 0 \mathrm { m }$ 分辨率的Landsat 5和Landsat 8影像为基本数据源,在 ArcGIS10.2、ENVI5.0和Graphab 1.2.1软件中,提取郑州市域范围内的绿地空间信息,分析了绿地斑块规模、数量和空间分布特征的动态变化过程,揭示了绿地空间连通性动态变化的规律和原因,探讨了图论指数在诊断和优化绿地空间连通性上的应用。结果表明;2000年到2013年间，随郑州市域绿地空间总量和斑块规模的增加,绿地空间整体连通性指数增加了4.7倍,且在2009年到2013年间增加幅度最大;绿地斑块规模与绿地空间整体连通性指数、最大连通单元体规模和绿地斑块节点度指数呈显著正相关关系;绿地空间连通性的区域差异特征与绿地空间分布特征一致,均呈现西高东低的分布规律，且随时间变化呈现出由西向东扩展的趋势;图论指数可以用来反映各种尺度上绿地空间的连通性,其中绿地斑块的节点度指数和中间度核心性指数可以用来诊断和筛选对整体绿地空间连通性起关键性和脚踏石作用的绿地斑块，在今后城乡绿地系统规划和绿地生态网络优化上具有重要的应用前景。

关键词：绿地空间；连通性；图论；遥感；郑州

# Dynamic changes of green-space connectivity based on remote sensing and graph theory : a case study in Zhengzhou， China

MU $\mathbf { B o } ^ { 1 , 2 }$ ,LI Huawei',Audrey L. Mayer³，HE Ruizhen’,TIAN Guohang   
1 College of Forestry，Henan Agricultural University，Zhengzhou 45Oo02，China   
2 Colegeof ResourcesandEnvironmental Sciences，Henan Agricultural University,Zhengzhou 45oo02，China   
3SchoolfFsodoetlelclUstooUn

Abstract：Gren space is the main part of human and natural ecological environmental systems.The connectivityof green spaceis fundamental for thesurvival offloraand fauna,humanoutdoor recreation,andurban sustainability.Theobjective of this studywas toquantifythedynamicchanges of green-spaceconnectivityof Zhengzhou,including therapidurbanization processes，determination of external and internal causes，and aalysisof the graph theoryapplied to the studyof greenspace connectivitydiagnosisand optimization bu using remote sensing dataand graph metrics.Theresults indicated that green-spaceconnectivityin Zhengzhou increased by4.7-fold with thegrowth of the gren-space areaand patch size from 2000 to 2013，with the largest incrementin2O09—2O13.Thegreenpatch sizewaspositivelycorrelated with the integral indexof connectivity，sizeof the largestcomponent，andnode degre.Thecharacteristicsof green-space connectivityin diffrent urban districts were consistent with the distribution of greenspace.Graph metrics were calculated using Graphab softwareand toreflectthegreen-spaceconnectivityindifferent scales.Nodedegreeandbetweenness centralitycanbeused to reflectthe locationandchangesof the keystone green patches，whichneed moreconsiderationinthenext stepof genspace planning.Therefore,theapplication of graph theorycombined with remotesensing isimportantforthe futuregreensystem planning and optimization. y

Key Words:green space；connectivity；graph theory；remote sensing；Zhengzhou，China

绿地空间不仅是大自然中动植物赖以生存的基础,也是城市环境与自然环境之间物质和能量流通的重要载体,更是人们户外休闲游憩的重要场所。同时,绿地也是一个城市健康可持续发展必须具备的绿色基础设施,在改善区域生态环境[1,2]、缓解人们的精神压力[3]和提高人们生活质量等方面均有着不可替代的作用[4-6]。

绿地空间规模、分布特征及其连通性不仅是绿地空间结构研究的重点,也是城乡绿地生态网络构建和绿地系统规划考虑的重要内容。绿地斑块规模是衡量其生态服务价值的重要指标[,绿地分布特征往往反映其存在的重要性和变化的原因,而绿地斑块间的连通性则对城乡绿地系统物质和能量的流通具有重要的意义[8]。尤其是在快速城市化建设引起的景观破碎化加剧[9],生物多样性急剧减少的背景下,景观连通性逐渐引起景观生态学家和景观规划设计师的重视,并对其进行了大量的研究。Park[10]基于7种物种分布和行为特征对美国菲尼克斯都市区不同城市梯度的景观生态连接度进行评估,并绘制出连接路径,为生态保护规划提供了重要依据;Rabinowitz[1]基于最短路径连接模型对美洲豹的迁徙廊道进行研究,找出了182条潜在的需要优化的生态廊道。在这些研究中,整体连通性指数(IIC)是最常用的评价指标,图论算法被认为是一种能够研究较大区域范围内生境网络连接度的简便有效方法[12-14],其图形分析能够为景观管理和土地利用规划等提供直观的决策支持[14]。

图论最早起源于17世纪欧拉关于哥尼斯堡七桥问题的研究,后来演变成数学的一个分支,中国的“河图洛书"被认为是图论起源的重要思想[15]。图的理论及其应用是构成图论的主要内容[16]。一个图是由若干节点和连接线共同组成的数据结构[47-I8],每条线连接两个节点,而在一定阈值范围内多个节点相互连接构成的连通体被称为一个连接单元[19]。在一个网络体系中,节点可以代表空间位置、物体、群体、生境或他们的属性;连接线(Links)则可以代表因果关系、统计信息、逻辑推理、空间关系或过程,如物质和能量的流通等[18]目前,图论已经被广泛应用在地理科学、信息技术科学、计算机科学和社会科学等问题分析中[17]。地理学家将图论用来研究水文过程、交通运输和路径优化等地貌的内在特征与外在联系[18];生态学家将其引入景观格局和过程的研究中,尤其是生境连接度的分析和生态网络的优化[17,20]。王铭子[8]认为城市绿地系统可以简化为由节点和连接线组成的网络结构。因此,图论指数也可以用来研究绿地系统的连通性和结构优化。

鉴于图论在绿地系统规划和绿道网络构建上具有重要的应用价值,本文基于图论原理和算法,借助遥感技术对过去13年间郑州市域极速城镇化过程中城乡绿地空间连通性的动态变化过程进行研究,并根据所得结果与绿地自身形态特征的关联性分析,揭示其发生变化的内因(绿地空间总量、板块规模和分布特征的变化)和外因(政府决策对绿地空间扩展的影响),论证和探讨图论指数在诊断和优化绿地空间连通性上的应用价值,希望能够为未来城乡绿地空间发展与规划提供一定的理论依据。

# 1研究区域概况

郑州坐拥嵩山,紧临黄河,地理位置优势显著,既是河南省的省会城市,中国八大古都之一,又是中原经济区(CPER)的核心增长城市和国家中心城市,南北京广通道和东西新欧亚大陆桥中段陇海-兰新通道在此交汇（图1)。在《全国流通节点城市布局规划(2015—2020年)》中还被定位为国家级流通节点城市,是我国的综合交通枢纽。市域总面积为 $7 4 4 6 . 2 \mathrm { k m } ^ { 2 }$ ,包括郑州市、新郑市、荥阳市、巩义市、登封市、新密市和中牟县,其中郑州市主城区总面积 $1 0 1 0 . 3 \mathrm { k m } ^ { 2 }$ ,包括二七区、金水区、管城区、中原区和惠济区,隶属于郑州市的上街区位于荥阳市西侧,故不在郑州市主城区内（图1)。2000年到2013年,郑州市域总人口从665.9万人增加至919.1万人,城镇化率从 $5 5 . 1 \%$ 增加至 $6 7 . 1 \%$ ,处于城镇化水平快速上升阶段。

![](images/8b7b4be2b32abd4eaed53bd3d6aaa3513069b5c45977b951559b0b7692a178b6.jpg)  
图1郑州区位和行政区划图  
Fig.1 Location and administrative districts of Zhengzhou in China

# 2研究方法

2.1遥感数据获取与处理

本文所用遥感影像,包括 2000年、2004年、2009 年的Landsat 5和 2013 年的 Landsat 8（path124，row 36,level1T产品）,均从美国USGS 网站和中国科学院计算机信息中心获取,影像精度为 $3 0 \mathrm { m }$ ,无云,图像质量较好。为了避免季节差异,所有影像均选自植被覆盖良好的夏季(5月和6月)。其它辅助影像解译的数据,包括同时期Google Earth 中的历史影像、2010 年郑州市总体规划图和郑州行政区划图等均为实验室长期留存。

遥感影像的解译步骤主要为：在ArcGIS10.2中采用世界1984_UTM_49N坐标系,分别对四期的遥感影像进行几何校正（误差小于0.5个像元）、辐射校正和大气校正后,借助 ENVI5.0,利用最大似然监督分类法对四个时期的遥感影像进行分类,并参照同时期Google Earth Pro中高分辨率历史影像,采用目视解译的方法对分类结果进行反复纠错,然后在ENVIclassic 中通过混淆矩阵对分类结果进行验证,直至分类精度高于 $9 5 \%$ 后生成最终分类结果[21]。最后,提取研究范围内的城乡绿地空间图像和数字化信息,包括所有植被覆盖良好的自然林草地和人工城市绿地,并在 ArcGIS10.2中按照面积大小,将所有的绿地斑块重分类为5个规模等级：$< 1 . 0 \ \mathrm { h m } ^ { 2 }$ ， $= 1 . 0 \cdot$ 1 ${ \cdot } 5 . 0 \ \mathrm { h m } ^ { 2 }$ ， $= 5 . 0$ 一 $1 0 . 0 \ \mathrm { h m } ^ { 2 }$ ， $= 1 0 . 0$ 一 $1 0 0 . 0 \ \mathrm { h m } ^ { 2 }$ $> 1 0 0 . 0 \ \mathrm { h m } ^ { 2 }$ 。

# 2.2景观分布指数的计算

景观分布指数能够定量化分析特定研究区域内各类景观空间在不同地域范围的分布特征,且不受空间范

围和景观面积的影响[22]。景观分布指数越大,说明该景观类型的分布权重越高[23]。景观分布指数 $( D )$ 的计算公式为：

$$
D = \frac { A _ { i } / T _ { i } } { A / T }
$$

式中， $A _ { i }$ 为某一空间范围内景观 $i$ 的面积, $T _ { i }$ 为研究区域景观 $i$ 的总面积,A为该空间总面积， $T$ 为研究区域总面积。本文将其用来研究绿地空间在郑州市域不同行政区域内的分布特征。

# 2.3 图论指数的计算

图论指数主要是从拓扑学的角度来反映绿地空间网络的连通性,适用于各种空间尺度,对城乡生态网络的构建具有重要作用[14]。本文在Graphab1.2.1软件中，以 $5 0 0 \mathrm { m }$ 服务半径为绿地斑块之间相互连通的距离阈值,选取五个图论指数(表1),来量化和可视化绿地空间连通性的变化过程和绿地斑块位置的重要性,并将其与绿地斑块规模和分布特征进行关联性分析,揭示绿地空间连通性变化的内在原因和图论指数在诊断和优化绿地系统连通性上的应用。

表1图论指数的含义与计算公式  
Table1 The meaning and calculation formula of selected graph metrics   
表2不同规模绿地空间总面积和斑块数量  

<html><body><table><tr><td>图论指数 Graph metrics</td><td>含义 Meaning</td><td>计算尺度 计算公式 Scale Formula</td><td></td></tr><tr><td>Integral Index of Connectivity 整体连通性指数[24]</td><td>取值从0到1,其值越趋近1,连通性越好， 用来评估景观要素对整体连通性的重要 程度。</td><td>全局 IIC=</td><td>MM ai@j A²台台1+nl</td></tr><tr><td>连通单元体数量[12] Number of Components</td><td>数量越少,全局连通性越强</td><td>全局</td><td>NC = nc</td></tr><tr><td>最大连通单元体面积 Size of the Largest Component</td><td>其值越大,相互连通的斑块数量越多,全局 连通性越强</td><td>全局</td><td>SLC = max{ack}</td></tr><tr><td>斑块节点度指数[25]Node degree</td><td>表示某一斑块与其它斑块的连接能力</td><td>个体</td><td>Dgi = |Ni|</td></tr><tr><td>中间度核心性指数[26-27]</td><td>指通过某一斑要的最短路径能和，反映节点</td><td>个体</td><td></td></tr></table></body></html>

公式中,A指研究区域总面积, $n$ 指斑块数量， $\scriptstyle { \mathrm { ~ n c ~ } }$ 指连通单元体数量， $n l _ { i j }$ 指斑块 $\mathbf { \chi } _ { i }$ 和 $j$ 之间连接线数量， $a _ { i }$ 指斑块 $i$ 的可承载力（一般指表面积)， $\boldsymbol { a c } _ { k }$ 指连通单元体 $k$ 的可承载力（组成连通单元体 $k$ 的所有斑块承载力之和)， $N _ { i }$ 指接近斑块 $i$ 的所有斑块， $d _ { i j }$ 指斑块 $i$ 和斑块 $j$ 之间的距离(一般指它们之间的最小距离)， $e _ { j k } ^ { - a d }$ 指斑块j和斑块k之间流动的可能性， $\propto$ 指移动距离的阻碍系数,β指衡量承载力多少的指数， $P _ { j k }$ 指斑块j和k 之间的最短路径所通过的所有斑块[27]

# 3结果与分析

3.1 绿地空间规模的动态变化

由图2 和表2可知,近年来,郑州市域绿地空间总面积显著增加,且绿地空间的增长主要出现在北部的邙山、巩义市东南的青龙山、环翠裕景区和郑州市西南的贾鲁河发源地。2000年至 2013 年间,在一系列国家和当地绿化政策的推动下(如退耕还林、园林城市建设和森林生态城建设等),绿地面积以年均 $9 8 \mathrm { k m } ^ { 2 }$ 的速度从$9 6 3 . 9 6 \mathrm { k m } ^ { 2 }$ 增加至 $2 2 3 6 . 5 7 \mathrm { k m } ^ { 2 }$ ,且在 2009 年到 2013 年间增速最快,5 年间增加了 $8 0 6 . 9 2 \mathrm { k m } ^ { 2 }$ ,年均增加161.38$\mathrm { k m } ^ { \bar { 2 } }$ 。随着绿地斑块规模的增加,其面积所占比例逐渐增加,斑块数量所占比例也逐渐减少。其中大型绿地斑块( $\mathrm { \Phi } > 1 0 0 . 0 \mathrm { h m } ^ { 2 }$ )面积增长趋势与总绿地面积增长趋势一致,且以2009 年到2013年间增速最快,五年间增加了 $8 4 . 7 2 \%$ ;中型绿地斑块 $( 5 . 0 { - } 1 0 0 . 0 \mathrm { h m } ^ { 2 }$ )面积和数量所占比例均呈先增加后减少的变化趋势,但面积所占比例的峰值出现在 2004 年,而数量所占比例的峰值出现在 2009 年;小型绿地斑块( $< 5 . 0 \mathrm { h m } ^ { 2 }$ )面积和数量及其所占比例变化不大。

http://www.ecologica.cn

![](images/bb8b9c49b87b76b67e334fa8dc007575c8763eabc3d45f6cc3a12e412d64a18d.jpg)  
图2郑州绿地空间等级分布图  
Fig.2Green space size and distribution maps of Zhengzhou，China

Table 2The area and patch number of different size green spaces   

<html><body><table><tr><td>年份 Year</td><td>绿地 Green space</td><td><1.0 hm²</td><td>= 1.0—5.0 hm²</td><td>=5.0—10.0 hm²</td><td>=10.0—100.0 hm²</td><td>>100.0 hm²</td><td>合计 Total</td></tr><tr><td>2000</td><td>总面积/km²</td><td>35.21</td><td>99.74</td><td>54.87</td><td>125.66</td><td>648.48</td><td>963.96</td></tr><tr><td rowspan="5"></td><td>所占比例/%</td><td>3.65</td><td>10.35</td><td>5.69</td><td>13.04</td><td>67.27</td><td>100</td></tr><tr><td>斑块数量/个</td><td>7395</td><td>4478</td><td>788</td><td>565</td><td>87</td><td>13313</td></tr><tr><td>所占比例/%</td><td>55.55</td><td>33.64</td><td>5.92</td><td>4.24</td><td>0.65</td><td>100</td></tr><tr><td>总面积/km²</td><td>47.05</td><td>141.19</td><td>85.49</td><td>401.11</td><td>694.16</td><td>1369.00</td></tr><tr><td>所占比例/%</td><td>3.44</td><td>10.31</td><td>6.24</td><td>29.30</td><td>50.71</td><td>100</td></tr><tr><td></td><td>斑块数量/个</td><td>9602</td><td>6289</td><td>1225</td><td>1137</td><td>77</td><td>18330</td></tr><tr><td></td><td>所占比例/%</td><td>52.38</td><td>34.31</td><td>6.68</td><td>6.20</td><td>0.42</td><td>100</td></tr><tr><td>2009</td><td>总面积/km²</td><td>33.04</td><td>131.95</td><td>88.35</td><td>307.33</td><td>868.98</td><td>1429.65</td></tr><tr><td></td><td>所占比例/%</td><td>2.31</td><td>9.23</td><td>6.18</td><td>21.50</td><td>60.78</td><td>100</td></tr><tr><td rowspan="5">2013</td><td>斑块数量/个</td><td>6291</td><td>5733</td><td>1262</td><td>1214</td><td>160</td><td>14660</td></tr><tr><td>所占比例/%</td><td>42.91</td><td>39.11</td><td>8.61</td><td>8.28</td><td>1.09</td><td>100</td></tr><tr><td>总面积/km²</td><td>51.02</td><td>140.12</td><td>84.38</td><td>355.85</td><td>1605.20</td><td>2236.57</td></tr><tr><td>所占比例/%</td><td>2.28</td><td>6.26</td><td>3.77</td><td>15.91</td><td>71.77</td><td>100</td></tr><tr><td>斑块数量/个</td><td>10924</td><td>6212</td><td>1205</td><td>1284</td><td>428</td><td>20053</td></tr><tr><td></td><td>所占比例/%</td><td>54.48</td><td>30.98</td><td>6.01</td><td>6.40</td><td>2.13</td><td>100</td></tr></table></body></html>

# 3.2绿地空间分布特征的动态变化

由图2可以看出，大型绿地斑块多集中在距离市区较远的西部山区，小型绿地斑块则较多分布在东部城市化水平较高的郑州市区及其相邻市区内部。由景观分布指数计算结果可以看出（表3）,面积 $> 1 0 0 . 0 \mathrm { h m } ^ { 2 }$ 的绿地斑块主要分布在西部的登封市和巩义市境内,这是因为登封市和巩义市境内大多为山地和丘陵,风景名胜云集,但随着时间的变化,其分布指数有所下降,分别从2000年的2.34和2.40下降到2013年的1.77 和1.77;而中部的新密市、荣阳市和郑州市境内绿地空间分布指数逐渐增加,分别从 2000 年的1.27、0.55 和0.02增加到 2013年的1.79、0.90 和0.40;东南部的中牟县和新郑市境内绿地空间分布指数也有所增加,但增加幅度不大。说明郑州市域大型绿地斑块分布指数自西向东依次递减,大型绿地斑块逐渐从西部的登封市和巩义市向中东部的郑州市、新郑市和中某县蔓延。面积 $< 1 0 0 . 0 \mathrm { h m } ^ { 2 }$ 的中小型绿地斑块在2000 年主要分布在中西部的郑州市和新密市境内,2004 年逐渐向中南部的新郑市拓展,2009 年和2013年主要分布在东南部的中牟县和新郑市境内,随时间的推移由中西部向东南部转移,且与城市空间的主要发展方向一致,说明在郑汴新城、航空新城的建设过程中,对绿地空间的重视程度有所增加,绿地空间在随城市空间同步增长。

表3不同规模绿地空间分布指数动态变化  
Table 3Trends of green space distribution index in different districts   

<html><body><table><tr><td rowspan="2">年份 Year</td><td rowspan="2">绿地空间规模 Green space size</td><td rowspan="2">登封市</td><td rowspan="2">巩义市</td><td rowspan="2">新密市</td><td colspan="2">郑州市</td><td rowspan="2">新郑市</td><td rowspan="2">中牟县</td></tr><tr><td>荥阳市</td></tr><tr><td>2000</td><td><1.0 hm²</td><td>0.74</td><td>1.02</td><td>1.23</td><td>1.05</td><td>1.32</td><td>0.79</td><td>0.92</td></tr><tr><td rowspan="8">2004</td><td>= 1.0—5.0 hm²</td><td>0.86</td><td>0.84</td><td>1.24</td><td>0.89</td><td>1.37</td><td>0.88</td><td>0.95</td></tr><tr><td>= 5.0—10.0 hm²</td><td>1.00</td><td>0.62</td><td>1.39</td><td>0.65</td><td>1.29</td><td>1.01</td><td>1.03</td></tr><tr><td>= 10.0—100.0 hm²</td><td>1.07</td><td>0.85</td><td>1.68</td><td>0.35</td><td>1.25</td><td>0.66</td><td>1.05</td></tr><tr><td>>100.0 hm²</td><td>2.34</td><td>2.40</td><td>1.27</td><td>0.55</td><td>0.02</td><td>0.19</td><td>0.14</td></tr><tr><td><1.0 hm²</td><td>0.66</td><td>0.74</td><td>1.27</td><td>1.03</td><td>1.14</td><td>1.28</td><td>1.00</td></tr><tr><td>= 1.0—5.0 hm²</td><td>0.73</td><td>0.79</td><td>1.20</td><td>1.08</td><td>1.31</td><td>1.20</td><td>0.85</td></tr><tr><td>=5.0—10.0 hm²</td><td>0.72</td><td>0.82</td><td>1.01</td><td>1.14</td><td>1.43</td><td>1.15</td><td>0.87</td></tr><tr><td>= 10.0—100.0 hm²</td><td>0.85</td><td>1 1.41</td><td>0.98</td><td>1.36</td><td>1.11</td><td>0.65</td><td>0.76</td></tr><tr><td rowspan="4">2009</td><td>>100.0 hm²</td><td>2.19</td><td>2.48</td><td>1.52</td><td>0.54</td><td>0.00</td><td>0.23</td><td>0.00</td></tr><tr><td><1.0 hm²</td><td>0.72</td><td>0.80</td><td>1.05</td><td>0.78</td><td>1.06</td><td>1.41</td><td>1.21</td></tr><tr><td>= 1.0—5.0 hm²</td><td>0.78</td><td>0.79</td><td>1.02</td><td>0.77</td><td>0.95</td><td>1.30</td><td>1.34</td></tr><tr><td>=5.0—10.0 hm²</td><td>0.89</td><td>0.79</td><td>1.05</td><td>0.67</td><td>0.96</td><td>1.20</td><td>1.35</td></tr><tr><td rowspan="6">2013</td><td>= 10.0—100.0 hm²</td><td>0.79</td><td>0.78</td><td>1.30</td><td>0.64</td><td>0.89</td><td>1.23</td><td>1.32</td></tr><tr><td>>100.0 hm²</td><td>2.17</td><td>1.84</td><td>1.42</td><td>0.54</td><td>0.32</td><td>0.32</td><td>0.28</td></tr><tr><td><1.0 hm²</td><td>0.86</td><td>0.76</td><td>0.90</td><td>0.89</td><td>0.98</td><td>1.23</td><td>1.31</td></tr><tr><td>= 1.0-5.0 hm²</td><td>0.73</td><td>0.79</td><td>0.85</td><td>0.96</td><td>1.14</td><td>1.27</td><td>1.27</td></tr><tr><td>=5.0—10.0 hm²</td><td>0.90</td><td>0.69</td><td>0.71</td><td>1.02</td><td>1.21</td><td>1.20</td><td>1.25</td></tr><tr><td>= 10.0- -100.0hm²</td><td>1.02</td><td>0.21</td><td>1.11</td><td>1.00</td><td>0.99</td><td>1.10</td><td>0.91</td></tr><tr><td> >100.0 hm²</td><td></td><td>1.77</td><td>1.77</td><td>1.79</td><td>0.90</td><td>0.40</td><td>0.29</td><td>0.15</td></tr></table></body></html>

3.3全局水平上绿地空间连通性的动态变化

# 3.3.1图论指数的动态变化

由绿地空间全局水平上的图论指数变化(表4)可知,2000 年到 2013年,绿地空间连通单元体数量（NC)随时间的推移呈逐渐减少的变化趋势,13年间共减少了673个;除 2009 年之外,最大连通单元体面积（SLC）和整体连通性指数(IIC)均随时间的推移逐渐增加,其中最大连通单元体面积扩大了3.7倍,整体连通性指数从2000 年的 $1 . 5 2 \times 1 0 ^ { - 3 }$ 增加到2013 年的 $7 . 2 2 \times 1 0 ^ { - 3 }$ ,增加了4.7倍;说明相互连通的绿地斑块越来越多，绿地空间的连通性在增加。而且2009 年至2013年间最大连通单元体面积(SLC)和整体连通性指数(IIC)增加幅度最大,与绿地空间总量的变化趋势一致。说明郑州市域整体绿地空间连通性随着绿地空间总量和斑块规模的扩大在逐渐增加。但是其整体连通性指数仍然处于较低水平,在今后城乡绿地系统规划过程中,还应该继续加强对绿地空间的整合与连接。

Table 4Trends of graph metrics of green space in global level in Zhengzhou,China   

<html><body><table><tr><td>图论指数Graph index</td><td>2000年</td><td>2004年</td><td>2009年</td><td>2013年</td></tr><tr><td>连通单元体数量 NC</td><td>1479</td><td>1375</td><td>1123</td><td>806</td></tr><tr><td>整体连通性指数 IIC(×10-)</td><td>1.52</td><td>2.14</td><td>1.77</td><td>7.22</td></tr><tr><td>最大连通单元体面积SLC/km²</td><td>476.28</td><td>849.33</td><td>560.79</td><td>1769.86</td></tr></table></body></html>

NC：Number of Components；IIC：Integral Index of Connectivity；SLC：Size of the Largest Component

# 3.3.2 图论指数动态变化的行政区域差异性分析

不同行政区域内全局水平上绿地空间图论指数的计算结果表明(表5）,巩义市境内绿地空间的整体连通性指数最大,2013年达到 $3 2 . 1 8 \times 1 0 ^ { - 3 }$ ,其次为登封市、新密市、荥阳市、郑州市、新郑市和中牟县,呈由西向东逐渐递减的变化趋势;2000 年到2013年,随着时间的推移，每个行政区内的整体连通性指数和最大连通单元体面积都在增加,其中郑州市境内增加幅度最大,其整体连通性指数和最大连通单元体面积分别是原来的78.95和7.64倍;绿地空间连通单元体数量除中牟县增加8个以外,均呈逐渐减少的变化趋势,其中登封市境内绿地空间连通单元体数量减少最多,13年间共减少了185个；新郑市在2004 年之后取代中牟县成为最大连通单元体面积最小的区域,这主要是因为2009年之后城市空间快速大规模的向东南方向扩张,侵蚀了大量农田和绿地,降低了东部地区绿地空间的连通性。 \~

表4郑州市域绿地空间全局水平上的图论指数变化趋势  
表5不同行政区域内绿地空间全局水平上的图论指数变化趋势  

<html><body><table><tr><td rowspan="2">图论数tries</td><td rowspan="2"></td><td colspan="3"></td><td rowspan="2">2013年</td></tr><tr><td>2000年</td><td>2004年</td><td>2009年</td></tr><tr><td>郑州市</td><td>整体连通性指数IIC（×10-)</td><td>0.01</td><td>0.12</td><td>0.28</td><td>0.92</td></tr><tr><td rowspan="4">荥阳市</td><td>最大连通单元体面积SLC/km²</td><td>8.03</td><td>42.89</td><td>36.65</td><td>61.36</td></tr><tr><td>连通单元体数量NC/个</td><td>260</td><td>207</td><td>220</td><td>154</td></tr><tr><td>整体连通性指数IIC（×10-3）</td><td>0.63</td><td>1.01</td><td>0.56</td><td>3.83</td></tr><tr><td>最大连通单元体面积 SLC/km²</td><td>43.16</td><td>70.53</td><td>32.17</td><td>133.52</td></tr><tr><td rowspan="4">中牟县</td><td>连通单元体数量NC/个</td><td>211</td><td>213</td><td>151</td><td>105</td></tr><tr><td>整体连通性指数IIC(×10-3)</td><td>0.01</td><td>0.05</td><td>0.18</td><td>0.11</td></tr><tr><td>最大连通单元体面积 SLC/km²</td><td>10.8</td><td>26.17</td><td>75.39</td><td>52.31</td></tr><tr><td>连通单元体数量 NC/个</td><td>275</td><td>362</td><td>210</td><td>283</td></tr><tr><td>新郑市</td><td>整体连通性指数 IIC（×10-3)</td><td>0.06</td><td>0.21</td><td>0.30</td><td>0.49</td></tr><tr><td></td><td>最大连通单元体面积 SLC/km²</td><td>14.6</td><td>26.81</td><td>24.2</td><td>31.38</td></tr><tr><td></td><td>连通单元体数量 NC/个</td><td>216</td><td>230</td><td>196</td><td>187</td></tr><tr><td>新密市</td><td>整体连通性指数 IIC（×10-）</td><td>1.59</td><td>3.78</td><td>2.89</td><td>19.54</td></tr><tr><td></td><td>最大连通单元体面积SLC/km²</td><td>80.84</td><td>210.37</td><td>144.69</td><td>452.71</td></tr><tr><td></td><td>连通单元体数量 NC</td><td>152</td><td>148</td><td>123</td><td>23</td></tr><tr><td>巩义市</td><td>整体连通性指数 IIC（×10-)</td><td>11.39</td><td>15.86</td><td>11.81</td><td>32.18</td></tr><tr><td rowspan="4">登封市</td><td>最大连通单元体面积SLC/km²</td><td>213.42</td><td>291.86</td><td>234.09</td><td>457.56</td></tr><tr><td>连通单元体数量NC/个</td><td>179</td><td>116</td><td>148</td><td>79</td></tr><tr><td>整体连通性指数IIC（×10-)</td><td>4.45</td><td>4.91</td><td>7.15</td><td>20.72</td></tr><tr><td>最大连通单元体面积SLC/km²</td><td>152.92</td><td>152.55</td><td>177.47</td><td>541.45</td></tr><tr><td></td><td>连通单元体数量NC/个</td><td>211</td><td>167</td><td>143</td><td>26</td></tr></table></body></html>

# 3.3.3 图论指数与斑块规模相关性分析

全局水平上绿地空间的图论指数与不同等级绿地斑块面积的相关性分析结果表明(表6),整体连通性指数和最大连通单元体面积分别与绿地空间总量和大型绿地斑块 $\mathrm { \Phi } > 1 0 0 . 0 \mathrm { h m } ^ { 2 }$ )总面积呈显著或极显著正相关关系；而连通单元体数量与绿地空间总量和大型绿地斑块( $\mathrm { \Phi } > 1 0 0 . 0 \mathrm { h m } ^ { 2 }$ )总面积呈显著负相关关系;且绿地斑块规模越大,与图论指数相关性越高。说明绿地空间总量越大,连通性越强,大型绿地斑块不仅决定了绿地空间的总体变化趋势,也对整体绿地空间连接度起到决定性的作用。因此,在今后城乡绿地系统规划过程中，方面要重视对大型绿地斑块的拓展与保护,另一方面要加强中小型绿地斑块之间、中小型绿地斑块与大型绿地斑块之间的连通性,从而提高全局水平上绿地空间物质能量的流通能力,增强绿地空间的生态功能。

表6绿地空间连通性指数与绿地空间规模的相关性分析   

<html><body><table><tr><td>图论指数 Graph metrics</td><td>绿地空间总量 Green space area</td><td><1.0hm² 的斑块总面积</td><td>= 1.0—5.0hm² 的斑块总面积</td><td>=5.0—10.0hm² 的斑块总面积</td><td>= 10.0—100.0hm² 的斑块总面积</td><td>>100.0hm² 的斑块总面积</td></tr><tr><td>整体连通性指数IIC</td><td>0.95 *</td><td>0.19</td><td>0.35</td><td>0.55</td><td>0.56</td><td>0.96**</td></tr><tr><td>最大连通单元体面积SLC</td><td>0.95 *</td><td>0.20</td><td>0.42</td><td>0.62</td><td>0.67</td><td>0.92 *</td></tr><tr><td>连通单元体数量NC</td><td>-0.95 *</td><td>0.07</td><td>-0.41</td><td>-0.75</td><td>-0.66</td><td>-0.92 *</td></tr></table></body></html>

\*\*在.01水平(双侧)上显著相关；\*在0.05水平(双侧)上显著相关

3.4个体斑块水平上(Locallevel)绿地斑块连通性的动态变化

个体斑块水平上,绿地斑块的节点度指数和中间度核心性指数的动态变化(图3—5)不仅反映了每一个绿地斑块连通性的动态变化过程,还能够表明每个斑块对整体绿地空间连通性的重要性和媒介作用的强度，对未来城乡绿地系统规划具有重要意义。

# 3.4.1 绿地斑块节点度指数( $\mathrm { D g } { \dot { } }$ )动态变化

由图3可知,2000 年至2013年,高节点度指数的绿地斑块显著增多,并呈由西向东逐渐扩散的趋势;节点度指数大于25的绿地斑块数量增加了2倍,由 2000年的6个增加到 2013年的12个;2003年郑州市森林生态城规划中的西北森林组团(图3中A处)和西南森林组团(图3中B处)的绿地斑块节点度指数逐渐增加,并成为对整体绿地空间连通性非常重要的关键区域;西部的嵩山风景名胜区和南部的具茨山森林公园一直是郑州市域节点度指数较高的绿地斑块,其斑块规模的稳定性对整体绿地空间连通性至关重要,其中嵩山风景名胜区是郑州市域内节点度指数最大的斑块,且从2000 年到 2013年,其节点度指数由135增加到 280,增加了1.07倍;通过相关性分析发现,绿地斑块节点度指数与绿地斑块面积呈正相关关系（图4),说明绿地斑块规模越大,其节点度指数越高,与周边其它斑块的连通性越强,对整体绿地空间连通性贡献越大。

# 3.4.2绿地斑块中间度核心性指数(BC)动态变化

由图3和5可知,具有最大中间度核心性指数的绿地斑块均出现在具有高节点度指数的绿地斑块周边,是维持两个斑块之间连通的关键,且随着其自身和相邻斑块规模和数量的变化而出现或消失。如图5中 A处的绿地斑块在 2000 年和2004年中间度核心性指数最大,但是 2004 年之后,随着A斑块及其周边斑块规模的扩大和数量的增多,到2009 年其核心性消失,并与相邻斑块融为一体,说明A斑块在 2000 年到 2004年是维持相邻两个斑块相互连通的关键性斑块,也称为"脚踏石"斑块。B和C 处则是由于其相邻斑块规模的缩小而成为 2009 年中间度核心性指数最大的绿地斑块,2009 年到2013 年间又随着其相邻斑块规模和数量的扩大而消失。D和E斑块则由于其相邻斑块规模的进一步扩大和高节点度斑块数量的增多,而成为 2013 年中间度核心性指数最大的斑块,也是今后绿地系统规划过程中应重点考虑保护和拓展的绿地斑块。

# 4讨论

# 4.1郑州市域绿地空间连通性动态变化及原因

2000 年至2013年为郑州快速城镇化的中期阶段,虽然城市空间急速扩张和人口数量的急剧增加给绿地空间的发展带来了极大的威胁,但是根据本文量化结果显示,郑州市域范围内的绿地空间总量在逐渐增加,绿地空间的连通性也逐渐增强。究其原因,国家和当地政府颁布和实施的绿化政策和相关规划是重要的外界推力[21],例如:1999 年国家颁布的"退耕还林"政策和 2000 年创建国家园林城市的绿化政策遏制了绿地空间的大规模衰减,并出现恢复性增加,这些措施的实施对促进郑州市域绿地空间总量的增长具有重要的影响;2003年郑州市政府实施的绿地系统规划和森林生态城规划则决定了绿地空间增长的主要位置,如嵩山贾鲁河绿脉、沿黄河绿带和西北、西南、东北和东南森林组团等;2009 年中国第二届绿化博览会在郑州举行,更是进一步推动了郑州市域绿地空间的快速发展。另外,早期绿地系统规划过程中“重指标、轻结构”的做法,致使绿地空间破碎化严重,连通性较低,直至2011年郑州都市区郊野森林公园体系规划中引入绿道网络规划和2012 年郑州市“两环三十一放射"绿色生态廊道的建设,才逐步改善和提高了绿地空间的连通性。因此,政府决策的支持与推动对未来绿地空间的健康可持续发展至关重要。

![](images/4a16d93c4d004e34e3096eda26341d8f24ff3c783d4c95d27ceb79b31c21f7bf.jpg)  
图3市域绿地斑块的节点度指数动态变化  
Fig.3Dynamic changes of node degree of green patches in Zhengzhou in China

绿地空间总面积和大型绿地斑块总面积与全局水平上绿地空间的整体连通性呈正相关关系，且绿地斑块规模越大,相关性越强(表6);绿地斑块规模还与个体斑块水平上绿地斑块的节点度指数呈正相关关系（图4);绿地空间连通性的区域差异特征与绿地空间分布特征一致,均呈现西高东低的分布规律,且随时间变化呈现出由西向东扩展的趋势(表3和表5)。个体斑块水平上具有最大中间度核心性指数的绿地斑块随绿地斑块规模和节点度指数的变化而变化,且往往分布在具有最大节点度指数的绿地斑块周边,是维护斑块之间连通的关键性斑块,也是未来绿地系统规划过程中需要重点关注和优化的位置（图3和图5)。因此,绿地空间总量、绿地斑块规模和和具有高中间度核心性指数的斑块优化决定了绿地空间的整体连通性,是影响绿地空间连通性动态变化的内在要素。

![](images/05c65420737ff2cbd36d45d311904d62e27f3c9961182e79245c6520347d06a4.jpg)  
图4绿地斑块面积与其节点度指数的相关性分析  
Fig.4The linear regression analysis between patch area and node degree

# 4.2基于图论的绿地空间连通性诊断

绿地空间连通性的诊断对绿地生态服务功能的评价、生物多样性保护和绿地系统的科学合理规划均有重要的意义。以往对绿地空间连通性的诊断大多是基于景观生态学理论和GIS 空间分析法,侧重于从整体上计算和评价一定范围内的景观连接度或一定距离内的景观连通性,研究尺度较宏观,缺乏整体景观结构与局部斑块特征之间的关联性研究和变化过程的研究,难以更精确的指导绿地系统的规划、建设和绿地空间结构的优化。本研究则引入图论算法,分别从全局与斑块两个水平上来分析绿地空间连通性的动态变化过程,及其与斑块自身形态分布特征的关系,并根据图论指数的变化诊断了绿地空间连通性发生变化的具体位置和原因,对指导未来科学合理的城乡绿地资源建设与管控具有重要意义。而且基于图论和Graphab 软件的计算方法具有快速、便捷 准确定位和可视化强等特点,能够简化多种尺度上的景观结构,在未来景观连通性的诊断与优化上具有重要的实践价值。如通过对绿地斑块节点度指数的诊断,能够识别对整体绿地空间连通性具有重要作用的斑块(图3);通过对绿地斑块中间度核心性指数的诊断,能够发现绿地空间连通性易受影响和降低的部位,以及对整体绿地空间连通性起关键和脚踏石作用的斑块(图5）,预测下一步绿地系统规划和建设过程中需重点优化的地方。

# 4.3基于图论的绿地空间连通性优化措施

# 4.3.1高节点度斑块的保护和发展

高节点度斑块就是与其它斑块连通性最好的斑块,对一定范围内整体绿地空间连通性具有重要的统筹作用,假如该类斑块遭到破坏,该区域范围内绿地空间的整体连通性必然遭到重大破坏。由图4可知,绿地斑块的节点度指数与绿地斑块的规模呈正相关关系。因此,在今后绿地系统规划过程中，应该重点保护和发展该类具有高节点度指数的大型绿地斑块,进一步加强其连通强度和辐射范围。

![](images/e5b46caf71f08c6f4b6f3c8452a1b80c1a29c6941f2ab9ffddcc43b427eb3319.jpg)  
图52000 年一2013年市域绿地斑块的中间度核心性指数(BC)动态变化

# 4.3.2 高中间度核心性斑块规模的拓展

具有高中间度核心性指数的斑块规模较小，但位置却极其重要,是相邻高节点度斑块相连通的唯一媒介，亦称“脚踏石”斑块。中间度核心性指数越大，说明该绿地斑块在整个绿地空间网络中的踏脚石和媒介作用越重要,所承载的流通效率越强,对维持整体绿地空间连通性的作用越重要[28]。其出现和消失过程如图6所示,从连通体a到b:随着连通单元体a中E、F和A斑块规模的扩大,A斑块和E、F斑块逐渐融为一体,A斑块的"脚踏石"作用消失,进而由于连通单元体a和G斑块规模的扩大,B斑块成为连接连通单元体a和G斑块的核心性斑块;从连通体b到a:由于绿地斑块规模减小,B斑块的“脚踏石”作用消失,A斑块的“脚踏石”作用再现。因此,在未来绿地系统规划过程中,应该优先找出该类关键性斑块,拓展其规模,进而有效提高绿地空间的整体连通性。

![](images/bc6a51fffcd48feac9232516773eb83a15b178b8b09387e37b198bd33c029eef.jpg)  
Fig.5Dynamic changes of Betweenness Centrality of green patches in Zhengzhou，China   
图6新旧核心性斑块产生与消失过程示意图Fig.6Process of new key-stone green patch produce（left toright）and old key-stone green patch disappear（right to left）

# 5结论

本文基于多时相的Landsat遥感影像数据,利用遥感软件和技术提取了四个时期的郑州市域绿地空间数量化信息,分析了过去13年间快速城镇化过程中,绿地空间总量和斑块规模逐渐增加并由西向东蔓延的动态变化规律;结合图论原理和Graphab 1.2.1软件,计算和分析了郑州市域绿地空间连通性随绿地空间总量和斑块规模的变化而变化的过程。结果表明：绿地空间连通性的区域差异特征与绿地空间的分布特征具有一致性;绿地斑块规模与绿地空间的整体连通性指数、最大连通单元体规模和绿地斑块的节点度指数呈显著正相关关系;绿地斑块节点度指数和中间度核心性指数的大小反映了该斑块对整体绿地空间连通性的重要程度。揭示了政府决策和规划是绿地空间连通性发生变化的外在动力;绿地空间总量、斑块规模和位置的重要性是影响绿地空间连通性发生变化的内在要素。

通过对图论算法和Graphab 软件的应用,本研究诊断和展示了对郑州市域整体绿地空间连通性具有重要作用的稳定型斑块和核心性斑块的变化过程,并提出在未来绿地系统规划中保护和拓展高节点度、高核心性斑块是下一步绿地空间结构调整与优化的重点。

# 参考文献（References）：

[1］冯娴慧.城市绿地与风的环境效应研究.中国园林，2010，26(2)：82-85.  
［2］郑祚芳，轩春怡，高华.影响北京城市生态环境的气候指数变化趋势.生态环境学报，2012,21（11)：1841-1846.  
[3]PeschadtKK，tigdorUKsociatostwearkaracterstidpercevedestorativeessofsallpublcbaesceLandscape and Urban Planning，2013,112：26-39.  
[4]PeschrdtKK,SchipperijJ,tigsdoterUK.Useofsmallpublicurbangrenspaces（SUGS).UrbanForestry&UrbanGring，2,1(3):235-244.  
[5]SaphorsJD,LiWstimatigeueofubagears：adoprgalyisfthinglefilyousigmarketinosgeles，A.Landscape and Urban Planning，2012，104(3/4）:373-387.  
[6] 毛齐正，罗上华，马克明，郭建国，唐荣莉，张育新，宝乐，张田.城市绿地生态评价研究进展.生态学报，2012，32(17)：5589-5600.  
[7] 李想，李闯，王凤友，王诗阳，王雪.大连中心城区绿地系统生态服务价值时空分异特征研究.地理科学，2014，34（3)：302-308.  
[8] 王铭子.基于连接度的城市绿地生态网络研究[D].北京：北京林业大学，2010.  
[9] LiuSL,DongYH,Deng,LiuQ,ZhaoHD,DongSK.Forestfragentationdlandscapeoivityhngeaoaedithodetwokextension and city expansion:a case study in the Lancang River Valley.Ecological Indicators，2O14,36:160-168.  
[10] ParkS.Spatialetofaaollctiitunentotalotdsset,187: 425.  
[11] RabinowitzA,ZelrKangeidodelfldsaecoetivindoseatiofortejgar，PanteraocaologicalCoseatio,2010，143(4):939-945.  
[12] Urban D，Keitt T.Landscape connectivity:a graph-theoretic perspective. Ecology，2001,82(5）:1205-1218.  
[13] MinorE,Urbanaofraekfeaatingldapiiseatioaoeatioo,2(2):297-307.  
[14]FolteteJC，GrardetX，luzelCAmethodoogicalframeworkforeuseoflandscapeaphsinland-useplaing.LandscapeandUrbanPlanning，2014，124：140-150.  
[15] 王丽丽.图论的历史发展研究[D].济南：山东大学，2012.  
[16] 方富贵.图论的算法和应用研究.计算机与数字工程，2012，40(2)：115-117，132-132.  
[17] BunAG,UrbanD，KeitTandscapecocti：coservationlicationofaphtoyJoualofEviroentalaagnt,2000,59(4):265-278.  
[18] HeckanT,hagartWilacentelopntsfislcatioioolgomolg130-146.  
[19]MinorEbialliulaelsoalas(6):1771-1782.  
[20] 许文雯，孙翔，朱晓东，宗跃光，李杨帆.基于生态网络分析的南京主城区重要生态斑块识别.生态学报，2012，32(4)：1264-1272.  
[21] MuB,MayerAL,HeRZ,TianGHLndusedyamicsandpolicyimpicationsinCentralChina;acasestudyofZhengzou.Cies,65839-49.  
[22] 喻红，曾辉，江子瀛.快速城市化地区景观组分在地形梯度上的分布特征研究.地理科学，2001,21（1)：64-69.  
[23] 侯明行，刘红玉，张华兵，王聪，谭清梅.地形因子对盐城滨海湿地景观分布与演变的影响.生态学报，2013,33（12)：3765-3773.  
[24] Pascual-HortalL，SauraSomparsonandevelopntofapasedlandscapecoectividices：owadstheprorzatioofbiatpatches and corridors for conservation.Landscape Ecology，2006,21(7）：959-967.  
[25]Freeman L C.Centrality in social networks conceptual clarification.Social Networks,1979,1(3）：215-239.  
[26]BodinOauraankingdiiualbiatatcssoetivitroviders：ntegratingtwokalsndatchovalts.Ecological Modelling，2010,221（19）：2393-2405.  
[27]Folteteeelodelosetael38: 316-327.  
［28］吴未，张敏，许丽萍，欧名豪.基于不同网络构建方法的生境网络优化研究一 一以苏锡常地区白鹭为例.生态学报，2016,36（3)：844-853.