# 改进随机子空间LDA结合多补丁集成学习的鲁棒人脸识别算法“

冯代高，张友俊

(上海海事大学 信息工程学院，上海 201306)

摘要：针对化妆对人脸识别准确率的负面影响，提出了基于补丁集成学习的改进鲁棒人脸识别算法。首先，将每张人脸图像嵌入补丁中并用一组特征描述符描述每个补丁，即本地梯度Gabor模式(LGP)、Gabor空间定序定比测量直方图(HGSFRM)和密集采样局部多值模式(DSLMP)。然后，使用改进的随机子空间线性判别分析(SRS-LDA)方法采样补丁，并在化妆之前和化妆之后图像之间建立多个公共子空间进行集成学习。最后，利用协作和稀疏表示分类器比较这个子空间中的特征向量，同时通过求和规则联合得到的分数。实验将提出的算法在多种化妆数据集上进行评估分析，结果表明提出的算法相比于其他专为妆后人脸识别设计的算法有更高的识别精度。

关键词：人脸识别；鲁棒评估；描述符算法；补丁集成；改进随机子空间 中图分类号：TP391.41 doi:10.3969/j.issn.1001-3695.2018.03.019C

# Robust face recognition algorithm based on multiple patch integration learning and improved random subspace LDA

Feng Daigao, Zhang Youjun (Collge OfInformation Engineering,Shanghai Maritime University，Shanghai 201306,China)

Abstract: Aimingatthenegativeefects ofmakeuponfacerecognition,this paperpresentsanimprovedrobustfacerecognition algorithmbasedonpatch integrationlearning.Inthepro-posed scheme,this papertesselates each faceimage intopatchesand represents each patch withasetoffeature descriptors,viz.,Local GaborPattern(LGP),HistogramofGaborSpaceFixedRati Measures (HGSFRM)and Densely Sampled Local Multi-valued Patern (DSLMP).Then,usesan improved Random Subspace Linear Discriminant Analysis (SRS-LDA)methodto perform ensemble learning bysampling patches and constructing multiple common subspaces betwee before-makeupand after-makeup facial images.Finallyuses Collborative-based and Sparsebased RepresentationClassifiers tocompare featurevectors inthissubspace and theresulting scores combined bythesum-rule. The proposed face matching algorithm is evaluatedon multiple makeup dataset.Results show that this algorithm has higher recognition accuracy than other algorithms designed for face recognition under makeup situation.

Keywords:facerecognition;robust evaluation;signatureintegrationalgorithm;patch integration;improvedrandomsubspace

# 0 引言

人脸自动识别已在诸如个人认证、视频监控和人机交互等领域广泛使用。人脸自动识别通过从输入的人脸图像中提取有识别力的特征并将这个特征与数据集中储存的模板进行比较来进行识别[1。随着鲁棒性特征表示和匹配技术的发展，人脸识别系统的准确度不断提高[2]，多个公开基准数据库上错误率的显著降低。

目前，人脸识别领域仍然存在许多挑战，特别是异构人脸识别。面部彩妆是一种非常常见的面部异构，妆容下的面部识别准确度极为重要。图1为彩妆应用效应的实例。但是近期的研究表明，面部彩妆后人脸的识别准确度存在较大的问题。由于化妆可能大幅改变容颜，从而给人脸自动识别提出了挑战。根据文献[3]所述，由于化妆的应用，商业和学术的人脸识别方法的识别精度大幅度降低。人脸化妆的应用可以影响现有许多的依赖对比度和纹理信息线索建立的匹配程序。同时，识别多种彩妆结合后的妆容比识别单独使用某一种化妆品的妆容更具挑战。解决混合妆容异构后的识别问题是开发鲁棒的人脸识别系统的关键。

到目前为止，解决化妆引入的变化而造成的挑战的科技文献很有限。文献[4]利用典型相关分析(canonicalcorrelationanalysis,CCA)连同支持向量机(support vectormachine,SVM)分类器一起改进化妆之前和化妆之后图像的匹配。为了使匹配图像之间的差距最小化，文献[5]研究了从化妆之前和化妆之后图像中提取的特征之间的映射。使用改进的CCA和偏最小二乘法(partialleast squares,PLS)研究了该映射。尽管文中证明了基于映射的方法的有效性，但是它有两个限制。首先，化妆之前和化妆之后人脸图像之间的映射可能是复杂的、空间变化的和非线性的,因此，为了描述化妆之前和化妆之后样本之间的复杂关系，研究单个映射远远不够;其二，CCA和PLS方法有过拟合训练数据的倾向，所以不能在看不见的对象上得到较好的结果。文献[6,7]提出了基于全局和局部信息综合评分的人脸检测方法，该类方法在小样本范围内具有较高的识别精度，但是在扩大的样本范围内识别精度有待研究。

因此，提出了一种基于补丁子空间集成的鲁棒人脸识别算法以解决在化妆后异构人脸图像识别的问题。该方法通过将人脸图像嵌入补丁集中，利用多种模式提取特征向量，最后经过分类比较器及求和规则获得识别结果。同时，通过随机选择不同补丁作为每个基于子空间的分类器的输入避免了过度拟合问题。该算法在多个化妆数据集上进行了评估，结果证明了算法的有效性。

# 1基于多补丁集成学习的鲁棒人脸识别算法

面对化妆时的人脸识别提出的多补丁集成学习方法流程如图2所示，对于一张人脸图像，首先将这张图像镶嵌于补丁当中，然后基于本地梯度 Gabor 模式(local gabor pattern,LGP)[8]、

Gabor 空间定序定比测量直方图(histogramof gaborspacefixedratio measures,HGSFRM)和密集采样局部多值模式(DenselySampledLocalMulti-valuedPattern,DSLMP)9]，将多个特征描述符应用于每个补丁中。这些描述符捕获全局和局部信息。接着，使用基于费舍尔分离准则的权值学习方案[10排序每个补丁的重要性。然后，基于与补丁相关的权值，使用半随机采样方法选择多组补丁并创建子空间。在这些子空间中使用基于协作的表示分类器(collaborative-basedrepresentationclassifiers,CRC)[l]和基于稀疏的表示分类器(sparse-basedrepresentationclassifiers,SRC)构建集成分类器对子空间补丁进行评分[12]。最后，使用求和规则融合由分类器生成的分数，该过程从多个模式取分数的加权平均。经过以上步骤，完成对一个人像图片的识别。

![](images/bfc5ea6942cf19d99ac86ba39f36fa8a77b6428182184edc8f6afde73ad0356e.jpg)  
图1化妆改变人脸外观实例

![](images/04a7c1834ddcb4c3668179d7b4a2c84e24a5d1e9c47dd5c80424fb8f20412aa6.jpg)  
训练阶段  
图2多补丁集成学习流程框架

该方法为人脸匹配器提出了一种集成的框架，该框架对化妆的应用具有鲁棒性。该方法使用对应于三个不同特征向量符的多个子空间和多个图像补丁。在这些子空间中联合应用了稀疏和协作分类器。使用来自每个补丁的权值信息引导每次选择，并不使用纯随机采样。

描述符的选择在人脸识别算法中至关重要。使用LGP、HGSFRM和DSLMP描述符表示每张人脸图像中的补丁。

数学上，将Gabor滤波器描述为[9]

$$
\varphi _ { \mu , \nu } ( z ) = \frac { \left\| k _ { \mu , \nu } \right\| ^ { 2 } } { \beta ^ { 2 } } e ^ { - \frac { \left\| k _ { \mu , \nu } \right\| ^ { 2 } \left\| z \right\| ^ { 2 } } { 2 \beta ^ { 2 } } } [ e ^ { i k _ { u , \nu ^ { z } } } - e ^ { - \frac { \beta ^ { 2 } } { 2 } } + e ^ { \beta k } ]
$$

其中: $\mu$ 和 $\nu$ 分别为Gabor滤波器的方向和规模。 $z$ 为像素位置，表示规范算子。 $\beta$ 为默认值是 $2 \pi$ 的恒量。通过 $k _ { \mu , \nu } = k _ { \nu } e ^ { i \phi _ { \mu } }$ 给出 $k _ { \mu , \nu }$ ，其中 $k _ { \nu } = k _ { \mathrm { m a x } } / s ^ { \nu }$ ， $\phi _ { \mu } = \pi \mu / 8$ 。这里， $k _ { \operatorname* { m a x } }$ 为最大频率,$s$ 为频域中核心程序之间的间距因子。利用Gabor核函数通过执行输入图像的卷积获得图像的Gabor响应：$G _ { \mu , \nu } ( z ) = I ( z ) * \varphi _ { \mu , \nu } ( z )$ 。复杂的Gabor响应有两部分：实数部分$r _ { \mu , \nu } ( z )$ 和虚数部分 $i _ { \mu , \nu } ( z )$ 。因此，Gabor 梯度 $A _ { \mu , \nu } ( z )$ 和相计算为

$$
A _ { \mu , \nu } ( z ) = \sqrt { r _ { \mu , \nu } ( z ) ^ { 2 } + i _ { \mu , \nu } ( z ) ^ { 2 } }
$$

$$
\theta _ { \mu , \nu } ( z ) = \arctan ( i _ { \mu , \nu } ( z ) / r _ { \mu , \nu } ( z ) )
$$

# 1.1局部 Gabor 梯度模式(LGP)

为了编码Gabor梯度响应,将梯度描述符定义为[10]

$$
\xi ( x _ { c } ) = \arctan \left( \sqrt { \beta } \cdot \frac { M _ { \nu } } { M _ { h } + \sqrt { \lambda } } \right)
$$

其中: $M _ { \nu }$ 和 $\boldsymbol { M } _ { h }$ 分别为沿着垂直和水平方向计算的图像梯度。这里，这两个方向互相正交。具有参数 $\beta$ 和 $\lambda$ 的反正切函数(arctan)阻止输入增加和减少太快。令 $\gamma _ { c }$ 表示矩形中心像素的强度值，该矩形由从 $x _ { 0 }$ 到 $\boldsymbol { x } _ { R - 1 }$ 采样的临近点围成，其中 $R$ 为领域大小。其梯度的计算为

$$
M _ { \nu } = \gamma _ { m o d ( i + 4 , R ) } - \gamma _ { i }
$$

$$
M _ { h } = \gamma _ { m o d ( i + 6 , R ) } - \gamma _ { m o d ( i + 2 , R ) }
$$

其中：用 $m o d$ 表示模运算符， $i$ 为临近像素的指数。在本文的实现中，本文使用 $R = 6 \setminus \ \beta = 8$ 和 $\lambda = 1 \times 1 0 ^ { - 6 }$ 。

# 1.2空间Gabor定序定比测量(HGSFRM)

为了编码相位响应，本文使用定序测量(ordinalmeasure,$\mathrm { O M } ) ^ { [ 1 1 ] }$ 。OM比较了两个不同的区域以确定哪个区域具有较大值(如均值)。本文使用多叶微分滤波器(multi-lobedifferentialfilters,MLDF)[12]来提取定序特征。数学上，将MLDF表示为

$$
M L D F = C _ { p } \sum _ { i = 1 } ^ { N _ { p } } \frac { 1 } { \sqrt { 2 \pi \delta _ { p i } } } \mathrm { e x p } \Bigg [ \frac { - ( z - \mu _ { p i } ) ^ { 2 } } { 2 \delta _ { p i } ^ { 2 } } \Bigg ]
$$

$$
- C _ { n } \sum _ { j = 1 } ^ { N _ { n } } \frac { 1 } { \sqrt { 2 \pi \delta _ { n j } } } \mathrm { e x p } \Bigg [ \frac { - ( z - \mu _ { n j } ) ^ { 2 } } { 2 \delta _ { n j } ^ { 2 } } \Bigg ]
$$

其中: $z$ 为像素位置， $\mu$ 和 $\delta$ 分别为2D高斯滤波器的中心位置和规模。 $ { \boldsymbol { N } } _ { p }$ 为正叶数， $\boldsymbol { N } _ { n }$ 为负叶数。 $C _ { p }$ 和 $C _ { n }$ 为常系数，用以确保MLDF 的输出，即 $C _ { p } N _ { p } = C _ { n } N _ { n }$ 。MLDF为差分带通滤波器的一种类型。

# 1.3密集采样局部多值模式(DSLMP)

为了生成DSLMP特征，将每个LBP编码的图像划分为非重叠补丁，并从每个补丁中提取直方图信息[13]。每张图像中的补丁数为 256，每个补丁的大小为 $1 6 \times 1 6$ 。所有这三个特征描述符如表1所示。

表1本文框架中使用的基于补丁的特征描述符的总结  

<html><body><table><tr><td>特征类型</td><td>LGP</td><td>HGSFRM</td><td>DSLMP</td></tr><tr><td>补丁尺寸</td><td>16 *16</td><td>16 *16</td><td>16 *16</td></tr><tr><td>补丁镶嵌</td><td>非重叠</td><td>非重叠</td><td>重叠</td></tr><tr><td>补丁数</td><td>5120</td><td>5120</td><td>5120</td></tr><tr><td>每个补丁中bins 数</td><td>32</td><td>32</td><td>59</td></tr></table></body></html>

# 1.4半随机子空间 LDA(SRS-LDA)

1.4.1训练阶段

权值学习：在采样补丁之前，本文给每个提取的补丁分配权值，接着，基于这些权值排序这些补丁。基于费舍尔的分离准则计算权值。本文的假设为，不同面部区域通过化妆可能对人脸识别有不同的影响，因为化妆信息是不均布的。对于每个补丁 $p$ 及其相关的特征向量 $Y _ { i , j } ( p )$ ，类内平均距离 $D _ { 1 } ( p )$ 为

$$
D _ { 1 } ( p ) = \frac { 1 } { c ^ { 2 } } \sum _ { i = 1 } ^ { c } \frac { c } { ( l _ { i } - 1 ) } \sum _ { j = 1 } ^ { l _ { i } - 1 } \sum _ { k = j + 1 } ^ { l _ { i } } \phi ( Y _ { i , j } ( p ) , Y _ { i , k } ( p ) )
$$

其中， $\phi$ 表示两个特征向量之间的卡方距离， $l _ { i } = n _ { i } + m _ { i }$ 表示每个分类中样本的数量。类内距离的方差计算如下：

$$
V A R _ { 1 } ( p ) = \sum _ { i = 1 } ^ { c } \sum _ { j = 1 } ^ { l _ { i } - 1 } \sum _ { k = j + 1 } ^ { l _ { i } } \left( \phi ( X _ { i , j } ( p ) , X _ { i , k } ( p ) ) - \mathrm { D } _ { 1 } ( p ) \right) ^ { 2 }
$$

类间平均距离的计算如下：

$$
D _ { 2 } ( p ) = \frac { 2 } { c ^ { 2 } } \sum _ { c ( c - 1 ) } ^ { c - 1 } \sum _ { q = i + 1 } ^ { c } \frac { 1 } { l _ { i } l _ { q } ( c - 1 ) } { \sum _ { j = 1 } ^ { l _ { i } } \sum _ { k = 1 } ^ { l _ { q } } } \phi ( Y _ { i , j } ( p ) , Y _ { i , k } ( p ) )
$$

类间距离的方差计算如下：

$$
V A R _ { 2 } ( p ) = \sum _ { i = 1 } ^ { c - 1 } \sum _ { q = i + 1 } ^ { c } \sum _ { j = 1 } ^ { l _ { i } } \sum _ { k = 1 } ^ { l _ { q } } ( \phi ( Y _ { i , j } ( p ) , Y _ { i , k } ( p ) ) - D _ { 2 } ( p ) ) ^ { 2 }
$$

每个补丁 $p$ 的学习权值计算为

$$
W ( p ) = \frac { ( D _ { 1 } ( p ) - D _ { 2 } ( p ) ) ^ { 2 } } { V A R _ { 1 } ( p ) + V A R _ { 2 } ( p ) }
$$

学习权值确定了用于识别的不同补丁的重要性。接着，按照权值降序储存补丁，用以引导每个特征向量补丁采样过程。

补丁采样：创建多个子空间 $( K )$ 用以生成对应于每个描述符的分类器的集成。基于加权补丁的半随机采样构建每个子空间。半随机的含义是选择补丁的概率与其权值相关。对于创建第 $k , k = \left\{ 1 , 2 , . . . , k \right\}$ 个子空间，本文从 $Y _ { i , j } ^ { B }$ 和 $Y _ { i , j } ^ { A }$ 采样有关特定描述符的 $\alpha$ 个补丁，其中 $i = \{ 1 , 2 , . . . , c \} \ \setminus \ j = \{ 1 , 2 , . . . , n _ { i } \}$ 且$\alpha = \{ 1 , 2 , . . . , P \}$ ，以获得 $Y _ { i , j } ^ { B } \in R ^ { D \times 1 }$ 和 $Y _ { i , j } ^ { A } \in R ^ { D \times 1 }$ 。通过将 $\alpha$ 个特征向量连接到一个向量表示中，获得Y 和Y，其中D=α×d，$d$ 为每个补丁的特征维数(见表1)。考虑到补丁可以被全面的利用，可以考虑 $\alpha$ 的 $60 \%$ 选自补丁的前半， $\alpha$ 的 $40 \%$ 选自补丁的剩余一半。 $K$ 和 $\alpha$ 是根据经验拟定的，为了减少计算量，后面章节给出了实验后的建议取值。

子空间构造[14]：由于 $D$ 的维度通常高于样本的数量，所以执行特征降维以减少计算时间并避免小样本规模问题。减低特征维度的常用方法是应用主成分分析(PrincipalComponentAnalysis,PCA)。PCA寻找可以最好地重建初始向量的投影空间。为了找到这个子空间，分别从化妆之前和化妆之后采样的特征向量中计算平均向量 $\eta ^ { \scriptstyle A }$ 和 $\eta ^ { { \scriptscriptstyle B } }$ ： $\eta ^ { B } = \frac { 1 } { N } \sum _ { i = 1 } ^ { c } \sum _ { j = 1 } ^ { n _ { i } } \Upsilon _ { i , j } ^ { B }$ 和$\eta ^ { A } = \frac 1 { N + M } \sum _ { i = 1 } ^ { c } \sum _ { j = 1 } ^ { n _ { i } + m _ { i } } \mathbf Y _ { i , j } ^ { B }$ 。整个协方差矩阵的计算如下：

$$
S = \frac { 1 } { N + M } \sum _ { i = 1 } ^ { c } \sum _ { j = 1 } ^ { n _ { i } + m _ { i } } ( \mathbf { Y } _ { i , j } - \pmb { \eta } ) ( \mathbf { Y } _ { i , j } - \pmb { \eta } ) ^ { T }
$$

特征向量 $W _ { \scriptscriptstyle E }$ 可从从协方差矩阵 $s$ 中计算获得： $S W _ { _ { E } } = \lambda W _ { _ { E } }$ u在生成 $W _ { \scriptscriptstyle E }$ 之后，可将化妆之前和化妆之后样本投影到新的子空间中，如下：

$$
\mathbf { y } _ { i , j } ^ { B } = W _ { E } ^ { T } ( \mathbf { Y } _ { i , j } ^ { B } - \boldsymbol { \eta } ^ { B } )
$$

$$
\mathbf { y } _ { i , j } ^ { A } = W _ { E } ^ { T } ( \mathbf { Y } _ { i , j } ^ { A } - \boldsymbol { \eta } ^ { A } )
$$

y, 和y,分别为PCA后化妆之前和化妆之后样本的投影特征向量。使用的特征向量数为 $\operatorname* { m i n } ( N - c , M - c )$ 。

使用化妆之前和化妆之后的特征向量来计算类间散度和类内散度矩阵。这确保了学习的特征表示对化妆变化不太敏感。当为特征描述符构造第 $k$ 个子空间时，使用化妆之前 $( \mathbf { y } _ { i , j } ^ { B } )$ 和化妆之后 $( \mathbf { y } _ { i , j } ^ { A } )$ 投影向量计算第 $i$ 个主体的平均类向量。

$$
\eta _ { i } ^ { ( k ) } = \frac { 1 } { n _ { i } + m _ { i } } \Biggl ( \sqrt { \sum _ { j = 1 } ^ { n _ { i } } y _ { i , j } ^ { 2 B } + \sum _ { j = 1 } ^ { n _ { i } } y _ { i , j } ^ { 2 A } } \Biggr )
$$

接着，计算类间散度矩阵，如下：

$$
S _ { B } ^ { ( k ) } = \sum _ { i = 1 } ^ { c } ( \eta _ { i } ^ { ( k ) } - \eta ^ { ( k ) } ) ( \eta _ { i } ^ { ( k ) } - \eta ^ { ( k ) } ) ^ { T }
$$

其中: ${ \eta ^ { ( k ) } = \frac { 1 } { c ^ { 2 } } \sum _ { i = 1 } ^ { c } \eta _ { i } ^ { ( k ) } }$ 。类内散度矩阵的计算如下：

$$
\begin{array} { l } { S _ { \boldsymbol { W } } ^ { ( k ) } = \displaystyle \sum _ { i = 1 } ^ { c } \sum _ { j = 1 } ^ { n _ { i } } ( \mathbf { y } _ { i , j } ^ { B } - \boldsymbol { \eta } _ { i } ^ { ( k ) } ) ( \mathbf { y } _ { i , j } ^ { B } - \boldsymbol { \eta } _ { i } ^ { ( k ) } ) ^ { T } } \\ { \quad + \displaystyle \sum _ { i = 1 } ^ { c } \sum _ { j = 1 } ^ { m _ { i } } ( \mathbf { y } _ { i , j } ^ { A } - \boldsymbol { \eta } _ { i } ^ { ( k ) } ) ( \mathbf { y } _ { i , j } ^ { A } - \boldsymbol { \eta } _ { i } ^ { ( k ) } ) ^ { T } } \end{array}
$$

LDA的目的是寻找最优投影 $\omega _ { { } _ { F } }$ ，它可以最大化类间散度矩阵行列式和类内散度矩阵行列式的比例。该优化问题的定义为

$$
\omega _ { _ { F } } ^ { ( k ) } = \arg \operatorname* { m a x } _ { W _ { F } } \frac { \omega _ { _ { F } } ^ { T } S _ { _ B } ^ { ( k ) } \omega _ { _ { F } } } { \omega _ { _ { F } } ^ { T } S _ { _ { w } } ^ { ( k ) } \omega _ { _ { F } } }
$$

这相当于解决 $S _ { _ B } ^ { ( k ) } \psi ^ { ( k ) } = \lambda ^ { ( k ) } S _ { _ B } ^ { ( k ) } \psi ^ { ( k ) }$ 的广义特征值问题，其中 $k = \{ 1 , 2 , . . . , K \}$ 。对于每个子空间，训练阶段的输出为 $\eta ^ { B } \cdot \eta ^ { A }$ ，$\omega _ { _ { F } } ^ { ( k ) }$ 和 $\omega _ { { } _ { E } }$ 。这种处理方式的目的在于：(a)在权值学习过程中一起使用化妆之前和化妆之后的补丁；(b)生成相应的子空间。其中，化妆之前和化妆之后的特征向量用于学习LDA的类内和类间散度矩阵。为每个描述符重复构造的这些子空间，也称为通用子空间。

# 1.4.2测试阶段

在测试阶段，将隔离测试集中主体化妆之后的图像当作探针，同时将其与当作图库图像的化妆之前的图像进行比较。令$\mathrm { Y } _ { i , j } = f ( I _ { i , j } )$ 表示从 $I _ { i , j }$ 中提取的一组特征向量， $I _ { i , j }$ 为来自测试样本的化妆之前的图像或化妆之后的图像。从$\{ \Upsilon _ { i , j } ( p ) : \Upsilon _ { i , j } ( p ) \in \Upsilon _ { i , j } , 1 < p < P \}$ 中选择 $\alpha$ 补丁的相同集并将其连接为一个特征向量 $\Upsilon _ { i , j } ^ { B }$ 或 $\mathbf { Y } _ { i , j } ^ { A }$ 。训练集中和测试集中补丁的位置和顺序相同。

子空间投影：对于每个导出的子空间 $k = \{ 1 , 2 , . . . , K \}$ ，用下式获得化妆之前和化妆之后测试样本的表示。

$$
\mathbf { y } _ { i , j } ^ { B } = W _ { F } ^ { T } W _ { E } ^ { T } ( \mathbf { x } _ { i , j } ^ { B } - \mu ^ { B } )
$$

$$
\mathbf { y } _ { i , j } ^ { A } = W _ { F } ^ { T } W _ { E } ^ { T } ( \mathbf { x } _ { i , j } ^ { A } - \mu ^ { A } )
$$

其中： $\mathbf { y } _ { i , j } ^ { B }$ 或 $\mathbf { y } _ { i , j } ^ { A }$ 分别为化妆之前和化妆之后测试样本最终投影的特征向量。倘若化妆信息未知，则可采用化妆检测方案[15]进行区分。总平均向量 $\eta$ 可用于投影，从而导致匹配精度略微减少 $( < 1 \%$ 识别率)。

SRC和CRC分类：如前所述，化妆之前的样本被用作图库，化妆之后的样本被用作探针。令（204号 $\mathbf { Y } ^ { B } = \{ \mathbf { y } _ { 1 , 1 } ^ { B } , . . . , \mathbf { y } _ { 1 , n _ { 1 } ^ { \prime } } ^ { B } , . . . , \mathbf { y } _ { i , 1 } ^ { B } , . . . , \mathbf { y } _ { i , n _ { 1 } ^ { \prime } } ^ { B } , . . . , \mathbf { y } _ { c ^ { \prime } , 1 } ^ { B } , . . . , \mathbf { y } _ { c ^ { \prime } , n _ { 1 } ^ { \prime } } ^ { B } \}$ 表示化妆之前样本的图库特征向量， $c ^ { \prime }$ 为图库中主体的数量， $n _ { i } ^ { ' }$ 为第 $i$ 个主体的样本数。令 $\mathbf { y } _ { i , j } ^ { A }$ 表示化妆之后的探针样本。通过用探针样本替换图库计算距离分数，从而获得化妆之前化妆之后样本之间的相似度分数。这是使用稀疏和协作表示[16]原则进行计算的。SRC和CRC有其自身的优点，并能在分类中提供补充信息。因此，本文为每个子空间开发了两个分类器，一个基于SRC，另一个基于CRC，综合应用它们的输出作为分类依据。

# 2 实验仿真与分析

为了验证基于多补丁集成学习的人脸识别算法对化妆之前和化妆之后人脸样本识别的有效性，采用YMU数据集中的相关人脸数据进行了如下实验。

# 2.1化妆数据集

使用YMU-数据集进行仿真实验。为了减少由于缩放和姿势引起的变化，基于眼部地标，使用仿射变换几何规范化人脸图像。将所有规范化的人脸图像裁剪并调整至维度为 $1 2 8 \times 1 2 8$ ，将图像从RGB 转换为灰度图。

![](images/a63e8832db0c961a2a0e5f0c36d578c92f9f7be9bf7fed940228de61fb335ad0.jpg)  
图3调整和裁剪之后样本的实例

出于训练人脸匹配程序的目的，组建另一个数据集。该训练数据集由来自FAM数据集、亚洲女性化妆数据集和整个MIAA数据集的女性受试者的一个子集组成。训练数据集中，样本的总数为796，对应于398个受试者。每个受试者有一个化妆之前和一个化妆之后的样本。将这个数据集称为"化妆训练（Makeup TrainingData，MTD）”。由于MTD的每个受试者的样本数有限，所以本文使用面部对称性来生成镜像的人脸样本。通过这种方式，有助于构造更多鲁棒的子空间。应该注意的是，通过MTD训练并不会造成实验结果的过度优化，这是因为它与YMU属于2个不同的数据库，在训练和测试受试者之间没有重复。在实验中使用了以下参数值：子空间数 $K$ ，对于每个描述符为45；对于HGSFRM和LGP，$\lambda _ { 1 } = 0 . 1 5 , \lambda _ { 2 } = 0 . 1 , \alpha = 1 8 0$ ；对于LBP， $\alpha = 8 0$ 。SRS-LDA 特征向量的维度数为256。

# 2.2YMU数据集上的实验

为了评估本文提出人脸匹配程序的性能，进行下列三类的识别实验。

a)比较 $B$ 和 $B ^ { ( } B ^ { \mathrm { v s } } B ^ { ) }$ ：用以比较的这两张均为化妆之前的样本。

b)比较 $A$ 和 $A ^ { ( } A ^ { \mathrm { v s } } A ^ { ) }$ ：用以比较的这两张图像均为化妆之后的图像。

c)比较 $A$ 和 $B ^ { ( } A ^ { \mathrm { v s } } B ^ { ) }$ ：用以比较的一张图像为化妆之后的图像，而另一种图像为化妆之前的图像。

在 YMU 数据集中考虑的匹配场景的等效错误率(equalerrorrates.EER)总结如图4所示。COTS-1、COTS-2和COTS-3为商业人脸识别软件算法[15]，它们代表着人脸识别任务中的最先进性能。当匹配化妆之后和化妆之前样本时，这些评估算法都有明显较高的 EER。对于匹配场景 $A ^ { \mathrm { v s } } B$ ，本文显著地将EER从接近 $20 \%$ 减少到了 $6 . 3 6 \%$ ，获得了最低的等效错误率。

![](images/76984f11bb337205029fc5c9f4abac630d7c0f8f57f8afd59fcc5a29cccf8067.jpg)  
图4不同算法识别错误率

# 2.3算法融合

本文还考虑了将本文提出的方法与COTS 融合，以进一步提高匹配性能。基于最小-最大规则和简单的求和规则规范化由不同匹配程序生成的个体匹配分数。由图5可见，就EER和真实接受率(genuineacceptrate,GAR)方面，融合的匹配程序显著提高了人脸匹配的性能。很明显，本文提出的方法和COTS 提供了互相补充的信息。COTS-1、COTS-2和COTS-3获得的EERs分别为 $1 3 . 0 4 \%$ 、 $7 . 7 9 \%$ 和 $9 . 3 3 \%$ 。COTS-1、COTS-2 和 COTS-3在误识率（fault accept rate,FAR） $0 . 1 \%$ 处获得的GARs(GAR:$0 . 1 \%$ FAR)分别为 $4 9 . 3 6 \%$ 、 $7 7 . 1 5 \%$ 和 $5 8 . 9 7 \%$ 。本文提出方法获得的EER为 $6 . 4 1 \%$ ，GAR为 $6 9 . 8 9 \%$ 。当融合本文提出的方法和COTS-2及COTS-3时，本文获得了最佳结果： $84 . 1 1 \%$ GAR和 $5 . 0 8 \%$ EER，该结果优于COTS-2和COTS-3的单一算法测试结果。这表明，本文提出的方法可以有效改进COTS 算法。必须注意的是，本文只关注鲁棒的特征提取和匹配；这与端对端COTS匹配程序正好相反，端对端COTS匹配程序具有多年研究的优势，因此可能具有先进的前处理和后处理程序。尽管如此，本文提出的方法仍在识别率及融合算法改进方面非常具有竞争力。

![](images/84ca6f59b57ef186e38a2ab0323f41641f058c36729b7e1b8dc520746597f246.jpg)  
图5YMU数据集上单一算法和融合算法在不同误识率下的真实接受率曲线

相比于 $A ^ { \mathrm { v s } } B$ 上的随机采样，由权值学习产生的半随机采样方案将GAR大约提高了 $4 \%$ 。由于半随机采样方案的使用，该方法的稳定性是不确定的。为了证实 SRS-LDA 的稳定性，本文重复实验3.1并报告EER和GAR的分布。如图6所示，在 $0 . 1 \%$ 的FAR处，EER值范围为 $6 . 1 3 \%$ 到 $6 . 6 9 \%$ ，GAR的变化范围为 $6 9 . 1 8 \%$ 到 $70 \%$ 。该实验结果表明，采用半随机方案并没有造成集成算法的不稳定。

![](images/74363f574b76d1ae828110430d6633e56774f02cf763a4378688c88d1f6908eb.jpg)  
图6YMU数据集上SRS-LDA方法的稳定性的示例：6.41 $\pm 0 . 2 8$ $( \mathrm { E E R } ) , 6 9 . 8 9 \pm 0 . 7 1 ( \mathrm { F A R } = 0 . 1 \%$ 处的GAR)

# 2.4描述符个体分析

在多补丁集成学习算法中使用了三种类型的特征描述(LGP、HGSFRM和DSLMP）。但是，个体特征描述符的性能不同。如果只使用基于描述符的方法，则 $A ^ { \mathrm { v s } } B$ 的匹配性能非常低。如图7所示,LGP、HGSFRM和DSLMP获得的EER分别为 $20 . 7 9 \%$ 、 $20 . 5 4 \%$ 和 $1 9 . 9 3 \%$ 。这表明，整体学习方案框架的使用进一步提高了算法性能。在采用了SRS-LDA方法之后，匹配性能显著增加。在大量识别实验后之后的辨识数据中可以看出，LGP、HGSFRM和DSLMP的融合得到了最佳结果，由此证实了在本文提出框架中使用这些特征的合理性。HGSFRM获得了个体特征描述符之间的最佳整体性能。

![](images/254b9947923785e22e6fb31aedd1bc8d0adcaed5853820db8e476d44d3c18d54.jpg)  
图7采用不同描述符的GAR与EER测试数据

# 2.5 子空间数

在 SRS-LDA 中需要考虑的一个重要的参数是使用的子空间数 $( K )$ 。出于此目的，本文构造了另一个实验来分析本文提出方法的收敛性。本文逐渐增加子空间数并计算相应的Rank-1精度。如图8所示，本文提出方法的性能起先随着子空间数的增加而增加，然后稳定。HGSFRM在60次迭代中到达顶峰，而DSLMP和LGP分别在50和80次迭代之后到达顶峰。

在本文实验中，将子空间数设置为95。实验表明在这个子空间数下的算法性能稳定。

![](images/32c1558b98697b066fded3a84acf547a8203ed701e4c74e42e2fd164a73ade61.jpg)  
图8对于不同特征描述符(YMU数据集),子空间数对 SRS-LDA 算法的影响

# 2.6计算复杂性

由于训练阶段是离线执行的，在实时操作期间只有测试样本的特征提取和分类会影响计算时间。特征提取过程为简单的线性操作且其资源占用有限，DSLMP和CRC即采用纯随机采样方式，各方法计算耗时如表2所示，可见SRS-LDA的计算时间比其他方法均要低，这是因为提出的SRS-LDA方法虽然由集成学习算法生成的随机子空间彼此独立，但是它们可以被并行处理，在计算上可以有效地满足实际人脸识别系统的要求。

表2本文提出算法的计算时间(使用MatlabR2016在处理器为i7-

2800CPU,RAM 为 $3 . 4 0 \mathrm { G H z }$ 和 16GB 的64位操作系统上进行实验)

<html><body><table><tr><td>算法</td><td>LGP</td><td>HGSFRM</td><td>DSLMP</td><td>CRC</td><td>SRS-LDA</td></tr><tr><td>时间(s)</td><td>4.18</td><td>2.14</td><td>3.82</td><td>1.34</td><td>0.62</td></tr></table></body></html>

# 2.7 大规模识别实验

为了证明实际人脸检索实验利用来自FRGC及MIW数据集的图像的子集增加化妆之前的样本。在这个实验中，将来自YMU 数据集的化妆之后的样本用作探针。从FRGC 数据集中选择子集为10000 的照片图像(10K:4574女性 $^ +$ 5426 男性)。从MIW 数据集添加112张人脸图像添加到了图库，从而总共有10414张图像(302张化妆之前的YMU图像、10KFRGC图像以及112张MIW图像)。人脸匹配精度数据如图9所示的曲线。从实际实验数据中可以看出，在使用前述完全相同算法的前提下，大规模样本辨识精度只有轻微下降。这意味着，本文提出的方法可应用到一个大的数据集。

![](images/efa31d8fb85230f85e45d84ebcd4abc802db103269872c2965723495040c5ff2.jpg)  
图9不同规模数据样本下的识别精度曲线

# 3 结束语

本文为匹配化妆之后图像和化妆之前图像提出了一种方法。该方法基于补丁集成的学习，为三个不同描述符生成了多个子空间。随后利用Fisher的分离准则在生成子空间之前引导补丁采样过程。在生成的半随机子空间中，同时使用SRC和CRC进行分类。最终输出为来自个体描述符的匹配分数。YMU数据集及更大规模数据集上的实验结果表明了本文提出方法的有效性。本文提出的方法可与COTS算法融合，进一步提高匹配精度。

# 参考文献：

[1]刘峰，孟凡荣，梁志贞．基于一阶和二阶信息图像表示的人脸识别[J]. 计算机应 用研究,2017,34(2):603-606.(Liu Feng,Meng Fanrong,Liang Zhizhen.Face recognition based on first and two order information image representation [J].Application Research of Computers,2017,34 (2): 603- 606.)   
[2]邹国锋，傅桂霞，李海涛，等．多姿态人脸识别综述[J].模式识别与 人工智能,2015,28(7):613-625.(Zou Guofeng,Fu Guixia,Li Haitao,et al.Overview of multi pose face recognition [J].Pattern Recognition and Artificial Intelligence,2015,28(7): 613-625.)   
[3]Ueda S,Koyama T. Influence of make-up on facial recognition [J] Perception,2010,39 (2): 260-264.   
[4]陈熙，张戈．基于非高斯二维Gabor 滤波器的生物特征提取算法[J]. 计算机工程与应用，2017,53(18):170-175.(Chen Xi,Zhang Ge. Biometric extraction algorithm based on non Gauss two-dimensional gabor filter [J].Application Research of Computers,2017,53 (18): 170-175.)   
[5]陈婧，张苏．基于熵加权Gabor 特征的鲁棒人脸识别方法[J].控制工 程,2017,24(8): 1623-1629.(Chen Jing, Zhang su.Robust face recognition method based on entropy weighted Gabor feature [J].Control Engineering, 2017,24(8): 1623-1629.)

[6]范守科，朱明．基于加权分块稀疏表示的光照鲁棒性人脸识别[J].计 算机应用研究,2015(5):1563-1567.(Fan Shouke,Zhu Ming.Illumination robust face recognition based on weighted block sparse representation [J]. Application Research ofComputers,2015(5):1563-1567.)

[7] 苏煜，山世光，陈熙霖，等．基于全局和局部特征集成的人脸识别[J]. 软件学报,2010,21(8):1849-1862.(Su Yu,Shan Shi Guang,Chen Xilin, et al.Face recognition based on global and local feature integration [J]. Journal of Software,2010,21(8): 1849-1862.)

[8]Liu B,Yan XU,Qiang MI,et al.Face recognition based on LBP feature and improved Fisher criterion [J].Computer Engineering& Applications, 2017.

[9]闵永智，程天栋，殷超，等.基于GLCM与自适应Gabor滤波器组的纹 理图像分割[J].计算机工程，2017,43(1):280-286.(Min Yongzhi, Cheng Tiandong,Yin Chao,et al.Texture image segmentation based on GLCMand adaptive Gabor filter banks [J]. Computer Engineering,2017,43 (1):280-286.)

[10]向征，谭恒良，马争鸣．改进的HOG和Gabor,LBP性能比较[J].计算 机辅助设计与图形学学报，2012,24(6):787-792.(Xiang Zheng,Tan Hengliang，Ma Zhengming.contending. Performance Comparison of Improved HOG,Gabor and LBP[J]. Journal of Computer Aided Design and Graphics,2012,24 (6): 787-792.

[11] Sun Z,Tan T.Ordinal Measures for Iris Recognition [J].IEEE Trans on

Pattern Analysis& Machine Intelligence,2009,31(12):2211-26.

[12] Nguyen HV,Bai Li, Shen Linlin.Local gabor binary pattern whitened PCA: a novel approach for face recognition from single image per person [C]/ Advances in Biometrics.Berlin: Springer, 2009:269-278.

[13]邵珠宏，欧阳军林，廖帆，等．基于局部特征和集成学习的鲁棒彩色人 脸识别算法[J]．东南大学学报：自然科学版，2015,45(2):251-255. (Shao Zhuhong,Ouyang Junlin，Liao Fan，et al.Robust color face recognition algorithm based on local features and integrated learning [J] Journal of Southeast University:Natural Science Edition,2015,45 (2):251- 255.)

[14]Juefeixu F,PalDK,Singh K,et al.A preliminary investigation on the sensitivity of COTS face recognition systems to forensic analyst-style face processing for occlusions [Cl// Proc of IEEE Conference on Computer Vision and Pattern Recognition.2015:25-33.

[15] Proenca H,Neves JC.Deep-PRWIS: periocular recognition without the iris and sclera using deep learning frameworks [J].IEEE Trans on Information Forensics& Security,2017,34(9):34-42.

[16]黄超，高理平．人脸样貌独立判别的协作表情识别算法[J].计算机应 用研究，2017,34(9):2858-2862.(Huang Chao,Gao Li Ping.Facial expression independent discriminating cooperative expression recognition algorithm[J].Application Research ofComputers,2017,34(9):2858-2862.)