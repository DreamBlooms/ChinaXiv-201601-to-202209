# 黄土高原植被物候对季节性干旱的敏感性响应

吉珍霞¹，侯青青²，裴婷婷1，陈英1，谢保鹏³，吴华武4.5（1.甘肃农业大学资源与环境学院,甘肃 兰州730070；2.甘肃农业大学草业学院,甘肃 兰州730070;3.甘肃农业大学管理学院,甘肃 兰州730070；4.草业生态系统教育部重点实验室(甘肃农业大学)，甘肃 兰州730070；5.中国科学院南京地理与湖泊研究所,江苏 南京210008)

摘要：在全球变暖的背景下，干旱事件发生频率和强度的增加导致陆地生态系统中植被多样性发生重大变化，研究植被物候对季节性干旱的响应对保护黄土高原的生态系统具有重要意义。基于MODIS遥感归一化植被指数(MODISNDVI:MOD13Q1)数据及降水和气温逐月格点数据，采用岭回归分析方法,探讨黄土高原植被物候对季节性干旱的敏感性响应。结果表明：(1)上年夏季干旱指数（Standardized precipitation evapotranspiration index,SPEI)和上年秋季 SPEI会延迟植被生长季始期(Startof the season,SOS),年初冬季SPEI和当年春季SPEI导致植被 SOS提前。年初冬季SPEI相比于当年春季SPEI和当年秋季SPEI更容易延迟植被生长季末期(End of the season,EOS),而当年夏季SPEI会导致植被EOS提前。（2)黄土高原植被物候对季节性SPEI具有明显的空间异质性。青海境内年初冬季干旱程度减弱时，会造成植被SOS提前；当年夏季干旱程度加剧会导致黄土高原大部分植被提前结束生长。(3)黄土高原不同植被物候对季节性SPEI响应差异明显，灌木SOS相比于森林SOS和草地SOS更容易受干旱的影响，草地SOS最易受年初冬季干旱的影响。该研究可为黄土高原植被应对季节性干旱提供一定的科学依据。

关键 词：植被物候；季节性干旱；敏感性响应；黄土高原

# 文章编号：

植被物候是指生物受其所处环境(气候、水文、土壤等)影响出现以年为周期的自然现象[1-2],而干旱通常被定义为降水量低于长期平均降水量并持续很长时间的周期性自然气候事件[3]。在全球变暖的背景下[4],干旱影响着生态系统中各种植被的生长发育，而植被生产力、陆地生态系统碳储备及碳循环深受植被物候的影响[5-6]。因此,清楚地掌握不同植被物候对干旱的响应，有助于揭示干旱对陆地生态系统的影响，对减少当地生态和经济损失有重要意义[7]。

目前，国内外对干旱与植被生长关系之间的研究取得了很大进展，Zhang等认为干旱会导致植被生长减缓、生物量减少以及增加植被死亡率，而不同植被的吸水能力和水分亏缺适应策略可以决定不同植被的抗旱性和恢复能力[37],Hanson等[8]证明了根系发达的植被不易受到干旱缺水的影响。此外，不同植被对不同时间尺度的干旱表现出差异性，且不同时间尺度的干旱对不同植被的生长有明显的时滞效应和积累效应[79],即植被受到严重干旱后，需要一定的时间来修复受损的根系和恢复受干旱前的生长能力[10],而植被恢复时间的长短取决于植被生长环境和植被类型[11-12]。然而,在探索干旱对植被物候的影响过程中，大多研究采用的相关分析法认为干旱对植被物候变化产生了复杂的影响。例如，澳大利亚南部干旱年份植被生长季始期(Startof the season,SOS)没有发生变化[13],但半干旱山区植被SOS呈现了延迟趋势[14]；干旱会延迟内蒙古植被 SOS 和植被生长季末期(End of the season,

# 干吴区地理

EOS)，极端干旱会提前青藏高原植被半花期和缩短花期持续时间[15],东北地区干旱会导致草地 SOS延迟,森林SOS提前[16]。黄土高原地处中国干旱半干旱地区，是世界上分布最集中且面积最大的黄土区，以往大部分学者大多关注气候对植被生长和植被物候产生的影响，如谢宝妮等采用偏相关分析量化温度和降水对1982—2011年黄土高原植被物候的影响时，发现黄土高原物候受到降水和温度的共同调控,其中温度是主要驱动因子;吉珍霞等[18]研究黄土高原植被物候变化及其对季节性气候变化的响应时，发现黄土高原植被SOS对各季节温度的响应强于各季节降水。由此来看，黄土高原植被物候易受温度的影响。除此以外，该地区属于生态环境脆弱带，植被易受自然灾害，尤其是干旱的影响[119],持续干旱的发生容易导致植被受到水分胁迫而引发病变和死亡，从而降低植被生产力和碳储存能力[20-21],Wu等[22]研究表明该地区干旱的持续时间和严重程度均在增加，但由于干旱固有的复杂性和不确定性，以及不同植被对干旱的抵抗力和恢复力存在差异，使得季节性干旱对不同植被物候影响的研究较少。

因此，本文基于2001—2018年黄土高原植被物候(包括植被SOS、植被EOS)和季节性干旱数据，采用岭回归分析方法探讨物候对季节性SPEI的敏感性响应，旨在揭示不同植被物候对季节性干旱的响应规律，为植被应对水分胁迫和生态环境保护提供科学依据。

# 1数据与方法

# 1.1 研究区概况

黄土高原地处中国西北地区，地处 $1 0 0 ^ { \circ } 5 2 ^ { \prime }$ 2$1 1 4 ^ { \circ } 3 3 ^ { \prime } \mathrm { E } \mathrm { ~ } . 3 3 ^ { \circ } 4 1 ^ { \prime } { \sim } 4 1 ^ { \circ } 1 6 ^ { \prime } \mathrm { N }$ 之间，海拔 $8 3 { \sim } 5 0 1 0 \mathrm { ~ m }$ 。气候受经纬度和地形的双重制约，由东南湿润季风气候向西北内陆干旱气候过渡,年均温 $3 . 6 { \sim } 1 4 . 3 ~ \mathrm { ^ { \circ } C }$ 每年的太阳总辐射量 $5 . 0 { \times } 1 0 ^ { 9 } { \sim } 6 . 3 { \times } 1 0 ^ { 9 } \mathrm { J } { \cdot } \mathrm { m } ^ { - 2 }$ ，年降水量 $3 0 0 { \sim } 8 0 0 ~ \mathrm { m m }$ ，降水量从西北向东南增加，每年的潜在蒸散量远高于降水量，范围在 $8 6 5 { \sim } 1 2 7 4 ~ \mathrm { m m }$ 之间[10]。夏季是发生中旱、重旱和极旱次数最多的季节，但整个黄土高原年尺度干旱以轻度干旱为主，主要分布在陕西、山西大部分区域[23-24]。黄土高原植被受气候的影响呈东南一西北走向水平地带性分布[17],主要植被类型有森林、灌木、草地和农田,其中草地占比 $6 5 . 0 \%$ ,农田占比 $2 4 . 2 \%$ ，森林占比$6 . 2 \%$ ,灌木占比 $0 . 3 \%$ （图1）。

![](images/ff9d29bf38600c2e3b61007123bd132d4040124873417ba7fe3923c0973914c0.jpg)  
图1 2001—2018年黄土高原植被类型 Fig.1Vegetation types in the Loess Plateau from 2001 to 2018

# 1.2数据来源与处理

研究采用归一化植被指数(Normalizationdiffer-encevegetation index,NDVI)提取植被物候参数。NDVI来源于美国国家航空航天局（NationalAero-nautics and Space Administration,NASA)的MODIS土地覆盖动态产品（MOD13Q1)，空间分辨率为 $2 5 0 \mathrm { m }$ 时间分辨率为16 d(https://lpdaacsvc.cr.usgs.gov/ap-peears）,参考文献将 $\mathrm { N D V I } _ { \mathrm { m e a n } } = 0 . 0 5$ 作为排除非植被的阈值[25],再采用16d最大合成的NDVI数据进行时间序列重构去除噪声，设置窗口大小和有理多项式均为3。最后采用Jonsson等[26提出的动态阈值法，将动态阈值设定为 $2 0 . 0 \%$ ） $5 0 . 0 \%$ 和 $8 0 . 0 \%$ ，根据沙坡头、海北和鄂尔多斯站点实地记录的物候数据和已有文献物候数据[17-18],经反复测试将植被 SOS和植被EOS的动态阈值设定为 $2 0 . 0 \%$ 和 $8 0 . 0 \%$ 。将NDVI曲线上升阶段，距离最小值为最大值与最小值间距离 $2 0 . 0 \%$ 的时间点定义为植被SOS。将ND-VI曲线下降阶段，距离最大值为最大值与最小值间距离的 $8 0 . 0 \%$ 的时间点定义为植被EOS。要说明的是NDVI数据时间序列长度为2001—2019年，由于Timesat3.2软件只能从 $n$ 年数据中提取到 $n { - } 1$ 年的物候参数[27]，故最终得到2001—2018年的物候数据，该结果已在文献[18]验证，验证结果表明本文提取的物候数据具有一定的可靠性。

逐月格点降水和气温数据来源于国家气象科学数据(https://data.cma.cn/data/index.html），本文运用2001—2018年黄土高原及其周边448个格点数据，水平分辨率为 $0 . 5 ^ { \circ }$ 。由于干旱指数(Standard-ized precipitation evapotranspiration index,SPEI)通过气温和降水数据生成,可以评估干旱的严重程度和持续时间，故优于其他干旱指数。本文利用R语言计算得到每个格点的季节性SPEI指数后，采用ANUSPLIN软件插值为 $2 5 0 \mathrm { m }$ 分辨率的季节性SPEI栅格数据集。SPEI指数结合标准降水指数（Standardizedprecipitationindex,SPI)多尺度效用与Palm-er干旱严重指数对气温和降水的敏感性，能够揭示区域气候的干旱特征[28-29]。3个月尺度的SPEI可以用来反应干旱的季节性变化特征，冬季为1、2月和上年12月，春季为3、4月和5月，夏季为6、7月和8月，秋季为9、10月和11月。由于植被SOS发生在春季,故计算时采用上年夏季、上年秋季、年初冬季和当年春季的SPEI;植被EOS发生在秋季，计算时采用年初冬季、当年春季、当年夏季、当年秋季的SPEI,详细分析见文献[24」。

土地利用覆盖数据来源于由NASA提供的MO-DIS土地利用覆盖图（MCD12Q1产品）,该数据的空间分辨率为 $5 0 0 \mathrm { m }$ ,时间为2001年和2018年(https://lpdaacsvc.cr.usgs.gov/appeears），因考虑到黄土高原自退耕还林(草)工程实施以来，该区环境治理成效显著[30],不同植被受退耕还林还草的影响较大，故去除了植被发生变化的区域，只提取2001—2018年土地利用覆盖类型未发生变换的区域，通过合并得到森林、灌丛、草地、农田以及其他5种植被类型[31],本文主要分析森林、灌木和草地。

# 1.3 研究方法

由于岭回归可以消除自变量之间的共线性，又摒弃了最小二乘方法的不偏性，因此作为一种改进的最小二乘估计法被广泛运用于实际的回归过程[31-32]。本文利用岭回归来探究物候对季节性SPEI的敏感性，其原理如下：

多元线性回归模型[33]：

$$
Y = X \times \beta + \varepsilon
$$

式中： $Y$ 为因变量的 $n$ 维观测向量； $X$ 为自变量的观测矩阵,维数为 $n \times p ( n > p ) \ ; \beta$ 为 $p \times 1$ 维的向量;$\boldsymbol { \varepsilon }$ 为 $n$ 维随机向量。

最小二乘估计量[33]：

$$
{ \hat { \beta } } = \left( X ^ { \prime } \times X \right) ^ { - 1 } \times X ^ { \prime } \times Y
$$

式中： $\hat { \beta }$ 为 $\beta$ 的最小二乘估计量； $X ^ { \prime }$ 为 $X$ 的逆矩阵； $X$ 为自变量的观测矩阵；Y为因变量的 $n$ 维观测向量。

最小二乘估计的结果虽然在理论上有较好的成效，但其参数估计可能不稳定，容易导致参数估计不合理,故本文采用岭回归分析消除多重共线性对估计的影响[34]。岭回归作为一种改进普通最小二乘估计的方法，其形式为：

$$
\hat { \beta } _ { \mathrm { R R } } = \left( X ^ { \prime } \times X + k \times I \right) ^ { - 1 } \times X ^ { \prime }
$$

式中： $\hat { \beta } _ { \mathrm { R R } }$ 为自变量对因变量的敏感系数； $X ^ { \prime }$ 为 $X$ 的逆矩阵； $X$ 为自变量的观测矩阵； $k$ 为岭参数； $I$ 为单位矩阵。要说明的是：本文物候是因变量，季节性SPEI是自变量，所有变量均在R语言中进行了线性去趋势，计算得到的回归系数是各自变量对因变量的敏感系数。

# 2结果与分析

# 2.1黄土高原植被物候的时空变化特征

黄土高原植被SOS的空间变化特征如图2a所示。黄土高原植被SOS主要集中在第90\~150d,植被 SOS 由东南向西北逐渐延迟[18]。2001—2018年植被 SOS年际变化趋势表明，植被SOS多年呈提前趋势，每年平均提前0.38d(图3a)。2011年的植被SOS最大(第132d)，物候发生时间最迟;2018年的植被SOS最小(第114d)，物候发生时间最早。

黄土高原植被EOS的空间变化特征如图2b所示。黄土高原植被EOS主要集中在第260\~310d,从总体来看宁夏高原和青海境内植被EOS较早，中部偏南区域植被EOS较迟。2001—2018年植被EOS年际变化趋势表明，植被EOS多年呈延迟趋势，每年平均延迟2.83d(图3b)。2002年的植被EOS最小，表明2002年物候结束时间较早；2018年的植被EOS最大，表明物候结束时间较迟。

由黄土高原植被物候的年际变化斜率可知（图3)，植被EOS的斜率大于植被SOS的斜率，表明植被物候多年推迟趋势较植被SOS提前趋势明显。

# 2.2黄土高原植被物候对季节性SPEI的敏感性

黄土高原植被物候对不同季节SPEI的敏感性随十旱发生时间的变化如图4所示，上年夏季和上年秋季的SPEI与植被SOS像元正百分比占比较大（均为 $6 1 . 0 \%$ ),即反映出大部分植被SOS受上年夏季和上年秋季SPEI的影响(通过 $P { < } 0 . 0 5$ 的显著性像元占比均小于 $5 0 . 0 \%$ )，会延迟植被生长。同样，年初冬季和当年春季的SPEI与植被SOS负敏感性像元占比较大，反映出大部分植被SOS受年初冬季和当年春季SPEI的影响，会提前开始植被生长。植被EOS与年初冬季SPEI的正敏感性像元占比最大(通过 $P { < } 0 . 0 5$ 显著性像元占比大于 $5 0 . 0 \%$ ),即反映出年初冬季SPEI相比于其他季节SPEI更容易导致植被EOS延迟植被生长期，而当年夏季发生干旱更容易导致大面积植被提前结束生长期。

干辛区地理  
图22001—2018年黄土高原植被物候空间分布  
![](images/31e276571cb3dacbf137ed46975d85764a3f0eeae9ccae078bf1a7120fd7ea33.jpg)  
注：SOS为植被生长季始期;EOS为植被生长季末期。下同。

![](images/c586307c3f20b2d39161f97eaa1ece96cbf6c9e2a47a88776518479f015b8745.jpg)  
Fig.2Spatial distributions of vegetation phenology in the Loess Plateau from 2Ool to 2018   
图32001—2018年黄土高原植被物候时间趋势变化  
Fig.3 Temporal trends of vegetation phenology in the Loess Plateau from 2Ool to 2018

# 2.3黄土高原植被物候对季节性SPEI敏感性的空间分布

基于2001—2018年黄土高原植被物候对不同季节SPEI的岭回归分析（图5），植被EOS和植被SOS均对季节性SPEI具有明显的空间异质性。当年春季和年初冬季SPEI与植被SOS的敏感性较其他2个季节正负敏感性差异明显，当年春季SPEI与植被SOS敏感系数为负的区域主要分布在黄土高原中部，而植被SOS与年初冬季SPEI显著为负敏感性零散分布在整体区域(通过 $P { < } 0 . 0 5$ 的像元占比为$7 0 . 1 \%$ )，尤其是青海境内，即青海境内年初冬季干旱程度减弱时，植被的萌芽期会提前，其原因可能是适当的气温促使植被SOS提前[。上年夏季SPEI和上年秋季SPEI与植被SOS的敏感系数正负像元占比接近，且正敏感系数像元占比分别为$6 1 . 4 \%$ 和 $6 1 . 2 \%$ （图4)，上年夏季SPEI与植被SOS负敏感系数较高的区域主要分布在黄土高原东北部，整个研究区植被SOS与上年秋季SPEI的敏感系数较小。年初冬季SPEI与植被EOS的敏感性较大，且显著正敏感性大范围分布在整个研究区（通过 $P <$

![](images/9dd70c22de74c8a2d256b963ae9b34d8236d678070b32cd5aadaac7a1064a058.jpg)  
注：SPEI为标准化降水蒸散发指数。  
图4黄土高原植被物候与季节性干旱的敏感性系数和像元正百分比

![](images/5785df57f2647dc26ce939bacfe3745f2c25816e8a39cb9b0b20b187f91ff510.jpg)  
Fig.4Sensitivityof vegetation phenology to seasonal drought and positive percentage of pixel in theLoessPlateau   
图5黄土高原植被物候对季节性干旱的敏感性   
Fig.5Sensitivity of phenology to seasonal drought in the Loess Plateau

0.05的像元占比为 $7 3 . 4 \%$ ),表明年初冬季干旱程度减弱，会推迟黄土高原植被的生长。植被EOS与当年春季SPEI的正负敏感性差异明显，甘肃、宁夏和陕西境内部分地区呈负敏感性。植被EOS与当年夏季SPEI在黄土高原东南部分地区呈正敏感性，其他大部分区域为负敏感性，表明夏季干旱过强会导致植被提前结束生长。大部分区域的植被EOS与当年秋季SPEI的敏感系数较小，表明植被在结束生长期间对干旱的响应较弱。

# 2.4黄土高原不同植被物候对季节性SPEI的敏感性

另外，对比分析不同植被物候对不同季节SPEI的敏感系数(图6)，发现植被SOS和植被EOS均对不同季节SPEI表现出不同的敏感程度(草地SOS和灌木EOS与年初冬季和当年春季的SPEI通过 $P <$

![](images/0543ea16d48778e3cddf0422f5b06033a4940cb878f54f90a052da867453e337.jpg)  
图6黄土高原不同植被物候对干旱的敏感系数  
Fig.6Sensitivity coeficients of different vegetation phenology to drought in the Loess Plateau

0.05显著性检验的像元占比均高于 $6 5 . 0 \%$ )。森林SOS对春季SPEI的敏感性高于其他3个季节，且只有上年夏季干旱程度减弱，才会提前森林SOS。灌木SOS对不同季节SPEI均表现出正敏感性，即不同季节SPEI均会导致灌木SOS延迟。4个季节SPEI与草地SOS的敏感系数均为负值，且年初冬季SPEI>当年春季SPEI>上年夏季SPEI>上年秋季SPEI,表明草地SOS在干旱程度较弱时会提前，且年初冬季干旱程度在各季节中对草地SOS的影响最大。当年春季和年初冬季SPEI与不同植被EOS的敏感系数均为正值，表明年初冬季和当年春季SPEI均会导致植被EOS推迟，尤其是年初冬季SPEI。灌木EOS对年初冬季和当年春季SPEI的敏感性高于森林EOS和草地EOS,表明灌木相比于森林和草地更易受干旱的影响。当年夏季SPEI与不同植被EOS 的敏感系数均为负值，表明干旱程度加剧会导致不同植被提前结束生长。不同植被EOS受当年夏季SPEI影响，物候提前依次为森林>草地>灌木;当年夏季和当年秋季SPEI均会导致灌木提前结束生长，尤其是当年秋季SPEI。

# 3讨论

SPEI除了能够识别不同时间尺度的干旱外，它还考虑了降水和气温，故被广泛运用于半干旱和干旱的环境中。黄土高原大部分地区属于干旱和半干旱气候,SPEI在时间和空间上均表现出了很大的差异性[35-36],且季节性SPEI受地形和大气环流的影响似乎比年际平均SPEI更能反映出干旱变化的复杂性,故采用季节性SPEI更能细化干旱对植被物

候的影响。

Zhao 等[9研究黄土高原干旱对植被的积累效应和时滞效应时发现,干旱对植被的积累效应发生在5\~10个月的范围内，而时滞效应发生在2\~3个月内。这个结果间接验证了本文研究结果,物候发生之前的干旱和物候发生时的干旱均会对植被物候产生影响。以往研究认为气温和降水是影响植被生长和植被物候的主要因素[38],而本文通过分析干旱对植被物候的影响后，认为干旱程度的大小也是影响植被物候的一个重要因素，干旱事件的发生对干旱和半干旱地区植被活动会产生重要影响。本文发现，年初冬季和当年春季的SPEI与植被SOS负敏感系数占比较大，由于SPEI越小，指示干旱程度越高，故年初冬季和当年春季干旱减弱会提前植被SOS,导致这一结果可能的原因是黄土高原植被经历了寒冷干燥的冬季后[37],春季气候回暖与干旱协同促进了植被萌芽[39]。Yao等[37]认为黄土高原夏秋季炎热多暴雨的天气会增加潜在蒸散量，再加该地区全年降水量少和降水频率小。当夏季干旱发生，经过一定时间的积累,植被没有充足的土壤水分供给到植被碳的合成[16],造成植被光合作用减弱、植被气孔关闭,导致叶片过早衰老，从而促使植被提前结束生长。植被物候对季节性干旱的空间敏感性响应正负差异明显，可认为干旱的发生会导致黄土高原区域内植被物候空间异质性变大。此外，本文还发现植被EOS受季节性SPEI的影响较植被SOS复杂，森林SOS较灌木SOS和草地SOS更容易受当年春季SPEI的影响，不同季节干旱均会导致灌木SOS延迟、草地SOS提前，原因可能是不同生态系统中不同群落的各种植被生理特性以及功能策略不同[3],导致不同植被物候对季节性干旱有着不同的敏感程度。另外，裴婷婷等[31指出黄土高原灌木的水分利用效率对气候的敏感程度明显高于森林和草地，可能导致灌木EOS比森林EOS和草地EOS更易受季节性SPEI的影响，可相应证实本文结论。

# 4结论

（1）上年夏季和上年秋季干旱程度加剧会延迟植被SOS，而年初冬季和当年春季干旱程度减弱可提前植被SOS。年初冬季SPEI相比于当年春季SPEI和当年秋季SPEI更容易延迟植被EOS，当年夏季干旱加剧会导致植被提前结束生长。

（2）植被EOS和植被SOS均对季节性SPEI具有明显的空间异质性。黄土高原青海境内年初冬季干旱程度减弱时，会造成植被SOS提前。当年夏季十旱程度加剧会导致黄土高原大部分植被提前结束生长。大部分植被结束生长期间对干旱的响应相对其他季节较弱。

（3）不同季节SPEI均会导致灌木SOS延迟、草地SOS提前，且灌木相比于森林和草地更容易受干旱的影响。年初冬季干旱程度相比于其他季节对草地SOS带来的影响最大,但森林、灌木和草地均会随当年夏季干旱程度加剧而提前结束生长。

# 参考文献(References)

[1]黄文琳,张强,孔冬冬,等.1982—2013年内蒙古地区植被物候 对干旱变化的响应[J].生态学报,2019,39(13):4953-4965. [Huang Wenlin, Zhang Qiang,Kong Dongdong,et al.Response of vegetation phenology to drought in Inner Mongolia from 1982 to   
2013[J].Acta Ecologica Sinica,2019,39(13): 4953-4965.] [2] 张学霞，葛全胜,郑景云.北京地区气候变化和植被的关系 基于遥感数据和物候资料的分析[J].植物生态学报，2004,28 (4): 499-5O6.[Zhang Xuexia, Ge Quansheng,Zheng Jingyun. Relationships between climate change and vegetation in Beijing using remote sensed data and phenological data[J]. Chinese Journal of Plant Ecology,2004,28(4): 499-506.] [3] Vicente-Serrano S M,Gouveiab C,Camarero JJ,et al.Response of vegetation to drought timescales across global land biomes[J]. Proceedings of the National Academy of Sciences,2012,110(1): 52-   
57. [4] IPCC. Climate change 2O13: The physical science basis: The summary for policymakers of the working group I contribution to the fifth assessment report[R]. Cambridge,UK: Cambridge University Press, 2013.   
[5]黄文洁.青藏高原高寒草地植被物候及其对气候变化的响应 [D].兰州:兰州大学,2019.[Huang Wenjie.Alpine grassland phenology response to climate change over Tibetan Plateau[D]. Lanzhou: Lanzhou University,2019.]   
[6]Lloyd D.A phenological classification of terrestrial vegetation cover using shortwave vegetation index imagery[J]. International Journal of Remote Sensing,1990,11(12): 2269-2279.   
[7]Zhang Q, Kong D D,Singh VP,et al. Response of vegetation to different time-scales drought across China: Spatiotemporal patterns, causes and implications[J]. Global & Planetary Change,2017,152 (5): 1-11.   
[8] Hanson PJ,Weltzin JF.Drought disturbance from climate change: Response of United States forests[J]. Science of the Total Environment,0,6(3):   
[9]Zhao A Z,Yu Q Y,Feng L L,et al. Evaluating thecumulative and time-lag effects of drought on grassand vegetation:Acase study in the Chinese Loess Plateau[J]. Journal of Environmental Management, 2020,261(5): 110214,doi: 10.1016/j.jenvman.2020.110214.   
[10]Anderegg W R,Berry JA,Field CB.Field linking definitions, mechanisms,and modeling of drought-induced tree death[J].Trends Plant Science,2012,17(12): 693-700.   
[11]Peng J, Wu C Y, Zhang X Y,et al. Satelite detection of cumulative and lagged effects of drought on autumn leaf senescence over the northern Hemisphere[J]. Global Change Biology,2019,25(6): 2174-2188.   
[12]WenYY,Liu XP, Xin Q C,etal.Cumulative effects of climatic factorson terrestrial vegetation growth[J]. Journal of Geophysical Research: Biogeosciences,2019,124(4): 789-806.   
[13] Ma X,Huete A, Moran S,et al.Abrupt shifts in phenology and vegetation productivity under climate extremes[J]. Journal of Geophysical Research: Biogeosciences,2015,120: 2036-052.   
[14]He Z,DuJ, ChenL,etal.Impactsofrecentclimatextremsn spring phenologyinarid-mountain ecosystems in China[J].Agricultural and Forest Meteorology,2018,260-261: 31-40.   
[15] 牟成香,孙庚,罗鹏,等.青藏高原高寒草甸植物开花物候对极 端干旱的响应[J].应用与环境生物学报,2013,19(2):272-279. [Mou Chengxiang, Sun Geng, Luo Peng,et al. Flowering responses of alpine meadow plant in the Qinghai-Tibetan Plateau to extreme drought imposed in different periods[J]. Chinese Journal of Applied and Environmental Biology,2013,19(2): 272-279.]   
[16] Yuan M,ZhaoL,LinA,etal.Impacts of preseasondroughtovegetation spring phenology across the northeast China Transect[J]. Science of the Total Environment,2020,738:140297,doi: 10. 1016/j.scitotenv.2020.140297.   
[17] 谢宝妮,秦占飞,王洋,等.基于遥感的黄土高原植被物候监测 及其对气候变化的响应[J].农业工程学报,2015,31(15):153- 160.[Xie Baoni, Qin Zhanfei, Wang Yang,et al. Monitoring vege

# 干吴区地理

tation phenology and their response to climate change on Chinese Loess Plateau based on remote sensing[J]. Transactions of the Chinese Society of Agricultural Engineering,2015,31(15): 153-160.]   
[18] 吉珍霞,裴婷婷,陈英,等.黄土高原植被物候变化及其对季节 性气候变化的响应[J].生态学报,2021,41(16):1-13.[Ji Zhenxia,Pei Tingting, Chen Ying,et al. Vegetation phenology change and its response to seasonal climate changes on the Loess Plateau [J]. Acta Ecologica Sinica,2021,41(16): 1-13.]   
[19] Ping Z, Wen A, Zhang X. et al. Soil conservation and sustainable eco-environment in the Loess Plateau of China[J]. Environmental Earth Sciences,2013, 68(3): 633-639.   
[20] Chu H S,Venevsky S,Wu C, et al. NDVI-based vegetation dynamics and its response to climate changes at Amur-Heilongjiang River Basin from 1982 to 2015[J].Science of the Total Environment, 2019,650(2): 2051-2062.   
[21]Liu D,Wang T, Yang T,et al. Deciphering impacts of climate extremes on Tibetan grasslands in the last fifteen years[J]. Science Bulletin, 2019, 64(7): 446-454.   
[22]Wu JW, Miao C Y,Zheng HY,et al. Meteorological and hydrological drought on the Loess Plateau, China: Evolutionary characteristics,impact,and propagation[J]. Journal of Geophysical Research: Atmospheres, 2018,123(20): 569-584.   
[23] 邹磊,余江游,夏军,等.基于SPEI的渭河流域干旱时空变化特 征分析[J].干旱区地理,2020,43(2):329-338.[Zou Lei,Yu Jiangyou,Xia Jun,et al. Temporal-spatial variation characteristics of drought in the Weihe River Basin based on SPEI[J].Arid Land Geography,2020,43(2): 329-338.]   
[24] 侯青青,裴婷婷,陈英,等.1986—2019年黄土高原干旱变化特 征及趋势[J].应用生态学报,2021,32(2):649-660.[Hou Qingqing,Pei Tingting,Chen Ying,et al. Variations of drought and its trend in the LoessPlateau from 1986 to 2019[J]. Chinese Journal of Applied Ecology,2021,32(2): 649-660.]   
[25] 秦格霞,吴静,李纯斌,等.中国北方草地植被物候变化及其对 气候变化的响应[J].应用生态学报,2019,30(12):4099-4107. [Qin Gexia,Wu Jing,Li Chunbin,et al.Grassland vegetation phenology change and itsresponse to climate changes in north China[J]. Chinese Journal of Applied Ecology,2019,30(12): 4099-4107.]   
[26]Jonsson P,Eklundh L. Seasonality extraction by function fiting to time-series of satellite sensor data[J].IEEE Transactions on Geoscience and Remote Sensing,2002,40(8): 1824-1832.   
[27] 倪璐,吴静,李纯斌,等.近30年中国天然草地物候时空变化特 征分析[J].草业学报,2020,29(1):1-12.[Ni Lu,Wu Jing,Li Chunbin,etal.Temporal and spatial variations innatural grassland phenology in China over the last 3O years[J].Acta Prataculturae Sinica,2020,29(1): 1-12.]   
[28] Liu Z P, Wang YQ, Shao M G,et al. Spatiotemporal analysis of multiscalar drought characteristics across the Loess Plateau of China[J]. Journal of Hydrology,2016,534(534): 281-299.   
[29] 赵建婷,王艳君,苏布达,等.印度河流域气温、降水、蒸发及干 旱变化特征[J].干旱区地理,2020,43(2):349-359.[Zhao Jianting,Wang Yanjun,Su Buda,et al. Spatiotemporal distributions of temperature,precipitation,evapotranspiration,and drought in the Indus River Basin[J].Arid Land Geography,2020,43(2): 349- 359.]   
[30] 刘静,温仲明,刚成诚.黄土高原不同植被覆被类型NDVI对气 候变化的响应[J].生态学报,2020,40(2):678-691.[Liu Jing, Wen Zhongming, Gang Chengcheng. Normalized difference vegetation index of different vegetation cover types and its responses to climate change in the Loess Plateau[J].Acta Ecologica Sinica, 2020,40(2): 678-691.]   
[31] 裴婷婷,李小雁,吴华武,等.黄土高原植被水分利用效率对气 候和植被指数的敏感性研究[J].农业工程学报,2019,35(5): 119-125,319.[Pei Tingting,Li Xiaoyan, Wu Huawu,at el. Sensitivity of vegetation water use eficiency to climate and vegetation index in Loess Plateau, China[J]. Transactions of the Chinese Society of Agricultural Engineering,2019,35(5): 119-125,319.]   
[32] 王义闹,卢庆华.关于多重共线性的三个知识点的准确表述[J] 温州大学学报(自然科学版),2019,40(3):7-12.[Wang Yinao, Lu Qinghua.The accurate expression of three knowledge points about multicollinearity[J]. Journal of Wenzhou University (Natural Science Edition),2019,40(3): 7-12.]   
[33] 甘胜进,王琼瑾.一类线性回归模型的参数估计[J].华中师范大 学学报（自然科学版),2021,5(3):351-355.[Gan Shengjin, Wang Qiongjin. Estimation for a class of linear regression models [J]. Journal of Central China Normal University (Natural Sciences Edition),2021,55(3): 351-355.]   
[34]WalkerE,Birch JB.Influence measures inridgeregression[J]. Technometrics,1988,30(2): 221-227.   
[35]师玉锋,梁思琦,彭守璋.1901—2017年黄土高原地区气候干 早的时空变化[J].水土保持通报,2020,40(1):283-289,325. [Shi Yufeng, Liang Siqi,Peng Shouzhang.Spatiotemporal variation of climate drought in Loess Plateau region during 1901—2017[J]. Buletin ofSoiland Water Conservation,2020,40(1): 283-289,25.]   
[36] 张永瑞,张岳军,靳泽辉,等.基于SPEI指数的黄土高原夏季干 旱时空特征分析[J].生态环境学报,2019,28(7):1322-1331. [Zhang Yongrui, Zhang Yuejun, Jin Zehui, et al. The temporal and spatial characteristics of summer drought in the Loess Plateau based on SPEI[J].Ecology and Environmental Sciences,2019,28 (7): 1322-1331.]   
[37]Yao JQ,Dilinuer Tuoliewubieke,Chen J,et al. Identification of drought events and correlations with large-scale ocean-atmospheric patterns of variability:A case study in Xinjiang,China[J].Atmosphere,2019,10(2): 94,doi: 10.3390/atmos10020094.   
[38] 安彬,肖薇薇,张淑兰,等.1960—2017年黄土高原地表温度时 空变化特征[J].干旱区地理,2021,44(3):778-785.[An Bin, Xiao Weiwei, Zhang Shulan,et al. Spatial and temporal characteristics of surface temperature in the Loess Plateau during 1960- 2017[J]. Arid Land Geography,2021, 44(3): 778-785.]

# Sensitive response of vegetation phenology to seasonal drought in the Loess Plateau

JI Zhenxia’，HOU Qingqing2，PEI Tingting1，CHEN Ying $^ { 1 , 3 }$ ， XIE Baopeng³， WU Huawu4.5

(1.College ofResourcesandEnvironment,GansuAgriculturalUniversity,Lanzhou73oo,Gansu,China;2.Collgeof Pratacultural Science,Gansu AgriculturalUniversity,Lanzhou 73oo7o,Gansu,China;3.Colegeof Management,Gansu AgriculturalUniversity,Lanzhou 73oo,Gansu,China;4.KeyLaboratoryofGrassandEcosystem(Gansu Agricultural University),MiistryofEducation,Lnzhou3Ooo,Gansu,China;5.NanjingIstituteofGeographyandLimnologyCise Academy of Sciences,Nanjing 210o08,Jiangsu, China)

Abstract: Under the background of global warming,the increasing frequency and intensity of drought events significantly change the vegetation diversity in terestrial ecosystems. Vegetation productivity,carbon storage, and the carbon cycle in terrestrial ecosystems are deeply affcted by vegetation phenology. However, there are few studies on the efects of seasonal drought on different vegetation phenology due to the inherent complexity, uncertainty of drought,and differences in the resistance and resilience of diferent vegetation to drought. Therefore,based on the normalized diffrential vegetation index,landuse cover,and monthly temperature and monthly precipitation data,this study calculated the start of the season (SOS),end of the season (EOS),and standardized precipitation evapotranspiration index (SPEI) of vegetation on the Loess Plateau.Additionaly, it analyzed the response of vegetation phenology changes to seasonal SPEI using the Ridge regression analysis method from 200l to 2018.The results are as follows.(1) The vegetation SOS was delayed by the intensification of drought in summer and autumn of last year, whereas the SOS of vegetation was advanced by the weakening of drought in winter and spring of the same year. SPEI in the winter at the beginning of the year is more likely to delay vegetation EOS than SPEI in the spring and fallof the same year.An intensification of the summer drought could cause vegetation to stop growing earlier. (2) The EOS and SOS of vegetation showed obvious spatial heterogeneity in response to seasonal SPEI.The SOS of vegetation in the Loess Plateau willbe advanced when the drought degree decreases at the beginning of winter in Qinghai.The intensification of drought in summer would lead to the premature end of most vegetation growth on the Loess Plateau.The response of most vegetation to drought at the end of the growth period was weaker than in other seasons.(3)The SOS of shrub was delayed,and the SOS of grassand was advanced due to SPEI in diferent seasons,and shrub was more susceptible to drought than forest and grassland.Droughts in winter atthe beginning of the year have the greatest impact on the SOSof grassland than other seasons.Meanwhile,the growth of forests,shrubs,and grassand wil end earlier with drought intensities in summer.This study revealed the response law of vegetation phenology to seasonal drought in the Loess Plateau. It provided a scientific basis for vegetation response to water stress and ecological environment protection.

Key words: vegetation phenology; seasonal drought; sensitivity response; the Loess plateau