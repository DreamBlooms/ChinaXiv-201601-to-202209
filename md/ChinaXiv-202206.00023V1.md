# 基于博弈论组合赋权的洪水风险评价以武威地区为例

苏广全¹²，吕海深²，朱永华¹²，陈庭兴}²，花佳程1,2（1.河海大学水文水资源与水利工程科学国家重点实验室,江苏 南京210098;2.河海大学水文水资源学院，江苏 南京210098)

摘要：洪水灾害是世界范围内发生最为频繁的自然灾害。中国是世界上洪水风险增长最显著的地区之一。针对甘肃省武威市山洪灾害多发的实情，采用结合主客观权重的博弈论组合赋权的洪水评价方法，应用GIS技术，从致灾因子危害性、孕灾环境稳定性和承灾体脆弱性三方面出发，共选取7个指标构建洪水风险评价指标体系,得到了各评价单元的洪水风险度空间分布。评价结果表明：武威市整体洪水风险等级为较低风险，与历史洪水事件数据吻合较好。其中，洪水高风险区只占总面积的 $4 . 9 4 \%$ ,集中分布于凉州区与古浪县交界处和天祝藏族自治县西南部地区;较低风险区与低风险区之和占总面积的 $4 3 . 8 4 \%$ ,集中于民勤县的东部沙漠区。通过将单一赋权方法与博弈论组合赋权法进行了比较,表明博弈论组合赋权法可以减少单一赋权方法的主观性,提高洪水风险图的精度,为洪水风险管理提供依据。

关键词：洪水灾害；风险区划；层次分析法；博弈论；熵权法；武威地区

洪水灾害是世界发生最为频繁的自然灾害[]。随着气候变化及城市化进程的加速，中国成为百年内世界上洪水风险增长最显著的地区。洪水风险评估作为洪水风险管理的重要工具，对防洪减灾工作具有重要的实际应用价值，可以提高公众对洪水风险的意识。

20世纪以来，各国开展了大量的洪水风险评估研究，形成以下3种洪水风险评估方法：（1）基于历史数据[3-5],结合机器学习或统计方法来确定洪水风险薄弱区；（2）构建评价指标体系进行洪水风险分析[6-8]；（3）采用雷达遥感数据或二维水动力模型进行洪水淹没情景分析[9-]。这些广泛应用的洪水风险分析方法仍存在一些不足：如基于历史资料进行风险分析的方法无法准确反映洪水的空间变异性；构建评价指标体系的方法往往在指标赋权上存在主观性；采用雷达遥感和水动力模型的方法需要大量的数据，且不考虑承灾体和致灾环境对洪水风险的影响[12]。

洪水风险评估需要综合多种要素来确定洪水风险，各要素与最终洪水风险之间的关系具有模糊性和随机性。因此，考虑模糊关系的模糊综合评价模型广泛应用于风险评价[13]。模糊综合评价模型中最重要的问题就是指标权重的确定，以往研究多采用单一赋权方法,如AHP(analytic hierarchy pro-cess)法、德尔菲法等主观赋权方法[68.14],CRITIC法、熵权法等客观赋权方法[613]。然而，主观赋权方法严重依赖专家的主观经验，客观赋权方法仅依靠数据计算权重，不考虑评价因素对评价主体的重要性，得到结果往往与实际情况存在较大差异。为减少赋权主观性，并兼顾决策者经验，结合主客观赋权的博弈论组合赋权方法被提出，以期得到更为符合实际情况的赋权结果[15]

近年来，气候变化导致水循环加速，极端气象事件频发，干旱区、半干旱区的洪水风险评价研究得到关注，但研究尺度多为省一级[4-5.16],没有对洪水风险脆弱区进一步细化，且研究多侧重于洪水危险性，缺乏对洪水易损性的考虑。甘肃省武威市环境气候复杂多变，南部祁连山植被覆盖度高，河网密集，降雨频繁，是甘肃省中部的暴雨中心之一，受到山脉融雪影响，春季洪水时有发生[1];北部为荒漠区，降雨稀少，植被稀疏。受到区域南部多山地形和沙漠地区气候的影响，武威市洪水灾害频率极高，根据历史资料，1971—2012年武威市仅山洪灾害平均每年发生11次[18]。2006年7月底凉州区西营镇山区每小时降水超 $8 0 \ \mathrm { m m }$ ,产生泥石流造成了严重的人员伤亡以及经济损失；2011年8月14—18日凉州、古浪、天祝3县区产生洪涝致 $1 0 . 7 4 \times 1 0 ^ { 4 }$ 人受灾。研究表明，武威市近年山区降水有所增加，洪水频率呈现增长趋势[19]

该研究基于GIS技术，通过对武威市的暴雨次数、归一化植被指数、高程标准差、人口密度等因子的综合分析，并采取博弈论组合赋权方法构建洪水风险评价模型。将AHP法和熵权法与博弈论组合赋权法进行比较，验证所提出的方法对洪水风险管理的有效性，对结果进行合理性分析，对武威市洪水风险进行评估和分区，为武威市的洪水预报、预警、防控提供合理依据。

# 研究区概况与方法

# 1.1 研究区概况

武威地区位于甘肃省中部，地理位置为 $3 6 ^ { \circ } 2 9 ^ { \prime } \sim$ $3 9 ^ { \circ } 2 7 ^ { \prime } \mathrm { N } , 1 0 1 ^ { \circ } 4 9 ^ { \prime } { \sim } 1 0 4 ^ { \circ } 1 6 ^ { \prime } \mathrm { E }$ ，总面积 $3 2 3 4 5 { \mathrm { k m } } ^ { 2 }$ ,是黄土高原、青藏高原和蒙新高原的交汇处(图1)。南接祁连山脉，中部为河西走廊平原，北交腾格里和巴丹吉林两大沙漠,海拔在 $1 2 0 0 { \sim } 4 7 0 0 \mathrm { m }$ 间,由南至北高程逐渐降低。年均降雨量在 $1 0 0 { \sim } 6 0 0 ~ \mathrm { m m }$ ，降雨集中在6一9月，8月最多，降雨量呈现由南向北减少的趋势。区域内蒸发强烈，空气干燥。流经的主要河流为黄河和石羊河，其中石羊河发源于祁连山脉东段，上游由西营河、黄羊河和西大河等河流组成，下游内流入民勤县的沙漠盆地，流域面积 $3 . 9 8 \times 1 0 ^ { 4 }$ $ { \mathrm { k m } } ^ { 2 }$ 。

# 1.2 研究方法

首先，根据灾害理论2及武威自然环境和社会经济特征，按照致灾因子危害性、孕灾环境稳定性、承灾体脆弱性3个方面选取了7个指标作为洪水风险评价要素：第一步，构建洪水风险评价指标体系；

![](images/ed7e54be5efa89e4d39badb4ccaf485adce67324cc31dc01a17ae9c7ff8b55b0.jpg)  
图1研究区概况  
Fig.1 Overview of study area

第二步，通过GIS技术对指标预处理，分别选取熵权法与层次分析法计算客观权重与主观权重，采用博弈论进行组合赋权;第三步，根据博弈论组合赋权得到各指标组合权重，采用模糊综合评价方法构建武威洪水风险评价模型，选择自然断点法将洪水风险等级划分为：高风险、较高风险、中风险、较低风险、低风险等5个风险等级;最后，基于历史洪灾，将AHP法、熵权法与博弈论组合赋权法进行比较，验证所提出的方法对洪水风险管理的有效性，确定洪水风险区划，为洪水灾害管理提供合理建议，研究路线图见图2。

# 1.3洪水风险评价指标体系

研究基于灾害风险理论，通过对致灾因子的风险性评估、孕灾环境稳定性的分析、承灾体易损性的评价来揭示区域的致灾机制[20]，并参考洪水风险的相关研究[6.7.21],选取以下洪水风险评价指标：历史最大日降雨量(RF）、暴雨次数(RFT）、高程标准差（DEM）、归一化植被指数(NDVI）、水系距离（DR）、GDP密度（GDP）、人口密度(POP），以下对指标内容、来源和处理方法进行说明。

# 1.3.1致灾因子指标

(1）历史最大日降雨量(RF)：暴雨是引起武威洪水的主要原因，历史最大降雨则反映了洪水可能造成的最大损失。选择1961一2019年中国地面降水日值 $0 . 5 ^ { \circ } { \times } 0 . 5 ^ { \circ }$ 格点数据集，数据来自国家气象科学数据中心(http://data.cma.cn/)，采用反距离权重插值法获得研究区域逐日降雨数据。

![](images/df1fa615b45dc90a2991b56509aaefe4080980f58d9648ad547b4f9bc5f09dd5.jpg)  
图2研究路线  
Fig.2Flow chart of the study

(2）暴雨次数(RFT)：暴雨发生越频繁的地区，未来发生洪水的可能性越大。根据武威 $0 . 5 ^ { \circ } { \times } 0 . 5 ^ { \circ }$ 格点降雨数据，统计日降雨量 $3 0 \mathrm { m m }$ 以上的次数，采用Kriging插值法计算得到武威暴雨次数数据。

# 1.3.2孕灾环境指标

(1）高程标准差(DEM)：高程标准差越大，表示格点附近的地形起伏越大，更易形成洪水。选择SRTMDEM90M分辨率原始高程数据，数据来自(https://www.gscloud.cn/search）,通过GIS邻域分析得到研究区高程标准差。

(2）归一化植被指数(NDVI)：植被直接影响产汇流过程，对洪水的形成时间和规模大小有着重要作用。数据来自中国科学院资源环境科学与数据中心（https://www.resdc.cn/）。

(3）水系距离(DR)：距离河流湖泊越近，越容易受到洪水侵袭。水系数据来自国家1：1000000标准矢量地图数据（https://www.webmap.cn/main.do?method=index），通过GIS近邻分析得到区域内各点距水系距离。

1.3.3承灾体指标相同量级的洪水发生在不同的地区，所造成的损失是不同的，洪水具有社会属性，涉及到经济和人口要素。GDP密度和人口密度数据均为 $1 \mathrm { k m }$ 栅格数据，来自中国科学院资源环境科学与数据中心（https://www.resdc.cn/）。

确定评价指标体系后，对图层进行预处理，将各指标图层重采样为 $1 \mathrm { k m }$ 分辨率，通过栅格计算器进行指标标准化，标准化方法见式(1）、(2)，通过GIS统计工具统计各评价指标熵值，进而计算熵权法指标权重。

# 1.4 熵权法

熵来源于热力学，用来描述分子运动的不可逆现象。在信息论中，熵反映了信息的无序化程度，可以用来度量信息量的大小，某项指标携带的信息越多，表示该项指标对决策的作用越大，此时熵值越小,即系统的无序度越大[22]。计算指标权重主要步骤如下：

(1)指标数据标准化：对于正向指标，也即越大越优型，按下式处理：

$$
r _ { i j } = \frac { a _ { i j } - ( a _ { j } ) _ { \operatorname* { m i n } } } { ( a _ { j } ) _ { \operatorname* { m a x } } - ( a _ { j } ) _ { \operatorname* { m i n } } }
$$

对于负向指标，即越小越优型指标，按下式处理：

$$
r _ { i j } = \frac { ( a _ { j } ) _ { \mathrm { m a x } } - a _ { i j } } { ( a _ { j } ) _ { \mathrm { m a x } } - ( a _ { j } ) _ { \mathrm { m i n } } }
$$

式中： $( a _ { j } ) _ { \mathrm { m a x } }$ 为第 $j$ 项评价指标的最大值; $( a _ { j } ) _ { \mathrm { m i n } }$ 为第 $j$ 项评价指标的最小值; $a _ { i j }$ 为第 $j$ 项评价指标在第 $i$ 个评价单元的指标值; $r _ { i j }$ 为第 $j$ 项评价指标在第 $i$ 个评价单元标准化指标值。

（2）计算指标熵：

$$
H _ { j } = - { \frac { 1 } { \ln m } } \Biggl ( \sum _ { i = 1 } ^ { m } f _ { i j } \ln f _ { i j } \Biggr ) , ( i = 1 , 2 , \cdots , m ; j = 1 , 2 , \cdots , n )
$$

$$
f _ { i j } = \frac { r _ { i j } } { \displaystyle \sum _ { i = 1 } ^ { n } r _ { i j } }
$$

式中：当 $f _ { i j } = 0$ ， $f _ { i j } \ln f _ { i j } = 0$ ， $\mathbf { \Omega } _ { m }$ 为研究区的基本网格单元数； $n$ 为评价指标数量； $H _ { j }$ 为指标熵。

（3）根据指标熵计算熵权，如下式：

$$
Z _ { j } = - \frac { 1 - H _ { j } } { n - \displaystyle \sum _ { j = 1 } ^ { n } H _ { j } }
$$

式中： $Z _ { j }$ 为第 $j$ 个指标的权重且 $0 \leqslant Z _ { j } \leqslant 1 , \sum _ { j = 1 } ^ { n } H _ { j } = 1$

# 1.5层次分析法(AHP)

层次分析法基本原理是：将评价系统的多种方案的各种要素分解成目标层、准则层、指标层，进行两两判断比较并计算出各要素的权重，根据综合权重按最大权重原则选出最优方案。层次分析法可操作性强，结构灵活，其基本步骤如下：

（1）构建研究系统的递阶层次：层次分析法首先要将所研究对象进行分层次化处理，一般可分为三层，即目标层、准则层、指标层。(2）构造判断矩阵：对同一层次的不同要素进行两两判断，得到两两判断矩阵，为了对其重要性进行分级，通常采用1-9标度法，（3）层次单排序：对本层次各要素重要性进行两两判断，从而计算出对上一层次的权重。

# 1.6博弈论组合赋权

博弈论组合赋权广泛应用于自然灾害风险评价[23-24],在博弈论中,假定各个方案都是理性决策的结果,其目的是寻求目标系统整体利益最优解。其最终结果不是由单一方决策者掌控的，而是由所有决策者共同实现的[24]。它可以归结为一个多主体的优化问题，其基本思想是在不同方法的权重之间寻找一致或妥协，即最终赋权结果与各个基本方法权重之间的偏差达到最小。

博弈论组合赋权的实质是不同赋权方法的结果进行综合，所以使用博弈论进行组合赋权结果前，要对2种方法的赋权结果进行一致性检验。其中不同赋权方法的结果一致性程度可通过距离函数表示：

$$
d \big ( W _ { 1 } W _ { 2 } \big ) = \left[ \frac { 1 } { 2 } \sum _ { j = 1 } ^ { n } \big ( w _ { j } ^ { ( 1 ) } - w _ { j } ^ { ( 2 ) } \big ) ^ { 2 } \right] ^ { \frac { 1 } { 2 } }
$$

式中： $\textstyle \left. W _ { 1 } \right.$ 表示熵权法赋权； $\boldsymbol { W } _ { 2 }$ 表示层次分析法赋权； $\boldsymbol { w } _ { j } ^ { ( 1 ) }$ 表示熵权法赋权权重; $\boldsymbol { w } _ { j } ^ { ( 2 ) }$ 表示层次分析法赋权权重; $d \big ( W _ { 1 } W _ { 2 } \big )$ 值越小,代表2种方法赋权结果一致性越高,研究认为 $d \big ( W _ { 1 } W _ { 2 } \big ) \leqslant 0 . 4$ 时满足一致性要求。

在通过一致性检验后，对2种方法进行组合赋权，具体步骤如下：

（1）假设共采取 $L$ 种方法对评价指标进行赋权，其中任一方法赋权结果的向量为$\omega _ { k } = \{ \omega _ { { k } 1 } , \omega _ { { k } 2 } , \cdots , \omega _ { { k } n } \} ( k = 1 , 2 , \cdots , L )$ ，则 $L$ 个向量可任意线性组合为：

$$
\omega = \sum _ { k = 1 } ^ { L } \beta _ { k } \omega _ { k } ^ { T }
$$

式中： $\omega$ 为全部可能的组合权重向量； $\boldsymbol { \omega } _ { k } ^ { T }$ 为单一方法赋权结果; $\beta _ { \iota }$ 为权重系数且规定 $\beta _ { \iota } > 0$ 0

(2）为了求得最优的权重组合方法，就是使得博弈论组合赋权结果向量与各方法赋权结果向量离差最小，则最优权重系数依据下式求解：

$$
\operatorname* { m i n } \Biggr \| \sum _ { k = 1 } ^ { L } \beta _ { k } \omega _ { k } ^ { T } - \omega _ { g } \Biggr \| ^ { 2 }
$$

式中： $\omega _ { _ { g } }$ 为博弈论组合赋权结果。

根据矩阵微分性质将式(8)展开可得以下线性方程，求解以下线性方程组便可得到最优权重系数：

$$
\left[ \begin{array} { c c c c c } { \omega _ { 1 } \omega _ { 1 } ^ { T } } & { \omega _ { 1 } \omega _ { 2 } ^ { T } } & { \cdots } & { \omega _ { 1 } \omega _ { L } ^ { T } } \\ { \omega _ { 2 } \omega _ { 1 } ^ { T } } & { \omega _ { 2 } \omega _ { 2 } ^ { T } } & { \cdots } & { \omega _ { 2 } \omega _ { L } ^ { T } } \\ { \vdots } & { \vdots } & { \vdots } & { \vdots } \\ { \omega _ { L } \omega _ { 1 } ^ { T } } & { \omega _ { L } \omega _ { 2 } ^ { T } } & { \cdots } & { \omega _ { L } \omega _ { L } ^ { T } } \end{array} \right] \left[ \begin{array} { l } { \beta _ { 1 } } \\ { \beta _ { 2 } } \\ { \vdots } \\ { \beta _ { k } } \end{array} \right] = \left[ \begin{array} { l } { \omega _ { 1 } \omega _ { 1 } ^ { T } } \\ { \omega _ { 2 } \omega _ { 2 } ^ { T } } \\ { \vdots } \\ { \omega _ { L } \omega _ { L } ^ { T } } \end{array} \right]
$$

（3）根据上列线性方程组求得最优权重系数后，对权重系数进行归一化处理，将归一化的最优权重系数带入式(7)，得到博弈论组合赋权结果。

# 2结果与分析

# 2.1多方法对比分析

基于洪水风险灾害理论搭建评价指标体系，根据专家评价构建洪水风险评价指标判断矩阵，各层次指标权重均通过一致性判断。通过GIS分析工具计算洪水风险评价指标熵值，得到熵权法各评价指标权重。两者权重通过一致性检验，经博弈论组合赋权计算权重系数为： $\beta _ { \scriptscriptstyle 1 } = 0 . 5 2 5$ ， $\beta _ { { } _ { 2 } } = 0 . 4 7 5$ 。

根据表1，熵权法赋权结果显示对武威洪水风险影响较大的因子有人口密度、GDP密度及暴雨次数，忽视了高程标准差和水系距离等加剧洪水灾害危险性的环境因素；AHP法结果显示影响较大的因子有高程标准差、历史最大日降雨量和暴雨次数，缺少对人口密度和GDP密度等洪水灾害易损性指标的考虑。

无论是基于数据的客观赋权方法，或是反映专家意见的主观赋权方法都未能综合考虑致灾因子危害性、孕灾环境稳定性和承灾体脆弱性三方面的要素，经过博弈论组合赋权，既能较好地反映专家的主观意愿，又能克服一些客观权重的不足。

由上述3种评价方法分别构建模糊综合评价模型，采用自然断点法对洪水风险进行分级，以验证组合赋权方法的有效性，生成洪水风险空间分布图

# 表1洪水风险评价指标赋权结果

Tab.1 Result of flood risk assessment index weighting   

<html><body><table><tr><td rowspan="2">准则层</td><td rowspan="2">指标层</td><td colspan="3">赋权结果</td></tr><tr><td>熵权法</td><td>AHP</td><td>组合权重</td></tr><tr><td>致灾因子危害性</td><td>历史最大日降雨量(RF)</td><td>0.070</td><td>0.413</td><td>0.233</td></tr><tr><td></td><td>暴雨次数(RFT)</td><td>0.197</td><td>0.131</td><td>0.166</td></tr><tr><td>孕灾环境稳定性</td><td>高程标准差(DEM)</td><td>0.009</td><td>0.113</td><td>0.058</td></tr><tr><td></td><td>归一化植被指数(NDVI)</td><td>0.071</td><td>0.067</td><td>0.038</td></tr><tr><td></td><td>水系距离(DR)</td><td>0.011</td><td>0.073</td><td>0.072</td></tr><tr><td>承灾体脆弱性</td><td>人口密度(POP)</td><td>0.306</td><td>0.138</td><td>0.226</td></tr><tr><td></td><td>GDP密度(GDP)</td><td>0.336</td><td>0.067</td><td>0.208</td></tr></table></body></html>

（图3）。

熵权法得到的洪水风险图中，高风险和较高风险地区面积为 $3 6 5 3 { \mathrm { ~ k m } } ^ { 2 }$ ，占 $1 1 . 7 3 \%$ ，较低风险和低风险地区面积为 $1 9 2 5 2 \mathrm { k m } ^ { 2 }$ ，占 $6 1 . 8 0 \%$ ；采用层次分析法的洪水风险图，高风险和较高风险地区面积为$1 3 8 0 0 ~ \mathrm { k m } ^ { 2 }$ ，占 $4 4 . 3 0 \%$ ，较低风险和低风险地区占$3 8 . 1 0 \%$ ；在组合赋权中，高风险地区和较高风险地区面积占 $3 4 . 8 1 \%$ ,中风险地区占 $2 1 . 3 6 \%$ ,较低风险和低风险地区面积为 $1 3 6 5 6 ~ \mathrm { k m } ^ { 2 }$ ，占 $4 3 . 8 4 \%$ 。AHP法和熵权法所得到的洪水风险分区差异较大，说明采用不同赋权方法的洪水风险评价存在不确定性。

各赋权方法不仅在洪水风险面积上有较大差异，空间分布也存在不同。熵权法较组合赋权风险低估地区占 $56 . 3 4 \%$ ，高估地区占 $2 . 8 8 \%$ ，与组合赋权方法比较，评价一致地区占 $4 0 . 7 8 \%$ ;AHP法较组合赋权低估地区占 $8 . 2 4 \%$ ,高估地区占 $3 7 . 8 6 \%$ ,与组合赋权方法比较，评价一致地区占 $5 3 . 9 0 \%$ 。AHP法与组合赋权法洪水风险分布一致性较高，而熵权法则较组合赋权法低估。

# 2.2历史洪水验证

根据《中国气象灾害大典》《中国气象灾害年鉴》和相关文献8统计历史洪水，将历史洪水分别在熵权法、AHP法和博弈论组合赋权洪水风险图中进行叠置分析，可以得到该地区的洪水风险评价等级；根据相关研究将历史洪水分为5个等级，洪水次数 $> 1 3$ 为高风险， $1 0 <$ 洪水次数 $\leqslant 1 3$ 为较高风险， $8 \leqslant$ 洪水次数 $\leqslant 1 0$ 为中风险， $5 \leqslant$ 洪水次数 $< 8$ 为较低风险，洪水次数 $< 5$ 为低风险。比较后的结果如表2。由于洪水风险评估主要关注中高风险地区，首先对中风险及以上洪水地区进行验证，AHP法在这些地区多为高估，与历史评价一致地区占$2 6 . 3 1 \%$ ;而熵权法有较大低估，特别未能识别出高风险地区，评价一致地区仅占 $2 1 . 0 5 \%$ ;组合赋权方法结果最为准确，但在中风险地区有所高估，与历史一致地区占 $4 2 . 1 1 \%$ 。针对较低和低风险地区，3种方法都存在一定高估，其中熵权法表现最好。因此博弈论组合赋权更能反映武威市洪水风险分布规律，既能准确识别洪水脆弱区，也不高估洪水风险，故下文仅对组合赋权洪水风险图进行分析。

![](images/6bb9b713c08adc1106a0ea5ae865aac268a21e20d5128ebfb33e540369a52fca.jpg)  
图3洪水风险图  
Fig.3Flood risk map

表2历史洪水多发区洪水风险评价  
Tab.2 Flood risk assessment in areas prone to historical floods   

<html><body><table><tr><td>历史洪水</td><td>洪水次数/次</td><td>AHP</td><td>熵权法</td><td>组合赋权</td><td>历史洪水</td><td>洪水次数/次</td><td>AHP</td><td>熵权法</td><td>组合赋权</td></tr><tr><td>打柴沟镇</td><td>17</td><td>较高</td><td>中</td><td>较高</td><td>古丰乡</td><td>8</td><td>较高</td><td>中</td><td>较高</td></tr><tr><td>华藏寺镇</td><td>17</td><td>高</td><td>中</td><td>较高</td><td>钱宝乡</td><td>8</td><td>较高</td><td>较低</td><td>较高</td></tr><tr><td>黄羊川镇</td><td>16</td><td>较高</td><td>中</td><td>较高</td><td>松山镇</td><td>8</td><td>高</td><td>较低</td><td>较高</td></tr><tr><td>安远镇</td><td>15</td><td>较高</td><td>中</td><td>较高</td><td>朱岔乡</td><td>8</td><td>较高</td><td>中</td><td>较高</td></tr><tr><td>干城乡</td><td>13</td><td>较高</td><td>中</td><td>较高</td><td>旦马乡</td><td>7</td><td>高</td><td>中</td><td>较高</td></tr><tr><td>新堡乡</td><td>13</td><td>较高</td><td>中</td><td>较高</td><td>康宁乡</td><td>7</td><td>较高</td><td>较低</td><td>中</td></tr><tr><td>十八里堡</td><td>12</td><td>较高</td><td>中</td><td>较高</td><td>石门镇</td><td>7</td><td>较低</td><td>较低</td><td>较低</td></tr><tr><td>西营镇</td><td>12</td><td>中</td><td>中</td><td>中</td><td>古浪镇</td><td>6</td><td>较高</td><td>中</td><td>较高</td></tr><tr><td>哈溪镇</td><td>11</td><td>高</td><td>中</td><td>较高</td><td>大红沟乡</td><td>5</td><td>较高</td><td>中</td><td>较高</td></tr><tr><td>横梁乡</td><td>11</td><td>较高</td><td>中</td><td>较高</td><td>黄羊镇</td><td>5</td><td>中</td><td>较高</td><td>较高</td></tr><tr><td>天堂镇</td><td>10</td><td>较高</td><td>中</td><td>较高</td><td>金塔乡</td><td>4</td><td>中</td><td>较高</td><td>较高</td></tr><tr><td>东大滩乡</td><td>9</td><td>较高</td><td>较低</td><td>中</td><td>抓喜秀龙</td><td>4</td><td>高</td><td>中</td><td>较高</td></tr><tr><td>炭山岭镇</td><td>9</td><td>较高</td><td>中</td><td>较高</td><td>高坝镇</td><td>3</td><td>较低</td><td>较低</td><td>较低</td></tr><tr><td>西大滩乡</td><td>9</td><td>较高</td><td>较低</td><td>中</td><td>西靖乡</td><td>3</td><td>较低</td><td>低</td><td>较低</td></tr><tr><td>朵什乡</td><td>8</td><td>较高</td><td>较低</td><td>中</td><td colspan="5"></td></tr></table></body></html>

# 2.3洪水风险区划分析

通过研究区洪水风险区划分析，可以确定子区域洪水风险等级和风险来源，由图4可以获得武威市整体及其行政区不同洪水风险等级占比和影响区域洪水风险的主要因素。武威市洪水风险由西南向东北递减，高风险地区集中在凉州区西南部的石羊河上游、西营河、五坝河、黄羊河和沙沟河和天祝藏族自治区西南部的干沙河、毛藏河。凉州区高风险区占总面积 $1 4 . 5 3 \%$ ，导致地区洪水风险较高的主要原因是承灾体脆弱性较高，凉州区西南部地处祁连山脉北麓，河网密集，降雨集中，人口密度大，经济发达，发生洪水会造成严重损失。而天祝藏族自治县较高的洪水风险来源于致灾因子危险性，天祝藏族自治县西南部受到祁连山脉影响，降雨频繁，易产生较大暴雨。低风险地区主要集中在民勤县东部沙漠区，占总面积的 $5 6 . 2 8 \%$ ，主要原因是民勤县位于腾格里和巴丹吉林两大沙漠相交处，造成该地独特的沙漠气候，历史降雨稀少，蒸发强烈，储水能力差，石羊河在此内流进入沙漠，整体河网稀

![](images/d77e1a280bccfd28a9c1bd9f77c6c533fe2dabc2f0ce10caf24601942339baad.jpg)  
图4洪水风险区划分析  
Fig.4 Flood risk zoning analysis

疏,人口密度较小。

# 3结论

对武威市洪水风险进行评估，根据研究获得的武威市洪水风险图与实测历史洪水资料，以及研究区洪水风险相关研究的洪水风险图进行比较，结果显示该研究对于武威市洪水风险区划判断比较准确。得到以下结论：

（1）采用主客观权重相结合的博弈论组合赋权方法，可以减少单一方面的局限性，提高洪水风险图的精度。

(2）武威市整体洪水风险等级为较低风险。洪水风险呈现由西南向东北递减的分布特征，高风险集中分布于凉州区与古浪县交界处以及天祝藏族自治区西南部，低风险地区主要分布在民勤县内的沙漠区。高风险地区只占 $4 . 9 4 \%$ ，较低风险和低风险地区面积占 $4 3 . 8 4 \%$ ○

（3）武威市各县区洪水风险的主要来源各不相同。致灾因子危险性呈现由西南向东北递减的带状分布特点，高危险区主要分布在天祝县祁连山脉地区，低危险区集中在东北部的石羊河下游。孕灾环境稳定性分布较为均匀，除祁连山区稳定性较高，中部河西平原区及东部沙漠区稳定性相近。承灾体脆弱性地区差异性明显，凉州区与古浪县交界处脆弱性远高于其他地区。

# 参考文献(References):

[1] Lian JJ,Xu H S,Xu K,et al. Optimal management of the flooding risk caused by the joint occurrence of extreme rainfall and high tide level in a coastal city[J]. Natural Hazards,2O17,89(1): 183- 200.   
[2] Hirabayashi Y,Mahendran R,Koirala S,etal.Global flood risk under climate change[J].Nature Climate Change,2O13,3(9): 816- 821.   
[3] Straatsma MW,Kleinhans M G.Flood hazard reduction from automatically applied landscaping measures in river scape,a python package coupled to a two-dimensional flow model[J]. Environmental Modelling and Software,2018,101:102-116.   
[4] Liu Y,Lu X Y,Yao Y Z,et al.Mapping the risk zoning of storm flood disaster based on heterogeneous data and a machine learning algorithm in Xinjiang,China[J]. Journal of Flood Risk Management, 2020,14(1): 1-14.   
[5]张俊兰,罗继,王荣梅.近20 a新疆升温融雪(冰)型洪水频次时 空变化及大气环流型分析[J].干旱区研究,2021,38(2):339- 350.[Zhang Junlan,Luo Ji, Wang Rongmei. Combined analysis of the spatiotemporal variations in snowmelt (ice) flood frequency in Xinjiang over 2O years and atmospheric circulation pattrns[J]. Arid Zone Research,2021,38(2): 339-350.]   
[6]Xu H S,Ma C,Lian JJ,et al.Urban flooding risk assessment based on an integrated k-means cluster algorithm and improved entropy weight method in the region of Haikou, China[J]. Journal of Hydrology,2018,563: 975-986.   
[7]周刚,崔曼仪,李哲,等.新疆春季融雪洪水危险性动态评价研 究[J].干旱区研究,2021,38(4): 950-960.[Zhou Gang,Cui Manyi, Li Zhe,et al. Dynamic evaluation of the risk of the spring snowmelt flood in Xinjiang[J].Arid Zone Research,2021,38(4): 950- 960.]   
[8]Chen X L, Zhang H, Chen W J,et al. Urbanization and climate change impacts on future flood risk in the Pearl River Delta under shared socioeconomicpathways[J].Sienceof the Total Environment, 2021, 762: 1-14.   
[9]QuirosE,Gagnon A S.Validationofflodrisk maps usingopen source optical and radar satelite imagery[J]. Transactions in GIS, 2020,24(5): 1208-1226.   
[10] 叶爱民,刘曙光,韩超,等.MIKEFLOOD耦合模型在杭嘉湖流 域嘉兴地区洪水风险图编制工作中的应用[J].中国防汛抗旱, 2016,26(2): 56-60.[Ye Aimin,Liu Shuguang,Han Chao,et al. Application of MIKEFLOOD coupling model in flood risk mappingat Jiaxing area of Zhejiang Province[J]. China Flood& Drought Management,2016,26(2): 56-60.]   
[11]孙煜航,程舒鹏,张祺,等.黄河下游花园口至艾山河段滩区洪 水漫滩风险度评估研究[J].北京大学学报(自然科学版),2021, 57(3):575-586.[Sun Yuhang, Cheng Shupeng, Zhang Qi,et al. Research on flood risk assessment of floodplains from Huayuankou to Aishan section in the lower Yellow River[J].Acta ScientiarumNaturalium Universitatis Pekinensis,2O21,57(3):575- 586.]   
[12] 黄崇福,郭君,艾福利,等.洪涝灾害风险分析的基本范式及其 应用[J].自然灾害学报,2013,2(4):11-23.[Huang Chongfu, Guo Jun,Ai Fuli,etal.Basic paradigm of risk analysis in flood disaster and its application[J]. Journal of Natural Disasters,2O13,22 (4): 11-23.]   
[13] 王兆礼,赖成光,陈晓宏.基于熵权的洪灾风险空间模糊综合评 价模型[J].水力发电学报,2012,31(5):35-40.[Wang Zhaoli,Lai Chengguang,Chen Xiaohong. Spatially fuzzy comprehensive as sessment model forflood hazardrisk based on entropyweight[J]. Journal of Hydroelectric Engineering,2012,31(5): 35-40.]   
[14]李春华,叶春,赵晓峰,等.太湖湖滨带生态系统健康评价[J].生 态学报,2012,32(12):3806-3815.[Li Chunhua,Ye Chun, Zhao Xiaofeng,et al. The ecosystem health assessment of the littoral zone of Lake Taihu[J].Acta Ecologica Sinica,2012,32(12): 3806- 3815.]   
[15] 陈加良.基于博弈论的组合赋权评价方法研究[J].福建电脑, 2003(9):15-16.[Chen Jialiang.Research on evaluation method of combination weighting based on game theory[J]. Journal of Fujian Computer,2003(9): 15-16.]   
[16] 裴惠娟,陈晋,李雯,等.甘肃省暴雨洪水时空分布及风险评估 [JJ.自然灾害学报,2017,26(3):167-175.[Pei Huijuan,Chen Jin, Li Wen, et al. Spatiotemporal pattern and risk assessment of storm flood in Gansu Province[J]. Journal of Natural Disasters,2O17,26 (3): 167-175.]   
[17] 徐凯莉,吕海深,刘名文,等.数值模拟方法在河流冰塞水位模 拟中的应用——以黄河三湖河口弯道段为例[J].干旱区研究, 2021,38(6): 1556-1562.[Xu Kaili, Lyu Haishen,Liu Minwen, et al. Numerical simulation of the ice jam stage in the Sanhuhekou bend reach of the Yellow River[J].Arid Zone Research,2O21,38(6): 1556-1562.]   
[18] 王荣喆,李玲萍,李文莉.基于GIS技术的武威市山洪灾害风险 区划初探[J].干旱气象,2013,31(3):602-608.[Wang Rongzhe,Li Lingping,Li Wenli.Risk division of flood disaster in Wuwei based on GIS[J]. Journal of Arid Meteorology,2013,31(3): 602-608.]   
[19] 陈庭兴,吕海深,朱永华.基于GEV分布的西营河流域洪水特 性分析[J].干旱区研究,2021,38(6):1563-1569.[Chen Tingxing, Lyu Haishen,Zhu Yonghua.Analysis of flood characteristics in Xiying River Basin based on GEV distribution[J].Arid Zone Research,2021,38(6): 1563-1569.]   
[20] 史培军.三论灾害研究的理论与实践[J].自然灾害学报,2002, 11(3):1-9.[Shi Peijun.Theory on disaster science and disaster dynamics [J]. Journal of Natural Disasters,20O2,11(3): 1-9.]   
[21] 张红萍.山区小流域洪水风险评估与预警技术研究[D].北京: 中国水利水电科学研究院,2013.[Zhang Hongping.Study on the Flood Risk Management and Technology of the Small Mountain Watershed[D].Beijing:China Institute of Water Resources & Hydropower Research(IWHR),2013.]   
[22] 孟宪萌,胡和平.基于熵权的集对分析模型在水质综合评价中 的应用[J].水利学报,2009,40(3):257-262.[Meng Xianmeng, Hu Heping.Application of set pair analysis model based on entropy weight to comprehensive evaluation of water quality[J]. Journal of Hydraulic Engineering,2009,40(3): 257-262.]   
[23] 路遥,徐林荣,陈舒阳,等.基于博弈论组合赋权的泥石流危险 度评价[J].灾害学,2014,29(1):194-200.[Lu Yao,Xu Linrong, Chen Shuyang,et al. Combined weight method based on game theory for debris flow hazard risk assessment[J]. Journal of Catastrophology,2014,29(1): 194-200.]   
[24] 甘蓉,宣昊,刘国东,等.基于博弈论综合权重的物元可拓模型 在地下水质量评价中的应用[J].水电能源科学,2015,33(1): 39-42.[Gan Rong, Xuan Hao,Liu Guodong,et al.Application of weighted matter-element extension based game theory in groundwater quality evaluation[J].Water Resources and Power, 2O15,33 (1): 39-42.]

# Combined weight method based on game theory for flood risk assessment in the Wuwei Region

SU Guangquan¹²， LYU Haishen1²， ZHU Yonghuat2, CHEN Tingxing1²， HUA Jiacheng1,2   
(1.State Key Laboratory of Hydrology-Water Resources and Hydraulic Engineering,Hohai University,   
Nanjing 21Oo98,Jiangsu,China; 2. College of Hydrology and Water Resources,Hohai University, Nanjing 210098, Jiangsu, China)

Abstract: Floods are the most frequent natural disasters in the world,and the Chinese region has shown the most significant increase in flood risk worldwide.Based on the frequency of flash floods in Wuwei City,Gansu Province,a flood risk assessment method combined with subjective and objective weights and based on game theory was adopted and GIS technology was applied.Seven indicators were selected to construct a flood risk assessment index system from three aspects: disaster dangers,disaster environment sensitivity,and suffering flexibility.Then,the risk zoning chart offlood disaster in Wuwei was drawn,which showed that the overallflood risk level of Wuwei City is low and flood risk shows a decreasing distribution characteristic from southwest to northeast.The results are in good agreement with historic flood event data in whichthe highest risk area accounts only for $4 . 9 4 \%$ of the total area, which is concentrated at the junction of Liangzhou District and Gulang County and southwest of Tianzhu County.The sum of the lowest risk area and the lower risk area accounts for $43 . 8 4 \%$ of the total area,which is concentrated in the easter desert area of Minqin County.The main sources offlood risk varyamong counties in Wuwei City.The risk of disaster-causing factors presents abelt-like distribution characteristic that decreases from southwest to northeast.The highest risk areas are distributed mainly in the Qilian Mountains of Tianzhu County,and the lowest risk areas are concentrated in lower reaches of the Shiyang River in the northeast.The distribution of the disaster environment sensitivity is relatively uniform except for the Qilian Mountains with higher stability.There are obvious differences in the vulnerability of disaster-bearing bodies,and the vulnerability at the junction of Liangzhou Countyand Gulang County is much higher than that of other regions.The entropy method and analytic hierarchy process are used for comparison with the game theory combination weighting method, which demonstrates that the combination weighting method of game theory can reduce the subjectivity of the single weighting method, improve the accuracy of the flood risk map,and provide valuable information for flood management.

Keywords: flood disaster;risk zoning;analytic hierarchy process；game theory； entropy method; Wuwei Region