# 基于单个移动信标节点的路径规划方法

乔学工，段亚青

(太原理工大学 信息与计算机学院，太原 030024)

摘要：在基于移动信标节点的无线传感器网络中，移动信标节点的路径规划问题直接影响定位性能，针对现有路径规划方法没有充分考虑到网络内未知节点的分布情况，存在定位覆盖率低且网络成本高的问题，设计了一种基于单个移动信标节点的路径规划方法，先通过网络内未知节点的分布情况，确定虚拟信标节点的位置以及数目；然后提出了一种基于高斯递减策略的非线性动态变化收敛因子改进灰狼优化算法，用于TSP算法求解路径规划问题，获得移动信标节点最短移动路径。仿真结果表明，该方法有效地提高了网络内未知节点的定位覆盖率，并且有效节省了网络成本。

关键词：无线传感器网络；移动信标节点；虚拟信标节点；灰狼优化算法；路径规划 中图分类号：TP393 doi:10.19734/j.issn.1001-3695.2018.07.0546

Path planning method based on single mobile beacon node

Qiao Xuegong, Duan Yaqing (Institute of Information & Computer,Taiyuan University of Technology,Taiyuan O3oo24,China)

Abstract: In the wireless sensor network basedonmobile beacon nodes,the path planning problem of mobile beacon nodes has important influenceonpositioning performance.However,theexisting path planning methoddoes nottakefullaccount ofthe distributionofunknown nodes inthe networks,the positioning efficiencyislowandthecost islarge.Therefore,this paper designed apath planning methodof mobile beaconnode: Firstly,determinedthe positionof the virtual beacon nodes, and the number by making full use of sensor nodes distribution;then proposed the grey wolf optimization algorithm of nonlinear dynamicchange convergence factor basedon Gausian decreasing strategy.This algorithm isused in the TSP algorithm to solve the path planing problem,and can obtain the shortest moving path of the mobile beacon node. Simulation results show that the proposed method can efectively improve the locatization coverage and save the localization cost.

Key words: wirelesssensor network;mobile beacon node;virtual beacon node;the graywolf optimization(gwo）；path planning

# 0 引言

无线传感器网络[1]（wireless sensor network,WSN）通常被部署在特定的区域执行特定的任务。节点定位是WSN的关键基础技术之一。通常，信标节点越多，定位覆盖率越高。但是基于WSN中节点能量、体积、通信能力有限，通常随机部署在环境偏僻或者环境恶劣的区域，规模相对较大，以往利用固定信标节点定位的方式对信标节点个数和分布要求很高，容易造成整个网络成本高。移动信标节点可以解决此问题，利用虚拟信标节点代替固定信标节点，通过对移动信标节点合理规划移动路径，降低网络成本，克服了固定信标节点定位的不足，实用性更强。在移动信标节点辅助定位中，信标节点移动路径对节点定位有很大影响。关于静态路径规划的研究有很多，文献[2]提出SCAN、double-SCAN曲线的移动信标节点路径规划方法，信标节点按照预先设定好的曲线移动，double-SCAN路径规划方法有效地解决了SCAN路径规划方法的共线问题。文献[3]提出了一种基于Z型曲线的路径规划方法，在避免了信标节点共线情况下，移动路径较短，能耗低，但是未知节点定位覆盖率不高。上述方法均属于静态路径规划方法，静态路径规划适用于节点均匀分布的网络拓扑中，在节点随机分布的网络拓扑中，适用性不强，节点定位覆盖率比较低。基于上述问题，动态路径规划的研究越来越多，可以减少信标节点数量，降低网络成本，提高效率。文献[4]提出了基于禁忌搜索的动态路径规划方法，移动信标节点在移动过程中与周边节点进行信息通信，动态选取移动方向，但是该方法对于网络不连通的不规则区域来说移动信标节点仅根据未知节点密度或禁忌集无法获取更优的移动方向，所以存在重复搜索移动路径冗长的问题；文献[5]提出了一种利用改进虚拟力的方法决策信标节点的下一步移动方向的路径规划方法，有效克服了未知节点分布不均造成的路径冗长问题，但是对未知节点的定位覆盖率比较低。另外，文献[6]提出了一种基于虚拟点优先级的移动sink路径优化方法，该方法通过网格方法划分虚拟点，sink沿着通过TSP算法求解的最短路径收集传感器节点的数据。如何获取移动信标节点的最短路径，以降低网络能耗，是一个关键问题，考虑到传感器节点的通信范围是以通信半径为半径的圆形区域，问题可以建模为带有圆形邻域的旅行商问题（travelingsalesmanproblem,TSP）。

本文提出一种基于未知节点分布情况的单个移动信标节点的路径规划方法，适用于未知节点分布不均匀的情况，有效解决了移动路径冗长的问题，提高了网络拓扑中未知节点定位覆盖率，且降低了网络成本。具体的实现方法是结合网络中传感器节点的分布情况，选出移动信标节点的停留位置（即虚拟信标节点的位置)，然后移动信标节点沿着基于改进灰狼优化的TSP算法求解的最短移动路径移动。TSP是一个经典的NP完全问题，目前已提出多种改进的群智能算法用于求解 TSP 问题[7\~10]，而且取得了比较好的效果。GWO[11]是一种模拟灰狼群围捕猎物行为启发提出的新型智能优化算法，文献[12]研究了基于GWO求解路径规划问题，经过与其他算法对比基于GWO的TSP算法求解的路径更优。因此本文移动信标节点沿着采用基于改进GWO的TSP算法求解的最短路径移动。

# 1 虚拟信标节点的选取

在基于移动信标节点的无线传感器网络中，移动信标节点的路径规划问题直接影响定位性能，现有的路径规划方法没有充分考虑到网络内未知节点的分布情况，定位覆盖率低且网络成本高。考虑到定位性能和网络成本，本文虚拟信标节点选择的原则：a）在保证定位覆盖率的情况下尽可能减少虚拟信标节点数目，虚拟信标节点数目直接影响路径长度；b)考虑到定位性能，由于传感器节点接收到至少三个不共线信标节点的位置信息才能通过三边测量法进行自身位置估计，因此在虚拟信标节点位置的选择上，避免三个虚拟信标节点共线、三个虚拟信标节点中某两个相距很近以及三个虚拟信标节点位置都相距很近的情况。

设 A、B、C 为三个信标节点，O 为待定位节点，若三个信标节点共线，如图1所示。A、B、C中有两个信标节点相距很近，比如A和B相距很近，如图2所示，这两种情况都容易出现节点O被定位在镜像对称位置O'上；若A、B、C都相距很近，有可能出现O定位失败的情况，如图3所示。dA.B、dA.c dB.c、do.A、do.B、do.c分别是A和B、A和C、B和C、O和A、O和B、O和C之间的距离。

![](images/1dbb544fc3fefade6df2deaaf47d88a5da8bf1bb6368c3ebbd439c6bc24c1b97.jpg)

![](images/cd85b75389e2d80cf8a78d8226e0f597ad46fd90d0c12b52f82de81aedd2bfd7.jpg)  
图1A、B、C在一条直线上 图2 （204号 $d _ { _ { A , B } } \backslash \{ d _ { _ { A , C } } , d _ { _ { A , B } } \backslash \{ d _ { _ { B , C } }$ （204号 Fig. 1 A,B,C are ina straight line Fig. 2 （204 $d _ { _ { A , B } } \backslash \{ d _ { _ { A , C } } , d _ { _ { A , B } } \backslash \{ d _ { _ { B , C } }$ （20

![](images/1a259785598e4f41cd919ede2217878d4d6c2561c3d5cf6e610da038930db62c.jpg)  
图3 $d _ { o , A } \approx d _ { o , B } \approx d _ { o , C } , d _ { { A , B } } \backslash \{ d _ { o , A }$ （204号 Fig.3 （ $d _ { o , A } \approx d _ { o , B } \approx d _ { o , C } , d _ { { A , B } } \backslash \{ d _ { o , A }$

因此本文在虚拟信标节点选取时，设置了参数δ，δ越小，对应的三个虚拟信标节点为顶点构成的三角形越接近等边三角形，等边三角形的定位精度最高，所以选取8值最小的组。

$$
\mu = \frac { d _ { A , B } + d _ { A , C } + d _ { B , C } } { 3 }
$$

$$
\delta = \sqrt { \frac { ( d _ { _ { A , B } } - \mu ) ^ { 2 } + ( d _ { _ { A , C } } - \mu ) ^ { 2 } + ( d _ { _ { B , C } } - \mu ) ^ { 2 } } { 3 } }
$$

传感器节点接收到至少三个不共线信标节点的位置信息才能通过三边测量法进行自身位置估计。如果传感器节点落在以三个不共线信标节点为圆心，通信半径为半径的圆的交集内，可以实现自身位置估计。本文以此思想将传感器节点分组。

虚拟信标节点选取步骤如下：

a)在无线传感器网络中随机部署 $N$ 个传感器节点，给传感器节点编号，编号取值为1，2，…， $N$ 。无线传感器网络的通信半径为 $R$ ，通过传感器节点之间相互通信，将信号强度值用RSSI测距方法转换成距离值，建立一个 $N ^ { * } N$ 的距离求值矩阵 $D$ 。

$$
D ( i , j ) = \left\{ \begin{array} { l l } { d i s t , \frac { \partial { + } } { \partial { \big | } } } \\ { 0 , i = j } \\ { - 1 , \frac { \partial { + } } { \partial { \big | } } \langle \frac { \partial { + } } { \partial { \big | } } } \end{array} \right.
$$

b)每三个不共线的传感器节点为一组，一共有 $K$ 组，给小组编号1组，2组，…， $K$ 组，建立矩阵 $G$ ， $G ( i , j )$ 中 $i$ 是行序号表示组号， $j$ 的取值是1，2，3，对应列存储 $i$ 组包含的三个传感器节点的编号。

c)判断 $G$ 矩阵中每个小组是否有意义。这里的有意义定义为：以 $G$ 矩阵每行包含的以三个传感器节点为圆心，通信半径 $R$ 为半径的三个圆的公共区域面积内存在可以相互通信的其他传感器节点。建立 $K ^ { * } N$ 的矩阵表 $s$ ，记录与每组的三个传感器节点都可以相互通信的传感器节点， $i$ 表示小组序号， $j$ 表示传感器节点的序号。

[1j节点与第组包含的三个传感器节点都可以相互通信S(i,j)=0,j节点与第组包含的三个传感器节点至少有一个不可以相互通信

d)计算 $s$ 矩阵每行的和，记录在 $K ^ { * } 1$ 维列向量 $L V$ 中，任意一行的和 $L V \left( i \right)$ 表示：和第 $i$ 组包含的三个传感器节点都能互相通信的传感器节点的数目。

e)根据S矩阵每行和由大到小的顺序更新 $s$ 矩阵的行的排列，同时更新 $G$ 矩阵行的排列， $G$ 矩阵行的序号排列和 $s$ 矩阵的行的序号排列始终是一一对应的，即小组编号。

f)按照如下规则更新 $\textit { S } ( i , \ j )$ ，按列查找元素1， $j$ 从1到 $N$ ，从 $j$ 列的第一个元素开始寻找，如果 $\textit { S } ( i , \ j ) = 1$ ，则令 $s$ 的第 $j$ 列从 $i$ 行开始到 $K$ 行的元素全部更新为0。

g)再次计算 $s$ 矩阵每行的和，记录在 $L V$ 中，如果 $L V \left( i \right)$ $\scriptstyle = 0$ ，更新 $G$ (i，j) $\scriptstyle = 0$ ， $\scriptstyle \mathrm { j = 1 } , 2 , 3$ ，将第 $i$ 组视为冗余小组。

h)按行执行，从第 $i$ 行开始，如果 $0 { < } L V ( i ) { < } 3$ ，第 $i$ 组的三个传感器节点确定为虚拟信标节点；如果 $L V \ ( i ) \ \geq 3$ ，将矩阵 $s$ 第 $i$ 行所有取值为1的元素的列序号分组即传感器节点分组，三个不共线的为一组，如果不存在满足条件的组，那么第 $i$ 组的三个传感器节点确定为虚拟信标节点；如果存在满足条件的组，那么根据式(1)和(2)计算每组的δ值，选取8值最小的组所包含的三个传感器节点为虚拟信标节点。

# 2 基于改进灰狼优化的TSP求解最短移动路径

# 2.1灰狼优化算法的改进

灰狼优化算法是一种仿生群体智能优化算法，是通过模仿自然界灰狼群体的社会领导层级机制和捕食行为提出的。为了从数学上对灰狼的社会等级进行建模，在设计GWO时，将最佳的解决方案视为 $\mathfrak { a }$ ，因此，第二个和第三个最佳解决方案被分别视为 $\beta$ 和8，剩下的候选方案视为 $\boldsymbol { \mathbf { \rho } } _ { \infty }$ ，在GWO算法中狩猎(优化)是由 $\mathfrak { a }$ 、 $\beta$ 和δ引导的，@跟随其他三种狼。

狩猎过程的第一步是灰狼群包围猎物。其数学表达为

$$
 { \boldsymbol { D } }  { = }  { \vert \boldsymbol { C } \cdot \boldsymbol { X } _ { P } ( t ) - \boldsymbol { X } ( t ) \vert }
$$

$$
\begin{array} { r } { X ( t + 1 ) = X _ { { \scriptscriptstyle P } } ( t ) - \pmb { A } \cdot \pmb { D } } \end{array}
$$

其中： $X _ { \mathrm { P } }$ 是猎物的位置， $X$ 是灰狼的位置。 $\mathbf { \Phi } _ { t }$ 表示当前迭代的次数， $t _ { \mathrm { m a x } }$ 为最大迭代次数。 $D$ 表示包围步长。 $A$ 和 $c$ 为系数向量。

$$
A { = } 2 a { \cdot } r _ { 1 } - a { , } C { = } 2 \cdot r _ { 2 }
$$

收敛因子 $\textbf { \em a }$ 随着迭代次数从2线性递减到 $0 \circ \ r _ { I }$ 和 $r _ { 2 }$ 是[0,1]的随机向量。

在猎捕阶段，其他灰狼个体根据 $a , \beta$ 和8的位置来更新个体位置，数学表达为

$$
\left\{ \begin{array} { l l } { \displaystyle D _ { \alpha } = \mid C _ { 1 } \cdot X _ { \alpha } ( t ) - X ( t ) \mid } \\ { \displaystyle D _ { \beta } = \mid C _ { 2 } \cdot X _ { \beta } ( t ) - X ( t ) \mid } \\ { \displaystyle D _ { \delta } = \mid C _ { 3 } \cdot X _ { \delta } ( t ) - X ( t ) \mid } \end{array} \right.
$$

$$
\left\{ \begin{array} { l l } { X _ { 1 } = X _ { \alpha } ( t ) - A _ { 1 } \cdot D _ { \alpha } } \\ { X _ { 2 } = X _ { \beta } ( t ) - A _ { 2 } \cdot D _ { \beta } } \\ { X _ { 3 } = X _ { \delta } ( t ) - A _ { 3 } \cdot D _ { \delta } } \end{array} \right.
$$

$$
X ( t + 1 ) = \frac { X _ { 1 } + X _ { 2 } + X _ { 3 } } { 3 }
$$

最后，攻击阶段，在此阶段根据 $A$ 和 $c$ 的值来控制探索和开发过程。在迭代过程中，收敛因子 $\pmb { a }$ 是逐渐减小的， $A$ 的波动范围随着 $\textbf { \em a }$ 的减小而减小， $A$ 是[-a，a]内的一个随机值，当 $| A | \leqslant 1$ 时，灰狼群向着猎物攻击，以实现局部搜索，当A>1，灰狼群体远离猎物，以加强算法的探索能力实现全局搜索。从式（7）可以看出 $c$ 在整个迭代过程中都是一个随机量， $c$ 的随机性是为了随机的强化或弱化猎物在定义的距离方程中的影响，并且在最后的迭代过程中一直加强搜索，可以避免陷入局部最优。

本文对灰狼优化算法的改进如下：

针对收敛因子进行改进。灰狼优化算法在搜索过程中是非线性变化的，收敛因子 $\mathbf { \Delta } _ { a }$ 随迭代次数线性递减策略不符合实际优化搜索过程。

文献[13]提出了基于余弦函数（记为cosGWO）和二次函数(记为2GWO)的非线性动态变化收敛因子更新方法，更新公式遵循式（11）（12)，仿真结果表明其优于基于正弦函数、正切函数和对数函数的更新方法。

$$
a _ { t } = ( a _ { i n i t i a l } - a _ { f i n a l } ) \times \cos [ \frac { t } { t _ { \operatorname* { m a x } } } ]
$$

$$
a _ { t } = a _ { i n i t i a l } - ( a _ { i n i t i a l } - a _ { f i n a l } ) \times ( \frac { t } { t _ { \operatorname* { m a x } } } ) ^ { 2 }
$$

其中 $: a _ { i n i t i a l }$ 和 $a _ { f i n a l }$ 分别是 $\mathbf { \Delta } _ { a }$ 的初始值和终值， $t$ 为当前迭代次数， $t _ { m a x }$ 为最大迭代次数。

文献[14]中提出了一种基于指数函数（记为eGWO）的非线性动态变化收敛因子更新公式：

$$
a _ { t } = a _ { i n i t i a l } - \exp ( - \lambda \times \frac { t } { t _ { \operatorname* { m a x } } } ) ^ { 3 }
$$

其中 $: a _ { i n i t i a l }$ 和 $a _ { f i n a l }$ 分别是 $\mathbf { \Delta } _ { a }$ 的初始值和终值， $t$ 为当前迭代次数， $t _ { m a x }$ 为最大迭代次数。 $\lambda$ 是调节系数，参考文献中取值为25。

本文提出一种基于高斯递减策略的非线性动态变化收敛因子更新公式为

$$
a _ { t } = ( a _ { i n i t i a l } - a _ { f i n a l } ) \times \exp [ - \frac { t ^ { 2 } } { \left( e \times t _ { \mathrm { m a x } } \right) ^ { 2 } } ] + a _ { f i n a l }
$$

其中： $a _ { i n i t i a l }$ 和 $a _ { f i n a l }$ 分别是 $a$ 的初始值和终值。当 $\mathbf { a } _ { t - \mathbf { a } _ { f i n a l } } < \mathbf { T }$ 时，$\scriptstyle \mathbf { a } _ { t } = \mathbf { a } _ { f i n a l }$ ， $\mathrm { ~ T ~ }$ 为a的停止阈值， $\mathrm { T } { = } 0 . 0 0 1$ ； $\boldsymbol { \mathscr { e } }$ 是扩展常数，本文取值为 $0 . 6 \mathrm { \Omega _ { \circ } }$ ，前期具有较高的全局搜索能力，之后 $\mathbf { \Delta } _ { a }$ 迅速减小进入局部搜索，加快收敛速度，后期有较高的局部搜索能力，以

提高收敛精度。为了验证本文改进收敛因子的有效性，在实验   
仿真部分进行了对比，本文中 $a _ { i n i t i a l } { = } 2$ ，afinal=0。 算法的伪代码如下： Initialize iteration count (t) Initialize the grey wolf population $X _ { i } ( \mathrm { i } = 1 , ~ 2 , ~ \cdots , ~ N )$ Initialize $\mathbf { \Delta } _ { \pmb { a } }$ ， $A$ ，and $c$ ： calculate the fitnessof each search agent $\mathbf { X } _ { a } = \mathbf { \Phi }$ the best search agent $\mathrm { X } _ { \beta } =$ the second best search agent $\mathbf { \nabla } \mathbf { X } _ { \delta } = \mathbf { \nabla }$ the third best search agent while( $\tau \leq \mathrm { m a x }$ number of iterations) for each search agent calculate convergence factor $\pmb { a }$ by equation(16) update the position of the $\boldsymbol { \omega }$ by equation(7)\~(10) and   
equation (14) end for update ${ \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf { } } { \mathbf } { \mathbf { } } { \mathbf { } } { \mathbf } { \mathbf { } } { \mathbf } { \mathbf { } } { \mathbf } { \mathbf { } } { \mathbf } { \mathbf } { } { \mathbf } { \mathbf } { } { \mathbf } { \mathbf } { } { \mathbf } { } \mathbf { } \mathbf { } { \mathbf } { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf { } \mathbf \mathbf { } \mathbf { } \mathbf { \mathbf } \mathbf { } \mathbf { \mathbf } \mathbf { \mathbf } { \mathbf } { \mathbf \mathbf } { \mathbf \mathbf } { \mathbf }  \mathbf \mathbf { } \mathbf \mathbf { } \mathbf \mathbf { } \mathbf { } \mathbf \mathbf { } \mathbf { } \mathbf \mathbf { \mathbf } { \mathbf } \mathbf { \mathbf \mathbf } { \mathbf \mathbf \mathbf } { \mathbf } { \mathbf \mathbf }  \mathbf \mathbf \mathbf { } \mathbf { \mathbf } \mathbf { } \mathbf \mathbf { \mathbf \mathbf } \mathbf { } \mathbf { \mathbf } { \mathbf \mathbf \mathbf \mathbf { } \mathbf \mathbf }  \mathbf \mathbf \mathbf { } \mathbf \mathbf { } \mathbf \mathbf \mathbf { } \mathbf \mathbf { \mathbf \mathbf } \mathbf { \mathbf }  \mathbf \mathbf \mathbf \mathbf { } \mathbf \mathbf { \mathbf } \mathbf$ ，and $c$ calculate the fitness of all search agents update $X _ { \mathfrak { a } }$ ， $X _ { \beta }$ and $X _ { \delta }$ （204号 $t = t + 1$ end while return $X _ { \mathfrak { a } }$

# 2.2 适应度函数设计

基于改进灰狼的TSP算法求解最优移动路径，解的评价方法一般是根据目标函数设计适应度函数，本文中移动信标节点移动路径越短，网络能耗越低，可延长网络生命周期，所以本文目标函数是移动路径最短，根据灰狼个体位置的排列顺序，计算个体间的总距离（即路径长度)，本文将路径长度的倒数设为该解的适应度值fitness，适应度值越大，个体就越优。

# 2.3基于改进GWO算法的路径规划流程

a）初始化种群，灰狼个体编码为1到 $\mathfrak { n }$ 的随机排列，n即虚拟信标节点数，N为种群大小； $t$ 为当前迭代次数，tmax为最大迭代次数；控制因子 $\textbf { \em a }$ 初始值为2、终止值为0。初始化， $\scriptstyle t = 0$ 。

b)计算每个个体的适应度函数值fitness。将个体按适应函数值从大到小排序，排在第一位的设为 $\mathbf {  { a } }$ ，排在第二位的设为β，排在第三位的设为δ，其余的为 $\boldsymbol { \mathbf { \rho } } _ { \infty }$ 。

c)搜索更新，即灰狼的包围、猎捕、攻击。根据式(7)\~(10)(14)更新个体位置。

d)计算适应度函数值，更新 $\mathfrak { a }$ 、β、δ个体，令 $\scriptstyle t = t + 1$ 。

e)若t>tmax，tmax为最大迭代次数，停止搜索，否则转至步骤b)。

# 3 仿真实验与算法分析

为了验证算法的有效性和合理性，本文用MATLAB2016(b)进行了仿真实验。仿真条件，边长为 $1 0 0 \mathrm { m }$ 的正方形区域内随机分布100个传感器节点，信标节点通信半径为R，算法中种群大小为100，最大迭代次数为1000，使用MATLAB2016(b)进行仿真分析。图5\~7分别是本文算法在$\scriptstyle \mathrm { R } = 3 0 \mathrm { ~ m ~ }$ 、 $\scriptstyle \mathrm { R = 4 0 ~ m }$ 、 $\scriptstyle \mathrm { R = 5 0 ~ m }$ 时的移动信标路径规划图，定位覆盖率为1。图8是将本文信标节点停留位置选择方法与传统的SCAN算法、DOUBLESCAN算法以及文献[15]中提出的SLMAT算法在不同网络拓扑长度下进行对比，SLMAT算法是LMAT算法[16]和SCAN算法的结合，虚拟信标节点的停留位置是等边三角形的三个顶点位置，此等边三角形的边长是通信半径的 $\sqrt { 3 }$ 倍，虚拟信标节点的移动路径类似于SCAN算法。仿真图是在R为40米时，不同网络拓扑边界长度下的虚拟信标节点数对比图。图9是将本文提出的移动信标节点路径规划方法与传统的SCAN算法、DOUBLE_SCAN算法以及SLMAT算法在不同R下进行对比的定位覆盖率对比仿真图；图10是在边长为100米的正方形区域内分别随机分布不同数目的传感器节点，R取值为30米时，定位覆盖率对比仿真图。图11是在边长为100米的正方形区域内随机分布100个传感器节点，不同R下的移动路径长度对比图。图12是在边长为100米的正方形区域内随机分布100个传感器节点，R取值为40米时，不同网络拓扑边界长度下的移动路径长度对比图。

![](images/ebf0fe1bb6294c2824fe65aa9a7b83e87b88f08dcb7287981137c841f478ccd4.jpg)  
图4基于改进GWO算法的路径规划流程图

![](images/05255ffed331acbcb5ae258968ce8f1dea1eebd8c00b033ddfdcf43c28715c0f.jpg)  
Fig.4Path planning flow chart based on improved GWO algorithr

![](images/0c6b71be7c5c516862aacc893b0c2919c19d626b8f23257daaeeeb346de55d18.jpg)  
图5 $R { = } 3 0$ 米，定位覆盖率 $^ { = 1 }$ ，路径规划图  
Fig.6 $\scriptstyle { R = 4 0 }$ Meters,location coverage ${ \bf \mu } = 1 { \bf \sigma }$ ,path planning   
图6 $R { = } 4 0$ 米，定位覆盖率 $^ { = 1 }$ ，路径规划图

![](images/3e68dfc8091b60f0bf814d81b2ac653c268f7d6f48834b0bbf864e3feacaceb2.jpg)  
图7 $R { = } 5 0$ 米，定位覆盖率 $_ { - 1 }$ ，路径规划图

在图5\~7中实心圆圈代表虚拟信标节点的位置，空心圆圈代表未知节点的位置。比较图5\~7可以看出，通信半径增大，虚拟信标节点数减少，移动路径长度减小。图11可验证了这一结论。本文提出的移动信标节点路径规划方法可以达到良好的定位覆盖率且有效解决了冗余移动。

从图8可以看出本文算法随网络拓扑边界长度的改变虚拟信标节点数变化不大，出现数目减少的情况是由于本文算法的虚拟信标节点数是由网络拓扑中未知节点的分布情况决定的，网络拓扑区域变大，通信半径不变时覆盖率降低了，相应的得到的虚拟信标节点数也会减少。SCAN、DOUBLE_SCAN算法以及SLMAT算法虚拟信标节点数是由网络拓扑边界长度和通信半径决定的，仿真结果表明网络边界长度增大会使虚拟信标节点数大大增加。而本文算法主要取决于网络中未知节点分布情况，受网络拓扑边界长度影响相对较小，本文算法适用范围广，实用性更强。

![](images/b180b0976fb6b4adb3e337ddf7a49f79e1fca46c1321f0632f09df8ce7f401cf.jpg)  
Fig.7 $R { = } 5 0$ Meters,location coverage ${ \bf \mu } = 1 { \bf \rho }$ ,path planning   
图8不同网络拓扑边界长度的虚拟信标节点数对比图

![](images/baf981d71f4c0d56d37420810502ba1e567095b8d4ea4be1463505eb29fd8b28.jpg)  
Fig.30Meters,location coverage ${ \bf \mu } = 1 { \bf \sigma }$ ,path planning   
Fig.8Comparison of virtual beacon nodes with different network   
图9不同通信半径的定位覆盖率对比图  
Fig.9Comparison of location coverage ratio with different communication radius

由图9可以看出，未知节点定位覆盖率随着通信半径的增大而增大，在通信半径小于 $4 0 \mathrm { ~ m ~ }$ 的时候，本文算法相比SCAN、DOUBLE_SCAN算法以及SLMAT算法定位覆盖率要高很多。在通信半径大于40米的时候，本文算法覆盖率几乎达到1，SLMAT算法定位覆盖率达到 $9 5 \%$ 以上，SCAN、DOUBLE_SCAN算法定位覆盖率均达到 $90 \%$ 以上。结合实际情况，信标节点的通信半径并不会很大，所以本文算法更具可用性，且性能更好。

![](images/926f0902509e5fa9ee33b968b62db31d9b0b1c0af9a21b75ead50a8a7c1a37ba.jpg)  
图10不同传感器节点个数的定位覆盖率对比图

of sensor nodes

由图10可以看出在网络拓扑内传感器节点数不同的情况下，本文算法的定位覆盖率同样高于SCAN、DOUBLE_SCAN、SLMAT算法。由此，可以看出本文提出的基于移动信标节点的路径规划方法具有良好的定位覆盖率。

![](images/56e9369b5995cd1fe6037d5a2d302df32cabe8fc5a2325d4e69c6945ed2b33ed.jpg)  
Fig.1O Comparison of location coverage ratio with different number   
图11不同通信半径的移动路径长度对比图

![](images/1f5e4eb57de74dd20fdc6f7479c06ee6ba696cb98e9c9b0d9f5a34ce6a2e6c82.jpg)  
Fig.11Comparison of length of the moving path with different communication radius   
图12不同网络拓扑边界长度的移动路径长度对比图  
Fig.12Comparison of length of the moving path with different network topological boundaries 从图11和12可以看出使用本文基于改进灰狼优化TSP

求解的路径长度不论是在不同信标节点通信半径的条件下还是在不同网络拓扑边界长度条件下，相比文献[14]提出的基于二次函数和余弦函数以及文献[15]提出的基于指数函数的非线性动态变化收敛因子更新方法的灰狼优化算法求解的路径长度更短，即本文提出的基于高斯递减策略的非线性动态变化收敛因子改进灰狼优化算法精度更高，寻优能力更强，验证了本文对灰狼优化算法改进的有效性。移动信标节点沿着基于本文改进灰狼的TSP求解的最短路径移动，有效节省了网络能耗，延长了网络生命周期。

本文提出的移动信标节点路径规划方法在同等条件下比SCAN、DOUBLE_SCAN、SLMAT算法都有更短的移动路径长度，SCAN、DOUBLE_SCAN、SLMAT算法移动路径长度是由网络拓扑边界长度和通信半径决定的，在通信半径一定的情况下，移动路径长度随着网络拓扑边界长度的增加而增加，本文算法网络拓扑边界长度对移动路径长度的影响相对较小，更具实用性。

# 4 结束语

本文提出的移动信标节点路径规划方法，是基于网络中未知节点的分布情况选取移动信标节点停留位置，符合无线传感网络动态拓扑的特点，灵活性强。本文算法减少了信标节点的停留位置，移动信标节点沿着基于收敛因子非线性动态变化的灰狼的TSP算法求解的最短移动路径移动，节省了信标节点的能量消耗，延长了网络的生命周期，提高了系统可用性，降低了网络成本。该算法还提高了无线传感网络的定位覆盖率，通过仿真验证了算法的有效性。本文算法信标节点在覆盖待定位节点时信标节点的位置更接近于正三角形，理论上可以提高定位精度，但本文侧重路径规划，对定位技术研究不足，设计高定位精度的定位算法是下一步的主要工作。

# 参考文献：

[1]Suja GJ,Jose S,Raman RB,et al.Performance analysis of big data gathering in wireless sensor network using an EM based clustering scheme [C]//Proc of the 5th International Conference on Advances in Computing and Communications.2015:109-113.   
[2]Koutsonikolas D,Das SM,Hu YC.Path planning of mobile landmarks forlocalizationinwirelesssensornetworks[J].Computer Communications,2007,30(13): 2577-26592.   
[3]Rezazadeh J,Moradi M,Ismail A S,et al.Superior path planning mechanism for mobile beacon-assisted localization in wireless sensor networks [J].IEEE Sensors Journal, 2014,14(9): 3052-3064.   
[4]殷文正，姜卫东，陶金．基于禁忌搜索算法的 AUV动态路径规划策 略[J]．南京大学学报：自然科学版，2017，53(1)：144-150.（Yin Wenzheng, Jiang Weidong,Tao Jin. Strategy of dynamic path planning based on tabu search algorithm for AUV [J] Journal of Nanjing University: Natural Sciences,2017,53(1):144-150.)   
[5]Geng Feng，Xue Shengjun.Mobile beacon node path scheme in arbitraryregionforwirelesssensornetworks[C]//Procof International Conference on Electronic and Mechanical Engineering and Information Technology.2011:12-14.   
[6]张希伟，沈琳，蒋益峰．移动协助传感器网络中 sink 的路径优化策 略[J].通信学报，2013,34(2):85-93.(Zhang Xiwei,Shen Lin, Jiang Yifeng.Optimizingpath selection ofmobile Sink nodesin mobility-assistant WSN [J]. Journal on Communications,2O13,34(2): 85-93.)   
[7]Elloumi W,Abed HE,Abraham A,et al.A comparative study of the improvementof performance using a PSO modified by ACO applied to TSP[J].Applied Soft Computing,2014,25:234-241.   
[8]王克甫，薛鹏，黄全振，等．求解旅行商问题的改进果蝇算法 [J]. 计算机工程与设计，2014，35(8):2789-2792,2821．(Wang Kefu, XuePeng，Huang Quanzhen，et al. Improved fruit fly optimization algorithm for TSP problems [J].Computer Engineering and Design 2014,35(8):2789-2792,2821.)   
[9]王沛栋，唐功友，杨熙鑫，等．一种求解旅行商问题的改进蚁群算法 [J]．中国海洋大学学报：自然科学版，2013，43(1):93-97.（Wang Peidong,Tang Gongyou,Yang Xixin,et al.An improved ant conony algorithm for traveling salesman problems [J].Periodical of Ocean University of China: Natural Sciences,2013,43(1):93-97.)   
[10]马继辉，余明捷，陈鑫杰，等．基于Hama 并行蚁群算法模型及TSP 应用研究[J].交通运输系统工程与信息，2016，16(3):168-173，180. (Ma Jihui,Xu Mingjie,Chen Xinjie,et al.Hama-based parallel ant colony optimization algorithm mode and TSP applied research [J]. Journal of Transportation Systems Engineering and Information Technol0gy,2016,16(3):168-173,180.)   
[11]Mirjalili S,MirjaliliSM,LewisA.Greywolf optimizer[J].Advances in Engineering Software,2014,69:46-61.   
[12] Zhang Sen,Zhou Yongquan,Li Zhiming,et al.Grey wolf optimizer for unmanned combat aerial vehicle path planning [J].Advances in Engineering Software,2016,99(C):121-136.   
[13]魏政磊，赵辉，李牧懂，等.控制参数值非线性调整策略的灰狼优化 算法[J].空军工程大学学报：自然科学版，2016,17(3)：68-72.（Wei Zhenglei,Zhao Hui.Li Mudong，et al.A grey wolf optimization algorithm based on nonlinear adjustment strategy of control parameter [J].Journal of Air Force Engineering University:Natural Science Edition,2016,17(3):68-72.)   
[14]罗佳，唐斌．基于收敛因子非线性动态变化的灰狼优化算法[J]．中 国科技论文,2016,11(17):1991-1997.(Luo Jia,Tang Bin.Grey wolf optimization algorithm based on nonlinear convergence factor dynamic changing[J].China Sciencepaper, 2016,1(17): 1991-1997.)   
[15] HanGuangjie，YangXuan，LiuLi，etal.Adisaster management-oriented path planning for mobile anchor node-based localization in wireless sensor networks [J]. IEEE Trans on Emerging Topics in Computing,2017:1-1.   
[16]Han Guangjie,Yang Xuan,Liu Li,et al.Path planning usinga mobile anchor node based on trilateration in wireless sensor networks [J]. Wireless Communications and Mobile Computing,2013，13(14): 1324-1336.