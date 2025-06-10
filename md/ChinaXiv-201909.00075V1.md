# 泥石流易发性评价模型的构建

以白龙江流域石门乡羊汤河段为例 王高峰，杨强，田运涛，叶振南，陈宗良，高幼龙， 郭宁，邓兵

（中国地质调查局水文地质环境地质调查中心，河北保定071051)

摘要：以白龙江流域石门乡至羊汤河段为例,采用松散物质面密度、地层岩性、构造断裂密度、地震密度、坡向、土壤可蚀性、土地利用类型、坡长坡度、沟床比降、流域沟壑密度及年均降雨量等11项评价因子的归一化值,在GIS平台下运用层次分析法建立泥石流易发性评价模型，将研究区泥石流易发性评价栅格图划分为4个等级。研究表明：泥石流中高易发区域占整个研究区面积的 $5 1 . 0 4 \%$ ，区内发育的泥石流流域面积占中高易发区面积的 $6 8 . 7 1 \%$ ，其分布特点具有沿大型活动性断裂呈带状分布,在次级断裂和小型褶皱密集区集中发育;沿易崩易滑地层呈片状展布,在沟壑密集带分区块集中发育;在坡面侵蚀强的区域多为泥石流高易发区，呈串珠状连片分布。利用研究区泥石流数据库对评价结果进行检验,检验曲线表明分区效果良好，检验曲线下面积即AUC值为 $6 2 . 1 3 \%$ ，说明易发性评价结果较为可靠。

关键词：泥石流；易发性评价；AHP层次分析法；模型构建；白龙江流域

泥石流易发性评价是风险评价的前提，是指在一定的孕灾背景条件下泥石流的空间发生概率，主要判断评价区内容易发生泥石流的位置，而不考虑发生的具体时间和规模，进而预测评价区域未来产生泥石流灾害的可能性。国内外有关区域泥石流易发性以栅格单元、流域地貌单元、行政区划单元及均一条件单元为评价单元取得了不少成果。20 世纪70 年代，Hollingsworth等采用专家打分法构建了滑坡泥石流评价的基本框架;Carrara等²利用RS和GIS技术进行了滑坡泥石流灾害评价制图方法的研究。中国泥石流易发性评价以区域研究为特色，现有的研究方法主要根据泥石流发育的环境背景因子，如选取地层岩性、坡度、构造及土地利用等，结合泥石流历史数据和成灾过程等信息库，基于GIS技术采用统计学和地学的方法，在较大的区域尺度上对泥石流灾害发生的可能性进行预测[3-12]。以上研究成果不论在评价方法还是模型构建都在很大程度上推动了泥石流灾害易发性评价的发展，但由于评价对象的地域差异和目标不确定性，评价因子选取和分级需根据研究区泥石流易发性背景条件进行重新划分。再者以流域地貌为基本评价单元对泥石流易发性进行评价时，一个泥石流流域只被赋予一种易发性值，但是某一流域范围内的泥石流不一定只有一种易发性，所以有必要以栅格为基本评价单元对研究区整体进行泥石流易发性评价。

白龙江流域泥石流灾害受地震、气候及人类活动等影响强烈，致使泥石流流域内物源量、土地利用类型等孕灾环境及诱发泥石流临界雨量也随之变化，泥石流灾害易发性表现为动态变化特征。而以往的易发性评价多基于静态的孕灾环境条件，不能有效反映其动态变化规律。由于对泥石流灾害易发性动态变化认识不够，以往看似易发性低的泥石流沟却发生了严重的地质灾害。如2015 年武都区柏林乡后沟降雨诱发沟道弃渣揭底，冲毁拦挡坝，泥石流物质冲入北峪河;2017年‘ $8 \cdot 6 ^ { \prime }$ 文县梨坪泥石流灾害，造成7人死亡、2人失踪，舟曲县峰迭镇庙沟上游支沟黑天岭爆发泥石流，一次冲出泥石流固体物质达 $4 . 2 \times 1 0 ^ { 4 } ~ \mathrm { m } ^ { 3 }$ 。

因此，需要分析降雨和地震影响下，基于泥石流发育特定孕灾环境分析进行泥石流易发性评价具有现实意义，评价结果能有效降低泥石流灾害带来的损失，为地质灾害防治提供靶区。本文依据地质调查项目“陇南白龙江流域地质灾害调查2016年度调查成果”，从研究区地形地貌、物源条件、水土流失程度及水文环境等背景条件出发，分析了研究区泥石流灾害易发性的静态和动态因子，最终筛选了11个影响泥石流灾害发生的评价因子，基于GIS 的层次分析模型对研究区进行了泥石流易发性评价，以期为该区域工程建设及城镇规划防灾减灾预警工作提供参考。

# 1 研究区概况及数据来源

# 1.1 研究区概况

研究区面积 $2 \ 0 7 2 . 9 \ \mathrm { k m } ^ { 2 }$ ,位于白龙江流域甘肃段中下游,包括白龙江干流武都区石门乡至文县临江镇段及其支流蒲池河、北峪河下游、福津河、龙坝河、羊汤河。在地形地貌上地处青藏高原东部、秦岭山地西缘，属典型的深切峡谷地貌，区内泥石流流域具有比降陡、沟谷中后缘形态多呈大肚子状的特点，不仅易于水流汇聚，而且物源极为丰富。地质构造上地处松潘－甘孜褶皱带和南秦岭褶皱带两个不同构造体系的交接部位，研究区南北两端受构造运动活动极为强烈。北部属武都“山”字形构造西翼白龙江复背斜南端,主要受NWW向的白龙江断裂和光盖山迭山断裂、NE向礼县－罗家堡断裂、近E向两当-江洛断裂影响,南部主要受哈南－青山湾 -稻畦子断裂及文康断裂影响，导致岩体变形破碎，为泥石流提供了丰富的固体松散物质。此外，该区复杂的构造又为泥石流发育提供了良好的地形条件[13]。同时,该段位于我国南北地震带中北段,历次地震活动加剧了山体和岩土结构破坏及其他地质灾害的发生，导致固体松散物质剧增，诱发一系列新的泥石流等地质灾害。该区地层岩性极为复杂，属西秦岭地层区，从前震旦系到第四系均有出露，分布最为广泛的地层为泥盆系、志留系、石炭系和侏罗系，其中以泥盆系和志留系地层分布最为广泛，岩性强度较低，多属软弱岩层，易受降雨侵蚀、构造破坏和风化剥蚀(图1）。气候上白龙江中游属暖温带向亚热带过渡区，降雨垂向上随海拔增高具有增大的趋势，常以连阴雨、暴雨形式出现。受山地气候及地形的影响，研究区降水具有时空分布不均、年内分配差异性较大的特征，降水具有由东南向西北递减趋势且局地小气候现象明显，多年平均降雨量在$4 3 6 \sim 7 7 8 \ \mathrm { m m }$ 。据前人研究降雨在一日之内亦有不同,在同一泥石流沟域也存在差异性[14] C

![](images/9c29a7b7b9621c4b226173a454063efae1757f0c1331bc6c01896804d42b4753.jpg)  
图1研究区示意图Fig.1The study area

# 1.2 数据来源

以往对泥石流易发性评价的相关研究中，若评价区大而比例尺小的空间数据，多采用栅格单元，栅格单元在GIS软件中易于划分且计算便捷。因本文研究区面积较大，故选取栅格单元作为泥石流易发性评价的基本单元。然后在ArcGIS平台下将各参评因子图层的矢量数据转化为 $2 5 \mathrm { ~ m ~ } \times 2 5 \mathrm { ~ m ~ }$ 的栅格数据进行叠加计算。本文所需的主要数据类型及数据源汇总见表1。

# 2 区域泥石流易发性评价分析

# 2.1 评价因子选取

本文在分析研究区地形地貌、物源条件、水土流失程度及水文环境等泥石流发育的静态特征和动态触发因素基础上，结合泥石流易发性评价已有的研究成果[7-12],选取了11项评价因子：松散物质面密度、地层岩性、构造断裂密度、地震密度、坡向、土壤可蚀性、坡度坡长、土地利用类型、沟床比降、流域沟壑密度及年均降雨量等影响因子。

松散物质面密度( $\mathbf { C } _ { 1 }$ )对泥石流形成起到决定

# 表1数据类型及数据来源

Tab.1 Sources and types of the data   

<html><body><table><tr><td>基础数据</td><td>数据来源与制作</td><td>数据格式</td></tr><tr><td>DEM</td><td>地理空间数据，用于提取坡度坡长、坡向、沟壑密度及泥石流沟床比降</td><td>国家地理信息中心：25m×25m栅格数据</td></tr><tr><td>DOM/DLG</td><td>土地利用类型数据</td><td>国家地理信息中心：5m×5m和25m×25m栅格 和矢量数据</td></tr><tr><td>地质数据</td><td>岩性分区、断层密度计算</td><td>1:200000 区域地质图，矢量数据</td></tr><tr><td>地震数据</td><td>震级大于3级的地震活动次数</td><td>国家地震科学数据共享中心网站，矢量数据</td></tr><tr><td>遥感数据</td><td>用于泥石流物源、基本特征和土地利用类型等解译</td><td>高分二号数据，栅格数据</td></tr><tr><td>泥石流灾害统计</td><td>根据《陇南白龙江流域地质灾害调查》《陇南市地质灾害防治规划 (2011—2020年)》遥感影像解译</td><td>矢量数据</td></tr><tr><td>降雨资料</td><td>兰州中心气象台，陇南市地质灾害专业监测网络</td><td>点云(矢量)数据</td></tr></table></body></html>

性作用,松散物质储量越丰富，遭受到的累积灾害链发育程度就越大,而泥石流流域内不良地质体发育程度直接决定了固体松散物的储量，所以单位面积内不良地质体发育程度是表征松散物储量的重要指标;地层岩性( $\mathbf { C } _ { 2 }$ )影响岩石的风化程度，进而影响泥石流松散固体物质的聚集;构造断裂密度( $\mathbf { C } _ { 3 } \mathbf { \Psi } ,$ 反映构造活动的强弱，为泥石流提供松散固体物质的来源;地震密度( $\mathrm { : C _ { 4 } }$ )反映地震波的反复作用程度，能造成大量坡体失稳和岩体破坏,表现为土体的黏聚力和有效黏聚力随着地震周次的增加逐渐降低，地震作用为泥石流灾害提供了丰富的物源，随着时间的推移，松散固体物质逐渐固结、运移到冲积扇或下游沟道，泥石流的易发性也随之降低，通过CF 模型分析研究区泥石流松散固体物源与地震密度的关系(图2);坡向 $( \mathrm { C } _ { 5 }$ )的差异导致干湿条件的不同，从而影响斜坡干湿循环程度，在中国阳坡的地质灾害较阴坡发育;土壤可蚀性( $\left. \mathbf { C } _ { 6 } \right.$ 反映流域坡面的直接破坏程度，是人类活动、坡体破坏及岩石风化侵蚀等因素的综合体现;坡长坡度因子 $\big ( \mathrm { C } _ { 7 } \big )$ 是土壤侵蚀的关键性因子，能反映泥石流流域沟坡产流、汇流能力的大小;土地利用类型( $\mathrm { C } _ { 8 }$ )是植被覆盖管理和水土保持措施的综合体现,可作为降雨侵蚀动力的抑制因子，发育茂密的植被及良好的水土保持措施具有固土护坡及雨水截留作用，利于缓解坡面径流的汇聚,对泥石流的发育具有抑制作用;沟床比降(C。)是泥石流地形势能因素的综合体现,亦是判别泥石流搬运沟道物质难易程度的指标，利用研究区泥石流数据库信息，通过信息量模型可得出研究区泥石流与沟床比降之关系（图3），得出 $300 \text{‰}$ 左右沟床比降有利于泥石流的形成;流域沟壑密度( $\mathrm { { C } _ { 1 0 } }$ ）是水流汇集能力的表现,在一定程度上反映了该地区地形切割程度、起伏程度和岩土体松散程度，反映土壤侵蚀的严重程度，也能反映地貌的演化阶段；年平均降雨量( $\mathbf { C } _ { 1 1 }$ ),研究区主要为降雨型泥石流灾害，主要受连续降雨、暴雨，尤其是特大集中降雨的激发，持续的强降雨通过减小土体内聚力和增加水的作用来激发泥石流起动，本文研究所用降雨数据主要为分布于陇南山地406处气象观测点所采集的多年平均降雨量，选用皮尔逊ⅢI(P-IⅢ)分布函数统计方法，可推导出多年平均降雨量等值线图，在考虑与泥石流间的关系时，需要在ArcGIS平台下对多年平均降雨量进行Spline 插值,得出结果进行分级以及重分类。

![](images/a461e59af1428da0a5ec74155bc81ca89e7bfef5dcb9ebbce0447995d50880cd.jpg)  
图2地震密度与泥石流流域内固体松散物质的关系 Fig.2Relationship between seismic density and solid loose material in the debris flow basin

![](images/274156a8b37598e8063f7bfc4bd4f987704c129b6e645456c3150bcaf1de6380.jpg)  
图3沟床比降与泥石流灾害的关系  
Fig.3Relationship between gully bed slope and debris flow disaster

在ArcGIS10.2平台上，利用高精度DEM、遥感影像图及地质图等资料，得到上述9个评价因子图层，然后采用4级量化标准对参评因子进行归一化处理[4,12,15],将对泥石流形成影响最小者等级赋值为1，影响最大者等级赋值为4（表2）。

# 2.2评价因子权重确定

在多指标评价中，指标权重的确定具有至关重要的作用，用以反映指标之间的相对重要性，合理地确定指标权重，关系到多指标评价结果的可靠性与正确性。基于研究区泥石流的分布及发育特征，采用层次分析法对评价因子指标赋权重值进行易发性评价。AHP是一种可以解决多指标的复杂问题、定量与定性相结合的决策方法，其优点是精度高，使用方便[18]。具体步骤：首先建立层次结构模型（图4);二是参考以往研究[4,15]对11个参评指标因子之间的相互重要性进行打分，并结合研究区的泥石流易发性因子级别分级分析结果，采用1\~9标度方法最终构建判断矩阵;三是在Matlab软件下计算比较矩阵的特征向量和最大特征值，将特征向量进行归一化处理,若满足一致性检验则可得各单层次因子权重值;最后将得到的单层次因子权重进行总权重值计算，得出评价因子的总权重值(表3）。

表2评价因子等级划分及赋值  
Tab.2Classification and valuation of assessment indexes   

<html><body><table><tr><td>影响因子</td><td></td><td></td><td>地</td><td></td><td>地震密度</td><td>坡向</td><td></td><td>坡长度</td><td>用地型</td><td>海床比</td><td></td><td></td></tr><tr><td rowspan="4">分 级 围</td><td>不易</td><td><1</td><td>古近系</td><td><0.25</td><td>2.2~2.8</td><td></td><td>石质</td><td><0.09</td><td></td><td><60</td><td><0.3</td><td><550</td></tr><tr><td>（低发</td><td>1~5</td><td></td><td>0.25-0.35</td><td>20242</td><td>45°~90°</td><td>砂石质</td><td>0.09~0.25</td><td>成林</td><td>60~100</td><td></td><td>0.3~0.5 550~600</td></tr><tr><td>中易发 范 (赋值3)</td><td>5~10</td><td>P前震系0.45~0.6 Q第四系</td><td></td><td>1.0~1.6</td><td>135°~225° 270°~325° [sWW]</td><td></td><td>[SSE~SSW]、土石质 0.25~0.48</td><td>园经地 林地</td><td>100~150 >350</td><td></td><td>0.5~0.7 600~650</td></tr><tr><td>（高发）</td><td>>10</td><td>新 留系</td><td>0.35~0.45、</td><td>0.4~1.0</td><td>90°~135° 225S270。 [ssW]</td><td>土质</td><td>0.48~1</td><td>早地</td><td>150~350</td><td>0.7~1.2</td><td>>650</td></tr><tr><td>分级方法 及依据</td><td></td><td>单位面积 内不良地</td><td>岩石的软 硬程度进 行量化分</td><td>单位面积 内断层线</td><td>单位面内震爱 震次数,CF模 分级点 法</td><td>ArcGIS软 件默认分</td><td>文献 [16]</td><td>自然断点 法</td><td></td><td>[17]息，量型然 自然断点法断点法</td><td>概单位 文献长度比值，的总长</td><td>多平 量等值 线图进 分级</td></tr></table></body></html>

![](images/558c24dfefbd5a356d552a2fc08cccda96f83146b1ecf98ed35acee66b7b0b9e.jpg)  
图4评价因子层次模型  
Fig.4Hierarchy model of assessment indexes for debris flow

从表3可以看出，本文选取的区域泥石流易发性评价指标，影响泥石流形成的关键因子为物源条件和水动力条件，只有在物源和地形条件都具备的前提下，降水诱发极易爆发泥石流灾害。

# 2.3 区域泥石流易发性评价分析

在ArcGIS10.2平台环境下分别对11个评价因子按等级划分标准进行易发程度等级赋值，将得出的评价因子分级赋值栅格图层进行加权叠加（图5），可得研究区泥石流易发性评价栅格图（图6）。区域泥石流易发性计算模型如下：

$$
R = \sum _ { i = 1 } ^ { n } C _ { i } W _ { i }
$$

式中： $R$ 为泥石流易发性指数; $\textstyle \mathbf { \big | } \mathbf { \big | } _ { i }$ 为评价因子权重;  
$C _ { i }$ 为评价因子分级赋值栅格图层。

经上式计算得到泥石流易发性栅格统计图层，按自然断点法将研究区泥石流易发性统计图层划分不易发区、低易发区、中易发区、高易发区4个等级，获得研究区基于层次分析法的泥石流易发性评价分区图，评价分区结果见表4。

从分区结果图6空间位置上看，泥石流中高易发区主要分布在两水镇－蒲池乡、武都区-透坊沟段白龙江干流左岸、龙坝河中下游(梨坪乡）、外纳乡下游至临江上游段，即白龙江两岸、桥头乡集镇周边及福津河右岸。其中高易发区面积约为452.44$ { \mathrm { k m } } ^ { 2 }$ ,占整个研究区面积的 $2 1 . 8 3 \%$ ,区内发育的泥石流流域面积为 $4 3 6 . 5 8 ~ \mathrm { k m } ^ { 2 }$ ，占高易发区面积的$9 6 . 5 0 \%$ ；而中易发区面积约为 $6 0 5 . 5 0 ~ \mathrm { k m } ^ { 2 }$ ，占整个研究区面积的 $2 9 . 2 1 \%$ ，区内发育的泥石流流域面积为 $4 2 8 . 8 3 ~ \mathrm { k m } ^ { 2 }$ ，占中易发区面积的 $7 0 . 8 2 \%$ 。中高易发区内泥石流分布有以下特点： $\textcircled{1}$ 沿大型活动性断裂呈带状分布，在次级断裂和小型褶皱密集区集中发育； $\textcircled{2}$ 与地层岩性关系密切，高易发区域主要是由千枚岩、炭质板岩等软弱岩组成的志留系一段及由灰岩、千枚岩软硬互层构成泥盆系四、五段易滑地层区，而中易发区域主要是软硬相间组成的较坚硬易崩地层区； $\textcircled{3}$ 在沟壑密集带集中分块、分区发育； $\textcircled{4}$ 在坡面侵蚀程度强的区域多为泥石流高易发区，呈串珠状连片分布； $\textcircled{5}$ 研究区南北两侧泥石流易发性受控的影响因子不同，泥石流性质亦有差异，北部主要受控于软弱的易滑地层及“山”字形活动性断裂影响，多黏性泥石流;而南部受控于NE 向断裂及地震影响，山体松动多易崩地层，主要为稀性泥石流。低易发区和不易发区面积约1014.96$ { \mathrm { k m } } ^ { 2 }$ ,占研究区总面积的 $4 8 . 9 6 \%$ ,区内发育的泥石流较少，不易发区内发育的泥石流仅占 $2 5 . 5 8 \%$ ，多为稀性潜在泥石流沟谷，主要分布在蒲池河上游及研究区中西部海拔较高的区域。该区内高山植被覆盖度较高，构造断裂分布稀少，主要出露灰岩、砂岩及板岩，岩体完整，风化较弱。

表3评价因子权重值  
Tab.3Weighted values of assessment indexes   
表4泥石流易发性评价结果统计   

<html><body><table><tr><td>第一层 次指标</td><td>第一层 次指标 权重</td><td>第二层 次指标</td><td>第二层 次指标 相对权重</td><td>第二层 次指标 总权重</td><td>第一层 次指标</td><td>第一层 次指标 权重</td><td>第二层 次指标</td><td>第二层 次指标 相对权重</td><td>第二层 次指标 总权重</td></tr><tr><td rowspan="5">物源敏感性 (B）</td><td rowspan="5">0.478</td><td>松散物质面密度(C)</td><td>0.441</td><td>0.211</td><td>水土流失程度</td><td>0.289</td><td>土壤可蚀性(C6)</td><td>0.523</td><td>0.151</td></tr><tr><td>地层岩性(C）</td><td>0.232</td><td>0.111</td><td>（B）</td><td></td><td>坡长坡度(C)</td><td>0.284</td><td>0.082</td></tr><tr><td>断层密度（C）</td><td>0.153</td><td>0.073</td><td></td><td></td><td>土地利用类型（Cg)</td><td>0.193</td><td>0.056</td></tr><tr><td>地震密度(C4)</td><td>0.111</td><td>0.053</td><td>地形地貌(B）</td><td>0.146</td><td>沟床比降(Cg)</td><td>1</td><td>0.146</td></tr><tr><td>坡向(C5）</td><td>0.064</td><td>0.031</td><td>水文环境(B4)</td><td></td><td>0.087流域沟壑密度(C1o)</td><td>0.25</td><td>0.022</td></tr></table></body></html>

Tab.4Statistic results of debris flow susceptibility   

<html><body><table><tr><td>易发区分级</td><td>易发区面积 /km²</td><td>易发区面积百分比 /%</td><td>实际泥石流流域面积 /km²</td><td>实际泥石流流域面积百分比 /%</td><td>易发区内实际泥石流 流域面积百分比/%</td></tr><tr><td>高易发区</td><td>452.44</td><td>21.83</td><td>436.58</td><td>34.66</td><td>96.50</td></tr><tr><td>中易发区</td><td>605.50</td><td>29.21</td><td>428.83</td><td>34.05</td><td>70.82</td></tr><tr><td>低易发区</td><td>568.44</td><td>27.42</td><td>279.83</td><td>22.22</td><td>49.23</td></tr><tr><td>不易发区</td><td>446.52</td><td>21.54</td><td>114.20</td><td>9.07</td><td>25.58</td></tr></table></body></html>

![](images/74b7f1feb7ee27ee21886594a7dfd4cdb956c67fb74d2a0c47ac6a8c2bc570a7.jpg)

![](images/adc62ebde25b06c19305db673427c226a5cdc0c5b679412e197a54c78242c839.jpg)

![](images/b06d2d6ebf13d04aab8520b4f6e34fbfa468bb6f6f28b26b1bc39ea143d8a02a.jpg)  
图6泥石流易发性评价

# 3评价分区结果检验

通过野外调查统计以及泥石流分布图和区域泥石流易发性评价分区图层的对比分析，以预测泥石流流域面积累积百分比作为横坐标，以实际调查泥石流流域面积累积百分比为纵坐标，构建评价结果检验曲线对泥石流易发性评价分区结果进行检验。生成的检验曲线下方的面积（AUC）用来定量表达易发性预测的准确度，又可以评价实际泥石流与预测模型的拟合程度，如检验曲线呈凸形，AUC面积越接近1，则易发性评价结果越好。中高易发区的面积约为 $1 0 5 7 . 9 4 \mathrm { k m } ^ { 2 }$ ，占研究区总面积的$5 1 . 0 4 \%$ ,而两易发区内实际发育的泥石流流域面积为 $8 6 5 . 4 1 ~ \mathrm { k m } ^ { 2 }$ ,占统计泥石流总面积的 $6 8 . 7 1 \%$ ，占中高易发区总面积的 $8 1 . 8 0 \%$ ，表明易发性评价预测结果与实际发育泥石流对比，检验效果较好。从图7预测泥石流流域面积百分比累加与实际泥石流流域面积百分比累加关系曲线可以看出，检验曲线呈明显的凸形，说明泥石流易发性评价结果是理想的。积分计算得到图7中检验曲线下AUC的面积为0.6213，即研究区泥石流易发性的预测准确性达$6 2 . 1 3 \%$ ，表明此次泥石流预测结果未达到较为理想的效果。分析误差产生的主要原因为此次泥石流易发性预测评价单元以栅格为主，评价过程将泥石流流域分割成若干个栅格单元，未考虑泥石流流域特征，导致各评价因子定量化的精度受到影响。

据刘希林等[研究认为，泥石流灾害易发性评价结果的合理性应满足以下条件： $\textcircled{1}$ 灾害点落在越高等级易发区，其百分比越大越合理; $\textcircled{2}$ 灾害点落在越低等级易发区，其面积百分比越大越合理; $\textcircled{3}$ 灾害点在各等级易发区的百分比与各等级易发区面积占总面积百分比的比值即频率比应该随易发区等级的增高而增大。从表5可以看出，两种计算结果都完全满足条件 $\textcircled{1} \textcircled{3}$ ,而本文评价结果虽总体上符合检验条件 $\textcircled{2}$ 的要求，但低易发区以下分区面积百分比小于中高易发区面积百分比。而文献[19]分区结果中高易发区面积百分比远大于低易发区以下分区面积百分比，检验曲线下AUC的面积为0.4338。

![](images/96e5112949b8a1a2941e9912e5ea6f410e4dbd9a9c2db339fd2329dd1d6ec800.jpg)  
Fig.6Assessment of debris flow susceptibility   
图7泥石流易发性评价结果检验曲线 Fig.7Graph showing the success rate of assessment of debris flow susceptibility

表5泥石流易发性评价结果对比分析  
Tab.5Comparative analysis of the evaluated results of debris flow susceptibility   

<html><body><table><tr><td rowspan="2">易发区分级</td><td colspan="5">本文研究结果</td><td colspan="5">文献[19]研究结果</td></tr><tr><td>易发区面积/ km²</td><td>易发区面积 百分比/%</td><td>泥石流 点数/处</td><td>泥石流 百分数/%</td><td>频率比</td><td>易发区面积/ km²</td><td>易发区面积 百分比/%</td><td>泥石流 点数/处</td><td>泥石流 百分数/%</td><td>频率比</td></tr><tr><td>高易发区</td><td>452.44</td><td>21.83</td><td>79</td><td>39.11</td><td>1.79</td><td>793.52</td><td>38.28</td><td>135</td><td>66.83</td><td>1.75</td></tr><tr><td>中易发区</td><td>605.50</td><td>29.21</td><td>76</td><td>37.62</td><td>1.29</td><td>968.62</td><td>46.73</td><td>56</td><td>27.72</td><td>0.59</td></tr><tr><td>低易发区</td><td>568.44</td><td>27.42</td><td>34</td><td>16.83</td><td>0.61</td><td>197.99</td><td>9.55</td><td>10</td><td>4.95</td><td>0.52</td></tr><tr><td>不易发区</td><td>446.52</td><td>21.54</td><td>13</td><td>6.44</td><td>0.30</td><td>112.76</td><td>5.44</td><td>1</td><td>0.50</td><td>0.09</td></tr></table></body></html>

由此得出，虽然文献[19]评价结果基本上合理，但从形成泥石流的孕灾背景条件出发，基于Arc-GIS的层次分析模型对研区进行泥石流易发性分区评价结果更为合理。主要是因为本文在评价过程中不仅选取了松散物源面密度和沟床比降两个形成泥石流的关键因子，也考虑了地震和降雨等动态致灾因子，而文献[19]认为道路是影响泥石流灾害的最主要因子，但泥石流松散物源大多发育在泥石流的形成区及流通区，受道路的影响较小，而且评价指标未充分考虑泥石流形成的固体松散物质空间分布和泥石流沟床比降情况，

# 4结论

（1）研究区以中山为主的峡谷区，大部分区域坡度在 $1 5 ^ { \circ } \sim 4 0 ^ { \circ }$ ,岩性软弱,以千枚岩和板岩为主，易形成泥石流滑坡和崩塌补给泥石流。同时该区气候条件干湿明显，岩石物理风化作用强烈，在软弱浅变质岩区斜坡变形破坏极为严重，促使斜坡地带发育丰富的浅层松散堆积物，在极端强降雨条件下容易激发形成泥石流灾害。基于研究区野外调查的泥石流数据库信息和遥感解译资料，选取11个评价因子建立了白龙江流域石门乡至羊汤河段泥石流易发性评价指标体系，在ArcGIS平台下基于AHP模型对研究区泥石流灾害易发性进行了评价与分析。

（2）该区泥石流中高易发区主要为松散物质丰富区，地层岩性较为软弱的地区，土地利用类型为旱地和草地坡面侵蚀程度强的区域。构造断裂、水系作用也对泥石流灾害的孕育有着至关重要的影响，主要体现为沿大型活动性断裂呈带状分布，在次级断裂和小型褶皱密集区集中发育，在沟壑密集带集中分块、分区发育。易发性分区结果亦表明研究区南北两侧泥石流易发性受控的影响因子不同，泥石流性质亦有差异，北部主要以黏性泥石流为主，而南部则多为稀性泥石流。

（3）根据实际情况和评价结果检验曲线分析，该区泥石流易发性的预测准确率为 $6 2 . 1 3 \%$ ，评价结果较为可靠。对泥石流易发性评价而言，评价因子权重的确定是评价过程的关键内容，但本文在确定因子权重时采用了AHP法，虽然这种方法便捷，但其权重确定中不可避免地存在主观性，其合理性还有待于进一步论证。再者参评因子选取及空间化数据的不确定性，因子层级划分的主观性，对评价结果具有一定的影响。因此，后续需更科学地建立甘肃境内白龙江干流泥石流灾害评价体系及方法。

# 参考文献(References）:

[1]Hollingsworth R,Kovacs G S.Soil slumps and debris flows:Prediction and protection e[J].Bulletin of the Assocition of Engineering Geologists,1981,38(1） :17 -28.   
[2]Carrara A,Cardinali M,Guzzetti F. Uncertainty in assessing landslide hazard and risk[J].ITC Journal,1992,2:172-183.   
[3]岳溪柳,黄玫,徐庆勇,等.贵州省喀斯特地区泥石流灾害易发 性评价[J].地球信息科学学报,2015,17（11）:1395－1 403. [Yue Xiliu,Huang Mei,Xu Qingyong,et al.The susceptility assessmeng of debris flow in Karst Region of Guizhou province[J]. Journal of Geo-Information Science,2015,17（11）：1 395- 1 403.]   
[4]黎艳,陈剑,许冲,等.基于AHP 的半干旱区泥石流易发性评 价——以金沙江上游奔子栏－昌波河段为例[J].现代地质， 2015,29(4):975-982.[Li Yan,Chen Jian,Xu Chong,et al. Susceptibility assessmeng of debris flow in the semiarid region based on AHP method;An example from the Benzilan-Changbo segmeng of the Upper Jinsha river[J].Geoscience,2015,29（4）： 975 -982.]   
[5]孟凡奇,李广杰,秦胜伍,等.基于证据权法的泥石流危险度区 划[J].吉林大学学报（地球科学版）,2010,40（6)：1380- 1384.[Meng Fanqi,Li Guangjie,Qin Shengwu,et al. Zoning of debris flow hazard degree with weigth of evidence method[J]. Journal of JilinUniversity(Earth ScienceEdition）,2O10,40（6）： 1380 -1384.]   
[6]张若琳,孟晖,连建发.基于GIS 的中国泥石流易发性评价 [J].成都理工大学学报（自然科学版）,2013,40（4）:379－ 386.[Zhang Ruolin,Meng Hui,Lian Jianfa. Susceptibility evaluation of debris flow in Chian based on GIS[J].Journal of Chengdu University of Technlology（Science $\&$ Technology Edition）,2013, 40(4) :379 -386.]   
[7]刘希林,庙成,田春山.区域滑坡和泥石流灾害两种危险性评 价方法的比较分析[J].防灾减灾工程学报,2017,37（1)：71- 78.[Liu Xilin,Miao Cheng,Tian Chunshan.Comparative analysis of two methods for assessment hazard of landslide and debris flow on a regional scale[J]. Journal of Disaster Prevention and Mitigation Engineering,2017,37（1）:71-78.]   
[8]贾贵义,全永庆,黎志恒,等.基于组合赋权法的白龙江流域甘 肃段地质灾害危险性评价[J].冰川冻土,2014,36（5）：1 227 -1 236.[Jia Guiyi,Quan Yongqing,Li Zhiheng,et al. Geo-hazards assessment for the Gansu segment in Bailongjiang river basin by using combination weighting method[J].Journal of Glaciology and Geocryology,2014,36(5）:1 227 -1 236.]   
[9]宁娜,马金珠,张鹏,等.基于GIS 和信息量法的甘肃南部白龙 江流域泥石流灾害危险性评价〔J].资源科学,2013,35（4）： 892-899.[Ning Na,Ma Jinzhu,Zhang Peng,et al.Debris flow

hazard assessment for the Bailongjiang River,Southern Gansu[J]

Resources Science,2013,35(4） :892-899.」   
[10]刘林通，孟兴民,郭鹏.等.基于流域单元和信息量法的白龙江 流域泥石流危险性评价〔J].兰州大学学报（自然科学版）， 2017,53(3）:292-298.[Liu Lintong,Meng Xingmin,Guo Peng, et al.Assessment of debris flow hazards in the Bailongjiang river based on the watershed unit and information value method[J]. Journal of Lanzhou University(Naturnal Sciences Edition）,2017, 53(3) :292 -298.]   
[11]陈玉.基于经验权重方法的舟曲县泥石流易发性评估[J].防 灾科技学院学报,2013，15（4）：54-60.［ChenYu.Debris flow susceptibility assessment of Zhouqu Gansu,China based on experience weight method[J].Journal of Institute of Disaster Prevention, 2013,15(4) :54 -60.]   
[12］柳金峰,黄江成,欧国强,等.甘肃陇南武都区泥石流易发性评 价[J].中国地质灾害与防治学报,2010,21（4)：8-13.［Liu Jinfeng,Huang Jiangcheng,Ou Guoqiang,et al.Susceptility evaluation of debris flow in the Wudu District,Longnan City,Gansu Province[J].The Chinese Journal of Geological Hazard and Control, 2010,21(4):8-13.]   
[13]孟兴民，陈冠，郭鹏,等.白龙江流域滑坡泥石流灾害研究进展与 展望[J].海洋地质与第四纪地质,2013,33（4)：1-15.[Meng Xingming,Chen Guan,Guo Peng,et al.Research of landslides ans debris flow in Bailong river basin:Progress and prospect[J].Marine Geology & Quaternary Geology,2013,33(4):1-15.]   
[14]刘传正，苗天宝，陈红旗,等.甘肃舟曲2010年8月8日特大山 洪泥石流灾害的基本特征及成因[J].地质通报,2011,30（1)： 141-150.[Liu Chuanzheng,Miao Tianbao,Chen Hongqi,et al. Basic feature and origin of the“8.8”mountain torrent-debris flow disaster happened in Zhouqu County,Gansu,China[J].Geological

Bulletin of China,2011,30(1):141-150.]

[15]林虹宇，丁明涛，佘涛,等.岷江上游典型泥石流活动特征及其 易发性评价[J].中国地质灾害与防治学报，2017，28（4)：6- 14.[Lin Hongyu,Ding Mingtao,She Tao,et al. Characteristic analysis and susceptibility assessment of the typical debris flow in the upper reaches of Min River[J].The Chinese Journal of Geological Hazard and Control,2017,28(4):6-14.]   
[16]黄诗峰,钟邵南,徐美.基于GIS 的流域土壤侵蚀量估算指标 模型方法——以嘉陵江上游西汉水流域为例[J].水土保持学 报,2001,15(2）:105-107.[Huang Shifeng,Zhong Shaonan, $\mathrm { X u }$ Mei.Categorical modal od estimating soil erosion based on GIS:A case study in Xihanshui Watershed[J].Journal of Soil and Water Conservation,2001,15(2):105-107.]   
[17］彭建,李丹丹，张玉清.基于GIS 和RUSLE的滇西北山区土壤 侵蚀空间特征分析——以云南省丽江县为例[J].山地学报， 2007,25(5）:548-556.[Peng Jian,Li Dandan,Zhang Yuqing. Analysis of spatial characteristics of soil erosion in mountain areas of Northwestern Yunnan based on GIS and RUSLE[J].Journal of Mountan Science,2007,25(5):548-556.]   
[18」王高峰,高幼龙，王洪德,等.基于图幅调查的六盘山镇滑坡易 发性研究[J].科学技术与工程,2017,17（36）:22-29.[Wang Gaofeng,Gao Youlong,Wang Hongde,etal.Analyses on landslide susceptibility of Liupanshan town based on map sheet survey[J]. Science Technology and Engineering,2017,17（36）:22-29.]   
[19］黎志恒,贾贵义,张永军,等.甘肃省白龙江流域主要城镇环境 工程地质勘查报告[R].兰州：甘肃省地质环境监测院，2013. [Li Zhiheng,Jia Guiyi,Zhang Yongjun,et al.Report of Environmental Engineering Geological Exploration of Main Towns in Bailong River Basin,Gansu Province[R].Lanzhou:Institute of Geological and Environmental Monitoring,Gansu Province,2O13.]

# Establishment of Assessment Model for Debris Flow Susceptibility :A Case Study Along the Yangtang River Reach in Shimen Township in the Bailong River Basin

WANG Gao-feng， YANG Qing， TIAN Yun-tao， YE Zhen-nan， CHEN Zong-liang, GAO You-long，GUO Ning，DENG Bing (Center for Hydrogeologyand EnvironmentalGeology Survey,China GeologySurvey,Baoding O71051,Hebei,China)

Abstract：In this study,the hierarchyanalysis,GIS means and normalizedvalues of9 evaluation factors,such as loose material surface density,stratigraphic lithology,tectonic fracturedensity,seismic density,slopeaspect,soil erodibility,land use type,slopelength and gradient,gully bed slope andgullydensity,and average annualrainfall, were used.The purposes of the study was to develop anassessment model for debris flow susceptibility along the Yangtang river reach in Shimen Township inthe Bailong River Basin.Finally,thegrid diagram of assesing debris flowsusceptibilityin the study area was divided into 4 grades.Theresults showed that the proportion of the areas with high debris flow susceptibility accounted for $5 1 . 0 4 \%$ of the whole study area,and the areas with mid-high debris flow susceptibility accounted for $6 8 . 7 1 \%$ . The debris flows were distributed along the large active fault zones ,especially in the zones with intensive secondary fracturesand smallfolds.They were alsodistributed along the slidable strata,especiall in the zones with dense gullies.Debris flow occurred easilyon the slopes with high soil erosion.The results were tested by the database of debris flow in the study area.

Key words:：debris flow；susceptibility assessment；analytic hierarchy process；model development；Bailong River Basin