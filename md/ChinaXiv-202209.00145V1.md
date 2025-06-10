# 基于图模型的高光谱图像分类算法

黄怛鑫，蒋俊正

(桂林电子科技大学信息与通信学院，广西桂林541004)

摘要：高光谱图像（Hyper Spectral Image，HSI)分类是 HSI处理中的重要预处理手段,其目标是对 HSI数据中每个像素点进行类别标记,标记结果常用于识别、勘探等应用。针对 HSI分类任务中存在的数据量大、数据维度高、已知样本量少等难点,提出一种基于图模型的半监督分类算法。该算法将 HSI数据建立为图以实现降维，而后将分类问题归结为一个无约束的优化问题。由于在求解优化问题时涉及到矩阵求逆，数据规模大时计算复杂度会变高。为了避免大规模的矩阵求逆，采用拟牛顿法进行求解,通过对 Hessian 矩阵进行分解,对计算步长时涉及到的求逆操作进行近似，且该算法能够分布式实现。仿真实验表明,与现有算法相比，本算法在大规模且类别多的 HSI分类任务下计算复杂度较低，能完成较高精度的分类。

关键词：高光谱图像;半监督学习；分布式算法；无约束优化；大规模问题中图分类号：TP391.4;TP322+.3 文献标志码： 文章编号：A

# Graph base hyperspectral images classification algorithm

HUANG Daxin， JIANG Junzheng

(Schoolof Information and Communication，Guilin University of Electronic Technology，Guilin 541O04，China)

Abstract:Classification thatasigns labelfor pixel in HSIdatasetisanimportant preprocessed method in hyperspectral imAge（HSD） processing，label information is useful forappication such as recognition and exploration.Agraph based semisupervisedclasification method is proposedtotackleproblemsoflargedata volume，highdata dimension，andsmall known BamplesizeinHSIclassificationtask.Dataset was modeledwith graph fordimensionalreducing，thenthetaskisformulated Sanunconstrained optimization problem inthis method.Matrix inverse is inevitable for solving such problem，and complexity would increase with largescale.Inorder toavoid large scale matrix inversion,aquasi-Newton method whichapproximates inversion operationaccording todecompositionof Hessianmatrixisused，such methodcanbeimplemented indistributed manner. Simulations demonstrate that，compared with existing methods，proposed algorithm has lower complexityand higher accuracy in large scale and multi-class HSI classification task.

Key words:hyperspectral images；semi-supervised learning；distributed algorithm；unconstrained optimization；large scale problem

高光谱图像(hyper spectral image,简称HSI)最先应用在卫星遥感技术上，现已在军事、医学、地质、农业等领域得到广泛的应用[1-5]。成像仪对待测目标进行多窄波成像，而后把成像结果进行组合，得到一个多频带的数据块，该数据块即为HSI。在HSI的成像过程中，同一物质在接收到不同波长的电磁波时，会因内部材料结构等因素的影响而呈现出不同的反射效果，相比于普通图像只包含空间信息，HSI的成像特点使其携带了更多的频谱信息。对HSI数据的研究较为广泛，有端元提取[6]、端元解混[7-8]、分类[9等，其中分类是最为基础的研究内容。分类的目的是对HSI数据中每个像素点进行类别标记，所得结果对HSI待测目标的识别与监测等任务而言有很大的参考价值[10]

HSI分类问题可使用监督学习[11-12]算法求解。这类算法在分类时需使用大量已标记数据，然而在实际情况中，几乎没有原始数据是已标记数据，而对原始数据进行标记需要消耗大量的人力与物力。因此，能有效利用少量已标记数据与海量无标记数据进行分类任务的半监督学习算法就受到了许多关注[13」而在分类问题中，维度过高的特征会引起“休斯现象”、“维数灾难"等问题，进而影响分类结果[14」。图半监督学习先使用图模型对数据进行降维，接着进行问题建模并优化出分类结果，其中比较具有代表性的有最小割算法[15]、局部全局一致算法[16]与高斯域与调和函数算法[17]。这些算法均为直推式学习算法[13],相比于推导式学习算法在优化过程中优化的是分类器的参数[13]，直推式学习算法目标函数的优化直接计算出分类结果,因此图半监督学习算法在计算速度上有一定有优势。经过十几年的发展，图半监督学习具有坚实的理论支撑，且在不同的应用背景下的实用性都得到了验证[18-19]

9 在数据规模较大时，图半监督学习算法的计算复杂度也随之提升，针对此问题，提出一种分类算法，从分解优化问题出发，在保证原有的分类精度情况下降低求解所需的时间，且该算法可以分布式实现。在该算法中，用一种较为简单的方式近似计算目标函数Hessian矩阵的逆，然后通过迭代求出优化问题的解。仿真实验表明，与现有的图半监督学习算法相比，该算法能在较短时间内获得较好的分类结果。

# 1基础知识

# 1. 1 高光谱图像简介

与人眼的成像系统类似，传统成像仪内部感光元器件只能感应到可见光频段 $( 3 6 0 \sim 8 3 0 ~ \mathrm { n m } )$ 内的电磁波，且成像时只能进行单宽波段成像，因此对成像结果的直观感受是即一张尺寸为 $\mathbf { \Psi } _ { m }$ 像素 $\times n$ 像素（以下简写为 $m \times n$ ）的彩色图像。而由于可见光频段上的电磁波均可以由红绿蓝(RGB)三色光组合表示而成，因此传统图像也被称为RGB图像，并在处理时通常使用对应RGB三个颜色分量的三张灰度图对其进行表示，此时成像结果即为一个数据块，由3张尺寸为 $m \times n$ 的图片重叠而成[2]。RGB图像低频率分辨率的成像特点，使得相关研究极度依赖图像内包含的空间信息。因此对于RGB图像而言，空间分辨率是最为重要的特性。相比于RGB图像成像仪，HSI成像仪所能感应到的电磁波频段更为宽广，覆盖范围通常为紫外波段到近红外波段。此外，HSI成像仪另一重要特性就是能进行多窄波段成像，即成像仪在成像过程中，把待测物体反射回的电磁波切分成多个波段，接着使用每个波段的电磁波进行成像，最后将多个成像结果合成为数据块。这样的成像方式使得HSI以尺寸为 $m \times n \times d$ 的数据块形式呈现，其中， $m \times n$ 是成像仪对单个波段响应的成像结果尺寸， $d$ 则是成像时切分的波段数，同一个像素点在 $d$ 个频率上的不同响应构成像素点的频率特性，频谱特性示意图如图1所示。成像的特性不同，使得HSI相比RGB图像拥有更为丰富的频谱信息与更为精细的频率分辨率。正因如此，大多数对HSI数据的研究主要从其频率信息出发。

![](images/922ccf040ac3112114127d460a1ecc1d289dac97f25d70dd809b7ac3904b84b3.jpg)  
图1高光谱图像频率特性

# 1.2分类问题与建模

在HSI各项研究中，分类是较为重要的研究内容。其根据HSI数据的频率信息，对每个像素点进行类别标记。如前所述，HSI表示为一个尺寸为 $m \times$ $n \times d$ 的数据块，该数据块由 $d$ 张对应不同波段的图片组成。由于 $d$ 张图片都是对同一个目标进行成像，不同图片上的相同位置像素点的值实际上就是该点对于不同频率电磁波的响应，而 $d$ 个响应就构成该像素点所对应物体的光谱特性。在HSI分类问题中，光谱特性是分类时的一个重要参考。光谱特性在引入更多信息的同时，也带来了特征的的维数问题，而过高维度会导致分类精度下降。因此先使用图建模算法对其进行降维，接着建立优化问题，进而求解得出分类结果。图是一种常见的数据结构，目前已在无线传感器网络、社交网等场合中得到应用[20]。图由节点与边组成，通常表示为 $G = \left\{ V , E , W \right\} , V$ 与 $E$ 分别为图的节点集与边集， $W$ 为图的权矩阵，权矩阵内为图上权重值。节点之间通过边相连接，边描述节点间的邻接关系与相似关系，边上权重即为权矩阵中的元素，两节点越相似，二者之间的权重值越大。此外,还常用拉普拉斯矩阵 $\pmb { L } = \pmb { D } - \pmb { W }$ 、归一化图拉普拉斯矩阵 $\pmb { L } _ { n } = \pmb { D } ^ { - 1 / 2 } \pmb { L } \pmb { D } ^ { - 1 / 2 }$ 来表示图的相关特性，其中 $\textbf {  { D } }$ 为度矩阵，其定义为

$$
D _ { i i } = \sum _ { j \in \mathscr { N } _ { i } } W _ { i j } ,
$$

其中 $\overline { { \mathcal { N } } } _ { i }$ 为节点 $i$ 的邻居集合。

一个像素点数为 $N$ ，频段数为 $d$ 的HSI数据通常用特征矩阵

$$
{ \pmb X } = [ { \pmb x } _ { 1 } , { \pmb x } _ { 2 } , \dots , { \pmb x } _ { N } ] \in { \bf R } ^ { N \times d }
$$

表示，矩阵中的每一行为对应像素点的频谱特征。根据该特征矩阵，用图对HSI数据进行建模，所建模图使用 $k$ 近邻图( $\mathrm { k N N }$ 图)。在建模时，首先计算第一个节点与余下所有节点的欧式距离(这一距离由频谱特征确定)，接着选择最相近的 $k$ 个节点作为邻居并与之相连，而后重复这2个步骤直到所有的节点都与其最近的 $k$ 个邻居相连，再用每个节点与其的距离计算出权重值：

$$
W _ { i j } = \Bigg \{ \mathrm { e } ^ { - \frac { \| \boldsymbol { x } _ { i } - \boldsymbol { x } _ { j } \| _ { 2 } ^ { 2 } } { \sigma } } , i \in \overline { { \mathcal { N } } } _ { i } ,
$$

该值用于描述边所连接的节点的相似程度,其中， $\mathbf { \boldsymbol { x } } _ { i }$ ${ \in } \mathbf { \bar { B } } ^ { 1 \times d }$ 与 $\boldsymbol { x } _ { j } \in \mathbb { R } ^ { 1 \times d }$ 分别为第 $i$ 个与第 $j$ 个像素点的频谱特征。通过以上步骤，便得到一个 $k \mathrm { N N }$ 图 $G$ 。像素点上的标签用 $\mathbf { y } = [ \mathbf { y } _ { l } ; \mathbf { y } _ { u } ]$ 表示， $\mathbf { y } _ { \iota }$ 代表已知标$\underline { { \tilde { x } } } \underline { { \tilde { \mathbf { \omega } } } } , \mathbf { \tilde { y } } _ { u }$ 代表未知标签，值为0。在实际的分类问题中 $\bar { \mathbf { y } } _ { l } \ll \mathbf { y } _ { u }$ 。在图半监督分类问题中,根据已知部分标签 $\mathbf { y } _ { \iota }$ 与所建模图刻画的数据特性学习出 $\textbf { y } _ { u }$ 的标签，完成分类。

# 2分类问题求解

根据所建立的图模型 $G = \left\{ V , E , W \right\}$ ，关于HSI的 $\mathbf { \Psi } _ { c }$ 分类问题可归结为

$$
\sum _ { j = 1 } ^ { c } \operatorname* { m i n } _ { { \bf f } _ { j } } ( { \bf f } _ { j } ) = \frac { \alpha } { 2 } \| { \bf f } _ { j } - { \bf y } _ { j } \| _ { 2 } ^ { 2 } + \frac { 1 } { 2 } { \bf f } _ { j } ^ { \intercal } { \bf L } _ { n } { \bf f } _ { j } ,
$$

其中， $\boldsymbol { y } _ { j }$ 为标签 one-hot 编码矩阵 $\boldsymbol { Y }$ 的第 $j$ 列，表示第 $j$ 类标签在数据中的分布情况。 $\boldsymbol { Y }$ 的定义为

$$
\begin{array} { r } { Y _ { i j } = \binom { 1 , f _ { i } = j , } { 0 , \sharp _ { \star } / \sharp _ { i } / \sharp _ { \star } } } \end{array}
$$

$\scriptstyle { { \cal L } } _ { n }$ 为图 $G$ 的归一化拉普拉斯矩阵。优化问题可以理解为学习出一个比较符合所建模图的标签one-hot编码矩阵 $F$ 。得到 $F$ 后，通过下式来取得最终的分类结果。

$$
\operatorname* { m a x } _ { j \in 1 , 2 , \ldots } { F _ { i , j \circ } } ( 
$$

不难看出，图半监督学习的主要任务是在对 $F$ ，即$f _ { \scriptscriptstyle 1 } , f _ { \scriptscriptstyle 2 } , \cdots , f _ { \scriptscriptstyle c }$ 的求解上。 $\boldsymbol { c }$ 个向量 $f _ { \scriptscriptstyle 1 } , f _ { \scriptscriptstyle 2 } , \cdots , f _ { c }$ 的求解过程相同，因此对仅对任一 $\boldsymbol { f } _ { j }$ 的求解进行分析，令$\pmb { f } = \pmb { f } _ { j }$ ，

$$
\operatorname* { m i n } _ { f } \varphi ( f ) : = { \frac { \alpha } { 2 } } \| f - \mathbf { y } \| _ { 2 } ^ { 2 } + { \frac { 1 } { 2 } } f ^ { \operatorname { T } } \mathbf { L } _ { n } f \circ
$$

显然，目标函数是一个关于 $f$ 的凸函数，且有解析解，解为 $\pmb { f } ^ { * } = ( \pmb { I } + \alpha ^ { - 1 } \pmb { L } _ { n } ) ^ { - 1 } \mathbf { y }$ 。但在数据规模变大时，集中式求解矩阵的逆会变得困难。

# 2.1 优化求解

式(6)可用牛顿法来求解。其一阶与二阶梯度信息分别为

$$
\scriptstyle { \left\{ \begin{array} { l l } { \nabla \varphi ( { \pmb f } ) = \alpha ( { \pmb f } - { \pmb y } ) + { \pmb L } _ { n } { \pmb f } , } \\ { \nabla ^ { 2 } \varphi ( { \pmb f } ) = \alpha { \pmb I } + { \pmb L } _ { n } \circ } \end{array} \right. }
$$

即目标函数的Hessian矩阵 $\pmb { H }$ 为 $\alpha { \pm } L _ { n }$ 。在牛顿法求解过程中，需要在每步迭代中计算Hessian矩阵的逆以求出步长 $\boldsymbol { s } ^ { k } = \boldsymbol { H } ^ { - 1 } \boldsymbol { \nabla } \varphi ( \boldsymbol { f } ^ { k } )$ ，而这在矩阵规模较大的情况下会相当耗时，在此提出一种近似牛顿法。

对于图归一化拉普拉斯 $L _ { n }$ ，有 $\pmb { L } _ { n } = \pmb { I } - \pmb { W } _ { n } , \pmb { W } _ { n }$ 为图的归一化权矩阵，其可以进一步分解为2个部分，对角部分 $W _ { n d }$ 与非对角部分 $\boldsymbol { W } _ { n u }$ ，其中 $W _ { n d } =$ $\operatorname { d i a g } ( \boldsymbol { W } _ { n } )$ ，且 $W _ { n } = W _ { n d } + W _ { n u }$ 。基于此，同样可将Hessian矩阵 $H$ 分割为对角部分与非对角部分，即

$$
\scriptstyle H = A - B ,
$$

其中：

$$
\left\{ \begin{array} { c } { { \pmb { \alpha } = \pmb { \alpha } \pmb { I } + \left( 1 + \theta \right) \left( { \pmb { I } } - { \pmb { W } } _ { n d } \right) , } } \\ { { \pmb { B } = \pmb { W } _ { n u } + \theta \left( { \pmb { I } } - { \pmb { W } } _ { n d } \right) \circ \pmb { I } } } \end{array} \right.
$$

其中， $\theta \geqslant 0$ 为控制矩阵分解的参数，设置为1。此外，所建模的图都不带自环，因此其归一化权矩阵的对角部分均为0，即 ${ \pmb W } _ { n d } = { \pmb 0 }$ 。基于此，取 $\theta = 1$ 时，式(10)可进一步更新为

$$
\begin{array} { r } { \left. \overset { \pmb { A } } { \operatorname { \vert { \cal { A } } } } = ( 2 + \alpha ) \pmb { I } , \right. } \\ { \left. \left. \overset { \pmb { B } } { \operatorname { \vert { \cal { B } } } } = \pmb { W } _ { n u } + \pmb { I } _ { \circ } \right. \right. } \end{array}
$$

此时，式中目标函数在第 $k$ 次迭代中时的牛顿步长为$s ^ { k } = - ( { \pmb A } - { \pmb B } ) ^ { - 1 } \nabla \varphi ( { \pmb f } ^ { k } )$ 。根据文献[21],可用

$$
\begin{array} { r } { s ^ { k } = - ( { \pmb I } - Q { \pmb B } ) { \pmb A } ^ { - 1 } \nabla \varphi ( { \pmb f } ^ { k } ) , } \end{array}
$$

对其进行近似。由文献[21」， $\varrho$ 与Hessian矩阵的逆等效，并可以通过泰勒公式对其进行近似，令 $\pmb { P } =$ $W _ { n } - \alpha \pmb { I }$ ：

$$
\pmb { Q } = ( \pmb { I } - \pmb { P } ) ^ { - 1 } \approx \pmb { I } + \pmb { P } ,
$$

式(12)中 $A$ 为对角矩阵，因此无需进行矩阵求逆即可计算出步长，进而降低了计算复杂度。迭代过程为

$$
\begin{array} { r l } & { \left( { { e ^ { k } } = A ^ { - 1 } \nabla \varphi ( { f ^ { k } } ) , } \right. } \\ & { \left. { \vphantom { { e ^ { k } } = A ^ { - 1 } \nabla \varphi ( { f ^ { k } } ) , } } \right) { u ^ { k } } = B { e ^ { k } } , } \\ & { \left. { \vphantom { { e ^ { k } } = A ^ { k } \nabla ^ { \varphi } ( { f ^ { k } } ) \cdot } } \right. } \\ & { \left. { \vphantom { { e ^ { k } } = A ^ { k } \nabla ^ { \varphi } ( { f ^ { k } } ) \cdot } } \right. } \\ & { \left. { \vphantom { { e ^ { k } } = A ^ { k } \nabla ^ { \varphi } ( { f ^ { k } } ) \cdot } } \right. } \end{array}
$$

# 2.2分布式求解

因所建图是 $k \mathrm { N N }$ 图，基于图的局部特性，上一小节提出的求解思路可以使用分布式的方式来实现。在分布式计算中，优化问题被分解为多个子问题并分配到计算节点上，此时复杂度较大的优化问题转换为多个复杂度较低的小问题。分布式计算可以充分有效地利用计算资源，且很好地降低计算复杂度。分布式算法中，计算节点除计算能力外，还具有一定的通信与存储能力，且每个节点都已经存储了图节点的邻居信息与已知标签信息。计算节点可以存储多个图节点信息，在此我们假设一个计算节点仅存储一个图节点,此时,式(6)转换为

$$
\underset { f } { \operatorname* { m i n } } \varphi ( f ) : = \frac { \alpha } { 2 } \sum _ { i = 1 } ^ { N } ( f _ { i } - y _ { i } ) ^ { 2 } + \frac { 1 } { 2 } { \mathbf { \mathit { f } } ^ { \mathrm { T } } } \mathbf { \mathit { L } } _ { n } { \mathbf { \mathit { f } } } ,
$$

其中， $f _ { j } \ 、 y _ { j }$ 分别为 $f , \mathbf { y }$ 在图中第 $j$ 个节点上的值。显然，式(15)的前半部分即为式中匹配项的分解，将匹配项分解为 $N$ 个相互独立的部分并分配到每个节点上。分解后,节点i上的一阶梯度信息为

$$
\triangledown \varphi ( f _ { i } ) = \alpha ( f _ { i } - y _ { i } ) + f _ { i } - \sum _ { j \in \overline { { \mathcal { N } } } } w _ { i j } f _ { j } ,
$$

其 ${ \mathscr W } _ { i j }$ 为 $W _ { n }$ 中第 $i$ 行 $j$ 列的元素,在图上则对应节点i与节点 $j$ 之间的权重值。由此,节点 $i$ 上进行的第k次迭代则为

$$
\left\{ \begin{array} { l l } { \displaystyle e _ { i } ^ { i } = A _ { i i } ^ { - 1 } \nabla \varphi ( f _ { i } ^ { k } ) , } \\ { \displaystyle u _ { i } ^ { k } = e _ { i } ^ { k } + \sum _ { j = \overline { { \boldsymbol { \nu } } } } e _ { j } ^ { k } , } \\ { \displaystyle s _ { i } ^ { k } = - e _ { i } ^ { k } + ( 1 - \alpha ) u _ { i } ^ { k } + \sum _ { j \in \overline { { \mathcal { N } } } _ { i j } } w _ { i j } u _ { j } ^ { k } , } \\ { \displaystyle f _ { i } ^ { k + 1 } = f _ { i } ^ { k } + s _ { i } ^ { k } \circ } \end{array} \right.
$$

在迭代完成后，所有的节点输出的 $\boldsymbol { \mathscr { f } } _ { i }$ 便可组合为one-hot编码矩阵 $F$ 的对应列。通过(16)与(17)可看出，节点 $\mathbf { \chi } _ { i }$ 在迭代过程中仅需获得其周边邻居上$f , e$ 以及 $\textbf { \em u }$ 的值即可计算即可完成迭代。对于节点$i$ ，分布式算法如下：

$$
{ \bf { y } } = { \bf { Y } } _ { : , j } , \quad k = 0 , \quad { \bf { f } } ^ { \intercal } = { \pmb { \theta } } , \quad { \pmb { f } } ^ { \prime } = { \pmb { I } }
$$

1)与 $\overline { { \mathcal { N } } } _ { i }$ 中的节点进行通信，获取 $f$ 在 $\overline { { \mathcal { N } } } _ { i }$ 上的值；2)计算 $e _ { i } ^ { k } = A _ { i i } ^ { - 1 } \nabla \varphi ( f _ { i } ^ { k } )$

3)与 $\overline { { \mathcal { N } } } _ { i }$ 中的节点进行通信，获取 $\scriptstyle { \boldsymbol { e } }$ 在 $\overline { { \mathcal { N } } } _ { i }$ 上的值  
4)计算

$$
u _ { i } ^ { k } = e _ { i } ^ { k } + \sum _ { j \in \mathcal { T } _ { i } } e _ { j } ^ { k } ;
$$

5)与 $\overline { { \mathcal { N } } } _ { i }$ 中的节点进行通信，获取 $\textbf { \em u }$ 在 $\overline { { \mathcal { N } } } _ { i }$ 的值;6)计算步长，  
$s _ { i } ^ { k } = - e _ { i } ^ { k } + ( 1 - \alpha ) u _ { i } ^ { k } + \sum _ { j \in \mathcal { N } _ { i } } w _ { i j } u _ { j } ^ { k } \ : ;$ （20  
7)计算 $f _ { i } ^ { k + 1 } = f _ { i } ^ { k } + s _ { i } ^ { k }$ ;  
endwhile  
令 $F _ { i j } = f _ { i }$ ;  
end while  
通过 $\operatorname* { m a x } _ { j \in 1 , 2 , \cdots , c } F _ { i j }$ 求得节点 $i$ 的分类结果 $\hat { y } _ { i }$ 。最终总合所有节点的分类结果输出 $\hat { \mathbf { y } }$ 。  
对算法过程分析可知，每个节点在一次迭代过程

中需要与周边邻居节点进行3次通信。

# 3仿真结果与分析

对KennedySpaceCenter（KSC）与Indian Pines数据集22 进行分类仿真。KSC数据内有202个波段图片，可分为13类，类别分布不平均。IndianPines内保留了200个波段数据，图片内像素分为16类，其类别分布更不平均，各类样本数目差距更大。

仿真时，设置单样本已知个数分别为5、10、15以及20,IndianPines的第7与第9类的已知数据最多为10个，且每种设置下均随机生成30组待学习数据，最后将30组数据的学习结果取平均作为最终结果。参数的设置如表1所示。为了更好衡量分类效果，仿真使用总体精度（OA）、平均精度（AA)以及Kappa系数三者的平均值作为评价指标。

表1参数设置  

<html><body><table><tr><td>参数名称</td><td>取值</td></tr><tr><td>邻居数k</td><td>5</td></tr><tr><td>高斯核标准差o</td><td>0.1</td></tr><tr><td>匹配项权重τ</td><td>0.5</td></tr></table></body></html>

图2、3分别为不同算法在不同数据下的OA曲线图。从图2可看出，在KSC数据中，本算法的分类效果与文献[19]算法大致相同，高于文献［20]中算法。从图3可看出，在IndianPines数据中，本算法结果与文献19中算法一致，且明显优于文献[20算法的结果。

表2与表3分别为在各类已知样本数量为15个的情况下，各算法在不同数据下的运行时间和各项分类评估参数。由于在不同已知样本数下的结果分布一致，仅选取数量为15 的仿真结果作展示。由表2可看出，在KSC数据中，本算法比文献19算法所用时间大大减少，虽然耗时高于文献[20]算法，但本算法各项评估参数都表明分类效果要更好。而表2中表明，在IndianPines 数据中，本算法的分类效果远超文献[20]，且所消耗的计算时间与文献［20]几乎一致。文献19算法基于各类样本分布均衡，且类别数目较少的前提，因此会在IndianPines数据中出现分类效果恶化的情况。

![](images/28ded602cd40f1a7a27fe7f8aba48e5c939ae01b058a7a8a53da5a0595acaa94.jpg)  
图2KSC数据下不同算法OA曲线

![](images/779d5ac5711128e4835fd090fb38fc58b2a34c0cb7fe5974474a7337d6b7ca8f.jpg)  
图3IndianPines 数据下不同算法OA曲线

表2KSC数据仿真结果  

<html><body><table><tr><td>评价指标</td><td>本算法</td><td>文献[19]算法</td><td>文献[20]算法</td></tr><tr><td>运行时间/s</td><td>8.05</td><td>35.08</td><td>1.35</td></tr><tr><td>OA/%</td><td>73.87</td><td>73.87</td><td>54. 74</td></tr><tr><td>AA/%</td><td>71. 13</td><td>71. 13</td><td>52.22</td></tr><tr><td>Kappa</td><td>68.19</td><td>68.19</td><td>48.00</td></tr></table></body></html>

表3Indian数据仿真结果  

<html><body><table><tr><td>评价指标</td><td>本算法</td><td>文献[19]算法</td><td>文献[20]算法</td></tr><tr><td>运行时间/s</td><td>39.10</td><td>242.50</td><td>35.08</td></tr><tr><td>OA/%</td><td>49.7</td><td>49.70</td><td>8.38</td></tr><tr><td>AA/%</td><td>64. 41</td><td>64.41</td><td>25.44</td></tr><tr><td>Kappa</td><td>60.61</td><td>60.61</td><td>22.36</td></tr></table></body></html>

图4、5分别为本算法在不同数据下分类时的迭代情况。由于在每个类别迭代的趋势一致，任选其中一条做展示。通过2图可发现，本算法在不同数据下均能较快收敛。而由之前算法分析可知，本算法每步的迭代都需要与邻居进行3次通信以完成信息交换。显然，该算法以单步迭代的多次通信换取了较快的迭代速度。

以上2个数据的仿真结果以及算法的分析可以说明，本算法在数据量较大的情况下更能体现出其优势，更适合数据量较大、类别数目较多的HSI分类任务。

![](images/fd61313411cd2de81121a44ef5a80616f977fa40c5a3b59851d8438f091185ee.jpg)  
图4KSC数据分类迭代曲线

![](images/9e435e622878156741b2569e78161798bb64421a611be9c688db385dbcafeb86.jpg)  
图5Indian数据分类迭代曲线

# 4结束语

针对HSI分类中未标记数据多、数据维度高、计算复杂度高等问题，提出一种基于图模型的分类算法，且该算法可以分布式运行。该算法把分类任务归结为一个无约束的优化问题，首先对优化问题进行拆分，并将拆分后的子优化问题分配到各个节点上，接着使用多计算单元对小优化问题迭代求解。仿真实验表明，本算法在数据规模大、类别多的分类任务下具有较大优势。后续工作将使用图信号处理理论应用到数据建模中，克服其对于样本数目分布不均衡的局限性，使其能更好地处理HSI分类问题。

# 参考文献：

LU G,FEI B. Medical hyperspectral imaging:a review [J].Journal of Biomedical Optics，20l4，19（1）： 010901. KHAN MJ,KHAN H S,YOUSAF A,et al. Modern trends in hyperspectral image analysis:a review[J]. IEEE Access,2018,6:14118-14129. 沈宇，房胜，郑纪业，等.基于高光谱成像技术的富士苹 果轻微机械损伤检测研究[J].山东农业科学，2020,52 (2):144-150. 麻永平，张炜，刘东旭.高光谱侦察技术特点及其对地 面军事目标威胁分析[J].上海航天，2012，29(1)：37-40 $+ 5 9$ ： 李鸿强,孙红,李民赞,等.基于高光谱的马铃薯微型种 薯分类检测高光谱地物识别技术基于高光谱遥感的树 种识别[J].分析测试学报，2020，39(11)：1421-1426. 杨华东，郝永平.结合局部空谱信息的高光谱图像多端 元提取[J].沈阳理工大学学报,2020,39(2)：7-12. 贾麒，廖守亿，张作宇，等.重加权稀疏非负矩阵分解的 高光谱解混[J].红外与激光工程,2020,49(增刊2)：1- 12.   
」刘颖,梁楠楠，李大湘,等.基于光谱距离聚类的高光谱 图像解混算法[J].计算机应用，2019，39（9)：2541- 2546.   
]WAN S,GONG C,ZHONG P,et al. Hyperspectral image classification with context-aware dynamic graph convolutional network_J.IEEE Transactions on Geoscience and Remote Sensing,2020,59(1):597-612.   
』赵春晖，王立国，齐滨.高光谱遥感图像处理算法及应 用[M.上海：电子工业出版社，2016：114-116.   
]DUNJKO V,BRIEGEL H J.Machine learning $\&$ artificial intelligence in the quantum domain:a review of recent progress [J]. Reports on Progress in Physics, 2018,81(7) :074001.   
[12]LIAKOS K G,BUSATO P,MOSHOU D,et al. Machine learning in agriculture:a review[J]. Sensors, 2018,18(8) :2674.   
[13]刘建伟,刘媛,罗雄麟.半监督学习算法[J].计算机学 报,2015,38(8):1592-1617.   
[14]周志华.机器学习[M].北京:清华大学出版社,2016:2- 6.   
[15][15] BLUM A,CHAWLA S. Learning from labeled and unlabeled data using graph mincuts[C]//Proceedings of the ICML,2001.   
[16][16] ZHOU D,BOUSQUET O,LAL T,et al. Learning with local and global consistency[J]. Advances in Neural Information Processing Systems,2Oo3,16(16): 321-328.   
[17][17] ZHU X,GHAHRAMANI Z,LAFFERTY JD. Semi-supervised learning using gaussian fields and harmonic functions[C]//Proceedings of the 2Oth International Conference on Machine Learning,2Oo3:912-919.   
[18]刘锦文,许静,张利萍,等.基于标签传播和主动学习的 人物社会关系抽取[J].计算机工程,2017,43（2)：234- 240.   
[19]CHEN J,JI D,TAN C L,et al. Relation extraction using label propagation based semi-supervised learning [C]//Proceedings of the Proceedings of the 21st International Conference on Computational Linguistics and 44th Annual Meeting of the Association for Computational Linguistics,2006:129-136.   
[20]SANDRYHAILA A，MOURA J M. Discrete signal processing on graphs[J]. IEEE Transactions on Signal Processing,2013,61(7):1644-1656.   
[21]KREJIC N,LUZANIN Z. Newton-like method with modification of the right-hand-side vector[J].Mathematics of Computation,2002,71(237) :237-250.   
[22]BAJOVIC D,JAKOVETIC D,KREJIC N et al. Newton-like method with diagonal correction for distributed optimization[J]. SIAM Journal on Optimization,2017, 27(2):1171-1203.   
[23]SHAO Y,SANG N,GAO C,et al. Probabilistic class structure regularized sparse representation graph for semi-supervised hyperspectral image classification[J]. Pattern Recognition,2017,63:102-114.

编辑：张所滨