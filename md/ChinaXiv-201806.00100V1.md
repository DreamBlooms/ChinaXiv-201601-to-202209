# 一种基于IBPSO的SDN控制器放置优化方案\*

王潇，杨金民

(湖南大学 信息科学与工程学院，长沙 410082)

摘要：软件定义网络（software defined network，SDN）通过控制器实现网络的灵活管控，因此控制器放置对网络整体性能至关重要。提出了改进离散粒子群优化（improved binary particle swarm optimization，IBPSO）算法用来解决控制器放置问题。该算法基于粒子群的全局最优和单个粒子的个体最优来决定粒子当前取值概率，消除粒子当前值对下一步迭代的影响，从而加快收敛速度，找到更优的最终结果。仿真结果表明，与离散粒子群优化（binary particle swarmoptimization，BPSO）算法相比，由该算法得出的控制器放置方案在实现控制器负载均衡的同时，还可以显著降低控制器的数量。

关键词：软件定义网络；控制器放置；负载均衡；粒子群算法中图分类号：TP393.0 doi: 10.3969/j.issn.1001-3695.2018.03.0225

# Optimization scheme for SDN controllers’placement based on IBPSO

Wang Xiao, Yang Jinmin (College ofComputer Science& Electronic Engineering Hunan University,Changsha 410082,China)

Abstract:The software defined network (SDN)realizes the flexiblecontrolof the network through thecontroler,so the placement oftecontroleriscritical totheoverallprformanceofthe network.This paper proposedan improved improved binaryparticle swarm optimization(IBPSO）algorithm to solve the controler placement problem.IBPSO algorithm determinesthecurrent valueof particles basedon boththe global optimalandthe individual optimal,thus weakening the influenceofparticlecurrntvalueonthenextiteration,andaccelerating theconvergence,whichleaded toabeterfinalesult. The simulation results show that compared with the BPSO algorithm,the controler placement scheme obtained by this algorithm can significantly reduce the numberof controllrs while realizing the load balancing ofthe controller. Key Words: software defined network; controllrs’ placement; load balancing; particle swarm algorithm

# 0 引言

传统网络难以满足云计算、大数据，以及相关业务提出的灵活的资源需求。传统网络设备的封闭性，使得在真实环境中规模部署新协议时通常会引发出一系列问题。因此，软件定义网络应运而生。软件定义网络(software defined network，SDN)[1]是一种新型的网络架构，它的核心理念是将网络的控制层面和数据转发层面进行分离，从而实现对网络的集中化控制。

SDN将原来封闭在交换机或路由器中的控制平面分离出来，形成一个网络部件，称之为 SDN 控制器。SDN 通过控制器来实现对数据转发设备的统一控制。在单控制器 SDN网络中如NOX[2]、Beacon[3]、Floodlight[4]，随着网络规模的不断增加,控制器的处理能力将会成为系统的瓶颈。因此，研究人员提出了多控制器 SDN网络，如Onix[5]、Hyperflow[6]、Kandoo[7]等。多控制器SDN网络通过在网络中部署多台控制器从而实现逻

辑上的集中式控制。

对于多控制器SDN网络来说，一个关键问题就是控制器放置问题（controllerplacement problem，CPP）。CCP问题最早是由Heller等人[8提出，其控制器位置是通过最小化控制器与交换机之间的平均时延和最大时延来确定的。文献[9]提出了一种基于密度的控制器放置算法，以解决控制器部署在延迟、容错和控制器数量方面的要求，但是未将控制器负载考虑在内。一种基于流管理的控制器放置策略，包括将业务负载迁移到冗余链路[10]、动态的添加或删除控制器、关闭相关连接[1]被提出用来节省开销。但是流管理会增加额外的成本，同时网络性能与节能之间的权衡也需要深入评估。

现有针对CCP问题的研究主要分为四类[12]，即减少交换机与控制器之间时延[8.13]、提高可靠性和弹性[14]、减低部署成本和资源消耗[15]、多目标方法[16]。但是在真实环境中，控制器的处理能力对网络的性能至关重要。如果控制器的负载过重，控制器将不能对流请求进行及时的处理，从而影响网络的性能;如果控制器负载过轻，控制器就未得到充分的利用，从而造成资源浪费。因此，合理的控制器放置方案能促进控制器的高效利用，使控制平面负载均衡。

本文将控制器的负载作为优化变量，建立面向SDN负载优化的数学模型，得出启发式的优化求解方案。该方案使用改进的离散粒子群优化算法即IBPSO 算法来得出控制器的放置方案。该方案首先将控制器放置问题模型化为粒子群中的粒子位置优化问题；然后将控制器处理能力作为约束条件，将控制器负载均衡度作为适应度函数来评价部署方案。每个粒子通过迭代不断向历史最佳位置和全局最佳位置优化，最终得到近似最优的SDN控制器放置方案。

# 1 SDN控制器放置问题建模

SDN控制器放置问题就是在一个给定的网络拓扑中，确定网络中的控制器与哪些交换机相连，能够使整个网络中的负载分布更均衡。SDN的网络拓扑可模型化为一个图G(V,E)，其中V是图G的结点集合，表示网络中的交换机集合，$\scriptstyle \mathsf { V } = \{ \mathsf { v } 1 , \mathsf { v } 2 , \ldots \mathsf { v } \mathrm { n } \}$ ， $\lvert \mathrm { V } \rvert { = } \mathrm { n }$ ；E为图G的边集合，表示交换机之间直接相连的的物理链路的集合；{C}表示控制器集合， $\vert { \bf C } \vert = \mathrm { m }$ 。假定在向网络G中部署控制器时，可以在网络中任何放置交换机的节点处放置控制器。交换机与控制器之间的关系用 $\scriptstyle \mathrm { n } \times \mathrm { m }$ 的分布矩阵 $X = ~ ( x _ { i j } )$ 来表示。 $x _ { i j }$ 表示交换机 $V _ { i }$ 与控制器 $C _ { j }$ 之间的连接关系，如果 $x _ { i j }$ 为1，则表示控制器 $C _ { j }$ 是交换机 $V _ { i }$ 的主控制器，否则 $x _ { i j }$ 取值为0。

在SDN网络中，控制器的负载来源于交换机的packet-in消息，以及控制器之间保持视图一致性的交换信息。其中，源于交换机的packet-in 消息占控制器负载的主要部分，所以本文使用交换机向控制器发送的packet-in消息数作为控制器负载的衡量指标。控制器 $C _ { j }$ 的负载用 $L _ { j }$ 表示， $f _ { i }$ 表示交换机的流请求数，控制器 $C _ { j }$ 的负载 $L _ { j }$ 可表示为

$$
L _ { j } = \sum _ { \nu _ { i } \in V } x _ { i j } \mathcal { I } _ { i }
$$

控制器 $C _ { j }$ 的最大处理能力用 $c _ { j }$ 表示，于是控制器 $C _ { j }$ 的利用率 $\begin{array} { r } { u _ { j } { = } L _ { j } / c _ { j } , } \end{array}$ 。SDN网络中所有控制器的平均利用率为 $\mathbf { \Pi } _ { u } ^ { - }$ 。

$$
\overline { { \pmb { u } } } = \frac { { \bf 1 } } { m } \sum _ { C _ { j } \in C } { \pmb { u } } _ { j }
$$

控制器的负载均衡度为 $\boldsymbol { \mathcal { Q } }$ 。

$$
Q = \frac { 1 } { m } \sum _ { j = 1 } ^ { m } ( u _ { j } - \overline { { u } } ) ^ { 2 }
$$

SDN控制器部署的优化模型为 $\operatorname* { m i n } Q , Q$ 的取值范围为（0）

考虑到控制器的处理能力，所以每个控制器所处理的请求数量不能大于 $c _ { j }$ ，即利用率：

$$
\mathbf { \Psi } _ { \pmb { \mathscr { u } } _ { j } } \le \mathbf { 1 }
$$

根据OpenFlow[协议，每一个交换机只能由一个主控制器控制，有约束条件：

$$
\forall \mathbf { i } , \sum _ { C _ { j } \in C } \mathbf { x _ { i j } } = \mathbf { 1 }
$$

$$
\forall i , j , x _ { i j } \in ( 0 , 1 )
$$

由式（5）可知，控制器负载均衡模型求解问题是一个0-1整数规划问题。针对0-1整数规划问题，常采用启发式算法来进行求解。因此，可以采用改进的离散粒子群优化算法来求解该模型。

# 2 改进的粒子群优化算法

BPSO算法是一种求解离散问题的启发式搜索算法。BPSO在求解时将问题的解抽象为搜索空间中的粒子，并通过适应度函数来评估粒子的适应值。BPSO将粒子的每一维的位置向量$x _ { i }$ 限定为1或者0，速度根据式（6）更新。用速度更新位置时，BPSO采用sigmoid函数将速度映射到[0,1]区间，如式（8）（9）所示。如果 $V _ { i }$ 高一些，粒子的位置 $x _ { i }$ 更有可能选1， $V _ { i }$ 低一点则 $x _ { i }$ 更有可能选0。其中：rand（）是（0,1）之间的随机数；pbest为个体历史最优值；gbest为种群历史最优值； $\mathbf { c } _ { 1 }$ 和 $\mathbf { c } _ { 2 }$ 为学习因子，是非负常数，通常取值为2； $\boldsymbol { \omega }$ 表示惯性因子。

$$
\begin{array} { r l } & { V _ { \mathrm { i } } = \omega \times V _ { i } + c _ { 1 } \times r a n d ( \it { \Delta } ) \times ( p b e s t _ { i } - } \\ & { x _ { i } ) + c _ { 2 } \times r a n d ( \it { \Delta } ) \times ( g b e s t _ { i } - x _ { i } ) } \end{array}
$$

$$
S \left( \nu _ { i } ^ { t + 1 } \right) = \frac { 1 } { 1 + e ^ { - \nu _ { i } ^ { t + 1 } } }
$$

$$
\mathbf { X } _ { i } ^ { \mathsf { t } + 1 } = \left\{ \begin{array} { l l } { 1 , r a n d ( ) \leq S ( \nu _ { i } ^ { t + 1 } ) } \\ { 0 , o t h e r w i s e } \end{array} \right.
$$

BPSO算法通过sigmoid函数将 $V _ { i }$ 转变为 $x _ { i }$ 取0或者取1的概率，未能充分利用粒子群算法的性能[18]。考虑到在现实社会中，人在做决定时往往会依赖于个人以往的历史经验以及群体的历史经验，因此，本文提出了IBPSO算法。该算法根据控制器放置问题的特点，重新定义了粒子及粒子位置更新过程。每个粒子代表一种控制器部署方案，在对粒子位置更新时根据粒子个体历史最优解pbest和种群历史最优解gbest由贝叶斯公式来决定粒子位置取值的概率。

# 2.1粒子位置定义

假设SDN网络中有 $\mathrm { ~ m ~ }$ 个控制器，交换机的数量为 $\mathfrak { n }$ 。在此初始化一群粒子，设初始化粒子的个数为 $\mathrm { ~ \bf ~ N ~ }$ ，每个粒子代表一种控制器部署方案。每个粒子都可以用一个 $\mathfrak { n }$ 维向量 $X _ { i }$ 表示。其中 $X _ { i = [ x _ { i l } , x _ { i 2 } \dots x _ { i n } ] , \mathrm { ~ I ~ } }$ 1为交换机的个数， $x _ { i l }$ 表示在第i种可行方案中，编号为1的交换机连接到的控制器编号。若交换机j与交换机 $\mathbf { k }$ 连接到同一个控制器，则有 $\scriptstyle x _ { i j } = x _ { i k }$ 。在第i中可行方案中交换机与控制器的连接关系可以用一个（0,1）位置矩阵$\boldsymbol { C } \boldsymbol { C } _ { i }$ 来表示：

$$
C C _ { i } = \left[ \begin{array} { c c c c c c c } { c _ { 1 1 } ^ { ~ i } } & { c _ { 1 2 } ^ { ~ i } } & { \ldots } & { c _ { 1 k } ^ { ~ i } } & { \ldots } & { c _ { 1 m } ^ { ~ i } } \\ { c _ { 2 1 } ^ { ~ i } } & { c _ { 2 2 } ^ { ~ i } } & { \ldots } & { c _ { 2 k } ^ { ~ i } } & { \ldots } & { c _ { 2 m } ^ { ~ i } } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } & { \ddots } & { \vdots } \\ { c _ { l 1 } ^ { ~ i } } & { c _ { l 2 } ^ { ~ i } } & { \ldots } & { c _ { l k } ^ { ~ i } } & { \ldots } & { c _ { l m } ^ { ~ i } } \\ { \vdots } & { \vdots } & { \ddots } & { \vdots } & { \ddots } & { \vdots } \\ { c _ { n 1 } ^ { ~ i } } & { c _ { n 2 } ^ { ~ i } } & { \ldots } & { c _ { n k } ^ { ~ i } } & { \ldots } & { c _ { n m } ^ { ~ i } } \end{array} \right]
$$

在位置矩阵 $\ C C _ { i }$ 中如果交换机1连接到控制器k，则在位置矩阵 $C C _ { i }$ 中元素 $\scriptstyle c _ { l k } { i = 1 }$ ，否则 $\scriptstyle c _ { l k } { } ^ { i } = 0$ 。根据式（5）可知，$\begin{array} { r } { \sum _ { k = 1 } ^ { m } c _ { l k } ^ { i } = 1 , \forall l \in \left\{ 1 , 2 , 3 . . . , n \right\} \circ } \end{array}$ （20

# 2.2粒子位置更新过程

假设交换机i在第 $\mathbf { k } { + } \mathbf { l }$ 次位置更新时连接到控制器h的概率为 $P ( X _ { i h } { } ^ { k + I } = 1 )$ ，反之为 $P ( X _ { i h } { } ^ { k + I } { = } 0 )$ 。在完全随机状态下$P ( X _ { i h } { } ^ { k + l } = 1 ) = P ( X _ { i h } { } ^ { k + l } = 0 ) = 0 . 5 ,$

假定在求解过程中，pbest和gbest对最佳值的判定是相互独立的。设粒子个体最优解的信任度为 $P p$ ，全局最优解的信任度为 $P g$ 。pbest和gbest是迭代过程中的历史最佳值，因此它们发现最优值的概率应该超过平均值，即 $P p { > } 0 . 5$ ， $P g { > } 0 . 5$ ，且$P g < P p < 1$ 。

引入 $\scriptstyle a$ 和 $\beta$ 两个变量，交换机 $\textbf { \em x }$ 在第 $\mathbf { k } { + } \mathbf { l }$ 次位置更新时连接到控制器 $\mathbf { h }$ 的概率由贝叶斯公式可得

$$
\begin{array} { c } { { P ( X _ { i h } ^ { k + 1 } = 1 | p b e s t _ { i h } ^ { k } = 1 , g b e s t _ { i h } ^ { k } = 1 ) } } \\ { { = \displaystyle \frac { P _ { p } \times P _ { g } } { P _ { p } \times P _ { g } + ( 1 - P _ { P } ) \times ( 1 - P _ { g } ) } = \alpha } } \end{array}
$$

$$
\begin{array} { c l } { P ( { \cal X } _ { i h } ^ { k + 1 } = 1 | p b e s t _ { i h } ^ { k } = 0 , g b e s t _ { i h } ^ { k } = 0 ) = } & { } \\ { { } } & { { \displaystyle \frac { ( 1 - P _ { P } ) \times ( 1 - P _ { g } ) } { P _ { p } \times P _ { g } + ( 1 - P _ { P } ) \times ( 1 - P _ { g } ) } { = } { \bf l } { - } \alpha } } \end{array}
$$

$$
\begin{array} { c } { P ( \left. X _ { i h } ^ { k + 1 } = 1 \right| p b e s t _ { i h } ^ { k } = 1 , g b e s t _ { i h } ^ { k } = 0 ) } \\ { = \frac { P _ { _ P } \times ( 1 - P _ { _ g } ) } { P _ { _ p } \times P _ { _ g } + ( 1 - P _ { _ P } ) \times ( 1 - P _ { _ g } ) } { = } \beta } \end{array}
$$

$$
\begin{array} { c } { P ( \left. X _ { i h } ^ { k + 1 } = 1 \right| p b e s t _ { i h } ^ { k } = 0 , g b e s t _ { i h } ^ { k } = 1 ) } \\ { = \frac { ( 1 - P _ { p } ) \times P _ { g } } { P _ { p } \times P _ { g } + ( 1 - P _ { P } ) \times ( 1 - P _ { g } ) } { = } 1 { - } \beta } \end{array}
$$

当 $P p$ 取值为0.7， $\mathrm { \sf P g }$ 为0.8，此时 $\scriptstyle { a = 0 . 9 }$ ， $\beta { = } 0 . 7$ ，IBPSO算法可取得最佳性能[19]。因此，本文令 ${ P p = } 0 . 7$ ， ${ P g = } 0 . 8$ 。位置更新过程伪代码如下：

算法1位置更新过程

1. r=rand ();   
2. if pbest $\mathfrak { t } _ { = 1 }$ and gbest $^ \mathrm { t } { = } 1$ then   
3. if $\operatorname { r } { < a }$ then $\mathbf { X } ^ { \mathrm { t } } { = } 1$   
4. else $\mathbf { \boldsymbol { x } } ^ { \mathrm { { t } } } { = } \boldsymbol { 0 }$   
5. else   
6. if pbest $^ \mathrm { t } { = } 0$ and gbest $\scriptstyle 1 = 0$ then   
7. if r<1-α then $\mathbf { x } ^ { \mathrm { { t } } } { = } 1$   
8. else $\mathbf { \boldsymbol { x } } ^ { \mathrm { { t } } } { = } \boldsymbol { 0 }$   
9. else   
10. if pbest $^ \mathrm { t } { = } 1$ and gbest $\scriptstyle { \mathsf { \Lambda } } = 0$ then   
11. if $\mathrm { r } { < } \beta$ then $\mathbf { X } ^ { \mathrm { t } } { = } 1$   
12. else $\mathbf { \boldsymbol { x } } ^ { \mathrm { { t } } } { = } \boldsymbol { 0 }$ （204号   
13. else   
14. if $\mathrm { r } { < } 1 { - } \beta$ then $\mathbf { x } ^ { \mathrm { { t } } } { = } 1$   
15. else   
16. $\mathbf { X } ^ { \mathrm { t } } { = } 0$ （204号

# 2.3适应度函数定义

适应度函数用来评估粒子取值的好坏。本文将控制器的控制器负载均衡度作为适应度函数：

$$
Q = \frac { 1 } { m } \sum _ { j = 1 } ^ { m } ( u _ { j } - \overline { { u } } ) ^ { 2 }
$$

IBPSO算法具体流程如下：

(a)输入网络拓扑G（V,E），设置控制器最大负载阈值$\mathbf { C } ^ { \mathrm { { t h } } } { = } ( \mathsf { c } _ { 1 } , \mathsf { c } _ { 2 } , . . . \mathsf { c } _ { \mathrm { { m } } } )$ ，请求流向量 $\mathrm { F } { = } \ \left( \mathrm { f _ { 1 } , f _ { 2 } , \ldots f _ { n } } \right)$ ）。设置最大迭代次数 $\mathrm { \Delta T }$ ，设置种群大小PopSize。

(b)初始化粒子的位置 $X _ { i } { = } \{ x _ { I } , x _ { 2 } { , } { \ldots } x _ { n } \}$ 。(c)初始化每个粒子的个体最优值。(d)计算全局最优解。(e)根据位置更新公式更新粒子的位置，得到 $X _ { i + l }$ 。(f)判断粒子是否满足约束条件（d）（e）如果是则进入步骤 $( \mathrm { g ) }$ ，否则转向步骤(b)。$( \mathrm { g ) }$ 根据式（13）计算新的状态的粒子的适应度。(h)更新每个粒子的个体最优解。(i)更新粒子的全局最优解。(j)如果经过多次迭代全局最优解不再发生改变或者迭代次数大于T，算法停止，输出全局最优解；否则算法回到步骤(e)，进行下一次迭代。

# 2.4算法分析

IBPSO算法通过条件概率得到粒子取值的概率，搜索效率更高。而BPSO 算法要先计算粒子的速度，通过sigmoid 函数将 $V _ { i }$ 转变为 $x _ { i }$ 取0或者取1的概率。

IBPSO算法在位置更新的过程中根据pbest和gbest来决定位置向量 $x _ { i }$ 的取值概率。在BPSO 算法中， $x _ { i }$ 的值受到上一次迭代结果的影响，随着迭代次数的增加，BPSO算法的随机性增强。

IBPSO算法的收敛性受到 $\scriptstyle a$ 和 $\beta$ 两个变量取值的影响。其中 $\scriptstyle a$ 取值表示当个体最优解和种群最优解相同时，个体最优解和种群最优解对 $x _ { i }$ 取值的影响，而 $\beta$ 表示当个体最优解和种群最解不同时，个体最优解和种群最优解对 $x _ { i }$ 取值的影响。当$0 . 5 { < } \beta { < } \alpha { < } I$ 时IBPSO 算法的收敛性最佳，而 $\scriptstyle { a = \beta = O . S }$ 时,IBPSO算法就变成了一种随机搜索算法，算法的收敛性较差。

本文根据IBPSO 算法获得SDN控制器放置方案，从而使整个网络中的控制器处于负载均衡的状态。因此，通过仿真实验来验证本文算法的有效性。

# 3 实验仿真与结果分析

本文选用的仿真平台是MATLAB2010，并对MATLAB中的biography做修改。搭建出可以模拟真实网络环境的网络仿真平台。在进行仿真实验时采用的是Salama模型随机生成网络拓扑。本文假设拓扑中的每个节点都可以部署交换机，控制器可以部署在每个交换机的位置。本文中预先设定实验中所使用的控制器每分钟能够处理2000条packet-in 消息。为了比较本文算法的性能，从控制器数量、网络中控制器的负载均衡度以及算法的收敛性三个方面将IBPSO与BPSO算法作比较。

# 3.1控制器数量

图1显示的是在不同网络规模下，两种算法在控制器部署中对控制器数量的要求。首先先预定一个较小的值k，并逐渐增加k的大小，直到找到满足各种约束的部署方案。此时，刚好没有控制器出现超载情况。由图1可知，采用IBPSO求解的控制器个数处于一个较低的水平。对于网络规模为 $5 0 ~ \mathrm { k m }$ （fraction of topologies $_ { = 0 . 5 }$ ）的网络来说，IBPSO得到的部署方案是需要4个控制器；对于网络规模达到 $9 0 \mathrm { k m }$ （fraction oftopologies $\scriptstyle \mathsf { \Lambda } = 0 . 9$ ）的网络来说，IBPSO 需要部署8个控制器。相同条件下，BPSO算法分别需要部署6和10个控制器。

![](images/8d119133839ca4e8aec01357e69542907971c81ef449c9c7a87789ce113439e2.jpg)  
图1控制器数量

# 3.2负载均衡度

本文使用负载均衡度来度量网络中各控制器负载的差异程度。负载均衡度的大小表示网络中控制器负载差异的大小，当负载均衡度值大小，表明了控制器间负载不均衡现象严重程度。图2表示，在相同的网络环境下，本文部署相同数量的控制器，两种算法下的控制器负载均衡度的情况。实验结果表明，使用IBPSO算法得到的控制器放置方案在负载均衡上优于由BPSO算法得到的放置方案。

# 3.3 收敛性

在相同的网络拓扑下，通过设置相同的控制器个数来比较IBPSO和BPSO算法的性能。经过40次的迭代，IBPSO得到了最佳适应值，而BPSO则需要经过50次的迭代才能够达到最佳适应值。在相同的迭代次数下，IBPSO取得的适应值要优于BPSO取得的适应值。由图3可知，IBPSO算法较之BPSO 算法具有更好的收敛性。

![](images/d0701b77d9d67b80e2b3db563c69b2be3318b8b840541b6b51cab1e991007af3.jpg)  
图2负载均衡度

![](images/fa35268bee63c7b42734dd134449ef2dfc3f483273f59301f1c1dea1479bcc2a.jpg)

# 4 结束语

本文将控制器的负载作为优化变量，提出SDN控制器部署优化模型，并将改进的二进制粒子群优化算法用于求解优化模型。IBPSO算法通过条件概率直接决定粒子粒子取值的概率，解决了BPSO求解过程中参考上一次迭代中 $x _ { i }$ 的值而陷于局部最优的问题，具有更好的收敛性。同时仿真实验结果表明，使用IBPSO算法能够有效的减少控制器部署个数，实现控制器负载的均匀分配。

# 参考文献：

[1]Kreutz D,Ramos F M V,Esteves Verissimo P,et al.Software-defined networking:a comprehensive survey [J].Proceedings of the IEEE,2014, 103 (1): 10-13.   
[2]Gude N,Koponen T,Petit J,et al. NOX: towards an operating system for networks [J].ACM Sigcomm Computer Communication Review,2008,38 (3): 105-110.   
[3]Erickson D.The beacon openflow controller [C]// Proc of ACM SIGCOMMHOTSDN.New York:ACMPress,2013:13-18.   
[4] Floodlight [EB/OL].[2013-12-29]. htp://www. projectfloo-dlight.org.   
[5]Koponen T,Casado M,Gude N,et al. Onix: a distributed control platform forlarge-scale production networks [Cl// Proc of the 9th USENIX Conference Symposium on Operating Systems Design and Implementation. Berkeley:USENIX Association,2010:351-364.   
[6]Tootoonchian A,Ganjali Y.HyperFlow:a distributed control plane for OpenFlow [C]// Proc of Internet Network Management Conference on Research on Enterprise Networking.Berkeley: USENIX Association,2010.   
[7]Yeganeh S H, Ganjali Y. Kandoo: a framework for efficient and scalable offloading of control applications [Cl// Proc of the 1st Workshop on Hot Topics in Software Defined Networks.New York:ACM Press,2012: 19-24.   
[8]Heller B,Sherwood R,Mckeown N.The controller placement problem [C]//Proc of ACM SIGCOMM HOTSDN.New York:ACM Press,2012: 19-24.   
[9]Liao Jianxin,Sun Haifeng，Wang Jingyu,et al.Density cluster based approach for controller placement problem in large-scale software defined networkings [J]. Computer Networks,2017,112: 24-35.   
[10]Muller LF,Oliveira RR,Luizelli M C,et al.Survivor:an enhanced controller placement strategy for improving SDN survivability [Cl// Proc of Global Communications Confere-nce.[S.1.]:IEEE Press,2014: 1909-1915.   
[11] Jimenez Y, Cervello-Pastor C,Garcia A J. On the controller placement for designing a distributed SDN control layer [Cl// Proc of Networking Conference.[S.1.] : IEEE Press,2014:1-9.   
[12] Wang Guodong,Zhao Yanxiao,Huang Jun,et al.The controller placement problem in software defined networking: a survey [J]. IEEE Network,2017, 31 (5): 21-27.   
[13] Han Lin,Li Zhiyang,Liu Weijiang,et al.Minimum control latency of SDN controller placement [C]// Proc of Trustcom//Bigdatase//spa.[S.1.] : IEEE Press,2017: 2175-2180.   
[14] Tanha M,Sajjadi D,Pan J.Enduring node failures through resilient controller placement for software defined networks [C]// Proc of Global Communications Conference.[S.l.]:IEEE Press,2017.   
[15] Sallahi A,St-Hilaire M. Expansion model for the controller placement problem in software defined networks [J]. IEEE Communications Letters, 2016,PP (99): 1.   
[16] Zhang Bang，Wang Xingwei,Ma Lianbo,et al.Optimal controller placement problem in Internet-oriented software defined network [C]// Proc of International Conference on Cyber-Enabled Distributed Computing and Knowledge Discovery. 2017: 481-488.   
[17] Mckeown N,Anderson T,Balakrishnan H,et al.OpenFlow:enabling innovation in campus networks [C]// Proc of ACM Sigcomm Computer Communication Review.New York: ACMPress,2008: 69-74.   
[18]刘建华，杨荣华，孙水华．离散二进制粒子群算法分析[J]．南京大学 学报：自然科学版,2011(5): 504-514.(Liu Jianhua,Yang Ronghua,Liu Shuihua. The analysis of binary particle swarm optimization [J].Journal of Nanjing University: Nat Sci Ed,2011 (5): 504-514.)   
[19]徐义春，肖人彬．一种改进的二进制粒子群算法[J].模式识别与人工 智能，2007,20 (6):788-793.(Xu Yichun,Xiao Renbin.An improved binary swarm optimizer [J].Pattrn Recognition and Artificial Intelligence, 2007,20 (6): 788-793.)