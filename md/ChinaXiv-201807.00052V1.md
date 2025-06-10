# 基于二进制烟花优化算法的认知无线网络频谱分配

杨军，张达敏，何庆，潘志远(贵州大学 大数据与信息工程学院，贵阳 550025)

摘要：针对当前无线频谱资源稀缺和利用率低的问题，提出一种基于二进制烟花优化算法的频谱分配方法。每个烟花个体进行分布式爆炸搜索，并对最优烟花的爆炸半径采用改进公式动态更新；在变异环节中，针对粒子间信息交流不足的缺点，引入遗传算法的交叉变异算子，进一步增强种群多样性；对选出的最优个体使用Metropolis准则进行模拟退火扰动，避免陷入局部最优。仿真实验表明，二进制烟花优化算法在认知无线网络的频谱分配中具有寻优精度高，收敛速度快的特点，较好地实现网络效益和用户比例公平性的最大化。

关键词：认知无线网络；频谱分配；二进制烟花优化算法；Metropolis准则 中图分类号：TP393 doi: 10.3969/j.issn.1001-3695.2018.04.0252

# Spectrum allocation of cognitive radio network based on binary fireworks optimization algorithm

Yang Jun, Zhang Damin†, He Qing, Pan Zhiyuan (College of Big Data & Information Engineering Guizhou University,Guiyang 55oo25,China)

Abstract: Acording to the scarcityof wireless spectrum resources and low utilization rate,this paper presented a spectrum allocation method basedonbinar fireworksoptimizationalgorithm.Each fireworkindividualcariesoutdistributed explosion search,and the method proposed an improved formula to update theexplosion radius of theoptimal fireworks dynamialy. Forthelack of informationexchangebetween particles inthevariation process,thealgorithm introduced thecrossver operatorand mutation operatorofthe genetic algorithm tofurther enhance the population diversity.Inorder toavoid faling intoa local optimum,the algorithmused simulated annealing with Metropolis criterion to perturb the selected optimal individuals.The simulation experiment shows that the method has thecharacteristicsof high optimization accuracyand high convergence speed.Itcanachieve the maximizationof the network efficiencyandthe proportional fairness among different users.

Key words:cognitiveradio network; spectrum allcation; binary fireworks optimization algorithm; metropolis criterion

# 0 引言

由于无线通信技术的迅速发展，无线频谱资源稀缺问题日益突出，并且频谱利用率低下，存在较多的频谱空洞错误!未找到引用源。。认知无线网络[1]（cognitive radio network，CRN）是一种具有认知过程的网络，它能分辨当前的网络状态，然后根据这些状态进行规划、决策和响应。针对认知无线网络提出的动态频谱分配方法可以很好的解决以上问题，其核心思想是在不影响主用户（授权用户）正常通信的情况下，次用户（认知用户）可以通过实时感知技术机会使用主用户的频谱，从而有效的分配可用的频谱资源，使得网络整体性能达到最优错误！未找到

# 引用源。。

目前，国内外的学者们对认知无线网络的频谱分配进行了广泛的研究，针对认知无线网络的体系架构和频谱接入等技术，现有的频谱分配方法主要有博弈论错误!未找到引用源。，竞价拍卖理论错误!未找到引用源。和图论着色理论错误!未找到引用源。等。考虑到 CRN节点之间的干扰关系，图论着色理论可以形象地表示出用户之间的地理位置，从而实现频谱资源的规划与管理，是一种方便有效的方法。由于认知无线网络的频谱分配是在考虑用户公平性的约束条件下进行，是一种典型的NP难问题，所以也可使用群智能算法用于解决。近年来，学者们将图论着色理论与智能优化算法相结合，并应用到频谱分配当中，取得了很多的成果。文献[6，7]提出基于遗传（genetic algorithm,GA）和量子遗传算法的频谱分配解决方案，但是遗传和量子遗传算法都容易早熟收敛，影响系统的最终寻优结果。文献[8，9]在认知无线网络的频谱分配中引入了免疫克隆选择算法(immunecloneselection,ICS)，很好地解决了种群进化后期缺乏多样性的问题，但是收敛速度不够快。文献[10]采用粒子群算法(particle swarmoptimization，PSO)进行频谱分配，虽然有较快的收敛速度，但是容易陷入局部最优。除此之外，还有很多其他的经典智能算法在CRN 频谱分配问题中同样也得到了广泛的应用，如蚁群算法错误!未找到引用源。、蜂群算法错误!未找到引用源。、布谷鸟算法错误!未找到引用源。等。但是这些方法都很难在收敛速度和寻优能力之间取得平衡，进而会影响最终的频谱分配结果以及网络性能。

本文以图论着色频谱分配模型为基础，以网络效益以及用户之间的比例公平性为优化目标，对传统二进制烟花算法错误!未找到引用源。\~错误!未找到引用源。的爆炸半径和变异算子进行改进，并加入Metropolis准则进行择优，提出了一种基于二进制烟花优化算法（binary fireworks optimization algorithm,BFOA）的频谱分配解决方案。通过实验仿真比较分析，证明了BFOA算法解决该问题的有效性和优越性。

# 1 认知无线网络频谱分配模型

# 1.1频谱分配图论模型

如图1所示，图论着色模型以无向图的形式诠释认知无线网络的拓扑结构，展现用户之间的地理位置关系以及互相存在的干扰。

![](images/8d9597b53ada963f539a647d21dd5f42ada67078c9604204b6e73974584153d2.jpg)  
图1认知无线网络拓扑结构

图中，主用户括号内为其授权频谱，认知用户括号内为其感知到的可用频谱， $r \dot { i } _ { i , m }$ 和 ${ r n } _ { { n , m } }$ 分别为各自的信号覆盖半径。假设在一片 $X * Y$ 的区域中，存在有 $I$ 个主用户和 $N$ 个认知用户，且其地理位置是随机分布的，区域内可用频谱的个数为 $M$ 。主用户使用固定的授权频谱，认知用户通过认知无线网络的频谱感知技术感知当前主用户的可用频谱，并机会接入进行使用，在满足频谱分配规则的前提下，认知用户允许同时使用多个频谱。当主用户 $i \big ( i = 1 , 2 , . . . , I \big )$ 分配的授权频谱为 $m \left( m = 1 , 2 , . . . , M \right)$ 时，则主用户 $i$ 在频谱 $m$ 上的覆盖范围是以 $i$ 为中心， $r \dot { \iota } _ { i , m }$ 为半径的圆形区域。若认知用户 $n { \big ( } n = 1 , 2 , . . . , N { \big ) }$ 机会接入了频谱 $m$ ，则认知用户 $n$ 在频谱 $m$ 上的覆盖范围是以 $n$ 为中心， ${ r n } _ { n , m }$ 为半径的圆形区域。假定用户间的干扰仅由地理位置上的相互距离决定。如果主用户 $i$ 和认知用户 $n$ 或者认知用户 $n$ 和 $k \left( k = 1 , 2 , . . . , N \right)$ 在同一频谱 $m$ 上的覆盖范围存在重叠则表明将产生干扰。

# 1.2数学建模

由于频谱分配的周期相对于网络环境的变化时间很短，所以假定在进行一次频谱分配的过程中，网络拓扑结构不发生改变。认知无线网络的频谱分配可以转化为数学模型进行表达。可由以下矩阵表示：

a)可用频谱矩阵 $L = \left\{ l _ { n , m } \left| l _ { n , m } \in \{ 0 , 1 \} \right. \right\} _ { N \times M }$ ，表示认知用户 $n$ 是否可以使用频谱 $m$ 。 $l _ { n , m } = 1$ 则表示可以，相反， $l _ { n , m } = 0$ 则表示不可以。

b)效益矩阵 $B = \left\{ b _ { n , m } \middle | b _ { n , m } = \left( r n _ { n , m } \right) ^ { 2 } \right\} _ { N \times M }$ ，表示认知用户 $n$ 使用频谱 $m$ （ $l _ { n , m } = 1$ ）时所得的效益，且效益为正。一般将网络带宽作为频谱效益。

c)干扰矩阵 $C = \{ c _ { n , k , m } | c _ { n , k , m } \in \{ 0 , 1 \} \} _ { N \times N \times M }$ ，表示不同的认知用户$n$ 和 $k$ 在使用同一频谱 $m$ 时是否会存在干扰。 $c _ { n , k , m } = 1$ 则表示存在干扰， $c _ { n , k , m } = 0$ 则表示不存在。

d)无干扰分配矩阵 $A = \{ a _ { n , m }  a _ { n , m } \in \{ 0 , 1 \} \} _ { N \times M }$ ，表示在可用频谱矩阵 $\boldsymbol { L }$ 和干扰矩阵 $c$ 都满足的条件下，频谱 $\mid m$ 是否可以分配给认知用户 $n$ 。 $a _ { n , m } = 1$ 表示可以， $a _ { n , m } = 0$ 则表示不可以。无干扰分配矩阵须满足如下约束条件：

$$
\begin{array} { r } { a _ { n , m } * a _ { k , m } = 0 \bigcap c _ { n , k , m } = 1 } \end{array}
$$

$$
\forall 1 \leq n , k \leq N \ , 1 \leq m \leq M
$$

由最终的无干扰分配矩阵和效益矩阵，可以得出频谱分配完成后网络中每个认知用户所得的效益。即

$$
R _ { n } = \sum _ { m = 1 } ^ { M } a _ { n , m } * b _ { n , m }
$$

网络获得的总效益即为所有认知用户获得的效益总和：

$$
\begin{array} { c } { { \displaystyle { F _ { s u m } = \sum _ { n = 1 } ^ { N } R _ { n } } } } \\ { { \displaystyle { \phantom { \sum _ { n = 1 } ^ { N } \sum _ { m = 1 } ^ { M } a _ { n , m } * b _ { n , m } } } } } \end{array}
$$

由网络获得的总效益不难得出其平均效益：

$$
\begin{array} { c } { { \displaystyle F _ { m e a n } = \frac { 1 } { N } \sum _ { n = 1 } ^ { N } R _ { n } } } \\ { { \displaystyle \qquad = \frac { 1 } { N } \sum _ { n = 1 } ^ { N } \sum _ { m = 1 } ^ { M } a _ { n , m } * b _ { n , m } } } \end{array}
$$

为了衡量每次频谱分配结果的公平性，即网络中各认知用户获得的效益是否均衡，可以用网络的比例公平性函数表示误！未找到引用源。 ：

$$
\begin{array} { r l r } {  { F _ { f a i r n e s s } = ( \prod _ { n = 1 } ^ { N } ( R _ { n } + 1 0 ^ { - 4 } ) ) ^ { \frac { 1 } { N } } } } \\ & { } & { = ( \prod _ { n = 1 } ^ { N } ( \sum _ { m = 1 } ^ { M } a _ { n , m } * b _ { n , m } + 1 0 ^ { - 4 } ) ) ^ { \frac { 1 } { N } } } \end{array}
$$

通过以上的描述和分析可以看出，网络获得的效益和用户间的比例公平性可以用来反映和评价认知无线网络频谱分配的结果，即可以直接作为算法执行过程中的目标函数。

# 2 BFOA算法设计

传统烟花算法由爆炸算子、变异算子和选择策略组成，且常用于连续变量的问题中。为适应离散化的频谱分配应用，提出一种全新的二进制烟花优化算法。在变异算子中针对粒子信息交流不足引入了经典遗传算法的交叉变异操作，进一步增强了种群的多样性。同时对选出的最优解以及将要进行下一轮爆炸的最优烟花运用模拟退火中的Metropolis准则进行随机扰动，起到避免算法陷入局部最优的作用，并提高了收敛速度。此外，将每轮迭代的最优烟花固定爆炸半径改为动态递减，利于自适应搜索到全局最优解。

# 2.1爆炸算子

种群中的每个个体属于一个烟花，烟花在发生爆炸时会产生大量的火花。在频谱分配问题中，适应度值较大(高质量)的烟花爆炸范围较小，产生的火花较多。相反，适应度值较小（低质量）的烟花爆炸范围就较大，产生的火花也较少。前者具有很好的小范围“挖掘能力”，后者则具有强大的大范围“探索能力”。因此，种群中的每个烟花根据各自匹配的适应度值进行爆炸，最终可以使得种群在全局搜索能力和局部搜索能力之间达到平衡。

每个烟花的爆炸半径和产生的火花数量由自身的适应度值和种群中其他烟花的适应度值共同决定，烟花i发生爆炸时对应的爆炸半径和火花数量分别为

$$
A _ { i } = c e i l \left( \hat { A } * \frac { f _ { \operatorname* { m a x } } - f \left( x _ { i } \right) + \varepsilon } { \displaystyle \sum _ { i = 1 } ^ { Z } \left( f _ { \operatorname* { m a x } } - f \left( x _ { i } \right) \right) + \varepsilon } \right)
$$

$$
S _ { i } = c e i l \left( \hat { S } * \frac { f \left( x _ { i } \right) - f _ { \operatorname* { m i n } } + \varepsilon } { \displaystyle \sum _ { i = 1 } ^ { Z } \left( f \left( x _ { i } \right) - f _ { \operatorname* { m i n } } \right) + \varepsilon } \right)
$$

其中：ceil表示向上取整， $\hat { A }$ 为二进制编码维数， $\hat { s }$ 为常数，用于控制产生的火花总数。 $z$ 为种群规模， $f _ { \mathrm { m a x } }$ 和 $f _ { \mathrm { m i n } }$ 分别为种群中最大和最小的适应度值。 $\boldsymbol { \varepsilon }$ 为机器精度，取 $\varepsilon = 1 0 ^ { - 6 }$ 0

当第 $i$ 个烟花发生爆炸时，产生的第 $j$ 个火花表示如下：

$$
\boldsymbol { x } _ { i } ^ { j } = \Theta \big ( x _ { i } , \boldsymbol { P } , \boldsymbol { r } _ { i } ^ { j } \big )
$$

$\Theta { \left( x _ { i } , P , r _ { i } ^ { j } \right) }$ 为二进制转换算子，表示从角标集合 $P = \left\{ 1 , 2 , . . . , \hat { A } \right\}$ 中随机选出 $r _ { i } ^ { j }$ 个元素，并在二进制编码的字符串 $x _ { i }$ 中对选出的角标对应的字符进行0-1替换。其中 $r _ { i } ^ { j }$ 为爆炸算子步长：

$$
r _ { i } ^ { j } = c e i l \left( A _ { i } * r a n d + \varepsilon \right)
$$

表示第 $i$ 个烟花的第 $j$ 个火花半径，满足 $0 < r _ { i } ^ { j } \le A _ { i }$ 。rand 是[0,1]上服从均匀分布的随机数。

# 2.2爆炸半径的改进

每个烟花的爆炸半径大小都与自身的质量密切相关，质量最优的烟花半径最小，且其周围的粒子相比其他烟花也最接近全局最优。所以需要对其加强深度的“挖掘”，才能提高目标优化的精度，因此质量最优的烟花爆炸产生的火花数量也是最多的。但是通过式（6）计算烟花的爆炸半径时，会容易发现，最优烟花常常会由于半径值过于偏小而难以产生出最多的火花错误!未找到引用源。

针对这一问题，本文在Logistic函数的基础上对最优烟花的爆炸半径进行改进。引入自适应搜索策略，使其前期侧重于全局搜索，而后期侧重于局部搜索。Logistic函数是一种常见的S型曲线，能够较好地反映事物有界增长的规律，通过对其积分简化可得到：

$$
y = { \frac { 1 } { 1 + e ^ { x } } }
$$

变形可得最优烟花半径公式：

$$
A _ { _ { o } } \left( g \right) = c e i l \left( r _ { \operatorname* { m i n } } + \frac { r _ { \operatorname* { m a x } } - r _ { \operatorname* { m i n } } } { 1 + e ^ { \alpha \left( g - \frac { G } { 2 } \right) } } \right)
$$

其中： $A _ { o } \left( g \right)$ 为每次迭代过程中最优烟花的半径， $r _ { \mathrm { m a x } }$ 和 $r _ { \mathrm { m i n } }$ 分别为进化开始和结束时设定的最优烟花半径。 $\sigma$ 为进化总代数，$\alpha$ 为控制参数， $\scriptstyle 0 < \alpha < 1$ 。

由式（11）可以看出，随着进化代数的不断增加，最优烟花的半径呈非线性递减，前半周期半径较大，下降较快，后半周期递减速率越来越缓慢，且逐渐趋向于最小半径值。这样有利于算法在迭代初期进行空间内的广泛搜索，而末期能够在全局最优附近进行进一步精确的局部搜索。

# 2.3改进变异算子

传统烟花算法的变异算子通常采用高斯变异，但高斯变异引导个体跳出局部最优解的能力较弱，且一般应用于实数编码问题。此外，烟花算法属于一种并行弥漫式爆炸搜索的算法，在寻优过程中粒子间缺乏信息交流，多样性有待进一步提高。本文引入遗传算法中的二进制交叉变异算子对其进行改进，加强了粒子间的信息传递和资源交互，更好地增强了种群的多样性。

当烟花完成爆炸后，搜索空间中存在烟花和爆炸火花两种元素。具体实现过程如下：

a）用目标函数评价所有烟花和爆炸火花的适应度值并排序。

b)从中选择合适的个体以概率 $p _ { c }$ 和 $p _ { { \scriptscriptstyle m } }$ 执行交叉变异操作：

$$
\mathrm { d i m } = c e i l ( { \hat { A } } ^ { * } r a n d ) \quad i f r a n d \leq p _ { c }
$$

$$
x _ { i , d } ^ { c } = \left\{ { \begin{array} { c c } { x _ { j , d } } & { i f d \in r a n d p e r m ( { \hat { A } } , \dim ) } \\ { x _ { i , d } } & { o t h e r w i s e } \end{array} } \right.
$$

$$
x _ { i , d } ^ { m } = \left\{ \begin{array} { c c } { 1 - x _ { i , d } } & { i f ~ r a n d \leq p _ { m } } \\ { x _ { i , d } } & { o t h e r w i s e } \end{array} \right.
$$

其中： $\boldsymbol { x } _ { i , d } ^ { c }$ 和 $x _ { i , d } ^ { m }$ 分别表示交叉和变异后第 $i$ 个个体第 $^ d$ 维的值。randperm $\hat { \boldsymbol A } , \mathrm { d i m } )$ 表示从维数 $\hat { A }$ 中随机选择 $\dim$ 个不重复的维参与交叉。

参与交叉变异的元素由两部分组成，一部分是适应度值排名靠前的个体，另一部分则在剩下的群体中随机选出相同数量的个体。这样更有利于产生优质个体，同时也没有放弃适应度差的个体身上的优秀基因，增强了个体之间的信息共享。

# 2.4选择策略

以上过程结束后，需要对当前候选者集合进行一定规则的筛选便于将种群中的优秀信息传递给下一代，继续作为烟花进行爆炸。其中候选者集合包括烟花，爆炸火花和变异火花。首先，采用精英保留机制，将适应度最好的烟花（火花）确定性地保留下来，剩余个体将使用轮盘赌的方式从候选集合中选取，

个体 $x _ { i }$ 被选中的概率为

$$
p \left( x _ { i } \right) = \frac { D \left( x _ { i } \right) } { \displaystyle \sum _ { j = 1 } ^ { K } D \left( x _ { j } \right) }
$$

$$
D \left( x _ { i } \right) = \sum _ { j = 1 } ^ { K } d \left( x _ { i } , x _ { j } \right)
$$

其中： $D \big ( x _ { i } \big )$ 为个体 $x _ { i }$ 与其他候选者之间的海明距离之和， $K$ 为参与轮盘赌选择的候选者数量。

# 2.5Metropolis 接受准则

为了使算法不易陷入局部最优，本文在烟花完成爆炸变异后引入了模拟退火算法的Metropolis准则，对选出的精英个体进行进一步优化。模拟退火算法通过模拟热力学中经典粒子系统的降温过程来求解组合优化问题中的极值问题。其核心思想是对当前的状态进行随机扰动产生一个新状态，并通过Metropolis准则判断是否接受该新状态。由于频谱分配问题属于求解最大值问题，故Metropolis 准则如下：

$$
p = \left\{ \begin{array} { c c } { 1 } & { f \left( x _ { i } \right) \leq f \left( x _ { j } \right) } \\ { \displaystyle \exp \left( - \frac { f \left( x _ { i } \right) - f \left( x _ { j } \right) } { T } \right) } & { f \left( x _ { i } \right) > f \left( x _ { j } \right) } \end{array} \right.
$$

其中： $x _ { i }$ 为当前解， $\boldsymbol { x } _ { j }$ 为新产生的解， $f \left( x \right)$ 为目标函数， $T$ 为初始温度。Metropolis准则不但能够接受优化解，而且还能够以一定的概率接受恶化解。当温度较高时，算法接受恶化解的概率较大；随着温度的递减，接受恶化解的概率逐渐减小，直至最后趋于0。从而更有利于算法跳出局部极值以趋向于全局最优。本文采用文献错误！未找到引用源。中的降温函数来控制温度的下降幅度：

$$
T \left( t + 1 \right) = T \left( t \right) * \beta ^ { 1 / s q r t \left( q \right) }
$$

其中： $0 < \beta < 1$ 为降温系数， $q$ 为当前迭代次数。通过此函数进行降温，可以达到退火初期降温快，而在后期下降缓慢的效果。并且，为避免在退火过程中因概率接受恶化解而错失当前为止的最优解，在迭代过程中添加了“bestsofar”记忆单元。

# 3 基于BFOA的频谱分配方案

在本文提出的基于二进制烟花优化算法的频谱分配方法中，每个烟花和产生的火花（爆炸火花、变异火花）代表一种可能的频谱分配策略。通过对烟花和火花的干扰约束处理后，用相应的目标函数进行评价从而最终选出最优的频谱分配方案。

# 3.1种群编码

认知无线网络的频谱分配问题采用二进制编码的方式。当可用频谱矩阵 $L$ 中的元素 $l _ { n , m } = 1$ 时，经过约束条件的处理，对应的无干扰分配矩阵 $A$ 中元素 $\boldsymbol { a } _ { n , m }$ 可能为0也可能为1。但$l _ { n , m } = 0$ 时， $\boldsymbol { a } _ { n , m }$ 必为0，表示频谱从刚开始就不可用。因此，可以只对 $\textbf { \em L }$ 矩阵中为1的元素进行编码，有助于提高计算速度。每个参与计算的烟花和火花个体其实是频谱分配矩阵到二进制字符串的映射，是一种可能的频谱分配方案。字符串长度即为$l = \sum _ { n = 1 } ^ { N } \sum _ { m = 1 } ^ { M } l _ { n , m }$ ，编码顺序遵循先 $n$ 递增，后 $m$ 递增的规则。

# 3.2 干扰约束处理

在频谱分配过程中，并非每一种分配方案都是可行的。因为可能会出现多个认知用户使用同一频谱时产生干扰冲突的问题，故需要进行干扰约束处理工作。当认知用户 $n$ 和 $k$ 在使用频谱 $m$ 时存在干扰，即干扰矩阵元素 $c _ { n , k , m } = 1$ ，则频谱 $m$ 只允许一个用户接入。此时需检查分配矩阵 $A$ 的第 $m$ 列第 $n$ 行和第 $k$ 行元素，若都为1则需处理：比较两行的元素之和 $s u m \big ( n \big )$ 和$s u m ( k )$ ，将最大者对应的 $m$ 列元素置换为0。即若$s u m ( n ) > s u m ( k )$ ，则将第 $n$ 行 $m$ 列改为0；若 $s u m ( n ) = s u m ( k )$ ，则随机选一改为0。经过干扰处理后的分配矩阵 $A$ 就是满足矩阵 $\boldsymbol { L }$ 和 $c$ 约束条件的有效解。

# 3.3算法实现流程

基于二进制烟花优化算法的频谱分配具体实现流程如下：

a)生成矩阵。由随机生成的CRN网络拓扑结构图得出可用频谱矩阵 $\textbf { \em L }$ ，效益矩阵 $B$ 以及干扰矩阵 $c$ 0

b)初始化参数。输入种群规模 $z$ ，最大迭代次数 $\boldsymbol { G }$ ，交叉变异概率 $p _ { c }$ 和 $p _ { { \scriptscriptstyle m } }$ ，初始温度 $T$ 等，并随机产生初始烟花种群$\boldsymbol { x } _ { i } ^ { g } = [ x _ { i 1 } ^ { g } , x _ { i 2 } ^ { g } , . . . , x _ { i l } ^ { g } ]$ ，使用相应的目标函数计算初始种群的适应度值。

c)终止条件判断。检测是否达到最大迭代次数 $\boldsymbol { G }$ ，若达到则退出循环，将当前最优烟花进行分配矩阵映射，输出最优频谱分配方案；若没有则继续执行d)。

d)爆炸操作。根据计算得出的爆炸半径 $A _ { i }$ 、 $A _ { o } \left( g \right)$ 和火花数量 $S _ { i }$ 对每个烟花进行爆炸，生成对应的火花 $x _ { i } ^ { j }$ 。

e)变异操作。从烟花和产生的火花集合中选出适应度值排名靠前的 $5 0 \% z$ 个元素，再从剩下的个体中随机选出 $5 0 \% Z$ 个元素组成参与变异的群体，以交叉概率 $p _ { c }$ 和变异概率 $p _ { { \scriptscriptstyle m } }$ 执行交叉变异操作，生成变异火花。

f)约束处理与择优。对烟花和产生的爆炸火花、变异火花群体进行干扰检查和约束处理。并计算适应度，选出最优个体。

g)搜索全局最优。利用Metropolis接收准则对选出的最优个体进行扰动更新并约束处理，进一步搜索将进行下一轮爆炸的全局最优烟花。

h)选择更新。将g)中选出的最优烟花对f)中的最优个体进行替换，并与其剩下个体组成集合。使用轮盘赌的方式产生其他 $N { - } 1$ 个进行下一次爆炸的烟花种群。

i) $g = g + 1$ ，转至c)。

# 4 仿真及结果分析

利用MATLAB建立仿真实验环境。在相同的网络拓扑结构基础上，将提出的二进制烟花优化算法（BFOA）与传统解决该问题的遗传（GA）、粒子群（PSO）和免疫克隆选择（ICS）算法进行比较，分别通过系统网络效益、用户的比例公平性来分析四种算法的性能错误!未找到引用源。错误！未找到引用源。，以及当网络环境中关键参数发生变化时对算法性能产生的影响。验证BFOA用于解决认知无线网络频谱分配问题的可行性与优越性。在给定的矩形网络区域中，随机分布 $I$ 个主用户， $N$ 个认知用户和M个可用频谱。认知用户通过动态接入与主用户共享频谱。经过大量实验得出如下的参数设置：进化总代数 $G = 2 0 0$ ，种群规模$Z = 1 0$ ，烟花总数为100， $r _ { \mathrm { m a x } } = 0 . 2 5 ~ l$ ， $r _ { \mathrm { m i n } } = 0 . 0 1 ~ l$ ， $\alpha = 0 . 0 5$ ，交叉变异概率 $p _ { c } = 0 . 6$ ， $p _ { { \scriptscriptstyle m } } = 0 . 1$ ，降温系数 $_ { \beta = 0 . 9 8 }$ 。

# 4.1算法优化性能比较

本组实验将比较四种算法的寻优能力和收敛性能。图2是各算法在40次不同的用户（主用户、认知用户）位置分布图下进行频谱分配时网络总效益的寻优结果。主用户 $I$ 、认知用户$N$ 、可用频谱 $M$ 数量均设置为15。表1对40次的寻优结果分别进行求和和均值比较。从图2和表1中可看出，本文提出的二进制烟花优化算法获得的网络总效益最大，且与其他算法的效益差值较明显。

460440我 320 4 ?BFOA300 u -ICs -PSO.GA2800 5 10 15 20 25 30 35 40实验次数

表140次网络总效益比较  

<html><body><table><tr><td>算法</td><td>40次效益总和</td><td>40 次效益均值</td></tr><tr><td>BFOA</td><td>15554.4</td><td>388.86</td></tr><tr><td>PSO</td><td>14972.0</td><td>374.30</td></tr><tr><td>ICS</td><td>14398.9</td><td>359.97</td></tr><tr><td>GA</td><td>14138.6</td><td>353.47</td></tr></table></body></html>

图3和4分别是四种算法在进行一次频谱分配时网络总效益和用户比例公平性的优化过程。主用户 $\boldsymbol { I }$ 、认知用户 $N$ 、可用频谱M数量均设置为10。由图可知，BFOA算法在优化过程中整体性能高于其他三种算法。从寻优精度上看，BFOA算法寻得的最优值最大，其次分别是PSO、ICS、GA 算法。BFOA最终的网络总效益和比例公平性收敛值比效果表现最差的GA分别高出 $8 . 3 \%$ 和 $8 . 9 \%$ 。由于烟花算法属于分布式爆炸搜索算法，具有执行效率高的特点，所以在进化开始时的寻优值就已经高出其他算法。从收敛性能上来看，BFOA算法在图3和图4 中分别在80代和60代左右就已经收敛，具有最快的收敛速度，且能很好地跳出局部最优。这是因为在每次迭代过程中对选出的最优烟花进行了一定程度的模拟退火扰动，使其能够更快地寻找到全局最优解。

![](images/3b8b67399dbe15fff5074c45b5362d7ef5b85948095445bb1ad9715b4ff96c39.jpg)  
图3网络总效益优化过程

![](images/6a2f29894c23863e24dbf968f63e321135ee5b3c614fcf26b5744c3e17184817.jpg)  
图4比例公平性优化过程

# 4.2可用频谱数量对算法影响的比较

当网络环境中的可用频谱数量发生变化时，算法的性能将会受到相应的影响。图5和6分别验证了在不同频谱数时网络平均效益和比例公平性的变化情况。这里认知用户数取 $N = 1 5$ 主用户 $I$ 和可用频谱M数量变化区间为5到30。在图5、6中，随着可用频谱数量的增加，系统网络平均效益和比例公平性都在不断提升。这是由于当频谱数量增加时，系统的频谱冲突和干扰都将会减轻。在变化的过程中，前期频谱数较少，四种算法得出的收益差距不是很大；后期频谱数越来越多时，可以较明显的看出，本文的BFOA算法和PSO算法获得的平均效益和比例公平性远大于ICS和GA算法，且BFOA的值比PSO更大，有效地证明了BFOA算法的优越性。

![](images/9ef468c4e0d8b941a6aa6eb291a1a2204bdb6e9e7b134981bd868071edb33c5a.jpg)  
图2不同用户位置分布图下的网络总效益  
图5可用频谱数量对网络平均效益的影响

![](images/d4eef1b3ff54b96a9a8cc0c0ebc917cb8dafeae6deabe6f7baf75383796f34ed.jpg)  
图6可用频谱数量对比例公平性的影响

# 4.3认知用户数量对算法影响的比较

为了进一步对比四种算法的性能，在以上比较分析的基础上，提出当区域中的认知用户数量发生改变时，对相关算法将会产生怎样的影响。图7和8展示了网络平均效益和比例公平性随认知用户数变化而变化的曲线。在本次对比实验中，主用户1和可用频谱数M均取15，认知用户数 $\mathbf { \Omega } _ { N }$ 的变化区间为5到30。由图可知，当网络环境中的主用户和可用频谱数固定，随着认知用户数量的上升，网络环境中的负荷加重，认知用户之间的干扰冲突也随之增加，系统的平均效益和比例公平性都在不断衰减。但BFOA算法收获的效益值和公平性仍然是四种算法中最高的，与PSO、ICS、GA相比更能实现认知无线网络的最优频谱分配，且在认知用户数量较多时更明显。

![](images/c54f117fafe441bb1ab3d12a07518e3bbe19853428a72799d6ea1b1dc94b91f1.jpg)  
图7认知用户数量对网络平均效益的影响

![](images/52bb94f71ef659df2ec8c89523d0480d84a2b3d8cb37b549e346110d00c1c4c9.jpg)  
图8认知用户数量对比例公平性的影响

# 5 结束语

针对当今无线通信技术中频谱资源稀缺以及利用率不高的问题，本文将二进制烟花算法进行优化改进，并与认知无线网络的频谱分配问题相结合，得出了较好的频谱分配结果。优化后的二进制烟花算法解决了传统烟花算法中收敛速度较慢，易陷入局部最优解的问题。仿真实验的结果分析表明，本文提出的 BFOA算法在进行频谱分配时，与其他三种算法相比能够获得更好的网络效益和用户比例公平性，从而提升了网络的整体性能。

参考文献：   
[1] 张平，李建武，冯志勇，等.认知无线网络基础理论与关键技术研究 [J].电信科学,2014,30(2):1-13. (Zhang Ping,LiJianwu,Feng Zhiyong, etal.Researchonbasictheoryandkeytechnologyof cognitiveradio network [J]. Telecommunications Science,2014,30 (2): 1-13.)   
[2]Mito la J,Jr Maguire G Q. Cognitive radio: making software radios more personal [J]. IEEE Personal Communications,1999,23 (2): 13-18.   
[3]Karaca HM, Kurt T,Dicle,S Z.Auction-Based Throughput Maximization in Cognitive Radio Networks under Interference Constraint [J].Wireless Personal Communications,2013,72 (2): 1259-1275.   
[4] 谢玉鹏，谭学治，马琳，等．基于分布式博弈论的频谱分配算法[J]. 系统工程与电子技术，2015，37(10):2391-2395.(XieYupeng，Tan Xuezhi,Ma Lin,etal. Spectrum allocation algorithm base on distributed game theory [J].Systems Engineering and Electronics,2O15,37(10): 2391-2395. )   
[5]Peng C,Zheng H, Zhao B Y.Utilization and fairness in spectrum assignment for opportunistic spectrum access [J].Mobile Networks & Applications,2006,11 (4): 555-576.   
[6]EI-Nainay,Mustafa Y.Island genetic algorithm-based cognitive networks [D]. Blacksburg, USA: Virginia Polytechnic Institute and State University 2009.   
[7]赵知劲，彭振，郑仕链，等．基于量子遗传算法的认知无线电频谱分配 [J]．物理学报,2009,58 (2):1358-1363.(Zhao Zhijin,Peng Zhen,Zheng Shilian,etal. Cognitive radio spectrum assignment based on quantum genetic algorithm [J].Acta Physica Sinica, 2009,58 (2): 1358-1363. )   
[8]柴争义，刘芳．基于免疫克隆选择优化的认知无线网络频谱分配[J]. 通信学报，2010,31(1):92-100.(Chai Zhengyi,Liu Fang.Spectrum allocation of cognitive wireless network based on immune clone selection optimization[J]. Jourmal on Communications,2010,31(11): 92-100.)   
[9]王晓飞，陈岳兵，张希，等．基于免疫克隆选择的认知无线网络频谱分 配研究[J].电子与信息学报，2011，33（7):1561-1567.(Wang Xiaofei Chen Yuebing, Zhang Xi, etal. Immune clonal selection based spectrum asignment for cognitive radio networks [J]. Journal of Electronics & Information Technology,2011,33(7): 1561-1567. )   
[10] 张丽影，曾志文，陈志刚，等.认知无线网络中基于约束算子的二进制 粒子群频谱分配算法[J].小型微型计算机系统，2013，34(6): 1226-1229. (Zhang Liying, Zeng Zhiwen,Chen Zhigang,etal. Spectrum allocation algorithm based on constraint operator of binary particle swarm in the congnitive wireless networks [J]. Journal of Chinese Computer Systems,2013,34 (6): 1226-1229.)

[11]Koroupi F,Talebi S,Salehinejad H. Cognitive radio networks spectrum allocation:An ACS perspective [J]. Scientia Iranica,2012,19 (3): 767-773.

[12] Gao H Y,Cao JL.Quantum-inspired bee colony optimization algorithm and its application for cognitive radio spectrum allocation [J].Journal of Central South University,2012,43 (12): 4743-4749.

[13]王先平，曹卉.基于量子布谷鸟搜索的认知无线网络频谱分配[J]．电 信科学，2016,32 (5):62-68.(Wang Xianping，Cao Hui. Spectrum allocation based on quantum cuckoo search algorithm in cognitive radio network[J].Telecommunications Science,2016,32(5):62-68.)

[14]薛俊杰，王瑛，孟祥飞，等．二进制反向学习烟花算法求解多维背包问 题[J].系统工程与电子技术，2017,39(2):451-458.(Xue Junjie,Wang Ying,Meng Xiangfei,etal.Binary opposite backward learning fireworks algorithmformultidimensionalknapsackproblem[J]. Systems EngineeringandElectronics,2017,39(2): 451-458.)

[15] Ying Tan,Chao Yu,Shaoqiu Zheng，et al.Introduction to fireworks algorithm[J]. International Journal of Swarm Intelligence Research,2013,

4(4):39-70.

[16] TAN Ying,ZHENG Shaoqiu. Recent advances in fireworks algorithm [J]. CAAI Trans on Intelligent Systems,2014,9(5): 515-528.   
[17]Shaoqiu Zheng,Andreas Janecek,Ying Tan.Enhanced fireworks algorithm [C]// Proc of IEEE International Conference on Evolutionary Computation. 2013:2069-2077.   
[18]张慕雪，张达敏，杨菊蜻，等．基于捕食搜索策略的模拟退火优化算法 [J]．计算机应用研究,2018,35（9).(Zhang Muxue,Zhang Damin,Yang Juqing,et al.Simulated annealing algorithm based on predatory search strategy[J/OL].Application Research of Computers，2018，35(9）. [2017-08-28]. http://www.arocmag.com/article/02-2018-09-020.html.)