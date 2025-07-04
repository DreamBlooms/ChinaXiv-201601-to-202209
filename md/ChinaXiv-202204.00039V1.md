# 结合状态预测的深度强化学习交通信号控制

唐慕尧，周大可，李涛(南京航空航天大学 自动化学院，南京 211100)

摘要：深度强化学习(Deep Reinforcement Leaming，DRL)可广泛应用于城市交通信号控制领域，但在现有研究中，绝大多数的 DRL 智能体仅使用当前的交通状态进行决策，在交通流变化较大的情况下控制效果有限。文中提出一种结合状态预测的DRL信号控制算法。首先，利用独热编码设计简洁且高效的交通状态；然后，使用长短期记忆网络(Long Short-Term Memory，LSTM)预测未来的交通状态；最后，智能体根据当前状态和预测状态进行最优决策。在SUMO(SimulationofUrbanMobility)仿真平台上的实验结果表明，在单交叉口、多交叉口的多种交通流量条件下，与三种典型的信号控制算法相比，所提算法在平均等待时间、行驶时间、燃油消耗、CO2排放等指标上都具有最好的性能。

关键词：交通信号控制；状态预测；深度强化学习；深度Q网络；长短期记忆网络中图分类号：TP181 doi:10.19734/j.issn.1001-3695.2021.12.0704

State prediction based deep reinforcement learning for traffic signal control

Tang Muyao, Zhou Dake†,Li Tao (School ofAutomation Engineering,Nanjing University ofAeronautics &Astronautics,Nanjing 2111oo,China)

Abstract: Urban trafic signal controlcan widelyuse deepreinforcement learning (DRL)technique.However,in existing researches,most DRLagentsonlyuse thecurrent traffic state to make decisions and havelimited control efects when the trafic flow changes greatly.Aiming at theproblem,this paper proposedastate prediction based deepreinforcement learning algorithmfortrafic signal control.Thealgorithmusedone-hotcoding todesignaconciseand eficient traffic stateandthen usedaLong Short-Term Memory(LSTM) to predictthe future state.Theagent made optimal decisions basedonthe current state and the predicted state.The experimental results on the simulation platform SUMO show that compared with three typicalsignal control algorithms,the proposed algorithm has thebest performance in terms of average waiting time,travel time,fuelconsumption,CO2emisionsandcumulativerewardboth inasingle intersectionandmultiple intersectionsunder different flow conditions.

Key words:trafc signal control; state prediction; deepreinforcement learning;deepq network; long short-term memory

# 0 引言

随着人们生活水平的提高，汽车保有量持续增长，城市的交通拥堵问题也日趋严重。交通信号控制是提高道路通行效率、缓解交通拥堵最直接、成本最低的途径。SCATS[]和SCOOT[2]是目前广泛使用的自适应交通信号控制系统，前者选择信号配时方案，后者利用简化的交通模型求解最优的信控策略。但是，简化模型的建立依赖于大量的假设和经验方程，因此，对于复杂多变的真实交通场景，这类系统的效果欠佳。近年来，随着人工智能技术的发展，强化学习[3(ReinforcementLearning，RL)尤其是数据驱动的深度强化学习，在交通信号控制方面展现出卓越的应用前景。

强化学习是一种“试错”的学习方法，通过与环境交互来学习最优策略。应用在交通信号控制中，可以把一个或几个交叉口看成一个智能体(Agent)，智能体观测路网状态后作出决策，通过最大化环境反馈的奖励以学习最优的信号配时方案。受到人脑工作模式的启发，深度学习[4](Deep Learning,DL)能够把底层特征组合形成更加抽象的高层特征，可以有效处理高维数据。深度强化学习(DRL)结合了DL 的强感知能力与RL的强决策能力，非常适用于交通信号控制的任务。

2010年，Arel等[5]首次将DRL引入交通信号控制领域，使用神经网络拟合Q值，但是缺少经验回放、目标网络部分。Liu等[提出3DQN_PSER算法，使用优先级序列经验回放(Priority Sequence ExperienceReplay，PSER)更新经验池中序列样本的优先级，使智能体获取与交通状态相似的前序样本，提高训练效率。Wei等[7提出模型Intellilight，使用相位门结构设置独立的学习通道，根据相位、动作对经验池进行划分，并用真实的交通数据做实验。Zheng 等[8]提出FRAP模型，利用不同信号相位间的竞争关系，实现了在交通流中翻转和旋转等对称情况下的普适性。Jin等使用动作策略阈值词典排序法(ThresholdLexicographic Ordering，TLO)自适应地选择优化目标，基于SARSA 算法对比多种函数逼近方法的改善效果。Tan 等[10]将大规模路网分为若干个子区域，对每个区域，使用Peraction DQN或WolpertingerDDPG 进行控制，将所有智能体的学习策略传递给全局智能体实现全局学习。这些 DRL信控方法本质上是一阶马尔可夫决策过程，智能体仅根据当前的状态进行决策，在复杂多变的实际交通场景下难以实现最优的控制效果。如果能合理预测未来状态，智能体将提前考虑可能出现的交通情况，学习更好的信控策略。$\mathrm { \Delta X u }$ 等[11提出了DRQN模型，跨8个时间步长集成隐藏状态输入DRL智能体，但这样显著地增加了状态的维数，容易导致神经网络过拟合。循环神经网络具有短时记忆能力，Chu等[2]在DRL智能体中采用LSTM网络来提取动态的交通信息，但该网络并没有直接预测未来的交通状态。

本文提出了一种结合状态预测的深度强化学习信号控制算法DQN_SP，主要特点有：1)通过引入显式的交通状态预测，DRL智能体利用当前和未来状态进行最优决策。2)精心设计智能体的状态，该状态包含最重要的交通信息且数据量小易于预测。在单交叉口、多交叉口的多种流量条件下验证了所提算法的有效性与可行性，车流数据模拟了现实中高低峰的情形，具有工程应用价值。

# 1 研究背景

本节将介绍强化学习、深度强化学习的基本概念和方法，以及DRL信号控制算法。

# 1.1强化学习

强化学习是和有监督学习、无监督学习并列的第三类机器学习方法，智能体通过与环境不断交互来学习为了达成某个目标所需的最佳策略。马尔可夫决策过程是一种通过交互式学习来达到目标的理论框架，其灵活抽象，可以很好地解释强化学习的基本流程。智能体根据当前策略，以一定概率执行最优动作并与环境交互，用动作价值函数 $q _ { \pi } ( s , a )$ 来表示智能体在状态 $s$ 下采取动作 $a$ 的期望回报，表示为

$$
q _ { \pi } ( s , a ) \dot { = } E _ { \pi } [ G _ { t } \mid S _ { t } = s , A _ { t } = a ] =
$$

$$
E _ { \pi } [ \sum _ { k = 0 } ^ { \infty } \gamma ^ { k } R _ { t + k + 1 } \mid S _ { t } = s , A _ { t } = a ]
$$

智能体在与环境交互后学习到最优策略，最优动作价值函数为在状态 $s$ 下采取动作 $\boldsymbol { a }$ 获得的最高回报值，根据贝尔曼最优方程，可得：

$$
\begin{array} { r l } & { q _ { * } ( s , a ) = } \\ & { E [ R _ { t + 1 } + \gamma \underset { a ^ { * } } { \operatorname* { m a x } } q _ { * } ( s _ { t + 1 } , a ^ { \prime } ) \big | S _ { t } = s , A _ { t } = a ] = } \\ & { \displaystyle \sum _ { s ^ { \prime } , r } p ( s ^ { \prime } , r \big | s , a ) [ r + \gamma \underset { a ^ { * } } { \operatorname* { m a x } } q _ { * } ( s ^ { \prime } , a ^ { \prime } ) ] } \end{array}
$$

不断迭代最优动作价值函数 $\boldsymbol { q } _ { * } ( s , a )$ 后，得到最优策略：

$$
\pi _ { * } = \arg \operatorname* { m a x } _ { a \in A } q _ { * } ( s , a )
$$

# 1.2深度强化学习

DRL是RL与DL的结合，是目前控制系统中先进的学习框架之一。2013年DeepMind[13]提出了DQN，不同于Q-Learning使用一张表来保存所有的Q值，DQN使用经验回放来更新目标价值。将智能体与环境交互获得的样本$( s , a , r , s ^ { \prime } )$ 存入经验池中，从经验池均匀采样小批量样本，使用随机梯度下降方法训练深度神经网络使其逼近Q值，随机采样能够打破样本间的强相关性，使训练收敛稳定。DQN使用同一个网络来选择动作和计算目标Q值，两者在迭代的过程中相互依赖，不利于算法的收敛。为了解决此问题，DeepMind提出了NatureDQN[14]，使用两个网络，当前网络 $\varrho$ 用来选择动作、更新参数，目标网络 $Q ^ { - }$ 用来计算目标Q值， $\varrho ^ { - }$ 网络的参数不需要实时迭代更新，而是每隔一段时间从当前网络$\varrho$ 复制过来，当前最优动作价值函数的优化目标表示为

$$
y ( s , a ) = r + \gamma \operatorname* { m a x } _ { a ^ { \prime } } q ( s ^ { \prime } , a ^ { \prime } ; w ^ { - } )
$$

其中 $w ^ { - }$ 表示目标值网络的参数。

上述算法计算目标Q值时都是通过贪婪法直接得到，虽然可以快速让Q值向优化目标靠近，但是很容易导致过度估计。为了缓解模型的过拟合问题，VanHasselt 等人[15]提出了DoubleDQN，先在当前网络 $\varrho$ 中寻找最大Q值对应的动作，再将此动作代入目标网络 $Q ^ { - }$ 计算目标Q值，优化目标表示为

$$
y ( s , a ) = r + \gamma q ( s ^ { \prime } , \arg \operatorname* { m a x } _ { a ^ { \prime } } q ( s ^ { \prime } , a ^ { \prime } ; w ) ; w ^ { - } )
$$

上述算法通过经验回放来训练深度Q网络，在经验池中对样本均匀采样，然而不同样本TD误差不同，对反向传播的影响也不一样。为了解决此问题，Schaul 等[16]基于DDQN提出了优先经验回放算法，给定正比于样本TD误差绝对值$\vert \delta ( t ) \vert$ 的优先级，并将优先级存入经验池，训练时使优先级高的样本更容易被采样，避免没有价值的迭代，提高算法收敛速度。Wang 等[17]对神经网络结构进行优化，提出 DuelingDQN，将Q网络分为价值函数与优势函数两部分。

# 1.3基于DRL的交通信号控制

基于DRL的信控方法不需要场景先验知识，而是通过与交通环境不断交互来学习最优策略。在此过程中，交叉口或路网看成一个智能体，状态是对交通环境的描述，动作是交通信号的变化，奖励衡量了动作后交通通行的效率变化。

现有的DRL信控算法在状态、动作、奖励定义方面有很大不同。状态定义分为两类，基于车辆的表示(如实时图像[7,18]、包括车辆位置或速度信息的DTSE 形式[6,19,20])，和基于特征的值向量表示(如排队长度[7,19,21]、累计延误[19,20]、等待时间[7,19)。动作定义分为选择一个可能的绿灯相位[6,20,21]、保持当前相位或切换至下一相位[7,11,19],或改变相位持续时间[9,22]。状态是环境的特征矩阵或向量，动作是离散的选择向量，奖励是与交通数据有关的标量值。奖励的定义主要考虑队列长度[6,7,19,20]、延误[7,19,20,22]等。DRL 算法主要分为基于值函数的 DQN[6,7,11,19,20]、基于策略的 DDPG[10,23]、基于AC 框架的 A2C[12,18]、A3C[24]等。

一些研究考虑了交通流的时序相关性。Yu等[23]把车辆的速度加入到状态表示中，Wei等7把表示车辆位置的实时图像喂入CNN网络，这两种方法通过合理设计状态体现交通流的动态特性。Chu等[2]使用LSTM网络拟合Q值，利用网络的记忆能力学习交通信息的变化趋势，但是没有直接预测未来的交通状态。为了克服DQN无法记住当前输入之前的历史信息这一缺点，Xu 等[提出了DRQN 模型，将当前的状态和几个历史状态输入智能体，可以看成n阶马尔可夫决策过程。Liu 等使用PSER更新经验池中序列样本的优先级，使当前时刻之前的样本数据更容易被采样。上述方法或多或少考虑了交通流的时序特性，但是没有对交通状态直接预测，因为微观状态维数大，容易引发维数灾难的问题，且和DRL结合时难以训练出令人满意的结果。

# 2 结合状态预测的深度强化学习交通信号控制算法

本文将状态预测与DRL中的DQN算法相结合，采用独热编码的形式精心设计微观状态，并用LSTM预测未来的状态，智能体根据当前状态和预测状态进行决策。本节将对状态、动作、奖励进行定义，并介绍所提算法DQN SP的网络模型。

# 2.1状态定义

本文需要利用当前和预测的交通状态进行决策，因此状态设计尤为关键。基于DTSE方法采用非均匀量化和独热编码来设计状态向量。本文用于仿真的交叉口为双向6车道，长500米，沿着车辆的行驶方向，左边的车道为左转车道，中间车道为直行车道，右边的车道为直行加右转车道。本文按照一定长度比例将车道划分为元胞，图1所示的是以交叉□西进口道为例的元胞设计图。其中，右边的两条车道看做一个整体进行划分，左边的左转车道单独进行划分，这样一个交叉口四个方向的车道将被划分为 80 个元胞。状态由每个元胞中是否有车辆来表示，如有车辆，状态取值为1，否则为0。

由图1西进口道的元胞设计图可以看出，交叉口附近以7米为单位划分出10个元胞，其中每个元胞都只能容纳1辆车，可以精确地反映车辆分布情况，离交叉口最远的元胞长230 米。与用实时图像[18]或对车道均匀划分[19]表示状态的方法相比，该方法使智能体更关注靠近路口的交通状况，降低了数据维度，缩短了计算时间。以每个元胞中是否有车辆作为状态，简化交通信息，能够反映环境的主要特征，即交叉□附近的车辆分布情况。另外，对这种独热编码形式的状态进行预测，可以看成二分类问题，相比于传统的回归预测，能够提高预测准确率。

![](images/2d8d266f28ca7551650768e22b67e177366f2a366ed68019bf6918237dd37203.jpg)  
图1交叉口西进口道的元胞设计图

# 2.2动作定义

智能体需要根据交通状态选择合适的动作来疏导交通，本文的动作定义为选择一个可能的信号相位。动作集合$A = \{ N S G , N S L G , E W G , E W L G \}$ ，分别表示南北方向直行和右转绿灯、南北方向左转绿灯、东西方向直行和右转绿灯、东西方向左转绿灯。每个相位的最短持续时间设为 $1 0 ~ s$ ，同时为了安全起见，绿灯和红灯切换期间会有时长 $3 ~ s$ 的黄灯。

# 2.3奖励定义

智能体在 $t$ 时刻观测环境状态为 $s _ { t }$ ，执行动作 $\boldsymbol { a } _ { t }$ 后得到环境对该动作的反馈 $r _ { t }$ ，用来衡量该动作的质量，是DRL能否收敛以及能否取得良好效果的关键。本文奖励 $r _ { t }$ 定义为相邻时间步的所有车道车辆排队长度之差：

$$
r _ { t } = \alpha q _ { t } - q _ { t + 1 }
$$

其中 $q _ { t }$ 表示 $t$ 时刻路网中所有车道的排队长度之和， $q _ { t + 1 }$ 表示下一时间步所有车道的排队长度之和， $\alpha$ 为系数，通过多次实验后设为0.9。

# 2.4结合状态预测的 DRL信控算法(DQN_SP)

本文所提算法DQN_SP采用LSTM预测未来微观状态$s _ { p }$ ，并将其与当前状态 $s$ 串联，作为增广状态输入DRL智能体，DRL 算法使用传统的DQN[13]，旨在验证结合状态预测后算法的有效性与可行性。DQN_SP的网络结构如图2所示，最优动作价值函数的优化目标表示为

$$
y ( s , s _ { p } , a ) = r + \gamma \operatorname* { m a x } _ { a ^ { \prime } } q ( s ^ { \prime } , s _ { p } ^ { \prime } , a ^ { \prime } )
$$

![](images/2714b27528f10a410114215cd950e2626ecaa835490e7d5916ce25241efedc8c.jpg)  
Fig.1Cellular design of the west entrance road at the intersection   
图2DQN_SP 的网络结构  
Fig.2The network structure ofDQN_SP

DQN_SP的算法流程如下所示。

1 初始化深度Q网络、LSTM网络、经验池  
2 for episode $\mathbf { \Psi } = \mathbf { \Psi } _ { 1 }$ to M do  
3 初始化路网环境，导入车流数据  
4 for $\textsf { t } = \textsf { 1 }$ to T do  
5 智能体观测当前环境状态 $s$   
6 LSTM预测 $n$ 个时间步后的微观状态 $s _ { p }$   
7 当前状态与预测状态串联后输入DQN智能体，智能体基于 $\varepsilon$   
贪婪策略执行动作 $a$ （204号  
8 智能体进入新的状态 $\boldsymbol { s } ^ { \prime }$ ，根据式(6)计算奖励 $\boldsymbol { r }$   
9 LSTM预测 $n$ 个时间步后的微观状态 $s _ { p }$ =  
10 将样本 $( s , s _ { p } , a , r , s ^ { \prime } , s _ { p } ^ { \prime } )$ 存入经验池中  
11 end for  
12 从经验池中抽取样本训练网络  
13 根据式(7)计算优化目标，使用均方误差损失函数更新深度Q  
网络参数 $w$   
14 使用二值交叉熵损失函数更新LSTM网络参数 $\theta$   
15 end for

# 3 实验结果与分析

本节首先介绍实验的仿真环境与算法超参数，然后介绍基准算法FTC、SOTL、DQN，最后在单交叉口、多交叉口的多种流量条件下验证了算法DQN_SP的有效性。

# 3.1仿真环境与超参数设置

SUMO是免费开源的交通系统仿真软件，其中的Traci(TrafficControlInterface)接口可以与多种开发环境在线交互，实现对交通信号的控制。本文以UbuntuGeForceRTX2080GPU作为硬件环境，算法通过深度学习框架Keras 实现，在SUMOv1.6.0下进行仿真实验。

交叉口设置：本文在单交叉口和多交叉口两种场景下分别进行仿真。交叉口由4条垂直的道路组成，每条道路长500米，为双向六车道，沿着车辆的行驶方向左边为左转车道，中间为直行车道，右边为直行加右转车道。多交叉口为4个相同的交叉口组成的 $2 \times 2$ 井字形路网，路口配置同单交叉口。

交通流设置：车辆生成的方式对交通信号控制有着重要的影响，本文中车辆的生成服从韦伯分布，其概率密度函数为

$$
f ( x ; \lambda , a ) = \left\{ \begin{array} { l l } { { \displaystyle \frac { a } { \lambda } ( \frac { x } { \lambda } ) ^ { a - 1 } e ^ { - ( \frac { x } { \lambda } ) ^ { a } } x \ge 0 } } \\ { { 0 } } & { { x < 0 } } \end{array} \right.
$$

其中 $\lambda$ 是比例参数设为1， $\boldsymbol { a }$ 是形状参数设为2，绝大多数车辆集中在某一段时间内进入路网，可以模拟现实生活中高峰低峰的情形。车辆从任意入口进入路网，以 $7 5 \%$ 的概率直行，$12 . 5 \%$ 的概率左转， $12 . 5 \%$ 的概率右转。车辆长 $5 ~ m$ ，加速度为 $\boldsymbol { \mathrm { ~ l ~ } } \boldsymbol { m } / s ^ { 2 }$ ，以 $3 6 k m / h$ 的速度进入路网，最大速度为 $5 0 k m / h$ ，车辆之间最小间距为 $2 . 5 ~ m$ 。

超参数设置：参照文献[7,9,19]并结合实验，超参数设置如下。训练回合数设为100，算法使用DNN评估Q值，隐藏层数为5，宽度为400，采用Adam优化器，学习率为0.001，批处理大小为80，每回合训练迭代800次，采用均方误差作为损失函数。预测网络使用6个LSTM单元，每个单元有3个LSTM层，神经元个数为80，采用Adam优化器，批处理大小为128，每回合训练迭代1次，采用二值交叉熵作为损失函数。RL经验池尺寸最小为600，最大为50000，折扣因子为0.75，使用 $\varepsilon$ 贪婪算法输出动作。

# 3.2实验评估与结果分析

本文在单交叉口和多交叉口两种场景下分别实验。对于单交叉口，仿真时长为 $5 4 0 0 ^ { \phantom { - } }$ ，进入路网的车辆数目为500、1000、1500，分别对应低、中、高三种流量条件。对于多交叉口，仿真时长也为 $5 4 0 0 ^ { s }$ ，进入路网的车辆数目设为2000、3000，分别对应低、高两种流量条件。对于每种流量条件，用随机种子seed生成20组车流数据，20组数据下车辆的平均等待时间、平均行驶时间、平均燃油消耗、平均 $\mathrm { C O } _ { 2 }$ 排放、平均累计奖励作为算法的性能指标。其中，平均等待时间主要来自于车辆排队时消耗的时间，与定义的奖励相关性最强，为主要指标，平均行驶时间、燃油消耗、 $\mathrm { C O } _ { 2 }$ 排放为次要指标。所提算法对1、5、10个时间步后的状态进行预测，分别记为DQN_SP_1、DQN_SP_5、DQN_SP_10。为了验证预测的有效性，将DQN_SP与下列基准算法进行比较：

固定配时控制(Fixed-time Control，FTC)。FTC 根据经典的韦伯斯特配时法[25]预先定义一套配时方案，广泛应用于现实交通场景中。

自组织交通灯(Self-organizing Traffic Lights，SOTL)[26]。当红灯方向的排队长度达到阈值时，该方向的信号灯就变成绿灯，若绿灯方向一定距离内车辆数过多，则延长绿灯时长。

基于DQN的交通信号控制。使用与所提算法DQN_SP相同的DQN 算法[13]，唯一区别在于其不对未来状态进行预测，所以网络输入维度减半，其余超参数设置以及状态、动作、奖励定义与DQN_SP相同。

图3是在单交叉口中流量条件下，训练与测试过程中，各算法的累计奖励对比和车辆平均等待时间对比。图3(a)给出了在单交叉口中流量条件下，DQN_SP与DQN 在训练过程中的累计奖励对比，两者区别不大。可见，增加了状态预测，不会降低算法的收敛速度，也不会削弱算法稳定性。图3(b)表示DQN_SP与三种基准算法的车辆平均等待时间对比。在训练的初始阶段，由于经验池中的样本太少，智能体还没有学到正确的控制策略，所以平均等待时间会大幅上升，随着训练的进行，交叉口通行状况逐渐好转，最终趋于平稳。

训练好的模型在随机生成的20组车流数据下进行测试，平均性能如表1所列，可以看出无论是预测1步、5步还是10步后的状态，DQN_SP的性能都比FTC、SOTL、DQN更加优越，且在主要指标上,DQN_SP_5改善最多，相比于DQN,车辆平均等待时间减少了 $6 . 0 6 \%$ ，累计奖励提高了 $5 . 6 1 \%$ 。然而在行驶时间、燃油消耗、 $\mathrm { C O } _ { 2 }$ 排放这三个次要指标上，DQN_SP_1改善效果最明显。图3(c)表示DQN_SP_5与DQN在20 次测试中的累计奖励对比，图3(d)表示DQN_SP_5与三种基准算法的车辆平均等待时间对比。结果显示，相较于传统的FTC、SOTL信号控制，基于DRL的方法在缩短车辆的等待时间上效果显著，且在18次测试中，DQN_SP_5的控制效果均优于DQN。

Tab.2Performance of algorithms under the condition of low traffic   

<html><body><table><tr><td colspan="6">flow at an intersection</td></tr><tr><td>Algorithm</td><td>Waiting time/s</td><td>Travel time/s</td><td>Fuel</td><td>CO2</td><td>Cumulative</td></tr><tr><td>FTC</td><td>17.73</td><td>101.64</td><td>consumption/ml 87.99</td><td>emissions/g 204.69</td><td>reward</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>SOTL</td><td>8.78</td><td>92.31</td><td>77.86</td><td>181.12</td><td></td></tr><tr><td>DQN</td><td>7.98</td><td>90.82</td><td>76.49 75.78</td><td>177.93</td><td>-37.11</td></tr><tr><td>DQN_SP_1</td><td>7.57</td><td>90.29</td><td></td><td>176.29</td><td>-35.54</td></tr><tr><td>DQN_SP_5</td><td>7.41</td><td>89.97</td><td>75.41</td><td>175.42</td><td>-34.59</td></tr><tr><td>DQN_SP_10</td><td>7.73</td><td>90.45</td><td>75.94</td><td>176.67</td><td>-36.07</td></tr></table></body></html>

表3单交叉口高流量条件下算法的性能

表2单交叉口低流量条件下算法的性能  
Tab.3Performance of algorithms under the condition of high traffic   

<html><body><table><tr><td colspan="6">flow at an intersection</td></tr><tr><td>Algorithm</td><td>Waiting time/s</td><td>Travel time/s</td><td>Fuel</td><td>CO2</td><td>Cumulative</td></tr><tr><td>FTC</td><td>22.75</td><td>109.20</td><td>consumption/ml 95.60</td><td>emissions/g 222.40</td><td>reward</td></tr><tr><td>SOTL</td><td>25.13</td><td>114.17</td><td>99.06</td><td>230.45</td><td></td></tr><tr><td></td><td>16.16</td><td></td><td>88.72</td><td></td><td></td></tr><tr><td>DQN DQN_SP_1</td><td>15.40</td><td>102.67</td><td>87.85</td><td>206.39</td><td>-207.04</td></tr><tr><td></td><td>15.15</td><td>101.88 101.53</td><td>87.58</td><td>204.37 203.73</td><td>-197.53 -194.86</td></tr><tr><td>DQN_SP_5</td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>DQN_SP_10</td><td>14.68</td><td>101.09</td><td>87.08</td><td>202.58</td><td>-189.16</td></tr></table></body></html>

![](images/ec1d9fb76c28768d0868b751b8667546e571f2af17bd1e98a83c227297ea2bbc.jpg)  
(a）训练过程中各算法的累计奖励对比

![](images/572c0063a1ccfc0c6c349945a47c3d4eba5e68cd52b24b7224d525cbee7e1607.jpg)  
(b)训练过程中各算法的车辆平均等待时间对比

![](images/32875a3502a22dbf9fdaf3131f16ca0aaf7b0fc733c725d2916ff69ace99bd05.jpg)  
(c)测试过程中算法DQN和 $\mathsf { D Q N \_ S P } _ { - } 5$ 的累计奖励对比

![](images/1b07404715a59c14cb0d863b0d2c32d5d1189f355b4818a769e9146c6b86f463.jpg)  
(d)测试过程中各算法的车辆平均等待时间对比 图3各算法的累计奖励对比和车辆平均等待时间对比 Fig.3Comparison of cumulative rewards of algorithms and comparison of average waiting time of vehicles

本文还在多交叉口场景下进行实验，每个交叉口信号都用一个智能体控制。本文旨在验证结合状态预测的DRL的有效性，因此，使用简单的多智能体协作策略：采用空间折扣因子削弱来自其他交叉口的奖励，当前交叉口奖励权重为0.5，邻居交叉口为0.2，对角交叉口为0.1。仿真时长5400秒，进入路网的车辆数目设为2000、3000辆，分别对应低流量和高流量，表4、5列出了算法在20次测试中的平均性能。在高流量情况下，SOTL控制效果糟糕，因为当交通流高度随机的时候，车辆驱动的控制方法很难奏效。在低流量条件下，DQN_SP_5的改善效果最好，相比于DQN，平均等待时间减少 $8 . 8 2 \%$ ，累计奖励提高 $8 . 1 1 \%$ ，然而在高流量条件下，

DQNSP10的改善效果最好，平均等待时间减少 $4 . 9 2 \%$ ，累计奖励提高 $4 . 5 9 \%$ 。由此可见，随着车流量变大，需要对更多时间步后的状态进行预测，以更有效地学习交通变化趋势，提高通行能力。

表4多交叉口低流量条件下算法的性能

Tab.4Performance of algorithms under the condition of low traffic flow at multiple intersections   

<html><body><table><tr><td>Algorithm</td><td>Waiting time/s</td><td>Travel time/s</td><td>Fuel consumption/ml</td><td>CO2 emissions/g</td><td>Cumulative reward</td></tr><tr><td>FTC</td><td>45.05</td><td>177.37</td><td>157.77</td><td>367.03</td><td></td></tr><tr><td>SOTL</td><td>29.15</td><td>158.72</td><td>136.97</td><td>318.63</td><td></td></tr><tr><td>DQN</td><td>21.54</td><td>151.11</td><td>129.86</td><td>302.11</td><td>-371.72</td></tr><tr><td>DQN_SP_1</td><td>20.23</td><td>149.39</td><td>128.01</td><td>297.79</td><td>-350.65</td></tr><tr><td>DQN_SP_5</td><td>19.64</td><td>148.78</td><td>127.39</td><td>296.34</td><td>-341.59</td></tr><tr><td>DQN_SP_10</td><td>20.27</td><td>149.46</td><td>128.06</td><td>297.92</td><td>-351.12</td></tr></table></body></html>

表5多交叉口高流量条件下算法的性能

Tab.5Performance of algorithms under the condition of high traffic flowat multiple intersections   

<html><body><table><tr><td colspan="5">Hgntanenowathurtipietersections</td></tr><tr><td>Algorithm</td><td>WaitingTravel time/s time/s</td><td>Fuel consumption/ml</td><td>CO2 emissions/g</td><td>Cumulative reward</td></tr><tr><td>FTC</td><td>51.05</td><td>185.78</td><td>166.42</td><td>387.14</td></tr><tr><td>SOTL</td><td>61.47</td><td>204.15 178.84</td><td>416.02</td><td>一</td></tr><tr><td>DQN</td><td>34.36</td><td>167.89 147.45</td><td>343.02</td><td>-836.09</td></tr><tr><td>DQN_SP_1</td><td>33.23</td><td>166.81 146.37</td><td>340.51</td><td>-811.05</td></tr><tr><td>DQN_SP_5</td><td>32.87</td><td>166.60 146.19</td><td>340.08</td><td>-803.14</td></tr><tr><td>DQN_SP_10</td><td>32.67</td><td>166.59</td><td>146.02 339.68</td><td>-797.98</td></tr></table></body></html>

综上所述，相较于基准算法，DQNSP在单交叉口和多交叉口的场景下都能学习更好的信号控制策略，有效缓解了交通拥堵，减少燃油消耗与污染排放。随着车流量的增多，需要预测更多时间步后的状态以获得更好的控制效果。

# 4 结束语

本文利用了交通数据的时序相关性，提出结合状态预测的深度强化学习交通信号控制算法DQN_SP，通过提取高维交通特征，并对未来微观状态进行预测，在单交叉口、多交叉口以及多种流量条件下都取得了更好的信控效果。与FTC、SOTL、DQN算法相比，DQN_SP在平均等待时间、行驶时间、燃油消耗、 $\mathrm { C O } _ { 2 }$ 排放方面具有提升。未来本文将进一步研究将状态预测与更先进的DRL算法(如TD3、SAC等)相结合，并使用真实的交通数据进行验证。

# 参考文献：

[1]Sims AG,Finlay AB.SCATS,splits and offsets simplified (SOS)[J]. Australian Road Research,1984,12(4):17-33.   
[2]Hunt PB,Robertson DI,Bretherton RD,et al.The SCOOT on-line traffic signal optimisation technique [J].Traffic Engineering& Control, 1982,23 (4): 190-192.   
[3]Sutton R S,Barto AG.Reinforcement learning:an introduction [M].MIT Press,2018.   
[4]LeCun Y,Bengio Y,Hinton G.Deep learning [J].Nature,2015,521 (7553): 436-444.   
[5]Arel I,Liu C,Urbanik T,et al. Reinforcement learning-based multi-agent system for network traffic signal control[J].IET Intelligent Transport Systems,2010,4(2): 128-135.   
[6]刘志，曹诗鹏，沈阳，等．基于改进深度强化学习方法的单交叉口信 号控制[J]．计算机科学，2020，47(12):226-232.(Liu Zhi,Cao Shipeng,Shen Yang,et al. Signal control of single intersection based on improved deep reinforcement learning method [J]. Computer Science,   
[7]Wei Hua, Zheng Guanjie,Yao Huaxiu,et al. Intelilight: areinforcement learning approach for intelligent traffic light control [C]// Proc of the 24th ACM SIGKDDInternational Conference on Knowledge Discovery & Data Mining. New York: ACM Press,2018: 2496-2505.   
[8] Zheng Guanjie, Xiong Yuanhao, Zang Xinshi,et al. Learning phase competition for traffic signal control $[ \mathrm { C } ] / \AA$ Proc of the 28th ACM International Conference on Information and Knowledge Management. New York: ACM Press,2019: 1963-1972.   
[9]Jin Junchen,Ma Xiaoliang.A multi-objective agent-based control approach with application in intelligent traffic signal system[J]. IEEE Trans on Intelligent Transportation Systems,2019,20 (10):3900-3912.   
[10] Tan Tian,Bao Feng,Deng Yue,et al. Cooperative deep reinforcement learning for large-scale traffic grid signal control [J]. IEEE Trans on Cybernetics,2019,50 (6): 2687-2700.   
[11] Xu Ming, Wu Jianping,Huang Ling,et al. Network-wide trafic signal control based on the discovery of critical nodes and deep reinforcement learning[J].JoualofInteligentTansportationSystems,024(1): 1-10.   
[12] Chu Tianshu, Wang Jie,Codeca L,et al. Multi-agent deep reinforcement learning for large-scale traffic signal control[J].IEEE Transon Intellgentsrtatis,,()95   
[13] Mnih V,Kavukcuoglu K,Silver D,et al.Playing atari with deep reinforcement learning [J].arXiv preprint arXiv: 1312.5602,2013.   
[14] Mnih V, Kavukcuoglu K,Silver D,etal. Human-level control through deep reinforcement learming [J]. Nature,2015,518 (7540): 529-533.   
[15] Van Hasselt H,Guez A,Silver D.Deep reinforcement learning with double q-learning [C]//Proc of the 30th AAAI Conferenceon Artificial Intelligence.Palo Alto,CA:AAAI Press,2016,30 (1):2094-2100.   
[16] Schaul T, Quan J,AntonoglouI,etal.Prioritized experience replay[C]// Proc of the 4th International Conference on Learning Representations. San Juan,Puerto Rico,2016: 322-355.   
[17] Wang Z, Schaul T, Hessel M,et al. Dueling network architectures for deep reinforcement learning [C// Proc of the 33rd International Conference on Machine Learning. New York: ACM Press,2016: 1995- 2003.   
[18] Mousavi SS,Schukat M, HowleyE.Trafficlight controlusingdeep policy-gradient and value-function-based reinforcement learning [J]. IET Intelligent Transport Systems,2017,11(7): 417-423.   
[19]孙浩，陈春林，刘琼，等．基于深度强化学习的交通信号控制方法 [J]．计算机科学,2020,47(2):169-174.(Sun Hao,Chen Chunlin,Liu Qiong,et al. Traffic signal control method based on deep reinforcement learning [J].Computer Science,2020,47 (2): 169-174.)   
[20] Van der Pol E, Oliehoek F A.Coordinated deep reinforcement learners for trafic light control [C]//Proc of the 30th Conference on Neural Information Processing Systems. Cambridge, MA: MIT Press,2016: 1- 9.   
[21] Wang Xiaoqiang,Ke Liangjun, Qiao Zhimin,et al. Large-scale traffic signal control using a novel multiagent reinforcement learning [J]. IEEE Trans on Cybernetics,2020,51(1): 174-187.   
[22] Touhbi S,Babram MA,Nguyen-Huu T, et al. Adaptive traffic signal control: exploring reward definition for reinforcement learning [J]. Procedia Computer Science,2017,109: 513-520.   
[23] Yu Bingquan,Guo Jinqiu, Zhao Qinpei,et al. Smarter and safer traffic signal controlling via deep reinforcement learning [C]// Proc of the 29th ACM International Conference on Information & Knowledge Management.New York:ACMPress,2020:3345-3348.   
[24] GendersW, Razavi S. Evaluating reinforcement learning state

representations for adaptive traffic signal control[J].Procedia Computer Science,2018,130:26-33. [25] WebsterFV.Traffic signal settings,road research technical [J].Road ResearchLaboratory,1958,39.

[26] Cools SB,Gershenson C,D'Hooghe B. Self-organizing traffic lights: a realistic simulation [M]//Advances in Applied Self-organizing Systems. London: Springer,2013: 45-55.