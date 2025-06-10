# 基于Spark并行的密度峰值聚类算法

孙伟鹏1，吴锡生‘，孟斌²

(1.江南大学 物联网工程学院，江苏 无锡 214122;2.中船重工集团第七O二研究所 软件工程中心，江苏 无锡214082)

摘要：针对FSDP聚类算法在计算数据对象的局部密度与最小距离时，由于需要遍历整个数据集而导致算法的整体时间复杂度较高的问题，提出了一种基于 Spark 的并行FSDP聚类算法 SFSDP。首先，算法通过空间网格划分将待聚类数据集划分成多个数据量相对均衡的数据分区；然后，利用改进的FSDP聚类算法并行地对各个分区内的数据执行聚类分析；最后，通过将分区间的局部簇集合并，生成全局簇集。实验结果表明，SFSDP与FSDP算法相比能够有效地进行大规模数据集的聚类分析工作，并且算法在准确性和扩展性方面都有很好的表现。

关键词：聚类；密度峰值；空间划分；并行；Spark 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2018.04.0377

# Spark-based parallel density clustering algorithm

Sun Weipeng1,Wu Xishengl,MengBin² (1.SchoolofIoTEngineeing,Jiangnan University,Wuxi Jiangsu 214122，China;2.SoftwareEngineeing Center,Cina Shipbuilding Group No.702 Institute,Wuxi Jiangsu 214082,China)

Abstract:InviewoftheproblemthattheoveraltimecomplexityoftheFSDPclusteringalgorithmishighbecause thealgorithm needs to traversethe entire data set whencalculating thelocaldensityandminimum distanceofdataobjects,this paper presents aSpark-based parallelFSDPclustering algorithmcaled SFSDP.First,thealgorithm divides the dataset intomultiple data partitions withrelativelyequal sizebyspatialmeshing;then,theclusteringanalysis isperformedonthedata ineachpartitionin parallelusing theimprovedFSDPclusteringalgorithm; Globalclustersare generatedby grouping togetherlocalclustersetween partitions.Experimental results show that SFSDP algorithmcan efectively perform large-scale dataset clustering analysis compared with FSDP algorithm,and the algorithm has a good performance in terms of accuracy and scalability.

Key words:clustering; density peak;space division; parallel; Spark

# 0 引言

随着互联网在全球范围内的快速普及，人们每天都会面对来自社会、商业、医学、工程和科学以及人们日常生活各个方面的海量数据。数据的爆炸式增长、广泛可用和巨大规模把本文带入了一个真正的数据时代。而如何快速方便地从这些杂乱无章的大规模数据中挖掘出有用的信息，并将这些非结构化的数据转变成知识，这种需求催生了数据挖掘的诞生[1]。在数据挖掘领域中，聚类分析作为一种常用的数据分析方法，可以在对数据对象集的相关信息一无所知的情况下，将数据对象集合划分成多个簇，使得同一个簇中的对象彼此相似，但与其他簇中的对象不相似[2]。迄今为止，国内外众多研究学者针对各类应用场景已经提出了各式各样的聚类算法[3]，使得聚类分析的研究得到了很大的发展。在现实生活中，聚类分析早已经被广泛应用于多个领域中，包括网页搜索、决策分析、图像模式识别、文档摘要自动生成、自然语言处理、商务智能、生物学与安全等。

FSDP(clustering by fast search and find of density peaks)作为一种新的基于密度的聚类算法[4]，该算法将具有较大局部密度且互相距离较远的数据对象作为聚类中心，然后将每一个非中心数据对象沿着密度递增的最近邻方向迭代划分给相应的聚类中心，实现聚类划分。该算法被提出后得到了大量研究学者的关注与研究[5\~8]。虽然FSDP算法具有算法原理简单、可以发现任意形状、大小的聚簇等优点，但该算法在面对数据量比较大或数据维度比较高的聚类任务时，由于FSDP 算法在计算数据集中数据对象的局部密度和最小距离的时间复杂度较高，聚类的效率相对较低，所以算法不能很好地适用于大规模数据的聚类。

针对FSDP聚类算法在进行海量、高维度数据聚类时存在效率低、伸缩性差的问题，本文提出了一种基于Spark的并行FSDP聚类算法SFSDP。该算法首先通过将海量数据集在空间中划分成多个数据量均衡的数据分区，然后将划分好的数据分区分发到集群中的计算节点上进行单独聚类，最后将局部聚类的结果合并生成全局聚簇集。实验结果表明，SFSDP与FSDP算法相比，算法在保证准确率的前提下，具备较强的可扩展性，能够有效处理大规模数据集的聚类分析工作。

# 1 相关工作

# 1.1FSDP 聚类算法

FSDP算法认为聚类的中心应该同时具备以下两个特点：a）聚类中心相对于包围它的数据对象密度要大，即聚类中心被局部密度较低的邻居包围；b)聚类中心与任何具有更高局部密度对象之间的距离较远。对于数据集中每个数据点，需要计算数据点的局部密度 $\rho _ { i }$ 和距离具有更高局部密度数据点的最小距离 $\delta _ { i }$ （下文简称为最小距离 $\delta _ { i }$ ）两个变量。其中局部密度 $\rho _ { i }$ 定义如式（1）所示。

$$
\rho _ { i } = \sum _ { j } e ^ { - \left( d _ { i j } / d _ { c } \right) ^ { 2 } }
$$

其中： $d _ { i j }$ 表示数据点 $i$ 与 $j$ 间的距离； $d _ { c }$ 表示截断距离。

最小距离 $\delta _ { i }$ 表示的是数据点 $i$ 与任何其他具有更高局部密度数据点之间的最小距离，其定义如式（2）所示。

$$
\delta _ { i } = \left\{ \begin{array} { l l } { \displaystyle \operatorname* { m i n } _ { j : \rho _ { j } > \rho _ { i } } \big ( d _ { i j } \big ) , i \geq 1 } \\ { \displaystyle \operatorname* { m a x } _ { j } \big ( d _ { i j } \big ) , \rho _ { i } = \operatorname* { m a x } ( \rho ) } \end{array} \right.
$$

通过计算数据集中的所有数据点的局部密度 $\rho _ { i }$ 和最小距离 $\delta _ { i }$ ，可得到数据集对应的 $\left( \rho _ { i } , \delta _ { i } \right)$ 分布。然后将该分布在平面坐标中画出，即可得到数据集对应的决策图。算法只需在图中选取同时具备较大 $\rho$ 和 $\delta$ 的数据点作为聚类中心，然后将剩余的数据点归类到它邻近有更高局部密度的数据点所属的簇即可完成数据集聚类。

# 1.2 Spark 分布式框架

Spark[9,10]是由UC Berkeley AMPLab 研发的一个快速而通用的并行计算框架。作为大数据时代最为主要的几个数据计算分析框架之一，Spark 为大数据分析应用提供了一个统一的数据处理平台，在这个平台下包含多个紧密集成的组件。其主要包含内核(spark core)部分和多个官方子模块(Spark SQL、Sparkstreaming、MLlib、GraphX)

Spark具有高扩展和高容错等优点，并已经被广泛用于各种生成环境中。与Hadoop一样，Spark也是为集群计算而设计的。但不同的是，Spark可以把执行的中间结果缓存到内存中，这种方式可以大大提高算法的执行效率，因此，Spark能够更好地适用于需要多次进行迭代的算法。并且与其他类似并行计算框架相比，Spark不仅在运行速度和通用性能方面有很大的优势，而且在可扩展性和容错性方面也有较好的表现。

# 2 问题描述和相关定义

问题描述：

给定一组待聚类数据集，其所处的d维空间区域DS称为数据集D的数据空间（data space）。其中 $p _ { i }$ 表示d维空间中的数据对象，为数据对象 $p _ { i }$ 在第 $\mathbf { k }$ 维数轴上的投影。可通过SFSDP聚类算法得到一组聚簇集。

SFSDP聚类算法的实现基于如下相关定义：

定义1空间网格、网格单元。将数据空间DS划分为多个互不重叠的区域，由这些区域构成的网格划分称为空间网格，记为G。其中每个子区域为空间网格的一个网格单元，记为 $\mathbf { g } _ { \mathsf { } }$

图1描述了基于二维数据空间DS的划分。其中，实线外边框围绕的大矩形代表数据空间DS；实线内边框围绕的小矩形分别表示由DS 划分的g1、g2、g3、g4网格单元。

定义2相邻网格单元。如果两个网格单元g1和g2所表示的空间区域在第i维是相邻区域，而在其他d-1维是同一区域，则g1和g2 称为相邻网格单元。

定义3内部点。网格单元区域内的数据点称为内部点。

定义4临界点、临界区域。在网格单元区域内且与网格单元任意边界之间的距离小于密度截距 $\sigma$ （见定义6）的点称做临界点，临界点也属于内部点。涵盖临界点的区域称为临界区域。

定义5扩展点、扩展区域。在网格单元区域以外且与网格单元任意边界之间的距离小于密度截距 $\sigma$ 的点称为扩展点。涵盖扩展点的区域称为扩展区域。

定义6改进的 $\rho _ { i }$ 计算公式、密度截距 $\sigma$ 、密度截距邻域)。由高斯函数的数学性质[1可知，在计算数据对象的 $\rho _ { i }$ 时，对于给定的截断距离 $d _ { c }$ ，当一个样本点距离指定数据点的距离大于$3 d _ { c } / \sqrt { 2 }$ 时，则该样本点对指定数据点局部密度的计算影响非常小。这也就是说，每个数据点的局部密度主要取决于与其距离小于 ${ 3 d _ { c } } / { \sqrt { 2 } }$ 的近邻数据点。因此，在计算数据点局部密度时，可以只通过计算距离数据点 $3 d _ { c } / \sqrt { 2 }$ 范围内的邻近点来近似表示该数据点的局部密度。改进后数据点的局部密度计算公式如式（3）所示。

$$
\rho _ { i } = \sum _ { { d _ { i j } \leq \sigma } } e ^ { - \left( { d _ { i j } \mathord { \left/ { \vphantom { d _ { i j } \left( d _ { c } \right) } } \right. \kern - delimiterspace } d _ { c } } \right) ^ { 2 } }
$$

其中： $\sigma { = } 3 d _ { c } / \sqrt { 2 }$ ， $\sigma$ 称为密度截距。距离数据对象小于 $\sigma$ 的范围称为数据对象的密度截距邻域。

数据空间网格划分如图1所示。由图1可知，对数据空间进行划分后，数据对象局部密度的计算只需要考虑数据对象所在网格单元内以及其相邻网格单元内的数据对象，有效避免了计算局部密度时需要遍历整个数据集的问题，大大降低了计算节点的工作负荷。

# 3 SFSDP算法设计与实现

FSDP算法在进行数据对象局部密度和最小距离计算时需要遍历数据集中的所有数据对象，所以在进行大规模数据聚类时，如果只采用单节点处理，则节点的计算量会很大，导致算法的效率很低。本文提出的SFSDP聚类算法通过将大规模数据的聚类任务分解为若干可通过单节点处理的小规模任务来完成聚类，大大提高了数据集聚类的速度。SFSDP算法的执行可分为三个阶段：

阶段1数据分区。根据数据集D在数据空间DS中的分布情况，通过空间划分将数据集D划分成若干规模较小且包含数据量大致均匀的数据分区。

阶段2局部聚类。各个计算节点在本地分区数据上执行改进的FSDP聚类算法，得到局部聚类结果。

阶段3局部簇合并。通过对局部聚类结果合并与调整，生成全局聚簇集。

![](images/80b645ccbfa7d34eccd35f262d8471ac999f759e95b26fe850b6a8b47e3e573b.jpg)  
图1数据空间网格划分

# 3.1数据分区

为了避免数据对象局部密度的计算需要遍历整个数据集，定义6给出了一种新的局部密度计算方法。改进后数据对象局部密度的计算只与数据空间中以该数据对象为中心、密度截距为半径范围内的数据对象有关，而与数据空间中其他的数据对象无关。因此，SFSDP算法可通过将数据空间划分成空间网格，这样在计算数据对象局部密度时，只需考虑所处网格单元内和相邻网格单元内的数据对象，大大降低了算法的时间复杂度。在进行空间网格划分时，为了使得各个计算节点间负载均衡，防止数据倾斜现象的发生，SFSDP算法采用基于网格单元内数据对象数目的划分策略，利用KD-Tree[12]将数据空间划分成多个包含数据对象数目相对均衡的网格单元。

在对数据集分区时，对于划分完成后网格单元内的临界点，由于其密度截距邻域范围内的一部分邻近数据点与其不在同一个网格单元内，为了计算这些临界点的局部密度，在进行数据分区时，需要将一些数据对象同时分配给多个不同的分区。从图1可以看出，如果网格单元g1对应的分区P仅包含g1内的数据对象，由于临界点q的密度截距邻域内包含了网格单元 g2中的数据对象，导致 $\mathsf { q }$ 的局部密度计算出错，所以对于与网格单元g1相对应的分区P，需要将相邻网格单元g2内的一些数据对象也包含在分区P中。为了能更好地给出数据分区的完整定义，使用 $\mathsf { p } \in \mathsf { P }$ 和 $\mathfrak { p } { \ll } \mathfrak { g }$ 来分别表示数据对象p属于数据分区

P 和数据对象p包含在网格单元g中。

定义7网格单元的扩展o空间。令g表示由数据空间DS通过空间网格划分得到的一个网格单元，将g各个维度的边界在空间中向外扩充密度截距 $\sigma$ 大小的距离得到的空间区域称为网格单元g对应的扩展 $\sigma$ 空间，记为 $\mathtt { g } \mathrm { + } \mathtt { \sigma }$ 。

由定义5和7可以看出，网格单元的扩展 $\sigma$ 空间即为网格单元包含的区域加上扩展区域。在图1中，由虚线围成的小矩形分别对应网格单元的扩充空间。

定义8数据分区。令 $\mathbf { g } { + } \sigma$ 表示由数据空间 DS 通过空间网格划分得到的网格单元 $\mathrm { \bf ~ g }$ 的扩展 $\sigma$ 空间，则$P = \left\{ p | p \in D \land p \prec g + \sigma \right\}$ 称为网格单元 $\mathrm { \bf ~ g }$ 对应的数据分区；相反， $\mathbf { g }$ 称为数据分区P对应的网格单元。

由定义8对数据分区的定义得知，一个数据分区包含了数据集中分布在对应网格单元扩展o空间区域内的所有数据对象。此时，对于分区内的数据对象p，如果 $\mathfrak { p }$ 包含在分区对应的网格单元内，则可以通过定义6给出的公式计算出数据对象p的局部密度估计。

数据分区算法实现：

输入：D为数据集；max为网格单元内最大数据对象数目。

输出：Partitions为数据集划分后得到的数据分区。

1．通过数据集D得到数据空间DS。  
2．将数据空间DS 划分成若干个大小相等且互不重叠的网格单元。  
3．将数据对象映射到网格单元，并计算每个网格单元内数据对象的个数。  
4．初始化一个待分割空间队列Queue,并将DS 添加到队列中。  
5．初始化一个空的网格单元集合G。  
6．弹出待分割空间队列中的队首空间区域 S。  
7．计算数据空间区域S内包含的数据对象数目n。如果n小于max，则将S添加到集合G中；否则，求得空间区域S内的数据对象在d维空间中各个维度的方差，选取方差最大的维度作为分割维度，将S划分成两个包含数据量均衡的子空间区域S1、S2，并将S1和S2添加到待分割空间队列中  
8．如果队列Queue为空，则将G作为数据集D的空间网格划分；否则跳转到步骤6。  
9．根据划分好的空间网格G，由定义8得到数据集的数据分区

# 3.2 分区内局部聚类

在数据集上完成数据分区工作后，为了使各个计算节点可以并行在对应的数据分区上执行局部聚类，需要对原始FSDP算法进行两处修改：

a）FSDP在计算数据点局部密度和最小距离时需要遍历整个数据集，为了可以在分区内独立计算这两个结果，这里分别采用公\式（3）和（4）在分区P内计算数据对象的局部密度和最小距离。

$$
\delta _ { i } = \left\{ \begin{array} { l l } { \displaystyle \operatorname* { m i n } _ { j : \rho _ { j } > \rho _ { i } } \big ( d _ { i j } \big ) , i \geq 1 } & \\ { \displaystyle \operatorname* { m a x } _ { j } \big ( d _ { i j } \big ) , \rho _ { i } = \operatorname* { m a x } ( \rho ) } & \end{array} \right. { p _ { i } , p _ { j } \in P }
$$

b）FSDP算法需要人为参与聚类中心的选取，为了摆脱算法的人为干预，本文采用式（5）作为辅助函数。算法通过为局部聚类设定一个聚类中心阈值，然后将分区内各个数据对象的y取值与设定的阈值作比较，将y取值大于设定阈值的数据对象作为聚类中心的候选对象。

$$
\gamma _ { i } = \rho _ { i } * \delta _ { i } , ( i = 1 , 2 , \cdots , n )
$$

局部聚类算法实现：

输入：P为数据分区； $d _ { c }$ 为截断距离；threshold为聚类中心阈值。

输出：数据分区的局部聚类结果。

1.for each point in P do  
2. 利用式（3）计算数据点的局部密度估计值 $\rho _ { i }$   
3. end for  
4. for each point in P do  
5. 利用式（4）计算数据点的最小距离和最近邻点  
6. end for  
7. for each point in P do  
8. 利用式（5）计算分区内数据对象的γi取值  
9. end for  
10.for each point in P do  
11. 比较数据点γi的取值与threshold的大小关系，如果  
Yi>threshold，则该数据点选为聚类中心，并给定所属簇  
12.for each point in P do  
13. if point not centerpoint then  
14. 将数据点划分给最近高密度邻点所属的簇  
15. end if  
16.end for  
17.计算每个聚簇的边界密度  
18.for each point in P  
19．如果数据对象的局部密度大于所属簇边界密度，则标记  
该数据对象为核心点，否则为光晕点  
输山米甲

# 3.3 局部簇合并

为了使得SFSDP聚类算法在局部聚类阶段各个计算节点可以独立在对应的数据分区上进行聚类，数据分区阶段将数据集划分成了若干组互相重叠的数据分区。这些相互重叠的分区内包含了一些公共的数据对象。在局部聚类合并阶段，算法可以通过评估这些公共数据对象（即临界点和扩展点）的特征，找出所有需要合并的局部簇。

为了描述的方便，假设C1和C2分别表示两个重叠分区P1和P2通过局部聚类得到的一个局部簇(即C1cP1，C2cP2，且 ${ \mathrm { P l } } \cap { \mathrm { P } } 2 \neq \Phi$ 。）

定理1合并点定理。如果存在数据点 $\mathsf { p } \in \mathbf { C } 1 \cap \mathbf { C } 2$ ，且p在局部簇C1和C2中都是核心成员，则需要合并C1和C2（即局部簇C1中的点和局部簇C2中的点应该归属于同一个全局簇)。数据点p称为局部簇C1和C2的合并点。

证明核心成员对应簇的中心，由高密度的数据对象组成。上述定理通过聚簇核心成员的定义可以很容易得出。

定理2所有的合并点一定是分区内的临界点或扩展点。如果数据点p是局部簇C1和C2的一个合并点，那么数据点p一定是分区内的临界点或扩展点。

证明因为由合并点 $\mathsf { p } \in \mathrm { C } 1 \cap \mathrm { C } 2$ 可以得出 $\mathsf { p } \in \mathsf { P } 1 \cap \mathsf { P } 2$ ，所以点p位于P1和P2的重叠区域。由临界点和扩展点的定义，定理2得证。

基于以上定理，在确定局部聚类的合并点时，只需要获取分区内所有的临界点和扩展点，并判断其是否满足定理1即可。为了获取到分区内所有的临界点和扩展点，由图1可以看出，一个分区的临界点同时也是相邻分区的扩展点，且只有扩展点和临界点才会出现在多个分区内，所以可以通过对局部聚类结果按照数据对象进行分组，然后通过过滤组内成员个数大于1的数据点作为合并点的候选对象，最后通过观察候选对象是否满足定理1来确定所有的合并点。

在找到所有的合并点后，根据合并点在不同分区中所属的局部簇可以得到不同分区间局部簇的关联关系。为了可以方便地给局部簇分配全局簇标识，利用图论知识将局部簇与其之间的关联关系分别表示成图的顶点和边，最终构建出一张局部簇关联图，属于同一个全局簇的局部簇集合对应了图中的一个连通子图。通过为图中各个连通子图的顶点所代表的局部簇生成一个全局聚簇标识即可完成局部簇标志到全局簇标志的映射。

局部簇合并算法实现：

输入：D为局部聚类结果,数据格式为Key-Value:(p,(pId,clusterId，flag))。其中p表示数据对象本身；pId表示数据分区Id；clusterId表示分区内局部簇Id；flag表示数据对象是核心成员还是光晕成员。

输出：全局聚类结果。

1．对数据集D按照数据对象p进行分组，通过过滤组内成员大于1的数据对象得到合并点候选对象集合CS。  
2．遍历合并点候选对象集合CS，通过观察候选对象在各分区局部簇中的标记（flag，是否为核心成员）和定理1判断候选对象是否为合并点，得到合并点集合MS。  
3．根据合并点所属的局部簇类，构建局部簇关联关系集合LS。集合元素格式为(pl.clusterId，p2.clusterId)，代表p 同时属于分区p1中标志为clusterId的局部簇和分区p2中标志为clusterId 的局部簇。  
4．初始化局部簇关联图G，将所有局部簇作为顶点添加到图G中，同时为每个顶点生成一条指向自身的边。  
5.遍历集合LS，对于集合中的每个元素(pl.clusterId，p2.clusterId)，如果在关联图G中不存在相对应的边，那么

将(p1.clusterId,p2.clusterId)作为图G的一条边加入到图中。最终，所有属于同一全局簇的局部簇构成了图G的一个连通子图。

6．为图G中的每个连通子图g生成一个全局簇标志，将g中所有顶点代表的局部簇标志都映射到这个全局聚簇标志，从而建立局部簇标识到全局簇标识的映射。

7．利用得到的局部簇标志到全局簇标志的映射更新每个局部簇中数据对象的簇标志。

# 3.4算法时间和空间复杂度分析

# 1）时间复杂度分析

假设待聚类数据集包含n个数据对象，FSDP聚类算法的时间消耗主要包含两个阶段：a)计算数据对象的局部密度阶段;b）计算数据对象的最小距离阶段。由于FSDP算法在这两个阶段的计算都需要两层循环遍历数据集，所以算法的整体时间复杂度为 $O ( n ^ { 2 } )$ 。而SFSDP聚类算法的时间消耗主要包含三个阶段：a）数据分区阶段；b）分区内局部聚类阶段；c）局部簇合并阶段。假设集群中一共有M个计算节点并行处理，在数据分区阶段，需要对数据集进行多次遍历来确定数据划分，时间复杂度为 $O ( n / m )$ 。在局部聚类阶段，假设指定每个网格单元内数据对象的数量最多不超过 $\mathrm { ~ m ~ }$ ，则数据集在数据分区阶段可大致划分成 $n / m$ 个数据分区，每个分区内数据对象的数量大致为 $\mathbf { m }$ （因为分区内包含了网格单元的扩展点，所以实际分区内的数据对象数量可能会大于 $\mathrm { ~ m ~ }$ 。这里由于网格单元的扩展点数量相对于 $\mathrm { ~ m ~ }$ 过小，所以可以忽略)。在每个分区上执行聚类的时间复杂度为 $O ( m ^ { 2 } )$ ，所以该阶段的时间复杂度为 $O ( ( m * n ) / M )$ 。在局部簇合并阶段，需要遍历数据集来查找局部簇的合并点和更新数据对象的全局簇标志，时间复杂度为 $O ( n / M )$ 。所以SFSDP算法最后总的时间复杂度计算公式如式（6）所示。考虑到计算节点间的通信和数据传输需要额外的代价，算法的实际时间复杂度会略大于这里给出的计算。

$$
T = O ( n / M ) + O ( ( n ^ { * } m ) / M ) + O ( n / M )
$$

# 2）空间复杂度分析

假设待聚类数据集包含 $\mathfrak { n }$ 个数据对象，由于需要记录数据集中每一对数据对象之间的距离，所以FSDP聚类算法的空间复杂度为 $O ( n ^ { 2 } )$ 。而在SFSDP中，假设指定每个网格单元内数据对象的数量最多不超过 $\mathrm { ~ m ~ }$ ，聚类算法将数据集划分到 $n / m$ 个分区中（这里是理想状态，实际分区的数量会大于等于 $n / m )$ 。因此，SFSDP聚类算法对每个计算节点的存储空间要求为$O ( m ^ { 2 } )$ 。

# 4 仿真实验

# 4.1实验环境搭建

本实验通过配置五台普通机器搭建 Spark 集群，其中每台计算机的硬件配置为IntelCore i5 $2 . 7 ~ \mathrm { G H z } ~ 4 \$ 核CPU，8GB内存，512GB 硬盘。软件环境为CentOS6.5操作系统。所有的计算节点通过千兆以太网交换机互连。Spark版本为2.3.0。

# 4.2算法准确性对比实验

为了验证SFSDP算法的准确性，实验选取表1中给出的测试数据集分别对SFSDP和FSDP算法进行聚类，得到的各个测试数据集的准确性对比实验结果如表2所示。

表1SFSDP与FSDP 算法聚类准确性  

<html><body><table><tr><td>数据集</td><td>样本数目</td><td>属性维度</td><td>类别个数</td></tr><tr><td>Spiral</td><td>312</td><td>2</td><td>3</td></tr><tr><td>R15</td><td>600</td><td>2</td><td>15</td></tr><tr><td>Aggregation</td><td>788</td><td>2</td><td>7</td></tr><tr><td>D31</td><td>3100</td><td>2</td><td>31</td></tr><tr><td>Iris</td><td>150</td><td>4</td><td>3</td></tr><tr><td>Wine</td><td>178</td><td>13</td><td>3</td></tr><tr><td>Glass</td><td>214</td><td>9</td><td>6</td></tr><tr><td>Seeds</td><td>210</td><td>7</td><td>3</td></tr><tr><td>WDBC</td><td>596</td><td>30</td><td>2</td></tr><tr><td colspan="2">表2</td><td>FSDP与SFSDP算法聚类准确性</td><td></td></tr><tr><td>数据集</td><td>FSDP</td><td></td><td>SFSDP</td></tr><tr><td>Spiral</td><td></td><td>1</td><td>1</td></tr><tr><td>R15</td><td>99.66%</td><td></td><td>99.24%</td></tr><tr><td>Aggregation</td><td>99.47%</td><td></td><td>94.52%</td></tr><tr><td>D31</td><td>96.16%</td><td></td><td>92.31%</td></tr><tr><td>Iris</td><td>87%</td><td></td><td>83.47%</td></tr><tr><td>Wine</td><td>70.78%</td><td></td><td>65.39%</td></tr><tr><td>Glass</td><td>57.34%</td><td></td><td>55.76%</td></tr><tr><td>Seeds</td><td>88.57%</td><td></td><td>86.35%</td></tr><tr><td>WDBC</td><td>57.47%</td><td></td><td>53.65%</td></tr></table></body></html>

由表2可以看出，SFSDP算法的聚类准确性相比于原始FSDP聚类算法略低。经过分析得知其主要原因有两个：a)在计算分区内扩展点的局部密度时，由于其密度截距范围内有一部分邻近对象不在同一个分区中，导致扩展点的局部密度计算偏小，可能致使扩展点被误判成光晕成员；b)由于在分区内判断数据对象的最小距离，对于有些边界点，其全局高密度最邻近数据点可能出现在相邻分区中，导致数据点划分出错。

# 4.3算法性能对比实验

为了度量 SFSDP算法与FSDP算法之间的性能差距，实验从香港科技大学智能城市研究小组(http://www.cse.ust.hk/scrg/)获取实验测试数据集。该测试数据集信息包含了4000多辆出租车的行驶数据。通过对原始文件处理，得到只含有车辆坐标的数据文件。从生成的坐标文件中随机选取生成大小不一的五个数据样本D1（1千个坐标点）、D2（2千个坐标点）、D3（5千个坐标点）、D4（1万个坐标点）、D5（2万个坐标点）。SFSDP算法和FSDP算法在上述五个测试集上执行的性能对比实验结果如图2所示。

从图2可以看出，FSDP算法由于无须对数据集进行分区和进行计算节点间的通信，在数据规模较小时算法用时较少；但当数据规模快速增长时，FSDP算法运行的时间会快速增长，在数据规模达到20000时，FSDP算法就已经不能有效地完成聚类分析，因此算法的伸缩性较差。而对于SFSDP算法来说，由于SFSDP算法需要在数据集分区和节点间通信上花费一定的时间，当数据规模较小时，数据集分区和节点间通信所占的时间比重较高，算法的效率劣于FSDP算法；但当数据规模上升时，随着数据分区及节点间通信时间比重的下降，SFSDP算法的整体花费时间增长平缓，因此算法具有较强伸缩性。

![](images/c74492c6146d7cbd39ab6c5643137793c1681f4543c0868a5ce6a65a8a3fe90d.jpg)  
图2SFSDP 和FSDP 算法运行的时间对比

# 4.4加速比和扩展比分析

为了更好地验证SFSDP算法的可扩展性，实验从车辆坐标数据文件中随机选取生成五个测试数据集：D1(1万个坐标点）D2（10万个坐标点）、D3（100万个坐标点）、D4（200万个坐标点）和D5（500万个坐标点）数据集。通过在不同数量节点下对各个测试集进行实验，计算对应测试数据集的加速比和扩展比。实验结果分别如图3和4所示。

从图3可以看出，SFSDP算法在进行聚类处理时，随着节点数量的增加，加速比也随之增大。但对于小规模数据集D1和D2，随着节点的增加，加速比曲线斜率下降比较明显。这主要是因为D1和D2的数据集规模较小，随着节点数目的增加，集群用于计算的时间比较小，而用于节点间通信的时间比较大。而对于大规模数据集D3、D4、D5，加速比更接近线性增加。在图4中，随着集群节点个数的增加，算法在各个数据集上的扩展比逐渐减小。这主要是因为随着集群中节点个数的增加，使得节点之间的通信代价增加。当数据规模越大时，SFSDP算法的扩展比越高，这表明算法在大规模数据上可以取得较好的扩展性。

![](images/3bf7f1a82c2d3886992feba9c93cfcfbdd1807080c3d8da6101ce5fd2d6cd8a3.jpg)  
图3SFSDP算法在不同规模测试集上的加速比

![](images/eb08559f978596045e645eb0595c2a95bbbadfe295c15ecb79561411a39094b4.jpg)  
图4SFSDP算法在不同规模测试集上的扩展比

# 5 结束语

针对FSDP聚类算法在进行海量、高维度数据聚类时存在效率低、伸缩性差的问题，为了适应大规模数据聚类分析，本文提出了一种基于Spark的并行FSDP聚类算法SFSDP。算法首先通过将海量数据集在空间中划分成多个数据量均衡的数据分区；然后利用多个计算节点在各个划分好的数据分区上并行执行改进后的FSDP聚类算法，得到各个数据分区的局部聚类结果；最后将局部聚类的结果合并生成全局聚类簇集。实验结果表明，SFSDP算法与FSDP算法相比，算法在保证准确率的前提下，具备较强的可扩展性，能够有效处理大规模数据集的聚类

# 参考文献：

[1]HanJiawei,KamberM.数据挖掘概念与技术[M].范明，译.北京：机 械工业出版社，2001:232-236.   
[2]Zhou Z H. Three perspectives of data mining [J].Artificial Intelligence, 2003,143 (1): 139-146.   
[3]Omran M G H, Engelbrecht A P, Salman A.An overview of clustering methods [J].Intelligent Data Analysis,2007,11(6): 583-605.   
[4]Rodriguez A,Laio A.Clustering by fast search and find of density peaks [J]. Science,2014,344 (6191): 1492-1496.   
[5]淦文燕，刘冲．一种改进的搜索密度峰值的聚类算法[J].智能系统学 报，2017,12 (2):229-236.(Gan Wenyan，Liu Chong.An improved clustering algorithm that searches and finds density peaks [J].CAAI Transactions on Intelligent Systems,2017,12(2): 229-236.)   
[6]蒋礼青，张明新．郑金龙．快速搜索与发现密度峰值聚类算法的优化研 究[J].计算机应用研究,2016,12(11):3251-3254.(Jiang Liqing,Zhang Mingxin,Zheng Jinlong,et al. Optimization ofclustering by fast search and find of density peaks [J].Application Research of Computers,2016,12 (11): 3251-3254.)   
[7]贺玲，吴玲达，蔡益朝.数据挖掘中的聚类算法综述[J].计算机应用 研究,2007,24(1):10-13 (He Ling,Wu Lingda,Cai Yichao.Survey of clustering algorithms in data mining[J].Application Research ofComputers, 2007,24(1): 10-13.)

[8]BieR,Mehmood R,Ruan S,et al.Adaptive fuzzy clustering by fast search

and find of density peaks [J].Personal& Ubiquitous Computing,2016,20 (5): 785-793.   
[9]Zaharia M,Chowdhury M,Franklin M J,et al. Spark: cluster computing with working sets[C]//Proc of Usenix Conference on Hot Topics in Cloud Computing.[S.1.] : USENIX Association,2010:10-10.   
[10] Zaharia M,Chowdhury M,Das T,et al.Resilient distributed datasets: a fault-tolerant abstraction for in-memory cluster computing [C]// Proc of Usenix Conference on Networked Systems Design and Implementation. [S. 1.] :USENIX Association,2012:2-2.   
[11] Barany I,Vu VH. Central limit theorems for Gaussian polytopes [J].Annals of Probability,2006,35 (4):1593-1621.   
[12] Bentley JL.Multidimensional binary search trees used for associative searching[J]. Communications of the ACM,1975,18 (9): 509-517.