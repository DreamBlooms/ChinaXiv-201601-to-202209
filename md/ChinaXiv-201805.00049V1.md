# 量子鲸鱼优化算法求解作业车间调度问题

闫旭，叶春明，姚远远(上海理工大学 管理学院，上海 200093)

摘要：为了克服基本鲸鱼优化算法（WOA)在解决作业车间调度问题时存在收敛精度低、容易陷入局部最优的缺陷，利用量子计算与优化思想提出了一种量子鲸鱼优化算法(QWOA)，并对其进行了计算复杂度分析、全局收敛性证明及仿真实验。通过对11个作业车间调度问题基准算例的仿真实验发现，与基本鲸鱼优化算法（WOA)、布谷鸟搜索算法(CS）、灰狼优化算法（GWO）相比，QWOA算法在最小值、平均值、寻优成功率等方面具有较优结果。研究表明，量子鲸鱼优化算法在解决作业车间调度问题时，具有更高的收敛精度和更好的全局搜索能力，且能够跳出局部最优。关键词：鲸鱼优化算法；量子计算与优化；作业车间调度；收敛性证明；混合算法  
中图分类号：TP301.06

# Solving Job-Shop scheduling problem by quantum whale optimization algorithm

Yan Xu, Ye Chunming, Yao Yuanyuan (Business School,University ofShanghai for Science and Technology,Shanghai 2Ooo93,China)

Abstract: Toovercome whaleoptimization algorithm's disadvantages of poorconvergence and being easily trapped in local optimain solving job-shop scheduling problem,this paper proposed a quantum whale optimization algorithm (QWOA) based on theidea of quantumcomputation.Then it provided thecomputational complexity analysis,global convergence proof and simulation experiments ofQWOA.Basedonasetof11JSP benchmark instances,the simulation experiments showthat QWOA has beter results than whale optimization algorithm (WOA),cuckoosearch(CS)and grey wolf optimizer (GWO),in the minimumvalue,average value andsuccessrate.Finall,this paperconcludes that QWOAhas themerits ofhigherconvergence accuracy, higher local optima avoidance and better exploration.

Key Words: whale optimization algorithm; quantumcomputingand optimization; job-shop scheduling problem;convergence proof; hybrid algorithm

# 0 引言

作业车间调度问题（Job-Shop scheduling problem，JSP）是最经典的离散制造系统调度问题。作为一种最困难的组合优化问题，JSP已经被证明是一种NP-hard问题，在多项式时间内找不到一个算法精确地求解其最优解，该问题的求解算法研究已成为车间调度领域的热点[I。因此，本文将采用新兴的鲸鱼优化算法解决作业车间调度问题。

鲸鱼优化算法（whale optimization algorithm，WOA），由Mirjalili等人[2]于2016年提出，其仿生学原理源自于座头鲸的狩猎行为。目前，对于鲸鱼优化算法的研究尚处于起步阶段，其正在被逐渐应用到更多的领域；如资源调度领域[31、选址与路径规划领域[4,5]、工业设计领域[6.7等。在算法的改进方面，其主要研究目标为对算法的收敛精度和收敛速度的提升，克服算法容易陷入局部最优、收敛速度慢、收敛精度低等方面的不足，具体涉及种群初始化方法的选择与优化、种群多样性的保持与提升、局部开发能力及全局搜索能力的平衡与提升、可行解的空间扰动与遍历等方面；如，Jangir等人[8]在原有算法的基础上提出了自适应鲸鱼优化算法（AWOA)，Ling 等人[9提出了LWOA算法，钟明辉等人[10]提出了一种随机调整控制参数的高效的鲸鱼优化算法(EWOA)，刘竹松等人[I提出了正余混沌双弦鲸鱼优化算法（CSCWOA)。综上所述，鲸鱼优化算法多用于连续优化问题求解，且尚未被应用于解决作业车间调度问题。因此，本文将借鉴量子计算与优化的思想对鲸鱼优化算法进行改进，并将其用于解决离散的作业车间调度问题。

# 1作业车间调度问题的数学描述

作业车间调度问题（JSP）一般被描述为：在给定每个工件的加工工艺、每个工件使用机器的序列及每个工件每道工序的加工时间的情况下，安排一种工件的加工顺序，使得 $n$ 个待加工的工件在 $\mathbf { \Sigma } _ { m }$ 台机器上进行加工，满足某种性能指标最优化。本文所使用的性能指标为“最小化最大完工时间”，且该问题需要满足如下假设及约束：

a）机器不发生故障，从零时刻开始加工工件。b)同一台机器在同一时刻只能加工一个工件；同一工件同一时刻只能在一台机器上加工。c)工件的加工工序严格遵守加工时间，一旦开始不得中断；工序间不允许抢占加工。d)每个工件的工艺路线固定，即工件使用机器的序列给定;每个工件在工艺路线中的每个工序的加工时间固定。但，不同工件的工序间无顺序约束。

通常对作业车间调度问题的数学模型描述有线性规划模型（LP）描述、整数规划模型（IP）描述、析取图模型描述。现利用整数规划模型对其进行如下描述：

$$
\operatorname* { m i n } \ \operatorname* { m a x } _ { 1 \leq k \leq m \atop 1 \leq i \leq n } \left\{ c _ { i k } \right\}
$$

$$
s . t . ~ c _ { i k } ^ { ~ } - t _ { i k } ^ { ~ } + M \left( 1 - a _ { i h k } ^ { ~ } \right) \geq c _ { i h } ^ { ~ }
$$

$$
c _ { j k } - c _ { i k } + M \left( 1 - x _ { i j k } \right) \geq t _ { j k }
$$

$$
c _ { i k } \ge 0
$$

$$
a _ { i h k } , x _ { i j k } = 0 , 1
$$

$$
i , j = 1 , 2 , . . . , n ~ ; h , k = 1 , 2 , . . . , m
$$

其中： $t _ { i k }$ 和 $c _ { i k }$ 表示工件 $i$ 在机器 $k$ 上的加工时间和完工时间。式（5）中， $a _ { i h k } = 1$ 表示机器 $h$ 先于机器 $k$ 加工工件 $i$ ; $x _ { i j k } = 1$ 表示工件 $i$ 先于工件 $j$ 在机器 $k$ 上加工；反之，二者皆为 $0 \circ \boldsymbol { \textbf { \em M } }$ （204号为一个大数，则式（2）表示工序的前后约束关系；式（3）表示工序的非阻塞约束关系；式（1）为目标函数，表示性能指标最大完工时间的最小化[12]。

# 2 量子鲸鱼优化算法

# 2.1基本鲸鱼优化算法 (WOA)

WOA算法的仿生学原理受启发于座头鲸独特的觅食行为（bubble-netfeedingmethod)。其原理为，座头鲸发现觅食目标后，沿形似螺旋的路径，通过制造气泡网的方式进行觅食，具体行为包含“气泡网攻击（bubble-netattackingmethod)”、“收缩包围（encirclingprey）”、“随机搜寻（Search for prey）”等三种主要方式。其中气泡网攻击捕食猎物的方式又可依据概率分为“螺旋式位置更新（spiralupdatingposition）”和“缩小包围距离（shrinkingencirclingmechanism）”两个步骤。则座头鲸的觅食行为可进行如下数学描述：

# 2.1.1气泡网攻击

鲸鱼以群体方式觅食，觅食过程中，鲸鱼个体根据随机概率值的大小，对“螺旋式位置更新（spiralupdatingposition:）”和“缩小包围距离（shrinking encircling mechanism）”这两种行

为进行选择。其中，“缩小包围距离（shrinkingencirclingmechanism）”与2.1.2节表述相同，“螺旋式位置更新（spiralupdatingposition）”的数学模型可描述为

$$
\overrightarrow { X } \left( t + 1 \right) = \overrightarrow { D ^ { \prime } } \cdot e ^ { b l } \cdot \cos \left( 2 \pi l \right) + \overrightarrow { X ^ { * } } \left( t \right)
$$

$$
\overrightarrow { D ^ { \prime } } = \left| \overrightarrow { X ^ { * } } \left( t \right) - \overrightarrow { X } \left( t \right) \right|
$$

其中：“.”表示点乘，“」」”表示取绝对值， $\mathbf { \Phi } _ { t }$ 表示当前的迭代次数，向量 $\overrightarrow { X } \left( t \right)$ 表示座头鲸的当前位置，向量 $\overrightarrow { X } \left( t + 1 \right)$ 表示座头鲸迭代更新后的位置，向量 $\overrightarrow { \boldsymbol { X } ^ { * } } ( t )$ 表示鲸群中的最佳觅食位置，参数 $b$ 为常数用来定义对数螺旋的形状，参数 $\mathbf { \xi } _ { l }$ 为[-1,1]之间的随机数，两者共同控制鲸鱼个体的螺旋式位置更新方式。当 $l = - 1$ 时鲸鱼个体距离觅食目标最近，当 $l = 1$ 时鲸鱼个体距离觅食目标最远。

在气泡网攻击过程中，将鲸鱼个体选择位置更新方式的行为概率设为 $p$ 。则气泡网攻击（Bubble-net attacking method）过程可以完整描述为

$$
\overrightarrow { X } \left( t + 1 \right) = \left\{ \begin{array} { l l } { \overrightarrow { X ^ { * } } \left( t \right) - \overrightarrow { A } \cdot \overrightarrow { D } \ , } & { p < p ^ { * } } \\ { \overrightarrow { D ^ { * } } \cdot e ^ { b l } \cdot \cos \left( 2 \pi l \right) + \overrightarrow { X ^ { * } } \left( t \right) \ , } & { p \geq p ^ { * } } \end{array} \right.
$$

2.1.2收缩包围(encircling prey)

根据 2.1.1节描述，当 $p < p ^ { * }$ 时（ $p ^ { * }$ 取0.5)，鲸鱼个体更新自身在空间中的位置，向较优的位置移动，以实现对猎物的收缩包围。其数学模型描述如下：

$$
\overrightarrow { D } = \left| \overrightarrow { C } \cdot \overrightarrow { X ^ { * } } \left( t \right) - \overrightarrow { X } \left( t \right) \right|
$$

$$
\overrightarrow { X } \left( t + 1 \right) = \overrightarrow { X } ^ { * } \left( t \right) - \overrightarrow { A } \cdot \overrightarrow { D }
$$

$$
\stackrel {  } { A } = 2 a \cdot \stackrel {  } { r _ { 1 } } - a
$$

$$
\stackrel { \longrightarrow } { C } = 2 \stackrel { \longrightarrow } { r _ { 2 } }
$$

$$
a = 2 - \frac { 2 t } { T _ { \operatorname* { m a x } } }
$$

其中： $T _ { \mathrm { m a x } }$ 为最大迭代次数， $\mathbf { \Phi } _ { a }$ 的值随着迭代次数的增加由 2向0线性递减； $\stackrel {  } { r _ { 1 } }$ 和 $\stackrel { \longrightarrow } { r _ { 2 } }$ 为（0,1）的随机向量；系数向量 $\vec { c }$ 和 $\vec { A }$ 控制鲸鱼个体的游走方式。需要指出的是，鲸鱼个体采取此种位置更新的前提是 $\left| { \vec { A } } \right|$ 小于1。即,当 $\left| { \vec { A } } \right|$ 小于1时鲸鱼个体 $\overrightarrow { X } \left( t \right)$ 向鲸群中的当前最优位置 $\overrightarrow { \boldsymbol { X } ^ { * } } ( t )$ 靠近。

# 2.1.3 随机搜寻(search for prey)

在 2.1.2节中，式（11)进行位置更新的前提是A小于1。则当A不小于1时，采取如下随机方式进行位置更新，并称之

为随机搜寻（searchforprey)。数学模型描述如下：

$$
\overrightarrow { X } \left( t + 1 \right) = \overrightarrow { X } \ r a n d \ - \overrightarrow { A } \cdot \overrightarrow { D } \ r a n d
$$

$$
\overrightarrow { D } _ { r a n d } = \left| \overrightarrow { C } \cdot \overrightarrow { X } _ { r a n d } - \overrightarrow { X } \left( t \right) \right|
$$

其中： $\overrightarrow { X } _ { r a n d }$ 表示鲸鱼群中随机的其他鲸鱼个体。式(15）(16)表示当A不小于1时，鲸鱼个体随机向其他个体游走靠近。

# 2.2量子鲸鱼优化算法(QWOA)

# 2.2.1量子计算与量子优化

量子计算（quantumcomputation，QC）由Feynman 首先于1982年提出，现已成为国内外学者关注的前沿学科。在量子计算中，信息的基本存储单位称为量子比特（quantumbit)，有别于经典比特，量子比特可以连续、随机地存储于两个极化状态的任意叠加态，按类型可分为单量子比特、双量子比特、多量子比特。其中单量子比特的叠加状态可以表示为

$$
| \varphi \rangle = \alpha | 0 \rangle + \beta | 1 \rangle
$$

$$
\scriptstyle 1 = \left| \alpha \right| ^ { 2 } + \left| \beta \right| ^ { 2 }
$$

其中： $| 0 \rangle$ 及 $\left. 1 \right.$ 为量子计算中微观粒子的两种基本状态的狄拉克记号表示， $\alpha$ 及 $\beta$ 表示量子态的概率幅，为一对复数。

量子计算中对量子状态进行逻辑变换的量子装置称为量子逻辑门，是实现量子计算的基础。常用的量子门有“Hadamard门”“Pauli-X门"“Pauli-Y门”"Pauli-Z门”"相位门”" $\pi / 8$ 门”“量子旋转门”等。其中量子旋转门可表示为

$$
R { \big ( } \theta { \big ) } = { \left[ \begin{array} { l l } { \cos ( \theta ) } & { - \sin ( \theta ) } \\ { \sin ( \theta ) } & { \cos ( \theta ) } \end{array} \right] }
$$

其量子状态的更新过程可表示为

$$
\scriptstyle { \left[ { \begin{array} { l } { \alpha ^ { \prime } } \\ { \beta ^ { \prime } } \end{array} } \right] } = R ( \theta ) { \overline { { \left[ \beta \right] } } }
$$

其中： $\theta$ 为旋转角度， $\begin{array} { r } { \left[ \begin{array} { l } { \alpha ^ { \prime } } \\ { \beta ^ { \prime } } \end{array} \right] } \end{array}$ 为更新后的概率幅[3]。

# 2.2.2量子鲸鱼优化算法

由于基本鲸鱼优化算法存在收敛精度低、容易陷入局部最优等缺点，因此采用量子计算与量子优化的思想对其进行改进，将量子旋转门操作加入基本鲸鱼优化算法中，对其位置更新方式进行改进，以提升基本算法的种群多样性和收敛精度。已知$\overrightarrow { X } \left( t \right)$ 为鲸鱼在搜索空间中的位置，设 $\overrightarrow { Q X } \left( t \right)$ 为鲸鱼经过量子旋转门操作后的位置。

由式（18）可知， $\beta = \sqrt { 1 - \alpha ^ { 2 } }$ ，则量子旋转门的更新过程可以简化为

$$
\alpha ^ { \prime } = \left| \alpha \cdot \cos ( \theta ) - \sqrt { 1 - \alpha ^ { 2 } } \cdot \sin ( \theta ) \right|
$$

相对式（20）而言，式（21）的量子旋转门操作方式被称为单链编码量子旋转门操作[14]。鲸鱼个体经过单链编码量子旋

转门操作后为

$$
\overrightarrow { Q X } \left( t \right) = \left| \overrightarrow { X } \left( t \right) \cdot \cos \left( \theta \right) - \sqrt { 1 - \overrightarrow { X } \left( t \right) ^ { 2 } } \cdot \sin ( \theta ) \right|
$$

当鲸鱼个体经过量子旋转门更新后，将其所对应解的质量与旋转之前解的质量进行对比，并选择其中较优者。将量子鲸鱼优化算法简称之为 QWOA(quantum whales optimizationalgorithm)，其具体步骤可分为：

a)设置迭代次数、种群规模、问题参数。

b)利用随机初始化方法生成初始种群。

c)计算鲸鱼个体的适应度值，找出种群中的当前全局最优解的位置。

d)根据 $p$ 及A的取值情况对鲸鱼个体的每个维度的变量进行位置更新。

e)对鲸鱼个体各维度的变量进行量子旋转门操作。

f)计算d)与e)的更新效果，并对二者进行选择，择优保留。

g)在最大迭代次数内，对鲸鱼群体重复c)\~f)操作。

h）输出求解结果。  
至此，量子鲸鱼优化算法的流程可完整描述如图1所示。

![](images/b7f56f343d44c3e0a3cc7dc8f1d8f1d34c1afecee33811df80a9f86a4f4d3ad8.jpg)  
图1量子鲸鱼优化算法流程

# 3 计算复杂度分析及收敛性证明

# 3.1计算复杂度分析

利用频度估计的方法对量子鲸鱼优化算法进行计算时间复杂度和空间复杂分析。设算法的最大迭代次数为 $T$ ，种群规模为 $P O P$ ，变量的维度为 $D I M$ 。由 2.2.2 节可知，Step4-Step6 为算法共同的原操作，为处于最内层循环的循环体，语句的执行频度均为 $f \left( n \right) = T \cdot P O P \cdot D I M$ ，则算法的渐进时间复杂度T(n)=O(f(n))=O(T·POP·DIM)在算法中，可变的储存空间受到种群规模 $P O P$ 和变量维度 $D I M$ 的影响，则其空间复杂度可表示为 $S \left( n \right) = O \left( f \left( n \right) \right) = O \left( P O P \cdot D I M \right)$

# 3.2算法收敛性证明[15]

利用概率测度法对QWOA算法进行全局收敛性证明。根据全局收敛性准则及定理，要证明算法为全局收敛算法，则算法需要满足如下两个假设：

假设1 $f { \big ( } D ( z , \xi ) { \big ) } \leq f ( z )$ ，并且如果 $\xi \in S$ ，则$f \bigl ( D \bigl ( z , \xi \bigr ) \bigr ) \leq f \bigl ( \xi \bigr ) \circ$ 其中: $f$ 为最小化问题的目标函数， $D$ 为可以保证产生较优最新解的算子或函数。 $z$ 为解空间 $R ^ { \scriptscriptstyle N }$ 的子集 $s$ 的一个点，能够使得函数的值最小化或在 $s$ 上产生可接受的函数值的下确界。 $\xi$ 为算法在样本空间上生成的向量。此假设的意义在于保证优化算法的正确运行，以使算法的解序列收敛于函数 $f$ 在 $s$ 上的下确界，。

假设2对于 $s$ 的任意 Borel 子集 $A$ ，若其概率测度$V \big [ A \big ] > 0$ ，则有 $\prod _ { k = 0 } ^ { \infty } \left( 1 - \mu _ { k } \left[ A \right] \right) = 0 .$ 其中: $\mu _ { k }  { \left[ A \right] }$ 为由分布 $\mu _ { k }$ 产生的对 $A$ 的概率测度。此假设的意义在于，在测度大于0的情况下，算法经无穷多次迭代后，不会错过解空间 $s$ 的任意 Borel子集 $A$ 。

按上述两假设要求对QWOA算法的全局收敛性进行证明。

引理1 QWOA 满足假设1。

证明1根据 2.2.2 节描述，可将函数 $D$ 在QWOA 算法中的描述定义为

$$
\begin{array} { r l } & { D \big ( G _ { t } , X _ { i , t } \big ) = \left\{ \begin{array} { l l } { G _ { t } \ , \qquad } & { f \big ( g \big ( X _ { i , t } \big ) \big ) \geq f \big ( G _ { t } \big ) } \\ { g \big ( X _ { i , t } \big ) \ , } & { f \big ( g \big ( X _ { i , t } \big ) \big ) < f \big ( G _ { t } \big ) } \end{array} \right. } \\ & { \qquad D \big ( G _ { t } , X _ { i , t } \big ) = \left\{ \begin{array} { l l } { G _ { t } \ , \qquad } & { f \big ( g \big ( X _ { i , t } \big ) \big ) \geq f \big ( G _ { t } \big ) } \\ { g \big ( X _ { i , t } \big ) \ , } & { f \big ( g \big ( X _ { i , t } \big ) \big ) < f \big ( G _ { t } \big ) } \end{array} \right. } \end{array}
$$

其中：函数 $D$ 表示对鲸鱼群当前全局最优位置解的计算与选择，连续应用函数 $g$ 对应量子旋转操作函数， $g \left( X _ { i , t } \right)$ 表示鲸鱼个体$i$ 的第 $t$ 次更新后的位置， $G _ { t }$ 为当前的全局最优解的位置。按照本文算法的定义，可知 $G _ { t }$ 所对应的适应度值是单调不增的，且逐渐向解空间的下确界收敛，因此引理1得证。

引理2QWOA满足假设2。

证明2 由上述可知：

$$
g \left( X _ { i , j , t } \right) = \left| X _ { i , j , t } \cdot \cos \left( \theta \right) - \sqrt { 1 - X _ { i , j , t } } \cdot \sin \left( \theta \right) \right|
$$

其中： $X _ { i , j , t }$ 为任意迭代步 $\mathbf { \Phi } _ { t }$ ，第 $i$ 只鲸鱼个体的第 $j$ 维度变量的位置， $g \left( X _ { i , j , t } \right)$ 、 $X _ { i , j , t }$ 的取值范围为[0,1]。则由式（24）可得：

$$
\theta = \operatorname { a r c c o s } \left( \pm g \left( X _ { i , j , t } \right) \right) - \sigma
$$

其中： $\sigma = \operatorname { a r c c o s } ( X _ { i , j , t } )$ 的取值范围为 $[ 0 , \frac { \pi } { 2 } ]$ ，欲使式（25）成立，则 $\theta$ 的取值范围为 $\cdot \frac { - \pi } { 2 } , \frac { 3 \pi } { 2 } ]$ 。设 $X _ { i , j , t }$ 为 $R ^ { \scriptscriptstyle N }$ 第 $j$ 维一点，g(Xi.j,t)为RN第j维不同于Xi,j,的任意点。可知当量子旋转角度落在 $\theta$ 范围内时， $X _ { i , j , t }$ 到达 $g \left( X _ { i , j , t } \right)$ 的概率大于 $\mathbf { \mathrm { ~ 0 ~ } }$ 。

定义 $\mu _ { i , t }$ 为对应于鲸鱼个体 $N$ 维变量的均匀分布，由上述可知，对 $s$ 的任意 Borel 子集 $A$ ，当 $V \big [ A \big ] > 0$ ，可得

$$
0 < \mu _ { i , t } \left[ A \right] < 1
$$

进而可得，由 $\mu _ { t }$ 产生的对 $A$ 的概率测度：

$$
\mu _ { _ t } \left[ A \right] = 1 - \prod _ { \mathrm { i } = 1 } ^ { S } \left( 1 - \mu _ { i , t } \left[ A \right] \right)
$$

通过式（26）（27）得到

$$
\prod _ { t = 0 } ^ { \infty } \left( 1 - \mu _ { t } \left[ A \right] \right) = 0
$$

至此，引理2得证。

所以，根据证明1及证明2可证QWOA算法满足假设1及假设2，为全局收敛算法。

# 4 仿真实验与分析

为了确定和检验鲸鱼优化算法解决作业车间调度问题的性能，本文选取作业车间调度标准测试问题库中的11个测试问题进行求解并与文献[16]中的其他算法作出比较。算法的运算环境为Windows10 专业版32 位操作系统，Intel(R)Core(TM)i7-2600C $\mathrm { P U } \ @ 3 . 4 0$ GHz处理器，4GRAM。算法的编程实现软件为Matlab2015b。

# 4.1WOA与灰狼优化算法和布谷鸟搜索算法的比较

灰狼优化算法[17]（grey wolf optimizer，GWO）由Mirjalili等人于2014 年提出；布谷鸟搜索算法[18]（cuckoo search，CS）由 Yang 等于2009 年提出；二者皆为新兴的智能算法。为了更准确地与GWO和CS算法就JSP问题进行比较，将WOA算法在求解JSP问题时的参数设置与文献[16保持一致，即种群规模为30，最大迭代次数为500，算法独立运行次数为30。得到如表1所示结果。

由表1的结果可知，在种群规模、迭代次数及算法运算次数相同的条件下，WOA算法与GWO算和CS算法在FT06、

LA01、LA06、LA11等问题中都能收敛到当前已知最优解（部分甘特图如图2所示)，但在寻优成功率上WOA算法要劣于GWO 算法和CS算法。

在最小值方面，WOA算法优于CS算法，但劣于GWO 算法。在平均值方面，WOA算法劣于GWO 算法，少部分优于CS 算法。

表1基本鲸鱼优化算法与灰狼优化算法和布谷鸟搜索算法的比较  
标准测试问题FT06-甘特图  
标准测试问题LA01-甘特图  

<html><body><table><tr><td rowspan="2">实例名称 （问题规模）</td><td rowspan="2">已知最优</td><td colspan="3">WOA</td><td colspan="3">GWO</td><td colspan="3">CS</td></tr><tr><td>最小值</td><td>平均值</td><td>寻优成功率</td><td>最小值</td><td>平均值</td><td>寻优成功率</td><td>最小值</td><td>平均值</td><td>寻优成功率</td></tr><tr><td>FT06 (6×6)</td><td>55</td><td>55</td><td>57.8</td><td>16.7%</td><td>55</td><td>57.6</td><td>20%</td><td>55</td><td>55.0</td><td>96.7%</td></tr><tr><td>FT10（10×10)</td><td>930</td><td>1065</td><td>1155.2</td><td>0%</td><td>989</td><td>1061.8</td><td>0%</td><td>1075</td><td>1131.6</td><td>0%</td></tr><tr><td>FT20（20×5)</td><td>1165</td><td>1334</td><td>1467</td><td>0%</td><td>1274</td><td>1378.4</td><td>0%</td><td>1368</td><td>1429.2</td><td>0%</td></tr><tr><td>LA01（10×5)</td><td>666</td><td>666</td><td>689.8</td><td>30%</td><td>666</td><td>673.7</td><td>56.7%</td><td>666</td><td>667.0</td><td>86.7%</td></tr><tr><td>LA06 (15×5)</td><td>926</td><td>926</td><td>933.8</td><td>53.3%</td><td>926</td><td>926.6</td><td>96.7%</td><td>926</td><td>926</td><td>100%</td></tr><tr><td>LA11 (20×5)</td><td>1222</td><td>1222</td><td>1241.0</td><td>40%</td><td>1222</td><td>1222.1</td><td>93.3%</td><td>1222</td><td>1226.8</td><td>56.7%</td></tr><tr><td>LA16（10×10)</td><td>945</td><td>994</td><td>1080.9</td><td>0%</td><td>979</td><td>1026.4</td><td>0%</td><td>1015</td><td>1043.8</td><td>0%</td></tr><tr><td>LA21 (15×10)</td><td>1046</td><td>1256</td><td>1337.6</td><td>0%</td><td>1167</td><td>1235.3</td><td>0%</td><td>1267</td><td>1331.5</td><td>0%</td></tr><tr><td>LA26(20×10)</td><td>1218</td><td>1510</td><td>1598.7</td><td>0%</td><td>1345</td><td>1459.3</td><td>0%</td><td>1487</td><td>1614.6</td><td>0%</td></tr><tr><td>LA31（30×10)</td><td>1784</td><td>1978</td><td>2161.1</td><td>0%</td><td>1871</td><td>1979.8</td><td>0%</td><td>2102</td><td>2198.8</td><td>0%</td></tr><tr><td>LA36（15×15)</td><td>1268</td><td>1555</td><td>1658.5</td><td>0%</td><td>1393</td><td>1501.7</td><td>0%</td><td>1600</td><td>1655</td><td>0%</td></tr></table></body></html>

![](images/7c2e7cb2560843d3a05fb0d9ee08d664e5945ed2a2b905b9d7eaf421f6215eda.jpg)  
图2部分标准测试问题的甘特图

上述结果说明，WOA算法虽然能够成功运用于在作业车间调度问题中，但与GWO与CS算法相比较并无明显优势，仍然存在较大改进空间。因此，本文采用改进后的QWOA算法继续对上述问题进行求解。

# 4.2 QWOA与WOA的比较

利用量子鲸鱼优化算法对上述问题进行求解，将算法的种群规模设置为30，最大迭代次数设置为500，量子旋转的角度设置为rand ${ } ^ { * } 2 ^ { * } \pi$ 。运算结果的对比如表2所示。

表2中，最小值提升、平均值提升、寻优成功率提升的计算方法分别为：（WOA最小值-QWOA最小值)/WOA最小值、（WOA平均值-QWOA平均值）/WOA平均值、QWOA寻优成功率-WOA寻优成功率。

通过QWOA与WOA算法就求解作业车间调度问题的比较可知，量子鲸鱼优化算法对算法的寻优成功率方面有很大的提升，在FT06、LA01、LA06、LA11等问题上的寻优成功率的值均在 $83 \%$ 以上，其中LA01、LA06、LA11的寻优成功率分别高达 $9 3 . 3 \% . 1 0 0 \% . 1 0 0 \%$ ，寻优成功率的平均提升率为 $5 9 . 2 \%$ 且在LA31问题中，收敛到了WOA、GWO、CS算法所无法收敛到的已知最优解，同时在LA16问题中也近乎收敛到已知最优解。

而且，QWOA对最小值及平均值的提升效果也十分显著，取值明显优于WOA、GWO、CS 算法，对WOA算法的最小值及平均值的平均提升率分别为 $10 . 5 \%$ 、 $9 . 7 \%$ 。

同时，图3中QWOA与WOA、CS、GWO等算法寻优曲线的特征对比，说明量子鲸鱼优化算法在求解作业车间调度问题的最优解时，收敛到最优值所需要的迭代次数更少;收敛的精度更高；跳出局部最优进行全局搜索的能力更强。

结合算法寻优的方差情况（受篇幅限制未予展示)，总体而言，利用量子计算与量子优化的思想对基本鲸鱼优化算法进行改进后，量子鲸鱼优化算法在求解作业车间调度优化问题时具有更高的收敛精度、更少的收敛次数和更强的全局搜索能力和 鲁棒性。

表2量子鲸鱼优化算法与基本鲸鱼优化算法的比较  

<html><body><table><tr><td rowspan="2">实例名称 (问题规模）</td><td rowspan="2">已知最优</td><td colspan="3">QWOA</td><td colspan="3">WOA</td><td colspan="3">改进提升效果</td></tr><tr><td>最小值</td><td>平均值</td><td>寻优 成功率</td><td>最小值</td><td>平均值</td><td>寻优 成功率</td><td>最小值</td><td>平均值</td><td>寻优 成功率</td></tr><tr><td>FT06 (6×6)</td><td>55</td><td>55</td><td>55.3</td><td>83.3%</td><td>55</td><td>57.8</td><td>16.7%</td><td>0%</td><td>4.3%</td><td>66.6%</td></tr><tr><td>FT10(10×10)</td><td>930</td><td>966</td><td>1007.2</td><td>0%</td><td>1065</td><td>1155.2</td><td>0%</td><td>9.3%</td><td>12.8%</td><td>0.0%</td></tr><tr><td>FT20(20×5)</td><td>1165</td><td>1207</td><td>1252.1</td><td>0%</td><td>1334</td><td>1467</td><td>0%</td><td>9.5%</td><td>14.6%</td><td>0.0%</td></tr><tr><td>LA01 (10×5)</td><td>666</td><td>666</td><td>667.5</td><td>93.3%</td><td>666</td><td>689.8</td><td>30%</td><td>0%</td><td>3.2%</td><td>63.3%</td></tr><tr><td>LA06（15×5)</td><td>926</td><td>926</td><td>926</td><td>100%</td><td>926</td><td>933.8</td><td>53.3%</td><td>0%</td><td>0.8%</td><td>46.7%</td></tr><tr><td>LA11 (20×5)</td><td>1222</td><td>1222</td><td>1222</td><td>100%</td><td>1222</td><td>1241.0</td><td>40%</td><td>0%</td><td>1.5%</td><td>60.0%</td></tr><tr><td>LA16（10×10)</td><td>945</td><td>946</td><td>994.3</td><td>0%</td><td>994</td><td>1080.9</td><td>0%</td><td>4.8%</td><td>8.0%</td><td>0.0%</td></tr><tr><td>LA21 (15×10)</td><td>1046</td><td>1110</td><td>1146.2</td><td>0%</td><td>1256</td><td>1337.7</td><td>0%</td><td>11.6%</td><td>14.3%</td><td>0.0%</td></tr><tr><td>LA26(20×10)</td><td>1218</td><td>1269</td><td>1331.1</td><td>0%</td><td>1510</td><td>1598.7</td><td>0%</td><td>16%</td><td>16.7%</td><td>0.0%</td></tr><tr><td>LA31(30×10)</td><td>1784</td><td>1784</td><td>1846.2</td><td>6.7%</td><td>1978</td><td>2161.1</td><td>0%</td><td>9.8%</td><td>14.6%</td><td>6.7%</td></tr><tr><td>LA36 (15×15)</td><td>1268</td><td>1357</td><td>1403.8</td><td>0%</td><td>1555</td><td>1658.5</td><td>0%</td><td>12.7%</td><td>15.4%</td><td>0.0%</td></tr></table></body></html>

![](images/08f93889096075c53a7907292fafbadc7ccd6015dbd3a9eed720bd46bf025f16.jpg)  
图3部分标准测试问题的寻优曲线对比

# 5 结束语

鲸鱼优化算法（WOA）是新兴的群智能算法，多应用于连续优化问题，在作业车间调度（JSP）这类离散组合优化问题中较少应用。本文验证了WOA算法解决JSP问题的可行性，并发现了其在解决JSP问题时的缺陷。为了克服WOA算法解决JSP问题时的缺陷，本文提出了一种量子鲸鱼优化算法

（QWOA)，并对其进行了计算复杂度分析、收敛性证明及实验仿真分析。

通过对比分析发现，本文所提出的QWOA算法在解决JSP问题时，具有迭代次数少、收敛精度高、全局搜索能力强等优点。

在未来的工作中，本文将利用WOA算法对多目标组合优化问题进行研究，并进一步提升WOA算法的应用性能。

# 参考文献：

[1]Cheng TC E,Peng B,Lu Z.A hybrid evolutionary algorithm to solve the job shop scheduling problem [J].Annals of Operations Research,2016,242 (2):223-237.   
[2]Mirjalili S,Lewis A.The whale optimization algorithm [J].Advances in Engineering Software,2016,95: 51-67.   
[3]Trivedi IN,Bhoye M,Bhesdadiya R H,et al.An emission constraint environment dispatch problem solution with microgrid using whale optimization algorithm [C]//Proc of Power Systems Conference.2017.   
[4]Prakash D B,Lakshminarayana C.Optimal siting of capacitors in radial distribution network using whale optimization algorithm [J].Alexandria Engineering Journal, 2016.   
[5]Dao T K,Pan T S,Pan JS.A multi-objective optimal mobile robot path planning based on whale optimization algorithm [C]// Proc of IEEE International Conference on Signal Processing.2017:337-342.   
[6]Kaveh A,Ghazaan M I. Enhanced whale optimization algorithm for sizing optimization of skeletal structures [J].Mechanics Based Design of Structures & Machines,2017,45:345-362.   
[7]Oliva D,Aziz MAE,Hassanien AE.Parameter estimation of photovoltaic cells using an improved chaotic whale optimization algorithm[J].Applied Energy,2017,200:141-154.   
[8]Jangir P,Trivedi IN,Jangir N,et al.A novel adaptive whale optimization algorithm for global optimization [J].Indian Journal of Science & Technology,2016,9 (38).   
[9]Ling Y,Zhou Y,Luo Q.Lévy Flight trajectory-based whale optimization algorithm for global optimization [J].IEEE Access,2017,5(99): 6168-6186.   
[10]钟明辉，龙文．一种随机调整控制参数的鲸鱼优化算法[J].科学技术 与工程,2017,17(12):68-73.   
[11]刘竹松，李生．正余混沌双弦鲸鱼优化算法[J].计算机工程与应用, 2017.   
[12] Cheng TCE,Peng B,Lu Z.Ahybrid evolutionary algorithm to solve the job shop scheduling problem [J].Annals of Operations Research,2016,242 (2): 223-237.   
[13]Dey S,Saha I,Bhattacharyya S,et al.Multi-level thresholding using quantum inspired meta-heuristics [J].Knowledge-Based Systems,2014, 67 (3): 373-400.   
[14]高洪元，刁鸣.量子群智能及其在通信技术中的应用[M].北京：电子 工业出版社,2016.   
[15]Fang W, Sun J,Chen H,et al.A decentralized quantum-inspired particle swarm optimization algorithm with cellular structured population [J]. Information Sciences,2016,330 (C):19-48.   
[16]姚远远，叶春明．求解作业车间调度问题的改进混合灰狼优化算法 [J/OL].计算机应用研究,2018,35(5)(2017-06-14).http://kns.cnki. net/kcms/detail/51.1196.TP.20170614.1317.050.html.   
[17] Mirjalili S.How effective is the Grey Wolf optimizer in training multi-layer perceptrons [J].Applied Intelligence,2015,43(1):150-161.   
[18] Li X,Yin M.Modified cuckoo search algorithm with self adaptive parameter method [J]. Information Sciences,2015,298 (C): 80-97.