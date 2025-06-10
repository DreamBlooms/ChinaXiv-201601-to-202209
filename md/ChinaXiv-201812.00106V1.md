# 第四方物流协同路径定制问题研究

崔妍'，黄 敏²，李波1

(1.沈阳工程学院 信息学院，沈阳 1101362.东北大学 信息科学与工程学院 流程工业综合自动化教育部重点实验室，沈阳 110819)

摘要：为了解决第三方物流（3PL）供应商面临的高运输成本问题，以第四方物流（4PL）供应商的角度，提出了多第三方物流（3PL）供应商协同为客户定制路径的问题。针对该问题在模型求解上要同时考虑路径与3PL供应商的特点，设计了基于k-短路的混合粒子群算法(K-PSO)。实验分析中，通过K-PSO 算法与遗传算法和枚举算法对不同节点数目以及不同3PL供应商个数下仿真算例的计算表明了算法的有效性。最后，通过对3PL转运成本的改变，展示了4PL协同运输的优势。

关键词：协同运输；粒子群算法；第四方物流；k-短路算法 中图分类号：F505 doi:10.19734/j.issn.1001-3695.2018.07.0535

Research on 4PL collaborative routing customization problem

Cui Yan1,Huang Min²,Li Bo1 (1.Colege of Information,Shenyang InstituteofEngineering,Shenyang110l36,China; 2.KeyLaboratoryofIntegrated AutomationofProcess IndustryofMinistryof Education，ColegeofInformation Science&Engineering,Northeastern University, Shenyang 110819,China)

Abstract: Inorder to solve thehigh transportationcost problemfaced bythethird partylogistics (3PL)suppliers,from the fourth party logistics (4PL）supplier's pointof view,a multi 3PLColaborativeRouting Customization Problemis proposed. Asthe problem needs to consider the route and the 3PLs simultaneously,a hybrid Particle Swarm Optimization based K-shortest path algorithm (K-PSO)isdesigned.In theexperimental analysis,theresultsshow the effectiveness of the K-PSO by comparing with the GA and enumeration algorithm with diferent nodes'and 3PL suppliers’number.Finally, through the changes of the 3PL suppliers'transit cost,it shows the advantages of the 4PLcoordinated transportation.

Key words: collaborative transportation; particle swarm optimization; fourth party logistics; $\mathbf { k }$ -shortest pathalgorithm

# 0 引言

第四方物流(forthpartylogistics,4PL)协同路径定制问题（4PL collaborative routing customization problem,4PLCRCP)是指单第三方物流(Third Party Logistics，3PL)供应商很难胜任或者需要付出较高代价才能完成客户交给的运输工作时，由4PL供应商利用其拥有的信息资源协同多个3PL供应商共同为客户定制运输方案的问题。

有关协同物流的研究，其核心任务是对网络资源进行整体规划、调配获取和集成优化[1]。对于4PLCRCP，4PL供应商不仅要协同多个物流分支，还肩负着为物流分支选择3PL供应商的工作。在之前的研究中，任意两节点间的3PL供应商被认为是独立的[2]。而实际运输中很多3PL业务范围大、只是在个别路段存在劣势。因此，4PL应利用其拥有的信息资源为客户选择3PL供应商，从而使配送方案更具优势。

在4PLCRCP中，由于协同机制的加入，使4PL要顾及各转运节点的具体情况。许多学者对4PL问题的求解方法进行了研究[2-5]。但是在4PLCRCP中，问题除了具有在多重图下寻找约束最短路的特征，还要计算转运节点的转换费用和时间。如果使用简单图求出所有路径，虽然理论可行，但解空间会非常庞大。因此，本文首先利用K-短路算法求解简单图的前K短路径，然后再利用粒子群算法选择路径上的供应商。提高了算法效率的同时增强了算法的有效性。

鉴于以上分析，本文基于4PL协同运输模式，建立了同时考虑3PL供应商停靠与转换成本的4PLCRCP数学模型。设计了基于K-短路算法的混合粒子群算法(K-PSO)。实验分析中，针对不同节点数目和不同3PL供应商数目下的实例计算，以及与遗传算法和枚举算法计算结果的对比分析表明了K-PSO算法的有效性。最后，通过对不同转换成本下的实例计算表明：与客户只使用单一3PL供应商的运输模式相比，选择4PL协同运输模式不仅可以增加任务按时完工的比率还能为客户节省一定的费用。

# 1 问题描述与建模

# 1.1问题描述

假设某4PL供应商拟承揽一项由供应点 $\nu _ { \mathrm { { } _ { l } } }$ 到目的点 $\nu _ { n }$ 的运输任务，其中 $\nu _ { 2 } \sim \nu _ { n - 1 }$ 为中转节点。网络由 $\boldsymbol { r }$ 个3PL供应商组成。4PL可以根据3PL供应商的运输范围指派任务。每个3PL供应商在运输过程和在经过中转节点时均需要一定的时间和费用。如果4PL在相邻路径使用不同的3PL供应商，还会产生转换3PL的时间和费用（起始和终止节点视为转换节点）。

将上述问题的3PL供应商看做边并以编号 $\mathbf { l } , . . . , r$ 标志，于是得到4PLCRCP运输网络多重图 $G ( V , E )$ （其中， $\boldsymbol { V }$ 为节点集， $E$ 为边集)。

基于上述假设，为建立4PLCRCP模型需要定义的参数及变量如下：

1）参数说明$\boldsymbol { r }$ 表示运输网络中3PL供应商的数量；$T$ 表示交货时间；$T _ { i j k }$ 表示:3PL供应商 $k$ 将货物由点 $i$ 运输到点 $j$ 的时间;$T _ { i }$ 表示在节点 $i$ 的停靠时间；$T _ { i } ^ { ' }$ 表示在节点 $i$ 更换3PL供应商的时间；$b _ { i } = \left\{ { \begin{array} { l } { - } \\ { 1 , } \end{array} } \right.$ 1,i是始发节点$b _ { i }$ ：点 $i$ 对货物的需求量， i是需求节点[0，否则$C _ { i j k }$ 表示 3PL 供应商 $k$ 将货物由点 $i$ 运至点 $j$ 的费用；$C _ { i }$ 表示在中转节点 $i$ 的停靠费用；$\boldsymbol { C } _ { i } ^ { ' }$ 表示在节点 $i$ 更换3PL供应商的费用。2）变量定义$x _ { i j k }$ 表示供应商 $k$ 是否承担 $i$ 到 $j$ 的运输任务，即$x _ { i j k } = \left\{ { 1 , } \atop { 0 , } \right.$ 供应商k负责i到j的运输任务否则$y _ { i }$ 表示节点 $i$ 是否承担运输任务，即$y _ { i } = { \left\{ \begin{array} { l l } { 1 , } \\ { 0 , } \end{array} \right. }$ 点i承担运输任务（204 否则$z _ { i }$ 表示途径点i时，是否在点 $i$ 更换 3PL 供应商。即$z _ { i } = \left\{ { 1 , \mathrm { y } _ { i } = = 1 } \atop { 0 , } \right.$ 且在点i更换3PL供应商否则其中 $i , j \in \{ 1 , . . . , n \} , k \in \{ 1 , . . . , r \}$ 。

# 1.2数学模型

本文目标是求得一条满足约束条件的费用最短路 $R$ 。在路径 $R$ 下，要同时考虑3PL供应商、转运节点以及转换3PL供应商的时间和费用。根据上述描述，建立的模型如下：

$$
Z = \operatorname * { m i n } ( \sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } \sum _ { k = 1 } ^ { r } C _ { i j k } x _ { i j k } + \sum _ { i = 1 } ^ { n } C _ { i } y _ { i } + \sum _ { i = 1 } ^ { n } C _ { \textit { i } } ^ { * } z _ { i } )
$$

s.t.

$$
\sum _ { i = 1 } ^ { n } \sum _ { j = 1 } ^ { n } \sum _ { k = 1 } ^ { r } T _ { i j k } x _ { i j k } + \sum _ { i = 1 } ^ { n } T _ { i } y _ { i } + \sum _ { i = 1 } ^ { n } T ^ { \prime } { } _ { i } z _ { i } \leqslant T
$$

$$
\sum _ { i = 1 } ^ { n } \sum _ { k = 1 } ^ { r } x _ { i j k } - \sum _ { i = 1 } ^ { n } \sum _ { k = 1 } ^ { r } x _ { j i k } = b _ { j } , \qquad j \in \{ 1 , 2 , . . . , n \}
$$

$$
\sum _ { i = 1 } ^ { n } \sum _ { k = 1 } ^ { r } x _ { i j k } = y _ { j } , \qquad j \in \{ 2 , . . . , n \}
$$

$$
\sum _ { j = 1 } ^ { n } \sum _ { k = 1 } ^ { r } x _ { i j k } = y _ { i } , \qquad i \in \{ 1 , 2 , . . . , n - 1 \}
$$

$$
z _ { i } \le y _ { i } \ , i \in \{ 1 , 2 , . . . , n \}
$$

$$
y _ { 1 } = 1
$$

$$
y _ { n } = 1
$$

$$
x _ { i j k } , y _ { i } , z _ { i } = 0 \not \equiv \not \{  \} \downarrow \ , { \ : } i , j \in \{ 1 , 2 , . . . , n \} , k \in \{ 1 , 2 , . . . , r \} { }
$$

在上面的模型中，式(1)为目标函数，表示在运输途中、在转运节点停靠和转换的费用总耗；式（2）表示到达目的地的时间不大于客户要求的时间；式(3)表示流量平衡；式(4)(5)表示选择的点是从起点到目的节点的通路；式(6)表示在i点转换则一定在i点中转；式(7)(8)分别表示路径的起始和终止节点；式(9)表示 $x _ { i j k }$ ， $y _ { i }$ 和 $z _ { i }$ 为0-1变量。

# 2 基于K-短路算法的混合PSO算法

# 2.1主要步骤

在K-PSO中，求解过程包含初始解生成和解的更新两个阶段。在第一阶段，首先利用K-短路算法求前K短路径，然后根据种群规模等比例扩展K短路数目，最后随机生成路径上的3PL并计算适值。在第二阶段，使用第一阶段的结果作为初始种群，然后利用PSO算法选择路径上的3PL。每代种群中，对上代K短路的平均适值进行从小到大排序。然后利用旋转轮盘法确定第K短路的数目。基于上面描述，算法的主要步骤如下：

a)利用K短路算法求前K短路径。根据K短路的结果确定K值。等比例扩展种群规模后，初始化路径上的3PL供应商并计算适值；b)根据K短路的平均适值由轮盘法分配第K短路径在种群中的个体数目；c)使用PSO算法求路径上的3PL供应商并计算适值。d)对于不同的K短路，是否有更好解？是：更新该K短路的最好解；否则，不变；e)是否达到最大迭代次数？是：转Step6；否：转Step2;f)算法运行结束，比较各个K短路的最好解，输出最优者。

# 2.2编码结构及初始解

根据问题特点，解的编码结构由路径上的节点集$P A T H = [ p _ { 1 } , . . . , p _ { l } ]$ 和边集 $P L = [ p l _ { 1 } , . . . , p l _ { { l - 1 } } ]$ 两个部分组成。其中$p _ { i }$ （ $p _ { i } \in V$ )表示路径上的第 $i$ 个节点， $p l _ { i } \left( p l _ { i } \in E \right)$ 表示使用的第 $i$ 个3PL供应商（ $i \in \{ 1 , . . . , n \} \ .$ )。

在初始解生成阶段，路径上的节点集 $P A T H$ 由 $\mathrm { ~ \bf ~ K ~ }$ 短路算法得到。等比例扩展节点集的数目至种群规模，通过随机生成3PL供应商的方法构成解的边集，从而构成解的初始种群。

# 2.3解的更新

在解的更新阶段，首先利用PSO算法的速度位置更新式[6]计算路径上3PL供应商的取值（0或者1)，然后使用轮盘赌方法确定3PL。具体方案如下：

假设第 $g$ 个粒子位置： $\begin{array} { r l } { P L _ { g i j } = } & { { } ( x _ { g i j 1 } , x _ { g i j 2 } , \ \ldots , x _ { g i j r } ) } \end{array}$ ，速度：$V _ { g i j } =$ $( V _ { g i j 1 } , V _ { g i j 2 } , \dots , V _ { g i j r } )$ ，其中 $g = 1 , . . . , P S$ ， $P S$ 表示种群规模,$i , j \in \{ 1 , 2 , . . . , n \}$ 。

$\forall k \in \{ 1 , 2 , . . . , r \}$ ，第 $g$ 个粒子的速度 $V _ { g i j k } ^ { d + 1 }$ 和位置 $x _ { g i j k } ^ { d + 1 }$ 更新公

式如下:

$$
V _ { g i j k } ^ { d + 1 } = V _ { g i j k } ^ { d } + c _ { 1 } \xi ( P _ { g i j k } ^ { d } - x _ { g i j k } ^ { d } ) + c _ { 2 } \eta ( P _ { g i j k } ^ { \prime d } - x _ { g i j k } ^ { d } )
$$

$$
\boldsymbol { x } _ { ~ g i j k } ^ { \scriptscriptstyle { d + 1 } } = \{ { \begin{array} { l l } { 1 , r a n d o m < S ( V _ { g i j k } ^ { d + 1 } ) } \\ { 0 , \Re { \stackrel {  } { \mathrm { E } } } } \end{array} } 
$$

$$
x _ { g i j k } ^ { d + 1 } = \left\{ { \begin{array} { l l } { 1 } & { { \frac { t } { 4 } } { \hat { \mathrm { E } } } { \frac { \hbar \hbar } { \mathrm { m m } } } \mathbb { J } | \not { \Xi } \mathrm { j } { \underline { { { \mathcal { H } } } } } } \\ { 0 } & { \qquad { \underline { { \mathcal { H } } } } \backslash \displaystyle { \mathrm { 4 j } } } \end{array} } \right.
$$

次数， $c _ { 1 }$ 和 $c _ { 2 }$ 为学习因子， $\xi$ 和 $\eta$ 为[0,1]的随机数， $P _ { g i j k } ^ { d }$ 为粒子 $g$ 所经历的最好点， $P _ { g i j k } ^ { \prime d }$ 为种群内所有粒子经历的当前最好点。

根据式（10）产生的 $V _ { g i j k } ^ { d + 1 }$ （ $k = 1 , 2 , . . . , r \ )$ ，由式（11）生成 $i$ 到 $j$ 的3PL的0-1取值。分别计算3PL取值为1时的路径适值，然后按照从小到大的顺序进行排序。设参数 $\mu \in ( 0 , 1 )$ ，得到基于序的评价函数：

$$
e \nu a l ( k ) = \mu ( 1 - \mu ) ^ { k - 1 }
$$

选择过程以旋转轮盘的方法为基础。根据评价函数(13)，旋转轮盘并由式（12）确定最终被选中的3PL供应商。

# 2.4适值函数

利用K-短路算法求解K短路径时，未考虑路径的时间约束。本文将时间约束作为罚值加入到目标函数中，从而形成适值函数式（14)。

$$
f = \left\{ \begin{array} { l l } { Z + \alpha ^ { * } ( T T - T ) ~ T T > T } \\ { Z ~ \sharp ~ \cdot \mathscr { H } \mathscr { U } } \end{array} \right.
$$

其中 $\alpha ( \alpha \geqslant 1 )$ 为惩罚系数。

# 3 数值实验

# 3.1实验数据

针对4PLCRCP的特点，假设网络节点集 $\mathrm { \Delta V }$ 中的 $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 个节点在 $1 0 0 ^ { * } 1 0 0$ 范围内随机生成。 $_ { \mathrm { N O } }$ 表示可能与节点 $\mathrm { i } ( \ \forall i \in V \$ ）有边相连的邻接点个数。D为邻接矩阵（其中 $\mathrm { D ( i , j ) = r }$ 表示i到j有r条边， $i , j \in V$ )。d(i,j).cost(ii)和d(i,j).time(ii)分别表示节点i到节点 $\mathrm { ~ j ~ }$ 的第ii $( \mathrm { i i } { = } 1 , . . . , \mathrm { r } )$ 条边的费用和时间属性。实验数据分别由下面三个阶段生成：

a)生成与节点i相连的节点。

$\forall j \in V \bigcup j \neq n \bigcup j \neq i$ ，如果j-i $\mathsf { \Lambda } \vert \leq \mathsf { N O }$ ，随机产生1\~NO之间的随机整数t1。如果 $\mathrm { \mathfrak { t } } { > } \mathrm { N O } { - } 1$ ，则设定i到j之间没有边相连，即 $ { \mathbf { D } } (  { \mathbf { i } } ,  { \mathbf { j } } ) { = } 0$ ；否则假设i到j有r条边相连，即 $\mathbf { D } ( \mathrm { i } , \mathrm { j } ) { = } \mathrm { r }$ 。

b)生成边（3PL供应商）的费用和时间属性。

$\forall i , j \in V$ ， $\forall i i \in r$ ，如果 $\mathrm { \Delta D ( i , j ) ~ \ \neq 0 }$ ，随机产生0\~1之间的随机数t2。假设当 $\scriptstyle { \mathfrak { t } } 2 > 0 . 2$ 时，i到 $\mathrm { j }$ 第ii条边的运输费用为1\~15之间的随机整数，即d(i,j).cost(ii)=rand(1,15)；i到j第ii条边的运输时间为两点之间的距离除以费用，即d(i,j).time(ii)=li-jl/d(i,j).cost(ii)。当 $\mathfrak { t } 2 \le 0 . 2$ 或对于其他节点，3PL供应商的费用和时间为无穷大。

c)生成节点的费用和时间属性。

$\forall i \in V$ ,对节点i的中转和转运费用分别赋予2\~12的随机整数;对节点i的中转和转运时间分别赋予4\~14的随机整数。

# 3.2结果分析

假设某4PL供应商拟承揽一项由节点 $\nu _ { 1 } = 1$ 到目的点$\nu _ { _ n } = 8$ ， $r = 5$ 的运输任务。数据由3.1节 $_ { \mathrm { N O } = 3 }$ 时产生。算法使用Matlab7.0并在core22.83GHzPc上实现。经多次实验，较为合理的算法参数设置如下：

$\mathrm { K } { = } 3 , \mathrm { P S } { = } 5 , \mathrm { G E N } { = } 2 0 , \mathrm { c } 1 { = } \mathrm { c } 2 { = } 2$ $\xi = 0 . 5$ $\eta = 0 . 8$ $\mu { \ = } 0 . 5$ $\alpha = 1 0 0$ 假设 $\scriptstyle \mathrm { T = } 2 6$ 天，得到的最优解为[1,3,6,8][1,5,5]

这意味着，当决策者（4PL）需要在26天内将货物由节点1运至节点8时，使用编号为1,5,5的3PL供应商分别负责节点1到3、节点3到6和节点6到8的运输工作。这一运输过程总耗时25天，费用157.7。

图1展示了 $\scriptstyle \mathrm { n = 8 }$ 时K-PSO算法的收敛情况。

为了增强算法求解4PLCRCP的说服力，随机产生$_ { \mathrm { N O = 5 } }$ 、 $\scriptstyle \mathrm { n = 3 0 }$ ， $_ { \mathrm { N O = 8 } }$ 、 $\scriptstyle \mathrm { n = 5 0 }$ 以及 $_ { \mathrm { N O = 8 } }$ 、 $\scriptstyle \mathtt { n = 1 0 0 }$ 的算例。通过改进文献[2]设计的遗传算法（简称GA）和枚举算法（简称 EM)，分别对上述算例进行求解。假设每个算例运行50次，得到的结果如表1所示。

![](images/32dbd57981106b28a1060ab59f8124a0e1fc20398282f59229c03f1b10dca73f.jpg)  
图18节点K-PSO 算法收敛曲线  
Fig.1Convergence curve of the 8-node K-PSO algorithm

表1中，“-”表示在相应算法中不存在该项信息。对于EM，当 $\scriptstyle \mathrm { n = 8 }$ 时，总计算时间79秒。这一结果与使用K-PSO和GA计算得到的结果一致。当 $\scriptstyle \mathrm { n = 3 0 }$ 时，EM无法在有限时间内求得最优解。而K-PSO算法在最好解的均值、偏差等方面均优于GA。另一方面，GA的种群规模远大于K-PSO的种群规模。造成这种现象的原因是协同机制的加入使得GA很难顾及每一转运点，从而计算的稳定性要依赖于种群规模。当 $\scriptstyle \mathrm { n = 5 0 }$ 和 $\scriptstyle \mathrm { n = 1 0 0 }$ 时，两种算法在偏差、最坏解和均值等方面的差异更加明显。因此，从表1可以看出，虽然K-PSO因计算K短路耗费了一定的时间，但K-PSO算法求解的平均质量要优于GA。

表1K-PSO与GA和EM的对比情况  
Table 1 The comparison of the K-PSO with GA and EM   

<html><body><table><tr><td>algorithm</td><td>V</td><td>E</td><td>T</td><td>K</td><td>PS</td><td>GEN</td><td>Best</td><td>Bad</td><td>Arg</td><td>msd</td><td>Time (s)</td></tr><tr><td>K-PSO</td><td>8</td><td>85</td><td>26</td><td>3</td><td>5</td><td>20</td><td>157.7</td><td>157.7</td><td>157.7</td><td>0</td><td><1</td></tr><tr><td>GA</td><td>8</td><td>85</td><td>26</td><td>-</td><td>20</td><td>30</td><td>157.7</td><td>157.7</td><td>157.7</td><td>0</td><td><1</td></tr><tr><td>EM</td><td>8</td><td>85</td><td>26</td><td></td><td></td><td></td><td>157.7</td><td></td><td></td><td></td><td>79</td></tr><tr><td>K-PSO</td><td>30</td><td>815</td><td>110</td><td>5</td><td>10</td><td>50</td><td>249.6</td><td>259.6</td><td>250.8</td><td>2.5</td><td>3</td></tr><tr><td>GA</td><td>30</td><td>815</td><td>110</td><td>-</td><td>70</td><td>40</td><td>249.6</td><td>261.4</td><td>254.6</td><td>5.7</td><td>1</td></tr><tr><td>EM</td><td>30</td><td>815</td><td>110</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>K-PSO</td><td>50</td><td>1 420</td><td>155</td><td>5</td><td>15</td><td>70</td><td>349.6</td><td>361.6</td><td>351.5</td><td>3.8</td><td>8</td></tr><tr><td>GA</td><td>50</td><td>1420</td><td>155</td><td>-</td><td>130</td><td>60</td><td>349.6</td><td>378.5</td><td>355.4</td><td>11.2</td><td>3</td></tr><tr><td>EM</td><td>50</td><td>1420</td><td>155</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>K-PSO</td><td>100</td><td>3160</td><td>280</td><td>8</td><td>25</td><td>100</td><td>587.1</td><td>611.2</td><td>590.4</td><td>5.2</td><td>14</td></tr><tr><td>GA</td><td>100</td><td>3160</td><td>280</td><td>-</td><td>220</td><td>100</td><td>587.1</td><td>635.6</td><td>596.9</td><td>17.9</td><td>5</td></tr><tr><td>EM</td><td>100</td><td>3160</td><td>280</td><td></td><td></td><td></td><td></td><td>1</td><td>1</td><td></td><td></td></tr></table></body></html>

图2展示了 $\scriptstyle \mathrm { n = 3 0 }$ ， $_ { \mathrm { N O = 5 } }$ ， $\mathrm { r } { = } 1$ ,5,10,15,20时，GA和K-PSO计算偏差的对比情况。

当 $\mathrm { r } { = } 1$ 时，任意两点之间只有一个3PL，于是4PLCRCP转换为带有约束的最短路问题。随着3PL数目增多，两种算法的偏差有所增加。但是当 $\mathrm { r } { = } 1 0$ ，15和20时，K-PSO的求解偏差缺有一定幅度的减少。产生这种现象的原因是随着3PL个数增多，K-PSO算法的选择余地变大。而GA却因3PL数目增加导致算法求解能力变弱。

# 3.3问题分析

在4PLCRCP中，4PL的决策结果不仅与3PL供应商的运输时间和费用有关，还与节点的转换成本有着千丝万缕的联系。表2展示了 $\scriptstyle \mathrm { n = 3 0 }$ 时4PL协同模式与单3PL供应商运输时的对比情况。在协同模式下，当 $C _ { i } ^ { ' } = T _ { i } ^ { ' } = 0$ 时，3PL供应商的转换成本为0，这时4PLCRCP转换为4PLRP问题[2]。随着转换费用增加，4PL尽量使用相同3PL供应商。与此同时，随着转运时间增加，运输方案也会随之改变。从表2可以看出，在满足时间约束的条件下，相同转换费用不同转换时间下的运输费用相同。但是随着转换时间的增加，如$C _ { i } ^ { \prime } { = } 1 , T _ { i } ^ { \prime } { = } 2 0$ ，4PL便无法按时完成任务，这时总的运输费用也会明显增大。由于3PL业务范围的限制，在 $\scriptstyle \mathrm { n = 3 0 }$ 的算例中，只有3PL供应商1,2.5能够独自完成部分任务。如果使用它们单独运输，虽然不需要支付转换成本，但可能会增加总的运输费用。对表2中不同转换成本下完成任务的个数（图3）以及与协同运输相比运输费用的增加幅度（图4）上来看，协同运输模式不仅可以节省费用，还在完成任务个数（图3）以及完成任务时的费用上（图4）明显优于客户使用单3PL

供应商的结果。

![](images/dc0f4e3a152091e8566761bd83bb4528c5103ee307e20d60fde0aa57faca55c4.jpg)  
图2不同3PL数量下的偏差对比情况

表2不同运输方式下转换成本对最优解的影响  
Table2The influence of the conversion cost on optimal solution under different transportation modes   

<html><body><table><tr><td rowspan="2">C</td><td rowspan="2">T</td><td colspan="3">协同运输</td><td>3PL(1)</td><td>3PL(2)</td><td>3PL(5)</td></tr><tr><td>路径</td><td>3PL 供应商</td><td>时间/费用</td><td>时间/费用</td><td>时间/费用</td><td>时间/费用</td></tr><tr><td>0</td><td>0</td><td>[1 5 11 18 22 23 30]</td><td>[5323 23]</td><td>66/227</td><td>95/227</td><td>86/234</td><td>88/296</td></tr><tr><td>1</td><td>0</td><td>[1 5 11 18 22 23 30]</td><td>[111111]</td><td>95/229</td><td>95/229</td><td>84/236</td><td>88/297</td></tr><tr><td>1</td><td>5</td><td>[1 5 11 18 22 23 30]</td><td>[111111]</td><td>105/229</td><td>105/229</td><td>94/236</td><td>98/297</td></tr><tr><td>1</td><td>10</td><td>[1 5 11 18 22 23 30]</td><td>[2 2 2 2 2 2]</td><td>104/236</td><td>115/749</td><td>104/236</td><td>108/297</td></tr><tr><td>1</td><td>15</td><td>[1 5 9 16 23 30]</td><td>[5 5 5 3 3]</td><td>105/270</td><td>125/1 749</td><td>114/696</td><td>118/1 127</td></tr><tr><td>1</td><td>20</td><td>[1 5 11 18 22 23 30]</td><td>[2 22222]</td><td>124/1 696</td><td>135/2 749</td><td>124/1 696</td><td>128/2127</td></tr><tr><td>2</td><td>0</td><td>[1 511 18 22 23 30]</td><td>[111111]</td><td>95/231</td><td>95/231</td><td>84/238</td><td>88/299</td></tr><tr><td>2</td><td>5</td><td>[1 5 11 18 22 23 30]</td><td>[1 11 1 11]</td><td>105/231</td><td>105/231</td><td>94/238</td><td>98/299</td></tr><tr><td>2</td><td>10</td><td>[1 5 11 18 22 23 30]</td><td>[2 22 2 2 2]</td><td>104/238</td><td>115/751</td><td>104/238</td><td>108/299</td></tr><tr><td>2</td><td>15</td><td>[1 5 9 16 23 30]</td><td>[55533]</td><td>105/273</td><td>125/1 751</td><td>114/698</td><td>118/1 129</td></tr><tr><td>2</td><td>20</td><td>[1 5 11 18 22 23 30]</td><td>[222222]</td><td>124/1 698</td><td>135/2 751</td><td>124/1 698</td><td>128/2 129</td></tr><tr><td>3</td><td>0</td><td>[1 5 11 18 22 23 30]</td><td>[111111]</td><td>95/233</td><td>95/233</td><td>84/240</td><td>88/301</td></tr><tr><td>3</td><td>5</td><td>[1 5 11 18 22 23 30]</td><td>[111111]</td><td>105/233</td><td>105/233</td><td>94/240</td><td>98/301</td></tr><tr><td>3</td><td>10</td><td>[1 5 11 18 22 23 30]</td><td>[222222]</td><td>104/240</td><td>115/753</td><td>104/240</td><td>108/301</td></tr><tr><td>3</td><td>15</td><td>[1 5 9 16 23 30]</td><td>[5 55 3 3]</td><td>105/276</td><td>125/1 753</td><td>114/700</td><td>118/1 131</td></tr><tr><td>3</td><td>20</td><td>[1 511 18 22 23 30]</td><td>[222222]</td><td>124/1 700</td><td>135/2 753</td><td>124/1 700</td><td>128/2 131</td></tr><tr><td>4</td><td>0</td><td>[1511 18 22 23 30]</td><td>[111111]</td><td>95/235</td><td>95/235</td><td>84/242</td><td>88/303</td></tr><tr><td>4</td><td>5</td><td>[1 5 11 18 22 23 30]</td><td>[111111]</td><td>105/235</td><td>105/235</td><td>94/242</td><td>98/303</td></tr><tr><td>4</td><td>10</td><td>[1 5 9 16 23 30]</td><td>[5 5 5 5 14]</td><td>104/242</td><td>115/755</td><td>104/242</td><td></td></tr><tr><td>4</td><td>15</td><td>[1 5 9 16 23 30]</td><td>[5 5533]</td><td>105/279</td><td>125/1 755</td><td></td><td>108/303</td></tr><tr><td>4</td><td>20</td><td>[1 5 11 18 22 23 30]</td><td>[222222]</td><td>124/1 702</td><td>135/2 755</td><td>114/702 124/1 702</td><td>118/1 133 128/2 133</td></tr></table></body></html>

![](images/bcf8a7f59b566f95ee191a8139d1dcdac2eca11f1b671214b73b6864ffca6cbf.jpg)  
图3不同运输方式下4PL完成任务的情况Fig.3The 4pls'task under the transportation modes

![](images/21766e74a779a43b079a8c0bc5b4c7ac4ac60447e1d22f27ba44dfa5cf45841d.jpg)  
Fig.2The deviation under the different 3PL quantities   
图4不同转运成本下3PL供应商1,2.5的费用增加幅度图Fig.4The different transfer costs'chart of the 1,2,5 3PL suppliei

# 4 结束语

第四方物流协同路径定制问题（4PLCRCP）是一类复杂的优化问题。本文在考虑转运成本基础上，建立了4PLCRCP的数学模型并设计了基于K 短路的粒子群算法（K-PSO)。通过K-PSO与GA和枚举算法的比较验证了K-PSO的有效性。另外，实验结果表明：如果4PL能够有效整合多个3PL供应商，那么即使在中转节点收取转换费用的情况下，仍然可以起到整合优势3PL、节省费用的目的。

# 参考文献：

[1]Guajardo M,Ronnqvist M.Operations research models for coalition structure in collaborative logistics [J].European Journal of Operational Research,2015,240(1):147-159.   
[2]Huang Min,Cui Yan, Yang Shengxiang.Fourth party logistics routing problem model with fuzzy duration time [J]. International Journal of Production Economics,2013,145(1):107-116.   
[3]Tao Yi, Chew EP,Lee LH.A column generation approach for the route planning problem in fourth party logistics [J].Journal of the Operational Research Society,2017,68(2):165-181.   
[4]Huang Min,Ren Liang,Lee LH.Model and algorithm for 4PLRP with uncertain delivery time [J].Information Sciences,2016,46(C): 211-225.   
[5]Liu Qiong，Zhang Chaoyong，Zhu Keren．Novel multi-objective resource allocation and activity scheduling for fourth party logistics [J]. Computers & Operations Research,2014,44(2):42-51.   
[6]DircksenM,MagninG.Evaluationofsynergypotentials in transportation networks managed by a fourth party logistics provider [J]. Transportation Research Procedia,2017,25(5): 824-841.   
[7]Cui Yan,Huang Min,Yang Shengxiang.Fourth party logistics routing problem model with fuzzy duration time and cost discount [J]. Knowledge Based Systems,2013,50(3):14-24.   
[8]王勇，吴志勇，陈修素，等．面向第4方物流的多代理人作业整合优 化算法[J].管理科学学报，2009,12(2):105-116.(Wang Yong，Wu Zhiyong,Chen Xiusu，et al. Optimization algorithm for multi-agent job integrationforfourth-party-orientedlogistics[J]．Journalof Management Sciences in China,2009,12(2):105-116.)   
[9]姚建明.4PL模式下网购供应链资源整合决策[J].系统管理学报, 2016,25(2):308-316.(Yao Jianming.Resources integration decision for online shopping supply chain with fourth party logistics [J]. Journal of Systems&Management,2016,25(2):308-316.)   
[10]任亮，黄敏，王兴伟．考虑客户拖期厌恶行为的 4PL 路径优化问题 [J]．计算机集成制造系统,2016,22(4):1148-1154.(Ren Liang,Huang Min,Wang Xingwei. Fourth party logistics routing problem considering tardiness aversion behavior of customer [J].Computer Integrated Manufacturing Systems,2016,22(4):1148-1154.)   
[11]林艳，全渝娟，王磊，等．文化基因算法在第四方物流路径规划中的 应用[J].计算机应用研究，2016，33(3):783-787.(Lin Yan，Quan Yujuang,WangLei,Wu Zujiang.Application of memetic algorithm in fourth-party logistics routing problem [J]. Application Research of Computers,2016,33(3):783-787.)   
[12]汪定伟．智能优化方法[M]．北京:高等教育出版社,2007.(Wang Dingwei. Intelligent optimization method[M].Beijing: Higher Education Press,2007.)