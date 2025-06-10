# 基于优先队列的时变网络最短路径算法

杨传印1,2，黄玮1,2†，薛少聪1,²，王劲松1,2(1．天津理工大学 计算机科学与工程学院，天津 30384;2．天津市智能计算和软件新技术重点实验室，天津 300384)

摘要：提出了基于优先队列的时变网络最短路径算法，能克服传统最短路径算法难以对时变网络求解最短路径的缺陷。提出的时间窗选择策略能够在算法求解过程中为节点选择合适的时间窗以降低路径长度，从而求得精确解。进一步地，算法使用了优先队列组织节点集合以提高计算效率。在随机生成的网络数据以及美国道路数据上的实验表明，基于优先队列的时变网络最短路径算法与经典方法相比，不仅能够求得精确解，运算速度也有所提高。

关键词：时变网络；优先队列；最短路径 中图分类号：TP183 doi: 10.3969/j.issn.1001-3695.2017.12.0804

# Time varying network shortest path algorithm based on priority queue

Yang Chuanyin1,2, Huang Wei1,2†, Xue Shaocong1, 2, Wang Jinsong1,2 (1.SchoolofComputerScience&Engineering,TianjinUniversityofTechnology,Tianjin30384,China;2.TanjinKey Laboratory of Intelligent Computing&Novel Software Technology,Tianjin300384, China)

Abstract: Thispaperpresentedatme-varying network shortestpathalgorithmbasedonpriority queue tosolvethe time-varying network shortest path problem which was dificult fortraditionalshortestpath algorithm.Proposedalgorithmcould address optimal solutionbyusing proposedtime-window selection strategy whichcould selectappropriatetime windowforthe nodeto reducethepathlength.Also,thealgorithmused thepriorityqueuetoorganizenodeset,whichcouldimproves thecomputational effciency.Experimentsonrandomlygenerated network dataand united stateroad data show thatcompared with clsical algorithm,theproposedalgorithmisnotonlyabletoobtainglobaloptimalsolutions,butalsoimprovethespeedofthealgorith.

Key words: time varying network; priority queue; shortest path

# 0 引言

最短路径问题是图论和算法设计中的一个基本问题，旨在求解给定网络中给定两点之间的最短路径，在路径规划[1,2]、GPS 导航[3.4]、社交网络[5,6]等领域应用非常广泛。

在众多的最短路径算法中，Dijkstra[是求解单源最短路径的代表算法，其使用贪心策略能够有效求得确定网络中最短路径。但由于时间复杂度较高，Dijkstra 算法并不能在大规模网络中表现出良好的性能。为解决这一问题，学术界对其进行了大量研究。王华[8]利用邻接点算法对Dijkstra 算法进行改进，在一定程度上降低了算法的时间复杂度和空间复杂度；马小雨等人[9]提出从减少搜索计算顶点数量入手,对经典Dijkstra 算法进行改进，提高了算法运行的效率；王树西等人[10]针对算法无法对不连通有向图等问题进行了改进，并将其用于道路选择系统中。尽管上述改进算法具有很多优点，但其仍存在着许多约束条件，未能解决高响应、大规模环境下的网络最短路径问题。2004年，

Throup[11]使用优先队列解决确定网络下的单源最短路径问题，利用优先队列的高效性有效提高了最短路径求解的速度。

传统算法难以解决时变网络最短路径问题。时变网络与普通的静态网络不同之处在于，一点到另一点的距离随着出发时间的变化而变化。这也就使得时变网络中的最短路径问题不仅需要考虑路径中的节点顺序问题，还需要考虑节点的出发时间问题。如图1所示，weight为走过此边所需的时间， $t$ 为对应weight有效的时间区间。若求从节点1至节点3的最短路径，则有可选路径 $_ { 1  2  3 }$ 和 $_ { 1  3 }$ ，且两条路径上分别有4个和2个时间窗。如何在算法运行过程中动态确定路径节点，并正确选择时间窗以使路径最短，是传统方法求解时变网络最短路径的原因。

时变网络比普通网络更为符合生产生活实际，在公路导航[12]、卫星网络[13]和路径规划[14]等方面都更符合实际情况。例如,在实际的道路交通环境下，一条道路在不同的时间区间下的通过时间可能是变化的，这时，使用时变网络模型来模拟道路交通更加科学。学术界已对动态网络最短路径问题进行了广泛研究，并获得了一定的研究成果。戴翠琴等人[13]使用改进的Dijkstra算法解决卫星时变网络中的最短路径算法，邹亮等人[15]使用遗传算法解决动态网络中的最短路径问题；Sever 等人[16]使用以动态规划为基础的综合策略的方式解决变动网络中的最短路径问题。以上方法中大多需要进行多次遍历，因此存在效率低下的问题，基于启发式算法还存在求解精确度不足等问题。

![](images/79b5586c44d729df2d6654fcfa62f9ad5eefd58c3c7f91e13db5956b2783da05.jpg)  
图1时变网络例

本文提出了一种基于优先队列的时变网络最短路径算法，算法使用时间窗选择策略，同时运用优先队列高效性的优点，能够快速求解时变网络最短路径问题。在随机时变网络数据与美国道路地图上的实验表明，提出的算法与经典算法相比，不仅能求得精确最短路径，求解速度也有所提高。

# 1 预备知识

优先队列[17]是一种基于堆的动态排序集合，常使用最小二叉堆为基础进行构造。利用其在数据结构上的优势，能够有效组织节点并提高计算速度。优先队列 $H$ 支持如下操作：

$f i n d M i n ( H )$ ：返回 $H$ 中最小的元素。由于在优先队列中最小元素在队列首位，返回队列中第一个元素即可。此操作时间复杂度为 $o ( 1 )$ 。

insert $( H , a )$ ：向 $H$ 中插入元素 $\boldsymbol { a }$ 。由于在插入后需要对优先队列进行维护,此操作时间复杂度为 $o ( \log n )$ 。

$d e c - k e y ( H , a , x )$ :将对象 $a$ 的值降至 $x$ 。若 $a$ 的值小于 $x$ ，则返回一个错误。此操作时间复杂度为 $o ( \log n )$ 。

extractMin $( H )$ ：去掉并返回 $H$ 中最小值的元素，即队列首元素,此操作时间复杂度为 $o ( \log n )$ 。

优先队列主要应用于基于事件驱动的模型中，一般用于对操作系统中进程的管理。操作系统将进程按优先级或执行时间进行排序后，可每次从队列首位取得需要操作的进程。得益于其较高的排序效率，在队列中某个进程的优先级发生变化时，优先队列能快速地对队列进行重新排序。

在时变网络最短路径规划问题中，由于两点之间的长度由前一个节点的出发时间决定，且一条边长的确定会影响周围多条边的长度，所以对于时变网络最短路径规划问题，需要逐个确定节点的出发时间，并在确定之后更新相邻边的长度。使用优先队列管理网络节点的方法和效果与进程管理相似：首先按节点距离路径开始节点的距离进行排序；每次取队列首位节点进行处理，即确定出发时间；在改变其他节点与开始节点的距离时，快速地重新排序。因此，利用优先队列进行时变网络最短路径规划是可行的。

# 2 问题定义

定义1时变网络（time varying network,TVN）

给定一个有向连通图 $G ( V , A , W )$ ，其中 $V = \{ \nu _ { 1 } , \nu _ { 2 } , . . . , \nu _ { n } \}$ 为图中节点集合， $A = \{ ( \nu _ { i } , \nu _ { j } ) | \nu _ { i } , \nu _ { j } \in V \}$ 为图 $G$ 中边的集合， $W$ 为一组时变函数，则称 $G$ 为时变网络。

在时变函数 $W _ { p q } ( t ) \in W$ 中， $W _ { p q } ( t )$ 为自 $\boldsymbol { \nu } _ { p }$ 至 $\nu _ { _ q }$ 且出发时刻为$t$ 时，边 $( \nu _ { _ { p } } , \nu _ { _ { q } } )$ 的长度。

定义2时间窗（time window）

在时变网络中，时间区间 $[ l , u )$ 称为时间窗。其中 $\mathbf { \xi } _ { l }$ 为时间窗下界， $u$ 为时间窗上界。对于时间窗集合 $[ l _ { 1 } , u _ { 1 } ) , . . . , [ l _ { m } , u _ { m } )$ ，若 $l _ { \mathrm { 1 } } = 0$ 且 $l _ { k } < u _ { k } = l _ { k + 1 }$ $( k = 1 , . . . , m )$ ，则称此集合为时间窗集。

设边 $( \nu _ { _ { p } } , \nu _ { _ { q } } )$ 上有时间窗集 $t w _ { p q }$ ， $t w _ { p q }$ 包含 $m$ 个时间窗，即${ t w _ { p q } } = \{ { t w _ { p q } ^ { i } } \vert i = 1 , . . . , m \}$ ,则在时变网络中，有

$$
W _ { p q } ( t ) = \left\{ \begin{array} { l l } { \theta _ { 1 } } & { , t \in t w _ { p q } ^ { 1 } } \\ { } \\ { \cdots } \\ { \theta _ { m } } & { , t \in t w _ { p q } ^ { m } } \end{array} \right.
$$

其中： $\theta _ { i }$ 为时间 $t$ 属于在时间窗 $t w _ { p q } ^ { i }$ 中时，边 $( \nu _ { p } , \nu _ { q } )$ 的长度。

定义3时变网络的路径（apathofTVN)

对于有序序列 $p a t h { = } { < } ( \nu _ { 1 } , t _ { 1 } ) , . . . , ( \nu _ { n } , t _ { n } ) >$ ， $\nu _ { i }$ 为序列中第i个节点， $t _ { i }$ 为 $\nu _ { i }$ 的出发时间，则称path为时变网络的一条路径。由此也可以得出，路径 path 的节点路由为节点序列 $< \nu _ { 1 } , \nu _ { 2 } , . . . , \nu _ { n } >$ 。

时变网络最短路径求解问题即在给定的时变网络 $G$ 中为每个节点 $\nu$ 选择全局最优的出发时间t，使自起点 $s$ 至终点 $T$ 的距离最小。由此，时变网络的最短路径问题可定义为

$$
\left\{ \begin{array} { l l } { \displaystyle \operatorname* { m i n } _ { \mathrm { ( } \boldsymbol { p } , \boldsymbol { q } ) \in A } x _ { \boldsymbol { p q } } \times W _ { \boldsymbol { p q } } \left( t _ { i } \right) } \\ { \mathrm { s u b j e c t ~ t o : } \quad \displaystyle \sum _ { ( 1 , \boldsymbol { p } ) \in A } x _ { \boldsymbol { 1 q } } - \displaystyle \sum _ { ( \boldsymbol { q } , \boldsymbol { 1 } ) \in A } x _ { \boldsymbol { q } } \left( 1 + \right. } \\ { \displaystyle \sum _ { ( \boldsymbol { p } , \boldsymbol { q } ) \in A } x _ { \boldsymbol { p q } } - \displaystyle \sum _ { ( \boldsymbol { q } , \boldsymbol { p } ) \in A } x _ { \boldsymbol { q p } } = 0 } \\ { \displaystyle \sum _ { ( \boldsymbol { n } , \boldsymbol { q } ) \in A } x _ { \boldsymbol { n q } } - \displaystyle \sum _ { ( \boldsymbol { q } , \boldsymbol { n } ) \in A } x _ { \boldsymbol { q } } = - 1 } \\ { \displaystyle x _ { \boldsymbol { p q } } \in ( 0 , 1 ) , \forall ( \boldsymbol { p } , \boldsymbol { q } ) \in A } \end{array} \right.
$$

其中： $\sum _ { ( p , q ) \in A } x _ { p q } \times W _ { p q } ( t _ { i } )$ 为最短路径长度; $x _ { p q }$ 为边 $( p , q )$ 是否存在于网络中的标志； $W _ { p q } ( t _ { i } )$ 为边 $( p , q )$ 在 $t _ { i }$ 时刻出发的长度。

# 3 基于优先队列的时变网络最短路径算法

在时变网络中，两点之间的距离由起点的出发时间决定。因此要求解时变网络中的最短路径，应逐个确定节点的出发时间。所以，算法主要问题在于如何高效组织节点，并在对迭代过程中节点的变化及时进行维护。优先队列具有便于取出元素、排序快、维护代价低等优点。采用优先队列按与出发节点的距离的方式组织节点，便于在迭代过程中快速取得与出发节点最近的节点。在更新过程中，若某节点的情况发生变化，优先队列可快速调整其位置，维护代价较低。因此，采用优先队列组织时变网络中的节点更为高效。

# 3.1算法流程

图2给出了算法的流程。算法基本流程如下：首先对给定的时变网络进行处理，得到优先队列；然后进行迭代循环：为队列首节点的后置节点选择时间窗并更新其与出发节点的距离，而后移除队列首节点，直至移除了目标节点；最后从目标节点开始，沿前置节点向出发节点回溯，得到最短路径。据此，算法可分为三个部分，即优先队列初始化部分、节点更新部分及生成最短路径部分。算法的各个部分功能分述如下：

$\textcircled{1}$ 优先队列初始化。负责对给定时变网络进行搜索以生成优先队列，并初始化节点。在节点搜索过程中，首先使用广度优先搜索算法获得有序节点序列，并为每个节点赋初值，完成优先队列及节点初始化。在广度搜索过程中，使用给定的出发节点S作为搜索的起点，以使S为队列首节点。最后对 $s$ 进行初始化。

$\textcircled{2}$ 节点更新。负责节点迭代更新及优先队列维护，以求出最短路径长度。每次迭代首先对队列首节点的后置节点进行时间窗选择及相关信息更新，然后将队列首节点移除并维护队列。重复此过程，直至将目标节点自优先队列移出。

$\textcircled{3}$ 生成最短路径。在节点更新的过程中，会同时为节点记录当前最短路径中本节点的前置节点。在节点更新完成后，通过自目标节点的前置节点向出发节点递归回溯，即可得到最短路径。

![](images/6d01936b20bc15d0570d10e2bcdd15137b657c75a9aae4f4808bb7edaf87dbc6.jpg)  
图2基于优先队列的时变网络最短路径算法流程

# 3.2算法形式化描述

下面介绍算法的形式化描述。在开始之前，首先给出算法中的符号及符号释义，见表1。

表1符号描述  

<html><body><table><tr><td>符号</td><td>符号含义</td></tr><tr><td>G</td><td>时变网络</td></tr><tr><td>A</td><td>符合优先队列结构的节点集合</td></tr><tr><td>BS(v)</td><td>节点V的后置节点</td></tr><tr><td>L</td><td>已选择时间窗的节点集合</td></tr><tr><td>S</td><td>出发节点，即最短路径起点</td></tr><tr><td>T</td><td>目标节点，即最短路径终点</td></tr><tr><td>twpq</td><td>边(p,q)上的时间窗集</td></tr><tr><td>twp</td><td>twpq 的第i个时间窗</td></tr><tr><td></td><td>twq的下界</td></tr><tr><td>u</td><td>tw的上界</td></tr><tr><td></td><td>选择twpq时边(p,q)的长度</td></tr><tr><td>F</td><td>V的父节点</td></tr><tr><td>tv</td><td>V出发时间</td></tr><tr><td>d</td><td>点V当前最短路径长度，即与S的距离</td></tr></table></body></html>

基于优先队列的时变网络最短路径算法如下所示。其与流程图对应关系如下：步骤 $1 { \sim } 3$ 为优先队列初始化部分；步骤$4 { \sim } 6$ 为节点更新部分；步骤 $7 { \sim } 8$ 为最短路径生成部分。

算法1基于优先队列的时变网络最短路径算法  
输入： $G$ 、S、 $T$ 。  
输出：最短路径path 及最短路径长度 $d _ { { } _ { T } }$ 。  
以 $s$ 为起点，对图 $G$ 进行广度搜索，获得包含图中全部节点的有序序列$A = \{ S , . . . , l _ { i } , . . . , T , . . . , l _ { n } \}$ ，设集合 $L = \{ \mathcal { O } \}$   
对 $A$ 中的每个节点 $\nu$ 设 $d _ { \nu } = \infty$ ， $F _ { \nu } = \mathcal { O }$   
设 $d _ { _ { A [ 0 ] } } = 0$ ，即 $d _ { s } = 0$   
当 $T \not \in L$ 时，循环步骤4-5：  
使用算法2更新 $\mathbf { \boldsymbol { A } } [ 0 ]$ 及 $B S ( A [ 0 ] )$   
令 $L = \{ L , A [ 0 ] \}$ ，并执行 extractMin(A)  
执行算法3，得到最短路径path  
输出，得到最短路径path 及最短路径长度 $d _ { { } _ { T } }$

算法2为节点更新算法。此子算法首先使用时间窗选择策略为节点选择时间窗，而后更新节点 $q$ 的当前最短路径 $d _ { \boldsymbol { q } }$ ，最后对优先队列进行维护。在算法输入部分中， $\boldsymbol { A } [ 0 ]$ 为优先队列首节点，BS(A[O])为时变网络中 A[O]的后置节点。

由第2章定义2及3可知，时间窗集合是由一系列非负且不重叠的时间区间组成的，每个时间区间都有其对应的边长。因此在为节点选择时间窗时，首先根据前置节点的出发时间排除无效的时间窗，然后计算每个时间窗在其最早时间出发的对应的路径长度，最后在路径长度最小的时间窗中取其出发时间。

根据分析，可得出时间窗选择策略：

为 $t w _ { p q }$ 中的每个时间窗计算对应长度 $\boldsymbol { d } _ { \boldsymbol { q } } ^ { \prime }$ ：若 $d _ { p } > u _ { p q } ^ { i }$ ，则视为此时间窗过期，令 $\dot { d _ { q } } = \infty$ ；若 $d _ { p } \in t w _ { p q } ^ { i }$ ，即 $d _ { p }$ 在时间窗中，则立即出发，令 $\dot { d _ { q } } = d _ { p } + \dot { \theta _ { p q } ^ { i } }$ ；若 $d _ { p } < l _ { p q } ^ { i } \ d _ { p }$ ，即 $d _ { p }$ 早于此时间窗,则等待 $l _ { p q } ^ { i } - d _ { p }$ 个单位时间，令 $d _ { q } ^ { ' } = l _ { p q } ^ { i } + \theta _ { p q } ^ { i }$ 。

为使得节点 $\boldsymbol { q }$ 能取得最短长度，若 $\dot { d _ { q } } < d _ { q }$ ，则使 $d _ { q } = d _ { q } ^ { ' }$ ，并记录当前最短路径的前置节点 $F _ { q } = p$ 。

算法2节点更新算法

输入： $\boldsymbol { A } [ 0 ]$ 、BS(A[0])、 $t w _ { p q }$ 、 $\boldsymbol { d } _ { p }$ 、 $d _ { \boldsymbol { q } }$   
输出：更新后的 $d _ { \boldsymbol { q } }$ 及更新后的优先队列 $A$ 。   
令 $p = A [ 0 ]$ ， $q \in B S ( A [ 0 ] )$ 对于 $t w _ { p q }$ 中的每个时间窗 $t w _ { p q } ^ { i }$ 若 $d _ { p } < l _ { p q } ^ { i }$ ，则设 $\dot { d _ { q } ^ { \prime } } = l _ { p q } ^ { i } + \theta _ { p q } ^ { i }$ ， $t _ { q } ^ { ' } = l _ { p q } ^ { i }$   
若 $l _ { p q } ^ { i } \leq d _ { p } < u _ { p q } ^ { i }$ ，则设 $d _ { q } ^ { ' } = d _ { p } + \theta _ { p q } ^ { i } t _ { q } ^ { ' } = d _ { p }$   
若 $d _ { p } > u _ { p q } ^ { i }$ ，则设 $\dot { d _ { q } ^ { * } } = \infty$ （204号   
若 $d _ { q } > d _ { q } ^ { ' }$ ，则设 $d _ { q } = d _ { q } ^ { ' }$ ， $F _ { q } = p$ ， $t _ { { _ q } } = t _ { { _ q } } ^ { ' }$   
对 $A$ 执行 $d e c - k e y ( A , q , d _ { q } )$ （204   
算法结束

当节点迭代完成后，集合 $\textbf { \em L }$ 中除 $s$ 以外的所有节点的 $F _ { \nu }$ 都已被赋值。可使用算法3从 $T$ 开始向前根据 $F _ { \nu }$ 向前迭代回溯至$s$ 得到所求最短路径。

算法3路径回溯算法   
输入： $T$ 、 $\boldsymbol { F } _ { \nu }$ 、 $s$ 。   
输出：最短路径path。   
设 $q = T$ ，并有有序序列 $\scriptstyle p a t h = < q >$   
当 $S \not \in p a t h$ 时，循环步骤3-4 （204号 $q = F _ { _ q }$ （20 $p a t h = < q , p a t h >$   
算法结束，得到最短路径路由path

# 3.3算法实例

为了进一步说明算法的运行过程，下面使用图3中的时变网络进行算例演示。图3中共有5个节点，出发节点 $s$ 和目标节点 $T$ 已经标出。

![](images/12832a7be3be85f3d2ca0dafe5bb8a637aaa013fe03a4e359f0c8ca0a775bd09.jpg)  
图3算例网络结构

时变网络的详细信息见表2。网络中的每条边都有 $1 { \sim } 2$ 个时间窗。其中时间窗为 $[ 0 , \infty )$ 的表示不论何时出发，边的长度都为对应的 $\theta$ 值。

图4将算法运行过程以优先队列结构进行展示，圆内标号为节点序号，括号内为节点 $\boldsymbol { d } _ { \nu }$ 。图4中 $\textcircled{1}$ 为初始化后的优先队列结构，从 $\textcircled{2}$ 开始使用算法2对优先队列进行更新， $\textcircled{9}$ 为最短路径长度及使用算法3求得的最短路径。

下面对每个步骤图进行解释：

运行算法1的第 $1 { \sim } 2$ 步。使用广度搜索对图 $G$ 进行搜索，生成优先队列A，并对 $A$ 中的节点进行初始化得到优先队列，最后初始化S点。

表2时变网络信息  

<html><body><table><tr><td>节点</td><td>后置边</td><td>tWpq</td><td>0</td></tr><tr><td rowspan="3">S</td><td>(S,1)</td><td>[0,1)</td><td>1</td></tr><tr><td></td><td>[1,8)</td><td>3</td></tr><tr><td>(S,2)</td><td>[0,2)</td><td>1</td></tr><tr><td>1</td><td>(1,T)</td><td>[0,0)</td><td>5</td></tr><tr><td rowspan="3">2</td><td>(2,3)</td><td>[0,8)</td><td>3</td></tr><tr><td>(2,T)</td><td>[0,2)</td><td>4</td></tr><tr><td></td><td>[2,8)</td><td>1</td></tr><tr><td>3</td><td>(3,T)</td><td>[0,8)</td><td>2</td></tr></table></body></html>

对 $\boldsymbol { A } [ 0 ]$ 即 $s$ 点的邻居节点1、2使用算法2更新节点信息，其中时间窗 $t w _ { s 1 }$ 及 $t w _ { s 2 }$ 都选择了第1个时间窗， $\theta$ 均为1。

将队列首元素 $s$ 并入 $\textbf { \em L }$ 中，并从 $A$ 中删除，维护优先队列。此时队列首节点为节点1。

运行算法2更新节点1的邻居节点 $T$ 并维护优先队列。更新后 $d _ { r } = 6$ ，由于 $\begin{array} { r } { d _ { \scriptscriptstyle T } < d _ { \scriptscriptstyle 3 } } \end{array}$ ， $T$ 节点在队列中的位置高于节点3。

将队列首元素节点1并入 $\textbf { \em L }$ 中，从 $A$ 中删除节点1并维护优先队列。此时队列首节点为节点2。

运行算法2更新节点2的邻居节点3、 $T$ ，更新后 $T$ 选择了 $t w _ { 2 T } ^ { 2 } = [ 2 , \infty )$ ， $d _ { r } = 3$ ， $d _ { 3 } = 4$ 。

将队列首元素节点2并入 $\boldsymbol { L }$ 中，并从 $A$ 中删除。此时 $T$ 为队列首节点。

由于 $T$ 没有后置节点，运行算法2后无值更新。将队列首元素 $T$ 并入 $\textbf { \em L }$ 中，并从优先队列中删除。此时节点循环更新结束，得到最短路径长度 $\begin{array} { r } { d _ { \cal T } = 3 } \end{array}$ 。

![](images/0364fbcc0b139b6e0b1814d2463d8a3862c8ae24f323a8006df51fa4cb536963.jpg)  
图4算例计算过程

使用算法3完成最短路径回，得到最短路径path，算法结束。

表3给出了算法运行过程中每个节点各项值的变化。关注目标节点 $T$ 在图4的 $\textcircled{4}$ 和 $\textcircled{6}$ 的两次数据变化，可以发现时间窗选择策略在寻找最优解中发挥的作用：

在 $\textcircled{4}$ 中，节点1为队列首元素， $d _ { 1 } = 1$ 。边 $( 1 , T )$ 上有唯一时间窗 $t w _ { 1 T } ^ { 1 } = [ 0 , \infty )$ $\theta _ { 1 T } ^ { 1 } = 5$ ，因此 $d _ { \scriptscriptstyle T } = d _ { \scriptscriptstyle 1 } + \theta _ { \scriptscriptstyle 1 T } ^ { \scriptscriptstyle 1 } = 6$ 。

在 $\textcircled{6}$ 中，节点2为队列首元素， $d _ { 2 } = 1$ 。边 $\left( 2 , T \right)$ 上有2个时间窗 $t w _ { 2 T } ^ { 1 } = [ 0 , 2 ]$ $\theta _ { 2 T } ^ { 1 } = 4$ 和 $t w _ { 2 T } ^ { 2 } = [ 2 , \infty )$ $\theta _ { 2 T } ^ { 2 } = 1$ ，对两个时间窗分析如下：

若选择 $t w _ { 2 T } ^ { 1 }$ ，即在1时刻立即出发， $d _ { \phantom { \prime } _ { T } } ^ { \prime } = d _ { 2 } + \theta _ { 2 T } ^ { 1 } = 1 + 4 { = } 5$ ：若选择 $t w _ { 2 T } ^ { 2 }$ ，即在2时刻出发， $d { \bf \Gamma } _ { T } ^ { \prime } = l _ { 2 T } ^ { 2 } + \theta _ { 2 T } ^ { 2 } = 2 + 1 = 3$ 。

所以，选择 $t w _ { 2 T } ^ { 2 }$ ，即在节点2处等待1个单位时间，并在时刻2出发，可以使得 $d _ { \scriptscriptstyle T }$ 达到最小值3。

表3节点状态  

<html><body><table><tr><td></td><td colspan="3">? S 0</td><td colspan="4">? C 9</td><td colspan="4">Θ 节点</td></tr><tr><td>乙</td><td colspan="4">S</td><td>S</td><td colspan="4">S 0 8</td><td></td><td>乙</td><td>I S</td></tr><tr><td>εt I I</td><td colspan="4">0 乙 乙</td><td>8 0 Q S S Q</td><td colspan="4">8 8 Q Q S S Q</td><td>8 Q 8</td><td>Q</td><td>8 0</td><td></td></tr><tr><td>乙 乙</td><td colspan="4">ss Q</td><td>8 Q</td><td colspan="4">Q</td><td></td><td></td><td>Q</td><td>Q</td></tr><tr><td>8 8</td><td>Q</td><td>8</td><td>8 亿</td><td>Q</td><td></td><td></td><td></td><td>I Q Q</td><td>Q Q</td><td></td><td></td><td>Q</td><td></td></tr><tr><td>7</td><td>Ｈ７７</td><td>7</td><td>VH 7</td><td>７７</td><td>VVH</td><td>7</td><td>7</td><td>VHHH</td><td>7</td><td></td><td></td><td>VWHV</td><td>所在集合</td></tr></table></body></html>

注：图中深色格为迭代后变化的内容。

# 3.4算法分析

# 3.4.1正确性分析

下面使用反证法来证明算法的正确性。由算法实例可以发现，在算法运行过程中，任意时刻时变网络中的任意一个节点一定属于集合 $A$ 或集合 $\boldsymbol { L }$ 。由此有以下定理：

定理1最短路径上的所有节点都属于集合 $\textbf { \em L }$ 。

证明由图5所示，假设有从 $s$ 到 $T$ 的路径 $p$ 和路径 $p ^ { \prime }$ ，其中 $p ^ { \prime } = p _ { 1 } + p _ { 2 }$ ，其中 $p$ 中的节点全部属于集合 $\boldsymbol { L }$ ，在 $p ^ { \prime }$ 中有至少一个节点在集合 $A$ 中，即图中的 $\boldsymbol { a }$ 点。当算法停止时， $T \in L$ 而 $a \not \in L$ ，说明有 $\boldsymbol { d } _ { \boldsymbol { T } } \leq \boldsymbol { d } _ { \boldsymbol { a } }$ 。同时，由于图中边长皆为正值，所以有 $p$ 的长度小于 $p ^ { \prime }$ 。

定理1得证。

定理1从算法迭代的角度证明了最短路径中的节点均已求得当前最短路径。下面定理2从时间窗角度证明了时间窗选择策略能为节点选择最优时间窗以求得当前最短路径。

![](images/daa9f11a071275338eeae4af963977902ee073595e688e432f814393eeb5815c.jpg)  
图5正确性说明图

定理2最短路径上的任意节点的出发时间所对应的当前路径长度都是最小的。

证明设有最短路径 $p a t h { = } { < } ( \nu _ { 1 } , t _ { 1 } ) , . . . , ( \nu _ { n } , t _ { n } ) >$ ，对于任意节点 $\nu _ { i }$ ，其当前路径长度 $d _ { i } = t _ { i } + \theta _ { i }$ 。由于 $\theta _ { i }$ 由 $t _ { i }$ 决定，因此 $d _ { i }$ 主要受 $t _ { i }$ 影响。下面讨论 $t _ { i }$ 在不同情况下对 $d _ { i }$ 的影响：

(1)设有 $t _ { i } ^ { ' } < t _ { i }$ ，使得 $\boldsymbol { d } _ { i } ^ { ' } = \boldsymbol { t } _ { i } ^ { ' } + \boldsymbol { \theta } _ { i } ^ { ' }$ ：由算法2的步骤1可知,$t _ { i }$ 可取值可能为 $d _ { i - 1 }$ 或 $l _ { i , i + 1 }$ （选定时间窗下界）。若 $t _ { i } ^ { ' } < d _ { i - 1 }$ ，根据算法2步骤1.c, $\dot { d _ { i + 1 } ^ { ' } } = \infty$ ；若 $t _ { i } ^ { ' } < l _ { i , i + 1 }$ ，根据算法2步骤1.d,$d _ { i } < d _ { i } ^ { ' }$ 。因此，若 $t _ { i } ^ { ' } < t _ { i }$ 则定有 $d _ { i } < d _ { i } ^ { ' }$ 。

（2）设有 $t _ { i } ^ { ' } > t _ { i }$ ，使得 $\dot { d _ { i } ^ { ' } } = \dot { t _ { i } ^ { ' } } + \dot { \theta _ { i } ^ { ' } }$ ，则有以下两种情况： $t _ { i } ^ { ' }$ 与 $t _ { i }$ 在同一时间窗内，或不在同一时间窗内。若 $t _ { i } ^ { ' }$ 与 $t _ { i }$ 在同一时间窗内，则有 $\dot { d _ { i + 1 } } = t _ { i } + \varepsilon + \theta _ { i }$ ，由于 $\varepsilon$ 为任意正数，所以 $d _ { i } < d _ { i } ^ { ' }$ ：若 $t _ { i } ^ { ' }$ 与 $t _ { i }$ 不在同一时间窗内，根据算法2步骤1.d， $d _ { i } < d _ { i } ^ { ' }$ 。因此，若 $t _ { i } ^ { ' } > t _ { i }$ 则定有 $d _ { i } < d _ { i } ^ { ' }$ 。

定理2得证。

3.4.2时间复杂度分析

定理3在具有 $n$ 个节点和 $m$ 个时间窗的时变网络中，基于优先队列的时变网络最短路径算法的时间复杂度为$o ( 3 n + m n + n \log ( n ) )$ 。

证明下面对三个算法进行时间复杂度分析：

算法2：假设每个节点有 $m$ 个时间窗，步骤1需要循环 $m$ 次，步骤2对优先队列的维护在最差情况下需要 $o ( \log ( n ) )$ 的时间。所以算法2的总时间为 $m + o ( \log ( n ) )$ 。

算法3：此算法是一个递归算法，用于递归求出最短路径路由。在最坏情况下，所有节点都在最短路径上，算法4的时间复杂度为 $o ( n )$ 0

算法1：对节点的广度搜索及节点初始化需要遍历所有节点，即时间复杂度为 $\ o ( n ) \times 2$ ；初始化出发节点时间复杂度为 $o ( 1 )$ ：步骤4-6的循环在最差情况下需要循环 $n$ 次，所以时间复杂度为 $n \times ( m + o ( \log ( n ) ) )$ ；循环结束后的算法4时间复杂度为 $o ( n )$ 。由此可得出算法的时间复杂度为

$$
\begin{array} { c } { { o ( n ) + o ( n ) + o ( 1 ) + n \times \left( m + o ( \log ( n ) ) \right) + o ( n ) } } \\ { { { } } } \\ { { = o ( 3 n + n ^ { 2 } + n \log ( n ) ) \enspace _ { \circ } } } \end{array}
$$

定理3得证。

由定理3可得到如下关于时间窗数量与算法性能的推论：

推论1若 $m < \log ( n )$ ，时间窗数量将不会对算法性能造成明显影响；若 $m > n$ ，算法的时间复杂度将显著提高。

证明由算法的三个主要部分分别是初始化、时间窗选择、节点迭代，分别耗时 $o ( 2 n )$ 、 $o ( m n )$ 和 $o ( n \log ( n ) )$ □

(1)若 $m < \log ( n )$ ，则 $o ( m n ) < o ( n \log ( n ) )$ ，算法迭代的时间大于选择时间窗的时间。

（2）若 $m > \log ( n )$ ，则 $o ( m n ) > o ( n \log ( n ) )$ ，时间窗选择的时间将超过迭代操作的时间。

(3）若 $m > n$ ，时间复杂度将大于 $o ( 3 n + n ^ { 2 } + n \log ( n ) )$ ，时间复杂度明显增长。此时，节点的时间窗复杂度会较大地影响算法的性能。

# 4 实验

本章将用Dijkstra 算法、Thorup[]的方法和基于优先队列的时变网络最短路径算法在5个随机生成的时变网络及美国道路网络进行实验对比。实验环境： $\mathrm { I n t e l ^ { ( R ) } C o r e ^ { T M } i 7 - 6 7 0 0 } 3 . 4 \mathrm { G H z }$ 16 GB内存，128GB SSD硬盘，Windows10 操作系统，VisualStudio 2015编程软件，C#语言实现。

# 4.1 随机地图测试

本组实验数据共5组，节点个数分别为 $1 0 0 0 { \sim } 9 0 0 0$ 个,使用Randgraph （http://www.dis.uniromal.it/challenge9/download.shtml）生成，对于地图中的每条边，参考此边的长度随机添加时间窗。表4概括了实验网络结构信息。

表4随机网络结构信息  

<html><body><table><tr><td>实验数据</td><td>节点数量</td><td>边数量</td><td>时间窗数量</td></tr><tr><td>D</td><td>1000</td><td>1507</td><td>4022</td></tr><tr><td>D</td><td>3000</td><td>4479</td><td>8743</td></tr><tr><td>D3</td><td>5000</td><td>7450</td><td>16871</td></tr><tr><td>D4</td><td>7000</td><td>10489</td><td>22354</td></tr><tr><td>D5</td><td>9000</td><td>13542</td><td>30874</td></tr></table></body></html>

每组实验都会随机选择一个出发节点和一个目标节点，进行多次重复实验。在实验过程中，基于优先队列的时变网络最短路径算法采用时间窗选择策略，其余两算法均采用选择首个可用时间窗以决定两点间的距离。

表5随机生成地图下的实验结果  

<html><body><table><tr><td rowspan="2">数据编号</td><td colspan="2">Dijkstra</td><td colspan="2">Thorup (2004)</td><td colspan="2">提出的方法</td></tr><tr><td>Error%</td><td>CT(ms)</td><td>Error%</td><td>CT(ms)</td><td>Error%</td><td>CT(ms)</td></tr><tr><td>D</td><td>10.74%</td><td>18</td><td>10.74%</td><td>7</td><td>0%</td><td>13</td></tr><tr><td>D</td><td>17.05%</td><td>136</td><td>17.05%</td><td>42</td><td>0%</td><td>46</td></tr><tr><td>D3</td><td>19.88%</td><td>377</td><td>19.88%</td><td>131</td><td>0%</td><td>138</td></tr><tr><td>D4</td><td>23.90%</td><td>839</td><td>23.90%</td><td>226</td><td>0%</td><td>233</td></tr><tr><td>D5</td><td>23.96%</td><td>1565</td><td>23.96%</td><td>366</td><td>0%</td><td>372</td></tr></table></body></html>

表5为三种算法在随机网络上的实验结果，包括每种算法在不同数据集下的错误率以及运算时间（CT)。错误率为0表示算法达到了全局最优解。由表5可以看出，提出的方法由于采用了优先队列结构，在5组数据中求解时间增长幅度不大，符合时间复杂度预期；相比之下，Dijkstra算法的运算时间增长迅速，在 ${ \bf D } _ { 5 }$ 数据集下耗时是提出算法的4倍；由于没有时间窗选择过程，Thourp的运算速度较提出的方法稍快；在运算精确度方面，提出的算法采用了时间窗选择策略，可取得最优时间窗并求得最短路径，在5组实验中均能够能求得最优解。而Dijkstra和Throup由于直接选用首个可用时间窗，从而产生了一定且相同的误差。

# 4.2美国道路地图测试

为了测试算法在真实网络中的性能，本节使用美国道路地图（http://www.dis.uniromal.it/challenge9/downloa d.shtml）进行测试。由于美国道路地图是静态道路网络，为了完善实验过程，实验前为网络中的部分边添加了时间窗。表6为实验网络结构信息。

表6实验用美国道路网络结构信息  

<html><body><table><tr><td>实验数据</td><td>节点数量</td><td>边数量</td><td>时间窗数量</td></tr><tr><td>New York- Dy</td><td>264,324</td><td>733,846</td><td>1,731,876</td></tr><tr><td>Colorado- Dc</td><td>435,666</td><td>1,057,066</td><td>2,621,523</td></tr><tr><td>Florida- DF</td><td>1,070,376</td><td>2,712,798</td><td>6,917,634</td></tr></table></body></html>

与随机网络数据的实验方法相同，表7中列出了在美国道路地图中的实验结果。在大规模网络中，提出的算法依然能够求得全局最优解，而其他算法由于难以选取最优时间窗，出现了 $1 0 \% \sim 2 0 \%$ 的计算误差。计算时间上，在美国道路地图中，Dijkstra 算法的计算时间上升最快，26万节点的平均计算时间为 $9 ~ \mathrm { m i n }$ ，100万节点的计算时间已经达到了约 $^ \textrm { \scriptsize 1 h }$ 。而提出的方法在26万节点中的计算时间在 $3 \mathrm { ~ s ~ }$ 以下，100万节点的平均计算时间约为 $9 \mathrm { ~ s ~ }$ ，体现出优先队列结构在运算速度上的优势；时间窗选择会消耗一部分运算时间，在 $\mathbf { D } _ { Y }$ 组中，提出的算法用Thorup $[ 1 1 ] _ { 1 0 \% }$ 的时间换取了 $1 1 . 3 7 \%$ 的准确度，在 $\mathbf { D } _ { { F } }$ 组中用Thorup $[ 1 1 ] _ { 3 \% }$ 的额外运算时间换取了 $20 \%$ 的准确度。

# 5 结束语

本文提出了一种基于优先队列的时变网络算法用于求解时变网络中的最短路径问题。提出的算法采用时间窗选择策略以克服传统算法难以对时变网络求最短路径精确解的问题。同时，算法采用优先队列组织网络节点，提高了算法求解速度。在随机实验数据及真实网络数据的实验表明，基于优先队列的最短路径算法能够快速求得时变网络最短路径的全局最优解。提出的算法在智能交通、路径规划及无人车等领域有更加广阔的应用前景。

表7美国道路地图下的实验结果  

<html><body><table><tr><td rowspan="2">数据编号</td><td colspan="2">Dijkstra</td><td colspan="2">Thorup (2004)</td><td colspan="2">提出的方法</td></tr><tr><td>Error%</td><td>CT(s)</td><td>Error%</td><td>CT(s)</td><td>Error%</td><td>CT(s)</td></tr><tr><td>Dy</td><td>11.37%</td><td>475.7</td><td>11.37%</td><td>2.61</td><td>0%</td><td>2.95</td></tr><tr><td>Dc</td><td>13.48%</td><td>615.5</td><td>13.48%</td><td>3.183</td><td>0%</td><td>3.446</td></tr><tr><td>DF</td><td>20.01%</td><td>3578</td><td>20.01%</td><td>8.943</td><td>0%</td><td>9.223</td></tr></table></body></html>

# 参考文献：

[1]王志中．基于改进蚁群算法的移动机器人路径规划研究[J].机械设计与制造,2018(1):242.  
[2]段宗涛,WangWeixing，康军，等．面向城市交通网络的K最短路径集合算法[J].交通运输系统工程与信息,2014,14(3):194.  
[3]董俊，黄传河.改进Dijkstra 算法在GIS导航应用中最短路径搜索研究[J].计算机科学,2012,39(10):245  
[4]韩非子．基于GIS的城市消防导航信息系统研究与应用[J].通讯世界，2017(12): 253.  
[5]付东炜．一种基于社交网络的社区关键节点的最短路径算法[J].科技资讯,2017,15(10):223.  
[6]Rezvanian A,Meybodi MR. Sampling social networks using shortest paths[J].Physica A Statistical Mechanics& Its Applications,2015,424: 254.  
[7]Dijkstra E W.A note on two problems in connexion with graphs [J].Numerische mathematik,1959,1(1): 269.  
[8]王华．基于邻接点算法的 Dijkstra 优化研究[J].计算机与数字工程,2013,41 (4): 518.  
[9]马小雨，余建国.Dijkstra 算法优化及其在GIS 中的应用[J].计算机光盘软件与应用,2014,17(11):58.  
[10]王树西，吴政学．改进的Dijkstra最短路径算法及其应用研究[J].计算机科学,2012,39(5):223.  
[11] Thorup M. Integer priority queues with decrease key in constant time andthe single source shortest paths problem [J].Journal of Computer& SystemSciences,2004,69 (3):330.  
[12]唐金环，戢守峰，沈贵财．时变网络下考虑碳排放的车辆路径优化[J].系统工程,2015,33(9):37.  
[13]戴翠琴，李剑，唐煌．卫星时变网络中基于连接计划的最短路径优化算法[J].重庆邮电大学学报：自然科学版,2017,29(01):29.  
[14]胡腾波，叶建栲.GIS时变权值网络最短路径算法研究[J].计算机与现代化,2008 (11):22.  
[15]邹亮，徐建闽．基于遗传算法的动态网络中最短路径问题算法[J].计算机应用,2005(4):742.  
[16] Sever D,Dellaert N,Van Woensel T,et al.Dynamic shortest path problems:Hybrid routing policies considering network disruptions [J]. Computers &Operations Research,2013,40 (12): 2852.  
[17] Thomas H. Cormen,introduction to algorithms.[M].3rd ed.Massachusets:The MIT Press,2009:183.