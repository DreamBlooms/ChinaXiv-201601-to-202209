# 基于短序列分组和拼接策略的子序列快速查询算法

范纯龙1²，王靖云1,²，滕一平1,²，丁国辉1,2(1.沈阳航空航天大学 计算机学院，沈阳 110136;2.辽宁省大规模分布式系统实验室，沈阳 110136)

摘要：子序列查询技术在金融、商业、医疗等领域均有重要应用，但因DTW（dynamic time warping）等相似性比对算法的时间复杂度较高，子序列长度对检索时间影响很大，限制了数据集上长子序列检索的效率。针对这一问题，提出一种子序列快速查询算法。该算法首先对数据集中特定长度下所有子序列进行分组并标记出代表性子序列;然后在查询时将查询序列切分成定长的小段序列，并用DTW算法确定与小段序列相似的代表子序列候选集；最后对候选集进行序列拼接，获取查询结果序列。实验表明新算法效率较典型算法提高约10倍。

关键词：序列数据查询；动态时间规整；子序列 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2018.11.0866

Fast subsequence query algorithm based on short sequence grouping and assembling strategy

Fan Chunlong1,²2, Wang Jingyun1,2, Teng Yiping1,2, Ding Guohui1,2 (1.School of Computer,Shenyang Aerospace University,Shenyang l10136,China;2.Large-scale Distributed System Laboratory in Liaoning Province,Shenyang l10136, China)

Abstract: Subsequence query technique has important applications in several fields such as finance,commerce,and healthcare. However,due to the high time complexityof similaritycomparison algorithms such as Dynamic Time Warping (DTW)，the length of subsequence has a great influence on theretrieval time，which limits the eficiencyof long subsequence retrieval on data sets.To theend,we present a fast subsequencequery algorithm based onshort sequence grouping andassembling strategy.Inthis algorithm,we firstseparate allsubsequences,whichare ina givenlength,in the data set into groups and mark outthe representative subsequence for each group.Then,during the query processing,the query sequence is cut into smallquery sequences ina fixed length,and using DTWalgorithm we compute the candidate sets ofsubsequences,ofwhich therepresentative subsequence hasa high similarity with the smallquery sequences.Finally, we assemble allthe sequences in thecandidate sets to derive the query resultsequences.Experiments show that the effciency of the new algorithm is about 1O times higher than that of the typical algorithm.

Key words: sequential data query; dynamic time warping; subsequence

# 0 引言

时间序列数据是指随着时间变化而形成的有序的数据列表[1，简称时序数据（timeseries)。时序数据反映了事物或事件随时间变化的状态，序列中的每个时间点都可以用数值或者符号来表示。时间序列数据广泛存在于金融、商业、医药、气象等应用领域中[2],对其的数据挖掘在股票价格预测、遗传物质分析、气象预测等领域均有较为广泛的应用[3]。序列数据查询是时间序列挖掘问题中基础且重要的问题，本文重点关注在大型时序数据中不同长度子序列的查询情况。

距离度量是序列查询技术的基础。欧氏距离（ED）因其计算简单且高效，是目前最常用的距离计算方法之一[4,5]。其他主流的距离度量方法有动态时间规整（DTW）[7]、最长公共子序列（LCSS）[8]、实序列编辑距离（EDR）[8]和实补偿编辑距离（ERP）[8]。这些度量方法都具有很强的鲁棒性，支持时序偏移和不等长序列数据的计算。

时间序列表示是提高查询效率的主要方法。时间序列数据普遍存在维度高和数据量大的特点，对于包含N条时间序列数据集，每条序列长度为n，因此需要计算的子序列总数为 $\mathrm { N } ^ { * } \mathrm { n } ( \mathrm { n } - 1 ) / 2$ 。例如，来自UCR时间序列数据集中的StarLightCurves基准数据个数为9236，每条序列的长度为1024，所以该数据集包含的子序列个数为 $4 . 8 3 ^ { * } 1 0 ^ { 9 }$ ，而现实的数据集一般会比此数据大三个数量级，显然，对所有子序列进行相似性比较是不切实际的。为避免数据量过大而导致系统性能下降，需要将数据表示成低维的形式。常见的表示方法包括离散傅里叶变换（DFT)[9]、离散小波变换（DWT)[10]、奇异值分解（SVD）[I]和分段累积近似（PAA）[12]等。这些方法虽然可以保留大部分原序列所携带的特征信息，但不是将效率作为其主要目标，因此不适用于大型数据集。

范围搜索和最近邻搜索[9]是序列查询的主要目标。通过聚类方法寻找出每一类的代表，进而利用代表进行查询。这类方法主要包括最近邻质心分类器[13]和K-means 聚类。文献[14]使用数据编辑的方法，既保持了原始数据以确保相似性查询准确性，又提高了分类速度。文献[15]介绍了利用DTW算法构建聚类，以及通过改进密度峰值的算法以提高聚类性能。然而该方法的目标是聚类，而不是相似性查询，这与目前的工作不符。

目前，最先进的查询算法(online explorationof time series,

ONEX）[16]同样面临着准确性与查询效率之间难以权衡的问题，尤其是在查询长子序列时，ONEX算法很难快速返回查询结果。然而某些系统以时间为代价来提高查询的准确率[17],缺乏实用性。文献[18]和文献[19]利用DTW算法将子序列查询转换为向量查询，但是该方法需要提供诸多参数，限制了查询效率[20]。

本文对现有的查询算法进行改进，提出一种快速查询长子序列的方法MONEX（modifyonlineexplorationof timeseries)。MONEX算法将候选序列分成子序列，然后根据子序列之间的相似性关系进行编码以支持快速查询子序列。由于对所有不同长度子序列之间相似性关系进行编码是不可行的，所以选取特定长度进行子序列切分，并利用复杂度较低的点对点距离（如欧氏距离)进行相似性编码。在查询阶段，该方法对查询序列进行切分，以确保长子序列的查询速度，然后采用改进的DTW算法进行相似性的计算，最后将相似的序列子段连接成完整的序列。

MONEX算法是对目前最先进的算法ONEX进行的改进。该算法与ONEX相比，查询效率提高了近10倍，准确率提高了 $0 . 0 3 \%$ 。虽然两种算法的准确率非常接近，但在查询长子序列时，MONEX算法的准确率和效率较现有的ONEX算法均有明显提升。

# 1 预备知识

# 1.1基本定义

定义1时间序列。已知时间序列为X， $\mathbf { X } = \left( x _ { 1 } , x _ { 2 } , . . . , \ x _ { n } \right)$ 表示包含 $\mathfrak { n }$ 个真实值的时间序列。D为时间序列数据集，${ \cal D } = \{ X _ { 1 } , X _ { 2 } , . . . , X _ { N } \}$ 表示包含N条时间序列的数据集。

然而现实数据集往往具有高维度和数据量大的特点，因此许多现实场景并不是直接对其进行分析，更多的是将时间序列拆分成较短的子序列然后再进行分析。下面介绍一下时间序列子序列的定义。

定义2时间序列子序列[16。假设存在一条时间序列$\mathbf { X } = \left( { \boldsymbol { x } } _ { 1 } , { \boldsymbol { x } } _ { 2 } , . . . , \ { \boldsymbol { x } } _ { n } \right)$ ， $X _ { \scriptscriptstyle p } [ i , j ]$ 是长度为i，起始位置为j的时间序列子序列，则 $X _ { \scriptscriptstyle p } \left[ i , j \right] { = } ( \mathbf { x } _ { \scriptscriptstyle j } , \mathbf { x } _ { i + 1 } , \mathbf { x } _ { { j + i - 1 } } )$ 其中 $1 { \le } \mathrm { i } { \le } \mathrm { n }$ ， $0 \leq \mathrm { j } \leq \mathbf { n } - 1$ ，$1 { \le } { \mathfrak { p } } { \le } { \mathbb { N } }$ 。

在进行查询时，一般都是根据设定的相似性阈值来判断两条序列是否相似。下面给出相似性阈值的定义。

定义3相似性阈值。通过比较时间序列X和Y的欧氏距离或DTW距离是否小于给定的相似性阈值ST，进而判断两个时间序列是否相似，表示为 $\mathrm { D i s t } ( \mathbf { X } , \mathbf { Y } ) \leq S T$ ，其中$\mathrm { D i s t } \in \{ \mathrm { E D } , \mathrm { D T W } \}$ 。

查询算法都要选择合适的距离度量方法。本文选择利用欧氏距离和DTW距离进行度量，但是由于时间列在搜集时序普遍存在噪声的影响，所以需要使用标准化距离。下面分别给出标准化欧氏距离和标准化DTW距离的定义。

定义4标准化欧氏距离。给定两个序列X和 $\mathrm { \Delta Y }$ ，标准化欧氏距离定义为

$$
\overline { { E D } } ( X , Y ) = { \frac { E D ( X , Y ) } { \sqrt { n } } } = { \sqrt { \frac { 1 } { n } \sum _ { i = 1 } ^ { n } ( x _ { i } - y _ { i } ) ^ { 2 } } }
$$

定义5标准化动态时间规整距离。给定两时间序列 $\mathrm { \Delta } \mathrm { X }$ 和 $\mathrm { \Delta Y }$ ，设 $\mathtt { m } \le \mathtt { n }$ ，标准化DTW距离定义为

$$
\overline { { D T W } } ( X , Y ) { = } \frac { \mathrm { D T W } ( \mathrm { X } , \mathrm { Y } ) } { 2 \mathrm { n } }
$$

# 1.2时间序列在线查询空间相似组

MONEX算法的核心是建立时间序列在线查询空间相似组。首先证明ED与DTW之间存在三角不等式，从而能够利用ED距离构建一个紧凑型的空间；然后在这种紧凑空间上处理基于DTW距离进行查询。

时间序列查询空间相似组，简称相似组，是由候选数据集D中特定长度的子序列根据它们之间的相似性关系组成的。由于候选数据集D数据量巨大，所以将候选序列只按特定长度切分而不是切分成所有可能的子序列。该特定长度根据数据集的大小按一定比例选取，长度记为length。

定义6代表序列。给定查询空间相似组S，则集合 S中序列的逐点平均值被定义为S的代表，记做，即对于所有的 $X _ { \scriptscriptstyle p } \left[ i , j \right] \in S , R _ { k } ^ { i } = a \nu g X _ { \scriptscriptstyle p } \left[ i , j \right]$ 。

定义7查询空间相似组。将数据集D中长度为length的子序列 $X _ { { \scriptscriptstyle p } } [ i , j ]$ 放入集合T中，假设这些属于T的子序列被分别放在具有它们各自代表 $R _ { k } ^ { i }$ 的相似组里，使所有子序列处在某一个查询空间相似组里，这个组记为 $G _ { k } ^ { i }$ 。查询空间相似组需要满足以下两个条件：

a）任意子序列 $X _ { { \scriptscriptstyle p } } [ i , j ]$ 与其代表 $R _ { k } ^ { i }$ 的欧氏距离小于或等于相似性阈值 ST的一半，即ED(x,[ij],R)≤T， $\exists \mathrm { i } \in [ 1 , \mathrm { n } ]$ ，$\forall \mathbf { j } \in \left[ \mathsf { l } , \mathsf { n - i } \right]$ ， $\forall \mathbf { p } \in [ 1 , \mathbf { n } ]$ 。

b）任意子序列 $X _ { { \scriptscriptstyle p } } [ i , j ]$ 与其代表 $R _ { k } ^ { i }$ 的欧氏距离小于或等于 $X _ { { \scriptscriptstyle p } } [ i , j ]$ 与其他代表 $R _ { k } ^ { i }$ 的欧氏距离，即$\begin{array} { r } { \mathrm { E D } \big ( X _ { p } \left[ i , j \right] , R _ { k } ^ { i } \big ) \leq \mathrm { E D } \big ( X _ { p } \left[ i , j \right] , R _ { l } ^ { i } \big ) } \end{array}$ ，其中 $\exists \mathrm { i } \in [ 1 , \mathrm { n } ]$ ， $\forall j \in \left[ 1 , \mathrm { n - i } \right]$ ，$\forall \mathbf { p } \in [ 1 , \mathbf { n } ]$ ， $\forall \mathrm { l } \in \left[ 1 , \mathrm { g } \right]$ ， $\mathbf { g }$ 表示代表的个数。

引理1对于相同查询空间相似组 $G _ { k } ^ { i }$ 中两个子序列X和Y，其标准化欧氏距离总是小于或等于阈值，即 $\overline { { E D } } ( X , Y ) \leq S \mathrm { T }$ ，其中X， $\mathbf { Y } \in G _ { k } ^ { i }$ 。

证明给出同一查询空间相似组中的两个长度相等的序列 $\mathbf { X } = \left( x _ { i } , . . . . x _ { j } \right)$ 和 $\mathbf { Y } = \left( y _ { i } , . . . . y _ { j } \right)$ ，以及这个组的代表 $\mathbf { R } = \left( r _ { i } , . . . r _ { j } \right)$ 6根据定义7可知， $\overline { { E D } } ( X , R ) \leq \frac { S T } { 2 }$ 且 $\overline { { E D } } ( Y , R ) \leq \frac { S T } { 2 }$ ，带入到定义4中可得

$$
\begin{array} { l } { \displaystyle \sqrt { \sum _ { k = i } ^ { j } \left( x _ { k } - r _ { k } \right) ^ { 2 } } \le \frac { S T } { 2 } } \\ { \displaystyle \sqrt { \sum _ { k = i } ^ { j } \left( y _ { k } - r _ { k } \right) ^ { 2 } } \le \frac { S T } { 2 } } \end{array}
$$

想要证明 $\overline { { E D } } ( X , Y ) \leq S \mathrm { T }$ ，只需证明 $\sqrt { \sum _ { k = i } ^ { j } ( x _ { k } - y _ { k } ) ^ { 2 } } \leq S T$ 。对式（3）和（4）两边同时平方可知

$$
E D ^ { 2 } \left( \mathrm { X } , \mathrm { R } \right) = \sum _ { k = i } ^ { j } { \left( x _ { k } - r _ { k } \right) } ^ { 2 } \leq { \frac { S T ^ { 4 } } { 4 } }
$$

$$
E D ^ { 2 } \left( \mathbf { Y } , \mathbf { R } \right) = \sum _ { k = i } ^ { j } { \left( y _ { k } - r _ { k } \right) } ^ { 2 } \leq { \frac { S T ^ { 4 } } { 4 } }
$$

因为 $x _ { k } - y _ { k }$ 可以表示为 $x _ { k } - r _ { k } + r _ { k } - y _ { k } = ( x _ { k } - r _ { k } ) + ( r _ { k } - y _ { k } )$ ，所以利用柯西一施瓦茨不等式可以得到$( x _ { k } - y _ { k } ) ^ { 2 } \leq 2 { \bigl ( } x _ { k } - r _ { k } { \bigr ) } ^ { 2 } + 2 { \bigl ( } r _ { k } - y _ { k } { \bigr ) } ^ { 2 }$ 。将这个结论与定义4和式（3）和（4）结合可得

$$
\sum _ { k = i } ^ { j } { \left( x _ { k } - y _ { k } \right) } ^ { 2 } \leq 2 \sum _ { k = i } ^ { j } { \left( x _ { k } - r _ { k } \right) } ^ { 2 } + 2 \sum _ { k = i } ^ { j } { \left( y _ { k } - r _ { k } \right) } ^ { 2 } = S T ^ { 2 }
$$

因此可以证明 $\overline { { E D } } ( X , Y ) \leq S \mathrm { T }$ 成立。

定义8代表空间。给定数据集 $\mathrm { ~ D ~ }$ 中，每个查询空间相似组 $G _ { k } ^ { i }$ 对应的代表 $R _ { k } ^ { i }$ 以及相关子序列 $X _ { \scriptscriptstyle p } \left[ i , j \right]$ 所组成的空间，

称为代表空间，记为R-space。

# 1.3基于ED-DTW三角不等式的时间规整检索

本文的时间序列在线查询系统框架是基于ED 与DTW距离之间的三角不等式关系建立的。由这个关系可知，若查询序列seq与查询空间相似组的代表序列相似，则这个序列seq与该组中所有的子序列都相似，确保了查询能够在压缩后的R-space 空间上进行，而不是在整个数据集上对查询序列进行比较，从而提高查询效率。换言之，如果查询序列和代表 $R _ { k } ^ { i }$ 之间的标准化DTW距离小于或等于相似性阈值的一半，那么该相似组中的所有子序列与该查询序列都相似，并且查询序列与相似组中的所有子序列的标准化DTW距离都小于或等于相似性阈值。

引理2给定 $Y ^ { \prime } { = } ( y _ { 1 } ^ { * } , . . . , y _ { n } ^ { * } )$ 为任意相似组中的任意子序列，$Y = ( y _ { 1 } , . . . , y _ { n } )$ 为该组的代表序列， $\scriptstyle \mathbf { X = } ( x _ { 1 } , \ldots , x _ { m } )$ 为查询序列，则可推出：若存在 $\overline { { E D } } ( Y , Y ^ { \prime } ) { \leq } \frac { S T } { 2 }$ 且 $\overline { { D T W } } ( X , Y ) \leq \frac { S T } { 2 }$ 则$\overline { { \mathrm { D T W } } } ( X , Y ^ { \prime } ) \leq S T$ 。

证明 由定义3和引理1可得

$$
\mathrm { E D } ( \mathrm { Y } , Y ^ { \prime } ) = \sqrt { \sum _ { i = 1 } ^ { n } ( y _ { i } - y _ { i } ^ { \prime } ) ^ { 2 } } \leq \sqrt { n } \frac { S T } { 2 }
$$

两边平方可得

$$
\mathrm { E D } ^ { 2 } \left( \mathrm { Y } , Y ^ { \prime } \right) = \sum _ { i = 1 } ^ { n } \left( y _ { i } - y _ { i } ^ { \cdot } \right) ^ { 2 } \leq n { \frac { S T ^ { 2 } } { 4 } }
$$

因为DTW 距离在求解过程中需要构造矩阵，所以现需构造矩阵 $\mathbf { M } ( \mathrm { X } , \mathrm { Y } )$ 和 $\mathbf { M } ( \mathbf { \mathrm { X } } , \mathbf { \mathrm { Y } } ^ { \cdot } )$ 。因为在矩阵M(X,Y)中弯曲路径 $\mathrm { ~ \bf ~ P ~ }$ 是从点（1,1）至点 ${ \bf \left( n , n \right) }$ ，那么相应的DTW权重最多为2nT $2 \mathrm { n } { \frac { S T } { 2 } } = n S T$ ，所以现在只需要证明在矩阵 ${ \bf { M } } ( { \bf { X } } , { \bf { Y } } ^ { \mathrm { ~ \tiny ~ { ~ \cdot ~ } ~ } }$ 中从点（1,1）至点（n,n）的弯曲路径的DTW 权重最多为 $2 \mathrm { n S T }$ 。在矩阵 $\mathbf { M } ( \mathrm { X } , \mathrm { Y } )$ 中，给定弯曲路径 $P = ( p _ { 1 } , p _ { 2 } , . . . , p _ { t } , . . . , p _ { T } )$ ，$n { \leq } \mathrm { T } { \leq } 2 \mathrm { n } - 1$ ， ${ p } _ { 1 } = ( 1 , 1 )$ ， ${ p _ { T } } = \left( n , n \right)$ ， $p _ { t } = \left( i _ { t } , j _ { t } \right)$ 。由引理2的已知条件可知， $\sqrt { \sum _ { t = 1 } ^ { T } \bigl ( x _ { i _ { t } } - y _ { i _ { t } } \bigr ) ^ { 2 } } \leq 2 \mathrm { n } \frac { S T } { 2 } = n S T$ ，将公式两边平方可得

$$
\sum _ { \mathrm { t = 1 } } ^ { T } ( x _ { i _ { t } } - y _ { i _ { t } } ) ^ { 2 } \leq n ^ { 2 } S T ^ { 2 }
$$

因为 $x _ { i } - y _ { i } ^ { \prime }$ 可以表示为 $x _ { i } - y _ { i } + y _ { i } - y _ { i } ^ { \prime } = ( x _ { i } - y _ { i } ) + ( y _ { i } - y _ { i } ^ { \prime } )$ ，所以利用柯西一施瓦茨不等式可以得到$( x _ { i } - y _ { i } ^ { \prime } ) ^ { 2 } \leq 2 { \big ( } x _ { i } - y _ { i } { \big ) } ^ { 2 } + 2 { \big ( } y _ { i } - y _ { i } ^ { \prime } { \big ) } ^ { 2 }$ ，则

$$
\sum _ { \mathfrak { t } = 1 } ^ { T } ( x _ { i _ { \mathfrak { t } } } - y _ { \mathfrak { i } _ { \mathfrak { t } } } ^ { \cdot } ) ^ { 2 } \leq 2 \sum _ { \mathfrak { t } = 1 } ^ { T } ( x _ { i _ { \mathfrak { t } } } - y _ { \mathfrak { i } _ { \mathfrak { t } } } ) ^ { 2 } + 2 \sum _ { \mathfrak { t } = 1 } ^ { T } ( y _ { i _ { \mathfrak { t } } } - y _ { \mathfrak { i } _ { \mathfrak { t } } } ^ { \cdot } ) ^ { 2 }
$$

代入式（10）和（9）可得

$$
\sum _ { \mathrm { t = 1 } } ^ { T } ( x _ { i _ { t } } - y _ { \dot { i } _ { t } } ^ { \cdot } ) ^ { 2 } \leq 2 n ^ { 2 } S T ^ { 2 } + \frac { 2 n ^ { 2 } S T ^ { 2 } } { 4 } = \frac { 5 } { 2 } n ^ { 2 } S T ^ { 2 }
$$

因为 n'ST²恒小于等于2n'ST²，所以不等式成立，即$\overline { { \mathrm { D T W } } } ( X , Y ^ { \prime } ) \leq S T$ 成立。

# 2 MONEX算法

# 2.1算法思想

MONEX算法从构建查询空间相似组，计算代表距离以及连接子序列这三个步骤执行一次完整查询。具体步骤如下：

a)将候选序列按照长度length切分成所有可能的子序列，根据这些子序列之间的相似关系形成查询空间相似组，

与此同时计算出每个查询空间相似组的代表并将这些代表存入代表空间R-space之中。将查询序列也按长度length切分成小段时间序列。

b）将上述的小段时间序列与每组代表序列做DTW查询，得到与每段时间序列子段最相似的代表序列以及对应的查询空间相似组。

c）将上述步骤所得的查询空间相似组按照对应的小段时间序列的顺序排列，查找这些相似组中的子序列是否可以按顺序拼接成连续的序列，若可以拼接则拼接起来。

# 2.2查询空间相似组构建算法

查询空间相似组构建算法是为了寻找长度为length 的子序列所在的相似组，然后获得每组相应的代表。

a)将数据集D中现有时间序列分解成长度为length的所有子序列。为去除连续数据所产生的偏差，使用RANDOMIZE-IN-PLACE方法对子序列进行随机排序。

b)将重新排序后的子序列集合中的第一个子序列指定为第一组的成员，并将其指定为第一组的代表。重新排序后选择的代表可以确保相似组不受所提供子序列顺序的影响而产生偏差。

c)将余下的子序列与先前的代表进行比较，即计算两者之间的欧氏距离，选择具有最小欧氏距离的一组，再观察其欧氏距离是否满足小于或等于相似性阈值一半的条件。若条件全部符合，则将该子序列放入目前的查询空间相似组中；否则将其放在新的组中，并被指定为新组的代表。然后重复该步骤，直到所有的子序列都放入到对应的查询空间相似组中。

算法1查询空间相似组构建算法

Input：数据集D，相似性阈值ST，特定长度i。  
Output：代表{R},相似组{G}。  
Begin  
$\{ { \bf G } \} = \mathcal { O } , \{ { \bf R } \} = \mathcal { O }$   
随机化子序列  
$\{ { \sf X } \} =$ 特定长度i下的所有子序列  
minSM=0，mink $_ { : = 0 }$ ，members[] $\scriptstyle = \varnothing$   
for $X _ { p } \in X$ doif $G = { \mathcal { O } }$ ）then$G  G _ { \mathrm { 1 } }$ $G _ { k } \gets X _ { \rho } \left[ i , j \right]$ （2 /\*子序列长度为i,起始位置为 $\mathbf { j } ^ { * } \boldsymbol { / }$ $G _ { k } . m e m b e r s \gets [ i , j ]$ /\*将组内子序列的下标计入到 members  
数组中 $^ { * } /$ $R \gets X _ { p } \left[ i , j \right]$ （204号elsefor $\scriptstyle \mathbf { k } = 1$ to Representative.count do$\mathsf { m i n S M } = \mathsf { E D } ( \mathsf { R } , \ X _ { p } \left[ i , j \right] )$ mink $\scriptstyle : = 1$ Representative indexif( $\operatorname* { m i n } S M \le S T / 2$ ）then$G _ { m i n k }  X _ { \mathit { p } } [ i , j ]$ （204号$G _ { m i n k } . m e m b e r s = [ i , j ]$ update $R _ { m i n k }$ （204else$\begin{array} { l } { G  G _ { K + 1 } } \\ { R _ { k + 1 }  X _ { p } [ i , j ] } \end{array}$

End

算法的复杂性是衡量算法好坏的重要指标，具有较高复杂度的算法无法适应于对大型数据的处理。由所给数据可知，本文提出的查询空间相似组的复杂度为 $\mathrm { O } ( \mathrm { n } l ^ { 2 } \mathrm { g } )$ ，其中： $\mathfrak { n }$ 代

表数据集中时间序列的数量； $\mathbf { \xi } _ { l }$ 代表被分解成的子序列个数；  
g代表查询空间相似组个数。

通常情况下，初始的时间序列都具有固定长度，而且在分组过程中还要将这些序列进行切分，所以时间序列长度这个量不能看做是无穷大量。序列个数n随着数据集的大小而增减，而且通常情况下，n比 $\mathbf { \xi } _ { l }$ 大很多。因此可以将i看做关于n的常数。此时的复杂度可概括为O(ng)。

g的大小可以用概率来论证。假设在某个时刻有 $\mathbf { k }$ 个相似组，并且有一条新加入的时间序列X，那么新的分组有 $( \mathbf { k } { + } 1$ ）种可能，序列X或者属于 $\mathbf { k }$ 个组之中的一个序列或者是新建立的第（ $\mathbf { k } { + } \mathbf { l }$ ）组中的序列。假设这些事件发生的概率是相等的，那么序列X在新的相似组中的概率是 k+1。那么新建一个相似组的期望是几何分布，值为 ${ \frac { 1 } { p } } = k$ 。因此， $\sum _ { k = 1 } ^ { g } { \bigl ( } k + 1 { \bigr ) } = n$ ，则变量g对应的复杂度为 $\mathrm { o } { \big ( } { \sqrt { n } } { \big ) }$ ，所以算法整体的复杂度为（204号 ${ \bf O } \big ( \mathrm { { n } } ^ { 3 / 2 } \big )$ □

# 2.3多相似性参数设置

如 2.2节所述，本文的代表空间是由特定的阈值和特定长度的子序列构建而成。然而每个分析师对相似程度的要求不尽相同，需要调节阈值 ST 和子序列的特定长度length 来制定符合它们要求的查询空间相似组。

定义9代表距离。在R-space 中，每两个代表 $R _ { k } ^ { i }$ 和 $G _ { k } ^ { i }$ 之间的欧氏距离定义为代表距离 $D _ { c }$ ，即 $D _ { c k l } ^ { \ i } = E D { \left( R _ { k } ^ { i } , R _ { l } ^ { i } \right) }$ 。

定义10相似空间。SP-Space 是一个概念上的空间，在其对应的规模下，子序列长度为特定长度length，相似性阈值为ST。

基于相似性阈值可以为每个特定长度的子序列集合建立相应的相似空间。一般来说，如果 $S T ^ { \prime } \ge S T + D _ { C }$ ,两个相似组就会合并成一个新的相似组。现有两个指标SThalf和STfinal，在长度为length的情况下，当计算出的相似组有一半合并成新的相似组时，则阈值记为SThalf;当全部的相似组合并时，此时阈值记为STfinal。例如，现有特定长度i，SThalf=0.5，STfinal $\scriptstyle 1 = 0 . 7 8$ ，也就是说，长度为i的子序列组成的所有相似组中，当新阈值等于0.5时表明相似组有一半合并了，当新阈值等于0.78或者更高时则表明全部合并了。为完成长子序列的查询，将候选序列分解成所有长度的子序列并不现实，这里将特定长度length 设为10、20、50、80 和100 五种。根据长度length的不同，分别计算出对应的SThalf和STfinal。根据SThalf和STfinal这两个参数将相似等级划分如下：

a）“严格”等级，ST<SThalf;  
b）“中间”等级，SThalf $\mathbf { \sigma } \leq \mathbf { S } \mathbf { T } \leq \mathbf { S } ^ { \prime }$ Tfinal;  
c）“模糊”等级， $\mathrm { S T > }$ STfinal。

根据参数相似等级，以本文使用数据为例，如果分析师要求给出子序列长度为i的"严格"等级的相似性阈值范围的推荐，则推荐值在[0.0.6]内。分析师在此区间内选择的任何值都会返回“严格”相似性的结果。

在该区间中选择较低的值则会导致每个查询空间相似组中的子序列有更"严格"的相似性。

算法2不同参数阈值求解

Input：相似性阈值 $S T ^ { \prime }$ ，代表距离 $D _ { c }$ 。

Output：查询空间相似组 $\{ G ^ { \prime } \}$ 。

Begin

if $S T ^ { \prime } = = 5 \intercal$ then

$G ^ { \prime } { = } G$ else if $S T ^ { \prime } < 5 \mathsf { T }$ then split groups G else if $S T ^ { \prime } < D _ { c }$ then merge pair of groups with this condition else if $S T ^ { \prime } \ge D _ { c }$ then if $S T ^ { \prime } - S T \geq D _ { c }$ then merge groups with this condition else if $S T ^ { \prime } < D _ { c }$ then $G ^ { \prime } { = } G$ （204号 end

# 2.4基于查询空间相似组的查询过程

本文所研究的查询属于用户驱动的查询类型，即分析师通过提供目标查询序列进行查询。这种查询分为两种类型：

a)查询系统会返回与用户提供的查询序列最相似的时间序列，并且长度也与查询序列相同。例如，用户希望在特定的时间段内查询与苹果股票波动类似的股票，这种情况下，查询序列是数据集中存在的序列。

b)用户可以自己设计所需要的股票波动，并查询数据集中该序列的最佳匹配，这样的序列可能不存在于数据集中，而是查询出的最接近的序列。通常情况下，第一种情形的查询较多。

在查询长子序列时，为了提高算法效率，MONEX算法提出将查询序列切分成等长的查询序列子段，即把长序列分割成若干个短序列进行查询，然后再将查询到的短序列拼接成与原序列长度相等或相近的序列。下面根据算法要求，对时间序列子段进行定义。

定义11时间序列子段。将查询序列切分成 $\mathrm { ~ m ~ }$ 个长度为的l时间序列子段，表示为 $X _ { \boldsymbol { q } } \left[ m \right]$ ，其中 $1 \leq \mathbf { m } \leq { \frac { n } { l } }$ ，且 $\mathrm { ~ m ~ }$ 为正整数， $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 为查询序列长度。

如1.2节所介绍，查询空间相似组是基于ED所形成的紧凑序列组，查询系统则在相似组上应用时间规整策略进行查询。具体步骤如下：

a)将查询序列按照特定长度length切分成查询序列子段，最后小于长度length的子段可以忽略不计。

b)在组间进行查找，计算出每一个时间序列子段与每组代表之间的DTW距离，记为dist。选出每一子段对应的最小dist 按顺序存入 $b e s t _ { n u m }$ 数组中，并获取该组的序号 $G _ { n u m k }$ 和代表序号 $R _ { n u m k }$ 。

c）判断第numk组中的子序列是否能与 $\mathrm { \ n u m k } { + } 1$ 组中的子序列拼接起来，找到前后组中能够拼接成查询序列长度的子序列。

d)找出上述拼接起来的序列其每段子序列与该子序列所在组的代表之间的欧氏距离（这个距离在构建相似组时已经计算过，只需通过子序列的标号即可获取)，选取欧氏距离最小的一条序列作为最终查询结果。

算法3查询处理器

Input：查询序列Q,特定长度length,数组members。Output：拼接完成的序列 $\{ { \sf x } \}$ 。  
Begin  
$\{ \times \} = \mathcal { O }$ ， $\scriptstyle { \mathfrak { m } } = { \mathfrak { n } } / { \dot { \mathbf { 1 } } }$ ，numk $\scriptstyle = \varnothing$   
$X _ { q } = \{ Q _ { 1 } , Q _ { 2 } \ldots Q _ { m } \}$   
（204号 $/ { ^ * }$ 查询序列按照特定长度i切分成查询序列子段\*/for $\scriptstyle { \mathsf { q } } = 1$ to m do

$d i s t _ { k } = D T W \big ( \mathrm { \nabla } X _ { q } , G _ { k } . R _ { k } \big )$ /\*计算每一个 $X _ { q }$ 分别与每组的代表的DTW距离\*/numk=best distance index$b e s t _ { n u m k } \gets \operatorname* { m i n } { \{ d i s t _ { k } \} }$ （ /\*选出每一个 $X _ { q }$ 对应的最小距离\*/$R _ { n u m k } \gets R _ { k }$ $G _ { n u m k }  G _ { k }$ endfor $\scriptstyle \mathbf { k } = 1$ to m doif $( \ G _ { n u m k . } m e m b e r s . [ i , j + i ] \ \& \ G _ { n u m k + 1 } . m e m b e r s . [ i , j ] ) = 1 \ )$ $/ { * }$ 判断第numk 组中的 $X _ { { \scriptscriptstyle p } } [ i , j ]$ 与第numk $^ { + 1 }$ 组中的 $X _ { { \scriptscriptstyle p } } [ i , j ]$ 是否能拼接 $^ { * } /$ $\{ x \}  X _ { \mathit { p } } [ 2 i , j ]$ endend

# 3 实验结果及分析

本文在真实数据集上，从查询时间和准确率两个方面来评估MONEX算法的性能，并与已有的两种方法进行比较。a)使用标准的DTW距离对数据集中每条子序列与查询序列进行距离计算，然后找出距离最小的子序列，该算法能够确保计算出最佳的查询结果；b)ONEX[19]方法，该方法首先将序列切分成所有可能长度的子序列，然后用聚类算法分别将不同长度的子序列数据降维，最后在降维数据中进行查询，该方法在查询多维数据时有较好的效果。

实验环境为Visual2010,使用语言为 $\mathrm { C } { + } { + }$ ，实验在Inter(R)  
Corei5-34703.2GHz，4GB内存的Windows7操作系统上实  
现。本文从最大的公共时间序列集合UCRtimeseries  
collection中选取数据。选取的数据集有Face(four)、Symbols、  
MALLAT、ECG5000 和HandOutlines，数据点个数分别为  
8400、39800、56320、70000和 $1 \ 0 0 2 \ 3 3 0$ 。为了使查询效  
果更加准确，需要将每一条序列进行归一化。具体做法为：  
找出每一条序列中的最小值(min)和最大值(max)，对于任意  
一条序列 $\mathbf { X } = \left( { \boldsymbol { x } } _ { 1 } , { \boldsymbol { x } } _ { 2 } , . . . , \ { \boldsymbol { x } } _ { n } \right)$ ，将归一化的点 $x _ { i }$ 记为 $\frac { x _ { i } - m i n } { m a x - x _ { i } }$ 。

# 3.1 查询时间比对

本文利用标准DTW和ONEX算法与本文MONEX算法进行比对。测试将从不同规格候选序列数据集的查询时间和不同长度查询查询序列的查询时间两个方面进行。

在测试不同规格候选序列数据集的查询时间时，需要将查询20次的平均响应时间作为查询时间。此外，为了测试查询序列在数据集中和不在数据集中的查询效果，首先从候选数据集中截取10条不同长度的子序列，然后再从其他数据集中截取另外10条不同长度的子序列，最后将这20条子序列作为查询序列集。查询时间的计算共分两个步骤：a)将每条子序列进行5次查询，计算其平均时间作为一次查询的时间;b)记录将20条不同长度子序列进行查询的时间，并计算出平均时间作为该算法的查询时间。

MONEX算法的查询时间比标准DTW算法快很多，因此在图1中纵轴用对数来表示时间，而且时间的单位ms。如图1所示，本文提出的MONEX算法查询时间始终优于标准DTW查询算法几个数量级，并且比ONEX系统有更短的响应时间。可以看出，在数据集较小的情况下，ONEX与本系统的查询时间不相上下，但随着候选数据集的增大，查询时间的差异变得明显，本系统的平均查询速度比ONEX快10倍。

在测试查询查询序列的长度对查询效率的影响时，本文从HandOutlines数据集中截取20条长度由小到大的子序列作为查询序列集，子序列的长度范围在 20\~400间。将每条子序列进行5次查询，计算出平均时间作为该查询序列的查询时间。

1010 m

如图2所示，相同的候选数据集下，随着查询序列长度增加，子序列查询时间的差异变得明显，但MONEX算法的查询时间始终优于ONEX算法，并且查询序列越长，查询速度的优势越明显。

![](images/c7335921345096341ac47daf6a32488260d543e7ecb8d0f233adbc665504148f.jpg)  
  
Fig.1 Response time   
图2不同长度查询序列查询时间  
Fig.2Response time of sample sequences at different lengths

# 3.2 查询准确率比对

由于DTW的运算结果即为两序列间的最小距离，所以使用标准DTW距离作为评价标准。由此可知，MONEX算法准确率的评估即为考察查询所得的子序列与查询序列的距离度量结果对标准DTW距离的逼近程度。对此结合文献[21]中对于对比路径准确性的定义以及文献[7]中对查询准确率的定义，将MONEX算法准确率的计算定义为

$$
A c c u r a c y = [ 1 - a \nu e r a g e ( e r r ) ] ^ { * } 1 0 0 \%
$$

$$
\mathrm { a v e r a g e } ( \mathrm { e r r } ) = \frac { 1 } { n } \sum _ { i } ^ { n } \frac { a p p r D i s t - o p t i m D i s t } { o p t i m D i s t }
$$

式（14）中：optimDist为使用标准DTW算法返回的距离；apprDist为改进查询算法返回的距离。标准DTW算法返回的距离optimDist已是最相似序列间的距离，而改进的查询算法由于查询偏差将产生更大的距离值，因此近似距离apprDist恒大于optimDist，进而准确率accuracy 恒大于或等于0。查询准确率如表1所示，不同长度查询序列查询准确率如表2所示。

表1查询准确率  
  

<html><body><table><tr><td colspan="3">Table 1</td><td colspan="3">Queryaccuracy</td></tr><tr><td>准确率</td><td>Face</td><td>symbols</td><td>MALLAT</td><td>ECG5000</td><td>HandOutlines</td></tr><tr><td>MONEX</td><td>97.36</td><td>97.89</td><td>97.82</td><td>99.21</td><td>97.67</td></tr><tr><td>ONEX</td><td>97.77</td><td>97.64</td><td>97.78</td><td>99.48</td><td>97.15</td></tr></table></body></html>

Table 2 Query accuracy of different lengths sequences   

<html><body><table><tr><td>准确率</td><td>20</td><td>50</td><td>100</td><td>200</td><td>400</td></tr><tr><td>MONEX</td><td>97.06</td><td>97.34</td><td>97.75</td><td>98.03</td><td>97.93</td></tr><tr><td>ONEX</td><td>97.12</td><td>97.25</td><td>97.18</td><td>97.21</td><td>97.14</td></tr></table></body></html>

对于上述相似性查询，本节使用与3.1节相同的数据集进行查询。由于标准DTW距离算法将查询尽可能准确的结果作为目标，所以将它视为标准。由表1和2可知，本系统的准确率比ONEX系统平均高出 $0 . 0 3 \%$ ，虽然两者精度接近，但在查询长子序列时MONEX系统的准确率有着明显提升。

# 3.3 预处理评估

在本节中测试本系统在不同相似性阈值下预处理的时间消耗和空间占用情况。图3显示了在改变相似性阈值ST 的情况下，本系统离线构建查询空间相似组的时间。由图3可知，对于数值比较低的相似性阈值，其构建时间更长，因为要创建的分组更多。随着相似性阈值的增加，构建时间逐渐变小；当阈值增加到一定程度时，构建的时间将保持不变。也就是说，当阈值增加到一定值时，该长度下的所有子序列都已合并。

在不同相似性阈值下所形成的代表数量可以显示系统在预处理时生成信息的大小。如图4所示，相似性阈值越大，代表空间中存储的代表数越少。表3显示了在阈值为0.2的情况下，各种数据集中代表的个数、切分子序列的个数以及空间占用大小。

表3特定数据集下的代表数，子序列数及占用空间

表2不同长度查询序列查询准确率  
Table 3 Number of representatives under specific data set,number of subsequences and occupied space   

<html><body><table><tr><td>数据集</td><td>代表数</td><td>子序列数</td><td>空间占用/MB</td></tr><tr><td>Face(four)</td><td>13</td><td>7944</td><td>1.99</td></tr><tr><td>Symbols</td><td>24</td><td>37900</td><td>94.75</td></tr><tr><td>MALLAT</td><td>128</td><td>55275</td><td>138.19</td></tr><tr><td>ECG5000</td><td>67</td><td>60500</td><td>151.25</td></tr><tr><td>HandOutlines</td><td>623</td><td>995300</td><td>2488.25</td></tr></table></body></html>

![](images/22e80bb962e681ffe371a435fafa7a80f9bb378bec15facd01b1e3a6e72a4957.jpg)  
图3不同阈值大小下的分组时间

![](images/39efa8e5fbac8dcbfb6fda6a12501e8db1e0c409f0b2b2b3374fb7cd5651e048.jpg)  
Fig.3 Grouping time in different threshold sizes   
图4不同阈值大小下的分组个数Fig.4 Grouping numbers in different threshold sizes

# 4 结束语

本文提出了改进的时间序列在线查询算法MONEX，该方法是基于ONEX算法的改进算法。实验结果表明，随着候选数据集的增大，查询时间的差异变得明显，本系统的查询速度比ONEX快10倍，并且在相同的候选数据集下，随着查询序列长度增大，MONEX算法在查询时间上的优势也更加明显，与此同时查询的准确率比ONEX系统高出 $0 . 0 3 \%$ 。

目前查询的最相似子序列长度必须与查询序列保持一致，但在实际查询中，最相似的子序列的长度未必是与查询序列等长的，这可能影响查询的准确率，使查询具有局限性。在今后的工作中，可以改变查询序列的分割策略，使其能够应对不同长度的查询。

# 参考文献：

[1] Hinich,Melvin J. Time series analysis by state space methods [J]. Technometrics,2005,47(3): 373-373.   
[2]Eduardo JR,Vagelis H,Carlos C,et al.Correlating financial time series with micro-blogging activity [C]// Proc of the 5th ACM International Conference on Web Search and Data Mining.California: ACM Press,2012:513-522.   
[3] 范剑青，姚琦伟．非线性时间序列：建模、预报及应用[M].北京： 高等教育出版社,20o5:1-7.(Fan Jianqing,Yao qiwei.Nonlinear time series:modeling，forecasting and application [M].Beijing:Higher Education Press,2005:1-7.）   
[4]Stefan A,Athitsos V, Das G. The move-split-merge metric for time Series[J]. IEEE Trans on Knowledge and Data Engineering,2013,25 (6): 1425-1438.   
[5]Khatua M, Safavi S H,Cheung N M. Sparse laplacian component analysis for Internet traffic anomalies detection [J].IEEE Trans on Signal and Information Processing Over Networks,2018,PP (99): 1-1.   
[6]Fu W C,Keogh E, Lau L Y,et al. Scaling and time warping in time series querying [J]. Vldb Journal,2008,17 (4): 899-921.   
[7]Dau HA, Keogh E. Matrix profile V: a generic technique to incorporate domain knowledge into motif discovery [Cl// Proc of the 23rd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. New York: ACMPress,2017: 125-134.   
[8]Sharif M,Lujo B,Michael K.R.On the suitability of Lp-Norms for creating and preventing adversarial examples [C]// Proc of IEEE CVPRW. Salt Lake City: IEEE Press,2018:1686-16888.   
[9]Hui Y, Yufang W, Yuan G.Research on similarity mining for flight data [C]// Proc of the 2nd International Workshop on Education Technology and Computer Science.[S.1.]: IEEE Press,2010:150-153.   
[10] Khandelwal I,Satija U,Adhikari R.Efficient financial time series forecasting model using DWT decomposition [C]// Proc of IEEE CONECCT.[S.1.]: IEEE Press,2015: 1-5.   
[11] Wang Y,Wang P，Pei J，et al.A data-adaptive and dynamic segmentation index for whole matching on time series [J]. Very Large Database Endowment,2013,6 (10):793-804.   
[12] Cunningham JP,Yu B M.Dimensionality reduction for large-scale neural recordings [J]. Nature Neuroscience,2014,17(11): 1500-9.   
[13] Petitjean F,Forestier G,Webb G I,et al.Faster and more accurate classification oftime series by exploiting a novel dynamic time warping averaging algorithm.[J].Knowledge and Information Systems,2016, 47 (1): 1-26,.   
[14] Begum N,Ulanova L,Wang J，et al.Accelerating dynamic time Warping clustering with a novel admissible pruning strategy[C]//Proc of the 21th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining.[S.1.] :ACMPress,2015:49-58.   
[15] Neamtu R,Ahsan R,Rundensteiner E,et al. Interactive time series exploration powered by the marriage of similarity distances [J].Very Large Database Endowment,2016,10 (3):169-180.   
[16] FrancoisP,Forestier G,Webb GI,et al.Faster and more accurate classification of time series by exploiting a novel dynamic time warping averaging algorithm [J].Knowledge and Information Systems,2016,47 (1): 1-26.   
[17] AthitsosV,Papapetrou P,PotamiasM, et al. Approximate embedding-based subsequence matching of time series [C]//Proc of ACM SIGMOD.Athens:ACMPress,2008:365-378.   
[18] Neamtu R,Ahsan R,Rundensteiner E,et al.Interactive time series exploration powered by the marriage of similarity distances [J].Very Large Database Endowment,2016,10 (3):169-180.   
[19] Rakthanmanon T,Campana B,Mueen A,et al. Searching and mining trillions of time series subsequences under dynamic time warping [C]// Proc of the 18th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining.California:ACMPress,2012: 262-270.   
[20] Nagendar G,Jawahar C V.Efficient word image retrieval using fast DTW distance [C]// Proc of the 13th International Conference on Document Analysis and Recognition.Hyderabad:IEEE Press,2015: 876-880.   
[21] Moradi HR,Furuichi S,Minculete N.Estimates for tsalis relative operator entropy[J].Mathematical Inequalities and Applications,2017, 20 (4): 1079-1088.