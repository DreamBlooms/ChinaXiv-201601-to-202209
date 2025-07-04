# 一种改进过采样算法在类别不平衡信用评分中的应用‘

邵良杉，周玉

(辽宁工程技术大学 系统工程研究所，辽宁 葫芦岛 125105)

摘要：针对信贷行业信用评分业务中存在的样本类别不平衡问题，首先在信用评分各影响因素Fisher比率值分析的基础上确定主要评判指标；而后以基于支持度的过采样算法（SDSMOTE）为样例合成算法，支持向量机（SVM）为基预测器，Boosting 算法为框架构建基于Fisher-SDSMOTE-ESBoostSVM的类别不平衡信用评分预测模型；并在基分类器训练结束后引入“淘汰策略”，删除未被正确分类的合成样例，重新生成正类样例并修正样例权重；最后以UCI数据库中德国信用数据集为实验样本，F-measure值和G-mean值为评价指标，对比分析Fisher-SDSMOTE-ESBoostSVM与其他集成学习算法的预测结果。实验结果表明，Fisher-SDSMOTE-ESBostSVM算法应用到信贷行业客户信用评分预测中具有可行性和适应性，且预测准确率较高，具有一定的实际应用价值。

关键词：信用评分；类别不平衡；SDSMOTE 算法；Fisher准则；支持向量机；集成学习 中图分类号：TP391 doi:10.3969/j.issn.1001-3695.2017.12.0798

# Application of improved oversampling algorithm in class-imbalance credit scoring

Shao Liangshan, Zhou Yu (System Engineering Institute Liaoning Technical University,Huludao Liaoning 125105,China)

Abstract:Inviewoflass-imbalance inrealcreditsoringbusinessofcredit industry,firstlydeterminingthe ainealuation indicators ofcredit scoring basedonacomprehensive analysis of the influence factors'Fisherratiovalue.Then,choosing the SMOTE based on support degree(SDSMOTE) oversampling algorithm to synthesize new samples,SVM played as the base predictorand Boosting algorithm as theframework,acreditscoring predictionmodel whichassociatedclass-imbalance with Fisher-SDSMOTE-ESBoostSVMtheorywasproposed.Besides,the"eliminationstrategy"wasintroducedtodeletethesythetic sample which was notclasified accurately,after thatsynthesized thenew positive classample againand modifiedthe sample weight.Fnally,teGermancreditdataset inthe UCIdatabase wasselectedastheexperimentaldataset,andF-measure vale and G-mean value as evaluation standard,comparing and analyzing the predictionresult ofFisher-SDSMOTE-ESBoostSVM modelandothers ensemble learning algorithm.Experimental results show that the application of Fisher-SDSMOTEESBoostSVMalgorithm tocustomercredit scoreprediction is feasible andapplicable,andshowahigh level ofaccuracy,which proved that the algorithm have a certain practical application value.

Keywords:creditscoring;clas-imbalance;SDMOTEalgorithm;Fishercriterion;supportvectormachine; ensembleleaing

# 0 引言

信用评分模型是一种以客户的信用历史资料为依据，为保障各类金融行业的金融安全、运用定量统计分析方法而设定的一种评估或预测信用风险的划定模型。近年来信贷行业规模和涉及领域不断扩大使得信用评分问题日益突出，如何建立高效、可靠的信用评分模型显得尤为重要。

目前，已有一些学者将基于统计和机器学习的方法应用到信用评分模型构建中，如逻辑回归[1]、支持向量机[2]、提升树[3]等方法，并取得了较好的效果。但应用信用评分模型解决实际问题的过程中存在一些不容忽视的问题，如前期筛选使得"好”客户数量较“坏”客户多，将“好”客户错分为“坏”客户与将“坏”客户错分为“好”客户的代价是不同的，信用评分模型所涉及评判指标的维度较高、数据之间存在冗余等。因此构建信用评分模型是一种类别不平衡、数据间冗余较高的学习问题。目前，采样和代价敏感学习是处理类不平衡问题的常用方法。代价敏感学习要求明确错分的代价，而信贷业务中较难准确评估错分的代价，在实际问题中更多地采用采样的方法。采样方法分为过采样和欠采样方法两种，随机欠采样主要是随机删除负类（多数类）中部分样例，对正类（少数类）没有采取任何操作，Herrera[4] 提出一种基于K-nearest neighbor 的有指导的欠采样方法，通过保留正类附近的负类样本有效避免关键信息丢失；Blake 等人[5]提出BalanceCascade 算法，对负类样例不重复采样、固定正类样例，最终建立多个子分类器形成联合分类器。但欠采样方法在删除负类样例的过程中，难免会删除部分含有效信息的负类样例。随机过采样通过随机复制正类样例改善了类间不平衡度，但易出现过拟合问题，对此学者们提出了不同的改进方法，Chawla等人[提出一种新的过采样方法 SMOTE(synthetic minority over-sampling technique)，通过在正类样例及其临近正类样例连线上随机选取一点合成正类样例来解决数据失衡问题；Han等人[在SMOTE 算法的基础上提出了Borderline-SMOTE 算法，通过在边缘区域内进行插值使新生成样本更加有效；Nakamura等人[8]提出基于密度的SMOTE改进算法，根据正类样本的分类密度形成聚类簇来控制新样本的合成。

在现有研究的基础上，本文提出一种基于支持度的改进过采样 SMOTE 算法—SDSMOTE(SMOTE based on support degreeSDSMOTE)来处理客户信用评分问题中类别不平衡问题，而后以Boosting集成学习方法为框架，SVM为基学习器，迭代过程中引入“淘汰策略”（eliminationstrategy)，删除被基分类器错误分类的正类合成样本来确保合成样本的质量；此外，鉴于信用评分问题涉及的评判指标维数较高，在合成正类样例前根据各指标Fisher比率值来筛选指标。

# 1 理论分析

# 1.1Boost-SVM 基本原理

支持向量机（support vector machine，SVM）[9,l0]核心思想是建立一个分类超平面作为决策曲面，最大化正负类之间的隔离边缘。SVM 首先设定训练集 $T = \left\{ ( x _ { 1 } , y _ { 1 } ) , \cdots , ( x _ { l } , y _ { l } ) \right\}$ ，其中$x _ { i } \in X$ 为特征向量， $y _ { i } \in Y = \{ + 1 , - 1 \}$ $( i = 1 , 2 , \cdots , l )$ ；选取适当的核函数 $K ( x _ { 1 } , x _ { 2 } )$ 和参数 $c$ ，构造求解最优化问题：

$$
\begin{array} { c } { { \displaystyle { \operatorname* { m i n } _ { \alpha } } \frac { 1 } { 2 } \sum _ { i = 1 } ^ { j } \sum _ { j = 1 } ^ { l } y _ { i } y _ { j } \alpha _ { i } \alpha _ { j } K ( x _ { i } , x _ { j } ) - \sum _ { j = 1 } ^ { l } \alpha _ { j } } } \\ { { s . t . \quad \displaystyle { \sum _ { i = 1 } ^ { l } } y _ { i } \alpha _ { i } = 0 , \quad \ 0 \leq \alpha _ { i } \leq C , i = 1 , \cdots , l } } \end{array}
$$

得到最优解： $\boldsymbol { \alpha } ^ { * } = ( \alpha _ { 1 } ^ { * } , \cdots \alpha _ { l } ^ { * } ) ^ { T }$ 。选取 $\alpha ^ { * }$ 的一个正分量$0 < \alpha _ { j } ^ { * } < C$ ，并据此计算阈值 $b ^ { * } = y _ { i } - \sum _ { i = 1 } ^ { l } y _ { i } \alpha _ { i } ^ { * } K ( x _ { i } - x _ { j } )$ ；构造决策函数：

$$
f ( x ) = \mathrm { s g n } ( \sum _ { i = 1 } ^ { l } \alpha _ { i } ^ { * } y _ { i } K ( x _ { 1 } , x _ { 2 } ) + b ^ { * } ) ~ \circ
$$

Boosting 算法与 SVM有一个共同点，即在学习过程中注重“最富信息”的样本点[11,12]。Boosting 算法在初次训练时赋予每个样本相同的概率，进入迭代后，对分类错误的样本加大权重使得在下一次迭代中可以更加关注这些点。Boost-SVM算法拟将支持向量机作为集成学习机框架的学习器，即以支持向量机为Boosting算法的基分类器，进一步提高学习机的泛化能力。

# 1.2改进的 SMOTE算法

SMOTE[13,14]基本思想是通过线性内插法在两个临近的正类样本中合成新的正类样本，其可有效避免过度拟合问题，但其无法指导如何选取正类样本及合成新样本。针对以上不足，本文提出一种基于支持度的 SDSMOTE 算法。SDSMOTE 算法通过计算各正类样本的支持度来确定边界样本，可以实现有选择、有差别地合成边界样本的目标，提高合成样本的质量。具体方法如下：

a)使用Tomeklinks数据清理技术对样本数据集中噪声点进行清除。b)设去除噪声后数据集中正类样本数为 $\mathbf { \Sigma } _ { m }$ ，负类样本数为$n$ ，样本维数为 $d$ 。随机选取一个正类样本 $X _ { i } = ( x _ { i 1 } , x _ { i 2 } , \cdots , x _ { i t } )$ （20（204号 $( i = 1 , 2 , \cdots , m )$ ，利用式（3）计算到 $X _ { i }$ 到每一个负类样本yj(j=1,2,,n）之间的欧式距离和。

$$
S _ { i } = \sum _ { j = 1 } ^ { n } \sqrt { ( x _ { i 1 } - y _ { j 1 } ) ^ { 2 } + \cdots + ( x _ { i d } - y _ { i d } ) ^ { 2 } }
$$

c)计算所有 $S _ { i }$ 加和，并以此根据式（4）计算得到正负类样本之间的平均距离：

$$
S _ { a v e } = { \sum _ { i = 1 } ^ { m } S _ { i } \mathord { \left/ { \vphantom { \sum _ { i = 1 } ^ { m } S _ { i } \left( m \times n \right) } } \right.}  \kern - delimiterspace } ( m \times n ) 
$$

d)将 $S _ { a v e }$ 设置为距离参数，选取一个正类样本 $X _ { i }$ 为圆心并以距离参数为半径画一个圆，计算每个圆区域内负类样本个数作为正类样本的支持度 $k _ { i }$ ，支持度较大意味着正类样本 $X _ { i }$ 被分配一个较高的选择可能性值 $P _ { i } = k _ { i } \Bigg / \sum _ { i = 1 } ^ { m } k _ { i }$ ；相反，样本会被分配一个较小Pi。

e)设定需要合成的正类样本数 $L$ 为数据集中正类样本与负类样本的差值，根据正类样本的 $P _ { i }$ 值，可以得到以每个正类样本附近需要合成的新样本个数 $l _ { i } = P _ { i } \cdot L$ ，设需要合成的正类样本为 $X _ { n e w } = \{ x _ { n e w 1 } , x _ { n e w 2 } , \cdots , x _ { n e w d } \}$ ，对被选的正类样本使用改进的差值公式：

$$
X _ { _ { n e w } } = X _ { i } + r a n d ( 0 , 1 ) \times \left( X _ { _ { m a x } } - X _ { i } \right)
$$

其中： $X _ { \mathrm { m a x } }$ 为以 $X _ { i }$ 为圆心的圆中距离 $X _ { i }$ 最远的正类样本点，添加新合成的样本到数据集中参与训练和测试。

# 1.3基于Fisher准则的特征选择

Fisher准则[15]是一种基于距离的特征选择方法之一，其基本思想是鉴别性能较强的特征，即表现为类内距离尽可能小，类间距离尽可能大的特征。采用单个特征的Fisher比值作为准则，并以此对特征进行排序，可以选出鉴别性能较强的特征，从而达到降维的目的。在特征选择过程中，设定存在训练样本{(x,y),(x,y),(xn,yn)}，其中n为样本数量，x∈R，k为特征向量的维数， $y _ { i } = \left\{ - 1 , 1 \right\} ^ { l }$ 为类别标号，1表示正类，-1表示负类。每一类中包含 $n _ { i }$ 个样本， ${ x _ { i } } ^ { ( k ) }$ ， $m _ { i } ^ { ( k ) }$ ， $m ^ { ( k ) }$ 分别为第$i$ 类样本 $x _ { i }$ ，第 $i$ 类样本的均值，所有样本的均值在第 $k$ 维上的取值。用 $S _ { B } ^ { ( k ) }$ 和 $S _ { \omega } ^ { ( k ) }$ 表示该维特征在训练样本集上的类间方差和类内方差。

$$
S _ { B } ^ { ( k ) } = \sum _ { i = 1 } ^ { 2 } \frac { n _ { i } } { n } \Big ( m _ { i } ^ { ( k ) } - m ^ { ( k ) } \Big ) ^ { 2 }
$$

$$
{ S _ { \omega } ^ { ( k ) } = \frac { 1 } { n } \sum _ { i = 1 } ^ { 2 } \sum _ { x \in \omega _ { i } } { ( x ^ { ( k ) } - m _ { i } ^ { ( k ) } ) } ^ { 2 } } = \frac { 1 } { n } ( { \delta _ { 1 } ^ { 2 } + \delta _ { 2 } ^ { 2 } } )
$$

则单个特征的Fisher准则比值可以表示为

$$
J _ { \it f i s h e r } ( k ) = S _ { \it B } ^ { ( k ) } \big / S _ { \omega } ^ { ( k ) }
$$

将 $J _ { \it f i s h e r }$ 称为特征的Fisher比率值，某维特征在训练集上的Fisher比率值越大，说明该维特征的类别区分度越好，包含越多的鉴别信息，噪声特征的 $J _ { \it f i s h e r }$ 值趋近于0。

# 2 仿真实验及性能分析

# 2.1Fisher-SDSMOTE-ESBoostSVM算法实现

本文首先根据Fisher比率值对各评判指标进行选择，而后借助过采样SDSMOTE算法合成正类样本，分类算法选取Boosting算法为框架并以SVM模型为基分类器，同时引入“淘汰策略”删除被基分类器错误分类的合成正类样例，最终构建基于Fisher-SDSMOTE-ESBoostSVM的类不平衡数据集分类模型。其具体实现过程如下：

a）输入样本数据Z，借助Fisher准则方法在样本集中进行权重计算，并输出特征权重向量W。根据特征权重值对属性进行筛选，构成降维后新的样本集S。b)输入新样本集，应用SDSMOTE 算法合成少数类样本。将合成样本添加到样本集S中。c）对新样本集中的每个样例设置相同的初始权重值。d）调用SVM学习算法，形成基分类器，借助Boosting权重更新过程使下一次迭代时，被当前基分类器错分的样例可以得到更多关注；同时引入“淘汰策略”，删除错误合成的正类样例，消除其对集成学习器分类效果的影响。e）根据正类样例减少个数重新执行SDSMOTE算法合成新样本，将合成样例添加实验样本集后重新规范化权值。权值计算公式如下：

$$
w ^ { n e w } _ { t } ( i ) = \left\{ \begin{array} { l l } { \displaystyle \frac { 1 } { n _ { t } } , } & { \quad x _ { i } \in S _ { t } } \\ { \displaystyle w ^ { n e w } _ { t } ( i ) \times \frac { n _ { t } - m } { n _ { t } } , } & { \quad x _ { i } \notin S _ { t } } \end{array} \right.
$$

其中： $w _ { t } ^ { o l d } \setminus w _ { t } ^ { n e w }$ 分别表示第 $\mathbf { \Phi } _ { t }$ 次迭代时，合成样例和原始样例权值； $n _ { t }$ 为训练样本个数； $\mathbf { \Sigma } _ { m }$ 为淘汰的正类合成样本个数； $S _ { \ t { t } }$ 为第 $\mathbf { \Phi } _ { t }$ 次迭代重新合成的正类样例集合。

f）重复执行d）e）步，直到达到迭代次数 $T$ ，计算各基分类器权重，最后组合基分类器形成强分类器。具体流程如图1所示。

![](images/a30f52e1ff6b86d351037e576f920242a83bbf0d9202d5e20c97a688a38fba0e.jpg)  
图1算法实现流程

# 2.2评价指标

单纯地将准确率（accuracy）作为模型分类效果的评价机制对不平衡数据来说意义不大，不少学者针对不平衡数据预测提出了一些更加合理的评价机制[16]，如特异性（specificity)）、敏感性（sensitivity）、正类的查准率（precision）、几何平均值（G-mean）、正类的F-measure值等。两类别情况下，正类和负类的预测情况可具体分为TP（实际正类，预测正类）、FP(实际负类，预测正类)、FN(实际负类，预测正类)、TN(实际负类，预测负类)四种。定义各度量计算公式为

特异性Specificity = $S p e c i f i c i t y = \frac { T N } { T N + F P }$   
敏感性 Sensitivity = $S e n s i t i \nu i t y = \frac { T P } { T P + F N }$   
正类查准率Precision = $P r e c i s i o n = \frac { T P } { T P + F P }$   
几何平均值 G-mean =Sensitivity·Specificity   
正类F-measure F-measure: $F - m e a s u r e = \frac { ( 1 + \beta ^ { 2 } ) S e n s i t i \nu i t y \cdot P r e c i s i o n } { \beta ^ { 2 } S e n s i t i \nu i t y + P r e c i s i o n }$

在仅考虑模型正类预测性能的情况下，敏感性 sensitivity 和正类查准率precision是相对重要的度量，正类F-measure 值是敏感性和查准率的调和均值，其计算结果接近两者中的较小者，故较大的F-measure 值对应的 sensitivity 和 precision 较大，其中 $\beta$ 通常取值为1。需要同时考虑模型对两类的预测性能，即希望TP和TN都较大时，可以使用G-mean 衡量模型在两个类别上的平均性能。因此，本文选取正类F-measure 和G-mean作为模型分类效果的评价指标。

# 2.3算法有效性验证

为测试本文所建模型对类不平衡数据集的分类效果，选取了来自UCI数据库和KEEL数据库中5组不同的数据集进行实验，各数据集的特征信息如表1所示。实验过程中采用10折交叉验证（10-foldcross-validation）的测试方法，将数据集等分为10 份，轮流选择其中9份作为训练集，1份作为测试集。对10次实验结果中各度量值取均值作为模型的最终评价结果。经反复测试实验参数设置为：Boosting迭代次数为500次，基分类器分数为20个，SVM中核函数选择径向基（RBF）函数，核参数 $\gamma$ 取值为2， $c$ 取值为100。

表1不平衡数据集特征与分布  

<html><body><table><tr><td>数据集</td><td>特征</td><td>正类</td><td>负类</td><td>不平衡比</td><td>约简特征</td></tr><tr><td>Pima</td><td>8</td><td>268</td><td>500</td><td>0.538</td><td>7</td></tr><tr><td>Ionosphere</td><td>34</td><td>126</td><td>225</td><td>0.563</td><td>29</td></tr><tr><td>wpbc</td><td>35</td><td>46</td><td>148</td><td>0.316</td><td>31</td></tr><tr><td>Wine</td><td>13</td><td>48</td><td>178</td><td>0.266</td><td>11</td></tr><tr><td>Sonar</td><td>60</td><td>77</td><td>168</td><td>0.449</td><td>52</td></tr></table></body></html>

为同时验证所提出的Fisher-SDSMOTE-ESBoostSVM算法中 SDSMOTE的性能、特征提取及“淘汰策略”的有效性。实验另外分别测试不经特征提取使用的 SMOTE-BoostSVM、SDSMOTE-BoostSVM 算法，采用特征提取的Fisher-SMOTE-BoostSVM、Fisher-SDSMOTE-BoostSVM四种算法所得出的specificity、sensitivity、F-measure 和G-mean 值。表1最后一栏中列出了Fisher准则提取的特征数情况。表2为以上五种算法的各评价指标值的对比情况。

分析表2可以看出，经特征提取的两类算法和不经过特征提取的两类算法的比较中，显然经过特征提取的算法分类效果较好，说明Fisher算法有效地提取出了关键属性，剔除了不相关或冗余的特征，达到了提高模型精确度，减少运行时间的目的。而Fisher-SDSMOTE-BoostSVM 的分类效果要远好于Fisher-SMOTE-BoostSVM算法，说明基于SDSMOTE算法通过有选择、有差别地合成边界样本目标，在一定程度上有效避免了SMOTE合成新样本的盲目性，提高了正类合成样本的质量进而提高正类样本的分类准确率。Fisher-SDSMOTE-ESBoostSVM算法分类效果更优于Fisher-SDSMOTE-BoostSVM算法具有大幅度提升，表明结合“淘汰策略”的SDSMOTE-BoostSVM 算法具有更好的分类性能。综合以上实验结果表明，本文所构建的Fisher-SDSMOTE-ESBoostSVM分类器模型，在不同空间结构以及不同维度的不平衡数据集下拥有更强的正负类识别率、更好的综合性能。

表25种不平衡数据集的评价机制数值  

<html><body><table><tr><td>数据集</td><td>算法</td><td>Specificity</td><td>Sensitivity</td><td>G-mean</td><td>F-measure</td></tr><tr><td rowspan="5">Pima</td><td>SMOTE-Bo0stSVM</td><td>0.704 ± 0.43</td><td>0.559± 0.133</td><td>0.627 ± 0.036</td><td>0.642 ± 0.042</td></tr><tr><td>Fisher-SMOTE-BoostSVM</td><td>0.778± 0.21</td><td>0.611 ± 0.104</td><td>0.687± 0.030</td><td>0.698± 0.035</td></tr><tr><td>SDSMOTE- BoostSVM</td><td>0.740± 0.52</td><td>0.724 ± 0.039</td><td>0.732 ± 0.025</td><td>0.764± 0.037</td></tr><tr><td>Fisher-SDSMOTE-BoostSVM</td><td>0.81 ± 0.034</td><td>0.798 ± 0.24</td><td>0.804 ± 0.013</td><td>0.823 ± 0.028</td></tr><tr><td>本文算法</td><td>0.959 ± 0.017</td><td>0.893 ± 0.016</td><td>0.925±0.009</td><td>0.894±0.006</td></tr><tr><td rowspan="6">Ionosphere</td><td>SMOTE- Bo0stSVM</td><td>0.741± 0.149</td><td>0.55 ± 0.109</td><td>0.638 ± 0.059</td><td>0.658 ± 0.102</td></tr><tr><td>Fisher-SMOTE-BoostSVM</td><td>0.765 ± 0.103</td><td>0.625 ± 0.082</td><td>0.691 ± 0.083</td><td>0.735 ± 0.087</td></tr><tr><td>SDSMOTE- Bo0stSVM</td><td>0.79 ± 0.078</td><td>0.692± 0.091</td><td>0.739 ± 0.071</td><td>0.781± 0.074</td></tr><tr><td>Fisher-SDSMOTE-BoostSVM</td><td>0.823 ± 0.066</td><td>0.796 ± 0.054</td><td>0.809 ±0.052</td><td>0.847 ± 0.067</td></tr><tr><td>本文算法</td><td>0.881± 0.050</td><td>0.962 ± 0.031</td><td>0.921 ± 0.039</td><td>0.884 ± 0.044</td></tr><tr><td>SMOTE- BoostSVM</td><td>0.692 ± 0.119</td><td>0.604 ±0.086</td><td>0.647 ± 0.087</td><td>0.654 ± 0.074</td></tr><tr><td rowspan="5">wpbc</td><td>Fisher-SMOTE-BoostSVM</td><td>0.797 ± 0.082</td><td>0.682 ± 0.073</td><td>0.737 ± 0.065</td><td>0.773 ± 0.053</td></tr><tr><td>SDSMOTE- BoostSVM</td><td>0.826±0.082</td><td>0.753 ± 0.076</td><td>0.788± 0.076</td><td>0.766 ± 0.062</td></tr><tr><td>Fisher-SDSMOTE-BoostSVM</td><td>0.857 ± 0.073</td><td>0.785 ± 0.062</td><td>0.820 ± 0.062</td><td>0.833 ± 0.047</td></tr><tr><td>本文算法</td><td>0.907± 0.056</td><td>0.894 ± 0.044</td><td>0.901 ± 0.037</td><td>0.880±0.021</td></tr><tr><td>SMOTE- BoostSVM</td><td>0.692 ± 0.111</td><td>0.604 ± 0.097</td><td>0.647 ± 0.089</td><td>0.647 ± 0.102</td></tr><tr><td>Wine</td><td>Fisher-SMOTE-BoostSVM</td><td>0.763 ±0.089</td><td>0.745 ± 0.064</td><td>0.754 ± 0.076</td><td>0.742 ± 0.082</td></tr><tr><td>(3vs other)</td><td>SDSMOTE- B00stSVM</td><td>0.802 ± 0.091</td><td>0.812 ± 0.063</td><td>0.807 ± 0.065</td><td>0.809 ± 0.073</td></tr><tr><td rowspan="8"></td><td>Fisher-SDSMOTE- BoostSVM</td><td>0.843 ± 0.074</td><td>0.832 ± 0.045</td><td></td><td></td></tr><tr><td>本文算法</td><td>0.923 ±0.032</td><td></td><td>0.837 ± 0.051</td><td>0.855 ± 0.057</td></tr><tr><td>SMOTE- BoostSVM</td><td>0.702 ±0.109</td><td>0.909 ± 0.036 0.572 ± 0.098</td><td>0.916 ± 0.033</td><td>0.925 ± 0.028</td></tr><tr><td>Fisher-SMOTE-BoostSVM</td><td>0.786 ± 0.082</td><td>0.595 ± 0.076</td><td>0.634 ± 0.122 0.684 ± 0.082</td><td>0.658 ± 0.097 0.736±0.067</td></tr><tr><td>SDSMOTE- BoostSVM</td><td>0.825 ± 0.087</td><td>0.727 ± 0.069</td><td>0.774 ± 0.065</td><td>0.798 ± 0.059</td></tr><tr><td>Fisher-SDSMOTE-BoostSVM</td><td>0.866 ± 0.056</td><td>0.776 ± 0.102</td><td>0.820 ± 0.058</td><td>0.845 ± 0.065</td></tr><tr><td>本文算法</td><td></td><td></td><td></td><td></td></tr><tr><td></td><td>0.947 ± 0.047</td><td>0.891±0.049</td><td>0.919±0.043</td><td>0.914 ± 0.023</td></tr></table></body></html>

# 2.4Fisher-SDSMOTE-ESBoosting 算法鲁棒性对比分析

为检验所构建模型的鲁棒性，采用参考文献[17]中的鲁棒

性评价机制对以上5种算法的鲁棒性进行对比分析，将算法 $m$ 在某一特定数据集上的相对性能用该算法在求解问题时得到的

AdjustedRandIndex的值与最大AdjustedRandIndex值的比值表示。具体计算方法为

$$
b _ { \phantom { ' } m } { = } R _ { m } / m a x ( R _ { m } ) \qquad \qquad m = 1 , 2 , \cdots , k
$$

# (10)

在某个数据集上表现最好的算法 $m ^ { * }$ 对应的性能 $b _ { _ { m ^ { * } } }$ 为1,而其他算法的相对性能 $b _ { _ { m ^ { * } } }$ 小于1，且 $b _ { _ m ^ { * } }$ 值越大，相应算法 $m$ 在所有算法中的相对性能越好。因此，本文选取各算法在所有数据集上的 $b _ { _ m ^ { \dagger } }$ 值的总和来评价其鲁棒性，总和值越大算法的鲁棒性越强。同样选择以上5个数据集为测试数据，将正类与负类样例按1：10的比例进行选取，并借助10折交叉验证法进行测试。各算法参数设置同上。图2为5种算法的G-mean 评价指标的鲁棒性对比（限于篇幅对各算法进行缩写）。

![](images/13cafee5fa0b52fae6ed86401e1a41f25bd2c521d7ea0fc13569bf701880bedf.jpg)  
图2不平衡数据下G-mean 的AdjustedRand Index 鲁棒性能比较

由图2可知，本文所提的Fisher-SDSMOTEESBoostSVM算法对各数据集的 $b _ { { } _ { m } }$ 均为1，且具有最高的总和值，表明所提算法对不同空间结构及不同维度的数据不均衡分类问题均表现出良好的性能，在对比的其他四种算法中具有最好的鲁棒性。这是由于本文算法不仅考虑了样本的属性特性，利用改进的SDSMOTE算法使过采样更具针对性，而引入的“淘汰策略”对合成的正类样例进行二次筛选，提高了合成样本的质量，进而提高了模型的分类准确率。

# 3 算法在信用评分中的应用

# 3.1数据准备和预处理

本文选用UCI数据集中German公开数据集，该数据集中包含1000条贷款申请记录，其中700条为信誉良好的“good”客户，300条存在违约情况的“bad”客户。数据集中每条记录对应20个变量描述其特征属性，其中定量数据类型定属为13个，包括现有账户状况、信用记录、信贷目的、储蓄账户、当前工龄、婚姻状况、其他应收账款、抵押类型、其他分期付款计划、住房情况、工作状态、电话状态、是否为外籍工作者；7种数值属性包括持续时间，借贷额度、分期付款金额占可支配收入比例，现居住地居住时间，年龄、未清还贷款金额，蟾养人数。

令 $X = ( x _ { 1 } , x _ { 2 } , \cdots x _ { n } ) ^ { T }$ 代表信用评分参考信息变量，每个样例可表示为 $x _ { i } = ( x _ { i 1 } , x _ { i 2 } , \cdots , x _ { n i } ) ^ { T }$ ，全部样本可表示为 $S = \{ ( x _ { i } , y _ { i } ) \}$ ，i=1,2,…,N；y代表客户贷款偿还情况，$I = \{ i \vert y _ { i } = 1 , i \in N , ( x _ { i } , y _ { i } ) \in S \}$ 表示信用良好的客户，$J = \{ i \vert y _ { i } = - 1 , i \in N , ( x _ { i } , y _ { i } ) \in S \}$ 表示信用较差的客户。因此，信用评分问题可以简单地描述成是否可以通过客户的特征属性$x _ { i }$ 而准确地将他们分成优质与劣质客户[18]。

SVM为基于距离度量的分类模型，其对数量间数量级差别比较敏感。为避免数量级差别对分类结果的影响，在模型训练实验前使用最大一最小规范化方法对数据进行规范化。

$$
x _ { i } = \frac { x _ { i } - x _ { \operatorname* { m i n } } } { x _ { \operatorname* { m a x } } - x _ { \operatorname* { m i n } } }
$$

# 3.2实验结果及性能分析

为验证信用评分问题中各评判指标的Fisher比率值对分类器的影响，首先对数据进行预处理，而后按照式（8）计算出各特征的Fisher比率值，并对这些特征以此进行降序排列，最后依次选取各个特征建立分类模型，计算模型的G-mean值和F-measure值。测试结果如图3所示。

![](images/544b02306241689878b9d8b1b81d5e4d1413ca504f005884f6126f9eb7642dec.jpg)  
图3按Fisher分排序的特征分类模型测试结果

由图3可知，随着Fisher比率值的降低，相应特征对分类的影响逐渐减小，按照Fisher比率值大小排序后前18个特征对模型分类效果有较大影响，而其余特征对分类结果影响较小，可以忽略不计，故将其视为噪声特征删除。

实验过程以MATLAB2012b为平台，采用十折交叉验证将数据集平均分成10份，训练数据集和测试数据集的比例为1：9，每份数据集依次作为训练数据集。各类算法的设置亦同上。为避免机器学习不稳定性带来的随机影响，每折运行10次，实验次数共100次，最后得到每个评价指标的均值。同时将构建模型运行效果与SMOTE-BoostSVM、Fisher-SMOTE-BoostSVMSDSMOTE-BoostSVM、Fisher-SDSMOTE-BoostSVM模型的实验结果对比，各评价指标计算结果如图4所示。

对比五种算法的实验结果可以看出，算法总体分类准确率从大到小的排名依次为Fisher-SDSMOTE-ESBoostSVM、Fisher-SDSMOTE-BoostSVM、SDSMOTE-BoostSVM、Fisher-SMOTE-BoostSVM、SMOTE-BoostSVM，算法整体分类准确率随正类样本分类准确率的提高得到明显改进.另外，从图3中可以看出，本文提出的Fisher-SDSMOTE-ESBoostSVM算法在整体分类准确率上有较大提高，说明本文所提出的改进过采样算法及“淘汰策略”通过产生新的质量较高的正类样本平衡训练信息，较好地解决了客户信用评分中的类别不平衡问题。综上实验结果表明，相比其他算法，本文提出的Fisher-SDSMOTE-ESBoostSVM算法在处理信用评分中类不平衡问题时效果较好，学习性能更优，具有较好的适用性。

算法分类效果较优与其他三种算法，说明对过采样算法进行改进并结合“淘汰策略”确保合成样本的正确性使分类器对少数类样本具有了更强的学习能力，可以为类别不平衡信用评分问题提供一定的参考作用。

![](images/267f6eff437df832e752c8d6b66981a3f49d9d675fdf358895326ff3c79a33a7.jpg)  
图4五种模型各指标值对比

![](images/d07ec78642d84829d3a83d8149085ca199e4435053547ce3ec38ffd7a9b79344.jpg)  
图5ROC 曲线对比

# 3.3 与其他算法的对比

为进一步测试所构建算法的性能，本文将其与KM-SMOTE-RF、Fisher-RUS-AdaboostSVM，Relief-CSCART三种集成分类算法进行了对比。三种集成分类算法的集成策略见表3。10次实验结束后得到各评价指标均值如表4所示，各算法对应的ROC曲线如图5所示。

表3三种集成算法的集成策略描述   

<html><body><table><tr><td>算法</td><td>策略</td></tr><tr><td>KM-Borderline-</td><td>K-Mean聚类+基于边界的过采样算法SMOTE+</td></tr><tr><td>SMOTE-RF</td><td>随机森林集成学习算法</td></tr><tr><td>Fisher-RUS-</td><td>Fisher特征提取方法+欠采样算法RUS+</td></tr><tr><td>AdaboostSVM</td><td>Adaboost+SVM基分类器</td></tr><tr><td>Relief-CSCART</td><td>Relief特征选择方法+代价敏感决策树</td></tr></table></body></html>

表4本文算法与其他三种集成学习算法对比情况  

<html><body><table><tr><td>算法</td><td>G-mean</td><td>F-measure</td></tr><tr><td>KM-Borderline-SMOTE-RF</td><td>0.823</td><td>0.798</td></tr><tr><td>RUS-AdaboostSVM</td><td>0.882</td><td>0.845</td></tr><tr><td>Relief-CS-CART</td><td>0.895</td><td>0.873</td></tr><tr><td>Fisher-SDSMOTE-ESBoostSVM</td><td>0.923</td><td>0.896</td></tr></table></body></html>

从图5可以看出，四种算法对信用评分预测的表现是相当的，Fisher-RUS-AdaboostSVM、Relief-CS-CART的分类效果相差不大，较优于KM-SMOTE-RF算法，说明了特征选择在处理不平衡数据分类问题上的有效性；Fisher-RUS-AdaboostSVM算法更优于Relief-CS-CART算法，表明对于信用评分分类预测问题，从数据层面处理不平衡问题相对与从算法层面处理不平衡问题更具优势；而本文提出的Fisher-SDSMOTE-ESBoostSVM

# 4 结束语

本文针对信贷行业中客户信用评分业务存在的类别不平衡问题，首先采用Fisher准则对信用评分中各评判指标进行选择，合理降低了数据维度，减小了数据间信息冗余；并提出一种基于支持度的SDSMOTE过采样算法指导正类样本的合成，有效避免了传统SMOTE 算法合成样本的盲目性，使过采样更具针对性，进而提高正类样本的分类效率。以Boosting集成学习算法为框架，SVM为基分类器，引入“淘汰策略”，删除基分类器中分类错误的正类样本，重新合成并更新样例权重，提高了合成样本的质量。

实验结果表明，本文所提出的算法相比其他集成算法具有较好的F-measure和G-mean值，应用到信贷行业客户信用评分预测中具有可行性和适用性。本文仅将客户分为信用好和信用差客户，如何对客户信用等级进行更详细的划分是今后研究的重点。

# 参考文献：

[1]张婷婷.Logistic 回归及其相关方法在个人信用评分中的应用[D]．太原：太原理工大学,2017.  
[2] 陆爱国，王珏，刘红卫．基于改进的 SVM学习算法及其在信用评分中的应用[J]．系统工程理论与实践,2012,32(3):515-521.  
[3]陈启伟，王伟，马迪，等．基于Ext-GBDT集成的类别不平衡信用评分模型[J].计算机应用研究,2018,35(2):1-9  
[4]Herrera F. On the use of map reduce for imbalanced big data using RandomForest [J]. Information Sciences An International Journal,2014,285 (3):112-137.  
[5]Blake C L,Merz C J. UCI Repository of machine learning databases [D].Irvine (CA): University of California,1998  
[6]ChawlaNV, Bowyer KW,HallL O,et al. SMOTE: synthetic minority over-sampling technique [J]. Journal ofArtificial Intelligence Research,2002,16(1): 321-357.  
[7]Han H,Wang W Y,Mao B H. Borderline-SMOTE: a new oversamplingmethod in imbalanced data sets learning [C]// Proc of InternationalConference on Intelligent Computing.2005: 878-887.  
[8]Nakamura M,Kajiwara Y,OtsukaA,et al.LVQ-SMOTE-learningvectorquantization based synthetic minority over-sampling technique forbiomedical data [J].Biodata Mining,2013,6(1): 16.  
[9] 郭明玮，赵宇宙，项俊平，等．基于支持向量机的目标检测算法综述[J].控制与决策,2014,29(2):193-200.  
[10]徐乾，王文剑，张文浩．处理非平衡数据的粒度 SVM学习方法[J].计算机工程与应用,2011,47(24):97-99+114.  
[11]李诒靖，郭海湘，李亚楠，等．一种基于Boosting的集成学习算法在不均衡数据中的分类[J]．系统工程理论与实践,2016,36(1):189-199.  
[12]李雄飞，李军，董元方，等．一种新的不平衡数据学习算法PCBoost[J].计算机学报,2012,35(2):2202-2209.  
[13]黄海松，魏建安，康佩栋．基于不平衡数据样本特性的新型过采样SVM分类算法[J].控制与决策,2017,：1-10  
[14]赵清华，张艺豪，马建芬，等.改进SMOTE 的非平衡数据集分类算法研究[J].计算机工程与应用,2017,：1-7.  
[15]周绍磊，廖剑，史贤俊.基于Fisher准则和最大熵原理的SVM核参数选择方法[J].控制与决策,2014,29(11):1991-1996.  
[16]古平，欧阳源遊．基于混合采样的非平衡数据集分类研究[J].计算机应用研究,2015,32(2):379-381+418.  
[17]陶新民，郝思媛，张冬雪，等．基于样本特性欠取样的不均衡支持向量机[J].控制与决策,2013,28(7):978-984.  
[18]韩璐，韩立岩．正交支持向量机及其在信用评分中的应用[J].管理工程学报,2017,31(2):128-136.