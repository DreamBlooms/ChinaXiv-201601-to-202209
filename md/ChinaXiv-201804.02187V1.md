# 基于特征加权的代理判别模型模式识别方法

潘海洋1,2，郑近德1，郭雨怡1

(1.安徽工业大学 机械工程学院，安徽 马鞍山 243032;2.湖南大学 汽车车身先进设计制造国家重点实验室，长沙410082)

摘要：针对以往模式识别方法的不足及特征值贡献度的问题,提出了基于特征加权的代理判别模型(agentdiscriminatemodel based feature weighted，ADMFW）模式识别方法。该方法的核心在于利用加权因子获取加权特征，并采用代理模型建立加权特征之间的关系函数，即首先计算特征值的权值因子，评估特征值的显著度，进而对每个特征值予以权值；然后利用加权特征和代理模型建立预测模型；最后采用预测模型对未知样本进行识别诊断。对滚动轴承实测数据的分析结果表明，ADMFW可以有效地对滚动轴承的工作状态和故障类型进行识别。

关键词：贡献度；ADMFW；权值因子；滚动轴承 中图分类号：TP391.4 doi:10.3969/j.issn.1001-3695.2017.11.0846

# Pattern recognition method of agent discriminate model based feature weighted

Pan Haiyang1,², Zheng Jinde1, Guo Yuyil (1.Schoolof Mechanical Enginering Anhui UniversityofTechnology,Ma'anshanAnui243032,China;2.State Key Laboratory ofAdvanced Design &Manufacture for Vehicle Body Hunan University,Changsha 41oo82, China)

Abstract:In viewofthe shortcomings ofthe previous paternrecognition methodsand thesaliencyproblemoffeatures,this paper proposed apatern recognition method—Agent discriminate model based feature weighted (ADMFW).The core ofthis method is touse the weighting factortoobtaintheweighted featureandutilize theagentdiscriminate model to establish the weighting functionof weighted feature.Firstly,calculating the weighting factorsofthefeatures toevaluate thesaliencyofthe featureandassigningtheweightstofeatures.Secondlyusingthe weightingfeaturesandtheagentdiscriminate modeltoestablish the prediction model.Finaly,applying the predictionmodel to identifythe unknownsamples.Theanalysisofthe experimental data of rolling bearing shows that this method can identify the working states andfault types ofroling bearings ffectively. Key words: saliency; agent discriminate model based feature weighted; weighting factor; roling bearing

# 0 引言

模式识别方法作为机械故障诊断中的重要一环，其识别精度的好坏直接影响到机械设备的安全运行。目前常用的模式识别方法有人工神经网络和支持向量机，并且已在机械故障诊断领域得到了广泛应用，收到了良好的应用效果[1]。

人工神经网络的核心是应用经验风险最小化原则（empiricalriskminimization，ERM)，该原则容易使人工神经网络陷入局部化最优，致使输出结果极不稳定，而且需要大量样本数据[2.3]。支持向量机（support vector machine，SVM）槟弃了传统的ERM，其依据结构风险最小化原则（structure riskminimization，SRM）[4,5]，具有更优的泛化能力，但该方法需要人工设定参数及选择核函数。

近年来，Raghuraj等人根据特征值之间的相互关系提出了一种基于多变量预测模型（variable predictivemodelbasedclassdiscriminate，VPMCD）模式识别方法[6，其核心思想是认为特征之间存在某种联系，依据这种联系构造预测模型，从而完成识别分类。文献[7,8]已将该方法及其改进的算法应用于机械故障诊断领域，并且与人工神经网络及支持向量机进行对比，获得了良好的应用效果。但是VPMCD方法并没有对算法的输入特征进行评估，即每类特征在群体中的显著度存在差异。当某类特征值对模型的贡献度很小或者不显著时，则利用该类特征建立的模型不足以反映该样本特征之间的真实关系。VPMCD直接采用提取的特征建立预测模型，忽略了每类特征的显著性。鉴于上述模式识别方法并未对特征值进行显著度评估，导致预测模型偏离真实模型。因此，本文以特征值之间的相互关系为基础，以Kriging代理判别模型为载体，以特征加权为核心，提出了一种基于特征加权的代理判别模型（ADMFW）模式识别方法。

ADMFW方法依据特征之间的内在关系，选择Kriging 函数建立代理判别模型，Kriging代理判别模型作为一种有效的估计函数模型，已广泛应用于石油、采矿等领域[9]。经典的 Kriging函数通常包含三种回归模型和七种相关模型，通过对两类模型的不同组合，获取不同的预测代理模型，然后从这些模型中获取最佳预测模型。然而，Kriging模型也没有对特征值的显著度予以说明，使之不能建立较为准确的样本预测模型。熵权法是结合特征值寻求最佳特征显著性的一种特征评价方法[10]，其基本原理是根据特征指标的之间的差异性，获取特征对应的信息熵，通过熵值的大小判断该特征指标的信息量，从而对特征指标赋予权值。本文借鉴该方法的思想，依据样本特征值本身都具有一定的显著性，然后利用权值因子对特征值的显著度予以赋值，最后通过显著度的大小对模型特征进行加权，削弱不显著特征对模型的影响[11]。

综上所述，文本依据特征值之间的相互关系，利用Kriging模型逼近特征值之间的真实关系模型，提出了基于特征加权的代理判别模型模式识别方法，并研究将ADMFW方法应用于滚动轴承故障诊断中的可行性。由于现场采集的振动信号中或多或少包含了环境噪声及其他部件的干扰噪声，致使提取的特征中也含有噪声因素，此时，每个特征值的显著度将由于噪声的原因产生变化，通过加权的思想可以评估特征值的显著程度，并且赋予权值，弱化显著度低的特征。因此，首先将所提取的特征值进行特征评价，根据评价指标对特征值进行加权处理，然后采用Kriging代理模型中的回归模型和相关模型依次组合建立数学代理判别模型，并以最小预测相对误差平方和为判据选择最佳代理判别模型，从而完成滚动轴承的故障诊断。

# 1 基于特征加权的代理判别模型模式识别方法

# 1.1特征加权

熵权法是结合特征值寻求最佳特征显著性的一种特征评价方法，其基本原理是某指标特征的值差异性越大，则对应的信息熵就越小，同时，该指标特征提供的对应信息量越大，其指标特征的权值便越大；反之，如果某项指标特征值差异性越小，则对应的信息熵值越大，该指标特征提供的对应信息量就越小，其指标的权值也会越小。

对于特征数组 $\{ f _ { i , j } , i = 1 , 2 , \cdots , S ; j = 1 , 2 , \cdots , N \}$ ，其中 $f _ { i , j }$ 为某种状态下的第 $i$ 个样本中的第 $j$ 个特征值。 $s$ 为某种状态下的样本数量总和， $N$ 为每个样本的特征值个数。

a）计算某种状态第 $i$ 个样本的第 $j$ 个特征值的指标比重。

$$
p _ { i j } = \frac { f _ { i , j } } { \displaystyle \sum _ { i = 1 } ^ { N } f _ { i , j } }
$$

其中:样本数为 $i = 1 , 2 , \cdots , S$ ，特征值个数为 $j = 1 , 2 , \cdots , N$ 。

b）计算第 $j$ 个特征值的熵值 $e _ { j }$ 。

$$
e _ { j } = - k \sum _ { i = 1 } ^ { N } p _ { i j } \ln p _ { i j }
$$

其中： nN’j=1,2,…,N。当每种状态下的类别及特征指标比重均相同时，则 $p _ { i j } = \textmu$ ，此时熵值达到最大。即 $e = 1$ ，则

$$
\begin{array} { c } { { e = - k \displaystyle \sum _ { i = 1 } ^ { N } \displaystyle \frac { 1 } { N } \ln \displaystyle \frac { 1 } { N } } } \\ { { = - k \ln \displaystyle \frac { 1 } { N } = 1 } } \end{array}
$$

其中， $k = 1 /  { \mathrm { l n } } N$ ，并且 $0 \leq e _ { i } \leq 1$ 。

c）计算各特征指标的权值 $\alpha _ { j }$ ，对于某特征指标，如果熵值越小，其包含的信息量将越多，则熵权越大；反之亦然，权值$\alpha _ { j }$ 表示为

$$
\alpha _ { j } = ( 1 - e _ { j } ) \Bigg / ( S - \sum _ { j = 1 } ^ { S } e _ { j } )
$$

$\alpha _ { j }$ 即为权重因子，如果特征指标的差异性越大，则对应的信息熵越小，同时，该特征指标反映的信息量越大，此时该特征指标的权重因子 $\alpha _ { j }$ 便越大，表示相应的特征值对分类越好，其在模型中显著度越高。

d)根据各类特征值的显著度，予以每类特征值相应的权值，从而在特征集 $\{ f _ { i , j } \}$ 里选择出更敏感的特征值进行故障诊断。

# 1.2 ADMFW原理

ADMFW模式识别方法以Kriging模型为基础建立预测模型，其变量代理判别模型 ADM形式可以表示成如下：

$$
f ( x ) = g ( x ) + u ( x )
$$

其中： $g ( x )$ 表示模型的确定性函数，即Kriging 函数中的回归模型，该模型通常分为三类：常数模型、一次回归模型、二次回归模型。这些模型是Kriging 函数的主要框架结构。 $u ( x )$ 作为模型的不确定性部分，它可以提供模型对模拟局部偏差的近似值，即Kriging函数中的相关模型。

$u ( x )$ 的协方差矩阵为

$$
C o \nu [ u ( x _ { i } ) u ( x _ { j } ) ] = \sigma _ { u } ^ { 2 } R [ R ( x _ { i } , x _ { j } ) ]
$$

其中： $R$ 为对称矩阵； $R ( x _ { i } , x _ { j } )$ 为 $x _ { i } , x _ { j }$ 的相关函数（ $( \mathbf { \Phi } _ { i , j = 1 , 2 , \cdots , n }$ ， $n$ 为采样点数）[9]。其具体函数有七种，公式如下：

$$
{ \mathrm { G a u s s i a n : ~ } } R ( x _ { i } , x _ { j } ) = \exp ( - \sum _ { k = 1 } ^ { n } \theta _ { k } \left| x _ { i } ^ { k } - x _ { j } ^ { k } \right| ^ { 2 } )
$$

$$
{ \mathrm { E x p o n e n t i a l : } } R ( x _ { i } , x _ { j } ) = \exp ( - \sum _ { k = 1 } ^ { n } \theta _ { k } \left| x _ { i } ^ { k } - x _ { j } ^ { k } \right| )
$$

c)Generalized exponential:

$$
R ( x _ { i } , x _ { j } ) = \exp ( - \sum _ { k = 1 } ^ { n } \theta _ { k } \left| x _ { i } ^ { k } - x _ { j } ^ { k } \right| ^ { \theta _ { n + 1 } } ) ~ ( 0 < \theta _ { n + 1 } \leq 2 )
$$

d)Linear:

$$
\operatorname* { m a x } \{ 0 , \sum _ { k = 1 } ^ { n } ( 1 - \theta _ { k } \left| x _ { i } ^ { k } - x _ { j } ^ { k } \right| )
$$

e)Spherical:

$$
R ( x _ { i } , x _ { j } ) = \sum _ { k = 1 } ^ { n } ( 1 - 1 . 5 \xi _ { k } + 0 . 5 \xi _ { k } ^ { 3 } ) \xi _ { k } = \operatorname* { m i n } \{ 1 , \theta _ { k } \left| x _ { i } ^ { k } - x _ { j } ^ { k } \right| \}
$$

f)Cubic:

$$
R ( x _ { i } , x _ { j } ) = \sum _ { k = 1 } ^ { n } ( 1 - 3 \xi _ { k } ^ { 2 } + 2 \xi _ { k } ^ { 3 } ) \ \xi _ { k } = \operatorname* { m i n } \{ 1 , \theta _ { k } \left| x _ { i } ^ { k } - x _ { j } ^ { k } \right| \}
$$

g)Spline:

$$
R ( x _ { i } , x _ { j } ) = \left\{ \begin{array} { l l } { \underset { k = 1 } { \overset { n } { \sum } } ( 1 - 1 5 \xi _ { k } ^ { 2 } + 3 0 \xi _ { k } ^ { 3 } ) \quad } & { 0 \leq \xi _ { k } \leq 0 . 2 } \\ { \hfill } \\ { \frac { n } { k - 1 } . 2 5 ( 1 - \xi _ { k } ) ^ { 3 } \quad } & { 0 . 2 < \xi _ { k } \leq 1 } \\ { \hfill } \\ { 0 \quad } & { \xi _ { k } > 1 } \\ { \xi _ { k } = \theta _ { k } \big | x _ { i } ^ { k } - x _ { i } ^ { k } \big | } & { } \end{array} \right.
$$

其中，向量 $\theta = ( \theta _ { 1 } , \theta _ { 2 } , \cdots , \theta _ { k } , \cdots , \theta _ { m } ) ^ { \mathrm { T } }$ ， $\mathbf { \lambda } _ { m }$ 为变量个数。 $x$ 的响应值为 $y ( x )$ ， $y ( x )$ 的估计值可以表示为

$$
\tilde { y } ( x ) = \tilde { \lambda } + r ^ { \operatorname { T } } ( x ) R ^ { - 1 } ( y - g ( x ) \tilde { \lambda } )
$$

其中： $y$ 的长度是 $n$ 。 $r ^ { \mathrm { { T } } } ( x )$ 的长度也是 $\mathbf { \Omega } _ { n }$ ，是 $x$ 和样本x,x,,x之间对应相关向量，其形式为：

$$
\boldsymbol { r } ^ { \mathrm { T } } ( \boldsymbol { x } ) = ( R ( x , x _ { \mathrm { 1 } } ) , R ( x , x _ { \mathrm { 2 } } ) , { \cdots } , R ( x , x _ { n } ) )
$$

式（14）中的估计值 $\tilde { \lambda }$ 由下式来表示：

$$
\tilde { \lambda } = ( g ( x ) ^ { \mathrm { T } } R ^ { - 1 } g ( x ) ) ^ { - 1 } g ( x ) ^ { \mathrm { T } } R ^ { - 1 } y
$$

此时，模型方差的估计值 $\tilde { \sigma } _ { u } ^ { 2 }$ 可以通过 $\lambda ^ { * }$ 和 $y$ 表示为

$$
\tilde { \sigma } _ { u } ^ { 2 } = { \frac { ( y - g \lambda ^ { * } ) ^ { \mathrm { T } } R ^ { - 1 } ( y - g \lambda ^ { * } ) } { n } }
$$

其中： $\lambda ^ { * }$ 作为 $\lambda$ 的最优估计值。

参数 $\theta$ 可以通过极大似然估计得出。即当 $\theta _ { j } > 0$ 时，式(18)的值最大:

$$
\operatorname* { m a x } ( - \frac { n \ln ( \tilde { \sigma } _ { u } ^ { 2 } ) + \ln | R | } { 2 } )
$$

其中： $\tilde { \sigma } _ { u } ^ { 2 }$ 和 $R$ 为参数 $\theta _ { j }$ 的函数，任意一个 $\theta _ { j }$ 的值都能生成一个插值模型，最终的Kriging模型是通过求解式（18）的无约束非线性最优问题得到的。

以 $p$ 个特征值为例，对以上代理模型中的回归模型采用特征值 $x _ { j } ( j \neq i )$ 对 $x _ { i }$ 进行预测，都可以得到代理判别模型（agentdiscriminatemodel，ADM）为

$$
x _ { i } = f ( x _ { j } , b _ { 0 } , b _ { j } , b _ { j j } , b _ { j k } ) + e
$$

式（19）称为特征值 $x _ { i }$ 的回归模型 $g ( x )$ 。其中，特征值 $x _ { i }$ 称为被预测变量； $x _ { j } ( j \neq i )$ 称为预测变量； $\mathbf { \Psi } _ { e }$ 为预测误差;$b _ { 0 } , b _ { j } , b _ { j j } , b _ { j k }$ 为模型参数。

以上为建立的初始 $\mathbf { \Pi } _ { \mathbf { A D M } }$ 模型，其参数未进行加权，得到的模型需要进一步的加权，才能满足后续预测的需要。因此采用熵权法评价技术对模型特征加权，以式（19)为初始预测模型，通过初始化参数，然后根据特征值的信息熵不同，赋予参数一个权值系数，弱化显著性较小的特征值对整体建模的影响，最终对整个代理判别模型加权值，其特征加权代理判别模型如下：

$$
x _ { i } = f ( x _ { j } , w _ { 0 } \ast b _ { 0 } , w _ { j } \ast b _ { j } , w _ { j j } \ast b _ { j j } , w _ { j k } \ast b _ { j k } ) + e
$$

其中： $w _ { o } , w _ { j } , w _ { j j } , w _ { j k }$ 为权值系数，且 $w _ { o } + w _ { j } + w _ { j j } + w _ { j k } = 1$ 0

对于有 $g$ 类分类问题的状况，首先对每一类的每一个样本都提取 $p$ 个特征值 $\boldsymbol { x } = [ x _ { 1 } , x _ { 2 } , \cdots , x _ { p } ]$ ，接着分别对不同状态类别下的训练样本数据建立数学代理判别模型，并且以最小预测相对误差平方和为判据选择最佳代理判别模型，选定特征评价算法，使该算法达到给模型的每一项特征加一个权值系数，得到加权代理判别模型，因此，不同状态类别下的所有特征值可以建立 $g \times p$ 个加权代理判别模型 $\mathbf { A D M } _ { i } ^ { k }$ （ $k = 1 , 2 , \cdots , g$ 代表不同的类别， $i = 1 , 2 , \cdots , p$ 代表不同的特征值)。然后对测试样本进行预测分类，提取同样的特征值，并用建立的 $g \times p$ 个代理判别模型 $\mathbf { A D M } _ { i } ^ { k }$ 分别对测试样本的特征值进行预测，可以得到 $g \times p$ 个预测特征值 $\tilde { x } _ { i }$ ，最后再以同一个类别下的所有加权特征相对预测误差平方和达到最小作为判据，对待测样本完成有效分类，该方法称之为基于特征加权的多变量代理判别模型模式识别方法。

基于特征加权的多变量代理判别模型模式识别方法步骤如下：

1）ADMFW训练过程

a)对于若干类（ $g$ ）分类问题，每一类选取 $\mathbf { \Omega } _ { n }$ 个样本作为训练，即标识为 $n _ { 1 } , n _ { 2 } , \cdots , n _ { g }$ 。对每个样本提取 $p$ 个特征值，即为 $\boldsymbol { x } = [ x _ { 1 } , x _ { 2 } , \cdots , x _ { p } ]$ ，此时，通过熵权法对每一类特征进行评估，获取其信息熵值，并以此计算出对应的权值因子 $w _ { k }$ 矩阵，此时输入特征即为 $x _ { k } * w _ { k }$ （ $k$ 为样本类别)。

b)选择第 $k ( 1 \leq k \leq g )$ 类训练样本的特征量 $x _ { i } ( i = 1 , 2 , \cdots , p )$ 作为被预测变量，选择剩下的 $_ { p - 1 }$ 个特征量 $x _ { j } ( j \neq i )$ 作为预测变量。

c)令回归模型和相关模型逐个配对，建立一个完整的函数模型。因此函数预测变量具有 $M \times R$ ( $M$ 和 $R$ 分别表示回归模型和相关模型的数量）种可能的组合方式，对于任一特征值 $x _ { i }$ 都可以建立 $n _ { k } = M \times R$ 个函数方程，接着把第 $k$ 类的训练样本特征值进行函数回代，利用函数预测模型可以得到特征值 $x _ { i }$ 的预测量 xipred°

d)分别对 $n _ { k }$ 个变量代理判别模型进行计算，即模型的相对预测误差平方和 $S S E _ { l } = \sum _ { \nu = 1 } ^ { n _ { k } } [ ( x _ { i \nu } - x _ { i \nu p r e d } ) \big / ( x _ { i \nu } - \overline { { x } } _ { i \nu } ) ] ^ { 2 }$ ，其中（204 $( l = 1 , 2 , \cdots , C _ { p - 1 } ^ { r } )$ ， $\mathbf { \Lambda } _ { \nu }$ 为第 $\nu$ 个训练样本， $\overline { { x } } _ { i \nu }$ 为 $x _ { i \nu }$ 的平均值。另外，选择 $S S E _ { l }$ 的最小值所对应的变量代理判别模型作为第 $k$ 类训练样本中特征量 $x _ { i }$ 的变量代理判别模型 $\mathbf { A D M } _ { i } ^ { k }$ 。

e)令 $k = k + 1$ ，重复步骤 $\textcircled{3} \sim \textcircled{4}$ 直至 $k = g$ 终止。因此， $g$ 个类别下的所有加权特征分别构建了代理判别模型 $\mathbf { A D M } _ { i } ^ { k }$ 。

f)将参与建模的训练样本输入每一个 ADM模型，即回代测试。当识别率最高时，选择此时的 $\mathbf { \Pi } _ { \mathbf { A D M } }$ 模型作为最佳的预测模型。

2）ADMOW模型的测试过程

a)选择待测样本，并且提取待测样本特征值$\boldsymbol { x } = [ x _ { 1 } , x _ { 2 } , \cdots , x _ { p } ]$ 。

b)对于待测样本的特征值 $x _ { i }$ ，拟分别运用建立的变量代理判别模型 $\mathbf { A D M } _ { i } ^ { k }$ 进行预测分析，可以得到对应的预测值 $x _ { i p r e d } ^ { k }$ （其中 $k = 1 , 2 , \cdots , g$ 代表不同的类别， $i = 1 , 2 , \cdots , p$ 代表不同的特征量)。

c)计算相同类别下求得的所有加权特征相对预测误差平方和值 $S S E ^ { k } = \sum _ { i = 1 } ^ { p } [ ( x _ { i } - x _ { i p r e d } ^ { k } ) \big / ( x _ { i } - \overline { { x } } _ { i } ) ] ^ { 2 }$ ，并以 $\boldsymbol { S } \boldsymbol { S } \boldsymbol { E } ^ { k }$ 最小作为判别判据对待测样本进行识别。

# 2 基于ADMFW的滚动轴承故障诊断方法

对于滚动轴承故障诊断而言，其特征提取作为至关重要的环节，只有选择适合的特征提取方法才能得到理想的识别诊断结果。本文拟提取标准差和峭度作为特征值，标准差和峭度已被广泛应用于多种故障诊断场合并取得了较好的效果。但拾取的振动信号往往具有非平稳和非线性特性，直接从原信号提取特征会影响诊断效果，因此，论文采用局部特征尺度分解（localcharacteristic scale decomposition，LCD)[l2]对原信号进行分解，获取分量信号，并对分量信号提取特征。其具体步骤如下：

a)设置采样频率 $f _ { s }$ ，拾取滚动轴承正常状态、内圈故障、 外圈故障各若干组样本数据。

b)采用LCD方法对拾取的信号进行分解，得到若干单分量信号，然后对前几个单分量信号分别提取标准差和峭度作为特征值，组成特征值向量矩阵。

c)选取一定数量的样本作为训练样本，对其进行加权，通过ADMFW建立预测模型。

d)用预测模型对测试样本进行评估分类，确定滚动轴承的最终状态类型。

# 3 应用分析

为了验证所提方法的有效性，拟应用于湖南大学现场采集的滚动轴承数据中。实验所用滚动轴承型号为6307E，并且采用激光切割的方法在滚动轴承的内外圈分别设置故障，来模拟滚动轴承内圈故障和外圈故障，其中切割槽的宽度为 $0 . 1 5 \mathrm { m m }$ 槽的深度为 $0 . 1 3 \mathrm { m m }$ 。实验时，转速设置为 $6 8 0 \mathrm { r p m }$ ，采样频率为 $4 0 9 6 ~ \mathrm { H z }$ ，实验装置图如图1所示（调速电机选择直流伺服电机，功率是 $6 0 0 \mathrm { W }$ )，其振动信号通过加速度传感器安装在轴承座上进行采集。实验采集三种状态的振动信号，即正常状态、内圈故障以及外圈故障，每种状态采集200组样本数据进行验证。

首先对采集到的时域信号进行LCD分解，每个信号可以分解得到若干单分量；接着对前两个单分量进行特征（标准差、峭度）提取；然后采用ADMFW方法对特征进行加权及训练建模，即通过熵权法进行特征评估，计算权值因子，获得加权特征，其权值因子如图2所示；最后采用ADMFW方法对测试样

本进行验证。

![](images/2b3bbe7d40deb0a9ef8660eb686c896929269e619fb61abbef376b88225fae3c.jpg)  
图1滚动轴承故障实验装置  
图2各类特征的权值因子

0.8第一个特征第一个特征0.6 第一个特征第四个特征国 0.4 0.2 小0正常状态 内圈故障 外圈故障滚动轴承状态类别

拟随机抽取120组数据样本作为训练，余下80组作为测试。为了说明ADMFW方法的有效性，拟与VPMCD、ADM模型进行对比，另外，引入两种计算分类精度方法，即误识率(falseacceptancerate，FAR）和Kappa系数。FAR越低，其他状态类别被识别为该类别的概率越低，识别准确性越高；Kappa系数值越大，表示分类精度越高，对比结果如表1所示。

表1三种分类方法的识别效果对比  

<html><body><table><tr><td>分类器</td><td>识别率/%</td><td>误识率/%</td><td>Kappa</td></tr><tr><td>VMMCD</td><td>93.75</td><td>9.38</td><td>0.9063</td></tr><tr><td>ADM</td><td>94.17</td><td>8.75</td><td>0.9125</td></tr><tr><td>ADMFW</td><td>99.58</td><td>0.63</td><td>0.9938</td></tr></table></body></html>

通过表1可知，无论是何种判别指标，ADMFW方法均优于VPMCD和ADM方法。这是由于VPMCD采用单纯的回归模型建立预测模型，当特征值之间具有复杂关系时，该回归模型建立的预测模型不能充分特征值之间的复杂关系；ADM模型虽然引入相关模型，进一步逼近特征值之间的真实关系，得到更高的识别率，但是，无论VPMCD还是ADM模型都没有考虑特征值的显著度，即对模型的敏感性。ADMFW方法考虑到特征值之间的复杂关系及特征值的显著度，通过引入权值因子，削弱显著度较低的特征值，进而得到更加真实的预测模型及更高的识别率。

为了验证所提方法的优越性，同时排除偶尔性的因素，再次采用10-CV交叉检验法来测试算法的准确性，并与VPMCD、ADM方法进行对比分析。选取同样的200 组样本数据，进行10 折交叉验证，其识别结果如图3所示，通过测试，ADMFW具有更优越的识别效果。

![](images/3f81c84402523437efc3b94f3ecf9d5e76fcfe0e1ae98498e6da3278c5d97bc8.jpg)  
图3三种分类方法在10折交叉检验法下得到的识别率

# 4 结束语

本文结合特征值之间复杂关系及特征值本身的显著性，提出了一种特征加权的代理判别模型模式识别方法，并将其应用于滚动轴承故障诊断中，通过实验分析比较，得出以下结论：a）对于参与建模的特征值，其本身都具有一定的显著性，利用权值因子对特征值的显著度予以赋值，然后通过显著度的大小对模型特征进行加权，削弱不显著特征对模型的影响，从而建立更加真实的代理判别模型。b）ADMFW方法建立预测代理模型的过程实际上就是回归模型和相关模型逐步组合的过程，通过相对误差平方和来自动获取最优组合模型，使得分类结果更加客观、准确。c）通过对滚动轴承状态诊断的分析结果表明，ADMFW方法可以准确地对滚动轴承的状态类型进行识别，从而为滚动轴承的故障诊断提供了一种新的方法。

# 参考文献：

[1]Sugumarm V, Ramachandran K I. Fault diagnosis of roller bearring using fussy classifier and histogram features with focus on automatic rule learning [J].Expert Systems with Applications,2011,38 (5): 4901-4907.   
[2]Wang Huaqing, Chen Peng.Intelligent diagnosis method for rolling element bearing faults using possibility theory and neural network [J].Computer & Industrial Engineering,2011,60 (4): 511-518.   
[3]Fei Shengwei, Zhang Xiaobin.Fault diagnosis of power transformer based on support vector machine with genetic algorithm [J].Expert Systems with Applications,2009,36(8): 11352-11357.   
[4]Zhang Xiaoyuan,Liang Yitao, Zhou Jianzhong,et al.A novel bearing fault diagnosis model integrated permutation entropy,ensemble empirical mode decomposition and optimized SVM[J].Measurement,2015,69:164-179.   
[5]Liu Xiaofeng,Bo Lin,Luo Honglin.Bearing faults diagnostics based on hybrid LS-SVMand EMD method[J].Measurement,2015,59:145-166.   
[6]Rao Raghuraj,Samavedham L.Variable predictive models:a new multivariate classification approach for pattrn recognition applications [J]. Pattern Recognition,2009,42(1):7-16.   
[7]Yang Yu,Pan Haiyang,Ma Li,et al.Aroller bearing fault diagnosis method based on the improved ITD and RRVPMCD[J].Measurement. 2014,55: 255-264.   
[8]Zheng Jinde.Rolling bearing fault diagnosis based on partially ensemble empirical mode decomposition and variable predictive model-based class discrimination [J].Archives of Civil and Mechanical Engineering,2016,16 (4): 784-794.   
[9]Gou Peng,Liu Wei,Cui Weicheng.A Comparison of Approximation Methods for Multidisciplinary Design Optimization of Ship Structures [J]. Journal of ship mechanics,2007,11(6): 913-923.   
[10]郭金维，蒲绪强，高祥，等．一种改进的多目标决策指标权重计算方法 [J]．西安电子科技大学学报,2015,41(6):118-125.   
[11] Zhou Wenhua,Wang Rusong.An entropy weight on the fuzzy synthetic assessment of Beijing urban ecosystem health [J].Acta Ecologica Sinica, 2005,25 (12): 3245-3251.   
[12]程军圣，郑近德，杨宇．基于局部特征尺度分解的经验包络解调方法及

其在机械故障诊断中的应用[J].机械工程学报,2012,48(19):87-94.