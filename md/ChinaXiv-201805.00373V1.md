# 基于对偶图正则化的多层概念分解算法

张显 叶军

(南京邮电大学 理学院，南京 210023)

摘要：摘要：为了进一步挖掘数据间的隐藏信息，在多层概念分解(MCF)算法的框架下，考虑每一层分解下的数据流形和特征流形，提出了一种基于对偶图正则化的多层概念分解(DGMCF)算法。该算法通过对数据的逐层分解，以分层的方式学习，并在每一层分解数据中构建数据空间和特征属性空间的拉普拉斯图，用于反映数据流形和特征流形的多元几何结构信息，从而能够更好地从复杂数据中提取出更有效的特征。采用交替选代的方法求解算法的目标函数并证明了算法的收敛性。通过在三个真实数据库(TDT2、PIE、COIL20）上的实验表明，该方法在数据的聚类表示效果方面优于其他方法。

关键词：概念分解；多层分解；对偶回归；流形学习；聚类 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2017.10.0935

# Dual-graph regularized multilayer concept factorization

Zhang Xian, Ye Jun (School of Natural Sciences,Nanjing University ofPosts&Telecommunications,Nanjing210023,China)

Abstract: In order to further excavate the hidden information between data,underthe framework of multilayer concept factorization (MCF）algorithm，this paper proposedanovel algorithmcalled dual-graphregularized multilayer concept factorization(DGMCF)algorithm,which encoded thegeometricstructure informationofdataandfeature spaces byconstructing twoLaplacianregularizeterm ineachlayerfactorization,respectively.Bythis way,theproposed methodcouldlearnfeatures in ahierarchical manner,and thus providedabeterchanceforlearning meaningfulfeatures fromthecomplexdata.Moreover,it developed the iterativeupdating optimization scheme for DHCF,andalso provided theconvergence proofoftheoptimization scheme.ExperimentalresultsonTDT2documentdatasets,PIEandCOIL20imagedatasetsdemonstratetheefectivenessofour proposed method.

Key Words: CF; multilayer factorization; dual regularized; manifold learning; clustering

# 0 引言

如何从海量的高维数据中挖掘出隐藏信息和有效数据，已成为现今机器学习、数据挖掘、社会网络分析等领域的研究热点[1\~3]。合适的数据表示方式能够挖掘出数据中的潜在结构，有利于数据进一步的处理。目前，矩阵分解方法作为一种有效的数据处理方式引起了许多研究者的关注。常用的矩阵分解算法包括奇异值分解(singularvalue decomposition,SVD)、非负矩阵分解(nonnegative matrix factorization，NMF)[4]和 概念分解(concept factorization, CF)[5]等。

在NMF和CF的框架下，已有许多文献对其进行了拓展。结合标签信息，Liu等人[提出了半监督的矩阵分解方法，一种是约束非负矩阵分解(constrainedNMF,CNMF)，另一种是约束概念分解(constrainedCF,CCF)[7]。这两种方法都是将标签信息作为硬约束分别嵌入在NMF和CF框架中的。将流形学习的思想[8\~11融入至NMF和CF方法中，文献[12]提出了图正则的非负矩阵分解（graph regularizedNMF,GNMF）算法，文献[13]提出了局部连续概念分解算法(locallyconsistentCF,LCCF)，这两种方法在文本聚类及人脸识别等应用中均取得了不错的效果。

然而以上方法均是对数据进行单层分解。已有文献表明[14,15]，对数据进行单层分解很难获取原始数据中隐藏的层次信息，从而不能更好地对数据进行表示。因此，X.Lietal.[16]提出了多层非负矩阵分解(MultilayerNMF,MNMF)算法，该方法能更好的从混合信号中对原信号进行分离。在CF的框架下，Li等人[16]提出了多层概念分解(multilayerCF,MCF)，通过利用多层模型，MCF方法能够从高维数据中获取数据隐藏的层次信息。考虑到数据的几何结构信息，最近Li等人[17在MCF方法的基础上，在每一层概念分解中结合流形学习的思想，提出了图回归的多层概念分解(graph regularized multilayerCF,GMCF)。GMCF方法不仅使用了多层结构，而且还考虑了每个数据层的流形几何结构，的确有助于挖掘数据最本质的信息。

GNMF、LCCF和GMCF方法都利用了数据的空间结构信息，它们可以有效地提高学习的质量，然而这些工作只考虑了数据空间的分布结构，没有利用特征属性空间的结构信息。最近，Shang 和Ye 等人[18,19]分别在非负矩阵分解和概念分解框架下提出了同时考虑了数据流形和特征流形的几何结构的双图正则化非负矩阵分解(Graph Dual regularization NonnegativeMatrixFactorization,DNMF)算法和双图正则化概念分解(graphdual regularization concept factorization,GCF)算法，均取得了不错的效果。这也进一步说明了不但数据空间的几何结构信息可以有效地提高学习的质量，同时特征属性空间的几何结构信息也能对学习的质量起到辅助作用。

因此，为了进一步挖掘数据间的隐藏信息，同时利用好数据的几何结构信息，在多层概念分解(MCF)算法的框架下，考虑每一层分解下的数据流形和特征流形，提出了一种基于对偶图正则化的多层概念分解算法(dual graphregularizedmultilayerconcept factorization，DGMCF)。该算法在每一层分别在数据空间和特征空间构建图来反映它们各自的分布流形几何结构信息，以此来获得数据的几何结构信息。建立基于对偶图正则化的多层概念分解模型，推导出该算法的交替迭代更新规则，给出该算法的收敛性证明，实验结果表明了算法的有效性和准确性。

# 1 相关工作

# 1.1概念分解(CF)算法

给定非负矩阵 ${ \pmb X } = \left[ { \pmb x } _ { 1 } , \cdots , { \pmb x } _ { N } \right] \in { \pmb R } ^ { M \times N }$ ， $\scriptstyle { \boldsymbol { X } }$ 的每一列代表一个样本。CF 算法的目标是寻求两个非负矩阵 $\pmb { W } = [ w _ { j k } ] \in \pmb { R } ^ { N \times K }$ ，$\pmb { V } = [ \nu _ { j k } ] \in \pmb { R } ^ { N \times K }$ ，其中 $K \ll \operatorname* { m i n } \left\{ M , N \right\}$ ，使其满足 $\pmb { X } \approx \pmb { X } \pmb { W } \pmb { V } ^ { T }$ 。CF 的目标函数可表示为

$$
\operatorname* { m i n } _ { W , V } : J _ { C F } = \left\| X - X W V ^ { T } \right\| _ { F } ^ { 2 } s . t . W , V \geq 0
$$

相应的乘积更新迭代规则在文献[5]中已详细地给出。

# 1.2多层概念分解(MCF)算法

面对一些复杂数据，特别是病态数据，Li 等人[16在概念分解的基础上采用分层的方法，逐层地对数据进行概念分解，提出了多层概念分解(MCF)算法。MCF 的思想是：记 $X = X W _ { 1 } V _ { 1 }$ 为第1层分解，将 $V _ { _ { 1 } }$ 作为初始数据进行第二层分解得$V _ { 1 } = V _ { 1 } W _ { 2 } V _ { 2 }$ ，依此类推，得到第 $L$ 层的概念分解 $\pmb { V } _ { L - 1 } = \pmb { V } _ { L - 1 } \pmb { W } _ { L } \pmb { V } _ { L }$ ，则最终 $X = X W _ { 1 } V _ { 1 } W _ { 2 } V _ { 2 } { \cdots } W _ { L } V _ { L }$ ，且 ${ \cal W } = { \cal W } _ { 1 } V _ { 1 } W _ { 2 } V _ { 2 } \cdots$ WL， $V = V _ { \ L }$ 。多层概念分解的目标函数可表示为

$$
\operatorname* { m i n } _ { W _ { l } , V _ { l } } : J _ { M C F } = \left\| X _ { l } - X _ { l } W _ { l } V _ { l } ^ { T } \right\| _ { F } ^ { 2 } s . t . W _ { l } , V _ { l } \geq 0
$$

相应的乘积更新迭代规则在文献[5]中已详细地给出。

# 1.3双图正则化概念分解(GCF)算法

Ye 等人[19]在概念分解算法的基础上同时考虑了数据和特征属性的几何结构信息，提出了双图正则化的概念分解算法。其目标函数可表示为

$$
\begin{array} { r l } & { \underset { W , V } { \operatorname* { m i n } } : J _ { G C F } = \left\| X - X W V ^ { T } \right\| ^ { 2 } } \\ & { \quad \quad \quad + \alpha \operatorname { T r } ( V ^ { T } L _ { \mathrm { v } } V ) + \beta \operatorname { T r } ( W ^ { T } L _ { \mathrm { w } } W ) } \end{array}
$$

$$
s . t . \ W , V \geq 0
$$

$$
 { \boldsymbol { L } } _ { \mathrm { { w } } } =  { \boldsymbol { X } } ^ { T }  { \boldsymbol { L } } _ { U }  { \boldsymbol { X } } =  { \boldsymbol { X } } ^ { T } (  { \boldsymbol { D } } ^ { \mathrm { { U } } } -  { \boldsymbol { S } } ^ { U } )  { \boldsymbol { X } } =  { \boldsymbol { D } } ^ { \mathrm { { w } } } -  { \boldsymbol { S } } ^ { W }
$$

针对式(3)的乘积更新迭代规则在文献[16]中已详细地给出。

# 2 基于对偶图正则化的多层概念分解(DGMCF)

# 2.1 构建对偶图正则项

最近的研究表明：不仅观测到的数据分布在一个低维子流形上，称之为数据流形；而且数据的特征也分布在一个低维子流形上，称之为特征流形[18]。在对数据进行概念分解的过程中，由于每一层数据分解后均涉及数据流形及特征流形的几何结构信息获取，所以在每一层分别用两个图来刻画数据流形和特征流形的几何结构，即数据图和特征图。

第 $l$ 层分解下数据图构造

设第 $\mathbf { \Phi } _ { l }$ 层分解下图的顶点集合为数据集 $\left\{ ( \mathbf { x } _ { 1 } ) _ { l } , \cdots , ( \mathbf { x } _ { N } ) _ { l } \right\}$ ，若第 $j$ 个样本与第 $s$ 个样本互为近邻点，则第 $j$ 个样本与第 $s$ 个样本之间存在一条边，其权值为 $( s _ { j s } ^ { V } ) _ { l }$ ，对应的邻域矩阵：

$$
( \mathbf { S } _ { j s } ^ { V } ) _ { l } = \left\{ \begin{array} { l l } { 1 , } & { i f \left( \mathbf { x } _ { s } \right) _ { l } \in N _ { p } \left( ( \mathbf { x } _ { j } ) _ { l } \right) ; } \\ { 0 , } & { o t h e r w i s e . } \end{array} \right. \  \ { j , s = 1 , \cdots , N }
$$

其中： $N _ { p } \Big ( ( \mathbf { x } _ { j } ) _ { l } \Big )$ 表示第 $l$ 层分解下 $\mathbf { X } _ { j }$ 的 $p$ 最近邻数据样本集。此时在第 $\mathbf { \xi } _ { l }$ 层分解下数据图的拉普拉斯矩阵可表示为$\left( \boldsymbol { L _ { \scriptscriptstyle V } } \right) _ { l } = D _ { l } ^ { \scriptscriptstyle V } - S _ { l } ^ { \scriptscriptstyle V }$ 。令 $\pmb { V } _ { l } = \left[ ( \pmb { \nu } _ { 1 } ^ { T } ) _ { l } , \cdots , ( \pmb { \nu } _ { N } ^ { T } ) _ { l } \right] ^ { T }$ 为待求的第 $\mathbf { \xi } _ { l }$ 层分解下的低维数据表示，则其表示的平滑度为

$$
\begin{array} { r l } {  { \big ( \mathcal { O } _ { 1 } \big ) _ { l } = \frac { 1 } { 2 } \sum _ { j , s = 1 } ^ { N } ( \mathbf { S } _ { j s } ^ { V } ) _ { l } \| ( \pmb { \nu } _ { j } ) _ { l } - ( \pmb { \nu } _ { s } ) _ { l } \| ^ { 2 } } } \\ & { = \mathrm { T r } ( \pmb { V } _ { l } ^ { T } \pmb { D } _ { l } ^ { V } \pmb { V } _ { l } ) - \mathrm { T r } ( \pmb { V } _ { l } ^ { T } \pmb { S } _ { l } ^ { V } \pmb { V } _ { l } ) } \\ & { = \mathrm { T r } ( \pmb { V } _ { l } ^ { T } ( \pmb { L } _ { V } ) _ { l } \pmb { V } _ { l } ) } \end{array}
$$

第 $\mathbf { \xi } _ { l }$ 层分解下特征图构造

类似地，在第 $l$ 层分解下将图的顶点集合定义为特征集$\left\{ ( \mathbf { x } _ { 1 } ^ { T } ) _ { l } , \cdots , ( \mathbf { x } _ { M } ^ { T } ) _ { l } \right\}$ ，对应的领域矩阵定义如下：

$$
\begin{array}{c} ( \mathbf { S } _ { j s } ^ { W } ) _ { l } = \left\{ \begin{array} { l l } { 1 , } & { i f ~ ( \mathbf { x } _ { s } ^ { T } ) _ { l } \in N _ { p } \left( ( \mathbf { x } _ { j } ^ { T } ) _ { l } \right) ; } \\ { 0 , } & { o t h e r w i s e . } \end{array} \right. \  \end{array} _ { j , s = 1 , \cdots , M }
$$

可得到在第 $\mathbf { \xi } _ { l }$ 层分解下特征图的拉普拉斯矩阵表示为$( \pmb { L } _ { \pmb { W } } ) _ { l } \ b { = } \pmb { X } _ { l } ^ { T } ( \pmb { L } _ { U } ) _ { l } \pmb { X } _ { l } = \pmb { X } _ { l } ^ { T } ( \pmb { D } _ { l } ^ { U } - \pmb { S } _ { l } ^ { U } ) \pmb { X } _ { l } \ b { = } \pmb { D } _ { l } ^ { V } - \pmb { S } _ { l } ^ { V }$ 令

W=[(w),,(w),]为待求的低维数据表示，则相应的平滑度为

$$
w ^ { ( K + 1 ) } = \arg \operatorname* { m i n } _ { w } G ( w , w ^ { ( K ) } )
$$

$$
\begin{array} { r l } & { \big ( \boldsymbol { \mathcal { O } } _ { 2 } \big ) _ { l } = \displaystyle \frac { 1 } { 2 } \sum _ { j , s = 1 } ^ { M } ( \mathbf { S } _ { j s } ^ { W } ) _ { l } \left\| ( { \boldsymbol { w } } _ { j } ^ { T } ) _ { l } - ( { \boldsymbol { w } } _ { s } ^ { T } ) _ { l } \right\| ^ { 2 } } \\ & { \quad = \operatorname { T r } ( { \boldsymbol { W } } _ { l } ^ { T } \mathbf { { D } } _ { l } ^ { W } { \boldsymbol { W } } _ { l } ) - \operatorname { T r } ( { \boldsymbol { W } } _ { l } ^ { T } \mathbf { { S } } _ { l } ^ { W } { \boldsymbol { W } } _ { l } ) } \\ & { \quad = \operatorname { T r } ( { \boldsymbol { W } } _ { l } ^ { T } ( L _ { w } ) _ { l } { \boldsymbol { W } } _ { l } ) } \end{array}
$$

# 2.2构建DGMCF算法的目标函数

为了同时考虑样本的数据流形和特征流形的几何结构信息，在MCF算法的目标函数中添加基于数据图和特征图的正则项，得到DGMCF算法的目标函数为

$$
\begin{array} { r l } & { \underset { { \boldsymbol { V } _ { l } , \boldsymbol { V } _ { l } } } { \operatorname* { m i n } } : { \boldsymbol { J } _ { D G M C F } } = \left\| \boldsymbol { X } _ { l } - \boldsymbol { X } _ { l } \boldsymbol { W } _ { l } \boldsymbol { V } _ { l } ^ { T } \right\| ^ { 2 } + \alpha \big ( \boldsymbol { \mathcal { O } } _ { 1 } \big ) _ { l } + \beta \big ( \boldsymbol { \mathcal { O } } _ { 2 } \big ) _ { l } } \\ & { s . t . \quad { \boldsymbol { W } _ { l } , \boldsymbol { V } _ { l } } \ge 0 } \end{array}
$$

其中： $\alpha \ge 0 , \beta \ge 0$ 为正则化参数。

# 2.3 DGMCF目标函数的求解

DGMCF 算法中的目标函数 $J _ { D G M C F }$ 是关于两个变量 $\pmb { W } _ { l }$ 和 $\boldsymbol { V } _ { \iota }$ 的非凸函数，因此求其全局最优解是不现实的。利用交替迭代法可得到问题的局部最优解。记K,=XX,则目标函数JDGMCF可重写为

$$
\begin{array} { r l } & { J _ { D G M C F } = \mathrm { T r } [ ( X _ { l } - X _ { l } W _ { l } V _ { l } ^ { T } ) ^ { \mathbf { T } } ( X _ { l } - X _ { l } W _ { l } V _ { l } ^ { T } ) ] } \\ & { + \alpha \mathrm { T r } \Big ( V _ { l } ^ { T } \big ( L _ { V } \big ) _ { l } V _ { l } \Big ) + \beta \mathrm { T r } \Big ( W _ { l } ^ { T } \big ( L _ { W } \big ) _ { l } W _ { l } \Big ) } \\ & { = \mathrm { T r } \Big ( K _ { l } - 2 V _ { l } W _ { l } ^ { T } K _ { l } + V _ { l } W _ { l } ^ { T } K _ { l } W _ { l } V _ { l } ^ { T } \Big ) } \\ & { + \alpha \mathrm { T r } \Big ( V _ { l } ^ { T } \big ( L _ { V } \big ) _ { l } V _ { l } \Big ) + \beta \mathrm { T r } \Big ( W _ { l } ^ { T } \big ( L _ { W } \big ) _ { l } W _ { l } \Big ) } \end{array}
$$

令 $\Psi _ { \scriptscriptstyle l } = [ \psi _ { \scriptscriptstyle j k } ^ { l } ] , \Phi _ { \scriptscriptstyle l } = [ \varphi _ { \scriptscriptstyle j k } ^ { l } ]$ 为约束 $\pmb { W } _ { l } \ge 0$ 和 $\pmb { V } _ { l } \ge 0$ 对应的拉格 朗日乘子，则式(9)的拉格朗日函数 $\mathbf { L }$ 为

$$
\begin{array} { r l } & { L = \mathrm { T r } \left( K _ { l } - 2 V _ { l } W _ { l } ^ { T } K _ { l } + V _ { l } W _ { l } ^ { T } K _ { l } W _ { l } V _ { l } ^ { T } \right) } \\ & { \quad + \alpha \mathrm { T r } \left( V _ { l } ^ { T } \left( \pmb { L } _ { \nu } \right) _ { l } V _ { l } \right) + \beta \mathrm { T r } \left( \pmb { W } _ { l } ^ { T } \left( \pmb { L } _ { \nu } \right) _ { l } \pmb { W } _ { l } \right) } \\ & { \quad + \mathrm { T r } ( \pmb { \varPsi } _ { l } \pmb { W } _ { l } ^ { T } ) + \mathrm { T r } ( \pmb { \varPhi } _ { l } V _ { l } ) } \end{array}
$$

对函数 $\mathbf { L }$ 分别关于 $\mathbf { \nabla } W _ { l }$ 和 $\boldsymbol { V } _ { \iota }$ 求偏导，由KKT最优性条件可以得到DGMCF算法的更新迭代公式为

$$
\left( \boldsymbol { w } _ { l } \right) _ { j k } ^ { ( t + 1 ) } \gets \left( \boldsymbol { w } _ { l } \right) _ { j k } ^ { ( t ) } \frac { ( K _ { l } V _ { l } + \beta ( S ^ { W } ) _ { l } W _ { l } ) _ { \mathrm { j k } } } { ( K _ { l } W _ { l } V _ { l } ^ { T } V _ { l } + \beta ( D ^ { W } ) _ { l } W _ { l } ) _ { \mathrm { j k } } }
$$

$$
\left( \nu _ { l } \right) _ { j k } ^ { ( t + 1 ) } \gets \left( \nu _ { l } \right) _ { j k } ^ { ( t ) } \frac { ( \mathbf { K } _ { l } \mathbf { W } _ { l } + \boldsymbol { \alpha } ( \boldsymbol { S } ^ { V } ) _ { l } \mathbf { V } _ { l } ) _ { \mathrm { j k } } } { ( \mathbf { V } _ { l } \mathbf { W } _ { l } ^ { T } \mathbf { K } _ { l } \mathbf { W } _ { l } + \boldsymbol { \alpha } ( \boldsymbol { D } ^ { V } ) _ { l } \mathbf { V } _ { l } ) _ { \mathrm { j k } } }
$$

DGMCF方法将在迭代次数达到最大时停止或在停止准则$\left\| J _ { D G M C F } ^ { t } - J _ { D G M C F } ^ { t - 1 } \right\| < \varepsilon$ 满足时停止迭代。

# 2.4DGMCF算法的收敛性证明

定义1当满足条件： $G \big ( w , w ^ { \prime } \big ) \geq F \big ( w \big )$ 和 $G { \big ( } w , w { \big ) } = F { \big ( } w { \big ) }$ 时，$G \big ( w , w ^ { \prime } \big )$ 为 $F { \big ( } w { \big ) }$ 的一个辅助函数。

引理1若 $G$ 为 $F$ 的辅助函数，则函数 $F$ 在如下的更新公式下为单调下降的。

证明

$$
F ( w ^ { ( K + 1 ) } ) { \le } G ( w ^ { ( K + 1 ) } , w ^ { ( K ) } ) { \le } G ( w ^ { ( K ) } , w ^ { ( K ) } ) { = } F ( w ^ { ( K ) } ) \cdot
$$

令 $\left( w _ { l } \right) _ { a b }$ 为矩阵 $\mathbf { \nabla } W _ { l }$ 的元素， $F _ { ( w _ { l } ) _ { a b } }$ 为目标函数 $J _ { D G M C F }$ 中仅与 $\left( w _ { l } \right) _ { a b }$ 元素有关的项，即

$$
F _ { \left( w _ { l } \right) _ { a b } } = \left\| X _ { l } - X _ { l } W _ { l } V _ { l } ^ { T } \right\| ^ { 2 } + \beta \operatorname { T r } \left( W _ { l } ^ { T } \left( \pmb { L } _ { w } \right) _ { l } W _ { l } \right)
$$

考虑到算法是基于元素运算的，故首先证明 $F _ { \left( w _ { l } \right) _ { a b } }$ 在式(11)下为单调下降的。事实上由于：

$$
F _ { ( w _ { l } ) _ { a b } } ^ { \prime } = \left( - 2 K _ { l } V _ { l } + 2 K _ { l } W _ { l } V _ { l } ^ { T } V _ { l } + 2 \beta \big ( { \pmb { L } } _ { w } \big ) _ { l } W _ { l } \right) _ { a b }
$$

$$
F _ { \left( w _ { l } \right) _ { a b } } ^ { \prime \prime } = 2 \big ( { \pmb K } _ { l } \big ) _ { a a } \left( { \pmb V } _ { l } ^ { T } { \pmb V } _ { l } \right) _ { b b } + 2 \beta \big ( \big ( { \pmb L } _ { \pmb W } \big ) _ { l } \big ) _ { a a }
$$

引理2函数 $G ( w _ { l } , \left( w _ { l } \right) _ { a b } ^ { ( t ) } )$ 为 $F _ { \left( w _ { l } \right) _ { a b } }$ 的辅助函数。

$$
\begin{array} { r l } & { G ( w _ { l } , \left( w _ { l } \right) _ { a b } ^ { ( t ) } ) = F _ { ( w _ { l } ) _ { a b } } ( \left( w _ { l } \right) _ { a b } ^ { ( t ) } ) } \\ & { + F _ { ( w _ { l } ) _ { a b } } ^ { \prime } ( \left( w _ { l } \right) _ { a b } ^ { ( t ) } ) ( w _ { l } - \left( w _ { l } \right) _ { a b } ^ { ( t ) } ) } \\ & { + \frac { ( K _ { l } W _ { l } V _ { l } ^ { T } V _ { l } ) _ { a b } + \beta ( ( \pmb { D } ^ { W } ) _ { l } W _ { l } ) _ { a b } } { \big ( w _ { l } \big ) _ { a b } ^ { ( t ) } } ( w _ { l } - \left( w _ { l } \right) _ { a b } ^ { ( t ) } ) ^ { 2 } } \end{array}
$$

证明 由定义1，显然 $G ( w _ { l } , w _ { l } ) = F _ { ( w _ { l } ) _ { a b } } ( w _ { l } )$ 。令 $F _ { \left( w _ { l } \right) _ { a b } } ^ { } \left( w _ { l } \right)$ 的Taylor展开序列为

$$
\begin{array} { r l } & { F _ { \left( w _ { l } \right) _ { a b } } \left( w _ { l } \right) = F _ { \left( w _ { l } \right) _ { a b } } ( \left( w _ { l } \right) _ { a b } ^ { \left( t \right) } ) + F _ { \left( w _ { l } \right) _ { a b } } ^ { \prime } ( \left( w _ { l } \right) _ { a b } ^ { \left( t \right) } ) ( w _ { l } - \left( w _ { l } \right) _ { a b } ^ { \left( t \right) } ) } \\ & { \qquad + [ \left( { \pmb { K } } _ { l } \right) _ { a a } \left( { \pmb { V } } _ { l } ^ { T } { \pmb { V } } _ { l } \right) _ { b b } + \beta \big ( \left( { \pmb { L } } _ { w } \right) _ { l } \big ) _ { a b } ] ( w _ { l } - \left( w _ { l } \right) _ { a b } ^ { \left( t \right) } ) ^ { 2 } } \end{array}
$$

由式(15)知，证明 $G ( w _ { l } , \left( w _ { l } \right) _ { a b } ^ { ( t ) } ) \geq F _ { \left( w _ { l } \right) _ { a b } } ( w _ { l } )$ 等价于证明：

$$
\begin{array} { r l } & { \frac { \left( K _ { l } W _ { l } V _ { l } ^ { T } V _ { l } \right) _ { a b } + \beta ( ( \pmb { D } ^ { W } ) _ { l } W _ { l } ) _ { a b } } { \left( w _ { l } \right) _ { a b } ^ { ( t ) } } } \\ & { \qquad \geq ( \pmb { K } _ { l } ) _ { a a } ( \pmb { V } _ { l } ^ { T } V _ { l } ) _ { b b } + \beta \mathopen { } \mathclose \bgroup \left( \left( \pmb { L } _ { w } \right) _ { l } \aftergroup \egroup \right) _ { a a } } \end{array}
$$

事实上：

$$
( K _ { l } W _ { l } V _ { l } ^ { T } V _ { l } ) _ { a b } = \sum _ { i = 1 } ^ { k } \bigl ( K _ { l } W _ { l } \bigr ) _ { a i } \bigl ( V _ { l } ^ { T } V _ { l } \bigr ) _ { i b } \geq \bigl ( K _ { l } W _ { l } \bigr ) _ { a b } \bigl ( V _ { l } ^ { T } V _ { l } \bigr ) _ { b b }
$$

$$
\ge \sum _ { i = 1 } ^ { k } \bigl ( { \pmb K } _ { l } \bigr ) _ { a i } \bigl ( { w } _ { l } \bigr ) _ { i b } ^ { ( t ) } \bigl ( { \pmb V } _ { l } ^ { T } { \pmb V } _ { l } \bigr ) _ { b b } \ge \bigl ( { w } _ { l } \bigr ) _ { a b } ^ { ( t ) } \bigl ( { \pmb K } _ { l } \bigr ) _ { a a } \bigl ( { \pmb V } _ { l } ^ { T } { \pmb V } _ { l } \bigr ) _ { b b }
$$

且

$$
\begin{array} { l } { \displaystyle \beta ( ( { \pmb D } ^ { W } ) _ { l } { \pmb W } _ { l } ) _ { a b } = \beta { \displaystyle \sum _ { j = 1 } ^ { M } } ( ( { \pmb D } ^ { W } ) _ { l } ) _ { a j } \big ( { \pmb w } _ { l } \big ) _ { j b } ^ { ( t ) } \geq \beta ( ( { \pmb D } ^ { W } ) _ { l } ) _ { a a } \big ( { \pmb w } _ { l } \big ) _ { a b } ^ { ( t ) } } \\ { \geq \beta ( ( { \pmb D } ^ { W } ) _ { l } - ( { \pmb S } ^ { W } ) _ { l } ) _ { a a } \big ( { \pmb w } _ { l } \big ) _ { a b } ^ { ( t ) } = \beta ( \big ( { \pmb L } _ { \pmb w } \big ) _ { l } ) _ { a a } \big ( { \pmb w } _ { l } \big ) _ { a b } ^ { ( t ) } } \end{array}
$$

因此，可知式(15)成立，即G(w,(w)ab)≥F()(w）。

引理3函数 $G ( \nu _ { l } , \left( \nu _ { l } \right) _ { a b } ^ { ( t ) } )$ 为 $F _ { \left( v _ { l } \right) _ { a b } }$ 的辅助函数。

$$
\begin{array} { r } { G ( \nu _ { l } , \left( \nu _ { l } \right) _ { a b } ^ { \left( t \right) } ) = F _ { \left( \nu _ { l } \right) _ { a b } } ( \left( \nu _ { l } \right) _ { a b } ^ { \left( t \right) } ) + F _ { \nu _ { a b } } ^ { \prime } ( \left( \nu _ { l } \right) _ { a b } ^ { \left( t \right) } ) ( \nu _ { l } - \left( \nu _ { l } \right) _ { a b } ^ { \left( t \right) } ) } \\ { + \frac { ( V _ { l } W _ { l } ^ { T } K _ { l } W _ { l } ) _ { a b } + \alpha ( ( D ^ { V } ) _ { l } V _ { l } ) _ { a b } } { \left( \nu _ { l } \right) _ { a b } ^ { \left( t \right) } } ( \nu _ { l } - \left( \nu _ { l } \right) _ { a b } ^ { \left( t \right) } ) ^ { 2 } } \end{array}
$$

引理3的证明过程同引理2的证明，限于篇幅，此处具体证明参见引理2。

定理1对于给定的数据 $\scriptstyle { \boldsymbol { \mathbf { \mathit { X } } } }$ 及任意的 $\pmb { W } _ { l } \ge 0$ $\pmb { V } _ { l } \ge 0$ ，提出的交替迭代更新规则式(11)和(12)可使得目标函数JDGMCF(W,V)单调下降。

证明由引理2.3，将式(15)(17)分别代入式(13)得

$$
\begin{array} { c } { { \left( w _ { l } \right) _ { a b } ^ { \left( t + 1 \right) } = \left( w _ { l } \right) _ { a b } ^ { \left( t \right) } - \left( w _ { l } \right) _ { a b } ^ { \left( t \right) } \displaystyle \frac { F _ { \left( w _ { l } \right) _ { a b } } ^ { \prime } \left( \left( w _ { l } \right) _ { a b } ^ { \left( t \right) } \right) } { 2 ( { \boldsymbol { \cal K } } _ { l } W _ { l } V _ { l } ^ { T } V _ { l } ) _ { a b } + 2 \beta ( ( { \boldsymbol { \cal D } } ^ { W } ) _ { l } W _ { l } ) _ { a b } } } } \\ { { = \left( w _ { l } \right) _ { a b } ^ { \left( t \right) } \displaystyle \frac { ( { \boldsymbol { \cal K } } _ { l } V _ { l } + \beta ( { \boldsymbol { \cal S } } ^ { W } ) _ { l } W _ { l } ) _ { a b } } { ( { \boldsymbol { \cal K } } _ { l } W _ { l } V _ { l } ^ { T } V _ { l } + \beta ( { \boldsymbol { \cal D } } ^ { W } ) _ { l } W _ { l } ) _ { a b } } } } \end{array}
$$

$$
\begin{array} { r l r } {  { \big ( \nu _ { l } \big ) _ { a b } ^ { ( t + 1 ) } = \big ( \nu _ { l } \big ) _ { a b } ^ { ( t ) } - \big ( \nu _ { l } \big ) _ { a b } ^ { ( t ) } \frac { F _ { \binom { \prime } { l } _ { l } } ^ { \prime } ( \big ( \nu _ { l } \big ) _ { a b } ^ { ( t ) } ) } { 2 ( V _ { l } W _ { l } ^ { T } K _ { l } W _ { l } ) _ { a b } + 2 \alpha ( ( D ^ { V } ) _ { l } V _ { l } ) _ { a b } } } } \\ & { } & { \qquad = \big ( \nu _ { l } \big ) _ { a b } ^ { ( t ) } \frac { ( K _ { l } W _ { l } + \alpha ( S ^ { V } ) _ { l } V _ { l } ) _ { a b } } { ( V _ { l } W _ { l } ^ { T } K _ { l } W _ { l } + \alpha ( D ^ { V } ) _ { l } V _ { l } ) _ { a b } } } \end{array}
$$

由于式(15)(17)分别为 $F _ { \left( w _ { l } \right) _ { a b } }$ 及 $F _ { ( \nu _ { l } ) _ { a b } }$ 的辅助函数，所以F()及F(vi)分别在迭代更新式(11)(12)下为单调下降。

# 2.5DGMCF算法的具体步骤

输入：数据集矩阵 $\scriptstyle { \boldsymbol { X } }$ 口

1：初始化参数。设定最大迭代次数(IterMax)及误差限 $\mathbf { \sigma } _ { \varepsilon }$ ，设定近邻点参数 $p$ 、分解维度 $K$ 、正则化参数 $\alpha$ 和 $\beta$ 。

2：记 $\pmb { X } _ { 1 } = \pmb { X }$ ，并随机生成非负矩阵 $W$ 和 $\boldsymbol { V }$ 。for $\scriptstyle { l ^ { = 1 } : { L } }$   
for $\scriptstyle { \mathbf { \alpha } } _ { t } = 1$ :IterMax (t为迭代次数)

3：计算数据图和特征图的邻接矩阵(S)和(S"）。

4:计算对角矩阵(D),和(D")，。

5：固定 $V _ { l } ^ { ( t ) }$ ，根据式(10)更新 $\pmb { W } _ { l }$ 得 $\mathbf { \boldsymbol { W } } _ { l } ^ { ( t + 1 ) }$ 。

6：固定 $\mathbf { \boldsymbol { W } } _ { l } ^ { ( t + 1 ) }$ ，根据式(11)更新 $\boldsymbol { V } _ { \iota }$ 得 $V _ { l } ^ { ( t + 1 ) }$ 。

7:重复步骤2和3,直至终止条件 $\left\| J _ { D G M C F } ^ { t } - J _ { D G M C F } ^ { t - 1 } \right\| < \varepsilon$ 被满足，停止迭代,并记X+=V；

8：end for

输出：分解后的矩阵 $\pmb { W } = \prod _ { l = 1 } ^ { L } \pmb { W } _ { l }$ 和 $V = V _ { _ L }$ 6

# 2.6DGMCF算法复杂度分析

为了比较本文所提算法和其他算法的计算复杂度，本文对CF、GCF、GMCF和DGMCF算法的计算复杂度进行了比对。经过 $\mathbf { \Phi } _ { t }$ 次迭代更新后，CF和GCF算法的计算复杂度分别为$O ( t N ^ { 2 } K + N ^ { 2 } M )$ 和 $O ( N ^ { 2 } M + N M ^ { 2 } + t N ^ { 2 } K )$ 。对于GMCF和DGMCF 算法，均对数据进行了 $\mathbf { \Omega } _ { L }$ 层的分解，GMCF 算法构建$\mathfrak { p }$ 最近邻图的计算复杂度为 $O ( N ^ { 2 } M + N ^ { 2 } p )$ ，DGMCF 算法创建数据图和特征图所需的计算复杂度为 $O ( N ^ { 2 } M + N M ^ { 2 } )$ ，所以GMCF和DGMCF算法总的计算复杂度分别为$O ( L ( N ^ { 2 } M + N ^ { 2 } p + t N ^ { 2 } K ) ) ~ , ~ O ( L ( N ^ { 2 } M + N M ^ { 2 } + t N ^ { 2 } K ) )$ 0

# 3 数值实验

# 3.1聚类实验

为了验证本文所提算法的有效性，分别在文本数据库TDT2和图像数据库PIE、COIL20三个数据集上将所提DGMCF算法与CF、LCCF、MCF、GMCF和GCF算法进行了聚类比较实验。聚类实验中常用准确率(accuracy,ACC)和归一化互信息(normalizedmutual information,NMI)[5]作为聚类算法的评价标准。

$\bullet$ TDT2 文本数据库：包含了56类的10021个文档。

$\bullet$ PIE人脸数据库：选择了68人的11554幅图像，除第38个人164幅图像外，其余人都是170幅图像。本实验中图像的大小为 $3 2 ^ { * } 3 2$ 的灰度图像。

$\bullet$ COIL20 物体图像数据库：包含了20个物体的1440 幅图像，图像的大小为 $3 2 ^ { * } 3 2$ 的灰度图像。

实验中，对于MCF、GMCF及DGMCF方法结合文献[],选择 $L { = } 1 0$ ，并且每一层的最大迭代次数设置为500次。对于LCCF、GMCF、GCF和DGMCF方法，构造图所需近邻点数 $p$ 都设置为5。对不同的聚类数 $k$ 0 $k = 2 , \cdots , 1 0 )$ ，DGMCF 算法与五种相关的比较算法在三个数据库上20次实验平均的聚类结果如表$1 { \sim } 3$ 所示。从表 $1 { \sim } 3$ 可得到如下的结论：

a）在TDT2 数据库中，本文所提算法比传统CF 算法平均ACC和NMI分别提高了 $1 1 . 2 3 \%$ 和 $1 1 . 6 7 \%$ ，比GCF算法分别提高了 $1 . 9 4 \%$ 和 $2 . 6 5 \%$ 。比GMCF算法分别提高了 $2 . 2 8 \%$ 和$2 . 3 3 \%$ 。在PIE 数据库中，DGMCF比CF算法平均ACC和NMI分别提高了 $1 3 . 7 0 \%$ 和 $1 2 . 1 8 \%$ ，比GCF算法分别提高了 $3 \%$ 和$2 . 4 5 \%$ 。比GMCF算法分别提高了 $3 . 4 9 \%$ 和 $2 . 9 0 \%$ 。在COIL20数据库中，DGMCF比CF算法平均ACC和NMI分别提高了$1 0 . 9 3 \%$ 和 $1 3 . 1 8 \%$ ，比GCF算法分别提高了 $3 . 3 6 \%$ 和 $4 . 0 2 \%$ 。比GMCF算法分别提高了 $4 . 0 2 \%$ 和 $7 . 1 7 \%$ 。

b)LCCF算法利用了数据分布的几何结构信息，所取得的聚类效果比CF本身要好。这就表明数据分布的几何结构在进行聚类工作时是有效的，特别对图像数据集，它们空间分布具有潜在的流形结构。在三个数据库中GCF算法所得效果优于LCCF算法，这是因为GCF算法不但考虑了数据流形的几何结构信息，而且也利用了特征流形的结构信息。另外，GMCF算法所取得的效果优于CF及LCCF，主要原因是该方法通过逐层分解并在每一层结合数据分布的几何结构信息，使得该方法能够学习出更利于数据表示的特征。

c）最后本文提出的DGMCF算法比GCF算法的聚类质量更好，其主要原因是DGMCF算法利用了多层分解的思想，在每一层分解中结合数据流形及特征流形的结构信息，能够更加深层次地挖掘出表征数据最本质的特征，尤其是在图像数据集中所取得的聚类效果比文本数据集要更加的明显些。

表1TDT2 数据库上的聚类实验结果  

<html><body><table><tr><td rowspan="2">k</td><td colspan="7">accuracy/%</td><td rowspan="2">normalized mutual information/%</td><td colspan="4"></td></tr><tr><td>CF</td><td>LCCF</td><td>MCF</td><td>GMCF</td><td>GCF</td><td>DGMCF</td><td>CF</td><td>LCCF</td><td>MCF</td><td>GMCF</td><td>GCF DGMCF</td></tr><tr><td>2</td><td>86.13</td><td>94.23</td><td>95.34</td><td>96.45</td><td>96.21</td><td>97.31</td><td>67.28</td><td>84.18</td><td>83.49</td><td>85.38</td><td>85.94</td><td>87.79</td></tr><tr><td>3</td><td>79.67</td><td>88.53</td><td>87.63</td><td>89.53</td><td>91.04</td><td>93.56</td><td>68.91</td><td>78.23</td><td>80.12</td><td>83.43</td><td>81.33</td><td>84.63</td></tr><tr><td>4</td><td>78.29</td><td>86.65</td><td>85.46</td><td>87.16</td><td>89.45</td><td>91.28</td><td>69.78</td><td>77.58</td><td>79.94</td><td>81.16</td><td>80.64</td><td>84.46</td></tr><tr><td>5</td><td>73.63</td><td>83.41</td><td>83.62</td><td>84.87</td><td>87.66</td><td>89.63</td><td>64.65</td><td>72.04</td><td>74.36</td><td>76.32</td><td>76.56</td><td>79.36</td></tr><tr><td>6</td><td>74.82</td><td>81.26</td><td>81.47</td><td>83.47</td><td>84.61</td><td>85.42</td><td>67.86</td><td>74.86</td><td>75.28</td><td>77.73</td><td>77.41</td><td>80.24</td></tr><tr><td>7</td><td>70.53</td><td>79.12</td><td>80.11</td><td>80.65</td><td>80.39</td><td>82.25</td><td>66.54</td><td>73.32</td><td>73.36</td><td>75.65</td><td>75.17</td><td>77.55</td></tr><tr><td>8</td><td>67.04</td><td>74.28</td><td>74.87</td><td>76.75</td><td>75.20</td><td>78.32</td><td>68.31</td><td>69.73</td><td>70.23</td><td>73.43</td><td>72.58</td><td>75.76</td></tr><tr><td>9</td><td>67.35</td><td>75.18</td><td>75.68</td><td>75.78</td><td>73.28</td><td>75.85</td><td>69.43</td><td>70.42</td><td>69.68</td><td>71.65</td><td>72.20</td><td>74.05</td></tr><tr><td>10</td><td>68.65</td><td>69.24</td><td>71.56</td><td>71.94</td><td>71.86</td><td>73.54</td><td>69.81</td><td>69.59</td><td>70.45</td><td>71.87</td><td>71.85</td><td>73.76</td></tr><tr><td>Avg.</td><td>74.01</td><td>81.32</td><td>81.75</td><td>82.96</td><td>83.30</td><td>85.24</td><td>68.06</td><td>74. 44</td><td>75.21</td><td>77.40</td><td>77.08</td><td>79.73</td></tr></table></body></html>

表2PIE 数据库上的聚类实验结果  

<html><body><table><tr><td rowspan="2">k</td><td colspan="8">accuracy/%</td><td colspan="5">normalized mutual information/%</td></tr><tr><td>CF</td><td>LCCF</td><td>MCF</td><td>GMCF</td><td>GCF</td><td>DGMCF</td><td>CF</td><td>LCCF</td><td></td><td>MCF</td><td>GMCF</td><td>GCF</td><td>DGMCF</td></tr><tr><td>2</td><td>57.23</td><td>62.89</td><td>66.43</td><td>68.35</td><td>67. 14</td><td>70.38</td><td>48.62</td><td>60.43</td><td>62.17</td><td></td><td>64.23</td><td>64.59</td><td>67.35</td></tr><tr><td>3</td><td>58.14</td><td>58.42</td><td>63.54</td><td>68.46</td><td>69.25</td><td>71.43</td><td>49.14</td><td>57.85</td><td></td><td>56.12</td><td>60.87</td><td>61.78</td><td>64.87</td></tr><tr><td>4</td><td>58.36</td><td>60.12</td><td>64.02</td><td>71.24</td><td>71. 71</td><td>72.57</td><td>47.23</td><td></td><td>53.54</td><td>55.45</td><td>58.63</td><td>58.38</td><td>61.56</td></tr><tr><td>5</td><td>58.89</td><td>60.61</td><td>63.21</td><td>71.36</td><td>72.86</td><td>74. 47</td><td>48.54</td><td></td><td>54.42</td><td>54.48</td><td>57.13</td><td>56.36</td><td>58.88</td></tr><tr><td>6</td><td>57.63</td><td>59.01</td><td>62.53</td><td>68.11</td><td>69.67</td><td>73.54</td><td></td><td>46.13</td><td>51.28</td><td>52.87</td><td>53.76</td><td>54.78</td><td>57.34</td></tr><tr><td>7</td><td>57.80</td><td>59.36</td><td>61.15</td><td>67.32</td><td>70.27</td><td>72.08</td><td></td><td>45.64</td><td>48.24</td><td>49.38</td><td>51.35</td><td>51.87</td><td>54.23</td></tr><tr><td>8</td><td>55.97</td><td>56.12</td><td>60.89</td><td>65.76</td><td>64.03</td><td>69.35</td><td>41.29</td><td></td><td>45.11</td><td>46.12</td><td>48.56</td><td>49.41</td><td>51.54</td></tr><tr><td>9</td><td>57.26</td><td>57.45</td><td>60.43</td><td>64.92</td><td>65.39</td><td>70.18</td><td></td><td>39.56</td><td>42.56</td><td>44. 78</td><td>47. 75</td><td>48.35</td><td>50.05</td></tr><tr><td>10</td><td>56.85</td><td>57.07</td><td>61.32</td><td>64.53</td><td>64.10</td><td>67.45</td><td></td><td>37.45</td><td>40.76</td><td>42.35</td><td>44.85</td><td>45.61</td><td>47.38</td></tr><tr><td>Avg.</td><td>57.57</td><td>59.01</td><td>62.61</td><td>67.78</td><td>68.27</td><td></td><td>71.27</td><td>44.84</td><td>50.47</td><td>51.52</td><td>54.12</td><td>54.57</td><td>57.02</td></tr></table></body></html>

表3COIL20 数据库上的聚类实验结果  

<html><body><table><tr><td rowspan="2">k</td><td colspan="8">accuracy/%</td><td colspan="2">normalized mutual information/%</td><td colspan="3"></td></tr><tr><td>CF</td><td>LCCF</td><td></td><td>MCF</td><td>GMCF</td><td>GCF</td><td>DGMCF</td><td>CF</td><td>LCCF</td><td>MCF</td><td>GMCF</td><td>GCF</td><td>DGMCF</td></tr><tr><td>2</td><td>89.72</td><td>90.74</td><td>91.25</td><td>91.86</td><td>92.48</td><td>95.06</td><td>71.13</td><td>74.51</td><td>74.89</td><td>76.47</td><td>80.40</td><td></td><td>84.28</td></tr><tr><td>3</td><td>79.34</td><td>84.22</td><td>85.03</td><td>86.12</td><td>85.36</td><td>90.31</td><td>63.21</td><td>68.69</td><td></td><td>73.02</td><td>75.23</td><td>76.35</td><td>80.45</td></tr><tr><td>4</td><td>73.04</td><td>78.14</td><td>79.34</td><td>80.28</td><td>82.69</td><td>87.43</td><td>66.38</td><td></td><td>70.63</td><td>72.16</td><td>74.26</td><td>77.43</td><td>81.26</td></tr><tr><td>5</td><td>71.33</td><td>74.46</td><td>74. 12</td><td>78.32</td><td>79.23</td><td>83.37</td><td>67.67</td><td></td><td>72.22</td><td>70.31</td><td>72.65</td><td>78.56</td><td>82.43</td></tr><tr><td>6</td><td>75.21</td><td>79.59</td><td>78.75</td><td>80.56</td><td>82.90</td><td>84.52</td><td></td><td>65.33</td><td>68.81</td><td>68.63</td><td>70.24</td><td>74.89</td><td>78.37</td></tr><tr><td>7</td><td>63.85</td><td>70.08</td><td>74.57</td><td>75.27</td><td>73.62</td><td>76.87</td><td></td><td>66.67</td><td>70.57</td><td>69.89</td><td>71.32</td><td>75.31</td><td>79.29</td></tr><tr><td>8</td><td>64.64</td><td>71. 64</td><td>72.55</td><td>73.24</td><td>75.51</td><td>78.48</td><td></td><td>67.28</td><td>70.67</td><td>71.96</td><td>72.35</td><td>76.45</td><td>80.77</td></tr><tr><td>9</td><td>62.86</td><td>67.87</td><td>69.13</td><td>71.30</td><td>70.02</td><td>73.29</td><td></td><td>66.40</td><td>69.86</td><td>70.21</td><td>71.51</td><td>72.71</td><td>77.32</td></tr><tr><td>10</td><td>62.15</td><td>65.71</td><td>66.69</td><td>67.37</td><td>68.44</td><td>71. 16</td><td></td><td>66.27</td><td>68.69</td><td>69.28</td><td>70.38</td><td>70.63</td><td>74.76</td></tr><tr><td>Avg.</td><td>71.35</td><td>75.83</td><td>76.83</td><td>78.26</td><td>78.92</td><td></td><td>82.28</td><td>66.70</td><td>70.52</td><td>71. 15</td><td>72. 71</td><td>75.86</td><td>79.88</td></tr></table></body></html>

# 3.2参数选择

DGMCF算法主要有四个参数：构造对偶图时所需近邻点数 $p$ 、两个正则化参数 $\alpha$ 和 $\beta$ 及分解的层数 $L$ 。对于分解的层数 $L$ 的讨论，在文献[17]中已经给出了详细的讨论。为简便起见，设定 $\alpha = \beta$ 。下面讨论DGMCF 算法关于参数的稳定性，即给出算法参数设定值与算法的聚类准确率(accuracy)之间的变化情况。当讨论正则化参数 $\alpha$ 时，设定所选择的近邻点数 $p = 5 .$ 类似地，讨论 $p$ 时，设定正则化参数 $\alpha = 1 0 0$ 。为了同时能与LCCF、GMCF和GCF算法进行比较，实验中也设定LCCF、GMCF和GCF算法中的图正则参数与近邻点数与本文取相同数值。分别在文本数据库TDT2和图像数据库PIE、COIL20中进行了比较实验，同时CF、MCF算法作为参考数值也一并给出，如图1、2所示。

![](images/2d848e0f1691f474ed8b1d30de0c6cf0d6cac85f9d1ef33ec683a9c41a3fd520.jpg)

![](images/fa44378e757b6c00ac04458dd2028a1b03e78cf66385c5ab48df9a2bc080547c.jpg)  
图1各种算法的聚类准确率随正则化参数( $\alpha = \beta$ )改变的变化情况

![](images/f14020e8ae49a18c446c73443437bda2e5921a87e7d323c7fcde63bdd88843a6.jpg)  
图2各种算法的聚类准确率随构建图边数( $p$ )改变的变化情况

由图1、2所示的结果，可以得到如下的结论：

a)提出的DGMCF 算法对于两个正则参数来讲是非常稳定的。当两个正则化参数取值在 $1 \sim 1 0 0 0$ 时，算法能够取得不错的聚类效果。同时DHCF算法本身所得的结果要优于其他算法。

b)提出的DGMCF算法的聚类准确率随着最近邻数取值过大而降低，这是由于过大的最近邻数生成的图不再能准确地反映样本间固有的几何结构。

# 4 结束语

本文提出了一种基于对偶图正则化的多层概念分解算法，利用多层分解思想，在每一层同时利用数据流形和特征流形的几何结构信息，进一步挖掘出表征数据最本质的特征。本文还给出了DGMCF算法的目标函数及迭代更新公式，并给出了算法的收敛性证明。大量的实验结果表明提出的算法比已有相关算法在数据表示方面的性能更好。

# 参考文献：

[1]Yi Yugen, Shi Yanjiao,Zhang Huijie,et al. Label propagation based semisupervised nonnegative matrix factorization for feature extraction [J]. Neurocomputing,2015,149:1021-1037.   
[2]王萌萌，左万利，王英，等．一种基于加权非负矩阵分解的多维用户人 格特质识别算法 [J].计算机学报,2016,39(12):2562-2577.   
[3]贺超波，汤庸，杨阿桃，等．基于分布式非负矩阵分解的大规模主题社 区挖掘[J].中国科学：信息科学,2016,46(6):714-728.   
[4]Lee D D, Seung H S.Learning the parts of objects by non-negative matrix factorization [J]. Nature,1999,401: 788-791.   
[5]Xu Wei, Gong Yihong.Document clustering by concept factorization [C]// Proc of International Conference on Research and Development in Information Retrieval.2004: 202-209.   
[6]Liu Haifeng,Wu Zhaohui,Li Xuelong et al. Constrained nonnegative matrix factorization for image representation [J]. IEEE Trans on Pattern Analysis and Machine Intelligence,2012,34(7):1299-1311.   
[7]Liu Haifeng,Yang Genmao,Wu Zhaohui,et al.Constrained concept factorization for image representation [J].IEEE Trans on Cybernetics,2014, 44 (7): 1214-1224.   
[8]TenenbaumJB,Silva VD,Langford JC.A global geometric framework for nonlinear dimensionality reduction [J]. Science,2000,290 (550o): 2319- 2323.   
[9]Roweis S T, Saul LK.Nonlinear dimensionality reduction by locally linear embedding [J]. Science,2000,290 (5500): 2323-2326.   
[10]Belkin M,Niyogi P. Laplacian eigenmaps and spectral techniques for embedding and clustering [C]// Advances in Neural Information Processing Systems.2002: 585-591.   
[11] Guan Naiyang,Tao Dacheng,Luo Zhigang,et al. Manifold regularized discriminative nonnegative matrix factorization with fast gradient descent [J].IEEE Trans on Image Processing,2011,20(7): 2030-2048.   
[12] Cai Deng,He Xiaofei,Han Jiawei,et al. Graph regularized nonnegative matrix factorization for data representation [J].IEEE Trans on Pattern Analysis and Machine Intelligence,2011,33(8):1548-1560.   
[13] Cai Deng,He Xiaofei, Han Jiawei. Locally consistent concept factorization for document clustering [J].IEEE Trans on Knowledge and Data Engineering,2011,23(6): 902-913.   
[14] Cichocki A, Zdunek R.Multilayer NMF using projected gradient approaches [J]. Intermational Journal of Neural Systems,2007,17(6): 431-446.   
[15] Rajabi R, Ghassemian H. Spectral unmixing ofhyperspectral imagery using multilayer NMF [J].IEEE Geoscience and Remote Sensing Letters,2015, 12 (1): 38-42.   
[16]Li Xue,Zhao C,Shu Z,et al. Multilayer concept factorization for data representation [C]// Proc of the 10th International Computer Science & Education.2015: 486-491.   
[17] Li Xue,Shen Xiaobo,Shu Zhenqiu,et al. Graph regularized multilayer concept factorization for data representation [J].Neurocomputing,2017, 238:139-151.   
[18] Shang Fanhua,Jiao Lichen,Wang Fei.Graph dual regularization nonnegative matrix factorization for co-clustering [J]. Pattern Recognition, 2012,45 (6): 2237-2250.   
[19] Ye Jun,Jin Zhong.Dual-graph regularized concept factorization for clustering [J].Neurocomputing,2014,138(3),120-130.