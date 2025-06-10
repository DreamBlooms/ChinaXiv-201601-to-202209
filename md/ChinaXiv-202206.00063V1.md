# 基于特征分解的快速位姿图优化算法

李雨洁‘，魏国亮ʰ，蔡洁‘，王苗苗a(上海理工大学a.理学院;b.管理学院，上海 200093)

摘要：位姿图优化(pose graph optimization，PGO)是计算机视觉领域中广泛应用的高维非凸优化算法，很难直接求解，主要依赖于迭代技术，对初始值的质量要求较高，在实践中很难得到保证。针对位姿图优化问题进行了研究，提出了基于特征分解的位姿图简单封闭解算法，该算法首先对 PGO 问题的最大似然估计进行半定松弛，然后将其转换为特征分解问题，并利用数据的稀疏性设计了改进的模型降阶方法进行求解，进一步提高了算法的计算速度。算法具有可伸缩性、计算成本低和精度高等优点。最后，在模拟和真实的位姿图数据集上进行实验评估，结果表明在不影响精度的情况下，该算法可以快速地进行位姿图优化。

关键词：位姿图优化；最大似然估计；特征分解；模型降阶 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2022.02.0122

Fast pose optimization algorithm based on eigen decomposition

Li Yujiea, Wei Guoliangbt, Cai Jiea, Wang Miaomiaoa (a.CollgeofScience,UniversityofShanghaiforScience&Technology,b.BusinessSchool,Universityofhanghaifor Science & Technology,Shanghai 200093,China)

Abstract: Pose graphoptimization (PGO)is a high dimensional non-convex optimization algorithm widelyused in the field ofcomputer vision.Itis hardtosolve directlyand mainlyrelies oniterative techniques.Itrequires high qualityofinitial value which is dificult to be guaranteed in practice.Thispaper studied PGO problemand proposed a simple closed solution algorithm for pose graph based on eigen decomposition.This algorithm first developed thesemidefiniterelaxation of maximum-likelihood estimation(MLE)forPGO problems.Then it transformed MLEinto eigen decomposition problem,and designed an improved modelreduction method to solve the problem by using the sparsityofdata, which further improves the computational speedofthe algorithm.The algorithm has theadvantagesof scalability,lowcomputational costand high precision.Finaly,experimentalevaluationonsimulatedandreal-worldpose-graphdatasetsshowsthat theproposedalgorithm can optimize the pose graph quickly without compromising accuracy.

Key words: pose graph optimization; maximum-likelihood estimation; eigen decomposition; model reduction

# 0 引言

SLAM(Simultaneous Localization and Mapping)是在机器人缺乏环境先验信息的情况下，通过传感器的测量值在对自身运动进行估计的同时建立环境模型[I]，这对在未知场景中进行自主导航和探索至关重要。近年来，SLAM技术广泛应用于日常生活中，例如自动驾驶[2]，搜索救援[3]，精密农业[4]等，成为研究热点。SLAM系统分为前端和后端，如图1所示。前端视觉里程计(visulaodometry，VO)，是根据相邻图像估计相机之间的相对运动，但这个过程存在累积误差，需要后端对前端输出的结果进行优化，得到最优的位姿估计和全局一致[5]的地图，提高SLAM系统的精度。

![](images/ce0a881e586b7cf41be2f04396f0e1b8579e2d5a73aaf43610c60837a6baf0ef.jpg)  
图1SLAM系统框架  
Fig.1Architecture of SLAM system

PGO是目前机器人领域中应用最广泛的SLAM后端优化技术[6]，将SLAM问题用图进行直观表示，其中图的顶点表示机器人的绝对位姿，边表示相对测量值，然后对图进行优化，得到更精确的结果。PGO的目标问题通常是高维的[7],涉及很多变量和约束，所以对优化算法的计算效率要求很高。此外由于目标问题的非凸性，在求解时容易陷入局部极小值使估计完全无用，所以在保证计算效率的基础上，避免陷入局部极小值是PGO问题的重中之重。

目前PGO问题的求解算法主要划分为三类[8]，第一类算法是利用问题的全局结构进行迭代求解。Lu和Milios[9]首次提出用位姿图表示SLAM问题，并进行迭代非线性优化。Olson等人[10]提出用随机梯度下降方法求解PGO问题，该方法具有良好的稳定性和可扩展性，即使给定较差的初始估计，也可以快速优化机器人的位姿。Grisetti等人[1]改进了Olson等人的工作，使用树状结构定义和更新局部区域，显著提高了随机梯度下降方法的收敛性。Kaess 等人[12\~14]提出了增量平滑算法，该类算法可以更好地处理非线性测量模型，通过增量重新排序提高了优化效率，可以实现大规模PGO问题的更新。Rosen 等人[15]研究了PGO问题的最小二乘结构，指出了降低其非线性和非凸性的可能性。Kümmerle等人[16]利用图结构的稀疏性，使用高斯-牛顿方法进行求解。然而，上述所有的非线性优化技术都是局部搜索方法，并不能保证解的最优性。

第二类算法旨在寻找良好的初始值，以提高收敛速度并降低收敛到局部极小值的风险。Carlone等人[17]提出了LAGO算法，为2DPGO问题提供了精确的初始估计，但是LAGO算法只能应对中低噪声数据集。之后在文献[18]中对几种先进的初始化方法进行了回顾和比较，结果表明，使用弦方法作为初始化器，GTSAM作为求解器是迭代求解的最佳组合。Nasiri等人[19]提出了RS算法求解PGO问题，该算法在高噪声下也能得到最优解的精确近似，具有较好的鲁棒性。

第三类算法是对PGO问题进行松弛，以克服目标问题的非凸性。Carlone等人对原问题进行半定松弛，利用拉格朗日对偶理论验证了 $\boldsymbol { 2 \mathrm { D } ^ { [ 2 0 ] } }$ 和 $3 \mathrm { D } ^ { [ 2 1 ] }$ SLAM中解的最优性；并证明了当对偶间隔为零时，可以检索出原问题的全局最优解。Rosen等人[22利用PGO问题的低秩、几何结构，将其简化为低维黎曼流形上的等价优化问题，并设计了一种截断信任域方法进行求解，比使用内点法求解快几个数量级。Eriksson等人[23]利用图论对旋转平均问题进行了理论分析，求解出了噪声水平的误差界，以确保解的全局最优性。然而，因为这些解是通过松弛约束得到的，所以通常不在原问题的可行域内，需要重新投影。

综上，目前PGO的相关算法可以收敛到全局最优近似解，但是计算速度较慢，计算成本过高。为了加快求解效率，Singer[24]提出通过特征分解进行角同步的计算，但是只能应用于2D问题，不能扩展到更常用的3D问题。之后在文献[25]中，将特征分解方法扩展到了3D问题，但是只计算了位姿的旋转部分，忽略了平移部分的优化。Arrigoni 等人[26]提出用特征分解方法解决运动同步问题，同时对旋转和平移进行优化(即在线性群 $S E ( 3 )$ 上进行优化)，但是增大了优化矩阵的维度，随着问题规模的增加，求解速度会受到很大影响；并且为了最终得到满足 $S E ( 3 )$ 形式的解，牺牲了估计的精度。

本文在上述问题的基础上提出了基于特征分解的快速位姿图优化算法，即EDPO算法。该算法分为两个阶段进行优化：第一阶段使用改进的特征分解算法优化旋转矩阵，第二个阶段使用最小二乘法求解平移部分。该算法具有可伸缩性、计算成本低和精度高等优点。本文的主要贡献如下：

a)提出了一种新颖的PGO算法，将原PGO问题划分为两个子问题。首先对旋转矩阵的行列式约束进行松弛，推导出了基于特征分解的封闭解，再将解投影到正交群上以满足旋转矩阵的性质；然后使用最小二乘法优化位姿的平移部分。

b)提出了一个简洁的矩阵公式，将原PGO问题的公式改写为可以进行特征分解的形式，与对应的图结构的Laplacian矩阵建立了联系，以便进行特征分解；并且该矩阵公式可以处理数据缺失的情况，计算更精确。

c)为了提高特征分解模型的计算性能，提出了一种改进的模型降阶方法，高效地解决了推导出的特征分解模型的高维问题。

d)在模拟和真实的PGO数据集上的对比实验表明，在不影响精度的情况下，EDPO算法显著提高了计算效率。

# 位姿图优化理论基础

# 1.1 图的理论基础

图结构可以用 $\scriptstyle { \mathrm { G } = } ( \mathrm { V } , \mathrm { E } )$ 表示，其中 $\mathrm { \Delta V }$ 是非空集合称为节点集，E是 $\mathrm { ~ v ~ }$ 中元素构成的无序二元组的集合，称为边集，本文中节点数和边数分别用 $\mathfrak { n }$ 和 $\mathbf { m }$ 表示。若每对不同的顶点之间都恰有一条边相连，则该图为完全图(如图 2)。

令 $A \in \mathbb { R } ^ { n \times n }$ 为G的邻接矩阵，其元素为

$$
A _ { i j } = \left\{ { \begin{array} { l } { 1 , ( i , j ) \in E } \\ { 0 , ( i , j ) \not \in E } \end{array} } \right.
$$

很显然， $A$ 为对称矩阵。令 $D \in \mathbb { R } ^ { n \times n }$ 为 $\boldsymbol { G }$ 的度矩阵，则 $D$

为对角阵，对角线上的元素为各个顶点的度，即 $D _ { i i } = \sum _ { j } A _ { i j }$ .令$\boldsymbol { L } \in \mathbb { R } ^ { n \times n }$ 为 $G$ 的Laplacian 矩阵，则有 $\scriptstyle L = D - A$ .以图2为例，该图的邻接矩阵 $A$ 、度矩阵 $D$ 和Laplacian 矩阵 $\boldsymbol { L }$ 分别为

$$
A = { \left[ \begin{array} { l l l l } { 0 } & { 1 } & { 1 } & { 1 } \\ { 1 } & { 0 } & { 1 } & { 1 } \\ { 1 } & { 1 } & { 0 } & { 1 } \\ { 1 } & { 1 } & { 1 } & { 0 } \end{array} \right] } , D = { \left[ \begin{array} { l l l l } { 3 } & { 0 } & { 0 } & { 0 } \\ { 0 } & { 3 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 3 } & { 0 } \\ { 0 } & { 0 } & { 0 } & { 3 } \end{array} \right] } , L = { \left[ \begin{array} { l l l l } { 3 } & { - 1 } & { - 1 } & { - 1 } \\ { - 1 } & { 3 } & { - 1 } & { - 1 } \\ { - 1 } & { - 1 } & { 3 } & { - 1 } \\ { - 1 } & { - 1 } & { - 1 } & { 3 } \end{array} \right] }
$$

![](images/097d3819a35de130023a0a99a83155b849b7a86e7c7f57694b5a527300231562.jpg)  
图2完全图示例  
Fig.2 Complete graph

加权图是由图 $\scriptstyle { \mathrm { G } = } ( \mathrm { V } , \mathrm { E } )$ 和定义在其边上的权重函数 $w$ 组成的三联体 $ { \bf G } { = } ( \mathrm { V } , \mathrm { E } , \mathrm { w } )$ 。在一些应用中，给出了反映测量值可靠性的非负权重 $w _ { i j }$ ，将其存储在图的邻接矩阵 $A = [ w _ { i j } ]$ 中，因此，加权图的度矩阵 $D$ 定义为 $D _ { i i } = \sum _ { j } w _ { i j }$ □

# 1.2位姿图优化

位姿图是图优化的一种具体形式，其中图的顶点表示机器人的绝对位姿，边表示相对测量值，本文将其用于解决机器人的轨迹优化问题。

PGO计算在给定 $\mathbf { m }$ 对相对测量值的条件下，n个机器人位姿 $\mathbf { \psi } _ { X _ { 1 } , \dots , X _ { n } }$ 的最大似然估计。在三维问题中，机器人的绝对位姿和相对测量值都是特殊欧式群 $S E ( 3 )$ 中的元素$S E ( 3 ) \doteq \{ ( R , t ) : R \in S O ( 3 ) , t \in \mathbb { R } ^ { 3 } \}$ ，旋转矩阵需要同时满足正交约束和行列式约束。本文使用符号 $\boldsymbol { x } _ { i } = ( R _ { i } , t _ { i } )$ 和 $\overline { { \boldsymbol { x } } } _ { i j } = ( \overline { { \boldsymbol { R } } } _ { i j } , \overline { { \boldsymbol { t } } } _ { i j } )$ 分别表示绝对位姿和相对测量值。

本节提出一个修改后的 PGO 公式，其中将使用弦距离来量化旋转误差，从测量值的生成模型开始，然后推导出相应的最大似然估计。

# 1.2.1测量值的生成模型

假设以下是相对测量值 $( \overline { { R } } _ { i j } , \overline { { t } } _ { i j } )$ 的生成模型

$$
\begin{array} { l } { { \overline { { { t } } } _ { i j } = R _ { i } ^ { T } ( t _ { j } - t _ { i } ) + \tilde { t } _ { i j } , \tilde { t } _ { i j } \sim g a u s s i a n ( 0 _ { 3 } , \omega _ { t } ^ { 2 } I _ { 3 } ) } } \\ { { \overline { { { R } } } _ { i j } = R _ { i } R _ { j } ^ { T } \tilde { R } _ { i j } , \tilde { R } _ { i j } \sim \nu o n M i s e s ( I _ { 3 } , \omega _ { R } ^ { 2 } ) } } \end{array}
$$

其中gaussian $( \mu , \Omega )$ 表示均值为 $\mu$ 和协方差矩阵为 $\Omega$ 的高斯分布；vonMises $( S , k )$ 表示均值为S，参数为 $\mathbf { k }$ 的各向同性的vonMises-Fisher分布。

# 1.2.2最大似然估计

求解位姿的最大似然估计(MLE)等价于最小化负对数似然：

$$
f _ { M L E } ^ { * } = \operatorname* { m i n } _ { \{ x _ { i } \in S E ( 3 ) \} } \sum _ { ( i , j ) \in E } - \log L ( \overline { { R } } _ { i j } \left| x \right. ) - \log L ( \overline { { t _ { i j } } } \left| x \right. ) .
$$

$$
- \log L ( \overline { { \boldsymbol { R } } } _ { i j } | \boldsymbol { x } ) = \frac { k _ { i j } ^ { 2 } } { 2 } \big \| \boldsymbol { R } _ { i } - \overline { { \boldsymbol { R } } } _ { i j } \boldsymbol { R } _ { j } \big \| _ { F } ^ { 2 } + c o n s t .
$$

$$
- \log L ( \overline { { t _ { i j } } } \left| x \right. ) = \tau _ { i j } ^ { 2 } \left\| t _ { j } - t _ { i } - R _ { i } \overline { { t _ { i j } } } \right\| ^ { 2 } + c o n s t .
$$

其中， $\left\| \bullet \right\| _ { F } ^ { 2 }$ 表示矩阵的Frobenius 范数。

将式(4)和(5)代入到式(3)中，得到最大似然估计：

$$
f _ { M L E } ^ { * } = \underset { \{ t _ { i } \in B ^ { 3 } \} } { \operatorname* { m i n } } \sum _ { ( i , j ) \in E } \tau _ { i j } ^ { 2 } \left. t _ { j } - t _ { i } - R _ { i } \overline { { t } } _ { i j } \right. ^ { 2 } + \frac { k _ { i j } ^ { 2 } } { 2 } \left. R _ { i } - \overline { { R } } _ { i j } R _ { j } \right. _ { F } ^ { 2 }
$$

MLE问题是高维、非凸的，假设 $\operatorname* { m i n } _ { R _ { i } \in S O ( 3 ) } \frac { k _ { i j } ^ { 2 } } { 2 } \big \| R _ { i } - \overline { { R } } _ { i j } R _ { j } \big \| _ { F } ^ { 2 }$ 是式(6)的最优旋转解，则平移的求解变成一个最小二乘问题[19],因此，将原优化问题划分为两个子问题：

$$
\begin{array} { r l r } & { } & { \underset { R _ { i } \in S O ( 3 ) } { \operatorname* { m i n } } \frac { k _ { i j } ^ { 2 } } { 2 } \big \| R _ { i } - \overline { { R } } _ { i j } R _ { j } \big \| _ { F } ^ { 2 } } \\ & { } & \\ & { } & { \underset { t _ { i } \in { \cal R } ^ { 3 } } { \operatorname* { m i n } } \tau _ { i j } ^ { 2 } \left\| t _ { j } - t _ { i } - { R _ { i } } \overline { { t _ { i j } } } \right\| ^ { 2 } } \end{array}
$$

在接下来的部分中，将先求解问题式(7)，然后用得到的最优旋转解来求解问题式(8)。

# 2 本文方法

# 2.1旋转优化模型

为了求解旋转问题式(7)，下面证明通过特征分解可以找到一个全局最优旋转解 $\boldsymbol { \mathrm { ~ R ~ } ^ { * } }$ 。为方便进行推导计算，在后面的推导中使用块矩阵，将所有位姿的旋转矩阵堆叠在 $R \in \mathbb { R } ^ { 3 n \times 3 }$ 中

$$
R = \left[ R _ { 1 } ^ { T } , . . . , R _ { n } ^ { T } \right] ^ { T } , R _ { i } \in S O ( 3 )
$$

首先考虑所有相对测量值都可用(即完全图)，并且相对测量值不含噪声的情况，将旋转测量值 $\overline { { R } } _ { i j }$ 堆叠在块矩阵$\overline { { \boldsymbol { R } } } \in \mathbb { R } ^ { 3 n \times 3 n }$ 中，即

$$
{ \overline { { R } } } = { \left( \begin{array} { l l l l } { I _ { 3 } } & { { \overline { { R } } } _ { 1 2 } } & { \dots } & { { \overline { { R } } } _ { 1 n } } \\ { { \overline { { R } } } _ { 2 1 } } & { I _ { 3 } } & { \dots } & { { \overline { { R } } } _ { 2 n } } \\ { \dots } & { } & { } & { \dots } \\ { { \overline { { R } } } _ { n 1 } } & { { \overline { { R } } } _ { n 2 } } & { \dots } & { I _ { 3 } } \end{array} \right) }
$$

基于 $\overline { { R } } _ { i j } = R _ { i } R _ { j } ^ { \textit { T } }$ ，则有

$$
\left\{ \begin{array} { c } { { \overline { { { R } } } = R R ^ { T } } } \\ { { r a n k ( \overline { { { R } } } ) = 3 } } \end{array} \right.
$$

因为 $R ^ { T } R = n I _ { 3 }$ ，可得到

$$
\overline { { R } } R = n R
$$

这意味着在没有噪声的情况下， $R$ 的列是由 $\overline { { R } }$ 的与特征值 $\mathfrak { n }$ 对应的特征向量构成的，因为 $\overline { { R } }$ 的秩为3，所以其余特征值均为零， $\mathfrak { n }$ 就是 $R$ 的最大特征值。式(12)等价于式(13)

$$
( n I _ { 3 } - \overline { { R } } ) R = 0
$$

其次考虑相对运动测量被噪声破坏的情况，式(12)对应的优化问题为

$$
\operatorname* { m i n } _ { R _ { i } \in O ( 3 ) } \frac { k _ { i j } ^ { 2 } } { 2 } \big \| \overline { { R } } R - n R \big \| _ { F } ^ { 2 }
$$

此处放松了旋转矩阵的行列式约束，即在 $O ( 3 )$ 中进行优化， $O ( 3 ) \doteq \{ R \in \mathbb { R } ^ { 3 \times 3 } : R ^ { T } R = I _ { 3 } \}$ 。

然而在实际应用中并非所有相对测量值都可用，所以下面考虑数据缺失的情况。缺失的相对运动对应 $\overline { { R } }$ 中的零块，$( A \otimes \mathbb { I } _ { 3 } ) \circ { \overline { { R } } }$ 表示可用的相对运动信息，其中， $\otimes$ 表示Kronecker积，·表示Hadamard积。邻接矩阵 $A$ 在与 $1 _ { 3 }$ 进行Kronecker乘积后被扩维，以匹配 $\overline { { R } }$ 的块结构。在这种情况下，式(12)可以推广为

$$
( ( A \otimes 1 _ { 3 } ) \circ \overline { { { R } } } ) R = ( D \otimes I _ { 3 } ) R
$$

等价于

$$
( ( D \otimes I _ { 3 } ) - ( A \otimes 1 _ { 3 } ) \circ { \overline { { R } } } ) R = 0
$$

观察到 $D \otimes I _ { 3 }$ 对应于 $( D \otimes 1 _ { 3 } ) \circ { \overline { { R } } }$ ，因为 $\overline { { R } }$ 的对角线上的元素是单位阵，并且 $D \otimes I _ { 3 }$ 是块对角阵。所以式(16)可以再进一步改写为

$$
( ( L \otimes 1 _ { 3 } ) \circ \overline { { R } } ) R = 0
$$

当噪声存在时，上式不完全成立，对应的优化问题为

$$
\operatorname* { m i n } _ { R _ { i } \in O ( 3 ) } \left\| M R \right\| _ { F } ^ { 2 }
$$

其中， $M = ( ( L \otimes 1 _ { 3 } ) \circ \overline { { R } }$ 0

命题1问题式(18)存在一个封闭解，由 $M ^ { T } M$ 的最小特征值相关的三个特征向量给出。

证明 问题式(18)等价于

$$
\begin{array} { c } { \operatorname* { m i n } t r ( R ^ { T } ( M ^ { T } M ) R ) } \\ { s . t . R _ { i } \in O ( 3 ) } \end{array}
$$

对应的拉格朗日函数为

$$
L ( R , \Lambda ) { = } t r ( R ^ { T } ( M ^ { T } M ) R ) { + } t r ( \Lambda ( R ^ { T } R { - } n I _ { 3 } ) )
$$

其中， $\Lambda = b l k d i a g ( \Lambda _ { 1 } , . . . , \Lambda _ { n } ) \in \mathbb { R } ^ { 3 n \times 3 n }$ 为拉格朗日乘子，根据拉格朗日定理[27]，将 $\mathrm { ~ L ~ }$ 对 $\mathtt { R }$ 的偏导数设置为零，可得到稳定性条件：

$$
2 ( M ^ { T } M ) R + 2 R \Lambda = 0
$$

即 $( M ^ { T } M ) R = - R \Lambda$ ，令 $r _ { i } ( \mathrm { i } \mathrm { = } 1 , 2 , 3 )$ 为 $M ^ { \boldsymbol { r } } M$ 的任意三个特征向量，且 $\lambda _ { i }$ 是对应的特征值，则 $R = [ r _ { 1 } , r _ { 2 } , r _ { 3 } ]$ 同时满足式(21)及约束 $R ^ { T } R = n I _ { 3 }$ 。也就是说，任意三个特征向量都可以组成拉格朗日函数的一个稳定点。如果 $r _ { i } ( i = 1 , 2 , 3 )$ 是 $M ^ { \scriptscriptstyle T } M$ 的最小特征值对应的特征向量，则得到问题式(18)的最小值，所以原优化问题转换为求解矩阵的特征向量问题。

最终求得了问题式(18)的封闭解，但这是原问题松弛形式下求得的解，可能不完全满足旋转矩阵的性质，为了得到更精确的旋转估计值，用 $F$ 表示命题1得到的包含特征向量的 $3 n \times 3$ 的矩阵。其中 $F _ { i }$ 表示第 $i$ 个位姿旋转的估计值，需要通过奇异值分解 $F _ { i } = U _ { i } \sum _ { i } V _ { i } ^ { T }$ 找到与其最接近的旋转矩阵，并令 $\hat { R } _ { i } ^ { T } = U _ { i } V _ { i } ^ { T }$ ，再进一步强制执行 $\operatorname* { d e t } ( { \hat { R } } _ { i } ) = 1$ ，得到满足旋转约束的解。

# 2.2改进的模型降阶方法

在旋转优化模型建立后，需要进行特征值和特征向量的求解。因为在实际应用中需要求解的矩阵是高维且稀疏的，使用传统算法会大量填充零元素，严重消耗内存，所以需要寻求有效的求解方法。目前常用的方法是Arnoldi模型降阶方法[26]，该方法用一个较小系统近似原始系统，稳定性强，计算速度快，适用于大规模的特征求解问题。本文在Arnoldi模型降阶方法的初始化阶段进行了改进。

Arnoldi模型降阶方法，首先要建立矩阵 $M ^ { \scriptscriptstyle { T } } M$ 的Krylov子空间的一组标准正交基 $( \nu _ { 1 } , . . . , \nu _ { r } )$ ，这组基的构造需要经过迭代计算

$$
w = ( M ^ { \boldsymbol { \tau } } M ) \nu _ { j }
$$

得到 $w$ ，然后再将 $w$ 与之前的向量进行正交，得到 $\boldsymbol { \nu } _ { j + 1 }$ 。然而，仅通过一次正交化可能得不到稳定的系统，所以本文在正交化之后又加入重正交化步骤，这样可以保证得到的子空间的基具有较好的正交性。算法1总结了改进的模型降阶方法。

算法1改进的模型降阶方法输入：对称矩阵 $M ^ { \scriptscriptstyle T } M$ 和单位向量 $\nu _ { 1 }$ 输出： $M ^ { T } M$ 的特征值与特征向量 $\lambda _ { i } , \varphi _ { i } ( i = 1 , 2 , . . . , r )$

步骤1：for j=l:r-1

$$
w = ( M ^ { \tau } M ) \nu _ { j }
$$

$$
h _ { i j } = \nu _ { i } ^ { _ { T } } w ; w = w - h _ { i j } \nu _ { i } ;
$$

end

for $\mathrm { i } { = } 1 \mathrm { : } \mathrm { j }$ //重正交化

$$
\begin{array} { r } { s = \nu _ { i } ^ { T } w ; } \end{array}
$$

$$
h _ { i j } = h _ { i j } + s ; w = w - s \nu _ { i } ;
$$

end

$$
h _ { j + 1 , j } = 0
$$

$$
\nu _ { j + 1 } = w / h _ { j + 1 , j }
$$

end

$$
V _ { j + 1 } = [ V _ { j } , \nu _ { j + 1 } ] ;
$$

end

$$
H _ { r } = [ h _ { i , j } ]
$$

步骤2： $( M ^ { T } M ) V _ { r } = V _ { r } H _ { r } + h _ { r + 1 , r } \nu _ { r + 1 } e _ { r } ^ { T }$ /\*得到 $r$ 步 Arnoldi 分解，其中 $\boldsymbol { e } _ { r }$ 是单位矩阵 $I _ { r }$ 的最后一行 $^ { * } /$

步骤3：计算矩阵 $H _ { r }$ 的特征值和对应的特征向量，分别为

$$
\lambda _ { i } , \eta _ { i } ( i = 1 , 2 , . . . , r ) ;
$$

步骤4：矩阵 $M ^ { \scriptscriptstyle T } M$ 的特征值和特征向量分别为

$$
\lambda _ { i } = \lambda _ { i } , \varphi _ { i } = V _ { r } \eta _ { i } ( i = 1 , 2 , . . . , r ) ;
$$

步骤5：返回 $\lambda _ { i } , \varphi _ { i } ( i = 1 , 2 , . . . , r )$

# 2.3基于特征分解的封闭解算法

通过2.1节的旋转优化模型找到了最优解 $R ^ { * }$ 后，问题式(8)可以写为

$$
\operatorname* { m i n } _ { t _ { i } \in R ^ { 3 } } \tau _ { i j } ^ { 2 } \left\| t _ { j } - t _ { i } - R _ { i } ^ { \ast } \overline { { t } } _ { i j } \right\| ^ { 2 }
$$

与2.1节类似，使用块矩阵进行推导，将平移向量$t _ { i } ( i = 1 , . . . , n )$ 堆叠在 $t \in \mathbb { R } ^ { 3 n }$ 中

$$
t = [ t _ { 1 } ^ { T } . . . t _ { n } ^ { T } ] ^ { T }
$$

因此，式(23)可以重写为

$$
\operatorname* { m i n } _ { t \in R ^ { 3 n } } \bigl \| ( B \otimes I _ { 3 } ) t - C \bigr \| ^ { 2 }
$$

其中， $\boldsymbol { B } \in \mathbb { R } ^ { m \times n }$ 是包含权重的邻接矩阵，在与 $I _ { 3 }$ 进行Kronecker乘积后被扩维，以匹配 $t$ 的结构； $C \in \mathbb { R } ^ { 3 m }$ 是包含相对平移测量值的矩阵， $c$ 的第 $k$ 行是 $R _ { i } ^ { * } \overline { { t _ { i j } } }$ ，（ $e _ { k } = ( i , j ) \in E$ )。显然，这是一个线性最小二乘问题，封闭解为

$$
t ^ { * } = ( B ^ { T } B ) ^ { - 1 } B ^ { T } C
$$

由于 $B ^ { r } B$ 是对称的，可以使用Cholesky分解进行预处理，这样可以加快计算逆矩阵的速度。结合前面的旋转优化模型，得到了完整的EDPO算法，总结在了算法2中。

算法2 EDPO 算法

输入：图的节点 $V$ 、边 $E$ 、相对测量值 $( \overline { { R } } _ { i j } , t _ { i j } )$ 以及权重 $k _ { i j } ^ { 2 } .$ ， $\tau _ { i j } ^ { 2 }$ 输出：位姿估计 $R _ { i } , t _ { i } ( i = 1 , 2 , . . . , n )$ （204号

步骤1：将原PGO 问题划分为式(7)(8)两个子问题；

步骤2：求解子问题 $\operatorname* { m i n } _ { R _ { i } \in S O ( 3 ) } \frac { k _ { i j } ^ { 2 } } { 2 } \big \| R _ { i } - \overline { { R } } _ { i j } R _ { j } \big \| _ { F } ^ { 2 }$

$$
\begin{array} { l } { { A ( i , j ) = k _ { i j } ; D ( i , i ) = D ( i , i ) + k _ { i j } ; } } \\ { { \overline { { R } } ( b l o c k ( i , j ) ) = \overline { { R } } _ { i j } ; \overline { { R } } ( b l o c k ( i , i ) ) = I _ { 3 } ; } } \end{array}
$$

end

$$
\begin{array} { r } { L = D - A ; } \end{array}
$$

$$
M = ( ( L \otimes \mathbf { l } _ { 3 } ) \circ { \overline { { R } } }
$$

3.用算法1求解 $M ^ { \scriptscriptstyle T } M$ 的最小特征值和对应的三个特征向量，记为 $r _ { i } ( i = 1 , 2 , 3 )$

4.for i=1:n

$$
\begin{array} { c } { { F _ { i } = r ( 3 ^ { * } i - 2 : 3 ^ { * } i , 3 ) ; } } \\ { { { } } } \\ { { { [ U _ { i } , \sum _ { i } , V _ { i } ] = S V D ( F _ { i } ) ; } } } \\ { { { } } } \\ { { R _ { i } = U _ { i } V _ { i } ^ { T } ; } } \end{array}
$$

end

步骤3：求解子问题minτl-t-iu²

$$
\begin{array} { r c l } { { } } & { { } } & { { e _ { k } = ( i , j ) \in E } } \\ { { } } & { { } } & { { B ( k , i ) = - \tau _ { i j } ; B ( k , j ) = \tau _ { i j } ; } } \\ { { } } & { { } } & { { C ( 3 ^ { * } k - 2 : 3 ^ { * } k ) = R _ { i } \overline { { { t } } } _ { i j } ; } } \end{array}
$$

$$
\begin{array} { c } { \displaystyle \{ . ~ t ^ { * } = ( B ^ { T } B ) ^ { - 1 } B ^ { T } C ; } \\ { t _ { i } = t ^ { * } ( 3 ^ { * } i - 2 : 3 ^ { * } i ) ; } \end{array}
$$

步骤4：返回 $R _ { i } , t _ { i } ( i = 1 , 2 , . . . , n )$ ：

# 3 实验结果与分析

在本节中，分别在模拟和真实的3DPGO 数据集上进行实验，将提出的EDPO 算法与高斯一牛顿法(记为G-N)、EIG算法[26]进行对比，评估EDPO 算法的性能。以下所有实验都是在DellOptiPlex7040 微型台式机电脑上进行的，实验运行环境配置为Intel $\textsuperscript { \textregistered }$ Core i5-6500 CPU $@$ 3.20GHz，4GB内存，运行Windows10系统。

# 3.1模拟噪声实验

为了探究测量噪声(包括旋转和平移)、问题规模大小对EDPO算法性能的影响，所以进行了一组模拟实验。首先向原始cube数据子集的相对测量值添加噪声，该数据集模拟了机器人沿直线穿过规则立方体的轨迹。测量值 $\tilde { x } _ { i j } = ( \tilde { R } _ { i j } , \tilde { t } _ { i j } )$ 根据式(2)进行采样，其中，旋转噪声的标准差 $\sigma \mathrm { R } \in [ 0 ^ { \circ } , 1 0 ^ { \circ } ]$ ，平移噪声的标准差 $\sigma \mathrm { T } \in [ 0 \mathrm { m } , 1 \mathrm { m } ]$ 。

然后分别在不同噪声水平(包括旋转和平移)、不同规模大小的cube 数据集上，对比了EDPO 算法和G-N算法、EIG算法的目标函数值以及运行时间。本文的目标函数为损失函数，所以数值越小说明结果越精确。所有的统计数据都是经过100次随机实验取平均值得到的，模拟实验的结果如下。其中，图3的(a)(b)分别描述旋转噪声(平移噪声固定为 $\sigma \mathrm { T } { = } 0 . 1$ =位姿数量固定为 $5 ^ { 3 }$ )对三种算法的目标函数值和运行时间的影响，从图中可以看出，EDPO算法的速度比G-N法和EIG算法要快得多，目标函数值与G-N法基本持平。这组模拟实验的结果表明，EDPO算法在合理的操作条件下可以得到SLAM问题的全局最优近似解。

![](images/258e304912e311802584aded6ec7b19fa3f82e7920429eca55c15967157251c6.jpg)  
图3不同水平的旋转噪声对算法性能的影响Fig.3Influence of different levels of rotating noise onalgorithm performance

同时，还记录了三种算法的误差对比分析结果，包括平均误差、中值误差和均方根误差，误差越小，表示算法越稳定鲁棒性越好。实验结果分别记录在图4的(a)(b)(c)中。可以看到，旋转噪声的标准差 $\sigma \mathrm { R } \in [ 0 ^ { \circ } , 1 0 ^ { \circ } ]$ 时，EDPO算法的误差值小于EIG 算法，与G-N法基本持平，这表明EDPO算法在一定的旋转噪声水平下可以恢复机器人的位姿轨迹。

图5的(a)(b)分别描述平移噪声(旋转噪声固定为 $\sigma \mathbf { R } { = } 5 ^ { \circ }$ ，位姿数量固定为 $5 ^ { 3 }$ )对三种算法的目标函数和运行时间的影响，从图中可以看出，EDPO 的速度比G-N 法和 EIG 法要快，目标函数值与G-N法基本持平，所以总体性能要优于G-N法和EIG法。

![](images/c2362235a7afcef925a6020dd0ad4d0d8c82bfef07dff727d0ca2355bc942224.jpg)  
Fig.4Error comparison of optimization results

图4优化结果的误差比较

![](images/e9bab17c26c04b8650abd6f4d172fbf91da45f286cf81b966457968e86f5e3cd.jpg)  
Fig.5Influence of different levels of translation noise on algorithm performance

图6的(a)(b)分别描述位姿数量的增加对三种算法性能的影响(旋转噪声固定为 $\sigma { \mathrm { R } } { = } 5 ^ { \circ }$ ，平移噪声固定为 $\sigma \mathrm { T } { = } 0 . 1$ )从图中可以看出，问题规模的增加对EDPO运行时间的影响要小于G-N法和EIG 算法，并且目标函数值与G-N法基本持平，这验证了EDPO算法具有可伸缩性，适用于大规模问题。

![](images/c8aabe2e433d0b606d6673e7a17573e67e2b11bef0d0c0941d4d34452856f8b4.jpg)  
图5不同水平的平移噪声对算法性能的影响  
(b）位姿数量对运行时间的影响  
图6位姿数量对算法性能的影响  
Fig.6The influence of pose number on algorithm performance

# 3.2算法性能对比实验

选择了6个公开的3DSLAM数据集作为本文的实验数据集，其中sphere、torus和cube 数据集是模拟数据集，cubicle、rim 和garage是真实数据集。sphere 数据集模拟了机器人在球面上运动的轨迹；torus数据集模拟了机器人在环面表面上运动时的轨迹；cube数据集是对机器人在三维网格世界上行走的轨迹进行了模拟。garage 是收集自Vertigo 的真实数据集；cubicle、rim是RIM中心收集的两个真实数据集，通过对3D激光扫描仪获取的点云进行ICP获取了相对位姿约束。对于每个数据集，都将相应的位姿数量(n)和相对测量值的数量(m)整理在了表1中。

表1数据集信息  
Tab.1 Datasets information   

<html><body><table><tr><td>数据集</td><td>n</td><td>m</td></tr><tr><td>Sphere</td><td>2200</td><td>8647</td></tr><tr><td>Torus</td><td>5000</td><td>9047</td></tr><tr><td>Cube</td><td>8000</td><td>22236</td></tr><tr><td>Rim</td><td>10195</td><td>29743</td></tr><tr><td>Cubicle</td><td>5750</td><td>16869</td></tr><tr><td>Garage</td><td>1661</td><td>6275</td></tr></table></body></html>

在本部分实验中，将在以上3DSLAM数据集上评估EDPO的性能，这一组数据集更好地表示了实际应用中的问题分布。表2记录了EDPO算法、G-N法和EIG算法在每个数据集上的运行结果，包括数据集的初始值、求解的目标函数值、算法的运行时间以及EDPO算法求得的数据集的最小特征值。表3记录了三种算法优化得到的轨迹与地面真实轨迹之间的误差结果对比，包括平均误差、中值误差、均方根误差以及标准差。

通过表2可以看到在每个数据集中，得到的结果与3.1节的模拟实验结果相似。在优化结果方面，EDPO 在 torus、cube、cubicle、garage四个数据集上得到的解与G-N法持平，优化结果(机器人轨迹)如图7所示；在sphere 和rim 两个数据集上求解的结果比G-N法差，但是差异较小。通过表3可以看到，在本节比较的六个数据集中，EDPO 算法的轨迹误差要低于EIG算法，与G-N法基本持平。综上，在三种优化方法中，EIG 算法的优化结果要差于EDPO 算法和G-N 法，因为EIG算法将旋转和平移同时优化，只进行单一的特征分解得到四个特征向量，然后再投影到SE(3)上，为了满足SE(3)的形式，导致得到的平移估计不是最优的。EDPO算法先对旋转矩阵进行优化，然后用得到的最优解求解平移部分，保证平移估计的准确性。

另一方面，通过表2的相关数据可以看出，EDPO的求解速度要远远快于G-N法和EIG算法，这是因为EDPO算法执行直接的全局优化，用直接法对机器人的位姿进行优化求解，计算复杂度更低；而G-N法是迭代搜索技术，需要对位姿不断进行迭代优化直至收敛，所以运行时间在很大程度上取决于迭代次数；EIG算法将位姿的旋转部分和平移部分同时进行优化，扩大了位姿表示的矩阵维数，增大了计算复杂度，因此要慢于EDPO 算法。所以EDPO 算法在求解速度上更具优势，在速度至关重要的低噪声水平应用中，EDPO 算法的结果与G-N法结果之间的区别可以忽略不计，因此，该算法可以快速地求解得到一个很好的解。

表23DSLAM数据集的实验结果  
Tab.2Experimental results of a 3D SLAMdatasets   
表33DSLAM数据集的误差结果对比  

<html><body><table><tr><td rowspan="2">数据集</td><td rowspan="2">初始值</td><td colspan="3">EDPO</td><td colspan="2">G-N</td><td colspan="2">EIG</td></tr><tr><td>入</td><td>f</td><td>time(s)</td><td>f</td><td>time(s)</td><td>f</td><td>time(s)</td></tr><tr><td>Sphere</td><td>1.291×106</td><td>4.53×10-5</td><td>2.972×10</td><td>0.16</td><td>2.657×10</td><td>3.04</td><td>3.393×10³</td><td>0.43</td></tr><tr><td>Torus</td><td>1.996×106</td><td>1.53×10-3</td><td>2.422×104</td><td>1.27</td><td>2.422×104</td><td>10.66</td><td>2.475×104</td><td>4.54</td></tr><tr><td>Cube</td><td>7.327×107</td><td>7.51×10-3</td><td>8.432×104</td><td>3.12</td><td>8.432×104</td><td>599.05</td><td>8.733×104</td><td>8.16</td></tr><tr><td>Rim</td><td>4.532×107</td><td>1.28×10-5</td><td>8.983×104</td><td>1.98</td><td>8.602×104</td><td>43.76</td><td>4.147×105</td><td>5.81</td></tr><tr><td>Cubicle</td><td>4.994×106</td><td>9.43×10-6</td><td>4.643×104</td><td>2.63</td><td>4.643×104</td><td>338.01</td><td>7.227×104</td><td>7.12</td></tr><tr><td>Garage</td><td>8.36×103</td><td>4.25×10-7</td><td>1.288×100</td><td>0.28</td><td>1.288×100</td><td>1.53</td><td>1.422×100°</td><td>0.57</td></tr></table></body></html>

Tab.3Comparison of error results in 3D SLAM datasets

EDPO G-N EIG  
数据集平均误差 中值误差 均方根误差 标准差 平均误差 中值误差均方根误差 标准差 平均误差 中值误差均方根误差 标准差  
Sphere 0.554 0.549 0.578 0.171 0.546 0.538 0.571 0.167 0.672 0.659 0.701 0.215  
Torus 0.802 0.741 0.908 0.426 0.802 0.742 0.908 0.426 0.986 0.989 1.064 0.527  
Cube 0.834 0.866 0.899 0.334 0.833 0.864 0.896 0.333 1.114 0.876 1.195 0.486  
Rim 0.671 0.679 0.697 0.190 0.648 0.657 0.675 0.186 0.847 0.895 0.902 0.231  
Cubicle 0.723 0.702 0.787 0.316 0.721 0.667 0.787 0.309 0.943 0.937 1.047 0.428  
Garage 0.388 0.352 0.419 0.159 0.388 0.351 0.419 0.159 0.552 0.541 0.624 0.199(a) Torus 数据集 (b) Cubicle 数据集 (c)Cube 数据集 (d) Garage 数据集

图7EDPO 优化结果 Fig.7EDPO optimization results

这些结果进一步证明了EDPO 提供了一种有效的方法，可以恢复真实操作条件下的SLAM的全局最优近似解，而且在计算速度上具有明显的优势。计算速度的提高可以提升PGO技术的优化性能，对于基于图的SLAM，随着位姿图维数的增加，计算复杂度增大，EDPO算法可以提供一种平衡精度和时间的有效方法。

# 4 结束语

在 PGO问题中，最大似然估计能够以较高的精度求解位姿，然而，所涉及的优化策略往往过于繁琐，需要良好的初始化才能得到全局最优近似解。本文提出了基于特征分解的封闭解算法，该算法可以快速进行优化求解，并适用于大规模的SLAM问题。该算法由两部分组成，先针对旋转部分进行优化求解，得到旋转最优解后再对平移求解，并且针对该模型特点引入了模型降阶方法，在不影响精度的情况下，极大地提高了计算效率。最后，在模拟和真实的SLAM数据集上进行实验，结果表明，EDPO能够在合理的操作条件下快速恢复SLAM问题的全局最优近似解。在以后的工作中，希望能将本文算法整合到一个完整的SLAM系统中，以进一步验证和增强算法的实际性能。

# 参考文献：

[1]Cadena C,Carlone L,Carrillo H,et al.Past,present,and future of simultaneous localization and mapping: toward the Robust-Perception age[J].IEEE Trans on Robotics,2016,32 (6):1309-1332.   
[2]高兴波，史旭华，葛群峰，等．面向动态物体场景的视觉SLAM综述 [J]．机器人，2021,43(06):733-750.(Gao Xingbo,Shi Xuhua,Ge Qunfeng,et al.A review of visual SLAM for dynamic object scenarios [J].Rob0t,2021,43 (06): 733-750.)   
[3]王燕，索寒生，贾贵金．石化危险事故搜救移动机器人 SLAM问题 研究[J].控制工程,2018,25(2):6.(Wang Yan,Suo Hansheng,Jia Guijin.Research on MOBILE robot SLAMforPetrochemical Hazardous Acciuen Kescue [J]. Couol EIgIeerig Ol CIna,∠Uio,∠(∠): 0.)   
[4] 李晨阳，彭程，张振乾，等．融合里程计信息的农业机器人定位与地 图构建方法[J]．农业工程学报,2021,37(21):16-23.(Li Chenyang, Peng Cheng,Zhang Zhenqian,et al.Localization and map construction method of agricultural robot integrating odometer information [J]. Trans of the Chinese Society of Agricultural Engineering,2021,37 (21): 16- 23.)   
[5]Bazeille S,Filliat D.Combining odometry and visual loopclosure detection for consistent topo-metrical mapping [J]. RAIRO: Operations Research,2010,44 (4): 365-377.   
[6]梁明杰，闵华清，罗荣华．基于图优化的同时定位与地图创建综述 [J]．机器人，2013,35(4):13.(Liang Mingjie,Min Huaqing,Luo Ronghua.Graph-based SLAM: a survey [J].Robot,2013,35 (4):13.)   
[7]Griseti G,Kyummerle R, Stachniss C,et al.A tutorial on graph-based SLAM[J]. IEEE Intelligent Transportation Systems Magazine,2010,2 (4): 31-43.   
[8]张洪华，刘璇，陈付豪，等．基于图优化的SLAM后端优化研究与发 展[J].计算机应用研究,2019(1):7.(Zhang Honghua,Liu xuan,Chen Fuhao,et al. Research and development of SLAM Back-end optimization based on graph optimization [J]. Application Research of Computers, 2019 (1): 7.)   
[9]LuF,Milios E.Globally consistent range scan alignment for environment mapping [J].Autonomous Robots,1997,4(4): 333-349.   
[10] Olson E,Leonard J,Teller S.Fast iterative alignment of pose graphs with poor initial estimates [C]// Proc of IEEE International Conference on Robotics and Automation.[S.I.] : IEEE Press,2006: 2262-2269.   
[11] Griseti G,Stachniss C,Grzonka S,et al.A tree parameterization for efficiently computing maximum likelihood maps using gradient descent [C]// Proc of Robotics: Science and Systems. Boston: MIT Press,2007: 3-9.   
[12] Dellert F, Kaess M. Square Root SAM: Simultaneous localization and mapping via square root information smoothing [J]. The International Journal of Robotics Research,2006,25 (12):1181-1203.   
[13] Kaess M,Ranganathan A,DellaertF.iSAM: Incremental smoothing and mapping [J]. IEEE Trans on Robotics,2008,24 (6): 1365-1378.   
[14]Kaess M,Johannsson H,Roberts R，et al.iSAM2:Incremental smoothing and mapping using the Bayes tree [J].The International Journal of Robotics Research,2012,31 (2): 216-235.   
[15] Rosen D M,Kaess M,Leonard JJ. RISE: An incremental trust-region method for robust online sparse least-squares estimation [J].IEEE Trans on Robotics,2014,30 (5): 1091-1108.   
[16]Kyummerle R,Grisetti G,Strasdat H,et al. g2o:A general framework for graph optimization [Cl// Proc of IEEE International Conference on Robotics and Automation. [S.I.] : IEEE Press,2011: 3607-3613.   
[17] Carlone L,Aragues R,Castellanos JA,et al.A linear approximation for graph-based simultaneous localization and mapping [C]// Proc of Robotics: Science and Systems.Boston: MIT Press,2012: 41-48.   
[18] Carlone L,Tron R,Danilidis K,et al. Initialization techniques for 3D SLAM:a survey on rotation estimation and its use in pose graph optimization [C]// Proc of IEEE International Conference on Robotics and Automation.[S.I.] : IEEE Press,2015: 4597-4604.   
[19] Nasiri S M, Moradi H, Hosseini R.A linear least square initialization method for 3D pose graph optimization problem [C]/ Proc of IEEE International Conference on Robotics and Automation.[S.I.]:IEEE Press,2018:2474-2479.   
[20] Carlone L,Dellaert F.Duality-based verification techniques for 2D SLAM[C]// Proc of IEEE International Conference on Robotics and Automation.[S.I.] :IEEE Press,2015: 4589-4596.   
[21] Carlone L,Rosen D M,Calafiore G,et al.Lagrangian duality in 3D SLAM: verification techniques and optimal solutions [Cl//Proc of IEEE International Conference on Intellgent Robots and Systems.Vancouver: IEEE Press,2015: 125-132.   
[22] Rosen DM, Carlone L,Bandeira A S,et al. SE-Sync: Acertifiably correct algorithm for synchronization over the special Euclidean group [J].The International Journal of Robotics Research,2019,38 (2-3): 95-125.   
[23] Eriksson A, Olsson C,Kahl F,et al. Rotation averaging and strong duality [C]// Proc of the IEEE Conference on Computer Vision and Pattern Recognition. [S.I.] : IEEE Press,2018:127-135.   
[24] Singer A.Angular synchronization by eigenvectors and semidefinite programming [J].Applied & Computational Harmonic Analysis,2011, 30 (1): 20-36.   
[25] Singer A, Shkolnisky Y.Three-dimensional structure determination from common lines in cryo-EM by eigenvectors and semidefinite programming [J]. SIAM Journal on Imaging Sciences,2011,4 (2): 543- 572.   
[26] Arrigoni F,Rossi B,Fusiello A. Spectral synchronization of multiple views in SE (3)[J]. SIAM Journal on Imaging Sciences,2016,9(4): 1963-1990.   
[27] Eriksson A,Olsson C,Kahl F,et al. Rotation averaging with the chordal distance: Global minimizers and strong duality[J].IEEE Trans on Pattern Analysis and Machine Intelligence,2019,43 (1): 256-268.   
[28] Jbilou K.An Arnoldi based algorithm for large algebraic Riccati equations [J]. Applied Mathematics Letters,2006,19 (5): 437-444.