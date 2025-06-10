# 基于SEBS模型的精河流域蒸散发研究

郑倩倩¹，代鹏超²，张金燕¹，毋兆鹏1.3(1.新疆师范大学地理科学与旅游学院,新疆 乌鲁木齐830054；2.乌鲁木齐气象卫星地面站，新疆 乌鲁木齐830054；3.新疆干旱湖泊环境与资源实验室,新疆 乌鲁木齐830054)

摘要：以干旱区生态脆弱区精河流域为研究区,选取1990—2016年气象观测日值数据及对应时期Landsat系列影像六景，基于地表能量平衡系统模型方法,对1990—2016年蒸散发的时空格局进行了研究。结果表明：（1）在全球升温的大背景下,近26a来研究区蒸散发整体呈增加趋势,Morlet小波分析显示存在5a、7a、13a尺度变化周期。（2）研究区蒸散发量在空间呈现南高北低特征,蒸散发减少区域在东北未利用地，蒸散发显著增加区域在艾比湖西北部和南部山区。（3）不同土地利用类型下的蒸散发量由高至低为：林地 $>$ 水体 $>$ 草地 $>$ 耕地 $>$ 建设用地 $>$ 未利用地。4）与地表蒸散发表现出高度正相关的气象因素为风速，地表参数为高程(DEM)与地表比辐射率(ε);与地表蒸散发表现出高度负相关的气象因素为近地表空气相对湿度,地表参数为温度植被干旱指数(TDVI)与地表温度 $( T _ { s } )$ 。

关键词：SEBS模型；蒸散发；时空格局；精河流域；新疆

地表蒸散发是陆面水循环中最重要的水文过程之一，也是联系植物气孔行为、碳交换和水分利用的关键生态过程，同时也是土壤一植被一大气联系体（SPAC,Soil-Plant-Atmosphere Continuum）中水分运动的重要连接桥梁[。地表蒸散量的估算不仅是流域水资源评价、管理和调控的重要依据，而且它的变化还影响区域和全球的水文循环[2]

早在1802年Dalton利用包含温度、湿度和风速的蒸发公式估算地表蒸散发以来，更多学者先后提出波文比-能量平衡法[3]、蒸散空气动力学方法[4]、Penman-Monteith(P-M)模型[5等一系列蒸散发观测法和计算方法。20世纪70年代后，伴随着遥感技术的快速发展，实现了蒸散发研究点到面的突破，并涌现出了许多蒸散发估算的空间遥感模型，如地表能量平衡指数SEBI模型、陆面能量平衡算法(SE-BAL,Surface Energy Balance Algorithm for Land）[7]地表能量平衡系统（SEBS,SurfaceEnergyBalanceSystem)[等。其中,SEBS模型充分考虑干、湿两种极端状况，尤其是针对干旱区水分和能量分布不均的特点，能在具备更明确物理概念的同时，有效提高蒸散量遥感估算精度。因此，近年来在国内外得以较广泛应用[9]。

精河流域作为艾比湖流域的一部分，是新疆生态环境最脆弱的地区之一，在全球变暖的大背景下，多年径流水资源不断减少，引发一系列生态环境问题，精确估算区域内蒸散发情况可为优化水资源配置提供依据。相关学者多运用参考作物计算法研究艾比湖蒸散量的时空变化特征及其对不同气象因子的敏感性[10-11];郭家新等[12]根据水热平衡原理构建TVETI蒸散指数反演艾比湖流域地表蒸散发；张晓玉等[13]结合MODIS数据和气象观测数据，利用SEBS模型估算艾比湖流域的地表蒸散发。但对其子流域一精河流域的蒸散发动态变化及其机理研究较少，本文借助定量遥感手段结合SEBS模型，估算精河流域地表通量及日蒸散发量，运用Morlet小波分析、重心迁移等方法分析蒸散发的动态时空变化规律和特征，从而探索该模型在复杂地表条件下的适用性。

# 1研究区及数据

# 1.1 研究区概况

精河流域 $\langle 8 1 ^ { \circ } 0 7 ^ { \prime } 5 2 ^ { \prime \prime } { \sim } 8 3 ^ { \circ } 0 5 ^ { \prime } 4 8 ^ { \prime \prime } \mathrm { E }$ $4 4 ^ { \circ } 0 0 ^ { \prime } 2 1 " .$ ）$4 5 ^ { \circ } 0 0 ^ { \prime } 5 6 ^ { \prime \prime } \mathrm { N } .$ )位于新疆天山支脉婆罗科努山北麓，准噶尔盆地西南边缘。地势南高北低，平均海拔320$\mathbf { m }$ ,夏季降水量稀少，冬季干燥寒冷，大陆性气候特征显著。区内风沙天气多，持续时间长，日照充足，年日照率 $6 1 \% \sim 6 4 \%$ ,夏季平均日照时数在 $^ { 1 0 \mathrm { { h } } }$ 以上，干燥的气候和活跃的大风天气，决定了研究区丙强烈的蒸散发，是我国西北干旱区生态环境严重退化的典型区域之一(图1)。

![](images/18ee36c1db64dcd3a82c5a2a2148c99c0efd16bd3e52e520e37c4572d7ccb659.jpg)  
图1研究区示意图

# 1.2数据来源

气象资料来自中国气象局气象数据中心网站(http://data.cma.cn），实际观测数据选取中国地面国际交换站精河气象站(站点编号：51334)日值数据，时间起止为1990年1月1日至2016年12月31日。

空间遥感数据来自中国地理空间数据云(http://www.gscloud.cn）,分别是Landsat-5TM的1990年、1994年、1998年影像数据;Landsat-7ETM $^ +$ 的2002年、2007年、2011年影像数据;Landsat-8 OLI_TIRS的2013年、2016年影像数据，月份均为9月（秋季），空间分辨率 $3 0 \mathrm { ~ m ~ }$ ，轨道号：P146/R029，云量均低于$1 0 \%$ 。基础影像预处理及空间建模分析、图形处理分别用ENVI5.1、ArcGIS10.1软件进行操作，其中基于TM-destripe工具对来源于Landsat-7ETM $^ +$ 的3期问题影像进行了条带修复处理。

# 2SEBS模型机理

基于地表能量平衡系统(SEBS)，由荷兰学者Su于2002年提出[8]。模型理论包括三个部分：一是地表物理参数反演，主要包括地表反照率、地表比辐射率、地表温度、归一化植被指数(NDVI)、地表粗糙度；二是热传导粗糙度长度运算，主要包括参考高度下的气压、温度、湿度和风速，其中参考高度用大气尺度气象模型估算；三是蒸发比计算，主要包括向下的太阳辐射和长波辐射(图2)。

模型的数学基础为地表能量平衡方程[13-15]（式1）：

$$
\lambda E { = } R _ { { \scriptscriptstyle n } } { - } G { - } H
$$

式中： $\lambda E$ 为潜热通量( $\mathrm { W } \cdot \mathrm { m } ^ { - 2 } ,$ ； $R _ { n }$ 为地表净辐射通

![](images/219c5931fc8345c745d13f8c05bff48b658dc3a40f4c602457457055ead14daf.jpg)  
Fig.1 Location map of study area   
图2 SEBS模型技术流程图  
Fig.2 Technical flow chart of SEBS model

量 $\mathrm { W } \cdot \mathrm { m } ^ { - 2 } ,$ ） $H$ 为感热通量 $\left( \mathbb { W } \cdot \mathbf { m } ^ { - 2 } \right.$ ）； $G$ 为土壤热通量 $\left( \mathbb { W } \cdot \mathbf { m } ^ { - 2 } \right)$ 0

地表净辐射通量的计算方法[16(式2)：

$$
R _ { \mathfrak { n } } = ( 1 - \alpha ) R _ { \mathfrak { s } } + ( R _ { \mathfrak { L } } ^ { \downarrow } - R _ { \mathfrak { L } } ^ { \uparrow } ) - ( 1 - \varepsilon ) R _ { \mathfrak { L } } ^ { \downarrow }
$$

式中： $R _ { n }$ 为地表净辐射通量( $\mathrm { W } \cdot \mathrm { m } ^ { - 2 } .$ ） $R _ { s }$ 为入射的短波辐射量 $\left( \mathbb { W } \cdot \mathbf { m } ^ { - 2 } \right) ; \mathbf { \alpha }$ 为地表反照率； $R _ { L } ^ { \downarrow }$ 为入射的长波辐射量 $\left( \mathbb { W } \cdot \mathbf { m } ^ { - 2 } \right)$ ； $R _ { L } ^ { \uparrow }$ 为向外的长波辐射量！ $\left( \mathbb { W } \cdot \mathbf { m } ^ { - 2 } \right)$ ：$\boldsymbol { \varepsilon }$ 是地表比辐射率。其中入射的短波辐射是利用太阳常数、太阳入射角、相对日地距离和大气单向透过率计算；入射的长波辐射由改进的史蒂夫·波尔兹曼定律估算而来(式3)；向外的长波辐射采用StefanBoltzmann方程，通过地表比辐射率和地表温度计算(式4)。

$$
R _ { L } ^ { \downarrow } = 1 . 0 8 { \left( - \ln { \tau _ { s w } } \right) } ^ { 0 . 6 2 5 } \sigma T _ { a } ^ { 4 }
$$

$$
R _ { L } ^ { \uparrow } = \varepsilon \sigma T _ { s } ^ { 4 }
$$

式中： $\boldsymbol { \tau } _ { s w }$ 为大气单向透过率； $\sigma$ 为史蒂夫·波尔兹曼常数 $\left[ 5 . 6 7 { \times } 1 0 ^ { - 8 } \mathrm { W } { \cdot } \left( \mathrm { m } ^ { - 2 } \cdot \mathrm { K } ^ { - 4 } \right) \right]$ $T _ { a }$ 为空气温度(K);$T _ { s }$ 为地表温度(K)。其中空间空气温度数据由地表温度的中纬度修正函数获得。

土壤热通量的计算方法(式5)：

$$
G = R _ { { \scriptscriptstyle n } } [ \Gamma _ { { \scriptscriptstyle c } } + ( 1 - F _ { { \scriptscriptstyle c } } ) ( \Gamma _ { { \scriptscriptstyle s } } - \Gamma _ { { \scriptscriptstyle c } } ) ]
$$

式中： $\Gamma _ { c }$ 为全植被覆盖下土壤热通量占净辐射的比$( \Gamma _ { c } { = } 0 . 0 5 )$ ； $\Gamma _ { c }$ 裸土下土壤热通量占净辐射的比（ $\Gamma _ { c } = 0 . 3 1 5 ^ { \prime }$ ； $\boldsymbol { F _ { c } }$ 为植被覆盖度，通过归一化植被指数(NDVI)计算(式6)。

$$
F _ { _ c } = \frac { \mathrm { N D V I - N D V I } _ { \operatorname* { m i n } } } { \mathrm { N D V I } _ { \operatorname* { m a x } } - \mathrm { N D V I } _ { \operatorname* { m i n } } }
$$

感热通量计算较为复杂，是把地表参数和大气边界层参数平均风速和平均温度、地表位温差等结合，通过整体参数化求解,最终获得摩擦风速 $( \mu _ { * } )$ 、莫宁霍夫长度 $( L )$ 、感热通量 $( H )$ 。

$$
\mu = \frac { \mu _ { * } } { k } \biggl [ \ln \biggl ( \frac { z - d _ { 0 } } { z _ { 0 m } } \biggl ) - \Psi _ { m } \biggl ( \frac { z - d _ { 0 } } { L } \biggl ) + \Psi _ { m } \biggl ( \frac { z _ { 0 m } } { L } \biggl ) \biggr ]
$$

$$
L = - \frac { \rho c _ { _ { p } } \mu _ { * } ^ { 3 } \theta _ { \it { v } } } { k g H }
$$

$$
H = k \mu _ { * } \rho C _ { P } ( \theta _ { \mathrm { 0 } } - \theta _ { \mathrm {  a } } )
$$

$$
\left[ \ln \left( { \frac { z - d _ { 0 } } { z _ { 0 h } } } \right) - \Psi _ { h } \left( { \frac { z - d _ { 0 } } { L } } \right) + \Psi _ { n } \left( { \frac { z _ { 0 h } } { L } } \right) \right] ^ { - 1 }
$$

式中： $\mu _ { * }$ 为摩擦风速 $\left( \mathbf { m } { \cdot } \mathbf { s } ^ { - 1 } \right)$ $k$ 为卡门常数( $\scriptstyle \overbrace { k = 0 . 4 1 } .$ ；$z$ 为参数测量高度 $( \mathbf { \Phi } _ { \mathrm { m } } ) { \bf { ; } } d _ { 0 }$ 为零平面位移高度 ${ \mathrm { ( } } { \mathrm { m } } { \mathrm { ) } } ; z _ { 0 m }$ 为动量交换粗糙度长度 $\left( \mathbf { \Phi } _ { \mathrm { m } } \right) ; z _ { 0 h }$ 为热量交换粗糙度长度 $\mathrm { ( m ) }$ $L$ 为莫宁-奥布霍夫长度 $\mathrm { ( m ) }$ $\Psi _ { { m } }$ 和 $\Psi _ { h }$ 分别为动量交换和热量交换MOS稳定度订正的数 $_ { ; \rho }$ 为空气密度 $\left( \mathbf { k g } \cdot \mathbf { m } ^ { - 3 } \right)$ ; $C _ { p }$ 为空气定压比热容 $\left( \mathbf { J } { \cdot } \mathbf { k } \mathbf { g } ^ { - 1 } { \cdot } \mathbf { K } ^ { - 1 } \right)$ （204号（ $C _ { p } { = } 1 0 0 5$ ； $\theta _ { 0 }$ 和 $\theta _ { a }$ 分别为地表位温(K)和参数测量高度 $z$ 处的大气位温(K)。

蒸散比的计算过程中假设：

$\textcircled{1}$ 假设在极端干旱状态下，地表无蒸散发，潜热通量为0,则：

$$
H _ { d } = R _ { n } - G
$$

$\textcircled{2}$ 假设在极端湿润状态下，水分充足，感热通量趋近于0,此时蒸散发速率最大，则：

$$
H _ { \scriptscriptstyle w } = R _ { \scriptscriptstyle n } - G - \lambda E _ { \scriptscriptstyle w }
$$

$$
L _ { _ w } = { \frac { \rho \mu _ { \ast } ^ { 3 } } { k g 0 . 6 1 ( R _ { _ n } - G ) / \lambda } }
$$

$$
r _ { e w } = \frac { 1 } { k \mu _ { * } } \biggl [ \ln \biggl ( \frac { z - d _ { 0 } } { z _ { 0 h } } \biggr ) - \Psi _ { h } \biggl ( \frac { z - d _ { 0 } } { L _ { w } } \biggr ) + \Psi _ { h } \biggl ( \frac { z _ { 0 h } } { L _ { w } } \biggr ) \biggr ]
$$

综合 $\textcircled{1} , \textcircled{2}$ ,蒸散比 ${ \bf \Xi } ( { \bf \Lambda } \Lambda { \bf \Lambda } )$ 的计算公式可表示为（式15）：

$$
\Lambda _ { _ r } = 1 - { \frac { H - H _ { _ w } } { H _ { d } - H _ { _ w } } }
$$

$$
\Lambda = \frac { \lambda E } { R _ { _ n } - G } = \frac { \Lambda _ { _ r } \lambda E _ { _ w } } { R _ { _ n } - G }
$$

式中： $\Lambda$ ，为相对蒸散比； $H _ { d }$ 为极端干旱条件下的感热通量; $H _ { w }$ 为极端湿润条件下的感热通量； $\lambda E _ { \scriptscriptstyle w }$ 为湿润条件下的潜热通量； $L _ { w }$ 为极端湿润条件下奥布霍夫长度； $r _ { e w }$ 为极端湿润条件下外部阻抗。

最终日蒸散发估算借助蒸散比完成：

$$
E T _ { _ { \mathrm { d a y } } } = 8 . 6 7 \times 1 0 ^ { 7 } \times \Lambda _ { _ { i n s } } \times { \frac { R _ { _ { \mathrm { n d a y } } } } { \lambda \rho } }
$$

式中： $E T _ { \mathrm { d a y } }$ 为日蒸散量； $\Lambda _ { i n s }$ 为瞬时蒸发比， $\Lambda _ { \it { i n s } } =$ Λ; $R _ { \mathrm { n d a y } }$ 为日净辐射通量； $\lambda$ 为气化潜热； $\rho$ 为大气密度。

SEBS所采用的动量粗糙度模型适用于分布均匀的低矮植被。因地区、土地覆被类型等条件的不同，会导致地表粗糙度存在明显差异，进而对模型模拟精度产生较大影响。本研究根据研究区植被覆盖的实际情况，基于二阶闭合理论，对动量粗糙度长度( $z _ { 0 m }$ ）零平面位移( $d _ { \mathrm { o } }$ )的计算进行调整，以减少因地表植被分布不均引起的蒸散发反演的不确定性。其中动量粗糙度长度的计算区分部分植被覆盖和完全植被覆盖两种情况(式17);零平面位移借助叶面积指数计算(式18)。

$$
z _ { _ { 0 m } } = \left\{ \begin{array} { l l } { { z _ { 0 s } + 0 . 3 h ( C _ { d } \cdot \mathrm { L A I } ) ^ { 1 / 2 } , ( 0 { \leqslant } \mathrm { L A I } \leqslant 1 ) } } \\ { { 0 . 3 h \biggl ( 1 - \displaystyle \frac { d _ { 0 } } { h } \biggr ) , ( 1 < \mathrm { L A I } < 7 . 5 \ ) } } \end{array} \right.
$$

$$
d _ { \mathrm { o } } = 1 . 1 \ln \bigl [ 1 + \bigl ( C _ { d } \mathrm { L A I } \bigr ) ^ { 1 / 4 } \bigr ]
$$

式中： $h$ 为冠层高度; $z _ { 0 s }$ 底层粗糙长度,取0.01; $C _ { d }$ 为叶片拖拽系数，取0.2;LAI为叶面积指数，可利用植被覆盖度获取。

# 3精度验证

对于本研究模型结果的验证，主要采用"点"和“面”[17-18]相结合的方法。“点"验证主要通过精河气象站点的日实测蒸发数据完成(表1)。其中，对比蒸发血数据，SEBS模型蒸散量的平均误差率为 $- 8 . 3 9 \%$ ;对模型中地表参数的验证，地表温度、大气温度的平均误差率分别为 $1 1 . 2 2 \% , 1 2 . 7 9 \%$ □

表1SEBS模型精度验证结果  
Tab.1 SEBS modelaccuracyverificationresults   

<html><body><table><tr><td>日期</td><td>蒸发皿 (E601B)/mm</td><td>SEBS 蒸散量/mm</td><td>相对 误差/%</td><td>实测地表 温度/C</td><td>遥感反演 地表温度/C</td><td>相对 误差/%</td><td>实测大气 温度/C</td><td>遥感反演 大气温度/℃</td><td>相对 误差/%</td></tr><tr><td>1990-09-05</td><td>2</td><td>1.706</td><td>-14.72</td><td>17.3</td><td>19.939</td><td>13.23</td><td>15.6</td><td>14.647</td><td>-6.11</td></tr><tr><td>1994-09-30</td><td>2.1</td><td>2.099</td><td>-0.03</td><td>18.5</td><td>19.822</td><td>6.67</td><td>6.2</td><td>13.74</td><td>-15.19</td></tr><tr><td>1998-09-25</td><td>2.8</td><td>2.336</td><td>-16.56</td><td>19.8</td><td>22.771</td><td>13.05</td><td>18.2</td><td>14.621</td><td>-19.66</td></tr><tr><td>2002-09-28</td><td>2.8</td><td>2.741</td><td>-2.13</td><td>19.1</td><td>23.265</td><td>17.9</td><td>17.6</td><td>16.815</td><td>-4.46</td></tr><tr><td>2007-09-10</td><td>4.1</td><td>3.701</td><td>-9.73</td><td>27.7</td><td>25.254</td><td>-9.68</td><td>21.5</td><td>20.235</td><td>-5.88</td></tr><tr><td>2011-09-05</td><td>4.4</td><td>4.254</td><td>-3.31</td><td>28.1</td><td>24.329</td><td>-15.5</td><td>23.5</td><td>19.432</td><td>-17.31</td></tr><tr><td>2013-09-18</td><td>3.5</td><td>3.48</td><td>-0.59</td><td>18.5</td><td>19.776</td><td>6.45</td><td>16.6</td><td>22.158</td><td>25.08</td></tr><tr><td>2016-09-25</td><td>2.7</td><td>2.389</td><td>-11.52</td><td>29.12</td><td>31.406</td><td>7.28</td><td>23.65</td><td>25.689</td><td>8.62</td></tr></table></body></html>

“面"的验证过程中，由于Penman-Monteith模型具有很好的物理基础，作为统一的标准计算方法，无需进行地区校正和改变任何参数即可适用于世界各地,且具有较高精度和良好可比性[19-20],故在参考“点"验证结果的基础上，将Penman-Monteith模型、SEBS模型反演的区域整体蒸散发结果进行对比验证，结果表明SEBS模型呈现的多年趋势与Pen-man-Monteith模型数据较为一致（图3），能够很好的适用于精河地区。

4.5 -P-M -SEBS4.0 线性(P-M) -线性(SEBS)3.5022 y=0.3314x+0.8959R²=0.8021.0 y=0.2277x+0.42470.5 R²=0.587101990 1994 1998 2002 2007 2011 2013 2016年份

# 4蒸散发时空变化

# 4.1蒸散发时间变化

研究区模型反演日蒸散量在26a间整体呈增加趋势，表现为 $1 . 0 3 5 \ \mathrm { m m } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ 。其中，1990年至1998年变化浮动小,均值分别为 $1 . 5 \mathrm { m m } , 1 . 6 4 7 \mathrm { m m }$ 、$1 . 4 1 ~ \mathrm { m m }$ ;在1998一2011年有显著增加，均值增加$1 . 8 9 \mathrm { m m }$ ;主要体现在艾比湖湖区、南部及东南部山区、精河流域中上游平原区。2011—2013年减少，均值减少 $0 . 8 2 1 ~ \mathrm { m m }$ ;2013—2016年再次增加，均值增加 $1 . 3 1 6 \mathrm { m m }$ （图4）。

为了解研究区蒸散发变化的周期特征，利用精河气象站(站点编号：51334)1990—2016年历史观测数据，计算Morlet小波系数并绘制小波方差图及小波系数实部等值线图。小波方差图显示，在1990—2016年研究期内有3个峰值,分别在5a、7a、13a的时间尺度上(图5)。其中，13a大尺度周期对照图6周期震荡特征非常明显，经历了7个正负循环交替过程，且2014年出现的正等值线至2016年尚未闭合，表明未来一段时间内蒸散量将会偏高，既印证了前述研究期内的蒸散发特征，又表现出研究区未来蒸散发持续增高的趋势。7a时间尺度上的小波方差值略高于5a时间尺度，从图6中可以看出，7a尺度的周期变化下同时嵌套了5a的周期震荡，说明精河流域蒸散发存在不同尺度周期的复杂嵌套结构，即小尺度变化嵌套在大尺度的变化下，这与其他学者研究一致[21-23]

![](images/b73cef8d5c76b23971296cbfb2e54ba3d63d3ae2adf7ca14b82a9cacb9dcb168.jpg)  
Fig.4Spatial distribution of evapotranspiration in remote sensing inversion in the study area

![](images/a0d058ee870cccd9e89d219ce9768e7e6d6ac9a688a3fa29dae244c4d17fbd57.jpg)  
图4研究区遥感反演蒸散量空间分布  
Fig.5Waveletvariance diagram

# 4.2土地利用类型影响下的蒸散发空间特征

研究区蒸散发空间分布不均衡，湖泊、河流上下游、山地的蒸散量差异明显，基本呈现南高北低的空间分布特征，即南部林地出现相对高值，北部除艾比湖区为高值区外，干裸的未利用地出现最低值。由图7可知，蒸散发增加及基本不变区域所占面积最多，达 $7 4 . 5 4 \%$ ，主要集中在北部湖区、中部绿洲区及南部山区；蒸散发减少区域主要集中在东北部未利用地，所占面积为 $2 5 . 4 6 \%$ O

![](images/fbffbbc398549ac1779a573f64e782bb27eb9b184e32c455220ca0350867bc8f.jpg)  
图5小波方差   
图6小波系数实部等值线  
Fig.6Real coefficient contour of wavelet coefficients

![](images/f57c39f78371c74ad50e410565ce1e2c135b98013ac15621e3e7dfcdf2119797.jpg)  
图7近26a研究区蒸散发空间变化趋势  
Fig.7Trend of evapotranspiration in the near 26 years study   
图8近26a研究区各土地利用类型空间重心迁移  
Fig.8Migration of the spatial center of gravity of various land use types in the near26 years study area

area

参考中国土地资源分类系统[24]，对研究区进行土地利用分类。在借助重心迁移模型[25]明确了研究区近26a不同土地利用类型的空间重心迁移特征基础上(图8)，对比分析了研究区蒸散发空间变化趋势(图7)。结果表明：近 $2 6 \mathrm { a }$ ,耕地、林地、草地均呈现向东的迁移趋势，耕地整体向东迁移 $4 . 9 9 \mathrm { k m }$ 而林、草地呈现向东南方向的迁移趋势，分别迁移$1 3 . 9 6 \ \mathrm { k m } \setminus 1 0 . 3 7 \ \mathrm { k m }$ ，使蒸散发轻微增加区域集中分布在艾比湖湖区及其以南的水域充沛区域。蒸散发呈现高值的水体，向西北方向迁移 $7 . 2 1 \ \mathrm { k m }$ ，因而使蒸散发显著增加的区域主要出现在艾比湖西北部。蒸散发呈现低值的建设用地、未利用地有明显的分异。其中，由于绿洲城市的扩张，建设用地整体向西南方向迁移 $2 3 . 6 7 ~ \mathrm { k m }$ ,未利用地呈现向东北方向的迁移趋势，共迁移 $3 . 0 8 \mathrm { k m }$ ，导致蒸散发减少区域主要发生在东北未利用地和中部托里乡旦达嘎沙漠。

# 5驱动因子分析

# 5.1自然驱动因子

蒸散发作为表征气候的因子之一，其变化决定于与其相关的气象因子的共同作用结果。为定量分析各个气象因子对蒸散发变化的贡献，对气温、相对湿度、降水量、风速、太阳辐射、日照时数及日较差进行了相关性分析(表2)。

针对研究区地表蒸散发而言，由于研究区西北部阿拉山口的存在，风速与其有着最高的正相关性，而近地面空气相对湿度则对其表现出最高的负相关影响。需要强调的是，气温相较于其他气象因子与研究区蒸散发正相关性的显著水平虽然较低，但由于其决定着空气中饱和水汽含量和水汽扩散的速度，因此对蒸散发的直接影响仍不可忽视。联合国政府间气候变化专门委员会(IPCC)的报告显

44.0000 4444 1990 44444444 2002 2016  
(a)林地 (b)草地 (c)水体  
10.814410.01144 1994 19982013 2011 4440 2011 2016 24231  
1990 2002 2007 2016 20021998 20137 20112007·年份 10.81 ·年份 4422 ·年份 19940 3km 0 2.5km 0 1.5km 2013L √ 1994 1998  
82°52'0"E 82°56'0"E 83°0'0"E 82°46'30"E 82°50'20"E 82°54'10"E 82°52'30"E 82°55'0"E 82°57'30"E  
(d)耕地 10.040 (e)建设用地 145214 1994 (f)未利用地  
10.9004 2002 1994 201990 2016,  
1994 2007 10.904 20112007 1998 1004104 20072011  
21023t4 1990 ·年份 2016 2016 2013 。年份km 2213100 ·年份998 1990 20020 1 km 0 2 kmL 2013  
82°37'30"E 82°39'0"E 82°40'30"E 82°43'20"E 82°50'0"E 82°56'40"E 82°55'30"E 82°57'40"E

表2实际蒸散量与气象参数相关性分析  
Tab.2 Correlation analysis between actual evapotranspiration and meteorological parameters   

<html><body><table><tr><td></td><td>气温</td><td>相对湿度</td><td>降水量</td><td>风速</td><td>太阳辐射</td><td>日照时数</td><td>日较差</td></tr><tr><td>实际蒸散量</td><td>0.634*</td><td>-0.796**</td><td>-0.337**</td><td>0.823**</td><td>0.804**</td><td>0.765*</td><td>0.796**</td></tr></table></body></html>

注：\*、\*\*分别表示在0.05和0.01水平上显著相关。

示[26],2015—2019年，全球平均气温较工业化前时代升高了 $1 . 1 ~ \mathrm { { ^ { \circ } C } }$ ;对研究区而言，近60a的平均气温以 $0 . 3 3 ~ \mathrm { ^ { \circ } C } \cdot ( 1 0 \mathrm { a } ) ^ { - 1 }$ 的气候倾向率呈显著( $\scriptstyle \cdot = 0 . 0 5$ 上升趋势[27]。而反演结果显示出蒸散量在近26a的持续增加，在一定程度上响应了气候变暖的事实。在2013年出现的低值，则主要是由于影像日期前1d的天气过程导致气温与风速均较低所致

选取地表温度 $( T _ { s } )$ 、地表比辐射率 $( \varepsilon )$ 、地面数字高程(DEM)以及温度植被干旱指数(TVDI)4个地表参数，与研究区蒸散发进行相关性分析，结果表明：DEM、地表比辐射率与蒸散发呈正相关关系。其中海拔超过 $5 0 0 \mathrm { ~ m ~ }$ 后，除在 $2 8 0 0 \mathrm { ~ m ~ }$ 处由于天山云杉分布海拔界线会出现小幅度下降外，蒸散发整体随DEM增加呈显著上升。加之，地形能够影响地表辐射能量的吸收状况，故蒸散量也随地表比辐射率的增加而增加。由于研究区未利用地多为岩石、戈壁、盐碱地，植被覆盖率少，地表升温快，因此地表温度与蒸散发呈负相关关系。而TVDI与蒸散发的负相关性，表明了表层土壤水分含水量对蒸散发的显著影响，即土壤水分含水量越少，蒸散发越小(图9)。

# 5.2人为影响因子

不同的土地利用会使土壤湿度和地表温度状况发生改变，进而对区域蒸散发产生影响。由表3可见，近26a研究区建设用地、水体、耕地整体呈增加趋势;林地、草地、未利用地整体呈减少趋势。其中，在人口不断增长及绿洲农业的发展影响下，耕地面积增长迅速，动态度为 $1 2 . 2 4 \%$ ；林草地虽呈减少趋势，但自研究区实施"三北"防护林、退耕还林、等林业重点工程及草原生态保护奖补政策以来，面积逐渐恢复。因此，致使林地、草地、耕地成为蒸散发高值区。由图10可以看出，牲畜数量随人口总数增加，也呈现增加趋势。牲畜数量作为衡量草场合理利用的重要指标，其增长的快慢可直接导致草场面积变化，说明随着人类对大自然改造能力的大幅度提高，能够直接影响下垫面土地覆被的变化，进而在一定程度上影响下垫面的蒸散发变化。

![](images/3428fc3e48eb5363e527ceb40323eea4f0333a6d69bc7c025aa42faa310fff90.jpg)  
图9蒸散发与地表参数的散点图  
Fig.9Scatter plot of evapotranspiration and surface parameters

表31990—2016年研究区土地利用动态度变化  
Tab.3Dynamic changes of land use in the study area from 199o to 201   
1%   

<html><body><table><tr><td>年份</td><td>林地</td><td>水体</td><td>草地</td><td>耕地</td><td>建设用地</td><td>未利用地</td></tr><tr><td>1990—1994</td><td>-0.50</td><td>1.34</td><td>10.32</td><td>2.17</td><td>13.48</td><td>-1.62</td></tr><tr><td>1994—1998</td><td>-7.74</td><td>0.37</td><td>-9.10</td><td>14.58</td><td>1.71</td><td>2.07</td></tr><tr><td>1998—2002</td><td>-7.59</td><td>10.95</td><td>12.43</td><td>12.11</td><td>1.40</td><td>-2.55</td></tr><tr><td>2002—2007</td><td>-0.88</td><td>-8.18</td><td>-1.54</td><td>7.24</td><td>16.21</td><td>0.66</td></tr><tr><td>2007—2011</td><td>1.24</td><td>1.50</td><td>2.82</td><td>1.06</td><td>6.61</td><td>-0.38</td></tr><tr><td>2011—2013</td><td>27.49</td><td>-5.26</td><td>7.18</td><td>10.40</td><td>9.49</td><td>-2.83</td></tr><tr><td>2013—2016</td><td>36.85</td><td>15.31</td><td>-6.43</td><td>-1.51</td><td>14.36</td><td>1.62</td></tr><tr><td>1990—2016</td><td>-0.82</td><td>0.99</td><td>-0.22</td><td>12.24</td><td>18.89</td><td>-0.33</td></tr></table></body></html>

![](images/8f2b9dede0a35f4b02844aaae1eff9592da03e6ab48040436b0d0db4b23d46bc.jpg)  
图10研究区总人口与牲畜数量的关系 Fig.1O The relationship between the total population and the number of livestock in the study area

# 6结语

区域蒸散发受自然和人为因素共同作用的影响，在气候变化导致全球升温的背景下，我国西北诸河流域整体蒸散发增大[28],本文研究的结果同样显示了蒸散发显著增加的事实，并且其时空分布格局也在发生着变化。随着区域经济的发展和城市化进程加快，虽然越来越多的自然生态下垫面被人工下垫面所取代，天然渗透层被不透水层替代，但对蒸散发贡献较少的城市用地仍不可忽视。2012年以来，研究区在践行生态文明和绿色理念的过程中新增城市绿地面积 $0 . 1 2 7 \mathrm { k m } ^ { 2 }$ ，使得建设用地蒸散发逐年增加。

此外还需关注的是，虽然26a间研究区蒸散发整体呈正向发展，但在空间上不均衡，这种变化在有可能促进局部极端水文气象事件发生的同时，也会给水资源管理和极端事件风险管理带来挑战。随着流域频繁的人类活动和过度开采自然资源，至2015年艾比湖水域面积整体呈减少趋势，其中，2006年湖面面积退缩达历年之最[29-30],湖盆裸露，湖区周边植被稀少、未利用地面积增加，使得研究区蒸散发减少区域出现在东北未利用地。但因2007年艾比湖国家级自然保护区的成立及研究区统一管理、优化水资源，实施节水灌溉工程，自2016年起，艾比湖湖面开始恢复，至2017年有 $3 2 8 { \mathrm { ~ k m } } ^ { 2 }$ 湖面面积扩充[30],由此使得研究区显著增加的蒸散发区域出现在了保护区西北部。本文研究结论如下：

(1）在全球气候变暖的背景下，精河流域1990一2016年蒸散发整体呈波动性增加趋势，随时间推移存在着 $5 \mathrm { ~ a ~ . 7 ~ a ~ . 1 3 ~ }$ a的三类尺度的周期变化规律。在空间上基本呈现南高北低的特征，26a间蒸散发减少区域在东北未利用地，蒸散发显著增加区域在艾比湖西北部和南部山区。

(2）在研究区域内，不同土地利用类型下的蒸散发表现为：林地 $>$ 水体 $>$ 草地 $>$ 耕地 $>$ 建设用地>未利用地，说明区域蒸散量的大小不仅受区域气候、自然地理等条件影响，还与下垫面土地利用、植被盖度等有关。随着经济的发展，自然生态下垫面被人工下垫面所取代的同时，也在影响并改变着区域蒸散发量。

(3）研究区风速与地表蒸散发具有显著正相关性，近地面空气相对湿度与地表蒸散发具有显著负相关性；地表参数相关分析表明，地表比辐射率中 $( \varepsilon )$ 、DEM与蒸散发具有显著的正相关性，地表温度1 $\left( T _ { s } \right)$ 、温度植被干旱指数(TVDI)与蒸散发具有显著负相关性。

参考文献(Reference):   
[1]代鹏超,牛苏娟,毋兆鹏,等.新疆精河流域实际蒸散发时空变 化特征[J].生态与农村环境学报,2017,33(7):600-606.[Dai Pengchao, Niu Sujuan,Wu Zhaopeng,et al.Spatiotemporal variation of actual evapotranspiration in Jinghe River Basin of Xinjiang [J]. Journal of EcologyandRural Environment,2017,3(7):600 606.]   
[2]周妍妍,郭晓娟,郭建军,等.基于SEBAL模型的疏勒河流域蒸 散量时空动态[J].水土保持研究,2019,26(1):168-177.[Zhou Yanyan,Guo Xiaojuan,Guo Jianjun, et al.Spatial and temporal dynamics of evapotranspiration in the Shule River Basin based on SEBAL model[J]. Research of Soil and Water Conservation, 2019 26(1): 168-177.]   
[3]Bowen L S.The ratio of heat losses by conduction and by evaporation from any water surface[J]. Physics Review,1926,27(6): 779-789.   
[4]Thornthwaite C W, Benjamin Holzman.The determination of evaporation from land and water surfaces[J]. Monthly Weather Review, 1939, 67: 4-11.   
[5]Monteith JL.Evaporation and environment[J]. Symposia of the So ciety for Experimental Biology,1965,19:205-234.   
[6]Menenti M, Choudhury B J. Parameterization of land surface e vap-oration by means of location dependent potential evaporationand surface temperature range[C]//Exchange Processes at the Land Surface for a Range of Space and Time Scales. Walling-ford, Eng: IAHS Press,1993: 561-568.   
[7]Bastiaanssen W G M, Menenti M,Feddes R A,et al.A remote sensing surface energy balance algorithm for land (SEBAL) 1.Formulation[J].Journal of Hydrology,1998,212-213:198-212.   
[8]Su Z. The surface energy balance system（SEBS)for estima-tion of turbulent heat fluxes[J]. Hydrology and Earth System Sciences, 2002, 6( 1) : 85-99.   
[9]李晓媛,于德永.蒸散发估算方法及其驱动力研究进展[J].干旱 区研究,2020,37(1):26-36.[Li Xiaoyuan, Yu Deyong.Progress on evapotranspiration estimation methods and driving forces in ar id and semiarid regions[J].Arid Zone Research,2O2o,37(1): 26- 36.]   
[10] 王媛,董煜,焦黎.艾比湖绿洲参考作物蒸散量的敏感性分析 [J].灌溉排水学报,2019,38(7):110-115.[Wang Yuan,Dong Yu,Jiao Li. Sensitivity analysis of the reference evapotranspiration in Ebinur Lake Oasis[J]. Journal of Irrigation and Drainage, 2019,38(7): 110-115.]   
[11] 谭娇,丁建丽,董煜,等.新疆艾比湖绿洲潜在蒸散量年代际变 化特征[J].农业工程学报,2017,33(5):143-148.[Tan Jiao,Ding Jianli,Dong Yu,et al.Interdecadal variation characteristics of potentialevapotranspirationinEbinur LakeOasisin Xinjiang[J]. Transactionsof the Chinese Societyof Agricultural Engineering, 2017, 33(5): 143-148.]   
[12] 郭家新,高敏华,朱小强,等.基于空间三角形法的艾比湖蒸散 发时空变化及其驱动力研究[J].安徽农学通报,2017,23(18): 57-63.[Guo Jiaxin,Gao Minhua, Zhu Xiaoqiang,et al.Analysis of spatiotemporal changs of evapotranspiration and driving forces of the Ebinur Lake Basin based on triangle method[J]. Journal of Anhui Agricultural Sciences,2017,23(18): 57-63.]   
[13] 张晓玉,范亚云,热孜宛古丽·麦麦提依明,等.基于SEBS 模型 的干旱区流域蒸散发估算探究[J].干旱区地理,2018,41(3): 508-517. [Zhang Xiaoyu,Fan Yayun,Maimaitiyiming Reziwanguli,et al.Evapotranspiration estimation of watershed in arid area based on SEBS model[J]. Arid Land Geography,2018,41(3): 508-517.]   
[14] 王燕鑫,李瑞平,李夏子.河套灌区不同土地类型生长季蒸散发 量估算及其变化特征[J].干旱区研究,2020,37(2):364-373.[ Wang Yanxin,Li Ruiping,Li Xiazi.Estimation and variability of evapotranspiration for different land types during the growing season in the Hetao Irrigation District[J]. Arid Zone Research,2020, 37(2): 364-373.]   
[15] 金学杰,周剑.基于SEBS 模型和Landsat 8数据的黑河下游蒸 散发时空特性分析[J].冰川冻土,2017,39(3):572-582.[Jin Xuejie,Zhou Jian. Spatial and temporal characteristics of evapotranspiration in the lower reaches of the Heihe River based on SEBS model and Landsat 8 data[J].Journal of Glaciology and Geocryology,2017,39(3): 572-582.]   
[16] Allen R, Tasumi M, Treza R. SABLE-Advanced Training and User Manual-Idaho Implementation[M]. Idaho,Estados Unidos: Universidad de Idaho,2002:5-18.   
[17] 宋文献,江善虎,杨春生,等.基于SEBS 模型的老哈河流域蒸散 发研究[J].水资源与水工程学报,2012,23(5):115-118,122. [Song Wenxian,Jiang Shanhu,Yang Chunsheng,et al.Study on evapotranspiration in the Laoha River Basin based on SEBS model [J]. Journal of Water Resources and Water Engineering,2012,23 (5):115-118,122.]   
[18] 赵军,刘春雨,潘竟虎,等.基于MODIS数据的甘南草原区域蒸 散发量时空格局分析[J].资源科学,2011,33(2):341-346. [Zhao Jun,Liu Chunyu,Pan Jinghu,et al.Analysis of temporal and spatial patterns of evapotranspiration in Gannan grassland based on MODIS Data[J]. Resources Science,2011,33(2): 341-346.]   
[19] 李宝富,陈亚宁,李卫红,等.基于遥感和SEBAL模型的塔里木 河干流区蒸散发估算[J].地理学报,2011,66(9):1230-1238. [Li Baofu,Chen Yaning,Li Weihong,et al.Estimation of evapotranspiration in the main stream of Tarim River based on remote sensing and SEBAL model[J]. Acta Geographica Sinica,2011,66 (9): 1230-1238.]   
[20] 阿布都沙拉木·吐鲁甫,买买提·沙吾提,马春玥,等.基于 SEBAL模型的渭-库绿洲蒸散量特征及影响因子研究[J].地球信 息科学学报，2018,20(9)：1361-1372.[Abdusalam Turup, Mamat Saeut,Ma Chunyue, et al. Study on the characteristics of evapotranspiration and its influencing factors in the Ugan and Kuqa Rivers delta Oasis based on SEBAL model[J]. Journal of Geo-Information Science,2018,20(9): 1361-1372.]   
[21] 宁婷婷,刘文兆,林文,等.近56年来内蒙古东胜矿区潜在蒸散 发的时程变化[J].水土保持学报,2014,28(3): 62-66,82.[Ning Tingting,Liu Wenzhao,Lin Wen,et al.Temporal changes of potential evapotranspiration in Dongsheng mining area in Inner Mongolia during recent 56 years[J]. Journal of Soil and Water Conservation,2014,28(3):62-66,82.]   
[22]许婧璟,靳晓言,强皓凡,等.新疆艾比湖流域潜在蒸散变化特 征与成因分析[J].灌溉排水学报,2018,37(2):89-94.[Xu Jingjing,Jin Xiaoyan,Qiang Haofan,etal.Variety characteristics and cause analysis of potential evapotranspiration in the Ebinur Lake Basin in Xingjiang[J]. Journal of Irrigation and Drainage, 2018,37(2): 89-94.]   
[23]汪彪,曾新民,刘正奇，等.中国西北地区参考作物蒸散量的估 算与变化特征[J].干旱气象,2016,34(2):243-251.[Wang Biao, Zeng Xinmin,Liu Zhengqi,et al.Estimation and variation characteristics of the reference crop evapotranspiration in Northwest China during 1956-2011[J]. Journal of Arid Meteorology,2016,34 (2): 243-251.]   
[24]张景华,封志明,姜鲁光.土地利用/土地覆被分类系统研究进 展[J].资源科学,2011,33(6):1195-1203.[Zhang Jinghua,Feng Zhiming, Jiang Luguang.Research progress in land use/land cover classification system[J].Resources Science,2011,33(6): 1195-1203.]   
[25]王非,毋兆鹏,汪洋,等.基于RS和GIS的塔里木盆地荒漠化动 态监测[J].生态学杂志,2017,36(4):1029-1037.[Wang Fei,Wu Zhaopeng,Wang Yang,et al.Dynamic monitoring of desertification in Tarim Basin based on RS and GIS[J]. Journal of Ecology, 2017,36(4): 1029-1037.]   
[26]IPCC.Special Report on Global Warming of 1.5 ℃(SR15)[M]

Cambridge:Cambridge University Press,2O18:785.

[27] 热孜宛古丽·麦麦提依明,杨建军,刘巍.艾比湖流域1957— 2013 年潜在蒸散、气温、降水变化特征分析[J].冰川冻土, 2016,38(1):69-76.[Reziwanguli Maimaityiming,Yang Jianjun, Liu Wei. Changing characteristics of potential evapotranspiration, air temperature and precipitation in Ebinur Lake basin from 1957 to 2013[J]. Journal of Glaciology and Geocryology，2016,38(1): 69-76.]   
[28] 苏布达,周建,王艳君,等.全球升温 $1 . 5 ~ \mathrm { { ^ { \circ } C } }$ 和 $2 . 0 \mathrm { { ‰} }$ 情景下中国 实际蒸散发时空变化特征[J].中国农业气象,2018,39(5):293- 303.[Su Buda,Zhou Jian,Wang Yanjun,et al. Spatial and temporal variation of actual Evapotranspiration in China under the $1 . 5 ~ \mathrm { { ^ { \circ } C } }$ and $2 . 0 \ : \mathrm { ‰}$ global warming scenarios[J]. Chinese Journal of Agrometeorology,2018,39(5): 293-303.]   
[29] 苏向明,刘志辉,魏天锋,等.艾比湖面积变化及其径流特征变 化的响应[J].水土保持研究,2016,23(3):252-256.[Su Xiangming,Liu Zhihui,Wei Tianfeng,et al.Response of the change of area and its runoff characteristics in Aibi Lake[J]. Research of Soil and Water Conservation,2016,23(3):252-256.]   
[30]葛翔宇.基于机器学习近30a艾比湖湖面变化及自然驱动因素 分析[D].乌鲁木齐:新疆大学,2019.[Ge Xiangyu.Analysis of Lake Surface Change and Natural Driving Factors in Ebinur Lake Based on Machine Learning in Recent 3O a[D]. Urumqi: Xinjiang University,2019.]

# Evapotranspiration in the Jinghe River Basin based on the surface energy balance system

ZHENG Qian-qian'， DAI Peng-chao²， ZHANG Jin-yan'， WU Zhao-peng $^ { 1 , 3 }$ (1.Collge ofGeographical Scienceand Tourism,Xinjiang Normal University,Urumqi 83oo54,Xinjiang,China; 2.Urumqi Meteorological Satellite Ground Station, Urumqi 83o054, Xinjiang, China; 3.Laboratory ofArid Lake Environment and Resources,Urumqi 83oo54, Xinjiang, China)

Abstract: The arid ecological fragilearea of Jinghe Basin was selected as the research area.Daily meteorological observation data from 1990 to 2016 and six scenes of corresponding Landsat series images were investigated.The results show that under the context of global warming,evapotranspiration inthe study area as a whole has increased over the past 26 years and Morlet wavelet analysis shows that there are 5 a,7a,13 a scale change cycles. Additionally,evapotranspiration in the study area is spatially high in the south and low in the north.The evapotranspiration was reduced in the unused land in the northeast and significantly increased in the northwestern part of Lake Aibiand the southern mountainous area.Evapotranspiration under diferent land-use types followed the pattern from high to low of forest land $>$ water body $>$ grassland $>$ cultivated land $>$ construction land $>$ unused land. Amongthe measured meteorological factors，wind speed was highlypositively correlated with surface evapotranspiration,along with elevation and specific surface emisivity.The meteorological factors that show a highly negative correlation with surfaceevapotranspiration were near-surface air relative humidity,and the surface parameters were temperature vegetation drought index and surface temperature.

Keywords: SEBS model; evapotranspiration; space-time pattern; Jinghe River Basin; Xinjiang