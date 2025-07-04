# 基于增强学习的网格化出租车调度方法

何胜学

(上海理工大学 管理学院，上海 200093)

摘要：高度信息化的网格化城市管理可以为出租车运营优化提供新的实时动态乘客需求信息和车辆位置信息。以此为契机，针对城市出租车空驶率高和司乘匹配率低的问题，提出了一种网格化的出租车实时动态调度的增强学习控制方法。通过为出租车提供空驶巡游的动态最佳路线，新的控制方法旨在提高出租车的服务效率，并降低乘客的等待时间。首先，以城市单元网格为基础，明确出租车调度的关键问题；其次，以空驶路线的动态调整为控制手段，建立调度的增强学习模型；最后，给出求解模型的Q学习算法，并通过算例验证新调度方法的有效性。研究表明新方法可以有效提高司乘匹配率、增加总的出租车运营收入、减少乘客平均等车时间和减少总的出租车空驶时间。

关键词：城市交通；出租车调度；增强学习；网格化管理；自适应式控制中图分类号：U491 doi:10.3969/j.issn.1001-3695.2017.11.0995

# Grid-based taxi dispatching method based on reinforcement learning

He Shengxue (Business School, University of Shanghai for Science & Technology,Shanghai 20oo93,China)

Abstract:Highly-informed grid-based city managementcan supplythereal time passnger informationand the position informationoftaxis fortaxi operationoptimization.Onthis account,weproposedagrid-basedtaxi dispatchingdynamiccontrol method basedonreinforcement learningto solvethe problemofthe highvacantaxis rateandthe low matchingrate between taxisand pasengers.Byprovidingtheoptimalcruisingroutes forthevacantaxis,thenewcontrolmethodaims to improvethe serviceleveloftaxisandtolowerthewaitingtimeofpassengers.Firstlybasedothegridsofityweclarifidthekeyproblem oftaxidispatching.Secondly,byusingtheadjustmentofvacanttaxiroute asthecontrolaction,eformulated thereiforcement learning model of taxi dispatching.At last,we proposed the corresponding Qlearning algorithm to solve the new model. Numerical example demonstrated the efectivenessofthe newdispatching method.Theresultsshow that thenew method can not only increase the matchrate between taxisand passengersandthe totalicomeofoperationoftaxiservice,butalsoreduce the average waiting time of passengers and the total travel time of vacant taxis.

Key Words: urban transportation; taxi dispatching; reinforcement learning; grid management; adaptive control

# 0 引言

信息时代的迅猛发展为交通科学研究提供了新的契机与挑战。大数据技术的广泛应用使得过去对出租车出行需求的经验性估计演变为实时动态网络化分布的特征分析与预测。GPS 和GIS的发展为管理部门提供了对出租车的实时位置和行驶轨迹的更加全面信息。过去的扬招式出租车服务也逐渐被各种信息平台的APP服务所替代。上述变化为出租车公司或相关管理部门提供了进一步优化系统运作的机遇。如何有效利用实时车辆位置信息和乘客的出行需求分布实现出租车的实时调度优化业已成为出租车企业面对的首要技术问题。以网格化城市管理为依托，本文提出基于网格化出行需求信息更新和出租车路线优

化的动态出租车调度控制方法。

下面简单介绍出租车调度的相关研究现状。合理的出租车调度可以有效减少出租车空驶产生的费用，有时减少的比例高达 $9 0 \% ^ { [ 1 , 2 ] }$ 。早期研究重点关注出租车的合理定价和总体规模，而当前研究则涉及出租车服务系统的各个方面。其中主要包括网络规模的出租车运行建模[3\~5]、随机的乘客出行需求[6]、出租车电招系统[7,8]、基于元胞网络的出租车运行[9]、需求响应式出租服务[10]以及司乘匹配过程分析[8,11,12]。上述研究的共同之处均假设空载出租车的运行满足网络均衡、出行需求信息事先已知，并且出租车巡游速度给定。在均衡条件下，每一辆空载的出租车选择最近的可获得最大收益的区域作为行驶目的地，没有出租车能通过单方面改变空载行驶路线获得更高收益。上述研究较少考虑动态变化的出行需求和路网实时交通状态的影响，因此很难满足当前高度信息化出租车市场发展的需要。

随着出租车叫车APP的大量涌现，出租车调度在提高司乘匹配率方面变得越来越重要[13]。针对出租车调度优化问题，研究者分别从车辆路径问题(vehicle routingproblem,VRP)[14\~16]和两分图匹配问题（bipartite graph matching problem,BGMP）[2,17,18]角度出发进行建模研究。一般而言，基于VRP的研究为每一辆出租车分配一系列的乘客；而基于BGMP的研究遵循就近原则匹配出租车和乘客。上述研究共同的不足是对出租车运行时间的随机性和乘客出行需求的随机性的考虑不足，因此实用性不强。

针对上述的现有研究不足，本文从四方面进行了改进：a)通过定义城市的网格化区块图，依据网格的乘客出行大数据(可从叫车APP平台和实际调查得到)建立各网格的出行率动态时间分布和目的地选择率。通过上述数据在控制方法实施中预测需求，决策空驶出租车路线。实际的出行需求也可通过实际的系统状态变量体现，并为调度方法所利用；b）为了更好地体现实时交通路网的交通状态对出租车巡游速度的影响，新控制方法可以在各个控制时刻利用实时路况信息和当前的出租车GPS位置更新达到目的地的时间(可通过重新计算最短路径实现)，从而实现对出租车巡游速度随机特征的把控，提升现有调度系统的可靠性；c）新的调度方法以出租车系统运行的仿真模型为基础，使得系统的状态演变更加细致，控制行为的选择更加准确。例如，对每个乘客旅行过程的各个关键时间点的精确描述；d）以增强学习理论为基础，新的控制方法可以有效地处理线上线下的优化学习，并可以根据系统的各种外在变化，如突增的出行需求，适应性地作出调整。

# 1 基本参变量和调度目标

# 1.1基本参变量

$T$ 表示离散时间步长,即实施调度控制的时间间隔。

$k$ 表示时间分段标记， $k = 0 , 1 , . . . , K \circ t = k T$ 表示实施调度控制的一个时间点， $K$ 是实施调度控制的时间范围。

$P$ 表示所有乘客集合， $p \in P$ 表示一个典型的乘客。

$V$ 表示所有出租车集合， $\nu \in V$ 表示一辆典型的出租车。

$G$ 表示所有单元网格的集合， $g \in G$ 表示一个典型的网格。

$\gamma _ { g }$ 表示网格 $g$ 在一个时间分段内的乘客生成率。

$r _ { g , h }$ 表示在网格 $g$ 内生成的一个乘客选择另一网格 $h$ 作为其目的地的概率。

$g _ { p } ^ { o }$ 表示乘客 $p$ 的出发网格,即起点。

${ g } _ { p } ^ { D }$ 表示乘客 $p$ 的目的地网格,即终点。

$t _ { p , 1 }$ 表示乘客 $p$ 的生成时刻，即该乘客利用APP请求服务的时间。

$t _ { p , 2 }$ 表示乘客 $p$ 在其出发网格的登车时刻。

$t _ { p , 3 }$ 表示乘客 $p$ 到达目的地时的下车时刻。

$t _ { p } ^ { W }$ 表示乘客 $p$ 的等车时间。当有出租车满足其需求时， $t _ { p } ^ { W }$

等于 $t _ { p , 2 } - t _ { p , 1 }$ 。

$t _ { p } ^ { R }$ 表示乘客 $p$ 的坐车时间。当有出租车满足其需求时， $t _ { p } ^ { R }$ 等于 $t _ { p , 3 } - t _ { p , 2 }$ 。

$d _ { p }$ 表示乘客 $p$ 的起点与终点之间的乘车距离。

（204号 $\eta _ { \nu }$ 表示出租车 $\nu$ 的状态。当该车有乘客乘坐时， $\eta _ { \nu }$ 取值为1；否则，为0。

$g _ { \nu }$ 表示出租车 $\nu$ 的标记网格。当该车有乘客 $p$ 乘坐时， $g _ { \nu }$ 取值为 ${ g } _ { p } ^ { D }$ ；否则，为出租车 $\nu$ 的实际所在网格。

$t _ { \nu }$ 表示出租车 $\nu$ 的等待激活时间，即距离该车下次被实施调度的时间间隔长度。当该车有乘客 $p$ 乘坐时， $t _ { \nu }$ 表示距离网格 ${ g } _ { p } ^ { D }$ 的行程时间；否则， $t _ { \nu }$ 的值为0。

$G _ { _ { g , n } }$ 表示从网格 $g$ 出发，在 $n$ 个时间步长 $T$ 内，一辆出租车可以达到的网格集合，即网格 $g$ 的 $n$ 级邻域。

$P _ { g } ( k )$ 表示网格 $g$ 内在时刻 $k T$ 等待出租车的乘客集合，ng,p(k)表示集合P(k)中的乘客总数;

$V _ { g } ^ { 1 } ( k )$ 表示时刻 $k T$ 在网格 $g$ 内空驶的出租车集合，ng.v,(k)表示V(k)中的出租车总数。

$V _ { g } ^ { 2 } ( k )$ 表示时刻 $k T$ 以网格 $g$ 为目的地载客行驶的出租车集合， $n _ { g , V , 2 } ( k )$ 表示 $V _ { g } ^ { 2 } ( k )$ 中的出租车总数。

$c _ { 0 }$ 表示出租车的起步价格。

$\vec { c }$ 表示超出起步距离 $d _ { 0 }$ 后,出租车每公里的单价。

$\hat { t }$ 表示乘客在起点的最长可接受等车时间。

# 1.2网格化出租车调度思想

图1给出了一个城市网格化的示意图。乘客 $p$ 从其起点 $g _ { p } ^ { o }$ （204号出发沿虚线路径乘坐出租车达到目的地 ${ g } _ { p } ^ { D }$ 。任意乘客的乘车路线将由调度系统通过最短路径搜索算法得到。网格 $g$ 的1级邻域有两种选择方式。一种是由与其紧邻的上下左右4个网格与其自身构成；另一种则进一步包括与其4个角相接的4个对角网格。网格的2级邻域则由其1级邻域包含的所有网格的1级邻域构成。第一种选择方式得到的邻域称为基础型邻域；第二种选择方式得到的邻域称为扩展型邻域。在算例分析时，本文将比较两种邻域构成方法对结果的影响。

![](images/4a6565b7cc5d1eda870979c492ead0a0f74114830585fedcbb24df38e3a2ec9a.jpg)  
图1城市网格化图

需要区分两种乘客生成方式。实际应用时，当前乘客的信息完全由相应APP平台提供；而未来的乘客则由历史数据预测得到。在算例分析部分，本文通过给定的网格乘客生成率 $\gamma _ { g }$ 和目的地分布概率 $r _ { g , h }$ 来仿真实现当前乘客信息和对未来乘客信息的预测。具体操作可分三步。首先依据 $\gamma _ { g }$ 随机生成当前时间阶段的乘客；然后根据 $r _ { g , h }$ 利用轮盘赌规则确定每个新乘客的目的地；最后利用最短路搜索算法确定乘客的乘车路线。

当一辆空驶出租车 $\nu$ 与同一网格内的乘客 $p$ 匹配后，出租车将按照乘客的乘车路线行驶。出租车的状态 $\eta _ { \nu } \cdot g _ { \nu }$ 和 $t _ { \nu }$ 随之更新。在任意给定的时间 $k T$ ，同一网格内的等待乘客与未载客出租车的匹配遵循如下两原则。乘客按照等待时间长短排序，排除等待时间超过 $\hat { t }$ 的乘客。排序后的乘客等待时间越长越早得到服务。假设所有出租车同质，在匹配中无优先权问题。匹配完成后更新各个网格的特征 $P _ { g } ( k ) \ , \ V _ { g } ^ { 1 } ( k )$ 和 $V _ { g } ^ { 2 } ( k )$ 。当$d _ { p } \geq d _ { 0 }$ 时乘客 $p$ 的付费为 $c _ { p } = c _ { 0 } + \vec { c } ( d _ { p } - d _ { 0 } )$ ；否则，乘客 $p$ 的付费为 $c _ { 0 }$ 。因为假定出租车载客的行驶时间 $t _ { \nu }$ 会受到实际路网交通状态的影响，因此实际应用时 $t _ { \nu }$ 应当根据GPS 提供的车辆位置和交通状态不断调整。在每一控制时间点 $k T$ ，根据载客车辆运行过程中GPS提供的车辆位置和网络中交通状况，以出租车的当前位置为起点，以所载乘客的目的地为终点，计算车辆的最佳行驶路线，并更新车辆预期抵达目的地的时间，即 $t _ { \nu }$ 。在随后的算例分析中，为了模拟上述动态调整过程，本文假设$t _ { \nu }$ 为随机变量。根据出租车 $\nu$ 所载乘客 $p$ 的 $d _ { p }$ 大小对 $t _ { \nu }$ 的大小做随机性处理。具体做法为设定一个单位距离的行驶时间随机误差量 $\chi$ 服从正态分布 $n ( 0 , \ell )$ ，且车辆行驶各路段的行程时间相互独立。那么距离 $d _ { p }$ 的随机时间误差 $\chi _ { p }$ 满足正态分布$n ( 0 , d _ { p } \ell )$ 。假如车辆行驶距离 $d _ { p }$ 的期望时间为 $\overline { { t _ { \nu } } }$ ，那么$t _ { \nu } = \overline { { t } } _ { \nu } + \chi _ { p }$ 。在仿真模拟时，通过为 $\chi _ { _ { p } }$ 取满足其概率分布的一个随机量，具体确定 $t _ { \nu }$ 的值。

在乘客生成和司乘匹配过程中系统的运行基本是确定性的，而当可行的匹配完成后如何确定空载出租车的巡游路线则成为调度系的最大挑战。在过去的扬招式出租车服务中，司机凭个人经验确定空驶巡游路线。但是这种方式会带有很大的随意性，往往造成部分区域出租车数量过多，而部分区域的乘客却得不到及时服务的情况。在信息高度发达的今天，出租车服务的APP化为本文提供了重新审视该问题，即从系统整体角度考虑优化出租车的空驶巡游路线的机会。下节将从增强学习角度详细分析该问题。

出租车调度的核心是确定空载车辆的巡游路线，而目的则是减少乘客的平均等车时间、提高司乘匹配率、减少车辆总的空驶时间和增加出租车运营收入。本研究以提高司乘匹配率为控制行为的直接价值评估指标。在数值算例分析中将对上述乘客的平均等车时间、司乘匹配率、车辆总的空驶时间和出租车运行总收入进行分析。

# 2 增强型学习模型

出租车调度系统的增强学习(RL)控制模型包括五个主要组成部分，即控制行为、控制信息、状态变量、状态价值函数和控制策略。

假设当前时刻为 $k T$ 。当每一个网格可行的司乘匹配完成后，可能会出现部分区域的乘客需要继续等待，而部分网格出现空载的出租车。此时，需要对空载出租车的巡游路线进行决策。设当前空载出租车 $\nu$ 所在网格 $g$ 的1级邻域为 $G _ { _ { g , 1 } }$ 。那么$\nu$ 可以选择 $G _ { _ { g , 1 } }$ 中的任意网格作为 $( k + 1 ) T$ 时刻的目的地。令$V ( k ) : = \{ \nu | \nu \in V , \eta _ { \nu } ( k ) = 0 \}$ 。对于 $\nu \in V ( k )$ ，其选择的下一控制时刻 $( k + 1 ) T$ 的目的地网格设为 $h _ { \nu } ( k )$ 。那么由所有 $h _ { \nu } ( k )$ ，$\forall \nu \in V ( k )$ 构成的网格向量就是对应当前时刻 $k T$ 的控制行为，表示为 $a ( k )$ 。显然当集合 $V ( k )$ 包含的元素较多时， $a ( k )$ 的可行域 $A ( k )$ 将非常庞大。基于增强学习的调度控制目的就是在每个控制时刻选取合理的控制行为，从而实现系统时空上的整体优化。

系统运行中伴随的随机或不确定因素被称为增强学习的控制信息。出租车调度中主要存在两种不确定性因素。一种是单元网格中乘客生成的随机性；另一种是出租车载客行程时间的不确定性。前者在模型中由乘客生成率 $\gamma _ { g }$ 和目的地的分布概率（204号 $r _ { g , h }$ 确定，而后者由具有随机特征的出租车 $\mathbf { \Phi } _ { \nu }$ 的等待激活时间$t _ { \nu }$ 来体现。但为了表述方便，将上述随机因素用抽象向量 $\Delta$ 表示。向量 $\Delta$ 就是系统所需的控制信息。

在每一个控制时间点，控制系统需要基于系统当前的状态和相关的控制信息确定最佳的控制行为。系统的状态变量就是一组描述系统给定时刻状态的特征向量。全面细致地描述出租车服务系统需要对系统大量的细节加以刻画。但是这不仅会造成状态变量过于繁琐，也会使随后的控制行为决策为繁复的次要因素所困。因此本研究将以网格为对象，主要考虑三个特征量，即 $n _ { _ { g , P } } ( k ) \setminus n _ { _ { g , V , 1 } } ( k )$ 和 $n _ { { _ { g , V , 2 } } } ( k )$ 。

假设每次控制行为决策前，每个网格内所有可行的司乘匹配均已完成。此时对于任意网格 $g$ ，其对应的等待乘客数目$n _ { { _ g , P } } ( k )$ 和空载出租车数目 $n _ { { _ { g , V , 1 } } } ( k )$ 不能同时为正。本文选择司乘匹配完成后的 $n _ { _ { g , P } } ( k ) \setminus n _ { _ { g , V , 1 } } ( k )$ 和 $n _ { { _ { g , V , 2 } } } ( k )$ 作为 $k T$ 时刻网格$g$ 状态特征。将所有网格在 $k T$ 时刻的状态特征整合为系统状态向量

$$
s ( k ) : = \{ \cdots , n _ { g , P } ( k ) , n _ { g , V , 1 } ( k ) , n _ { g , V , 2 } ( k ) , \cdots \}
$$

$s ( k )$ 就是对应控制阶段 $k$ 的系统状态变量。所有可行系统状态变量值构成系统状态空间集合 $s$ 。

控制策略指的是由系统状态变量决定控制行为的一种决策函数，即任意给定一个系统状态，依据控制策略可得到对应的唯一控制行为。将任意一个控制策略表示为 $\pi \in \Pi$ ，其中 $\pi$ 为所有可行策略集合。控制策略的函数形式可表示为

$$
a = A ^ { \pi } ( s )
$$

增强学习模型的目的就是在给定约束条件下确定可实现一定目的的最佳策略。本研究的目的之一就是确定实现提高司乘匹配率的出租车空载巡游路线与网格状态量之间的合理关联关系。

对于任意控制阶段，控制行为一旦确定必然会对系统当前和后续的运行产生影响。一般而言控制行为的当前影响较易度量，比如本文中空载车辆下一时刻的目的地一旦确定，随之增加的司乘匹配数就会有所变化。由于系统运行环境不断变化，控制行为的远期系统影响往往难以准确估计。在增强学习中，本文将控制行为直接导致的系统优化目标的变化量称为控制行为的收益，对应的行为收益函数表示为f(s(k),a(k),△(k +1))。

行为收益函数 $f ( s ( k ) , a ( k ) , \Delta ( k + 1 ) )$ 中的 $\Delta ( k + 1 )$ 表示从阶段 $k$ 到阶段 $k + 1$ 系统演变过程中可变为已知的随机控制信息。计算收益函数值的过程分四步。首先在当前阶段完成各个网格的所有可行司乘匹配，确定一个具体控制行为 $a ( k )$ ；其次，在已实现的 $\Delta ( k + 1 )$ 基础上，更新阶段 $k + 1$ 各个网格的空载出租车数；接着，在各个网格实现所有可能的等车乘客与刚刚变为空载的车辆的匹配；最后在各网格实现剩余等车乘客与空载车辆的司乘匹配，记录该类匹配的总数，即对应控制行为 $a ( k )$ 的收益函数值。上述计算的依据为刚完成载客任务的车辆就处于对应的网格，而其他的空载车辆则是由上阶段空载车辆经过路线控制(即控制行为 $a ( k )$ 的作用)后得到的。

合理的控制决策必须考虑控制行为对系统后续状态的影响，以及这种影响的时间衰减性。因此选取如下的优化目标：

$$
\operatorname* { m a x } _ { \pi \in \Pi } \mathbb { E } \{ \sum _ { k = 0 } ^ { \infty } [ \gamma ^ { k } f ( s ( k ) , A ^ { \pi } ( s ( k ) ) , \Delta ( k + 1 ) ) ] \}
$$

其中： $\gamma < 1$ 为折扣因子，算子 $\mathcal { B }$ 表示求变量的期望值。直接求解优化问题(3)非常困难，因此通常的做法是转而求解该问题等价的Bellman方程。为了简化公式表述，用下标“ $k$ ”取代变量的时间标签“ $( k )$ ”。设系统处于状态 $s$ 时的状态价值为 $V ( s )$ 。依据 Bellman 方程，最优状态价值 $\boldsymbol { V } ^ { * } ( s )$ 应满足：

$$
V ^ { ' } ( s _ { k } ) = \mathbb { E } [ - f ( s _ { k } , A ^ { ' } ( s _ { k } ) , \Delta _ { k + 1 } ) + \gamma V ^ { ' } ( s _ { k + 1 } \mid s _ { k } , A ^ { ' } ( s _ { k } ) , \Delta _ { k + 1 } ) ]
$$

下文将设计对应的Q学习算法求解上述问题。 $V ( s )$ 与Q函数 $Q ( s , a )$ 具有如下关系：

$$
V ( s ) = \operatorname* { m a x } _ { a } { Q ( s , a ) } \ .
$$

与 $V ( s )$ 相比， $Q ( s , a )$ 的变量维度增加了一位；但是实际应用时可通过比较不同控制行为的 $Q ( s , a )$ 值更加方便地确定最佳行为。问题的求解依赖于 $Q ( s , a )$ 的具体形式，但是目前不存在 $Q ( s , a )$ 的任何具体形式。因此需要利用某种带有待定参数 $\theta$ （204号的近似函数 $\boldsymbol { Q } ( s , a , \theta )$ 来替代 $Q ( s , a )$ 。最常见的做法是利用人工神经网络(ANN)近似技术完成上述任务。此时参数 $\theta$ 表示神经网络的联接权重和节点阈值[19.20]。根据 ANN 基本理论，利用多层的ANN即可实现对各种函数的无限逼近。特别是当具体函数形式未知条件下，ANN的规范统一结构和有效地参数调整机制为研究提供了一种便捷有效函数近似工具。

# 3 Q学习算法

Q 学习算法是求解增强学习模型的一种非常有效算法[19]。通过将状态价值函数转换为Q函数，可以在算法执行过程中通过直接比较Q函数值的大小选取最佳的控制行为。通过迭代学习，当Q函数的近似形式接近实际Q函数时，上述的控制行为选取变得更加有效。而利用状态价值函数确定最佳控制行为时，必须针对每一个可选行为，将系统进行状态转移，从而确定下一状态的价值函数值。通过比较这些可能的后续状态价值函数值，确定最佳控制行为。与Q学习算法相比，利用状态价值函数来确定控制行为不仅繁琐，而且系统状态转移所带来的计算量也非常可观。因此，本文选取Q学习算法作为求解增强学习模型的基本算法。

在算法中 $k$ 代表当前阶段的序列号，显然 $k T$ 对应一个控制时刻。 $\mathbf { \Sigma } _ { m }$ 表示对系统进行仿真模拟的序号。 $K$ 和 $M$ 分别是总的阶段数目和模拟仿真总次数。针对网格化出租车调度优化的Q算法的求解具体步骤如下：

a)初始化。对所有的系统状态s，给出价值函数Ω(,ak)的近似值以及控制行为 $a _ { k } \in A ( k )$ ， $k ^ { = } \{ 0 , 1 , . . . , K - 1 \}$ 。令 $m$ =1，并初始化s'(k)。

b)选择一个随机信息的样本路径 $\omega ^ { m }$ 。

c)将下面操作步骤依 $k ^ { = } 0 , 1 , . . . , K - 1$ 加以循环迭代:

(a)利用 $\boldsymbol { \varepsilon }$ 贪婪规则确定控制行为。以概率 $\boldsymbol { \varepsilon }$ ，从控制行为集 $A ( k )$ 中随机选择行为 $a _ { k } ^ { m }$ 。而以概率 $_ { 1 \cdot \varepsilon }$ ，利用公式$a _ { k } ^ { m } \in \underset { a _ { k } \in A ( k ) } { \arg \operatorname* { m a x } } \bar { Q } _ { k } ^ { m - 1 } ( s _ { k } ^ { m } , a _ { k } , \theta )$ 选择行为 $a _ { k } ^ { m }$ 。

(b)对信息 $\Delta _ { k + 1 } ^ { m } : = \Delta ( \omega _ { k + 1 } ^ { m } )$ 进行取样，并计算状态变量$s _ { k + 1 } ^ { m } = S ^ { M } ( s _ { k } ^ { m } , a _ { k } ^ { m } , \Delta _ { k + 1 } ^ { m } )$ 。

(c)计算 $\begin{array} { r l } & { \hat { q } _ { k } ^ { m } = - f ( s _ { k } ^ { m } , a _ { k } ^ { m } , \Delta _ { k + 1 } ) + } \\ & { \gamma \operatorname* { m a x } _ { a _ { k + 1 } \in A ( k + 1 ) } \bar { Q } _ { k + 1 } ^ { m - 1 } ( s _ { k + 1 } ^ { m } , a _ { k + 1 } , \theta ) } \end{array} \mathrm { ~ }$

(d)更新参数 $\begin{array} { r l } & { \theta : = \theta + \lambda \nabla \bar { Q } _ { k } ^ { m - 1 } ( - f ( s _ { k } ^ { m } , a _ { k } ^ { m } , \Delta _ { k + 1 } ) + } \\ & { \gamma \bar { Q } _ { k + 1 } ^ { m - 1 } - \bar { Q } _ { k } ^ { m - 1 } ) } \end{array}$ 行为 $a _ { k + 1 }$ 可由 $\boldsymbol { \varepsilon }$ 贪婪规则确定。其次，基于更新后的参数 $\theta$ ，按照下式计算Q因子：

$$
\bar { Q } _ { k } ^ { m } ( s _ { k } ^ { m } , a _ { k } ^ { m } ) = ( 1 - \alpha _ { m - 1 } ) \bar { Q } _ { k } ^ { m - 1 } ( s _ { k } ^ { m } , a _ { k } ^ { m } , \theta ) + \alpha _ { m - 1 } \hat { q } _ { k } ^ { m } \circ
$$

${ \bf d } )$ 令 $m { : = } m + 1$ .如果 $m \leq M$ ，转步骤b)。

e)给出最终的Q因子 $( \overline { { Q } } _ { k } ^ { M } ) _ { k = 1 } ^ { K - 1 }$ 和 $\theta$ 。

上述算法的目的可看做最小化 $\theta$ 的函数z(0)=(1/2)(q-Q"-(s,a,0)²。函数z(0)的负梯度方向为$\nabla \bar { Q } _ { k } ^ { m - 1 } ( s _ { k } ^ { m } , a _ { k } ^ { m } , \theta ) ( \hat { q } _ { k } ^ { m } - \bar { Q } _ { k } ^ { m - 1 } ( s _ { k } ^ { m } , a _ { k } ^ { m } , \theta ) )$ 其中： $\theta$ 作为自变量，而 $\hat { q } _ { k } ^ { m }$ 为给定值。按照经典非线性规划理论，在自变量 $\theta$ 的可行域内，如果当前的 $\theta$ 对应的函数值非局部或全局最小值，且步长足够小，目标函数 $z ( \theta )$ 的值将沿当前变量 $\theta$ 处的负梯度方向下降。因此算法中的参数 $\lambda$ 相当于沿可行下降方向的搜索步长。可以通过试错法确定 $\lambda$ 的合理取值。

# 4 数值实验

本章以图2中由15个网格构成的出租车调度区域为例对本文给出方法进行验证分析。15个网格的编号和对应的乘客生成率 $\gamma _ { g }$ 已在图中标出。网格的长和宽均为 $1 0 0 0 \mathrm { m }$ 。离散时间步长 $T$ 为 $1 0 0 \mathrm { s }$ ，总的时间分段数 $K$ 设为100。出租车的平均速度为 $3 6 \mathrm { k m / h r }$ （即 $1 0 \mathrm { m / s } )$ 。出租车的起步费 $c _ { 0 }$ 为14元，起步距离$d _ { 0 }$ 为 $3 \mathrm { k m }$ ，而超出起步距离后每公里的单价 $\vec { c }$ 为2.5元。乘客在起点的最长可接受等车时间 $\hat { t }$ 设为 $4 0 0 \mathrm { s }$ 。假设网络中运行的出租车总数为30辆。总的仿真次数 $M$ 为300次，参数 $\mathbf { \sigma } _ { \varepsilon }$ 和折扣因子γ均设为0.5，算法的步长 $\lambda$ 设为 $0 . 0 1$ 。 $\boldsymbol { \varepsilon }$ 值的大小决定了学习过程中的利用已有经验进行控制行为选取和控制行为随机选取的占比。 $\mathbf { \sigma } _ { \varepsilon }$ 值的较大，控制行为随机选取的几率就大，算法运行的前期可能需要更多的迭代得到较好的系统表现，但是后期的最佳控制行为选择会更有效。而当 $\varepsilon$ 值的较小时，在算法运行的前期，系统表现较好，但需要更多的迭代实现后期的系统表现提升[19]。γ作为目标的时间折扣因子，其大小反映了算法对系统表现随时间变化的一种折现评价[9]。上述 $\boldsymbol { \varepsilon }$ 和y值的选择只是各种可能性的一种，实际应用时应通过试算确定其合理取值。上述 $\lambda$ 步长的选择也只是一个示例，实际算法应用时，应通过试算确定合理取值。一般而言当Q函数值较大时，$\lambda$ 的取值应当较小。否则，由于目标函数的剧烈变化，算法在执行初期将极不稳定[20]。假设出租车行驶1公里可能产生的行驶时间误差服从均值为0而标准方差为 $2 0 ~ \mathrm { s }$ 的正态分布。

![](images/7f517c60edb0ff11c67d61a698bc79e0ac102a4267d4381f5b5a40e924354403.jpg)  
图2具有15个网格的调度区域

为了使随后的图表更加清晰简洁，定义如下的符号变量。$n _ { \scriptscriptstyle { T C } }$ 表示总的司乘匹配数； $n _ { _ { N S } }$ 表示未得到服务而损失的乘客数；$\overline { { t _ { w } } }$ 表示乘客平均等车时间(s)； $I$ 表示总的出租车运营收入(元);（204号 $T _ { _ { N O } }$ 表示总的出租车空驶时间(s)。NC 表示无控制情景下的出租车运营；CBN表示基于基础型邻域的调度控制；CEN表示基于扩展型邻域的调度控制。

表1不同控制情景下的优化结果比较  

<html><body><table><tr><td>控制方法</td><td>nTc</td><td>nNs</td><td></td><td>I</td><td>TNO</td></tr><tr><td>NC</td><td>719</td><td>235</td><td>135.3</td><td>10991</td><td>69400</td></tr><tr><td>CBN</td><td>845</td><td>139</td><td>130.3</td><td>12725</td><td>47200</td></tr><tr><td>CEN</td><td>983</td><td>53</td><td>105.9</td><td>14393</td><td>54200</td></tr></table></body></html>

表1给出了三种不同控制方式下，出租车服务系统的运行表现。控制情景下的数据来自系统在300次仿真后，排除 $\boldsymbol { \varepsilon }$ 贪婪机制而仅采用最佳控制行为的运算结果。可以看出，与无控制情景相比，调度控制可以明显改善系统的运行效率；而基于扩展型邻域的调度在多个方面优于基于基础型邻域的调度。因为优化的直接目标是增加司乘的匹配数，因此基于扩展型邻域的调度需要出租车空驶更多的时间实现更多的司乘匹配。这可以解释为什么表1中CEN的总出租车空驶时间 $T _ { \scriptscriptstyle { N O } }$ 比CBN要高。

下面以基础型邻域控制CBN为例，分析随着仿真次数的增加各个系统运行指标的变化情况。

![](images/6d1e6685d9d63a1973157a619559020f31bfecaf613b38a94f9c334656b9bc72.jpg)  
图3司乘匹配数的变化情况

![](images/0ada8e653cc2127ae8bbab8d83f99b11d0afb14269582139bd5cecc0ee22cb9a.jpg)  
图4未得到服务而损失的乘客数的变化情况

图3和4分别给出了司乘匹配数nrc和损失的乘客数ns随仿真次数增加的变化情况。随着仿真次数的增加，可以看出司乘匹配数 $n _ { \scriptscriptstyle { T C } }$ 呈现出上升的趋势，而损失的乘客数 $n _ { \scriptscriptstyle { N S } }$ 呈现下降趋势。而具体数值的随机波动变化源于系统本身的随机特征和算法中 $\boldsymbol { \varepsilon }$ 贪婪机制选择控制行为的随机性。

图5中乘客平均等车时间 $\overline { { t _ { \scriptscriptstyle W } } }$ 随着仿真次数的增加在130秒上下随机波动。这说明仿真次数的增加并不能明显改善乘客的平均等车时间。但是本文发现利用扩展型邻域可以降低平均等车时间，而控制条件下平均等车时间均低于无控制的情景。

![](images/2a3cc4b123d26d859d426454be471b5ef07c3c0d8930ed3dc9d2c6857da26fd3.jpg)  
图5乘客平均等车时间 $\overline { { t _ { _ W } } }$ 的变化(时间单位：秒)

图6中的总运营收入随着仿真次数的增加呈现出明显的增加趋势。图7中总的出租车空驶时间随着仿真次数的增加呈现出明显的减少趋势。这些变化与图3中司乘匹配数的增加趋势相对应。

算例求解的计算机程序用Java1.8.0编写，在NetBeansIDE8.0.2开发环境下实现，所用计算机处理器为Intel?Corei3-3120MCPU。两种控制方式下完成300次系统仿真的计算时间均为14s，而完成一次仿真的计算时间约为 $0 . 0 4 \mathrm { s } _ { \mathrm { \odot } }$

![](images/81f962446357b8eaf46b5dd9fe8914ab3fd12da67f326a88efb596a7528cc5d8.jpg)  
图6总的出租车运营收入 $I$ 的变化(单位：元)

![](images/56e0c401dccd805bb506a3632812bd56b8af47afa7c405510a0ae42f4ba58e8b.jpg)  
图7总的出租车空驶时间 $T _ { _ { N O } }$ 的变化 (单位：s)

# 5 结束语

在网格化城市管理的背景下，针对网格化的出租车出行需求动态数据和网格化的出租车路线规划，提出了一种网络出租车调度的增强学习控制方法。新的控制方法可以有效处理系统的随机动态特征(包括随机的行程时间和出行需求)，通过无监督的自适应式强化学习实现出租车的空车路线调度。通过定义网格和网格邻域概念，使得在实施控制方法时可有效利用基于网格大数据的出租车出行需求特征与需求预测。动态的路线调整过程也使得利用实时的车辆定位信息成为现实。在出租车服务系统运行表现上，新的调度控制方法不仅可以增加司乘匹配数和降低乘客流失风险，而且可以增加出租车总的运营收入和降低乘客平均等车时间。

本文研究可从多个方面加以拓展，包括考虑出租车的不同类别、乘客的优先级别、网格划分的不同方式以及实际道路交通状态的实时影响分析等。同时研究方法的有效性还有待进一步的实证分析改进。

# 参考文献：

[1]祝进城，帅斌，孙朝苑，等．固定费率下城市出租车拥挤收费模型与算 法[J].计算机应用研究,2013,30(8):2288-2291.   
[2]Zhan X, Qian X,Ukkusuri S V.A graph-based approach to measuring the efficiency ofanurban taxi service system[J].IEEE Trans on Intelligent Transportation Systems,2016,17(9): 2479-2489   
[3]胡继华，黄泽，邓俊．考虑出行方向的广州出租车时空可达性研究[J]. 计算机应用研究,2014,31(2):454-456.   
[4]Jung J,Chow JY,Jayakrishnan R,et al. Stochastic dynamic itinerary interception refueling location problem with queue delay for electric taxi charging stations[J].Transportation Research Part C,2014,40(1):123-142   
[5]Sayarshad H R,Chow JY. Survey and empirical evaluation of nonhomogeneous arrival process models with taxi data[J]. Journal of Advanced Transportation,2016,50(7):1275-1294.   
[6]Zhang W, Ukkusuri S V. Optimal fleet size and fare setting in emerging taxi marketswithstochastic demand [J]. Computer-Aided Civil and Infrastructure Engineering,2016,31(9): 647-660.   
[7]He F, Shen Z M. Modeling taxi services with smart phone-based e-hailing applications [J]. Transportation Research Part C,2015,58 (1):93-106.   
[8]WangX,HeF,Yang H,etal. Pricing strategies fora taxi-hailingplatform [J].Transportation Research Part E,2016,93 (2): 212-231.   
[9]Wong R,Szeto W,Wong S. Acel-based logit-opportunity taxi customersearch model[J]. Transportation Research Part C,2014,48 (1): 84-96.   
[10] Amirgholy M, Gonzales EJ.Demand responsive transit systems with timedependent demand: user equilibrium,system optimum,and management strategy[J].Transportation Research Part B,2016,92(2):234-252.   
[11] Yang T, Yang H,Wong S C.Taxi services with search frictions and congestion externalities [J].Journal of Advanced Transportation,2014,48 (6): 575-587.   
[12] Zha L,YinY,Yang H.Economicanalysisofride-sourcing markets[J] Transportation Research Part C,2016,71(2): 249-266.   
[13] Nie Y M. How can the taxi industry survive the tide of ride sourcing?Evidence from Shen Zhen, China[J].Transportation Research Part C,2017,79 (2): 242-256.   
[14] Pillac V, Gendreau M, Gueret C,et al. Areview of dynamic vehicle routing problems [J].European Journal of Operations Research,2013,225 (1):1- 11.   
[15] Hosni H,Naoum-Sawaya J,ArtailH.The shared-taxi problem: formulation and solution methods[J].Transportation Research PartB,2014,70(3): 303- 318.   
[16] Jung J, JayakrishnanR,ParkJY.Dynamic shared-taxi dispatch algorithm withhybrid-simulated annealing[J].Computer-Aided Civiland Infrastructure Engineering,2016,31(4): 275-291.   
[17] Agatz N, Erera A, Savelsbergh M,et al. Optimization for dynamic ridesharing:a review [J]. European Journal of Operations Research,2012,223 (2):295-303.   
[18] Nourinejad M,Roorda MJ.Agent based model for dynamic ride sharing[J]. Transportation Research Part C,2016,64(1): 117-132.   
[19] Warren B P. Approximate dynamic programming-solving the curses of dimensionality [M].Hoboken:Wiley,2011.   
[20]DimitriPB,JohnNT,JohnT.Neuro-dynamic programming [M].Nashua: Athena Scientific,1996.