# 黄骅市未利用地开发适宜性分区研究

何玲1,2；闫慧慧1；贾启建³；张利1,2；宋周莺4(1.河北农业大学国土资源学院保定07100;2.国土资源部环渤海土地利用—河北沧州野外基地沧州061000;3.河北农业大学农村发展学院保定071000;4.中国科学院地理科学与资源研究所北京100101)

摘要：未利用地作为重要的土地后备资源，研究其开发适宜性及其开发模式是实现土地可持续利用的重要举措，对保障我国粮食安全、实现经济发展和生态文明建设均具有重要意义。同时，科学引导土地开发利用，对未利用地可能的开发利用方向进行适宜性评价、研究确定开发分区，也是推动国土科技创新的重点。在此背景下，本文以河北省黄驿市为例，将未利用地做宜耕、宜建和生态风险三重评价，并结合权衡模型和遗传算法对上述三重评价进行耦合分析，确定开发分区，进而解决多开发方向之间的权衡问题，为全国未利用地开发提供示范。研究表明：1)黄驿市未利用地宜耕开发可分为4个等级，主要为 $N$ 级(不适宜)宜耕未利用地，集中在市东部沿海;2)宜建开发可分3个等级，主要为J3级(低适宜)宜建未利用地，集中分布在市中部和西部;3)生态风险区可分为5级，呈东高西低的空间格局，主要为中低和中高生态风险未利用地;4)黄骅市未利用地资源可分为耕地、建设用地、生态用地三种重点开发区，其中,耕地重点开发区主要分布在中部和西部，建设用地重点开发区主要分布在黄骅镇周围,生态用地重点开发区主要位于东部沿海。研究结果可为破解土地供需两难提供科技支持。

关键词：未利用地;适宜性评价;生态风险评价;开发分区；黄驿市中图分类号：F301.24 文献标识码：A

# Regionalization of suitable development on unutilized land in Huanghua City HE Ling1, 2, YAN Huihui1, JIA Qijian3, ZHANG Li1, 2, SONG Zhouying4

(1.Collgddoalibodgona;gacaiobe CircumBohastdsosa;uraeloaib BaodingO710oo,China;4.Institute of Geographic Sciences and Natural Resources Research CAS,Beijing 1Ooo1,China)

Abstract:Asanimportantreservelandresources,studyingunutilizedland'sdevelopmentsuitabilityanddevelopmentmodeisan important measure torealize sustainablelanduse,anddevelopingunutilizedlandisanimportantactiontoachievefoodscurity, economicdevelopmentand ecologicalcivilization.Meanwhile,inorder to guide developmentandutilizationofunutilizedland, suitableevaluationandexploitation partitionsarethefocusonhowtopromote scientificandtechnological innovation.Wetake Huanghua Cityasacasetostudytheevaluationonsuitabilityandecologicalriskofutilizedland,asedonwhich weusecoupling modelandgeneticalgorithmtoevaluate thetripletcoupling exploitationpartitions ofunutilizedland.Andwe hope thecasestudy canprovidemethodologicaldemonstrationsondevelopmentandutilzationofunutizedland.Researchresultsilustratethat,()The exploitationsuitabilityofthearableunutilizedlandincludesfourgrades,andthelargestarableunutilizedlandisintheeastof Huanghuacity.(2)Theconstructivesuitabilityof theunutilizedlandhas three grades,andthethird grade whichconcentrateinthe centerandwestofHuanghuacityhas thebiggestarea.(3)Therearefivegradesaboutecologicalriskregion,whichhighecological riskregionsareintheeastofHuanghuacityandlowecologicalriskregionsareinthe westofthecity.Thelargestregionisidle to lowecologicalriskegion.(4)ItcanbedivdedintothreeKindsofeyexploitationpartitions,suchasexploitationpartitionofrable land,constructieland,ndologicallandeploiatiprtinofablendinlyonctratsinterdstf thecity,theexploiationpartitionofconstructielandmainlylocatedintecentralofteHuanghacity,theexploitatiopartitionof ecologicaland mainlyconcentrated intheeastsideof thecity.Theresultsmaycrack the dilemmaof land supplyanddemand.

Keywords: Unutilized land; Suitable evaluation; Ecological risk evaluation;theexploitation partitions; Huanghua city

# 1引言

中国正处于转型发展的关键时期，随着工业化、城镇化的快速推进，由此带来的土地资源合理开发约束和资源瓶颈的重要途径。2013年,国土资源部发布的《全国国土规划纲要(2011\~2030年)》明确指出，“推进未利用地开发利用,是统筹经济发展与耕地保护、破解土地供需两难的必然选择,是化解征地矛盾、促进社会和谐稳定的重要出路”。

近年来,国内外学术界也开始逐渐重视未利用地资源的研究。一方面,部分学者从实际工作出发,分析在国土资源部门的组织引导下,我国各地的未利用地开发模式及其存在的问题。例如普遍存在的耕地"占优补劣"现象[5-7];以及在未利用地开发过程中,不合理开发导致的生态问题,如土地沙化、水土流失及土壤盐渍化等[8-10]。另一方面,国内外学者针对上述问题进行了深入研究并寻求解决办法。例如Pereira[11]、Fitzsimons[12]、Mehrmoush[13]、唐常春[14]、金贵[15]等不断丰富与完善了土地评价指标体系,从不同角度对土地利用适宜性进行评价，进而引导土地利用分区;张凤荣[16]、舒帮荣[17]、吴大放[18]和关小克[19]等则从生态安全性和生态适宜性角度提升了生态指标在评价指标体系中的比重;廖和平[20]、刘耀林[21、欧阳志云[22]等将模糊评价法、计算智能理论和生态位适宜度方法引入土地评价领域,拓展了该领域的研究方法体系。但总体而言,现有文献的研究对象主要是未利用地整体,较少对更细致的未利用地地类进行适宜性评价；另外，对更细致的未利用地地类进行多目标分析及多用途耦合的决策方法仍有待探索。

正是在这种背景下,本文以河北省黄骅市为例,通过对该市常见的未利用地宜耕和宜建用途建立评价指标体系,基于多学科交叉研究,采用综合指数法、权衡模型和遗传算法对土地开发利用及其风险进行评估,进而通过耦合分析确定土地利用开发分区。首先,本文将未利用地分别进行宜耕、宜建和生态风险三重评价;其次,结合权衡模型和遗传算法对上述三重评价进行耦合,进而确定土地利用开发分区,以期为我国未利用地开发及土地利用规划提供新方法及研究示范。

# 2 数据与方法

# 2.1 研究区概况

黄骅市位于河北省东南部, $3 8 ^ { \circ } 0 9 ^ { \prime } { \sim } 3 8 ^ { \circ } 3 9 ^ { \prime } \mathrm { N }$ ，东经 $1 1 7 ^ { \circ } 0 5 ^ { \prime } { \sim } 1 1 7 ^ { \circ } 4 9 ^ { \prime } \mathrm { E }$ 。黄骅市地势低洼平坦,海拔高程在$ { 1 { \sim } } 7  { \mathrm { ~ m ~ } }$ 之间,年平均气温 $1 3 ^ { \circ } \mathrm { C }$ 左右,年蒸发量 $1 5 0 0 { \sim } 2 0 0 0 \mathrm { m m }$ ，降水量 $5 0 0 { \sim } 6 0 0 ~ \mathrm { m m }$ 。全市土壤瘠薄,盐碱化程度严重,土壤含盐量在 $0 . 3 \%$ 以上,最高达 $3 . 2 9 \%$ ；土壤有机质含量较低,平均为 $9 . 5 \ \mathrm { g { \cdot k g } ^ { - 1 } }$ 。全市有未利用地 $6 6 5 9 0 . 5 3 \mathrm { h m } ^ { 2 }$ ，占全市土地总面积的 $2 9 . 4 6 \%$ ，涉及地类主要有盐碱地、其他草地、内陆滩涂和沿海滩涂四种地类,各地类面积分别为 $3 4 \ 0 7 5 . 6 5 \ \mathrm { h m } ^ { 2 }$ 、 $2 7 0 6 . 3 2 \mathrm { h m } ^ { 2 }$ 、 $6 8 1 1 . 1 3 \mathrm { h m } ^ { 2 }$ 、 $2 2 9 9 7 . 4 3 \mathrm { h m } ^ { 2 }$ 。盐碱地所占比例最大,为全市未利用地面积的 $5 1 . 1 7 \%$ ，其次为沿海滩涂，占全市未利用地面积的 $34 . 5 4 \%$ ,其他草地的分布面积最少,为 $4 . 0 6 \%$ 。

# 2.2 数据来源

未利用地资源适宜性评价及开发分区,涉及生态、社会、经济等多方面的诸多指标,指标涉及面广、数据量大。本文研究数据一部分来自303个有效样点实地调查获取的一手数据,另一部分来自河北省国土、建设、水利、环保等部门。1)国土资源局: $1 : 1$ 万最新土地利用变更调查成果, $1 : 1$ 万遥感影像,新一轮市乡两级土地利用总体规划,土地整治与基本农田规划,地质灾害防治规划,耕地后备资源调查资料。2)建设规划局:城市总体规划,城镇体系规划,建筑地基承载力技术规程。3)水利局:水利志,水资源开发利用现状与综合评价,地下水开采相关文件。4)环保局:生态环境规划相关资料。

# 2.3 研究方法

# 2.3.1未利用地适宜性评价方法

1)适宜性评价步骤

未利用地评价的前提是合理划分评价单元，常见的划分方法有叠置法、地块法和网格法等,划分方法不同评价结果存在差异。选取地块法划分评价单元要求对研究区内土地状况十分熟悉,该方法能避免由于单元划分打破地块边界的缺陷,评价结果便于操作,地块开发利用方向更加明确。

适宜性评价具体操作步骤如下：第一，根据未利用地特点和地表形态对宜耕或宜建利用的限制，建立指标体系;指标选取、指标分值及权重均采用特尔斐法确定，特尔斐法是采用背对背的通信方式征询专家小组成员的预测意见，经过多轮征询,使专家小组意见趋于集中并获得集体判断结果。第二，定量化处理各评价指标相关数据;确定评价指标适宜度属性值,输入属性数据库,生成矢量格式的适宜性评价底图。第三，将评价底图经过缓冲区处理、栅格化处理生成栅格格式单因子评价图。第四,采用综合指数法计算未利用地开发适宜性。第五,在ArcGIS软件中利用自然断点发对研究区未利用地适宜性进行等级划分。

2)适宜性评价方法 综合指数法

适宜性评价采用综合指数法，根据各评价指标及其分值、权重,进行各指标要素的加权叠加分析,计算得到综合分值[15,23]:

$$
H = \sum _ { j = 1 } ^ { n } w _ { j } f _ { j }
$$

式中, $H$ 为综合分值; $\boldsymbol { w } _ { j }$ 为第 $j$ 个参评因素的权重; $f _ { j }$ 为第 $j$ 个参评因素的质量分值; $n$ 为参评因素总个数。

权重总和为1,综合分值为0\~100分，运用ArcGIS自然间断法将综合分值按上述评价体系进行重分类，划分各土地利用方式适宜性等级分值区间,最终得出综合评价结果。

# 2.3.2未利用地开发生态风险评价

未利用地开发生态风险评价是利用土地科学、环境学、生态学、地理学、生物学等多学科综合知识，采用量化分析技术手段预测、分析和评价将要进行的未利用地开发生态系统及其组分可能造成的损伤。因而，在确定评价指标时既要考虑未利用地特点、又要充分利用周边环境。指标选取、指标分值及权重均采用特尔斐法,评价过程采用综合指数法。

# 2.3.3土地利用开发分区划分方法

未利用地合理开发模式的决策分析过程,需要综合考虑社会、经济、生态等多种影响因素[24-25]。不同决策主体所追求的未利用地适宜性之间可能存在矛盾，为实现最终目标之间的相对均衡，并协调不同利益主体,需在矛盾目标之间寻求平衡点。本文基于已有的宜耕、宜建和生态风险三重评价,结合权衡模型和遗传算法对上述三重评价进行耦合分析,进而确定土地利用开发分区。

(1)权衡模型的构建方法

遗传算法是一类随机优化算法,通过不断对染色体的评价以及对染色体中基因的作用,有效地利用已有信息来指导搜索,从而改善优化质量的状态。本研究利用遗传算法,以未利用地宜耕、宜建、宜生态(所有未开发为耕地或建设用地的地类,且可依据实际情况用作林地、牧草地或保持现状的地类,本文统称为宜生态用途)等用地类型为染色体,以未利用地总面积与社会经济发展状况为约束条件模拟其过程,通过模型反复迭代,求得模型非劣解组合，以便划分开发分区。

1)设置耦合要素。耦合要素即模型变量,综合考虑资料可获取性与变量可操作性，设置宜耕、宜建、宜生态三种未利用地开发利用方式为变量。其中,宜耕未利用地设为 $x _ { \iota }$ ,宜建未利用地设为 $x _ { 2 }$ ,宜生态未利用地设为 $x _ { 3 }$ 。

2)确定耦合目标。耦合目标由两个或多个分项目标组成,最终实现综合目标。如,未利用地适宜性目标包括经济、社会、生态效益目标。综合目标即是实现多目标最优化。其原始模型为:

$$
\operatorname* { m a x } ( X ) = { \Big \{ } f _ { 1 } ( x ) , f _ { 2 } ( x ) , \cdots f _ { p } ( x ) { \Big \} }
$$

式中， $X$ 为综合效益,元; $f _ { I } \left( x \right) , f _ { 2 } \left( x \right) , \ldots f _ { p } \left( x \right)$ 为分项目标效益,元; $P$ 为耦合目标个数。

$\textcircled{1}$ 适宜性目标

提取各评价单元适宜性评价等级结果,求和得到研究区全域未利用地开发适宜性评价结果,最终目标是使其最大化。具体公式计算如下：

$$
f _ { 1 } \left( x \right) = \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } s _ { i j } x _ { i j }
$$

式中， $f _ { 1 } \left( x \right)$ 为分项目标效益,元; $m$ 为未利用地开发利用类型数, $( m { = } 1 , 2 , 3 )$ ： $n$ 为参评单元个数; $x _ { i j }$ 为评价单元 $j$ 作为 $i$ 类土地利用方式的面积, $\mathbf { m } ^ { 2 } ; \mathbf { \boldsymbol { s } } _ { i j }$ 为评价单元 $j$ 作为 $i$ 种土地利用方式利用综合指数法得出的适宜性分值。

$\textcircled{2}$ 经济、社会、生态效益目标

经济、社会与生态各分项效益目标通过相关文献初步确定[24-25],利用特尔斐法结合黄骅市实际情况修正,修正结果分别按如下公式进行计算:

$$
\begin{array} { c } { { f _ { 2 } \left( x \right) = \displaystyle \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } a _ { i j } x _ { i j } } } \\ { { f _ { 3 } \left( x \right) = \displaystyle \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } b _ { i j } x _ { i j } } } \end{array}
$$

$$
f _ { 4 } \left( x \right) = \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } c _ { i j } x _ { i j }
$$

式中， $f _ { 2 } \left( x \right) \cdot f _ { 3 } \left( x \right) \cdot f _ { 4 } \left( x \right)$ 分别为研究区未利用地资源开发利用的经济效益、社会效益、生态效益，元； $a _ { i j } \ 、 \ b _ { i j }$ 、 $c _ { i j }$ 分别为评价单元 $j$ 作为 $i$ 类土地利用类型的经济、社会、生态相对效益系数(表1),其他符号含义同上。

Table 1Relative efficiency coefficient values of three types of land use   

<html><body><table><tr><td>未利用地利用类型</td><td>经济效益系数 Coefficient of economic</td><td>社会效益系数 Coefficient of social benefit</td><td>生态效益系数 Eco-efficiency coefficient</td></tr><tr><td>Utilization types of unused land</td><td>efficiency</td><td></td><td></td></tr><tr><td>宜耕 Cultivation suitability 宜建 Construction suitability</td><td>0.39 1.00</td><td>1.00 0.51</td><td>0.28 0.03</td></tr><tr><td>宜生态 Ecological suitability</td><td>0.18</td><td>0.29</td><td>1.00</td></tr><tr><td></td><td></td><td></td><td></td></tr></table></body></html>

# 3)设置约束条件

本文主要考虑研究区土地利用条件状况约束、模型运算约束两个方面。如,土地利用条件约束包括土地总面积,模型运算约束包括系统变量非负约束;若权衡模型中所涉变量为地类面积,必须保证为正数;另外,代表地块的每个评价单元必须有且只有一种对应的土地利用方式,不可出现空缺或重叠现象。

$\textcircled{1}$ 未利用地总面积约束。宜耕、宜建、宜生态三类用地面积之和为研究区未利用地的总面积,即:

$$
A = \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } \ x _ { i j }
$$

式中， $A$ 为研究区未利用地资源总面积， $\mathbf { m } ^ { 2 }$ ；其他符号含义同上。

$\textcircled{2}$ 模型运算约束。系统变量非负约束:权衡模型中所涉变量为地类面积,必须为正数，即:$x _ { 1 } > 0 , { \bf x } _ { 2 } > 0 , x _ { 3 } > 0 .$ 0

(2)遗产算法对权衡模型求解

运用遗传算法借助Matlab 软件辅助进行权衡模型的运行与求解。一是利用Random函数确定初始种群,以此为父代进行后代的遗传变异进化，Random函数在适宜性较高地区随机选择父代个体,生成模型的初始解集;二是根据数据库中单元编号顺序,由左到右,从下到上依次进行邻域分析,选取适应性高的个体进行后代个体遗传;三是在正常遗传操作过程中,随机选取部分个体进行交叉、变异操作,以产生新个体，然后重新计算适应度值的大小,择优进化;四是在模型约束条件制约下,产生符合条件的进化结果,并将结果输入到GIS 数据库中,确定最终结果的数量与空间位置[26-27]。模型运算过程中遗传代数设置为100,优秀后代个体占父代个体数目设置为1/3,依此步骤逐渐进化,使得非劣解集逐渐趋于最优。

# 3计算结果

# 3.1 评价指标体系

3.1.1未利用地宜耕评价指标体系

未利用地宜耕评价分别进行其他草地、盐碱地、沿海滩涂和内陆滩涂等适宜性评价,盐碱地和其他草地评价选取表土质地、土地构型、地下水埋深、地下水开采限制、地下水矿化度、土壤含盐量和植被覆盖度7项指标(表2);内陆滩涂和沿海滩涂选取表土质地、地下水埋深、土地构型、周边土源类型及土源距离5项指标(表3)。

表1三类用地相对效益系数值  
表2盐碱地、其他草地宜耕评价指标体系  
Table 2 The arable suitability evaluation index system of saline-alkali soil and other grass land   

<html><body><table><tr><td>分值</td><td>表土质地</td><td>土体构型</td><td>地下水埋深</td><td>地下水开采限制</td><td>地下水矿化度</td><td>土壤含盐量</td><td>植被覆盖度(%)</td></tr><tr><td>Scores</td><td>Topsoil</td><td>Land structure</td><td>(m)</td><td>Ground-water</td><td>(g/L)</td><td>Soil salt content</td><td>Vegetation</td></tr></table></body></html>

表3内陆滩涂、沿海滩涂宜耕评价指标体系  

<html><body><table><tr><td></td><td>texture</td><td></td><td>Under-ground water depth</td><td>mining limit</td><td>Mineralization of groundwater</td><td></td><td>coverage</td></tr><tr><td>100</td><td>壤土 Loam</td><td>通体壤，壤//壤 Soil/Sand/Soil</td><td>>10</td><td>无 No prohibit</td><td>0~1</td><td>无盐化 No salinozation</td><td>>70</td></tr><tr><td>90</td><td>Sandysoil</td><td>//砂，壤/粘/填 Soil/Stick/Soil</td><td>5~10</td><td></td><td></td><td>轻度</td><td></td></tr><tr><td>80</td><td></td><td>砂/粘/砂 Sand/Stick/Sand</td><td></td><td></td><td>1~2</td><td>Light salinozation</td><td>50~70</td></tr><tr><td>70</td><td>粘y</td><td>St/砂ick粘</td><td></td><td>限制</td><td></td><td>M中rate</td><td></td></tr><tr><td>60</td><td></td><td>Sand/Stick/Stick</td><td>2~5</td><td>Restriction</td><td></td><td>salinozation</td><td>30~50</td></tr><tr><td>50</td><td></td><td>通体粘 Quintana stick</td><td></td><td></td><td>2~5</td><td></td><td>10~30</td></tr><tr><td>40 30</td><td></td><td></td><td></td><td></td><td></td><td>重度 Severe</td><td></td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td><td>salinozation</td><td></td></tr><tr><td>20 10</td><td></td><td></td><td></td><td></td><td>>5</td><td></td><td>0~10</td></tr><tr><td>0</td><td></td><td></td><td>0~2</td><td>禁止 Prohibit</td><td></td><td></td><td></td></tr><tr><td>权重</td><td>0.18</td><td>0.14</td><td>0.14</td><td>0.10</td><td>0.14</td><td>0.18</td><td>0.12</td></tr></table></body></html>

Table 3 The arable suitability evaluation index system of inland and outland beach   

<html><body><table><tr><td>分值 Scores</td><td>表土质地 Topsoil texture</td><td>地下水埋深(m) Under-ground water depth</td><td>土体构型 Land structure</td><td>周边土源类型 Surrounding soil source type</td><td>源距离m) distance</td></tr><tr><td>100</td><td>壤土 Loam</td><td>>10</td><td>通体壤,壤/砂/壤 Quintana soil, Soil/Sand/Soil</td><td>洪积物 Diluvium</td><td>0~500</td></tr><tr><td>90</td><td>砂土 Sandy soil</td><td>5~10</td><td>壤/砂/砂,壤/粘/壤 Soil/Sand/Sand,Soil/Stick/Soil</td><td></td><td></td></tr><tr><td>80</td><td></td><td></td><td>砂/粘/砂 Sand/Stick/Sand</td><td></td><td>500~1000</td></tr><tr><td>70</td><td>粘土Clay</td><td></td><td>u//SdQuintana sand 粘/砂/粘,砂/粘/粘</td><td>黄土台</td><td></td></tr><tr><td>60</td><td></td><td></td><td>Stick/Sand/Stick, Sand/Stick/Stick</td><td>Loess platform</td><td>1000~2000</td></tr><tr><td>50</td><td></td><td>2~5</td><td>通体粘</td><td></td><td></td></tr><tr><td>40</td><td></td><td></td><td>Quintana stick</td><td></td><td></td></tr><tr><td>30</td><td></td><td></td><td></td><td></td><td>2000~3000</td></tr><tr><td>20</td><td></td><td></td><td></td><td></td><td>>3000</td></tr><tr><td>10</td><td></td><td></td><td></td><td>无</td><td></td></tr><tr><td>0</td><td></td><td>0~2</td><td></td><td>No soil source</td><td></td></tr><tr><td>权重 Weight</td><td>0.18</td><td>0.24</td><td>0.28</td><td>0.15</td><td>0.15</td></tr></table></body></html>

# 3.1.2未利用地宜建评价指标体系

宜建评价根据未利用地自然属性、地表形态和工程地质条件对建设用地开发利用的限制程度进行评价。宜建评价针对未利用地总体选择地质灾害、地基承载力、淡水水源保障、地下水埋深、交通条件和洪涝程度6项指标(表4)。刚发布的《国土资源"十三五"规划纲要》明确提出控制建设用地总量,因此本文对各项指标进行严格把控,即任一指标低于30分不做建设用地开发。

<html><body><table><tr><td>分值</td><td></td><td>地基承载力 foundation</td><td>Fr水水源保ce</td><td>地下水埋深 depth</td><td>交通条件(距要道 距)m transportation</td><td>洪度</td></tr><tr><td>100</td><td>低易发区 Low-prone areas</td><td></td><td>充分满足 Sufficient satisfaction</td><td>>3</td><td>0-500</td><td>标高高于设防洪水位≥1.0m</td></tr><tr><td>90</td><td></td><td>坚硬</td><td>满足 Satisfaction</td><td></td><td></td><td></td></tr><tr><td>80</td><td></td><td>Hard</td><td></td><td></td><td>500-1000</td><td>标高高于设防洪水位 0.0~1.0 m</td></tr><tr><td>70</td><td>中易发区</td><td>较硬</td><td></td><td>2-3</td><td></td><td>The elevation is O~1.O meters above the flood control level.</td></tr><tr><td>60</td><td>Middle prone areas</td><td>Relatively hard</td><td>基本满足</td><td></td><td>1000-1500</td><td></td></tr><tr><td>50</td><td></td><td>较软</td><td>Basic satisfaction</td><td>1-2</td><td></td><td>标高低于设防洪水位 0.0~1.5 m</td></tr><tr><td>40</td><td></td><td>Relatively soft</td><td></td><td></td><td></td><td>The elevation is O~1.5 meters lower than the flood control level.</td></tr><tr><td>30</td><td>高易发区</td><td>极软</td><td>缺乏</td><td></td><td>1500-2000</td><td></td></tr><tr><td>20</td><td>High-prone areas</td><td>Very soft</td><td>Lack</td><td><1</td><td>>2000</td><td></td></tr><tr><td>10 权重</td><td>0.17</td><td>0.15</td><td>0.14</td><td>0.21</td><td>0.12</td><td>0.21</td></tr></table></body></html>

注：地质灾害由《黄驿市地质灾害防治"十二五"规划分区图》矢量化获得;地基承载力参考《河北省建筑地基承载力技术规程》DB(J)/T48-2005中关于不同物质构成确定对应承载力获得;交通便利度通过距道路远近做缓冲区，距离道路越近越利于开发建设,反之亦然。

# 3.1.3未利用地开发生态风险评价指标体系

结合未利用地开发生态风险评价特点，从盐渍程度、植被覆盖度、土层厚度和沥涝程度构建指标体系(表5)。

表4未利用地宜建评价指标体系 'able 4 The constructive suitability evaluation index system of unutilized land   
表5生态风险评价指标体系  
Table 5 The ecological risk evaluation index system   

<html><body><table><tr><td colspan="2">盐渍程度 Salinity degree</td><td colspan="2">植被覆盖度 Vegetation coverage</td><td colspan="2">土层厚度 Soil thickness</td><td colspan="2">沥涝程度 Waterlogging degree</td></tr><tr><td>分值</td><td>Grand级gsandard</td><td>分值</td><td>分级标准</td><td>分值</td><td>分级标准 standard</td><td>分值</td><td>Grad标准dard</td></tr><tr><td>20</td><td>轻度盐碱，土壤含盐量<0.2% Light salinozation and Soil salt content is lower than 0.2%</td><td>10</td><td>>70%</td><td>20</td><td>>1m</td><td>20</td><td>降雨强度大于30 mm·h-1,或排水体 系健全,降雨后有短期洪涝。 The rainfallitensity is greater than 30mm/h,or the drainage system is perfect,and there are short-term floods after rainfall.</td></tr><tr><td>40</td><td>中度盐碱,土壤含盐量0.2-0.4% Moderate salinozation and Soil salt content is 0.2-0.4%</td><td>30</td><td>50%~70%</td><td>40</td><td>0.6~1.0 m</td><td>40</td><td>排水体系基本健全,丰年大雨后田 面积水2~3天。 The rainfall intensity is 2O-30mm/h, or the drainage system is basically perfect,and the paddy field will be 2~3 days after the heavy rain in</td></tr></table></body></html>

降雨强度小于 $2 0 \mathrm { m m } \cdot \mathrm { h } ^ { - 1 }$ ，基本无排水体系，一般大雨后田面积水>3天

<html><body><table><tr><td rowspan="2">60</td><td rowspan="2">重度盐碱,土壤含盐量0.4-0.6% Severe salinozation and Soil salt content is 0.4-0.6%</td><td rowspan="2">50</td><td rowspan="2">30%~50%</td><td rowspan="2">60</td><td rowspan="2">0.3~0.6 m</td><td rowspan="2">60</td><td rowspan="2">The rainfall intensity is lower than 2 mm/h,or there is no drainage system and the paddy field will be more tha 3 daysafter the heavy rain in genera year.</td></tr><tr><td></td></tr><tr><td>80</td><td>盐土,土壤含盐量>0.6% Saline soil and Soil salt content is</td><td>70</td><td>10%~30%</td><td>80</td><td><0.3m</td><td>80</td><td></td></tr><tr><td></td><td>above 0.6%</td><td>90</td><td><10%</td><td></td><td></td><td></td><td></td></tr><tr><td>权重 Weight</td><td>0.3</td><td></td><td>0.25</td><td></td><td>0.2</td><td></td><td>0.25</td></tr></table></body></html>

# 3.2未利用地适宜性评价结果

# 3.2.1未利用地宜耕评价结果

根据测算结果，黄驿市的未利用地宜耕性可以划分为4个等级， $H _ { I }$ 值 $\scriptstyle \sum 8 4$ 为S1级(高适宜), $7 6 { \sim } 8 4$ 为S2 级(中适宜), $6 0 \sim 7 6$ 为S3级(低适宜), ${ < } 6 0$ 为 $N$ 级(不适宜)。其中，内陆滩涂主要为S1级宜耕未利用地其他草地主要是S2级宜耕未利用地,沿海滩涂全部为 $N$ 级,盐碱地主要是S1和S2级宜耕未利用地(表6)。

表6黄骅市各地类未利用地资源宜耕评价结果  
Table 6 The arable suitability evaluation results of each type of unutilized land in Huanghua city   

<html><body><table><tr><td rowspan="2">级别 Degree</td><td colspan="2">S1级 S1 degree</td><td colspan="2">S2级 S2 degree</td><td colspan="2">S3级 S3 degree</td><td colspan="2">N级 N degree</td><td colspan="2">总计 Total</td></tr><tr><td>面积rcm2)</td><td>比例%) on</td><td>面积(hm2)</td><td>比o) on</td><td>面积(bm2)</td><td>比pof) on</td><td>面积(hm2)</td><td>比(%) on</td><td>面积(hm2)</td><td>比o) on</td></tr><tr><td>内陆滩涂 inland beach</td><td>4306.79</td><td>19.10</td><td>0.00</td><td>0.00</td><td>2504.34</td><td>43.16</td><td>0.00</td><td>0.00</td><td>6811.13</td><td>10.23</td></tr><tr><td>其他草地 other grass land</td><td>926.39</td><td>4.11</td><td>1330.66</td><td>10.27</td><td>375.56</td><td>6.47</td><td>73.71</td><td>0.29</td><td>2706.32</td><td>4.06</td></tr><tr><td>沿海滩涂 Coastal beach</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>22997.43</td><td>90.97</td><td>22997.43</td><td>34.54</td></tr><tr><td>盐碱地 Saline land</td><td>17319.16</td><td>76.80</td><td>11624.76</td><td>89.73</td><td>2921.92</td><td>50.36</td><td>2209.81</td><td>8.74</td><td>34075.65</td><td>51.17</td></tr><tr><td>总t</td><td>22552.34</td><td>100.00</td><td>12955.43</td><td>100.00</td><td>5801.81</td><td>100.00</td><td>25280.95</td><td>100.00</td><td>66590.53</td><td>100.00</td></tr></table></body></html>

黄骅市未利用地的宜耕资源从空间布局上看(图1),S1级宜耕未利用地资源面积为 $2 2 5 5 2 . 3 4 \mathrm { h m } ^ { 2 }$ ，占全市未利用地资源总面积的 $3 3 . 8 7 \%$ ,主要分布在黄骅市中北部和南部区域,涉及乡镇主要包括吕桥镇、羊二庄回族镇、国营中捷农场、羊三木回族乡等。S2级宜耕未利用地资源面积为 $1 2 9 5 5 . 4 3 \mathrm { h m } ^ { 2 }$ ，占全市未利用地资源总面积的 $1 9 . 4 6 \%$ ，主要分布在黄骅市中部和西部区域。S3级宜耕未利用地资源面积为 $5 8 0 1 . 8 1 \mathrm { h m } ^ { 2 }$ 占全市未利用地资源总面积的 $8 . 7 1 \%$ ;主要分布在黄骅镇周围。 $N$ 级宜耕未利用地资源面积为25280.95$\mathbf { h } \mathbf { m } ^ { 2 } .$ 占全市未利田地资 源总面积的 $3 7 . 9 6 \%$ ，主要

分布在东部沿海。

![](images/c1403278b0a4ba127ba0721314aaada3ce17cad160c1d231c7016a07b444c4e5.jpg)  
图1黄骅市未利用地资

3.2.2未利用地宜建评价结果

根据测算结果,黄驿市的未利用地宜建性可以划分为3个等级,如表7所示, $H _ { 2 }$ 值 $\mathord { \geq } 7 0$ 为 $J I$ 级(高适宜),$5 8 \sim 7 0$ 为 $J 2$ 级(中适宜), $< 5 8$ 为 $J 3$ 级(低适宜)。其中, $J 3$ 级宜建未利用地面积较大，而 $J 2$ 级宜建未利用地面积较小。

表7黄驿市各未利用地资源类型宜建评价结果  
able 7 The constructive suitability evaluation results of each type of unutilized land in Huanghua city   

<html><body><table><tr><td rowspan="3">级别 Degree</td><td colspan="2">J1级 J1 degree</td><td colspan="2">J2级</td><td colspan="2">J3级</td><td colspan="2">总计</td></tr><tr><td colspan="2">面积(hm²)</td><td colspan="2">J2 degree</td><td colspan="2"> J3 degree</td><td colspan="2">Total</td></tr><tr><td>Area</td><td>比例(%) Proportion</td><td>面积(hm²) Area</td><td>比例(%) Proportion</td><td>面积(hm²) Area</td><td>比例(%)</td><td>面积(hm2) Area</td><td>比例(%) Proportion</td></tr><tr><td>内陆滩涂 inland beach</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>6811.13</td><td>14.16</td><td>6811.13</td><td>10.23</td></tr><tr><td>其他草地 other grass land</td><td>0.00</td><td>0.00</td><td>192.01</td><td>39.35</td><td>2514.31</td><td>5.23</td><td>2706.32</td><td>4.06</td></tr><tr><td>沿海滩涂 Coastal beach</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>22997.43</td><td>47.80</td><td>22997.43</td><td>34.54</td></tr><tr><td>盐碱地 Saline land</td><td>17996.17</td><td>100.00</td><td>295.94</td><td>60.65</td><td>15783.54</td><td>32.81</td><td>34075.65</td><td>51.17</td></tr><tr><td>计</td><td>17996.17</td><td>100.00</td><td>487.95</td><td>100.00</td><td>48106.41</td><td>100.00</td><td>66590.53</td><td>100.00</td></tr></table></body></html>

具体来看, $J 3$ 级宜建未利用地面积最大,为 $4 8 1 0 6 . 4 1 \mathrm { h m } ^ { 2 }$ ，占全市未利用地的 $7 2 . 2 4 \%$ 。从空间格局看(图2), $J 3$ 级宜建未利用地主要集中在沿海滩涂和中部地区,涉及乡镇有南排河镇、新村回族乡、南大港管理区和国营中捷友谊农场等;从土地类型看， $J 3$ 级宜建未利用地主要是沿海滩涂和盐碱地,分别占 $J 3$ 级宜建用地的 $4 7 . 8 0 \%$ 和 $3 2 . 8 1 \%$ ；内陆滩涂全部为 $J 3$ 级。 $J I$ 级宜建未利用地面积为 $1 7 9 9 6 . 1 7 \mathrm { h m } ^ { 2 }$ ，占全市未利用地的 27.03,主要分布在中部和西部,包括黄驿镇、羊三木回族乡、旧城镇等乡镇;从土地类型看,全部是盐碱地。 $J 2$ 级宜建未利用地面积很少，主要涉及部分盐碱地和其他草地。

![](images/8a544876909e26152184e629f5eba84bb7f98145b828325d3a8c01d790e6b114.jpg)  
Fig.1 The arable suitability evaluation grades of unutilized land in Huanghua city   
图2黄骅市未利用地资源宜建性评价等级图  
Fig.2 The constructive suitability evaluation grades of unutilized land in Huanghua city

# 3.3未利用地生态风险评价结果

根据生态风险估算结果,将黄骅市未利用地分为高生态风险区、中高生态风险区、中生态风险区、中低生态风险区和低生态风险区。其中,高生态风险区不宜进行耕地和建设用途开发，其他生态风险区参与耦合计算确定开发利用方向。

表8黄驿市各地类未利用地资源生态风险评价结果  
Table 8 The ecological risk evaluation results of each type of unutilized land in Huanghua city   

<html><body><table><tr><td rowspan="2">级别 Degree</td><td colspan="2">低生态风险区 Low ecologically risky zone</td><td colspan="2">中低生态风险区 Middle and low ecologically risky zone</td><td colspan="2">中生态风险区 Middle ecologically risky zone</td><td colspan="2">中高生态风险区 Middle and high ecologically risky zone</td><td colspan="2">高生态风险区 High ecologically risky zone</td></tr><tr><td>面积(hm2) Area</td><td>比例%) on</td><td>面积(hm2) Area</td><td>比( on</td><td>面积(hm2) Area</td><td>比例(%)</td><td>面积(hm2) Area</td><td>比例 on</td><td>面积(hm2) Area</td><td>比例%) on</td></tr><tr><td>内陆滩涂 inland beach 其他草地</td><td>0.00</td><td>0.00</td><td>1001.25</td><td>4.90</td><td>2 482.63</td><td>19.41</td><td>2 468.42</td><td>13.27</td><td>858.83</td><td>67.98</td></tr><tr><td>other grass land</td><td>525.29</td><td>3.89</td><td>1304.48</td><td>6.38</td><td>876.55</td><td>6.85</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td></tr><tr><td>沿海滩涂ch</td><td>0.00</td><td>0.00</td><td>0.00</td><td>0.00</td><td>7 305.36</td><td>57.11</td><td>15 287.57</td><td>82.20</td><td>404.50</td><td>32.02</td></tr><tr><td>盐碱地 Saline land</td><td>12 980.65</td><td>96.11</td><td>18 127.00</td><td>88.72</td><td>2 126.63</td><td>16.63</td><td>841.38</td><td>4.52</td><td>0.00</td><td>0.00</td></tr><tr><td>总计 Total</td><td>13 505.94</td><td>100.00</td><td>20 432.73</td><td>100.00</td><td>12 791.17</td><td>100.00</td><td>18 597.37</td><td>100.00</td><td>1263.33</td><td>100.00</td></tr></table></body></html>

测算结果表明(表8),黄驿市未利用地资源中，中低和中高生态风险区分布最广，面积分别为20 432.73$\mathrm { h m } ^ { 2 }$ 和 $1 8 5 9 7 . 3 7 \mathrm { h m } ^ { 2 }$ ，占未利用地资源的 $3 0 . 6 8 \%$ 和 $2 7 . 9 3 \%$ ;高生态风险区面积最小，占未利用地资源的$1 . 9 0 \%$ ；而低生态风险区和中生态风险区分别占全市未利用地资源的 $2 0 . 2 8 \%$ 和 $1 9 . 2 1 \%$ 。

从空间格局看(图3),黄驿市未利用地生态风险呈现西高东低的空间格局。高生态风险区和中高生态风险区主要分布在东部沿海和中部地区。从土地类型看,高生态风险区和中高生态风险区主要是内陆滩涂和沿海滩涂，低生态风险区和中低生态风险区主要是盐碱地。从适宜性评价结果看，高生态风险区和中高生态风险区主要涉及 $N$ 级宜耕和 $J 3$ 级宜建未利用地,不宜用作第一开发时序用地,人类的开发活动会加剧对区域生态环境破坏，因此该区域可开发为林地等生态系统服务价值相对较高的用地类型或留作最后开发时序用地;中生态风险区分布广泛,涉及各种未利用地类型,适宜性评价结果主要涉及S2级宜耕和 $J I$ 、 $J 2$ 级宜建未利用地,开发活动会对区域生态环境产生影响,因此该区域应尽量不用作第一开发时序用地;低生态风险区和中低生态风险区主要分布在县中西部地区,土地类型主要是盐碱地,适宜性适宜性评价结果主要涉及S1、S2级宜耕和 $J I$ 、 $J 2$ 宜建未利用地,该类型区域内土地开发条件好,可用作首选开发用地。

![](images/465be8734e6b270ad378cacc0b430201f10ec3d87721aae2f4aac3e218ad9087.jpg)  
图3黄骅市未利用地资源生态风险评价等级图

Fig.3 The ecological risk evaluation grades of unutilized land in Huanghua city

# 3.4未利用地开发分区

基于上述分析，根据权衡模型分区方法进行测算,将黄驿市未利用地资源划分为耕地开发区、建设用地开发区和生态用地开发区三种类型(表9)。如图4所示,黄驿市的未利用地资源中生态用地保护区面积最大,主要分布在东部和中部地区;耕地开发区次之，主要分布在中部和西部地区;建设用地开发区面积最小，主要分布在黄骅镇周围。

表9黄骅市各乡镇未利用地开发分区结果  
Table 9 The results on exploitation partitions of unutilized land in Huanghuacity hm²   

<html><body><table><tr><td>乡镇名称 Name of villages and towns</td><td>耕地开发区 The arable exploitation zone</td><td>建设用地开发区 The constructive exploitation zone</td><td>生态用地开发区 The ecological exploitation zone</td><td>乡镇名称 Name of villages and towns</td><td>耕地开发区 The arable exploitation zone</td><td></td><td>建设用地开发区生态用地开发区 The constructiveThe ecological exploitation zone exploitation zone</td></tr><tr><td>常镇 Town</td><td>936.29</td><td>0.00</td><td>853.89</td><td>Na南aT镇wn</td><td>148.68</td><td>200.93</td><td>15986.46</td></tr><tr><td>官庄乡n Village</td><td>429.77</td><td>0.00</td><td>87.97</td><td>齐家务乡 Qijiawu Village 滕庄子乡</td><td>1223.95</td><td>131.33</td><td>456.43</td></tr><tr><td>中捷农场 Zhongjie Farm</td><td>2902.78</td><td>150.39</td><td>4345.19</td><td>Tengzhuangzi Village</td><td>2260.43</td><td>144.71</td><td>2017.85</td></tr><tr><td>H镇 Town</td><td>811.32</td><td>2439.96</td><td>834.42</td><td>X新村回i 羊二庄镇</td><td>0.00</td><td>0.00</td><td>8030.46</td></tr><tr><td>旧城镇 Jiucheng Town</td><td>1400.46</td><td>20.58</td><td>1236.79</td><td>Yangerzhuang Town</td><td>3830.44</td><td>0.00</td><td>2535.17</td></tr><tr><td>Lv昌桥镇wn</td><td>900.00</td><td>0.00</td><td>3310.40</td><td>羊三木 Village</td><td>2036.43</td><td>0.00</td><td>688.94</td></tr><tr><td>南大港管理区 Nandagang Administrative zone</td><td>2225.04</td><td>491.06</td><td>3522.01</td><td></td><td></td><td></td><td></td></tr><tr><td>总计 Total</td><td>19105.58</td><td>3578.97</td><td>43905.98</td><td></td><td></td><td></td><td></td></tr></table></body></html>

![](images/e34496cf5d555349bdb2ba79b529310c93fc46c37b34568f3d6b09239be4e048.jpg)  
图4黄骅市未利用地开发分区图  
Fig.4The exploitation partitions of unutilized land in Huanghua city

耕地开发区面积为 $1 9 \ 1 0 5 . 5 8 \mathrm { h m } ^ { 2 }$ 。占全市未利用地的 $2 8 . 6 9 \%$ ,主要分布在羊二庄镇、中捷农场和滕庄子乡等。该区域适宜性评价多为 $_ { S I }$ 、 $S 2$ 级宜耕未利用地用地和中低生态风险区、低生态风险区。该开发区地势相对平坦,有可利用水源和土源,宜采取工程措施,实施盐碱地整治和土地开发整理工程,增加耕地后备资源,提升耕地质量。

建设用地开发区面积为 $3 5 7 8 . 9 7 \mathrm { h m } ^ { 2 }$ ，占全市未利用地的 $5 . 3 7 \%$ ;空间分布较集中,主要分布黄骅镇等。该开发区适宜性评价主要涉及 $J I$ 、 $J 2$ 级宜建未利用地和低生态风险区、中低生态风险区。基于该区域立地条件较好、交通便利,有可利用水源,在土地利用总体规划确定的有条件建设区和允许建设区范围内,宜鼓励和引导项目实施民生工程、基础设施及重点建设项目。

生态用地开发区面积最大为 $4 3 9 0 5 . 9 8 \mathrm { h m } ^ { 2 }$ 。占全市未利用地的 $6 5 . 9 4 \%$ ,主要位于市东部和中部,包括南排河镇、新村回族乡和中捷农场等。适宜性评价结果多为 $N$ 级和S3级宜耕未利用地, $J 3$ 级宜建未利用地,高生态风险区、中高生态风险区。基于该区域表土质地差,宜尽量减少人类开发利用活动,保持原有生态环境。

# 4结论

土地资源是人类一切社会经济活动的载体,应通过因地制宜的土地利用形成合理的土地利用开发分区[16]。本文以河北省黄骅市为例,基于303个有效样点调查数据,分析未利用地适宜性评价及其开发分区方法,以期为国土资源部门缓解土地供需矛盾、保障经济社会发展提供有效方法。

研究结果显示,(1)黄驿市未利用地宜耕开发可分为4个等级; $N$ 级宜耕未利用地面积最大,主要分布在黄骅市东部区域;S3级宜耕未利用地面积最小;S1级宜耕未利用地主要分布在黄驿市中北部和南部区域、S2 级宜耕未利用地主要分布在黄驿市中部和西部区域。(2)未利用地宜建性可以划分为3个等级， $J 3$ 级宜建未利用地面积最大,主要集中在沿海滩涂和中部地区; $J I$ 级宜建未利用地主要分布在中部和西部; $J 2$ 级宜建未利用地分布广泛，主要涉及部分盐碱地和其他草地。(3)生态风险区可分为5级,黄驿市未利用地生态风险呈现东高西低的空间格局;高生态风险区和中高生态风险区主要分布在东部沿海和中部地区;低生态风险区和中低生态风险区主要分布在市西部和中部,以盐碱地为主。(4)黄驿市未利用地可分为耕地、建设用地、生态用地三种重点开发区,其中,耕地重点开发区主要分布在中部和西部,可通过盐碱地整治和土地开发整理工程,增加耕地后备资源;建设用地重点开发区主要分布在中部黄驿镇周围,宜优先用于民生工程、基础设施及重点建设项目用地;生态用地重点功能区主要位于市东部,宜尽量减少人类开发利用活动，以生态保护为主。

# 5讨论

本文的适宜性评价及其开发分区研究主要是针对黄驿市的每处评价单元进行,尚未考虑地类集中连片情况;在今后的研究中,将会进一步在权衡模型中增加地类集中连片的约束条件,使研究方法更贴合我国国土地资源实际利用情况。

在适宜性评价过程中,只选择了宜耕和宜建用途,黄驿市也有开发为牧草地、湿地、林地等的未利用地,但黄骅市这样的土地面积很少,且宜草、宜湿地等用途可看做生态用途,本文涉及到了生态用地区(将林地、园地、草地、湿地、水域等统一看做生态用地),因此并没有将草地、湿地等开发用途单独评价,为了提高开发分区精度,今后会进一步开展多种用途适应性评价。

# 参考文献 References

[1]WeiYD,YeXY.Urbanization,urban land expansionand environmentalchange in China[J].Stochastic Environmental Research and Risk Assessment,2014,28(4): 757-765.   
[2]HualouLong,JianZou,YansuiLiu.Diferentiationofruraldevelopmentdrivenbyindustrializationandurbanizationiaste coastal China[J]. Habitat International, 2009,33: 454-462.   
[3]陈百明，张凤荣．我国土地利用研究的发展态势与重点领域[J]．地理研究，2011,30(1):1-9.   
Chen BM,Zhang FR.Trend and priority areas in land use research of China[J]. Geographical Research,2O11,30(1):1-9. [4]韦仕川，吴次芳，杨杨．黄河三角洲未利用地适宜性评价的资源开发模式[J].中国土地科学，2013,27(1):55-60. WeiSC,WuCF,YangY.ThelanddevelopmentmodelsinYellowRiverDelta:Basedonland suitabilityevaluation forunutilized land resources[J]. China Land Sciences,2013,27(1): 55-60.   
[5]党丽娟，徐勇，汤青，等．广西西江沿岸后备适宜建设用地潜力及空间分布[J]．自然资源学报，2014,29(3):387-397. DangLJ,XUY,Tang Q,etal.Potentialand spatial distrbutionofsuitableconstructionland along the Xijiang riverside in Guangxi[J]. Journal of Natural Resources,29(3): 387-397.   
[6]魏海，秦博，彭建，等.基于GRNN 模型与邻域计算的低丘缓坡综合开发适宜性评价——以乌蒙山集中连片特殊困难片区 为例[J]．地理研究，2014,33(5):831-841.   
Wei H,QinB,PengJ,etal.Evaluationoncomprehensiveexploitationsuitabilityoflow-slopehillylandbasedonGRNNmodeland neighborhoodcalculation: AcasestudyofWumeng Mountaincontinuouspoverty-stricken region[J]. Geographical Research,2014, 33(5): 831-841.   
[7]唐常春，孙威．长江流域国土空间开发适宜性综合评价[J]．地理学报，2012,67(12):1587-1598.   
Tang CC,Sun W. Comprehensive evaluation ofland spatial development suitability of the Yangtze River Basin[J]. Acta Geographica Sinica, 2012, 67(12): 1587-1598.   
[8]李猷，王仰麟，彭建，等．基于景观生态的城市土地开发适宜性评价：以丹东市为例[J]．生态学报，2010,30(8):2141- 2150.   
LiY,Wang YL,PengJ,etal.Asessmentofurbanlandsuitabilityforconstructioninviewoflandscapeecology:Acasestudyof Dandong City[J]. Acta Ecologica Sinica,2010,30(8): 2141-2150.   
[9]类淑霞,郝晋珉,王丽敏．生态脆弱区宜耕未利用土地开发适宜性评价——以山西省大同市为例[J]．中国生态农业学报， 2011, 19(6): 1417-1423.   
Lei SX,HaoJM,WangLM.Evaluationofexploitatiosuitabilityofunutilizedarablelands inecologicallfragileareas: Acase study of Datong City, Shanxi Province[J]. Chinese Journal of Eco-Agriculture,2011,19(6): 1417-1423.   
[10]韦仕川，刘勇，栾乔林，等．基于生态安全的黄河三角洲未利用地开垦潜力评价[J]．农业工程学报，2013,29(22): 244- 251.   
Wei S C,LiuY,LuanQL,etal.EvaluationonreclamationpotentialofunusedlandoftheYellwriverdeltabasedoncological security[J]. Transactions of the Chinese Society of Agricultural Engineering,2013,29(22): 244-251.   
[11]PereiraJ,LucienDL.Amultiplecriteriadecision-makingaproachtoGS-basedlandsutabilityevaluation[J].Inteatioal Journal of Geographical Information Systems,1993,7(5): 407-424.   
[12]FitzsimonsJPearsonCJ,LawsonC,etal.Evaluationofland-useplaingingenbeltsbasedonitrisiccharacteristicsand stakeholder values[J]. Landscape and Urban Planning, 2012, (106): 23-34.   
[13]MehrnoushA,EzatallahM.Land CapabilityAssssment forRegional Planingusing AHPand GIS at Shandiz Urban Region, Northeast Iran[J]. Environment and Urbanization Asia, 2014,5,(1): 105-118.   
[14]唐常春，孙威．长江流域国土空间开发适宜性综合评价[J]．地理学报，2012,67(12):1587-1598   
Tang CC,Sun W.Comprehensive evaluation ofland spatial development suitabilityof the Yangtze River Basin[J]. Acta Geographica Sinica,2012, 67(12): 1587-1598.   
[15]金 贵，王占岐，胡学东，等．基于模糊证据权模型的青藏高原区土地适宜性评价[J]．农业工程学报，2013，29(18)： 241-250.   
Jing G,Wang ZQ,Hu XD,etal.LandsuitabilityevaluationinQinghai-ibet Plateaubasedonfuzzy weight ofevidence model[J]. Transactions of the Chinese Society of Agricultural Engineering,2013,29(18): 241-250.   
[16]张凤荣，郭力娜，关小克，等．生态安全观下耕地后备资源评价指标体系探讨[J].中国土地科学，2009,23(9):4-8,14. Zhang FR,GuoLN,Guan X K,etal.Studyontheevaluation indicators of thearablelandfromtheviewofecological security[J]. China Land Science, 2009,23(9): 4-8, 14.   
[17]舒帮荣，黄琪，刘友兆，等．基于变权的城镇用地扩展生态适宜性空间模糊评价：以江苏省太仓市为例[J]．自然资源 学报，2012,27(3): 402-412. ShuB R,Huang Q,LiuYZ,etal.Spatial fuzzyasssmentofecologicalsuitabilityforurbanland expansionbasedonvariable weights: Acase study of Taicang[J]. Journal of Natural Resources, 2012, 27(3): 402-412.   
[18]吴大放，刘艳艳，刘毅华，等．耕地生态安全评价研究展望[J]．中国生态农业学报，2015,23(3):257-267.   
WuDF,LiuYY,LiuH,etalProgressoecologicalsecurityevaluatinofculivatedland[J].CineseJualofEco-Agiclture 2015,23(3):257-267.   
[19]关小克，张凤荣，郭力娜，等．北京市耕地多目标适宜性评价及空间布局研究[J]．资源科学，2010,32(3):580-587. Guan XK,ZhangFR,GUOLN,etal.Asuitabilityevaluatioofcutivatedland inbijingformulti-purposes useanditspati temporal investigation[J]. Resources Science,2010,32(3): 580-587.   
[20]廖和平．未利用地适宜性评价方法研究：以攀枝花市仁和区为例[J]．西南师范大学学报：自然科学版，1997,22(2):199 205.   
LiaoHP.Researchonthemethodofsuitabilityevaluationof theunutilizedland[J].JournalofSouthwest China Normal University: Natural Science,1997,22(2): 199-205.   
[21]刘耀林，焦利民．基于计算智能的土地适宜性评价模型[J].武汉大学学报：信息科学版，2005,30(4):283-287. Liu YL,JiaoLM.odeloflandsuitabilityvaationbasedoncomputatioalintelligenceJ].GeomaticsandIfomatioScience of Wuhan University,2005,30(4): 283-287.   
[22]欧阳志云，王如松，符贵南．生态位适宜度模型及其在土地利用适宜性评价中的应用[J]．生态学报,1996,16(2):113- 120.   
Ouyang ZY,WangRS,FUGN.Ecological nichesuitability modelandits applicationinland suitablityasessment[J].Acta Ecologica Sinica,1996,16(2): 113-120.   
[23]袁磊，赵俊三，李红波，等．云南山区宜耕未利用地开发适宜性评价与潜力分区[J]．农业工程学报，2013,29(16):229 237.   
YuanL,ZhaoJS,LIHB,etal.Exploitationsuitabilityevaluationandpotentialareazoningforarableunusedlandinmountainous areasof Yunnan province[J].Transactions oftheChinese Societyof Agricultural Engineering,2O13,29(16):229-237.   
[24]武启祥，杨永芳，朱连奇．县域土地利用结构与效益的权衡[J].经济地理，2013,33(8):147-152.   
Wu QX,Yang YF,ZhuLQ.Trade-OffBetween Structureand EficiencyofLandUsein County Scale[J].Economic Geography, 2013, 33(8): 147-152.   
[25]王华，刘耀林，姬盈利．基于多目标微粒群优化算法的土地利用分区模型[J]．农业工程学报，2012,28(12):237-244. Wang H,LiuYL,JiYL.Landuse zoning modelbasedon multi-objective particle swami optimizationalgorithm.Transactions of the Chinese Society of Agricultural Engineering, 2012, 28(12): 237-244.   
[26]Duh JD,BrownDG.Knowledge-informedParetosimulatedannealingformulti-bjective spatial alocation[J].Computers, Environment and Urban Systems,2007,31(3): 253-281.   
[27]CaoK,BattM,HuangB,etal.Spatialmultijectielanduseotimzatio:extensiostotenon-domnatedsotigeetic algorithm-I[J]. International Journal of Geographical Information Science,2011, 25(12): 1949-1969.