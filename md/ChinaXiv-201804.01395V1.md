# 异构多核计算系统的Codelet任务调度策略

裴颂文¹²，吕春龙1，宁钟²，顾春华1(1．上海理工大学 光电信息与计算机工程学院，上海 200093;2．复旦大学 管理学院，上海 200433)

摘要：Codelet数据流计算模型在处理大规模并行计算任务时效果显著，但该模型目前缺少在异构多核环境中的任务调度策略。因此，提出了一种在异构多核环境下基于蚁群算法的Codelet 任务调度策略。该调度策略将启发式算法与蚁群算法相融合，在发挥各自优势的同时克服了启发式算法不能得出最优解的缺陷以及蚁群算法初始信息匮乏的问题。实验结果表明，智能蚁群任务调度策略相比Codelet运行时系统中原生的动态调度和静态调度策略具有更高的执行效率。

关键词：数据流计算；Codelet模型；异构多核；蚁群算法；任务调度 中图分类号：TP183 doi: 10.3969/j.issn.1001-3695.2017.12.0840

# Codelet task sched uling policy of heterogeneous multicore computing system

Pei Songwen1,²,Lyu Chunlongl, Ning Zhong², Gu Chunhual (1.SchoolofOptical-Electrical&ComputerEngineering,UniversityofShanghaiforScience&Technology,hanghai0093, China; 2.School of Management,Fudan University,Shanghai 200433,China)

Abstract: Codelet dataflowmodel hassignificant effectsongaininghigh performanceofcomputing large-scale paralel tasks, butthe modelcurrentlylacks shedulingpolicyinheterogeneous multi-core environment.Regarding tothis issue,this paper proposedaCodelettaskschedulingstrategybyfusing antcolonyalgorithm withaheuristicaproach inheterogeneous multicore environment.Ithadbothadvantagesofthe heuristicalgorithmandantcolonyalgorithm,anditovercomedboth defectsofthe heuristic algorithmthatcould notderive an optimal solutionandthe defects oftheantcolonyalgorithmthat was lack of the initial information.Theexperimentalresultshows,thesmartantcolonyschedulingpolicyis much more effcient thanthenative dynamic and static scheduling policies in the runtime system implementation of the Codelet model.

Key words: dataflowcomputation; Codelet model; heterogeneous multi-core; ant colony algorithm; task schedule

# 0 引言

数据流计算模型是由麻省理工学院的Dennis[1提出，被认为是冯诺依曼控制流计算机在并行化计算方向上的突破性贡献。数据流计算模型执行指令的方式与传统的冯氏计算机基于指令控制流的方法不同，它采用有向图描述数据流模型，指令所需的数据一旦就绪即可触发该执行，具有高度的并行性。数据流计算模型充分发掘了程序内在的数据并行性，使用细粒度的并行机制克服传统控制流模型的局限性。为了提高多核系统的执行效率并解决数据流模型细粒度所引起的问题，混合数据流计算模型应运而生。混合数据流模型[2.3]结合了数据流和冯诺依曼控制流各自的优势，最大化利用硬件资源的同时，还能降低系统功耗。Codelet模型[4.5]就是一种重要的混合数据流计算模型。

多核处理器已经成为主流计算机的重要计算部件，改变了以往处理器仅支持少量计算单元的应用环境。随着并行执行模型的不断完善,Suettlerlein[提出了Codelet 模型，并基于此模型，提出了对应的运行时系统DARTS。Codelet模型是一种细粒度的、由事件驱动的、混合控制流/数据流的并行执行模型[7]。Codelet模型由基本执行单位Codelet和线程程序TP（threadedprocedure）组成。其中，Codelet主要负责存储执行指令，TP作为Codelet的容器，负责输入、输出及保存共享数据。DARTS作为Codelet模型的运行时系统，负责多核、众核上的任务调度、负载平衡、内存管理和功耗管理等。本文使用DARTS 实现和模拟任务在Codelet模型中的执行过程。

多核处理器又分为同构多核和异构多核两种类型。Kumar等人[8指出，同构多核存在一定的局限性，如果在芯片上集成多个简单的内核，将会造成能耗和芯片冷却的负担。而异构多核处理器除了配置通用的处理器核外，还集成了一些特定功能的处理器核心，能够加快程序的执行速度并降低系统功耗[9]。异构多核处理器系统的发展受到广泛的关注并将成为未来处理器的发展方向，然而Codelet 数据流计算模型缺乏在异构计算环境下的任务调度方案。

执行模型的选择是并行系统设计中最根本的问题，而调度策略 $. [ 1 0 ^ { \sim } 1 2 ]$ 又决定了任务在执行模型的执行效率[5]。为了减少并行任务的执行时间，本文提出了一种面向异构Codelet的智能蚁群任务调度策略。通过改进蚁群算法，使其适用于异构Codelet模型，将各Codelet分配至指定的执行单元，从而完成任务在模型中的调度，最后使用标准任务图集中的有向无环图模拟仿真实验过程并与DARTS中自带的两种调度策略进行对比，以验证新调度策略的有效性。

# 1 Codelet模型与蚁群算法

CodeletCodelet是Codelet数据流计算模型的基本执行单元，由一系列机器指令组成，这些机器指令可看做是单一的、非抢占式的计算单元。在Codelet程序执行模型中，Codelet 是最基本的调度单位，任务被划分成许多相连通的Codelet。与传统任务的并行机制不同，Codelet的执行语义是当且仅当所有需要的资源可用时，Codelet才会被激活。然后，Codelet将根据调度策略分配给对应的目标处理单元，并且多个激活的Codelet可以并行执行。

# 1.1 DARTS

DARTS(delawareruntime system)[是实现Codelet数据流计算模型的运行时系统，其主要作用是根据调度策略分配硬件资源来加载和执行Codelet。DARTS运行时由四种对象类型组成：线程程序调度器(TPS)、Codelet调度器(CDS)、抽象机配置和出口Codelet。其中，TPS主要负责线程程序和Codelet的负载均衡，并在空闲时执行已激活的Codelet；CDS的任务主要是执行对应执行单元上已激活的Codelet；抽象机配置是运行时与用户交互的接口，可由用户设置Codelet模型的硬件环境；出□Codelet 是任务在Codelet 模型所执行的最后一个Codelet,该Codelet亦即任务执行完毕的信号。本文仅考虑单一集群下的 Codelet 调度策略，在DARTS中，一个集群下有一个TPS 和多个CDS，调度器的数量一般等于或小于实际处理器所拥有的处理单元。

# 1.2调度模型

在Codelet数据流计算模型中，任务调度的目标是寻找可在机器上运行的最优或近似最优的调度方案。Codelet在依赖关系的约束下，尽可能地缩短任务执行时间。假定m是某个计算任务中Codelet节点的数量，n是某个集群/多核处理器中计算单元（对应调度器）的数量，调度任务即是将m个Codelet分配给n个调度器。每个Codelet的计算都会独占调度器直到该Codelet的计算任务执行完毕。

本文采用CDG（Codeletgraph）模拟真实机器执行数据流计算任务时的Codelet调度场景。如图1所示，CDG由Codelet、token和event三部分组成。Codelet是基本的执行单位，token表示Codelet执行完毕后发出的信号，event表示两个Codelet间的依赖关系。CDG 可以明确地表示出Codelet 的状态与Codelet之间的依赖关系。

![](images/87b3d9d6694771247a72982f8bf9044774abf5b4c0788d2db2ed45e38b718c72.jpg)  
图1 CDG（Codelet graph）

CDG采用有向无环图 $\mathrm { G = < V , }$ $\mathrm { E > }$ 描述Codelet数据流计算模型。Codelet 的节点构成顶点集合 $\scriptstyle \mathrm { V = } \{ n _ { i } \}$ ， $i \in [ 0 , \mathrm { N } \mathrm { - } 1 ] , \mathrm { N }$ 是Codelet任务数；边集 $\scriptstyle { \mathrm { E } = \{ e _ { i , j } \} }$ ， $i , j \in [ 0 , \mathrm { N - 1 } ]$ ， $\boldsymbol { e } _ { i , j }$ 表示Codelet任务 $n _ { i }$ 与 $n _ { j }$ 之间的数据依赖关系。如表1所示，本文定义了Codelet模型中的数据结构和调度相关的参数。

表1符号和参数定义  

<html><body><table><tr><td>符号</td><td>定义</td></tr><tr><td>prec(i)</td><td>n的直接前驱集合</td></tr><tr><td>succ(i)</td><td>n的直接后继集合</td></tr><tr><td>C(i,j)</td><td>n和nj之间数据传输时间</td></tr><tr><td rowspan="2">allow(t)</td><td>解的构造过程中，调度步骤t的就绪任务集合，包括所有</td></tr><tr><td>前驱均已接受调度的Codelet任务</td></tr><tr><td>FT(i)</td><td>Codelet任务n的结束时刻</td></tr><tr><td>ETC(i, j)</td><td>任务ni在调度器pj上的执行时间</td></tr><tr><td rowspan="2">MK(s)</td><td>s 的调度长度;MK(s)=maX(FT(i));异构CDG 调度的 i∈[0,N−1]</td></tr><tr><td>优化目标为：min(MK(s))</td></tr><tr><td>S</td><td>Codelet节点的调度序列（调度方案）</td></tr></table></body></html>

# 1.3蚁群算法

蚁群算法（ant colony optimization Algorithm，ACO）[13,14]最早由意大利学者MarcoDorigo 等人在20 世纪90 年代提出，是一种从群体智能演化而来的解决大规模组合优化问题的算法。蚂蚁通过信息素传递信息，如果某个路径较短，则单位时间内通过的蚂蚁数量相对多，在该路径上残留的信息素就越多，后续蚂蚁将有倾向地选择该路径通行。蚁群算法正是利用了这一原理，通过这种积极的反馈，使其具有强大的全局趋同性。蚁群算法以信息素为载体，具有发现较优解的能力，可进行大范围的全局搜索，同时具备一定的鲁棒性和潜在的并行性。蚁群算法已经在组合优化、函数优化、网络路由、机器人路径规划、数据挖掘等领域获得了广泛的应用，并取得了较好的效果。本文对蚁群算法进行改进，使其适用于异构环境下的Codelet 模型的任务调度。

# 2 智能蚁群任务调度策略

本文面向异构多核的Codelet计算环境，融合启发式算法HEFT(heterogeneous earliest-finish-time)[15]和蚁群算法提出了一种智能蚁群任务调度策略 SACTS（smart ant colony taskscheduling)。HEFT算法会在每个步骤中选择相距出口节点最远的Codelet计算节点，并将选择的Codelet分配给异构计算单元执行。智能蚁群任务调度策略会根据HEFT算法计算出每个Codelet计算任务的静态优先级，优先级越高，相应的Codelet就需要越早被调度执行。智能蚁群任务调度策略将各个Codelet的静态优先级引入到蚁群算法中作为调度Codelet 计算任务的重要依据。

图2展示了本文提出的智能蚁群任务调度策略的流程。智能蚁群任务调度策略的具体执行步骤如下： $\textcircled{1}$ 首先导入CDG图、数据传输的时间开销C以及任务执行开销ETC； $\textcircled{2}$ 根据HEFT算法计算出每个Codelet 节点的静态优先级 $r a n k$ ； $\textcircled{3}$ 蚂蚁从Codelet $n _ { s t a r t }$ 开始节点出发，根据动态状态转移规则选择下一个调度的Codelet节点； $\textcircled{4}$ 将选择的Codelet节点分配给能最早执行完成的调度器（计算单元）； $\textcircled{5}$ 判断该蚂蚁是否遍历完所有的Codelet节点，如果是，则进行局部信息素更新，否则继续选择下一个Codelet 节点； $\textcircled{6}$ 判断所有蚂蚁是否都完成一次遍历，如果都完成遍历，则进行全局信息素更新，否则继续分配蚂蚁进行下一轮遍历； $\textcircled{7}$ 记录本次迭代计算的最优解并更新动态因子； $\textcircled{8}$ 判断是否达到最大迭代次数，如果是则输出最优解，否则继续下一轮迭代。

![](images/2d406d7202d2428dbd22a279a5b8fd5c3fc1f1474a91d0dd58ca4f110ab48f9c.jpg)  
图2智能蚁群任务调度策略流程

# 2.1参数定义

如表2所示，本文定义了智能蚁群任务调度策略所使用的参数和初始化值。

表2参数和初始化值  

<html><body><table><tr><td>参数</td><td>参数的含义 初始化值</td></tr><tr><td>m</td><td>蚂蚁数量 50</td></tr><tr><td>n</td><td>迭代次数 200</td></tr><tr><td>T0</td><td>信息素矩阵初始值 0.001</td></tr><tr><td>β</td><td>启发式信息在蚂蚁选择路径中所起作用大小 1.2</td></tr><tr><td>qo</td><td>动态因子，调节已知信息利用和新信息探索之间的比例 0.1</td></tr><tr><td>p</td><td>局部信息素挥发因子 0.1</td></tr><tr><td>P</td><td>全局信息素挥发因子 0.1</td></tr></table></body></html>

# 2.2构造调度序列的解

智能蚁群任务调度策略将蚁群算法的某个解 $s$ 表示为 $s$ $\mathbf { \Omega } = \{ \mathbf { \Omega } n _ { 0 } \ , \ n _ { 1 } \  \cdots , \ n _ { i } \ , \cdots , \ n _ { N - 1 } \ \}$ 。按照蚂蚁走过的路径，依次将Codelet任务节点添加到 $s$ 队列中， $s$ 队列满，则表示蚂蚁完成了一次遍历，蚂蚁移动的路径即Codelet的某个调度序列。智能蚁群任务调度策略执行过程中依赖 $s$ 队列和 $a l l o w$ 集合。 $s$ 队列依次记录了所有已经被调度的Codelet任务节点；初始化时所有的节点均未被调度， $s$ 队列为空。allow(t)表示在选择第 $\mathbf { \Phi } _ { t }$ （20个Codelet任务节点时，可供选择的Codelet任务节点集合；初始化时，allow(0)仅有开始节点 Codelet $n _ { s t a r t }$ 。 如算法1所示，构造了智能蚁群任务调度策略的解。该算法循环N次，每次会选择一个Codelet任务节点记录在 $s$ 队列中，然后将该Codelet任务节点分配给最早执行完成的调度器并且记录其执行完成的时间。当 $s$ 队列满时，输出所有Codelet任务节点中最大的结束时间，即解 $s$ 的调度长度(调度开销)，解 $s$ 即Codelet节点的调度序列。

算法1解的构造输入：CDG图G输出：MK(s)

1. for each ant k  
2. build a queue $s$ of ant path;  
3. build a queue allow of Codelets to be chosen;  
4. t=0;  
5. add Codelet $n _ { s t a r t }$ to allow(t);  
6. while $\mathbf { \Delta t } < \mathbf { N }$ do  
//通过动态转移规则从 $a l l o w ( t )$ 中选择下一个调度的Codelet  
7. choose Codelet $n _ { i }$ from $a l l o w ( t )$ by dynamic rule;  
//选择能最早执行完成Codelet 的调度器（计算单元）  
8. choose a scheduler to execute Codelet $n _ { i }$ ·  
9. record FT of Codelet n; ;  
10. add the Codelet $n _ { i }$ to $s$   
11. $\scriptstyle { \mathrm { t } } = { \mathrm { t } } + 1$ ：，  
12. update allow(t);

13. end while

14. $M K ( s ) = \operatorname* { m a x } _ { i \in [ 0 , N - 1 ] } \left( F T ( i ) \right) ;$ （204

15.end for

# 2.3启发式信息定义

在智能蚁群任务调度策略中， $\eta$ 为蚂蚁的调度操作提供启发式知识，能促使蚁群更快发现较优解或最优解，减少求解的盲目性。智能蚁群任务调度策略将HEFT算法中使用的启发式知识带入 $\eta$ 。在HEFT算法中，距离出口节点最远的任务最重要，应该先接受调度，因此 $\eta$ 可以定义为Codelet节点的静态优先级 $r a n k ( n _ { i } )$ ,根据式(1)计算。

$$
r a n k ( n _ { i } ) = w _ { i } + \operatorname* { m a x } _ { n _ { j } \in s u c c ( n _ { i } ) } ( c _ { i , j } + r a n k ( n _ { j } ) )
$$

其中： $s u c c ( n _ { i } )$ 是Codelet $n _ { i }$ 的直接后继集合； $c _ { i , j }$ 是边 $( i , j )$ 的通信开销； $w _ { i }$ 是Codelet $n _ { i }$ 在调度器上的平均计算开销。静态优先级 $r a n k$ 值是通过向上遍历Codelet任务图递归求得。对于Codelet $n _ { e x i t }$ ，其 $r a n k$ 值根据式(2)求得。

$$
r a n k ( n _ { e x i t } ) = W _ { e x i t }
$$

智能蚁群任务调度策略在初始化时计算出每个Codelet的rank，之后该值作为所有蚂蚁共有的信息， $r a n k$ 值越高，蚂蚁选择该Codelet的概率越高。

# 2.4动态状态转移规则

蚂蚁通过状态转移规则决定下一个调度的Codelet任务。智能蚁群任务调度策略使用动态伪随机概率规则进行状态转移，见式(3)。

$$
n _ { i } = \arg \operatorname* { m a x } _ { w \in a l l o w ( i ) } \{ [ \tau ( i , w ) ] [ \eta ( i , k ) ] ^ { \beta } \} , \quad \mathrm { i f } q < q _ { 0 }
$$

$\tau ( i , w )$ 为 $( i , w )$ 边上的信息素强度， $\tau ( i , w )$ 值越大，蚂蚁选择Codelet $n _ { k }$ 的概率就越大。 $\eta ( i , w )$ 即为 $\eta ( n _ { \mathrm { w } } )$ 根据式(1)(2)计算可得。

在本文提出的动态伪随机概率规则中，通过调整动态因子$q _ { 0 }$ 来控制收敛速度。 $q _ { 0 }$ 值越小，按照式(4)随机性选择的概率就越大，蚁群选择的多样性会越好；反之， $q _ { 0 }$ 值越大，蚂蚁选择allow(i)集合中 $[ \tau ( i , j ) ] [ \eta ( i , j ) ] ^ { \beta }$ 值最高的 Codelet $n _ { i }$ 的概率就越大，收敛速度会加快。因此在智能蚁群任务调度策略初期设定较小的 $q _ { 0 }$ 值增加蚁群选择的多样性，而在后期随着迭代次数的增长将 $q _ { 0 }$ 值调整为较大的值可以加快收敛速度。根据式(4) $q _ { 0 }$ 值计算可得。

$$
q _ { 0 } { = } q _ { \mathrm { m i n } } + \frac { ( q _ { \mathrm { m a x } } - q _ { \mathrm { m i n } } ) ^ { * } l } { n }
$$

其中： $\mathbf { \xi } _ { l }$ 表示当前迭代次数； $n$ 表示最大迭代次数。

根据式(3)，蚂蚁在每次的状态转移时都会生成一个[0,1]之间的随机数 $q$ 。若 $q < q _ { 0 }$ ，蚂蚁选择allow(i)集合中[τ(i,j)][n(i,j)]β值最高的Codeletn；反之，蚂蚁根据式(5)计算allow(i)中每个Codelet任务被选择的概率，进行随机概率选择。qo表示已知信息利用和新信息探索之间的比例。

$$
p _ { i } ( j ) = \left\{ \begin{array} { l l } { \displaystyle { \frac { [ \tau ( i , j ) ] [ \eta ( i , j ) ] ^ { \beta } } { \sum _ { w \in a l l o w ( i ) } [ \tau ( i , w ) ] [ \eta ( i , w ) ] ^ { \beta } } } , i f w \in a l l o w ( i ) } \\ { 0 , \qquad o t h e r w i s e } \end{array} \right.
$$

# 2.5信息素更新

在构造解的过程中，每一只蚂蚁通过局部更新规则对自己选择的边进行局部信息素更新。在一次迭代中，当所有的蚂蚁都完成了解的构造后，再对最佳路径上的边进行全局信息素更新。

# 2.5.1局部信息素更新规则

局部信息素更新的目的是防止本轮迭代中的后续蚂蚁得到相同的解，因此在构造解过程中，蚂蚁挥发当前调度对应的信息素 $\tau ( t , n )$ ，更新公式为

$$
\tau ( t , n ) = \tau ( t , n ) ^ { * } ( 1 - \rho ) + \tau _ { 0 } ^ { ~ * } \rho
$$

# 2.5.2全局信息素更新规则

在一次迭代中所有蚂蚁完成解的构造后，对信息素矩阵进行全局更新，增加蚁群找到的最优调度步骤上的信息素，更新公式为

$$
\tau ( t , n ) = \tau ( t , n ) ^ { * } ( 1 - \varphi ) + \Delta \tau ( t , n ) ^ { * } \varphi
$$

$$
\Delta \tau ( t , n ) = \frac { 1 + \operatorname* { m a x } ( 0 , M K ( o l d ) - M K ( n e w ) ) } { \operatorname* { m i n } ( M K ( o l d ) , M K ( n e w ) ) } , ( t , n ) \in g b \mathfrak { b e t t e n }
$$

式(8)中 $M K ( o l d )$ 是本次迭代开始前算法得到的最优解，$M K ( n e w )$ 是本次迭代找到的最优解，gbbetter是其中的更优者。

# 3 实验与分析

# 3.1实验环境

实验环境配置为 Intel Core i7-6700HQCPU，NvidiaGTX1080TiGPU,16GBDDR4主存，每个核包含 $1 2 8 \mathrm { K B }$ 的一级数据缓存和指令缓存，1MB 的二级缓存和6MB 的三级缓存，CentOS-7-x86_64操作系统。使用的运行时系统是基于Codelet模型设计的DARTS。为了评价智能蚁群任务调度策略的性能，实验采用标准任务图集 STG（standard task graph）。STG[16]是一种评估多处理器调度算法的基准程序。本文在STG图结构不变的基础上，随机生成各节点在不同调度器上的执行时间以及Codelet节点在调度器之间的数据通信时间。

# 3.2实验数据及结果分析

实验使用了包含300、500、750、1000、1250、1500个节点的随机 STG以及基于实际应用生成的STG：RobotControl(88 个节点)、Sparse Matrix Solver(96 个节点)、SPECfpppp(334个节点)。在异构多核调度器环境中，比较了DARTS中两种适用于Codelet 模型的调度策略（（静态策略(staticpolicy)、动态策略(dynamic policy）6）和智能蚁群任务调度策略的任务执行时间。其中，静态策略采用轮询法将已激活的Codelet分配给指定的调度器。动态策略将所有可执行的Codelet存放在一个队列中，每当有调度器空闲时，都可单独访问该队列并获取Codelet，因此动态策略适用于非对称的应用程序。

表3所示是三种调度策略执行包含不同节点的随机STG所需的时间。SACTSPolicy 的执行时间相比于Static Policy[减少了 $3 4 . 7 \% { \sim } 4 7 . 6 \%$ ，SACTSPolicy的执行时间相比于DynamicPolicy减少了 $5 . 7 \% { \sim } 2 3 . 5 \%$ 。

表3随机STG的执行时间  

<html><body><table><tr><td>Codelet数量</td><td>Static Policy[6]</td><td>Dynamic Policy[6]</td><td>SACTS Policy</td></tr><tr><td>300</td><td>148.8</td><td>103.0</td><td>97.2</td></tr><tr><td>500</td><td>251.5</td><td>174.2</td><td>152.3</td></tr><tr><td>750</td><td>377. 4</td><td>264.1</td><td>225.7</td></tr><tr><td>1000</td><td>668.2</td><td>468.1</td><td>382.6</td></tr><tr><td>1250</td><td>853.0</td><td>584.6</td><td>447.2</td></tr><tr><td>1500</td><td>1200.1</td><td>781.5</td><td>635.8</td></tr></table></body></html>

图3所示是智能蚁群任务调度策略SACTS相比于静态策略和动态策略的执行时间加速比。加速比的计算公式为：某个调度策略执行任务时间/SACTS执行任务时间。由图可知，SACTS相比StaticPolicy和DynamicPolicy 的执行时间加速比均大于1，这说明 SACTS 要优于DARTS 运行时系统原生的Static Policy和Dynamic Policy。其中SACTS相比Static Policy的执行时间加速比在1.53\~1.90，相对于Dynamic Policy 的执行时间加速比在 $1 . 0 6 { \sim } 1 . 3 1$ 。随着Codelet任务节点数量的增加，智能蚁群任务调度策略相对于静态策略和动态策略的执行时间加速比总体呈现递增状态，这说明随着Codelet任务节点规模的扩大时，智能蚁群任务调度策略的执行效率也在不断提高。

2□SACTS-Static ■SACTS-Dynamic1.5具 1 1 10.50300 500 750 1000 1250 1500Codelet节点数量

图4所示是三种调度策略执行基于实际应用生成的STG的执行时间。对于robot，使用 SACTS 的执行时间比 Static Policy减少了 $2 4 . 7 \mathrm { ~ s ~ }$ ，比Dynamic Policy 减少了 $7 . 1 \mathrm { ~ s ~ }$ ；对于sparse,使用 SACTS 的执行时间比 Static Policy 减少了 $2 7 . 3 \mathrm { ~ s ~ }$ ，比DynamicPolicy 减少了 $8 . 4 ~ \mathrm { s }$ ；对于fppPp，使用 SACTS 的执行时间比 Static Policy 减少了 $6 7 . 7 \mathrm { ~ s ~ }$ ，比Dynamic Policy 减少了$2 0 . 5 \mathrm { s }$ 。实验结果表明，智能蚁群任务调度策略在处理实际应用时，也具有相当好的执行效率。

如表4所示,HEFT以及SACTS在异构多核的Codelet计算环境下，对不同STG进行调度的执行时间。其中，SACTS(第一轮迭代)是指蚁群在迭代1次后得到最优调度序列，SACTS是指蚁群在迭代200次后得到的最优调度序列。Codelet任务在调度器的执行时间为[0,100]区间的随机变量，调度器之间的数据传输时间为[0,10]区间的随机变量。对于Codelet数量为88(robot)、96(sparse)、334(fpppp)、300、500、750、1000、1250、1500 的 STG，SACTS(第一轮迭代)比HEFT 的执行时间减少了$1 0 \% { \sim } 2 3 . 8 \%$ ,SACTS比HEFT的执行时间减少了 $1 1 . 2 \% { \sim } 2 6 . 3 \%$ 。SACTS执行时间比HEFT少的主要原因是蚁群在每一次迭代过程中都会增加最优路径上的信息素，通过这种积极的正反馈可以得到较优解或最优解。SACTS(第一轮迭代)即蚁群在迭代1次后得到最优调度序列的执行时间少于HEFT主要原因是HEFT算法中的启发式知识可以促使蚁群更快发现较优解或最优解，减少了求解的盲目性。实验结果表明智能蚁群任务调度策略的性能优于HEFT，并且改善了蚁群算法初始信息匮乏的缺点。

![](images/b3703a57ea33be129dab0c88f671511e167d70b79b1b1fa0c3866cb8a0b78a1f.jpg)  
图3执行时间加速比  
图4STG 的执行时间

表4STG 的执行时间  

<html><body><table><tr><td>Codelet数量</td><td>HEFT</td><td>SACTS(第一轮迭代)</td><td>SACTS Policy</td></tr><tr><td>88(robot)</td><td>1993</td><td>1683</td><td>1557</td></tr><tr><td>96(sparse)</td><td>1870</td><td>1651</td><td>1584</td></tr><tr><td>334(fpppp)</td><td>6499</td><td>5263</td><td>5238</td></tr><tr><td>300</td><td>7117</td><td>5342</td><td>5239</td></tr><tr><td>500</td><td>11588</td><td>8834</td><td>8704</td></tr><tr><td>750</td><td>17208</td><td>14196</td><td>14018</td></tr><tr><td>1000</td><td>22454</td><td>19273</td><td>19027</td></tr><tr><td>1250</td><td>24585</td><td>22133</td><td>21826</td></tr><tr><td>1500</td><td>31915</td><td>27573</td><td>27240</td></tr></table></body></html>

# 4 结束语

随着Codelet数据流模型以及异构多核系统的发展，Codelet任务调度策略成为制约异构Codelet数据流模型执行效率的重要因素之一。本文在异构多核环境下，研究了Codelet数据流模型的调度策略，并提出了智能蚁群任务调度策略。智能蚁群任务调度策略将启发式算法 HEFT[I2]和改进的蚁群算法相融合，提高了模型的执行效率，缩短了任务执行时间。通过实验证明，在解决大规模Codelet任务调度问题时，智能蚁群任务调度策略与Codelet运行时系统中的原生动态调度和静态调度策略相比具有更高的效率。随着性能和速度的提高，处理器的能耗和散热问题在设计高性能系统时成为关键的挑战。在Codelet数据流模型中，如何有效的降低能耗以及均衡处理器核心上的能耗，防止处理器上出现局部过热，是未来工作的研究重点。

# 参考文献：

[1]Dennis JB.First version of a data flow procedure language [C]//Proc of Symposium Programming.Berlin: Springer 1974: 362-376.   
[2]Yazdanpanah F,Alvarez-Martinez C,Jimenez-Gonzalez D,et al.Hybrid dataflow//von-neumann architectures [J].IEEE Trans on Parallel and Distributed Systems,2014,25 (6):1489-1509.   
[3]Grafe VG,Hoch JE,Davidson G S.Eps'88:combining the best features of Von neumann and dataflow computing [R].Albuquerque: Sandia National Labs,1989.   
[4]Zuckerman S,Suetterlein J,Knauerhase R,et al.Using a codelet program execution model for exascale machines: position paper [C]//Proc of the 1st International Workshop on Adaptive Self-Tuning Computing Systems for the Exaflop Era.2011: 64-69.   
[5]Suettlerlein J, Zuckerman S,Gao G R.An implementation of the Codelet model[M]// WolfF,Mohr B,Mey D.Euro-Par 2013 Parallel Processing Workshops.Berlin: Springer.2013: 633-644.   
[6]Suetterlein J. DARTS: a runtime based on the Codelet execution model [D]. State of Delaware:University ofDelaware,2014.   
[7]Pei S,Wang J,Cui W,et al.Codelet scheduling by genetic algorithm [C]/ Proc of IEEE Trustcom//BigDataSE//ISPA.2016:1492-1499.   
[8]Kumar R,Tullsen D M,Jouppi N P,et al. Heterogeneous chip multiprocessors [J]. IEEE Computer, 2005,38 (11): 32-38.   
[9]Augonnet C,Thibault S,Namyst R,et al. StarPU: a unified platform for task scheduling on heterogeneous multicore architectures [J]. Concurrency and Computation: Practice and Experience,2011,23 (2):187-198.   
[10]赵国亮，李云飞，王川．异构多核系统任务调度算法研究[J].计算机 工程与设计,2014,35(9):3099-3106.   
[11]裴颂文，宁静，张俊格.CPU-GPU 异构多核系统的动态任务调度算法 [J].计算机应用研究,2016,33(11):3315-3319.   
[12] Nguyen T D,Vaswani R,Zahorjan J.Parallel application characterization for multiprocessor scheduling policy design [C]//Feitelson DG,Rudolph L Job Scheduling Strategies for Parallel Processing. Berlin: Springer,1996: 175-199.   
[13] Chiang C W,Huang YQ,Wang W Y.Ant colony optimization with parameteradaptation for multi-mode resource-constrained project scheduling [J].Journal of Intelligent and Fuzzy Systems,2008,19 (4): 345- 358.   
[14] Chiang C W,Lee Y C,Lee C N,et al.Ant colony optimisation for task matching and scheduling [J].IEE Proceedings-Computers and Digital Techniques,2006,153 (6): 373-380.   
[15] Li M,Wang H, Li P. Tasks mapping in multi-core based system: hybrid ACO&GA approach [C]//Proc of the 5th International Conference on ASIC. 2003:355-340.   
[16] Tobita T,Kasahara H.A standard task graph set for fair evaluation of multiprocessor scheduling algorithms [J]. Journal of Scheduling,2oo2,5 (5): 379-394.