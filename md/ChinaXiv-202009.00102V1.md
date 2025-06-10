# 基于混沌PSO的高维多视图数据IWKM聚类算法

陈高祥1,²，陈都鑫1

(1．东南大学 计算机科学与工程学院，南京 211189;2.江苏联合职业技术学院 苏州学院，江苏 苏州 215000)

摘要：针对传统聚类算法无法处理大数据中多视图高维数据问题，提出了一种基于混沌粒子群优化算法的智能加权K均值聚类算法。首先，在聚类模型中引入聚类之间的耦合程度以扩大聚类的相似性。其次，为了消除初始聚类中心的敏感性，利用混沌粒子群优化算法通过全局搜索得到最优初始聚类中心、视图权重和特征权重。然后，引入一种精确摄动策略提高混沌粒子群优化算法的寻优性能。最后通过在 apache spark 和 single node 两个平台上的实验验证了提出的方法在视图多、维数高的复杂数据集条件下具有较好的聚类性能。

关键词：大数据；K均值聚类；高维多视图数据；粒子群优化算法中图分类号：TP301.6 doi:10.19734/j.issn.1001-3695.2020.02.0045

IWKM clustering algorithm for high dimensional multi view data based on chaos PSO

Chen Gaoxiang1,², Chen Duxin1 (1.SchoolofComputer Science &Engineering,Southeast University,Nanjing Jiangsu211189,China;2.Suzhou College, Jiangsu United Vocational & Technical College,Suzhou Jiangsu 215oo0, China)

Abstract: Aiming atthe problemthattraditionalclustering algorithm can't deal with multi viewand high dimension data in bigdata,this paperproposedan intellgent weighted K-means clusteringalgorithmbasedonchaos particleswarm optimization algorithm.Firstly,itintroduced thecouplingdegree betweenclusters toxpandthesmilarityoflusters.Secondly,order to eliminate thesensitivityoftheinitial clustering center,itused chaosparticle swarmoptimizationalgorithmtoobtain the optimal nitialclustering center,viewweightand featureweightthrough global search.Then,it introducedanacurate perturbationstrategy to improve the performance ofchaosparticleswarm optimization.Finaly,experiments onApache spark and single node showthatthe proposed method hasbeter clustering performance under thecondition of complex data sets with multiple views and high dimensions.

Keywords: bigdata; K-means clustering; high-dimensional multi view data; particle swarm optimization algorithm

# 0 引言

当前，人工智能、移动互联网、社交网络和物联网生成大量数据，并推动大数据应用的快速发展[1,2]。在各种大数据应用中，都有许多高维多视图数据，高维多视图数据通常以各种来源获得的多个特征空间和不同结构进行描述[3]。传统聚类方法将所有视图作为一个统一的变量集，对此类具有数量、种类、速度、准确性和价值等多视图的数据聚类效果较差[4]。在大数据环境下，如何实现高维多视图数据的聚类以适应各种复杂的、大规模的应用是最具挑战性的问题之一[5]。

由于大数据的广泛应用，多视图数据的聚类吸引了许多研究人员的关注。文献[6将多视图任务的非监督特征选择保留在集群结构中，然后提出一种交替算法来实现该结构。对于多视图聚类问题，文献[7]提出了一种新颖的多视图关联传播算法，该算法特别适合于对两个以上的视图进行聚类。在文献[8]中，提出了局部自适应聚类(local adaptive clusteringLAC)算法，该算法为每个聚类的每个特征分配权重，通过使用迭代算法最小化其目标函数。文献[9]等提出了一种多视图数据的自动两级变量加权K均值(two-variablesweightedK-means,TWKM)聚类算法，该算法可以同时计算视图和单个变量的权重，但是很容易导致在单个特征和单个视图上具有较大权重的聚类，因此权重的分布不平衡。然而，上述算法主要关注于具有视图方式关系的问题，而忽略了数据集高维特征的重要性，使得聚类结果与实际应用存在较大差异，此外，上述方法由于聚类性能的限制对大数据应用中更复杂的高维数据的聚类效果较差。

为了解决实际大数据应用中的高维多视图数据聚类问题，并且进一步提升该聚类算法的聚类性能，提出了一种基于混沌粒子群优化算法(chaos particle swarmoptimization,CPSO)的智能加权K均值(intelligentweightedK-means,IWKM)聚类算法。

# 1 相关理论

# 1.1加权K均值聚类算法

集群是数据对象的集合，这些数据对象在同一集群中彼此相似，但与其他集群中的对象不同[10]。给定数据对象集$\mathbf { X } = [ x _ { i , j } ] _ { N * D }$ ， $N$ 是数据对象的数量， $D$ 是数据对象的维度。也就是说，数据对象具有 $D$ 个特征。聚类问题试图找到X的 $k$ 分区。簇的中心是 $\boldsymbol { Z } = [ z _ { k , j } ] _ { C ^ { * } D }$ 。 $\pmb { U } = [ u _ { i , k } ] _ { N * C }$ ，模糊除法矩阵，描述对象是某些集群的隶属度。

作为具有敏感初始聚类中心的聚类算法，K均值被广泛用于实际应用中，例如图像分割和数据挖掘[11,12]。K均值的目标是找到一个分区，以最小化带簇的平方和。在聚类过程中，用以下式子解决样本划分任务：

$$
\begin{array} { r l } & { \displaystyle \mathrm { F } ( \pmb { U } , \pmb { Z } ) = \sum _ { k = 1 } ^ { C } \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { D } u _ { i , k } \left( x _ { i , j } - z _ { k , j } \right) ^ { 2 } } \\ & { \mathrm { ~ } s . t . \displaystyle \sum _ { k = 1 } ^ { C } u _ { i , k } = 1 , 1 \leq i \leq N , u _ { i , k } \in \{ 0 , 1 \} } \end{array}
$$

其中： $\boldsymbol { \mathbf { \mathit { v } } }$ 被定义为分区矩阵， $u _ { i , k }$ 是一个二进制变量。

$\pmb { Z } = \{ \pmb { Z } _ { 1 } , \pmb { Z } _ { 2 } , . . . , \pmb { Z } _ { \mathrm { k } } \}$ 是一组向量，表示 $k$ 个簇的质心。 $\left( x _ { i , j } - z _ { k , j } \right) ^ { 2 }$ 是第 $i$ 个对象与第 $j$ 个变量上的第 $k$ 个簇的中心之间的距离度量。

在经典的K均值聚类算法中，所有特征均具有相同的权重，在诸如消费者细分之类的聚类问题中，所有特征均得到同等对待。实际上，在许多实际应用中，数据集中不同特征对聚类的影响是不同的，因此有必要为不同特征分配不同的权重。K均值类型聚类中的自动变量加权是加权K均值聚类算法，目标函数为

$$
\operatorname { F } ( U , Z , W F ) = \sum _ { k = 1 } ^ { C } \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { D } u _ { i , k } w f _ { j } ^ { \beta } \left( x _ { i , j } - z _ { k , j } \right) ^ { 2 }
$$

$$
s . t . \sum _ { k = 1 } ^ { c } u _ { i , k } = 1 , \ u , u _ { i , k } \in \{ 0 , 1 \} \quad \sum _ { j = 1 } ^ { D } w f _ { j } = 1 , 0 \leq w f _ { j } \leq 1
$$

其中， $\pmb { U }$ 被定义为 $n \times k$ 分区矩阵。 $W F$ 是特征的权重。

# 1.2软子空间聚类算法

软子空间聚类算法根据维度在发现相应聚类中的作用来确定维度的子集。维度的贡献是通过在聚类过程中分配给维度的权重来衡量的。在文献[13]中提出了一种软子空间聚类算法，目标函数的建模为

$$
\begin{array} { l } { { \displaystyle { \mathrm { F } ( U , Z , W C F ) = \sum _ { k = 1 } ^ { C } \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { D } u _ { i , k } w c f _ { k , j } ^ { \beta } \left( x _ { i , j } - z _ { k , j } \right) ^ { 2 } } } } \\ { { \displaystyle s . t . \sum _ { k = 1 } ^ { C } u _ { i , k } = 1 , 1 \leq i \leq N , u _ { i , k } \in \left\{ 0 , 1 \right\} , } } \\ { { \displaystyle \sum _ { j = 1 } ^ { D } w c f _ { k , j } = 1 , 0 \leq w c f _ { k , j } \leq 1 } } \end{array}
$$

其中WCF是每个集群中每个属性的权重。

# 2 IWKM算法

# 2.1高维多视图数据的聚类模式

用于将 $\mathrm { ~  ~ { ~ \cal ~ X ~ } ~ }$ 划分为具有视图和特征权重的集群的聚类建模为以下目标函数的最小化。

$$
\begin{array} { l } { { \mathrm { ~ \operatorname* { m i n } ~ } \mathrm { ~ F i n s s } ( X , Z , W , W , W ) = } } \\  { \frac { C } { { \sum _ { i = 1 } ^ { C } \sum _ { i = 1 } ^ { D } \sum _ { j = 1 } ^ { T } \sum _ { j = 1 } ^ { D } \omega _ { i , i , k } w _ { i , j } w _ { j , \left( i , i , j - z _ { i , j } \right) } ^ { \dag } } } } \\ { { \sum _ { i = 1 } ^ { C } \sum _ { j = 1 } ^ { T } \sum _ { j > \operatorname* { m i n } , w \forall i , j } w _ { j , \left( z _ { i , k } - \cdot \cdot \right. , \cdot \right. , \cdot } ) ^ { 2 } } } \\ { { \left. \left( \begin{array} { l } { { C } } \\ { { \sum _ { i = 1 , k } ^ { C } - 1 , 1 \leq i \leq N , u _ { i , k } \leq [ 0 , 1 ] } } \\ { { \sum _ { i = 1 } ^ { D } w _ { i } = 1 , 0 \leq w _ { i , p _ { i } } \leq 1 } } \\ { { \omega _ { i , k } + 1 , 0 \leq w _ { i , p _ { i } } \leq 1 , 0 \leq i \leq T } } \\ { { \omega _ { i , k } \leq 1 } } \end{array} \right) } } \\ { { \left( \begin{array} { l } { { S } } \\ { { \sum _ { i = 1 } ^ { D } w _ { i , k } = 1 , 0 \leq w _ { i , p _ { i } } \leq 1 , 0 \leq i \leq T } } \\ { { \omega _ { i , k } ^ { \prime } = 1 , 0 \leq w _ { i , p _ { i } } \leq 1 , 0 \leq i \leq T } } \\ { { \omega _ { i , k } ^ { \prime } = 1 , 2 \leq i , \omega _ { i , p _ { i } } \leq 1 } } \end{array} \right) } } \end{array}
$$

其中 $\pmb { U } = [ u _ { i , k } ] _ { N \times C }$ 是一个 $N { \times } C$ 分区矩阵，其元素 $u _ { i , k }$ 为二进制，其中 $u _ { i , k } = 1$ 表示对象 $i$ 已分配给集群 $k$ 。 $\pmb { Z } = [ z _ { k , j } ] _ { C \times D }$ 是一个$N { \times } C$ 矩阵，其元素 $z _ { k , j }$ 表示簇 $k$ 的第 $j$ 个特征。 $W V = \left[ w \nu _ { \scriptscriptstyle t } \right] _ { T }$ 是$T$ 视图的权重。 $W F = [ w f _ { j } ] _ { j } \in \mathrm { V i e w } _ { t }$ 是视图 $\textit { t }$ 下的特征权重。$w \nu _ { t } w f _ { j } \left( x _ { i , j } - z _ { k , j } \right) ^ { 2 }$ 是第 $i$ 个对象与第 $k$ 个簇的中心之间的第 $j$ 个特征的加权距离度量。 $w \nu _ { t } w f _ { j } \left( z _ { k , j } - o _ { j } \right) ^ { 2 }$ 是第 $k$ 个聚类与平均聚类中心之间的第 $j$ 个特征的加权距离度量， $o _ { j }$ 是 $c$ 个聚类的平均聚类中心。该值描述集群之间的耦合程度，越大表示相异性越大。

# 2.2 CPSO 和粒子编码

在IWKM中，提出了CPSO以帮助算法获得更好的初始聚类中心、视图权重和特征权重。每个粒子 $i$ 代表 $D$ 维解空间中的候选解，它具有两个向量：位置向量 $X _ { i } = [ x _ { i } ^ { 1 } , x _ { i } ^ { 2 } , . . . , x _ { i } ^ { D } ]$ 和速度向量 $V _ { i } = [ \nu _ { i } ^ { 1 } , \nu _ { i } ^ { 2 } , . . . , \nu _ { i } ^ { D } ]$ 。在演化过程中，通过以下等式更新迭代 $t + 1$ 上维度为 $d$ 的粒子 $i$ 的速度矢量和位置矢量：

$$
\begin{array} { c } { { \nu _ { i } ^ { d } \left( t + 1 \right) = \omega { \nu } _ { i } ^ { d } \left( t \right) + c _ { 1 } r _ { 1 } \left( p B e s t _ { i } ^ { d } \left( t \right) - p _ { i } ^ { d } \left( t \right) \right) } } \\ { { + c _ { 2 } r _ { 2 } \left( g B e s t ^ { d } \left( t \right) - p _ { i } ^ { d } \left( t \right) \right) } } \\ { { x _ { i } ^ { d } \left( t + 1 \right) = x _ { i } ^ { d } \left( t \right) + { \nu } _ { i } ^ { d } \left( t + 1 \right) } } \end{array}
$$

其中 $d = 1 , 2$ ， $D$ 表示搜索空间的每个维度， $\omega$ 是惯性权重， $c _ { I }$ 和 $c _ { 2 }$ 分别是认知学习系数和社会学习系数， $r _ { 1 }$ 和 $r _ { 2 }$ 是在[0,1]范围内的两个均匀随机数， $p B e s t _ { i } ^ { d } ( t )$ 是在粒子 $i$ 的第 $t$ 次迭代之前找到的具有最佳适应度的维度 $\boldsymbol { d }$ 上的位置， $g B e s t ^ { d } \left( t \right)$ 是整个粒子群在维度 $\boldsymbol { d }$ 上找到的最佳位置。惯性权重 $\omega$ 通常更新为

$$
\omega = \omega _ { \mathrm { m a x } } - ( \omega _ { \mathrm { m a x } } - \omega _ { \mathrm { m i n } } ) \times g / \ : g _ { \mathrm { m a x } }
$$

其中 $\omega _ { \mathrm { m a x } }$ 和 $\omega _ { \mathrm { m i n } }$ 是初始权重和最终权重，分别设置为0.9和0.4。$g$ 是当前进化世代数， $g _ { \mathrm { m a x } }$ 是最大世代数，并设置为150。 $c _ { 1 }$ 和 $c _ { 2 }$ 分别设置为1.8。维度 $\textit { d }$ 上每个粒子的速度限制在$[ - \nu \operatorname* { m a x } ^ { d } , \nu \operatorname* { m a x } ^ { d } ]$ ， $\nu \operatorname* { m a x } ^ { d } \in R ^ { + }$ 。因此，如果速度 $\nu _ { i } ^ { d } \left( t \right)$ 超过 $\nu \mathrm { m a x } ^ { d }$ ，则将其重新分配给 $\nu \mathrm { m a x } ^ { d }$ 。否则，如果速度 $\nu _ { i } ^ { d } \left( t \right)$ 小于 $- \nu \operatorname* { m a x } ^ { d }$ ，则将其重新分配给-vmaxd。如果 $\nu \mathrm { m a x } ^ { d }$ 太大，粒子可能会错过良好的解决方案。另一方面，如果 $\nu \mathrm { m a x } ^ { d }$ 太小，粒子可能会陷入局部最优状态。通常将最大速度 $\nu \mathrm { m a x } ^ { d }$ 设置为搜索范围的$20 \%$ 。

粒子编码是使用粒子群搜索最佳解的前提[14]。在IWKM中，初始聚类中心、视图权重和特征权重被编码为粒子表示形式。每个粒子由 $F \times C + T + F$ 维实数向量编码。 $F$ 是聚类问题中对象的特征数。群中的第i个粒子被编码为

$$
\begin{array} { r } { \boldsymbol { X } _ { i } = \left[ \begin{array} { l } { x _ { i } ^ { 1 , 1 } , x _ { i } ^ { 1 , 2 } , . . . , x _ { i } ^ { 1 , F } , . . . , x _ { i } ^ { C , 1 } , x _ { i } ^ { C , 2 } , . . . , x _ { i } ^ { C , F } } \\ { w \nu _ { i } ^ { 1 } , . . . , w \nu _ { i } ^ { T } , w f _ { i } ^ { 1 } , . . . , w f _ { i } ^ { F } } \end{array} \right] } \end{array}
$$

$$
x { \big ( } t + 1 { \big ) } = r \cdot x { \big ( } t { \big ) } \cdot ( 1 - x ( t ) ) , r \in N , x ( 0 ) \in [ 0 , 1 ]
$$

$$
d ( p B e s t , g B e s t ) = \frac { 1 } { N _ { - } S } \sum _ { i = 1 } ^ { N _ { - } S } \sqrt { \sum _ { j = 1 } ^ { \dim } ( p B e s t _ { i j } , g B e s t _ { j } ) ^ { 2 } } \leq Q _ { - } d
$$

$$
s d ( p B e s t _ { j } ) =
$$

$$
\sqrt { \frac { 1 } { N _ { - } S } \sum _ { i = 1 } ^ { N _ { - } S } ( p B e s t _ { i j } - \frac { 1 } { N _ { - } S } ( p B e s t _ { 1 j } + p B e s t _ { 2 j } + \cdots + p B e s t _ { N , j } ) ) ^ { 2 } } \le Q _ { - } p B e s t _ { N _ { - } } ,
$$

$$
s d ( g B e s t _ { j } ) = \sqrt { \frac { 1 } { m - 1 } \sum _ { t = 1 } ^ { m - 1 } ( g B e s t _ { j } ( m ) - g B e s t _ { j } ( t ) ) ^ { 2 } } \leq Q _ { - } g B e s t
$$

# 2.3 精确扰动和CPSO

为了避免局部最优和过早收敛，利用跳跃或突变在丰富群体智能中粒子的搜索行为方面具有很大的优势[15]。在CPSO中，混沌逻辑序列扰动被用于帮助粒子脱离局部最优并获得更好的搜索质量，具有确定性、遍历性和随机性，将其定义为等式(9)，其中r是控制参数， $x$ 是变量， $\mathbf { r } = 4$ ，t =0,1,2,...。

可以将CPSO的精确扰动概括为以下过程的相互作用。

a）创建合适的扰动粒子：为了减少粒子搜索过程中总体稳定性的损害和CPU的计算负荷，通过简单的随机抽样方法从总共 $N _ { - } S$ 个粒子中随机选择 $N _ { - } S / K _ { - } s p a r k$ 个粒子作为扰动对象。 $K _ { - } s p a r k$ 是apache spark 中的工作程序节点数。

b）精确扰动时间：扰动的时间是粒子群过早收敛的时间。pBest和 $g B e s t$ 之间的平均距离用于判断粒子是否处于过早收敛状态，记,为等式(10)。其中， $N _ { - } S$ 和dim是群的粒子数和粒子的维度， $\scriptstyle Q _ { - } d$ 代表过早收敛的阈值。如果$d ( p B e s t , g B e s t ) \le Q _ { - } d$ ，则出现过早收敛和局部最优，然后应采用适合 $N _ { - } S / K _ { - } s p a r k$ 粒子的扰动。

c）精确扰动维度：由于粒子具有一个以上的维，因此根据惯性的优先级，优先选择一些具有较高惯性的维来进行扰动。第 $j$ 维中的pBest 和 $g B e s t$ 的惯性可以由均方差给出，分别记为等式(11)和(12)。其中 $N _ { - } S$ 和 $m$ 是群的粒子数和当前迭代数。如果 $s d ( p B e s t _ { j } ) \le Q _ { - } p B e s t$ 或 $s d ( g B e s t _ { j } ) \le Q \_ g B e s t$ ，则第 $j$ 维的 $p B e s t \ , g B e s t$ 是惰性的，需要进行扰动。其中 $\varrho _ { - } p B e s t$ 和$\boldsymbol { Q } _ { - } g B e s t$ 分别是pBest 和 $g B e s t$ 的惰性阈值。

# 2.4IWKM流程

IWKM算法的流程图如图1所示。

![](images/dfdf1f034a52678102bbb1424a74698c0ef4d18b786370cd844f04fc441fc657.jpg)  
图1IWKM算法流程图  
Fig.1Flowchart ofIWKMalgorithm

# 3 实验评估

# 3.1测试环境和 spark

在分布式和并行计算环境中，apache spark 是一个重要的开源集群计算框架，它为隐式数据并行和容错的整个集群编程提供了一个接口[16]。spark 的弹性分布式数据集(RDD)是分布式程序的工作集，可以提供受限形式的分布式共享内存。通常，由于重复的重新启动作业、大数据读取和改组，MapReduce作为有效的海量并行数据处理框架，不适合迭代算法。因此，本文选择了apache spark 作为大数据应用中IWKM的计算平台。在本文的实验中，对IWKM进行了测试，并在包括 apache spark 和 single node 在内的各种计算环境中进行了比较。Single node 配备了IntelCore i5-4210M2.6Hz，3.8GRAM和ubuntu14.04LTS操作系统。

Apache spark由一个主节点，配置为IntelCore i7-$3 8 2 0 @ 3 . 6 \mathrm { G H z }$ ，64GDDRIII和1T高效云磁盘，十个工作节点，相关配置为IntelXeonE5-2690@2.9GHz，16GDDRIII和 500G高效云磁盘，应用版本为apache spark1.6.0。

# 3.2测试数据集和评估指标

为了评估所提算法的性能，本文还通过RI，JC和Folk的评估指标，将IWKM与LAC，亲和传播(afinitypropagation,AP)[17]，归一化分割(normalized cut,Ncut)[11],密度聚类(density clustering,DC)[18]和TWKM进行了比较。为了公平比较，PSO和CPSO使用相同的人口规模30和相同的150个适应度值评估。IWKM和其他五种算法已在5个高维多视图数据集中进行了测试，其中包括多特征数据集，互联网广告数据集，Spambase 数据集，图像分割集和心电图数据集。这些数据集及其应用的基本信息如表1所示。

表1高维多视图数据集的特征  
Tab.1Characteristics of high dimensional multi view data sel   

<html><body><table><tr><td>序号</td><td>数据集</td><td>数据量</td><td>数据类别</td><td>数据特征视觉数目</td><td></td><td>单个类的大小</td></tr><tr><td>1</td><td>多特征</td><td>2000</td><td>10</td><td>649</td><td>6</td><td>(200,200...,200)</td></tr><tr><td>2</td><td>互联网广告</td><td>2359</td><td>2</td><td>1557</td><td>6</td><td>(381,1978)</td></tr><tr><td>3</td><td>Spambase</td><td>4601</td><td>2</td><td>57</td><td>3</td><td>(2788,1813)</td></tr></table></body></html>

<html><body><table><tr><td>4</td><td>图像分割</td><td>2310</td><td>7</td><td>19</td><td>2</td><td>(330,330...,.30)</td></tr><tr><td>5</td><td>心电图</td><td>2126</td><td>3</td><td>21</td><td>3</td><td>(1655,295,176)</td></tr></table></body></html>

多特征数据集是从荷兰实用程序图的集合中提取的手写数字数据集，其中包含 2000 个属于10类(0-9)的数字对象。每类有200个对象。每个对象均由649个特征表示，这些特征分为以下六个视图：a)Mfeat-fou视图包含76个字符形状的傅里叶系数；b)Mfeat-fac视图包含216个配置文件相关性;c)Mfeat-kar 视图包含64个Karhunen-Love 系数；d)Mfeat-pix视图包含240个像素窗口；e)Mfeat-zer视图包含47个Zernike时刻；fMfeat-mor视图包含6个形态特征。

互联网广告数据集包含来自各种网页的3279张图像，这些图像被分类为广告或非广告。有20张图片的值缺失。本文的实验在3259个实例上进行，删除了缺失值的实例。在六个视图中描述了实例。视图1包含3种图像几何形状(宽度，高度，长宽比)；视图2在包含图片的页面网址(基本网址)中包含457个词组；视图3包含495个图像URL的短语(图像URL)；视图4在图像所指向的页面的URL中包含472个短语(目标URL)；视图5包含111个锚文本；视图6包含19个图像的文本alt(替代)html标签(alt文本)。

Spambase数据集是一个数据集，其垃圾邮件的收集来自邮局主管和具有现场垃圾邮件的个人，非垃圾邮件的收集来自现场工作和个人电子邮件，其中包含4601个属于2类(垃圾邮件、非垃圾邮件)的对象。每个对象都由57个要素表示，这些要素分为三个视图，分别是单词频率视图，字符频率视图和大写游程视图。a）单词频率视图包含word类型的48个连续实数属性；b)字符频率视图包含char类型的6个连续实数属性；c)大写游程视图包含测量连续大写字母序列长度的3 个连续实数属性。

在该数据集中，从7张室外图像的数据库中随机抽取了2310个实例。手动分割图像以为每个像素创建一个分类。每个实例都是一个 $3 { \times } 3$ 的区域。数据集包含19个特征，可分为2个视图：形状视图包含9个有关形状信息的特征，而RGB视图包含10个有关颜色信息的特征。

自动处理 2126 例胎儿心电图(Cardiotocograms,CTG)并测量相应的诊断特征。CTG还由三位专家产科医生进行分类并为他们每个人分配了共识分类标签。分类既涉及形态学模式(A，B，C..)，也涉及胎儿状态(N，S，P)。因此，该数据集可用于10类或3类实验。在此实验中，将其用作3类数据集。在数据集中，可以将21个要素划分为3个视图：每秒指标，可变性视图和直方图视图。

# 3.3评估指标

由于已为本文的实验选择了五个数据集的真实分区，因此可以通过将所得聚类与外部结构按照外部标准进行比较来评估聚类算法的性能。一些常用的标准包括兰德指数(RandIndex,RI)，杰卡德系数(JaccardCoefficient,JC)和Folk(FowlkesRussel）。令 $\mathbf { C } = \{ \mathbf { C } _ { 1 } , \mathbf { C } _ { 2 } , \mathbf { C } _ { \mathrm { M } } \}$ 为数据集中的 $\mathbf { \Omega } _ { M }$ 个簇，$\mathbf { C } ^ { \prime } = \{ \mathbf { C } _ { 1 } ^ { \prime } , \mathbf { C } _ { 2 } ^ { \prime } , . . . . , \mathbf { C } _ { \mathrm { N } } ^ { \prime } \}$ 由聚类算法生成的 $N$ 个聚类的集合。给定数据集中的一对点 $\left( { { X } _ { i } } , { { X } _ { j } } \right)$ ，称为

SS 是一对数据点的数量，其中 $X _ { i } , X _ { j } \in \mathbf { C } _ { m }$ ， $X _ { i } , X _ { j } \in \mathbf { C } _ { n } ^ { \prime } , i \neq j$ 。$_ { D D }$ 是一对数据点的数量，其中$X _ { i } \in \mathbf { C } _ { m 1 } , X _ { j } \in \mathbf { C } _ { m 2 } , X _ { i } \in \mathbf { C } _ { n 1 } ^ { \prime } , X _ { j } \in \mathbf { C } _ { n 2 } ^ { \prime } , i \neq j , m 1 \neq m 2 , n 1 \neq n 2$ 。

$\boldsymbol { S D }$ 是一对数据点的数量，其中$X _ { i } , X _ { j } \in \mathbf { C } _ { m } , X _ { i } \in \mathbf { C } _ { n 1 } ^ { \prime } , X _ { j } \in \mathbf { C } _ { n 2 } ^ { \prime } , i \neq j , n 1 \neq n 2 ~ ,$ 。

$D S$ 是一对数据点的数量，其中$X _ { i } \in \mathbf { C } _ { m 1 } , X _ { j } \in \mathbf { C } _ { m 2 } , X _ { i } , X _ { j } \in \mathbf { C } _ { n } ^ { \prime } , i \neq j , m 1 \neq m 2$ 。

本文使用的三个外部标准可以定义如下：

$R I = ( S S + D D ) / \left( S S + S D + D S + D D \right)$ ,RI值越大，说明聚类结果与真实情况越吻合。

$J C = S S / \left( S S + S D + D S \right)$ ，该指标用于衡量两个数据的相似度，JC值越大，相似度越大，聚类精度越高。$F o l k = \sqrt { \frac { S S } { S S + S D } } \times \sqrt { \frac { S S } { S S + D S } }$ ，该指标用于评价聚类质量，Folk 值越大，说明聚类质量越高。

# 3.4参数分析

为了分析3个参数( $\scriptstyle Q _ { - } d$ ， $\boldsymbol { Q } _ { - } \boldsymbol { g } b e s t$ 和 $\boldsymbol { Q } _ { - } p B e s t$ )对高维多视图数据的聚类性能的影响，在singlenode上对3个数据集(Mfeat数据集，互联网广告数据集以及Spambase 数据集)中的IWKM进行了测试。为了减少统计错误，所有数据集均独立进行了10次模拟。

根据过早收敛的阈值，本文将 $\scriptstyle Q _ { - } d$ 在Mfeat和Spambase数据集中以5步长设置在[5，45]。将 $\scriptstyle Q _ { - } d$ 在互联网广告数据集中以3步长设置在[2，20]。关于它们的平均评价指标的统计结果如图2所示。从图2可以看出，当 $\scriptstyle Q _ { - } d$ 分别选择为25、8和30时，IWKM具有在singlenode上的3个数据集中进行聚类的最佳性能。参数 $\underline { { Q } } _ { - } g b e s t$ 和 $\boldsymbol { Q } _ { - } p B e s t$ 是维度惯性的阈值，用于测量每个维度中位置的可感知变化是否发生。三个数据集上的参数 $\boldsymbol { Q } _ { - } \boldsymbol { g } b e s t$ 和 $\boldsymbol { Q } _ { - } p B e s t$ 也与 $\scriptstyle Q _ { - } d$ 类似地进行分析。关于它们的平均评价指标的统计结果分别示于图3和图4。当参数 $\boldsymbol { Q } _ { - } g b e s t$ 设置为5,5.0E-5和5.0E-4，且参数 $\boldsymbol { Q } _ { - } p B e s t$ 设置为3.0E-6，3.0E-5和0.03，IWKM在 single node上的3个数据集中的聚类性能是最好的。由于在Spambase 中JC 和RI的值几乎相等，因此JC和RI的曲线重叠。因此，根据参数分析的结果，将选择最佳参数值 $\scriptstyle Q _ { - } d$ ， $\underline { { Q } } _ { - } g b e s t$ 和 $\boldsymbol { Q } _ { - } p B e s t$ 并在下一个实验中进行测试。

![](images/333f22f0ffeb8f12c9640a484e4582e88944a63e16a3e7c8b1d56e3cea14ca25.jpg)

![](images/2bc43d49765a76cc919eced296a3a30871e4cd6f8d96cb8d2041c39380e0e540.jpg)  
(a)多特征数据集

![](images/0c8c129e29f210111e295b435ffcd1b3ba0660a29654e1a4704358d1757737de.jpg)  
Fig.2Parameter change curve of $\scriptstyle Q _ { - } d$

![](images/2906176ff720a0df6b557675056d2d9602cd92cace26d27a88642f5fd866bdcb.jpg)  
图2参数 $\scriptstyle Q _ { - } d$ 变化曲线  
(c)Spambase 数据集

![](images/0129dbd742565716b6ccbff5d3559b1a76683aa725d6d847a4c9b3b66c22af5d.jpg)  
(a)多特征数据集

![](images/b99049c77982e8ebeb60236423fcd4584a31974a1c3559a8f514da44cf3d7f5e.jpg)  
Fig.3Parameter change curve of Q_gbest

![](images/51cafef698d84722783404ed375c3f645aeb125cbeeb30c81ddccad0b7077078.jpg)  
图3参数 $\boldsymbol { Q } _ { - } g b e s t$ 变化曲线  
图4参数Q_pbest变化曲线  
Fig.4Parameter change curve of Q_pbest

# 3.5 PSO 和 CPSO 的比较

为了验证CPSO在IWKM中聚类中心、视图权重和特征权重的优化，本文在singlenode上的三个高维多视图数据集中测试了CPSO和PSO。通过CPSO和PSO将数据集运行10次，图7记录并比较了各种算法的平均结果。在CPSO中，提出了一种精确的扰动，包括合适的扰动粒子、精确的扰动时间和扰动维数，以提高优化性能。从图7中可以看出，CPSO可以在singlenode上的所有三个高维多视图数据集中实现更好的解决方案精度，并尽早获得最佳解决方案。显然，CPSO在IWKM集群方面比PSO具有更好的性能。因此，本文可以得出结论，作为一种重要的优化方法，CPSO可以帮助IWKM在高维多视图数据中获得更好的初始聚类中心、视图

权重和特征权重。

# 3.6IWKM视图权重比较

为了进一步评估获得视图权重的性能，在五个不同的高维多视图数据集中测试了TWKM和IWKM。两个算法在数据集中运行了10次，并记录了IWKM和TWKM的平均结果并在表4中进行了比较。显然，IWKM和TWKM可以为5个高维多视图数据集获得有效权重。特别是，在互联网广告和图像分割这两个数据集中，TWKM和IWKM在获得视图权重方面具有相似的性能。但是，在apache spark和singlenode上，在其他3个数据集(Mfeat，Spambase 和心电图)中,IWKM可以获得比TWKM更好、更合理的视图权重。TWKM计算出的视图权重常常集中在一个视图上，这与现实应用不符。IWKM计算的权重比TWKM计算的权重更合理，并且特征的权重处于相同情况。因此，本文可以得出结论，在视图权重方面，IWKM比TWKM具有更好的性能。

利用CPSO进行优化得到六个聚类算法的最优参数值，如表2所示。为了进一步验证所提出算法在大数据应用中对高维多视图数据进行聚类的综合性能，在apachespark和single node两种不同的计算平台上，通过RI，JC和Folk的评估指标，在五个高维多视图数据集中将IWKM与其他五种算法进行了比较。

在实验中，视图数与特征数的乘积记录为 $\boldsymbol { p } _ { f \times \nu }$ ，用于描述高维多视图数据的复杂性。特征数越大，高维多视图数据越复杂。在表1中，根据 $p r o _ { f \times \nu }$ 的值，Mfeat的数据集(特征数：649，视图数：6， $p _ { f \times \nu } = 6 4 9 \times 6 = 3 8 9 4$ )、互联网广告数据集(特征数：1557，视图数：6， $p _ { f \times \nu } = 1 5 5 7 \times 6 = 9 3 4 2$ )比 Spambase 数据集(特征数：57，视图数：3， $p _ { f \times \nu } = 5 7 \times 3 = 1 7 1$ )、图像分割数据集(特征数：19，视图数：2， $p _ { f \times \nu } = 1 9 \times 2 = 3 8$ )、心电图数据集(特征数：21，视图数：3， $p _ { f \times \nu } = 2 1 \times 3 = 6 3$ )更复杂。

表3总结了IWKM与其他5种算法在apache spark 和single node上的综合比较。比较它们的平均结果(10 倍)和标准偏差以减少统计误差。从这些结果中，可以看到IWKM在Mfeat 数据集和互联网广告数据集中明显优于的其他五种算法。在Spambase 数据集中，IWKM的性能优于TWKM和DC，但AP在Mfeat数据集中的效果最差。在Mfeat数据集中，DC和IWKM均比LAC，AP，Ncut和TWKM更好。在互联网广告数据集中，AP,TWKM和IWKM的性能优于LAC,Ncut 和DC。LAC 明显优于 Spambase 数据集中的其他5种算法(包括IWKM)，但Spambase 数据集的复杂度低于Mfeat数据集和互联网广告数据集。因此，可以得出结论，在这些复杂的数据集中，IWKM在针对具有更多视图和更高维度数据集来说，例如多特征和互联网广告数据集，胜过其他五种算法。在心电图数据集中，IWKM优于其他的5种算法。但是，在图像分割中，Ncut和TWKM的性能要优于IWKM。由于心电图数据集比图像分割数据集更为复杂，因此高维多视图数据集越复杂，IWKM的性能越好。总之，IWKM可以更加有效地处理大数据应用中的高维多视图数据集的聚类。同时，在这些复杂的数据集中，IWKM优于其他五种算法。

![](images/ca7dcebfc1b2d2faee675071770aeedbaf9f36ab1b66f7f82a764660fbbf9eb5.jpg)  
图5PSO与CPSO 的比较  
Fig.5Comparison between PSO and CPSO

表2实验中六种聚类算法的参数值   
Tab.2Parameter values of six clustering algorithms in the experiment   
表3五种算法的比较  

<html><body><table><tr><td>算法</td><td>多特征</td><td>互联网广告</td><td>Spambase</td><td>图像分割</td><td>心电图</td></tr><tr><td>LAC(h)</td><td>2</td><td>2</td><td>14</td><td>2</td><td>5</td></tr><tr><td>AP(，p)</td><td>(0.9,2.7)</td><td>(0.9,60.0)</td><td>(0.9,12.0)</td><td>(0.9,-4.7)</td><td>(0.9,-24)</td></tr><tr><td>Ncut(e)</td><td>1.0E-8</td><td>1.0E-8</td><td>1.0E-8</td><td>1.0E-8</td><td>1.0E-8</td></tr><tr><td>DensityC(P）</td><td>1.6</td><td>1.4</td><td>1.9</td><td>1.7</td><td>1.5</td></tr><tr><td>TWKM(,n )</td><td>(30,7)</td><td>(80,25)</td><td>(53,18)</td><td>(70,40)</td><td>(40,18)</td></tr><tr><td>IWKM(Q_d,Q_gBest,Q_pBest）</td><td>(25.0,0.5,3.0E-6)</td><td>(8.0,5.0E-5,3.0E-5)</td><td>(30.0,5.0E-4,0.03)</td><td>(20.0,5.0,3.0E-5)</td><td>(20,5.0,3.0)</td></tr></table></body></html>

Tab.3Comparison of five algorithms   

<html><body><table><tr><td>数据集</td><td></td><td>LAC</td><td>AP</td><td>Ncut</td><td>DensityC</td><td>TWKM</td><td>IWKM</td></tr><tr><td rowspan="3">多特征</td><td>RI</td><td></td><td>0.9344 ±0.0000 0.8931 ±0.0000 0.9317 ±0.0065</td><td></td><td>0.9578 ±0.0000</td><td>0.9456 ±0.0000</td><td>0.9586 ±0.0118</td></tr><tr><td>JC</td><td></td><td></td><td>0.5365 ±0.0000 0.3510 ±0.0000 0.4959 ±0.0342</td><td>0.6720 ±0.0000</td><td>0.5937 ±0.0000</td><td>0.6820 ±0.0719</td></tr><tr><td>Folk</td><td></td><td></td><td>0.6988 ±0.0000 0.5226 ±0.0000 0.6625 ±0.0301</td><td>0.8060 ±0.0000</td><td>0.7467 ±0.0000</td><td>0.8116 ±0.0466</td></tr><tr><td rowspan="4">互联网广告</td><td>RI</td><td></td><td></td><td>0.7154±0.0000 0.8124±0.0000 0.6803 ±0.0016</td><td>0.6996 ±0.0000</td><td>0.8131 ±0.0000</td><td>0.8179 ±0.0132</td></tr><tr><td>JC</td><td></td><td>0.7055 ±0.0000 0.7785±0.0000</td><td>0.6151±0.0026</td><td>0.6974 ±0.0000</td><td>0.7792 ±0.0000</td><td>0.7858 ±0.0088</td></tr><tr><td>Folk</td><td></td><td></td><td>0.8322 ±0.0000 0.8759 ±0.0000 0.7646 ±0.0017</td><td>0.8293 ±0.0000</td><td>0.8764 ±0.0000</td><td>0.8809 ±0.0043</td></tr><tr><td>RI</td><td></td><td></td><td>0.7112 ±0.0000 0.5527 ±0.0000 0.5616 ±0.0000</td><td>0.5209 ±0.0000</td><td>0.5208 ±0.0000</td><td>0.5225 ±0.0003</td></tr><tr><td rowspan="3">Spambase</td><td>JC</td><td></td><td></td><td>0.5893 ±0.0000 0.4797 ±0.0000 0.4611 ±0.0000</td><td>0.5196 ±0.0000</td><td>0.5194 ±0.0000</td><td>0.5222 ±0.0002</td></tr><tr><td>Folk</td><td></td><td></td><td>0.7397 ±0.0000 0.6590 ±0.0000 0.6358 ±0.0000</td><td>0.7194 ±0.0000</td><td>0.7192 ±0.0000</td><td>0.7225 ±0.0003</td></tr><tr><td>JC</td><td></td><td></td><td>0.3252±0.0000 0.2254±0.0000 0.3038±0.0000</td><td>0.2573 ±0.0000</td><td>0.2996 ±0.0000</td><td>0.2297 ±0.0065</td></tr><tr><td rowspan="3">图像分割</td><td>RI</td><td></td><td></td><td>0.5319 ±0.0000 0.8110 ±0.0000 0.8974 ±0.0000</td><td>0.5388 ±0.0000</td><td>0.8252 ±0.0000</td><td>0.8047 ±0.0103</td></tr><tr><td>Folk</td><td></td><td></td><td>0.5055 ±0.0000 0.3682 ±0.0000 0.4706 ±0.0000</td><td>0.4115 ±0.0000</td><td>0.4645 ±0.0000</td><td>0.3750 ±0.0036</td></tr><tr><td>JC</td><td></td><td></td><td>0.3854±0.0000 0.3067 ±0.0000 0.1886 ±0.0000</td><td>0.3535 ±0.0000</td><td>0.3897 ±0.0000</td><td>0.3984 ±0.0000</td></tr><tr><td rowspan="2">心电图</td><td>RI</td><td></td><td>0.5408±0.0000 0.5034±0.0000 0.4346 ±0.0000</td><td></td><td>0.4617 ±0.0000</td><td>0.5086 ±0.0000</td><td>0.5576 ±0.0210</td></tr><tr><td>Folk</td><td></td><td>0.5705 ±0.0000 0.4885 ±0.0000 0.3721 ±0.0000</td><td></td><td>0.5262 ±0.0000</td><td>0.5656 ±0.0000</td><td>0.5854 ±0.0054</td></tr></table></body></html>

表4TWKM和IWKM计算的视图权重   
Tab.4View weights calculated by TWKMand IWKM   

<html><body><table><tr><td>TWKM特征权值</td><td>IWKM特征权值</td></tr><tr><td rowspan="7">多特征</td><td>1.66665E -6 0.23424</td></tr><tr><td>1.66665E-6 0.23358</td></tr><tr><td>1.66665E -6 0.25141</td></tr><tr><td>1.66665E-6 0.01263</td></tr><tr><td>1.66665E -6 0.09903</td></tr><tr><td>0.99999 0.16911</td></tr><tr><td>1.66665E -6 0.11030</td></tr><tr><td rowspan="4">0.20205 互联网广告</td><td>0.16166</td></tr><tr><td>0.21539 0.12580</td></tr><tr><td>0.19255 0.29347</td></tr><tr><td>0.30720</td></tr><tr><td rowspan="6">Spambase</td><td>0.16216 0.22784</td><td>0.00157</td></tr><tr><td></td><td></td></tr><tr><td>0.99999</td><td>0.58757</td></tr><tr><td>3.33331E-6 3.33331E-6</td><td>0.06495 0.34748</td></tr><tr><td>0.4684598</td><td></td></tr><tr><td>0.5315402</td><td>0.44744640 0.55255359</td></tr><tr><td rowspan="3">心电图</td><td>9.999933E-01</td><td>0.1592640</td></tr><tr><td>3.333311E-06</td><td>0.4687741</td></tr><tr><td>3.333311E-02</td><td>0.3719617</td></tr></table></body></html>

# 4 结束语

针对传统聚类算法无法处理大数据中多视图高维数据问题，提出了一种基于混沌粒子群优化算法的智能加权K均值聚类算法。通过实验证明了CPSO可以帮助IWKM在高维多视图数据中获得更好的初始聚类中心、视图权重和特征权重，为聚类精度的提升提供良好的初始值要求。另外提出方法能够有效实现多视图高维数据的聚类，且针对视图越多、维数越高、数据越复杂的数据集越能够体现该算法的优越性。但是本文方法由于数据来源问题，只应用了五类数据，对方法的验证效果还需要更多类别的数据进行验证，需要进一步研究。

# 参考文献：

[1]臧艳辉，赵雪章，席运江.Spark框架下利用分布式NBC的大数据文 本分类方法[J].计算机应用研究，2019,36(12): $3 7 0 5 - 3 7 0 8 + 3 7 1 2$ # (Zang Yanhui, Zhao Xuezhang， Xi Yunjiang. Large datatext classification using distributed NBC in spark framework [J].Computer application research,2019,36 (12):3705-3708+3712.)   
[2]邹劲松，李芳．大数据下的分布式精确模糊 KNN 分类算法[J].计 算机应用研究，2019,36(12):3701-3704.(Zou Jinsong,Li Fang. Distributed accurate fuzzy KNN classification algorithm under big data [J].Computer application research,2019,36 (12):3701-3704.)   
[3]张贝娜，冯震华，张丰，等．基于时空多视图BP神经网络的城市空 气质量数据补全方法研究[J].浙江大学学报（理学版），2019,46 (06):737-744.(Zhang Beina,Feng Zhenhua, Zhang Feng,et al. Study on the method of urban air quality data completion based on spatiotemporal multi view BP neural network [J]. Journal of Zhejiang University (SCIENCE EDITION),2019,46(06):737-744.)   
[4]Shi Hong,Li Yan,Han Yang，et al,Cluster structure preserving unsupervised feature selection for multi-view tasks,Neurocomputing 175 (2016) 686-697.   
[5]张天真．基于非负矩阵分解的多视图聚类方法研究[D]．西安电子 科技大 学，2018.(Zhang Nai．Multi view clustering based on nonnegative matrix decomposition [D].Xi'an University of Electronic k-means clustering algorithm for image segmentation, Opt.-Int. J.Light Electron Opt. 2018,126 (24): 4817-4822.   
[7] 洪敏，贾彩燕，李亚芳，等．样本加权的多视图聚类算法[J].计算 机研究与发展,2019,56(08):1677-1685.(Hong Min,Jia Caiyan,Li Yafang,et al. Sample weighted multi view clustering algorithm [J]. Computer research and development,2019,56 (08): 1677-1685.)   
[8]梁丹，于海燕，范九伦，等.核空间局部自适应模糊C-均值聚类图 像分割算法 [J].微电子学与计算机,2019,36(02):21-25.(Liang Dan, Yu Haiyan,fan Jiulun,et al. Kernel space local adaptive fuzzy c-means clustering image segmentation algorithm [J]. Microelectronicsand computer,2019,36 (02): 21-25.)   
[9] Chen Xu, Xu Xuan, Huang Jiazhi, et al. Tw-k-means: automated twolevel variable weighting clustering algorithm for multiview data, IEEE Trans.Knowl. Data Eng.2016,28 (4): 932-944.   
[10] Kumar D,Bezdek J,Palaniswami M,et al,A hybrid approach to clustering in big data,IEEE Trans.Cybern.2016,46 (10): 2372-2385.   
[11]王杰，陈彬，袁鹏，等．数据驱动的最优互惠避碰模型偏好速度研究 [J]．系统仿真学报,2019,31(12):2731-2739.(Wang Jie:Chen Bin, Yuan Peng,et al. Study on data-driven orca preference velocity [J]. Journal of System Simulation,2019,31 (12): 2731-2739.)   
[12]倪龙强，张丽华，姚新涛，等．一种基于粗糙集证据理论深度融合的 局部冲突快速合成方法[J].兵工学报,2019,40(12):2560-2569.(Ni Longqiang, Zhang Lihua,Yao Xintao,et al.A fast synthesis method of local conflicts based on deep fusion of rough set evidence theory [J]. Journal of military engineering,2019,40 (12): 2560-2569.)   
[13]范虹，侯存存，朱艳春，等．烟花算法优化的软子空间MR图像聚类 算法[J].软件学报,2017,28(11):3080-3093.(Fan Hong,Hou Cuncun, Zhu Yanchun,et al. Soft subspace MR image clustering algorithm optimized by fireworks algorithm[J].Journal of software,2017,28 (11): 3080-3093.)   
[14]王彩云，黄盼盼，李晓飞，等．基于AEPSO-SVM算法的雷达HRRP 目标识别[J]．系统工程与电子技术,2019,41(09):1984-1989.(Wang Caiyun, Huang Panpan,Li Xiaofei, et al. Radar HRRP target recognition based on aepso-svm algorithm [J]. System engineering and electronic technology,2019,41(09): 1984-1989.)   
[15]刘久富，丁晓彬，郑锐，等．混沌量子粒子群的权重类条件贝叶斯网 络分类器参数学习[J]．系统工程与电子技术,2019,41(10):2304- 2309.(Liu Jiufu,Ding Xiaobin, Zheng Rui,et al. Parameter learning of Bayesian network classifier with weight class condition of Chaos Quantum Particle Swarm [J]. System engineering and electronic technology,2019,41 (10): 2304-2309.)   
[16] Tang Zi,Liu Min,Ammar A,et al. An optimized mapreduce workflow scheduling algorithm for heterogeneous computing, J. Supercomput. 2016,72 (6): 2059-2079.   
[17]陈云芳，夏涛，张伟，等．基于亲和传播的动态社会网络影响力扩散 模型[J].通信学报,2016,37(10):40-47.(Chen Yunfang,Xia Tao, Zhang Wei,et al. Dynamic social network influence difusion model based on affinity Communication [J]. Journal of communications, 2016, 37 (10): 40-47)   
[18]陈宸，叶波，邓为权，等．基于 SLIC 超像素算法和密度聚类的 TA2 钛板表面缺陷定量化评估研究[J]．电子测量与仪器学报,2019,33 (11): 128-135.(Chen Chen, Ye Bo,Deng Weiquan,et al. Quantitative evaluation of surface defects of TA2 titanium plate based on SLIC superpixel algorithm and density clustering [J].Journal of electronic measurement and instrumentation,2019,33 (11): 128-135.)