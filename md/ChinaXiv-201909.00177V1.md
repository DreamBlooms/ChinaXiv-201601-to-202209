# 基于地表温度和叶面积指数的干湿限研究及区域蒸散发估算

王军1,2.3，李和平1,2,3，鹿海员1,2,3，张瑞强1,2,3，曹雪松1,2,3（1．中国水利水电科学研究院牧区水利科学研究所,内蒙古 呼和浩特010020；2．水利部牧区水利科学研究所，内蒙古 呼和浩特010020；3．流域水循环模拟与调控国家重点实验室,北京100038)

摘要：针对遥感能量平衡方法估算区域蒸散发 $( E T )$ 存在的空间歧义性问题，本文以METRIC模型为例，基于地表温度 $( T _ { \mathrm { s } } )$ 与叶面积指数 $( L A I )$ 相关趋势图，按照“ $T _ { \mathrm { s } }$ 频率直方图占比前 $5 \%$ 的最高温度区 $\mathbf { \nabla } _ { \cdot } L A I$ 频率直方图占比后$5 \%$ 的裸土区为‘干点’， $T _ { \mathrm { s } }$ 频率直方图占比后 $5 \%$ 的最低温度区 $\ 、 L A I$ 频率直方图占比前 $5 \%$ 的湿地或农田为‘湿点""的提取方案,综合确定研究区的干湿限,并通过下垫面涡度相关系统实测数据验证了模型估算精度。经检验，校准期和验证期的区域 $E T$ 估算控制精度平均为 $1 5 \%$ ,与以往研究成果相比,结果相对合理,提取方案在一定程度上可为METRIC 模型主观确定干湿限提供帮助。将 $E T$ 估算结果按土地利用分类提取,研究区不同土地利用类型表现为 $E T _ { \mathrm { \# K \# K } } > E T _ { \mathrm { \# K \# K } } > E T _ { \mathrm { \# K \# K } } > E T _ { \mathrm { \# K \# K \# K \# K } } > E T _ { \mathrm { \# K \# K \# K \# K } } > E T _ { \mathrm { \# K \# K \# K \# K \# K } } \approx E T _ { \mathrm { \# K \# K \# K \# K \# K } } \simeq E T _ { \mathrm { \# K \# K \# K \# K } }$ ,成果对区域遥感 $E T$ 精准估算研究具有一定参考意义。

关键词：蒸散发；METRIC 模型；干湿限；地表温度；叶面积指数；内蒙古

蒸散发（evapotranspiration， $E T )$ 作为陆面水文循环和能量循环过程的重要环节，是水热平衡联系的纽带[1],准确监测和估算其时空变化规律,对提高区域水分生产利用效率、缓解地区用水矛盾等具有重要理论价值和现实意义[2-3]。随着ET研究理论的不断深入，涌现出许多，如水量平衡法、蒸渗仪法、波文比法、空气动力学法、涡度相关法、闪烁通量法等监测和估算方法[4-10],这些方法在微观和农田尺度可详尽描述ET过程的特征规律，为下垫面水汽交换、农田灌溉决策、水资源综合管理提供了重要参考和依据(11-13]。目前,ET研究尺度逐渐由微观拓展到宏观，但这些传统的监测手段和方法并不能详尽反映区域ET的真实空间特征。遥感技术的出现，克服了传统方法中定点观测难以推广到大尺度的瓶颈[14]，为大范围 $E T$ 估算提供了有效解决方案。

近年来，遥感ET模型的发展从简单到复杂、从经验到机理，在理论创新和方法应用上已取得众多成果，其中，以遥感能量平衡（RSEB)为理论基础的METRIC模型是当前估算区域ET的典型代表。该模型计算的关键是地表阻抗( $\left( \boldsymbol { r } _ { a _ { } } ^ { } \right)$ )和地气温差(dT)

两个参数，参数 $r _ { a }$ 通过莫宁-奥布霍夫循环迭代实现最优求解；另一参数 $d T$ 在求解过程中，METRIC模型巧妙利用“干点”和“湿点”两个干湿限解决了经验参数 $\boldsymbol { a }$ 和 $b$ 求解问题，大大简化了显热通量计算。但是，模型要求研究者必须对研究区物理背景进行深入了解，确保主观选取的干湿点为研究区内显热通量和潜热通量的上下临界点，才能保证显热通量和潜热通量的计算精度。研究者在应用MET-RIC 这类模型时，由于干湿限的确定具有很大的主观性，往往因找不到理想的“十点”和“湿点”像元导致模型计算精度不高，从而产生遥感ET空间歧义性问题[15],即不同研究者利用相同的遥感数据和模型却得到不同的ET估算结果。其原因是不同研究者认识标准不一致，主观选取的干湿限标准不一，计算的显热通量或潜热通量差别较大，从而影响了区域ET模拟精度，限制了模型更大范围的应用。基于此，本文针对METRIC 模型计算区域 $E T$ 出现的空间歧义性问题，通过地表温度( $ { T _ { \mathrm { s } } }$ )和叶面积指数$( L A I )$ 梯形特征空间模型理论构建干湿限，尝试提出一种“干点”和"湿点”像元的简易提取方法,并借助下垫面涡度相关系统实测水汽通量数据验证模型估算精度，进一步探讨ET的时空分布特征，以期为区域遥感ET精准估算提供帮助。

# 1 研究方法

METRIC(mapping evapotranspiration at high res-olutionwithinternalizedcalibration）模型是以SEBAL模型为理论基础(16-17],考虑下垫面高程、坡度、坡向等因素的干扰，通过将遥感表面信息转换为地表反照率、地表比辐射率、植被指数和 $T _ { \mathrm { s } }$ 等地表特征参数，结合下垫面气象观测数据计算区域 $E T$ 的一种方法[18-19]。其理论方程为：

$$
L E = R _ { \mathrm { n } } - G - H
$$

式中： $L E$ 为潜热通量； $R _ { \mathrm { n } }$ 为地表净辐射量； $G$ 为土壤热通量； $H$ 为显热通量。式中各能量分项单位均为W·m−2。

# 1.1 地表净辐射量

$R _ { \mathrm { n } }$ 是由天空(包括太阳和大气)向下投射与由地表(包括土壤、植物、水面)向上投射之间全波段辐射量之差，该值是下垫面能量、水分传输的主要动力。其计算方程式为：

$$
R _ { \mathrm { n } } = \left( 1 - \alpha \right) \cdot K _ { \mathrm { i n } } + \left( L _ { \mathrm { i n } } - L _ { \mathrm { o u t } } \right) - \left( 1 - \varepsilon \right) \cdot L _ { \mathrm { i n } }
$$

式中： $\alpha$ 为地表反照率,无量纲; $K _ { \mathrm { i n } }$ 为短波辐射; $L _ { \mathrm { i n } }$ 为下行的长波辐射； $L _ { \mathrm { o u t } }$ 为上行的长波辐射； $\boldsymbol { \varepsilon }$ 为地表比辐射率，无量纲。式中能量分项单位均为W·$\mathrm { ~ m ~ } ^ { - 2 }$ 。各参数计算依据详见文献[14]。

# 1.2 土壤热通量

$G$ 是指由于传导作用而存储在植被和土壤中的那部分能量，其变化主要受地表净辐射和下垫面植被覆盖影响。综合比较，本文参照Bastiaanssen 和Wright等成果[16,20],采用下列经验公式进行计算：

$$
G = { \frac { T _ { \mathrm { s } } - 2 7 3 . 1 5 } { \alpha } } { ( 0 . 0 0 3 ~ 8 \alpha + 0 . 0 0 7 ~ 4 \alpha ^ { 2 } ) } ~ \cdot
$$

$$
( 1 - 0 . 9 7 8 N D V I ^ { 4 } ) \cdot R _ { \mathrm { n } }
$$

式中： $T _ { \mathrm { s } }$ 为地表温度(K);NDVI为归一化植被指数，其计算依据卫星热红外波段和红外波段计算，无量纲;其他参数意义同上。

# 1.3 显热通量

$H$ 是描述陆面与大气能量交换的一个过程，通过对流或传导的方式，从地球表面转移到大气中的那部分能量。对于 $H$ 的计算，METRIC 模型基于“干点”和"湿点"像元、零平面位移以上高度 $\mathbf { z } _ { 1 }$ 和 $\mathbf { z } _ { 2 }$ 处温差 $d T$ （ $d T = T _ { 1 } - T _ { 2 } )$ 与 $T _ { \mathrm { s } }$ 之间的线性关系假设，巧妙地避免了下垫面气象数据空间插值及订正 $T _ { \mathrm { s } }$ 引起的误差，进而通过高程、坡度、坡向修正，实现遥感影像每个像元计算结果的校准。其计算方程式为：

$$
H = \rho _ { \mathrm { a i r } } c _ { \mathrm { p } } \ \frac { d T } { r _ { \mathrm { a } } }
$$

式中： $\cdot \rho _ { \mathrm { a i r } }$ 为空气密度( $\mathbf { \nabla } ( \log \cdot \mathbf { \nabla } \mathbf { m } ^ { - 3 } )$ ） $c _ { \mathrm { p } }$ 为空气定压比热容 $( 1 ~ 0 0 4 ~ \mathrm { J } \cdot \mathrm { k g } ^ { - 1 } \cdot \mathrm { K } ^ { - 1 } ) ; i$ $r _ { \mathrm { a } }$ 为两个近表面高度之间的空气动力学阻抗，其计算是假设地面 $2 0 0 \mathrm { ~ m ~ }$ 以上的掺混层空气运动不受下垫面影响，整个研究区域为同一常数，利用 $2 0 0 \mathrm { ~ m ~ }$ 处的风速推算地表的摩擦风速求解[16,18]； $d T$ 通过与 $T _ { \mathrm { s } }$ 之间线性关系式计算。其计算方程式如下：

$$
d T = a T _ { \mathrm { s , a d t u m } } + b
$$

$$
a = \frac { d T _ { \mathrm { { \scriptscriptstyle * } } } - d T _ { \mathrm { { \scriptscriptstyle * * } } } } { T _ { \mathrm { { s , a d t u m } \mathrm { \scriptscriptstyle * } } } - T _ { \mathrm { { s , a d t u m } \mathrm { \scriptscriptstyle * \mathrm { \scriptscriptstyle * } } } } }
$$

$$
b = d T _ { \mathcal { F } } - a T _ { \mathrm { s , a d t u m \mathcal { F } } }
$$

$$
T _ { \mathrm { s , a d t u m } } = T _ { \mathrm { s } } + 0 . 0 0 6 5 \Delta Z
$$

式中： $\boldsymbol { a } , \boldsymbol { b }$ 为经验参数; $T _ { \mathrm { s , a d t u m } }$ 为修正地表温度（K），对于非平原区需要利用数值高程差 $\Delta Z$ 修正,其中$\Delta Z$ 为每个像元的高程与参考高程之差；其他参数意义同上。

# 2研究区概况与数据预处理

# 2.1 研究区概况

研究区选在内蒙古典型草原区锡林河流域（地理坐标为 $1 1 5 . 5 3 ^ { \circ } \sim 1 1 7 . 2 5 ^ { \circ } \mathrm { E } , 4 3 . 4 1 ^ { \circ } \sim 4 4 . 6 3 ^ { \circ } \mathrm { N } )$ ，面积约为 $1 1 \ 1 7 2 \ \mathrm { k m } ^ { 2 }$ 。地势呈东南高西北低,海拔在 $9 0 2 \sim 1 ~ 6 2 1 ~ \mathrm { m }$ 。多年平均降水量为 $1 8 8 ~ \mathrm { m m }$ ,多年平均蒸发量约为 $1 ~ 9 0 3 ~ \mathrm { m m }$ ,在空间分布上由东南向西北递增，属典型的大陆性温带半干旱气候。区内土地利用类型主要是以草地为主（图1a和图1b）。

# 2.2 数据源及预处理

数据源处理包括遥感和气象数据。其中，遥感数据来自USGS网站的Landsat5TM数据（分辨率$3 0 ~ \mathrm { m } \dot { }$ ），结合云覆盖状况，选用2006年8月4日卫星过境时刻的遥感影像作为校准期数据，2007年7月6日、2008年8月25日、2009年6月25日和8月12日作为验证期数据，利用DEM对原始数据进行几何校正和掩膜处理，得到模型所需的遥感数据(表1)。

![](images/00eb2ba3e3205bf50673aa4991819dc5a4a25a2990689c2fc6b30ad36302e97b.jpg)  
图1研究区位置图  
Fig.1Geographical location of the study area

Tab.1Information of landsat 5 TM Data (PATH124/ROW 29 and 30)   
表2卫星过境时刻各站点气象信息  

<html><body><table><tr><td></td><td>日期</td><td>儒略日 /d</td><td>卫星过境 当地时刻</td><td>云覆盖 /%</td></tr><tr><td rowspan="4">校准期 验证期</td><td>2006-08-04</td><td>216</td><td>10：51:48</td><td>0</td></tr><tr><td>2007-07-06</td><td>187</td><td>10:52:15</td><td>0</td></tr><tr><td>2008-08-25</td><td>238</td><td>10：44:09</td><td>0</td></tr><tr><td>2009-06-25</td><td>176</td><td>10:47:00</td><td>6</td></tr><tr><td></td><td>2009 -08-12</td><td>224</td><td>10:48:09</td><td>0</td></tr></table></body></html>

表1Landsat5TM数据信息(PATH124/ROW29和30)  
Tab.2Meteorological information of the stations at satellite transit time   

<html><body><table><tr><td>站点</td><td>经度 /(°)</td><td>纬度 /(°)</td><td>海拔 /m</td><td>风速 /(m·s-1)</td><td>气温 /℃</td><td>水汽压 /kPa</td></tr><tr><td>东乌珠穆沁旗116.97</td><td></td><td>45.52</td><td>840.50</td><td>2.8</td><td>25.5</td><td>0.91</td></tr><tr><td>阿巴嘎旗</td><td>114.95</td><td>44.02</td><td>1127.90</td><td>3.2</td><td>23.9</td><td>0.89</td></tr><tr><td>化德县</td><td>114.00</td><td>41.90</td><td>1 140.00</td><td>3.1</td><td>18.1</td><td>0.85</td></tr><tr><td>西乌珠穆沁旗117.60</td><td></td><td>44.58</td><td>996.60</td><td>4.9</td><td>22.2</td><td>0.90</td></tr><tr><td>锡林浩特市</td><td>116.07</td><td>43.95</td><td>990.80</td><td>4.3</td><td>24.2</td><td>0.81</td></tr><tr><td>林西县</td><td>118.07</td><td>43.60</td><td>800.30</td><td>0.9</td><td>23.0</td><td>0.92</td></tr><tr><td>多伦县</td><td>116.47</td><td>42.18</td><td>1 245.40</td><td>1.3</td><td>19.3</td><td>0.88</td></tr></table></body></html>

气象数据来自锡林浩特市等周边7个旗县的气象站，具体包括气温、风速和水汽压等。其中，气温用于 $T _ { \mathrm { s } }$ 和地表净辐射计算；风速用于空气动力学阻抗计算；水汽压用于大气透过率、地表反照率等参数计算。以2006年8月4日为例，各气象站点在卫星过境时刻（11：00左右）气象数据整理见表2。

# 3干湿限分析与ET估算

# 3.1 干湿限确定与分析

模型中的干湿限即“干点”和“湿点”两种特殊的极限像元。其中，“干点”指没有植被覆盖的干燥的闲置农田或荒地，温度很高，蒸散量几乎为0的像元，“干点”满足 $H { \approx } R _ { \mathrm { n } } - G { \ } , L E { \approx } 0$ ；“湿点”是指影像中水分供应充足、植被生长茂盛、温度很低、处于潜在蒸散水平的像元，可以是植物生长良好的完全覆盖的区域或开放的水体,在“湿点”上 $H \approx R _ { \mathrm { n } } \ - \$ $G - L E$ ,特殊情况下 $H { \approx } 0$ 。通过对“干点”和“湿点”

点位信息提取,便可以求得dT值的分布[21],但这种提取过程往往伴随空间歧义性的出现。针对模型计算出现的空间歧义性问题,Tasumi[22]借鉴 Moran 提出的dT/SAVI（SAVI表示土壤调节植被指数）梯形特征空间模型理论，假定 $d T$ 与下垫面 $T _ { \mathrm { s } }$ 高度相关的前提下，参照 $T _ { \mathrm { s } }$ 与 $L A I$ 相关趋势图选定干湿限[22]（图2）。

图2中，A点附近为干燥裸土区，集中在该区域的像元表现为土地裸露缺水;B点附近为湿润裸土区，集中在该区域的像元一般为盐碱地或裸露的沙地；C点附近为高覆盖湿润区，集中在该区域的像元一般为水分湿润的湿地或农田;D点附近为高覆盖缺水区，集中在该区域的像元一般为植被高覆盖的旱作耕地或草地。根据Tasumi研究结论，“干点"在$T _ { \mathrm { s } }$ 频率直方图占比前 $5 \%$ 像元中提取，“湿点”在 $T _ { \mathrm { s } }$ 频率直方图占比后 $3 \% \sim 5 \%$ 像元中提取。

![](images/c93466d98459cf16952cf5fed3936e5cf615f9c97dd9aaebcf4cec84fcf65c52.jpg)  
图2地表温度 $( T _ { \mathrm { s } } )$ 与叶面积指数 $( L A I )$ 相关趋势图 Fig.2Correlation of surface temperature $( T _ { \mathrm { s } } )$ and leaf area index $( L A I )$

在实际操作过程中，受季节、土地利用类型及云覆盖等因素影响，仅通过 $T _ { \mathrm { s } }$ 选取干湿限仍存在较大的偶然性和不确定性。因此，本文提取方案是综合考虑下垫面 $T _ { \mathrm { s } }$ 和植被覆盖及土地利用现状，首先剔除云覆盖的干扰，在Tasumi提取方案基础上，加入LAI约束,将“干点”提取范围集中到A点，“湿点”提取范围集中到C点。具体提取是以土地利用为底图，考虑有效像元提取的便利性， $L A I$ 控制线设置过小，符合约束条件的像元难以发现， $L A I$ 控制线过大，符合约束条件的像元过多，无法提取到有效干湿限，因此 $L A I$ 干湿限控制线参照 $T _ { \mathrm { s } }$ 中的 $5 \%$ 提取，即选取 $T _ { \mathrm { s } }$ 频率直方图占比前 $5 \%$ 的最高温度区、 $L A I$ 频率直方图占比后 $5 \%$ 的裸土区为“干点”，选取 $T _ { \mathrm { s } }$ 频率直方图占比后 $5 \%$ 的最低温度区 $. L A I$ 频率直方图占比前 $5 \%$ 的湿地或水田为“湿点”。

![](images/ae92f387f226c3f1c209e9d5ef37147adb17445bdb0903358086cc850bb37868.jpg)  
图3研究区地表温度和叶面积指数空间分布  
Fig.3Spatial distribution of surface temperature $( T _ { \mathrm { s } } )$ and leaf area index ( $\cdot L A I )$ in the study area

图3是区域“干点”和“湿点”像元提取需要计算的 $T _ { \mathrm { s } }$ 和 $L A I$ 值。其中, $T _ { \mathrm { s } }$ 依据单窗算法计算[23]经式（8）高程调整计算，2006年8月4日研究区$T _ { \mathrm { s } } \in \left[ 2 8 3 . 0 \ \mathrm { K } , 3 2 5 . 0 \ \mathrm { K } \right]$ ,均值为 $3 0 6 . 2 \mathrm { ~ K ~ }$ （图3a）；$L A I$ 依据土壤调节植被指数(SAVI)计算[15],确定研究区 $L A I \in \left[ 0 . 0 , 6 . 0 \right]$ ，均值为0.38（图3b）。方案根据控制条件叠加 $T _ { \mathrm { s } }$ 和 $L A I$ 指数图，剔除了云覆盖的无效像元（图3a中 $T _ { \mathrm { s } }$ 在 $2 8 3 \sim 2 9 3 \mathrm { ~ K ~ }$ 的部分像元），确定了研究区的“干点”( $T _ { \mathrm { s } } = 3 1 5 . 8 {  { \mathrm { ~ K } } } , L A I =$ 0.00)和"湿点”( $T _ { \mathrm { s } } = 2 9 6 . 6 \textrm { K } , L A I = 1 . 7 3 \textrm { ) }$ 像元。

# 3.2 结果验证

干湿限确定后，利用莫宁-奥布霍夫循环迭代，实现显热通量和潜热通量计算，进而通过蒸发比法扩展得到日 $E T$ 值。通过METRIC模型反演的区域

ET是否真实地反映了下垫面蒸散耗水特征，需要进行结果验证及对比分析。受监测技术的限制，目前仍未有较成熟的技术实现 $E T$ 的区域尺度验证。对于模型的估算结果，本文采用内蒙古锡林郭勒草原生态系统国家野外科学观测研究站实测数据完成。该站位于研究区东南部，站内布设的涡度相关系统实测水汽通量数据来验证METRIC模型的估算结果。经现场调查，涡度相关系统方圆 $2 ~ \mathrm { k m }$ 内均为天然草地（图1c），植被类型主要以大针茅和羊草为主[24],因此可以根据研究区土地利用现状图及NDVI的取值特征，选择以系统所在位置（地理坐标为 $1 1 6 . 6 7 ^ { \circ } \mathrm { E } , 4 3 . 5 5 ^ { \circ } \mathrm { N }$ ;海拔 $\mathrm { ~ 1 ~ } 2 5 0 \mathrm { ~ m } \mathrm { ~ }$ )为中心的 $3 \times$ 3大小窗口范围内9个像元 $( 0 . 8 1 \times 1 0 ^ { 4 } \ \mathrm { m } ^ { 2 }$ ） $E T$ 估算结果平均值为代表，进行实测的蒸散量与MET-RIC 模型估算的 $E T$ 之间的对比分析（图4）。

图 $\mathrm { 4 a }$ 显示了研究区5个不同时相的METRIC模型遥感估算 $E T$ 值与涡度相关实测 $E T$ 值之间的数值关系，2006年8月4日 $\cdot 2 0 0 7$ 年7月6日、2008年8月25日 $\cdot 2 0 0 9$ 年6月25日和8月12日等5个不同时相遥感估算 $E T$ 值与涡度相关实测 $E T$ 值的相对误差分别为 $1 9 \%$ $2 7 \%$ 、 $10 \%$ $4 \%$ 和 $16 \%$ ，平均相对误差为 $1 5 \%$ 。结合Kalma等对不同遥感估算$E T$ 方法的精度统计发现，与基于地面的 $E T$ 测量值相比，大多数相对误差范围为 $1 5 . 0 \% \sim 3 0 . 0 \% ^ { \mathrm { ~ ( ~ ) ~ } }$ 25]，从误差结果分析，这种干湿限提取方案计算的区域ET估算可以满足区域 $E T$ 研究的精度要求。由图4b可以看出，利用METRIC模型估算的ET与涡度相关系统实测水汽通量数据在一定程度上变化趋势整体吻合，模拟值与实测值之间具有较高的拟合优度（决定系数 $R ^ { 2 }$ 为0.98）;根据统计显示，在各个时相上METRIC模型估算结果均存在不同程度的高估现象。受仪器设备和资料数据的限制，如果需要对ET估算结果进行系统的、多区域的对比验证，则需要在研究区布设大孔径闪烁仪等设备，来进一步印证模型估算结果的可信度。

# 3.3 ET空间特征分析

根据METRIC 模型的基本原理及算法，本文基于自主开发的区域 $E T$ 计算系统V1.0（软件著作权登记号2017SR680304），计算得到研究区不同时相的ET值(图5）。其中：图 $5 ( \mathrm { \ a \sim e ) }$ 依此为锡林河流域2006年8月4日 $\cdot 2 0 0 7$ 年7月6日、2008年8月25日、2009年6月25日和8月12日的ET结果；图5f为研究区土地利用空间分布。

结合研究区LAI(图3b)和土地利用空间分布图（图5f)分析，从锡林河流域东南部的林草交错带到西北部的低覆盖草地，降水量逐渐减少、干旱化程度逐渐加剧， $L A I$ 也存在显著差异，因此在气候条件、土壤供水状态、土地利用类型等因素的综合影响下，锡林河流域 $E T$ 的估算结果也表现出明显的空间分异特性。将图5中ET结果与土地利用类型相结合进行分析，发现除水体等高蒸散特性地物之外，5个时相的 $E T$ 估算结果均表现出了从东南向西北递减的变化趋势。流域东南部为大兴安岭南麓灌木林区，降水相对丰富，林草植被长势良好，具备了较好的 $E T$ 条件。另外，近年来流域内少量天然草地开发变成了种植青贮玉米的灌溉人工草地，相对充足的供水条件保证了东南部林草交错区和耕地区的ET值最接近于水体的蒸散强度。流域西北部属于典型草原区，该区降水稀少、气候干旱,生态环境十分脆弱，加上近年来过度放牧导致草原类型逐步退化成荒漠草原，降水稀少和植被类型单一共同限制了ET，因此该地区实际ET明显低于其他区域。

![](images/53a900d7318837b0014f5129deb5cbbd38d4ae46ebef7de63de2b3d9ed5faacb.jpg)  
图4METRIC 模型的遥感估算与涡度相关实测ET值对比

Fig.4Comparison between $E T$ values estimated by METRIC model and measured by eddy covariance syste

![](images/9c939196aee95958ae987f5aa7190d34ed3b8c1c22726a87adab412e46041900.jpg)  
图5ET估算结果  
Fig.5Estimated results of ET

另外，将5个时相的 $E T$ 结果平均化处理，不同土地利用类型表现为 $\begin{array}{c} \begin{array}{c} E T _ { \mathrm { \tiny { \mathcal { H } \ / 4 } } } > E T _  \mathrm  \tiny  \frac { . . . 6 7 }  9 9 \mathrm  \tiny  \frac { . . . 6 7 }  9 9 \mathrm  \tiny  \frac { . . . . 6 7 }  9 9 \mathrm  \tiny \frac { 5 }  9 9 \mathrm  \tiny \frac { 5 }  9 \mathrm \tiny  \frac { \frac \cdot . . . . 6 7 }  9 9 \mathrm  \tiny \frac { \frac 5 }  9 9 \mathrm  \tiny \frac \frac { 5 }  9 \mathrm \tiny  \frac \frac { \frac \ddots }  9 9 \mathrm \mathrm  \tiny \frac \frac { \frac \ddots }  9 \mathrm \Big \frac  \frac \Big \frac { \frac \Big } { 5 }  9 \mathrm \tiny \frac  \frac \Big \frac { \frac \Big } { 5 \Big } { 5 \Big } { 9 \mathrm \tiny \frac { \frac \Big \frac } { 5 \Big \Big { \frac \Big \frac } { 5 \Big } { 5 \Big \Big \Big \} { \frac \Big \Big { \frac 5 } { 5 \Big } } { 9 \mathrm \Big { \Big \Big \frac \Big { \frac \frac } { 5 \Big \Big { \Big \frac \Big } { 5 \Big } { 5 \Big \Big \Big \Big { \frac \Big \frac } { 5 } { 5 \Big \Big \Big \Big { \frac \Big \Big } { 5 \Big \Big \Big \Big { \frac \Big } \frac { 5 } } { 9 \mathrm \Big { \Big \Big \Big \frac { \Big \frac \Big } { 5 \Big \Big \Big { \frac \Big \Big } { 5 \Big \Big \Big { \Big \frac } \Big { 5 \Big \Big \Big } { \Big \frac \Big } { 5 \Big \Big \Big { \Big \frac \Big } { 5 \Big \Big \Big \Big { \frac \Big } \Big { 5 \Big \Big \Big } { 5 \Big \Big \Big \Big { \frac \Big \Big } { 5 \Big \Big \Big \Big { \frac \Big } \Big { 5 \Big \Big \Big \Big { \Big \frac } \Big { 5 \Big \Big \Big \Big { \Big \frac } \Big { 5 \Big \Big \Big { \Big \Big \Big \frac } { 5 \Big \Big \Big { \Big \Big \Big \Big } { \Big \frac } { 5 \Big \Big \Big \Big { \Big \Big \Big \Big } { 5 \Big \Big \Big \Big { \Big \Big \frac } { 5 \Big \Big \Big \Big { \Big \Big \Big } \Big { \Big \Big \Big } \Big { \Big \Big \Big } } } } } } } } } } } } } } } } } } > } } } } \end{array} } \mathrm { \hfill ~ E T \ T \mathrm { \ S ~ \ i f \Psi \Psi \Psi \Psi \Psi ~ \quad > \quad } } } \end{array}$ （204号$E T _ { \vec { \ast } \vec { \ast } \vec { \ast } \vec { \ast } \vec { \ast } | | \mathcal { H } \pm \vec { \ast } \vec { \ast } \vec { \ast } } > E T _ { \vec { \ast } \vec { \ast } \vec { \ast } } \circ \vec { \ast } \vec { \ast } \vec { \ast } \vec { \ast } \vec { \ast } \vec { \ast } \vec { \ast } \vec { \ast } \vec { \ast } \vec { \ast }  \approx E T _ { \vec { \ast } \vec { \ast } \vec { \ast } \vec { \ast } \vec { \ast } } \$ 。分析原因，充足的水分为水体 $E T$ 创造了条件；林地多分布在河谷低洼地带，下垫面相比其他类型水分较为充足；耕地多是在天然草地基础上开垦形成，喷灌和滴灌等灌水技术为 $E T$ 提供了水分保证。另外，根据实地调查发现，由于近年来气候干旱及降雨减少，导致流域西北地区的典型草原已退化成植被覆盖度低、干旱少水的荒漠化草地或沙地，使得草地的平均 $E T$ 强度整体偏低。

表3不同土地利用类型ET估算结果  
Tab.3Estimated ETresults ofdifferent land   

<html><body><table><tr><td>use types</td><td colspan="4"></td><td colspan="2">/(mm·d-1)</td></tr><tr><td>耕地</td><td></td><td>林地</td><td>草地</td><td>水体</td><td>城乡工矿 居民用地</td><td>未开发 利用土地</td></tr><tr><td>平均值</td><td>1.38</td><td>1.89</td><td>1.11</td><td>4.43</td><td>1.12</td><td>1.32</td></tr></table></body></html>

# 4结论

针对遥感能量平衡方法估算区域 $E T$ 值的空间歧义性问题，以METRIC模型为例，基于 $T _ { \mathrm { s } }$ 与 $L A I$ 相关趋势图，按照“ $T _ { \mathrm { s } }$ 频率直方图占比前 $5 \%$ 的最高温度区 $, L A I$ 频率直方图占比后 $5 \%$ 的裸土区为‘干点’， $T _ { \mathrm { s } }$ 频率直方图占比后 $5 \%$ 的最低温度区、 $L A I$ 频率直方图占比前 $5 \%$ 的湿地或水田为‘湿点’”的提取方案，综合确定了研究区的“干点”和"湿点”像元，进而实现了区域 $E T$ 的估算。经涡度相关系统实测水汽通量数据验证，校准期和验证期的区域ET估算精度平均为 $1 5 \%$ ,与以往研究成果相比，结果相对合理，提取方案在一定程度上可为METRIC 模型主观确定干湿限提供帮助；将 $E T$ 按土地利用分类提取,研究区不同土地利用类型为： $E T _ { \mathrm { \scriptscriptstyle \mathscr { X } \mathscr { H } } } >$ $E T _ { \mathrm { \# \# \# } } > E T _ { \mathrm { \# \# \# } } > E T _ { \bar { \jmath } }$ 开发利用土地 $>$ ET城乡工矿居民用地 $\approx$ $E T _ { ☉ \mathrm { f l f } }$ 。成果对区域遥感 $E T$ 精准估算研究具有一定参考意义。

结合本文研究结论，对METRIC模型估算区域ET面临的干湿限提取问题有如下认识和思考： $\textcircled{1}$ 植被覆盖良好、水分充足的区域或开放的水体是潜在的“湿点”，“湿点”像元的地表净辐射量与土壤热通量差值几乎全部转化成了潜热通量，使用此类方法的前提是，研究区必须存在符合“湿点”要求或标准的像元。 $\textcircled{2}$ 目前研究者受认知背景和下垫面条件的影响，干湿点选取标准尚未统一，易出现因空间歧义导致的 $E T$ 估算误差。本文提取模型所需的干湿限是基于 $T _ { \mathrm { s } }$ 和 $L A I$ 相关趋势图，但估算的ET精度仍有提高的潜力。笔者认为，深入研究干湿限内涵和标准，并讨论影响干湿限分布的主控因子，能对模型的发展起到帮助，这也是我们下一步研究工作的重点。

致谢：特别感谢内蒙古锡林郭勒草原生态系统国家野外科学观测研究站陈世苹研究员在涡度相关系统水汽通量数据等方面提供的帮助。

# 参考文献（References）:

[1]Allen R G,Pereira L S,Raes D,et al. Crop Evapotranspiration; Guidelines for Computing Crop Water Requirements[C]//FAO Irrigation and Drainage Paper 56.Rome:Food and Agriculture Organization of the United Nations,1998.   
[2]Maria P M,Abel S,Javier F,et al.A review of water scarcity and drought indexes in water resources planning and management[J]. Journal of Hydrology,2015,527:482-493.   
[3]金翠,张柏,宋开山,等.土地利用/覆被变化对区域蒸散发影 响的遥感分析——以吉林省乾安县为例[J].干旱区研究, 2009,26(5）:734-743.[Jin Cui,Zhang Bai,Song Kaishan,et al.RS-based analysis on the effects of land use/cover change on regional evapotranspiration:A case study in Qian'an county,Jilin province[J].Arid Zone Research,2009,26(5） :734-743.]   
[4]Rana G,Katerji N.Measurement and estimation of actual evapotranspiration in the field under Mediterranean climate：A review [J].European Journal of Agronomy,2000,13(2-3）:125-153.   
[5]HowellTA,Schneider A D,Jensen M E.History of lysimeter design and use for evapotranspiration measurements[C]//Allen R G,Howell TA,Pruitt W O,et al.Proceeding of the International Symposium on Lysimetry.New York:American Society of Civil Engineers,1991:1-9.   
[6]Bowen IS.The ratio of heat losses by conduction and evaporation from any water surface[J].Physical Review,1926,27(6）:779 - 798.   
[7]Thornthwaite C W,Holzman A.Report of the commutation on transpiration and evaporation[J]. Transactions of the American Geophysical Union,1944,25:683-693.   
[8]Thornthwaite C W.An approach towards a rational classification of climate[J].Geographical Review,1948,38:55 -94.   
[9]Massman WJ,Lee X.Eddy covariance flux corrections and uncertainties in long-term studies of carbon and energy exchanges[J]. Agricultural and Forest Meteorology,2002,113(1-4）:121-144.   
[10]Wang T,Ochs GR,Cliford SF.A saturation-resistant optical scintillometer to measure[J].Journal of Optical Society of America, 1978,68(3) :334-338.   
[11］王婧,刘廷玺,雷慧闽,等.基于涡度相关的半干旱区沙丘－草

甸水热通量对比分析[J].干旱区研究，2016，33（3）：593- 600.[Wang Jing,Liu Tingxi,LeiHuimin,etal.Heat and water vapor fluxes of dune-meadow landscape in semiarid area based on eddy covariance measurements[J].Arid Zone Research,2O16,33 (3):593 -600.]

[12]赵文智，吉喜斌，刘鹄.蒸散发观测研究进展及绿洲蒸散研究展望[J].干旱区研究,2011,28（3）：463-470.［ZhaoWenzhi,Ji Xibin,Liu Hu.Progresses in evapotranspiration research and

prospect in desert oasis evapotranspiration research[J]. Arid Zone Research,2011,28(3） :463 -470.]   
[13］崔俊杰,白洁,郑磊,等.新疆地区遥感、融合和陆面模式模拟 的蒸散产品的不确定性分析[J].干旱区研究,2018,35（3)： 597 -605.[Cui Junjie,Bai Jie,Zheng Lei,et al. Uncertainty of evapotranspiration products based on fusion of multi-source remote sensing data and land surface modes in Xinjiang[J].Arid Zone Research,2018,35(3） :597 -605.]   
[14］刘钰,彭致功.区域蒸散发监测与估算方法研究综述[J].中国 水利水电科学研究院学报,2009,7（2）:96－104.[Liu Yu, Peng Zhigong.A review of monitoring and estimating methods for regional evapotranspiration[J].Journal of China Institute of Water Resources and Hydropower Research,2009,7(2):96 -104.]   
[15］冯景泽,王忠静.遥感蒸散发模型研究进展综述[J].水利学 报,2012,43（8）:914-925.[Feng Jingze,Wang Zhongjing.A review on evapotranspiration estimation models using remotely sensed data[J]. Journal of Hydraulic Engineering,2012,43（8）:914 - 925.]   
[16]Bastiaanssen WG M,Menenti M,Feddes R A,et al.A remote sensing surface energy balance algorithm for land（SEBAL）1.formulation[J]. Journal of Hydrology,1998,212-213:198-212.   
[17]Bastiaanssen W G M,Pelgrum H,Wang J,et al. A remote sensing surface energy balance algorithm for land（SEBAL）2.validation [J]. Journal of Hydrology,1998,212-213:213-229.   
[18]Allen R G,Tasumi M,Trezza R. Satelite-based energy balance for mapping evapotranspiration with internalized calibration（METRIC）model[J]. Journal of Irrigation and Drainage Engineering, 2007,133(4) :381 -394.   
[19]González-Dugo M,Gonzalez-Piqueras J,Campos I,et al. Estimation of surface energy fluxes in vineyard using field measurements of canopy and soil temperature[J]. Remote Sensing and Hydrology, 2012,352 :59 - 62.   
[20]Wright JL. New evapotranspiration crop coeficients[J]. Journal of the Irrigationand Drainage Division,1982,108:57 -74.   
[21］杨肖丽,任立良,袁飞,等.利用 SEBAL 模型对沙拉沐沦河流 域蒸散发的分析[J].干旱区研究,2010,27（4）：507-514. [Yang Xiaoli,Ren Liliang,Yuan Fei,etal. Study on evapotranspiration in the Shalamulun River basin using SEBAL model and MODIS data[J]. Arid Zone Research,2010,27(4) :507-514.]   
[22]Tasumi M.Progress in Operational Estimation of Regional Evapotranspiration Using Satellite Imagery[D].Moscow: University of Idaho,2003:96-101.   
[23]Qin Z H,Karnieli A,Berliner P.A mono-window algorithm for retrieving land surface temperature from Landsat TM data and its application to the Israel-Egypt border region[J].International Journal of Remote Sensing,2012,22(18):3 719 -3 746.   
[24]Chen SP,Chen JQ,Lin G H,et al.Energy balance and partition in Inner Mongolia steppe ecosystems with different land use types [J]．Agricultural and Forest Meteorology，2009,149（11）: 1 800 -1 809.

[25]Kalma JD,Mcvicar TR,Mccabe MF.Estimating land surface evaporation:A review of methods using remotely sensed surface temperature data[J].Surveys in Geophysics,2008,29(4-5）,421 - 469.

# Dry-Wet Edge Based on Land Surface Temperature and Leaf Area Index and Estimation of Regional Evapotranspiration

WANGJun123，LIHe-ping1,23，LUHai-yuan1,23，ZHANG Rui-qiang ng1,2,3， CAO Xue-song' 1,2,3 (1.Institute of Water Resources for Pastoral Area，China Institute of Water Resources and Hydropower Research, Hohhot O10020，Inner Mongolia，China; 2.Instituteof Water Resources for Pastoral Area，Ministryof Water Resources，Hohhot O1002O，Inner Mongolia，China; 3.State Key Laboratory of Simulation and Regulation of Water Cycle in River Basin， Beijing l0038，China)

Abstract：The METRIC model was chosen to reveal the spatial ambiguity issue encountered during the calculation of regional evapotranspiration $( E T )$ by remote sensing energy balance method. The study was based on the trend graph of surface temperature $( T _ { \mathrm { s } } )$ and leaf area index $( L A I )$ . The dry pixel was chosen as the bare soil area where the $T _ { \mathrm { s } }$ frequency histogram accounted for the top $5 \%$ of the high-temperature region，and the $L A I$ frequency histogram accounted for $5 \%$ of the region. The wet pixel was chosen as the wetland or farmland where the $T _ { \mathrm { s } }$ frequency histogram accounted for the last $5 \%$ of the low-temperature region，and the $L A I$ frequency histogram accounted for the top $5 \%$ of the region. After that，the measured data of the eddy covariance system were used to verify the estimation accuracy of the model. The results showed that the average estimation accuracy of evapotranspiration in he calibration period and verification period was $1 5 \%$ ，which was relatively reasonable compared with the previous research results.The selection schemecould help the Mapping Evapotranspiration with Internalized Calibration (METRIC）model to subjectively determine the dry-wet edge.The evapotranspiration values of diferent land use typeswere calculated，and they were in an order of $E T _ { \mathrm { w a t e r } } > E T _ { \mathrm { f o r e s t } } > E T _ { \mathrm { a r a b l e l a n d } } > E T _ { \mathrm { u n u s e d l a n d } } >$ （204号 $E T _ { \mathrm { u r b a n } }$ and rurali dusia a $\approx E T _ { \mathrm { g r a s s l a n d } }$ ，which could berefered in researchingthe precision estimationof regional remote sensing evapotranspiration.

Key words:evapotranspiration；METRIC model；dry-wet edge； surface temperature；leaf area index； InnerMongolia