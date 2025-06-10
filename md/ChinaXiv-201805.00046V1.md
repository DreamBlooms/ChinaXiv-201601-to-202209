# 新模糊聚类有效性指标

耿嘉艺，钱雪忠，周世兵(江南大学 物联网工程学院，江苏 无锡 214122)

摘要：模糊聚类是模式识别、机器学习和图像处理等领域的重要研究内容。模糊C-均值聚类算法是最常用的模糊聚类实现算法，该算法需要预先给定聚类数才能对数据集进行聚类。提出了一种新的聚类有效性指标，对聚类结果进行有效性验证。该指标从划分熵、隶属度、几何结构角度，定义了紧凑度、分离度、重叠度三个重要特征测量。在此基础上，提出了一种最佳聚类数确定方法。将新聚类有效性指标和传统有效性指标在6个人工数据集和3个真实数据集进行实验验证。实验结果表明，所提出的指标和方法能够有效地对聚类结果进行评估，适合确定样本的最佳聚类数。

关键词：模糊C-均值聚类；聚类数；聚类有效性指标；模糊聚类中图分类号：TP391

New fuzzy clustering validity index

Geng Jiayi, Qian Xuezhong, Zhou Shibing (Shool of InternetofThings Engineering,Jiangnan University,Wuxi Jiangsu 214122)

Abstract:Fuzzyclustering isanimportantresearch contentinthefieldsofpattrrecognition,machine learmingand mage procesing.FuzzyC-means clustering algorithm is the mostcommonlyused fuzzyclusteringalgorithm.The algorithm needs to presetthe numberofclusters inorder to clusterthedata set.This paper proposeanew clustering validity index tovalidate the clusteringresults.This indexdefines the threeimportant features ofcompactness,resolutionandoverlap degree from the perspective of partition entropy,membershipdegree and geometric structure.On this basis,this paper propose a method of determining theoptimalclusteringnumber.Thispapervalidatethenewclusteringvalidityindexandthetraditional efectivene indexin six artificialdatasets andthreerealdatasets.The experimentalresults showthatthe proposed indexesandmethods canefectivelyevaluate theclusteringresultsandare suitablefordeterminingtheoptimalclustering numberof thesamples.

Key Words: fuzzy C-means clustering; number of clusters; clustering validity index; fuzzy clustering

# 0 引言

聚类是将没有先验知识的样本，按照特定的规则，将相似的样本归为一类，不相似的样本分到不同的类中{{1}}}。聚类分为两大方向，传统聚类和模糊聚类。传统聚类为硬划分，每个样本必须清晰的划分到不同的子类中，只有属于和不属于两种情况。但是现实中的大部分数据都具有不确定性，一个样本数据可能在不同程度上属于多个类{[}{2}{}}。因此，Ruspini{[}{3}{}引入了模糊划分的概念，从而出现了模糊聚类。相应地隶属度范围也从二值逻辑{0,1}扩展到[0,1]。模糊聚类相比传统聚类，更能反映出真实的世界。实现模糊聚类最常用的算法为Dunn{[}{4}{})提出的模糊C-均值算法（fuzzy C-Means，FCM）。该算法通过迭代，使目标函数最小化。FCM算法设计简单、解决问题的范围广。但是FCM算法需要通过聚类有效性验证，以确定最佳聚类数和判断分类结果的好坏{}(5}{}。

选择合适的聚类有效性指标是研究聚类有效性的重要步骤{){(6}(]。目前已经存在了许多聚类有效性指标，但是由于数据集的结构多种多样，没有一个聚类指标适用于任何类型的数据集，没有一种指标的表现总优于其他指标{7}{I]。比如朴尚哲等在文献{[}{8}{})中,列举了近年来一些常用的聚类有效性指标，包含基于隶属度的聚类有效性指标、基于类内紧致度和类间离散度的聚类有效性指标、基于熵和数据结构的聚类有效性指标等，这些指标只能在特定的数据集上发挥自己的优势，并不能运用在所有数据集上。本文针对现有模糊聚类有效性指标的不足，提出新的聚类有效性指标。该指标结合数据集的划分熵、隶属度以及数据结构，定义了紧凑度、分离度、重叠度，能够克服噪声和重叠的影响，准确地找到最佳聚类数。实验结果表明，新指标在人工数据集和真实数据集上均取得了良好的效果。

# 1 相关工作

# 1.1 FCM算法

FCM算法是基于目标函数的模糊C划分，通过优化目标函数得到均匀的 $\mathbf { \Psi } _ { c }$ 个模糊集 $\{ [ \} \{ 9 \} \{ ] \}$ 。目标函数是由隶属度、样本到聚类中心的偏差，两者结合构成。通过迭代，最小化目标函数，当迭代次数超过规定的数值或目标函数差值小于阈值时终止。FCM需要事先初始化聚类原型和给定聚类数。

假设数据集有n个样本，每个样本为p维 X={x,X,,X},X∈RP。目标函数为

$$
{ \bf { J } } _ { \mathrm { { m } } } ( { \bf { U } } , { \bf { V } } , { \bf { X } } ) { = } \sum _ { \mathrm { i = 1 } } ^ { \mathrm { c } } { \sum _ { \mathrm { k = 1 } } ^ { \mathrm { n } } { { \bf { u } } _ { \mathrm { i k } } ^ { \mathrm { m } } } \| { \bf { x } } _ { \mathrm { { k } } } { - \bf { V } } _ { \mathrm { i } } \| ^ { 2 } }
$$

隶属度矩阵约束条件：

$$
0 \leqslant \mathbf { u } _ { \mathrm { i j } } \leqslant 1 , 1 \leqslant \mathrm { i } \leqslant \mathrm { c } , 1 \leqslant \mathrm { j } \leqslant \mathrm { n }
$$

$$
\sum _ { i = 1 } ^ { c } \mathfrak { u } _ { \mathrm { i j } } { = } 1 , 1 { \leqslant } \mathrm { j } { \leqslant } \mathfrak { n }
$$

$$
0 \leqslant \sum _ { \mathrm { j = 1 } } ^ { \mathrm { n } } \mathbf { u } _ { \mathrm { i j } } \leqslant \mathrm { n , 1 \leqslant i \leqslant c }
$$

其中： $\boldsymbol { c }$ 表示聚类数； $\mathbf { m }$ 表示模糊程度，范围 $[ 1 , \infty ]$ ；U为 $\mathrm { c } ^ { * } \mathrm { N }$ 矩阵，表示样本属于模糊子集的隶属程度； $\mathrm { \Delta V }$ 为 ${ \mathsf { c } } ^ { * } { \mathsf { p } }$ 矩阵，表示聚类原型。FCM算法通过不断迭代更新聚类原型 $\mathrm { \Delta V }$ 和U,从而最小化目标函数。更新公式为：

$$
\mathrm { v _ { i } = \frac { \displaystyle \sum _ { k = 1 } ^ { n } u _ { i k } ^ { m } \mathbf { x } _ { k } } { \displaystyle \sum _ { k = 1 } ^ { n } \mathbf { u } _ { i k } ^ { m } } , 1 \leqslant i \leqslant c }
$$

$$
\mathbf { u } _ { \mathrm { i k } } = { \frac { \left\| \mathbf { x } _ { \mathrm { k } } - \mathbf { v } _ { \mathrm { i } } \right\| ^ { - { \frac { 2 } { \operatorname* { m } - 1 } } } } { \displaystyle \sum _ { \mathrm { i = 1 } } ^ { \mathrm { c } } \left\| \mathbf { x } _ { \mathrm { k } } - \mathbf { v } _ { \mathrm { i } } \right\| ^ { - { \frac { 2 } { \operatorname* { m } - 1 } } } } } , 1 \oplus \mathrm { i } \oplus \mathrm { c } , 1 \oplus \mathrm { k } \oplus \mathrm { n }
$$

FCM算法步骤如下：

a)给定参数C、模糊程度 $\mathrm { ~ m ~ }$ 、最大迭代次数和迭代终止条件。

b)初始化聚类原型，并更新模糊隶属矩阵U。

c)更新模糊聚类原型矩阵 $\mathrm { \Delta V }$ 。

d)如果大于迭代次数或目标函数差值小于阈值，则停止，否则转到步骤b)。

# 1.2传统聚类有效性指标

1)PC{D{{00

$$
\mathrm { { V } _ { \mathrm { { P C } } } = \frac { 1 } { n } \sum _ { j = 1 } ^ { c } \sum _ { i = 1 } ^ { n } u _ { i j } ^ { 2 } }
$$

划分系数PC形式简单，易于计算，但是仅考虑了每个集群的紧凑度，并且与数据的几何结构缺乏直接的联系。随着聚类数的变化，呈现单调趋势。这些不足直接导致指标无法验证具有大量小簇的分区和复杂数据集。

2)MPC{Dm{m

$$
\mathrm { \Delta V _ { M P C } = 1 - \frac { k } { k - 1 } ( 1 - V _ { P C } ) }
$$

指标对划分系数PC存在的单调递减趋势问题进行了优化，但是对于PC指标其他方面地缺陷并没有进行改进。指标在人工数据集上的效果不理想。

3)PE{D{1{2)}

$$
\mathrm { \Delta V _ { \mathrm { { p E } } } = - \frac { 1 } { n } \sum _ { j = 1 } ^ { c } \sum _ { i = 1 } ^ { n } u _ { i j } \mathrm { { l o g u } _ { i j } } }
$$

划分熵PE 指标简单，运算量小。同样存在以下问题：只考虑了每个集群的紧凑度；与数据集的几何结构缺乏联系；存在单调趋势。指标仅在分离较好的数据集上，表现良好，在噪声和重叠数据集上表现不佳。

4)XB{D{1}{(3}}

$$
\mathrm { V _ { \mathrm { { x B } } } = \frac { \displaystyle \sum _ { i = 1 } ^ { c } \sum _ { j = 1 } ^ { n } u _ { i j } ^ { m } \| v _ { i } - x _ { j } \| ^ { 2 } } { \displaystyle n \operatorname* { m i n } _ { i \neq j } \| v _ { i } - v _ { j } \| ^ { 2 } } }
$$

指标将数据的隶属度和几何结构考虑在内，紧致度为所有样本数据到聚类中心距离的和，分离度为类中心之间距离的最小值。该指标存在两个缺点：当 $\mathtt { c } \mathtt { \to } \mathtt { n }$ 时，XB指标变为0；当$\mathrm { m } {  } \infty$ 时， $\mathrm { X B }  \infty$ 。在上述两种情况下，指标失去稳定性，无法判断最佳聚类数。

5)UV{D{1{40)

$$
\mathrm { V _ { \mathrm { U V } } = \frac { 1 } { n } \sum _ { i = 1 } ^ { c } \sum _ { j = 1 } ^ { n } u _ { i j } ^ { 2 } + \frac { 1 } { n } \sum _ { i = 1 } ^ { c } \sum _ { j = 1 } ^ { n } u _ { i j } ^ { 2 } \mathrm { e x p } ( - \frac { \lVert \mathrm { x _ { j } - v _ { i } } \rVert ^ { 2 } } { \varepsilon } ) }
$$

$$
\varepsilon { = } \frac { 1 } { \mathrm { n } } \sum _ { \mathrm { j = 1 } } ^ { \mathrm { n } } { \| \mathbf { x } _ { \mathrm { j } } - \overline { { \mathbf { x } } } \| ^ { 2 } } , \mathrm { \overline { { x } } = } \frac { 1 } { \mathrm { n } } \sum _ { \mathrm { j = 1 } } ^ { \mathrm { n } } { \mathbf { x } _ { \mathrm { j } } }
$$

该指标引入指数函数测量数据与中心的距离，相比于欧氏距离，在一定程度上能够克服噪声对数据的影响，但是由于指标只考虑了集群的紧凑度和分离度，没有考虑重叠度对分类的重大影响，所以在重叠数据集上效果不是很理想。

6)FM{D{) {(5}0)

$$
\mathrm { V _ { \mathrm { F M } } = a _ { \mathrm { f } } \times ( - \frac { 1 } { n } \sum _ { i = 1 } ^ { c } \sum _ { j = 1 } ^ { n } [ u _ { i j } l o g ( u _ { i j } ) ] ) }
$$

$$
\mathrm { \mathfrak { a } _ { f } = \frac { \displaystyle \sum _ { i = 1 } ^ { c } \sum _ { j = 1 } ^ { n } ( \mathfrak { u _ { i j } } - 1 / c ) ^ { 2 } \lVert \mathbf { x _ { j } } - \mathbf { v _ { i } } \rVert ^ { 2 } } { \displaystyle n \operatorname* { m i n } _ { i \neq k } \lVert \mathbf { v _ { i } } - \mathbf { v _ { k } } \rVert ^ { 2 } } }
$$

该指标将划分熵和模糊划分因子这两个重要评价指标考虑在内，定义了聚类的紧致性和分离性。由于该指标采用相距最近两个类中心之间的距离作为的分离度，此类情况在噪声数据集上的表现不佳。

# 2 新聚类有效性指标

聚类有效性指标的好坏，直接影响着最终聚类结果的质量。新聚类有效性指标是由紧凑度、重叠度和分离度三者共同构成。紧凑度由类内距离表示，分离度由最小隶属度表示，重叠度由隶属度和划分熵相结合表示。好的聚类对应较小的紧凑度、重叠度，较大的分离度。该指标充分考虑了数据集的整体信息，能够准确地判断出数据集的最佳聚类数。

# 2.1 紧凑度

定义1 定义vs(cU)为第i类所有样本到第i类中心的平均距离，即

$$
\mathrm { v s ( c , U ) { = } \sum _ { i = 1 } ^ { c } } \sum _ { \mathrm { k = 1 } } ^ { \mathrm { n ( i ) } } { \frac { \left\| \mathbf { x } _ { \mathrm { k } } - \mathbf { v } _ { \mathrm { i } } \right\| ^ { 2 } } { \mathrm { n ( i ) } } }
$$

其中： $x _ { k }$ 表示第i类的第k个样本， $\nu _ { i }$ 表示第i类的聚类中心， $n ( i )$ 表示第i个聚类的样本数目。

定义2定义vd(c,U)为第i类所有样本两两之间的平均距 离，即

$$
\mathrm { v d ( c , U ) { = } \sum _ { i = 1 } ^ { c } \sum _ { k \neq \mathrm { h } } ^ { n ( i ) } \frac { \lVert \mathbf { x _ { k } - } \mathbf { x _ { h } } \rVert ^ { 2 } } { ( n ( i ) ^ { 2 } - n ( i ) ) / 2 } }
$$

其中：分母表示第i类所有样本两两之间距离的总个数。

定义3定义类内紧凑度 ${ \mathrm { V a r } } ( { \mathrm { c } } , { \mathrm { U } } )$ 为前两者相加（样本与中心距离的平均值、类内样本之间距离的平均值）的和，即：

$$
\scriptstyle \mathrm { V a r ( c , U ) = v s ( c , U ) ^ { * } v d ( c , U ) }
$$

$$
= \sum _ { \mathrm { i = 1 } } ^ { \mathrm { c } } \sum _ { \mathrm { k = 1 } } ^ { \mathrm { n ( i ) } } \frac { \left\| { \bf x _ { \mathrm { k } } } - { \bf v _ { \mathrm { i } } } \right\| ^ { 2 } } { \mathrm { n ( i ) } } \ast \sum _ { \mathrm { i = 1 } } ^ { \mathrm { c } } \sum _ { \mathrm { k \neq hslash } } ^ { \mathrm { n ( i ) } } \frac { \left\| { \bf x _ { \mathrm { k } } } - { \bf x _ { \mathrm { h } } } \right\| ^ { 2 } } { ( \mathrm { n ( i ) } ^ { 2 } - \mathrm { n ( i ) } ) / 2 }
$$

紧凑度表示类内样本的集中程度。为了解释相关概念，结合示意图进行说明。图1表示第i类的所有样本点到该类聚类中心的距离，值越小，说明类内样本距离类中心越近，表明了类内样本与类中心的结构关系；图2表示的第i类所有样本数据，两两之间的距离，值越小，说明类中的数据越紧，表明了类内样本数据的整体结构信息。类内紧凑度将两者结合起来，共同发挥各自的优势。显然Var(c,U)的最小值，表明类内的数据点彼此接近，具有较高的紧凑度。

![](images/f3ae239a21aa2fe71299dd47341d22e3c8a627b43b66000692a8fc3dafb992cc.jpg)  
图1类内样本与中心距离

![](images/98fdccb0dc7858b791165e53629216e8d7a8ee062bf2bcd55c983a7762732183.jpg)  
图2类内样本之间距离

![](images/293cc348dbba49482e1daf12e76c1cc6013af33aa51e6429fc51f944beac10c1.jpg)  
图3三个类分布示意图

# 2.2 分离度

定义4定义 $S _ { i j }$ 为第 $\mathbf { k }$ 个样本属于第i类和第j类之间最小的隶属度，即：

$$
{ \bf S } _ { \mathrm { i j } } = \operatorname* { m i n } _ { \mathrm { i } \neq \mathrm { j } } { ( { \bf u } _ { \mathrm { i k } } , { \bf u } _ { \mathrm { j k } } ) } , \mathrm { k } { = } 1 , 2 , . . . , \mathrm { n }
$$

定义5定义总体离散度 $\operatorname { s e p } ( \mathrm { c } , \mathrm { U } )$ 为 $S _ { i j }$ 总和的相反数，即

$$
\mathrm { S e p ( c , U ) { = } 1 { - } \frac { 1 } { c } \sum _ { i = 1 } ^ { c - 1 } \sum _ { j = i + 1 } ^ { c } ( \frac { 1 } { n } \sum _ { k = 1 } ^ { n } S _ { i j } ) }
$$

分离度表示两个模糊集群之间的分离程度。大部分指标的分离度通过计算类中心之间的距离，而类中心无法反映样本分布的整体形状，而且对于噪声数据使用距离判断会出现偏差。比如在图3中，两个类之间具有相同的距离，分离性也可以不同。AB与AC类中心的距离相等，但是明显AB比AC分离。此处新指标借鉴Chen 等{D}(l)}{6}{提出的分离度，通过一个样本数据相对两个类的模糊隶属度最小值作为分离度量，第k个样本越接近于一个类的距离中心，则相对该类的隶属度越接近于1，另一个类越接近于0，相应地定义4的值也越接近于0。此时类间模糊性也越小，类间越分离。总体离散度是将定义4的值求和，并取反求得，值越大，表示数据点相对于类的模糊程度越低，越能够清晰地划分到集群中，分离越好。

# 2.3 重叠度

定义6定义 $C _ { i j }$ 为第 $\mathbf { k }$ 个样本属于第i类和第j类之间隶属度的乘积，即

$$
\mathbf { C } _ { \mathrm { i j } } { = } \sum _ { \mathrm { k } = 1 } ^ { \mathrm { n } } ( \mathbf { u } _ { \mathrm { i k } } ^ { 2 } { * } \mathbf { u } _ { \mathrm { j k } } ^ { 2 } ) , \mathrm { k } { = } 1 , 2 , { \ldots } , \mathrm { n }
$$

定义7 定义总体重叠度 $\mathrm { C o p ( c , U ) }$ 为 $C _ { i j }$ 的总和与熵的结 合,即

$$
\mathrm { C o p ( c , U ) { = } \frac { 1 } { n } \sum _ { i = 1 } ^ { c - 1 } \sum _ { j = i + 1 } ^ { c } } \mathrm { C _ { i j } } ^ { * } \mathrm { f ( x _ { k } ) }
$$

$$
\mathrm { f ( x _ { k } ) { = } { - } \sum _ { i = 1 } ^ { \mathrm { { c } } } \sum _ { k = 1 } ^ { n } \ u _ { i k } { ^ { \ast } } l o g u _ { i k } }
$$

重叠度用于衡量界限不明确的两个类之间的重叠程度。两个类之间的重叠度定义为隶属度平方的乘积，当两个类别之间划分较清晰，隶属度之间相差越大，乘积的值越小，类划分时越明确，聚类结果越清晰。第k个样本相对于每类样本的隶属度都为 $1 / \mathrm { c }$ ，此时重叠度的值达到最大。这里与熵结合起来，可较好地反映出划分结果的模糊程度和不确定性度，值越小，它的不确性程度越小，需要的信息量越小，则分类效果越可靠，此处作为权重评价指标。显然总体重叠度的值越小，说明两个类之间划分越清晰，重叠越小。

# 2.4 归一化

由于紧致度、分离度和重叠度有不同的量纲，故需做归一

化处理，将各个聚类数对应地的指标值，除以最大的指标值，此时各度量范围变为[0,1]，其结果可表示为

$$
\mathrm { { V a r } ^ { n } ( c , U ) = \frac { V a r ( c , U ) } { V a r _ { \mathrm { m a x } } } , V a r _ { \mathrm { m a x } } = \operatorname* { m a x } _ { c } \left( V a r ( c , U ) \right) }
$$

$$
\mathrm { S e p } ^ { \mathrm { n } } ( \mathrm { c } , \mathrm { U } ) { = } \frac { \mathrm { S e p } ( \mathrm { c } , \mathrm { U } ) } { \mathrm { S e p } _ { \mathrm { m a x } } } , \mathrm { S e p } _ { \mathrm { m a x } } { = } \operatorname* { m a x } _ { \mathrm { c } } \left( \mathrm { S e p ( \mathrm { c } , \mathrm { U } ) } \right)
$$

$$
\mathbf { C o p } ^ { \mathrm { n } } ( \mathrm  c , U ) = \frac { C o p ( \mathrm { c , U ) } } { C o p _ { \mathrm { m a x } } } , C o p _ { \mathrm { m a x } } = \operatorname* { m a x } _ { \mathrm { c } } \left( C o p ( \mathrm { c , U ) } \right)
$$

2.5聚类有效性指标

$$
\scriptstyle \mathsf { W } ( \mathbf { c } , \mathbf { U } ) = \mathbf { V } \mathbf { a r } ^ { \mathrm { n } } ( \mathbf { c } , \mathbf { U } ) + { \frac { \mathbf { C o p } ^ { \mathrm { n } } ( \mathbf { c } , \mathbf { U } ) } { \mathbf { S e p } ^ { \mathrm { n } } ( \mathbf { c } , \mathbf { U } ) } }
$$

将划分熵、隶属度、几何结构这些模糊聚类中重要的特征结合起来，共同构成新聚类有效性指标。从紧凑度角度出发，希望 $\mathrm { V a r ( c , U ) ^ { \{ n \} } }$ 越小越好，表示类内距离越紧密；从分离度出发，希望 $\mathrm { S e p ( c , U ) ^ { \{ n \} } }$ 越大越好，表示类间距离越分散；从重叠角度出发，希望 $\mathrm { C o p ( c , U ) ^ { \{ n \} } }$ 越小越好，表示重叠达到最小。显然，W(c,U)越小，表示数据点被清晰地分到集群中，此时聚类效果最好。最佳聚类数与数据集的真实结构相符，找到最佳聚类数是聚类有效性指标的首要任务。该指标在噪声数据集、重叠数据集上，都能够准确地找到最佳聚类数。

# 3 确定最佳聚类数的算法

本文是在FCM算法和W聚类有效性指标下，提出的一种新的确定最佳聚类数的算法，解决了FCM需要事先确定最佳聚类数的问题，步骤如下：

a)初始化聚类数c 的选择范围为[Cmin、Cmax]。

b)c以1为单位递增，调用FCM算法，利用FCM得到的最优解（U,V），带入W指标。

c)计算并存储聚类有效性指标的值。

d)如果 $\mathsf { c } { \mathsf { < C m a x , c } } { \mathsf { = c } } { \mathsf { + } } 1$ ，转到步骤2，否则转到步骤5。

e)选取与最小指标值对应地c作为最佳聚类数。

f)输出最佳聚类数以及指标值。

# 4 实验结果

为了检验新聚类有效性指标能否取得良好效果，将新聚类有效性指标和已有的聚类有效性指标PC、MPC、PE、XB、UV、FM，应用于6个人工数据集和3个真实数据集，观察它们的聚类效果。聚类数搜索范围为[2,Cmax]， $\operatorname { C m a x } { = } { \sqrt { n } }$ 。指标中涉及的距离度量均为欧氏距离；参数 $\mathbf { m }$ 在何值取得最佳，尚缺乏理论指导，Pal 和Bezdek([}{1}{7}{}}提出 $\mathbf { m }$ 在[1.5，2.5]时FCM聚类算法的结果最好，实验首先取 $\mathrm { m } { = } 2$ 的情况。并且在不同的模糊加权m值下，观察新聚类有效性指标是否鲁棒。

# 4.1有效性实验

# 4.1.1人工数据集

图4为人工数据集分布结构示意图。DS1、DS2、DS3是高斯分布数据集，DS4、DS5、DS6是均匀分布数据集。DS1和

DS4数据集类与类之间分离明确；DS2和DS5数据集有150个噪声污染数据；DS3 数据集中，三类样本数据彼此之间存在较大的重叠，另两类分离较好；DS6数据集中，五类样本数据彼此之间都存在一定的重叠。

表1为人工数据集的具体数值信息和各个有效性指标计算得到的最佳聚类数，为了更直观地说明，图5详细地列出了DS2和DS3数据集的聚类数-指标关系图。针对分离较好的数据集DS1和DS4，所有指标均有效。针对噪声数据集：DS2数据集，PE 和FM得到的最佳聚类数为2类，其次才是4，XB则误判为6类，其余指标均可以有效的判定为4类；DS5数据集，仅有MPC、W能正确的判定为3类。针对重叠数据集：DS3和DS6由于重叠区域较多，传统聚类有效性指标失去判别能力，仅有W指标能够正确地判断这两个数据集的最佳聚类数为 5类。

![](images/5e4202a6f64dcb34e896fb11fd839fb2b55f39b46dda337735eb840f49c55d4b.jpg)  
图4人工数据集分布结构图

表17种有效性指标在人工数据集上的最佳聚类数（ $\mathrm { m } { = } 2$ ）  

<html><body><table><tr><td rowspan="2">数据</td><td rowspan="2">样本 样本</td><td colspan="11">实际</td></tr><tr><td>数目 维数</td><td>类数</td><td>PC</td><td></td><td>MPC</td><td>PE</td><td>最佳聚类数 XB</td><td>UV</td><td>FM</td><td></td><td>W</td></tr><tr><td>DS1</td><td>403</td><td>2</td><td>3</td><td></td><td>3</td><td>3</td><td>3</td><td>3</td><td>3</td><td></td><td>3</td><td>3</td></tr><tr><td>DS2</td><td>653</td><td>2</td><td>4</td><td></td><td>4</td><td>4</td><td>2</td><td>6</td><td>4</td><td></td><td>2</td><td>4</td></tr><tr><td>DS3</td><td>603</td><td>2</td><td>5</td><td></td><td>4</td><td>4</td><td>2</td><td>4</td><td>4</td><td></td><td>2</td><td>5</td></tr><tr><td>DS4</td><td>600</td><td>2</td><td>4</td><td></td><td>4</td><td>4</td><td>4</td><td>4</td><td>4</td><td></td><td>4</td><td>4</td></tr><tr><td>DS5</td><td>390</td><td>2</td><td>3</td><td></td><td>2</td><td>3</td><td>2</td><td>2</td><td>2</td><td></td><td>2</td><td>3</td></tr><tr><td>DS6</td><td>750</td><td>2</td><td>5</td><td></td><td>2</td><td>4</td><td>2</td><td>4</td><td>4</td><td></td><td>2</td><td>5</td></tr></table></body></html>

# 4.1.2真实数据集

真实数据集来源于公共数据库UCI数据库，是加州大学欧文分校提出的，用于机器学习常用的标准测试数据库。

a)Iris数据集：分为3类，分别为IrisSetosa、IrisVersicolour、IrisVirginica。在这个数据集上，有两类数据几乎不可辨别，另一个集群分离较好。所以,最佳聚类数判定为3类，次最佳为2类，这两种情况符合数据集的结构。传统指标判定2类为最佳，新聚类指标3类为最佳。

b)Wdbc 数据集：分为2类，分别为Malignant、Benign。

特征是从乳房块的细针抽吸（FNA）的数字化图像计算的，描述了图像中存在的细胞核的特征。核特征提取用于乳腺肿瘤诊断。以上所有指标都正确的判断出最佳聚类数为2。

c)Seeds数据集：分为3类，分别为三种不同品种的小麦籽粒Kama、Rosa和Canadian。只有新聚类有效性指标能正确地判断出聚类数为3类，其余指标均误判为2类最佳。

![](images/1c7032c1239d599e36315347c0ca2e2481cc0669d5487cfc3e211ed126cd8b2a.jpg)  
图57种有效性指标的聚类数-指标关系图

表2为真实数据集的具体数值信息和各个有效性指标计算得到的最佳聚类数，为了更直观地说明，图6详细地列出了Iris和Seeds数据集的聚类数-指标关系图。实验结果表明只有新聚类有效性指标可以在以上所有人工数据集和真实数据集下，正确判断出最佳聚类，在噪声和重叠数据都表现出了良好的效果。PC、PE、MPC指标缺乏跟数据结构的直接联系，因而得到的最佳聚类有效性指标对应的聚类个数与实际情况不符。XB 指标当m和c增加到一定程度，失去可靠性。UV和FM只考虑了紧凑度和分离度，没有考虑重叠度。新指标在一定程度上弥补了以上传统指标的缺点，具有较强的适应性。

表27种有效性指标在真实数据集上的最佳聚类数（ $\scriptstyle 1 = 2$ ））  

<html><body><table><tr><td rowspan="2">数据</td><td rowspan="2">样本 样本</td><td rowspan="2">实际</td><td colspan="8">最佳聚类数</td></tr><tr><td>维数</td><td>类数</td><td>PC</td><td>MPC</td><td>PE</td><td>XB</td><td>UV</td><td>FM</td><td>W</td></tr><tr><td>Iris</td><td>数目 150</td><td>4</td><td>3</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td><td>3</td></tr><tr><td>Wdbc</td><td>569</td><td>32</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td></tr><tr><td>Seeds</td><td>210</td><td>7</td><td>3</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td><td>3</td></tr></table></body></html>

![](images/c4775ede73290de3d033719f67469b40841ae64fb51c00e48a0cb217287dcd49.jpg)  
图67种有效性指标的聚类数-指标关系图

# 4.2m 的比较

m 为模糊加权指数，控制着聚类结果的模糊程度，正是由于m的引入，使传统聚类推广到模糊聚类。 $\mathbf { m }$ 根据已有经验一般选择范围在[1.5，2.5]。现将聚类有效性指标分别在 $\mathrm { m } { = } 1 . 5$ 、1.7、2、2.3、2.5五种情况下，应用于以上数据集。实验结果表明，PC、MPC、PE、XB和UV，随着 $\mathbf { m }$ 的变化，聚类结果发生变化，只有FM和W指标不随 $\mathrm { ~ m ~ }$ 的变化而变化，对 $\mathrm { ~ m ~ }$ 鲁棒;在聚类正确率方面，只有新提出的W指标，正确率为 $100 \%$ 。实验表明新指标在不同的 $\mathrm { ~ m ~ }$ 下，能够得到较好结果，有较强的可靠性和鲁棒性。

表3W在不同模糊加权指数下的最佳聚类数  

<html><body><table><tr><td>m</td><td>DS1</td><td>DS2</td><td>DS3</td><td>DS4</td><td>DS5</td><td>DS6</td><td>Iris</td><td>Wdbc</td><td>Seeds</td></tr><tr><td>1.5</td><td>3</td><td>4</td><td>5</td><td>4</td><td>3</td><td>5</td><td>3</td><td>2</td><td>3</td></tr><tr><td>1.7</td><td>3</td><td>4</td><td>5</td><td>4</td><td>3</td><td>5</td><td>3</td><td>2</td><td>3</td></tr><tr><td>2</td><td>3</td><td>4</td><td>5</td><td>4</td><td>3</td><td>5</td><td>3</td><td>2</td><td>3</td></tr><tr><td>2.3</td><td>3</td><td>4</td><td>5</td><td>4</td><td>3</td><td>5</td><td>3</td><td>2</td><td>3</td></tr><tr><td>2.5</td><td>3</td><td>4</td><td>5</td><td>4</td><td>3</td><td>5</td><td>3</td><td>2</td><td>3</td></tr></table></body></html>

表4PC在不同模糊加权指数下的最佳聚类数  

<html><body><table><tr><td>m</td><td>DS1</td><td>DS2</td><td>DS3</td><td>DS4</td><td>DS5</td><td>DS6</td><td>Iris</td><td>Wdbc Seeds</td><td></td></tr><tr><td>1.5</td><td>3</td><td>4</td><td>4</td><td>4</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td></tr><tr><td>1.7</td><td>3</td><td>4</td><td>4</td><td>4</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2</td><td>3</td><td>4</td><td>4</td><td>4</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2.3</td><td>3</td><td>4</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2.5</td><td>3</td><td>4</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td></tr></table></body></html>

表5MPC在不同模糊加权指数下的最佳聚类数  

<html><body><table><tr><td>m</td><td>DS1</td><td>DS2</td><td>DS3</td><td>DS4</td><td>DS5</td><td>DS6</td><td>Iris</td><td>Wdbc Seeds</td><td></td></tr><tr><td>1.5</td><td>3</td><td>6</td><td>4</td><td>4</td><td>5</td><td>4</td><td>2</td><td>2</td><td>3</td></tr><tr><td>1.7</td><td>3</td><td>6</td><td>4</td><td>4</td><td>3</td><td>4</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2</td><td>3</td><td>4</td><td>4</td><td>4</td><td>3</td><td>4</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2.3</td><td>3</td><td>4</td><td>4</td><td>4</td><td>3</td><td>4</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2.5</td><td>3</td><td>4</td><td>5</td><td>4</td><td>3</td><td>4</td><td>2</td><td>2</td><td>2</td></tr></table></body></html>

表6PE在不同模糊加权指数下的最佳聚类数  

<html><body><table><tr><td>m</td><td>DS1</td><td>DS2</td><td>DS3</td><td>DS4</td><td>DS5</td><td>DS6</td><td>Iris</td><td>Wdbc Seeds</td><td></td></tr><tr><td>1.5</td><td>3</td><td>5</td><td>4</td><td>4</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td></tr><tr><td>1.7</td><td>3</td><td>4</td><td>4</td><td>4</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2</td><td>3</td><td>2</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2.3</td><td>3</td><td>2</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2.5</td><td>3</td><td>2</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td></tr></table></body></html>

表7XB在不同模糊加权指数下的最佳聚类数  

<html><body><table><tr><td>m</td><td>DS1</td><td>DS2</td><td>DS3</td><td>DS4</td><td>DS5</td><td>DS6</td><td>Iris</td><td>Wdbc Seeds</td><td></td></tr><tr><td>1.5</td><td>3</td><td>6</td><td>4</td><td>4</td><td>4</td><td>4</td><td>2</td><td>2</td><td>2</td></tr><tr><td>1.7</td><td>3</td><td>6</td><td>4</td><td>4</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2</td><td>3</td><td>6</td><td>4</td><td>4</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2.3</td><td>3</td><td>4</td><td>5</td><td>4</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2.5</td><td>3</td><td>4</td><td>5</td><td>4</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td></tr></table></body></html>

表8UV在不同模糊加权指数下的最佳聚类数  

<html><body><table><tr><td>m</td><td>DS1</td><td>DS2</td><td>DS3</td><td>DS4</td><td>DS5</td><td>DS6</td><td>Iris</td><td>Wdbc Seeds</td><td></td></tr><tr><td>1.5</td><td>3</td><td>6</td><td>5</td><td>4</td><td>5</td><td>4</td><td>2</td><td>3</td><td>3</td></tr><tr><td>1.7</td><td>3</td><td>6</td><td>5</td><td>4</td><td>3</td><td>4</td><td>2</td><td>2</td><td>3</td></tr><tr><td>2</td><td>3</td><td>4</td><td>4</td><td>4</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2.3</td><td>3</td><td>4</td><td>4</td><td>4</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2.5</td><td>3</td><td>4</td><td>3</td><td>4</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td></tr></table></body></html>

表9FM在不同模糊加权指数下的最佳聚类数  

<html><body><table><tr><td>m</td><td>DS1</td><td>DS2</td><td>DS3</td><td>DS4</td><td>DS5</td><td>DS6</td><td>Iris</td><td>Wdbc Seeds</td><td></td></tr><tr><td>1.5</td><td>3</td><td>2</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td></tr><tr><td>1.7</td><td>3</td><td>2</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2</td><td>3</td><td>2</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2.3</td><td>3</td><td>2</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td></tr><tr><td>2.5</td><td>3</td><td>2</td><td>2</td><td>4</td><td>2</td><td>2</td><td>2</td><td>2</td><td>2</td></tr></table></body></html>

# 5 结束语

针对现有指标的缺陷，本文提出了W聚类有效性指标。根据在人工数据集和真实数据集上的实验结果表明，W指标可以在有噪声和类间存在重叠的情况下作出正确判断，并且与模糊加权指数的相关性很小，性能稳定。由于FCM算法的处理对象主要针对团簇状分布数据，对非团簇状分布数据有效性差。在今后的研究过程中，可以针对非团簇状分布数据的有效性问题进行深入的研究。

# 参考文献：

[1]Zalik KR.Cluster validity index for estimation of fuzzy clusters of different [J].Pattern Recognition,2010,43 (10): 3374-3390.   
[2]Yang Lei. Extending information-theoretic validity indices for fuzzy clustering [J].IEEE Trans on Fuzzy Systems,2017,25 (4): 1013-1018.   
[3]Ruspini EH. A New Approach to Clustering [J]. InfCont,1969,15 (1): 22-32.   
[4]Dunn J C.A Fuzzy relative of the ISODATA process its use in detecting compact well-separated clusters[J].Journal of Cybernetics,1974,3(3):32- 57.   
[5]Le Capitaine H, Carl Freli.A cluster-validity index combiningan overlap measure and a separation measure based on fuzzy-aggregation operators [J] IEEE Trans on Fuzzy Systems,2011,19 (3): 580-588.   
[6]Bezdek JC,Life Fellow.The generalized c index forinternal fuzzy cluster validity[J].IEEE Trans on Fuzzy Systems.2016,24(6):1500-1512.   
[7]高新波，谢维信．模糊聚类理论发展及应用的研究进展[J].科学通报, 1999,44 (21): 2241-2251.   
[8]朴尚哲，超木日力格，于剑．模糊C 均值算法的聚类有效性评价[J]. 模式识别与人工智能,2015,28(5):452-461.   
[9]Tas demir K.Avalidity index for prototype-based clustering ofdata sets with complex cluster structures [J].IEEE Trans on Systems,2011,41(4):1039-1053.   
[10]范九伦．基于模糊熵的聚类有效性函数_范九伦[J].模式识别与人工 智能,2001,14(4):390-394.   
[11] Liliane Silva.An Interval-based framework for fuzzy clustering applications [J].IEEE Trans on Systems,2015,23 (6): 2174-2187.   
[12]毕凯．基于模糊测度和证据理论的模糊聚类集成方法[J].控制与决策, 2015,30(5):823-830.   
[13] Xie XL,Beni G.A validity measure for fuzzy clustering[J]. IEEE Trans on Pattern Analysis and Machine Intelligence,1991,13 (8): 841-847.   
[14]张宇献，刘通．基于改进划分系数的模糊聚类有效性函数[J].沈阳工 业大学学报,2014,36(4):431-435.   
[15]孟令奎，胡春春．基于模糊划分测度的聚类有效性指标[J].计算机工 程,2007,33 (11): 15-17.   
[16] Chen M Y,Linkens DA. Rule-base self-generation and simplification for data-driven fuzzy models [J].Fuzzy Sets and Systems,2004,142 (2): 243- 265.   
[17]Pal NR,Bezdek JC.On Cluster Validity for the fuzzy C-Means model [J]. IEEETrans onFuzzy Systems,1995,3(3):370-379.