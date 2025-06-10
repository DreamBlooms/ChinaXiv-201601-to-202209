# 基于动态EM-SHSMM的异常数据下设备健康预测研究

吴健飞，刘勤明(上海理工大学 管理学院，上海 200093)

摘要：针对设备退化过程中异常数据下的剩余有效寿命预测问题，提出了一种基于动态的期望最大化算法(EM)-分段隐半马尔可夫模型(SHSMM)预测方法。首先，基于 SHSMM的理论框架，采用期望最大化参数自适应估计算法估计模型中的未知参数；其次，基于WGM(1，1)模型，提出动态前向后向灰色填充算法处理样本中的异常数据，并利用健康预测过程预测设备的剩余有效寿命；最后，通过实例分析对模型进行评价和验证。结果表明，提出的设备健康预测方法能有效解决异常数据的问题。

关键词：分段隐半马尔可夫模型；期望最大化自适应估计算法；动态前向后向灰色填充算法；寿命预测中图分类号：TP181 doi:10.3969/j.issn.1001-3695.2018.01.0025

# Equipment health prognosis based on dynamic EM-SHSMM under abnormal data

Wu Jianfei, Liu Qinming† (Business School,University ofShanghai for Science&Technology,Shanghai 2Ooo93,China)

Abstract: Aiming atthe problemof remaininguseful life prognosis under abnormaldata during equipment degradation,this paperdeveloped aprognostic methodbasedondynamic expectation maximization(EM) -segmented hiddensemi-Markov model (SHSMM).First,basedonthe SHSMMmodelframework,itused the expectation maximizationalgorithm toestimate the unknownparametersof themodel.Secondly,to process theanomalydata inthesamples,it proposedadynamic forwardbackward gray-fillagorithmbasedonWGM(1,1),and itcarriedoutteequipmenthealthprognosis.Finaly,iusedacas studyto evaluate theperformanceofthe model.Theresultsshowthattheproposed methodcould efectivelysolve the problem of abnormal data.

Key words:segmented hidden semi-Markov model(SHSMM);expectation-maximization algorithm(EM);dynamic forward backward gray filling algorithm; prognostics

# 0 引言

随着现代化生产制造技术的蓬勃发展，许多机械设备变得越来越复杂。这些机械设备由于运行环境、负载等因素的影响，其性能及健康状态将会发生不可避免的退化，进而造成设备最终的失效。一旦发生由失效引起的事故，所造成的人员财产损失甚至环境破坏往往是不可估量的。因此，及时评估设备的健康状态、预测设备的剩余使用寿命，并据此确定对设备实施维护的最佳时机，对于切实保障复杂设备的运行安全性、可靠性与经济性具有重要的意义[I]。

关于健康预测的研究，引起了国内外学者的广泛的关注，并在最近十年得到了长足的发展。例如Peng 和 Tseng 考虑了Wiener过程的漂移系数为随机变量时的退化建模问题，推导出了寿命分布的显示解，但该方法没有利用设备运行过程中的监测数据[2]。Carr和Wang考虑了多源监测数据下的剩余寿命预测问题，基于拓展卡尔曼滤波技术，提出了一种近似的剩余寿命预测方法，实例验证结果表面多源信息融合能够有效降低剩余寿命预测的不确定性[3]。Kharoufeh等考虑了复杂运行环境下设备的可靠性预测问题，提出了非时齐马尔可夫变化和非时齐半马尔可夫变化两种方法来描述随机环境的变化[4]。Dong和He在隐马尔可夫(HMM)基础上提出了隐半马尔可夫预测(HSMM)方法，搭建了一个集成框架多传感器收集的信号进行融合，显著提高了健康预测的准确性[5-6]。Peng 和 Dong 又对隐半马尔可夫模型进行了优化改进，通过引入基于役龄的老化因子，从而准确描述和预测生产设备的性能劣化[7]。针对设备剩余寿命预测问题，Liu提出了一种基于自适应隐式半马尔可夫模型(AHSMM)的设备健康预测方法，并通过实验证明了该方法比传统的HSMM更有效[8]。FangX等人针对退化信号缺失问题，提出了一个半参数方法来预测部分退化系统的剩余寿命[9]。然而，目前的剩余寿命预测研究大都假设样本数据是完整的[10-14]。但在工程实际中，由于噪声、扰动和人为因素的影响会产生不合常理的数据，而在设备剩余寿命预测研究中对于异常数据的处理大都是简单剔除或者不处理[15-16]。

异常数据的存在会给寿命预测带来较大的偏差，这样带偏差的寿命预测应用于健康管理时势必会对决策结果产生影响[17]。因此，针对样本数据有异常的情况，本文在 SHSMM的整体架构下，首先利用期望最大化自适应估计算法估计模型的未知参数。其次，在改善的WGM(1,1)模型基础上提出动态前向后向灰色填充算法对样本中的异常数据进行处理，并将处理后的完整数据输入到训练好的SHSMM模型中进行状态识别与寿命预测。

# 1 SHSMM基本理论

# 1.1 SHSMM结构

与常规HMM中每个隐藏状态只对应着单一的观测值不同，SHSMM中每个隐藏状态都对应着一个片段的观测值，即一个观测值序列。SHSMM考虑了状态的持续时间，所以当前状态向下一状态进行转换，不仅与当前所处的状态有关，还与当前所处状态的持续时间有关。SHSMM的模型表达式可以描述为$\scriptstyle \theta = ( \pi , A , B , D )$ ，其中： $\pi$ 为初始状态概率分布， $A$ 为宏观状态转移概率矩阵， $B$ 为观测值概率矩阵， $D$ 为状态驻留分布。与常规 HMM类似，SHSMM也需要解决评估、识别和训练问题。

# 1.2推理过程

首先定义一个前向变量：

$$
\alpha _ { t } \left( i \right) = P ( O _ { 1 } O _ { 2 } , \cdots , O _ { t } , q _ { t } = i / \lambda )
$$

表示在 $t$ 时刻产生观测序列 $( O _ { I } O _ { 2 } , \cdots , O _ { t } )$ ，并终止于状态 $i$ 的概率。

假设设备在状态 $i$ 持续的时间为 $d$ ，概率为 $P ( d / j )$ 。 $O _ { I } O _ { 2 }$ $\dots , O _ { t - d }$ 表示在 $_ { t - d }$ 时刻以状态 $i$ 结束而产生的一系列观察变量，$O _ { t - d } O _ { t - d + I }$ ，…， $O _ { t }$ 表示在 $t$ 时刻以状态 $j$ 结束的观察变量，将在$_ { t - d }$ 时刻的所有状态和这些状态的可能持续时间相加，可以得到以下递归公式：

$$
\alpha _ { t } ( j ) = \sum _ { i = 1 } ^ { N } \sum _ { d = 1 } ^ { D } \alpha _ { t - d } \left( i \right) a _ { i j } P _ { j } \left( d \right) \prod _ { s = t - d + 1 } ^ { t } b _ { j } \left( O _ { s } \right)
$$

其中 $: D$ 是每个状态可能持续的最长时间。给定模型 $\lambda$ ，产生观察序列 $o$ 的概率为

$$
P ( O \mid \lambda ) = \sum _ { j = 1 } ^ { N } \alpha _ { T } \left( j \right)
$$

与前向变量类似，后向变量可表示为

$$
\beta _ { t } \left( i \right) = \sum _ { j = 1 } ^ { N } \sum _ { d = 1 } ^ { D } \beta _ { t + d } \left( j \right) a _ { i j } P _ { j } \left( d \right) \prod _ { s = t + 1 } ^ { t + d } b _ { j } \left( O _ { s } \right)
$$

# 2 期望最大化参数自适应估计算法

为了解决SHSMM中的模型训练问题，采用期望最大化估

计方法来估计 $\theta _ { \circ }$ 令 $O { = } \{ \ O _ { { l } } , o _ { 2 } , \cdots , o _ { t } \ \}$ 表示当前采集到的观测值， $S { = } \{ s _ { l } , s _ { 2 } , { \cdots } , s _ { t } \}$ 表示观测值对应的状态，基于观测值 $o$ 的对数似然函数可以表示为

$$
L \left( \theta \right) = { \log \left[ p \left( { O / \theta } \right) \right] }
$$

其中 $: p ( O / \theta )$ 为观测值 $\{ o _ { l } , o _ { 2 } , \cdots , o _ { t } \}$ 的联合概率密度函数，由于$s$ 是一个隐含变量，因此直接使上式关于 $\theta$ 最大化是不可行的。因此，通过最大化似然函数 $p ( O , S / \theta )$ 并对隐含变量 $s$ 求取关于$\mathbf { \delta } _ { O , S / \theta }$ 的期望来估计逼近参数。具体过程为

E步骤：计算

$$
L \Big ( \theta / \hat { \theta } ^ { i } \Big ) = E _ { s / O , \hat { \theta } ^ { i } } \left\{ \log p \big ( O , S / \theta \big ) \right\}
$$

其中 $\hat { \theta } ^ { i }$ 表示在第 $i$ 步估计的参数值。式(2)可以推导为

$$
L \Big ( \theta / \hat { \theta } ^ { i } \Big ) = \sum _ { s } p \Big ( O , S / \hat { \theta } ^ { i } \Big ) \log p \big ( O , S / \theta \big )
$$

又

$$
\begin{array} { r } { p ( O , S / \theta ) = \pi _ { s _ { q _ { 1 } } } P _ { s _ { q _ { 1 } } } ( d = q _ { 1 } - q _ { 0 } ) b _ { s _ { q _ { 1 } } } \left( O _ { 1 } ^ { q _ { 1 } } \right) \cdots } \\ { a _ { s _ { q _ { N - 1 } } S _ { q _ { N } } } P _ { S _ { q _ { n } } } ( d = q _ { N } - q _ { N - 1 } ) b _ { s _ { q _ { N } } } \left( O _ { q _ { N - 1 } + 1 } ^ { q _ { N } } \right) } \end{array}
$$

$$
\begin{array} { c } { { \log p \displaystyle ( { \cal O } , { \cal S } / \theta ) = \log \pi _ { { s _ { q _ { 1 } } } } + \sum _ { n = 1 } ^ { N - 1 } \log a _ { { s _ { q _ { n } } } { s _ { q _ { n + 1 } } } } + } } \\ { { \displaystyle \sum _ { n = 1 } ^ { N } \log b _ { { s _ { q _ { n } } } } \left( { \cal O } _ { q _ { n - 1 } + 1 } ^ { q _ { n } } \right) + \sum _ { n = 1 } ^ { N } \log P _ { { s _ { q _ { n } } } } \left( d = q _ { n } - q _ { n - 1 } \right) } } \end{array}
$$

故 ${ \cal L } \Big ( \theta / \hat { \theta } ^ { i } \Big )$ 可以表示为

$$
\begin{array} { r l } & { \begin{array} { r } { L \Big ( \theta ^ { \prime } \hat { \theta } ^ { i } \Big ) = \displaystyle \sum _ { s } l o g \pi _ { s _ { \mathrm { q } } } p \Big ( O , S ^ { \prime } \hat { \theta } ^ { i } \Big ) + } \\ { \displaystyle \sum _ { s } \Bigg ( \displaystyle \sum _ { n = 1 } ^ { N - 1 } l o g a _ { s _ { \mathrm { q } } , s _ { \mathrm { q } + 1 } } \Big ) p \Big ( O , S ^ { \prime } \hat { \theta } ^ { i } \Big ) + } \end{array} } \\ & { \begin{array} { r } { \sum _ { s } \Bigg ( \displaystyle \sum _ { n = 1 } ^ { N } l o g a _ { s _ { \mathrm { q } } , s _ { \mathrm { q } + 1 } } \Bigg ) p \Big ( O , S ^ { \prime } \hat { \theta } ^ { i } \Big ) + } \\ { \displaystyle \sum _ { s } \Bigg ( \displaystyle \sum _ { n = 1 } ^ { N } l o g b _ { s _ { \mathrm { q } } , s _ { \mathrm { q } } } \Big ( O _ { q _ { \mathrm { m } + 1 } + 1 } ^ { q _ { \mathrm { q } } } \Big ) \Bigg ) p \Big ( O , S ^ { \prime } \hat { \theta } ^ { \prime } \Big ) + \cdots + } \end{array} } \\ & { \begin{array} { r } { \displaystyle \sum _ { s } \Bigg ( \displaystyle \sum _ { n = 1 } ^ { N } l o g { P } _ { s _ { \mathrm { q } } } \Big ( d = q _ { n } - q _ { n - 1 } \Big ) \Bigg ) p \Big ( O , S ^ { \prime } \hat { \theta ^ { \prime } } \Big ) } \end{array} } \end{array}
$$

$\mathbf { M }$ 步骤：计算

$$
\hat { \theta } ^ { ( i + 1 ) } = \arg \operatorname* { m a x } _ { \theta } \Big \{ L \Big ( \theta / \hat { \theta } ^ { i } \Big ) \Big \}
$$

由于要极大化的参数单独出现在方程(6的各个部分中，所以只需对各个部分分别极大化。利用拉格朗日乘数法可得到第$i { + } 1$ 步估计的参数值：

$$
 \overline { { { \pi } } } _ { i } = \frac { \pi _ { i } \Bigl [ \sum _ { d = 1 } ^ { D } \beta _ { d } \left( i \right) P _ { i } \left( d \right) \prod _ { s = { t - d + 1 } } ^ { d } b _ { i } \left( O _ { s } \right) \Bigr ] } { \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { N } \sum _ { d = 1 } ^ { D } \alpha _ { { t - d } } \left( i \right) a _ { i j } P _ { j } \left( d \right) \prod _ { s = { t - d + 1 } } ^ { t } b _ { j } \left( O _ { s } \right) \beta _ { t } \left( j \right) } \left( \begin{array} { c } { { { \pi } } } \\ { { { \pi } } } \end{array} \right) ,
$$

$$
\overline { { a } } _ { i j } = \frac { \sum _ { t = 1 } ^ { T } \alpha _ { t } \left( i \right) a _ { i j } \sum _ { d = 1 } ^ { D } P _ { j } \left( d \right) \prod _ { s = t + 1 } ^ { t + d } b _ { j } \left( O _ { s } \right) \beta _ { t + d } \left( j \right) } { \sum _ { j = 1 } ^ { N } \sum _ { t = 1 } ^ { T } \alpha _ { t } \left( i \right) a _ { i j } \sum _ { d = 1 } ^ { D } P _ { j } \left( d \right) \prod _ { s = t + 1 } ^ { t + d } b _ { j } \left( O _ { s } \right) \beta _ { t + d } \left( j \right) }
$$

$$
\overline { { b } } _ { j } \left( k \right) = \frac { \sum _ { t = 1 , O _ { t } = V _ { k } } ^ { T } \alpha _ { t } \left( j \right) \beta _ { t } \left( j \right) } { \sum _ { k = 1 } ^ { K } \sum _ { t = 1 } ^ { T } \alpha _ { t } \left( j \right) \beta _ { t } \left( j \right) }
$$

$$
\overline { { P } } _ { j } \left( d \right) = \frac { \sum _ { t = 1 } ^ { T } \sum _ { i = 1 } ^ { N } \alpha _ { t } \left( i \right) a _ { i j } P _ { j } \left( d \right) \beta _ { t + d } \left( j \right) \prod _ { s = t + 1 } ^ { t + d } b _ { j } \left( O _ { s } \right) } { \sum _ { d = 1 } ^ { D } \sum _ { t = 1 } ^ { T } \sum _ { i = 1 } ^ { N } \alpha _ { t } \left( i \right) a _ { i j } P _ { j } \left( d \right) \beta _ { t + d } \left( j \right) \prod _ { s = t + 1 } ^ { t + d } b _ { j } \left( O _ { s } \right) }
$$

然后迭代 $E$ 步骤和 $M$ 步骤直到 $p ( O / \theta )$ 收敛终止，由此得到对应的参数估计值。

# 3 基于SHSMM的设备健康预测

# 3.1WGM(1,1)模型

在传统的 $G M ( 1 , 1 )$ 模型中都将生成系数 $W$ 值等于0.5，然而，这并没有考虑到背景影响因素对预测过程的干扰。因此，为了提高模型的预测精度，对原始 $G M ( 1 , 1 )$ 模型中的背景值进行改进，令：

$$
Z ^ { ( 1 ) } \left( k \right) = W X ^ { ( 1 ) } \left( k \right) + \left( 1 - W \right) X ^ { ( 1 ) } \left( k - 1 \right)
$$

将 $Z ^ { ( 1 ) } ( k )$ 代入差分方程 $X ^ { ( 0 ) } ( k ) + a Z ^ { ( 1 ) } ( k ) = b$ 中，并通过数学归纳法可得预测模型为：

$$
\hat { X } ^ { ( 0 ) } \left( k \right) = \frac { { \left( { 1 + a W - a } \right) ^ { k - 2 } } { \left[ b - a { X ^ { ( 0 ) } } \left( { 1 } \right) \right] } } { { \left( { 1 + a W } \right) ^ { k - 1 } } } , k = 2 , 3 \cdots
$$

利用最小二乘法可求出参数 $a , \ b$ ，再将 $a , \ b$ ， $W$ 的值代入到方程(16)中就可得到预测值 $\hat { X } ^ { ( 0 ) } ( k )$ 。

由于给定一个样本数据，模型的精度只取决于生成系数 $W$ 所以如何找到最优生成系数是关键。令 $\varepsilon _ { k } = X ^ { ^ { ( 0 ) } } ( k ) - \hat { X } ^ { ^ { ( 0 ) } } ( k )$ 这样根据真实值与预测值的离差平方和 $S = \sum _ { k = 1 } ^ { n } \varepsilon _ { k } ^ { 2 }$ 最小来找到使模型精度最高的生成系数 $\boldsymbol { W } ^ { * }$ ，并最终以该生成系数下的WGM(1,1)模型进行预测。

# 3.2动态前向后向灰色填充算法

采集设备在各个监测时刻点的健康状态值构成样本数据集$X ^ { ( 0 ) } { = } ( X ^ { ( 0 ) } ( 1 ) , \ X ^ { ( 0 ) } ( 2 ) , \ \cdots , \ X ^ { ( 0 ) } ( n ) )$ 。动态前向后向灰色填充算法的基本步骤如下：

a)找到样本数据集中的第一个异常值 $X ^ { ( 0 ) } ( k _ { 1 } )$ 并将其标记为缺失值，其中 $k _ { 1 }$ 表示第1个异常数据的监测时刻点。

b)在 $( X ^ { ( 0 ) } ( u )$ ，…， $X ^ { ( 0 ) } ( k _ { 1 } { - } 1 ) ~ )$ 前向序列基础上建立WGM(1,1)模型，并计算相对误差，然后动态的向前增大 $\tau$ 个步长，在$( X ^ { ( 0 ) } ( u - \tau )$ ，…， $X ^ { ( 0 ) } ( k _ { 1 } { - } 1 ) )$ 基础上建立新的WGM(1,1)模型，并计算相对误差。循环上述步骤，直到满足 $\tau$ 小于预设值 $w$ 。选择产生相对误差最小的前向灰色预测模型，并计算出异常数据前向填补值 $\hat { X } ^ { ( 0 ) } ( k _ { 1 } )$ 。

c)在 $( X ^ { 0 ) } ( k _ { 1 } { + } 1 ) , ~ \cdots , ~ X ^ { ( 0 ) } ( \nu ) )$ 后向序列基础上建立WGM(1,1)模型，并计算相对误差，然后动态的向后增大 $\tau$ 个步长，在$( X ^ { ( 0 ) } ( k _ { 1 } { + } 1 ) , ~ \cdots , ~ X ^ { ( 0 ) } ( ~ \nu { + } \tau ) )$ 基础上建立新的WGM(1,1)模型，并计算相对误差。循环上述步骤，直到满足 $\tau$ 小于预设值 $w$ 。选择产生相对误差最小的后向灰色预测模型，并计算出异常数据后向填补值x(k）。

d)将步骤b)c）中的计算结果进行加权平均得到：

$$
\overline { { { X } } } ^ { ( 0 ) } \left( k _ { 1 } \right) = \frac { y } { y + z } \hat { X } ^ { ( 0 ) } \left( k _ { 1 } \right) + \frac { z } { y + z } \overset { \cdot \cdot \ ( 0 ) } { X } ^ { ( 0 ) } \left( k _ { 1 } \right)
$$

其中： $y$ 为最优前向灰色模型中样本数据的个数， $z$ 为最优后向灰色模型中样本数据的个数，并将 $\bar { X } ^ { ( 0 ) } ( k _ { 1 } )$ 作为异常数据的填补值。

e)检查填补后的样本数据是否存在异常值，若存在返回步骤1，否则算法终止。

# 3.3健康预测过程

将通过动态前向后向灰色填充算法处理过的完整观测向量输入到各个状态下的SHSMM中，并计算观测向量在不同模型下的似然概率对数值，其中输出似然概率对数值最大的状态即为当前设备所处的状态，从而实现设备的状态识别，在此基础上进行设备的寿命预测。基本预测过程如图1所示。

![](images/710b804d57855d2fa01c115ab61b72f3568135662988977987f78844272c2856.jpg)  
图1健康预测基本过程

假设设备当前所处的健康状态为状态 $l$ ， $R U L _ { I }$ 表示设备处于健康状态l的平均剩余有效寿命，则

$$
R U L _ { i } = a _ { l l } \left[ D ( h _ { l } ) + R U L _ { i + 1 } \right] + a _ { l l + 1 } \left( R U L _ { i + 1 } \right)
$$

# 4 案例分析

为了验证本文所提方法在设备状态识别与寿命预测中的有效性与实用性，本研究应用美国卡特彼勒公司液压泵的全寿命数据进行了实验分析。液压泵可分为好、中、差、坏4种状态。在实验过程中，针对每一种条件收集振动信号，每个状态条件下各获取30个数据样本，采用前20组数据进行模型训练，后10 组数据用于测试模型，具体实验数据如表1所示。

# 4.1模型训练

实验中设定SHSMM训练的最大迭代步数为30，收敛误差限定在 $e { = } 0 . 0 0 0 \ 1$ 。在模型训练过程中，随着迭代次数的增加，最大似然概率的对数值也在增加，直到满足收敛误差为止。基于SHSMM的训练曲线如图2所示。图2可以看出，4个模型的迭代曲线均可以达到训练时设定的误差标准，其训练步数均不超过20步，另外在利用matlab计算过程中，从迭代开始到收敛结束所花费时间不超过30s，说明该方法训练速度快、训练精度高。

表1部分实验数据  

<html><body><table><tr><td>状态</td><td>好</td><td>中</td><td>差 坏</td></tr><tr><td>1</td><td>2.62</td><td>2.41 31.26</td><td>41.78</td></tr><tr><td>2</td><td>2.80</td><td>2.46 20.66</td><td>44.12</td></tr><tr><td>3</td><td>2.65</td><td>2.58 8.89</td><td>31.08</td></tr><tr><td>4</td><td>3.22</td><td>2.37 5.06</td><td>57.04</td></tr><tr><td>5</td><td>2.39</td><td>2.53 41.07</td><td>60.15</td></tr><tr><td>6</td><td>2.38</td><td>2.42 7.53</td><td>108.03</td></tr><tr><td>7</td><td>2.07</td><td>2.44 12.67</td><td>77.27</td></tr><tr><td>8</td><td>2.24</td><td>2.54 5.74</td><td>35.61</td></tr><tr><td>9</td><td>2.25</td><td>2.58 23.22</td><td>69.00</td></tr><tr><td>10</td><td>2.35</td><td>2.37 3.46</td><td>43.44</td></tr><tr><td>11</td><td>2.24</td><td>2.53 2.62</td><td>55.00</td></tr><tr><td>12</td><td>2.28</td><td>2.46 3.66</td><td>44.12</td></tr><tr><td></td><td>：</td><td></td><td></td></tr></table></body></html>

![](images/8f399e4d9fe712cff8acdd2a075b7b15914a6b8b061e183b38ca1fb561b5fad2.jpg)  
图2基于SHSMM的模型训练

利用液压泵的全寿命历史数据训练得到各个状态之间的转移概率以及每个状态下的驻留时间均值和方差，见表2和表3。

表2四个状态之间的转移概率  

<html><body><table><tr><td>状态类别</td><td>好</td><td>中</td><td>差</td><td>坏</td></tr><tr><td>好</td><td>0.8897</td><td>0.1095</td><td>0.0006</td><td>0.0002</td></tr><tr><td>中</td><td>0.0000</td><td>0.7204</td><td>0.2702</td><td>0.0004</td></tr><tr><td>差</td><td>0.0000</td><td>0.0000</td><td>0.9267</td><td>0.0733</td></tr><tr><td>坏</td><td>0.0000</td><td>0.0000</td><td>0.0000</td><td>1.0000</td></tr></table></body></html>

表3四个状态下的驻留时间均值和方差  

<html><body><table><tr><td>状态类别</td><td>好</td><td>中</td><td>差</td><td>坏</td></tr><tr><td>均值</td><td>10.5351</td><td>9.7753</td><td>11.4432</td><td>10.5366</td></tr><tr><td>方差</td><td>1.8291</td><td>0.9893</td><td>1.2641</td><td>0.1980</td></tr></table></body></html>

# 4.2状态诊断

将各个状态下的测试数据分别输入到训练好的HMM 和SHSMM模型中进行测试，可以获得40个测试数据的状态识别结果，结果如表4所示。从表4可以看出，基于SHSMM的状态识别率为 $100 \%$ ，明显要好于HMM。

分别从各个状态下的测试数据中随机选取6组数据，将其设置为异常数据，并将含有异常数据的测试数据输入到训练好的模型中进行测试，同时利用提出的动态前向后向灰色填充算法对异常数据进行处理，然后将处理后的完整测试数据输入到训练好的模型中进行测试，测试结果如表5所示。从表5可以看出异常数据会降低模型的识别率，而处理后的SHSMM识别率为 $100 \%$ 。

表4SHSMM状态识别结果  

<html><body><table><tr><td colspan="2">健康状态</td><td>好</td><td>中</td><td>差</td><td>坏</td><td>诊断率</td></tr><tr><td rowspan="5">HMM</td><td>好</td><td>9</td><td>1</td><td>0</td><td>0</td><td>90%</td></tr><tr><td>中</td><td>2</td><td>7</td><td>1</td><td>0</td><td>70%</td></tr><tr><td>差</td><td>0</td><td>1</td><td>8</td><td>1</td><td>80%</td></tr><tr><td>坏</td><td>0</td><td>1</td><td>2</td><td>8</td><td>70%</td></tr><tr><td>好</td><td>10</td><td>0</td><td>0</td><td>0</td><td>100%</td></tr><tr><td rowspan="3">SHSMM</td><td>中</td><td>0</td><td>10</td><td>0</td><td>0</td><td>100%</td></tr><tr><td>差</td><td>0</td><td>0</td><td>10</td><td>0</td><td>100%</td></tr><tr><td>坏</td><td>0</td><td>0</td><td>0</td><td>10</td><td>100%</td></tr></table></body></html>

表5异常数据下和处理后的状态识别结果  

<html><body><table><tr><td>健康状态</td><td>好</td><td>中</td><td>差 坏</td><td></td><td>诊断率</td></tr><tr><td rowspan="3">异常数据下的SHSMM</td><td>好 5</td><td>1</td><td>0</td><td>0</td><td>83.3%</td></tr><tr><td>中</td><td>0 4</td><td>2</td><td>0</td><td>66.7%</td></tr><tr><td>差</td><td>0 1</td><td>3</td><td>2</td><td>50%</td></tr><tr><td rowspan="4">处理后的SHSMM</td><td>坏</td><td>0 0</td><td>1</td><td>5</td><td>83.3%</td></tr><tr><td>好</td><td>6 0</td><td>0</td><td>0</td><td>100%</td></tr><tr><td>中 差</td><td>0 6 0 0</td><td>0 6</td><td>0 0</td><td>100%</td></tr><tr><td></td><td></td><td></td><td></td><td>100%</td></tr><tr><td></td><td>坏</td><td>0 0</td><td>0</td><td>6</td><td>100%</td></tr></table></body></html>

# 4.3寿命预测

通过对液压泵的全寿命历史数据进行训练，可以获得健康状态间的转移概率以及每个健康状态驻留时间的均值和方差。并且经过测试数据检验，通过训练得到的参数值都是可行的。由方程(19)可知，设备的剩余有效寿命等于当前所处状态下驻留时间均值加上设备下一个健康状态下的剩余有效寿命。根据状态识别结果确定液压泵当前所处的健康状态，然后利用方程(19)计算出液压泵的平均剩余有效寿命。假设液压泵当前处于的健康状态类别为“差”，即第3种状态。由表2和表3知，$a _ { 3 3 } { = } 0 . 9 2 6 7$ ， $D ( h _ { 3 } ) { = } 1 1 . 4 4 3 2$ ， $R U L _ { 4 } { = } 1 0 . 5 3 6 6$ ，计算出液压泵的平均剩余有效寿命为： $R U L { = } 0 . 9 2 6 7 ^ { * } 1 1 . 4 4 3 2 { + } 1 0 . 5 3 6 6 { = } 2 1 . 1 4 1 0 ,$ 与设备处于当前状态的实际剩余寿命21的相对误差仅为 $0 . 6 7 \% ^ { [ 8 ] }$ 因此，剩余预测结果也是可行的。

# 5 结束语

本文提出了一种针对设备健康预测中异常数据如何处理的新方法。提出的动态EM-SHSMM模型能够有效的对设备退化状态进行识别以及剩余寿命的预测，采用期望最大化自适应估计算法估计模型的未知参数，基于WGM(1,1)模型，提出了动态灰色前向后向填充算法对异常数据进行处理，并通过对卡特彼勒公司液压泵的状态诊断实验证明了它的有效性。最后，根据当前的状态识别结果和模型的训练信息可以得到设备的剩余有效寿命。

本文所提出的新方法能够有效解决机械设备故障诊断和寿命预测中存在的数据异常情况。但是，本文仅给出了在SHSMM下的设备状态诊断和寿命预测过程，而健康预测的目的是对设备进行维修决策，因此接下来的研究是根据SHSMM的预测结果对设备进行维护。

# 参考文献：

[1]胡昌华，施权，司小胜，等．数据驱动的寿命预测和健康管理技术研究 进展[J].信息与控制,2017,46(1):72-82.   
[2]Peng C Y,Tseng S T.Mis-Specification Analysis of Linear Degradation Models [J].IEEE Trans on Reliability,2009,58 (3): 444-455.   
[3]Carr M J,Wangbc W.An approximate algorithm for prognostic modelling using condition monitoring information [J]．European Journal of Operational Research,2011,211(1): 90-96.   
[4]Kharoufeh JP,Cox S M,Oxley M E.Reliability of manufacturing equipment in complex environments [J].Annals of Operations Research, 2013,209 (1): 231-254.   
[5]Dong M,He D,Banerjee P,et al. Equipment health diagnosis and prognosis using hidden semi-Markov models [J].International Journal of Advanced Manufacturing Technology,2006,30(7): 738-749.   
[6]Dong M,He D.Hidden semi-Markov model-based methodology for multisensor equipment health diagnosis and prognosis [J].European Journal of Operational Research,2007,178 (3): 858-878.   
[7]Peng Y,Dong M.A prognosis method using age-dependent hidden semiMarkov model for equipment health prediction [J].Mechanical Systems & Signal Processing,2011,25 (1): 237-252.   
[8]刘勤明，李亚琴，吕文元，等．基于自适应隐式半马尔可夫模型的设备 健康诊断与寿命预测方法[J].计算机集成制造系统,2016,22 (9): 2187-2194.   
[9]Fang X, Zhou R,Gebraeel N.An adaptive functional regression-based prognostic model for applications with missng data [J].Reliability Engineering& System Safety,2015,133:266-274.   
[10]武昭融，李秀君，李梦晨，等．基于衰变-Markov 模型的沥青路面性能 预测研究[J].上海理工大学学报,2016,38(2):187-191.   
[11] Daroogheh N,Baniamerian A,Meskin N,et al.Prognosis and health monitoring of nonlinear systems using a hybrid scheme through integration ofPFs and neural networks [J].IEEE Trans on Systems Man& Cybernetics Systems,2017,47(8):1990-2004.   
[12] Zhao FQ,Xie MJ,Tian ZG,et al. Integrated equipment health prognosis considering crack initiation time uncertainty and random shock [J]. Chinese Journal of Mechanical Engineering,2017: 1-13.   
[13]冯磊，王宏力，司小胜，等．基于半随机滤波一期望最大化算法的剩余 寿命在线预测 [J]．航空学报,2015,36(2):555-563.   
[14]陈雄姿，于劲松，唐获音，等．基于贝叶斯 LS-SVR 的锂电池剩余寿命 概率性预测[J].航空学报,2013,34(9):2219-2229.   
[15]曾绍华，魏延，唐远炎．剔除支持向量回归中异常数据算法[J].重庆 大学学报：自然科学版,2012,35(12):120-132.   
[16]徐艺文，徐宁彬，庄重文，等．面向群智感知车联网的异常数据检测算 法[J].湖南大学学报：自科版,2017,44(8):145-151.   
[17] Si X,Hu C,Zhou D. Nonlinear Degradation Process Modeling and Remaining Useful Life Estimation Subject to Measurement Error[J].Acta Automatica Sinica,2013,39 (5):530-541.