# 一种基于信息熵的混合属性数据谱聚类算法

姜智涵1,2,3，朱军1,3，周晓锋1,3，李帅1,2,3(1．中国科学院沈阳自动化研究所，沈阳110016;2.中国科学院大学，北京 100049;3．中国科学院网络化控制系统重点实验室，沈阳110016)

摘要：针对传统的聚类算法只能处理单属性的数据，不能很好地处理混合属性数据的聚类问题，以及目前大多数混合属性数据聚类算法对初始化敏感、不能处理任意形状的数据的问题，提出一种基于信息熵的混合属性数据谱聚类算法，用于处理混合类型数据。首先，提出了一种新的相似性度量方式，利用谱聚类算法中的数值型数据构成的高斯核函数矩阵与新的基于信息熵的分类型数据构成的影响因子矩阵相结合代替了传统的相似度矩阵，新的相似度矩阵避免了数值属性与分类属性数据之间的转换和参数调整；然后，把新的相似度矩阵运用到谱聚类算法中，以便于处理任意形状的数据，最终得出聚类结果。通过在UCI的数据集上的实验表明,该算法能有效地处理混合属性数据的聚类问题，且具有较高的稳定性以及良好的鲁棒性。

关键词：混合属性数据；谱聚类；高斯核函数；影响因子中图分类号：TP doi:10.3969/j.issn.1001-3695.2018.02.0080

# Entropy-based spectral clustering algorithm for mixed type data

Jiang Zhihan1,2,3, Zhu Jun1,3, Zhou Xiaofengl,3, Li Shuai1,2,3 (1.ShenyangInstituteofAutomation,ChineseAcademyofSciences,henyang016,China;2.UniversityofChineseAcademy ofSciences,Beijing049,China;3.KeyLaboratoryof Network Control System,ChineseAcademyofSciences,Shenyang 110016, China)

Abstract:Aimingatthe problemthatthetraditional clustering algorithmcanonlydeal with single atributedataand can't handletheclustering problemofmixedtypedataverywell.Mostoftheclusteringalgorithmsfor mixedtypedatacurrntlyhave theproblemofinitializing sensitive andcan’thandlethedataofarbitraryshape.This paper proposedanentropy-based spectral clustering algorithm for mixed type data todeal with mixed type data.First,it proposed anew similarity measure.Itused the numerical datainthe spectral clusteringalgorithmconstitutesa Gaussian kernel functionof the matrix,andused the classificationdata constitutes anentropy-based the influence factorof the matrix.Anew similarity matrix combines these two matrices.Insteadofthetraditional similaritymatrixitproposed thenew similarity matrix avoid feature transformationand parameter adjustment between the numerical dataand theclassification data.Then,itappliedthe new similarity matrix tothe spectral clustering algorithm soas todeal with the dataofarbitraryshape,andfinallgottheclusteringresult.Experiments on UCIdatasetsshowthatthisalgorithmcaneectivelydeal withteclustering problemofmixedatributedata,withhighstability and good robustness.

Key Words: mixed type data; spectral clustering; Gaussian kernel function; influence factor

# 0 引言

聚类分析的目的是在数据集的子集之间寻找相关性，并评估这些子集中的元素之间的相似性[,2]。聚类在包括生物学、经济学和医学在内的各个领域都有很多应用。它的应用包括数据挖掘、文档检索、图像分割和模式识别[3]。传统的聚类方法只能处理单属性的数据，如K-means[4]、RDBSCAN[5]、CSSA-OIK[6]、基于竞争思想的分级聚类[7等算法只针对处理数值型数据，而K-modes[8]、COOLCAT[9]、CECD[10]等算法只针对处理分类型数据。在处理混合属性数据时，上述的算法都得不到期望的聚类效果[]。

处理混合类型数据的一种直接处理方式是将分类属性转换为新的形式，如二进制字符串，然后应用到前面提到的基于数值属性的聚类算法中。但是二进制编码有三个缺点：首先，这种方法破坏了分类属性的原始结构。为了避免分类属性之间的参数调整，Li等人[2]提出了一个基于混合数据相似度度量的SBAC算法。其次，如果分类属性的定义域很大，那么转换后的二进制就会有更大的维度。最后，维护的难度。如果将属性值添加到分类属性中，那么所有对象将被更改。为了更好地解决这个问题，许多研究人员在过去十几年里，基于相似度指标直接研究了分类属性。一些方法基于相似度的度量指标考虑了数值属性和分类属性，如K-prototypes[13]。然而考虑到数据在簇归属上的不确定性，Chatzis等人[14]提出了KL-FCM-GM算法来扩展K-prototypes 算法，KL-FCM-GM算法是假设簇中的数据符合高斯分布。还有一些是基于无参数的相似度度量的方法，如OCIL[15].但是这种度量方式只能度量一个对象与一个簇之间的相似性。就像K-prototypes 算法一样，OCIL使用K-means的形式来对混合类型数据进行聚类，是一种迭代的聚类算法。因此，这种算法对初始化很敏感，适用于球面分布的数据[16]。

针对传统的聚类算法只能处理单属性的数据，不能很好地处理混合属性数据的聚类问题，以及目前大多数混合属性数据聚类算法对初始化敏感、不能处理任意形状的数据的问题，本文提出了一种基于信息熵的混合属性数据谱聚类(EBSCMD)算法。该算法利用谱聚类算法中的数值型数据构成的高斯核函数矩阵与新的基于信息熵的分类型数据构成的影响因子矩阵相结合代替了传统的相似度矩阵，避免了数值属性和分类属性数据之间的转换和参数调整，再把新的相似度矩阵运用到谱聚类算法中处理任意形状的数据，最终得出聚类结果。为了验证EBSCMD算法的可行性以及有效性，本文利用一些UCI数据集进行了一些实验，并与其他算法进行了比较。实验结果表明，EBSCMD算法能有效地处理混合属性数据的聚类问题，且具有较高的稳定性及鲁棒性。

# 1 谱聚类算法及其相关定义

谱聚类算法是一种基于谱图理论的聚类算法，其本质是将聚类问题转换为图的最优划分问题[17]。与传统的聚类算法相比，谱聚类算法具有能在任意形状的样本空间上聚类且收敛于全局最优解的优点。其主要思想是把所有的数据对象看做空间中的点，这些点之间可以用边连接起来。距离较远的两点之间的边权重值较低，而距离较近的两点之间的边权重值较高。通过对所有数据点组成的图进行切图，让切图后不同的子图间的边权重和尽可能的低，而子图内的边权重和尽可能的高，从而达到聚类的目的。在构造适当的图基础上，将原来的聚类问题转换为图论中的子图最优划分问题[18]。

谱聚类算法一般分为三步[19]:

a)根据数据之间的相似度建立相似度矩阵；b)求相似度矩阵最小的 $\mathrm { ~ k ~ }$ 个特征值对应的特征向量，并构

成新的特征向量空间；

c使用 $\mathrm { \sf ~ K ^ { - } ~ }$ -means算法对这个新的向量空间聚类，输出聚类结果。

算法中相关定义如下：

定义1无向权重图。对于一个图 $\textbf { \textit { G } }$ ，一般用点的集合 $\nu$ 和边的集合 $\pmb { L }$ 来描述，即为 ${ \pmb G } ( V , { \pmb L } )$ 。其中 $V$ 即为数据集里面所有的点 $( v _ { 1 } , \ v _ { 2 } , \ . . . v _ { n } )$ 。对于 $V$ 中的任意两点，可以有边连接，也可以没有边连接。定义权重 $w _ { i j }$ 为点 $\boldsymbol { v } _ { i }$ 与点 $v _ { j }$ 之间的权重。由于是无向图，所以 $w _ { i j } = w _ { j i }$ 。

定义2度矩阵 $\textbf {  { D } }$ 。对于有边连接的两个点 $\boldsymbol { v } _ { i }$ 和 $v _ { j }$ ， $w _ { i j } { > } 0$ 对于没有边连接的两个点vi和 $\mathbf { v _ { j } }$ ， $w _ { i j } { = } 0 _ { \circ }$ 对于图的任意一个点 $\mathbf { v _ { i } }$ 它的度 $d _ { i }$ 定义为它相连的所有边的权重之和，即$d _ { i } = \sum _ { j = 1 } ^ { n } w _ { i j }$

利用每个点度的定义，本文可以得到一个 $n \times n$ 的度矩阵 $\textbf {  { D } }$ 。它是一个对角矩阵，对应第i行的第i个点的度数，定义如下：

$$
D = \left[ { \begin{array} { c c c c } { d _ { 1 } } & { 0 } & { \cdots } & { 0 } \\ { 0 } & { \ddots } & { \cdots } & { \vdots } \\ { \vdots } & { \cdots } & { \ddots } & { 0 } \\ { 0 } & { \cdots } & { \cdots } & { d _ { n } } \end{array} } \right]
$$

定义3邻接矩阵 $\pmb { W } _ { \odot }$ 。利用所有点之间的权重值，可以得到图的邻接矩阵 $\pmb { W }$ 。它也是一个 $n \times n$ 的矩阵，第i行的第j个值对应权重 $w _ { i j }$ 。这里定义邻接矩阵的方法是全连接法，此方法的相似矩阵与邻接矩阵相同。 $\mathbf { w _ { i j } }$ 计算采用高斯核函数，即$w _ { i j } = \exp \left( - { \frac { \| { \mathbf { x } } _ { i } - { \mathbf { x } } _ { j } \| _ { 2 } ^ { 2 } } { 2 { \sigma } ^ { 2 } } } \right)$ (3)

定义4拉普拉斯矩阵 $\textbf { \em L }$ 。拉普拉斯矩阵是对称矩阵，由$\pmb { D }$ 和 $\pmb { W }$ 相减得到的，即 $\scriptstyle { L = D - W }$ 0

定义5相似矩阵S。由样本点距离度量组成的矩阵。

对于数值型数据，一般利用欧氏距离作为数据之间的相似性度量，然后利用高斯核函数把其转换为无向加权图边上的权值，构建出一个关于数值型数据的高斯核函数矩阵。用这种方法处理能很好地解决数值型数据聚类问题，并能取得全局最优解。对于分类型数据，若利用欧氏距离表示混合数据之间的相似性度量，把分类型数据转换为数字，然后计算欧氏距离。显然不能准确反映数据的内在联系，所以利用谱聚类算法解决混合数据聚类问题的关键在于为混合数据定义一个合适的相似性度量，并为之选择合适的相似度矩阵。

# 2 基于信息熵的混合属性数据谱聚类算法

本文提出了一个新的相似性度量作为一个统一的框架用于处理包含数值型数据和分类型数据的混合型数据。为了更好地对任意形状的数据进行聚类，将新的相似性度量方式引入到谱

聚类算法中。同时，为了更好地适应谱聚类算法的算法流程，本文构建了一个新的分类型数据的相似度矩阵与高斯核函数矩阵相融合运用到谱聚类算法中。

# 2.1 相似性度量矩阵

关于混合属性数据的相关公式符号描述如下：$X = \left\{ \pmb { x } _ { 1 } , \pmb { x } _ { 2 } , \cdots , \pmb { x } _ { n } \right\}$ 表示 $\mathrm { ~ N ~ }$ 个混合数据对象的数据集，对于每一个 $\mathbf { \lambda } _ { \pmb { x } _ { i } }$ ， $i \in \left[ 1 , \mathrm { N } \right]$ ，混合型数据集 $\mathbf { \sigma } _ { \pmb { x } _ { i } }$ 代表） $\mathsf { M } ( \boldsymbol { M } = \boldsymbol { M } _ { n } + \boldsymbol { M } _ { c }$ )个属性Am), A)，， $A _ { M _ { n } } ^ { ( n ) }$ ， $A _ { M _ { n } + 1 } ^ { ( n ) } , \cdots , A _ { M _ { n } + M _ { c } } ^ { ( \mathrm { c ) } }$ ,这里 $A _ { 1 } ^ { \mathrm { ( n ) } } , A _ { 2 } ^ { \mathrm { ( n ) } } , \cdots , A _ { M _ { n } } ^ { \mathrm { ( n ) } }$ 代表 $\boldsymbol { M } _ { n }$ 个数值型数据， $A _ { 1 } ^ { \mathrm { ( c ) } } , A _ { 2 } ^ { \mathrm { ( c ) } } , \cdots , A _ { M _ { c } } ^ { \mathrm { ( c ) } }$ 代表 $M _ { c }$ 个分类型数据。 $x _ { i , k } ^ { ( \mathrm { n } ) }$ 代表${ \pmb x } _ { i } ^ { ( \mathrm { n } ) }$ 的第 $\mathbf { k }$ 个属性， ${ \pmb x } _ { i } ^ { ( \mathrm { n } ) }$ 表示数值部分。 $x _ { i , k } ^ { \mathrm { ( c ) } }$ 代表 ${ \pmb x } _ { i } ^ { \scriptscriptstyle ( \mathrm { c } ) }$ 的第 $\mathbf { k }$ 个属性， ${ \pmb x } _ { i } ^ { \scriptscriptstyle ( \mathrm { c } ) }$ 表示分类部分。 $\mathsf { D O M } \left( A _ { k } ^ { c } \right)$ （ $1 \leq k \leq M _ { n }$ ）表示 $x _ { i , k } ^ { \mathrm { ( c ) } }$ 的定义域。这个分类属性的定义域表示为DOM $\left( A _ { k } ^ { c } \right) =$ $\left\{ \pmb { a } _ { k , \mathrm { 1 } } , \pmb { a } _ { k , \mathrm { 2 } } , \cdots , \pmb { a } _ { k , \mathrm { r } _ { k } } \right\}$ ， $r _ { k }$ 表示第k列分类属性的数量。同时， $\mathbf { \boldsymbol { x } } _ { i }$ 表示一个向量 $\begin{array} { r l } { \left[ \pmb { x } _ { i } ^ { \mathrm { ( n ) } } , \pmb { x } _ { i } ^ { \mathrm { ( c ) } } \right] = } & { \left[ \pmb { x } _ { i , 1 } ^ { \mathrm { ( n ) } } , \pmb { x } _ { i , 2 } ^ { \mathrm { ( n ) } } , \cdots , \pmb { x } _ { i , \mathrm { M } _ { n } } ^ { \mathrm { ( n ) } } , \pmb { x } _ { i , \mathrm { M } _ { n } + 1 } ^ { \mathrm { ( c ) } } , \cdots , \pmb { x } _ { i , \mathrm { M } } ^ { \mathrm { ( c ) } } \right] \mathrm { ~ c ~ } } \end{array}$

与传统的相似性测量方法不同，在用谱聚类算法处理混合属性数据时，本文需要构建一个关于混合属性数据的相似性度量矩阵，这个相似性度量矩阵需要融合数值型数据的相似度矩阵和分类型数据的相似度矩阵。

# 2.1.1数值型数据的相似度矩阵

对于数值型数据，本文采用谱聚类算法中的高斯核核函数定义 $\pmb { x } _ { i } ^ { ( \mathrm { n } ) }$ 与 $\boldsymbol { x } _ { j } ^ { ( \mathrm { n } ) }$ 之间的相似性度量为 $S _ { n } \left( \pmb { x } _ { i } ^ { \mathrm { ( n ) } } , \pmb { x } _ { j } ^ { \mathrm { ( n ) } } \right)$ ，公式如下：

$$
\mathrm { S } _ { n } \left( \pmb { x } _ { i } ^ { ( n ) } , \pmb { x } _ { j } ^ { ( \mathrm { n } ) } \right) = \mathrm { e x p } \left( - \frac { \lVert \mathbf { \Delta x } _ { i } ^ { ( \mathrm { n } ) } - \mathbf { x } _ { j } ^ { ( \mathrm { n } ) } \rVert _ { 2 } ^ { 2 } } { 2 \sigma ^ { 2 } } \right)
$$

其中： $\sigma$ 是一个可调节的参数。

谱聚类算法利用高斯核函数把数据点之间的相似性度量转换为无向加权图边上的权值，构建出一个关于数值型数据的高斯核函数矩阵 $\pmb { W }$

$$
\begin{array} { r } { W = \left[ \begin{array} { l l l l l l } { 0 } & { \cdots } & { x _ { 1 j } ^ { ( \mathrm { n } ) } } & { \cdots } & { x _ { 1 n } ^ { ( \mathrm { n } ) } } \\ { \vdots } & { \ddots } & { \vdots } & { \cdots } & { \vdots } \\ { \vdots } & { \cdots } & { x _ { i j } ^ { ( \mathrm { n } ) } } & { \cdots } & { \vdots } \\ { \vdots } & { \cdots } & { \vdots } & { \ddots } & { \vdots } \\ { x _ { n } ^ { ( \mathrm { n } ) } } & { \cdots } & { x _ { n j } ^ { ( \mathrm { n } ) } } & { \cdots } & { 0 } \end{array} \right] } \end{array}
$$

$\pmb { W }$ 是一个 $n \times n$ （ $\scriptstyle \mathbf { n } = \mathbf { N }$ ）的矩阵，对角线上的元素全是0， $\pmb { x } _ { i j } ^ { ( n ) }$ 代表 $\mathbf { \Delta } \mathbf { x } _ { i } ^ { ( \mathrm { n } ) }$ 与 $\boldsymbol { x } _ { j } ^ { ( n ) }$ 之间的相似性度量 $S _ { n } \left( \pmb { x } _ { i } ^ { ( \mathrm { n } ) } , \pmb { x } _ { j } ^ { ( \mathrm { n } ) } \right)$ 。

# 2.1.2分类型数据的相似度矩阵

首先，本文定义 $\mathbf { \Delta } \mathbf { x } _ { i , k } ^ { ( \mathrm { c } ) }$ 与 ${ \bf \Delta } \mathbf { x } _ { \mathrm { j } , k } ^ { \mathrm { ( c ) } }$ 之间的相似性度量为

$$
S _ { c } ^ { ' } \left( x _ { i , k } ^ { \scriptscriptstyle ( \mathrm { c } ) } , x _ { j , k } ^ { \scriptscriptstyle ( \mathrm { c } ) } \right) _ { 0 }
$$

$$
\begin{array} { r } { S _ { c } ^ { ' } \left( \boldsymbol { x } _ { i , k } ^ { \mathrm { ( c ) } } , \boldsymbol { x } _ { j , k } ^ { \mathrm { ( c ) } } \right) = \displaystyle \frac { \int ( 1 , i f \ : \boldsymbol { x } _ { i , k } ^ { \mathrm { ( c ) } } = \boldsymbol { x } _ { \mathrm { j } , k } ^ { \mathrm { ( c ) } } } { \upsilon , i f \ : x _ { i , k } ^ { \mathrm { ( c ) } } \neq \boldsymbol { x } _ { \mathrm { j } , k } ^ { \mathrm { ( c ) } } } } \end{array}
$$

这种定义分类型数据的相似性度量是假设每个分类属性的权重是相同的。然而在实践中每个分类属性在分类型数据部分对相似度的计算有不同的贡献，其中一个主要的原因是不同的属性有不同的分布。因此公式可以进一步修改，如下所示：

$$
S _ { c } \left( \pmb { x } _ { i , k } ^ { \mathrm { ( c ) } } , \pmb { x } _ { j , k } ^ { \mathrm { ( c ) } } \right) = \sum _ { k = 1 } ^ { M _ { c } } { w _ { k } \pmb { S } _ { c } ^ { ' } \left( \pmb { x } _ { i , k } ^ { \mathrm { ( c ) } } , \pmb { x } _ { j , k } ^ { \mathrm { ( c ) } } \right) }
$$

这里 $0 \leq w _ { k } \leq 1 , \sum _ { k = 1 } ^ { M _ { c } } w _ { k } = 1$ 。显然， $w _ { t }$ 是分类属性 $A _ { k } ^ { \mathrm { ( c ) } }$ 的权重，它代表了对分类属性部分重要性的计算。

然后，讨论如何计算每个分类属性 $A _ { k } ^ { \mathrm { ( c ) } }$ 的权重 $w _ { k }$ 。本文把信息熵的概念应用到权重的计算上。数据集中分类型数据的不均匀性越大，分类型数据的信息熵就越大。另外，数据集中的分类属性的不均匀性与分类属性的重要性相对应。因此，根据信息熵公式可以计算分类属性 $A _ { k } ^ { \mathrm { ( c ) } }$ ，DOM $\left( A _ { k } ^ { c } \right) \ =$ $\left\{ \pmb { a } _ { k , 1 } , \pmb { a } _ { k , 2 } , \cdots , \pmb { a } _ { k , \mathrm { r } _ { k } } \right\}$ ，定义如下：

$$
H _ { A _ { k } ^ { \left( \mathrm { c } \right) } } = - \sum _ { a _ { k , t } \in D O M \left( A _ { k } ^ { \left( \mathrm { c } \right) } \right) } p \left( a _ { k , t } \right) \log _ { 2 } \left( p \left( a _ { k , t } \right) \right) ,
$$

这里p(ak,)是属性值a，的概率；p(a $p \left( a _ { k , t } \right) = \frac { \sum _ { i = 1 } ^ { N } S _ { c } ^ { ' } \left( x _ { i , k } ^ { \left( \mathrm { c } \right) } , a _ { k , t } \right) } { N }$ 子表示 $A _ { k } ^ { \mathrm { ( c ) } }$ 中的分类属性值与 $a _ { k , t }$ 相等的个数； $\mathrm { ~  ~ N ~ }$ 是数据集中的对象总数。观察式（8）可以注意到，如果 $A _ { k } ^ { \mathrm { ( c ) } }$ 中值的数量 $r _ { k }$ 非常大，那么分类属性的信息熵 $H _ { _ { A _ { k } ^ { ( c ) } } }$ 也会很高。这与实际情况是不一样的。为了降低太多不同值甚至唯一值对分类属性的影响，本文重新定义了分类属性的信息熵 $H _ { _ { A _ { k } ^ { \left( \mathrm { c } \right) } } }$ ：

$$
H _ { _ { A _ { k } ^ { \mathrm { ( e ) } } } } = - \frac { 1 } { r _ { k } } \sum _ { t = 1 } ^ { r _ { k } } p \left( a _ { k , t } \right) \log _ { 2 } \left( p \left( a _ { k , t } \right) \right)
$$

因此，可以量化分类属性 $A _ { k } ^ { \mathrm { ( c ) } }$ 的重要性为

$$
w _ { k } = \frac { H _ { _ { A _ { k } ^ { \mathrm { ( c ) } } } } ^ { ' } } { \sum _ { k = 1 } ^ { M _ { c } } H _ { _ { A _ { k } ^ { \mathrm { ( c ) } } } } ^ { ' } }
$$

将式（10）带入到式（7）中，最终得到分类属性的相似性度量 $S _ { c } \left( \boldsymbol { x } _ { i } ^ { \scriptscriptstyle ( \mathrm { c } ) } , \boldsymbol { x } _ { j } ^ { \scriptscriptstyle ( \mathrm { c } ) } \right)$ ，公式如下：

$$
S _ { c } \left( \boldsymbol { x } _ { i } ^ { \left( \mathrm { c } \right) } , \boldsymbol { x } _ { j } ^ { \left( \mathrm { c } \right) } \right) = \sum _ { k = 1 } ^ { M _ { c } } \left( \frac { { H } _ { A _ { k } ^ { \left( \mathrm { c } \right) } } ^ { \left( \mathrm { c } \right) } } { \sum _ { k = 1 } ^ { M _ { c } } { H } _ { A _ { k } ^ { \left( \mathrm { c } \right) } } ^ { \left( \mathrm { c } \right) } } . \boldsymbol { S } _ { c } ^ { \prime } \left( \boldsymbol { x } _ { i , k } ^ { \left( \mathrm { c } \right) } , \boldsymbol { x } _ { j , k } ^ { \left( \mathrm { c } \right) } \right) \right)
$$

最后，为了更好地适应谱聚类算法的算法流程，需要构建一个分类型数据的相似度矩阵，本文称之影响因子矩阵 $F$ ，形式如下：

$$
\begin{array} { r } { F = \left[ \begin{array} { c c c c c c } { 0 } & { \cdots } & { x _ { 1 j } ^ { \left( \mathrm { c } \right) } } & { \cdots } & { x _ { 1 n } ^ { \left( \mathrm { c } \right) } } \\ { \vdots } & { \ddots } & { \vdots } & { \cdots } & { \vdots } \\ { \vdots } & { \cdots } & { x _ { i j } ^ { \left( \mathrm { c } \right) } } & { \cdots } & { \vdots } \\ { \vdots } & { \cdots } & { \vdots } & { \ddots } & { \vdots } \\ { x _ { n 1 } ^ { \left( \mathrm { c } \right) } } & { \cdots } & { x _ { n j } ^ { \left( \mathrm { c } \right) } } & { \cdots } & { 0 } \end{array} \right] } \end{array}
$$

显然， $F$ 同样是一个 $\scriptstyle n \times n$ （ $\mathrm { n } { = } \mathrm { N } .$ ）的矩阵，对角线上的元素全是0， $\boldsymbol { x } _ { i j } ^ { ( \mathrm { c } ) }$ 代表 $\pmb { x } _ { i } ^ { \mathrm { ( c ) } }$ 与 $\boldsymbol { x } _ { j } ^ { \mathrm { ( c ) } }$ 之间的相似性度量 $S _ { c } \left( \pmb { x } _ { i } ^ { \mathrm { ( c ) } } , \pmb { x } _ { j } ^ { \mathrm { ( c ) } } \right)$ 。

# 2.1.3混合型数据的相似度矩阵

从上面的内容可以很容易地发现数值型数据的相似性度量方法是通过高斯核函数把数值型数据点之间的相似性度量转换为无向加权图边上的权值，构建出一个高斯核函数矩阵 $W _ { \mathrm { { \ell } } }$ 。而对于分类型数据来说，分类型数据的相似性度量方法则是利用了信息熵的概念计算每个分类属性的权重，然后利用计算出来的权重把分类型数据点之间的相似性度量乘以对应权重求和，构建了一个影响因子矩阵 $F _ { \mathrm { { c } } }$

对于分类属性，本文在建立相似性度量矩阵时，虽然每个分类属性在分类型数据部分对相似度的计算有不同的贡献，但是对分类属性的利用信息熵进行了处理，则可以认为当分类型数据点之间相同的个数越多时，数据间相似性越大；分类属性相同的个数越少时，数据相似性越小。所以本文的混合型数据的相似度矩阵 $s$ 用高斯核函数矩阵 $\pmb { W }$ 和影响因子矩阵 $F$ 点乘得到，公式如下：

$$
S = F \cdot W = \left[ \begin{array} { c c c c } { S ( 1 , 1 ) } & { \cdots } & { \cdots } & { S ( 1 , \mathfrak { n } ) } \\ { \vdots } & { \ddots } & { \cdots } & { \vdots } \\ { \vdots } & { S ( \mathrm { i , j } ) } & { \ddots } & { \vdots } \\ { S ( \mathrm { n , 1 } ) } & { \cdots } & { \cdots } & { S ( \mathrm { n , n } ) } \end{array} \right]
$$

# 2.2算法实现

2.2.1EBSCMD算法的实现流程EBSCMD算法流程如图1所示。

开始  
设置聚类数目、高斯核函数  
参数g。输入数值型数据和  
分类型数据两个数据集  
按2.1节构建数值型数据的高斯核函数  
矩阵W、分类型数据的影响因子矩阵F  
以及混合数据的相似度矩阵S  
↑  
按公式（14）构建拉普拉斯矩  
阵L，并按公式（15）标准化拉  
普拉斯矩阵  
↑  
计算标准化的拉普拉斯矩阵  
的最小的k个特征值所对应的  
特征向量，组成特征矩阵M  
↓  
用k-means对特征  
矩阵M进行聚类  
得到被标记的n  
个样本  
结束

按EBSCMD算法过程描述如下：

输入：混合型数据中的数值型数据和分类型数据两个数据集，聚类个数k。

输出：被标记聚类类别的 $\mathfrak { n }$ 个样本，即 $C = \left( c _ { 1 } , c _ { 2 } , \cdots , c _ { n } \right)$ 。

a)对输入的数值型数据进行标准化处理，构建数值型数据的高斯核函数矩阵 $\pmb { W } _ { \mathrm { c } }$

b)对输入的分类型数据利用信息熵公式计算每个分类属性的权重，构建分类型数据的影响因子矩阵 $F$ 。高斯核函数矩阵 $\pmb { W }$ 与影响因子矩阵 $F$ 点乘得到混合数据的相似度矩阵 $s$ 。

c)根据相似度矩阵 $s$ 得到度矩阵 $\pmb { D }$ ，构建拉普拉斯矩阵 $L ,$ （20公式如下：

$$
\pmb { L } = \pmb { D } - \pmb { S }
$$

标准化拉普拉斯矩阵得到 $\scriptstyle { \vec { L } }$ ，公式如下：

$$
\pmb { L } ^ { ' = } \pmb { D } ^ { - 1 / 2 } \pmb { L } \pmb { D } ^ { - 1 / 2 }
$$

其中：度矩阵 $\textbf {  { D } }$ 对角元素 $d _ { i } = { \sum _ { j = 1 } ^ { n } S \left( i , j \right) }$ 。

d)计算标准化的拉普拉斯矩阵 $\dot { L }$ 的最小的 $k _ { \mathrm { 1 } }$ 个特征值所对应的特征向量，并对 $k _ { \mathrm { 1 } }$ 个特征向量组成的矩阵进行标准化处理，最终组成 $n \times k _ { \mathrm { 1 } }$ 维的特征矩阵 $M _ { \circ }$ 在实验过程中，为了能够快速地找出最优解，参数 $k _ { \mathrm { { \scriptscriptstyle 1 } } }$ 的选取基本等于聚类个数 $\mathbf { k }$ 或稍大于 $\mathbf { k }$ 。

e)对特征矩阵 $\pmb { M }$ 使用 $\mathbf { k }$ -means算法进行最终得出被标记聚类类别的 $\mathfrak { n }$ 个样本。

# 2.2.2计算复杂度分析

本文算法第1步计算数值型数据的高斯核函数矩阵 $\pmb { W }$ ，时间复杂度为 $O \big ( m n ^ { 2 } \big )$ ，其中 $\mathfrak { n }$ 为样本数目， $\mathbf { m }$ 表示数值属性维数；第2步计算分类型数据的影响因子矩阵 $F$ 和构建相似度矩阵 $s$ ，时间复杂度为 $O \left( 2 c n ^ { 2 } \right) + O \left( n ^ { 2 } \right) + O \left( 2 n \right)$ ，其中 $\mathfrak { n }$ 为样本数目，c表示分类属性维数；第3和4步对相似度矩阵 $s$ 进行特征分解，时间复杂度为 $O \left( n ^ { 3 } \right)$ ；第5步对特征矩阵M进行 $\mathbf { k }$ means聚类，时间复杂度为 $O { \big ( } k n t { \big ) }$ ，其中 $\mathbf { k }$ 表示聚类数目，t表示 $\mathbf { k }$ -means迭代次数。所以本算法的时间复杂度为$O \left( n ^ { 3 } \right) + O \left( ( 2 c + m + 1 ) n ^ { 2 } \right) + O \left( ( \mathrm { k t } + 2 ) n \right)$ 。本文算法和传统的谱聚类算法在时间复杂度上基本处于同一个级别。

# 3 实验分析

为了研究EBSCMD算法的有效性，本文将其应用于UCI机器学习知识库中的混合数据集。实验中的操作系统为Windows10,集成开发环境为Python3。硬件条件为CPU为IntelCore i7$2 . 8 \ : \mathrm { G H z }$ ，内存为8GB。

# 3.1 实验结果分析

本节主要对EBSCMD 算法进行对比实验与分析。从UCI机器学习知识库中选取了四个混合类型数据集，并与其他三个经典算法进行了比较，验证本算法的可行性和有效性。

为了验证EBSCMD算法的有效性，实验中使用了从UCI机器学习知识库中获取的四个混合类型的数据集：Heart、CreditApproval、Australian CreditApproval、BankMarketing。这些数据集的详细信息由表1列出。表1中列举了四个数据集的聚类个数、维度（即数值属性个数加上分类属性个数）、和数据集中的对象个数。

表1混合类型数据集的详细信息  

<html><body><table><tr><td>Data set</td><td>Cluster</td><td>Dimension(M + M.)</td><td>N</td></tr><tr><td>Heart</td><td>2</td><td>6+7</td><td>270</td></tr><tr><td>Credit Approval</td><td>2</td><td>6+9</td><td>653</td></tr><tr><td>Australian Credit Approval</td><td>2</td><td>6+8</td><td>690</td></tr><tr><td>Bank Marketing</td><td>2</td><td>7+9</td><td>4521</td></tr></table></body></html>

在这四个混合类型数据集的基础上，分别用EBSCMD、K-Prototypes、OCIL、KL-FCM-GM算法对以上数据集进行了聚类实验。同时，本文使用聚类精度（ACC）来度量聚类结果的准确度。对于N个不同的样本， $Y = \left( y _ { 1 } , y _ { 2 } , \cdots , y _ { n } \right)$ 表示真正的类别标签， $C = \left( c _ { 1 } , c _ { 2 } , \cdots , c _ { n } \right)$ 表示本文预测的聚类标签。ACC 的计算公式为

$$
A C C = \sum _ { i = 1 } ^ { N } \sigma { \big ( } y _ { i } , m a p ( \mathbf { c } _ { i } ) { \big ) } / \mathbf { N }
$$

这里map(是通过匈牙利算法将每一个聚类标签映射到一个类别标签，这个映射是最优的，如果 $y _ { i } = m a p ( \mathbf { c } _ { i } )$ 则$\sigma \big ( y _ { i } , m a p ( \mathbf { c } _ { i } ) \big )$ 就等于1或者 $0 _ { \circ }$ 此外， $\mathrm { ~  ~ N ~ }$ 是数据集中的对象个数，ACC值越高，聚类的性能就越好。

EBSCMD算法在实验中式(4)中的参数o的变化是1.0\~15.0，参数值每次增加0.5来寻找最优的聚类效果。K-Prototypes 算法中的参数 $\boldsymbol { \gamma }$ 的变化是 $0 . 1 { \sim } 2 . 1$ ，每次增加0.1;KL-FCM-GM算法中的参数 $\lambda$ 的变化同样是0.1\~2.1，每次增加0.1。在表2中本文列举出来了EBSCMD、K-Prototypes、OCIL、KL-FCM-GM算法四种算法的聚类精度。

EBSCMD、K-Prototypes、OCIL和KL-FCM-GM算法在四个UCI数据集上的参数选择及聚类准确率分别在表 2\~5中列出。

从表2可以看出，算法K-Prototypes、OCIL、KL-FCM-GM在Heart数据集上的聚类准确率的均值分别为0.7830、0.7411和0.7926；而EBSCMD算法在 $\sigma = 2 . 0$ 时聚类准确率为0.8333，比K-Prototypes、OCIL、KL-FCM-GM算法聚类准确率分别高出了 $5 . 0 3 \%$ ， $9 . 2 2 \%$ ， $4 . 0 7 \%$ ，因此EBSCMD算法性能更好。

表2Heart数据集上的实验结果  

<html><body><table><tr><td>Data set</td><td>Heart</td></tr><tr><td>EBSCMD</td><td>ACC</td></tr><tr><td>Para</td><td>k=2，σ=2.0</td></tr><tr><td>K-Prototypes</td><td>0.7830 ± 0.0445</td></tr></table></body></html>

<html><body><table><tr><td></td><td>Para</td><td>k=2，γ=0.2</td></tr><tr><td>OCIL</td><td>ACC</td><td>0.7411 ± 0.0678</td></tr><tr><td rowspan="3">KL-FCM-GM</td><td>Para</td><td>k=2</td></tr><tr><td>ACC</td><td>0.7926± 0</td></tr><tr><td>Para</td><td>k=2，λ=0.8</td></tr></table></body></html>

从表3可以看出，算法K-Prototypes、OCIL、KL-FCM-GM在CreditApproval数据集上的聚类准确率的均值分别为0.8017、0.6634和0.5914；而EBSCMD算法在 $\sigma = 1 3 . 0$ 时聚类准确率为0.8254，比K-Prototypes、OCIL、KL-FCM-GM算法聚类准确率分别高出了 $2 . 3 7 \%$ 、 $1 6 . 2 \%$ 、 $23 . 4 \%$ ，因此EBSCMD算法性能更好。

表3CreditApproval数据集上的实验结果  

<html><body><table><tr><td>Data set</td><td></td><td>Credit Approval</td></tr><tr><td>EBSCMD</td><td>ACC</td><td>0.8254</td></tr><tr><td rowspan="3">K-Prototypes</td><td>Para</td><td>k=2，σ=13.0</td></tr><tr><td>ACC</td><td>0.8017 ± 0.0122</td></tr><tr><td>Para</td><td>k=2，γ=0.1</td></tr><tr><td>OCIL</td><td>ACC</td><td>0.6634± 0.0407</td></tr><tr><td rowspan="3">KL-FCM-GM</td><td>Para</td><td>k=2</td></tr><tr><td>ACC</td><td>0.5914 ± 0.0847</td></tr><tr><td>Para</td><td>k=2，λ=0.3</td></tr></table></body></html>

从表4可以看出，算法K-Prototypes、OCIL、KL-FCM-GM在Australian CreditApproval 数据集上的聚类准确率的均值分别为0.7955、0.6668和0.8319；而EBSCMD算法在 $\sigma = 1 3 . 5$ 时聚类准确率为0.8319，比K-Prototypes、OCIL、KL-FCM-GM算法聚类准确率分别高出了 $3 . 6 4 \%$ 、 $1 6 . 5 1 \%$ 、 $0 . 0 0 \%$ ，因此EBSCMD算法性能更好。

表4AustralianCreditApproval数据集上的实验结果  

<html><body><table><tr><td>Data set</td><td></td><td>Australian Credit Approval</td></tr><tr><td>EBSCMD</td><td>ACC</td><td>0.8319</td></tr><tr><td rowspan="3">K-Prototypes</td><td>Para</td><td>k=2，σ=13.5</td></tr><tr><td>ACC</td><td>0.7955± 0.0180</td></tr><tr><td>Para</td><td>k=2，γ=1.0</td></tr><tr><td>OCIL</td><td>ACC</td><td>0.6668±0.0382</td></tr><tr><td rowspan="3">KL-FCM-GM</td><td>Para</td><td>k=2</td></tr><tr><td>ACC</td><td>0.8319 ± 0</td></tr><tr><td>Para</td><td>k=2，λ=1.5</td></tr></table></body></html>

从表5可以看出，算法K-Prototypes、OCIL、KL-FCM-GM在BankMarketing数据集上的聚类准确率的均值分别为0.6134、0.6245和0.5400；而EBSCMD算法在 $\sigma = 2 . 0$ 时聚类准确率为0.6350，比K-Prototypes、OCIL、KL-FCM-GM算法聚类准确率分别低了 $2 . 1 6 \%$ ， $1 . 0 5 \%$ ， $9 . 5 0 \%$ ，因此EBSCMD 算法性

能更好。

表5BankMarketing 数据集上的实验结果  

<html><body><table><tr><td>Data set</td><td></td><td>Bank Marketing</td></tr><tr><td>EBSCMD</td><td>ACC</td><td>0.6350</td></tr><tr><td rowspan="3">K-Prototypes</td><td>Para</td><td>k=2，σ=2.0</td></tr><tr><td>ACC</td><td>0.6134 ± 0.0817</td></tr><tr><td>Para</td><td>k=2，γ=0.2</td></tr><tr><td rowspan="2">OCIL</td><td>ACC</td><td>0.6245 ± 0.0372</td></tr><tr><td>Para</td><td>k=2</td></tr><tr><td rowspan="2">KL-FCM-GM</td><td>ACC</td><td>0.5400 ± 0.0133</td></tr><tr><td>Para</td><td>k=2，λ=0.3</td></tr></table></body></html>

![](images/9f41870c49cf20bc9b4cdaac1a409902fbfdba2f24486690dd5e049e4265fc63.jpg)  
图2EBSCMD与其他算法对比

图2汇总了本文算法和对比算法在四个UCI数据集上的聚类准确率。由图2可以看出，在所选取混合类型数据集上EBSCMD算法的聚类准确率是这四种算法中较高的，证明了EBSCMD算法的有效性，显示出本文算法在处理混合属性数据时的可行性。EBSCMD 算法具有较好的聚类效果的原因在于：EBSCMD算法利用信息熵对混合数据中分类型数据进行处理，与利用高斯核函数计算数值型数据的相似度的方法相结合，避免了分类型数据和数值型数据的特征转换和参数调整。这种相似性度量方式应用简单，且具有广泛的覆盖性，并且EBSCMD算法在参数固定后运行稳定且不具有随机性，表明本文算法具有较高的稳定性以及良好的鲁棒性。

# 3.2 算法执行时间

表6列出了EBSCMD算法在四个UCI数据集上的平均执行时间。算法的执行时间和数据集的维度与数据量相关。从表6 可以看出，Heart、Credit Approval、Australian Credit Approval三个数据集的数据量相对较小，因此算法执行时间较短；而BankMarketing数据集的数据量相对较大，因此算法执行时间较长。

表6EBSCMD算法在各个数据集上的时间复杂度统计  

<html><body><table><tr><td>Data set</td><td>平均执行时间/s</td></tr><tr><td>Heart</td><td>2.6s</td></tr><tr><td>Credit Approval</td><td>15.2s</td></tr></table></body></html>

<html><body><table><tr><td>Australian Credit Approval</td><td>15.6s</td></tr><tr><td>Bank Marketing</td><td>617.8s</td></tr></table></body></html>

# 4 结束语

本文总结现有的混合型数据聚类算法原理以及各自的优缺点，提出了一种基于信息熵的混合数据谱聚类算法。该方法引入了一种新的基于信息熵的混合型数据的相似性度量用于谱聚类算法中，基于信息熵的方法处理混合型数据中的分类型数据，建立起分类型数据间的关联，并与数值型数据的高斯核函数计算方式相结合，更准确地计算了混合类型数据的相似性度量；又把这种相似性度量方式与谱聚类算法相结合，使算法可以处理任意形状的数据，从而提高了聚类准确度以及算法的鲁棒性。

EBSCMD算法能有效地处理混合属性数据的聚类问题。虽然建立了分类型数据间的关联，但并没有考虑数值型数据间的关联以及其本身重要度对实验结果的影响。在下一步的研究工作中，将考虑摆脱谱聚类算法本身的高斯核函数矩阵，用信息熵的方式处理数值型数据，建立其内部的关联性，进一步的对混合属性数据进行高效地聚类。

# 参考文献：

[1]On N I,Boongoen T,Kongkotchawan N.A new link-based method to ensemble clustering and cancer microarray data analysis [J]. International Journal of Collaborative Intelligence,2014,1(1): 45.   
[2]Ludwig S A.MapReduce-based fuzzy C-means clustering algorithm: implementation and scalability [J].International Journal of Machine Learning& Cybermetics,2015,6(6): 923-934.   
[3]Bouras C,Tsogkas V.Assisting cluster coherency via n-grams and clustering as a tool to deal with the new user problem [J]. International Journal of Machine Learning& Cybernetics,2014,7(2):1-14.   
[4]Lloyd S.Least squares quantization in PCM[J]. IEEE Trans on Information Theory,1982,28 (2): 129-137.   
[5]张涛，刘昶，周晓锋，等．基于真实核心点的密度聚类方法[J//OL].计 算机应用研究,2018,35(12):1-7.(Zhang Tao,Liu Chang,Zhou Xiaofeng, et al.Density clustering algorithm based on real core point [J/OL]. Application Research of Computers,2018,35 (12): 1-7.)   
[6]王日宏，崔兴梅，李永珺．自适应调整的布谷鸟搜索K-均值聚类算法 [J//OL].计算机应用研究,2018,35(12):1-7.(Wang Rihong,Cui Xingmei, Li Yongjun. Self-adaptive adjustment of cuckoo search K-means clustering algorithm[J//OL].Application Research of Computers,2018,35(12):1-7.)   
[7] 张文倩，庄华亮，陈翔，等．基于竞争思想的分级聚类算法[J].信息 与控制,2017,46 (5): 614-619.(Zhang Wenqian, Zhuang Hualiang, Chen Xiang, et al. Hierarchicalclustering algorithm based on competitive learning [J].Information and Control,2017,46 (5): 614-619.)   
[8]Huang Zhexue.A fast clustering algorithm to cluster very large categorical data sets in data mining [C]//Proc of Research Issues on Data Mining & Knowledge Discovery, 1997: 1-8.   
[9]Daniel Barbara,LiY,Couto J.COOLCAT:an entropy-based algorithm for categorical clustering[C]//Proc ofDBLP.2002:582-589.   
[10]李桃迎，陈燕，张金松，等．一种面向分类属性数据的聚类融合算法研 究[J].计算机应用研究,2011,28(5):1671-1673.(Li Taoying,Chen Yan, Zhang Jinsong,et al. Clustering ensemble algorithm for categorical data [J]. Application Research of Computers,2011,28 (5):1671-1673.)   
[11]陈晋音，何辉豪．基于密度和混合距离度量方法的混合属性数据聚类 研究[J].控制理论与应用，2015,32(8):993-1002.(Chen Jinyin,He Huihao.Density-based clustering algorithm for numerical and categorical data with mixed distance methods [J].Control Theory and Application,2015, 32 (8):993-1002.)   
[12]Li Cen,Biswas G. Unsupervised learning with mixed numeric and nominal data[J].IEEE Trans on Knowledge& Data Engineering,2002,14(4):673- 690.   
[13] Huang Zhexue.Extensions to the K-means algorithm for clustering large data sets with categorical values [J].Data Mining& Knowledge Discovery, 1998,2 (3): 283-304.   
[14] Chatzis S P.A fuzzy c-means-type algorithm for clustering of data with mixed numeric and categorical atributes employing a probabilistic dissimilarity functional [J].Expert Systems with Applications,2011,38(7): 8684-8689.   
[15] Cheung YM,Jia H.Aunified metric for categorical and numerical attributes in data clustering [M]//Advances in Knowledge Discovery and Data Mining. Berlin: Springer,2013:135-146.   
[16]Ding Shifei,Du Mingjing,Sun Tongfeng,et al.An entropy-based density peaks clustering algorithm for mixed type data employing fuzzy neighborhood [J]. Knowledge-Based Systems,2017 (133): 294-313.   
[17] Fan R K C. Spectral graph theory [M]// American Mathematical Society. 1997.   
[18]乔晓明，潘晓英．基于稀疏图的鲁棒谱聚类算法[J//OL].计算机应用 研究,2018,35 (6):1-2.(Qiao Xiaoming,Pan Xiaoying.Robust spectral clustering based on sparse graph [J//OL].Application Research of Computers,2018,35 (6): 1-2.)   
[19]马恒，丁世飞．一种基于混合数据相似性度量的谱聚类算法 [J].小型 微型计算机系统,2016,37(8):1746-1750.(MaHeng,Ding Shifei.Spectral clustering algorithm based on of mixed data similarity measure [J].Journal of Chinese Computer System,2016,37(8):1746-1750.)