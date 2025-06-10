# 内蒙古半干旱区蒸散估算和归因分析

韩典辰¹，张方敏¹，陈吉泉²，李云鹏³，卢琦45，卢燕宇(1.南京信息工程大学应用气象学院/江苏省农业气象重点实验室,江苏 南京210044；2.密歇根州立大学地理环境空间科学系全球变化观测中心,密歇根 东兰辛MI48825；3.内蒙古自治区生态与农业气象中心,内蒙古 呼和浩特010051；4.中国林科院荒漠化研究所,北京10091；5.中国林科院沙漠林业实验中心,北京100091;6.安徽省气象局气象科学研究所大气科学与卫星遥感安徽省重点实验室,安徽 合肥230031)

摘要：蒸散(Evapotranspiration,ET)是生态系统水循环中的重要一环,决定了生态系统水分和热量传输。从区域尺度对蒸散及其蒸腾(Transpiration,T)和蒸发(Evaporation， $E$ )组分进行量化，认识环境因素对其的影响机制，有助于合理利用、分配水资源，为研究气候变化对区域生态系统水文循环的影响提供参考。基于生态系统生产力模拟(Boreal ecosystem productivity simulator,BEPS)模型,验证模型在研究区域的适用性，量化1981—2018年内蒙古半干旱区的ET及其组分的变化情况，并对其进行归因分析。结果表明：经不同数据验证，BEPS模型计算结果能够精确反应研究区域ET及其组分的分布情况和变化趋势。1981—2018年研究区草地、农田和森林多年平均ET分别为 $2 7 8 . 2 2 \ \mathrm { m m } \cdot 3 6 2 . 5 0 \ \mathrm { m m }$ 和 $3 0 8 . 8 1 \ \mathrm { m m }$ 。 $E , T$ 和ET多年呈显著上升趋势，上升速率分别为0.42$\mathrm { m m } { \cdot } \mathrm { a } ^ { - 1 } { \cdot } 0 . 6 3 \ \mathrm { m m } { \cdot } \mathrm { a } ^ { - 1 }$ 和 $1 . 0 5 \ \mathrm { m m ^ { \cdot } a ^ { - 1 } }$ 。ET与 $T$ 在全区域内空间分布格局相似，与 $E$ 相反，ET年际波动主要受到 $T$ 年际波动的影响。综合影响因子的变化和 $E , T , { \mathrm { E T } }$ 对因子的敏感性，研究区域草地和农田 $T$ 和ET以及森林的ET主要受到饱和水汽压差(VPD)和平均气温(TEMP)变化的控制。农田和森林归一化植被指数(Normalized difference vegetable index,NDVI)都呈减小趋势,但森林环境 $T$ 对NDVI的变化更加敏感，因此负贡献更大。

关键词：蒸散；蒸发；蒸腾；BEPS模型；半干旱区

# 文章编号：

蒸散(Evapotranspiration,ET)表示陆面水分转化为水蒸汽后进入大气的过程[1]，主要由蒸发(Evaporation, $E$ )和蒸腾(Transpiration,T)组成，是生态系统水循环中的重要一环，与水分物理传输过程和能量转换过程密切相关。随着气候变化和人类城市化发展,ET发生了明显且复杂的变化[3]。从区域尺度量化蒸发、蒸腾和蒸散情况，认识环境因素对其的影响机制，有助于科学认识区域水文循环过程，促进区域水资源管理，为气候变化影响生态系统水文循环的相关研究提供科学参考[4]

半干旱地区生态环境较脆弱，气候变化与人类活动极易对生态系统带来不可逆影响[5]。由于降水少，水资源时空分布不均匀，使得水分成为制约半干旱地区生态系统发展的重要因素[6-7]。蒸散作为半干旱地区水循环中的主要组成之一，其变化特征受到植被自身特性和环境条件的影响，具有显著的区域异质性和季节差异性[8]。众多学者对半干旱地区蒸散时空格局和变化规律进行了研究。代鹏超等[9]基于陆地表面能量平衡算法(Surface energy bal-ancealgorithmforland,SEBAL)研究了精河流域蒸散的时空变化，认为近60a蒸散呈波动减小趋势，且空间分布与地表利用类型有关。金学杰等"基于地表能量平衡系统（Surface energy balance system,SEBS)模拟了黑河下游蒸散变化，表明不同地表利

# 干旱区地理

用类型蒸散有相似的季节变化特征，但变化幅度不同。蹇东南等"采用互补相关理论模型，研究蒸散与气象要素的关系，认为下垫面供水和实际水汽压变化使得蒸散增加。王思如等[2]利用生态水文模型，分析了科尔沁沙地气象因子变化和蒸散的关系，认为降水的年际变化是影响蒸散的主要因子。对比分析，发现我国半干旱地区蒸散空间分布不均匀，变化趋势及其主控因子存在一定差异，并且少有研究将蒸散拆解为蒸腾和蒸发，进一步分析蒸散过程中水分的分配问题。

气候变化与人类活动加剧的背景下，内蒙古半干旱区的锡林郭勒和乌兰察布地区暖干化使得当地水分供需平衡存在不确定性[13]。分析其蒸散时空变化不仅能帮助揭示水文循环机理，又有利于评估区域水分亏缺状况，为当地干旱灾害评估与水资源开发利用提供科学依据。因此本研究选择位于半干旱区的锡林郭勒盟和乌兰察布市作为研究区，分析和量化目标区域蒸发、蒸腾和蒸散的时空变化及其组分关系，对比不同气象要素和植被生长状况对蒸发、蒸腾和蒸散变化的影响，揭示半干旱区生态系统蒸发、蒸腾和蒸散对气候变化的响应特征及主控因子。

# 1材料与方法

# 1.1 研究区概况

本文研究区域为内蒙古半干旱区的锡林郭勒盟与乌兰察布市，地理位置位于 $4 0 . 1 6 ^ { \circ } { \sim } 4 6 . 7 7 ^ { \circ } \mathrm { N }$ $1 1 0 . 3 3 ^ { \circ } \sim 1 1 9 . 9 1 ^ { \circ } \mathrm { E }$ 之间(图1）。该区域面积约为$2 8 . 5 6 \times 1 0 ^ { 4 } ~ \mathrm { k m } ^ { 2 }$ ,多年平均总降水量为 $3 1 4 . 7 6 ~ \mathrm { m m }$ ,多年平均气温为 $3 . 1 2 ~ \mathrm { ^ { \circ } C }$ ,属于温带大陆性气候，地表覆盖类型主要以草地和农田为主。研究区内2个代表性草地生态观测站[4为多伦站和锡林浩特站，经纬度分别为 $4 2 . 5 3 ^ { \circ } \mathrm { N }$ ， $1 1 6 . 2 2 ^ { \circ } \mathrm { E }$ 和 $4 3 . 5 3 ^ { \circ } \mathrm { N }$ $1 1 6 . 6 7 ^ { \circ } \mathrm { E }$ ，有长期水汽通量观测试验，用于本研究对比验证。

根据地表植被覆盖类型数据统计，1981—2018年研究区草地、农田和森林多年平均分别占$7 5 . 0 7 \% . 1 1 . 6 7 \% . 5 . 9 4 \%$ ，植被覆盖分布面积变化较小,其中草地面积增长 $1 . 5 0 \%$ ,农田面积减少 $0 . 8 4 \%$ ，森林面积共减少 $1 . 5 6 \%$ 。因此本研究忽略由于植被覆盖类型变化的影响，主要探究气候变化和植被生长状况对研究区域水循环的影响。

注：该图基于国家测绘地理信息局标准地图服务网站下载的审图号为GS(2019)3333号的标准地图制作，底图边界无修改。下同。

![](images/43c295342df3cb902de0a366d0c5f53a72790b28db2c14b14bc634765a9416a2.jpg)  
图1研究区示意图  
Fig.1Distribution map of study area

# 1.2模型介绍

本文采用生态系统生产力模拟(Boreal ecosys-temproductivitysimulator,BEPS)模型模拟区域的蒸腾、蒸发和蒸散。模型最主要的特点是将冠层叶片分为阳叶和阴叶，通过进行气孔导度的积分对叶片尺度的Farquhar瞬时光化学模型进行时空尺度转换,模拟计算逐日的碳水循环通量[15-16]。经过不断发展和完善，BEPS被证实能够准确的估算生态系统蒸散过程,并成功应用于东亚[17-18]和中国[19]等地。模型的ET主要计算过程详见Chen等[20]和Liu等[21]

# 1.3数据来源

模型需要的气象输人数据来自于国家气象科学数据中心的中国地面气候资料日值数据集(http:/data.cma.cn），包括1981—2018年国家气象站点的气温、降水量、相对湿度、日照时数等日数据。该数据集经严格的质量控制，包括空间和时间上的一致性检查及相应的人工核查与更正，进一步对数据进行异常值剔除。研究区域地势较平坦，因此采用Kriging方法插值至 $0 . 0 1 ^ { \circ }$ 并根据研究区域边界掩膜裁剪[22],获得 $9 5 8 \times 6 6 2$ 像元数的空间日数据集。

1981—2018年的叶面积指数(Leaf areaindex,LAI)数据来源于中国科学院地理科学与资源研究所刘荣高团队制作的每8d的 $1 ~ \mathrm { k m }$ GLOBMAPLAIV3产品,该产品经验证具有较高的精度[23]。将数据重采样至像元分辨率为 $0 . 0 1 ^ { \circ }$ ，并掩膜至与气象数据相同大小，统一作为模型输入数据

地表利用类型数据来源于中国科学院地理科学与资源研究所资源环境科学数据中心（http://www.resdc.cn/)。该数据集以LandsatTM/ETM遥感影像为主要数据源，通过人工目视解译生成，是目前我国精度最高的土地利用遥感监测数据产品之一。土地利用类型主要划分为农田、森林、草地、水域、居民用地和裸地6个一级类型。数据分辨率为$0 . 0 1 ^ { \circ }$ ,根据研究区域进行裁剪掩膜，作为模型地表覆盖类型输入数据。

归一化植被指数（Normalized difference vegeta-tionindex，NDVI)是反映植被生长状况的重要参数。本文选用1981—2015年GIMMS3g数据(https://ecocast.arc.nasa.gov/data/pub/gimms）和 1998—2018年中国科学院SPOT/VEGETATIONNDVI合成数据(http://www.resdc.cn）。数据预处理包括对原始数据进行格式转换、投影转换、数据拼接、裁切等，并将数据重采样为 $0 . 0 1 ^ { \circ }$ 分辨率的影像。为获得连续一致的 NDVI,使用最大值合成法计算NDVI年数据[24],用于区域蒸散及组分变化的归因分析。

站点验证数据采用研究区内多伦站和锡林浩特站的开路涡度相关系统观测的水汽通量数据。利用垂直风速脉动的平均协方差和水汽浓度标量的乘积计算 $3 0 ~ \mathrm { m i n }$ 平均潜热通量，利用EddyPro软件对数据进行处理计算，包括去除野点、二维坐标旋转订正等。将每日潜热通量除以汽化潜热( $\lambda \approx$ $2 . 4 5 ~ \mathrm { M J \cdot k g ^ { - 1 } }$ )计算得出日蒸散数据。对于缺失时间短（ $( < 2 \mathrm { h } )$ 的数据采用线性内插法进行插补，对于缺失时间较长的数据采用日平均法对其进行插补[25]，通量数据的能量平衡比率大于 $9 0 \%$ ，符合能量不闭合程度的要求，说明数据质量良好[26],通量数据的具体处理方法介绍详见Tian等的文章[27-28]

# 1.4敏感性分析

本文采用由McCuen提出的敏感性系数，即因变量与单个自变量要素相对变化量之比，反映各自变量要素对因变量变化的贡献情况，具体计算方法见毕彦杰等[29]的研究。结合敏感性系数及自变量本身变化情况，综合解析和量化要素对因变量的作用。本文主要选择平均气温(TEMP）、降水量(PRE）、饱和水汽压差(VPD）、太阳总辐射(RAD）和NDVI5个要素分析其变化对蒸发、蒸腾和蒸散变化

的贡献。

# 2结果与分析

# 2.1 模型验证

图2给出了BEPS模型模拟的研究区多伦站和锡林浩特站2006—2008年月蒸散与相应实测值对比结果。BEPS模型月ET模拟值与2站点月实测值差距较小，RMSE分别为 $9 . 6 2 ~ \mathrm { m m }$ 和 $1 0 . 1 4 ~ \mathrm { m m }$ （图$2 \mathrm { a } { \sim } \mathrm { b }$ )。BEPS模型可以解释2站 $8 5 \%$ 的蒸散变化

![](images/2c41f212c72f81a388e6de108d1f3d1976ed5d91fad7152f78eb04c3a23e51ef.jpg)  
图22006—2008年月蒸散模拟值和实测值变化及对比 Fig.2 Changes and comparison of simulated and measured values of monthly evapotranspiration from 2oo6 to 2008

注：ET为蒸散。下同。

# 干旱区地理

Tab.1 Comparisons of simulated values from BEPS model and measured data   

<html><body><table><tr><td colspan="2">纬度/N经度/E</td><td>年份</td><td>ET实测值/mm</td><td>ET模拟值/mm</td><td>T实测值/mm</td><td>T模拟值/mm</td><td></td><td>T/ET实测值 T/ET模拟值</td><td>参考文献</td></tr><tr><td>42.05</td><td>116.28</td><td>2006</td><td>433.53</td><td>423.60</td><td></td><td>1</td><td></td><td>一</td><td>[30]</td></tr><tr><td>43.55</td><td>116.67</td><td>2006</td><td>281.57</td><td>317.76</td><td>1</td><td>1</td><td>1</td><td>一</td><td>[30]</td></tr><tr><td>44.13</td><td>116.33</td><td>2004</td><td>323.14</td><td>294.12</td><td>1</td><td>1</td><td>1</td><td>一</td><td>[31]</td></tr><tr><td rowspan="3">43.53</td><td></td><td>2006</td><td>318.04</td><td>297.60</td><td>1</td><td>1</td><td></td><td>1</td><td>[31]</td></tr><tr><td>116.67</td><td>2006</td><td>307.70</td><td>316.92</td><td>1</td><td>1</td><td>1</td><td>1</td><td>[32]</td></tr><tr><td></td><td>2011</td><td>415.12</td><td>389.25</td><td>1</td><td>一</td><td>1</td><td>一</td><td>[32]</td></tr><tr><td rowspan="2">43.63</td><td>116.71</td><td>2004</td><td>1</td><td>一</td><td>155.25</td><td>158.64</td><td></td><td>一</td><td>[33]</td></tr><tr><td></td><td>2006</td><td>1</td><td>一</td><td>95.70</td><td>99.80</td><td>1</td><td>一</td><td>[33]</td></tr><tr><td>43.60</td><td>116.70</td><td>2003—2005</td><td>1</td><td>一</td><td>一</td><td></td><td>0.44</td><td>0.45</td><td>[34]</td></tr><tr><td>43.50</td><td>116.70</td><td>2003(5-9月）</td><td></td><td>二</td><td>二</td><td>1 二</td><td>0.62</td><td>0.63</td><td>[35]</td></tr></table></body></html>

注：ET为蒸散;T为蒸腾;T/ET为蒸腾和蒸散的比值。下同。

（图2c)。通过与他人文献结果对比(表1)，BEPS模型模拟 $T$ 时平均相对误差为 $3 . 2 0 \%$ ,模拟ET时平均相对误差为 $6 . 7 0 \%$ ,模拟T/ET时平均相对误差为$1 . 9 0 \%$ ,这表明BEPS模型在站点尺度模拟准确性较好[30-35]。将T、ET和T/ET空间分布情况与Niu等[32]发布的1981—2015年中国陆地生态系统蒸腾蒸散比数据集结果相对比，三者空间分布情况高度一致。综上，BEPS模型估算结果合理，可以用于研究区 $E , T$ 和ET的模拟计算。

# 2.2蒸散及其组分的时空特征

根据地表利用类型数据，提取草地、农田和森林像元，并统计不同地表利用类型下 $E , T$ 和ET。表2给出了研究区域1981—2018年不同地表类型年平均耗水量和产水量(PRE-ET)的总体情况。草地的$E , T$ 和ET耗水量分别为 $1 7 0 . 2 0 \ \mathrm { m m } \cdot 1 0 8 . 0 2 \ \mathrm { m m }$ 和$2 7 8 . 2 2 \mathrm { m m }$ 。农田的 $E , T$ 和ET耗水量分别为149.73$\mathrm { m m } , 2 1 2 . 7 7 \ \mathrm { m m }$ 和 $3 6 2 . 5 0 ~ \mathrm { m m }$ 。森林的 $E , T$ 和ET耗水量分别为 $1 1 9 . 1 7 \ \mathrm { m m } , 1 8 9 . 6 4 \ \mathrm { m m }$ 和 $3 0 8 . 8 1 ~ \mathrm { { m m } }$ 。结果表明,农田总耗水量最大，森林次之，草地最小。结合降水量看，森林PRE-ET最大，为53.52$\mathbf { m } \mathbf { m }$ ;草地次之，为 $3 1 . 3 2 ~ \mathrm { m m }$ ;农田PRE-ET为负值，

# 表21981—2018年研究区不同地表类型年平均耗水量

表1BEPS模型模拟值与实测值数据对比  
Tab.2 Average annual water consumption of different surface types in the study area from 1981 to 2018 $/ \mathrm { m m }$   

<html><body><table><tr><td>地表类型</td><td>PRE</td><td>E</td><td>T</td><td>ET</td><td>PRE-ET</td></tr><tr><td>草地</td><td>309.54</td><td>170.20</td><td>108.02</td><td>278.22</td><td>31.32</td></tr><tr><td>农田</td><td>350.07</td><td>149.73</td><td>212.77</td><td>362.50</td><td>-12.43</td></tr><tr><td>森林</td><td>362.33</td><td>119.17</td><td>189.64</td><td>308.81</td><td>53.52</td></tr></table></body></html>

注：PRE为降水量； $E$ 为蒸发；PRE-ET为产水量。

为 $- 1 2 . 4 3 ~ \mathrm { m m }$ 。

图3为1981—2018年研究区 $E , T$ 和ET的年际变化。结果表明研究区 $E , T$ 和ET多年平均值分别为 $1 6 7 . 1 3 ~ \mathrm { m m } , 1 1 9 . 1 6 ~ \mathrm { m m }$ 和 $2 8 6 . 3 5 \ : \mathrm { m m }$ ,三者均呈显著上升趋势 $( P { < } 0 . 0 5 )$ ,上升速率分别为 $0 . 4 2 \ \mathrm { m m ^ { \cdot } a ^ { - 1 } }$ 、$0 . 6 3 ~ \mathrm { m m ^ { \cdot } a ^ { - 1 } }$ 和 $1 . 0 5 ~ \mathrm { { m m } \cdot \mathrm { { a } ^ { - 1 } } }$ 。与 $T$ 相比, $E$ 年际变化较平稳，波动幅度更小，因此ET年尺度波动主要受到 $T$ 影响，变化情况与 $T$ 更一致。T/ET多年平均值为 $4 1 . 5 3 \%$ ,38a共上升 $3 . 8 0 \%$ ，表明蒸腾在蒸散中的比例呈增加趋势。

图4为研究区1981—2018年多年年均 $E , T$ ET和T/ET的空间分布。 $E$ 多年平均空间分布整体呈西北向东南递减趋势，在西北部植被稀疏区 $E$ 较高，可达 $1 6 0 ~ \mathrm { m m }$ ，但在东北部地区 $E$ 较低，小于140$\mathbf { m } \mathbf { m }$ 。 $T$ 空间分布和 $E$ 相反，在西北部草地稀疏区 $T$ 较低，东北部和东南部森林、农田覆盖区较高。在西北部地区， $T$ 小于 $8 0 ~ \mathrm { m m }$ ，在东北部至南部的森林农田覆盖区， $T$ 大于 $1 2 0 ~ \mathrm { m m }$ 。ET和T/ET空间分布与 $T$ 相似，草地覆盖区ET多小于 $2 7 5 ~ \mathrm { m m }$ ,南部和东北部农田和森林覆盖区域ET且大于 $3 0 0 \mathrm { m m }$ 。T/ET在西北部植被覆盖度较低区小于0.40，南部农田覆盖区和东北部森林覆盖区大于 $0 . 5 0$ 。

![](images/cb6bfe0839616265c70d5b63445ed765d9374853041127f86dc99de034db9e45.jpg)  
注：E为蒸发；T为蒸腾;T/ET为蒸腾和蒸散的比值。下同。 图31981—2018年研究区蒸发、蒸腾、蒸散、蒸腾和 蒸散比的变化趋势   
Fig.3Trends of evaporation,transpiration, evapotranspiration and transpiration/evapotranspiration in the study area from 1981 to 2018

![](images/bee3e317218085249c7bf31ffd54ab5ac0f2bf0df53aac732c9a1bb2f58adb5a.jpg)  
图41981—2018年研究区蒸发、蒸腾、蒸散、蒸腾和蒸散比的空间分布 Fig.4Spatial distributions of evaporation, transpiration,evapotranspiration and transpiration/evapotranspiration in the study area from 1981 to 2018

图5为1981—2018年研究区 $E , T , { \mathrm { E T } }$ 和T/ET的变化趋势空间分布。 $E$ 在全区域多呈增大趋势，特别在东北部森林和中南部农田区呈增大速率且大于 $0 . 5 0 \mathrm { m m } \cdot \mathrm { a } ^ { - 1 }$ ，在西北部和南部部分地区呈减小趋势，但减小趋势不显著。在农田覆盖的中南部和南部地区， $T$ 增大趋势显著( $( P { < } 0 . 0 5 )$ ,增大速率大于$1 . 0 0 \ \mathrm { m m ^ { \cdot } a ^ { - 1 } }$ ,但在东北部森林覆盖区， $T$ 呈减小趋势,减小速率最快为 $- 0 . 7 8 ~ \mathrm { m m } \cdot \mathrm { a } ^ { - 1 }$ 。综合 $E$ 和 $T$ 变化，ET在全区域多呈增大趋势，特别在北部草地覆盖区和南部农田覆盖区增大趋势较显著（ $_ { ( P < 0 . 0 5 ) }$ ，增大速率大于 $1 . 5 0 \mathrm { m m ^ { . } a ^ { - 1 } }$ ;ET仅在西北部和东北部部分地区呈减小趋势，但不显著。T/ET空间变化趋势和 $T$ 相似，从整体上看西部地区多呈上升趋势，但在东北部森林覆盖区域T/ET呈下降趋势，减小速率最快为 $- 0 . 0 0 2 \cdot \mathrm { a } ^ { - 1 }$ 。

# 2.3蒸散及其组分的归因分析

表3为1981—2018年研究区主要影响因子变化情况。NDVI区域平均值为0.22,表现为增加趋势，变化率为 $0 . 0 0 0 1 \cdot \mathrm { a } ^ { - 1 }$ ,草地呈增大趋势,农田和森林均呈减小趋势,其中森林减小趋势最大,为 $- 0 . 0 0 0 4 \cdot \mathrm { a } ^ { - 1 }$ 。TEMP在全区域平均为 $3 . 1 2 ^ { \circ } \mathrm { C }$ ,呈增大趋势,变化率为 $0 . 0 5 ^ { \circ } \mathrm { C } \cdot \mathrm { a } ^ { - 1 } , 3 8$ a升高 $1 . 9 0 ^ { \circ } \mathrm { C }$ 。PRE在全区域多年年均为 $3 1 4 . 7 6 ~ \mathrm { m m }$ ,全区域内呈减小趋势,森林减小最快，变化率为 $- 1 . 0 0 \ \mathrm { m m } \cdot \mathrm { a } ^ { - 1 }$ ,38a下降了38.00$\mathrm { m m }$ 。VPD在全区域多年年均为 $0 . 3 7 \mathrm { k P a }$ ，全区域多呈增大趋势，平均变化率为 $0 . 0 0 2 \mathrm { \ k P a } \cdot \mathrm { a } ^ { - 1 } ,$ 38a上升$0 . 0 9 \mathrm { k P a }$ 。RAD全区域呈减小趋势，农田减小速率最快,变化率为 $- 0 . 1 7 \ \mathrm { W \cdot m ^ { - 2 } \cdot a ^ { - 1 } } , 3 8$ a下降 $6 . 4 6 \mathrm { \ : W \cdot m ^ { - 2 } }$ 。

![](images/d3975323c4a613808d9f031253cdc765678dd0df470ac778c21aaaf4ab1e84a5.jpg)  
图51981—2018年研究区蒸发、蒸腾、蒸散、蒸腾和蒸散比的变化趋势空间分布 Fig.5Spatial distributions of change rates for evaporation, transpiration,evapotranspiration and transpiration/evapotranspiration in the study area from 1981 to 2018

表31981—2018年研究区主要影响因子的变化率统计  
Tab.3Change statistics of main influencing factors of the study area from 1981 to 2018   

<html><body><table><tr><td>地表类型</td><td>NDVI/a-1</td><td>TEMP/C·a-1</td><td>PRE/mm•a−1</td><td>VPD/kPa·a-1</td><td>RAD/W·m2·a−1</td></tr><tr><td>全区域</td><td>0.0001</td><td>0.05</td><td>-0.88</td><td>0.002</td><td>-0.11</td></tr><tr><td>草地</td><td>0.0002</td><td>0.05</td><td>-0.92</td><td>0.002</td><td>-0.10</td></tr><tr><td>农田</td><td>-0.0003</td><td>0.05</td><td>-0.32</td><td>0.002</td><td>-0.17</td></tr><tr><td>森林</td><td>-0.0004</td><td>0.05</td><td>-1.00</td><td>0.002</td><td>-0.08</td></tr></table></body></html>

注：NDVI为归一化植被指数;TEMP为平均气温;VPD为饱和水汽压差;RAD为地表总辐射。下同

1981—2018年各要素变化对区域 $E$ 变化的贡献情况如表4所示。森林 $E$ 变化最大，相对变化率为 $1 5 . 9 0 \%$ ，考虑 $E$ 对各要素变化的敏感性系数及各要素相对变化率，VPD增大为森林 $E$ 增加的主要原因，VPD增大引起 $E$ 增大 $1 2 . 2 2 \%$ 。草地和农田 $E$ 相对变化率分别为 $9 . 3 8 \%$ 和 $1 0 . 9 0 \%$ 。与森林主导因子相似，草地和农田 $E$ 变化的主导因子也为VPD。综合全区域 $E$ 相对变化率为 $9 . 5 5 \%$ $E$ 的主导因子排序为VPD>PRE $>$ RAD $\mathrm { > }$ TEMP>NDVI。

1981—2018年各要素变化对区域T变化的贡献情况如表5所示。农田 $T$ 相对变化率最大，为$2 4 . 8 0 \%$ 。综合 $T$ 对各因子变化的敏感性和各因子相对变化，VPD和TEMP增大为农田 $T$ 增大的主要原因。森林 $T$ 变化主要受到VPD增大的正向影响和NDVI减小的负向影响，相对变化率为 $1 3 . 8 3 \%$ 。草地T相对变化率为 $1 9 . 3 4 \%$ ，主导因子和农田相似。综合全区域， $T$ 相对变化率为 $2 0 . 0 9 \%$ ,主导因子依次为VPD>TEMP>NDVI>RAD>PRE。

1981—2018年各要素变化对区域ET变化的贡献情况如表6所示。农田ET相对变化率最大，为

$1 9 . 1 0 \%$ 。各要素对农田ET相对贡献大小依次为VPD>TEMP>RAD>NDVI>PRE，VPD和TEMP增大为农田ET增大的主要原因。草地和森林相对变化率分别为 $1 3 . 2 5 \%$ 和 $1 4 . 6 4 \%$ ,各要素对草地和森林ET相对贡献依次为VPD>TEMP $\mathrm { > }$ NDVI>RAD>PRE。综合全区域ET相对变化率为 $1 3 . 9 3 \%$ ，主导因子排序为VPD>TEMP>RAD>PRE>NDVI。

# 3讨论

研究通过站点ET实测数据和前人模拟结果相对比验证发现， $T . { \mathrm { E T } }$ 和T/ET估算相对误差最小分别为 $2 . 1 0 \% . 2 . 3 0 \%$ 和 $1 . 6 0 \%$ 。Li等[36]研究结果表明,T/ET和LAI水平相关，当LAI较小时，T/ET稳定在 $0 . 3 3 { \scriptstyle \pm 0 . 5 0 }$ ,而在植被生长状况良好区域，T/ET大于0.40。本研究区西北部LAI数值较小，变化范围为 $1 . 3 0 { \sim } 2 . 0 0 ~ \mathrm { m } ^ { 2 } { \cdot } \mathrm { m } ^ { - 2 }$ ，全区域年均T/ET为0.38，而东

Tab.4 Contribution analysis of influencing regulators to evaporation dynamics in the study area from 1981 to :   

<html><body><table><tr><td rowspan="2">地表类型</td><td colspan="5">相对贡献/%</td><td rowspan="2">E相对变化率/%</td><td rowspan="2">R</td><td rowspan="2">主导因子排序</td></tr><tr><td>NDVI</td><td>TEMP</td><td>PRE</td><td>VPD</td><td>RAD</td></tr><tr><td>全区域</td><td>-0.08</td><td>1.11</td><td>1.94</td><td>7.32</td><td>-1.32</td><td>9.55</td><td>0.94</td><td>VPD>PRE>RAD>TEMP>NDVI</td></tr><tr><td>草地</td><td>-0.17</td><td>1.09</td><td>1.50</td><td>7.38</td><td>-0.72</td><td>9.38</td><td>0.96</td><td>VPD>PRE>TEMP>RAD>NDVI</td></tr><tr><td>农田</td><td>1.45</td><td>1.11</td><td>1.02</td><td>8.54</td><td>-1.84</td><td>10.90</td><td>0.94</td><td>VPD>RAD>NDVI>TEMP>PRE</td></tr><tr><td>森林</td><td>1.46</td><td>2.25</td><td>1.19</td><td>12.22</td><td>-2.46</td><td>15.90</td><td>0.92</td><td>VPD>RAD>TEMP>NDVI>PRE</td></tr></table></body></html>

注：5个自变量要素相对贡献之和等于因变量蒸发相对变化乘以 $R ^ { 2 } ; R ^ { 2 }$ 为整体拟合优度。下同。

表41981—2018年研究区影响因子对蒸发变化的贡献分析  
表61981—2018年研究区影响因子对蒸散变化的贡献分析  

<html><body><table><tr><td rowspan="2">地表类型</td><td colspan="5">相对贡献/%</td><td rowspan="2">T相对变化率/%</td><td rowspan="2">R</td><td rowspan="2">主导因子排序</td></tr><tr><td>NDVI</td><td>TEMP</td><td>PRE</td><td>VPD</td><td>RAD</td></tr><tr><td>全区域</td><td>3.42</td><td>5.41</td><td>-1.12</td><td>11.50</td><td>-2.37</td><td>20.09</td><td>0.84</td><td>VPD>TEMP>NDVI>RAD>PRE</td></tr><tr><td>草地</td><td>4.67</td><td>5.35</td><td>-1.63</td><td>10.13</td><td>-1.74</td><td>19.34</td><td>0.86</td><td>VPD>TEMP>NDVI>RAD>PRE</td></tr><tr><td>农田</td><td>-1.31</td><td>8.37</td><td>-1.12</td><td>16.49</td><td>-1.63</td><td>24.80</td><td>0.84</td><td>VPD>TEMP>RAD>NDVI>PRE</td></tr><tr><td>森林</td><td>-3.49</td><td>3.27</td><td>-0.63</td><td>13.04</td><td>-1.14</td><td>13.83</td><td>0.85</td><td>VPD>NDVI>TEMP>RAD>PRE</td></tr></table></body></html>

表51981—2018年研究区影响因子对蒸腾变化的贡献分析  
Cab.6Contribution analysis of influencingregulators to evapotranspiration dynamics in thestudyareafrom1981 to 20   

<html><body><table><tr><td rowspan="2">地表类型</td><td colspan="5">相对贡献/%</td><td rowspan="2">ET相对变化率/%</td><td rowspan="2">R</td><td rowspan="2">主导因子排序</td></tr><tr><td>NDVI</td><td>TEMP</td><td>PRE</td><td>VPD</td><td>RAD</td></tr><tr><td>全区域</td><td>0.79</td><td>4.96</td><td>-1.01</td><td>10.84</td><td>-2.84</td><td>13.93</td><td>0.91</td><td>VPD>TEMP>RAD>PRE>NDVI</td></tr><tr><td>草地</td><td>2.44</td><td>2.88</td><td>-0.33</td><td>8.65</td><td>-1.49</td><td>13.25</td><td>0.91</td><td>VPD>TEMP>NDVI>RAD>PRE</td></tr><tr><td>农田</td><td>-1.54</td><td>6.65</td><td>-0.65</td><td>15.34</td><td>-2.07</td><td>19.10</td><td>0.92</td><td>VPD>TEMP>RAD>NDVI>PRE</td></tr><tr><td>森林</td><td>-1.32</td><td>3.27</td><td>-0.63</td><td>13.04</td><td>-1.14</td><td>14.64</td><td>0.90</td><td>VPD>TEMP>NDVI>RAD>PRE</td></tr></table></body></html>

# 干吴区地理

部森林和南部农田覆盖区植被生长状况较好，T/ET则稳定在0.50左右，与Li等研究结果相符。1981—2018年BEPS模拟多年平均ET结果介于 $2 7 8 . 2 2 \sim$ $3 6 2 . 5 0 ~ \mathrm { m m }$ ;牛忠恩等[37]基于PT-JPL模型对中国ET分布情况进行估算，内蒙古地区多年平均ET介于$3 0 0 { \sim } 4 0 0 ~ \mathrm { m m }$ ;王思如等[12]基于WaVEM模型对内蒙古科尔沁地区ET变化进行研究，发现ET介于200\~$4 5 0 \mathrm { m m }$ ,以上均与本研究模拟结果相符。因此通过站点实测数据及研究结果的比对证明BEPS模型结果合理，可以较准确模拟研究区ET及其组分。

半干旱区不同的生态条件会影响蒸散对气候条件的响应[38]。根据对 $E , T$ 和ET空间分布结果,研究区西北部植被稀疏，年均NDVI小于0.15,但较高的气温及较大的VPD使得蒸发速率较快。研究区东部和南部森林和农田环境植被覆盖度较高，年均NDVI大于0.27，下垫面粗糙度更高，植被的蒸腾作用成为地表和大气间水分交换的主要方式，因此在东北部森林和南部农田覆盖区域T和T/ET均高于其他区域。根据Jiang等[39研究,半干旱区T是主导ET变化的主要驱动组分，结合图3和图 $^ { 4 , E }$ 的高值区主要分布在西北部植被稀疏区，年际间波动主要受到气候条件支配，而 $T$ 高值区主要分布在东北部森林和南部农田覆盖区，年际变化除受到气候条件影响外还受到植被生长状况以及人为因素（例如农田人工灌溉等)影响，因此 $E$ 年际波动较小，变化趋势较平稳，而ET和T年际波动变化一致性较高。

T/ET表征植被蒸腾对生态系统蒸散的贡献率，是准确量化生态系统水分利用效率的关键参数[40]TEMP、VPD和NDVI升高和地表植被生长会影响T/$\mathrm { E T } ^ { [ 4 1 ] }$ 。TEMP增大,有利于延长植被生长季;VPD作为大气水分亏缺状况的表征因子，主要通过影响裸地和植被表面的水分梯度，调节叶片气孔导度影响植被蒸腾量[42]。半干旱地区升温效应增大了水分梯度和叶片气孔导度，加速叶片和外界水汽交换，对T/ET起促进作用。NDVI增大表明研究区域植被长势逐渐增加，冠层截获的辐射增多，导致蒸腾耗水增加，同时长势良好的树木和作物水分利用效率更高[43],蒸腾作用随之增强。结合 $E$ 和 $T$ 归因分析结果，研究区草地NDVI多年呈增大趋势，对草地 $E$ 为负贡献，对T为正贡献，有利于增大草地生态系统蒸散中蒸腾的比例，提高了草地的水分利用效率。而森林和农田NDVI多年呈下降趋势，特别在森林覆盖区NDVI下降速率最快，因此农田和森林部分区域T/ET呈减小趋势， $E$ 在ET中的占比逐渐增加。

根据前人研究，ET和气候条件、地表覆盖类型有密切关系[44]。如表2,研究区域单位面积草地 $E$ 大于农田和森林，但T小于农田和森林,这主要由于草地植被叶面积较小，地表土壤裸露较多，到达地表的光照辐射能量使得地表蒸发旺盛，而森林和农田植被叶片面积较大，更高的冠层高度和植被层厚度有利于吸收更多光照辐射能量，导致下渗到土壤表层的水分不易蒸发，进而被植被发达的根系吸收，为蒸腾作用提供更多水分来源。另一方面，农田多分布在研究区域南部，平均年PRE为350.07$\mathbf { m } \mathbf { m }$ ，但PRE-ET仅为 $- 1 2 . 4 3 ~ \mathrm { m m }$ ，说明农牧资源的不合理分配，可能导致未来半干旱区域更容易发生土壤干旱，进而造成该区域水土流失及土壤退化等环境问题。

# 4结论

本文以位于内蒙古半干旱区的锡林郭勒盟和乌兰察布市为例，结合遥感、气象资料和站点观测资料等，采用BEPS模型，分析和量化以农田、草地和森林为主的半干旱区 $E , T$ 和ET的时空变化，揭示半十旱草地生态系统 $E , T$ 和ET对气候变化的响应特征及主控因子，得出主要结论如下：

经过站点实测数据对比，BEPS模型计算结果能够精确反应研究区ET及其组分的分布情况和变化趋势。研究区域草地、农田和森林年均ET分别为$2 7 8 . 2 2 \ \mathrm { m m } \cdot 3 6 2 . 5 0 \ \mathrm { m m }$ 和 $3 0 8 . 8 1 ~ \mathrm { { m m } }$ 。 $E , T$ 和ET多年呈显著上升趋势，上升速率分别为 $0 . 4 2 ~ \mathrm { { m m } \cdot \mathrm { { a } ^ { - 1 } } }$ 、$0 . 6 3 ~ \mathrm { m m ^ { \bullet } a ^ { - 1 } }$ 和 $1 . 0 5 ~ \mathrm { m m } \cdot \mathrm { a } ^ { - 1 }$ ,1981—2018年共上升$1 5 . 9 6 ~ \mathrm { m m } \cdot 2 3 . 9 4 ~ \mathrm { m m }$ 和 $3 9 . 9 \ \mathrm { m m }$ 。ET与 $T$ 在全区域内空间分布格局相似，与 $E$ 相反，ET年际波动主要受到 $T$ 年际波动的影响。综合影响因子的变化和$\boldsymbol { E } , \boldsymbol { T } , \mathrm { E T }$ 对因子的敏感性，研究区域草地和农田 $T$ 和ET以及森林的ET主要受到VPD和TEMP变化的控制。农田和森林NDVI都呈减小趋势，但森林 $T$ 对NDVI变化更加敏感，因此负贡献更大。

#

参考文献(References)   
[1]Thornthwaite C W.An approach toward a rational classification of climate[J]. Geographical Review,1948,38(1): 55-94.   
[2]Burba G G,Verma S B. Seasonal and interannual variability in evapotranspiration of native talgrass prairie and cultivated wheat ecosystems[J]. Agricultural and Forest Meteorology,2OO5,135(1- 4): 190-201.   
[3]Li Z,Liu X,NiuT,etal.Ecologicalrestorationand its efectsona regional climate: The source region of the Yellow River,China[J]. Environmental Science and Technology,2015,49(10): 5897-5904.   
[4]宁亚洲,张福平,冯起,等.基于 SEBAL模型的疏勒河流域蒸散 发估算与灌溉效率评价[J].干旱区地理,2020,43(4):928-938. [Ning Yazhou, Zhang Fuping,Feng Qi, et al. Estimation of evapotranspiration in Shule River Basin based on SEBAL model and evaluation on irrigation efficiency[J]. Arid Land Geography,2020, 43(4): 928-938.]   
[5]黄建平,季明霞,刘玉芝,等.干旱半干旱区气候变化研究综述 [J].气候变化研究进展,2013,9(1):9-14.[Huang Jianping,Ji Mingxia,Liu Yuzhi,et al.An overview of aridand semi-arid climate change[J]. Climate Change Research,2013, 9(1): 9-14.]   
[6]李鹏飞,孙小明,赵昕奕.近50年中国干旱半干旱地区降水量 与潜在蒸散量分析[J].干旱区资源与环境,2012,26(7):57-63. [Li Pengfei, Sun Xiaoming, Zhao Xinyi. Analysis of precipitation and potential evapotranspiration in arid and semi-arid area of China in recent 5O years[J]. Journal of Arid Land Resources and Environment,2012,26(7): 57-63.]   
[7]吴国栋,薛河儒,刘廷玺.1961—2016年锡林河流域降水及平 均气温变化特征及趋势[J].干旱区地理,2021,44(3):769-777. [Wu Guodong,Xue Heru, Liu Tingxi. Change characteristics and trends of precipitation and average temperature in the Xilinhe River Basin from 1961 to 2016[J].Arid Land Geography,2021,44(3): 769-777.]   
[8]Zhang K, John S, Kimball, et al.A review of remote sensing based actual evapotranspiration estimation[J].Wiley Interdisciplinary Reviews: Water,2016,3(6): 834-853.   
[9]代鹏超,牛苏娟,毋兆鹏,等.新疆精河流域实际蒸散发时空变 化特征[J].生态与农村环境学报,2017,33(7):600-606.[Dai Pengchao, Niu Sujuan,Wu Zhaopeng,et al. Temporal and spatial characteristics of actual evapotranspiration in Jinghe Watershed, Xinjiang[J].Journal of Ecologyand Rural Environment,2017,33 (7): 600-606.]   
[10] 金学杰,周剑.基于 SEBS 模型和Landsat 8数据的黑河下游蒸 散发时空特性分析[J].冰川冻土,2017,39(3):572-582.[Jin Xuejie,Zhou Jian.Analysis of spatial-temporal characteristics of evapotranspiration in the lower reaches of Heihe River based on surface energy balance system model and Landsat 8data[J]. Journalof GlaciologyandGeocryoogy,2017,39(3):57-52.   
[11] 蹇东南,李修仓,陶辉,等.基于互补相关理论的塔里木河流域 实际蒸散发时空变化及影响因素分析[J].冰川冻土,2016,38 (3): 750-760.[Jian Dongnan,Li Xiucang,Tao Hui,et al. Spatiotemporal variation of actual evapotranspiration and its influence factors in the Tarim River Basin based on the complementary relationshipapproach[J].Journalof Glaciologyand Geocryology, 2016,38(3): 750-760.]   
[12]王思如,雷慧闽,段利民,等.气候变化对科尔沁沙地蒸散发和 植被的影响[J].水利学报,2017,48(5):535-544.[Wang Siru, Lei Huimin,Duan Limin,et al. Simulated impacts of climate change on evapotranspiration and vegetation in Horqin Sandy Land [J]. Journal of Hydraulic Engineering,2017,48(5): 535-544.]   
[13] 赵水霞,王文君,吴英杰,等.近59a锡林郭勒草原旱灾驱动气 候因子分析[J].干旱区研究,2021,38(3):785-793.[Zhao Shuixia,Wang Wenjun,Wu Yingjie,et al.Analysis of drought-driving climatic factors of Xilin Gol grassland in the past 59 years[J].Arid Zone Research,2021,38(3): 785-793.]   
[14] 韩典辰,张方敏,陈吉泉,等.半干旱区草地站蒸散特征及其对 气象因子和植被的响应[J].草地学报,2021,29(1):166-173. [Han Dianchen, Zhang Fangmin, Chen Jiquan,et al. Charcteristics of grassland evapotranspiration in semi-arid area and its responses to meteorological factors and vegetation[J].Acta Agrestia Sinica, 2021, 29(1): 166-173.]   
[15]Liu J,Chen JM, Cihlar J,etal.A process-based Boreal ecosystem productivity simulator using remote sensing inputs[J]. Remote Sensing of Environment,1997,62: 158-175.   
[16]Chen JM,Liu J, Cihlar J,et al. Daily canopy photosynthesis model through temporal and spatial scaling for remote sensing applications[J]. Ecological Modeling,1999,124: 99-119.   
[17]Zhang FM,Ju W M, Shen SH,et al. Variations of terrestrial net primary productivity in East Asia[J]. Terrestrial Atmospheric and Oceanic Sciences,2012,23(4): 425-437.   
[18] 张方敏,居为民,陈镜明,等.基于BEPS生态模型对亚洲东部 地区蒸散量的模拟[J].自然资源学报,2010,25(9):1596-1606. [Zhang Fangmin,Ju Weimin,Chen Jingming,et al. Study on evapotranspiration in East Asia using the BEPS ecological model [J]. JournalofaturalResources,1,25(9):596-166.]   
[19] Zhang F M,Ju W M,Shen S H,et al.How recent climate change influences water use eficiency in East Asia[J]. Theoretical and Applied Climatology,2014,116(1): 359-370.   
[20]Chen JM, Chen XY,Ju W M,et al. Distributed hydrological model for mapping evapotranspiration using remote sensing inputs[J]. Journal of Hydrology,2005,305:15-39.   
[21]Liu J, Chen JM, Cihlar J. Mapping evapotranspiration based on remote sensing: An application to Canada's landmass[J].Water Resources Research,2003,39:1189-1200.   
[22] 肇毓锋,吴奇.多时间尺度下Kriging与IDW空间插值方法的适 用性研究[J].黑龙江水利科技,2020,48(11):9-14.[Zhao Yufeng, WuQi.Applicability of Krigingand IDW spatial interpolation

# 干吴区地理

methods on multiple time scales[J].Heilongjiang Hydraulic Science and Technology,2020,48(11): 9-14.]   
[23]Liu Y, Liu R G, Chen JM.Retrospective retrieval of long- term consistent global leaf area index(1981—2011） from combined AVHRR and MODIS data[J]. Journal of Geophysical Research, 2012,117: G04003,doi: 10.1029/2012JG002084.   
[24]Brent N H. Characteristics of maximum-value composite images from temporal AVHRR data[J]. International Journal of Remote Sensing,1986,7(11): 1417-1434.   
[25]Falge E,Baldocchi D,Olson R,et al. Gap filling strategies for defensible annual sums of net ecosystem exchange[J]. Agricultural and Forest Meteorology,2001,107(1): 43-69.   
[26] 翁升恒,张方敏,冯妍,等.江淮流域稻麦轮作蒸散特征及其影 响因子[J].节水灌溉,2020(8): 27-33.[Weng Shengheng, Zhang Fangmin,Feng Yan,et al.Characteristics of evapotranspiration and its influencing factors in rice-wheat rotation in the Jianghuai River Basin[J]. Water Saving Irrigation,2020(8): 27-33.]   
[27]Miao H, Chen S,Chen J,et al. Cultivation and grazing altered evapotranspiration and dynamics in Inner Mongolia steppes[J]. Agricultural andForest Meteorology,2009,149(11): 1810-1819.   
[28] Tian D,Niu S,Pan Q,et al. Nonlinear responses of ecosystem carbon fluxes and water-use eficiency to nitrogen addition in Inner Mongolia grassland[J]. Functional Ecology，2016,30(3):490- 499.   
[29] 毕彦杰,赵晶,赵勇,等.京津冀地区潜在蒸散量时空演变特征 及归因分析[J].农业工程学报,2020,36(5):130-140.[Bi Yanjie,Zhao Jing, Zhao Yong,et al. Spatial-temporal variation characteristicsand atribution analysis of potential evapotranspiration in Beijing-Tianjin-Hebei region[J]. Transactions of the Chinese Society of Agricultural Engineering,2020,36(5): 130-140.]   
[30] Chen S,Chen J,Lin G,et al.Energy balance and partition in Inner Mongolia steppe ecosystems with different land use types[J]. Agricultural and Forest Meteorology,2009,149(11): 1800-1809.   
[31] Zheng Han,Yu Guirui,Wang Qiufeng,et al. Spatial variation in annual actual evapotranspiration of terrestrial ecosystems in China: Results from eddy covariance measurements[J]. Journal of Geographical Sciences,2016(10): 1391-1411.   
[32] Niu Z, He H, Zhu G,et al. A spatial-temporal continuous dataset of the transpiration to evapotranspiration ratio in China from 1981——2015[J]. Scientific Data,2020,7(1):369,doi:10.1038/ s41597-020-00693-x.   
[33] Chen Y,Lee G,Lee P,et al.Model analysis of grazing effct on above-ground biomass and above-ground net primary production of a Mongolian grassland ecosystem[J].Journal of Hydrology,2007, 333(1): 155-164.   
[34]Hu Z,Yu G, Zhou Y,et al. Partitioning of evapotranspiration and its controls in four grassland ecosystems: Application of a twosource model[J].Agricultural & Forest Meteorology,20o9,149(9): 1410-1420.   
[35]Huang X,Hao Y,Wang Y,et al.Partitioning of evapotranspiration and its relation to carbon dioxide fluxes in Inner Mongolia steppe [J]. Journalof Arid Environments,2010,74(12): 1616-1623.   
[36]Li X,Lin C J,Sun Z,et al.A simple and objective method to partition evapotranspiration into transpiration and evaporation at eddycovariance sites[J].Agricultural and Forest Meteorology，2019, 265: 171-182.   
[37] 牛忠恩,胡克梅,何洪林,等.2000—2015年中国陆地生态系统 蒸散时空变化及其影响因素[J].生态学报,2019,39(13):4697- 4709.[Niu Zhong'en,Hu Kemei,He Honglin,et al. The spatialtemporal patterns of evapotranspiration and its influencing factors in Chinese terrestrial ecosystem from 2000 to 2015[J].Acta Ecologica Sinica,2019,39(13): 4697-4709.]   
[38]Liu S,Li SG,Yu G R,et al. Seasonal and interannual variations in water vapor exchange and surface water balance over a grazed steppe in central Mongolia[J]. Agricultural Water Management, 2010,97(6): 857-864.   
[39]Jiang Z, Yang Z, Zhang S,et al.Revealing the spatio-tempralvariability of evapotranspiration and its components based on an improved Shutleworth- Wallace model in the Yellow River Basin[J]. Journal of Environmental Management,2020,262:110310,doi: 10.1016/j.jenvman.2020.110310.   
[40] Xiao L R,Lu Q Q,He HL,etal.Estimation and analysis of the ratio of transpiration to evapotranspiration in forest ecosystems along the north-south transect of east China[J]. Journal of Geographical Sciences,2019,29(11): 1807-1822.   
[41] Zhao J, Liang W, Yang Y T, et al. Separating vegetation greening and climate change controls on evapotranspiration trend over the Loess Plateau[J]. Scientific Reports,2017,7(1): 951-954.   
[42] 赵晓涵,张方敏,韩典辰,等.内蒙古半干旱区蒸散特征及归因 分析[J].干旱区研究,2021,38(6):1614-1623.[Zhao Xiaohan, Zhang Fangmin, Han Dianchen, et al. Evapotranspiration changes and its atribution in semi-arid regions of Inner Mongolia[J].Arid Zone Research,2021,38(6): 1614-1623.]   
[43]Naama R Y,Dan Y,Gabriel S,et al. Dynamics of evapotranspiration partitioning in a semi-arid forest as afcted by temporal rainfall patterns[J].Agricultural and Forest Meteorology,2012,157: 77-85.   
[44]Gokmen M, Vekerdy Z, Verhoef W,et al. Satelite-based analysis of recent trends in the ecohydrology of a semi-arid region[J].Hydrology and Earth System Sciences,2013,17(10): 3779-3794.

# Evapotranspiration of a semi-arid landscape in Inner Mongolia: Estimation and attribution

HAN Dianchen'， ZHANG Fangmin'， CHEN Jiquan²， LI Yunpeng',LU Qi4§， LU Yanyu6

(1.JiangsuKeyLaboratoryofgiculturalMeteorologyColgeofAppliedeteorologyNanjingUnversityofIformatioience   
&Technology,Nanjing44,Jangsu,China;2.DpartmentofGeography,EnvronmentandpatialScienceandCetefor Global ChangeandEarthObservation,MichiganStateUniversity,EastLansingM48825,Michigan,USA；3.Ecologicalan Agricultural Meteorological Centerof Inner Mongolia Autonomous Region,Hohhot Olo51,Inner Mongolia,China; 4.DesertificationResearch Institute,Chinese AcademyoforestrySciences,BeijingOO91,China;5.DesertForestry Experimental Center,ChineseAcademyofForestry Sciences,BeijingO91,China;6.Auhui Instituteof Meteorological Sciences,Auhuirovince KeyLaboratoryofAtmospheric ScienceandSateliteRemoteSensing,Hefei3031,Anhui,China)

Abstract: Evapotranspiration (ET) is the most important flux term in the ecosystem water budget because it is related to water and heat exchange between ecosystems and the atmosphere. Quantifying the magnitude and dynamics of ET and its components include evaporation $( E )$ and transpiration $( T )$ at regional scales and deriving a mechanistic understanding of the underline regulations is esential for managing water resources under the changing climate.On the basis of a mechanistic ecosystem model (BEPS),we estimated the magnitudes of ET and its components in the semi-arid region ( $( 4 0 . 1 6 ^ { \circ } - 4 6 . 7 7 ^ { \circ } \mathrm { N }$ and $1 1 0 . 3 3 ^ { \circ } - 1 1 9 . 9 1 ^ { \circ } \mathrm { E } )$ of Inner Mongolia, China from 1981 to 2018.Compared with diferent data, the BEPS could provide accurate estimates for changes in ET andits components by validating with ground measurements.The total average annual ETof grassland,cropland, and forests in the study area from 1981 to 2018 was $2 7 8 . 2 2 \mathrm { m m }$ ， $3 6 2 . 5 0 ~ \mathrm { m m }$ ,and $3 0 8 . 8 1 \ \mathrm { m m }$ , respectively. Over the study period, $E , T ,$ and ET increased at a rate of $0 . 4 2 ~ \mathrm { m m ^ { \cdot } a ^ { - 1 } }$ ， $0 . 6 3 ~ \mathrm { m m ^ { . } a ^ { - 1 } }$ ,and $1 . 0 5 ~ \mathrm { m m ^ { . } a ^ { - 1 } }$ ,respectively. Across the study region, we found that the spatial distribution patterns of $T$ was opposite to that of $E$ and similar to thatof ET.From the interannual variation standpoint,the interannual fluctuations in ET were primarily influencedby those inT.Considering thechanges in influencing factors and the sensitivities of the thre fluxes, we concluded that $T$ and ET of the grasslands and croplands and ET of forests were mainly controled by vapor presure deficit and air temperature. Although both cropland and forest normalized diference vegetation index (NDVI) showed decreasing trends, forest environmental $T$ was more sensitive to changes in NDVI, thus receiving more negative influence than cropland.

Key words: evapotranspiration； evaporation; transpiration； BEPS model; semi-arid area