# 基于AHP和混合Apriori-Genetic算法的交通事故成因分析模型

邓晓衡，曾德天

(中南大学 信息科学与工程学院，长沙 410075)

摘要：针对交通事故数据多维多层的特点，对交通事故的主要成因与潜在规律进行了研究。从驾驶员、车辆、时间一地点、环境四个维度出发，提出了基于层次分析法（AHP）和混合Apriori-Genetic 的模型挖掘事故成因。首先，引入AHP对事故诱发因素进行重要度排序，在客观分析的基础上将事故因素量化，筛选出引发交通事故的主要因素；其次，结合混合的Apriori和遗传算法对主要因素进行定向分析，找出关联规则，提高挖掘的准确性。相关对比实验的结果表明该模型可以减少无用规则的产生并提高挖掘的准确性，具有一定的科学意义和应用价值。

关键词：交通事故；层次分析法；Apriori；遗传算法；成因分析 中图分类号：TP391 doi: 10.3969/j.issn.1001-3695.2017.12.0818

# Traffic accident causation analysis model based on AHP and hybrid Apriori-Gentic algorithm

Deng Xiaoheng, Zeng Detian (School of Information Science&Engineering,Central South University,Changsha 410o75,China)

Abstract: In viewofthecharacteristicofmulti-dimensionaland multi-ayer in traficacidentdata,this paperproposedanew modeltoesearch themainreasonsand potentialrules in trafficaccidents.Themodelstarts fromthe four main dimensionssuch as thedrivers,the vehicles,thetime-addressandtheenvironment,andusesawaywhich basedonAHPand hybrid AprioriGentic algorithmtominecausesofaccident.Firstofall,theAHPsortedtheimportanceoftheinfluencingfactorsaboutaccident. Thenonthe basis ofobjective analysis,the model quantifiedthe influencing factors and selected the main influencing factors. Finally the modelcombined the genetic algorithm with the Apriori todirectionalanalyze the main influencing factorsand find the association rules out.Theexperimental result shows that the model could reduces the generation of useless rulesand improves the accuracy of mining, which has certain scientific significance and application value.

Key Words: traffic accident; AHP(analytic hierarchy process）; Apriori; genetic algorithm; causational analysis

# 0 引言

近年来，随着中国的汽车和驾驶人员数量高速增长，道路交通压力大增，交通事故有愈演愈烈的趋势[1]。同时中国是世界上交通事故死亡人数最多的国家之一，中国公安部官方最新的数据显示2015年全国交通事故发生总计187781起[2.3]。伴随着交通事故的产生，事故历史数据也逐步积累。为了探究交通事故的形成原因，利用数据挖掘技术对历史事故数据进行挖掘，希望能够找出数据中潜在的深层规则和数据模式，从而为交通事故的预防提供决策支持。由于在交通事故数据中诱发交通事故的因素众多，加上事故数据集中数据字段纷繁复杂且冗余信息很多，导致成因分析难以进行。为此本模型引入了层次分析法进行数据预处理。

层次分析法(AHP)[8]是运筹学家萨蒂提出的应用网络系统理论和多目标综合评价方法。它是一种将定性与定量相结合的系统分析方法，该方法将一个复杂问题分割成若干层，每层又包含若干因素，通过对事物的复杂本质和相关影响因素的深入分析后，绘制清晰的层次结构图，然后逐个的将各因素建立判断矩阵，通过计算判断矩阵的特征值和特征向量，得到不同因素的权重，根据权重值的大小评价结果，选出最佳的方案。

与此同时，为了提升挖掘的准确性，模型针对交通事故数据集将Apriori与遗传算法结合使用。Apriori 算法为布尔关联规则挖掘频繁项集算法[9]。它使用一种称作逐层搜索的迭代方法，k项集用于探索 $\mathbf { k } { + } \mathbf { l }$ 项集，直到不可能找到更大的频繁项集。通过频繁项集得出 $\mathrm { A } { = } { > } \mathrm { B }$ 形式的关联规则，对于每一条规则主要有支持度和置信度两个参数进行衡量。

遗传算法通过模拟达尔文自然进化的思想来搜索全局最优解，它的初始种群是由随机产生的规则组成[10]。对每条染色体（规则）进行编码，由用户给出进化过程中的适应度函数，根据适者生存的原则，逐代优化，形成由当前群体中最适合的规则以及这些规则的后代组成的新群体。后代通过使用诸如交叉和变异等遗传操作来创建。

本文对城市交通事故成因分析展开研究，以贵阳市2015年全年交通事故历史数据[4为分析依据，结合层次分析法和混合的Apriori-Genetic 算法对数据进行建模分析，首先以AHP算法确定影响因素权重，选择主影响因子，剔除次要因素，简化运算；同时采用关联规则对主因素字段进行关联，通过遗传算法优化搜索结果。从而探究主因素背后的综合作用规律与交通安全的详细情况，如道路情况及其他交通环境对事故发生的影响，提高数据的利用价值。

# 1 相关工作

随着交通事故数据的大量积累，如何对数据建模研究并从中快速抽取出有用的信息成为了研究的重点工作。关联规则算法可以产生大量的关联规则，对于探究交通事故成因具有较好的适应性[5\~7]。关联规则是使用支持度来寻找频繁项集，根据置信度发现关联规则，但在交通事故数据中由于字段过多，如果直接使用关联规则算法会产生大量无用且重复的频繁项与关联规则。

为了准确地找出交通事故的成因，需要对关联规则算法进行改进与优化，使其可以更好的应用到交通事故研究中来。遗传算法的搜索根据适应度函数进行，具有很强的方向性和目的性，可以弥补Apriori 漫无目的搜寻的缺陷。Ghosh 等人[11]提出了基于遗传算法的频繁模式挖掘，他们将遗传算法引入到购物篮数据挖掘中，改良了挖掘的过程，在全局搜索的同时减少了时间复杂度，这一方法简单高效，同时在更大的数据集方面有更好的表现性。Chadokar等人[12]提出了用于网络通信的混合关联规则与遗传算法，他们利用Apriori 算法处理网络通信数据，得到频繁项集，之后再将频繁项集通过遗传算法得到更少更优的规则，实验通过对比单个apriori算法和混合算法的时间复杂度和产生的频繁项以及规则数量表明混合算法可以减少计算所花费的时间，并在产生的规则数量上更少，但规则质量更高。只是以上混合算法均针对特定场景设计，不具有普适性，如果要应用到交通事故成因分析中来，需要重新设计。

Jain 等人[13]提出了优化的关联规则挖掘算法，他们提出了正向的关联规则[14,15]挖掘和负向的关联规则[16,17]挖掘，对于每条规则引入了相关系数的概念，使用遗传算法来挖掘有效的正向关联规则与负向关联规则。这一方法可以减少搜索的空间同时通过每条关联规则所带的相关系数来判断此关联规则是否合适进一步的挖掘，但此模型在时间复杂度上效果并不理想。

# 2 模型设计

# 2.1数据描述

本数据由贵阳市政府在 2016 年贵阳市交通大数据竞赛[4]中提供。原始的交通事故历史数据以excel文本的形式提供，共56651条，含二十多个字段。事故成因种类分为9种，具体的分类见表8。通过引入2015年贵阳市天气环境数据，形成了最终的数据集。由于数据中字段较多，无法直接开展关联规则分析。

# 2.2 层次分析法

层次分析法将定性定量相结合，迅速准确的找到问题的关键，并且能对各层次影响因素权重排序。故将其引入到本次成因分析的模型中来。

![](images/d5047f2449e2a2d33eb8b29a5398932a3c97cf0089b1e357b2f46dbcb7107d37.jpg)  
图1事故数据集中的系统层次结构

在交通事故数据集中，数据字段被大体分属为驾驶员类、车辆类、时间-地点类、环境类四个不同的维度，如图1中系统层次结构图所示。在与贵阳市通管理局及交通领域相关专家学者共同交流分析后，结合专家知识，参照ahp的9分位比率，构造了上下层次的判断矩阵，并进行矩阵一致性的检验；构造上下层次的判断矩阵见表1\~5。

表1目标(goal)层与中间(middle)层的判断矩阵G-C表  

<html><body><table><tr><td>G</td><td>C1</td><td>C2</td><td>C3</td><td>C4</td></tr><tr><td>C1</td><td>1</td><td>5</td><td>3</td><td>2</td></tr><tr><td>C2</td><td>1/5</td><td>1</td><td>1/2</td><td>1/4</td></tr><tr><td>C3</td><td>1/3</td><td>2</td><td>1</td><td>1/2</td></tr><tr><td>C4</td><td>1/2</td><td>4</td><td>2</td><td>1</td></tr></table></body></html>

表2中间(middle)层与方案(scheme)层的判断矩阵C1-S   

<html><body><table><tr><td>C1</td><td>S1</td><td>S2</td><td>S3</td><td>S4</td></tr><tr><td>S1</td><td>1</td><td>5</td><td>3</td><td>2</td></tr><tr><td>S2</td><td>1/5</td><td>1</td><td>1/3</td><td>1/2</td></tr><tr><td>S3</td><td>1/3</td><td>3</td><td>1</td><td>2</td></tr><tr><td>S4</td><td>1/2</td><td>2</td><td>1/2</td><td>1</td></tr></table></body></html>

表3中间层(middle)与方案(scheme)层的判断矩阵C2-S   

<html><body><table><tr><td>C2</td><td>S5</td><td>S6</td><td>S7</td><td>S8</td></tr><tr><td>S5</td><td>1</td><td>1</td><td>1/2</td><td>1/3</td></tr><tr><td>S6</td><td>1</td><td>1</td><td>1/3</td><td>1/3</td></tr><tr><td>S7</td><td>2</td><td>3</td><td>1</td><td>1/2</td></tr><tr><td>S8</td><td>3</td><td>3</td><td>2</td><td>1</td></tr></table></body></html>

表4中间(middle)层与方案(scheme)层的判断矩阵C3-S   

<html><body><table><tr><td>C3</td><td>S9</td><td>S10</td><td>S11</td><td>S12</td></tr><tr><td>S9</td><td>1</td><td>3</td><td>2</td><td>4</td></tr><tr><td>S10</td><td>1/3</td><td>1</td><td>1/2</td><td>2</td></tr><tr><td>S11</td><td>1/2</td><td>2</td><td>1</td><td>3</td></tr><tr><td>S12</td><td>1/4</td><td>1/2</td><td>1/3</td><td>1</td></tr></table></body></html>

表5中间(middle)层与方案(scheme)层的判断矩阵C4-S   

<html><body><table><tr><td>C4</td><td>S13</td><td>S14</td><td>S15</td></tr><tr><td>S13</td><td>1</td><td>5</td><td>3</td></tr><tr><td>S14</td><td>1/5</td><td>1</td><td>1/3</td></tr><tr><td>S15</td><td>1/3</td><td>3</td><td>1</td></tr></table></body></html>

之后判断上述矩阵能否通过一致性检验，计算矩阵的最大特征值（如下所示）和其对应的特征向量，以及相应的一致性指标CI和检验系数CR值。

$$
\lambda _ { \mathrm { m a x 1 } } = 4 . 0 2 1 1 \quad \lambda _ { \mathrm { m a x 2 } } = 4 . 1 0 7 4 \quad \lambda _ { \mathrm { m a x 3 } } = 4 . 0 4 5 8
$$

$$
\lambda _ { \operatorname* { m a x } 4 } = 4 . 0 3 1 0 \lambda _ { \operatorname* { m a x } 5 } = 3 . 0 3 8 5
$$

CI代表矩阵的一致性，CI越大，说明一致性越差；考虑到一致性的偏离可能是由于随机原因造成的，因此在检验判断矩阵是否具有满意的一致性时，还需将CI和平均随机一致性指标RI进行比较，得出最终检验系数CR。计算公式分别如下所示：

$$
C I = \frac { \lambda _ { \operatorname* { m a x } } - n } { n - 1 }
$$

$$
C R = \frac { C I } { R I }
$$

平均随机一致性指标RI的值可以通过查平均随机一致性指标标准值表得到，它只和矩阵的阶数相关。当矩阵的阶数 $\scriptstyle \mathrm { n = 3 }$ 时，RI取0.58；当矩阵的阶数 $\scriptstyle { \mathrm { n = 4 } }$ 时，RI取0.90。对于每个矩阵，如果最终计算出来的CR值远小于0.1，则说明矩阵的一致性检验通过，可以进行下一步的工作，否则重新分析构造矩阵。

表6列出了部分的计算结果及中间值， $\omega _ { \boldsymbol { k } }$ 代表相应矩阵最大特征值对应的特征向量。最终可以得出方案层中每个属性相对于目标层的权重值，选取权重大于某一阈值的字段作为影响交通事故的主要因素，现经过经验测试选取合适的阈值为0.044。

表6部分计算的结果及中间值  

<html><body><table><tr><td></td><td>G-C</td><td>C1-S</td><td>C2-S</td><td>C3-S</td></tr><tr><td>@k1</td><td>0.4773</td><td>0.4909</td><td>0.1377</td><td>0.4673</td></tr><tr><td>@k2</td><td>0.0809</td><td>0.0863</td><td>0.1258</td><td>0.1601</td></tr><tr><td>Qk3</td><td>0.1539</td><td>0.2483</td><td>0.2879</td><td>0.2772</td></tr><tr><td>@k4</td><td>0.2880</td><td>0.1745</td><td>0.4486</td><td>0.0954</td></tr><tr><td>晨max</td><td>4.0211</td><td>4.1074</td><td>4.0458</td><td>4.0310</td></tr><tr><td>CI</td><td>0.007</td><td>0.0358</td><td>0.0153</td><td>0.0103</td></tr><tr><td>CR</td><td>0.0078</td><td>0.039</td><td>0.017</td><td>0.0011</td></tr></table></body></html>

通过层次分析法对照表7中的数据可以发现准则层中的Driver相对目标层TrafficAccident所占权重为0.4773，而方案层中 Driver age 相对 Driver 所占权重为 0.4909，故 Driver age字段相对于TrafficAccident所占的权重为$0 . 4 7 7 3 ^ { * } 0 . 4 9 0 9 { = } 0 . 2 3 4 3$ ；同理将方案层中每个字段相对于目标层TrafficAccident所占权重依次计算，选取最终权重大于阈值的字段做为主要事故影响因素。

表7各字段属性相对目标层的权重值排列  

<html><body><table><tr><td>criterion layer</td><td>Weight</td><td>scheme layer</td><td>Weight</td></tr><tr><td rowspan="3">Driver</td><td rowspan="3">0.4773</td><td>Driving years</td><td>0.4909</td></tr><tr><td>Driving gender</td><td>0.0863</td></tr><tr><td>Driver age</td><td>0.2483</td></tr><tr><td rowspan="5">Vehicle</td><td></td><td>Way of training</td><td>0.1745</td></tr><tr><td></td><td>Car brand 1</td><td>0.1377</td></tr><tr><td>0.0809</td><td>Car brand 2</td><td>0.1258</td></tr><tr><td></td><td>Car color 1</td><td>0.2879</td></tr><tr><td></td><td>Car color 2</td><td>0.4486</td></tr><tr><td></td><td></td><td>The day</td><td>0.2772</td></tr><tr><td>Time- Address</td><td>0.1539</td><td>The month</td><td>0.1601</td></tr><tr><td></td><td></td><td>The time</td><td>0.4673</td></tr><tr><td rowspan="5">Environment</td><td rowspan="5">0.2880</td><td>The address</td><td>0.0954</td></tr><tr><td>Weather condition</td><td>0.6369</td></tr><tr><td>Temperature</td><td>0.1047</td></tr><tr><td></td><td></td></tr><tr><td>Wind condition</td><td>0.2583</td></tr></table></body></html>

# 2.3混合的 Apriori-Genetic 算法

结合遗传算法的优点，本文设计了一种针对交通事故成因分析的混合遗传关联规则挖掘算法，采用Apriori来发现输入数据中的频繁项集。通过将频繁项按某种形式进行编码转换为染色体，将这批染色体作为遗传算法的初始种群，再根据预定义的适应度函数对每条染色体计算其适应值，通过选择适应值高的一批染色体进行复制，通过遗传操作（选择，交叉，变异）

产生新的一代群体。通过不断的繁殖进化，最后收敛到一批具有较高适应度的个体上或者迭代的次数达到了预设定的阈值，即输出最优分类规则集。混合算法的流程图如图2所示。

![](images/f254a94715b80eb345aa025df42ff8c73db35141000c370556cef74aef5e276a.jpg)  
图2混合算法的总体流程图

# 2.3.1编码设计

对于交通事故数据集，将影响交通事故的因素作为规则前件部分，将交通事故原因类型作为规则后件。期望能够找到“驾龄、年龄、培训驾校、时间等字段 $\Rightarrow$ 事故原因类型”这一形式的规则，规则的前件中每一个特征属性（如驾龄）有 $\mathfrak { n }$ 个分类，则使用相应x位二进制进行表示，其中 $\mathbf { x }$ 与 $\mathfrak { n }$ 满足关系：

$$
\operatorname* { m i n } \{ x \mid 2 ^ { x } > n \}
$$

规则的后件“事故原因类型”作为分类属性，代表造成事故的原因，事故原因共有9种（见表8)，用二进制表示的方法同规则前件中的特征属性。表9描述了数据中驾龄字段的分类。

表8事故原因类型分类与对照表  

<html><body><table><tr><td>Label</td><td>Mean</td></tr><tr><td>1</td><td>追尾的</td></tr><tr><td>2</td><td>逆行的</td></tr><tr><td>3</td><td>倒车的</td></tr><tr><td>4</td><td>停车时未挂低速档、未拉驻车制动，导致车辆滑行的</td></tr><tr><td>5</td><td>开关车门的</td></tr><tr><td>6</td><td>违反交通信号的</td></tr><tr><td>7</td><td>未按规定让行的</td></tr><tr><td>8</td><td>依法应负全责的其他情形</td></tr><tr><td>9</td><td>不符合前8款规定或者双方同时具有上述情形的</td></tr></table></body></html>

通过Apriori算法得出事故频繁项集，挑选其中同时含有特征属性与分类属性的项集，作为初始的规则进行编码。例如频繁项：[培训方式 $\ c = ^ { \prime }$ 驾校培训，驾龄 $\scriptstyle = ^ { \prime }$ 驾龄1，事故原因类型$\scriptstyle = ^ { \prime } 1 ^ { \prime } ]$ ，其中培训方式有’驾校培训’与’自培’两类，则式（5)中 $\scriptstyle \mathtt { n } = 2$ ， $\mathbf { x }$ 最小取2；可设'驾校培训对应编码为’01'，’自培'对应’10'，若此属性未出现在此频繁项中则对应的二进制为${ \mathrm { \Delta } } ^ { \cdot } { 0 0 } ^ { \cdot }$ ，其他字段的编码设计同理。在程序中构造了一个列表用于存放规则所对应的二进制染色体。列表的长度为23，对应AHP方法筛选出的7个特征属性和1个分类属性，每个属性字段所对应的编码按固定顺序依次存于列表当中。

表9驾龄字段的分类与对照表  

<html><body><table><tr><td>Label</td><td>Mean</td></tr><tr><td>驾龄1</td><td>0-4 years</td></tr><tr><td>驾龄2</td><td>5-11 years</td></tr><tr><td>驾龄3</td><td>12-19 years</td></tr><tr><td>驾龄4</td><td>20 years and more</td></tr></table></body></html>

# 2.3.2定义适应度函数

适应度函数是用来评价个体适应环境的能力，是进行自然选择的依据。对于期望的规则可以使用支持度，置信度，覆盖度等多种指标进行评价。在适应度函数设计中，基于综合考虑，令适应度函数

$$
F \left( r \right) = a ^ { \ast } S \left( r \right) + b ^ { \ast } C \left( r \right) + c ^ { \ast } C R \left( r \right)
$$

其中：变量 $\mathrm { ~ \bf ~ r ~ }$ 代表规则，a，b，c均为常量系数并且 $\mathbf { a }$ ，b，c的取值范围为[0,1]。令 $\mathrm { ~ N ~ }$ 为整个数据集的记录数，C为规则中除去‘事故原因类型’属性后的其他字段，C在 $\mathrm { ~  ~ N ~ }$ 中出现的频数用 $R _ { c }$ 表示； $\mathrm { ~ D ~ }$ 表示‘事故原因类型’字段， $\mathrm { ~ D ~ }$ 在 $\mathrm { ~  ~ N ~ }$ 中出现的频数用 $R _ { D }$ 表示；C,D同时出现在数据集中的频数计为 $R _ { c } \cup R _ { D }$ ，S(r)为规则的支持度，则S(r)的定义为

$$
S ( r ) = \frac { R _ { c } \cup R _ { D } } { N }
$$

C(r)为规则的置信度，C(r)的定义为

$$
C ( r ) = \frac { R _ { c } \cup R _ { b } } { R _ { c } }
$$

同理规则的覆盖度CR(r)定义为

$$
C R ( r ) = { \frac { R _ { c } \cup R _ { b } } { R _ { b } } }
$$

常量系数a，b，c是本模型的关键所在，可由用户根据需要进行调整，从而对规则评价的偏重可以发生相应的改变，使得进化沿用户期望的方向进行，提高挖掘的准确性。

# 2.3.3遗传算子设计

1)选择算子

选择操作使用轮盘赌操作，其具体过程描述如下所示：对于 Apriori算法选出的初始种群中的每个染色体，计算其适应度值，将所有的适应度值刻画到一个圆盘上，即适应度值的大小表示在圆盘上的面积。在转动轮盘的过程中，单个染色体的面积越大，则被选中的概率越大。

2)交叉算子

从ICGA和GP会议的历年相关文献来看，交叉概率的选取并无固定的方法与逻辑，一般取0.4\~0.99；但交叉概率取值过大，则不利于种群中优秀基因的保存，取值过小就会导致种群进化缓慢。在本次交通事故数据处理中经反复测试，交叉概率为0.6时，对于进化速度和实验结果能有一个较好的表现。

故设置交叉概率为0.6，为了在不破坏种群的基因多样性的前提下加快种群的进化速度，使用选择算子选择出父本和母本后，按单点交叉随机产生交叉位，形成两个新的个体，考虑到在挖掘中为了找到更优的规则，将新产生的个体按适应度排序，再从中挑选出大于适应度阈值的个体加入到解中；同时也将这些挑选出的个体加入到原先的种群，从而丰富种群。这样既保存了父本和母本的基因，又在进化的过程中保持了种群的多样性。

3)变异算子

在遗传算法中使用可变的变异概率，设P为变异概率。具体描述如下：

if(个体的适应度 $>$ 群体的平均适应度)

then {P 取一个相对较小的值或接近0;}else {P值取一个相对较大的值;}

# 3 实验结果

# 3.1实验设计

采用保留“事故原因类型"属性类别比例的分层采样，随机采样选取数据集中 $70 \%$ 的数据作为测试集，用来寻找关联规则；$30 \%$ 为验证集，验证生成的关联规则在验证集上的置信度。层次分析法最终选取出了驾龄、性别、年龄、培训驾校、时间、天气状况、风力风向共7个字段作为事故成因分析的主要影响因素，和事故原因类型字段一起作为混合的Apriori和遗传算法的输入。分别使用单独的Apriori 算法，单独的遗传算法以及混合的Apriori-Genetic 算法对事故历史数据进行处理，比较数据挖掘结果并进行性能测试。同时在找到的期望规则数量上，将混合算法与C4.5及随机森林等其他的机器学习算法进行比较，以验证其性能。实验环境为intelCorei5-4200H处理器，8GB内存，Windows7操作系统，python 语言。

# 3.2混合算法的挖掘结果

为便于比较，令适应度函数F(r)（参见式（4)）中常系数$\scriptstyle \mathbf { a } = \mathbf { b } = \mathbf { c } = 1$ 。对于预处理后的数据集实施混合的Apriori-Genetic算法，支持度阈值设为0.1，在表10中列出了使用本文提出的模型找到的部分适应度较高的期望规则，规则后面分别附有相应的适应度，支持度，置信度，和覆盖度。

第一条规则男性，8-12点 $\therefore \Rightarrow 1$ 事故类型1的适应度为1.72，其支持度为0.28，置信度为0.71，覆盖度为0.73，从规则中可以看出驾驶员为男性&时间为上午8-12点的组合中，经常会出现事故原因为追尾的事故，且规则具有较高的覆盖度。规则'0-4年驾龄，女性 $\prime = > \prime$ 事故类型4'的适应度为1.71，它显示了女性驾驶员在驾龄偏低的情况下，易发生类型4的事故，这也显示了年轻女性司机在技术上还需多加练习。规则'自培'，'雨天 $\mathrel { \mathop : } = \textgreater$ =事故类型7显示，对于驾驶员为自培形式的在雨天容易发生未按规定让行的事故，说明未经驾校培训的驾驶员在交通规则的学习上需要加强。而当驾驶员为驾校培训&18-25岁的男性时，出现事故原因为未按规定让行的事故概率亦较高。推测可能是年轻人驾驶技术不娴熟导致。通过详细分析得出的交通事故规则结果集，可以找出有意义的组合规则，对于交通事故的针对性预防和科学的管理具有重要的意义。

当用户对规则评价的偏重发生了改变，如更加关注置信度时，则可以使置信度的系数b相对a和c而言较大，最终得出的期望规则集会在置信度上有更好的表现。此处以$\mathsf { a } { = } 1 { > } \mathsf { b } { = } \mathsf { c } { = } 0 . 5$ ； ${ \sf b } { = } 1 { > } { \tt a } { = } { \tt c } { = } 0 . 5$ 以及 $\mathsf { c } { = } 1 { > } \mathsf { a } { = } \mathsf { b } { = } 0 . 5$ 进行三组不同偏重下的规则挖掘实验，得出的适应度最高的期望规则集分别如表11\~13 所示。

表10 $\scriptstyle \mathtt { a } = \mathtt { b } = \mathtt { c } = 1$ 条件下挖掘规则结果表  

<html><body><table><tr><td>规则</td><td>适应度 支持度</td><td>置信度</td><td>覆盖度</td></tr><tr><td>'male','time2'=>'1'</td><td>1.72</td><td>0.28</td><td>0.71 0.73</td></tr><tr><td>'Driving experience 1','female'=>'4'</td><td>1.71</td><td>0.32</td><td>0.88 0.51</td></tr><tr><td>'school training'=>'1'</td><td>1.66</td><td>0.37</td><td>0.79 0.54</td></tr><tr><td>'male','rain'=>'1'</td><td>1.73</td><td>0.44</td><td>0.67 0.62</td></tr><tr><td>'self training','rain'=>'7'</td><td>1.91</td><td>0.41</td><td>0.83 0.67</td></tr><tr><td>'self training','male','time 3'=>'7'</td><td>1.55</td><td>0.33</td><td>0.75 0.47</td></tr><tr><td>'school training','male','age 2'=>'7'</td><td>1.32</td><td>0.25</td><td>0.71 0.36</td></tr></table></body></html>

表11 $\mathbf { a } { = } 1$ ， $\scriptstyle \mathsf { b } = \mathbf { c } = 0 . 5$ 条件下挖掘规则结果表  

<html><body><table><tr><td rowspan="2">规则</td><td colspan="3">适应支持 置信度 覆盖度</td></tr><tr><td>度 度</td><td>/2</td><td>/2</td></tr><tr><td>'male','time2'=>'1'</td><td>1.00 0.28</td><td>0.355</td><td>0.365</td></tr><tr><td>'Driving experience1','female'=>'4'</td><td>1.015 0.32</td><td>0.44</td><td>0.255</td></tr><tr><td>'school training '=>'1'</td><td>1.035 0.37</td><td>0.395</td><td>0.27</td></tr><tr><td>'male','rain'=>'1'</td><td>1.085 0.44</td><td>0.335</td><td>0.31</td></tr><tr><td>'self training','rain'=>'7'</td><td>1.16 0.41</td><td>0.415</td><td>0.335</td></tr><tr><td>'self training','male','time 3'=>'7'</td><td>0.94 0.33</td><td>0.375</td><td>0.235</td></tr><tr><td>'school training','Northeasterlywind', 'rain'=>'6'</td><td>0.881 0.42</td><td>0.298</td><td>0.163</td></tr></table></body></html>

表12 $\scriptstyle \mathbf { b = } 1$ ， $\mathsf { a } { = } \mathsf { c } { = } 0 . 5$ 条件下挖掘规则结果表  

<html><body><table><tr><td>规则</td><td colspan="3">适应度支持度/2置信度覆盖度/2</td></tr><tr><td>'male','time2'=>'1'</td><td>1.212</td><td>0.14</td><td>0.71 0.365</td></tr><tr><td>'Driving experience 1','female'=>'4'</td><td>1.295</td><td>0.16 0.88</td><td>0.255</td></tr><tr><td>'school training'=>'1'</td><td>1.245</td><td>0.185 0.79</td><td>0.27</td></tr><tr><td>'male','rain'=>'1'</td><td>1.2</td><td>0.22</td><td>0.67 0.31</td></tr><tr><td>'self training','rain'=>'7'</td><td>1.37</td><td>0.205</td><td>0.83 0.335</td></tr><tr><td>'Driving experience1','rain'=>'3'</td><td>1.173</td><td>0.097</td><td>0.79 0.286</td></tr><tr><td>'self training','male','time 3'=>'7'</td><td>1.15</td><td>0.165</td><td>0.75 0.235</td></tr><tr><td>'school training','male','age 2'=>'7'</td><td>1.015</td><td>0.125</td><td>0.71 0.18</td></tr><tr><td>'Driving experience 2','time 3'=>'7'</td><td>1.037</td><td>0.112</td><td>0.82 0.105</td></tr></table></body></html>

将表11与10对比分析可知，表11结果集中新增了规则（黑体加粗部分)：驾校培训'，东北风'，雨天 $\prime { = } >$ 事故类型 $6 ^ { \prime }$ ·由天气历史数据可知，贵阳地区的风向长期以冬季的东北风和夏季的西南风为主，针对此规则建议可以加强驾校培训学员在冬季起东北风且雨天时的安全教育；此规则的支持度较高，置信度为0.596，但覆盖度的值偏低，其余规则与表10基本保持

一致。

将表12与10对比分析易知，在重点关注置信度的情况下，结果集中同样找到了两条适应度较高的新规则：0-4年驾龄'，雨天 $! { \Rightarrow } ^ { \prime }$ 事故类型3'以及'5-11年驾龄'，'下午13-18点 $\therefore \Rightarrow 1$ 事故类型7'，它们都具有较高的置信度，但由于其他指标值不高的原因，导致在系数全部相等时，在混合算法的挖掘中适应度不高而未展现出来，其余规则亦与表10基本保持一致。将表13与10对比分析可知，在重点关注覆盖度的情况下，发现了一条适应度较高的新规则：'女性'，'自培'，雨天 $: > "$ 事故类型1，其余规则同表10保持一致。

对于适应度函数中系数的不同设置体现了用户对于不同指标的关注程度，而用户的偏重会在接下来混合算法的挖掘结果中有所体现，即可能找到一些新的期望规则，从而达到定向挖掘的目的，提高模型分析的精确性。

表13 $\scriptstyle { \mathsf { c } } = 1$ ， $\mathsf { a } { = } \mathsf { b } { = } 0 . 5$ 条件下挖掘规则结果表  

<html><body><table><tr><td>规则</td><td>适应度支持度/2置信度/2覆盖度</td><td></td><td></td></tr><tr><td>'male','time2'=>'1'</td><td>1.225</td><td>0.14</td><td>0.355 0.73</td></tr><tr><td>'Driving experience 1','female'=>'4'</td><td>1.11</td><td>0.16</td><td>0.44 0.51</td></tr><tr><td>'school training '=>'1'</td><td>1.12</td><td>0.185</td><td>0.395 0.54</td></tr><tr><td>'male','rain'=>'1'</td><td>1.175</td><td>0.22</td><td>0.335 0.62</td></tr><tr><td>'self training','rain'=>'7'</td><td>1.29</td><td>0.205</td><td>0.415 0.67</td></tr><tr><td>'self training','male','time 3'=>'7'</td><td>1.01</td><td>0.165</td><td>0.375 0.47</td></tr><tr><td>'female','self training','rain'=>'1'</td><td>1.059</td><td>0.089</td><td>0.31 0.66</td></tr></table></body></html>

# 3.3与其他算法的性能比较

对于混合算法找出的规则在验证集中计算其相应的适应度值，图3显示了规则在测试集与验证集中适应度的比较。可以看出，除规则r6差别较大外，其他规则总体较为接近，说明上述找到的规则是可靠的。

接下来只使用Apriori算法对AHP选出的字段数据进行挖掘，得出关联规则；只使用遗传算法对选出的字段数据进行挖掘，初始种群随机生成，其种群大小和混合算法的初始种群相等，函数适应度的设计同式(4)，对于遗传算法中的遗传算子的设计与Apriori-Genetic 混合算法保持一致。通过设置不同的支持度和遗传代数对比三种算法的实验效果。

图4上图所示是混合算法与单独Apriori算法在不同支持度下产生的期望规则(这里定义“期望规则"的适应度值大于1.0，从而保证规则的可靠性)在数量上的比较，其中混合算法的遗传代数为100；可以看出在相同的支持度下，由于混合算法使用了支持度、置信度、覆盖度作为规则的评价指标，加上遗传算法的优化，故混合算法能找到更多且更符合用户期望的规则，而Apriori在支持度增大时，得到的期望规则却逐渐减少。图4下图所示是混合算法与单独遗传算法在相同的支持度（0.1）不同的遗传代数下产生的期望规则数量比较。而在遗传代数较少时，由于单独遗传算法的初始种群为随机生成，发现的期望规则数相对混合算法较少，但随着遗传代数的增加，搜索空间增大，简单遗传算法和混合算法所找到的规则数趋于接近，效果相差不大。

![](images/d0a2b6137def1ee00b39cb5848edae65216fb845f898ed9dce088e2cb897545a.jpg)  
图3相关期望规则在测试集与验证集上适应度的比较

Assosiation Description: r1:'male','time2'=>'1' r2:'Driving experience 1','female'=>'4' r3:'school training $" { \Rightarrow } "$ = r4:'male','rain'=>'1' r5:'self training','rain'=>'7' r6:'self training','male','time ${ } ^ { 3 ^ { \prime } = > " }$ r7:'school training','male','age $2 ^ { \prime } { = } > ^ { \prime } 7 ^ { \prime }$

Numbers Apriori GA 50 三 40   
Vssreserertes 30 20 10 0- support 0.05 0.1 0.15 0.2 Simple Genetic Numbers 1GA 60 50 sersee 30 20 10- 0 50 times 100 times 200 times 400 times iterate numbers of Algorithm

图4不同算法下生成期望规则在数量上的比较

同时对比混合算法与C4.5，随机森林等其他算法获得的期望规则数量，图5显示了在不同支持度阈值下不同算法获得的期望规则数量。数据显示混合算法的寻找能力要优于C4.5与随机森林算法，验证了混合算法的优秀性能。

图6所示是混合算法与单独apriori算法在不同支持度下运行结束的时间比较，以及混合算法与单独遗传算法在相同的支持度（0.1）不同的遗传代数下运行结束的时间比较。由图可知当遗传代数较少时混合算法的表现要优于单独的遗传算法；但混合算法的运行时间要差于单独的Apriori算法。

为了降低混合算法的时间复杂度，在读取数据并计算适应度函数时通过开启多线程协作，可以降低算法的时间复杂度。

图7所示是并行化后的混合算法与单独apriori算法在不同支持度下运行的时间比较，以及并行化后的混合算法与单独遗传算法在相同的支持度（0.1）不同的遗传代数下运行的时间比较。由图可知混合算法在并行化后的运行时间有较大改善，接近于单独的 Apriori 算法。

Numbers GA 60- C4.5 50 1 40   
Asaeesesreetes 30 20 10- 0 Support

![](images/a73ac45d6124a9906753a2bc5ad02c86b7408ccb9ffd1090917b6c689c7816d7.jpg)  
图5不同算法下获得的期望规则在数量上的比较

![](images/cd908226da613b02f73f4f0882c6714d853e3b838f6910aad1feed97bb35b340.jpg)  
图6不同算法在运行时间上的比较（单位：s)  
图7混合算法并行化后与其他算法在运行时间上的比较(单位：s)

# 4 结束语

本文主要面向交通事故数据集的数据挖掘工作，针对交通事故数据复杂的多维多层特点，在对比现有事故处理算法的基础上，引入了AHP方法，同时设计了混合的Apriori-Genetic 算法用于挖掘交通事故成因，并建立了事故成因分析模型，挖掘事故成因。通过对比混合算法与传统算法的性能，表明混合算法具有可行性，同时实验结果表明该模型可以提高挖掘的准确性并减少无用规则的产生，具有较好的应用价值。但AHP矩阵的构造终究带有一定的主观性，如何消除这一误差将是下一步的研究工作。

参考文献:   
[1]中华人民共和国交通运输部.2014 中国交通运输统计年鉴[M].北京： 人民交通出版社，2015:11-15.   
[2]中华人民共和国公安部．交通事故发生数总(起)[EB/OL].(2015-6-17) [2017-7-8]. htp://data. stats. gov. cn/search. htm?s $\ L =$ trafficaccident   
[3]中华人民共和国公安部．中华人民共和国道路交通事故统计报告 [EB/OL]. (2016-8-5)[2017-7-9]. htp://www.mps.gov.cn/n2256342/index. html.   
[4]贵阳市政府．贵阳交通大数据竞赛 [EB/OL].(2015-7-23)[2017-7-12] http://jzd. gygov.gov.cn/art/2016/1/15/art_24609878350.html.   
[5]Tibebe B.Mining road trafc accident data to improve safety: role of roadrelated factors on accident severity in ethiopia [C]/ Proc of AAAI Spring Symposium on Artificial Intelligence for Development. 2010: 377-384.   
[6]Marukatat R. Structure-based rule selection framework for association rule mining of traffic accident data [C]// Proc of International Conference on Computational and Information Science.Berlin: Springer,2006: 231-239.   
[7]Murat Y S. Modelling traffic accident data by cluster analysis approach [J]. TEKNIK DERGI,2009,20 (3): 759-777.   
[8]RoshamidaAJ,Amir MA U. Risk assessment ofdry bulk cargooperations using Analytic Hierarchy Process (AHP） method [J]. IEEE Trans on Information and Communication Technology, 2016:146-159.   
[9]Agrawal R, Imielinski T,Swami A.Mining association rules between sets of items in large databases [J].ACM SIGMOD Record,1993: 207-216.   
[10] Whitley LD.The GENITOR algorithm and selection pressure:why rank based allocation of reproductive trials is best [C]// Proc of the3rd International Conference on Genetic Algorithms.San Francisco: Morgan Kaufmann Publishers Inc,1989:116-123.   
[11] Ghosh S,Biswas S,Sarkar D,et al. Mining frequentitemsets using genetic algorithm[J].International Journal ofArtificial Intelligence&Applications, 2010,1 (4) .   
[12] Chadokar S K, Singh D. Optimizing network traffic by generating association rulesusingHybrid Apriori-Genetic algorithm[J].IEEE Trans. on Wireless and Optical Communications Networks,2013:1-5.   
[13] S.Jain.Mining & optimization of association rules using effective algorithm [J].International Journal of Emerging Technology and Advanced Engineering,2012,2(4): 281-285.   
[14] KishorP,PorikaS.Anefcientappoachformining positiveand ngative association rules from large transactional databases [J]. IEEE Trans on Inventive Computation Technologies,2016,1:74-77.   
[15]Naredi S,Deshmukh R A. Improved extraction ofquantitative rules using Best M Positive Negative Association Rules Algorithm [J]. IEEE Trans on Electronics,Computing and Communication Technologies,2015:13-18.

[16]Ravi C,Khare N.EO-ARM:an efficient and optimized k-map based positive-negative association rule mining technique [J]. IEEE Trans on Circuit,Power and Computing Technologie,2014:1723-1727.

[17] Doshi M,Roy B.Enhanced data processing using positive negative association mining on AJAX data.Circuits [J].IEEE Trans on Systems, Communication and Information Technology Applications,2014:386-383.