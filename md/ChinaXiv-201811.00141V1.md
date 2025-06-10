# Adhoc云中基于移动预测的多准则任务卸载算法

田广东，葛东玉

(重庆邮电大学 通信与信息工程学院，重庆 400065)

摘要：为了提升Adhoc云中任务卸载的效率，针对节点随机移动性及资源异构性对任务卸载的影响，提出一种基于移动预测的多准则任务卸载算法，根据时间序列分析预测节点逃离时间，并将其作为节点移动性衡量指标。运用层次分析法得到CPU速度、核心数、负载及移动性的权重，最后根据任务大小及计算得到的组合权重进行任务卸载，仿真结果表明，相比于随机任务分配算法和Min-Min调度算法，该算法能够有效降低任务执行时间和能量消耗。

关键词：Adhoc云；多准则；任务卸载；时间序列分析；层次分析法中图分类号：TN92 doi:10.19734/j.issn.1001-3695.2018.07.0468

# Multi criteria task offloading algorithm in Ad hoc cloud based on mobility prediction

Tian Guangdong, Ge Dongyu (School ofCommunication&Information Engineering,Chongqing Universityof Posts&Telecommunication,Chongqing 400065, China)

Abstract:Inordertoimprove theeficiencyoftaskoffloainginAdhoccloud,aimingat theefectofnoderandommovement andresourceheterogeneityontaskofloading,this paperproposes the multicriteriataskofloadingalgorithmbasedonmobility prediction,whichisused to predict node escaping time basedon time series analysis andasa measure ofmobility.Byusing the analytic hierarchyprocesstogetthe weightsofCPUspeed,numberofcores,workloadand mobility,thetaskisoffloaded according totask sizeandthecombined weights which has been calculated,the simulationresults showthatthe algorithmcan reducethe task execution timeand energyconsumption effectivelycompared with therandom task assignment algorithm and Min-Min scheduling algorithm.

Key words: Ad hoc cloud; multi criteria; task offloading; time series analysis; analytic hierarchy process

# 0 引言

随着智能设备的迅速普及，越来越多需要密集计算资源且高能耗的移动应用程序被开发应用，并受到广泛关注[I]。尽管近年来智能设备的性能得到了很大提升，但仍不能满足用户在大数据时代爆炸式的数据处理需求。因此，移动云计算[2]（mobilecloudcomputing，MCC）逐渐成为解决智能设备资源受限的主要技术。MCC 为智能设备提供了高效的远程计算服务，移动用户通过MCC将计算密集型的任务卸载到远程云或本地小型云设备[3]处理，完成后再将计算结果返回，以此降低任务在本地处理的开销，缓解移动设备的资源遗乏问题。远程云虽然计算能力强，但会带来延迟和开销较高的问题；本地小型云计算能力强且通信带宽大，但却无法保证用户随时随地接入；而Adhoc云[4作为无基础设施下MCC的一种扩展，可以通过与附近的移动设备共享其闲置资源进行任务卸载[5]，具有部署快速且扩展灵活等优点。

为实现高效的任务卸载，现有研究为MCC设计了各种协议与机制，而对于Adhoc云的研究仍处于起步阶段，为解决计算密集型应用卸载问题，文献[6]提出了一种在线批调度启发式方法，动态地选择移动设备进行任务卸载。文献[7]提出了一种用于异构移动云的通用卸载框架，它使用移动设备、附近的小型云和远程云来提高MCC服务的性能和可用性。然而，所提出的框架并没有充分考虑Adhoc云的特性。

为了满足移动设备的延迟限制，文献[8]提出了一种节能任务调度方案，并针对不同的任务，设计了一种自适应概率调度器，不仅能满足延迟约束，而且能在执行计算密集型实时应用程序时最小化能耗，但其计算复杂度较高。为降低能耗和计算成本，文献[9]提出了一种基于微云辅助的任务分配机制，制定了一个两阶段 Stackelberg 博弈来确定 slave 节点提供的执行单元数量，而master节点将以此确定补偿策略，但是该机制在任务分配时并未考虑可用移动设备的资源异构性。

上述方法虽然能够在一定程度上降低任务执行的时间或能耗，但是均未充分考虑Adhoc云中节点的随机移动性和资源异构特性对任务卸载的影响。虽然影响任务卸载的因素众多，而作为Adhoc网络最基本的特性，节点的随机移动性和异构性无疑是影响Adhoc云中任务卸载的最重要因素，如何选择合适的节点及合理地分配资源成为亟待解决的问题。针对于上述问题，本文提出了一种基于移动预测的多准则任务卸载算法，充分考虑Adhoc云中节点的随机移动性和资源异构性，提高任务卸载效率。

# 1 系统模型

为了不失一般性，假设在Adhoc云中有 $M + 1$ 个节点，其中的一个节点（master）有一组待处理的计算密集型任务 $W$ ，如果只依靠自身资源来完成这些任务很可能会耗尽自身资源或带来较高的延迟，十分影响用户体验。而其他 $M$ 个节点（slave）则具备较为丰富的闲置资源，在一定范围内master节点可以通过优质的无线网络（Wi-Fi）将任务卸载到slave节点，任务完成后再将结果返回，从而实现自身资源的扩展。

本文主要考虑节点的移动性和异构性，暂不考虑节点间通信成本。为了实现多任务同时执行，假设master节点根据处理器时隙进行任务分配，则第 $i$ 个任务的执行时间可表示为

$$
T _ { i } = { \sum _ { s = 1 } ^ { i } t _ { s } } = \sum _ { s = 1 } ^ { i } ( \frac { W _ { i } } { S \times C } + \frac { D _ { i } } { S \times C } )
$$

即第 $i$ 个任务的执行时间为其执行期间所有时隙的和，其中第一个时隙的大小取决于该时隙内执行任务的数量和最小任务的大小，而剩余时隙的大小取决于该时隙内当前执行任务和下一个较小任务大小的差异，即

$$
t _ { i } = \left\{ \begin{array} { c c } { \left( \operatorname* { m i n } ( W ) \times N \right) / \left( S \times C \right) } & { i = 1 } \\ { \left( W _ { i } - W _ { i - 1 } \right) \times \left( N - \left( i + 1 \right) \right) / \left( S \times C \right) } & { i > 1 } \end{array} \right.
$$

其中: $s$ 和 $C$ 分别为节点CPU速度和核心数， $D _ { i }$ 为第 $i$ 个任务执行时节点原有负载。

# 2 多准则任务卸载算法

节点的移动性和异构性作为Adhoc网络最基本的特性，对Adhoc云中高效的任务卸载有着重要影响，高效的任务卸载能显著降低任务执行时间和能量消耗，提升用户体验。本文综合考虑Adhoc云中节点的移动性与资源异构性，提出一种高效的任务卸载算法，能够有效降低任务执行时间与能量消耗。

# 2.1移动预测

在Adhoc网络中，节点移动性的量化通常表示为相对移动速度，根据连续两次收到的信号强度差异确定节点移动速度，即

$$
\nu _ { i } = \lg { \frac { P _ { r 2 } } { P _ { r 1 } } }
$$

其中: $P _ { r 1 }$ 和 $P _ { r 2 }$ 分别为连续两次接收的信号功率。显然，若$\nu _ { \scriptscriptstyle i } > 0$ ，则认为节点在靠近，移动性相对较好；反之则认为其移动性较差。这种方法虽然计算简单，但实际网络中节点的能量会随着网络的运行而降低，并且信号接收功率很容易受噪声影响，存在较大误差。

而根据时间序列分析[10]可以较为准确地预测Adhoc 网络中节点的位置信息。任何实际的Adhoc网络都是需要完成某些具体任务的，因此，节点的运动不会是完全杂乱无章的。如果将节点的移动坐标信息采样为离散时间序列，则可以利用时间序列进行建模和预测，使节点能够预测其他节点在未来一段时间内的位置信息，在一定程度可以减少网络的开销，提升资源利用率。

预测问题是随机过程领域的基本问题，针对时间序列的预测，指的是在 $t$ 时刻对未来第 $\mathbf { \xi } _ { l }$ 步的取值 $x _ { t + l }$ 进行预测，获得预测值 $x _ { t } ( l )$ 。研究表明，一个平稳的时间序列总可以表示成一系列白噪声 $\left\{ A _ { t } \right\}$ 的线性组合，即

$$
x _ { t } = \sum _ { j = 0 } ^ { \infty } G _ { j } a _ { t - j }
$$

令 $t = t + l$ 并展开得：

$$
\begin{array} { r } { x _ { t + l } = ( G _ { 0 } a _ { t + l } + G _ { 1 } a _ { t + l - 1 } + \cdots + G _ { l - 1 } a _ { t + 1 } ) } \\ { + ( G _ { l } a _ { t } + G _ { l + 1 } a _ { t - 1 } + \cdots G _ { l + t - 1 } a _ { 1 } ) } \end{array}
$$

其中，对于右边第一部分，由于 $\left\{ A _ { t } \right\}$ 是白噪声，因而在 $t$ 时刻无法预测未来 $l$ 时间段内的序列值，即这一部分是无法计算的，可视为第 $\mathbf { \xi } _ { l }$ 步的预测误差 $e _ { t } ( l )$ 。对于第二部分，由于在 $t$ 时刻，所有的序列值 $a _ { t } , a _ { t - 1 } , . . . , a _ { 1 }$ 都已确定，因此是可以计算的，可视为第 $l$ 步的预测值 $x _ { t } ( l )$ ，则式(5)可记为

$$
x _ { t + l } = e _ { t } ( l ) + x _ { t } ( l )
$$

由于 $x _ { t } ( l )$ 包含了所有可计算的项，因此可以认为预测误差$e _ { t } ( l )$ 的方差达到最小。设白噪声 $\left\{ A _ { t } \right\}$ 的方差为 $\boldsymbol { \sigma } _ { a } ^ { 2 }$ ，则 $e _ { t } ( l )$ 的方差为

$$
V a r [ e _ { t } ( l ) ] = \sum _ { j = 0 } ^ { l - 1 } G _ { j } ^ { 2 } V a r [ a _ { t + l - j } ] = \sigma _ { a } ^ { 2 } \sum _ { j = 0 } ^ { l - 1 } G _ { j } ^ { 2 }
$$

在几何上可以证明 $x _ { t } ( l )$ 为向量 $x _ { t + l }$ 在无限维上的正交投影，此时， $e _ { t } ( l )$ 为最小，即 $x _ { t + l }$ 完全回归于 $x _ { t } ( l )$ 。这就是使预测误差的方差为最小意义下的最优预测，即最小均方误差预测。

针对随机时间序列建模时，为确保可靠性，通常要求时间序列具有平稳性、正态性、零均值性等统计特性。因此，在获得样本序列后，首先需要检验该序列是否满足这些特性。如果不满足，则需要通过预处理得到满足要求的时间序列。

序列的平稳性检验可采用参数型检验法或非参数型检验法。对于非平稳时间序列，通常可采用多次差分的方式进行平稳化，并且只需在后续处理过程结束后进行恢复即可；正态性检验，也称为纯随机性检验。纯随机序列，即服从正态分布的白噪声，在统计学中被认为是不具有任何分析价值的。在平稳性检验后，还需要检验正态性，确保该过程对应的时间序列具有进一步分析、预测的价值。对于一个具有实际价值的Adhoc网络，其节点的移动总是为了完成某种特定任务。因此，节点的坐标序列不会是纯随机序列，可省略正态性检验的过程；零均值检验是检验时间序列所描述的随机过程均值是否为零。这里，时间序列描述的是节点的坐标，难以保证移动的节点坐标均值为零，因此需要对原始序列进行零化处理。

样本序列经过预处理后，就可以进行模型选择了。在时序分析预测领域，最常用的一组模型是 ARMA(Auto RegressiveMovingAverage Model)模型，这也是当前时序分析中效果最佳的一组预测模型。

模型选定之后还要进行参数估计和模型检验，ARMA模型的参数估计方法大致上可以分为三类：第一类是基于时序理论本身所发展的参数估计法，第二类是基于优化理论迭代运算的优化参数估计法，第三类是基于控制理论中差分模型的参数估计法。这里主要使用第三类方法中的广义最小二乘估计。ARMA的建模过程是一个动态修正的过程，在完成参数估计后，需要检验模型的有效性。理论上，ARMA模型成立的根本条件是$\{ a _ { t } \}$ 为白噪声，因此，实际使用的模型检验方法都是围绕这一点展开的。

根据以上步骤，结合具体的Adhoc网络节点移动场景，给出预测流程：

a)初始化全局参数；b)对节点的位置信息采样，得到样本序列；c)判断序列是否平稳，若是则进行下一步，否则进行差分处理后再执行步骤c);d)选择合适的时间序列预测模型；e)根据选择的预测模型进行参数估计；f)模型检验，判断预测误差是否为白噪声，若是则进行下一步，否则返回步骤d);

g)根据以上步骤进行最后的最小均方误差预测并输出结果。

如前所述，在实际的Adhoc 网络中，不会存在运动完全杂乱无章的节点。因此根据时间序列预测，基于节点的历史位置坐标，可以估算出其下一时刻的速度，再结合预测出的下一时刻位置坐标，可以估计各节点逃离master节点通信范围所需的时间 $T _ { i } ^ { p r e }$ 。显然， $T _ { i } ^ { p r e }$ 越大，任务执行成功的概率就越高，移动性越好。假设节点在某时刻的移动轨迹如图1所示，以master节点坐标为圆心、通信距离 $R$ 为半径构造其通信范围，图中 $x _ { i }$ 和 $y _ { i }$ 为节点位置坐标， $\nu _ { _ { x } }$ 和 $\nu _ { y }$ 分别为当前速度的水平和垂直分量。

则下一时刻节点的坐标为

$$
x _ { t } = \frac { - k ( y _ { i } - k x _ { i } ) \pm \sqrt { ( 1 + k ^ { 2 } ) R ^ { 2 } - { ( k x _ { i } - y _ { i } ) } ^ { 2 } } } { 1 + k ^ { 2 } }
$$

$$
y _ { t } = k ( x _ { t } - x _ { i } ) + y _ { i }
$$

其中 $k = \nu _ { _ y } / \nu _ { _ x }$ ，因此可以计算出 $T _ { i } ^ { p r e }$ 为

$$
T _ { i } ^ { p r e } = \frac { \sqrt { ( x _ { i } - x _ { t } ) ^ { 2 } + ( y _ { i } - y _ { t } ) ^ { 2 } } } { \sqrt { \nu _ { x } ^ { 2 } + \nu _ { y } ^ { 2 } } }
$$

![](images/ca35fc5b0d133374a5ea0c0f888d36936fa24b076d4b38876e3ea2fb02e6af40.jpg)  
图1节点移动轨迹示意图  
Fig.1Node moving trajectory chart

# 2.2权重确定

影响任务执行的异构因素主要有CPU速度、核心数及负载，根据以上因素和节点的移动性构造权值公式为

$$
f _ { i } = \omega _ { 1 } d _ { i } + \omega _ { 2 } s _ { i } + \omega _ { 3 } c _ { i } + \omega _ { 4 } t _ { i }
$$

$$
\omega _ { 1 } + \omega _ { 2 } + \omega _ { 3 } + \omega _ { 4 } = 1
$$

其中: $\omega _ { \mathrm { { l } } }$ ， $\omega _ { 2 }$ ， $\omega _ { 3 }$ ， $\omega _ { 4 } \in ( 0 , 1 )$ 为权值因子； $s _ { i } \ 、 \ c _ { i }$ 、 $d _ { i }$ 和 $t _ { i }$ 分别表示节点CPU速度、核心数、剩余空闲负载和逃离时间。

本文采用层次分析法[1确定权值因子，层次分析法是美国运筹学家Saaty教授提出的一种简便、灵活而又方便使用的多准则决策方法。该方法中各项比例标度及其意义如表1所示。

Table1Importance scale and their definitions   

<html><body><table><tr><td>标度值</td><td>意义</td></tr><tr><td>1</td><td>两因素同等重要</td></tr><tr><td>3</td><td>一个因素稍微重要</td></tr><tr><td>5</td><td>一个因素明显重要</td></tr><tr><td>7</td><td>一个因素强烈重要</td></tr><tr><td>9</td><td>一个因素极端重要</td></tr><tr><td>2,4,6,8</td><td>为上述相邻判断的中值</td></tr></table></body></html>

多数公有云服务提供商都能为用户提供无限的资源，而在Adhoc云中，可用资源高度依赖于节点数量及其硬件规格，节点的移动性则是另一个需要考虑用于任务卸载决策的因素，更接近的节点，往往可以被认为更适合任务卸载[12]，各因素对比情况如表2所示，其中节点的移动性可以用得到的预测逃离时间作为衡量指标，并且表中数据可根据实际情况作出相应调整。

表1标度值及其意义  
表2各因素两两对比情况  
Table 2Various factors comparison levels   

<html><body><table><tr><td>因素</td><td>CPU速度</td><td>核心数</td><td>负载</td><td>移动性</td></tr><tr><td>CPU速度</td><td>1</td><td>1</td><td>1/4</td><td>5</td></tr><tr><td>核心数</td><td>1</td><td>1</td><td>1/3</td><td>5</td></tr><tr><td>负载</td><td>4</td><td>3</td><td>1</td><td>7</td></tr><tr><td>移动性</td><td>1/5</td><td>1/5</td><td>1/7</td><td>1</td></tr></table></body></html>

根据表2可以得到判断矩阵为

$$
A = { \left( \begin{array} { l l l l } { 1 } & { 1 } & { 1 / 4 } & { 5 } \\ { 1 } & { 1 } & { 1 / 3 } & { 5 } \\ { 4 } & { 3 } & { 1 } & { 7 } \\ { 1 / 5 } & { 1 / 5 } & { 1 / 7 } & { 1 } \end{array} \right) }
$$

对该矩阵归一化处理后，通过计算得到各权值因子分别为$\omega _ { 1 } = 0 . 5 4 8 \ , \omega _ { 2 } = 0 . 1 9 4 \ , \omega _ { 3 } = 0 . 2 0 6 \ , \omega _ { 4 } = 0 . 0 6 2$ 。

# 2.3算法描述

如前所述，影响任务卸载的因素主要有节点CPU速度、核心数、负载及移动性，综合考虑以上因素，结合时间序列分析与层次分析法提出一种多准则任务卸载算法，描述如下：

算法1基于移动预测的多准则任务卸载算法

$\mathbb { N P U T } : N , S _ { N } , W , C _ { N } , P _ { N } , C P I , R _ { T } , \mathbf { R } _ { \mathrm {_ N } } , T _ { N } ^ { p r e }$   
$1 X  W$   
2 Sort(Descend, $X$ ）   
$\begin{array} { r l } & { 3 \ \forall _ { n = 1 \ldots N } E _ { t L } ^ { n } = 0 \mathrm { f o r i } = 1 \colon \big | X \big | \mathrm { d o } } \\ & { 4 \ \forall n \in N m a p < X _ { i } , E _ { L } ^ { n } >  \frac { \big | X _ { i } \big | \times C P I _ { n } / S _ { n } } { R _ { X _ { i } ^ { n } } } \times 1 0 0 } \end{array}$   
5 end   
$\begin{array} { r l } & { 6 \ \forall n \in N , \mathbf { R } _ { \mathfrak { n } } = P _ { \mathfrak { n } } - E _ { t L } ^ { n } } \\ & { 7 \ \mathrm { w h i l e } ( | X | ! = \operatorname { N U L L } ) } \\ & { 8 \ ( \hat { d } _ { \mathfrak { n } } , s _ { \mathfrak { n } } , \hat { c } _ { \mathfrak { n } } , \hat { t } _ { \mathfrak { n } } ) = { \arg \operatorname* { m a x } { \mathfrak { f } } } \left( d _ { \mathfrak { n } } , s _ { \mathfrak { n } } , c _ { \mathfrak { n } } , t _ { \mathfrak { n } } \right) } \\ & { \qquad \forall n \in N , d _ { \mathfrak { n } } \in \mathbf { R } _ { \mathrm { N } } , c _ { \mathfrak { n } } \in C _ { N } , t _ { \mathfrak { n } } \in T _ { N } } \\ & { 9 \ \mathrm { f } ( d _ { \mathfrak { n } } , s _ { \mathfrak { n } } , c _ { \mathfrak { n } } , t _ { \mathfrak { n } } ) \gets \omega _ { \mathfrak { n } } d _ { \mathfrak { n } } + \omega _ { 2 } s _ { \mathfrak { n } } + \omega _ { 3 } c _ { \mathfrak { n } } + \omega _ { 4 } t _ { \mathfrak { n } } } \end{array}$   
$1 0 N o d e I D \gets g e t I D ( N , \hat { d } _ { n } , \hat { s } _ { n } , \hat { c } _ { n } , \hat { t } _ { n } )$   
$1 1 m a p < N o d e I D >  x _ { 1 }$ where $x _ { 1 } \in X$   
$1 2 E _ { t L } ^ { n }  E _ { t L } ^ { n } + E _ { L } ^ { n }$   
$1 3 X  X / x _ { 1 }$   
14 end   
15OUTPUT: $m a p < N , X >$

其中: $N$ 为节点数量， $S _ { \scriptscriptstyle { N } }$ 为节点CPU速度， $W$ 为待卸载任务，$C _ { N }$ 为节点CPU核心数， $P _ { N }$ 为节点最大负载， $C P I$ 为每条指令执行时CPU所花费的平均时钟周期数， $R _ { T }$ 为任务实际执行时间， $\scriptstyle \mathbf { R } _ { \mathrm { N } }$ 为节点的剩余空闲负载， $T _ { N } ^ { p r e }$ 为节点的预测逃离时间， $\boldsymbol { E } _ { t L } ^ { n }$ 为节点预计执行任务时负载，上标^表示arg函数的最大返回值。执行步骤如下：

a)master节点通过周期性地广播“hello”报文发布任务卸 载请求;

b)在通信范围内的节点根据自身状态选择是否接受任务，若接受则向master节点发送“hello”报文，报文携带的信息包括自身CPU速度、核心数、负载及位置信息；

c)master节点根据任务大小将待卸载任务降序排列;

d收集各节点提供的信息并根据位置信息计算其逃离时间；e)根据式(11)和计算出的权值因子计算出各节点的组合权

重；

f)将计算得到的组合权重值按照降序排列；

g)将任务列表中的任务按照对应关系分配给具有相应权重的节点;

h)判断任务完成情况，已完成任务移出列表，未完成任务重新分配；

i)不断重复以上步骤，直至任务列表为空或节点列表为空。

# 3 仿真与分析

本文通过MATLAB 将所提WCST 算法（即Workload,Cores，Speed，Time）与随机任务分配算法（RM）及Min-Min调度算法[13]进行仿真对比。随机任务分配算法是将任务完全随机地分配给可用节点，而Min-Min调度算法则是网格计算中经典的任务调度算法，该算法首先找到全部任务的最小执行时间，然后在所有任务中选择具有最小执行时间的任务。算法通过将任务分配给能得到最小完成时间的资源而进行，重复相同的过程，直到全部任务都被调度完成。Min-Min 算法的局限性在于它优先选择较小的任务进行调度，使用了具有很高计算能力的资源，其结果是，当较小任务的数量超过较大任务的数量时，调度结果不会最佳，并且往往不能实现负载均衡。

仿真场景中选择Adhoc网络中应用最广泛的随机点移动模型，节点数设置为4，对应CPU分别为四核1300MIPS、单核1008MIPS、双核1600MIPS 和八核1200MIPS（MillionInstructionsPerSecond，表示CPU每秒处理的百万级的机器语言指令数)，待卸载任务设置如表3所示，其中每个任务分为五个子任务，通过六个任务的完成情况来验证所提算法的有效性，衡量指标为任务执行时间和能量消耗。

表3任务大小设置情况  
Table 3Task size setup situation   

<html><body><table><tr><td>Task ID</td><td colspan="4">子任务大小 （指令数，单位：1.0e+11）</td></tr><tr><td>1</td><td>0.0026</td><td>0.0452</td><td>0.2339 0.7392</td><td>1.1712</td><td></td></tr><tr><td>2</td><td>0.0018</td><td>0.0448</td><td>0.2366</td><td>0.7323</td><td>1.1190</td></tr><tr><td>3</td><td>0.0029</td><td>0.0438</td><td>0.2314</td><td>0.7321</td><td>1.2575</td></tr><tr><td>4</td><td>0.0016</td><td>0.0440</td><td>0.2347</td><td>0.7302</td><td>1.3371</td></tr><tr><td>5</td><td>0.0027</td><td>0.0438</td><td>0.2400</td><td>0.7311</td><td>1.4427</td></tr><tr><td>6</td><td>0.0028</td><td>0.0444</td><td>0.2335</td><td>0.7372</td><td>1.4018</td></tr></table></body></html>

任务执行时间是影响用户体验最重要的因素，图2是RM算法、Min-Min算法以及WCST算法分别完成六个任务的执行时间对比图，从图中可以看出相比于RM算法，WCST算法可以明显减少任务的执行时间，这是因为RM算法在任务分配时是完全随机的，而WCST算法充分考虑设备的异构性（CPU速度、核心数及负载）和移动性，根据各因素的权重组合进行任务分配，保证了任务执行成功的可能，从而实现了高效的任务卸载。而相比于Min-Min 算法，WCST 算法在任务1和任务2上消耗了稍长的执行时间，这是因为任务1和任务2较小，因此会被Min-Min算法优先调度并使用具有较强计算能力的资源而其余任务则依然是WCST算法更能有效降低任务执行时间，并且相比于RM算法和Min-Min算法，WCST算法可以通过更合理的任务分配有效均衡各个任务的执行时间。

![](images/62720665f9c703be2fd9e761cc025ab9041c00912873267b165f0d9f2cbf7506.jpg)  
图2任务执行时间对比图

能量消耗是影响用户体验的另一重要因素，图3是RM算法、Min-Min算法以及WCST算法分别执行六个任务的能耗对比图。从图中可以看出，相比于RM算法，WCST算法能有效降低任务执行的能量消耗，这是因为当智能设备的负载过高或是CPU性能不佳时，执行计算密集的任务不仅效率低而且会消耗较多能量，WCST算法充分考虑了这些因素，从而能够实现更高效的任务卸载，并且相比于Min-Min算法，WCST算法也能在一定程度上降低能耗并实现负载均衡。

![](images/92611e29767db34bc0d2ac1cdf51be3a6a868c815d7c7300d4d4b7fa85997199.jpg)  
Fig.2Task execution time comparison chart   
图3任务执行能耗对比  
Fig.3Task execution energy consumption comparison chart

鉴于算法中存在大量参数，如CPU速度、核心数、负载及节点预测逃离时间等，下面着重针对负载及预测逃离时间增加实验以验证算法中主要参数对任务卸载效率的影响。首先在所提WCST算法中去除负载这一因素进行仿真实验，限于篇幅，这里只以任务执行时间作为衡量指标，得到结果如图4所示。

之后再针对移动性对任务卸载的影响进行仿真实验，同样在原有算法基础上去除预测逃离时间这一因素，得到结果如图5所示。

如图4和5所示，在原有算法基础上去除负载因素后，相比于原有算法，任务执行时间显著增加，在去除预测逃离时间因素之后，任务执行时间也有些许增加。这说明算法中的各个因素都直接影响着任务执行的效率，并且权重越大的因素对任

务执行效率的影响越大。

![](images/ceb734a016b73732b4ffbe9c2031080f49b9d3f5233a098a47b5c0698d23a3ff.jpg)  
图4任务执行时间对比图

![](images/af6401412700e7c489adf5a88cff93a41e62a93b3a942a31372b55187242c868.jpg)  
Fig.4Task execution time comparison chart  
图5任务执行时间对比图  
Fig.5Task execution time comparison chart

# 4 结束语

Adhoc云作为移动云计算在无预设基础设施下的一种扩展，具有广阔的应用前景，但Adhoc网络中节点的随机移动性和异构性是影响其应用的重要因素。本文针对Adhoc云中节点移动性和异构性对任务卸载的影响，提出一种基于移动预测的多准则任务卸载算法，根据时间序列分析预测节点逃离时间并将其作为移动性衡量指标，充分考虑节点的异构特性，运用层次分析法得到各因素权重，最后根据得到的组合权重进行任务卸载。仿真结果表明，相比于随机任务分配算法和Min-Min算法，所提算法虽然复杂度稍高，但能有效降低任务执行时间和能量消耗，提升用户体验。

# 参考文献：

[1]Muraleedharan R.Cloud-vision: real-time face recognition using a mobilecloudlet-cloudaccelerationarchitecture[C]//Computers and Communications.Piscataway,NJ:IEEE Press,2012:00o059-000066.   
[2]Dinhi H T,Lee C,Niyato D,et al.A survey of mobile cloud computing: architecture,applications,and approaches [J].Wireless Communications & Mobile Computing,2013,13 (18): 1587-1611.   
[3]Liu Yanchen,Lee M, ZhengYanyan.Adaptive multi-resource allocation for cloudlet-Based mobile cloud computing system [J].IEEE Trans on Mobile Computing,2016,15 (10):2398-2410.   
[4]Yaqoob I,Ahmed E,Gani A,et al.Mobile Ad hoc cloud: A survey [J]. Wireless Communications& Mobile Computing,2016,16(16): 2572-2589.   
[5]Zhou Bowen,Dastjerdi A V,Calheiros R N,et al.A context sensitive offloading scheme for mobile cloud computing service [C]// Proc of IEEE, International Conference on Cloud Computing.New York,USA: IEEE Press, 2015: 869-876.   
[6]Li Bo,Pei Yijian,Wu Hao,et al.Heuristics to allocate high-performance cloudlets for computation offloading in mobile Ad hoc clouds [J].Journal of Supercomputing,2015,71(8):3009-3036.   
[7]Zhou Bowen,Dastjerdi AV,Calheiros R,et al.mCloud:A context-aware offloading framework for heterogeneous mobile cloud [J].IEEE Trans on Services Computing,2017,PP(99): 1-1.   
[8]Shi Ting,Yang Mei,Li Xiang,et al.An energy-efficient scheduling scheme for time-constrained tasks in local mobile clouds [J].Pervasive & Mobile Computing,2016,27(C): 90-105.   
[9]Guo Xijuan,Liu Liqing,Chang Zheng,et al.Data offloading and task allocation for cloudlet-assisted Ad hoc mobile clouds [J].Wireless Networks, 2018:1-10.   
[10]Rojas I,Pomares H. Time series analysis and forecasting[J].Contributions to Statistics,2016.   
[11] Sun Lu.A min-max optimization approach for weight determination in analytic hierarchy process[J]．东南大学学报(英文版),2012,28(2).   
[12] Azar H,Majma M R.Using a multi criteria decision making model for managing computational resources at mobile ad-hoc cloud computing environment [C]//Proc of International Conference on Engineering and Technology.Piscataway,NJ: IEEE Press,2017:1-5.   
[13]Patel G,MehtaR,BhoiU,et al.Enhanced load balanced Min-min algorithm for static meta task scheduling in cloud computing[J].Procedia Computer Science,2015:545-553.