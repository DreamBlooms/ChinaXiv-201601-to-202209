# 求解多目标带时间窗VRP问题的文化狼群算法

李小川，刘媛华，王影歌(上海理工大学 管理学院，上海 200093)

摘要：针对以最小化总距离和车辆数为目标的带时间窗车辆路径问题的求解，提出一种基于文化基因的狼群算法。根据客户近邻度矩阵构建初始狼群，提高狼群的优良性。结合问题特征与狼群算法的寻优思想，重新定义了群体的游走和突袭行为。提出头狼变异策略，增加了最优解的邻域搜索范围。受文化算法启发，将当前最优解的有利信息作为信仰空间的知识来指导狼群进化方向，提高搜索效率。通过仿真实验及与其他算法对比，表明文化狼群算法求解车辆数更少、总距离更短，且具有更好的稳定性。

关键词：车辆路径问题；时间窗；多目标；文化狼群算法 中图分类号：TP18 doi: 10.19734/j.issn.1001-3695.2018.10.0733

Cultural wolf pack algorithm for solving multi-objective VRP with time window

Li Xiaochuan, Liu Yuanhua, Wang Yingge (BusinessSchool,UniversityofShanghai forScience&Technology,Shanghai 2Ooo93,China)

Abstract: To solve the vehiclerouting problem with time window forthe shortest lengthofvehicle travel and the minimum numberofthe using vehicles,this paper proposed a cultural wolf pack algorithm.To improve the quality ofthe wolf pack, this paper constructed the initial wolf pack according to the customers nearest neighbor matrix. Considering the features of this problemandthe wolfpack algorithm,this paper redefied the inteligent behaviors ofartificial wolves.The mutation of leader wolf increased the searching range ofthe optimal solution.According to the favorable information of the curent optimal solution,this paper constructed the knowledge of the belief space to guidetheevolution direction ofthe wolf pack and improve the search eficiency.Simulation results show that the cultural wolf pack algorithm can get less numberof vehicles, shorter total distance and better stability than other algorithms.

Key words: vehicle routing problem; time window; multi-objective; cultural wolf pack algorithm

# 0 引言

车辆路径问题（vehicle routing problem,VRP）具有非线性、非凸性、复杂性和约束条件多且相互之间难以协调的特点，是典型的非线性规划模型，也被证明为NP-hard问题。该问题自1959年由Dantzig等人[提出以来一直受到众多学者的研究和关注，拥有更多限制条件的车辆路径问题也相继被提出。带时间窗车辆路径问题（VRPwith time window,VRPTW）由Savelsbergh[2提出，其在VRP的基础上增加了客户接受服务时间区间的约束，主要优化目标为最小化车辆数目、最小化总行驶距离、最小化总成本等[3]。

VRPTW比VRP更符合现实的物流配送过程，但其求解过程也更加复杂，智能启发式算法在求解该问题时具有一定的优越性，受到很多学者的青睐。目前已有多种智能优化算法应用于VRPTW 的求解，如遗传算法[4-6]、差分进化算法[7,8].蚁群算法[9\~II]等。以上算法均对VRPTW 问题的求解进行了一定程度的探究，但是遗传算法和差分进化算法存在易早熟收敛的问题，蚁群算法易陷入局部循环，迄今为止尚没有哪种算法对VRPTW问题具有绝对的求解优势，因此寻找对该问题求解性能更优的算法仍具有重要的现实意义。

文化算法（cultural algorithm,CA）由Reynolds[12]受人类吸取经验来指导自身或他人行为的启发而提出，对智能算法的自组织过程赋予显性指导条件。CA为上层信仰空间（也称信度空间）和底层种群空间组成的双层并行结构[13]，信仰空间以接受函数的形式记录种群迭代过程中的有用信息，并对其分析总结形成知识来指导种群空间中粒子的后续进化过程。CA为智能算法的改进提供了一种思想，各种符合CA结构的算法都可以作为种群空间的一部分参与进化[14]，从而提高基本算法的性能。狼群算法（wolf packalgorithm,WPA）模拟大自然中狼群分工协作、群体捕食的行为进行迭代寻优，符合文化算法的基本结构[15]。本文提出一种文化狼群算法（culturalwolfpackalgorithm，CWPA）用于求解多目标VRPTW，用狼群算法来进行迭代寻优，提取每代最优路径（头狼）中的最优车辆基因段作为形势知识，并以其子段作为规范知识来指导探狼游走和猛狼突袭行为，避免进化的盲目性，从而提高搜索效率。通过实验验证了本文CWPA较蚁群算法蝙蝠算法、禁忌搜索算法等对比算法在求解多目标VRPTW问题时的优越性，为该问题的求解提供了一种新思路。

# 1多目标VRPTW数学规划模型

# 1.1问题描述

本文研究的多目标VRPTW问题可以描述为由 $k$ 辆规格相同的车为 $n \ ( n \geq k )$ 个客户配送货物，每辆车从配送中心出发，服务完该路径上的客户后回到配送中心，通过合理规划路径，使得配送车辆数和总距离最小。同时还要满足以下条件：a）每辆车装载的总货物都必须满足其最大载重量限制；b)每辆车可以服务多个客户，但每个客户都只能由一辆车服务；c）客户 $i$ 只在时间区间 $\big [ T _ { e i } , T _ { l i } \big ]$ 内接受服务，其中 $T _ { e i }$ 和 $T _ { l i }$ 分别为客户 $i$ 接受服务的最早和最晚时间，若配送车辆早于$T _ { e i }$ 到达，则需要等到 $T _ { e i }$ 进行服务，但最大等待时间要受到约束；d）车辆 $k$ 在客户 $i$ 处的服务结束后即刻去往下一客户处或者返回配送中心。

# 1.2参数定义

$N = \{ 1 , 2 , \cdots , \mathrm { n } \}$ ：所有客户的集合  
$K = \{ 1 , 2 , \cdots , { \mathrm { k } } \}$ ：所有配送车辆的集合  
$d _ { i j }$ :客户 $i$ 与客户 $j$ 之间距离  
$W _ { k }$ ：车辆 $k$ 的最大载重量  
$r _ { i }$ ：客户 $i$ 的货物需求量  
$P _ { k }$ ：车辆 $k$ 服务的客户点集  
$\left[ T _ { e i } , T _ { l i } \right]$ :客户 $i$ 的时间窗  
$T _ { a i }$ :车辆到达客户 $i$ 处的时间点  
$T _ { w i }$ :辆在客户 $i$ 处的等待时间  
$S _ { i }$ ：客户 $i$ 的服务时间

决策变量：$x _ { i j k } = \{ { \begin{array} { l } { 1 , \mp \ddag { \# \llap / \# } k \brace \Re \iiiint \ o \{ { \mathbb { k } } ^ { 2 } \Im \overleftrightarrow { \mathcal { F } } \overleftrightarrow { \Xi } ^ { 2 } \} ^ { - 1 } i \} \boxed { \mp 1 } \ddag \exists \pm \ddag \exists \rlap / \hbar \mathbb { k } \gg / j } } \\ { 0 , \ \mathrm { o t h e r s } } \end{array}  , i , j \in N $

$$
x _ { i k } = { \left\{ \begin{array} { l l } { 1 , { \mathcal { \ddot { Z } } } - i \mathbb { H } \mathbb { \tilde { H } } \mp { \frac { \ell + \mathbb { H } \mathbb { H } } { 4 \mathbb { H } } } k { \mathbb { H } } \mathbb { k } { \mathcal { \ddot { H } } } { \mathcal { \ddot { H } } } } \\ { 0 , { \mathrm { ~ o t h e r s ~ } } } \end{array} \right. } , i \in N , k \in K
$$

# 1.3数学模型

$$
C _ { 1 } = \operatorname* { m i n } \sum _ { j = 1 } ^ { N } \sum _ { k = 1 } ^ { K } x _ { 0 j k }
$$

$$
C _ { 2 } = \operatorname* { m i n } \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { N } \sum _ { k = 1 } ^ { K } x _ { i j k } d _ { i j }
$$

s.t.

$$
\sum _ { i = 1 } ^ { N } \sum _ { k = 1 } ^ { K } x _ { i j k } = 1 , j \in N
$$

$$
\sum _ { i = 1 } ^ { N } r _ { i } x _ { i k } \leq W _ { k } \mathrm { ~ , ~ } k \in K
$$

$$
\sum _ { k = 1 } ^ { K } x _ { i k } = 1 , i \in N
$$

$$
\sum _ { i = 1 } ^ { N } x _ { 1 i k } = \sum _ { j = 1 } ^ { N } x _ { j 1 k } , k \in K
$$

$$
\sum _ { i = 2 } ^ { N } x _ { i j k } = \sum _ { j = 2 } ^ { N } x _ { j i k } \mathrm { ~ , ~ } k \in { \cal K }
$$

$$
\sum _ { i , j \in N } x _ { i j k } = \vert P _ { k } \vert - 1 _ { , k \in K }
$$

$$
T _ { e i } < T _ { a i } + T _ { w i } + S _ { i } \leq T _ { l i } \ , i \in N
$$

$$
W _ { i } = \operatorname * { m a x } \left\{ 0 , \mathrm { T } _ { e i } - \mathrm { T } _ { a i } \right\} , i \in N
$$

式（3）和（4）分别表示车辆数最少和总距离最小的目标函数；式(5)约束了每辆车一次只能服务一个客户；式(6)表示车辆装载货物不能超过该车最大载重量；式（7）约束了每个客户只能被一辆车服务；式（8）表示每辆车从配送中心出发，最后还要回到配送中心；式（9）约束了车辆 $k$ 配送过程的连续性，即服务完客户 $i$ 后也必须从该点出发；式（10)约束了每辆车的路径都不存在子回路；式（9）和式（10）共同约束了客户只在时间窗内接受服务。

# 2 求解多目标VRPTW的文化狼群算法

狼群算法将狼群的捕食过程抽象为探狼游走、头狼召唤、猛狼突袭、围攻捕食等行为，根据狼群的食物分配规则来进行种群更新。算法的初始释放狼群进行搜索，选取嗅到食物气味浓度最大（即适应度值最好，取值 $F _ { b e s t }$ ）的作为头狼，另选除头狼外适应度值较好的 $M$ 只狼作为探狼，每只探狼有$h$ 次游走机会，即在 $h$ 个不同方向进行局部搜索，游走过程中若嗅到的食物气味浓度 $f _ { i }$ 大于 $F _ { b e s t }$ ，则该探狼取代头狼位置， $F _ { b e s t } = f _ { i }$ ，否则退回原位，继续游走。头狼发出召唤后，猛狼向头狼方向奔袭，此过程类似粒子群算法的社会行为，奔袭途中嗅到的食物气味浓度若大于 $F _ { b e s t }$ ，则该猛狼立即转为头狼并发起召唤，否则继续奔袭至与头狼距离 $d _ { i } \leq \operatorname* { m i n } d$ 。接着猛狼联同探狼对猎物发起围攻，根据其围攻结束后若嗅到的食物气味浓度的大小决定是否更新位置。将狼群按适应度值由大到小排列，选取前 $s$ 只保留到下一代，其余的则被淘汰。

狼群的游走、奔袭行为使得狼群算法拥有较好的局部和全局搜索能力，围攻行为进一步增强了算法寻优性能，但是WPA在寻优过程中主要存在以下两方面不足：a）探狼在游走过程中存在一定的盲目性，学习能力较差；b）猛狼在奔袭时的距离判别法存在较大的主观性，且增加了算法复杂度[16,17]。CA的重要思想为将种群进化过程中的经验提取出来，经过分析处理形成知识，并存储于信仰空间。信仰空间中的知识一般超越算法的自学习能力，从而使算法具有跟更高的智能。本章提出的CWPA首先由WPA进行路径搜索，将最优路径中的最优车辆信息作为信仰空间中的知识，对探狼和猛狼的行为进行指导，增加狼群的寻优性能。

# 2.1适应度函数的构造

采取精英保留策略，以路径总距离和车辆数作为评价指标，构造如下适应度函数：

$$
f = \mu \frac { D _ { i } } { \displaystyle { \sum _ { i \in N } D _ { i } } } + \frac { C _ { i } } { \displaystyle { \sum _ { i \in N } C _ { i } } }
$$

其中： $D _ { i }$ 为第 $i$ 个解的路径总距离； $C _ { i }$ 为第 $i$ 个解所需车辆数； $\mu$ 为权重系数， $\mu$ 的加入是为避免极端解（比如车辆数较多，但总距离较短的解）的影响。

# 2.2算法编码

CWPA采用整数编码来表示车辆路径，配送中心用0表示，客户则用其对应的编号表示。例如由1个配送中心为5个客户进行配送，序列03501420表示由两辆车进行配送，车辆1从配送中心出发，依次服务客户3和5后回到配送中心，车辆2从配送中心出发，依次服务客户1、4和2后回到配送中心，基因位4中的0表示车辆1的终点和车辆2的起点。

# 2.3 初始狼群的构造

1）路径选择规则

初始狼群个体对路径节点的合理选择，可以提高狼群的整体质量，加快收敛速度。设 $d _ { i j }$ 为客户 $i$ 与 $j$ 之间的距离，且 $d _ { i j } = d _ { j i }$ ，由此构如下近邻度矩阵：

$$
C ( \mathrm { i }  \mathrm { j } ) = ( \mathrm { c } _ { i j } ) _ { n \times n } \ , \mathrm { ~ } i , j \in N
$$

其中： $c _ { i j } \in \{ 1 , 2 , \cdots , \ \mathrm { n - 1 } \}$ ，表示客户 $i$ 与客户 $j$ 的近邻度( $c _ { i i } = \infty$ ，如 $c _ { 2 6 } = 5$ 表示客户2是距客户6第5近的客户。

若车辆当前所在客户节点为 $i$ ，选取客户 $j$ 作为下一节点概率 $P ( { \mathrm { i } } , { \mathrm { j } } )$ 可由式(15)得到

$$
\begin{array}{c} P ( \mathbf { i } , \mathbf { j } ) = \left\{ \begin{array} { l l } { \displaystyle p _ { 0 } \frac { \eta ( \mathbf { i } , \mathbf { j } ) } { \sum _ { j = 1 } ^ { c _ { w } } \eta ( \mathbf { i } , \mathbf { j } ) } , c _ { i j } \leq c _ { m } } & \\ { \displaystyle ( 1 - p _ { 0 } ) \frac { \eta ( \mathbf { i } , \mathbf { j } ) } { \displaystyle \sum _ { j = c _ { m } + 1 } ^ { n } \eta ( \mathbf { i } , \mathbf { j } ) } , c _ { i j } > c _ { m } } & \end{array} \right. , i , j \in N  \end{array}
$$

其中：

$$
\eta ( \mathbf { i } , \mathbf { j } ) = \frac { \displaystyle \frac { 1 } { c _ { i j } } } { \displaystyle \sum _ { j \in N , j \neq i } \frac { 1 } { c _ { i j } } } , i \in N \
$$

$c _ { m }$ 为最大近邻度判定常数，在车辆路径选择中认为近邻度小于一定范围内的客户作为相邻节点较为合理； $p _ { \mathrm { 0 } } = 0 . 9 8$ ，表示与客户 $i$ 的近邻度 $c _ { i j } \leq c _ { m }$ 的客户 $j$ 将以较大的概率$p _ { 0 } \frac { \eta ( \mathrm { i } , \mathrm { j } ) } { \displaystyle \sum _ { j = 1 } ^ { c _ { m } } \eta ( \mathrm { i } , \mathrm { j } ) }$ $i$ 的近邻度 $c _ { i j } > c _ { m }$ 的客户也有机会以较小概率被选为下一服务点。当客户 $i$ 被选为服务点后，即刻令 $P ( \mathfrak { j } , \mathrm { i } ) = 0$ ，以保证每个客户都只被服务一次。

# 2）初始解构造步骤

设配送车辆规格相同，载重量为 $W$ ， $w _ { k }$ 为车辆 $k$ 的剩余载重量， $L _ { k }$ 为车辆 $k$ 服务的客户点集合， $\boldsymbol { K }$ 为最多使用的车辆数，车辆从配送中心出发时间无先后顺序，则初始解的构造步骤为：

a）初始化 $k = 1$ ， $w _ { k } = W$ ， $L _ { k } = \{ 0 \}$ 。b）随机产生车辆1的初始服务客户 $s$ 中 $w _ { 1 } = w _ { 1 } - q _ { s }$ ，$L _ { 1 } = L _ { 1 } \cup \{ s \}$ ，令 $P ( { \mathrm { i } } , { \mathrm { s } } ) = 0$ 。c）生成一个[0.1]之间的随机数 $\boldsymbol { p }$ ，根据式（15）选择车辆 $k$ 的配送节点 $i$ 。d)若 $q _ { i } \leq w _ { k }$ ，且 $T _ { a i } + T _ { w i } \leq T _ { l i }$ ，则 $w _ { k } = w _ { k } - q _ { i }$ ， $L _ { k } = L _ { k } \cup \{ i \}$ ，令 $P ( \mathfrak { j } , \mathrm { i } ) = 0$ ，转c)，否则执行e)。e） $k = k + 1$ ，若 $k \geq K$ ，则令 $k = K$ ，转c)。f将 $L _ { k }$ 整理为可行解 $[ | L _ { 1 } | | L _ { 2 } | \cdots | L _ { k } | 0 ]$ 。g）重复执行b)\~f)，生成 $N$ 个初始解。h)中 $\left| L _ { k } \right|$ 为集合 $L _ { k }$ 里元素的顺序排列，序列末尾的0表示车辆 $k$ 完成配送任务后回到配送中心。

# 2.4信仰空间

# 1）信仰空间的形成

信仰空间对每次迭代中最优个体的优秀基因进行分析构成形势空间和规范空间，为种群的进化方向及范围提供指导[19]。车辆路径问题的可行解由每辆车服务的客户编号排列组成，因此可以提取初始种群最优个体中表示最优车辆配送的客户集合作为形势知识，其部分连续配送客户子集作为规范知识。例如初始种群最优个体的最优车辆（以下简称最优车辆）配送客户集为{[2.5,3]}，则形势知识和规范知识的形成过程分别如图1(a)和(b)所示，其中规范知识包括|2.5.3、|2.5和5,3三个基因段。

![](images/8ce4c24d35e08d5d3e98c798478af30591fe1c4696e0dc8dc9412c44e01f74bc.jpg)  
(a)形势知识形成过程

(a) Formative process of situational knowledge

![](images/d1c863e7befc5c222f49b2786d137b9351f8b528c82c5235d4cc350ee8baf30e.jpg)  
图1信仰空间形成过程  
Fig.1Formatiive process of belief space

原则上，配送车量在不超载的前提下装载的货物越多越好，如果装载货物过少则存在较大的浪费，考虑货物装载量与行驶距离两方面的因素确定最优车辆的判定准则如式(17)所示，使 $g ( w _ { k } , D _ { k } )$ 取最小值时的车辆即为最优车辆。

$$
g ( w _ { k } , D _ { k } ) = w _ { k } \ \times D _ { k }
$$

其中： $w _ { k }$ 为车辆 $k$ 的剩余装载量； $D _ { k }$ 为车辆 $k$ 的行驶总距离。

2）信仰空间的更新

信仰空间的更新采取精英保留策略，形势知识更新如下：

$$
X ( { \mathrm { t } } + 1 ) = { \left\{ \begin{array} { l l } { [ X ( { \mathrm { t } } ) - X _ { w } ( { \mathrm { t } } ) ] \cup K _ { b } ( { \mathrm { t } } + 1 ) \quad , \quad g _ { b } ( { \mathrm { t } } + 1 ) < g _ { x } ( { \mathrm { t } } ) } \\ { X ( { \mathrm { t } } ) \cup K _ { b } ( { \mathrm { t } } + 1 ) \ , \ g _ { b } ( { \mathrm { t } } + 1 ) \geq g _ { x } ( { \mathrm { t } } ) \& K _ { r } ( { \mathrm { t } } ) \cap K _ { b } ( { \mathrm { t } } + 1 ) = \emptyset } \end{array} \right. }
$$

其中： $X ( { \mathfrak { t } } + 1 )$ 为第 $t + 1$ 代的形势知识； $X _ { w } ( \mathfrak { t } )$ 为第 $\mathbf { \Phi } _ { t } \mathbf { \Phi } _ { t }$ 代形势知识中 $g$ 值最大的车辆服务的客户集合； $K _ { b } ( { \sf t } + 1 )$ 为第 $t + 1$ 代最优车辆服务客户集合； $g _ { b } ( { \mathbf t + 1 } )$ 为第 $t + 1$ 代最优车辆的 $g$ 值；$g _ { x } ( \mathfrak { t } )$ 为前 $t$ 代的最小 $g$ 值； $K _ { r } ( \mathfrak { t } )$ 为 $X ( \mathfrak { t } )$ 中所有客户点集合。

# 2.5探狼游走

选取除头狼外适应度值较好的 $M$ 只人工狼作为探狼，$M$ 取 $\left[ \frac { N } { \alpha + 1 } , \frac { N } { \alpha } \right]$ 内的随机整数， $\mathbf { \Omega } _ { N }$ 为狼群个体总数， $\alpha$ 为探狼比例因子。探狼的游走次数 $h$ 根据迭代次数动态取值， $h$ ，其中 $D ( { \mathfrak { t } } )$ 为第 $t$ 代规范知识中的基因段个数。探狼游走过程中，首先将探狼基因序列中的 ${ } ^ { \left. 6 \right. , , }$ 移除；然后将规范知识中的每个基因段分别在其首尾和中间随机位置各添加一次，每次添加需将原序列中的相应编号移除，例如某探狼的除“0”基因序列为5,2,8.9,4,7，在其末尾添加8,4，得到8,4,5,2.9,7；最后将其转换为可行解编码。若该探狼嗅到食物气味浓度大于头狼，则取代头狼位置，并发起召唤；否则退回原位，继续游走至 $h ( \mathfrak { t } )$ 次。

# 2.6猛狼突袭

猛狼向头狼方向突袭相当于增加了当前最优解的领域范围，提高了搜索效率。以其中一只猛狼为例，具体步骤为：

a)令 $k = 1$ ，提取规范知识中表示 $g$ 值最小车辆所有配送客户的序列 $L _ { g }$ 0b)根据近邻度矩阵分别找到与 $L _ { g }$ 首尾客户 $^ { a , b }$ 距离最近的客户 $a ^ { 1 } , b ^ { 1 }$ 。c）将 $L _ { g }$ 插入到猛狼序列MW 中 $a ^ { 1 }$ 之前，得到序列 $M W ^ { 1 }$ 。d)移除 $M W ^ { 1 }$ 中与 $L _ { g }$ 重复的客户得到序列 $M W ^ { 2 }$ 0e）将 $M W ^ { 2 }$ 中的 $b ^ { \scriptscriptstyle 1 }$ 移到 $b$ 之后得到猛狼完成突袭后的序列 $M W ^ { 3 }$ 。f）计算适应度 $f _ { n e w }$ 。g）若 $f _ { n e w }$ 小于当前头狼适应度 $f _ { b }$ ，执行h)；否则，退回原位后转i)。h)该猛狼取代头狼，更新信仰空间，并重新发起召唤。i）令 $k = k + 1$ ，若 $k > 2$ ，该狼结束奔袭；若 $k > 2$ ，令$c = b ^ { 1 } , b ^ { 1 } = a ^ { 1 } , a ^ { 1 } = c$ ，转c)。

# 2.7头狼变异

CWPA用头狼变异行为取代WPA中的狼群围攻行为。WPA中群狼围攻行为实质上是各粒子对当前最优粒子的邻域进行深度搜索的过程，而本文CWPA的改进猛狼突袭操作已经充分利用了头狼信息，如果再进行狼群围攻操作会增加许多无效操作。另外，如果将每只人工狼的围攻行为看做一次变异操作，则狼群围攻相当于进行了N-1次变异行为，实际上由3.1节可知头狼变异次数为3时即可取得较好的结果，所以会节省算法运行时间。头狼变异采取单点变异策略，变异对象为单个客户点，例如头狼的去“0”序列为2,5,9,3.6.8.4,1,7，客户2.5由车辆1配送，客户9,3.6.8由车辆2配送，客户4,1,7由车辆3配送，图2表示头狼变异过程。

![](images/5d5826c80d334b73cb4d92d44eacb996c223b57331f54816a726408b6e14341f.jpg)  
图2头狼变异过程

# 2.8CWPA 算法步骤

a)初始化各参数，设置初始人工狼个数。b）根据3.3节中步骤进行狼群初始化，由式（13）计算狼群适应度，取最优适应度值 $f _ { b }$ 的人工狼被选为头狼。c）根据3.4节内容构造或更新信仰空间。d）随机选一 $\left[ \frac { N } { \alpha + 1 } , \frac { N } { \alpha } \right]$ 内的整数作为探狼个数，计算第t代每只探狼的游走次数 $h ( \mathfrak { t } )$ 。若游走过程 $f$ (探狼i) $< f _ { b }$ ，该探狼取代头狼位置，转c)更新信仰空间，再转e)；否则继续游走至h(t)次。e)根据3.6节步骤进行猛狼突袭。f)执行头狼变异操作，若某次变异后适应度值优于 $f _ { b }$ ，则该变异狼取代头狼位置，转g)。g）更新狼群，记录当前头狼适应度值。若 $t < G$ ，则 $t = t + 1$ ，转c)；否则算法结束，输出最优结果。

# 2.9CWPA算法特点分析

本文提出的CWPA主要分为三个阶段：探狼游走阶段，探狼个体在各自的邻域范围内进行深度局部搜索，处在了局域最优解附近，而全局最优解也有较大概率在这些点中产生；猛狼突袭阶段，猛狼个体利用了文化空间中的有利信息向当前头狼靠近，避免了突袭的盲目性，相当于增加了最优个体的搜索邻域，也有利于种群的全局进化方向；经过前两阶段的搜索，狼群基本集中在最优点附近，这时执行头狼变异行为有利于增加种群多样性。所以CWPA在理论上具有较好的局部和全局寻优性能。

# 3 仿真实验结果及分析

为了验证本文所提文化狼群算法CWPA求解多目标VRPTW的效能，利用MATLABR2012a软件进行两组仿真实验，仿真环境为处理器Intel(R）Core(TM)i5-2350M CPU2.30GHzRAM4GB,Win7操作系统的PC机。

# 3.1CWPA算法参数设置

CWPA与相关文献中其他改进算法的公共参数采取一致性原则，旨在使其运行结果与文献中的实验结果更具可比性。针对CWPA部分重要的特有参数，本文在Solomon标准数据集上进行了多组测试实验，可以得出：最大近邻度判定常数$c _ { m }$ 为5\~7，探狼比例因子 $\alpha$ 为4或5，头狼变异次数 $\mathbf { \nabla } _ { m }$ 为3时能取得相对较好的求解效果。此外，CWPA对信仰空间规范知识形成机制的灵敏度也较大，分析多组实验结果总结出图3所示的规律。图中 $s$ 表示经式（17）判定的最优车辆所配送的客户数，S-1，S-2，2表示规范知识中提取的最优车辆配送客户子集中包含的客户数，取 $s$ 时表示不执行规范知识操作，取S-1时表示规范知识提取包含S-1个客户数的连续客户子集，取S-2时表示规范知识提取包含S-1和S-2个客户数的连续客户子集，同理取2时表示规范知识提取包含S-1、S-2、2个客户数的连续客户子集。可以看出取S-1时搜索效果较不执行规范知识时有明显提升，当取S-2或更小值时对搜索效果的贡献度基本为零，但是会使算法运行时间呈非线性增加，因此本文规范知识只提取包含S-1个客户数的连续客户子集。

![](images/2fc20bff0ceaa7dec17a7552fe448b061affecad69b4d9416eb013f70966df30.jpg)  
Fig.2Mutation process of leader wolf   
图3规范知识运行机制对算法性能影响 Fig.3Relation between operating mechanism of normative knowledge and algorithmic performance

# 3.2 仿真实验1

首先以文献[3]中的算例为例进行仿真实验，并对狼群算法、文化狼群算法和文献[3]中提出的单点重组精英遗传混合蝙蝠算法MRGBA与文献[11]中所提的单亲遗传混合蚁群算法PHACA求得的结果进行对比。算例可以描述为：由1个配送中心为20个客户配送货物，配送车辆规格相同，最大载重量均为8t，车速均为 $4 0 \mathrm { { k m / h } }$ ，车辆在客户点的最大等待时间为4.5h，求解目标为最小化配送车辆和总距离，客户信息如表1所示（其中客户0为配送中心）。

表1客户信息表  
Table1 Clients information   

<html><body><table><tr><td>客户 编号</td><td>客户坐标 /km</td><td>需求量 /t</td><td>最早接受 服务时刻/h</td><td>最晚接受 服务时刻/h</td><td>服务 时间/h</td></tr><tr><td>0</td><td>(70,70)</td><td>0</td><td>0</td><td>0</td><td>0</td></tr><tr><td>1</td><td>(107,77)</td><td>3.4</td><td>1.5</td><td>3.5</td><td>0.2</td></tr><tr><td>2</td><td>(109,139)</td><td>0.8</td><td>3.0</td><td>5.5</td><td>0.2</td></tr><tr><td>3</td><td>(120,22)</td><td>3.9</td><td>2.0</td><td>5.0</td><td>0.2</td></tr><tr><td>4</td><td>(48,47)</td><td>1.9</td><td>1.5</td><td>5.0</td><td>0.4</td></tr><tr><td>5</td><td>(116,22)</td><td>3.2</td><td>2.0</td><td>5.5</td><td>0.2</td></tr><tr><td>6</td><td>(12,138)</td><td>1.4</td><td>4.0</td><td>8.0</td><td>0.5</td></tr><tr><td>7</td><td>(86,40)</td><td>2.2</td><td>1.5</td><td>3.0</td><td>0.4</td></tr><tr><td>8</td><td>(121,124)</td><td>2.1</td><td>2.5</td><td>5.0</td><td>0.2</td></tr><tr><td>9</td><td>(61,57)</td><td>3.5</td><td>4.5</td><td>8.0</td><td>0.2</td></tr><tr><td>10</td><td>(40,113)</td><td>2.3</td><td>2.0</td><td>3.5</td><td>0.2</td></tr><tr><td>11</td><td>(129,24)</td><td>1.8</td><td>2.5</td><td>5.5</td><td>0.4</td></tr><tr><td>12</td><td>(12,84)</td><td>1.6</td><td>2.0</td><td>4.5</td><td>0.4</td></tr><tr><td>13</td><td>(44,116)</td><td>2.7</td><td>3.0</td><td>6.0</td><td>0.2</td></tr><tr><td>14</td><td>(102,52)</td><td>1.5</td><td>3.5</td><td>5.5</td><td>0.2</td></tr><tr><td>15</td><td>(41,36)</td><td>1.3</td><td>4.0</td><td>7.0</td><td>0.2</td></tr><tr><td>16</td><td>(132,138)</td><td>2.4</td><td>3.0</td><td>6.0</td><td>0.4</td></tr><tr><td>17</td><td>(104,139)</td><td>2.9</td><td>3.0</td><td>5.0</td><td>0.2</td></tr><tr><td>18</td><td>(104,54)</td><td>1.3</td><td>1.0</td><td>3.5</td><td>0.4</td></tr><tr><td>19</td><td>(22,104)</td><td>1.1</td><td>2.0</td><td>4.5</td><td>0.4</td></tr><tr><td>20</td><td>(46,133)</td><td>0.7</td><td>2.0</td><td>4.5</td><td>0.4</td></tr></table></body></html>

算法参数为：最大迭代次数 $G = 2 0 0$ ，人工狼个数 $N = 2 0$ ，最多使用车辆数 $K = 9$ ，探狼比例因子 $\alpha = 4$ ，最大近邻度判定常数 $c _ { m } = 6$ ，头狼变异次数 $m = 3$ ， $\mu = 0 . 5$ 。MRGBA和PHACA参数参见文献[3]和文献[11]，每种算法独立运行25次。

图4为CFWA与FWA的迭代优化对比。可以看出CFWA在100代时开始收敛，而FWA的收敛代数为160代左右，并且CFWA的收敛效果要明显好于FWA。表2记录了本文算法与其他文献中的两种改进方法求解多目标VRPTW的统计结果。在最优车辆数方面，CWPA求解结果为6，优于WPA以及文献[3]提出的MRGBA算法和文献[11]提出的PHACA算法；在最优总距离方面，CWPA求解结果为 $1 \ 0 0 5 . 7 \ \mathrm { k m }$ 分别比MRGBA和PHACA减少 $7 . 7 5 \%$ 和 $1 3 . 1 1 \%$ 。CWPA求解的平均车辆数以及平均总距离也优于WPA、MRGBA和PHACA求解结果，说明CWPA具有更好的稳定性；在平均收敛时间方面，WPA<CWPA<PHACA<MRGBA,但WPA求解精度较低，总体来说CWPA的求解效率更高。

表2CWPA与WPA、MRGBA、PHACA求解结果对比Table 2Results comparison among CWPA、WPA、MRGBA an(  

<html><body><table><tr><td colspan="5">PHACA</td></tr><tr><td></td><td>WPA</td><td>CWPA</td><td>MRGBA[3]</td><td>PHACA[11]</td></tr><tr><td>最少车辆数/veh</td><td>8</td><td>6</td><td>6</td><td>7</td></tr><tr><td>平均车辆数/veh</td><td>8.36</td><td>6.76</td><td>6.70</td><td>7.36</td></tr><tr><td>最短总距离/km</td><td>1164.2</td><td>1005.7</td><td>1090.2</td><td>1157.4</td></tr><tr><td>平均总距离/km</td><td>1290.6</td><td>1152.4</td><td>1164.1</td><td>1187.2</td></tr><tr><td>平均收敛时间/s</td><td>51.90</td><td>55.17</td><td>57.66</td><td>56.25</td></tr></table></body></html>

表3\~6分别为WPA、CWPA、MRGBA和PHACA各运行25次所得的最优结果。图5为本文所提CWPA求得的最优路径图。

![](images/34afb31a5b4486813faf0f9ed648291f7e143ff29c6a063ebb4b82b6bf080d0b.jpg)  
图4CWPA和WPA迭代优化图 Fig.4Evolution diagrams ofCWPA and WPA

表3WPA最优结果  
Table 3Optimal consequence of WPA   

<html><body><table><tr><td>车辆号</td><td>配送路径</td></tr><tr><td>1</td><td>0-3-7-0</td></tr><tr><td>2</td><td>0-1-2-17-0</td></tr><tr><td>3</td><td>0-18-14-0</td></tr><tr><td>4</td><td>0-4-15-9-0</td></tr><tr><td>5</td><td>0-5-11-0</td></tr><tr><td>6</td><td>0-10-13-20-6-0</td></tr><tr><td>7</td><td>0-19-12-0</td></tr><tr><td>8</td><td>0-8-16-0</td></tr></table></body></html>

表4CWPA最优结果Table 4Optimal consequence of CWPA  

<html><body><table><tr><td>车辆号</td><td>配送路径</td></tr><tr><td>1</td><td>0-4-15-9-0</td></tr><tr><td>2</td><td>0-7-11-14-18-0</td></tr><tr><td>3</td><td>0-5-3-0</td></tr><tr><td>4</td><td>0-12-19-6-13-0</td></tr><tr><td>5</td><td>0-10-20-17-2-0</td></tr><tr><td>6</td><td>0-1-16-8-0</td></tr></table></body></html>

表5MRGBA最优结果

Table 5Optimal consequence of MRGBA   

<html><body><table><tr><td>车辆号</td><td>配送路径</td></tr><tr><td>1</td><td>0-4-15-9-0</td></tr><tr><td>2</td><td>0-11-14-3-0</td></tr><tr><td>3</td><td>0-18-7-5-0</td></tr><tr><td>4</td><td>0-12-19-6-13-0</td></tr><tr><td>5</td><td>0-1-16-8-0</td></tr><tr><td>6</td><td>0-10-20-17-2-0</td></tr></table></body></html>

表6PHACA最优结果

Table 6Optimal consequence of PHACA   

<html><body><table><tr><td>车辆号</td><td>配送路径</td></tr><tr><td>1</td><td>0-7-3-0</td></tr><tr><td>2</td><td>0-15-4-9-0</td></tr><tr><td>3</td><td>0-1-2-17-0</td></tr><tr><td>4</td><td>0-18-14-11-5-0</td></tr><tr><td>5</td><td>0-10-13-20-6-0</td></tr><tr><td>6</td><td>0-19-12-0</td></tr><tr><td>7</td><td>0-8-16-0</td></tr></table></body></html>

![](images/3e993615d482ccf666573b6cbabb2422e1fb0e70e793ae88cd51706b4a474c6a.jpg)  
图5CWPA最优路径图Fig.5Optimal route of CWPA

# 3.3 仿真实验2

为了进一步验证本文所提CWPA算法求解不同类型和规模问题的性能，选取Solomon 标准测试数据集中的六个基准问题（R1-02、R2-06、C1-04、C2-08、RC1-05、RC2-07)进行仿真实验。CFWA参数设置为：最大迭代次数 $G = 1 0 0 0$ ，人工狼个数 $N = 6 0$ ，最多使用车辆数依次为25、8、20、8、20、8，探狼比例因子 $\alpha = 4$ ，最大近邻度判定常数 $c _ { m } = 6$ ，头狼变异次数 $m = 3$ ， $\mu = 0 . 5$ 。对每个问题独立求解 50 次，并与文献[10]提出的动态混合蚁群优化算法DHACO 和文献[20]提出的并行禁忌搜索算法ITSH求解结果进行对比。

表7CWPA与DHACO、ITSH求解结果对比

Table 7Results comparison among CWPA、DHACO and ITSI   

<html><body><table><tr><td rowspan="2">基准问题</td><td colspan="2">DHACO[10]</td><td colspan="2">ITSH[20]</td><td colspan="3">CWPA</td></tr><tr><td>OTD</td><td></td><td>OTVMCT/sOTD</td><td></td><td>OTVMCT/sOTD</td><td></td><td>OTV MCT/s</td></tr><tr><td>R1-02</td><td>1486</td><td>17</td><td>68</td><td>1487 17</td><td>-</td><td>1486</td><td>17 67</td></tr><tr><td>R2-06</td><td>935</td><td>3</td><td>11 995</td><td>3</td><td>- 932</td><td>3</td><td>13</td></tr><tr><td>C1-04</td><td>825</td><td>10</td><td>41 825</td><td>10</td><td></td><td>825 10</td><td>39</td></tr><tr><td>C2-08</td><td>588</td><td>3</td><td>19 588</td><td>3</td><td>588</td><td>3</td><td>16</td></tr><tr><td>RC1-05</td><td>1579</td><td>14</td><td>82 1629</td><td>13</td><td>-</td><td>1594 13</td><td>77</td></tr><tr><td>RC2-07</td><td>1061</td><td>3</td><td>23</td><td>1061 3</td><td>-</td><td>1061</td><td>3 18</td></tr></table></body></html>

表7为本文CWPA以及文献[10]提出的动态混合蚁群优化算法DHACO和文献[20]提出的并行禁忌搜索算法ITSH对各算例求解的最优总距离（optimaltotaldistance,OTD）和最优车辆数（optimal totalvehicle,OTV）和平均收敛时间（meanconvergencetime,MCT)。可以看出，CWPA在求解基准问题R1-02和RC1-05时都取得了较好的解，并且在求解R2-06时取得了比DHACO和ITSH更优的解，在求解RC1-05时，求得的最优路径总距离大于DHACO所求结果，但均优于ITSH所求结果，在求解C1-04和C2-08时取得了与DHACO和ITSH相同的最优解。

由表7还可以看出CWPA求解大部分算例时的平均收敛时间均优于DHACO，在求解RC2-07算例时相比DHACO具有明显的时耗优势，在求解R2-06算例时的平均收敛时间多于DHACO，但是CWPA求得的最优路径距离更优，说明CWPA在求解不同类型和规模的VRPTW问题时均具有较好的性能。

# 4 结束语

本文针对多目标VRPTW问题的求解，首先建立了以最小化总距离和总车辆数为目标的数学模型。将狼群算法嵌入文化算法的框架，提出了文化狼群算法，利用近邻度概率矩阵建立初始狼群，提高了狼群的优良性，提取当前最优解的编码信息作为信仰空间的知识来指导底层狼群向着有利的方向进化。通过实验仿真验证了文化狼群算法求解多目标VRPTW问题的有效性，进一步与相关文献中的其他算法进行比较，表明文化狼群算法具有更好的稳定性。下一步的研究目标为更合理的设置文化狼群算法的参数，并且尝试将其用在拥有更多目标个数的多目标VRPTW问题的求解中。

# 参考文献：

[1]Dantzig G B,Ramser JH. The truck dispatching problem [J]. Management Science,1959,6(1): 80-91.   
[2] Savelsbergh M W P.Local search in routing problems with time windows [J].Annals of Operations Research,1985,4(1): 285-305.   
[3]殷亚，张惠珍．求解带硬时间窗的多目标车辆路径问题的多种混合 蝙蝠算法 [J].计算机应用研究，2017,34(12):1-8.(Yin Ya,Zhang Huizhen．Multi-hybrid bat algorithm for solving multi-objectives vehicle routing problem with hard time-window[J].Application Research of Computers,2017,34(12):1-8.)   
[4]Ursani Z,Essam D,Cornforth D,et al.Localized genetic algorithm for vehicle routing problem with time windows [J].Applied Soft Computing,2011,11 (8): 5375-5390.   
[5]Ghoseiri K,Ghannadpour S F.Multi-objective vehicle routing problem with time windows using goal programming and genetic algorithm [J]. Applied Soft Computing,2010,10 (4):1096-1107.   
[6] 高志波，龙科军，王倩，等．车辆路线问题的自适应遗传模拟退火算

法[J]．中国科技论文，2017，12（7):764-769.(Gao Zhibo,LongKejun，Wang Qian，et al.A self-adaptive genetically simulatedannealing algorithm of vehicle routing problem[J]. China Sciencepaper,2017,12(7): 764-769.)

[7]侯玲娟，周泓．基于离散差分进化算法的随机车辆路径问题[J].工业工程,2014,17(3):101-107.(Hou Lingjuan,Zhou Hong.A noveldiscrete diferential evolution algorithm for stochastic VRPSPD[J].Industrial Engineering Journal,2014,17(3):101-107.）

[8]王君．带时间窗车辆路径问题的差分进化混合算法[J].计算机工 程与应用,2013,49 (2):24-28,66.(Wang Jun. Differential evolution hybrid algorithm for vehicle routing problem with time windows [J]. Computer Engineering and Applications,2013,49 (2): 24-28,66.)   
[9] 李卫斌，董影影，李小林，等．改进蚁群算法在应急 VRP 中的应用 及收敛性分析[J]．计算机应用研究,2014,31(12):3557-3559,3567. (Li Weibin,Dong Yingying,Li Xiaolin,et al.Application of improved ant colony algorithm in emergency VRP and its convergence analysis [J].Application Research of Computers,2014,31 (12):3557-3559, 3567.)   
[10]葛斌，韩江洪，魏臻，等．求解带时间窗车辆路径问题的动态混合蚁 群优化算法[J]．模式识别与人工智能，2015,28（7):641-650.(Ge Bin,Han Jianghong,Wei Zhen,et al.Dynamic hybrid ant colony optimization algorithm for solving the vehicle routing problem with time windows [J].Pattern Recognition and Artificial Intelligence,2015, 28(7):641-650.)   
[11]刘云，张惠珍．多目标带时间窗的车辆路径问题的单亲遗传混合蚁 群算法[J]．公路交通科技，2016,33(6):95-100,106.(Liu Yun, Zhang Huizhen.A partheno-genetic hybrid ant colony algorithm for solving multi-objective vehicle routing problem with time window [J]. Journal of Highway and Transportation Research and Development, 2016,33 (6): 95-100,106.)   
[12] Reynolds R G.An introduction to cultural algorithms [C]// Proc of the 3rd Annual Conference on Evolutionary Programming. San Diego: World Scientific Press,1994: 131-139.   
[13] Reynolds R G,Kinnaird H L.Optimization problem solving with auctions in cultural algorithms [J].Memetic Computing,2013,5 (2): 83-94.   
[14] Gao Hongyuan,Diao Ming.Cultural firework algorithm and its application for digital filters design [J]. International Journal of Modeling,Identification and Control, 2011,14 (4): 324-331.   
[15]钱荣鑫．一种基于文化机制的狼群算法[J].信息技术,2015,45 (12): 98-102.(Qian Rongxin.A wolf pack algorithm based on cultural mechanism [J].Information Technology,2015,45 (12): 98-102.)   
[16]薛俊杰，王瑛，李浩，等．一种狼群智能算法及收敛性分析[J].控 制与决策,2016,31(12):2131-2139.(Xue Junjie,Wang Ying,Li Hao, et al.A smart wolf pack algorithm and its convergence analysis [J]. Control and Decision,2016,31(12): 2131-2139.)   
[17] Wu Husheng, Zhang Fengming.A uncultivated wolf pack algorithm for high dimensional functionsand itsapplication in parameters optimization of PID controller [C]// Proc of IEEE Congresson Evolutionary Computation.Piscataway， NJ: IEEE Press，2014: 2430-2438.   
[18] Robert G, Chung C.A self-adaptive approach to representation shifts in cultural algorithms [C]/ Proc of IEEE International Conference on Evolutionary Computation.1996: 94-99.   
[19]黎明，江乐旗，陈昊．基于文化算法的无人飞行器航迹规划[J].模 式识别与人智能，2017,30(2):152-161.(Li Ming,Jiang Leqi,Chen

Hao.Route planning method for unmanned aerial vehicle based on cultural algorithm [J].Pattern Recognition and Artificial Intelligence, 2017,30 (2):152-161.)

[2O] CordeauJF,MaischbergerM.Aparallel iterated tabusearch heuristic for vehicle routing problems [J].Computers & Operations Research, 2012,39 (9):2033-205.