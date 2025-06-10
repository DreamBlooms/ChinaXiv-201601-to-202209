# 一种求解动态优化问题的免疫文化基因算法

杨洲¹，袁亦川¹，罗廷兴²，秦进1(1．贵州大学 计算机科学与技术学院，贵阳 550025;2.贵阳市信息产业发展中心，贵阳 550081)

摘要：针对传统免疫网络动态优化算法局部寻优能力弱、寻优精度低及易早熟收敛的缺点，提出一种求解动态优化问题的免疫文化基因算法。基于文化基因算法基本框架，将人工免疫网络算法作为全局搜索算法，采用禁忌搜索算法作为局部搜索算子；同时引入柯西变异加强算法的全局搜索能力，并有效防止早熟收敛。通过对经典动态优化函数测试集在相同条件下的实验表明，该免疫文化基因算法相较于其他同类算法具有较好的搜索精度和收敛速度。

关键词：动态优化；人工免疫；禁忌搜索；柯西变异 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2018.03.0165

# Immune-based memetic algorithm for dynamic optimization problems

Yang Zhou1, Yuan Yichuan1,Luo Tingxing², Qin Jin1 (1.CollgeofComputerScience &Technology Guizhou University,Guiyang 55o25,China;2.Guiyang InformationIndustry Development Center, Guiyang 550081,China)

Abstract:The traditional immune networkoptimizationalgorithmhas the shortcomingsofweak local searching ability,low precisionand prematureconvergence.Inorder to improve thealgorithmperformance,this paperproposedanartificial-immunenetwork-based memetic algorithm for dynamic optimization problems.Basedon the framework of memetic algorithm,an artificialimmune networkalgorithmservesastheglobalsearchalgorithm,andatabusearchalgorithmserveasthelocalearch operator. Atthe same time,the algorithm introduced the Cauchy variation to improve global searching abilityand prevent prematureconvergence.The experimentalresults showthat the improved algorithmhasbeter search precision and convergence speed compared with other algorithms.

Key words:dynamic optimization;artificial immune; tabu search; Cauchy mutation

# 0 引言

$$
D O P = { \left\{ \begin{array} { l l } { o p t i m i z e \quad f ( x , t ) } \\ { s . t . \quad x \in X ( t ) \subseteq S , t \in T } \end{array} \right. }
$$

在现实世界中，许多优化问题往往具有动态变化的性质。例如调度问题中，新任务的不断到达，产品原材料质量的不断变化，机器随时间增加的不断磨损以及随时可能发生的故障等。也就是说，动态优化问题中某些目标或条件随着时间不断发生着变化，某个时刻最坏的选择在下一时刻有可能会变好，而有些条件本来无关紧要却突然变得重要。社会变化日新月异，动态优化问题所涉及领域已经扩大到包含几乎所有工程、科学、经济和生活方面的问题。因此，对于动态优化问题及其解决方法的研究越来越受到研究人员的关注错误!未找到引用源。。

在目前的研究中，动态优化问题通常被视做一系列静态优化问题的组合，其动态性主要表现在环境变化的频率以及环境变化的剧烈程度。动态优化问题错误!未找到引用源。可以定义如下：

$s$ 表示搜索空间， $t$ 表示时间， $f$ 表示目标函数， $x$ 为可行解， $X ( t )$ 是在 $t$ 时间的可行解集合， $f ( x , t )$ 表示在 $t$ 时刻候选解的目标函数值。

动态优化问题与静态优化问题的区别在于静态优化问题只需要算法收敛到全局最优值即可，而动态优化问题不仅需要算法找到每个时刻的全局最优值，而且还需要具备快速追踪随时变化的最优解的能力，这就要求动态优化算法兼具快速收敛和保持多样性的能力错误!未找到引用源。目前，解决动态优化问题的算法主要包括进化算法和群智能算法两类。进化算法是基于生物进化机制的一类优化算法。传统进化算法通常用于求解静态优化问题，研究者通过加入多样性、记忆机制、预测机制、多种群等策略，将其改进为求解动态优化问题的进化算法。群智能算法是模仿生物群体的行为和相互间作用的一类优化算法，包括蚁群优化算法错误！未找到引用源。、粒子群优化算法错误!未找到引用源。、萤火虫优化算法错误！未找到引用源。、鱼群优化算法错误！未找到引用源。等。伴随发展，其衍生出一些新颖的启发式算法。例如，近年提出的烟花算法就是受到烟花爆炸的启发错误!未找到引用源。。人工免疫系统是模仿生物免疫系统功能的一类智能方法，广泛应用于优化、故障诊断、控制等领域。人工免疫算法的记忆机制、克隆变异和网络交互等特点使其在优化方面相较于传统优化算法效果更好。人工免疫算法可改进范围十分广泛，可以引入不同机制或与其他算法结合。例如，Liu等人提出一种用于求解多峰函数优化的协同人工免疫网络算法(CoAIN)错误!未找到引用源。，通过借鉴粒子群算法的协作性，使网络中个体不仅相互抑制，而且相互合作，从而提高算法搜索能力。赵辉等人提出一种基于分布式精英进化模型的人工蜂群免疫算法错误!未找到引用源。，结合蜂群思想和免疫克隆选择算法，克服传统人工蜂群算法收敛速度慢、搜索精度低等缺点。

文化基因算法(memeticalgorithm,MA)是近些年演化计算领域的一个研究热点，其将全局搜索与局域搜索结合的思想有利于平衡动态优化算法探索与开发间的关系。因此，本文将在已有研究的基础之上，提出一种免疫文化基因动态优化算法。算法针对传统人工免疫网络算法求解动态优化问题中出现的寻优精度低、收敛速度慢以及后期可能出现的早熟收敛等缺点，在算法寻优到一定程度时，利用禁忌搜索良好的爬山能力在当前最优解邻域内进行搜索，提高算法的搜索精度，并防止算法因陷入局部最优而停滞。同时，引入柯西变异算子和原有高斯变异算子切换使用，提高算法全局寻优能力。通过对函数集的实验仿真验证所提出的免疫文化基因动态优化算法的性能。

# 1 相关研究

# 1.1dopt-aiNet算法

人工免疫网络算法基于生物免疫系统的信息处理机制发展起来，主要涉及细胞克隆选择、细胞变异、免疫细胞网络等免疫学原理。人工免疫网络算法刚刚出现时主要用于解决信息压缩和数据聚类。2002年，Castro 等人首次利用人工免疫网络算法求解优化问题，提出人工免疫网络优化算法(opt-aiNet)错误!未找到引用源。之后，又在opt-aiNet 的基础上进行改进，提出人工免疫网络动态优化算法(dopt-aiNet)错误！未找到引用源。。并在 2009 年参加CEC 举办的动态优化竞赛，在求解动态优化问题上表现出良好性能错误!未找到引用源。

dopt-aiNet算法模仿生物免疫细胞发现外来抗原，识别抗原，刺激免疫细胞克隆扩增并产生抗体消灭抗原的免疫过程。其具体流程如下所示：

a)初始化种群,生成初始细胞种群，并计算细胞个体适应度;b)细胞克隆,对每个细胞个体进行克隆扩增；c)细胞突变,对克隆细胞个体进行高斯变异；d)精英选择,在每组变异后的细胞个体中选择适应度值最高的细胞个体留下；e)细胞抑制判断,判断细胞种群是否达到抑制条件，若达到

条件，继续，否则转入h);

f)细胞抑制,抑制距离小于设定值的两细胞个体中适应度低 的细胞个体;

g)引入新细胞：按比例随机产生新细胞个体加入当前细胞种群中;

h)终止条件判断：判断当前是否达到终止条件，若达到终止条件，输出结果，否则，转入b)。

# 1.2禁忌搜索算法

禁忌搜索算法(tabu search,TS)是一种元启发式搜索算法错误！未找到引用源。，通过模仿人类的记忆功能，使用禁忌表来封锁刚刚搜索过的区域来避免迁回搜索，从而使算法能够跳出局部极值。相比其他传统优化算法，禁忌搜索算法具有更强的“爬山”能力和局部搜索能力。禁忌搜索算法在旅行商问题、0-1背包问题等组合优化问题上已有十分广泛的应用，近年来许多学者也尝试将其运用于函数优化问题的求解。

禁忌搜索算法其本质是一种优秀的邻域搜索算法，具有很快的收敛速度。但其收敛速度的快慢和寻优结果的优劣很大程度上取决于初始解的好坏，好的初始解往往能够帮助算法快速收敛到全局最优解，而差的初始解将可能大大降低算法收敛速度。禁忌搜索算法的关键在于邻域的选取、禁忌表的设计以及特赦准则。邻域体现局部搜索思想，禁忌表体现算法避免迁回搜索的特点，特赦准则是对优秀解的一种反馈。禁忌搜索算法的基本思路主要是搜索当前一个解的邻域，如果解邻域内的最优解优于当前解，将当前解替换为该解邻域内的最优解，并继续在当前解的邻域内进行搜索，直到算法终止。TS算法流程可分为以下几个步骤：

a)初始化参数：给定初始解 $X _ { \mathfrak { o } }$ ，计算目标函数值 $f ( X _ { 0 } )$ ，并将初始解赋值给当前解 $X = X _ { \mathrm { o } }$ ：

b)生成邻域和候选解集：生成当前解 $X$ 的邻域 $N ( X )$ ，从中选出一定数量的解作为候选解集合，并计算所有候选解的目标函数值；

c)判断是否满足邻域搜索条件：如果候选解集合不空并且未选出最优解Y，继续，否则直接转入e);

d)判断禁忌准则：从候选解集合中找到最优解 $Y$ ，如果Y不在禁忌表中，将 $Y$ 赋值给当前最优解，否则，将其从当前解邻域中删除，转入c);

e)禁忌表更新：如果找到最优解Y，将当前解 $X$ 插入禁忌表，并赋值 $X = Y$ ：

f)判断结束：如果满足结束条件，则终止计算，否则转入b)。

# 2 免疫文化基因动态优化算法

文化基因算法是基于Darwinian的自然进化理论和Darkins的文化进化思想产生的一种混合算法框架错误!未找到引用源。算法将进化算法和某些局域搜索方法结合在一起，进化算法负责执行全局搜索，局部搜索策略用于改善某些个体的搜索精度，从而使算法在探索和开发间保持平衡。

# 2.1算法思想

人工免疫网络算法(dopt-aiNet)在求解动态优化问题时，主要通过初始化、克隆扩张、高频变异、精英选择等操作来优化候选解，最终找到问题的解，并且通过抑制机制和抑制之后引入新个体的方式维持解决动态优化问题所必须的种群多样性。算法种群个体广泛分布在解空间各个区域往往能体现良好的全局搜索能力，但当算法寻优到一定程度时，容易出现寻优能力不足，导致早熟收敛，一定程度上影响了算法的寻优精度。针对dopt-aiNet算法求解动态优化问题存在的不足，本文基于文化基因算法思想提出解决动态优化问题的免疫文化基因算法(artificial immune network based memetic algorithm,AINMA)。利用禁忌搜索的局部搜索优势，结合人工免疫网络算法全局搜索能力强的特点，通过在细胞抑制之后引入禁忌搜索，人工免疫网络为禁忌搜索提供好的初始解，提高算法的搜索精度。此外，引入柯西变异算子与传统高斯变异算子结合变异，寻优前期使用柯西变异保证更大限度的搜索整个解空间，寻优后期使用高斯变异算子保证算法搜索精度。同时，改进算法采用设立侦测细胞的方式侦测环境变化，侦测种群在每次迭代之后计算适应度，如果适应度发生变化即环境发生改变，引导寻优种群重新开始搜寻新的最优值。

# 2.2 柯西变异算子

传统高斯变异算子是对个体 $X _ { _ i } = ( x _ { _ i 1 } , x _ { _ i 2 } , \cdots , x _ { _ { i n } } )$ 按照式(2)进行操作。

$$
x _ { _ { i j } } = x _ { _ { i j } } + \eta * G ( 0 , 1 )
$$

其中: $\eta$ 为控制变异步长的常数， $G ( 0 , 1 )$ 是均值为0，偏差为1的高斯分布函数产生的随机数。

柯西变异算子是对个体 $X _ { _ i } = ( x _ { _ { i 1 } } , x _ { _ { i 2 } } , \cdots , x _ { _ { i n } } )$ 按照公式(3)进行操作。

$$
x _ { _ { i j } } = x _ { _ { i j } } + \eta * C ( 0 , 1 )
$$

其中: $\eta$ 为控制变异步长的常数， $C ( 0 , 1 )$ 是由 $t = 1$ 的柯西分布函数产生的随机数。

比较高斯密度函数和柯西密度函数可知，柯西密度函数两端尾巴比高斯密度函数更长，这就使得由柯西变异产生的变异子代与父代差异更大，个体则有更大几率跳出局部最优，因此，柯西变异往往比高斯变异具有更好的全局搜索能力。本文将两种变异方式结合使用，在算法寻优前期，使用柯西变异能够防正寻优个体陷入局部最优导致算法提前停滞，当算法满足抑制条件进入抑制过程，也就是说寻优已经到达一定程度，可能十分靠近全局最优，此时使用高斯变异防止过度变异导致寻优个体远离全局最优值。

# 2.3禁忌表、邻域与特赦准则

本文将禁忌搜索融合于dopt-aiNet 算法中，利用免疫算法克隆、变异、选择等操作为禁忌搜索提供一个较好的初始解，再通过禁忌搜索作为局部搜索工具提高整个算法的寻优精度。以下是对AINMA算法中禁忌表、邻域和特赦准则的简要介绍：

禁忌表是禁忌搜索算法的核心，在AINMA算法中用来存放最近访问过的邻域候选解，从而防止迁回搜索，也可以避免算法陷入局部最优。

禁忌搜索中特赦准则的设立是为了防止错过优良解。在AINMA算法中，当某个邻域候选解的适应度优于历史最优解，无论这个候选解是否在禁忌表中，都接受这个候选解。

禁忌搜索中，邻域的划分十分关键。不同于组合优化问题，函数优化问题的解空间是连续的，因此，本文采用文献错误！未找到引用源。中提及的邻域划分方式选取邻域解。

将动态优化问题中单个静态优化问题用如式(4)的模型表示：

$$
\operatorname* { m i n } f ( X ) \quad s . t . \quad L \leq X \leq U
$$

其中： $X$ 为 $n$ 维变量， $X = ( x _ { 1 } , x _ { 2 } , \cdots , x _ { n } )$ ，对应分变量的上下限分别为 $L = ( l _ { 1 } , l _ { 2 } , \cdots , l _ { n } ) , U = ( u _ { 1 } , u _ { 2 } , \cdots , u _ { n } )$ 9

用同心超矩阵将当前解的分量 $x _ { j } ( j = 1 , \cdots , n )$ 分成 $k$ 个空间。每个空间按式(5)划分。

$$
\begin{array} { r l } & { R _ { i } ( x , r _ { i - 1 } , r _ { i } ) = \{ x ^ { \prime } \mid r _ { i - 1 , j } \leq \left| x _ { j } ^ { \prime } - x _ { j } \right| < r _ { i , j } \} } \\ & { l < x _ { j } ^ { \prime } < u _ { j } , j = 1 , 2 , \cdots , n , i = 1 , 2 , \cdots , k } \\ & { r _ { i } = r _ { i - 1 } * 2 , i = 1 , 2 , \cdots , k } \\ & { R _ { 0 } ( x , r _ { 0 } ) = \{ x ^ { \prime } \mid \left| x _ { j } ^ { \prime } - x _ { j } \right| < r _ { 0 } \} } \\ & { l < x _ { j } ^ { \prime } < u _ { j } , j = 1 , 2 , \cdots , n } \end{array}
$$

在 $R _ { i }$ 的每个同心矩形内随机选取一个点，选出的 $k$ 个点组成当前解分量 $\boldsymbol { x } _ { j }$ 的邻域候选解 $\{ x _ { 1 } ^ { \prime } , x _ { 2 } ^ { \prime } , \cdots , x _ { k } ^ { \prime } \}$ 。

# 2.4算法流程

AINMA算法可分为以下几个步骤：

a)初始化种群：生成寻优种群和侦测种群，并设置相应参 数值;

b)克隆：寻优种群个体克隆扩张;

c)变异：对每个克隆个体进行高频突变，如果变异标志为0，选用柯西变异算子进行突变，否则选用高斯变异算子进行突变，并计算变异个体的适应度值；

d)选择：在每组变异个体中选择适应度大的个体留下；

e)抑制判断：判断是否达到抑制条件，若达到条件，继续，否则转入i);

f)抑制：变异标志设置为1，抑制距离小于设定值的两个体 中适应度低的个体;

g)禁忌搜索：生成当前最优解的邻域和候选解集合，在候选解集中寻找最优解，并不断更新禁忌表，重复该搜索过程直到满足结束条件；

h)引入随机个体：随机产生新个体加入当前寻优种群中；

i)侦测环境变化：利用侦测种群侦测环境是否发生变化，若发生变化，将变异标志设置为0，否则，继续;

j)停止判断：判断当前是否达到停止条件，若达到停止条件，输出结果，否则，转入b)。

AINMA算法流程图如图1所示。

![](images/e255c3f7ebb8bf099238543d28efe0b63599340ab799cea9c3f329af590c43ac.jpg)  
图1AINMA算法流程图

# 3 实验与分析

# 3.1实验设置

为了验证本文提出的免疫文化基因动态优化算法的性能，采用文献错误！未找到引用源。中提出的generalizeddynamicbenchmark generator(GDBG)函数测试集进行仿真测试。GDBG函数测试集包含6种测试函数类型，每种测试函数对应7种改变类型，包括小幅改变、大幅改变、随机改变、混沌改变、周期性改变、周期带噪声改变和维度改变。该动态函数测试集由表1所示5种函数通过旋转、组合形成以下6类不同难度的问题：

F1: rotation peak function(with 10 and 50 peaks) F2:composition of Sphere's function F3: composition of Rastrigin's function F4:composition of Griewank's function F5:composition of Ackley's function F6: hybrid composition function F1是最大值优化问题，F2-F6是最小值优化问

F1分为两种测试函数，一种带有10个峰，另一种带有50个峰。

表1GDBG基础组成函数表达式  

<html><body><table><tr><td>name</td><td>function</td><td>range</td></tr><tr><td>Sphere</td><td>f（x)=∑x²</td><td>[-100,100]</td></tr><tr><td>Rastrigin</td><td>f(x)=∑"(x² -10cos(2πx)+10)</td><td>[-5,5]</td></tr><tr><td>Weierstrass</td><td>f(x)=∑"-1(∑[a cos(2πb²(xi +0.5))D-n∑[a² cos(πb)] k=0 a = 0.5,b=3,kmax = 20</td><td>[-0.5,0.5]</td></tr><tr><td>Griewank</td><td>1 f(x)= Vi 4000(x）-II.cos)+1</td><td>[-100,100]</td></tr><tr><td>Ackley</td><td>f(x)=-20exp(-0.2√≥x²)-exp(∑cos(2πx))+ 20+e</td><td>[-32,32]</td></tr></table></body></html>

本文选择使用误差均值(Average mean)作为算法性能评价指标。计算方式如式(6)所示。

$$
m e a n = \sum _ { i = 1 } ^ { n u n s } \sum _ { j = 1 } ^ { n u n g e } E _ { i , j } ^ { l a s t } \left( t \right) / \left( { r u n s ^ { \ast } n u m } _ { - } c h a n g e \right)
$$

其中：runs表示算法独立运行的次数，num_change表示每种改变发生的次数， $E _ { i , j } ^ { l a s t } ( t )$ 表示算法在第 $i$ 次独立运行中第$j$ 次改变时的适应度绝对误差值，如式(7)所示。

$$
E ^ { l a s t } ( t ) = \left| f ( x _ { b e s t } ( t ) ) - f ( x ^ { * } ( t ) ) \right|
$$

其中： $f ( x _ { b e s t } ( t ) )$ 和 $f ( x ^ { * } ( t ) )$ 分别表示算法寻得最优值和理论最优值。

实验中，测试函数的参数设置包括维度 $d = 1 0$ ，变化范围$d \in [ 5 , 1 5 ]$ ；搜索范围 $x \in [ - 5 , 5 ] ^ { n }$ ；改变频率 $f r e = 1 0 0 0 0 ^ { \ast } d$ ；改变次数 $n u m _ { - } c h a n g e = 6 0$ ；变化周期 $p e r i o d = 1 2$ 。算法的参数设置包括：种群规模 $N = 1 0$ ；克隆规模 $C = 3$ ；抑制阈值$\zeta = 5$ ；变异步长 $\eta = 1$ 。

# 3.2 结果与分析

为验证本文提出的免疫文化基因算法(AINMA)的性能，利用基本人工免疫网络动态优化算法(dopt-aiNet)、粒子群动态优化算法(CPSO)、变量重定位正交粒子群算法(OLPSO-VRS)、免疫文化基因算法(AINMA)以及不含禁忌搜索的免疫文化基因算法(AINMAwithoutTS)对GDBG动态函数测试集进行了相同条件下的仿真实验。实验结果对每个测试函数进行5次独立测

试后平均得出。仿真结果如表2所示，表中数据均以科学计数表示，并将4种算法在每种情况下的误差均值最小值进行加粗。表 2 AINMA、AINMA(without TS)、dopt-aiNet、CPSO、OLPSO-VRS 对 GDBG 的误差均值对比  

<html><body><table><tr><td>Func.</td><td>Algorithm</td><td>T1</td><td>T2</td><td>T3</td><td>T4</td><td>T5</td><td>T6</td><td>T7</td></tr><tr><td rowspan="5">F1(10p eaks)</td><td>AINMA</td><td>2.76e-04</td><td>2.45e+00</td><td>2.75e+00</td><td>5.91e-04</td><td>1.91e+00</td><td>1.38e-01</td><td>2.29e+00</td></tr><tr><td>AINMA(without TS)</td><td>5.81e-04</td><td>2.45e+00</td><td>2.97e+00</td><td>1.15e-03</td><td>2.26e+00</td><td>6.49e-01</td><td>3.17e+00</td></tr><tr><td>dopt-aiNet</td><td>1.72e-01</td><td>4.57e+00</td><td>5.03e+00</td><td>6.34e+00</td><td>5.84e+00</td><td>1.03e+01</td><td>3.93e+00</td></tr><tr><td>CPSO</td><td>4.78e-02</td><td>2.48e+00</td><td>4.69e+00</td><td>6.48e-02</td><td>1.39e+00</td><td>1.34e+00</td><td>3.78e+00</td></tr><tr><td>OLPSO-VRS</td><td>2.08e-02</td><td>2.36e+00</td><td>3.57e+00</td><td>9.73e-02</td><td>1.36e+00</td><td>1.27e+00</td><td>3.54e+00</td></tr><tr><td rowspan="5">F1(50p eaks)</td><td>AINMA</td><td>2.90e-04</td><td>1.47e+00</td><td>2.77e+00</td><td>1.07e-01</td><td>7.04e-01</td><td>2.86e-01</td><td>1.71e+00</td></tr><tr><td>AINMA(without TS)</td><td>5.76e-04</td><td>1.49e+00</td><td>3.59e+00</td><td>5.18e-01</td><td>7.75e-01</td><td>4.72e-01</td><td>2.31e+00</td></tr><tr><td>dopt-aiNet</td><td>4.58e-01</td><td>4.41e+00</td><td>4.98e+00</td><td>3.09e+00</td><td>3.28e+00</td><td>5.94e+00</td><td>4.12e+00</td></tr><tr><td>CPSO</td><td>3.74e-01</td><td>4.16e+00</td><td>4.84e+00</td><td>3.13e-01</td><td>2.01e+00</td><td>1.63e+00</td><td>3.77e+00</td></tr><tr><td>OLPSO-VRS</td><td>1.91e-01</td><td>3.35e+00</td><td>3.87e+00</td><td>1.27e-01</td><td>1.36e+00</td><td>9.34e-01</td><td>3.77e+00</td></tr><tr><td rowspan="5">F2</td><td>AINMA</td><td>2.94e-03</td><td>2.28e+01</td><td>2.21e+00</td><td>2.94e-03</td><td>3.46e+00</td><td>2.27e-01</td><td>7.76e-01</td></tr><tr><td>AINMA(without TS)</td><td>5.76e-03</td><td>2.85e+01</td><td>8.11e+00</td><td>2.15e-01</td><td>6.20e+00</td><td>3.27e-01</td><td>7.92e-01</td></tr><tr><td>dopt-aiNet</td><td>9.37e-01</td><td>1.08e+01</td><td>2.02e+01</td><td>1.86e+00</td><td>9.87e+01</td><td>5.99e+00</td><td>4.19e+00</td></tr><tr><td>CPSO</td><td>1.17e+00</td><td>1.24e+01</td><td>8.54e+00</td><td>6.05e-01</td><td>2.37e+01</td><td>1.69e+00</td><td>4.12e+00</td></tr><tr><td>OLPSO-VRS</td><td>8.82e-01</td><td>1.08e+01</td><td>8.28e+00</td><td>6.69e-01</td><td>1.66e+01</td><td>1.10e+00</td><td>2.03e+00</td></tr><tr><td rowspan="5">F3</td><td>AINMA</td><td>1.35e+01</td><td>8.43e+02</td><td>8.47e+02</td><td>4.53e+02</td><td>8.01e+02</td><td>6.04e+02</td><td>5.26e+02</td></tr><tr><td>AINMA(without TS)</td><td>2.16e+01</td><td>8.58e+02</td><td>8.91e+02</td><td>4.54e+02</td><td>8.02e+02</td><td>6.51e+02</td><td>5.26e+02</td></tr><tr><td>dopt-aiNet</td><td>7.65e+02</td><td>1.01e+03</td><td>1.00e+03</td><td>1.10e+03</td><td>1.04e+03</td><td>1.29e+03</td><td>1.11e+03</td></tr><tr><td>CPSO</td><td>1.25e+02</td><td>8.04e+02</td><td>7.85e+02</td><td>4.56e+02</td><td>8.36e+02</td><td>7.70e+02</td><td>5.97e+02</td></tr><tr><td>OLPSO-VRS</td><td>1.51e+01</td><td>7.51e+02</td><td>5.66e+02</td><td>3.22e+02</td><td>5.21e+02</td><td>3.79+02</td><td>4.15e+02</td></tr><tr><td rowspan="5">F4</td><td>AINMA</td><td>3.06e-03</td><td>1.40e+01</td><td>6.78e+00</td><td>3.81e-03</td><td>5.06e+01</td><td>6.71e-01</td><td>7.86e-01</td></tr><tr><td>AINMA(without TS)</td><td>6.01e-03</td><td>5.48e+01</td><td>8.67e+00</td><td>6.57e-03</td><td>5.53e+01</td><td>6.84e-01</td><td>7.93e-01</td></tr><tr><td>dopt-aiNet</td><td>1.09e+00</td><td>1.35e+02</td><td>8.68e+01</td><td>5.77e+00</td><td>3.01e+02</td><td>1.59e+01</td><td>5.59e+01</td></tr><tr><td>CPSO</td><td>2.87e+00</td><td>3.47e+01</td><td>3.26e+01</td><td>7.85e-01</td><td>6.15e+01</td><td>5.28e+00</td><td>1.08e+01</td></tr><tr><td>OLPSO-VRS</td><td>1.24e+00</td><td>3.00e+01</td><td>2.18e+01</td><td>9.55e-01</td><td>4.13e+01</td><td>1.45e+00</td><td>7.85e+00</td></tr><tr><td rowspan="5">F5</td><td>AINMA</td><td>8.66e-03</td><td>1.61e-02</td><td>1.55e-01</td><td>7.37e-03</td><td>2.54e+00</td><td>6.25e-01</td><td>1.80e-01</td></tr><tr><td>AINMA(without TS)</td><td>1.84e-02</td><td>9.47e-01</td><td>1.55e-01</td><td>2.18e+00</td><td>3.79e+01</td><td>6.69e-01</td><td>2.02e-01</td></tr><tr><td>dopt-aiNet</td><td>3.58e+01</td><td>3.67e+01</td><td>3.09e+01</td><td>1.17e+02</td><td>1.01e+03</td><td>4.57e+02</td><td>2.35e+02</td></tr><tr><td>CPSO</td><td>2.16e+00</td><td>2.65e+00</td><td>4.04e+00</td><td>1.12e+00</td><td>8.16e+00</td><td>5.74e+00</td><td>5.89e+00</td></tr><tr><td>OLPSO-VRS</td><td>5.64e-01</td><td>3.22e-01</td><td>4.52e-01</td><td>1.21e-01</td><td>5.99e-01</td><td>3.28e-01</td><td>6.20e-01</td></tr><tr><td rowspan="5">F6</td><td>AINMA</td><td>2.12e-01</td><td>2.34e+01</td><td>7.68e+00</td><td>2.97e+00</td><td>1.40e+01</td><td>4.40e+00</td><td>4.74e+00</td></tr><tr><td>AINMA(without TS)</td><td>1.97e+00</td><td>5.04e+01</td><td>1.23e+01</td><td>4.30e+00</td><td>1.52e+01</td><td>4.53e+00</td><td>5.12e+00</td></tr><tr><td>dopt-aiNet</td><td>2.36e+01</td><td>3.48e+02</td><td>4.29e+02</td><td>8.67e+01</td><td>8.74e+02</td><td>5.27e+02</td><td>3.62e+02</td></tr><tr><td>CPSO</td><td>7.93e+00</td><td>2.47e+01</td><td>2.86e+01</td><td>7.54e+00</td><td>6.79e+01</td><td>2.68e+01</td><td>3.48e+01</td></tr><tr><td>OLPSO-VRS</td><td>5.72e+00</td><td>1.43e+01</td><td>1.25e+01</td><td>7.73e+00</td><td>1.94e+01</td><td>7.51e+00</td><td>9.77e+00</td></tr></table></body></html>

根据表2中算法对比结果分析可知，本文所提出的免疫文化基因动态优化算法(AINMA)在所有49种测试情形下，误差均值都比传统免疫网络动态优化算法(dopt-aiNet)小。也就是说，AINMA算法具有更强的寻优能力。与不含禁忌搜索的免疫文化基因算法比较，在大多数情况下，AINMA算法比不含禁忌搜索的算法误差更小，也就是说，禁忌搜索的引入为算法精度提升做出一定贡献。从测试函数角度分析，由于F3的基础组成函数Rastrigrin函数是典型非线性多模态函数，峰与峰之间起伏较大，并且具有大量局部极值点，因此，算法在F3上的误差均值相较于其他几类测试函数大。6类测试函数中，AINMA算法在F3、F4、F4、F6上的精度提升最为明显，表明算法对于较复杂问题的求解能力有很大改善。从变化类型角度分析，算法在

T1、T4、T6三种变化类型下的误差均值相对较小，即算法在问题发生小幅变化、混沌变化和周期噪声变化情况下寻优能力较好。综合分析，AINMA 算法与dopt-aiNet、CPSO、OLPSO-VRS三个算法相比，49种测试情况下有37种测试情况误差均值最小。其中，与CPSO相比，AINMA 算法仅在个别问题上不如CPSO 出色；与OLPSO-VRS 相比，AINMA 算法仅在F3上稍劣于OLPSO-VRS，但差距并不明显。总之，AINMA算法无论在收敛精度还是寻优能力上都有极大改善，并表现出对各类动态优化问题广泛的适应性。

根据仿真实验结果，可以得出各类测试函数在各种变化类型下的收敛曲线图，以下分别列举F1-F6在T1变化类型下的收敛曲线图进行分析。如图2至图8所示，各图纵坐标表示适应度值，其中F1为最大值优化问题,F2-F6为最小值优化问题；横坐标表示环境改变的次数，本文实验设置改变次数为60次，各图随机选取连续10次变化进行分析。

![](images/f35d2346b53d38be172ee48c911976fb6087f3d3ad9f08279bb61a06cf3ebd7b.jpg)  
图2F1(10 peaks)在T1收敛曲线图

![](images/21c6cf7a39e01eaf20c266d57cfb4c3dcc9ae0ee8179f4488063bfa7d078deb1.jpg)  
图3F1(50 peaks)在T1收敛曲线图

![](images/dc331fb2d18a5f8fde2aa4ace417042acaf40ae4cb2cc4fdd061533bc6b9a96b.jpg)  
图4F2在T1收敛曲线图

![](images/bfde467fd0e7a920f8a660210c8f42e39d216d5ef6180d12d5f4b5bde4fc7669.jpg)  
图5F3在T1收敛曲线图

![](images/b3e99cd3bdc21952ea74adc5e1e0b1a89bdd35902df5a83f30d3d4fb36bcf37f.jpg)  
图6F4在T1收敛曲线图

![](images/d52a4d0e6b4e861aa9fce5e787e82d2b281c2e14e75c45c67606f5c848b159a0.jpg)  
图7F5在T1收敛曲线图

![](images/10eea195f93d295e091c661f52a61dda94f821ddbb3b89b1cdef4c8c67ba924d.jpg)  
图8F6在T1收敛曲线图

在动态优化问题中，收敛曲线图通常反映算法的收敛速度、对于环境变化的响应以及是否存在提前停滞现象。通过观察分析算法在各类问题中的收敛曲线图，一方面可以了解算法对该类动态优化问题的适应程度，即当问题发生变化时，算法是否能及时适应环境变化，调整搜索方向；另一方面可以了解算法在每次变化内的收敛速度，收敛速度越快，算法越能够适应快速变化的环境。

从图2可以看出，包含10个峰的F1测试函数在T1变化类型下收敛速度较快，收敛过程中极少出现停滞状态，算法在环境发生变化时能及时响应并快速搜索新的全局最优值。图3所示是包含50个峰的F1测试函数在T1变化类型下的收敛曲线图，由于峰数增加导致的环境复杂性变化并未影响算法的收敛速度，算法依然能够快速收敛。图4表示F2测试函数在T1变化类型下的收敛性，由图可知，算法第一次从较差初始值收敛到全局最优值后，当环境发生改变时，算法的适应度值并未大幅上升，表明算法始终保持良好的多样性。图5所示F3测试函数由于函数本身的复杂性，算法易陷入局部最优值，并且算法对于环境的适应速度较慢，前期寻优结果差，但当算法逐渐适应环境之后，其寻优精度不断提升。图6至图8所示F4-F6 测试函数在T1变化类型下的收敛曲线图所反映的特征与图4相似。

综合以上分析可知，AINMA算法继承了传统人工免疫网络算法的多样性，并在此基础上提高的收敛速度和搜索精度，当环境发生变化时能够快速响应并开始新的搜索。分析表明，AINMA算法对于求解连续函数动态优化问题有良好性能。

# 4 结束语

本文在传统人工免疫网络算法(dopt-aiNet)的基础之上，针对算法搜索精度低和寻优后期易出现早熟收敛的缺陷，提出了一种免疫文化基因动态优化算法(AINMA)。AINMA 算法保留了dopt-aiNet算法多样性好的优点，通过引入柯西变异算子，与传统高斯变异算子交替使用，在算法不同寻优时期使用不同的变异方式，充分发挥两种变异算子的优势，防止个体陷入局部最优，一定程度上提高了算法的全局搜索能力。同时，利用禁忌搜索的局部寻优能力，将其融合进dopt-aiNet 算法当中，有效提高算法的寻优精度。通过对GDBG动态函数测试集的仿真实验表明，AINMA算法相较于改进前在搜索精度和收敛速度上都有很大提高，并且与其他同类动态优化算法比较也有明显优势。

本文所提出的AINMA算法对于存在大量局部最优的复杂动态问题表现出适应性差的现象。下一步将深入分析，提出改进。

# 参考文献：

[1]段海滨，张祥银，徐春芳．仿生智能计算[M]．北京：科学出版社,2011. (Duan Haibin,Zhang Xiangyin,Xu Chunfang.Bio-inspired Computing [M]. Beijing: Science Press,2011.)   
[2]陈莉，丁立新.动态优化算法综述[J].武汉大学学报(理学版)，2011, 57 (3):255-264.(Chen Li,Ding Lixin. Survey on dynamic optimization algorithms[J].Journal ofWuhan University:Natural Science Edition,2011, 57 (3): 255-264. )   
[3]Fu Haobo,Lewis PR,Sendhoff B,et al.What are dynamic optimization problems?[C]//Proc of IEEE Congress on Evolutionary Computation. Piscataway,NJ:IEEE Press,2014:1550-1557.   
[4]Gao Shangce,Wang Yirui, Cheng Jiujun,et al.Ant colony optimization with clustering for solving the dynamic location routing problem[J].Applied Mathematics and Computation,2016,285 (C): 149-173.

[5]Luo Wenjian,Yang Bin,Bu Chenyang,et al.A hybrid particle swarm optimization for high-dimensional dynamic optimization [C]//Proc ofAsiaPacific Conference on Simulated Evolution and Learning. Berlin: Springer, 2017: 981-993.

[6]Yang Xinshe，He Xingshi. Firefly algorithm:recent advancesand applications [J]. International Journal ofSwarm Intelligence,2013,1(1):1- 14.   
[7]Yazdani D, Sepasmoghaddam A,Dehban A,et al.A novel approach for optimization in dynamic environments based on modified artificial fish swarm algorithm[J]. International Journal of Computational Intelligence and Applications,2016,15 (2):1650010.   
[8]Tan Ying, Zhu Yuanchun.Fireworks Algorithm for Optimization [C]//Proc of the 1st International Conference on Advances in Swarm Inteligence. Berlin: Springer,2010: 355-364.   
[9]Liu Li, Xu Wenbo.A cooperative artificial immune network with particle swarm behavior for multimodal function optimization[C]//Proc of IEEE Congress on Evolutionary Computation.Piscataway,NJ: IEEE Press,2008: 1550-1555.   
[10]赵辉，李牧东，翁兴伟．分布式人工蜂群免疫算法求解函数优化问题 [J].控制与决策,2015,30(7):1181-1188.(Zhao Hui,Li Mudong,Weng Xingwei.Distributed artificial bee colony immune algorithm for the problems of function optimization [J]. Control and Decision,2015,30(7): 1181-1188. )   
[11] De Castro L N,Timmis J.An artificial immune network for multimodal function optimization [C]// Proc of IEEE Congresson Evolutionary Computation. Piscataway, NJ: IEEE Press,2002: 699-704.   
[12] Castro L N D,Timmis J.An artificial immune network for multimodal function optimization [Cl// Proc ofConference on Genetic and Evolutionary Computation. New York:ACMPress,2005:289-296.   
[13] ZubenFJV.Adynamicartifcialimmunealgorithappliedtochallenging benchmarking problems [C]// Proc of IEEE Congress on Evolutionary Computation.Piscataway,NJ: IEEE Press,2009: 423-430.   
[14]刘光远．禁忌搜索算法及应用[M].北京：科学出版社,2014.(Liu Guangyuan.Tabu search algorithm and application [M].Beijing:Science Press,2014.)   
[15]李志勇，李玲玲，王翔，等．基于 Memetic 框架的混沌人工蜂群算法 [J].计算机应用研究,2012,29(1):4045-4049.(LiZhiyong,LiLingling, Wang Xiang,et al.Chaos artificial bee colony based on memetic framework [J].Application Research of Computers,2012,29 (11): 4045-4049.)   
[16]张晓菲，张火明．基于连续函数优化的禁忌搜索算法[J]．中国计量学 院学报,2010,21 (3): 69-74. (Zhang Xiaofei, Zhang Huoming.Improved tabu search algorithm for continuous problems [J].Journal of China University of Metrology,2010,21 (3): 69-74.)   
[17] Li Changhe, Yang Shengxiang,Nguyen TT,et al. Benchmark generator for CEC'2009 competition on dynamic optimization [J]. Sensor Letters,2008, 11 (5): 900-909.