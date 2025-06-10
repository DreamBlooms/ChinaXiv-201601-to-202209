# 自动化集装箱港口考虑AGV伴侣的AGV调度优化问题研究

程聪聪，梁承姬，李晔(上海海事大学 物流科学与工程学院，上海 201306)

摘要：为提高自动化集装箱港口设备的工作效率，提出了一种新的集装箱进出口工艺：堆场一场桥一AGV 伴侣一AGV一岸桥。在考虑AGV伴侣容量限制的基础上，建立了带时间窗约束的AGV调度混合整数规划模型，设计了启发式算法求解 AGV伴侣时间窗，采用粒子群算法进行求解，得出了相应AGV调度优化方案。求解结果表明，AGV 伴侣的设置能有效改善AGV与场桥间的协调性、设备间的等待时间；并且AGV伴侣容量一定时，场桥的等待时间随着AGV的数量增加而减少。

关键词：自动化集装箱港口；AGV伴侣；AGV调度；时间窗；粒子群算法 中图分类号：U691.3 doi: 10.3969/j.issn.1001-3695.2018.02.0091

# Study on AGV scheduling with considering AGV partner in automated container ports

Cheng Congcong,Liang Chengji, Li Ye (InstituteofLogistics Science&Engineering,Shanghai Maritime University,Shanghai201306)

Abstract: To improve the eficiencyof automaticcontainer port equipment.This paper proposes anew container import and export technologynamelyyard-yardcrane-AGVpartner-AGV-quaycrane.Onthe basis ofconsidering thebuffercapacity limit,anAGV scheduling mixed integer programming model with time windowconstraint was built.Aheuristic algorithm was designedto solve the AGVpartner’s time windowandthe model was solvedbyPSOalgorithm,and presents acoresponding scheduling optimization scheme.The experiment results showthattheseting ofthe AGV partercan efectively improve the coordinationbetween AGVand yard crane and reduce the waiting time between the equipment.Whenthe AGV partner capacity is certain ,the waiting time of the yard crane decreases with the increase of AGV.

Key Words: Automated terminal; AGV partner; AGV dispatching; Time window; PSO algorithm

# 0 引言

自动化集装箱集装箱码头作为物流中连接海运和陆运的重要一环，是集装箱运输的中转站，在现代物流中占据越来越重要的地位。近年来，随着船舶的不断大型化[，船只载箱量不断增加，各港口面临着加快船只周转速度、缩短船只在港时间进而发挥大型船的营运成本优势的新挑战[2。如何提高自动化集装箱码头作业效率已成为当前集装箱码头研究重点关注的内容。传统港口集装箱进出口工艺中，使用比较多的是以堆场集装箱起重机（场桥）为主，再配以集卡进行水平运输和岸桥进行岸边装卸作业，以此来完成集装箱的进出口作业。目前传统港口主要采用的集装箱进出口工艺流程是：堆场-轮胎吊-集卡-岸桥。这种工艺往往会出现场桥等待集卡或者集卡等待场桥的情况，这两种情况均会造成港口设备之间的操作出现不连贯、不协调的情况。因此，在自动化集装箱港口中，由于AGV具有自动化、智能化、并行作业的特点，可很好的满足自动化集装箱码头水平运输的要求，一般用自动导引小车（AGV）替代传统港口中的集卡。而由于AGV的应用，AGV伴侣也将应用于港口中。AGV伴侣是安装在箱区前可用于装载或卸载集装箱的支架，可由液压和电动机驱动[3]。如图1所示，在自动化港口中，由于AGV 伴侣的存在，将使自动化集装箱港口与传统码头的进出口的调度方式变得不同，即由原来的堆场-轮胎吊-集卡-岸桥模型，变为文中提出的堆场-场桥-AGV伴侣-AGV-岸桥模型。该模型可以很好的协调AGV与场桥间的等待问题，从而提高港口的作业效率，降低设备等待时间。

对于AGV的调度，已经有很多专家学者进行了研究。Gharehgozli等人提出了一个自适应的大规模邻域搜索算法来解决集装箱码头的集卡路径规划问题。Yong等人基于贪心算法与最小费用流算法提出AGV的调度与配置，有效降低了AGV在码头前沿的等待时间，并且降低了AGV拥堵的可能性。马越汇等人以最末任务结束时间最小化为目标，研究了不确定环境下自动化集装箱码头AGV的调度与配置问题。Saidi-Mehrabad等人提出两阶段蚁群算法对车间调度以及AGV调度进行了研究，并利用经济分析的方法求解出车间中AGV的最佳投入数量以及最佳路由。朱兴业分析了集装箱码头AGV运输系统的组成及特点以及集装箱码头AGV调度影响因素，并在Netlogo平台上做了仿真分析。

![](images/2ce78223dc387837602cdbec1cffbf6a2cbe7233ef68f5db412c62accc8b70de.jpg)  
图1自动化集装箱港口堆场缓存区

港口的其他设备（场桥和岸桥）对AGV调度有很大影响，这方面的研究有：梁承姬等人考虑集装箱顺序及岸桥干涉、集卡作业面调度等约束,建立了一个以最大完工时间最小化为目标的混合整数规划模型，并比较使用遗传算法和粒子群算法求解该模型。杨静蕾[°在龙门吊“作业面”装卸工艺和进出口集装箱同时进行作业的条件下，建立了以集卡行驶距离最短为目标的数学规划模型。张想[]从“作业面”模式的集卡调度问题出发，将集卡、场桥以及岸桥联动协调考虑建立模型，采用NCL语言对模型进行验证。李尤丰等人[2建立了基于空驶最小的集卡动态调度模型，引入N6邻域方法，对集卡路径进行优化。Agra等人[13]利用改进的分支定界法，提出了一种相对位置数学模型，研究泊位分配和岸桥分配问题。Kaveshgar等人[14]提出了一种混合整数规划模型研究场桥和集卡调度问题，并开发遗传算法和贪心算法结合的算法求解该模型。

设备间的缓存区能改善场桥与AGV间的协调问题，目前，针对该方面的研究有：张彦[15通过将缓存区容量问题转化为离散的时间窗问题,加入集卡资源的动态使用和释放，并在此基础上建立数学模型对集卡数量的配置问题进行优化求解。汤鹏飞等人[16在岸桥下设置缓存区，研究ALV 的调度问题；刘枚莲[17]针对泊位作业中的岸桥可能出现等待的问题，着重分析集卡和岸桥的作业衔接，寻找泊位作业阻塞或死锁的原因，借鉴计算机领域中的缓存思想，提出缓存作业区。Nguyen等人[以自动化码头的ALV为研究对象，讨论了如何利用接收、交付地点以及交付任务的时间的相关信息调度ALV。Suruchika等人[19]研究了双码堆场起重机，对其进行随机建模，并对场桥的吞吐能力进行了干扰延迟。最后建立离散事件仿真模型求解，得出干涉效应可以使起重机的吞吐量降低 $3 5 \%$ 的结论。梁承姬等2研究了双小车岸桥的中转平台对于AGV调度的影响，并将中转平台容量转化为时间窗进行进一步的研究。

上述的文献大多数是对港口的某一问题进行研究和优化，而很少的去研究各设备间的影响。因此本文将在此基础上研究AGV伴侣对自动化集装箱港口进出口作业流程改进，减少各设备简单等待，以此提高港口中的作业效率。文中在对自动化集装箱港口AGV路径进行路径规划时，考虑堆场缓存区（AGV伴侣）的缓存作用，将缓存区的容量约束转换为时间窗约束，从而获得最优的AGV调度方案。

# 1 问题描述

在自动化集装箱港口中，场桥与AGV的相互协调性，很大程度上决定了集装箱进出口堆场的效率。针对港口间堆存设备与运输设备间的相互等的问题，文中提出一种新的集装箱进出□流程工艺，以AGV伴侣作为设备间的桥梁，能够有效地提高设备间的连贯性和协调性，减少场桥与AGV的相互等待时间，使得场桥与AGV的效率明显提高。

对于场桥作业来说，出口箱时，场桥将集装箱直接卸在缓存区，不需等待AGV的到来。进口箱时，场桥可以直接从缓存区吊取需要装箱的集装箱，不需要等待AGV运输。整个流程保证了场桥能够连续工作，极大的提高了场桥利用率。对于AGV运输来说，进口箱时，AGV到达堆场后，将所载运的集装箱卸在缓存区，完成卸箱任务后即可离开，不需要等待场桥过来取箱。出口箱时，AGV也可以实现即到即走，不需要等待场桥将集装箱装载到AGV上。这样可以很好地解决设备的等待问题，各设备操作之间的相互依赖性也得以降低。

本文将以AGV作为研究对象，重点研究场桥作业顺序下，将缓存区（AGV伴侣）的容量约束转化为时间窗的约束，建立以场桥的作业延迟时间、AGV的总行驶时间及场桥等待时间最小为目标的AGV调度混合整数规划模型，采用粒子群算法进行求解，并给出了相应调度优化方案。最后讨论了不同缓存区容量和AGV数量时的，最小完工时间以及场桥等待时间，并给出最优缓存区数量和AGV数量等。

# 2 缓存区容量约束模型

# 2.1模型假设

本文主要研究AGV伴侣对AGV调度的影响，为使问题简单便于求解，所以假设如下：

a）不同堆场前方设置的缓冲区的容量大小必须保持一致;  
b）每一辆 AGV 一次只能运送一个集装箱;  
c）场桥的操作时间和集装箱装卸顺序已知;

d）岸桥在AGV运送集装箱到达时能够立即作业；

e）AGV从初始位置出发完成所有任务，相互独立且功能及各指标相同；

f）只考虑两个箱区A1、A2，且A1为进口箱区、A2为出口箱区。

# 2.2符号说明

本文是在已知场桥作业顺序的基础上,考虑堆场前方设置的缓存区容量限制的情况下对参与自动化集装箱码头装卸工作的AGVs进行作业调度。每一个待装卸的集装箱称之为一个任务，用i，j来表示。要装载的集装箱的起点位置是它所在岸桥的位置，终点位置是对应于箱区的位置。

i, $j$ 表示集装箱任务， $^ { k , l }$ 表示场桥编号， $\scriptstyle O , F$ 表示虚拟开始任务和虚拟结束任务， $L$ 表示所有进口集装箱集合，$U$ 表示所有出口集装箱集合，且有$Q = L \cup U , ~ Q ^ { ' } = O \cup Q , ~ Q ^ { ' } = Q \cup F$ ； $\overline { { \boldsymbol { Q } } }$ 表示所有任务的集合， ${ \overline { { Q } } } = \{ O , F \} \cup Q$

$V$ 表示AGV 集合， $\scriptstyle \nu = \mid V \mid$ ，有 $\nu$ 辆AGV完成任务则有 $\nu$ 条直接的AGV调度路径；

$K$ 表示场桥的集合， $K ^ { ' } { = } K \cup \{ k ^ { o } \}$ $\boldsymbol { K } ^ { \prime } = \boldsymbol { K } \cup \{ \boldsymbol { k } ^ { F } \} ;$ （20

$m _ { k }$ ：表示场桥 $k$ 的任务数量， $k \in K$ ：$L ^ { k }$ ：表示场桥 $k$ 的进口箱任务数量， $k \in K$ ：$U ^ { k }$ ：表示场桥 $k$ 的出口箱任务数量， $k \in K$ ：$s _ { i } ^ { k }$ ：表示场桥 $k$ 所属的任务 $i$ 的计划开始作业时刻；（20 $y _ { i } ^ { k }$ ：表示场桥 $k$ 操作任务 $i$ 的实际开始时刻；（202 $z _ { i } ^ { k }$ :表示 AGV 装载场桥 $k$ 的任务 $i$ 时到达堆场缓存区的时

刻；

$B _ { k }$ ：表示设置在场桥 $k$ 下方的缓存区的容量;$M$ 表示一个比较大的整数;$d$ ：表示AGV装卸一个集装箱的时间；$c _ { k i } ^ { l j }$ ：表示 AGV 从完成场桥 的任务 $i$ 后到完成场桥 $l$ 的任务 $j$ 之间的准备时间;

决策变量

$x _ { i j \nu } = \left\{ { 1 \atop 0 } \right.$ 表示第v个AGV在完成场桥第i个任务之后，接着操作第j个任务其他

# 2.3准备时间 $c _ { k i } ^ { l j }$ 的计算

由于假设岸桥能够即时作业，所以不考虑海侧岸桥和AGV的等待时间。两个任务之间的准备时间 $c _ { k i } ^ { l j }$ 会因为采用不同的装卸方式而产生不同的值其中 $a$ 为AGV空载行驶时间， $d$ 代表AGV装卸集装箱的时间， $d _ { \iota } , d _ { u }$ 代表场桥装卸一个集装箱的时间， $b$ 代表AGV的重载行驶时间。AGV有八种装卸方式：a）开始进口集装箱。停留在初始位置的AGV在接到进口箱指令后，空载行驶到卸船岸桥下装载进口箱然后将集装箱运至所属堆场下方的缓存区内存放，等待场桥作业。此时$c _ { k i } ^ { \infty } = a + d _ { l } + b + d _ { u } ;$

b）开始出口集装箱。AGV接到出口箱指令，从初始位置空载行驶至堆场缓存区处装载出口箱然后将集装箱运至该箱所装船的岸桥处。此时 $c _ { k i } ^ { \infty } = a + d _ { \iota } + b + d _ { \iota }$ ：c）只进箱。AGV从上一个进口箱任务的终点位置空载行驶到卸船岸桥下，从岸桥装载卸船箱重载运送到进口箱堆场缓冲区内存放， $c _ { k i } ^ { l j } = a + d _ { l } + b$ ；d）先进后出。AGV从上一个进口箱任务的终点空载行驶到负责出口箱任务的场桥处。。此时 $c _ { k i } ^ { l j } = a$ 。如果场桥 $k$ 和场桥 $l$ 是同一场桥，即 $k = l$ 时 $a = 0$ ·e）先出后进。AGV将出口箱从场桥处运送至装船岸桥后，然后空载至卸船岸桥装运集装箱，运送至指定的场桥位置。此时 $c _ { k i } ^ { l j } = b + d _ { u } + a + d _ { l } + b$ ；f）只出口。AGV从完成上一个出口箱任务的终点位置，空载行驶到下一个所需作业的堆场缓存区处。此时$c _ { k i } ^ { l j } = b + d _ { u } + a ;$ g）结束进口。AGV将进口箱从岸桥运输至堆场缓存区处再空载行驶到 AGV的出发位置。此时， $c _ { F F } ^ { l j } = a$ ；h）结束出口。AGV将出口箱从出口箱区缓存区重载运输至岸桥，再空载行驶到AGV的出发位置。此时，$c _ { F F } ^ { l j } = b + d _ { u } + a$ 。

2.4模型建立

$$
M i n T = \sum _ { k = 1 } ^ { m } \sum _ { i = 1 } ^ { m _ { k } } ( y _ { i } - s _ { i } ) + \sum _ { k = 1 } ^ { m } \sum _ { i = 1 } ^ { m _ { k } } ( y _ { i } - z _ { i } )
$$

约束条件：

$$
\sum _ { \nu = 1 } ^ { V } \sum _ { j = 0 } ^ { m + 1 } x _ { i j \nu } = 1 , \forall k \in K , i = 1 , 2 , \cdots m + 1
$$

$$
\sum _ { V = 1 } ^ { V } \sum _ { i = 0 } ^ { m + 1 } x _ { i j \nu } = 1 , \forall k \in K , \nu = 1 , 2 , \cdots m + 1
$$

$$
\sum _ { l = 1 } ^ { m } \sum _ { j = 1 } ^ { m } x _ { k i } ^ { l j } = 1 , \forall k \in K , i = 1 , 2 , \cdots m _ { k }
$$

$$
\sum _ { k = 1 } ^ { m } \sum _ { i = 1 } ^ { m _ { k } } x _ { k i } ^ { l j } = 1 , \forall l \in K , j = 1 , 2 , \cdots m _ { l }
$$

$$
y _ { i } ^ { k } - y _ { i - 1 } ^ { k } \geq s _ { i } ^ { k } - s _ { i - 1 } ^ { k } , i = 2 , 3 , \cdots
$$

$$
y _ { i } ^ { k } \geq s _ { i } ^ { k }
$$

$$
y _ { i } ^ { k } \geq z _ { i } ^ { k } , i \in L ^ { k }
$$

$$
y _ { i } ^ { k } \le z _ { i } ^ { k } , i \in U ^ { k }
$$

$$
\begin{array} { r } { z _ { j } ^ { l } - \big ( z _ { i } ^ { k } + c _ { k i } ^ { l j } \big ) \geq M ( x _ { k i } ^ { l j } - 1 ) , \forall k \in Q , \forall l \in Q \ ( } \end{array}
$$

$$
m _ { o } = m _ { \nu } \mathop = = \vert V \vert
$$

$$
\sum _ { l \in K } \sum _ { j = 1 } ^ { m _ { i } } x _ { \infty } ^ { l j } = \mid V \mid
$$

上述公式的含义为：

式（1）为目标函数，即场桥操作集装箱任务的延迟时间，由场桥操作某个任务的实际开始时间减去该任务的计划开始时间和场桥操作每个任务的实际开始时刻减去AGV到达缓存区的时刻构成；式（2）表示每辆AGV一次只运输一个集装箱；式（3）表示每个集装箱任务分派给一辆AGV；式（4）表示任意一个任务只有一个后继任务；式（5）表示任意一个任务只有一个前序任务；式（6）表示由同一场桥处理的两个相邻任务的实际开始时间间隔要满足计划开始的时间间隔；式（7）表示任意场桥处理任意任务的实际开始时间要在计划开始时间之后；式（8）表示对于进口箱任务场桥的实际处理时间要晚于AGV的到达时刻；式（9）示对于出口箱任务AGV的到达时刻要早于场桥的实际处理时刻；式（10）表示由同一AGV操作的相邻的两个任务的到达场桥处的时间之间的关系；式（11）对于虚拟开始工作节点和虚拟结束工作节点而言，其虚拟场桥的任务量等于AGV的数量；式（12）表示每一辆AGV路径都以虚拟开始工作为起点。

在缓存区中，由于缓存区的容量有限，所以在任一个操作时刻，缓存区的集装箱量不能超过缓存区的容量，其约束条件如下：

$$
\begin{array} { r l r } {  { \sum _ { i \in I ^ { k } } u _ { i } ^ { k } - \sum _ { i \in I ^ { k } } \nu _ { i } ^ { k i } + \sum _ { i \in I ^ { k } } \nu _ { i } ^ { k i } - \sum _ { i \in I ^ { k } } \Delta _ { i } ^ { k i } \leq B _ { k } } } \\ & { } & \\ & { } & { \times \epsilon K , t \in \{ y _ { i } ^ { k } , \forall i \in U ^ { k } , : z _ { i } ^ { k } , \forall i \in L ^ { k } \} } \\ & { } & \\ & { } & { t - y _ { i } ^ { k } \leq M \cdot u _ { i } ^ { k } , t \in \{ y _ { i } ^ { k } , \forall i \in U ^ { k } \} } \\ & { } & \\ & { } & { t - z _ { i } ^ { k } \leq M \cdot ( \nu _ { i } ^ { k i } - 1 ) , t \in \{ z _ { i } ^ { k } , \forall i \in U ^ { k } \} } \\ & { } & \\ & { } & { t - y _ { i } ^ { k } \leq M \cdot ( u _ { i } ^ { k } - 1 ) , t \in \{ y _ { i } ^ { k } , \forall i \in L ^ { k } \} \ \leq } \\ & { } & { t - z _ { i } ^ { k } \leq M \cdot \nu _ { i } ^ { k i } , t \in \{ z _ { i } ^ { k } , \forall i \in L ^ { k } \} } \\ & { } & { u _ { i } ^ { k } , \nu _ { i } ^ { k i } = \{ 0 , 1 \} } \end{array}
$$

式（13）表示时刻 $\mathrm { \Omega _ { t } }$ 在缓存区堆场出口集装箱的数目、AGV运送到的集装箱数目、进口集装箱数目、AGV运走的集装箱数目的总和不能超过缓存区的容量；式（14）表示每刻缓存区上的集装箱数量要满足缓存区的容量限制式；（15）对于出口集装箱作业而言，当 $t > y _ { i } ^ { k }$ 时， $u _ { i } ^ { k t } = 1$ 即场桥将集装箱从堆场卸载到缓冲区；式（16）对于进口集装箱作业而言，当$t > z _ { i } ^ { k }$ 时， $\nu _ { i } ^ { k t } = 1$ 即场桥将集装箱从缓冲区运至箱区；式（17）对于进口集装箱作业而言，当 $t > y _ { i } ^ { k }$ 时， $u _ { i } ^ { k t } = 1$ 即AGV将集装箱释放到缓冲区；式（18）对于出口集装箱作业而言，当 $t > z _ { i } ^ { k }$ 时， $\nu _ { i } ^ { k t } = 1$ 即 AGV 将集装箱从缓冲区取走；式（19）为两个0-1变量用来对t时刻缓存区中集装箱数量进行约束。

# 2.5启发式方法求解缓存区时间窗

本节以10个任务为例，堆场缓存区容量为2，利用启发式方法求解缓存区的时间窗

表1场桥个任务类型  

<html><body><table><tr><td>任务编号</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td></tr><tr><td>任务类型</td><td>L</td><td>U</td><td>L</td><td>U</td><td>U</td><td>L</td><td>L</td><td>U</td><td>L</td><td>U</td></tr></table></body></html>

根据启发式方法，计算各任务的时间窗如图2所示，其中$y _ { i }$ 表示场桥实际拿起或放下集装箱时刻。由于场桥第的一个任务是进口箱任务，所以应该计算该任务的时间窗下界，很容易得出任务1的时间窗为 $\big [ 0 , y _ { 1 } \big ]$ 。接下来计算任务2的时间窗，由于该任务为出口箱任务，要先计算该任务后所有装船任务可能到达缓存区的时刻。如图3所示，任务3到达缓存区的最早可能时刻为 $y _ { 2 }$ ，任务5到达缓存区的最早可能时刻为 $y _ { 3 }$ ，任务7到达缓存区的最早可能时刻为 $y _ { 5 }$ ，任务9到达缓存区的最早可能时刻为 $y _ { 7 }$ 。再计算时间窗的上界，从第3阶段开始，计算缓存区内集装箱数量的变化，该阶段任务3和任务2进入缓存区，满足容量约束，该阶段对应的时间段可以添加到时间窗内；再看第4阶段，该阶段任务3被场桥运至堆场中，离开缓存区，任务5和任务2进入缓存区，满足容量约束，该阶段对应的时间段可以添加到时间窗内；再看第5阶段，该阶段任务5还未到场桥作业的时刻，故继续留在缓存区内。任务4和任务7进入缓存区，此时缓存区内的集装箱数量已超过容量上限，故任务二无法再进入，因此该阶段的时间段无法增加到该任务的时间窗上，任务2的时间窗上界计算终止，进入场桥下一个任务的时间窗求解，此时任务2的时间窗为： $\left[ y _ { 2 } , y _ { 4 } \right]$ 。其他任务的时间窗计算以此类推，最终得出10个任务的时间窗如图3所示。

![](images/4b9d2f524f8a7ee28987bb8c1206eb3b9d2585350d253f3d9a68f14146f8519e.jpg)  
图2计算场桥每个任务的时间窗示意图

![](images/8ac0f5bcc8dc0659bbbdb7505da5b4f5e35aa0177d21329df1e1cb07467d0f4d.jpg)  
图3场桥各个任务的时间窗

通过以上介绍的方法可以将缓存区的容量约束转换为场桥的每个作业任务的时间窗约束，将约束条件式（13）\~（19）转换成如下约束：

$$
\begin{array} { r } { z _ { i } ^ { k } \in W _ { i } ^ { k } = [ y _ { u } ^ { k } , y _ { i } ^ { k } ] , } \end{array}
$$

$$
u \leq i , u \in \mathbf { L } ^ { k } \cup U ^ { k } , i \in \mathbf { L } ^ { k } , k \in K
$$

$$
\begin{array} { r } { z _ { i } ^ { k } \in W _ { i } ^ { k } = [ y _ { i } ^ { k } , y _ { \nu } ^ { k } ] , } \end{array}
$$

$$
i \leq \nu \ , \nu \in { \bf L } ^ { k } \cup U ^ { k } \nu , i \in U ^ { k } , k \in K
$$

# 3 粒子群算法求解

粒子群算法（PSO）由Kennedy 和Eberhart在1995年提出，该算法模拟鸟集群飞行觅食的行为，通过鸟之间的集体协作使群体达到最优目的。由于粒子群算法结构简单，参数较少，并且该算法的具有记忆性，最优粒子会将信息传递给其他粒子，收敛速度更快。而且粒子群算法应用广泛，不仅可以求解连续函数问题，还能用于随机优化问题的求解，所以本文将运用粒子群算法研究自动化集装箱码头考虑场桥作业顺序和缓存区容量限制的AGV调度问题。

# 3.1PSO 算法数学表达式

设搜索空间为D维，总粒子数为 $\mathfrak { n }$ 。第i个粒子位置表示为向量 $X _ { i } = ( x _ { i 1 } , x _ { i 2 } \cdots \cdot \cdot , x _ { i D } )$ ；第i个粒子飞行历史中的过去最优位置（即该位置对应解最优）为$P _ { i } = ( p _ { i 1 } , p _ { i 2 } \cdots \cdot \cdot , p _ { i D } )$ 其中第 g个粒子的过去最优位置$P _ { g }$ 为所有 $P _ { i } ( i = 1 , 2 , \cdots \cdot \cdot , n )$ 中的最优;第i个粒子的位置变化率（速度)为向量。每个粒子的位置按如下公式进行变化：

$$
\begin{array} { r l } & { \nu _ { i d } ( t + 1 ) = \varpi \times \nu _ { i d } ( t ) + } \\ & { c _ { 1 } \times r a n d ( ) \times [ p _ { i d } ( t ) - x _ { i d } ( t ) ] + } \\ & { c _ { 2 } \times r a n d ( ) \times [ p _ { g d } ( t ) - x _ { i d } ( t ) ] } \end{array}
$$

$$
\begin{array} { c } { { x _ { i d } ( t + 1 ) = x _ { i d } ( t ) + \nu _ { i d } ( t + 1 ) } } \\ { { { } } } \\ { { 1 \leq i \leq n ; 1 \leq d \leq D } } \end{array}
$$

其中： $\mathbf { \Psi } _ { c _ { 1 } , c _ { 2 } }$ 为加速因子，通常为正常数，一般等于2；rand（)为[0,1]间随机数； $\varpi$ 较大适于对解空间进行大范围探查， $\varpi$ 较小适于进行小范围开挖。第 $d ( 1 \leq d \leq D )$ 维的位置变化范围为 $[ - X M A X _ { d }$ ， $X M A X _ { d . } ^ { \quad }$ 1，速度变化范围为$[ - V M A X _ { d }$ ， $V M A X _ { d } ]$ 1，迭代中若位置和速度超过边界范围则取边界值。

PSO 算法可用伪代码如下表示：dofor每个粒子(each particle)按式(1)计算适应度;if 粒子当前适应度优于该粒子历史最优适应度then 记历史最优适应度值和位置( $P _ { i }$ )为该粒子当前适应  
度和位置( $X _ { i } )$ end选择当前粒子群(或相邻子群)中适应度最优的粒子；if 当前粒子群(或相邻子群)中最优适应度优于群内历史最优适  
应度then 记粒子群(或相邻子群)历史最优适应度和最优位置 $P _ { g }$ (or  
$P _ { l }$ )为当前群内最优适应度和最优粒子的位置;for每个粒子按式(22)计算粒子飞行速度 $V _ { i }$ 按式(23)更新粒子位置 $X _ { i }$ end

# 3.2算法实现过程

1）初始化粒子群a)粒子群划分成若干个两两相互重叠的相邻子群;b)每个粒子位置向量 $X _ { \nu }$ 的每一维随机取 $1 \sim K$ （AGV数）之间的整数， $X _ { r }$ 的每一维随机取 $1 \sim L$ （场桥任务数）之间的实数;c)每个速度向量 $V _ { \nu }$ 的每一维随机取 $- ( K - 1 ) \sim ( L - 1 )$ （AGV数）之间的整数， $V _ { r }$ 每一维随机取$- ( L - 1 ) \sim ( L - 1 )$ 之间的实数;d)用评价函数Eval评价所以粒子；e)将初始评价值作为个体历史最优解 $P _ { i }$ ，并寻找各子群内的最优解 $P _ { t }$ 和种群体内最优解 $P _ { g }$ g。2)重复执行以下步骤，直到满足终止条件或达到最大迭代次数a)对每一个粒子，按式（22）计算 $V _ { \nu } \setminus V _ { r }$ 和 $X _ { \nu }$ 、$X _ { r }$ ，其中 $X _ { \nu }$ 向上取整，当V、X超过其范围时取边界值；b)用评价函数Eval评价所有粒子；c)若某个粒子的当前评价值优于其历史最优评价值，则记当前评价值为该历史最优评价值，同时将当前位置向量记为该粒子历史最优位置 $P _ { i }$ ：

d)寻找当前各相邻子群内最优和总群体内最优解，若优于历史最优解则更新P、Pg。

对于子群内有多个体同为最优值的情况，则随机取其中一个为子群内当前最优解，其中，评价函数Eva1完成以下任务：根据式(1)计算该粒子所代表AGV调度方案的成本，在计算中场桥任务的执行次序要根据对应 $X _ { r }$ 值的大小顺序，由小到大

# 执行

# 3.3粒子编码策略

粒子群优化算法的关键问题是粒子的位置与问题的解相对应，本文的粒子编码方式用2L维的向量X表示m个任务、n台AGV车的调度优化问题。每个任务对应两维：完成该任务的车辆编号k,该任务的在k车行驶的任务次序为r。文中创新的将2n 维向量X分成两个L维向量： $X _ { \nu }$ （表示任务对应车辆编号）和 $X _ { r }$ （各任务的任务次序）。例如,假设进口集装箱任务为10,AGV台数为4台，若某粒子的位置向量X为：

<html><body><table><tr><td>任务编号</td><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td><td>6</td><td>7</td><td>8</td><td>9</td><td>10</td></tr><tr><td>X</td><td>1</td><td>1</td><td>2</td><td>2</td><td>2</td><td>3</td><td>3</td><td>3</td><td>4</td><td>4</td></tr><tr><td>X</td><td>1</td><td>2</td><td>3</td><td>1</td><td>2</td><td>1</td><td>3</td><td>2</td><td>1</td><td>2</td></tr></table></body></html>

根据评价函数Eva1评价规则，则该粒子对应解路径为  
AGV1: $0 {  } 1 {  } 2 {  } \mathrm { F }$   
AGV2: $0 {  } 4 {  } 5 {  } 3 {  } \mathrm { F }$   
AGV3: $0 {  } 6 {  } 8 {  } 7 {  } \mathrm { F }$   
AGV4: $_ { 0 \to 9 \to 1 0 \to \mathrm { F } }$

# 4 算例及结果分析

本文以2台场桥、20个集装箱为例，AGV处理一个集装箱任务的时间固定为20s即 $d = 2 0 s$ ，场桥进口一个集装箱的时间固定为 $q l = 1 2 0 s$ ，出口一个集装箱的时间固定为$q u = 1 1 0 s$ ，各场桥的任务性质、先后顺序、计划开始时间如表2所示。假设装载的集装箱和卸载的集装箱都位于箱区的同一贝位。AGV在AGV池、场桥间与各箱区间的行驶时间如表3所示，设AGV的数量为5。

表2 场桥的作业顺序及开始时间 /s  

<html><body><table><tr><td colspan="4">场桥1</td><td colspan="4">场桥2</td></tr><tr><td>任务</td><td>性质</td><td>ql/qu</td><td>ksi</td><td>任务</td><td>性质</td><td>ql/qu</td><td>ksi</td></tr><tr><td>1</td><td>L</td><td>120</td><td>0</td><td>11</td><td>L</td><td>120</td><td>0</td></tr><tr><td>2</td><td>U</td><td>110</td><td>230</td><td>12</td><td>U</td><td>110</td><td>230</td></tr><tr><td>3</td><td>L</td><td>120</td><td>230</td><td>13</td><td>L</td><td>120</td><td>230</td></tr><tr><td>4</td><td>U</td><td>110</td><td>460</td><td>14</td><td>U</td><td>110</td><td>460</td></tr><tr><td>5</td><td>U</td><td>120</td><td>670</td><td>15</td><td>L</td><td>120</td><td>460</td></tr></table></body></html>

<html><body><table><tr><td>6</td><td>U</td><td>110</td><td>880</td><td>16</td><td>U</td><td>110</td><td>690</td></tr><tr><td>7</td><td>U</td><td>110</td><td>1090</td><td>17</td><td>L</td><td>120</td><td>690</td></tr><tr><td>8</td><td>L</td><td>120</td><td>1090</td><td>18</td><td>U</td><td>110</td><td>920</td></tr><tr><td>9</td><td>U</td><td>110</td><td>1320</td><td>19</td><td>L</td><td>120</td><td>920</td></tr><tr><td>10</td><td>L</td><td>120</td><td>1320</td><td>20</td><td>U</td><td>110</td><td>1150</td></tr></table></body></html>

注：10代表岸桥1的第一个任务；L代表进口箱，U代表出口箱。

表3AGV在各个场桥及各箱区间的行驶时间/s  

<html><body><table><tr><td></td><td>O/F</td><td>YC1</td><td></td><td>A1（进口）</td><td>A2（出口）</td></tr><tr><td>O/F</td><td>0</td><td>130</td><td>100</td><td>150</td><td>180</td></tr><tr><td>YC1</td><td>130</td><td>0</td><td>30</td><td>230</td><td>150</td></tr><tr><td>YC2</td><td>100</td><td>30</td><td>0</td><td>260</td><td>180</td></tr><tr><td>A1</td><td>150</td><td>230</td><td>260</td><td>0</td><td>30</td></tr><tr><td>A2</td><td>180</td><td>150</td><td>180</td><td>30</td><td>0</td></tr></table></body></html>

注：A1为进口集装箱堆场，A2为出口集装箱堆场。

# 4.1粒子群算法求解结果

利用第三节中粒子群算法对模型进行求解,收敛曲线如图4所示，在250代左右，目标函数值趋于稳定，最终得到的目标函数值为12625s；同时最优的AGV调度方案如表4所示。

![](images/8043e189a169e292b32fecd4698ea2300b30c32081ceff870cbe4ec022c8c95c.jpg)  
图4最终迭代收敛曲线图

表4最终求得的AGV的调度方案如下  

<html><body><table><tr><td>AGV</td><td>最终调度方案</td></tr><tr><td>AGV1</td><td>0—1—8-9-18-F</td></tr><tr><td>AGV2</td><td>0-—2—5—14—15-F</td></tr><tr><td>AGV3</td><td>0—3—10—12—16—F</td></tr><tr><td>AGV4</td><td>0—6—7—13—19-F</td></tr><tr><td>AGV5</td><td>0—4—11—17—20-F</td></tr></table></body></html>

# 4.2不同缓存区容量下时间窗比较

由于每个任务的时间窗的大小和缓存区的容量相关，本节将讨论不同缓存区容量下，每个任务的时间窗大小。

对于进口箱任务，该任务的时间窗的最早开始时间为该任务能够最早进入缓存区的时间，最晚开始时刻为该任务被场桥吊具起吊的时刻；对于出口箱任务，该任务的时间窗的最早开始时间为该任务被场桥卸载到缓存区的时间，最晚开始时刻为该任务被AGV装离缓存区的时刻；如图5所示，每个任务的时间窗大小，与该任务的任务类型相关。不同的任务类型其时间

窗也不相同。

随着缓存区的不断增加，每个任务的时间窗的上下界会发生变化。具体分为：进口箱任务的下界和出口箱任务的上界发生变化。从图7可以看出，任务5、任务6、任务7以及任务9 的时间窗发生明显变化。

![](images/4210e9247185ec69073f70ea7e3d7f1b66a023dc28706989a777d77430dcb7a0.jpg)  
图5不同缓存区容量下时间窗比较

# 4.3不同缓存区容量和AGV数量下目标函数值的比较

如图6所示，当AGV数量为5，不管缓存区容量是多少，此时的目标函数的值都是最小的。此后，优化目标值虽有所增加但是增加的幅度很小。这说明合理的配置AGV数量对整个装卸作业的意义重大。

![](images/55f385184c850bba61cf644c5313fef4736362828a53157004fd97923b99c62f.jpg)  
图6不同缓存区量和AGV数量下的目标函数值变化

当缓存区容量一定时，AGV的数量从3台增加到5台时，目标函数值迅速下降，说明AGV与场桥相互等待的时间也减少了。这是因为，当AGV数量不足时，对于出口集装箱而言，无法及时的将缓存区的集装箱运至岸桥处，当缓存区容量达到上限时，会造成场桥与AGV的相互等待；对于进口集装箱而言，由于AGV的不足而不能及时的将集装箱运送至缓存区，也会造成AGV与场桥的相互等待。但并不是随着AGV的增多，目标函数值会持续下降。如图中所示当AGV的数量大于5时，目标函数值值反而增大了。这是因为当AGV过多时，而场桥的能力有限，不能及时将缓存区内的AGV取走，造成后续的AGV无法将集装箱卸至缓存区，由此产生AGV与场桥的相互等待。

当AGV数量一定时时，随着缓存区容量场增大，目标函数值将会减小。这是因为当进行进口箱任务时，缓存区越大，缓存区可同时存放更多的集装箱，AGV将不必等待场桥；对于出□箱任务，缓存区越大，场桥可以将更多的集装箱放置于缓存区，不必等待AGV的到来。这样可以大大减少AGV与场桥间的相互等待。

# 4.4不同缓存区容量和AGV数量下场桥等待时间的比较

如图7所示，当AGV数量一定时，缓存区容量越大，场桥与AGV的等待时间就越少。由于缓存区的存在，场桥在装卸过程中，可以不必等待AGV的到来，在AGV运输集装箱的过程中，可以对缓存区中的其他集装箱进行作业。从图可以看出，3台AGV时，缓存区容量为2的场桥等待时间明显低于缓存区容量为1的情况。由此可以说明，缓存区可以更好地有效利用港口的设备资源，提高设备作业的连贯性和协调性，减少设备间的等待时间，提高港口的操作效率。

由于缓存区的容量是有限制的，当缓存区容量达到上限，AGV此时运输集装箱到达堆场时，AGV不可避免的进入等待环节；同样场桥卸载的出口箱时，由于缓存区容量达到上限，新到达的集装箱将不允许进入，场桥也不可避免地进入等待的环节。正是因为缓存区的容量是有限制的，所以当AGV数量增加到6辆的时候，随着缓存区容量的增加，场桥的等待时间将不会有明显变化。

![](images/8a806b6fa13bda844374115a215daa7851ad6ae7b97cb7612a73745eb3e2a5ec.jpg)  
图7不同缓存区量和AGV数量下的场桥等待时间变化

# 5 结束语

AGV作为自动化集装箱港口的主要运输工具，其调度问题与堆场和场桥关系很紧密，如何在场桥作业的制约下合理调度水平运输设备，降低设备作业之间的依赖性，提高港口作业设备之间的连贯性与协调性以及港口的生产率，降低船舶的在港时间，最小化港口的生产成本成为当前各集装箱港口需要解决的首要问题。因此，本文考虑缓存区容量限制，建立了以场桥的作业延迟时间、AGV的总行驶时间及场桥等待时间最小为目标的AGV调度混合整数规划模型，采用粒子群算法进行求解。最后讨论了不同缓存区容量和AGV数量时的AGV调度方案，并给出最优缓存区数量和AGV数量。从设计的算例来看，缓存区的设置对于提高港口装卸设备利用率有着重要意义。

集装箱码头水平运输设备的调度还会受到岸桥的等码头其他资源分配和调度方案的影响，为此，加强AGV、场桥与其他多个资源的集成调度将会成为提高码头生产效率的重要手段。此外水平运输车辆在空载和重载时的行驶速度具有明显的不确定性，因此考虑不确定因素情况下码头装卸设备的集成调度问题将会成为今后研究的重点。

# 参考文献：

[1]梅叶．新常态下我国内贸集装箱运输发展策略[J].集装箱化,2015,26 (5):4-8.(Mei Ye.Under the new normal, China's domestic trade container transport development strategy[J]. Containerization, 2015,26(5): 4-8.)

[2]江少文．集装箱船舶大型化对上海港发展的影响和机遇[J]．中国航海， 2007(3):77-80.(Jiang Shaowen.The impact and opportunity oflarge-scale container ship to Shanghai port development [J]. China Sailing,2007 (3): 77-80.)

[3]金祺，罗勋杰，韩保爽．自动化集装箱码头水平运输设备选型[J].水 运工程，2016 (9):87-90.(Jin Qi,Luo Xunjie,Han Baoshuang. The automation level of container terminal transportation equipment selection [J].Marine Traffic Engineering,2016 (9): 87-90.)

[4]Gharehgozli AH,Laporte G,Yu Y,et al. Scheduling twin yard cranes in a container block [J]. Transportation Science,2014,49(3): 686-705.

[5]Cheng YL,Sen HC,Natarajan K,et al.Dispatching automated guided vehicles in a container terminal [M]// Supply Chain Optimization. Boston: Springer,2005:1-30

[6]马越汇，胡志华．不确定环境下自动化集装箱码头AGV调度与配置问 题[J].广西大学学报：自然科学版，2016,41(2).(MaYuehui,Hu Zhihua.Automatic container terminal AGV scheduling and configuration problem under uncertain environment [J]. Journal of guangxi university (natural science edition),2016,41 (2).)

[7]Saidi-Mehrabad M, Saeed Dehnavi-Arani S,Evazabadian F.An ant colony algorithm (ACA） for solving the new integrated model of job shop scheduling and conflict-free routing of AGVs [J].Computers & Industrial Engineering,2015,86 (8): 2-13.

[8]朱兴业．集装箱自动化码头自动导引小车调度仿真分析[C]//自动化 集装箱码头应用技术交流会论文集.2015.(Zhu Xingye.Simulation analysis of automatic guide car scheduling for container automation terminal [C]//Proc of Automatic Container Terminal Application Technology Exchange Meeting.2015.)

[9]梁承姬，沈佳杰.考虑装卸顺序的岸桥与集卡协调调度问题研究[J] 计算机应用研究,2016,33(12):3591-3595.(Liang Chengji,Shen Jiajie. Study on the coordinated scheduling of quay crane and yard truck in loading and unloading sequence [J]. Computer Application Research,2016,33 (12): 3591-3595.)

[10]杨静蕾．集装箱码头物流路径优化研究[J]．水运工程,2006(1):32-35. (Yang Jinglei. Study on logistics path optimization of container terminal [J]. Marine Traffic Engineering,2006(1): 32-35.)

[11]张想．基于NCL的集装箱码头集卡路径优化问题研究[D]．大连：大 连海事大学，2011.(Zhang Xiang.Study on optimization of container terminal set card path based on NCL [D].Dalian:Dalian Maritime University,2011)

[12]李尤丰，李勤丰，刘玉霞等．一种新的集卡动态调度模型及算法[J]. 南京师大学报：自然科学版，2014,37(1):104-111.(LiYoufeng,Li Qinfeng,Liu Yuxia,etal.A new set card dynamic scheduling model and algorithm[J]. Journal ofnanjing normal university: Natural Science Edition, 2014,37 (1): 104-111. )

[13] AgraA,Oliveira M.MIP approaches for the integrated berth allocation and quay crane assignment and scheduling problem [J].European Journal of Operational Research,2018,264(1):138-148

[14]KaveshgarN,Huynh N. Integrated quay crane and yard truck scheduling for unloading inbound containers [J].International Journal of Production Economics,2015,159:168-177

[15]张彦．离散时间窗下集卡数量优化研究[J].武汉理工大学学报：信息与管理工程版,2013,35(2):202-206.(Zhang Yan.Optimization of thenumber of CARDS in discrete time window [J].Journal of WuhanUniversity of Technology: Information And Management Engineering,2013,35 (2):202-206)

[16]汤鹏飞，梁承姬，丁一，等.考虑岸桥缓存区的ALV调度优化问题研究 [J]．广西大学学报：自然科学版,2015,40(6):1540-1550.(Tang Pengfei, Liang Chengji,DingYi,etal.Study on theALV scheduling optimization problem of quay crane cache area [J]. Journal of Guangxi University: Natural Science Edition,2015,40(6):1540-1550.)

[17]刘枚莲．基于缓存思想的集装箱码头泊位作业优化[J]．大连海事大学 学报，2010,36 (4):39-42.(Liu Meilian.A container terminal berth optimization based on the idea of caching[J].Journal of dalian maritime university,2010,36(4):39-42.)

[18]Nguyen VD,KimKH.A dispatching method for automated lifting vehicles inautomated port container terminals [J]．Computers & Industrial Engineering,2009,56 ():1002-1020.

[19] Saini S,Roy D,KosterR.A stochastic model for the throughput analysis of passing dual yard cranes [J].Computers & Operations Research,2o17,87: 40-51.

[20]梁承姬，李晔，汤鹏飞.考虑双小车岸桥中转平台的 AGV调度问题研 究[J].计算机应用研究,2018,35(4):1056-1061.(Liang Chengji,LiYe, Tang Pengfei. Study on AGV scheduling with considering dual-trolly quay crane's transfer platform[J]. Computer Application Research,2018,35 (4): 1056-1061. )