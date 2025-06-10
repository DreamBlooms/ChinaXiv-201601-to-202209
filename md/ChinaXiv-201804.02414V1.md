# 自组织多目标粒子群优化算法

梁静1，郭倩倩1，岳彩通1，瞿博阳²(1．郑州大学 电气工程学院，郑州 450001;2.中原工学院 电子信息学院，郑州 450007)

摘要：针对多目标粒子群优化算法收敛性和多样性难以平衡的问题，提出一种利用问题的结构信息来解决多目标问题的自组织多目标粒子群算法。通过自组织映射网络发现种群和非支配解集分布的结构，构造出当前粒子的邻域关系，从邻域中选出非支配解，从而引导种群局部和全局的搜索。提出了精英学习策略，通过对精英粒子进行变异，引导算法跳出局部最优。实验结果表明，所提算法可以兼顾收敛性和多样性，有效地解决多目标优化问题。

关键词：多目标粒子群优化；自组织映射；种群分布；精英学习策略 中图分类号：TP183 doi: 10.3969/j.issn.1001-3695.2018.01.0070

# Self-organizing multi-objective particle swarm optimization algorithm

Liang Jing1, Guo Qianqian1, Yue Caitong1, Qu Boyang² (1.SchoolofElectricalEngineering,Zhengzhou University,Zhengzhou450ol,China;2.SchoolofElectric&Infortio Engineering,Zhongyuan University of Technology,Zhengzhou 45ooo7,China)

Abstract: In order to kep the balance betweenconvergence and diversityof multi-objective particle swarm optimization algorithm,thepaperproposed aself-organizing multi-objectiveparticle swarmalgorithm(SMPSO),whichutilized structureof population to solve multi-objectiveoptimization problems.The distributionofthe population and non-dominatedsolutions founded by self-organizing map network helped toconstruct the particleneighborhood relations，so as to improve the algorithm'slocaland globalsearchabilitybyselectingnon-dominatedsolutionasleaderintheneighborhood.Theeliteeaing strategy could helppopulation jumpoutlocal optimum bydoing mutationon eliteparticles.Theexperimental results show its ability to keepconvergenceand diversity,andshowits effectivenesstosolvethemulti-objectiveoptimizationproblems.

Key words: multi-objective particleswarm optimization;self-organizing map; populationdistribution;elite learning strategy

# 0 引言

在现实应用中，有很多问题需要同时优化多个目标，两个及以上目标的问题叫做多目标优化问题(multi-objectiveoptimizationproblems,MOP)。这些目标之间往往是相互冲突的，一个目标的性能提高会导致其他目标性能的降低，因此同时优化多个目标是很困难的。不同于单目标优化问题，多目标问题得到的不是一个解，而是由许多非支配解组成的解集，称为帕累托解集。帕累托解集在目标空间对应的目标值便组成了帕累托前沿。由于多目标问题得到的解可能有无限多个，所以找出所有的解是不实际的。在实际操作中，找出一定数量的非支配解，尽可能覆盖并靠近真正的帕累托前沿，且这些解分布均匀，是本文所需要解决的挑战性难题。

解决多目标问题的方法有两大类，一类是传统的数学解析性算法，一类是进化算法。进化算法是一类以种群为基础的带有随机搜索方式的方法，具有经过不断演化而获得逼近真实帕累托前沿的能力，因此被广泛应用到多目标问题的求解上，如NSGA-II 错误！未找到引用源。、多目标差分(DE）错误！未找到引用源。、多目标粒子群(MOPSO)算法错误!未找到引用源。在以种群为基础的算法中，粒子群算法具有快速收敛的特点错误!未找到引用源。。对于多目标粒子群优化算法，平衡收敛性和多样性是至关重要的。因此提出了很多改进策略：随机选择策略，从外部存储中随机选择一个全局最优gbest是简单且高效的策略；超体积贡献，拥挤距离等也可以作为选择 gbest 的指标；一个种群分不同偏好的子种群错误!未找到引用源。，一个负责全局搜索，另一个负责局部收敛；文献错误!未找到引用源。中粒子不同维度向不同的个体学习，可以增加种群多样性。EPSO 错误!未找到引用源·引入了均衡因子，以提高种群全局搜索能力。AGE-MOPSO 错误!未找到引用源。利用种群收敛状态，自适应调整惯性权重和学习因子的值，以达到探索和开发的最佳平衡。但这些策略很少利用到多目标优化问题的特性，即在一定的条件下， $\mathbf { \nabla } _ { m }$ 个目标的多目标问题在目标空间的帕累托前沿及决策空间的帕累托解集会形成 $m { - } 1$ 维的片段连续的流型形状[9]。基于多目标问题的这种规则性，文献错误！未找到引用源。提出将自组织映射网络应用于种群的重组操作中，有效地提高了多目标算法的性能。但目前尚未有人将自组织映射网络与多目标粒子群优化算法结合。本文提出的自组织引导机制的自组织多目标粒子群优化算法(self-organizingmulti-objective particle swarmoptimizationalgorithm，SMPSO)，利用自组织映射网络可以将高维信息映射到低维网络，且保持特征分布不变性的特点，映射当前种群和帕累托解集的结构信息，为粒子构建新的邻域关系，引导粒子的搜索过程，以此平衡多目标粒子群算法的收敛性和多样性。

# 相关背景知识

# 1.1 多目标优化问题

一个连续的多目标优化问题可以表述为如下形式:

$$
\begin{array} { l } { \displaystyle \mathrm { M i n ~ } \mathrm { F } ( \mathrm { x } ) = ( f _ { 1 } ( x ) , f _ { 2 } ( x ) , . . . , f _ { m } ( x ) ) } \\ { \mathrm { s . t . ~ } x { = } ( x _ { 1 } , x _ { 2 } , . . . , x _ { n } ) \in \Omega } \end{array}
$$

其中： $\Omega = [ a _ { i } , b _ { i } ] ^ { n }$ 是搜索空间的可行域； $x$ 是决策空间 $\Omega$ 中的$n$ 维决策变量； $\mathbf { \nabla } _ { m }$ 是待优化目标的个数。函数 $\mathrm { F } : \Omega \to R ^ { m }$ 定义了 $\mathbf { \nabla } _ { m }$ 个待优化目标函数由决策空间 $\Omega$ 到目标空间 $\boldsymbol { R } ^ { m }$ 的映射。

一些多目标问题的相关定义如下：

定义1帕累托支配性。决策变量 $x$ 支配决策变量 $y ($ 记为$x \prec y$ )当且仅当满足以下条件：

$$
\begin{array} { r l } & { ( \forall i \in \{ 1 , 2 , . . . , m \} : f _ { i } ( x ) \leq f _ { i } ( y ) ) } \\ & { \land ( \exists j \in \{ 1 , 2 , . . . , m \} : f _ { i } ( x ) < f _ { i } ( y ) ) } \end{array}
$$

即在 $m$ 个目标函数中， $x$ 的每个目标函数值都不大于 $y$ 的目标函数值，且 $x$ 至少有一个目标函数值小于 $y$ 的目标函数值。

定义2帕累托解。决策变量 $x$ 是帕累托解：

$$
\lnot \exists y \in \Omega : y \prec x
$$

即在可行域空间内，不存在任何一个粒子支配粒子 $x$ 。

定义3帕累托解集（Pareto optimal set，PS）定义为

$$
\mathbf { P S } = \left\{ x \in \Omega \vert \lnot \exists y \in \Omega \colon y \prec x \right\}
$$

定义4帕累托前沿（Pareto front，PF）定义为

$$
\mathbf { P F } = \{ \operatorname { F } ( x ) | x \in \mathbf { P S } \}
$$

# 1.2多目标问题的规则性

在一定条件下，一个连续的 $m$ 个目标问题的PF和PS会形成 $m { - } 1$ 维的流型，如0所示。

鉴于这种规则性，有很多构造分布模型的算法错误!未找到引用源。，例如用主成分分析法构造模型错误！未找到引用源。，利用模型产生新解，但这种构造模型的方法，效果依赖于模型参数的选取。

# 1.3粒子群优化算法

粒子群优化算法是基于种群的随机搜索的全局寻优进化算法错误!未找到引用源。它通过模仿鸟类运动规则在搜索空间中寻找最优位置。与其他进化算法相似，搜索由种群个体来组成，这些搜索个体叫做粒子。粒子由两个特征即位置和速度信息组成。假设当前种群由 $N$ 个粒子组成，粒子的搜索范围是 $n$ 维超空间。粒子 $i \in ( 1 , 2 , . . . N )$ 的位置和速度信息分别表示为$x _ { i } = ( x _ { i 1 } , x _ { i 2 } , . . . , x _ { i n } )$ 和 $\nu _ { i } = ( \nu _ { i 1 } , \nu _ { i 2 } , . . . , \nu _ { i n } )$ 。其更新公式如下：

$$
\begin{array} { c } { { \nu _ { i } ( t + 1 ) = w ^ { * } \nu _ { i } ( t ) + c _ { 1 } r _ { 1 } ( x _ { p b e s t _ { i } } - x _ { i } ( t ) ) + c _ { 2 } r _ { 2 } ( x _ { g b e s t _ { i } } - x _ { i } ( t ) ) } } \\ { { { } } } \\ { { x _ { i } ( t + 1 ) = x _ { i } ( t ) + \nu _ { i } ( t + 1 ) } } \end{array}
$$

其中： $\mathbf { \Psi } _ { t }$ 是迭代代数； $w$ 是可以用来平衡局部和全局搜索的惯性因子，较高的惯性因子给先前经验大的权值而有益于全局搜索，反之，偏向于局部搜索； $c _ { _ 1 } , c _ { _ 2 }$ 代表两个加速因子影响种群的收敛速度； $r _ { 1 } , r _ { 2 }$ 是在(0,1)正态分布之间产生的随机量；pbest 和gbest分别是个体最优和全局最优解。

![](images/4bf6b049c13ad8368c485824a4fa46099542c2f77ceaf072488559c21ab3be68.jpg)  
图1多目标问题的规则性

多目标粒子群算法中，寻找的不是唯一的gbest，而是用邻域最优的个体nbest代替gbest。式（6）改为如下形式：

$$
\nu _ { i } ( t + 1 ) = w ^ { * } \nu _ { i } ( t ) + c _ { 1 } r _ { 1 } ( x _ { p b e s t _ { i } } - x _ { i } ( t ) ) + c _ { 2 } r _ { 2 } ( x _ { n b e s t _ { i } } - x _ { i } ( t ) )
$$

# 2 自组织多目标粒子群优化算法SMPSO

本文提出的 SMPSO 算法，主要是利用自组织映射网络（self-organizingmappingnetwork,SOM）发现种群和多目标问题帕累托前沿的结构信息，然后引导粒子的飞行。同时结合了精英学习策略和多项式变异，增加种群多样性。SMPSO流程如0所示。

![](images/396b4fb19540aeb6a7167574ad5f53daaa649cef71e1834092b684232df580ff.jpg)  
图2SMPSO的流程

# 2.1 SOM 模型为 PSO 粒子构建邻域信息

神经网络与进化算法的结合大多是用进化算法优化神经网络的参数错误!未找到引用源。，本文中利用自组中映射网络为粒子群算法中的粒子构建邻域关系，从而引导粒子的飞行。

如0所示，SOM包括一个输入层和一个表示层。假设输入数据是 $n$ 维，表示层有 $N = N _ { 1 } \times N _ { 2 }$ 个神经元。每个神经元$u \in ( 1 , 2 , . . . , N )$ 赋予位置 $z ^ { u } = ( z _ { 1 } ^ { u } , z _ { 2 } ^ { u } )$ 和权值 $\boldsymbol { w } ^ { u } = ( w _ { 1 } ^ { u } , w _ { 2 } ^ { u } , . . . , w _ { n } ^ { u } )$ 。

![](images/11a1c3a45e5ab1d829bee87fdafc1bcd11419106188f627756038327c6565f07.jpg)  
图3SOM的拓扑结构示意图

SOM的流程分为两个阶段：a)学习阶段，随机选择训练数据，根据欧氏距离选择获胜神经元，更新获胜神经元及其邻域神经元的权值；b)聚类阶段，将测试数据映射到神经元，相似的数据会映射到相邻神经元。

构建的 SOM 模型，神经元的权值 $\boldsymbol { w } ^ { u } = ( w _ { 1 } ^ { u } , w _ { 2 } ^ { u } , . . . , w _ { n } ^ { u } )$ 的初始值与种群粒子的位置信息相同，每迭代一代更新一次。进化过程中得到的新的非支配解的位置信息是SOM的训练数据（TS），SOM更新之后，将种群（POP）和外部存储集（EXA）的粒子位置映射在网络结构上，根据神经元的位置信息，构建粒子的邻域，从而选择合适的引导粒子nbest。具体步骤如算法1所示。

# 2.2 算法1nbest 的选择

输入：POP，EXA，TS，权值 $\boldsymbol { w } ^ { u } = ( w _ { 1 } ^ { u } , w _ { 2 } ^ { u } , . . . , w _ { n } ^ { u } )$ ,学习率 $\eta _ { \mathrm { 0 } }$ ,学习半径 $\sigma _ { 0 }$ 。

输出： $\boldsymbol { w } ^ { u } = ( w _ { 1 } ^ { u } , w _ { 2 } ^ { u } , . . . , w _ { n } ^ { u } )$ ，每个粒子的nbest_i。

a)计算每个神经元之间的距离 $\left\| z ^ { u } - z ^ { u ^ { * } } \right\| _ { 2 }$ ,根据距离排序,神经元 $\mathrm { ~ u ~ }$ 的邻域神经元集合 ${ \boldsymbol { \mathrm { I } } } ^ { u }$ ， $\textstyle \mathrm { I } _ { k } ^ { u }$ 是距离神经元 $\mathrm { ~ u ~ }$ 第 $k ^ { \mathrm { { t h } } }$ 近的神经元。

b)选择训练数据 $x = ( x _ { 1 } , . . . x _ { i } , . . . x _ { n } ) \in \mathbf { T S }$ ，判断获胜神经元：

$$
u ^ { \prime } = \arg \operatorname* { m i n } _ { 1 \leq u \leq N } \left\| x - w ^ { u } \right\| _ { 2 }
$$

其中： $\left. _ { - } \right.$ 是欧氏距离。

c)更新获胜神经元及其邻域神经元 $( u \in \mathbf { U } )$ 的权值：

$$
\begin{array} { r l } & { \mathbf { U } = \{ u \left| 1 < u \leq N \wedge \left\| z ^ { u } - z ^ { u ^ { \star } } \right\| _ { 2 } < \sigma ( t ) \} \right. } \\ & { \left. w _ { t + 1 } ^ { u } = w _ { t } ^ { u } + \eta ( t ) ^ { \ast } \exp ( - \left\| z ^ { u } - z ^ { u ^ { \star } } \right\| _ { 2 } ) ( x - w _ { t } ^ { u } ) \right. } \end{array}
$$

其中： $\eta ( t ) = \eta _ { \scriptscriptstyle 0 } * ( 1 - \frac { t } { M A X \mathrm { g e } n } )$ ； $\sigma ( t ) = { \sigma _ { 0 } } ^ { * } ( 1 - \frac { t } { M A X g e n } )$ ；MAXgen是最大迭代代数。

d)将待分类数据POP、EXA输入，根据式（9）判断获胜神经元。ind2unit记录POP每个粒子的获胜神经元，unit2nbest记录每个神经元上对应的nbest。

e)nbest_i记录粒子 $\mathrm { ~ x ~ }$ 的nbest备选库

for $\mathrm { i } { = } 1 { : } \mathrm { N P }$

$\mathrm { u } =$ ind2unit(i)；/粒子i的获胜神经元u

nbest_i $\mathbf { \Sigma } = \mathbf { \Sigma }$ unit2nbest $\{ \boldsymbol { \mathrm { I } } _ { k } ^ { u } \}$ ;/神经元u的邻域神经元上对 应的nbest/

end

如0所示，当前粒子i的获胜神经元是 $\mathbf { \Omega } _ { u }$ ，根据神经元的位置确定邻域神经元，邻域神经元上对应的EXA中的个体则组成nbest的备选库nbest_i。参照快速排序法，根据占优性和拥挤距离，选择排序靠前且稀疏的个体为粒子 $i$ 的nbest。相较于将目标空间划分成几部分的分解策略错误!未找到引用源。错误!未找到引用源。，此策略有以下优点：

a)SMPSO选出来的粒子在决策空间距离粒子较近，产生有 效子代的效率更高。

b)SMPSO在决策空间为粒子构建邻域，整个种群有不同的引导粒子，保持了种群的多样性。

c)SOM的结构是根据目前得到的非支配解集不断学习的，权值信息不断更改，更靠近PF，产生的解更符合问题的结构。

![](images/723184853c27060a39c0c325715af9412aa84b3ad92e0e289aae6cf0dde6aaf9.jpg)  
图4nbest 的选择

# 2.3 扰动变异策略

对于多目标粒子群算法，保留非支配解是至关重要的。因为它们是当前搜索到的最佳位置，具有一定的引导意义。但由于缺乏对待优化问题的先验知识，当种群处于收敛停滞状态时，有可能是陷入了局部最优。本文中除了使用外部存储集之外还引入了精英学习策略，在目前得到的最优位置处进行变异，有利于全局最优解的进一步寻找。

在为粒子 $x$ 选择nbest之后，进行子代更新，更新之后的粒子按照一定概率进行精英学习。

$j { = } \mathrm { r a n d } ( 1 , n ) { < } p r ;$ （204

$$
x ( j ) = n b e s t ( j ) + \mathrm { n o r m r n d } ( 0 , p r ^ { 2 } ) \times ( b _ { j } - a _ { j } )
$$

其中： $a _ { j } \mathfrak { F } \mathbb { H } b _ { j }$ 是粒子 $\mathrm { ~ x ~ }$ 第 $j ^ { \mathrm { t h } }$ 维的上下界；pr 的值随着迭代次数的增加，从0.2线性减少为0.05。在进化初期，较大的变异范围有利于算法的全局搜索，随着迭代的进行，算法需要在局部范围找到更精确的解，因此小的变异范围更适合。正态分布的概率密度如图5所示。由0可知，当pr值较大时，产生的随机值较大的概率比较大，从而粒子的变异范围较大，有利于产生较大的扰动；随着迭代的进行，pr值减小，产生的随机数在均值0附近的概率会越来越大，变异范围减小，此时的nbest已接近于真实的最优位置，小范围的变异更有利于寻找精确解。

![](images/a8d34e9463c6a046a9b8454fa3ba45f4341c4f37a7946c49433b204167ba4d3a.jpg)  
图5正态分布的概率密度图

同时，为了避免种群陷入局部最优，引入了多项式变异。ifrand() $_ { | < 1 / n }$

$$
x ( j ) = x ( j ) + \zeta _ { j } \times ( b _ { j } - a _ { j } )
$$

$$
\zeta _ { j } = \left\{ \begin{array} { l l } { [ 2 \times r n d + ( 1 - 2 \times r n d \times ( \displaystyle { \frac { b _ { j } - x ( j ) } { b _ { j } - a _ { j } } } ) ^ { e t a + 1 } ) ] ^ { \frac { 1 } { e t a + 1 } } - 1 } & { \mathrm { i f ~ } r n d < 0 . 5 } \\ { 1 - [ 2 - 2 \times r n d + ( 2 \times r n d - 1 ) ( \displaystyle { \frac { x ( j ) - b _ { j } } { b _ { j } - a _ { j } } } ) ^ { e t a + 1 } ] ^ { \frac { 1 } { e t a + 1 } } } & { \mathrm { o t h e r w i s e } } \end{array} \right.
$$

其中：rnd是在（0,1）间的随机数；eta是变异分布指数。

# 2.4 SMPSO 算法的具体步骤

在 SMPSO中，利用SOM模型为粒子构建邻域，SOM权值随着种群每迭代一次进行一次更新；训练数据只采用新加入外部存储集EXA的粒子，节约计算量且避免数据训练过度。在子代更新中加入了扰动策略，平衡了收敛与多样性。对粒子位置进行了边界处理，边界粒子速度置反可以避免粒子集中于边界位置。算法2给出了SMPSO算法的具体步骤。

# 2.5算法2 SMPSO 的具体步骤

输入：种群大小 $N P$ ，PSO参数 $w , c _ { 1 } , c _ { 2 }$

输出：外部存储集EXA。

a)初始化种群和SOM网络权值。

初始化种群NP个粒子 $\mathbf { P O P } = \{ x ^ { 1 } , x ^ { 2 } , . . . , x ^ { N P } \}$ ,EXA=POP;SOM的训练数据 $\mathrm { T S } { \mathrm { = } } \mathrm { P O P }$ ， $\{ w ^ { 1 } , w ^ { 2 } , . . . , w ^ { N P } \} { = } \mathbf { P O P }$ ，学习率 $\eta _ { \mathrm { 0 } }$ ,学习半径$\sigma _ { 0 }$ 。

b)根据神经元之间的距离 $\left\| \boldsymbol { \mathsf { Z } } ^ { u } - \boldsymbol { \mathsf { z } } ^ { u ^ { * } } \right\| _ { 2 }$ ,计算神经元 $\mathrm { ~  ~ u ~ }$ 的邻域神经元集合 ${ \boldsymbol { \mathrm { I } } } ^ { u }$ ， $\textstyle \mathrm { I } _ { k } ^ { u }$ 是距离神经元 $\mathrm { ~  ~ u ~ }$ 第 $k ^ { \mathrm { { t h } } }$ 近的神经元。

c)循环。

(a)SOM权值更新：根据TS及式（9）（10)更新网络权值。

(b)参考算法1，为粒子选择nbest备选库，按照NSGA-II

的快速排序法对备选库的粒子进行排序，选择排序靠前且稀疏的粒子作为nbest。

(c)子代更新。

在 SMPSO中，粒子群更新公式为

$$
\nu = w \times \nu + r a n d \times c _ { 1 } \times ( p b e s t - x ) + r a n d \times c _ { 2 } \times ( n b e s t - x )
$$

其中： $w = w _ { \mathrm { m a x } } - ( w _ { \mathrm { m a x } } - w _ { \mathrm { m i n } } ) ^ { * } \frac { t } { M A X g e n } ~ \mathrm { c }$

速度边界处理：超过边界的值赋予边界值。

$$
x = x + \nu
$$

之后，按照一定概率执行精英学习策略，参考式（11)。位置边界处理：超过边界的值赋予边界值且速度置反。

进行多项式变异操作，参考式（12）和（13）。

(d)更新EXA和TS。

外部存储集EXA的更新策略，根据占优性和拥挤距离排序，保留排序靠前且稀疏的粒子；

训练数据TS=unique(EXA,TS)，即只把新产生的加入EXA的粒子作为训练数据。

d)结束，否则返回步骤c)。

# 3 仿真实验与分析

# 3.1实验设置

3.1.1测试函数

本文采用文献错误！未找到引用源。中的GLT1-GLT6和文献错误！未找到引用源。中DLTZ2、DLTZ4和DLTZ5为测试函数。0列出了测试函数的决策变量和Pareto前沿的信息。

表1用于算法性能比较的多目标优化测试问题  

<html><body><table><tr><td>测试问题</td><td>目标维数</td><td>变量维数</td><td>变量范围</td><td>Pareto 前沿特点</td></tr><tr><td>GLT1</td><td>2</td><td>10</td><td>[0,1]×[-1,1]"-1</td><td>线性 不连续</td></tr><tr><td>GLT2</td><td>2</td><td>10</td><td>[0,1]×[-1,1]"-1</td><td>凸PF 连续</td></tr><tr><td>GLT3</td><td>2</td><td>10</td><td>[0,1]×[-1,1]"-1</td><td>凸PF 连续</td></tr><tr><td>GLT4</td><td>2</td><td>10</td><td>[0,1]×[-1,1]"-1</td><td>凸 PF 不连续</td></tr><tr><td>GLT5</td><td>3</td><td>10</td><td>[0,1]² ×[-1,1]"-2</td><td>凸PF 连续</td></tr><tr><td>GLT6</td><td>3</td><td>10</td><td>[0,1]² ×[-1,1]"-2</td><td>凸 PF 不连续</td></tr><tr><td>DTLZ2</td><td>3</td><td>12</td><td>[0,1]"</td><td>凹形，连续</td></tr><tr><td>DTLZ4</td><td>3</td><td>12</td><td>[0,1]"</td><td>凹形 非均匀</td></tr><tr><td>DTLZ5</td><td>3</td><td>12</td><td>[0,1]"</td><td>线型 连续</td></tr></table></body></html>

# 3.1.2比较算法

为了比较算法(SMPSO)的性能,选取三种代表性的多目标优化的对比算法。这些算法中有 NSGAII 错误!未找到引用源。、2LBMOPSO错误！未找到引用源。、pCCSAMOPSO错误！未找到引用源。、IM-MOEA错误!未找到引用源·和 MOEA/IGD-NS 错误!未找到引用源。各算法的实验参数都按照对应参考文献设置。

# 3.1.3实验参数

实验中GLT1-GLT4是2目标的多目标问题，种群大小设为100，SOM的网络结构设置为一维（ $1 \times 1 0 0$ )，外部存储容量均为100，测试函数的最大评价次数为50000。GLT5-GLT6和DTLZ系列是3目标的多目标问题，种群大小设为150，SOM的网络结构设置为二维（ $1 5 \times 1 0$ )，外部存储容量均为150，测试函数的最大评价次数为70000。每种算法在所有测试函数上均独立运行25 次。

# 3.1.4性能指标

为了评估算法获得的近似PF的收敛性和均匀性，本文采用反转世代距离(inverted generational distance，IGD)和超体积值(hyper-volume，HV)作为性能评估指标。令 $\mathbf { P }$ 为真实Pareto最优解集， $\mathbf { p } ^ { * }$ 是得到的Pareto 最优解集，则 $I G D$ 的计算如下：

$$
I G D ( \mathbf { P } ^ { * } , \mathbf { P } ) = \frac { \sum _ { x } ^ { * } \in \mathbf { P } ^ { * } d ( x ^ { * } , \mathbf { P } ) } { \left| \mathbf { P } ^ { * } \right| }
$$

其中： $d ( x ^ { * } , \mathbf { P } )$ 是 $x ^ { * }$ 到 $\mathbf { P }$ 中任何一个点的最小距离； $\left| \mathbf { P } ^ { * } \right|$ 是 $\mathbf { p } ^ { * }$ 的基数。

$H V$ 的计算方式为

$$
H V ( \mathbf { P } , r ) = V O L ( \bigcup _ { x \in \mathbf { P } } [ f _ { 1 } ( x ) , r _ { 1 } ] \times . . . [ f _ { m } ( x ) , r _ { m } ] )
$$

其中： $\pmb { r } = ( r _ { 1 } , . . . , r _ { m } )$ 是目标空间里被任何帕累托前沿占优的参考点； $V O L ( . )$ 是勒贝格测度。GLT1、GLT3 的参考点 $\pmb { r } = ( 2 , 2 )$ ，GLT2的 $\pmb { r } = ( 2 , 1 1 )$ ,GLT4的参考点 $\pmb { r } = ( 2 , 3 )$ ,GLT5-GLT6、DLZ2和 DLZ4-DLZ5 的参考点 $\pmb { r } = ( 2 , 2 , 2 )$ □

实验中 $I G D$ 和 $H V$ 的值都用来衡量种群的收敛性和分布性， $I G D$ 值越小（ $H V$ 的值越大)，则得到的PF 越好。得到的IGD值很小且 $H V$ 值很大，则得到PF 非常接近真实的PF，且能完全覆盖真正的PF。

# 3.2 实验结果及分析

SMPSO算法中需要更新拓扑结构的权值，且在一定概率下进行变异。为了比较各种算法的时间复杂度，将6个比较算法在9个多目标测试问题上独立运行25次的耗时均值列于0内。可以看出SMPSO算法的时间复杂度比NSGAII和IM-MOEA的大，但保持在同一数量级，在3目标的测试问题上耗时比2LBMOPSO，pCcsAMOPSO 和MOEA/IGD-NS相对较少。

0和0列出了6种比较算法在9个多目标测试问题上的$I G D$ 和HV性能指标值。其中，平均值(mean)和标准差值(std)是同一算法在同一测试问题上独立运行25次的统计结果；同时，采用粗体字和灰色背景表示所有对比算法在每一个测试问题中的最小IGD值和最大HV值。每种算法对同一个问题的排名及综合排名列在表内。同时用秩和检验， $5 \%$ 的显著性水平比较各算法与SMPSO的显著性差异。分别用“†”、“”和 ${ \bf \Omega } ^ { 6 6 } \approx { \bf \Omega } ^ { 9 }$ 表示算法SMPSO比对比算法较好，较差和没有明显差异的情况。

表2各种算法在每个测试问题上的平均耗时/s  

<html><body><table><tr><td></td><td>2LBMOPSO</td><td>NSGAII</td><td>pccsAMOPSO</td><td>IM-MOEA</td><td>MOEA/IGD-NS</td><td>SMPSO</td></tr><tr><td>GLT1</td><td>62.14</td><td>12.38</td><td>82.72</td><td>18.49</td><td>5.49</td><td>46.3</td></tr><tr><td>GLT2</td><td>63.75</td><td>10.86</td><td>98.07</td><td>19.57</td><td>5.94</td><td>45.35</td></tr><tr><td>GLT3</td><td>68.88</td><td>9.97</td><td>143.67</td><td>24.22</td><td>24.38</td><td>45.36</td></tr><tr><td>GLT4</td><td>72.42</td><td>12.03</td><td>84.86</td><td>20.41</td><td>10.78</td><td>50.41</td></tr><tr><td>GLT5</td><td>138.1</td><td>19.91</td><td>138.20</td><td>25.68</td><td>183.45</td><td>76.11</td></tr><tr><td>GLT6</td><td>140.84</td><td>20.99</td><td>602.35</td><td>23.66</td><td>176.82</td><td>74.56</td></tr><tr><td>DTLZ2</td><td>134.24</td><td>20.16</td><td>635.679</td><td>20.12</td><td>426.54</td><td>76.41</td></tr><tr><td>DTLZ4</td><td>131.33</td><td>20.7</td><td>543.43</td><td>20.45</td><td>372.61</td><td>79.87</td></tr><tr><td>DTLZ5</td><td>130.42</td><td>20.38</td><td>605.28</td><td>22.92</td><td>390.28</td><td>78.56</td></tr></table></body></html>

表3测试函数性能度量IGD 的均值(标准差)  

<html><body><table><tr><td>函数</td><td></td><td>2LBMOPSO</td><td>NSGAII</td><td>pccsAMOPSO</td><td>IM-MOEA</td><td>MOEA/IGD-NS</td><td>SMPSO</td></tr><tr><td rowspan="2">GLT1</td><td>mean</td><td>1.17E-01*[6]</td><td>4.35E-02*[3]</td><td>8.12E-02*[4]</td><td>3.61E-02*[2]</td><td>9.88E-02[5]</td><td>2.38E-02[1]</td></tr><tr><td>std</td><td>4.40E-02</td><td>3.07E-02</td><td>2.41E-02</td><td>1.95E-02</td><td>5.22E-03</td><td>2.25E-02</td></tr><tr><td rowspan="2">GLT2</td><td>mean</td><td>1.12E-01*[3]</td><td>4.28E-02[2]</td><td>7.12E-01[5]</td><td>6.59E-01*[4]</td><td>1.95E+00*[6]</td><td>3.82E-02[1]</td></tr><tr><td>std</td><td>2.20E-01</td><td>2.89E-03</td><td>4.67E-01</td><td>2.22E-01</td><td>1.60E-01</td><td>1.88E-03</td></tr><tr><td rowspan="2">GLT3</td><td>mean</td><td>6.64E-02*[5]</td><td>2.81E-02[2]</td><td>1.12E-01*[6]</td><td>4.17E-02*[3]</td><td>6.53E-02*[4]</td><td>9.32E-03[1]</td></tr><tr><td>std</td><td>2.17E-02</td><td>1.46E-02</td><td>4.46E-02</td><td>8.31E-03</td><td>5.53E-03</td><td>5.32E-03</td></tr><tr><td rowspan="2">GLT4</td><td>mean</td><td>1.32E-01*[4]</td><td>1.16E-01*[3]</td><td>2.27E-01*[5]</td><td>6.14E-02*[2]</td><td>2.62E-01*[6]</td><td>4.17E-02[1]</td></tr><tr><td>std</td><td>7.04E-02</td><td>7.80E-02</td><td>9.81E-02</td><td>4.16E-02</td><td>1.50E-02</td><td>4.90E-02</td></tr><tr><td rowspan="2">GLT5</td><td>mean</td><td>5.14E-02*[4]</td><td>6.51E-02[5]</td><td>8.88E-02*[6]</td><td>4.86E-02[3]</td><td>3.43E-02 [1]</td><td>4.77E-02[2]</td></tr><tr><td>std</td><td>2.70E-03</td><td>4.57E-03</td><td>1.84E-02</td><td>2.96E-03</td><td>1.25E-03</td><td>2.57E-03</td></tr></table></body></html>

表4测试函数性能度量 $H V$ 的均值(标准差)  

<html><body><table><tr><td rowspan="2">GLT6</td><td>mean</td><td>4.99E-02*[4]</td><td>5.83E-02*[5]</td><td>7.34E-02*[6]</td><td>3.18E-02[2]</td><td>2.71E-02[1]</td><td>4.12E-02[3]</td></tr><tr><td>std</td><td>1.77E-03</td><td>5.37E-03</td><td>3.59E-02</td><td>1.26E-03</td><td>1.56E-03</td><td>3.34E-03</td></tr><tr><td rowspan="2">DTLZ2</td><td>mean</td><td>6.15E-02*[4]</td><td>1.00E-01*[6]</td><td>5.27E-02 [2]</td><td>7.78E-02*[5]</td><td>4.29E-02 [1]</td><td>5.51E-02[3]</td></tr><tr><td>std</td><td>2.46E-03</td><td>7.48E-03</td><td>1.69E-03</td><td>3.50E-03</td><td>3.65E-04</td><td>2.04E-03</td></tr><tr><td rowspan="2">DTLZ4</td><td>mean</td><td>6.28E-02*[2]</td><td>3.15E-01 [6]</td><td>1.05E-01*[4]</td><td>6.73E-02[3]</td><td>2.12E-01*[5]</td><td>5.40E-02[1]</td></tr><tr><td>std</td><td>1.64E-03</td><td>7.99E-02</td><td>1.16E-01</td><td>2.38E-03</td><td>3.02E-01</td><td>2.05E-03</td></tr><tr><td rowspan="2">DTLZ5</td><td>mean</td><td>4.36E-03*[5]</td><td>3.69E-03*[4]</td><td>3.37E-03 [2]</td><td>1.57E-02[6]</td><td>2.80E-03 [1]</td><td>3.68E-03[3]</td></tr><tr><td>std</td><td>2.68E-04</td><td>5.14E-04</td><td>2.16E-04</td><td>1.96E-03</td><td>2.19E-04</td><td>2.41E-04</td></tr><tr><td>Rank</td><td></td><td>4.111</td><td>4.000</td><td>4.444</td><td>3.333</td><td>3.333</td><td>1.778</td></tr><tr><td>//</td><td></td><td>9/0/0</td><td>7/0/2</td><td>7/0/2</td><td>6/0/3</td><td>5/3/1</td><td></td></tr></table></body></html>

<html><body><table><tr><td>函数</td><td></td><td>2LBMOPSO</td><td>NSGAII</td><td>pccsAMOPSO</td><td>IM-MOEA</td><td>MOEA/IGD-NS</td><td>SMPSO</td></tr><tr><td rowspan="2">GLT1</td><td>mean</td><td>～～[6]</td><td>3.26E+00*[3]</td><td>3.17E+00*[4]</td><td>3.28E+00[2]</td><td>3.17E+00*[5]</td><td>3.31E+00[1]</td></tr><tr><td>std</td><td></td><td>6.84E-02</td><td>5.38E-02</td><td>3.44E-02</td><td>2.42E-02</td><td>5.30E-02</td></tr><tr><td rowspan="2">GLT2</td><td>mean</td><td>1.84E+01*[4]</td><td>1.97E+01*[2]</td><td>1.83E+01*[5]</td><td>1.90E+01*[3]</td><td>1.64E+01*[6]</td><td>1.98E+01[1]</td></tr><tr><td>std</td><td>1.11E-02</td><td>7.03E-03</td><td>6.47E-01</td><td>2.34E-01</td><td>5.51E-01</td><td>1.01E-02</td></tr><tr><td rowspan="2">GLT3</td><td>mean</td><td>3.93E+00*[5]</td><td>3.94E+00*[4]</td><td>3.91E+00*[6]</td><td>3.94E+00*[3]</td><td>3.94E+00*[2]</td><td>3.95E+00[1]</td></tr><tr><td>std</td><td>4.03E-03</td><td>2.75E-03</td><td>3.70E-02</td><td>1.74E-03</td><td>1.13E-03</td><td>1.06E-03</td></tr><tr><td rowspan="2">GLT4</td><td>mean</td><td>4.86E+00[2]</td><td>4.85E+00[3]</td><td>4.40E+00[6]</td><td>4.81E+00[4]</td><td>4.42E+00[5]</td><td>4.97E+00[1]</td></tr><tr><td>std</td><td>1.27E-01</td><td>1.83E-01</td><td>9.14E-01</td><td>1.35E-01</td><td>2.07E-02</td><td>2.59E-02</td></tr><tr><td rowspan="2">GLT5</td><td>mean</td><td>3.88E+00*[3]</td><td>3.87E+00*[4]</td><td>3.85E+00*[5]</td><td>3.81E+00*[6]</td><td>3.88E+00[2]</td><td>3.90E+00[1]</td></tr><tr><td>std</td><td>1.31E-02</td><td>2.35E-02</td><td>2.75E-02</td><td>2.03E-02</td><td>1.56E-02</td><td>1.56E-02</td></tr><tr><td rowspan="2">GLT6</td><td>mean</td><td>3.85E+00[4]</td><td>3.84E+00[6]</td><td>3.86E+00[2]</td><td>3.85E+00[5]</td><td>3.89E+00[1]</td><td>3.86E+00[3]</td></tr><tr><td>std</td><td>1.08E-02</td><td>1.42E-02</td><td>3.32E-02</td><td>2.34E-02</td><td>1.27E-02</td><td>1.37E-02</td></tr><tr><td rowspan="2">DTLZ2</td><td>mean</td><td>3.48E+00*[4]</td><td>3.47E+00*[5]</td><td>3.49E+00*[2]</td><td>3.48E+00*[3]</td><td>3.46E+00*[6]</td><td>3.49E+00[1]</td></tr><tr><td>std</td><td>2.46E-03</td><td>7.48E-03</td><td>1.69E-03</td><td>4.25E-02</td><td>2.94E-02</td><td>3.59E-03</td></tr><tr><td rowspan="2">DTLZ4</td><td>mean</td><td>3.48E+00[5]</td><td>3.57E+00[1]</td><td>3.55E+00 [2]</td><td>3.52E+00[3]</td><td>3.47E+00*[6]</td><td>3.50E+00[4]</td></tr><tr><td>std</td><td>1.64E-03</td><td>7.99E-02</td><td>1.16E-01</td><td>2.63E-02</td><td>2.08E-01</td><td>2.05E-03</td></tr><tr><td rowspan="2">DTLZ5</td><td>mean</td><td>2.84E+00*[1]</td><td>2.84E+00[5]</td><td>2.84E+00[2]</td><td>2.84E+00[4]</td><td>2.83E+00[6]</td><td>2.84E+00[3]</td></tr><tr><td>std</td><td>2.68E-04</td><td>5.14E-04</td><td>2.16E-04</td><td>2.30E-02</td><td>6.19E-03</td><td>2.16E-04</td></tr><tr><td>Rank</td><td></td><td>3.778</td><td>3.667</td><td>3.778</td><td>3.667</td><td>4.333</td><td>1.778</td></tr><tr><td>//≈</td><td></td><td>8/0/1</td><td>7/1/1</td><td>5/1/3</td><td>7/1/1</td><td>7/1/1</td><td></td></tr></table></body></html>

从0中可以看出，SMPSO算法对大多测试问题都有很好的性能度量。对于测试问题GLT1-GLT4和DTLZ4，SMPSO算法得到的IGD均值最小。对于测试问题GLT5，SMPSO的IGD值仅大于MOEA/IGD-NS 算法,对于GLT6、DLTZ2和DLTZ5,SMPSO算法的IGD指标排名第三。表中的Rank值是算法对所有测试问题的平均排名，可以看出SMPSO的排名最高。且秩和检验的结果表明，SMPSO在大多测试问题上明显优于其他对比算法。

0 中“～～”表示2LBMOPSO 算法对测试问题GLT1的结果较差，性能指标HV出现负值，不作统计。SMPSO 算法对于GLT1-GLT5和DTLZ2，HV值均为最大。对于GLT6，DLTZ5测试问题， $H V$ 均值排名第三。当然，SMPSO不可能在所有测试问题上效果都比较好，如在DTLZ4上效果较差。综合排名和显著性水平显示，SMPSO对大部分测试问题都有较好的多样性。

为了进一步显示各种算法求得最优解集的收敛和多样性的情况，以测试问题GLT1、GLT3、GLT6、DTLZ4-DTLZ5为例，将测试函数运行25次结果，按IGD值排名中间的一次运行结果显示如0所示。

![](images/9029c442cbac0bce7ec74334d75ad0e32c084523efc9e72349e0da2bb08076a0.jpg)

![](images/6b419d96ccdcc600d44731a63e33a3bef31d0afdb966469ca0d92b3fb1b9c5aa.jpg)

(c)GLT6的PF对比

从0中可以看出，无论是2目标还是3目标问题，SMPSO得到的PF均可以较好地覆盖真正的PF，相对于对比算法，SMPSO能较好的处理PF不连续的情况，如GLT1和GLT6，在 SMPSO 中的SOM网络结构可以较好地发现问题的结构信息，且网络结构的整体性有利于种群的全局搜索，因此找到的PF 没有缺失。GLT3虽然PF是连续的，但是测试函数的复杂，导致找到的PF能完全覆盖真正的帕累托前沿有一定的难度。DTLZ4的问题上，SMPSO得到的PF虽然能较全面地覆盖真正的PF，但图中显示分布的均匀性略差。DTLZ5 测试问题比较简单，大部分算法得到的帕累托前沿能够靠近真正的PF。

为了验证用SOM构造邻域关系的合理性，0将以GLT2问题为例，列出在进化过程中神经元上对应的粒子及粒子的nbest备选库在决策空间和目标空间的分布。

从图中可以看出，在进化的过程中，为粒子选择的nbest不论在PF或是PS空间，都是外部存储集EXA中距离粒子个体比较近的，有利于局部搜索，增加产生高质量粒子的可能性。粒子a和b对应的神经元在拓扑结构中距离较近，它们映射的粒子距离也比较近。同理，c粒子对应的神经元在拓扑结构上，距离较远，则a、b距离c粒子及其邻域较远。这也是SOM的特性之一，即相似的个体聚在一起。每进化一代之后，权值学习一次，因此权值的调整也是慢慢累积的。图(b)中粒子c在PF空间分布距离邻域较远，是因为SOM的映射关系是在PS空间建立的，所以反映在PF空间会有所偏差。

![](images/9a59a772b823ffd91c507e0c2bdc869d33355dd7b30fa796bfefdcd2ee9a3086.jpg)  
图7不同粒子的邻域分布

，是当前外部存储集EXA;

★是粒子a，第40号神经元对应的粒子，☆是粒子a的nbest备选；是粒子b，第45号神经元对应的粒子， $\bigcirc$ 是粒子 $\mathbf { b }$ 的nbest备选；是粒子c，第80号神经元对应的粒子，是粒子c的nbest备选。

SMPSO算法中精英变异策略中的参数 $p r$ 初始值的选取，在参考了数学模型的概率分布之外，另外进行了实验的验证。如0所示，设定 $p r$ 最小值为 $0 . 0 5 , p r$ 初始值分别设为0.1、02、0.3、0.4和0.5，折线图显示没有某一个 $p r$ 初始值可以使所有测试问题的 $I G D$ 值均为最小，但是 $p r$ 初始值设为0.2时可以使大多测试问题的 $I G D$ 值较小，且变异概率较小可以降低计算复杂度。因此 $p r$ 初始值设为0.2， $p r$ 线性减小到最小值为0.05而不是0，是为了在算法的后期仍能产生一定的扰动。

![](images/8b8d808688e62161312de6bf4248ac61b66d327a88d6a8a0b4cef2844965aa13.jpg)  
图8不同 $p r$ 初始值对各个测试问题 $I G D$ 值的影响

SMPSO中根据多目标优化问题的规则性，2目标问题，采用一维（ $1 \times 1 0 0$ )SOM，3目标问题，采用二维（ $1 5 \times 1 0$ )SOM。为了验证SOM拓扑结构对算法性能指标 $I G D$ 和 $H V$ 的影响，将SOM的拓扑结构作出如下改变：2目标问题改用二维( $1 0 \times 1 0$ ）SOM，3目标问题改用一维（ $1 \times 1 5 0$ ）SOM，将算法独立运行25次的平均值结果显示如0所示。

![](images/f763f2077706d5d73e4903e5d652b43f5d2c76d312ff25055f5d0dfb9eb0262c.jpg)  
(b)第400代时粒子的分布  
图9SOM拓扑结构对IGD和 $H V$ 的影响

从图9（a）中可以看出，对于2目标的测试问题GLT1、GLT3，IGD值在二维SOM的情况下较小，GLT2、GLT4,在一维SOM的情况下较小，3目标的测试问题在二维SOM时IGD值较小；从（b）中可以看出，SOM拓扑结构的改变对2目标问题的HV值影响不大，3目标问题的HV值在二维 SOM的情况下略高。因此，总的来说，2目标问题对一维或二维拓扑结构的SOM无明显偏好，3目标问题较偏好二维拓扑结构的SOM。

# 4 结束语

通过结合多目标问题的规则性和自组织映射网络的映射关系不变性，本文提出了一种新算法。该算法为多目标粒子群算法构建了一种新的邻域关系，为每个粒子选取了更合适的引导粒子，同时加入了精英学习机制。算法兼顾了收敛性和多样性，对大多的多目标问题都能得到分布均匀且靠近真正PF的解集。在后续研究中，将该算法应用到高维多目标问题上，并进一步改进算法的性能。

# 参考文献：

[1]Deb K.A fast elitist multi-objective genetic algorithm: NSGA-II[J].IEEE Trans on Evolutionary Computation,20oo,6 (2):182-197.   
[2]林震，侯杏娜，韦晓虎．基于动态多策略差分进化模型的 MOEA//D 算 法[J].计算机应用研究,2017,34(9):2624-2628.(Lin Zhen,Hou Xingna, Wei Xiaohu. MOEA//D based on dynamic multi-strategy differential evolution model [J].Application Research of Computers,2017,34 (9): 2624-2628. )   
[3]Coello C A C,Pulido G T,Lechuga M S.Handling multiple objectives with particle swarm optimization [J]. IEEE Trans on Evolutionary Computation, 2004,8 (3): 256-279.   
[4]Kennedy J,Eberhart R.Particle swarm optimization [C]// Proc of IEEE International Conference on Neural Networks.2002 (4):1942-1948.   
[5]韩敏，张丽君．基于多样性检测的双子群多目标粒子群算法[J].控制 与决策,2017,32 (12): 2268-2272.(Han Min,Zhang Lijun.Bi-group multiobjective particle swarm optimization algorithm based on diversity metric [J]. Control and Decision,2017,32 (12): 2268-2272. )   
[6] 肖闪丽，王宇嘉，聂善坤.动态邻居维度学习的多目标粒子群算法[J]. 计算机工程与应用,2017,53 (20):31-38.(Xiao Shanli,Wang Yujia,Nie Shankun.Multi-objective particle swarm optimization based on dynamic neighborhood for dimensional learning [J]. Computer Engineering and Applications,2017,53 (20): 31-38.)   
[7]夏星宇，高浩，王创业．均衡策略粒子群算法在图像分割中的应用[J]. 郑州大学学报：工学版,2018,39(1):59-66.(Xia Xingyu,Gao Hao,Wang Chuangye. Quantification calculation and modeling simulationof distribution network losses considering harmonic factor [J].Journal of Zhengzhou University: Engineering Science,2018,39 (1): 59-66.)   
[8]韩敏，何泳．基于高斯混沌变异和精英学习的自适应多目标粒子群算 法[J].控制与决策，2016,31(8):1372-1378.(Han Min,He Yong. Adaptive multi-objective particle swarm optimization with Gaussian chaotic mutation and elite learning [J]. Control and Decision,2016,31(8): 1372- 1378.)   
[9]Schutze O,Mostaghim S,Dellnitz M,et al.Covering pareto sets by multilevel evolutionary subdivision techniques[C/ Procof Evolutionary Multi-Criterion Optimization, Second International Conference.2003:118 132.   
[10] Zhang Hu, Zhou Aimin,Song Shenmin,et al. A self-organizing multiobjectiveevolutionaryalgorithm [J].IEEE Transon Evolutionary Computation,2016,20 (5): 792-806.   
[11]时光，刘健辰，陈忠华，等．基于DE-EDA多目标优化的受电弓模糊控 制[J].计算机工程与应用，2016,52(1):229-232.(ShiGuang,Liu Jianchen, Chen Zhonghua,et al. Control of pantograph based on DE-EDA multi-objective optimization [J]. Computer Engineering and Applications, 2016,52 (1): 229-232.)   
[12] Wang Handing, Zhang Qingfu,JiaoLicheng,et al. Regularity model for noisy multi-objective optimization [J]. IEEE Trans on Cybernetics,2016,46 (9): 1997-2009.   
[13]毛晓波，张群，梁静，等．基于 PSO-RBF 神经网络的雾霾车牌识别算 法研究[J].郑州大学学报：工学版,2017,38(4):46-50.(Mao Xiaobo, Zhang Qun,Liang Jing,et al. The haze plate recognition system based on PSO-RBFneural network[J].Journal of Zhengzhou University: Engineering Science,2017,38 (4): 46-50.）   
[14] Wang Hu, Yen G G. Adaptive multi-objective particle swarm optimization based on parallel cellcoordinate system [J]. IEEE Trans on Evolutionary Computation,2015,19 (1): 1-18.   
[15] Zhao Shizheng,Suganthan PN. Two-lbests based multi-objective particle swarm optimizer[J]. Engineering Optimization,2011,43(1):1-17.   
[16] Gu Fangqing,Liu Hailin,Tan K C.Amultiobjective evolutionary algorithm using dynamic weight design method[J]. International Journal of Innovative Computing Information & Control,2012,8(5): 3677-3688.   
[17] Deb K,Thiele L,Laumanns M,et al. Scalable test problems for evolutionary multiobjectiveoptimization[M]//EvolutionaryMultiobjective Optimization. 2005: 105-145   
[18] ChengRan,Jin Yaochu,NarukawaK,etal.AMultiobjective evolutionary algorithm using Gaussian process-based inverse modeling [J]. IEEE Trans on Evolutionary Computation,2015,19 (6): 838-856.   
[19] Tian Ye, Zhang Xingyi, Cheng Ran,et al. A multi-objective evolutionary algorithm based on an enhanced inverted generational distance metric [C]// Proc of IEEE Congress on Evolutionary Computation.2016: 5222-5229.