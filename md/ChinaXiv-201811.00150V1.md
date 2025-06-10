# 基于自然最近邻相似图的谱聚类

刘友超，张曦煌

(江南大学 物联网工程学院，江苏 无锡 214122)

摘要：谱聚类是基于谱图划分理论的一种聚类算法，由于其对非凸数据集具有优越的性能而广受欢迎，但是传统谱聚类算法经常在处理一些结构复杂的数据集时效果不甚理想，并且其相似度矩阵构造时参数的选取往往需要依靠多次实验及个人经验。在这种情况下，提出一种基于自然最近邻相似图的谱聚类（NSG-SC）算法。自然最近邻是一种新颖的最近邻概念，可以有效地避免K最近邻以及ε-最近邻方法需要人为设置参数的缺点。该算法构造相似度矩阵时依靠数据集自身的特性进行搜索，避免了参数选取不当以及离散点所带来的影响，更加真实地反映了数据集的结构关系。实验结果表明，提出的NSG-SC算法具有可行性和有效性。

关键词：谱聚类；自然最近邻；相似图；相似度矩阵 中图分类号：TP301.6 doi:10.19734/j.issn.1001-3695.2018.06.0460

# Spectral clustering based on natural nearest neighbor similarity graph

Liu Youchao, Zhang Xihuang (School of Internet of Things Engineering,Jiangnan University,Wuxi Jiangsu 214122,China)

Abstract:Thespectralclusteringisaclusteringalgorithmbasedonthe theoryofspectralpartitioning,anditisapopularethod due to itssuperiorperformance inthedatasets withnon-convex clusters.Butthe taditionalspectralclusteringalgorithmcannot oftengetcorrectresultsoncomplex data sets,andthechoiceofparameters ofafinitymatrixconstruction depends onmultiple testsandpersonal experience.Basedothesituation,thispaperproposesaspectralclusteringalgorithmbasedonnaturalnearest neighborsimilarity graph（NSG-SC）.Naturalnearestneighborisanovelconceptinterms ofnearestneighbor,anditcanavoid the disadvantagesof K-nearest neighborandε-nearest neighbor.Theyusuallyneed setparametersartificially efectively.The algorithmconstructsanafinitymatrix dependingonthecharacteristicsofthedatasets,anditavoidssomeadverseeffects.Itis that nappropriate choiceof parameters andisolated points causethem.The algorithm canalsoreflect beter characteristics of data.The results of experiments showthat the proposed algorithm named NSG-SC has feasibility and effectiveness.

Key words: spectral clustering; natural nearest neighbor; similarity graph; afnity matrix

# 0 引言

聚类分析是机器学习领域的一个重要分支，是人们认识和探索数据之间内在联系的有效手段。聚类分析作为一种重要的无监督学习方法，其主要思想是按照特定的标准，将数据划分到多个互不相交的簇，使其满足簇内数据具有较高的相似性，而簇间数据具有较低的相似性[1]。

到目前为止，已经有许多聚类的算法被提出。比较典型的有：基于划分的聚类方法，如K-means[2]、K-medoids[3]等；基于密度的聚类方法，如DBSCAN（density-based spatial clusteringof applications with noise）[4]、OPTICS（ordering points to identifythe clusteringstructure）[5]等；基于网格的聚类方法，如STING（statistical informationgrid）[6]等；基于层次的聚类方法，如

ROCK(A hierarchical clustering algorithm forcategoricalattributes)[7]、CURE（clustering using representatives）[8]等；基于模型的聚类方法以及基于图论的谱聚类方法。

谱聚类算法建立在谱图理论基础之上，其本质是利用谱松弛方法将聚类问题转换为图的最优划分问题。对比传统聚类算法，其能够在任意形状的样本空间上完成聚类，并且收敛于全局最优解。因此谱聚类也被广泛应用于生物信息学[9]，模式识别[10]，图像分割[11]及文本挖掘[12]等领域。

比较经典的谱聚类算法有 $\mathrm { N g }$ 等人提出的k路划分的NJW谱聚类算法[13]以及Zelnik-Manor 提出的自适应谱聚类算法[14]等。目前，对于谱聚类的研究主要集中在相似度矩阵构造、特征向量选取、自动确定聚类数目、拉普拉斯矩阵选取和海量数据运用等方面[15]。

在对谱聚类已知的这些研究方向中，相似度矩阵的构造是重中之中。因为其直接影响到特征向量的获取，从而影响到最终聚类的结果。有关谱聚类中相似度矩阵构造的研究一直没有停止。2011年，Yang等人提出了一种密度敏感的距离度量方法[16]。该度量方法定义了一个可调节长度的线段，该线段能适应不同密度区域的距离度量。在高密度区域中线段缩短，而在低密度区域中该线段则相应地拉长。该算法能处理多尺度聚类问题，对参数选择相对不敏感，但也存在着聚类效果不稳定，真实数据集上的效果欠佳等问题。2012年，Li等人使用邻近传播原则提出了一种新的相似度矩阵构建方法[17]，该相似度矩阵能增加同一簇中点对的相似度，从而更好地检测数据结构。2013年，Blekas等人提出了一个基于牛顿运动方程的谱聚类算法[18]。他们建立了一个潜在的轨道分析交互模型并且使用了牛顿预处理方法去获得有价值的相似性信息，丰富了相似度矩阵。2015年，Inkaya等人提出了一个基于密度和连通性的自适应相似图构建算法[19]，利用该算法可以对数据集构建相似图，之后再由相似图得到相似度矩阵，由此得到了一种新的谱聚类算法[20]。该算法有着能找到具有任意形状和可变密度的簇的局部特征以及表现稳定等优点，但是也存在着对噪声点的处理能力不强和存在混合聚类时数据点之间的邻近关系不是很精确等问题。

自然最近邻[21]是一种新型的最近邻概念，属于无尺度最近邻方法的范畴。该方法依靠数据集自身特性搜索，能有效地避免K最近邻以及ε-最近邻方法需要人为设置参数的缺点。本文借鉴了自然最近邻概念，用以代替传统谱聚类算法构建相似度矩阵时所采用的K近邻法、ε近邻法或全连接法。利用自然最近邻搜索算法构建一个免参数的相似图，再利用高斯核函数根据相似图构建相似度矩阵，最后再结合经典谱聚类算法的步骤，就可以得到一种基于自然最近邻相似图的谱聚类算法（spectralclustering based on natural nearest neighbor similarity graph，简称NSG-SC)。实验证明，本文所提出的NSG-SC算法具有更加优秀的聚类效果。

# 1 相关研究

# 1.1自然最近邻

最近邻的概念早在1951年就已经被提出，一经提出便受到广泛的关注及研究，现已广泛应用于人工智能、数据挖掘及模式识别等领域。现在使用最为广泛的两个最近邻概念均由Stenvens提出，分别是K最近邻及ε-最近邻。K最近邻的基本思想是找出数据集中每个对象周围与其距离最短的K个对象，其中参数K需要人工设置。ε-最近邻的基本思想则是找出数据集中每个对象周围半径ε范围内的对象，其中参数ε需要人工设置。可以看出，无论是K最近邻还是ε-最近邻，其最近邻的搜索都非常依赖于参数的设置，而不是根据数据集自身的特性进行搜索。

自然最近邻是一种近几年才提出的新型最近邻概念，其属于无尺度最近邻方法的范畴，不需要进行人工的参数设置，这也是其与K最近邻和ε-最近邻最大的区别。该方法受到人类社会友谊关系的启发，可以在不给定参数的情况下，根据数据集自身的属性特点，有效地确定数据集中的邻域，为每个数据点动态地选择数量不同的最近邻点。

自然最近邻的基本思想是根据密度划分，密度较大区域的数据点自然就拥有较多的近邻点，相对地，密度较小区域的数据点拥有的近邻点就较少。而数据集中相对离群的数据点只拥有几个或完全没有近邻点。正因为噪声点和异常点没有近邻点，所以正常点也不会把它们当成近邻点。

定义1 $\boldsymbol { r }$ 邻域。定义公式如下：

$$
K N N _ { r } ( x _ { i } ) = \bigcup _ { n = 1 } ^ { r } \{ f i n d K N N ( x _ { i } , n ) \}
$$

其中: $f i n d K N N ( x _ { i } , n )$ 表示 $K N N$ 搜索函数，它返回 $x _ { i }$ 的第 $\mathbf { \Omega } _ { n }$ 个最近邻， $K N N _ { r } ( x _ { i } )$ 表示原始数据集 $X$ 的一个子集。

定义2自然最近邻。基于 $\boldsymbol { r }$ 邻域，如果点 $X$ 在点 $Y$ 的 $\boldsymbol { r }$ 邻域中并且点 $Y$ 也在点 $\boldsymbol { \underline { X } }$ 的 $\boldsymbol { r }$ 邻域中，则称 $X$ 和 $Y$ 互为自然最近邻，具体定义公式如下：

$$
\begin{array} { l } { { x _ { j } \in N N ( x _ { i } ) } } \\ { { \iff ( x _ { i } \in K N N _ { r } ( x _ { j } ) ) \wedge ( x _ { j } \in K N N _ { r } ( x _ { i } ) ) } } \end{array}
$$

定义3稳定搜索状态。当且仅当满足如下条件时，自然最近邻算法达到稳定搜索状态：

$$
\begin{array} { r l } & { ( \forall x _ { i } ) ( \exists x _ { j } ) ( r \in N ) \land ( x _ { i } \neq x _ { j } ) } \\ & {  ( x _ { i } \in K N N _ { r } ( x _ { j } ) ) \land ( x _ { j } \in K N N r ( x _ { i } ) ) } \end{array}
$$

其中: $\boldsymbol { r }$ 是搜索轮数，若满足公式(3)则代表该轮搜索是稳定的，不需要提前终止搜索。

算法1自然最近邻搜索算法

Input :thedata set $X$   
$r = 1 , f l a g = 0 , N a N \_ E d g e = \emptyset$   
$\forall x \boldsymbol { i } \in X , N a N \_ N u m ( x \boldsymbol { i } ) = 0$   
while $f l a g = 0 d o$ （20 for all $x _ { i } \in X$ do $k n n _ { r } ( x i ) = f i n d K N N ( x _ { i } , r )$ $K N N _ { r } ( x _ { i } ) = K N N _ { r } ( x _ { i } ) \cup \{ k n n _ { r } ( x _ { i } ) \}$ 5 $f \ x _ { i } \in K N N _ { r } ( k n n _ { r } ( x _ { i } ) )$ （204 && $\{ k n n _ { r } ( x _ { i } ) , x _ { i } \} \not \in N a N _ { - } { l }$ Edgethen $\begin{array} { r l } & { N a N \mathrm { _ - } E d g e = N a N \mathrm { _ - } E d g e \cup \{ x _ { i } , k n n _ { r } ( x _ { i } ) \} } \\ & { N a N \mathrm { _ - } N u m ( x _ { i } ) = N a N \mathrm { _ - } N u m ( x _ { i } ) + 1 } \\ & { N a N \mathrm { _ - } N u m ( k n n _ { r } ( x _ { i } ) ) } \\ & { \qquad = N a N \mathrm { _ - } N u m ( k n n _ { r } ( x _ { i } ) ) + 1 } \end{array}$ end $i f$ （204号 end for $c n t = c o u n t ( N a N \_ N u m ( x _ { i } ) = = 0 )$ $r e p = r e p e a t ( c n t )$ $i f \ a l l ( N a N \_ N u m ( x i ) ) \neq 0 \parallel r e p \geq \sqrt { r - r e p } \ t h e n$ $f l a g = 1$ end $i f$ （204 $r = r + 1$   
end while   
$\lambda = r - 1$   
Output :NaN_Edge

其中: $N a N _ { - } E d g e$ 代表的是连接两个顶点之间的边的集合。把数据集 $\boldsymbol { \underline { X } }$ 中每个数据看做一个顶点，若两个顶点 $x _ { i }$ 和 $x _ { j }$ 之间插入了一条边，则将该边放入 $N a N _ { - } E d g e$ 集合中。函数count 的作用是统计 $N a N _ { - } N u m$ 集合中为0的元素的个数。函数repeat是为了统计变量 $c n t$ 连续出现的重复次数。

# 1.2NJW 谱聚类

NJW谱聚类算法是 $\mathrm { N g }$ 等人提出的一种比较经典的多路划分谱聚类算法[13]，其构建相似度矩阵采用的是基于高斯核函数的全连接法，该算法的基本步骤如下：

输入：初始数据集 $X = \{ x _ { 1 } , x _ { 2 } , \cdots , x _ { n } \}$ ，聚类数 $k$

输出：聚类结果C={Ci,C2,.,Ck}

a)构建相似度矩阵 $A$ ，定义公式如下：

$$
A _ { i j } = \left\{ { \begin{array} { l l } { e ^ { - { \frac { \| x _ { i } - x _ { j } \| ^ { 2 } } { 2 \sigma ^ { 2 } } } } \quad } & { i f i \neq j } \\ { 0 } & { o t h e r w i s e } \end{array} } \right.
$$

其中 $\sigma$ 为缩放参数，需要手动设置。

b)计算出度矩阵 $D$ 并利用 $D$ 和 $A$ 计算出拉普拉斯矩阵 $\mathbf { \Omega } _ { L }$ 。其中度矩阵 $D$ 定义公式如下：

$$
D _ { i j } = \left\{ \begin{array} { l l } { { \displaystyle \sum _ { j = 1 } ^ { n } A _ { i j } } } & { { ~ i f ~ i = j ~ } } \\ { { 0 } } & { { ~ o t h e r w i s \epsilon } } \end{array} \right.
$$

拉普拉斯矩阵 $L$ 定义公式如下：

$$
L = D ^ { - 1 / 2 } A D ^ { - 1 / 2 }
$$

c)计算出 $L$ 的前 $k$ 个最大特征向量 $\{ z 1 , z 2 , \cdots , z \boldsymbol { k } \}$ ，然后建立矩阵 $z$ 并将其标准化得到矩阵 $Y$ 。其中 $z$ 定义公式如下：

$$
Z = [ z 1 , z 2 , \cdots , z k ] \in R ^ { n \times k }
$$

$Y$ 定义公式如下:

$$
Y _ { i j } = \frac { Z _ { i j } } { \sqrt { \displaystyle \sum _ { j = 1 } ^ { n } Z _ { i j } } ^ { 2 } }
$$

# 2 NSG-SC算法

# 2.1算法思想

本文先根据算法1构建数据集的自然最近邻关系集合，得到集合 $N a N _ { - } E d g e$ 。之后再把原数据集中的每个数据点看做一个顶点，得到集合 $\boldsymbol { V }$ 。以 $N a N _ { - } E d g e$ 作为边的关系集合， $\boldsymbol { V }$ 作为顶点的关系集合，由此可以构建一个无向加权图，命名为NSG(natural nearest neighbor similarity graph)，定义如下：

$$
N S G = ( V , N a N _ { - } E d g e )
$$

NSG 由许多连通子图组成，其中每个连通子图代表一个潜在的簇，同一连通子图中的任意两个点之间都存在着一条或多条边可以将两点直接或间接连通。确定 $N S G$ 连通子图数量 $g$ ，将其与目标聚类数 $k$ 比较，如果 $g$ 大于 $k$ ，则表示存在着过多独立的簇。因此，在这种情况下新插入一条边 $( \nu _ { i } , \nu _ { j } )$ 在点 $x _ { i }$ 和$x _ { j }$ 之间。具体的 $( \nu { } _ { i } , \nu { } _ { j } )$ 定义如下：

$$
( \nu _ { i } , \nu _ { j } ) = \arg \operatorname* { m i n } \{ d _ { i j } \ : \vert \ : \nu _ { i } \in C _ { p } , \nu _ { j } \in C _ { q } , p \neq q \}
$$

其中 $C _ { p }$ 和 $C _ { q }$ 分别代表一个连通子图。

插入操作完成之后更新连通子图数量 $g$ 和相似图 NSG。重复比较 $g$ 和 $k$ ，进行连通子图合并操作直到 $g$ 和 $k$ 相等。NSG 如图1所示。其中红色的边代表NSG在合并子图之前便存在的边,蓝色的边代表合并子图之后新增加的边。

![](images/cecba271b5f7cf98aa489a49c898f4358520a1c36eda4371f701c75966ab8877.jpg)  
图1相似图 NSG  
Fig.1Similarity graph NSG

最后再利用高斯核函数构建相似度矩阵 $A$ ，定义公式如下：

$$
A _ { i j } = \left\{ \begin{array} { c c } { \displaystyle { \exp ( - \frac { { d _ { i j } } ^ { 2 } } { ( \operatorname* { m a x } { \{ d _ { i h } : ( i , h ) \in \mathrm { N a N } _ { - } \mathrm { E d g e } \} } ) ^ { 2 } } ) } } & { \mathrm { i f } ( i , j ) \in \mathrm { N a N \_ E d g e } } \\ { 0 } & { \mathrm { o t h e r w i s e } } \end{array} \right.
$$

其中： $\operatorname* { m a x } \{ d _ { i h } : ( i , h ) \in N a N \_ E d g e \}$ 表示同一连通子图中最长的边。

# 2.2算法描述

输入：初始数据集 $X = \ \{ x _ { 1 } , x _ { 2 } , \cdots , x _ { n } \}$ ，聚类数 $k$ （20输出： 聚类结果C={Ci,C2,,C}Step1 根据算法1得到关系集合 NaN_EdgeStep2 根据定义式(9)，构建无向加权图 NSGStep3确定 NSG 的各个连通子图构成及连通子图数量 $g$ ，再通过连通子图互相合并将其数量缩减至 $k$ 个

Step4利用式(11)构建相似度矩阵 $A$

Step5 依次进行1.2节中 NJW 谱聚类算法的 step2、step3、step4得到最终聚类结果 $c$

# 2.3算法时间复杂度分析

设待聚类原始数据集 $\boldsymbol { \underline { X } }$ 的样本数量为 $n$ ，根据1节算法1的步骤描述，在自然最近邻搜索阶段，算法的时间复杂度由以下几个主要步骤决定：a）创建可用于存储数据集的k-d树，此步骤的时间复杂度为 $O ( n \log n ) : { \mathsf { b } } )$ 对于单独一轮 $\boldsymbol { r }$ 自然最近邻搜索，其时间复杂度为 $O ( n \log { n } )$ 。一共进行了 $\lambda$ 轮搜索，所以搜索的总时间复杂度为 $O ( \lambda n \log n )$ ，其中 $2 \leq \lambda \leq n \circ \lambda$ 一般为6或7，对于高维或不规则的数据集，20≤λ≤30。

根据2.1节的NSG-SC 算法步骤描述，除自然最近邻搜索外其余步骤的时间复杂度由以下几个主要步骤决定：1）构建相似度矩阵，时间复杂度为 $O ( n ^ { 2 } )$ ；2）K-means 步骤，时间复杂度为 $O ( n k t )$ ，其中 $\mathbf { \Phi } _ { t }$ 为迭代次数，一般不超过300。

综上分析，在 $\mathbf { \Omega } _ { n }$ 较大的情况下，NSG-SC 算法的时间复杂度仍为 $O ( n ^ { 2 } )$ ，和一般的谱聚类算法时间复杂度相同。

如何确定目标聚类数 $k$

NSG-SC算法虽然在相似图构建过程中无须参数，但在之后的步骤中还是需要手动设置参数 $k$ 的值。确定目标聚类数 $k$ 其实是大多数聚类算法都存在的一个普适性问题，目前已经有各式各样或多或少成功的方法为这个问题提供了解决思路。

最常用且简单的方法是可视化数据，之后直接观察出聚成几类比较合适，但通常情况下这种方法并不奏效。在基于模型的聚类中，通常存在比较有效的标准可以从数据中选取 $k$ 值。这个标准通常基于数据的对数似然性，之后可以采取频率或贝叶斯方法来处理[22]。而在对基础模型没有或很少假设的情况下，则一般使用各种不同的指标来选取k值。常见地可以使用ad-hoc 度量方法如簇内和簇间相似性比率，过度信息理论标准[23]和间隔统计量等。

# 3 实验与分析

# 3.1相关算法及参数设置

本文算法分别与K-means 算法，NJW 谱聚类算法[13]（以下简称 NJW 算法)，Self-Tuning 谱聚类算法[4]（以下简称 ST-SC算法)和文献[20]提出的算法(以下简称DAN算法)进行比较。K-means 算法的参数 $k$ 为目标聚类数；NJW算法的参数 sigma为缩放参数，在此次实验中选取经验值sigma $_ { . = 0 . 0 0 5 }$ ，参数 $k$ 为目标聚类数；ST-SC算法的参数K为构建相似度矩阵时选取的每个点的最近邻K个点，这里设置为作者在原文中建议的值$\scriptstyle \mathrm { K = } 7$ ，参数 $k$ 为目标聚类数；DAN算法的参数 $k$ 为目标聚类数。本文提出的NSG-SC 算法的参数 $k$ 为目标聚类数。

# 3.2人工数据集实验及分析

为了验证NSG-SC算法的有效性，本文先将NSG-SC算法与K-means 算法、NJW 算法和 ST-SC 算法在图2 所示的四个人工合成数据集上进行实验。四种人工数据集分别是ChainLink、Sticks、ThreeCircles 和UnbalanceSpiral，其详细信息如表1所示。分别对这四种人工数据集进行实验后，实验的最终聚类结果如图2\~5所示。每张图左上为K-means 算法，右上为NJW算法，左下为ST-SC 算法，右下为NSG-SC 算法。

表1四种人工数据集  
Table 1 Four type of artificial data sets   

<html><body><table><tr><td colspan="3">Table1</td><td></td></tr><tr><td>数据集</td><td>实例数</td><td>维度</td><td>类别</td></tr><tr><td>ChainLink</td><td>1000</td><td>3</td><td>2</td></tr><tr><td>Sticks</td><td>512</td><td>2</td><td>4</td></tr><tr><td>ThreeCircles</td><td>1801</td><td>2</td><td>3</td></tr><tr><td>UnbalanceSpiral</td><td>567</td><td>2</td><td>3</td></tr></table></body></html>

对比分析可知，本文提出的NSG-SC 算法在四个数据集上均可以正确聚类；在ChainLink数据集上，ST-SC算法可以正确聚类，K-means 算法和NJW 算法在两个流形簇相互靠近的地方无法正确聚类；在Sticks数据集和UnbalanceSpiral数据集上，K-means 算法、NJW 算法和ST-SC 算法均出现不同程度的错误聚类，这表明簇间较高的相似度会导致这些算法的错误判断；在ThreeCircles 数据集上，ST-SC 算法可以正确聚类，K-menas算法和NJW算法的聚类则完全错误。通过实验表明，NJW算法和ST-SC算法构建的相似度矩阵在簇间相似度较高的情况下无法真实地反映出数据集结构，从而导致样本错误聚类。而NSG-SC算法利用自然最近邻相似图构建出的相似度矩阵，在数据集较为复杂且簇间相似度较高的情况下，仍能正确地反映出数据集的真实结构，从而得到正确的聚类结果。由此分析推断NSG-SC算法在处理复杂数据集时往往能获得更优秀的聚类结果。

![](images/8f7048bba29b5dd925a6076f8ac00d61f8f06cac1063c24da9abe87b7e733002.jpg)  
图2ChainLink数据集实验结果

![](images/e6f42ccb235d725fb0f1514f47ba28cac00c55aaad38a422cc6eee12568662d8.jpg)  
Fig.2Experiment results of ChainLink   
图3Sticks 数据集实验结果  
Fig.3Experiment results of Sticks

# 3.3评价指标

在接下来的真实数据集实验中，将分别采用ARI[24](adjusted rand index）和 AMI[25]（adjusted mutual information)这两个指标来评价K-means 算法、NJW 算法、ST-SC 算法、

![](images/e400d466671733b2a1f30c76396d60362eb20bf309270abb88b7f8cd154f7444.jpg)  
DAN算法与NSG-SC算法的效果。  
图4ThreeCircles 数据集实验结果

![](images/0972d251a0fe28b295a3765334cbb14479cb7d386f6fe22b8fea171f0a5906e7.jpg)  
Fig.4Experiment resultsofThreeCircles   
图5UnbalanceSpiral数据集实验结果  
Fig.5Experiment results ofUnbalanceSpriral

RI（randindex）在统计学中，特别是在聚类中，表示的是两个簇间的相似性度量。从数学的角度来看，RI指标与准确性有关。RI指标的取值范围为[O,1]。而ARI指标在RI指标的基础上进一步实现了“在聚类结果随机产生的情况下，指标应该接近零”的效果。ARI指标取值范围为[-1,1]，值越大意味着聚类结果与真实情况越吻合。从广义的角度来讲，ARI指标衡量的是两个数据分布的吻合程度。

MI(mutualinformation)是信息论里的一种有用信息度量，它可以看成是一个随机变量中包含的关于另一个随机变量的信息量，或者说是一个随机变量由于已知另一个随机变量而减少的不确定性。AMI指标是对MI指标的进一步改进，它常用于聚类，类似于ARI指标对于RI指标的纠正，并且与信息的变化密切相关。AMI指标同ARI指标一样，取值范围也是[-1,1],

值越大意味着聚类效果越好。

# 3.4真实数据集实验及分析

为了验证算法在真实数据集上的效果，判断算法是否具有实际意义，分别采用UCI数据库中的Iris、Wine、Vehicle和Landsat共四个数据集进行实验。数据集详细信息如表2所示。

Table Four type of UCI data   

<html><body><table><tr><td>数据集</td><td>实例数</td><td>维度</td><td>类别</td></tr><tr><td>Iris</td><td>150</td><td>4</td><td>3</td></tr><tr><td>Wine</td><td>178</td><td>13</td><td>3</td></tr><tr><td>Vehicle</td><td>846</td><td>18</td><td>4</td></tr><tr><td>Landsat</td><td>2000</td><td>36</td><td>6</td></tr></table></body></html>

经过真实数据集的实验后，ARI指标和AMI指标的评价结果如表3、4所示。

表2四种UCI数据  
表3各算法ARI指标对比  

<html><body><table><tr><td colspan="2">KMEANS</td><td>NJW</td><td>STSC</td><td>DAN</td><td>NSGSC</td></tr><tr><td>Iris</td><td>0.7302</td><td>0.5638</td><td>0.8857</td><td>0.5609</td><td>0.9122</td></tr><tr><td>Wine</td><td>0.3711</td><td>0.3963</td><td>0.7987</td><td>0.3885</td><td>0.8035</td></tr><tr><td>Vehicle</td><td>0.0785</td><td>0.0254</td><td>0.1270</td><td>0.2765</td><td>0.3988</td></tr><tr><td>Landsat</td><td>0.2975</td><td>0.5564</td><td>0.5231</td><td>0.7231</td><td>0.7105</td></tr></table></body></html>

表4各算法AMI指标对比

Table 3ARI index of algorithms comparison   
Table 4AMI index of algorithms comparison   

<html><body><table><tr><td colspan="2">KMEANS</td><td>NJW</td><td>STSC</td><td>DAN</td><td>NSGSC</td></tr><tr><td>Iris</td><td>0.7484</td><td>0.5821</td><td>0.8623</td><td>0.5910</td><td>0.8968</td></tr><tr><td>Wine</td><td>0.4226</td><td>0.4371</td><td>0.7593</td><td>0.3755</td><td>0.7544</td></tr><tr><td>Vehicle</td><td>0.0923</td><td>0.0445</td><td>0.1555</td><td>0.2976</td><td>0.4135</td></tr><tr><td>Landsat</td><td>0.3234</td><td>0.5897</td><td>0.6222</td><td>0.7960</td><td>0.8142</td></tr></table></body></html>

由表3和4的对比分析可知，Iris数据集上ST-SC算法和NSG-SC算法表现较好，具体在指标上NSG-SC算法略高于ST-SC 算法；Wine 数据集上ST-SC 算法和NSG-SC 算法仍表现较好，其中NSG-SC 算法的 ARI指标高于 ST-SC 算法，AMI指标低于ST-SC算法；Vehicle 数据集上所有算法表现均不理想，但NSG-SC算法的指标评价还是显著高于其他算法；Landsat数据集上DAN 算法和NSG-SC 算法表现较好，其中NSG-SC算法的ARI指标低于DAN算法，AMI指标高于DAN算法。综上所述，NSG-SC算法在真实数据集上的表现依然优越，能够真实地反映出数据集的结构关系，从而得到更好的聚类结果。

# 4 结束语

本文提出了一种基于自然最近邻相似图的谱聚类算法。利用自然最近邻关系无须设定参数、能基于数据集自身特性进行搜索和受离散点影响小等优点，精确地划分出每个样本的邻域，构建相似图，从而得到能比传统谱聚类算法使用的K近邻法、ε 近邻法或全连接法更为真实地反映样本相似性关系的相似度矩阵，最后再进行谱聚类。在人工数据集和UCI真实数据集上的实验表明NSG-SC 算法在处理一些结构复杂的数据集时，能更好地反映出数据集的结构关系，从而得到更优秀的聚类结果。

算法还有提升空间，后续研究可考虑引入模糊近邻关系处理混合聚类或加入成对约束信息优化聚类效果，还可考虑与启发式算法结合。

# 参考文献：

[1]Xu Rui,Wunsch D. Survey of clustering algorithms [J].IEEE Trans on Neural Networks,2005,16 (3): 645-678.   
[2]Jain AK.Data clustering: 5O years beyond K-means [J].Pattrn Recognition Letters,2010,31(8): 651-666.   
[3]Park HS,Jun CH.A simple and fast algorithm for K-medoids clustering [J]. Expert Systems with Applications,2009,36 (2): 3336-3341.   
[4] Yang Jing, Gao Jiawei, Liang Jiye,et al. An improved DBSCAN clustering algorithm based on data field [J]. Journal of Frontiers of Computer Science and Technology,2012,6 (10): 903-911.   
[5]Kalita HK,Bhattacharyya D K,Kar A.A new algorithm for ordering of points to identify clustering Structure based on perimeter of triangle: OPTICS(BOPT）[C]// Proc of the 15th International Conference on Advanced Computing and Communications.Piscataway,NJ: IEEE Press, 2007: 523-528.   
[6] Ansari S,Chetlur S,Prabhu S,et al.An overview if clustering analysis techniques used in data mining[J]. International Journal of Emerging Technology and Advanced Engineering,2013,3 (12): 284-246.   
[7]Agarwal P,Alam MA,Biswas R.A hierarchical clustering algorithm for categorical atributes [C]// Proc of the 2nd International Conference on Computer Engineering and Applications.Piscataway,NJ: IEEE Press,2010: 365-368.   
[8]Zhou Yajian,Xu chen,Li Jiguo.Unsupervised anomaly detection method based on improved CURE clustering algorithm [J].Journal on Communications,2010,31(7): 18-23.   
[9]Higham D J,Kalna G,Kibble M. Spectral clustering and itsuse in bioinformatics [J].Journal of Computational and Applied Mathematics, 2007,204 (1): 25-37.   
[10] Chih-Hsuan W. Recognition of semiconductor defect patterns using spatial filtering and spectral clustering[J].Expert Systems with Applications,2008, 34 (3): 1914-1923.   
[11] Shan Zeng,Rui Huang, Zhen Kang,etal. Image segmentation using spectral clustering of Gaussian mixture models [J]. Neurocomputing,2014,144: 346-356. using evolutionary manifold-ranking and spectral clustering [J].Expert Systems with Applications,2012,39 (3):2375-2384.   
[13] Ng A Y,Jordan M I,Weiss Y. On spectral clustering:analysis and an algorithm [C]// Advances in Neural Information Processing Systems. Cambridge,MA: MIT Press,2001: 849-856.   
[14] Zelnik-Manor L,Perona P. Self-tuning spectral clustering [C]//Advances in Neural Information Processing Systems. Cambridge,MA: MIT Pres, 2004, 17: 1601-1608.   
[15] Jia Hongjie,Ding Shifei,Xu Xinzheng,et al. The latest research progress on spectral clustering [J]. Neural Computing and Applications,2014,24: 1447-1486   
[16] Yang Peng, Zhu Qingsheng, Huang Biao.Spectral clustering with density sensitive similarity function [J]. Knowledge-Based Systems,2011,24 (5): 621-628.   
[17] Li Xinye,Guo Lijie.Constructing affinity matrix in spectral clustering based on neighbor propagation [J]. Neurocomputing,2012,97: 125-130.   
[18] Blekas K, Lagaris IE.A spectral clustering approach based on Newton's equations of motion [J]. International Journal of Intelligent Systems,2013, 28 (4): 394-410.   
[19] Inkaya T,Kayaligil S,Evin Ozdemirel N.An adaptive neighborhood construction algorithm based on density and connectivity [J]. Pattern Recognition Letters,2015,52: 17-24.   
[20] InkayaT.Aparameter-free similarity graph forspectralclustering[J].Expert Systems with Applications,2015,42: 9489-9498.   
[21] Zhu Qingsheng,Feng Ji, Huang Jinlong. Natural neighbor: a self-adaptive neighborhood method without parameter K[J].Pattern Recognition Letters, 2016,80: 30-36.   
[22] Fraley C,Raftery AE. Model-based clustering,discriminant analysis,and density estimation.[J] Journal of the American Statistical Association,2002, 97: 611-631   
[23] StillS, Bialek W.How manyclusters?An information-theoretic perspective. [J] Neural Computation,2004,16 (12): 2483-2506.   
[24] Santos JM,Embrechts M.On the use of the adjusted rand index as a metric forevaluating supervised classification [C]// Proc of International Conference on Artificial Neural Networks.Berlin: Springer,20o9:175-184.   
[25] Cai Deng,He Xiaofei, Han Jiawei.Document clustering using locality preserving indexing [J]. IEEE Trans on Knowledge and Data Engineering, 2005,17 (12): 1624-1637.