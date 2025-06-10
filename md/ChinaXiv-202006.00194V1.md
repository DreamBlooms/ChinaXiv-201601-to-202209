# 常见遥感干旱监测指标在哈萨克斯坦的一致性分析

孙博¹，钱静¹，陈曦1²，邢秀为'，周启鸣1,3（1．中国科学院深圳先进技术研究院,广东 深圳518055；2．中国科学院中亚生态与环境研究中心,新疆 乌鲁木齐830011；3．香港浸会大学地理系,中国香港 九龙塘)

摘要：利用主被动微波卫星(SMAP)土壤含水量数据，从相同空间尺度上对比了全球在运行系统中3种常见遥感干旱指数[距平植被指数(AVI)、植被健康指数(VHI）、植被供水指数(VSWI)]在哈萨克斯坦农业干旱监测上的一致性。通过皮尔森相关系数 $( r )$ 和肯德尔秩相关系数 $( \tau )$ ,分别检验干旱指数与土壤含水量及其在干旱等级判断上的相关性,以评估遥感在哈萨克斯坦作物生长季中后期干旱监测中的适用性。结果表明：不同干旱指数在该地区一致性不高。基于植被状况的遥感干旱指数与土壤含水量相关性较低,而结合植被和地表温度的综合指数具有显著正相关。不同土层比较上，VSWI指数与作物根区( $0 \sim 1 0 0 \ \mathrm { c m }$ )土壤含水具有较强相关性( $_ { r > 0 . 6 ) }$ ，表明其对植物生长季中后期的土壤含水状况有较好的响应能力。

关键词：遥感干旱指数；SMAP；土壤含水量；一致性分析；哈萨克斯坦

干旱是水分收支与供求不平衡出现水分短缺的现象，同时也是对农业影响最为严重的自然灾害之一。中亚地区是“一带一路”建设的核心区域。哈萨克斯坦是中亚国土面积第一大国，是“丝绸之路经济带”重要节点国家，北临俄罗斯，东与我国新疆接壤,战略地位十分显著。作为传统农业大国，哈萨克斯坦是世界上最大的小麦面粉出口国和第6大粮食出口国，也是我国粮食储备重要的战略合作伙伴。由于哈萨克斯坦地处中亚内陆干旱区，水资源短缺，频繁发生的农业旱灾成为影响该国经济发展的重要掣肘，同时也会导致国际粮食价格大幅波动。作为全球重要的小麦产区，哈萨克斯坦被联合国粮农组织（FAO)列入全球干旱重点监测地区。

国际上对干旱的分类包括：气象干旱、农业干旱、水文干旱、社会经济干旱等。对于干旱事件的监测，传统方法主要依赖地面观测及气象观测数据。由于气象站点稀疏，对旱情监测的准确性和及时性明显不足。另外，根据气象数据分析的是气象层面的干旱，而气象干旱是否导致了农业灾害无法确切得知[1]。随着遥感技术的发展,通过遥感数据观测植物生长状况以及叶片冠层温度，由此间接反映土壤含水量状况是目前开展大范围农业干旱监测的常

见手段[2] 。

遥感监测农业干旱多从土壤湿度以及作物需水状况角度开展。前者包括热惯量法、微波监测法等，后者包括作物形态和冠层温度监测等方法。从技术发展上看，干旱监测手段由以往单一指标逐渐向多源、综合指标监测方向发展[3-6]。根据干旱监测原理和不同指数近似关系，有学者将遥感干旱指数分为：土壤水分变化、植被形态及绿度变化、冠层温度变化、植被水分变化[7]。由于地域性差异以及不同作物响应干旱程度的不同，目前尚不存在一种遥感模型能够适用于所有地区、所有状况下的干旱监测[8]

学者对遥感干旱监测的地域有效性做了大量分析。韩宇平等[9利用中国海河地区历史资料，选取特定年份干旱事件与干旱指标结果对比的正确率,验证年际尺度干旱指数的适用性。牟伶俐等[0]对比了山西和山东地区地面测量土壤湿度和气象卫星遥感干旱监测指数之间的相关性。杨鹏等["]利用土壤熵情数据和3种遥感干旱监测模型的相关性验证，分析遥感干旱指数在河北地区的适用性。李新尧等[12]利用月尺度气象降水数据对比滞后植被状况指数，验证遥感指数在陕西农业干旱上的有效性，较弱的两者相关性证实气象干旱和农业干旱存在一定差别。Shahabfar等[13]利用相关性分析,对比了4个遥感指数和5个水平衡参数，分析遥感指数在伊朗不同气候区的适用性。张宏民等[14]在苏丹干旱地区应用 $2 5 ~ \mathrm { k m }$ 分辨率AMSR-E土壤湿度数据验证了其与3种遥感干旱指数的相关性。Dubovyk 等[15]利用 $0 . 5 ^ { \circ }$ 空间分辨率月度标准气象指数以及 $1 ~ \mathrm { k m }$ 植被健康指数产品，分析了与MODIS-EVI植被条件下干旱指数在哈萨克斯坦地区的一致性。从上述各地区验证工作来看，针对遥感干旱监测模型的地域有效性，国内外学者常利用多元统计方法（统计相关），分析干旱指数与作物生长环境的显著性及相对误差值来评价指标的区域适应性[16]。常见验证数据包括微波反演土壤湿度、地面实测土壤情数据以及气象降水资料等。

目前，针对包含哈萨克斯坦小麦种植区的全球粮食主产区，世界主要经济体中国和美国均开发有多种基于遥感参数的干旱监测系统，例如：中国CropWatch全球农作物产区干旱监测系统、美国国家海洋和大气管理局(NOAA)全球农业干旱监测系统等[17]。为保证干旱监测模型在全球具有广泛适用性,运行平台中采用了多种较为通用的遥感干旱指标，例如植被状况指数（VCI）、植被健康指数(VHI)等。由于全球性的干旱指标在地区级干旱监测中依然存在较大差异[18],因此,对于遥感干旱指标在特定地区，特别是中亚干旱地区农业干旱监测中的适用性评估十分关键。

由于中亚地区特殊的历史及经济等原因，较为缺乏气象站点和地面实测数据，难以通过传统地面嫡情数据验证遥感干旱指数的有效性。而微波遥感土壤含水量测量具有覆盖范围广、面上观测等优势。本文采用主被动微波SMAP反演土壤含水量数据，在相同空间尺度上，对比分析目前全球在运行的干旱监测系统中几种典型遥感指数与微波反演土壤含水量的相关性，以评估基于植被一温度的遥感干旱监测模型对中亚地区地表湿度干旱状况的响应能力，为“一带一路”中亚主产作物区的农情监测预警系统有效性评估，以及相关参数的选取提供依据。

# 研究区概况

本文选择哈萨克斯坦北部3州作为研究区，包括：科斯塔奈州、北哈萨克斯坦州、阿克莫林州（图1)。研究区属于典型大陆性气候，冬季严寒、夏季干燥炎热，年均降水量 $3 0 0 ~ \mathrm { m m }$ 左右。该区域土地覆盖以耕地为主， $9 5 \%$ 以上耕地均种植小麦。由于农作物种植结构单一，减少了不同作物对干旱指数响应差异造成的影响，是分析不同干旱指数与土壤含水量相关性的绝佳区域。

# 2研究方法

利用MODIS产品数据集构建基于可见光一热红外的遥感干旱指数模型，对比SMAP主被动微波量测的土壤含水量状况，通过皮尔森相关系数 $( r )$ 和肯德尔秩相关系数 $( \tau )$ 检验两者相关性，以评估不同干旱指数对土壤含水状况响应的一致性。

![](images/8b4ff5b7e28571e76baec252009f7fc9230d5aadba4e9369b155ece9f9f7e64d.jpg)  
图1研究区地理位置示意图及植被覆盖情况(2015年)  
Fig.1Location of the study area and vegetation coverage（2015)

# 2.1 数据选取及预处理

由于不存在针对所有情况下的干旱监测指数，常见“植被一温度”干旱指标主要针对作物生长季中后期，即植被覆盖率较高情况下的干旱监测。因此，采样时间上，选择研究区作物生长季中后期6月下旬数据。遥感干旱指数采用MODIS 相邻8d合成产品参与计算，以减少数据质量及云层遮挡造成数据缺失等问题。采用数据包括：植被指数NDVI产品MOD13A2（ $1 \ \mathrm { k m } \ \times \ 1 \ \mathrm { k m } \ \rangle$ 和地表温度LST产品MOD11A2( $1 \ \mathrm { k m } \ \times \ 1 \ \mathrm { k m } ,$ 。为了分析植被、温度同期状况和距平值等指标，同时采用了MODIS全时间序列（2000—2018年）的同期数据用于历史状况分析。

土壤含水量数据采用同期SMAP主被动微波遥感土壤含水量监测L4级产品数据SPL4SMGP（9$\mathrm { k m } \ \times \ 9 \ \mathrm { k m }$ )。该数据由主动微波雷达和被动微波辐射计数据经过协同综合得到。SMAP是美国航空航天局(NASA)于2015年最新发射全球首个针对土壤含水量探测的卫星，同时搭载了被动和主动微波传感器(L波段的辐射计和雷达）。SMAP任务的目的是了解地球水、能量和碳循环之间的关联性，并提升监测和预测诸如洪水、干旱等自然灾害的能力。通过结合主被动微波传感器测量的结果，SMAP提供全球9$\mathrm { k m }$ 空间分辨率的土壤含水量数据，为高空间分辨率土壤含水量以及全球干旱状况监测提供了有力的工具。据测算，SMAP测量土壤含水量的精度在全球多个地区达到设计目标（均方根误差，RMSE $< 0 . \ 0 4$ $\mathrm { c m } ^ { 3 } \cdot \mathrm { c m } ^ { - 3 }$ ),具有较高的可信度[19-20]。另外,在同属中亚干旱区中国西北的地面验证工作表明，SMAP在干旱半干旱地区对土壤含水量反演精度RMSE为$0 . 0 3 2 ~ \mathrm { c m } ^ { 3 } \cdot \mathrm { c m } ^ { - 3 [ 2 1 ] }$ ,同样具有稳定的可靠性。

辅助数据包括基础矢量数据、同期MODIS全球土地利用与覆盖分类产品数据MCD12C1。为保证数据在相同空间分辨率上的可比性，所有MODIS产品采用像素平均，将空间分辨率重采样到与SMAP数据保持一致。

# 2.2遥感干旱指数

从目前全球在运行的干旱监测系统中选取常见的遥感指数,包括:距平植被指数（AVI)[22]、植被供水指数（VSWI)[23]、植被健康指数（VHI）[24]。从遥感监测干旱原理角度，分别代表了“作物形态和绿度”“植被水分变化”“冠层温度变化”这几大类别干旱指数[7]。由于模型构建简单、参数易于获取、适

# 表1在运行系统常见遥感干旱指数及计算公式

Tab.1 Selected remote sensing drought indices and calculation formulas   

<html><body><table><tr><td>指数名称</td><td>计算公式</td></tr><tr><td>距平植被指数(AVI)</td><td>AVI= NDVI,-NDVI</td></tr><tr><td>植被供水指数(VSWI)</td><td>VSWI= NDVI/LSTi</td></tr><tr><td>植被健康指数(VHI)</td><td>VHI=a×VCI+（1-a）× TCI</td></tr></table></body></html>

注： $\mathrm { N D V I } _ { i }$ 和 $\mathrm { L S T } _ { i }$ 分别为时刻 $\mathbf { \chi } _ { i }$ 植被指数和地表温度； $\overline { { \mathrm { N D V I } } }$ 为植被指数的多年同期平均值；VCI和TCI分别为植被状况指数和温度状况指数，VCI= $\mathrm { V C I } = \frac { \mathrm { N D V I } _ { i } - \mathrm { N D V I } _ { \operatorname* { m i n } } } { \mathrm { N D V I } _ { \operatorname* { m a x } } - \mathrm { N D V I } _ { \operatorname* { m i n } } }$ NDVI-NDVI;TCI=S $\mathrm { N D V I } _ { \operatorname* { m i n } }$ ，$\mathrm { \Delta N D V I _ { \mathrm { m a x } } }$ 分别为同一地点植被指数多年同期最小值和最大值;$\mathrm { L S T _ { \mathrm { m i n } } }$ ， $\mathrm { L S T } _ { \operatorname* { m a x } }$ ,分别为同一地点地表温度多年同期最小值和最大值。$\mathbf { \Delta } _ { a }$ 为VHI调整系数(0.5）。

用性强，上述指标在全球范围的干旱监测中均有广泛应用。指数的计算公式如表1。

# 2.3 相关性分析

利用皮尔森相关系数 $( r )$ 分析不同遥感干旱指数与SMAP土壤含水量之间的相关性，并建立与不同土层土壤含水量之间的相关矩阵。皮尔森相关系数 $( r )$ 的计算如公式（1），其取值范围为-1，1」。相关系数的绝对值越大，两组数据相关性越强。当相关系数为1时，表现完全正相关；当相关系数为-1时，表现完全负相关;相关系数越接近于0,相关性越弱。

$$
r = { \frac { \displaystyle \sum _ { i = 1 } ^ { n } ( X _ { i } - { \overline { { X } } } ) ( Y _ { i } - { \overline { { Y } } } ) } { \displaystyle { \sqrt { \sum _ { i = 1 } ^ { n } ( X _ { i } - { \overline { { X } } } ) ^ { 2 } } } { \sqrt { \sum _ { i = 1 } ^ { n } ( Y _ { i } - { \overline { { Y } } } ) ^ { 2 } } } } }
$$

式中： $X _ { i }$ 表示样本 $i$ 遥感干旱指数的取值； $\overline { { \boldsymbol X } }$ 为遥感干旱指数样本平均值; $Y _ { i }$ 为样本 $\mathbf { \chi } _ { i }$ 土壤含水量的取值； $\overline { { Y } }$ 为土壤含水量样本平均值; $n$ 代表样本数。

此外，在干旱程度分级基础上，利用肯德尔秩相关系数 $( \tau )$ 分析遥感干旱指数与土壤湿度对于干旱等级表现上的相关性。肯德尔相关系数 $( \tau )$ 的计算如公式(2），其取值范围为[-1，1]，含义表达与皮尔森相关系数相同。

$$
\tau \_ b = \frac { n _ { \mathrm { c } } - n _ { \mathrm { d } } } { \sqrt { \left( n _ { 0 } - n _ { 1 } \right) \left( n _ { 0 } - n _ { 2 } \right) } }
$$

式中： $\begin{array} { r } { n _ { 0 } = n \big ( n - 1 \big ) / 2 , n _ { 1 } = \sum _ { i } t _ { i } \big ( t _ { i } - 1 \big ) / 2 , n _ { 2 } = \sum _ { j } u _ { j } } \end{array}$ $( u _ { j } - 1 ) / 2 ; n _ { c }$ 为测试数据两组一致的对数; $n _ { \mathrm { d } }$ 为两组不一致的对数； $n _ { 1 }$ 针对遥感干旱指数等级; $i$ 表示遥感干旱指数等级中具有相同取值集合的个数; $t _ { i }$ 表示第 $i$ 个相同取值集合中包含的元素个数; $n _ { 2 }$ 针对土壤湿度干旱等级数据计算，计算过程与 $n _ { 1 }$ 计算方式相似。

# 3 实验结果

# 3.1遥感指数与土壤含水量的相关性

由于大部分遥感干旱指数主要针对地表具有植被覆盖情况下的干旱监测，无植被覆盖的荒漠区会有较大偏差。因此，根据已有同期2015年MODIS土地利用与覆盖分类数据（MCD12C1），利用ArcGIS空间领域分析，选取分析尺度下完全属于植被覆盖的样本点作为分析样点，以剔除研究区内其他地物类型(如裸露地、水体、建成区等)对分析结果的影响。据此，研究区范围共选出2650余个样本点，采样时间为该地区作物生长季中后期(2015年6月26日）。图2显示了AVI、VSWI、VHI等指标与 $0 \sim 1 0$ cm表层土壤以及 $0 \sim 1 0 0 \ \mathrm { c m }$ 作物根区土壤体积含水量的散点关系图，干旱指数与土壤含水量相关性分析结果见表2。

![](images/651d43dc8929deb5ea3636d0f21205df7b9ada927a81bdb7fa9ba8029f8693f7.jpg)  
图2遥感干旱指数与不同土层土壤含水量相关性散点图  
Fig.2Scatter plots of remote sensing drought indices against soil moisture measures

# 表2遥感干旱指数与不同土层土壤含水量相关性矩阵(Pearson'sr)

Tab.2Correlation matrix among different remote sensing drought indices and SMAP soil moisture(SM) by soil layer(Pearson's r)   

<html><body><table><tr><td></td><td>AVI</td><td>VSWI</td><td>VHI</td><td>SM(0~10 cm)</td><td>SM(0 ~100 cm)</td></tr><tr><td>AVI</td><td>1</td><td>0.34</td><td>0.73</td><td>0.03 *</td><td>0.11</td></tr><tr><td>VSWI</td><td></td><td>1</td><td>0.62</td><td>0.48</td><td>0.62</td></tr><tr><td>VHI</td><td></td><td></td><td>1</td><td>0.35</td><td>0.29</td></tr><tr><td>SM(0 ~10 cm)</td><td></td><td></td><td></td><td>1</td><td>0.54</td></tr><tr><td>SM(0~100 cm)</td><td></td><td></td><td></td><td></td><td>1</td></tr></table></body></html>

注： $*$ 表示未通过显著性测试( $P > 0 . 0 5$ )，SM代表土壤含水量。

结果显示，不同遥感干旱指数监测结果并非一致。其中，VHI与另两种指数一致性较好，而 AVI与VSWI一致性不高。与微波反演土壤含水量数据相比，VSWI与土壤含水量显著正相关，并且与深层土壤含水量相关性更高( $_ { ( r > 0 . 6 ) }$ 。VHI与土壤含水量也存在显著正相关，但相关性较弱。此外，AVI与土壤表层含水量并未通过显著性检验( $\textstyle P > 0 . 0 5 )$ ，表明其与土壤表层含水量不存在显著相关性。

# 3.2遥感指数表现干旱程度上的一致性

根据广泛采用的干旱等级划分标准[22,25],对AVI、VHI进行干旱分级，干旱状况可分为：湿润/适宜、发生干旱、中度干旱、严重干旱。由于VSWI不存在统一的干旱分级标准，且缺乏地面参数校对，因此，本文不对VSWI分级进行比较。对于土壤含水量的干旱分级，在缺少研究区土壤情调查资料情况下，本文参考具有相似地理环境、土壤状况以及同为小麦种植区的中国新疆地区，参照国标《农业干旱分级标准》（GB/T32136-2015）[26]要求（ $( 0 \sim 1 0 0$ cm 土层含水量状况)进行土壤湿度的干旱分级。表3显示了基于遥感指数VHI、AVI以及土壤含水量的干旱分级的等级相关一致性分析结果。

# 表3遥感指数干旱等级与土壤湿度干旱等级的相关性(Kendall's $\cdot$ ）

Tab.3Rank correlation（Kendall's $\cdot$ ）betweenremote sensing drought indices and SMAP soil moisture   

<html><body><table><tr><td>干旱等级</td><td>土壤含水量/%</td></tr><tr><td>AVI干旱等级</td><td>-0.03 *</td></tr><tr><td>VHI干旱等级</td><td>0.21</td></tr></table></body></html>

注： $*$ 表示未通过显著性测试( $\textstyle P > 0 . 0 5$ ）。

对干旱程度的判断上，常见遥感干旱指数与微波土壤含水量对干旱等级的判断存在明显差异。其中，AVI干旱分级与土壤含水量干旱等级的相关性并不显著，而VHI干旱分级与土壤含水量干旱等级呈现弱的正相关关系。说明综合了植被状况和温度的干旱监测指数优于仅依赖植被状况对干旱的判断，与皮尔森相关性检测得到的结论相似。

# 4分析与讨论

目前，遥感干旱指数研究较多，但针对中亚农业国家干旱遥感监测的有效性研究较少。为了测试遥感十旱指数的区域有效性，不同学者根据数据的限制采用了不同的方法，例如：用地面量测的土壤情数据、用气象站点观测的降水数据，以及由降水数据派生的气象干旱指标数据开展验证。由于遥感监测干旱的原理是通过植被状况来反映土壤含水量，而非直接反映大气降水。因此上述验证方案中利用气象降水数据、气象十旱指标等方法属于间接验证方法,其可靠性上略显不足。通常而言，与土壤含水量参数进行直接比较具有较高可信度。然而，传统方法中基于站点测量的土壤含水量是“点”数据，无法代表一定区域内的土壤含水量真实状况[27],并且通常考虑成本因素，地面测量样本点较少，缺少广泛地区代表性，属于小样本验证。此外，用“点”数据验证遥感“面”数据，空间尺度上的不一致，会导致评价准确性的偏差[28]。由于点验证存在时空不匹配、缺乏连续空间代表性等不足，前人基于地面实测的验证结果可以看到，遥感干旱指数与地面实测土壤含水量相关性测度指标通常较低[29-31]。

中亚哈萨克斯坦地区因历史、经济等因素，缺少地面实测土壤含水量数据以及相应监测条件。考虑到验证数据空间尺度的一致性，本研究利用SMAP主被动微波土壤含水量数据，对比了遥感干旱指数与土壤含水量的一致性，证实遥感干旱指数与土壤含水量存在正相关。需要指出的是，即便参考地面实测土壤含水量数据，也仅仅是一致性趋势上的解释。对遥感干旱指数的解释，除了水分因素，同时受其他因子，如温度、辐射通量等影响。

大量研究表明，作物生长季中后期的灌浆期、成熟期与产量直接相关，是农业干旱监测关键时期。同时，大部分遥感干旱指数主要针对于地面有较高植被覆盖的情况，生长季后期，遥感监测干旱有效性越来越高[32]。就本研究案例而言,作物生长季中后期从6月下旬到8月。但由于SMAP主动微波传感器(L波段雷达)在2015年7月7日之后出现故障，故采样数据选取了2015年6月下旬SMAP数据进行分析和比较。

有学者利用中国区MODIS数据（2009年4月7日)测试多个指数之间的相关性[7],表明不同遥感干旱指数对农业干旱的描述并非完全一致。本研究结果证实，在哈萨克斯坦作物种植区遥感干旱指数之间存在不一致性。其中，利用植物生长状况（如AVI指数)反映土壤含水量的相关性不高。在现有干旱监测系统中，该指数可用于评估干旱灾害发生时的影响范围，但无法用于干旱预警。而VHI、VSWI等结合了植被指数与地表温度指标对土壤含水量的反馈更加敏感。由于中亚干旱地区主要受水分和温度限制，依据植被指数与地表温度在干旱区呈现的负相关关系，采用NDVI-LST综合指数监测干旱不失为一种更加有效的方法。从不同土壤深度的比较上，植被供水指数（VSWI）与作物根区的土壤含水量( $0 \sim 1 0 0 ~ \mathrm { c m } )$ 较之表层土壤 $\left( 0 \sim 1 0 \ \mathrm { c m } \right)$ 体现了更高的一致性。对干旱等级的判断上，因受限于所选干旱指数的类型，整体上遥感指数与土壤含水量干旱等级的一致性不高。另一方面，就不同地区的植被状况而言，现有干旱监测系统中采用全球一致的固定阈值干旱等级划分方案也会存在一定误差。

# 5结论

针对现有在运行的全球干旱监测系统监测结果，本文利用SMAP主被动微波反演土壤含水量数据，从统一的空间尺度上，对比分析了研究区小麦生长季中后期遥感干旱指数的一致性，并通过两种相关性验证手段，利用大量空间样本检验了典型遥感干旱指数与土壤含水状况的相关性，以评估遥感指数在哈萨克斯坦农作物干旱监测中的适用性。分析结论如下：

（1）从统一的空间尺度上证实遥感干旱监测指标与土壤含水量之间存在显著相关性。（2）相较于单一植被状况指数，综合“植被—温度"的干旱监测指标(如VHI、VSWI)与土壤含水量在本研究区具有更好相关性，对地表干旱状况的表征有一致性趋势，体现了高植被覆盖下“植被一地温”指数对干旱状况的敏感性。(3）考虑干旱区对水分的依赖，植被供水指数(VSWI)对于作物根区（ $0 \sim 1 0 0 ~ \mathrm { c m } ,$ 土壤含水状况的响应高于对土壤表层 $( 0 \sim 1 0 \ \mathrm { c m } ) \$ 的响应。

未来研究工作拟根据生长季不同时期植被覆盖情况开展时间上更加细化的分析，便于针对性选取合适的干旱监测指数，为中亚干旱区农业干旱监测预警以及提高作物估产的准确性提供帮助。

# 参考文献(References）：

[1］李红梅,李林,李万志.气象干旱监测指标在青海高原的适用性分析[J].干旱区研究,2018,35（1）：114-121.［LiHongmei，

LiLin,Li Wanzhi.Applicability of meteorological drought indices in drought monitoring in the Qinghai Plateau[J].Arid Zone Research,2018,35（1） :114 -121.]

[2]柳钦火,辛景峰,辛晓洲,等.基于地表温度和植被指数的农业 干旱遥感监测方法[J].科技导报,2007,25(6):12－18.[Liu Qinhuo,Xin Jingfeng,Xin Xiaozhou,etal.Monitoringagricultural drought by vegetation index and remotely sensed temperature[J]. Science & Technology Review,2007,25(6）:12-18.] [3]Kogan F N. Operational space technology for global vegetation assessment[J].Bulleinof theAmerican MeteorologicalSociety,   
2001,82(9) :1949-1964. [4］王鹏新,龚建雅,李小文.条件植被温度指数及其在干旱监测 中的应用[J].武汉大学学报（信息科学版）,2001,26（5）：412 -418.[Wang Pengxin,Gong Jianya,Li Xiaowen.Vegetation-temperature condition index and itsapplication for drought monitoring [J].Geomatics & Information Science of Wuhan University,2001,   
26(5):412 -418.] [5]Sandholt I,Rasmussen K,Andersen J.A simple interpretation of the surface temperature/vegetation index space for assessment of surface moisture status[J].Remote Sensing of Environment,2002,   
79(2) :213 - 224. [6]Liu X,Zhu X,Pan Y,et al.Agricultural drought monitoring:Progress,challenges,and prospects[J]. Journal of Geographical Sciences,2016,26(6) :750 - 767. [7］孙灏,陈云浩,孙洪泉.典型农业干旱遥感监测指数的比较及 分类[J],农业工程学报,2012,28（14）：147-154.[Sun Hao, Chen Yunhao,Sun Hongquan. Comparisons and classification system of typical remote sensing indexes for agricultural drought[J]. Transactions of the Chinese Societyof Agricultural Engineering （Transactions of the CSAE）,2012,28(14）:147-154.] [8］王俊霞,朱秀芳,刘宪锋,等.基于多源遥感数据的旱情评价研 究——以河南省为例[J].国土资源遥感，2018,30(1)：180-   
186.[Wang Junxia,Zhu Xiufang,Liu Xianfeng,et al. Research on agriculture drought monitoring method of Henan Province with multi-sources data[J]. Remote Sensing for Land & Resources,   
2018,30(1) :180 -186.] [9］韩宇平,马海娇,严登华.典型干旱指标在海河流域的适用性 评价[J].华北水利水电大学学报（自然科学版）,2016,37 (1）:6-14.[Han Yuping,Ma Haijiao,Yan Denghua.Applicability evaluation of typical drought indexes in the Haihe River Basin [J]. Journal of North China University of Water Resources and Electric Power（Natural Sciences Edition）,2016,37（1）:6 -14.] [10］牟伶俐,吴炳方,闫娜娜,等.农业旱情遥感指数验证与不确定 性分析[J].水土保持通报,2007,27（2）:119-122.[Mu Lingli,Wu Bingfang,Yan Nana,et al.Validation of agricultural drought indices and their uncertainty analysis[J].Bulletin of Soil and Wa

ter conservation,2007,27(2）:119-122.][11］杨鹏,李春强,高祺,等.多种干旱遥感监测模型在河北地区的适用性研究[J].江苏农业科学，2018，46（16）：231-237.[Yang Peng,Li Chunqiang,Gao Qi,etal.Applicabilityof variousdrought remote sensing monitoring models in Hebei Province[J].Agricultural Science of Jiangsu,2018,46(16）:231-237.]

[12］李新尧,杨联安,聂红梅,等.基于植被状态指数的陕西省农业 干旱时空动态[J].生态学杂志，2018,37（4）：1172-1180.［Li Xinyao,Yang Lian'an,Nie Hongmei,et al.Assessment of temporal and spatial dynamics of agricultural drought in Shaanxi Province based on vegetation condition index[J].Chinese Journal of Ecology,2018,37(4):1172-1180.]

[13]Shahabfar A,Eitzinger J.Agricultural drought monitoring in semiarid and arid areasusing MODIS data[J].The Journal of Agricultural Science,2011,149(4) :403-414.

[14］张宏民,赵书河，陈诚,等.苏丹遥感干旱指数及其适用性[J]. 遥感信息,2016,31（4）:48-55.［Zhang Hongmin,Zhao Shuhe, Chen Cheng,et al.Adaptability of remote sensing drought index in Sudan[J].Remote Sensing Information,2016,31(4）:48-55.] [15]Dubovyk O,Ghazaryan G,Javier González,et al.Drought hazard in Kazakhstan in 200O -2016:A remote sensing perspective[J].Environmental Monitoring and Assessment,2O19,191:510.

[16]黄友昕，刘修国，沈永林，等.农业干旱遥感监测指标及其适应性评价方法研究进展[J].农业工程学报，2015,31（16)：186-195.［Huang Youxin,Liu Xiuguo,Shen Yonglin,et al.Advances inremote sensing derived agricultural drought monitoring indices andadaptability evaluation methods[J].Transactions of the ChineseSociety of Agricultural Engineering,2015,31（16）:186-195.][17］王芝兰，周甘霖,张宇,等.美国干旱监测预测业务发展及其科学挑战[J].干旱气象,2019,37（2）：183-197.[Wang Zhilan,Zhou Ganlin,Zhang Yu,etal.Progresses and challenges on droughtmonitoring and forecast in the United States[J].Journal of AridMeteorology,2019,37(2) :183-197.]

[18］牟伶俐.农业旱情遥感监测指标的适应性与不确定性分析 [D].北京：中国科学院遥感应用研究所,2006.［MuLingli Suitability and Uncertainty Analysisof Agricultural Drought Indicator with Remote Sensing[D].Beijing:Institute of Remote Sensing Applications,Chinese Academy of Sciences,2006.]

[19]Chan SK,BindlishR,O'Neil PE,et al.Assessment of the SMAP passive soil moisture product[J].IEEE Transactions on Geoscience and Remote Sensing,2016,54(8） :4994-5007.

[20］白瑜，孟治国，赵凯,等.像元尺度土壤水分监测网络及其对L 波段土壤水分产品的初步验证结果[J].遥感技术与应用， 2018,33(1）:78-87.［Bai Yu,Meng Zhiguo,Zhao Kai,et al. Pixel scale soil moisture monitoring network and its preliminary validation of L band soil moisture product[J].Remote Sensing

Techniques and Applications,2018,33（1） :78 -87.] [21]Ma C,Li X,WeiL,et al.Multi-scale validation of SMAP soil moisture products over cold and arid regions in Northwestern China using distributed ground observation data[J].Remote Sensing, 2017,9(4) :327.

[22］陈维英，肖乾广，盛永伟.距平植被指数在1992年特大干旱监测中的应用［J].环境遥感，1994，36（2）：106-112.［ChenWeiying,Xiao Qianguang,Sheng Yongwei.Application of anomalyvegetation index in monitoring extreme drought in 1992[J].ChinaEnvironment of Remote Sensing,1994,36(2）:106 -112.]

[23]Carlson T N,Gillies RR,Perry E M.A method to make use of thermal infrared temperature and NDVI measurements to infer surface soil water content and fractional vegetation cover[J].Remote Sensing Reviews,1994,9(1/2):161-173.

[24］Kogan F N.Application of vegetation index and brightness temperature for drought detection[J].Advances in Space Research, 1995,15(11):91-100.

[25]Food and Agriculture Organization of the United Nations（FAO）, Earth Observation-Global Indicators.http://www.fao.org/giews/ earthobservation/asis/index_2. jsp?lang $\mathbf { \sigma } = \mathbf { \sigma }$ en#vhi,2019 -11-1.

[26]中国国家标准化管理委员会.GB/T32136-2015.中华人民共和国国家标准：农业干旱等级［S].北京：中国标准出版社，2015.[Standardization Administration of theP.R.C.GB/T32136-2015.National Standard of the People's Republic of China:Ag-ricultural Drought Grade Standard［S].Beijing:China StandardPress,2015.]

[27］申晓骥，安如.欧空局主、被动微波土壤湿度产品的比较验证 [J].遥感信息,2017,32（2）:89-93.[Shen Xiaoji,An Ru. Comparative evaluation of ESA CCI active and passive microwave soil moisture products[J].Remote Sensing Information,2017,32 (2):89-93.]

[28］梁芸，张峰,韩涛.利用EOS/MODIS 植被供水指数监测庆阳地 区的土壤湿度［J].干旱气象,2007,25（1）:44－47.［Liang Yun,Zhang Feng,Han Tao.Monitoring soil humidity by using EOS/MODIS VSWI product in Qingyang[J].Arid Meteorology, 2007,25(1) :44-47.]

[29］孙丽，王飞，吴全.干旱遥感监测模型在中国冬小麦区的应用 [J].农业工程学报,2010,26（1）:243-249.[Sun Li,Wang Fei,Wu Quan.Drought monitoring by remote sensing in winterwheat-growing area of China[J].Transactions of the Chinese Society of Agricultural Engineering,2010,26(1）:243-249.]

[30］张洁,武建军，周磊，等.基于MODIS 数据的农业旱灾监测方 法对比分析[J].遥感信息,2012,27（5）：48-54.［Zhang Jie, Wu Jianjun,Zhou Lei,et al. Comparative study on remotely sensed methods of monitoring agricultural drought based on MODIS data [J].Remote Sensing Information,2012,27(5）:48-54.]

[31］宋扬，房世波，梁瀚月，等.基于MODIS 数据的农业干旱遥感 指数对比和应用[J].国土资源遥感，2017，29（2）：215-220. [Song Yang,Fang Shibo,Liang Hanyue,et al. Comparison and application of agricultural drought indexes based on MODIS data[J]. RemoteSensingforLand&Resources,2017,29(2):215-220.] [32］彭擎,王让会，蒋烨林,等.植被一地温指数(NDVI-LST)在新 疆干旱监测中的适用性[J].生态学报，2018,38（13）：4694- 4703.[Peng Qing,Wang Ranghui,Jiang Yelin,et al. Adaptability of drought situation monitor in Xinjiang with the NDVI-LST index [J].Acta Ecologica Sinica,2018,38(13）:4694-4703.]

# Consistency and comparison among remote sensing drought indices and SMAP soil moisture in Kazakhstan

SUN Bo’， QIAN Jing'，CHEN Xi $^ { 1 , 2 }$ ， XING Xiu-wei’， ZHOU Qi-ming1,3 (1.Shenzhen InstitutesofAdvanced Technology,Chinese Academy of Sciences,Shenzhen 518055,Guangdong,China; 2.Research CenterforEcologyndEnvionmentofCentralAsia,ChineseAcademyofSciences，Urumqi8ol1,Xinjiang,China; 3. Department of Geography,Hong Kong Baptist University,Kowloon Tong,Hong Kong SAR,China)

Abstract：Inorder to evaluatethe applicabilityof remote sensing drought indices for agricultural drought monitoringin thearid zone of Central Asia,several typical indices (i.e.,AVI,VHI,and VSWI）from curent global drought monitoring systems were assessed using active and passve microwave soil moisture data (SMAP).Data from late June,the middle and late period in the plant growing season,wereutilized for this experiment.Acording to datasets for existing land use and land cover,more than 2 65O samples fuly covered by vegetation were chosen.Correlations between remote sensing drought indices and soil moisture were examined using the Pearson correlation coefficient $( r )$ and Kendall rank correlation coefficient $( \tau )$ . Resultes show that AVI and soil moisture are not significantlycorrelated.However,VHIand VSWIare significantly positively correlated with soil moisture at two layers,including the surface layer ( $0 - 1 0 ~ \mathrm { c m } ^ { \cdot }$ ）and the root zone layer ( $( 0 - 1 0 0 ~ \mathrm { c m } )$ ). By comparison,VSWI exhibits a strong correlation with soil moisture at root zone level ( $r > 0 . 6$ ）,which also shows a good response to drought conditions in the middle and late stages of the growing season in Kazakhstan.For determining drought grade,VHI shows a weak positive correlation with soil moisture.

Key words: remote sensing drought index； SMAP；soil moisture;validity test； Kazakhstan