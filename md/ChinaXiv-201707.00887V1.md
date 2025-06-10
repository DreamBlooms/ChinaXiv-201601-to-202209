# DOI:10.5846/stxb201604250780

詹云军,朱捷缘，严岩.基于元胞自动机的城市空间动态模拟.生态学报,2017,37（14)：4864-4872.  
hanYJ,ZuJcsadaectaolcac）.

# 基于元胞自动机的城市空间动态模拟

詹云军¹，朱捷缘1²，严 岩2，

1武汉理工大学，资源与环境工程学院，武汉430070  
2中国科学院生态环境研究中心，城市与区域生态国家重点实验室，北京100085

摘要：城市空间动态的模拟与预测可以为城市可持续发展规划与管理提供重要的参考依据。SLEUTH元胞自动机模型在城市空间模拟中较强的适用性和可移植性,该模型通过对历史数据的蒙特卡洛迭代自动寻找城市增长误差最小的参数组合,解决了传统元胞自动机模型中转换规则不易确定的问题。以武汉市为研究案例,运用 SLEUTH模型进行了城市空间动态模拟与情景预测。2007年至2011年的城市空间模拟结果显示,模拟结果与实际历史数据可以获得良好的空间匹配度,Lee-Salee 形状指数均在0.6以上,显示 SLEUTH元胞自动机模型经过本地化校正后具有较强的适用性和满意的模拟精度。进而,设置了现状趋势、基本保护、严格保护等3种情景对武汉2025 年城市空间动态进行了预测,结果显示,各情景模式下城市居住用地均明显增长,农业用地、林地、水域等均有所减少;现状趋势情景和基本保护情景下农田、林地、水域减少的幅度较大,会加剧区域的生境破碎、耕地功能下降、水资源匮乏、湖滨湿地萎缩等生态问题,说明这两种情景不能有效满足城市生态系统健康和可持续发展的需要。严格保护情景下,城市居住用地扩张的程度得到了明显的控制,水域和林地得到了有效的保护,对于重要的自然生态系统组分保护及其服务能力维持可以起到显著作用。

关键词：城市扩展；土地利用；模拟；元胞自动机(SLEUTH模型)；武汉

# Dynamic simulation of urban space based on the cellular automata model

ZHAN Yunjun1，ZHU Jieyuan1,²，YAN Yan

1 Wuhan Universityof Technology，School of Resource andenvironmental engineering，Wuhan 430o7O,China   
2StateKeyLboratoryofUbanndRegionalcolgReseachCenterforcoEniroentalSciences，ChineseAcademyofSciences，ein 100085，China

Abstract:The dynamic simulationand prediction of urban spacecan provide an important reference forthe planning and management of sustainableurban development.Thecelular automata model SLEUTH has strong universalityand portability inurban spatial simulation.Itisbasedonthe Monte Carlo iterationof urban historical dataand iscapableofautomatically identifyingurban growth parameters with minimumeror，which hasfectivelyresolved thedificultiesencountered in determining theconversion rules when using the traditionalcelular automata models.Inthis study,weapplied the SLEUTH model to perform urban spatial simulation and prediction underdiferent scenarios in Wuhan City.Ourfindings revealed that theurbanspatial simulationresults for the period 2OO7 to2O11 showed a strongcorelation with actual historicaldata.The Lee-Salle shape index wasgreater thanO.6，which proves that the SLEUTH model exhibitsa strong universality and suitable simulationaccuracyafter local corection.Moreover,theurban dynamicchanges in Wuhan in2O25 were predicted underthree scenarios，namely，the current development trend scenario，the basicprotection scenario，and the strict protection scenario.Theresultsof simulationunder these three scenarios indicate thaturban residentiallandwillincrease significantly，whereasagriculturalland，woodand，water，andotherland woulddecrease，particularlyunderthecurrent development trendand basic protectionscenarios.Under thesetwoscenarios，considerable decreasesareobserved in agriculturalland，woodland，andwater,whichmayintensifyhabitatfragmentation,ndresultinadeclineinthequalityof cultivated land，waterresource shortage，wetland shrinkage，andother ecological problems.Under thestrictprotection scenario,therapid proliferationofconstruction land wouldberestricted toalargeextentand waterbodiesand woodland would be transformed the least，which would effectivelyprotect natural ecosystemcomponentsand maintain sustainable ecosystem services

Key Words:urban expansion；land use；simulation；celular automata model（SLEUTH model）；Wuhan

城市是一个具有开放性、动态性、自组织性的时空动态复杂系统,城市空间扩展是在特定的地理环境和一定的社会经济发展阶段中,不同时空尺度下的自然、人文、社会、经济、文化等多种因素的综合反映。随着城市空间的不断扩张,对自然资源的侵占力度也不断加强,由此带来一些区域生态环境问题,如热岛效应、植被退化、生态系统服务功能下降、生物多样性降低等[1-4]。因此,对城市时空演化特征进行定量化描述和预测可为区域的可持续发展和土地利用管理决策提供科学依据,城市空间动态模拟是城市生态环境研究中的重要方向[5]。

近年来,许多学者从不同角度建立了数学模型和空间模型开展城市空间扩展和动态模拟研究,如Clarke等利用城市发展的历史数据,根据城市的交通、地形条件等设定适当的参数,建立SLEUTH模型对旧金山和华盛顿都市区进行了成功模拟和长期预测[6-7];黎夏和詹云军等将神经网络与元胞自动机（cellular automatamodel，CA)模型相结合,挖掘城市扩展土地利用演变的规律[89],但该方法属于黑箱结构,对模型参数的物理意义难以解释;刘小平和单玉红等利用智能体模型对城市空间扩张和土地利用格局演变进行模拟[10-11],智能体模型能模拟个体或群体的行为及决策模式对土地利用产生的影响,但个体决策行为具有极大的复杂性,增加了模型的不确定性,为模型的验证和移植带来了困难[12]。其中,SLEUTH模型是一种基于元胞自动机（CA)的城市扩展与土地利用变化模型,其设计思路是基于交通、地形和城市化的约束条件计算每个元胞单元发展的可能性,把城市化的元胞作为种子点,通过其扩散带动整个区域的发展,其中离种子点越近的元胞越容易被城市化[6]。与其他模型相比,SLEUTH模型具有较强的普适性和可移植性,最大的特点是根据模拟结果与历史训练数据的拟合度,通过蒙特卡洛迭代自动寻找城市增长误差最小的组合方案,从而得到城市扩展过程最佳的参数组合[13],解决了传统CA模型中转换规则不易确定的问题。近年来,SLEUTH模型被成功的应用于国内的城市空间研究,如北京、广州、长沙等城市[14-16]。

武汉是我国华中地区最大城市,也是长江经济带国家战略中长江中游最重要的城市。近年来,武汉市在“武汉 $^ { 8 + 1 }$ 城市圈”的发展规划以及旧城改造的政策背景下,城市空间向周围的快速扩展,土地利用结构演变剧烈,城市化进程日益加快,由此也在一定程度上造成了武汉市水域湿地面积缩减、水质污染、耕地减少等生态问题,城市发展、空间扩张与生态环境保护之间的矛盾成为区域可持续发展面临的重要难题。本文以武汉市武昌地区为例,在已有的城市扩展机制和 SLEUTH模型应用研究的基础上,对武汉市城市空间进行动态模拟,预测不同情景下城市空间扩张格局,进而探讨城市土地扩张的生态环境影响及可能采取的对策及效果,以期为武汉城市空间发展和可持续规划与管理提供参考。

# 1研究区域和研究方法

# 1.1 研究区域

武汉市位于长江和汉水交汇处，地处 $2 9 ^ { \circ } 5 8 ^ { \prime } \mathrm { N }$ 到 $3 1 ^ { \circ } 2 2 ^ { \prime } \mathrm { N } , 1 1 3 ^ { \circ } 4 1 ^ { \prime } \mathrm { E }$ 到 $1 1 5 ^ { \circ } 0 5 ^ { \prime } \mathrm { E }$ 之间，是华中地区的特大城市。本文以武汉市的武昌区、洪山区、青山区和江夏区的北部为研究区,该区域大部分为平原地区,湖泊水系众多,空间格局上具有从城市核心区到郊区的过渡,产业上由青山区的老工业区和洪山、江夏区的经济开发

区并存，研究区示意图如图1所示。

![](images/4f455fefb64ddf74104bd18d9d9940b7968571cc05dabeb16ab5567d2faefa7d.jpg)  
图1研究区位置示意图  
Fig.1A map of the location of the study area

# 1.2 方法与数据

1.2.1 SLEUTH模型

SLEUTH元胞自动机模型可以模拟和预测城市增长和土地利用演化,模型名称来自6个输入图层的首字母缩写,分别是坡度图层（Slope）、土地利用图层（Landuse）、排除图层（Exclusion）、城市化图层（UrbanExtent）道路图层（Transportation）和山体阴影图层（Hillshade）[6,17]。模型转换规则受扩散系数、繁衍系数、蔓延系数、坡度阻碍系数和道路引力系数5个参数控制,它们决定了城市增长的4种类型,即自发增长、新扩展中心增长、边缘增长和道路影响增长。本文的城市空间动态模拟具体涉及到居住用地的增长和其他用地类型之间的转换,因此初始种子元胞是已经城市化的居住用地元胞,自发增长指在满足坡度条件的可城市化的区域发展新的居住用地元胞的可能性;新的扩展中心增长表示自发增长产生的新的居住用地元胞成为新的扩展中心的可能性;边界增长是原有的扩展中心和新产生的扩展中心周围继续演变为居住用地的可能性;道路影响型增长表示城市交通网络对城市扩张的引力作用。

运用 SLEUTH模型进行居住用地增长模拟前需进行校正处理,即根据历史数据来进行样本训练,这是一个蒙塔卡罗迭代处理过程[6]。校正过程可分3个阶段,即粗校正、精校正和终校正,根据模型5个参数的初始范围,通过反复计算不同的参数组合所产生的模拟结果与实际情况的拟合度,逐步缩小参数范围,最终确定最优的参数组合[7],代表了居住用地增长的历史轨迹方向,并以此参数组合对城市未来空间扩展进行模拟和预测。

# 1.2.2 数据来源与预处理

本研究所用基础数据来源包括:2005 年、2007 年、2009 年、2011年4期季相一致、高度 $3 0 \mathrm { m }$ 的武汉市GoogleEarth截图,从国际科学数据服务平台下载分辨率为 $3 0 \mathrm { m }$ 的 DEM数据。针对 SLEUTH模型的运行要求,对上述数据做了相应的校正、裁切处理,然后结合遥感解译和目视解译,在ARCGIS 中制作了 SLEUTH模型模型所需的居住用地范围图层、土地利用图层、交通图层和排除图层,利用DEM数据制备了研究区的坡度图层及山体影图层,输入数据图层如图2所示,由于土地利用图层在模拟结果验证中会展示,在此部分不再列举。最后所有输入图层均按照统一的横轴墨卡托(UTM_WGS1984_49N)投影设定,全部转换成无符8位灰度的GIF格式的栅格图像。 1

![](images/eb233972cf7817d12ee48c6725c42adf9e0f1e029f3a14c97ee24af71b3fe822.jpg)  
图2SLEUTH模型输入数据图层  
Fig.2 Input data layersofSLEUTH model

本文的城市空间动态演变主要关注居住用地与其他土地利用之间的转变,因此对土地利用类型进行重新分类(表1),居住用地图层指各类住宅用地,具体包括居住小区和城中村居住用地;商业服务业用地、公共基础设施用地和水域作为排除图层参与模型运行，限制其向居住用地演化;此外，考虑到除了交通网络良好的可达性对居住用地建设的导向作用外,还将生态环境好的湖泊、教育用地和设施发达的商业服务业对居住用的吸引作用集成到模型中,运用ARCGIS软件将这类吸引居住用地开发的区域从面转换成线,成为“引力道路"纳入交通图层,不同等级的道路设置不同的相对权重值来表示不同的可达性和吸引力，一起参与模型的校准、模拟和预测过程。

http ://www.ecologica.cn

表1土地利用类型分类  
Table 1 Classifications of land use types   

<html><body><table><tr><td>土地利用类型编码 The code of landuse type</td><td>重分类的土地利用类型 Landuse type Reclassify</td><td>原土地利用类型 Original landuse type</td></tr><tr><td>1</td><td>交通用地</td><td>高速路、主干道、次干道</td></tr><tr><td>2</td><td>居住用地</td><td>各类住宅用地,包括商品房和城中村用地</td></tr><tr><td>3</td><td>公共基础设施用地</td><td>商业服务业设施用地、公共管理与公共服务用地(行政办公用地、教育科研 用地等）、交通枢纽、公园、广场</td></tr><tr><td>4</td><td>工业用地</td><td>能源、制造、化工等各类工矿用地、软件园等</td></tr><tr><td>5</td><td>农业用地</td><td>农田</td></tr><tr><td>6</td><td>水域</td><td>河流、湖泊、湿地</td></tr><tr><td>7</td><td>林地</td><td>天然林地、灌丛</td></tr><tr><td>8</td><td>荒地</td><td>未利用地、荒草地</td></tr></table></body></html>

# 1.2.3 情景设计

本文基于研究区城市空间变化的历史趋势和城市生态保护需求,设置了现状趋势、基本保护、严格保护等3种发展情景。利用 SLEUTH模型的参数获取结果,通过修改排除图层和 SLEUTH模型的输入参数,以2011年居住用地范围为“种子点”,预测其2012—2025 年的土地利用变化,实现3种情景下城市土地利用变化的模拟预测。（1)现状趋势情景：将公共基础设施用地作为排除图层,排除概率设为 $100 \%$ ,对其他用地不设发展限制,同时限制发展坡度设为 $2 5 ^ { \circ }$ ,即地形超过 $2 5 ^ { \circ }$ 的区域不能演化居住用地元胞;(2)基本保护情景：从保护湖泊湿地和基本农田的角度,适当控制城市发展的速度,在现在趋势发展情景设计基础上,将研究区域内的水域设置 $6 0 \%$ 的保护概率,农业用地设置 $5 0 \%$ 的保护概率，同时限制发展坡度设置为 $2 5 ^ { \circ }$ ;（3)严格保护情景：该情景加强了对农田、水域、林地等生态用地的保护力度,将水域的保护概率设为 $100 \%$ ,农田和林地保护概率设为 $9 0 \%$ ,同时将限制发展坡度设置为 $1 5 ^ { \circ }$ 。1

# 2结果与讨论

# 2.1土地利用变化的历史动态分析

根据各用地类型对应的面积计算出 2007年至2011年的土地利用转移概率（表2）,分析土地利用转移概率矩阵可以得到,农业用地和荒地的耗减度比较大,耗减的农业用地向居住用地和荒地的转化占很大比例，$2 2 . 4 8 \%$ 的荒地被开发成新的住宅用地。居住用地总体上的净增加量为 $1 0 . 3 4 ~ \mathrm { k m } ^ { 2 }$ ,同时从表2中可以得到2007年到2011年期间已有的居住用地的耗减度为 $1 3 . 1 8 \%$ ,原因是城区的一些破旧的城中村和老工业区的旧住宅被拆除,转变成暂时的荒地(空地),表明历史年份中居住用地元胞在增长的同时也有一小部分在衰败和死亡。研究区域内水域的整体面积变化不大,可能是越来越注重生态宜居环境的住宅开发模式合理的保护了水域的边界,也可能与政府采取的"还湖、还渔”等政策密切相关。

新增的居住用地呈散点填充在中心城区的待建用地中以及城郊区的工业园周围的闲置用地上,部分新增居住用地元胞围绕湖泊沿岸分布,这也是武汉特殊的自然环境优势之处,住宅开发模式向靠近江河湖泊的生态宜居环境方向发展。2005年至2011年研究区土地利用变化的主要特征是城市空间的扩张及其对农业用地的占用,这可以说是改革开放后武汉市土地利用变化的主要历史形态。

# $2 . 2 ^ { ^ { \prime } }$ 模型校正与模拟精度检验

本文用处理之后的4期研究区城市居住用地数据作为训练样本对模型进行校正,以获取城市增长最佳参数。模型会将训练结果与真实数据进行对比,并且用Lee-Salle 指数来评价校正结果精度,Lee-Salle形状指数是各控制年份的模拟增长结果与实际城市居住用地范围的空间匹配度，用公式表示为：

$$
S = ( A \cap B ) / ( A \cup B )
$$

S 为Lee-Sallee 形状指数,A为模拟的城市居住用地面积, $B$ 为实际的城市居住用地面积。

Table 2The transition probabilities between different landuse types from 2oo7 to 2011   

<html><body><table><tr><td>土地利用类型 Landuse types</td><td>交通用地 Transportation land</td><td>居住用地 Residential land</td><td>公共地 Public</td><td>工业用地 Industrial land</td><td>农业用地 Agricultural land</td><td>水域 Water area</td><td>林地 Woodland</td><td>荒地 Unused land</td></tr><tr><td>交通用地 Transportation land</td><td>99.38</td><td>0.13</td><td>facilities land 0.05</td><td>0.04</td><td>0.07</td><td>0.08</td><td>0.08</td><td>0.17</td></tr><tr><td>居住用地 Residential land</td><td>1.73</td><td>86.82</td><td>0.97</td><td>0.58</td><td>0.62</td><td>0.02</td><td>1.10</td><td>8.16</td></tr><tr><td>公共基础设施用地</td><td>0.36</td><td>0.70</td><td>97.31</td><td>0.20</td><td>0.03</td><td>0.07</td><td>0.56</td><td>0.75</td></tr><tr><td>Public facilities land 工业用地 Industrial land</td><td>0.30</td><td>0.84</td><td>0.60</td><td>94.79</td><td>0.00</td><td>0.05</td><td>0.55</td><td>2.88</td></tr><tr><td>农业用地 Agricultural land</td><td>2.28</td><td>4.04</td><td>0.80</td><td>1.60</td><td>75.56</td><td>0.47</td><td>2.49</td><td>12.75</td></tr><tr><td>水域 Water area</td><td>0.20</td><td>0.18</td><td>0.09</td><td>0.04</td><td>0.12</td><td>98.50</td><td>0.13</td><td>0.73</td></tr><tr><td>林地Woodland</td><td>1.39</td><td>4.33</td><td>1.48</td><td>0.72</td><td>1.16</td><td>0.11</td><td>83.34</td><td>7.47</td></tr><tr><td>荒地 Unused land</td><td>3.64</td><td>22.48</td><td>8.24</td><td>8.98</td><td>1.82</td><td>4.19</td><td>5.58</td><td>45.06</td></tr></table></body></html>

# 执行校正模块，本文中校正的3个阶段的参数设置和检验结果如表3所示

表22007年至2011年土地利用类型转移百分比  
表3 SLEUTH模型校正结果  

<html><body><table><tr><td rowspan="3">增长系数 Growth coefficient</td><td colspan="2">粗校正 Coarse calibration MONTE_CARLO=4</td><td colspan="2">精校正Fine calibration</td><td rowspan="3">终校正Final calibration MONTE_CARLO=9</td><td rowspan="3">最终系数 Final</td></tr><tr><td colspan="2">n=3125</td><td colspan="2">MONTE_CARLO= 7 n = 7776</td></tr><tr><td>Lee-Sallee= 0.8299 范围Range</td><td>步长Step</td><td>Lee-Salle = 0.8242 步长 Step</td><td>Lee-Sallee = 0.8243</td></tr><tr><td>扩散系数 Dispersion_coefficient</td><td>1—100</td><td>25</td><td>范围Range 0-10</td><td></td><td>范围Range 步长 Step</td><td></td></tr><tr><td>繁衍系数 Breed_coefficient</td><td>1—100</td><td>25</td><td>0-10</td><td>0-5 0-5</td><td>1 1</td><td>3 4</td></tr><tr><td>蔓延系数 Spread_coefficient</td><td>1—100</td><td>25</td><td>0-10</td><td>0-5</td><td>1</td><td>1</td></tr><tr><td>坡度阻碍系数 Slop_coefficient</td><td>1—100</td><td>25</td><td>75—100</td><td>95—100</td><td>1</td><td>95</td></tr><tr><td>道路引力系数 Road_coefficient</td><td>1—100</td><td>25</td><td>25-75</td><td></td><td>10</td><td>45</td></tr></table></body></html>

3个校正阶段的Lee-Sallee 值均达到0.82以上,说明模型校正结果非常理想。最后获得研究区的增长系数组合为:3(扩散系数）、4（繁衍系数）1（蔓延系数）、95（坡度阻力系数)和45（道路引力系数)。运行SLEUTH模型的测试(Test)模块,以2005 年为初始年,以校正阶段提取的最佳系数组合作为模型模拟的初始参数,对研究区2006年至2011年的土地利用变化情况进行模拟,得到逐年的土地利用模拟结果（图3）。对土地利用模拟结果从空间匹配性和面积精确度两个方面进行评估,选择 Lee-Salle形状指数为主要指标评估模拟结果与历史数据在空间位置上的匹配性,各控制年份 2007、2009 和2011年的 Lee-Salle 指数依次为0.87,0.94、0.67,均在0.6以上,空间匹配度比较高;利用面积比指数对模拟的土地利用面积进行精度验证（表4),计算结果表明各用地类型的演化在数量上的模拟精度也比较高,精度均达到 $7 9 \%$ 以上,交通用地、公共基础设施用地、工业用地、农业用地、水域和林地的模拟精度均达到 $9 2 \%$ 以上,其中水域的模拟精度最高。相比较而言,荒地的模拟精度稍低,可能受“旧城改造”和产业上“退二进三"的政策影响,一些污染较大的老工业区和城中村的拆除导致临时空地(待建用地)增多,而 SLEUTH模型模拟过程并没有捕捉突变式的社会经济政策影响。

Table 3 Calibrationresultsof SLEUTHmodel   
表4土地利用变化模拟结果与实际数据精度对比  
Table4 Simulation accuracy of landuse simulation results and the actual data in2oo7 and 2011   

<html><body><table><tr><td></td><td colspan="3">2007年</td><td colspan="3">2011年</td></tr><tr><td>土地利用类型 Landuse types</td><td>实际面积 Actual</td><td>模拟面积 Simulated</td><td>精度 Accuracy/%</td><td>实际面积 Actual</td><td>模拟面积 Simulated</td><td>精度 Accuracy/%</td></tr></table></body></html>

http://www.ecologica.cn

![](images/676ec12a6a6a944356e52f95163aae7c31ad0ab87c6d139df1e6bd8f9a80a534.jpg)  
图32007年土地利用模拟图与真实图；2011年土地利用模拟图与真实图  
Fig.3 Land use simulation result and actual map in 2oo7;Land use simulation result and actual map in 200'

续表

<html><body><table><tr><td rowspan="2">土地利用类型</td><td colspan="3">2007年</td><td colspan="3">2011年</td></tr><tr><td>实际面积</td><td>楼面</td><td>精度 Accuracy/%</td><td>实际面积</td><td>模拟面积</td><td>精度 Accuracy/%</td></tr><tr><td>交通用地 Transportation land</td><td>area/hm² 5268</td><td>area /hm² 5086</td><td>96.55</td><td>area/hm² 6092</td><td>area/hm² 5757</td><td>94.50</td></tr><tr><td>居住用地 Residential land</td><td>11207</td><td>12511</td><td>88.36</td><td>12241</td><td>13482</td><td>89.86</td></tr><tr><td>公共基础设施用地 Public facilities land</td><td>5322</td><td>5016</td><td>94.25</td><td>6026</td><td>5554</td><td>92.17</td></tr><tr><td>工业用地 Industrial land</td><td>3811</td><td>4096</td><td>92.52</td><td>4590</td><td>4455</td><td>97.06</td></tr><tr><td>农业用地 Agricultural land</td><td>26458</td><td>26145</td><td>98.81</td><td>20271</td><td>21801</td><td>92.45</td></tr><tr><td>水域Water area</td><td>19205</td><td>19109</td><td>99.50</td><td>19285</td><td>19111</td><td>99.10</td></tr><tr><td>林地Woodland</td><td>5781</td><td>5455</td><td>94.36</td><td>5972</td><td>5815</td><td>97.37</td></tr><tr><td>荒地 Unused land</td><td>4577</td><td>4211</td><td>92.00</td><td>7152</td><td>5654</td><td>79.05</td></tr><tr><td>合计 Total</td><td>81629</td><td>81629</td><td></td><td>81629</td><td>81629</td><td>二</td></tr></table></body></html>

# 2.3不同情景下的城市空间预测结果

运用模型模拟,得到研究区3种情景下 2012—2025年土地利用变化结果。2025 年研究区土地利用格局见图4,各土地利用类型面积变化见图5。从面积变化看,各情景下居住用地均明显增加,城市居住用地对其他用地类型均有不同程度的侵占,对农业用地和荒地的占用最多。从扩展模式看,总体表现为从旧城中心区向外不断蔓延,区域内没有产生新的大规模居住隔离组团,新增的居住用地元胞主要是在原有的原有城市化基础上向外围郊区蔓延扩展,空间格局较破碎化;同时也有内部填充式增长,表现为中心城区内部的空地出现呈散点状分布的居住用地元胞。此外,在城市交通的推动下,居住用地沿交通便利区域蔓延速度比较迅速,青山区和洪山区外围的高速路、洪山区的白沙洲大道、光谷一路以及江夏区的武昌大道周围出现了一定量的新增居住用地元胞。江河湖泊沿岸的新增居住用地元胞也很明显,显示出“道路引力”的效果。

从图5可以看出,不同情景下土地利用变化趋势差异较大。现状趋势情景下城市扩展呈无序蔓延状态，尤其是城郊结合区土地利用变化尤为剧烈。城镇用地扩张迅速，占用了大量的农田和荒地，林地和水域也有相当程度的损失。居住用地增加最为显著，2011一2025年,将增加 $5 6 7 3 . 6 \mathrm { h m } ^ { 2 }$ ,年均增长 $3 7 8 . 2 4 \mathrm { { h m } } ^ { 2 }$ 。农田损失量约为 $2 7 4 2 . 8 4 \mathrm { h m } ^ { 2 }$ ,林地减少 $6 6 7 . 0 8 ~ \mathrm { h m } ^ { 2 }$ ,水域将减少$5 4 6 . 1 2 ~ \mathrm { h m } ^ { 2 }$ ,这会加剧区域的生境破碎、耕地功能下降、水资源匮乏、湖滨湿地萎缩等生态问题，加大城市发展与生态保护之间的矛盾。

![](images/b53b2ea15fe49090442b61756c606fb11d219575d372afcbbe9262a56ce5618b.jpg)  
图4三种情景下的2025年土地利用变化预测图现状趋势情景，基本保护情景，严格保护情景

基本保护情景下，城市扩张的速度得到了一定程度的控制。居住用地将增加 $4 5 7 5 . 6 \ \mathrm { h m } ^ { 2 }$ ,年均增长量为$3 0 5 . 0 4 \mathrm { h m } ^ { 2 }$ 。农田损失较为显著下降,损失量为1781.$6 4 \mathrm { { h m } } ^ { 2 }$ 。林地和水域等自然生态类型仍然有显著损失,林地减少了 $6 3 5 . 7 6 \ \mathrm { h m } ^ { 2 }$ ,水域减少 $2 7 0 . 3 6 \ \mathrm { h m } ^ { 2 }$ 。从空间格局来看，此种情景下的城市空间扩展空间形态也比现状趋势情景下稍显紧凑。

![](images/73a623fddddea1f5de6d786e23d273b1eb5c5fe27f184ba18448fa70d720bfe2.jpg)  
Fig.4Predictionresultsofurbangrowthandlandusein2025underdiferentscenariosinthestudyareacurrentdevelopmenttrend scenario，basic protection scenario,strict protection scenario   
图52011一2025年研究区的土地利用类型面积变化Fig.5The area change of different land use types in the studyarea from 2011to 2025

严格保护情景下,由于加大了对各类湖泊湿地和基本农田的保护力度,居住用地的大肆扩张得到适当的控制,土地利用变化速度明显降低。居住用地增幅显著减小,增加 $2 5 8 3 . 7 2 \ \mathrm { h m } ^ { 2 }$ ,年均增长量为 $1 7 2 . 2 5 \mathrm { h m } ^ { 2 }$ 。林地、水域等生态用地损失明显降低,林地减少 $2 0 3 . 4 ~ \mathrm { h m } ^ { 2 }$ ,水域减少 $1 2 9 . 9 6 \ \mathrm { h m } ^ { 2 }$ ,相比基本保护情景，损失量分别下降了 $6 8 . 0 1 \% . 5 1 . 9 3 \%$ 。这显示出生态保护措施具有显著的调控效果,对于限制建设用地的肆意扩张和保护水域、农田等各类生态用地及其生态系统服务能力可以起到积极作用。

3 种情景下,工业用地和公共基础设施用地的面积变化均不明显,主要是由于这些用地类型规模不大,历史变动也较小,从而根据历史外推趋势得到的预测面积变化也不显著。

# 3结论

在GIS 和RS 技术的支持下,利用SLEUTH元胞自动机模型对武汉市武昌、洪山和江夏部分地区的城市空间演变进行模拟和情景预测,揭示不同土地保护强度下的城市扩展趋势,主要结论如下：

(1)从模型模拟精度来看,2007年至2011年的城市空间模拟结果与历史数据的空间匹配度较高,形状指数和面积比指数均较大,模拟精度较高,表明 SLEUTH元胞自动机模型通过本地化校正后可以应用在城市空间动态模拟中，具有较强的适用性和可移植性。

(2)对武汉 2025 年城市空间扩展的模拟结果表明,各情景下居住用地均明显增加,对其他用地类型均有不同程度的侵占,显示城市居住用地增长在未来土地利用变化过程中占据主导地位。从空间扩展模式来看,新增的居住用地元胞主要是在原有的城市化基础上向外围郊区蔓延扩展,空间格局较破碎化，同时辅以内部空地填充增长;此外,城市交通和自然环境优越的湖泊水系对城市空间的扩展有很强的吸引作用。

(3)从不同情景下的模拟结果来看,3种情景下农业用地、水域、林地和荒地的面积均有所减少,现状趋势情景和基本保护情景下农田和水域减少的幅度较大，会继续加剧区域的生境破碎、耕地功能下降、水资源匮乏等生态问题,说明现状趋势和一般保护两种情景下,城市重要生态组分及其生态服务能力将受到较为显著的损害,进而威胁城市生态系统健康和可持续发展。严格保护情景下模拟结果显示,城市居住用地扩张的程度得到了明显的控制,水域和林地得到了有效的保护,对于重要的自然生态系统组分保护及其服务能力维持可以起到显著作用，保障城市系统健康和可持续发展。

本文的研究结果可以为城市空间动态相关研究和武汉城市发展调控提供参考。此外，城市空间的演变受多种因素的综合影响,存在许多不确定性,进一步更为深入的研究,应当研究将城市交通发展、新区建设、功能区转移、城市发展规划等多方面的影响因素纳入模型,揭示其对城市空间动态的影响机制并在此基础上进行未来情景预测模拟,为城市可持续管理提供更为精确和明确的参考依据。

# 参考文献（References）：

[1］傅伯杰，张立伟.土地利用变化与生态系统服务：概念、方法与进展.地理科学进展，2014,33(4)：441-446.  
[2］赵丹,李锋，王如松.城市土地利用变化对生态系统服务的影响——以淮北市为例.生态学报，2013，33（8)：2343-2349.  
3]SetKCnealpHutaLoblforeastsbepasitdtpactsodesitydborfthe National Academy of Sciences of the United States of America,2012,109(40）：16083-16088.  
[4］严岩，赵景柱，王延春，罗祺姗.中国耕地资源损失驱动力分析.生态学杂志，2005，24（7)：817-822.  
[5] Huang S L， Wang S ${ \mathrm { H } } ,$ Budd WW. Sprawl in Taipei'speri-urban zone：responses to spatial planning and implications for adapting globalenvironmental change.Landscape and Urban Planning，2009,90(1/2）: 20-32.  
[6]ClarkeKC,GdosLJLoseoucellatomatooeldGoubagohpdictfoSanFiodWasgto/Baltimore.International Journal of Geographical Information Science,1998,12（7）： 699-714.  
[7]SilvaEA,CarkeKC.CalbrationoftheSLEUTHurbangrowthodelforLisbonandPorto，Portugal.Computers，EnvironmentandUrbanSystems,2002,26(6): 525-552.  
8 黎夏，叶嘉安.基于神经网络的单元自动机CA及真实和优化的城市模拟.地理学报，2002，57(2)：159-166.  
[9] 詹云军，黄解军，吴艳艳.基于神经网络与元胞自动机的城市扩展模拟.武汉理工大学学报，2009，31（1)：86-90  
[10]刘小平，黎夏，艾彬，陶海燕，伍少坤，刘涛.基于多智能体的土地利用模拟与规划模型.地理学报，2006，61（10)：1101-1112.  
[11] 单玉红，朱欣焰.城市居住空间扩张的多主体模拟模型研究.地理科学进展，2011，30(8)：956-966.  
[12] 田光进，邹建国.基于智能体模型的土地利用动态模拟研究进展.生态学报，2008，28（9)：4451-4459.  
[13] Dietzel C,ClarkeKC.Towardoptimalcalibrationof theSLEUTHlandusechangemodel.TransactionsinGIS,20O7,11(1）：29-45.  
[14] 张岩，李京，陈云浩.利用 SLEUTH模型进行北京城市扩展模拟研究.遥感信息，2007，（2)：50-54.  
[15] 李明杰，钱乐祥，吴志峰，崔海山，侯西勇.广州市海珠区高密度城区扩展 SLEUTH模型模拟.地理学报，2010,65(10)：1163-1172.  
[16] 刘勇，吴次芳，岳文泽，黄经南.基于 SLEUTH模型的杭州市城市扩展研究.自然资源学报,2008，23（5）：797-807.  
[17] DietzelC，ClarkKC.Thftofdisagatiglndsecategielautoatadrngodelcalibationdforecastioes，Environment and Urban Systems，2006，30(1）：78-101.