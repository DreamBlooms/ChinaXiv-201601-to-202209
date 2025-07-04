# 基于电磁感应数据的膜下滴灌土壤水分动态变化研究

E佳文1，彭杰'，刘新路'，吴家林'，齐威¹，王楠²，柳维扬}（1.塔里木大学植物科学学院,新疆 阿拉尔843300；2.浙江大学环境与资源学院,浙江 杭州310058)

摘要：快速、无损监测农田土壤水分含量，是智慧农业的重要研究内容。以新疆南疆阿拉尔国家农业科技园区膜下滴灌棉田为研究对象，运用EM38-MK2大地电导率仪快速、高效的获取了4组不同时期的棉田土壤表观电导率数据，并同步采集表层土壤( $( 0 { \sim } 2 0 \mathrm { c m } )$ )样品，通过构建表观电导率数据与室内测定含水量数据间的反演模型获取了测点的含水量数据，并按照土壤水分干旱分级标准对研究区土壤水分进行划分，综合利用GIS软件和地统计方法对土壤水分的时空变异性进行研究。结果表明：4个时期的土壤水分反演模型决定系数均大于0.80且均方根误差(RMSE)和平均绝对百分误差(MAPE)均较小，表明反演模型精度较高，土壤表观电导率与表层土壤水分相关性较好；不同时期土壤含水量数据表明土壤水分具有很强的时间变异性，变异性由中等变异转变为弱变异再转变为中等变异；受人为灌溉等因素的影响，变异函数模型也存在差异；半方差分析中4个时期的土壤水分块金值与基台值之比均大于 $7 5 \%$ ，表明土壤水分在空间上趋近于弱空间相关；高程反距离权重(IDW)插值图及水分克里格插值图表明微地形是影响土壤水分分布的重要因素。本研究可为干旱区膜下滴灌棉田土壤水分动态监测提供重要的方法支撑，从而更好地指导农业灌溉。

关键词：膜下滴灌；电磁感应；时空变异；棉田；地统计学

# 文章编号：

土壤水分是土壤组成中不可或缺的部分，是构成农业可持续发展的重要指标之一[]。有学者认为，干旱胁迫是制约植物生长的主要因子之一，仅干旱就影响到世界 $45 \%$ 的农业用地[2]。新疆地处亚欧大陆腹地，降水稀少，蒸发强烈。尤其南疆地区，受地理位置、气候条件及地表径流等因素的影响，水资源短缺，严重制约了该地区农业的发展。膜下滴灌技术因具增温保、节水保湿、促进水分高效利用等特点，在新疆棉田中被大面积推广，截至目前推广面积已超过 $2 . 6 6 \times 1 0 ^ { 6 } \mathrm { h m } ^ { 2 [ 3 ] }$ ,新疆已成为全国农业应用滴灌技术规模最大的片区。

土壤水分的实时监测是农田精准灌溉的重要内容之一。随着技术的发展及理论的不断完善，土壤水分的测量手段也更加丰富。传统土壤水分测量方法的最大局限是很难在有效时间内获得大范围土壤水分数据，适用尺度小，仅限于测量有限点的水分信息，对空间连续土壤水分信息的获取难度大，而土壤水分由于微地形、土壤质地、地下水位等因素的空间分布差异，具有强烈的空间变异特性，即使田间尺度也具有这种空间变异特性，这对土壤水分的实时监测带来了难度，因此，传统土壤水分观测手段在很大程度上限制了精准灌溉农业的发展[3]。电磁感应技术具有快速、高效及非破坏性的优势被广泛应用于土壤属性调查研究[4]。蒋志云等4通过实验构建模型肯定了EM38测量水分的可行性 $( R ^ { 2 } { = } 0 . 6 5 )$ 。Hossain等[5]通过验证不同高度的EM38深度响应函数，建立回归模型，对根区土壤含水量进行了较准确的预测。Reedy、Padhi、Sherlock等[6-8通过设立实验并验证，发现土壤水分与土壤表观电导率间存在着较高的相关性。目前，电磁感应技术主要应用于土壤含盐量的测定、土壤含盐量的空间变异及土壤剖面电导率的预测等[9-11]。对水分的预测主要用于农牧交错带退耕地[8、麦田土壤水分的测量[等方面。利用EM38-MK2对干旱区膜下滴灌棉田土壤水分动态变化方面的研究却鲜见报道。

综上，为探究膜下滴灌棉田土壤水分动态变化，本研究采集了新疆南疆阿拉尔市国家农业科技园区4组不同时期棉田土壤表观电导率数据及表层1 $\mathrm { 0 } { \sim } 2 0 \ \mathrm { c m }$ )土壤样品的含水量数据，通过统计分析建立了不同时期表层土壤水分的预测模型并对模型进行验证，探讨应用EM38-MK2测定十旱区膜下滴灌棉田不同时期土壤水分含量的思路及方法。根据土壤水分分级标准，综合应用GIS和地统计方法分析表层土壤水分的时空变异特征。

# 材料与方法

# 1.1 研究区概况

研究区位于新疆维吾尔自治区阿拉尔市12团国家农业科技园区 $\langle 8 0 ^ { \circ } 3 0 ^ { \prime } { \sim } 8 1 ^ { \circ } 5 8 ^ { \prime } \mathrm { ~ E ~ }$ 、 $4 0 ^ { \circ } 2 2 ^ { \prime }$ \~

$4 0 ^ { \circ } 5 7 ^ { \prime } \mathrm { N }$ ,图1)，平均海拔 $1 0 0 0 \mathrm { m }$ ,属温带大陆性干旱气候[12],全年干旱少雨,年均降雨量不足 $5 0 \mathrm { m m }$ 年均蒸发量高达 $2 0 0 0 \mathrm { m m } ^ { [ 1 3 ] }$ ,蒸降比为40:1,高额蒸发使该地区盐渍化现象严重，盐渍化易造成土壤表面板结和作物生理性干旱，对农作物的生长不利。本研究以园区内膜下滴灌棉田土壤水分为调查对象，种植棉花品种为新陆中78号，灌溉水引自塔里木河，地下水位 $1 . 5 { \sim } 2 . 0 ~ \mathrm { m }$ 。研究区面积约 $1 8 ~ \mathrm { h m } ^ { 2 }$ P区内地势相对平坦，利于EM38-MK2大地电导率仪大面积测量。棉花从播种至收获共灌水5次，灌溉时间分别为2018年6月22日、7月9日、7月25日、8月13日和8月25日，全年灌水量为 $5 8 5 0 \mathrm { m } ^ { 3 } { \cdot } \mathrm { h m } ^ { - 2 }$ ,其中冬灌和春灌为大水漫灌,灌水量为 $3 0 0 0 \mathrm { m } ^ { 3 } { \cdot } \mathrm { h m } ^ { - 2 }$ ，生育期内采用膜下滴灌方式,灌水量为 $2 8 5 0 \mathrm { m } ^ { 3 } { \cdot } \mathrm { h m } ^ { - 2 }$ ，土壤质地主要为砂壤土，土壤有机质平均含量较低,约为 $4 . 0 { \sim } 5 . 1 \ \mathrm { g } \cdot \mathrm { k g } ^ { - 1 \ [ 1 3 ] }$

# 1.2EM38-MK2结构

EM38-MK2大地电导率仪(图2)是通过电磁感应原理来获取土壤综合表观电导率(ECa)的仪器，该仪器设置有3个线圈，即分布于图2中的前、中、

![](images/df88f693b1980f39fb5d09b562cce6e77afbff6e62830d90a531af36d6385f0f.jpg)  
Fig.1 Geographic position of study area

![](images/302f4596a4e3073dca8534a507fbb0943d306ffabc14548e6b2a880e2eb4e6de.jpg)  
图1研究区地理位置图  
图2EM38-MK2大地电导率仪  
Fig.2 Conductivity meter EM38-MK2

# 干吴区地理

后部位，前部为发射线圈，中、后部为接收线圈，相邻线圈间为等间距 $0 . 5 \mathrm { ~ m ~ }$ ;该仪器有垂直偶极和水平偶极2种测定模式，当仪器处于垂直偶极模式时，可探测 $0 . 7 5 \mathrm { ~ m ~ }$ 和 $1 . 5 \mathrm { ~ m ~ }$ 深度范围内的数据（分别用$\mathrm { E C } _ { \mathrm { h 0 . 7 5 } }$ 和 $\mathrm { E C } _ { \mathrm { h } 1 . 5 }$ 表示)；当仪器处于水平偶极模式时，可探测 $0 . 3 7 5 \mathrm { m }$ 和 $0 . 7 5 \mathrm { m }$ 深度范围内的数据(分别用$\mathrm { E C } _ { \mathrm { v 0 } . 3 7 5 }$ 和 $\mathrm { E C } _ { \mathrm { v 0 . 7 5 } }$ 表示）。

# 1.3表观电导率数据与土样采集及处理

研究区南北长约 $9 0 0 \mathrm { ~ m ~ }$ ,东西长约 $2 0 0 \mathrm { m }$ 。表观电导率数据获取方法如下：以南北方向为主线，东西方向以 $2 0 ~ \mathrm { m }$ 为行间距，共设置10条南北向的测线（图1)。将EM38-MK2大地电导率仪设置为自动测定模式，数据采集频率为1个· $\mathrm { ~ s ~ } ^ { - 1 }$ ,表观电导率采集样点间距大致为 $1 \mathrm { m }$ ，每次采集表观电导率数据约9000个。分别于2018年6月3日（头水前）、7月7日（二水后）9月9日（五水后）10月27日（冬灌前）进行了4次表观电导率的采集。

每次采集表观电导率的同时，同步采集18个表层土壤样品。根据测线的表观电导率数据集大小，分别以最大值与最小值为上下限，确定研究区表观电导率的范围，将获得的表观电导率数据集划分为18个梯度，依次按照划分的表观电导率梯度采集土壤样品；记录采样点的表观电导率数据，用土钻采集样点表层土壤样品，保存于自封袋中并编号，防止水分蒸发。每次采样时间统一为北京时间11:00——13:00。

将采集的土样带回实验室清理完残膜、大于2$\mathbf { m } \mathbf { m }$ 的石子及作物根系后，装入干净铝盒，置于$1 0 5 ~ \mathrm { { ^ circ C } }$ 恒温箱中采用质量烘干法测定土壤含水量。空铝盒质量记为 $m _ { 0 }$ ,新鲜土样加铝盒质量记为 $m _ { 1 }$ 烘干后的土样及铝盒质量记为 $m _ { 2 }$ ，记土壤含水量为$w ( \% )$ 。

$$
w ( \% ) { = } ( m _ { \mathrm { 1 } } - m _ { \mathrm { 2 } } ) / ( m _ { \mathrm { 1 } } - m _ { \mathrm { 0 } } ) { \times } 1 0 0 \%
$$

# 1.4数据分析

采用 $\operatorname { E x c e l } 2 0 1 9$ 和 SPSS24软件进行数据处理;半变异函数模型及模型参数采用 $\mathrm { G S } { + } 7 . 0$ 软件计算;采用ArcGIS10.2进行克里格插值；采用反距离权重(Inverse distance weighting,IDW)进行高程数据基准插值。结合经典统计学和地统计学分析，对比不同时期土壤水分插值图与研究区高程插值图对土壤水分时空变异性进行分析。

# 1.5模型构建与精度验证

本文建模方法为多元线性回归（Multiplelinearregression,MLR）,模型精度验证采用决定系数 $\left( R ^ { 2 } \right)$ 、平均绝对百分误差（MAPE）均方根误差(RMSE）。$R ^ { 2 }$ 值反映观测值与预测值之间的相关性强度；RMSE用来检验模型的预测能力；MAPE用来验证模型的精度。 $R ^ { 2 }$ 值越大、RMSE值与MAPE值越小，表明模型的精度越高，预测能力越强。

# 2结果与分析

# 2.1土壤含水量解译模型的建立与验证

以EM38-MK2水平和垂直2种模式下所测的土壤表观电导率数据为因变量，实测土壤水分值为自变量，运用多元线性回归构建不同时期土壤含水率解译模型。建模时，将每次采集的18个土壤水分数据以2:1比例划分为建模集(12个)和验证集(6个），采用建模集和验证集 $R ^ { 2 }$ 、RMSE和MAPE检验模型精度。由表1可知，不同时期土壤水分解译模型建模集与验证集 $R ^ { 2 }$ 均大于0.80,与蒋志云等4的试验结果( $R ^ { 2 } { = } 0 . 6 5$ )具有一致性。对土壤水分解译模型进行精度验证，模型验证集 $R ^ { 2 }$ 、RMSE、MAPE与建模集的均大致相近，表明模型精度较高，稳定性较好。

表1土壤水分解译模型的验证  
Tab.1 Validation interpretation model of soil moisture   

<html><body><table><tr><td rowspan="2">日期(年-月-日)</td><td colspan="2">建模集</td><td colspan="2">验证集</td><td rowspan="2">MAPE/%</td></tr><tr><td>R</td><td>RMSE</td><td>R</td><td>RMSE</td></tr><tr><td>2018-06-03</td><td>0.87</td><td>0.87</td><td>0.84</td><td>1.10</td><td>8.45</td></tr><tr><td>2018-07-07</td><td>0.97</td><td>0.80</td><td>0.97</td><td>0.82</td><td>3.86</td></tr><tr><td>2018-09-09</td><td>0.91</td><td>0.54</td><td>0.90</td><td>0.71</td><td>3.99</td></tr><tr><td>2018-10-27</td><td>0.84</td><td>1.09</td><td>0.81</td><td>1.52</td><td>9.20</td></tr></table></body></html>

注:RMSE,均方根误差;MAPE,平均绝对百分误差。

不同时期的模型相比较而言，6、10月建模集与验证集 $R ^ { 2 }$ 较7、9月相对偏低，RMSE及MAPE则相对偏高。因研究区土壤类型为盐渍化土壤，种植前需对土壤漫灌压盐，将土壤表层盐分淋洗至耕作层以下，冬灌时间为2017年10月末。本研究测定土壤水分时间为头水前(2018年6月3日），冬灌后至头水前，因长时间未灌溉、气候、土壤质地等因素的影响，水分含量减少，使模型 $R ^ { 2 }$ 较7、9月偏低；10月测定土壤水分时间为2018年10月27日（冬灌前），而第5次灌溉时间为2018年8月25日，10月末测定土壤水分时棉花已全部采摘，棉花采摘前需先对棉花叶面喷施脱叶剂，喷施脱叶剂加速了棉花叶片的凋零脱落，植被覆盖度显著降低，导致水分散失加剧;其次影响土壤水分含量的因素为地膜覆盖，棉花收获前需先进行揭膜回收，揭膜回收加剧了土壤水分的蒸发，造成土壤水分含量降低，导致10月模型 $R ^ { 2 }$ 降低。但总体来讲，6月和10月的模型 $R ^ { 2 }$ 均大于0.80,精度较高。

# 2.2土壤水分数据分析

每次采集表观电导率数据约9000个，不同时期共采集约36000个表观电导率数据。表观电导率数据结合反演模型获得研究区所有测点的土壤水分含量数据。对不同时期土壤水分数据分别进行分析，统计特征值见表2。由表2可知，不同时期土壤水分最小值介于 $5 . 7 8 \% \sim 1 2 . 9 5 \%$ 之间，最大值介于$1 7 . 0 6 \% { \sim } 2 7 . 7 4 \%$ 之间，头水前及棉花采摘后土壤含水量较低。研究区表层土壤盐分含量较高，尤其在生产季末，即棉花采摘完的10月底，因此播种前需对土壤进行冬灌压盐。而6月采集土壤样品时间为头水灌溉前，距上次冬灌间隔8个月，且正值夏季，此时也是棉花的生理需水期,棉花根系大量吸收土壤水分，主要受气温、蒸发等因素的影响，土壤水分含量降低。2018年8月25日为研究区最后1次灌溉，而最后1次采集土壤样品为10月，受灌溉制度及天气因素的影响，土壤水分含量较7、9月发生变化。

由表2可知，9月变异系数小于 $10 \%$ ，表明9月

# 表2不同时期土壤水分统计特征值

Tab.2 Statistical characteristic values of soilmoistureatdifferentperiods   
表3不同时期土壤水分半方差函数模型参数  

<html><body><table><tr><td colspan="5">日期(年-月-日)最小值/%最大值/%平均值/%标准差变异系数/%</td></tr><tr><td>2018-06-03</td><td>5.78</td><td>17.06 11.37</td><td>3.12</td><td>27.44</td></tr><tr><td>2018-07-07</td><td>12.61 27.74</td><td>16.35</td><td>2.06</td><td>12.59</td></tr><tr><td>2018-09-09</td><td>12.95 19.99</td><td>14.96</td><td>0.89</td><td>5.94</td></tr><tr><td>2018-10-27</td><td>6.12</td><td>17.81</td><td>12.27 2.61</td><td>21.27</td></tr></table></body></html>

土壤水分在水平方向为弱变异;而6、7、10月变异系数在 $10 \% { \sim } 1 0 0 \%$ 之间，表明6、7、10月土壤水分在水平方向为中等变异。对比不同时期的变异系数可以发现，6、7、9月3个月变异系数随着月份逐渐降低。受喷施脱叶剂、灌溉制度及天气等多方面因素的影响，10月变异系数较9月相比明显上升，10月土壤水分在水平方向上由9月的弱变异演变为中等变异。不同时期土壤水分含量最大值与最小值之比分别为2.95、2.19、1.54、2.91。该比值表明，6、10月土壤水分含量的空间变异最强，9月相对较弱，这一点可以从变异系数明显看出，

为了进一步分析模型的可靠性，将每期采集的18个土样的水分实测值统计值与研究区利用模型反演的水分统计值进行了对比。6、7、9月和10月采集土样的实测水分含量数据平均值分别为 $1 1 . 4 9 \%$ 、$1 6 . 9 3 \% 1 4 . 4 9 \% \cdot 1 2 . 8 5 \%$ ，标准差分别为3.06、2.10、1.00、2.49，变异系数分别为 $2 6 . 6 3 \% . 1 2 . 4 0 \% . 6 . 9 0 \%$ ）$1 9 . 3 8 \%$ 。预测土壤水分含量与样品实测土壤水分含量的各值均相差较小，且变化趋势一致，表明EM38-MK2能够较精确预测土壤水分含量，对农业灌溉有一定指导意义。

# 2.3土壤水分的空间分析

本研究最优半方差函数理论模型的选取及模型参数调整参考赵亚楠等[14]、杨晓潇等[15]、左小安等的研究。由吕真真等文献可知，当数据符合正态分布方能进行普通克里格插值，否则可能存在比例效应。经SPSS24软件检验，6、7、9、10月预测土壤水分数据近似服从正态分布，符合地统计分析的要求。经 $\mathrm { G S } { + } 7 . 0$ 软件计算，2018年不同时期土壤水分最优半方差函数模型及模型参数(表3)，其中，$C _ { 0 }$ 为块金值， $C _ { 0 } { + } C$ 为基台值，Range为变程，

块金值与基台值之比反映系统空间相关性的程度，空间相关性强弱的划分参考孙运朋等[18]的文献。由表3可知，不同时期块金值与基台值之比均大于 $7 5 \%$ ，表明土壤水分空间相关程度为弱空间相

Tab.3 Parameters of semi-variogram models of soil moisture at different periods   

<html><body><table><tr><td>日期(年-月-日)</td><td>理论模型</td><td>块金值(Co)</td><td>基台值(Co+C)</td><td>块金值/基台值/%</td><td>变程/m</td><td>决定系数(R)</td></tr><tr><td>2018-06-03</td><td>球状模型</td><td>0.0077</td><td>0.0361</td><td>78.7</td><td>131.6</td><td>0.85</td></tr><tr><td>2018-07-07</td><td>球状模型</td><td>0.0014</td><td>0.0169</td><td>91.8</td><td>116.2</td><td>0.81</td></tr><tr><td>2018-09-09</td><td>球状模型</td><td>0.0008</td><td>0.0036</td><td>77.1</td><td>121.3</td><td>0.84</td></tr><tr><td>2018-10-27</td><td>指数模型</td><td>0.0095</td><td>0.0621</td><td>84.7</td><td>136.8</td><td>0.91</td></tr></table></body></html>

# 干旱区地理

关。不同时期土壤水分块金值 $C _ { 0 }$ 均较小，介于$0 . 0 0 0 8 { \sim } 0 . 0 0 9 5$ 之间，表明由采样误差短距离变异引起的正基底效应较弱[19]。6、7、9、10月土壤水分含量空间自相关距分别为 $1 3 1 . 6 ~ \mathrm { m } , 1 1 6 . 2 ~ \mathrm { m } , 1 2 1 . 3 ~ \mathrm { m }$ $1 3 6 . 8 \mathrm { ~ m ~ }$ ,且10月土壤水分含量自相关距最大，其次为6、9月，7月最小;通过自相关距的差异可以看出空间异质性程度的不同，由自相关距可知，10月土壤水分含量变异强度强于其他3个时期，7月的短程变异强于其他3个时期。

2018年研究区4个时期理论模型也具有差异，6、7、9月理论模型为球状模型，10月为指数模型出现此差异的原因与当地的棉田灌溉制度及人为因素(揭膜)有密切关系。

# 2.4不同时期土壤水分空间分布特征

按土壤水分干旱程度分级标准2将土壤水分分为5个等级：湿润（土壤含水率 ${ > } 2 0 \%$ )，适宜水分（ $1 5 \% { \sim } 2 0 \%$ )，轻度干旱( $12 \% - 1 5 \%$ )，中度干旱( $5 \% \sim$ $12 \%$ ),严重干旱(土壤含水率 ${ < } 5 \%$ )。利用地统计软件ArcGIS10.2对2018年不同时期的表层土壤水分含量值进行普通克里格插值，并根据土壤水分含量分级标准进行分级后获得研究区的土壤水分含量分级图(图3）。

为了进一步分析微地形对土壤水分空间分布的影响，对EM38-MK2电导率仪记录的高程数据进行处理，将研究区高程最小值 $9 9 9 . 1 \mathrm { ~ m ~ }$ 作为基准高程，以高程值与基准值的差值来进行IDW插值，插值结果如图4所示。

由图3可以看出，6月研究区大部分区域以重度干旱和中度干旱为主;重度干旱区大面积且集中分布在研究区东南部、中部及西北部，约占研究区总面积的 $4 4 . 3 6 \%$ ,适宜棉花生长的土壤含水量面积仅占总面积的 $2 . 2 4 \%$ ；7月土壤水分含量较6月有明显改善，主要以轻度干旱为主，占总面积的 $6 4 . 5 3 \%$ 。中度干旱区分布在研究区的西北部、中部及东部的边缘地带，占总面积的 $1 8 . 8 1 \%$ 。经2018年6月22日第1次灌溉后，7月适宜棉花生长的区域在6月的基础上明显扩大。2018年8月25日为最后1次灌溉，由图3可以看出，9月土壤水分含量已出现向自然状态土壤水分含量恢复的趋势。至10月，研究区土壤水分含量已基本恢复至自然状态下的含量，干旱程度、分布区域与6月相似，以重度干旱和中度干旱为主。

由图4可以看出，研究区地势受人为耕作的影响，地形微起伏变化较明显，最大地势差可达$0 . 0 6 6 1 \mathrm { ~ m ~ }$ 。有研究表明，起伏的微地形增加了地表的粗糙程度，凹陷的地表对水有更强的捕捉能力;

![](images/397253e8c16ff55fdb424cda3403878433be190a9b4ffda58e443a87196433bf.jpg)  
图32018年不同时期土壤水分含量分级  
Fig.3Classification of soil moisture content map at different periods in 2018

图4研究区高程反距离权重(IDW)插值图 Fig.4Inverse distance weighting (IDW) interpolation of elevation of the study area   
![](images/94eb75a1b84a3d72c0bd0a08bf1773c0346d18ce440bc53f81561733429bbab8.jpg)  
注：基准高程 $9 9 9 . 1 \mathrm { ~ m ~ }$ □

同时，微地形的起伏状况也会导致水文过程发生变化，受地表与地下径流的影响，土壤中的水分也随之发生分异和积累[21]。

由图4可以看出，研究区微地形东部略高于西部,南部微地形起伏程度高于北部。结合土壤水分插值图可以看出研究区干旱程度南部与东部较重，北部与西部较轻，研究区灌溉方式为膜下滴灌，灌溉后水分受自身重力、蒸发作用及作物根系的吸收，滴灌水无法渗入土壤深处，大部分分布在土壤表层。水分在土壤表层分布，极易受微地形因素的影响，使水分分布不均，这点由水分分布图及高程IDW插值图可以明显看出。研究区北部靠近塔里木河，塔里木河在一定程度也影响了研究区北部的土壤水分分布。土壤质地也是影响土壤水分含量的一个重要因素，研究区土壤为沙壤土，而沙壤土对水的束缚性较弱，容易造成表层土壤水分散失。

# 3结论

本研究以新疆南疆阿拉尔国家农业科技园区膜下滴灌棉田为研究对象，运用EM38-MK2大地电导率仪快速、高效的获取了4组不同时期棉田土壤表观电导率数据，并同步采集了表层土壤(0\~20cm)样品，通过构建表观电导率与室内测定含水量数据之间的反演模型获取了测点的含水量数据，分析了土壤水分含量与表观电导率之间的相关性，并对土壤水分时空变异性进行研究。主要结论如下：（1）反演模型决定系数均大于0.80，且RMSE和MAPE均较低，表明土壤水分含量与表观电导率之间具有良好相关性，EM38-MK2能够较精确预测土壤水分含量，可以更好地指导农业灌溉。(2）受当地棉田灌溉制度及人为灌溉因素的影响，不同时期最优变异函数模型也表现出差异，具体为6、7、9月为球状模型，10月为指数模型。(3）高程反距离权重(IDW)插值图表明研究区微地形东部略高于西部，南部高于北部，最大地势差可达 $0 . 0 6 6 1 \mathrm { ~ m ~ }$ ;克里格插值图表明微地形影响了土壤水分的分布；土壤水分分级标准及克里格插值图表明不同时期土壤水分变化明显，水分分布较复杂。

综上，本研究可为干旱区膜下滴灌棉田土壤水分动态监测提供重要的方法支撑，从而更好地指导农业灌溉。

# 参考文献(References)

[1]周倩倩,丁建丽,杨爱霞,等.基于实测高光谱和电磁感应的绿 洲土壤含水量估测[J].干旱区资源与环境,2018,32(3):152- 157.[Zhou Qianqian,Ding Jianli, Yang Aixia,et al. Estimation of soil moisture spatial distribution based on measured spectral and electromagnetic induction instruments in the arid oasis[J]. Journal of Arid Land Resources and Environment,2018,32(3): 152-157.]   
[2] Abdelraheem A, Esmaeili N,O'Connell M,et al.Progress and perspective on drought and salt stress tolerance in cotton[J]. Industrial Crops and Products,2019,130:118-129.   
[3] 赵波,王振华,李文昊.滴灌方式及定额对北疆冬灌棉田土壤水 盐分布及次年棉花生长的影响[J].农业工程学报,2016,32(6): 139-148.[Zhao Bo,Wang Zhenhua,Li Wenhao.Effects of winter drip irrigation mode and quota on water and salt distribution in cotton field soil and cotton growth next year in northern Xinjiang[J] Transactions of the Chinese Society of Agricultural Engineering,

# 干旱区地理

2016,32(6): 139-148.]   
[4]蒋志云,李小雁,张志华,等.基于EM38电导率仪土壤水分探 测研究[J].干旱区研究,2015,32(1):48-55.[Jiang Zhiyun,Li Xiaoyan, Zhang Zhihua,et al. EM38 for soil moisture content estimation in the farming-pastoral ecotone in Inner Mongolia[J].Arid Zone Research,2015,32(1): 48-55.]   
[5]Hossain MB,Lamb D W,Lockwood PV,et al.EM38 for volumetric soil water content estimation in the root-zone of deep vertosol soils[J]. Computers and Electronics in Agriculture,2O10,74(1): 100-109.   
[6]Reedy R C,Scanlon B R.Soil water content monitoring using electromagnetic induction[J]. Journal of Geotechnical and Geoenvironmental Engineering,2003,129(11): 1028-1039.   
[7]Padhii J, Misra R K.Sensitivity of EM38 in determining soil water distribution inan irrigated wheat field[J]. Soil and Tillage Research,2011,117: 93-102.   
[8]Sherlock MD,Mcdonnell JJ.Anew tool for hillslope hydrologists: Spatially distributed groundwater level and soil water content measured using electromagnetic induction[J]. Hydrological Processes, 2003,17(10): 1965-1977.   
[9]张为政,殷丽娟.电磁感应电导仪(EM38)测定土壤含盐量的研 究[J].应用生态学报,1993,4(3):289-294.[Zhang Weizheng, Yin Lijuan. Determination of soil salt content with electromagnetic induction conductometer (EM38)[J]. Chinese Journal of Applied Ecology,1993,4(3): 289-294.]   
[10] 李晓明,杨劲松,刘梅先,等.基于电磁感应的典型干旱区土壤 盐分空间异质性[J].农业工程学报,2010,26(12):97-101.[Li Xiaoming,Yang Jingsong,Liu Meixian,et al. Spatial heterogeneity of soil salinity in typical arid area based on electromagnetic induction[J]. Transactions of the Chinese Society of Agricultural Engineering,2010,26(12): 97-101.]   
[11] 李洪义,史舟,程街亮,等.基于EM38的土壤剖面电导率预测 研究[J].中国农业科学,2008,41(1):295-302.[Li Hongyi, Shi Zhou, Cheng Jieliang,et al. Inversion of soil conductivity profiles based on EM38 apparent electrical conductivity[J]. Scientia Agriculture Sinica,2008,41(1): 295-302.]   
[12] Peng J,Biswasc A, Jiang Q S,et al.Estimating soil salinity from remote sensing and terrain data in southern Xinjiang Province, China [J]. Geoderma,2019,337: 1309-1319.   
[13] 刘新路,彭杰,冯春晖,等.基于电磁感应仪数据的南疆棉田土 壤电导率反演模型研究[J].土壤学报,2020,57(3):646-655. [Liu Xinlu,Peng Jie,Feng Chunhui, et al.Inversion model for soil conductivity in cotton field in south Xinjiang based on EM38- MK2 data[J].Acta Pedologica Sinica,2020,57(3): 646-655.]   
[14] 赵亚楠,周玉蓉,王红梅.宁夏东部荒漠草原灌丛引入下土壤水 分空间异质性[J].应用生态学报,2018,29(11):3577-3586. [Zhao Yanan, Zhou Yurong,Wang Hongmei. Spatial heterogeneity of soil water content under introduced shrub (Caragana korshinski) in desert grassland of the eastern Ningxia, China[J]. Chinese Journal of Applied Ecology,2018,29(11): 3577-3586.]   
[15] 杨晓潇,王秀兰,王计平,等.天津市滨海新区土壤水盐空间变 异分析[J].中国水土保持科学,2019,17(3):39-47.[Yang Xiaoxiao,Wang Xiulan,Wang Jiping,et al. Spatial variation analysis of soil moisture and salinity in Tianjin Binhai New Area[J].Science of Soil and Water Conservation,2019,17(3): 39-47.]   
[16] 左小安,赵哈林,张铜会,等.科尔沁不同类型沙地土壤水分在 降水后的空间变异特征[J].干旱区地理,2006,29(2):275-281. [Zuo Xiaoan, Zhao Halin, Zhang Tonghui,et al. Spatial variability of soil moisture after rainfallin different type sands of Horqin Sand [J].Arid Land Geography,2006,29(2): 275-281.]   
[17]吕真真,杨劲松,刘广明.基于EM38-MK2的滨海土壤电导率精 确解译模型[J].排灌机械工程学报,2014,32(10):894-900.[Lu Zhenzhen, Yang Jinsong, Liu Guangming.Accurate modelsof interpreting soil electrical conductivity based on EM38-MK2[J]. Journal of Drainage and Irrigation Machinery Engineering,2O14,32(10): 894-900.]   
[18] 孙运朋,陈小兵,张振华,等.滨海棉田土壤盐分时空分布特征 研究[J].土壤学报,2013,50(5):891-899.[Sun Yunpeng, Chen Xiaobing, Zhang Zhenhua,et al. Temporal- spatial distribution of soil salt incoastal coton fieldsoilJ].ActaPedologica Sinica, 2013,50(5): 891-899.]   
[19] 姚荣江,杨劲松,姜龙.电磁感应仪用于土壤盐分空间变异及其 剖面分布特征研究[J].浙江大学学报(农业与生命科学版), 2007,33(2):207- 216.[Yao Rongjiang,Yang Jingsong，Jiang Long.Study on spatial variability and profile distribution characteristics of soil salinity by Kriging with an electromagnetic induction[J].Journal of Zhejiang University (Agriculture and Life Sciences),2007,33(2): 207-216.]   
[20] 宋帅杰.抗蒸腾剂和保水剂对雷竹林抗高温干旱生理的影响 [D].杭州:浙江农林大学,2015.[Song Shuaijie.Physiological effects of antitranspirant and super absorbent polymer on heat and drought resistance of Phylostachys violascens forest[D]. Hangzhou: Zhejiang A&F University,2015.]   
[21]司梦可,曹建生,阳辉.微地形变化对地表水文过程影响的研究 进展[J].中国生态农业学报(中英文),2019,27(10):1587-1595. [Si Mengke, Cao Jiansheng, Yang Hui.Advances in research on the effects of micro-topography changes on surface hydrological processes[J]. Chinese Journal of Eco-Agriculture,2019,27(10): 1587-1595.]

# Dynamic variation of soil moisture in field with drip irrigation under film using electromagnetic induction data

WANG Jiawen', PENG Jie'， LIU Xinlu'， WU Jialin', QI Wei'， WANG Nan²，LIU Weiyang' (1.College of Plant Science,Tarim University,Alar8433Oo,Xinjiang,China；2.Schoolof Environment and Resources,Zhejiang University,Zhejiang 31Oo58,Hangzhou, China)

Abstract: Rapid and non-destructive monitoring of soil moisture content in farmland are essential contents of accurate irigation. Traditional soil water measurement methods are applicable to small scale and difficult to obtain spatial continuous soil moisture information.Soil moisture is afected by microtopography and soil texture.It has strong spatial variability characteristics.Electromagnetic induction technology has been widely used in soil properties investigation owing to itsadvantages ofrapid,efficient,and non-destructive.In this study, the coton fields under mulched drip irigation in Alar National Agricultural Science and Technology Park in southern Xinjiang are considered.EM38-MK2 is used to obtain soil apparent electrical conductivity data of four groups of cotton fields at different stages rapidly and effectively. Surface soil samples ( $\mathrm { ( 0 - 2 0 ~ c m ) }$ ）are collected simultaneously.The observation points’water content is obtained by constructing an inversion model between the soil apparent electrical conductivity data and the indoor measured water content data.Then,the study area's soil moisture is divided into the soil moisture and drought classification criteria.Finally,the soil moisture's spatiotemporal variability is investigated using GIS software and geostatistical methods syntheticaly.The results show that the determination coeficients of the soil moisture inversion model in four diferent periods are greater than 0.80,and root mean square error (RMSE)and mean absolute percentage error(MAPE)are small,indicating thatthe inversion model has high precision and the correlation between soil apparent electrical conductivity and surface soil moisture is good.The data of soil moisture content in diferent periods show that moisture has strong time variability，which changes from medium variability to weak variabilityand then to medium variability. Moreover,the variation function model is diferent owing to the influence of artificial irigation factors.In the semi-variance analysis,the ratios of Nugget and Sillof soil moisture in four different periods are more than $7 5 \%$ ， indicating that soil moisture tends to be a weak spatial correlation.The maps of elevation inverse distance weight (IDW) interpolation and moisture Kriging interpolation show that microtopography is an essential factor affecting soil moisture distribution.This study can provide an important method of support for the dynamic monitoring of soil moisture incottn fields under mulched drip irrigation in arid areas to better guide agricultural irrigation.

Key words: drip irrigation under film； electromagnetic induction； spatiotemporal variability；coton field;geo-statistics