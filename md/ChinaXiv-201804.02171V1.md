# 基于改进贝叶斯优化算法的CNN超参数优化方法

邓帅a,b

(北京工业大学a.北京未来网络科技高精尖创新中心;b.北京市物联网软件与系统工程技术研究中心，北京 100124)

摘 要：CNN框架中，如何对其模型的超参数进行自动化获取一直是一个重要问题。提出一种基于改进的贝叶斯优化算法的CNN超参数优化方法。该方法使用改进的汤普森采样方法作为采集函数，利用改进的马尔可夫链蒙特卡洛算法加速训练高斯代理模型。该方法可以在超参数空间不同的CNN框架下进行超参数优化。利用CIFAR-10、MRBI和SVHN 测试集对算法进行性能测试，实验结果表明，改进后的CNN超参数优化算法比同类超参数优化算法具有更好的性能。

关键词：贝叶斯优化；卷积神经网络；高斯过程；超参数优化 中图分类号：TP183 doi:10.3969/j.issn.1001-3695.2018.01.0021

# Hyper-parameter optimization of CNN based on improved Bayesian optimization algorithm

Deng Shuaia, b (a.BeijingAdvancedInnovationCenterforFutureInternetTechnologyb.BeijingEngineeringResearchCenterforITSoftware &Systems,Beijing University ofTechnology,Beijingl0o124,China)

Abstract:Inthe framework of convolutional neural network(CNN），how toobtain the hyper-parametersof itsmodel automaticallyisanimportantand pressingresearchtopic.I this paper,we proposedahyper-parameteroptimization methodof CNN based on improved Bayesian optimization algorithm.This method uses the improved Thompson sampling method as the acquisition function.The improved Markov Chain MonteCarloalgorithm isused toacelerate the Gausian surrogatemodel. The proposed method can be used to optimize hyper-parameters in frameworks ofCNN with diferent hyper-parameter space. Theperformanceofthe algorithm was testedbyusing thesetestingsets: CIFAR-10,MRBIandSVHN.The experimentalresults showthatthe improved hyper-parameter optimization algorithmofCNN hasbeter performance than the other algorithms. Key words: Bayesian optimization; convolutional neural networks; Gausian process hyper-arameter optimization

# 0 引言

由于任何一个CNN模型都无法对所有数据集进行最佳泛化，因此在将CNN应用于新数据集之前，必须先选择一组适当的超参数。CNN的超参数包括层数，每层隐藏单元的数量，层的激活函数，层的内核大小，网络内这些层的配置等。为新数据集选择新的模型可能是一个耗时且繁琐的任务。被调整的超参数的数量以及每个新的超参数集合的评估时间使得它们在CNN模型中的优化尤其困难。超参数对不同CNN架构的影响的研究已经显示出复杂的关系，其中在简单CNN网络中提供巨大性能改进的超参数在更复杂的体系结构中并不具有相同的效果[I]。这些研究还表明，一个数据集上的结果可能不会转移到具有不同图像属性、先验概率分布、类别数量或训练示例数量的另一个数据集。由于没有明确的公式来选择一组正确的超参数，所以它们的选择通常取决于先前的经验和实验性错误的组合。由于CNN 算法计算成本高，在传统的平台上可能需要数天时间来进行训练，所以重复的反复实验既是低效的，也不是彻底的。

针对这种未知黑盒函数的优化，贝叶斯优化[2]提供了一个有效的方法，并且已经被证明在许多具有挑战性的优化基准函数上优于其他的最先进的全局优化算法。对于连续函数，通常假定未知函数是从高斯过程（GP）采样的，并且在观察时保持该函数的后验分布。为了选择下一个实验的超参数，可以优化当前最好的结果或者高斯过程置信区间(UCB)的期望增量(EI)[3,4]。Bergstra 等人[5]提出的 TPE（Tree-structured Parzen EstimatorApproach）算法和Snoek等人[提出的GPEIMCMC算法已经证明EI和UCB在许多黑盒函数的全局最优化的函数评估中是有效的。然而CNN 超参数优化具有与其他黑盒优化问题相区别的特征。首先每一次对CNN 超参数的评估可能需要一个可变的时间量，不清楚EI和UCB是否适用于CNN的超参数优化的函数评估；并且不确定这些优化算法得到的超参数对于具有不同数据模式或结构的域的CNN框架是否最优。

本文基于CNN 框架和已有贝叶斯优化算法，提出一种改进的贝叶斯优化算法对CNN 超参数进行优化。该方法利用高斯过程对超参数进行建模，利用改进的马尔可夫链蒙特卡洛（improvedMarkovChainMonteCarlo,IMCMC）算法加速训练高斯过程模型的训练，即计算高斯代理模型的超参数（长度尺度和协方差振幅等)。并使用改进的汤普森采样（improvedthompsonsampling,ITS）方法作为采集函数获得下一个采样点并计算loss值，然后合并到历史观测集中。这个过程迭代直到获得一组性能良好的超参数。该方法可以在超参数空间不同的CNN框架下进行超参数优化。利用CIFAR-10、MRBI和SVHN测试集对算法进行性能测试，说明了本文提出的方法获得的超参数比TPE和GPEIMCMC等同类的优化算法得到的超参数性能更好，更稳定。

# 1 贝叶斯优化算法介绍

对于超参数的优化，可以将这种优化看做是反映泛化性能的未知黑盒函数的优化，并调用针对这些问题开发的算法。这些优化问题与作为训练过程一部分经常遇到低层次目标是不同的：这里函数评估（求值目标函数调用一次）代价很大，因为它们涉及到主要的机器学习算法的完成。在这种函数求值代价大的情况下，希望花费计算时间来更好的选择在哪里寻找最佳参数。在贝叶斯优化中，感兴趣的是在一些有界集合∧上找到函数 $f \left( \lambda \right)$ 的最小值，本文将把它作为 $\mathbb { R }$ 的一个子集。使得贝叶斯优化不同于其他程序的是它为 $f \left( \lambda \right)$ 构造一个概率模型，然后利用这个模型来决定在哪里去评估函数，同时整合不确定性。基本的思路是使用 $f \left( \lambda \right)$ 以前评估中可用的所有信息来学习目标函数的形态，而不是简单地依靠局部梯度和Hessian 近似。这可以实现通过较少的评估就可以找到复杂非凸函数的最小值，代价是执行更多的计算以确定下一个采样点。因此分为了两个步骤：a）选择一个先验函数来表达关于被优化函数的假设，本文使用的高斯过程，因为其具有灵活易处理的特性；b）选择一个采集函数，用来从后验模型构造一个效用函数，来确定下一个采样点。

将要优化的CNN的超参数看做是多维空间的点。超参数的贝叶斯优化通过在超参数 $\lambda \in \Lambda$ 的空间中对损失函数 $f \left( \lambda \right)$ 进行一个高斯先验建模来执行。通过验证集 $X _ { V }$ 可以观察到这种损失函数的一些噪声， $f \left( \lambda \right)$ 表示为

$$
L { \left( m _ { \lambda } , X _ { V } \right) } = \frac 1 { \left| X _ { V } \right| } \sum _ { \left( x _ { i } , y _ { i } \right) \in X _ { V } } l { \left( m _ { \lambda } \left( x _ { i } \right) , y _ { i } \right) }
$$

$$
f \left( \lambda \right) = L \left( m _ { \lambda } , X _ { V } \right) + \varepsilon
$$

其中： $m _ { \lambda }$ 是通过在给定训练数据集 $X _ { T }$ 上运行具有超参数 $\lambda$ 的卷积神经网络A 而获得的模型参数， $l \left( \cdot , y \right)$ 是目标损失函数。真实的 $f \left( \lambda \right)$ 是未知的，只能通过在验证数据集上计算观测噪声

来量化。

# 2 改进的贝叶斯优化算法

# 2.1高斯过程

对于建模损失函数，高斯过程(GP)一直被认为是一种方便且强大的模型优化算法。在这里将采用 $f : \Lambda \to \mathbb { R }$ 的形式。GP 由下列性质定义：任意有限的 $\mathrm { ~  ~ N ~ }$ 个点 $\left\{ \lambda _ { n } \in \Lambda \right\} _ { n = 1 } ^ { N }$ 在 $\mathbb { R } ^ { N }$ 上引起多变量高斯分布。这些点中的第 $\mathbf { n }$ 个被认为是函数值 $f { \big ( } \lambda _ { n } { \big ) }$ ，高斯分布的良好的边缘化特征使本文能够以闭合的形式计算边界和条件。所得到的函数分布的性质完全由均值函数 $\mu : \Lambda \to { \mathbb { R } }$ ，$\mu ( \lambda ) = E \big [ f ( \lambda ) \big ]$ 和协方差函数（核函数） $k : \Lambda \times \Lambda \to \mathbb { R }$ ，$k \big ( \lambda , \lambda ^ { \prime } \big ) = E \Big [ \big ( f \big ( \lambda \big ) - \mu \big ( \lambda \big ) \big ) \big ( f \big ( \lambda ^ { \prime } \big ) - \mu \big ( \lambda ^ { \prime } \big ) \big ) \Big ]$ 决定[7]。假设在输入集$G = \left\{ \lambda _ { 1 } , . . . , \lambda _ { t } \right\}$ 和观测集的输出 $y = \left\{ L \left( h _ { \lambda _ { i } } , X _ { V } \right) \right\} _ { i = 1 } ^ { t }$ 上调节 $G P \big ( \mu , k \big )$ ：其中 $y _ { n } = f { \bigl ( } \lambda _ { n } { \bigr ) } + \varepsilon$ 带有一个独立同分布的高斯噪声$\varepsilon \sim \mathcal N \left( 0 , \sigma _ { n } ^ { 2 } \right)$ 。测试点 $\lambda _ { * }$ 处的预测分布表示为

$$
\hat { f } _ { * } = k _ { * } ^ { T } \left( K + \sigma _ { n } ^ { 2 } I \right) ^ { - 1 } y
$$

$$
V \left[ f _ { \ast } \right] = k \left( \lambda _ { \ast } , \lambda _ { \ast } \right) - k _ { \ast } ^ { T } \left( K + \sigma _ { n } ^ { 2 } I \right) ^ { - 1 } k \ast
$$

其中： $k _ { * } = \left[ k \left( \lambda _ { 1 } , \lambda _ { * } \right) , . . . , k \left( \lambda _ { N } , \lambda _ { * } \right) \right] ^ { T }$ ， $\kappa$ 是一个半正定矩阵（204号 $\big [ k \big ( \lambda , \lambda ^ { \prime } \big ) \big ] _ { \forall \left( \lambda , \lambda ^ { \prime } \right) \in \left( G \times G \right) }$ 。在每一次实验t中，GP以全部的历史观测点值对集合 $\mathcal { H } = \left\{ \lambda _ { i } , L \Big ( h _ { \lambda _ { i } } , X _ { V } \Big ) \right\} _ { \mathrm { i } = 1 } ^ { t - 1 }$ 为条件评估 $f { \left( \lambda _ { t } \right) }$ 。然后在利用平衡开发和勘探的采集函数的基础上，使用预测的后验均值和方差来选择下一组超参数。因为GP需要计算协方差矩阵的逆，因此它的计算复杂度为 ${ \mathrm { O } } ( { \mathrm { n } } ^ { 3 } )$ 0

# 2.2对GP模型训练的优化

初始化GP 时，采用一个零均值函数和一个Matér5/2协方差函数[7]。Matérn5/2kernel表示为

$$
K _ { M _ { 5 2 } } ( \lambda , \lambda ^ { \prime } ) = \theta _ { 0 } \left( ( 1 + \sqrt { 5 r ^ { 2 } ( \lambda , \lambda ^ { \prime } ) } + \frac { 5 } { 3 } r ^ { 2 } ( \lambda , \lambda ^ { \prime } ) \right) e x p \left\{ - \sqrt { 5 r ^ { 2 } ( \lambda , \lambda ^ { \prime } ) } \right\}
$$

其中 $r ^ { 2 } \left( \lambda , \lambda ^ { \prime } \right) = \sum _ { d = 1 } ^ { D } \theta _ { d } \left( \lambda _ { d } - \lambda _ { d } ^ { \prime } \right) ^ { 2 }$ ， $\theta _ { d }$ 为长度尺度， $\theta _ { 0 }$ 为协方差振幅。与通常使用的平方指数内核相比，这个协方差函数产生二阶可微的样本函数，放宽了对后验概率密度函数平滑度的假设。本文介绍两种常用的训练GP超参数的方法，分别是最大化似然方法(maximumlikelihood，ML)和MCMC方法，并对其中的MCMC方法进行优化。

# 2.2.1MaximumLikelihood 方法

一旦获得一个新点，在这一点上评估确切的后验概率密度函数并更新GP。在GP每次更新之后，通过最大化边际似然(marginallikelihood)来优化超参数(长度尺度 $\theta _ { d }$ 和协方差振幅$\theta _ { 0 }$ )。log marginallikelihood可以写成如下形式：

$$
L = \log p \left( y \Big | \lambda , \theta \right) = - \frac { 1 } { 2 } y ^ { T } \left( K + \sigma _ { n } ^ { 2 } I \right) ^ { - 1 } y - \frac { 1 } { 2 } \log \left| K + \sigma _ { n } ^ { 2 } I \right| - \frac { n } { 2 } \log 2 \pi \left( K + \sigma _ { n } ^ { 2 } I \right) .
$$

训练目标为最大化针对训练样本的对数边际似然值，得到对应的超参数。并对超参数进行完全贝叶斯处理（仅由8总结），并且求解边际似然函数的时候加入了nugget term[8,协方差 $K$ 应该替换为

$$
K _ { \nu } = \left( \left( 1 - \nu \right) r \left( \lambda _ { i } - \lambda _ { j } \right) + \nu \delta _ { i , j } \right) _ { i , j }
$$

其中：nuggetterm可以有效避免奇异解问题，使相关矩阵的条件数量适中，让最大似然估计更可靠。其计算复杂度为 ${ \mathrm { O } } ( { \mathrm { n } } ^ { 3 } )$ 。

# 2.2.2改进的MCMC方法

使用贝叶斯定理，可以得到模型参数的非标准化后验概率密度：

$$
p \big ( \theta \big | y \big ) \propto p \big ( y | \theta \big ) p \big ( \theta \big )
$$

其中 $p ( \theta )$ 表示GP 模型参数的先验分布。

MetropolisHasting（MH）通常用于从平稳分布生成样本的马尔可夫链[]。假设马尔可夫链中的第 $\mathfrak { n }$ 个样本为 $\theta _ { n }$ ，则其原生形式的 MH 首先从提议分布(proposal distribution) $q \big ( \theta \big | \theta _ { n } \big )$ 中提取一个随机候选并接受候选，其接受概率为：

$$
\rho \left( \theta _ { n } , \theta \right) = \operatorname* { m i n } \left( 1 , \frac { q \left( \theta _ { n } \big | \theta \right) p \left( \theta , y \right) } { q \left( \theta \big | \theta _ { n } \right) p \left( \theta _ { n } \big | y \right) } \right)
$$

这意味着在每个建议的样本上都必须对代价高的后验概率密度函数式(8)上进行探测-即要运行的仿真模型。因为获得像后验概率密度函数这么精确的提议 $q \big ( \theta \big | \theta _ { n } \big )$ 是非常困难的，所以接受率通常很低，这导致了“拒绝不想要的提议点"花费了太多计算量。

为了提高MH的接受率,本文使用评估更快的GP代理来修改常用的提议分布，例如以 $\theta$ 为中心，协方差为 $\Sigma _ { p } = \sigma _ { p } ^ { 2 } I$ 的高斯分布。候选样本 $\theta$ 是从建议分布中抽取的。不使用公式（9)直接测试这个候选点的接受程度，而是用概率 $\rho _ { A }$ 来测试这个候选点对GP代理 $\boldsymbol { p } ^ { * } ( \boldsymbol { \theta } , y )$ 的接受程度：

$$
\rho _ { A } ( \theta _ { n } , \theta ) = \operatorname* { m i n } ( 1 , \frac { q ( \theta _ { n } | \theta ) p ^ { * } ( \theta | y ) } { q ( \theta | \theta _ { n }  ) p ^ { * } ( \theta _ { n } | y ) } )
$$

与式(9)相比，降低了很多计算成本。直观地说，通过过滤

掉被精确概率密度函数拒绝的高概率的候选点来修改提议分布。只有被GPsurrogate接受的候选点才会被接受评估，其概率为：

$$
\rho _ { E } ( \theta _ { n } , \theta ) = \operatorname* { m i n } ( 1 , \frac { p ( \theta | \boldsymbol { y } ) p ^ { * } ( \theta _ { n } | \boldsymbol { y } ) ) } { p ( \theta _ { n } | \boldsymbol { y } ) p ^ { * } ( \theta | \boldsymbol { y } ) } )
$$

通过这种方式提高了接受率，避免了以高概率被拒绝的提议，从而避免了不必要的模型拟合过程，其计算复杂度为${ \mathrm { O } } ( { \mathrm { n } } ^ { 2 } ) { \mathrm { + O } } ( { \mathrm { n } } )$ 。这是在不牺牲采样精度的情况下实现的，因为最终的马尔可夫链是通过精确的后验概率密度函数生成的。由于篇幅有限，参考文献[14用近似的方法详细讨论马尔可夫链的遍历性、收敛性和计算复杂度。

因为采用Maximumlikelihood方法计算GP超参数的时候，需要进行求导等大量运算并且还可能在求解过程中陷入局部极值，因此本文采用改进的MCMC方法，该方法不仅使GP模型训练更快，而且在拟合模型的过程中不会出现局部最优解。两种方法的性能比较在下文实验部分给出。

# 2.3采集函数

在基于模型的优化过程中，在每一次迭代t中，一个采样函数用于取样下一个点来评估。这个采集函数使用观察模型函数 $f \left( \lambda \right)$ ，并给每一组超参数一个量化值 $a \big ( \lambda \big | f ( \cdot ) \big )$ 来平衡对新采样点的开发与勘探，以最大限度地找到全局最优解。而且本文的观测结果是 $\left\{ \lambda _ { n } , y _ { n } \right\} _ { n = 1 } ^ { N }$ ,其中 $y _ { n } \sim N \bigl ( f \bigl ( \lambda _ { n } \bigr ) , \nu \bigr )$ 和 $\nu$ 是引入函数观测的噪声方差。用 $a : \Lambda \to R ^ { + }$ 表示的采集函数通过代理优化来确定下一步应评估4中的哪个点 $\lambda _ { n e s t } = \arg m a x _ { \lambda } a \big ( \lambda \big | f \big ( \cdot \big ) \big )$ ，其中提出了几个不同的函数。一般来说，这些采集功能取决于先前的观察结果以及GP 超参数;把这个依赖表示为 $a \big ( \lambda ; \{ \lambda _ { n } , y _ { n } \} , \theta \big )$ 在高斯过程之前，这些函数完全依赖于模型的预测均值函数$\mu ( \lambda ; \{ \lambda _ { n } , y _ { n } \} , \theta )$ 和预测方差函数 $\sigma \big ( \lambda ; \{ \lambda _ { n } , y _ { n } \} , \theta \big )$ 。在这个过程中，将 $\lambda _ { b e s t } = \arg m i n _ { \lambda _ { n } } f \big ( \lambda _ { n } \big )$ 表示为最佳当前值。

# 2.3.1常用的采集函数

a)GPupperconfidencebound(GP-UCB).通过寻找最大化GP的置信区间的点来完成的[7]:

$$
\hat { \lambda } = a r g \operatorname* { m a x } _ { \lambda } \{ \mu ( \lambda ) + \beta ^ { \smash { \sum _ { \beta = 0 } ^ { \lfloor \chi  } } } \sigma ( \lambda ) \}
$$

其中 $\mu ( \lambda )$ 和 $\sigma ( \lambda )$ 由 Sherman-Morrison-Woodbury 公式[7]评估。参数 $\beta$ 使在样本空间的开发和探索保持平衡。式(12)使用BOBYQA(bound optimization by quadratic approximation)进行优化[11]。

b)Expectedimprovement。可以选择在当前最好的情况下最大化期望增量(EI)。这在高斯过程下也有闭合形式：

$$
a _ { E I } \left( \lambda \vert \mu , \sigma \right) = E \biggl [ \operatorname* { m a x } \left( 0 , f \left( \lambda \right) - f \left( \lambda _ { b e s t } \right) \right) \biggr ]
$$

其中 $\lambda _ { b e s t }$ 是目前为止基于观测集的最优解。由于其简单的形式，EI使用标准的black-box优化算法进行优化[6]。

在本文中，本文重点讨论EI标准和本文提出的改进后的汤普森采集函数(Improved Thompson Sampling,ITS)，因为 GP-EI已被证明比GP-UCB 有更好的表现[6]，并且GP-EI不像GP-UCB，它不需要自己调整参数。在实验部分，本文直接比较了GP-EI、GP-ITS 以及GP-UCB 的性能。

# 2.3.2基于汤普森采样改进的采集函数

上面两种采集函数那样的探索性方法，在某些导致过度开发的情景下，这种对新观测点的采集往往是贪婪的[12]。虽然这种采集的特殊问题可以用类似GLASSES算法[15]的方式解决但这些都是难处理的。在本节中提出一种计算快速并且可以明确平衡勘探和开采的替代采集函数，是在汤普森抽样[13](Thompson sampling)基础上进行改进的一种方法。对于任何新提出的duel $[ \lambda , \lambda ^ { \prime } ]$ ，两个可能的结果 $\{ 0 , 1 \}$ 对应于或 $\lambda ^ { \prime }$ 赢得了竞争(duel)[13]，两个结果的概率由 $\pi _ { \tilde { f } }$ 给出。它遵循两步决策的竞争：

a)选择 $\lambda$ ：首先，使用一个连续的汤普森采样[121从模型生成一个样本 $\tilde { \boldsymbol { f } }$ ，并通过对 $\Lambda$ 进行积分来计算关联的soft-Copland分数。新duel的第一个元素 $\lambda _ { n e s t }$ 选择为

$$
\lambda _ { n e x t } = a r g \mathop { m a x } _ { \lambda \in \Lambda } \int _ { \Lambda } \pi _ { \tilde { f } } \left( \left[ \lambda , \lambda ^ { \prime } \right] ; \mathcal { H } _ { j } \right) d \lambda ^ { \prime }
$$

在 Copeland score 中的 $V o l \big ( \Lambda \big ) ^ { - 1 }$ 项在这里已经减小了，因为它不改变最优位置。这一步骤的目标是选择孔多塞胜者(CondorceWinner)时平衡勘探(exploration)和开发(exploitation),这与汤普森抽样的做法是一样的：它可能选择一个接近当前Condorcet获胜者的点，但是该原则也允许探索其他地点，将决策建立在一个随机样本 $\tilde { \boldsymbol { f } }$ 上。而且，收集的评估值越多，对CondorceWinner的选择就越贪婪。

b)选择 $\lambda ^ { \prime }$ ：在给定 $\lambda _ { n e s t }$ 基础上，这个duel 的第二个元素被选为在 $\lambda _ { n e s t }$ 的方向上使 $\sigma ( f _ { * } )$ 的方差最大化的位置。具体地说，$\lambda _ { n e s t }$ 被选择为

$$
\lambda _ { n e s t } ^ { ' } = a r g \operatorname* { m a x } _ { \lambda _ { * } ^ { ' } \in \Lambda } V \Bigg [ \sigma \big ( f _ { * } \big ) \Big | \bigg [ \lambda _ { * } , \lambda _ { * } ^ { ' } \bigg ] , \mathcal { H } _ { j } , \lambda _ { * } = \lambda _ { n e s t } \Bigg ]
$$

这一步骤纯粹是在 $\lambda _ { n e w }$ 的方向上进行探索，其目标是找到信息丰富的比较，以便在前面步骤中确定的当前好位置上运行。

总之,改进后的汤普森取样法选择下一个duel为

$$
\arg \operatorname* { m a x } _ { [ \lambda , \lambda ^ { \prime } ] } \alpha _ { I T S } ( [ \lambda , \lambda ^ { \prime } ]  \mathcal { H } _ { j } ) = [ \lambda _ { n e s t } , \lambda _ { n e s t } ^ { \prime } ]
$$

其中: $\lambda _ { n e s t }$ 和 $\lambda _ { n e s t } ^ { \prime }$ 是在上面定义的。该策略结合了一个点的选取和一个点的高概率，以及一个点的竞争结果相对于前一个点来说是不确定的。由于该采集函数可以平衡exploration 和exploitation，因此在超参数寻优过程中基本不会陷入局部极值。

# 2.4改进的贝叶斯优化算法的实现

本文中使用拉丁超立方体抽样(Latinhypercube samplingHS）方法初始化观测集。经过改进的算法实现如下：

算法1：基于改进的贝叶斯算法的CNN 超参数优化算法(GPITSIMCMC)   
Input: $X _ { T }$ and $X _ { V }$ ，some training and validation datasets,   
$N$ the number of initial points ，A the CNN algorithm，and   
$L$ the loss function   
Output: Return the best model of CNN   
$\begin{array} { r } { \mathbf { 1 } \colon \mathcal { H } _ { 0 }  \{ [ \lambda _ { j } , \lambda _ { j } ^ { ' } ] , L \Big ( h _ { \lambda _ { j } } , X _ { V } \Big ) \} _ { j = 1 } ^ { N } b y \ L H S } \end{array}$   
2:for $t \in { 1 , . . . , T }$ do   
3: $f ( \lambda ) \gets G P \big ( \mathcal { H } _ { t - 1 } \big )$ and learn $\pi _ { f , t - 1 } ( \lambda )$ //Fit GP   
4: Compute the acquisition for duels $\alpha$ ：   
5: Next duel $\cdot \left[ \lambda _ { t } , \lambda _ { t } ^ { \prime } \right] = \arg \operatorname* { m a x } \alpha \big ( \left[ \lambda , \lambda ^ { \prime } \right] \big )$   
5: $m _ { \lambda _ { t } } \gets A \Big ( \big [ \lambda _ { t } , \lambda _ { t } ^ { \prime } \big ] , X _ { T } \Big ) \quad / / \top \mathsf { r a i n ~ m o d e l }$   
6: （204号 $l _ { \lambda _ { t } } \gets L \Big ( m _ { \lambda _ { t } } , X _ { V } \Big )$ //Compute validation loss   
7: $\mathcal { H } _ { t }  \mathcal { H } _ { t - 1 } \cup \{ ( [ \lambda _ { t } , \lambda _ { t } ^ { \prime } ] , l _ { \lambda _ { t } } ) \}$ //Update observations   
8:end for   
9:return $\begin{array} { r } { \operatorname * { a r g m i n } _ { m \in \mathcal { H } _ { T } } L \big ( m , X _ { V } \big ) } \end{array}$

# 3 实证分析

在本节中，通过实证分析了本文提出的算法，并对现在常用的超参数优化进行比较。本文进行比较的算法主要有Bergstra等人提出的TPE 算法和JasperSnoek等人提出的GPEIMCMC算法。首先使用Branin-Hoo函数简单测试本文算法的性能;然后使用 CIFAR-10、MRBI(rotated MNISTwith background images)和SVHN（StreetViewHouse Numbers Dataset）数据集测试本文算法对CNN超参数的优化性能，并与同类优化算法比较得出结论。

# 3.1实验环境

众所周知，神经网络和深度学习方法需要仔细调整大量超参数。多层卷积神经网络就是这样一个模型的一个例子，如Saxe等人所证明的那样，对体系结构和超参数进行彻底的探索是非常有益、有必要的。本文研究了一个与 Snoek 和Domhan使用的 cuda-convnet 相同架构的卷积神经网络[16]。Snoek 和Domhan使用的超参数的搜索空间不同，本文使用类似于Snoek等人的搜索空间。其中6个超参数用于随机梯度下降，两个超参数用于响应归一化层(response normalization layers)，搜索空间如表1所示。Snoek等人的两个超参数被排除在本文的实验之外：由于Caffe框架的限制，响应归一化层的宽度被排除；由于与动态资源分配不相容，所以epochs数目被排除。

表1三层卷积神经网络的超参数及其范围  

<html><body><table><tr><td>Hyper-parameter</td><td>Scale</td><td>Min</td><td>Max</td></tr><tr><td>LearningParameters</td><td></td><td></td><td></td></tr><tr><td>Initial Learning Rate</td><td>log</td><td>5*10-5</td><td>5</td></tr><tr><td>Convl l2 Penalty</td><td>log</td><td>5*10-5</td><td>5</td></tr><tr><td>Conv2 l2 Penalty</td><td>log</td><td>5*10-5</td><td>5</td></tr><tr><td>Conv3l2 Penalty</td><td>log</td><td>5*10-5</td><td>5</td></tr><tr><td>FC4 l2 Penalty</td><td>log</td><td>5*10-5</td><td>5</td></tr><tr><td>Learning Rate Reductions</td><td>integer</td><td>0</td><td>3</td></tr><tr><td>Local ResponseNormalization</td><td></td><td></td><td></td></tr><tr><td>Scale</td><td>log</td><td>5*10-6</td><td>5</td></tr><tr><td>Power</td><td>linear</td><td>1*10-2</td><td>3</td></tr></table></body></html>

# 3.2实验结果

# 3.2.1Branin-Hoo 函数

利用Branin-Hoo 函数测试比较 MML(maximum marginallikelihood，MML)方法和改进后的IMCMC(improvedMCMC)方法训练GP的性能，同时比较标准的方法和 TPE[5]方法的性能（按函数计算的次数表述)，如图1所示。Branin-Hoo函数定义在 $0 \leq x _ { 1 } \leq 1 5 , 0 \leq x _ { 2 } \leq 1 5 , x \in \mathbb { R }$ 上，是贝叶斯优化技术的共同标准[6]。在 Branin-Hoo 中，GP-EI 和 GP-ITS 明显优于 TPE 和 GP-UCB，IMCMC方法优于MML。

![](images/594c6d4d39d3391e6f1a70235b47aabc445dac7baf68e76aad95214226645801.jpg)  
图1在Branin-Hoo 函数上比较GPITSIMCMC 和一些标准方法

# 3.2.2 AlexKrizhevsky's CNN框架

本文使用三个图像分类数据集：CIFAR-10、MRBI（TheMNISTRotated Background Images Dataset）和 SVHN（The StreetViewHouseNumbersDataset)。CIFAR-10 和 SVHN包含 $3 2 \mathrm { x } 3 2$ 的 RGB 图像，而 MRBI包含 $2 8 \mathrm { x } 2 8$ 的灰度图像。每个数据集分为训练、验证和测试集：CIFAR-10有40000，10000和10000个实例；SVHN分别有600000，6000，26000；MRBI分别有10000，2000，50000个样本用于训练、验证和测试。对所有数据集进行图像归一化和均值削减预处理。本文为CIFAR-10和MRBI设置max_iter为300（对于CIFAR，这对应于训练集上的 75个epochs)，而对于SVHN，由于其较大的训练集，最大迭代maxiter被设置为600。在以下的所有图表中，该算法使用ValidationError进行最优超参数的选取，使用TestError评估最优超参数的性能。

![](images/18e107eeb344573b34dc99c7b115b0ad6cd8d298afea7531ae81dd8e3fdd7653.jpg)

![](images/2a4d6e88aae72965615ae283b98a76757e08b22297f2087ee825dd90141e8c05.jpg)  
(b)MRBI测试误差结果图  
(c)SVHN测试误差结果图  
图2比较不同超参数优化算法在CIFAR-10、MRBI和SVHN数据集上的平均测试误差

本文使用GPITSIMCMC对CIFAR-10、MRBI和SVHN测试集上的CNN的8个超参数进行了优化，并在随机初始化运行中报告平均测试误差(Average Test error).并与使用TPE、GPEIMCMC方法以及人类专家[1o](HumanExpert)凭经验获得的最佳参数获得的平均结果进行对比。结果显示在图2中，从图（a）（b）中可以看出：在CIFAR-1O 测试集和MRBI测试集中，TPE 性能优于 GP EI MCMC 和 Human Expert，GP ITSIMCMC性能优于TPE；从图（c）中可以看出：在SVHN测试集中，GPEIMCMC 性能优于TPE 和Human Expert，GP ITSIMCMC性能优于GPEIMCMC。从总体上看，GPITSIMCMC找到的最佳参数比TPE方法和GPEIMCMC方法找到的超参数平均性能高出了 $1 \%$ 以上，比HumanExpert找到的超参数平均性能高出了 $3 \%$ 以上。

# 4 结束语

本文提出了一种基于改进的贝叶斯优化算法的卷积神经网络超参数优化算法。该方法利用高斯过程回归对超参数进行建模，把一种以改进的汤普森采样方法作为采集函数，并且使用改进的马尔可夫链蒙特卡洛算法(IMCMC)对GP超参数求解过程进行加速。该方法适用于各种不同卷积神经网络的超参数优化。实验结果表明该方法可以比目前其他常见的优化算法表现出更好的性能。下一步工作的重点在于将GPITSIMCMC方法进行并行化来提高卷积神经网络超参数优化算法的收敛速度。

# 参考文献：

[1]Breuel T M.The effects of hyperparameters on SGD training of neural networks [J].arXiv preprint arXiv:1508.02788,2015.   
[2]Mockus J.Bayesian approach to global optimization: theoryand applications [M].Springer Science & Business Media,2012.   
[3]Jones D R.A taxonomy of global optimization methods based on response surfaces [J].Journal of global optimization,20o1,21(4): 345-383.   
[4]Klein A,Falkner S,Bartels S,et al.Fast bayesian optimization of machine learning hyperparameters on large datasets [J].arXiv preprint arXiv:1605. 07079,2016.   
[5]J.Bergstra,R.Bardenet,Y.Bengio,and B.Kégl.Algorithms for HyperParameter Optimization [C]// Proc.of NIPS.2011.   
[6]Jasper Snoek,Hugo Larochelle,and Ryan P.Adams.Practical Bayesian optimization of machine learning algorithms [C]//Proc of NIPS.2012.   
[7]Rasmussen C E, Williams C K I. Gaussian processes for machine learning [M].Cambridge: MIT press,2006.   
[8]Pepelyshev A.The role of the nugget term in the Gaussian process method [M]/Advances in Model-Oriented Design and Analysis. Physica-Verlag HD, 2010: 149-156.   
[9]Kapli P,Lutteropp S,Zhang J,et al. Multi-rate Poisson tree processes for single-locus species delimitation under maximum likelihood and Markov chain Monte Carlo [J].Bioinformatics,2017,33 (11):1630-1638.   
[10] Krizhevsky A,Hinton G.Learning multiple layers of features from tiny images [EB/OL]. (2009-04-08).http://www.cs.toronto.edu/\~kriz/learningfeatures-2009-TR. pdf.   
[11] Powell M JD.Developments of NEWUOA for minimization without derivatives [J].IMA Journal of Numerical Analysis,2008,28 (4): 649-664.   
[12] Hernandez-Lobato JM,Hofman M W,Ghahramani Z. Predictive entropy search for efficient global optimization of black-box functions [C]// Advances in Neural Information Processing Systems.2014:918-926.   
[13] Wu H,Liu X.Double thompson sampling for dueling bandits [C]//Advances in Neural Information Processing Systems.2016: 649-657.   
[14] Christen JA,Fox C.Markov chain Monte Carlo using an approximation [J]. Journal of Computational and Graphical statistics,20o5,14(4): 795-810.   
[15] Gonzalez J, Osborne M,Lawrence N.GLASSES:Relieving the myopia of Bayesian optimisation [Cl//Artificial Intelligence and Statistics.2016: 790- 799.   
[16] Domhan T,Springenberg JT，Hutter F. Speeding up automatic hyperparameter optimization of deep neural networks by extrapolation of learning curves [C]//Prod of IJCAI. 2015: 3460-3468.