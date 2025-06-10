# 考虑基站选址的UAV交通巡视路径超级时空网络模型

王冬冬，何胜学†，路扬(上海理工大学 管理学院，上海 200093)

摘要：针对考虑基站选址的无人机交通巡视路径优化问题，提出一个超级网络与时空网络相结合的方法，并通过该方法建立模型。通过在时空网络添加虚拟起降点，与全部时刻的备选基站相连接构成超级时空网络，可将考虑基站选址的路径规划转换为一个单纯的多UAV路径规划问题。与不考虑基站选址的路径规划相比，考虑基站选址能够使最大单机飞行时间和总飞行时间分别减少 $5 . 7 1 \%$ 和 $1 1 . 5 9 \%$ 。数值分析表明，基站选址和交通巡视路径规划整合可有效减少UVA的巡视成本。

关键词：城市交通；基站选址；超级时空网络；无人机；路径规划 中图分类号： $\mathrm { U } 4 9 1 . 1 \substack { + 2 }$ doi: 10.3969/j.issn.1001-3695.2018.03.0163

# UAV traffic patrolling path planning super-space-time network model considering base stationlocation problem

Wang Dongdong, He Shengxue†, Lu Yang (SchoolofManagement,UniversityofShanghai forScience&Technology,Shanghai 20oo93,China

Abstract:Basedon the optimization problem of siteselection and optimal path planing of UAVduring traffc network inspection,this paper proposeda methodofcombiningsuper network with space-time network,andbuiltamodelthroughthis method.This paper constructeda super-space-time networkbyading virtual take-of andlanding points inthespace-time network,andrequires thevitualtakeoffandlandingpointtoeconectedwiththealterativeasestationsataltims.Inths way,thepath planning considering the site selectionofthebase station was transformed intoasimple multi-UAVpath planning problem.Compared withthepath planning withoutconsideringthe siteselectionofthebase station,considering thebase station site selection could reduce the maximum stand-alone flight time and total flight time by $5 . 7 1 \%$ and $1 1 . 5 9 \%$ ，respectively. Numericalanalysis shows thate integrationofbase stationlocationand trafic patrolrouteplanningcan efectivelyreduce the UVA patrol costs.

Key words: urban traffic; base station location; super-space-time network; UAV; path planning

# 0 引言

随着无人机技术的快速发展，无人机已经广泛应用于电力巡检、植物保护、灾难救援和路网巡视[1-2]。由于路网规模一般都比较大，路网巡视一般需采用多基站的多机巡视方式。受到单机续航时间和巡视任务特征约束的限制，有效的无人机路网巡视必须考虑起降基站位置的选择和具体路线的规划。本文将针对无人机起降基站选址和交通路网巡视路径规划的整合优化问题展开研究。

国内外对无人机在路径规划方面的研究主要涉及确定最佳的无人机数量[3]、尽可能多的巡视目标点[45]及求解算法研究[6]等。刘晓锋等人建立了一个多目标优化模型，在总飞行距离最短的前提下，分别考虑了使用最少数量的无人机巡视所有目标和无人机数量不足的情况下尽可能多的巡视目标，并通过一种进化算法求解路径规划问题5。Niu 等人提出使用无人机作为一种移动型交通检测器对高速公路进行巡视，在最短的时间内尽可能多的巡视未布设固定型交通检测器路段。刘晓锋等人以无人机数量最少、总飞行距离最短为目标对未布设固定型交通检测器的路段进行巡视，要求每架无人机必须先后穿过所经过路段两端的节点，把对路段的巡视转化为带有一定约束的旅行商问题[8]。上述研究均仅在满足巡视任务的前提下，对无人机的巡视路径进行优化。这些研究均假设无人机起降基站位置给定，而忽略了基站位置对巡视路径的影响。在复杂的路网结构中，除了给定的系列巡视任务会影响巡视路径，基站位置的选择也会对最终的巡视路线造成影响。因此，有必要将基站选址和巡视路径规划问题加以整合，从而同时确定最佳的基站位置和对应巡视路径，使总的飞行成本最小，巡视效率最高。

当前针对无人机基站选址的研究很少。本文通过超级网络添加一个虚拟起点和一个虚拟终点，与实际路网中的所有备选基站相连接。所有的无人机在巡视开始时全部从虚拟起点起飞，自由选择发射基站进入实际路网，完成巡视任务后自由选择降落的基站离开实际路网，最后到达虚拟终点，结束飞行。通过该思想不但可以确定最优的巡视路径，而且能够找出最佳的基站位置，同时还将多起终点的多机巡视问题，转化为了单起讫点的多机巡视问题，降低了问题的求解难度。

利用添加虚拟节点构建超级网络，从而实现选址与路线规划整合优化的思想最早被何胜学等人应用于无预警的紧急公交疏散研究之中[9]。随后何胜学等人又利用该思想分析了考虑上客点选择的公交疏散问题[10]，而陈经纬等人利用该思想对无人车运行计划制定问题进行了研究[11]。由于本文考虑的巡视次数和巡视时间间隔约束问题需要使用时空网络的方法建模，而为了综合考虑基站选址，需要将超级网络与上述时空网络加以结合，从一个新的视角对该问题进行研究。本文拟通过构建超级时空网络，建立考虑基站选址的多无人机路网巡视路径优化模型，并利用超级时空网络能够在巡视网络中自由选择起飞和降落备选基站的理论特性，将基站选址和巡视路径规划整合转换为单纯的多无人机巡视路线规划问题。

# 1 问题描述

为了较好地表达本文考虑的时间约束问题，将动态的路径规划转化为静态路径规划，实现对无人机动态时空轨迹的细致刻画，这里引入时空网络作为研究框架，从时间和空间两个方面对无人机在路网上的动态巡视进行描述。通过在原有二维原始路网基础上增加纵向时间轴，将无人机的动态飞行轨迹静态展现在时间轴上，实现在时间的维度对无人机飞行轨迹的细致刻画。首先根据路网中的路段行程时间确定单位时长，确保所有路段的行程时间都是单位时长的整数倍。然后根据划分的时间段对原始路网节点进行复制，并依据原始路段添加对应时空路段，完成原始路网到时空路网的转换。

为整合基站选址问题，在原网络中添加虚拟起降点，并与对应备选实际起降基站相连接。假设无人机在巡视开始时全部从虚拟起点起飞，完成巡视任务后，均在虚拟终点降落。上述方法，即通过添加虚拟起降点构成超级网络，可以有效地将基站选址与多机巡视路径规划问题转换为一个单起降点对的多无人机路线规划问题。

这里通过在时空网络添加虚拟起降点，与时空路网中全部时刻的所有备选基站相连接，组成超级时空网络。从新的视角巧妙地将综合考虑基站选址的交通巡视路径规划问题整合转化为一个单纯的有固定起终点的多UAV交通巡视路径规划问题，有效降低问题的求解难度。图1给出了一个简单的超级时空网络模型。图1的原始路网有、 $j$ 、 $k$ 三个节点，i为起点， $k$ 为终点，对应的路段行程时间标示在路段上方。设道路均为双向道路，且无人机飞行速度固定。首先根据路段行程时间确定单位时长，然后根据需要将原始路网复制5份。左侧纵轴上分别标示着原始路网在时空网络中对应的时刻。然后添加一个虚拟起点和一个虚拟终点。为保证虚拟起终点的建立不会增加无人机的飞行时间，规定虚拟起终点到对应实际起降基站的行程时间为0。

以图1为例，可对无人机在超级时空路网中的一种可能运行轨迹进行如下描述。在 $t = 0$ 时刻，无人机从虚拟起点出发进入节点 $i$ ，这里用(i,0)表示；在 $t = 1$ 时刻到达节点 $j$ ，表示为(j,1)；在 $t = 2$ 时刻返回节点 $i$ ，用(i,2)表示，然后经节点 $j$ 在$t = 4$ 时刻到达节点 $k$ ，表示为(k,4)，最后到达虚拟终点。其中从(i,0)到(j，1)的过程用 $( i , 0 , j )$ 表示，代表无人机在 $t = 0$ 时刻开始从节点 $i$ 到节点 $j$ 的巡视。

![](images/edd248a18a85155604b336c1fcf0cb70b0c4dabdf6cbef456711e139dc1f70a1.jpg)  
图1简单的超级时空网络图

# 2 模型构建

# 2.1参变量说明

从图1可以看到，时空路网比二维的简单原始路网多了一个纵向时间坐标，因此原本在简单路网中道路节点、路段的表示方法，在这里不再适用，需要在原来的基础上增加一个时间维度。例如：原始路网中的道路节点 $n$ ，在时空路网中用 $( n , t )$ 表示，代表在时刻 $\textit { t }$ 的节点 $n$ 。同时在原始路网中的路段 $( m , n )$ ，在时空路网中用 $( m , t , n )$ 表示，代表在 $\textit { \textbf { t } }$ 时刻开始进行从 $m$ 点沿路段 $( m , n )$ 到 $n$ 点的巡视。其中，为了区分无人机是否在时刻 $t$ 进行了从 $m$ 点到 $n$ 点的巡视，我们在这里引入了一个0-1变量$X _ { m , t , n } ^ { p }$ 。当无人机 $\boldsymbol { p }$ 在 $\textit { t }$ 时刻开始进行从 $m$ 点到 $n$ 点的巡视时$X _ { m , t , n } ^ { p } = 1$ ，否则 $X _ { m , t , n } ^ { p } = 0$ 。其它变量含义如下：

$N$ 或 $\textbf { \em M }$ 表示原始路网中所有节点的集合，有 $n \in N$ ：

$\scriptstyle P$ 表示所有无人机的集合，有 $p \in { \pmb P }$ ：  
$_ { T }$ 表示时空路网中根据单位时长划分时间点的集合，时间点分别对应时空网络中时间坐标上的时刻，有 $t \in T$ ，其中时间点的最大值用 $n _ { \scriptscriptstyle T }$ 表示；  
(N,T）表示时空路网中所有节点的集合，是一个由节点和时间组成的二维集合，集合中元素的表达方式为 $( n , t )$ ·  
$( M , N )$ 表示原始路网中所有路段的集合，有 $( m , n ) \in ( M , N )$ ：$( { \bar { M } } , { \bar { N } } )$ 表示原始路网中需要被多次巡视的路段的集合，有$( { \bar { M } } , { \bar { N } } ) \subset ( M , N )$ ；  
$( M , T , N )$ 表示时空路网中所有路段在任意时刻的集合，是一个由路段和时间组成的三维集合，集合中元素的表达方式为$( m , t , n )$ ;  
$t _ { { \scriptscriptstyle m } , n }$ 表示原始路网中路段 $( m , n )$ 的路段行程时间， $t _ { { \scriptscriptstyle m } , n } = t _ { { \scriptscriptstyle n } , m }$ ；$N ^ { o }$ 表示原始路网中无人机备选发射基站的集合，其中 $\boldsymbol { n } ^ { o } \in \boldsymbol { N } ^ { o }$ ：$N ^ { p }$ 表示原始路网中无人机备选降落基站的集合，其中$\boldsymbol { n } ^ { d } \in \boldsymbol { N } ^ { D }$ ;  
$\textit { \textbf { o . } } \boldsymbol { { p } }$ 分别表示虚拟起点和虚拟终点；  
$\Delta t$ 表示某路段被多次巡视时的最小巡视时间间隔；  
$N _ { _ m }$ 表示在原始路网中与节点 $m$ 有道路直接相连的邻近全部节点组成的集合，其中 $N _ { _ m } \subset N$ ;  
$\pmb { R } _ { m , n }$ 为原始路网中 $( \mathbf { m , n } )$ 所在道路的最少巡视次数；  
$\delta$ 为基站中最小的起飞或降落时间间隔;  
$T ^ { \dprime }$ 为无人机 $p$ 的最大巡航时间。

# 2.2 目标函数的建立

a)多无人机进行协同路网巡视需要一套高效合理的飞行路径。首先，在满足一系列巡视任务的同时，无人机的总飞行成本应尽量最小。这里通过控制无人机的总飞行时间最小来使无人机的总飞行成本最小。无人机的总飞行时间等于各架无人机所巡视路段的行程时间之和，可表示为：

$$
\operatorname* { m i n } : f _ { 1 } = \sum _ { m } \sum _ { n \in N _ { m } } \sum _ { t } \sum _ { p \in P } x _ { m , t , n } ^ { p } \cdot t _ { m , n }
$$

b)有时需要考虑多无人机协同巡视任务的高效性，即所有无人机在最短的时间范围内完成所有的巡视任务。这里通过限制单机的最大巡航时间来实现该目标，引入一个参数 $z$ ，其中，∑∑Σxmμnt≤Z,∀p∈P，只要令z的值最小即可。对应的代价函数可表示为

$$
\operatorname* { m i n } : f _ { 2 } = Z
$$

# 2.3 约束条件的建立

为解决基站选址难题，在时空网络中添加一个虚拟起点和一个虚拟终点，构成超级时空网络。所有的无人机在巡视开始时必须从虚拟起点起飞进入实际路网，最后也必须全部降落到虚拟终点。每架无人机只能从虚拟起点起飞一次，也只能从虚拟终点降落一次，对应的约束表达如式（3）（4）所示。

$$
\sum _ { t } \sum _ { n ^ { o } \in N ^ { o } } x _ { o , t , n ^ { o } } ^ { p } = 1 , \forall p \in P
$$

$$
\sum _ { t } \sum _ { n ^ { d } \in N ^ { D } } x _ { n ^ { d } , t , D } ^ { p } = 1 , \forall p \in P
$$

针对巡视问题，要求所有路段至少巡视一次，对一些未布设固定型交通检测器、事故频发路段适当增加巡视次数，使巡视更加切合实际需要。在时空路网中，单路段在整个巡视过程中的被巡视总次数应大于等于该路段所要求的最低巡视次数，该约束如式（5）所示。

$$
\sum _ { p \in P } \sum _ { t } x _ { n , t , m } ^ { p } + \sum _ { p \in P } \sum _ { t } x _ { m , t , n } ^ { p } \geq R _ { m , n } , \forall ( m , n ) \in ( M , N )
$$

其次，为满足上式提出的巡视次数问题，无人机可能会在连续时间段内对同一路段往返重复巡视。模型中考虑添加适当的路段巡视时间间隔约束来避免这种不合理的巡视方式，这里通过限制单路段在给定时间段 $\Delta t$ 内的巡视次数来实现该目标。即每条路段在时间段 $\Delta t$ 内的双向巡视总次数不大于1。对应约束如式（6）所示。

$$
\begin{array} { l } { { \displaystyle { \sum _ { \phi = t } ^ { t + \Delta t } \sum _ { p \in P } x _ { n , \phi , m } ^ { p } } + \sum _ { \phi = t } ^ { t + \Delta t } \sum _ { p \in P } x _ { m , \phi , n } ^ { p } \le 1 } \ , \ }  \\ { { \displaystyle { \forall \ 0 \le t \le n _ { T } - \Delta t , ( m , n ) \in ( \bar { M } , \bar { N } ) } } } \end{array}
$$

然后考虑节点流量守恒问题，即从某节点离开的无人机数量应该等于到达该节点的无人机数量。具体约束如式(7)所示。

$$
\sum _ { p \in P } \sum _ { m \in N _ { n } } x _ { n , t , m } ^ { p } = \sum _ { p \in P } \sum _ { m \in N _ { n } } x _ { m , t - t _ { m , n } , n } ^ { p } , \forall ( n , t ) \in ( N , T )
$$

为避免多无人机在基站同时起飞或降落时发生相互碰撞，模型中要求给定时间段 $\boldsymbol { \mathscr { s } }$ 内至多一架无人机在同一基站起降。具体约束如式（8）（9）所示。

$$
\sum _ { \phi = t } ^ { t + \delta } \sum _ { p \in P } x _ { m ^ { o } , \phi , n } ^ { p } \leq 1 , \forall ( m ^ { o } , n ) \in ( M ^ { o } , N )
$$

$$
\sum _ { \phi = t } ^ { t + \delta } \sum _ { p \in P } x _ { m , \phi , n ^ { d } } ^ { p } \leq 1 , \forall ( m , n ^ { d } ) \in ( M , N ^ { D } )
$$

最后考虑无人机的最大巡航时间问题。单架无人机的巡航时间不应大于其最大巡航时间，对应约束如式（10）所示。

$$
\sum _ { m } \sum _ { n \in N _ { m } } \sum _ { t } x _ { m , t , n } ^ { p } \cdot t _ { m , n } \leq T ^ { p } , \forall p \in P
$$

对某一架无人机 $\boldsymbol { p }$ 而言，只要将超级时空路网中所有$X _ { m , t , n } ^ { p } = 1$ 的数据按照时间顺序排列就可得到无人机 $p$ 在实际路网中的运行轨迹。

如果优化的目标是在最短时间内完成所有巡视任务，则还需考虑如下约束：

$$
\sum _ { m } \sum _ { n \in N _ { m } } \sum _ { t } x _ { m , t , n } ^ { p } \cdot t _ { m , n } \leq Z , \forall p \in P
$$

以式(1)为目标，而以式(3)-(10)为约束，可得到最小化总飞行成本的基站选址和巡视路径规划整合优化模型；以式(2)为目标，而以式(3)-(11)为约束，可得到最小化单机最长飞行时间的基站选址和巡视路径规划整合优化模型。上述两个模型均为大规模的线性整数规划模型。求解这类问题的经典方法主要包括分支定界法和割平面法，也可使用一些经典的启发式算法，如遗传算法、模拟退火算法和蚁群算法等。目前有很多求解整数规划问题效率很高的商业软件，如Cplex、Lingo、Matlab 等。本文将采用商业软件Lingol1对模型进行求解。

# 3 算例分析

图2展示了一个由12个节点和17条路段组成的道路网络，使用无人机对该路网进行巡视。道路节点间的路段行程时间以单位时长的整数倍标示在路段上方。每条路段至少巡视一次，其中（3,4)，（4,5)，（4,6）所在路段为重点路段需要至少巡视两次。同时为避免短时间内某一路段的往返重复巡视，要求巡视时间间隔应大于所有重点路段中最大行程时间的两倍，这里的巡视时间间隔应大于6。无人机在巡视开始时全部从基站起飞，完成所有的巡视任务后回到基站。基站一般建立在道路节点上，单位时间内每个基站至多有一架无人机起飞或降落。

![](images/785d7f7866eafdfc0617a3c20bf15eab5f4b924b02e5da0d312c94d12eb6262b.jpg)  
图2路网示意图

利用图1给出的方法将小区的道路网转化为时空路网，按照行程时间将实际路网拓扑足够多的 $n$ 份。为找出该路网中最佳的基站位置，我们选择12个备选基站分别位于路网中的所有节点位置。假设分别存在节点13、14作为虚拟起点和虚拟终点，与时空路网中的所有备选基站相连接，并且虚拟起终点到时空路网中所有备选基站的时间阻抗均为0。无人机均从虚拟起点起飞，经时空网络中的任意备选基站进入时空路网，完成巡视任务后，经任意备选基站离开时空路网。由于所有的无人机都从虚拟起点起飞，最后全部降落到虚拟终点，并且自由选择从哪个备选基站加载进入或离开时空路网，因此在总飞行代价最小的目标下，可以找出最佳的基站位置和对应路径。同时，选出的基站是具有时间和空间属性的时空路网中的节点，因此只要得到基站在时空路网中的位置，就可以得到实际路网中具体的基站位置和进入或离开基站的时间。

首先使用两架无人机依据本文提出的方法，基于超级时空网络理论从路网中找出最佳的基站位置和相应路径，得到无人机的时空路网运行轨迹如表1所示。

表1无人机在时空路网中的运行轨迹  

<html><body><table><tr><td>UAV</td><td>无人机在时空路网中的运行轨迹</td><td>巡视时间</td></tr><tr><td rowspan="3">1</td><td>(13,0,11) (11,0,6) (6,1,4) (4,3,3)</td><td></td></tr><tr><td>(3,6,12)(12,9,11)(11,12,10)(10,14,7)</td><td>22</td></tr><tr><td>(7,15,8)(8,18,9)(9,19,10)(10,22,14)</td><td></td></tr><tr><td rowspan="3">2</td><td>(13,0,8) (8,0,2)(2,4,1)(1,9,3)</td><td></td></tr><tr><td>(3,10,4)(4,13,5) (5,15,7) (7,17,6)</td><td>24</td></tr><tr><td>(6,19,4)(4,21,5) (5,23,2)(2,24,14)</td><td></td></tr></table></body></html>

1号无人机在 $t = 0$ 时刻从虚拟起点经节点11起飞，在 $t = 2 2$ 时刻经节点10降落到虚拟终点，历时22个单位时间；2号无人机在 $t = 0$ 时刻从虚拟起点经节点8起飞，在 $t = 2 4$ 时刻经节点2降落到虚拟终点，历时24个单位时间。完成整个巡视任务所需要的总巡视时间为46，完成任务所需要的最短时间长度为24。

无人机的数量、重点路段的位置会对无人机的基站选址和巡视效率产生影响。无人机的巡视效率主要体现在无人机的总飞行时间和最大单机飞行时间上。接下来，对图2中的路网进行一系列情景分析，研究不同的参数变量对基站选址和巡视效率的影响。

表2展示了一系列情景分析结果。其中P代表无人机的数量；RL代表重点路段的位置；O、D分别代表起飞基站和降落基站的位置，并与无人机的编号相对应；AT代表无人机的总飞行时间；TL代表无人机的最大单机飞行时间。

表2情景分析  

<html><body><table><tr><td>情景</td><td>P</td><td>RL</td><td>0</td><td>D</td><td>AT</td><td>TL</td></tr><tr><td>1</td><td>2</td><td>(3,4)(4,5）(4,6)</td><td>11,8</td><td>10,2</td><td>46</td><td>24</td></tr><tr><td>2</td><td>2</td><td>(1,3）(9,10）(11,12)</td><td>6,4</td><td>1,12</td><td>48</td><td>24</td></tr><tr><td>3</td><td>2</td><td>(4,6）(7,8)(10,11)</td><td>3,2</td><td>5,7</td><td>46</td><td>24</td></tr><tr><td>4</td><td>3</td><td>(4,6）(7,8）(10,11)</td><td>5,10,7</td><td>3,10,2</td><td>46</td><td>16</td></tr><tr><td>5</td><td>1</td><td>(4,6）(7,8）(10,11)</td><td>7</td><td>3</td><td>47</td><td>47</td></tr></table></body></html>

对比情景1/2/3，无人机数量固定为2架，重点路段分别位于路网的中间、边界以及两者兼有。对比分析表明，重点路段的位置不同，起降基站的位置以及巡视效率也不相同，但是无论参变量如何变化总能得到理想的结果。对比情景3/4/5，重点路段位置固定，当无人机数量较少仅为1架时，无人机从一个基站起飞，另一个基站降落。为满足巡视任务要求，无人机需进行不必要的飞行。当无人机数量超过2架时，随着基站数增加，无人机的总飞行时间可以达到最优。以上5种情景共选出了19个基站，其中18个基站所在交叉口连通路段的巡视总次数为奇数。仅情景4中存在一个基站位于交叉口10处，该交叉□连通路段的巡视总次数为偶数，但是该处同时作为第二架无人机的起飞和降落基站。总结以上情景得出结论：为了使巡视效率最高，起降基站必须完全分布在通过路段的总巡视次数为奇数的交叉口。这与欧拉“七桥问题"中一笔画问题的基本原理相符，佐证了结论的正确性，同时也说明利用本文的方法求出的基站位置和相应路径是正确的。

具体情形如图3所示，当某交叉口连通路段的总巡视次数为偶数时，称为“偶点”。无人机可以从连通的某路段进入，最后全部离开，刚好完成该交叉口附近所有路段的巡视要求，即“七桥问题”当中的“过路点”。某交叉口连通路段的总巡视次数为奇数时，称为“奇点”。无人机通过该交叉口进出N次后，会剩下一条路段未被巡视，如果只进无出，它就是终点；如果有出无进，它就是起点。因此，如果起点和终点不是同一个点，那么它们必须是奇点；如果起点和终点是同一个点，那么它们就必须是偶点。

![](images/0325d3e491d7583fc99145c87f5fe9fd6dd3c9551ac40ecb55f8ae9398d99c1a.jpg)  
图3交叉口示意图

为进一步证实本文提出的模型和方法的有效性，选取新的路网示意图2，如图4所示进行算例分析。使用两架无人机分别对不考虑基站选址和综合考虑基站选址的路网巡视进行研究。该路网由15个节点和23条路段组成，每条路段至少巡视一次，其中（2，3)，(5，8)，(6，9)，（7，14）所在路段需要至少巡视两次。同时为避免短时间内某一路段的往返重复巡视，要求巡视时间间隔应大于6。

![](images/acff76075fdbb9aa1112f6e67ef34e2fc5f452a2f830f258d57cfd571858152d.jpg)  
图4路网示意图2

首先进行不考虑基站位置的路网巡视，从路网中随机选定基站的位置。两架无人机分别以节点3和节点13所处位置为基站，在 $t = 0$ 时刻起飞，最终分别在 $\scriptstyle t = 3 4$ 和 $t = 3 5$ 时刻回到基站。整个巡视任务在35个单位时间内完成，对应的无人机总飞行时间为69个单位时长。

接下来实现基站选址和最佳巡视路径的整合优化问题。利用本文提出的方法，基于超级时空网络理论从路网中找出最佳的起飞点和降落点。1号无人机选择节点6处作为起飞基站，在 $t = 0$ 时刻起飞， $t = 3 3$ 时刻降落到节点4处的基站；2号无人机为了满足单路段的多次巡视时间间隔约束，在 $t = 4$ 时刻从节点3位置的基站起飞，在28个单位时长后完成所有巡视任务，并最终降落到节点11处的基站。整个巡视任务在33个单位时间内完成，对应的无人机总飞行时间为61个单位时长。

根据以上两种情形，得到无人机在不考虑基站选址和考虑基站选址的飞行信息。表3展示了两种情况下的飞行信息对比结果。其中起点和终点分别代表无人机的起飞基站和降落基站所在的节点位置。T代表各架无人机的实际飞行时间；TL代表无人机的最大单机飞行时间；AT代表完成整个巡视任务所需要的总飞行时间；Base表示基站位置所处的节点号。与不考虑基站位置的路径规划相比，综合考虑基站选址和最佳路径规划能够使最大单机飞行时间减少 $5 . 7 1 \%$ ，总飞行时间减少 $1 1 . 5 9 \%$ 。分析结果表明，本文基于超级时空网络理论建立的模型能够有效地解决基站选址和最佳路径规划的整合优化问题，证明该模型和方法是正确的。

表3无人机飞行信息对比表  

<html><body><table><tr><td>情景</td><td>UAV</td><td>起点</td><td>终点</td><td>T</td><td>TL</td><td>AT</td><td>Base</td></tr><tr><td>1</td><td>1</td><td>3</td><td>3</td><td>34</td><td>35</td><td>69</td><td>3/13</td></tr><tr><td></td><td>2</td><td>13</td><td>13</td><td>35</td><td></td><td></td><td></td></tr><tr><td>2</td><td>1</td><td>6</td><td>4</td><td>33</td><td>33</td><td>61</td><td>3/4/6/11</td></tr><tr><td></td><td>2</td><td>3</td><td>11</td><td>28</td><td></td><td></td><td></td></tr></table></body></html>

# 4 结束语

针对无人机在交通网络巡视时的基站选址和巡视路径规划的整合优化问题，提出利用超级网络与时空网络相结合的方法建立对应的整数规划优化模型。这里通过超级网络添加虚拟起终点，与时空路网中全部时刻的所有备选基站相连接构成超级时空网络。在巡视开始时，无人机全部从虚拟起点起飞，经时空路网某时刻的某备选基站进入路网，完成巡视任务后经某备选基站离开到达虚拟终点。由于无人机可以自由选择进出的备选基站以及进出备选基站的时间，因此可以找出最佳的起降基站位置和进出基站的时间。与不考虑基站选址的路径规划相比，将基站选址和交通巡视路径规划整合可有效减少UVA的巡视成本，证明了该模型和方法的正确性。最后，通过考虑单路段的巡视次数和巡视时间间隔，使得优化结果更符合现实。

# 参考文献：

[1]刘晓锋，彭仲仁，张立业，等．面向交通信息采集的无人飞机路径规划 [J].交通运输系统工程与信息,2012,12(1):91-97.(Liu Xiaofeng,Peng Zhongren, Zhang Liye,et al. Unmanned aerial vehicle route planning for traffic information collection [J].Journal of Transportation Systems Engineering and Information Technology,2012,12 (1): 91-97.)   
[2] Coifman B, Mccord M, Mishalani R G,et al. Roadway traffic monitoring from an unmanned aerial vehicle [J]. Intelligent Transport Systems Iee Procedings,2006,153 (1): 11-20.   
[3]AvellarG SC,Pereira GAS,PimentaLCA,et al.Multi-UAV routing for area coverage and remote sensing with minimum time [J]. Sensors,2015,15 (11): 27783-27803.   
[4]Liu Xiaofeng,Gao Limei,Guan Zhiwei,et al.A multi-objective optimization model for planning unmanned aerial vehicle cruise route [J]. International Journal of Advanced Robotic Systems,2016,13 (3):1-9.   
[5]Kim N V, Chervonenkis MA. Situation control of unmanned aerial vehicles for road traffic monitoring [J]. Modern Applied Science,2015,9 (5): 1-13.   
[6] Jevtic A,Andina D, Jaimes A,et al. Unmanned aerial vehicle route optimization using ant system algorithm [C]// Proc of International Conference on System of Systems Engineering.2010:1-6.   
[7]Niu Shuyun,Zhang Jisheng,Zhang Fan,et al.A method of UAVs route optimization based on the structure of the highway network[J].International Journal of Distributed Sensor Networks,2015,2015(1):1667-1670.   
[8]Liu Xiaofeng,Guan Zhiwei, Song Yuqing,et al.An optimization model of UAV route planning for road segment surveillance [J]. Journal of Central South University,2014,21(6): 2501-2510.   
[9]何胜学．无预警紧急疏散中公交车辆路径的确定方法[J].运筹学学报, 2014,18 (3): 47-59.(He Shengxue. Determining optimal routes for transit vehicles in no-notice emergency evacuation [J]. Operations Research Transactions,2014,18 (3): 47-59.)

[10]何胜学，陈经纬．考虑上客点选择的公交紧急疏散时空路网模型[J] 计算机应用研究,2017,34(7):2001-2005.(He Shengxue,Chen Jingwei. Time-space network model of emergency transit evacuation with choice of pick-up points [J].Application Research of Computers,2017,34(7): 2001- 2005.)

[11]陈经纬，何胜学，程龙．基于时空网络的无人车运行计划制定[J].计 算机应用研究,2017,34(12):3642-3646.(Chen Jingwei,He Shengxue, Cheng Long.The operational plan of the automated-vehicle based on timespace network[J].Application Research ofComputers,2017,34(12):3642- 3646.)