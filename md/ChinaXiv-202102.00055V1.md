# 基于地理探测器的干旱区内陆河流域产水量驱动力分析以疏勒河流域为例

郑续¹，魏乐民¹，郭建军²，周妍妍¹，陈冠光¹，岳东霞}（1兰州大学资源环境学院，甘肃 兰州730000;2中国科学院西北生态环境资源研究院，沙漠与沙漠化重点实验室,甘肃 兰州730000)

摘要：明确干旱区产水量的驱动因素，能为区域水资源优化和可持续发展提供科学依据。基于MODIS植被指数、HWSD的土壤数据集以及气象要素数据，采用InVEST模型和地理探测器探究疏勒河流域多年平均产水量的空间分布，揭示不同空间尺度上产水量的单因子及双因子交互驱动机制。结果表明：疏勒河流域多年平均产水量呈现南部>北部>中部。流域尺度上，产水量空间格局的主导驱动力为降水，坡度与降水交互驱动作用最为显著。区域尺度上，南部山区、北部马鬃山地区和中部平原区的主导驱动力各不相同，分别为日照时数、人为干扰强度、降水，双因子交互作用显示人为干扰强度与其它因子的交互最为显著。不同土地利用类型中，耕地产水量的主导驱动力为坡度，而其它地类产水量的主要影响因子为降水。各地类中降水与其他因子的交互均大大增强了单因子驱动力。因此，干旱区产水量多尺度驱动机制研究对区域水资源可持续管理至关重要。

关键词：产水量；InVEST模型；地理探测器；疏勒河流域

# 文章编号：

生态系统服务指生态系统为人类直接或间接提供的各种产品和服务，是维持人类生产生活和可持续发展的基础1。近年来，国内外学者主要集中于生态系统服务制图[2]、服务间权衡与协同[3]、不同情景下生态系统服务的优化4等方面的研究，其中产水量作为重要的支持服务之一，其驱动力研究亦是国内外学者关注的焦点。产水量驱动力的研究不仅可以深入的了解致使其发生变化的机理，亦可为系统间产水服务的优化奠定基础。目前关于产水量驱动力的研究主要有定性和定量两大类方法，定性的分析仅能表征产水量与各因子的驱动关系，不能确定各因子在多大程度上影响产水量空间格局，如孙艺杰等5以黄土高原为例，定性的探究了地形坡度以及退耕还林对水源涵养等服务的影响；傅伯杰等以综述的形式定性的描述了不同土地利用对各类生态系统服务的重要作用。而定量研究可以量化自然、社会经济、人类活动等方面的驱动因子对产水量的影响程度。如LI等利用相关分析法定量的探究了自然和人为驱动力对水截留量等服务的影响;陈珊珊等8利用逐步回归的方式探究了商洛市蒸散发、土壤深度等自然因子与产水量间的显著程度;窦攀烽等9利用统计方法探究了不同气候背景和土地利用情景对产水服务的贡献度。

驱动力的研究不仅可以深入的了解致使生态系统服务发生变化的机理，亦可为系统之间的服务流动以及生态系统服务的优化、区域空间规划奠定基础。已有产水量驱动力定量分析主要利用相关性分析、主成分分析、地理空间加权、回归分析等方法，这些方法需要线性假设前提，具有一定的主观性，且不能反映因子之间的交互作用。但是，产水量的变化不仅是一个因子单独的驱动作用，而是由多个因子共同影响。地理探测器作为一种揭示现

# 干旱区地理

象驱动力的统计方法，不仅可以定量的探测各因子对产水量的解释度，而且可以探测各驱动因子间的交互作用。然而，目前产水量交互作用驱动机制的研究还存在不足。大多数学者仅开展了流域、县域以及栅格等空间尺度产水量单因子驱动机制的研究,如王鹏等[0]利用地理探测器探究整个海原县水源涵养等服务的单因子驱动力；苏常红等"在流域尺度展开了产水量等服务的单因子驱动力分析；张琨等[12]在栅格尺度上探究植被覆盖度对产水量等生态系统服务的影响。而关于不同空间尺度上产水量交互作用驱动机制的研究还较少。但尺度效应作为景观生态学的核心问题3，尺度的改变往往直接导致研究结果的变化。因此，针对不同空间尺度的产水量交互探测的工作亟待开展。

疏勒河流域地处我国西北干旱区，降水稀少，日照时数大。近年来，人类活动的干扰强度加大，流域内大量的水被用于农田灌溉，打破了水资源在空间上的平衡4，有研究表明根据绿洲目前的用水模式,有必要考虑绿洲的适宜规模[15]。因此,选择该流域进行产水量驱动力研究具有典型性和代表性。已有研究表明，产水量的空间分布格局受到地形因子、气象要素、植被覆盖度和人类活动等因素的影响[2.16],因此,本文基于InVEST模型和地理探测器探究疏勒河流域产水量空间分布规律，并选取高程、坡度、降水、气温、日照时数、植被覆盖度、人为干扰强度7大要素作为驱动因素，探讨不同空间尺度上各要素以及双因子交互作用对流域产水量空间分布的解释度，以期深入了解产水量空间分布格局的驱动机制，为流域生态系统服务优化和水资源的科学配置提供重要参考。

# 数据来源与研究方法

# 1.1 研究区概况

疏勒河流域地处我国西北内陆，地理位置介于$9 3 . 4 1 3 ^ { \circ } \mathrm { E } { \sim } 9 8 . 9 8 4 ^ { \circ } \mathrm { E } , 3 8 . 2 5 2 ^ { \circ } \mathrm { N } { \sim } 4 2 . 7 9 3 ^ { \circ } \mathrm { N }$ 之间，流域总面积约为 $1 . 2 5 \times 1 0 ^ { 5 } ~ \mathrm { k m } ^ { 2 }$ 。流域地势南北高，中部低，海拔在 $9 1 4 \sim 5 ~ 8 1 6 ~ \mathrm { m }$ 之间。结合地形地貌以及行政分区，可将该流域划分为3大自然地理分区，分别为北部马鬃山区、中部平原区和南部山区[（图1)。流域内平均降水量小，光热资源丰富，潜在蒸散量大于 $2 8 0 0 \mathrm { m m }$ ,水资源极度匮乏[14,18],流域中下游及北部马鬃山区的绝大部分区域为戈壁、裸岩、沙地，生态环境极度脆弱

![](images/da023a19242262066e6b5df6eec0b766dae5fcb98c235f99e5349514764f24a4.jpg)  
图1研究区概况图  
Fig.1Sketch map of the Shule River Basin

# 1.2数据来源与处理

本研究所需要的基础数据如表1所示，植被覆盖度的计算方法见参考文献[19]，所有数据均在Arc-GIS10.3平台上统一投影为WGS_1984_UTM_47N，并重采样为 $1 0 0 0 \mathrm { m }$ 。

# 1.3研究方法

1.3.1InVEST模型本研究利用InVEST模型中产水量模块计算产水服务，为了概化气象要素波动对评估结果造成的误差，该模型中气象要素采用37a(1979—2015年)均值。模型中需要输入数据包括多年平均降雨、土地利用、流域边界、土壤深度、年均潜在蒸散发[20]、植被可利用水[21]、蒸散发系数[22]等,其中,根系深度参考类似研究的相关成果[21.23]。产水量表示为某一栅格的降水量与实际蒸散发量之差，模型中计算公式如下：

$$
Y _ { \mathrm { { i } } } = \left( 1 - { \frac { A E T _ { \mathrm { { i } } } } { P _ { \mathrm { { i } } } } } \right) \times P _ { \mathrm { { i } } }
$$

式中： $Y _ { i }$ 表示每个栅格单元 $i$ 上的年产水量; $A E T _ { i }$ 表示栅格单元 $i$ 的年实际蒸散量； $P _ { i }$ 表示栅格单元 $i$ 的年降水量。

1.3.2地理探测器地理探测器最早由王劲峰等[24]提出，后经过不断的完善，其探测两因素之间的相

# 表1研究所用到的基础数据汇总表

Tab.1 Basic data summary used in the study   

<html><body><table><tr><td>数据名称</td><td>时间分辨率</td><td>空间分辨率</td><td>数据来源</td></tr><tr><td>数字高程模型</td><td>1</td><td>30m</td><td>地理空间数据云</td></tr><tr><td>土地利用</td><td>2001年、2005年、2010年、2015年</td><td>30m</td><td>利用Landsat数据目视解译</td></tr><tr><td>气温、降水</td><td>1979—2015年</td><td>0.1°</td><td>寒区旱区科学数据中心</td></tr><tr><td>月日照时数</td><td>2001年、2005年、2010年、2015年</td><td>1 km</td><td>国家地球系统科学数据共享服务平台</td></tr><tr><td>归一化植被指数</td><td>2001年、2005年、2010年、2015年</td><td>1 km</td><td>美国国家航空航天局提供的MODIS13A3产品</td></tr><tr><td>土壤数据</td><td>1</td><td>1 km</td><td>南京土壤所提供的1：1000000土壤数据集</td></tr></table></body></html>

关性比通用的回归更加可靠，并广泛应用于自然科学、社会科学以及环境科学等领域[10.25-27],包括分异及因子探测、交互作用探测、生态探测及风险探测4个模块。其核心思想是两个变量之间存在较高的相关性，则其在空间上分布规律也应该具有相似性，并且可以避免因子间的共线性，各个影响因子相互独立，添加或排除因子并不影响其他因素的结果[28]。用 $q$ 值度量模型的解释度,表达式如下：

$$
q = 1 - \frac { \displaystyle \sum _ { h = 1 } ^ { L } N _ { h } \sigma _ { h } ^ { 2 } } { N \sigma ^ { 2 } }
$$

式中： $q$ 表示自变量对因变量的解释度，取值范围在[0-1]之间； $h$ 表示分区数目； $N \mathrm { ~ , ~ } N _ { h }$ 分别为全区及层内的单元数； $\sigma \cdot \sigma _ { \boldsymbol { h } }$ 分别为全区和层 $h$ 的方差。

运用地理探测器探究各驱动因子对生态系统产水服务的解释度，参考前人相关研究中创建的随机点数[29],结合疏勒河流域实际面积，在整个流域以及不同的地理分区创建1000个随机点，不同的土地利用创建500个随机点，并提取每个随机点上的驱动因子及产水量的数值用于输入模型。由于地理探测器的自变量只能识别类型量，故将本研究中所用到的海拔、坡度、植被覆盖度、人为干扰强度指数、日照时数、气温、降水等7个连续性自变量利用自然断点法进行离散化，使其成为类型量。

1.3.3人为干扰强度人为干扰强度指数(HDI)可以反映不同土地利用所承受的人类活动的干扰强度[30]。为了体现人为干扰强度的空间异质性,本文对覆盖整个流域的网格（ $8  { \mathrm { k m } } \times 8  { \mathrm { k m } }$ )进行采样计算，样本点数据代表整个的格网的值，并在Arc-GIS10.3中进行克里格插值，从而得到 $1 \ \mathrm { k m } \times 1 \ \mathrm { k m }$ 的人为干扰强度空间分布图。

$$
H D I = \sum _ { i = 1 } ^ { n } A _ { i } { \frac { P _ { i } } { A } }
$$

式中： $n$ 为土地利用类型数量； $A _ { i }$ 为土地利用类型i的总面积; ${ \boldsymbol { P } } _ { i }$ 为土地利用类型i的人为扰动强度参数；A为所有土地利用类型的总面积。

# 2结果与分析

# 2.1产水量的空间分布

疏勒河流域多年平均产水量在空间上存在较为明显的异质性(图2),整体上南部山区产水量最大，北部马鬃山地区次之，中部平原区最小。南部山区降雨量大，且大面积的冰雪覆盖增大了地面的反照率，使得地表温度降低，实际蒸散发量减小，因而该区域的多年平均产水量较大。中部平原区的其余区域多年平均产水量在 $3 0 \sim 8 0 ~ \mathrm { { m m } }$ 之间，而花海、昌马、双塔等灌区土壤含水率较高[7],在土地利用类型不变的情况下，较高的土壤含水率使该区域

![](images/28681ec5a531ed1351a8e7ceeee9043b56b05ee0af6dd251b385bbbe960ba6cf.jpg)  
图2疏勒河流域2001—2015年平均产水量空间分布Fig.2Spatial pattern of annual average water yieldin the Shule River Basin during 2OO1—2015

# 干吴区地理

实际蒸散发量大幅增加，产水量几乎为0。北部马鬃山区降雨大于平原地区[31],且地表覆被为戈壁、沙漠、裸岩等,多年平均产水量在 $6 0 \sim 1 2 0 \mathrm { m m }$ 之间。

# 2.2产水量的驱动力分析

2.2.1流域尺度上产水量的驱动力分析降水的因子解释度最高，表明降水对流域产水量的空间异质性具有显著影响，且箱体长度最长，降水的解释度变幅较大(图3)，这可能与西北干旱地区降雨量减少，但降雨变率增大有关[32]。日照时数对流域产水量的因子解释度仅小于降水。高程的因子解释度约为0.21,最短的箱体长度表明其对产水量空间分布的影响最稳定。人为干扰强度、植被覆盖度和气温的因子解释度相差不大，坡度对流域产水量的解释能力最弱。

![](images/0a9030e556e4e62300c6ffe04ad515051f09d525d5f6128ffc7761d7c72d4b4d.jpg)  
图3疏勒河流域2001—2015年各驱动力 因子解释度(q值)箱线图 Fig.3Box plots of driving force in the Shule River Basin during 2001—2015

疏勒河流域因子间交互均大于任意单因子的解释度(表2)，且存在非线性增强和双因子增强两种结合方式，非线性增强交互作用更为显著。其中，降水与高程、日照时数、人为干扰强度、气温的交互以及气温门高程、气温门日照时数、高程门日照时数均为双因子增强型(门表示因子间交互），其余任意两因子间为非线性增强型。疏勒河流域降水对产水量空间格局的作用显著(图3)，双因子交互解释度均不小于0.60，其中降水和坡度间交互作用最为显著(0.75)。人为干扰强度与任意因子交互解释度均大于单因子解释(0.10)的四倍之多，即表明在疏勒河流域，产水量的空间格局受到自然和社会经济因素的共同制约，人类活动对产水量的影响在其他因子的综合作用下会呈现明显的放大作用，其中，人为干扰强度坡度最为显著(0.70)，因此，在坡度较大地区应减少人类活动的干扰，否则其对环境的反馈作用是呈倍数增长的。

2.2.2不同地理区的产水量驱动力分析在南部山区，日照时数因子解释度最大(0.33)，这可能因为南部山区水量充足，日照时数所引起的蒸散发量大，从而影响该地区产水量的空间格局。中部平原区降水作为主要的驱动因子，其因子解释度达到0.30，植被覆盖度和人为干扰强度的解释度次之。在北部马鬃山地区，人为干扰强度对流域产水量的空间格局起着显著的影响，这可能是因为北部马鬃山区土地利用类型较为单一，人类活动更容易改变该区域生态系统服务的空间格局(图4)。

不同地理区双因子交互作用存在着明显的差异(图5)。整体上，各个分区自然与社会经济因素

# 表2疏勒河流域驱动因子交互作用探测结果

Tab.2 Detection results of driving factor interaction in Shule River Basin   

<html><body><table><tr><td></td><td>植被覆盖度</td><td>高程</td><td>日照时数</td><td>坡度</td><td>人为干扰强度</td><td>气温</td><td>降水</td></tr><tr><td>植被覆盖度</td><td>0.11</td><td>NE</td><td>NE</td><td>NE</td><td>NE</td><td>NE</td><td>NE</td></tr><tr><td>高程</td><td>0.38</td><td>0.20</td><td>BE</td><td>NE</td><td>NE</td><td>BE</td><td>BE</td></tr><tr><td>日照时数</td><td>0.65</td><td>0.49</td><td>0.32</td><td>NE</td><td>NE</td><td>BE</td><td>BE</td></tr><tr><td>坡度</td><td>0.52</td><td>0.45</td><td>0.67</td><td>0.15</td><td>NE</td><td>NE</td><td>NE</td></tr><tr><td>人为干扰强度</td><td>0.52</td><td>0.57</td><td>0.58</td><td>0.70</td><td>0.10</td><td>NE</td><td>BE</td></tr><tr><td>气温</td><td>0.39</td><td>0.33</td><td>0.46</td><td>0.50</td><td>0.63</td><td>0.18</td><td>BE</td></tr><tr><td>降水</td><td>0.72</td><td>0.66</td><td>0.60</td><td>0.75</td><td>0.68</td><td>0.65</td><td>0.57</td></tr></table></body></html>

注:NE表示非线性增强型;双因子解释度大于两因子解释度之和;BE表示双因子增强型;两因子交互的解释度大于单因子解释度的最大值

![](images/4e6109e5a2f2490f5ab2fd6db677dce94a11d551418931854d329eb1078ffa1c.jpg)  
图4疏勒河流域不同地理分区因子解释度(q值) Fig.4Factor interpretation of different geographic zones in the Shule River Basin

![](images/d2d3415b484c4d0b429ae3de5ee8ff98426d98b6d2c9240c4c9f540143c9b805.jpg)

交互显著，体现了人类活动扰动与自然基底环境叠加后对产水量空间分布的综合影响，这一结果也说明了产水量的空间分布格局受多种因素的影响，但各个分区主导交互因子各有不同。由于疏勒河干流以及其支流经过流域南部山区及中部平原区，且降水量充足，因此，南部山区和中部平原区，人为干扰强度与降水的交互解释度最大，分别为0.71和

0.61。南部山区其它因子两两之间的交互解释度均不小于0.3。中部平原区，坡度门高程、坡度降水以及植被覆盖度、人为干扰强度与其它因子交互解释度均大于0.5。而北部马鬃山地区，日照时数门气温、日照时数门高程以及人为干扰强度与其它各因子的交互最为显著(解释度均在0.5以上），其中，人为干扰强度n高程最显著(0.58)。高程与其它因子的交互作用次之，降水和坡度两因子与其它各因子的交互作用强度较弱(解释度均低于0.5)。

![](images/c52545767c49d54d9a771b692b9dde9eb30857c18046c47fa48e375afc6adbf9.jpg)  
图5疏勒河流域各地理分区双因子交互解释度  
Fig.5Factor interactive interpretation of different geographic zones in the Shule River Basin   
图6疏勒河流域不同土地利用类型的因子解释度Fig.6Factor interpretation of differentland use in the ShuleRiver Basin

2.2.3不同土地利用的产水量驱动力分析建设用地、未利用地、草地、林地的主导因子各不相同（图6)。耕地产水量空间格局的主导因子为坡度(0.14)，人为干扰强度和日照时数次之，其余各因子的解释度均小于0.1,这可能是疏勒河流域耕地在整个流域的分布较为集中，在降水等因素变化不大的情况下，坡度的变化会影响坡体的产水能力。其它地类中降水均作为主导解释因子，其中，建设用地多为人工地面且植被覆盖度较低，因此，除植被覆盖度和人为干扰强度的因子解释度较低外，其余因子解释度均大于0.65;未利用地中，人为干扰强度和坡度的因子解释度小于0.3,其余各因子解释度较大；相较于林地中降水的因子解释度，草地中降水的解释度较大(0.44)，这可能是因为草地的蒸散发量相对林地较小[33],故被植被吸收利用的水分较多，因此，对产水量的贡献较大。

不同土地利用双因子交互作用均增强了单因

# 干旱区地理

![](images/59a5a45210c90d1277549cb7914e5dabd909e6558a502649b80ef6b38729e8a8.jpg)  
图7不同土地利用类型双因子交互解释度 Fig.7Factor interactive interpretation of different land use in the Shule River Basin

子解释度(图7)。耕地双因子交互中植被覆盖度门日照时数最为显著(0.45)，坡度作为耕地的主导解释因子，该因子与其他因子的交互均不小于0.3。除此之外，其余地类均表现为降水与某一因子的交互最为显著。其中，建设用地多为裸露的人工表面，该地类上生态水文过程几乎完全被改变[34],双因子解释度均大于0.8，其中降水门高程的因子解释度最大。未利用地中降水门坡度为0.96，且任意双因子解释度均大于0.5。草地生态系统双因子交互中人为干扰强度门植被覆盖度、人为干扰强度降水、降水门坡度、气温坡度的因子解释度均大于0.7，其中人为干扰强度门降水最强(0.79)。林地生态系统人为干扰较小，自然因子之间的交互作用最显著，其中降水与坡度的双因子交互解释度最高(0.50)，表明林地产水量空间格局受降水和坡度两因子共同制约。人为干扰强度与植被覆盖度、降水、高程的交互大大提升了林地产水量格局的解释度。

# 3讨论

在西北干旱区生态环境建设中，产水量作为重要的生态系统服务功能是维系生态安全和可持续发展的关键。目前产水量的研究主要集中在单因子驱动力，关于不同尺度驱动力交互作用的定量研究还较少。本文利用InVEST模型和地理探测器，定量的探究了干旱区内陆河流域不同空间尺度上产水量的双因子交互驱动力。

在整个流域上，降水对疏勒河流域的产水量空间分布有着显著的影响，尽管不同的地理分区主导解释因子各不相同，但降水仍在不同区域内对产水量起着相对一致的重要作用，这也与已有产水量驱动力的研究结论吻合[35],同时也不能否认其它因子对产水量空间格局的影响。另一方面，疏勒河流域产水量的驱动力也存在较为明显的空间异质性，南部、中部、北部主导因子分别为日照时数、降水、人为干扰强度，这可能因为南部山区存在冰雪覆盖区，该区域日照时数所引起的蒸散发量大，从而影响该地区产水量的空间格局；中部平原区，土地利用类型主要为耕地、草地和未利用地，且海拔相对较低，该区域降水量对产水量空间格局起着相对重要的作用；在北部马鬃山地区土地利用类型较为单一，人类活动等外界因素容易改变该区域产水量的空间格局。不同土地利用上，耕地作为坡度制约的地类，其产水量的空间分布格局受坡度的影响亦最大；其它土地利用类型产水量的主导因子均为降水。不同尺度上产水量单因子驱动力的差异揭示了产水量变化的尺度效应，提示在进行区域水资源调配优化时需要充分考虑尺度的选取问题。

在实际生态过程中，一种现象往往由多种因素共同作用，不同空间尺度上，疏勒河流域产水量空间格局多因子驱动机制也存在差异。流域尺度上，降水与其它因子的交互皆显著，其中降水与坡度的双因子交互解释度最高，即疏勒河流域尺度上产水量的空间格局主要受区域自然基底环境的影响，社会经济因素的影响相对较小;不同地理分区中，南部和中部平原区人为干扰强度与降水的交互作用显著，北部马鬃山地区，人为干扰强度与高程的交互作用最强，即受人类活动的干扰，自然和社会经济因子之间的交互作用最为显著，体现了人类活动扰动与自然基底环境叠加后对产水量空间分布的综合影响，而这与孙栋元等[3关于疏勒河流域干流降水量受人类活动和气候因素双重影响的研究结论一致;尽管不同的土地利用类型下垫面各异，但因子间的交互作用均大大增强了单因子解释度。疏勒河流域水资源严重短缺，灌溉农业导致耕地的土壤含水量较高[],较丰富的含水量增大了日照时数引起的实际蒸散发量，同时农作物生长季植被覆盖度较高，这也进一步增加了该区域的实际蒸散发量[7],从而直接影响耕地的产水量空间格局,因此,耕地中植被覆盖度门日照时数的双因子交互作用最为显著(0.45)。除此之外，其它土地利用类型上均表现为降水与某一因子的交互显著，这也与戴尔阜等[38]关于气候因子是影响产水量空间格局的主要驱动力的结论相一致。自然界和人类生态系统间存在着密切的联系，产水量的空间格局受到多种因素共同的影响，不能将其看作一个孤立的现象，本研究说明产水量的空间分布格局受到自然和人为因素共同的作用，双因子的交互更进一步明晰产水量空间格局影响机制。

考虑到地理尺度在可持续发展评估中的重要性[39],我们认为本文案例中不同尺度研究均对区域水资源可持续评估与管理有着重要的作用。由于可持续性的空间维度亦作为决策的影响因素之一，因此不同尺度上主导驱动力的异质性将导致决策和政策制定的差异。同样不同尺度的研究结果可能导致决策的冲突[40],例如，在整个流域上，水资源的可持续性更侧重对流域降水与坡度的关注（表2)，而在不同地理分区中则要将人类活动的影响纳入到水资源管理中(图4、图5)。因此，本研究中同时考虑不同尺度的产水量驱动机制有助于更好的指导区域水资源调配。

InVEST模型中的产水量模块以水量平衡原理为基础，规避了当量因子法计算产水量的主观性，但研究区南部有冰雪覆盖，冰雪融水会增加流域的来水量，使模型中计算的产水量相对偏小。另外，限于数据问题，本文仅考虑了流域、地理分区和不同土地利用的因子驱动力，没有在更多的尺度上进行产水量驱动力异质性的探索，这些不足有待于在今后的研究中不断改善。

# 4结论

产水量的变化关乎干旱区生态系统安全，基于地理探测器的双因子交互探测有助于进一步加深对产水量驱动机制的理解，本文关于不同空间尺度上产水量驱动力的研究得到如下结论：

（1）疏勒河流域多年平均产水量南部 $\mathrm { \dot { > } }$ 北部>中部。(2）流域尺度上产水量空间格局主要受自然因素降水的影响，且降水与其它因子交互最为显著。

(3）不同地理分区，南部山区和中部平原区主导因子分别为日照时数和降水，北部马鬃山区人为干扰强度解释度最大；人为干扰强度与自然因子的交互作用在各个地理分区均显著。

(4）不同土地利用上，耕地坡度因子解释度最大，其它地类降水因子解释度最大。不同地类上双因子交互作用均显著。

# 参考文献(References)

[1]COSTANZA R,D'ARGE R, DEGROOT R,et al. The value of the world's ecosystem services and natural capital[J]. Ecological Economics,1998,25(1): 3-15. [2]LING HB, YAN JJ,XUHL,et al. Estimates of shifts in ecosystem service values due to changes in key factors in the Manas River basin,northwest China[J]. Science of the Total Environment,   
2019,659: 177-187. [3]ZHENG Z M,FUB J,FENG X M. GIS-based analysis for hotspot identification of tradeoff between ecosystem services: A case study in Yanhe Basin, China[J]. Chinese Geographical Science,2016,26 (4): 466-477. [4]WU X T, WANG S,FUB J, et al. Land use optimization based on ecosystem service assessment:A case study in the Yanhe watershed[J].Land Use Policy,2018,72:303-312. [5]孙艺杰,任志远,郝梦雅,等.黄土高原生态系统服务权衡与协 同时空变化及影响因素—以延安市为例[J].生态学报,2019,   
39(10): 3443-3454. [SUN Yijie,RENG Zhiyuan, HAO Mengya, et al. Spatial and temporal changes in the synergy and trade-off between ecosystem services,and its influencing factors in Yanan, Loess Plateau[J]. Acta Ecologica Sinica,2019,39(10):3443-   
3454.] [6]傅伯杰,张立伟.土地利用变化与生态系统服务:概念、方法与 进展[J].地理科学进展,2014,33(4):441-446.[FU Bojie, ZHANG Liwei. Land-use change and ecosystem services: Concepts, methods and progressJ]. Progress in Geography,2014, 33(4): 441-   
446.] [7]LI J, ZHOU Z X. Natural and human impacts on ecosystem services in Guanzhong-Tianshui economic region of China[J]. Environmental Science and Pollution Research,2016,23(7): 6803-6815. [8]陈姗姗,刘康,包玉斌,等.商洛市水源涵养服务功能空间格局 与影响因素[J].地理科学,2016,36(10):1546-1554.[CHEN Shanshan,LIU Kang,BAO Yubin,et al. Spatial patern and influencing factors of water conservation service function in Shangluo City[J]. Scientia Geographica Sinica,2016,36(10): 1546-1554.] [9]窦攀烽,左舒翟,任引,等.气候和土地利用/覆被变化对宁波地 区生态系统产水服务的影响[J].环境科学学报,2019,39(7):   
2398-2409.[DOU Panfeng, ZUO Shudi, REN Yin,et al. The impacts of climate and land use/land cover changes on water yield service in Ningbo region[J]. Acta Scientiae Circumstantiae,2019,

# 干吴区地理

39(7): 2398-2409.]   
[10] 王鹏,刘小鹏,王亚娟,等.黄土丘陵沟壑区生态移民过程及其 生态系统服务价值评价——以宁夏海原县为例[J].干旱区地 理,2019,42(2): 433-443.[WANG Peng, LIU Xiaopeng, WANG Yajuan,et al. Ecological migration process and the evaluation of its ecosystem service value in Loess hilly and gully region: A case study of Haiyuan County,Ningxia[J]. Arid Land Geography,2019, 42(2): 433-443.]   
[11] 苏常红,王亚璐.汾河上游流域生态系统服务变化及驱动因素 [J].生态学报,2018,38(22): 7886-7898.[SU Changhong,WANG Yalu.Evolutionofecosystemservicesanditsdrivingfactors in the upper reaches of the Fenhe River watershed,China[J].Acta Ecologica Sinica,2018,38(22): 7886-7898.]   
[12] 张琨,吕一河,傅伯杰,等.黄土高原植被覆盖变化对生态系统 服务影响及其阈值[J].地理学报,2020,75(5):949-960. [ZHANG Kun,LYU Yihe,FU Bojie,etal. The effects of vegetation coverage changes on ecosystem service and their threshold in the Loess Plateau[J]. Acta Geographica Sinica,2020,75(5): 949-960.]   
[13] 邬建国.景观生态学-格局、过程、尺度与等级[M].第二版.北 京：高等教育出版社,2007.[WU Jianguo.Landscape ecology: Pattern, process,scale and hierarchy[M]. $2 ^ { \mathrm { n d } }$ ed. Beijing: Higher Education Press,2007.]   
[14] 刘建军.疏勒河流域水环境综合治理方案探讨[C]/2018(第六 届）中国水生态大会,2018:1-5.[LIU Jianjun.Discussion on comprehensive water environment management scheme of Shule River Basin[C]//2018(6\*）ChinaWaterEcology Conference, 2018: 1-5.]   
[15]ZHANG X F,JIN X,BAI X,et al. Impacts of water resource planning on regional water consumption pattern: A case study in Dunhuang Oasis,China[J]. Journal of AridLand,2019,11(5):713-728.   
[16] 张玲玲.甘肃白龙江流域生态系统服务评估及影响因素[D].兰 州：兰州大学,2016.[ZHANG Lingling.Ecosystem servicesassessment and its driving forces in the Bailongjiang Watershed of Gansu[D].Lanzhou: Lanzhou University,2016.]   
[17] 郭晓娟.疏勒河流域净初级生产力与土壤含水量耦合关系研究 [D].兰州:兰州大学,2019.[GUO Xiaojuan.Coupling relationship between net primary productivity and soil moisture content in the Shule River Basin[D].Lanzhou $:$ Lanzhou University,2019.]   
[18] 郭晓娟,周妍妍,郭建军,等.疏勒河流域土壤含水率反演[J].干 旱区研究,2018,35(6):1317-1326.[GUO Xiaojuan,ZHOU Yanyan, GUO Jianjun,et al.Inversion of soil moisture content in the Shule River Basin[J].Arid Zone Research,2018,35(6): 1317-1326.]   
[19] 陈洪磊,欧阳炜,吕凤玲,等.官渡河流域植被覆盖变化与地形 因子相关性[J].水土保持研究,2019,26(3):135-140,147. [CHEN Honglei, OUYANG Wei,LYU Fengling,et al. Variation of vegetation cover and its correlation of topographic factors in Guandu River Basin[J].Research of Soil and Water Conservation, 2019, 26(3): 135-140,147.]   
[20]WOLOCK D M, MCCABE G J. Estimates of runoff using water-balance and atmospheric general circulation models[J]. JAWRA Journal of the American Water Resources Association,1999,35(6): 1341-1350. [21] 贾芳芳.基于 $\mathrm { I n V E S T }$ 模型的赣江流域生态系统服务功能评估 [D].北京:中国地质大学(北京),2014.[JIA Fangfang.InVEST model based ecosystem services evaluation with case stdy on Ganjiang River Basin[D].Beijing:China University of Geosciences (Beijing),2014.] [22] 周彬.基于生态服务功能的北京山区森林景观优化研究[D].北 京:北京林业大学,2011.[ZHOU Bin.Forest landscape optimization based on eeosystem services for mountainous area of Beijing [D]. Beijing: Beijing Forestry University,2011.] [23] 徐佩,彭培好,王玉宽,等.九寨沟自然保护区生态水的计量与 评价研究[J].地球与环境,2007(1):61-64.[XU Pei,PENG Peihao, WANG Yukuan, et al. Estimation and assessment on eco-water storage of the Jiuzhaigou Natural Reserve[J].Earth and Environment, 2007(1): 61-64.] [24]王劲峰,徐成东.地理探测器:原理与展望[J].地理学报,2017,   
72(1):116-134.[WANG Jinfeng,XU Chengdong. Geodetector: Principle and prospective[J].Acta Geographica Sinica,2017,72 (1): 116-134.] [25] 邹雅婧,闫庆武,谭学玲,等.渭北矿区土壤侵蚀评估及驱动因 素分析[J].干旱区地理,2019,42(6):1387-1394.[ZOU Yajing, YAN Qingw,TAN Xueling, et al. Evaluation of soil erosion and driving factors analysis in Weibei mining area[J].Arid Land Geography,2019,42(6): 1387-1394.] [26] 王伟,张佳莹,彭东慧,等.中国区域旅游发展潜力演变格局与 影响因素分析[J].干旱区地理,2019,42(4):953-960.[WANG Wei, ZHANG Jiaying,PENG Donghui,et al. Evolving pattern and influencing factors of regional tourism development potential in China[J]. Arid Land Geography,2019,42(4): 953-960.] [27] 雒占福,张金,刘娅婷,朱立祥.2000—2017年中国城市绿化水 平的时空演变及其影响因素研究[J].干旱区地理,2020,43(2):   
481-490.[LUO Zhanfu,ZHANG Jin,LIU Yating,et al. Spatialtemporal evolution characteristics and affecting factors of urban greninglevel in China during 20o—2017[J].AridLandGeography, 2020,43(2): 481-490.] [28]DING Yueting, ZHANG Ming, QIAN Xiangyan, et al. Using the geographical detector technique to explore the impact of socioeconomic factors on $\mathrm { P M } _ { 2 . 5 }$ concentrations in China[J]. Journal of Cleaner Production,2019,211: 1480-1490. [29]YUAN Xuefeng,HAN Jichang,SHAO Yajing,et al. Geodetection analysis of the driving forces and mechanisms of erosion in the hilly- gully region of northern Shaanxi Province[J]. Journal of Geographical Sciences,2019,29(5): 779-790. [30] 贡璐,张海峰,安尼瓦尔·阿木提,等.干旱区内陆河流域典型 绿洲土地利用格局变化中的人为影响空间分异研究[J].干旱 区地理,2009,32(4):585-591.[GONG Lu, ZHANG Haifeng, AMUTI Aniwar,et al.Spatial diference analysis of land use change and human impact in typical oasis in arid land[J].Arid Land Geography,2009,32(4): 585-591.] [31]张丽.疏勒河流域降水分布规律及变化趋势分析[J.甘肃水利 水电技术,2015,51(7): 1-4,21.[ZHANGLi.Analysis of precipitation distribution and variation trend in shule river basin[J]. Gansu Water Resources and Hydropower Technology,2015,51(7): 1-4,21.]   
[32]徐栋.全球变暖背景下亚非干旱区降水变化及其与水汽输送的 关系研究[D].兰州:兰州大学,2016.[XUDong.Characteristics of precipitation and its relationship with vapor transport in AsiaAfrica arid region under global warming[D].Lanzhou: Lanzhou University,2016.]   
[33]张明明.2000—2015年中国干旱半干旱区蒸散发时空变化及 其影响因素分析[D].西安:长安大学.2019.[ZHANG Mingming.Analysis of the temporal and spatial variation of evapotranspiration and its driving factors in arid and semi-arid region of China from 2000 to 2015[D].Xi'an: Chang'an University,2019.]   
[34]唐文超.基于生态水文过程的城市水空间体系构建方法[D].重 庆：重庆大学,2015.[TANG Wenchao.The construction method of city water space system based on ecohydrological process[D]. Chongqing: Chongqing University,2015.]   
[35]赵亚茹,周俊菊,雷莉,等.基于InVEST模型的石羊河上游产水 量驱动因素识别[J].生态学杂志,2019,38(12):3789-3799. [ZHAO Yaru,ZHOU Junju,LEI Li,et al. Identification of water yield drivers in the upstream of Shiyang River based on InVEST model[J]. Chinese Journal of Ecology,2019,38(12): 3789-3799.]   
[36]孙栋元,齐广平,鄢继选,等.疏勒河干流降水变化特征[J].干旱 区研究,2020,37(2):291-303.[SUN Dongyuan,QI Guangping, YAN Jixuan,et al.Research on variation characteristics of precipitation in the mainstream of Shule River[J].Arid Zone Research, 2020,37(2): 291-303.]   
[37] 张殿君,张学霞,武鹏飞.黄土高原典型流域土地利用变化对蒸 散发影响研究[J].干旱区地理,2011,34(3):400-408.[ZHANG Dianjun,ZHANG Xuexia,WUPengfei.Relationship between ET and LUCC in typical watershed of Loess Plateau over the past 20 years[J].Arid Land Geography,2011,34(3): 400-408.]   
[38]戴尔阜,王亚慧.横断山区产水服务空间异质性及归因分析[J]. 地理学报,2020,75(3): 607-619.[DAI Erfu,WANG Yahui. Spatial heterogeneity and driving mechanisms of water yield service in the Hengduan Mountain region[J].Acta Geographica Sinica, 2020,75(3): 607-619.]   
[39]GUO Jianjun,YUE Dongxia,LI Kai,et al.Biocapacity optimization in regional planning[J]. Scientific Reports,2O17,7: 41150.   
[40]HOU Ying,LYU Yihe,CHEN Weiping,et al. Temporal variation and spatial scale dependency of ecosystem service interactions:A case study on the central Loess Plateau of China[J].Landscape Ecology,2017,32(6):1201-1217.

# Driving force analysis of water yield in inland river basins of arid areas based on geo-detectors: A case of the Shule River

ZHENG Xu'，WEI Le-min'， GUO Jian-jun²，ZHOU Yan-yan', CHEN Guan-guang'，YUE Dong-xia' (1CollegeofEarthand Environmental Sciences,Lanzhou University,Lanzhou 73ooo0,Gansu,China; 2KeyLaboratory ofDesert and Desertification,Northwest InstituteofEco-Environmental and Resources, Chinese Academy of Sciences,Lanzhou 73ooo0,Gansu, China)

Abstract: Definingthe driving factors of water yield inarid areas can provide a scientific basis for regional water resources optimization and sustainable development.In this paper,the InVEST model and geo-detectors were used to explore the spatialdistribution oftheaverage annual water yield inthe Shule River Basin,Gansu Province, China and thedriving forces at diferent spatial scales in 2015,basedonthe MODIS vegetation index,HWSDsoil dataset, and meteorological data.Results show that the average annual water yield of the Shule River Basin was inan order of south $>$ north $>$ middle.At the basin scale,the dominant driving force of the spatial pattern of water yield is precipitation.The interaction of slopeand precipitation is the most significant for water yield.At the regional scale, the dominant interpretation factors in the southern Qilian Mountains,northern Ma Zong mountains area,and the central plainsare precipitation,human disturbance intensity,and precipitation,respectively.Most significantfactor interaction is between human disturbance intensityand other factors.Indiffrent land uses,the slope incultivated land is the dominant driving force,while precipitation of other land types is the main influencing factorof water yield.The interaction between precipitationand otherfactors in various categories has greatly enhanced the single factor driving force.Therefore,the research atthe multi-scaledriving mechanism of water yield inarid regions is crucial to the sustainable management of regional water resources.

Key words:water yield; InVEST model; geo-detector; Shule River Basin