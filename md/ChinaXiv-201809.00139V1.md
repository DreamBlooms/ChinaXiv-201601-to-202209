# 基于因果效应的贝叶斯网络结构学习方法

安宁，滕越，杨矫云，李廉(合肥工业大学 国家智慧养老国际科技合作基地，合肥 230009)

摘要：从数据中学习贝叶斯网络结构是一个NP-hard问题，提高网络结构学习算法精度是研究的重难点。基于 JudeaPearl因果理论，提出了一种贝叶斯网络结构学习方法，提升了现有算法的准确率。利用改进的Pearl因果效应和BDe评分，学习网络节点优先次序，利用K2算法学习初始网络，并通过BDe评分反向调节、互信息和BDe评分删除边以修正学习结果。实验在贝叶斯网络标准数据集ASIA、ALARM上进行，在样本量为 $2 0 0 0 { \sim } 2 0 0 0 0$ 的 20组实验中，学习准确率较MMHC算法平均提升 $1 6 \%$ ，准确率标准差较MMHC算法平均缩小 $1 7 \%$ 。实验表明，基于因果效应的方法较MMHC算法有更好地性能。

关键词：贝叶斯网络；阿尔茨海默病；K2 算法；因果效应；BDe评分；互信息中图分类号：TP301.6 doi: 10.3969/j.issn.1001-3695.2018.07.0348

# Bayesian network structure learning method based on causal effect

An Ning, Teng Yue, Yang Jiaoyun†,Li Lian (National Smart Eldercare International S&TCoperation Base,SchoolofComputer&Information,Hefei Universityof Technology,Hefei230009,China)

Abstract: Learning bayesian networks fromdatais a NP-hard problem.Improvingtheaccuracyof network structure learning algorithms is important,yetdificultyforresearchers.ThepaperproposedaBayesiannetworkstructurelearingalgorithmbased onJudea Pearl’scausal theoryto improve theaccuracyof existing algorithms.The algorithm madeuseof theimproved causal efect andtheBDe scoring-functionto learn the nodes order.thenapplied K2algorithmtoachievean initialized network.At last,itusedtheBDesoring-functiontoadjustthenetworkiversely,besides,itusedmutual-iformationandBDeoresto prune the edges.The proposed method outperforms MMHC algorithm on the ASIA and ALARM data set, with $16 \%$ accurate improvement,and $1 7 \%$ standard deviation less on average.The results show that the method base on causal effect is batter then MMHC algorithm.

KeyWords:Bayesiannetwork;Alzheimer'sdisease;K2algorithm; Causal efect;BDescoring-function;Mutualinformation

# 0 引言

贝叶斯网络是不确定知识表达的重要工具、是一些节点联合概率分布的有向无环图，它由有向无环图（directedacyclicgraph）和条件概率表（conditionalprobability table）两部分组成。其中，有向无环图定性的表示了变量之间的独立关系，条件概率表则定量的表示了变量间的依赖程度。由于其图形可视化的特点，被广泛应用于生物医药领域[1,2]、预测领域[3,4]、分类[56]、因果推断[7,8]、视觉识别[9]、信息检索[10]等。

贝叶斯网的构建方法主要分为通过专家知识构建和通过数据构建。通过专家知识构建贝叶斯网络是一项非常繁琐且容易出错的工作，而从数据中学习得到贝叶斯网络是一个NP-hard问题[]。因此，如何高效、高质量地从数据中学习贝叶斯网络成为了研究的重难点之一。近几十年来，涌现了很多结构学习方法，基于条件独立测试的算法[12,13]、基于评分搜索的算法[14\~16]以及混合条件独立性测试和评分搜索的方法[17]。

基于评分函数的方法包含两个部分：a）用来衡量网络和数据拟合程度的评分函数,如BIC（Bayesianinformationcriterion）评分标准，它是在样本满足独立同分布的前提下，用对数似然度来度量网络结构与观测数据的拟合程度[18]、还有假设结构先验分布服从狄利克雷分布的BDe评分[15]、假设结构先验分布服从均匀分布的CH评分（K2评分函数）[19]、基于数据编码总长度度量的MDL评分（minimumdescription length）[l4]等；b）寻找最高评分函数的方法。如：需要节点优先顺序的K2算法[21,22]、最大最小爬山算法[23]、更容易获得全局最优的粒子群算法[20]、爬山算法等。由于搜索空间是关于节点个数指数上升的，所以不能使用穷举法得到评分最高的网络。

基于条件独立性测试的方法虽然能较准确的学习贝叶斯网络结构，但只适用于离散数据，对于多维数据下的学习效率不理想。结合条件独立性测试和评分搜索的方法有更高的准确率。其中最为代表性的是MMHC方法。MMHC算法分为第一阶段MMPC算法，和第二阶段的评分方法。MMPC算法首先确定目标变量 $T$ 的父子节点集 $C P C ( T )$ ，以 $T$ 变量的父子节点集为条件，计算网络中其他变量关于 $T$ 变量的最小依赖程度$A s s o c ( X , T | C P C ( T ) )$ 。最小依赖程度取最大的变量加入到 $T$ 的候选父子节点集。直到 $M a x A s s o c ( X , T | C P C ( T ) )$ 为零进入MMPC算法第二阶段，通过两个准则删除第一阶段错误加入的候选父子节点，从而构建无方向的贝叶斯骨架。MMHC算法第二阶段则是通过删除、增加、反向三个调节因子结合评分函数进行打分，取最高分值作为网络学习结果[23]。

K2算法是一种可以明显缩小搜索空间的贪婪搜索算法，但需要提供节点优先顺序（在序列中，排在前的节点不可能是排在后的节点的子节点)。节点顺序的正确性，直接影响了网络的训练结果。近年来，有部分学者针对K2节点优先顺序做了相关研究[17]，从算法的时间复杂度和准确性来说，仍不能满足大数据下的应用。

基于因果效应的方法从JudeaPearl提出的因果理论入手[24],通过定义的因果效应强度计算、无边网络BDe评分计算，得到节点优先顺序。结合K2算法和互信息学习贝叶斯网络。在标准数据库下的实验表明，该方法在准确率和标准差性能上远高于其他方法。

# 1 贝叶斯网络和因果推断

# 1.1 贝叶斯网络

贝叶斯网是一个带参数的有向无环图，可以用 $< G , \Theta >$ 来表示。其中： $G$ 代表有向无环图，如图1所示。 $\Theta$ 代表父节点对于子节点的条件概率表。 $G$ 是一个二元组 $\langle \mathrm { V } , \mathrm { G } \rangle$ ，其中 $V$ 代表所有随机变量组成的点集， $V = \{ X _ { 1 } , . . . , X _ { n } \}$ ， $X _ { i }$ 为图 $\mathbf { G }$ 中第i个节点， $E$ 代表边组成的集合，根据图论的相关知识，边集用矩阵$A _ { n ^ { * } n }$ 来表示。若 $X _ { i } \to X _ { j }$ ，则矩阵 $A _ { i , j } = 1$ ，否则 $A _ { i , j } = 0$ 。在有向无环图中，节点代表每一个变量，边代表变量之间的依赖关系。

如图1所示， $X = \{ X _ { 1 } , . . . , X _ { n } \}$ 代表随机变量，若在图中存在箭头 $X _ { i } \to X _ { j }$ ， ${ \mathrm { i , j } } \in \{ 1 , 2 \cdots { \mathrm { n } } \}$ ，则表明 $X _ { i }$ 是 $\boldsymbol { X } _ { j }$ 的父节点。根据马尔可夫假设， $\mathrm { X } _ { 1 }$ ， $X _ { 2 } \ldots X _ { \mathrm { n } }$ 的联合概率分布可以用式（1）表示。

$$
P ( X _ { 1 } , . . . , X _ { n } ) = \prod _ { i = 1 } ^ { n } P ( X _ { i } | \pi ( X _ { i } ) )
$$

其中： $\pi ( \boldsymbol { X } _ { i } )$ 表示 $X _ { i }$ 的所有父节点。

![](images/698d73f8683a9346e4e2332ff4fc786c325ab033e90c3d1d8be69fa9886a1d79.jpg)  
图1一个贝叶斯网络

# 1.2 因果理论

传统的统计学用相关性来描述随机变量间的关系。但是相关性不能完全概括随机变量之间的关系。例如可以很容易得到“刮风一树叶摇晃”的关联关系。根据常识，刮风是树叶摇晃的原因，有刮风 $$ 树叶摇晃。但反过来，则会认为树叶摇晃是刮风的原因，这显然是错误的。在关联关系中，存在着因果关系。

Pearl对于这一系列问题，提出了因果理论。他对于事物间的因果性的强度用平均因果效应来描述，更加形式化的，用式（1）描述两事物 $X , ~ Y$ 之间的平均因果效应（average causeeffective，ACE）。

$$
\begin{array} { l } { { A C E = P ( Y = 1 \vert d o ( X = 1 ) ) } } \\ { { - P ( Y = 1 \vert d o ( X = 0 ) ) } } \end{array}
$$

其中： $d o ( X = 1 )$ 为 Pearl 定义的“do一操作”。式（3）给出了“do一操作”的形式化定义：

$$
\begin{array} { l } { P ( Y = y \vert d o ( X = x ) ) } \\ { \frac { } { Z } P ( Y = y \vert X = x , Z = z ) P ( Z = z ) } \end{array}
$$

其中： $Z$ 为 $X$ 到 $Y$ 的后门路径集合。

# 2 贝叶斯网络结构学习方法

由于K2算法需要为之提供节点优先次序，而节点优先次序只能定性地描述变量之间的父子关系，所以基于因果效应的方法第一步定义了节点优先度，用于定量地描述节点之间父子关系。2.1节定义了节点优先度的计算方法，将节点优先度向量降序排列，得到节点优先次序。第二步通过节点优先次序，结合K2算法初始化贝叶斯网络。为提高运算效率，提出的节点优先度计算方法不考虑两节点之间的后门路径，虽然在不考虑后门路径的情况下，大部分节点优先次序已经是真实的优先次序，但部分节点优先次序和真实优先次序有一定偏差，得到的初始化网络存在反向边和多边的情况。所以第三步通过逐一将已有边反向和删除，寻找比初始化网络评分更高的网络代替初始化网络。为避免使用评分删除和反向调节时陷入局部最优，使用互信息删除边策略同时删除部分多余边，这样可以使评分从另一个新的起始点开始。最后，直到评分不再上升时结束算法。

# 2.1节点优先度和节点优先次序

节点优先次序包括两个算法，分别从改进的因果效应和无边BDe评分出发，通过两个算法得到节点优先度向量。降序排列该向量，得到节点优先次序。更加形式化地，有如下定义：

定义1节点优先度。对于任意的节点 $X _ { i }$ 、 $x _ { j } \in$ $V \{ X _ { 1 } , \dots , X _ { n } \}$ ， $\mathrm { ~ v ~ }$ 是贝叶斯网络中的节点集， $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 为贝叶斯网络节点个数，对于节点集 $Y = \{ X _ { 1 } , \textrm { X } _ { 2 } . ~ . ~ . ~ \mathrm { X } \mathrm { i } . 1$ ， $\mathrm  X _ { i + 1 } , . . . \mathrm { X _ { n } } \}$ 和节点 $X _ { i }$ 。给定一个判断标准 S，存在 $\mathrm { ~  ~ N ~ }$ 个节点 $\{ \boldsymbol { X } _ { k } ^ { 1 } , ~ \boldsymbol { X } _ { k } ^ { 2 } , ~ \boldsymbol { X } _ { k } ^ { N } \}$ ， $X _ { k } \in Y$ ，使得判断标准S成立，则 $\mathrm { ~ N ~ }$ 为节点 $X _ { i }$ 的优先度。

# 2.1.1基于因果效应的节点优先度算法

使用如下形式近似数据集中任意两节点 $X _ { i } , X _ { j }$ 之间的因果效应（cause effective）CEx;→x :

$$
\begin{array} { l } { \displaystyle { C E _ { X _ { i } \to X _ { j } } = \frac { N \big ( X _ { j } = 1 \big ) } { N } * \Big [ P \big ( X _ { j } = 1 | X _ { i } = 1 \big ) - P \big ( X _ { j } = 1 | X _ { i } = 0 \big ) \Big ] } } \\ { \displaystyle { - \frac { N \big ( X _ { j } = 0 \big ) } { N } \big [ P \big ( X _ { j } = 0 | X _ { i } = 1 \big ) - P \big ( X _ { j } = 0 | X _ { i } = 0 \big ) \big ] } } \end{array}
$$

其中： $N { \big ( } X _ { j } = 1 { \big ) }$ 表示 $\boldsymbol X _ { j } { = } 1$ 的样本个数， $\mathrm { ~  ~ N ~ }$ 表示总样本量。$X _ { i } = 1$ 表示随机变量 $X _ { i } = t u r e$ ， $X _ { i } = 0$ 表示随机变量 $X _ { _ { j } } = f a l s e$ 。不考虑“do-操作”，并拓展J.pearl的因果效应。式（2）的ACE只考虑了 $X$ 节点对于 $Y$ 节点在 $\scriptstyle \ Y = 1$ 处的因果效应。如式（4)所示，考虑了 $X _ { i } \to X _ { j }$ 在 $X _ { j } = 1$ 和 $X _ { _ j } = 0$ 两处的因果效应。

使用因果效应作为判断标准，算法从网络中的一个节点出发，依次计算该节点对于其他节点的因果效应，若$C E _ { X _ { i }  X _ { j } } > C E _ { X _ { j }  X _ { i } }$ ，则 $X _ { i }$ 的节点优先度加一，否则 $X _ { j }$ 的节点优先度加一。算法遍历网络中任意两节点之间的因果效应。假设有N个节点，共进行 $\begin{array} { r } { \sum _ { x = 1 } ^ { N - 1 } x . } \end{array}$ 次计算。降序排列节点优先度向量，得到节点优先次序。

# 2.1.2基于BDe评分函数的节点优先度方法

BDe 是最早的贝叶斯网络数据拟合程度的评分函数之一，它假设数据服从狄里克雷分布（dirichletdistribution)，有如下形式：

$$
\begin{array} { l } { { s c o r e ( G \vert D ) = } } \\ { { { \displaystyle \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { q _ { i } } } \Biggl [ l o g \frac { \Gamma \bigl ( \alpha _ { i j ^ { * } } \bigr ) } { \Gamma \bigl ( \alpha _ { i j ^ { * } } + m _ { i j ^ { * } } \bigr ) } + \sum _ { k = 1 } ^ { r _ { i } } l o g \frac { \Gamma \bigl ( \alpha _ { i j k } + m _ { i j k } \bigr ) } { \Gamma \bigl ( \alpha _ { i j k } \bigr ) } \Biggr ] } } \end{array}
$$

其中： $\Gamma ( ^ { * } )$ 为伽马函数， $m _ { i j k }$ 表示数据中第i个节点，取第k个值，其父节点为第j个值的样本个数， $\alpha _ { i j k }$ 是狄利克雷分布的超参数，角标含义同 $\mathbf { m } _ { i j k }$ 。 $m _ { i j ^ { * } } = \sum _ { k } \mathbf { m } _ { i j k }$ ， $\mathbf { a } _ { i j ^ { * } } = \sum _ { k } \mathbf { a } _ { i j k }$ 。

使用BDe函数作为判断节点优先度的标准，得到基于BDe评分函数的节点优先度向量。算法开始从一个只有节点的网络出发。对于网络中所有节点 $X _ { i } \in \{ X _ { 1 } , . . . , X _ { n } \}$ 和$X _ { j } \in \{ X _ { 1 } , X _ { 2 } . . . X _ { i - 1 } , X _ { i + 1 } . . . X _ { n } \}$ 构建两个图G，其中： $G _ { \imath }$ 的节点 $X _ { i }$ 指向 $X _ { j }$ ， $G _ { 2 }$ 的 $X _ { j }$ 指向 $X _ { i }$ 。然后根据 BDe 评分函数计算 $s c o r e ( G _ { 1 } | D )$ 和 $s c o r e ( G _ { 2 } | D )$ ，若 $s c o r e ( G _ { 1 } | D ) _ { \ > }$ （204号score $\cdot ( G _ { 2 } | D )$ ，则 $X _ { i }$ 的优先度加一，反之亦然。降序排列节点优先度向量得到节点优先次序。

需要特别说明的是，若在节点优先度向量中，X节点和Y节点的节点优先度相同，则使用当前节点优先度评判标准，仅针对X和Y两个节点判断节点优先顺序。

# 2.2 初始化网络

运用得到的节点优先次序结合K2算法学习初始化网络。在节点优先度计算环节中，大部分情况可以直接得到正确的节点优先次序，但是由于基于因果效应的节点优先度计算方法删除了“do-操作”和后门路径，基于BDe评分的节点优先度计算方法只考虑无边网络评分，所以节点优先度向量和真实优先度向量可能存在偏差，到这里得到的是一个近似正确的网络。

K2（cooperandHerskovits,1992）是贝叶斯网络结构学习算法之一，设随机变量 $D = \{ X _ { 1 } , . . . , X _ { n } \}$ 是一组完备数据集。K2算法使用CH评分作为评分准侧，其形式如下：

$$
s c o r e K 2 = \sum _ { \mathrm { i = 1 } } ^ { \mathrm { n } } \left[ \sum _ { \mathrm { j = 1 } } ^ { \mathrm { q i } } \left[ l o g \frac { ( r _ { i } - 1 ) ! } { \left( m _ { i j ^ { * } } + r _ { i } - 1 \right) ! } + \sum _ { k = 1 } ^ { r _ { i } } l o g ( m _ { i j ^ { * } } ) \right] \right]
$$

其中： $\mathbf { m } _ { i j k }$ 表示数据中第i个节点，取第 $\mathbf { k }$ 个值，其父节点为第j个值的样本个数， $m _ { i j ^ { * } } = \sum _ { k } \mathbf { m } _ { i j k }$ 。为了缩小搜索空间，需要给K2算法提供节点次序和最大父节点个数。排在节点次序前的随机变量不能成为排在节点次序后的随机变量的子节点。例如，若有节点顺序 $o r d e r = \{ . . . X _ { i } , . . . , X _ { j } . . . \}$ ，则 $X _ { i }$ 不可能是 $X _ { j }$ 的子节点。K2算法的结果正确性很大程度取决于节点次序。节点次序一般通过先验知识获得，但在现实中，基本无法通过先验知识获得节点次序，以下提供了从数据中学习节点次序的方法。

# 2.3反向调节和基于互信息的删边策略

# 2.3.1基于互信息的删除边策略

大部分情况下，初始化的网络就是真实的贝叶斯网络。但也有可能由于节点次序的略微偏差导致网络中少量边是错误的。因此需要对这些边进行反向调整和删除操作。由于2.3.2的评分调节策略是在某一特定情况下，对网络的某些边进行反向和删除操作，容易陷入局部最优，无法更贴近全局最优。为了使评分的初始值更贴近全局最优，减少容易陷入局部最优的情况，使用互信息删除关联度较小的边(这些边在真实网络中不存在，在当前状态下的评分有可能高于删除后的评分)，从而更容易使2.3.2的评分方法贴近全局最优。互信息可以用来描述变量之间相关程度，用下式描述：

$$
I ( X ; Y ) { = } H ( X ) { - } H ( X | Y )
$$

其中： $H ( X )$ 为变量 $X$ 的信息熵， $H ( X | Y )$ 为变量 $X$ 对于变量 $Y$ 的条件信息熵。变量 $X$ 的信息熵可以用下式描述：

$$
\begin{array} { r } { H \left( X \right) = - \sum _ { \begin{array} { c } { X = x } \end{array} } P \left( x \right) { } ^ { * } l o g P \left( x \right) } \end{array}
$$

同样地，变量X和变量Y的条件信息熵可以用式（9）描述。

$$
H ( X \mid Y ) = - \sum _ { X = x Y = y } P ( x | y ) * l o g P ( x \mid y )
$$

信息熵描述了变量所含信息不确定性的多少。使用互信息代替条件独立测试，可以有效地提升计算效率。删除边策略是将所有节点之间的互信息进行降序排列，对于网络中的所有节点，依次作为目标节点 $T$ ，选择目标节点 $T$ 的互信息排名靠前的h个节点作为可能和目标节点 $T$ 有边的节点集。然后在初始化网络中，对于和目标节点有边连接的节点Y依次查看a)T节点是否在 $Y$ 节点的前h个互信息倒序排列列表中;b） $Y$ 节点是否在 $T$ 节点的前h个降序排列的互信息节点列表中。若a）b)都不满足，则删除目标节点 $T$ 和 $Y$ 节点之间的边。为了避免错误的删除正确边以及不能删除多余边两种情况，根据节点数量来选择h的数值。在实验部分，取 $\mathtt { h } { = } \lceil \frac { 3 } { 8 } n \rceil$ ，其中 $\mathfrak { n }$ 是节点个数。

# 2.3.2基于BDe评分的反向调节和删边调节

完成了2.3.1节的环节后，已经将网络中大部分相关度不高的节点对之间的边删除，此时网络评分更接近全局最优。这时还需要调节部分由于节点次序错误导致的反向边。

在这个环节，使用BDe评分作为调节标准，使用反向边和删除边两个算子，对于网络中的边集 $E = \{ e _ { 1 } , e _ { 2 } . . . e _ { n } \}$ ，依次将边$e _ { i }$ 反向和删除，然后计算BDe评分，若BDe评分高于反向前网络的BDe评分，将边 $e _ { i }$ 反向或删除。直到评分不再增加停止算法。

# 3 实验结果

基于因果效应的方法在两个贝叶斯标准数据库下测试（ASIA数据库、ALARM数据库），并与MMHC算法、MCMC算法、爬山法和随机K2算法进行对比。对于同一组数据，从正确边、丢失边、反向边、多边的平均值以及标准差进行对比。取不同样本量数据进行实验，样本量分别为(2000、4000、6000、8000、10000、12000、14000、16000、20000）.实验表明，该方法在正确边个数、错误边个数均胜过其他贝叶斯网络学习方法。

# 3.1ASIA数据库

ASIA数据库是贝叶斯标准数据库之一，描述了胸腔诊断网络，如图2所示。实验结果如表1和图3、4所示。

可以看到，基于因果效应的方法在10组实验中，平均正确边数高达7.0条，而MMHC算法的平均正确边数仅为6.3条，正确边数量较MMHC算法提升了 $1 1 . 1 \%$ 。图3展示了不同算法在不同样本量下的正确边数量。在ASIA数据库中，MMHC算法是对比算法中性能最为优越的。图4针对MMHC算法进行了正确边增量对比。为便于阅读，隐藏横坐标相应样本量，横坐标数值同图3。

![](images/68ef2a4f9e28001622f4a016eff5002857656f1779ded8a6206a00186cdc1c45.jpg)  
图2ASIA网络

表1ASIA网络学习结果比较分析  

<html><body><table><tr><td colspan="2">基于因果效应</td><td rowspan="2">爬山法</td><td rowspan="2"></td><td rowspan="2">随机节点顺序 的K2方法</td><td rowspan="2">MMHC算法</td><td rowspan="2"></td><td rowspan="2">MCMC算法</td></tr><tr><td></td><td>的方法</td></tr><tr><td>正确边</td><td>平均 7.0</td><td>标准差 0.94</td><td>平均 标准差 3.75</td><td>平均</td><td>标准差 平均</td><td>标准差</td><td>平均 标准差</td></tr><tr><td>丢失边</td><td>0.1</td><td>0.32</td><td>1.75 0.65</td><td>3.41 0.16 1.32</td><td>6.3 0.5</td><td>0.82 0.71</td><td>3.9 2.18 0.5</td></tr><tr><td>反向边</td><td>0.8</td><td>0.96 0.79</td><td>1.75</td><td>0.36 3.26 0.26</td><td>1.2</td><td>0.63</td><td>0.71 3.5 1.78</td></tr><tr><td>多余边</td><td>0.7</td><td>3.29 1.06 1.68</td><td>1.31</td><td>4.67 0.24</td><td>0.6</td><td>0.84</td><td>4.0 1.70</td></tr><tr><td>图错误</td><td>1.5 1.51</td><td>5.93</td><td>2.81</td><td>9.27 0.28</td><td>2.3</td><td>1.26</td><td>8.0 3.50</td></tr></table></body></html>

![](images/19246b6408ffcfde89eb9c1475cfc84555d45f7b154ffc7cf910d82ed20a9554.jpg)  
图3ASIA网络正确边对比

![](images/3586eda8154181842f7796035ea8b99bb6df9a796977d99010b31f193ec58945.jpg)  
图4ASIA网络正确边增量对比

实验表明，在ASIA数据集上，基于因果效应的方法比MMHC算法有更高的准确性，在十组实验数据中，有四组达到了全局最优，学习到了全部正确的网络结构（正确边为8条的网络结构)，而MMHC算法仅有一组学习到了完全正确的网络结构。对于大多数样本来说，该方法较MMHC 算法更容易达到全局最优。

# 3.2 ALARM网络

ALARM网络来源于医疗诊断监控系统，由37个节点和46条边组成。其网络结构如图5所示。

![](images/99f4dc9e1bc790ea931cd4e0098e8cfa33620ca53fa248eaaf132ee8828fbb4e.jpg)  
图5ALARM网络结构

这里选用基于BDe评分的节点优先次序计算方法来进行实验。实验表明，该方法能准确学习贝叶斯网络。表2给出了实验结果。基于因果效应的方法在ALARM十组数据集中平均正确边数为41.2条，而MMHC算法的平均正确边数仅有34.1条，较MMHC算法正确率提升 $20 . 8 \%$ 。结合ASIA网络的实验结果，在20 组实验数据中，平均正确率较MMHC方法提升$1 6 \%$ 。

图6给出了不同算法在不同样本量数据下的正确边对比，MMHC算法性能优于其他对比算法。图7给出了基于因果效应的方法较MMHC算法的增量对比。为方便对比，图7隐藏了横坐标数值，具体数值同图6。

表2ALARM网络学习结果比较分析  

<html><body><table><tr><td colspan="2">基于因果效应</td><td rowspan="2">爬山法</td><td rowspan="2"></td><td rowspan="2">随机节点顺序 的K2方法</td><td rowspan="2"></td><td rowspan="2">MMHC 算法</td><td rowspan="2">MCMC算法</td></tr><tr><td></td><td>的方法</td></tr><tr><td></td><td>平均</td><td>标准差</td><td>平均</td><td>标准差 平均</td><td>标准差</td><td>平均 标准差</td><td>平均</td><td>标准差</td></tr><tr><td>正确边</td><td>41.2</td><td>3.08</td><td>21</td><td>4.24 21.9</td><td>0.61</td><td>34.1</td><td>6.05</td><td>20 3.56</td></tr><tr><td>丢失边</td><td>0.5</td><td>0.53</td><td>2.5</td><td>0.71 2.40</td><td>0.25</td><td>0.3</td><td>0.48</td><td>3.5 2.11</td></tr><tr><td>反向边</td><td>4.2</td><td>2.53</td><td>22.5</td><td>4.94 21.8</td><td>0.54</td><td>11.6</td><td>6.19</td><td>22.5 2.83</td></tr><tr><td>多余边</td><td>5.5</td><td>2.32</td><td>12</td><td>2.82 40.8</td><td>1.45</td><td>4.1</td><td>1.45</td><td>44.5 8.03</td></tr><tr><td>图错误</td><td>10.2</td><td>4.80</td><td>37</td><td>7.07 64.9</td><td>1.66</td><td>16.0</td><td>6.93</td><td>70.5 10.54</td></tr></table></body></html>

可以看到，基于因果效应的方法在ALARM图的十个数据库中有8个数据库好于MMHC算法，在丢失边和反向边上都好于MMHC 算法。由于使用K2 算法得到初始化网络，当节点优先次序错误时，会导致多余边数量的上升。在第二部分删除边调节中，仅考虑同时最多删除一条边的评分比较，这虽然可以提高运算效率，但是还是存在陷入局部最优的可能性，从而导致多余边在某些情况下不能完全删除。图8给出了两个网络，20组实验结果的平均标准差数据对比。

基于因果效应的方法，正确边标准差平均较MMHC低 $1 7 \%$ 号其中ASIA网络中，正确边标准差无明显差异，这是因为ASIA只有8个节点8条边，相对于大型网络，算法学习难度较低，不容易陷入局部最优。而在alarm网络中，由于共有46条边需要学习，学习难度较大，容易陷入局部最优，所以标准差差距也相对较大。对比随机K2方法的平均标准差，虽然随机K2算法的标准差性能是最好的，但是如图9所示随机K2方法准确率明显低于基于因果效应的方法。分析随机K2方法的图结果发现，当节点顺序有较大偏差时，虽然正确边和爬山法、MCMC相差不大，但随机K2方法生成的网络更偏向于全连通网络，应用价值非常低。图9给出了算法的正确率对比。可以看到，在两个网络的平均正确率上，该方法较MMHC有明显的提升。

![](images/80e6de53b55554d643e7e892cd24fce5b78c53f4e60b7127874f6f9a21b98c2c.jpg)  
图6ALARM网络正确边对比

![](images/d25beb89dbc9de909034ff26f176f24902de285065d55c5660db02428ae35c13.jpg)  
图7ALARM网络增量对比

![](images/c752b1148aff1232de87d9d12e1dc5c9fc91e361475cae7069b0cebc1c758f9e.jpg)  
图8不同方法标准差对比

![](images/4c3d907f158f0bdc053b4155645c2649e04a668c829342f9c1e125b1e579b95c.jpg)  
图9不同方法正确率对比

实验表明，基于因果效应的方法较其他算法有更好的准确性和稳定性，在ASIA数据库上胜过MMHC算法，远超爬山法、随机K2法和MCMC算法。在大型网络ALARM中，随着样本数的增加，较 MMHC 算法的效率也随之提升，远超过MMHC、MCMC等算法，有更好的准确性和稳定性。

# 4 结束语

贝叶斯网络是用来描述节点联合概率的图模型，贝叶斯网络中的箭头可以表示因果性。提出了基于pearl 因果效应和基于BDe评分函数的节点优先度算法，结合K2算法在贝叶斯网络标准数据库上胜过MMHC等算法。基于因果效应的方法在调节反向边环节，是通过评分函数调节的。目前已有的评分函数，都需要假设数据服从某一个先验分布。这使得评分函数不能准确的描述数据和网络的拟合程度。考虑到在今后的研究中，可以通过文本挖掘关键词网络中有相关关键词的句子，用自然语言处理的方法识别出贝叶斯网络箭头的方向，从而调整从数据中学习得到的图的部分错误边方向。这也是今后贝叶斯网络学习的发展趋势。

# 参考文献：

[1]Seixas FL, Zadrozny B,Laks J,et al.ABayesian network decision model for supporting the diagnosis of dementia,Alzheimer's disease and mild cognitive impairment [J].Computers in Biology and Medicine,2014,51(7): 140-158.   
[2]Ramazzotti D, Graudenzi A,Antoniotti M. Modeling cumulative biological phenomena with Suppes-Bayes causal networks:[J/OL].Evolutionary Bioinformatics Online,2018,14.(2016-02-25)[2018-02-26].http://dx. doi. org/10.1101/041343.   
[3]Fenton N,Neil M,Marquez D. Using Bayesian networks to predict software defects and reliability[J]. Journal of Risk& Reliability,2017,222 (22): 701-712.   
[4] 金杉，崔文，金志刚．正态分布的贝叶斯网络火灾数据融合预警研究 [J].计算机应用研究,2016,33(5):1473-1476.   
[5] Sein M，傅顺开，吕天依，等．一般贝叶斯网络分类器及其学习算法 [J].计算机应用研究,2016,33(5):1327-1334.   
[6]He Lianghua,Hyu Die,Wan Meng,et al. Common Bayesian network for classification of EEG-Based multiclass motor imagery BCI[J]. IEEE Trans on Systems Man & Cybernetics Systems,2017,46 (6): 843-854.   
[7] 高瑞，王双成，杜瑞杰．企业运行指标因果分析的动态贝叶斯网络方法 [J].计算机应用研究,2016,33(5):1433-1436.   
[8]Kaiser JL, Bland CL,Ii D JK.Identifying causal networks linking cancer processes and anti-tumor immunity using Bayesian network inference and metagene constructs [J].Biotechnol Prog,2016,32 (2): 470-479.   
[9]Klinger T,Rottensteiner F, Heipke C.A dynamic Bayes network for visual pedestriantracking[J].ISPRS-InternationalArchivesofthe Photogrammetry:Remote Sensing and Spatial Information Sciences,2014, XL-3 (3): 145-150.   
[10]徐建民，唐万生，陈振亚．贝叶斯网络在信息检索中的应用[J].河北 大学学报：自然科学版,2007,27(1):93-98.   
[11] Chickering DM,Heckerman D,Meek C.Large-sample learning ofBayesian networks is NP-Hard [M].brookline: JMLR.org,2004.   
[12] Zhao bo,Wyu Qingchang,Yin Shitang,et al.An improved Bayesian network structure learning algorithm based on the conditional independence test[J].Journal ofYunnan UniversityofNationalities,2011,20 (5).   
[13] Geng Zhi, Wang Chi, Zhao Qiang.Decomposition of search for V-structures in DAGs[J]. Journal of Multivariate Analysis,2005,96 (2): 282-294.   
[14] Lam W, Bacchus F.Learning Bayesian belief networks: an approach based on the MDL principle [J].Computational Intelligence,1994,10 (3):269- 293.   
[15] Cooper G F,Herskovits E.A Bayesian method for the induction of probabilistic networks from data [J]. Machine Learning,1992,9(4): 309- 347.   
[16] Li Guoling, Xing Lining, Zhang Zhongshan,et al. Anew Bayesian network structure learning algorithm mechanism based on the decomposability of scoring functions [J].IEICE Transon Fundamentals of Electronics Communications & Computer Sciences,2017,100(7):1541-1551.   
[17] Chen Xuewen,Anantha G,Lin Xiantong. Improving Bayesian network structure learning with mutual information-based node ordering in the K2 algorithm[J].IEEE Transon Knowledge& Data Engineering,2008,20(5): 628-640.   
[18]张连文．贝叶斯网引论[M].北京：科学出版社,2006.   
[19] Acid S,Campos LMD.Searching for Bayesian network structures in the space of restricted acyclic partially directed graphs [M]. USC: AI Access Foundation, 2003.   
[20] Liu Xuqing,Liu Xinsheng. Structure learning of Bayesian networks by continuous particle swarm optimization algorithms [J]. Journal of Statistical Computation & Simulation,2018,88 (9):1-29.   
[21]LernerB,MalkaR.Investigation of the K2 algorithmin learning bayesian network classifiers.[J].Applied Artificial Intelligence,2011,25(1):74-96.   
[22] Cooper G F,Herskovits E.A Bayesian method for the induction of probabilistic networks from data[J].Machine Learning,1992,9(4):309 347.   
[23] Tsamardinos L,Brown L E,Aliferis CF,et al. The max-min hill-climbing Bayesian network structure learning algorithm.[J]. Machine Learning, 2006, 65 (1): 31-78.   
[24] Pearl J,Glymour M,JewellNP.Causal inference in statistics: a primer [M], Hoboken: Wiley,2016: 53-87.