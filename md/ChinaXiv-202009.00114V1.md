# 联合结构化图学习与/范数谱嵌入的鲁棒聚类算法

汤立伟，张家珲，彭勇，孔万增(杭州电子科技大学 计算机学院，杭州 310018)

摘要：谱聚类算法一般是在给定的输入图上进行谱分解，然后通过后置处理(如K均值聚类或谱旋转)得到最终的聚类结果。此类方法存在两个不足：a)将图的构造与谱分解割裂成两个独立的阶段，导致了结果的次优性；b)常用的基于 $l _ { 2 }$ 范数度量谱特征向量的相似性具有噪声敏感性。为了克服上述两点不足，提出基于联合结构化图学习与 $l _ { 1 }$ 范数谱嵌入的鲁棒聚类算法(记为CLRL1)。在该算法框架下，一方面图的学习过程与聚类过程可以有效结合起来进行协同优化，另一方面 $l _ { 1 }$ 范数的使用可以很好地约束谱特征向量的相似性以提升算法的鲁棒性。在多个常用数据集上进行的实验结果表明，改进的算法聚类性能得到了明显的提升。

关键词：谱聚类；结构化图学习； $l _ { 1 }$ 范数；联合学习 中图分类号：TP18 doi:10.19734/j.issn.1001-3695.2020.01.0034

Robust clustering algorithm based on joint structured graph learning and $l _ { 1 }$ -norm spectral embedding

Tang Liwei, Zhang Jiahui, Peng Yong†, Kong Wanzeng (SchoolofComputer Science&Technology,Hangzhou Dianzi University,Hangzhou310o18,China)

Abstract:Givenafixed graph,the graph-based clustering usuallperforms the eigen-decomposition toobtain the spectral eigenvectors based on which we need to conduct post-processng steps such as Kmeans or spectral rotation to obtain the final clustering asignments.This paradigm maycause two limitations:a)this two-stage strategy breaksdown the connection between the graph construction and the calculation of spectral eigenvectors;and b) the $l _ { 2 }$ -norm based similarity measure between spectral eigenvectors isusuallsensitiveto noise.Todeal with these twolimitations,this paper proposedarobust clustering algorithm based on joint structured graph learning and $l _ { 1 }$ -norm spectral clustering, termed CLRL1.In the proposed framework,ononehandthe graphlearning processandthe clustering processcanbeoptimizedtogethertowards theoptimum; on the other hand,the $l _ { 1 }$ -norm similarity measure of spectral eigenvectors is used to improve the model robustness. Experiments on extensive benchmark data sets show the effectiveness of the proposed algorithm.

Key words: spectral clustering; structured graph learning; $l _ { 1 }$ -norm; joint learning

# 0 引言

聚类是机器学习与数据挖掘领域一类重要的数据分析方法并得到了广泛的应用，例如图像分割[1和复杂网络分析。聚类是一个将数据样本划分为多个类簇的过程，其目标是使得簇内样本的相似度较高，而簇间样本的相似度较低。常用的聚类方法有k均值聚类[2,3]，基于图的谱聚类方法[4\~7]等；一般情况下，两类方法都可以取得较好的聚类效果。

传统的谱聚类方法都需要经过两个阶段，第一阶段是基于样本数据关系图的构造，第二阶段是采用优化手段对图拉普拉斯矩阵进行谱分解以得到聚类标志矩阵。通常这样获得的聚类标志矩阵是连续的并且可能含有负值，需要再通过k均值方法或者是谱旋转方法来进行离散化已得到最终的聚类结果。这种两阶段的方式将图的构造与谱分解割裂成两个独立的过程，造成了最终结果的次优性。因此，传统谱聚类算法具有以下两个缺陷：a）无法从图中直接获得最终的聚类结果，还需采用其他的聚类方法以获得聚类结果。b）谱聚类结果依赖于构造图的质量，对特定图的构造方法极其敏感[8]。

2范数是传统谱聚类算法普遍运用于度量数据间相似度的度量指标，它具有噪声敏感性，一般情况下仅适用于对高斯噪声进行建模。相比之下， $\ell _ { 1 }$ 范数[9更适合于稀疏的大噪声，

可以提高模型的鲁棒性[10]。

本文提出了一种新型基于结构化图学习的范数谱嵌入聚类方法，能有效弥补了传统谱聚类的缺陷。本文在真实数据集和加噪数据集上做了大量实验，结果表明本文提出的新型聚类算法的表现超过同类算法，具有良好的收敛性和鲁棒性。

# 1 算法的提出

图聚类学习一般是在给定的图上进行，假定与图相对应的相似矩阵为 $\mathbf { W } \in \mathbb { R } ^ { n \times n [ 1 1 ] }$ (这里 $n$ 为数据点的个数)。如果基于数据样本构造的图 $\mathbf { w }$ 质量不高，将直接导致聚类的效果变得不理想。本文的目标是在图 $\mathbf { w }$ 的基础上学习一个新的具有良好特性的结构化图 $\mathbf { S } \in \mathbb { R } ^ { n \times n }$ 。显然，S应该是非负的[12],并且行和为1的。除此之外，本文基于如下的定理来给出关于S的秩的约束[13,14]。

定理1拉普拉斯矩阵中零特征值的个数等于图关联矩阵对应的图中连通分量的个数。

本文希望S具有秩 $k$ （假定聚类的类簇个数为 $k$ ，根据上述定理，将其转换为对应的拉普拉斯矩阵的秩的约束为$r a n k ( { \bf L } { \bf s } ) = n - k _ { \scriptscriptstyle \mathrm { ~ \odot ~ } }$ 这里 $\mathbf { L } _ { \mathbf { S } } = \mathbf { D } _ { \mathbf { S } } - ( \mathbf { S } + \mathbf { S } ) / 2$ ，其中Ds为对角的度矩阵，第 $i$ 个对角元素定义为 $\begin{array} { r } { ( \mathbf { D } \mathbf { s } ) _ { i i } = \sum _ { i } s _ { i j } } \end{array}$ 。基于图关联矩阵 $\mathbf { W }$ ，进行结构化图S的学习，可以通过优化如下的目标函数来实现，其中S1表示矩阵S与向量1相乘， $\mathbf { S 1 } = \mathbf { 1 }$ 即约束矩阵S行和为1。

$$
\operatorname* { m i n } _ { \mathbf { s } \geq \mathbf { 0 } , \mathbf { s } \mathbf { 1 } = \mathbf { 1 } } \left\| \mathbf { S } - \mathbf { W } \right\| _ { 2 } ^ { 2 } , \ s . t . \ r a n k ( \mathbf { L } _ { \mathbf { s } } ) = n - k .
$$

假定 $\sigma _ { i } ( { \bf L } { \bf s } )$ 是 $\mathbf { L _ { S } }$ 的第 $_ i$ 小特征值，鉴于图拉普拉斯矩阵具有半正定性质，显然 $\sigma _ { i } ( { \bf L } _ { \bf S } ) \geq { \bf 0 }$ ；因此(1)式可等价于

$$
\operatorname* { m i n } _ { \mathbf { s } \geq \mathbf { 0 } , \mathbf { S } \mathbf { 1 } = \mathbf { 1 } } \| \mathbf { S } - \mathbf { W } \| _ { 2 } ^ { 2 } + \gamma \sum _ { i = 1 } ^ { k } \sigma _ { i } ( \mathbf { L } \mathbf { s } ) .
$$

当正则化参数 $\gamma$ 足够大时，(1)式中的约束条件近似被(2)式中的第二项满足。假设数据 $\mathbf { x } _ { i } \in R ^ { d \times 1 }$ 对应的聚类标志向量为 $\mathbf { f } _ { i } \in R ^ { 1 \times k }$ ，根据 Ky Fan 定理[14]，(2)式可以写成

$$
\operatorname* { m i n } _ { \mathbf { s } , \mathbf { F } } \| \mathbf { S } - \mathbf { W } \| _ { 2 } ^ { 2 } + \gamma \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } s _ { i j } \| \mathbf { f } ^ { i } - \mathbf { f } ^ { j } \| _ { 2 } ^ { 2 } ,
$$

$$
\boldsymbol { t } . \ \mathbf { S } \geq \mathbf { 0 } , \mathbf { S 1 } = \mathbf { 1 } , \mathbf { F } \in \mathbb { R } ^ { n \times k } , \mathbf { F } ^ { T } \mathbf { F } = \mathbf { I } _ { k } .
$$

这里的 $\mathbf { F }$ 为聚类标志矩阵，其第 $i$ 行对应于 $\mathbf { f } ^ { i }$ 。

可以看到，式(3)中的第二项，对于聚类标志向量 $\mathbf { f } ^ { i }$ 和 $\mathbf { f } ^ { j }$ 相似性的度量使用的是 $\ell _ { 2 }$ 范数。一般来说， $\ell _ { 2 }$ 范数比较适合于刻画高斯类误差，而且是噪声敏感的。这里本文采取文献[9]中提出的 $\ell _ { 1 }$ 范数[15]，来提高模型的鲁棒性[15,16]，即采用如下的基于 $\ell _ { 1 }$ 范数的谱嵌入模型：

$$
\operatorname* { m i n } _ { \mathbf { F } ^ { T } \mathbf { F } = \mathbf { I } } \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } s _ { i j } \| \mathbf { f } ^ { i } - \mathbf { f } ^ { j } \| _ { 2 } .
$$

构造一个 $n ^ { 2 }$ 维度的向量 $\mathbf { p }$ ，使得 $\mathbf { p }$ 的第 $( ( i - 1 ) * ( n + j ) )$ （204号个元素为 $s _ { i j } \| \mathbf { f } ^ { i } - \mathbf { f } ^ { j } \| _ { 2 }$ 。最小化 $\mathbf { p }$ 的 $\ell _ { 1 }$ 范数会使最终得到的目标变得更加稀疏，从而产生一个更利于聚类结果的 $\mathbf { F }$ 。所以式(4)实际上是一个广义的 $\ell _ { 1 }$ 范数，这里本文沿用文献[9]的命名。

结合文献[8,9]的思想，本文提出最终的优化算法模型：

$$
\operatorname* { m i n } _ { \mathbf { s } , \mathbf { F } } \| \mathbf { S } - \mathbf { W } \| _ { 2 } ^ { 2 } + \gamma \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } s _ { i j } \| \mathbf { f } ^ { i } - \mathbf { f } ^ { j } \| _ { 2 } ,
$$

$$
\mathbf { \boldsymbol { s . t . } } \ \mathbf { S } \geq \mathbf { 0 , S 1 } = \mathbf { 1 , F } ^ { T } \mathbf { F } = \mathbf { I } _ { k } .
$$

该目标函数的正则化项是非平滑的，本文提出了一种迭代的算法去求解，即交替优化图关联矩阵S与聚类标志矩阵$\mathbf { F }$ ，直至目标函数收敛为止。如图1所示，传统的谱聚类先构图后进行谱分解，本文提出的CLRL1算法联合进行图的构造与谱分解，并且采用了结构化图学习与 $\ell _ { 1 }$ 范数普嵌入的方法以提高模型的鲁棒性。

![](images/04094bfec199110a88673305ef199f5044b756ad0e432322f21bb9e5cf66c1a3.jpg)  
图1CLRL1算法与传统谱聚类算法的流程对比 Fig.1Comparison of CLRL1 and traditional spectral clustering algorithm

# 2 模型的优化

为优化目标函数式(5)，本文在固定一个变量的情况下求解另一个变量。以下是每个变量更新规则的详细推导过程。

a）固定F更新S。问题式(5)中与S关联的目标函数为

$$
\begin{array} { c } { { \displaystyle \displaystyle \operatorname* { m i n } _ { { \bf S } } \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } ( s _ { i j } - w _ { i j } ) ^ { 2 } + \gamma \sum _ { i , j = 1 } ^ { n } d _ { i j } s _ { i j } , } } \\ { { s . t . ~ s _ { i j } \ge 0 , \displaystyle \sum _ { j = 1 } ^ { n } s _ { i j } = 1 . } } \end{array}
$$

这里 $d _ { i j } = \lVert { \bf f } ^ { i } - { \bf f } ^ { j } \rVert _ { 2 }$ ，即 $\mathbf { d } _ { i }$ 是一个向量，其第 $_ j$ 个元素为$d _ { i j } ($ 同理得 ${ \bf { s } } _ { i }$ 和 $\mathbf { w } _ { i }$ 。对 ${ \bf { S } } _ { i }$ 进行配方，可得：

$$
\operatorname* { m i n } _ { \mathbf { s } _ { i } } \frac { 1 } { 2 } \left\| \mathbf { s } _ { i } - ( \mathbf { w } _ { i } - \frac { \gamma } { 2 } \mathbf { d } _ { i } ) \right\| _ { 2 } ^ { 2 } , s . t . \mathbf { s } _ { i } \geq \mathbf { 0 } , \mathbf { s } _ { i } ^ { T } \mathbf { 1 } = 1 .
$$

该式实际上对应一个单纯形约束下的欧式距离问题。令$\begin{array} { r } { \mathbf v _ { i } = \mathbf w _ { i } - \frac { \gamma } { 2 } \mathbf d _ { i } } \end{array}$ ，(7)式对应的拉格朗日函数为

$$
\mathcal { L } ( \mathbf { s } _ { i } ) = \frac { 1 } { 2 } \left\| \mathbf { s } _ { i } - \mathbf { v } _ { i } \right\| _ { 2 } ^ { 2 } - \eta ( \mathbf { s } _ { i } ^ { T } \mathbf { 1 } - 1 ) - \mathbf { s } _ { i } ^ { T } \boldsymbol { \beta } .
$$

其中 $\eta \in \mathbb { R }$ 和 $\beta \in \mathbb { R } ^ { n \times 1 }$ 为拉格朗日乘子。本文将 $\mathbf { s } _ { i }$ 具体的求解算法总结在算法1中，具体的推导过程可参见文献[17]。

算法1固定 $\mathbf { F }$ 求得S的算法

输入：给定的向量 $\mathrm { ~ v ~ i ~ } 2 ~ \mathrm { ~ R ~ } ^ { \mathrm { ~ n ~ f ~ 1 ~ } }$   
输出：目标向量si2Rnf1。  
a)计算 $\mathrm { \Delta g = \ v _ { i } \ r }$ $\frac { \mathrm { ~ 1 ~ 1 ~ } ^ { \mathrm { ~ T ~ } } } { \mathrm { ~ c ~ } } \mathrm { ~ v ~ } _ { \mathrm { ~ i ~ } } + \mathrm { ~ \frac ~ { ~ 1 ~ } ~ { ~ c ~ } ~ } 1$   
b)根据牛顿法得到根;  
c)对于每个t2 [1;c]，得到最优的 $\mathrm { s _ { i } ^ { ( t ) } } \ d { \stackrel { \ldots } { } } = \mathrm { ( g _ { t } \ d { \cdot } \ d { \Omega } _ { 1 } \ d { \bigcirc } \ d { \bigcirc } \ d { \bigcirc } \ d { \bigcirc } \ d { \bigotimes } \ d { } _ { + } }$ 。b）固定S更新 $\mathbf { F }$ 。关于变量 $\mathbf { F }$ 的拉格朗日函数为

$$
\mathrm { ~ L ~ ( F ~ ) = ~ \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } s _ { i j } k f ^ { i } ~ i ~ { \bf ~ f } ^ { j } k _ { 2 } ~ i ~ { \bf ~ \mathrm { T } } r ( \bigcirc ( F ^ { \mathrm { ~ T ~ } } F ~ i ~ I ) ) { \bf : \mathrm { } } }
$$

定义S是S的重加权的图关联矩阵，即

$$
\tilde { s } _ { i j } = \frac { s _ { i j } } { 2 \lVert \mathbf { f } ^ { i } - \mathbf { f } ^ { j } \rVert _ { 2 } } ,
$$

其对应的拉普拉斯矩阵为 $\widetilde { \mathbf { L } } = \widetilde { \mathbf { D } } - \widetilde { \mathbf { S } }$ ,D是一个对角矩阵，第行的对角元素是 $\textstyle \sum _ { j = 1 } ^ { n } { \tilde { s } } _ { i j _ { \circ } }$ 使用式(9)对 $\mathbf { F }$ 求导并令导数为零，可以得到

$$
\frac { \partial \mathcal { L } ( \mathbf { F } ) } { \partial \mathbf { F } } = \widetilde { \mathbf { L } } \mathbf { F } - \mathbf { F } \pmb { \Lambda } = \mathbf { 0 } .
$$

显然，聚类标志矩阵 $\mathbf { F }$ 的解为矩阵 $\widetilde { \mathbf { L } }$ 前 $\mathbf { k }$ 个小特征值对应的特征向量所组成的矩阵。因为L是依赖于 $\mathbf { F }$ ，因此需要迭代的更新F和L。

本文将目标函数(5)的整个优化过程总结在算法2中。

算法2联合结构化图学习与 $\ell _ { 1 }$ 范数谱嵌入的鲁棒聚类算法

输入：数据 $\mathbf { X } \in \mathbb { R } ^ { d \times n }$ ，类簇个数，正则化参数 $\gamma$ 。

输出：聚类标志矩阵 $\mathbf { F } \in \mathbb { R } ^ { n \times k }$

a)初始化。根据HeatKernel函数来计算图关联矩阵$\mathbf { W } \in \mathbb { R } ^ { n \times n }$ (邻域为5，带宽参数设置为数据点对距离的平均值)；计算对应的拉普拉斯矩阵L,并对其进行特征分解以初始化F。

b)当算法未收敛时执行：固定 $\mathbf { F }$ ，根据算法1更新S；根 据式(10)计算S与L；固定S，根据式(11)更新F;

下面对算法优化过程的收敛性进行简要分析。CLRL1模型的求解分为两部分，一部分是求解S，另一部分是求解 $\mathbf { F }$ 。由于S是解析解，故只需证明 $\mathbf { F }$ 的收敛性[18]。

引理1对于任意非零向量 $\mathbf { f } _ { t } \in \mathbb { R } ^ { k }$ ，有如下不等式成立

$$
\| \mathbf { f } \| _ { 2 } - { \frac { \| \mathbf { f } \| _ { 2 } ^ { 2 } } { 2 \| \mathbf { f } _ { t } \| _ { 2 } } } \leq \| \mathbf { f } _ { t } \| _ { 2 } - { \frac { \| \mathbf { f } _ { t } \| _ { 2 } ^ { 2 } } { 2 \| \mathbf { f } _ { t } \| _ { 2 } } } .
$$

证明 显然 $( \sqrt { f } - \sqrt { f _ { t } } ) ^ { 2 } \ge 0$ ，故有

$$
\begin{array} { c c c } { { ( \sqrt { f } - \sqrt { f _ { t } } ) ^ { 2 } \geq 0 \implies f - 2 \sqrt { f f _ { t } } + f _ { t } \geq 0 \implies } } \\ { { \sqrt { f } - \displaystyle \frac { f } { 2 \sqrt { f _ { t } } } \leq \frac { \sqrt { f } } { 2 } \implies \sqrt { f } - \displaystyle \frac { f } { 2 \sqrt { f _ { t } } } \leq \sqrt { f _ { t } } - \displaystyle \frac { f _ { t } } { 2 \sqrt { f _ { t } } } } } \end{array}
$$

将式(13)中的 $f$ 和ft使用 $\| \mathbf { f } \| _ { 2 } ^ { 2 }$ 和|ft|进行代换，即得到式(12)。

根据引理1，本文给出如下关于算法1收敛性的定理。

定理2CLRL1算法将在每次迭代中单调减小目标函数式(5)第二项的值，并收敛到问题的局部最优值。

证明当S固定时，根据CLRL1算法的执行步骤5，可以得到

$$
\mathbf { F } _ { t + 1 } = \arg \operatorname* { m i n } _ { \mathbf { F } ^ { T } \mathbf { F } = \mathbf { I } } \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } \tilde { s } _ { i j } \| \mathbf { f } ^ { i } - \mathbf { f } ^ { j } \| _ { 2 } ^ { 2 } .
$$

其中 $\begin{array} { r } { \tilde { s } _ { i j } = \frac { s _ { i j } } { 2 \| \mathbf { f } ^ { i } - \mathbf { f } ^ { j } \| _ { 2 } } } \end{array}$ ，所以

$$
\sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } \frac { s _ { i j } \| \mathbf { f } _ { t + 1 } ^ { i } - \mathbf { f } _ { t + 1 } ^ { j } \| _ { 2 } ^ { 2 } } { 2 \| \mathbf { f } _ { t } ^ { i } - \mathbf { f } _ { t } ^ { j } \| _ { 2 } } \leq \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } \frac { s _ { i j } \| \mathbf { f } _ { t } ^ { i } - \mathbf { f } _ { t } ^ { j } \| _ { 2 } ^ { 2 } } { 2 \| \mathbf { f } _ { t } ^ { i } - \mathbf { f } _ { t } ^ { j } \| _ { 2 } } .
$$

根据引理1，可以得到

$$
\begin{array} { r } { \displaystyle \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } s _ { i j } ( \| \mathbf { f } _ { t + 1 } ^ { i } - \mathbf { f } _ { t + 1 } ^ { j } \| _ { 2 } - \frac { \| \mathbf { f } _ { t + 1 } ^ { i } - \mathbf { f } _ { t + 1 } ^ { j } \| _ { 2 } ^ { 2 } } { 2 \| \mathbf { f } _ { t } ^ { i } - \mathbf { f } _ { t } ^ { j } \| _ { 2 } } ) } \\ { \displaystyle \leq \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } s _ { i j } ( \| \mathbf { f } _ { t } ^ { i } - \mathbf { f } _ { t } ^ { j } \| _ { 2 } - \frac { \| \mathbf { f } _ { t } ^ { i } - \mathbf { f } _ { t } ^ { j } \| _ { 2 } ^ { 2 } } { 2 \| \mathbf { f } _ { t } ^ { i } - \mathbf { f } _ { t } ^ { j } \| _ { 2 } } ) } \end{array}
$$

将不等式(15)和(16)两边相加，可得

$$
\sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } s _ { i j } \| \mathbf { f } _ { t + 1 } ^ { i } - \mathbf { f } _ { t + 1 } ^ { j } \| _ { 2 } \leq \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } s _ { i j } \| \mathbf { f } _ { t } ^ { i } - \mathbf { f } _ { t } ^ { j } \| _ { 2 } .
$$

根据不等式(17)，在t轮迭代过后，算法将收敛。达到收敛后，式(17)左右两边会达到相等，此时， $\mathbf { F } _ { t }$ 和 $\tilde { \mathbf { L } } _ { \ell }$ 将满足式(11)，即满足KKT条件。因此算法CLRL1的收敛性即得到了证明。

# 3 实验结果

为检验所提出算法的有效性，本文分别在非加噪和加噪的数据集上进行了聚类。下面分别从数据与实验设置、实验结果与分析等方面进行介绍。为了评估聚类的结果，本文利用精度(ACC)，标准化互信息(NMI)和纯度(Purity)三个指标来衡量各个算法的表现[19]。

# 3.1数据集与实验设置

为了比较算法的性能，选择在标准数据集上进行测试。使用的是COLI20灰度物体图片数据集，Yeast酵母数据集，Wine葡萄酒化学成分数据集，Uspst手写数字数据集，AR人脸数据集，Dig手写数字数据集。

COLI20数据集包含了1440张 $1 2 8 \times 1 2 8$ 像素的灰度图片(包含了20个不同物体，每个物体每隔5度进行一次拍摄)，分为了20类。

Yeast数据集包含了1484条预测蛋白质定位的10类数据样本。

Wine 数据集包含了178条酒的化学分析数据，每条数据样本有13个维度，共3类。

Uspst数据集是Usps数据集的子集，每张手写数字图是$1 6 \times 1 6$ 像素的大小，一共2007张图片，一共是10类手写数字。

AR数据集包含2600张 $6 0 \times 4 3$ 像素的100类彩色人脸图片，图像具有正面视图面，具有不同的面部表情，照明条件和遮挡(太阳眼镜和围巾)，每个人参与两次拍摄，相隔两周(14天)，两次都拍摄相同的照片。AR为来源于100个人的人脸图像数据集，每个人分两次共拍摄了26张人脸图像，单次拍摄13张(其中7张为不同光照、不同表情等条件，3张为戴眼镜，3张为戴围巾)。在前一部分实验中，对于每个人的人脸图像，本文选择不含眼镜与围巾装饰的14张，由此形成一个1400 张的数据子集。对于第二部分加噪实验中，本文使用所有的2600张人脸图像作为数据。

Dig数据集包含了1797张 $8 \times 8$ 像素的0-9手写数字灰度图片。各数据集的样本数、维度与类簇数特性如表1所示。

Tab.1 Description of the selected datasets   

<html><body><table><tr><td>数据集</td><td>样本数</td><td>维度</td><td>类簇数</td></tr><tr><td>COLI20</td><td>1440</td><td>1024</td><td>20</td></tr><tr><td>Yeast</td><td>1484</td><td>1470</td><td>10</td></tr><tr><td>Wine</td><td>178</td><td>13</td><td>3</td></tr><tr><td>Uspst</td><td>2007</td><td>256</td><td>10</td></tr><tr><td>AR</td><td>2600</td><td>2580</td><td>100</td></tr><tr><td>Dig</td><td>1797</td><td>64</td><td>10</td></tr></table></body></html>

选择比较的算法是K-means,NMF,NCut,CLR[8],L1_un[9]RMNMF[19]。CLR 是一种图学习的聚类算法，L1_un 是一种利用L1范数图的聚类算法。RMNMF是一种联合非负矩阵分解与谱聚类的算法。对于聚类模型CLRL1、CLR、L1_un、NCut、NMF、RMNMF本文设置近邻数为5，权重使用热核函数(HeatKernelfunction)来进行计算，其中带宽参数使用各点对之间距离的平均值。对于各NMF算法，基矩阵的列数设为聚类类别数。如果模型中存在自由正则化参数，按照$\{ 1 0 ^ { - 5 } , 1 0 ^ { - 4 } \cdots , 1 0 ^ { 5 } \}$ 的次序挑选出使聚类结果最优的参数进行保留。根据文献[19]，RMNMF对正则化参数入在 $0 . 0 0 1 \sim 1$ 之间的选择不敏感，本文将RMNMF 算法中的自由参数设置为0.01。对于本文提出的CLRL1算法以及CLR算法，本文采用了一种启发式的方法来加速调参过程，先将正则化参数$\lambda$ 设置为一个小的值，在之后的每一次迭代中，如果计算得到Ls的0特征值个数大于 $k$ ，就将入除以2，如果计算得到Ls的0特征值个数小于k，就将入乘2，否则就停止迭代，得到最佳入。对于k均值聚类和需要k均值聚类进行后处理的NMF算法、Ncut算法，本文将k均值聚类算法重复5次，记录下得到的最佳结果。

# 3.2非加噪数据实验结果

表2\~4分别给出了参与比较的各个算法在选用的6个数据集上的所得到的结果，其中最好的结果在表格中以加粗形式表示。

表1所选数据集的描述  
表2各算法的聚类精度对比  

<html><body><table><tr><td></td><td>COLI20</td><td>Yeast</td><td>Wine</td><td>Uspst</td><td>AR</td><td>Dig</td></tr><tr><td>Kmeans</td><td>45.28</td><td>13.68</td><td>70.22</td><td>63.03</td><td>16.15</td><td>70.78</td></tr><tr><td>NMF</td><td>49.93</td><td>23.79</td><td>58.43</td><td>62.73</td><td>35.95</td><td>64.50</td></tr><tr><td>Ncut</td><td>68.13</td><td>24.26</td><td>61.80</td><td>59.34</td><td>14.36</td><td>77.35</td></tr><tr><td>CLR</td><td>78.47</td><td>29.72</td><td>72.47</td><td>54.46</td><td>34.59</td><td>66.33</td></tr><tr><td>L1_un</td><td>72.08</td><td>30.19</td><td>72.47</td><td>68.31</td><td>26.52</td><td>70.56</td></tr><tr><td>RMNMF</td><td>59.51</td><td>36.32</td><td>73.59</td><td>68.06</td><td>33.95</td><td>75.79</td></tr><tr><td>CLRL1</td><td>85.21</td><td>37.53</td><td>72.47</td><td>70.65</td><td>37.17</td><td>81.74</td></tr></table></body></html>

表3各算法的归一化互信息聚类指标对比

Tab.2Performance of different algorithms with respect to accuracy $1 \%$   
Tab.3Performance of different algortihms with respect to normalized mutual information $1 \%$   

<html><body><table><tr><td></td><td>COLI20</td><td>Yeast</td><td>Wine</td><td>Uspst</td><td>AR</td><td>Dig</td></tr><tr><td>Kmeans</td><td>72.54</td><td>1.98</td><td>42.88</td><td>60.50</td><td>50.15</td><td>69.66</td></tr><tr><td>NMF</td><td>70.47</td><td>6.56</td><td>33.37</td><td>60.04</td><td>65.80</td><td>66.37</td></tr><tr><td>Ncut</td><td>79.63</td><td>6.42</td><td>34.68</td><td>64.11</td><td>43.46</td><td>84.36</td></tr><tr><td>CLR</td><td>93.53</td><td>4.43</td><td>39.48</td><td>70.87</td><td>58.92</td><td>75.71</td></tr><tr><td>L1_un</td><td>90.18</td><td>3.53</td><td>39.48</td><td>78.73</td><td>55.77</td><td>85.10</td></tr><tr><td>RMNMF</td><td>68.39</td><td>13.44</td><td>39.61</td><td>60.19</td><td>61.86</td><td>67.04</td></tr><tr><td>CLRL1</td><td>95.77</td><td>13.36</td><td>39.48</td><td>81.94</td><td>75.45</td><td>89.39</td></tr></table></body></html>

表4各算法的聚类纯度表现  
Tab.4Performance of different algorithms with respect to Purity $\%$   

<html><body><table><tr><td></td><td>COLI20</td><td>Yeast</td><td>Wine</td><td>Uspst</td><td>AR</td><td>Dig</td></tr><tr><td>Kmeans</td><td>49.10</td><td>32.48</td><td>70.22</td><td>70.80</td><td>17.16</td><td>73.79</td></tr><tr><td>NMF</td><td>55.00</td><td>33.76</td><td>62.92</td><td>68.61</td><td>38.81</td><td>70.90</td></tr><tr><td>Ncut</td><td>70.14</td><td>34.37</td><td>61.80</td><td>63.73</td><td>19.30</td><td>81.30</td></tr><tr><td>CLR</td><td>85.00</td><td>32.68</td><td>72.47</td><td>64.97</td><td>37.74</td><td>67.84</td></tr><tr><td>L1_un</td><td>72.30</td><td>32.35</td><td>72.47</td><td>71.90</td><td>27.16</td><td>70.56</td></tr><tr><td>RMNMF</td><td>60.48</td><td>41.91</td><td>73.59</td><td>72.84</td><td>35.74</td><td>75.79</td></tr><tr><td>CLRL1</td><td>89.79</td><td>39.42</td><td>72.47</td><td>80.92</td><td>67.12</td><td>81.75</td></tr></table></body></html>

可以看出，本文改进的CLRL1算法在所用的数据集上取得了较好的结果，聚类效果明显优于其他的算法。对精度指标，CLRL1算法在COLI20、Yeast、Uspst、AR、Dig 数据集上取得了最优的结果，分别比次优算法精度提高 $6 . 7 4 \%$ $1 . 2 1 \%$ ， $2 . 3 4 \%$ ， $2 . 5 8 \%$ 和 $4 . 3 9 \%$ 。RMNMF与CLRL1是两种不同的聚类算法，RMNMF使用L21范数度量矩阵分解的误差，是一种联合矩阵分解与谱聚类的算法，可以看成是特征学习与聚类同时进行；CLRL1重点在于联合结构化图学习与谱聚类，二者侧重点有所不同，因而对数据以及噪声分布特性的表现有所不同，虽然CLRL1在少数数据集的某些指标上未取到最优结果，但在这些情况下二者实验结果的差别比较微弱，多数情况下CLRL1的表现更优。由此本文认为将图的构造过程与聚类标志矩阵的求解过程联合起来进行协同优化以避免两阶段模式带来的次优性对聚类性能提升是有益的虽然此实验中未对数据集进行主动加噪，但是数据集本身也存在一定的噪声，因此改进的CLRL1算法相对于CLR性能也有一定的改善。

图2 给出了CLRL1模型中的正则化参数在Uspst数据集上的敏感性实验结果。对该数据集，的取值设置在[10,50]将是合适的。对其他数据集，参数的敏感性曲线有类似的走势。

![](images/bed5f248258e131049ce6ea63d2acd2b80710c57e3acd9f8f7202f2020fea690.jpg)  
图2在Uspst数据集上参数的敏感曲

关于CLRL1算法的收敛性，图3给出了其在COLI20和Uspst两个数据集上目标函数值随迭代次数增加的下降情况。可以看出，该算法具有很好的收敛速度。

![](images/89a16b5a98a072f3a04abc4d0cbd03ce60e9e3052b468a7d619ad87df0827174.jpg)  
Fig.2Sensitive curve of parameter $\gamma$ on the Uspst dataset   
图3在COLI20和Uspst数据集上目标函数的收敛曲线图 Fig.3Convergence property of objective function value on COLI20 dataset and Uspst dataset

# 3.3加噪数据实验结果

为了测试的CLRL1的鲁棒性，本节的实验将对COLI20数据集做主动加噪处理，即在原始图像中及嵌入块状噪声和椒盐噪声，如图4所示。块状加噪后分别得到在原图像上随机加入1、2块 $4 \times 4$ 随机位置噪声块的数据集，椒盐加噪分别得到在原图像上加上 $10 \%$ 、 $20 \%$ 随机噪点的数据集，如图4所示。此外，本文还将在包含围币与眼镜遮挡的AR人脸图像数据集上进行实验；图5给出了单个人员分两次拍摄的26张人脸图片。

![](images/b318533b39402fe8f7a5ae023da28a8a822b3556934896c24a90204299114316.jpg)  
图4COLI20数据集非加噪图和加噪样图

![](images/2a0e75dee922bf4457fa5513c29c2224e09133a40a7738e9504c1b3c13f3e954.jpg)  
Fig.4Non-noisy and noisy sample images in COLI20 data set

本文将对本文提出的算法CLRL1与CLR 算法、L1_un算法、RMNMF算法分别在四个人工加噪数据集与加噪AR数据集上进行实验。图6-8给出了三种算法在含块状躁声的COIL20数据集上的实验结果；图9\~11给出了三种算法在随机像素置乱COIL20数据集上的实验结果。表5给出了对比算法在含眼镜与围币遮挡的完整AR数据集上的实验结果。

![](images/8b2224d5413b83d7a78586a9aa39d5d236b97509183943eecd06377dd16b177e.jpg)  
Fig.5Sample face images of one subject in two sessions of AR data set   
图6在含块状噪声COIL20数据集上的各算法聚类精度 Fig.6ACC ofalgorithms on COIL20 with block occlusion

![](images/d1540350583d388dccf1b699e4b4525a1fce30af06cdc2280a5ea845de3abb4c.jpg)  
图5单个人两次实验拍摄的26张人脸图像  
图7在含块状噪声COIL20数据集上的各算法聚类互信息Fig.7NMI of algorithms on COIL20 with block occlusion

![](images/2a6ec0b132f5b5065ed8f726bfca59f98ab74d696eceedb757b68051590290a5.jpg)  
图8在含块状噪声COIL20数据集上的各算法聚类纯度 Fig.8Purity of algorithms on COIL20 with block occlusion

![](images/10f37968708524d7470a57571c7a4ae859e137cc13c45ef18a086290aa8be855.jpg)

![](images/39cb2147434b164e3f59e9da1ca22da5e6f595e9f36219b7db80fa99ef9892b3.jpg)  
图9在随机像素置乱COIL20数据集上的各算法聚类精度Fig.9ACC of algorithms on COIL20 with random pixel corruptior  
图10在随机像素置乱COIL20数据集上的各算法聚类互信息 Fig.10NMIof algorithms on COIL20 with randompixel corruption

![](images/466b5f135ff985035ab0b8f2a612b9d62997f4be64eee580cef64a7a89f08ee0.jpg)  
图11在随机像素置乱COIL20数据集上的各算法聚类纯度Fig.11Purity of algorithms on COIL20 with random pixel corruption表5在含真实噪声的AR数据集上各算法的聚类效果

Tab.5Performance of algorithms on AR data set with real disguises   

<html><body><table><tr><td></td><td>ACC</td><td>NMI</td><td>Purity</td></tr><tr><td>CLR</td><td>0.1854</td><td>0.3802</td><td>0.2000</td></tr><tr><td>L1_un</td><td>0.1535</td><td>0.3292</td><td>0.1600</td></tr><tr><td>RMNMF</td><td>0.1992</td><td>0.4698</td><td>0.2107</td></tr><tr><td>CLRL1</td><td>0.2015</td><td>0.5126</td><td>0.3777</td></tr></table></body></html>

从上述实验结果，可以看出本文提出的CLRL1算法鲁棒性上明显优于传统CLR算法、L1_un 算法以及RMNMF算法。本文使用的L1范数是广义的L1范数，即由加权的L21范数相加得到的。这使得L1范数使得算法在面对噪声时的表现更加鲁棒[19,20]。对比CLR与CLRL1的实验结果，本文认为，在随机像素置乱、块状噪声与真实噪声的数据集上，使用e1范数来度量聚类标识向量之间的相似性均可以提升模型的鲁棒性。对比L1_un与CLRL1的实验结果，本文可以得出联合实现图的学习与聚类过程要优于两阶段模式的“先构图再聚类"的效果。

# 4 结束语

本文提出了一种联合结构化图学习与1范数谱嵌入的鲁棒聚类算法。一方面，该算法将图的学习与聚类过程结合起来，在同一个目标函数中实现二者的协同优化，避免了“先构图再聚类"这一两阶段模式带来的次优性问题；另一方面，该算法使用了1范数来度量聚类标识向量之间的距离，避免了常用的2范数度量带来的噪声敏感问题。通过大量的实验(正常数据集与加噪数据集)上的实验结果表明，改进的算法具有更好的鲁棒性，聚类效果得到了提升。

# 参考文献：

[1]刘汉强，张青．区间模糊谱聚类图像分割方法[J].计算机工程与科 学,2018,40(09):1611-1616.(Liu Hanqiang,Zhang Qing.Interval fuzzy spectral clusteringimage segmentation method [J]. Computer Engineering and Science,2018,40 (09): 1611-1616.)   
[2]Wagstaff K, Cardie C, Rogers S,et al. Constrained k-means clustering with background knowledge [C]//Proc of the Eighteenth International Conference on Machine Learning. New York:ACM Press,2001,1: 577- 584.   
[3]刘靖明，韩丽川，侯立文．基于粒子群的 K 均值聚类算法[J]．系 统工程理论与实践,2005,25(6):54-58.(Liu Jingming,Han Lichuan, Hou Liwen.K-means clustering algorithm based on particle swarm [J]. Systems Engineering-Theory & Practice,2005,25(6):54-58.)   
[4]蔡晓妍，戴冠中，杨黎斌．谱聚类算法综述[J].计算机科学,2008, 35(7):14-18.(Cai Xiaoyan,Dai Guanzhong,Yang Libin. Overview of spectral clustering algorithms [J].Computer Science,20o8,35(7): 14- 18.)   
[5]Ng AY, Jordan MI,Weiss Y.On spectral clustering:Analysis and an algorithm [C]// Advances in Neural Information Processing Systems. 2002: 849-856.   
[6]Chan PK,Schlag MDF, Zien JY. Spectral k-way ratio-cut partitioning and clustering [J].IEEE Trans on Computer-Aided Design of Integrated Circuits and Systems,1994,13 (9):1088-1096.   
[7]万月，陈秀宏，何佳佳．基于加权密度的自适应谱聚类算法[J].计 算机工程与科学,2018,40 (10):1897-1901.(Wan Yue,Chen Xiuhong, He Jiajia. Adaptive spectral clustering algorithm based on weighted density [J]. Computer Engineering and Science,2018,40 (10):1897- 1901.)   
[8]Nie Feiping,Wang Xiaoqian,Jordan MI,et al.The constrained laplacian rank algorithm for graph-based clustering [C]// Thirtieth AAAI Conference on Artificial Intelligence.2016:1969-1976.   
[9] Nie Feiping,Wang Hua, Huang Heng,et al. Unsupervised and semisupervise learning via l1-norm graph [C]// IEEE International Conference on Computer Vision.2011: 2268-2273.   
[10]邹鹏，李凡长．鲁棒谱多流形聚类算法[J].小型微型计算机系统, 2018,v.39 (06): 12-16.(Zou Peng,Li Fanchang.Robust spectral multimanifold clustering algorithm[J].Mini-Micro Systems,2018,v.39 (06):

# 12-16.)

[11]王卫卫，李小平，冯象初，等．稀疏子空间聚类综述[J]．自动化学 报，2015，41 (8):1373-1384.(Wang Weiwei，Li Xiaoping，Feng Xiangchu,et al.Overview of Sparse Subspace Clustering [J].Acta Automatica Sinica,2015,41 (8):1373-1384.)   
[12]Li Tao,Ding C.The relationships among various nonnegative matrix factorization methods for clustering[C]//IEEE International Conference on Data Mining.2006:362-371.   
[13] Chung FR K,Graham F C.Spectral graph theory [M].American Mathematical Society,1997.   
[14] Fan K.On a theorem of Weyl concerning eigenvalues of linear transformations I[J].Proceedings of the National Academy of Sciences of the United States of America,1950,36(1):31-35.   
[15] Ding C,Zhou Ding,He Xiaofeng,et al.R1-PCA:rotational invariant L1- norm principal component analysis for robust sub space factorization [C]//International Conference on Machine Learning.2oo6:281-288.   
[16] Peng Yong,Lu Baoliang.Robust structured sparse representation via half-quadratic optimization for face recognition [J].Multimedia Tools and Applications,2017,76 (6): 8859-8880.   
[17] Nie Feiping,Yang Sheng,Zhang Rui,et al.A general framework for auto-weighted feature selection via global redundancy minimization [J]. IEEE Transactions on Image Processing,2019,28(5),2428-2438.   
[18] Nie Feiping,Huang Heng,Cai Xiao,et al.Efficient and robust feature selection via joint l2,1-norms minimization [C]// Advances in neural information processing systems.2010:1813-1821.   
[19] Huang Jing，Nie Feiping，Huang Heng，et al.Robust manifold nonnegative matrix factorization [J].ACM Transactions on Knowledge Discovery from Data,2014,8(3):11:1-21.   
[20] Zhao Haifeng,Wang Zheng,Nie Feiping.A new formulation of linear discriminant analysis for robust dimensionality reduction [J].IEEE Transactions on Knowledge and data engineering,2018,31(4): 629-640.