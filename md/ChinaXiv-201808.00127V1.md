# 基于差分进化的复杂软件系统动态可靠性分配

张世金1，张国富1,2,3，苏兆品1,2,3，岳峰1,2,3(1.合肥工业大学 计算机与信息学院，合肥 230601；2.工业安全与应急技术安徽省重点实验室，合肥 230601；3.安全关键工业测控技术教育部工程研究中心，合肥230601)

摘要：现有关于复杂软件系统可靠性分配的研究均基于结构固定的软件系统，而实际情况中软件系统结构往往不固定。针对这一矛盾，构建复杂软件系统动态可靠性分配优化模型，并基于差分进化设计复杂软件系统动态可靠性分配算法。在系统结构发生变化时，首先基于D-S证据理论对系统中各模块的全局权重重新进行评估，并考虑变化前后系统的关联性，在差分进化生成初始种群时保留了部分历史解。最后，通过仿真实验分析验证了所提方法的有效性。

关键词：复杂软件系统；动态可靠性分配；差分进化；D-S证据理论；保留历史解中图分类号：TP311.5 doi:10.3969/j.issn.1001-3695.2018.03.0265

# Dynamic reliability allocation of complex software system based on differential evolution

Zahng Shijin1, Zahng Guofu1,2,3, Su Zhaopin1,2,3, Yue Feng1, 2, 3 (1.Schoolof Computer& Information,Hefei Universityof Technology，Hefei 23060l，China;2.Anhui Province Key Laboratoryof IndustrySafety&EmergencyTechnology，Hefei 230601,China;3.Enginering Research Centerof Safety Critical Industrial Measurement & Control Technology for Ministry of Education,Hefei 230601,China)

Abstract:Existingresearch onthe reliabilityalocationofcomplex software system just basedon software systems whose structure werefixed,butthe structureofsoftwaresystems always change inpractice.Forthiscontradiction,this paperpresents a dynamic reliability alocation optimization model of complex software system.Atthe same time,developing a dynamic reliabilityallocation algorithmofcomplexsoftware system basedondiferential evolution.Specificaly，when thesystem structure changes,we firstestimate the parametersof each module accordingto the Dempster-Shafer evidencetheory.Next, takingaccountof therelevanceof thesystembeforeandafterthechange,weretainsome historical solutions inthe previous searchtoformpartoftheinitial population indiferential evolution.Finally，verifyingtheefctivenessof theproposed approach by simulation experiments.

Keywords:complex software system；dynamicreliabilityallcation；diferential evolution;Dempster-Shafer envidence theory; reserve historical solutions

# 0 引言

可靠性设计一直是软件工程领域一个非常重要和活跃的方向。随着大规模复杂软件系统不断在电力系统、铁路运输、航空航天、国家安全等安全关键领域内的广泛应用，对软件系统的可靠性的要求越来越高，软件可靠性分配问题也越来越受到研究者和设计者的关注[1-3]。但是，软件可靠性无法精确测量，只能通过对软件系统进行测试来度量其可靠性，对于软件开发工程师来说，为达到最优的可靠性，在开发的早期阶段完成软件可靠性分配是软件工程的一个重要环节[3]。

在可靠性分配问题建模方面，Zahedi等人[4以成本为约束构建软件系统可靠性最大化模型。Leung[56根据操作剖面定义软件可靠性函数，并考虑到每个客户的软件操作剖面，同时满足成本预算和软件质量要求等实际约束条件。Kapur等人[7将系统冗余与预算约束相结合，使系统可靠性最大化，而且还考虑了可供不同模块使用的替代品之间的兼容性问题。Roy 等人[8]针对多功能多用户数字中继系统设计了一种软件可靠性分配方案以提高输电线路故障的检测、分类和定位的可靠性。Chatterjee等人[提出了一种结合用户视点的软件可靠性分配模型，为了将用户需求和偏好纳入软件的技术设计和可靠性，建立了一个系统层次结构，将用户的系统视图与软件管理人员和程序员结合起来。

在可靠性分配问题求解方面，韩冰青等人[10]基于模拟退火遗传算法，将软件系统的可靠性分配问题表达为带约束条件的组合优化问题，并采用模拟退火的适应度拉伸方法和多点交叉操来提高解的质量。徐悦等人[1基于罚函数的混合分布估计和自适应交叉差分进化[12]（differentialevolution,DE）的优化算法对顺序、并发、循环、容错四种体系结构的复杂软件可靠性进行评估。Sangeetha 等人[13]利用多目标遗传算法求解考虑可靠性、成本和进度的多目标可靠性分配问题。然而，上述已有工作只是针对单一软件系统结构，在一些复杂软件系统中往往包含多个软件。而且，上述工作大都采用层次分析法预测各模块的参数值，没有考虑实际工程中的不确定性和不完全性。为此，Yue 等人[14基于复杂软件系统层次结构，构建成本约束的系统可靠性最大化模型，并利用D-S证据理论[15]估计各模块的参数值，并基于差分进化搜索最优可靠性分配方案。

不过，上述已有工作都是考虑静态场景下的软件可靠性分配问题。需要注意的是，在实际的软件开发过程中，由于用户需求的变化或者开发人员的程序改进，导致软件系统的结构往往并不固定，变化之前建立的可靠性分配方案显然不能再适应变化后的系统结构。而根据现有的结构完全重新优化新的可靠性分配方案又显得费时费力。针对这一情景，本文首先提出一种针对复杂软件系统的动态可靠性分配模型，模拟复杂软件系统结构会发生变化的可靠性分配问题，并基于D-S证据理论和DE 算法求解这一动态优化问题，同时在优化时考虑历史解以提高最终解的质量，最后通过仿真实验验证了所提方法的有效性。

# 1 问题描述

通常，复杂软件系统层次结构[14是自上而下进行的，如图1所示。

第一层为软件层，是用户对每个软件 $S _ { \iota }$ 可靠性 $R _ { l } ( l = 1 , \cdots , p )$ 的总体评估。第二层为功能层， $F _ { k } ( k = 1 , \cdots , f )$ ，表示每一软件都存在若干功能。第三层为程序层， $P _ { i } ( i = 1 , \cdots , n )$ ，表示每一功能都由若干程序实现。第四层为模块层， $M _ { j } ( j = 1 , \cdots , m )$ ，表示每一程序都包含若干模块这里每个模块是独立的，且只将可靠性指标分配到模块层为止。

![](images/e7c3495775e9898b09bd3ccc988631df67a598556cfe8685b9332104de7d4ac7.jpg)  
图1复杂软件系统层次结构

通常，用户在软件中执行各种功能的可靠性程度通过“软件实用性”来衡量。在上述层次结构中，程序层既反映了用户对软件可靠性的观点，又反映了程序员的建议，因此，通常从程序层的视角去研究复杂软件系统的实用性 $U$ 。

$$
U = \sum _ { i = 1 } ^ { n } w _ { P _ { i } } r _ { P _ { i } }
$$

其中： $w _ { P _ { i } }$ 为程序 $P _ { i }$ 的全局权重， $r _ { P _ { i } }$ 为程序 $P _ { i }$ 的可靠性。由于模块是独立的单元，所以 $r _ { P _ { i } }$ 可根据下式计算：

$$
r _ { P _ { i } } = \prod _ { M _ { j } \in P _ { i } } r _ { M _ { j } }
$$

其中： $r _ { M _ { j } }$ 为模块 $\boldsymbol { M } _ { \flat }$ 分配到的可靠性。此外，每个模块 $\boldsymbol { M } _ { \flat }$ 有一个全局权重 $w _ { M _ { j } }$ 。

复杂软件系统动态可靠性分配问题即是在一定的预算约束下，完成复杂软件系统中各模块的可靠性分配，使得系统的实用性达到最大。

$$
\operatorname* { m a x } U = \sum _ { i = 1 } ^ { n } \left( w _ { P _ { i } } \prod _ { j = 1 \land M _ { j } \in P _ { i } } ^ { m } r _ { M _ { j } } \right)
$$

s.t.

$$
0 \leq r _ { M _ { j } } \leq 1 , j = 1 , \cdots , m
$$

$$
a _ { M _ { j } } + b _ { M _ { j } } r _ { M _ { j } } \le w _ { M _ { j } } \sum _ { l = 1 } ^ { p } B _ { s _ { l } } , j = 1 , \cdots , m
$$

$$
\sum _ { j = 1 \land M _ { j } \in S _ { l } } ^ { m } \left( a _ { M _ { j } } + b _ { M _ { j } } r _ { M _ { j } } \right) \leq B _ { S _ { l } } , l = 1 , \cdots , p
$$

在上述模型中， $m$ 的值是动态变化的，即模块数是变化的。目标函数 $U$ 为整个复杂软件系统的整体实用性，是各模块可靠性 $r _ { M _ { j } }$ 的函数。其中， $r _ { M _ { j } }$ 是唯一的未知变量，因为 $m$ 的值是动态变化，所以变量集 $r _ { M _ { 1 } } , \cdots , r _ { M _ { j } } , \cdots , r _ { M _ { m } }$ 也是动态变化的。约束条件式(4)是对模块 $\boldsymbol { M } _ { \flat }$ 可靠性的约束;约束条件式(5)是对模块 $\boldsymbol { M } _ { \flat }$ 成本的预算约束，其中 $a _ { M _ { j } }$ 为模块 $\boldsymbol { M } _ { \flat }$ 达到可靠性 $r _ { M _ { j } }$ 的固定开销成本， $b _ { M _ { j } }$ 为可变成本，即 $\boldsymbol { M } _ { \flat }$ 提高一个单位的可靠性所要增加的成本， $B _ { s _ { i } }$ 为软件 $S _ { \iota }$ 的预算成本， $w _ { M _ { j } } \sum _ { l = 1 } ^ { p } B _ { S _ { l } }$ 为模块 $\boldsymbol { M } _ { \flat }$ 的最大预算。约束条件式(6)是对软件 $S _ { \iota }$ 的成本约束。

# 2 动态可靠性分配算法

# 2.1差分进化

DE 是一种基于群体的启发式搜索算法[2]。主要的进化流程包括变异、交叉和选择。

DE算法通过差分策略实现个体变异，常见的差分策略是随机选取种群中两个不同的个体，将其向量差缩放后与原始个体 $\boldsymbol { \cal X }$ 进行向量合成生成一个新的变异个体 $V$ 。

$$
V = X + F { \bigl ( } X _ { r _ { 1 } } - X _ { r _ { 2 } } { \bigr ) }
$$

其中： $X _ { r _ { 1 } }$ 、 $X _ { r _ { 2 } }$ 是两个随机选取的与 $X$ 不相同的个体， $F \in \left( 0 , 2 \right)$ 为缩放因子。

交叉操作的自的是从原始个体 $\boldsymbol { \underline { X } }$ 和变异个体 $V$ 中根据交叉概率 $C R$ 交换基因值产生新的试验个体 $U$ 。如果随机数rand $\left( 0 , 1 \right) \leq C R$ ， $U = V$ ；否则 $U = X$ 。再通过适应度函数对试验

个体 $U$ 进行评价，选择较优的个体组成下一代新种群。如果 $U$ 的适应度值优于 $\scriptstyle { \frac { } { X } }$ ，则 $X = V$ ；否则 $\boldsymbol { \cal X }$ 保持不变。

# 2.2 D-S证据理论

D-S证据理论[15]通过合并多重证据从而做出决策，对推理进行合理的解释而达到一定程度的信念。Yue 等[14]基于D-S证据理论来估计每个程序和模块的全局权重。在本文中，我们仍然采用这种方法对变化后的系统结构中各个程序和模块的全局权重重新进行估计。

设 $U _ { x }$ 是变量 $\boldsymbol { \cal X }$ 可能值的样本空间，则称 $U _ { x }$ 为 $\boldsymbol { \cal X }$ 的一个识别框架。 $\boldsymbol { \cal X }$ 的基本概率分布函数 $U$ 满足： $\mu : 2 ^ { \upsilon _ { x } }  [ 0 , 1 ]$ ;（204 $\mu ( \emptyset ) = 0$ ； $\sum _ { A \in 2 ^ { U _ { X } } } \mu ( A ) = 1$ 。其中， $2 ^ { U _ { x } }$ 为 $U _ { x }$ 的所有非空子集的集合， $\mu ( A )$ 表示对 $A$ 的精确信任度，为集合 $A$ 的基本概率数。当来自不同数据源的数据对相同的识别框架提供不同的评估信息时，可用如下的合成规则被用于信息融合。

设 $\mu _ { 1 } ( B )$ 和 $\mu _ { 2 } ( C )$ 为同一识别框架的两个不同的证据，则

$$
\mu _ { 1 2 } ( A ) = \left\{ \begin{array} { l l } { 0 , A = \emptyset } \\ { \displaystyle \sum _ { B \cap C } \mu _ { 1 } ( B ) \cdot \frac { \mu _ { 2 } ( C ) } { ( 1 - K ) } , A \neq \emptyset } \end{array} \right.
$$

$$
K = \sum _ { B \cap C = \emptyset } \mu _ { 1 } ( B ) \cdot \mu _ { 2 } ( C )
$$

其中： $\scriptstyle A = B \cap C$ ； $\kappa$ 为归一化常数，用来计算所有非空集合的基本概率之和，可以避免在组合时将非零的概率赋给空集。通过$K$ 可以把空集所丢弃的信度按比例分配到非空集上，有效的表示了证据间的冲突程度，其值越大说明证据之间的冲突越大。

在本文中，首先根据各个软件的预算 $B _ { s _ { i } }$ 确定各个软件的全局权重 $w _ { S _ { l } } = \spadesuit \sum _ { l = 1 } ^ { B _ { S _ { l } } } B _ { S _ { l } }$ ∑Bs；然后让用户和程序员根据每个功能、程序、模块在各自所属的软件、功能、程序中的重要程度，给出每个功能、程序、模块在各自的软件、功能、程序中的一个局部权重，即图1中的每条线上都有一个局部权重值。然后根据文献[14]的计算和合成方法给出每个程序、模块在整个复杂软件系统中的全局权重 $w _ { P _ { i } }$ 和 $w _ { M _ { j } }$ 。值得注意的是，当模块数发生变化时，只需要根据先前的每个程序的全局权重（并没有发生变化）、每个模块新的局部权重（发生了变化）来估计每个模块的全局权重。

# 2.3算法描述

如图2所示，在优化过程中，如果系统结构发生变化，首先利用D-S证据理论基于每个模块新的局部权重估计各模块新的全局权重，然后以式(3)为适应度函数，以式(4)\~(6)为约束条件，基于DE 算法搜索新系统结构下的最优可靠性分配方案。特别地，在初始化种群时，根据个体的适应度值排序，保留历史搜索中最好的 $7 5 \%$ 的个体作为当前优化的部分初始解，其余$2 5 \%$ 的个体仍然根据约束条件随机初始化。

![](images/b94339c95d5614dbe2cb5f2fe519f310dcf4f8fce3e1504bc0f8ee6bc986edb3.jpg)  
图2动态可靠性分配算法流程图

# 3 仿真实验与分析

# 3.1实验环境

为了验证本文方法的有效性，在优化过程中设计了一个复杂软件系统，该系统包含 $t _ { 1 }$ 、 $t _ { 2 }$ 和 $t _ { 3 }$ 三个状态。三种状态下的系统层次结构和各个单元的局部权重如图3所示。

![](images/a3ccda3032d63369ab4f22649446b09da877b75f4717ac5d66ee80c3c9b733e5.jpg)  
图3各状态下的系统层次结构和局部权重

$S _ { 1 }$ 、 $S _ { 2 }$ 和 $S _ { 3 }$ 的预算分别为250、450和300。状态 $t _ { 2 }$ 相比于状态 $t _ { 1 }$ 的变化在于程序 $P _ { 1 }$ 与 $P _ { 2 }$ 新增了一个模块 $M _ { 8 }$ ，程序 $P _ { 5 }$ 新增了一个模块 $M _ { 9 }$ 。相应的 $P _ { 1 }$ 、 $P _ { 2 }$ 和 $P _ { 5 }$ 关联的模块的权重也发生了改变，而 $P _ { 3 }$ 和 $P _ { 4 }$ 包含的模块的局部权重没有变化。状态 $t _ { 3 }$ 相比于状态 $t _ { 2 }$ 的变化在于程序 $P _ { 1 }$ 新增了一个模块 $M _ { 1 2 }$ ，程序 $P _ { 3 }$ 新增了两个模块 $M _ { \mathfrak { n } }$ 和 $M _ { 1 1 }$ ，程序 $P _ { 4 }$ 新增了一个模块 $M _ { \mathfrak { n } 1 }$ 。相应的 $P _ { 1 }$ 、

$P _ { 3 }$ 和 $P _ { 4 }$ 关联的模块的局部权重发生了改变，而 $P _ { 2 }$ 和 $P _ { 5 }$ 包含的模块的局部权重没有变化。

此外，在DE 算法中，交叉概率 $C R = 0 . 5$ ，缩放因子 $F = 0 . 9 4$ ，种群规模为60。

# 3.2实验结果

基于D-S证据理论得到程序层的全局权重为$w _ { P _ { i } } = \{ 0 . 2 6 2 8 , 0 . 0 2 8 4 , 0 . 5 1 0 6 , 0 . 0 5 8 2 , 0 . 1 4 \}$

三种状态下模块层的全局权重如表1所示。

表1各状态下的模块层的全局权重  

<html><body><table><tr><td>状态</td><td>WM</td></tr><tr><td rowspan="2">t1</td><td>{0.2239,0.0353,0.4007,0.2165,0.0619,</td></tr><tr><td>0.0359,0.0256}</td></tr><tr><td rowspan="2">t</td><td>{0.1962,0.0329,0.3977,0.2168,</td></tr><tr><td>0.049,0.036,0.0257,0.0329,0.0128]</td></tr><tr><td>t</td><td>{0.0997,0.0293,0.2364,0.1418,0.0436.0.032， 0.0228.0.0293,0.0114,0.1421,0.1368,0.0748}</td></tr></table></body></html>

图4给出了DE 在状态 $t _ { \mathrm { { l } } }$ 下分别迭代10次、20次和30次后系统结构变为状态 $t _ { 2 }$ 后的优化结果。其中，“纯静态优化”指的是DE 直接在状态 $t _ { 2 }$ 下搜索；“考虑历史解”指的是在系统结构变为状态 $t _ { 2 }$ 后，DE将 $t _ { \mathrm { { l } } }$ 状态下的部分历史解作为初始种群来搜索；“不考虑历史解”指的是在系统结构变为状态 $t _ { 2 }$ 后，DE直接随机生成初始种群来搜索。“考虑历史解”和“不考虑历史解”均是属于动态优化。从图4可以看出，考虑历史解要比不考虑历史解明显收敛的快，说明保留前一状态下的历史解能够缩短初始种群与最优种群的距离。而且，还可以看出，在状态 $t _ { 1 }$ 迭代次数较少的情形下，动态优化也可以找到和纯静态优化相似的解，这是因为状态 $t _ { 2 }$ 下有足够的迭代次数以保证DE的充分探索。

![](images/b382a34663420cf6870dbb59b94558e620a35b6b00120db29e84c9e9649faae5.jpg)

图5给出了DE在状态 $t _ { 1 }$ 下迭代5次后状态 $t _ { 2 }$ 下迭代5次、状态 $t _ { 1 }$ 下迭代10次后状态 $t _ { 2 }$ 下迭代10次和状态 $t _ { 1 }$ 下迭代15次后状态 $t _ { 2 }$ 下迭代15次后系统结构变为状态 $t _ { 3 }$ 后的优化结果。其中，“纯静态优化”指的是DE 直接在状态 $t _ { 3 }$ 下搜索；“考虑历史解”指的是在系统结构变化后，DE将前一状态下的部分历史解作为当前状态下的初始种群来搜索；“不考虑历史解”指的是在系统结构发生变化后，直接在当前状态下随机生成初始种群来搜索。从图5可以看出，随着变化频率的增加，动态优化和静态优化的差距越来越明显，说明系统结构变化频繁不利于可靠性分配问题的优化。但是可以看出，考虑历史解仍然要优于不考虑历史解。而且，在总的迭代次数较少、前面状态下迭代次数较大的情况下，考虑历史解的优势尤其明显，因为最后一个状态没有足够的迭代次数来保证DE的充分探索。因此，在恶劣情形下的动态优化，考虑历史解是一个提高最终解质量的一个有效手段。

![](images/a0b26707d0afeb035df334a982e0892a128fa62087b71f68694eb7b3f0126802.jpg)  
图4DE从状态 $t _ { \mathrm { l } }$ 到状态 $t _ { 2 }$ 后的优化结果

![](images/bdc04b9aac5caabf1154c3c60c9b7c4c47ed2962c70e096c99cd7cef0adf44ce.jpg)

![](images/d25adbbff3e63f87cb3181671652c21a3eb7435711aef0c19793a81c8bc369fd.jpg)  
(a) $t _ { 1 }$ 状态迭代5次后 $t _ { 2 }$ 状态迭代5次  
(b) $t _ { 1 }$ 状态迭代20次

(b） $t _ { 1 }$ 状态迭代10次后 $t _ { 2 }$ 状态迭代10次

![](images/1573e24364b01727ec1e627a70b73c7514ec4cf930d0d2544a73e06901f57a67.jpg)  
(c） $t _ { 1 }$ 状态迭代15次后 $t _ { 2 }$ 状态迭代15次   
图5DE从状态 $t _ { \mathrm { { l } } }$ 到状态 $t _ { 2 }$ 再到状态 $t _ { 3 }$ 后的优化结果

# 4 结束语

针对用户需求的变化或程序员的改进，在可靠性分配优化过程中复杂软件系统的结构可能会随着时间发生变化，本文构建了复杂软件系统动态可靠性分配优化模型，并基于D-S证据理论和差分进化设计了复杂软件系统动态可靠性分配算法。在系统结构发生变化时，首先基于D-S证据理论对系统中各模块的局部权重进行估计，并在差分进化生成初始种群时保留部分历史解。仿真实验结果验证了所提方法的有效性，但需要注意的是当模块数增加至比较多时可能导致问题的目标函数无解，第二组实验的结果也表明当模块数增加至一定数目时，目标函数的解空间会变得非常小，这会极大的限制差分进化的性能，因此本文提出的算法仅适于模块数较少时的情形。在后续的工作中，需要考虑：动态多目标可靠性分配问题；当软件层、功能层或程序层发生变化时的优化问题；根据模型推演 $r _ { M _ { j } }$ 的上下界，设计约束处理技术以提高算法的搜索性能。

# 参考文献：

[1]徐仁佐，张良平，张大帅．软件可靠性分配的一个非线性规划模型 [J]. 计算机工程,2003,29(17): 34-36.(Xu Renzuo,Zhang Liangpin,Zhang Dashuai.A nonlinear programming model of software reliability allocation [J].Computer Engineering,2003,29(17):34: 36.)   
[2]高峰，件林博，岳肠，等．基于AHP与AdaBoosting 的软件可靠性组合 模型[J].计算机工程,2017,43(12):69-72.(Gao feng,Wu Lingbo,Yue Yang,et al. Software reliability combination model based on AHP and AdaBoosting [J]. Computer Engineering,2017,43(12):69-72.)   
[3] 张策，孟凡超，考永贵，等．软件可靠性增长模型研究综述[J].软件 学报,2017,28(9):2402-2430.(Zhang Ce,Meng Fanchao,Kao Yonggui, et al.Survey of software reliability growth model[J].Journal of Software, 2017,28 (9):2402-2430.)   
[4]Zahedi F,Ashrafi N. Software reliability allocation based on structure, utility,price,and cost[J].IEEE Trans on Software Engineering,1991,17 (4): 345-356.   
[5]Leung Y W. Optimal reliability allcation for modular software system designed for multiple customers[J].IEICE Trans on Information& Systems,1996,79 (12): 1655-1662.   
[6]Leung Y W. Software reliability allocation under an uncertain operational profile [J]. Journal of the Operational Research Society,1997,48 (4): 401-411.   
[7]Kapur PK,Bardhan AK,JhaPC.Optimal Reliability Allocation Problem for a Modular Software System [J]. Opsearch,2003,40 (2):138-148.   
[8]Roy D S,Mohanta D K,Panda A K.Software reliability allocation of digital relay for transmission line protection using a combined system hierarchy and fault tree approach [J].IET Software,20o8,2(5): 437-445.   
[9]Chatterjee S,Singh JB,Roy A.A structure-based software reliability allocation using fuzzy analytic hierarchy process [J]. International Journal of Systems Science,2015,46 (3): 513-525.   
[10]韩冰青，高建华．基于模拟退火遗传算法的软件可靠性分配及研究[J]. 计算机工程,2003,29 (4): 67-69.(Han Bingqing,Gao Jianhua.Reliability allocation and research of software system based on Simulated Anealing Genetic Algorithm [J]. Computer Engineering,2003,29 (4): 67-69.)   
[11]徐悦，皮德常．基于混合智能优化算法的复杂软件可靠性分配[J].软 件学报，2018,29 (9):1-19.(Xu Yue,Pi Dechang.Complex software reliability allocation based on hybrid intelligent optimization algorithm [J]. Journal of Software,2018,29 (9): 1-19.)   
[12] Das S,Mullick S S,Suganthan P N.Recent advances in diffrential evolution: an updated survey [J]. Swarm & Evolutionary Computation, 2016, 27: 1-30.   
[13] Sangeetha M, Arumugam C, Kumar K M S,et al. An effective approach to support multi-objective optimization in software reliability allocation for improving quality [J]. Procedia Computer Science,2015,47: 118-127.   
[14] Yue F,Zhang G, Su Z,et al.Multi-softwarereliability allocation in multimedia systems with budget constraints using Dempster-Shafer theory and improved differential evolution [J].Neurocomputing，2O15,169: 13-22.   
[15] YagerRR,Liu L.Classic Works of the Dempster-Shafer Theory of Belief Functions [M]// Classic Works on the Dempster-Shafer Theory ofBelief Functions (Studies in Fuzziness and Soft Computing）.New York: Springer-Verlag,2007: 1-34.