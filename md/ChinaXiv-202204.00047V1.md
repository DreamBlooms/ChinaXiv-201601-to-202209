# 改进布谷鸟算法求解双资源约束柔性车间调度问题

罗浩嘉a，潘大志a,b†

(西华师范大学 a.数学与信息学院;b.计算方法与应用研究所，四川 南充 637009)

摘要：针对双资源约束的柔性车间调度问题(DRCFJSP)，以优化最大完工时间为目标，设计出一种具有改进解码方案的布谷鸟算法对其进行求解。由于DRCFJSP除了需要考虑机器的分配，还需要兼顾工人的加工情况，因此改进了传统解码方式以避免机器和工人在加工时间上的冲突，同时在解码时尽可能利用机器和工人的空闲时间。在布谷鸟算法核心框架下，将布谷鸟种群随机划分为3个子群，每个子群采用不同Levy飞行方式独立进行寻优，并通过差分算子实现子群间信息交流，不仅增强了算法的全局搜索能力也平衡了算法的局部搜索能力。最后通过基准测试算例进行实验仿真分析并与其他算法进行对比，验证了改进布谷鸟算法和改进解码方法的有效性优越性。

关键词：柔性车间调度；双资源约束；布谷鸟算法；改进解码方法 中图分类号：TP301.6 doi:10.19734/j.issn.1001-3695.2022.01.0030

Improved cuckoo algorithm for flexible job shop scheduling with dual resource constraints

Luo Haojia,Pan Dazhia, bt (a.SchoolofMathematics &Information,b.InstituteofComputingMethods &Applications China West Normal University, China West Normal University,Nanchong Sichuan 6370o9,China)

Abstract: Aiming atthe flexible job shop scheduling problem with dual resource constraints (DRCFJSP),this paper designs a cuckoo algorithm withanimproveddecoding scheme to solveit with thegoal ofoptimizingthe maximum completion time. Since DRCFJSPneeds to consider the alocationofmachines andthe processing situationof workers,this paper improves the traditional decoding method toavoidtheconflictof procesing time between machines and workers,and makes useof the idle time ofmachines and workers as much as posible during decoding.Under thecore frameworkofthecuckoo algorithm, this paperdivides thecuckoo population into threesubpopulations randomly,andeach subpopulationadopts differentLevy flight methods to search for the optimum independently,and realizes the information exchange between subpopulations throughthediference operator,whichnotonlyenhances the globalsearchabilityofthealgorithmbutalsobalances the local search abilityofthe algorithm.Throughthe experimentalsimulationanalysis ofthe benchmarktestcase,theresults showthe effectiveness and superiority of the improved cuckoo algorithm and the improved decoding method.

Key words: flexible job shop scheduling; dual resource constraints; cuckoo algorithm; improved decoding method

# 0 引言

调度在制造业和服务行业中起着至关重要的作用，作业车间调度问题作为调度中的典型问题，在制造系统领域得到了广泛的关注。近些年也有很多基于作业车间调度的扩展研究，比如带模糊加工时间的车间调度[1,2]、带阻塞问题的车间调度[3\~5]和多目标车间调度[6.7]等，这些扩展研究都是车间调度问题在实际情况中的应用。双资源约束柔性作业车间调度问题(Dual Resource Constrained Flexible Job-shop SchedulingProblem，DRCFJSP)是柔性作业车间调度问题(FlexibleJob-Shop SchedulingProblem，FJSP)的一个扩展，在FJSP的基础上增加了工人这一约束条件,在进行加工时需要兼顾工人和机器的加工情况，因此DRCFJSP比FJSP更接近实际生产情况。近些年来，也有一些元启发式算法对DRCFJSP进行研究，如Li等[8提出了一种分支种群遗传算法，引入了基于扇区分割的轮盘选择算子，利用精英进化算子的优化搜索能力，有效降低了算法复杂度，避免了算法早熟。Zhang 等[针对具有资源灵活性的双资源约束作业车间调度问题，提出了一种新颖的混合离散粒子群优化算法，引入了具有可变邻域结构的改进模拟退火算法，提高了算法的局部搜索能力。Lei等[10]提出了一种有效的变量邻域搜索，通过两个邻域搜索程序依次执行，分别为两个子问题产生新的解决方案，从而增强算法的搜索能力。Zheng 等[1]提出了一种具有新编码方案的知识引导果蝇优化算法来求解最小化完工时间的DRCFJSP，将知识引导搜索和基于气味搜索相结合，平衡了算法全局探索和局部开发能力。

布谷鸟搜索算法(cuckoo search，CS)[12]是由剑桥大学学者Yang和Deb于2009年通过模拟布谷鸟寄生育雏行为提出的一种新型元启发式搜索算法。由于其所用参数少、全局搜索能力强等优点，被普遍应用于连续性优化问题、调度问题、工程优化问题等多个领域。Ouaar 等[13]在不改变布谷鸟算法框架的情况下，将布谷鸟算法离散化，用于求解车间调度问题。ALAA等[14]改进CS算法中的Lévy飞行，加强对种群最优个体领域的搜索，并将改进后的算法用于求解柔性车间调度问题。Majumdera等[15]针对作业准备时间不相等的并行批处理机调度问题，提出了一种混合离散布谷鸟搜索(HDCS)算法来求解其最小完工时间。他们通过将CS算法与变量邻域搜索算法结合，构造了该混合算法，并且对Levy飞行方式进行了改进，对算法的搜索进行了优化。唐红涛等[16在考虑到企业的实际生产情况下，建立了一个调度目标为最大完工时间最小的分布式柔性车间调度模型，通过对布谷鸟算法的编码和初始化策略进行调整以提高初始解的质量，同时对布谷鸟算法的搜索操作进行了改进，在加快算法的收敛速度的同时保证解的质量。罗函明等[17]在求解混合流水车间调度问题时，将布谷鸟算法进行离散化，并改进其解码方式，提高解的质量。

目前，有关DRCFJSP问题的研究并不算多，但大部分工厂在进行生产时，工人的配合却是必不可少的，因此本文在FJSP问题的基础上，考虑到工厂的实际加工情况，增加了工人约束，通过工人操控机器对工件进行加工。针对以上问题，本文在编码时增加了工人信息，同时将种群分为3个子群，对子群的步长因子进行自适应调整，提高种群多样性。最后对算法解码进行了改进，将工人信息考虑进了算法解码中，并且充分利用解码时产生的空闲时间，以达到缩短算法最终完工时间的目的。通过标准测试集对改进后的算法进行了仿真实验，并与其他算法进行了对比，证明了改进CS算法求解DRCFJSP问题的有效性与稳定性。

# 1 双资源约束柔性车间调度模型

双资源约束的柔性车间调度问题(DRCFJSP)描述如下：$w$ 个工人 $W = \{ W _ { 1 } , W _ { 2 } , . . . , W _ { w } \}$ 操作 $m$ 台机器 $M = \{ M _ { 1 } , M _ { 2 } , \dots , M _ { m } \}$ 对 $n$ 个工件 $J = \{ J _ { 1 } , J _ { 2 } , . . . , J _ { n } \}$ 进行加工，工件 $J _ { i } \left( i { = } 1 , 2 , . . . , n \right)$ 包含确定的 $n _ { i }$ 道工序 $\{ O _ { i , 1 } , O _ { i , 2 } , . . . , O _ { i , n _ { i } } \}$ 。每个操作的加工时间取决于机器和工人分配，不同的机器和工人可能会导致加工时间不同。调度的目标是确定所有工件的加工顺序以及每道工序选用的工人和机器，使得最大完工时间(makespan)最小。DRCFJSP中的符号定义如表1所示。

Tab.1Symbol variable definition   

<html><body><table><tr><td>符号</td><td>定义</td></tr><tr><td>n</td><td>工件总数</td></tr><tr><td>m</td><td>机器总数</td></tr><tr><td>W</td><td>工人总数</td></tr><tr><td>M</td><td>总的机器集</td></tr><tr><td>W</td><td>总的工人集</td></tr><tr><td>Oi.j</td><td>工件i的第j道工序</td></tr><tr><td>SEij</td><td>工序Oij最早开始加工时间</td></tr><tr><td>CEij</td><td>工序Oij最早完工时间</td></tr><tr><td>SLij</td><td>工序Oi.最晚开始加工时间</td></tr><tr><td>CLi</td><td>工序Oi.j最晚完工时间</td></tr><tr><td>Sk</td><td>机器k的开始加工时间</td></tr><tr><td>Fk</td><td>机器k的结束加工时间</td></tr><tr><td>L</td><td>一个足够大的正数</td></tr><tr><td>Tijkw</td><td>工序Oi在机器k上由工人w加工所需时间</td></tr><tr><td>PW[v]</td><td>工序v由同一工人加工的前一道工序，若v为该工人加工 的第一道工序，则PW[v]=-1</td></tr><tr><td>SW[v]</td><td>工序V由同一工人加工的后一道工序，若为该工人加工 的最后一道工序，则SW[v]=-1</td></tr></table></body></html>

决策变量如下：

1，如果工序 $O _ { i j }$ 在机器 $k$ 上由工人 $\mathbf { \Omega } _ { \mathcal { W } }$ 加工Xijkw0，否则1，如果工序 $\cdot O _ { g , h }$ 与工序 $\cdot O _ { i , j }$ 都在机器k 上加工，且工序  
yghijk = （204号 $O _ { g , h }$ 先于工序 $O _ { i , j }$ （204号[0，否则[1，如果工序 $\cdot O _ { g , h }$ 与工序 $\cdot O _ { i , j }$ 都由工人w 加工，且工序  
$z _ { g h i j w } =$ $O _ { g , h }$ 先于工序 $\cdot O _ { i , j }$ （204号[0，否则

以最小化最大完工时间为优化目标建立数学模型，其目

# 标函数为

$$
\operatorname* { m i n } { C _ { \mathrm { m a x } } } = \operatorname* { m a x } \left( C E _ { i , j } \right)
$$

其约束条件如下：

$$
\forall i \in J , \forall j \in J _ { i } , \sum _ { k \in M } \sum _ { w \in W } x _ { i j k w } = 1
$$

$$
\forall i \in J , \forall j \in J _ { i } , C E _ { i , j } = S E _ { i , j } + \sum _ { k \in M } \sum _ { w \in W } \left( T _ { i j k w } x _ { i j k w } \right)
$$

$$
\forall i \in J , \forall j \in J _ { i } , C L _ { i , j } = S L _ { i , j } + \sum _ { k \in M } \sum _ { w \in W } \left( T _ { i j k w } x _ { i j k w } \right)
$$

$$
\forall i \in J , \forall j \in J \left\{ 1 , 2 , . . . , n _ { i } - 1 \right\} , C E _ { i , j } \leq S E _ { i , j + 1 }
$$

$$
\begin{array} { r } { \forall g , i \in J , \forall h \in J _ { g } , \forall j \in J _ { i } , \forall k \in M , C E _ { g , h } \leq S E _ { i , j } + L \big ( 1 - y _ { g h i j k } \big ) } \end{array}
$$

$$
\begin{array} { r } { \forall g , i \in J , \forall h \in J _ { g } , \forall j \in J _ { i } , \forall w \in W , C E _ { g , h } \leq S E _ { i , j } + L \big ( 1 - z _ { g h i j w } \big ) } \end{array}
$$

$$
\forall k \in M , S _ { k } \geq 0
$$

$$
\forall k \in M , \forall i \in J , \forall j \in J _ { i } , \forall w \in W , S _ { k } \leq S E _ { i , j } + L \big ( 1 - x _ { i j k w } \big )
$$

$$
\forall k \in M , \forall i \in J , \forall j \in J _ { i } , \forall w \in W , C E _ { i , j } \cdot x _ { i j k w } \leq F _ { k }
$$

若 $P W [ O _ { i , j } ] = - 1$ ，令 $C E _ { P W [ O _ { i , j } ] } = 0$ ，则有 $\forall i \in J , \forall j \in J _ { i }$

$$
S E _ { i , j } = \operatorname* { m a x } ( C E _ { P M [ O _ { i , j } ] } , C E _ { P J [ O _ { i , j } ] } , \sum _ { k \in M } \sum _ { w \in W } S _ { k } \cdot x _ { i j k w } )
$$

若 $S W [ O _ { i , j } ] = - 1$ ，令 $S L _ { \mathrm { { S W } [ } O _ { i , j } \mathrm { { l } } ] } = C _ { \mathrm { { m a x } } }$ ，则有 $\forall i \in J , \forall j \in J _ { i }$

$$
C L _ { i , j } = \operatorname* { m a x } ( S L _ { S M [ O _ { i , j } ] } , S L _ { S J [ O _ { i , j } ] } , S L _ { S W [ O _ { i , j } ] } )
$$

式(1)表示每个工序只能在一台机器上由一个工人进行加工；式(2)表示每个工序的最早完工时间等于该工序最早开始加工时间与所需加工时间之和；式(3)表示最晚完工时间等于最晚开始加工时间与所需加工时间之和；式(4)表示同一工件上工序加工的先后顺序约束；式(5)表示每个机器任一时刻最多只能加工一道工序；式(6)表示每个工人任一时刻最多只能加工一道工序；式(7)表示所有机器不能提前进行工作，从0时刻开始可用；式(8)工件在机器上进行加工时机器必须是空闲的；式(9)机器必须在加工结束后才能停止，中途不能停止；式(10)计算工序最早开始加工时间；式(11)计算工序最晚完工时间。

表2为一个DRCFJSP问题实例，该实例由三个工件三个机器和两个工人构成。表中给出了每道工序在某个机器上由某个工人加工所需的时间，其中“-”表示对应工人无法操作对应机器对该工序进行加工。例如， $O _ { 1 , 1 }$ 无法由工人 $W _ { 1 }$ 在机器 $\boldsymbol { M } _ { \mathrm { ~ l ~ } }$ 上进行加工，但 $O _ { \mathrm { { l } , \mathrm { { l } } } }$ 可以由工人 $W _ { 1 }$ 在 $M$ 2上进行加工且所需加工时间为1。

表1符号变量定义  
表2DRCFJSP 问题实例  
Tab.2Examples of DRCFJSP problems   

<html><body><table><tr><td rowspan="2">Job</td><td rowspan="2"></td><td colspan="3">W</td><td colspan="3">W</td></tr><tr><td>M</td><td>M</td><td>M</td><td>M</td><td>M</td><td>M3</td></tr><tr><td rowspan="2">J</td><td>0</td><td>-</td><td>1</td><td>-</td><td>-</td><td>1</td><td>6</td></tr><tr><td>01.2</td><td></td><td>2</td><td>-</td><td>-</td><td>2</td><td>2</td></tr><tr><td rowspan="2">J</td><td>02.1</td><td>5</td><td></td><td>-</td><td>-</td><td>-</td><td>2</td></tr><tr><td>02.2</td><td>4</td><td></td><td>-</td><td>-</td><td>-</td><td>3</td></tr><tr><td rowspan="3">J</td><td>03.1</td><td>4</td><td>6</td><td>-</td><td>-</td><td>6</td><td></td></tr><tr><td>03.2</td><td>2</td><td>2</td><td>-</td><td>-</td><td>2</td><td></td></tr><tr><td>03.3</td><td>6</td><td>4</td><td></td><td></td><td>4</td><td>1</td></tr></table></body></html>

# 2 改进布谷鸟算法求解DRCFJSP

# 2.1布谷鸟算法

布谷鸟算法作为一种新型启发式搜索算法，主要基于两个更新策略：一是通过Levy飞行机制寻找寄生巢穴，二是通过偏好随机游走策略代替被发现的鸟巢。在布谷鸟算法中每一个鸟巢代表一个可行解。在理想状态下，布谷鸟的位置更新公式如下：

$$
X _ { i } ^ { t + 1 } = X _ { i } ^ { \prime } + \alpha \oplus L e \nu y ( \beta )
$$

其中， $X _ { i } ^ { t }$ 表示第 $i ( i = 1 , 2 , . . . , n )$ 个鸟巢在第 $t$ 代的位置； $\oplus$ 为点对

点乘法； $\alpha$ 通常取值为 $\scriptstyle { \alpha = 1 }$ 。 $L e \nu y ( \beta )$ 为随机搜索路径，服从levy分布：

$$
L e \nu y ( \beta ) \sim \mu = t ^ { - \beta } , 1 < \beta \leq 3
$$

为方便运算，文献[12]使用式(13)产生levy随机数：

$$
L e \nu y ( \beta ) = \frac { \phi \times \mu } { | \boldsymbol { \upsilon } | ^ { \frac { 1 } { \beta } } }
$$

其中， $\mu$ 和 $\upsilon$ 均服从标准正态分布， $\beta = 1 . 5$ 。

$$
\phi = \left( \frac { \Gamma ( 1 + \beta ) \times \sin ( \pi \times \displaystyle \frac { \beta } { 2 } ) } { \Gamma ( ( \displaystyle \frac { 1 + \beta } { 2 } ) \times \beta \times 2 ^ { \frac { \beta - 1 } { 2 } } ) } \right) ^ { \frac { 1 } { \beta } }
$$

综合上述公式，布谷鸟的位置更新公式如下：

$$
X _ { i } ^ { t + 1 } = X _ { i } ^ { t } + \alpha _ { 0 } \times \frac { \phi \times \mu } { | \upsilon | ^ { \frac { 1 } { \beta } } } ( X _ { i } ^ { t } - X _ { b e s t } )
$$

按发现概率 $P _ { a }$ 丢弃部分解后，采用偏好随机游走重新生成相同数量的新解，公式如下：

$$
X _ { i } ^ { t + 1 } = X _ { i } ^ { t } + \gamma ( X _ { g } ^ { t } - X _ { k } ^ { t } )
$$

其中， $\gamma$ 是服从均匀分布的缩放因子， $X _ { g } ^ { t } , X _ { k } ^ { t }$ 表示第 $t$ 代的两个随机数。

# 2.2算法编码

由于标准布谷鸟算法适用于解决连续性优化问题，无法直接将其用于解决车间调度问题，因此本文引入最小位置规则(smallest position value,SPV)来建立个体与实际调度的映射关系。如图1所示，SPV规则是将原向量进行升序排列得到新向量，新向量中各分量所对应的原向量中的位置即为整数编码序列。本文在算法编码时先随机生成工序加工序列(OS)，然后根据所生成的加工序列，对机器和工人进行分配。整个算法包含了三层序列，第一层是工序加工序列(OS)，第二层是机器分配序列(MA)，第三层是工人分配序列(WA)。该编码由表1的问题实例得出，表示3个工件由2个工人在3台机器上加工的调度，其中工件1包含2道工序、工件2包含2道工序，工件3包含3道工序，工件的加工顺序为：$O _ { 2 , 1 }  O _ { 2 , 2 }  O _ { 3 , 1 }  O _ { 1 , 1 }  O _ { 1 , 2 }  \ O _ { 3 , 2 }  O _ { 3 , 3 }$ 。结合整个序列可知，工序$O _ { 2 , 1 }$ 由工人2在机器3上加工，工序 $O _ { 2 , 2 }$ 由工人2在机器3上加工，工序 $O _ { 3 , 1 }$ 由工人1在机器2上加工，其余工序依此类推。

编码带 1 1 2 2 3 3 3  
随机值 0.21 0.37 -0.24 -0.55 0.81 0.66 0.15SPV 升序排列  
随机值 -0.55 -0.24 0.15 0.21 0.37 0.66 0.81  
编码带 2 2 3 1 1 3 3分配机器工人OS 2 2 3 1 1 3 3$O _ { 2 , \mathrm { l } }$ $O _ { 2 , 2 }$ 中 $O _ { 3 , 1 }$ $O _ { \parallel , \parallel }$ $O _ { 1 , 2 }$ 中 $O _ { 3 , 2 }$ 中 $O _ { 3 , 3 }$ WA 2 2 1 1 1 2 2$W _ { 2 }$ ${ \underline { { W _ { 2 } } } }$ $W _ { \parallel }$ 中 $W _ { 1 }$ 中 $W _ { 1 }$ 中 $W _ { 2 }$ $W _ { 2 }$ MA 3 3 2 2 2 1 3M $M _ { 3 }$ $M _ { ☉ }$ $M _ { ☉ }$ 1 $M _ { 2 }$ （24号 $M _ { \mathrm { 1 } }$ （24 M

# 2.3 改进解码算法

相比于单资源约束的FJSP问题，DRCFJSP在加工时不仅受前一道工序的结束时间和机器最早可开始加工时间的约束，还受到工人最早可开始加工时间的约束。因此本文通过对插入式解码方案进行改进，得到一种可以同时对机器和工人进行主动解码的改进解码方案，改进解码方案的核心是有效利用机器和工人加工时产生的空闲时间，将机器和工人提前安排到合适的空闲时间段内进行加工，以达到缩短整个加工时间的目的。记工件i的第 $j$ 道工序 $O _ { i j }$ 的开始加工时间为$S T _ { i j }$ ，结束加工时间为 $E T _ { i j }$ ，该工序的紧前完工时间为 $E T _ { i , j - 1 }$ ，工人 $s$ 操作机器 $k$ 对工序 $O _ { i j }$ 加工所需时间为 $T _ { i j k s }$ 。在解码时首先需要判断所选机器和工人的加工情况，再根据加工情况判断是否有空闲时间以及空闲时间是否满足插入条件。当机器和工人均有空闲时间时，有以下三种可能出现的情况：

情况一：如图2所示，机器和工人的空闲时间不重合，因此无法进行插入操作。

![](images/72dbccd7bd12c4edc9bda7e351050726dda241b86e60e186da66a09ef19e48d8.jpg)  
图2第一种情况

情况二：如图3所示，机器和工人有重合的空闲时间段$T _ { a }$ ，但 $\textstyle T _ { a }$ 小于工序所需加工时间 $T _ { i j k s }$ ，即 $T _ { a } < T _ { i j k s }$ ，因此无法进行插入操作。

![](images/cb4f7648eaf36cabd12419fc0e924de1e0616557e435a07573ed9a44de9735ac.jpg)  
Fig.2The first situation   
图3第二种情况

情况三：如图4所示，机器和工人有重合的空闲时间段$T _ { a }$ ，且 ${ \cal T } _ { a }$ 大于等于工序所需加工时间 $T _ { i j k s }$ ，即 $T _ { a } \ge T _ { i j k s }$ ，因此可以进行插入操作。

![](images/58b9b5c7db587263b583ada9fc4e84c2cb2cdfde25138dc4b0ebc25c857c53b5.jpg)  
图1算法编码过程  
Fig.1Algorithm coding process   
Fig.3The second situation   
图4第三种情况  
Fig.4The third situation

综合解码时可能出现的所有情况，本文给出了解码算法的伪代码，如算法1所示。

算法1改进解码方法伪代码输入：总工序数 $T P$ ，机器和工人可加工信息。

输出：工序开始时间 $S T _ { i j }$ 和完工时间 $E T _ { i j }$ ，机器加工时间 $[ S M _ { k } , E M _ { k } ]$ 工人加工时间 $[ S W _ { s } , E W _ { s } ]$ 。

1:For $t p = 1$ to $T P$

2： $O _ { i j } = O S ( t p ) ; f l a g = 0$ ；%flag 用于判断是否插入空闲时间

3：获取 $O _ { i j }$ 可选的加工机器和工人 $s$ ，加工所需时间 $T _ { i j k s }$ ；

4：机器 $k$ 和工人 $s$ 的加工时间 $[ S M _ { k } , E M _ { k } ] _ { \setminus } [ S W _ { s } , E W _ { s } ]$ 和对应空闲时间 $[ A S M _ { k } , A E M _ { k } ] _ { \setminus } [ A S W _ { s } , A E W _ { s } ]$ ：

5:If $j = 1$ %工件第一道工序

6:If $[ S M _ { k } , E M _ { k } ] { = } { = } { \emptyset }$ && $[ S W _ { s } , E W _ { s } ] = \emptyset$ %工人和机器都还未进行加工

7: $S T _ { i j } = 0 \ ; \ E T _ { i j } = S T _ { i j } + T _ { i j k s } k \quad \mathrm { ~ ; ~ } f l a g = 1 \ ;$

8: End If

9:Else

10: If $[ A S M _ { k } , A E M _ { k } ] \sim = \emptyset$ && $[ A S W _ { s } , A E W _ { s } ] = \emptyset$ %机器有空闲时间，工人无空闲时间

11: If $A S M _ { k } > = \operatorname* { m a x } \{ E W _ { s } \}$ && $A S M _ { k } > = E T _ { i , j - 1 }$ && $A S M _ { k } + T _ { i j k s } < = A E M _ { k }$

12: $ S T _ { i j } = A S M _ { k } \textbf { ; } E T _ { i j } = S T _ { i j } + T _ { i j k s } \textbf { ; } f l a g = 1 \textbf { ; }$ （204号  
13: End If  
14: Else If $[ A S M _ { k } , A E M _ { k } ] { = } \emptyset$ && $[ A S W _ { s } , A E W _ { s } ] \sim = \emptyset$ %机  
器无空闲时间，工人有空闲时间  
15: $\mathbf { I } \mathbf { f } \ A S W _ { s } > = \operatorname* { m a x } \{ E M _ { k } \}$ && $A S W _ { s } > = E T _ { i , j - 1 }$ && $A S W _ { s } + T _ { i j k s } < = A E W _ { s }$   
16: $ S T _ { i j } = A S W _ { s } \textbf { ; } E T _ { i j } = S T _ { i j } + T _ { i j k s } \textbf { ; } f l a g = 1 \textbf { j }$ （204号  
17: End If  
18: Else If $[ A S M _ { k } , A E M _ { k } ] \sim = \emptyset$ && $[ A S W _ { s } , A E W _ { s } ] \sim = \emptyset$ %机  
器和工人均有空闲时间  
19: $\mathbf { I } \mathbf { f } \operatorname* { m a x } ( A S M _ { k } , A S W _ { s } ) > = E T _ { i , j - 1 } \ \& \& \operatorname { m a x } ( A S M _ { k } , A S W _ { s } ) + T _ { i j k s } < =$   
$\operatorname* { m i n } ( A E M _ { k } , A E W _ { s } )$ （204  
20: $S T _ { i j } = \operatorname * { m a x } \{ A S M _ { k } , A S W _ { s } \} \ : ; \ : E T _ { i j } = S T _ { i j } + T _ { i j k s } \ : \ ; \ : f l a g = 1 \ : ;$   
21: End If  
22: Else $\%$ 机器和工人均无空闲时间  
23: $S T _ { i j } = \operatorname * { m a x } \{ E T _ { i , j - 1 } , E M _ { k } , E W _ { s } \} \ ; \ E T _ { i j } = S T _ { i j } + T _ { i j k s } \ ; \ f l a g = 1 \ ;$   
24: End If  
25: End If  
26:If $f l a g = 0$   
27: $S T _ { i j } = \operatorname * { m a x } \{ E T _ { i , j - 1 } , E M _ { k } , E W _ { s } \} \ ; \ E T _ { i j } = S T _ { i j } + T _ { i j k s } \ ; \ f l a g = 1 \ ;$   
28: End If  
29: 更新工序 $O _ { i j }$ 的最早完工时间 $E T _ { i j }$ 以及机器 $k$ 和工人 $s$ 的加工时  
间和空闲时间;  
30: End For

# 2.4算法更新

2.4.1改进Levy飞行

在标准布谷鸟搜索算法中，Levy飞行的步长越长搜索精度越低，适用于全局探索，步长越短搜索精度越高，局部搜索能力越强。由于标准Levy飞行的步长因子是一个固定值，缺乏自适应性，可能导致算法在搜索时搜索速度慢且容易陷入局部最优。针对这种情况，本文采用两种方法对步长因子进行改进，通过将布谷鸟种群随机划分为三个子群，三个子群分别采用固定步长因子的Levy飞行方式与两种改进自适应步长因子的Levy飞行方式进行独立的更新操作。根据不同搜索阶段种群的搜索情况，自动调整步长因子的大小，以达到平衡全局寻优速率和搜索精度的关系的目的。

其中，第一种改进方法如式(18)所示，根据当前鸟巢与当前最优鸟巢的位置关系，对步长因子 $\alpha$ 进行自适应调整，使得Lévy飞行在当前最优鸟巢附近进行较为细致的搜索，有利于锁定全局最优解。

$$
\alpha = \alpha _ { 0 } \times ( X _ { i } ^ { t } - X _ { b e s t } )
$$

其中， $\alpha _ { 0 }$ 通常取值为 $0 . 0 1$ ， $X _ { i } ^ { \prime }$ 表示第 $t$ 代的第 $i$ 个鸟巢位置，$X _ { b e s t }$ 表示当前最优鸟巢位置。

第二种改进方法如式(19)所示，采用了文献[18]提出的改进方式，主要通过算法的迭代次数对步长因子 $\alpha$ 进行控制。在算法初期，步长因子 $\alpha$ 的值较大，搜索范围也大，降低了算法陷入局部最优的可能，到了算法后期，步长自适应减小，搜索精度得到了提高，更利于找到最优解：

$$
\alpha = ( \alpha _ { \mathrm { m a x } } + \alpha _ { \gamma } ) \times \cos \biggl ( \frac { t _ { i } } { t _ { \mathrm { m a x } } } \biggr )
$$

其中， $t _ { i }$ 表示当前迭代次数， $t _ { \mathrm { m a x } }$ 表示迭代总次数，取 $\alpha _ { \mathrm { m a x } } = 0 . 9$ ，$\alpha _ { \gamma }$ 为[-0.05,0.05]上随机步长因子。

# 2.4.2信息交流

由于三个子群是分别独立的进行寻优操作，为了提高寻优效率，每进化 $k$ 代后，各个种群之间通过一定的策略进行种群间个体的信息交流，以交换种群信息,保持种群的多样性。信息交流的原则是：将子群中的较差个体与最优个体进行信息交流,从而引导较差个体向全局最优个体位置进行搜索。本文引入差分进化算法的DE/best/1变异策略对子群进行差分，

其计算公式如下：$V _ { i , g } = X _ { b e s t , g } + F ( X _ { r 1 , g } - X _ { r 2 , g } )$ (20)  
其中， $X _ { b e s t , g }$ 表示当前全局最优个体， $X _ { r 1 , g }$ ， $X _ { r 2 , g }$ 表示子群中  
较差的两个个体。改进后的布谷鸟算法如算法2所示。算法2改进布谷鸟算法更新伪代码输入：迭代次数iter，子群inest。输出：当前最优鸟巢信息 $X _ { b e s t , g }$ 。1:For $i = 1$ to iter2: Forinest $^ { = 1 }$ to33: 每个子群采用不同步长因子的Levy飞行进行更新，步长因子更新式(12)(18)(19);4: 对鸟巢进行评价并按照概率 $P _ { a }$ 舍弃较差的鸟巢，采用式(17)生成相同数量的新鸟巢；5: End For6: 对这一代鸟巢进行评价，更新当前最优鸟巢信息 $X _ { b e s t , g }$ ：7: If $i / k = 0$ 8: 按照式(20)对子群进行差分；9: End If10:End For

# 2.5算法流程

Step1初始化参数，布谷鸟种群数目 $n$ ，最大迭代次数iter，发现概率 $P _ { a }$ 。

Step2初始化种群，根据映射规则，将鸟巢信息转换为包含调度信息的可行序列，采用改进解码算法对其进行解码得到完工时间，保留当前最优鸟巢，并随机将种群分为3个子群。

Step3分别采用标准Lévy飞行公式和两种改进Levy飞行公式更新子群鸟巢位置，解码得到完工时间，更新当前最优鸟巢。按照式(17)进行偏好随机游走，淘汰部分差的解并生成相同数量的新解。

Step4每迭代k次，引入差分算子来实现三个子群之间的信息交流，用改进解码算法对其进行解码得到完工时间，更新当前最优鸟巢。

Step5当达到最大迭代次数则输出全局最优解，否则转到Step3继续进行迭代。

# 3 实例仿真与分析

# 3.1实验环境和测试实例

本文采用 Matlab R2018a 编程，运行环境为 Intel(R)Xeon(R) CPU E5- $@ 3 . 3 0 \mathrm { G H z }$ ，RAM8GB。考虑到目前针对DCRFJSP的研究成果较少，且没有标准算例可供参考比较，为了更好的通过比较实验结果来验证算法的性能，本文选择Brandimarte[19]标准测试集中的MK1-MK10算例对算法进行测试，同时根据文献[11]中的工人分配方式进行仿真实验，具体工人机器分配情况如表3所示。

# 3.2 结果和分析

由于算法的参数对算法的性能以及运行时间有很大影响为了保证算法以较优的状态运行，本文引入文献[20]所采用的正交实验法对参数进行设置。图5为不同参数情况下，本文算法求解MK01算例，运行10次的平均值变化趋势图。图5(a)为最大迭代次数iter的影响曲线图，从图中可以看出，当迭代次数设置较小时，可能导致算法在尚未收敛的情况下被迫停止，从而影响算法的寻优结果，随着迭代次数的增加，获得的解的质量也逐渐提高，但是当迭代次数到了某一值后，继续增加迭代次数并不能明显提高取得最优解的次数，还会增加算法的复杂度，因此在保证运行效率的基础上，设置最大迭代次数 $i t e r = 2 0 0$ 。图5(b)可以看出，当种群规模在50左右，能获得比较优秀的解，因此设置种群数量 $\scriptstyle n = 5 0$ 。图5(c)为发现概率 $p a$ 的影响曲线图，当发现概率在0.25左右时，得到的解最优，随着发现概率逐渐增大，得到的解的质量也逐渐降低，因此最终设置发现概率 $p a = 0 . 2 5$ 0

Tab.3Worker and Machine Allocation

表3工人和机器分配  

<html><body><table><tr><td>Instance</td><td>W</td><td>Allocation</td></tr><tr><td>MK1-2</td><td>4</td><td>M(W)={M,M,M5},M(W2)={M,M4,M5}, M(W3)={M,M4,M6},M(W4)={M,M,M4} M(Wi)={M,,M5},M(W)={M,M4},</td></tr><tr><td>MK3-4</td><td>6</td><td>M(W3)={M,M4,M6},M(W4)={M,M,M,M}, M(W5)={M6,M,M8},M(W6)={M5,M8}</td></tr><tr><td>MK5</td><td>3</td><td>M(W)={M,,M,M4},M(W2)={M,M4}, M(W)={M,M2,M3} M(W)={M,M,Mo},M(W2)={M,M,M11},</td></tr><tr><td>MK6,10</td><td>8</td><td>M(W3)={M,M4,M,M1},M(W4)={M,M,,M12,M13}, M(W5)={M6,M,Mg,M15},M(W6)={M5,Mg,M1o}, M(W)={M4,M,,M14,M15},M(W8)={M,,M,M,M14}</td></tr><tr><td>MK7,11</td><td>4</td><td>M(W)={M,M,M5},M(W2)={M,M4}, M(W3)={M,M4},M(W4)={M,M,M5} M(Wi)={M,M,M5},M(W2)={M,M4,M},</td></tr><tr><td>MK8,9,12, 13</td><td>6</td><td>M(W3)={M,M4,M,M1o},M(W4)={M,M,M}, M(W5)={M5,M6,M},M(W6)={M,M4,Mg,M10} 种群规模n 47.5</td></tr><tr><td>46.5 AAC 45.5</td><td></td><td>47 46</td></tr><tr><td>50 48 47.5</td><td>100 150 (a)</td><td>(b) 发现概率pa</td></tr><tr><td>AAC</td><td></td><td></td><td></td></tr><tr><td>47 46.5 0.2</td><td>0.3 0.4</td><td>0.5</td><td>0.7 0.8</td></tr></table></body></html>

图5参数影响趋势图

为测试本文算法的有效性，将其与不同的算法进行了比较，每个算例连续充分实验20次，记录多次实验的结果并进行分析，仿真实验结果见表4。其中，VNS、KGFOA和MBSA分别为文献[10]、文献[11]和文献[21]中提出的算法求解DRCFJSP所得的最优值；ICS为普通解码方式的改进布谷鸟算法求解所得的最优值；CSND为具有改进解码方式的标准布谷鸟算法求解所得的最优值；ICSND为本文采用的具有改进解码方式的改进布谷鸟算法求解所得的最优值。

从表4可以看出，在仅对布谷鸟算法进行改进的情况下，当问题规模较小时，容易得到比较优秀的值；但是当问题规模逐渐增大，机器和工人空闲时间也随之增多，普通的解码方式无法有效利用这些空闲时间，因此仅靠改进布谷鸟算法已经无法得到更好的解。对于CSND，由于布谷鸟算法本身具有一定的优越性，能较好地兼顾全局和局部搜索，再加上改进解码方式有效的缩短了完工时间，求解的效率也得到了一定的提升。对于本文所使用的ICSND，不仅对布谷鸟算法进行了改进，增强了算法的搜索能力，还对解码方式进行了调整，有效利用了工人和机器的空闲时间，极大的缩短了完工时间，将ICSND与其他算法进行对比，可以发现在大部分算例的求解上，ICSND都能得到更优的解。

表4不同算法求解Brandimarte算例的结果对比

'ab.4Comparison of the results of different algorithms for solvin   

<html><body><table><tr><td colspan="6">the Brandimarte example</td></tr><tr><td>Instance</td><td>VNS</td><td>KGFOA</td><td>MBSA ICS</td><td>CSND</td><td>ICSND</td></tr><tr><td>MK1</td><td>63</td><td>61</td><td>47 49</td><td>46</td><td>44</td></tr><tr><td>MK2</td><td>51 52</td><td>39</td><td>40</td><td>40</td><td>38</td></tr><tr><td>MK3</td><td>204 204</td><td>204</td><td>213</td><td>204</td><td>204</td></tr><tr><td>MK4</td><td>69 67</td><td>79</td><td>80</td><td>75</td><td>67</td></tr><tr><td>MK5</td><td>337 287</td><td>239</td><td>244</td><td>237</td><td>235</td></tr><tr><td>MK6</td><td>89 86</td><td>75</td><td>82</td><td>76</td><td>73</td></tr><tr><td>MK7</td><td>184 184</td><td>185</td><td>198</td><td>185</td><td>181</td></tr><tr><td>MK8</td><td>536 551</td><td>561</td><td>612</td><td>572</td><td>557</td></tr><tr><td>MK9</td><td>437 407</td><td>407</td><td>457</td><td>436</td><td>430</td></tr><tr><td>MK10</td><td>328</td><td>315</td><td>311 332</td><td>292</td><td>290</td></tr></table></body></html>

图6和图7为采用本文ICSND算法求解算例MK1和MK2所得的甘特图，其中，横坐标为加工时长，纵坐标为机器，方框里的第一个数字表示工件，第二个数字表示对应的工人。

![](images/e6e5264163fe52fe897caa909e88c826c21b7544cc7e9ebcca40c07bc4fc3862.jpg)  
图6MK1甘特图

![](images/f8ee00991bcfab10033293fa96341c8dbb1e4313c6f459e047fdaa65e1e36b4e.jpg)  
Fig.5Parameter influence trend graph   
Fig.6MK1 gantt chart   
图7MK2甘特图  
Fig.7MK2 gantt chart

为了更好的衡量本文所使用的算法性能，引入文献[10]所使用的相对百分比偏差最优值 $M R P D$ 和相对百分比偏差平均值 $A R P D$ 这两个指标来评估算法能力，计算公式为

$$
M R P D = \operatorname* { m i n } \left( \frac { C _ { \operatorname* { m a x } } - C _ { \operatorname* { m a x } } ^ { l o w } } { C _ { \operatorname* { m a x } } ^ { l o w } } \times 1 0 0 \right)
$$

$$
A R P D = \frac { 1 } { s } \sum _ { i = 1 } ^ { s } \Biggl ( \frac { C _ { \mathrm { m a x } } - C _ { \mathrm { m a x } } ^ { l o w } } { C _ { \mathrm { m a x } } ^ { l o w } } \times 1 0 0 \Biggr )
$$

其中， $C _ { \mathrm { m a x } }$ 为各个算法求出的最优解， $C _ { \mathrm { m a x } } ^ { l o w }$ 为本文求出的最优解。

从表5可以看出，采用了改进解码方式的算法MRPD和ARPD都优于普通解码方式的算法，而ICSND无论从解的质量还是最优解的获取都优于CSND，改进后的布谷鸟算法性能整体优于标准布谷鸟算法，具有更强的搜索能力。表6通过将ICSND与VNS、KGFOA和MBSA的实验结果进行对比可以看出，ICSND 的最小百分比偏差都为0，并且平均百分比偏差也更小，得到的解更加稳定，质量也比较好。而其他三种算法，在大部分情况下的求解质量都不如ICSND算法，平均百分比偏差的值也更大。因此相对于其他三种算法，ICSND算法具有更好的求解能力，在求解DRCFJSP问题时的稳定性和解的质量都更优。

Tab.5Comparative analysis between different cuckoo algorithms   

<html><body><table><tr><td rowspan="2">Instance</td><td rowspan="2">Cmax</td><td colspan="2">ICSND</td><td colspan="2">ICSND</td><td colspan="2">ICS</td></tr><tr><td>MRPD</td><td>MRPD</td><td>MRPD</td><td>ARPD</td><td>MRPD</td><td>ARPD</td></tr><tr><td>MK1</td><td>44</td><td>0</td><td>3.11</td><td>0</td><td>6.44</td><td>8.89</td><td>14.67</td></tr><tr><td>MK2</td><td>38</td><td>0</td><td>2.37</td><td>2.63</td><td>4.2</td><td>5.26</td><td>10.26</td></tr><tr><td>MK3</td><td>204</td><td>0</td><td>2.45</td><td>0</td><td>3.34</td><td>5.39</td><td>10.69</td></tr><tr><td>MK4</td><td>67</td><td>0</td><td>4.10</td><td>10.45</td><td>18.20</td><td>20.89</td><td>24.93</td></tr><tr><td>MK5</td><td>235</td><td>0</td><td>8.89</td><td>1.70</td><td>2.46</td><td>4.68</td><td>6.09</td></tr><tr><td>MK6</td><td>73</td><td>0</td><td>2.73</td><td>2.73</td><td>4.52</td><td>13.69</td><td>16.98</td></tr><tr><td>MK7</td><td>181</td><td>0</td><td>2.70</td><td>2.21</td><td>3.20</td><td>6.07</td><td>9.66</td></tr><tr><td>MK8</td><td>557</td><td>0</td><td>2.52</td><td>2.49</td><td>4.12</td><td>8.71</td><td>12.72</td></tr><tr><td>MK9</td><td>430</td><td>0</td><td>1.03</td><td>0.69</td><td>2.14</td><td>10.80</td><td>12.48</td></tr><tr><td>MK10</td><td>290</td><td>0</td><td>0.89</td><td>0.34</td><td>1.44</td><td>9.31</td><td>11.31</td></tr></table></body></html>

表6布谷鸟算法和其他三种算法的对比分析

表5不同布谷鸟算法之间的对比分析  
Tab.6Comparative analysis of the cuckoo algorithm and the other three algorithms   

<html><body><table><tr><td rowspan="2">Instance</td><td rowspan="2">mxnxw</td><td rowspan="2">Clow</td><td colspan="2">ICSND</td><td colspan="2">VNS</td><td colspan="2">KGFOA</td><td colspan="2">MBSA</td></tr><tr><td>maxMRPD</td><td>ARPD</td><td>MRPD</td><td>ARPD</td><td>MRPD</td><td>ARPD</td><td>MRPD</td><td>ARPD</td></tr><tr><td>MK1</td><td>10×6×4</td><td>44</td><td>0</td><td>3.11</td><td>35.55</td><td>58.76</td><td>40.00</td><td>46.67</td><td>0</td><td>5.11</td></tr><tr><td>MK2</td><td>10×6×4</td><td>38</td><td>0</td><td>2.37</td><td>36.84</td><td>68.38</td><td>34.21</td><td>47.36</td><td>0</td><td>2.89</td></tr><tr><td>MK3</td><td>15×8×6</td><td>204</td><td>0</td><td>2.45</td><td>0</td><td>49.18</td><td>0</td><td>41.00</td><td>0</td><td>4.49</td></tr><tr><td>MK4</td><td>15×8×6</td><td>67</td><td>0</td><td>4.10</td><td>0</td><td>31.76</td><td>-11.94</td><td>26.28</td><td>5.94</td><td>15.52</td></tr><tr><td>MK5</td><td>15×4×3</td><td>235</td><td>0</td><td>8.89</td><td>22.12</td><td>38.70</td><td>43.40</td><td>33.37</td><td>1.27</td><td>2.04</td></tr><tr><td>MK6</td><td>10×15×8</td><td>73</td><td>0</td><td>2.73</td><td>17.80</td><td>70.44</td><td>21.91</td><td>61.27</td><td>1.36</td><td>3.56</td></tr><tr><td>MK7</td><td>20×5×4</td><td>181</td><td>0</td><td>2.70</td><td>1.65</td><td>10.19</td><td>1.65</td><td>2.73</td><td>2.79</td><td>5.68</td></tr><tr><td>MK8</td><td>20×10×6</td><td>557</td><td>0</td><td>2.52</td><td>-1.95</td><td>20.79</td><td>-4.62</td><td>16.70</td><td>1.54</td><td>4.77</td></tr><tr><td>MK9</td><td>20×10×6</td><td>430</td><td>0</td><td>1.03</td><td>-6.43</td><td>26.98</td><td>0.45</td><td>19.91</td><td>3.41</td><td>9.84</td></tr><tr><td>MK10</td><td>20×15×8</td><td>290</td><td>0</td><td>0.89</td><td>8.62</td><td>56.55</td><td>13.10</td><td>48.91</td><td>3.80</td><td>8.47</td></tr></table></body></html>

# 4 结束语

本文在布谷鸟算法核心框架不变的基础下对其进行改进通过将布谷鸟种群划分为3个子群，并分别采用不同Lévy飞行方式进行寻优，同时引入差分算子进行子群间的信息交流，大大增加了算法的搜索能力。在解码时设计了一种改进解码方式，在避免机器和工人的加工时间冲突的同时，主动寻找可进行插入的空闲时间，大大的缩短了整个加工的完工时间。最后通过基准测试算例进行实验验证和比较，证明了改进布谷鸟算法和改进解码方式的有效性和稳定性。在后续研究中，考虑将生产过程中常见的动态因素考虑进去，比如机器故障、机器维护、紧急插单以及紧急撤单等。

# 参考文献：

[1]陈可嘉，段瑞明，刘碧玉，等.模糊置换流水车间调度的多目标模型 [J].运筹与管理,2021,30(08):28-36.(Chen Kejia,Duan Ruiming,Liu Biyu,et al.A multi-objective model for fuzzy replacement flow shop scheduling [J]. Operations Research and Management,2021,30 (08): 28- 36.)   
[2]Lin J.Backtracking search based hyper-heuristic for the flexible job-shop scheduling problem with fuzzy processing time [J]. Engineering Applications of Artificial Intelligence,2019,77:186-196.   
[3]轩华，王晶，李冰，等．阻塞混合流水车间调度优化研究[J].控制 工程,2020,27 (08):1346-1350.(Xuan Hua,Wang Jing,Li Bing,et al. Research on Optimal Scheduling of Blocked Mixed Flow Shop [J]. Control Engineering,2020,27 (08):1346-1350.)   
[4]Shao Z,Shao W,Pi D.Effective constructive heuristic and iterated

greedy algorithm for distributed mixed blocking permutation flow-shop scheduling problem [J].Knowledge-Based Systems,2021,221 (5): 106959.

[5] 轩华，王晶，张慧贤，等．混合遗传算法求解含机器可利用约束的 HFSP[J].计算机应用与软件,2021,38(06):176-181.(Xuan Hua, Wang Jing,Zhang Huixian,et al.Hybrid Genetic Algorithm for HFSP with Machine Availability Constraints [J]. Computer Applications and Software,2021,38 (06): 176-181.)   
[6] 张洪亮，丁仁曼，徐公杰．考虑区间工时的多目标柔性作业车间节 能调度[J/OL]．系统仿真学报：1-13(2021-08-17)[2021-09-10]. https://doi.org/10．16182/j.issn1004731x.joss．21-0395.(Zhang Hongliang,Ding Renman,Xu Gongjie.Multi-objective Flexible Job Shop Energy Saving Scheduling Considering Interval Working Hours [J/OL]. Journal of System Simulation: 1-13 (2021-08-17)[2021-09-10]. https://doi.org/10.16182/j. issn1004731x. joss.21-0395.)   
[7] Wang H, Sheng B,Lu Q,et al. A novel multi-objective optimization algorithm for the integrated scheduling offlexible job shops considering preventive maintenance activities and transportation processes [J]. Soft Computing,2021,25 (4): 1-27.   
[8]Li J,Yuan H.A Hybrid Genetic Algorithm for Dual-Resource Constrained Job Shop Scheduling Problem [J].Computers & Industrial Engineering,2016,102:113-131.   
[9]Jing Z,Wang W,Xu X.A hybrid discrete particle swarm optimization for dual-resource constrained job shop scheduling with resource flexibility [J]. Journal of Inteligent Manufacturing,2017,28 (8): 1961-1972.   
[10] Lei D,Guo X. Variable neighbourhood search for dual-resource constrained flexible job shop scheduling [J]. International Journal of Production Research,2014,52 (9):2519-2529.   
[11] Zheng X L，Wang L.A knowledge-guided fruit fly optimization algorithm for dual resource constrained flexible job-shop scheduling problem [J]. International Journal of Production Research,2016,54 (18): 5554-5566.   
[12] Yang X S,DEB S. Cuckoo search via Lévy flight [C]// Proceedings of World Congress on Nature & Biologically Inspired Computing.India Washington: IEEE Publications,2009:210-214.   
[13] Ouaarab A,Ahiod B,Yang X S.Discrete Cuckoo Search Applied to Job Shop Scheduling Problem [M]. Recent Advances in Swarm Intelligence and Evolutionary Computation. Springer International Publishing,2015: 121-137.   
[14] Alaa S,Alobaidi A.Two Improved Cuckoo Search Algorithms for Solving The Flexible Job-Shop Scheduling Problem [J]. International Journal on Perceptive and Cognitive Computing,2016,2 (2): 25-31.   
[15] Majumdera A,Lahaa D,Suganthan P N.A hybrid cuckoo search algorithm in parallel batch processing machines with unequal job ready times [J].Computers & Industrial Engineering,2018,124: 65-76.   
[16]唐红涛，刘家毅．改进的布谷鸟算法求解考虑运输时间的分布式柔 性流水车间调度问题[J].运筹与管理,2021,30(11):76-83.(Tang Hongtao,Liu Jiayi. Improved Cuckoo Algorithm for Distributed Flexible Flow Shop Scheduling Problem Considering Transportation Time [J]. Operations Research and Management,2021,30 (11):76-83.)   
[17]罗函明，罗天洪，吴晓东，等．求解混合流水车间调度问题的离散布 谷鸟算法[J].计算机工程与应用，2020,56(22):264-271.(Luo Hanming，Luo Tianhong，Wu Xiaodong，et al.Discrete Cuckoo Algorithm for Solving Hybrid Flow Shop Scheduling Problem [J]. Computer Engineering and Applications,2020,56 (22): 264-271.)   
[18]施文章，韩伟，戴睿闻．模拟退火下布谷鸟算法求解车间作业调度 问题[J]．计算机工程与应用，2017,53(17):249-253,259.(Shi Wenzhang,Han Wei, Dai Ruiwen. Cuckoo algorithm under simulated annealing to solve job shop scheduling problems [J].Computer Engineering and Applications,2017,53 (17): 249-253,259.)   
[19]Brandimarte P.Routing and scheduling in a flexible job shop by tabu search [J].Annalsof Operations research,1993,41 (3):157-183.   
[20]王文艳，徐震浩，顾幸生．离散水波优化算法求解带批处理的混合 流水车间批量流调度问题[J].华东理工大学学报：自然科学版， 2021,47(05):598-608.(Wang Wenyan,Xu Zhenhao,Gu Xingsheng. Discrete water wave optimization algorithm for batch flow scheduling

problem in mixed flow workshop with batch processing[J]. Journal of East China University of Science and Technology:Natural Science,2021, 47 (05): 598-608.) [21] Gnanavelbabu A,Caldeira R H,Vaidyanathan T.A simulation-based modified backtracking search algorithm for multi-objective stochastic flexible job shop scheduling problem with worker flexibility[J].Applied Soft Computing,2021,2021(113): 107960.