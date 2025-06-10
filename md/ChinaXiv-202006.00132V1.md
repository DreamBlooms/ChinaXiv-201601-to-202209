# 基于MODIS的青海草地产草量变化遥感分析

黄鑫，刘建红²，申克建³4，刘咏梅,²，王雷1,2

（1西北大学城市与环境学院，陕西西安710127；2西北大学陕西省地表系统与环境承载力重点实验室，陕西西安710127；3青海省农牧业遥感中心,青海西宁810007；4 农业部规划设计研究院,北京100125)

摘要：青海省属于全国四大牧区之一，及时监测草地植被长势、准确估算牧草产量对青海牧区可持续发展与生态保护具有重要意义。草地产草量遥感估算主要基于植被指数与地面实测数据的统计关系,但是估算涉及植被指数、统计模型和建模指标等因素,不同组合建立的估算模型的精度不同。本文基于青海省MODIS 数据与地面实测产草量数据，选择了6种植被指数 $( N D V I , E V I , R V I ,$ （204号$D V I \sqrt { R D V I \sqrt { M S A V I } } )$ 、5种统计模型（简单线性模型、二次多项式模型、幂函数模型、指数函数模型、对数函数模型)以及3种建模指标(植被指数年度最大值 ${ { \cal { W } } _ { \operatorname* { m a x } } }$ 、植被指数生长季累积值 $V I _ { \mathrm { s e a s o n - c u m } }$ 、植被指数年度累积值 $V I _ { \mathrm { a n n u a l - c u m } }$ ),研究不同组合下估算模型的精度差异，并从中选出最优产草量估算模型,用于估算青海省2015年和2016年的产草量。结果表明：(1)6种植被指数中,基于NDVI的产草量估算精度最高;非线性模型的估算精度高于线性模型,尤其是指数模型,适用于大多数草地类型产草量的估算;基于NDVI年度最大值的估算模型对大多数草地类型都具有最高的决定系数$( R ^ { 2 } )$ 。(2)从干重来看，高产草量区 $( \mathbf { \nabla } > 1 \ 2 0 0 \ \mathrm { k g } \cdot \mathrm { h m } ^ { - 2 } ,$ )主要位于青海东部的高寒草原，中等产草量区 $\mathrm { ( 6 0 0 \sim 1 ~ 2 0 0 ~ k g ~ \cdot ~ h m ~ ^ { - 2 } ~ ) }$ 位于青海南部和东部的高寒草原和禾草草原，低产草量区( $< 6 0 0 ~ \mathrm { k g }$ ： $\mathrm { h m } ^ { - 2 }$ )位于青海西部和北部的高寒草甸、高寒草原、高寒荒漠和盐生草甸。（3)与2015 年相比，2016 年青海省干草总产量减少 $3 1 . 6 0 \times 1 0 ^ { 4 } \mathrm { ~ t ~ }$ ，减幅为 $1 . 3 6 \%$ 。其中，禾草草原和高寒草甸的减产幅度最大，而荒漠草原和盐生草甸的产量则有所增加。本文可为草地产草量遥感估算的研究和实践提供参考。

关键 词：青海省；产草量；遥感；MODIS；植被指数文章编号

草地长势监测、产草量估算和载畜能力评估对牧区的生态保护和可持续发展具有重要意义[1-2]产草量不仅能直接反映草原植被生产力，也是开展草原载畜能力评估的基础[3-5]。传统的产草量测定方法耗时耗力，难以在宏观尺度上大规模应用。自20世纪90年代以来，大量研究通过建立遥感植被指数和地面样方产草量的统计模型,对草地产草量及其区域变化进行估算分析[4,6-12]。研究表明,产草量与光谱植被指数之间有很强的关联性。在各种植被指数中，归一化差值植被指数（NormalizedDifferenceVegetationIndex,NDVI)最为常用,是监测植被生长活动的良好指标[13-15],也是适用于低生物量环境的植被指数。此外，许多其它植被指数，如比值植被指数（Ratio Vegetation Index,RVI）[16]、重归一化差值植被指数（Renormalized DifferenceVegetationIndex,RDVI）、增强型植被指数（EnhancedVege-tation Index , $E W I { \mathrm { ~ } }$ [12,17-19]、差值植被指数（DifferenceVegetationIndex,DVI）垂直植被指数（PerpendicularVegetation Index,PVI)[20]、修正型土壤调整植被指数（Modified Soil Adjusted Vegetation Index，MSA-VI)[19]和优化土壤调整植被指数(Optimized Soil Ad-justedVegetation Index,OSAVI)[19]等,也都被用来估算产草量或生物量。

但是基于统计关系建立的产草量估算模型具有

很强的地域性[2I],由于自然条件的差异,不同的植被指数可能适用于不同的草地类型。如LI等[通过比较发现，对于低地草甸、山地荒漠草原和山地草甸，RVI与鲜草产量的相关性比NDVI更好，但对于平原荒漠草原则相反。而YU等[12]和傅新宇等[17]的研究表明，NDVI和EVI在估算草地产草量时的精度存在差异，对于大部分高寒草地而言，基于NDVI的估算精度更高。类似地,杨秀春等[19]也发现,相比于其他植被指数，NDVI和SAVI更适合用于监测北方农牧交错带的草原生长状况。此外,在产草量估算的统计模型方面，有研究表明非线性模型往往比线性模型的拟合效果更好，尤其是指数模型和幂函数模型[4,11,16,22]。并且前人研究多直接采用植被指数最大值来估算产草量，关于植被指数累积值或均值是否能用于产草量估算的研究相对较少[18,23]  
O

草地产草量遥感估算涉及植被指数、统计模型和建模指标等因素，不同组合建立的估算模型的精度不同。尽管前人已在此方面进行了大量的研究，但对于青海草原而言，哪种植被指数、哪种统计模型、哪种指标最适宜用于产草量估算还有待进一步研究。针对以上问题,本文基于青海省草地地面实测产量数据和MODIS数据，选择了6种植被指数$( N D V I , E V I , R V I , D V I , R D V I , M S A V I ) ,$ 5种统计模型（简单线性模型、二次多项式模型、幂函数模型、指数函数模型、对数函数模型)以及3种建模指标（年度植被指数最大值 ${ { V } _ { \operatorname* { m a x } } }$ 、植被指数生长季累积值$V I _ { \mathrm { s e a s o n – c u m } }$ 、植被指数年度累积值 $V I _ { \mathrm { a n n u a l - c u m } }$ )来研究不同估算模型的精度差异。首先研究哪种植被指数和估算模型最适合用于估算青海省不同草地类型的产草量，然后比较基于3种建模指标的产草量估算精度差异，最终选出最优产草量估算模型用于估算2015年及2016年的青海草原产草量并进行变化分析，以期为草地产草量遥感估算的研究和实践提供参考。

# 研究数据与方法

# 1.1 研究区概况

青海省位于中国西北内陆、青藏高原东北部，全省下辖2个市6个州（图1），地理坐标介于$8 9 ^ { \circ } 3 5 ^ { \prime } \mathrm { E } \sim 1 0 3 ^ { \circ } 0 4 ^ { \prime } \mathrm { E } \mathrm { ~ } . 3 1 ^ { \circ } 3 9 ^ { \prime } \mathrm { N } \sim 3 9 ^ { \circ } 1 9 ^ { \prime } \mathrm { N }$ 之间。全省平均海拔在 $3 \ 0 0 0 \ \mathrm { m }$ 以上，属高原大陆性气候,夏季短暂，年均温在 $- 6 \sim 9 \mathrm { { ^ { c } } }$ 之间，平均年降水量在

![](images/84cfc7569b737e843c4a618e28a68c22efd30b4e8cfd83adcbc024887d8a6417.jpg)  
图1青海省草地类型及地面样点分布图  
Fig.1Grassland types and the ground survey samples in Qinghai Province

$2 5 0 \sim 5 5 0 ~ \mathrm { m m }$ 之间。青海省是我国主要牧区之一，天然草地面积占我国草地总面积的 $1 0 . 7 2 \%$ ，达$4 . 1 9 \times 1 0 ^ { 7 } ~ \mathrm { h m } ^ { 2 }$ 。其中,可利用草地面积约为 $3 . 8 7 \times$ $1 0 ^ { 7 } ~ \mathrm { h m } ^ { 2 }$ ,主要分布在东北部的祁连山地、西南部的青南高原以及西北部的柴达木盆地区，主要草地类型包括高寒草原、禾草草原、高寒草甸、高寒荒漠等[24]

# 1.2 数据来源

1.2.1地面调查数据研究区2015年及2016年的产草量地面实测数据来源于青海省草原监理中心的地面调查样方，所有样方的调查时间集中在每年的7月20日～8月31日之间，该时期是草地植被生长最旺盛的时期。调查时,矮小灌木及草本植物的样方大小为 $1 \mathrm { ~ m ~ } { \times } 1 \mathrm { ~ m ~ }$ ,灌木及高大草本样方的大小为 $1 0 \ \mathrm { m } \times 1 0 \ \mathrm { m } ^ { [ 2 5 ] }$ 。调查内容包括经纬度、草地类型、产草量鲜重和样方平均海拔高度等。草地类型图(图1)源于2007年出版的《中华人民共和国植被图 $\left( 1 \colon 1 ~ 0 0 0 ~ 0 0 0 \right) \rangle$ 。

为保证地面实测数据的可靠性，本文首先将记录不完整的样方标记为无效样方，然后再根据样方产草量的总体标准差，将出现较大偏差的样方标记为异常样方，将两者一并剔除。若出现2个或多个样方落在同一像元内的情况，则取其平均值作为一个样点使用。经过筛选最终得到2015年的有效样点数为234个，2016年的有效样点数为352个，具体见表1和图1。

因沼泽草甸没有地面实测数据（表1），且其面积所占比例非常小（图1），所以将其排除在后续分析中。尽管高寒荒漠缺少地面实测数据，但其所占面积比较大，由于它与高寒草原的地理位置和植被特征接近，因此采用高寒草原的估产模型估算其产草量。

表1各草地类型地面样点数量  
Tab.1Number of field samples for each grassland type   
表26种植被指数计算公式  

<html><body><table><tr><td>草地类型</td><td>2015 年样点数</td><td>2016年样点数</td></tr><tr><td>高寒荒漠</td><td>0</td><td>0</td></tr><tr><td>禾草草原</td><td>28</td><td>54</td></tr><tr><td>荒漠草原</td><td>7</td><td>20</td></tr><tr><td>高寒草原</td><td>59</td><td>74</td></tr><tr><td>盐生草甸</td><td>5</td><td>8</td></tr><tr><td>高寒草甸</td><td>135</td><td>196</td></tr><tr><td>沼泽草甸</td><td>0</td><td>0</td></tr><tr><td>总计</td><td>234</td><td>352</td></tr></table></body></html>

1.2.2遥感数据本文结合了2种 MODIS 的产品数据－ MOD09Q1 和 MOD09A1。MOD09Q1和MOD09A1的时间分辨率均为8d，但前者只包含红光波段和近红外波段的反射率波段，空间分辨率为$2 5 0 \mathrm { ~ m ~ }$ ,而后者包含蓝光、绿光波段在内的一共7个波段的反射率波段，空间分辨率为 $5 0 0 \mathrm { ~ m ~ }$ 。本文将从MOD09A1数据中提取的蓝光波段重采样至250m，然后结合MOD09Q1数据中的红光波段和近红外波段，计算了6种植被指数 $( N D V I , E V I , R V I , D V I ,$ （204号RDVI、MSAVI），计算公式如表2所示。

Tab.2Equations of the six vegetation indices   

<html><body><table><tr><td>植被指数</td><td>公式</td></tr><tr><td>NDV[26]</td><td>PNIR+PR NDVI =PNIR -PR</td></tr><tr><td>EVI[27]</td><td>EVI = 2.5(pNIR-PR) PNIR +6.0pR-7.5pR+1</td></tr><tr><td>RVI[28]</td><td>PR RVI=PNIR</td></tr><tr><td>DVI[28]</td><td>DVI = pNIR-PR[28]</td></tr><tr><td>RDVI[29]</td><td>RDVI= PNIR-PR √PNIR+PR</td></tr><tr><td>MSAVI: MSAVI[30]</td><td>1 2pNIR +1-√(2ρNIR +1)²-8(ρNIR -PR) 2</td></tr></table></body></html>

注： ${ \mathrm { : } } \rho _ { N I R } \circ { \mathcal { P } } _ { R }$ 和 $\rho _ { R }$ 分别表示近红外波段、红光波段和蓝光波段的反射率

受海拔高度和水汽的影响，研究区的大气状况多变，数据中存在的噪声会影响产草量估算的准确性。因此，本文通过线性插值对突然上升或下降的点进行替换，然后计算了以下三项建模指标：(1)全年植被指数最大值,记为 ${ { V } _ { \operatorname* { m a x } } }$ 。（2)生长季植被指数累积值,记为 $V I _ { \mathrm { s e a s o n - c u m } }$ ;(3)全年植被指数累积值,记为 $V I _ { \mathrm { a n n u a l - c u m } }$ 。青海省草地一般在每年的5月上旬返青，在每年的9月底进入枯黄期，因此本文将草地的生长季定义为5\~9月。

# 1.3 研究方法

1.3.1产草量估算方法首先按不同草地类型，建立6种植被指数 $( N D V I , E V I , R V I , D V I , R D V I , M S A -$ $\overrightarrow { V I }$ 的 ${ { \cal { W } } _ { \operatorname* { m a x } } }$ 与对应地面样点鲜草产量的回归模型，从中选出决定系数 $( R ^ { 2 } )$ 最高的植被指数作为最优植被指数。然后，将最优植被指数的三项建模指标（204 $( \underbrace { V I } _ { \mathrm { m a x } } \underbrace { V I } _ { \mathrm { s e a s o n - c u m } } \underbrace { V I } _ { \mathrm { a n n u a l - c u m } } )$ 和5 种统计回归模型(线性模型、多项式模型、指数函数模型、幂函数模型、对数函数模型)两两组合，建立鲜草产量估算模型，再采用回归方程决定系数( $\cdot R ^ { 2 } \cdot$ ）、RMSE和REE来评价各模型精度，从中选出最优模型估算鲜草产量。最后,根据《中国草地资源》[31]中的干鲜比折算系数（表3），将鲜草产量换算成干草产量并进行分析。

Tab.3Conversion coefficient for fresh grass yield to hayyieldfor each grassland type   

<html><body><table><tr><td>草地类型</td><td>折算系数</td></tr><tr><td>高寒荒漠</td><td>1.0/2.5</td></tr><tr><td>禾草草原</td><td>1.0/3.0</td></tr><tr><td>荒漠草原</td><td>1.0/3.0</td></tr><tr><td>高寒草原</td><td>1.0/3.0</td></tr><tr><td>盐生草甸</td><td>1.0/3.2</td></tr><tr><td>高寒草甸</td><td>1.0/3.2</td></tr></table></body></html>

1.3.2模型验证在建立产草量估算模型前,将样点数据分为建模样本和检验样本两部分，其中建模样本约占4/5,检验样本约占1/5，各草地类型建模样点数及检验样点数具体如表4所示。其中，有2种草地类型由于样点数量过少，无法对其模型精度进行检验(表4)。在验证模型精度时，采用回归方程的决定系数 $R ^ { 2 } \ 、 R M S E ^ { [ 2 3 , 3 2 - 3 3 ] }$ 和 $R E E ^ { [ 3 4 - 3 5 ] }$ 三项指标来评价模型精度，公式如(1)和(2)所示：

$$
R M S E = { \sqrt { \frac { \displaystyle \sum _ { i = 1 } ^ { m } \left( Y _ { i } - Y _ { i } ^ { ' } \right) ^ { 2 } } { n } } }
$$

$$
R E E = R M S E / { \bar { Y } }
$$

式中： $Y _ { i }$ 为第 $\mathbf { \chi } _ { i }$ 个样本的实测鲜草产量 $( \mathrm { k g } \cdot \mathrm { h m } ^ { - 2 }$ ）；$Y _ { i } ^ { ' }$ 为第 $i$ 个样本的估算鲜草产量( $\mathrm { ^ { ' } k g } \cdot \mathrm { h m } ^ { - 2 }$ ）； $\bar { Y }$ 为$Y _ { i }$ 的平均数； $n$ 为检验样本数。

表3各草地类型干鲜比折算系数  
表4各草地类型建模及检验样点数  
Tab.4Modeling and validation samples of each grassland type   

<html><body><table><tr><td rowspan="3">草地类型</td><td colspan="2">建模样点数</td><td colspan="2">检验样点数</td><td colspan="2">总样点数</td></tr><tr><td>2015年 2016年</td><td></td><td>2015年 2016年</td><td></td><td>2015年</td><td>2016年</td></tr><tr><td>禾草草原</td><td>22</td><td>43</td><td>6</td><td>11</td><td>28</td><td>54</td></tr><tr><td>荒漠草原</td><td>7</td><td>16</td><td>0#</td><td>4</td><td>7</td><td>20</td></tr><tr><td>高寒草原</td><td>48</td><td>58</td><td>11</td><td>16</td><td>59</td><td>74</td></tr><tr><td>盐生草甸</td><td>5</td><td>8</td><td>0#</td><td>0#</td><td>5</td><td>8</td></tr><tr><td>高寒草甸</td><td>109</td><td>155</td><td>26</td><td>41</td><td>135</td><td>196</td></tr><tr><td>总计</td><td>191</td><td>280</td><td>43</td><td>72</td><td>234</td><td>352</td></tr></table></body></html>

注：#表示由于没有足够的样点，故将所有样点用于建模使用，不预留检验样点

# 2 结果与分析

# 2.1最优产草量估算植被指数

基于6种植被指数全年最大值( ${ { V I } _ { \operatorname* { m a x } } }$ ),本文建立了2015年和2016年各草地类型的鲜草产量估算模型。以2016年为例，各估算模型的决定系数$\scriptstyle ( R ^ { 2 } )$ 如图2所示。在大多数情况下,基于 $N D V I _ { \operatorname* { m a x } }$ 、$R D V I _ { \operatorname* { m a x } }$ 和 $R V I _ { \operatorname* { m a x } }$ 的产草量估算精度更高。从不同草地类型来看，对于禾草草原和荒漠草原，无论使用何种模型， $N D V I _ { \operatorname* { m a x } }$ 都是产草量估算的最优植被指数。其中,禾草草原的二次多项式模型 $R ^ { 2 }$ 最高，为0.79;

![](images/1163a11316e543670564cdf4ad2dd33a09adcdafeb9c97f802f61fdbae8b3462.jpg)  
注：M1线性模型;M2二次多项式模型;M3幂函数模型;M4 指数函数模型;M5对数函数模型  
图22016年植被指数全年最大值与鲜草产量的回归模型决定系数

Fig.2 $\boldsymbol { R } ^ { 2 }$ of regression model between the annual maximum of vegetation index and fresh grass yield in 20荒漠草原的幂函数模型 $R ^ { 2 }$ 最高，为0.81。对于高寒草原和高寒草甸， $N D V I _ { \operatorname* { m a x } }$ 在大多数情况下的估算精度更高。其中，基于指数模型的 $R ^ { 2 }$ 最高，分别为0.85和0.72。对于盐生草甸而言，在大多数情况下除 $D V I _ { \operatorname* { m a x } }$ 外,其他植被指数的 $R ^ { 2 }$ 非常接近。其中,基于 $D V I _ { \operatorname* { m a x } }$ 的二次多项式模型 $R ^ { 2 }$ 最高，达0.95。综合来看，在大多数情况下非线性模型比线性模型的拟合效果更好，基于NDVI的估算模型相较于其他植被指数具有更高的决定系数 $( R ^ { 2 } )$ 。2015年所得结果的趋势与2016年一致。

![](images/7904287ca89521b2743b7e0f0e2c75d7013e5560bbe7d7271b860e6d6c579f09.jpg)  
黄鑫等：基于MODIS的青海草地产草量变化遥感分析  
  
Fig.3Validations of estimationmodelsbased ondifferentmetrics in 2016

# 2.2最优产草量估算模型

根据上述分析，进一步比较了基于NDVI的全年最大值( $\cdot N D V I _ { \operatorname* { m a x } }$ ）、生长季累积值 $( N D V I _ { \mathrm { s e a s o n - c u m } } )$ 年度累积值 ${ } ^ { ' } N D V I _ { \mathrm { { a n n u a l - c u m } } } { } ~ \cdot$ )的产草量估算模型精度。以2016年为例（图3），对于荒漠草原、高寒草原、高寒草甸和盐生草甸而言,基于 ${ { \cal { W } } _ { \operatorname* { m a x } } }$ 、 $V I _ { \mathrm { s e a s o n – c u m } } \ \mathrm { , }$ （204号$V I _ { \mathrm { a n n u a l - c u m } }$ 这3种指标的产草量估算模型的 $R ^ { 2 }$ 非常接近,而对于禾草草原,基于 $N D V I _ { \operatorname* { m a x } }$ 的产草量估算模型的 $R ^ { 2 }$ 明显高于基于另外2种指标的估算模型。此外,在大多数情况下，基于 $N D V I _ { \operatorname* { m a x } }$ 的估算模型的RMSE低于基于 $N D V I _ { \mathrm { s e a s o n - c u m } }$ 和基于 $N D V I _ { \mathrm { a n n u a l - c u m } }$ 的估算模型,而模型精度(1-REE)高于基于 $N D V I _ { \mathrm { s e a } }$ $\scriptstyle \operatorname { s o n - c u m }$ 和基于 $N D V I _ { \mathrm { a n n u a l - c u m } }$ 的估算模型。因此,综合$R ^ { 2 } , R M S E$ 和模型精度这三项指标,基于 $N D V I _ { \operatorname* { m a x } }$ 的

估算模型效果最好，最适合青海省的牧草产量估算。  
2015 年所得结果的趋势与2016年一致。

通过上述分析选出2015年及2016年各草地类型的最优估产模型。考虑到使用不同植被指数和统计模型可能会产生潜在的不确定性，因此选择最优估产模型时，在精度相差不大的情况下采用相同的植被指数和统计模型，最终结果如表5所示。

# 2.3产草量空间分布

基于上述各草地类型的最优估产模型计算鲜草产量后，再乘以表1中列出的转换系数得到干草产量。2015年及2016年青海省鲜草产量和干草产量的空间分布如图4所示。结合图1可知，不同草地类型及不同地区的产草量存在明显的差异。产草量的空间分布格局主要与草地类型、海拔、地形等有关。从干重来看,产草量较高的区域 $\mathit { \Omega } ^ { \prime } > 1 \ 2 0 0 \ \mathrm { k g }$ ：$\mathbf { h } \mathbf { m } ^ { - 2 }$ )主要分布在东部高寒草原;中等产量区（600$\sim 1 \ 2 0 0 \ \mathrm { k g } \cdot \mathrm { h m } ^ { - 2 } ,$ )分布在南部和东部的高寒草原以及禾草草原;低产量区（ $< 6 0 0 \mathrm { ~ k g ~ } \cdot \mathrm { ~ h m } ^ { - 2 }$ )主要分布在西部和北部的高寒草甸、高寒草原、高寒荒漠以及盐生草甸。

# 2.4产草量变化分析

2.4.1不同行政区的产草量变化2015年和2016年青海省各州市产草量及其变化情况如表6所示。以2016年为例，最大的3个干草产区是南部和西部的玉树州、果洛州和海西州，干草产量共计 $1 . 5 5 \times$ ${ 1 0 } ^ { 7 }$ t,占全省总产量的 $6 7 . 6 3 \%$ 。此外,有6个地区的平均干草单产超过 $5 0 0 \ \mathrm { k g } \cdot \mathrm { h m } ^ { - 2 }$ ,主要位于青海省东南部，包括黄南州、西宁市、海北州、海东市、果洛州和海南州;平均干草单产低于 $5 0 0 \ \mathrm { k g } \cdot \mathrm { h m } ^ { - 2 }$ 的地区主要位于西北部的海西州和玉树州。尽管青海省西部地区的干草产量占全省很大比例，但由于地形、气候等自然条件恶劣，其干草单产远低于东南部地区，而东南部地区虽然干草单产较高，但由于草原面积相对较小,其干草产量仅占全省的一小部分。

图5表示了青海省2015—2016年干草产量的变化情况。与2015年的产量相比，2016年海东市和黄南州的产量显著增加，超过 $5 \%$ 。如图5b所示，这两个地区干草产量增加大于 $1 5 0 \ \mathrm { k g } \cdot \mathrm { h m } ^ { - 2 }$ 的像元比例超过 $3 5 \%$ 。此外,海南州东部、玉树州南部、果洛州东部以及海北州的一些地区也出现了显著的增长。从绝对产量来看，黄南州增产量最高，达$1 3 . 9 9 \times 1 0 ^ { 4 } \mathrm { ~ t ~ }$ ,而海西州减产量最高，达 $4 3 . 9 8 \times 1 0 ^ { 4 }$ t。减产地区主要集中在海西州东部、果洛州北部和海南州西部，其中海西州有 $7 5 \%$ 以上的草地产量下降,干草总产量下降了 $1 2 . 9 8 \%$ 。尽管青海省部分地区的产量大幅增加，但由于海西州及玉树州北部的产量普遍下降，导致2016年全省干草总产量比2015年减少 $3 1 . 6 0 \times 1 0 ^ { 4 } \mathrm { ~ t ~ }$ ,减产幅度为 $1 . 3 6 \%$ 。

# 2.4.2不同草地类型的产草量变化

青海省2015年和2016年各草地类型的产草量及其变化情况如表7和图6所示。以2016年为例，前三大产草草地类型为高寒草甸、高寒草原和禾草草原,共占全省总产草量的 $9 5 . 5 8 \%$ 。从2015年到

表52015年及2016年各草地类型的最优估产模型  

<html><body><table><tr><td>年份</td><td>草地类型</td><td>植被指数</td><td>最优模型</td><td>模型表达式</td><td>R²</td><td>RMSE /kg·hm-2</td><td>模型精度 /1-REE,%</td></tr><tr><td>2015年</td><td>禾草草原</td><td>NDVImax</td><td>二次多项式</td><td>y =2 333.9-5 800.9x +10 332x²</td><td>0.81***</td><td>541.22</td><td>79.05</td></tr><tr><td></td><td>荒漠草原</td><td>NDVImax</td><td>幂函数模型</td><td>y = 3 261. 3x1.4281</td><td>0.95 ***</td><td>1</td><td>一</td></tr><tr><td></td><td>高寒草原</td><td>NDVImax</td><td>指数模型</td><td>y = 250.74e3.71x</td><td>0.83***</td><td>331.27</td><td>80.24</td></tr><tr><td></td><td>盐生草甸</td><td>NDVImax</td><td>指数模型</td><td>y = 449. 14e3.44x</td><td>0.95 ***</td><td>1</td><td>1</td></tr><tr><td></td><td>高寒草甸</td><td>NDVImax</td><td>指数模型</td><td>y = 391.34e2. 92x</td><td>0.74 ***</td><td>660.96</td><td>71.17</td></tr><tr><td>2016年</td><td>禾草草原</td><td>NDVImax</td><td>二次多项式</td><td>y =1 684.7 -4 841x +10 624x²</td><td>0.79 ***</td><td>639.61</td><td>76.42</td></tr><tr><td></td><td>荒漠草原</td><td>NDVImax</td><td>幂函数模型</td><td>y =4 570. 7x1. 56</td><td>0.81***</td><td>337.93</td><td>75.65</td></tr><tr><td></td><td>高寒草原</td><td>NDVImax</td><td>指数模型</td><td>y =184.09e4.18x</td><td>0.85 ***</td><td>678.43</td><td>74.72</td></tr><tr><td></td><td>盐生草甸</td><td>NDVImax</td><td>指数模型</td><td>y =594. 22e3.09x</td><td>0.81 ***</td><td></td><td>一</td></tr><tr><td></td><td>高寒草甸</td><td>NDVImax</td><td>指数模型</td><td>y = 191.78e3.88x</td><td>0.72 ***</td><td>658.08</td><td>78.00</td></tr></table></body></html>

注：y表示鲜草产量 $/ \mathrm { ~ k g ~ } \cdot \mathrm { h m } ^ { - 2 }$ $\mathbf { \Psi } _ { x }$ 表示 $N D W$ ，数值范围为 $- 1 . 0 \sim 1 . 0$ · $^ { * * }$ 表示通过0.001显著性检验( $P < 0 . 0 0 1$ )；-表示无数据

![](images/ba4e81debcdfa4b5445c4c27150483dfa8e3e745fb8c56d66cce30269df14329.jpg)  
图42015年及2016年青海省鲜草产量和干草产量的空间分布

Fig.4Spatial distribution of fresh grass yieldand the hayyield in2O15and 2O16in QinghaiProvince

表62015年及2016年青海省各州市产草量  
Tab.6Grass yield statistics at prefecture-level in Qinghai Province in 2015 and 2016   

<html><body><table><tr><td rowspan="2">地区</td><td rowspan="2">草地面积 /104 hm²</td><td colspan="2">鲜重／104t</td><td colspan="2">干重／104t</td><td colspan="2">平均干草单产／kg·hm -2</td><td rowspan="2">干重绝对变 化量／104t</td><td rowspan="2">变化幅度 /%</td></tr><tr><td>2015年</td><td>2016年</td><td>2015年</td><td>2016年</td><td>2015年</td><td>2016年</td></tr><tr><td>西宁市</td><td>44.15</td><td>148.59</td><td>152.92</td><td>47.94</td><td>49.34</td><td>1085.77</td><td>1 117.60</td><td>1.41</td><td>2.94</td></tr><tr><td>海东市</td><td>76.14</td><td>172. 16</td><td>192.75</td><td>56.64</td><td>63.47</td><td>744.34</td><td>833.99</td><td>6.82</td><td>12.04</td></tr><tr><td>海北州</td><td>253.34</td><td>714.07</td><td>724.37</td><td>225. 29</td><td>228.65</td><td>891.76</td><td>905.06</td><td>3.36</td><td>1.49</td></tr><tr><td>海西州</td><td>1 417.92</td><td>1 051.05</td><td>915.99</td><td>338.91</td><td>294.93</td><td>314.71</td><td>273.87</td><td>-43.98</td><td>-12.98</td></tr><tr><td>海南州</td><td>292.19</td><td>665. 62</td><td>678.06</td><td>214.47</td><td>218.83</td><td>734.10</td><td>749.02</td><td>4.36</td><td>2.03</td></tr><tr><td>玉树州</td><td>1 570. 60</td><td>2 440.43</td><td>2 425.91</td><td>768.83</td><td>763.69</td><td>490.41</td><td>487.13</td><td>-5.14</td><td>-0.67</td></tr><tr><td>果洛州</td><td>619.10</td><td>1 603.18</td><td>1 563.92</td><td>501.67</td><td>489.26</td><td>810.79</td><td>790.73</td><td>- 12.42</td><td>-2.47</td></tr><tr><td>黄南州</td><td>143.13</td><td>531.11</td><td>575. 67</td><td>166.63</td><td>180.62</td><td>1 164.17</td><td>1 261.90</td><td>13.99</td><td>8.39</td></tr><tr><td>青海省</td><td>4 416.58</td><td>7 326.22</td><td>7 229.60</td><td>2 320.38</td><td>2 288.78</td><td>569.90</td><td>562.14</td><td>-31.60</td><td>-1.36</td></tr></table></body></html>

![](images/48505baace88e352344116b9ca24359b7aec2114895ab0bb03e2870ca647ba08.jpg)  
Fig.5Hay yield changes at the prefecture-level in Qinghai Province from 2O15 to 2016

表72015年及2016年青海省各草地类型产草量  
Tab.7Grass yields of different grassland types in Qinghai Province in 2O15 and 2016   

<html><body><table><tr><td rowspan="2">草地类型</td><td rowspan="2">草地面积 /104 hm²</td><td colspan="2">鲜重／104t</td><td colspan="2">干重／104t</td><td colspan="2">平均干草单产</td><td colspan="2">草地类干重</td><td rowspan="2">干重绝对</td><td rowspan="2">变化 /%</td></tr><tr><td>2015年</td><td>2016年</td><td>2015年</td><td>2016年</td><td>2015年</td><td>2016年</td><td>2015年 2016年</td><td>/104t</td></tr><tr><td>高寒荒漠</td><td>53.69</td><td>30.36</td><td>26.15</td><td>12.14</td><td>10.46</td><td>226.88</td><td>195.39</td><td>0.50</td><td>0.44</td><td>-1.68</td><td>-13.84</td></tr><tr><td>禾草草原</td><td>219.13</td><td>485.55</td><td>465.79</td><td>161.85</td><td>155.26</td><td>739.38</td><td>709.28</td><td>6.71</td><td>6.56</td><td>-6.59</td><td>-4.07</td></tr><tr><td>荒漠草原</td><td>55.54</td><td>49.90</td><td>74.28</td><td>16.63</td><td>24.76</td><td>299.90</td><td>446.47</td><td>0.69</td><td>1.05</td><td>8.13</td><td>48.87</td></tr><tr><td>高寒草原</td><td>1135.15</td><td>958.51</td><td>892.56</td><td>319.50</td><td>297.52</td><td>282.24</td><td>262.82</td><td>13.25</td><td>12.57</td><td>- 21.98</td><td>-6.88</td></tr><tr><td>盐生草甸</td><td>204.11</td><td>177.81</td><td>222.19</td><td>55.57</td><td>69.43</td><td>278.31</td><td>347.76</td><td>2.30</td><td>2.93</td><td>13.87</td><td>24.96</td></tr><tr><td>高寒草甸</td><td>2 749.48</td><td>5 905.01</td><td>5 792.19</td><td>1 845.32</td><td>1810.06</td><td>671.72</td><td>658.89</td><td>76.54</td><td>76.45</td><td>-35.26</td><td>-1.91</td></tr><tr><td>总计</td><td>4 417.10</td><td>7 607.14</td><td>7 473.16</td><td>2 411.01</td><td>2 367.50</td><td>545.84</td><td>535.98</td><td>100.00</td><td>100.00</td><td>-43.51</td><td>-1.80</td></tr></table></body></html>

![](images/1f4ff385ddca011ca7d3ba9f9e7369ba99eb548e6cf27242d12b789de9c626db.jpg)  
图52015—2016年青海省各州市干草产量变化  
图62015—2016年青海省各草地类型干草产量变化Fig.6Hay yield changes of different grassland types in QinghaiProvince from 2015 to 2016

2016年，荒漠草原和盐生草甸的干草产量增加，但高寒荒漠、禾草草原、高寒草原和高寒草甸的干草产量减少。其中，荒漠草原的干草产量增幅最大，为$4 8 . 8 7 \%$ ,高寒荒漠的干草产量减幅最大，为 $1 3 . 8 4 \%$ 。

此外，如图6所示，低产草地类型（如荒漠草原和盐生草甸)的增产像元比例超过 $80 \%$ 。相比之下，禾草草原和高寒草甸等高产草地类型的产草量略微下降。其中，禾草草原干草产量下降超过150$\mathrm { k g } \cdot \mathrm { h m } ^ { - 2 }$ 的像元比例大于 $2 5 \%$ 。总体来看，青海省干草产量表现出略微的减产趋势，产量减少在 $0 \sim$ $8 0 \ \mathrm { k g } \cdot \mathrm { h m } ^ { - 2 }$ 的像元占大多数。

# 3结论与讨论

草地产草量变化分析是载畜能力评估和草地气候变化响应等研究中非常关键的一步。遥感产草量估算涉及到植被指数、统计模型、建模指标、草地类型以及不同的处理和建模方式等要素，这些要素对产草量估算结果存在一定的影响。为了提高产草量估算精度，本文基于地面实测数据和MODIS数据，选择了6种植被指数 $( N D V I , E V I , R V I , D V I , R D V I ,$ MSAVI）、5种常用的统计模型（线性模型、二次多项式模型、幂函数模型、指数函数模型、对数函数模型)和3种建模指标 $\left( \left. U _ { \mathrm { m a x } } \right. _ { \mathrm { \Theta } } V I _ { \mathrm { s e a s o n - c u m } } \right. _ { \mathrm { \Theta } } \left. V I _ { \mathrm { a n n u a l - c u m } } \right)$ 进行产草量估算精度比较,在此基础上选择最优产草量估算模型估算了2015 年和2016 年青海省草地的产草量,并对产草量的变化情况进行分析。通过比较发现,6种植被指数中，基于NDVI的产草量估算精度最高。这与前人在高寒草地进行研究所得的结论一致[12,17],与其他草地研究中得出的结论不一致[16,19],本文进一步证实了 NDVI确实是更加适合用来估算高寒草地的产草量的植被指数。而非线性模型的估算精度高于线性模型,尤其是指数模型，适用于大多数草地类型产草量的估算。这与前人在不同区域、不同草地类型进行研究所得的结论非常一致[4,1,16,22]。相比与 NDVI生长季累积值和年度累积值，NDVI年度最大值的估算模型对大多数草地类型都具有最高的决定系数 $( R ^ { 2 } )$ ,说明植被指数最大值对于指示草地产草量具有较好的作用，能够代表草地最大的生产力。

青海省草地产草量的空间分布格局主要与草地类型、海拔、地形等因素有关。干草产量较高的区域（204号 $( \mathbf { \nabla } > 1 \ 2 0 0 \ \mathrm { k g } \cdot \mathrm { h m } ^ { - 2 } ,$ )主要分布在东部高寒草原；中等产草量区 $\mathit { ' 6 0 0 - 1 ~ 2 0 0 ~ \mathrm { k g } ~ \cdot ~ \mathrm { h m } ^ { - 2 } }$ )分布在南部和东部的高寒草原和禾草草原；低产草量区（ $< 6 0 0$ $\mathbf { k g } \cdot \mathbf { h m } ^ { - 2 }$ )主要分布在西部和北部的高寒草甸、高寒草原、高寒荒漠和盐生草甸。与2015年相比,2016 年青海省干草产量略有下降,下降了 $3 1 . 6 \times$ $1 0 ^ { 4 } \mathrm { ~ t ~ }$ ,减幅为 $1 . 3 6 \%$ ,产量增加的草地类型主要为荒漠草原和盐生草甸，而产量减少的主要为禾草草原和高寒草甸。本研究不仅可为青海牧区生态保护以及可持续发展提供参考，同时也为产草量遥感估算研究提供了有益的补充。

# 参考文献(References)

[1]ALI I,CAWKWELL F,DWYER E,et al. Satelite remote sensingof grasslands：From observation to management［J].Journal ofPlant Ecology,2016,9(6) :649-671.  
[2] 韩其飞，陆研,李超凡.气候变化对中亚草地生态系统碳循环的影响研究［J].干旱区地理,2018,41（6)：1351－1357.［HAN Qifei,LU Yan,LI Chaofan.Impact of climate change on

grassland carbon cycling in Central Asia[J].Arid Land Geography,2018,41(6) :1351-1357.]

[3］王顺利,王荣新,敬文茂,等.祁连山干旱山地草地生物量对水 分条件的响应[J].干旱区地理，2017，40（4）：772－779. [WANG Shunli,WANG Rongxin,JING Wenmao,et al. Biomass of grassland and response to soil moisture on arid mountain land in the Qilian Mountains[J].Arid Land Geography,2017,40(4）:772 -779.]

[4]XU B,YANG X C,TAO W G,et al. MODIS-based remote sensing monitoring of grass production in China[J].International Journal of Remote Sensing,2008,29(17 -18）:5313-5327.   
[5］徐斌,杨秀春.东北草原区产草量和载畜平衡的遥感估算［J]. 地理研究,2009,28（2）:402-408.［XU Bin,YANG Xiuchun Calculation of grass production and balance of livestock carrying capacity in rangeland region of northeast China[J]. Geographical Research,2009,28（2）:402-408.]   
[6]徐剑波,宋立生,赵之重,等.近15a来黄河源地区玛多县草地 植被退化的遥感动态监测[J].干旱区地理,2012,35(4）：615 -622.[XU Jianbo,SONG Lisheng,ZHAO Zhizhong,et al. Monitoring grassland degradation dynamically at Maduo County in source region of Yellow River in past 15 years based on remote sensing[J].Arid Land Geography,2012,35(4）:615-622.1   
[7]LI X W,LI M D,DONG S K,et al. Temporal-spatial changes in ecosystem services and implications for the conservation of alpine rangelands on the Qinghai-Tibetan Plateau[J].Rangeland Journal,2015,37(SI) :31 -43.   
[8]MA W H,FANG JY,YANG Y H,et al. Biomass carbon stocks and their changes in northern China's grasslands during 1982 - 2006 [J].Science China-Life Sciences,2010,53(7）:841 -850.   
[9]PIAO S L,FANG JY,ZHOU L M,et al.Changes in biomass cal bon stocks in China's grasslands between 1982 and 1999[J]. Global Biogeochemical Cycles,2007,21（GB2002）:doi:10.1029/ 2005GB002634.   
[10]RUSCHG M,ZAPATA P C,CASANOVESF,et al. Determinants of grassland primary production in seasonally-dry silvopastoral systems in Central America[J].Agroforestry Systems,2014,88（3）: 517 -526.   
[11]WEHLAGE D C,GAMON JA,THAYER D,et al. Interannual variability in dry mixed-grass prairie yield;A comparison of MODIS, SPOT and field measurements[J]．Remote Sensing,2016,8 (87210） :doi:10.3390/rs8100872.   
[12]YU L,ZHOU L,LIU W,et al. Using remote sensing and GIS technologies to estimate grass yield and livestock carrying capacity of alpine grasslands in Golog Prefecture,China[J].Pedosphere, 2010,20(3):342 - 351.   
[13]MOHAMMAT A,WANG X H,XU X T,et al. Drought and spring cooling induced recent decrease in vegetation growth in Inner Asia [J].Agricultural and Forest Meteorology,2013,178-179:21- 30.   
[14]PIAO SL,MOHAMMAT A,FANGJY,et al. NDVI-based increase in growth of temperate grasslands and its responses to climate changes in China[J]. Global Environmental Change-human and Policy Dimensions,2006,16(4）:340 -348.   
[15]ZHOU L M,TUCKER C J,KAUFMANN R K,et al. Variations in northern vegetationactivityinferred fromsatellite dataof vegetation index during 1981 to1999[J]. Journal of Geophysical ResearchAtmospheres,2001,106（D17）:20069 - 20083.   
[16]LI JL,LIANG TG,CHEN Q G. Estimating grassland yields using remote sensing and GIS technologies in China[J]. New Zealand Journal of Agricultural Research,1998,41(1) :31-38.   
[17］傅新宇,唐川江,张新跃,等.四川草原 MODIS 数据的产草量 估算[J].地球信息科学学报,2013,15（4):611-617.［FU Xinyu,TANG Chuanjiang,ZHANG Xinyue,et al. Estimation of grass yield based on MODIS data in Sichuan Province,China[J]. Journal of Earth Information Science,2013,15(4）:611-617.]   
[18］杨淑霞,张文娟,冯琦胜,等.基于 MODIS 逐日地表反射率数 据的青南地区草地生长状况遥感监测研究［J].草业学报， 2016,25(8）:14-26.[YANG Shuxia,ZHANGWenjuan,FENG Qisheng,etal.Monitoring of grassand herbage accumulation byremote sensing using MODIS daily surface reflectance data in the Qingnan Region[J].Acta Prataculturae Sinica,2016,25(8）:14- 26.]   
[19］杨秀春,徐斌,朱晓华,等.北方农牧交错带草原产草量遥感监 测模型[J].地理研究,2007,(2）:213-221.[YANG Xiuchun, XU Bin,ZHU Xiaohua,et al. Models of grass production based on remote sensing monitoring in northern agro-grazing ecotone[J]. Geographical Research,2007,（2）:213-221.]   
[20]DI BELLA C,FAIVRE R,RUGET F,et al. Remote sensing capabilities to estimate pasture production in France[J]. International Journal of Remote Sensing,2004,25(23）:5359 -5372.   
[21］张扬建,范春捆,黄珂,等.遥感在生态系统生态学上应用的机 遇与挑战[J].生态学杂志,2017,36(3）:809-823.[ZHANG Yangjian,FAN Chunkun,HUANG Ke,et al. Opportunities and challenges in remote sensing applications to ecosystem ecology [J].Chinese Journal of Ecology,2017,36(3）:809 -823.]   
[22］罗玲,王宗明,任春颖,等.基于 MODIS 数据的松嫩草原产草 量遥感估算模型与空间反演[J].农业工程学报,2010,26（5）： 182 -187.[LUO Ling,WANG Zongming,REN Chunying,et al. Models for estimation of grassandproductionand spatial inversion based on MODIS data in Songnen Plain[J]. Journal of Agricultural Engineering,2010,26(5）:182-187.]   
[23］荀其蕾,董乙强,安沙舟,等.基于 MOD 09GA 数据的新疆草地 生长状况遥感监测研究[J].草业学报，2018，27（4）：10－26. [XUN Qilei,DONG Yiqiang,AN Shazhou,et al. Monitoring of grassland herbage accumulation byremote sensing using MOD 09GA data in Xinjiang[J].Acta Prataculturae Sinica,2018,27 (4) :10 -26.]   
[24］青海省草原总站.青海草地资源[M].西宁:青海人民出版社, 2012.[Qinghai General Station of Grassland. Qinghai grassand resources[M].Xining:Qinghai People's Publishing House,2012.]   
[25］金云翔,徐斌,杨秀春,等.内蒙古锡林郭勒盟草原产草量动态 遥感估算［J].中国科学:生命科学,2011,41（12）：1185- 1195.[JIN Yunxiang,XU Bin,YANG Xiuchun,et al.Remote sensing dynamic estimation of grass production in Xilinguole,Inner Mongolia[J]. Scientia Sinica（Vitae）,2011,41（12）：1185 1195.]   
[26]ROUSE JW.Monitoring the vernal advancement and retrogradation （greenwave efect）of natural vegetation[R]. NASA/GSFCT Type Report ,1974.   
[27]HUETE A,DIDAN K,MIURA T,et al. Overview of the radiometric and biophysical performance of the MODIS vegetation indices[J]. Remote Sensing of Environment,2002,83(1):195-213.   
[28] PEARSON R L,MILLER L D. Remote mapping of standing crop biomass for estimation of the productivity of the shortgrass prairie [C]//Proceedings of the English International Symposium on Remote Sensing of Environment,1972,2:1375-1381.   
[29]ROUJEAN JL,BREON F M. Estimating PAR absorbed by vegetation from bidirectional reflectance measurements[J]. Remote Sensing of Environment,1995,51(3):375-384.   
[30]QI J,CHEHBOUNI A,HUETE A R,et al.A modified soil adjusted vegetation index[J].Remote Sensing of Environment,1994,48 (2) :119 -126.   
[31］中华人民共和国农牧业畜牧兽医司,全国畜牧兽医总站.中国 草地资源[M].北京：中国科学技术出版社,1996.［Department of Agriculture,Animal Husbandry and Animal Husbandry and Veterinary of the People's Republic of China,General Animal Husbandry and Veterinary Station of China. China grassand resources[M].Beijing:China Science and Technology Press, 1996.]   
[32]MKHABELA M S,BULLOCK P,RAJ S,et al. Crop yield forecasting on the Canadian Prairies using MODIS NDVI data[J].Agricultural and Forest Meteorology,2011,151(3）:385-393.   
[33]SHRESTHA R,DIL,YU E G,et al. Regresson model to estimate flood impact on corn yield using MODIS NDVI and USDA cropland data layer[J]. Journal of Integrative Agriculture,2017,16(2）:98 -407.   
[34]LOBELL D B,ASNER G P.Cropland distributions from temporal unmixing of MODIS data[J].Remote Sensing of environment, 2004,93(3) :412 -422.   
[35]MAKELA H,PEKKARINEN A.Estimation of forest stand volumes byLandsat TM imagery and stand-level field-inventory data[J].   
Forest Ecology and Management,2004,196(2-3):245-255.

# Grassland yield change in Qinghai Province based on MODIS data

HUANG Xin’，LIU Jian-hong1,2，SHEN Ke-jian³4，LIU Yong-mei12，WANG Lei1.2 (1College of Urban and Environmental Science,Northwest University,Xi'an 71O127 ,Shaanxi,China;   
2 Shaanxi Key Laboratory of Earth Surface System and Environmental Carrying Capacity,Northwest University, Xi'an 710127,Shaanxi,China ;   
3Remote Sensing Center for Agriculture and Animal Husbandry of Qinghai,Xining 81007,Qinghai,China;   
4Chinese Academy of Agricultural Engineering,Beijing 100125,China）

Abstract：Qinghai Province isoneof the four major pastoral areas in China.It is of great significance to monitor thegrowth of grassand vegetation andaccurately estimate grass yields forthe sustainable developmentand ecological protection of the Qinghai pastoral area.Remote sensing estimation of grass yields is mainly basedon statistical relationshipbetween vegetation index and ground measured data.However,the selection of different vegetation indexes,various statistical models,and optional modeling metrics afect the accuracyof the estimationresults.Basedon the ground measured grass yield data of the Qinghai Province and the Moderate Resolution Imaging Spectroradiometer（MODIS）data,this paper selected six vegetation indexes,five statistical models,and three modeling metrics to testthe accuracyof different estimation models.The vegetation indexes included the Normalized Diference Vegetation Index（NDVI）,Enhanced Vegetation Index（EVI）,Ratio Vegetation Index（RVI）,Diference Vegetation Index (DVI）,Renormalized Diference Vegetation Index（RDVI）,and Modified Soil Adjusted Vegetation Index（MSAVI).The statistical modelsconsisted of a simple linear model,quadratic polynomial model,power function model, exponential function model,and logarithmic function model.The modeling metrics included the annual maximum value of vegetation index,cumulative value of vegetation index in growing season,and annual cumulative value of vegetation index.First,we explored which vegetation indexand estimation model were the most suitable for estimating the grass yields of diferent grassland types in the Qinghai Province.Then,we compared the accuracyof estimated grass yields from the three modeling metrics.Finally,we selected theoptimal grass yield estimation models to estimate grass yields of the Qinghai Province in 2O15and 2O16 and analyzed grass yield change during 2015- 2016.Theresults showed as follws:(1）among the six vegetation indexes,NDVI was the most suitable vegetation index to estimate grass yields in the Qinghai Province.The accuracy of nonlinear models was generally higher than that of linear models,especiallythe exponential models,whichare suitable forestimating grass yieldsof most grassland types.Theestimation models basedon the annual maximum of NDVIshowed the highest coefficientof determination $( R ^ { 2 } )$ for almost all grassand types.(2） from the perspective of hay yields,the high-yield area $\mathit { \Omega } > 1 \ 2 0 0 \ \mathrm { k g }$ （204号 （20 $\cdot \mathrm { h m } ^ { - 2 }$ ）was mainly located in the Alpine steppes in eastern Qinghai,and the middle-class area $\left( 6 0 0 - 1 ~ 2 0 0 ~ \mathrm { k g } ~ \cdot \right.$ （20 $\mathrm { h m } ^ { - 2 }$ ）was located in the grassteppes and the Alpine steppes in the north and east of Qinghai.Grasslands with low-yield （ $< 6 0 0 \ \mathrm { k g } \cdot \mathrm { h m } ^ { - 2 }$ ）were located in the Alpine meadows,Alpine steppes,Alpine deserts,and salt meadows in the western and northern part of Qinghai.（3）the total hay production in the Qinghai Province was $3 1 . 6 0 \ \times$ （20 （204号 ${ { 1 0 } ^ { 4 } }$ t in 2016,showing $1 . 3 6 ~ \%$ decrease compared to 2015.Among all,the grass steppes and Alpine meadows showed the highest yield loss,while in the desert steppes and salt meadows,the yield increased.This study not only provideda reference for ecological protection and sustainable development inthe pastoral area of Qinghai,but also provided research and practices for estimating grassland yield using remote sensing technology.

Key words:Qinghai Province；grass yield；remote sensing；MODIS；vegetation index