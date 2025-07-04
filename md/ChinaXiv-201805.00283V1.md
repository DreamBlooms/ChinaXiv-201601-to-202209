# 约束条件下BN参数最大熵模型扩展学习算法

郭文强，李然，侯勇严，高文强(陕西科技大学 电气与信息工程学院，西安 710021)

摘要：在很多智能系统的参数建模时，用户往往面对建模样本稀少的困境。针对在小数据集条件下贝叶斯网络(BN)参数建模的问题，提出了一种约束数据最大熵BN参数学习算法（CDME)。首先利用小数据集估算BN参数，随后把定性的专家经验转换为不等式约束，并利用 Bootstrap 算法生成满足约束的一组参数候选集，再根据信息最大熵进行加权计算出 BN参数。实验结果表明，当数据量充分时，CDME 参数学习算法与经典的MLE 算法的学习精度近似，表明了算法的正确性；在小数据集条件下，利用CDME 算法，可以对 BN 进行参数建模，学习精度优于 MLE 算法和QMAP 算法。CDME 算法在实际故障诊断样本数据相对稀缺的条件下，获取了诊断BN模型参数，在此基础上完成的诊断推理结果也印证了算法的有效性，为小数据集条件下的参数建模提供了一条新途径。

关键词：贝叶斯网络；小数据集；参数学习；最大熵模型中图分类号：TP301.6 doi: 10.3969/j.issn.1001-3695.2017.08.0868

# Extension parameters learning for BN based on constraints and maximum entropy model

Guo Wenqiang†, Li Ran, Hou Yongyan, Gao Wenqiang (School ofElectrical&Information Engineering Shaanxi UniversityofScience&Technology,Xi'an710o21 China)

Abstract:Whilethe intellgent systems need parameter modeling,users often facethe dilemmaofscarce modelingsamples.In this paper,aBNparameterlearning method-constraineddata maximum entropy(CDME)algorithmisproposedforthemodeling of BN parameters under the smalldata sets.In the caseof estimating BN parameters by using smalldata sets,the qualitative expert knowledgeis transformed into inequalityconstraintsforthe sakeof generating candidate parameter sets by Bootstrap algorithm.ThentheBNparameters areestimated inthe lightof themaximum entropyprinciple.Theexperimentalresultsshow that CDMEalgorithm learming effectsaresimilartothe classical MLEalgorithmwhen the modelingdata sizeissuficient. However,whenthedata size is limited,theparametersofBNcan be modeledbyusingthe CDME,andthe learntaccuracy is superiorto MLEorQMAPalgorithm.CDME is alsoapplied toareal faultdiagnosis whilete datasetisrelatively scarce.The resultsofthe diagnosisreasoning demonstrate thatthe presentedparameter learning approachis effective.The CDMEparameter learning algorithm provides a new modeling way for BN parameter under the small data sets.

Key Words: Bayesian Network; small dataset; parameter learning; maximum entropy model

# 0 引言

贝叶斯网络（Bayesiannetwork，BN）在解决复杂系统的不确定性和不完整性问题凸显出强大的适应性，并且成功应用于智能系统涉及的众多领域[I\~3]。BN 建模是BN推理的基础，而BN推理的结果也往往能检验出建模方法的有效性。BN的建模包括结构建模和参数建模[4\~5]。人们常常可以根据领域专家的经验获取一些定性知识，从而完成BN结构建模。而对于BN的参数建模，即估算BN的参数问题，专家往往很难直接确定出正确的定量参数。在样本数据充足的情况下，经典的最大似然估计（MaximumLikelihoodEstimation,MLE）算法，是目前基于数据较为有效的学习方法之一。但在实际中，从某些系统中获取大量的有效样本数据非常困难和昂贵，如地震预测、航空发动机故障诊断系统中的样本数据等，这样就导致所能获得的系统特征数据相对较少，不能准确地估算出BN中的参数，对系统模型的推理产生影响，甚至得出与客观规律相违背的推理结果[6\~8]。

在小数据集条件下BN的参数建模研究中，文献[9]利用定性约束提出了梯度下降估计（gradient-descent estimation,GDE）方法，利用APN（adaptive probabilistic networks）算法进行求解。文献[10]针对定性影响约束提出了保序回归估计（isotonicregression estimation,IRE）方法，利用保序回归算法校正初始参数使得参数满足序约束。文献[11]针对规范性约束提出了最小自由能(MinimumFreeEnergy,MFE)估计方法，该方法首先将包含KL距离（Kullback-Leibler,divergence）和熵函数的最小自由能函数作为目标优化函数；然后，通过拉格朗日乘子将最小自由能函数与规范性约束结合起来，通过求极值的方法求取参数。文献[2]提出了利用定性影响约束进行BN参数学习的约束最大期望（constrained expectation maximum,CEM)方法。GDE、IRE、MFE、CEM方法的约束类型单一，约束对参数的约束力较小，只能将参数限制到较为宽泛的可行域内，导致参数学习结果不够精确。文献[8]提出了基于双重约束的参数估计（dualconstrainedestimation,DCE）方法，利用Beta分布拟合和保序回归的方法进行小数据集条件下参数的双重约束学习。该算法适用于BN 模型节点均为二值的情况。而现实系统中，如故障诊断等多模式分类问题，其网络节点状态往往是多值的，这就限制了DCE 算法的应用。文献[12,13]提出了约束最大似然（constrainedmaximumlikelihood,CML）方法。该方法首先构建非单调性约束模型；然后，将最大函数与非单调性约束结合构造凸优化问题然后求解。文献[14]提出了定性最大后验概率（qualitative maximuma posterior,QMAP）方法，然后，利用贝叶斯估计方法将真实统计数据和虚拟小数据相结合学习得到BN参数。

分析可以发现：CML方法对参数约束类型没有特殊要求，对参数约束利用率较低，学习效果往往比QMAP逊色[12]。QMAP方法是目前在小数据集条件下一种较为行之有效的新方法[8]。QMAP方法利用定性约束通过拒绝一接受算法对满足约束的参数集合进行虚拟采样，而拒绝一接受算法是建立在概率分布函数估计的基础上，在实际中BN参数的概率分布函数往往很难估计，因而QMAP方法的实用性也受到挑战。

为了解决小数据集条件下BN参数的估计问题，本文提出了一种约束数据最大熵（constrained data maximum entropy,CDME）的参数学习算法。它把小数据集参数学习结果与利用专家经验约束扩展生成的参数候选集有机结合起来，在信息最大熵的基础上估计出BN的参数。

# 1 BN参数学习背景知识

贝叶斯网络参数学习是在结构已知的情况下，通过样本数据和先验知识，获得所有网络节点的条件概率分布的过程。BN由有向无环图( $\operatorname { D A G } ) G$ 和关联每个变量的概率分布集合组成。式（1）为BN的联合概率分布[1]。

$$
P ( X _ { \mathfrak { i } } , X _ { \mathfrak { i } } { \cdot } ^ { \bullet \bullet } X _ { \mathfrak { n } } ) = \prod _ { i = 1 } ^ { n } P ( X _ { \mathfrak { i } } \mid P _ { \mathfrak { a } } ( X _ { \mathfrak { i } } ) )
$$

其中： $P _ { a } ( X _ { i } )$ 表示 $G$ 中 $X _ { _ i }$ 的父节点集合条件概率分布,$P ( X _ { i } \mid P _ { a } ( X _ { i } ) )$ 表示包含在 $G$ 中给定父节点值的变量的每个值的概率。

$P ( X _ { i } \mid P _ { a } ( X _ { i } ) )$ 的第 $k$ 个概率值表示为$\theta _ { _ { i j k } } = P ( X _ { _ { i } } = k \mid P _ { _ a } ( X _ { _ { i } } ) = j )$ 即是节点 $X _ { i }$ 的一个参数，其中，$\theta _ { _ { i j k } } \in \theta$ ， $1 \leq i \leq n$ ， $1 \leq j \leq q _ { i }$ ， $1 \leq k \leq r _ { i }$ 。 $r _ { \scriptscriptstyle i }$ 表示 $X _ { i }$ 的状态数量，$q _ { i }$ 表示 $X _ { i }$ 父节点组合 $P _ { a } ( X _ { i } )$ 的状态数量。显然，节点 $X _ { i }$ 一共有$r _ { i } \times q _ { i }$ 个参数，它们构成了一个 $r _ { i } \times q _ { i }$ 维的矩阵，称之为节点 $X _ { i }$ 的条件概率分布表（condition probability table,CPT）。

# 1.1最大似然估计算法

最大似然估计（MLE）表示为

$$
L _ { \rho } ( e _ { \mathrm { _ 1 } } , e _ { \mathrm { _ 2 } } , \cdots e _ { _ m } ) = \prod _ { i = 1 } ^ { m } f _ { \rho } ( e _ { i } )
$$

其中： $( e _ { _ 1 } , e _ { _ 2 } , \cdots e _ { _ m } )$ 是样本集， $\theta$ 表示该分布的参数， $f _ { \theta } ( e _ { i } )$ 为其概率密度函数7。特别是在实际中，可以用式（3）估计每个参数：

$$
\theta _ { i j k } ^ { M L E } = \frac { N _ { i j k } } { N _ { i j } }
$$

其中： $P _ { a } ( X _ { i } )$ 表示在样本 $D$ 中，父节点 $P _ { a } ( X _ { i } )$ 取第 $j$ 个组合状态的频数，即 $N _ { _ { i j } } = \sum _ { k = 1 } ^ { r } N _ { _ { i j k } }$

MLE 常用于较充分数据集下BN参数估算，但式（3）有一个主要缺陷是不能估计 $N _ { _ { i j } } = 0$ 时的 $\theta _ { i j k } ^ { M L E }$ 。而当训练集有限时,观察值为0的现象时常发生，尤其是数据集规模较小时。为了解决这个问题，这里对式（3）做了一点修正如式（4）所示。

$$
\theta _ { i j k } ^ { * } = \frac { N _ { i j k } + \varepsilon } { N _ { i j } + u \varepsilon }
$$

其中： $u = r _ { i } \times q _ { i } \colon \varepsilon$ 为一个接近于零但不为零的常数。为满足实验要求，式（4）中 $\boldsymbol { \varepsilon }$ 取0.00001。

# 1.2常见的约束集合

在现实世界中，领域专家虽然很难给出BN 模型参数的定量表达,但却往往可以提供节点间的定性信息，即约束信息。式（5）反映了专家先验知识（ $\varOmega$ 和 $G$ ）、数据 ${ \bf \Xi } ( D ) .$ ）与BN参数之间的联系[11,12]。

$\log P ( \theta | G , D , \Omega ) = \log ( D \mid \theta , \Omega ) + \log ( G \mid \theta , \Omega ) - C$ (5)其中： $\theta$ 是学习得到的BN参数， $G$ 是BN结构， $D$ 是样本数据， $\varOmega$ 是通过专家经验知识形成的约束信息。

在BN中常见的约束集合可由定性领域知识转换而来。定性领域知识可以定义为条件概率上的不同约束，这些约束可以描述成以下约束形式[13,15]:

a）范围约束（rangeconstraints）定义了BN中任意参数的上下界， $0 < \alpha _ { _ { i j k } } \leq \theta _ { _ { i j k } } \leq \beta _ { _ { i j k } } \leq 1$ 。b）交叉分布约束（cross-distributionconstraints）定义了一对不同条件参数的相对关系。如果两个约束参数节点指数i和状态值 $k$ ，有不同的父节点组合 $j$ ，这个约束就被称为交叉分布约束，通常由定性因果关系得到，$\theta _ { _ { i j k } } \leq , \geq \theta _ { _ { i j k } } , \forall j \neq j ^ { \prime }$ 。

c）内分布约束（intra-distributionconstraints）定义了一对相同条件的参数的相对关系。如果约束参数共享节点指数i和父节点组合 $j$ ，却有不同的状态值 $k$ ，则这个约束被称为内分布约束， $\theta _ { _ { i j k } } \leq , \geq \theta _ { _ { i j k } }$ ， $\forall k \neq k ^ { \prime }$ 。

d）间分布约束（inter-distributionconstraints）定义了一对相同条件的参数的相对关系。如果两个约束参数不共享任何节点指数 $i .$ 、父节点组合 $j$ 和状态值 $k$ ，这个约束被称为间分布约束， $\theta _ { _ { i j k } } \leq , \geq \theta _ { _ { i j k } } , \forall i \neq i , j \neq j , k \neq k$ 。

e）公理约束。描述参考固定父节点配置状态的参数之间的关系。这意味着，这是一个领域专家不需要提供且非常基本的约束， $\sum _ { k = 1 } ^ { r } \theta _ { _ { i j k } } = 1 , 0 \leq \theta _ { _ { i j k } } \leq 1 , \forall i , j , k$ 。

f）近似等式约束。描述任何两个参数之间的密切关系。为了便于计算，因此可以将其写为：$\left| \theta _ { i j k } - \theta _ { i j k } \right| \le \sigma , \forall i \neq i , j \neq j , k \neq k ^ { \prime } \ .$

g)添加协同约束。描述不同分布下两个参数之和的比较关系： $\begin{array} { r } { \theta _ { _ { i j _ { 1 } k } } + \theta _ { _ { i j _ { 2 } k } } \le \theta _ { _ { i j _ { 3 } k } } + \theta _ { _ { i j _ { 4 } k } } , \forall i , k } \end{array}$

h)乘积协同约束。描述不同分布下两个参数的乘积之间的比较关系： $\theta _ { _ { i j _ { \mathrm { l } } k } } * \theta _ { _ { i j _ { \mathrm { 2 } } k } } \le \theta _ { _ { i j _ { \mathrm { 3 } } k } } * \theta _ { _ { i j _ { \mathrm { 4 } } k } } , \forall i , k$ 。

# 1.3 最大熵原理

最大熵的基本思想是在满足所有已知事件的基础上对未知事件作最客观均一的估计。要从一个允许的概率分布集合 $C$ 中选择一个模型，选择具有最大熵 $H _ { \mathbf { \Phi } } ( p )$ 的模型 $p _ { * } \in C$ ，其模型的形式化表示为[16]

$$
\begin{array} { l } { p _ { \ast } = \arg \underset { \underset { p \in C } { \operatorname* { m a x } } } { \operatorname* { m a x } } H ( p ) } \\ { = \arg \underset { p \in C } { \operatorname* { m a x } } _ { - } \sum _ { \boldsymbol { x } , \boldsymbol { y } } p ( \boldsymbol { x } ) p ( \boldsymbol { y } \mid \boldsymbol { x } ) \log p ( \boldsymbol { y } \mid \boldsymbol { x } ) } \end{array}
$$

其中： $C$ 为满足约束条件的概率分布集合， $x , y$ 为随机变量对应事件，条件分布 $p ( y \vert x )$ 的数学测量由条件熵提供。

本文选择最大熵统计模型作为原始领域（BN知识和样本数据）和目标领域（BN参数学习）的估计模型，主要基于以下考虑：最大熵所采用的BN分布参数对数据的先验分布也不作任何要求，可任意组合，而不会破坏整个估计模型的一致性；同时，它自然地解决了统计模型中参数平滑的问题，即BN参数应满足约束知识 $\varOmega$ ，假设有 $L$ 条参数候选集都满足约束知识，根据最大熵原理，它们有均等的概率逼近真实的BN参数。因此，即使目标领域中部分特征未在原始领域出现，由于约束知识的支持，也能获得较好的参数估算效果

# 1.4 KL距离

KL距离，常用来衡量两个概率分布的距离。本文用KL距离来衡量BN参数估算方法的精度。如式（7）所示[17]。

$$
K L ( \theta _ { i } | \theta _ { i } ) = \sum _ { j = 1 } ^ { q _ { i } } \sum _ { k = 1 } ^ { r _ { i } } \theta _ { i j k } \ln \frac { \theta _ { i j k } } { \theta _ { i j k } ^ { ' } }
$$

其中： $\theta _ { _ { i j k } }$ 代表真实参数， $\dot { \theta _ { i j k } }$ 代表估算得到的参数。显然，估计的BN参数越接近真实BN参数，KL值越小。

# 2 约束数据最大熵参数学习算法

本文提出的约束数据最大熵BN参数学习算法的流程如图1所示。

开始参数设置α、L、Q、θ=Φ  
由初始小样本集根据式(4)  
计算一组初始参数 $\boldsymbol { \theta } _ { i j k } ^ { * } ( S )$   
并把 $\theta _ { i j k } ^ { * } ( S )$ 插入参数集0利用Bootstrap法随机生成  
第（L-1个参数候选集 结束√N 是约果 8最终Y  
0=10-1(2）,0） 0={(,((S))L=L-1N YL<1?

CDME算法主要步骤如下：

a)设置参数权重因子 $\alpha$ $( 0 { \leq } \alpha { \leq } 1$ )；备选参数集个数 $L$ 、约束 集合 $\varOmega$ ，令中间变量参数集 $\theta$ 为空集;

b)由初始小样本集根据式(4)计算出一组初始参数 $\theta _ { _ { i j k } } ^ { * } ( S )$ ，并把 $\theta _ { i j k } ^ { ' } ( S )$ 插入参数集 $\theta$

c)利用Bootstrap[18]方法生成第 $\left( L \mathbf { - } 1 \right)$ 个参数候选集 $\theta _ { i j k } ^ { L - 1 } ( \Omega )$ u

d)判断第 $\left( L \mathrm { - } 1 \right)$ 个参数候选集 $\theta _ { i j k } ^ { L - 1 } ( \Omega )$ 是否满足约束 $\varOmega$ 。如满足，则把第 $( L \mathrm { - } 1 )$ 个参数候选集 $\theta _ { \boldsymbol { i } \boldsymbol { j } \boldsymbol { k } } ^ { L - 1 } ( \Omega )$ 插入中间变量参数集$\theta$ ，并令 $\scriptstyle { L = L - 1 }$ ；否则，返回第三步。

e)判断 $L$ 是否小于1。

（a）若是，输出，并将备选参数集 $\theta$ 参数取出，根据最大熵原则，按式（8）进行计算得到最终的学习参数θCDME 。

$$
\theta _ { _ { i j k } } ^ { C D M E } = \frac { \displaystyle \alpha \sum _ { _ { B = 1 } } ^ { { L - 1 } } \theta _ { _ { i j k } } ^ { ( B ) } + ( 1 - \alpha ) \theta _ { _ { i j k } } ^ { * } ( S ) } { L }
$$

$\sum _ { B = 1 } ^ { L - 1 } \theta _ { i j k } ^ { ( B ) }$ $( L - 1 )$ 参数候选集的和， $\theta _ { i j k } ^ { * } ( S )$ 是由初始小样本集计算出的一组初始参数， $\scriptstyle a$ 是权重因子。

(b）否则，跳转至步c)。

注意到式（8）的参数模型中，当 $\scriptstyle a = 0$ ， $L { = } 1$ 时，在样本数据量充足条件下计算BN参数时，上式的形式实际是MLE 的结果。因此该参数模型是MLE算法的泛化形式；MLE是该参数模型的一种特例。

根据定性约束生成的候选参数具有同样的权重，体现了最大熵原则。另外，当 $\scriptstyle a$ 取较小值时，样本数据在参数学习结果中的决定性作用会凸显，而定性约束的专家经验对学习结果影响会减少；反之，当 $\alpha$ 取较大值时，定性约束的专家经验对学习结果影响会增大，可补偿样本数据量少对学习结果的影响。

约束数据最大熵BN参数学习算法拟定了一个用约束信息和小数据集估算BN参数的框架。它可以将样本数据和专家定性经验等不同源的信息集中到一个框架下进行综合考虑，在解决BN参数问题时具有良好的形式上的一致性。

# 3 实验与分析

本文进行了两组实验分析来验证本文方法的有效性。第一组实验引用经典贝叶斯网络模型草坪湿润模型[19]在模拟数据下分别采用MLE方法、QMAP方法和本文方法进行BN参数学习对比研究；第二组实验是在真实故障诊断数据下采用本文方法进行BN参数学习及推理诊断，进一步验证本文所提BN参数学习方法的优越性及实用性。本文所有实验所用PC配置为：2GHz处理器，6G内存，程序通过MATLAB2014a 编程完成。

# 3.1模拟数据BN参数建模实验

草坪湿润模型是验证BN 学习算法的经典实验模型之一。图2为该BN模型的结构图。

![](images/3092569de94f66bd4b67179da78d7f4066c4ae101c2fdece31da5f5fcbfb28c1.jpg)  
图2草坪湿润BN模型

图中该网络共有4个节点，分别是：C、S、R、W节点，对W节点进行参数学习。

# 3.1.1实验设置

参数权重因子 $\alpha$ 取0.3，备选参数集个数 $L$ 为500，参数事件集合如表1所示，对节点W中的参数进行了编号。其中事件取值“1”表示事件为“假”，“2”表示事件为“真”。表2为参数P(WIS,R)所满足的约束集合 $\varOmega$ 。

表1参数事件集合  

<html><body><table><tr><td>参数编号</td><td>事件</td></tr><tr><td>P1</td><td>P(W=1|S=1,R= 1)</td></tr><tr><td>P2</td><td>P(W=1|S=1,R= 2)</td></tr><tr><td>P3</td><td>P(W= 1| S= 2,R= 1)</td></tr><tr><td>P4</td><td>P(W=1| S=2,R= 2)</td></tr><tr><td>P5</td><td>P(W= 2|S= 1,R= 1)</td></tr><tr><td>P6</td><td>P(W=2|S=1,R= 2)</td></tr><tr><td>P7</td><td>P(W= 2|S= 2,R = 1)</td></tr><tr><td>P8</td><td>P(W=2|S=2,R= 2)</td></tr></table></body></html>

表2参数P(W|S.R)所满足的约束集合  

<html><body><table><tr><td>约束编号</td><td>约束条件</td><td>约束编号</td><td>约束条件</td></tr><tr><td>C1</td><td>P1>P5</td><td>C5</td><td>P7>P3,</td></tr><tr><td>C2</td><td>P8>P5</td><td>C6</td><td>P6>P5</td></tr><tr><td>C3</td><td>P8>P4</td><td>C7</td><td>P6>P2,</td></tr><tr><td>C4</td><td>P8>P7</td><td>C8</td><td>P7>P5,</td></tr><tr><td>C9</td><td>P8>P6</td><td></td><td>/</td></tr></table></body></html>

在表2中， $\mathbf { P l } { \mathrm { > P } } 5$ 表示在喷灌机(S）“没有喷水且天气（R)没有下雨”这一条件下，草坪事件W为“不湿”的概率大于“草地湿”的概率，本文将其称为约束条件“C1”，以此类推形成其他8个条件。很显然，上述约束集合是符合大众的认知，是能够被领域专家所欣然接受的。

# 3.1.2实验结果分析

本文将在约束给定的情况下，给出不同样本数量下的 KL距离对比，KL距离通过式（7）计算得到。为了显示方便，本文对KL距离做了对数处理，形成相应的分贝值（dB)，以此来衡量学习方法的学习精度。

在样本数量为35组的条件下，分别用MLE、QMAP、和CDME方法学习W节点参数。图3所示为三种方法学习15次得到的估计参数与真实参数间KL距离取平均值的对比情况。图4所示为相应的KL距离的盒形图。

![](images/1ddb28d3b18bbd18a37b3897c68c2298d702cec17c52327d67e15e67d0259e8d.jpg)  
图31\~35组样本数量下W节点三种方法KL距离对比

![](images/71eb3430ac8accd700df978eab2377088426022aad37e0899065d799ce40f306.jpg)  
图41\~35组样本数量下不同学习算法KL距离盒形图对比

![](images/908a011567b17a9ef2c36762689c124430c328c1ba8ac19692e643a27fc315ab.jpg)  
图51\~300组样本数量下W节点三种方法KL距离对比

在样本数量相对充足时，实验中取300组样本，用三种方法学习W节点参数的KL距离对比如图5所示。

通过BN参数学习对比实验结果可以发现：在小数据样本数量下，MLE方法KL距离较大，QMAP方法和CDME方法具有明显优势，且CDME学习精度略高于QMAP；随着样本数量的不断增加，MLE方法KL距离值逐渐减小，并且在样本数量分别等于30和31时其KL距离与QMAP方法和CDME方法的KL距离相交。但QMAP方法的KL距离下降趋势不明显。与QMAP不同，CDME方法随着样本数量增加，KL距离总体呈一定的下降趋势。

分析可知，CDME方法在小数据集条件下，可充分利用参数间的约束条件，估算出的BN参数在精度方面较MLE、QMAP方法更具优良的性能；在样本数量充足时本文方法依然可行，并能充分利用获取的数据集中蕴藏的信息，补偿BN建模的不确定性，不断修正、提高学习参数的精度。

# 3.2真实数据下BN参数建模及故障诊断实验

本实验所用的轴承故障诊断模型和469条特征数据集均出自文献[20]。实验原始数据源自美国CaseWesternReserveUniversity轴承故障模拟实验室，他们用破坏性实验获取了丰富的典型故障类型的监测数据。而实际生产过程中，人们能获取的设备故障数据往往有限。为此，本文分别尝试在小数据（35组）和充足数据（300 组）条件下，利用CDME 算法进行BN参数学习，然后在此基础上，利用后169组特征数据集进行推理诊断实验，验证CDME算法的有效性。轴承故障诊断BN 模型结构如图6所示。

![](images/a7ff90b848053a9753a3e4077346b921b342528b9dd1534b38c75ff0926e4314.jpg)  
图6轴承故障诊断模型

图6中该BN模型共有9个节点，1个父节点，8个子节点代表8个特征向量 $\mathrm { D } _ { 0 } { \sim } \mathrm { D } _ { 7 }$ 。父节点有四种状态分别为：正常状态、内圈故障、外圈故障和滚动体故障。它们分别对应BN 诊断模型的四种网络诊断输出，诊断信度为 $\scriptstyle \gamma = 0 . 7 0$ 。为了对轴承故障进行诊断，先通过领域专家的经验完成了BN模型的结构建模。其次，对故障数据利用特征提取函数并离散化后得到特征向量，然后采取CDME方法进行故障诊断BN参数建模，得到故障诊断推理所需的BN模型。

# 3.2.1实验参数设置

备用参数集个数 $L$ 设为500；参数约束集 $\varOmega$ 根据专家经验得到8条； $\alpha$ 取0.3。BN推理选用经典的联合树算法。

# 3.2.2故障诊断推理结果对比

表3和表4是分别利用35组、300组特征数据建模，然后使用169组特征数据诊断推理结果。

表335组数据下CDME学习方法推理结果  

<html><body><table><tr><td>状态类型</td><td>测试个数</td><td>正判个数</td><td>正判率</td></tr><tr><td>正常状态</td><td>169</td><td>169</td><td>100%</td></tr><tr><td>内圈故障</td><td>169</td><td>169</td><td>100%</td></tr><tr><td>滚动体故障</td><td>169</td><td>154</td><td>91.12%</td></tr><tr><td>外圈故障</td><td>169</td><td>139</td><td>82.25%</td></tr></table></body></html>

表4300 组数据下CDME 学习方法推理结果  

<html><body><table><tr><td>状态类型</td><td>测试个数</td><td>正判个数</td><td>正判率</td></tr><tr><td>正常状态</td><td>169</td><td>169</td><td>100%</td></tr><tr><td>内圈故障</td><td>169</td><td>169</td><td>100%</td></tr><tr><td>滚动体故障</td><td>169</td><td>162</td><td>95.86%</td></tr><tr><td>外圈故障</td><td>169</td><td>157</td><td>92.90%</td></tr></table></body></html>

实验结果表明：在小数据集条件下，用CDME算法建模之后进行推理，在整体上其正判率较高，推力能力较好（仅在推断外圈故障时其正判率略低于其他状态)。由此也进一步说明用CDME 算法在小数据集条件下进行参数建模的有效性。在样本数量较充足时，CDME算法可利用数据集信息修正BN学习参数，提高了BN模型的学习精度。

# 4 结束语

本文提出的CDME 算法利用小数据集估算BN参数的同时，把定性的专家经验转换为不等式约束，利用Bootstrap 算法生成满足约束的参数候选集，再根据信息最大熵原则计算出BN参数。实验表明：本文所提的CDME方法在小数据集下学习BN的参数具有一定的有效性和优越性。在故障诊断建模方面的应用，诊断推理结果印证了算法的实用性。在样本数量充足时本文算法依然可行，并能充分利用获取的数据集中蕴藏的信息，消减BN建模中的不确定性，不断修正、提高学习参数的精度。本文研究的CDME算法在实际智能系统建模数据稀缺的情况下，具有较好的实用前景，为小数据集条件下的BN参数建模提供了一种新途径。

# 参考文献：

[1]Dojer N.Learning Bayesian networks from datasets joining continuous and discrete variables [J].International Journal ofApproximate Reasoning,2016,

78 (C):116-124

[2]Liao Wenhui,Ji Qiang.Learning Bayesian network parameters under incomplete data with domain knowledge [J].Pattern Recognition,2009,42 (11): 3046-3056.   
[3]陈为，朱标，张宏鑫.BN-Mapping：基于贝叶斯网络的地理空间数据可 视分析[J].计算机学报,2016,39(07):1281-1293.   
[4]李硕豪，张军．贝叶斯网络结构学习综述[J].计算机应用研究,2015, 32 (3): 641-646.   
[5]陈静，蒋正凯，付敬奇．基于 Netica 的自学习贝叶斯网络的构建[J]. 电子测量与仪器学报,2016,30(11):1687-1693.   
[6]肖蒙，张友鹏．小数据集条件下的多态系统贝叶斯网络参数学习[J]. 计算机科学,2015,42(4):253-257.   
[7] 李子达，廖士中．小样本贝叶斯网络参数学习方法[J].计算机工程, 2016,42 (8): 153-159+165.   
[8]郭志高，高晓光，邸若海．小数据集条件下基于双重约束的 BN 参数学 习[J]．自动化学报,2014,40(7):1509-1516.   
[9]Altendorf EE,Restificar AC,Dietterich TG.Learning from Sparse Data by Exploiting Monotonicity Constraints [C]//Proc of the 21st Conference on Uncertainty in Artificial Intelligence.20o5:18-25.   
[10] Feelders A,Gaagl.Learning Bayesian networks parameters under order constraints [J]. International Journal of Approximate Reasoning,2006,42 (1//2): 37-53.   
[11] Isozaki T,Kato N, Ueno M.“Data temperature"in minimum free energies for parameter learning of Bayesian networks [J]. International Journal on Artificial Intelligence Tools,2009,18(5): 653-671.   
[12] Niculescu R,Mitchell M,Rao B.Bayesian network learning with parameter constraints [J].Journal of Machine Learning Research,20o6,7(1):1357- 1383.   
[13] Campos C,Tong Yang, Ji Qiang. Constrained maximum likelihood learning of bayesian networks for facial action recognition [Cl// Computer Vision. 2008:168-181.   
[14] Chang Rui,Shoemaker R,Wang Wei.A novel knowledge-driven systems biology approach for phenotype prediction upon genetic intervention [J]. Transactions on Computational Biology and Bioinformatics,2011,1(8): 1170-1181.   
[15] Guo Zhigao,Gao Xiaoguang,Di Ruohai,et al.Learning Bayesian network parameters from small data set: a spatially maximum a posteriori method [C]//Proc of International Workshop on Advanced Methodologies for Bayesian Networks.2015:32-45.   
[16] Berger AL,Pietra S,Pietra V.A Maximum Entropy approach to Natural Language Processing[J]. Computational Linguistics,1996,22(1): 38-73.   
[17] Kullback S,Leibler R A. On information and sufficiency [J].Annals of Mathematical Statistics,1951,22(1): 79-86.   
[18]孙慧玲，胡伟文，刘海涛．小样本情况下参数区间估计的改进方法[J] 哈尔滨理工大学学报,2017,22(01):109-113.   
[19] Stuart J.Russell,PeterN.人工智能：一种现代的方法 [M]．殷建平，译. 3版．北京：清华大学出版社,2013.   
[20]郭文强，张宝嵘，彭程，等．基于小波包和 BN 模型的深沟球轴承故障 诊断[J].轴承,2016,59(3):48-52.