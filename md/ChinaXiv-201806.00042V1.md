# 黑河径流对LUCC和气候变化的敏感性分析

罗开盛1,²，陶福禄2.3（1．南京信息工程大学遥感与测绘工程学院,江苏 南京210044;2．中国科学院地理科学与资源研究所陆地表层格局与模拟院重点实验室,北京100101;3．中国科学院大学,北京100049)

摘要：为了定量评估径流对土地利用变化(LUCC)和气候变化的敏感性及其时空变异,基于土地利用、土壤、数字高程(DEM）、气象和实测径流数据,借助 SWAT模型并结合统计方法定量评估了黑河径流对LUCC 和气候变化的敏感性。结果表明：1980—2009 年流域径流对LUCC 的敏感性值为 $0 . 0 2 0 \ \mathrm { m m } \cdot \mathrm { k m } ^ { - 2 }$ 。径流对LUCC 的敏感性从大到小分别是上游 $( 0 . 1 0 8 \ \mathrm { m m } \cdot \mathrm { k m } ^ { - 2 }$ ）、中游 $\left( 0 . 0 0 4 \ \mathrm { m m } \cdot \mathrm { k m } ^ { - 2 } \right.$ )和下游 $( 0 . 0 0 1 \ \mathrm { m m } \cdot \mathrm { k m } ^ { - 2 }$ ）。 $1 \ \mathrm { m m }$ 降雨变化在上游、中游和下游引起的产水量变化分别是 $0 . 4 9 \sim 0 . 2 8 8 ~ \mathrm { m m } _ { \setminus } 0 . 0 0 6 \sim 0 . 0 3 8 ~ \mathrm { m m }$ 和 $0 \sim 0 . 0 0 2 ~ \mathrm { m m }$ 。 $1 \ \mathrm { { ^ { c } } }$ 气温变化在上游、中游和下游引起的产水量变化分别是 $1 3 . 4 1 3 \sim 7 8 . 9 0 2 ~ \mathrm { m m } _ { \cdot } 1 . 1 0 5 \sim 6 . 5 0 0 ~ \mathrm { m m }$ 和 $0 . 4 6 1 \sim 2 . 7 1 0 \ \mathrm { m m }$ 。径流对气温的敏感程度要远远高于对降水的敏感度。在时间趋势上,径流对 LUCC 的敏感性表现出下降趋势;上游表现出减少趋势,而下游表现出增加趋势。流域径流对气温的敏感性表现为上升趋势。

关键词：径流；气候变化；LUCC；敏感性；SWAT模型；黑河

土地利用变化(LUCC)可以通过改变能量平衡的方式间接影响流域水循环；也可以通过改变植物截留、蒸散发、下渗、地下水补给、基流和地表径流等水文要素的方式直接影响流域水循环[1]。气候变化对降水、蒸发、径流、土壤湿度等造成直接影响，进而导致水资源总量及其时空格局的改变[2]。因此,LUCC和气候变化对水循环过程和水资源的影响的研究一直受到广泛关注。在流域尺度上，气候及LUCC相互作用对水文过程的影响会直接导致水资源供需关系的变化，进而对流域生态、环境以及经济发展等多方面产生影响[1-2]。LUCC 和气候变化已经成为影响流域水文水资源的重要因素。

SWAT模型是基于物理机制的水文模型，由于其较为完善的模型结果和分布式模拟方式，在世界各地得到了广泛应用，其已经成为我国进行水文模拟的有效工具[3]。SWAT模型在长江[4]、黄河[5]、海河[6渭河[7] 滦河流域[8]等湿润半湿润区域得到较好的结果。同时成功应用到干旱半干旱的叶尔羌河流域[9]、玛纳斯河流域（10]、石羊河流域(]等。但总的来说，应用到干旱与半干旱的研究相对少些。

这可能和模型的结构有关，SWAT模型将现实中可能存在的沿子流域边界剖面的二维水分联系，概化为通过河道的一维联系[5-7]，所以有研究认为SWAT模型在干旱区的某些地区不太适用，需要改进地下水模块。例如,程磊等[12]发现SWAT模型不能很好地模拟壤中流和基流，但是这种简化在河道输水量占主导的山区影响不大。有学者已成功将SWAT模型应用于黑河上中游区域,例如, ${ { \mathbb { W } } _ { \mathbf { u } } }$ 等[13]构建了黑河中上游SWAT模型，评估了未来气候和土地利用变化对水文的影响。在这一地区，水分过程主要为降水、凝结水入渗、蒸发、人工取水-灌溉等，以垂向水分运动为主，横向水力联系较少见。因此，在以垂向水分运动为主导的黑河下游地区，SWAT模型能较好地模拟蒸发，从而实现对水量平衡的近似表达。也正因为如此,Zang 等[14-15]已经成功将SWAT模型应用到整个黑河流域并取得了良好的模拟结果。

水是黑河流域环境变化的关键因素，但是上中下游受气候变化和人类活动的影响强度存在差异。研究表明气候变化和LUCC是影响流域的两大主要因素；不少学者定量研究了流域径流对气候变化和LUCC 的响应[16]。但是流域径流对哪个因素更加敏感？是气候变化还是LUCC？在上中下游存在何种差异？在时间上存在何种变异或者趋势？这些我们并不是很清楚。而回答这些问题需要探究黑河流域径流对LUCC和气候变化的敏感性。为此，本文利用DEM、土壤、土地利用和气象数据驱动SWAT模型，通过实测径流数据对模型进行率定，借助SWAT模型并结合统计方法，定量评估了黑河流域径流对LUCC和气候变化的敏感性并揭示其时空变异。

# 1 研究区概况

黑河流域是中国第二大内陆河流域 $( 3 8 ^ { \circ } \sim 4 2 ^ { \circ }$ $\mathrm { N } , 9 8 ^ { \circ } \sim 1 0 1 ^ { \circ } \mathrm { E }$ ）（图1）。面积大约 $1 4 . 3 1 \times 1 0 ^ { 5 } ~ \mathrm { k m } ^ { 2 }$ ，年均径流量 $3 4 . 4 3 \times 1 0 ^ { 8 } \ \mathrm { m } ^ { 3 }$ 。流域地势南高北低,海拔 $8 7 9 \sim 5 ~ 5 7 3 ~ \mathrm { m }$ 。莺落峡和正义峡水文站分别是上游和中游的水文控制站。上游年均降水量大约300$\mathbf { m } \mathbf { m }$ ,年均气温在 $- 2 . 9 \sim 1 . 5 \mathrm { ~ \textdegree C }$ ；中游年均降水量50$\sim 2 0 0 \ \mathrm { m m }$ ,年均气温 $7 . 2 \sim 9 . 6 ~ \mathrm { ^ { \circ } C }$ ,年均蒸发为2$0 0 0 \sim 3 ~ 0 0 0 ~ \mathrm { m m }$ 。下游年均降水量 $4 0 \sim 5 0 ~ \mathrm { m m }$ ,年均气温为 $1 0 . 3 2 \mathrm { ~ } \mathrm { ~ } ^ { \circ } \mathrm { ~ C ~ }$ ，年均蒸发量达到 $2 \ 3 0 0 \sim 3 \ 8 0 0$ mm(17]

96°E 98°E 100°E 102°E 104°E东居延海N 吉诃德A 马鬃山 ·额济纳旗 2。狼心山梧桐沟0玉门镇 金塔 新嘉峪关海拔/m 新地5573 酒泉 肃南高阿善右旗 N.68托勒 野牛沟 山丹 民勤879 。河流 扎马什克祁连. 气象站 060120180240km水文站

# 2 数据与方法

# 2.1 数据收集与预处理

土地利用数据利用中国科学院环境数据中心(http://www.resdc.cn/）的 $1 : 1 0 0 \ 0 0 0$ 遥感监测数据。时间分别是20世纪80年代末期、1995年、2005年、2010年5期，20世纪80年代末期、1995年的土地利用数据分别代表1980s和1990s的土地利用状况。2005年的土地利用于初步模型的输入数据。

1980—2016年的气象数据来自中国气象数据共享中心（http://cdc.cma.gov.cn/）和寒区与旱区科学数据中心（http://westdc.westgis.ac.cn/）。气象站点分别是祁连、吉诃德、梧桐沟、鼎新、金塔、酒泉、高台、托勒、野牛沟、张掖、山丹和额济纳旗。同时利用了邻近阿拉善旗、民勤、马鬃山和玉门镇等气象站的数据进行补充。利用12个气象站点的气象要素日值构建天气发生器以插补缺失的气象数据。

土壤数据利用联合国粮农组织的世界和谐数据库（Harmonized World Soil Database,简称HWSD）的HWSDV1.1版本。SWAT所需的大部分物理参数可通过HWSD自带的属性表中查询获得。但是土壤饱和容重（SOL_BD）、土壤层有效水量（SOL_AWC）、土壤饱和水力传导度（SOL_K）、土壤侵蚀力因子（USLE_K)等参数需要计算获得。SOL_BD、SOL_AWC、SOL_K等3个参数值通过SPAW（SoilPlantAtmosphere Water）的 SWCT（Soil -Water -Characteristics）模块计算获得。USLE_K通过美国通用方程(USLE)计算获得。

数字高程(DEM)数据下载于NASA数据网站上（http://wist.echo.nasa.gov/api）的 ASTER GlobalDEM（简称ASTERGDEM）。预处理包括投影转换和"填洼”处理。

河道年和月的实测径流数据用于模型的率定，数据来自于黑河流域管理局以及黑河流域水文年鉴。率定的水文站点包括上游的扎马什克、上游水文控制站一莺落峡、中游水文控制站一正义峡

# 2.2 水文过程模拟

2.2.1 SWAT模型的构建和率定 2005 年的土地利用数据用于模型初始的构建，将处理好的其他数据输入模型中构建SWAT模型。利用SWAT-CUP2012中的SUFI-2算法进行模型的校准。利用决定系数 $( R ^ { 2 } )$ 和纳西系数(NS)来衡量模型模拟结果[5]。决定系数衡量模拟值和实测值的拟合效果,范围为 $0 \sim 1$ ,值越大表示模拟效果越好(6。一般NS 值大于0.45模拟结果可以接受(5-6) 。

# 2.3敏感性分析方法

2.3.1影响量分离方法通过9个情景来定量分离黑河流域过去30a(1980—2009年)LUCC和气候对径流的影响量。M1、M2和 $\mathbf { m } ^ { 3 }$ 用来定量分离

1980s的LUCC和气候变化单独引起的径流变化量。M4、M5和M6用来定量区分1990s的LUCC和气候变化单独引起的径流变化量（表1）。M7、M8和 M9用来计算2000s的LUCC和气候变化单独引起的径流变化量(表2）。径流总体变化利用产水量的变化来表征。每个年代中LUCC和气候变化引起的径流变化分上游、中游和下游分别进行定量区分。以1980s的LUCC和气候变化对径流变化的贡献为例。M1是1980s的土地利用和1980s的气候,M2是1980s的土地利用和1990s的气候,产水量的变化Y2－Y1 是由气候变化所引起的变化量。 $\mathbf { m } ^ { 3 }$ 是1990s土地利用和1980s的气候,那么Y3-Y1就是LUCC所引起的变化量。同理，M4是1990s的土地利用和气候，Y4-Y1则为1980s径流变化受到各种因素影响的综合变化量。（Y4-Y1）-（Y2－Y1）-（Y3-Y1)是其他因素对径流变化的影响量，称为残差。2000s的LUCC和气候变化单独引起的径流变化量通过M7、M8、M9计算获得。把2000—2016年分成2000—2008 年和2009—2016年2个时段来近似获得2000s的LUCC和气候变化单独引起的径流变化量。

2.3.2敏感性计算方法本研究利用产水量表征径流。为了反映径流随着LUCC和气候的微小变化

# 表1评估LUCC 和气候变化在1980s 和1990s贡献率的控制实验情景

Tab.1A list of the different modeling experiments to evaluate the impactsofLUCCandclimate in 1980s and1990s   

<html><body><table><tr><td>实验情景</td><td>土地利用数据</td><td>气候数据</td></tr><tr><td>M1</td><td>1980s</td><td>1980s</td></tr><tr><td>M2</td><td>1980s</td><td>1990s</td></tr><tr><td>m</td><td>1990s</td><td>1980s</td></tr><tr><td>M4</td><td>1990s</td><td>1990s</td></tr><tr><td>M5</td><td>1990s</td><td>2000s</td></tr><tr><td>M6</td><td>2000s</td><td>1990s</td></tr></table></body></html>

# 表2分离2000s的LUCC和气候变化贡献率的控制实验情景

Tab.2A list of the different modeling experiments to evaluate the impacts of LUCC and climate in 2000s   

<html><body><table><tr><td>实验</td><td>土地利用数据</td><td>气候数据</td></tr><tr><td>M7</td><td>2005</td><td>2000-2008</td></tr><tr><td>M8</td><td>2005</td><td>2009-2016</td></tr><tr><td>M9</td><td>2010</td><td>2000-2008</td></tr></table></body></html>

而变化的影响程度，利用产水量对LUCC和气候变化的敏感性值来评估径流对二者的敏感性。模型输出的产水量函数 $Y$ 受到土地利用 $L$ ，气候 $C$ 以及其他因素 $Q _ { i }$ 的影响。

$$
Y = F ( L , C , O _ { 1 } , O _ { 2 } , \cdots , O _ { i } )
$$

LUCC的敏感性用数学方程可表示为：

$$
S _ { L } = \frac { \varDelta Y } { \varDelta L }
$$

式中： $S _ { L }$ 是径流对LUCC 的敏感性值； $\varDelta Y$ 是产水量的变化量； $\varDelta L$ 是对应时间段内土地利用（LUCC）的变化量。通过比较不同情境产水量和土地利用的变化量，可得到对应时间内径流对LUCC的敏感性。

径流对气候变化的敏感性用数学方程可表示为：

$$
S _ { C } = { \frac { \varDelta Y } { \varDelta C } }
$$

式中： $S _ { C }$ 是径流对气候变化的敏感性值； $\varDelta Y$ 是产水量的变化量； $\Delta C$ 是对应时间段内气象要素的变化量。由于气象要素的量纲不同，而且不知道影响量的累加权重，因此无法准确获得径流对整个气候变化的敏感性值。虽然气象包括气温、降水、风速、相对湿度、日照时间和气压等6个要素，但径流过程主要受到气温和降水的影响。因此只需要估算径流对气温和降水的敏感性。气温和降水具体的敏感性值不能获得,但是可以获得敏感性的取值范围[ $S _ { \mathrm { m i n } }$ ，$S _ { \mathrm { m a x } }$ ]，假设 $\varDelta Y$ 是气候变化引起的综合变化量。如果气象6要素同等重要，权重为1/6，然而气温和降雨是主要因子，二者权重要大于 $1 / 6$ ;那么气温或者降水在综合变化量的权重在(1/6，1)之间，以降水为例，降水敏感性的最大值和最小值可表示为：

$$
S _ { \mathrm { m i n } } = \frac { \Delta Y } { 6 \Delta P }
$$

$$
S _ { \mathrm { m a x } } = { \frac { \Delta Y } { \Delta P } }
$$

式中： $S _ { \mathrm { m i n } }$ 和 $S _ { \mathrm { m a x } }$ 分别是降水敏感性的最小值和最大值； $\varDelta Y$ 是产水量的变化量； $\varDelta P$ 是对应时间段内降水的变化量。利用相同的方法可以求出气温敏感性的最大值、最小值和取值范围。如果降水与气温的敏感性最小值都大于LUCC 敏感性值，则说明径流对气候变化更加敏感。

# 3结果与讨论

# 3.1 土地利用和气候变化

流域上游、中游和下游在1980s气温最低，1990s上升，2000s最高，气温有明显的升高趋势。在1980s和1990s，上游气温的变化量都最大，分别升高了 $1 . 4 6 ~ \mathrm { ^ { \circ } C }$ 和 $1 . 3 7 \mathrm { ~ \textdegree C }$ ;在1980s,中游气温的变化量小于下游，但是在1990s中游气温的变化量稍微大于下游，差别不大。 $2 0 0 0 \mathrm { s }$ 气温最低的是上游区域,为 $- 1 . 9 9 \mathrm { ~ } ^ { \circ } \mathrm { C }$ （表3）。

Tab.3Mean temperature in each decade in the Heihe Riverbasin during 1980—2009 /9   

<html><body><table><tr><td>1980s</td><td>1990s</td><td>2000s</td></tr><tr><td>流域</td><td>4.84 5.41</td><td>5.89</td></tr><tr><td>上游</td><td>-5.18 -3.72</td><td>-1.99</td></tr><tr><td>中游</td><td>7.49 8.06</td><td>8.50</td></tr><tr><td>下游</td><td>8.72 9.47</td><td>9.9</td></tr></table></body></html>

表31980—2009年黑河流域各年代平均气温  

<html><body><table><tr><td></td><td>1980s</td><td>1990s</td><td>2000s</td></tr><tr><td>流域</td><td>1 833.29</td><td>1 804.34</td><td>1 946.21</td></tr><tr><td>上游</td><td>3 923.47</td><td>3 656.27</td><td>4 004.87</td></tr><tr><td>中游</td><td>1 178.52</td><td>1 211.86</td><td>1 269.77</td></tr><tr><td>下游</td><td>334.6</td><td>507.65</td><td>428.59</td></tr></table></body></html>

# 表41980一2009年黑河流域各年代降水量

如表4所示，上游降水量在各年代都是最高。上游和中游在2000s的降水量最多，下游地区的降水量在1990s最多。1980s 降水量变化最大的是下游区域，增加了 $1 7 3 \ \mathrm { m m }$ 。1990s降水量变化最大的区域是上游区域，增加了 $3 4 8 . 6 \ \mathrm { m m }$ 。2000s中游降水量最多，为 $4 ~ 0 0 4 . 8 7 ~ \mathrm { { m m } }$ 。

# 3.2 土地利用变化

上游1980s变化最大的是草地和城乡-工矿-居民用地，1990s变化最大的是水体和草地，2000s变化最大的是未利用土地和耕地。林地总体上有所下降。耕地和草地有增有减。中游人工表面一直保持持续增长的趋势。耕地在1980—2010 年间变化面积最大，且为扩大趋势。中游耕地和城乡－工矿-居民用地在1980—2010 年变化速率最大，且为持续增长。未利用土地在1980—2010年一直在减小。草地总体呈现减少趋势。耕地总体上在扩张。下游林地、草地和未利用土地在1980—2010年表现为减少,而耕地、城乡-工矿-居民用地总体上在扩大。就整个流域而言，城乡-工矿-居民用地在过去30多年(1980—2009 年)不断扩大;耕地从1990s开始迅速扩大;草地、水体和未利用土地有增有减

# 3.3校准和验证结果

采用 $N S$ 系数、 $\cdot ^ { R ^ { 2 } }$ 评估模型的性能。在年尺度上，莺落峡水文站在校准期和验证期的NS系数分别是0.84和 $0 . 7 9 { ; R } ^ { 2 }$ 分别是0.96和0.93。正义峡水文站在校准期和验证期的NS系数分别是0.67

Tab.4Annual precipitation in each decade in the Heihe River basin during 1980—2009 /mm   
表5黑河流域土地利用变化  
Tab.5Land use change in the Heihe River basin   
/km²   

<html><body><table><tr><td></td><td>时段</td><td>林地</td><td>草地</td><td>耕地</td><td>城乡－工矿－居民用地</td><td>水体</td><td>未利用土地</td></tr><tr><td rowspan="3">上游</td><td>1980s</td><td>-48.57</td><td>-176.02</td><td>1. 19</td><td>247.95</td><td>0.27</td><td>-26.36</td></tr><tr><td>1990s</td><td>9.05</td><td>192.52</td><td>-0.03</td><td>-0.05</td><td>-246.86</td><td>45.14</td></tr><tr><td>2000s</td><td>-26.88</td><td>- 24.22</td><td>352.64</td><td>45.42</td><td>33.22</td><td>-380.98</td></tr><tr><td rowspan="4">中游</td><td>1980-2010</td><td>-43.46</td><td>14.4</td><td>1.63</td><td>0.18</td><td>0.01</td><td>26.56</td></tr><tr><td>1980s</td><td>52.95</td><td>205.80</td><td>-302.60</td><td>12.98</td><td>149.25</td><td>-64.39</td></tr><tr><td>1990s</td><td>- 79.64</td><td>- 442.49</td><td>802.31</td><td>54.10</td><td>- 181.18</td><td>-182.92</td></tr><tr><td>2000s</td><td>-11.89</td><td>-23.88</td><td>278.90</td><td>47.92</td><td>2.19</td><td>-293.27</td></tr><tr><td rowspan="4">下游</td><td>1980-2010</td><td>-30.00</td><td>-210.23</td><td>525.01</td><td>68.00</td><td>-30.26</td><td>-312.04</td></tr><tr><td>1980s</td><td>-418.33</td><td>359.12</td><td>2.02</td><td>-7.35</td><td>- 40.65</td><td>105.74</td></tr><tr><td>1990s</td><td>410.24</td><td>-527.46</td><td>84.86</td><td>10.96</td><td>66.27</td><td>-43.84</td></tr><tr><td>2000s</td><td>-10.50</td><td>12.66</td><td>80.33</td><td>1.03</td><td>33.44</td><td>-116.46</td></tr><tr><td rowspan="5">整个流域</td><td>1980-2010</td><td>-9.79</td><td>-6.27</td><td>88.84</td><td>2.97</td><td>35.45</td><td>-109.81</td></tr><tr><td>1980s</td><td>-383.77</td><td>732.87</td><td>- 350.36</td><td>5.17</td><td>307.60</td><td>- 311.23</td></tr><tr><td>1990s</td><td>323.94</td><td>-1117.82</td><td>947.77</td><td>65.66</td><td>-311.89</td><td>92.96</td></tr><tr><td>2000s</td><td>-26.88</td><td>-24.22</td><td>352. 64</td><td>45.42</td><td>33.22</td><td>-380.98</td></tr><tr><td>1980-2010</td><td>-68.19</td><td>-343.94</td><td>628.14</td><td>71.13</td><td>5.52</td><td>-292.56</td></tr></table></body></html>

实测值 模拟值 80   
-s·u)/ Muahhekh 01-1982 01-1987 01-1993 01-1997 01-2006 01-2010 210 (b)莺落峡   
（-s·)/ 180 120 AganaA A人 = 90 P 60 州 30 0 01-1982 01-1987 01-1993 01-1997 01-2006 01-2010 150 (c)正义峡   
-s·u)/ 120 90 60 30 4 W 5 P WWww 1 0 01-1982 01-1987 01-1993 01-1997 01-2006 01-2010 月-年

# 表6SWAT模型模拟结果评估

Tab.6Performance of the Soil and Water Assessment Tool(SWAT)   

<html><body><table><tr><td rowspan="2">时间尺度</td><td rowspan="2">水文站点</td><td colspan="2">校准期 (1982-1997 年)</td><td colspan="2">验证期 (1998-2010 年)</td></tr><tr><td>R²</td><td>NS</td><td>R²</td><td>NS</td></tr><tr><td>年尺度</td><td>札马什克</td><td>0.92</td><td>0.78</td><td>0.90</td><td>0.74</td></tr><tr><td rowspan="5">月尺度</td><td>莺落峡</td><td>0.85</td><td>0.75</td><td>0.80</td><td>0.73</td></tr><tr><td>正义峡</td><td>0.68</td><td>0.67</td><td>0.63</td><td>0.55</td></tr><tr><td>札马什克</td><td>0.95</td><td>0.76</td><td>0.90</td><td>0.74</td></tr><tr><td>莺落峡</td><td>0.90</td><td>0.71</td><td>0.80</td><td>0.73</td></tr><tr><td>正义峡</td><td>0.73</td><td>0.56</td><td>0.63</td><td>0.55</td></tr></table></body></html>

和 $0 . 5 5 ; R ^ { 2 }$ 分别是0.68和0.63。在月尺度上，莺落峡水文站在校准期和验证期的 NS系数值分别是0.71和0.73。其结果表明所构建的模型性能比较好，特别是上游区域。SWAT模型对径流的模拟效果比较好，但是峰值的模拟效果相对较差（图2）。这可能是由于模型对地下水过程刻画比较概化的原因所导致的。总的来看，构建的SWAT模型完全可以满足本次研究的需要。

# 3.3径流对气候变化的敏感性

表7列出了径流对平均气温的敏感性值。上游区域1980s径流对平均气温敏感性的最大值趋近于$4 9 . 8 7 ~ \mathrm { m m } \cdot \mathrm { ^ { \circ } C } ^ { \mathrm { ~ - 1 ~ } }$ ,也就是气温变化 $1 \ \mathrm { { ^ { \circ } C } }$ ，径流将会变化 $4 9 . 8 7 ~ \mathrm { m m }$ ;敏感性取值范围是 $8 . 4 7 8 \sim 4 9 . 9 7 0$ $\mathrm { m } \mathrm { m } \cdot \mathrm { } ^ { \mathrm { ~ \textregistered ~ } ^ { - 1 } }$ 。1980s上游径流对气温的敏感性取值范围要远远大于中游和下游，因为上游的最小值都比中游和下游的最大值大。上游区域2000s的敏感性值在1980—2009 年，是1980s 和1990s 的10倍左右。1990s下游区域的敏感性取值范围最小，为0.$3 6 0 \ \sim 2 . 1 1 6 \ \mathrm { m m } \cdot \mathrm { ~ \textcircled { C } } ^ { - 1 }$ 。2000s上游敏感性取值范围最大,为 $1 0 8 . 2 5 0 \sim 6 3 6 . 7 6 5 ~ \mathrm { { m m } \cdot { ^ { \circ } C ^ { - 1 } } }$ 。在1980$- 2 0 0 9$ 年,黑河上游区域径流对气温的敏感性最大；中游敏感性要比下游稍大一些，因为中游的敏感性取值范围的最小值相对更大。

# 表7径流对平均气温的敏感性

Tab.7 Sensitivity of mean temperature   

<html><body><table><tr><td rowspan="2">年代</td><td colspan="2">流域</td><td colspan="2">上游</td><td colspan="2">中游</td><td colspan="2">下游</td></tr><tr><td>Smin</td><td>Smax</td><td>Smin</td><td>Smax</td><td>Smin</td><td>Smax</td><td>Smin</td><td>Smax</td></tr><tr><td>1980s</td><td>2.365</td><td>13.912</td><td>8.478</td><td>49.870</td><td>0.256</td><td>1.509</td><td>0.456</td><td>2.680</td></tr><tr><td>1990s</td><td>4.753</td><td>27.958</td><td>8.259</td><td>48.584</td><td>2.140</td><td>12.591</td><td>0.360</td><td>2.116</td></tr><tr><td>2000s</td><td>25.816</td><td>151.857</td><td>108.250</td><td>636.765</td><td>1.270</td><td>7.471</td><td>0.824</td><td>4.846</td></tr><tr><td>1980-2009年</td><td>10.978</td><td>64.576</td><td>13.413</td><td>78.902</td><td>1. 105</td><td>6.500</td><td>0.461</td><td>2.710</td></tr></table></body></html>

注： $S _ { \mathrm { t m i n } }$ 是最小敏感性值; $S _ { \mathrm { t m a x } }$ 是最大的敏感性值。

# 表8径流对平均降水的敏感性

Tab.8Sensitivity of precipitation   
/mm·mm-1   

<html><body><table><tr><td rowspan="3">年代</td><td colspan="2">流域</td><td colspan="2">上游</td><td colspan="2">中游</td><td colspan="2">下游</td></tr><tr><td>Spmin</td><td>Spmax</td><td>Spmin</td><td>Spmax</td><td>Spmin</td><td>Spmax</td><td>Spmin</td><td>Spmax</td></tr><tr><td>1980s</td><td>0.044</td><td>0.274</td><td>0.044</td><td>0.272</td><td>0.004</td><td>0.026</td><td>0.002</td><td>0.012</td></tr><tr><td>1990s</td><td>0.015</td><td>0.095</td><td>0.039</td><td>0.241</td><td>0.015</td><td>0.096</td><td>0.002</td><td>0.012</td></tr><tr><td>2000s</td><td>0.021</td><td>0.130</td><td>0.057</td><td>0.357</td><td>0.002</td><td>0.011</td><td>0.002</td><td>0.010</td></tr><tr><td>1980-2009年</td><td>0.027</td><td>0.166</td><td>0.049</td><td>0.288</td><td>0.006</td><td>0.038</td><td>0.000</td><td>0.002</td></tr></table></body></html>

注： $S _ { \mathrm { p m i n } }$ 是最小敏感性值； $S _ { \mathrm { p m a x } }$ 是最大的敏感性值。

表8中列出了产水量对降水的敏感性值。可以看出，1980s黑河流域上游敏感性值的取值范围大于中游和下游区域,为 $0 . 0 4 4 \sim 0 . 2 7 2 \mathrm { ~ m m ~ } \cdot \mathrm { ~ m m } ^ { \mathrm { ~ - ~ } 1 }$ 相当于降水改变 $1 ~ \mathrm { m m }$ ，径流将会变化 $0 . 0 4 4 \sim 0$ ·$2 7 2 ~ \mathrm { m m }$ 。而中游和下游降水分别改变 $1 \ \mathrm { m m }$ ,径流则要改变 $0 . 0 0 4 \sim 0 . 0 2 6 ~ \mathrm { m m }$ 和 $0 . 0 0 2 \sim 0 . 0 1 2 \ \mathrm { m m } .$ 。1990s下游径流对降水的敏感性值最低，降水改变1$\mathbf { m } \mathbf { m }$ ,径流仅仅变化 $0 . \ 0 0 2 \sim 0 . 0 1 2 \ \mathrm { m m }$ 。2000s上游区域的敏感性取值范围最大，为 $0 . 0 5 7 \sim 0 . 3 5 7 \ \mathrm { m m }$ （204 $\cdot \ \mathrm { m m } ^ { - 1 }$ ,相当于降水改变 $1 \ \mathrm { m m }$ ,径流将会变化0.$0 5 7 \sim 0 . 3 5 7 \ \mathrm { m m }$ ;中游和下游差不多，当降水改变1$\mathbf { m } \mathbf { m }$ ,径流改变 $0 . 0 0 2 \sim 0 . 0 1 \ \mathrm { m m }$ 。1980—2009年，流域上游敏感性取值范围大于中游区域和下游区域,径流对降水的敏感性最大， $1 \ \mathrm { m m }$ 所引起的径流变化为 $0 . 4 9 \sim 0 . 2 8 8 ~ \mathrm { m m }$ 。中游区域径流对降水的敏感性取值范围大于下游,为 $0 . \ 0 0 6 \sim 0 . \ 0 3 8 \ \mathrm { ~ m m } \cdot$ ：$\mathbf { m } \mathbf { m } ^ { - 1 }$ 。下游径流对降水最不敏感,敏感性取值范围为 $0 \sim 0 . 0 0 2 \ \mathrm { m m } \cdot \mathrm { m m } ^ { - 1 }$ 。

径流对气温和降水的敏感性存在时空差异。上游最敏感，中游低一些，下游最小。各区域径流对气温和降水的敏感性在1980—2009年间波动。同时发现，径流对气温的敏感程度要远远高于对降水的敏感度。上游祁连山的冰雪融水是径流的重要补给源，气温的持续上升导致冰雪融化。研究表明1980s以来气温的升高导致冰雪持续融化，并导致径流的增加[8-9]。农田是中游的主要土地利用方式，气温的升高将会导致蒸发能力增强，实际蒸发量增加，对径流的变化产生直接的影响。而下游区域地表径流量很小，降水稀少，气候变化对水文的影响主要表现为垂直方向[10],气温升高对地下水系统的影响相对更直接。

# 3.4径流对LUCC的敏感性

表9列出了径流对LUCC的敏感性值，在1980s,上游土地利用变化 $1 ~ \mathrm { k m } ^ { 2 }$ ,径流将变化0.114$\mathbf { m } \mathbf { m }$ ,敏感性最大;在2000s的值为 $0 . \ 0 8 0 \ \mathrm { \ m m }$ ：$\mathrm { k m } ^ { - 2 }$ ,敏感性最小。上游区域的敏感性值在1980—2009年逐渐降低。中游区域在1980s敏感性值最大,土地利用变化 $1 ~ \mathrm { k m } ^ { 2 }$ ,径流将变化 $0 . 0 1 6 ~ \mathrm { m m }$ 。中游径流对LUCC敏感性值总体呈下降趋势，但中间有波动，而且比上游同期值要小；下游1980s的值最小,接近零;2000s 的值最大，为 $1 . 2 3 5 \ \mathrm { m m } \cdot \mathrm { k m } ^ { - 2 }$ （2下游区域敏感性值1980—2009年不断增加。

/mm·℃-1   
表9径流对LUCC的敏感性  
Tab.9Sensitivity of land -use $/ \mathrm { m m } \cdot \mathrm { k m } ^ { - 2 }$   

<html><body><table><tr><td>年代</td><td>流域</td><td>上游</td><td>中游</td><td>下游</td></tr><tr><td>1980s</td><td>0.031</td><td>0.114</td><td>0.016</td><td>0.000</td></tr><tr><td>1990s</td><td>0.016</td><td>0.103</td><td>0.000</td><td>0.002</td></tr><tr><td>2000s</td><td>0.002</td><td>0.010</td><td>0.001</td><td>1.235</td></tr><tr><td>1980 -2009 年</td><td>0.020</td><td>0.108</td><td>0.004</td><td>0.001</td></tr></table></body></html>

在1980—2009 年，上游区域径流对LUCC最为敏感，其次是中游，再次是下游；上游、中游和下游径流对LUCC 的敏感性值分别是 $1 0 . 1 0 8 \ \mathrm { m m } \cdot \mathrm { k m } ^ { - 2 }$ 、$0 . 0 0 4 \ \mathrm { m m } \cdot \mathrm { k m } ^ { - 2 }$ 和 $0 . 0 0 1 \ \mathrm { m m } \cdot \mathrm { k m } ^ { - 2 }$ 。在上游地区，径流对LUCC的敏感性在不断减小，在2000s最小。尽管中游区域LUCC对径流的影响最大，但是径流对LUCC的敏感程度要远远小于上游区域，而且敏感程度呈现出变小趋势。下游区域径流对LUCC 的敏感性最小,但有增加趋势,特别是 $2 0 0 0 \mathrm { s }$ 。

LUCC是人类活动的集中体现，LUCC对径流的影响一定程度上体现了人类活动对径流的影响。黑河上游区域是整个流域的产流区，自然环境恶劣，人口稀少，受人类活动的干扰很小，正因为如此，生态系统相对比较脆弱，抵抗外界干扰的能力和适应环境变化的能力较中游和下游要小得多，一旦干扰强度和频率超过生态系统的承受能力，将会产生严重的后果。中下游区域，特别是中游区域，是经济中心和人口集中地，在长期的人类活动干扰下，水文系统在不断地适应和自我调节，敏感性降低，而稳定性增强。

# 3.5 研究的局限性

SWAT水文模型的参数多且模型的校准比较复杂，存在一定的不确定性。与此同时，黑河中游是高强度人类活动影响区，地表水与地下水转化关系复杂，SWAT模型对地下水模拟较为概括。这些都不可避免造成模型模拟的结果具有一定的误差。在后续的研究中需要进行SWAT模型的地下水模块改进与MODFLOW耦合来改善地下水模拟的研究工作。

# 4结论

（1）流域上游径流对降雨敏感性取值范围大于中游和下游， $1 \ \mathrm { m m }$ 降雨变化在上游、中游和下游所引起径流的变化分别是 $0 . 4 9 \sim 0 . 2 8 8 ~ \mathrm { { m m } , 0 . 0 0 6 \sim }$ $0 . 0 3 8 ~ \mathrm { m m }$ 和 $0 \sim 0 . 0 0 2 \ \mathrm { m m }$ 。径流对气温的敏感性从大到小依次是上游、中游和下游。气温变化 $1 \ \mathrm { { ^ { c } } }$ 在上游、中游和下游所引起径流的变化量分别是$1 3 . 4 1 3 \sim 7 8 . 9 0 2 ~ \mathrm { m m } _ { \mathrm { , } } 1 . 1 0 5 \sim 6 . 5 0 0 ~ \mathrm { m m }$ 和 $0 . 4 6 1 \sim$ $2 . 7 1 0 \ \mathrm { m m }$ 。同时发现，径流对气温的敏感程度要远远高于对降水的敏感度。

（2）黑河流域径流对LUCC的敏感性值为$0 . 0 2 0 \ \mathrm { m m } \cdot \mathrm { k m } ^ { - 2 }$ 。1980—2009 年上游区域径流对

LUCC 的敏感性最大,为 $0 . 1 0 8 \ \mathrm { m m } \cdot \mathrm { k m } ^ { - 2 }$ 。其次是中游,敏感性值是 $0 . 0 0 4 \ \mathrm { m m } \cdot \mathrm { k m } ^ { - 2 }$ 。下游区域最小,敏感性值为 $0 . 0 0 1 \ \mathrm { m m } \cdot \mathrm { k m } ^ { - 2 }$ 。

（3）从时间趋势上看，整个流域径流对LUCC的敏感性表现出下降趋势；但存在空间差异，上游表现出下降趋势，而下游却表现为增加趋势。流域径流对气温的敏感性表现为上升趋势

# 参考文献（References）:

[1]Prestele R,Arneth A,Bondeau A,et al. Current challenges of implementing anthropogenic land -use and land -cover change in models contributing to climate change assessments[J].Earth System Dynamics,2017,8(2）:369-386.   
[2]Zare M,Mohammady M,Pradhan B.Modeling the effect of land use and climate change scenarios on future soil loss rate in Kasilian watershed of northern Iran[J].Environmental Earth Sciences,2017, 76(8) :305.   
[3]Senent-aparicio J,Pérez -sánchez J,Carrillo - garcia J,et al. Using SWAT and fuzzy TOPSIS to assess the impact of climate change in the headwaters of the Segura River Basin （SE Spain） [J].Water,2017,9(2）:149.   
[4]张小咏,李佳,杨艳昭,等.基于 SWAT模型的长江源区径流模 拟[J].西北林业大学学报,2012,27（5）:38-45.（Zhang Xiaoyong,Li Jia,Yang Yanzhao,et al.Runoff simulation of the catchent of the Yangtze River based on SWAT model[J].Journal of Northwest forestry University,2012,27(5):38-45.   
[5]Tang Y,Tang Q,Tian F,et al. Responses of natural runoff to recent climatic changes in the Yellow River basin,China[J].Hydrology & Earth System Sciences,2013,17(11):4 471-4 480.   
[6]王中根,朱新军,夏军,等.海河流域分布式 SWAT 模型的构建 [J].地理科学进,2008,27（4）:1-6.［Wang Zhonggen,Zhu Xinjun,Xia Jun,et al.Study on distributed hydrological model in Hai River Basin[J].Progress in Geography,2008,27(4):1 -6.]   
[7]左德鹏,徐宗学.基于SWAT模型和 SUFI-2 算法的渭河流域 月径流分布式模拟[J].北京师范大学学报（自然科学版）， 2012,48（5）:490 -496.[Zuo Depeng,Xu Zongxue.Distributed hydrological simulation using SWAT and Sufi-2 in the Wei River Basin[J]. Journal of Beijing Normal University(Natural Science）, 2012,48(5):490-496.]   
[8］李莹,黄岁樑.河流域景观格局变化对水沙过程的影响[J]. 生态学报,2017,37（7）:2 463-2475.[Li Yin,Huang Suiliang. Effects of landscape pattern change on flow and sediment processes in the Luanhe River Basin[J].Acta Ecologica Sinica,2017,37 (7) :2 463 -2 475.]   
[9］梁建辉.基于 SWAT模型的新疆叶尔羌河流域气候变化对区 域地下水动态影响研究[J].地下水,2017,39（4）：232-233. [Liang Jianhui.Dynamic impact study of climate change on regional groundwater in Xinjiang Yarkant River Basin based on SWAT model[J].Ground Water,2017,39(4）:232-233.]   
[10］李慧,雷晓云,包安明,等.基于 SWAT模型的山区日径流模拟

在玛纳斯河流域的应用[J].干旱区研究，2010，27（5）：686-690.[Li Hui,Lei Xiaoyun,Bai Anming,et al.Application of simu-lation about montanic daily runoff volume in the Manas River Basinbased on SWAT model[J].Arid ZoneResearch,2010,27(5） :686-690.]

[11]张永勇，张士锋，翟晓燕，等.气候变化下石羊河流域径流模拟 与影响量化[J].资源科学,2013,35（3）：601-609.［Zhang Yongyong,Zhang Shifeng,Zhai Xiaoyan,et al.Runof simulation on the impact of climate change in the Shiyang River Basin[J].Resources Science,2013,35(3):601-609.]

[12]程磊，徐宗学，罗睿，等.SWAT在干旱半干旱地区的应用—以窟野河流域为例[J].地理研究，2009，28（1）：65－73，[Cheng Lei,Xu Zongxue,Luo Rui,et al. SWAT application in aridand semi-arid region :A case study in the Kuye River Basin[J].Geographical Research,2009,28（1） :65-73.]

[13]WuF,Zhan J,Su H,et al.Scenario-based impact assessment of Land Use/Cover and Climate Changes on watershed hydrology in Heihe River Basin of Northwest China[J].Advances in Meteorology,2014,2014,(3):1-11.

[14]Zang CF,Liu J,Velde MVD,et al.Assessment of spatial and temporal patterns of green and blue water flows in inland river basins in Northwest China[J].Hydrology & Earth System Sciences,   
2012,16(8) :2 859 -2 870. [15]Zang C,Liu J,Gerten D,et al.Influence of human activities and climate variability on green and blue water provision in the Heihe River Basin,NW China[J]. Journal of Water& Climate Change,   
2015,6(4):800-815. [16]程国栋，肖洪浪,傅伯杰,等.黑河流域生态一水文过程集成研 究进展[J].地球科学进展,2014,29（4）：431-437.［Chen Guodong,Xiao Honglang,Fu Bojie,et al.Advances in synthetic research on the Eco-hydrological process of the Heihe River Basin [J].Advances in Earth Science,2014,29(4）:431-437.] [17]刘浏，刘丽丽，索滢.近53a黑河流域水文气象要素时空演变 特征[J].干旱区研究，2017,34（3）:465-478.［LiuLiu，Liu Lili,Suo Ying. Spatiotemporal evolution of hydro - meteorological variables in the Heihe River Basin in recent 53 years[J].Arid Zone Research,2017,34(3) :465-478.]

# Sensitivity Analysis of Runoff to LUCC and climate change in Heihe River Basin

LUO Kai - shengl,2 TAO Fu -lu 2,3 \*

(1.Schoolof Remote Sensingand Geomatics Engineering,Nanjing University of Information Science andTechnology,Nanjing,210044,Jiangsu,China； 2.Key Laboratory for surface patter and processes,Institute of Geographical sciences and Natural resources,Chinese Academy of Sciences,Beijing,1Oo1o1,Beijing,China ; 3.College ofResources and Environment,UniversityofChinese AcademyofSciences,Beijing,ooo49,China)

Abstract：To quantitative assessing the sensitivity of runof to climate and land use/cover change（LUCC）in Heihe River Basin during 198O-2O09.Multiple data sources（including land-use digital elevation data、soil、 weather）spanning from 198O to 2016 were applied to drive the SWAT,observed runoffdata was used forcalibration and validation.The results indicate that the sensitivity value of runof to LUCC is $0 . 0 2 0 \mathrm { m m }$ ？ $\mathrm { k m } - 2$ ,which means that the land use changes $1 \mathrm { k m } ^ { 2 }$ ,and the runoff will change $0 . 1 1 4 ~ \mathrm { m m }$ . Meanwhile,The changes of runoff caused by the variation of the $1 \mathrm { m m }$ precipitation in the upstream,middle- stream and downstream were $0 . 4 9 - 0 . 2 8 8 ~ \mathrm { m m } , 0$ ： $0 0 6 - 0 . 0 3 8 \mathrm { m m }$ and $0 - 0 . 0 0 2 \mathrm { m m }$ respectively,and the variation of $1 \mathrm { { ^ { \circ } C } }$ in the upstream,middle - stream and downstream were $1 3 . 4 1 3 - 7 8 . 9 0 2 \mathrm { m m }$ ， $1 . 1 0 5 - 6 . 5 0 0 \mathrm { m m }$ and $0 . 4 6 1 - 2 . 7 1 0 \mathrm { m m }$ .We further found that the sensitivityof runoffto temperature is much higher than thatof precipitation.The sensitivityof runof toLUCC from big to small is upstream ( $ { \left( 0 . 1 0 8 \ m m \right) }  { \mathrm { : } } \ k  { \mathrm { m - } } 2  { \mathrm { : } }$ ，middle reaches ( $ { 0 . 0 0 4 }  { \mathrm { \ m m ? } }  { \mathrm { \ k m - \ } 2 }  { \mathrm { \ m } }$ ）and downstream（0.001 mm？ km -2）from198O to 2009.Temporally，the sensitivity of runoff to LUCC in the whole basin shows a downward trend；the upstream region shows a decrease trend，while the downstream shows an increasing trend.The sensitivity of basin runoff to temperature is increasing during 198O - 2009.

Key words: runoff； climate change； land use change；sensitivity；SWAT model， Heihe river