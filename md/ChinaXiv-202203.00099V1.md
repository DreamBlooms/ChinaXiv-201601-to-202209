# TIGGE降水预报在中国干旱半干旱地区的适用性评估

可超禄¹²，吕海深1²，朱永华¹²，李文韬¹²，谢冰绮³，徐凯莉¹²，刘名文12（1.河海大学水文水资源与水利工程科学国家重点实验室,江苏 南京210098；2.河海大学水文水资源学院，江苏 南京210098；3.珠江水利委员会珠江水利科学研究院,广东 广州510630)

摘要：TIGGE降水产品作为目前中短期集合预报最权威的数据集合的重要组成部分,其在中国干旱半干旱地区的适用性如何，还需要进一步探讨。基于中国干旱半干旱地区2015—2017年实测降水数据,采用平均绝对偏差、均方根误差、TS评分等指标，从降水量预报、降水分级预报、降水探测能力和空间预报精度等多角度出发,综合评估了TIGGE数据中心的ECMWF、JMA、KMA和UKMO4种模式在研究区的预报效果。结果表明：（1）4种模式对小雨的预报效果均较好,在进行不同降水量级预报时,JMA对于小雨的降水预报效果最佳,而对于其他降水量级的降水预报,4种模式无明显差别；（2）针对日降水量预报,KMA效果最差,而ECMWF最精确；(3）在不同降水阈值下对降水的探测能力评估结果显示，ECMWF更具优势，尤其在以 $2 5 \mathrm { m m \cdot d ^ { - 1 } }$ 为阈值时优势明显;(4)空间预报精度检验结果显示，各模式在 $8 0 ^ { \circ } { \sim } 1 0 0 ^ { \circ } \mathrm { E } , 3 5 ^ { \circ } { \sim } 4 5 ^ { \circ } \mathrm { N }$ 范围表现最佳，主要是新疆中部以及新疆、甘肃和青海三省交界处，对比各模式之间，ECMWF表现更稳定，KMA则表现较差。

关键词：TIGGE；降水预报；降水量级；空间预报精度；干旱半干旱地区；中国

降水作为洪水预报的输入条件，对洪水预报精度影响较大。随着数值天气预报技术的不断进步，相关数值模式产品迅速兴起。数值模式预报产品特指气象部门计算并输出的数值天气预报格点数据产品，也是目前气象部门输出的唯一一类预测未来天气状况的数值产品。目前，预报员可以参考的数值模式产品较多，主要包括：欧洲模式、中国T639模式、美国模式、日本模式、德国模式以及省气象台或各区域中心引进开发的中尺度模式[1-7]。目前短期降水预报已经较为成熟，尤其是预见期1\~7d的预报精度较高，因此将降水预报数据作为水文模型驱动数据，进行水文预报，从而延长预见期、提高洪水预报精度提供了可能[8-9]。国内外许多学者已经将气象预报数据与洪水预报模型耦合进行水文预报[10-11]。大多研究表明,气象水文耦合的洪水预报具有一定的预报精度且能有效延长洪水预报预见期[12-14]

全球交互式大集合（THORPEXInteractive Gar-nd GlobalEnsemble）,简称TIGGE,THORPEX是一个世界天气研究计划，旨在加速提高1天至2周高影响天气预报的准确性，造福人类。作为THOR-PEX项目的关键组成部分，TIGGE能评价并代表各成员国的集合预报系统针对较高影响天气要素的预报水平，从而实现共享全球集合数值预报产品，促进全球天气预报业务以及数值预报技术的进步。其权威性及可公开获取性已为天气预报业务相关学科的科研机构提供了大量的研究数据，产生了丰硕的科研成果，已初步展现集合预报在高影响天气预报中的优良应用前景[1-6]。不同模式产生的预报产品都有着模式误差限制，随之产生的问题就是如何通过充分利用各模式的预报产品，从而提升预报准确率。已有研究表明，多模式集合技术表现出更高的预报技巧[15-16],在实际生产中,对每个预报模式赋予合理的权重系数是提高多模式集合技术精度的关键[7]。在此之前,评估各模式在研究区的预报能力，筛选出预报能力适用性更佳的单个预报模式是有必要的。

目前，针对TIGGE预报结果的评估和应用已取得一定进展[17],对单一模式在具体流域的评估总能找到该模式的优点，但随着预报产品的日趋丰富和综合集成预报服务需要的增强，作为集成模式基础的模式预报性能的评估也成为研究热点。而TIG-GE对中国干旱半干旱地区(以下称"研究区")的预报效用鲜见报道，研究区大部分属于温带大陆性气候,降水量稀少且集中于夏秋季,生态环境脆弱[18-19],如何利用好预报信息，评估多模式的预报效果，分析结果差异的原因，进而进行下一步的多模式集成提供研究基础，对改进研究区的中期预报有着重要意义。本文拟对TIGGE资料中心的ECMWF、JMA、KMA和UKMO4种模式在研究区的预报效果进行评价，从降水量预报、降水分级预报、降水探测能力和空间预报精度等多角度出发，综合分析了多类预报产品在研究区的适用性。

# 中商 研究区和数据介绍

# 1.1研究区域

根据中国年降水量分布图，将年降水量小于$4 0 0 \mathrm { m m }$ 的地区划分为中国干旱半干旱地区，即降水量小于蒸发量的地区。研究区位于 $2 7 . 2 7 ^ { \circ } { \sim } 4 9 . 8 5 ^ { \circ } \mathrm { N }$ $7 3 . 4 3 ^ { \circ } \sim 1 2 1 . 9 1 ^ { \circ } \mathrm { E }$ ，总面积约 $4 . 5 6 \times 1 0 ^ { 6 } ~ \mathrm { k m } ^ { 2 }$ （图1）。区内大部分地区属于温带大陆性气候，降水量稀少，植被覆盖低,沙漠、裸地、盐碱地等广布[18.20]。本文中研究区边界范围划定依据中国科学院资源环境与数据中心的中国生态地理分区数据(https://www.resdc.cn/data.aspx?DATAID $_ { 1 = 1 2 5 }$ ）。

# 1.2数据及处理

1.2.1预报数据本文应用的TIGGE数据来自于ECMWF（欧洲中心)的ECMWF（欧洲）、JMA（日本）、KMA（韩国）、UKMO(英国)4种模式的控制预报产品。由于各个机构发布的降水预报时空分辨率不完全统一，因此统一选取世界时(UniversalTime Co-ordinated，UTC)00:00作为预报起点，对应北京时间$0 8 \colon 0 0 \mathrm { \left( U T C + 8 \colon 0 0 \right) }$ ),预报时长统一为 $1 6 8 \mathrm { ~ h ~ }$ （未来 $1 \sim$ 7d),空间分辨率为 $0 . 5 ^ { \circ } \times 0 . 5 ^ { \circ }$ 。再考虑到预报数据的缺失情况，时间序列选择了预报数据完整性较好的2015—2017年。选取的模式基本信息见表1，预报数据可从https://apps.ecmwf.int/datasets/data/tigge/levtype%3Dsfc/type%3Dcf/免费获取。默认数据格式为GRIB2类型，可用Python中xarray $^ +$ cfgrib库进行

![](images/9efd52c00e168172ba5bfa77663f7d7812a15a40a2213b208c38285e40bd5ce6.jpg)  
图1研究区域示意图  
Fig.1Schematic diagram of the study area

# 表1参与评价的预测和实测资料基本信息

<html><body><table><tr><td colspan="2">数据类型 ECMWF JMA KMA</td><td>UKMO 实测</td></tr><tr><td>国家 欧洲</td><td>日本 韩国 英国</td><td>中国</td></tr><tr><td>预见期</td><td>168 h</td><td>24 h</td></tr><tr><td>起报时间</td><td>0:00(UTC)</td><td>8:00(北京时间)</td></tr><tr><td>预报步长</td><td>6h</td><td>24 h</td></tr><tr><td>空间分辨率</td><td colspan="2">0.5°x0.5°</td></tr><tr><td>区域范围</td><td>27°~50°N，73°~122E</td><td></td></tr><tr><td>资料长度</td><td>2015年1月1日至2017年12月31日</td><td></td></tr></table></body></html>

查看和处理。

1.2.2实测数据实测资料来自国家气象科学数据中心气象资料室建立的中国地面降水日值 $0 . 5 ^ { \circ } \times$ $0 . 5 ^ { \circ }$ 格点数据集(V2.0)[21]。该数据集主要基于气象资料室存档的全国2474个国家级台站近50a逐月、逐日降水量资料和利用GTOP030数据（分辨率为$3 0 ~ \mathrm { m } { \times } 3 0 ~ \mathrm { m }$ )重采样生成的中国范围 $0 . 5 ^ { \circ } \times 0 . 5 ^ { \circ }$ 数字高程模型数据DEM，使用局部薄盘光滑样条(Par-tialthinplatesmoothing splines)法进行空间插值而生成。质量评估结果显示，中国东南地区的插值绝对误差普遍高于其他地区，夏季误差明显大于其他季节，当出现大雨和中雨日时，弱化了降水强度，而出现小雨日时，更接近实测降水，资料对青藏高原、天山山脉和塔里木盆地等大地形附近的降水空间特征描述较准确[22-23]。因此,该数据集可以用于代表我国干旱半干旱地区实测降水数据，本文使用到的实测数据基本信息见表1。

1.2.3数据处理对比预报数据和实测数据，二者数据时空尺度不同，须将其统一，及对其进行预处理。具体处理方法为：(1)统一空间尺度，将原本网格中心相差 $0 . 2 5 ^ { \circ }$ 的预报数据和实测数据进行双线性插值处理，再通过掩膜提取得到研究区范围数据；(2）统一时间尺度，预报数据为预报步长为 $6 \mathrm { { h } }$ 的累计降水量，而实测数据为逐日降水量，且预报数据存在数据缺失的情况，因此先提取出预报数据的预报步长为 $2 4 \mathrm { h }$ 的逐日降水数据，再根据每种模式数据缺失情况做空对应实测数据的天数，使得二者时间尺度统一。

# 2 研究方法

在洪水预报中引入定量预报降水是延长洪水预见期的重要手段与方法[24]。且降水1\~7d的日降水预报还可延长水库实时调度以及径流预报的预见期,提高预报要素的可利用性[17]。通过分析不同预报模式在预见期1\~7d的降水量预报、降水分级预报、降水探测能力和空间预报精度4个方面的结果差异，以获得在研究区具体雨量级、具体位置的模式适用情况，为后期的降水订正与集成，提升洪水预报精度和预见期提供一定的参考。

参照气象部门划分降水等级标准，将日降水划分为6个等级(表2)。但由于研究流域大暴雨发生次数较少，所以将大暴雨其归于暴雨等级内，且本文仅仅研究有水的情况，所以无雨不在考虑范围内。对于降水量预报,首先使用网格平均法[15]提前将降水数据处理为研究区的面平均降水，从而检验所选TIGGE模式在研究区的日降水预报的总体效果[15]；然后根据实测降水数据，将其按照降水等级标准分成4类，得到数据位置索引，并以此索引提取预测数据，得到不同降水等级的预报数据，以此检验降水量分级预报能力；最后计算研究区的预报误差来揭示各预报模式的地域性差异。对于降水探测能力，根据列联表选取阈值分别为 $0 . 1 \ \mathrm { m m } \setminus 1 0 . 0$ $\mathrm { m m } , 2 5 . 0 \ \mathrm { m m } , 5 0 . 0 \ \mathrm { m m }$ 的降水数据数量来计算统计指标，以揭示不同模式不同预见期的降水探测能力差异。

Tab.1 Basic information of prediction and measured datainvolvedinevaluation   
表2降雨等级划分标准  
Tab.2 Grade of precipitation /(mm· d1)   

<html><body><table><tr><td>无雨</td><td>小雨</td><td>中雨</td><td>大雨</td><td>暴雨</td><td>大暴雨</td></tr><tr><td><0.1</td><td>(0.1,10]</td><td>(10,25]</td><td>(25,50]</td><td>(50,100]</td><td>(100,200]</td></tr></table></body></html>

# 2.1 统计指标

本文采用检验降水量预报常用指标来评估降水量预报效果["o]：平均绝对偏差(Bias）、均方根误差（RMSE）、预报偏小率 $( S _ { l } )$ 、预报偏小误差 $( X _ { l } )$ 、预报偏大率 $( S _ { g } )$ 及预报偏大误差 $( X _ { g } )$ 。其中，Bias描述预报模式的偏离方向与程度；RMSE则反映预报序列与实测序列之间的偏差，且不考虑偏差的方向，对较大误差更为敏感； $S _ { l }$ 与 $X _ { l \setminus S _ { g } }$ 与 $X _ { g }$ 分别反映预报数据相对实测数据的平均偏小和偏大程度[15]

$$
\mathrm { B i a s } = \frac { \displaystyle \sum _ { t = 1 } ^ { N } ( F _ { t } - O _ { t } ) } { N } , \mathrm { R M S E } = \Biggl [ \frac { 1 } { N _ { t } } \sum _ { t } ^ { N } \bigl ( F _ { t } - O _ { t } \bigr ) ^ { 2 } \Biggr ] ^ { \frac { 1 } { 2 } }
$$

$$
S _ { g } = N _ { g } / N , X _ { g } = \sum _ { t } ^ { N _ { g } } X _ { g t } / N _ { g } , S _ { l } = N _ { l } / N , X _ { l } = \sum _ { t } ^ { N _ { l } } X _ { l t } / N _ { l }
$$

式中： $F _ { t }$ 和 $O _ { t }$ 分别为第 $\mathbf { \Phi } _ { t }$ 天的预报降水和实测降水；$N$ 为预报天数； $X _ { g t }$ 为第 $\mathbf { \Phi } _ { t }$ 天降水偏大的误差； $X _ { l t }$ 为第 $\mathbf { \Phi } _ { t }$ 天降水偏小的误差。若 $F _ { t } { > } O _ { t }$ 则预报偏大， $X _ { g t } { = } F _ { t } { - }$ $O _ { t } , N _ { g }$ 为 $N$ 天降水预报中偏大的总天数；反之若 $F _ { t } { < } O _ { t }$ 则预报偏小， $X _ { l t } = F _ { t } – O _ { t } , N _ { l }$ 为 $N$ 天降水预报中偏小的总天数[17]。以上各指标均越接近0表示预测值与实测值一致性越好，对应的预报模式效用越好。

# 2.2分类指标

在利用连续性指标对降水量及分级预报进行定量评价之余，还需注意到预报模式对降水事件的探测能力的评估也很有必要。本文使用Wilks[5]提出的分类指标方法，通过计算预报数据与实测数据的分类指标，分析4种预报模式对实际降水事件的探测能力，使用了TS评分（临界成功指数）POD(命中率) $, F A R$ (误报率)3个指标。其中TS评分综合考虑成功探测和误报降水事件，能反映预报降水实际探测降水能力[26]； $P O D$ 表示在所有实际降水事件中，对应预报降水能探测到的降水事件所占比例；FAR表示在所有预报降水事件中，实际没有降水的比例。 $T S , P O D$ 以及 $F A R$ 的取值范围均为0\~1,其中，TS和 $P O D$ 的数值越大、 $, F A R$ 的数值越小则表明预报效果越好。对降水事件的探测可以分为4种情况(表3)，3种指标计算公式如下：

$$
T S = \frac { H } { H + M + F } , P O D = \frac { H } { H + M } , F A R = \frac { F } { H + F }
$$

式中： $H$ 为实测数据与预报数据均探测到的降水事件数量； $F$ 为实测降水数据没有探测到而预报数据

# 表3预报降水数据与实际降水数据列联表

Tab.3 Contingency table of forecast and actual precipitation data   

<html><body><table><tr><td rowspan="3">降水事件</td><td colspan="2">实际降水数据</td></tr><tr><td>有降水</td><td>无降水</td></tr><tr><td>有降水 预报降水数据</td><td>Hit(H)</td><td>False(F)</td></tr><tr><td>无降水</td><td>Miss(M)</td><td>二</td></tr></table></body></html>

探测到的降水事件数量； $M$ 为实测降水数据探测到而预报降水数据没有探测到的降水事件数量。计算不同降水阈值下的分类指标，综合评估不同降水强度下各TIGGE模式对降水事件的探测能力。

# 3结果与分析

# 3.1日降水量预报能力评价

为了对4种TIGGE模式在整个研究区的适用情况进行整体把握，使用网格平均法[15提前将多模式降水和实测降水处理成研究区平均降水,采用Bias、RMSE $\mathrm { , } S _ { l } \mathrm { , } X _ { l } , S _ { g }$ 及 $X _ { \mathrm { g } }$ 6个评估指标，结果如图2所示。

由图2中Bias随预见期的变化可知，Bias均呈负偏差，说明各模式对降水量的预报普遍偏小，再结合 $S _ { l }$ 和 $S _ { g }$ 随预见期的变化可知， $S _ { l }$ 的变化范围为0.65\~0.85， $S _ { g }$ 的变化范围为 $0 . 1 5 { \sim } 0 . 3 5 , S _ { l }$ 明显大于$S _ { g }$ ，尽管 $S _ { l }$ 随预见期延长呈下降趋势，而 $S _ { g }$ 呈上升趋势，说明降水量预报同时存在偏大和偏小现象，但预报值较实测值一致性偏小是引起降水量预报偏差的主要原因。

![](images/a2df51e4c65462ad21168a1d26a6ae47336a104393ad60f4e12b388d7aab6bd6.jpg)  
图21\~7d预见期日值降水预报检验结果  
Fig.2The verification results of the 1-7 day lead time precipitation forecasts

由各指标随预见期变化趋势可知，各模式的预报误差主要在前3d中增加，之后预报误差趋于稳定，无显著变化。且第1d的预测效果最佳，其中UKMO的Bias接近0。1\~3d预见期内Bias、RMSE、$X _ { l \setminus } X _ { g }$ 的变化范围分别为 $- 0 . 4 \mathrm { { \sim } - 0 . 1 5 ~ \mathrm { { m m } } }$ ， $0 . 4 { \sim } 0 . 9$ $\mathrm { m m }$ $, - 0 . 7 { \sim } - 0 . 3 ~ \mathrm { m m } , 0 . 2 { \sim } 0 . 6 ~ \mathrm { m m }$ ，表示TIGGE数据对于日降水量的预报效果较好，且精度存在3d的衰减期后趋于稳定。

将模式之间进行对比，预见期1d时，UKMO有略微优势，其后是ECMWF和KMA，JMA最次；预见期2d时，ECMWF领先;预见期3d以后，ECMWF有着明显优势，UKMO次之，KMA最差，总而言之，虽然不同指标在前3d预见期的对比略有变化，但无论是误差判断指标还是精度指标的判定而言，考虑整个研究区面平均雨量时，ECMWF和UKMO在预报日降水量时效果均要更好一些。

# 3.2降水分级预报能力评价

对于降水量预报，除了需要整体把握研究区的适用情况外，将预报数据进行降水分级评估也很有必要。以实测降水数据按照表2分级，再索引对应(同日期、经纬度)网格位置的预报数据生成数据系列，采用平均绝对偏差(Bias）、均方根误差(RMSE）、预报偏小率 $( S _ { l } )$ 、预报偏小误差 $( X _ { l } )$ 、预报偏大率$( S _ { g } )$ 及预报偏大误差 $( X _ { g } )$ 06个评估指标，分别计算不同降水强度下预见期1\~7d的精度指标，结果如图3所示。从指标Bias和RMSE随1\~7d预见期及降水量级的变化可知，小雨的Bias的变化范围在 $0 \mathrm { \sim } - 0 . 7$ $\mathbf { m } \mathbf { m }$ 之间，小雨的RMSE的变化范围在 $3 . 3 { \sim } 4 . 3 ~ \mathrm { m m }$ 之间，说明各预报模式对小雨的预报能力较高，但随着降水量级的增加，预报能力逐渐下降，暴雨的RMSE变化范围增加到了 $4 4 { \sim } 6 0 ~ \mathrm { m m }$ ，例如发生于2016年6月8日，位于研究区东部 $\mathrm { ' } 1 0 9 ^ { \circ } { \sim } 1 1 1 ^ { \circ } \mathrm { E } , 3 8 ^ { \circ } { \sim } 3 9 . 5 ^ { \circ } \mathrm { N } \mathrm { \rangle }$ 的这场暴雨，当日实测单格网最大日降水量100.65$\mathbf { m } \mathbf { m }$ ,对应的4种TIGGE模式只有ECMWF的预见期1\~3d探测到此次暴雨，其他3种TIGGE模式均未探测到此次暴雨，且ECMWF模式出现明显的高估；同一降水量级下，随预见期增长，前2d是各模式误差的主要增长期，后5d预报误差趋于稳定，第1d预报效果最好，且前2d误差衰减明显。说明在分级预报能力上，TIGGE对预见期1d，中小雨预报效果最佳，且存在2d的误差衰减。

![](images/66fa4cc7593e14e13b683b14b285463d497834892b3bcdb300a48b06c152bdb9.jpg)  
图31\~7d预见期降水分级预报评价结果  
Fig.3The verification results of the 1-7day lead time forecasts of different precipitation levels

从预报偏小率 $( S _ { l } )$ 、预报偏小误差 $( X _ { l } )$ 、预报偏大率 $( S _ { g } )$ 及预报偏大误差 $( X _ { g } )$ 随1\~7d预见期及降水量级的变化可知，4种模式偏大率均高于偏小率，而偏大误差除小雨略小于偏小误差外，其他均大于偏小误差，这也反映在小雨的偏差都表现为轻微的负偏，其他降水等级都表现为较大的正偏。说明4种模式预报时偏大现象更多，除小雨外更严重。

对比模式之间，可发现只有在小雨时差异性较显著，各模式的Bias变化范围在 $- 0 . 7 { \sim } 0 \ \mathrm { m m }$ 之间，相差很小，而RMSE显示JMA模式的预报效果最好，且随预见期增加，JMA的预报效果在第2d增加后，后3\~7d呈现回落趋势，其他3种模式则遵守2d衰减期的总体规律。在中、大、暴雨的表现中，4种模式表现非常接近，由此可得出，4种模式在分级降水预报的表现由好到次为：JMA、ECMWF、UKMO、KMA。

# 3.3降水探测能力评价

分类指标可以基于实测格点数据分析预报数据在降水事件上的捕捉能力，本文主要使用了TS评分（临界成功指数） $\ 、 P O D$ （命中率） $. F A R$ （误报率）3个指标，针对1\~7d预见期，计算了4种TIGGE模式在研究区2015—2017年的日累积降水量，阈值分别为 $0 . 1 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ （小雨） $1 0 \ \mathrm { m m \cdot d }$ （中雨） $. 2 5 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ （大雨） $. 5 0 \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ (暴雨)下的分类指标，计算结果如图4所示。

![](images/13992a6118a9ab228870a562d8245a559381b71204ca963292d0081fe3f20b33.jpg)  
图41\~7d预见期降水探测能力评价计算结果  
Fig.4 The scores of the 1-7 day lead time forecasts of precipitation detection capability

由图4可知，阈值为 $0 . 1 \ \mathrm { m m ^ { \bullet } d ^ { - 1 } }$ 的TS评分范围为 $0 . 3 2 { \sim } 0 . 4 8 , P O D$ 的范围为 $0 . 5 { \sim } 0 . 8 , F A R$ 的范围为$0 . 3 5 \mathrm { \sim } 0 . 5 5$ ，说明各预报模式对小雨的探测能力较高，但随阈值的增加，3个指标计算结果逐渐恶化，POD的减少总是伴随FAR的增加，表明各TIGGE模式的探测能力显著降低，如阈值为 $5 0 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 时TS评分多在0.00\~0.06之间，显示几乎没有技巧；随预见期的延长，各模式对不同阈值降水量的探测能力也逐渐降低，且衰减期以前3d为主，第1d探测能力最强，前2d衰减最显著。

将各模式之间进行对比，各模式在大雨时差异性较大，中雨时差异性较小，在暴雨时探测能力太差，不具有比较意义。对于阈值为 $0 . 1 \ \mathrm { m m ^ { \bullet } d ^ { - 1 } }$ 时，虽然KMA的POD占优势，但同时其 $F A R$ 也是最大的，已有研究表明,TIGGE倾向于多预报小雨[15],会造成命中事件碰巧很多，这也是 $F A R$ 一开始就很高的原因，无法得出KMA有更佳的探测能力的结论；对于阈值为 $2 5 \mathrm { m m \cdot d ^ { - 1 } }$ 时，3项指标统一显示，ECMWF明显优于另外3种模式。整体而言，以不同阈值计算的3个分类指标中，ECMWF发挥更稳健，尤其在以 $2 5 \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 为阈值时优势明显。

![](images/727e42ff99b68a8850eb812252261dc2e8c3b0dab99de8f2e229e3ac81822fca.jpg)  
图51\~3d预见期RMSE( $\operatorname { m m } \cdot \mathrm { d } ^ { - 1 }$ 0空间分布  
Fig.5The spatial distribution of the 1-3 day lead time forecasts of RMSE $\mathrm { ( m m \cdot d ^ { \cdot 1 } }$ ）

# 3.4空间预报精度评价

根据上文检验结果，4种TIGGE模式均存在 $2 \sim$ 3d的预报能力衰减，在后几日预见期内预报能力趋于稳定。所以以RMSE为精度指标，选择前3d预见期的TIGGE模式降水数据，与对应格网位置上的实测降水数据进行计算，为便于分析，将格网计算结果进行等值线插值，并统一分辨率层次为 $1 \mathrm { m m ^ { \cdot } d ^ { - 1 } }$ 且将结果大于 $6 \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 的区域统一颜色，以颜色深浅及所占据面积和位置可分析在空间上的预报精度，再以研究区内的省级行政地图为底图，得到空间分布图(图5)。同时针对实测降水数据按照时间维求均值，绘制2015—2017年实测降水均值空间分布图(图6)。

![](images/e33b185a8d1e07ee5b98d4184433251c6359568c77a604ab14333026560cb502.jpg)  
图62015—2017年实测降水均值空间分布 $( \mathrm { m m } \cdot \mathrm { d } ^ { \cdot } )$ Fig.6 The spatial distribution of the 2015-2017 observedprecipitation $( \mathrm { m m \cdot d ^ { - 1 } }$ ）

由图5可知，绝大部分区域的RMSE结果小于6$\mathbf { m } \mathbf { m } \cdot \mathbf { d } ^ { - 1 }$ ,且小于 $3 \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 的区域占比达一半甚至更多，说明各模式在研究区的预报精度均较好；整体看来，RMSE呈现明显的空间规律，由西向东先增后减，在 $8 0 ^ { \circ } { \sim } 1 0 0 ^ { \circ } \mathrm { E } , 3 5 ^ { \circ } { \sim } 4 5 ^ { \circ } \mathrm { N }$ 范围表现最佳，在 $1 0 0 ^ { \circ } \sim$ $1 2 0 ^ { \circ } \mathrm { E } , 3 5 ^ { \circ } { \sim } 4 0 ^ { \circ } \mathrm { N }$ 范围则表现较差，说明各模式在研究区表现最好和最差的区域呈现出一定的一致性，结合图5、图6可看出，RMSE高值区域位于新疆伊犁河谷以及研究区东部，同时这2个地区的实测降水量也较高，二者呈现相似的空间分布特征，分析可能原因是丰富的降水量使得预报精度下降，也就是说，降水越频繁的地区，预报精度越低;1d预见期表现最好，第2d、3d则逐渐下降，说明各模式仍显示出随预见期的增加，预报精度减弱的现象，且前2d是主要衰减期。

对比各模式之间，预见期为1d时，ECMWF有着明显的优势，其精度指标在 $1 \ \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 和 $2 \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 以下均占比最多，其后为UKMO，相比起JMA，UK-MO主要优势在于其 $2 \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 以下面积占比更大，最后是KMA;2d和3d预见期时，ECMWF仍表现出稳定的优势，除KMA较差，另外2种模式差异不明显，但就表现较差的面积占比来说，UKMO更多。整体而言，4种模式中ECMWF表现更稳健，KMA则表现较差，在不同预见期上，JMA和UKMO差异不大，不过具体应用时，还是要考虑具体研究区，将经纬度分辨率增加，再作进一步评估。

# 4结论

以中国干旱半干旱地区为研究对象，对TIGGE数据中心的ECMWF、JMA、KMA和UKMO模式2015一2017年日降水数据进行了精度检验，采用多种指标分别从降水量预报、降水分级预报、降水探测能力和空间预报精度4个方面综合分析了各式预报产品在研究区的适用性。得出如下结论：

（1）对于1\~7d预见期内平均日降水量和不同降水量级日降水量，TIGGE4个模式均有较强的预报能力，且有较好的预报时效性。对于日降水量级预报，4种模式对小雨预报能力较好，其RMSE均小于 $4 . 3 0 ~ \mathrm { m m }$ ，而对暴雨及以上量级降水预报效果较差，其最佳的预见期1d的RMSE也达到了 $4 4 . 0 0 \mathrm { m m }$ 以上；4种模式在小雨时表现为轻微的预报偏小，在其他降水量级误差来源主要是预报偏大；对比各个模式对降水量的预报效果，进行 $1 0 ~ \mathrm { m m }$ 以下的降水预报时，JMA最优，而对于 $1 0 ~ \mathrm { m m }$ 以上的降水预报，四者无明显差别。对于日降水量预报，KMA模式对日降水量的预报效果最差，而ECMWF模式则最精确，整体而言，这4种模式预报时偏小现象更多，但偏大和偏小程度则差不多。

（2）在不同降水阈值下，各模式均表现出一定的降水捕捉能力，整体而言，ECMWF更具优势，尤其在以 $2 5 \mathrm { m m } \cdot \mathrm { d } ^ { - 1 }$ 为阈值时优势明显。空间预报精度检验结果显示，各模式在 $8 0 ^ { \circ } { \sim } 1 0 0 ^ { \circ } \mathrm { E } , 3 5 ^ { \circ } { \sim } 4 5 ^ { \circ } \mathrm { N }$ 范围表现最佳，主要是新疆中部以及新疆、甘肃和青海三省交界处，在 $1 0 0 ^ { \circ } { \sim } 1 2 0 ^ { \circ } \mathrm { E } , 3 5 ^ { \circ } { \sim } 4 0 ^ { \circ } \mathrm { N }$ 范围则表现较差;对比各模式之间，ECMWF仍表现更稳健，KMA则表现较差。

（3）4种TIGGE模式也表现出一些统一的特点：随预见期的延长，在降水量预报、降水量分级预报、降水探测能力以及空间预报精度4个方面都有着2\~3d的衰减期，第1\~2d的衰减幅度最大;随降水量级的增加，精度指标和分级指标也表现出衰减现象。

（4）本文对TIGGE降水预报的检验是在中国干旱半干旱地区的首次适用,此次检验有助于进一步改进研究区中期降水预报结果。针对以上误差分析对TIGGE降水资料进行订正以及集成，可提高各预报要素的可利用性。针对小雨降水量级预报偏小,其他降水量级偏大，而日降水量偏小，可以选取1个阈值，阈值以下预报值适当增大，阈值以上预报值适当减小来同时改善降水量及和降水量的预报结果;前3d衰减期内的预报结果相差较大，要分别考虑修正系数，3d后可以用第3d的修正系数进行数据修正；对于预报结果较好的ECMWF、JMA等模式可以在后期分配较高权重进行多模式数据集成；空间预报精度则可以作为研究区选择预报模式的基础，在此基础进行评价、订正与集成；另外，夏季降水占据了研究区全年降水的主要成分，本文的评价结果更适用于夏季，如果对另外的季节有应用需求，可选择对应季节数据参照本文评价模式进行评价，获取更有针对性的评价结果。

# 参考文献(References)：

[1]智协飞,黄闻.基于卡尔曼滤波的中国区域气温和降水的多模 式集成预报[J].大气科学学报,2019,42(2):197-206.[Zhi Xie fei,HuangWen.Multimodel ensemble forecasts of surface air temperature and precipitation over China by using Kalman filter[J]. Transactions of Atmospheric Sciences,2019,42(2): 197-206.]   
[2]王建群,段蓉,蔡晨凯.TIGGE模式在淮河水系史河流域的应用 [J].河海大学学报(自然科学版),2020,48(1):14-21.[Wang Jianqun,Duan Rong,Cai Chenkai.Application of TIGGE precipitation forecast in Shihe catchment of Huaihe River Basin[J]. Journal ofHohai University(Natural Sciences Edition), 2020, 48(1): 14-21.]   
[3]王海霞,智协飞.基于TIGGE多模式降水量预报的统计降尺度 研究[J].气象科学,2015,35(4): 430-437.[Wang Haixia,Zhi Xiefei.Statistical downscaling research of precipitation forecast based on TIGGE multimodel ensemble[J]. Journal of the Meteorological Sciences,2015,35(4): 430-437.]   
[4]杜开连,葛忆,张佳丽,等.赤山湖流域TIGGE降水预报精度评 价研究[J].江苏水利,2020(7):48-51.[Du Kailian,GeYi, Zhang Jiali,et al. Study on the evaluation of TIGGE precipitation forecast precision in Chishan Lake Catchment[J]. Jiangsu Water Resources, 2020(7): 48-51.]   
[5]Amit B, Vinay K,Anjali S,et al.Application of multimodel superensemble technique on the TIGGE suite of operational models[J]. Geomatics,2021,1(1): 81-91.   
[6]Amini S,Azizian A,Arasteh P D.How reliable are TIGGE daily deterministic precipitation forecasts over diferent climate and topographicconditionsof Iran?[J].Meteorological Applications, 2021,28(4): e2013,doi: 10.1002/met.2013.   
[7]张成军,纪晓玲,马金仁,等.多种数值预报及其释用产品在宁 夏天气预报业务中的检验评估[J].干旱气象,2017,35(1):148- 156.[Zhang Chengjun,Ji Xiaoling, Ma Jingren, et al.Verification of numerical forecast and its application products in weather forecast in Ningxia[J]. Journal of Arid Meteorology,2017,35(1): 148-156.]   
[8]金君良,舒章康,陈敏,等.基于数值天气预报产品的气象水文 耦合径流预报[J].水科学进展,2019,30(3):316-325.[Jin Junliang,Shu Zhangkang, Chen Min, et al. Meteo-hydrological coupled runoff forecasting based on numerical weather prediction products [J]. Advances in Water Science,2019,30(3): 316-325.]   
[9]包红军,王莉莉,沈学顺,等.气象水文耦合的洪水预报研究进 展[J].气象,2016,42(9):1045-1057.[Bao Hongjun,Wang Lili, Shen Xueshun, et al.A review: Advances of flood forecasting of hydro-meteorological forecast technology [J]. Meteorological Monthly,2016, 42(9): 1045-1057.]   
[10] 雍燕兰,杨云川,赵铜铁钢.水文集合预报检验指标调研及其在 西江流域季节降水预报中的应用[J].水文,2020,40(6):31-39. [Yong Yanlan, Yang Yunchuan, Zhao Tongtiegang,et al. Verification metrics of hydrological ensemble forecasts and their applications to seasonal precipitation forecasts of the Xijiang River Basin [J]. Journal of China Hydrology,2020,40(6): 31-39.]   
[11]Patrice D, Jean-Luc M,Richard A. Hydrological ensemble forecasting using a multi-model framework[J]. Journal of Hydrology, 2021,600:126537,doi.org/10.1016/j.jhdrol.2021.157.   
[12] 殷志远,王志斌,李俊,等.WRF模式与Topmodel模型在洪水预 报中的耦合预报试验研究[J].气象学报,2017,75(4):672-684. [Yin Zhiyuan,Wang Zhibin, Li Jun,et al. An experimental study on the prediction of flood using coupled WRF- Topmodel model [J].Acta Meteorologica Sinica,2017,75(4): 672-684.]   
[13] 刘章君,郭生练,许新发,等.贝叶斯概率水文预报研究进展与 展望[J].水利学报,2019,50(12):1467-1478.[Liu Zhangjun, Guo Shenglian,Xu Xinfa,et al.Bayesian probabilistic hydrological forecasting: Progress and prospects[J]. Journal of Hydraulic Engineering,2019,50(12): 1467-1478.]   
[14] 雷晓辉,王浩,廖卫红,等.变化环境下气象水文预报研究进展 [J].水利学报,2018,49(1):9-18.[Lei Xiaohui,Wang Hao,Liao Weihong,et al. Advances in hydro-meteorological forecast under changing environment[J]. Journal of Hydraulic Engineering,2018, 49(1): 9-18.]   
[15] 舒章康,汪琳,金君良,等.TIGGE多模式降水预报产品检验与 集成研究[J].水利水运工程学报,2021(2):10-19.[Shu Zhangkang,Wang Lin, Jin Junliang,et al.Verification and integration of TIGGE multimode precipitation forecast products[J]. Hydro- Science and Engineering,2021(2): 10-19.]   
[16]赵琳娜,吴昊,田付友,等.基于TIGGE资料的流域概率性降水 预报评估[J].气象,2010,36(7):133-142.[Zhao Linna,Wu Hao, Tian Fuyou,et al.Assessment of probabilistic precipitation forecasts for the Huaihe Basin using TIGGE data[J]. Meteorological Monthly,2010,36(7):133-142.]   
[17]杜雅玲,陆桂华,吴志勇,等.基于TIGGE数据的中期降水预报 在江苏省的应用效果评估[J].南水北调与水利科技,2017,15 (6): 17-25,44.[Du Yaling,Lu Guihua,Wu Zhiyong,et al. Assessment of TIGGE medium-term precipitation forecast in Jiangsu Province[J]. South-to- North Water Transfers and Water Science & Technology,2017,15(6): 17-25,44.]   
[18] 高艳红,许建伟,张萌,等.中国 $4 0 0 ~ \mathrm { { m m } }$ 等降水量变迁与干湿 变化研究进展[J].地球科学进展,2020,35(11):1101-1112. [Gao Yanhong,Xu Jianwei, Zhang Meng,et al.Advances in the study of the $4 0 0 ~ \mathrm { m m }$ isohyet migrations and wetness and dryness changes on the Chinese mainland [J].Advances in Earth Science, 2020,35(11): 1101-1112.]   
[19] 陈庭兴,吕海深,朱永华.基于GEV分布的西营河流域洪水特 性分析[J].干旱区研究,2021,38(6):1563-1569.[Chen Tingx

ing,Lyu Haishen, Zhu Yonghua.Analysis of flood characteristics inXiyingRiverBasinbased onGEVdistribution[J].Arid Zone Research,2021,38(6): 1563-1569.]

[20] 王晓峰,张明明,尹礼唱,等.2000—2015年中国干旱半干旱地 区沙漠化进程驱动力研究[J].生态环境学报,2019,28(5):948-   
957.[Wang Xiaofeng, Zhang Mingming,Yin Lichang,et al. Study on the driving factors in desertification process in arid and semiarid region of China from 20OO to 2O15[J]. Ecology and Environmental Sciences,2019,28(5): 948-957.] [21] 马洁华,孙建奇，汪君,等.2018年夏季我国极端降水及滑坡泥 石流灾害预测[J].大气科学学报,2019,42(1):93-99.[Ma Jiehua, Sun Jianqi,Wang Jun,et al.Real-time prediction for 2018 JJA extreme precipitation and landslides[J]. Transactions of Atmospheric Sciences,2019,42(1): 93-99.] [22] 赵煜飞,朱江.近50年中国降水格点日值数据集精度及评估 [J].高原气象,2015,34(1): 50-58.[Zhao Yufei, Zhu Jiang.Assessing quality of grid daily precipitation datasets in China in recent 50 years[J]. Plateau Meteorology,2015,34(1): 50-58.] [23] 孙铭悦,吕海深,朱永华,等．2套气象数据在资料缺乏地区的 适用性评估——以呼图壁河流域为例[J].干旱区研究,2022,   
39(1): 94-1O3.[Sun Mingyue,Lyu Haishen, Zhu Yonghua,et al. Applicability assessment of two meteorological datasets in areas lacking data with the Hutubi River Basin as an example[J].Arid Zone Research,2022,39(1): 94-103.] [24] 赵琳娜,包红军,田付友,等.水文气象研究进展[J].气象,2012,   
38(2): 147-154.[Zhao Linna,Bao Hongjun, Tian Fuyou,et al.Advances in hydrometeorological research[J]. Meteorological Monthly,2012,38(2): 147-154.] [25]Wilks D S. Statistical Methods in the Atmospheric Sciences[M]. USA:Academic Press: 2011: 301-394. [26] 王在文,梁旭东,范水勇,等.数值模式降水评分对分辨率的敏 感性初探[J].暴雨灾害,2016,35(1):10-16.[Wang Zaiwen,Liang Xudong,Fan Shuiyong,et al. Impact of spatial resolution on precipitation forecast score in numerical weather prediction models [J]. Torrential Rain and Disasters,2016,35(1): 10-16.]

# Assessment of TIGGE precipitation forecast models in arid and semi-arid regions of China

HE Chaolul²，LYU Haishen1²，ZHU Yonghual²，LI Wentao'²，XIE Bingqi³, XU Kaili'²，LIU Mingwen1,2 (1.State Key Laboratoryof Hydrology-Water Resources and Hydraulic Enginering,Hohai University,Nanjing 210098,Jiangsu,China; 2.CollgeofHydrology and WaterResources,Hohai University,Nanjing 21098,Jiangsu, China; 3.Pearl River Water Resources Research Institute,Pearl River Water Resources Commission, Guangzhou 510630, Guangdong, China)

Abstract: Short- and medium-term precipitation forecast products are important to improve the prediction period and accuracy of flood forecasts.With global climate change,the prediction of precipitation patterns becomes increasingly complex and important.To date,there have been no available reports on the applicability of TIGGE precipitation products (a significant aspect of the most authoritative data set for short-and medium-term ensemble forecasts) in the arid and semi-arid regions of China.On the basis of precipitation data measured from $2 0 1 5 -$ 2017 in arid and semi-arid regions of China,the mean absolute deviation,root mean square error,TS score,and other indicators were used to analyze the precipitation forecast,precipitation classification forecast, precipitation detection ability,and spatial prediction accuracy.The prediction efects of the ECMWF, JMA,KMA,and UKMO models in the TIGGE data center were evaluated comprehensively in the study area.The results show that the four models effectively forecast light rain.The JMA modelhas the best forecast efficacy for light rain at different precipitation levels; for other precipitation levels,no significant diference was seen between the four models. The KMA model performs the worst for the daily precipitation forecast,whereas the ECMWF model is the most accurate.The evaluation results of precipitation detection capabilities under diferent precipitation thresholds show that ECMWF is more advantageous, especially when the threshold is $2 5 \ \mathrm { m m \cdot d ^ { - 1 } }$ . The spatial accuracy test results show that each model performs better in the range of $8 0 ^ { \circ } - 1 0 0 ^ { \circ } \mathrm { E }$ and $3 5 ^ { \circ } - 4 5 ^ { \circ } \mathrm { N }$ ，mainly in central Xinjiang and at the junction of Xinjiang, Gansu,and Qinghai provinces. Out of allthe models,the ECMWF model demonstrated the best performance and the KMA model the worst.

Keywords: TIGGE；precipitation forecast； precipitation level; space-prediction accuracy；arid and semi-arid regions; China