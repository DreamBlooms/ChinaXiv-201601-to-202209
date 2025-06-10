# 利用PSO-SA混合优化支持向量回归的径流预报模型研究

蒋林利1，李洁1，吴建生1,2

(1．广西科技师范学院 数学与计算机科学学院，广西 来宾 546199;2.武汉理工大学 信息工程学院，武汉 430070)

摘要：为了有效提高径流预报的准确度，提出一种有效的融合优化策略，采用基于粒子群和模拟退火算法相结合的混合方法同时优化支持向量回归核函数类型和内核参数，以此建立一种有效的混合优化支持向量回归径流预报模型。提出的方法为核函数选择和参数优化提供了一种有效途径。通过对广西柳州柳江径流实例分析，并与纯粹的支持向量回归模型对比，研究结果表明，该模型预测稳定，具有较高泛化性能和预测准确度，为径流预报提供了一种有效预测方法。

关键词：支持向量回归；粒子群；模拟退火；融合改进；径流预报模型 中图分类号：TP301.6 doi: 10.3969/j.issn.1001-3695.2018.03.0148

# Runoff forecasting based on hybrid optimized support vector regression using PSO-SA

Jiang Linli1,Li Jiel,Wu Jiansheng1,2 (1.DeptofMathematics&ComputerScienceGuangxiScience&TechnologyTeachersColege,LaibinGuangxi545004,China; 2.School of Information Engineering,Wuhan University ofTechnology,Wuhan 43oo70,China)

Abstract: Inordertoefectivelyimprovetheaccuracyofrunoffrecasting,thispaperpropoedanefectivehybridoptimiation strategy which was basedonthecombinationof particle swarm optimizationand simulated annealing algorithm,and it also optimized the typeof kernel functionand the kerelparameter setingof Support Vector Regressionto establish an effective hybridoptimizationsupport vectorregressionrunofforecasting model.Theproposed method providedaneffective wayforthe choice ofkernel functions andparameter optimization.Byanalyzing the examples ofGuangxiLiujiang's Riverrunoffand with puresupportvectorregresion modelcomparison,theresultsofthestudyshowthatthemodel is stable inpredictionand ithas highgeneralizatonperformanceandaccuracyofprediction,and itcanprovideanefectivepredictiomethodforrunoffrecast. Key words:supportvectorregression; particle swarm optimization;simulatedannealing; fusion improvement;unof forecast model

# 0 引言

准确及时的降雨径流预报是水资源管理一个非常重要的课题，因为有效准确的降雨径流预报有助于指导提前防备，可以有效避免如生命安全、经济损失等的意外事故[1]。然而，由于存在影响水文的各种非线性因素[2]，如降雨特征、流域形态、水位和土壤含水量等，一个相对稳固、准确的降雨径流模型的开发已经成为了水文学领域中一个非常困难的课题[3]。此外，数据的缺失、噪声数据和无效数据更是加重了降雨径流模型研究中数据的匮乏[4]，模型构建面临更大的挑战。

神经网络(NNS)[5能够在潜在关系未知或者难以描述的情况下，发现数据之间微妙的函数关系，已经成为模拟降雨径流预报一个非常有用的方法[。然而，神经网络也存在着一些不足，如一系列控制参数的获取，难以获得一个稳定的解决方案和存在模型过拟合的风险。

近年来，支持向量机(support vector machine，SVM)得到不断发展，这是一种基于统计学习理论的学习机，坚持结构风险最小化原则，并坚持寻求最大限度地减少所产生误差的上限，而不是训练误差最小化[7]。随着Vapnik对不敏感损失函数的引入，支持向量机的回归模型，即支持向量回归(support vectorregression，SVR)，在解决非线性估计问题上也得到了越来越多的关注。SVR成为了解决大规模数据集分类问题的有力方法。并且由于其许多有吸引力的特点和良好的泛化性能，在学术界和工业界平台上已经取得了很大的成功。

然而，使用支持向量机的回归时都面临两个问题：如何选择SVR的核函数类型以及如何确定SVR核函数的最佳参数，这两个问题至关重要。因为核函数类型影响支持向量回归参数，参数的优化又决定了核函数的性能，两者相互影响和作用，需要协同考虑。SVR的性能高度依赖于SVR的核函数类型和SVR核函数的参数设置。恰当的SVR核函数类型和SVR核函数的参数可以提高SVR回归精度。而不当的SVR参数将会导致过拟合或者低拟合[8]。普通的 SVR模型中，支持向量回归模型产生的效果很大程度上依赖于操作者的经验，操作人员依据经验通过试凑获得最优且有效的参数，然而稍不小心，便容易使模型陷入过拟合，这样的模型可能会很好地预测过去的事件，但无法预测未来事件。

与此同时，基于智能群体的粒子群优化算法(particleswarmoptimization，PSO)已经被广泛地应用于优化核函数参数。KennedyJ于1995年提出的粒子群优化算法收敛速度快，能不断更新粒子的位置及速度来搜索最优解。对一些相对简单的问题，简单的优化算法便可以得到满意的结果。但是对于多维的非线性优化问题，粒子群优化算法在优化过程中容易出现局部收敛现象，从而导致陷入局部最优解。为了使粒子群算法避免局部最优解，研究人员提出了各种方法弥补PSO 缺陷，改进PSO 算法优化模型。吴建生等提出使用BP算法避免粒子群优化算法在局部搜索过程中的收敛停滞现象[9]。而模拟退火算法（SimulatedAnnealing，SA）是一种良好可有效避免陷入局部极小值，并能够在全局寻找最优解的优化算法，可以有效的弥补PSO 算法的缺陷。

近年来的一些研究也已经相继提出了针对高斯核函数参数优化的算法，如遗传算法(genetic algorithm，GA)、粒子群优化(PSO)和免疫算法(immune algorithm，IA)[10\~12]，但没有出现针对SVR核函数类型的选择算法。

为此，本文提出一种模拟退火和粒子群混合算法优化SVR的核函数类型及其参数，命名为SVR-HPSOSA。该算法能同时确定SVR模型适当的核函数类型和最优核参数。SVR-HPSOSA算法可以使粒子群优化算法避免过早陷入局部最优解，能够找到全局最优解。并应用于广西柳州市的柳江径流数据中，建立基于混合粒子群及模拟退火算法进化支持向量回归的径流预报模型。结果表明，运用SVR-HPSOSA模型进行日降雨量径流预报，显示了较高的模型预测精度和泛化能力。

# 1 支持向量回归

# 1.1支持向量回归模型

支持向量机回归分析的主要思想是：假设 $\left( x _ { i } , d _ { i } \right) _ { i = 1 } ^ { N }$ 是给定的训练数据， $x _ { i }$ 是输入向量， $d _ { i }$ 是输出向量， $\mathrm { ~  ~ N ~ }$ 为数据的总维数。线型回归函数定义如下式：

$$
f ( x ) = \omega \phi ( x _ { i } ) + b
$$

其中： $\omega$ 和 $\mathsf { b }$ 是相关系数， $\phi ( x )$ 是从输入空间到高维特征空间的非线性映射。

支持向量机的目的是在不敏感函数训练模式中保证 $\left\| \omega \right\| ^ { 2 }$ 规范尽可能的小。根据文献[13],支持向量机函数为

$$
f ( x , \alpha _ { i } , \alpha _ { i } ^ { * } ) = \sum _ { i = 1 } ^ { N } ( \alpha _ { i } , \alpha _ { i } ^ { * } ) K ( x , x _ { i } ) + b
$$

其中： $K ( x , x _ { i } )$ 为核函数。在机器学习理论中，有如下四种常用的核函数：

# 1.2支持向量回归参数

支持向量回归方法是近年来出现的解决非线型回归问题的一种高效方法。设计一个有效的支持向量回归模型，需要精心挑选支持向量回归的四个基本参数。不同的参数设置会对支持向量机性能产生显著的差异。这要确定的四个参数包括：

a）核函数类型。核函数用于在输入空间和特征空间之间构  
造一个非线性映射。b）内核参数。包括表示多项式核的拦截参数t，代表多项  
式核的程度系数d，表示高斯核函数的带宽 $\sigma$ ，以及 sigmoid  
核函数的参数 $\alpha$ 和 $\beta$ 。c）正则化参数 $c$ 。代表最大限度地减少训练误差和减少模  
型复杂度的产生成本。d)ε-不敏感损失函数。它等效于在训练数据点的近似精度。

# 2 HPSOSA混合优化支持向量回归策略

# 2.1粒子群优化算法

PSO是由Kennedy 和Eberhart 在1995发明的一种进化计算技术，它已经被成功地用于解决复杂的优化问题，由于其在简单仿真系统中的灵活性和有效性，引起了研究者的兴趣。粒子群优化算法源于对鸟群捕食的行为研究。粒子群优化算法的基本思想是通过群体中个体之间的协作和信息共享来寻找最优解。

PSO的优势在于简单容易实现并且没有许多参数的调节。目前已被广泛应用于函数优化、神经网络训练、模糊系统控制以及其他遗传算法的应用领域。但是近年的研究已经指出了其在应用领域的不足，如由于过早收敛导致在搜索过程中发生粒子群最优解陷入局部最小的缺点。

粒子群优化算法的算法思想是：粒子i在N维空间的位置表示为矢量 $X _ { i } = ( x _ { 1 } , x _ { 2 } , \cdots , x _ { N } )$ ，飞行速度表示为矢量$V _ { i } = ( \nu _ { 1 } , \nu _ { 2 } , \cdots , \nu _ { N } )$ 。每个粒子都有一个由目标函数决定的适应值(fitnessvalue)，并且知道自己到目前为止发现的最好位置（ $P _ { b e s t }$ )和现在的位置 $X _ { i }$ 。这个可以看作是粒子自己的飞行经验。

除此之外，每个粒子还知道到目前为止整个群体中所有粒子发现的最好位置( $G _ { b e s t }$ ） $G _ { b e s t }$ 是 $P _ { b e s t }$ 中的最好值)。这是粒子同伴的经验。粒子就是通过自己的经验和同伴中最好的经验来决定下一步的运动。

PSO 初始化为一群随机粒子(随机解)。然后通过迭代找到最优解。在每一次的迭代中，粒子通过跟踪两个“极值"(Pbest，$G _ { b e s t }$ )来更新自己。找到这两个最优值后，标准 PSO 算法粒子通过下面的公式来更新自己的速度和位置。

$$
V _ { i } = \omega { \times } V _ { i } + c _ { 1 } { \times } r a n d ( ) { \times } ( P b e s t _ { i } - x _ { i } ) + c _ { 2 } { \times } r a n d ( ) { \times } ( G b e s t _ { i } - x _ { i } )
$$

$$
x _ { i } = x _ { i } + V _ { i }
$$

上面两式中 $i = 1 , 2 , \cdots , M \mathrm { ~ , ~ } \mathrm { M }$ 是该群体中粒子的总数； $\omega$ 非负，称为惯性因子； $V _ { i }$ 是粒子的速度； $P _ { b e s t }$ 和 $G _ { b e s t }$ 如前定义；randO是介于(0.1)之间的随机数； $X _ { i }$ 是粒子的当前位置。 $^ { c 1 }$ 和 $c 2$ 是学习因子，通常取 $c 1 = c 2 = 2$ ；在每一维，粒子都有一个最大限制速度 $V _ { \mathrm { m a x } }$ ，如果某一维的速度超过设定的 $V _ { \mathrm { m a x } }$ ，那么这一维的速度就被限定为 $V _ { \mathrm { m a x } }$ （ $V _ { \mathrm { m a x } } > 0 \AA \AA$ ）。

# 2.2模拟退火算法

模拟退火算法（SA）是一种随机全局搜索优化算法，它是基于统计热力学来模拟退火行为过程[14]。可以将退火过程中系统熵值类比为目标函数值F，来模拟这个退火系统的算法。1983年，Kirkpatrick等提出模拟退火算法，并将其应用于组合优化问题的求解。模拟退火算法是一种可以有效避免陷入局部极小并最终趋于全局最优的串行结构的优化算法。

算法遵循Metropolis 抽样稳定准则，即以概率接受新状态。假设在状态 $\mathbf { X } _ { \mathrm { o l d } }$ 时，系统受到某种扰动而使其状态变为 Xnew。与此相对应，系统的能量也从 $\mathrm { E ( x _ { \mathrm { 0 l d } } ) }$ 变成 $\mathrm { E } ( \mathrm { x } _ { \mathrm { n e w } } )$ ，系统由状态$\mathbf { X o l d }$ 变为状态 $\mathbf { X } \mathrm { { n e w } }$ 的接受概率p定义为

$$
p = \exp [ - ( E _ { j } \cdot E _ { i } ) / k _ { B } T ]
$$

模拟退火算法的实现流程如图1所示。

![](images/1e59c0d51432793d87d807eefd78c08d1aba8f3c315485e809aed1f994b6f321.jpg)  
图1 SA算法流程图

# 2.3HPSOSA混合优化支持向量回归参数

为了得到全局或者接近全局的最优解，本文提出了一种混合粒子群和模拟退火算法的混合优化算法(HPSOSA)，充分利用了模拟退火算法能避免局部最优解获得全局最优解及粒子群算法速度快容易执行的优势。HPSOSA算法容易实现，综合了粒子群和模拟退火算法两者的优点。

一般说来，当基于一个小而且适当的特征子集选择参数时，大多数的研究人员仍然遵循试验-误差的方式，首先，基于不同的参数集构建几个SVR模型，在验证集上进行测试，从而获得最优参数。然而，这个过程是耗时的，而且需要一些运气。除了适当的核函数类型外，参数的优化设置也可以提高SVR模型的准确度。而核函数类型会影响核参数，为了得到适当的SVR核函数和最优的SVR参数，两者应同时考虑。

本文采用 HPSOSA 算法同时优化核函数类型和核参数设置，建立基于HPSOSA优化的支持向量机回归模型，将改进的SVR-HPSOSA模型应用于中国广西柳州市柳江的日降雨径流预报中。

# 2.4染色体表示

表1概括出了需要优化的各种核函数类型、有效的核函数参数以及SVR参数。因此，将染色体设计成三部分组成。核函数类型（整数），内核参数以及SVR参数（实数）。表1显示出了具有 $\boldsymbol { d }$ 维染色体的表示，其中 $d$ 是不同数据集变化的特征数。染色体00,01,10,11表示核函数类型，这四个值分别表示系统将选择线性核函数，多项式核函数，高斯核函数和S型核函数。染色体 $\left\{ x _ { i , 1 } , x _ { i , 2 } \right\}$ 代表了内核参数的值，染色体 $\left\{ { { x } _ { i , 3 } } , { { x } _ { i , 4 } } \right\}$ 分别代表了惩罚参数及不敏感损失函数的值。

表1核函数类型、参数及支持向量回归参数表  

<html><body><table><tr><td>核类型</td><td colspan="2">核参数</td><td colspan="2">SVR参数</td><td>整型编码</td><td>实型参数编码</td></tr><tr><td>线性核</td><td>Y</td><td>-</td><td>C</td><td>ε</td><td>00</td><td>Xi,1,Xi,2,Xi</td></tr><tr><td>多项式核</td><td>d</td><td>d</td><td>C</td><td></td><td>01</td><td>Xi,1,Xi,2,Xi,3，Xi,4</td></tr><tr><td>高斯核</td><td>C</td><td>0</td><td>C</td><td>8</td><td>10</td><td>Xi,1,Xi,2,Xi3,Xi,</td></tr><tr><td>S曲线形核</td><td>α</td><td>β</td><td>C</td><td></td><td>11</td><td>Xi,1,Xi,2,Xi,3,Xi,4</td></tr></table></body></html>

说明： $\gamma , \mathrm { d } , \mathrm { t } , \mathrm { C } , \sigma , \beta$ 和α表示核函数参数变量

# 2.5 SVR-HPSOSA模型

图2说描述了支持向量回归优化算法SVR-HPSOSA的过程。本文提出的SVR-HPSOSA算法具体描述过程如下：

a)粒子的初始化及粒子群参数设置：生成SVR内核类型及0参数的初始粒子组合。设 $k = 0$ ，并随机初始化粒子群位置以及粒子群的速度 $\nu _ { i } ^ { 0 }$ 。

b)输入训练数据并根据式子(11)计算每个染色体的适应值。

c)评估所有粒子的适应价值，通过对适应值的简单比较确定 $G _ { b e s t }$ 和 $P _ { b e s t }$ 。适应函数被定义为对训练数据集采用MAPEcrossv-alidaton函数的5次迭代交叉验证，表示如下：

$$
M \mathbf { i n f } = M A P E _ { c r o s s \nu - a l i d a t i o n }
$$

$$
\sum _ { \substack { M A P E _ { c r o s s \nu - a l i d a t i o n } } } ^ { l } = \frac { \displaystyle \sum _ { i = 1 } ^ { l } \left| a _ { i } - p _ { i } \right| / a _ { i } } { l } \times 1 0 0 \%
$$

其中：‘是训练数据样本数； $a _ { i }$ 是实际值， $p _ { i }$ 是预测值。在本研究中，5次迭代交叉验证法提供了计算成本和有效参数估计值之间的最佳折衷，被用于在训练数据集上计算适应值。对每一个粒子，通过式(11)计算他的适应值。

d)执行粒子群算法。根据适应度评估结果更新全局和个体值。设置平均训练变化精度为全局值，验证精度为个体最佳值。

e)计算 $\Delta F i t n e s s = F i t n e s s ( s _ { i } ^ { k + 1 } ) - F i t n e s s ( s _ { i } ^ { k } )$ ，随机选择一个数$U \in [ 0 , 1 ]$ 。如果 $\Delta F i t n e s s > 0$ ，意味着适应度函数增加，新的位置发生变化。新位置 $s _ { i } ^ { k + 1 }$ 根据的如下原则设置： $\exp ( \frac { \Delta F i t n e s s } { T _ { i } } ) > U$ 有粒子的速度都已经确定，转向第f)步，否则，转向步b)，用相同的估计方法为尚未被接受的粒子生成新的速度。在我们研究的100个例子中，相同的粒子将迫使最后的速度被接受，同时考虑机器的执行时间，可以防止进入无休止的循环。对于可能的失败并没有发生在我们的研究和模拟过程中。

f)通过简单的适应度值比较，更新每个粒子的新位置，修改 $G _ { b e s t }$ 和 $P _ { b e s t }$ 的值。

g)当进化过程已经达到一个满意的状态（或者最大回归数已经达到），则继续执行步骤3，否则，调整惯性权重 $\omega$ ，以及模拟退火温度 $T _ { i + 1 } = k ^ { * } T _ { i }$ ，设置 $k { = } \mathbf { k } { + } 1$ ，并返回到步骤b)。

h)输出最好方案 $G _ { b e s t }$ 及其适应度值。取回停止迭代时的核函数类型及参数值。

i)基于选出的核函数类型和参数，在更大训练集上反复训练和构建支持向量回归。最后，利用训练好的SVR模型在测试集上进行测试。

![](images/c4686c77acae9f2528f2fcf5d827a32db4e81d4948bb9a2e0251ed13bfdaded7.jpg)  
图2HPSOSA优化SVR 流程图

# 3 应用实例及结果分析

实验采用改进的SVR-HPSOSA方法，运行环境配置：英特尔赛扬 $\mathrm { ~ M ~ } 1 . 8 6 \mathrm { G H z }$ 处理器，内存1.5GB，WindowsXP操作系统和Matlab开发环境。PSO参数设置如下：迭代次数为100；种群数量为100；最小惯性权重为0.1，最大惯性权重为0.9，学习率为2。初始温度为5000；终止温度为0.9，温度降低系数为0.001。

# 3.1实验数据

广西柳江属珠江水系，干流全长773.3公里，流域面积57173平方公里，跨黔、桂、湘三省30个县、市，天然落差1306米，平均比降 $1 . 6 8 \text{‰}$ ，年均流量1865立方米/秒，汛期为 4-9月。到了汛期就柳江河段而言，洪水发生较为频繁，从1988 年至今的近20年间，大洪水的发生较为频繁，灾害也很严重，发生超过100年一遇的特大洪水1次（“1996.7”），20至50年一遇的大洪水3次（ $^ { \omega } 1 9 8 8 . 8 ^ { \prime \prime }$ 、“1994.6”和“2004.7”洪水），10至20年一遇的较大洪水1次（“2000.6”洪水）。为此建立较为准确的汛期柳江径流预报模型，对于防灾减灾意义十分重要。本文建立模型的数据选取广西柳江老桥口的每天12时的流速（ $m ^ { 3 } / s$ ）数据进行应用实例分析，总数据为2008年1月1日至2010年9月30日期间共1004个数据点。将数据分为两部分，2008年1月1日到2010年3月31日期间的821个数据点用于模型训练，余下的183个样本（2010年4月1日到2010年9月30日为主要汛期）用于模型测试。

# 3.2输入变量

一般来说，降雨-径流涉及的因果变量关系包括降雨量、降雨前水位、水流蒸发、温度等。大多数研究应用降雨量和前期流量（或水位）作为输入变量。根据逐步回归方法，同时考虑前期降雨量和径流时间序列，更能与 $X _ { ( t + 1 ) }$ 相关，因此，选择这两个最佳的输入组合作为此模型的输入。由文献[15]，考虑将径流时间点 $t - 1 ( X _ { ( t - 1 ) } )$ 、 $t - 2 ( X _ { ( t - 2 ) } )$ 、 $t - 3 ( X _ { ( t - 3 ) } )$ 、 $t - 4 ( X _ { ( t - 4 ) } )$ 的值及降雨量时间点 $t - 1 ( R _ { ( t - 1 ) } )$ 的值作为模型的输入，通过逐步回归方法消除低影响因子并选择出最优影响力的因子。

# 3.3 SVR-HPSOSA模型训练

使用相同的预测因子，对SVR-HPSOSA模型预测结果与SVR模型结果进行比较。本研究进行了简单的参数设置，设置高斯核函数带宽 $\delta \mathrm { = } 0 . 7 5$ ，另外两个参数，正则常数C及损失函数的选择基于试验-误差法。具有测试最小均方误差平方根(RMSE)的参数被认为是最优的。得到了基于最好测试和预测结果（使RMSE最小）下的最优参数是（ $\mathrm { C } { = } 8$ ， $\scriptstyle \mathtt { \varepsilon } = 0 . 0 7$ ）。

# 3.4性能评价

在许多文献中有很多关于降雨-径流预报模型性能指标。本文使用以下的评价指标来衡量该模型的性能：均方根误差（RMSE），平均绝对百分比误差（MAPE）及效率系数（CE）。此外，由于降雨径流模型峰值点非常重要，本文使用式（12）来比较不同模型在捕捉径流时间序列的整个径流数据峰值的性能指标。

$$
C E _ { p e a k } = 1 - \frac { \displaystyle \sum _ { i = 1 } ^ { n } ( x _ { p i } - x _ { p i } ^ { * } ) ^ { 2 } } { \displaystyle \sum _ { i = 1 } ^ { n } ( x _ { p i } - \overline { { { x _ { p } } } } ) ^ { 2 } }
$$

（204号 $C E _ { p e a k }$ 是峰值的效率系数， $x _ { p i }$ ， $x _ { p i } ^ { * }$ ， $\overset { - } { x } _ { p }$ 和 $n$ 分别代表观测值、预测值和观测平均值，以及观测到的数据峰值个数。

性能评价指标（RMSE）和（MAPE）主要是从数值上评价模型的性能，其值越小说明模型的预测性能越好；性能指标（CE）主要是看模型能否对径流的趋势做出正确的判断，其值越大就说明模型能够较为准确把握径流未来趋势；性能指标公式(12)是洪水峰值趋势的判断指标，对于径流模型在实际应用中，最关心的就是能否较为准确预测灾害性洪水，即洪水峰值达到时刻和对洪水峰值趋势跟踪，本文把流速大于 $4 0 0 0 ~ ( ~ m ^ { 3 } \mathrm { / } s$ ）看做是洪峰值，其中(12)中的 $\boldsymbol { \eta }$ 就是在预测时间区间中大于4000$\mathrm { ~ ( ~ } m ^ { 3 } / s$ ）样本个数。

# 3.5结果分析

图3为2010年4月1日到9月30日，对小于4000的径流，SVR-HPSOSA和单纯SVR（高斯核）两种模型分别得到的预测值与观测值的比较。图4是2010年4月1日到9月30日，对大于4000的径流，分别使用单纯SVR（高斯核）和提出的SVRHPSOSA模型得到的预测峰值与观测峰值的比较。通过两图我们可以看到SVR-HPSOSA模型的结果比SVR模型更接近实际观察到的水位值。特别是，SVR-HPSOSA模型对径流峰值预测能产生更好的预测结果，而其他模型估计略高或略低。

![](images/4ab3ddcd7810794ec0f6996edeb0f5c1637fef7d2cad0d865bb0464d5f2e6b8f.jpg)  
图3小于4000 径流观测值与两种模型预测结果比较

![](images/4d3b95ea78e5054b369ff5b34e032517faf9b4936c2e877a322f65b1fb499b33.jpg)  
图4大于4000 径流观测值与两种模型预测结果比较

表2以图表的方式分别给出了使用纯SVR（高斯核）和SVR-HPSOSA两种模型的拟合精度、预测精度和模型效率三种性能指标对比。正如表2所示，对于训练数据，SVR模型的均方根误差为167.863；而SVR-HPSOSA模型，误差只为74.218。同样，对于测试数据，SVR模型的均方根误差为909.564；而对于SVR-HPSOSA模型，误差达到201.723。针对训练和测试数据的MAPE指标，SVR-HPSOSA模型也低于SVR模型。这些结果表明，观察和预测值之间的偏差是非常小的。此外，SVR-HPSOSA模型的CE效率系数是所有模型中最大的。这也意味着SVR-HPSOSA模型能够捕获到日径流的平均变化趋势。

实验结果表明，SVR-HPSOSA模型在径流预测上是非常有前途的，既有良好的拟合表现，也有有效的预测表现。体现了SVR-HPSOSA模型训练和测试结果的一致性。从RMSE、MAPE和CE三个性能指标的表现来看，对具有相同输入的径流预测，SVR-HPSOSA模型要优于SVR模型。

与其他模型相比，SVR-HPSOSA模型对峰值预测能力。峰值估计通常是在实际降雨-径流应用中防洪减灾计划最重要参考之一，被作为建模过程考查的关键。从表2可以看出，SVR-HPSOSA模型对极端径流数据有更好预测能力，大大超过了SVR模型。SVR-HPSOSA模型训练数据的 $C E _ { p e a k }$ 值为0.984，测试数据是0.977。显示出了对峰值数据较高的处理能力。因此，本文提出的模型适合用于建立柳江汛期径流SVR预测模型，而且预测精度高。

从表2可以进一步看出，径流模型核函数类型最佳的选择是Sigmoid曲线核函数，最优的核参数设置为： $\alpha$ 等于0.325,$\beta$ 为0.0264，SVR最优的参数设置： $c$ 为18.60， $\varepsilon$ 为0.1059。

表2 SVR和 SVR-HPSOSA模型径流预测结果比较  

<html><body><table><tr><td colspan="4">模拟数据(2008年1月1日-2009年3月31日)</td></tr><tr><td>模型</td><td>MAPE</td><td>RMSE</td><td>CE CEpeak</td></tr><tr><td>SVR</td><td>15.758%</td><td>167.863</td><td>0.987 0.929</td></tr><tr><td>SVR-</td><td>3.734%</td><td>74.218</td><td>0.997 0.984</td></tr><tr><td>HPSOSA</td><td></td><td>预测数据(2010年4月1日-2010年年9月30日)</td><td></td></tr><tr><td>模型</td><td>MAPE</td><td>RMSE CE</td><td>CEpeak</td></tr><tr><td>SVR</td><td>25.881%</td><td>909.564</td><td>0.822 0.482</td></tr><tr><td>SVR-</td><td></td><td></td><td></td></tr><tr><td>HPSOSA</td><td>5.284%</td><td>201.723 0.992</td><td>0.977</td></tr><tr><td></td><td>核函数类型和参数</td><td></td><td></td></tr><tr><td>α</td><td>β</td><td>C</td><td></td></tr><tr><td>Sigmoid</td><td>0.325</td><td>0.0264</td><td>18.60 0.1059</td></tr></table></body></html>

注：拟合模型中的径流峰值为48个样本，径流峰值为21个样本，径流值大于4000，为峰值

# 4 结束语

降雨-径流系统是最活跃的动态气象系统之一。本文的优势和关键在于融合PSO和SA各自的优势进化SVR核函数类型及参数，用以建立一种径流预报模型SVR-HPSOSA。在真实降雨-径流数据实验中，训练出了SVR模型合适的核函数类型和参数值，与纯粹SVR模型预测进行比较，SVR-HPSOSA模型预测显示出了相对高的精度。根据本文的研究结果，SVR-HPSOSA方法具有以下的特点：

a）SVR-HPSOSA算法能避免局部最优解，通过混合SA的接受准则和PSO随机接受原则，减少了局部搜索端点附近的震动偏离；根据新旧位置之间不同的适应度值，运用规则接受新位置，还是重新计算另一个可信位置。这使得模型可以跳出局部最优解，并减少局部搜索终点附近的震动偏离。这些特性提高了解决方案的质量和收敛速度。

b）SVR-HPSOSA算法具有运算速度快和能在全局方向搜索最优解的优点，通过结合PSO运行机制、并行处理干扰机制以及SA解决搜索路径的特点，可以快速找到一个好的解决方案。

c）根据本文的研究结果，我们可以得出以下结论：S曲线核函数的SVR模型可以作为实际径流预测应用中的一种手段，从实证结果的角度看，它能得到较好的预报精度，具有较高的预测质量。

d）采用Sigmoid曲线核函数时，支持向量机实现的是一种前向神经网络，但是由于使用SVR方法，网络隐含层节点数、连接权值都是在设计的过程中自动确定，而且SVR的理论决定了它最终求得的是全局最优值而不是局部最小值，也保证了它对于未知样本的良好泛化能力而不会出现过学习现象，以此可以解释Sigmoid曲线核函数的SVR模型最为适宜径流预测模型。可以推广在其它地区的径流预测上，同样可以被认为是水文研究系统管理中较强的径流预测工具。

# 参考文献：

[1]Wu Jiansheng,Liu Mingzhe,Jin Long.Ahybrid support vector regression approach for rainfall forecasting using particle swarm optimization and projection pursuit technology [J]. International Journal of Computational Intelligence and Applications,201o,9 (2): 87-104.   
[2]滕少华，樊继慧，陈潇等.SVM 多分类器协同挖掘局域气象数据[J]. 广西大学学报：自然科学版,2014,39(5):1131-1137.(Teng Shaohua,Fan Jihui,Chen Xiao,etal.Application of SVM-based multi-classifiers in miningcooperatively local area meteorological data[J]. Journal of Guangxi University: Natural Science Edition,2014,39 (5): 1131-1137.)   
[3]Wu Jiansheng.An effective hybrid semi-parametric regression strategy for rainfall forecasting combining linear and nonlinear regression [J]. International Journal of Applied Evolutionary Computation,2011,2(4): 50-   
[4]Talei A,Chua L H C,Quek C.A novel application of a neuro-fuzzy computational technique in event-based rainfall-runoff modeling [J]. Expert Systems with Applications,2010,37(12): 7456-7468.   
[5] 张成刚，宋佳智，姜静清，等．一种改进的降噪自编码神经网络不平衡 数据分类算法[J].计算机应用研究,2017,34(5):1329-1332.(Zhang Chenggang,Song Jiazhi,Jiang Jingqing,etal. Imbalanced data classification algorithm of improved de-noising auto-encoderneural network [J]. Application Research ofComputers,2017,34(5):1329-1332.)   
[6]Kisi O,Shiri J,Tombul M.Modeling rainfall-runoff processusing soft computing techniques [J]. Computers & Geosciences,2013,51(2):108-117.   
[7]Hong Weichang,Dong Yucheng, Zheng Feifeng,et al. Hybrid evolutionary algorithms inaSVR traffic flow forecasting model[J].AppliedMathematics & Computation,2011,217(15): 6733-6747.   
[8] 张淑娟，邓秀勤，刘波．基于粒子群优化的最小二乘支持向量机税收预 测模型研究 [J].计算机科学,2017,44(s1):119-122.(Zhang Shujuan, Deng Xiuqin, Liu Bo.Research on tax forecasting model based on PSO and least squares support vector machine [J]. Computer Science,2017,44 (s1): 119-122. )   
[9]Trelea IC.The particle swarm optimization algorithm: convergence analysis and parameter selection [J]. Information Processing Letters,2016,85 (6): 317-325.   
[10] Chakrapani B, Varadarajan V.Genetic algorithm based demand side management for smart grid [J].Wireless Personal Communications,2017, 93 (2): 481-502.   
[11]李学俊，徐佳，朱二周，等.任务调度算法中新的自适应惯性权重计算 方法[J].计算机研究与发展,2016,53(9):1990-1999.(LiXuejun,Xu Jia, Zhu Erzhou,etal.A novel computation method for adaptive inertia weight of task scheduling algorithm [J]. Journal of Computer Research and Development,2016,53 (9): 1990-1999.)   
[12] Ireneusz G.Discussion on semi-immune algorithm behaviour based on fractal analysis [J]. Soft Computing,2017,21 (14): 3945-3956.   
[13]Bermolen P,Ros .Supprt vectregessinforlinkloadprdiction[J]. Computer Networks,2009,53 (2): 191-201.   
[14]吴意乐，何庆．基于改进遗传模拟退火算法的WSN 路径优化算法[J] 计算机应用研究,2016,33(10):2959-2962.(Wu Yile,He Qing.WSN path optimization algorithm based on improved genetic simulated annealing algorithm [J].Application Research of Computers,2016,33(10):2959- 2962.)   
[15] Asadi S,Shahrabi J,Abbaszadeh P,et al.A new hybrid artificial neural networks for rainfal-runoff process modeling [J]. Neurocomputing,2013, 121 (18): 470-480.