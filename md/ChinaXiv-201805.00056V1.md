# 面向不平衡数据分类的KFDA-Boosting算法

王来1，樊重俊1，杨云鹏1，袁光辉 2a,2b(1.上海理工大学 管理学院，上海 200093;2.上海财经大学a.信息管理与工程学院;b.实验中心，上海 200433)

摘要：数据分布的不平衡性和数据特征的非线性增加了分类的困难，特别是难以识别不平衡数据中的少数类，从而影响整体的分类效果。针对该问题，结合KFDA（kemel fisher discriminant analysis）能有效提取样本非线性特征的特性和集成学习中 Boosting 算法的思想，提出了KFDA-Bosting 算法。为了验证该算法对不平衡数据分类的有效性和优越性，以G-mean 值、少数类的查准率与查全率作为分类效果的评价指标，选取了UCI中10 个数据集测试 KFDA-Boosting 算法性能，并与支持向量机等六种分类算法进行对比实验。结果表明，对于不平衡数据分类，尤其是对不平衡度较大或呈非线性特征的数据，相比于其他分类算法，KFDA-Boosting 算法能有效地识别少数类，并且在整体上具有显著的分类效果和较好的稳定性。

关键词：核费希尔判别分析；集成学习；不平衡数据；分类中图分类号：TP301.6

# KFDA-Boosting algorithm oriented to imbalanced data classification

Wang Lai1, Fan Chongjun1†, Yang Yunpeng1, Yuan Guanghui2a, 2b (1.BusinessShool,Universityofanghaiforience&echnologyhanghio3,hna;2.a.hoolofIotio Management&Engineering,b.ExperimentalCenter,ShanghaiUniversityofFinance&Economics,hanghaiO0433,Cina)

Abstract:Theimbalanceofdatadistributionandthenonlinearityofdatacharacteristicsincreasethedificultyofclassification, especiallytherecognitionofthemnorityclassamples intheimbalanceddatatusaectingteoverallclassficatioeffect. For the above problem,an algorithmcalled KFDA-Boosting was proposed in this paper,whichcombinedthecharacteristicof KFDA,namely Kernel Fisher Discriminant Analysis,effectively extracting the samples’nonlinear features and the idea of Bostingalgorithmintheensemblelearning.Inorder toverifytheeffectivenessandsuperiorityofthealgorithm inthe clasificationofimbalanceddata,the paperusedthe G-meanvalue,the precisionandrecallof theminorityclasssamples to evaluate theperformanceofclassifier,andselected10datasetsofUCItotesttheKFDA-Boostingalgorithm,whichompared with other six algorithms,suchassupport vectormachine.Compared withotheralgorithms,theresultsshowthatthealgorithm caneffctivelyidentifytheminrityclas,andhasasignificanteffctontheclassificationofimbalanceddataandbeterstability on the whole, especially for the data with larger unbalance degree or nonlinear characteristics.

Key Words: Kernel Fisher discriminant analysis; ensemble learning; imbalanced data; classify

# 0 引言

不平衡数据分类，在许多领域中有着重要的应用，如疾病诊断、文本识别、入侵检测等。所谓不平衡数据，即数据集中某一类或某些类样本数远多于其他类别。对于不平衡数据分类，人们更多地关注少数类样本，并且少数类的错分代价相对较大。同时，随着数据量的增加，数据间越来越呈现非线性的特征，甚至为强非线性，这也增加了识别少数类的困难。因此，有效利用样本特征，精准地识别少数类样本，从而改善整体的分类效果，对解决不平衡数据的分类问题具有重大的价值与意义。

近年来，针对不平衡数据分类问题的研究，研究人员主要是从数据层和算法层两个层面着手。

在数据层面上，主要是通过重采样实现各类样本数的平衡，其中包括欠采样和过采样。对于重采样方法的研究，主要围绕Laurikkala提出的邻域清除算法[1]和Chawla等人提出的SMOTE算法2展开。例如，郑文昌等人[3提出了面向不平衡数据集的SMOTE-SVM交通事件检测算法，其中采用了SMOTE算法对事件数据进行过采样，以降低不平衡性。类似地，衣柏衡、杨毅等人[4'5]先通过改进的SMOTE 算法平衡各类别的样本数，再基于分类算法处理不平衡数据。但过采样可能会引入其他噪声，而欠采样可能丢失某些有用的重要信息。在算法层面上，主要包括代价敏感学习、集成学习等方法。代价敏感学习，为不同类型的错误分配不同的代价，以达到分类时产生的错误总代价最低的目标[67]。例如，邹鹏等人[8]针对客户价值细分问题中的不平衡数据，设计了代价敏感决策树算法，以实现对客户价值的有效识别。师彦文等[9针对不平衡数据集，提出了将代价敏感和随机森林相结合的分类算法。而集成学习，主要包括Boosting 算法[10]和Bagging 算法[1I]。对于运用集成学习解决不平衡数据分类的研究，较多的是在Freund 和Schapire 两人提出的 Boosting 算法的基础上进行改进[12,13,14]。例如，应维云等人[15]将LDA加入Boosting 算法中建立弱分类器，应用到客户流失预测中。虽然LDA-Boosting 提高了分类效率，但对包含非线性特征的不平衡数据进行分类时，并不能达到理想的效果；李诒靖等人[I6以KNN作为弱分类器，利用BPSO对数据进行特征提取后采用Adaboost-KNN 算法进行分类，但最优特征子集的选取容易陷入局部最优解，进而影响最终的分类效果。

以上两个层面，并未充分考虑到样本特征的有效利用，尤其是非线性特征。针对该问题，考虑到Boosting作为一种有效的分类学习方法，在处理那些难以学习的样本时会赋以更高的权重，使得分类器在下次训练中聚焦到那些样本上，从而能够在一定程度上提升对不平衡数据的分类效果。而核Fisher判别分析能够十分有效地对非线性特征进行提取，本文将这两种算法结合起来，提出了KFDA-Boosting 算法。

KFDA-Boosting算法利用核Fisher判别分析有效地提取非线性判别特征，并借助集成学习中Boosting算法的思想改善其分类性能。最后，对UCI中选取的10个数据集进行了仿真实验，以测试KFDA-Boosting算法对不平衡数据分类的可行性和有效性，并和其他六种分类算法的分类效果对比分析，期望体现该算法对少数类的有效识别，且整体的分类效果有一定的提升。

# 1 KFDA-Boosting算法

# 1.1Boosting 算法思想

本文主要以二分类问题为例，阐述 Boosting 算法思想[17,18]如下：

给定弱分类器和训练集

$$
S = \bigl \{ ( x _ { 1 } , y _ { 1 } ) , ( x _ { 2 } , y _ { 2 } ) , \cdots , ( x _ { m } , y _ { m } ) \bigr \}
$$

其中： $x _ { i } ( i = 1 , 2 , \cdots , m )$ 是一个 $\mathbf { \Omega } _ { n }$ 维列向量， $y _ { i }$ 表示第 $i$ 个样本的标签， $y _ { i } \in Y = \left\{ + 1 , - 1 \right\}$ 。

首先，对训练集中各样本赋予一个初始权重。接着，在每轮迭代过程中，会产生一个弱假设 $h _ { t } : X \to \{ 1 , - 1 \}$ ，并相应地更新样本权重，即增大那些被错误分类的样本的权重，减小分类正确的样本的权重，使得弱分类器在下次迭代中集中到那些被错分的样本上。经过 $T$ 轮迭代后，根据其分类精度得到的权重，将每轮迭代过程中产生的弱假设进行加权，从而得到最终的分类器。

# 1.2改进的核Fisher判别分析

核Fisher判别分析的基本思想是将一输入空间 $R$ 非线性映射到另一个特征空间 $F$ ，然后在特征空间中利用Fisher判别分析，以达到对输入空间进行分类的目的[19,20]。

考虑到Boosting 算法的特点，本文对原始的核Fisher判别分析加以改进，即对每个样本赋予相应的权重。具体思路与过程如下：

在特征空间 $F$ 中，每个样本对应的权重为 $D _ { t , i }$ ，其看做是第 $i$ 个样本，在第 $\mathbf { \Phi } _ { t }$ 轮学习中的权重。在变换后的空间 $F$ 中，各类样本的均值 $m _ { t , k } ^ { \phi }$ 和样本类内离散度矩阵 $S _ { t , k } ^ { \phi }$ 分别为

$$
m _ { t , k } ^ { \Phi } = \frac { \displaystyle \sum _ { y _ { i } = k } D _ { t , i } \phi ( x _ { i } ) } { \displaystyle \sum _ { y _ { i } = k } D _ { t , i } } , k = - 1 , 1
$$

$$
S _ { t , k } ^ { \phi } = \frac { \displaystyle \sum _ { y _ { i } = k } D _ { t , i } ( \phi ( x _ { i } ) - m _ { t , k } ^ { \phi } ) ( \phi ( x _ { i } ) - m _ { t , k } ^ { \phi } ) ^ { T } } { \displaystyle \sum _ { y _ { i } = k } D _ { t , i } } , k = \pm 1
$$

由上述 $m _ { t , k } ^ { \phi }$ 和 $S _ { t , k } ^ { \phi }$ ，样本类间离散度矩阵 $S _ { t , B } ^ { \phi }$ 和样本类内离散度矩阵 $S _ { t , W } ^ { \phi }$ 可表示为

$$
\boldsymbol { S } _ { t , B } ^ { \phi } = ( \boldsymbol { m } _ { t , 1 } ^ { \phi } - \boldsymbol { m } _ { t , - 1 } ^ { \phi } ) ( \boldsymbol { m } _ { t , 1 } ^ { \phi } - \boldsymbol { m } _ { t , - 1 } ^ { \phi } ) ^ { T }
$$

$$
S _ { t , W } ^ { \phi } = \sum _ { y _ { i } = 1 } D _ { t , i } S _ { t , 1 } ^ { \phi } + \sum _ { y _ { i } = - 1 } D _ { t , i } S _ { t , - 1 } ^ { \phi }
$$

即

$$
S _ { t , W } ^ { \phi } = \sum _ { k = 1 , - 1 } \sum _ { y _ { i } = 1 } D _ { t , i } \bigl ( \phi ( x ) - m _ { t , k } ^ { \phi } \bigr ) \bigl ( \phi ( x ) - m _ { t , k } ^ { \phi } \bigr ) ^ { T }
$$

根据Fisher判别准则，此时Fisher准则函数的表达式为

$$
J _ { _ { F } } ( w ) = \frac { w _ { t } ^ { _ T } S _ { t , B } ^ { \phi } w _ { t } } { w _ { t } ^ { _ T } S _ { t , W } ^ { \phi } w _ { t } ^ { _ t } }
$$

由此得到了特征空间中的Fisher判别函数，从而实现Fisher判别。但如果特征空间 $F$ 维数非常高，甚至为无限维时，无法直接通过上式求解最佳判别矢量。针对该问题，引入核函数。本文采用RBF核函数（即Gauss径向基核函数）作为映射函数$\phi$ ，即

$$
k ( x , y ) = \exp ( - \frac { \left\| x - y \right\| ^ { 2 } } { \sigma ^ { 2 } } )
$$

其中： $x , \ y$ 为对应的样本值； $\sigma$ 为常数，其决定非线性化的程度。

由再生核理论可知，高维空间中的任一解都可以被表示为该空间中训练样本线性组合的形式，即有

$$
w _ { t } = \sum _ { i = 1 } ^ { m } \alpha _ { i } \phi ( x _ { i } ) = \alpha \phi ( x )
$$

其中： ${ \alpha } = ( \alpha _ { 1 } , \alpha _ { 2 } , \cdots , \alpha _ { m } ) ^ { T } \in R ^ { n }$ 为各个元素 $\phi ( x _ { i } )$ 的线性系数。

根据 $m _ { t , k } ^ { \phi } ( k = - 1 , ~ 1 )$ 的定义和式(8)，将特征空间 $F$ 中训练样

本的均值 $m _ { t , k } ^ { \phi }$ 投影到 $w _ { t }$ 上，可得

$$
\boldsymbol { w _ { t } ^ { T } } \boldsymbol { m } _ { t , k } ^ { \phi } = \frac { 1 } { \displaystyle \sum _ { y _ { i } = k } D _ { t , i } } \sum _ { j = 1 } ^ { m } \sum _ { y _ { i } = k } \alpha _ { j } k ( \boldsymbol { x _ { j } } , \boldsymbol { x _ { i } ^ { k } } ) D _ { t , i } = \alpha ^ { T } \boldsymbol { M _ { t , k } }
$$

其中：

$$
M _ { t , k } = \frac { 1 } { \sum _ { y _ { i } = k } D _ { t , i } } \Bigg ( \sum _ { y _ { i } = k } k \big ( x _ { 1 } , x _ { i } \big ) , \sum _ { y _ { i } = k } k \big ( x _ { 2 } , x _ { i } \big ) , \cdots , \sum _ { y _ { i } = k } k \big ( x _ { m } , x _ { i } \big ) \Bigg ) \stackrel { } { 0 } \quad
$$

则可将式(6)中右边分式的分子、分母分别转换为如下形式：

$$
\begin{array} { r l } & { w _ { t } ^ { \textit { T } } S _ { t , B } ^ { \phi } w _ { t } = w _ { t } ^ { \textit { T } } \big ( m _ { t , 1 } ^ { \phi } - m _ { t , - 1 } ^ { \phi } \big ) \big ( m _ { t , 1 } ^ { \phi } - m _ { t , - 1 } ^ { \phi } \big ) ^ { T } w _ { t } } \\ & { \qquad = \alpha ^ { T } ( M _ { t , 1 } - M _ { t , - 1 } ) ( M _ { t , 1 } - M _ { t , - 1 } ) ^ { T } \alpha } \\ & { \qquad = \alpha ^ { T } M \alpha } \end{array}
$$

其中：

$$
\boldsymbol { M } = ( M _ { t , 1 } - M _ { t , - 1 } ) ( M _ { t , 1 } - M _ { t , - 1 } ) ^ { T }
$$

$$
\begin{array} { r l } & { \boldsymbol { w } _ { t } ^ { T } \boldsymbol { S } _ { t , W } ^ { \phi } \boldsymbol { w } _ { t } = \boldsymbol { w } _ { t } ^ { T } \displaystyle \sum _ { k = 1 , - 1 } \sum _ { y _ { i } = 1 } D _ { t , i } \Big ( \phi ( x ) - m _ { t , k } ^ { \phi } \Big ) \Big ( \phi ( x ) - m _ { t , k } ^ { \phi } \Big ) ^ { T } \boldsymbol { w } _ { t } } \\ & { \qquad = { \alpha _ { t } ^ { T } } H \alpha _ { t } } \end{array}
$$

其中：

$$
H = \sum _ { k = 1 , - 1 } \sum _ { y _ { i } = k } D _ { t , i } ( k _ { x _ { i } } - M _ { t , k } ) ( k _ { x _ { i } } - M _ { t , k } ) ^ { T }
$$

$$
k _ { x _ { i } } = \left( k ( x _ { 1 } , x _ { i } ) , k ( x _ { 2 } , x _ { i } ) , \cdots , k ( x _ { m } , x _ { i } ) \right) ^ { T }
$$

联立式（6）（11）（13）可得，特征空间中的Fisher判别式转变为

$$
J ( \alpha ) = { \frac { { \alpha } ^ { T } M { \alpha } } { { \alpha } ^ { T } H { \alpha } } }
$$

根据广义的Ralyeigh熵的性质得

$$
\alpha = H ^ { - 1 } ( M _ { t , 1 } - M _ { t , - 1 } )
$$

所以，特征空间 $\phi ( x )$ 在 $\alpha$ 上的投影为

$$
{ w _ { t } } \phi ( x ) \mathrm { { = } } \sum _ { j = 1 } ^ { m } \alpha _ { j } k ( x _ { j } , x )
$$

# 1.3KFDA-Boosting 算法流程

将改进的核Fisher 判别分析加入到Boosting 算法框架之中，得到KFDA-Boosting 算法流程如下。

对于训练集

$$
S = \left\{ ( x _ { 1 } , y _ { 1 } ) , ( x _ { 2 } , y _ { 2 } ) , \cdots , ( x _ { m } , y _ { m } ) \right\} ,
$$

其中： $y _ { i }$ 表示第 $i$ 个样本的标签， $y _ { i } \in Y = \{ + 1 , - 1 \}$ ；弱学习算法为改进的KFDA，迭代次数为 $T$ ，对于第 $i$ 个样本在第 $t$ 轮迭代时的分布为记为D；。

对于每轮迭代过程中的弱假设 $h _ { t } : X \to \{ 1 , - 1 \}$ ，其分类效果由错误率 $\varepsilon _ { t }$ 衡量：

$$
\varepsilon _ { t } = \sum D _ { t , i } I [ h _ { t } ( x _ { i } ) \neq y _ { i } ] = P _ { D _ { t , i } } ( h _ { t } ( x _ { i } ) \neq y _ { i } )
$$

KFDA-Boosting分类算法

输入：训练集 $S = \bigl \{ ( x _ { 1 } , y _ { 1 } ) , ( x _ { 2 } , y _ { 2 } ) , \cdots , ( x _ { m } , y _ { m } ) \bigl \}$ ，其中 $x _ { i } \in X$ ，

yi∈Y={+1,-1}，迭代次数T;

$D _ { 1 , i } = \left\{ \begin{array} { l l } { \displaystyle \frac { 1 } { 2 N _ { + } } , \mathrm { i f } y _ { i } = } \\ { \displaystyle \frac { 1 } { 2 N _ { - } } , \mathrm { e l s e } } \end{array} \right.$ $y _ { i } = 1$ （2041 初始化样本权重：D1.i ，其中 $N _ { + }$ ， $N _ { - }$ 分别为正类、负类样本的总数;2for $\scriptstyle { \mathrm { t } } = 1$ to $T$ 3训练针对样本分布为 $D _ { 1 , t }$ 的加权KFDA4求解得到 $H , M _ { t , k } , k = 1 , - 1$ ，5求解得到最优 $\alpha$ ；6 得到弱分类器h(xi)={ $h _ { t } ( x _ { i } ) = \left\{ { \begin{array} { l l } { + 1 , } & { { \mathrm { i f } } \ w _ { t } \phi ( x _ { i } ) > \theta _ { t } } \\ { - 1 , } & { { \mathrm { e l s e } } } \end{array} } \right.$ ，阈值 $\theta _ { t }$ 由各类样本均值在 $\alpha$ 上投影的加权平均值决定，权重分别为对应类的样本总数;7计算分类错误率 $\varepsilon _ { t } = \sum _ { k = 1 , - 1 } \sum _ { y _ { i } = k } D _ { t } ( i ) I ( h _ { t } ( x _ { i } ) \neq y _ { i } )$ （208 if $\varepsilon _ { t } > 0 . 5$ （209 continue10 else if $\scriptstyle { \cal T } = t - 1$ （20211 break12 end if13 令α $\alpha _ { t } = \frac { 1 } { 2 } \mathrm { l o g } \frac { 1 - \varepsilon _ { t } } { \varepsilon _ { t } } \ ;$ 14 更新样本权重：for $i { = } 1$ to $m$ （204号15 $D _ { t + 1 , i } = \frac { D _ { t , i } } { Z _ { t } } \mathrm { e x p } ( - \alpha _ { t } ( I ( h _ { t } ( x _ { i } ) = y _ { i } ) ) )$ ,其中 $Z _ { { \scriptscriptstyle t } }$ 为归一化算子,使得 $\sum _ { i } D _ { t + 1 , i } = 1$ 16 end for $i$ （17 end for $t$ （20输出：最终假设 $H ( x ) = \mathrm { s i g n } ( \sum _ { t = 1 } ^ { T } \alpha _ { t } h _ { t } ( x ) )$ （20

# 2 分类评价指标

在不平衡数据中，少数类对应为正类，多数类对应为负类表1给出了二分类问题的混淆矩阵。

表1二分类问题的混淆矩阵  

<html><body><table><tr><td></td><td>正类(预测)</td><td>负类(预测)</td></tr><tr><td>正类 (实际）</td><td>TP</td><td>FN</td></tr><tr><td>负类（实际）</td><td>FP</td><td>TN</td></tr></table></body></html>

在传统的分类算法中，通常采用分类准确率作为分类性能评价指标，即

$$
a c c u r a c y = { \frac { T P + T N } { T P + T N + F P + F N } }
$$

通常情况下，不平衡数据中的正类样本数所占比例小，因而 TP不会太大，甚至出现为0的情况，而TN值很大，使得分类的最终准确率较大，但却因此忽略了分类器对正类的识别正确率。所以，准确率并不能真正意义上反映分类器的性能。

鉴于分类正确率存在以上缺陷，本文采用G-mean值作为整体的分类性能评价指标，即

$$
G - m e a n = { \sqrt { T P R \cdot T N R } }
$$

其中： $T P R = \frac { T P } { T P + F N }$ $T N R = \frac { T N } { T N + F P } \circ$

G-mean值作为不平衡数据分类常用的评价指标，分别用TPR、TNR来衡量正类和负类的分类性能，其值越大表明分类效果越好。二者其中若有一个值的结果不佳，就会导致G-mean值不理想。

同时，为了进一步衡量对正类的分类效果，在此引入正类的查准率（precision）与查全率（recall)，其定义分别如下：

$$
p r e c i s i o n = \frac { T P } { T P + F P }
$$

$$
r e c a l l = \frac { T P } { T P + F N }
$$

# 3 算法实验与结果分析

# 3.1数据来源

从UCI中选取了10个数据集作为测试数据。为了将所选的数据集看做二分类问题的研究对象，作以下规定：如果数据集为两类，则将其中数目较少的一类作为正类，如Sonar、Ionosphere 数据集等；如果数据集为多类别，即其类别数大于2，将其中的某一类作为正类，剩下的类统一合并当作负类。经过上述规定与处理后，按不平衡度（IL）大小升序排列，得到用于二分类的不平衡数据集情况，如表2所示。

# 3.2 数据预处理

为了防止属性值之间差距过大，而影响算法的迭代过程。因此，在进行算法实验之前，对原始数据进行归一化处理。

对于数据表中的任一特征属性，选取该特征属性数值中的最大取值，然后将所有样本的该属性值除以上述最大值得到各样本对应的归一化值。即计算公式如下所示：

$$
{ x _ { i , j } } ^ { \mathrm { ' } } { = } \frac { x _ { i , j } } { \operatorname* { m a x } ( x _ { j } ) } , i { = } 1 , \cdots , m ; j { = } 1 , \cdots , N
$$

其中： $\operatorname* { m a x } ( x _ { j } )$ 表示样本第 $j$ 个特征属性数值中的最大值。

表2实验数据集  

<html><body><table><tr><td>数据集名</td><td>样本数</td><td>特征数</td><td>类别数</td><td>正类数/负类数</td><td>IL</td></tr><tr><td>Sonar</td><td>208</td><td>60</td><td>2</td><td>97/111</td><td>1.14</td></tr><tr><td>Ionosphere</td><td>351</td><td>34</td><td>2</td><td>126/225</td><td>1.79</td></tr><tr><td>Seeds</td><td>210</td><td>7</td><td>3</td><td>70/140</td><td>2.00</td></tr><tr><td>Wine</td><td>178</td><td>13</td><td>3</td><td>48/130</td><td>2.71</td></tr><tr><td>Ecoli</td><td>336</td><td>7</td><td>8</td><td>52/284</td><td>5.46</td></tr><tr><td>Fertility</td><td>100</td><td>9</td><td>2</td><td>12/88</td><td>7.33</td></tr><tr><td>Balance</td><td>625</td><td>4</td><td>3</td><td>49/576</td><td>11.76</td></tr><tr><td>Glass</td><td>214</td><td>9</td><td>7</td><td>13/201</td><td>15.46</td></tr><tr><td>Page-</td><td>5473</td><td>10</td><td>5</td><td>88/5385</td><td>61.19</td></tr><tr><td>Yeast</td><td>1484</td><td>8</td><td>10</td><td>20/1464</td><td>73.20</td></tr></table></body></html>

经过上述处理后，各样本的特征属性值转换为[0,1]的数，同时这也消除了量纲的影响，且便于后续的迭代计算。

# 3.3对比实验与结果分析

本文实验采用了五折交叉验证，通过随机地将数据集等分成五份，每次将其中的一份数据集将其中的作为测试集，另外四份则作为训练集。最后，将五次实验得到评价指标值（包括正确率、G-mean值、少数类查准率与查全率）的平均值，即作为该算法测试的最终评价结果。其中，正确率虽然对于不平衡数据分类的效果评价上存在缺陷，但本文计算该值主要是用作对比说明。

为了验证KFDA-Boosting算法对不平衡数据分类的有效性，本文与其他六种算法进行对比实验，即决策树（DT）、支持向量机（SVM）、人工神经网络（ANN）、核Fisher判别分析(KFDA）基于代价敏感的决策树（CS-DT）、结合过采样SMOTE 算法的支持向量机（SMOTE-SVM)。其中 SVM、KFDA 与 KFDA-Boosting使用的是同种核函数，即RBF核，且最大迭代次数设置为200。另外，为了便于比较，其中的SMOTE-SVM和CS-DT参数设置方式分别同文献[3,8]。

通过实验得到以上七种算法的正确率、G-mean 值、正类查准率和查全率最终结果，其对比情况分别如表3\~6所示。为了更加直观地比较分析各算法的分类效果，将表3\~6中的测试结果绘制成对应的折线图，如图1\~4所示。

表3各算法测试的正确率对比情况  

<html><body><table><tr><td>编号</td><td>数据集名</td><td>DT</td><td>SVM</td><td>ANN</td><td>KFDA</td><td>CS-DT</td><td>SMOTE-SVM</td><td>KFDA-Boosting</td></tr><tr><td>1</td><td>Sonar</td><td>0.7200</td><td>0.8621</td><td>0.8196</td><td>0.8103</td><td>0.8516</td><td>0.8856</td><td>0.8276</td></tr><tr><td>2</td><td>Ionosphere</td><td>0.8429</td><td>0.8714</td><td>0.8429</td><td>0.9285</td><td>0.8757</td><td>0.9247</td><td>0.9428</td></tr><tr><td>3</td><td>Seeds</td><td>0.8535</td><td>0.9167</td><td>0.9167</td><td>0.9048</td><td>0.8975</td><td>0.9375</td><td>0.9286</td></tr><tr><td>4</td><td>Wine</td><td>0.9558</td><td>0.9470</td><td>0.9667</td><td>0.9485</td><td>0.9683</td><td>0.9653</td><td>0.9874</td></tr><tr><td>5</td><td>Ecoli</td><td>0.7264</td><td>0.9254</td><td>0.5475</td><td>0.6870</td><td>0.9628</td><td>0.9528</td><td>0.9491</td></tr><tr><td>6</td><td>Fertility</td><td>1.0000</td><td>0.8808</td><td>1.0000</td><td>0.8168</td><td>1.0000</td><td>0.9112</td><td>0.9625</td></tr><tr><td>7</td><td>Balance</td><td>0.5585</td><td>0.7546</td><td>0.8992</td><td>0.6960</td><td>0.8239</td><td>0.8967</td><td>0.9040</td></tr><tr><td>8</td><td>Glass</td><td>0.8926</td><td>0.9444</td><td>0.9302</td><td>0.7701</td><td>0.9153</td><td>0.9513</td><td>0.9247</td></tr><tr><td>9</td><td>Page-Blocks</td><td>0.9569</td><td>0.9508</td><td>0.9673</td><td>0.8537</td><td>0.9571</td><td>0.9281</td><td>0.9486</td></tr><tr><td>10</td><td>Yeast</td><td>0.9623</td><td>0.9822</td><td>0.9865</td><td>0.9833</td><td>0.9586</td><td>0.9845</td><td>0.9857</td></tr></table></body></html>

表4各算法测试的G-mean值对比情况  

<html><body><table><tr><td>编号</td><td>数据集名</td><td>DT</td><td>SVM</td><td>ANN</td><td>KFDA</td><td>CS-DT</td><td>SMOTE-SVM</td><td>KFDA-Boosting</td></tr><tr><td>1</td><td>Sonar</td><td>0.5960</td><td>0.8610</td><td>0.6975</td><td>0.7542</td><td>0.8235</td><td>0.8663</td><td>0.8424</td></tr><tr><td>2</td><td>Ionosphere</td><td>0.8435</td><td>0.8919</td><td>0.7755</td><td>0.8512</td><td>0.8652</td><td>0.9111</td><td>0.9271</td></tr><tr><td>3</td><td>Seeds</td><td>0.8008</td><td>0.9106</td><td>0.9192</td><td>0.9250</td><td>0.8896</td><td>0.9467</td><td>0.9445</td></tr><tr><td>4</td><td>Wine</td><td>0.9252</td><td>0.9265</td><td>0.9542</td><td>0.9236</td><td>0.9578</td><td>0.9655</td><td>0.9837</td></tr><tr><td>5</td><td>Ecoli</td><td>0.7096</td><td>0.8706</td><td>0.6041</td><td>0.6996</td><td>0.8875</td><td>0.8766</td><td>0.8558</td></tr><tr><td>6</td><td>Fertility</td><td>1.0000</td><td>0.0000</td><td>1.0000</td><td>0.8885</td><td>1.0000</td><td>0.8589</td><td>0.9787</td></tr><tr><td>7</td><td>Balance</td><td>0.0000</td><td>0.4517</td><td>0.5638</td><td>0.7324</td><td>0.7853</td><td>0.8574</td><td>0.8622</td></tr><tr><td>8</td><td>Glass</td><td>0.8702</td><td>0.9014</td><td>0.9247</td><td>0.8732</td><td>0.8827</td><td>0.9375</td><td>0.9289</td></tr><tr><td>9</td><td>Page-Blocks</td><td>0.7806</td><td>0.8127</td><td>0.8806</td><td>0.8208</td><td>0.9264</td><td>0.9051</td><td>0.9325</td></tr><tr><td>10</td><td>Yeast</td><td>0.0984</td><td>0.5891</td><td>0.6228</td><td>0.8052</td><td>0.7153</td><td>0.7468</td><td>0.9464</td></tr></table></body></html>

表5各算法测试的正类查准率对比情况  

<html><body><table><tr><td>编号</td><td>数据集名</td><td>DT</td><td>SVM</td><td>ANN</td><td>KFDA</td><td>CS-DT</td><td>SMOTE-SVM</td><td>KFDA-Boosting</td></tr><tr><td>1</td><td>Sonar</td><td>0.7188</td><td>0.8468</td><td>0.7941</td><td>0.8095</td><td>0.7425</td><td>0.8451</td><td>0.8293</td></tr><tr><td>2</td><td>Ionosphere</td><td>0.7586</td><td>0.7429</td><td>0.9412</td><td>0.8422</td><td>0.8530</td><td>0.8783</td><td>0.9055</td></tr><tr><td>3</td><td>Seeds</td><td>0.8162</td><td>0.8643</td><td>0.8467</td><td>0.7875</td><td>0.8817</td><td>0.9034</td><td>0.8889</td></tr><tr><td>4</td><td>Wine</td><td>0.9267</td><td>1.0000</td><td>0.9091</td><td>0.9546</td><td>0.9315</td><td>0.9785</td><td>0.9764</td></tr><tr><td>5</td><td>Ecoli</td><td>0.3043</td><td>0.7273</td><td>0.2051</td><td>0.2571</td><td>0.8914</td><td>0.9645</td><td>0.8876</td></tr><tr><td>6</td><td>Fertility</td><td>1.0000</td><td></td><td>1.0000</td><td>0.4805</td><td>1.0000</td><td>0.9216</td><td>0.9560</td></tr><tr><td>7</td><td>Balance</td><td>0.0000</td><td>0.0903</td><td>0.4570</td><td>0.1628</td><td>0.7563</td><td>0.8212</td><td>0.8547</td></tr><tr><td>8</td><td>Glass</td><td>0.5443</td><td>0.4536</td><td>0.6521</td><td>0.2404</td><td>0.8145</td><td>0.8776</td><td>0.8643</td></tr><tr><td>9</td><td>Page-Blocks</td><td>0.5455</td><td>0.5455</td><td>0.7619</td><td>0.7182</td><td>0.8457</td><td>0.8125</td><td>0.8768</td></tr><tr><td>10</td><td>Yeast</td><td>0.0265</td><td>0.5869</td><td>0.6733</td><td>0.6576</td><td>0.7542</td><td>0.8234</td><td>0.8538</td></tr></table></body></html>

表6各算法测试的正类查全率对比情况  

<html><body><table><tr><td>编号</td><td>数据集名</td><td>DT</td><td>SVM</td><td>ANN</td><td>KFDA</td><td>CS-DT</td><td>SMOTE-SVM</td><td>KFDA-Boosting</td></tr><tr><td>1</td><td>Sonar</td><td>0.6216</td><td>0.8789</td><td>0.7297</td><td>0.9120</td><td>0.8134</td><td>0.9268</td><td>0.9189</td></tr><tr><td>2</td><td>Ionosphere</td><td>0.8462</td><td>0.9546</td><td>0.6154</td><td>0.9873</td><td>0.9673</td><td>0.9531</td><td>0.9857</td></tr><tr><td>3</td><td>Seeds</td><td>0.7857</td><td>0.8929</td><td>0.9286</td><td>1.0000</td><td>0.8913</td><td>0.9876</td><td>1.0000</td></tr><tr><td>4</td><td>Wine</td><td>1.0000</td><td>0.9169</td><td>1.0000</td><td>1.0000</td><td>1.0000</td><td>0.9543</td><td>1.0000</td></tr><tr><td>5</td><td>Ecoli</td><td>0.7236</td><td>0.8208</td><td>0.8000</td><td>0.9122</td><td>0.9351</td><td>0.9218</td><td>0.9265</td></tr><tr><td>6</td><td>Fertility</td><td>1.0000</td><td>0.0000</td><td>1.0000</td><td>1.0000</td><td>1.0000</td><td>0.8765</td><td>1.0000</td></tr><tr><td>7</td><td>Balance</td><td>0.0000</td><td>0.2592</td><td>0.3386</td><td>0.5778</td><td>0.7868</td><td>0.8427</td><td>0.8905</td></tr><tr><td>8</td><td>Glass</td><td>1.0000</td><td>1.0000</td><td>1.0000</td><td>1.0000</td><td>1.0000</td><td>1.0000</td><td>1.0000</td></tr><tr><td>9</td><td>Page-Blocks</td><td>0.6777</td><td>0.6667</td><td>0.8889</td><td>0.7533</td><td>0.8562</td><td>0.9414</td><td>0.9353</td></tr><tr><td>10</td><td>Yeast</td><td>0.0575</td><td>0.5586</td><td>0.4563</td><td>0.7342</td><td>0.7896</td><td>0.8011</td><td>0.9279</td></tr></table></body></html>

由图1和2可以看出，与DT、SVM、ANN及两种改进的分类算法（CS-DT、SMOTE-SVM）相比，在表3中的五个数据集测试结果上，本文KFDA-Boosting算法的G-mean值最大，而在其他数据集上的G-mean值与对应的最大值相差并不大，这表明本文算法整体分类效果良好。当数据集的不平衡度逐渐增大时，与传统的DT和SVM算法相比，CS-DT和SMOTE-SVM在个数据集上测试的G-mean 值均有不同程度的增大，整体分类效果得到较好地改善。而在不平衡度增大一定程度时，本文算法仍具有很大的G-mean值，且相对优于CS-DT和SMOTE-SVM两种改进算法的对应值，如测试集Page-Blocks、Yeast。与此同时，DT、SVM、ANN三种算法测试的正确率虽均达到了 $90 \%$ 以上，但其对应的G-mean值却较小。

在图3与4中进一步可以看出，随着不平衡度逐渐增大，KFDA-Boosting在对应数据集上测试的正类查准率与查全率两项指标的均值都很大，而其他算法的对应值相对较小，该情况在呈非线性特征的不平衡数据测试上表现得尤为明显，例如数据集Yeast，这表明本文算法能有效利用样本的非线性特征，且对少数类样本具有很强的识别能力。从侧面也证实了，分类正确率作为不平衡数据分类的评价指标有时并不能有效地衡量分类器的分类效果。

![](images/d085db0cac65d1ad9bf5d02d0437aa225305e527610cbc25f75be37ed9eeb6ce.jpg)  
图1各算法测试的正确率对比

![](images/c1c803c266934ec56f3a9f67be67bf3cd56ad8ea016149d137db8bd79c018818.jpg)  
图2各算法测试的G-mean 值对比图

![](images/39218e1eef463483b94313a678468751e3b0820d19a9030d808d14300f0d2c88.jpg)  
图3各算法测试的正类查准率对比

![](images/29b1a3dcb77b5f69047e315ecf27a480377185919ee777f83263909d2e2e6d94.jpg)  
图4各算法测试的正类查全率对比图

同时还可以看出，对于同一数据集，KFDA-Boosting算法的G-mean 值及正类查准率大于KFDA对应的值。除数据集Ionosphere外，本文算法的正类查全率大于KFDA对应的指标值或与对应最优值相当，这表明本文提出的算法，与单独采用KFDA相比，分类效果有很大地提升，尤其是针对正类样本的识别。

此外，进一步可以算出各种分类算法测试的G-mean值方差分别为0.1173、0.0889、0.0263、0.0063、0.0069、0.0039、0.0025，由此可说明，针对不同的数据集，本文提出的KFDA-Boosting算法与其他分类算法相比，整体分类具有较好的稳定性。

# 4 结束语

对于不平衡数据分类中，数据特征越来越呈现非线性，加大了识别少数类的困难，本文提出了一种基于改进的核Fisher判别分析与 Boosting 算法的分类方法，即 KFDA-Boosting 算法。该算法能有效利用样本特征，尤其是非线性特征，以实现对原始数据的非线性判别，保证了样本的最佳可分离性。最后，本文算法通过对UCI中的10个数据集的测试实验表明，对于不平衡度较大或呈非线性特征的数据，本文算法分类的效果显著，与DT、SVM、ANN、KFDA、CS-DT、SMOTE-SVM相比，KFDA-Boosting算法能有效地识别少数类，表现出良好的整体分类效果，并具有较好的稳定性。这也证明了该算法在处理不平衡数据分类问题的可行性和有效性。

为了扩大本文算法对不平衡数据分类的适用性，后续研究将考虑多分类问题及相应的评价指标，并进一步改善本文算法对不平衡数据的分类性能。

# 参考文献：

[1]Laurikkala J. Improving identification of difficult small classes by balancingclass distribution [C]//Proc of the 8th Conference on AI in Medicine.2001:63-66.  
[2]Chawla NV,Bowyer K W,HallL O,et al. SMOTE: synthetic minority over-sampling technique [J].Artificial Intelligence Research,2002,16 (3): 321-357.  
[3]郑文昌，陈淑燕，王宣强．面向不平衡数据集的 SMOTE-SVM 交通事件检测算法[J].武汉理工大学学报,2012,34(11): $5 8 \substack { - 6 2 + 1 2 3 }$ #  
[4]衣柏衡，朱建军，李杰．基于改进 SMOTE的小额贷款公司客户信用风险非均衡 SVM分类 [J]．中国管理科学,2016,24(03):24-30.  
[5]杨毅，卢诚波，徐根海．面向不平衡数据集的一种精化BorderlineSMOTE方法[J]．复旦学报：自然科学版,2017,56(05):537-544.  
[6]蒋盛益，谢照青，余雯．基于代价敏感的朴素贝叶斯不平衡数据分类研究[J].计算机研究与发展,2011,(S1):387-390.  
[7]李勇，刘战东，张海军．不平衡数据的集成分类算法综述[J].计算机应用研究,2014,31(5):1287-1291.  
[8]邹鹏，莫佳卉，江亦华，等．基于代价敏感决策树的客户价值细分[J].管理科学,2011,24(2):20-29.  
[9]师彦文，王宏杰．基于新型不纯度度量的代价敏感随机森林分类器[J]计算机科学,2017,44(S2):98-101.  
[10]SchapireRE.The strength of weak learnability[C]//Proc of the 2nd AnnualWorkshop on Computational Learning Theory.1989:197-227.  
[11]Breiman L.Bagging predictors [J].Machine Learning,1996,24(2):123-140.  
[12]LiK,Fang X,Zhai J,etal.An imbalanced data classification method drivenby boundary samples-boundary-boost [C]//Proc of International Conferenceon Information Science and Control Engineering.2016: 194-199.  
[13]胡小生，温菊屏，钟勇．动态平衡采样的不平衡数据集成分类方法[J].智能系统学报,2016,11(02):257-263.  
[14]秦孟梅，邱建林，陆鹏程，等．基于AdaBoost的类不平衡学习算法[J].计算机应用研究,2017,34(11):3229-3232+3254.  
[15]应维云，蔺楠，谢雅雅，等．用LDABoosting 算法进行客户流失预测[J]．数理统计与管理,2010(3):400-408.  
[16]李诒靖，郭海湘，李亚楠，等．一种基于Boosting 的集成学习算法在不均衡数据中的分类[J]．系统工程理论与实践,2016(1):189-199.  
[17]王璐林．面向不平衡样本的Boosting分类算法研究[D].哈尔滨：哈尔滨工业大学,2013.  
[18]李想.Boosting分类算法的应用与研究[D].兰州：兰州交通大学,2012.  
[19]常志朋，程龙生．核Fisher判别分析多参数自动优化算法[J]．系统工程与电子技术,2013,(01):212-217.  
[20]李建云，邱菀华．核Fisher 判别分析方法评估消费者信用风险[J]．系统工程理论方法应用,2004(6):548-552+556.