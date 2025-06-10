# 基于变异交叉方程与进化选择机制的回溯优化改进算法

赵琳敬la,1b，葛宝臻la,1b，陈雷la,1b,2+

(1．天津大学a.精密仪器与光电子工程学院，天津 3072;b.光电信息技术教育部重点实验室，天津 300072;2.天津商业大学 信息工程学院，天津 300134)

摘要：针对回溯搜索优化算法存在的收敛速度慢，容易陷入局部最优等问题，提出了一种改进算法。首先利用t分布产生变异尺度系数，加快了算法收敛速度；接着完善交叉方程结构，引入最优个体控制种群搜索方向，有效提高了算法开发能力；最后提出进化选择机制，引入差分进化算法变异因子，一定概率下以较差解替换较优解，避免算法陷入局部最优。在数值实验中，选取了15个测试函数进行仿真测试，并与5种表现良好的算法进行了比较，结果表明，该算法在收敛速度及搜索精度方面有明显优势。

关键词：回溯搜索优化算法；变异方程；交叉方程；差分进化算法 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2017.12.0848

# Backtracking search optimization algorithm based on mutation and crossing equations and evolutionary selection mechanism

Zhao Linjingla,1b, Ge Baozhenla,1b, Chen Leila,1b, 2† (1.a.SchoolofPrecisionInstruments&Opto-Electronics Engineering,b.KeyLaboratoryofOpto-Electronics Information& Technical Scienceofinstryofducation,njinUnversity,iajin,China;2.holofIformatonEning, Tianjin University of Commerce,Tianjin 300134, China)

Abstract:According tothe slow convergence and easinessto trap in local optimum of backtracking search optimization algorithm,this paper presented an improved algorithm.The method proposedamutationscale factor based ontdistribution firstlyto speeduptheconvergencerate;then the algorithm improved the structure ofcrossover equation and introduced the optimal indiviualtocontrolthedirectionofpopulationsearch,whichefectivelyimprovedthedevelopmentcapability.Finaly thealgorithmproposedtheevolutionaryselectionmechanism,introducedthe mutationfactorofdiferentialevolutionalgorithm andreplacedtheoptimalsolution with worsesolutionunderacertainprobability,whichcanavoidalgorithmtofallintohelocal optimum.The numerical experiments selected 15 test functions forsimulationand compared with 5well-behaved algorithms. The results show that the proposed algorithm has obvious advantages in terms ofconvergencerate and search accuracy. Key words: backtracking search optimization algorithm(BSA); mutation equation; crossing equation; diferential evolution

# 0 引言

近些年，进化算法以其结构简单、参数较少、易于实现等特点受到广泛应用，各种进化算法层现叠出，如经典的遗传算法（geneticalgorithm,GA）[1]、粒子群优化算法（particle swarmoptimization,PSO)[2]、差分进化算法（deferential evolution,DE）[3]、人工蜂群算法（artificial bee colony algorithm,ABC）[4]等。然而随着高维多模态复杂优化问题出现的愈加频繁，使全局优化算法面临着更大的挑战。对此，学者们在现有进化算法的基础上，提出了大量改进算法以及新的优化算法。例如，Zhu 等人[5]提出的蜂群改进算法GABC，李文斌等人[提出的差分进化改进算法CNS-DE，姜凤利等人[7提出的粒子群优化改进算法IPSO，以及 Meng 等人[8]提出的鸡群算法（chicken swarmoptimization,CSO），Zheng等人[9]提出的水波算法（waterwaveoptimization,WWO），高江锦等人[10]提出的免疫否定进化选择算法（immune evolution negative selection algorithm,IENSA）等新型进化算法。

回溯搜索优化算法（backtracking search algorithm,BSA）是Civicioglu[11]于2013年提出的一种新型进化算法。算法框架与差分进化算法类似，但具体操作有本质区别[12]。BSA采用历史种群控制搜索方向，加之其高效新颖的混合交叉策略，使其各项性能都取得了不错的成绩。

但整体来看，BSA探索能力较强而开发能力有待提高，导致收敛速度较慢。针对这一缺点，本文提出了基于t分布的变异系数F，以及加入最优个体引导的新交叉方程，在保证探索能力的基础上，大大提高了算法的收敛速度。同时，提出进化选择机制，引入差分进化算法变异算子DE/rand/1，增加全局探索能力，避免算法早熟收敛。最后，选取15个测试函数，对包括本文改进算法在内的六种算法进行数值实验，结果表明，本文改进算法显著提高了BSA的收敛速度和精度。

# 1 回溯搜索优化算法介绍

BSA是一种基于群体智能的进化算法，算法结构与其他进化算法类似，主要包括五个步骤，分别为种群初始化、选择1、种群变异、种群交叉、选择 $\mathrm { I I }$ 。

# 1）种群初始化

BSA初始化种群的方法为随机产生，方程如式(1)(2)所示。

$$
P o p _ { i , j } \sim U ( L o w _ { j } , U p _ { j } )
$$

$$
O l d p o p _ { i , j } \sim U ( L o w _ { j } , U pmb { p } _ { j } )
$$

其中：Pop 为初始种群；Oldpop 为历史种群； $i \in \{ 1 , 2 \cdots N \}$ ，（204号 $j \in \{ 1 , 2 \cdots D \}$ ： $N$ 是种群个数； $D$ 是种群维数； $L o w$ 和 $\mathrm { U } p$ 分别为搜索空间的下界和上界； $U$ 为随机均匀分布函数。

2）选择I

BSA通过历史种群控制搜索方向，选择I的目的是在每次迭代开始时选择新的历史种群。选择策略如式(3)所示。

$$
i f a < b ~ t h e n ~ O l d p o p = P o p
$$

其中：a、b是（0,1）上服从均匀分布的随机数。在确定Oldpop之后，将Oldpop中种群的位置进行重新排列，公式如下：

$$
O l d p o p = \mathrm { r a n d p e r m } ( O l d p o p )
$$

其中：randperm是重新排序函数。

3）变异

BSA的变异方程如(5)所示。

$$
M = P o p + F \cdot ( O l d p o p - P o p )
$$

其中：F为变异尺度系数用以控制搜索方向矩阵(Oldpop-Pop)的幅度， $F = 3 *$ randn，randn 是一服从标准正态分布的随机数。

# 4）交叉

BSA 提出了一种新型的交叉策略，通过设置混合比例参数来控制种群粒子交叉个数。具体公式如式(6)所示。

$$
\pmb { T } _ { i , j } = \left\{ \begin{array} { l l } { \pmb { M } _ { i , j } , } & { \pmb { M } \pmb { a p } _ { i , j } = 1 } \\ { \pmb { P o p } _ { i , j } , } & { \pmb { M a p } _ { i , j } = 0 } \end{array} \right.
$$

其中： $M \pmb { a } _ { P _ { i , j } }$ 为 $N { \times } D$ 的二元整数矩阵；初始赋值为1。具体公式如式(7)如示。

$$
\left\{ \begin{array} { l l } { M a p _ { i , ( u \left[ 1 : \mathrm { m i x r a t e } \cdot \mathrm { r a n d } \cdot D \right] ) } = 0 , } & { a < b } \\ { M a p _ { i , r a n d i ( D ) } = 0 , } & { a \geq b } \end{array} \right.
$$

其中： $\operatorname { r a n d i } ( D )$ 为从 $[ 0 , D ]$ 中随机取一个整数，rand; $a , b$ 为[0,1]的随机数；mixrate为交叉概率；mixrate $\cdot \cdot$ rand · $D$ 为交叉长度;$u =$ randperm(D)，为 $[ 1 , 2 \cdots D ]$ 重新排序后的整数向量。BSA通过调用这两种等概率的Map产生方式，有效控制新种群 $_ { T }$ 中变异元素的个数。

在新种群T确定后，对种群中的元素进行边界检测，若超出搜索范围，则按式(1)产生新的个体。

# 5）选择ⅡI

通过贪婪法则在新种群与初始种群中选择适应度值较好的个体，并记录当前全局最优解和对应的解向量，同时更新初始种群。更新方程如式(8)所示。

$$
P o p _ { i } = \{ { \begin{array} { l l } { T _ { i } } & { f i t n e s s ( T _ { i } ) < f i t n e s s ( P o p _ { i } ) } \\ { P o p _ { i } } & { o t h e r w i s e } \end{array} }
$$

重复上述过程，直到满足终止条件，最后输出最优解。

# 2 BSA改进算法

BSA算法全局探索能力较强而局部开发能力稍显弱势，究其原因是该算法仅在历史种群的引导下进行变异，缺少最优个体的引导。针对这一特点，本文对变异及交叉方程进行了改进；另一方面，本文提出了算法进化率 $P$ ，引入差分进化变异因子，使算法后期种群多样化，避免算法陷入局部最优。本文将所提出的改进算法简记为MEBSA。

# 2.1变异尺度系数改进

原始 BSA 算法的变异尺度系数 $F = 3 ^ { * } r a n d n$ ，分布范围过广，容易产生较大或较小的极值，不利于种群的快速收敛。为此，本文提出了一种基于 $\mathrm { ~  ~ { ~ t ~ } ~ }$ 分布的变异尺度系数。其表达式为

$$
F = 2 * { \sqrt { \mathrm { t r n d } ( d f ) } }
$$

其中： $\operatorname { t r n d } ( d f )$ 是一服从 $\mathrm { ~  ~ \Omega ~ } _ { \mathrm { ~ t ~ } }$ 分布的随机数。

t分布只有一个参数，即自由度 $d f _ { \ l }$ ，其密度函数较于标准正态分布的密度函数表现为厚尾，且其形状随着df的增大而无限接近于正态分布。因此，相比于正态分布，通过自由度df，可以很方便地控制t分布的形状，且因其厚尾的特点，在整体分布趋势较为集中的基础上，也可以一定概率取到处于边界的极值，从而避免算法过分收敛，陷入局部最优。本文取 $d f { = } 1 0 .$ 基于t分布的变异尺度系数与原始系数绝对值比较，在不同区间的简要分布情况如表1所示。

表1各区间简要分布概率  

<html><body><table><tr><td>区间</td><td>(0,0.5)</td><td>(0.5,1)</td><td>(1,1.5)</td><td>(1.5,2)</td><td>(2,4)</td><td>>4</td></tr><tr><td>2 * trnd(df)</td><td>0.0487</td><td>0.1412</td><td>0.2229</td><td>0.2447</td><td></td><td>0.3404 0.0021</td></tr><tr><td>3 * randn</td><td>0.132</td><td>0.128</td><td>0.121</td><td>0.112</td><td>0.323</td><td>0.1824</td></tr></table></body></html>

由表1可以看出，与原始系数相比，新的变异系数产生的扰动较为集中，且不会产生过大的数值，加快了种群的收敛速度，一定程度上提高了算法的局部开发能力。

# 2.2 交叉方程改进

通过对BSA算法的分析可知，该算法因其独特的变异交叉操作，全局探索能力强，但因其仅在历史种群的引导下控制搜

索方向，导致该算法的收敛速度较慢，局部开发能力还不够强。针对这一缺点，本文算法引入最优个体的引导，提出了一个新的交叉方程，公式如式(10)(11)所示。

$$
\begin{array} { r } { T _ { i , j } ^ { { \mathrm { ~ ~ } } } = \left\{ \begin{array} { l l } { M _ { i , j } ^ { { \mathrm { ~ ~ } } + { C ( G p o p } _ { i , j } - P o p _ { i , j } ) , } } & { M a p _ { i , j } = 1 } \\ { P o p _ { i , j } ^ { { \mathrm { ~ ~ } } + { C ( G p o p } _ { i , j } - P o p _ { i , j } ) , } } & { M a p _ { i , j } = 0 } \end{array} \right. } \end{array}
$$

$$
G p o p = \mathrm { r e m p a t } ( ( \mathrm { n o r m r n d } ( 1 , 1 ) . * G m i n i m i z e r ) , N )
$$

其中： $C$ 为一服从标准正态分布的随机数；Gpop是一个 $N \times D$ 矩阵，矩阵元素由当前种群最优个体的正态分布组成。这样一来，BSA算法的交叉变异方程趋于完整，不仅有历史种群的引导，还有当前最优个体控制搜索方向。值得一提的是，本文没有直接采用当前全局最优个体引导，而是加上了正态分布的扰动，使算法在大大提高了收敛速度之外，也保证了全局探索能力。

# 2.3 进化选择机制

原始BSA算法在初期迭代中具有较好的探索能力，然而随着循环次数的增多，仍然面临着早熟收敛的问题，对于较复杂的多峰多极值函数，存在可能无法搜索到最优值的缺点。因此，本文提出了进化选择机制，引入算法进化率 $P$ ，设定每隔per代，计算一次 $P$ 。当 $P$ 小于所设阈值ε时，随机选取 $\varrho$ 个当前个体，引入差分进化算法变异算子DE/rand/1，产生 $\varrho$ 个新的个体，并替换掉当前种群及历史种群中的相应个体,以一定的概率将较差的解代替较优解，使算法中后期的种群更加多样化，避免早熟收敛。新个体产生公式如式(12)所示。

$$
N e w p o p _ { i } = p o p _ { \nu ( i ) } + W ( P o p _ { r 1 } - P o p _ { r 2 } )
$$

其中： $i \in \left\{ 1 , 2 , \cdots Q \right\}$ ， $\pmb { \nu } ( i ) = \pmb { c r } ( i )$ ， $c r =$ randperm $( N )$ ； $W$ 取[-1,1]的随机数； $r 1 \neq r 2 \in \left\{ 1 , 2 , \cdots N \right\}$ 且互不相同。本文算法设定 $p e r { = } 1 0 0$ ，$\varepsilon = 0 . 5$ ， $Q = \operatorname { c e i l } ( 0 . 3 * N )$ 。其中：ceil为向上取整函数。下面给出改进BSA算法的流程：

1 种群初始化  
2while 不满足算法停止条件do  
3 进行选择I，选取oldpop  
4 if rand<rand do  
5 （204 $M \pmb { a p } _ { i , ( u \lceil 1 : \mathrm { m i x r a t e } \cdot \mathrm { r a n d } \cdot D \rceil ) } = 0$ （20  
6 else  
7 $M \pmb { a } \pmb { p } _ { i , r a n d i ( D ) } = 0$ （204号  
8 end if  
9 按式(10)进行变异操作  
10 按式(6)进行交叉操作  
11 if $\scriptstyle P < \theta . 5$   
12 for i=1: ceil(0.3\*N)  
13 按式(12)产生新的个体，并替换  
14 end for  
15 end if  
16 进行选择II，更新Pop  
17 end while

18输出最优解

# 3 数值实验及结果分析

为了测试本文改进算法的效果，选取了15个测试函数进行数值实验，同时与标准BSA、BSA改进算法COBSA[13]、DS[14]、MABC 算法[15]以及CSO 算法进行了对比实验。表2给出了15个测试函数的名称、维数、搜索空间和最优

值[16,17]。其中，F1\~F7 是简单的单峰测试函数；F8\~F9 是多峰少极值函数；F10\~F15是多峰多极值函数。这些函数的局部极值个数随着函数维数的增加呈指数级增长，这类函数对大多数算法都是很难求解的。

表215个函数的简单描述  

<html><body><table><tr><td>函数</td><td>名称</td><td>维数</td><td>搜索空间</td><td>最优值</td></tr><tr><td>F1</td><td>Sphere</td><td>60</td><td>[-100,100]</td><td>0</td></tr><tr><td>F2</td><td>Schwefel 2.22</td><td>60</td><td>[-10,10]</td><td>0</td></tr><tr><td>F3</td><td>Sumsquare</td><td>60</td><td>[-10,10]</td><td>0</td></tr><tr><td>F4</td><td>Exponential</td><td>60</td><td>[-1.28,1.28]</td><td>0</td></tr><tr><td>F5</td><td>Schwefel 1.2</td><td>10</td><td>[-30,30]</td><td>0</td></tr><tr><td>F6</td><td>Elliptic</td><td>30</td><td>[-100,100]</td><td>0</td></tr><tr><td>F7</td><td>R-H-Ellipsoid</td><td>80</td><td>[-100,100]</td><td>0</td></tr><tr><td>F8</td><td>Zakharov</td><td>60</td><td>[-5,10]</td><td>0</td></tr><tr><td>F9</td><td>Salomon</td><td>60</td><td>[-100,100]</td><td>0</td></tr><tr><td>F10</td><td>Alpine</td><td>60</td><td>[-10,10]</td><td>0</td></tr><tr><td>F11</td><td>Rastrigin</td><td>100</td><td>[-100,100]</td><td>0</td></tr><tr><td>F12</td><td>Griewanlk</td><td>60</td><td>[-600,600]</td><td>0</td></tr><tr><td>F13</td><td>Schaffer</td><td>10</td><td>[-100,100]</td><td>0</td></tr><tr><td>F14</td><td>Weierstrass</td><td>60</td><td>[-0.5,0.5]</td><td>0</td></tr><tr><td>F15</td><td>NCRastrigin</td><td>50</td><td>[-5.12,5.12]</td><td>0</td></tr></table></body></html>

# 3.1停止条件制定及参数设定

（a）所求结果与测试函数的理论最优解绝对值之差小于Matlab系统最小正浮点数 $4 . 9 4 0 7 \mathrm { e } { - 3 2 4 }$ ，即eps（O）时，停止。

（b）达到最大进化代数epoch时，停止。

达到最大进化代数之前算法终止，则本次运行结果为成功。实验种群数目取60，epoch取50000。实验均在相同配置的计算机上，使用MATLAB2013b进行编程测试。

# 3.2 测试结果分析

针对同一测试函数，每种算法独立运行30次，比较六种算法对15个标准测试函数结果的统计平均值(mean）、方差（std）、平均迭代次数（miter）及成功率（srate）。测试结果如表3所示。从表3中可以看出，在30次的独立运行中，无论是在单峰测试函数、多峰少极值函数还是复杂的多峰多极值函数上，MEBSA都能达到预设精度，且迭代次数远远小于其他五种算法。充分证明了MEBSA不仅具有较快的收敛速度和强鲁棒性，还有较强的全局搜索性能，能够快速跳出局部最优，避免早熟收敛。

<html><body><table><tr><td colspan="2"></td><td colspan="2">表3</td><td colspan="4">六种算法对15个测试函数的测试结果</td></tr><tr><td></td><td>问题统计量</td><td>BSA</td><td>DS</td><td>CSO</td><td></td><td>COBSA</td><td>MABC MEBSA</td></tr><tr><td></td><td>mean 3.04e-158 9.12e-257</td><td></td><td></td><td></td><td></td><td>5.01e-16</td><td></td></tr><tr><td></td><td>std</td><td>9.02e-158</td><td>0</td><td></td><td>0</td><td>5.83e-17</td><td>0</td></tr><tr><td>F1</td><td>miter</td><td>50000</td><td>50000</td><td>23003</td><td>10538</td><td>50000</td><td>2356</td></tr><tr><td></td><td>srate</td><td>0</td><td></td><td></td><td></td><td>0</td><td></td></tr><tr><td></td><td>mean</td><td>2.22e-95 3.99e-143</td><td></td><td></td><td></td><td>8.51e-16</td><td></td></tr><tr><td>F2</td><td>std</td><td>3.70e-95 1.22e-142</td><td></td><td></td><td></td><td>1.10e-16</td><td>0 0</td></tr><tr><td></td><td>miter</td><td>50000</td><td>50000</td><td></td><td>13851 15496</td><td>50000</td><td>4045</td></tr><tr><td></td><td>srate</td><td>0</td><td>0</td><td></td><td></td><td>0</td><td></td></tr><tr><td></td><td>mean</td><td>1.56e-158 1.69e-257</td><td></td><td></td><td></td><td>5.19e-16</td><td></td></tr><tr><td>F3</td><td>std</td><td>5.08e-158</td><td>0</td><td></td><td></td><td>6.46e-17</td><td>0 0</td></tr><tr><td></td><td>miter</td><td>50000</td><td>50000</td><td></td><td>20375</td><td>50000</td><td>2158</td></tr><tr><td></td><td>srate</td><td>0</td><td>0</td><td></td><td>10452</td><td>0</td><td>1</td></tr><tr><td></td><td>mean</td><td></td><td>1.44e-96 6.27e-145</td><td></td><td></td><td>648.6356</td><td>0</td></tr><tr><td>F4</td><td>std</td><td></td><td>2.39e-96 2.89e-144</td><td></td><td></td><td>44.0127</td><td>0</td></tr><tr><td></td><td>miter</td><td></td><td>50000</td><td></td><td>15347</td><td>50000</td><td>4082</td></tr><tr><td></td><td>srate</td><td>50000</td><td>0</td><td>13845</td><td></td><td>0</td><td>1</td></tr><tr><td></td><td>mean</td><td>0</td><td>0.0086</td><td>1 1.46e+03</td><td>1 0</td><td>2.4568e+03</td><td>0</td></tr><tr><td>F5</td><td>std</td><td>0.0020</td><td>0.0094</td><td>505.9816</td><td>0</td><td>299.1724</td><td>0</td></tr><tr><td></td><td></td><td>0.0014</td><td>50000</td><td>50000</td><td>27097</td><td>50000</td><td>3924</td></tr><tr><td></td><td>miter</td><td>50000</td><td>0</td><td></td><td>1</td><td>0</td><td>1</td></tr><tr><td></td><td>srate</td><td>0</td><td>0</td><td>0 0</td><td>0</td><td>8.11e-16</td><td>0</td></tr><tr><td></td><td>mean</td><td>0</td><td>0</td><td>0</td><td>0</td><td>8.60e-17</td><td>0</td></tr><tr><td>F6</td><td>std</td><td>0</td><td>38504</td><td>6752</td><td>10521</td><td>50000</td><td>2510</td></tr><tr><td></td><td>miter</td><td>48359</td><td>1</td><td></td><td></td><td>0</td><td>1</td></tr><tr><td></td><td>srate</td><td>1</td><td></td><td>1 0</td><td>1 0</td><td>5.23e-16</td><td>0</td></tr><tr><td></td><td>mean</td><td>1.85e-158 5.22e-256</td><td>0</td><td>0</td><td>0</td><td>6.84e-17</td><td>0</td></tr><tr><td>F7</td><td>std</td><td>9.33e-158</td><td>50000</td><td>16510</td><td>11087</td><td>50000</td><td>2204</td></tr><tr><td></td><td>miter</td><td>50000</td><td>0</td><td>0.8</td><td>1</td><td>0</td><td>1</td></tr><tr><td></td><td>srate mean</td><td>0</td><td>2.67e-06</td><td>0.85</td><td>2.48e-211</td><td>8.87e-16</td><td>0</td></tr><tr><td>F8</td><td>std</td><td>1.07e-05</td><td>1.44e-06</td><td>2.69</td><td>0</td><td>1.32e-16</td><td>0</td></tr><tr><td></td><td>miter</td><td>1.12e-05 50000</td><td>50000</td><td>50000</td><td>50000</td><td>50000</td><td>3825</td></tr><tr><td></td><td>srate</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td></td><td>mean</td><td>0.6632</td><td>0.3699</td><td>0.2409</td><td>0.0999</td><td>2.4199</td><td>0</td></tr><tr><td>F9</td><td>std</td><td>0.1129</td><td>0.0535</td><td>0.0555</td><td>2.31e-12</td><td>0.1375</td><td>0</td></tr><tr><td></td><td>miter</td><td>50000</td><td>50000</td><td>50000</td><td>50000</td><td>50000</td><td>2277</td></tr><tr><td></td><td>srate</td><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td><td>1</td></tr><tr><td></td><td>mean</td><td>2.45e-13</td><td>9.84e-52</td><td>0.0095</td><td>0</td><td>1.77e-15</td><td>0</td></tr><tr><td>F10</td><td></td><td></td><td>5.15e-51</td><td>0.0153</td><td>0</td><td>1.47e-15</td><td>0</td></tr><tr><td></td><td>std</td><td>1.32e-12</td><td>50000</td><td>30202</td><td>15461</td><td>50000</td><td>4121</td></tr><tr><td></td><td>miter</td><td>50000</td><td>0</td><td>0.57</td><td>1</td><td>0</td><td>1</td></tr><tr><td></td><td>srate</td><td>0</td><td>0.1658</td><td>24.5163</td><td>0</td><td>0</td><td>0</td></tr><tr><td></td><td>mean</td><td>0.0995</td><td>0.3771</td><td>94.3434</td><td>0</td><td>0</td><td>0</td></tr><tr><td>F11</td><td>std</td><td>0.3036</td><td>13523</td><td>10757</td><td>661</td><td>9703</td><td>158</td></tr><tr><td></td><td>miter</td><td>33252</td><td>0.83</td><td>0.83</td><td>1</td><td>1</td><td>1</td></tr><tr><td></td><td>srate</td><td>0.5</td><td>0</td><td>1.11e-17</td><td>0</td><td>1.07e-16</td><td>0</td></tr><tr><td></td><td>mean</td><td>2.47e-04</td><td>0</td><td>3.39e-17</td><td>0</td><td>1.07e-16</td><td>0</td></tr><tr><td>F12</td><td>std</td><td>0.0014</td><td>3864</td><td>9803</td><td>698</td><td>40922</td><td>165</td></tr><tr><td></td><td>miter srate</td><td>7379 0.97</td></table></body></html>

为了进一步直观说明MEBSA算法的先进性，图1\~4给出了典型的四种测试函数的收敛曲线。其中横坐标为迭代次数，纵坐标为函数值。(注：为了方便进化曲线的显示和观察,本文对函数值取以10为底的对数)。

![](images/d126b7860133caa7aafdde632f14a17e2ae12c93f68a33d96baafb9dffa6a606.jpg)  
图1F3函数的收敛曲线

![](images/09030663cb6dddf3728b7c7305780d967c37c8a435fdd03a19d4186c5121e454.jpg)  
图2F6函数的收敛曲线

![](images/c34e18244522ed6dadb8ccb74e73d097dae810aadff5daad2bfaac9db987c7de.jpg)  
图3F8函数的收敛曲线

![](images/64410121810c2e28240f2bf709bbd0291bf0a49509ded50eb44e33b267d9a548.jpg)  
图4F10函数的收敛曲线

结合图表可以看出，针对F3、F6、F10等其他五种算法也能部分成功运行的函数，MEBSA能以最少的迭代次数以及最快的收敛速度达到预设精度；针对F8、F9 等其他五种算法均不能成功的函数，MEBSA依然能以较快速度成功收敛。进一步展示了MEBSA算法的优越性。

# 4 结束语

为了解决标准 BSA 算法收敛速度相对较慢及搜索精度不高的问题，本文提出了新的变异尺度系数F，并加入最优个体的引导，构造了一个新的交叉方程；同时，为了防止算法陷入局部最优，提出了进化选择机制，引入差分进化变异算子。最后，选取15个测试函数，并与五种算法进行了对比。结果表明，本文改进算法MEBSA有效提高了算法的各项搜索性能。

# 参考文献：

[1]Holland JH.Adaptation in natural and artificial systems [M].[S.1.] : Ann Arbor.University ofMichigan Press,1975.   
[2]Eberhart R,Kennedy J.A new optimizer using particle swarm theory [C]// Proc of Micro Machine and Human Science.Washington DC:IEEE Computer Society,1995:39-43.   
[3]Storn R,Price K.Differential evolution: a simple and efficient heuristic for global optimization over continuous spaces [J]．Journal of Global Optimization,1997,11 (4): 341-359.   
[4]Karboga D,Basturk B.A powerful and efficient algorithm for numerical function optimization: artificial bee colony (ABC)algorithm[J].Journal of Global Optimization,2007,39 (3): 459-471.   
[5]Zhu Guopu,Kwong S.Gbest-guided artificial bee colony algorithm for numerical function optimization[J].Applied Mathematics & Computation, 2010,217(7):3166-3173.   
[6]李文斌，陈嶷瑛，贺毅朝，等．邻域结构为复杂网络的差分演化算法 [J].计算机应用研究,2016,33(2):370-374.   
[7]姜凤利，张宇，王永刚，等．一种基于引导策略的自适应粒子群优化算 法[J].计算机应用研究,2017,34(12):3599-3602.   
[8]Meng Xianbing,Liu Yu, Gao Xiaozhi,et al.A new bio-inspired algorithm: chicken swarm optimization [C]// Proc of International Conference on Swarm Intelligence.Hefei: Springer International Publishing,2O14: 86-94   
[9]Zheng Yujun.Water wave optimization: a new nature-inspired metaheuristic [J].Computers and Operations Research,2015,55: 1-11.   
[10]高江锦，杨韬．免疫进化否定选择算法[J].计算机应用研究,2017,34 (5): 1293-1297.   
[11] Civicioglu P. Backtracking search optimization algorithm for numerical optimization problems [J].Applied Mathematics and Computation,2013, 219 (15): 8121-8144.   
[12]田文凯，刘三阳，王晓娟．基于差分进化的回溯搜索优化算法研究与改 进[J].计算机应用研究,2015,32(6):1653-1656.   
[13] Zhao Lei,Jia Zhicheng,Chen Lei,et al. Improved backtracking search algorithm based on population control factor and optimal learning strategy [J].Mathematical Problems in Engineering,2017,5(1): 26-36.   
[14] Civicioglu P. Transforming geocentric cartesian coordinates to geodetic coordinates by using diffrential search algorithm [J].Computers and Geosciences,2012,46 (3): 229-247.   
[15] Gao Weifeng,Liu Sanyang.A modified artificial bee colony algorithm [J]. Computers and Operations Research,2012,39 (3): 687-697.   
[16] Liang Jing, Qin A K, Suganthan PN,et al. Comprehensive learning particle swarm optimizer for global optimization of multimodal functions [J].IEEE Trans on Evolutionary Computation,2006,10 (3):281-295.   
[17] Karaboga D,Akay B.Acomparative study of artificial bee colony algorithm [J].Applied Mathematics and Computation,2009,214 (1): 108-132.