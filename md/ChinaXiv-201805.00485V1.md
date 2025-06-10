# 基于方差最大化旋转变换的K近邻故障诊断策略“

张成，郭青秀，李元(沈阳化工大学 技术过程故障诊断与安全性研究中心，沈阳 110142)

摘要：为了提高FD-KNN 针对潜隐变量在非线性和多模态过程中的故障检测能力，提出一种基于方差最大化旋转变换的K近邻故障检测与诊断策略。首先，通过方差最大化方法建立旋转变换将原始数据变换到新的正交空间；接下来在该正交空间中执行FD-KNN方法进行故障检测；最后，结合贡献图方法给出基于贡献图的故障诊断策略。通过一个非线性模拟实例，证明方法对潜隐变量故障诊断是有效的;同时，在典型非线性工业过程田纳西过程进行测试，与PCA、FD-KNN和PC-KNN等方法进行对比，实验结果进一步证明了方法的有效性。

关键词：K近邻；方差最大化旋转；故障检测；故障诊断；过程控制；主元分析中图分类号：TP277 doi:10.3969/j.issn.1001-3695.2018.02.0139

Varimax rotationbased K nearest neighbors fault diagnosis strategy

Zhang Cheng, Guo Qingxiu, Li Yuan+ (Shenyang UniversityofChemical TechnologyResearch CenterforTechnical ProcessFaultDiagnosis&Safety,SheYang 110142, China)

Abstract:Aimingto improvethfaultdetectionabilityofFD-KNNinthenonlinearandmultimodalprocess,this paperproposes a $\mathbf { k }$ nearest neighbors fault detection method based on varimax rotation (Rot-KNN).First,implement varimax rotation in observeddatasettoobtainanorthogonalspace.Next,implementFD-KNNintheneworthogonalspacetodetectfaults.Atlast, proposeafault diagnosis strategy basedoncontributionchart.Anonlinear simulation exampleandthe TennesseeEastman (TE) processesofatypicalnonlinear industrialprocessprovethatthemethodis efectiveforthelatentvariablefaultdiagnosis.The experimental results indicate that the proposed method outperforms the PCA,FD-KNN and PC-KNN.

Key words:K nearestneighbors;varimaxrotation;fault detection;fault diagnosis；processcontrol;principal component analysis

# 0 引言

随着工业生产的快速发展，过程监视与故障诊断技术在保证生产安全、提高生产效率等方面的作用变得越来越重要。由于分布式控制系统可以自动测量和存储大量的多变量采样数据，因此基于数据驱动的多元统计过程控制(multivariablestatisticalprocess control,MSPC)方法已经成为当今研究的热点问题[1]。而由于现代生产工艺过程的机械化、电气化、自动化和化学化等特点，大量复杂工业过程具有非线性和多模态特征，典型的有：青霉素发酵过程，半导体铝蚀刻工艺过程，TennesseeEastman(TE)过程，高分子聚合过程和废水处理过程等[2\~6]。

主元分析(principal component analysis,PCA）作为一种典型的、基于数据驱动的多元统计过程控制方法，已经被广泛地应用在化工生产过程中并且取得了可喜的成果[7-9]。PCA方法依据方差信息通过线性变换将原始空间分解成主元子空间(principal component subspace,PCS)和 残差子空间(residualsubspace,RS)，同时应用Hotelling'sT²和平方预测误差(squaredpredictionerror,SPE)两个统计量实现对上述两个子空间的状态监控。T和SPE控制限通常在假设过程变量服从多元高斯分布的前提下进行确定，这将影响PCA方法在非线性过程的故障检测性能[10]。为了解决非线性过程的监控问题，一些基于PCA 的非线性方法已经被提出，同时获得了快速发展[11-12]。近些年，基于核理论的主元分析(kernel principal component analysis,KPCA)方法已经有效地被用于解决非线性系统的过程监控问题[13"15]。为了刻画过程数据的动态特性和进行相关的应用分析，通过增广时间序列变量来扩大数据矩阵进而将其自相关特性纳入到相应的增广矩阵中，形成了动态主元分析（dynamicPCA,DPCA）方法[16-17]。DPCA 是一种将传统 PCA 推广到动态多变量过程的方法，由于考虑了数据中的序列相关性，因此在含有时滞系统的故障诊断中具有良好的表现。

上述方法，如PCA和KPCA，适用于监控单模态过程；将其应用于多模态过程通常存在较高的误报情况[18]。为了监视多模态过程，He 等提出一种基于 $k$ 最近邻故障检测方法(faultdetectionbased on K-nearest neighbors,FD-KNN)[19]。FD-KNN 方法应用当前样本与其近邻的距离相似度度量当前样本状态，因此变量的尺度变换是首要考虑的问题。通常FD-KNN与Z-score 标准化方法结合使用，通过Z-score方法调节监控变量尺度来提高FD-KNN的检测性能。然而，当样本具有较高维数时，FD-KNN需要统计高维数据的距离，这将产生大量的时间消耗，同时对存储空间也提出更高的要求。针对上述缺陷，He 等提出一种基于PCA和FD-KNN 相结合的检测方法（principal component-basedKnearestneighbor rule for fault detection，PC-KNN）[20]。首先，应用PCA获得主元子空间；接下来，在主元子空间中执行FD-KNN方法。PC-KNN在低维主元子空间中计算样本间距离，这将降低距离计算的复杂度，同时提高计算效率。然而，PC-KNN方法只检测发生在主元子空间的故障；当故障完全发生在残差子空间时，PC-KNN方法是无效的。综上，相对检测结果而言，PC-KNN不具有优于FD-KNN的检测性能。

考虑到PC-KNN方法的上述缺陷及FD-KNN处理非线性和多模态过程的优势，结合具有非线性和多模态特征的典型工业过程，本文提出一种基于方差最大化旋转变换的k近邻故障检测与诊断策略(varimaxrotation -basedk nearest neighbors faultdetectionand diagnosis strategy,Rot-KNN)。方差最大化旋转是在PCA中使用的一种方法。它通过坐标变换使各个因子载荷的方差之和最大，同时将负载矩阵旋转到尽量接近简单结构。相比PC-KNN方法，Rot-KNN虽然计算负载增大，但其能够使得故障检测结果更全面，不存在PC-KNN在残差子空间故障检测方面的缺陷；相比FD-KNN方法，Rot-KNN可以提高对潜隐变量故障的检测能力；相比PCA、KPCA和DPCA等方法，Rot-KNN方法能够有效处理具有非线性、多模态等特征的过程监控问题，能够提高过程故障检测率(faultdetectionrate,FDR)、降低误报率(false alarm rate,FAR)。

# 1 FD-KNN

FD-KNN方法的基本原理是使用样本与其近邻的距离度量样本之间的差异。首先，在训练集中查找样本 $X$ 的前 $k$ 个近邻$X \left\{ X ^ { ( 1 ) } , X ^ { ( 2 ) } , \cdots , X ^ { ( K ) } \right\}$ 。其次，计算 $X$ 与其前 $k$ 个近邻样本的距离平方和:

$$
D ^ { 2 } = \sum _ { i = 1 } ^ { k } d _ { i } ^ { 2 }
$$

其中: $d _ { i }$ 为样本 $X$ 与其第 $i$ 近邻 $\boldsymbol { X } ^ { ( i ) }$ 的欧式距离。最后，根据非中心的卡方分布，确定置信度为 $\alpha$ 的检测控制限 $D _ { \alpha } ^ { 2 } { [ 2 1 ] }$ 由于核密度估计(kernel density estimation,KDE)方法是一种典型的无参数分布估计方法，已经取得了良好的效果[22-26]，因此，$D _ { \alpha } ^ { 2 }$ 也可以应用KDE 方法进行确定。当待检测样本的 $D ^ { 2 }$ 大于控制限 $D _ { \alpha } ^ { 2 }$ 时判定其为故障样本，否则判定其为正常样本。FD-KNN具体计算过程如下。

1)离线建模  
a)在训练集 $X$ 中查找每个样本 $x$ 的前 $k$ 个近邻样本；b)应用式（1）计算 $x$ 与 $k$ 近邻距离 $D ^ { 2 }$ ：  
c)确定训练模型的控制限 $D _ { \alpha } ^ { 2 }$ （20  
2)在线检测  
a)在训练集 $X$ 中寻找待检测样本 $x _ { * }$ 的前 $k$ 个近邻样本;b)利用式（1）计算 $x _ { * }$ 与 $k$ 近邻距离 $D _ { * } ^ { 2 }$ ·

c)将 $D _ { * } ^ { 2 }$ 与控制限 $D _ { \alpha } ^ { 2 }$ 比较，若 $D _ { * } ^ { 2 } > D _ { \alpha } ^ { 2 }$ 判 $x _ { * }$ 为故障，否则 $x _ { * }$ 为正常。

由于变量尺度与量纲差异影响，通常在过程监控之前对采样数据需要进行有效的标准化处理。Z-score是一种常用的数据预处理方法，通过调整变量的均值与方差，能够使不同量纲变量在同一尺度下进行比较。因此，通常将 $Z$ -score与监控方法结合使用，提高经典算法对过程的监控能力，例如FD-KNN,PCA和KPCA等。

Z-score与FD-KNN相结合的方法对变量相互独立的过程进行监控是有效的。假设数据集包含两个测量变量 $x _ { 1 } = t , x _ { 2 } = s$ 且$s \sim N ( 0 , 1 6 ^ { 2 } ) , t \sim N ( 0 , 1 ^ { 2 } )$ 。随机生成 200 个训练样本和两个故障样本 $\mathrm { F } _ { 1 }$ 和 $\mathrm { F } _ { 2 }$ ，其散点图如图1(a）所示。故障样本Fi和 $\mathrm { F } _ { 2 }$ 分别沿 $s$ 和 $t$ 方向偏离数据中心，故障尺度为4倍标准差长度，例如 $\mathrm { F } _ { 1 } ( 6 4 , 0 ) , \mathrm { F } _ { 2 } ( 0 , 4 )$ ．应用Z-score方法对上述数据集进行标准化处理，其结果如图1(b）所示。可以看出，在标准化后数据集中故障样本与训练样本分离；同时，FD-KNV方法能够准确识别出上述两个故障， $D ^ { 2 }$ 的检测结果如图2所示。

![](images/356c1b7c61bd34c84f491f4c7866474583d2512bfafb73623a1692d7af8de06e.jpg)  
图1数据散点图

![](images/c87a28dc709bd5da12a96823b34c84bcef72181bd86f566114a3417127619471.jpg)  
图2 D²控制图

上述例子中变量 $x _ { 1 }$ 和 $x _ { 2 }$ 是相互独立的，因此Z-score 与FD-KNN相结合的方法具有较好的检测结果。但当变量之间存在相关性时，对于微弱故障而言，上述方法通常存在局限性。例如数据集的两个测量变量满足如下关系：$\left\{ { \begin{array} { l } { x _ { 1 } = s \cos ( \theta ) + t \sin ( \theta ) } \\ { x _ { 2 } = - s \sin ( \theta ) + t \cos ( \theta ) } \end{array} } \right.$ ，其中0=π/ $\theta = \pi _ { \mathit { \Delta } }$ 4， ，数据集的分布如图3所示。

# 2 基于方差最大化旋转变换的 $\boldsymbol { \mathsf { k } }$ 近邻故障检测与诊 断策略

# 2.1基于方差最大化的旋转变换

设随机向量 $\mathbf x = [ \mathbf x _ { 1 } , \mathbf x _ { 2 } , \cdots , \mathbf x _ { \mathbf n } ]$ 包含 $n$ 个随机变量，其协方差矩阵 $\Sigma = \mathbf { E ( x ^ { T } x ) } , \ \lambda _ { i } \setminus \pmb { p } _ { i } \ ( i = 1 , 2 , \cdots , n )$ 分别为 $\pmb { \Sigma }$ 的特征值和特征向量且 $\lambda _ { i }$ 按降序排列。

考虑线性变换：

$$
\mathbf { y } = \mathbf { x } \mathbf { P }
$$

其中 $\mathbf { y } = [ \mathbf { y } _ { 1 } , \mathbf { y } _ { 2 } , \cdots , \mathbf { y _ { n } } ]$ ， $\mathbf { P } { = } [ \mathbf { p } _ { 1 } , \mathbf { p } _ { 2 } , \cdots , \mathbf { p _ { n } } ]$ 是一个正交矩阵。

可以看出，随机变量 $y _ { i }$ 的方差和 $y _ { i }$ 与 $y _ { j } \ ( i \neq j )$ 的协方差分别为

$$
V a r ( y _ { i } ) = E ( y _ { i } ^ { T } y _ { i } ) = \lambda _ { i }
$$

将Z-score与FD-KNV相结合的方法应用在当前数据集时，检测结果如图4所示。可以看出，故障2被误检为正常点。产生这种错误结果的主要原因是Z-score方法被应用在观测变量的上，观测变量的标准化并不能同步标准化变量 $s$ 和 $t$ 。如果沿着 $s$ 和t对数据进行标准化，则两个故障均能被FD-KNN 检测到。就上例而言，如果按照数据分散程度建立新的坐标体系，然后沿新的方向进行标准化处理，可以提高FD-KNN的检测能力。

![](images/a877981fc72ff67c4ba86a8c7c21dd2a559af52ce3fd15709ed4d37c0603f00a.jpg)  
图3数据散点图

![](images/8480e622fe6feeed364d9e4a4c9d0dd530b35b2f490f4e231f06b5008a36c8c0.jpg)  
图4 $\mathrm { D } ^ { 2 }$ 控制图

$$
C \mathrm { o v } ( y _ { i } , y _ { j } ) = \mathbf { p } _ { i } ^ { T } \mathbf { \Sigma } \mathbf { p } _ { j } = 0
$$

由式（3）（4）可知， $y _ { i }$ $y _ { i } ( i { = } 1 , 2 , \cdots , n )$ 的方差是按照降序排列的;新的互异随机变量yi与y;的协方差为0，即yi与yj是不相关的。由文献[1,2]可知， $y _ { i } ( i = 1 , 2 , \cdots , n )$ 代表数据变异性最大的方向，同时其协方差矩阵$\Lambda = \bf d i a g \{  { \lambda _ { 1 } , } { \lambda _ { 2 } , } \cdots , { \lambda _ { n } }  \}$ 具有一个简单但是精炼的对角结构

# 2.2基于方差最大化旋转变换的 $\mathsf { K }$ 近邻故障检测与诊断策略

设训练数据集为 $X _ { \boldsymbol { m } \times \boldsymbol { n } }$ ，其中 $m$ 和 $n$ 分别为样本数量和监控变量数量。首先计算 $X _ { \boldsymbol { m } \times \boldsymbol { n } }$ 的协方差矩阵 $\Sigma$ 并将 $\Sigma$ 进行特征分解，记 $\pmb { \Sigma }$ 的特征值与特征向量分别为 $\lambda _ { i } \setminus \pmb { p } _ { i }$ $( i = 1 , 2 , \cdots , n )$ ，且 $\lambda _ { i }$ 降序排列。接下来，依据公式（2）将 $X$ 作旋转变换$Y = X P$ 并将 $Y$ 进行标准化处理，标准化数据集记为$\overline { { Y } } = Y L ^ { { - I / 2 } }$ 。最后，应用FD-KNN方法在数据集 $\bar { Y }$ 上进行故障检测。对数据集沿着正交且变异性大的方向依次进行标准化处理，然后应用FD-KNN方法进行故障检测，可以提高FD-KNV的故障检测率。

Rot-KNN具体过程如下。

# 1)模型建立

a)对训练集 $X$ 进行中心化处理;b)将 $X$ 的协方差矩阵 $\Sigma$ 进行特征分解；c)作旋转变换 $Y = X P$ 并将 $Y$ 进行标准化，获得中心化矩阵 $\bar { Y }$ ;d)在 $\bar { Y }$ 上执行FD-KNN方法并根据KDE方法确定统计控制限D 。

# 2)在线检测

对于一个测试样本 $x _ { t e }$ 执行以下步骤进行故障检测。

a)将 $x _ { t e }$ 依据模型建立中第 $\textcircled{1}$ 步的均值进行中心化处理;

b)作旋转变换 $y _ { t e } = x _ { t e } P$ 并按照模型建立中第 $\textcircled{3}$ 步将 $y _ { t e }$ 进行标准化，结果记为 $\overline { { y } } _ { t e }$ ；

c）在 $\bar { Y }$ 中查找 $\overline { { y } } _ { t e }$ 的 $\mathbf { k }$ 近邻样本并计算距离统计值 $D _ { t e }$ ：

d)比较 $D _ { t e }$ 与 $D _ { \alpha } ^ { 2 }$ ：若 $D _ { t e } > D _ { \alpha } ^ { 2 }$ ，则 $x _ { t e }$ 为故障样本；否则， $x _ { t e }$ 为正常样本。

当一个样本被检测为故障时，执行相应的诊断方法分析故障产生的原因是必要的。在经典的方法中，如PCA和KPCA,通常应用贡献图的方法进行故障诊断[27-29]。对于一个已被中心化样本 $\mathbf { x } = [ x _ { 1 } , x _ { 2 } , \cdots , x _ { n } ]$ ,经过基于方差最大化旋转变换后变换成 $\mathbf { y } = [ y _ { 1 } , y _ { 2 } , \cdots , y _ { n } ]$ ，其中 $y = x P$ 。样本 $\mathbf { x }$ 的统计指标$D ^ { 2 }$ 可以通过式(5)进行计算。

$$
\begin{array} { r l } { D ^ { 2 } } & { { = } { \displaystyle \sum _ { j = 1 } ^ { k } } \Big \| ( { \overline { { \mathbf { y } } } } - { \mathbf { \overline { { y } } } } ^ { ( j ) } ) \Big \| ^ { 2 } } \\ & { { = } { \displaystyle \sum _ { j = 1 } ^ { k } } \Big \| ( { \mathbf { y } } - { \mathbf { y } } ^ { ( j ) } ) { \mathbf { A } } ^ { - 1 / 2 } \Big \| ^ { 2 } } \\ & { { = } { \displaystyle \sum _ { j = 1 } ^ { k } } \sum _ { i = 1 } ^ { n } ( y _ { i } - y _ { i } ^ { ( j ) } ) ^ { 2 } / \lambda _ { i } } \end{array}
$$

其中: $\overline { { \boldsymbol y } } ^ { ( j ) }$ 为 $\overline { { y } }$ 的第 $j$ 近邻样本。于是，变量 $y _ { h }$ 对 $D ^ { 2 }$ 的贡献可以整理成

$$
c o n _ { h } = \sum _ { j = 1 } ^ { k } ( y _ { h } - y _ { h } ^ { ( j ) } ) ^ { 2 } / \lambda _ { h }
$$

若样本 $x$ 已经被检测为故障且 $c o n _ { h } > D ^ { 2 } / n$ 时，确定 $y _ { h }$ 为经过坐标旋转后的失控变量。

由于 $y _ { h } = x p _ { h } = \sum _ { i = I } ^ { n } x _ { i } p _ { i , h }$ 和 $y _ { h } ^ { ( j ) } = x ^ { ( j ) } p _ { h } = \sum _ { i = I } ^ { n } x _ { i } ^ { ( j ) } p _ { i , h }$ ，其中 $p _ { h } ^ { T } = [ p _ { 1 , h } , p _ { 2 , h } , \cdots , p _ { n , h } ]$ ，因此，式(6)可以整理成如下形式，

$$
\begin{array} { r l } { c o n _ { h } } & { = \displaystyle \sum _ { j = 1 } ^ { k } \Biggl ( ( y _ { h } - y _ { h } ^ { ( j ) } ) \frac { n ^ { \frac { p } { 2 } } } { \sum _ { i = 1 } ^ { k } } ( x _ { i } - x _ { i } ^ { ( j ) } ) p _ { i , h } \Biggr ) / \lambda _ { h } } \\ & { = \displaystyle \sum _ { i = 1 } ^ { n } \Biggl ( \sum _ { j = 1 } ^ { k } ( y _ { h } - y _ { h } ^ { ( i ) } ) ( x _ { i } - x _ { i } ^ { ( j ) } ) p _ { i , h } \Biggr ) / \lambda _ { h } } \\ & { = \displaystyle \sum _ { i = 1 } ^ { n } \Biggl ( x _ { i } \cdot \sum _ { j = 1 } ^ { k } \bigl ( ( y _ { h } - y _ { h } ^ { ( j ) } ) p _ { i , h } / \lambda _ { h } \bigr ) \Biggr ) } \\ & { \cdot \displaystyle \sum _ { i = 1 } ^ { n } \Biggl ( \sum _ { j = 1 } ^ { k } \bigl ( ( y _ { h } - y _ { h } ^ { ( i ) } ) x _ { i } ^ { ( j ) } p _ { i , h } / \lambda _ { h } \bigr ) \Biggr ) } \end{array}
$$

由式(7)可得，变量 $x _ { l }$ 对 $y _ { h }$ 的贡献为

$$
C o n _ { l . h } ^ { } = x _ { l } \cdot \sum _ { j = 1 } ^ { k } \Bigl ( ( y _ { h } - y _ { h } ^ { ( j ) } ) p _ { l , h } / \lambda _ { h } \Bigr )
$$

若经过式(6)计算存在 $s$ 个失控变量 $\hat { y } _ { h }$ $( h = 1 , 2 , \cdots , s )$ ，则原 始变量 $x _ { l }$ 贡献为

$$
C _ { l } = \sum _ { s } \mathopen { } \mathclose \bgroup \left| C o n _ { l . h } \aftergroup \egroup \right|
$$

在故障诊断过程中，通常认为具有较大贡献的变量的异常变化是引起故障发生的主要原因。

# 1)故障诊断

假设 $\boldsymbol { x } = [ x _ { 1 } , x _ { 2 } , \cdots , x _ { n } ]$ 为一个故障样本，$y = [ y _ { 1 } , y _ { 2 } , \cdots , y _ { n } ] = x P$ ，具体诊断过程如下。

a)根据式（6）计算变量 $y _ { i } ( i { = } 1 , 2 , \cdots , n )$ 对 $D ^ { 2 }$ 的贡献$c o n _ { i }$ ，并判定失控变量数目 $s$ ：

b)根据式（8）计算变量 $x _ { i }$ $( i = 1 , 2 , \cdots , n )$ 对 $s$ 个失控变量的贡献 $C o n _ { i . j }$ ， $j = 1 , 2 , \cdots , s$ ：

c)根据式（9）计算 $x _ { i }$ $\mathbf { \Phi } _ { i } ( i = 1 , 2 , \cdots , n )$ 的总贡献 $C _ { i }$ ：

d)比较 $C _ { i }$ $( i = 1 , 2 , \cdots , n )$ 。通常较大的 $C _ { i }$ 所对应的变量$x _ { i }$ 为异常变量。

# 3 仿真实验

# 3.1数值例子

本例将通过一个包含4个观测变量的非线性实例验证本文方法的有效性，具体模型如式（10）所示。

$$
\left\{ \begin{array} { l l } { x _ { 1 } } & { = 5 s - t } \\ { x _ { 2 } } & { = 3 s + t } \\ { x _ { 3 } } & { = e ^ { 0 . 2 s } + t ^ { 2 } } \\ { x _ { 4 } } & { = s ^ { 5 } } \end{array} \right.
$$

其中:潜隐变量 $^ { s , t }$ 分别在区间[-50,50]和[0,1]上服从均匀分布。

由模型式（10）随机生成500个样本构成训练集；随机生成100个样本用于校验不同方法的有效性。通过调整潜隐变量$t$ 的初始值，设置两类故障，相对于变量 $t$ 的均匀分布，第二类故障较第一类故障具有更大的偏离尺度。图5给出上述样本的潜隐变量 $\mathbf { \alpha } _ { s , t }$ 分布情况，同时图6给出各个变量$x _ { i }$ 0 $\overset { \cdot } { l } = 1 , 2 , \cdots , 4 )$ 的分布情况。

首先，执行传统的FD-KNN方法进行故障检测，经过寻优测试，近邻数 $k { = } 5$ 。在检测之前，应用Z-score方法对数据集进行标准化处理，检测结果如图7所示。可以看出，FD-KNN方法不能有效检测第一类故障。由图5和6可以看出，第一类故障在潜隐变量 $t$ 的方向发生微弱偏移，但这种偏移在观测变量$x _ { i }$ 0 $( i = 1 , 2 , \cdots , 4 )$ 上并没有直观表现；换句话说，单从观测变量的角度进行观察，第一类故障样本更像一组正常的样本。因此，沿着观测变量 $x _ { i }$ 1 $( i = 1 , 2 , \cdots , 4 )$ 执行Z-score 方法，并不能提高FD-KNN的检测性能。

![](images/a6d5d8af29a51087e0891357b130bac20ac4b2a5e2a8c50f0c6d138c8cbff995.jpg)  
图5s,t变量 $^ { s , t }$ 散点图

![](images/8e104b3e0b73cfbd0bcd1458367400714155752f40616253e545acdd7dffa939.jpg)  
图6变量 $\scriptstyle x _ { i } ( \mathrm { i = } 1 , 2 , \ldots , 4 )$ 分布

![](images/10d69cf54b08b9fdc182ff34ad3f9a7eee56b6e10cedca982790179e193deaad.jpg)  
图7FD-KNN检测结果

接下来，Rot-KNN方法在本例中被执行，同时将其检测结果与FD-KNN方法进行比较。首先将观测数据集进行中心化处理。然后，对中心化数据执行基于方差最大化的旋转变换，获得变换后的新的数据集，已被标准化的各个变量分布如图8所示。由变量 $y _ { 4 }$ 可以看出，第一类故障已经偏离了正常轨迹。接下来在旋转后的数据集上执行FD-KNN方法，检测结果如图9所示。可以看出，两类故障完全被检测；同时从故障尺度观测，故障2 具有大于故障1的故障尺度，这与初始化设置是一致的。

![](images/80d0fa66f1b2bbb98be93be6aae287ccc14a22f99c9ba5428066a63d10cdb038.jpg)  
图8变量yi(i=1,2...,n)分布

![](images/4bfa6b6c4d712ecbd733d57b920cfef602216a5ebfb0c821385290a90ba3b4d2.jpg)  
图9.Rot-KNN检测结果

在本例中根据Rot-KNN的故障检测结果，分别对两个故障样本（两类故障中的第50个样本）进行了诊断分析。首先根据式（6）确定经过旋转变换后第四个变量 $y _ { 4 }$ 为失控变量，如图（10）所示。接下来，应用公式（7）计算原始变量对失控变量的贡献，贡献图如图（11）所示。可以看出，对于上述两个故障，原始变量 $x _ { 1 }$ 和 $x _ { 2 }$ 对失控变量 $y _ { 4 }$ 具有较大贡献，因此可以推断出变量 $x _ { 1 }$ 和 $x _ { 2 }$ 的异常变化引起这两个故障的发生。事实上，由模型(10)可知，潜隐变量 $t$ 的异常变化可以通过变量 $x _ { 1 }$ 和 $x _ { 2 }$ 的线性组合来确定，因为三者满足如下关系$8 t = 5 x _ { 2 } - 3 x _ { 1 } \mathrm { ~ } \circ$ （20

Contr of yi to D²,i=123 4 y4 cninin 105 y4 y1 y2 100 L y1 y2 2

![](images/53eb0ea35173227971fa48741c08131a1e60dde90081d8a56e4528dbd0b06690.jpg)  
图10yi的贡献：1.故障1中第50个样本；2.故障2中第50个样本

为了与Rot-KNN方法进行对比分析，传统的PCA- $\cdot \mathrm { T } ^ { 2 }$ 、PCA-SPE 和PC-KNN等方法分别对本例进行了故障检测。首先，根据方差累计贡献率（ $C P V = 9 0 \%$ ），2个主元被选取，同时将原始空间分成主元子空间和残差子空间。图12给出PCA- $\cdot \mathrm { T } ^ { 2 }$ 、PCA-SPE 的检测结果。结合两个子空间的检测结果，可以发现只有第二类故障被检测出来，说明上述方法对大尺度故障是有效的。第一类故障没有被检测出来的主要原因是 $\mathrm { T } ^ { 2 }$ 和 SPE 两个统计量控制限的确定过程通常假设变量服从多元高斯分布，而本例中变量并不满足服从多元高斯分布的假设，如图13所示。在上述主元子空间，执行FD-KNN方法，即PC-KNN,检测结果如图14所示。PC-KNN方法监控样本在主元子空间的变化，并没有考虑样本在残差子空间的变化。因此，当故障发生完全发生在残差子空间时，PC-KNN通常具有较高的误报率，检测结果证实了这一点。

![](images/af3a9a3933654876c93dbca7d638f1cad265d1074b7d6fcb50ac03ffba41a38b.jpg)  
图 $1 1 \mathrm { \ x _ { i } }$ 的贡献：1.故障1中第50个样本；2.故障2中第50个样本  
图12PCA $\cdot \mathrm { T } ^ { 2 }$ 、PCA-SPE 检测结果

![](images/e36cff919e8d0c1498e5aa73185fb8611850030ec254f2ffd1a4b8a0db1f7c64.jpg)  
图 $1 3 \ \mathrm { x _ { i } }$ 高斯分布统计

![](images/78524984f5f52d7c08b67e14af90b4c0285c766dff3db487c24e1a296af6ada8.jpg)  
图14PC-KNN检测结果

# 3.2 TE过程

TE过程是Downs等人基于TennesseeEastman化学公司实际化工生产过程提出的一个仿真系统[30]。TE 仿真系统对单元操作间的非线性关系和物料与能量平衡以及汽、液相平衡规律进行了准确的设计,对于化工过程的各类真实故障实现了模拟。由于整个系统各部分之间耦合严重、高度非线性且开环不稳定，在过程控制技术、过程监控和优化以及过程运行系统集成的基础平台的研究领域中得到了广泛的应用[31]。如图15所示，TE过程包含五个操作单元：反应器、冷凝器、循环压缩机、分离器和汽提塔；包含四种气体原料A、C、D和E,两种液态产物G和H,还包含副产物F和惰性气体B.整个过程共包含22个连续过程测量变量、19个成分测量变量和11个控制变量。TE过程是一个常用的标准问题(benchmarkproblem),其较好地模拟了实际复杂工业过程系统的许多典型特征，因此被作为仿真例子广泛应用于控制、优化、过程监控与故障诊断的研究中[32-34]。

![](images/9582099f93cc1cb15f3eaeea01b67753504c7167814ec4ab350abbe3ebf845ff.jpg)  
图15TE过程

TE 仿真系统通过3分钟采样间隔不仅能够模拟正常操作环境，同时还可以模拟21种故障环境[27]。在本节中，依据文献[36],选取33个变量对故障进行分析；960个正常样本被用于建立模型；480个正常样本被用于模型校验；每种故障包含960个样本，同时故障于161时刻被引入并持续到过程结束。

如文献[35]介绍，由于故障3,9和15的故障尺度较小且整个过程表现平稳，因此各种方法均不能有效检测以上过程故障；PCA- $\cdot \mathrm { T } ^ { 2 }$ ，PCA-SPE和FD-KNN等方法可以及时准确地检测故障1、2、6、7、8、12、13和14，且故障检测率达到 $9 5 \%$ 以上；基于PCA的不同方法，如KPCA和DPCA，对故障5、10、16和19的故障检测率均低于 $8 5 \%$ 。在本节中，将Rot-KNN对故障5、10、14、16和19进行检测和诊断并与PCA- $\cdot \mathrm { T } ^ { 2 }$ ，PCA-SPE，FD-KNN等方法进行对比分析，相关参数设置见表1，各种方法的故障检测率和误报率见表2。由表2可以看出，对于故障14，Rot-KNN方法同样具有良好的检测性能，故障检测率达到 $100 \%$ ，同时故障误报率低于其他方法；对于故障5、10、16和19，Rot-KNN的故障检测率高于 $90 \%$ ，而其他方法的故障检测率均低于 $6 0 \%$ 。图16给出Rot-KNN与FD-KNN关于故障5、10、16和19的故障检测控制图。

表1参数设置

<html><body><table><tr><td colspan="3"></td></tr><tr><td></td><td>主元数(PCs) 16</td><td>近邻数(k)</td></tr><tr><td>PCA FD-KNN</td><td></td><td>3</td></tr><tr><td>Rot-KNN</td><td></td><td>3</td></tr><tr><td></td><td>表2各种方法故障检测率与误报率（FDR/FAR)</td><td></td></tr><tr><td colspan="3"></td></tr><tr><td>Fault</td><td>PCA-T² PCA-SPE</td><td>FD-KNN Rot-KNN</td></tr><tr><td rowspan="2">5</td><td>30.13 30.75</td><td>27.13 100.00</td></tr><tr><td>/1.88 /4.38 /0.00</td><td>/0.05</td></tr><tr><td>49.25 10</td><td>55.88 45.00</td><td>90.63</td></tr><tr><td>/1.88 99.63</td><td>/3.13</td><td>/0.63 /0.10</td></tr><tr><td>14</td><td>100.00</td><td>100.00 100.00</td></tr><tr><td>/0.63</td><td>/3.75</td><td>/0.93 /0.63</td></tr><tr><td>35.75 16</td><td>53.13</td><td>33.00 92.38</td></tr><tr><td>/17.50</td><td>/8.13 /6.88</td><td>/3.75</td></tr><tr><td rowspan="2">20.63 19 /0.63</td><td>35.50</td><td>13.88 91.38</td></tr><tr><td>/1.88</td><td>/0.00 /1.25</td></tr></table></body></html>

在本节中，应用基于贡献图的故障诊断策略对上述故障进行了诊断，诊断结果如图17所示。由于本文方法与其他方法均能有效检测故障14，因此首先对故障14进行故障诊断，校验本文方法的有效性。故障14发生的主要原因是反应器冷却水阀门被粘住。该类型故障直接引起反应器温度 $\left( x _ { 9 } \right)$ 、反应器冷却水出口温度 $( x _ { 2 1 } )$ 和反应器冷却水流量（ $_ { ( x _ { 3 2 } ) }$ 的异常变化[29]。图17(a)给出本文方法对故障14的诊断结果。可以看出变量 $x 9$ X21， $x _ { 3 2 }$ 对统计量 ${ \bf D } ^ { 2 }$ 贡献显著，这说明本文诊断结果与上述分析相一致，验证了本文诊断方法的有效性。接下来，对故障5、10和16（本文方法具有较高检测率）进行故障诊断，图17（b-d)给出各类故障诊断贡献图。冷凝器冷却水入口温度异常变化引起故障5的发生，这将直接影响冷凝器冷却水出口温度 $\left( x _ { 3 3 } \right)$

和汽提塔下溢 $( x _ { 1 7 } )$ 的测量。上述结论通过故障5的诊断结果（图17（b））得到证实。进料C温度的异常变化引起故障10的发生，这将直接影响汽提塔下溢 $( x _ { 1 7 } )$ 和汽提塔温度（ $\cdot { x } _ { 1 8 }$ ）的正常测量，图17（c）给出故障10的诊断结果。图17（d）给出故障16的诊断结果。可以看出，故障16主要是由于汽提塔相关变量的异常变化所引起的，如汽提塔下溢 $( x _ { 1 7 } )$ 、汽提塔温度 $_ { ( x 1 8 ) }$ 0和汽提塔气阀 汽阀 $\left( x _ { 3 1 } \right)$ .换句话说，该类型故障主要发生在制过程中。 1。

![](images/19f1715d2559ae196594ad9ecd438df30b997d0d4d1b1f5a9508a85b1e2afbc5.jpg)  
(a)故障14

![](images/8d2be8a3bc4a98e156fd0e29b5e31987794d840acd6e945c71e37b0b42a8cc1f.jpg)  
(b)故障5

0 -NN0 100 200 300 400500600 7008009001000 Sample 2000 1 100 200 300 400 500600700 800 1000 Sample (a)故障5 MVMu 1002003004005006007008009001000 Sample 400 1002003004005006007008009001000 Sample (b）故障10 Ayhn 1002003004005006007008009001000 Sample 300 200 1002003004005006007008009001000 Sample (c）故障16 1000 -NN1Y 500 100 200 300 400 500600700 8009001000 Sample 200 150 O-NN N 400500600700 300 Sample (d)故障19

![](images/40e7555cf978252613a3341c931b593ff1807ff6c94c90f79b2bd962ff96fbd2.jpg)  
图16Rot-KNN与FD-KNN故障检测结果  
图17Rot-KNN故障诊断结果

# 4 结束语

本文为提高FD-KNN方法对潜隐变量故障的检测率，提出基于方差最大化旋转变换的k近邻故障检测方法，Rot-KNN。通过一个模拟实例和一个工业实例，与传统监控方法PCA、FD-KNN和PC-KNN进行对比，实验结果验证了本文方法的有效性。本文方法从检测性能上分析优于FD-KNN和PC-KNN，但是其具有较高的计算复杂性。因此，降低复杂的计算过程是本文方法的下一步研究问题。同时，关于近邻数 $k$ 的确定方法也是一个开放研究的问题，本文是通过交叉验证的方法确定近邻数，确定过程较为复杂。接下来在Rot-KNN方法中将重点研究近邻数的确定问题。

参考文献：   
[1]Qin S J. Statistical process monitoring: basics and beyond [J].Journal of Chemometrics,2010,17(8-9): 480-502.   
[2]Fan S K S,Lin S C,Tsai PF.Wafer fault detection and key step identification forsemiconductor manufacturing using principal component analysis, AdaBoost and decision tree [J].Journal ofthe Chinese Institute of Industrial Engineers,2016,33 (3):151-168.   
[3]Ringwood JV,Lynn S,Bacelli G,et al.Estimation and Control in Semiconductor Etch:Practiceand Possibilities[J].IEEE Transon Semiconductor Manufacturing,2010,23 (1): 87-98.   
[4]Wang Fan; Tan Shuai; Yang Yawei,et al.Hidden Markov model-based fault detection approach for multimode process [J]. Industrial& Engineering Chemistry Research,2016,55 (16).   
[5]Jayavani S,Deka H,Varghese TO,et al.Recent development and future trends in coir fiber - reinforced green polymer composites: Review and evaluation [J].Polymer Composites,2016,37(11): 3296-3309.   
[6]Katsoyiannis A,Samara C.Ecotoxicological evaluation of the wastewater treatment process of the sewage treatment plant of Thessaloniki, Greece [J]. Journal ofHazardous Materials,2007,141(3): 614.   
[7]张成，李元．基于统计模量分析间歇过程故障检测方法研究[J].仪器 仪表学报,2013,34(9): 2103-2110.(Zhang Cheng,Li Yuan.Study on the fault-detection method in batch processbased on statistical pattrn analysis [J],Chinese Journal of Scientific Instrument,2013,34(9): 2103-2110.)   
[8]Shams MAB,Budman HM,DueverTA.Fault detection,identification and diagnosis using CUSUM based PCA[J]. Chemical Engineering Science, 2011,66 (20): 4488-4498.   
[9]JaffelI,Taouali O,Harkat MF,etal.Afault detection index using principal component analysis and mahalanobis distance [J].IfacPapersonline,2015, 48 (21): 1397-1401.   
[10]李元，燕亚运，唐晓初．基于局部模型的多阶段在线产品质量预测 [J]. 系统仿真学报,2016,28(4):966-971.(LiYuan,YanYayun,Tang Xiaochu Multi-stage online product quality prediction based on local model [J]. Journal of System Simulation,2016,28 (4): 966-971. )   
[11] JiaF,MartinEB,MorrisAJ.Non-linear principal componentsanalysis for process fault detection [J]. Computers & Chemical Engineering,1998,22 (12): S851-S854.   
[12] Turnip A,Hong K S,Jeong M Y. Real-time feature extraction of P300 component using adaptive nonlinear principal component analysis [J]. BioMedical Engineering OnLine,2011,10(1):83.   
[13]Le JM, Yoo C K,Sang WC,et al. Nonlinear process monitoring using kernel principal component analysis [J].Chemical Engineering Science, 2004,59(1): 223-234.

[14]Wang Huang，Yao Ma.Fault detection of batch processes based on multivariatefunctionalkernelprincipalcomponentanalysis[J]. Chemometrics& Intelligent Laboratory Systems,2015,149:78-89.

[15] Zhang, Yingwei. Enhanced statistical analysis of nonlinear processes using KPCA,KICA and SVM[J]. Chemical Engineering Science,2009,64 (5): 801-811.   
[16] Rato TJ,Reis MS.Advantage of using decorrelated residuals in dynamic principal component analysis for monitoring large-scale systems [J]. Industrial& Engineering Chemistry Research,2013,52 (38):13685-13698.   
[17] Rato T J, Reis M S.Fault detection in the Tennessee Eastman benchmark process using dynamic principal components analysis based on decorrelated residuals (DPCA-DR)[J]. Chemometrics& Intelligent Laboratory Systems. 2013,125 (7): 101-108.   
[18] Wang Guozhu; Liu Jianchang; Zhang Yingwei,et al.A novel multi - mode data processing method and its application in industrial process monitoring [J]. Journal ofChemometrics,2015,29(2): 126-138.   
[19] He Q P,Wang Jin.Fault detection using the $\mathbf { k }$ nearest neighbor rule for semiconductor manufacturing processes [J]. IEEE Trans on Semiconductor Manufacturing,2007,20 (4): 345-354.   
[20] He QP,Wang Jin.Principal component based k-nearest-neighbor rule for semiconductor process fault detection [Cl// Proc of American Control Conference.2008:1606-1611.   
[21] He QP,Wang Jin.Large-scale semiconductor process fault detection using a fast pattern recognition-based method [J].IEEE Trans on Semiconductor Manufacturing,2010,23 (2): 194-200.   
[22] Ma Hehe; Hu Yi; Shi Hongbo.Fault detection and identification based on the neighborhood standardized local outlier factor method [J]. Industrial & Engineering Chemistry Research,2013,52(6): 2389-2402.   
[23] Kano M, Sakata T,Hasebe S.Just-in-time statistical process control for flexible fault management [C]//Proc of Sice Conference.2010:1482-1485   
[24] Wang Guozhu; Liu Jianchang; Li Yuan,et al.Fault detection based on difusion maps and k nearest neighbor diffsion distanceoffeature space [J]. Journal of Chemical Engineering of Japan,2015,48 (9): 756-765.   
[25] Karunamuni R J,Alberts T.A generalized reflection method of boundary correction in kernel density estimation [J]. Canadian Journal of Statistics, 2010,33 (4):497-509.   
[26] Terrell G R,Scott DW. Variable Kernel Density Estimation [J].Annals of Statistics,1992,20(3): 1236-1265.   
[27] Miller P, Swanson R E, Heckler C E. Contribution plots: a missing link in multivariate quality control [J]. Applied Mathematics & Computer Science, 1998, 8, 775.   
[28] Westerhuis JA,Gurden SP,Smilde AK.Generalized contribution plots in multivariate statistical process monitoring [J]. Chemometrics& Intelligent Laboratory Systems,2000,51(1):95-114.   
[29] Huang Jian； Yan Xuefeng. Gaussian and non-gaussian double subspace statistical process monitoring based on principal component analysis and

independent component analysis [J].Industrial& Engineering Chemistry Research,2015,54,1015.

[30] Downs J,Vogel E F.A plant-wide industrial process control problem [J]. Computers& Chemical Engineering,1993,17(3):245-255.

[31]吴永建，袁德成，郭金玉．基于隐含马尔可夫模型的过程监视方法在 TE 过程中的应用[J].沈阳化工大学学报，2004,18(2):144-146.(Wu Yongjian,Yuan Decheng,Guo Jinyu.Application of process monitoring method based on hidden markovmodel in TE process [J].Journal of Shenyang University of Chemical Technology,2004,18 (2): 144-146)

[32] Ge Zhiqiang,Song Zhihuan.Nonlinear probabilistic monitoring based on the gaussian process latent variable model[J]. Industrial & Engineering

Chemistry Research,2010,49 (10): 4792-4799.

[33]Wang Jin,He QP.Multivariate statistical process monitoring based on statistics pattern analysis [J]. Industrial & Engineering Chemistry Research, 2010,49 (17): 7858-7869.

[34] Jia,Qilong; Zhang, Yingwei. Quality-related fault detection approach based on dynamic kernel partial least squares [J].Chemical Engineering Research & Design,2016,106:242-252.

[35]郭小萍，杨猛，李元．基于改进重构贡献图的故障定位方法[J].仪器 仪表学报,2015,36 (5): 1193-1200.(Guo Xiaoping,Yang Meng,Li Yuan. Fault location method based on improved reconstruction contribution map [J].Chinese Journal of Scientific Instrument,2015,36 (5):1193-1200)