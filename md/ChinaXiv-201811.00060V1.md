# 2000一2015年中国荒漠化土地识别和监测

胡云锋1,²，张云芝1,²，韩月琪1,2（1中国科学院地理科学与资源研究所,资源与环境信息系统国家重点实验室,北京100101;2中国科学院大学，北京101408）

摘要：荒漠化是生态退化的极端表现形式，包括气候变异和人类活动在内的种种因素造成的干旱、半干旱和亚湿润干旱区的土地退化。快速和准确地识别中国荒漠化地区,是防范和治理荒漠化的关键。针对2000—2015年我国陆地生态系统NPP的变化趋势、稳定性和荒漠化敏感性进行了综合分析,构建了识别荒漠化土地的技术方法。结果表明：(1)近16a以来,我国内蒙古阴山以南、新疆天山以北、西藏阿里地区、长江以南大部地区，植被净初级生产力均出现了不同程度的下降趋势，且一半以上的区域处于植被生态系统不稳定状况;在全国 $5 6 . 2 \%$ 的国土属于荒漠化敏感区内，上述区域容易受气候、自然条件、人为干扰变等影响而发生荒漠化。（2)2000年以来，我国土地荒漠化退化区域面积约 $2 0 . 7 4 \times 1 0 ^ { 4 } \mathrm { k m } ^ { 2 }$ ，占国土总面积的 $2 . 1 6 \%$ 。主要为五大分布区域，即内蒙古高原中部的典型草原和荒漠化草原区、新疆天山—阿尔泰山山地草原区、新疆塔里木河下游的温带荒漠和绿洲区，青藏高原的阿里一昆仑山高寒荒漠区，青海省的青南山高寒草原区。(3)荒漠化进程伴随有生产力下降、植被盖度降低和地表温度不断攀升的地表关键参数演变特征，荒漠化的形成受气候影响显著，降雨的减少是造成土地荒漠化进程突出的主要因素;人类活动、不合理的种植业、畜牧业等在一定程度上对土地荒漠化起到推动作用。

# 关键词： $N P P$ ；荒漠化；空间分布；生态退化

中图分类号：TP79 文献标识码：A 文章编号

荒漠化是生态退化的极端表现形式，荒漠化包括沙漠化，是指在干旱、半干旱地区和一些半湿润地区，生态环境遭到破坏，造成土地生产力衰退或丧失而形成荒漠的过程[1-2] ○

荒漠化与荒漠是分属两个不同范畴的概念，荒漠化是一个动态过程，通常利用土地退化过程来表述荒漠化概念的定义[3]

目前，利用高分辨率时间遥感影像对荒漠化进行动态监测，成为区域尺度乃至全球尺度荒漠化的有效监测评价方式。在不同尺度上，许多学者构建了不同的荒漠化评价指标体系。HELLDEN[4]利用遥感的方法对苏丹荒漠化地区进行了干旱影响监测研究，证明了气候对荒漠化的重大影响。丁建丽等[5]利用NDVI对塔里木南缘绿洲荒漠化动态进行了研究;李宝林等[6利用NOAA/AVHRR数据在低密度植被区的MSAVI来提取荒漠化信息，对荒漠化的动态变化及驱动因子进行了分析。然而，作为土地退化的极端表现形式，土地退化过程在某种意义上表现为植被退化，植被的变化能够反映荒漠化发生、发展的过程[7]。NDVI、植被覆盖度等能在一定程度上反映区域的生态环境状况；植被净初级生产力（NPP)的变化对温度、降水等气候因素较为敏感，能够很好地表征全球气候变化，直观反映生态系统中地表植被在自然环境状况下的生产能力和生态质量状况,用来进行土地、生态退化监测[8-1]WEISS 等[12]基于归一化植被指数(NDVI)采用变异系数和线性回归分析法，对植被生物量与变化趋势进行了分析，并结合土地利用数据确定了区域荒漠化的发展态势。徐文科等[13]根据植被覆盖度和生物量信息，基于遥感信息与荒漠化程度的经验回归方程,判定了鄂尔多斯草地的荒漠化程度。荒漠化的发生与生态脆弱性紧密联系在一起，荒漠化脆弱敏感性越高的区域越容易发生荒漠化。刘军会等[14-15]针对土地沙化、土壤侵蚀、土壤盐渍化、石漠化等生态问题对全国以及内蒙区域生态环境敏感性进行了综合评价;张龙生等[16]采用表征生态脆弱性结果的土地退化指标，即土地沙漠化、土壤侵蚀（水蚀）、土壤盐渍化3项指标，进行了甘肃省生态脆弱性评价研究。

纵观已有研究发现，大多研究针对荒漠化的影响因素、荒漠化评价指标以及不同时期荒漠化程度监测对比，缺乏针对长时间序列下土地退化过程形成荒漠区域的快速定位、识别和空间分布的相关研究。荒漠化过程是一个在时间上连续发展、不断演变的土地退化现象，荒漠化过程不等同于荒漠状态，利用静态指标用于判断动态过程，单一参数、单一方法过于简单、武断。通过研究生态系统状况变化趋势，可以模拟产生退化的结果；利用脆弱性的理论，判断生态系统被干扰的程度，可以确定退化生态系统的类型[17],但简单地线性趋势,不足以说明复杂的、非线性变化的生态系统演变过程。针对上述研究不足，本文以长时序卫星遥感数据、气象站点监测数据、区域资源环境背景数据等为依托，构建了综合识别与监测荒漠化土地的技术方法，旨在快速、准确、定性地对荒漠化区域进行空间识别，以期为制定有效的荒漠化防治对策、确定区域荒漠化防治工程重点区域与合理布局提供科学决策参考。

# 1 数据与方法

# 1.1 数据及预处理

研究使用了基于遥感反演的长时序NPP、ND$W , L A I , L S T$ 产品，基于气象台站网络观测的长时序气象要素空间插值产品，以及包括土壤质地、DEM在内的基础地理空间背景等三类基础数据。其中：

2000—2015年 NPP、NDVI、LAI、LST 等产品来源于美国国家航空航天局（NASA）（https： $/ /$ lad-sweb.modaps.eosdis.nasa.gov/search/）。NDVI 是MODIS13A216d产品， $N P P$ 是MODIS17A3 年值产品，空间分辨率均为 $1 \ \mathrm { k m } \times 1 \ \mathrm { k m }$ ,对于NDVI产品需要进一步采用最大值合成法（MVC）得到逐年NDVI数据。叶面积指数（LAI）数据来自于MODISMCD15A3H产品，原始数据空间分辨率 $5 0 0 \mathrm { ~ m ~ }$ ，同样采用最大值合成法得到年值产品、并重采样至1000$\mathbf { m }$ 分辨率;地表温度(LST)数据来自于MODIS11A2产品，原始数据空间分辨率为 $1 \ 0 0 0 \ \mathrm { m }$ ，采用最大值合成法得到年值数据。

气象站点监测数据：从中国气象科学数据共享服务网下载中国地面气候资料数据集（http：//data.cma.cn/），获取全国2000—2015年742个气象站点降雨量、温度、风速每日4次的观测记录。在依次完成日、月、年统计基础上，基于ArcGIS平台应用Kriging方法开展空间插值，获取空间分辨率为 $1 ~ \mathrm { k m }$ $\times 1 ~ \mathrm { k m }$ 的气象栅格数据。

土壤质地数据：来源于中国科学院南京土壤研究所的1:100万土壤质地数据。土壤属性库包括土壤表层年里、粉砂、沙粒、有机质含量等字段。

# 1.2 模型方法

生态环境敏感性：是指生态系统对区域内自然和人类活动干扰的敏感程度，它反映区域生态系统在遇到干扰时，发生生态环境问题的难易程度和可能性的大小，并用来表征外界干扰可能造成的后果[18]。荒漠化主要与干旱联系在一起,通常被用于描述干旱、半干旱地区发生的土地退化过程。荒漠化发生的基本条件，一般强调为干旱区地表干燥、土壤浅薄、植被覆盖低、风力作用强等特征[19]。故选取干燥度指数 $\cdot { \geqslant } 6 \textnormal { m } \cdot \textnormal { s } ^ { - 1 }$ 起沙风天数、土壤质地、植被覆盖度作为荒漠化评价指标[20]

$$
D _ { i } { = } 4 { \sqrt { I _ { i } \times W _ { i } \times T _ { i } \times C _ { i } } }
$$

式中： $D _ { i }$ 为 $\mathbf { \chi } _ { i }$ 像元荒漠化敏感性指数; $I _ { i \setminus } W _ { i \setminus } T _ { i \setminus } C _ { i }$ 分别为 $i$ 评价单元的干燥度指数、起沙风天数、土壤质地和植被覆盖敏感性等级值（表1）。

干燥度指数采用修正的谢良尼诺夫公式[计算； ${ \geqslant } 6 \textnormal { m } \cdot \textnormal { s } ^ { - 1 }$ 起风沙天数选用冬春季节(12、1～5月份)大于 $6 \mathrm { ~ m ~ } \cdot \mathrm { ~ s ~ } ^ { - 1 }$ 起沙风天数;植被覆盖度由NDVI计算得到。

# 表1荒漠化敏感性评价指标及分级赋值标准

Tab.1 Indicators and classification criteria of desertification sensitivity   

<html><body><table><tr><td>类型</td><td>干燥度 指数</td><td>≥6m·s-1 起沙风天数</td><td>土壤 质地</td><td>植被覆盖 度/%</td><td>分级 赋值</td></tr><tr><td>不敏感</td><td>≤1.0</td><td>≤5</td><td>基岩</td><td>≥80</td><td>1</td></tr><tr><td>轻度敏感</td><td>1.0~1.5</td><td>5~10</td><td>粘质</td><td>60~80</td><td>3</td></tr><tr><td>中度敏感</td><td>1.5~4.0</td><td>10~20</td><td>砾质</td><td>40~60</td><td>5</td></tr><tr><td>高度敏感</td><td>4.0~16.0</td><td>20~30</td><td>壤质</td><td>20~40</td><td>7</td></tr><tr><td>极敏感</td><td>≥16.0</td><td>≥30</td><td>沙质</td><td>≤20</td><td>9</td></tr></table></body></html>

趋势分析：在栅格尺度上对全国2000—2015 年逐像元植被净初级生产力（NPP)的变化开展线性回归分析，得到过去 $1 6 \mathrm { ~ a ~ }$ 来NPP变化的斜率。与简单比较2个时间断面上 $N P P$ 差值的方法相比，长时序趋势分析方法可以消除特定年份的个例影响，客观反映长时序 NPP演化趋势[22-23]。公式如下：

$$
S l o p e = \frac { n \times \sum _ { i = 1 } ^ { n } ( i \times Y _ { i } ) \ - \ \sum _ { i = 1 } ^ { n } i \sum _ { i = 1 } ^ { n } Y _ { i } } { n \times \sum _ { i = 1 } ^ { n } i ^ { 2 } \ - ( \sum _ { i = 1 } ^ { n } i ) ^ { 2 } }
$$

式中：Slope为趋势线的斜率，即 $N P P$ 趋势; $Y _ { i }$ 表示第 $i$ 年的 $N P P$ 值； $n$ 为监测时段的年数( $n = 1 6$ 。为了检查回归模型的有效性，还必须进行显著性检验。

变异系数（CoefficientVariation, $\underbrace { C V } _ { \phantom { \left( C V \right) } }$ ：由于NPP的变化并非简单线性增加或者线性减少， $N P P$ 的变化可能有其他更加复杂的变化形态。为此，可以通过衡量NPP的变化幅度来评估生态系统的稳定性。变异系数即是反映观测值变异程度的一个统计量，它是标准差与平均值的比值[24-25]。 $C V$ 表示数据分布的离散程度， $C V$ 值越大，表示数据分布越离散，时间序列数据波动越大； $C V$ 值越小，表示数据分布较紧凑，时间序列数据较稳定。计算公式如下：

![](images/7c685c316bc89aaf673ee40a1b9cf9e0ef1b4c97068d496325f79583586378a4.jpg)  
图1荒漠化识别流程图  
Fig.1Process of desertification identification

$$
C V = \frac { S T D _ { _ { N P P } } } { M e a n _ { _ { N P P } } }
$$

式中： $S T D _ { \scriptscriptstyle { N P P } }$ 为 $N P P$ 逐年标准差; $M e a n _ { \scriptscriptstyle { N P P } }$ 为逐年NPP的平均值。为了能更加直观地揭示植被 $N P P$ 变化、评估生态系统随时间变化的稳定性，将 $C V$ 值分为4个级别：非常稳定( $C V { \leqslant } 0 . 0 5$ ）、稳定 $( 0 . 0 5 <$ $C V { \leqslant } 0 . 1$ ）、变异较小 $( 0 . \ 1 < C V \leqslant 0 . \ 1 5$ ）、变异剧烈0 $C V > 0 . 1 5 )$ 。

荒漠化识别流程：根据荒漠化敏感性指数模型，可以计算得到荒漠化极敏感区域、高度敏感区域和中度敏感区域;在上述区域内，如果发生 $N P P$ 显著下降过程，或者发生了NPP下降（但不显著）且NPP长时序变化波动较大过程,则将上述上述区域定义为发生荒漠化区域。具体流程如下：

根据上述模型和识别流程，可以清楚知道：荒漠化土地均发生在荒漠化敏感区；荒漠化进程可以用2种NPP变化模式指正，即：NPP显著下降以及NPP下降且NPP年际波动超出一定范围。

# 2 结果分析

# 2.1 荒漠化敏感区

综合长期气象观测数据、土壤质地、植被覆盖等数据，可以得到中国土地荒漠化敏感性指数图（图2）。统计表明：全国 $5 6 . 2 \%$ 的国土属于荒漠化敏感区(中度敏感、高度敏感、极敏感);其中， $1 6 . 8 \%$ 的国土(约 $1 5 9 . 2 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 } )$ 属于极敏感区域;另外$4 3 . 8 \%$ 的国土属于荒漠化不敏感或轻度敏感区。

从空间上看，我国东北平原部分、华北平原大部、内蒙古高原、黄土高原、青藏高原、新疆大部，均为荒漠化敏感区（中度以上）。其中，松辽平原、内蒙古高原、黄土高原,青藏高原中西部、塔里木盆地、准噶尔盆地等，属于荒漠化高度敏感、极敏感区；这些地区气候干燥，地表生态类型多为草地、稀疏林地和沙漠、荒漠，植被覆盖低，地表以沙性土壤为主，在气候变化和不合理的人类活动影响下，区域土地容易发生荒漠化。

需要强调指出的是：虽然有 $5 6 . 2 \%$ 的国土属于荒漠化敏感区，但是这些国土本身在现状自然属性上仍然属于耕地、草地和沙地、沙漠类型中的一种。只要没有不利的气候变化和不合理的人类干扰，上述敏感区并不会成为生态退化区，由耕地、草地向荒漠转变。

![](images/8785e4777abd4cd29f2cc3cfcd38f365ad89f06bf6e7c36d39e7c595273c2712.jpg)  
Fig.2Spatial distribution of desertification sensitivity in China

![](images/55c49475f84eef143659eac2cdc5478c0b9ef2620aa0bf3e56713e59e8aa854d.jpg)  
图2中国荒漠化敏感性空间分布  
图32000—2015年中国陆地生态系统净初级生产力(NPP)变化趋势  
Fig.3Trend of net primary productivity（NPP）of terrestrial ecosystem in China from 2OO0 to 201:

# 2.2NPP变化趋势

NPP指示了生态系统生产力水平，NPP下降意味着生态系统物质生产能力下降、生态系统服务功能处于退化过程。对2000—2015年NPP开展变化趋势及显著性分析，结果表明：2000年以来，全国$2 4 . 9 \%$ 的国土上 $N P P$ 呈现下降态势，其中显著下降的区域占全部国土面积的 $3 . 5 6 \%$ ;其它 $7 5 . 1 \%$ 的国土上NPP呈现增长趋势（图3）。

从空间上看，在内蒙古阴山地区、新疆天山一阿尔泰山地区、西藏羌塘高原、华南大部、华东长三角地区、华北太行山地区，2000—2015年期间NPP呈现下降态势（图3）。其中，新疆的天山一阿尔泰山的广大地区、云贵高原东部地区、长江三角洲等三个地区的NPP的线性下降趋势通过了显著性检验。在上述NPP显著下降区域,可以判断当地生态系统处于退化过程中；但是否属于荒漠化进程，还需要进一步结合其他证据判断。

# 2.3 NPP稳定性

在成熟的、稳定的生态系统中，其年际NPP一般保持平衡，不随时间发生大幅变化。生态系统发生较大变化时，年际 $N P P$ 随时间变化也会发生较大变异。对NPP变异系数进行计算，结果表明：2000—2015年期间，全国 $6 2 . 6 \%$ 的国土上NPP变化处于不稳定状态，其中有 $3 1 . 1 \%$ 的国土上 $N P P$ 变化属于剧烈状态；另有 $3 7 . 4 \%$ 的国土NPP变化较为稳定（图4）。

从空间上看，在中国华北大部、东北中西部地区、内蒙古高原中东部、黄土高原、青藏高原、新疆天山地区，这些地区NPP的变化较为强烈，其中，东北大小兴安岭地区、内蒙古呼伦贝尔、锡林郭勒、乌兰察布、鄂尔多斯、以及陕西、陕西、甘肃和宁夏的黄土高原地区、青海南部、青藏高原中部、东南部，新疆天山一阿尔泰山地区，NPP呈现为剧烈变化。

需要强调指出的是，长时段（2000—2015 年）NPP剧烈变化指示区域生态系统处于快速演替中，但上述演替进程可能是生态系统正向演替（如退耕还林还草），也可能是生态系统逆向演替（如森林砍伐、草地沙化、沼泽干涸等）。因此，在运用NPP剧烈变化指标确定生态退化区时，还需要进一步结合

NPP变化的方向来综合确定。即只有NPP变化剧烈、且NPP长期变化趋势为降低的区域,才是生态退化区域。

# 2.4荒漠化区域空间分布

综合应用前述荒漠化敏感性评价、NPP变化趋势分析、NPP稳定性分析等成果，在GIS叠加功能支持下，运用前述基于决策树的中国荒漠化土地识别流程进行综合，可以得到我国荒漠化土地空间分布图(图5）。

统计表明：2000—2015年期间，我国发生荒漠化的区域土地总面积约 $2 0 . 7 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,占国土总面积的 $2 . 1 6 \%$ 。从空间上看，荒漠化土地主要分布在5大区域,即：内蒙古高原中部的典型草原和荒漠化草原区、新疆天山一阿尔泰山山地草原区、新疆塔里木河下游的温带荒漠和绿洲区，青藏高原的阿里一昆仑山高寒荒漠区，青海省的青南山高寒草原区。

从省域尺度统计：2000—2015年，我国的土地荒漠化主要发生在西藏、新疆、内蒙古和青海三省（自治区），另外还有少量发生于甘肃、山东、河北、宁夏等省（自治区）（表2）。其中：西藏荒漠化面积最大,约为 $1 0 . 5 5 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,占全部土地荒漠化面积的 $5 0 . 8 5 \%$ ;新疆荒漠化面积次之，约 $4 . 1 5 \times 1 0 ^ { 4 }$ $ { \mathrm { k m } } ^ { 2 }$ ,占全部土地荒漠化面积的 $1 9 . 9 9 \%$ ;内蒙古荒漠化面积约 $4 . 1 3 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,占全部土地荒漠化面积的 $1 9 . 9 0 \%$ ；青海省荒漠化面积约 $1 . 0 4 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ，占全部土地荒漠化面积的 $5 . 0 2 \%$ ;其他各省的荒漠化土地面积相对较小,均不足 $0 . 5 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 号

表2中国主要省(自治区)荒漠化区域面积及占比统计表  
Tab.2Desertification area and proportion in China's   

<html><body><table><tr><td></td><td colspan="3">major provinces(autonomous regions )</td></tr><tr><td>省(区)</td><td>荒漠化区 域面积 /104km²</td><td>占本省(自治区） 国土面积比例 /%</td><td>占全国荒漠化 面积比例 /%</td></tr><tr><td>西藏</td><td>10.55</td><td>8.77</td><td>50.85</td></tr><tr><td>新疆</td><td>4.15</td><td>2.52</td><td>19.99</td></tr><tr><td>内蒙古</td><td>4.13</td><td>3.6</td><td>19.9</td></tr><tr><td>青海</td><td>1.04</td><td>1.45</td><td>5.02</td></tr><tr><td>山东</td><td>0.21</td><td>1.37</td><td>1.02</td></tr><tr><td>甘肃</td><td>0.18</td><td>0.46</td><td>0.87</td></tr><tr><td>河北</td><td>0.11</td><td>0.6</td><td>0.54</td></tr><tr><td>吉林</td><td>0.09</td><td>0.46</td><td>0.42</td></tr><tr><td>黑龙江</td><td>0.09</td><td>0.2</td><td>0.43</td></tr><tr><td>宁夏</td><td>0.08</td><td>1.63</td><td>0.41</td></tr><tr><td>山西</td><td>0.03</td><td>0.2</td><td>0.15</td></tr><tr><td>辽宁</td><td>0.02</td><td>0.14</td><td>0.1</td></tr><tr><td>河南</td><td>0.01</td><td>0.03</td><td>0.03</td></tr><tr><td>四川</td><td>0.001</td><td>0.003</td><td>0.01</td></tr></table></body></html>

![](images/8827b3fda2e9b90d26746f5f84f2b35e992432a7e08b9dccf3d16b6cf1f3371c.jpg)  
图42000—2015年中国陆地生态系统净初级生产力(NPP)时序稳定性

![](images/ef390576528c79cb5e59a19f2983a9165cef0028803a4b603d2026a55d5f8de7.jpg)  
ig.4Temporal stability of net primary productivity（NPP）of terrestrial ecosystem in China from 2000 to 201   
图52000—2015年中国荒漠化土地空间分布图  
Fig.5Spatial distribution of desertification lands in China from 2OOO to 2015

# 2.5 地表物理特征变化

对荒漠化土地关键地表物理特征参数的变化进行分析发现(图6），在上述5大区域、共计 $2 0 . 7 \times$

$1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 的荒漠化区域中,有 $6 1 . 8 \%$ 的土地( $\phantom { = } 1 2 . 8 \times$ $1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ )同时出现了 $L A I$ 下降趋势, $70 \%$ 的土地0 $1 4 . 5 \times 1 0 ^ { 4 } \ k m ^ { 2 } \ .$ )同时出现了 $L S T$ 上升趋势;另有$7 . 9 \times 1 0 ^ { 4 } \mathrm { k m } ^ { 2 }$ 土地的 $L A I$ 呈现上升趋势、 $6 . 2 \times$

![](images/03bbe0603583147c186fbe140ff20870fa3b7e06631379a55c0d07f778476818.jpg)  
Fig.6Trends of $L A I , L S T$ change from 2002 to 2005

$1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 的区域 $L S T$ 呈现下降趋势。

显然，在上述荒漠化土地中，出现了NPP下降、$L A I$ 下降 $, L S T$ 上升的整体变化趋势,3个指标在栅格尺度上出现了很高程度的变化协同。这一方面说明了荒漠化进程伴随有生产力下降、植被盖度降低和地表温度不断攀升的地表关键参数演变特征，另一方面也说明本研究综合采用荒漠化敏感性、NPP变化趋势和NPP年际波动程度三大指标识别荒漠化过程具有很高的可靠性，其结果具有很高的可信度。

# 3驱动因子分析

为了探究荒漠化区域形成驱动机制，对荒漠化分布范围较广且集中连片分布的5大区域开展重点分析。

# 3.1 气候变化

鉴于本研究所识别出的5大荒漠化区域均位于西部人口低密度区，人类干扰强度较低，气候变化是区域土地荒漠化的第一要素。研究表明：在本研究所指出的5个地区中，内蒙古高原中部典型草原和荒漠化草原区、青藏高原阿里一昆仑山高寒荒漠区这2个区域荒漠化格点出现了高于所在区域、省区水平的气候暖干化趋势。青海省的青南高寒草原区虽然降水量呈现增加趋势，但干燥度呈现明显的增加趋势。由此可见,过去16a来，气温普遍升高、大气降水明显减少，区域气候呈现暖干化态势，是上述地区出现荒漠化的重要驱动因素。

在新疆塔里木河下游温带荒漠和绿洲区，新疆天山一阿尔泰山山地草原区这2个地区，出现了区域气候整体呈现气温降低、降水减少的冷干化态势，荒漠化格点降水量变化趋势高于所在区域、省区水平，干燥程度也较高于所在区域、省区水平，故冷干化的区域气候变化也促进了这一地区荒漠化土地面积的增加。总体而言，降雨的减少，是造成上述地区荒漠化进程明显比周边地区明显的最主要因素，

# 3.2 土地活动

土地变化动态度反映了单位时间内区域土地利用/覆盖类型的变化的剧烈程度，是反映人类土地开发活动强度的直接指标[26]。计算表明：在本研究所指出的5个地区、20个旗县中（表4），其土地利用动态度大部分高于它们所在省区（内蒙古、新疆、西藏、青海)的土地利用动态度。这表明，人类直接的干扰活动，对于区域荒漠化是一个重要的驱动因素。

在本研究所指出的5个地区、20个旗县中，其土地利用动态度与它们所在省区（内蒙古、新疆、西藏、青海)的土地利用动态度相比，除了内蒙古达尔罕茂明安联合旗、四子王旗，西藏改则县，新疆博乐市、乌苏市以及新疆塔里木河下游温带荒漠和绿洲区的尉犁、和静、沙雅县之外，其它地区并没有表现出高动态的趋势；在青藏高原的阿里一昆仑山高寒荒漠区、新疆天山一阿尔泰山山地草原区的大部分地区，其土地利用动态度甚至低于所在省区土地变化动态度。这表明，在荒漠化地区，由人类直接作用引起的土地利用和土地覆被类型的变化并不是驱动土地荒漠化的基本因素，驱动土地荒漠化的另有其他因素。事实上，上述5个地区，除了内蒙古高原中部典型草原区，新疆博乐市、乌苏市及绿洲区之外，其它地区均为人口密度极小的少人区，甚至是无人区；人口稀少就决定了人类对于区域土地的干预程度不高，发生土地利用/土地覆被类型变化的可能性极小。

表3荒漠化地区气候变化统计表 Tab.3Statistics of climate change in desertification regions   

<html><body><table><tr><td rowspan="2">区域</td><td colspan="3">荒漠化格点气候变化</td><td colspan="3">荒漠化区域气候变化</td><td colspan="3">荒漠化省区气候变化</td></tr><tr><td>T（气温） 变化斜率</td><td>变化斜率</td><td>P(降水量）A(干燥度) 变化斜率</td><td>T(气温） 变化斜率</td><td>P(降水量）A(干燥度) 变化斜率</td><td>变化斜率</td><td>T(气温） 变化斜率</td><td>P(降水量）A(干燥度) 变化斜率</td><td>变化斜率</td></tr><tr><td>内蒙古高原中部典型草原 和荒漠化草原区</td><td>0.050</td><td>-1.415</td><td>-0.017</td><td>-0.071</td><td>-1.288</td><td>-0.035</td><td>-0.087</td><td>3.001</td><td>-0.061</td></tr><tr><td>青藏高原的阿里一昆仑山 高寒荒漠区</td><td>0.762</td><td>-8.816</td><td>-0.124</td><td>0.525</td><td>-6.469</td><td>-0.174</td><td>0.344</td><td>-8.156</td><td>-0.092</td></tr><tr><td>青海省的青南高寒草原区</td><td>0.699</td><td>0.493</td><td>0.133</td><td>0.610</td><td>-1.423</td><td>-0.132</td><td>0.328</td><td>0.354</td><td>-0.206</td></tr><tr><td>新疆塔里木河下游温带荒 漠和绿洲区</td><td>-0.951</td><td>-2.652</td><td>-0.107</td><td>-0.939</td><td>-2.983</td><td>-1.427</td><td>-0.556</td><td>-1.422</td><td>-0.702</td></tr><tr><td>新疆天山—阿尔泰山山地 草原区</td><td>-0.318</td><td>-3.005</td><td>0.030</td><td>-0.300</td><td>-3.499</td><td>0.018</td><td>-0.556</td><td>-1.422</td><td>-0.702</td></tr></table></body></html>

Tab.4Statistics of land use change in desertification regions   

<html><body><table><tr><td rowspan="2">区域</td><td rowspan="2">旗县</td><td>荒漠化旗县土地 利用动态度</td><td>荒漠化区域土地 利用动态度</td><td>荒漠化省区土地</td></tr><tr><td></td><td>55.17</td><td>利用动态度 45.67</td></tr><tr><td>内蒙古高原中部典型草原和荒漠化草原区</td><td>达尔罕茂明安联合旗 苏尼特右旗</td><td>58.58 43.57</td><td></td><td></td></tr><tr><td rowspan="6">青藏高原的阿里一昆仑山高寒荒漠区</td><td>四子王旗</td><td>58.42</td><td></td><td></td></tr><tr><td>仲巴县</td><td>27.21</td><td>30.40</td><td>44.01</td></tr><tr><td>申扎县</td><td>31.22</td><td></td><td></td></tr><tr><td>班戈县</td><td>30.49</td><td></td><td></td></tr><tr><td>尼玛县</td><td>36.01</td><td></td><td></td></tr><tr><td>改则县</td><td>64.38</td><td></td><td></td></tr><tr><td></td><td>措勤县</td><td>29.46</td><td></td><td></td></tr><tr><td rowspan="2">青海省的青南高寒草原区</td><td>治多县</td><td>77.54</td><td>73.97</td><td>78.35</td></tr><tr><td>曲麻莱县</td><td>65.25</td><td></td><td></td></tr><tr><td rowspan="2">新疆塔里木河下游温带荒漠和绿洲区</td><td>尉犁县</td><td>59.41</td><td>63.40</td><td>59.01</td></tr><tr><td>和静县</td><td>65.52</td><td></td><td></td></tr><tr><td rowspan="6">新疆天山一阿尔泰山山地草原区</td><td>沙雅县</td><td>70.35</td><td></td><td></td></tr><tr><td>博乐市</td><td>71.25</td><td>70.51</td><td>59.01</td></tr><tr><td>乌苏市</td><td>70.08</td><td></td><td></td></tr><tr><td>托里县</td><td>50.94</td><td></td><td></td></tr><tr><td>和布克赛尔蒙古自治县</td><td>40.11</td><td></td><td></td></tr><tr><td>富蕴县</td><td>37.07</td><td></td><td></td></tr><tr><td></td><td>福海县</td><td>52.00</td><td></td><td></td></tr></table></body></html>

表4荒漠化地区土地利用变化动态度统计表  
表5荒漠化地区社会发展要素变化统计表  
Tab.5Statistics of social development factors in desertification regions   

<html><body><table><tr><td rowspan="2">区域</td><td rowspan="2">旗县</td><td colspan="2">荒漠化地区社会发展</td><td colspan="2">省区社会发展</td></tr><tr><td>牲畜头只数 变化速率</td><td>第一产业 增加值增速</td><td>牲畜头只数 变化速率</td><td>第一产业 增加值增速</td></tr><tr><td>内蒙古高原中部典型草原和荒漠化草原区</td><td>达尔罕茂明安联合旗</td><td>-0.034</td><td>0.113</td><td>0.027</td><td>0.107</td></tr><tr><td rowspan="5">青藏高原的阿里一昆仑山高寒荒漠区</td><td>苏尼特右旗</td><td>-0.007</td><td>0.089</td><td>0.027</td><td>0.107</td></tr><tr><td>四子王旗</td><td>-0.013</td><td>0.090</td><td>0.027</td><td>0.107</td></tr><tr><td>仲巴县</td><td>-0.025</td><td>0.096</td><td>-0.014</td><td>0.067</td></tr><tr><td>申扎县</td><td>0.002</td><td>0.073</td><td>-0.014</td><td>0.067</td></tr><tr><td>班戈县</td><td>-0.017</td><td>0.085</td><td>-0.014</td><td>0.067</td></tr><tr><td></td><td>尼玛县</td><td>-0.009</td><td>0.026</td><td>-0.014</td><td>0.067</td></tr><tr><td rowspan="4">青海省的青南高寒草原区</td><td>改则县</td><td>-0.010</td><td>0.106</td><td>-0.014</td><td>0.067</td></tr><tr><td>措勤县</td><td>-0.022</td><td>0.094</td><td>-0.014</td><td>0.067</td></tr><tr><td>治多县</td><td>1</td><td>0.143</td><td>-0.005</td><td>0.116</td></tr><tr><td>曲麻莱县</td><td>1</td><td>0.134</td><td>-0.005</td><td>0.116</td></tr><tr><td>新疆塔里木河下游温带荒漠和绿洲区</td><td>尉犁县</td><td>0.038</td><td>0.152</td><td>0.052</td><td>0.119</td></tr><tr><td rowspan="5">新疆天山—阿尔泰山山地草原区</td><td>和静县</td><td>0.006</td><td>0.113</td><td>0.052</td><td>0.119</td></tr><tr><td>沙雅县</td><td>-0.005</td><td>0.084</td><td>0.052</td><td>0.119</td></tr><tr><td>博乐市</td><td>-0.004</td><td>0.130</td><td>0.052</td><td>0.119</td></tr><tr><td>乌苏市</td><td>0.005</td><td>0.088</td><td>0.052</td><td>0.119</td></tr><tr><td>托里县</td><td>0.011</td><td>0.143</td><td>0.052</td><td>0.119</td></tr><tr><td></td><td>和布克赛尔蒙古自治县</td><td>0.006</td><td>0.110</td><td>0.052</td><td>0.119</td></tr><tr><td></td><td>富蕴县</td><td>-0.004</td><td>0.075</td><td>0.052</td><td>0.119</td></tr><tr><td></td><td>福海县</td><td>0.002</td><td>0.100</td><td>0.052</td><td>0.119</td></tr></table></body></html>

# 3.3社会发展

除了气候变化、直接的土地利用和土地覆被类型变化驱动之外，不合理的种植业、畜牧业等也会对区域土地荒漠化带来推动作用。

研究表明：在本研究所指出的5个地区、20个旗县中，青海省青南高寒草原区治多县、曲麻莱县，新疆尉犁县、博乐市、托里县，以及青藏高原的阿里一昆仑山高寒荒漠区内除尼玛县外第一产业增速明显高于本省区水平，农、林、牧、渔业和采集业在某种程度上给区域土地荒漠化带来一定的推动作用。另外,内蒙古高原中部典型草原和荒漠化草原区牲畜头数呈现降低趋势，而本省区牲畜头数呈现增加趋势，说明可能是除畜牧业之外的不合理的种植业等导致的土地荒漠化。

# 4结论

本文利用2000—2015年共16a的MODISNPP数据，估算了中国的生态退化状况，针对典型生态退化的极端表现形式一荒漠化生态环境问题，构建了快速、综合识别典型荒漠化退化区域的技术方法，揭示了我国荒漠化退化区域的空间分布；并对退化区域的叶面积指数和地表温度进行相应的时序变化趋势分析，进一步论证了结果的可靠性。主要结论如下：

（1）2000年以来，我国荒漠化土地区域面积约$2 0 . 7 4 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ，占国土总面积的 $2 . 1 6 \%$ 。主要分布在内蒙古高原中部的典型草原和荒漠化草原区、新疆天山一阿尔泰山山地草原区、新疆塔里木河下游的温带荒漠和绿洲区，青藏高原的阿里一昆仑山高寒荒漠区，青海省的青南山高寒草原区这五大区域。荒漠化分布范围较广的省、自治区依次为：西藏、新疆、内蒙古和青海，其他区域荒漠化区域面积相对较小,均不足 $0 . 5 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ 。

(2）荒漠化进程伴随有生产力下降、植被盖度降低和地表温度不断攀升的地表关键参数演变特征。荒漠化土地有 $6 1 . 8 \%$ 的区域叶面积指数呈现逐渐下降趋势， $70 \%$ 区域地表温度呈现逐渐上升。荒漠化的形成受气候影响显著，降水的减少是荒漠化进程突出的主要因素。

(3）人类活动对于区域荒漠化有一定的驱动作用，但在青藏高原的阿里一昆仑山高寒荒漠区、新疆天山一阿尔泰山山地草原区等大部分人口稀少地区人类活动并不是驱动土地荒漠化的基本因素。不合理的种植业、畜牧业等对区域土地荒漠化也带来一定的推动作用，而荒漠化进程受气候、人类活动、社会发展等多种因素都有一定的影响作用。

# 参考文献(References）

[1］章家恩,徐琪.生态退化研究的基本内容与框架[J].水土保持 通报,1997,（6）:46-53.[ZHANG Jiaen,XU Qi.Basic content and structure of ecological degradation[J].Bulletin of Soil & Water Conservation,1997,(6）:46-53.]   
[2]刘国华,傅伯杰,陈利顶,等.中国生态退化的主要类型、特征 及分布［J].生态学报,2000,（1）：14-20.［LIUGuohua,FU Bojie,CHEN Liding,et al.Characteristicsand distributions of degraded ecological types in China[J].Acta Ecologica Sinica,2000, (1) :14 -20.]   
[3]董玉祥.“荒漠化”与"沙漠化"[J].科技术语研究,2000,（4）： 18-21.［DONG Yuxiang.“Desertification”and“desertification” [J].Chinese Science and Technology Terms Journal,2OoO,（4）： 18-21]   
[4]VER N S R,PARUELO JM,OESTERHELD M. Assessing desertification[J]. Journal of Arid Environments,2006,66（4）:751- 763.   
[5］丁建丽,塔西甫拉提·特依拜,熊黑钢,等.塔里木盆地南缘绿 洲荒漠化动态变化遥感研究——以策勒县为例[J].遥感学 报， $2 0 0 2 , 6 \left( 1 \right) : 5 6 - 6 2 + 8 2$ ，[DING Jili,TIYIP Tashpolat, XIONG Heigang，et al.Study of oasis desertification dynamic change in the south of Tarim Basin[J]. Journal of Remote Sens（204 $\mathrm { i n g } , 2 0 0 2 , 6 ( 1 ) : 5 6 - 6 2 + 8 2 . \mathit { \Omega } ]$   
[6］李宝林,周成虎.东北平原西部沙地沙质荒漠化的遥感监测研 究[J].遥感学报, $2 0 0 2 , 6 \left( 2 \right) : 1 1 7 \mathrm { ~ - ~ } 1 2 2 \mathrm { ~ + ~ } 1 6 3$ [LI Baolin, ZHOU Chenghu.A study on monitoring sandy desertification in sandy land of west Northeast China Plain[J].Journal of Remote Sensing,2002,6(2): $1 1 7 - 1 2 2 + 1 6 3 .$ ]   
[7］殷贺,李正国,王仰麟.荒漠化评价研究进展[J].植物生态学 报,2011,35(3）:345-352.[YIN He,LI Zhengguo,WANG Yanglin.A review on the research progress of desertification assessment [J].Chinese Journal of Plant Ecology,2011,35(3）:345-352.]   
[8］奚砚涛,徐勇,刘欣婷.2000-2013 年江苏省不同植被类型 NDVI时空变化特征[J].水土保持研究,2016,（1)： $8 6 - 9 1 +$ （204号 82.[ XI Jiantao,XU Yong,LIU Xinting. Spatiotemporal changes of diffrent vegetation coverage in Jiangsu Province in the period from 2000 to 2013[J].Research of Soil and Water Conservation.2016, (1) $: 8 6 - 9 1 + 8 2$ ］   
[9]SEAN T M. Convergence of terrestrial plant production across global climate gradients[J]. Nature,2014,7512(512）.   
[10]PONCE CAMPOS G E,MORAN M S,HUETE A,et al. Ecosystem

resilience despite large-scale altered hydroclimatic conditions[J].

Nature,2013,494(7437) :349-352.   
[11］苑全治,吴绍洪,戴尔阜,等.过去50 年气候变化下中国潜在 植被NPP的脆弱性评价[J].地理学报,2016，（5）：797－806. [YUAN Quanzhi,WU Shaohong,DAI Erfu,et al.NPP vulnerability of China's potential vegetation to climate change in the past 50 years[J].Acta Geographica Sinica,2016,（5） :797 -806.]   
[12]WEISS E,MARSH S E,PFIRMAN E S.Application of NOAAAVHRR NDVI time-series data to assess changes in Saudi Arabia' s rangelands[J]. International Journal of Remote Sensing,2001,22 (6):1005 -1027.   
[13］徐文科,蔡体久，琚存勇.基于RS和GIS 的毛乌素沙地荒漠化 程度定量估测[J].林业科学,2007,43（5）：48-53.[XUWenke,CAI Tijiu,JU Cunyong. Quantitative estimation of desertification degree based on RS and GIS in Mu Us Sandland,Inner Mongolia[J].Scientia Silvae Sinicae,2007,43(5）:48-53.]   
[14］刘军会,高吉喜,马苏,等.内蒙古生态环境敏感性综合评价 [J].中国环境科学,2015,（2）:591-598.[LIU Junhui,GAO Jixi,MA Su,et al.Comprehensive evaluation of eco-environmental sensitivity in Inner Mongolia,China[J].China Environmental Science,2015,（2） :591-598.]   
[15］刘军会,高吉喜,马苏,等.中国生态环境敏感区评价[J].自然 资源学报,2015,（10）:1607-1616.［LIU Junhui,GAO Jixi,MA Su,et al.Evaluation of ecological sensitivity in China[J].Journal of Natural Resources,2015,（10）:1607 -1616.]   
[16］张龙生,王建宏,尚立照.基于土地退化的甘肃省生态脆弱性 评价研究［J].中国沙漠,2010,30（4）：783－787.［ZHANG Longsheng,WANG Jianhong,SHANG Lizhao.Ecological vulnerability assessment based on land degradation data in Gansu Province [J].Journal of Desert Research,2010,30(4）:783 -787.]   
[17］赵平,彭少麟，张经炜.生态系统的脆弱性与退化生态系统 [J].热带亚热带植物学报,1998,（3）：179－186.[ZHAO Ping,PENG Shaolin,ZHANG Jingwei. The fragility of ecosystem and the restoration of degraded ecosystem[J].Journal of Tropical & Subtropical Botany,1998,（3）:179 -186.]   
[18］欧阳志云,王效科,苗鸿.中国生态环境敏感性及其区域差异 规律研究［J].生态学报,2000，（1）：10－13.［OUYANG Zhiyun,WANG Xiaoke,MIAO Hong. China's eco-environmental sensitivity and its spatial heterogeneity[J].Acta Ecologica Sinica, 2000,(1):10 -13.]   
[19］金远亮,彭华,闫罗彬,等.中国南方湿润区"荒漠化"问题讨论 [J].地理科学进展,2015,34（6）:772-780.[JIN Yuanliang， PENG Hua,YAN Luobin,et al. Discussion on desertification of humid region in southern China[J].Progress in Geography,2015,34 (6):772-780.]   
[20］生态功能区划暂行规程［EB/OL].http://www.zhb.gov.cn/. [Temporary regulation of ecological function zoning[EB/OL]. http://www.zhb.gov.cn/.]   
[21］中国科学院自然区划工作委员会.中国气候区划(初稿)[M]. 北京：科学出版社,1956.［Natural Zoning Work Committee Chinese Academy of Sciences.China’s climate zoning（first draft） [M]. Beijing: Science Press,1956.]   
[22] STOW D,DAESCHNER S,HOPE A,et al.Variability of the seasonally integrated normalized diference vegetation index across the north slope of Alaska in the 199Os[J].International Journal of Remote Sensing,2003,24(5）:1111 -1117.   
[23］潘竟虎，黄克军，李真.2001—2010 年疏勒河流域植被净初级 生产力时空变化及其与气候因子的关系［J].生态学报,2017： 1888-1899.[PAN Jinghu,HUANG Kejun,LI Zhen. Spatio-temporal variation in vegetation net primary productivity and its relationship with climatic factors in the Shule River Basin from 2001 to 2010[J]. Acta Ecologica Sinica,2017:1888 -1899.]   
[24］叶辉,王军邦,黄玫,等.青藏高原植被降水利用效率的空间格 局及其对降水和气温的响应[J].植物生态学报.2012,36 (12）:1237-1247.[YE Hui,WANG Junbang,HUANG Mei,et al. Spatial pattern of vegetation precipitation use efficiency and its response to precipitation and temperature on the Qinghai-Xizang Plateau of China[J].Chinese Journal of Plant Ecology,2012,36 (12):1237 -1247.]   
[25］张仁平,冯琦胜,郭靖,等.2000—2012年中国北方草地 NDVI 和气候因子时空变化[J].中国沙漠.2015,35（5）：1403- 1412.[ ZHANG Renping,FENG Qisheng,GUO Jing,et al. Spatiotemporal changes of NDVI and climatic factors of grassand in northern China from 2000 to 2012[J].Journal of Desert Research, 2015,35(5) :1403 -1412.]   
[26］刘纪远,布和敖斯尔.中国土地利用变化现代过程时空特征的 研究—一基于卫星遥感数据［J].第四纪研究,2000,20（3）： 229 -239.[LIU Jiyuan,AOSER B. Study on spatial-temporal feature of modern land use change in China: Using remote sensing techniques[J]. Quaternary Sciences,2000,20(3）:229 -239.]

# Identification and monitoring of desertification lands in China from 2000 to 2015

HUYun-feng1,2，ZHANGYun-zhi1,2，HAN Yue-qi12 (1State KeyLaboratoryofResources andEnvironmental Information System，InstituteofGeographic SciencesandNatural Resources Research,Chinese Academy of Sciences,Beijing 100lo1,China；2University of Chinese Academy of Sciences,Beijing 101408,China）

Abstract：Desertification isan extreme manifestationof ecological degradation which refers to land degradation in arid,semi-aridand drysub-humid arid regions caused byvarious factors including climate variabilityand human activities.Howto identifythedesertification landsquicklyandaccuratelyisthe keypoint topreventand control desertsanddesertification.This paper analyzesthechanging trend,stabilityanddesertificationsensitivityof terrestrial ecosystem NPPin China from 2OOO to 2015,andconstructsatechnical method to identify desertification lands.The main conclusions are as follows:（1）over the past 16 years,there have been different declining levels of net primary productivity in the southof Yin Mountain in Iner Mongolia,northof Tianshan Mountains in Xinjiang,andmost regionsinthe south of Yangtze River,and vegetation ecosystem is in instability state in more than halfof the regions; $56 . 2 \%$ of the country's land belongs to the desertification sensitive area,and the above area is susceptible to desertification due toclimate,naturalconditions and human disturbance.（2）Since 2O,theareaof desertification lands in China is about 2O7 4OO square kilometers,accounting for $2 . 1 6 \%$ of the total land area. The area can be divided into five regions,namelythe typical graslandand desertification steppe inthecentral Inner MongoliaPlateau,the Tianshan-Altay Mountain steppe area in Xinjiang,the temperate desert and oasis area in the lowerreaches of the Tarim Riverin Xinjiang,thealpine-desertareaoftheAli-Kunlun Mountains in the Qinghai-Tibet Plateauand south Qinghai alpine grasland area.（3）Thedesertification processis accompanied by the evolution of key parameters such as the decrease of productivity,the decrease of vegetation cover and the rising surface temperature.The formationofdesertificationisaffctedbyclimate,and thedecreaseofrainfall isthemain factorthatcauses the process of desertification.Inaddition,humanactivitiesand unreasonable farmingand animal husbandry also formed the desertification in some extended.

Key words:NPP；desertification；spatial distribution；ecological degeneration