# 甘肃中东部植被生长季NDVI时空变化及其对气候因子的响应

赵鸿雁，陈英²，周翼²，裴婷婷²，谢保鹏²，王晓倩'1甘肃农业大学资源与环境学院,甘肃 兰州 730070；2 甘肃农业大学管理学院,甘肃 兰州 730070)

摘要：为分析研究生态保护与修复工程实施背景下甘肃中东部植被生长季NDVI时空变化及其对气候因子的响应，采用MODIS 数据产品MOD09Q1,运用最大值合成法、趋势分析法与相关分析法，对该区域2008—2016年NDVI的时空变化特征及其对气候因子的响应进行了分析研究。结果表明：(1）时间层面上,2008—2016年植被生长季 NDVI呈现出增加的趋势,增加速率为 $0 . 0 0 1 \mathrm { ~ 4 ~ a ~ } ^ { - 1 }$ ，2012年增幅最大;空间层面上,2008—2016年研究区内的低山丘陵区和平原区的植被生长季NDVI增加明显;部分中起伏山地植被活动减弱。（2）生长季NDVI对不同气候因子的响应程度不同，在$P < 0 . 0 5$ 的显著性水平下，生长季NDVI对气温的变化最敏感，区域内大部分面积上二者呈现出强相关与极强相关;降水次之，以中等相关与强相关为主；太阳辐射最小，以弱相关甚至不相关为主。研究结果可为针对区域差异性并有所侧重的生态工程的实施提供相应的参考与依据，从而加强区域生态安全，进而促进国家生态安全屏障的加快建设。

关键词：NDVI；趋势分析法；气候因子；甘肃中东部

近年来，改善生态环境以缓解现阶段社会主要矛盾备受关注[1]。作为陆地生态系统敏感成员的植被能够通过其最直观的表现较好的表征区域生态环境状态[2-3],其覆盖变化能够反映一定区域内自然、人工和经济生态系统中各因素对植被的影响程度[4-5]。采用人工治理修复与自然恢复相结合生态保护与修复工程耦合了自然和社会经济生态系统，使得区域的整体生态功能逐步恢复和提升。目前关于生态工程方面的研究主要包括生态工程治理成效[6-7]及其效益评价[8-10]方面和工程实施现状及问题分析[1]等方面。气候是决定地球上植被覆盖状况的最主要因素，作为自然因素的气候因子与植被间相互关系的研究已成为全球变化研究的重要内容[12],而定量指标归一化植被指数 NDVI与植被覆盖之间呈正相关关系[12-14],且被广泛用于植被变化和植被一气候关系的研究。因此，可运用植被生长季NDVI来探析生态工程实施背景下区域植被覆盖变化状况及其对气候因子的响应情况，从而实现自然与人为双重因素对生态环境影响的初步探究。目前关于植被生长季NDVI应用方面的研究主要集中在区域和项目区上，具体体现为区域尺度上植被覆盖时空变化及驱动因素分析方面[15-17]和项目尺度上单一研究对象的变化方面[18-19]。基于生态工程背景对植被生长季NDVI时空变化及其对气候因子响应方面的研究鲜有涉及。

考虑到黄土高原地区相对恶劣的自然条件和脆弱的生态系统，区域内严重的水土流失及其治理成效备受关注[2],植被状况作为生态治理成效最为直观的体现亦给予了高度关注。甘肃中东部地区脆弱的生态环境一直以来都是生态工程治理的观点所在，近年来对于该区域植被覆盖变化方面的研究鲜有涉及。基于此，本研究以2008一2016年为研究时段,采用 MOD09Q1 数据,基于ENVIClassic $5 . 3 +$ IDL8.5与ArcGIS10.2平台和MRT工具对研究时段内的NDVI数据进行相应的处理，来探究多种生态工程人工治理修复与自然修复对区域植被覆盖状况的影响，并进一步探究其对气候因子的响应，从而分析科学评价研究区生态环境质量提升程度，实现多年来黄土高原地区生态工程治理成效的定性分析，为后期区域生态保护与修复政策的制定提供相应的参考，实现对区域生态环境保护与修复的进一步指导。

# 数据来源与研究方法

# 1.1 研究区概况

本研究中的甘肃中东部地区为典型的黄土丘陵沟壑区，具体的地理位置如图1所示，涉及甘肃省陇中、东地区和陇南山地，共计4个市区。其中，庆阳市与平凉市属于生态环境极为脆弱、沟坝地和坡旱地广泛分布的陇东地区；中部偏南的定西市属于黄土高原西部边缘地带和西秦岭末端的陇中地区；天水市则由于北秦岭与祁连山的共同作用，属于区域内多分布向斜构造和断陷谷地的陇南山地。无论是植被还是降水分布，整个研究区均因黄土高原独特的气候而呈现自东南至西北地带性分异的规律。自1999 年退耕还林还草生态工程的实施,区域内的植被状况有所好转，至2012年东部百万亩土地整治重大工程项目以及其后实施的山水林田湖草生态保护与修复工程，均使得区域内生态环境状况明显改善，人民生活质量再创新高，旨在加强区域生态环境改善、保护与管护，以及更进一步提高人民生活水平的重大工程相继开展。主观上生态环境得到极大改善，但从植被角度来客观分析生态工程治理成效方面的研究相对缺乏。

# 1.2 数据来源与预处理

本研究中 2008—2016年的MODIS（Moderate-Resolution Imaging Spectroradiometer）数 据产品MODO9Q1来源于美国LPDAAC（LandProcessDis-tributedActiveArchiveCenter,USA）,主要采用USGSEROS 数据中心所开发的MRT（MODISReprojectionTool)工具来完成对影像子波段(第1、2波段)的格式与投影转换以及重采样等处理。DEM数据来源于美国地质勘探局，是ASTERGDEM $\mathrm { V } 2 ~ 3 0 ~ \mathrm { m }$ 分辨率数字高程。降水、气温与太阳辐射数据来源于寒区旱区科学数据中心，SWAT模型中国大气同化驱动数据集（CMADSV1.0）。MOD09Q1数据产品空间分辨率为 $2 5 0 \mathrm { ~ m ~ }$ ,时间分辨率为 $8 \mathrm { ~ d ~ }$ 。本研究主要基于ENVIClassic5. $3 + \mathrm { I D L } 8 . 5$ 及其插件“小熊工具箱V3.0”、ArcGIS10.2与MRT工具来对研究区的原始影像进行处理，其中采用最大值合成法获取了研究区植被生长季的月度NDVI数据。由于影像拍摄过程中会受到云、太阳高度角等的影响，影像数据会产生异常值，需要对其进行滤波处理，本研究中采用的是 S-G（Savtzky-Golay)滤波[20-21]法。

![](images/75c53dbf74df8c3d9905816003d825ad484715ef2efa103660978025458830a9.jpg)  
图1地理位置区位图  
Fig.1Location map

# 1.3 研究方法

1.3.1最大值合成法（MVC）本研究中的最大值合成法 MVC（Maximum Value Composites）[22]主要用于植被生长季( $( 4 \sim 1 0$ 月）NDVI月度数据的获取。该方法能够在一定程度上减少原始影像拍摄过程中云、太阳高度角等的影响，其计算公式如下所示：

$$
\mathrm { M a x } N D V I _ { i } = \mathrm { M a x } \left( N D V I _ { 1 } , N D V I _ { 2 } , N D V I _ { 3 } , N D V I _ { 4 } \right)
$$

式中： $\mathbf { M a x } N D V I _ { i }$ 表示月度NDVI最大值; $i$ 为月份，取值为 $4 \sim 1 0 ; N D V I _ { 1 } \sim N D V I _ { 4 }$ 分别表示相应月份内原始影像预处理后的 $N D W$ 值。

1.3.2Savtzky-Golay 滤 波法Savtzky-Golay 滤波法即 Savtzky-Golay 滤波拟合法，它通过确定合理的滤波参数，对研究区植被生长季NDVI数据作加权多项式拟合，以求得最小均方根误差，这样远离大多数点的一些边缘点便不会参与拟合[23]。故拟合时过于偏离正常生长趋势线的噪声部分会被丢弃。其基本公式如下所示：

$$
Y ^ { * } \ = \frac { \displaystyle \sum _ { i = - m } ^ { m } C _ { i } \times Y _ { j + 1 } } { N }
$$

式中： $\boldsymbol { Y } , \boldsymbol { Y } ^ { * }$ 分别表示原始NDVI数值和平滑后的NDVI数值; $C _ { i }$ 为多项式拟合系数，表示从滤波器首部开始的第 $i$ 个NDVI值的权重; $N$ 为滤波器的长度，其大小等于 $2 \ m + 1$ 。

1.3.3趋势分析法趋势分析法[22]的原理在于运用一元线性回归分析的方法对区域内时序植被生长季NDVI的变化趋势和其强度进行分析。其中，回归方程的斜率slope代表研究时段内每个栅格点植被指数的变化趋势。若 $s l o p e > 0$ ,代表该栅格植被状况有所改善，且slope值越大改善效果越明显；反之亦然；若 $s l o p e = 0$ ,则表示植被状况无变化。

$$
s l o p e \ = \frac { \displaystyle { n \times \sum _ { i = 1 } ^ { n } \left( i \times M _ { N D M _ { i } } \right) \ - \ \sum _ { i = 1 } ^ { n } i \sum _ { i = 1 } ^ { n } M _ { N D M _ { i } } } } { \displaystyle { n \times \sum _ { i = 1 } ^ { n } i ^ { 2 } \ - \ \left( \sum _ { i = 1 } ^ { n } i \right) ^ { 2 } } }
$$

式中： $s l o p e$ 是趋势线的斜率； $n$ 是时间序列的长度，

本研究中为9a（2008—2016年）； $i$ 是第 $i$ 年； $N D W _ { i }$   
是第i年生长季NDVI值(4\~10月）。

# 2结果与分析

# 2.1 甘肃中东部2008—2016年植被生长季 NDVI时空变化分析

2.1.1 甘肃中东部2008—2016年植被生长季 ND-VI年际变化分析本研究首先基于8d合成的MOD09Q1数据的第1、2波段计算得到了相应时长研究区的NDVI数据，然后运用最大值合成法计算得到研究区植被生长季(4～10月）NDVI月度数据，最后得到研究区2008—2016年年际NDVI均值及其变化情况如图2所示。

由图2可知，总体上植被生长季NDVI年际变化呈现出增加趋势，且以 $0 . 0 0 1 4 \cdot { \mathrm { ~ a ~ } } ^ { - 1 }$ 的速率增加,2012年是一个明显的突变点，增幅最大。2008—2011年，生长季年际NDVI均值变化相对稳定，保持在 $0 . 1 9 1 9 \sim 0 . 1 9 9 4$ 之间。这主要是由于研究区所属区域为典型的黄土丘陵沟壑区，生态环境相对脆弱，多年来由于退耕还林还草等各种生态工程的治理，生态环境状况有所改善，人民生活水平有所提升，其对于生态环境的认知程度亦得到有效改观，最为显著的是2008—2011年甘肃省广泛开展的退耕还林还草工程成效的保存率和管护率均达到 $9 9 \%$ 以上，种植结构中饲草类作物的种植比例提高了$10 \%$ ,区域内生态治理成效显著。

2012年作为一个明显的突变点，可以看出2011一2012年，生长季年际NDVI变化最大，达到了$0 . 0 3 0 \ 6$ 。2011年是研究时段内实施退耕还林还草面积最大的一年，2008年开展的大规模土地整治特别注重研究区内旱坡地的整理，于滞后期2a后土地生产力显著提高，导致2012年NDVI变化最大。2012年后，生长季NDVI保持基本稳定。这主要是由于2013年研究区内开展了甘肃东部百万亩土地整治重大项目工程，主要针对研究区内的黄土梁与黄土塬等水土流失较为严重的地区进行了相应的治理，于2014和2015年再次开展的新一轮退耕还林还草，尤其注重特色林果业的发展，注重生态效益与经济效益兼优，并优先安排生态环境脆弱、生态地位重要的区域，同时加强退耕地保护与退耕经营权适度流转，均使得区域内的土地生产能力不仅得到提高，农民的收入也显著增加 $\phantom { + } \phantom { + } \phantom { + } \phantom { + } \phantom { + } 2 0 1 5$ 年后各地充分认识到山水林田湖是一个生命共同体，对山水林田湖草进行统一保护与修复必须遵循自然规律，使得区域内NDVI变化相对稳定并有所提高。

![](images/e168a67215216403bd859ec03fd45c149fa85a9119827430b6c607e1eb8712f3.jpg)  
图2甘肃中东部2008—2016年植被生长季NDVI年际变化

2.1.2 甘肃中东部 2008—2016年植被生长季ND-VI空间变化分析本研究基于ENVI5.3平台，采用时序数据趋势分析模型，对研究区9a的NDVI空间变化情况进行了相应分析，具体结果如图3所示。

图3a为2008—2016年NDVI空间变化，变化量介于 $- 0 . 2 9 0 \mathrm { ~ 8 ~ } \sim 0 . \mathrm { ~ 2 6 9 ~ 9 ~ }$ 之间。陇东地区的NDVI的增加状况明显较好，主要以平凉与庆阳两市的交界处最为明显，而平凉东部以及庆阳南部NDVI的变化相对较小；隶属于陇南山地的天水市的NDVI变化呈现出自东南向西北递减的趋势，以东部NDVI增加最为明显;陇中地区的NDVI变化则较小,尤其是定西中部地区呈现出NDVI负向增加情况，但总体上NDVI仍是增加的。以上变化均说明研究区内所实施的各种生态保护与修复工程过多注重各自治理工程的成效，忽视了各工程相互之间的联系，导致区域整体上生态治理成效欠佳。近年来以“山水林田湖是一个生命共同体”的倡议为指引，区域内开始注重生态系统内部之间的有机联系，生态环境的全面改善与修复有待进一步发展。

图3b为2008—2016年植被指数变化趋势的斜率（slope），介于 $- 0 . 0 4 2 \ 3 \sim 0 . 0 3 8 \ 4$ 之间，说明植被变化情况相对较大。依据罗敏等[23]的划分依据,说明区域内植被变化相对稳定，基本无退化现象。slope值比较高的区域主要分布在以平凉与庆阳两市交界处为代表的低山丘陵区和平原地区，这些地区植被生长季NDVI明显上升，植被覆盖程度增加，植被活动明显增强。slope值较低的区域主要分布在以平凉东部、定西与天水两市交界处、定西中西部地区以及庆阳南部的黄土塬和中起伏山地，这些地区植被生长季NDVI有所下降，植被覆盖程度下降，植被活动相对减弱。植被活动减弱可主要归因于区域内相对较差的自然条件，年降水量明显低于蒸发量，加之生态工程的实施破坏了原有的平衡系统，区域植被耗水与蒸散发加剧，导致土壤出现干层，出现部分植被死亡，导致植被NDVI指数相应有所下降，植被活动减弱。研究区内并无slope为0的区域。

![](images/ce0335973c33d9759e7dfc729b0c54bd2eab9a4759f84310fd3a1b3af718f5c5.jpg)  
g.2 Variation of annual NDVI of vegetation growing season in mid and eastern Gansu Province from 2O08 to 2C   
图3甘肃中东部2008—2016 年 $N D W$ 空间变化及变化趋势图  
Fig.3Spatial and trend variation of NDVI in mid and eastern Gansu Province from 2OO8 to 2016

# 2.2甘肃中东部 2008—2016年植被生长季 NDVI对气候因子的响应分析

由于植被覆盖变化对气候变化的响应在不同区域上差异较大，研究区属于干旱半干旱地区，故气温、降水与太阳辐射会直接或间接地对区域植被覆盖状况造成影响。气温上升增强了植物内部酶的活性，加速了化学反应速率，使得植被春、秋季物候期有所提前或推迟，延长了植被生长季，植被覆盖状况有所改善；气温过高会使植物的蒸腾作用加快，导致植被耗水与蒸散发量均增加，土壤水分加快流失，植被活动因水分限制而相应减弱。而降雨量会直接影响土壤含水量，同样会加速植物内部化学反应速度[24]。太阳辐射较好的阳坡由于降雨量较少会容易导致更多的蒸散发，使植被覆盖降低，阴坡则由于光照和太阳辐射较弱而容易形成干冷的天气，植被活动明显较弱,甚至不利于植被的生长[25]

因此，为探究生态保护与修复工程实施情况下气候因子（月累积降水/ $\mathbf { \dot { m } } \mathbf { m }$ 、月平均气温/ $\mathrm { ^ \circ C }$ 与月平均太阳辐射 $\mathbf { \nabla } ^ { \prime } \mathbf { M } \mathbf { J } \cdot \mathbf { \nabla } \mathbf { m } ^ { - 2 }$ )对植被生长季NDVI的影响，本研究先从时间层面上分析了年均NDVI与气候因子的变化情况如图4所示。

由图4可知，生长季NDVI与降水的变化情况除2010 年、2015年与2016年外，其余年份变化趋势基本一致,表现出一定程度上的同步。生长季NDVI与气温变化趋势除2012年、2016年外，其余年份变化趋势基本一致。生长季NDVI与太阳辐射变化除 2011年、2014年与2015年外，其余年份变化趋势基本吻合。总体来说，较降水与太阳辐射，气温与生长季NDVI的变化趋势吻合程度更高。

鉴于年际气候因子与生长季NDVI呈现出基本一致的变化趋势，为进一步探讨二者之间相关关系的密切程度，本研究基于像元尺度，运用小熊工具箱v3.0中的时序数据相关分析模型来探究2008—2016年空间上气候因子与植被生长季NDVI间相关关系的密切程度。时序数据相关性分析模型是用来分析两组多波段数据之间的相关性，输出两组多波段数据的相关系数波段。本研究以2008一2016 年生长季NDVI月度数据为输入数据，输出2008—2016年生长季NDVI与各气候因子之间的相关系数。根据相关系数的等级划分，将其分为基本不相关( $| r | \leqslant 0 . 2 \AA ,$ 、弱相关（ $\ : ( 0 . 2 < \mid r \mid \leqslant 0 . 4 \ :$ 、中等相关（ $0 . 4 < \mid r \mid \leqslant 0 . 6 \$ ）、强相关 $( 0 . 6 < \mid r \mid \leqslant 0 . 8 )$ ）、极强相关 $( 0 . 8 < \mid r \mid \leqslant 1 )$ 5级，并统计得到2008—2016年不同相关( $\textstyle P < 0 . 0 5 )$ 等级下生长季NDVI与降水、气温和太阳辐射之间的占比情况如图5所示。

![](images/5ff22a2fd51bb249bfbed18336f6c9521d4de4018b19c0c074649cf1a520ba44.jpg)  
Fig.4Slope map and annual variation of different slopes’NDVI in mid and eastern Gansu Province from 2008 to 2017

由图5可知，不同相关等级下，降水与生长季NDVI之间在区域内大部分面积上显示为中等程度相关与强相关，弱相关与基本不相关次之，极强相关占比最少。气温与生长季NDVI之间在区域内大部分面积上显示为强相关与极强相关，中等程度相关面积量占比次之，基本不相关与弱相关面积占比较少。太阳辐射与生长季NDVI之间在区域内大部分

![](images/a87de87e2bd335b1da0bd3410692c64f75292ee375542e04aeb8d196c4ff0008.jpg)  
图4甘肃中东部2008—2016年生长季NDVI与气候因子年际变化

■降水■气温口太阳辐射 ■降水■气温 □太阳辐射 ■降水■气温口太阳辐射60 80  
806040 %/中 6040  
20 20  
0 0 08000 6007 2000 2007 707 3055 4422 005 9100 800% 6000 2000 242T 207 305 4401 2000 9000 800% 6000 2000 401 2302 3505 402 2301 9500年份 年份 年份■降水 ■气温 □太阳辐射 ■降水 ■气温 □太阳辐射100 80品 □ □ %/ 60 □□ 40200 08000 6007 2000 2307 2402 3505 4422 2500 9500 8000 6007 2100 2301 222 3000 4402 2001 9400年份 年份

面积上显示不相关或者弱相关，少部分区域显示中等程度相关，极少部分区域显示出强相关与极强相关。因此，总体来说，气温对植被的生长状况最敏感,降水次之，太阳辐射最小。

综上，2010年、2011年、2012年、2014年、2015年与2016年生长季NDVI变化与气候因子变化不一致。2010 年区域内生长季NDVI与降水之间的相关系数以强相关与极强相关为主，但该年份生长季NDVI较2009年有所下降，降水是上升的，而气温是显著下降的，太阳辐射是增加的，这进一步说明生长季NDVI对气温的敏感性，气温的下降导致区域内以农作物为主的部分植被长势欠佳，从而导致生长季NDVI下降。2011年气温与降水均呈现下降趋势，尽管太阳辐射上升不少，但生长季NDVI还是呈现出下降的趋势，这也说明降水与气温对生长季NDVI影响较大，太阳辐射影响较小。2012年降水和气温与生长季NDVI的相关性较强，在各气候因子均有所增加的情况下，区域内生长季NDVI明显增加。2014年与2015年各气候因子均呈直线下降的趋势，区域内大部分面积的生长季NDVI与气温和降水呈现出强相关与极强相关，可见该阶段NDVI下降与气温和降水关系密切。2016年降水有所回升，但是年均气温升高了 $1 \mathrm { ~ \textdegree C }$ ，气温与生长季NDVI之间的关系以极强相关为主，气温升高导致区域内部植被欠佳，导致区域内生长季NDVI下降。总体来说，尽管研究区属于干旱半干旱区，降水并不是影响区域内植被生长状况的最主要因素，这与区域地处黄土丘陵沟壑区有极大的相关性，一系列生态工程对水土流失等的治理使得降水与植被生长状况不再呈现出负相关关系，并逐渐转向正相关。植被生长对气温的变化仍是最敏感的。

# 3讨论

赵安周、石玉琼和秦国玲等研究得到大型生态工程对 NDVI均会产生正面影响[4,8,26]。甘肃中东部地区土层厚、地下水位深、蒸发量大于降水量，生态环境相对脆弱。1999年以来生态工程通过人工种植，组建新的植被系统，打破了原有的平衡系统，植被耗水大于降水补给，强化了土壤干燥化程度。针对这一现象，从土壤水分的角度来说,在生态工程实施初期，土壤条件较好，植被树木较多，枯枝落叶和腐殖质增多，土壤表面性质得到改善，土壤蓄水量增强,表层土壤水分有所增加[27]。生态工程实施6\~12a间存在大幅波动,12a之后灌木就会成为工程区的优势种，群落结构趋于稳定，动植物残体逐渐增多，改善了土壤环境，使得土壤水分逐渐增多，植被覆盖相应增加[28]。12a之后随着土壤深度的增加，土壤含水量减少的越多，导致土壤干层出现。故对于植被覆盖度合理阈值的确定以及下垫面特征如土壤水分对植被覆盖的影响有待进一步研究。

本研究得到区域内2008—2016年植被生长季NDVI呈现出明显增加的趋势,这与崔丹丹等[25]、曹博等[29]的研究结果一致,且NDVI增加区域集中在陇中和陇东地区。区域内植被生长季NDVI对气候因子中的气温最敏感，二者之间的相关性在 $9 5 \%$ 的显著性水平下大部分以强相关和极强相关为主；降水次之，以中等相关与强相关为主；太阳辐射的影响则为最小，以弱相关甚至不相关为主。这与曹永强等[24]、曹博等[29]的研究结果相似,鉴于区域间的差异性，相关性程度也有所不同。故气候因子对生长季NDVI影响程度的定量研究有待进一步探讨。

# 4结论

（1）甘肃中东部地区2008—2016年年际NDVI在时间层面上呈现为增加的趋势，增加速率为$0 . 0 0 1 4 \cdot { \mathrm { ~ a ~ } } ^ { - 1 }$ ,2012 年增幅最大;在空间层面上,其空间变化图与slope图均显示研究区内的低山丘陵区和平原区NDVI增加最为明显，植被活动明显增强；而在研究区内的部分中起伏山地，植被活动出现减弱的现象，但后期正确认识到了多种生态工程之间的有机联系，生态治理后的管护力度有所增加，植被活动相应增强，生态环境质量明显提升。

(2)生长季NDVI对不同气候因子的响应程度不同，其中气温变化与生长季NDVI变化关系最密切，在区域内大部分面积上呈现出强相关与极强相关，降水次之，以中等相关与强相关为主，太阳辐射的影响则为最小，以弱相关甚至不相关为主。本研究对研究区植被生长季NDVI的时空变化及其与气候因子变化之间的相关性所进行的研究可为针对区域差异性并有所侧重的生态工程的实施提供相应的参考与依据，从而加强区域生态安全，进而促进国家生态安全屏障的加快建设。

# 参考文献(References)

[1］中共环境保护部党组.构建人与自然和谐发展的现代化建设 新格局一一党的十八大以来生态文明建设的理论与实践[J]. 环境保护,2016,44（13）:11-13.[PartyGroup of theMinistryof Environmental Protection of the Communist Party of China.Building a new modernization construction pattern of the human and nature harmonious development：Based on the theory and practice since the eighteenth congress of the ecological civilization construction[J].Environmental Protection,2016,44(13）:11-13.]

[2］穆少杰,李建龙，陈奕兆，等.2001—2010年内蒙古植被覆盖度时空变化特征[J].地理学报，2012，67（9）：1255-1268.［MUShaojie,LIJianlong,CHENYizhao,etal.Spatial differences of var-iations of vegetation coverage in Inner Mongolia during 2001—2010[J].Acta Geographica Sinica,2012,67(9）:1255-1268.][3] PARMESAN C,YOHE G.A globally coherent fingerprint of cli-mate change impacts across natural systems[J].Nature,2Oo3,421(6918) :37 -42.

[4］赵安周,张安兵,刘海新,等.退耕还林(草)工程实施前后黄土 高原植被覆盖时空变化分析[J].自然资源学报，2017,32（3）： 449-46O.［ZHAO Anzhou,ZHANG Anbing,LIU Haixin,et al. Spatiotemporal variation of vegetation coverage before and after implementation of grain for green project in the Loess Plateau[J]. Journal of Natural Resources,2017,32(3）:449-460.]

[5] CAOS X,CHEN L,SHANKMAND,et al.Excessive reliance on afforestation in China's arid and semi-arid regions:Lessons in ecological restoration[J].Earth-Science Reviews,2011,104（4）： 240-245.

[6]赵婷,张义,赵伟,等.退耕还林还草工程对土壤微生物和土壤酶影响的研究进展［J].江苏农业科学，2018，46（1）：9-14.[ZHAO Ting,ZHANG Yi,ZHAO Wei,et al.Research progress ofeffects of the farmland-to-forest/grassland conversion program onsoil microorganism and soil enzyme[J]. Jiangsu Agricultural Sci-ences,2018,46(1) :9-14.]

[7］陈孟立,曾全超,黄懿梅,等.黄土丘陵区退耕还林还草对土壤细菌群落结构的影响[J].环境科学，2018，39（4）：1824-1832.［CHEN Mengli,ZENGQuanchao,HUANG yimei,et al.Effects of the farmland-to-forest/grassland conversion program onthe soil bacterial community in the Loess Hilly Region[J].Envi-ronmental Science,2018,39（4）:1824- 1832.]

[8］秦国玲.土地整治对 NDVI的影响研究[D].昆明：昆明理工大 学,2017.[QIN Guoling.Study on the effect of land consolidation on NDVI[D].Kunming:Kunming University of Science and Technology,2017.]

[9］张景忠,王云毅.内蒙古达拉特旗风沙区退耕还林还草生态效益评价［J].西部资源，2017，（2）：164－166，175.［ZHANGJingzhong,WANGYunyi.Evaluation of ecological benifits on refor-estation in Dalad Banner wind sand area of Inner Mongolia[J].Western Resource,2017,(2):164-166,175.]

[10］欧阳真程，赵小敏，张晗，等.鄱阳湖平原区土地整治项目生态效益评价——以江西省鄱阳县为例[J].江西农业学报,2018,30（2）：123-128.［OUYANG Zhencheng，ZHAO Xiaomin,ZHANG Han,et al.Evaluation of ecological benefit of land recla-mation project in Poyang Lake Plain:A case study of Poyang Coun-ty,Jiangxi Province[J].Acta Agriculturae Jiangxi,2O18,30（2）：123 -128.]

[11］宗瑜.退耕还林还草的现状及问题分析[J].中国农业信息，2016,(4）:93-94.[ZONG Yu.Analysis on the status and prob-lems of returning farmland to forest and grass[J].China Agricul-tural Information,2016,（4) :93-94.]

[12]ROERINKGJ,MENENTIM,SOEPBOERW,etal.Assessment of climate impact on vegetation dynamics by using remote sensing [J].Physics and Chemistry of the Earth,2002,28(1）:103 -109.

[13］张慧，李平衡，周国模,等.植被指数的地形效应研究进展[J]. 应用生态学报,2018,29(2）:669-677.[ZHANG Hui,LIPing heng,ZHOU Guomo,et al.Advances in the studies on topographic effects of vegetation indices[J].Chinese Journal ofApplied Ecology,2018,29(2) :669-677.]

[14]CARLSONTN,RIPLEY DA.On the relation between NDVI,fractional vegetation cover,and leaf area index[J].Remote Sensing of Environment,1997,62(3） :241 -252.

[15］沈关东，朱志梅,刘欢，等.基于NDVI的渭南市植被覆盖时空变化研究[J].中国人口·资源与环境，2016，26（S2）：351-353.［SHEN Guandong,ZHU Zhimei,LIU Huan,et al.Researchonspatial-temporal variations of vegetation cover in Weinan Citybased on NDVI[J].China Population,Resources and Environ-ment,2016,26(S2):351-353.]

[16］胡砚霞，黄进良，杜耘，等.2000—2015年丹江口库区植被覆盖 时空变化趋势及其成因分析[J].长江流域资源与环境，2018， 27(4）:862-872.[HU Yanxia,HUANG Jinliang,DU Yun,et al. Spatio-temporal trends of vegetation coverage and their causes in the Danjiangkou reservoir region during 2OoO to 2015[J].Resources and Environment in the Yangtze Basin,2018,27（4）： 862 -872.]

[17］刘旻霞,赵瑞东,邵鹏,等.近15a黄土高原植被覆盖时空变化 及驱动力分析[J].干旱区地理,2018，41（1）：99-108.［LIU Minxia,ZHAO Ruidong,SHAO Peng,et al.Temporal and spatial variation of vegetation coverage and its driving forces in the Loess Plateau from 2001 to 2015[J].Arid Land Geography,2018,41 (1):99 -108.]

[18］木热提江·阿不拉，张晓萍，陈利利，等.基于GIMMSNDVI的 黄土高原地区荒漠化时空特征分析[J].中国水土保持科学， 2015,13（3）:24-31.［ABLA Murat,ZHANGXiaoping,CHEN Lili,et al.Spatial-temporal distribution of desertification on theLoessPlateau using the GIMMS NDVI data[J].Science of Soil and Water Conservation,2015,13(3）:24-31.]

[19］黄珂,刘忠,杨丽芳.基于多年MODIS-NDVI的黄淮海农区冬 小麦生产力评价[J].农业工程学报，2014,30（2)：153-161. [HUANG Ke,LIU Zhong,YANG Lifang.Evaluation of winter wheat productivity in Huang-Huai-Hai region by multi-year graded MODIS-NDVI[J].Transactions of the Chinese Society of Agricultural Engineering,2014,30(2）:153-161.]

[20］宫攀，陈仲新.基于MODIS 数据的东北地区植被物候参数提 取[J].土壤通报,2009,40（2）：213-217.［GONGPan,CHEN Zhongxin.Regional vegetation phenology monitoring based on MODIS[J].Chinese Journal of Soil Science,2009,40（2）:213- 217.]

[21］SAVITZKYA,GOLAY MJE.Smoothing and differentiation of data by simplified least squares procedures[J].Analytical Chemistry,1964,36:1627 - 1639.

[22］徐建华.现代地理学中的数学方法［M].北京：高等教育出版 社,2002.[XU Jianhua.Mathematical methods in modern geography[M].Beijing:Higher Education Press,2002.]   
[23］罗敏,古丽·加帕尔,郭浩,等.2000-2013 年塔里木河流域生 长季NDVI时空变化特征及其影响因素分析［J].自然资源学 报,2017,32(1）:50-63.[LUO Min,JIAPAER Guli,GUO Hao, et al.Spatial-temporal variation of growing-season NDVI and its responses to hydrothermal condition in the Tarim River Basin from 2000 to 2013[J]. Journal of Natural Resources,2017,32（1）： 50-63.]   
[24］曹永强,张亮亮,袁立婷.辽宁省植被生长季 NDVI对气候因子 的响应[J].植物学报,2018,53（1）:82-93.[CAO Yongqiang， ZHANG Liangliang,YUAN Liting.Correlation analysis of normalized difference vegetation index（NDVI） and climatic factors in the vegetative growing season in Liaoning Province[J].Chinese Bulletin of Botany,2018,53(1）:82-93.]   
[25］崔丹丹,张耀南,陈广庭.2001—2010 年甘肃省植被覆盖的时 空变化[J].中国沙漠,2014,34（4）,1161-1166.［CUI Dandan,ZHANG Yaonan,CHEN Guangting. Spatial and temporal variation of NDVI in Gansu,China during 2001—201O based on re mote sensing[J]. Journal of Desert Research,2014,34（4）, 1161 - 1166. ]   
[26］石玉琼,郑亚云,李团胜.榆林地区 2000—2014年 NDVI时空 变化［J].生态学杂志,2018,37（1):211-218.[SHI Yuqiong, ZHENG Yayun,LI Tuansheng.The spatiotemporal change of NDVI in Yulin,Shaanxi Province,China from 20oO to 2014[J].Chinese Journal of Ecology,2018,37(1):211-218.]   
[27］李航.黄土丘陵沟壑区退耕坡面土壤水分和产流特征[D].杨 凌：西北农林科技大学,2018.［LI Hang.Characteristics of soil moisture and runoff on abandoned slopeland in the hill and gully Loess Plateau region［D].Yangling：Northwest Agriculture and Forestry University,2018.]   
[28］马俊梅,满多清,李得禄,等.干旱荒漠区退耕地植被演替及 土壤水分变化[J].中国沙漠,2018,38（4）:800－807.[MA Junmei,MAN Duoqing,LI Delu.et al. Characteristics of vegetation succession and soil moisture in advanced cropland of arid desert region[J].Journal of Desert Research,2018,38（4）： 800 -807.]   
[29］曹博,张勃,马彬,等.2000—2014 年甘肃省 NDVI时空变化特 征[J].中国沙漠,2018,38(2）:418-427.[CA0 Bo,ZHANG Bo,MA Bin,et al.Spatial and temporal variation of NDVI in Gansu,China from 2000 to 2014[J].Journal of Desert Research, 2018,38(2) :418 -427.]

# Spatiotemporal variation of NDVI in vegetation growing season and its responses to climatic factors in mid and eastern Gansu Province from 2008 to 2016

ZHAO Hong-yan’，CHEN Ying'²，ZHOU Yi²，PEITing-ting², XIE Bao-peng²， WANG Xiao-qian' (1College of Resources and Environment,Gansu Agricultural University,Lanzhou 73oo7O,Gansu，China; 2College of Management,Gansu Agricultural University,Lanzhou 73oo7O,Gansu,China)

Abstract：As a sensitive memberof terrestrial ecosystem,vegetation can characterize the influence extentof natural and human factors on theregional ecological environment.In viewof the scarcityof good ecological environment in the world,ecological engineering was used as a means to protect and restore the ecological environment.The quantitative index normalized diference vegetation index（NDVI） was widely used to study vegetation change and therelationship between vegetation and climate.Therefore,inorder to analyze the NDVI variation inthe vegetation growing season in mid and eastern Gansu Province,northwest China underthe background of implementing the Ecological Engineering for Ecological Protectionand Restoration,MOD09Ql data wasused toanalyze the spatiotemporal variation of $N D W I$ in the vegetation growing season and its responses to climatic factors by applying maximum value composite（MVC）,trendand corelation analysis approach from 2008 to 2016.The results showed as follows:：（1) On the time level,the NDVIof the vegetation growing season showed an increasing trend from 2008 to 2O16,with an increasing rate of $0 . 0 0 1 4 \mathrm { ~ a ~ } ^ { - 1 }$ ,and the largest increase occurred in 2O12. On the spatial level,the NDVI of the vegetation growing season in the studyarea,the low hilly areas and plains,increased significantly from 2O08 to 2016. Furthermore,the vegetation activity in the rolling hills in some areas is weakened.（2）The response degree of $N D$ # $\boldsymbol { { \mathit { W } } } _ { }$ to different climatic factors is diferent in vegetation growing season.At the significant level of $P < 0 . 0 5 , N D V I$ variationinthe growing season is the most sensitive to the changeof temperature.Most of the areas in the region show strongand extremely strong correlation,andthe precipitation isthe second sensitive factor with moderate and strong correlation,andthe solar radiation is the least,with weaklycorrelation or even without correlation.Theresearch can provide the corrsponding reference and basis for the implementation of the ecological engineering based onregional diferences and the particular purposes,soas to strengthen theregional ecological securityand accelerate the construction of the national ecological security barrier.

Key words:NDVI; trend analysis approach ;climatic factors ;mid and eastern Gansu Province