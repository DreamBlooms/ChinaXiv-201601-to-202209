# 基于局部结构学习的非线性属性选择算法

李佳烨，张乐园，雷聪，甘江璋，吕治政(广西师范大学 广西多源信息挖掘与安全重点实验室，广西 桂林 541004)

摘要：针对大多数高维数据之间不仅有相似性，而且还有非线性关系等特点，提出一种基于局部结构学习的非线性属性选择算法。该算法首先通过核函数把数据映射到高维空间，在高维空间中表示出数据属性之间的非线性关系；然后在低维空间中通过局部结构学习来充分挖掘属性之间的相似性，同时通过低秩约束来排除噪声的干扰；最后通过稀疏正则化因子来进行属性选择、核函数映射来找出数据属性之间的非线性关系、局部结构学习来找出数据属性之间的相似性。该算法是一种嵌入了局部结构学习的非线性属性选择算法。实验结果表明，该算法相比其他的对比算法，有更好的效果。

关键词：属性选择；核函数；低秩；局部结构学习；稀疏正则化 中图分类号：TP301.6 doi: 10.19734/j.issn.1001-3695.2018.07.0524

Nonlinear feature selection algorithm via local structure learning

Li Jiaye†, Zhang Leyuan, Lei Cong, Gan Jiangzhang, Lyu Zhizheng (Guangxi Key Labof Multi-source Information Mining& Security，Guangxi Normal University,Guilin Guangxi 541004, China)

Abstract: Due tothat most high-dimensionaldata notonlyhasthe similarities,butalso nonlinearrelationships.This paper proposeda nonlinear feature selection algorithm based onlocal structure learning.Firstly,the algorithm mapped the data to high-dimensional space through kernel functions，and expressesthenonlinearrelationship betweendata featuresin high-dimensional space.Then,itexploitedthesimilaritybetween the features inthe low-dimensional space through local structurallearing.Atthesame time,iteliminatedtheinterferenceofnoisebythelow-rankconstraint.Finaly,itselected features bysparseregularization factors.It findthe non-linearrelationships between data features bythe kernel function, andfind the similaritiesbetween thedata atributes as the local structure learning.The algorithmis anonlinear feature selectionalgorithmembedded with local tructure learning.Experimentalresultsshowthatthealgorithmhasbeterresults than other comparison algorithms.

Key words: feature selection; kernel function; low-rank; local structure learning; sparse regularization

# 0 引言

随着计算机与科学技术的发展，信息时代来临，与此同时带来了大量的高维数据[1]。人工智能，数据挖掘等领域也蓬勃发展。人们面对成千上万的数据处理起来会十分困难，而且有时还会出现"维数灾难"等问题[2，3]。针对这些高维数据，人们必须对其进行预处理。而属性选择便是其中一种十分有效的方式[4]。通过属性选择来对数据进行预处理从而缩小数据维度是十分必要的[5]。

属性选择[6]包括线性属性选择和非线性属性选择，它们的根本目的都是寻找一个相对较小且具有代表性的属性子集。常用的属性选择方法有很多[7]，但它们都不能挖掘出数据属性之间的非线性关系。局部结构学习刚开始是运用到样本上，通过构建样本之间的相似矩阵来充分体现样本之间的结构[8]，从而达到较好的实验效果。但它不能充分体现属性之间的结构关系。为此，本文通过核函数把数据的每一个属性映射到高维空间，从而使它们之间的非线性关系在高维空间中线性可分；与此同时再把局部结构学习运用到数据属性上，从而更好的表示出数据属性在低维空间中的局部结构关系。提出了一种更加有效的属性选择算法，称作基于局部结构学习的非线性属性选择算法（nonlinearfeatureselectionalgorithmvialocal structure learning，缩写为LS_NFS）。

本文首先通过核函数对数据处理，得到核矩阵，从而解决了只能进行线性属性选择的限制；其次对数据属性构建相似矩阵来进行局部结构学习，可以提高分类准确率；其中还在模型中进行了低秩约束，低秩约束可以排除噪声的干扰；最后嵌入一个向量的-范数来进行属性选择。由于本文同时考虑了数据属性之间的非线性关系和相似性，所以比单一的线性属性选择方法具有更好的效果。经实验验证，该算法在分类准确率上能达到较好的效果。

收稿日期：2018-07-15；修回日期：2018-08-27基金项目：国家自然科学基金资助项目（61170131，61263035，61573270，90718020）；国家重点研发计划资助项目（2016YFB100905）；国家“973”计划资助项目（2013CB329404）；中国博士后科学基金资助项目（2015M570837）；广西自然科学基金资助项目（2015GXNSFCB139011，2015GXNSFAA139306)

作者简介：李佳烨（1993-），男，山西晋城人，硕士研究生，主要研究方向为数据挖掘、机器学习(jiaye_ligxnu@126.com)；张乐园（1995-），男，安徽蒙城人，硕士研究生，主要研究方向为机器学习、数据挖掘；雷聪（1991-），男，湖北大冶人，硕士，主要研究方向为数据挖掘、机器学习；甘江璋(194-），男，湖南衡阳人，硕士研究生，主要研究方向为机器学习和数据挖掘；吕治政（1992-），男，湖北黄冈人，硕士研究生，主要研究方向为机器学习和数据挖掘.

# 1 相关理论背景

# 1.1核函数

核函数在很早以前就被引入到了机器学习领域，它的引入在一定程度上减轻了“维数灾难”，大大减小了计算量。只要一个对称函数在任意数据集上产生的核矩阵是半正定的，那么这个函数就是核函数。它的形式和参数是多种多样的，通过选取不同的核函数形式和参数，可以改变从低维空间到高维空间的映射，进而对高维空间的性质产生影响，最终改变各种核函数的性能。

常用的核函数有高斯核函数、多项式核函数、感知器核函数、样条核函数等。由于高斯核函数相比其他三种核函数大多数情况下都具有良好的性能，所以本文算法用高斯核函数。即

$$
k ( \pmb { x } _ { i } , \pmb { x } _ { j } ) = \exp ( - \frac { \left\| \pmb { x } _ { i } - \pmb { x } _ { j } \right\| _ { 2 } ^ { 2 } } { 2 \sigma ^ { 2 } } )
$$

其中： $\pmb { x } _ { i }$ 、 $\boldsymbol { \mathscr { x } } _ { j }$ 分别表示第 $i$ 和第 $j$ 个属性。 $\sigma$ 为高斯核的宽度参数，它控制了函数的径向作用范围。

因此，本文通过利用高斯核函数把数据属性映射到核空间，进而充分挖掘数据属性之间的非线性关系。

# 1.2局部结构学习简介

前人已经证明通过建立数据之间的局部结构可以起到降维的作用[9，因此本文通过在低维空间中建立数据属性之间的相似矩阵来进行局部结构学习。

假设给定样本数据集 $\pmb { X } \in \pmb { R } ^ { n \times d }$ ，其中 $n$ 和 $d$ 分别表示样本数和属性数。通过局部结构学习得到下面的式子：

$$
\begin{array} { r } { \underset { \mathbf { w } } { \operatorname* { m i n } } \sum _ { i , j } ^ { d } \Big \| \boldsymbol { x } _ { i } ^ { T } \mathbf { W } - \boldsymbol { x } _ { j } ^ { T } \mathbf { W } \Big \| _ { 2 } ^ { 2 } s _ { i , j } } \end{array}
$$

其中： $x _ { i } \in R ^ { n \times 1 }$ 表示第 $i$ 个属性， $\pmb { W } \in \pmb { R } ^ { n \times d }$ 是一个高维数据在低维空间中的转换矩阵， $s _ { i , j }$ 是矩阵 $s$ 的一个元素，表示属性 $x _ { i }$ 和属性 $x _ { j }$ 的相似性。如果属性 $x _ { i }$ 是属性 $x _ { j }$ 的第 $k$ 个最近的邻居，则 $s _ { i , j }$ 的值通过高斯核函数式（1）可得；其他情况 $s _ { i , j } = 0 ,$ 0

# 2 算法描述和优化

# 2.1算法描述

本文首先把数据集 $\pmb { X } \in \pmb { R } ^ { n \times d }$ 拆成 $d$ 个列向量，每个向量$x _ { i } \in R ^ { n \times 1 }$ $i = 1 , . . . , d$ ；然后把每个 $x _ { i }$ 中的每个元素看成一个独立的属性值 $x _ { i j } \in R , j = I , . . . , n$ ；并将它们投影到核空间就得到核矩阵 $\pmb { K } ^ { ( i ) } \in \pmb { R } ^ { n \times n }$ ，即

$$
\pmb { K } ^ { ( i ) } = \left[ \begin{array} { l l l l } { k ( x _ { i 1 } , x _ { i 1 } ) } & { k ( x _ { i 1 } , x _ { i 2 } ) } & { \cdots } & { k ( x _ { i 1 } , x _ { i n } ) } \\ { k ( x _ { i 2 } , x _ { i 1 } ) } & { k ( x _ { i 2 } , x _ { i 2 } ) } & { \cdots } & { k ( x _ { i 2 } , x _ { i n } ) } \\ { \cdots } & { \cdots } & { \cdots } & { \cdots } \\ { k ( x _ { i n } , x _ { i 1 } ) } & { k ( x _ { i n } , x _ { i 2 } ) } & { \cdots } & { k ( x _ { i n } , x _ { i n } ) } \end{array} \right]
$$

这样原始的 $\pmb { X } \in \pmb { R } ^ { n \times d }$ 就变成了 $d$ 个核矩阵 $\pmb { K } ^ { ( i ) } , i = 1 , . . . , d$ 。

无监督的属性选择算法是为了挖掘数据中更具有代表性的属性。在没有类标签 $Y$ 的情况下，用数据矩阵 $X$ 作为一个响应矩阵，可以更好的保持数据原始特征的内部结构[10,]。为了充分挖掘数据属性的非线性关系。得到下面式子：

$$
X = \sum _ { i = 1 } ^ { d } \alpha _ { i } K ^ { ( i ) } W
$$

其中： $\pmb { W } \in \pmb { R } ^ { n \times d }$ 表示核系数矩阵； $\pmb { a } \in \pmb { R } ^ { d \times 1 }$ 用来进行属性选择，相当于属性的权重向量； $a _ { i }$ 对应于向量 $\pmb { a }$ 的一个元素；$\pmb { K } ^ { ( i ) } \in \pmb { R } ^ { n \times n }$ 是核矩阵。

为了使 $X$ 取得更好的拟合效果，同时考虑数据属性之间在低维空间上的结构关系，本文得到如下式子：

$$
\operatorname* { m i n } _ { S , W , \alpha } \left\| X - \sum _ { i = 1 } ^ { d } \alpha _ { i } K ^ { ( i ) } \mathbf { W } \right\| _ { F } ^ { 2 } + \lambda _ { 1 } \sum _ { i , j } ^ { d } \left\| x _ { i } ^ { T } \mathbf { W } - x _ { j } ^ { \operatorname { \alpha } _ { T } } \mathbf { W } \right\| _ { 2 } ^ { 2 } s _ { i , j }
$$

由于相似矩阵 $s$ 受参数 $\sigma$ 的影响变化特别大。为了减少调整参数的次数，同时学习到更有效的相似矩阵，本文把结构学习和低维空间学习相互交替进行，从而达到它们最优的结果。具体得到如下式子：

$$
\begin{array} { r l } & { \underset { S , W , \alpha } { \operatorname* { m i n } } \left\| X - \sum _ { i = 1 } ^ { d } \alpha _ { i } K ^ { ( i ) } W \right\| _ { F } ^ { 2 } + \lambda _ { 1 } \sum _ { i , j } ^ { d } \left\| x _ { i } ^ { T } W - x _ { j } ^ { \ T } W \right\| _ { 2 } ^ { 2 } s _ { i , j } + \lambda _ { 2 } \left\| s _ { i } \right\| _ { 2 } ^ { 2 } } \\ & { s . t . , \forall i , s _ { i } ^ { T } \mathbf { 1 } = 1 , \mathbf { s } _ { i , i } = 0 , s _ { i , j } \geq 0 , \mathrm { i f } \ j \in \mathrm { N } ( i ) , o t h e r w i s e \ 0 } \end{array}
$$

其中： $\lambda _ { 1 }$ ， $\lambda _ { 2 }$ 是调优参数， $s _ { i }$ 是相似矩阵 $s$ 的第 $i$ 列， $\left\| s _ { i } \right\| _ { 2 } ^ { 2 }$ 被用来保持旋转不变性。1代表元素全为1的向量， $\mathbf { N } ( i )$ 代表第 $i$ 个属性的邻居组成的集合， $s _ { i } ^ { \scriptscriptstyle T } \mathbf { 1 } = 1$ 是为了保持旋转不变性。因此，上式就可以使距离越近的属性对应的 $s _ { i , j }$ 值越大，距离越远的属性对应的 $s _ { i , j }$ 值越小。

为了排除离群点的干扰，同时去除噪声样本[12]。本文对矩阵 $W$ 加入了低秩约束[13]，即

$$
W = A B
$$

其中 $\pmb { A } \in \pmb { R } ^ { n \times r }$ ， $\pmb { B } \in \pmb { R } ^ { r \times d }$ ， $r \leq \operatorname* { m i n } ( n , d )$ ，同时本文对矩阵 $A$ 进行正交限制，去充分考虑输出变量之间的相关性，再加入一个 $\pmb { a }$ 的 $l _ { 1 } -$ 范数来进行稀疏学习和属性选择。最后得到最终的目标函数如下：

$$
\begin{array} { l } { \displaystyle \operatorname* { m i n } _ { { s , A , B , \alpha } } \left\| X - \sum _ { i = 1 } ^ { d } \alpha _ { i } K ^ { ( i ) } A B \right\| _ { F } ^ { 2 } + \lambda _ { 1 } \sum _ { i , j } ^ { d } \big \| x _ { i } ^ { T } A B - x _ { j } ^ { T } A B \big \| _ { 2 } ^ { 2 } s _ { i , j } } \\ { + \lambda _ { 2 } \left\| s _ { i } \right\| _ { 2 } ^ { 2 } + \lambda _ { 3 } \left\| \alpha \right\| _ { 1 } } \\ { s . t . , \forall i , s _ { i } ^ { T } \mathbf { 1 } = 1 , \mathbf { s } _ { i , i } = 0 , } \\ { s _ { i , j } \geq 0 , \operatorname { i f } j \in \mathrm { N } ( i ) , o t h e r w i s e \ 0 , A ^ { T } A = I } \end{array}
$$

其中： $\pmb { A } ^ { T } \pmb { A } = \pmb { I } \in \pmb { R } ^ { r \times r }$ ， $\lambda _ { 1 }$ 、 $\lambda _ { 2 }$ 、 $\lambda _ { 3 }$ 是调优参数。核矩阵 $\pmb { K }$ 是通过高斯核函数计算出来，主要作用是把数据映射到核空间，从而挖掘数据属性之间的非线性关系。最后一项 $\pmb { a }$ 的 $l _ { 1 } -$ 范数是对 $\pmb { a }$ 进行稀疏，从而来进行属性选择。 $\pmb { a }$ 向量对应的元素的值为零，则表示该属性不选。

本文提出的算法具有以下优点：

a)由于一般的属性选择算法只能寻找出数据属性之间的线性关系，并不能发现数据属性之间的非线性关系。因此本算法把数据矩阵的每一个属性通过核函数分别映射为一个核矩阵，从而在核空间中充分挖掘数据属性之间的复杂非线性关系。进而对数据属性之间的关系挖掘的更加彻底。

b）不同于普通的局部结构学习，只是针对样本计算出一个样本之间相似关系的最优结果。而本算法是针对数据属性，同时把相似矩阵学习和低维空间学习相互交替进行，从而达到最优的属性选择效果。

c）低秩约束可以明显的减少计算量，同时低秩表征着数据的冗余程度。噪声样本会使系数矩阵的秩增加，使用低秩约束可以降低噪声的干扰，同时低秩是对数据全局结构的考虑。从而提高算法的运行效率和分类准确率。

LS_NFS算法（算法1）伪代码如下。

输入：训练样本 $\pmb { X } \in \pmb { R } ^ { n \times d }$ ，控制参数 $\lambda _ { 1 } , \lambda _ { 2 } , \lambda _ { 3 }$ ·

输出：分类准确率；

a）通过训练样本得出类指示矩阵；b）通过式(1)和(3)建立每个数据属性对应的核矩阵 $\pmb { K } ^ { ( i ) }$ ：c）通过式(6)建立数据属性之间的结构相似矩阵 $s$ d）依据所选择的模型调用算法3求解全局最优解，得到属性选择向量 $\pmb { a }$ ·e）利用最优解 $\pmb { a } ^ { * }$ 对原始属性集 $\scriptstyle { \frac { } { X } }$ 进行属性选择后得到的属性集作为样本新的属性集；

f）对新的属性集构成的样本采用SVM分类。

# 2.2算法优化

由于目标函数不是共凸的，所以无法直接得到闭式解。因此本文提出一种交替迭代优化方法来求解该问题，具体分以下四步：

1）固定 $s$ ， $\textbf {  { B } }$ ， $\textbf { \em a }$ ，优化 $A$ ：当固定 $s$ ， $\pmb { B }$ ， $\pmb { a }$ 之后，优化问题式(8)将变为

$$
\operatorname* { m i n } _ { A } \left\| X - \sum _ { i = 1 } ^ { d } \alpha _ { i } K ^ { ( i ) } A B \right\| _ { F } ^ { 2 } + \lambda _ { 1 } \sum _ { i , j } ^ { d } \left\| x _ { i } ^ { T } A B - x _ { j } ^ { \ T } A B \right\| _ { 2 } ^ { 2 } s _ { i , j }
$$

$P { = } \sum _ { i = 1 } ^ { d } \alpha _ { i } K ^ { ( i ) }$ ，则式(9)可以写成如下式子：

$$
\begin{array} { r } { \underset { \mathbf { \theta } _ { \mathbf { \theta } } } { \operatorname* { m i n } } { \left\| \boldsymbol { X } - \boldsymbol { P } \mathbf { \boldsymbol { A } } \boldsymbol { B } \right\| _ { F } ^ { 2 } } + \lambda _ { 1 } \sum _ { i , j } ^ { d } \left\| \boldsymbol { x } _ { i } ^ { T } \mathbf { \boldsymbol { A } } \boldsymbol { B } - \boldsymbol { x } _ { j } ^ { T } \mathbf { \boldsymbol { A } } \boldsymbol { B } \right\| _ { 2 } ^ { 2 } s _ { i , j } } \\ { s t . , \mathbf { \theta } . \boldsymbol { A } ^ { T } \mathbf { \boldsymbol { A } } = \boldsymbol { I } \quad \quad } \end{array}
$$

对式(10)进行化简可得

$$
\begin{array} { r l } & { \underset { A } { \operatorname* { m i n } } t r ( X ^ { T } X - X ^ { T } P A B - B ^ { T } A ^ { T } P ^ { T } X + B ^ { T } A ^ { T } P ^ { T } P A B ) } \\ & { + \lambda _ { 1 } t r ( { \pmb { B } } ^ { T } A ^ { T } X { \pmb { L } } X ^ { T } A B ) , s . t . , A ^ { T } A = I } \end{array}
$$

其中 $\operatorname { t r } ( \cdot )$ 表示矩阵的迹， $\pmb { L } = \pmb { Q } - \pmb { S } \in \pmb { R } ^ { d \times d }$ 是一个拉普拉斯矩阵，$\varrho$ 是一个对角矩阵，它每一列的元素为 $q _ { i , i } = \sum _ { j = 1 } ^ { d } s _ { i , j }$ 。对 $A$ 求导可得：

$$
2 \lambda _ { 1 } X L X ^ { T } A B B ^ { T } - 2 P ^ { T } X B ^ { T } + 2 P ^ { T } P A B B ^ { T }
$$

由于对 $A$ 进行了正交限制，可以用参考文献[14]中的方法去优化它。

2）固定 $A$ ， $s$ ， $\textbf { \em a }$ ，优化 $\textbf {  { B } }$

当固定 $A$ ， $s$ ， $\pmb { a }$ 之后，优化问题式(8)将变为

$$
\operatorname* { m i n } _ { \pmb { B } } \left\| \pmb { X } - \sum _ { i = 1 } ^ { d } \alpha _ { i } \pmb { K } ^ { ( i ) } \pmb { A } \pmb { B } \right\| _ { F } ^ { 2 } + \lambda _ { 1 } \sum _ { i , j } ^ { d } \left\| \pmb { x } _ { i } ^ { T } \pmb { A } \pmb { B } - \boldsymbol { x } _ { j } ^ { \textit { T } } \pmb { A } \pmb { B } \right\| _ { 2 } ^ { 2 } S _ { i , j }
$$

易得式(13)等价于以下式子：

$$
\begin{array} { r l } & { \underset { \boldsymbol { B } } { \operatorname* { m i n } } t r ( \boldsymbol { X } ^ { T } \boldsymbol { X } - \boldsymbol { X } ^ { T } P A \boldsymbol { B } - \boldsymbol { B } ^ { T } A ^ { T } \boldsymbol { P } ^ { T } \boldsymbol { X } + \boldsymbol { B } ^ { T } A ^ { T } \boldsymbol { P } ^ { T } \boldsymbol { R } A \boldsymbol { B } ) } \\ & { + \lambda _ { 1 } t r ( \boldsymbol { B } ^ { T } A ^ { T } \boldsymbol { X } \boldsymbol { L } \boldsymbol { X } ^ { T } A \boldsymbol { B } ) } \end{array}
$$

对 $\textbf {  { B } }$ 求导，并令其导数为零，则可得

$$
\pmb { { \cal B } } = ( A ^ { T } { \pmb { P } } ^ { T } { \pmb { P } } \pmb { A } + \lambda _ { 1 } \pmb { A } ^ { T } { \pmb { X } } \pmb { L } { \pmb { X } } ^ { T } \pmb { A } ) ^ { - 1 } \pmb { A } ^ { T } \pmb { P } ^ { T } \pmb { X }
$$

3)固定 $A$ $1 , \ B , \ a$ ，优化 $s$

固定 $A$ ， $\textbf {  { B } }$ ， $\pmb { a }$ 之后，优化问题式(8)将变为

$$
\begin{array} { r l } & { \underset { \boldsymbol { s } } { \operatorname* { m i n } } \lambda _ { 1 } \sum _ { i , j } ^ { d } \big \| \boldsymbol { x } _ { i } ^ { T } \boldsymbol { A } \boldsymbol { B } - \boldsymbol { x } _ { j } ^ { T } \boldsymbol { A } \boldsymbol { B } \big \| _ { 2 } ^ { 2 } s _ { i , j } + \lambda _ { 2 } \left\| s _ { i } \right\| _ { 2 } ^ { 2 } } \\ & { s . t . , \forall i , s _ { i } ^ { T } \mathbf { 1 } = 1 , \mathrm { s } _ { i , i } = 0 , } \\ & { s _ { i , j } \geq 0 , \mathrm { i f ~ } j \in \mathrm { N } ( i ) , o t h e r w i s e \ 0 } \end{array}
$$

本文先计算出每两个数据属性之间的欧氏距离来构建所有属性的近邻。如果第 $j$ 个属性不属于第 $i$ 个属性的近邻，则 $s _ { i , j }$ 的值为零；否则，通过式(19)求解 $s _ { i , j }$ 的值。

与此同时，优化 $s$ 等价于单独地优化每一个 $s _ { i } ( i = 1 , . . . , d )$ ，因此本文进一步把优化问题转换为如下式子：

$$
\underset { s _ { i } ^ { T } = 1 , s _ { i , i } = 0 , s _ { i , j } \geq 0 } { \operatorname* { m i n } } { \sum _ { i , j } ^ { d } } { \sum _ { \left( \lambda _ { 1 } \left\| { \boldsymbol { x } } _ { i } ^ { T } { \boldsymbol { A } } { \boldsymbol { B } } - { \boldsymbol { x } } _ { j } ^ { T } { \boldsymbol { A } } { \boldsymbol { B } } \right\| _ { 2 } ^ { 2 } s _ { i , j } + \lambda _ { 2 } s _ { i , j } ^ { 2 } \right) } }
$$

这里令 $\pmb { Z } \in \pmb { R } ^ { d \times d }$ ，其中 $\mathbf { Z } _ { i , j } = \lambda _ { 1 } \left\| x _ { i } ^ { T } A B - { x _ { j } } ^ { T } A B \right\| _ { 2 } ^ { 2 }$ ，这样(17)式进一步变成：

$$
\operatorname* { m i n } _ { \substack { s _ { i } ^ { T } 1 = 1 , s _ { i , i } = 0 , s _ { i , j } \geq 0 } } \left\| s _ { i } + \frac { \lambda _ { 1 } } { 2 \lambda _ { 2 } } { \bf Z } _ { i } \right\| _ { 2 } ^ { 2 }
$$

在KKT条件下，能够得到如下：

$$
s _ { i , j } = ( - \frac { \lambda _ { 1 } } { 2 \lambda _ { 2 } } Z _ { i , j } + \tau ) _ { + }
$$

由于每个数据属性都有近邻，这里对每个 $Z _ { i } ( i = 1 , . . . d )$ 进行降序排列，即 $\hat { Z } _ { i } = \{ \hat { Z } _ { i , l } , . . . , \hat { Z } _ { i , d } \}$ ，则可知 ${ \boldsymbol { s } } _ { i , k + 1 } = 0$ ， $s _ { i , k } > 0$ 。可得

$$
- \frac { \lambda _ { 1 } } { 2 \lambda _ { 2 } } \hat { Z } _ { i , k + 1 } + \tau \le 0
$$

在条件 $s _ { i } ^ { T } \mathbf { 1 } = 1$ 的限制下能够得到：

$$
\sum _ { j = 1 } ^ { k } ( \frac { \lambda _ { 1 } } { 2 \lambda _ { 2 } } \hat { Z } _ { i , k } + \tau ) = 1 \Rightarrow \tau = \frac { 1 } { k } + \frac { \lambda _ { 1 } } { 2 k \lambda _ { 2 } } \sum _ { j = 1 } ^ { k } \hat { Z } _ { i , k }
$$

4)固定 $A$ $\mathbf { \xi } , \mathbf { \xi } _ { B } , \mathbf { \xi } _ { S }$ ，优化 $\pmb { a }$

当固定 $A$ ， $\textbf {  { B } }$ ， $s$ 之后，优化问题式(8)变成：

$$
\operatorname* { m i n } _ { \pmb { \alpha } } \left\| \boldsymbol { X } - \sum _ { i = 1 } ^ { d } \alpha _ { i } \pmb { K } ^ { ( i ) } \pmb { A } \pmb { B } \right\| _ { F } ^ { 2 } + \lambda _ { 3 } \left\| \pmb { \alpha } \right\| _ { 1 }
$$

： $f ( \pmb { \alpha } ) = \left\| \pmb { X } - \sum _ { i = 1 } ^ { d } \alpha _ { i } \pmb { K } ^ { ( i ) } \pmb { A } \pmb { B } \right\| _ { F } ^ { 2 }$ $F ( \pmb { \alpha } ) = f ( \pmb { \alpha } ) + \lambda _ { 3 } \| \pmb { \alpha } \| _ { 1 }$

注意到 $\left\| \pmb { a } \right\| _ { 1 }$ 是凸但非平滑的。所以使用近似梯度法优化$\pmb { a }$ ，本文可以通过下面的规则进行更新迭代 $\pmb { a }$ 。

$$
\pmb { a } _ { t + 1 } = \arg \operatorname* { m i n } _ { \pmb { a } } G _ { \eta t } ( \pmb { a } , \pmb { a } _ { t } )
$$

$$
G _ { \eta t } \left( \alpha , \alpha _ { t } \right) = f \left( \alpha _ { t } \right) + < \nabla f \left( \alpha _ { t } \right) , \alpha - \alpha _ { t } > + \frac { \eta _ { t } } { 2 } \left. \alpha - \alpha _ { t } \right. ^ { 2 } + \lambda _ { 3 } \left. \alpha \right. _ { 1 }
$$

在上式中， $\nabla f ( \pmb { \alpha } _ { t } ) \mathrm { = } 2 \pmb { \alpha } _ { t } ^ { T } \sum _ { i = 1 } ^ { n } ( \pmb { M } ^ { ( i ) } ( \pmb { M } ^ { ( i ) } ) ^ { T } ) - 2 \sum _ { i = 1 } ^ { n } \pmb { X } _ { i } ( \pmb { M } ^ { ( i ) } ) ^ { T }$ ，这里的 $\pmb { M }$ 矩阵是在求导过程中产生的。 $\eta _ { t }$ 是一个调优参数， $\pmb { a } _ { t }$ 是第 $t$ 次迭代中 $\pmb { a }$ 的值。

通过忽略式(25)中的独立的 $\pmb { \alpha }$ 可以得到

$$
\pmb { \alpha } _ { t + 1 } = \pi _ { \eta _ { t } } ( \pmb { \alpha } _ { t } ) = \arg \operatorname* { m i n } _ { \pmb { \alpha } } \frac { 1 } { 2 } \| \pmb { \alpha } - \pmb { U } _ { t } \| _ { F } ^ { 2 } + \frac { \lambda _ { 3 } } { \eta _ { t } } \| \pmb { \alpha } \| _ { 1 }
$$

其中： $\pmb { U } _ { t } = \pmb { a } _ { t } - \frac { 1 } { \eta _ { t } } \nabla f ( \pmb { a } _ { t } )$ ， $\pi _ { \eta _ { t } } ( \pmb { a } _ { t } )$ 是 $\pmb { a } _ { t }$ 在凸集 $\eta _ { t }$ 上的欧几里德投影，因为 $\left\| \pmb { a } \right\| _ { 1 }$ 具有可分离形式，所以式(26)可以写成如下形式：

$$
\alpha _ { t + 1 } ^ { i } = \arg \operatorname* { m i n } _ { \alpha ^ { i } } \frac { 1 } { 2 } \big \| \alpha ^ { i } - U _ { t } ^ { i } \big \| _ { 2 } ^ { 2 } + \frac { \lambda _ { 3 } } { \eta _ { t } } \big | \alpha ^ { i } \big |
$$

其中： $\alpha ^ { i }$ 和 $\boldsymbol { \alpha } _ { t + 1 } ^ { i }$ 分别是 $\pmb { a }$ 和 $\pmb { a } _ { t + 1 }$ 的第 $i$ 个元素，则根据式(27)，$\boldsymbol { \alpha } _ { t + 1 } ^ { i }$ 可以得到以下闭式解：

$$
\alpha ^ { i ^ { * } } = \left\{ \begin{array} { c c } { \displaystyle u _ { t } ^ { i } - \frac { \lambda _ { 3 } } { \eta _ { t } } \times s i g n ( u _ { t } ^ { i } ) , } & { \mathrm { i f } \left\| u _ { t } ^ { i } \right\| > \displaystyle \frac { \lambda _ { 3 } } { \eta _ { t } } } \\ { 0 , } & { \mathrm { o t h e r w i s e } . } \end{array} \right.
$$

为了加速式(24)中的近似梯度算法，本文加入了辅助变量：

$$
\mathbf { } V _ { t + 1 } = \pmb { \alpha } _ { t } + \frac { \beta _ { t } - 1 } { \beta _ { t + 1 } } ( \pmb { \alpha } _ { t + 1 } - \pmb { \alpha } _ { t } )
$$

其中 $\beta _ { t + 1 } = \frac { 1 + \sqrt { 1 + 4 \beta _ { t } ^ { 2 } } } { 2 }$ ，综上所述，得到算法 2。

算法2.优化求解式(22)的伪代码 输入： $\eta _ { \mathrm { 0 } }$ ， $\beta _ { \mathrm { { l } } } = 1$ ，Y

输出： $\pmb { a }$

1.初始化 $\scriptstyle t = 0$ ， $\pmb { a } _ { 0 }$ 为一个随机的向量

2.do{

3. while $F ( \pmb { a } _ { t } ) > G _ { \eta t - 1 } \left( \pi _ { \eta t - 1 } ( \pmb { a } _ { t } ) , \pmb { a } _ { t } \right)$

4.令n-=m

5.end while

6.令n,=m-  
7.计算 $\pmb { a } _ { t + 1 } = \arg \operatorname* { m i n } _ { \pmb { \alpha } } G _ { \eta t } ( \pmb { \alpha } , \pmb { V } _ { t } )$   
8.计算β+ $\beta _ { { \mathrm { t } } + 1 } = \frac { 1 + \sqrt { 1 + 4 \beta _ { \mathrm { t } } ^ { ~ 2 } } } { 2 }$   
9．计算式(29)}  
10.while (convergence)

# 算法3优化求解式(8)的伪代码

输入：训练样本 $\pmb { X } \in \pmb { R } ^ { n \times d }$ ，控制参数 $\lambda _ { 1 } , \lambda _ { 2 } , \lambda _ { 3 } , r ;$   
输出： $A , \ B , \ S$ ， $\pmb { a }$ ：  
1.初始化 $\scriptstyle t = 0$   
2.随机初始化矩阵 ${ \bf A } ^ { ( 0 ) }$ 和 ${ \pmb B } ^ { ( 0 ) }$ ，初始化 ${ \pmb S } ^ { ( 0 ) }$ 为全零矩阵；  
3.do{  
3.1 通过式(9)计算 $\boldsymbol { A } ^ { ( t + 1 ) }$ ；  
3.2 通过式(13)计算 $\boldsymbol { B } ^ { ( t + 1 ) }$ ：  
3.3 通过式(16)计算 $S ^ { ( t + 1 ) }$ ：  
3.4 通过算法2计算出 $\pmb { a } ^ { ( t + 1 ) }$ ：  
3.5更新 $t = t + 1$ ；}  
4.while (式(8)收敛)

# 2.3算法收敛性证明

根据式(19)，对于所有的 $i , j = 1 , . . . , n$ ， $s _ { i , j } ^ { ( t + 1 ) }$ 有一个闭式解。可以得到以下式子：

$$
\begin{array} { l } { \displaystyle \left\| X - \sum _ { i = 1 } ^ { d } \alpha _ { i } K ^ { ( i ) } \pmb { A } ^ { ( t ) } \pmb { B } ^ { ( t ) } \right\| _ { F } ^ { 2 } + \lambda _ { 1 } \sum _ { i , j } ^ { d } \big \| x _ { i } ^ { T } \pmb { A } ^ { ( t ) } \pmb { B } ^ { ( t ) } - x _ { j } ^ { T } \pmb { A } ^ { ( t ) } \pmb { B } ^ { ( t ) } \big \| _ { 2 } ^ { 2 } s _ { i , j } ^ { ( t + 1 ) } } \\ { \displaystyle + \lambda _ { 2 } \sum _ { i , j } ^ { d } \big \| s _ { i } ^ { ( t + 1 ) } \big \| _ { 2 } ^ { 2 } } \\ { \leq \displaystyle \left\| X - \sum _ { i = 1 } ^ { d } \alpha _ { i } K ^ { ( i ) } \pmb { A } ^ { ( t ) } \pmb { B } ^ { ( t ) } \right\| _ { F } ^ { 2 } + \lambda _ { 1 } \sum _ { i , j } ^ { d } \big \| x _ { i } ^ { T } \pmb { A } ^ { ( t ) } \pmb { B } ^ { ( t ) } - x _ { j } ^ { T } \pmb { A } ^ { ( t ) } \pmb { B } ^ { ( t ) } \big \| _ { 2 } ^ { 2 } s _ { i , j } ^ { ( t ) } } \\ { \displaystyle + \lambda _ { 2 } \sum _ { i , j } ^ { d } \big \| s _ { i } ^ { ( t ) } \big \| _ { 2 } ^ { 2 } } \end{array}
$$

当固定 $\pmb { \alpha }$ ， $S ^ { ( t + 1 ) }$ 去更新 $\boldsymbol { A } ^ { ( t + 1 ) }$ 和 $\pmb { B } ^ { ( t + 1 ) }$ 时，可以得到：

$$
\begin{array} { l } { \displaystyle \left\| X - \displaystyle \sum _ { i = 1 } ^ { d } \alpha _ { i } K ^ { ( i ) } A ^ { ( t + 1 ) } B ^ { ( t + 1 ) } \right\| _ { F } ^ { 2 } + \lambda _ { 1 } \sum _ { i , j } ^ { d } \left\| x _ { i } ^ { T } A ^ { ( t + 1 ) } B ^ { ( t + 1 ) } - x _ { j } ^ { T } A ^ { ( t + 1 ) } B ^ { ( t + 1 ) } \right\| _ { 2 } ^ { 2 } s _ { i , j } ^ { ( t + 1 ) } } \\ { + \lambda _ { 2 } \sum _ { i , j } ^ { d } \left\| s _ { i } ^ { ( t + 1 ) } \right\| _ { 2 } ^ { 2 } } \\ { \leq \displaystyle \left\| X - \displaystyle \sum _ { i = 1 } ^ { d } \alpha _ { i } K ^ { ( i ) } A ^ { ( t ) } B ^ { ( t ) } \right\| _ { F } ^ { 2 } + \lambda _ { 1 } \sum _ { i , j } ^ { d } \left\| x _ { i } ^ { T } A ^ { ( t ) } B ^ { ( t ) } - x _ { j } ^ { T } A ^ { ( t ) } B ^ { ( t ) } \right\| _ { 2 } ^ { 2 } s _ { i , j } ^ { ( t + 1 ) } } \\ { + \lambda _ { 2 } \sum _ { i , j } ^ { d } \left\| s _ { i } ^ { ( t + 1 ) } \right\| _ { 2 } ^ { 2 } } \end{array}
$$

由上面两式可得：

$$
\begin{array} { l } { \displaystyle \left\| X - \displaystyle \sum _ { i = 1 } ^ { d } \alpha _ { i } K ^ { ( i ) } A ^ { ( t + 1 ) } B ^ { ( t + 1 ) } \right\| _ { F } ^ { 2 } + \lambda _ { 1 } \sum _ { i , j } ^ { d } \left\| x _ { i } ^ { T } A ^ { ( t + 1 ) } B ^ { ( t + 1 ) } - x _ { j } ^ { T } A ^ { ( t + 1 ) } B ^ { ( t + 1 ) } \right\| _ { 2 } ^ { 2 } s _ { i , j } ^ { ( t + 1 ) } } \\ { + \lambda _ { 2 } \sum _ { i , j } ^ { d } \left\| s _ { i } ^ { ( t + 1 ) } \right\| _ { 2 } ^ { 2 } } \\ { \leq \displaystyle \left\| X - \displaystyle \sum _ { i = 1 } ^ { d } \alpha _ { i } K ^ { ( i ) } A ^ { ( t ) } B ^ { ( t ) } \right\| _ { F } ^ { 2 } + \lambda _ { 1 } \sum _ { i , j } ^ { d } \left\| x _ { i } ^ { T } A ^ { ( t ) } B ^ { ( t ) } - x _ { j } ^ { T } A ^ { ( t ) } B ^ { ( t ) } \right\| _ { 2 } ^ { 2 } s _ { i , j } ^ { ( t ) } } \\ { + \lambda _ { 2 } \sum _ { i , j } ^ { d } \left\| s _ { i } ^ { ( t ) } \right\| _ { 2 } ^ { 2 } } \end{array}
$$

定理1设 $\{ \alpha _ { t } \}$ 是由算法2产生的序列，那么对于 $\forall t \geq 1$ ，式(30)成立。

$$
F ( \pmb { \alpha } _ { t } ) - F ( \pmb { \alpha } ^ { * } ) \leq \frac { 2 \gamma L \left\| \pmb { \alpha } _ { 1 } - \pmb { \alpha } ^ { * } \right\| _ { F } ^ { 2 } } { ( t + 1 ) ^ { 2 } }
$$

根据参考文献[15]可知，是事先定义的常量， $L$ 是式(23)中 $f ( { \pmb a } )$ 梯度的Lipschitz 常数以及 $\pmb { a } ^ { * } = \arg \operatorname* { m i n } _ { \pmb { a } } F ( \pmb { a } )$

通过上面的不等式和定理1，能够很容易地看出本文的

算法是收敛的。

# 3 实验结果和分析

# 3.1实验数据集和对比算法

本文在六个数据集上测试LS_NFS 算法的性能，分别为Movements、Ecoli、Urban_land、Ionosphere、Colon、Lung_discrete。其中前三个均来自UC[16]，而后三个来自属性选择数据集[17]。数据集的详情如表1所示。

表1数据集信息统计  
Table 1 Dataset information statistics   

<html><body><table><tr><td>数据集</td><td>样本数</td><td>属性数</td><td>类数</td></tr><tr><td>Movements</td><td>360</td><td>90</td><td>15</td></tr><tr><td>Ecoli</td><td>336</td><td>343</td><td>8</td></tr><tr><td>Urban_land</td><td>168</td><td>147</td><td>9</td></tr><tr><td>Ionosphere</td><td>351</td><td>34</td><td>2</td></tr><tr><td>Colon</td><td>62</td><td>2000</td><td>2</td></tr><tr><td>Lung_discrete</td><td>73</td><td>325</td><td>7</td></tr></table></body></html>

本文的实验均在Win7系统下，MATLAB2014a平台上运行测试。选择五种对比算法与本文提出的算法进行比较：LS[18]根据两个数据点很近，则它们很可能有很多相似的关系。通过计算其拉普拉斯分数来反映局部结构的保持能力。最后达到好的属性选择效果。CSFS[19]是一种凸半监督多标签属性选择算法，它主要用于大规模多媒体分析。它把不同属性之间的相互关系考虑在内，同时给无标签数据初始化一个为零的标签，最后最小化稀疏来进行属性选择。NetFS[20]是一个鲁棒的无监督属性选择算法，它将潜在的表示学习嵌入到属性选择中来减轻噪声的影响，从而达到好的效果。RUFS[21]也是一个鲁棒的无监督属性选择算法，它把聚类和属性选择同时进行，并且减少了算法的时间和空间复杂度。RSR[22]通过 $l _ { 2 , 1 } -$ 范数来约束自我表示系数矩阵，从而选择具有代表的特征，并确保了对离群点的健壮性。

分析以上的算法，它们都各有各自的优点，但都没有考虑属性之间的非线性关系和相似性。而本文的算法通过结合局部结构学习与核方法来更充分地挖掘属性之间的关系，进而选择出更好的属性子集。

# 3.2实验结果和分析

本文实验首先通过十折交叉验证来对数据集进行划分，用算法选好的属性构成新的属性集，然后再用SVM进行分类。最后用分类准确率来评估算法的性能。所有的算法都是在同一环境下进行，最后提取10次运行实验结果的均值加减均方误差来评价各算法的性能。

具体地，分类准确率定义如下：

$$
a c c = { X _ { c o r r e c t } } / { X }
$$

其中： $X$ 代表样本总数， $X _ { c o r r e c t }$ 代表分类正确的样本数。同时定义标准差来衡量本文算法的稳定性，如下所示：

$$
s t d = \sqrt { \frac { 1 } { N } \sum _ { i = 1 } ^ { N } ( a c c _ { i } - \mu ) ^ { 2 } }
$$

其中： $N$ 表示实验次数， $\ a c c _ { i }$ 代表第 $i$ 次实验的分类准确率，$\mu$ 代表平均分类准确率，std越小，代表算法越稳定。

各个算法在六个数据集上实验结果对比如图1所示，具体数据结果如表2所示。

通过图1中的6个子图所示，能够很清楚地看到LS_NFS算法在6个数据集上的效果都是很好的。从Ionosphere 和Colon两个数据集上，可以看出，对于二分类问题，LS_NFS算法体现出了很好的性能。与此同时，在余下的四个多分类数据集上，LS_NFS 算法也有比较突出的表现。由于每个数

据集都有各自的特点，不同的算法可能适用不同的数据集。 相比大部分情况下是较高的，最后的分类效果也是最好的。所以不能保证每次的结果都是最好的，但与其他的对比算法

![](images/6d317588f3d2c82656b59b25aca78da5f35d227ec382be894933ccd5f95c88cc.jpg)  
图1实验结果图  
Fig.1Experimental results

表2准确率（均值 $\cdot \pm$ 均方差）统计结果  
Table2Accuracy (mean $\pm$ standard deviation) statistical results   

<html><body><table><tr><td>数据集</td><td>LS</td><td>CSFS</td><td>NetFS</td><td>RUFS</td><td>RSR</td><td>LS_NFS</td></tr><tr><td>Movements</td><td>82.50±0.75</td><td>82.31±1.71</td><td>60.61±8.66</td><td>73.75±7.99</td><td>77.78±1.56</td><td>88.81±0.86</td></tr><tr><td>Ecoli</td><td>42.56±0.03</td><td>81.66±0.61</td><td>84.47±1.78</td><td>83.29±1.84</td><td>85.81±0.82</td><td>86.19±0.69</td></tr><tr><td>Urban_land</td><td>55.61±1.69</td><td>59.86±1.90</td><td>56.96±0.88</td><td>53.75±1.73</td><td>60.97±2.53</td><td>63.77±1.79</td></tr><tr><td>Ionosphere</td><td>86.69±0.39</td><td>87.92±0.93</td><td>87.70±1.61</td><td>82.52±2.44</td><td>74.94±0.02</td><td>94.90±0.33</td></tr><tr><td>Colon</td><td>79.24±1.83</td><td>82.40±2.02</td><td>64.38±0.29</td><td>69.79±3.56</td><td>72.29±2.31</td><td>84.14±1.50</td></tr><tr><td>Lung_discrete</td><td>85.59±1.34</td><td>76.11±2.55</td><td>72.45±7.48</td><td>82.20±1.57</td><td>54.73±2.67</td><td>87.20±1.32</td></tr><tr><td>平均</td><td>72.03±1.01</td><td>78.38±1.62</td><td>71.10±3.45</td><td>74.22±3.19</td><td>71.09±1.65</td><td>84.17±1.08</td></tr></table></body></html>

论改进算法。

通过表2可以看出LS_NFS算法与其他五种对比算法的具体情况，与LS算法比较平均提高了 $1 2 . 1 4 \%$ ；比CSFS算法平均提高了 $5 . 7 9 \%$ 。此外，对比NetFS、RUFS、RSR 算法，准确率分别提高了 $1 3 . 0 7 \%$ 、 $9 . 9 5 \%$ 、 $1 3 . 0 8 \%$ 。从标准差上来看，LS_NFS算法在六个数据集上的平均标准差虽然不是最小的，但仅次于LS算法，只比LS算法的平均标准差高0.07。这一定程度上也说明LS_NFS算法有较好的稳定性。LS_NFS算法取得较好的效果，主要与以下两点有关：考虑了数据属性之间的相似性；充分的考虑了数据属性之间的非线性关系。

虽然不同类型的数据集的分布不同，且有一些干扰因素。但从实验结果来看，本文提出的LS_NFS具有最好的属性选择效果。相比其他对比算法，分类准确率也是最高的，同时也说明LS_NFS算法选出了最有代表性的属性。

# 4 结束语

本文通过考虑数据属性之间的相似性和非线性关系，提出了一种新的无监督非线性属性选择算法。即通过局部结构学习找出属性之间的相似性，然后通过核方法来找出数据属性之间的非线性关系，最后通过稀疏正则化因子来进行属性选择。在整个模型中还加入了低秩约束，来更好的完善提出的模型。比一般的属性选择算法更具有显著的挖掘效果。经实验结果证实，本文的算法在分类准确率和稳定性上都取得了很大的提升。在今后的工作中，本文尝试结合更前沿的理

# 参考文献：

[1]Zhu Xiaofeng,Suk HI,Shen Dinggang.Matrix-similarity based loss function and feature selection for Alzheimer's disease diagnosis [C]// Proc of IEEE Conference on Computer Vision and Pattern Recognition. 2014:3089-3096.   
[2]Zhu Xiaofeng,Huang Zi, Shen Hengtao,et al. Dimensionality reduction bymixed kernel canonical correlation analysis [J].Pattern Recognition, 2012,45(8):3003-3016.   
[3]Zhu Xiaofeng,Zhang Shichao,Jin Zhi,et al.Missing value estimation for mixed attribute dataSets [J].IEEE Transactions on Knowledge and Data Engineering,2011,23(1): 110-121.   
[4]Zhu Xiaofeng，Li Xuelong，Zhang Shichao.Block-rowsparse multi-view multi-label learning for image classification.[J].IEEE Trans on Cybernetics,2016,46(2): 450-461.   
[5]Wei Xiaokai,Yu P S.unsupervised feature selection by preserving stochastic neighbors [C]//Proc of the 19th International Conference on Artificial Intelligence and Statistics 2O16:1.   
[6]Zhu Xiaofeng,Huang Zi,Yang Yang,et al.Self-taught dimensionality reduction on the high-dimensional small sized data[J]. Pattern Recognition,2013,46(1):215-229.   
[7]Zhang Shichao,Jin Zhi,Zhu Xiaofeng.Missing data imputation by utilizing information within incomplete instances[J]. Journal of Systems and Software,2011,84(3): 452-459.   
[8]Nie Feiping,Zhu Wei,Li Xuelong.Unsupervised feature selection with structured graph optimization [Cl//Proc of the 3Oth AAAI Conference on Artificial Intelligence.Palo Alto:AAAI Press,2016:1302-1308.   
[9]Hou Chenping，Nie Feiping，Li Xuelong，et al. Joint embedding learning and sparse regression:a framework for unsupervised feature selection [J].IEEE Trans on Cybern,2017,44(6):793-804.   
[10] Shao Weixiang，He Lifang，Lu C T,et al.Online unsupervised multi-view feature selection [C]//Proc of the 16th IEEE International Conference on Data Mining.Piscatraway,NJ:IEEE Press 2016: 1203-1208.   
[11] Jian Ling,Li Jundong,Shu Kai,et al.Multi-label informed feature selection [C]/Proc of International Joint Conference on Artificial Intelligence.Palo Alto:AAAI Press,2016:1627-1633.   
[12] Liu Xinwang,Wang Lei,Zhang Jian,et al.Global and local structure preservation for feature selection [J].IEEE Trans on Neural Networks &Learning Systems,2017,25 (6):1083-1095.   
[13]Lu Canyi,Lin Zhouchen,Yan Shuicheng.Smoothed low rank and sparsematrix recovery byiteratively reweighted least squares minimization [J].IEEE Trans on Image Processing，2015,24(2): 646-654.   
[14]Wen Zaiwen，Yin Wotao.A feasible method for optimization with orthogonality constraints [J].Mathematical Programming，2O13,142 (1-2): 397-434.   
[15] Nesterov Y. Introductory lectures on convex optimization [J].Applied Optimization,2004,87(5): xviii,236.   
[16] UCI repository of machine learning datasets [EB/OL].[2016-05-27]. http://archive.ics.uci.edu/ml/   
[17] Featureselection datasets[EB/OL].[2016-05-27].http://feature selection.asu.edu/datasets.Php   
[18] He Xiaofei, Cai Deng,Niyogi P.Laplacian score for feature selection. [C]/Proc of International Conference on Neural Information Processing Systems.Cambridge $\because$ MITPress,2005:507-514.   
[19] Chang Xiaojun,Nie Feiping,Yang Yi,et al.A convex formulation for semi-supervised multi-label feature selection [C]// Proc of the 28th AAAI Conference on Artificial Intelligence.Palo Alto:AAAI Press, 2014:1171-1177.   
[20] Li Jundong,Hu Xia,Wu Liang,et al.Robust unsupervised feature selection networked data[C]/Proc of SIAM International Conference on Data Mining.2016:387-395.   
[21] Qian Mingjie,Zhai Chengxiang.Robust unsupervised feature selection [C]//Proc of International Joint Conference on Artificial Intelligence. 2013:1621-1627.   
[22] Zhu Pengfei,Zuo Wangmeng,Zhang Lei,et al.Unsupervised feature selection by regularized self-representation [J].Pattern Recognition, 2015,48(2): 438-446.