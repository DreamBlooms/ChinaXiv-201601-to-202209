# 基于贝叶斯最小风险的癫痫脑电自动检测算法

卫作臣，邹俊忠，张见，陈兰岚(华东理工大学，信息科学与工程学院，自动化系，上海 200237)

摘要：癫痫脑电的自动检测是一个不平衡分类问题。提出一种新的不平衡分类算法，基于增减序列合并周期分割算法提取时域特征，引入随机映射优化了旋转森林的计算效率，进而计算基于海林格距离的贝叶斯最小风险来给出测试样本标签。该算法在1s片段上得到了 $9 0 . 6 6 \%$ 灵敏性， $9 2 . 5 2 \%$ 特异性，F2分数为0.9055，并且检出了 $9 8 . 5 6 \%$ 的癫痫发作，检测延迟为 $1 . 3 2 \mathrm { ~ s ~ }$ ，在不平衡的癫痫脑电数据集上表现出了良好的性能，对于癫痫辅助诊断有着极大的临床意义。

关键词：癫痫；时域特征；随机映射；旋转森林；代价敏感；贝叶斯最小风险 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2018.07.0415

# Automatic detection of epileptic EEG based on minimum Bayesian risk and rotation forest

Wei Zuochen, Zou Junzhong, Zhang Jian, Chen Lanlan (Dept.of Automation,Schoolof Information Science & Engineering，East China Universityof Science & Technology, Shanghai 200237, China)

Abstract:Automaticdetectionof epilepticdischargesinelectroencephalograph(EEG)isanimbalancedclassification problem.This paper proposesa novel automatic epileptic EEG detection approach.This studycalculates the time domain features based onthe mergerofincreasing and decreasing sequence (MIDS),and employs Random Projectionto improve the complexity of RotationForest,aswellas predicts the sample label using Minimum BayesianRisk based onthe Hellinger distance.This approach yielded $9 0 . 6 6 \%$ sensitivity, $9 2 . 5 2 \%$ specificity and F2-score of 0.9o55 in EEG segment classification task.Moreover,the proposed approach achieved $9 8 . 5 6 \%$ sensitivity of seizures with the average latency 1.32s.The proposed method shows good performanceontheepileptic EEG imbalanced data,andhas great clinicalsignificancefortheauxiliary diagnosis of epilepsy.

Key Words: epilepsy;time-domain feature; random projection; rotation forest; cost sensitive; minimum bayesian risk

# 0 引言

癫痫是一种由脑部神经元异常放电引起的慢性疾病，癫痫的发作往往会给病人带来极大的痛苦。世界卫生组织(WHO)在其 2017年的报告中指出[1]，全世界大概有50万癫痫患者，其中的 $2 5 \%$ 为儿童。医生诊断癫痫最直接的方式为人工判读脑电图，这一过程是非常耗时的，并且给医生带来了较大的工作负担。因此，提出一种高效的、精准的癫痫脑电自动检测的算法对于癫痫的辅助诊断有着极大的临床意义。

癫痫患者的脑电分为发作期与发作间期两部分，其特征波包括棘波、尖波、棘慢复合波与尖慢复合波。癫痫脑电检测这一课题已经引起了大量科研工作者的关注，随着近些年来机器学习方法的快速发展，癫痫脑电自动检测算法的效果也有了显著的提升。2010年，Shoeb等人[2提取了脑电的时空域与功率谱特征，讨论了机器学习算法在癫痫发作自动检测中的应用效果，得到了 $9 6 \%$ 的检出率以及4.6s的发作检测延迟。2012年，Martis 等人[3提出了一种基于经验模态分解（EMD）提取脑电特征的方法，并且使用C4.5决策树作为分类模型，得到了$9 5 . 3 3 \%$ 的准确率。2014年，Chen等人[4提出了基于小波分解的极限学习机癫痫发作检测模型，比较了样本熵，近似熵与递归定量分析（RQA）等非线性特征的分类效果。2015年，Donos等人[5提取了多个维度的信号特征，并且将随机森林应用于癫痫分类中，得到了 $9 3 . 8 4 \%$ 的灵敏性，3.03s的检测延迟。随着深度学习的兴起，2017年，Acharya等人[6将脑电信号分为发作期，发作前期与正常脑电信号三部分，提出了深度卷积神经网络的癫痫发作的多分类算法。在癫痫预测领域，Khan 等人[8]基于小波分量与卷积神经网络得到了 $8 7 . 8 \%$ 的癫痫发作检出率以及0.142/小时的误判率。

在以往的大量有关癫痫脑电自动检测的研究中，时域、频域、时频域以及非线性特征均有所涉及。其中时域特征是最本质的特征，医生在临床上判读脑电图中的癫痫特征波的依据往往是时域波形。时域特征相比其他特征有着以下三点优势：a)时域特征有着明确的物理意义；时域特征是最直接的特征，是无须作变换就可以观测到的信息；无须作信号平稳的假设。在之前的研究中[8\~10提出了一种基于视觉组织原则的信号波形处理方法，这种方法通过学习医生判读脑电图的视觉感知与完形的过程来建立模型，有效而灵活地分割了信号的周期，突出了时域波形状特征并去除了冗余信息，这一方法已经在癫痫放电检测、疑似癫痫的噪声自动分离以及睡眠自动分期中体现了良好的性能。

在癫痫脑电自动检测这一问题中，可采集到的癫痫波的数量是大大少于正常脑电样本的，因此实际上这是一个不平衡二分类的问题，而不平衡数据集训练出的模型一般会偏向多数类，此时的模型准确率无法很好地评价模型性能[1]。在数据层面上，不平衡数据集可以使用欠抽样或过抽样方法来使其变得平衡，但这两种方法都有着各自的缺陷。欠抽样方法会减少模型学习到的多数类样本信息，而过采样方法通过随机复制少数类样本来实现数据集的平衡，这样会导致模型的泛化性能变差，容易过拟合。SMOTE[I2]算法通过近邻来生成不重复的少数类样本，但容易造成类边界模糊。代价敏感（cost-sensitive）思想是另一种解决不平衡数据集问题的方法，它是针对不同类错分代价不同所提出的模型学习思想，这一学习方法不关注模型的错误率，而是通过预测的最小代价来训练与选择模型。Domingos[13]提出了基于元代价（Metacost）的代价敏感算法，即将基分类器当作黑箱子，通过代价敏感矩阵得出的误分类风险来更新训练集标签。在分类问题上，大多数机器学习方法都假设各类错分代价相同，而对于不平衡数据集则不是这样，少数类样本比多数类样本珍贵，并且应当对少数类的错分施加更大的惩罚，因此代价敏感思想是一种在算法层面上处理不平衡数据集的方法。

本文的提出了一种快速、高效的不平衡分类算法，并脑电信号中癫痫波的自动检测问题进行分析，所使用的数据集为不平衡数据集，以此来研究在类别不平衡情况下所提出的算法自动识别癫痫脑电的性能。本文提出了基于视觉组织原则的时域信号特征提取方法，算法部分主要的贡献与创新点可分为以下两部分：

a)改进了旋转森林算法[14]，使用随机映射代替标准旋转森林特征旋转过程中的PCA 映射来提高运算的时间效率，并且Johnson-LindenstraussLemma 定理保证了随机降维方法的精度。

b)提出了基于贝叶斯最小风险的代价敏感分类方法，根据海林格距离来评估样本不平衡程度，并赋予少数类和多数类不同的错分代价。根据代价矩阵计算出样本预测风险，从而将预测样本分为误分类风险最小的那一类。相比传统方法，这一基于贝叶斯最小风险的方法有效地提高了少数类即癫痫波的检出率。

# 1 方法与模型

# 1.1时域特征提取

1.1.1基于视觉组织原则的周期分割法

这一简单高效的时域算法在之前的研究中[8]已被详细介绍，在这一小节简单陈述算法流程与相关概念。

![](images/8975dbe63cb7f8b7451878af6ed7f5f703506abe6aa6432d3bfa06352170436a.jpg)  
图1相邻波形的11种组合模式，空心圆表示完整的波形组合，实心圆为不完整的波形组合

定义1增减序列。定义 $s ( i )$ 为时序列的第 $i$ 个采样点，假设 $s ( i )$ ， $s ( i + m )$ 为两个局部极小值， $s ( i + n )$ 为一个局部极大值，则认为这三个点构成了一个单位波， $i$ 到 $i + n$ 为上升序列，$i$ 到 $i + m$ 为下降序列。

1)杂波合并条件

首先，由于癫痫特征波中的棘波为 $2 0 { \sim } 7 0 ~ \mathrm { m s }$ ，尖波周期为$7 0 { \sim } 2 0 0 ~ \mathrm { m s }$ ，所以周期小于 $2 0 ~ \mathrm { m s }$ 的波被认为是杂波；其次，波的幅值小于 $1 0 \mu V$ 同样被判定为杂波。

a）不完整波形条件

定义序列 $s ( i )$ 中的极值点索引为序列 $s ( a ( i ) )$ ，那么假设相邻两个波的极值序列为$[ s ( a ( i ) ) , s ( a ( i + 1 ) ) , s ( a ( i + 2 ) ) , s ( a ( i + 3 ) ) , s ( a ( i + 4 ) ) ] ,$ 这两个波的组合模式共11种，如图1所示，其中5种为不完整的模式，需要合并。令

$$
\begin{array} { r l } & { h _ { 1 } = s ( a ( i + 1 ) ) - s ( a ( i ) ) } \\ & { h _ { 2 } = s ( a ( i + 1 ) ) - s ( a ( i + 2 ) ) } \\ & { h _ { 3 } = s ( a ( i + 3 ) ) - s ( a ( i + 2 ) ) } \\ & { h _ { 4 } = s ( a ( i + 3 ) ) - s ( a ( i + 4 ) ) } \end{array}
$$

则图1中不完整的波形模式可归纳为下述5种规则：

$$
\begin{array} { c } { { h _ { 1 } / h _ { 2 } < r \& h _ { 3 } / h _ { 4 } < r } } \\ { { \ } } \\ { { h _ { 2 } / h _ { 1 } < r \& h _ { 4 } / h _ { 3 } < r } } \\ { { \ } } \\ { { h _ { 2 } / h _ { 1 } < r \& h _ { 3 } / h _ { 4 } < r } } \end{array}
$$

$$
h _ { 2 } / h _ { 1 } < r \& h _ { 3 } / h _ { 4 } \geq r
$$

$$
\& h _ { 2 } / h _ { 1 } \ge r \& h _ { 3 } / h _ { 2 } < r
$$

其中 $\boldsymbol { r }$ 为合并系数，之前的研究中表明 $_ { r = 0 . 5 }$ 可以较好地适应各种节律的波。对于尖形波， $r { = } 0 . 3$ ，尖形波需要满足以下三个条件： $2 0 m s \leq T \leq 2 0 0 m s$ ; ${ h / T > 2 }$ ；突出于背景： $h / h _ { _ { p r e } } > 4$ ，其中 $h _ { p r e }$ 为该波之前1分钟内所有波的平均幅值。

b）增减序列合并算法（MIDS）

每两个相邻的基于极值点定义出的波做一次运算，根据规则评价是否为不完整波或杂波，若是，则执行算法1的合并操作。

# 算法1增减序列合并（MIDS）

Input: raw time sequence $s$ · index of extremum sequence $a$   
Output: the merged sequence.   
for each value $s ( a ( i ) )$ of $s$ DO 证 $[ s ( a ( i ) ) , s ( a ( i ) ) , s ( a ( i + 2 ) ) ]$ is a cluster or incomplete then $\begin{array} { c } { { a ( i + 1 ) \longleftarrow a r g m a x ( s ( a ( i + 1 ) ) , s ( a ( i + 3 ) ) ) } } \\ { { \nonumber } } \\ { { a ( i + 1 + k ) \longleftarrow a ( i + 3 + k ) , k \nonumber = 1 \ldots N - 3 - i } } \end{array}$ end if $i \gets i + 2$   
end for   
return $s ( a )$ （204号

1.1.2 特征计算

使用上节的MIDS算法处理原始信号后，得到了周期分割序列，以分割后的单个完整波形[s(a(i)),s(a(i+1)),s(a(i+2))]为基础，提取17维时域特征，各个特征计算过程如下：

a)周期,即 $T = a ( i + 2 ) – a ( i )$ ：b)上升幅度 $h _ { i n } = s ( a ( i + 1 ) ) - s ( a ( i ) )$ （204号c)下降幅度 $h _ { _ { d e } } = s ( a ( i + 1 ) ) - s ( a ( i + 2 ) )$ （204号d)上升时长 $a ( i + 1 ) - a ( i )$ ；e)下降时长 $a ( i + 1 ) - a ( i + 2 )$ ：f)波形幅值的标准差 $\sqrt { \frac { 1 } { T } \sum _ { k = a ( i ) } ^ { a ( i + 2 ) } ( s ( k ) - s _ { m e a n } ) ^ { 2 } }$ ，评价波形变化程度;g)锐度 $2 s ( a ( i + 1 ) ) - s ( a ( i ) ) - s ( a ( i + 2 ) )$ h)幅值平方和 $\sqrt { \sum _ { k = a ( i ) } ^ { a ( i + 2 ) } s ( k ) ^ { 2 } }$ ：i)幅值均值 $\frac { 1 } { T } \sum _ { k = a ( i ) } ^ { a ( i + 2 ) } s ( k )$ j)相邻点差值标准差 $\sqrt { \sum _ { k = a ( i ) } ^ { a ( i + 2 ) - 1 } ( s ( k + 1 ) - s ( k ) ) ^ { 2 } }$ (s(k+1)-s(k))²，评价波形波动程度;

k)Hjorth参数[15]，复杂度，化简表示为$\frac { \sqrt { \displaystyle \sum _ { k = a ( i ) } ^ { a ( i + 2 ) - 2 } ( s ( k + 1 ) - s ( k ) ) ^ { 4 } } \sqrt { \displaystyle \sum _ { k = a ( i ) } ^ { a ( i + 2 ) } ( s ( k ) ) ^ { 2 } } } { \displaystyle \sum _ { k = a ( i ) } ^ { a ( i + 2 ) - 1 } ( s ( k + 1 ) - s ( k ) ) ^ { 2 } }$

1)峰度系数 $\frac { T \displaystyle { \sum _ { k = a ( i ) } ^ { a ( i + 2 ) } ( s ( k ) - s _ { m e a n } ) ^ { 4 } } } { ( \displaystyle { \sum _ { k = a ( i ) } ^ { a ( i + 2 ) } ( s ( k ) - s _ { m e a n } ) ^ { 2 } } ) ^ { 2 } } - 3$ ，度量波形的聚集程度;m)最大幅值与波形标准差的比值 $\frac { m a x ( s ( k ) ) } { \sqrt { \frac { 1 } { T } \sum _ { k = a ( i ) } ^ { a ( i + 2 ) } \left( s ( k ) - s _ { m e a n } \right) ^ { 2 } } }$ n)上升角度的余切 $\frac { a ( i + 1 ) - a ( i ) } { s ( a ( i + 1 ) ) - s ( a ( i ) ) }$   
0)下降余切 $\frac { a ( i + 1 ) - a ( i + 2 ) } { s ( a ( i + 1 ) ) - s ( a ( i + 2 ) ) }$   
p)幅值较大侧/周期max(hm,hde）； $\frac { m a x ( h _ { i n } , h _ { d e } ) } { T }$   
q)幅值较小侧/周期min(h,hde) $\frac { m i n ( h _ { i n } , h _ { d e } ) } { T }$

在本实验中，选择时长为1s的多导联脑电片段为一个样本，因此每一个导联中的这17个时域特征取所有完整波的均值，因此特征维度为 $1 7 ^ { * } N$ ， $N$ 为导联数量。

# 1.2基于随机映射的旋转森林

1.2.1随机映射

随机映射（random porjection,RP）是机器学习中的一种降维方法，它将高维空间 $R ^ { d }$ 中的样本集 $\boldsymbol { S } _ { d }$ 通过一个随机转换矩阵 $M _ {  { \boldsymbol { \ k } } , d }$ 映射到低维空间 $R ^ { k }$ 中，如式（1）[16]所示，Johnson-LindenstraussLemma[17]给出了这种映射方法降维后的精度范围。

$$
S _ { k } = M _ { k , d } S _ { d }
$$

定理1 Johnson-LindenstraussLemma。高维空间中的 $n$ 个样本点可以映射到一个为 $O ( l o g n / \varepsilon ^ { 2 } )$ 的低维空间中，并且样本间距离变化不会超过 $( 1 \pm \varepsilon )$ 。

对于任意的 $0 < \varepsilon < 1$ 与正整数 $n$ ，有整数 $k$

$$
k \geq 4 ( \varepsilon ^ { 2 } / 2 - \varepsilon ^ { 3 } / 3 ) ^ { - 1 } \ln n
$$

则对于任意的空间 $R ^ { d }$ 中包含 $n$ 个样本的数据集 $s$ ，存在映射： $f : R ^ { d } \to R ^ { k }$ ，且对于任意 $u , \nu \in S$ 存在：

$$
( 1 - \varepsilon ) \big \| u - \nu \big \| ^ { 2 } \leq \big \| f ( u ) - f ( \nu ) \big \| ^ { 2 } \leq ( 1 + \varepsilon ) \big \| u - \nu \big \| ^ { 2 }
$$

证明过程见文献[17]。

因此，定理1指出，在低维空间维度不小于一个阈值的前提下，映射后的样本间距离相比原始空间中的数据集在一个范围内保持不变，并且映射 $f$ 可以随机得出。相比其他的降维方法，随机映射的计算量非常小，对于 $n$ 个样本点的原始数据集，随机映射的复杂度仅为 $O ( d k n )$ 。其次，转换矩阵为随机产生，无须计算原始数据集的信息，仅通过保证样本间距离变化误差来实现降维，这一特性对于样本间距离有意义的数据集有着较大优势。

近几年来，随机映射凭借着它较小的计算量以及相比传统降维方法较好的性能已被应用在各种领域中[18.19]。本文使用随机映射来实现旋转森林算法中的特征旋转部分，在保证变换效果的前提下，提高了整个算法的计算效率。

# 1.2.2改进的旋转森林算法

旋转森林（rotation forest）是Rodri'guez[20]于 2006 年提出的一种基于随机森林（randomforest）思想的改进算法。旋转森林在抽取样本子集的同时，将特征分为多个子集，每一个基分类器都选取不同的特征子集进行特征维度线性变换，以此增加基分类器间的多样性。相比传统的随机森林算法，旋转森林由于其基分类器更大的差异，相比随机森林会进一步地降低各个子模型间的相关性，从而得到一个方差更低的模型，这一算法在部分领域已经得到应用[2I]。本文使用随机映射代替文献[20]中的主成分分析（PCA）来优化旋转森林算法中的核心部分，即特征线性变换的过程。随机映射相比PCA不需要计算数据的协方差矩阵，并且定理1保证了随机投影的精度，整个计算流程如下：

$\mathbf { \alpha } _ { \mathbf { { a } } } )$ 有训练集 $X _ { n ^ { * } N }$ ，其中 $n$ 为特征维度， $N$ 为样本数量， $Y$ 为标签列， $E _ { k }$ 为第 $k$ 个基分类器。假设特征分为 $\mathbf { \nabla } _ { m }$ 个不相交特征子集，则每个子集包含特征 $F = n / m$ 个；

$\vert b \vert$ 随机抽取样本训练基分类器，使用随机映射进行特征的线性变换，按特征索引顺序排列后得到每个基分类器的线性变换矩阵 $R _ { k }$ ：

$\mathbf { \sigma } _ { c ) }$ 使用数据集 $X R _ { k } , Y$ 训练基分类器 $E _ { k }$ ；

$\mathbf { \Delta } _ { d ) }$ 则预测时样本各个类别的输出概率为$p ( j | x ) = \frac { 1 } { K } { \sum _ { 1 } ^ { K } p r e d _ { k } ( j | x R _ { k } ) }$ ∑predk（jlxRk），其中j为类别，样本最终预测类别为 $\arg \operatorname* { m a x } ( p ( j | x ) )$ 。

# 1.3贝叶斯最小风险预测

# 1.3.1海林格距离

海林格距离（Hellinger distance）由Hellinger 提出，在统计学中，用来度量两个概率分布的相似程度，是 $f -$ divergence散度的一种，定义如下：

定义2海林格距离（HD)。有概率分布P和Q，则这两个分布之间的海林格距离为

$$
h ( P , Q ) = \frac { 1 } { \sqrt { 2 } } \Big \| \sqrt { P } - \sqrt { Q } \Big \| _ { 2 }
$$

Cieslak等人基于海林格距离提出了海林格决策树(HDDT)算法[22]，通过在决策树分裂时计算节点上样本类间的海林格距离代替传统的gini指数，在不同样本比例的数据集上取得了良好的效果。由此可知，相比直接使用样本比例度量类间分布情况的方法，海林格距离度量表现出了更好的性能。

# 1.3.2贝叶斯风险计算

本实验中所使用的为不平衡癫痫脑电数据集，随着类间比例的变化，两类样本各自的误分类代价应当随之而变化。本文使用代价敏感思想[13]来研究这一问题，提出了一种基于海林格距离的新颖的类间不平衡评价方式，并根据评价值给出代价敏感损失矩阵，进而计算出各类别贝叶斯最小风险实现预测。

定义3HD评价指标。有样本集S，包含两类标签，则类间的海林格距离为

$$
h ( + , - ) = \frac { 1 } { \sqrt { 2 } } \left\| \sqrt { \frac { S _ { + } } { S } } - \sqrt { \frac { S _ { - } } { S } } \right\| _ { 2 }
$$

其中： $S _ { + }$ 表示正样本数量， $S .$ 表示负样本数量， $s$ 表示样本集总的样本数量。

定义4代价矩阵。对于样本集 $s$ ，二分类问题的误分类代价矩阵为

$$
\mathbf { C } = \left[ \begin{array} { c c } { 0 } & { C _ { - , + } } \\ { C _ { + , - } } & { 0 } \end{array} \right]
$$

其中： $C ( \cdot , + )$ ，表示将负类预测为正类的代价，反之亦然，此处的 $c$ 值根据类间的海林格距离算出。

定义5贝叶斯最小风险预测。令 $p ( j | x )$ 为模型将样本 $x$ 预测为 $j$ 类概率值，则最终预测类别为

$$
y = \underset { i } { \arg \operatorname* { m i n } } ( \sum _ { j } p ( j \vert x ) C ( j , i ) )
$$

本文提出的基于贝叶斯最小风险预测的算法考虑了训练模型的数据集的样本分布情况，根据类间的不平衡程度给出代价损失矩阵，将使用不平衡数据集训练出的偏向多数类的模型通过赋予不同的误分类损失加以调节。这一算法将模型看做一个黑箱子，不在模型内部针对不平衡训练集问题进行调整，而是在模型之外根据训练集的实际分布给出预测概率的置信度，通过计算最小贝叶斯风险来预测样本类别，从而减少不平衡训练集带来的影响。

算法2：基于海林格距离的贝叶斯最小风险预测（HD-MBR）

Input:Train set S; Probabilities of each class for sample $x p ( j | x )$

Output: predicted class $y$ calculate Hellinger Distance:

$$
H D \gets \frac { 1 } { \sqrt { 2 } } \bigg \| \sqrt { \frac { S _ { + } } { S } } - \sqrt { \frac { S _ { - } } { S } } \bigg \| _ { 2 }
$$

calculate cost matrix:

$$
\mathbf { C } \gets \left[ \begin{array} { c c } { 0 } & { 1 - \sqrt { 2 } H D } \\ { 1 } & { 0 } \end{array} \right]
$$

The predicted class:

$$
y = \underset { i } { \arg \operatorname* { m i n } } ( \sum _ { j } p ( j \vert x ) C ( i , j ) )
$$

return y

# 1.4算法流程

算法流程如图2所示。

# 2 实验结果与讨论

# 2.1 数据集

本文使用公开的癫痫脑电数据集CHB-MIT[23-26]来测试所提出算法的性能。为了确保数据集特征维度的统一，选用数据集中使用23导联采集脑电信号的12个病人的数据，23个导联包括FP1-F7，F7-T7，T7-P7，P7-O1，FP1-F3，F3-C3，C3-P3，P3-O1，FP2-F4，F4-C4，C4-P4，P4-O2，FP2-F8，F8-T8，T8-P8,P8-O2，FZ-CZ，CZ-PZ，P7-T7，T7-FT9，FT9-FT10，FT10-T8,T8-P8。信号采样率为256Hz，每一份病人的数据中均包含多次癫痫发作。

![](images/50446e9be070b7637da3604be58b82dd9183d679e1173fe31ad9b8d34f18a508.jpg)  
图2算法整体流程

# 2.2实验设计

实验环境为Ubuntu16.04系统、英特尔i7-7700k 处理器、32 GB运行内存。实验数据中样本为时长1s的多导联脑电片段，取所有的癫痫发作脑电片段构造正样本，并且在每一次癫痫发作之前的脑电信号中随机选出时长固定的间期脑电片段。由于发作时长不固定，因此每次发作的正负样本比例是不同的。按此方法处理每一次发作，得到一个不平衡的数据集，不同份数据的不平衡比例约在1：4到1：20之间。为了更好地评估所提出算法的性能，使用留一法（leave-one-out）进行交叉测试。即假定患者 $n$ 的脑电数据中存在 $N$ 次发作，则测试第i次发作时使用剩下的N-1次数据训练，迭代 $i$ 的值直至 $\scriptstyle i = N ,$ 0

算法性能评价分为两部分，分别为

a)基于片段评价（segment-based)。即以1s 时长的样本为单位，评估模型性能，是一个癫痫脑电样本的分类问题。

b)基于事件评价（event-based)。以一次发作为单位，判断是否检出以及检出延迟，是一个癫痫发作的检测问题。

由于样本集正负比例不平衡，因此无法用准确率评价模型性能，所选取的评价指标为灵敏性（sensitivity），特异性（specificity）， $F \beta$ 分数（ $F \beta$ -score）以及检测延迟（latency），指标计算方式如下：

$$
F \beta = ( 1 + \beta ^ { 2 } ) \frac { p r e c i s i o n ^ { * } s e n s i t i \nu i t y } { ( \beta ^ { 2 } * p r e c i s i o n ) + s e n s i t i \nu i t y }
$$

其中：检测延迟为基于事件的评价方式的评价指标。 $F \beta$ 分数是精准率与灵敏性的一个加权平均，由于在癫痫检测中，漏检一次癫痫比误判一次正常脑电的后果要严重，因此实验中选择 $\beta = 2$ 来表示癫痫样本的重要性，即使用 $F 2$ 分数作为评价指标。

# 2.3结果分析

实验对12份数据各自的癫痫发作做交叉测试，基于1s癫痫样本的分类结果如表1所示。

表1基于1s片段的癫痫脑电分类结果  

<html><body><table><tr><td>编号</td><td>灵敏性/%</td><td>特异性/%</td><td>F2分数</td></tr><tr><td>1</td><td>94.59</td><td>97.36</td><td>0.9501</td></tr><tr><td>2</td><td>82.98</td><td>59.13</td><td>0.7655</td></tr><tr><td>3</td><td>92.52</td><td>97.55</td><td>0.9623</td></tr><tr><td>4</td><td>88.60</td><td>94.66</td><td>0.8959</td></tr><tr><td>5</td><td>92.75</td><td>98.21</td><td>0.9377</td></tr><tr><td>6</td><td>96.72</td><td>90.04</td><td>0.9117</td></tr><tr><td>7</td><td>90.80</td><td>96.00</td><td>0.9171</td></tr><tr><td>8</td><td>93.12</td><td>94.58</td><td>0.9331</td></tr><tr><td>9</td><td>97.03</td><td>93.27</td><td>0.9601</td></tr><tr><td>10</td><td>87.43</td><td>98.24</td><td>0.8912</td></tr><tr><td>11</td><td>97.02</td><td>97.11</td><td>0.9700</td></tr><tr><td>12</td><td>74.33</td><td>94.05</td><td>0.7718</td></tr><tr><td>总体</td><td>90.66</td><td>92.52</td><td>0.9055</td></tr></table></body></html>

从表1中可以看出，模型在所有数据上均表现出了良好的效果，大部分灵敏性在 $8 5 \%$ 以上，特异性在 $90 \%$ 以上。平均灵敏性和特异性 $9 0 . 6 6 \%$ 、 $9 2 . 5 2 \%$ ，平均F2分数为0.9055。

为了体现所提出算法相比传统机器学习算法的优越性能，使用随机森林以同样的方式做测试，所提出算法正是在随机森林上进行了特征子空间分割、特征旋转、代价敏感以及贝叶斯最小风险预测这些改进得到的。在评价指标中，F2分数综合考虑了模型的灵敏性和精准率，图3通过不同病人数据的F2分数来进行算法之间的性能比较。同时，表2列出了随机森林在12 份数据上的平均指标值，结果表明，提出的算法相比随机森林，提高了 $1 0 . 2 9 \%$ 的灵敏性，0.0867的F2分数，而特异性只下降了 $2 . 8 \%$ 。在临床上，漏判的癫痫放电相比误判的正常脑电要付出更大的代价，提出的算法则符合这个思想，并且相比传统模型提升明显。

![](images/79c3fc519fd97d5009cd8f38344a20bdcda2d39a2a2d56f1466a862ae03b6f0a.jpg)  
图3模型F2分数比较

表2与传统模型的结果对比  

<html><body><table><tr><td>模型</td><td>灵敏性/%</td><td>特异性/%</td><td>F2分数</td></tr><tr><td>随机森林</td><td>80.37</td><td>95.32</td><td>0.8188</td></tr><tr><td>本文算法</td><td>90.66</td><td>92.52</td><td>0.9055</td></tr></table></body></html>

进一步地，为了验证所提出算法中的核心部分贝叶斯最小风险预测相比传统不平衡分类算法的优越性能，在同样的模型下，分别采用权重法与SMOTE过采样这两种方法处理训练集，来代替本文的贝叶斯最小风险预测方法。在 SMOTE 处理过程中，调节采样率生成与多数类等量的少数类样本，在权重法中，则按照样本比例加权。从表3的对比结果中可以看出，本文算法相比SMOTE方法与权重法在灵敏度上分别提高了 $3 . 8 5 \%$ 、$4 . 9 8 \%$ ，F2分数提高了0.0285、0.0384。这一结果表明，本文提出的算法在不平衡数据集上的效果要优于传统的权重法与SMOTE 算法。

表3与传统不平衡数据集处理算法的结果对比  

<html><body><table><tr><td>算法</td><td>灵敏性/%</td><td>特异性/%</td><td>F2分数</td></tr><tr><td>权重法</td><td>85.68</td><td>93.94</td><td>0.8671</td></tr><tr><td>SMOTE</td><td>86.81</td><td>93.63</td><td>0.8770</td></tr><tr><td>本文算法</td><td>90.66</td><td>92.52</td><td>0.9055</td></tr></table></body></html>

为了进一步评估模型的发作检测性能，将每次测试的发作脑电按时间顺序排列，以此来观察每次发作是否被检出，以及其检出延迟，表4列出了基于事件的癫痫检测结果。

表4癫痫发作检测结果  

<html><body><table><tr><td>编号</td><td>检出率/% 延迟/s</td></tr><tr><td>1</td><td>100 1.14</td></tr><tr><td>2</td><td>100 0.5</td></tr><tr><td>3 100</td><td>0.86</td></tr><tr><td>4</td><td>100 2.25</td></tr><tr><td>5 100</td><td>2.2</td></tr><tr><td>6 100</td><td>0.5</td></tr><tr><td>7 100</td><td>0.67</td></tr><tr><td>8 100</td><td>1.6</td></tr><tr><td>9 100</td><td>1.25</td></tr><tr><td>10 100</td><td>1.57</td></tr><tr><td>11 100</td><td>0.57</td></tr><tr><td>12 92.31</td><td>2.77</td></tr></table></body></html>

检测结果表明，11份数据中的发作全部被检出，仅在数据

12 中存在漏检。考虑每一份数据的发作次数，平均检出率为$9 8 . 6 5 \%$ ，平均检测延迟为1.32s。

由于现阶段提出的大部分算法的评价方式为基于癫痫事件的评价，表5列出了在公开数据集CHB-MIT上的其他癫痫发作事件检测研究的结果，并与本文所提出方法的比较。结果表明，所提出的算法效果相比其他文献有所提高，并且与大部分其他的研究不同，本文的实验结果是在不平衡数据集上得到的，这说明该算法在不平衡数据集上有着极大的潜力。

表5与其他方法比较结果  

<html><body><table><tr><td>方法</td><td>检出率/%</td><td>延迟/s</td></tr><tr><td>文献[2]方法</td><td>96</td><td>4.6</td></tr><tr><td>文献[25]方法</td><td>100.0</td><td>3.36</td></tr><tr><td>文献[26]方法</td><td>98.5</td><td>1.76</td></tr><tr><td>本文算法</td><td>98.65</td><td>1.32</td></tr></table></body></html>

# 2.4讨论

大部分脑电信号的模式识别研究均是在平衡数据集上测试所提出的算法性能，本实验考虑患者脑电信号中的癫痫波数量很少，针对这一不平衡的数据集分类问题提出了基于贝叶斯风险预测的算法，并在不平衡的癫痫脑电数据集上进行应用分析，由结果可以看出，在不同类别比例的测试集上该算法均可以保持良好的性能以及稳定的效果。只要知道训练该模型的训练集样本分布情况，就可以通过不同的误分类代价计算贝叶斯风险，以此代替传统的输出概率实现样本的分类。

本文使用了高效简洁的时域特征，在医生判读脑电图的过程中，信号的时域特征是最直接的特征，且物理意义明确，医生往往可以通过癫痫波中的尖、棘波及其复合波的形状特征做出判断。本文使用了我们之前研究提出的周期分割算法来进行时域特征的提取，这一算法基于合并、分割的规则模拟医生在判读时域信号的过程中视觉完形，神经感受野的概念，在时序列信号处理中相当于为特征提取的过程给出了一个灵活、自适应时间窗口，该窗口符合人的视觉感知与判断，所分割出的完整波形符合人的视觉感知，因此提取出的特征也提供了时序信号中每一个完整波形的信息，实验结果证明了所提取的特征的有效性。另外，本文选用了1s时长的片段作为样本进行分类，相比大部分癫痫脑电识别算法，这是一个非常短的时间窗口，大部分算法不足以在1s内提取出判别癫痫放电的信息，而对于基于周期分割的特征提取方法来说，这些信息是足够的。进一步来看，这一特征提取方法是基于每一个波来提取特征的，从而有效地判断出一个完整的波形是否是异常放电，这种在短时间内提取有效特征的方法在在线检测中有着极大的优势。

在模型部分，本文使用随机映射优化了传统旋转森林方法中特征子空间的变换这一核心部分。相比传统的PCA 旋转方法，随机映射是一种快速的投影算法。PCA需要计算特征的协方差矩阵，并通过SVD分解来求得该矩阵的特征值与特征向量，排序后得出变换矩阵，这一计算计算代价高昂。随机映射则使用随机生成的变换矩阵进行映射，且定理1给出的距离不变性可以保证变换后的精度，相当于根据数据间的距离进行投影。随机映射无需计算数据的协方差矩阵及其特征值、特征向量，计算量要小于PCA。

贝叶斯最小风险的预测方法为不平衡数据集训练出来的模型提供了良好的分类性能，并且计算过程简单。表2的结果表明，对比未作处理的传统随机森林算法在效果上有着明显的提升。传统的不平衡分类方法往往为过采样、欠采样等，本文将所提出的不平衡分类算法与权重法、SMOTE算法对比，表3已经从效果上体现了本文算法要优于这两种传统算法，同时在训练效率上，本文算法在时间和空间效率上均有所提升。在本文的树模型中，权重法对少数类错分做出的加权惩罚体现在每一个叶节点分裂的过程中，所需的乘法次数要多于本文算法。SMOTE算法根据所有的少数类样本及其近邻来生成少数类样本，需要根据欧式距离计算每一个少数类样本的近邻，并根据预设好的采样率与每一个近邻生成新的样本。假设数量为 $\mathfrak { n }$ 的训练集中，少数类样本数量为p，SMOTE 算法在计算每个少数类样本的K 近邻时需要遍历 ${ \tt p } ^ { 2 }$ 次，存储近邻索引则需要 $\mathrm { { p } ^ { * } \mathbf { k } }$ 的空间。在生成样本过程中，时间复杂度则与需要生成的样本数目线性相关，并且需要额外的空间去存储这些生成的样本。本文算法的在知道各类样本数量的情况下，训练过程与平衡数据集情况下没有区别，除计算一次海林格距离外不需要进行其他的额外计算，仅需在预测时遍历一次测试集即可得出最小风险，这一过程的时间效率高于SMOTE 算法。所需额外存储的变量仅为代价敏感矩阵，而在二分类问题中，代价敏感矩阵为两个值，所需存储空间可忽略不计，远低于SMOTE方法的空间复杂度。

从理论角度来看，本文算法不需要对原始数据集做生成、更新或者欠采样处理。欠采样方法会丢弃掉大量的负样本信息，影响模型性能；随机过采样采用随机复制少数类样本来增加少数类样本，会造成样本多样性不足，少数类样本的信息实际上没有增加，造成模型泛化性能变差；权重法对少数类样本加权的过程相当于产生了新的数据分布，将分类器的重点集中在少数类样本的身上，但这个权值的选择往往过于主观；SMOTE过采样的方法是通过近邻合成新样本，为生成的样本提供了一定的多样性，但同样存在缺陷，首先最优近邻数值难以确定，其次由类边缘样本生成的样本会造成边界模糊的问题，加大样本集的可分性。本文提出的不平衡分类算法统计了数据的分布情况，但不需要对数据集做任何修改，而是根据分布给出不同的误分类代价，在模型层面对不同类别的错分情况计算风险，通过获得一个整体误分类风险最小的模型来实现不平衡分类问题的解决。

本文的算法框架由基于视觉组织的时域特征提取、改进的旋转森林以及贝叶斯最小风险预测三部分组合而成。所提取的时域特征为短时间的波形特征，如时长、幅值、锐度、峭度等等，这些特征大部分都是可以视觉观察到的一些波的形状特征，从医生视觉判读的角度来看，这些特征已经为单个波提供了一定的可分性。模型部分采用随机映射优化了标准的旋转森林算法，并且针对特征的线性变换降低了各个子分类器的相关性，可以进一步地降低整个模型的方差。基于贝叶斯最小风险的预测则是本文算法中解决数据不平衡的核心技术，效果上优于传统模型以及常见的不平衡分类算法，并且训练效率上有所提升。因此整个算法框架在不平衡数据集的分类问题上表现出了优越的性能。

# 3 结束语

本文提出了基于时域特征的不平衡癫痫脑电检测算法，将多导联脑电信号分割周期后的时域特征输入改进的旋转森林模型，并且使用贝叶斯最小风险代替输出概率得到测试样本的类别。最终在基于1s的癫痫放电分类问题上得到了 $9 0 . 6 6 \%$ 的灵敏性， $9 2 . 5 2 \%$ 的特异性，0.9055的F2分数，相比传统的随机森林模型，提高了 $6 \%$ 的灵敏性，0.9的F2分数，并且在发作检测方面，检出了 $9 8 . 5 6 \%$ 的癫痫发作，检测延迟为1.32s。这一算法在不平衡脑电数据集上得到了优良的性能，优于许多平衡数据集上的自动检测算法，并且解除了癫痫样本不充足这一限制。本实验中选取固定时长的间期脑电片段构建不同类别比例的样本集，若加大不平衡比例，本文提出的方法相比传统方法理论上提升会更显著。同时算法符合临床判读脑电图的思想，有着极大的临床意义。

# 参考文献：

[1]World Health Organization.Epilepsy [R],Geneva: WHO,2017.   
[2]Shoeb A,Guttag J,Application of machine learning to epileptic seizure onset detection [C]// Proc of the 27th,International Conference on Machine Learning.2010.   
[3]Martis RJ,Acharya UR,Tan JH,et al.Application of empirical mode decomposition (EMD） for automated detection of epilepsy using EEG signals [J]. International Journal of Neural Systems,2012,22(6):1250027.   
[4]Chen Lanlan，Zhang Jian，Zou Junzhong，et al.A framework on wavelet-based nonlinear features and extreme learning machine for epileptic seizure detection [J].Biomedical Signal Processing & Control, 2014,10 (1): 1-10.   
[5]Donos C,Dumpelmann M,Schulzebonhage A.Early seizure detection algorithm based on intracranial EEG and random forest classification [J]. International Journal of Neural Systems,2015,25 (05):150426195043004.   
[6]Acharya U R,Oh S L,Hagiwara Y,et al.Deep convolutional neural network for the automated detection and diagnosis of seizure using EEG signals [J].Computers in Biology& Medicine,2017.   
[7]Khan H,Marcuse L,Fields M,et al.Focal onset seizure prediction using convolutional networks [J].IEEE Trans on Biomedical Engineering,2018, PP (99): 1-9.   
[8]Zhang Jian,Zou Junzhong,Wang Min,et al.Automatic detection of

interictal epileptiform discharges based on time-series sequence merging

method [J].Neurocomputing,2013,110 (8): 35-43.   
[9]Wei Zuochen，Zou Junzhong，Zhang Jian．Automatic recognition of chewing noises in epileptic EEG based on period segmentation [J]. Neurocomputing,2016,190:107-116.   
[10]李同庆，邹俊忠，张见，等．基于周期分割的睡眠自动分期研究[J]. 计算机工程与应用,2018.(LiTongqing,Zhou Junzhong,Zhang Jian,et al. The Research of automatic staging of slep based on period segmentation [J]. Computer Engineering and Applications,2018,.）   
[11] Zhang Chong,Tan K C,Li Haizhou,et al.A cost-sensitive deep belief network for imbalanced classification [J]. IEEE Trans on Neural Networks & Learming Systems,2018,PP (99): 1-14.   
[12] Ma Li,Fan Suohai.CURE-SMOTE algorithm and hybrid algorithm for feature selection and parameter optimization based on random forests [J]. Bmc Bioinformatics,2017,18 (1): 169.   
[13] Domingos P,MetaCost:a general method for making classifiers cost-sensitive [Cl// Proc of ACM SIGKDD International Conference on Knowledge Discovery and Data Mining.New York:ACM Press,1999: 155-164.   
[14] Su Chong,Ju Shenggen,Liu Yiguang,et al. Improving random forest and rotation forest for highly imbalanced datasets [J]. Intelligent Data Analysis, 2015,19 (6): 1409-1432.   
[15] Olejarczyk E, Jozwik A, Zmyslowski W,et al.Automatic detection and analysis of the EEG sharp wave-slow wave paterns evoked by fluorinated inhalation anesthetics [J].Clinical Neurophysiology Official Journal of the International Federation of Clinical Neurophysiology，2012,123(8): 1512-1522.   
[16] Bingham E,Mannila H. Random projection in dimensionality reduction: applications to image and text data [C]// Proc of the 7th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining. New York: ACM Press,2001: 245-250.   
[17]Dasgupta S,Gupta A.An elementary proof of the Johnson-Lindenstrauss Lemma [J]. Random Structures & Algorithms,1999,22（1).

[18] Li Gen,Gu Yuantao.Restricted isometry property of Gaussian random projection for finite set of subspaces [J]. IEEE Trans on Signal Processing, 2018,PP(66):1705-1720.

[19] Hoyos-Idrobo A,Varoquaux G,Thirion B.Fast brain decoding with random sampling and random projections [Cl// Proc of International Workshop on Pattern Recognition in Neuroimaging.2O16: 1-4.   
[20] Rodriguez JJ,Kuncheva LI,Alonso C J.Rotation forest: A new classifier ensemble method [J].IEEE Trans on Pattern Anal Mach Intell,2006,28 (10): 1619-1630.   
[21]陆慧娟，刘亚卿，孟亚琼，等．面向基因数据分类的核主成分分析旋转 森林算法[J].计算机科学与探索，2017，11(10):1570-1578.（Lu Huijuan,Liu Yaqing,Meng Yaqiong,et al.Classfier algorithm of genetic data based on kernel principal component analysis and rotation forest [J]. Journal of Frontiers of Computer Science and Technology,2O17,11 (10): 1570-1578. )   
[22] Cieslak D A, Chawla N V.Learning decision trees for unbalanced data [C]// Proc of European Conference on Machine Learning and Knowledge Discovery in Databases.Springer-Verlag,2008: 241-256.   
[23] Shoeb A.Application of machine learning to epileptic seizure onset detection and treatment [D]. Cambridge:Massachusetts Institute of Technology, 2009.   
[24]王凤琴，卢官明，柯亨进，等．基于跨层全连接神经网络的癫痫发作期 识别[J/OL].计算机应用研究,2019,36（7).[2018-04-12].http://www. arocmag.com/article/02-2019-07-013.html.(WangFengqin，Lu Guanming,Ke Hengjin. Epileptic EEG identification with cross layer fully connected neural network [J/OL].Application Research of Computers, 2019,36 (7) .)   
[25] Supratak A，Li Ling，Guo Yike.Feature extraction with stacked autoencoders for epileptic seizure detection [Cl// Proc of the 36th Annual International Conference of IEEE Engineering in Medicine and Biology Society. Piscataway, NJ: IEEE Press,2014: 4184-4187.   
[26] Ahammad N,Fathima T, Joseph P.Detection of epileptic seizure event and onset using EEG [J].Biomed Research International,2014,2014(1): 450573.