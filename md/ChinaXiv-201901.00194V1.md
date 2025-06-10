# 基于指数衰减惯性权重的分裂粒子群优化算法

王永贵，曲彤彤，李爽(辽宁工程技术大学 软件学院，辽宁 葫芦岛 125105)

摘要：针对粒子群优化算法因种群多样性丧失而陷入局部最优、早熟收敛的问题，提出一种基于指数衰减惯性权重的分裂粒子群优化算法（EDW-DPSO）。首先，采用半均匀初始化种群，使种群以整体均匀、局部随机的方式分布；其次，引入动态分裂算子，对满足分裂条件的粒子执行分裂操作，增加种群多样性，避免粒子陷入局部最优；最后，采用指数衰减的惯性权重，平衡粒子全局搜索和局部开发能力。实验结果表明，该算法在前期有较大的搜索空间，种群多样性增加，后期则强调局部开发，提高收敛精度和优化能力，加快粒子跳脱局部极值逼近全局最优。

关键词：粒子群优化算法；种群多样性；半均匀；分裂；指数衰减惯性权 中图分类号：TP301.6 doi:10.19734/j.issn.1001-3695.2018.10.0734

Disruption particle swarm optimization algorithm based on exponential decay weight

Wang Yonggui, Qu Tongtong, Li Shuang (College of Software,Liaoning Technical University,Huludao Liaoning l251o5,China)

Abstract:To overcome the localoptimum and premature convergence due to loss of population diversityof the particle swarm optimization algorithm,this paper proposed adisruption particle swarm optimization algorithm based on exponential decay weight (EDW-DPSO).Firstly,the population wassemi-uniformly initialized todistribute thepopulation inanoveral uniform,locallyrandom manner. Secondly,te dynamic spliting operator was introduced to perform spliting operations on particles which satisfyingthe splitingcondition,increasingthediversityofthepopulationandavoidingthe particlesfaling into localoptimum.Finaly,theexponentialdecreasing inertiaweight wasusedtobalance the global searchandlocal development abilityof the particles.Theexperimental results show that the algorithm has alarge search space inthe early stage，and the population diversity increases.In the later stage,emphasizeing the local development to improve the convergence precision andoptimization ability.It can also accelerate particles jumping out of the local extremum and approximate globle optimum.

Key words:particle swarm optimization algorithm;population diversity；semi-uniform；disruption;exponential decay weight

# 0 引言

粒子群优化(particle swarm optimization，PSO)[l]算法是由Kennedy和Eberhart于1995年根据人类社会，鸟类聚集等群体有机行为提出的一种群智能算法。PSO算法因其易于实现，调参灵活，收敛快等特点，一经提出便引起学者高度关注，并广泛应用于函数优化[2.3]、模式识别[4.5]、神经网络训练等领域[6.7]。

PSO 算法的寻优原理是根据个体与群体经验调整自身状态，过程中因个体间缺乏联系，种群多样性逐渐丧失，导致算法易陷入局部极值，全局最优解8搜索能力弱的问题。为此学者们提出多种改进措施：文献[9]为提高种群多样性，提出交互粒子概念,将种群随机动态划分成多个子种群，并利用环拓扑结构来进行信息共享；文献[10]利用混沌运动的随机性特点，将混沌优化和PSO算法相结合，并采用混沌载波来优化搜索策略，避免算法陷入局部极值；文献[11根据粒子历史最佳位置和距离，确定不同的惯性权重，提高了算法在静态和动态环境中解的质量和收敛速度；文献[12]将随机因子引入惯性权重，并采用多次随机初始化，以实现调节惯性权重的自适应性，提高收敛精度；文献[13]将粒子群优化算法与遗传算法结合，利用遗传算法中的变异、交叉、选择等操作对算法参数二次优化，提高算法的收敛速率，使算法具有较强鲁棒性。文献[14]将布谷鸟算法引入高动态粒子群算法，利用中位数聚类算法对种群进行动态划分，融合后的算法有效提高了全局搜索能力。

综上所述，粒子群优化算法的改进策略一直在发展和探索中，但仍存在一些问题。若仅对算法参数改进，速度与位置的更新呈一定比例，限制粒子全局搜寻，无法避免陷入局部最优；若与其他算法融合，增加了需人为调控的参数很难达到增加种群多样性的预想，且计算量大，算法执行效率低。

针对上述问题，本文提出了一种改进的粒子群优化算法:基于指数衰减惯性权重的分裂粒子群优化算法（disruptionparticle swarm optimizationalgorithm based on exponentialdecayweight，EDW-DPSO）。EDW-DPSO主要有以下改进：a）为避免随机初始化种群带来的无效解，提出半均匀式初始化种群，使种群既不丧失随机性又能相对均匀地遍布于搜索空间；b）为扩大粒子的搜索空间，引入分裂算子，分裂满足条件的粒子以增加种群多样性并提高收敛精度；c）为平衡种群全局搜索与局部开采能力，采用指数衰减的惯性权重，使算法在优化前期有较快的收敛速度，提高全局搜索能力，后期则以较小的速率缓慢更新粒子位置，提高寻优效率和收敛稳定性。

# 1 基本理论

PSO 算法是一种基于群体的随机搜索算法。假设NP 个粒子组成的种群在 $\mathfrak { n }$ 维空间内展开搜索，每个粒子代表一个候选解，具有速度与位置两个属性，利用其计算目标函数的适应度值，通过适应度值评估粒子当前位置。每个粒子更新速度和更新位置如下：

$$
V _ { i , n } ^ { k + 1 } = \omega V _ { i , n } ^ { k } + c _ { 1 } \left( P b e s t _ { i , n } ^ { k } - X _ { i , n } ^ { k } \right) + c _ { 2 } ( G b e s t _ { i , n } ^ { k } - X _ { i , n } ^ { k } )
$$

$$
X _ { i , n } ^ { k + 1 } = V _ { i , n } ^ { k + 1 } + X _ { i , n } ^ { k }
$$

其中： $V _ { i , n } ^ { k }$ 、 $X _ { i , n } ^ { k }$ 、 $P b e s t _ { i , n } ^ { k }$ 、 $G b e s t _ { i , n } ^ { k }$ 分别为第i个粒子在 $\mathfrak { n }$ 维空间 $\mathbf { k }$ 次迭代的速度、位置、个体最优及全局最优的位置。其他参数的具体说明见表1。

表1基本PSO算法参数说明  
Table1Basic PSO algorithm parameter description   

<html><body><table><tr><td>参数</td><td>说明</td><td>范围</td></tr><tr><td>k</td><td>迭代次数</td><td>由实际问题决定</td></tr><tr><td>n</td><td>向量维度</td><td>问题解的长度，变量个数</td></tr><tr><td>@</td><td>惯性权重</td><td>常为非负数，调节解空间的搜索范围</td></tr><tr><td>C1C2</td><td></td><td>学习因子[0,4]间，常为2，影响种群多样性与收敛速度</td></tr><tr><td>1r</td><td>随机数</td><td>[0,1]之间，增加粒子的随机性</td></tr></table></body></html>

# 2 指数衰减惯性权重的分裂PSO

# 2.1 半均匀初始化

为保证PSO 算法在初始化种群时既不丧失粒子群本身的随机性，同时避免粒子初始化位置过度集中的问题，本文提出一种半均匀式初始化方式生成种群，即一半种群仍采用基本PSO算法中随机化方式生成，另一半种群采用先整体均匀再局部随机的方式生成，即根据均匀化的统计实验原理，先人为干预种群，设定新的解集空间，将粒子对应的搜索空间均匀划分成固定的NP/2个新的解空间，然后粒子对应的初始解在新的等分空间中随机生成，这使粒子群算法在整体均匀的基础上进一步保留了种群本身的随机性，避免了随机初始化种群导致粒子群初始化位置过于集中，使种群既相对均匀的分布在整个搜索空间，又能保持种群的随机性、多样性。能够有效提高种群的搜索效率，促进粒子进行全局搜索。半均匀式初始化种群的策略如下：

$$
\left\{ \begin{array} { l l } { \displaystyle X _ { i , t } ^ { 0 } = r a n d ( \phi _ { t } , \varphi _ { t } ) } \\ { \displaystyle X _ { j , t } ^ { 0 } = r a n d ( \phi _ { t } + \frac { ( \varphi _ { t } - \phi _ { t } ) } { N P / 2 } ( j - 1 ) , \phi _ { t } + \frac { ( \varphi _ { t } - \phi _ { t } ) } { N P / 2 } j ) } \end{array} \right.
$$

其中：NP为种群规模；种群向量维度为 $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 维，i、 $\mathrm { j }$ 分别为种群中第i，j个个体， $i = ( 1 , 2 , \cdots , N P / 2 )$ ，$j = ( N P / 2 + 1 , N P / 2 + 2 , \cdot \cdot , N P )$ ： $\mathrm { ~  ~ t ~ }$ 为 $\mathfrak { n }$ 维变量中第t个变量，t维粒子的搜索空间为 $( \phi _ { t } , \varphi _ { t } )$ ； $X _ { i , t } ^ { 0 }$ 、 $X _ { j , t } ^ { 0 }$ 为第0代种群第i、 $\mathrm { ~ j ~ }$ 个粒子的第t个变量初始值。

# 2.2指数衰减惯性权重

由式（1）（2）可知，PSO算法通过粒子的速度和位置变化实现寻优，而粒子位置的变化与惯性权重有关，因此惯性权重是影响算法性能和效率的关键因素，学者对此进行大量研究：文献[15]首次提出使用线性递减惯性权重，以线性方式减小权值，加快算法收敛速度；文献[16]在速度更新方程中引入压缩因子来控制粒子的速度变化，文献[17]提出了基于迭代次数变化选取固定惯性权重的策略。以上改进都能很好的提高算法性能，但固定的变换形式，使种群的搜索过程虽是动态进行但却是可预知的变更，进而使粒子的速度与位置在迭代时一直以不变的比例进行改变，限定了粒子速度与位置变换的步长，固定的步长不利于个体的全局搜索，缩小了种群的搜索范围，间接影响种群多样性的保留。因此，本文采用非线性指数衰减惯性权重，公式如下：

$$
V _ { i , n } ^ { k + 1 } = e ^ { - \alpha } V _ { i , n } ^ { k } + c _ { 1 } r _ { 1 } \left( P b e s t _ { i , n } ^ { k } - X _ { i , n } ^ { k } \right) + c _ { 2 } r _ { 2 } \left( G b e s t _ { i , n } ^ { k } - X _ { i , n } ^ { k } \right)
$$

$$
\alpha = k \frac { \ln { \omega _ { \mathrm { m a x } } } - \ln { \omega _ { \mathrm { m i n } } } } { k _ { \mathrm { m a x } } } - \ln { \omega _ { \mathrm { m a x } } }
$$

其中： $e ^ { - \alpha }$ 为递减的指数函数；参数 $\alpha$ 影响移动步长的大小;$\omega _ { \mathrm { m a x } }$ 和 $\omega _ { \mathrm { m i n } }$ 为设定的惯性权重最大值和最小值( $\omega _ { \mathrm { m a x } } = 0 . 9 , \omega _ { \mathrm { m i n } } = 0 . 4$ ）。由于指数函数的特点，使算法在前期搜索阶段有较大的移动步长，扩大了搜索区域，保证算法的全局搜索能力并提高搜索效率；而在后期开发阶段，较小的步长将减缓粒子的更新速度，避免局部极值问题，提高算法收敛稳定性，平衡算法的搜索和开发能力。

# 2.3分裂算子

# 1）分裂条件

为了模拟天体中的分裂现象[18]，使在迭代中种群适应度值最小的粒子对应天体分裂中的大质量物体即核心 $\mathrm { ~ M ~ }$ ，不参与分裂；其余粒子对应天体分裂中的质点群 $\mathrm { m }$ ，且每个粒子都存在被分裂的可能。粒子的分裂条件如下：

$$
\frac { P _ { i , j } } { p _ { i , b e s t } } < C
$$

其中： $P _ { i , j }$ 为当前粒子i与粒子j的距离； $P _ { i , b e s t }$ 为当前粒子i与最优粒子之间的距离。但为降低算法的复杂度，本文用粒子间适应度值的大小代替粒子间距离的远近，因此粒子j是将整个种群的适应度值按升序排列后，下标刚好小于i的粒子。

# 2）分裂算子

为了充分利用 $P _ { i , j }$ ，平衡全局搜索和局部开发性能，设定分裂算子D如下：

$$
D = \left\{ \begin{array} { l l } { P _ { i , j } \times U ( - \frac { 1 } { 2 } , \frac { 1 } { 2 } ) , } & { i f ~ P _ { i , b e s t } \ge e ^ { - k / k _ { \mathrm { m a x } } } , } \\ { P _ { i , j } + U ( - \frac { P _ { i , j } } { 2 } , \frac { P _ { i , j } } { 2 } ) , } & { o t h e r w i s e . } \end{array} \right.
$$

其中： $U ( - \frac { 1 } { 2 } , \frac { 1 } { 2 } )$ 和 $U ( - \frac { P _ { i , j } } { 2 } , \frac { P _ { i , j } } { 2 } )$ P,P)是在区间[- $[ - \frac { 1 } { 2 } , \frac { 1 } { 2 } ]$ 和 $[ - \frac { P _ { i , j } } { 2 } , \frac { P _ { i , j } } { 2 } ]$ 均匀分布的随机数， $e ^ { - \frac { k } { k _ { \mathrm { m a x } } } }$ 是设定的阈值。为了对应上文的指数衰减惯性权重，将阈值同样设为随迭代次数 $\mathbf { k }$ 指数衰减的函数。随迭代次数 $\mathbf { k }$ 的增加，粒子接近全局最优， $P _ { i , b e s t }$ 逐渐减小，当 $P _ { i , b e s t } \geq e ^ { - k / k _ { \mathrm { m a x } } }$ 时， $D \in [ - \frac { P _ { i , j } } { 2 } , \frac { P _ { i , j } } { 2 } ]$ [PP]有助于粒子的全局搜索；当 $P _ { i , b e s t } < e ^ { - \displaystyle { k / k _ { \mathrm { m a x } } } }$ 时， $D \in [ \frac { P _ { i , j } } { 2 } , \frac { 3 P _ { i , j } } { 2 } ]$ 有助于粒子的局部开采。

# 3）分裂策略

为了提高种群多样性和找到全局最优解，通过式（8）所示的分裂策略更新满足分裂条件的粒子。本算法采用的分裂策略如下：

$$
X _ { i } ^ { k } = \frac { k } { k _ { \operatorname* { m a x } } } X _ { i } ^ { k } + ( 1 - \frac { k } { k _ { \operatorname* { m a x } } } ) X _ { i } ^ { k } D
$$

动态分裂策略由分裂项 $( 1 - \frac { k } { k _ { \operatorname* { m a x } } } ) X _ { i } ^ { k } D$ 和粒子自身位置信息 ${ \frac { k } { k _ { \operatorname* { m a x } } } } X _ { i } ^ { k }$ 两部分组成。分裂项，由随迭代次数 $\mathbf { k }$ 线性递减的系数 $1 - \frac { k } { k _ { \operatorname* { m a x } } }$ 和分裂算子 $D$ 组成；自身位置信息，由随迭代次数k线性递增的系数 $\frac { k } { k _ { \operatorname* { m a x } } }$ 组成。在寻优前期，以分裂项为主进行粒子分裂，增加种群多样性，帮助粒子探索更广阔的搜索区域，避免局部最优；在寻优后期，粒子已接近全局最优，因此粒子主要利用其自身位置信息即可。动态分裂策略有助于提高算法的收敛精度。

# 3 算法流程

a）初始化PSO 算法基本参数，（ $\omega _ { \mathrm { m i n } } , \omega _ { \mathrm { m a x } } \ ) = ( 0 . 4 , 0 . 9 )$ ，$\left( \begin{array} { l } { c _ { 1 } , c _ { 2 } } \end{array} \right) \ = \ \left( \ 2 . 0 , \ 2 . 0 \right)$ ，种群规模NP，每维变量的上下界范围 ${ \bf \Xi } ( { \bf \Lambda } \phi _ { t } , \varphi _ { t }$ ）,粒子的最大飞行速度 $V _ { \mathrm { m a x } }$ ；最大迭代次数 $k _ { \operatorname* { m a x } }$ ：

b）由式（3）半均匀初始化种群;c）更新粒子 $V _ { i , n } ^ { k }$ ， $V _ { i , n } ^ { k }$ ，得到新一代种群;d)根据目标函数计算粒子适应度值，更新 $P b e s t _ { i , n } ^ { k }$ 和Gbestn;e）判断粒子是否满足分裂条件（6），满足则执行步骤f)，否则执行步骤g)；f）由式（7）（8）进行粒子分裂；g）由式（4）（5）更新粒子 $V _ { i , n } ^ { k }$ ， $V _ { i , n } ^ { k }$ ;h)若 $k \geq k _ { \operatorname* { m a x } }$ ，则输出当前粒子的适应度值，否则重复步骤c)\~h)。

# 4 实验与结果分析

为确保实验的公平性，本文所有实验均在InterCorei5-3337UCPU $1 . 8 ~ \mathrm { G H z }$ ，12GB内存的机器上实现，采用MATLABR2014b作为实验平台。种群规模 $\mathrm { N P } { = } 3 0$ ，种群维数 $\scriptstyle \mathbf { N } = 3 0$ ，最大迭代次数 $k { = } 1 0 0 0$ ，粒子初始化范围为表2测试函数的搜索空间界限，每种测试函数独立运行30次，可接受误差为0.1。

为评定算法性能，选择以下评价准则：a）“Mean”代表最后一次迭代所获得目标函数适应度值的均值，衡量算法的寻优质量；b）“Std”代表标准差，衡量算法的稳定性；c)“SuccR”代表有效解次数占总执行次数的比例，衡量算法的鲁棒性。

# 4.1算法测试函数

为验证本文改进PSO算法的可行性，选取2个经典单峰函数和3个复杂多峰测试函数进行算法验证，如表2所示，并列出了测试函数的搜索空间和理论最优解。其中 $f _ { 1 }$ 、 $f _ { 2 }$ 为典型的单峰函数，仅有一个极值点，但 $f _ { 2 }$ 为非凸病态函数，较难找到最优解； $f _ { 3 }$ 、 $f _ { 4 }$ 和 $f _ { 5 }$ 为可变不可分的旋转三角多峰函数，有大量极值点。

# 4.2单项改进策略可行性验证

为验证所提EDW-DPSO算法各项改进措施的有效性，现分别对单项改进措施进行验证。

# 4.2.1指数衰减惯性权重策略

为验证指数衰减惯性权重模式EDWPSO（exponentialdecayweightPSO)在前期搜索阶段具有较好的全局搜索能力，后期具有较高的局部开采性能。将EDWPSO算法与惯性权重粒子群优化算法（LDWPSO）[19]、衰变因子粒子群优化算法（CFPSO)[20]进行对比，用测试函数 $f _ { 1 }$ 、 $f _ { 4 }$ 、 $f _ { 5 }$ 进行验证,如图1所示。

表2测试函数

Table 2 Test function   

<html><body><table><tr><td>编号</td><td>函数名</td><td>函数</td><td></td><td>搜索空间</td><td>最优解</td></tr><tr><td>f</td><td>Sphere</td><td colspan="3" rowspan="2">f= i=1</td><td rowspan="2">[-100,100]" (0...0)</td></tr><tr><td></td><td>Rosenbrock</td></tr><tr><td>f</td><td></td><td colspan="2">f= [100(xi+1-x2)²+(1-xi)²] i=1 f=-20exp(-0.02 ∑x²/n-exp(l/n∑cos(2x))+20)</td><td>[-10,10]" [-32,32]n</td><td>(.,..,.1)</td></tr><tr><td>f f4</td><td>Ackley</td><td colspan="2">i=1 i=1 f4= [x²-10cos(2πxi +10)]</td><td>[-5.12,5.12]n</td><td>(0...0)</td></tr><tr><td>f5</td><td>Rastrigin Griewank</td><td colspan="2">i=] f5= 40x²-+1</td><td></td><td>(0...0)</td></tr><tr><td>10°</td><td>Sphere Function 10</td><td colspan="2">i=1 √i Rastrigrin Function 4000台</td><td>[-600,600]n Griewank Function</td><td>(0...0)</td></tr><tr><td colspan="2">100 10</td><td colspan="3"></td></tr></table></body></html>

图1函数收敛特性线

Fig.1 Convergence characteristic line of function

从图1中可以清楚地看出，不管是对于简单的单峰测试函数还是复杂的多峰测试函数，EDWPSO都比LDWPSO、CFPSO的收敛性能好，并较快地进入全局最优。而且图1b)和c)显示出算法在经过一定的迭代次数后，适应度值都集中在一个值，说明算法具有较强的稳定性，充分证明了指数衰减惯性权重策略可以避免最优解陷入局部极值现象。

# 4.2.2天体分裂策略

为验证分裂算子（DPSO）能够提高粒子群优化算法种群多样性及收敛精度，增大找到全局最优解的机会，将算法DPSO与标准粒子群优化算法（SPSO）[2I、量子行为粒子群优化算法（QPSO）[22]做两个方面性能对比。

a）寻优性和稳定性方面比较。用测试函数 $f _ { 2 }$ 、 $f _ { 3 }$ 、 $f _ { 4 }$ 进行验证，计算粒子适应度函数平均适应度值，算法的稳定性由方差衡量。实验结果如表3所示。

Table 3Comparison of optimal performance and stability   

<html><body><table><tr><td>函数</td><td>评价准则</td><td>SPSO</td><td>QPSO</td><td>DPSO</td></tr><tr><td rowspan="2">f</td><td>Mean</td><td>2.5913E+01</td><td>3.7149E+01</td><td>1.9077E-02</td></tr><tr><td>Std</td><td>1.9150E+01</td><td>2.7733E+01</td><td>2.9113E-02</td></tr><tr><td rowspan="2">f</td><td>Mean</td><td>4.3751E+00</td><td>1.3323E-01</td><td>8.0818E-02</td></tr><tr><td>Std</td><td>9.7228E-01</td><td>4.0906E-01</td><td>2.7044E-01</td></tr><tr><td rowspan="2">f4</td><td>Mean</td><td>4.8560E+01</td><td>3.6886E+01</td><td>6.0133E-03</td></tr><tr><td>Std</td><td>1.1036E+01</td><td>9.2230E+00</td><td>2.6608E-02</td></tr></table></body></html>

表3的实验结果表明，DPSO算法与其他改进的粒子群算法比较，在寻优性能和稳定性方面均有较好表现，对于单峰函数 $f _ { 2 }$ ，DPSO算法的平均适应度值和方差明显小于SPSO和 QPSO 算法，且 SPSO 和 QPSO 的方差是 DPSO 的$6 . 5 8 6 \mathrm { E } \mathrm { + } 0 2$ 、 $9 . 5 5 1 \mathrm { E } { + } 0 2 \$ 倍，体现了算法具有更强的稳定性。对于多峰函数 $f _ { 3 }$ ，各算法优化效果较为相同，但在 $f _ { 4 }$ 中，其他两种算法的平均适应度值是DPSO的 $8 . 0 7 5 4 \mathrm { E } { + } 0 3$ 、$6 . 1 3 4 1 \mathrm { E } { + } 0 3$ 倍，体现了算法具有更好的寻优质量。从上述实验结果可知，DPSO算法收敛性和稳定性俱佳，有较好的寻优性能。

b）种群多样性方面比较。用测试函数 $f _ { 1 }$ 、 $f _ { 5 }$ 进行验证，如图2所示。对于单峰函数 $f _ { 1 }$ ，在搜索的前期，DPSO与SPSO、QPSO有相近的种群多样性；在搜索的后期，DPSO 种群多样性骤减，确保了种群精细、快速的收敛。对于多峰函数 $f _ { 5 }$ ，在搜索前期，DPSO比SPSO、QPSO种群多样性高，增加了种群多样性；而后期骤减，提高种群收敛精度，逼近全局最优。上述结果表明，因分裂粒子在搜索前期以分裂过程为主，使粒子能探索出更广阔的搜索空间，能够增强种群多样性；后期则根据自身位置信息调整，提高了收敛精度。

![](images/206fd6796b61dc6426c418eda8db1deaf437eef3f31b6ae8923fbd68284180e7.jpg)  
图2种群多样性对比  
Fig.2Comparison of population diversity

以上两个单项改进策略的验证实验表明，本文所提出的指数衰减惯性权重和分裂算子策略，在增强种群多样性和算法收敛性能上有显著提高，说明EDW-DPSO 算法具有可行性和有效性。

# 4.3对比实验

为进一步验证本文算法的优化性能，选用标准粒子群优化算法（standard particle swarm optimization,SPSO）[21]、混沌粒子群优化算法（chaos-particle swarmoptimization,CPSO）[23]、自调节粒子群优化算法（selfregulatingparticleswarm,SRPSO)[24]、综合学习粒子群优化算法（comprehensivelearningparticleswarm optimizer,CLPSO ）[25]与 本文EDW-DPSO做对比实验。使用5个标准测试函数3项评价准则验证算法性能。各算法实验统计结果如表4所示。

表3寻优性能和稳定性比较  
表4不同PSO 算法性能比较  
Table 4Performance comparison of different PSO algorithms   

<html><body><table><tr><td>函数</td><td>评价准则</td><td>SPSO</td><td>CPSO</td><td>SRPSO</td><td>CLPSO</td><td>EDW-DSPSO</td></tr><tr><td rowspan="3">fi</td><td>Mean</td><td>8.3674E-04</td><td>5.5678E-05</td><td>9.4315E-08</td><td>2.1020E-06</td><td>2.8871E-13</td></tr><tr><td>Std</td><td>4.4666E-04</td><td>3.0705E-04</td><td>2.9024E-07</td><td>5.3500E-06</td><td>7.3204E-13</td></tr><tr><td>SuccR</td><td>5.6667E-02</td><td>7.4933E-01</td><td>8.8563E-01</td><td>8.9116E-01</td><td>1.0000E+00</td></tr><tr><td rowspan="3">f</td><td>Mean</td><td>2.5913E+01</td><td>9.9126E-02</td><td>6.9088E-01</td><td>3.7847E+00</td><td>1.4226E-03</td></tr><tr><td>Std</td><td>1.9150E+01</td><td>5.4625E-02</td><td>1.3907E-01</td><td>2.0182E+00</td><td>8.0813E-03</td></tr><tr><td>SuccR</td><td>9.6438E-02</td><td>7.8000E-01</td><td>7.393E-01</td><td>7.2980E-01</td><td>1.0000E+00</td></tr><tr><td rowspan="3">f</td><td>Mean</td><td>6.3751E+00</td><td>8.1377E-01</td><td>2.8002E+00</td><td>1.3263E+00</td><td>1.6892E-02</td></tr><tr><td>Std</td><td>9.7228E-01</td><td>3.5268E-01</td><td>9.4011E-01</td><td>7.0526E-01</td><td>3.4031E-02</td></tr><tr><td>SuccR</td><td>3.2853E-01</td><td>1.0000E+00</td><td>1.0000E+00</td><td>9.9536E-01</td><td>1.0000E+00</td></tr><tr><td rowspan="3">f4</td><td>Mean</td><td>4.8560E+00</td><td>2.1617E-01</td><td>4.5011E+00</td><td>6.9080E-01</td><td>5.9053E-03</td></tr><tr><td>Std</td><td>1.1036E+01</td><td>9.2807E+00</td><td>1.9705E+00</td><td>5.0137E+00</td><td>7.2203E-03</td></tr><tr><td>SuccR</td><td>5.5163E-01</td><td>1.0000E+00</td><td>9.9806E-01</td><td>1.0000E+00</td><td>1.0000E+00</td></tr><tr><td rowspan="3">f</td><td>Mean</td><td>2.1305E+01</td><td>6.1833E+00</td><td>1.4708E-02</td><td>6.0202E+00</td><td>1.9230E-08</td></tr><tr><td>Std</td><td>2.9725E+00</td><td>2.6256E+00</td><td>2.4121E-02</td><td>2.0369E+00</td><td>4.1280E-08</td></tr><tr><td>SuccR</td><td>4.5106E-01</td><td>9.9892E-01</td><td>1.0000E+00</td><td>1.0000E+00</td><td>1.0000E+00</td></tr></table></body></html>

表4数据表明，在相同情况下，EDW-DPSO算法在5个测试函数中显示出明显优势，平均适应度值更优，收敛精度更高。对于单峰函数 $f _ { 1 }$ ，相比于其他改进粒子群算法，EDW-DPSO算法均值和方差的收敛精度达到了 $1 0 ^ { - 1 3 }$ ，说明EDW-DPSO算法具有较强收敛性和稳定性。对于病态函数 $f _ { 2 }$ ，CPSO算法与本文算法有相近的实验结果，但与其他算法相比，在性能上依然有很大提高。多峰测试函数 $f _ { 3 }$ 、 $f _ { 4 }$ 、 $f _ { 5 }$ 的实验结果显示，SPSO、CPSO、SRPSO、CLPSO四种算法在平均适应度值和方差两方面表现相近，但EDW-DPSO算法表现出了更好的全局寻优和收敛性能，尤其对于测试函数 $f _ { 5 }$ ，因其在超过15维空间时，特性转变趋向单峰函数，优化效果较为理想。另外本文算法得到的全局极值都集中均值的附近，不会因测试次数的增加而远离均值。这是由于本文算法在速度更新方程中采用指数衰减策略，指数函数的特征为速度更新过程提供了一个动态步长，从而保证了前期的全局搜索能力和后期局部开采性能。本文算法的成功率表现良好，部分测试函数的结果显示为1，表现出了较强的全局寻优能力，在单峰函数和多峰函数上有更强的鲁棒性。

为了更清楚且直观地比较各算法的性能，图3展示了SPSO、CPSO、SRPSO、CLPSO和EDW-DPSO这五种改进算法在表2中的五个标准测试函数上的适应度的对数曲线。图中横坐标为迭代次数，纵坐标表示适应度值。

从图3直观地可以看出，EDW-DPSO算法的适应度曲线随着迭代次数增加呈现出递减的趋势，在迭代的初期能够较快的逼近全局最优。对于函数 $f _ { 2 }$ 、 $f _ { 4 }$ 、 $f _ { 5 }$ ，本文算法有较高的收敛速度。指数衰减惯性权重使粒子在搜索前半部分位移变化速度快，后半部分位移速度变化慢，能够更好地搜索目标函数值。对比不同测试函数的适应度曲线，SPSO、CPSO算法在寻优时易陷入局部最优，这是由于SPSO算法无法向局部其他粒子学习，易造成启发式学习和计算资源的浪费，使算法的寻优质量较差；CPSO算法利用混沌映射创建初始种群，利用最优解附近混沌搜索结果替代种群中部粒子，而混沌策略是在种群陷入局部极值后开始生效，所以在求解多峰问题时表现较差，存在陷入局部极值现象。EDW-DPSO算法利用分裂算子（模拟天体分裂现象），粒子在搜索的前期以执行分裂过程为主，增加粒子的数量。此过程帮助粒子探索更广阔的搜索区域，丰富种群多样性，避免粒子陷入局部最优。数据和图示都显示出本文算法能够增加种群多样性，提高收敛精度，在单峰和复杂的多峰问题上都能取得最优解。EDW-DPSO算法表现出了较强收敛性和稳定性。

![](images/597b79d01de1299ae1d22668411883243ee5d5e9a557c3cd621cb2723ea4058b.jpg)  
图3函数的适应度值收敛对比曲线  
Fig.3Contrastive Convergence Curve of function Fitness

# 5 结束语

本文提出一种基于指数衰减惯性权重的分裂粒子群优化算法，通过多角度对比仿真实验总结该算法特点：a）为保障初始化种群的随机性以及避免因随机初始化导致种群出现局部聚集的状况，提出了半均匀式初始化种群策略，使种群以整体均匀、局部随机的方式分布；b）为扩大搜索空间，提出分裂算子，寻优前期主要执行粒子分裂，增加种群多样性；在寻优的后期，粒子已接近全局最优，主要利用其自身位置信息即可；c）为平衡搜索与开发能力，采用指数衰减惯性权重，在前期搜索阶段以较大的前进步长，帮助粒子探索更广阔的搜索区域；后期开发阶段则以小的前进步长强调寻优精度，提高局部开发性能。实验结果表明，该算法可增加种群多样性，具有较强的稳定性和较高的收敛速度，在处理复杂的优化问题上具有实用价值。下一步研究方向是拓宽EDW-DPSO在高维优化问题中的应用范围。

# 参考文献：

[1]Kennedy J,Eberhart R.Particle swarm optimization [C]/ Proc of IEEE International Conference on NeuralNetworks.Piscataway，NJ:IEEE Press,1995:1942-1948.   
[2]Castro JP,Landa-Silva D，Pérez JA M.Exploring feasible andinfeasible regions in the vehicle routing problem with time windows using a multi-objective particle swarm optimization approach [M]/ NatureInspiredCooperativeStrategiesforOptimization. Berlin :Springer,2009:103-114.   
[3]Du Baoxiang,Wei Xu,Song Bing,et al.Prediction of chaotic time series of rbf neural network based on particle swarm optimization [M]// Inteligent Data analysis and its Applications,volume II. [S.1.]:Springer International Publishing,2014: 489-497.   
[4]Banda N, Engelbrecht A,Robinson P. Continuous emotion recognition using a particle swarm optimized NARX neural network [C]// Proc of IEEE International Conference on Affective Computing & Intelligent Interaction.2015:380-386.   
[5] Hasan M,Abdullah S N H S,Othman Z A. Face recognition based on opposition particle swarm optimization and support vector machine [C]// Proc of IEEE International Conference on Signal & Image Processing Applications. 2013: 417-424.   
[6] Chhabra Y, Varshney S,Ankita.Hybrid particle swarm training for convolution neural network (CNN)[C]// Proc of Tenth International Conference on Contemporary Computing. [S.l.]:IEEE Computer Society,2017:10-12.   
[7] Zhang Li,Lu Fei，Zhao Yongyi.Based on the particleswarm optimization_neural network integration algorithm in internet of vehiclesapplication[C]//AdvancedInformationManagement, Communicates,Electronic & Automation Control Conference.2017: 1973-1977.   
[8] Park JS,Shazzad K M,Kim D S.Toward modeling lightweight intrusion detection system through correlation based hybrid feature selection [C]//Proc of Chinese Intelligent Systems Conference.Berlin: Springer-Verlag,2005: 279-289.   
[9] 王燕燕，葛洪伟，王娟娟，等．一种动态分组的粒子群优化算法[J]. 计算机工程,2015,41(1):180-185.(Wang Yanyan,Ge Hongwei, Wang Juanjuan,et al.A particle swarm optimization algorithm of dynamic grouping[J].Computer Engineering,2015,41(1): 180-185.）   
[10] 李文，伍铁斌，赵全友，等．改进的混沌粒子群算法在TSP中的应用 [J]．计算机应用研究,2015,32(7):2065-2067.(Li Wen,Wu Tiebin, Zhao Quanyou,et al. Improved algorithm of chaotic particle swarm and its application in TSP[J].Application Research of Computer,2015,32 (7): 2065-2067.)   
[11] Taherkhani M,Safabakhsh R.A novel stability-based adaptive inertia weight for particle swarm opti-mization [J]. Applied Soft Computing, 2016,38: 281-295.   
[12]叶洪涛，皮倩瑛．多策略融合粒子群算法及其收敛性分析[J].计算 机工程与应用,2016,52(24):1-71-177.(Ye Hongtao,Pi Qianying. Multi-strategyparticleswarm optimizationalgorithmandits convergence analysis [J]. Computer Engineering and Applications, 2016, 52 (24): 1-71-177. )   
[13] 江祥奎，范永青，王婉．基于粒子群遗传算法的 BP神经网络摄像机 标定[J]．计算机科学与探索，2014,8(10):1254-1262.(Jiang Xiangkui,Fan Yongqing，Wang Wan.BP neural network camera calibrationbased on particle swarm optimization genetic algorithm [J]. Journal of Frontiers of Computer Science & Technology,2014,8(10): 1254-1262.)   
[14]高云龙，闫鹏．基于多种群粒子群算法和布谷鸟搜索的联合寻优算 法[J].控制与决策,2016,31(4):601-608.(Gao Yunlong,Yan Peng. Unified optimization based on multi-swarmPSO algorithm and cuckoo search algorithm[J].Control and Decision,2016,31(4): 601-608.)   
[15] Shi Yuhui,Russell C.Eberhart.A modified particle swarm optimizer [C]/Proc of IEEE Congress on Evolutionary Computation.Piscataway, NJ: IEEE Service Center,1998.69-73.   
[16] Clerc M,Kennedy J.The particle swarm-explosion，stability，and convergence in a multidimensional complex space [J].IEEE Trans on Evolutionary Computation,2002,6(1):58-73.   
[17]张焱，高兴宝．一种改进的粒子群算法[J].计算机工程与应用, 2009,45 (26):428-431.(Zhang Yan,Gao Xingbao.Modified particle swarmoptimization algorithm [J].Computer Engineeringand Applications,2009,45 (26): 428-431.)   
[18]Harwit M.Astrophysical Concepts [M].New York :Springer,2006.   
[19] Yan Renwu.LDW-PSO optimization algorithm and its application on the optimal reactive compensation of power network [J].Software Guide,2014: 69-72.   
[20] Clerc M,Kennedy J.The particle swarm-explosion，stability，and convergence in a multidimensional complex space [J]. IEEE Trans on Evolutionary Computation,2002,6(1): 58-73.   
[21]秦全德．粒子群算法研究及应用[D]．广州：华南理工大学，2011. (Qin Quande.Research and application of particle swarm optimization [D].Guangzhou: South China University of Technology, 2011.)   
[22] Sun Jun,Xu Wenbo,Feng Bin.Adaptive parameter control for quantum-behaved particle swarm optimization on individual level [C]// Proc of IEEE International Conference on Systems,Man and Cybernetics.2006:3049-3054.   
[23]刘玲，钟伟民，钱锋．改进的混沌粒子群优化算法[J].华东理工大 学学报,2010,36 (2):267-272.(Liu Ling,Zhong Weimin,Qian Feng. Improved chaos particle swarm optimization algorithm [J].Journal of East China University of Technology,2010,36 (2):267-272.)   
[24] Tanweer MR, Suresh S, Sundararajan N.Self regulating particle swarm optimization algorithm [J].Information Science,2015,294:182-202.   
[25] Liang JJ,Qin A K, Suganthan P N,et al. Comprehensive learning particle swarm optimizer for global optimization of multimodal functions [J]. IEEE Trans on Evolutionary Computation,20o6,10(3): 281-295.