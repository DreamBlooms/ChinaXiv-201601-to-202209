# 基于Cubist模型的天山北坡草地鼠群密度时空分布特征

潘群12，施海洋2.3，张文强2.3，罗格平2.3.4，陈春波2.3(1.新疆大学资源与环境科学学院,新疆乌鲁木齐830046；2.中国科学院新疆生态与地理研究所荒漠与绿洲生态国家重点实验室,新疆 乌鲁木齐830011；3.中国科学院大学,北京100049；4.中国科学院中亚生态与环境研究中心，新疆 乌鲁木齐 830011)

摘要：鼠害是影响草原生态健康的重要因素，了解小型啮齿动物种群密度时空分布特征,对精准的鼠害综合防治具有重要意义。以往对小型啮齿动物时空分布的研究多局限于静态的站点分布或小范围的种群密度时间变化分析，缺乏对较大时空尺度小型啮齿动物种群密度变化的分析。从已发表的文献中收集了天山北坡草地1982—2015年小尺度的有效洞口密度实地调查信息，同时结合环境因子数据，再根据海拔将研究区划分为 $\leqslant 9 0 0 \mathrm { ~ m ~ }$ 和 ${ > } 9 0 0 \mathrm { ~ m ~ } 2 \$ 类，运用Cubist模型和随机森林模型，分析有效洞口密度时空分布。结果表明：(1)1982—2015年天山北坡海拔 $\leqslant 9 0 0 \mathrm { ~ m ~ }$ 地区的有效洞口密度总体呈增加趋势，而海拔 ${ > } 9 0 0 \ \mathrm { m }$ 的地区总体呈减少趋势。基于Cubist模型构建有效洞口密度与环境因子的模型拟合精度明显优于随机森林模型。(2)植被状况、气象因子和放牧强度是天山北坡有效洞口密度时空分布主要的环境驱动因素。在天山北坡内海拔 $\leqslant 9 0 0 \mathrm { ~ m ~ }$ 和 ${ > } 9 0 0 \mathrm { ~ m ~ }$ 的地区中，有效洞口密度的驱动机制存在着显著差异。(3)在海拔 $\leqslant 9 0 0 \mathrm { ~ m ~ }$ 地区，影响有效洞口密度时空分布主要是叶面积指数，而对于海拔 ${ > } 9 0 0 \mathrm { ~ m ~ }$ 地区为归一化植被指数。这可能是受到大沙鼠(Rhom-bomys opimus)和黄兔尾鼠(Eolagurusluteus)消耗不同类型植被的影响。

关键词：有效洞口密度；环境因子；Cubist模型；随机森林模型；天山北坡

# 文章编号：

啮齿动物是草地哺乳动物中种类和数量最多的一类动物，就物质循环和能量流动而言，其在草地生态系统中具有重要的功能和地位[]。然而，其种群数量过高可能会对草地造成危害即草原鼠害，其危害主要表现在啃食和储藏大量牧草、挖土造丘，导致草地裸露,严重破坏植被空间结构，降低草原生产力和草地牧草产量[2-3],打破原有"土-草-畜-鼠"的动态平衡,致使草地退化严重[4]。

新疆具有丰富的草地资源，然而近年来，由于过度放牧、草地资源开发不当、全球气候异常等，导致新疆草地鼠害持续大面积发生，已对畜牧业的可持续发展和草原生物多样性产生了不利影响。为了更及时地防治鼠害，需要加深对啮齿动物种群密度时空分布驱动机制的理解并更准确地预测其时空分布。目前，虽然已有较多对于啮齿动物空间分布格局的研究，但大多集中于研究小尺度的种群数量随时间的变化5或研究其潜在空间分布，却很少涉及大尺度的种群密度时空分布的变化特征及其机制。如乔雪丽等利用最大熵模型(MaxEnt)对在不同环境条件下的大沙鼠在亚洲的潜在地理分布进行预测；何咏琪等基于“3S"技术与地面实地调查数据，建立了草原鼠害监测模型并模拟出了青海省草原鼠害分布区；Mohammadi等"模拟了伊朗气候变化下两种沙漠跳鼠的当前和未来潜在分布。

目前，环境因子已被广泛用于物种种群密度分布的驱动机制分析和时空分布预测[9-10]。对啮齿动物而言，环境条件在其种群密度波动和空间分布中扮演着重要角色，可通过直接或其相互作用对其产生重要影响[11]。啮齿动物种群密度的时空分布受地形[12]、土壤质地[13]、气温[5]、降水[14]、植被[15-16]放牧[17]等的影响，且其具有年际和季节性变化的特征[18]。因此，通过建立啮齿动物种群密度与环境因子的关系来预测其种群密度的时空分布具有一定可行性。在衡量害鼠种群密度的指标中，有效洞口密度是最有效的指标之一[19]。该指标已广泛地在实地调查中被估计并记录，样本数相对丰富，适用于本研究中大尺度种群密度的归一性分析和预测

天山山脉北坡属于中亚干旱地区典型的山地-绿洲-沙漠(从高地到低地)生态系统[20],动植物的分布很大程度上取决于海拔的变化。在天山北坡，啮齿动物对草原的损害主要由分布在平原荒漠草地的大沙鼠(Rhombomysopimus)和山地草原的黄兔尾鼠(Eolagurusluteus)引起，且大沙鼠主要栖息在海拔 $9 0 0 \mathrm { ~ m ~ }$ 以下的荒漠草地[2]。因此,本文结合文献中数据特点将天山北坡分为海拔 $\langle \leqslant 9 0 0 \mathrm { ~ m ~ }$ 和 ${ > } 9 0 0$ $\mathrm { ~ m ~ } 2$ 类区域，且主要的优势种分别为大沙鼠和黄兔尾鼠。

综上，本文以有效洞口密度反映害鼠的种群密度，从已发表的文献收集天山北坡草地小尺度的有效洞口密度的实地调查信息，利用遥感技术、统计分析等手段，对2类区域分别运用随机森林(RF)模型和Cubist模型模拟有效洞口密度。最后，选取较优方法定量研究环境因子对有效洞口密度时空分布的影响，对1982—2015年的天山北坡草地有效洞口密度时空分布进行预测，并分析其变化特征

# 数据与方法

# 1.1 研究区概况

天山北坡(图1)是指由横贯新疆中部天山山脉发育的河流向北流经的区域，地理位置为 $7 9 ^ { \circ } 5 3 ^ { \prime }$ 2$9 6 ^ { \circ } 0 6 ^ { \prime } \mathrm { E }$ $4 2 ^ { \circ } 5 0 ^ { \prime } { \sim } 4 6 ^ { \circ } 1 2 ^ { \prime } \mathrm { N }$ ,东起伊吾，西至温泉县，北连古尔班通古特沙漠。区域内自然条件的垂直分带性明显，地势南高北低,海拔由山地的 $5 0 0 0 \mathrm { ~ m ~ }$ 左右下降到沙漠边缘的 $2 0 0 \mathrm { ~ m ~ }$ 左右。由于位于亚欧大陆腹地,远离海洋，属于典型的温带大陆性气候，其特点是冬季寒冷漫长，夏季干旱炎热，年均温在$- 6 . 5 { \sim } 1 1 . 0 ^ { \circ } \mathrm { C }$ ,降水季节变化显著，年内降水量主要集中在5、6月，2月最少，年降水量由南部山区中低山带的 $5 0 0 \mathrm { m m }$ 降至北部沙漠区的 $1 0 0 \mathrm { m m }$ 左右。天山北坡独特的自然条件使其成为全球温带干旱区大型山地-绿洲-沙漠生态系统的典型代表[22]

# 1.2数据来源

本研究采用的数据主要包括有效洞口密度和

![](images/4c13f4d7daebb0c51752a57b4069d2270a35776a73aedd4d5843d357a5ff5983.jpg)  
图1基于文献搜集的天山北坡鼠洞调查样点分布

Fig.1Sample distributionofrathole investigationonthe north slopeofTianshan Mountains basedon literaturecolectior

# 干吴区地理

环境因子数据(表1)。有效洞口密度数据通过已公开发表的文献[23-45]获取，所搜集记录中仅有地名但无经纬度信息的通过GPSSPG网站(http://www.gpsspg.com/)进行查询[46]。对得到的数据进行整理，最终得到了275条具有时空信息的有效洞口密度数据，年份跨度为1982—2015年。本文初步选择了21个可能影响有效洞口密度的环境因子，主要包括年份、月份、地形、土壤质地、植被、气温、降水量、短波辐射和放牧强度。

# 1.3 研究方法

首先，通过ArcGIS10.2软件对获得的1982—2015年的有效洞口密度时空信息进行整理，生成含有准确空间位置信息的月尺度矢量文件。随后，根据每个样本的时空信息提取对应的21个环境因子并根据海拔将天山北坡分为 $\leqslant 9 0 0 \mathrm { ~ m ~ }$ 和 ${ > } 9 0 0 \mathrm { ~ m ~ } 2$ 类。最后，分别基于RF模型和Cubist模型拟合有效洞口密度，并选取较优模型定量研究有效洞口密度时空分布的变化特征及其机制。

表1环境因子数据来源  
Tab.1 Data sources of environmental factors   

<html><body><table><tr><td>环境因子</td><td>空间分辨率</td><td>数据来源</td></tr><tr><td>海拔</td><td>30m</td><td>美国地质勘探局全球卫星影像(USGS Earth Explorer,http:/earthexplorer.usgs.gov)</td></tr><tr><td>坡度</td><td>30m</td><td>美国地质勘探局全球卫星影像(USGS Earth Explorer,http://arthexplorer.usgs.gov)</td></tr><tr><td>坡向</td><td>30m</td><td>美国地质勘探局全球卫星影像(USGS Earth Explorer,http://arthexplorer.usgs.gov)</td></tr><tr><td>粉砂含量</td><td>1 km</td><td>国家冰川冻土沙漠科学数据中心(http://www.ncdc.ac.cn)47)</td></tr><tr><td>砂土含量</td><td>1 km</td><td>国家冰川冻土沙漠科学数据中心(htp://www.ncdc.ac.cn)[47]</td></tr><tr><td>黏土含量</td><td>1 km</td><td>国家冰川冻土沙漠科学数据中心(htp://www.ncdc.ac.cn)[47]</td></tr><tr><td>归一化植被指数(NDVI)</td><td>8km</td><td>美国国家航天航空局(NASA)的全球监测与模型研究组(GIMMS)提供的3g.v1数 据(https://ecocast.arc.nasa.gov/data/pub/gimms/)</td></tr><tr><td>叶面积指数(LAI)</td><td>8 km</td><td>NOAA气候数据记录(CDR)的AVHRR叶面积指数(LAI)和吸收光合有效辐射的 部分(FAPAR)数据集</td></tr><tr><td>年平均气温</td><td>1 km</td><td>中国1km分辨率逐月平均气温数据集(1901—2017年)[48-49)</td></tr><tr><td>年最低气温</td><td>1 km</td><td>中国1km分辨率月最低温度数据集(1901—2017年)[49-50]</td></tr><tr><td>年最高气温</td><td>1 km</td><td>中国1km分辨率月最高温度数据集(1901—2017年)[49.51]</td></tr><tr><td>月平均气温</td><td>1 km</td><td>中国1km分辨率逐月平均气温数据集(1901—2017年)[48-49)</td></tr><tr><td>月最高气温</td><td>1 km</td><td>中国1km分辨率月最高温度数据集(1901—2017年)[4,.1]</td></tr><tr><td>月最低气温</td><td>1 km</td><td>中国1km分辨率月最低温度数据集(1901—2017年)[49-50]</td></tr><tr><td>年累积降水量</td><td>1 km</td><td>中国1km分辨率逐月降水量数据集(1901—2017年)[49.52]</td></tr><tr><td>调查前3月的平均降水量</td><td>1 km</td><td>中国1km分辨率逐月降水量数据集(1901—2017年)[49.52]</td></tr><tr><td>月累积降水量</td><td>1 km</td><td>中国1km分辨率逐月降水量数据集(1901—2017年)[49.52]</td></tr><tr><td>放牧强度</td><td>0.08333°</td><td>世界粮农组织(FAO,http://www.fao.org/livestock-systems/en/)野外实测数据 新疆</td></tr><tr><td>短波辐射</td><td>0.1°</td><td>统计年鉴[22.53] 中国区域地面气象要素驱动数据集(1979—2018年)[4-55]</td></tr></table></body></html>

1.3.1RF模 型RF模型是一种以决策树为基本单元的集成学习方法[56]。其基于Bagging算法,从原始样本集 $N$ 中有放回地随机抽取 $n$ 个样本生成新的训练样本集，通过算法训练得到 $n$ 棵决策树，最后通过平均的方式整合各决策树的预测结果，便可得到RF模型的最终结果。RF模型在每个回归树的建立过程中，对样本空间和特征空间进行随机采样，引入随机属性，进而降低了回归树模型之间的相关性，又通过组合大量的回归树，改善了模型的泛化性，使得此算法具备高效、准确等特点。本研究利用网格搜索算法57探索各区数据的最优参数组合，采用Python中scikit-learn包进行模型构建[58]

1.3.2Cubist模型Cubist模型是Quinlan的M5'模型树的进一步发展[59]。Cubist模型在多元线性模型中得到一系列if-then形式的规则，当一组变量符合规则的条件时，使用相应的模型计算变量的预测值[]。Cubist算法用一系列组合起来的分段线性模型，很好地解决了非线性问题。此外，该方法还具有变量的重要性分析功能[6]。本研究使用R软件中Cubist程序包，其主要参数为committees 和neigh-

borso

1.3.3模型精度验证本文从数据集随机选择 $8 0 \%$ 作为模型的训练样本集，剩余的 $2 0 \%$ 作为模型验证样本集。选用均方根误差(RMSE)和决定系数 $\left( R ^ { 2 } \right)$ 作为模型精度评价指标，综合评价RF模型和Cubist模型的预测能力。计算公式如下：

$$
{ \mathrm { R M S E } } = { \sqrt { \sum _ { i = 1 } ^ { n } ( Y _ { i } - Y _ { i } ^ { \prime } ) ^ { 2 } { \Bigg / } n } }
$$

$$
R ^ { 2 } = 1 - { \sum _ { i = 1 } ^ { n } ( Y _ { i } - Y _ { i } ^ { \prime } ) ^ { 2 } } \bigg / { \sum _ { i = 1 } ^ { n } ( Y _ { i } - \bar { Y } ) ^ { 2 } }
$$

式中： $Y _ { i } \setminus Y _ { i } ^ { \prime }$ 和 $\bar { Y }$ 分别为有效洞口密度实际值、预测值和样本平均值； $n$ 为样本数。

# 2结果与分析

# 2.1有效洞口密度样本数据分布特征分析

对从文献中获取的有效洞口密度数据进行统计分析，如表2所示，共275条数据，其中最小值为1个： $\mathrm { h m } ^ { - 2 }$ ,最大值为1370个· $\mathrm { h m } ^ { - 2 }$ ，平均值为254.23个 $\mathrm { h m } ^ { - 2 }$ 。海拔 $\leqslant 9 0 0 \mathrm { ~ m ~ }$ 地区的样点有效洞口密度范围为4\~1220个· $\mathrm { h m } ^ { - 2 }$ ，海拔 ${ > } 9 0 0 \ \mathrm { m }$ 地区的样点有效洞口密度在1\~1370个· $\mathrm { h m } ^ { - 2 }$ 之间。

# 2.2草原有效洞口密度拟合模型精度评价与优选

将全部环境因子作为自变量，有效洞口密度为因变量，分别构建RF模型和Cubist模型并计算 $R ^ { 2 }$ 和RMSE(图2)。结果表明，在海拔 $\leqslant 9 0 0 \ \mathrm { m }$ 地区其RF模型和Cubist模型的 $R ^ { 2 }$ 分别为0.773和0.832，在海拔 ${ > } 9 0 0 \mathrm { ~ m ~ }$ 地区其RF模型和Cubist模型的 $R ^ { 2 }$ 均在0.600以上，Cubist模型均高于RF模型。同时，RF模型的RMSE均大于Cubist模型。综上，Cubist模型具有更高的拟合精度和更小的误差，因此本研究采用Cubist模型来预测天山北坡草地有效洞口密度。

# 2.3影响因子的重要性分析

本文基于Cubist模型各因子的重要性排序，分析环境因子对天山北坡草地有效洞口密度时空分布的影响(图3)。Cubist模型可根据样本信息将相关性不强的输入因子剔除，结合预测因子的相对重要性，筛选出预测结果较好的影响因子。重要性显示海拔 $\leqslant 9 0 0 \ \mathrm { m }$ 和海拔 ${ > } 9 0 0 \mathrm { ~ m ~ }$ 地区之间存在着显著差异。在天山北坡海拔 $\leq 9 0 0 \mathrm { ~ m ~ }$ 地区，对草地有效洞口密度分布贡献最大的是月最低气温，其次为月平均气温、叶面积指数(LAI)。而对于 ${ > } 9 0 0 \mathrm { ~ m ~ }$ 地区，贡献最大的为年累积降水量，其次为放牧强度、归一化植被指数(NDVI)。气候因子、植被状况与人类活动因子对天山北坡有效洞口密度时空分布影响较大。

# 2.4天山北坡草地有效洞口密度时空分布

使用此Cubist模型对研究区草地有效洞口密度时空分布进行反演(图4)。并根据Cubist模型分别计算1982—2015年天山北坡草地有效洞口密度在4月和10月的平均值(图5)。比较1982、1993、2004年和2015年有效洞口密度的年际空间分布差异以及其春季(4月)和秋季(10月)的季节性变化。结果表明，有效洞口密度具有明显的区域差异，靠近人类活动频繁的农田生态系统周围草地有效洞口密度普遍较高，而北部受人类干扰较少的荒漠地区其密度较低。在海拔 $\leqslant 9 0 0 \ \mathrm { m }$ 地区4月有效洞口密度平均为354个· $\mathrm { h m } ^ { - 2 }$ ,10月平均为424个· $\mathrm { h m } ^ { - 2 }$ ;海拔>$9 0 0 \mathrm { m }$ 地区4月有效洞口密度平均为421个· $\mathrm { h m } ^ { - 2 }$ ,10月平均为407个· $\mathrm { h m } ^ { - 2 }$ 。1982—2015年海拔 $\leqslant 9 0 0 \ \mathrm { m }$ 地区有效洞口密度整体为波动递增的趋势，34a间4月的有效洞口密度增加了 $3 7 . 2 5 \%$ ，10月增加了$4 1 . 5 8 \%$ ;而海拔 ${ > } 9 0 0 \ \mathrm { m }$ 地区整体为波动递减的趋势，34a间4月减少了 $4 . 8 3 \%$ ,10月减少了 $2 6 . 9 9 \%$ ，且草地有效洞口密度波动剧烈(图5)。在天山北坡海拔 $\leqslant 9 0 0 \mathrm { ~ m ~ }$ 地区每年10月的有效洞口密度相对于4月显著增加，体现出较强的季节差异性。

# 3讨论

本研究主要基于Cubist模型、结合环境因子预测有效洞口密度，基本实现了草原小型啮齿动物种群密度时空量化与表达，有效地弥补了目前在大时

表2有效洞口密度统计描述  
Tab.2Statistical description of active burrow entrance densities   

<html><body><table><tr><td>数据类型</td><td>样本数</td><td>最小值/个·hm-2</td><td>最大值/个·hm²</td><td>平均值/个·hm-2</td><td>标准差</td></tr><tr><td>全部数据</td><td>275</td><td>1</td><td>1370</td><td>254.23</td><td>254.23</td></tr><tr><td>海拔≤900m地区数据</td><td>190</td><td>4</td><td>1220</td><td>251.76</td><td>222.54</td></tr><tr><td>海拔>900m地区数据</td><td>85</td><td>1</td><td>1370</td><td>259.73</td><td>253.62</td></tr></table></body></html>

![](images/4f46a6ecd90bb6b9cd54367e19006d5243e766b0c20ad4d9331abb917687f682.jpg)  
图2有效洞口密度拟合值在海拔 $\langle \leqslant 9 0 0 \mathrm { ~ m ~ }$ 和 ${ > } 9 0 0 \mathrm { ~ m ~ }$ 地区的验证散点图 Fig.2 Scatter polt of fiting values of active burrow entrance densities in areas with an elevation less than or equal to $9 0 0 \mathrm { ~ m ~ }$ and higher than $9 0 0 \mathrm { m }$

![](images/d4d69ec800274d64996048ad4ffbcbac06a1729a46cf18147a138fcf7244e7c2.jpg)  
注：LAI为叶面积指数；NDVI为归一化植被指数。图3有效洞口密度的影响因子重要性  
Fig.3Importance of influencing factors for active burrow entrance densities

空尺度草原害鼠时空变化规律研究方面的不足。已有的研究因缺乏长时间序列以及较大研究区的

观测，导致对小型啮齿动物种群密度区域分布差异的认识存在局限性。

![](images/26f7e5bfd9888a718619011e36092745e25c365b6d9fe45b70dd1b258545ab2a.jpg)  
图41982—2015年天山北坡草地每11a的有效洞口密度空间分布

![](images/ca3c758ff60d2674336bf91b6b1c41101f1da8017482d43dc0428da1d8370e2a.jpg)  
Fig.4Spatial distributions of activeburrow entrance densities in grassand on the north slope of Tianshan Mountains every 11 years from 1982 to 2015   
图51982—2015年天山北坡草地有效洞口密度在海拔 $\langle \leqslant 9 0 0 \mathrm { ~ m ~ }$ 和 ${ \it \Omega } > 9 0 0 { \mathrm { ~ m } }$ 地区的变化趋势  
Fig.5Changetrendofactiveburrow entrancedensities ingrasslandonthe north slopeofTianshan Mountains inareas withan elevation less than or equal to $9 0 0 \mathrm { ~ m ~ }$ and higher than $9 0 0 \mathrm { m }$ from 1982 to 2015

# 干旱区地理

在研究方法方面，已有的研究中鲜有将RF、Cubist模型等机器学习方法应用到小型啮齿动物种群密度估算的研究方面。因此，本研究尝试将不同机器学习方法在该领域进行应用，这也是本文的主要创新点之一。所构建的Cubist模型在量化环境因子对有效洞口密度的影响方面，优于RF模型。草原小型啮齿动物生态特点是种群数量波动剧烈，有些年份较低,有些年份猛增，且其分布具有明显的区域性差异[2]。Cubist模型可以针对不同区域构建合适的应用模型，其能够同时处理连续的和离散的数据[63],因此,相对于RF模型,Cubist模型可能能够更好地模拟草原有效洞口密度。

首先，本研究发现植被状况在鼠类种群密度的时空分布中占重要地位，但一个有趣的现象是，在海拔 $\langle \leqslant 9 0 0 \mathrm { ~ m ~ }$ 地区，影响有效洞口密度时空分布的主要是LAI,而对于海拔 ${ > } 9 0 0 \ \mathrm { m }$ 地区为NDVI（图3）。这可能是由于遥感NDVI数据在监测梭梭的生长和地下生物量方面不是很有效。因为在海拔 $\langle \leqslant 9 0 0 \mathrm { ~ m ~ }$ 的平原荒漠地区，大沙鼠将梭梭的嫩根和树枝作为主要食物，而黄兔尾鼠主要食用青蒿属植物。有效洞口密度与LAI或NDVI之间关系的差异可能受到海拔 $\leqslant 9 0 0 \ \mathrm { m }$ 和 $\lvert > 9 0 0 \mathrm { ~ m ~ }$ 地区中大沙鼠和黄兔尾鼠所消耗不同类型植被的影响。植被生长状况直接决定鼠类食物数量和品质[64。植物群落的各项指标（植被高度、盖度、密度和地下生物量以及群落多样性等)都综合地影响着啮齿动物种群密度[65-67]。因本文中有效洞口密度数据是通过已公开发表的文献获取，而文献中缺乏调查有效洞口密度时所涉及的植被基本性状指标，且我们目前无法获取天山北坡植被群落的空间数据。因此,本文环境变量中的植被性状指标只涉及植被指数(NDVI、LAI),虽植被指数已广泛用来定性和定量评价植被覆盖及其生长活力[8]，但对于优势植物种类等性状指标的缺乏，可能会使环境因子的预测能力受到很大的限制。此外，使用NDVI和LAI数据较粗糙的空间分辨率可能会给此类分析带来不确定性，特别是在植被覆盖率较低的沙漠地区，这可能导致低估空间植被变异性对有效洞口密度的影响。除食物因素外，气候因子与放牧强度对啮齿动物种群密度也产生了极大的影响，并且影响会因地区而异。对比2类地区，发现有效洞口密度对温度响应显著的区域为海拔 ${ \leqslant } 9 0 0 ~ \mathrm { { m } }$ 地区，而降水影响显著的区域为 ${ > } 9 0 0 \ \mathrm { m }$ 地区。这可能是因为在 ${ > } 9 0 0 \mathrm { ~ m ~ }$ 海拔带降水的时空异质性较高，因此对植被生长的影响更大[9],这与天山北坡和全国范围的相关性空间研究结论是相吻合的[70-71]。此外,梭梭是大沙鼠的主要食物来源,而黄兔尾鼠主要食用青蒿属植物，且黄兔尾鼠其在阴雨刮风等气温较低天气条件下，活动性明显降低。这可能也是黄兔尾鼠种群密度对降水更敏感的原因。在自然情况下，鼠类通过与草地环境的相互作用、相互协调使之经常保持动态的平衡状态。然而，长期以来，人们为经济利益所驱动的高强度利用方式，深刻地影响鼠类及天敌动物赖以生存地草地基质条件，而群居的植食性鼠类生殖力强，种群数量增长快，往往在此类次生环境中占据优势而发生鼠害[2]。一些学者基于大面积的草地调查资料也发现了草地鼠类种群密度的空间分布与放牧强度有密切关系[73-74]

其次，天山北坡海拔 ${ \cdot } > 9 0 0 \mathrm { ~ m ~ }$ 靠近人类活动频繁的农田生态系统周围的草地区域，其有效洞口密度普遍较高，这可能是因为黄兔尾鼠主要栖息在丘陵及荒漠草原,农垦后聚集在农田及水渠附近[75]。黄兔尾鼠数量年际变动较为剧烈，往往在中低密度水平连续维持若干年之后，种群密度突然升高，而后又处于低潮期。低潮后，在自然条件适宜的年份密度又开始增大(图5)。由本研究可以发现，黄兔尾鼠数量的年际变动可能主要归因于降水量、放牧强度和植被状况，但鉴于黄兔尾鼠种群密度与植被-降水-人类活动的关系复杂、时空不确定性大，这一现象的产生机制，还需要进一步探讨。

最后，环境因子和有效洞口密度是一个动态变化的过程，遥感技术能够及时进行大范围监测了解环境各个时期的变化。有效洞口密度的时空动态在响应环境因子和人类活动的复杂作用时展现出叠加效应，需要从多视角研究小型啮齿动物种群密度时空变化。本文选择了1982—2015年的数据进行建模，能够反映啮齿动物种群密度的年际和季节的变化情况，但对于偶尔极高的繁殖率，环境因子的预测能力可能受到很大的限制。此外，鼠类种群年龄结构、天敌种群分布以及人为因素[76-77]在鼠洞密度分布的预测中具有重要影响，这在未来的研究中需要更多关注。

# 4结论

本研究收集了1982—2015年的天山北坡有效洞口密度的小尺度时空分布数据和环境因子数据，并基于Cubist模型估算天山北坡草地有效洞口密度，量化了环境要素对小型啮齿动物种群密度的影响，取得了较好的研究精度和效果，为区域草原鼠害预防预测工作提供了新思路、新方法。得到以下结论：

（1）利用Cubist模型和RF模型对天山北坡草地有效洞口密度进行预测，海拔 $\langle \leqslant 9 0 0 \mathrm { ~ m ~ }$ 地区拟合效果 $R ^ { 2 }$ 分别为0.832和0.773，海拔 ${ > } 9 0 0 \mathrm { ~ m ~ }$ 地区 $R ^ { 2 }$ 分别为0.667和0.612，Cubist模型拟合精度明显优于RF模型。

(2）基于Cubist模型的影响因子重要性分析结果，植被状况、气象因子和放牧强度是天山北坡有效洞口密度时空分布的主要环境驱动因素。在天山北坡内的海拔 $\leqslant 9 0 0 \ \mathrm { m }$ 和 ${ > } 9 0 0 \ \mathrm { m }$ 地区中，有效洞口密度的驱动机制存在着显著差异。

(3）在海拔 $\langle \leqslant 9 0 0 \mathrm { ~ m ~ }$ 地区，气温对有效洞口密度的贡献度比在海拔 ${ \bf > } 9 0 0 { \bf \ m }$ 地区更高，而降水量对其影响更低。在海拔 $\langle \leqslant 9 0 0 \mathrm { ~ m ~ }$ 地区，影响有效洞口密度时空分布的主要是LAI,而对于海拔 ${ > } 9 0 0 \ \mathrm { m }$ 地区为NDVI。这可能是受到大沙鼠和黄兔尾鼠所消耗不同类型植被的影响。

（4)有效洞口密度的时空分布具有明显的年份和季节波动，1982—2015年海拔 $\leqslant 9 0 0 \ \mathrm { m }$ 地区有效洞口密度整体为波动递增的趋势，34a间4月有效洞口密度增加了 $3 7 . 2 5 \%$ ,10月增加了 $4 1 . 5 8 \%$ ;而海拔 ${ \cdot } { > } 9 0 0 \mathrm { ~ m ~ }$ 地区整体为波动递减的趋势，34a间4月减少了 $4 . 8 3 \%$ ,10月减少了 $2 6 . 9 9 \%$ ○

(5）在海拔 ${ > } 9 0 0 \mathrm { ~ m ~ }$ 地区，草地有效洞口密度波动剧烈，有效洞口高密度区主要分布在靠近人类活动的牧区和绿洲区。这可能主要归因于降水量、放牧强度和植被状况的叠加效应，但鉴于黄兔尾鼠种群密度与植被-降水-人类活动的关系复杂、时空不确定性大，这一现象的产生机制，还需要进一步探讨。未来可通过大数据分析手段、提高数据的精度或多视角考虑种群密度的影响因子，尤其是植被基本性状指标，并与空间异质性探测方法结合，多层次深化本研究方向和主题。

# 参考文献(References)

[1]胡雷,阿的鲁骥,字洪标,等.高原酚鼠扰动及恢复年限对高寒草甸土壤养分和微生物功能多样性的影响[J].应用生态学报，

2015,26(9): 2794-2802.[Hu Lei,Ade Luji, Zi Hongbiao,et al.Effects of highland rat disturbance and recovery on soil nutrients and microbial functional diversity in high-cold meadows[J].Chinese Journal of Applied Ecology,2015,26(9): 2794-2802.]   
[2]李燕妮,袁帅,付和平,等.典型草原啮齿动物密度与牧草损失 量的关系[J].兽类学报,2018,38(4):369-376.[Li Yanni,Yuan Shuai,Fu Heping,et al.Relationship between the densityof typical grassland rodents and the loss of pasture[J]. Acta Theriologica Sinica,2018,38(4): 369-376.]   
[3]刘汉武,王荣欣,张凤琴,等.我国害鼠不育控制研究进展[J].生 态学报,2011,31(19): 5484-5494.[Liu Hanwu,Wang Rongxin, Zhang Fengqin,et al.Advances in the control of rodent sterility in China[J]. Acta Ecologica Sinica, 2011,31(19): 5484-5494.]   
[4] 韩立辉,尚占环,任国华,等.青藏高原"黑土滩"退化草地植物 和土壤对秃斑面积变化的响应[J].草业学报,2011,20(1):1-6. [Han Lihui, Shang Zhanhuan,Ren Guohua,et al.Responses of plants and soil to changes of bald spot area in degraded grassland of“black soil beach”in Qinghai Tibet Plateau[J].Acta Prataculturae Sinica,2011,20(1): 1-6.]   
[5]郭强,王玉琴,鲍根生,等.气象因子对高原酚鼠种群数量的影 响[J].草业学报,2020,29(8):188-194.[Guo Qiang,Wang Yuqin,Bao Gensheng,et al.Efects of meteorological factors on the population of Plateau Zokor[J]. Acta Prataculturae Sinica, 2020, 29 (8): 188-194.]   
[6]乔雪丽,林峻,吴建国,等.气候变化情景下大沙鼠潜在地理分 布[J].生态学报,2021,41(17):1-9.[Qiao Xueli,Lin Jun,Wu Jianguo,et al.Potential geographical distribution of gerbils under climate change scenario[J]. Acta Ecologica Sinica,2021,41(17): 1-9.]   
[7]何咏琪,黄晓东,侯秀敏,等.基于3S技术的草原鼠害监测方法 研究[J].草业学报,2013,2(3):3-40.[He Yongqi,Huang Xiaodong,Hou Xiumin,etal.Monitoring grassland rodents with 3S techonlogies[J].Acta Prataculturae Sinica,2013,2(3): 33-40.]   
[8]Mohammadi S,Ebrahimi E, Moghadam M S,et al. Modelling current and future potential distributions of two desert jerboas under climate change in Iran[J]. Ecological Informatics,2019,52: 7-13.   
[9]栗小东,王晶,杨春蕙,等.基于两种机器学习方法分析东海北 部海域三疣梭子蟹(Portunus trituberculatus)时空分布[J].海洋与 湖沼,2021,52(5):1284-1292.[Li Xiaodong,WangJing,Yang Chunhui,etal.SpatiotemporaldistrutioofPrtunustrituberculatus in the northern East China Sea based on two machine learning methods[J]. Oceanologia etLimnologia Sinica,2021,52(5):1284- 1292.]   
[10]Forney KA,Becker EA,Foley DG,etal.Habitat-based models of cetacean density and distribution in the central North Pacific[J]. Endangered Species Research,2015,27(1): 1-20.   
[11] 黄彬,卫万荣,张灵菲,等.环境条件对啮齿动物种群的影响[J]. 草业科学,2013,30(6):949-953.[Huang Bin,Wei Wanrong, Zhang Lingfei,et al.Impact of environmental conditions on rodent population[J]. Pratacultural Science,2013,30(6): 949-953.]

# 干吴区地理

[12] 马涛,郑江华,温阿敏,等.基于无人机低空遥感的荒漠林大沙 鼠鼠洞分布与地形的关系——以新疆古尔通古特沙漠南缘局 部为例[J].林业科学,2018,54(10):180-188.[Ma Tao,Zheng Jianghua,Wen Amin,et al.Relationship between the distribution of Rhombomys opimus holes and the topography in desert forest based on low altitude remote sensing with the unmanned aerial vehicle (UAV): A case study at the southern margin of the Gurbantunggut Desert in Xinjiang,China[J]. Scientia Silvae Sinicae,   
2018,54(10): 180-188.] [13] 冯峰,贡保草,牛克昌.不同放牧模式下高原鼠兔密度与高寒植 被和土壤的关系[J].草业科学,2019,36(1):2915-2925.[Feng Feng,Gong Baocao,Niu Kechang.Relationship between plateau pika density and alpine vegetation and soil under different grazing modes[J]. Pratacultural Science,2019,36(11): 2915-2925.] [14] Brown JH, Ernest S K M. Rain and rodents: complex dynamics of desert consumers[J]. BioScience,2002,52(11): 979-987. [15]乌云嘎,查木哈,张晓东,等.荒漠区啮齿动物群落与植物因子 的冗余分析[J].草业科学,2014,31(12):2323-2332.[Wu Yunga, Cha Muha, Zhang Xiaodong,et al.Redundancy analysis between rodent communities and plant factors in desert[J].Pratacultural Science,2014,31(12): 2323-2332.] [16] 周立志,马勇,李迪强.大沙鼠在中国的地理分布[J].动物学报,   
2000,46(2): 130-137.[Zhou Lizhi, Ma Yong,Li Diqiang. Distribution of great gerbil (Rhombomys opimus) in China[J].Acta Zoologica Sinica,2000,46(2): 130-137.] [17] 袁帅,武晓东,付和平,等.不同干扰下荒漠啮齿动物群落多样 性的多尺度分析[J].生态学报,2011,31(7):1982-1992.[Yuan Shuai,Wu Xiaodong,Fu Heping,et al. Multi-scales analysis on diversity of desert rodent communities under different disturbances [J]. Acta Ecologica Sinica,2011,31(7): 1982-1992.] [18] 王利清,武晓东,付和平,等.人为不同干扰方式下荒漠啮齿动 物群落格局年间变动趋势[J].干旱区资源与环境,2011,25(3):   
146-151.[Wang Liqing,Wu Xiaodong,Fu Heping,et al. The annual fluctuating tendency and patterns of desert rodent communities under human disturbance[J]. Journal of Arid Land Resources and Environment, 2011,25(3): 146-151.] [19] 熊瑞东,程武学,熊钰丹,等.基于无人机的若尔盖高寒草地鼠 害程度估算模型研究[J].中国农业信息,2020,32(6):32-45. [Xiong Ruidong, Cheng Wuxue, Xiong Yudan,et al. Estimation model of rodent damage degree in Zoige alpine grassland based on UAV[J]. ChinaAriulturalforatio,22(6):.] [20] Zhang M,Luo G,Cao X,et al. Numerical simulation of the irrigation effects on surface fluxes and local climate in typical mountainoasis-desert systems in the Central Asiaarid area[J]. Journal of Geophysical Research: Atmospheres,2019(124): 12485-12506. [21] 韩崇选,李金钢,杨学军,等.中国农林啮齿动物与科学管理 [M].杨凌:西北农林科技大学出版社,2005:183-186.[Han Chongxuan,Li Jingang,Yang Xuejun, et al. Rodents and scientific management in agriculture and forestry in China[M]. Yangling: Northwest A&F University Press,2005:183-186.]   
[22] 张文强,罗格平,郑宏伟,等.基于随机森林模型的内陆干旱区 植被指数变化与驱动力分析:以北天山北坡中段为例[J].植物 生态学报,2020,44(11): 1113-1126.[Zhang Wenqiang,Luo Geping, Zheng Hongwei,et al. Analysis of vegetation index change and driving force in inland arid area based on random forest model: Acase studyof the midle partof thenorther slopeof north Tianshan Mountains[J]. Chinese Journal of Plant Ecology,2020,44 (11): 1113-1126.]   
[23] 龚红花,乌图那生.新疆博州草原鼠害发生分布区域与防治的 研究[J].草食家畜,2011(4):17-20.[Gong Honghua,Wutu Nasheng.The research on prevention of rodent damage andits distribution in Bozhou[J]. Grass-Feeding Livestock,2011(4):17-20.]   
[24] 马良贤,王学锋,侯兰新,等.新疆东部草原鼠害的调查及危害 类型的划分[J].西北民族学院学报,1996(1): 47-50.[Ma Liangxian,Wang Xuefeng,Hou Lanxin,et al. Investigation and classification of rodent damage in grassland in eastern Xinjiang[J]. Journal of Northwest Minzu University,1996(1):47-50.]   
[25] 杨东生.用经验预测黄兔尾鼠种群数量的发生趋势[J].草食家 畜,2007(2):15-17. [Yang Dongsheng.Predicting the population trend of yellow rabbit tail ratby experience[J]. Grass-Feding Livestock, 2007(2): 15-17.]   
[26] 张小侠.乌苏市草地鼠害生物防治措施[J].农村科技,2013(6): 44-45.[Zhang Xiaoxia. Biological control measures of grassland rodents in Wusu City[J]. Rural Science and Technology,2013(6): 44-45.]   
[27] 党惠才,郭正财.大沙鼠种群数量动态及周期性[J].新疆畜牧 业,2010(11): 48-50.[Dang Huicai, Guo Zhengcai. Population dynamicsandperiodicityof Rhombomysopimus[J]. Xinjiang Xumuye, 2010(11): 48-50.]   
[28] 张宏伟,姚明琴,林超波,等.2012年新疆兵团准噶尔盆地动物 鼠疫监测分析[J].兵团医学,2013,37(3):58-60.[Zhang Hongwei,Yao Mingqin,Lin Chaobo,et al. Monitoring and analysis of animal plague in Junggar Basin of Xinjiang Bingtuan in 2012[J]. Journal of Bingtuan Medicine,2013,37(3): 58-60.]   
[29] 尹文江,张宏伟,解卫刚,等.2010年新疆五家渠准噶尔盆地大 沙鼠鼠疫自然疫源地监测报告[J].兵团医学,2012,34(4):54- 56.[Yin Wenjiang,Zhang Hongwei, Xie Weigang,et al. Monitoring report on natural foci of gerbils plague in Junggar Basin, Xinjiang,2010[J]. Journal of Bingtuan Medicine,2012,34(4): 54-56.]   
[30] 徐满厚,刘彤,姜莉.古尔班通古特沙漠南部梭梭鼠害特征及防 治生态阈值研究[J].干旱区资源与环境,2012,26(6):126-133. [Xu Manhou, Liu Tong, Jiang Li. Study on damage characteristics and control ecological threshold of Haloxylon ammodendron in the south of Gurbantunggut Deser[J]. Jourmal of Arid Land Resources and Environment,2012,26(6): 126-133.]   
[31] 魏旭明,杨钦环,韩兵兵,等.兵团六师草原生态监测情况[J].中 国畜牧业,2014(4): 50-51.[Wei Xuming,Yang Qinhuan,Han Bingbing,et al. Grassand ecological monitoring of the sixth division of Bingtuan[J]. China Animal Industry,2014(4): 50-51.]   
[32]解卫刚.尹文江.新疆兵团第六师103 团准噶尔荒漠鼠疫监测

分析[J].疾病预防控制通报,2016,31(6):41-42,82.[Xie Weigang,Yin Wenjiang.Monitoring and analysis of plague in Junggar Basinof the103regimentoftesixth divisionof Xinjiang Bingtuan[J]. Bulletin of Disease Control and Prevention,2O16,31(6): 41- 42, 82.]   
[33] 姚明琴,刘成刚,陆志刚,等.八师石河子荒漠地区鼠疫疫源地 现状调查[J].疾病监测与控制,2016,10(4):304-306.[Yao Mingqin,Liu Chenggang,Lu Zhigang,et al.Investigation on plague foci of eight divisions in Shihezi desert area[J]. Journal of Diseases Montor and Control,2016,10(4): 304-306.]   
[34] 林超波,董思文,谭华,等.2010—2012年新疆生产建设兵团农 六师鼠疫监测结果分析[J].疾病预防控制通报,2013,28(5): 67-68.[Lin Chaobo,Dong Siwen,Tan Hua, et al.Analysis of surveillance results of plague in six divisions of Xinjiang Production and Construction Corps from 2010 to 2012[J]. Bulletin of Disease Control and Prevention,2013,28(5): 67-68.]   
[35] 尹小平,田延河,骄娃,等.新疆北部边境口岸大沙鼠种群分布 特征及活动规律调查[J].中国媒介生物学及控制杂志,2015, 26(2): 196-199.[Yin Xiaoping,Tian Yanhe,Jiao Wa,et al. The distribution characteristics and activity patterns ofthe Rhombomys opimus population in northern Xinjiang borders[J]. Chinese Journal of Vector Biology and Control,2015,26(2): 196-199.]   
[36] 阿帕尔,沙依拉吾,努尔古丽.克拉玛依市鼠类的调查报告[J]. 新疆畜牧业,2007(增刊1):38-40.[Apaer,Shayilawu,Nuerguli. Investigation report on rodents in Karamay City[J]. Xinjiang Xumuye, 2007(Suppl. 1): 38-40.]   
[37] 艾尼瓦尔·库尔班,塞力汗,马俊杰,等.乌鲁木齐戈壁荒漠动物 鼠疫自然疫源地调查[J].地方病通报,2009,24(6):20-21,23. [Kuerban Einiwaer,Sailihan,Ma Junjie,etal.Investigationonnatural foci of desert animal plague in Gobi, Urumqi[J].Endemic Diseases Bulletin,2009,24(6): 20-21,23.]   
[38] 郭刚.新疆北疆地区鼠类和体外寄生生物病原携带及遗传特征 研究[D].乌鲁木齐:新疆医科大学,2016.[Guo Gang.Distribution and genetic on the rodents,ectozoic parasites and associated pathogens in northern regionof Xinjiang[D]. Urumqi: Xinjiang Medical University,2016.]   
[39] 周旭东,张永军,黄健,等.新疆甘家湖自然保护区啮齿动物群 落结构与时间动态分析[J].动物学杂志,2004,39(6):58-61. [Zhou Xudong,Zhang Yongjun,Huang Jian,et al.Analysis of community structure and change of the rodents at Ganjiahu Nature Reserve in Xinjiang[J]. Chinese Journal of Zoology,2004,39(6): 58- 61.]   
[40] 靳新霞,张大铭.莫索湾垦区啮齿动物群落结构与物种多样性 分析[J].动物学杂志,2005,40(6):30-37.[Jin Xinxia, Zhang Daming. Rodent community structure and species diversity of analysisinMosuowanreclamation[J].Chinese Journal of Zoology, 2005, 40(6): 30-37.]   
[41] 张大铭,艾尼瓦尔.呼图壁种牛场草原生态站鼠类群落初步研 究[J].新疆大学学报(自然科学版),1997,14(3):53-56.[Zhang Daming,Einiwaer.Preliminary study on rodent community in grassland ecological station of Hutubi catle farm[J].Journal of Xinjiang University (Natural Science Edition),1997,14(3): 53- 56.]   
[42] 张大铭,姜涛,马合木提,等.阿拉山口啮齿动物群落结构及其 变化[J].兽类学报,1998,18(2):75-76,57.[Zhang Daming,Jiang Tao, Mahemuti, et al. The community structure and changes of rodents in Alataw pass[J]. Acta Theriologica Sinica,1998,18(2): 75- 76, 57.]   
[43] 陶双庆,侯兰新,赵新春,等.对黄兔尾鼠生态的一些观察[J].干 旱区研究,1985,2(3): 42-45.[Tao Shuangqing,Hou Lanxin, Zhao Xinchun, et al. Some observations on the ecology of Lagurus luteus [J]. Arid Zone Research,1985,2(3): 42-45.]   
[44] 党惠才,郭正财,康淑红.草原兔尾鼠种群数量分布及周期性初 探[J].新疆畜牧业,2007(增刊1): 21-22.[Dang Huicai,Guo Zhengcai, Kang Shuhong.Population distribution and periodicity of Lagurus lagurus[J]. Xinjiang Xumuye,2007(Suppl.1): 21-22.]   
[45] 李小锋,刘秀梅,李建明,等.天山北坡不同类型草地产草量变 化原因分析[J].新疆畜牧业,2011(5):30-33.[Li Xiaofeng, Liu Xiumei,Li Jianming,et al.Analysis on the change of grass yield in different types of grassland on the north slope of Tianshan Mountain[J]. Xinjiang Xumuye, 2011(5): 30-33.]   
[46] 刘洋,石娟.气候变化背景下埃及吹绵在中国的适生区预测 [J].植物保护,2020,46(1):108-117.[Liu Yang,Shi Juan.Prediction of potential geographical distribution of Icerya aegyptiaca in China under climate change[J].Plant Protection,202O,46(1):108- 117.]   
[47]卢玲,刘超.基于世界土壤数据库(HWSD)的中国土壤数据集 (v1.1)[DB/OL]. [2019-09-21]. htp://www.ncdc.ac.cn.[Lu Ling,Liu Chao.Chinese soil dataset based on Harmonized World Soil Database version 1.1[DB/OL].[2019-09-21]. http://www.ncdc.ac.cn.]   
[48] 彭守璋.中国 $1 ~ \mathrm { k m }$ 分辨率逐月平均气温数据集(1901—2017) [DB/OL]. [2019-05-17]. https:/oi.org/10.11888/Meteoro.pdc.270 961. [Peng Shouzhang. $1 - \mathrm { k m }$ monthly mean temperature dataset for china (1901—2017)[DB/OL].[2019-05-17]. https://doi.org/10. 11888/Meteorotpdc.270961.]   
[49] Peng S Z,Ding Y X,Liu W Z,et al.1 km monthly temperature and precipitation dataset for China from 1901 to 2017[J].Earth System Science Data,2019,14(4): 1931-1946.   
[50] 彭守璋.中国 $1 ~ \mathrm { k m }$ 分辨率月最低温度数据集(1901—2017)[DB/ OLJ. [2019-05-17]. htp://data.tpdc.ac.cn/zh-hans/data/5b644091- 5fbf-4cd8-9324-6a543c9c369f.[Peng Shouzhang.1-kmmonthly minimum temperature dataset for China (1901—2017)[DB/OL]. [2019-05-17]. htp:/data.tpdc.ac.cn/zh-hans/data/5b644091-5fbf4cd 8-9324-6a543c9c369f.]   
[51] 彭守璋.中国 $1 ~ \mathrm { k m }$ 分辨率月最高温度数据集(1901—2017)[DB/ OL]. [2020-04-09]. htp://data.tpdc.ac.cn/zh-hans/data/35fff9f8e1b-4296-801f-d8231e4f8dc3.[Peng Shouzhang.1-km monthly maximum temperature dataset for China (1901—2017)[DB/OL]. [2020-04-09]. http://data.tpdc.ac.cn/zh-hans/data/35fff9f-8e1b-4 296-801f-d82 31e4f8dc3.]   
[52] 彭守璋.中国 $1 \mathrm { k m }$ 分辨率逐月降水量数据集(1901—2017)[DB/ OL]. [2020-04-09]. htp:/data.tpdc.ac.cn/zh-hans/data/faae7605-

# 干旱区地理

a0f2-4d18-b28f-5cee413766a2. [Peng Shouzhang.1-km monthly precipitation dataset for China (1901—2017)[DB/OL].[2020- 04-09]. htp://data.pdc.ac.cn/zh-hans/data/faae7605-a0f2-4d18- b28f-5cee413 766a2.]   
[53]Gilbert M,Nicolas G,Cinardi G,et al.Global distribution data for catle,buffaos,hors,heepgoats,g,ickesandducksin 2010[J].Scientific Data,2018,5(1):180227,doi:10.1038/sdata. 2018.227.   
[54]阳坤,何杰.中国区域地面气象要素驱动数据集(1979—2018) [DB/OL].[2019-05-09]. http://data.tpdc.ac.cn/zh-hans/data/802 8b9 44-daaa-4511-8769-965612652c49.[Yang Kun, He Jie. China meteorological forcing dataset (1979—2018)[DB/OL]. [2019-05-09]. http://data.tpdc.ac.cn/zh-hans/data/8028b944-daaa-4511-8769- 965612652c49.]   
[55]Yung K,He J,Tang W J,et al. On downward shortwave and longwave radiations over high altitude regions: Observation and modeling in the Tibetan Plateau[J].Agricultural and Forest Meteorology, 2010,150(1): 38-46.   
[56]BreimanL.Random forests[J]. Machine Learning,200l,45(1): 5-32.   
[57] Lujan-Moreno G A,Howard PR,Rojas O G,etal. Design of experiments and response surface methodology to tune machine learning hyperparameters,with a random forest case-study[J].Expert Systems with Applications,2018,109:195-205.   
[58] 方馨蕊,温兆飞,陈吉龙,等.随机森林回归模型的悬浮泥沙浓 度遥感估算[J].遥感学报,2019,23(4):756-772.[Fang Xinrui, Wen Zhaofei, Chen Jilong,et al. Remote sensing estimation of suspended sediment concentration based on stochastic forest regression model[J].Journal of Remote Sensing,2019,23(4): 756-772.]   
[59] Quinlan JR. Combining instance-based and model-based learning [C]/Machine Learning,Proceedings of the Tenth International Conference.Amherst: University of Massachusetts,1993: 236-243.   
[60]Goh K M, Maulidiani M,Rudiyanto R,et al. Rapid assessment of total MCPD esters in palm-based cooking oil using ATR-FTIR application and chemometric analysis[J]. Talanta,2019,198: 215-223.   
[61] 戴舒,付迎春,赵耀龙.基于Cubist模型树的城市不透水面百分 比遥感估算模型[J].地球信息科学学报,2016,18(10):1399- 1409.[Dai Shu,Fu Yingchun, Zhao Yaolong. The remote sensing model for estimating urban impervious surface percentage based on the cubic model tree[J]. Journal of Geo-Information Science, 2016,18(10): 1399-1409.]   
[62] 王玮,冯琦胜,于惠,等.“3S"技术在草地鼠虫害监测与预测中 的应用[J].草业科学,2010,27(3):31-39.[Wang Wei,Feng Qisheng,Yu Hui,etal.Applicationof“3S”technologyonoitoring and prediction of the grassland rodents and insects[J]. Pratacultural Science,2010,27(3): 31-39.]   
[63] 陈家乐,唐林茜,相满城,等.区域土壤-水稻籽粒镉耦合关系 模型的构建和验证[J].生态学杂志,2021,40(8):2341-2347. [Chen Jiale,Tang Linxi, Xiang Mancheng,et al. Model constructions and verifications for regional cadmium coupling relationships in soil-rice grain[J]. Chinese Journal of Ecology,2021,40 (8): 2341-2347.]   
[64]Turchin P,Batzli G O.Availability of food and the population dynamics of arvicoline rodents[J]. Ecology,2001,82(6): 1521-1534.   
[65] 马久,袁帅,郭乾伟,等.典型草原啮齿动物群落与植物群落相 关性分析[J].草原与草业,2021,33(3):28-35.[Ma Jiu,Yuan Shuai, Guo Qianwei, et al. Correlation analysis of main populations ofrodentcommunitiesand plantcommunitiesunderdiferentgrazing disturbance in typical steppe[J]. Grassland and Prataculture, 2021, 33(3): 28-35.]   
[66] 张军,葛庆征,张卫国,等.植被性状与高原酚鼠栖息地适合度 的关系[J].草业科学,2011,28(5):836-840.[Zhang Jun,Ge Qingzheng，Zhang Weiguo，et al.Correlations between vegetation properties and fitness of Plateau Zoker habitat[J].Prataculltural Science,2011,28(5): 836-840.]   
[67] 边疆晖,樊乃昌,景增春,等.高寒草甸地区小哺乳动物群落与 植物群落演替关系的研究[J].兽类学报,1994(3):209-216.[Bian Jianghui,Fan Naichang,Jing Zengchun,et al.Studyon the succession relationship between small mammal community and plant community inalpinemeadow area[J].Acta Theriologica Sinica, 1994(3): 209-216. ]   
[68] 岳健,穆桂金,唐自华,等.基于NDVI的新疆荒漠地区植被覆 盖度遥感估算经验模型研究[J].干旱区地理,2020,43(1):153- 160.[Yue Jian, Mu Guijin,Tang Zihua,et al. Remote sensing estimation models for vegetation coverage in desert regions of Xinjiangbased on NDVI[J].Arid Land Geography,2020,43(1):153- 160.]   
[69] 姜萍,丁文广,肖静,等.新疆植被NPP及其对气候变化响应的 海拔分异[J].干旱区地理,2021,44(3):849-857.[Jiang Ping, Ding Wenguang,Xiao Jing,et al. Altitudinal difference of vegetation NPPand itsresponsetoclimatechangein Xinjiang[J].Arid Land Geography,2021, 44(3): 849-857.]   
[70] 李杨,刘艳,马丽,等.天山北坡气候因子对植被影响的空间分 异性研究[J].干旱区资源与环境,2011,25(7):91-95.[Li Yang, Liu Yan,Ma Li, etal. Spatial variation of the vegetation effected by climatic factors in the north slope of Tianshan Mountains[J]. Journal of Arid Land Resources and Environment,2O11,25(7): 91-95.]   
[71] 陈云浩,李晓兵,史培军.基于遥感的NDVI与气候关系图式研 究[J].中国图象图形学报,2002(4):2-25,107.[Chen Yunhao, Li Xiaobing,Shi Peijun.The image forms of correlation betwen NDVI and climate factors in China using remotely sensed data[J]. Journal of Image and Graphics,2002(4): 22-25,107.]   
[72] 钟文勤,樊乃昌.我国草地鼠害的发生原因及其生态治理对策 [J].生物学通报,2002,37(7):1-4.[Zhong Wenqin,FanNaichang Causes of grassland rodent damage and its ecological control countermeasures in China[J]. Buletinof Biology,2002,37(7): 1-4.]   
[73] Li G L, Yin BF, Wan X R, et al. Successive sheep grazing reduces population densityof Brandt’svoles insteppe grasslandbyaltering food resources: A large manipulative experiment[J]. Oecologia, 2016,180(1): 149-159.

[74]袁帅,付和平,武晓东,等.基于结构方程模型分析荒漠啮齿动 物优势种对不同放牧干扰的响应[J].生态学报,2017,37(14): 4795-48O6.[Yuan Shuai,Fu Heping,Wu Xiaodong,et al.Response of dominant desert rodent species to grazing disturbances: A structural equation modeling analysis[J].Acta Ecologica Sinica, 2017, 37(14): 4795-4806.]

[75] 罗泽珣,陈卫,高武,等.中国动物志,兽纲第六卷啮齿目下册（仓鼠科)[M].北京:科学出版社,2000:325-329.[Luo Zexun,ChenWei,Gao Wu,etal.Fauna Sinica,Mammalia Vol.6Rodentia

Part II: Cricetidae[M].Beijing: Science Press,200O:325-329.]   
[76]李俊,阿布力米提·阿不都卡迪尔.红尾沙鼠(Meriones libycus)的 年龄鉴定及种群年龄组成[J].干旱区研究,2007,24(1):43-48. [Li Jun,Abudukadier Abulimiti. Study on the age identification and the population age composition of Meriones libycus[J].Arid Zone Research,2007,24(1): 43-48.]   
[77]Randall JA,Konstantin R,ParkerPG,et al.Flexible social structure ofa desert rodent,Rhombomys opimus:Philopatry,kinship,and ecological constraints[J]. Behavioral Ecology,20O5(6): 961-973.

# Spatiotemporal distribution of rat population density in grassland on the north slope of Tianshan Mountains based on Cubist model

PAN Qun12，SHI Haiyang2,，ZHANG Wenqiang2，LUO Geping234，CHEN Chunbo $^ { 2 , 3 }$

(1.College ofResoucesandEnvironmentalSiences,XinjiangUniversityUrumqi3046,Xijiang,Cina;.tateKey Laboratoryof DesertandOasis Ecology,Xinjiang Instituteof EcologyandGeography,Chinese AcademyofSciencesUrumqi 830011,Xinjiang,China;3.UniversityofChineseAcademyofSciences,BeijingOo049,China;4.CentralAsiaCenterfor Ecology and Environmental Research Center, Chinese Academy of Sciences,Urumqi 830011,Xinjiang,China)

Abstract:Rodent damage is an important factor afecting grassland ecological health.Understanding the spatiotemporal distribution characteristics of small rodent population density is crucial for accurate comprehensive rodent control. Previous studies on the spatiotemporal distribution of smal rodents were mostly limited to static site distribution or time change analysis of small-scale population density; investigation on the population density change ofsmallrodents ona large temporal and spatial sale is lacking.In this study,the field survey information of small-scale active burrow entrance densities on the grassland on the north slope of Tianshan Mountains from 1982 to 2015 was collcted from the literature and combined with environmental variable data. The study area was divided as areas with elevation of $\leqslant 9 0 0 \ \mathrm { m }$ and ${ > } 9 0 0 \ \mathrm { m }$ .The spatiotemporal distribution of active burrow entrance densities was analyzed using the Cubist and random forest (RF） models.The following results were obtained.(1) From 1982 to 2015,the active burrow entrance densities increased in the area with an elevation of $\leqslant 9 0 0 \mathrm { ~ m ~ }$ on the north slope of Tianshan Mountains,whereas that in the area with an elevation of ${ > } 9 0 0$ （204号 m decreased. The fiting accuracy of the Cubist model of active burrow entrance densities and environmental factors was beter than that of the RF model. (2)Vegetation status,meteorological factors,and grazing intensity were found to be the primary environmental driving factors for the spatiotemporal distribution of active burrow entrance densities on the north slope of Tianshan Mountains.Significant differences in the driving mechanism of active burrow entrance densities were found between the aras with an elevation of $\leqslant 9 0 0 \ \mathrm { m }$ and those with an elevation of ${ > } 9 0 0 \ \mathrm { m }$ on the north slope of Tianshan Mountains. (3) The main factor affecting the spatiotemporal distribution of active burrow entrance densities was the leaf area index and normalized diference vegetation index for the areas with elevation $\leqslant 9 0 0 \mathrm { ~ m ~ }$ and ${ > } 9 0 0 \mathrm { ~ m ~ }$ ，respectively. This difference may be affected by the consumption of different types of vegetation by gerbils (Rhombomys opimus）and yellow rabbit tail rats (Eolagurus luteus).

Key words:active burrow entrance densities； environmental factors; Cubist model; random forest model; northern slope of Tianshan Mountains