# 科尔沁沙丘草甸相间地区土地利用与覆被识别

曹文梅¹，刘廷玺¹，王喜喜²，王冠丽'，李东方¹，童新'(1.内蒙古农业大学水利与土木建筑工程学院,内蒙古自治区水资源保护与利用重点实验室，内蒙古 呼和浩特 010018；2.美国欧道明大学，诺福克23529)

摘要：为了实现基于单独光学遥感数据对科尔沁沙丘草甸相间地区土地利用与覆被(LULC)类型的识别,选用2018年64景Sentinel-2影像,结合影像分割技术,利用植被物候信息和生境特征，建立了基于群落水平的LULC决策树识别规则，总体分类精度为0.91,Kappa系数为 $0 . 8 9$ 。分类结果显示：研究区旱地分布面积最大，占 $3 3 . 7 9 \%$ ，灌木群落次之，占 $2 5 . 0 3 \%$ ，高多样性半灌木群落和乔木林相近，分别为 $1 4 . 5 4 \%$ 和 $10 \%$ ,低多样性半灌木群落、草甸地和流动沙地分别占 $5 \%$ 左右，剩余类型的总占比小于 $5 \%$ 。该方法不仅可以准确反映研究区覆被类型的空间分布情况,还能给出不同覆被类型的生长发育状况，可为该区域物质循环研究提供基础数据，同时为该区域历史LULC识别提供阈值参考。

关键词：遥感；土地利用与覆被；多尺度分割；决策树；分类；哨兵2号卫星；多时相；科尔沁沙地

科尔沁沙地是中国四大沙地中最大的沙地，其生态系统脆弱，是华北地区沙尘暴的主要来源[1-2]。土地利用与覆被(landuse/landcover,LULC)监测是该地区风沙化趋势预测的基础。Duan等[3]利用Landsat系列数据研究了当地土地风沙化的时空动态，指出2010年的沙化土地占监测面积( $( 1 . 2 5 \times 1 0 ^ { 5 }$ $ { \mathrm { k m } } ^ { 2 } .$ 的 $2 4 \%$ ，而 $7 1 \%$ 为轻度和中度沙化土地，植被覆盖度达到 $30 \%$ 以上，主要分布在科尔沁沙地的中部和东部。位于科尔沁沙地东南边缘，科左后旗的沙化土地占监测面积( $1 1 6 3 2 \mathrm { k m } ^ { 2 } )$ 的 $5 0 \%$ ,其中 $78 \%$ 为轻度和中度沙化土地，可见当地的生态修复措施起到了显著成效[4]。另外，有研究表明沙地的LULC和水量平衡具有复杂关系[5-7],例如,在科尔沁沙地南部的张古台，由于阔叶林及农田种植面积的增加，导致当地的地下水位下降，从而使原始引进的樟子松人工林出现枯萎，出现大面积死亡的现象。因此，识别科尔沁沙地的LULC对当地的土地管理调配及可持续性发展研究具有重要意义。

随着遥感数据源的不断丰富以及遥感应用和计算机技术的快速发展，利用遥感数据获取土地利用与覆被信息已成为识别LULC的主要手段[8]。前期关于科尔沁沙地LULC的研究多数是基于植被覆盖度进行的分类[3.9]。随着当地沙化土地的不断修复，我们研究的重心应该转移到植被覆盖类型的精细划分以及植被多样性监测上。He等[10-]指出监测外来物种对生境结构和条件改造以及关键物种发生和传播变化的预警信号对于生态系统的管理至关重要。另外，Rocchini等[12-13]通过对比IKONOS和Landsat数据反演植被种类及多样性时的精度，指出对于植被多样性的反演，光谱分辨率比空间分辨率更重要。Conese和Maselli'4指出在复杂地貌的植被分类过程中可以通过多时相数据，借助植被物候信息从而提高反演分类精度。Sentinel-2卫星是欧空局哥白尼计划中发射的第2组卫星，它不仅比Landsat卫星产品的空间分辨率高，而且具有包括可见光、近红外(NIR）、植被红边和短波红外(SWIR)区的13个光谱波段。另外，还具有重访周期短达五天的高时间分辨率[15-16],因此,使用多时相Sentinel-

2卫星数据有望实现群落水平上的LULC精准识别。

本文以科尔沁东南边缘的沙丘草甸相间地区为例，基于2018年植被生长季64景Sentinel-2遥感数据和地面调查数据，利用植被物候信息和生境特征，结合基于面向对象影像分割技术的多分辨率分割（Multi-Resolution Segmenation,MRS)算法,建立基于群落水平的LULC决策树识别规则，以求给出能反应下垫面植被生长发育信息的研究区LULC空间分布格局，为后期该地区的生态系统健康评价提供参考数据。

# 1研究区概况

研究区位于科尔沁沙地东南缘，是西辽河流域中的一个闭流区域。隶属于内蒙古自治区通辽市科尔沁左翼后旗，为典型的荒漠化的沙丘草甸相间地区，地理坐标 $1 2 2 ^ { \circ } 1 0 ^ { \prime } { \sim } 1 2 3 ^ { \circ } 1 0 ^ { \prime } \mathrm { E } , 4 2 ^ { \circ } 5 0 ^ { \prime } { \sim } 4 3 ^ { \circ } 4 6 ^ { \prime } \mathrm { N } ,$ 海拔高度 $1 3 3 { \sim } 2 6 7 ~ \mathrm { m }$ ,总面积约 $5 7 8 7 . 3 2 \mathrm { k m } ^ { 2 }$ ，属半干旱-半湿润大陆性季风气候。研究区冬季主要受到蒙古地区冷高压的控制，多刮偏北风或偏西风，在夏季主要受大陆低气压以及副热带高压所控制，多以偏南和西南风为主。地表水和地下水资源较丰富，湖泊、沼泽、水泡密布(图1)，整个地表由多个相似小单元随机组合形成微波状起伏平原,每个小单元是由包围着湖泊的草甸斑块和其周围的沙丘斑块组成的[17]。本文选择研究区中的一个典型小单元作为LULC识别决策树规则建立的试验区。

# 2 数据来源

# 2.1Sentinel-2遥感影像

本研究使用Sentinel-2的level1C级影像产品（经过正射校正和亚像元级几何精校正的大气表观反射率)作为原始分析数据，影像通过欧洲空间局网站(https://scihub.copernicus.eu)检索获取,共计包括2018年植被生长季16次过境的64景产品。图2列出了过境的具体时间和试验区的气候状况。使用Sentinel Application Platform（SNAP）平台和$\mathrm { S e n } 2 \mathrm { c o r } 2 . 4$ 插件[18]对level1C级产品进行辐射定标和大气校正生成L2A级数据。采用最邻近内插法将L2A级数据的10个波段重采样生成空间分辨率为 $1 0 \mathrm { ~ m ~ }$ 的产品，10个波段分别是 $2 { \sim } 4 , 8 ( 1 0 \mathrm { m } ) , 5 \sim$ 7,8A,11和 $1 2 ( 2 0 \mathrm { m } )$ 。然后利用SNAP软件对各个时间的每个波段的4景影像进行镶嵌，最后利用ENVI软件将产品裁剪到研究区。

# 2.2地面调查数据

2018年7—9月，根据沙丘草甸相间分布的地貌类型，在试验区布设了54个调查点。在调查时，对于生长分布整齐的农田和乔木林只做踩点调查，对于生长分布不规则的其他植被做精细的调查。在每个精细调查点先布设一个 $1 0 \mathrm { m } { \times } 1 0 \mathrm { m }$ 的灌木、半灌木调查大样方，然后在大样方的4角和中心共计布设5个 $1 \mathrm { m } { \times } 1 \mathrm { m }$ 的草本调查小样方。分别调查样方内植被的种类、高度、密度，对于无性繁殖物种，其分株被视为物种密度的基本单位[19]。最后用收割法分物种获取样方内每一种植物的3个标准株，装入密封的塑料袋带回实验室，用烘箱 $6 0 ~ \mathrm { { ^ { \circ } C } }$ 干燥$4 8 \mathrm { { h } }$ ,测定其干质量，乘以密度得到该物种的地上生物量。利用获得的生物量、密度、高度计算每个调查点的Shannon多样性指数[20]

![](images/2012dcaea34cbb7fb511ef7c579bda8ee2e8d5bf834668fdf38a15ef9b1af792.jpg)  
图1研究区及试验区位置示意图  
Fig.1 The geographical location and the relief map of the study area and test area

![](images/ca2b2d4621e0531582d1495f59890f816b52b6ee78e4f7a489b42430176b0f3d.jpg)  
图22018年试验区气象条件及遥感卫片过境时间  
Fig.2Meteorological conditions and transit date of satellite in the test area of 2018

# 3 研究方法

# 3.1研究区LULC分类

参照前期对试验区进行的植被分类研究[2I-22]，结合2018年地面调查数据，研究区LULC被划分为10类，分别是：（1）居民用地，表示房屋分布聚集的区域；(2）水域;(3）旱地，主要作物是玉米；（4）水田，主要作物是水稻；（5）乔木林，代表树种是杨树；(6）灌木群落，优势物种是小叶锦鸡儿(Caraganamicrophylla)；（7）低多样性半灌木群落，优势物种是差巴嘎蒿（Artemisiahalodendron）；（8）高多样性半灌木群落,优势物种有冷蒿(Artemisia frigida）、草麻黄(Ephedra sinica)和冰草(Agropyron cristatum）;(9)草甸地,优势物种有苔草(Carexduriuscula)和芦苇(Phragmitescommunis）;（10）流动沙地,包括无植被覆盖和覆盖少量植被两种情况，当有植被覆盖时，优势物种是沙米（Agriophyllum squarrosum）和差巴嘎蒿，群落中植被种类少，生物量和多样性低。不同植被群落类型的组成及结构特征信息见表1。

# 3.2研究方法概述

基于群落水平研究区LULC识别步骤如下：第一步基于试验区实测数据构建LULC决策树识别规则。首先探寻影像最优分割方式，然后导入训练样本生成对象样本，分析不同LULC类型的归一化植被指数(Normalized Difference VegetationIndex，ND-VI)和各个波段反射率的时序变化规律，建立识别规则，并根据验证样本调试识别规则使解译结果最接近真实情况。其中训练样本为2018年的地面实测数据，验证样本是2015年采集的31个 $5 0 ~ \mathrm { m } { \times } 5 0 ~ \mathrm { m }$ 的调查点[2]，具体样本数量分配见表1。对于水域和居民用地特征明显的地物，采用人工勾绘的方法进行验证样本添加。第二步应用建立的识别规则实现研究区LULC解译，并借助Googleearth对结果进行粗评。

表1土地利用/覆被类型的实测数据统计结果  
Tab.1 Statistical results of field data on land use/cover types   

<html><body><table><tr><td>土地利用/覆被类型</td><td>优势物种</td><td>调查点/个</td><td>植被种类(类)</td><td>地上单位面积生物量/(g·m2)</td><td>Shannon多样性指数(H)</td><td>验证样本</td></tr><tr><td>草甸地</td><td>芦苇、苔草</td><td>6</td><td>9.17±4.95</td><td>438.65±340.23</td><td>1.51±0.68</td><td>125</td></tr><tr><td>流动沙地</td><td>沙米、差巴嘎蒿</td><td>5</td><td>6.33±1.6</td><td>107.35±58.08</td><td>1.09±0.31</td><td>55</td></tr><tr><td>低多样性半灌木群落</td><td>差巴嘎蒿</td><td>4</td><td>9.25±1.09</td><td>122.55±77.17</td><td>1.66±0.10</td><td>75</td></tr><tr><td>高多样性半灌木群落</td><td>冷蒿、麻黄、冰草</td><td>7</td><td>13.67±2.92</td><td>229.32±155.94</td><td>1.99±0.13</td><td>110</td></tr><tr><td>灌木群落</td><td>小叶锦鸡儿</td><td>16</td><td>13.88±4.57</td><td>1292.5±1367.16</td><td>1.81±0.25</td><td>130</td></tr><tr><td>乔木林</td><td>杨树</td><td>6</td><td>一</td><td>一</td><td>一</td><td>70</td></tr><tr><td>旱地</td><td>玉米</td><td>7</td><td>一</td><td>一</td><td>一</td><td>185</td></tr><tr><td>水田</td><td>水稻</td><td>3</td><td>二</td><td>二</td><td>二</td><td>25</td></tr></table></body></html>

注：-表示无测量数据。

3.2.1多尺度影像分割解译过程中的影像分割通过多分辨率分割(MRS)算法实现[23]。该算法具有3个用户定义参数：尺度、形状和紧凑度，尺度参数是判断所考察像素是否合并到临近影像对象的标准，形状参数的值等于1减去颜色参数，紧凑度参数的值等于1减去光滑度参数[24]。通过不同分割参数产生的不同对象层之间存在属性继承关系，确定好分割参数对于LULC的正确识别很重要[25-26]。首先通过目视法，选取居民用地、水域和植被3种差异显著的地物挑选用于影像分割的数据源，并采用ESP2(Estimatingthe ScaleParameter2)最优尺度工具[27]结合人工调试参数对比的方法获得最优分割参数。

3.2.2生长季时序NDVI数据处理NDVI指数是目前应用最广泛的植被指数，计算公式如下：

$$
\mathrm { N D V I } = { \frac { R _ { \mathrm { N I R } } - R _ { \mathrm { R E D } } } { R _ { \mathrm { N I R } } + R _ { \mathrm { R E D } } } }
$$

式中： $R _ { \mathrm { R E D } }$ 为红光波段的反射率； $R _ { \mathrm { N I R } }$ 为近红外波段的反射率，分别为Sentinel-2数据的波段4和8。

首先通过对计算生成的初始NDVI时序数据进行线性插值，获得4月4日至10月31日每间隔 $1 5 \mathrm { d }$ 的NDVI时序数据,例如, $\mathrm { N D V I _ { 5 \ / H 1 9 \ / H } { = } N D V I _ { 5 \ / H 9 \ / H } { + } ( N D \mathrm { - } }$ $\mathrm { V I } _ { 5 \sharp 2 4 \sharp } - \mathrm { N D V } \mathrm { I } _ { 5 \sharp 9 \sharp } ) ^ { \prime } ( 1 0 / 1 5 ) ,$ 。为进一步去除NDVI时序数据中的噪声，使其更为符合植被生长发育过程，采用双重逻辑函数滤波(DoubleLogistic,DL)法[28]对NDVI时序数据进行平滑处理（图3），采用 seasonal amplitude方法模拟植被生长过程，将Starttime和Endtime的参数均设置为0.5，获得植被NDVI季节最大值（ $\mathrm { \Delta N D V I _ { \mathrm { m a x } } }$ )和生长季开始时间$\mathrm { ( T i m e _ { s } ) }$ ），以上操作过程均在Timesat3.129软件中完成。

3.2.3非植被识别对水域的识别使用归一化水体指数（Normalized Difference Water Index,NDWI）,计算公式如下：

$$
\mathrm { N D W I } = \frac { R _ { \mathrm { G R E E N } } - R _ { \mathrm { N I R } } } { R _ { \mathrm { G R E E N } } + R _ { \mathrm { N I R } } }
$$

![](images/40aa128526fa83ef714142e8a678603fa9708456af030972904da5dbed47923d.jpg)  
图32018年单个像元乔木林时序NDVI双逻辑 斯蒂滤波处理过程   
Fig.3The processed NDVI curves of single pixel about forest by Double Logistic filter

式中： $R _ { \mathrm { G R E E N } }$ 为绿光波段的反射率； $R _ { \mathrm { N I R } }$ 为近红外波段的反射率，分别为Sentinel-2数据的波段3和8。

流动沙地的划分使用根据像元二分模型推导出的植被覆盖指数（Vegetation Coverage Index,VCI）[30-31],计算公式如下：

$$
\mathrm { V C I } = \frac { \mathrm { N D V I } - \mathrm { N D V I } _ { \mathrm { s o i l } } } { \mathrm { N D V I } _ { \mathrm { v e g } } - \mathrm { N D V I } _ { \mathrm { s o i l } } }
$$

式中： $\mathrm { \Delta N D V I _ { s o i l } }$ 为裸地对应的像元数值; $\mathrm { N D V I _ { v e g } }$ 为完全被植被覆盖时的像元数值，在本研究中，NDVI设置为 $\mathrm { \Delta N D V I _ { \mathrm { { m a x } } } }$ ,根据地面调查数据,将 $\mathrm { \Delta N D V I _ { \mathrm { s o i l } } }$ 设置为$0 . 2 5 , \mathrm { N D V I _ { v e g } }$ 设置为0.8。

由于居民用地中包含NDVI较低的裸地和房屋，以及NDVI较高的绿化和院内种植土地，所以通过NDVI值及波段反射率的时序变化很难划分。首先基于8月10日的真彩图，通过房屋的颜色选择样本，即选择颜色条件满足 $\mathrm { R } { \geqslant } 2 0 0 , \mathrm { G } { \leqslant } 1 5 0 , \mathrm { B } { \leqslant } 1 5 0$ 的对象为样本，然后在影像分割的基础上，通过基于样本分类功能划分出居民用地，划分流程如图4所示。

# 4结果与分析

# 4.1LULC决策树识别规则

图5a为生长季7种覆被类型的NDVI变化曲线，与植被的物候信息相关。可以看出，由于乔木林和草甸地的返青时间比其他植被早，从5月初到6月初，他们的NDVI均值高于其他植被。由于水田和旱地的返青时间和快速生长期比其他植被晚，从

![](images/612e6fc1a542433fef356cf94883b94e4e8a69da8e578951b058c6d41fd0d856.jpg)  
Fig.4 Schematic diagram of village remote sensing interpretation steps

![](images/96813ccc39ff0234c5d48c8bb8a7e802205270838e3c5aaa2817b6fc0ec253a5.jpg)  
图4居民用地遥感解译步骤示意图  
图5各覆被类型的遥感反演信息特征  
Fig.5Features of remote sensing inversion information of various types of cover

7月下旬到10月初，他们的NDVI均值高于其他植被。由于灌木的返青时间比半灌木早且长势更茂盛，在研究期间,灌木群落的NDVI均值大于半灌木群落。图5b为不同覆被类型对短波红外波段(B11)反射率的时间变化序列，与植被下垫面的水分条件有关。在研究期间，水田的平均反射率值最低，草甸地次之，低多样性半灌木群落最高，其他覆被类型的反射率比较接近。虽然各种覆被类型的遥感特征在平均水平上差异较为显著，但是由于相同覆被类型之间存在一定的发育差异，因此，需要寻找合适的划分规则和阈值使解译结果最接近真实情况。

综上所述，经过反复调试对比，建立的研究区LULC决策树识别规则如图6所示。首先划分居民用地，基于8月10日影像的10个波段进行第一次分割，分割尺度、形状参数、光滑度分别设置为108、0.9和0.1，基于导入的房屋样本进行分类。然后划分水域，基于5月4日影像的10个波段进行第二次分割，分割尺度、形状参数、光滑度分别设置为83、0.4和0.5，为了避免水中植被对NDWI指数的影响，以及考虑到研究区4月19日影像部分有云覆盖的情况，将4月19日和5月4日两期产品的NDWI指数的最大值大于0的对象定义为水域。接着对研究区的覆被类型进行详细识别，基于8月10日影像的10个波段进行第三次分割，分割尺度、形状参数、紧凑度分别设置为52、0.4和0.5。首先提取流动沙地，将VCI小于 $1 0 \%$ 的对象定义为流动沙地。其次提取农田，将返青时间大于阈值6(4月4日为1，每隔15d数值加1)，且7月上旬的NDVI增长率大于阈值0.1的对象中满足 $\mathrm { \Delta N D V I _ { \mathrm { m a x } } }$ 大于阈值0.5的对象定义为农田。接着提取草甸地，因为研究区草甸地表层含水量比固定、半固定沙丘、流动沙丘普遍偏大的特点[32],将对植被和土壤水分敏感的短波红外波段的反射率小于某个阈值的对象定义草甸地，采用5月24日影像的B11数据，阈值为0.3。接着提取乔木林，将返青时间小于特定阈值5的对象定义为乔木林。最后基于隶属度函数构建模糊规则[33识别半灌木群落和灌木群落，定义在6月3日NDVI的模糊区间从小增长到大是半灌木群落到灌木群落，模糊区间设定

![](images/4f9b631cf5008face7467d00d3524ceb9dadf60341fb976455fd3f89fbec3863.jpg)  
图6研究区土地利用/覆被类型决策树分类  
Fig.6 Classification decision tree of land use/cover type in the study area

为0.25\~0.3。

使用对水汽变化比较敏感的B11将农田划分为旱地和水田，与草甸地识别使用相同的数据，阈值为0.2。因为分布高多样性半灌木群落的沙丘恢复状态比分布低多样性半灌木群落的好，土壤的持水性能更好[21.34],将对B11反射率大于某个阈值的对象定义为低多样性半灌木群落，否则是高多样性半灌木群落，采用的是8月2日的数据，阈值设定为0.4。

# 4.2LULC识别结果

研究区的LULC空间分布如图7所示。本研究的总解译面积为 $5 5 5 8 . 9 1 ~ \mathrm { k m } ^ { 2 }$ ,其中旱地的分布面积最大，占总面积的 $3 3 . 7 9 \%$ 。灌木群落次之，占$2 5 . 0 3 \%$ ，主要分布在研究区的西北部分。高多样性半灌木群落和乔木林的分布面积相近，分别占总面积的 $1 4 . 5 4 \%$ 和 $10 \%$ 。剩余LULC的分布面积相对较小，占总面积的百分比由小到大为：水田$0 . 5 1 \%$ ，水域 $0 . 9 4 \%$ ，居民用地 $2 . 9 1 \%$ ，流动沙地$4 . 7 9 \%$ ，低多样性半灌木群落 $5 . 6 6 \%$ ，草甸地$5 . 6 7 \%$ ,其中高多样性半灌木群落也主要分布在研究区的西北部分，低多样性半灌木群落主要围绕流动沙地分布。

![](images/1c51115e843f9cf0452b59596849ed275f99cc7f5577d79fafdbbb46ad9deafd.jpg)  
图7土地利用/覆被类型解译结果  
Fig.7Interpretation results of land use/cover typesin the studyarea

# 4.3分类结果的评价

为了验证构建分类规则的精度和应用潜力，首先根据验证样本对试验区的分类结果进行精度评价，选用的评价指标有Kappa系数、总体分类精度、用户精度和制图精度，然后结合Googleearth数据对研究区的分类结果进行粗评价。其中用户精度表示在被分为某类的所有样本中，其真实样本所占的比例。制图精度表示某类的所有真实样本被正确划分的比例。总体分类精度表示所有样本中被正确分类的像元总数除以总像元数。Kappa系数能够结合所有因素综合评价分类的结果，更加准确的反映分类的整体精度。

从表2中可见，训练样本的总体分类精度为0.92，用户精度除乔木林和灌木群落以外均在0.90以上，制图精度除高多样性半灌木群落以外都在0.80以上，可能是由于部分乔木林的生长状态不符合正常物候，例如部分人工种植的杨树林在缺水状态下发育不良，因此可能被解译为灌木群落。其中水域、居民用地和水田的用户精度和制图精度均为1,经计算Kappa系数为0.89,说明对试验区的分类结果是比较接近真实状况的。另外，对于研究区分类结果，借助Googleearth工具，随机选择研究区内的3个位置，对范围内能够识别的水域、流动沙地、居民用地、乔木林和灌木群落进行模糊验证，同样达到了几乎完全一致的评价水平。

表2试验区分类精度  
Tab.2 Classification accuracy of study area   

<html><body><table><tr><td></td><td>乔木林</td><td>灌</td><td>低多样性落</td><td>高多样性落</td><td>草甸地</td><td>旱地</td><td>水田</td><td>流动</td><td>水域</td><td>居民</td><td>用精度</td></tr><tr><td>乔木林</td><td>60</td><td>0</td><td>0</td><td>0</td><td>25</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0.71</td></tr><tr><td>灌木群落</td><td>10</td><td>130</td><td>0</td><td>28</td><td>0</td><td>10</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0.73</td></tr><tr><td>低多样性半灌木群落</td><td>0</td><td>0</td><td>65</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>高多样性半灌木群落</td><td>0</td><td>0</td><td>5</td><td>82</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0.94</td></tr><tr><td>草甸地</td><td>0</td><td>0</td><td>0</td><td>0</td><td>100</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>旱地</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>175</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>水田</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>25</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td>流动沙地</td><td>0</td><td>0</td><td>5</td><td>0</td><td>0</td><td>0</td><td>0</td><td>55</td><td>0</td><td>0</td><td>0.92</td></tr><tr><td>水域</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>50</td><td>0</td><td>1</td></tr><tr><td>居民用地</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>75</td><td>1</td></tr><tr><td>制图精度</td><td>0.86</td><td>1</td><td>0.87</td><td>0.75</td><td>0.8</td><td>0.95</td><td>1</td><td>1</td><td>1</td><td>1</td><td></td></tr><tr><td>总体分类精度</td><td>0.91</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>Kappa系数</td><td>0.89</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr></table></body></html>

# 5结论

采用时间分辨率、空间分辨率和光谱分辨率均较高的Sentinel-2数据，根据植被物候信息以及生境条件对研究区植被进行识别。依据返青时间，覆被类型可划分为早、中、晚3大类，分别是返青最早的乔木林和草甸地，返青最晚的农田以及中间返青的其他植被群落。另外，根据植被生长环境的水分条件，可以将覆被类型划分为种植在水中的水稻，分布在水域周围水分条件相对较好的植被，有玉米地与草甸群落，以及分布在沙地水分条件相对差的植被。此外，还根据沙地植被多样性高低与土壤表层水分条件的关系，对半灌木群落进行了划分。根据上述植被特征并借助多分辨率分割算法建立决策树识别规则，总体分类精度为0.91,Kappa系数为0.89，不仅达到了研究区土地利用与覆盖类型精细划分的目的，而且能够反映不同下垫面的物候信息和生境条件，为以后研究区的生态系统健康评价提供了基础数据。

# 参考文献(References)：

[1] Li J,Xu B,Yang X,et al.Historical grassland desertification changes in the Horqin Sandy Land,Northern China (1985-2013) [J]. Scientific Reports,2017,7(3009): 1-12.   
[2] Zhang G,DongJ,Xiao X,et al. Effectiveness of ecological restoration projects in Horqin Sandy Land,China based on SPOT-VGT NDVI data[J]. Ecological Engineering,2012,38(1): 20-28.   
[3] DuanH,Wang T,Xue X,etal.Dynamics of aeolian desertification and its driving forces in the Horqin Sandy Land,Northern China [J].Environ Monit Assess,2014,186:6083-6096.   
[4] 那音太,乌兰图雅,秦福莹.基于3S技术的科尔沁沙地土地荒 漠化动态监测——以科尔沁左翼后旗为例[J].干旱区资源与 环境,2010,24(10): 50-54.[Na Yintai,Wulan Tuya, Qin Fuying. Dynamic monitoring of Horqin sandy land desertification based on 3S techniques:A case study in Horqin Left Wing Banner[J]. Journal of Arid Land Resources and Environment,201o,24(10): 50- 54.]   
[5] Zheng X,Zhu JJ,Yan QL,et al.Effects of land use changes on the groundwater table and the decline of Pinus sylvestris var. mongolica plantations in southern Horqin Sandy Land,Northeast China [J].Agricultural Water Management,2012,109: 94-106.   
[6] 焦树仁.辽宁省章古台樟子松固沙林提早衰退的原因与防治措 施[J].林业科学,2001,37(2):131-138.[Jiao Shuren.Report on the causes of the early decline of Pinus slyvestris var.Mongolica shelterbelt and its preventaive and control measures in Zhang Gutai of Liaoning Province[J]. Scientia Silvae Sinicae,2001,37 (2): 131-138.]   
[7]Li X R, Xiao HL, Zhang JG,et al. Long-term ecosystem effects of sand- binding vegetation in the Shapotou Region of the Tengger Desert,Northern China[J].Restoration Ecology,2004,12(3): 376- 390.   
[8]陈百明,刘新卫,杨红.LUCC 研究的最新进展评述[J].地理科 学进展,2003,22(1): 22-29.[Chen Baiming,Liu Xingwei, Yang Hong. Review of most recent progresses of study on land use and land cover change[J]. Progress in Geography,2003,22(1): 22-29.]   
[9] Wang Y, Zhang J,Tong S,etal.Monitoring the trends of aeolian desertified lands based on time-series remote sensing data in the Horqin Sandy Land, China[J]. Catena,2017,157: 286-298.   
[10] He K S,RociniD,Neteler M,etal.Benefitsof hyperspectralre mote sensing for tracking plant invasions Divers[J].Diversity and Distribution,2011,17: 381-392.   
[11]Vicente J,Randin CF, Gongalves J,et al.Where willconflicts between alien and rare species occur after climate and land- use change? A test with a novel combined modelling approach[J]. Biological Invasions,2011,13: 1209-1227.   
[12]Rocchini D.Efectsofspatialandspectralresolutio intiating ecosystem $\alpha$ diversity by satelite imagery[J]. Remote Sensing Environment, 2007,111: 423-434.   
[13] Nagendra H, Rocchini D, Ghate R,etal.Assessing plant diversity in a dry tropical forest: Comparing the utility of Landsat and IKONOS satellite images[J]. Remote Sensing,2010,2(2): 478-496.   
[14]Conese C, Maselli F. Use of multitemporal information to improve classification performance of TM scenes in complex terrain[J].Remote Sensing,1991,46: 187-197.   
[15]Drusch M, Del Bello U,Carlier S,et al. Sentinel-2: ESA's optical high-resolution mission for GMES operational services[J].Remote Sensing Environment, 2012,120: 25-36.   
[16] 田颖,陈卓奇,惠凤鸣,等.欧空局哨兵卫星 Sentinel-2A/B数据 特征及应用前景分析[J.北京师范大学学报(自然科学版), 2019,55(1): 57-65.[Tian Ying,Chen Zhuoqi,Hui Fengming,et al. ESA Sentinel-2A/B satellite: Characteristics and applications [J]. Journal of Beijing Normal University(Natural Science Edition), 2019, 55(1): 57-65. ]   
[17] 黄天宇,王冠丽,李东方,等.科尔沁沙地沙丘——草甸梯级生 态系统不同气象条件下气候学足迹特征[J].干旱区研究, 2019,36(5): 1127-135.[Huang Tianyu, Wang Guanli,LiDongfang,et al. Climatological footprints in dune-meadow cascade ecosystem under different meteorological conditions in the Horqin Sandy Land[J].Arid Zone Research,2019,36(5): 1127-1135.]   
[18]Muller-Wilm, U. Sen2Cor 2.5.5—Software Release Note[EB/OL]. https://step.esa.int/main/new-release-of-sen2cor-2-5-5,2019- 2-4.   
[19]Hutchings MJ.Weight-density relationships in ramet populations of clonal perennial herbs,with special reference to the $- 3 / 2$ power law[J]. Journal of Ecology,1979,67(1): 21-33.   
[20] Shannon C E.A mathematica theory of communication[J]. Bell System Technical Journal,1948,27(3): 479-523.   
[21] 曹文梅,刘小燕,王冠丽,等.科尔沁沙地自然植被与生境因子 的 MRT分类及DCCA分析[J].生态学杂志,2017,36(2):318- 327.[Cao Wenmei,Liu Xiaoyan,Wang Guanli,et al. Combined analyses of MRT and DCCA on relationships between plant community distribution and ecological factors of Horqin Sandy Land [J. Chinese Journal of Ecology,2017,36(2): 318-327.]   
[22] 包永志,刘廷玺,段利民,等.科尔沁沙地混生小叶锦鸡儿和人 工杨树光合特性及其对气候的响应[J].干旱区研究,2019,36 (2): 42O-429.[Bao Yongzhi, Liu Tingxi,Duan Limin,et al. Photosynthetic traits of Caragana microphylla and Populus spp.and their responses to climate in the Horqin Sandy Land[J].Arid Zone Research,2019,36(2): 420-429.]   
[23]Benz UC,Hofmann P,Willhauck G,et al. Multi-resolution,objectoriented fuzzy analysis of remote sensing data for GIS-ready information[J]. SPRS Journal of Photogrammetry & Remote Sensing, 2004,58:239-258.   
[24] Trimble Germany Gmb H.eCognition Developer 8.9 User Guide [EB/OL]. Trimble Germany GmbH, Munich,Germany,2013.   
[25] 滑永春,李增元,高志海.面向对象分割与混合像元分解相结合 提取沙化土地信息[J].干旱区研究,2020,37(5):1346-1352. [Hua Yongchun,Li Zengyuan,Gao Zhihai. Extraction of sand information using object-oriented segmentation combined with decomposition of mixed pixels[J].Arid Zone Research, 2020,37(5): 1346-1352.]   
[26] 邬亚娟,刘廷玺,童新,等.基于面向对象的干旱半干旱地区植 被分类[J].干旱区研究,2020,37(4):1026-1034.[Wu Yajuan, Liu Tingxi, Tong Xin,et al.Vegetation classification in arid and semi-arid areas using an object-oriented method[J]. Arid Zone Research,2020,37(4): 1026-1034.]   
[27]Drägu L,Csillik O,Eisank C,et al. Automated parameterisation for multi- scale image segmentation on multiple layers[J]. ISPRS Journal Photogramm Remote Sensing,2014,88(100): 119-127.   
[28]Beck P S A,Atzberger C,Hpgda KA,et al. Improved monitoring of vegetation dynamics at very high latitudes:A new method using MODIS NDVI[J]. Remote Sensing of Environment,2006,99: 321- 334.   
[29] Jönsson P,Eklundh L. TIMESAT: A program for analyzing time-series of satellite sensor data[J]. Computers & Geosciences,2004, 30: 833-845.   
[30] 李苗苗.植被覆盖度的遥感估算方法研究[D].北京:中国科学 院,2003.[Li Miaomiao.The Study on Remote Sensing Estimation Method of Vegetation Coverage[D].Beijing: Chinese Academy of Sciences,2003.]   
[31] 王永芳,张继权,马齐云,等.21世纪初科尔沁沙地沙漠化对区 域气候变化的响应[J].农业工程学报,2016,32(2):177-185. [Wang Yongfang, Zhang Jiquan,Ma Qiyun, et al.Response of aeolian desertification to regional climate change in Horqinsandy land at beginning of 21st century[J]. Transactions of the Chinese Society of Agricultural Engineering,2016,32(2): 177-185.]   
[32] 史小红,李畅游,刘廷玺.科尔沁沙地坨甸相间地区土壤水分空 间分布特性分析[J].中国沙漠,2007,27(5):837-842.[Shi Xiaohong,Li Changyou,Liu Tingxi.Analysis on spatial characteristics of soil water in marshland-dune areas in Horqin Sandy Land[J]. Journal of desert research,2007,27(5): 837-842.]   
[33] 汪求来.面向对象遥感影像分类方法及其应用研究[D].南京: 南京林业大学,2008.[Wang Qiulai.Study on Object-Oriented Romote Sensing Image Classification and Its Application-Taking Urban Vegetation Extraction in Futian, Shenzhen City for Example [D].Nanjing: Nanjing Forestry University,2008.]   
[34] 张继义,赵哈林,张铜会,等.科尔沁沙地植物群落恢复演替系 列种群生态位动态特征[J]).生态学报,2003,23(12):2741- 2746.[Zhang Jiyi, Zhao Haling, Zhang Tonghui,et al. Niche dynamics of main populations of plants communities in the restoring succession process in Horqin Sand Land[J].Acta Ecologica Sinica,2003,23(12): 2741-2746.]

# Land use and land cover classifications of Horqin Sandy Land dune-meadow areas

CAO Wenmei'， LIU Tingxi'， WANG Xixi, WANG Guanli', LI Dongfang'， TONG Xing' (1.WaterConservancyand CivilEngineering College,InnerMongolia Agricultural University,Inner Mongolia Water Resource Protection and Utilization Key Laboratory,Hohhot O1OO18,Inner Mongolia, China; 2.Civil and Environmental Engineering,Old Dominion University,Norfolk 23529,Virginia,USA)

Abstract: In this study,we determine land use/land cover (LULC) types using only optical remote sensing data in a dune-meadow area of Horqin Sandy Land in northeast China. We used 64 Sentinel-2 remote sensing images from 2018.An LULC decision tree recognition rule was established by combining image segmentation technology, vegetation phenology information,and habitat characteristics.Theoverallclassification accuracy was 0.91,and the Kappa coeffcient was O.89.The clasification results show that most of the study region was dryland area, accounting for $3 3 . 7 9 \%$ ，followed by shrub communities at $2 5 . 0 3 \%$ . High- diversity semi- shrub communities and arbor forests accounted for $14 . 5 4 \%$ and $10 \%$ ,respectively,while low- diversity semi- shrub communities, meadowlands,and mobile sand lands account for about $5 \%$ each.The total proportion of other LULC types was less than $5 \%$ ． The results show that this interpretation method better reflects the spatial distribution ofthe LULC while also providing growth and development data for diferent cover types.These data can be used to study material cyclesand provide threshold references for historical LULC identification of Horqin Sandy Land.

Keywords: remote sensing; land use/land cover; multi-resolution segmenation;decision-trees; clasification; Sentinel 2-A/B; time series;Horqin SandyLand