# 折扣{0-1}背包问题粒子群算法的贪婪修复策略探究

代祖华，周斌，龙玉晶，王宗泉(西北师范大学 计算机科学与工程学院，兰州 730070)

摘要：群智能启发式算法求解折扣{0-1}背包问题 $\mathrm { ( D \{ 0 - 1 \} K P ) }$ 时，为提升求解效率和求解质量，需采用某种修复与优化策略将非正常编码个体转换为符合解约束条件的编码个体。在引入项集价值密度概念基础上，以粒子群算法(PSO)为例，提出一组基于项集的贪婪修复与优化方法(Group Greedy Repair and Optimization Algorithm，GGROA),并进一步构造 PSO-GGRDKP 算法(PSO based GGROA for solving ${ \mathrm { D } } \{ 0 { \mathrm { - } } 1 \} { \mathrm { K P } } )$ 以探究GGROA方法的可行性和性能。PSO-NGROADKP(PSO based NGROA for solving D{0-1}KP)和 PSO-GRDKP(PSO based GROA for solving D{0-1}KP)是基于项贪心修复与优化方法的粒子群算法。在D{0-1}KP 标准数据集的实验结果表明：与 PSO-NGROADKP 和PSO-GRDKP相比，PSO-GGRDKP算法的解误差率略高，但算法时间性能分别提升 $1 3 . 8 \%$ 、 $12 . 9 \%$ 。

关键词：折扣{0-1}背包问题；启发式算法；粒子群算法；非正常编码个体；贪心修复与优化； $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 数据集 中图分类号：TP391 doi:10.19734/j.issn.1001-3695.2021.12.0701

Greedy repair strategy of particle swarm optimization for discounted {0-1} knapsack problem

Dai Zuhua, Zhou Bin, Long Yujing, Wang Zongquan (CollgeofComputer Science&Engineering,Northwest Normal University Gansu 730o70,China)

Abstract: Swarm intelligence heuristicalgorithmisused to solvediscounted {0-1} knapsack problem(D{0-1}KP).Inorder to improve the solution efficiency and quality,a repair and optimization strategy is needed to convert abnormal coding individuals into coding individuals that meet the solution constraints.On the basis ofintroducing theconcept of group value density,taking particle swarm optimization algorithm (SO)asan example,a set of greedyrepair and optimization methods based on group (GGROA) is proposed,and the PSO based GGROA for solving D{0-1}KP algorithm (PSO-GGRDKP) is further constructed to explore the feasibilityand performance of GGROA.PSO-NGROADKP and PSO-GRDKP are PSO algorithms basedon item greedyrepair and optimization method.The experimentalresults onD{0-1}KP standard data set show that compared with PSO-NGROADKP and PSO-GRDKP,PSO-GGRDKP has slightly higher error rate,butthe time performance of the algorithm is improved by $1 3 . 8 \%$ and $12 . 9 \%$ respectively.

Key words: discount {0-1}knapsack problem; heuristic algorithm; particle swamoptimizationalgorithm; non-normal coding individual; greedy repair and optimization; ${ \mathrm { D } } \{ 0 { - } 1 \} { \mathrm { K P } }$ dataset

# 0 引言

{0-1}背包问题({0-1}KnapsackProblem,{0-1}KP)是计算机科学一个重要的NPComplete问题，也是一类经典组合优化问题，在商业、经济、管理、安全等领域有着广泛应用背景。{0-1}KP自被提出后的几十年里被反复地研究，衍生出精确算法、非精确算法两大类算法。精确算法有动态规划、回溯法和分支限界法等；非精确算法主要有随机算法、近似算法、生物算法等。2005年，由GUDER首次提出的折扣{01}背包问题(Discount {0-1} Knap-sack Problem,D{0-1} KP)[1,2]是{0-1}背包问题的拓展形式，作为刻画折扣销售、捆绑销售等商业活动现象的经典数学模型，是商家设计商业营销方案、消费者购买商品决策的科学计算依据。

D{0-1}KP实例由一组项集(item_group)组成，每个项集有3项物品(项，item)可供背包装入选择，定义1给出了 ${ \mathrm { D } } \{ 0 { \mathrm { - 1 } } \} { \mathrm { K P } }$ 第一数学模型。

定义1 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 第一数学模型[3]：给定 $n$ 个项集和载重为 $c$ 的背包，每个项集 $i ( i = 0 , 1 , \cdots , n - 1 )$ 由3个项(item)组成，编号记作 $3 i , 3 i + 1 , 3 i + 2 ,$ 项对应重量系数记作 $w _ { 3 i } , w _ { 3 i + 1 } , w _ { 3 i + 2 } .$ 各项对应价值系数记作 $p _ { 3 i } , p _ { 3 i + 1 } , p _ { 3 i + 2 }$ ，其中 $p _ { 3 i + 2 } = p _ { 3 i } + p _ { 3 i + 1 } , w _ { 3 i + 2 } < w _ { 3 i } + w _ { 3 i + 1 } ,$ $w _ { 3 i } < w _ { 3 i + 1 } < w _ { 3 i + 2 } , w _ { 3 i + 2 } \leq C ,$ ${ \sum } _ { i = 0 } ^ { n - 1 } w _ { 3 i + 2 } > C , p _ { j } , w _ { j } ( 0 \leq j \leq 3 n - 1 ) , C$ 都是正整数，项集i的各项价值密度记作 $e _ { 3 i } , e _ { 3 i + 1 } , e _ { 3 i + 2 } = \left. p _ { 3 i } \right/ \sum _ { W _ { 3 i } } , \left. p _ { 3 i + 1 } \right/ w _ { 3 i + 1 } , \left. p _ { 3 i + 2 } \right/ w _ { 3 i + 2 }$ ，每个项集至多有一项被选择装入背包。在不超过背包载重量 $c$ 的条件下,从给定项集选择满足装入背包要求的项，使得装入背包所有项的价值系数之和达到最大。

D{0-1}KP是一个特殊整数规划问题，定义决策变量$x _ { j } = 1 ( 0 \leq j \leq 3 n - 1 )$ 表示项 $j$ 装入背包， $x _ { j } = 0$ 表示项 $j$ 未装入背包，对于决策向量 $( x _ { 0 } , x _ { 1 } , \cdots , x _ { 3 n - 1 } )$ ，D{0-1}KP 的整数规划模型为

$$
\operatorname* { m a x } { f ( x ) } = \operatorname* { m a x } \sum _ { i = 0 } ^ { n - 1 } ( x _ { 3 i } p _ { 3 i } + x _ { 3 i + 1 } p _ { 3 i + 1 } + x _ { 3 i + 2 } p _ { 3 i + 2 } )
$$

其中：

$$
x _ { 3 i } + x _ { 3 i + 1 } + x _ { 3 i + 2 } \leq 1 , x _ { 3 i } , x _ { 3 i + 1 } , x _ { 3 i + 2 } \in \{ 0 , 1 \}
$$

$$
\sum _ { i = 0 } ^ { n - 1 } ( x _ { 3 i } w _ { 3 i } + x _ { 3 i + 1 } w _ { 3 i + 1 } + x _ { 3 i + 2 } w _ { 3 i + 2 } ) \leq C
$$

$\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 的项集有4种选择状态，如果背包容量和项的价值系数取值范围很大，则不选择某个项集的约束条件较难确定，这意味着 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 的算法难度要大于 $\{ 0 \mathrm { - } 1 \} \mathrm { K P } ^ { [ 4 ] }$ 。以{01}KP 研究成果为基础，学者们进一步研究了 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 的各类算法。其中基础动态规划算法[5](BasicDynamic Programming,BDP)是处理小规模数据的精确解算法。2016 年贺毅朝等人[4]以“所选择项的价值系数之和使总重量最小”原则构造动态规划目标函数，提出一种新动态规划算法(NewExactalgorithmforD{0-1}KP,NE-DKP)，当背包容量大于所有的项集第三项价值累加和时，NE-DKP 算法性能好于BDP算法。动态规划算法是伪多项式时间复杂度，一般不适用于大规模 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 实例的求解。

群智能启发式算法是近年来求解 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 的主流算法，对于解决大规模实例有突出性能优势。应用 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 第一数学模型设计启发式算法，决策向量 $( x _ { 0 } , x _ { 1 } , \cdots , x _ { 3 n - 1 } )$ 的不同取值组合对应不同个体，这种二元编码法虽然便于个体演化算子的实现，但由于可行解约束条件(2)(3)的限制，编码空间中非正常编码个体(即个体编码不对应问题可行解)的概率至少为1 $- { \bigl ( } { \sqrt [ { 2 } ] { \bigr ) } } ^ { n }$ [3]。为此，需要采用某种策略将非正常编码个体转换为符合解约束条件的编码个体，以提升求解效率和求解质量。Michalewicz[]、贺毅朝[3.4]等学者先后提出的贪心修复与优化策略是消除非正常编码个体效果较好的方法。文献[4]在研究D{0-1}KP粒子群求解算法时，证明了给定项集中三个项目的价值重量比率关系只有四种情况，利用这一特性提出了GR-DKP(Greedy RepairAlgorithm forD{0-1}KP)算法，设计了基于GR-DKP 的粒子群求解算法(the PSO based Greedy Repair Algorithm for solvingD{0-1}KP，PSO-GRDKP)[4]。文献[3]在研究D{0-1}KP 第一遗传算法(First Genetic Algorithm，FirEGA)中再次提出贪心修复与优化 算 法(Greedy Repair and Optimization Algorithm,GROA)[3]，GROA 算法与GR-DKP 算法均按照非递增项价值密度对项进行贪心选取，若项集中有多项是选取状态时，选择价值密度最大项。杨洋等人进一步优化了GROA算法，构造了新贪心修复优化算法(New Greedy Repair and OptimizationAlgorithm，NGROA)[7]，该算法也按照非递增项价值密度对项进行贪心选取，但当项集中有多项是选取状态时，选择项集的价值最大项，应用NGROA 算法提出NFirEGA(New FirstGenetic Algorithm)的研究结果表明较之FirEGA 提升了 $\mathrm { \Delta D \{ 0 - \} }$ （204号1}KP求解质量。最近，文献[8]定义了项集价值密度概念，提出按非递增项集价值密度对项进行贪心选取的策略，当项集中多项是选取状态时，选择满足解约束条件的价值密度最大项。上述贪婪修复与优化算法[3\~8]的时间复杂度为 $O ( n )$ 。多数研究者采用文献[3]提出的GROA算法设计 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 的各类启发式进化算法，如差分进化算法(differential evolution algorithm,DE)[9]、变异蝙蝠算法(Mutated Double Codes Binary BatAlgorithm，MDBBA)[10]、差分进化帝王蝶优化启发式算法(Monarch Butterfly Optimization with Differential Evolution ,DEMBO)[11]、飞蛾搜索算法(Moth Search Algorithm,MS)[12]、基于Lagrange 插值的学习猴群算法(Lagrange Interpolationbased LearningMonkey Algorithm，LSTMA)[13]、基于环论的演化算法 (Ring Theory Based Evolutionary Algorithm，RTEA)[14]、基于离散混合教学的优化算法(Discrete Hybrid TeachingLearning based Optimization Algorithm，HTLBO)[15]等，以上研究常选用FirEGA算法[3]和基本启发式算法作为基线，通过对比求解质量和收敛速度以论证所研究算法的优化性能。

在采用第一数学模型和GROA算法构造D{0-1KP启发式算法的研究中[10.11,14]，文献[10]的仿真实验结果表明，在UDKP实例和SDKP实例上，双重编码二进制蝙蝠算法(DoublecodesBinaryBatAlgorithm，DBBA)的求解质量比FirEGA差，在IDKP实例和WDKP实例上,DBBA的求解质量好于FirEGA;帝王蝶优化算法(Monarch Butter fly Optimization，MBO)在 best、mean及worst三个评价指标上的求解结果要明显差于FirEGA算法[II];PSO-GRDKP算法求解精度和稳定性优于FirEGA[14]。这些研究结果表明，采用同一类贪婪修复与优化方法的不同启发式算法求解性能会有差异。本文基于项集价值密度[8概念，构造一组基于项集的贪婪修复和优化方法，并探究其可行性和性能，进一步讨论贪婪修复方法与数据实例类型之间的适应性关系。为避免启发式算法差异对研究内容的影响，以粒子群算法为例来构造D{0-1}KP求解算法。

# 1 相关研究工作

# 1.1二元粒子群优化算法

Kennedy和Eberhart通过对鸟群捕食行为的研究，在1995年提出标准粒子群算法(Particle Swarm Optimization，PSO)[16],BPSO(Binary Particle Swarm Optimization)是一种应用于离散空间搜索的二元粒子群优化算法[17]，Bansal 和Deep 用粒子速度作为{0-1}KP中物品选择为1或0的概率，提出了一种修正二元粒子群优化(Modified Binary Particle Swarm Optimization，MBPSO）算法来解决背包问题[18]。MBPSO 算法原理描述为：假设搜索空间为D维，定义D维向量 $x _ { i } = ( x _ { i 1 } , x _ { i 2 } , \cdots , x _ { i j } , \cdots , x _ { i D } )$ 表示粒子群中第i个粒子的位置，对应粒子速度为 $\nu _ { i } = ( \nu _ { i 1 } , \nu _ { i 2 } , \cdots , \nu _ { i j } , \cdots , \nu _ { i D } )$ ，个体极值$p _ { b e s t } = ( p _ { b e s t 1 } , p _ { b e s t 2 } , \cdots , p _ { b e s t j } , \cdots$ ， $p _ { b e s t D } \mathrm { . }$ )表示粒子群某次迭代的最优解，全局极值 $g _ { b e s t } = ( g _ { b e s t 1 } , g _ { b e s t 2 } , \cdot \cdot \cdot , g _ { b e s t j } , \cdot \cdot \cdot , g _ { b e s t D } )$ 表示种群在进化过程中的全局最优解，个体极值和全局极值由适应度函数确定，粒子进化公式为

$$
\nu _ { i j } ^ { t + 1 } = \nu _ { i j } ^ { t } + c _ { 1 } \cdot r _ { 1 } \cdot ( p _ { b e s t j } ^ { t } - x _ { i j } ^ { t } ) + c _ { 2 } \cdot r _ { 2 } \cdot ( g _ { b e s t } - x _ { i j } ^ { t } )
$$

$$
s i g ( \nu _ { i j } ^ { t + 1 } ) = \frac { 1 } { 1 + e ^ { - \nu _ { i j } ^ { t + 1 } } }
$$

$$
x _ { i j } ^ { t + 1 } = \left\{ { \begin{array} { l } { 0 , ~ i f ~ r _ { 3 } \geq s i g ( \nu _ { i j } ^ { t + 1 } ) } \\ { 1 , ~ o t h e r w i s e } \end{array} } \right.
$$

其中：t示进化迭代次数， $\nu _ { i j } ^ { t }$ 表示在 $t$ 次进化迭代中第 $i$ 个粒子的第 $j$ 维速度， $\boldsymbol { x } _ { i j } ^ { t }$ 表示在 $t$ 次进化迭代中第 $i$ 个粒子的第 $j$ 维位置。(4)式为粒子群的进化动力方程，主要由三方面构成：$\nu _ { i j } ^ { t }$ 属于粒子个体的惯性势； $c _ { 1 } \cdot r _ { 1 } \cdot ( p _ { b e s t j } ^ { t } - x _ { i j } ^ { t } )$ 来自粒子个体当前历史最好位置 $p _ { b e s t }$ 的引力势，代表粒子“个体认知”；$c _ { 2 } \cdot r _ { 2 } \cdot ( g _ { b e s t } - x _ { i j } ^ { t } )$ 是来自群体当前历史最好位置 $g _ { b e s t }$ 的引力势，代表粒子“社会认知”[19]。学习因子 $c _ { 1 } , c _ { 2 }$ 作为粒子“个体认知”和“社会认知”的主要加权系数，表示进化过程对粒子个体信息和社会信息的学习继承程度，主要影响着粒子的优化目标识别能力。 $r _ { 1 } , r _ { 2 } , r _ { 3 }$ 表示 $( 0 , 1 )$ 之间的随机数。

PSO-GRDKP算法[4]是 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 的一种粒子群求解算法，算法搜索空间维度 $D = 3 n - 1$ ，粒子适应度函数对应个体解的背包装入价值，学习因子 $\boldsymbol { c } _ { 1 } , \boldsymbol { c } _ { 2 }$ 的取值是2，算法时间复杂度是 $O ( n ^ { 3 } )$ 。该算法利用贪婪修复与优化算子对种群中不可行粒子进行校正和优化，有效提升种群中优质个体比率，增强算法寻优能力。

# 1.2不可行个体贪婪修复与优化算法

何毅朝等人在研究D{0-1}KP问题时先后提出GROA[3]、GR-DKP[4] 两种贪婪修复算法，其中GR-DKP在研究粒子群算法(PSO-GRDKP)时提出，以下给出GR-DKP算法伪代码。

# 算法1 GR-DKP

输入： $3 n$ 个项的价值向量 $P$ 、重量向量 $W$ ；背包容量 $c$ ； $H _ { [ 0 , \cdots , 3 n - 1 ] }$ ：按非递增项价值密度次序保存各项下标； $x _ { [ 0 , \cdots , 3 n - 1 ] }$ ：待修复粒子。输出：修复优化后的可行粒子 $x _ { [ 0 , \cdots , 3 n - 1 ] }$ 和适应度值 $f ( x )$ 。

1．fweight =O,fvalue=0

2．FORiIN $r a n g e ( 0 , n - 1 )$ ：IF $( x _ { 3 i } + x _ { 3 i + 1 } + x _ { 3 i + 2 } \geq 1 )$ ：3. $\begin{array} { r l } & { x _ { 3 i } = 0 , x _ { 3 i + 1 } = 0 , x _ { 3 i + 2 } = 0 } \\ & { } \\ & { j = \arg \operatorname* { m a x } _ { j \in \{ 3 i , 3 i + 1 , 3 i + 2 \} } \binom { p } { \binom { N } { W _ { j } } } } \\ & { } \\ & { x _ { j } = 1 , f w e i g h t + = w _ { j } } \\ & { k = 3 n - 1 } \end{array}$

4．WHILE $w e i g h t > C$ AND （204号 $k \geq 0$ ： IF( $~ \cdot ~ x _ { H [ k ] } = 1$ ）: $f w e i g h t - = w _ { H [ k ] } , x _ { H [ k ] } = 0$

k = k −1

5. FOR $j$ IN $r a n g e ( 0 , 3 n - 1 )$ ：$i = \operatorname* { i n t } \left( { H [ i ] \atop 3 } \right)$ IF $\mathrm { ~ ' ~ } x _ { 3 i } + x _ { 3 i + 1 } + x _ { 3 i + 2 } = 0 \mathsf { A N D } \ f w e i g h t + w _ { H [ j ] } \leq C \mathrm { ~ ' ~ } \big )$ $x _ { n _ { 1 / 1 } } = 1 , f w e i g h t + w _ { n _ { 1 / 1 } }$ （204号

6. FORiIN $r a n g e ( 0 , 3 n - 1 ) : f \nu a l u e + = x _ { i } \times p _ { i }$

7．RETURNx,fvalue

算法1第2-4步是对粒子 $x$ 的修复操作、第5步是对粒子 $x$ 的优化操作，算法时间复杂度是 $O ( n )$ 。将算法1第2步的 $j = \arg \operatorname* { m a x } _ { j \in ( 3 ( , 3 i + 1 , 3 i + 2 ) } \left( \mathcal { P } _ { j } \right)$ 置换为 $j = \arg \operatorname* { m a x } _ { \substack { j \in \{ 3 i , 3 i + 1 , 3 i + 2 \} } } \left( p _ { j } \right)$ ，则算法演化为NGROA[7]。

# 2 基于项集的 ${ \mathsf { D } } \{ 0 { \mathsf { - } } 1 \} { \mathsf { K P } }$ 粒子群优化算法

# 2.1基于项集的粒子修复与优化算法贪婪策略

D{0-1}KP已有研究提出的不可行粒子贪婪修复策略[3,4,7]，均按照项价值密度大小对数据排序预处理。本文引入项集价值密度 $R _ { i } ( i \in \{ 0 , 1 , \cdots , n - 1 \} )$ ，按照 $R _ { i }$ 大小以项集为单位对数据进行非递增排列，之后按次序选取项集的项。文献[8]给出了三种 $R _ { i }$ 算法如下：

$$
R _ { i } ^ { 1 } = \operatorname* { m a x } \left( e _ { 3 i } , e _ { 3 i + 1 } , e _ { 3 i + 2 } \right)
$$

$$
R _ { i } ^ { 2 } = \sum _ { k = 0 } ^ { 2 } e _ { 3 i + k }
$$

$$
R _ { i } ^ { 3 } = \frac { \displaystyle \sum _ { k = 0 } ^ { 2 } p _ { 3 i + k } } { \displaystyle \sum _ { k = 0 } ^ { 2 } w _ { 3 i + k } }
$$

易见， $R _ { i } ^ { 1 }$ 算法等效于GR-DKP[4]策略，结合NGROA算法思想，定义 $R _ { i } ^ { 4 }$ 如下：

$$
R _ { i } ^ { 4 } = e _ { 3 i + 2 }
$$

以下给出项集 $i$ 两种项选择策略 $\mathrm { i } t e m _ { i }$ 下：

$$
i t e m _ { i } ^ { 1 } = \operatorname* { m a x } _ { j } \left\{ e _ { j } \big | x _ { j } = 1 , j \in \{ 3 i , 3 i + 1 , 3 i + 2 \} \right\}
$$

$$
i t e m _ { i } ^ { 2 } = \left\{ \operatorname* { m a x } _ { j } \left\{ e _ { j } \left| x _ { j } = 1 , j \in \left\{ 3 i , 3 i + 1 \right\} \right\} , \right. \right. \subsetneqq \left. \sum _  j \in \left\{ 1 , 2 i , 3 i + 1 \right\} \right\} \left. \left. \sum _  j \in \left\{ 1 , 3 i + 1 \right\} \right\} \right.
$$

合式(7)\~(10)和式(11)(12),得到八种 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 基于项集的贪心修复优化方法(Group Greedy Repair and OptimizationAlgorithm,GGROA)，见表1所示。

表1 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 粒子群算法的GGROA策略

Tab.1 GGROA of D {0-1} KP forPSO algorithm   

<html><body><table><tr><td>项集价值密度R,i∈{0,n-1}</td><td>R</td><td>R</td><td>R</td><td>R</td></tr><tr><td>项集i的项选择策略</td><td>item</td><td></td><td>item</td><td></td></tr></table></body></html>

GGROA的伪代码描述见算法2，参数 $m \in \{ 1 , 2 , 3 , 4 \}$ 对应式(7)\~(10)的四种项集价值密度，参数 $z \in \{ 1 , 2 \}$ 对应式(11)(12)的两种项选择策略。

算法2 GGROA( $H ^ { m } , \mathrm { i } t e m ^ { z }$ ）

输入： $3 n$ 个项的价值向量 $P$ 、重量向量 $W$ ；背包容量 $c$ ； $H _ { [ 0 , \cdots , n - 1 ] } ^ { m }$ ：按非递增项价值密度次序保存各项下标； $x _ { [ 0 , \cdots , 3 n - 1 ] }$ ：待修复粒子。输出：修复优化后的可行粒子 $x _ { [ 0 , \cdots , 3 n - 1 ] }$ 和适应度值 $f ( x )$ 。

1:FORiIN $r a n g e ( 0 , n - 1 )$ ： $F l a g _ { i } = 0$ （204号 2: fweight ${ \bf \Omega } = 0 ,$ fvalue $= 0$ （20

3: FORiIN $r a n g e ( 0 , n - 1 )$ ：IF $( x _ { 3 i } + x _ { 3 i + 1 } + x _ { 3 i + 2 } \geq 1 )$ ：4: $\begin{array} { r l } & { x _ { 3 i } = 0 , x _ { 3 i + 1 } = 0 , x _ { 3 i + 2 } = 0 } \\ & { } \\ & { j = i t e m _ { i } ^ { z } } \\ & { x _ { j } = 1 , f w e i g h t + = w _ { j } , F l a g _ { i } = 1 } \\ & { k = n - 1 } \end{array}$

5: WHILE $f w e i g h t > C$ AND $k \geq 0$ ： IF( $F l a g _ { H ^ { m } [ k ] } = 1$ ): j = item()

$$
{ \it f w e i g h t - } = w _ { j } , x _ { j } = 0 , F l a g _ { H ^ { m } [ k ] } = 0
$$

$$
x _ { , } = 1 , f w e i g h t { + = w _ { , } }
$$

7: FORiIN $r a n g e ( 0 , 3 n - 1 ) : f i r a l u e + = x _ { i } \times p _ { i }$

8：RETURN x,fvalue

算法2第2步 $\sim$ 第5是对粒子 $x$ 的修复操作、第6步是对粒子 $x$ 的优化操作，算法时间复杂度是 $O ( n )$ 。

# 2.2基于 GGROA 的 ${ \mathsf { D } } \{ 0 { \mathsf { - } } 1 \} { \mathsf { K P } }$ 粒子群优化算法

文献[4]在构造PSO-GRDKP 算法中，采用了基础离散粒子进化式(4)\~(6)，学习因子的取值 $c _ { 1 } , c _ { 2 }$ 是2。为避免粒子进化公式和进化参数对研究内容的影响，方便同一基准条件下同类研究间的辨析，以下采用文献[4]的方案构造PSO-GGRDKP(PSO based GGROAfor solvingD{0-1}KP)，伪代码见算法3，其中参数 $m , z$ 算法2。

算法3 PSO-GGRDKP(m,z )

输入：3项的价值向量 $P$ 、重量向量 $W$ ，背包容量 $c$ ，种群规模 $N$ ，进化代数 $T$ ，学习常数 $c _ { _ { 1 } } = c _ { _ { 2 } } = 2$

输出：最佳粒子 $g _ { b e s t }$ 和装入背包总价值的近似最优解 $f i m e s s ( g _ { b e s t } )$

1:FORiIN $r a n g e ( 0 , n - 1 )$ ：$R _ { i } ^ { m } = f u n c t i o n _ { m } ( P _ { i } , W _ { i } )$

2：排列 $R _ { i } ^ { \circ } \ge R _ { + + } ^ { \circ } , i \in \left\{ 0 , \cdots , n - 1 \right\}$ ，按项集价值密度 $R _ { i } ^ { * }$ 非递增次序将项集下标存入 $H _ { [ 0 , \cdots , n - 1 ] } ^ { m }$

3: 初始化种群：population $= \left\{ \left( x _ { i } , \nu _ { i } \right) \middle | i \in ( 1 , \cdots . N ) \right\}$

4: FORiIN range(l,N)：

$$
x _ { \cdot } , f i t n e s s \left( x _ { \cdot } \right) { \ = } \mathrm { G G R O A } ( H ^ { \cdot } , \mathrm { i } t e m ^ { \cdot } )
$$

$$
b e s t = i n d e x \_ \operatorname* { m a x } \big ( \big \{ f t n e s s ( x _ { \scriptscriptstyle { i } } ) \big | i \in \{ 1 , \cdots , N \} \big \} \big )
$$

$$
g _ { b e s t } = p _ { b e s t } = x _ { b e s t }
$$

7: $t = 0$ （204号

8: WHILE $t < T$

9: FORiIN range(l,N)：

10: FOR $j$ IN $r a n g e ( 0 , 3 n - 1 )$ ：$\boldsymbol { \nu } _ { \boldsymbol { \psi } } ^ { t + 1 } = \boldsymbol { \nu } _ { \boldsymbol { \psi } } ^ { t } + \boldsymbol { c } _ { \boldsymbol { \imath } } \cdot \boldsymbol { r } _ { \boldsymbol { \imath } } \cdot ( \boldsymbol { p } _ { \mathrm { { e e p } } } ^ { t } - \boldsymbol { x } _ { \boldsymbol { \psi } } ^ { t } ) + \boldsymbol { c } _ { \boldsymbol { \imath } } \cdot \boldsymbol { r } _ { \boldsymbol { \imath } } \cdot ( \boldsymbol { g } _ { \mathrm { { e e p } 0 } } ^ { t } - \boldsymbol { x } _ { \boldsymbol { \psi } } ^ { t } )$ IF $( r _ { \mathrm { { s } } } \geq s i g ( \nu _ { \mathrm { { \# } } } ^ { \prime + 1 } ) ) \colon x _ { \mathrm { { \# } } } ^ { \prime + 1 } = 0$ （20ELSE: $x _ { * } ^ { t + 1 } = 1$   
11: $x _ { i } ^ { t + 1 } , f i t n e s s \left( x _ { i } ^ { \scriptscriptstyle t + 1 } \right) { = } \mathrm { G G R O A } ( H ^ { \scriptscriptstyle \infty } , \mathrm { i } t e m ^ { \scriptscriptstyle * } )$ （204号  
12: 1 $\mathsf { I F } \left( f i t n e s s \left( x _ { i } ^ { \prime + 1 } \right) > f i t n e s s \left( p _ { b e s t } \right) \right) : p _ { _ { b e n } } = x _ { i } ^ { \prime + 1 }$   
13: $\mathbb { I F } \left( f i t n e s s \left( \boldsymbol { p } _ { b e s t } \right) > f i t n e s s \left( \boldsymbol { g } _ { b e s t } \right) \right) : \boldsymbol { g } _ { b e t } = \boldsymbol { p } _ { b e t }$   
14: （204号 $t = t + 1$

15:RETURN $g _ { b e s t } , f i n e s s ( g _ { b e s t } )$ （204号

算法3中 $r _ { 1 } , r _ { 2 } , r _ { 3 }$ 是(0,1)区间的随机数，第1步中functionm $( m \in \{ 1 , 2 , 3 , 4 \} )$ 对应四种项集价值密度计算函数，即式$( 7 ) { \sim } 1 0 )$ ，第10步 $s i g ( x )$ 采用式(5)，算法时间复杂度是$O \left( n \log n \right) + 2 O \left( n \right) + 2 O \left( n N \right) + T \times \left[ O \left( n N \right) + O \left( n \right) \right]$ ，由于 $N < n$ 且 $T < n$ ，故PSO-GGRDKP算法时间复杂度是 $O ( n ^ { 3 } )$ 。

# 3 仿真实验与结果分析

# 3.1 实验方案设计

D{0-1}KP数据集是观察和评测算法性能的标准数据集[3],数据集由逆强相关D{0-1}KP实例(IDKP)、强相关 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 实例(SDKP)、弱相关 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 实例(WDKP)和不相关 $\mathrm { \Delta D \{ 0 - \} }$ $1 \} \mathrm { K P }$ 实例(UDKP)四类数据组成，四类D{0-1}KP实例的数据规模分别为 $3 0 0 { \leq } 3 n { \leq } 3 0 0 0$ 。为验证 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 的各类贪婪修复策略性能特点，进行两组实验。实验一：采用八种基于项集贪婪修复优化策略的 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 粒子群算法实验，以探究八种基于项集贪婪修复优化策略的可行性、性能以及与数据实例类型的适应性关系。实验二：评测PSO-GRDKP[4]、PSO-NGROADKP、PSO-GGRDKP三种典型不可行个体贪婪修复方法的D{0-1}KP粒子群性能特点。两组实验均以比较求解时间和解计算结果分析算法性能。所有实验均在ThinkStationP330计算机上进行，电脑配置Intel $\textsuperscript { \textregistered }$ CoreTMi7-8700CPU-3.2GHZ、16GBDDR4内存、NVIDIAP2200显卡，操作系统是MicrosoftWindows10教育版，算法均使用Python3.6编码。

记D{0-1}KP实例通过基本动态规划法计算得出的最优解为opt、粒子群算法的粒子规模为200、进化代数同项集数$n$ ，粒子群算法独立运算20次的近似最优解最大值为best、平均值为 mean、最差值为worst、平均时长为 $T$ □

# 3.2实验一算法数据与分析

表2列出八种项集贪心修复策略的对应编号(id)。

# 表2D{0-1}KP 的GGROA 策略及序号

Tab.2Ggroas and their serial numbers of D{O-1} KP   

<html><body><table><tr><td>id</td><td>(R,item)</td><td>id</td><td>(R,item)</td></tr><tr><td>1</td><td>(1,1)</td><td>5</td><td>(3,1)</td></tr><tr><td>2</td><td>(1,2)</td><td>6</td><td>(3.2)</td></tr><tr><td>3</td><td>(2.1)</td><td>7</td><td>(4,1)</td></tr><tr><td>4</td><td>(2.2)</td><td>8</td><td>(4.2)</td></tr></table></body></html>

表3所示为数据规模 $3 n = 9 0 0$ 和 $3 n = 1 8 0 0$ 的四类实例上运行八种贪婪修复优化方法的粒子群算法实验数据，PSO-GGRDKP算法名称下标编号对应表2。

应用八种贪婪修复策略对八个数据实例IDKP3、IDKP6、SDKP3、SDKP6、UDKP3、UDKP6、WDKP3、WDKP6分别独立求解20次，20个求解结果分布情况箱线图如图1所示。

表3D{0-1}KP标准数据实例PSO-GGRDKP 算法实验结果  
Tab.3PSO-GGRDKP algorithm experimental results of D {0-1} KP standard dataset   

<html><body><table><tr><td colspan="2">实例名</td><td>PSO-</td><td>PSO-</td><td>PSO-</td><td>PSO-</td><td>PSO-</td><td>PSO-</td><td>PSO-</td><td>PSO-</td></tr><tr><td colspan="2">(最优值)</td><td>GGRDKP1</td><td>GGRDKP2</td><td>GGRDKP3</td><td>GGRDKP4</td><td>GGRDKP5</td><td>GGRDKP6</td><td>GGRDKP7</td><td>GGRDKP8</td></tr><tr><td rowspan="5">IDKP3 (234804)</td><td>best mean</td><td>234772 234565.65</td><td>234737 234592.45</td><td>233983 233706</td><td>234160 233832.9</td><td>234450 234296.05</td><td>234413 234139.9</td><td>234720 234490.8</td><td>234668 234354.6</td></tr><tr><td>worst</td><td>233790</td><td>234183</td><td>233092</td><td>232980</td><td>234103</td><td>233119</td><td>234204</td><td>232898</td></tr><tr><td></td><td>12.18</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>T(s)</td><td></td><td>9.07</td><td>11.03</td><td>11.72</td><td>10.88</td><td>10.06</td><td>11.22</td><td>9.40</td></tr><tr><td>ERR</td><td>0.001</td><td>0.001</td><td>0.005</td><td>0.004</td><td>0.002</td><td>0.003</td><td>0.001</td><td>0.002</td></tr><tr><td>IDKP6</td><td>best</td><td>452250 451303.05</td><td>451982 450804</td><td>450537 449725.95</td><td>450171</td><td>450971</td><td>450816</td><td>451829</td><td>451876</td></tr><tr><td rowspan="5">(452463)</td><td>mean</td><td></td><td></td><td></td><td>449256.7</td><td>450148.5</td><td>449898.55</td><td>451071.3</td><td>450849.7</td></tr><tr><td>worst</td><td>449531</td><td>448999</td><td>446422</td><td>447609</td><td>448009</td><td>447226</td><td>449593</td><td>446822</td></tr><tr><td>T(s)</td><td>46.70</td><td>36.34</td><td>48.26</td><td>41.80</td><td>46.64</td><td>42.04</td><td>44.23</td><td>37.17</td></tr><tr><td>ERR</td><td>0.006</td><td>0.008</td><td>0.013</td><td>0.011</td><td>0.010</td><td>0.012</td><td>0.006</td><td>0.012</td></tr><tr><td>best</td><td>237313</td><td>237638</td><td>237273</td><td>237428</td><td>237414</td><td>236682</td><td>236973</td><td>236671</td></tr><tr><td>SDKP3 (238248)</td><td>mean</td><td>236644.85</td><td>236362.7</td><td>236428.45</td><td>236276.9</td><td>236661.5</td><td>235866.1</td><td>236064.6</td><td>236051.5</td></tr><tr><td rowspan="6"></td><td>worst</td><td>235198</td><td>232226</td><td>233959</td><td>232525</td><td>234957</td><td>234252</td><td>234342</td><td>234145</td></tr><tr><td>T(s)</td><td>11.48</td><td>9.56</td><td>10.46</td><td>9.10</td><td>10.66</td><td>9.01</td><td>10.37</td><td>9.32</td></tr><tr><td>ERR</td><td>0.01</td><td>0.01</td><td>0.01</td><td>0.01</td><td>0.01</td><td>0.01</td><td>0.01</td><td>0.01</td></tr><tr><td>best</td><td>462883</td><td>461926</td><td>462498</td><td>460133</td><td>462797</td><td>462300</td><td>462197</td><td>462010</td></tr><tr><td>mean</td><td>461454.95</td><td>458730.3</td><td>460320.15</td><td>456405.1</td><td>461389.9</td><td>459623.25</td><td>460858.45</td><td>460292.2</td></tr><tr><td>SDKP6 worst (466097)</td><td>459209</td><td>451076</td><td>456090</td><td>447800</td><td>458299</td><td>454888</td><td>455773</td><td>457203</td></tr><tr><td rowspan="6">WDKP3</td><td>T(s)</td><td>45.41</td><td>37.77</td><td>41.34</td><td>36.29</td><td>41.70</td><td>35.94</td><td>41.77</td><td>37.06</td></tr><tr><td>ERR</td><td>0.01</td><td>0.02</td><td>0.01</td><td>0.02</td><td>0.01</td><td>0.01</td><td>0.01</td><td>0.01</td></tr><tr><td>best</td><td>256286</td><td>255916</td><td>255712</td><td>255529</td><td>255879</td><td>255844</td><td>256083</td><td>256061</td></tr><tr><td>mean</td><td>255516.15</td><td>255491.25</td><td>255003.15</td><td>254928.75</td><td>255034</td><td>255448.45</td><td>255300.9</td><td>255713.75</td></tr><tr><td>worst</td><td>253410</td><td>254768</td><td>252796</td><td>253758</td><td>253558</td><td>254668</td><td>253481</td><td>254466</td></tr><tr><td>(256616) T(s)</td><td>10.77</td><td>8.98</td><td>12.47</td><td>9.00</td><td>10.50</td><td>10.32</td><td>11.77</td><td>9.85</td></tr><tr><td rowspan="6">WDKP6 (466050)</td><td>ERR</td><td>0.004</td><td>0.004</td><td>0.006</td><td>0.007</td><td>0.006</td><td>0.005</td><td>0.005</td><td>0.004</td></tr><tr><td>best</td><td>464720</td><td>464210</td><td>463503</td><td>463134</td><td>463414</td><td>463434</td><td>464072</td><td>464274</td></tr><tr><td>mean</td><td>463532.4</td><td>462831.4</td><td>462020.7</td><td>461409.2</td><td>461794.25</td><td>462586.1</td><td>462883.55</td><td>463214.55</td></tr><tr><td>worst</td><td>462308</td><td>459786</td><td>459081</td><td>459144</td><td>459866</td><td>460557</td><td>461176</td><td>461365</td></tr><tr><td>T(s)</td><td>44.32</td><td>38.93</td><td>44.48</td><td>36.44</td><td>45.07</td><td>40.76</td><td>43.48</td><td>37.56</td></tr><tr><td>ERR</td><td>0.005</td><td>0.007</td><td>0.009</td><td>0.010</td><td>0.009</td><td>0.007</td><td>0.007</td><td>0.006</td></tr><tr><td>UDKP3 (184006)</td><td>best</td><td>263944</td><td>267162</td><td>262269</td><td>267172</td><td>265006</td><td>267221</td><td>264710</td><td>267102</td></tr><tr><td rowspan="6"></td><td>mean</td><td>256631.2</td><td>266185</td><td>252478.55</td><td>266165.65</td><td>259174</td><td>266483.15</td><td>258556</td><td>266184.5</td></tr><tr><td>worst</td><td>227502</td><td>263431</td><td>229837</td><td>263871</td><td>233367</td><td>264297</td><td>237289</td><td>263701</td></tr><tr><td>T(s)</td><td>11.83</td><td>10.50</td><td>12.01</td><td>10.57</td><td>12.11</td><td>10.59</td><td>11.77</td><td>10.66</td></tr><tr><td>ERR</td><td>0.05</td><td>0.01</td><td>0.06</td><td>0.01</td><td>0.04</td><td>0.01</td><td>0.04</td><td>0.01</td></tr><tr><td>best</td><td>520183</td><td>529834</td><td>517776</td><td>530221</td><td>517264</td><td>529030</td><td>521267</td><td>528480</td></tr><tr><td>UDKP6 mean</td><td>506575.15</td><td>526417.6</td><td>504295.95</td><td>526795.8</td><td>504110.5</td><td>526440.7</td><td>508569.7</td><td>526602.7</td></tr><tr><td rowspan="4">(536578)</td><td>worst</td><td>457476</td><td>519485</td><td>464104</td><td>522972</td><td>451696</td><td>521096</td><td>464333</td><td>524425</td></tr><tr><td>T(s)</td><td>47.47</td><td>41.07</td><td>47.79</td><td>41.75</td><td>47.41</td><td>41.24</td><td>47.59</td><td>41.31</td></tr><tr><td>ERR</td><td>0.06</td><td>0.02</td><td>0.06</td><td>0.02</td><td>0.06</td><td>0.02</td><td>0.05</td><td>0.02</td></tr><tr><td></td></table></body></html>

由表3和图1可以看出，粒子群算法采用八种项集贪婪修复策略都是可行的，但不同的项集贪婪修复策略在同一类数据实例上存在显著性能差异，相同的项集贪婪修复策略在不同类型实例上性能表现也有不同。同类数据的两个实例，确定平均最优近似解前三的贪心修复策略交集为该类数据较佳的算法，其中，IDKP：PSO-GGRDKPi、PSO-GGRDKP2，SDKP:PSO-GGRDKP1、PSO-GGRDKP5，WDKP：PSO-GGRDKP1、PSO-GGRDKP8，UDKP:PSO-GGRDKP2、PSO-GGRDKP6。

结合每种数据实例的平均时长 $T$ ，进一步选择各类数据实例时间性能较优的求解算法，其中，IDKP：PSO-GGRDKP2，SDKP：PSO-GGRDKP5，WDKP：PSO-GGRDKP8，UDKP：PSO-GGRDKP2。

# 3.3实验二算法数据与分析

PSO-GRDKP、PSO-NGROADKP、PSO-GGRDKP算法实验数据见表4所示，其中PSO-GGRDKP算法根据实验一分析结果，选择四类数据实例上的性能较优的贪婪修复策略进行实验。

![](images/f58d65565ec5c30987fe4c5ed9a2ff25a35570e72c4833aa9a0dac294c1b9533.jpg)  
图1D{0-1}KP实例PSO-GGRDKP求解结果箱线图  
Fig.1Box plots ofPSO-GGRDKP results for D{0-1}KP instances

表4PSO-GGRDKP、PSO-NGROADKP、PSO-GRDKP 算法实验结果

Tab.4Algorithm experimental results of PSO-GGRDKP,PSO-NGROADKP,PSO-GRDKP   

<html><body><table><tr><td rowspan="2">Dataset</td><td rowspan="2">C</td><td rowspan="2">opt</td><td colspan="4">PSO-GGRDKP</td><td colspan="4">PSO-NGROADKP</td><td colspan="4">PSO-GRDKP</td></tr><tr><td>best</td><td>mean</td><td>worst</td><td>T/s</td><td>best</td><td>mean</td><td>worst</td><td>T/s</td><td>best</td><td>mean</td><td>worst</td><td>T/s</td></tr><tr><td>IDKP1</td><td>61500</td><td>70106</td><td>70090</td><td>70057</td><td>70037</td><td>1.106</td><td>70098</td><td>70097</td><td>70090</td><td>1.430</td><td>70106</td><td>70105</td><td>70098</td><td>1.284</td></tr><tr><td>IDKP2</td><td>103936</td><td>118268</td><td>118232</td><td>118168</td><td>118037</td><td>4.272</td><td>118235</td><td>118235</td><td>118232</td><td>5.294</td><td>118268</td><td>118268</td><td>118268</td><td>4.862</td></tr><tr><td>IDKP3</td><td>214453</td><td>234804</td><td>234640</td><td>234326</td><td>232619</td><td>9.216</td><td>234785</td><td>234778</td><td>234679</td><td>11.666</td><td>234802</td><td>234795</td><td>234686</td><td>11.048</td></tr><tr><td>IDKP4</td><td>251980</td><td>282591</td><td>282565</td><td>282350</td><td>281660</td><td>16.444</td><td>282579</td><td>282570</td><td>282423</td><td>20.327</td><td>282571</td><td>282562</td><td>282442</td><td>19.352</td></tr><tr><td>IDKP5</td><td>297482</td><td>335584</td><td>335460</td><td>335077</td><td>334317</td><td>29.298</td><td>335580</td><td>335562</td><td>335383</td><td>31.347</td><td>335541</td><td>335538</td><td>335474</td><td>30.543</td></tr><tr><td>IDKP6</td><td>415217</td><td>452463</td><td>451933</td><td>450909</td><td>449351</td><td>47.024</td><td>452410</td><td>452359</td><td>451760</td><td>47.535</td><td>452458</td><td>452412</td><td>451920</td><td>47.303</td></tr><tr><td>IDKP7</td><td>434677</td><td>489149</td><td>488657</td><td>487982</td><td>486639</td><td>50.667</td><td>489044</td><td>488975</td><td>488469</td><td>65.012</td><td>489118</td><td>489095</td><td>488870</td><td>58.752</td></tr><tr><td>IDKP8</td><td>464860</td><td>533841</td><td>532893</td><td>531437</td><td>527685</td><td>84.127</td><td>533749</td><td>533604</td><td>533060</td><td>88.726</td><td>533833</td><td>533810</td><td>533398</td><td>75.925</td></tr><tr><td>IDKP9</td><td>454989</td><td>528144</td><td>527458</td><td>526463</td><td>524077</td><td>92.545</td><td>528010</td><td>527978</td><td>527678</td><td>104.692</td><td>528115</td><td>528106</td><td>527965</td><td>95.705</td></tr><tr><td>IDKP10</td><td>496541</td><td>581244</td><td>580528</td><td>578794</td><td>576617</td><td>111.433</td><td>581043</td><td>580968</td><td>580350</td><td>142.916</td><td>581207</td><td>581194</td><td>581020</td><td>118.073</td></tr><tr><td>SDKP1</td><td>60143</td><td>94459</td><td>94325</td><td>93875</td><td>93098</td><td>1.178</td><td>94431</td><td>94411</td><td>94258</td><td>1.792</td><td>94232</td><td>93962</td><td>93413</td><td>1.423</td></tr><tr><td>SDKP2</td><td>100200</td><td>160805</td><td>160211</td><td>159881</td><td>159009</td><td>4.652</td><td>160663</td><td>160631</td><td>160359</td><td>5.340</td><td>160671</td><td>160321</td><td>159616</td><td>5.412</td></tr><tr><td>SDKP3</td><td>151680</td><td>238248</td><td>236996</td><td>236248</td><td>234059</td><td>12.609</td><td>238132</td><td>238081</td><td>237774</td><td>13.362</td><td>238055</td><td>237476</td><td>236394</td><td>11.994</td></tr><tr><td>SDKP4</td><td>214644</td><td>340027</td><td>338126</td><td>337472</td><td>336426</td><td>18.292</td><td>339817</td><td>339562</td><td>338477</td><td>21.282</td><td>339786</td><td>339055</td><td>337662</td><td>20.905</td></tr><tr><td>SDKP5</td><td>300632</td><td>463033</td><td>459165</td><td>457548</td><td>453168</td><td>28.383</td><td>462667</td><td>462163</td><td>461013</td><td>32.062</td><td>461309</td><td>459479</td><td>456502</td><td>33.365</td></tr><tr><td>SDKP6</td><td>289412</td><td>466097</td><td>462003</td><td>460618</td><td>457818</td><td>41.004</td><td>465596</td><td>465323</td><td>464135</td><td>49.359</td><td>465194</td><td>464176</td><td>462190</td><td>47.159</td></tr><tr><td>SDKP7</td><td>396421</td><td>620446</td><td>616378</td><td>612841</td><td>605344</td><td>56.047</td><td>619691</td><td>618860</td><td>617739</td><td>65.980</td><td>618204</td><td>616231</td><td>612674</td><td>64.845</td></tr><tr><td>SDKP8</td><td>424240</td><td>670697</td><td>664952</td><td>662384</td><td>654486</td><td>73.405</td><td>669310</td><td>668958</td><td>667365</td><td>83.399</td><td>668735</td><td>667212</td><td>664795</td><td>83.565</td></tr><tr><td>SDKP9</td><td>465564</td><td>739121</td><td>734123</td><td>730826</td><td>724267</td><td>93.362</td><td>737018</td><td>736819</td><td>735649</td><td>105.648</td><td>736476</td><td>734747</td><td>731842</td><td>107.098</td></tr><tr><td>SDKP10</td><td>477837</td><td>765317</td><td>758980</td><td>753068</td><td>747259</td><td>124.712</td><td>762795</td><td>762668</td><td>761977</td><td>126.717</td><td>761900</td><td>760266</td><td>757622</td><td>132.407</td></tr><tr><td>WDKP1</td><td>65423</td><td>83098</td><td>83025</td><td>82932</td><td>82731</td><td>1.122</td><td>83085</td><td>83082</td><td>83051</td><td>1.336</td><td>83083</td><td>83067</td><td>82927</td><td>1.361</td></tr><tr><td>WDKP2</td><td>102795</td><td>138215</td><td>137843</td><td>137759</td><td>137494</td><td>4.354</td><td>138175</td><td>138163</td><td>138015</td><td>5.128</td><td>138213</td><td>138185</td><td>137928</td><td></td></tr><tr><td>WDKP3</td><td>196603</td><td>256616</td><td>256114</td><td>255722</td><td>255289</td><td>9.431</td><td>256470</td><td>256432</td><td>256054</td><td>11.409</td><td>256586</td><td>256369</td><td>255310</td><td>5.356</td></tr><tr><td>WDKP4</td><td>239770</td><td>315657</td><td>314849</td><td>314640</td><td>314193</td><td>16.692</td><td>315585</td><td>315521</td><td>315022</td><td>20.221</td><td>315620</td><td>315418</td><td></td><td>12.101</td></tr><tr><td>WDKP5</td><td>325793</td><td>428490</td><td>427124</td><td>426391</td><td>424448</td><td>26.110</td><td>428188</td><td>428068</td><td>427534</td><td>31.547</td><td>428424</td><td>428129</td><td>314548</td><td>21.317</td></tr><tr><td>WDKP6</td><td>351265</td><td></td><td>464687</td><td>463570</td><td>461558</td><td>37.787</td><td>465756</td><td>465690</td><td></td><td>46.473</td><td>465857</td><td></td><td>426928</td><td>34.034</td></tr><tr><td>WDKP7</td><td>411219</td><td>466050 547683</td><td>545903</td><td>544410</td><td>542740</td><td>51.114</td><td>547239</td><td>547156</td><td>465292 546451</td><td>63.677</td><td>547369</td><td>465599 547091</td><td>464261 545921</td><td>50.446 70.765</td></tr><tr><td>WDKP8 424552</td></table></body></html>

从表4看出，三类贪婪修复优化策略的粒子群算法求解质量和时间性能各不相同。定义粒子群算法的解误差率 $E R R = 1 - m e a n \%$ ，各数据实例的解误差率平均值为$E R R _ { - } A V E$ ，该值越小，算法性能越优。进一步统计三类贪婪修复优化粒子群算法四类数据实例的平均解误差率与算法平均时长见表5所示。表中三类贪婪修复优化粒子群算法分别是 PSO-GGRDKP,PSO-GRDKP、PSO-NGROADKP。

由表5看出，在四类数据实例上，三类粒子群算法的平均解误差率呈现一致趋势： $I D K P < W D K P < S D K P < U D K P$ ，即对IDKP实例求解误差率最低，而UDKP实例的解误差率最高。三类算法中，PSO-NGROADKP平均解误差率最低，仅为$0 . 2 \%$ ，PSO-GGRDKP的平均解误差率略高于PSO-NGROADKP、PSO-GRDKP分别是 $0 . 7 \%$ ， $0 . 4 \%$ 。在四类数据实例上，PSO-GGRDKP的时间性能均显著优于PSO-GRDKP和PSO-NGROADKP，PSO-GGRDKP算法时间性能 较之 PSO-GRDKP 提升 $12 . 9 \%$ ，较之 PSO-NGROADKP算法时间性能提升 $1 3 . 8 \%$ 。三类粒子群算法的四类数据实例时间性能趋势表现不一致，PSO-GGRDKP、PSO-NGROADKP、PSO-GRDKP算法时间性能表现最好的数据实例各自为：WDKP、SDKP和IDKP。

Tab.5Solution average error rate and average time of three kinds of PSO   

<html><body><table><tr><td rowspan="2">数据集</td><td colspan="2">PSO-GGRDKP</td><td colspan="2">PSO-NGROADKP</td></tr><tr><td colspan="4">ERR_AVE T_AVE ERR_AVE</td></tr><tr><td>IDKP</td><td>0.002 44.613</td><td>0.000</td><td>51.895</td><td>0.000 46.285</td></tr><tr><td>SDKP</td><td>0.010 45.364</td><td>0.002</td><td>50.494</td><td>0.005 50.817</td></tr><tr><td>WDKP</td><td>40.981</td><td>0.001</td><td>51.658</td><td>0.001 53.938</td></tr><tr><td>UDKP</td><td>45.807</td><td>0.005</td><td>51.100</td><td>0.015 51.916</td></tr><tr><td>AVE</td><td>44.191</td><td>0.002</td><td>51.287</td><td>0.005 50.739</td></tr></table></body></html>

进一步探究算法解误差率与数据类型之间的关联性，表6给出了四类数据实例的项价值系数与项重量系数的相关系数 $\rho$ ，项价值密度均值“，项价值密度标准差 $\sigma$ 。结合表5统计值，易见除SDKP实例外，在IDKP、WDKP、UDKP类型上，三种算法解误差率与相关系数大小一致，即数据实例相关系数越大，则该实例上对应算法的解误差率越小。但SDKP相关系数略小于IDKP、略大于WDKP，其解误差率却高于WDKP。此外，SDKP与UDKP两类数据实例的相关系数差异很大，但其算法解误差率较为接近。从表6可以看出项价值密度均值有$I D K P _ { \mu } < W D K P _ { \mu } < S D K P _ { \mu } < U D K P _ { \mu }$ ，项价值密度标准差有：$I D K P _ { \sigma } < W D K P _ { \sigma } < S D K P _ { \sigma } < U D K P _ { \sigma }$ ，这与四类数据对应求解误差率表现趋势一致，说明D{0-1}KP的贪婪修复优化策略粒子群算法性能与项价值密度的均值、标准差等数据特征高度相关，这进一步解释了SDKP与UDKP性能表现较为相近的情况。

表5三类粒子群算法平均解误差率与平均时长  
表6 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 实例统计量  
Tab.6Statistical values of ${ \mathrm { D } } \{ 0 { \mathrm { - } } 1 \}$ KP instance   

<html><body><table><tr><td>Data set</td><td>p</td><td>μ</td><td></td></tr><tr><td>IDKP</td><td>0.956</td><td>0.844</td><td>0.222</td></tr><tr><td>SDKP</td><td>0.947</td><td>1.628</td><td>2.141</td></tr><tr><td>WDKP</td><td>0.931</td><td>1.079</td><td>0.230</td></tr><tr><td>UDKP</td><td>0.408</td><td>2.261</td><td>9.205</td></tr></table></body></html>

# 4 结束语

本文在定义D{0-1}KP的项集价值密度概念基础上，构造了具有八种组合策略的不可行个体贪婪修复优化方法(GGROA)，以粒子群算法为例，进一步构造了PSO-GGRDKP算法以探究GGROA方法用于求解 $\mathrm { D } \{ 0 \mathrm { - } 1 \} \mathrm { K P }$ 的可行性和性能。D{0-1}KP四类数据实例的算法运行结果表明：

1)适合各类实例的GGROA算子分别为IDKP：PSO-GGRDKP2,SDKP:PSO-GGRDKP5,WDKP: PSO-GGRDKP8,UDKP: PSO- $\mathrm { G G R D K P } _ { 2 }$ 。

2)与PSO-NGROADKP、PSO-GRDKP 相比，PSO-GGRDKP平均解误差率高于两个算法分别是 $0 . 7 \%$ 、 $0 . 4 \%$ 而算法时间性能较之两个算法提升 $1 3 . 8 \%$ 、 $12 . 9 \%$ 。

3)PSO-GGRDKP、PSO-NGROADKP、PSO-GRDKP算法解误差率与数据实例相关系数、项价值密度均值、项价值密度标准差等数据特征高度相关。

以上结果表明，PSO-GGRDKP 算法的解误差率略高于PSO-NGROADKP、PSO-GRDKP,但较显著改善了D{0-1}KP的算法时间性能。

本文以粒子群算法为例，构造D{0-1}KP的PSO-GGRDKP算法并验证其性能。受各类应用GROA的改进启发式算法研究结果启示，本文推断在不同启发式求解算法中使用GGROA的求解性能可能会有差异，限于篇幅，这将作为进一步研究工作讨论。近期，文献[20]提出D{0-1}KP 问题粒子群算法的项集个体编码方案，接下来考虑结合文献[20]的工作改进PSO-GGRDKP算法。

# 参考文献：

[1]Guder J.Discounted knapsack problems for pairs of items [D]. Nuremberg:University of Erlangen-Nurnberg,2005.   
[2]Guldan B.Heuristic and exact algorithms for discounted knapsack problems [D]. Nuremberg: University of Erlangen-Nuremberg,2007: 1- 78.   
[3] 贺毅朝，王熙照，李文斌，等．基于遗传算法求解折扣{0-1}背包问 题的研究 [J]．计算机学报,2016,39 (12):2614-2630.(He Yichao, Wang Xizhao,Li Wenbin,et al. Research on genetic algorithms for discounted{0-1} knapsack problem[J]. China Journal ofComputer,2016, 39 (12): 2614-2630.)   
[4]He YC,WangX Z,HeYL,et al. Exact and approximate algorithms for discounted{0-1}knapsack problem [J]. Information Sciences,2016,369 (11): 634-647.   
[5]Rong A,Figueira JR,Klamroth K.Dynamic programming based algorithms for the discounted{O-1}knapsack problem [J].Applied Mathematics & Computation,2012,218 (12): 6921-6933.   
[6]Michalewicz Z, Schoenauer M. Evolutionary algorithms for constrained parameter optimization problems [J]. Evolutionary Computation,1996, 4 (1): 1-32.   
[7] 杨洋，潘大志，贺毅朝．改进修复策略遗传算法求解折扣{0-1}背包 问题[J].计算机工程与应用,2018,54(21):37-42.(YangYang,PAN Dazhi,He Yichao. Improved repair strategy genetic algorithm solve discount{0-1}knapsack problem [J]. ComputerEngineeringand Applications,2018,54 (21): 37-42.)   
[8]Wilbaut C,Todosijevic R,HAnafi S,et al. Heuristic and exact fixationbased approaches for the discounted O-1 knapsack problem [J].arXiv preprint,2021,arXiv: 2106.03438.   
[9]Zhu H, He Y C,Wang X Z,et al. Discrete diferential evolutions for the discounted{0-1}knapsack problem [J]. International Journal of BioInspired Computation,2017,10 (4): 219-238.   
[10]吴聪聪，贺毅朝，陈嶷瑛，等．变异蝙蝠算法求解折扣{0-1}背包问 题[J].计算机应用,2017,37(005):1292-1299.(Wu Congcong,He Yichao,Chen Yiying，et al. Mutated bat algorithm for solving discounted{0-1}knapsackproblem[J].JournalofComputer Applications,2017,37 (005):1292-1299.)   
[11]冯艳红，杨娟，贺毅朝，等．差分进化帝王蝶优化算法求解折扣{0-1 背包问题[J]．电子学报，2018,46(6)：1343-1350.(Feng Yanhong, Yang Juan,He Yichao,et al.Monarch butterfly optimization algorithm with differential evolution for the discounted{0-1 knapsack problem [J]. Acta Electronica Sinica,2018,46 (6):1343-1350.)   
[12] Feng Y,Wang G G. Binary moth search algorithm for discounted {0-1 knapsack problem [J].IEEE Access,2018,6 (99):10708-10719.

[13]徐小平，徐丽，王峰，刘龙．基于Lagrange插值的学习猴群算法求解

折扣{0-1}背包问题[J]．计算机应用，2020,40(11):19-24.(Xu Xiaoping,Xu Li,Wang Feng,Liu Long.Learning monkey algorithm based on Lagrange interpolation to solve discounted{O-1}knapsack problem [J]. Journal of Computer Application,2020,40 (11):19-24.)   
[14]HeYC,Wang X Z,Gao S G.Ring theory-based evolutionaryalgorithm and its application to $\mathrm { D } \{ 0 { - } 1 \}$ KP[J].Applied Soft Computing,2019,77 (4):714-722.   
[15]Wu CC,Zhao JL,FengYH,et al.Solving discounted{0-1}knapsack problems by a discrete hybrid teaching-learning-based optimization algorithm[J].Applied Intelligence,2020,50(12):1872-1888.   
[16]Kennedy J,EberhartRC.Particle swarm optimization [C]//Proceedings ofIEEE International Conference OnNeural Networks.Perth,Australia: IEEE,1995:1942-1948.   
[17]Kennedy J,EberhartRC.Adiscrete binary version of the particle swarm algorithm [C]// IEEE International Conference on Systems,Man,and Cybernetics.Computational Cybernetics and Simulation，12-15 Oct. 1997.IEEE,1997,5(1):4104-4108.   
[18]Bansal JC,Deep K.A modified binary particle swarm optimization for Knapsack problems [J].Applied Mathematics and Computation,2012, 218 (22): 11042-11061.   
[19]麻荣永，杨磊磊，张智超．基于粒子迭代位移和轨迹的粒子群算法 C1、C2参数特性分析[J].数学计算：中英文版，2013,2(4):109-115. (MaRongyong,Yang Leilei, Zhang Zhichao.Analysis the Characteristic of C1,C2 based on the PSO of Iterative Shift and Trajectory ofParticle [J].Mathematical Computation,2013,2(4):109-115)   
[20] Truong T K.Different transfer functions for binary particle swarm optimization with a new encoding scheme for discounted{O-1} knapsack problem[J].Mathematical Problems in Engineering,2021,2021(4):1- 17.