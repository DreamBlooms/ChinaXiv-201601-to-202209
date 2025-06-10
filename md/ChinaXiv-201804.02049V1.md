# 置信传播和模拟退火相结合求解约束满足问题‘

吴拨荣，赵春艳，原志强(上海理工大学 理学院，上海 200093)

摘要：约束满足问题是人工智能领域的一个重要问题。针对一个具有精确相变现象和能产生大量难解实例的随机约束满足问题，提出了置信传播和模拟退火相结合的求解算法。这种算法先通过置信传播方程收敛后得到变量取值的边际概率分布，分别采用最大概率和最小分量熵的策略产生一组启发式的初始赋值，再用模拟退火对这组赋值进行修正。实验结果表明：该算法大大提高了初始赋值向最优解收敛的速度，表现出了显著优越于模拟退火算法的求解性能。

关键词：RB模型；相变现象；置信传播；模拟退火；算法效率 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2017.11.0790

Combining belief propagation and simulated annealing to solve random satisfaction problems

Wu Borong, Zhao Chunyan†, Yuan Zhiqiang (CollegeofScience,UniversityofShanghai for Science&Technology,Shanghai 2ooo93,China)

Abstract: Constraintsatisfactionproblem isan important isue intefieldofartificial inteligence.This paper proposedtwo algorithms combining belief propagationandsimulated anealing tosolvearandomconstraint satisfaction problem with exact phase transitions and large numberofhard instances.Thealgorithms firstlyobtain the marginalprobabilitydistributionof variable values after theconvergenceof the belief propagation equation,then uses the strategyof maximum probabilityand minimumcomponent entropy to generateasetofheurstic initialasignments,andthenuses simulatedannealing tomodifythe assignments.The experimental resultsshow that thealgorithms greatly improves the convergencerate from the initial assignments toward the optimal solution,and shows a significant advantage over simulated annealing algorithm.

Key words: RB model; phase transition; belief propagation; simulated annealing; algorithm efficiency

# 0 引言

约束满足问题(constraint satisfactionproblem，CSP)是人工智能研究领域中一个非常重要的分支，也是理论计算机科学的研究热点之一。同时，CSP在可信计算、启发式算法、求解器设计、大规模集成电路的自动布线、计算机视觉、定理证明、机器人动作规划和机器学习等诸多领域都有非常广泛的应用。

一个CSP由 $N$ 个变量和 $M$ 个约束组成。每个变量从其定义域 $D$ 中取值，每个约束由从 $N$ 个变量中随机挑选的 $k$ 个不同的变量构成，并且有一个相应的不协调赋值集合 $\boldsymbol { \mathcal { Q } }$ 来限制这 $k$ 个变量的取值为不可满足的。从可能的 $\binom { N } { k }$ 个约束中随机选取$M$ 个构成这个CSP的一个随机实例。求解CSP 就是至少找到随机实例的一个解，也就是这 $N$ 个变量的一组完全赋值，使得这M个约束同时被满足；或者证明随机实例无解。一般情况下，随机CSP是NP-完全问题。常见的随机CSP有可满足性问题（satisfiability，简称SAT）、RB 模型、最小顶点覆盖问题和哈密顿回路问题等。

RB（revisedB）模型是许可和李未为克服标准CSP模型中B 模型的平凡渐近不可满足性而提出的[1]。早期的许多理论分析和算法实验都是围绕四个标准的CSP模型A、B、C、D展开的。然而，Achlioptas 等人指出这四个模型存在一个共同的缺点，即平凡渐近无解性[2]。也就是说，随着 $N \to \infty$ ，这四个模型几乎都存在一个缺陷（flawed)变量，这个变量的任何取值都不能使其所在的约束可满足。为了克服这一缺点，一些改进的模型相继被提出[1-5]。这些改进的模型在约束关系中加入了如弧相容、路径相容等特殊结构，虽然能产生非平凡的难解实例，但是实例不是以简单、自然的方式产生的。2000年，许可和李未提出了对标准B模型的一个修改模型即RB模型，通过对变量定义域规模和约束数目的限制，避免了B模型不能产生难解实例的缺点。许可和李未在文献[1]中用二阶矩的方法严格证明了RB 模型存在精确的可满足性相变现象。随后，许可等分别从理论和实验上说明在可满足性相变发生的阈值附近，RB 模型随机实例的求解难度随着 $N$ 的增加呈指数级增长，即RB 模型在相变区域涌现出大量非平凡的难解实例[6.7]。RB 模型自提出以来，在较短的时间内，就受到了美国、英国、加拿大、法国和希腊等同行的关注，并被一些学者广泛研究和引用。虽然RB 模型的可满足性相变现象和相变点已经严格确立，但是求解一个随机实例却极具挑战。以RB 模型为基础构造的可满足性问题、约束满足问题、最大团、伪布尔和集合覆盖等问题作为难解算例被广泛应用于各种算法竞赛。2011年，赵春艳等引入统计物理中无序系统的空腔场方法，提出了由置信传播（beliefpropagation，BP）引导的消息传递算法来求解RB模型的随机实例[8]。随后，赵春艳等人提出了一种基于变量熵的BP算法[9]。2012年，赵春艳等人提出了加强的BP（reinforced BP)算法求解临近相变点时由RB模型生成的随机实例，并进一步指出了RB 模型解空间的结构特征和算法求解复杂性之间的联系[10]。2015年，任雪亮在BP方程中加入惩罚值，使得BP 算法适用于求解最大约束满足问题的RB 模型[II]。2016年，王晓峰和许道云从理论上分析了文献[9]中提出的基于变量的 BP算法在RB 模型可满足区域内的收敛性[12]。2017年，原志强和赵春艳提出了两种有效的改进的模拟退火算法即RSA（revisedsimulated annealing algorithm） 和 GSA（genetic-simulatedannealingalgorithm）来求解RB模型的随机实例[13]。

文献[13]中提出的RSA算法是对一组随机初始化的赋值利用改进的模拟退火算法进行修正直到得到随机实例的最优解为止。事实上，算法的效率对初始赋值具有较强的依赖性。一组好的启发式初始赋值会大大提高不完全算法的求解效率。而置信传播算法（BP）是一种经典的消息传递算法，在求解NP-完全问题中取得了很好的效果。基于以上分析，本文将置信传播算法（BP）与文献[13]中提出的改进的模拟退火算法RSA相结合，提出了两个BP-RSA算法用于求解具有可变取值域的随机约束满足问题即RB 模型，分别称为BP-RSA-1算法和BP-RSA-2 算法。在这两个算法中，先将RB 模型的随机实例表示成因子图，利用BP迭代方程收敛后得到变量取其定义域中各个分量的边际概率，分别采用最大概率赋值和最小分量熵赋值的策略得到一个启发式的初始赋值，然后再利用RSA算法对这个初始赋值进行修正，从而得到这个随机实例的最优解。数值结果表明：在控制参数（即约束紧度）进入相变区域时，算法总是能有效地找到RB模型随机实例的解，并且表现出显著优于RSA算法的性能。在非常接近理论的可满足性相变点时本文提出的BP-RSA-1 算法和BP-RSA-2 算法都陷入了局部最优解，从而失效。虽然这两个算法此时都无法找到RB 模型随机实例的解，但是得到的最优解只使得极少数的约束不可满足。

# 1 RB模型

设 $X = \{ x _ { 1 } , x _ { 2 } , . . . , x _ { N } \}$ 表示 $N$ 个变量的集合，每个变量 $x _ { i }$ 都在定义域 $D = \{ 1 , 2 , 3 , . . . , d \}$ 中取值，令 $\boldsymbol { d } = \boldsymbol { N } ^ { \alpha }$ ， $\alpha > 0$ 为常数;

$C = \left\{ C _ { 1 } , C _ { 2 } , . . . , C _ { M } \right\}$ 表示 $M$ 个约束的集合，每个约束$C _ { a } = < X _ { a } , Q _ { a } >$ ，这里 $X _ { _ a } = \{ x _ { 1 } ^ { a } , x _ { 2 } ^ { a } , . . . , x _ { k } ^ { a } \}$ 表示从 $N$ 个变量中随机挑选 $k$ （ $k \geq 2$ ）个不同的变量， $Q _ { a }$ 表示 $X _ { a }$ 的不协调赋值集合来限制这 $k$ 个变量的取值，即若对 $X _ { a }$ 中这 $k$ 个变量的赋值属于 $Q _ { a }$ ，则称约束 $C _ { a }$ 是不可满足的，否则就称这个约束就是可满足的。本文由以下两步生成RB 模型的随机实例$\mathrm { R B } ( k , N , r , \alpha , p ) ^ { [ 1 ] }$ 。

a)从可能的 $\binom { N } { k }$ 个约束中随机、可重复地挑选 $M$ 个构成约束集合 $\{ C _ { a } \} _ { a = 1 } ^ { M }$ ，这里 $M = r N \ln N$ 且 $r > 0$ 是常数；

b)对每个约束 $C _ { a } = < X _ { a } , Q _ { a } >$ ，随机挑选 $k$ 个不同的变量即 $X _ { a }$ 构成约束 $C _ { a }$ ；从可能的 $d ^ { k }$ 个赋值中随机、不重复地选取$p d ^ { k }$ 个 $k$ -元赋值作为 $X _ { a }$ 的不协调赋值集合 $Q _ { a }$ ，即 $Q _ { a } \subset D ^ { k }$ 且$\left| Q _ { a } \right| = p d ^ { k }$ ，这里 $0 < p < 1$ 表示约束紧度。

可以看出，在RB模型中，变量的定义域规模 $d$ 随着变量数 $N$ 的增加呈多项式级增长，约束数目的阶为 $O ( N \ln N )$ 。许可和李未在文献[1]中已经严格证明RB模型存在精确的可满足性相变现象，即用 $ { \operatorname { P r } } ( S A T )$ 表示随机实例 $\mathrm { R B } ( k , N , r , \alpha , p )$ 有解的概率，则有以下结论成立：

定理1设 $p _ { s } = 1 - e ^ { - \frac { \alpha } { r } }$ ，若 $\alpha > \frac { 1 } { k } \ , \quad r > 0$ 是两个常数，且满足 $k e ^ { - \frac { \alpha } { r } } \geq 1$ ，则

$$
\operatorname* { l i m } _ { N \to \infty } \operatorname* { P r } ( S A T ) = { \left\{ \begin{array} { l l } { 1 , } & { p < p _ { s } } \\ { 0 , } & { p > p _ { s } } \end{array} \right. } \circ
$$

定理2 设 $r _ { s } = - \frac { \alpha } { \ln ( 1 - p ) }$ 若 $\alpha > \frac { 1 } { k } \ , 0 < p < 1$ 是两个常 数，且满足 $k \geq \frac { 1 } { 1 - p }$ 则

$$
\operatorname* { l i m } _ { N  \infty } \mathrm { P r } ( S A T ) { = } \{ \begin{array} { l l } { 1 , \quad r < r _ { s } } \\ { 0 , \quad r > r _ { s } } \end{array} 
$$

这两个定理表明存在阈值 $p _ { s }$ 或 $r _ { s }$ ，当 $N \to \infty$ 时，若 $p > p _ { s }$ （或 $r > r _ { s }$ )，RB 模型随机实例可满足的概率趋于0；若 $p < p _ { s }$ （或 $r < r _ { s }$ )，RB模型随机实例可满足的概率趋于1。也就是说随着控制参数 $p$ （或 $\boldsymbol { r }$ ）的不断增加，随机实例有解的概率经历了从1到0的突然转变，这就是所谓的可满足性相变现象。2006年，许可和李未在文献[7]中证明了RB模型的随机实例对于树型归结具有指数级下界，指出RB模型在相变区域能产生大量的难解实例。

# 2 两种改进的置信传播算法

# 2.1RB 模型的因子图表示

将RB模型随机实例 $\mathrm { R B } ( k , N , r , \alpha , p )$ 表示成因子图形式，如图1所示。因子图是一个二分无向图，其中变量节点用圆圈表示，记做 $i , j , k , \dots$ ；约束节点用方框表示，记作 ${ \scriptstyle a , b , c , \ldots }$ ；若变量 $i$ 出现在约束 $a$ 中，则 $( a , i )$ 用边相连。显然，每个约束节点的度为 $k$ ，每个变量节点的平均度为 ${ \frac { M } { N } } = r \ln N$ ，因此RB 模型随机实例的因子图是局部树状结构的，这是使用置信传播算法的先决条件。

![](images/a221221442157ed4ae54f7a2911b704a597cf26664834bd63ef2daa50c2d7020.jpg)  
图1RB 模型随机实例的因子图表示

由于 $k \geq 2$ 时RB 模型都是NP-完全的，因此算法实验中取$k = 2$ ，即考虑算法在随机实例 $\mathrm { R B } ( 2 , N , r , \alpha , p )$ 上的性能。若取一组参数 $N = 6$ ， $r = 0 . 9$ ， $\alpha = 0 . 6$ ， $p = 0 . 2$ ，则 $d = 3 \ , \ \vert Q \vert = 2$ ，$M = 1 0$ ，由RB(2,6,0.9,0.6,0.2)生成的一个随机实例的因子图如图2所示， $Q _ { a }$ 是约束 $a$ 相应的不协调赋值集合。不难验证，对这6个变量的一组完全赋值 $X = \{ 3 , 3 , 3 , 2 , 1 , 1 \}$ 是这个实例的一个解.

![](images/b8b46157431032c588d24584271b821cccfb95b24ee9dc3ac875fbecbfa1072c.jpg)  
图2由RB(2,6.0.9.0.6.0.2)生成的一个随机实例的因子图

# 2.2 BP方程

设 $X _ { 0 } = ( x _ { 1 } , x _ { 2 } , . . . , x _ { N } )$ 为RB模型随机实例的一组完全赋值，$X _ { 0 } ^ { a } = ( x _ { 1 } ^ { a } , x _ { 2 } ^ { a } , . . . , x _ { k } ^ { a } )$ 为构成约束 $a$ 的变量的一组赋值。将目标函数定义为不可满足约束的数目，即

$$
E ( X _ { 0 } ) = \sum _ { a = 1 } ^ { M } [ 1 - S ( X _ { 0 } ^ { a } ) ]
$$

其中

$$
S ( X _ { 0 } ^ { a } ) = { \left\{ \begin{array} { l l } { 1 , \quad } & { { \ddagger { \left( x _ { 1 } ^ { a } , x _ { 2 } ^ { a } , . . . , x _ { k } ^ { a } \right) } \notin Q _ { a } } } \\ { 0 , \quad } & { { \ddagger { \left( x _ { 1 } ^ { a } , x _ { 2 } ^ { a } , . . . , x _ { k } ^ { a } \right) } \in Q _ { a } } } \end{array} \right. }
$$

由此可见，若目标函数值为0，表示这组完全赋值就是实例的一个解。否则，不是这个实例的解。

在因子图的每条边 $( i , a )$ 上定义两种信息，分别为变量发送给约束的信息 $\mu _ { i \to a } ( d _ { i } )$ 和约束发送给变量的信息 $\eta _ { a  i } ( d _ { i } )$ 。这里 $\mu _ { i \to a } ( d _ { i } )$ 表示在假设没有约束 $a$ 的情况下，变量 $i$ 取值为 $d _ { i }$ （ $\boldsymbol { d } _ { i } \in D$ ）的概率； $\eta _ { a  i } ( d _ { i } )$ 表示约束 $a$ 要求变量 $i$ 取值为 $d _ { i }$ （ $d _ { i } \in D$ )的概率。根据统计物理学中无序系统的空腔场理论，可得置信传播方程即BP迭代方程为

$$
\mu _ { i \to a } ( d _ { i } ) = Z _ { i \to a } \prod _ { b \in V ( i ) \backslash a } \eta _ { b \to i } ( d _ { i } )
$$

$$
\eta _ { a  i } ( d _ { i } ) = Z _ { a  i } \sum _ { \substack { d _ { j } \in D , j \in V ( a ) \backslash i } } S ( X _ { 0 } ^ { a } ) \prod _ { j \in V ( a ) \backslash i } \mu _ { j  a } ( d _ { j } )
$$

其中： $V ( i )$ 表示与变量 $i$ 相关联的约束集合， $\vert V ( i ) \backslash a$ 表示从$V ( i )$ 中去除约束 $a$ ； $V ( a )$ 表示与约束 $a$ 相关联的变量集合，$V ( a ) \backslash i$ 表示从 $V ( a )$ 中去除变量 $i$ ; $Z _ { i \to a }$ 与 $Z _ { a  i }$ 是归一化因子。若BP迭代方程收敛，则可以得到一组不动点记为 $\eta _ { a  i } ^ { f } ( d _ { i } )$ 。从而可以利用 $\eta _ { a  i } ^ { f } ( d _ { i } )$ 来求出每个变量 $i$ 取值的边际概率 $\eta _ { i } ( d _ { i } )$ ，即

$$
\eta _ { i } ( d _ { i } ) = \frac { \prod _ { a \in V ( i ) } \eta _ { a \to i } ^ { f } ( d _ { i } ) } { \sum _ { d _ { i } \in D } \prod _ { a \in V ( i ) } \eta _ { a \to i } ^ { f } ( d _ { i } ) }
$$

从而变量 $i$ 取值为 $d _ { i }$ 的分量熵为

$$
\mathrm { S } _ { i } ( d _ { i } ) { = } { - \eta _ { i } ( d _ { i } ) \cdot \ln ( \eta _ { i } ( d _ { i } ) ) }
$$

在下面的算法中，将采用两种策略对所有变量进行赋值，即最大概率赋值和最小分量熵赋值。最大概率赋值就是每个变量取其边际概率中最大值所对应的那个分量，而最小分量熵赋值就是每个变量取其最小分量熵所对应的那个分量。

在约束紧度 $p$ 较小的情况下，由这两种策略得到的所有变量的一组完全赋值可能就是一个解。但是随着 $p$ 的逐渐增加，这组完全赋值就不再是问题的解。这种情况下，把得到的这组赋值作为启发式的初始赋值，再利用文献[13]中改进的模拟退火算法RSA对这组赋值进行修正，从而得到问题的最优解。本文将这种置信传播（BP）与改进的模拟退火（RSA）相结合的算法称为BP-RSA算法。采用最大概率策略和采用最小分量熵策略得到启发式初始赋值的算法分别称为BP-RSA-1算法和BP-RSA-2算法。

# 2.3 BP-RSA-1算法

输入：由RB 模型生成的一个随机实例的因子图，BP方程的最大迭代次数 $t _ { \mathrm { m a x } }$ ，精度 $\varepsilon$ ；初始温度 $T _ { \mathrm { 0 } }$ ，终止温度 $T _ { f }$ ，温度控制参数 $a$ ，同一温度下迭代的次数 $L$ 。

输出：最优解及最小不可满足约束的数目，或BP方程不 收敛。

a)运行子程序BP 算法，得到 $\eta _ { _ { a  i } } ^ { f } ( d _ { i } )$ ·

b)对每个变量 $i$ ，由式（5）计算其取各个分量的边际概率$\eta _ { i } ( d _ { i } )$ 。将边际概率中最大值所对应的分量取值赋给变量 $i$ ，从而得到一组启发式初始赋值并设为 $s o l$ ·

c)由式（1）计算当前目标函数 $E ( s o l )$ ，令当前最优的一组赋值 $s o l \_ b e s t = s o l$ ，及当前最少不可满足约束的数目$E _ { - } b e s t = E ( s o l )$

d)令 $\scriptstyle { T = T _ { 0 } }$ ：

e)令 $i = 0$ ;

f)if( $E _ { - } b e s t = = 0$ ）{输出最优解 sol_best，及最少不可满  
足约束数目为 $| 0 \}$ ;else { do step7};g)随机生成一个0到1的实数 $r a n d _ { 0 }$ ：if( $r a n d _ { 0 } < 1 - 3 / T$ ){随机选出 $s o l$ 中的变量重新赋值，从而得  
到新的赋值 $s o l _ { - } n e w \}$ else{令 $s o l = s o l \_ b e s t$ ，随机选取一个不可满足的约束，从  
其所关联变量的协调赋值集合中随机选取一组赋值，从而得到  
一组新的赋值记作 $s o l \mathrm { ~ \ } _ { - } n e w \mathrm { ~ \ } \}$ h)计算 $\Delta E = E ( s o l ) - E ( s o l \_ n e w )$ if( $\Delta E < 0$ ){随机生成一个大于0小于1的实数 $r a n d _ { 1 }$ （20if $( r a n d _ { 1 } < \exp ( - \Delta E / T ) )$ {令 $s o l = s o l \_ n e w \_$ （204号else {do step i)};（204 $\}$ ;else {令 $s o l = s o l _ { - } n e w$ ， $E ( s o l ) = E ( s o l \_ n e w ) \_$ ：i)if $( \ E ( s o l ) < E _ { - } b e s t \ \{ \ s o l \_ b e s t = s o l \ , \quad E _ { - } b e s t = E ( s o l ) \ ,$   
do j)}else {do step10};j）) $i = i { + } 1$ ;$\mathbf { k } )$ if $( i < L ) \{ \mathrm { g o }$ to step6}， else{ $T = a \cdot T$ do step 1) };1) if ( $T < T _ { f }$ ){则输出没找到解}，else {do step e) $\}$ 。  
其中，子程序 BP 算法如下：a)令 $t = 0$ ，随机初始化因子图所有边上约束发送给变量的  
信息 $\eta _ { a  i } ^ { 0 } ( d _ { i } )$ ;$\boldsymbol { \mathbf { b } } ) \boldsymbol { t } = \boldsymbol { t } + \boldsymbol { \mathbf { 1 } }$ c)将 $\eta _ { a  i } ^ { t - 1 } ( d _ { i } )$ 代入式（3）得到变量发送给约束的信息  
（20 $\mu _ { i \to a } ^ { t } ( d _ { i } )$ （如果 $i$ 为叶子节点即 $V ( i ) \backslash a = \emptyset$ ，则令 $\mu _ { i \to a } ^ { t } ( d _ { i } ) = \frac { 1 } { d } \ : )$ d)将 $\mu _ { i \to a } ^ { t } ( d _ { i } )$ 代入（4更新信息 $\eta _ { a  i } ^ { t } ( d _ { i } )$ ：e)if（所有边上都满足 $| \eta _ { a  i } ^ { t } - \eta _ { a - i } ^ { t - 1 } | < \varepsilon \quad ) \{$ 则令  
$\eta _ { a  i } ^ { f } ( d _ { i } ) = \eta _ { a  i } ^ { t } ( d _ { i } )$ ，输出 $\eta _ { _ { a  i } } ^ { f } ( d _ { i } ) \}$ （204号else {do step b) $\}$ ：f) if( $t = t _ { \operatorname* { m a x } }$ )，{输出 BP 方程不收敛}。

2.4 BP-RSA-2算法

在 BP-RSA-2算法中，采用最小分量熵策略来得到一组启发式初始赋值，然后再用RSA算法对这组初始赋值进行修正。也就是把BP-RSA-1算法中的b)改为

b)对每个变量 $i$ ，由式(6)计算其各个分量的分量熵 ${ \bf S } _ { i } ( d _ { i } )$ 。将最小分量熵中所对应分量的取值赋给变量i，从而得到一组启发式初始赋值并设为sol；

输入输出及其他步骤均与BP-RSA-1算法相同。

# 3 实验结果与算法分析

# 3.1算法结果

对于RB 模型，本文取 $k = 2$ ， $\alpha = 0 . 8$ ， $r = 3$ ，$N \in \{ 2 0 , 4 0 , 6 0 , 8 0 , 1 0 0 \}$ 。由定理1可知二元RB 模型理论的可满足性相变点为 $p _ { s } = 0 . 2 3 4$ 。在不同 $N$ 下，二元 RB 模型的定义域规模 $d$ ，约束数目 $M$ 如表1所示。

表1二元RB 模型在不同问题规模 $N$ 下的参数值  

<html><body><table><tr><td>N</td><td>a</td><td>r</td><td>d</td><td>M</td><td>Ps</td></tr><tr><td>20</td><td>0.8</td><td>3</td><td>11</td><td>180</td><td>0.234</td></tr><tr><td>40</td><td>0.8</td><td>3</td><td>19</td><td>443</td><td>0.234</td></tr><tr><td>60</td><td>0.8</td><td>3</td><td>26</td><td>737</td><td>0.234</td></tr><tr><td>80</td><td>0.8</td><td>3</td><td>33</td><td>1052</td><td>0.234</td></tr><tr><td>100</td><td>0.8</td><td>3</td><td>40</td><td>1382</td><td>0.234</td></tr></table></body></html>

在BP-RSA-1和BP-RSA-2 算法中，均取BP方程的最大迭代次数 $t _ { \mathrm { m a x } } = 1 0 ^ { 3 }$ ，迭代精度 $\varepsilon { = } 1 0 ^ { - 4 }$ 。对于不同的 $N$ ，BP迭代方程在随机生成的50个 $\mathrm { R B } ( 2 , N , 3 , 0 . 8 , p )$ 实例上的收敛情况如图3所示。从图3可以看出，BP迭代方程在可满足性相变点$p _ { s } = 0 . 2 3 4$ 之前都是以概率1收敛的。因此总能够利用收敛后得到的不动点产生一组启发式的初始赋值。在RSA算法中，取初始温度 $T _ { \scriptscriptstyle 0 } = 9 7$ ，终止温度 $T _ { f } = 3$ ，温度控制参数 $a = 0 . 8$ ，同一温度下迭代的次数 $L = 1 0 ^ { 3 }$ 。

![](images/868aee5f922b33a31e20f69296d8320bbf374dee89127bda9e2fb0506c457c79.jpg)  
图3BP迭代方程收敛结果

对于不同的问题规模 $N$ ，分别在随机生成的50个实例$\ R { \bf B } ( 2 , N , 3 , 0 . 8 , p )$ 上来测试BP-RSA-1和BP-RSA-2这两个算法的求解性能，数值结果分别如图4和5所示。从图4可以看出，在 $N = 1 0 0$ 时，BP-RSA-1算法在约束紧度 $p \leq 0 . 1 1$ 的范围内以概率1找到解，而当 $p > 0 . 1 5$ 时算法失效；在 $N = 2 0$ 时，BP-RSA-1算法在约束紧度 $p \leq 0 . 1 6$ 的范围内以概率1找到解，$p > 0 . 2 3$ 则算法失效。从图5可以看出，在 $N = 1 0 0$ 时,BP-RSA-2 算法在约束紧度 $p \leq 0 . 1 1$ 的范围内以概率1找到解，而当$p > 0 . 1 5$ 时算法失效；在 $N = 2 0$ 时，BP-RSA-2 算法在约束紧度$p \leq 0 . 1 6$ 的范围内以概率1找到解， $p > 0 . 2 2$ 则算法失效。值得注意的是在这组参数下，理论的可满足性相变点为 $p _ { s } = 0 . 2 3 4$ ，因此这两个算法在接近相变点时都能有效地找到实例的解，并且这两种算法的求解效率几乎一样。

![](images/3b25655e4b74a463854bd90f4300b4ccb723d89abdc9bce122d93309eba9c135.jpg)  
图4BP-RSA-1算法在50个随机实例上的求解概率

![](images/90aa664284a4a9519f6da52ec4cd55bf3e18d7052a579cfbe537ce6c122140a2.jpg)  
图5BP-RSA-2算法在50个随机实例上的求解概率

BP-RSA-1算法和BP-RSA-2算法对于不同的变量数目 $N$ 在 $p = 0 . 0 6$ 处求解一个实例所需的平均运行时间如图6所示。这两个算法对于不同的 $N$ 在 $p = 0 . 1$ 处求解一个实例所需的平均运行时间如图7所示。

![](images/c760d6ffa71ed6ab4a7341a9b21a7f9cdde38034951df071be983f52b0ce7aa1.jpg)  
图6算法在 $\scriptstyle { p = 0 . 0 6 }$ 处的平均时间

![](images/68943763cc1c2dcaeb56b68fc0344ee014fe7f92ed3d4ab3ccae0f4c7d439fd5.jpg)  
图7算法在 $p { = } 0 . 1$ 处的平均时间

由于RB模型每个变量的取值有 $N ^ { \alpha }$ 个，因此 $N$ 个变量可能的取值就有 $N ^ { \alpha N }$ 个，即在最坏情况下，算法的时间复杂度为$O ( N ^ { \alpha N } )$ 。从图6和7可以看出，BP-RSA-1和BP-RSA-2算法具有指数级的时间复杂度，即算法的运行时间随着变量数目 $N$ 的增加呈指数级增长，并且这两个算法在相同的约束紧度下运行时间基本相同。

# 3.2算法比较

将本文提出的 BP-RSA-1算法和BP-RSA-2算法与文献[13]中提出的两种改进的模拟退火算法即GSA算法、RSA算法、随机游走算法以及BP 随机游走算法在 $N = 1 0 0$ 时进行对比，如图8所示。不难看出，本文提出的BP-RSA-1和BP-RSA-2算法的效率相差无几，都显著优于随机游走算法、RSA算法、BP随机游走算法。与GSA 算法相比，也表现出了良好的求解效率。取 $p = 0 . 1 2$ ，将RSA算法、GSA算法和BP-RSA-1算法在$N \in \{ 2 0 , 4 0 , 6 0 , 8 0 , 1 0 0 \}$ 的运行时间进行比较，如图9所示。可以看出，BP-RSA-1算法求解一个随机实例的平均时间明显小于RSA算法和GSA算法。这表明BP-RSA-1算法能更快地找到实例的解。

![](images/3ea26bb75972651a5c59ff629e45886d2766d6064715413310246c50a7a49bbd.jpg)  
图8算法求解效率的比较

![](images/52591f0161ee6cd3988d1d7a225ac1020fcf1b4d44ae44cca44abb5d8cacd0f7.jpg)  
图9算法平均运行时间的比较

# 3.3算法分析

在BP-RSA-1算法中，取 $N = 6 0$ ，BP迭代方程收敛的时间和BP-RSA-1算法的运行时间如图10所示。从图10可以看出，BP迭代方程收敛的时间随着约束紧度 $p$ 的增加呈线性增长，而随着 $p$ 的不断增大，BP迭代方程收敛时间占BP-RSA-1算法运行时间的比例越来越小，这就表明约束紧度 $p$ 越大，由置信传播(BP)算法得到的一组赋值就不再是实例的解，越需要RSA算法花费更多的时间来对这组启发式的初始赋值进行修正直到得到最优解。

从图4和5可以看出，BP-RSA-1和BP-RSA-2算法在理论相变点 $p _ { s } = 0 . 2 3 4$ 之前就已经失效，但是由这两种算法得到的最优解仅使得极少数约束是不可满足的。例如：取 $N = 6 0$ ，$M = 7 3 7$ ，当 $p { \geq } 0 . 1 7$ 时，由BP-RSA-1算法、BP-RSA-2 算法、

RSA算法和GSA算法所得到的平均最少不可满足约束的数目如表2所示。

![](images/4b6061cf43c0df9da934ddca2833657d29059b78274c2d3c18ad63a7238ec850.jpg)  
图10BP-RSA-1算法分步运行时间

表2算法失效时所得到的平均最少不可满足约束数目  

<html><body><table><tr><td>p</td><td>BP-RSA-1</td><td>BP-RSA-2</td><td>GSA</td><td>RSA</td></tr><tr><td>0.17</td><td>5.02</td><td>5.26</td><td>7.79</td><td>9.93</td></tr><tr><td>0.18</td><td>6.92</td><td>7.28</td><td>10.73</td><td>12.65</td></tr><tr><td>0.19</td><td>9.88</td><td>9.74</td><td>12.89</td><td>15.00</td></tr><tr><td>0.20</td><td>11.20</td><td>10.84</td><td>16.10</td><td>17.29</td></tr></table></body></html>

由表2可知，当 $p = 0 . 1 7$ 时，BP-RSA-1算法和BP-RSA-2算法的平均最少不可满足约束的数目占约束总数的比例约为$0 . 7 \%$ ；当 $p = 0 . 2 0$ 时，平均最少不可满足约束的数目占约束总数的比例约为 $1 . 5 \%$ 。这充分说明虽然这两个算法在非常接近理论相变点时找不到实例的解，但是得到的最优解仅使得不足 $2 \%$ 的约束不可满足。同时也可以看出，BP-RSA-1算法和BP-RSA-2算法所得到的平均最少不可满足约束的数目要低于由RSA算法和GSA算法所得到的平均最少不可满足约束的数目。

BP-RSA-1和BP-RSA-2这两个算法，都是利用BP方程迭代收敛到不动点后得到每个变量的边际概率分布，分别采用最大概率和最小分量熵的策略得到一组启发式的初始赋值，然后再利用RSA算法对这组赋值进行修正。从实验结果可以看出，这两个算法的求解概率和运行时间都基本相同。事实上，这两个算法虽然采用了不同的策略，但是得到的启发式的初始赋值是相同的。因此，这两个算法的性能基本相同。

由于这两个算法前期利用BP得到了一组启发式的初始赋值，这组初始赋值虽然不是随机实例的解，但是相对于RSA算法的随机初始化赋值，在一定程度上减少了不可满足约束的数目。因此后期再利用RSA算法进行修正时，大大提高了算法效率。因此BP-RSA-1和BP-RSA-2算法表现出了显著优越于RSA算法的性能。但是，由于在利用BP算法时，本文是同时将所有变量进行赋值的，这就忽略了变量之间取值的相互联系，没有充分考虑约束对变量取值的限制作用。从而导致算法在可满足性相变发生之前就已经失效。

# 4 结束语

本文提出了两个置信传播与模拟退火相结合的算法来求解具有可变取值域的随机约束满足问题（即RB模型)，分别称为BP-RSA-1和BP-RSA-2算法。这两个算法都是先通过BP迭代方程收敛后得到的不动点计算出所有变量取其各分量的边际概率，然后分别采取最大概率赋值和最小分量熵赋值的策略得到一组启发式的初始赋值，然后再通过执行RSA算法对得到的这组初始赋值进行修正直到得到最优解。而RSA算法则是对随机生成的一组初始赋值进行修正。实验结果表明，在接近理论相变点时，BP-RSA-1算法和BP-RSA-2算法都能有效地找到随机实例的解，且与RSA算法相比具有显著的优越性。虽然在理论可满足相变发生之前这两个算法已经失效，但是得到的最优解仅使得少于 $2 \%$ 的约束是不可满足的。因此，置信传播与模拟退火相结合的算法在求解大值域的约束满足问题时表现出了良好的性能，对求解大值域的约束满足问题具有一定的促进作用。

# 参考文献：

[1]Xu Ke,Li Wei.Exact phase transitions in random constraint satisfaction problems [J]. Journal of Artificial Inteligence Research,20oo,12 (1): 93- 103.   
[2]Achlioptas D,Kirousis L M,Kranakis E,et al.Random constraint satisfaction:A more accurate picture [C]// Proc of International Conference on Principles and Practice of Constraint Programming.Berlin: Springer, 1997: 107-120.   
[3]Smith B M. Constructing an asymptotic phase transition in random binary constraint satisfaction problems [J].Theoretical Computer Science,2001, 265 (1): 265-283.   
[4]Moloy M.Models for random constraint satisfaction problems [J].Siam Journal of Computing,2003,32 (4): 935-949.   
[5]Frieze A,Molloy M. The satisfiability threshold for randomly generated binary constraint satisfaction problems [J].Random Structure and Algorithms,2006,28 (3):323-339.   
[6]Xu Ke,Li Wei. Many hard examples in exact phase transitions [J]. Theoretical Computer Science,2006,355 (3): 291-302.   
[7]Xu Ke,Boussemart F, Hemery F,et al.Random constraint satisfaction: Easy generation ofhard(satisfiable) instance [J].Artificial Intelligence,2o07,171 (8-9): 514-534.   
[8]Zhao Chunyan, Zhou HJ, Zheng ZM,et al.A message-passing approach to random constraint satisfaction problems with growing domains [J].Journal of Statistical Mechanics: Theory and Experiment,2011,P02019.   
[9] 赵春艳，郑志明．一种基于变量熵求解约束满足问题的置信传播算法 [J]．中国科学:信息科学,2012,42(9):1170-1180.   
[10] Zhao Chunyan,Zhang Pan,Zheng Zhiming,et al.Analytical and beliefpropagation studies of random constraint satisfaction problems with growing domains [J].Physical Review E:Statistical Nonlinear & Soft

Matter Physics,2012,85 (2):016106.

[11]任雪亮．改进的置信传播算法在求解最大约束满足问题的应用 [D].长春：东北师范大学,2015.

[12]王晓峰，许道云.RB模型实例集上置信传播算法的收敛性[J].软件学报,2016,27(11):2712-2724.

[13]原志强，赵春艳．两种改进的模拟退火算法求解大值域约束足问题[J]计算机应用研究,2017,34(12):3611-3616.

[14] Riccitersenghi F, Semerjian G.On the cavity method for decimated random constraint satisfaction problems and the analysis of belief propagation guided decimation algorithms [J]. Journal of Statistical Mechanics Theory & Experiment,2009,9(3): 355-371.