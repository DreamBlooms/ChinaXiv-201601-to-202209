# 基于深度强化学习的随机资源受限多项目动态调度策略

郭晓剑，胡方勇

(江西理工大学 经济管理学院，江西 赣州 341000)

摘要：目前对于随机工期的分布式资源受限多项目调度(SDRCMPSP)问题的研究较少且大多数为静态调度方案，无法针对环境的变化实时地对策略进行调整优化，及时响应频繁发生的动态因素。为此建立了最小化总拖期成本为目标的随机资源受限多项目动态调度DRL 模型，设计了相应的智能体交互环境，采用强化学习中的DDDQN 算法对模型进行求解。实验首先对算法的超参数进行灵敏度分析，其次将最优组合在活动工期可变和到达时间不确定两种不同条件下对模型进行训练及测试，结果表明深度强化学习算法能够得到优于任意单一规则的调度结果，有效减少随机资源受限多项目期望总拖期成本，多项目调度决策优化提供良好的依据。

关键词：分布式多项目；随机调度；深度强化学习；资源约束中图分类号：TP18 doi:10.19734/j.issn.1001-3695.2022.03.0065

Stochastic resource-constrained multi-project dynamic scheduling strategy based on deep reinforcement learning

Guo Xiaojian, Hu Fangyong (SchoolofEconomics&Management,Jiangxi UniversityofScience&Technology,Ganzhou Jiangxi341ooo,China)

Abstract: There are few studies on the problem of stochastic resource-constrained distributed multi-project scheduling (SDRCMPSP)and most of them are static scheduling schemes,which cannot adjust and optimize the strategy in real time according to changes in the environment and respondto frequent dynamic factors ina timely manner.Therefore,this paper established astochastic resource-constrained multi-project dynamic scheduling DRL model withthe goal of minimizing the total dragcost,design thecorrsponding agent interaction environment,anduse the DDDQN algorithm inreinforcement learning tosolve the model.Theexperimentfirstanalyzes thehyperparametersof thealgorithm,andthentrainsandtests the modeluder twodiferentconditionsof variableactivitydurationand uncertainarival time,andtheresults show thatthe deepreinforcementlearning algorithmcanobtain schedulingresults thatare beter than anysingle rule,fectively reduce the total drag-offcostofrandomresources limited multi-project expectations,and providea good basis for multi-project scheduling decision optimization.

Key words: distributed multi-project; stochastic scheduling; deep reinforcement learning; resource-constrained

# 0 引言

随着社会的发展项目管理技术显得尤为重要，在项目调度的过程中资源的合理配置与调度起着决定性的作用，该类问题通常称之为资源受限项目调度问题(resource-constrainedproject schedulingproblem,RCPSP)[1]。现实情况下往往需要同时调度多个资源受限的项目[2]，且存在局部与全局资源的约束称之为分布式资源首先多项目调度(distributedresource-constrained multi-project schedulingproblem,DRCMPSP)。然而在工程实际中，项目实施可能受到各种不确定因素的影响，如缺少相关项目经验、生产设备故障、资源不可用、天气状况等导致活动工期或项目到达时间与预估时间产生偏离[3],使预先制定的多项目计划不可行，便需要一种有效的方法减少多项目的期望总拖期成本ETTC(except total tardiness cost)该类问题称之为随机资源受限多项目调度(SDRCMPSP)问题目前关于SDRCMPSP问题的文献相对较少，并且大部分调度策略是静态的[4]，如优先规则算法[5][6]。此外 Song 等采用优先规则启发式算法来生成基线计划，并将受影响的活动推至最早可行的时间执行[7]、Tosselli等采用了重复协商博弈的方法[8]、刘东宁等采用了多优先规则启发式方法(MPRH)[9],该方法虽然能够在活动工期变化的动态环境下减少多项目工期延误成本，但在每次决策点时需要进行多次仿真实验，未对以往经验进行有效的利用，无法及时对动态环境作出实时的决策。

以目标为导向的强化学习算法，以其能够实现离线学习与在线应用的优势被广泛运用于动态环境下的调度问题上[10]。且由以往文献可知强化学习算法在被广泛运用于车间作业的动态调度问题上并取得较好的结果[1I][12][13][14],且目前并未有文献研究深度强化学习算法在多项目随机调度问题上的应用，因此本文将该算法运用至SDRCMPSP的动态调度上。

本文针对活动工期、项目到达日期偏差情况而造成多项目作业的总拖期成本TTC(total tardiness cost)增加的影响，通过深度强化学习中智能体不断与环境进行仿真交互，采用文献[14]的DDDQN算法进行调度策略的优化。首先提出静态环境下多项目调度的数学模型并将其结合并行调度方案转换为动态调度过程，其次根据多项目动态调度流程及总拖期成本搭建与智能体交互的环境，运用DDDQN算法使的智能体在环境中根据当前状态不断进行探索和对现有知识的利用优化不同状态下的策略，以此降低随机资源约束多项目调度的ETTC。将所建立的模型与算法进行超参数的策略组合分析求出最优的超参数组合，后将该组合运用活动工期可变或项目到达时间不确定的动态环境下进行仿真研究。仿真结果表明应用深度强化学习方法能够使智能体学习到优于任何单一规则的调度策略，为多项目在动态环境下的调度提供良好的决策依据。

# 1 问题描述

# 1.1 多项目静态问题

假设一个多项目是由 $\mathrm { ~ m ~ }$ 单一项目 $\mathrm { i } ( \mathrm { i } { = } 1 , . . . , \mathrm { m } )$ 所组成，在项目i中存在 $\mathsf { a } _ { \mathrm { i j } } ( \mathrm { j } { = } 1 , . . . , \mathrm { J } _ { \mathrm { i } } )$ 个实活动其工期为dij和两个工期及资源用量为零的虚拟活动aio、 $\mathrm { a } _ { \mathrm { i } } ( \mathrm { J } _ { \mathrm { i } } { + } 1 )$ 。 $\mathrm { \mathbf { A } _ { i j } ^ { \mathrm { _ { j } } } }$ 表示活动 $\mathrm { a _ { i j } }$ 的紧前活动集合，活动aij的开始时间需大于 $\mathbf { A } _ { \mathrm { i j } }$ 中活动完成时间的最大值；Li表示项目i的局部资源集合，Rii表示局部资源的可用量；G表示全局资源集合用 $\mathrm { R _ { g } }$ 表示其可用量；活动aij在任意时刻被执行时，需要rij及 ${ \bf r } ^ { \mathrm { g } } _ { \mathrm { i j } }$ 的局部和全局可更新资源；项目i的到达时间为 $\mathrm { S T _ { i } }$ ，其完工日期以项目i的 $\mathrm { a } _ { \mathrm { i } } ( \mathrm { J } _ { \mathrm { i } } { + } 1 )$ 活动的完工时间$\mathrm { F T _ { i } ( J _ { i } { + } 1 ) }$ 表示。 $\mathrm { F T _ { i } ( J _ { i } + l ) }$ 当超出截止日期时便会产生拖期成本TC(tardinesscost)，对于项目i其延期成本TCi为

$$
\mathrm { T C _ { i } = \left( F T _ { i } \left( J _ { i } + 1 \right) - S T _ { i } - c p l _ { i } \right) \times c _ { i } }
$$

其中：ci表示项目i单位延期成本， $\mathrm { { { S T } _ { i } + \mathrm { { c p l } _ { i } } } }$ 表示项目i的截至日期。而在考虑全局资源分配的多项目调度问题中，其目标为最小化各项目的总拖期成本TTC，即

$$
\bf { M i n } \sum _ { i = 1 } ^ { m } \bf { T C } _ { i }
$$

# 1.2多项目动态调度转换

然而在实际情况中活动的工期会受到环境的不确定性而产生变化服从一定的概率分布，此时多项目的静态调度问题转变为动态调度问题。由于串行调度尽早安排活动的原理，不适用于动态环境下多项目的调度，本文采用并行调度方式实现多项目的动态调度。在多项目的并行调度过程中t表示当前时间(多项目开工至今的时间且初始为0)，存在的集合包括已完工活动集合F、正在执行的活动的作业集合D、所有紧前活动均已完工的候选活动集合P、各项目未选择活动的集合U，多项目动态调度流程如下：

a)输入多项目调度信息包括各项目的规模、活动工期、优先级关系、局部与全局资源需求量，清空所有活动集合。

b)判断所有未添加至U集合的项目的开始时间STi是否小于等于t，若是则将对应项目的所有活动添加至U。

c)判断U中是否存在所有紧前活动均已完工的活动，若存在则将其添加至P中并从U中删除该活动，否则转至步骤c)。

d)若P为非空集合：则根据调度规则从P中选取优先级最高的活动并判断所选活动与D中活动是否存在资源冲突，若是则转至步骤d)否则将该活动从P中删除后添加至D中，并继续步骤c)；若P为空集合：转至步骤d)。

e)判断D中最早完工的一个或若干个活动，令t等于该些活动的完工时间将其从D中移除并添加至F中。

f)判断多项目的活动是否全部完成，若是则输出各项目的完工时间即 $\mathrm { F T _ { i } ( J _ { i } { + } 1 ) ( i { = } 1 , \ldots , m ) }$ 同时计算 $^ +$ TTC,否则转至步骤b)。

# 2 基于DDDQN的分布式多项目动态调度

多项目动态调度的问题是要从当前时刻各项目的可执行活动集中按照一定规则并在满足局部、全局资源约束的条件下选取优先执行的若干个活动进行作业，直到所有项目的活动均调度完成为止。这是一个连续的决策过程，因此可以将该问题转换为马尔可夫或半马尔可夫决策问题，即对问题的状态、动作、即时奖励进行定义。

# 2.1状态描述

状态的特征定义应能够充分反映当前时刻智能体所处环境的局部和全局特征，当进行决策时，智能体需根据当前时刻的环境特征作出左右决策。当问题的状态集为有限个时，可以采取数组或表格的方式进行表示，被称之为RL。然而在实际问题中往往具有较大或者连续的状态空间，此时需要采用深度神经网络函数逼近的能力，消除RL算法面临的“维度灾难问题”。在本文中多项目调度的状态特征包括三个 $\mathrm { m } \times$ $\operatorname* { m a x } ( \mathrm { J _ { i } } { + } 1 )$ 的矩阵， $\operatorname* { m a x } ( \mathrm { J _ { i } } { + } 1 )$ 表示所有项目活动规模中的最大值，三个矩阵分别为调度结果矩阵FN、活动作业矩阵DN、可执行活动矩阵PN。

FN是由每个项目中各活动的完工时间组成的矩阵，在输入网络前对其进行最大值标准化处理，初始赋值为零。

$$
F N = \left[ \begin{array} { c c c c c } { F T _ { \prime \prime } } & { \cdots } & { F T _ { \prime , \mathscr I _ { r \prime } - \mathscr I } } & { \cdots } & { F T _ { \prime , m a x ( \mathscr I _ { r } - \mathscr I ) } } \\ { \vdots } & { \vdots } & { \vdots } \\ { F T _ { \prime \prime } } & { F T _ { \prime , \mathscr I _ { r \prime } } } & { F T _ { \prime , m a x ( \mathscr I _ { r } - \mathscr I ) } } \\ { \vdots } & { \vdots } & { \vdots } \\ { F T _ { m , \mathscr I } } & { \cdots } & { F T _ { m , \mathscr I _ { m } - \mathscr I } } & { \cdots } & { F T _ { m , m a x ( \mathscr I _ { r } - \mathscr I ) } } \end{array} \right]
$$

DN表示各项目中每个活动当前所处状态，若正在执行则为1否则为0由于该矩阵中的数值取值为1或0因此不需要规范化。

$$
D N = \left[ { \begin{array} { l l l l l } { 1 } & { \cdots } & { 1 } & { \cdots } & { 0 } \\ { \vdots } & { } & { \vdots } & { } & { \vdots } \\ { 1 } & { \cdots } & { 0 } & { \cdots } & { 0 } \\ { \vdots } & { } & { \vdots } & { } & { \vdots } \\ { 0 } & { \cdots } & { 0 } & { \cdots } & { 0 } \end{array} } \right]
$$

PN 表示各项目中每个活动是否在当前时刻执行(即该活动的所有紧前活动均已完成)若是则为1否则为0，同理无须进行规范化。

$$
P N = { \left[ \begin{array} { l l l l l } { 0 } & { \cdots } & { 1 } & { \cdots } & { 0 } \\ { \vdots } & { } & { \vdots } & { } & { \vdots } \\ { 0 } & { \cdots } & { 1 } & { \cdots } & { 0 } \\ { \vdots } & { } & { \vdots } & { } & { \vdots } \\ { 0 } & { \cdots } & { 1 } & { \cdots } & { 0 } \end{array} \right] }
$$

考虑到深度学习原始输入中的特征提取，将三个特征矩阵看做高度为矩阵行数、宽度为矩阵列数的图像的三个不同通道，采用卷积输入的形式进行训练。

# 2.2动作定义

在多项目动态调度DRL模型中，动作空间是由许多单一规则的调度算法组成，通过强化学习算法针对不同状态选择合适的调度规则，以此克服单一规则的局限性。本文选用15个单一的调度规则，前7个为集中式调度规则，后8个为复合式调度规则。其中OFTi表示项目i在仅考虑局部资源约束下的最优调度方案，采用基于活动列表编码的改进灰狼算法求解所得。15个调度规则如表1所示，其中项目i表示已经到达且候选活动集非空的项目，j表示该项目中的候选活动。其中规则1\~6将各项目的候选活动集视为一个集合在选择活动的同时确定了该活动所在项目，规则7\~14则是优先先择项目p之后从项目p的候选活动集中选取活动。

# 2.3奖励函数

由于本文研究的分布式多项目动态调度的目标时实现总拖期成本最小，为了即时奖励能够准确评价动作进行如下设定：

$$
r _ { t } = \frac { \sum _ { i = 1 } ^ { m } \Bigl ( \sum _ { j \in F _ { i } ^ { t } } d _ { i j } - \sum _ { j \in F _ { i } ^ { t - 1 } } d _ { i j } \Bigr ) } { \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { J _ { i } + 1 } d _ { i j } } + \frac { \bigl ( \operatorname* { m a x } \{ F T _ { i } ^ { t - 1 } \} - \operatorname* { m a x } \{ F T _ { i } ^ { t } \} \bigr ) \times \omega _ { i } } { \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { J _ { i } + 1 } d _ { i j } }
$$

其中:max $\{ F T _ { i } ^ { i } \}$ 表示 $\mathrm { ~  ~ t ~ }$ 时刻项目i已完工活动的最大完工时间，$\omega _ { \mathrm { i } }$ 表示项目拖期成本。令

$$
u _ { t } = \frac { \sum _ { i = 1 } ^ { m } ( \sum _ { j \in F ^ { t } } d _ { i j } - \operatorname* { m a x } \left\{ F T _ { i } ^ { t } \right\} \times \omega _ { i } ) } { \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { J _ { i } + 1 } d _ { i j } }
$$

则 $\mathrm { \ u _ { 0 } = 0 }$ 此时算法的累计奖励计算如下：

$$
\begin{array} { r l } & { R = \sum _ { t } ^ { T } r _ { t } = \sum _ { t = 1 } ^ { T } u _ { t - 1 } - u _ { t } = \mathbf { u } _ { 0 } - \mathbf { u } _ { 1 } + \mathbf { u } _ { 1 } - \mathbf { u } _ { 2 } + \cdots + \mathbf { u } _ { \mathrm { T } - 1 } - \mathbf { u } _ { \mathrm { T } } = \quad } \\ & { \mathbf { u } _ { 0 } - u _ { T } = \frac { \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { J _ { i } } d _ { i j } - \operatorname* { m a x } \{ F T _ { i } ^ { \mathrm { T } } \} \times \boldsymbol { \omega } _ { i } } { \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { J _ { i } + 1 } d _ { i j } } } \end{array}
$$

因此累计奖励R最大化同等与ur最小，由于各活动的预计工期 $\mathrm { d _ { i j } }$ 均为常数，则ur最小同等与各项目完工工期与拖期成本乘积之和最小即TTC 最小。

Tab.1 Action space   

<html><body><table><tr><td>序号</td><td>名称</td><td>公式</td></tr><tr><td>1</td><td>SOF</td><td>job = min{dij}</td></tr><tr><td>2</td><td>LOF</td><td> job = max{dij}</td></tr><tr><td>3</td><td>MINLFT</td><td> job = min{LFTij]</td></tr><tr><td>4</td><td>MINOFT</td><td>job = min{OFTij ]</td></tr><tr><td>5</td><td>WMDD</td><td>job= min{max{LFTij-t,dij}/wi}</td></tr><tr><td>6</td><td>WMDD2</td><td>job = min{max{OFTij-t,dij}/wi }</td></tr><tr><td>7</td><td>MINSLK</td><td> job= min{LSij-max{ESij,t}}</td></tr><tr><td>8</td><td>MINLT+OFT</td><td>p= min{FT|-LFTi}, job =min{OFTpj }</td></tr><tr><td>9</td><td>MINLT+LFT</td><td>p = min{FTi-LFTi},job = min{LFTp}</td></tr><tr><td>10</td><td>MAXLT+OFT</td><td>p= max{FTi-LFTi},job=min{OFTj }</td></tr><tr><td>11</td><td>MAXLT+LFT</td><td>p = max{FT'-LFTi}, job= min{LFTp}</td></tr><tr><td>12</td><td>MINTC+OFT</td><td>p = min{wi}, job=min{OFTpj}</td></tr><tr><td>13</td><td>MINTC+LFT</td><td>p = min{wi}, job =min{LFTpj }</td></tr><tr><td>14</td><td>MAXTC+OFT</td><td>p = max{wi}, job= min{OFTpj }</td></tr><tr><td>15</td><td>MAXTC+LFT</td><td>p = max{wi}, job = min{LFTpj}</td></tr></table></body></html>

# 2.4探索利用策略

合理的探索利用策略能够使得智能体充分利用所学到的经验知识，同时保证能够探索新的策略行为。本文采用的探索利用策略为线性递减的贪婪策略，智能体的动作策略如下：

$$
a = \left\{ \begin{array} { l l } { { \arg \operatorname* { m a x } _ { a ^ { \prime } } Q ( a ^ { \prime } ) } } & { { \mathrm { ~ r a n d ( ) < \varepsilon ~ } } } \\ { { r a n d o m } } & { { \mathrm { ~ r a n d ( ) > \varepsilon ~ } } } \end{array} \right.
$$

其中:rand(为一个[0,1]的随机数，ε为贪婪策略的概率，服从以下分布：

$$
\mathbf { \mathcal { E } ^ { t } } = \operatorname* { m i n } ( \varepsilon _ { \operatorname* { m i n } } , \varepsilon ^ { t - 1 } \times \varepsilon _ { r a t e } )
$$

其中 $: \varepsilon _ { \mathrm { { m i n } } }$ 为ε的最小值， $\mathrm { \varepsilon } _ { \mathrm { \varepsilon } _ { \mathrm { r a t e } } }$ 为衰减率。

# 2.5DDDQN 算法流程

a)定义算法折扣因学习率 $\mathtt { a }$ ，经验池容量M，网络训练周期L，目标网络更新周期 $\mathrm { \Delta N }$ ，最小训练批量mini_batch，最大训练回合T_max，初始化Q网络与目标Q网络参数 $\phantom { - } \Theta , \phantom { - } \Theta ^ { , }$ ，输入多项目调度信息，令 step $\scriptstyle = 0$ 。

b)重置各项目调度计划信息并清除调度结果集，初始化多项目调度状态 So。

c)根据当前状态state依据探索利用策略选择当前决策点智能体的action选择的优先规则调度算法，进行多项目调度流程中的步骤 ${ \mathsf { b } } ) { \sim } { \mathsf { e } } ,$ L

d)根据式(6)计算当前时刻的即时奖励值reward与下一时刻状态 state_以及训练是否结束标志done(结束为 True,未结束为False)，将{state,action,reward,state_,done}五元组储存至经验池中。

e)判断是否满足网络参数更新条件，若是则根据TD 误差对网络参数进行更新，否则转至步骤f)。

f)判断所有项目是否全部完工，若是则令 $\mathrm { s t e p } + = 1$ 转至步骤g)，否则转至步骤c)。

g)判断是否达到最大训练回合即 step $\scriptstyle \mathbf { \alpha } = \mathbf { T }$ _max，若是则停止训练并将Q网络参数保存本地，否则转至步骤 b)。

算法1基于DDDQN 的多项目动态调度伪代码

1初始化最小训练批量mini_batch,step-sizen，经验池容量M，网络训练周期L和目标网络更新周期N，最大训练周期T_max，动作选择次数 $\mathrm { \ n u m { = } } 0$ 。

2随机初始化Q网络参数0并将其参数复制给目标Q'网络 $\varTheta ^ { \ast }$   
3 forstep $\ O _ { \cdot = 1 }$ to M do  
4 重置多项目调度信息、清除调度结果，初始化调度状态s1。  
5 While多项目活动未全部完工then  
6 基于探索利用策略选择动作及对应的优先规则， $\mathrm { \ n u m ^ { + = 1 } }$ 。  
7 根据最大优先规则执行多项目调度中的步骤2、3、4直到  
产生资源冲突。  
8 计算当前奖励rt和下一状态 $\mathbf { s } { \mathrm { t } } + 1$ ，判断done 是否为True。  
9 将(st,at,rt,st+1,done）储存至经验池 $\mathbf { \delta M }$ 。  
10 i $\mathrm { \Delta f \ n u m ~ \% ~ L = = 0 }$ and num>mini_batch then  
11 从经验池中随机选取mini_batch个(st,at,rt,s $^ { + 1 }$ ,done)。  
12 for $\mathbf { j } = 1$ to mini_batch do  
$y _ { j } = \left\{ { r _ { j } } \atop { r _ { j } + \gamma Q ^ { \prime } \left( s _ { j + 1 } , \mathrm { a r g m a x } _ { a } \ : Q ( s _ { j + 1 } , a ; \theta ) , \theta ^ { \prime } \right) }  \right.$ if done $\ c =$ True  
13 令yj  
otherwise  
14 end for  
15 更根据y与 $Q ( \mathrm { s } , \mathrm { a } ; \boldsymbol { \theta } )$ 采用反向传播更新Q网络参数0  
16 end if  
17 if num $9 \%$ $\scriptstyle \mathbf { N } = = 0$ then  
18 将Q网络的参数θ复制给目标Q网络 $\Theta ^ { \prime } \gets \Theta$   
19 end if  
20 break  
21 end for

# 3 仿真实验

为验证所搭建仿真环境的有效性以及DDDQN算法解决对分布式多项目动态调度问题的有效性，选取 MPSPLIB 标准库中的MP305和MP902问题集进行测试，各问题集均含有5个算例具体信息如表2所示。实验在配备Windows1064位系统、24GB运行内存、处理器为AMDR74800H的笔记本上搭建tensflow2.0环境下运行。

表1动作空间  
表2问题集的具体信息  
表3常见工期分布  

<html><body><table><tr><td>信息</td><td>MP30_5</td><td>MP90_2</td></tr><tr><td>项目数</td><td>5</td><td>2</td></tr><tr><td>活动数</td><td>30</td><td>90</td></tr><tr><td>问题规模</td><td>150</td><td>180</td></tr><tr><td>平均资源利用系数</td><td>0.82</td><td>0.57</td></tr></table></body></html>

同时多项目中活动工期服从常见概率分布类型如表3所示。

Tab.2Specific information of question set   
Tab.3Common duration distribution   

<html><body><table><tr><td>名称</td><td>分布类型</td><td>区间</td><td>方差</td></tr><tr><td>U1</td><td>均匀分布</td><td>[d-√d,dij+d]</td><td>di/3</td></tr><tr><td>U2</td><td>均匀分布</td><td>[0,2dij]</td><td>dij2/3</td></tr><tr><td>EXP</td><td>指数分布</td><td>dije-dj</td><td>di²</td></tr><tr><td>B1</td><td>β分布</td><td>α=dij /2-1/3,β=2α</td><td>dij/3</td></tr><tr><td>B2</td><td>β分布</td><td>α=1/6,β=2α</td><td>dij2/3</td></tr></table></body></html>

# 3.1参数分析

在强化学习中超参数对于网络学习性能至关重要，目前对于超参数的确定一般依靠人工经验和随机搜索。为确定最优的超参数组合，本文选用算例MP30_5_5在工期为U1分布类型对模型的网络结构、速率rate、目标网络更新周期N、最小训练批量mini_batch、折扣率 $\gamma$ 等超参数进行了灵敏度分析，同时在对某一超参数进行灵敏度分析时其他超参数的取值均保持不变。图1为DRL模型的超参数在不同取值下的累计奖励迭代图，通过训练过程中累计奖励的变化来判断该超参数取值的效果。以图1(a)为例，其横坐标为模型的训练次数，纵坐标为累计奖励的变化曲线。从该图中可以看出不同网络结构能够影响算法的性能，当网络结构取值为红线所示时算法的性能最佳，将其确定为本文模型的网络结构，此时其他参数均保持不变。同理可得模型的其他超参数的取值，最终确定超参数策略如表4所示。

图1(a)表示五种不同卷积层对算法的影响，每一行表示滤波器数量和内核大小其中步幅均为(1，1)。由图中可以看出第4种网络结构相对于其他四种，能够为算法带来更有效的性能提升。图1(b)表示不同的学习率对于算法的影响，可以看当rate较低时算法训练性能最差，而rate较高时算法性能有所下降，因此本文选取学习率为0.0001。图1(c)表示不同的目标网络更新周期对算法的影响，从图中可以看出当$N = 1 0 0$ 周期的训练性能最好。图1(d)可以看出最小训练批量对算法的影响较小，当mini_batch为64时算法的性能会有所下降，当minibatch为256或128时算法的收敛趋势较为稳定，但由于256 需要更多的训练时间因此选用128。图1(e)表示不同的折扣系数对于算法的影响，同理当 $\gamma$ 较低时会降低算法性能，当γ较高时算法收敛较慢，选取0.99折扣率。

![](images/224b42e0e438ab99378558bfca80ebb1d0bb988f08017e2ad60e5a494ccadbf0.jpg)

![](images/9d040e3f3ca3e0733b93de3a8e0b9288efe4ec3fdccb58fd8e6adf19d5b846f0.jpg)  
(a)网络结构

![](images/f9ae3b9ad266f9cf05d7a53bf7e03e0f8fe859909cc05186ba3273192d941db6.jpg)  
(b)学习率

![](images/bf17ef4f2fa049428f783304a572eac86dbb32336fbe2ab28e0660b15e579d9a.jpg)  
(c）最小训练批量mini_batch   
(d）目标网络更新周期N

![](images/ddf02b298ef550658138603ef408a099d7fcfeb6a5cd515913abb21ef65250a1.jpg)  
图1各超参数的验证结果

# 3.2DRL模型求解问题集

本节将本文提出的DRL模型运用至两种问题集的10个算例上，实验分为模型训练阶段和测试阶段。在训练阶段，将DRL 模型分别在不同工期分布下的10个算例分别进行5000次仿真训练，模型的超参数取值策略如表4所示，并将各算例训练完成的模型保存本地。在模型的测试阶段，将10个算例所训练完成的10个模型分别在对应算例的5种工期分布下进行50次仿真调度求得平均的TTC。

表4超参数组合  
Tab.4Hyperparameter combinations   

<html><body><table><tr><td>超参数</td><td>取值</td></tr><tr><td>T_max</td><td>5000</td></tr><tr><td>Emin</td><td>10-5</td></tr><tr><td>£rate</td><td>0.9999</td></tr><tr><td>rate</td><td>10-3</td></tr><tr><td>M</td><td>105</td></tr><tr><td>N</td><td>100</td></tr><tr><td>mini_batch</td><td>128</td></tr><tr><td>Y</td><td>0.99</td></tr><tr><td>L</td><td>20</td></tr></table></body></html>

图2为算例MP3055在五种工期分布下的训练过程，其中横坐标为多项目的总拖期成本，纵坐标为模型的训练回合。可以看出对于方差相对较小的U1、B1的TTC迭代曲线处于最下方且波动最小；对于方差中等的U2、B2的TTC迭代曲线处于中间位置且波动中等；对于方差较大的Exp 的TTC迭代曲线处于最上方位置且波动较大，表明总拖期成本的期望水平随着活动工期不确定程度的增加而增大。

![](images/4ed93f6d1ceb3da10104de2a9cb26edd068916b5e5ad7b8386d045a76e318d37.jpg)  
Fig.1Verification results of each hyperparameter   
图2不同工期分布下的TTC迭代过程  
Fig.2TTC iteration process under different duration distributions

对于算例MP30_5_5训练完成的模型的测试阶段，将训练完成模型与动作空间中15种单一调度规则在对应工期分布下分别进行50次仿真调度求得平均的TTC如图3所示。由图3可以看出DRL算法克服单一规则的短视性，在动态环境中获得更好的调度结果。进一步的选取15种规则在5种工期分布下表现最好的规则与DRL模型所得的结果进行对比并以改进率improve作为评价指标，如式(11)所示。强化学习改进率如表5所示。

![](images/8e56c09d7d471d0e547f1e7b213aad8218c3bbc41c36e2d368a33b72a26ba333.jpg)  
图3不同工期分布下各动作的TTC

表6为优先规则算法和DRL模型调度在完成50次多项目调度过程的运行时间。可以看出与优先规则调度算法相比，训练后的模型可以根据环境的当前状态快速作出最优调度决策，速度相当于优先规则算法。

MP30_5与 $\mathrm { { M P 9 0 } } \_ { 2 }$ 问题集在不同工期分布下50次调度的平均TTC值如表7所示。对比文献[9]，其中 $ { \mathrm { M P } } 3 0 \_ 5$ 的在U1分布下的结果本文较差，而MP90_2的结果本文较优。

$$
i m p r o \nu e = \frac { B e s t - a g e n t } { B e s t } \times 1 0 0 \%
$$

Tab.5Improvement rate of reinforcement learning   

<html><body><table><tr><td>分布</td><td>agent</td><td>Best rule</td><td>Improve(%)</td></tr><tr><td>U1</td><td>4286.25</td><td>5455.55</td><td>21.43</td></tr><tr><td>U2</td><td>4890.75</td><td>5952.62</td><td>17.84</td></tr><tr><td>Exp</td><td>5825.32</td><td>7219.41</td><td>19.31</td></tr><tr><td>B1</td><td>4319.49</td><td>5632.16</td><td>23.31</td></tr><tr><td>B2</td><td>4889.91</td><td>6102.43</td><td>19.87</td></tr></table></body></html>

表6单一规则和DRL算法调度时间

表5强化学习改进率  

<html><body><table><tr><td>Scheduling time</td><td>MP30_2</td><td>MP30_5</td><td>MP30_10</td></tr><tr><td>Single rule</td><td>2.24</td><td>2.64</td><td>3.16</td></tr><tr><td>DRL</td><td>2.58</td><td>3.04</td><td>3.98</td></tr></table></body></html>

表7问题集不同分布下DRL结果

Tab.6Single rule and DRL algorithm scheduling time   
Tab.7DRL results under different distributions of problem sets   

<html><body><table><tr><td>TTC</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td></tr><tr><td>MP30_5</td><td>1467.57</td><td>1748.06</td><td>1422.57</td><td>1783.27</td><td>2279.03</td></tr><tr><td>Mp90_2</td><td>1001.58</td><td>1524.73</td><td>1025.81</td><td>1439.44</td><td>2497.44</td></tr></table></body></html>

# 3.3 不确定到达时间

在实际情况中项目的到达时间往往会因局部资源的缺乏而与预计的到达时间产生偏差。因此本节研究了DRL模型在项目到达时间不确定环境下对多项目总拖期成本的影响，其中项目活动的工期为常工期分布，项目到达时间服从以下分布：

$$
\begin{array} { l } { \mathbf { a } = 0 } \\ { \mathbf { a } = 1 } \\ { \mathbf { a } = 2 } \\ { \mathbf { a } = 3 } \\ { \mathbf { a } = 4 } \end{array}
$$

式(12)中的分布类型特征与3.2工期分布相同；a为[0,4]的随 $\mathrm { T C _ { i } = \big ( F T _ { i } \left( J _ { i } + 1 \right) - S T _ { i } - c p l _ { i } \big ) \times c _ { i } }$ 机整数，例如当 $\scriptstyle \mathbf { a } = 0$ 时表示项目i的到达时间为服从U1分布的随机数。

多项目到达时间不确定所产生的状态组合小于不确定工期情况，因此DRL模型的训练回合设置为5000次且模型的超参数组合与3.2节相同。图4为模型训练过程的总拖期成本TTC的变化曲线，在训练的过程中TTC随着训练的回合的增加不断减少并趋于稳定，表明模型进行了有效的训练。

同时现有文献并未有对不确定项目到达时间的DRCMPSP的研究，因此将训练完成的模型进行100次仿真实验后所得的平均TTC值3022.01，与15种规则中最优规则的TTC值4973.75进行对比，其改进率为 $6 4 . 6 \%$ 。

![](images/1d307954a9a91a293b2249c4b7bdb118661fcc91a1bf15e7213e8e4a1313bbf7.jpg)  
Fig.3TTC of each action under different duration distributions   
图4项目到达时间不确定  
Fig.4Uncertain arrival time of the project

# 4 结束语

本文首次将深度强化学习运用至多项目调度问题，在此基础上提出基于DRL的分布式多项目动态调度模型，以实现随机工期下分布式多项目调度问题总拖期成本最小化的目标。并搭建了智能体交互的仿真环境，以算例MP305和MP902问题集中的算例进行仿真实验，一方面对模型的超参数取值策略进行灵敏度分析，另一方面对通过算例对模型进行训练和测试。结果表明本文所提出的 DRL 模型对于实现分布式多项目在随机环境下的动态调度有一定优势，训练好的模型在决策阶段的作出策略的速度与优先规则相差无几，同时能够有效降低随机分布式多项目调度所需的总拖期成本，拓展了深度强化学习在随机性项目调度问题上的运用。

# 参考文献：

[1]LovaA,Tormos P.Analysis of Scheduling Schemes and Heuristic Rules Performance in Resource-Constrained Multiproject Scheduling [J]. Annals of Operations Research,2001,102(1-4):263-286.   
[2]Lee YH,Kumara S,Chatterjee K.Multi-agent based dynamic resource scheduling for distributed multiple projects using a market mechanism [J].Journal of Intelligent Manufacturing,2003,14(5): 471-484.   
[3]Davari M,Demeulemeester E.Important classes of reactions for the proactive and reactive resource-constrained project scheduling problem [J].Annals of Operations Research,2019,274(1-2):187-210.   
[4]Satic U,Jacko P, Kirkbride C. Performance evaluation of scheduling policies for the dynamic and stochastic resource-constrained multiproject scheduling problem [J]. International Journal of Production Research,2020,60 (4):1411-1423.   
[5]Wang Yanting,He Zhengwen, Kerkhove L P,et al. On the performance of priority rules for the stochastic resource constrained multi-project scheduling problem[J].Computers & Industrial Engineering,2O17,114 (DEC.): 223-234.   
[6]Chen Haojie,Ding Guofu, Zhang Jian,et al.Research on priority rules for the stochastic resource constrained multi-project scheduling problem with new project arrival [J].Computers & Industrial Engineering,2019, 137 (2):106060-.   
[7]Song Wen,Xi Hui,Kang Donghun,et al.An Agent-based Simulation System forMulti-Project SchedulingunderUncertainty[J].Simulation Modelling Practice and Theory,2018,86(11):187-203   
[8]TosselliL,Bogado V,E Martinez.Arepeated-negotiation game approach to distributed (re） scheduling of multiple projects using decoupled learning[J]. Simulation Modelling Practice and Theory,2019,98(4): 101980.   
[9]刘东宁，徐哲．基于多优先规则启发式的分布式多项目随机调度 [J]．系统工程理论与实践,2021,41(12):3294-3303.(Liu Dongning, Xu Zhe.A stochastic scheduling for distributed multi-project with multiPR heuristic [J/OL]. Systems Engineering-theory & Practice,41(12): 3294-3303.)   
[10]韩忻辰，俞胜平，袁志明，等．基于Q-learning 的高速铁路列车动态 调度方法[J].控制理论与应用，2021,38(10):1511-1521.(Han Xincheng，Yu Shengping,Yuan Zhiming，et al.High-speed railway dynamic scheduling based on Q-learning method [J]. Control Theory & Applications,2021,38 (10): 1511-1521.)   
[11]Waschneck B,Reichstaller A,Belzner L,et al.Deep reinforcement learning for semiconductor production scheduling[C]//SEMI Advanced Semiconductor Manufacturing Conference (ASMC) .2018.   
[12] Lin Chuncheng，Deng Derjiunn，Chih yenling， et al. Smart Manufacturing Scheduling with Edge Computing Using Multi-class Deep Q Network [J].IEEE Trans on Industrial Informatics,2019,15(7): 4276-4284.   
[13] Liu Chienliang，Chang Chuanchin，Tseng C J.Actor-Critic Deep Reinforcement Learning for Solving Job Shop Scheduling Problems [J]. IEEE Access,2020,PP(99): 1-1.