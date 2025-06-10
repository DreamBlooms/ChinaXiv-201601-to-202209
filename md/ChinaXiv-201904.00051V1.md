# 基于模糊蚁群的加权蛋白质复合物识别算法

毛伊敏」，刘银萍」，胡健²

(1.江西理工大学 信息工程学院，江西 赣州 34100;2.江西理工大学 应用科学学院 信息工程系，江西 赣州341000)

摘要：针对蚁群融合模糊C-means (FCM)聚类算法在蛋白质相互作用网络中进行复合物识别的准确率不高、召回率较低以及时间性能不佳等问题进行了研究，提出一种基于模糊蚁群的加权蛋白质复合物识别算法 FAC-PC(algorithm for identifying weighted protein complexes based on fuzzyant colony clustering)。首先，融合边聚集系数与基因共表达的皮尔逊相关系数构建加权网络；其次提出 EPS (essentialprotein selection)度量公式来选取关键蛋白质，遍历关键蛋白质的邻居节点，设计蛋白质适应度PFC(protein fitnesscalculation)来获取关键组蛋白质，利用关键组蛋白质替换种子节点进行蚁群聚类，克服蚁群算法中因大量拾起放下和重复合并过滤操作而导致准确率和收敛速度过慢的缺陷；接着设计相似度 SI (similarity improvement)度量优化拾起放下概率来对节点进行蚁群聚类进而获得聚类数目；最后将关键蛋白质和通过蚁群聚类得到的聚类数目初始化 FCM 算法，设计隶属度更新策略来优化隶属度的更新，同时提出兼顾类内距和类间距的FCM迭代目标函数，最终利用改进的FCM完成复合物的识别。将FAC-PC算法应用在DIP数据上进行复合物的识别，实验结果表明FAC-PC算法的准确率和召回率较高，能够较准确地识别蛋白质复合物。

关键词：蛋白质相互作用网络；蚁群聚类算法；模糊C-means；适应度；蛋白质复合物中图分类号：TP399 doi:10.19734/j.issn.1001-3695.2018.10.0799

Algorithm for identifying weighted protein complexes based on fuzzy ant colony clustering

Mao Yimin ',Liu Yinping 1,Hu Jian ² (1.Schoolof InformationEngineering,Jiangxi UniversityofSience&Technology，Ganzhou Jiangxi 341ooo,China; 2. Dept.ofInformationEngineeing,ColegeofAppliedScience,Jiangxi UniversityofScience&TechnologyGanzhou Jiangxi 341000,China)

Abstract: Aiming at the problem that the accuracyandrecallof the proteincomplexes identification algorithm based onant colony and fuzzyC-means (FCM)clustering are not high and therunning effciency is low,this paper proposed a novel protein complex recognition algorithm named FAC-PC (algorithm for identifying weighted protein complexes based on fuzzy antcolonyclustering).Firstly,combing withthePearsoncorrelationcoefficientandedgeaggregationcoeficient,it constructedthe weighted proteinnetwork.Secondly,inordertoovercomethedefectsof masive merger,filter,repeated pick-upand drop-downoperations inantcolony clustering algorithm,itdesigned the EPS(essential proteinselection) metric toselectesential protein,anddesignedthePFC(proteinftess calculation)metric totraverse neighborsofessential proteins to obtain essntial group proteins,then the esential group protein replaced the seed node in the process of ant colony clustering，which improved results that the accuracy and time performance.Furthermore，it proposed the SI (similarity improvement)metric tooptimize theprobabilityof pickingand droppng operations of ant colony toobtain the number of clustering.Finallyaccording to the improvedantcolonyalgorithm,itobtained theessential protein and the numberof clustering to initialize the FCMalgorithm,and designed the membership updatestrategy tooptimize the membership update,at the same time,anew FCM objective function which took a balance between intra-clustering and proposed inter-clustering variation，finally identified the protein complex byimproved FCM algorithm.It used FAC-PC algorithmto identifyprotein complexeson DIPdata.Theexperimental results show thatFAC-PCalgorithm has better performance on accuracy and recall, which is more reasonable to identify protein complexes.

Keywords:protein-protein interactionnetwork;antcolonyclusteringalgorithm; fuzzyC-means; fitnes; proteincomplex

# 0 引言

蛋白质相互作用网络（protein-protein interaction，PPI)是指一个生命有机体内的所有蛋白质之间相互作用组成的网络，它可以表示成一个无向图[1]。在一个PPI网络中，蛋白质复合物是指在相同时间和空间通过相互作用组成一个多分子机制的蛋白质集合[2]。大量的生物实验和计算方法实验产生了许多高质量、大规模的PPI网络数据，这些数据为识别蛋白质复合物奠定了基础，而蛋白质复合物的识别能够帮助人类预测未知的蛋白质功能，解释特定的生物进程，并为研究疾病的发生机理，寻找新的药物靶标，提供重要的理论基础[3]。因此，识别蛋白质复合物是生物信息领域中的一项研究热点。

后基因组时代生物信息学领域中一个非常活跃的研究领域。根据计算机理的不同，识别蛋白质复合物的算法大体分为：基于密度的方法[4,5]、基于层次的方法[6.7]和基于划分的聚类方法[8,9]。这些方法都有一定的缺陷，基于密度的聚类方法很难对网络中大量的稀疏节点进行聚类，算法挖掘的功能模块的准确率不高；基于层次的聚类方法难于检测出节点交叠的功能模块，聚类结果对网络的噪声非常敏感。由于模糊C-means(FCM）聚类算法实现简单，收敛速度快和局部搜索能力强，利用模糊隶属度划分数据可以改进数据的硬划分问题。因此，目前FCM聚类算法已成功应用于PPI网络复合物识别，成为该领域的研究热点。Trivodaliev 等人[10]提出将FCM与谱聚类相结合用于蛋白质模块功能挖掘。该算法是根据数据节点的模糊隶属度将数据划分到不同的类中，实验划分结果却存在对初始聚类中心和聚类数目敏感的缺陷，隶属度矩阵更新较慢以及目标函数仅仅考虑类内之间的差异，没有考虑类间距对实验结果造成的影响，导致蛋白质复合物识别的过程容易陷入局部最优，算法的预测精度不高和收敛速度较慢。除此之外，近年来涌现出许多群智能思想融合图聚类过程的检测方法，该类算法通过模拟社会性生物群体间的协作行为实现复合物的检测挖掘，展现了良好的检测质量[11]其中蚁群算法具有信息正反馈机制、并行性、全局化特征以及较强的鲁棒性特点，本身就可以直接聚类实现复合物的挖掘，因此基于蚁群的蛋白质复合物挖掘算法逐渐成为一新的研究热点。Ji等人[12]提出蚁群聚类思想应用到PPI网络模块检测问题上，提出了基于蚁群聚类的PPI网络模块检测算法ACC-FMD。赵学武等人[13]提出了融合时序保持特征和蚁群聚类的动态 PPI 网络复合物识别算法 ACC-DPC。这些算法的聚类过程存在反复拾起放下操作和大量的合并过滤操作，导致实验运行的时间效率以及准确性不高。为了克服 FCM聚类算法对初始聚类中心和聚类数目敏感的问题，文献[14]提出将 FCM 与群智能人工蜂群聚类算法相结合用于蛋白质复合物识别，弥补FCM算法的不足，取得了较好的聚类效果。然而上述研究都是将PPI网络有效地用未加权图模型来描述，已经被证明可以比较有效地识别蛋白质复合物，但由于 PPI网络本身的复杂性，可利用的PPI数据的不完整性以及PPI网络中存在噪声等众多问题，仅仅依靠PPI网络本身的蛋白质复合物研究已经受到了限制，实验结果容易受到假阳性以及噪声数据的影响；而且生物中每个蛋白质有着不同的功能，不同的边的重要性也不同，更真实、详尽地表达复杂蛋白质网络结构具有重要作用[15]。因此，将PPI网络构建为加权图来研究更为合理。目前从加权PPI网络图中识别蛋白质复合物越来越受到人们的关注。Dimitrakopoulos 等人[16]提出一种从加权蛋白质网络之中预测重叠蛋白质复合物的算法 GENA。Kouhsar 等人[17]提出一种快速高性能的WCOACH算法预测加权PPI网络中的蛋白质复合体。Ama 等人[18]提出-种跨模块中心移除的加权蛋白质复合物识别算法IMHRC。这些方法克服了假阳性以及噪声对实验结果的影响，能很好地识别精度和很强的鲁棒性，但是聚类结果的召回率和时间效率不高。虽然基于加权PPI网络的复合物识别取得了一定的成效，但是如何有效地构建加权PPI，如何克服复合物识别效果受假阳性的影响、蚁群聚类需大量的拾起放下和合并过滤操作，以及FCM算法对聚类中心和聚类数目敏感、隶属度更新较慢，目标函数仅仅考虑类内差异等导致的准确率、召回率不高以及执行效率低等缺陷，仍是亟待解决的问题。

针对以上问题，本文提出了基于模糊蚁群的加权蛋白质复合物识别算法FAC-PC（algorithm for identifying weightedproteincomplexesbased on fuzzyant colonyclustering)，主要工作为：a）融合边聚集系数与基因共表达的皮尔逊相关系数构建加权蛋白质网络；b）设计基于PPI网络拓扑特性与基因表达数据的EPS度量公式选取关键蛋白质；c）提出基于期望稠密度和模块度的PFC度量公式获取关键组蛋白质；d)设计基于权重的相似度SI度量优化蚁群算法的拾起放下概率，完成蚁群聚类获得聚类数目；e）利用蚁群聚类获得的聚类数目和关键蛋白质初始化FCM聚类算法，设计隶属度更新策略来改进FCM隶属度的更新计算，同时综合考虑类内和类间距，改进FCM算法的目标函数，最后利用改进的FCM完成复合物的识别。实验结果表明本文算法运行效率高聚类结果的准确率以及召回率较高。

# 1 相关工作

# 1.1FCM 聚类算法

FCM聚类算法[19]通过计算每个样本点对所有类中心的隶属度，并对目标函数不断进行优化找到最优解，从而决定样本点的隶属，达到对样本数据集进行聚类的目的。

设数据集 $X = \{ X _ { 1 } , X _ { 2 } , X _ { 3 } , . . . , X _ { n } \}$ ，其中 $X _ { i } = \{ X _ { i 1 } , X _ { i 2 } , . . . , X _ { i n } \}$ 。

FCM算法在满足约束条件 $\sum _ { j = 1 } ^ { C } u _ { i j } = 1 , i = 1 , 2 , . . . N$ 的前提下最小化目标函数 $J$ ，目标函数 $J$ 定义如下：

$$
J ( u , c , k ) = \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { K } { u _ { i j } } ^ { m } d ( x _ { i } , c _ { j } )
$$

其中： $m > 1$ 为模糊加权指数；类别数为 $K$ ， $d \left( x _ { i } , c _ { j } \right)$ 为 $x _ { i }$ 与 $c _ { j }$ 间的欧式距离。结合拉格朗日最小二乘法原理，最小化目标函数得到隶属度 $u _ { i j }$ 和聚类中心 $c _ { j }$ 的迭代更新表达式如下：

$$
u _ { i j } = \left[ \sum _ { k = 1 } ^ { C } \left( { \frac { d \left( x _ { i } , c _ { j } \right) } { d \left( x _ { i } , c _ { k } \right) } } \right) ^ { \frac { 1 } { m - 1 } } \right] ^ { - 1 } \ i = 1 , 2 , . . . , N ; j = 1 , 2 , . . . , K
$$

$$
c _ { j } = \frac { \displaystyle \sum _ { i = 1 } ^ { N } u _ { i j } ^ { m } \cdot x _ { i } } { \displaystyle \sum _ { i = 1 } ^ { N } u _ { i j } ^ { m } } , j = 1 , 2 , . . . , K
$$

该算法本质上是一种局部搜索寻优方法，计算简单，容易实现，但对初始聚类中心极为敏感，容易陷入局部极值而很难得到全局最优解，聚类个数需要人为设定，隶属度更新较慢以及目标函数仅仅考虑类内距，没有考虑类间距，这给蛋白质复合物挖掘造成十分不利的影响，因此采用传统的FCM算法无法对蛋白质复合物进行准确的挖掘。

# 1.2蚁群聚类算法

本文采用ACC-FMD算法[I2]的蚁群聚类思想来介绍蚁群聚类过程。该方法将PPI网络看成是无向图 $G ( V , E )$ ，其中：$V$ 表示蛋白质节点集合； $E$ 表示蛋白质相互作用边的集合。主要过程为：

a）选取种子节点。根据节点的聚集系数，将聚集系数大于阈值的节点选择出来。对于网络 $G ( V , E )$ 中的任意节点 $i ,$ 其聚集系数定义为

$$
\phi _ { i } = \frac { 2 n _ { i } } { \{ N e i g h ( i ) \| N e i g h ( i ) - 1 \} }
$$

其中：Neigh(i)表示节点 $i$ 的直接邻居集合； $n _ { i }$ 表示集合Neigh(i)中的节点之间的相互作用的个数。

b）聚类过程。蚂蚁开始遍历种子节点的领域，根据拾起放下概率模型来完成聚类。固拾起放下概率模型定义如下：

$$
P _ { p } ( j ) = \left[ \frac { k _ { p } } { k _ { p } + s ( i , j ) } \right] ^ { 2 }
$$

$$
P d ( j ) = \left\{ \begin{array} { c c } { 2 s ( i . j ) } & { s ( i , j ) < k d } \\ { 1 } & { \ddagger \nmid \mathrm { t f } } \end{array} \right.
$$

其中： $s ( i , j )$ 是节点 $i$ 和 $j$ 的结构相似性； $k _ { p }$ 和 $k _ { d }$ 两个参数。结构相似度定义为

$$
s ( i , j ) = \frac { \mid \tau ( i ) \cap \tau ( j ) \mid } { \sqrt { | \tau ( i ) \cap \tau ( j ) | } }
$$

其中： $\tau ( i )$ 是由节点 $i$ 和其直接邻居节点构成的集合。

c）信息传递。通过节点之间的相似性将上一代的最优解传递给下一代。该算法评价解的质量是通过模块化密度来实现的，每一代根据 $\mathrm { ~ D ~ }$ 值选取最优解，其定义为

$$
D = \sum _ { h = 1 } ^ { m } \frac { 2 l _ { h } - \overline { { l _ { h } } } } { n _ { h } }
$$

其中： $\mathbf { m }$ 是预测得到的复合物的数量； $\boldsymbol { l } _ { h }$ 是复合物 $\mathbf { h }$ 中的边数； $\overline { { l _ { h } } }$ 为边的一端在复合物内部，另一端在复合物的外部的边的数量； $n _ { h }$ 是复合物中节点的个数。

d）后处理过程。对初始聚类结果进行合并和过滤两个基本后处理操作。合并操作是合并两个相似度大于阈值的模块，对合并后的聚类结果过滤掉那些密度小于阈值的模块，其相似度定义为

$$
S \left( M _ { x } , M _ { y } \right) { = } \frac { \sum _ { i \in M _ { x , j \in M _ { y } } } r ( i , j ) } { \operatorname* { m i n } \left\{ \left| M _ { x } \right| , \left| M _ { y } \right| \right\} } 
$$

$$
r ( i , j ) = \left\{ \begin{array} { c c } { { 1 } } & { { i = j } } \\ { { \big | g _ { i } \cap g _ { j } \big | } } & { { } } \\ { { \big | g _ { i } \cup g _ { j } \big | } } & { { i \not = j , \big ( i , j \big ) \in E } } \\ { { 0 } } & { { \not \equiv \not \in \not { A } \not \in \not { A } } } \end{array} \right.
$$

蚁群聚类是一种启发式的搜索算法，具有正反馈性、自组织性和健壮性等优点，聚类过程却存在大量的重复合并过滤以及拾起放下操作，导致聚类的时间效率以及准确率较低，因此采用传统的蚁群算法无法有效地对蛋白质复合物进行准确挖掘。

# 2 FAC-PC 算法

# 2.1算法思想

针对蛋白质相互作用网络存在不稳定性，复合物的识别效果容易受到假阳性的影响；蚁群聚类效率受合并过滤以及重复拾起放下操作影响较大和FCM聚类结果对初始聚类中心、聚类数目敏感、隶属度更新较慢以及目标函数仅仅考虑类内之间的差异等问题，为提高算法的准确率、召回率、执行效率和降低假阳性的影响，本文借鉴文献[14]的群智能算法融合FCM算法来实现蛋白质复合物的挖掘思想，利用蚁群算法的信息正反馈机制、并行性、全局化特征以及较强的鲁棒性特点来解决FCM对聚类中心和聚类数目敏感的问题，提出了一种在加权PPI网络中有效地识别蛋白质复合物算法FAC-PC。具体FAC-PC算法思想为：首先以蛋白质相互作用网络为框架，利用边聚集系数与基因共表达的皮尔逊相关系数衡量相互作用边的可靠性进而构建加权网络；其次利用EPS度量公式选取关键蛋白质，遍历关键蛋白质的邻居节点，利用本文设计的PFC度量来获取关键组蛋白质，将关键组蛋白质替换种子节点进行蚁群聚类；接着使用相似度SI度量优化蚁群拾起放下概率来对节点进行蚁群聚类，获得聚类数目；最后将关键蛋白质和通过蚁群聚类得到的聚类数目初始化FCM算法，利用改进的隶属度更新策略来优化隶属度的更新，同时也提出兼顾类内距和类间距的FCM迭代目标函数，并利用改进的FCM算法最终完成复合物的识别。

# 2.2加权蛋白质网络的构建

针对传统的基于PPI网络的蛋白质复合物识别算法的准确度比较依赖于网络本身的可靠性，复合物的识别效果容易受到假阳性以及噪声数据的影响；生物蛋白质网络中不同边的重要性不同等问题，本文基于蛋白质复合物是成簇出现且倾向于共表达的事实，且蛋白质复合物的挖掘与相互作用的可靠程度之间关系密切，综合考虑蛋白质网络的拓扑边聚集系数和共表达生物特征，采用边聚集系数[20]和皮尔逊相关系数[21]衡量蛋白质两个节点之间相互作用的可靠程度。

边聚集系数作为蛋白质相互作用网络的一个重要拓扑特性，可以用来描述蛋白质相互作用之间的可靠性，还可以用来衡量蛋白质之间属于用一簇的概率，能够较好地识别出关键蛋白质。则蛋白质节点 $\boldsymbol { u }$ 和 $\nu$ 的边聚集系数 $E C C ( u , \nu )$ 计算如下：

$$
E C C = \frac { \mid N ( u ) \cap N ( \nu ) \mid } { \operatorname* { m i n } ( N _ { u } - 1 , N _ { \nu } - 1 ) }
$$

其中： $\mid N ( u ) \cap N ( \nu ) \mid$ 表示节点 $\boldsymbol { u }$ 和 $\nu$ 所共有的邻居节点数； $\boldsymbol { N _ { u } }$   
和 $N _ { \nu }$ 分别表示节点 $\boldsymbol { u }$ 和 $\nu$ 的度。

另一方面利用基因表达数据来计算两个蛋白质节点之间的皮尔逊相关系数，以衡量蛋白质之间的可信度。 $P C C ( u , \nu )$ 表示节点之间的皮尔逊相关系数，则节点 $\boldsymbol { u }$ 与 $\nu$ 之间的皮尔逊相关系数计算如下：

$$
P C C ( u , \nu ) = \frac { 1 } { k - 1 } \sum _ { t = 1 } ^ { k } \left( \frac { E _ { x p } ( u , t ) - \overline { { E _ { x p } ( u ) } } } { \sigma ( u ) } \right) \left( \frac { E _ { x p } ( \nu , t ) - \overline { { E _ { x p } ( \nu ) } } } { \sigma ( \nu ) } \right)
$$

其中： $\boldsymbol { \ N } _ { u }$ 和 $ { \boldsymbol { N } } _ {  { \boldsymbol { \nu } } }$ 分别代表节点 $u$ 和 $\mathbf { \sigma } _ { \nu }$ 的直接邻居集合； $k$ 为样本数；基因表达数据中时刻数 $E _ { x p } ( u , i )$ 和 $E _ { x p } ( \nu , i )$ 分别为蛋白质 $u$ 和 $\mathbf { \sigma } _ { \nu }$ 在时刻 $i$ 下的表达值； $\overline { { E _ { x p } ( u ) } }$ 和 $\overline { { E _ { x p } ( \nu ) } }$ 为蛋白质 $u$ 和 $\boldsymbol { \nu }$ 在所有时刻下的平均表达值； $\boldsymbol { \sigma } ( u )$ 和 $\sigma ( \nu )$ 表示蛋白质节点 $u$ 和 $\boldsymbol { \nu }$ 在所有时刻下的标准方差。

在PPI网络拓扑边聚集系数的基础上，融合基因共表达数据，设计出了边聚集系数与基因共表达的皮尔逊相关系数的乘积公式用于计算相互作用边的存在概率，从而构建加权蛋白质相互作用网络。则蛋白质相互作用网络中边的权重$P ( u \ : , \nu )$ 计算如下：

$$
P ( u , \nu ) = E C C ( u , \nu ) \times P C C ( u , \nu )
$$

通过式（13）构造的加权网络，不仅考虑了节点的拓扑特性聚集程度，而且还增加了皮尔逊相关系数来度量相互作用蛋白质的基因共表达强弱程度，可以将一部分权值为0的数据排除，降低预测方法对蛋白质相互作用网络本身可靠性的依赖程度以及假阳性和噪声数据对实验造成的影响，进而提高识别的准确度。加权后的蛋白质网络形式化定义如下：

定义1加权蛋白质网络 $D G ( V , E , P )$ 。其中：$V = \left( \nu _ { 1 } , \nu _ { 2 } , \nu _ { 3 } , \nu _ { 4 } , \nu _ { 4 } , . . . , \nu _ { n } \right)$ 表示蛋白质节点集合；$E = \left( e _ { 1 } , e _ { 2 } , e _ { 3 } , e _ { 4 } , e _ { 5 } , . . . e _ { m } \right)$ 表示蛋白质相互作用的集合；

$P = ( p ( e _ { 1 } ) , p ( e _ { 2 } ) , p ( e _ { 3 } ) , p ( e _ { 4 } ) , p ( e _ { 5 } ) , . . . p ( e _ { m } ) )$ 表示相互作用权重的集合。

# 2.3蚁群算法的改进

# 2.3.1关键蛋白质的选取

针对蚁群聚类种子节点的选取仅仅依靠PPI数据，识别的准确率比较依赖于网络本身的可靠性，实验结果容易受到假阳性的影响。为了降低假阳性的影响，提高聚类准确性，本文设计出基于边聚集系数和皮尔逊相关系数的关键蛋白质选取EPS度量公式。

给定蛋白质加权网络 $D G ( V , E , P )$ ， $E C C ( u , \nu )$ 表示节点 $\boldsymbol { u }$ 与 $\mathbf { \sigma } _ { \nu }$ 之间的边聚集系数， $P C C ( u , \nu )$ 表示节点之间的皮尔逊相关系数，则关键蛋白质选取EPS度量公式为

$$
E P S \left( u \right) = \delta + \sum _ { \left( u , \nu \right) \in E } \frac { P \left( u , \nu \right) - \operatorname* { m i n } P \left( u , \nu \right) } { \operatorname* { m a x } P \left( u , \nu \right) - \operatorname* { m i n } P \left( u , \nu \right) }
$$

$E P S ( u )$ 考虑到了节点 $\boldsymbol { u }$ 和 $\nu$ 在网络的拓扑特性的聚集程度，还增加了基因共表达程度来衡量一个节点和其邻居节点成簇的可能性，而且还考虑到基因表达数据与PPI网络数据的差别，因此能有效地评价一个蛋白质的关键性。根据式(14)，将高于关键性阈值的节点选取出来，这样可以降低假阳性和假阴性对实验结果产生的影响，而且使得有公共顶点的稠密子图的相似度尽可能降低，最终提高算法运行的准确率，本文设置 $\scriptstyle { \delta = 0 . 0 1 }$ 。

关键蛋白质的选取思想如下：首先基于蛋白质复合物是成簇出现且倾向于共表达的事实，利用式（13）来计算边的存在概率,构建加权网络；接着充分考虑节点之间的紧密程度以及共表达程度，利用EPS度量式（14）来计算网络节点的权重，将节点权重大于关键性阈值的节点选取出来作为关键蛋白质。这是因为关键性高的蛋白质对生命活动更为重要，从而求得的蛋白质复合物更能体现功能模块的生物特性，而且相比非关键蛋白质，关键蛋白质对于复合物的挖掘的重要性更高。

关键蛋白质的选取过程形式化如下：

输入：蛋白质网络 $G ( V , E , P )$ ，关键性阈值 $\theta$ ，基因表达数据和参数 $\delta$ 。

输出：关键蛋白质集合 $\{ \nu _ { 1 } , \nu _ { 2 } , . . . , \nu _ { k } \}$ 0a)构建加权蛋白质网络

(1) for each $\left( u , \nu \right) \in E$ do (2) Compute $E C C ( u , \nu )$ by Eq. (11) (3) Compute $P C C ( u , \nu )$ by Eq. (12) (4) Compute $P ( u , \nu )$ by Eq. (13) (5)end for $\mathbf { b } )$ 选取关键蛋白质 (1) $L = \mathcal { O }$ (1) for each $\nu _ { i } \in V$ do (2) If $E P S { \big ( } \nu _ { i } { \big ) } > \theta$ do (3) $L = L \cup \nu _ { i }$ 将L 中的关键蛋白质按照 EPS 权重非递 排序, $L = \{ \nu _ { 1 } , \nu _ { 2 } , . . . , \nu _ { k } \}$ 且 $E P S \left( \nu _ { 1 } \right) \geq E P S \left( \nu _ { 2 } \right) \geq . . . E P S \left( \nu _ { k } \right)$ (4) end if (5)end for

# 2.3.2关键组蛋白质的形成

针对蚁群聚类采用种子节点来扩展形成蛋白质复合物，若两个种子节点之间相似度比较大，那么聚类形成的两个复合物也比较相似，在后处理过程中，需要将这两个模块合并，而合并操作需要大量的操作计算，影响算法的时间性能；而且一个蛋白质节点可能处于多个种子节点的邻域内，蚁群算法需重复拾起放下操作导致的算法运行效率不高和准确率低等问题。为了提高实验运行效率以及识别出高内聚低耦合的复合物，本文提出蛋白质适应度PFC度量来选取关键组蛋白质，进而利用关键组蛋白质替代种子节点进行蚁群聚类。这是因为关键组蛋白质是一个子图，由于子图之间的差异性比原来蚁群聚类算法中种子节点之间的差异性大，所以求得的复合物不需要再进行合并，从而提高了算法的运行效率以及准确率；同时在每次拾起放下之前会判断加入该蛋白质节点和不包含该蛋白质的适应度差值是否大于0，如果适应度小于0，不对它进行拾起放下操作，减少拾起放下次数进而提高计算效率。

基于复合物是稠密子图且具有高度的模块性，设计出基于期望稠密度[22]和模块度[23]的蛋白质节点适应度PFC度量公式，根据节点适应度来遍历关键节点的邻域节点，最终形成关键组蛋白质，利用核心组蛋白质替代种子节点进行蚁群聚类。

给定一个蛋白质网络 $D G ( V , E , P )$ ，其中 $E D = { \frac { 2 \times \sum _ { \mathrm { i } = 1 } ^ { m } p ( { \boldsymbol { e } } _ { i } ) } { | V | \times ( | V | - 1 ) } } \ ,$ $E = \left( e _ { 1 } , e _ { 2 } , e _ { 3 } , e _ { 4 } , e _ { 5 } , . . . e _ { m } \right)$ ，和子图 $s$ ，则网络图 $G$ 的期望稠密度定义为

$$
E D = { \frac { 2 \times \sum _ { \mathbf { i } = 1 } ^ { m } { p { ( { e _ { i } } ) } } } { | V | \times ( | V | - 1 )  } }
$$

模块度的定义为

$$
W R = \frac { \underset { \nu \in S } { \sum } p ( \nu _ { a } , S ) } { \underset { \nu \in S } { \sum } p _ { o u t } ( \nu _ { a } , S ) + \underset { \nu \in S } { \sum } p ( \nu _ { a } , S ) }
$$

其中： $P$ 表示网络图中边的存在概率，通过边聚集系数和皮尔逊相关系数的乘积计算得到； $\nu _ { a }$ 是子图 $s$ 中的任意节点;$P ( \nu _ { a } , S )$ 是节点 $\nu _ { a }$ 与子图 $s$ 内部其他节点的连接边的权重；$P _ { o u t } \left( \nu _ { a } , S \right)$ 是节点 $\nu _ { a }$ 与 $D G . S$ 中其他节点的连接边的权重。该公式充分考虑到内部节点与外部节点之间的联系。考虑到关键组蛋白质是小而稠密的模块子图，为了挖掘高内聚低耦合的关键组蛋白质，进而提高蛋白质复合物识别的准确性，本文提出的子图适应度以及蛋白质适应度PFC的计算公式分别如下：

$$
F _ { S } = \rho E D \times ( 1 - \rho ) W R
$$

$$
P F C ( S , \nu ) = F _ { S + \nu } - F _ { S - \nu }
$$

其中： $\rho \in ( 0 , 1 )$ 表示期望稠密度和模块度这两种特征在 $F _ { s }$ 所占的重要程度， $\rho$ 越大，说明子图密度在 $F _ { s }$ 中影响力越大，而子图模块度的影响力越小； $S + \nu$ 与 $S _ { - \nu }$ 分别表示在子图 $s$ 加入节点 $\nu$ 和删除节点 $\nu$ 的聚类； $P F C ( S , \nu )$ 表示为子图 $s$ 含节点 $\nu$ 和不包含节点 $\nu$ 时的节点适应度之间的差值，当$P F C ( S , \nu )$ 越大，则节点 $\nu$ 越可能属于子图 $S _ { \circ }$ （20

关键组蛋白质的形成思想如下：首先基于加权蛋白质网络，遍历关键蛋白质节点的邻域节点，把关键蛋白质节点当作初始的关键组蛋白质子图 $S e t$ ；然后根据式（18）来判断是否将关键蛋白质的邻域节点添加进来，若节点 $\nu$ 使得$P F C ( S e t , \nu ) { = } F _ { S e t { + } \nu } - F _ { S e t { - } \nu } > 0$ ，则添加到关键组子图中，逐渐遍历关键节点的邻域，直到所有邻域节点都被遍历完或这些顶点对子图的适应度都为负，扩展的过程将结束，得到核心组蛋白质 $S e t$ 。

关键组蛋白质的形成过程如下：

输入：蛋白质网络 $D G ( V , E , P )$ ，关键蛋白质 $L = \{ \nu _ { 1 } , \nu _ { 2 } , . . . , \nu _ { k } \}$ 。  
输出：关键组蛋白质集合 $S e t$ 。

(1) $S e t = \emptyset$

(2)For $i { = } 1$ to $| L |$ do (3) $S e t _ { i } = S e t _ { i } \cup L ( \nu _ { i } )$ (4) For $\nu _ { j } \in N e i g h ( L ( \nu _ { i } ) ) { \mathrm { ~ d o } } /$ /遍历关键蛋白质的邻域节点 (5) If $P F C ( S e t _ { i } , \nu _ { j } ) > 0$ do (6) $S e t _ { i } = S e t _ { i } \cup \nu _ { j } / / \ S e t  \nu _ { j }$ 输出关键组蛋白质集合 Set (7) End if (8) End for (9)End for

例如，图1给出了一个包含节点 $\nu _ { 2 } \nu _ { 3 } \nu _ { 4 }$ 的加权网络图。根据节点适应度来判断是否添加 $\nu _ { 1 }$ ，若添加节点使得适应度差值大于0，则添加节点，否则不添加节点。具体节点适应度的计算过程如下：

![](images/b72c885ebd460397cc11c532e83022a24fa1d7e55727abe2c062fce451314cfd.jpg)  
图1实例图  
Fig.1Instance graph

由图1得知， $p \big ( \nu _ { 2 } , \nu _ { 3 } \big ) = 0 . 8$ ， $p \big ( \nu _ { 3 } , \nu _ { 4 } \big ) = 0 . 9$ （204号 $p ( \nu _ { 1 } \ , \nu _ { 5 } ) = 0 . 7$ ，若节点 $\nu _ { 1 }$ 添加到该图中，得到 $p \left( \nu _ { 1 } , \nu _ { 2 } \right) = 0 . 8 p \left( \nu _ { 1 } , \nu _ { 4 } \right) = 0 . 7$ ，根据式（18）来计算添加节点 $\nu _ { 1 }$ 和删除节点 $\nu _ { \mathrm { { l } } }$ 的节点适应度的差值，若大于0，则添加否则不添加。

$$
F _ { S + \nu } = 0 . 1 \times E D \times 0 . 9 \times W R =
$$

$$
\frac { 0 . 1 \times 2 \times ( 0 . 8 + 0 . 8 + 0 . 9 + 0 . 7 ) } { 4 \times 3 } \times 0 . 9 \times \frac { 0 . 8 + 0 . 8 + 0 . 9 + 0 . 7 } { 0 . 8 + 0 . 9 + 0 . 8 + 0 . 8 + 0 . 9 + 0 . 7 } = 0 . 0 3 1 3
$$

$$
F _ { s - \nu } = 0 . 1 \times E D \times 0 . 9 \times W R = \frac { 0 . 1 \times 2 \times ( 0 . 8 + 0 . 9 ) } { 2 \times 3 } \times 0 . 9 \times \frac { 0 . 8 + 0 . 9 } { 0 . 7 + 0 . 8 + 0 . 9 } = 0 . 0 3 6 1
$$

因为 $F ( S , \nu ) { = } F _ { _ { S + \nu } } - F _ { _ { S - \nu } } < 0$ ，所以不添加节点 $\nu _ { 1 }$ 。

# 2.3.3相似度改进的SI度量

针对蚁群算法需要反复计算节点的邻居节点数进而归一化共同邻居节点，造成算法的运行效率不高的问题，本文根据节点与核心组蛋白质的相似度SI度量公式来计算拾起放下的概率，再利用该模型完成聚类。下面给出相似度的 SI度量计算公式。

给定无向图 $D G ( V , E , P )$ ,其中： $V$ 表示蛋白质节点集合； $E$ 表示相互作用的集合； $P ( i , j )$ 为蛋白质节点 $i$ 与 $j$ 通过边聚集系数以及基因共表达信息乘积进行加权得到的边权重，则蛋白质 $i$ 与关键组蛋白质 $S e t$ 的相似度SI度量公式如下所示：

$$
S I ( i , S e t ) = \frac { \sum _ { j \in S e t } P ( i , j ) } { \mid S e t \mid ( \mid S e t \mid - 1 ) / 2 }
$$

证明：

a）对于 $\forall i , S e t$ ， $S I ( i , S e t ) = s ( S e t , i )$ ，对称性满足； b）对于 $\forall i , S e t$ ， $\sum _ { j \in S e t } P ( i , j ) \geq 0$ 且 $\vert S e t \vert ( \vert S e t \vert - 1 ) / 2 > 0$ 则 $S I ( i , S e t ) { \geq } 0$ ，非负性满足; c）对于 $\forall i , z , S e t$ ， $S I \left( i , z \right) + \mathrm { S I } \left( z , S e t \right) \geq S I \left( i , S e t \right)$ ，三角不等式 满足。

因此式（19）满足相似度度量的对称性、非负性、和三角不等式特性，且满足全局一致性聚类假设和局部一致性假设，是相似度度量公式。

本文在聚类的过程中，根据节点与关键组蛋白质的相似度SI度量公式来计算拾起放下的概率，再利用该模型完成聚类，故将式（5）和（6）的拾起放下概率模型公式转变为

$$
P _ { p } ( i ) = \left[ \frac { k _ { p } } { k _ { p } + S I ( i , S e t ) } \right] ^ { 2 }
$$

$$
P _ { d } ( i ) = \left\{ \begin{array} { c c } { 2 S I \left( i , \mathrm { S e t } \right) } & { , S I \left( i , \mathrm { S e t } \right) < k d } \\ { 1 } & { \ddagger \mathcal { M } \mathcal { 4 } } \end{array} \right.
$$

基于改进的蚁群算法，具体获得蛋白质复合物的聚类数目思想如下：根据2.3.1节选取出来的关键蛋白质作为初始的关键组蛋白质 $S e t$ ，遍历关键蛋白质的邻域节点，然后根据式（18）来判断是否将关键蛋白质的邻域节点添加进来，若节点 $\nu$ 使得 $P F C ( S e t , \nu ) { = } F _ { S e t + \nu } - F _ { S e t - \nu } > 0$ ，则添加到关键组子图中，再根据SI度量来计算节点与关键组蛋白质子图之间的相似度，根据拾起放下概率模型来实现蚁群聚类，重复迭代获得最优解，输出蚁群聚类的聚类数目。蚁群聚类的具体过程如下：

输入：蛋白质网络 $D G ( V , E , P )$ ，关键蛋白质 $L = \{ \nu _ { 1 } , \nu _ { 2 } , . . . , \nu _ { k } \}$ 。

输出：蛋白质复合物的聚类数目 $\mathsf { M } _ { \mathrm { c } }$ （204号  
$( 1 ) M = 0$ ， $s e t = \emptyset$   
(2)while $L \neq \emptyset$ do  
(3) for $\scriptstyle t = 1$ to $\boldsymbol { \tau }$ do  
(4) $S e t _ { i } = S e t _ { i } \cup L ( \nu _ { i } )$   
(5) for $\scriptstyle n = 1$ to $N$ do  
(6) for $\scriptstyle { i = 1 }$ to $\vert \iota \vert$ do  
(7) 调用关键组蛋白质的形成过程，得到集合Set  
(8) for $\nu _ { x } \in N e i g h ( S e t _ { i } )$ do  
(9) if $P F C ( S e t _ { i } , \nu _ { x } ) > 0$ do  
(10) 利用拾起放下概率模型对节点进行聚类  
(11) end if  
(12) end for  
(13) 蚂蚁 $\mathfrak { n }$ 得到自身的解  
(14) end for  
(15) 第 $t$ 代蚂蚁全部得到自身的解，根据模块度评价标准，求  
出本次迭代的最优聚类结果  
(16) M=M+1  
(17) end for  
(18) end for  
(19)Return M//输出蛋白质复合物的数目

本文将关键蛋白质节点以及通过改进的蚁群聚类算法获得的聚类个数初始化FCM算法，弥补FCM算法对初始聚类中心和聚类数目敏感的缺陷。

# 2.4FCM算法的改进

# 2.4.1隶属度更新的改进策略

针对FCM算法的聚类实际上就是一个隶属度矩阵 $u$ 和聚类中心 $\mathbf { \Psi } _ { c }$ 交替优化过程，当隶属度较大时，蛋白质节点所属的类别不发生改变以及隶属度更新较慢等问题，为了提高算法的收敛速度，可以修正隶属度矩阵 $u$ 来计算下一次迭代的聚类中心，使计算结果更加合理，提高算法的收敛速度。隶属度越大，样本对类中心的吸引力越大。本文基于竞争学习的思想，给出一种隶属度的改进策略：在通过蚁群算法得到初始的聚类中心和聚类数目之后，得到较为可靠的隶属度值，使得距离样本中心点的类中心作为获胜节点，距离次者的节点作对手，通过加入一个抑制参数来不同幅度减弱对手来加快赢着的收敛速度，进而提高算法的执行效率。具体描述为：对于对象 $x _ { i }$ ,若它对第 $\mathbf { \chi } _ { t }$ 类的隶属度最大，为 $\boldsymbol { u } _ { t i }$ ，与同一行的剩余隶属度相差较大时，整体的隶属度的更新速度加快的较多；对第 $s$ 类的隶属度为次大，为 $u _ { s i _ { i } }$ ，给定一个抑制参数 $\eta$ ，则隶属度的更新公式为

$$
u _ { \scriptscriptstyle i } ^ { \prime } = u _ { \scriptscriptstyle i i } + \eta u _ { \scriptscriptstyle s i } , u _ { \scriptscriptstyle s i } ^ { \prime } = ( 1 - \eta ) u _ { \scriptscriptstyle s i }
$$

由式(2)可以看出，在隶属度更新时，本文充分考虑及节点自身的状态，若对象 $x _ { i }$ 对 $t$ 类的隶属度以及对 $s$ 类的隶属度相差的不大，那么上述公式的更新速度就会变慢；若有明显的优势时，即加快隶属度的更新速度。公式中 $\eta$ 的取值会直接影响到算法的执行效率，本文通过实验验证，将参数设置为 $\scriptstyle \eta = 0 . 6$ 。

# $2 . 4 . 2 \ \mathrm { F C M }$ 目标函数选取的改进

针对传统的FCM算法的目标函数仅仅考虑了类内距离，没有考虑类间距，采用梯度法求解极值，所求解容易陷入局部最优，导致复合物挖掘的准确度不高。为了避免算法陷入局部最优，挖掘出高内聚低耦合的复合物，综合考虑类间距和类内距，本文根据Xie-Beni提出的聚类有效性指标[24]，给出一种兼顾类内和类间距的新FCM的目标函数。

类内距差异 $W ( u , c , k )$ 和类间距 $A ( u , c , k )$ 差异分别为

$$
W \left( u , c , M \right) = \sum _ { i = 1 } ^ { | V | } \sum _ { j = 1 } ^ { M } u _ { i j } ^ { m } d \left( x _ { i } , c _ { j } \right)
$$

$$
A ( u , c , M ) = \lvert V \rvert \times \operatorname* { m i n } _ { j \neq M } \lVert c _ { j } - c _ { M } \rVert ^ { 2 }
$$

综合考虑类内和类间距差异，改进FCM算法的目标函数，即

$$
J ( u , c , M ) = \frac { W ( u , c , M ) } { M A ( u , c , M ) } = \frac { \displaystyle \sum _ { i = 1 } ^ { | V | } \sum _ { j = 1 } ^ { M } u _ { i j } ^ { m } d ( x _ { i } , c _ { j } ) } { M | V | \operatorname* { m i n } _ { j \neq M } \| c _ { j } - c _ { M } \| ^ { 2 }  }
$$

# 2.5算法描述

FAC-PC算法具体的实现步骤如下：

a）初始化参数设计。蚂蚁数目为 $N$ ，蚁群迭代次数 $I$ 拾起参数 $k _ { p }$ ，放下参数 $k _ { d }$ ，关键阈值 $\theta \setminus \rho _ { \mathrm { ~ s ~ } } \delta \setminus \omega _ { \mathrm { ~ s ~ } } \varepsilon _ { \mathrm { ~ s ~ } } \eta _ { \mathrm { ~ s ~ } }$ 0

b）根据式（13）对蛋白质网络边进行加权，进而采取式（14）来计算 $\nu _ { i } \in V$ 节点的 EPS 值。若， $E P S { \big ( } \nu _ { i } { \big ) } > \theta$ 将该节点加入到关键蛋白质集合 $L$ 按照非递减的顺序进行排序，将权值 $P ( u \ , \nu ) { = } 0$ 的边当做噪声数据移除。

c）将关键蛋白质节点当做初始的关键组子图 $S e t$ ，遍历关键节点的邻域节点，根据式（18）计算节点 $\boldsymbol { \nu }$ 的适应度，若节点 $\nu$ 使得 $P F C ( S e t , \nu ) { = } F _ { S e t + \nu } - F _ { S e t - \nu } > 0$ ，则添加到关键组子图$S e t$ 中。重复操作，直到所有邻域节点都被遍历完或这些顶点对子图的适应度都为负，扩展的过程将结束，得到关键组蛋白质 $S e t$ 。

d）根据式（18）计算 $\nu$ 对于关键组蛋白质Set的节点适应度，若 $P F C ( \nu , S e t ) > 0$ ，利用式（20）和（21）计算拾起放下概率，利用拾起放下规则来完成蚁群聚类过程；否则不进行操作，直接转向步骤f)。

e）重复步骤d)，根据改进的蚁群算法得到聚类个数M。

f)将上述得到的关键蛋白质节点集合 $L$ 和聚类个数M初始化FCM聚类算法的初始聚类中心 $\mid c \mid$ 和聚类个数M，根据式（2）计算隶属度矩阵 $u _ { i j }$ ，再根据式（22）修正更新隶属度矩阵 $u _ { i j }$ ，接着利用式(3)更新FCM算法的聚类中心 $c _ { j }$ 。

g）根据式（25）计算FCM目标函数 $J ( u , c , M )$ ，并判断$\left\| \operatorname { J } ( u , c , M ) ^ { k } - \operatorname { J } \left( u , c , M \right) ^ { k - 1 } \right\|$ 是否小于 $\boldsymbol { \varepsilon }$ 。 若（204号 $\left\| \operatorname { J } ( u , c , M ) ^ { k } - \operatorname { J } ( u , c , M ) ^ { k - 1 } \right\| < \varepsilon$ ，停止计算，输出聚类结果 $u _ { i j }$ ；否则返回到步骤 f)。

根据上述步骤说明，本文算法的描述实现如下：输入：蛋白质网络 $G ( V , E , P )$ 。输出：蛋白质复合物。a)初始化参数：蚂蚁数目为 $N$ ，蚁群迭代次数 $\tau$ ，拾起参数 $k _ { p }$ ，放下参数 $k _ { d }$ ，核心节点阈值 $\theta$ ， $\rho ~ , ~ \delta ~ , ~ \omega ~ , ~ .$ $\boldsymbol { \varepsilon }$ ， $\eta$ ：b)获得蛋白质聚类数目。(1)for $\scriptstyle t = 1$ to $\boldsymbol { \tau }$ （204号(2) for $\scriptstyle n = 1$ to $N$ （204(3) 调用关键蛋白质的选取过程，获得关键蛋白质集合L(4) 调用改进的蚁群聚类算法，获得聚类数目M(5) end for(6)end forc)挖掘蛋白质复合物(1）for each $\nu _ { i } \in V$ do(2）Initialize $F C M \gets L , M$ ， $\scriptstyle \mathbf { k } = \mathbf { 1 } / /$ 初始化 FCM 的初始聚类中心和聚类数目(3）Compute $u _ { i j }$ by using Eq.(2)(4）Modify $u _ { i j }$ by using Eq.(22)(5）Update $c _ { j }$ by using Eq.(3)(6）Compute $J ( u , c , M )$ by using Eq.(25)(7) $\mathbf { i } \mathsf { f } \left\| \mathbf { J } \left( u , c , M \right) ^ { k } - \mathbf { J } \left( u , c , M \right) ^ { k - 1 } \right\| < \varepsilon$ ，STOP(8) else(9) $k = k + 1$ return to (4)-(7)(10) end if(11）end for(12)return $u _ { i j }$ //得到蛋白质复合物

# 2.6算法的时间复杂度

FAC-PC算法的计算复杂度由以下几个步骤构成：假设PPI网络中节点度的最大值为 $d _ { \operatorname* { m a x } }$ ，依据边聚集系数以及基因表达数据构建加权PPI网路的时间复杂度为 $O ( \left| E \right| )$ ；采用EPS公式选取关键蛋白质节点的时间复杂度为 $O ( | V | )$ ；采用节点适应度选取关键组蛋白质的时间复杂度为 $O ( | V | ^ { 2 } )$ ；假设一个节点经过拾起放下完成聚类的比较次数为 $O ( I N k _ { 3 } k _ { 1 } | V | ^ { 2 } )$ ，符合关键阈值的节点个数为 $k _ { 3 } \left| V \right|$ ，那么蚁群聚类算法的时间复杂度为 $O ( I N k _ { 3 } | V | ^ { 2 } )$ ；采用FCM算法完成最终的复合物识别聚类过程的时间复杂度为 $O ( | V | ^ { 2 } )$ ；因此，FAC-PC 算法的时间复杂度为 $O ( \vert E \vert + \vert V \vert + \vert V \vert ^ { 2 } + I N k _ { 3 } \vert V \vert ^ { 2 } + \vert V \vert ^ { 2 } )$ 即 $O ( I N k _ { 3 } | V | ^ { 2 } )$ 。而在ACC-FMD算法中，算法的时间复杂度主要取决于种子节点的选取和蚁群聚类过程，即 $O ( N I | V | ^ { 3 } )$ ；在ACC-DPC 算法中，算法的时间复杂度主要取决于初始簇的构建和蚁群聚类过程即 $O ( T | V | ^ { 3 } )$ ；在GENA算法中，算法的时间复杂度主要取决于初始化以及优化集群的过程，即 $O ( B | V | ^ { 3 } )$ ；在WCOACH算法中，算法的时间复杂度主要取决于初始核的检测和添加附件形成蛋白质复合物的过程，即 $O ( \tau V | ^ { 3 } )$ ；在IMHRC 算法中，算法的时间复杂度主要取决于主要蛋白质集群形成以及合并修复集群的过程，即 $O ( p \gamma \beta | V | ^ { 2 } )$ 。上述提及的 $T$ 、τ、γ、 $\beta$ 和 $B$ 分别表示基因表达时刻数、邻域亲和力阈值、中心获取阈值、中心移除阈值以及预测到的模块数目。

# 3 实验结果以及分析

# 3.1实验环境

FAC-PC算法实验的编程环境为Python3.5.2；操作系统

为Windows10家庭中文版；内存12GB；处理器为Intel(R)Core(TM)i5-4200H CPU $\textcircled { a } 2 . 8 \ : \mathrm { G H z }$ 。

# 3.2实验数据集

为验证本文提出算法的有效性，选用蛋白质相互作用数据相对完整和可靠的酵母蛋白质相互作用网络数据作为实验数据。具体实验数据如下所示：

a）酵母PPI网络数据来源于DIP数据库[25],去除重复以及自相互作用，该数据库包含4995个蛋白质和21554对相互作用。

b）实验采用的时序基因表达数据为GSE3431[26],包含7079个蛋白质和36个时刻下的基因表达值。

c）本文采用CYC2008[27]作为标准数据集，该数据集包含408个通过生物实验预测得到的蛋白质复合物。

# 3.3评价指标

# 3.3.1精度、召回率和F-measure度量

本文采用文献[28]的精度（Precision）、召回率（Recall)和F度量（ $F$ -measure）指标来评价算法性能，这些指标的计算依赖于邻域亲和评分。邻域亲和评分主要用来评价预测的复合物与实际复合物的匹配度，其定义为

$$
O S \left( p , b \right) = \frac { i ^ { 2 } } { \left| V _ { p } \right| \left| V _ { b } \right| }
$$

其中： $\vert V _ { p }$ |和 $\left. V _ { b } \right.$ 分别表示预测复合物 $p = \left( V _ { p } , E _ { p } \right)$ 和已知复合物 $b = \left( V _ { b } , E _ { b } \right)$ 的规模； $i$ 表示预测复合物和标准复合物交集的规模。若 $O S ( p , b ) \geq \omega$ ，则认为 $p$ 和 $b$ 匹配，一般 $\omega$ 的取值为0.2或者0.25，本实验中取值为0.2。设 $P$ 为算法预测结果集合， $B$ 为标准复合物集合，则 $P$ 中至少与一个实际复合物相匹配的复合物数量可表示为 $N _ { c p } = \mid \{ p \in P , \exists b \in B , O S ( p , b ) \geq \omega \} \mid$ ；另一方面， $B$ 中至少与一个预测的复合物相匹配的复合物数量为 $N _ { c b } = \mid \{ b \in B , \exists p \in P , O S ( p , b ) \geq \omega \} \mid$ ,这复合物检测方法的精度和召回率的定义为

$$
p r e c i s i o n { = } \frac { N _ { c p } } { | P | }
$$

$$
r \mathrm { e } c a l l = \frac { N _ { c b } } { | \boldsymbol { B } | }
$$

为了避免灵敏度和特异性所带来的偏见，采用 $F$ -measure综合评价指标来评估整体算法的性能。其计算公式如下：

$$
F - m e a s u r e = \frac { 2 \times p r e c i s i o n \times r e c a l l } { p r e c i s i o n + r e c a l l }
$$

# $\theta$ 值度量

随着蛋白质组学研究的深入，使得一个蛋白质与其功能注释向对应成为可能，蛋白质簇发生对于一个给定功能注释在统计学上的意义就可以通过一个超几何分布的等式来进行计算[29]：

$$
P - w h w e \ = \ 1 - \sum _ { i = 0 } ^ { k - 1 } { \frac { { \binom { F } { i } } { \binom { V - F } { C - i } } } { \binom { V } { C } } }
$$

其中： $V$ 代表PPI网络中包含的蛋白质总数； $C$ 为预测挖掘出的复合物数目； $F$ 为一个功能组数量； $k$ 为 $C$ 中包含 $F$ 中的蛋白质数目。如果 $P$ -value越小，越接近0，则说明蛋白质复合物能够随机出现这种功能的概率就越低，可能更具有生物意义。一般地，将 $P$ -value的最小值对应的功能作为该蛋白质复合物的主要功能。通过给每个识别的蛋白质复合物赋予 $P$ -value最小对应的功能，可以预测未知蛋白质的功能。

# 3.4参数选择

FAC-PC算法中，由于参数 $\theta$ 和 $\varepsilon$ 的取值影响实验的聚类效果，所以本文在15 组 $\theta$ 和 $\boldsymbol { \varepsilon }$ 的参数取值上独立运行20 次实验，取20次实验的平均值进行分析。实验使用到的参数设置如下： $m = 2$ ， $\scriptstyle \rho = 0 . 1$ ， $I = 2 0$ ， $\scriptstyle { \omega = 0 . 2 }$ ， $\scriptstyle { \delta = 0 . 0 1 }$ 蚂蚁个数 $N = 5 0$ ，拾起参数 $k _ { p } = 0 . 9$ ，放下参数 $k _ { d } = 0 . 2$ ， $\scriptstyle \eta = 0 . 6$ 。表1给出了具体参数设置情况，其中Seti代表第 $i$ 组参数。图2(a）和（b)中parseti分别代表 $\boldsymbol { \varepsilon }$ 取0.0015、0.0045、0.0075对应的$F$ -measure值和匹配的蛋白质复合物比例，相应的实验结果如图2所示。

表1实验参数设置   

<html><body><table><tr><td colspan="6">Table 1 Experimental parameter setting</td></tr><tr><td></td><td colspan="5">θ取值范围</td></tr><tr><td>ε取值范围</td><td>0.1</td><td>0.2</td><td>0.3</td><td>0.4</td><td>0.5</td></tr><tr><td>0.0015</td><td>Set1</td><td>Set2</td><td>Set3</td><td>Set4</td><td>Set5</td></tr><tr><td>0.0045</td><td>Set6</td><td>Set7</td><td>Set8</td><td>Set9</td><td>Set10</td></tr><tr><td>0.0075</td><td>Set11</td><td>Set12</td><td>Set13</td><td>Set14</td><td>Set15</td></tr></table></body></html>

由图2可知，随着 $\theta$ 从0到0.2逐渐增大， $F .$ -measure的值在 $\varepsilon$ 不同取值之下也逐渐增大， $F$ -measure达到最大值0.577，实验识别的复合物和已知的复合物的匹配比例也逐渐增加；随着 $\theta$ 从0.2到0.5逐渐增大， $F$ -measure的值在 $\varepsilon$ 不同取值之下逐渐降低，实验识别出的复合物和已知的复合物的匹配比例也逐渐降低。这是因为本文融合边聚集系数与基因表达数据构建加权网络，设计EPS公式来选取关键节点，同时利用节点适应度PFC度量来逐步遍历关键节点的邻居时，充分考虑内部节点与外部节点之间的联系，随着关键阈值的增大，算法识别的聚类数目逐渐增加，呈上升趋势，实际上每个类中包含的蛋白质数目越少，而类的数目个数就会越多，但是当阈值增大到一定值时，被扩充的节点与关键节点的作用概率要求提高，邻居节点被扩充的可能性就会随之降低，所要求的挖掘的复合物精度逐渐增加，对节点的相关信息要求更高，所以挖掘出的蛋白质复合物会更严格，导致算法 $F$ -measure值和匹配比例先增加后降低。通过观察发现存在一对合理取值即 $\scriptstyle { \varepsilon = 0 . 0 0 1 5 }$ ， $\scriptstyle \theta = 0 . 2$ 使 $F$ -measure达到最大值0.453且匹配比例达到 $6 3 . 1 4 \%$ 。

![](images/3d60d14180db157c63588d122952125ca1cb7d8829fefc73a6b4c8d31bd08d92.jpg)  
  
图2 $F$ -measure值和匹配的蛋白质复合物比例变化图 Fig.2 $F$ -measure and matched protein complex scale change graph

# 3.5EPS 度量的有效性分析

为了验证FAC-PC算法使用基于基因表达信息和边聚集系数的EPS度量公式的有效性，分别基于使用EPS度量选取关键蛋白质的FAC-PC算法和ACC-FMD 算法，在DIP数据库上进行复合物的识别，实验得到的 $F$ -measure和匹配比例如图3所示。

![](images/fcfa1227d641b4e4d5c2f8e681a27a8de4abb726e0ef8cea690a21457ff902ec.jpg)  
图3EPS 度量对比分析

由图3显示，使用关键蛋白质选取EPS度量的FAC-PC算法在precision、recall、 $F$ -measure取值和匹配的蛋白质复合物比例都比未使用 EPS 度量的取值要高。其中 precision的取值比未使用EPS度量提高 $1 9 . 1 3 \%$ ，recall的取值比未使用EPS度量提高 $2 7 . 4 3 \%$ ， $F$ -measure的取值比未使用EPS度量提高 $2 4 . 4 6 \%$ ，匹配的蛋白质复合物比未使用EPS度量提高 $2 6 . 2 5 \%$ 。实验结果说明，使用改进的EPS度量的算法的聚类效果得到了提高。这是因为FAC-PC充分考虑网络的拓扑特性以及基因共表达程度，根据关键权重度量公式来选择关键蛋白质，进而组成关键组蛋白质来进行聚类。也进一步证明利用关键组蛋白质能很好扩展为一个复合物。

# 3.6PFC和SI度量的有效性分析

为了验证FAC-PC算法使用PFC度量和SI度量的有效性，分别基于PFC度量以及SI度量的FAC-PC 算法和ACC-DPC算法，在DIP数据库独立执行20次进行复合物的识别，实验检测结果对比分析如图4所示。

![](images/52759d6293d073edf4899fd1d70c844031096a5f2eb0f0f96787f71a3c51315c.jpg)  
Fig.3Comparative analysis ofEPS metric   
Fig.4Comparative analysis ofPFC and SI metrics

图4显示的是使用PFC和SI度量的FAC-PC 算法在precision、recall、 $F$ -measure取值和匹配的蛋白质复合物比例与未使用这两种度量的对比情况，其中使用这两种度量的precision的取值比未使用这两种度量提高 $9 . 2 3 \%$ ，recall的取值比未使用这两种度量提高 $3 9 . 8 1 \%$ ， $F$ -measure的取值比未使用这两种度量提高 $2 8 . 8 4 \%$ ，匹配的蛋白质复合物比未使用这两种度量提高 $2 . 8 8 \%$ 。这是因为本文根据EPS度量公式选取关键蛋白质节点，同时使用关键组蛋白质代替种子节点进行聚类，考虑到网络的拓扑特性以及基因表达程度，同时也考虑到复合物的模块性以及稠密度，严格控制蚁群拾起放下操作，挖掘的复合物较准确，避免非关键蛋白质无效的拾起放下操作，实验结果说明，使用这两种度量的算法的聚类效果较优。

# 3.7算法性能的比较分析

本节将FAC-PC分别从精度、召回率和 $F$ -measure的比较分析、聚类效果的比较分析和功能富集的比较分析与ACC-FMD[13]、ACC-DPC[14]、GENA[17]、WCOACH[18]和IMHRC[19]进行比较分析。重复迭代次数20次。实验使用到的参数设置如下： $m = 2$ ， $\scriptstyle { \rho = 0 . 1 }$ ， $I = 2 0$ ， $\scriptstyle { \delta = 0 . 0 1 }$ ， $\scriptstyle { \omega = 0 . 2 }$ ，蚂蚁个数 $N = 5 0$ ，拾起参数 $k _ { p } = 0 . 9$ ，放下参数 $k _ { d } = 0 . 2$ ， $_ { \varepsilon = 0 . 0 0 1 5 }$ ，$\scriptstyle \theta = 0 . 2$ ， $\scriptstyle \eta = 0 . 6$ 。

# 1）精度、召回率和 $F$ -measure的比较分析

为了验证本文算法的性能，将FAC-PC算法与其他五种算法在DIP数据上独立运行20次，取实验结果的平均值进行分析，得到各种算法识别的复合物基本信息以及实验评价指标对比分析如表2和图5所示。

表2各算法识别的复合物的基本信息  
Table 2Basic information of protein complexes for each algorithm   

<html><body><table><tr><td>算法</td><td>PM</td><td>average</td><td>Ncp</td><td>Ncb</td></tr><tr><td>ACC-FMD</td><td>283</td><td>9.5</td><td>150</td><td>113</td></tr><tr><td>ACC-DPC</td><td>237</td><td>7.8</td><td>137</td><td>103</td></tr><tr><td>GENA</td><td>290</td><td>5.6</td><td>136</td><td>87</td></tr><tr><td>WCOACH</td><td>354</td><td>10.3</td><td>147</td><td>82</td></tr><tr><td>IMHRC</td><td>366</td><td>12.7</td><td>210</td><td>102</td></tr><tr><td>FAC-PC</td><td>369</td><td>13.5</td><td>233</td><td>144</td></tr></table></body></html>

在表2中，PM表示算法识别出的复合物总数，average是指每个簇中的蛋白质平均个数。由表2可以知道，FAC-PC算法共识别369个复合物，每个复合物平均包含13.5个蛋白质，其中233个预测结果较准确，标准集合中的144个复合物可以被算法准确识别到。相较而言，本文算法对于挖掘蛋白质复合物算法具有更高的效率，这是因为本文是基于关键组蛋白质进行蚁群聚类，严格控制蚁群拾起放下操作，同时将通过蚁群聚类得到的聚类数目以及关键蛋白质节点初始化FCM算法，在利用改进的隶属度更新策略解决FCM的隶属度更新较慢问题，以及综合考虑类内和类间距差异，提出新的目标函数并完成复合物的识别，使得聚类的挖掘效果的准确度和收敛速度加快。

![](images/5cb94c0de354b1ef0ebff66c204585b7bdd3fcd85b1377795e24ae33d782f999.jpg)  
图4PFC 和SI度量对比分析  
图5算法性能比较关系图  
Fig.5Performance comparison of algorithm

图5显示了各种算法在DIP数据集中识别的复合物的结果。从图中可以清晰地发现FAC-PC算法在精度、召回率和$F$ 度量指标上取得较好的结果。具体来说，FAC-PC算法的精度为 $6 3 . 1 4 \%$ ，相较 ACC-FMD、ACC-DPC、GENA、WCOACH和IMHRC分别提高了 $1 9 . 1 3 \%$ 、 $9 . 2 3 \%$ 、 $34 . 6 4 \%$ 、$5 2 . 0 6 \%$ 和 $10 . 0 5 \%$ ；召回率为 $3 5 . 2 9 \%$ ，相较 ACC-FMD、ACC-DPC、GENA、WCOACH和IMHRC分别提高了 $2 7 . 4 3 \%$ 、$3 9 . 8 1 \%$ 、 $6 5 . 5 1 \%$ 、 $7 5 . 6 1 \%$ 和 $4 1 . 1 8 \%$ ；F值度量为 $45 . 2 8 \%$ 相较ACC-FMD、ACC-DPC、GENA、WCOACH和IMHRC分别提高了 $2 4 . 4 6 \%$ 、 $2 8 . 8 4 \%$ 、 $5 4 . 4 8 \%$ 、 $67 . 1 7 \%$ 和 $3 0 . 0 2 \%$ 。实验结果表明，使用本文算法挖掘蛋白质复合物的聚类精度、召回率和 $F$ -measure相比较其他五种算法都得到了提高。这是因为，在ACC-FMD 算法中，使用种子节点进行蚁群聚类，若种子节点之间的相似度较大，会出现重复的拾起放下操作，会挖掘出重叠模块，且存在大量的合并过滤，导致挖掘的时间效率低；在ACC-DPC算法中，初始聚类中心的选取仅仅考虑到网络的拓扑特性聚类系数，没有考虑到蛋白质基因生物信息，选择簇中心的条件比较单一，仅仅根据拾起放下规则，在聚类的过程中存在大量的拾起放下操作，导致挖掘出的效果不佳；在GENA算法中，使用贪婪方法初始化集群，在聚类系数的基础上选取种子节点，仅仅考虑了网络的拓扑特性，挖掘的效果存在大量的重叠模块；在WCOACH算法中，仅仅利用GO信息来构建加权网络，缺乏考虑蛋白质网络本身的拓扑特性以及特征，且在聚类时，若核心节点选取较为相似，则会挖掘出大量重叠的模块，最终导致挖掘的准确性降低；在IMHRC算法中，构建加权PPI网络时，仅仅考虑节点度即网络的拓扑结构，没有融合生物信息，考虑构建的加权PPI网络比较单一，使得挖掘聚类效果不佳。而本文是综合考虑网络的拓扑结构和生物基因表达信息来构建加权网络，基于关键组蛋白质进行蚁群聚类，同时根据适应度来严格控制拾起放下操作，在最终使用FCM算法完成聚类的时候，综合考虑类内和类间距以及设计隶属度更新策略来改进隶属度更新较慢等问题，可以较为精确和快速地挖掘出蛋白质复合物。因此，本文提出的算法的聚类效果较好。

# 2）聚类效果的比较分析

为评估本文提出的FAC-PC 算法的聚类效果，将本文算法与其他五种算法挖掘的Elongator holoenzyme 复合物可视化进行对比分析聚类效果，聚类结果如图6所示。图6显示了不同算法检测到的 Elongator holoenzyme 复合物结果，其中图6(a)是该标准复合物所包含的蛋白质相互作用情况；(b)是本文算法的检测结果；(c)是ACC-FMD 算法的检测结果；(d)是ACC-DPC算法的检测结果；(e)是GENA算法的检测结果；(f)是算法WCOACH的检测结果；(g)是IMHRC 算法的检测结果。通过图6显示，本文算法能够准确地识别蛋白质复合物；ACC-FMD算法识别出标准复合物中的6个蛋白质，但是也包含了4个非 Elongator holoenzyme 复合物内的蛋白质；ACC-DPC算法识别出标准复合物中的6个蛋白质，但是也包含了1个非Elongatorholoenzyme 复合物内的蛋白质；GENA算法识别出标准复合物中的6个蛋白质，但是也包含了2个非 Elongator holoenzyme 复合物内的蛋白质；WCOACH算法识别出标准复合物中的5个蛋白质；IMHRC算法识别出标准复合物中的6个蛋白质，但是也包含了3个非Elongatorholoenzyme复合物内的蛋白质。实验结果表明，本文算法挖掘的蛋白质复合物聚类效果较好。这是因为，本文通过蛋白质网络的拓扑特性和基因表达信息来构建加权网络，可以降低假阳性的影响；同时根据EPS度量选取关键蛋白质，在通过节点适应度PFC度量来进一步选取关键组蛋白质，利用关键组蛋白质进行蚁群聚类，这样减少大量的拾起放下和重复的合并过滤操作，进而提高聚类运行效率和准确性；将得到的关键蛋白质节点以及聚类数目初始化FCM，接着根据隶属度更新的改进策略改进隶属度更新较慢的缺陷，以及综合考虑类内和类间距，优化FCM的目标函数；最后利用改进的FCM完成蛋白质复合物的挖掘。实验结果表明，本文算法在识别蛋白质复合物上具有较好的聚类效果。

![](images/8fbe2239a5155ce38f9f27db188d7bdbcd6543a18d69b3704e04e06108aabda2.jpg)

(a)Standardcomplexes(b)CompondsdetectedbyFAC-PCalgoritm(c)ComplexesdetectedbyACC-FMDalgorithm(d)Complexesdetected by ACC-DPC algorithm

![](images/0bb37199d49c3d67dc5b73f58a7448ea8af32d1f3b089b2045ef6abf0a0faf3e.jpg)  
图6各个算法的复合物挖掘可视化比较  
Fig.6Visualization comparison of protein complexes of each algorithm

3）功能富集的比较分析 能富集分析。 $P$ -value被认为是衡量识别的复合物是一个真正为了测试算法识别的复合物的生物学意义，本文采用功的蛋白质复合物的可能性。识别的复合物的低 $P$ -value值表

明该复合物具有很高的统计学意义，一般将 $P$ -value的最小值对应的功能作为该功能模块的主要功能，通过给每个识别的复合物赋予最小的 $P$ -value值对应的功能，可以识别预测复合物的功能。若一个模块的 $P { \cdot } { \nu } a l u e { < } 0 { . } 0 1$ ，则认为这个复合物是显著的。显著的复合物数量在识别出的复合物总数中所占的比例可以很好地评价各个算法的整体性。具体各个算法性能比较分析如表3所示。

Table 3Significant statistics of protein complexes detected by each   

<html><body><table><tr><td colspan="4">algorithm</td></tr><tr><td>算法</td><td>PM</td><td>SC</td><td>Proportion</td></tr><tr><td>ACC-FMD</td><td>283</td><td>141</td><td>49.82%</td></tr><tr><td>ACC-DPC</td><td>237</td><td>160</td><td>67.51%</td></tr><tr><td>GENA</td><td>290</td><td>135</td><td>46.55%</td></tr><tr><td>WCOACH</td><td>354</td><td>263</td><td>74.29%</td></tr><tr><td>IMHRC</td><td>366</td><td>180</td><td>49.18%</td></tr><tr><td>FAC-PC</td><td>369</td><td>305</td><td>82.66%</td></tr></table></body></html>

在表3中，PM表示算法识别出的复合物总数，SC是具有显著意义的复合物数目。FAC-PC 算法识别的复合物数目

中显著性复合物的比例达到 $8 2 . 6 6 \%$ ，相比较 ACC-FMD、ACC-DPC、GENA、WCOACH和IMHRC算法分别提高了$6 5 . 9 2 \% \cdot 2 2 . 4 4 \% \cdot 7 7 . 5 7 \% \cdot 1 1 . 2 7 \% \cdot 6 8 . 0 8 \%$ 。由此可见，FAC-PC算法识别出的复合物具有很强的生物统计学意义。这是因为本文提出的算法在构建加权网络的时候，综合考虑网络的拓扑特性和基因共表达程度，同时利用关键组蛋白质来进行蚁群聚类，将关键蛋白质节点以及聚类数目初始化FCM，根据隶属度相对更新策略来改进隶属度的更新较慢的问题，同时还综合考虑类内和类间距对实验结果产生的影响，提出新的目标函数，最终导致聚类效果较好，执行效率高，挖掘的生物蛋白质复合物更具有生物统计意义。

表4具体给出本文FAC-PC算法识别出的复合物实例。其中OS表示复合物的匹配率，SM表示的是正确匹配的蛋白质个数，Predictedprotein表示组成复合物的所有蛋白质，加粗部分表示被匹配的蛋白质。从表4可以看出，当$P \mathrm { - } \nu a l u e { = } 2 . 2 2 \mathrm { E } \mathrm { - } 1 8$ 时，本文算法识别的NatC复合物的匹配率达到了0.82，正确匹配的蛋白质个数是9，这是因为YGR134W和YNL288W蛋白质与复合物内部连接比较松散。由此可见，FAC-PC算法识别的蛋白质复合物效果更好。

表3各个算法识别的复合物的显著性统计信息  
表4FAC-PC算法识别的复合物实例  
Table 4Instances of protein complexes detected by FAC-PC algorithm   

<html><body><table><tr><td>P-value</td><td>OS</td><td>SM</td><td>Predicted protein</td><td>Real complex</td></tr><tr><td rowspan="3">2.22E-18</td><td rowspan="3">0.82</td><td></td><td>YCR093WYER068WYGR134WYPR072WYNL288W</td><td rowspan="3">NatC</td></tr><tr><td>9</td><td>YIL038CYNR052CYDL165W YAL021CYDR443C</td></tr><tr><td>YPL011C</td><td></td></tr><tr><td rowspan="4">2.18E-29</td><td rowspan="4">0.79</td><td rowspan="4">20</td><td>YLR421CYDL007WYER021W YPR108W YHR200W</td><td rowspan="4">Giplp /Gle7p</td></tr><tr><td>YDL097CYKL145WYGR232WYFR004WYDL147W</td></tr><tr><td>YOR261CYDR427W YOR259CYOR117WYGL048C</td></tr><tr><td>YHR027CYIL075CYFR010WYFR052WYDR394W</td></tr><tr><td rowspan="3">1.90E-32</td><td rowspan="3">0.65</td><td rowspan="3">12</td><td>YGL004CYBR272CYER012W</td><td rowspan="3">Cde28p/Clb5p</td></tr><tr><td>Y0R116CYNL151CYJL011CYKR025WYDL150W</td></tr><tr><td>YNR003CYDR045CYKL144CYOR224CYPR190C YOR207CYPR110CYDR005C</td></tr><tr><td rowspan="4">1.56E-29</td><td rowspan="4">0.88</td><td></td><td>YBR253WYPR070WYMR112CYGR104CYOL051W</td><td></td></tr><tr><td>23</td><td>YCR081WYOL135CYGL152WYDL005CYBR193C YDR308CYLR071CYGL025CYPL042C YHR058C</td><td>Glycine cleavage</td></tr><tr><td rowspan="2"></td><td></td><td rowspan="2"></td></tr><tr><td>YNR010WYHR042CYNL025CYOR174WYPR168W</td></tr><tr><td></td><td></td><td>YER022WYNL236WYBL093CYPL248C</td><td></td></tr></table></body></html>

# 4 结束语

# 参考文献：

本文在结合边聚集系数与基因表达数据构建的加权蛋白质网络，提出一种基于模糊蚁群聚类的蛋白质复合物识别算法FAC-PC。基于边聚集系数与基因表达数据，设计EPS公式选取关键蛋白质节点，基于期望稠密度与模块度改进节点适应度，提出PFC公式获取关键组蛋白质；基于权重改进相似度计算，设计SI相似度度量优化蚁群算法的拾起放下概率，利用关键组蛋白质完成蚁群聚类，获得聚类数目；最后将关键节点以及聚类数目初始化FCM算法，同时改进隶属度的更新公式，提出兼顾类内和类间距新的FCM目标函数，最终完成复合物的识别。为了评估算法的性能，本文将FAC-PC算法与其他五种算法进行了对比。实验结果表明，FAC-PC算法具有更高的准确率、召回率，识别的复合物具有更强的生物统计意义。今后可以将FAC-PC算法应用于疾病预测和关键蛋白质识别等相关研究中。

[1]冀俊忠，高光轩．基于文化算法的 PPI 网络功能模块检测方法[J]. 北京工业大学学报，2017，43(1):0013-0021.(Ji Junzhong，Gao Guangxuan.Detecting functional module method based on cultural algorithm in protein-protein interaction networks [J]. Journal of Beijing UniversityofTechnology,2017,43(1):0013-0021.)   
[2] 郑文萍，李晋玉，王杰．基于遗传算法的蛋白质复合物识别算法[J]. 计算机科学与探索,2018,12(5):794-803.(Zheng Wenping,Li Jinyu, Wang Jie.Protein complex recognition algorithm based on genetic algorithm [J]. Journal of Frontiers of Computer Science and Technology, 2018,12 (5): 794-803.)   
[3]Cai Leixin,Chen Rong,Lyu Qiang.Selecting the best of the predictions of compound structures for protein docking by spectral clustering [J]. Journal of Chinese Computer Systems,2015,36 (10): 2365-2368.   
[4]李敏，王建新，刘彬彬，等．基于极大团扩展的蛋白质复合物识别算 法[J]．中南大学学报,2010,41(2):560-565.(LiMin,WangJianxin, Liu Bin bin,et al.An algorithm for identifying protein complexes based 2010,41 (2):560-565.)   
[5]Kessler J,Andrushchenko V,Kapitan J,et al.Insight into vibrational circular dichroism of proteins by density functional modeling [J]. Physical Chemistry Chemical Physics,2018,20 (7): 4926-4935.   
[6]Aldeco R,Marin I.Jerarca:efficient analysis of complex networks using hierarchical clustering [J]. PLoS ONE,2010,5(7): 11585-11591.   
[7]Abeysirigunawardena S C,Kim H，Lai J,et al.Evolution of protein-coupled RNA dynamics during hierarchical assembly of ribosomal complexes [J]. Nature Communications，2017，8(1): 492-500.   
[8] 雷秀娟，高银，郭玲．基于拓扑势加权的动态PPI网络复合物挖掘方 法[J].电子学报,2018,46(1):145-151.(Lei Xiujuan,Gao Yin,Guo Ling.Ming protein complexes based on topology potential weight in dynamic protein-protein interaction networks [J].Acta Electronica Sinica,2018,46(1): 145-151.)   
[9]Yao Xiaohui,Yan Jingwen，Liu Kefei，et al.Tissue-specific network-based genome wide study of amygdala imaging phenotypes to identify functional interaction modules[J].Bioinformatics,2017,33 (20): 3250-3257.   
[10] Trivodaliev K,Cingovska I,Kalajdziski S.Protein function prediction byspectral clusteringofproteininteractionnetwork[J]. Communications in Computer & Information Science,2011,8 (25): 108-117.   
[11]冀俊忠，杨明浩，杨翠翠，等．快速的基于蚁群聚类的 PPI 网络功能 模块检测方法[J]．北京工业大学学报，2016,42(8):1182-1192.(Ji Junzhong,Yang Minghao,Yang Cuicui,et al.Fast ant colony clustering for functional module detection algorithm in PPI networks [J]. Journal of Beijing University of Technology,2016,42 (8): 1182-1192.）   
[12] Ji Junzhong,Liu Hongxin, Zhang Aidong,et al. ACC-FMD:ant colony clustering for functional module detection in protein-protein interaction networks [J]. International Journal of Data Mining & Bioinformatics, 2015,11 (3):331-363.   
[13]赵学武，程新党，吕嘉伟，等．融合时序保持特征和蚁群聚类的动态 PPI 网络复合物识别[J]．小型微型计算机系统，2017，38(6): 1311-1316.(Zhao Xuewu,Cheng Xindang,Lyu Jiawei,et al.Identify protein complexes by integrating temporal function continue feature and ant colony clustering on dynamic PPI networks [J]. Journal of Chinese Computer Systems,2017,38 (6):1311-1316.)   
[14] Lei Xiujuan,Wu Fangxiang,Tian Jianfang,et al.ABC and IFC: modules detection method for PPI network [J]. Biomed Research International,2014,8(1): 968173-968183.   
[15]张媛，贾克斌,Zhang Aidong.基于多视图融合的蛋白质功能模块检 测方法[J].电子学报,2014,42(12):2337-2344.(Zhang Yuan,Jia Kebin,Zhang Aidong. Consistent protein functional module detection from multi-view of biological data [J].Acta Electronica Sinica,2014, 42 (12): 2337-2344.)   
[16] DimitrakopoulosC，Theofilatos K，PegkasA，et al.Predicting overlapping protein complexes from weighted protein interaction Intelligence in Medicine,2016,71(7): 62-69.   
[17] Kouhsar M, Zaremirakabad F,Jamali Y.WCOACH: Protein complex prediction in weighted PPI networks [J].Genes & Genetic Systems, 2016,91 (1): 47-47.   
[18] Ama M, Eslahchi C.Discovering overlapped protein complexes from weighted PPI networks by removing inter-module hubs [J]. Scientific Reports,2017,7(1):3247-3260.   
[19] Kesemen O, Tezel O, Ozkul E. Fuzzy c-means clustering algorithm for directional data (FCM4DD)[J].Expert Systems with Applications, 2016,58 (C): 76-82.   
[20]倪问尹，王建新，熊慧军，等．基于不确定数据的功能模块预测[J]. 四川大学学报,2013,45(5):0080-0087.(Ni Wenyin,Wang Jianxin, Xiong Huijun,et al. Research of detecting functional modules based on uncertainty data [J]. Journal of Sichuan University，2013,45 (5): 0080-0087.)   
[21]李敏，张含会，费耀平．融合PPI和基因表达数据的关键蛋白质识别 方法[J]．中南大学学报,2013，44(3):1024-1029.(Li Min,Zhang Hanhui,Fei Yaoping. Essential protein discovery method based on integration of PPI and gene expression data [J]. Journal of Central South University,2013,44(3):1024-1039.)   
[22]赵碧海,李学勇，胡赛，等．基于关键功能模块挖掘的蛋白质功能预 测[J].自动化学报,2018,44(1):183-192.(Zhao Bihai,Li Xueyong, Hu Sai,et al.Prediction of protein functions based on essential functional modules mining [J].Acta Automatica Sinica,2018,44(1): 183-192.)   
[23]刘翠翠，孙伟．基于加权网络和局部适应度的蛋白质复合物识别算 法[J].计算机应用研究,2018,35(8):2308-2310.(Liu Cuicui,Sun Wei.Algorithm for identifying protein complexes based on weighted network and local fitness[J]. Application Research of Computers,2018, 35 (8): 2308-2310.)   
[24] Xie X L,Beni G.A validity measure for fuzzy clustering [J].IEEE Trans on Pattern Analysis and Machine Intelligence,1991,13(8): 841-847.   
[25] Li Xiaoli,Wu Min,Kwoh C K,et al. Computational approaches for detecting protein complexes from protein interaction networks: a survey [J].BMC Genomics,2010,11 (Suppl 1): 1-19.   
[26] Tu B P,Kudlicki A,Rowicka M,et al.Logic of the yeast metabolic cycle: temporal compartmentalization of cellular processes [J]. Science, 2005,310 (5751): 1152-1158.   
[27] Pu S,Wong J,Turner B,et al.Up-to-date catalogues of yeast protein complexes [J]. Nucleic Acids Research,2009,37 (3): 825-831.   
[28] Zhang Yijia,Lin Hongfei,Yang Zhihao,et al.A method for predicting protein complex in dynamic PPI networks [J].BMC Bioinformatics, 2016,17 (Suppl 7): 229-239.   
[29] Lei Xiujuan, Wu Shuang,Liang Ge,et al. Clustering and overlapping modules detection in PPI network based on IBFO [J].Proteomics,2013, 13 (2): 278-290.