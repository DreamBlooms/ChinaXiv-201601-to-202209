# 锡林河流域上游蒸散发估算及其时空特征

周亚军1,刘廷玺1,2,段利民1,²,王怡璇1,2,李霞¹,黎明扬1(1.内蒙古农业大学水利与土木建筑工程学院,内蒙古 呼和浩特 010018;2.内蒙古自治区水资源保护与利用重点实验室,内蒙古 呼和浩特010018）

摘要：为揭示锡林河流域上游蒸散发（ET）变化规律及其时空分布特征，采用Landsat8数据、气象观测数据和 SEBAL 模型估算 2015—2017年共12 期植物生长季的蒸散量，并分析其时空格局及影响因素。结果表明： $\textcircled{1}$ 研究区模型反演参数值与实测值拟合效果良好，地表净辐射 $( R _ { \mathrm { n } } )$ 、土壤热通量 $( G )$ 、ET的决定系数 $( \boldsymbol { R } ^ { 2 }$ ）分别为0.80、0.65和0.86； $\textcircled{2}$ 同一时段的 $\scriptstyle R _ { \mathrm { n } }$ 和 $E T$ 空间分布具有较高的一致性，整体呈现东高西低的趋势，具有显著的时空分异特征。4月日 $E T$ 值在 $0 { \sim } 4 . 6 7 \ \mathrm { m m }$ ，5—7月日ET值整体呈增加趋势，最大可达 $1 0 . 3 2 \mathrm { m m }$ ，9—10月日 $E T$ 值减少至 $0 { \sim } 3 . 3 4 ~ \mathrm { m m }$ ： $\textcircled{3}$ 不同土地利用类型蒸散量依次为：水体 $>$ 沼泽地 $>$ 耕地>草地 $>$ 沙地 $>$ 农村居民点， $E T$ 值与日平均气温 $( T )$ 、饱和水气压差（ $V P D$ ）、 $\scriptstyle R _ { \mathrm { n } }$ 呈正相关，与空气湿度（RH）呈负相关，对 $\textstyle R _ { \mathrm { n } }$ 的变化最为敏感。

关键词：SEBAL模型；蒸散发；时空特征；锡林河流域

流域蒸散发（evapotranspiration， $E T )$ ，包括土壤蒸发、水面蒸发和植被蒸腾，是地表水热平衡的重要参量[，可为植物的生长发育提供必要的水分和能量，对干旱半干旱地区内陆河流域生态水文循环过程起着至关重要的作用[2]。Rosenberg 等[3指出，地表降水的 $70 \%$ 以蒸散发形式回到大气中，在干旱区该比例可达 $90 \%$ 。因此，准确估算流域蒸散发的时空变化，对于了解干旱半干旱地区水文循环过程和区域气候变化，实现生态、水文、社会绿色协调发展具有重要意义。

从1802 年道尔顿(Dalton)提出蒸发量与水汽压差成比例关系4]，到20 世纪50年代估算潜在蒸发的 Penman 公式的提出[5]，再到 1965 年 Monteith 引入冠层阻抗的概念进一步完善了模型，人们在为实际蒸散量的理论估算进行了长期不懈的努力。但传统估算蒸散发的方法大多基于观测站点(如波文比系统等)，局限于单点尺度，很难在区域尺度扩展，空间代表性较差[。随着遥感技术的发展，极大地方便了大尺度非均匀下垫面的地表特征参数的获取，可以精确估算地表实际蒸散量的一系列遥感模型应运而生[8]。例如 SEBAL[9]、METRIC[10]、SEBS[1等。其中，SEBAL模型是基于地表能量平衡原理来反演蒸散发的方法，模型假设区域存在冷热极限点，很好的考虑了干旱地区空间异质性[12]，不仅在湿地、耕地、居民点等土地利用类型有较好的适用性，而且对水体蒸散的反演有较高的精度[13-14]。刘曼晴等[15]利用 SEBAL模型反演了水面蒸发且以此为估测值，与蒸发皿实测值有好的拟合效果。连晋姣等[1基于 SEBAL-METRIC 模型估算了夏季黑河中游样带尺度不同土地覆盖类型蒸散量，结果表明：在荒漠区与绿洲区分别选取"热点"可有效提高模型估算精度。Lee等[17利用改进的SEBAL对韩国的蒸散量进行了计算，得出平原地区的蒸散量高于高原地区的结论。

锡林河流域是我国的内陆河流域，由于水汽补给不足，加之不合理人类活动的影响，导致极端水文事件频发、径流调节能力降低、草原植被矮小且多样性降低、河谷湿地萎缩增多，流域生态水文功能退化等现象日趋严重[18]。因此亟需开展内陆河流域蒸散时空变化特征研究，掌握流域生态恢复的耗水规律，以期为该区域植被对水热分配响应提供科学依据。

# 1研究区概况及数据

# 1.1研究区概况

锡林河流域位于内蒙古中部锡林郭勒盟，发源于赤峰市克什克腾旗宝尔图山，在贝力克牧场转向西北流经锡林浩特市，最终注入查干诺尔沼泽地自然消失。流域内由小型湿地、滩地、沼泽地、河渠等水域组成，是典型的干旱半干旱区内陆河流域。好来吐郭勒、好来郭勒、呼斯特河是其最主要的3条支流[19]，主河全长 $1 7 5 \mathrm { k m }$ （图1)，锡林河河源至库尼苏曼为流域上游 $4 3 ^ { \circ } 2 6 ^ { \prime } { \sim } 4 4 ^ { \circ } 0 8 ^ { \prime } \mathrm { N }$ ， $1 1 6 ^ { \circ } 0 2 ^ { \prime } { \sim } 1 1 7 ^ { \circ } 1 2 ^ { \prime } \mathrm { E } )$ ，上游地区广泛分布着草甸草原的大针茅（Stipagrandis）、羊草（Leymus chinensis）、无芒雀麦（Bromus inermis）等优势物种。土壤类型主要以黑钙土、栗钙土为主，土壤有机质含量较高，腐殖质层平均 $3 7 \mathrm { c m } ^ { [ 2 0 ] }$ 。该区域气候属大陆性温带半干旱气候，流域多年平均降水量约 $2 7 8 . 9 \mathrm { { m m } }$ ，其中6—9月降水量占年总降水量的 $80 \%$ 以上，年平均气温为 $2 . 8 ^ { \circ } \mathrm { C } ^ { [ 2 1 ] }$ 。

![](images/42bdaf8db89562fb647d6a8b4442f3b50986f343596556de0d186e222656636a.jpg)  
图2土地利用类型图Fig.2 Map of land use types

![](images/b33069998cd07ca8c51e668612c96805db5a8b43947e969a076f9db630ebc7f4.jpg)  
图1研究区示意图  
Fig.1 Location of study area

# 1.3遥感数据

土地利用类型数据提取于 2015—2017年的Landsat8影像，根据我国《土地利用现状分类标准》将研究区共分为7类（图2)，包括水体（河流和湖泊）、沙地、耕地、沼泽地、高覆盖草地、低覆盖草地、农村居民点。

本文所采用的遥感数据为Landsat8OLI数据。在数据选择方面，由于生长季植被覆盖度高，基于SEBAL模型反演的蒸散量更加准确，根据研究区已有卫星数据的影像质量、成像时间等信息，选取锡林河流域上游 2015—2017年生长季的12期（2015年4、5、7、9月，2016年5、6、9月，2017年4、5、6、7、10月）无云或少云，清晰度高的遥感影像，影像数据取自美国地质调查局(USGS)网站(http://earthexplorer.usgs.gov/)以及地理空间数据云网站(http://www.gscloud.cn/)。

# 1.4气象数据及其他辅助数据

选取研究区2015—2017年各年4—10月石门气象站的气象数据，包括气温、相对湿度、风速、日照时数、降水和土壤温度等。数据采集频次为 $1 0 \mathrm { { H z } }$ ，每 $3 0 \mathrm { m i n }$ 记录1次，通过数据采集器 CR1000(CR1000,Campbell Scientific)储存，仪器型号和安装高度见表1。

为提高模型的估算精度，在 SEBAL计算过程中输入研究区的气温和风速数据。本文利用研究区附近的4个国家站 $2 \mathrm { m }$ 处气温 $( T _ { \mathrm { a } } )$ 和风速(W)，通过克里金插值法(Kriging method)得到与遥感数据空间分辨率相同的栅格数据。

使用的DEM数据为地理空间数据云网站(http://www.gscloud.cn/)下载的GDEMV2 $3 0 \mathrm { ~ m ~ }$ 分辨率数字高程数据。

表1气象站传感器基本信息  
Table1 Basic information of micrometeorological sensors   

<html><body><table><tr><td>产品名称</td><td>型号</td><td>安装高度/m</td><td>生产商</td></tr><tr><td>空气温湿度</td><td>HMP155A</td><td>2</td><td>Campbell Scientific Inc., USA</td></tr><tr><td>四分量净辐射仪</td><td>NR-LITE</td><td>2</td><td>Campbell Scientific Inc.,USA</td></tr><tr><td>风杯式风速仪</td><td>034B</td><td>2, 3.5</td><td>Met One Instruments Inc.,USA</td></tr><tr><td>土壤热通量板</td><td>HFP01</td><td>-0.1</td><td>Husker Flux Inc., USA</td></tr><tr><td>雨量筒</td><td>TEM525MM</td><td>2</td><td>Texas Electronics.,USA</td></tr><tr><td>土壤三参数仪</td><td>CS655</td><td>-0.1,-0.2,-0.4,-0.8</td><td>Campbell Scientific Inc.,USA</td></tr></table></body></html>

# 2 研究方法

# 2.1SEBAL蒸散模型及其参数计算

SEBAL 模型是Bastiaanssen 等[22]提出的单层计算模型，利用能量平衡方程计算蒸发瞬时潜热通量。然后对图像的每个像素点计算瞬时蒸发和日蒸发。

$$
\lambda E T = R _ { \mathrm { n } } - G - H
$$

式中： $\lambda$ 是水的汽化潜热 $( \mathbf { W } { \cdot } \mathbf { m } ^ { - 2 } { \cdot } \mathbf { m } \mathbf { m } ^ { - 1 } )$ ； $E T$ 是蒸散量（ $\mathbf { \dot { m } } \mathbf { m } )$ ; $R _ { \mathfrak { n } }$ 为净辐射量 $( \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 } )$ ; $G$   
为土壤热通量 $( \mathbf { W } { \cdot } \mathbf { m } ^ { - 2 } )$ ； $H$ 为显热通量！ $\mathbf { \chi } ( \mathbf { W } { \cdot } \mathbf { m } ^ { - 2 } { \cdot } \mathbf { m } \mathbf { m } ^ { - 1 }$ ）。

（1）净辐射通量 $( R _ { \mathrm { n } }$ ）计算公式：

$$
R _ { n } = ( 1 - \alpha ) R _ { s \downarrow } + R _ { \mathrm { L } \downarrow } - R _ { \mathrm { L } \uparrow } - ( 1 - \varepsilon _ { 0 } ) R _ { \mathrm { L } \downarrow }
$$

式中： $\boldsymbol { a }$ 为地表反照率； $R _ { \mathrm { s \downarrow } }$ 为入射到地表的太阳短波辐射，也叫太阳总辐射 $( \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 } )$ ; $R _ { \mathrm { L } \downarrow }$ 是 太阳入射的长波辐射 $( \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 } )$ ； $R _ { \mathrm { L } \uparrow }$ 为地表发射的长波辐射 $( \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 } )$ ； $\boldsymbol { \varepsilon }$ 为地表比辐射率，介于 0\~1之间。

（2）地表反照率计算公式为：

$$
\begin{array} { r } { \alpha = \frac { \alpha _ { \mathrm { { t o a } } } - \alpha _ { \mathrm { { p a t h \_ r a d i a n c e } } } } { \tau _ { s \mathrm { { w } } } ^ { 2 } } } \end{array}
$$

式中： $\alpha _ { \mathrm { t o a } }$ 为宽带行星大气顶反射率;αpath_radiance是大气路径反照率，值为 $0 . 0 2 5 { \sim } 0 . 0 4 ^ { [ 2 3 ] }$ ：$\tau _ { \mathrm { s w } }$ 是大气单向透射率，由以下公式计算：

$$
\tau _ { s \mathrm { w } } = 0 . 7 5 + 2 \times 1 0 ^ { - 5 } \times Z
$$

（3）入射的短波辐射 $( R \mathrm { s } \downarrow$ ）计算公式：

$$
R _ { s \downarrow } = G _ { s c } \times \mathrm { C o s } \theta \times d _ { \mathrm { r } } \times \tau _ { s \mathrm { w } }
$$

式中： $G _ { \mathrm { s c } }$ 是太阳常数，取1367 $( \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 } )$ ； $\theta$ 为太阳天顶角（从卫星图像的 MTL文件中获取);  
$d _ { \mathrm { r } }$ 为日地距离。

（4）入射的长波辐射 $( R _ { \mathrm { L } \downarrow }$ ）计算公式：

$$
R _ { \mathrm { L } \downarrow } = \varepsilon _ { \mathrm { a } } \sigma T _ { \mathrm { a } } ^ { 4 }
$$

式中： $\varepsilon _ { \mathrm { a } }$ 是大气比辐射率； $\sigma$ 为斯蒂芬-玻尔兹曼常数，取 $5 . 6 7 { \times } 1 0 ^ { - 8 } \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 } { \cdot } \mathrm { K } ^ { - 4 }$ . $T _ { \mathrm { a } }$ 为空气温度。

$$
\varepsilon _ { \mathrm { a } } = 1 . 0 8 ( - \mathrm { l n } \tau _ { s \mathrm { w } } ) ^ { 0 . 2 6 5 }
$$

（5）地表长波辐射 $( R _ { \mathrm { L } \uparrow } )$ ：

$$
R _ { \mathrm { L } \uparrow } = \varepsilon _ { 0 } \sigma T _ { s } ^ { 4 }
$$

式中： $\scriptstyle { \varepsilon _ { 0 } }$ 为地表比辐射率； $\sigma$ 为常数； $T _ { \mathrm { s } }$ 为地表温度(K)。

$$
\varepsilon _ { 0 } = 1 . 0 0 9 + 0 . 0 4 7 \cdot \ln ( \mathrm { N D V I } )
$$

(6)土壤热通量 $( G )$ ：利用植被指数、地表净辐射与其关系，来计算出土壤热通量值[24]。

$$
\begin{array} { r } { \frac { G } { R _ { \mathrm { n } } } = \frac { T _ { \mathrm { s } } } { ( 0 . 0 0 3 8 \alpha + 0 . 0 0 7 4 \alpha ^ { 2 } ) ( 1 - 0 . 9 8 \mathrm { N D V I ^ { 4 } } ) } } \end{array}
$$

（7）感热通量 $( H )$ ：

$$
H = \frac { ( \rho { \times } C _ { \mathrm { p } } { \times } d T ) } { r _ { \mathrm { a h } } }
$$

式中： $\rho$ 为空气密度，标准状态下取 $1 . 2 9 3 \mathrm { k g } { \cdot } \mathrm { m } ^ { - 3 }$ $C _ { \mathfrak { p } }$ 空气定压比热，通常取 $1 0 0 4 ( \mathbf { J } { \cdot } \mathbf { k g } ^ { - 1 } { \cdot } \mathbf { K } ^ { - 1 } )$ ：dT 是高度为 $Z _ { 1 }$ 和 $Z _ { 2 }$ 处的温度之差； $r _ { \mathrm { a h } }$ 为空气动力学阻力（ $\cdot \mathbf { S } { \cdot } \mathbf { m } ^ { - 1 }$ ）。

为求得 $d T$ 需要从影像中选择干湿像元：“热点"是植被覆盖很少的盐碱地，温度较高。“冷点"处水分充足，植被茂盛，地表温度很低，通过计算"热点"和"冷点"就可以得到所有像元的dT值。

# 2.2蒸发比及日蒸散发量

由于卫星过境得到的是瞬时影像，因此，需要转换得到日通量。SEBAL模型中假设 24h之内蒸发比是相对稳定的。

蒸发比〉：

$$
\begin{array} { r } { \Lambda _ { \mathrm { i n s t } } { = } \frac { \lambda E T } { R _ { \mathrm { n } } - G } { = } \Lambda _ { 2 4 } } \end{array}
$$

式中：入24是一天24h内的蒸散发比。

日蒸散量 $E T _ { 2 4 }$

$$
\begin{array} { r } { E T _ { 2 4 } = \frac { R _ { \mathrm { n 2 4 } } \times \Lambda _ { 2 4 } \times 8 6 4 0 0 } { [ 2 . 5 0 1 - 0 . 0 0 2 3 6 1 \times ( T _ { \mathrm { s } } - 2 7 3 . 1 5 ) ] \times 1 0 ^ { 6 } } } \end{array}
$$

式中： $R _ { \mathrm { n 2 4 } }$ 是一天内的净辐射量（ $( \mathbf { W } { \cdot } \mathbf { m } ^ { - 2 } .$ ）； $T _ { \mathrm { s } }$ 是地表温度（K)

# 2.3FAOPenman-Monteith模型

其计算公式为[25]:

$$
\begin{array} { r } { E T _ { 0 } = \frac { 0 . 4 0 8 \varDelta \left( R _ { \mathrm { n } } - G \right) + \gamma \frac { 9 0 0 } { T + 2 7 3 } u _ { 2 } \left( e _ { s } - e _ { \mathrm { a } } \right) } { \varphi + \gamma \left( 1 + 0 . 3 4 u _ { 2 } \right) } } \end{array}
$$

$$
E T = K _ { \mathrm { c } } \times E T _ { 0 }
$$

式中： $E T _ { 0 }$ 为潜在蒸散发（ $\mathbf { m m \cdot d } ^ { - 1 } .$ ； $E T$ 为实际蒸散发 $\left( \mathrm { m m } { \cdot } \mathrm { d } ^ { - 1 } \right)$ ； $K _ { \mathrm { c } }$ 为作物系数， $\varphi$ 为饱和水汽压曲线斜率 $\mathrm { { ( k P a \cdot ^ { \circ } C ^ { - 1 } ) } }$ ； $R _ { \mathrm { n } }$ 为冠层表面净辐射 $\left( \mathbf { M } \mathbf { J } \cdot \mathbf { m } ^ { - 2 } \cdot \mathbf { d } ^ { - 1 } \right)$ $T$ 为日平均气温 $( ^ { \circ } \mathbf { C } )$ ：$G$ 为土壤热通量 $( \mathbf { M } \mathbf { J } \cdot \mathbf { m } ^ { - 2 } \cdot \mathbf { d } ^ { - 1 } )$ ； $u _ { 2 }$ 为 $2 \mathrm { m }$ 高度处风速 $( \mathrm { m } { \cdot } \mathrm { s } ^ { - 1 } )$ ； $e _ { \mathrm { s } }$ 为饱和水汽压（ $\mathrm { \ k P a } \dot { }$ ； $e _ { \mathrm { a } }$ 为实际水汽压（ $\mathrm { \cdot k P a ) }$ ; $\gamma$ 为湿度计常数（ $\mathrm { { k P a } \cdot \mathcal { C } ^ { - 1 } ) }$ 。

# 2.4模型适用性评价

为评价SEBAL模型的适用性，采取相对均方差（RMSE）、一致性指数（d)、平均偏差（bias）、和 Nash-Sutcliffe 效率指数 $( E ) ~ 4$ 个统计量进行评价，计算公式如下[26]。

$$
\begin{array} { r } { R M S E = \left( \frac { 1 } { N } \sum _ { i = 1 } ^ { N } ( P _ { i } - O _ { i } ) ^ { 2 } \right) ^ { \frac { 1 } { 2 } } } \end{array}
$$

$$
\begin{array} { r } { d = 1 - \left[ \frac { \sum _ { i = 1 } ^ { N } ( P _ { i } - O _ { i } ) ^ { 2 } } { \sum _ { i = 1 } ^ { N } ( | P _ { i } - O _ { a v e } | + | O _ { i } + O _ { a v e } | ) ^ { 2 } } \right] } \end{array}
$$

$$
\begin{array} { r } { b i a s = \frac { 1 } { N } { \sum _ { i = 1 } ^ { N } } ( O _ { i } - P _ { i } ) } \end{array}
$$

$$
E = 1 - [ \sum _ { i = 1 } ^ { N } ( O _ { i } - P _ { i } ) ^ { 2 } / ( O _ { i } - \bar { O } ) ^ { 2 } ]
$$

# 2.5敏感性分析

敏感性分析是从定量角度分析相关气象因子发生变化时，对 $E T$ 的变化产生影响的定量参数[27]。其计算方法为 $E T$ 变化率与气象因子变化率的比值。

$$
\begin{array} { r } { S = l i m _ { \Delta V  0 } ( \frac { \Delta E T / E T } { \Delta Q / Q } ) = \frac { \partial E T } { \partial Q } \cdot \frac { V Q } { E T } } \end{array}
$$

式中： $s$ 为敏感系数； $\Delta E T$ 为实际蒸散量的变化量； $Q$ 和 $\Delta Q$ 分别为气象因子及其变化量。

# 3结果与分析

# 3.1SEBAL模型反演结果验证

为验证SEBAL模型反演精度，本文基于石门湿地气象站气象数据（石门气象站的建站时间为2015年11月，所以对模型的验证从2016年生长季开始)，以及 $\mathrm { F A O } 5 6 \mathrm { P - M }$ 计算的蒸散量与卫星过境时刻SEBAL 模型反演的 $E T$ 、 $R _ { \mathrm { n } }$ 、 $G$ 值进行验证对比。作物系数 $K _ { c }$ 在生长初期、生长中期和生长后期取值分别为[28]： $K _ { \mathrm { c i n i } } { = } 0 . 4$ 、 $K _ { \mathrm { c m i d } } { = } 0 . 9 3$ 和 $K _ { \mathrm { c e n d } } { = } 0 . 8$ 。

由实测值与反演值的回归分析（图3）可知： $E T$ 的模拟值与实测值的分布较为集中，大多分布在1:1直线附近，决定系数 $\textstyle R ^ { 2 }$ 最高，为 $0 . 8 6$ ， $R _ { \mathrm { n } }$ 和 $G$ 均在1:1线之上，反演值大于实测值，有一定高估， $R _ { \mathfrak { n } }$ 决定系数 $R ^ { 2 }$ 为0.80， $G$ 的模拟值较分散且波动相对较大， $\textstyle R ^ { 2 }$ 最小为0.65；由统计参数（表2）可知：RMSE可衡量模拟值与实测值之间的偏差， $E T$ 的RMSE为0.95，表明模拟值与实测值较接近，模拟结果最好； $d$ 值越接近1，表明模型模拟效果越好， $R _ { \mathrm { n } }$ ， $G$ ， $E T$ 分别为0.99、0.99 和0.96，均趋近于1，模拟效果较好；bias反映实测值与模拟值的偏差越接近O，精度越高，而Nash-Sutcliffe效率指数 $( E )$ 越接近1，表示模型可信度越高。综上所述，SEBAL模型对各个参数的模拟精度较高，因此，SEBAL模型在锡林河流域上游具有较好的适用性。

![](images/c52c9a6a0a036de79b8b86fdce3ed3860b1f1d9c8291637e1f562ecc533eb732.jpg)  
图3实测值与模型反演值对比  
Fig.3 Comparison of measured values and model inversion values

表2SEBAL模型适用性分析  
Table2 Adaptability analysis of SEBAL model   

<html><body><table><tr><td>参数</td><td>Rn/(W·m2)</td><td>G/(W·m-2)</td><td>ET/mm</td></tr><tr><td>相对均方差(RMSE)</td><td>47.21</td><td>10.77</td><td>0.95</td></tr><tr><td>一致性指数(d)</td><td>0.99</td><td>0.99</td><td>0.96</td></tr><tr><td>平均偏差(bias)</td><td>-67.88</td><td>-7.14</td><td>0.48</td></tr><tr><td>Nash-Sutcliffe 效率指数(E)</td><td>0.94</td><td>0.95</td><td>0.85</td></tr></table></body></html>

SEBAL模型估算日ET值与FAO56P-M计算值对比结果见图4，由图4可知：2016—2017年石门湿地生长季SEBAL模型估计值与P-M模型的计算值变化趋势基本一致，二者起伏大致相同。蒸散量的季节变化较为明显，研究区2016—2017年4—5月蒸散量处于较低水平，平均值为 $4 . 8 1 \ \mathrm { m m } { \cdot } \mathrm { d } ^ { - 1 }$ ，从6月开始呈增加趋势，6—8月蒸散量平均值为 $5 . 7 6 \mathrm { m m } { \cdot } \mathrm { d } ^ { - 1 }$ ，9月蒸散量开始减弱，9—10月蒸散量平均值为 ${ \left. 2 . 8 9 \right. \mathrm { m m } { \cdot } \mathrm { d } ^ { - 1 } }$ 。在出现降雨的时间，大部分 $E T$ 都会对应出现一个波谷，降雨事件结束之后会出现一个波峰。

![](images/eb53dabe9b11071cb2d4a3ebd2880f009d82b79d12a7cb0ff9ac6fe5a0c710a0.jpg)  
图42016—2017年石门湿地降水及SEBAL与P-M的计算值

Fig.4 Precipitation,SEBAL and P-M calculation value of ShiMen Wetland from 2016 to 2017

# $3 . 2 R _ { \mathrm { n } }$ 和 $E T$ 的时空格局

利用SEBAL模型估算研究区2015—017年4—10月的日 $R _ { \mathrm { n } }$ 值， $R _ { \mathrm { n } }$ 时空分布格局如图5所示。

![](images/06189abe655b8b9124bc324989b2f35c62654df372cba8ed1ae34f5ee9415f40.jpg)  
图52015—2017年SEBAL估算日 $R _ { \mathrm { n } }$ 时空分布

Fig.5 Spatio-temporal distribution of SEBAL estimated daily net radiation fluxes of 2O14 to 2016

由图5可以看出，锡林河流域上游的地表净辐射具有明显的季节性变化，总体 $R _ { \mathrm { n } }$ 值在$1 0 0 { \sim } 7 8 0 ~ \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 }$ ，最大值和最小值相差很大，空间上呈现东高西低的状态。生长季内河谷湿地的 $R _ { \mathfrak { n } }$ 一直保持较高的水平，在 $4 0 0 { \sim } 7 5 0 \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 }$ ，在相同气候条件下，不同土地利用状况直接影响地表能量的分配，与其他土地利用情况相比，河谷湿地水分充足，植被覆盖度高，热容量大，而地表温度和地表反照率低，其对太阳辐射的吸收能力强，反射能力弱，相应的地表净辐射值较大，所以在生长季内其净辐射通量值远高于其他土地利用类型；草地和沙地的$R _ { \mathrm { n } }$ 在4月保持在 $1 0 0 { \sim } 3 0 0 \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 }$ ，5—7月明显增大，在 $3 0 0 { \sim } 6 5 0 \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 }$ ，说明此时植被生命活动旺盛，太阳辐射是主要的能量来源。9—10 月 $\scriptstyle { R _ { \mathrm { n } } }$ 值整体降低，为 $1 2 0 { \sim } 5 2 0 \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 }$ 。

研究区基于SEBAL模型影响估算的2015—2017年日蒸散空间分布情况如图6所示。对比图5和图6可以看出，地表净辐射越高，蒸散量也越大，地表净辐射与蒸散发呈现相同的变化趋势，在5—7月随着日照时间和地表净辐射的增加，蒸散量也随之增大。

![](images/dc595ae3ec580838a66799e96111a8ba19ba3346d84ae01e581a7cc490a58957.jpg)  
图62015—2017年SEBAL估算日ET时空分布

Fig.6 Spatio-temporal distribution of SEBALestimated daily evapotranspiration of 2O14 to 2016

研究区内不同土地利用/覆被类型及不同时间的蒸散发差异明显，整体上来看呈现东高西低的趋势，东部为锡林河流域发源地，河谷湿地植被高度和覆盖度都较高，以植被蒸腾为主，因此，蒸散量相对较高。西部草原植被覆盖度低，土壤表层含水量少，地下水对地表蒸散发的贡献较小[29]。结合土地覆被类型图对日蒸散量进行统计，研究区最大ET可达10.32$\mathrm { m m \cdot d ^ { - 1 } }$ ，主要是湖泊和水库；河谷湿地蒸散无明显的地形差异，日蒸散量空间分布较均一，蒸散量一直保持较高的水平，在 $2 . 4 2 { \sim } 1 0 . 3 2 \ \mathrm { m m } { \cdot } \mathrm { d } ^ { - 1 }$ ；耕地在作物生长季5—9月蒸散量水平仅次于湿地，在 $1 . 8 2 { \sim } 8 \ \mathrm { m m } { \cdot } \mathrm { d } ^ { - 1 }$ ；图7中部分农村居民点日蒸散量也较高，这是由于一些农村居民点附近种植蔬菜等作物，且农村居民点一般与农田毗邻，存在较多与农田的混合像元；沙丘裸地土壤含水量低，植被蒸腾作用小，蒸散量少，在 $5 \mathrm { m m }$ 以下。各年4月的蒸散值处于较低水平，日蒸散量在 $0 { \sim } 4 . 6 7 \ \mathrm { m m { \cdot } d ^ { - 1 } }$ ，日蒸散量均值为 $1 . 8 9 \mathrm { m m } { \cdot } \mathrm { d } ^ { - 1 }$ ，5—7月蒸散量整体呈增加趋势，日蒸散量均值为 $5 . 4 5 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ ，到 $9 { \sim } 1 0$ 月蒸散量水平降低，日均蒸散量为1.78$\mathrm { m m \cdot d } ^ { - 1 }$ 。

# 3.3蒸散量影响因素

蒸散量主要受区域下垫面性质和气象要素的影响[30]，在其驱动下呈现出独特的时空变化特征。

# 3.3.1土地利用／覆被类型对蒸散量的影响

为进一步探究土地利用/覆被类型对蒸散的影响，以2015年为例，统计该年不同土地利用/覆被类型的日蒸散量像元频率分布，分析不同土地利用/覆被面积变化所导致的日总蒸散量的变化情况（图7)。水体及河谷湿地的日蒸散曲线比较靠右，蒸散量较大，频率分布随着不同的季节有明显的变化。其次为耕地，夏季耕地的日蒸散量与河谷湿地的蒸散量较为接近，在 $2 { \sim } 6 \mathrm { m m }$ 波动。草地的蒸散量在 $0 . 5 { \sim } 4 ~ \mathrm { m m }$ 变化，不同季节草地的频率分布大致相同。沙地和农村居民点的日蒸散量最小，且像元频率分布比较集中，植被稀疏，涵养水源能力差，使得蒸散量活动受限，日蒸散量在 $0 { \sim } 2 ~ \mathrm { m m }$ 。总体来看，植被区蒸散量大于非植被区的蒸散量，蒸散主要与植被覆盖度和水分的供给条件有关[31]。蒸散量依次为：水体>沼泽地>耕地>草地 $>$ 沙地>农村居民点。

![](images/1709ae5b81d3495b43e8f8aef1e06a158307e8df1dcf318192226d45d05d48c5.jpg)  
图72015年不同土地利用类型ET值统计对比  
Fig.7 Statistical comparison of $E T$ values of different land use types in 2015

不同土地利用/覆被类型导致 $E T$ 差异的原因有：植被覆盖度及植被类型不同，4月植被返青，9月植被到了生长后期开始枯萎，加之流域大部分地区牧民开始打草，植被覆盖度降低，流域整体蒸散量较小。生长季沼泽植物密集，植被覆盖度高，植被的蒸腾作用大，沼泽湿地蒸散量就越大，这与沈欣等[32在白洋淀湿地生态系统的研究结果一致；土壤类型不同，研究区草地土壤类型主要有黑钙土、厚栗黄土等，沙地主要为荒漠风沙土，沼泽地主要为草原沼泽土，不同的土壤类型对于太阳辐射的吸收不同[33]；土壤含水量不同，沼泽地有锡林河补给，耕地基本配备喷灌设施，水分供给充足，在相同的条件下沼泽地和耕地的蒸发量要大于研究区其他土地利用类型[34]。农村居民点和沙地的蒸散量较低，一般农村居民点因其包含大量不透水层，导致地表水源补给减少，日蒸散作用也相应减弱，表现为"干岛"效应，其通过吸收太阳辐射能量使地表温度增加，造成感热高潜热低，因此蒸散发量较低[35]。沙地相比于农村居民点而言， $E T$ 一部分来自于表层土壤水及降水蒸发，还有一部分来自于低覆盖的沙地灌木丛、披碱草等覆沙植被的蒸腾，所以，ET值较农村居民点略高。

# 3.3.2气象因子对蒸散量的影响

10 10 (a)太阳辐射 $/ \mathrm { W } { \cdot } \mathbf { m } ^ { - 2 }$ （20 (b）平均气温/℃ O 。   
P/ y=0.026x+0.7903 。 090 中 心 P得 y =0.1338x +2.4454 8 。 R²=0.832 0。 。 0 R²=0.7083 国 。 0 H 8 88 。 。 中 8 @ 5 8080 5000 886 新 8 。 0   
燕2 8 8 8 8 0 0 0 50 100 150 200 250 300 -30 -20 -10 0 10 20 30 40 10 （c）饱和水汽压差/kPa 10 (d) 相对湿度/%y=0.0008x²-0.158x+9.1481   
t y=0865 80 0 0 。 。 高 R²=0.2584 。 80 。 8 08 888 %8   
4 6 。 8 8 8 。 8 0。 。 量4 。 888 8 90 8   
散 % 。 散 。 。 。   
燕2 全 。 06 蒸2 & 8 。 中 @ 87 0 0 0 1 2 3 0 20 40 60 80 100

图8是 $E T$ 与平均温度 $T .$ 、VPD、 $R _ { \mathrm { n } }$ 、RH之间的关系。可以看出， $E T$ 与 $R _ { \mathrm { n } }$ 的拟合效果最好，决定系数为0.83，其次为 $T$ 和 $V P D$ ，决定系数分别为0.71和0.63，而对 $R H$ 的响应程度最低，为 $0 . 2 6$ 。

由表3可知 $T .$ 、VPD和 $R _ { \mathfrak { n } }$ 与 $E T$ 呈正相关关系，分别为0.76、0.72、0.83。与RH呈负相关关系，为0.53。从敏感系数绝对值大小可看出， $E T$ 对 $R _ { \mathfrak { n } }$ 的变化最敏感， $R H$ 次之， $T$ 和VPD的敏感性较低。综合来看 $\scriptstyle { R _ { \mathrm { n } } }$ 是影响区域蒸散量变化的的主要因子。

表3气象要素敏感系数及其与 $E T$ 的相关系数  
Table2 Meteorological element sensitivity coefficient and correlation coeficient with ET   

<html><body><table><tr><td>气象要素</td><td>与ET相关系数</td><td>敏感系数</td></tr><tr><td>平均温度(T)</td><td>0.76**</td><td>0.31</td></tr><tr><td>饱和水汽压差(VPD)</td><td>0.72**</td><td>0.29</td></tr><tr><td>地表净辐射(Rn)</td><td>0.83**</td><td>0.76</td></tr><tr><td>相对湿度(RH)</td><td>-0.53**</td><td>-0.47</td></tr></table></body></html>

注：\*\*表示在0.01性水平(双侧)上显著相关。

从根本上来看，无论是植物蒸腾还是土壤蒸发，在植被体内水分和土壤水分发生相变汽化的过程中，太阳辐射是主要的能量来源，太阳辐射增加，导致气温和水温升高，水分蒸发速率增加。因此，日蒸散量与太阳辐射存在较好的线性关系，这与牛忠恩等[3研究中国陆地生态系统蒸散时空变化及其影响因素所得到的结论一致。沼泽湿地蒸散量与饱和水汽压呈正相关关系，但在饱和水汽压过大之后，饱和水汽压的增加反而抑制了蒸散量的增大，因为当饱和水汽压很大时，蒸腾作用强烈，引起气孔部分关闭，降低蒸腾失水，Liu等3在分析北京地区气候变化对蒸散量的影响得到相同的结论。空气相对湿度大，水汽蒸发强度小，这与韦振锋等[38研究陕西省蒸散量对气候因子的响应所得到的结果相同。区域蒸散量变化与驱动因子的关系十分复杂，定量化度量相关因子对流域蒸散的影响会在进一步的研究中加以完善。

# 4结论

（1）利用SEBAL模型估算的 $R _ { \mathrm { n } }$ ， $G$ 及 $E T$ 值与实测值较接近，故采用SEBAL模型估算锡林河流域上游的蒸散量具有可行性。

(2） $R _ { \mathfrak { n } }$ 和 $E T$ 具有较高的一致性，季节性变化显著，空间上呈现东高西低的趋势，河谷湿地的 $R _ { \mathrm { n } }$ 和 $E T$ 在生长季内保持较高的水平， $R _ { \mathfrak { n } }$ 值在 $4 0 0 { \sim } 7 5 0 \ \mathrm { W } { \cdot } \mathrm { m } ^ { - 2 }$ 之间， $E T$ 值在$2 . 4 2 { \sim } 1 0 . 6 7 \ \mathrm { m m } { \cdot } \mathrm { d } ^ { - 1 }$ ，沙丘裸地蒸散量较少，在 $5 \mathrm { m m }$ 以下。

（3）土地利用/覆被类型和气象因子是影响蒸散量时空变化的主要因素。不同土地利用类型蒸散量依次为：水体>沼泽地 $>$ 耕地 $>$ 草地 $>$ 沙地 $\cdot >$ 农村居民点；锡林河流域上游 $E T$ 与 $T$ ，VPD、 $R _ { \mathfrak { n } }$ 呈正相关，与RH呈负相关。从敏感系数来看， $E T$ 对 $R _ { \mathrm { n } }$ 的变化最敏感。

参考文献   
[1]汪步惟,张雪芹.1971—2014 年青藏高原参考蒸散变化及其归因[J].干旱区研 究,2019,36(2):269-279.[Wang Buwei,Zhang Xueqin.Change and atribution of reference evapotranspiration over the Tibetan Plateau during the period of 1971-2O14[J].Arid Zone Research.2019,36(2):269-279.]   
[2]王卫光,李进兴,魏建德,等.基于蒸散发数据同化的径流过程模拟[J].水科学进 展,2018,29(2):159-168.[Wang Weiguang,Li Jinxing,Wei Jiande,et al.Runoff simulation by hydrological model based on the assimilated evapotranspiration[J].Advances in Water Science.2018,29(2):159-168.]   
[3] RosenbergNJ，BladBL,VermaSB.Microclimate: the biological environment[M].Microclimate:the Biological Environment.Wiley,1983.   
[4] Xu C Y,Singh V P.Cross comparison of empirical equations for calculating potential evapotranspiration with data from Switzerland[J].Water Resources Management,2002,16(3):197-219.   
[5] Penman H L.Natural evaporation from open water,bare soil and grass[J].Proceedings of the Royal Society A Mathematical,Physical,and Engineering Sciences,193,120-145.   
[6] Monteith JI L.Evaporation and environment[J].Symposia of the Society for Experimental Biology,1965,19:205-234.   
[7] 刘国水,许迪,刘钰.空间观测尺度差异对蒸散量时间尺度扩展方法估值的影响[J].水利学 报,2012,43(8):999-1003.[Lu Goshui,Xu Di,Liu Yu.Influence of spatial scale variation on ET temporal upscaling methods[J].Journal of Hydraulic Engineering.2012,43(8):999-1003.]   
[8]李放,沈彦俊.地表遥感蒸散发模型研究进展[J].资源科学,2014,36(7):1478-1488.[Li Fang,Shen Yanjun.Progress in remote sensing-based models for surface heat and water fluxes[J].Resources Science,2014,36(7):1478-1488.]   
[9] Bastiaanssen W G M,Pelgrum H,Wang J,et al.A remote sensing surface energy balance algorithm for land (SEBAL):2.Validation[J].Journal of Hydrology,1998,212(1-4):213-229.   
[10] Allen R G,Tasumi M,Trezza R.Satellite-Based energy balance formapping evapotranspiration with internalized calibration (METRIC)—Model[J].Journal of Irrigation and Drainage Engineering,2007,133(4):380-394.   
[11] 周剑,程国栋,李新,等.应用遥感技术反演流域尺度的蒸散发[J].水利学 报,2009,40(6):679-687.[Zhou Jian,Cheng Guodong,Li Xin,et al.Application of remote sensing technology to estimate river basin evapotranspiration[J].Journal of Hydraulic Engineering,2009,40(6):679-687.]   
[12] Losgedaragh S Z,Rahimzadegan M.Evaluation of SEBS,SEBAL,and METRIC models inestimation of the evaporation from the freshwater lakes (Case study:Amirkabir dam,Iran)[J].Journal of Hydrology,2018:S0022169418302798.   
[13] 秦孟晟,郝璐,郑箐舟,等.秦淮河流域土地利用/覆被变化对蒸散量变化的贡献[J].中 国农业 气 象 ,2019,40(5):269-283.[QinMengsheng,Hao Lu,Zheng Qingzhou,et al.Contributions of land use/cover change to the change of evapotranspiration in Qinhuai River Basin[J].Chinese Journal of Agrometeorology,2019,40(5):269-283.]   
[14] 周玲,张丽,许君一,等.基于 SEBAL 模型的漓江流域蒸散量变化分析[J].水土保持研 究,2015,22(4):32-337.[Zhou Ling,Zhang Li,Xu Junyi,et al.Analysis of the variations of evapotranpiration in Lijiang River Basin based on SEBAL model[J].Research of Soil and Water Conservation,2015,22(4): 332-337.]   
[15] 刘曼晴,胡德勇,于琛,等.辽河三角洲湿地生长季蒸散量时空格局及影响因素分析[J]. 生态学报,2020,40(2):701-710.[Liu Manqing,Hu Deyong,Yu Chen,et al.Temporal and spatial change characteristics of growing season evapotranspiration and its cause analysis in Liaohe River delta wetland,China[J].Acta Ecologica Sinica,2020,40(2):701-710.]   
[16] 连晋姣,黄明斌,李杏鲜,等.夏季黑河中游绿洲样带蒸散量遥感估算[J].农业工程学 报 ,2014,30(15):120-129,340.[Lian Jinjiao,Huang Mingbin,Li Xingxian,et al.Evapotranspiration estimation for oasis transect in middle reach of Heihe River Basin based on remote sensing[J].Transactionsof the Chinese Society of Agricultural Engineering,2014,30(15):120-129,340.]   
[17] Lee Y,Kim S.The modified SEBAL for mapping daily spatial evapotranspiration of SouthKoreausingthreefluxtowersandTerra MODISData[J].Remote Sensing,2016,8(12):983.   
[18] 王慧敏,郝祥云,朱仲元.基于干旱指数与主成分分析的干旱评价—以锡林河流域 为例[J].干旱区研究,2019,36(1):95-103.[WangHuimin,HaoXiangyun,Zhu Zhongyuan.Drought assessment based on drought index and principal component analysis:a cased study in the Xilin River Basin[J].Arid Zone Research,2019,36(1):95-103.   
[19] 焦玮,朱仲元,宋小园,等.基流分割方法在锡林河流域适用性分析[J]).干旱区研 究,2017,34(1):26-35.[Jiao Wei,Zhu Zhongyuan,Song Xiaoyuan,et al.Suitability analysis of baseflowseparation methodsintheXilinRiverBasin[J].AridZone Research,2017,34(1):26-35.]   
[20] 高凯,朱铁霞,其兵,等.围封对内蒙古锡林河流域羊草草原主要构成植物个体、枯落物 及群落热值的影响[J].应用生态学报,2012,23(4):998-1002.[Gao kai,Zhu Tiexia,Wang qibing,et al.Effects of enclosure on the caloric values of main plant species,liters,and communities in Leymus chinensis steppe in Xilin River Basin,Inner Mongolia[J].Chinese Journal of Applied Ecology,2012,23(4):998-1002.]   
[21] 张艳霞,于瑞宏,薛浩,等.锡林河流域径流量变化对气候变化与人类活动的响应[J].干 旱区研究,2019,36(1):67-76.[Zhang Yanxia,Yu Ruihong,Xue Hao,et al.Response of runoff volume change to climate change and human activities in the Xilin River Basin[J].Arid Zone Research,2019,36(1):67-76.]   
[22] Bastiaanssen W G M,Pelgrum H,Wang J,et al.A remote sensing surface energy balance algorithm for land (SEBAL):2.Validation[J].Journal of Hydrology,1998,212(1-4):213-229.   
[23] Allen R G .Using the FAO-56 dual crop coefficient method over an irrigated region as part of an evapotranspiration intercomparison study[J].Journal of Hydrology,2000,229(1-2):27-41.   
[24] Bastiaanssen W G M.SEBAL-based sensible and latent heat fluxes in the irrigated Gediz Basin,Turkey[J].Journal of Hydrology(Amsterdam),2000,229(1-2):0-100.   
[25] Allen R G,Pereira L S,Raes D et al.Crop evapotranspiration-guidelines for computing crop water requirements.FAO Irrigation and Drainage Paper 56.FAO,1998.   
[26] 顾峰,丁建丽,葛翔宇,等.基于 Sentinel-2数据的干旱区典型绿洲植被叶绿素含量估算 [J].干旱区研究,2019,36(4):924-934.[Gu Feng,Ding Jianli,Ge Xiangyu,et al.Estimation of chlorophyll content of typical oasis vegetation in arid area based on Sentinel-2 data[J].Arid Zone Research,2019,36(4):924-934.]   
[27] 董旭光,顾伟宗,王静,等.影响山东参考作物蒸散量变化的气象因素定量分析[J].自然 资源学报,2015,30(5):810-823.[Dong Xuguang,Gu Weizong,Wang Jing,et al.Quantitative analysis of climate factors for potential evapotranspiration changes in Shandong[J].Journal of Natural Res0urces,2015,30(5):810-823.]   
[28] 侯琼,王英舜,杨泽龙,等.内蒙古典型草原作物系数的动态模拟与确定[J].植物生态学 报,2010,34(12):1414-1423.[Hou Qiong,Wang Yingshun,Yang Zelong,et al.Dynamic simulationanddefinitionofcropcoefficientfortypicalsteppeinInner Mongolia,China[J].Chinese Journal of Plant Ecology,2010,34(12):1414-1423.]   
[29] 韩玲,赵成章,徐婷,等.不同土壤水分条件下洪泛平原湿地芨芨草叶片厚度与叶脉性 状的关系[J].植物生态学报,2017,41(5):529-538.[Han Ling,Zhao Chengzhang,Xu Ting,et al.Relationships between leaf thickness and vein traits of Achnatherum splendens under different soil moisture conditions in a flood plain wetland,Heihe River, China[J].Chinese Journal of Plant Ecology,2017,41(5):529-538.]   
[30]Cowley G S,Niemann J D,Green T R,et al.Impacts of precipitation and potential evapotranspiration patterns on downscaling soil moisture in regions with large topographic relief[J].Water Resources Research,2017,53(2):1553-1574.   
[31] 李宝富,陈亚宁,李卫红,等.基于遥感和 SEBAL模型的塔里木河干流区蒸散发估算[J]. 地理学报,2011,66(9):1230-1238.[Li Baofu,Chen Yaning,Li Weihong,et al.Remote sensing and the SEBAL model for estimating evapotranspiration in the Tarim River[J].Acta Geographica Sinica,2011,66(9):1230-1238.]   
[32] 沈欣,欧阳志云,段晓男,等.白洋淀湿地生态系统水分条件遥感监测方法[J].生态学 报,2008,28(10):5033-5038.[Shen Xin,OuYang Zhiyun,DuanXiaonian,etal.Inferring Baiyangdian wetland soil moisture from remote sensing :method research[J].Acta Ecologica Sinica,2008,28(10):5033-5038.]   
[33] Guo Y M,Cheng J.Feasibility of estimating cloudy-sky surface longwave net radiation using satellite-derived surface shortwave net radiation[J].Remote Sensing,2018,10(4):596-630.   
[34] 曾丽红,宋开山,张柏,等.2000年至 2008 年松嫩平原生长季蒸散量时空格局及影响因 素分析[J].资源科学,2010,32(12):2305-2315.[Zeng Lihong,Song Kaishan,Zhang Bai,et al.Analysis of spatiotemporal variations in evapotranspiration and its influencing factors over the Songnen Plain in the growing season during the period 2Oo0-2O08[J].Resources Science,2010,32(12):2305-2315.]   
[35] 张柏,宋开山,王宗明,等.基于 SEBAL模型的别拉洪河流域典型生态系统蒸散量估算 [J].资源 科 学 ,2009,31(10):1755-1763.[Zhang Bai,Song Kaishan,Wang Zongming,et al.Estimation of evapotranspiration for typical ecosystems in the Bielahong River Basin based on SEBAL[J].Resources Science,2009,31(10):1755-1763.]   
[36] 牛忠恩,胡克梅,何洪林,等.2000—2015 年中国陆地生态系统蒸散时空变化及其影响 因素[J].生态学报,2019,39(13):4697-4709.[Niu Zhongen,Hu Kemei,He Honglin,et al.The spatial-temporal patterns of evapotranspiration and its influencing factors in Chinese terrestrial ecosystem from 2000 to 2015[J].Acta Ecologica Sinica,2019,39(13):4697-4709.]   
[37] Liu H,Li Y,Josef T, et al. Quantitative estimation of climate change effects on potential evapotranspiration in Beijing during 1951-2O1O[J]. Journal of Geographical Sciences, 2014, 24(1): 93-112.   
[38] 韦振锋,陈思源,黄毅.1981一2010 年陕西潜在蒸散量时空特征及其对气候因子的响 应[J].地理科学,2015,35(8):1033-1041.[Wei Zhenfeng,Chen Siyuan,Huang Yi.Spatial and temporal characteristics of potential evaporation and climatic factors on the impact in Shaanxi Province in 1981-20i0[J].Scientia Geographica Sinica,2015,35(8):1033-1041.]

# Estimation of evapotranspiration and its spatiotemporal characteristics in the upper reaches of the Xilin River Basin

ZHOU Ya-jun1,LIU Ting-xi12,DUAN Li-min12,WANG Yi-xuan2,LI Xial,LI Ming-yag (1.WaterConservancyandCivil Engineering Collge,Inner Mongolia Agricultural University,Inner Mongolia Hohhot Oloo18,China;2.Inner Mongolia Key Laboratory of Water Resource Protection and Utilization, Inner MongoliaHohhot O10018,China)

Abstract:To reveal the evapotranspiration and its temporal and spatial distribution characteristics in the upper reaches of the Xilin River Basin,The ETestimation of 12 growth seasons during 2O15—2017 was conducted using a Surface Energy Balance Algorithm for Land (SEBAL）model with Landsat 8 data and meteorological observations,and analysis of its temporaland spatialpatterns and its influencing factors.Theresults show that :(1) The inversion parameter values of the model are wellfitted to the measured values,the decision coefficients of surface net radiation，soil heat flux, $E T$ are 0.80, 0.65,O.86.(2) The spatial distribution of $R _ { \mathrm { n } }$ and $E T$ at the same period has a high consistency，and the overall trend is east-high and low-west，with significant spatial differentiation characteristics.The daily $E T$ value in April is $\mathrm { 0 { \sim } 4 . 6 7 ~ m m }$ ,from May to July,the daily $E T$ increased overall,the maximum value is $1 0 . 3 2 \mathrm { m m }$ ，it's decreased fromO to $3 . 3 4 ~ \mathrm { m m }$ from September to October. The evapotranspiration of different land-use types is:water $>$ swamp $>$ arable land $>$ grassland $>$ sandy land $>$ rural settlements.(3）The evapotranspiration is positively correlated with the average temperature,saturated vapor pressure,and solar net radiation,negatively correlated with relative humidity, $E T$ is most sensitive to changes in solar radiation.

Key words: SEBAL model; Evaporation; The space-time characteristics;Xilin River Basin