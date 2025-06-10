# 基于排序优先经验回放的竞争深度Q网络学习

周瑶瑶，李烨

(上海理工大学 光电信息与计算机工程学院，上海 200093)

摘要：为减少深度Q网络算法的训练时间，采用结合优先经验回放机制与竞争网络结构的DQN方法，针对 OpenAIGym平台CartPole和MountainCar两个经典控制问题进行研究，其中经验回放采用基于排序的机制，而竞争结构中采用深度神经网络。仿真结果表明，相比于常规DQN算法、基于竞争网络结构的DQN方法和基于优先经验回放的 DQN 方法，该方法具有更好的学习性能，训练时间最少。同时，详细分析了算法参数对于学习性能的影响，为实际运用该方法提供了有价值的参考。

关键词：强化学习；深度Q网络；竞争网络；排序优先经验回放 中图分类号：TP181 doi:10.19734/j.issn.1001-3695.2018.06.0513

Dueling deep Q network learning with rank-based prioritized experience replay

Zhou Yaoyao, Li Ye (SchoolofOptical-Electrical &ComputerEngineering,UniversityofShanghaiforScience&TechnologyShanghai 200093, China)

Abstract:Toreduce the training time fordeepQnetwork,thepaperresearchedontwoclassicalcontrolproblems,i.e.Cart Poleand Mountain Car on Open AI Gym,byaDQN method combined with prioritized experience replay scheme and the dueling architecture(dueling DQN-PR).The prioritized experience replay was rank-basedand a deep neural network was adopted in the dueling architecture.The simulation results showed that compared with regular DQN,DQN with dueling network and DQN with prioritized experience replay,dueling DQN-PR acquiredbeter learning performance with least trainingtime.Meanwhile,the impactsof parametersondueling DQN-PR were analyzed indetail,which provides valuable reference for the practical application.

Key words: reinforcement learning; deep Q network; dueling network; rank-based prioritized experience replay

# 0 引言

在强化学习中，智能体与环境交互，观测到环境对智能体动作的反馈后，不断调整行为，以提升自身性能。尽管强化学习有许多成功应用，但由于采样和计算复杂性等问题，局限于低维问题。随着深度学习的发展，深度神经网络可以将高维数据进行可靠的低维表示[I]，解决了强化学习的计算复杂性问题[2]。

文献[3]首度将强化学习与深度学习相结合，提出了DQN（deepQ-network）深度强化学习方法，试图直接通过图片、语音等原始传感器数据学习以获得好的控制策略；同时为了解决神经网络训练数据存在相关性、数据分布不断变化的问题，采用了随机经验回放策略。针对DQN算法可能造成过度估计的问题，文献[4]提出doubleDQN方法，对于动作的选择与评估采用不同的神经网络。文献[5]提出优先经验回放（prioritizedreplay）机制，优先回放对于学习环境帮助更大的经验，使智能体更快适应环境。鉴于一状态下的各种动作重要性有所不同，文献[6]提出竞争网络（duelingnetwork）结构，采用两条流分别估计状态价值和状态独立的动作优势，这样对于各状态不必评估每个动作选项的效果，同时也进一步改善了采用经验回放时的学习性能。

优先性的定义对于学习性能具有影响。当采用比例优先性定义时，由于回放经验的采样概率正比于经验的时序误差，时序误差越大的经验会有更大概率被回放，学习效果容易受时序误差离群值的不利影响，而基于排序的优先经验回放鲁棒性更强。本文采用优先经验回放的竞争深度 $\boldsymbol { Q }$ 网络针对两个经典控制问题进行研究，其中经验回放采用基于排序的机制，而竞争结构中采用深度神经网络，同时分析了算法参数对于该方法学习性能的影响。

# 1 深度Q网络

通常强化学习问题可转换为马尔可夫决策过程并使用Q-learning算法解决[7]。当智能体选择动作后，环境会相应给予反馈作为状态动作的回报。智能体不断学习优化一个可迭代计算的 $\boldsymbol { Q }$ 函数，目标是找到每个状态下的最优策略以最大化期望回报。 $\boldsymbol { Q }$ 值的更新如下：

$$
\mathrm { Q } ( \mathrm { S } _ { t } , \mathrm { A } _ { t } ) \gets \mathrm { Q } ( \mathrm { S } _ { t } , \mathrm { A } _ { t } ) + \mathrm { a } \big ( \mathrm { R } _ { { \mathrm { t } } + 1 } + \gamma m a x _ { a } \mathrm { Q } \big ( \mathrm { S } _ { t + 1 } , \mathrm { a } \big ) - \mathrm { Q } ( \mathrm { S } _ { t } , \mathrm { A } _ { t } \big )
$$

其中： $\mathbf { Q } ( \mathbf { S } _ { t } , \mathbf { A } _ { t } )$ 为智能体在状态 $\mathbf { S } _ { t }$ 下选择动作 $\mathbf { A } _ { t }$ 的期望回报值； $\mathrm { ~ \mathsf ~ { ~ R ~ } ~ } _ { { \mathrm { t } } + 1 }$ 为状态 $\mathbf { S } _ { \iota }$ 下选择动作 $\mathbf { A } _ { \mathfrak { r } }$ 的即时回报值； $m a x _ { a } \mathbf { Q } ( \mathbf { S } _ { t + 1 } , \mathbf { a } )$ 表示状态 $\mathbf { S } _ { t + 1 }$ 下选择各种动作的最大期望回报值；Y为折扣因子，反映了未来回报相对于即时回报的影响，其值越低表示影响越小； $\mathfrak { a }$ 为学习速率。

Q-learning算法使用 $\boldsymbol { \mathcal { Q } }$ 表格来记录每个状态下每个动作的 $\boldsymbol { Q }$ 值并反复更新。然而实际中可能因状态太多，无法使用表格保存，此时可使用价值函数近似。价值函数可以是线性函数，也可以是非线性函数比如神经网络，这种神经网络称

为 $\boldsymbol { Q }$ 网络。

如何从高维的传感数据如视频、语音等进行学习是强化学习长期存在的挑战[3]。以往基于强化学习的系统的性能严重依赖于人工设计的特征的质量，而深度学习为从原始传感数据提取高层特征提供了可能。因此，在强化学习中引入卷积神经网络、循环神经网络等深度学习结构成为一种趋势。

深度 $\boldsymbol { \mathcal { Q } }$ 网络将 $\mathbf { R } _ { \mathfrak { t } + 1 } + \gamma m a x _ { a } \mathbf { Q } ( \mathbf { S } _ { t + 1 } , \mathbf { a } )$ 作为目标 $\boldsymbol { Q }$ 值，并基于网络输出的 $\boldsymbol { Q }$ 值与目标 $\boldsymbol { \mathcal { Q } }$ 值之间的偏差定义损失函数 $\mathrm { ~ L ~ }$

$$
\mathrm { L } \big ( \mathrm { w } \big ) { = } \mathrm { E } [ \big ( \mathbf { R } _ { \mathrm { t + 1 } } + \gamma m a x _ { a } \mathrm { Q } ( \mathbf { S } _ { t + 1 } , \mathbf { a } ) - \mathbf { Q } ( \mathbf { S } _ { t } , \mathbf { A } _ { t } , \mathbf { w } ) \big ) ^ { 2 } ]
$$

其中： $\mathbf { S } _ { t + 1 }$ ，a表示状态 $\mathbf { S } _ { t }$ 采取动作 $\mathbf { A } _ { t }$ 后的下一状态和动作；$\mathrm { Q } ( \mathrm { S } _ { t } , \mathbf { A } _ { t } , \mathbf { w } )$ 表示 $\boldsymbol { Q }$ 网络的输出值。在计算上，可采用随机梯度下降更新深度 $\boldsymbol { Q }$ 网络的权值。

# 2 竞争网络结构

在强化学习中，需要对每个状态的价值进行估计，但对于许多状态，没有必要估计每一个动作的价值。竞争网络结构将状态价值的表示和状态下的动作优势分开来评估。状态一动作价值函数 $\boldsymbol { \mathrm { Q } } ^ { \pi } ( s , a )$ 表示在状态 $s$ 下由策略 $\pi$ 选择动作 $\mathbf { \Delta } _ { a }$ 时的期望回报值，状态价值 $\mathbf { V } ^ { \pi } \left( s \right)$ 表示状态 $s$ 的价值，是该状态下由策略 $\pi$ 产生的所有动作的价值的期望值，则二者的差值表示状态 $s$ 下选择动作 $a$ 的优势，定义为

$$
\mathbf { A } ^ { \pi } \left( s , a \right) = \mathbf { Q } ^ { \pi } \left( s , a \right) - \mathbf { V } ^ { \pi } \left( s \right)
$$

因而，竞争网络存在两条数据流，一条流输出状态价值$\mathbf { V } ( \mathbf { s } ; \mathbf { \boldsymbol { \theta } } , \mathbf { \boldsymbol { \beta } } )$ ，另一条流输出动作优势 $\mathbf { A } { \left( \mathbf { s } , \mathbf { a } ; \mathbf { \boldsymbol { \theta } } , \mathbf { \boldsymbol { a } } \right) }$ 。其中θ表示对输入层进行特征处理的网络神经元参数， $^ { \cdot } \mathrm { ~ } ^ { \cdot } \mathrm { ~ } ^ { \cdot } \mathrm { ~ } ^ { \cdot }$ 分别为两条流的参数。采用竞争网络结构的深度 $\boldsymbol { Q }$ 网络的输出为：

$$
\operatorname { Q } ( \mathrm { s } , \mathrm { a } ; \theta , \mathrm { a } , \beta ) = \operatorname { V } \left( \mathrm { s } ; \theta , \beta \right) + \operatorname { A } \left( \mathrm { s } , \mathrm { a } ; \theta , \alpha \right)
$$

由于网络直接输出 $\boldsymbol { Q }$ 值，无法知道状态价值 $V$ 和动作优势 $A$ ，因此强制动作优势估计在选中动作下的优势为0，修改 $\boldsymbol { Q }$ 值表示：

$$
\begin{array} { r } { \mathbf { Q } ( \mathrm { s } , \mathrm { a } ; \theta , \mathrm { \alpha } , \beta ) = \mathbf { V } \left( \mathrm { s } ; \theta , \beta \right) + \mathbf { A } \left( \mathrm { s } , \mathrm { a } ; \theta , \alpha \right) - \operatorname* { m a x } _ { a ^ { \prime } \in A } \mathbf { A } \left( \mathrm { s } , \mathrm { a } ^ { \prime } ; \theta , \alpha \right) } \end{array}
$$

实际应用竞争网络结构时， $\boldsymbol { Q }$ 值的计算中通常用动作优势的平均值来代替动作优势最大值的求解，保证性能的同时提高了优化的稳定性[6]。

# 3 优先经验回放机制

DQN算法使用的均匀随机采样不是最优策略。在学习过程中，有巨大回报的经验如成功的尝试或失败的教训等可能会一直保留在记忆中，频繁回放这些经验可使智能体意识到正确或不当行为带来的后果，因而不断纠正自身的行为。优先经验回放的关键是如何判断经验的重要性，一种方法是直接基于采用状态动作转换产生的时序误差来衡量[8.9]，而本文则采用基于排序的优先性机制，定义经验的优先性为

$$
p _ { t } = 1 / r a n k ( \mathfrak { t } )
$$

其中： $r a n k ( t )$ 为按时序误差（绝对值）从大到小排序的经验序号。

据此可定义采样经验 $t$ 的概率为

$$
\mathtt { p } ( t ) = { \frac { p _ { t } ^ { \alpha } } { \sum _ { n } { p _ { n } } ^ { \alpha } } }
$$

其中： $n$ 为回放经验池的大小， $\mathfrak { a }$ 控制优先性使用的程度，其取值范围为[0,1]，当 $\scriptstyle { \mathfrak { a } } = 0$ 时表示均匀采样。

由于高时序误差的经验频繁回放，某些状态的访问频率过高，导致经验缺乏多样性，使得网络的训练易于过拟合，因此可通过重要性采样权重 $\mathbf { w }$ 来纠正[10];

$$
\mathbf { w } _ { i } = 1 / \left( \frac { p _ { i } } { p _ { m i n } } \right) ^ { \beta }
$$

其中： $p _ { i }$ 表示采样经验 $i$ 的概率， $p _ { m i n }$ 表示最小采样概率，参数 $\beta$ 表示纠正的程度。 $\boldsymbol { Q }$ 网络的损失函数 $L$ 定义为

$$
\begin{array} { r } { \mathrm { L } = \sum w \big ( t \big ) \big ( y _ { t } - \mathrm { Q } ( \mathrm { S } _ { t - 1 } , \mathrm { A } _ { t - 1 } ; \theta , \alpha , \beta ) \big ) ^ { 2 } } \end{array}
$$

其中： $y _ { t }$ 表示在时刻 $\mathbf { \Phi } _ { t }$ 的目标 $\boldsymbol { Q }$ 值， $\mathrm { Q } ( \mathrm { S } _ { t - 1 } , \mathrm { A } _ { t - 1 } ; \theta , \alpha , \beta )$ 表示竞争 $\boldsymbol { \mathcal { Q } }$ 网络的输出 $\boldsymbol { Q }$ 值。

智能体选择动作采取&-贪婪策略。初始时智能体不熟悉环境，随机采取动作，之后随着经验的增加，为选择使期望回报值最大的动作，需要降低采取随机动作的概率，而更倾向于贪婪策略。

# 4 算法描述

基于以上描述，给出基于排序优先经验回放的竞争深度$\boldsymbol { \mathcal { Q } }$ 网络算法（duelingDQN-PR）完整流程：

1）对于每个回合：2) 初始化环境，得到初始状态 $\mathbf { S } _ { t }$ 03） 对于回合中的每一步：4） 采用ε-贪婪策略选择动作，随机选择一个动作 $\mathbf { A } _ { t }$ ，或者$\mathbf { A } _ { t } = a r g m a x _ { a } \mathcal { Q } ( \mathbf { S } _ { t } , a ; \theta , \alpha , \beta )$ 。

5） 执行动作后观测到环境反馈 $\mathbf { R } _ { t }$ 和新状态 $\mathbf { S } _ { t + 1 }$ ，计算时序误差：$\delta _ { t } = \mathbf { R } _ { t } + \gamma m a x _ { A _ { t } } Q ( S _ { t } , A _ { t } ; \theta , \alpha , \beta ) - \mathbf { Q } ( \mathbf { S } _ { t - 1 } , \mathbf { A } _ { t - 1 } ; \theta , \alpha , \beta ) \ _ { c }$ （2号6) 将时序误差 $\delta _ { { t } }$ 按从大到小排列，得到 $\mathrm { r a n k } ( \mathrm { t } )$ 07) 计算状态动作转换经验的优先性 $p _ { t } = 1 / r a n k ( t )$ 。计算采样概率 $\mathsf { p } ( t ) = \frac { \boldsymbol { p _ { t } } ^ { \alpha } } { \sum _ { n } \boldsymbol { p _ { n } } ^ { \alpha } }$ ∑pa，重要性权重w(t)=1/ $\mathrm { \bf ~ w } \left( \mathrm { t } \right) = 1 / \Biggl ( \frac { p _ { i } } { p _ { m i n } } \Biggr ) ^ { \beta }$ ，以概率p(t)将转换经验 $\mathbf { \Delta S } _ { t - 1 } , \mathbf { A } _ { t - 1 } , \mathbf { R } _ { t } , S _ { t }$ )存储到经验回放池。

8) 从回放经验池根据采样概率进行采样。  
9） 计算Q网络标签y= $y _ { t } = \left\{ \begin{array} { c } { \mathrm { R } _ { t } , \mathcal { Z } _ { \mathrm { ~ c ~ l ~ E ~ } } ^ { \ast } \ast \mathrm { R } _ { : \infty } ^ { - } } \\ { \mathrm { R } _ { t } + \gamma m a x _ { A _ { t } } \mathcal { Q } ( S _ { t } , A _ { t } ; \theta , \alpha , \beta ) . } \end{array} \right.$ 其他  
10) 最小化损失函数 $\begin{array} { r } { \sum w \big ( t \big ) \big ( y _ { t } - \mathbf { Q } ( \mathrm { S } _ { t - 1 } , \mathrm { A } _ { t - 1 } ; \theta , \alpha , \beta ) \big ) ^ { 2 } } \end{array}$ ，更新网络。  
11) 每 $T$ 步，将目标网络参数以竞争 $\boldsymbol { \mathscr { Q } }$ 网络参数代替更新。

上述算法由于采用竞争网络结构，增加两条流分别计算状态价值和动作优势，增加了算法的空间复杂度，当动作空间维数为 $M$ ，增加的存储开销为 $O ( 1 ) + O ( M )$ ，总的存储开销为 $O ( M )$ 。基于排序的优先经验回放采用基于数组的二叉堆存储带有优先性的经验。在容量为 $N$ 的回放经验池中采样和更新的时间复杂度为 $O ( \log N )$ 0

# 5 仿真实验

# 5.1实验设置

为验证所提算法的效果，针对经典控制问题CartPole-vO和MountainCar-vO[1]进行研究。如图1所示，CartPole场景为放置平衡杆的小车左右移动使平衡杆保持直立；MountainCar 场景为位于两座山之间坡底的小车移动，最终到达一座山的标记最高处。采用OpenAIGym 强化学习工具包和Tensorflow1.0深度学习平台搭建仿真环境，编程语言采用Python3.5。设置回放经验池容量为50，每次从经验池采用的经验数量为32。深度神经网络的构建为四层全连接神经网络，CartPole场景下采用隐藏层第一、二层神经元数量分别为40和30，MountainCar场景下则为90和20，使用ReLU激活函数（RectifiedLinearUnit），梯度下降优化选择RMSProp算法。训练时的动作选择采取ε-贪婪策略，ε的初

始值为0.5，折扣因子为0.9。

减少训练时间。不同于DQN 算法中每次只有一个动作的价值得到更新，DuelingDQN算法中，状态价值随着 $\boldsymbol { \mathscr { Q } }$ 值的更新而更新，减少了学习过程的训练时间。本文方法结合了两种改进，花费的训练时间最少。

![](images/a5542b6a30d1062e2a7514b500855c48d489fa080ca9e52a6b3ce92c1263464e.jpg)  
图1经典控制问题场景

# 5.2 实验结果及分析

在CartPole和MountainCar场景下将DQN算法、基于排序优先经验回放的DQN 算法（DQN-PR）、竞争DQN 算法（DuelingDQN）和竞争DQN-PR 算法进行比较，实验结果如图2所示。可以看出，相比于DQN 算法，DQN-PR 优先使用时序误差高的经验来更新网络参数，使网络更快收敛，

图3和4给出了采用不同算法参数时DuelingDQN-PR算法的训练时间。其中，图3(a)和图4(a)为随机动作选择概率ε减少程度对训练时间的影响，当‘增量越大，即学习过程中选择随机动作的概率更快减小，意味着智能体在对环境有一定了解后会更大概率地使用贪婪策略选择动作，从而提高学习环境的速度，减少训练时间。同时随机动作选择概率ε仍然重要，因为探索未知动作产生的学习效果有利于更新 $\boldsymbol { \mathcal { Q } }$ 值，以获得更好的策略。图3(b)和图4(b)给出了不同的学习速率 $\mathfrak { a }$ 对于学习时间的影响， $\mathfrak { a }$ 分别取为0.001，0.005和0.01。由于实验环境比较简单，学习速率较小时，学习过程更加稳定，训练时间更少。然而对于复杂环境，学习速率的选取需要通过尝试，学习速率太小会使网络收敛过慢，学习速率太大会使损失函数振荡。在图3(c)和图4(c)中，目标网络参数的更新速度分别设置为每200、500、800步进行更新。可以看出，在CartPole场景下，更新频率越高则训练时间越少，这是由于目标网络更新速度的提高会使得网络更快收敛；在MountainCar场景下，更新频率越低则训练时间越少。在上坡过程，环境反馈的回报与小车在山坡的位置相关，小车离标记处越近，即所处山坡位置越高，则回报越大。学习较长时间段内的爬坡过程对小车的速度选择更有利。图3(d)和图4(d)反映了折扣因子Y对训练时间的影响。可以看出，当Y越大，未来回报对当前的期望回报值影响越大，智能体计算期望回报时，其中预测的未来回报所占比例更高，有利于学习环境，使得训练时间越少。对于时序相关性强的环境可采取较大Y值。

![](images/84e17477ff0c95028a51f5551f0af3d2d22fb74d93192cf439bbadca87dfa2d3.jpg)  
Fig.1 Classic control problem scene   
图2两个场景下不同算法训练时间的比较

![](images/9545f1966a57ba8f93b1cd4f8c20aabf9418833537e4411a0aade7d3f0b88980.jpg)  
Fig. 2 Comparison of training time of different algorithms in two scences

![](images/d10f2c18362f6cbe54f1bc6a9ebde70cd4e4203839cf978b5b42b5a32a89961b.jpg)  
Fig. 3 Comparison of training time under different algorithm parameters in cart pole scence

![](images/d6e4168f36dcd74676c9203ae0d27e02c9a438efad055d712dd5bf1b9d4a5aa0.jpg)  
图3Cart pole 场景下采用不同算法参数时的训练时间比较  
图4mountaincar场景下采用不同算法参数时的训练时间比较

(c）目标网络参数更新速度对DuelingDQN-PR算法训练时间的影响

Fig.4Comparison of training time under different algorithm parameters in mountain car scence

# 6 结束语

针对 OpenAI Gym平台CartPole 和Mountain Car 两个经典控制问题，采用基于排序优先经验回放的竞争深度 $\boldsymbol { \mathcal { Q } }$ 网络算法进行研究。实验结果表明，本方法有效地减少学习过程的训练时间。同时详细分析了各种关键算法参数对学习性能的影响，为方法的实际应用提供了参考。

# 参考文献：

[1]刘全,翟建伟,章宗长,等.深度强化学习综述[J].计算机学报,2018, 41(1):1-27.(Liu Quan,Zhai Jianwei, Zhang Zongchang,et al.A survey on deep reinforcement learning [J].Chinese Journal of Computers,2018, 41 (1): 1-27.)   
[2]Arulkumaran K，Deisenroth M P,Brundage M，et al.Deep reinforcement learning:a brief survey [J]. IEEE Signal Processing Magazine,2017,34 (6):26-38.   
[3]Mnih V,Kavukcuoglu K,Silver D,et al.Playing atari with deep reinforcement learning [J].Computer Science,2013.   
[4]Hasselt H V,Guez A,Silver D.Deep reinforcement learning with double Q-learning [J].Computer Science,2015.   
[5]Schaul T, Quan J,Antonoglou I,et al.Prioritized experience replay [J]. Computer Science,2015.   
[6]Wang Ziyu,Schaul T,Hessel M,et al.Dueling network architectures for deep reinforcement learning [C]//Proc of the 33rd International Conference on Machine Learning.2016.   
[7]Degris T,Pilarski PM, Sutton R S.Model-Free reinforcement learning with continuous action in practice [C]//Proc of American Control Conference.2012:2177-2182.   
[8]Van Hasselt H,Mahmood AR,Sutton R S.Off-policy TD() with a true online equivalence [C]//Proc of Conference on Uncertainty in Artificial Intelligence.2014.   
[9]Van Seijen，Harm，Sutton R S.True online TD (λ）[C]//Proc of

International Conference on International Conference on Machine Learning.2014:I-692. [10] Hou Yuenan,Liu Lifeng,Wei Qing,etal.A novel DDPG method with prioritizedexperiencereplay[C]//ProcofIEEEInternational

Conference on Systems,Man,and Cybernetics.2O17:316-321. [11] Malla N,Ni Zhen．A new history experience replay design for model-free adaptive dynamic programming [J]. Neurocomputing,2017, 266:141-149.