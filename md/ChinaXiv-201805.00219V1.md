# 云计算环境中面向DAG任务的多目标调度算法

徐健锐‘²，朱会娟³

(1.江苏大学 计算机科学与通信工程学院，江苏 镇江 212013;2.江苏联合职业技术学院 镇江分院，江苏 镇江212016;3．中国科学院大学 计算机与控制学院，北京100049)

摘要：为了实现任务执行效率与执行代价的同步优化，提出了一种云计算环境中的DAG任务多目标调度优化算法。算法将多目标最优化问题以满足Pareto最优的均衡最优解集合的形式进行建模，以启发式方式对模型进行求解；同时，为了衡量多目标均衡解的质量，设计了基于hypervolume 方法的评估机制，从而可以得到相互冲突目标间的均衡调度解。通过配置云环境与三种人工合成工作流和两种现实科学工作流的仿真实验测试，结果表明，比较同类单目标算法和多目标启发式算法，算法不仅求解质量更高，而且解的均衡度更好，更加符合现实云的资源使用特征与工作流调度模式。

关键词：云计算；工作流调度；多目标优化；Pareto 边界；亚马逊弹性计算云中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2017.07.0683

# Multi-objective scheduling algorithm of DAG tasks in cloud computing

Xu Jianrui1,², Zhu Huijuan3 (1.SchoolofComputerScience&Telecommunication EngineeringJiangsu University,ZhenjiangJiangsu 120l3,China;2. Zhenjiang Branch Jiangsu Union Technical Institute,Zhenjiang Jiangsu 2120l6,China;3.SchoolofComputer&Control Engineering, University of Chinese Academy of Sciences,Beijing 10oo49,China)

Abstract:Forimplementingthesynchronizationoptimizationoftasks executioneficiencyand executioncost,amulti-objective scheduling optimization algorithm ofDAG tasks incloud environment is presented.Our algorithmdefines the multi-objective optimization problemas the trade-ofoptimal solutions set satisfying Paretooptimal and solves this model bythe heuristic method.At thesame time,for evaluating thequalityof multi-objective trade-offsolutions,aevaluation mechanism basedon hypervolume methodisdesigned,whichcanobtain the trade-off scheduling solutions withconflictobjectives.Throughseting cloud environmentand three kinds ofsynthetic workflow andtwo kinds ofreal-world scientific workflow,weconstruct some simulation experiments.Theresults show that,compared with thesame typeof single objective algorithmand multi-objective heuristic algorithm,our algorithmnotonlyhashighersolvingquality,buthas beter trade-offdegreeofsolutions,whichcan conform to the mode of resource utility and workflow scheduling in real-world cloud.

Key Words: cloud computing; workflow scheduling; multi-objective optimization; Pareto front; Amazon EC2

# 0 引言

科学领域的实验任务通常定义为工作流形式，其任务根据数据流与计算相关性形成链式结构，如计算密集型和数据密集型工作流应用，其数据量和计算需求量巨大，需要高性能计算环境支持运行[I]。云计算的出现为科学工作流的执行提供了更高效的技术与支撑环境[2]。云以虚拟机（virtual machines,VM)的形式提供计算资源，而工作流中任务与计算资源间的映射问题即为工作流调度问题。云工作流调度包括两个层次：一是任务与VM间的映射，二是在单个VM上任务的顺序执行[3]。本文将以AmazonEC2云环境为基础解决云工作流调度的多目标最优化问题，重点关注于工作流调度执行跨度与执行代价的最优化，寻找最优调度方案。

相关研究中，文献[4]提出一种异构预算约束调度算法HBCS，通过定义代价因子调整可用预算与最低价格的比例，实现优化调度。文献[5]提出一种异构最快完成时间调度算法HEFT，通过赋予任务不同优先级，最小化任务调度时间。文献[6]提出一种基于预算约束的异构最快完成时间算法BHEFT，该算法是对HEFT算法的扩展实现，考虑了任务调度的最优预算约束问题。文献[7]提出基于离散粒子群优化的工作流调度算法CWDPSO，算法以资源使用成本和安全满意度为优化目标，利用粒子群进化求解了资源分配方案。HEFT、BHEFT、HBCS和CWDPSO四种算法均是将求解目标转换为单目标最优化，并不适用于AmazonEC2的云工作流调度场景。

多目标调度中，文献[8]提出POSH算法，将执行跨度与执行代价同步考虑，同时以用户定义的偏好因子设置两者权重，实现多目标优化。文献[9]中的 NSPSO 算法和文献[10]中的Fussy-PSO 算法均尝试使用粒子群优化算法实现工作流调度时执行跨度与执行代价的均衡。文献[11]提出多目标异构最快完成时间算法MOHEFT，旨在通过Pareto 线性启发式算法对HEFT进行扩展，实现多目标优化。然而，以上多目标调度算法仅适用于传统异构计算环境，IaaS云环境在计算模式、数据以及定价模型上均不同于传统计算环境。

本文将提出一种云环境中的工作流多目标调度算法CMOHEFT。算法以工作流任务的执行跨度makespan和执行经济代价的同步最小化为目标，通过启发式方法得到了多目标间的均衡最优解集合，并以Pareto 边界和hypervolume 值的方式对均衡解进行了有效性评估。

# 1 AmazonEC2云环境

Amazon弹性计算云EC2是一种IaaS（基础设施即服务，infrastructure asa service）云服务，可开放地向用户提供Amazon的计算设施。“弹性”特征表明用户可以通过请求或释放资源和实例的方式扩展和收缩自身的基础设施。目前，AmazonEC2提供三种类型的实例：

a）预留型实例，允许用户对多个主机资源作长期预订。b)按需型实例，允许用户仅按请求的资源和请求时间进行付费，付费单位为小时。

c)Spot型实例，允许用户对未使用的Amazon 资源进行投标，用户指定资源使用的最大出价，若出价高于当前spot价格（取决于资源需求量)，则用户获得实例；若出价小于 spot 价格，则Amazon回收实例。

AmazonEC2提供14种拥有不同性能和代价的不同类型按需实例。实例的计算性能根据弹性计算单元ECU（ElasticComputeUnit）进行定义，等同于一个拥有1.0-1.2GHz的Xeon处理器的能力。表1总结了这些资源的平均性能、单位小时计算能力的代价及单位费用的资源每秒浮点运算数GFLOPs（millions offloating point operation per second）。本文的多目标工作流调度算法将以表1的5种类型实例进行性能评估。

表1Amazon EC2 实例类型  

<html><body><table><tr><td>实例类型</td><td>平均性能/GFLOPS</td><td>价格/$/h</td><td>GFLOPS/$</td></tr><tr><td>m1.small</td><td>2.0</td><td>0.1</td><td>19.6</td></tr><tr><td>m1.large</td><td>7.1</td><td>0.4</td><td>17.9</td></tr><tr><td>m1.xlarge</td><td>11.4</td><td>0.8</td><td>14.2</td></tr><tr><td>c1.medium</td><td>3.9</td><td>0.2</td><td>19.6</td></tr><tr><td>c2.xlarge</td><td>50.0</td><td>0.8</td><td>62.5</td></tr></table></body></html>

# 2 模型描述

# 2.1工作流 DAG 任务模型

定义工作流应用为有向无循环图DAG， $W { = } ( A , D )$ ，其中，$A$ 表示包括 $n$ 个任务的任务集， $A { = } \cup n i { = } 1 \left\{ A _ { i } \right\}$ ， $D$ 表示任务间的控制流和数据流依赖关系， $D { = } \{ ( A _ { i } { , } A _ { j } { , } D a t a _ { i j } ) | ( A _ { i } { , } A _ { j } ) { \in } { \cal { A } } { \times } { \cal { A } } \}$ Dataij表示任务 $A _ { i }$ 与 $A _ { j }$ 间的数据传输量。令$p r e d ( A _ { i } ) = \{ A _ { k } | ( A _ { k } , A _ { i } , D a t a _ { k i } ) \in D \}$ 表示任务 $\mathbf { \mathcal { A } } _ { i }$ 的前驱任务集，即必须在 $A _ { i }$ 开始之前完成。假设每个任务 $A _ { i }$ 的计算负载是已知的，且表示为可执行的机器指令数量。

# 2.2资源模型

假设云平台由 $\mathbf { \nabla } _ { m }$ 个异构资源集合组成， $R = \cup m j = 1 \{ R j \}$ ，由Amazon EC2 的云资源类型提供，如：ml.small、ml.medium、ml.large、ml.xlarge、c1.medium及c1.xlarge。对于确定类型的给定资源 $R _ { j }$ ，其平均性能由GFLOPs 进行度量，即：Floating-point Operations PerSecond，每秒所执行的浮点运算次数。在本文的工作流模型中，假设工作流任务可以并行执行的方式运行于如表1所示的AmazonEC2虚拟机实例上，资源使用以单位小时收取费用（表1第三列)，最终的用户付费成本不仅取决于资源使用，而且包括数据存储与不同VM实例间的数据传输，具体包括以下四个部分：每小时的资源使用价格 $P E _ { R i }$ ；单位MB的数据存储价格 $P S _ { R i }$ ；单位MB 的数据接收价格 $P I _ { R i }$ ；单位MB的数据发送价格 $P O _ { R i }$ 。

# 2.3问题定义

本文的工作流调度问题即为将工作流任务调度至 Amazon云资源上执行，使得执行时间makespan和经济代价达到最小。令sched(Ai)表示任务 $A _ { i }$ 调度的执行资源，以下分别定义两个优化目标：

# 1）执行时间 makespan

令execution time $t ( A _ { i } , R _ { j } )$ 表示任务 $A _ { i }$ 在资源 $R _ { j } { = } s c h e d ( A _ { i } )$ 的计算时间与接收来自任意前驱任务 $A _ { p } \in p r e d ( A _ { i } )$ 的最大输入数据时间之和，表示为

$$
t ( A _ { i } , R _ { j } ) = \operatorname* { m a x } _ { A _ { p } \in p r e d ( A _ { i } ) } \frac { D a t { a _ { p i } } } { b _ { p j } } + \frac { w o r k l o a d ( A _ { i } ) } { s _ { j } }
$$

其中 $: D a t a _ { p i }$ 表示任务 $A _ { p }$ 与 $\mathbf { \mathcal { A } } _ { i }$ 间的数据传输量， $b _ { p j }$ 表示任务 $A _ { p }$ 的执行资源与资源 $R _ { j }$ 间的带宽，workload $\left( A _ { i } \right)$ 表示任务 $A _ { i }$ 的指令长度， $s _ { j }$ 表示资源 $R _ { j }$ 的计算速度，单位为每秒执行的机器指令数MIPS。任务 $A _ { i }$ 的完成时间 $T _ { A i }$ 包括任务本身的执行时间和其前驱的执行时间，表示为

$$
\begin{array} { r } { T _ { _ A } = \left\{ \underset { ^ { _ { o r r e d } ( A _ { i } ) } } { \operatorname* { m a x } } \{ T _ { _ A } , \right.} + t ( A _ { i } , { s c h e d ( A _ { i } ) } ) , p r e d ( A _ { i } ) = \emptyset   \\ { \left. \qquad \quad \right. } \\ { p r e d ( A _ { i } ) \neq \emptyset \qquad } \end{array}
$$

工作流的执行时间makespan 定义为所有任务中的最大完成时间为

$$
T _ { w } = \mathop { \operatorname* { m a x } } _ { i \in [ 1 , n ] } T ( A _ { { \varepsilon } } , s c h e d ( A _ { { \varepsilon } } ) )
$$

# 2）经济代价

工作流执行的经济代价包括两个部分：计算代价 $C ^ { ( c o m p ) }$ 和数据传输与存储代价 $C ^ { ( d a t a ) }$ 。

令 $C ( d a t a ) \ ( A i , R j )$ 表示任务 $A _ { i }$ 在资源 $R _ { j }$ 上执行过程中传输输入数据 $I n ( A _ { i } )$ 、输出数据 $O u t ( A _ { i } )$ 及存储数据 $D a t a ( A _ { i } )$ 的代价，表示为

$$
C _ { ( A _ { i } , R _ { j } ) } ^ { ( d a t a ) } = D a t a ( A _ { i } ) \times t ( A _ { i } , R _ { j } ) \times P S _ { R _ { i } } +
$$

$$
I n ( A _ { \iota } ) \times P I _ { \scriptscriptstyle R _ { \scriptscriptstyle R } } + O u t ( A _ { \iota } ) \times P O _ { \scriptscriptstyle R _ { \scriptscriptstyle R } }
$$

令 $C ( c o m p ) R j$ 表示使用资源 $R _ { j }$ 的代价，对于执行 $\mathbf { \mathcal { A } } _ { i }$ 的 $R _ { j }$ 令 $t ( s t a r t ) \mathbf { \mathbf { \Psi } } _ { } A i$ 表示任务的开始时间， $t ( e n d ) A i$ 表示任务的结束时间，可表示为

$$
t _ { _ A _ { i } } ^ { ( s t a r t ) } + t ( A _ { _ i } , R _ { _ j } ) + \operatorname* { m a x } _ { A _ { i } \in p r e d ( A _ { p } ) } \frac { D a t a _ { _ i p } } { b _ { _ j p } }
$$

同时，假设传输输入数据 $I n ( A _ { i } )$ 和输出数据 $O u t ( A _ { i } )$ 的时间均处于 $t ( s t a r t ) \_ s i i$ 和 $t ( e n d ) A i$ 之间。

考虑在资源 $R _ { j }$ 上调度的 $p$ 个任务集合为 $\{ J _ { 1 } , J _ { 2 } , . . . , J _ { p } \}$ ， $p { < } n$ 且 $s c h e d ( J _ { i } ) = R _ { j } , i \in [ 1 , p ]$ ，任务基于开始时间进行排列：t(start)$J 1 < t ( s t a r t ) J 2 < . . . < t ( s t a r t ) J p ,$ 。基于以上排列，将所有任务划分为 $q ( q { \leq } p )$ 个不同的群组 $G ( j ) k$ ， $1 { \leq } k { \leq } q$ ，使得同一组内的所有任务可以在无须释放资源的同时连续执行。群组中拥有最大开始时间的任务完成后，资源即可释放。

通过以下三个规则，构造第一个群组 $G ( j ) ~ 1 { = } \{ J _ { 1 } , J _ { 2 } , . . . , J _ { r } \}$ $r { \le } p$ ：

规则1第1个任务 $J _ { 1 }$ 属于第一个群组： $J _ { 1 } \in G ( j ) \ 1$ ：

规则2每个任务 $J _ { i } \in G ( j ) ~ 1 ( 2 { \le } i { \le } r )$ 在资源释放前完成。这表明由于 $J _ { i - 1 }$ 的执行，资源仍被租用时Ji即可开始：

$$
t _ { \jmath _ { i } } ^ { ( s t a r t ) } < t _ { \jmath _ { 1 } } ^ { ( s t a r t ) } + \left\lceil \frac { t _ { \jmath _ { i - 1 } } ^ { ( s t a r t ) } - t _ { \jmath _ { 1 } } ^ { ( s t a r t ) } } { 3 6 0 0 } \right\rceil \times 3 6 0 0
$$

规则3下一任务 $J _ { r - 1 } \mathrm { { \notin } } G ( j ) 1 ( r + 1 { \leq } p ) ^ { } $ 在资源已经释放时，在开始时间t(start) $_ { J r + 1 }$ 时立即开始执行，即：任务 $J _ { r }$ 完成执行后，执行 $J _ { r }$ 的最后租用周期1小时已经截止，而且资源 $R _ { j }$ 在t(end) $J r$ 与 $t ( s t a r t ) J r { + } 1$ 间是为空闲，表示为

$$
t _ { _ { J _ { 1 } } } ^ { ( s t a r t ) } \Bigg \lceil \frac { t _ { _ { J _ { \mathrm { r } } } } ^ { ( e n d ) } - t _ { _ { J _ { 1 } } } ^ { ( s t a r t ) } } { 3 6 0 0 } \Bigg \rceil \times 3 6 0 0 < t _ { _ { J _ { { r + 1 } } } } ^ { ( s t a r t ) }
$$

直到最后的任务 $J _ { p }$ 分配至一个群组后，即可建立连续的群组。第二个群组 $G ( j ) 2$ 以 $J _ { r + 1 }$ 代替 $J _ { 1 }$ 以同样的方式构建，同样的策略被使用至剩余群组的构建中。建立所有群组后，定义使用资源 $R _ { j }$ 的代价 $C ( c o m p ) \ R j$ 为执行所有群组需要的小时数与单位小时代价之积：

$$
C _ { R _ { j } } ^ { ( c o m p ) } = P E _ { R _ { j } } \times \sum _ { k = 1 } ^ { q } \Biggl [ \frac { \sum _ { A _ { i } \in G _ { R _ { j } } ^ { ( k ) } } t ( A _ { i } , R _ { j } ) } { 3 6 0 0 } \Biggr ]
$$

执行工作流 $W { = } ( A , D )$ 的经济代价为所有 $\mathbf { \nabla } _ { m }$ 个资源的计算代价与数据传输与存储代价之和：

$$
C _ { w } = \sum _ { j = 1 } ^ { m } C _ { R _ { j } } ^ { ( c o m p ) } + \sum _ { ( A _ { i } , A _ { j } , D a t a _ { i j } ) \in D } C _ { ( A _ { i } , R _ { j } ) } ^ { ( d a t a ) }
$$

# 3 多目标优化

多目标最优化问题通常可定义为：寻找使得矢量函数$f ( x ) { = } [ f _ { 1 } ( x ) , f _ { 2 } ( x ) , { \ldots } , f _ { o } ( x ) ]$ 最小化的所有解 $x$ ，其中， $\mathbf { \sigma } _ { o }$ 表示优化目标数量（本文为两个目标：执行时间makespan和经济代价）。工作流调度问题中每个解 $x$ 包括两个矢量：第一个矢量为包括$n$ 个元素的矢量 $( x _ { 1 } , x _ { 2 } , . . . , x _ { n } )$ ， $n$ 表示工作流的任务数量 $( n { = } | A | )$ ，$\scriptstyle x _ { i } = s c h e d ( A _ { i } )$ 表示任务 $\ A _ { i } \in A$ 执行的资源；第二个矢量为大小为$n$ 的排列 $p$ ，表示所有任务执行的顺序。

对于工作流调度问题，同时找到实现执行时间makespan和经济代价的最小化的解是不可能的。为了解决这一问题，本文引入Pareto占优的概念对同步最优进行评估。

如果解 $y$ 的 makespan 和代价均小于解 $z$ ，则称解 $y$ 占优解z。相反，如果两个解之间不存在相互占优（一个解拥有更小makespan，而另一个解拥有更小代价)，则称两个解为非占优。以图1为例，解 $a$ 占优解 $b$ ，由于其拥有更好的makespan 和代价。同样地，解 $a$ 占优解 $\boldsymbol { \mathscr { c } }$ 。同时，解 $a$ 与解 $d$ 是非占优的，由于解 $a$ 的 makespan 更优，而解 $d$ 的代价更优。最优非占优解的集合称为Pareto边界（包含解 $a$ 、 $d$ 和 $e$ 的趋势线)，表示不同目标间的均衡解集合。该集合中的每个解表示拥有不同makespan和代价的工作流任务的不同映射方案。

度量均衡解质量的方法为超体积hypervolume。给定均衡解$X$ 的集合,hypervolume $H V ( X )$ 测量的是 $X$ 中的点与参考点 $W$ 间的封闲区域，如图1所示，通常选择为最大目标值（即最高的makespan和经济代价）。因此，在 $X$ 中的点越多不同越好，其$H V ( X )$ 值也越高。图1中，包含实线图周围点的解集合优于包含正方形中点集合的解，因此，包含所有实线图周围点的集合的hypervolume 值高于包含正方形中点集合的hypervolume 值。

![](images/6497c612dce116664106017d38c3c5fbba14c48503f72c4793a8956248c0ea86.jpg)  
图1多目标均衡解

# 4多目标工作流调度算法设计

本节笔者改进了传统异构计算环境中的单目标优化算法HEFT 和多目标优化MOHEFT，使其可以适用于AmazonEC2的云环境中。传统异构系统中，资源数量与类型均是已知的，然而，云计算环境中的资源总量虽是有限的，但其资源提供模式是按需和动态的，资源可用性及其计算能力均是动态变化的。

为了使算法适应于新的云环境，考虑资源输入量为 $\scriptstyle { m = N \times I }$ 其中， $I$ 表示云提供者提供的实例类型数量，通过这种设置，可以确保资源最大量 $N$ 下的所有组合均是可能的。

算法1为单目标算法CHEFT的执行过程，算法的设计思路是：将任务调度过程划分为两个阶段，任务分级阶段和任务映射阶段。任务分级阶段中利用自顶向下分级的方式计算任务至工作流结构的出口任务间的距离（以任务至出口任务之间所有路径上边的最大数量表示)，然后根据各个任务的分级值对任务进行降序排列，得到任务调度优先序列，通过该分级方法可以使得拥有更大依赖性的任务优先得到执行。任务映射阶段中即仕所有资源上寻我 makespan 最小的调度解。仕该过程中，为了符合云环境的调度需求，需求测试局部调度方案是否需求多于 $N$ 个资源，如果不多于 $N$ ，则通过公式 $T _ { R a n k i } {  } \mathrm { m a x } _ { \mathit { A p } } { \in }$ $p r e d ( R a n k i ) \left\{ T _ { A p } + t ( R a n k _ { i } , R _ { j } ) \right\}$ 计算 makespan，否则，该解的 makespan设置为无穷。

算法2为多目标算法CMOHEFT的执行过程，算法的设计思路是：首先，以自顶向下分级的方式计算任务分级值，然后，设置可容纳 $K$ 个多目标均衡的空集 $s$ 。迭代访问根据分级值降序排列的任务集合，得到执行顺序。算法的目标在 $\mathbf { \nabla } _ { m }$ 个可用资源上是不断扩展集合 $s$ ，以创建并存储新的映射解。新的映射的搜索过程为寻找到 $K$ 个解为止。最后，以Pareto占优及

hypervolume 法评估解的质量，得到多目标最优解。算法2CMOHEFTRequire: $W { = } ( A , D ) , A { = } \cup n i { = } 1 \left\{ A _ { i } \right\} / / .$ 工作流应用  
（20 Require:N//最大同步实例（资源）数量Require: $I / /$ 不同实例类型数量算法1CHEFT Require: $R { = } \cup m j { = } 1 \left\{ R _ { j } \right\} / ,$ /资源集合， $\scriptstyle { m = N \times I }$ （204Require: $W { = } ( A , D ) , A { = } \cup n i { = } 1 \left\{ A i \right\} / / .$ 工作流应用 Require: $K / /$ 均衡解数量Require: $N / /$ 最大同步实例（资源）数量 Ensure: $S { = } \cup K$ Require: $I / /$ 不同实例类型数量 $i = 1 \ \{ s c h e d _ { W } \} , s c h e d _ { W } = \{ ( A _ { i } , s c h e d ( A _ { i } ) ) | A _ { i } \in { \cal A } \} / \langle { \bf K }$ 个均衡调度解集Require: $R { = } \cup m j { = } 1 \left\{ R _ { j } \right\} /$ /资源集合， $\scriptstyle { m = N \times I }$ （204 合Ensure: schedw $= \{ ( A _ { i } , s c h e d ( A _ { i } ) ) | A _ { i } \in A \} /$ /工作流调度 function CMOHEFT $( W , R , K )$ （204function CHEFT( $\mathbf { \partial } _ { [ W , R ] }$ （20 Rank←B-RANK(A)//根据B-rank对任务排序Rank $$ B-RANK(A)//根据B-rank 对任务排序 for $k {  } 1 , K$ do//创建K个空的工作流调度解sched $_ { W } {  } { \partial } / /$ 初始化工作流调度为空集 （204号 $S _ { k } { \gets } \emptyset$ （204for $i {  } 1 , n$ do//迭代所有分级任务 end for${ \mathrm { T } } _ { \mathrm { m i n } } {  } { \infty }$ for $i  1 , n$ do//迭代所有分级任务for $_ { j  1 , m }$ do//迭代所有资源 （204号 $S ^ { \prime } {  } \emptyset$ if COUNTRESOURCES(schedw,m) $\leq N$ then//如果使用实例 for $_ { j  1 , m }$ do//迭代所有资源  
数小于 $N$ （204 for $k {  } 1 , K \mathrm { d o } / /$ 迭代所有均衡调度解TRanki←maXApepred(Ranki) $\mathrm { \Delta T _ { A p } + } 1$ (Ranki,Rj)}//计算Ranki的完成 $s {  } S _ { k } \cup ( R a n k _ { i } { \mathrm { , } } R _ { j } )$ //扩展所有中间调度方案  
时间 if COUNTRESOURCES(schedw,m) ${ > } N$ then//如果使用实例else 数多于 $N$ （204号（204号 $T _ { R a n k i } {  } { \infty } / _ { I }$ 标识调度为无效 $T _ { s } { \gets } \infty / \$ 标记调度为无效end if $C _ { s } { \gets } \infty$ （204if $T _ { R a n k i } { < } T _ { m i n }$ then//保存最小完成时间 end if（20 $\mathrm { T } _ { \mathrm { m i n } } {  } \mathrm { T } _ { \mathrm { R a n k i } }$ （204 $S ^ { \prime } {  } S ^ { \prime } \cup \{ s \} / /$ 添加新映射至所有中间调度（204 $\mathrm { R } _ { \mathrm { m i n } } {  } \mathrm { R } _ { \mathrm { j } }$ （204号 end forend if end forend for $S ^ { \prime } \gets$ SORTCROWDDIST $( S ^ { \prime } , K ) / /$ 根据拥挤距离排序schedw $$ schedwU(Ranki,Rmin)//调度任务 $S { \longleftarrow } \mathrm { F I R S T } ( S ^ { \prime } , K ) / ,$ /选择 $K$ 个最高拥挤距离的调度end for end forreturn schedw return $S$ （end function end function

CHEFT与传统单目标算法不同之处在于算法1的步骤$1 2 \sim 1 6$ 行，传统单目标算法在每次新的局部调度中计算makespan，而CHEFT则测试局部调度方案是否需求多于 $N$ 个资源，如果不多于 $N$ ，则计算makespan（行13)，否则，该解的makespan设置为无限，即步骤15。通过该方法，无效调度方案将无法验证行17中的条件，且将被丢弃并而保留需求资源小于 $N$ 个同步实例的调度方案。

CMOHEFT与传统多目标算法的不同之处在于算法2的$1 7 { \sim } 2 0$ 行，CMOHEFT的资源量约束在第17行检查，如果未违背资源量约束，makespan和代价按算法前文进行计算，如果违背，则设置为无限，这可以使算法丢弃第24行中的解，仅仅产生至多 $N$ 个同步资源的均衡解。

算法时间复杂度分析。给定包括 $n$ 个任务和 $m$ 个资源的工作流调度场景，CHEFT算法需要先计算每个任务的分级值，该过程的时间复杂度为 $O ( n )$ 。然后，需要将排序后的 $n$ 个任务迭代方式在 $m$ 个可用资源上寻找执行跨度makespan 最小的调度解，该过程的时间复杂度为 $O ( n \times m )$ 。因此，CHEFT 算法的时间复杂度为 $O ( n ) { + } O ( n \times m ) { = } O ( n \times m ) ,$

CMOHEFT算法与CHEFT算法的过程有两个不同之处：一是算法在每次迭代中多个解的创建方式，二是考虑资源提供均衡解的可能性，两处不同均体现在CMOHEFT算法中的 $1 5 \sim$ 21行中。考虑均衡解的集合大小为 $K$ ，通常情况下，均衡解的数量为常数，且其值小于 $n$ 和 $m$ ，而CMOHEFT算法比较CHEFT仅额外需要执行 $K$ 次迭代，因此，CMOHEFT算法的最差时间复杂度为 $\mathrm { O } ( n ^ { \times } m ^ { \times } K )$ 。

# 5 实验配置

本节通过仿真实验以评估多目标算法CMOHEFT的有效性，仿真平台选择WorkFlowSim[12]。首先，给出了评估算法性能质量的比较指标，然后，描述了测试工作流的不同类型和实验中AmazonEC2设施的配置情况。实验中除了实现CHEFT和CMOHEFT算法之外，还选择了POSH算法[8]作为性能比较的参考算法，选择的原因是该算法同为多目标优化算法，且也考虑了均衡解的问题。

# 5.1评估指标

考虑三个指标比较三种算法的性能：执行工作流的最短makespan、执行工作流的经济代价及hypervolume评价指标。前两个指标主要用来评价单个指标的优化性能，hypervolume 则是评价多目标最优均衡解的质量。

Hypervolume的具体的计算方法是：给定由CMOHEFT算法计算得到的调度均衡解 $X$ 的集合，定义 $H V ( X )$ 表示一种hypervolume值，测量范围为是调度解集合 $X$ 中的单个点（表示一个调度解）与所选择的参考点 $W$ 间的封闲区域，基于工作流调度目标是执行makespan与执行代价的同步优化，参考点选取为调度均衡解集合 $X$ 中的最高的makespan和执行代价cost所表示的点。然后，将解集合中的个体解按照其在第一维目标上的值进行降序排列，按照以下公式计算个体解 $p _ { i }$ 的独立占优区域的Hypervolume 指标：

$$
H V ( p _ { i } ) { = } | \mathrm { m a k e s p a n } ( p _ { i - 1 } ) { \mathrm { - } } \mathrm { m a k e s p a n } ( p _ { i } ) | { \times } | \mathrm { c o s t } ( p _ { i + 1 } ) { \mathrm { - } } \mathrm { c o s t } ( p _ { i } ) |
$$

其中， $2 { \le } i { \le } K { - } 1$ ， $K$ 表示解集合中的解数量，makespan $( p _ { i } )$ 表示解集中第 $i$ 个个体解在执行跨度 makespan 上的值， $\mathrm { c o s t } ( p _ { i } )$ 同理。

# 5.2 工作流应用

实验中引入两种类型的工作流应用进行测试：人工配置不同属性的多类型的人工合成工作流应用和现实科学领域中的现实工作流。

# 1）人工合成工作流

利用随机工作流产生器产生三种类型合成工作流(如图2(a)和图2(b))，主要目的是分析任务数量对调度结果的影响，因此，所定义的工作流类型可以覆盖多种类型的工作流结构：

Type-1工作流：任务可以并行度为1和2时进行执行；

Type-2工作流：任务执行的并行度较高，且工作流较均衡（同一层次上的任务数相同)；

Type-3工作流：任务执行的并行度较高，但工作流不均衡（同一层次上的任务数不同）。

每个任务的大小和数据量的产生符合高斯分布，对于每种类型工作流，任务分布于100与1000之间，实例数为100。

# 2）现实工作流应用

考虑两种现实工作流应用：WIEN2K和POV-Ray，结构分别如图2(c)和图2(d)。

WIEN2K是基于波纹方法并利用密度泛函理论计算固体电子结构的一种材料科学工作流应用，属于Type-2工作流类型，由连续同步任务执行的两个并行部分组成。POV-Ray是一种构建立三维图形的开放工具，多用于生物学、医学、建筑学和数学可视化领域中，也属于Type-2工作流类型。

![](images/cc04ed0d4043db9e12ac1c84c4090ff39d581d10da780819c1585503ec948f1e.jpg)

(a)人工合成工作流结构-均衡 (b)人工合成工作流结构-非均衡

![](images/5578d8fea05fb5cdceeafd774ea02b8d57b8256de75dd28f6ac992369b1fea29.jpg)

# (c)WIEN2k工作流结构

![](images/d5d0c51512ba0787dfeda0af7be20d367d21ae4ceb1b671f5bfdee1d09141338.jpg)  
图2工作流应用结构

# 5.3资源配置

令用户可访问的Amazon实例的最大数量为 $N { = } 2 0$ ，实例共有五种类型，如表1所示，即： $\scriptstyle { I = 5 }$ ， $\scriptstyle { m = N \times I = 2 0 \times 5 = 1 0 0 }$ 。同时，设Amazon至外部互联网间的输出数据量为常数，且该数据输出仅发生于工作流执行的结束，因此不会影响调度结果。仿真实验中，数据发送与接收的代价均为0，即 $P I _ { R i } { = } 0$ ， $P O _ { R i } { = } 0$ 。

# 6 实验结果评估

# 6.1 合成工作流

1)Type-1工作流

图3是三种算法在makespan、经济代价和hypervolume 性能上的结果。图3(a)表明CMOHEFT在所有评估实例上的hypervolume 均优于POSH。图中未包含CHEFT是由于该算法仅得到最优makespan 的单一解。明显地，对于Type-1工作流，CMOHEFT在计算调度解时始终拥有相同的hypervolume 值，这表明均衡解的最优集合的形态并未随着工作流规模的变化而发生变化。在makespan方面(图3(b))，三种算法得到了相同解，这证实了CMOHEFT的性能比较CHEFT并未出现下降，而POSH以HEFT得到初始解，因此也是相同的 makespan。图3(c)表明CMOHEFT与POSH得到了相同的成本最低调度，两种算法在整个工作流的执行上均只使用了 $\mathrm { m l . s m a l l }$ ，这主要是由该类型工作流的较低的并行度导致的，而CHEFT则总是代价最高的。

图3(d)是CMOHEFT与POSH的均衡解图示，明显地，CMOHEFT的解质量更高。具体来说，CMOHEFT以增加约 $7 \%$ 的时间开销就可以平均降低若 $45 \%$ 的执行代价，而POSH得到相同的代价时，在makespan指标上则增加了约 $2 5 \%$ 。

![](images/56a7d948780539e819772d09fc2f94900e7594dc371f3ef2bab55159a5353e56.jpg)  
图3Type-1合成工作流

2)Type-2工作流

图4是Type-2工作流的执行结果。图4(a)表明，对于所有工作流规模，CMOHEFT 在均衡解质量上均是优于POSH 的。不同的工作流规模会导致拥有不同hypervolume值的Pareto 边界，这表明该问题中Pareto边界的形状取决于可并行执行的任务数量。对于makespan（图(b))，CMOHEFT与POSH甚至在有些情况下可以得到较CHEFT更优的makespan，这主要是由于CHEFT具有贪婪属性，较容易收敛于局部最优，而CMOHEFT与POSH以更大的搜索空间克服了这一缺陷。经济代价方面（图4(c))，CMOHEFT与POSH则以最优的makespan得到了相同的最低代价。

图4(d)得到的 CMOHEFT 与 POSH 的均衡解间的不同较Type-1更为明显。此时，CMOHEFT仅以增加 $1 . 4 \%$ 的 makespan而降低了 $30 \%$ 左右的代价。而POSH得到相同的代价则需要增加 $45 0 \%$ 的 makespan 开销。

![](images/04fe6f15a107cbb75ebbd9d59e8b843425cfe8aae276ee2353fc0b0532fab7ef.jpg)  
图4Type-2合成工作流

3)Type-3工作流

图5是Type-3工作流的执行结果，进一步证明了以上两类工作流的验证结果。总体看来，CMOHEFT更适应于AmazonEC2云环境中的工作流多目标调度。

![](images/ef4b21af89d47d0294f773777643ca27e9353436a4e4531efb1be88b5d86d910.jpg)  
图5Type-3合成工作流

# 6.2现实工作流

1)WIEN2k工作流

图6(a)表明，与合成工作流类似，CMOHEFT在hypervolume上仍优于POSH，并且，两间的差距明显大于以上合成工作流。这是由于现实工作流应用的求解复杂度变高的原因导致的。图6(b)和6(c)也证实了合成工作流中的结论。在makespan方面，三种算法性能相同。而在代价方面，CMOHEFT与POSH得到的代价更低。图6(d)中两种算法的均衡解方面得到的结果与Type-2类似，CMOHEFT可以更小的 makespan开销节省更多的代价。

![](images/f193ebe475da613bfda1a42068d22775946f5528961c07b10f083b8f8daa533f.jpg)  
图6 WIEN2k工作流

2)POV-Ray工作流

POV-Ray工作流的执行结果与WIEN2k工作流是类似的，如图7所示。对于该类工作流，任务数量更高，CMOHEFT计算高质量均衡解集合将越困难，这也导致hypervolume 值会随着任务数量增加而下降。然而，对于POSH则未出现明显类似的结果，但其Pareto 边界的质量明显也弱于CMOHEFT。其他结果则与以上工作流类型是类似的。

![](images/96dae2b4d7be5e7f016ce5ff64067505d35ba41054d0cdfcefcc49f685ebb121.jpg)  
图7POV-ray 工作流

# 6.3 资源数量的影响

本节分析放宽同步可使用资源的数量的限制对算法性能的影响，主要集中于研究资源数量规模与额外资源对计算均衡解的影响。实验配置以WIEN2k工作流为测试源。

图8和图9是同步资源数量设置为20、50和100时的执行结果。图8是资源数量对最小makespan的影响。可以看出，CMOHEFT计算得到的最小makespan 会随着资源使用数量的增加而降低。在所有情形中，算法在计算最优调度方案时均会利用所有允许使用的资源量。

图9是CMOHEFH与POSH计算得到的Pareto 边界情况。此图的目的是观察不同资源数量对不同均衡解的影响。对于CMOHEFH（图9(a))，其Pareto边界在所有情况下是类似的，唯一不同仅体现在最优makespan 的计算过程中。此时，拥有更高的资源量表明代价更高而调度时间更短(体现于边界左侧)。在最小化调度代价方面，得到的解并未受到同步使用资源量的影响。对于POSH（图9(b))，性能仍低于CMOHEFT。资源量的增加会导致POSH的调度时间变短但代价更高。同时，其中的一些调度方案会违背允许使用的同步资源量的限制。

![](images/32b0064f88a34e72a4ce81a6293461b40e514d4d2c4597967260fd4701e95bf5.jpg)  
图8不同资源数量限制下的最短makespan

![](images/64c04d59e8f92bfb76d968cf2be8cda1adb42db2efffa5132a9d85b07d996aae.jpg)  
图9不同资源数量约束下的Pareto 边界

# 7 结束语

本文提出了一种AmazonEC2云环境中的工作流多目标调度算法CMOHEFT。算法以工作流任务的执行跨度makespan和执行经济代价的同步最小化为目标，通过启发式方法得到了多目标间的均衡最优解集合，并以Pareto 边界和hypervolume 值的方式对均衡解进行了有效性评估。通过三种人工合成工作流和两种现实科学工作流任务的测试，结果表明，CMOHEFT算法比较单目标的CHEFT算法和多目标的POSH算法，大多数工作流类型中均可以得到更小的执行跨度和经济代价。

# 参考文献：

[1]Laili Y,Tao F, Zhang L,et,al.A study of optimal allocation of computing resources in cloud manufacturing systems [J]，International Journal of Advanced Manufacturing Technology,2012,63 (5): 671-690.   
[2]Liu L,Zhang M,Lin Y,et al.A survey on workflow management and scheduling in cloud computing [C]// Proc of the 14th IEEE//ACM International Symposium on Cluster, Cloud and Grid Computing.[S.1.] : IEEE Press,2014: 837-846.   
[3]Rodriguez M,Buyya R.Deadline based resource provisioning and scheduling algorithm for scientific workflows on clouds [J].IEEE Trans Cloud Computing,2014,2(2): 222-235.   
[4]Arabnejad H, Barbosa JG.A budget constrained scheduling algorithm for workflow applications [J]. Journal of Grid Computing,2014,12 (14):1-15.   
[5]Topcuoglu H,Hariri S,Wu MY,Performance-effective and low-complexity task scheduling for heterogeneous computing [J].IEEE Trans on Parallel Distributed Systems,2012,13 (3): 260-274.   
[6]Zheng W, Sakellariou R.Budget-deadline constrained workflow planning for admission control[J].Journal of Grid Computing,2013,11(4): 633-651.   
[7]杨玉丽，彭新光，黄名选，等，基于离散粒子群优化的云工作流调度 [J]．计算机应用研究,2014,31(12):3677-3681.   
[8]Su S,LiJ,Huang Q, et.al. Cost-efficient task scheduling for executing large programs in the cloud [J].Parallel Computing,2013,39 (4): 177-188.   
[9]Garg R,Singh A.Multi-objective workflow grid scheduling based on discrete particle swarm optimization [M]// Swarm,Evolutionary，and Memetic Computing. Berlin: Springer,2012: 183-190.   
[10] Garg R,Singh AK.Multi-objective workflow grid scheduling usingε-fuzzy dominance sort based discrete particle swarm optimization [J].Journal of Supercomputing,2014,68 (2): 709-732.   
[11] Zhang F,Cao J,HwangK,etal. Ordinal Optimized Scheduling of Scientific Workflows in Elastic Compute Clouds [C]// Proc of the 3rd IEEE International Conference on Cloud Computing Technology and Science. Washington DC: IEEE Computer Society,2012: 9-17.   
[12] Chen W,Deelman E.WorkflowSim:a toolkit for simulating scientific workflows in distributed environments [C]// Proc of the 8th IEEE International Conference on e-Science.[S.1.] :IEEE Press,2012:1-8.