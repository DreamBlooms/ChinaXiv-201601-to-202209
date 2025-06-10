# 考虑客户感知和资源效率的汽车机电维修瓶颈设备调度

杨琴，张伟，王文轲，郝婷婷，张燕(四川师范大学 商学院，成都 610101)

摘要：通过对汽车维修车间瓶颈设备的合理调度有效地提升系统效率和客户满意度。系统效率的提升可以通过最小化制造期（ $C _ { \mathrm { m a x } } \mathrm { . }$ ）来实现，而客户满意度受主观因素影响，因此构建调度问题的目标函数时应考虑客户的心理感知。研究结合行为科学理论，可以将人的“有限理性”行为融入与客户紧密接触的服务资源调度问题。首先，借助前景理论的价值函数，选取客户心理预期等待时间作为参考点，构建客户对修车等待时间的感知不满意程度函数；在此基础上，结合资源效率目标、任务和资源约束条件，构建多目标数学模型；设计与问题相适应的重调度规则和遗传算法，进行求解。最后，通过实例仿真验证了模型及算法的可行性和有效性。

关键词：客户感知；前景理论；汽车机电维修设备；瓶颈；调度 中图分类号：F406.2

# Multi-objective scheduling for vehicle electro-mechanical maintenance of bottleneck machine in consideration of customers’ perception and resource efficiency

Yang Qin, ZhangWei, WangWenke, Hao Tingting, Zhang Yan (Business School Sichuan Normal University,Chengdu 610101,China)

Abstract:The goals ofimproving system eficiencyand customer satisfaction can be achieved effectivelythrough arational scheduling forbottleneckmachineinmotorvehicle maintenance workshop.Ontheonehand,thepromotionofsystem effciency can beachieved byoptimizingthemake-span()；ontheotherhand,customersatisfactionisafectedbysubjectivefactor,it's necessary todo customer satisfaction into consideration while establishingan objective function of the scheduling problem. Combined with Behavioral Science Theory,the paper mixed people's bounded rationality into service resources scheduling problem relatedtothecustomer.Firstly,takecustomer expected waiting time asareference pointbyvirtueofvalue function in the prospecttheory,then establishcustomerdissatisfaction functiontowards waitingtime.Onthebaseofit,establishamultiobjective mathematicalmodelcombinedwiththeobjectiveofresourceeficiencyassignmentoftasksandresourceconstraints. Secondly,designgeneticalgorithmwhichiscorresponding tothescheduling problemandthensoleit.Ultimatelyerifythe feasibility and validity of model and algorithm by simulating example.

KeyWords:customerperception;theprospect theory;vehicleelectro-mechanical maintenance machine;botleneck;scheduling

# 0 引言

汽车维修车间是一个复杂系统，其机器环境相当于柔性加工车间，同时具有任务的到达时间动态、作业时窗缺乏柔性、直接接触客户等特征。1984年，以色列物理学家Goldratt[1]提出约束理论(theoryofconstraints,TOC)，指出瓶颈(bottleneck)是制约系统朝着目标前进的主要因素，决定了整个系统的性能，通过对瓶颈环节的优化可以简化大规模复杂调度问题，降低问题求解的复杂度。目前在实际应用方面，各维修车间通常是依据经验进行工作任务的调度，缺乏科学的规划，这会导致汽车维修作业过程中出现作业顺序安排不当导致总体作业时间延长作业安排不当导致维修设备实际作业能力不如作业负荷等诸多情况，也即在汽车维修作业过程中出现瓶颈设备。汽车机电维修瓶颈设备的合理调度可以提升资源效率和客户满意度。

汽车机电维修瓶颈设备的调度问题可以描述为受存在机器适用约束限制的异速并行机调度问题。在理论研究方面，异速并行机调度已经被证明是NP难题，研究主要集中在启发式算法的运用上[2\~8]。同时，汽车维修服务过程还伴随着客户的参与，因而需要更关注客户感受和客户满意度。基于完全理性假设，可以通过最小化与工期相关的惩罚函数（如滞后任务数量、加权滞后时间和等）来评价客户的满意度。但是，这些函数无法很好地反映客户对服务满意程度的主观感受。客户作为需求主体，其行为的基本特征是有限理性，其心理感知受内部主观因素影响，在等待和接受服务过程中会设定并依据获取信息修正“心理预期”，会表现出“参考依赖”“比较”“公平关切”和“决策偏差”等行为。

近年来已经有学者结合行为科学理论研究人的心理感知对调度方案的影响。Hjorth等人[结合前景理论研究人们对旅行时间的感知价值，构建了一个灵敏度不变或者减小的价值函数，证实随着时间的变化人们对旅行时间的感知价值增大；Liu等人[0运用前景理论对汽车共享服务系统进行了研究，分析顾客作出不理性的决策原因和背景，从而改善现有的服务系统，设计出新的产品；Zhou等人[I结合前景理论对驾驶员在可变信息标志下的路径选择行为特征进行研究，对前景理论中价值函数的参数进行了合理的估计，并通过实证检验也证明了该估计是可行并且有效的。借鉴上述研究成果，本文试图将前景理论价值函数应用于汽车维修任务中客户对等待时间的心理感知函数构建，更贴合实际地刻画客户的“参考依赖”“损失规避”和“敏感性递减”等心理特征。

研究通过对汽车机电维修瓶颈设备作业过程的分析，将其看做异速并行机调度问题，并在调度过程中考虑客户的心理感知，将行为科学理论融入与客户紧密接触的服务资源调度问题。具体内容包括：a)基于客户行为特征分析，借助前景理论，选取客户心理预期等待时间作为参考点，构建客户对等待时间的感知不满意程度函数；b)从系统目标、资源和任务约束条件三个方面，对问题进行了描述，构建维修车间的多目标调度数学模型；c)采用遗传算法，设计与问题相适应的遗传代码和迭代寻优方法，进行问题求解，进行

问题求解；d)通过实例仿真验证了模型及算法的可行性和有效性。

# 1 基于前景理论的客户感知不满意度函数构建

# 1.1客户行为特征分析

当汽车维修过程中通常会出现两种情况：a）简单的定期保养维护任务，作业时间短，客户会选择现场等待取车；b)复杂的检修和钣金油漆任务，作业时间长，客户会将车辆放置在维修车间，然后约定时间取车。两种情况下瓶颈资源存在差异，客户对等待时间的心理感知也不同。本文主要研究的是第一种情况，通过对客户现场等待取车过程中行为特征的分析，构建客户对等待时间的感知不满意程度函数。

保养维护任务作业时间短，通常在0.5\~2小时内就能完成，客服人员会依据车间现场作业情况，为客户提供一个取车时间。客户通常会选择现场等待，这类客户对等待时间的长短较为敏感，可能出现以下三种场景：

a)客户现场等待取车，任务提前完成，客户等待时间缩短，满意度提升。但如果任务过早完成，客户会担心维修质量，进而导致感知满意度降低。

b）客户现场等待取车，任务按时完成，客户按时取车，对

等待时间基本满意。

c)客户现场等待取车，任务延迟完成，客户等待时间延长，产生不满，不满程度随等待时间增长而增加，且表现出“不耐烦"的行为特征。

# 1.2客户感知不满意程度函数构建

前景理论的价值函数 $\nu$ 可以表示决策者主观感受的价值，它和参照点有关。决策的初始阶段，决策者会选择一个参考点，通常将价值为零的点作为一个参考点，后果值的盈亏变化都是相对于这个参考点而言。Kahneman 等[12]提出的价值函数，公式如下：

$$
\nu _ { j } \left( x \right) = \left\{ \begin{array} { l l } { { x ^ { \alpha } } } & { { \quad j = 1 , 2 , \cdots , n } } \\ { { - \lambda ( - x ) ^ { \beta } } } & { { } } \end{array} \right.
$$

其中: $\alpha$ ， $\beta$ 为风险态度系数， $\alpha , \beta < 1$ 表示敏感性递减； $\lambda$ 为损失厌恶系数，表示损失区间比收益区间更陡的特征。其曲线如图1（a）所示。

![](images/26ff35dac54f509cd9e334e39d92626b37e68864b4a1e7bf7a6170f71ffd92da.jpg)  
图1前景理论价值曲线

结合实际问题确定参考点，并基于前景理论的价值函数构建客户满意度函数，能很好地拟合客户对实际取车时间的满意度曲线。

# 1）参照点的确定

客户与客服人员约定取车时间，并以此作为心理预期，形成参照点 $d _ { j }$ 。参照点 $d _ { j }$ 受任务总的作业时间和 $\sum { p }$ 、客服人员结合车间现场因素给出的宽放时间ε的影响，dj=∑p+ε。其中， $\boldsymbol { \varepsilon } = \boldsymbol { k p } ~ , \boldsymbol { k }$ 的取值范围为[0.5,2]。当现场等待的客户数量很多时，由于"公平"从众"心理因素影响，客户能够承受更长的等待时间， $\mathbf { \sigma } _ { \varepsilon }$ 的取值较大。

2）构建客户感知不满意程度函数分析客户现场等待取车的三个场景，如图1(b)所示。

a)当任务按时完成时，客户按约定时间取车（即任务 $j$ 的取车时间 $C _ { j }$ 等于参考点 $d _ { j }$ ）。此时，客户不满意程度函数$S _ { j } ( C _ { j } )$ 对应一个基数 $S _ { 0 }$ ，设 $S _ { \mathrm { 0 } } = 0$ 。

b)当任务提前完成时，客服人员会通知客户提前取车（即$C _ { j }$ 早于参考点 $d _ { j }$ ）。此时，客户等待时间减少，处于"收益"状态，满意度提升（不满意程度为负，且下降）。但提前时间的边际效应递减，且提前时间过多会导致客户担心维修质量，进而导致感知满意度降低。所以客服人员告知客户的提前时间存在极值，用 $\boldsymbol { \xi } ^ { \prime }$ 表示。则取车时间存在最小值 $C _ { j } = d _ { j } - \xi ^ { \prime }$ ，且对

应满意度极值 $\boldsymbol { s } ^ { \prime }$ ;

c)当任务延迟完成时，客服人员会提前通知客户将延期取车（即 $C _ { j }$ 超过参考点 $d _ { j }$ ）。此时，客户等待时间增加，处于"损失"状态，不满意程度提升，结合客户"不耐烦"的心理特征，客户的不满意程度快速上升。当延长的等待时间大于特定数值时，客户会非常不满意提出投诉，进而可能流失。用 $\xi ^ { \cdot }$ 表示客户所能接受最长的延迟时间（依据现场调研， $\xi ^ { \cdot }$ 的取值为半小时左右），则取车时间大于等于 $d _ { j } + \xi ^ { " }$ 时，对应客户感知不满意函数上限 $\boldsymbol { s } ^ { \prime }$ 。

对比可见,图1(a)以坐标中心点旋转 $1 8 0 ^ { 0 }$ 形成的图像与图1(b)大致相似。图1(b)中,横坐标代表客户等待时间，其中坐标中心点的 $d _ { j }$ 代表预期等待时间；纵坐标代表客户感知不满意程度，其中坐标中心点的 $S _ { 0 }$ 代表不满意程度基数；坐标横轴以上代表客户感知不满意程度提升，存在不满意程度上限 $\boldsymbol { s } ^ { \prime }$ ；坐标横轴以下代表客户感知不满意程度下降(相当于满意度增加)，存在满意度极值 $s ^ { \prime }$ 。据此依据前景理论价值函数模型，得到一般情况下客户对实际取车时间的感知不满意程度函数，公式如下：

$$
S _ { j } { \Big ( } C _ { j } { \Big ) } = \left\{ \begin{array} { c l } { { \displaystyle S ^ { * } } } & { { \displaystyle C _ { j } = d _ { j } + \xi ^ { * } } } \\ { { \lambda _ { 1 } { \Big ( } C _ { j } - d _ { j } { \Big ) } ^ { \beta } + S _ { 0 } } } & { { \displaystyle d _ { j } \leq C _ { j } < d _ { j } + \xi ^ { * } } } \\ { { - { \Big ( } d _ { j } - C _ { j } { \Big ) } ^ { \alpha } + S _ { 0 } } } & { { \displaystyle d _ { j } - \xi ^ { * } < C _ { j } < d _ { j } } } \\ { { \displaystyle S _ { 0 } } } & { { \displaystyle C _ { j } = d _ { j } - \xi ^ { * } } } \end{array} \right. \quad \quad j = 1 , 2 , \cdots , n
$$

# 2 问题描述与建模

从优化目标、资源约束和任务约束三方面，对汽车维修车间烤漆房的调度问题进行描述，并建立优化调度模型。

# 2.1基本假设

假设1所有洗车客户都只进行简单的定期保养维护任务，即选择现场等待取车；

假设2汽车维修作业过程中工作任务在瓶颈工位开始加工则不允许中断。

# 2.2问题描述

1）优化目标

瓶颈资源的调度具有多目标特征。一方面，瓶颈存在资源短缺，调度中要提高资源利用率，可以通过最小化制造期 $C _ { \mathrm { m a x } }$ 来实现。另一方面，瓶颈工序的节奏确定了整个系统的节奏，客户对取车时间的感知不满意程度可以表示为任务在瓶颈环节完工时间的函数。据此，瓶颈环节的调度问题可描述为包含最小化制造期 $C _ { \mathrm { m a x } }$ 和客户感知不满意程度函数 $S _ { j } ( C _ { j } )$ 的多目标调度问题。

# 2）资源约束

机电工序的主要设备是举升机（包括：地藏式、两柱式、四柱式），一般车辆到达机电工序后要运用举升机举升，结合其他设备（包括：四轮定位仪、汽车诊断电脑、轮胎剥胎机、轮胎动平衡机、刹车光磨机、中央供油供气系统、汽车检测仪等）进行机电的检测和维修。不同举升机的性能和适用范围存在差异，任务只需从中选择一台进行作业，机器的数量可用m来度量。

# 3）任务约束

汽车维修车间机电工序的任务具有以下特征和约束：每个任务有具体工期 $d _ { j }$ 和加工时间 $p _ { j } ^ { i }$ （表示运用设备 $i$ 完成任务 $j$ 的时间）， $\Sigma { p } _ { j } ^ { a b }$ 表示瓶颈设备后各工序的作业时间和；任务存在设备使用限制 ${ M } _ { { j } }$ （表示任务 $j$ 只能运用的设备集合）。

# 2.3 调度模型设计

综上所述，汽车维修车间烤漆房的调度问题可描述为$Q m | M _ { j } | \theta _ { 1 } C _ { \operatorname* { m a x } } + \theta _ { 2 } \Sigma S _ { j } ( C _ { j } ^ { i } )$ ，即存在设备适用限制，以最小化制造期和客户感知不满意程度为目标的异速并行机调度问题。模型中： $\boldsymbol { x } _ { ( t ) j } ^ { i }$ 表示在时间 $\mathbf { \Phi } _ { t }$ ，设备 $i$ 是否开始用于任务 $j$ ， $\boldsymbol { x } _ { ( t ) j } ^ { i }$ 的取值有两种情况：

$$
x _ { ( t ) j } ^ { i } = \{ \begin{array} { l l } { { 1 } } &   t \mathbb H \mathbb H \mathbb H \mathbb H , \mathrm  \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \Sigma \ S \end{array}
$$

其中： $N$ 表示所有任务的集合；表示所有瓶 $M$ 颈设备的集合；$A$ 为所有线路约束 $i , k \to i$ $j$ 的集合，它限定设备 $i$ 先用于任务 $k$ ，紧接着用于任务 $j$ 。

$$
M i n \theta _ { 1 } C _ { \mathrm { m a x } } + \theta _ { 2 } \sum S _ { j } ( C _ { j } )
$$

s.t.

$$
S _ { j } \big ( C _ { j } \big ) = \left\{ \begin{array} { c c } { \displaystyle S ^ { ' } } & { C _ { j } = d _ { j } + \xi ^ { ' } } \\ { \lambda _ { 1 } \big ( C _ { j } - d _ { j } \big ) ^ { \beta } + S _ { 0 } } & { d _ { j } \leq C _ { j } < d _ { j } + \xi ^ { ' } } \\ { - \big ( d _ { j } - C _ { j } \big ) ^ { \alpha } + S _ { 0 } } & { d _ { j } - \xi ^ { ' } < C _ { j } < d _ { j } } \\ { S _ { 0 } } & { C _ { j } = d _ { j } - \xi ^ { ' } } \end{array} \right. \quad j = 1 , 2 , \cdots , n
$$

$$
C _ { j } ^ { i } = \big ( C _ { k } ^ { i } + p _ { j } ^ { i } \big ) \cdot x _ { ( t ) j } ^ { i } \qquad / \big ( i , k \to i , j \big ) \in A /
$$

$$
C _ { j } ^ { i } \geq p _ { j } ^ { i } ~ / ~ j \in N , i \in M /
$$

$$
\sum p _ { j } ^ { a b } \leq C _ { j } - C _ { j } ^ { i }
$$

$$
\sum _ { t = 0 } ^ { C _ { \mathrm { m a x } } } \sum _ { i = 1 } ^ { m } x _ { ( t ) j } ^ { i } = 1 \qquad / j \in N /
$$

$$
x _ { ( t ) j } ^ { i } \in \{ 0 , 1 \} \qquad / j \in N , i \in M /
$$

$$
\sum _ { t = 0 } ^ { C _ { \operatorname* { m a x } } } \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } x _ { ( t ) j } ^ { i } = n
$$

$$
w _ { j } \geq 0 , d _ { j } \geq 0 \qquad / j \in N /
$$

模型中，式（3）为目标函数。式 $( 4 ) \sim ( 1 0 )$ 为约束条件，其中式（4）度量了客户感知的不满意程度；式（5）度量了任务 $j$ 使用设备 $i$ 的实际完成时间；式（6）确保任务 $j$ 有足够的加工时间；式(7)保证瓶颈后各工序有足够的作业时间；式（8)保证某一特定任务只能被任意瓶颈设备服务一次，其中 $C _ { \mathrm { m a x } }$ 表示最后离开瓶颈设备的任务的完成时间；式（9）给出决策变量的取值范围；式（10）保证在所有任务都有机会开始；式（11）限定权重和预期任务完成时间的取值范围。 $n$

# 3 瓶颈设备调度问题的遗传算法设计

遗传算法是基于“适者生存"的一种高度并行、自适应和随机优化算法。研究借鉴该方法，结合具体问题，构建适应度函

数，实现汽车维修车间瓶颈设备的多目标调度。

# 3.1编码

把每个任务 $j$ 的加工设备 $a _ { j }$ 和任务在该设备上的加工次序号 $b _ { j }$ 定义成二维数组 $\begin{array} { r } { \left[ \begin{array} { l } { a _ { j } } \\ { b _ { j } } \end{array} \right] } \end{array}$ ，其中， $j = 1 , 2 , \cdots , n$ ，表示任务的数量。则 $n$ 项任务可以对应一个 $n \times 2$ 维矩阵 $\left[ \begin{array} { l } { a _ { 1 } a _ { 2 } \cdots a _ { n } } \\ { b _ { 1 } b _ { 2 } \cdots b _ { n } } \end{array} \right]$ 作为遗传算法的染色体，用于表征一个调度方案。例如：$\left[ { \begin{array} { l } { 1 3 3 1 2 2 1 2 } \\ { 2 1 2 1 3 1 3 2 } \end{array} } \right]$ 表示在设备1上加工的任务顺序为4，1，7；在设备2上加工的任务顺序为6，8，5；在设备3上加工的任务顺序为2，3。

# 3.2种群初始化

首先，随机产生 $h$ 个 $n$ 维行向量 $\left( a _ { 1 } a _ { 2 } \cdots a _ { n } \right)$ 作为染色体的第1行，其中 $a _ { j } \in M$ （ $M$ 表示所有设备的集合)；其次，根据以上随机向量确定每台设备 $i$ 上的加工任务总数 $n _ { i } \ { \stackrel { \triangledown } { \big ( } } \ \sum n _ { i } = n \ { \stackrel { \triangledown } { \big ) } }$ ；接着每一染色体中第2行与设备;相对应的元素随机地从[1,ni]中选取不重复的自然数，从而确定相应的任务在设备 $i$ 上的加工顺序。

# 3.3个体适应度的检测评估

本研究调度问题的目标是最小化客户的感知不满意程度和制造期。据此，设适应度函数为 $f \left( h \right) = \theta _ { 1 } C _ { \mathrm { m a x } } + \theta _ { 2 } \sum S _ { j } \left( C _ { j } ^ { i } \right)$

# 3.4交叉操作

首先，对两个父代个体第1行基因串进行两点交叉；接着，对两点交叉后的第2行基因串运用下述原则进行修正。假定经过两点交叉后第2 行基因串中与设备 $i$ 相应的 $n _ { i }$ 个元素为$b _ { i 1 } , b _ { i 2 } , \cdots b _ { i n _ { i } }$ ，则令其中最小值对应的新的基因值为1，次小值对应的新的基因值为2，依此类推。若交叉后，存在 $p$ 个相同的值对应新基因值 $q$ ，则从 $[ q , q + p - 1 ]$ 中随机地选取互不相同的 $p$ 个值作为修正后的相应位置的 $p$ 个基因值。例如：假设交叉的父代个体为：

$$
{ \binom { A _ { 1 } } { B _ { 1 } } } = { \left[ \begin{array} { l } { 1 3 \colon 3 1 2 \vdots 2 1 2 } \\ { 2 1 \colon 2 1 3 \vdots 1 3 2 } \end{array} \right] } , { \left[ \begin{array} { l } { A _ { 2 } } \\ { B _ { 2 } } \end{array} \right] } = { \left[ \begin{array} { l } { 3 2 \vdots 1 1 2 \vdots 3 3 1 } \\ { 1 2 \vdots 3 2 3 \vdots 2 3 1 } \end{array} \right] }
$$

符号“！"表示交叉点的位置。交叉后个体为：

$$
{ \binom { A _ { 1 } ^ { ' } } { B _ { 1 } ^ { ' } } } = { \left[ \begin{array} { l } { 1 3 \vdots 1 1 2 \vdots 2 1 2 } \\ { 2 1 \vdots 3 \underline { { 2 } } 2 3 \vdots 1 \underline { { 3 } } 2 } \end{array} \right] } , { \left[ \begin{array} { l } { A _ { 2 } ^ { ' } } \\ { B _ { 2 } ^ { ' } } \end{array} \right] } = { \left[ \begin{array} { l } { 3 2 \vdots 3 1 2 \vdots 3 3 1 } \\ { 1 \underline { { 2 } } \vdots \underline { { 2 } } 1 \underline { { 3 } } \vdots \underline { { 2 } } 3 \underline { { 1 } } } \\ { \equiv } \end{array} \right] }
$$

其中：带有下划线-， $\ c =$ 的位置表示经过交叉后第1个个体的第2 行基因串中与设备1相应的4个基因中存在相同的基因值，从而需修正基因的情形。运用上述原则进行修正，则修正交叉后个体的第2行基因串得到以下新个体：

$$
{ \left[ \begin{array} { l } { A _ { 1 } ^ { ' } } \\ { B _ { 1 } ^ { ' } } \end{array} \right] } = { \left[ \begin{array} { l } { 1 3 \vdots 1 1 2 \vdots 2 1 2 } \\ { 1 1 \vdots 3 \underline { { 2 } } 3 \vdots 1 \underline { { 4 } } 2 } \end{array} \right] } , { \left[ \begin{array} { l } { A _ { 2 } ^ { ' } } \\ { B _ { 2 } ^ { ' } } \end{array} \right] } = { \left[ \begin{array} { l } { 3 2 \vdots 3 1 2 \vdots 3 3 1 } \\ { 1 1 \vdots 2 1 2 \vdots 3 4 2 } \end{array} \right] }
$$

# 3.5变异操作

变异操作可设置为对：第1行的各个基因，随机地选取(0，1)的实数，若该实数小于变异概率 $p _ { h }$ ，则随机地从 $A _ { j }$ 中选取基因 $a _ { j } ^ { \prime }$ 替代 $a ^ { \prime }$ 。染色体的第2行基因串不进行变异操作，但为了尽可能多地保留父代信息(指同一台机器上的加工工件的先后顺序)，在第1行基因串变异完毕后采用交叉操作的修正方案进行修正，即若变异后个体的第2行基因串中与机器 $j$ 相应的 $n _ { i }$ 个元素为 $b _ { i 1 } , b _ { i 2 } , \cdots b _ { i n _ { i } }$ ，则令其中最小值对应的新的基因值为1,次小值对应的新的基因值为2，依此类推。若存在 $p$ 个相同值对应新基因值 $q$ ，则从 $[ q , q + p - 1 ]$ 中随机地选取互不相同的 $p$ 个值作为修正后的相应位置的 $p$ 个基因值。

例如，变异前个体 ${ \binom { A _ { 1 } } { B _ { 2 } } } = { \binom { 1 3 \underline { { { 3 } } } 1 2 2 1 2 } { 2 1 2 1 3 1 3 2 } }$ ，第1行基因串变异后 ${ \left[ \begin{array} { l } { A _ { 1 } ^ { ' } { \bigg ] } = { \binom { 1 3 1 1 2 2 1 2 } { 2 1 2 1 3 1 3 2 } } } \\ { B _ { 1 } } \end{array} \right] }$ 修正后 ${ \left[ \begin{array} { l } { A _ { 1 } ^ { ' } } \\ { B _ { 1 } ^ { ' } } \end{array} \right] } = { \left[ \begin{array} { l } { 1 3 \underline { { 1 } } 1 2 2 1 2 } \\ { 2 1 3 1 3 1 4 2 } \end{array} \right] }$ 其中带下划线的位置表示变异的情况。

# 3.6算法步骤

结合遗传算法模型与异速并行机问题特征，其迭代步骤如下：

a)令 $l = 0$ ，随机产生 $H$ 个初始个体构成初始种群 $Q ( 0 )$ ：b)评价初始种群中各个体的适配值（fitnessvalue）；

c)判断是否满足算法终止条件。若满足则输出结果；否则执行以下步骤；

d)令 $h = 0$ ·

e)根据适配值大小以一定方式执行复制操作来从 $Q ( l )$ 中选取两个个体；

f)若交叉概率 $p _ { c } > \xi \in \left[ 0 , 1 \right]$ ，则对选中个体执行交叉操作来产生两个临时个体；否则将选中的父代个体作为临时个体；

g)按变异概率 $\boldsymbol { p } _ { h }$ 对临时个体执行变异操作，产生两个新个体放入 $Q { \big ( } l + 1 { \big ) }$ ，并令 $h = h + 2$ ：

h)若 $h < H$ ，则返回步骤e)；否则令 $l = l + 1$ ，并返回步骤b)。

# 4 案例

现模拟汽车维修车间瓶颈设备一天的作业情况，用 $n \times m$ 标志每个组别，并应用上述方法进行调度，结合维修车间作业排序中经常使用的先到先服务规则（firstcomefirstserver,FCFS）进行比较。

通过现场调研，正常营业的汽车维修车间每天接受保养维护任务的数量范围为[20,100]，瓶颈设备的总量范围为[6,12],瓶颈设备的作业时间 ${ p } _ { j }$ 在区间[0.5,3]均匀分布。依据统计数据[13],定义 $\alpha = \beta = 0 . 8 8$ ， $\lambda _ { 1 } = 2 . 2 5$ 。参考点 $d _ { j } = r _ { j } + p + \varepsilon$ ,其中：$r _ { j }$ 表示任务到达瓶颈设备的时间，在区间[0,7]呈泊松分布； $p$ 表示任务在不同类型瓶颈设备的平均作业时间。

采用以下评价指标，定义一组满足相同特征的问题 $s$ ，令$I ( I \in S )$ 为其中的一个给定实例， $T ( H , I )$ 为针对实例 $I$ 采用启发式算法 $H$ 求得的目标函数值。则该实例在几种启发式算法下的最优解为 $B E S T ( I )$ ，且 $B E S T ( I ) = \operatorname* { m i n } \{ T ( H , I ) \}$ 。据此，对每类问题 $S$ 可以计算相对性能指标为

$$
\rho \big ( H , S \big ) = \frac { \displaystyle \sum _ { I \in S } T \big ( H , I \big ) } { \displaystyle \sum _ { I \in S } B E S T \big ( I \big ) }
$$

相对性能指标是一种评价算法优越性能的指标，通过描述某种算法得到的结果与所有算法求得结果中最优解的接近程度评价该算法的优越性如何。相对性能指标等于1，则该算法是所有算法中的最优算法；相对性能指标越接近1，表明该算法性能越好，但并不是最优算法。

所有算法均采用MATLAB编程实现，运行在奔腾双核，主频 $1 . 7 3 ~ \mathrm { G H z }$ 的计算机上进行实验仿真，测试结果如表1所示，由表上数据可得到以下结论：本文所用模型和算法的仿真结果显著优越;随问题规模的增大，指标性能的优越性更为明显。

表1调度性能比较  

<html><body><table><tr><td rowspan="2">问题n×m</td><td colspan="2">调度性能参数p(H,S)</td></tr><tr><td>GA</td><td>FCFS</td></tr><tr><td>20×6</td><td>1.000</td><td>1.017</td></tr><tr><td>60×6</td><td>1.000</td><td>1.024</td></tr><tr><td>60×8</td><td>1.000</td><td>1.028</td></tr><tr><td>100×8</td><td>1.000</td><td>1.043</td></tr><tr><td>100×12</td><td>1.000</td><td>1.051</td></tr></table></body></html>

# 5 结束语

针对当前企业中因缺乏科学规划，从而导致客户等待时间过长和设备利用率偏低的现状，本文以汽车维修车间瓶颈资源调度问题为例进行研究。在分析了取车时间提前或延迟对客户感知不满意程度影响边际效应递减的特征的基础上，引入前景理论中的价值函数，设计在取车过程中，包含一般情况和特殊情况在内的客户感知不满意度函数；并结合瓶颈资源特征，构建考虑客户感知满意度和资源效率在内的多目标调度模型，设计并提出与问题相适应的遗传算法；最后，结合案例进行系统仿真，结果表明本文所用算法在优化目标函数值上具有较大优越性。

本文的研究成果使得汽车维修车间瓶颈设备的调度更加合理，一是可以缩短客户等待取车的时间，提高客户的感知满意度，从而提高企业的核心竞争力；二是可以规范汽车维修作业的流程，提高维修设备的作业效率，降低企业的实际作业成本；三是对于服务系统的调度而言，对如何提高服务效率、降低服务成本提供了一条研究思路。

由于影响人感知和行为的因素众多、过程复杂，如何更贴切地刻画客户对调度方案的感知满意度还有待深入研究。后续计划首先运用实证方法研究对不同类别和场景下客户参考点的设置、时间敏感性和其他感知因素；其次再进一步完善对客户感知满意度函数的设计，并且设计匹配的算法对函数进行求解；最终将研究成果与实际案例结合起来。

# 参考文献：

[1]Goldratt E M,Cox J.The Goal: a process of ongoing improvement [M] NewYork: North River Press,1984.   
[2]Aktrk M,Atamtirk A,Güire S.Parallel machine match-up scheduling with manufacturing cost considerations [J]. Journal of Scheduling,2010,13 (1): 95-110.   
[3]Liao T W,Chang P C,Kuo RJet al.A comparison of five hybrid metaheuristic algorithms for unrelated parallel-machine scheduling and inbound trucks sequencing in multi-door cross docking systems [J].Applied Soft Computing,2014,21 (3): 180-193.   
[4]Balin S.Non-identical paralel machine scheduleing using genetic algorithm [J].Expert Systems with Applications,2011,38 (6): 6814-6821.   
[5]肖世昌，孙树栋，国欢．灾变遗传算法求解带时间窗的车辆调度问题 [J]．计算机应用研究,2014,31(12):3568-3571.   
[6]RodriguezFJ, Blum C, Garcia-Martinez C et al. GRASP with path-relinking for the non-identical parallel machine scheduling problem with minimising total weighted completion times [J].Annals of Operations Research,2012, 201 (1): 383-401.   
[7]Jia ZH,Leung JT.Ameta-heuristic to minimize makespan for parallel batch machines with arbitrary job sizes [J].European Journal of Operational Research,2015,240 (3): 649-665.   
[8] 赵明，宋晓宇，常春光．改进人工蜂群算法及其在应急调度优化问题中 的应用[J].计算机应用研究,2016,33(12):3596-3601.   
[9]Hjorth K,Fosgerau M. Using prospect theory to investigate the low marginal value of travel time for small tme changes [J]. Transportation Research Part B: Methodological,2012,46 (8): 917-932.   
[10] Liu A, Wuest T,Wei W,etal. Application of prospect theory on car sharing product service system [J]. Procedia CIRP,2014,16: 350-355.   
[11] Zhou L,Zhong S,Ma S,et al. Prospect theory based estimation of drivers'risk attitudes in route choice behaviors [J].Accident Analysis & Prevention,2014,73:1-11.   
[12] Kahileman D,Tversky A. Choices,values,and frames [M].New York: Cambridge University Press,2000.   
[13] Demirkol E,Mehta S V,Uzsoy R.A computational study of shifting bottleneck procedures for shop scheduling problems [J].Journal ofHeuristic, 1997, 3 (2): 111-137.