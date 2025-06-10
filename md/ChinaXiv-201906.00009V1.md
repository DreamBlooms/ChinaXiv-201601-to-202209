# 不同空间尺度的山洪灾害风险评价模型对比研究

田丰¹，张军²，冉有华³，刘金鹏4，周翼²

（1北京师范大学地理科学学部,北京100875；2 甘肃农业大学资源与环境学院,甘肃兰州 730070;中国科学院西北生态环境资源研究院,甘肃兰州730000；4甘肃省科学院地质自然灾害防治研究所,甘肃兰州 73000摘要：以山洪灾害风险评价的多准则决策模型、最大熵模型、信息量模型三种常见模型为研究对象,选取河西走廊和张掖市为地理区划(大中）、市域(小)空间尺度研究区，构建山洪灾害风险评价指标体系,分别完成基于三种模型的两种空间尺度的山洪灾害风险评价制图,基于甘肃省地质灾害调查与区划报告数据从模型验证、空间自相关、精度对比和尺度效应等角度对比分析三个模型应用于不同空间尺度的适应性，并给出优选模型。结果表明：最大熵模型是河西走廊(地理区划)空间尺度上山洪灾害风险评价的优选模型;多准则决策模型不适用于张披市(市域)空间尺度评价，且三个模型运行结果均没有河西走廊(地理区划)空间尺度上表现良好;三个模型的尺度效应明显，在地理区划空间尺度上应用较良好,缩小至市域空间尺度上模拟结果误差增大;不同空间尺度上，最大熵模型均优于多准则决策模型和信息量模型，适用于地理区划（大中）、市域（小)空间尺度的山洪灾害风险评价。

关键 词：山洪灾害；风险；空间尺度；模型适应性；模型对比文章编号： 1000-6060(2019)03-0559-11(0559\~0569)

山洪灾害对区域社会经济发展极为敏感，危害极大[1]。我国是一个多山的国家,山地面积占我国国土面积的2/3，加之我国降水时空分布不均，南北地域差异明显，且降水时段集中，山洪灾害频发，成为山区生命财产安全的主要威胁之一，因此，山洪灾害风险研究成为灾害防治与预警的关键问题和首要环节[2],并成为国内外学者关注的焦点,在风险理论[3-4],研究方法[5-6]等方面取得了显著成果,但由于山区环境复杂多样，山洪要素的不确定性，加之评价方法选取的适应性考虑欠佳，评价结果难以接近风险实际观测值，因此，研究山洪灾害风险评价方法选取及适应性显得尤为重要，且成为当前研究的难点之一。

纵观山洪灾害风险评价的发展历程，其方法创新及应用经历了两个发展阶段。第一阶段：早期基于联合国救灾组织1982年提出的风险理论的二元加权模型[7],理论将灾害风险系统分为致灾因子和孕灾环境危险性、承灾体易损性二个风险子系统，唐川[8]基于二元加权模型较早地开展了红河流域山洪灾害风险区划制图，模型具有良好的评价效果；杜俊基于二元风险理论进行模型演化,运用四种演化模型展开长江流域山洪灾害风险评价，并进行模型优化推演至全国，完成了全国大空间尺度的山洪灾害风险区划，结果显示，在不同空间尺度下，山洪影响因子作用机制发生变化，即模型产生尺度效应。第二阶段：基于地理空间技术的风险预测模型[10]GIS等地理信息技术的应用为高分辨率的大空间尺度山洪灾害风险评价建模及应用提供了支持，借助GIS 平台运行的最大熵模型[11]、信息量模型[2]、BP神经网络[13]、DEA[14]等预测模型,基于水文要素分析的膨胀算子[15]、FloodArea 模型[16]、种子蔓延算法[17]等水动力模拟模型被国内学者广泛应用至该领域，不断完善山洪灾害风险研究体系。但以上研究都是针对单一方法的区域应用，缺乏不同空间尺度上的不同模型的结果差异对比及模型适应性分析，基于此，本文选取两类模型中三种常见模型：多准则决策模型、最大熵模型和信息量模型作为研究对象，在地理区划(大中)和市域(小)两种空间尺度上进行风险评价，基于历史山洪灾害数据设计模型对比方案，探究不同模型在不同空间尺度上应用的适应性及尺度效应，并给出优选模型，研究结果以期为不同空间尺度的地质灾害风险评价模型选取提供科学参考。

# 1模型方案

# 1.1 模型原理

1.1.1多准则决策模型多准则决策模型是基于一般线性加权模型进行GIS 模块集成化的多因子分析模型，模型借助美国克拉克大学克拉克实验室（Clark Labs)开发的 IDRISI软件运算[18],多准则决策支持模型的一般步骤是：FUZZY模块数据标准化,WEIGHT权重计算，MAC加权合并（表1），基本数学模型为：

$$
R = \ \sum _ { i = 1 } ^ { n } { { { H } _ { i } } \times { { W } _ { i } } }
$$

式中： $H _ { i }$ 表示第 $i$ 个风险因子， $\textstyle \mathbf { \textit { W } } _ { i }$ 表示第 $i$ 个风险因子的权重。

1.1.2 最大熵模型 最大熵(Maximum Entropy，简称 MaxEnt)模型是基于最大熵理论[19],分析提取事物"出现点”影响环境变量，寻求在此约束条件下“未知点”最大熵的可能性分布，主要用于物种潜在生境分布预测模型[20]。构建模型需要已知点和环境变量两组数据，模型生成受试者ROC曲线，以曲线与横坐标所围矩形面积 $A U C$ 值检验模型精度。若 $A U C \in \left( 0 . 7 5 , 1 \right]$ ,即模型可用。

模型计算过程为：

$$
H _ { i } = - \sum _ { i = 1 } ^ { n } P ( x _ { i } ) \times \ln ( x _ { i } )
$$

式中： $H p$ 表示最大熵值， $x _ { i }$ 表示第 $i$ 个环境变量， $P$ $\left( \boldsymbol { x } _ { i } \right)$ 表示环境变量 $x _ { i }$ 可能出现的概率。

最大熵的概率分布即为：

$$
P = \arg \left[ \operatorname* { m a x } ( H _ { p } ) \right]
$$

1.1.3信息量模型信息量模型是以信息量理论为基础，通过分析评价要素的影响因子作用机理来寻求各环境变量“最佳组合"（贡献率最大)时评价要素信息量，以此预测未知区域评价要素分布情况的多因子综合评价方法[2I]。构建河西走廊山洪灾害风险信息量模型过程为：

$$
I ( H _ { i } , M T ) = \ln \frac { N _ { i } / \mathrm { \Delta } N } { S _ { i } / \mathrm { \Delta } S }
$$

式中： $s$ 表示研究区评价单元总面积， $N$ 表示研究区内山洪灾害单元面积， $S _ { i }$ 表示研究区内含有风险因子 $H i$ 的评价单元面积， $N _ { i }$ 表示研究区分布在风险因子 $H _ { i }$ 内的山洪灾害评价单元面积。

计算河西走廊单个评价单元总信息量：

$$
I = \ \sum _ { i = 1 } ^ { n } I ( H _ { i } , M T ) \ = \ \sum _ { i = 1 } ^ { n } \ln \frac { N _ { i } / \ N } { S _ { i } / \ S } \times W _ { i }
$$

# 1.2 模型结构

1.2.1因子输入山洪灾害受地质、地形地貌、水文气候、土壤和植被等主控因子共同作用，是致灾因子、孕灾环境和承灾体达到“最佳组合”时的结果[22]。研究根据山洪灾害发生的机制,选取致灾因子(3\~11月降水量 ${ } , 6 \sim 9$ 月 $0 \sim 2 4 \mathrm { ~ h ~ }$ 累计最大降水量）、孕灾环境(高程标准差、坡度、地貌类型、植被覆盖度 $\cdot 0 \sim 3 0 ~ \mathrm { c m }$ 粘粒含量 $\cdot 0 \sim 3 0 ~ \mathrm { c m }$ 砂粒含量、河网密度）、承灾体（土地利用/覆被变化、GDP、人口密度)12个风险因子（表2）。

驱动变量：3\~11月降水量、6\~9月 $0 \sim 2 4 \mathrm { ~ h ~ }$ 累计最大降水量

地形地貌变量：高程标准差、坡度、地貌类型植被变量：植被覆盖度

土壤变量：表层 $0 \sim 3 0 ~ \mathrm { c m }$ 粘粒含量 $\cdot 0 \sim 3 0 \ \mathrm { c m }$ 砂粒含量

水文变量：河网密度

社会经济变量：土地利用/覆被变化、GDP、人口密度

多准则决策模型对数据大小有要求，栅格数据分辨率太高，模型输入数据无法运行，因此，研究确定该模型输入数据栅格像元为 $1 \ \mathrm { k m } \times 1 \ \mathrm { k m }$ ,最大熵模型和信息量模型像元为 $3 0 \mathrm { ~ m ~ } \times 3 0 \mathrm { ~ m ~ }$ ,投影坐标系为WGS_1984_UTM_Zone_ $\ 、 4 8 \mathrm { N }$ 。

1.2.2数据来源地形数据是2010年ASTER发布的GDEMV230m高分辨率数字高程模型数据产品,数据来源于美国地质调查局（www.usgs.com）；地貌数据是中国100万地貌类型空间分布数据，来源于中国科学院资源环境科学数据中心（http：//www.resdc.cn）；土壤数据是中国土壤特征数据集[23],数据来源于国家自然科学基金委“中国西部环境与生态科学数据中心"（http：//westdc.westgis.

表1三种模型属性结构  
Tab.1Property structure of three models   
表2山洪灾害风险评价指标体系  

<html><body><table><tr><td></td><td>数学原理</td><td>适用条件</td><td>数据格式</td><td>数据大小</td><td>空间分辨率</td><td>运行软件</td></tr><tr><td></td><td>多准则决策模型加权求和函数Σx·w</td><td>多因子分析</td><td>连续栅格/.RST</td><td>≤500 MB</td><td>中低分辨率</td><td>IDRISI.K. v14.0.1</td></tr><tr><td>最大熵模型</td><td>最大评分参量函数argmax(x)</td><td>单、多因子分析</td><td>ASCII栅格/.ASC</td><td>GIS大数据</td><td>高分辨率</td><td>MaxEnt3.3.3 k</td></tr><tr><td>信息量模型</td><td>自然对数函数ln(x)</td><td>单、多因子分析</td><td>连续栅格/.GRID</td><td>GIS大数据</td><td>高分辨率</td><td>ArcGIS10.2</td></tr></table></body></html>

Tab.2Mountain torrent disaster risk assessment index system   

<html><body><table><tr><td>指标属性</td><td>类型</td><td>名称/代码</td><td>数据名称</td><td>数据类型／单位</td></tr><tr><td rowspan="2">致灾因子</td><td rowspan="2">降水</td><td>3~11月降水量</td><td>中国区域高时空分辨率地面气象要素驱动数据集</td><td>连续／mm</td></tr><tr><td>6~9月0~24h累计最大降水量</td><td>SWAT模型中国大气同化驱动数据集CMADSV1.1</td><td>连续／mm</td></tr><tr><td rowspan="4">孕灾环境</td><td>地形</td><td>高程标准差</td><td>GDEMV2</td><td>连续／m</td></tr><tr><td>地貌</td><td>坡度 地貌类型</td><td>中国100万地貌类型空间分布数据</td><td>连续／</td></tr><tr><td>植被</td><td>植被覆盖度</td><td>MOD13A2</td><td>分类 连续／%</td></tr><tr><td>土壤</td><td>表层0~30cm 粘粒含量</td><td>中国土壤特征数据集</td><td>连续／%</td></tr><tr><td rowspan="5">承灾体</td><td></td><td>表层0~30cm 砂粒含量</td><td></td><td>连续／%</td></tr><tr><td>水文</td><td>河网密度</td><td>GDEMV2</td><td>连续／km·km-2</td></tr><tr><td>社会经济</td><td>土地利用/覆被变化</td><td>2015年中国土地利用现状遥感监测数据</td><td>分类</td></tr><tr><td></td><td>GDP</td><td>2010 年中国GDP空间分布公里网格数据</td><td>连续／元·km-2</td></tr><tr><td></td><td>人口密度</td><td>2010 年中国人口空间分布公里网格数据</td><td>连续／人·km-2</td></tr></table></body></html>

ac.cn);降水数据是中国区域高时空分辨率地面气象要素驱动数据集[24],SWAT模型中国大气同化驱动数据集（CMADSV1.1）[25]，时间尺度是2014年，数据来源于中国寒区旱区科学数据中心（http：//westdc.westgis.ac.cn）;植被数据是MODIS植被指数产品MOD13A2，数据来源于美国地质调查局陆面分布式数据中心（www.usgs.gov）;社会经济数据是2015 年中国土地利用现状遥感监测数据,2010 年中国GDP、人口空间分布公里网格数据，来源于中国科学院资源环境科学数据中心（http://www.resdc.cn）。1.2.3精度评价精度评价是建模适应性判断的最直接依据，精度值低于评判分值，即建模失败，模型不可采用。本文利用文献资料法和统计数据对比分析法进行三种模型精度评价，本文基于山洪灾害历史统计数据统计落在风险等级内的山洪灾害点数据，以落在极高、高风险等级内的山洪灾害条数占样本总量的比例为评价依据,精度值低于0.6,表明此模型结果不可采信。

# 2 研究区概况

河西走廊 $( 9 2 ^ { \circ } \sim 1 0 3 ^ { \circ } \mathrm { E } , 3 6 ^ { \circ } \sim 4 2 ^ { \circ } \mathrm { N } )$ 位于甘肃省西北部，是丝绸之路经济带的陆上咽喉要地和黄金段,在“一带一路”国家倡议中，区位重要;也是甘肃省四大生态屏障之“河西内陆河屏障区”，生态环境脆弱，地形起伏明显，山脉连绵，山区面积广阔，降水变率大，地质灾害频发。南部乌鞘岭一祁连山一阿尔金山一带和北部马鬃山—龙首山—合黎山一带山脉连绵，山麓地带地形雨明显，加之雪山融水丰沛，河网发达，依河而建的河谷城市群人口密度大，山洪灾害风险高[],因此,本文确定河西走廊为地理区划（大中)空间尺度研究区，区位特殊(图1）。

张掖市位于河西走廊的腹部中心，是河西走廊经济较发达的城市之一，下辖山丹、民乐、高台、临泽和肃南裕固族自治县5县，中部平原地区土地肥沃，物产丰饶;肃南，山丹和民乐山区面积大，山洪灾害风险高，因此，本文确定张掖地区为市域(小)空间尺度研究区，地区典型。

本文以ArcGIS10.2为平台，利用其空间分析工具分别建立河西走廊和张掖市风险因子空间分布图层(图2、图3）。

# 3模型对比

# 3.1 模型结果

运行三种模型，分别生成三种模型在河西走廊和张掖市两个空间尺度上的山洪灾害风险数据，根据研究区山洪灾害发生特征划分风险等级（表3），

93°0'0"E 96°0'0"E 99°0'0"E 102°0'0"E 97°30'0"E 99°0'0"E 100°30'0"E 102°0'0"E(a)地理区划(大中)空间尺度 44.000N (b市域(小)空间尺度N N  
N.0.00 成 W WE N.0.0.68 白 WE N.0.0.68阿 华 敦煌市 族自治县 玉门市 嘉峰关市酒泉市 黎山金塔县 N.0.0O 族白治县张报 。 张披市G 山丹县台县图例 山丹县 N.0.0.88 图例 民乐县  
8.0.00.8 河西走廊海拔/m 界线 鑫昌市民勤县 武威 80.00.00 张掖市海拔/m 界线 2.0.0.88高：5774 0 100 200km 古浪县 高：5574 0L 50 100km  
93°0'0"E 96°0'0"E 99°0'0"E 102°0'0"E 97°30'0"E 99°0'0"E 100°30'0"E 102°0'0"E

完成基于三种模型的河西走廊和张掖市山洪灾害风险评价图（图4）。

# 3.2 模型验证

研究[11,26-27]表明,河西走廊山洪灾害频发区分布在酒泉肃北山区，张掖肃南山区，武威凉州区黄羊镇、西营村、南营村一带和民勤县石羊河水库库区等地区，山洪灾害风险呈现自东南向西北荒漠地区，走廊南北两侧山区向中部平原地区逐渐递减空间分布特征。多准则决策模型运行结果显示，河西走廊山洪灾害极高、高风险区主要是东起乌鞘岭，西至祁连山南侧山区一带和走廊东段大部分地区，呈带状连续性分布，与降水、植被覆盖度等风险因子成正相关性；最大熵模型和信息量模型结果中的极高风险分布区域相似度较高，分布在古浪北部，凉州区中部,山丹，民乐和高台中部地区，以及酒泉肃州区，金塔部分地区和阿尔金山北侧阿克塞北部地区，高风险区则呈现明显的分异性，最大熵模型是以极高风险地区为中心向南侧山区一带南移分布，信息量模型则是酒泉市肃州区以东的走廊大部分地区，最大熵模型和信息量模型结果块状非连续性分布特征显著，然而，信息量模型结果显示武威民勤县高风险分布地区广泛，然而，民勤县干旱少雨，多为平原区，除石羊河水库区因河网发达，地形起伏较大，山洪灾害风险较高外,多为山洪灾害少发区，由此可见，信息量模型运行结果误差较大，而最大熵模型更符合山洪灾害发生的实际情况，能更加客观地进行河西走廊山洪灾害风险分区防治与预警。

本文基于山洪灾害历史统计数据统计落在风险等级内的山洪灾害点数据，以其与山洪总数量比值为结果验证标准，落在极高和高风险区的山洪数量比值越高，精度越高，反之亦然(表4)。河西走廊样本总量385条，张掖市样本总量180条，河西走廊落在极高和高风险等级的历史山洪灾害数量比值排序为：最大熵模型(0.92）信息量模型（0.72）、多准则决策模型(0.69）;张掖市占比排序为：最大熵模型(0.9）、信息量模型（0.69）、多准则决策模型中 $3 8 . 8 9 \%$ );河西走廊山洪灾害验证点数量占比均大于0.6，表明三种模型运行结果可采信度较高；张掖市山洪灾害验证点数量占比中，多准则决策模型0.39，表明此模型不适用于市域(小)空间尺度评价；在两种空间尺度上，最大熵模型验证结果均最高。

# 3.3 空间相关性分析

为了进一步验证三种模型评价精度，本文使用全局Moran指数计算三种模型方案相邻县域栅格单元风险均值的空间相关性，以此反映河西走廊县域尺度内山洪灾害空间全局自相关性，相关性程度越高，表明此模型精度越高。

利用Geoda软件计算可得，三种模型应用于河西走廊的Z-value均大于1.96,表明统计结果可采信,且分布类型为聚集[9],从图5a可以看出,两种预测模型的Moran指数线斜率大于一般模型，表明相邻县域单元空间相关性更大，模型更易采用;最大熵模型和信息量模型明显优于多准则决策模型，最大熵模型的Moran's $I$ 值最高，为0.6798，即相关性最高，是地理区划(大中)空间尺度的优选模型。

张掖市相邻县域单元风险值Moran指数中，多准则决策模型最高，值为0.1949，最大熵模型和信息量模型Moran指数为负值（图5b），表明两种预测

95°E 100°E 95°E 100°E  
N WE S NZ NoI N WE N  
N68 NoOV N68 NoOV  
2 50100200km N88 200m N8895°E 100°E 95°E 100°E95°E 100°E 95°E 100°E  
NI WE N NI WE  
N68 No0V N68 NoO  
N8 低： 高程标准值 050100200km N88 N 3 坡度高84.1379 低：0 05010020k8m N8895°E 100°E 95°E 100°E95°E 100°E 95E 100°EN 低海拔丘陵小起伏低山  
N WE 满 NoI WE S N  
N68 地貌类 大起优 极高山 NoO N68 NO  
N8 N88 高：708144050100200km 一km N.8895°E 100°E 95°E 100°E95°E 100°E 95°E 100°E  
NI WE NZ NoI WE N  
N68 NoOV N NoOV  
N N88 3N 0- N8895°E 100°E 95°E 100°E95°E 100°E 95°E 100°E地利用/覆盖其他  
NI WE N N WE 旱地 1有林地S地  
N68 欢 NoOV N.68 农村居民点 川雪地 NoO其他建设用地  
N8 00 N88 050100200k N8895°E 100°E 95°E 100°E95°E 100°E 95°E 100°E  
NI WE N N N  
N68 NoOV N68 N0  
N8 GDP 45721050000 N88 28 人口密度值 高：19849 0_50100200m N8895°E 100°E 95°E 100°E95°E 100°E 95°E 100°E 102°EW N NoOVWE  
N68 N.68 N68 S N68  
3\~11月降水量值 高：175.3895 0204080km N8 N.88 最降水量 高：26.854 020.40 80 N8895°E 95°E 100°E 100°E 102E 102°Ez 95°E 95°E 100°E 100°E 102°E EWE 0  
N68 N68 N68 N.68  
高程标准差 低：0 高：116.144 020.40 8km N88 N.88 坡度 低：0 高：79.5063 0_20408km N8895°E 100°E 102°E 95°E 100°E 102E95°E 100°E E 95°E 100°E 102°E绿红 大起优中山 WE WE N0  
N.68 大起伏极高山 N68 N68 N68地貌类型低海拔平原低海拔台地中海拔平原中海拔6台  
N88 二 N.88 特N88 植被覆度 N88极高海拔兵陵小起伏极高山 低：0 020400km G595°E 100°E 102°E 95°E 100°E 102°E95°E 95°E 100°E国  
N68 N68  
N88 表0cm 香 0cmN 8 N88低：0 高：32.916 020400km 8 低：0 高：96.953 02040 8km95°E 100°E 102°E 95°E 100°E 102°E95°E 100°E 95°E 100°E 102°EWE WE NoOV  
Z N68  
3 N.68 N68土地用/覆盖变化有林  
N88 河网密度 高：0.488 129 N88 N88 地 WC 速川雪地 地 石质地 N88低：0 0.2040 80 地 点 02040 8kmkm95°E 100°E 102°E 95°E 100°E 102°E95°E 100°E 95°E 100°E 102°EN N NOWE WE  
N68 店 N68 N.68 N68  
N.88 GDP N88 8.88 人口密度 N88：10454.6 02040 Skm 高：12892 020.40 Skm95°E 100°E 102°E 95°E 100°E 102°E河西走廊 张掖市94°E 96°E 98°E 100°E 102°E 104Ez 98E 99E 100°E 101°E 102Ez  
NZ (a)IDRISI多准则决策模型 4 (a)IDRISI多准则决策模型 40  
NI WE N 高台县 WE  
NoO 瓜州县 S N N68 临泽县 S N.68敦煌市 ? 玉门市 肃南裕固族自治县 张掖市  
N68 阿克塞哈萨克族族自治 嘉峪关市金塔县 酒泉市 No0 区/县 县市/县 行政区  
N88 风 肃南裕固族 斗 N68 N 险风  
N8 凤 极高风险 050100 I 200km 民勤县 N.88 88 险 02550 100km N8894°E 96E 98°E 100°E 102°E 104°E 98E 99°E 100°E 101°E 102°E94°E 96°E 98E 100°E 102°E 104Ez 98E 99E 100E 101°E 102E  
N (b)最大熵模型 4 (b)最大熵模型  
N WE N 高台县 WE  
NO 瓜州县 S N N68 S N68敦煌市 玉门市  
N.68 哈萨克族族自治关 高台县 NoO  
N88 肃南裕固族自治 丹县 N.68 N88  
N28 三风 □ 极高风险 050100 200km 昌市民動县 N88 ■极高风险 02550 100km N8894°E 96°E 98E 100°E 102°E 104°E 98E 99E 100°E 101°E 102°E94°E 96°E 98°E 100°E 102°E 104°E 98E 99°E 100°E 101°E 102°E  
N (c)信息量模型 (c)信息量模型  
N # WE N 高台 WES NI N68 S  
No0V 敦煌市 瓜州县 N68玉门市 肃南裕固族阿克塞哈萨克族自治县 金塔 NoO 丹县  
N68 肃北蒙古族自治县 酒泉市  
188620 1 市 市 868N.88 N88 维 N8802550 100km94°E 96°E 98E 100°E 102E 104°E 98°E 99°E 100°E 101E 102E

表3不同空间尺度的三种模型风险等级划分标准  
Tab.3Mountain torrent disaster risk level division standard of three models   

<html><body><table><tr><td></td><td>空间尺度</td><td>极高风险</td><td>高风险</td><td>中风险</td><td>低风险</td></tr><tr><td rowspan="2">多准则决策模型</td><td>河西走廊</td><td>≥120.00</td><td>86.08~120.00</td><td>63.03~86.08</td><td>≤63.03</td></tr><tr><td>张掖市</td><td>≥100.00</td><td>65.00~100.00</td><td>65.00~40.00</td><td>≤40.00</td></tr><tr><td rowspan="2">最大熵模型</td><td>河西走廊</td><td>≥0.48</td><td>0.21~0.48</td><td>0.08~0.21</td><td>≤0.08</td></tr><tr><td>张掖市</td><td>≥0.40</td><td>0.14~0.40</td><td>0.05~0.14</td><td>≤0.05</td></tr><tr><td rowspan="2">信息量模型</td><td>河西走廊</td><td>≥0.46</td><td>0.20~0.46</td><td>-0.10~0.20</td><td>≤-0.10</td></tr><tr><td>张掖市</td><td>≥0.42</td><td>0.21~0.42</td><td>0.03~0.21</td><td>≤-0.03</td></tr></table></body></html>

Fig.4Mapping of mountain torrent disaster risk assessment in Hexi Corridorand Zhangye City based on three mode

# 干旱区地理

表4模型结果验证对比表  
Tab.4Models result verification comparison   

<html><body><table><tr><td rowspan="2"></td><td rowspan="2">空间尺度</td><td colspan="2">极高风险</td><td colspan="2">高风险</td><td colspan="2">中风险</td><td colspan="2">低风险</td></tr><tr><td>数量</td><td>比值</td><td>数量</td><td>比值</td><td>数量</td><td>比值</td><td>数量</td><td>比值</td></tr><tr><td>多准则决策模型</td><td>河西走廊</td><td>104</td><td>0.27</td><td>160</td><td>0.42</td><td>78</td><td>0.20</td><td>43</td><td>0.11</td></tr><tr><td rowspan="2">最大熵模型</td><td>张掖市</td><td>8</td><td>0.04</td><td>62</td><td>0.35</td><td>65</td><td>0.36</td><td>45</td><td>0.25</td></tr><tr><td>河西走廊</td><td>258</td><td>0.67</td><td>96</td><td>0.25</td><td>20</td><td>0.05</td><td>11</td><td>0.03</td></tr><tr><td rowspan="2">信息量模型</td><td>张掖市</td><td>131</td><td>0.73</td><td>31</td><td>0.17</td><td>13</td><td>0.07</td><td>5</td><td>0.03</td></tr><tr><td>河西走廊</td><td>120</td><td>0.30</td><td>160</td><td>0.42</td><td>91</td><td>0.24</td><td>14</td><td>0.04</td></tr><tr><td></td><td>张掖市</td><td>65</td><td>0.36</td><td>60</td><td>0.33</td><td>45</td><td>0.25</td><td>10</td><td>0.06</td></tr></table></body></html>

(a)河西走廊—多准则决策模型 (a)河西走廊—最大熵模型 (a)河西走廊—信息量模型 1.6 LH HH 2.7 LH HH 3.1 LH HH   
区 中区公 1.6 区 1.8 0.9 0.2 0.5 0.5 -0.5 -0.6 -0.8 -1.2 Moran's =-0.3 相 -1.7 Moran's I-0.6798 相 -2.1 |Mvran's =-05484 LL HL LL HL LL HL -1.9 -2.8 上 -3.4 -1.9-1.2-0.5 0.2 0.9 1.6 -2.8-1.7 -0.6 0.51.6 2.7 -3.4-2.1 -0.8 0.51.8 3.1 县域风险均值 县域风险均值 县域风险均值 (b)张掖市一多准则决策模型 (b)张披市—最大熵模型 (b)张披市—信息量模型 LH HH LH HH 1[m 一 HH   
区 B0 0.1 国区 1810 0.2 区 0.3 -0.5 -0.6 -0.6 Moran's I=0.1949 iMoran'sI=0.1155 Moran'sI=-0.090 3 -1.1 Z-value=2.6051 -1.4 Z-value=0.7077 -1.3 iZ-value=0.924 9 LL HL LL HL LL HL -1.7 1 -2.2 -2.1 L -1.7 -1.1 -0.50.1 0.7 1.3 -2.2-1.4-0.6 0.21.0 1.8 -2.1 -1.3 -0.5 0.3 1.1 1.9 县域风险均值 县域风险均值 县域风险均值

![](images/8535dcc19b21bca96ffb9fb4e02b2854b4f40385363bb21825f2635bedf5d6ca.jpg)  
图5相邻县域单元风险均值Moran 散点图  
Fig.5Moran scatter diagram of county risk mean value of contiguous unit   
图6模型模拟结果与实测值对比  
Fig.6Comparison between model-simulated result and measured value

模型运行结果相邻县域单元风险值呈负向相关，是因为预测模型是基于历史山洪灾害发生点提取山洪环境变量特征，从点拓展到面的过程，受降水，地形地貌，土壤和人口经济等因素的不稳定性影响，变化起伏明显，最大熵模型和信息量模型输出的山洪灾害风险存在严重的突变性，风险分布非连续性特征明显，多准则决策模型参数输入中，受主控因子降水影响渐变性特征明显，加之赋权最高，山洪灾害风险和降水分布特征相似，因此，在张掖市域空间尺度上，从空间自相关性角度分析三种模型的优越性，存在有不确切性。

# 3.4精度对比及尺度效应分析

选择河西走廊385条山洪灾害作为观测点（张掖市180个），以其风险综合评价分值为观测值，通过对比观测值与模型预测值间的误差来分析基于两种空间尺度的模型精度。多准则决策模型和最大熵模型的预测值与观测值吻合度较高(图6a)，其中，在山洪灾害高风险区武威市、金昌市和张掖市部分区域等河西走廊东部地区，多准则决策模型预测值偏高于观测值，在低山洪灾害风险的嘉峪关市和酒泉市，多准则决策模型预测值与观测值极其吻合，表明此模型模拟稳定性较差，易受参评因素影响;最大熵模型和信息量模型结果偏低于观测值，但信息量模型误差较大;最大熵模型结果曲线与观测值曲线比较平稳，预测值浮动较小,表明此模型更稳定;从图6b中可以看出，山洪灾害点编号介于 $1 5 0 \sim 2 4 1$ 间，多准则决策模型与最大熵模型结果与观测值吻合度较高，编号介于$2 4 2 \sim 3 2 9$ 间，三种模型预测结果与预测值偏差极大，但从整体来看，多准则决策模型结果下降趋势明显，稳定性较差，最大熵模型和信息量模型结果均偏低于观测值，但最大熵模型更接近观测值。

通过两种空间尺度的模型结果对比分析发现，两种空间尺度下模型计算结果存在差异，整体上呈现以下特点：河西走廊尺度上，多准则决策模型和最大熵模型预测结果与观测值吻合度最高，信息量模型误差最大;从张掖尺度上来看，三种模型计算结果误差差异较大，与观测值产生明显偏差；三种模型的尺度效应明显，在地理区划(大中)空间尺度上应用较良好，缩小至市域(小)空间尺度上模拟结果误差均增大。

# 4讨论

多准则决策模型本质是一般加权叠加模型[28]应用于山洪灾害风险评价时，空间尺度往往较大，评价单元常常超出一次山洪灾害事件实际发生的地域范围，不能充分反映各异质性影响因子变化规律与山洪灾害形成之间的复杂关系，评价结果仅仅是低空间分辨率的风险等级区划；此外，从模型应用来看，基于地图代数叠加的山洪灾害风险评价体系，容易忽视影响因子图层间的正负交互作用，如在山洪灾害风险评价系统中，降水是主控因子，地形和植被等是次控因子，短时间持续性强降水频率高的地区多为山区迎风坡，此区域植被发育良好，因此，在因子加权叠加时,植被赋权水平直接影响其消弱降水和地形等因子的程度，这在一定程度上增大了模型运行结果的误差;最大熵模型和信息量模型同属风险预测模型,模型基于统计数据提取各影响因素作用于已发区山洪灾害风险的贡献率，进而预测未知区域山洪灾害风险[29],结果更加客观。多准则决策模型稳定性较差，易受参评因素影响，一般地，在因子数据缺乏时，结果非连续性分类特征明显;信息量模型误差较大，结果分异性小,与实际情况吻合度较低，最大熵模型结果曲线与观测值曲线比较平稳，预测值浮动较小，表明此模型更稳定。另外，空间尺度上，本文以河西走廊为地理区划（大中)空间尺度研究区，以张掖市为市域(小)空间尺度研究区，地区典型，空间尺度具有代表性，研究结果可为类似大中、小空间尺度的山洪灾害风险评价模型选取提供科学参考。

# 5结论

本文从模型验证、空间自相关分析、精度对比及尺度效应分析三个层面对比多准则决策模型、最大熵模型和息量模型在河西走廊、张掖市两种空间尺度上的运行结果并分析其适应性，得出以下结论：

(1）河西走廊(地理区划)空间尺度上，最大熵模型运行结果优于信息量模型和多准则决策模型，是大空间尺度山洪灾害风险评价优选模型。（2）张掖市(市域)空间尺度上，多准则决策模型结果未通过评价标准，不适用于小空间尺度评价，最大熵模型和信息量模型适用，但结果均没河西走廊空间尺度上表现良好。（3）两种空间尺度上，三种模型的尺度效应明显，在地理区划空间尺度上应用较良好，缩小至市域空间尺度上模拟结果误差增大。（4）不同空间尺度上，最大熵模型均优于多准则决策模型和

信息量模型,适用于地理区划(大中）、市域(小)空   
间尺度的山洪灾害风险评价。   
参考文献（References）   
[1］崔鹏.中国山地灾害研究进展与未来应关注的科学问题[J]. 地理科学进展,2014,33(2）:145-152.[CUIPeng.Progress and prospects in research on mountain hazards in China[J].Progress in Geography,2014,33（2）:145-152.]   
[2]史培军,孔锋,叶谦,等.灾害风险科学发展与科技减灾[J].地 球科学进展,2014,29（11）：1205-1211.[SHI Peijun,KONG Feng,YE Qian,et al. Disaster risk science development and disaster risk reduction using science and technology[J].Advances in Earth Science,2014,29（11）:1205 -1211.]   
[3]OZSAHIN E,KAYMAZ C K. Avalanche susceptibility and risk analysis of eastern anatolian using GIS[J].Procedia-Social and Behavioral Sciences,2014,120:663 -672.   
[4]TOTSCHING R,FUCHS S. Mountain torrents: Quantifying vulnerability and assessing uncertainties[J].Engineering Geology,2015, 155 ;31 - 44.   
[5]DONATI L,TURRINI M C.An objective method to rank the importance of the factors predisposing to landslides with the GIS methodology:Application to an area of the Apennines（Valnerina; Perugia,Italy）[J].Engineering Geology,2002,63:277-289.   
[6］李祎琛,何亚伯,汪洋.基于粗糙集 RBF 神经网络村镇山洪灾 害损失预测研究——以神农架林区为例[J].灾害学,2017,32 (2）:227-234.[LI Yichen,HE Yabo,WANG Yang.Mountain torrent disaster lossprediction research based on RS and RBF neural network :A case study on Shennongjia[J]. Journal of Catastrophology,2017,32(2) :227-234.]   
[7]UNDRO.Natural disasters and vulnerability analysis[R]. Geneva : Office of the United Nations Disaster Relief Coordinator,1982.   
[8］唐川,朱静.基于GIS 的山洪灾害风险区划[J].地理学报, 2005,60(1）:87-94.[TANG Chuan,ZHU Jing.A GIS based regional torrent risk zonation[J]. Journal of Geographical Sciences, 2005,60(1) :87 -94.]   
[9]杜俊,任洪玉,张平仓,等.大空间尺度山洪灾害危险评估的比 较研究［J].灾害学,2016,31（3）:66-72.[DUJun,REN Hongyu,ZHANG Pingcang,et al. Comparative study of the hazard assessment of mountain torrent disasters in macro scale[J]. Journal of Catastrophology,2016,31(3）:66-72.]   
[10]DU X Y,LIN X F.Conceptual models on regional natural disaster risk assessment[J].Procedia Engineering,2012,45:96-100.   
[11］田丰,张军,冉有华.河西走廊泥石流灾害危险性评价及影响 因子分析[J].自然灾害学报,2017,26（3）：139-146.[TIAN Feng,ZHANG Jun,RAN Youhua.Hazard assessment and influence factorsanalysisofdebrisflowdisasterinHexi CorridorJ].Jounal of Natural Disasters,2017,26(3):139 -146.]   
[12］唐川,马国超.基于地貌单元的小区域地质灾害易发性分区方 法研究[J].地理科学,2015,35（1）:91-98.[TANG Chuan, MA Guochao.Small regional geohazards susceptibility mapping based on geomorphic unit[J]. Scientia Geographica Sinica,2015, 35(1) :91 -98.]   
[13］陈亚宁,王怀军,王志成,等.西北干旱区极端气候水文事件特 征分析[J].干旱区地理,2017,40(1):1-9.[CHEN Yaning, WANGHuaijun,WANG Zhicheng,etal.Characteristics of extreme climatic/hydrological events in the arid region of northwestern China[J].Arid Land Geography,2017,40(1):1 -9.]   
[14］顾春杰,孙爽,马金珠.基于DEA 模型和生产函数的泥石流易 损性评价[J].兰州大学学报（自然科学版），2014,50（5）： 751-756.［GU Chunjie,SUN Shuang,MA Jinzhu.Debris flow vulnerability assessment based on DEA model and production function[J].Journal of Lanzhou University（Natural Sciences）,2014, 50(5):751-756.]   
［15］李发文,张行南,杜成旺.基于GIS 和数学形态学的洪水淹没研 究[J].水利水电科技进展,2005,25(6):14-24.[LI Fawen, ZHANG Xingnan,DU Chengwang.Study on flood submergence based on GIS and mathematical morphology[J].Advances in Science and Technology of Water Resources,2005,25(6）:14-24.]   
[16］张磊,王文,文明章,等.基于“FloodArea"模型的山洪灾害精细 化预警方法研究[J].复旦学报（自然科学版),2015,54（3）： 282-287.[ZHANG Lei, WANG Wen,WEN Mingzhang,et al. Research on refined early-warming method of mountain flood disaster based on FloodArea[J].Journal of Fudan University（Natural Science）,2015,54(3） :282-287.]   
[17］丁志雄,李纪人,李琳.基于GIS 格网模型的洪水淹没分析方 法[J].水利学报,2004,35（6）：56-67.［DING Zhixiong,LI Jiren,LI Lin.Method for flood submergence analysis based on GIS grid model[J]. Jourmal of Hydraulic Engineering,2004,35（6）： 56 -67.]   
[18］刘雪萍.IDRISI遥感图像处理与地理信息系统教程［M].北 京：电子工业出版社,2014:127-135.[LIU Xueping.Tutorial of IDRISI remote sensing image processing and geographical information system[M].Beijing:Publishing House of Electronics Industry,2014:127-135.   
[19]PHILLIPS S J,ANDERSONB R P,SCHAPIRE R E. Maximum entropy modeling of species geographic distributions[J].Ecological Modelling,2006,190(3-4）:231-259.   
[20] ZHANG Jun,TIAN Feng,ZHOU Dongmei,et al.Land eco-security evaluation in the Shule River Basin during 2Oo5—2O14 in Gansu Province,China[J]. Human and Ecological Risk assessment：An International Journal,2017,23（7）:1731-1744.   
[21］宁娜,马金珠,张鹏,等.基于GIS 和信息量法的甘肃南部白龙 江流域泥石流灾害危险性评价［J].资源科学,2013,35（4）： 892-899.[NING Na,MA Jinzhu,ZHANG Peng,et al.Debris flow hazard assessment for the Bailongjiang River,Southern Gansu [J]. Resources Science,2013,35(4）:892 -899.]   
[22]毕硕本,蒋婷婷,钱育君.1470—1912 年西北东部地区极端干 早事件的复原及分形特征研究[J].干旱区地理,2017,40（2）： 248 -256.[BI Shuoben,JIANG Tingting,QIAN Yujun.Recovery of extreme drought events and their fractal characteristics in the eastern Northwest China from1470 to 1912[J].Arid Land Geography,2017,40(2) :248 -256.]   
[23]SHANGGUAN W,DAI Y,LIUB,etal.A soil particle-size distribution dataset for regional land and climate modelling in China [J].Geoderma,2012,172:85 -91.   
[24］何杰,阳坤.中国区域高时空分辨率地面气象要素驱动数据集

[DB/OC].寒区旱区科学数据中心,2011.doi:10.3972/west-dc.002.2014.db.［HE Jie,YANG Kun.China meteorologicalforcing dataset[DB/OC].Cold and Arid Regions Science DataCenter at Lanzhou,2011.doi:10.3972/westdc.002.2014.db.][25］孟现勇.SWAT模型中国大气同化驱动数据集（CMADSV1.1)[DB/OC].寒区旱区科学数据中心,2016.doi:10.3972/west-dc.002.2O16.db.［MENG Xianyong.China meteorological assimi-lation driving datasets for the SWAT model version1.1[DB/OC].Cold and Arid Regions Science Data Center at Lanzhou,2O16.doi:10.3972/westdc.002.2016.db.]

[26]田丰，冉有华,张军，等.河西走廊山洪灾害危险度区划[J].山 地学报,2017,35（6）:856-864.[TIAN Feng,RAN Youhua, ZHANG Jun,et al.Mountain torrent hazard division along Hexi Corridor[J].MountainResearch,2017,35(6):856-864.]

[27］田丰，张军，再有华，等.基于多源数据整合的河西走廊经济带 山洪灾害风险空间分布特征研究[J].干旱区资源与环境， 2018,32(7):196-203.[TIAN Feng,ZHANG Jun,RAN Youhua,et al. Study on mountain torrent disaster risk spatial distribution characteristic in the Hexi Corridor based on multi-source data integration[J]. Journal of Arid Land Resources and Environment, 2018,32(7) :196-203.]

[28]ARGYRIOUAV,TEEUWRM,RUSTD,SARRISA.GISmulticriteria decision analysis for assessment and mapping of neotectonic landscape deformation:A case study from Crete[J].Geomorphology,2016,253:262 -274.

[29］田丰,张军,冉有华,等.甘肃陇南市泥石流灾害危险性及影响因子评价[J].灾害学,2017,32（3）：197-203.［TIAN Feng,ZHANG Jun,RAN Youhua,et al.Assessment of debris flow disas-terhazard and influence factors in Longnan District[J].Journal ofCatastrophology,2017,32（3）:197-203.]

# Model comparison of mountain torrent disaster risk assessment in different spatial scale

TIAN Feng’， ZHANG Jun²，RAN You-hua³，LIU Jin-peng4， ZHOU Yi²   
(1FacultyfogacalSienceeijigalUiersityejing5in；lgeofesoucedEl   
Sciences,GansugiculturalUesityoOsuna；rthestIsitutefcoomentdce， ChineseAcademyofSciences,ChineseAcademyofSciences,Lanzhou73Oo,Gansu,China；4.Geological Natural Disaster Prevention Research Institute,Gansu Academy of Sciences,Lanzhou 73oooo,Gansu,China)

Abstract：This paper selected Hexi Corridor and Zhangye District,Gansu Province,China as the study zones with different spatial scale of geography division (large and medium scale,e.g.Hexi Corridor）and region (small scale, e.g. Zhangye District）.Three popular models in assessing mountain torrent disaster including multi-criterion model, MaxEntmodel and information model were set as the study object.Basedon the established risk assessment index system about mountain torrent disaster,the mapof risk assessment on mountain torrent disasterfor Hexi Corridor and Zhangye District was accomplished using the three models respectively.The model's suitabilitywas analyzed from the perspectives of the modelvalidation,spatial autocorelation,the precision comparison and the scale effect based on the statistics data about the geological disasters investigationand divisional reports in Gansu Province,and he preferred model was figured out.The result showed that MaxEnt model was the optimal model for risk assessment about mountain torrent disaster atthe spatial scale of geography division.The multi-criterion model wasn’t suitable at the spatial scale of region,and the results from three models for Zhangye District were not as goodas those for Hexi Corridor.The scale effectof the three models was extremely obvious,andthe application efect atthe spatial scaleof Hexi Corridor was beterthan that at the spatial scale of Zhangye District.The MaxEnt model wassuperior to the multi-criterion decision modelandthe information modelregardless of thespatialscale,and can beused to support the monitoring,pre-warning and protection enginering projects about mountain torrent disaster in Hexi Corridor.

Key words:mountain torrent disaster；risk assessment；spatial scale；model adaptation；model comparison