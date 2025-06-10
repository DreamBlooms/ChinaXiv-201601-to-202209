# 基于多种群的随机扰动蚁群算法求解分布式约束优化问题

石美凤，肖诗川，冯欣(重庆理工大学 计算机科学与工程学院，重庆 400054)

摘要：针对现有的基于蚁群优化思想求解分布式约束优化问题的算法收敛较慢，且容易陷入局部最优等问题，提出了一种基于多种群的随机扰动蚁群算法(Random disturbance based multi-population ant colony algorithm to solvedistributed constraint optimization problems，RDMAD)来求解分布式约束优化问题。首先，RDMAD提出了一种分工合作机制，将种群按比例划分为采用贪婪搜索的子种群和采用启发式搜索的子种群，同时构建分级更新策略，提高算法收敛速度和求解质量；然后，对采用贪婪搜索的子种群设计自适应变异算子和奖惩机制，防止算法陷入局部最优；最后在算法陷入停滞时触发随机扰动策略，增加种群多样性。将RDMAD与7种最先进的非完备算法在三类基准问题上的寻优结果进行了实验对比，实验结果表明RDMAD 在求解质量和收敛速度上优势明显，且稳定性较高。

关键词：分布式约束优化问题；蚁群算法；自适应变异算子；非完备算法 中图分类号：TP18 doi:10.19734/j.issn.1001-3695.2022.03.0084

# Random disturbance based multi-population ant colony algorithm to solve distributed constraint optimization problems

Shi Meifeng†,Xiao Shichuan, Feng Xin (College ofComputer Science& Engineering,Chongqing UniversityofTechnology,Chongqing 40054,China)

Abstract:Ant-based algorithm to solve distributedconstraint optimization problems (ACO_DCOP）isanexcellnt population-based algorithm for solving DCOPs.However,ACO_DCOP hassome shortcomings including very slow convergence speed and easily faling into local optima.Tocope with these issues,this paper proposes arandom disturbance based multi-population ant colony algorithm to solve DCOP(RDMAD).The method introduces a division of labor and cooperation mechanism to divide the population into two subpopulations for greedy search and heuristic search respectively. The method alsoconstructs ahierarchical update strategy to speed upconvergenceand improve solution quality.Furthermore, this paperdesignsanadaptive mutation operatorandareward andpunishment mechanism forthe greedy search subpopulation to prevent RDMAD falling into the local optima.Simultaneously,this paper introduces arandom disturbance strategy to increasethe population diversity whenRDMAD is stagnant.To verify theperformance of the proposed algorithm,RDMAD is compared with the other seven advanced incomplete algorithms on three types of benchmark problems.The extensive experimentalresultsshowthatthe proposedalgorithmissignificantlysuperiortothestate-of-the-arts algorithms insolution quality and convergence speed. In addition,RAMAD is far stable than the competing algorithms.

Keywords:distrbutedconstraintoptimizationproblems;antcolonyalgorithm;adaptive mutationoperator; incompletealgorithm

# 0 引言

多智能体系统(multi-agent system，MAS)[l]是分布式人工智能领域重要的一部分。分布式约束优化问题(distributedconstraintoptimization problems,DCOP)[2]是MAS基本框架之一，被广泛地应用于许多实际问题建模，如传感器网络[3]、任务调度[4]等。

在过去的二十年里，许多算法被提出用来求解DCOP。其中完备算法可得到问题的最优解。SyncBB[5]、AFB[6]、ADOPT[7]、BnB-ADOPT[8]等是典型的基于搜索的完备算法。DPOP[9]作为典型的基于推理的完备算法，其利用动态规划思想求解DCOP，但DPOP在求解过程中会遭受指数级的内存消耗。MB-DPOP[10]算法被提出用于降低 DPOP 算法内存消耗。为提高MB-DPOP 算法性能，Chen 等[11]提出RMB-DPOP算法减少MB-DPOP算法中的冗余推理，提高了算法的可扩展性。Rashik等[12]利用交叉边一致性缩短了DPOP的运行时间。由于DCOP是NP-Hard，相比之下，非完备算法虽然不能找到最优解，但在通信和计算方面有更好的性能。其中，基于局部搜索的非完备算法是目前的研究热点，其中包括DSA[3]和GDBA[13]等。此外，ALS[14]、PDS[15]和LSGA[16]等框架被用来提高基于局部搜索的算法的求解质量。Max-Sum[17]和Max-Sum_ADVP[18]等是基于推理的非完备算法，其中 agent通过因子图传播和积累效用。基于采样的非完备算法(如DUCT[I9])则通过对搜索空间进行采样来求解DCOP。近来，出现了一类利用种群求解DCOP的非完备算法。Mahmud 等[20]提出了一种利用进化优化思想求解DCOP 的算法。Chen 等[2I提出了利用蚁群优化思想求解DCOP的算法(ACO_DCOP),ACO_DCOP是目前唯一利用蚁群优化思想求解DCOP的算法，其从传统蚁群算法演变而来，然而ACO_DCOP算法中仅利用单种群寻优，同时受信息素影响，收敛较慢，容易陷入局部最优。目前多种群策略被广泛使用，薛宏全等[22]通过分析蚂蚁分工，利用核心蚁群和搜索蚁群的配合有效的解决了车间调度问题。朱佑滔等[23提出了一种多种群蚁群算法用于求解机械手臂的路径规划问题。陈佳等[24]采用主从蚁群的多种群机制有效求解旅行商问题。因此针对ACODCOP收敛较慢，且易陷入局部最优等问题，本文提出一种基于多种群的随机扰动蚁群算法求解分布式约束优化问题(RDMAD)。本文的主要贡献包括4个方面：

a)提出了一种分工合作机制，子种群分别通过执行贪婪搜索和启发式搜索使得局部和全局搜索相互协调，可以更好地探索解空间和开发优秀解。

b)提出了一种随机扰动策略，在算法陷入停滞时，触发随机扰动策略，种群重新划分为3个子种群，新增采用随机选值的子种群，增加种群多样性，有助于算法跳出局部最优。

c）设计了一种分级更新策略，执行不同任务的子种群采用不同更新方式，提高了算法的收敛速度和求解质量。

d）对RDMAD算法的复杂性进行了理论分析，并通过实验结果表明RDMAD算法在求解质量和收敛性能上优势明显。

# 1背景

# 1.1分布式约束优化问题

DCOP可定义为一个四元组 $\langle X , D , F , A \rangle$ [25]，其中 $\mathbf { \nabla } _ { A }$ 是agent 的集合 $\{ a _ { 1 } , a _ { 2 } , . . . , a _ { n } \}$ ； $\boldsymbol { \cal X }$ 是离散变量的集合 $\{ x _ { 1 } , x _ { 2 } , . . . , x _ { m } \}$ ，一个agent 控制一个或多个变量， $m \geq n$ ； $\mathrm { ~ D ~ }$ 是离散变量值域的集合 $\{ D _ { 1 } , D _ { 2 } , . . . , D _ { m } \}$ ，其中Di是变量 $x _ { i }$ 的值域； $F$ 是约束关系函数的集合 $\{ f _ { 1 } , f _ { 2 } , . . . , f _ { q } \}$ ，其中 $f _ { i } \in F$ 是子集 $x ^ { i } \subseteq X$ 的函数，该函数定义了 $x ^ { i }$ 中变量间的约束关系。

DCOP求解算法的目标为寻找一组赋值组合 $X ^ { \ast }$ 使式(1) 所示全局约束代价最小。

$$
X ^ { * } = \underset { X } { \arg \operatorname* { m i n } } \sum _ { i = 1 } ^ { q } f _ { i } ( x ^ { i } )
$$

本文中一个agent 控制一个变量，因此这里“agent”和“变量”可互换。图1(a)为DCOP的约束图，其中一个节点表示一个agent，两个agent之间的边表示它们之间存在约束关系，图1(b)为DCOP的约束矩阵，其中0、1为变量的取值，矩阵中其余值为当有约束的两个变量取值时对应的代价大小。例如，当 $\scriptstyle x _ { 1 } = 0$ ， $x _ { 2 } = 0$ 时，对应代价值为5。

![](images/449b56495ca8c7b4709655de7714ecb978491e9efd4dd7f732cc945e1c0b23c1.jpg)  
图1 DCOP实例  
Fig.1 ADCOP instance

# 1.2 ACO_DCOP

蚁群优化算法(Ant Colony Optimization,ACO)是一种基于种群的求解组合优化问题的元启发式算法，已成功应用于旅行商问题、约束满足问题等。由于DCOP中没有实际的路径可用，因此传统的ACO无法直接用于求解DCOP。目前仅有ACO_DCOP成功将蚁群优化思想应用于求解DCOP。

ACO_DCOP利用agent之间的消息传递机制来模拟蚂蚁的运动，首次将群体智能应用于求解DCOP。以图1为例得到图2(c)所示信息素路径构造图，其中节点表示agent。首先将图1(a)中的约束图转为广度优先搜索伪树[26]，如图 2(a)所示。然后构建的agent之间的消息传递顺序(蚂蚁爬行方向)，如图2(b)所示，其中上层agent 的优先级高于下层agent，同层间的agent邻居个数越多，值域越大优先级越高，若两个同层的agent具有相同的邻居数和值域大小，则agent的命名id 越小，优先级越高。因此agent $a _ { i }$ 的邻居可分为高优先级邻居 $\boldsymbol { H } _ { i }$ 和低优先级邻居 $L _ { i }$ ，且消息从高优先级的agent传向低优先级的agent。同时根据agent的取值不同，每两个agent之间有多条信息素路径。如图2(c)信息素路径构造图，当 $a _ { i }$ 取值为 $\boldsymbol { d } _ { i }$ ， $\boldsymbol { a } _ { j }$ 取值为 $\boldsymbol { d } _ { j }$ 时，则该路径上的信息素浓度为$\tau _ { i j } ( d _ { i } , d _ { j } )$ 。

每次迭代中，蚂蚁从优先级最高的agent 出发，在每只蚂蚁获得取值后，agent将蚂蚁取值发送给其低优先级邻居。当接收到其高优先级邻居的蚂蚁取值后，agent $a _ { i }$ 首先为每只蚂蚁合并收到的解集合，当 $a _ { i }$ 收到其所有高优先级邻居的蚂蚁取值后，采用转移概率为每只蚂蚁选取变量值域中的取值，否则等待其高优先级邻居的取值。 $a _ { i }$ 完成为每只蚂蚁取值后将蚂蚁取值发送给自己的低或最低优先级邻居。当最低优先级agent收到所有蚂蚁取值后，此时每只蚂蚁已经完成解的构建，计算每只蚂蚁构建的解的代价，代价越小解的质量越好，根据代价更新全局最优解并且计算每只蚂蚁的信息素增量，然后将信息素增量发送给所有agent。agent收到信息素增量信息后，更新和蒸发与其高优先级邻居间的信息素路径上的浓度，到此一次迭代结束。

![](images/c616e69d06d33d9f3dd65bfa4c93e58227b6e081bbc7a50f12b81f26319ef68c.jpg)  
Fig.2Pheromone path construction

# 2 RDMAD 算法

本文提出了一种基于多种群的随机扰动蚁群算法用于求解DCOP，其主要采用分工合作机制、分级更新和随机扰动策略。该算法利用子种群在寻优过程中的不同指导作用，有效地提高了算法收敛和求解性能。

# 2.1 初始化阶段

RDMAD 算法利用蚂蚁在agent之间的运动来构造解。首先RDMAD算法将agent之间的约束图转换为广度优先搜索的伪树结构，然后根据伪树结构构建agent消息传递顺序，生成最终构造图，如1.2节图2所示过程。RDMAD算法中，信息素信息由低优先级agent保存。在完成构造图构建后，初始化参数，并且每个agent 初始化蚂蚁解集为空。然后优先级最高agent为每只蚂蚁随机取值，再将取值信息发送给自己的低优先级邻居。以1.2节图2为例， $x _ { 1 }$ 为优先级最高节点，假设种群规模为2， $x _ { 1 }$ 为蚂蚁1取值为1，为蚂蚁2取值为0，则将 $x _ { 1 }$ 的 $i d$ 和蚂蚁取值{1,0}发送给 $x _ { 1 }$ 的低优先级邻居 $x _ { 2 } , x _ { 3 }$ 和 $x _ { 4 }$ 。

# 2.2 分工合作机制

基于种群求解DCOP的策略近几年才出现，这类算法都是直接从传统群体智能算法中演变而来，仅利用了单种群来寻优。本文在现有采用蚂蚁转移概率取值的种群上增加了采用贪婪搜索的子种群，利用多种群合作更好地平衡开发和探索。

当agent $a _ { i }$ 接收到来自其高优先级邻居的取值时，首先合并所有取值，当 $a _ { i }$ 接收到所有高优先级邻居的取值时， $a _ { i }$ 开始为蚂蚁选值，每个子种群的选值策略如下：

# 1）子种群1

agent $a _ { i }$ 采用贪婪搜索为子种群1中的蚂蚁取值，该方式增强了蚂蚁对局部的探索，有利于提高算法收敛速度。 $a _ { i }$ 采用式(2)为蚂蚁 $k$ 选取使 $a _ { i }$ 与其邻居间约束代价和最小时的取值 $d _ { i }$ 。

$$
d _ { i } = \underset { d _ { i } \in D _ { i } } { \arg \operatorname* { m i n } } ( \sum _ { j \in H _ { i } } \cos t _ { i j } ( d _ { i } , V _ { k , j } ) + e s t _ { i } ( d _ { i } ) )
$$

其中， $D _ { i }$ 是值域， $V _ { k , j }$ 是 $a _ { i }$ 的高优先级邻居 $a _ { j }$ 对蚂蚁 $k$ 的取

值， $\cos t _ { i j } ( d _ { j } , V _ { k , j } )$ 是 $a _ { i }$ 为蚂蚁 $k$ 取值为 $d _ { i }$ ， $\mid a _ { j }$ 为蚂蚁 $k$ 取值为$V _ { k , j }$ 时的约束代价，式(3)定义了 $a _ { i }$ 与其低优先级邻居 $L _ { i }$ 之间的最小约束代价和的预估值 $e s t _ { i } ( d _ { i } )$ ，其初始化为最优解。

$$
e s t _ { i } ( d _ { i } ) = \sum _ { j \in L _ { i } } \operatorname* { m i n } _ { d _ { j } \in D _ { j } } \cos t _ { i j } ( d _ { i } , d _ { j } )
$$

为避免种群因贪婪搜索快速陷入局部最优，本文为子种群1设计了一种自适应调整的变异算子 $p _ { m }$ ，其定义如式(4)所示。

$$
p _ { m } = 1 - m \frac { t o t a l c y c l e - c u r c y c l e } { t o t a l c y c l e }
$$

其中， $\mathbf { \nabla } _ { m }$ 为权值，可调整变异算子大小，totalcycle为总的迭代次数，curcycle为当前迭代次数。当 $a _ { i }$ 为种群1取值完成时，采用随机概率 $q \in [ 0 , 1 ]$ 挑选蚂蚁个体进行值交换，当小于$p _ { m }$ 时， $a _ { i }$ 随机选择蚂蚁 $k ^ { \prime }$ ，将当前蚂蚁 $k$ 的取值与蚂蚁 $k ^ { \prime }$ 的取值互换，得到新个体。

# 2）子种群2

子种群2保留原有的转移概率取值方式，其主要采用蚁群优化思想中的启发式搜索，这有利于蚂蚁对agent $a _ { i }$ 的解空间进行全局探索。该概率计算依赖于信息素因子和启发式因子，同时配合轮盘赌。 $a _ { i }$ 采用式(5)为蚂蚁 $k$ 取值为 $d _ { i }$ 的概率如下。

$$
p _ { k , i } ( d _ { i } ) = \frac { \theta _ { k , i } ( d _ { i } ) ^ { \alpha } \eta _ { k , i } ( d _ { i } ) ^ { \beta } } { \displaystyle \sum _ { d _ { i ^ { \prime } } \in D _ { i } } \theta _ { k , i } ( d _ { i } ^ { \prime } ) ^ { \alpha } \eta _ { k , i } ( d _ { i ^ { \prime } } ^ { \prime } ) ^ { \beta } }
$$

其中， $\alpha$ 和 $\beta$ 分别为信息素因子和启发式因子权重，信息素因子 $\theta _ { k , i } ( d _ { i } )$ 影响蚂蚁对路径的探索，其定义如式(6)所示。

$$
\theta _ { k , i } ( d _ { i } ) = \sum _ { j \in H _ { i } } \tau _ { i j } ( d _ { i } , V _ { k , j } )
$$

其中， $\theta _ { k , i } ( d _ { i } )$ 为 $a _ { i }$ 对蚂蚁 $k$ 取值 $d _ { i }$ 时， $a _ { i }$ 与其所有高优先级邻居之间的信息素浓度之和。启发式因子 $\eta _ { k , i } ( d _ { i } )$ 影响了蚂蚁对解的开发， $a _ { i }$ 与其邻居间的约束代价和越大，启发式因子越小，当前解被开发的可能性越小，如式(7)所示。

$$
\eta _ { k , i } ( d _ { i } ) = \frac { 1 } { \displaystyle \sum _ { j \in { \cal H } _ { i } } \cos t _ { i j } ( d _ { i } , V _ { k , j } ) + e L _ { i } ( d _ { i } ) - \mathrm { L C } }
$$

其中，LC为 $a _ { i }$ 与其邻居间的最小约束代价和，用于评估值 $d _ { i }$ 的可开发程度，如式(8)所示。

$$
\mathrm { L C } = \operatorname* { m i n } _ { d _ { i } \in D _ { i } } ( \sum _ { j \in H _ { i } } \operatorname* { m i n } _ { d _ { j } \in D _ { j } } \cos t _ { i j } ( d _ { i } , d _ { j } ) + e L _ { i } ( d _ { i } ) ) - 1
$$

# 2.3 随机扰动策略

种群的多样性影响了算法对解空间的搜索范围，由于蚂蚁是依靠路径上的信息素浓度寻优的，ACO_DCOP在迭代后期，种群多样性越来越小，因此算法容易陷入局部最优。本文设计了一种随机扰动策略来增加种群多样性。当算法停滞次数等于设定的阈值count，此时触发随机扰动策略。算法将种群重新划分成三个子种群，其中子种群1和2的任务不变，子种群3的任务则是扰动信息素积累，按式(9)采用完全随机取值，打破原有信息素累积规律。

$$
\ r { d _ { i } } = r a n d o m ( \ r { D _ { i } } )
$$

# 2.4分级更新策略

根据每个子种群的引导作用不同，构建分级更新策略。首先当最低优先级agent $a _ { i }$ 接收到所有高优先级邻居的取值后，计算每只蚂蚁的信息素增量 $\Delta _ { k }$ ，如式(10)所示。

$$
\Delta _ { k } = 1 - \frac { \cos t _ { k } - b e s t c o s t } { \frac { 1 } { K } \sum _ { k = 1 } ^ { K } \cos t _ { k } - b e s t c o s t }
$$

其中， $\cos t _ { k }$ 为蚂蚁 $k$ 构建的完整值分配对应的代价，bestcost为全局最优代价值， $K$ 为种群规模。最低优先级 $a _ { i }$ 将信息素增量 $\Delta _ { k }$ 、种群解集和最优解发送给其他所有agent。agent 利

用信息素增量 $\Delta _ { k }$ 更新与其高优先级邻居之间信息素路径浓度。更新策略如式(11)所示。

$$
\tau _ { i j } ( V _ { k , i } , V _ { k , j } ) = \tau _ { i j } ( V _ { k , i } , V _ { k , j } ) + \Delta _ { k } ^ { \prime } , \forall j \in H _ { i }
$$

$$
\Delta _ { k } ^ { \prime } = \left\{ \begin{array} { l } { { \delta _ { k , i j } , k \in \vec { \mathrm { \mathcal { F } } } \mathrm { \# } \mathrm { \# } _ { \mathrm { \# } } ^ { \# } } | } \\ { { 0 . 8 \Delta _ { k } , k \in \vec { \mathrm { \mathcal { F } } } \mathrm { \# } \mathrm { \# } _ { \mathrm { \# } } ^ { \# } } 2 } \\ { { 1 . 2 \Delta _ { k } , k \in \vec { \mathrm { \mathcal { F } } } \mathrm { \# } \mathrm { \# } _ { \mathrm { \# } } ^ { \# } } 3 } \end{array} \right.
$$

式(12)是各子种群信息素增量的定义。由于子种群1对种群的探索方向具有引导作用，因此子种群1的更新方式按式(13)所示奖惩机制进行。

$$
\delta _ { k , i j } = \left\{ { \begin{array} { l l } { \Delta _ { k } n _ { 1 } , } & { \Delta _ { k } \geq 0 } \\ { \Delta _ { k } / n _ { 1 } , } & { \Delta _ { k } < 0 } \end{array} } \right.
$$

其中， $n _ { 1 }$ 为子种群1的规模。若 $\Delta _ { k }$ 为正，相应路径将获得奖励，否则将受到处罚。该机制可减小路径上信息素浓度的差异，防止算法过快收敛。

分级更新策略体现了多种群在寻优过程中对算法的不同指导作用。通过这种模式，提高了算法的收敛速度和寻优质量。

# 2.5信息素蒸发

信息素蒸发阶段可使得蚂蚁忘记之前不好的路径，agent在更新信息素后，根据式(14)进行信息素蒸发，其中 $\rho$ 为蒸发率， $\tau _ { 0 }$ 为初始化浓度，信息素范围为[ $\tau _ { \mathrm { m i n } } ~ , \tau _ { \mathrm { m a x } } ~ ] _ { \mathrm { c } }$ （2

$$
\tau _ { i j } ( d _ { i } , d _ { j } ) = ( 1 - r _ { 1 } \rho ) \tau _ { i j } ( d _ { i } , d _ { j } ) + r _ { 2 } \rho \tau _ { 0 }
$$

其中， $r _ { \mathrm { i } }$ ， $r _ { 2 }$ 控制了蒸发率的大小，默认为1。在触发随机扰动策略时， $r _ { 1 } = 2$ ， $r _ { 2 } = 0 . 5$ ，增强信息素蒸发，有助于算法跳出局部最优。

# 2.6 RDMAD 算法步骤

RDMAD算法具体实现步骤如算法1所示。

算法1 RDMAD 算法(for agent $a _ { i }$ ）

输入：初始化参数 $\alpha , \beta , \rho , \tau _ { 0 } , K , c o u n t$ 。

输出：使全局约束代价最小的一组赋值组合 $\boldsymbol { X } ^ { * }$ 。  
1 for each $\boldsymbol { d } _ { i } \in D _ { i }$ do 计算 $e s t _ { i } ( d _ { i } )$ end for  
2 for each 蚂蚁 $\mathbf { k }$ do  
3 初始化解集： $V _ { k , * } \gets \{ \} , V \gets V \cup V _ { k , * }$ 盖  
4 if $a _ { i }$ 是优先级最高节点  
5 for each 蚂蚁 $\mathbf { k }$ do  
6 $a _ { i }$ 为蚂蚁随机取值为 $V _ { k , i }$ ， $V _ { k , * }  V _ { k , * } \cup V _ { k , i }$   
7 end for  
8 发送蚂蚁取值信息 $V$ 和 $a _ { i }$ 的 $i d$ 给低优先级邻居 $L _ { i }$   
9 end for  
10 When agent $a _ { i }$ 收到了取值信息 $( \ i d \ , \ r e c \nu _ { - } V$ )：  
7 for each 蚂蚁 $\boldsymbol { \mathsf { k } }$ do $V _ { \boldsymbol { k } , * }  V _ { \boldsymbol { k } , * } \cup r e c { \nu }  V$ end for  
8 if $a _ { i }$ 从其高优先级邻居收到了所有取值信息  
9 for each 蚂蚁k do  
10 if $\scriptstyle \mathtt { c } = = c o u n t$   
11 $a _ { i }$ 根据式(2)，(4)为子种群1取值  
12 $a _ { i }$ 根据式(5)，(9)分别为子种群2,3取值  
13 else $a _ { i }$ 根据式(2),(4)，(5)为子种群1,2取值  
14 合并取值 $V _ { k , * } \gets V _ { k , * } \cup V _ { k , \mathrm { i } }$ （204  
15 end for  
16 $a _ { i }$ 发送取值信息 $\{ i d , V \}$ 给 $L _ { i }$ 或最低优先级 $a _ { i }$   
17 if $a _ { i }$ 优先级最低且收到所有取值信息  
18 更新bestcost和其对应的最佳值分配 $\nu ^ { * }$ ，更新cou  
按式(10)计算每只蚂蚁的信息素增量 $\Delta _ { k }$   
19 发送信息素信息 $\left\{ \ V \ , \ \Delta \ , \ \nu ^ { * } \right.$ 分给所有agent  
20 When agent $a _ { i }$ 收到了信息素信息 $( \ i d \ , \ r e c { \nu } _ { - } V \ )$ ：  
21 根据式(11),(14)分别更新和蒸发信息素，更新 $e s t _ { i } ( d _ { i } )$ （204号  
22 if 不满足终止条件 then 开始下一轮循环

在信息素更新和蒸发阶段结束过后，还要对agent $a _ { i }$ 与其低优先级邻居 $L _ { i }$ 之间的最小约束代价和的预估值 $e s t _ { i } ( d _ { i } )$ 进行更新。由于在分布式场景中，agent仅知道其邻居的信息，并且根据消息传递顺序，agent仅知道其高优先级邻居的取值。因此该预估值可帮助 $a _ { i }$ 估算与其所有邻居的最优代价和，有助于启发式因子对当前取值的评估。 $e s t _ { i } ( d _ { i } )$ 的更新如算法 2所示。

算法2更新预估值 $e s t _ { i } ( d _ { i } )$ (for agent $a _ { i }$ ） 输入：种群解集 $V$ 。 输出：更新后的预估值 $e s t _ { i } ( d _ { i } )$ 。 1 for each $\boldsymbol { d } _ { i } \in \boldsymbol { D } _ { i }$ do 2 $\mathrm { s u m } = 0 , \mathrm { n u m } = 0$ 3 for each 蚂蚁 $\mathbf { k }$ do 4 if $V _ { k , i } = d _ { i }$ then 5 $s u m + = \sum _ { j \in L _ { i } } \mathrm { c o s t } _ { i j } ( d _ { i } , V _ { k , j } ) \ , \ \mathsf { n u m } \ = \ \mathsf { n u m } + 1$ 6 end for 7 if num $! { = } 0$ then 8 $\mathsf { a v e } = \mathsf { s u m } / \mathsf { n u m } , \quad e s t _ { i } ( d _ { i } ) = ( e s t _ { i } ( d _ { i } ) + \mathrm { a v e } ) / 2$ 9 end for

# 2.7RDMAD 算法复杂性分析

RDMAD算法复杂性分析主要包含算法的消息数、空间复杂度和时间复杂度。将改进后的RDMAD算法与ACO_DOCP算法进行比较。在每次迭代中，除最低优先级agent外，每个agent都会向其低优先级邻居(或最低优先级邻居)发送取值信息，最低优先级agent会向所有agent发送信息素信息。由于取值信息中包含了蚂蚁的解集，因此值消息的大小为 $O ( n K )$ ， $n$ 为 agent个数，因此RDMAD 算法中值消息大小与ACO_DCOP 算法一致。包含了蚂蚁的解集、信息素增量和最优解的信息素消息的大小为 $O ( ( K + 1 ) n { + } K )$ ，因此RDMAD 算法中信息素消息大小与ACO_DCOP 算法一致。

每个agent $a _ { i }$ 存储与其高优先级邻居间的信息素路径需要 $O ( | H _ { i } | | D _ { i } | | D _ { j } | )$ 大小的空间。因此RDMAD算法需要的空间大小与ACO_DCOP算法一致。时间复杂度主要是取值计算，在最坏情况下，当 $a _ { i }$ 为蚂蚁 $k$ 取值时，对于值域 $D _ { i }$ 中的每个值 $d _ { i }$ 会遍历其所有高优先级邻居的取值，因此 $a _ { i }$ 计算一个值消息需 $\mathrm { O } ( K | H _ { i } | | D _ { i } | )$ 次操作。因此RDMAD算法时间复杂度与ACO_DCOP 算法一致。

# 3 实验与结果分析

# 3.1实验设置

实验采用三类基准问题进行算法性能测试，包括随机DCOPs[27](EXP-1、EXP-2)、无尺度网络问题[28](EXP-3、EXP-4)和加权图着色问题 (EXP-5)。具体相关信息如表1所示。

表1问题配置  
Tab.1Problem configuration   

<html><body><table><tr><td>测试问题</td><td>agent个数</td><td>变量值域</td><td>约束代价范围</td><td>问题密度</td></tr><tr><td>EXP-1</td><td>70</td><td>10</td><td>[1,100]</td><td>0.1</td></tr><tr><td>EXP-2</td><td>70</td><td>10</td><td>[1,100]</td><td>0.6</td></tr><tr><td>EXP-3</td><td>70</td><td>10</td><td>[1,100]</td><td>10,3</td></tr><tr><td>EXP-4</td><td>70</td><td>10</td><td>[1,100]</td><td>10,7</td></tr><tr><td>EXP-5</td><td>120</td><td>3</td><td>[1,100]</td><td>0.05</td></tr></table></body></html>

# 3.2参数分析

为验证重要参数对RDMAD算法的影响，以随机DCOPs(EXP-1)为例，对RDMAD算法中的信息素因子 $\scriptstyle a$ 、启发式因子 $\beta$ 、信息素蒸发率 $\rho$ 以及触发阈值count进行了实验分析。为保证实验结果的公平性，本实验中采用控制变量法对每个参数进行调节，同时每个参数的每个值取独立运行30次的平均值作为该取值下的实验结果。各参数的实验结果如图3所示。

图3(a)显示了 $\scriptstyle a$ 变化对RDMAD算法性能的影响，从图中可以看到，随着 $\alpha$ 的增大算法求得的解质量也随之提高，但在 $\alpha > 1$ 后，算法的性能开始下降，因此根据实验结果， $\alpha$ 取1时RDMAD 算法的性能最好。图3(b)中的 $\beta$ 的取值也对RDMAD算法的性能有较大的影响，从图中可以看出 $\beta$ 越大，算法的求解质量和收敛性能都在提升，但当 $\beta { > } 3$ 后解的质量开始下降。从图3(c)的实验结果可以得出，信息素的蒸发率$\rho$ 也会影响算法的性能，但它的影响略小于参数 $\alpha$ 和 $\beta$ ，当$\rho { = } 0 . 0 0 2 5$ 时，RDMAD算法得到的解质量最好。最后图3(d)为触发间隔的选择实验，实验结果表明在触发随机扰动策略时，设置合适的触发间隔能有效提高求解质量。

因此根据实验结果，适当设置重要参数的值有利于提高算法的求解质量和收敛性能。为不失公平性，对比算法的参数采用原文推荐值。RDMAD算法参数设置为： $\alpha = 1$ ， $\beta = 3$ $\rho = 0 . 0 0 2 5 , \tau _ { 0 } = 3 , c o u n t = 8 0$ $K = 2 0 .$ 在未触发随机扰动策略时，子种群1、2的规模分别为 $0 . 5 \ : K$ ， $0 . 5 \ : K$ ；在触发随机扰动策略后，子种群1、2和3的规模分别为 $0 . 5 \ : K$ ， $0 . 3 \ : K$ 和 $0 . 2 \ : K$ □

![](images/b9827ad232b8247781bd3564bbd87455e93b6e23a5e6d84c67813a62dae12ad8.jpg)  
图3各参数实验结果  
Fig.3Parametric experimental results

# 3.3 实验结果及分析

为验证RDMAD算法的鲁棒性和寻优性能，在测试问题上与其他优秀的非完备DCOP算法进行比较，包括PDS-DSA[15]、GDBA[13]、ACODCOP[20]、DSAN[29]、DSA[3]、LSGA_DSA[16]、AED[21]。由于非完备算法具有随机性，因此每个实例取独立运行30次的均值为结果，每个测试问题随机生成20个实例。

表2为RDMAD 算法与ACODCOP算法，及其他对比算法在每个测试问题的20个实例上的约束代价的均值(Mean)和标准差(StdDev)。同时，采用Wilcoxon符号秩和检验法对实验结果进行统计分析，其中“ $^ +$ ”表示RDMAD算法在20个实例上得到的结果优于对比算法的个数；而“-”则表示相反意思。从表2的Mean值可以看出，在除EXP-2外的所有测试问题上，RDMAD算法得到的问题的约束代价值小于其他所有对比算法。且在EXP-2测试问题上，RDMAD算法Mean值只是略大于AED算法。同时，从统计结果来看，RDMAD算法每次得到的结果都优于 ACO_DCOP、DSA、DSAN和GDBA算法，且在其他测试问题上也具有明显优势，稳定性较高。另外，通过表2中的Wilcoxon符号秩和检验法的结果 $p$ -value也再一次验证了RDMAD算法在求解质量方面优势明显。

图4为所有算法在不同测试问题上的收敛曲线。在五个测试问题上，RDMAD算法均具有优秀的收敛和寻优性能。在EXP-1上，RDMAD 算法相比原来的ACO_DCOP 提高了约 $4 . 2 \%$ ，相比其他算法提高了约 $1 . 3 \% \sim 1 2 . 9 \%$ 。从各算法的收敛曲线可以发现，由于缺乏全局信息，DSA和DSAN算法的寻优能力较差。采用LSGA框架的DSA算法，虽然提高了DSA算法的局部搜索性能，但其对DSA算法的性能提升有限，相比LSGA-DSA算法，RDMAD算法具有更好的收敛性能。另外ACO_DCOP和AED算法都利用了种群对问题进行寻优，但从图中可以发现，RDMAD算法在收敛和寻优质量上比这两种算法表现更好。在EXP-2上，由于测试问题密度过高，agent间的约束增多，因此算法的性能受到一定影响，但RDMAD算法仍能保持较好的寻优性能，其收敛和寻优质量都优于ACODCOP，相比ACODCOP提高了约 $1 . 4 \%$ 。同时RDMAD算法能够得到与LSGA-DSA和AED算法同等质量的解，且收敛优势明显，相比其他算法提高了约 $1 . 1 \% \sim$ $2 . 7 \%$ 。同样的，在 EXP-3 和 EXP-4 上RDMAD 算法优于ACODCOP约 $4 . 4 \%$ 和 $2 . 8 \%$ ，相比其他算法分别提高约 $4 . 1 \%$ $\sim 1 7 . 2 \%$ 和 $0 . 6 \% \sim 8 . 3 \%$ 。可以看出，RDMAD算法在无尺度网络问题上(EXP-3,EXP-4)的表现更优秀，收敛速度也具有明显优势。这表明RDMAD算法在求解结构化问题时性能显著。最后，在EXP-5测试问题上，RDMAD算法同样表现出了良好的收敛和寻优性能，优于ACODCOP约 $1 8 . 4 \%$ ，同时相比其他算法提高了约 $1 8 . 7 \% \sim 6 2 . 7 \%$ 。

表2每个问题在20个实例上的统计结果  
Tab.2Results on 20 instances of each question

Mean±Std Dev 问题 RDMAD ACO_DCOP AED DSA LSGA-DSA PDS-DSA GDBA DSAN   
EXP-1 5340+79.7 5575+82.0 5463+72.6 5991+98.4 5431+71.0 5411+82.2 5797+86.4 6127+81.7 + 20 18 20 17 16 20 20 0 2 0 3 4 0 0   
（20 $p$ -value 0.000 0.001 0.000 0.001 0.007 0.000 0.000   
EXP-2 55439+210.6 56212+205.8 55400+225.0 56524+188.3 55456+211.5 56057+199.7 56129+149.9 57002+187.6 + 20 10 20 9 20 20 20 0 10 0 11 0 0 0   
（204号 $p$ -value 0.000 0.601 0.000 0.709 0.000 0.000 0.000   
EXP-3 3648+81.9 3816+69.3 3853+61.8 4360+76.9 3845+77.1 3804+80.4 4137+75.6 4408+61.9 + 20 18 20 19 17 20 20 0 2 0 1 3 0 0   
（20 $p$ -value 0.000 0.000 0.000 0.000 0.000 0.000 0.000   
EXP-4 12334+92.0 12684+126.5 12424+101.9 13160+139.2 12413+90.3 12589+106.3 12935+101.1 13449+73.2 + 20 17 20 15 20 20 20 0 3 0 5 0 0 0   
（20 $p$ -value 0.000 0.010 0.000 0.025 0.000 0.000 0.000   
EXP-5 279+29.3 342+36.4 343+31.9 747+45.7 396+31.5 372+31.7 476+41.1 693+44.7 + 20 17 20 20 19 20 20 0 3 0 0 1 0 0   
p-value 0.000 0.000 0.000 0.000 0.000 0.000 0.000 6.8x103 EXP-1 6.2x104 EXP-2 5.0x10 EXP-3 RDMAD RDMAD RDMAD 6.6 ACOADCOP 6.1 ACO_DCOP 4.8 ACOLDCOP 6.4 AEA 6.0 EA 4.6 E S PA DSASA PANSA 5.6 5.7 4.0 5.4 5.6 3.8 5.2 5.5 3.6 0 100 200 300 400 500600 700 800 0 100 200 300 400 500 600 700 800 0 100200 300400 500600700800 迭代轮次 迭代轮次 迭代轮次 (a)EXP-1上的实验对比结果 (b)EXP-2上的实验对比结果 (c)EXP-3上的实验对比结果 1.41 ×104 EXP-4 1000 EXP-5 RDMAD RDMAD 1.38 ASOADCOP 900 LSGA-DSA ACO_DCOP AED ↓ AED DSA 800 DSA PANSA DSAISA 1.29 500 1.26 400 300 1.23 0 100200 300400500 600 700800 0 100 200 300 400 500600700800 迭代轮次 迭代轮次 (d)EXP-4上的实验对比结果 (e)EXP-5上的实验对比结果

# 4 结束语

有效利用群体智能求解分布式约束优化问题，是提高DCOP求解算法性能的新思路，本文提出了一种基于多种群的随机扰动蚁群算法求解分布式约束优化问题。该算法首先充分地利用种群特性，通过多种群分工配合分级更新策略更好地平衡算法的探索和开发能力，提高了算法的收敛速度和求解质量。在此基础上利用随机扰动策略增加种群多样性，避免算法陷入局部最优。将RDMAD算法与ACODCOP算法，以及其他6种目前最先进的非完备算法在三类基准问题上进行比较，RDMAD算法在求解质量和收敛速度方面优势显著，且具有良好的稳定性。但是RDMAD缺少对agent局部收敛状态的利用，在以后的工作中将考虑引入信息熵等状态评价指标与随机扰动机制结合。

# 参考文献：

[1] 刘鸿福，陈璟，沈林成．分布式约束满足问题及其在MAS任务分配 中的应用[J].计算机应用研究,2009,26(2):515-517.(Liu Hongfu, Chen Jing,Shen Lincheng.Distributed constraint satisfaction problem and its application to multi-agent system task allocation [J]. Computer Application Research,2009,26 (2): 515-517.)   
[2]Leite R,Fabricio E,Barthes J.Distributed Constraint Optimization Problems:Review and perspectives[J].Expert Systemswith Applications,2014,41 (11): 5139-5157.   
[3] Zhang W,Wang G,Xing Z,et al.Distributed stochastic search and distributed breakout: properties，comparison and applications to constraint optimization problems in sensor networks [J].Artificial Intelligence,2005,161 (1-2): 55-87.   
[4]Sultanik E A,Modi P J,Regli W C. On modeling multiagent task scheduling as a distributed constraint optimization problem [C]. In Proc. of the 20th IJCAI,2007: 1531-1536.   
[5]Hirayama K,Yokoo M.Distributed partial constraint satisfaction problem [C].Principles and Practice of Constraint Programming-CP97. Springer Berlin Heidelberg,1997:222-236   
[6]Gershman A,Meisels A,Zivan R.Asynchronous forward bounding for distributed COPs [J]. Journal of Artificial Intelligence Research,2009, 34 (1): 61-88.   
[7]ModiPJ, Shen WM,Tambe M,et al.ADOPT:Asynchronous distributed constraint optimization with quality guarantees [J]. Artificial Intelligence, 2005,161(1): 149-180.   
[8]Yeoh W,Felner A,Koenig S. BnB-ADOPT: An asynchronous branchand-bound DCOP algorithm [J].Journal of Artificial Intelligence Research,2010,38:85-133.   
[9] Petcu A,Faltings B.A scalable method for multiagent constraint optimization [C]. IJCAI,2005,5: 266-271.   
[10] Petcu A,Faltings B. Mb-dpop: A new memory-bounded algorithm for distributed optimization [C].In Proceedingsof the twentieth international joint conference on artificial intelligence,2oo7:1452-1457.   
[11] Chen Z, Zhang W, Deng Y,et al. RMB-DPOP: Refining MB-DPOP by Reducing Redundant Inference [C]. In Proceedings of the 19th International Conference on Autonomous Agents and MultiAgent Systems,2020: 249-257.   
[12] Rashik,M.,Rahman,M.M., Khan,M.M.et al. Speeding up distributed pseudo-tree optimization procedures with cross edge consistency to solve DCOPs[J].Appl Intell,2021,51: 1733-1746.   
[13] Okamoto, Zivan, Nahon. Distributed breakout: Beyond satisfaction [C]. In Proceedings of the Twenty-Fifth International Joint Conference on Artificial Intelligence,2016: 447-453. International Joint Conference on Autonomous Agents and Multiagent Systems. DBLP,2008: 1449-1452.   
[15] Chen Z,Yu Z,He J,et al.A partial decision scheme for local search algorithms for distributed constraint optimization problems [C].In Procedings of the l6th international conference on autonomous agents and multiagent systems,2017: 187-194.   
[16] Chen Z,LiuL,He J. et al.A genetic algorithmbased framework for local search algorithms for distributed constraint optimization problems [J]. Auton Agent Multi-Agent Syst,2020,34: 41.   
[17]Farinelli A,Rogers A,Petcu A,et al. Decentralised coordination of lowpower embedded devices using the max-sum algorithm [C]. In Proceedings of the 7th International Conference on Autonomous Agents and Multiagent Systems (AAMAS),Estoril,Portugal,2008: 639-646.   
[18] Zivan R,Peled H. Max/min-sum distributed constraint optimization through value propagation on an alternating DAG [C]. International Conferenceon Autonomous Agents and Multiagent Systems.2012: 265- 272.   
[19] Ottens B, Dimitrakakis C,Faltings B. Duct: An upper confidence bound approach to distributed constraint optimization problems [C].In Proceedings of the 26th conference on Artificial Intelligence (AAAI), Toronto,Canada,2012: 528-533.   
[20] Mahmud S,Choudhury M, Khan M M,et al.AED:An anytime evolutionary DCOP algorithm [C]. In Proceedings of the 19th International Conference on Autonomous Agents and MultiAgent Systems,2020.   
[21] Chen Z,WuT,Deng Y,etal.An ant-based algorithm to solve distributed constraint optimization problems [C]. In Proc.of the 32th AAAI conference on Artificial Intelligence,2018: 4654-4661.   
[22]薛宏全，魏生民，张鹏，等．基于多种群蚁群算法的柔性作业车间调 度研究[J].计算机工程与应用，2013,49 (24):243-248.(Xue Hongquan，Wei Shengmin，Zhang Peng，et al. Flexible job-shop scheduling based on multiple ant colony algorithm [J]. Computer Engineering and Applications,2013,49 (24): 243-248.)   
[23]朱佑滔，何志琴，施文烨．多种群蚁群算法在机械手臂路径规划中 的设计与应用[J]．机械传动,2021,4:160-165.(Zhu Youtao,He Zhiqin,Shi Wenye.Design and Application of Multi-colony Ant Algorithm in Path Planning of Manipulator [J].Journal of Mechanical Transmission,2021,4: 160-165.)   
[24]陈佳，游晓明，刘升，等．结合信息熵的多种群博弈蚁群算法[J]. 计算机工程与应用,2019,55 (16):170-178.(Chen Jia,You Xiaoming, Liu Sheng,et al. Entropy-game based multi-population ant colony optimization [J]. Computer Engineering and Applications,2019,55 (16): 170-178.)   
[25] Zivan R, Okamoto S,Peled H. Explorative anytime local search for distributed constraint optimization [J].Artificial Intelligence,2014,212: 1-26.   
[26] Ziyu Chen, Zhen He, Chen He.An improved DPOP algorithm based on breadth first search pseudo-tree for distributed constraint optimization [J]. Applied Intelligence,2017,47: 607-623.   
[27] Zivan R,Okamoto S,Peled H. Explorative anytime local search for distributed constraint optimization[J].Artificial Intelligence,2014,212: 1-26.   
[28] Barabasi,A-L,Albert R. Emergence of scaling in random networks [J]. Science,1999,286: 509-512.   
[29] Arshad M, Silaghi MC.Distributed simulated annealing[J].Distributed Constraint Problem Solving and Reasoning in Multi-Agent Systems, 2004, 112.