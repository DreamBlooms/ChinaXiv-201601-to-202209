# 考虑电池包数量的自动化集装箱码头多AGV调度优化问题研究

许彭锦，梁承姬

(上海海事大学 物流研究中心，上海 201306)

摘要：针对自动化集装箱码头自动引导小车(automated guided vehicle，AGV)的实际换电特性，为了降低AGV的总任务完成时间和换电总时间，合理规划换电站内的电池包数量，建立了双层规划模型。首先考虑AGV的电池续航、空重载SOC变化特性和不同剩余电量与速度变化，以降低AGV的总任务完成时间为目标，构建考虑换电的多AGV集装箱任务调度上层模型。在此基础上，为了合理规划换电站内的电池包数量，考虑自动化码头中换电站的实际电池包选取原则和换电流程，对换电站和电池包的选择进行决策，以降低换电总时间为目标，构建换电电池包配置下层模型。最后通过遗传算法分别对小规模和大规模算例进行求解。算例结果表明，此双层规划模型能够有效地减少总任务完成时间和换电总时间，提高了 $6 . 4 6 \%$ 的AGV利用率，减少了 $23 . 1 \%$ 的换电站电池包数量。

关键词：自动化集装箱码头；自动牵引车；遗传算法；电池包数量 中图分类号：U691.3 doi:10.19734/j.issn.1001-3695.2022.03.0085

# Research on multi AGV scheduling optimization of automated container terminal considering number of battery packs

Xu Pengjin, Liang Chengji (LogisticsResearch Center,ShanghaiMaritime University,Shanghai201306,China)

Abstract:Acordingtotheactualpower exchangecharacteristicsofAGVinutomatedcontainerterminal,buildatwo-level programming model toreduce the total task completion time and power exchange timeof theAGV,andreasonablyplan the numberofbatterypacks in thepower exchange station.Firstly,considering the baterylife,airand heavyloadSOCvariation characteristicsand diferentresidual powerand speed changes ofAGV,inorder to rducethetotal task completiontimeof AGV,build an upper-level modelfor multi-AGVcontainer task schedulingconsidering power exchange.On this basis,in ordertoreasonablyplanthe numberofbatterypacks inthepower exchange station,considertheactualbaterypack selection principleandpower exchange processof thepower exchange station inthe automatic wharf, makedecisions on theselection of power exchange station and batery pack,and build the lower level model ofpower exchange batery pack configuration withthegoal ofreducing the totalpower exchange time.Finally,smal-scale andlarge-scale examples are solved bygenetic algorithm.The exampleresultsshow that the two-level programming modelcan efectivelyreduce the total taskcompletion time and the total power exchange time, improve the utilization rate ofAGV by $6 . 4 6 \%$ and reduce the number of battery packs in the power exchange station by $23 . 1 \%$ ：

Key words: automated container terminal; automated guided vehicle; genetic algorithm; number ofbattery packs

# 0 引言

在连接海-陆物流运输的整个过程中，集装箱码头起了至关重要的作用。随着全球经济一体化的全面发展，“地球村"概念深入落实，传统集装箱码头的运输效率高、安全性好等优势已经无法满足全球经济发展的需要了。而自动化集装箱码头相比于传统的集装箱码头，自动化集装箱码头的最大特点就是实现了集装箱的装卸作业、堆场的装卸作业和水平运输的自动化智能化操作。在整个码头和堆场的作业区域中，不再有人的参与，而是通过由电力驱动的AGV(AutomatedGuidedVehicle)小车，来对集装箱进行装卸搬运作业，因此，纯电力驱动的AGV的作业效率，很大程度上决定着整个集装箱码头的运作效率。AGV的电量状态可用SOC(State ofCharge)来描述，即电池使用一段时间或长期搁置不用后的剩余可放电电量与其完全充电状态的电量的比值，常用百分数表示。因此， ${ \bf K i m } ^ { [ 1 ] }$ 等人对于AGV的调度问题，采用了一种时间事件发生的方法，以最小AGV工作时间和最小船舶延误时间为目标，来对AGV进行任务分配。FrankSchneider[2]等人建立一个电池交换站网络，提出了一个动态规划模型来辅助最优收费决策，模型的结果能够有效地根据动态的电价来决策是否给电池充电。XiXiang[3]等人提出了一种考虑电池管理的自动化集装箱码头性能评估的嵌套半开放排队网络模型，在模型近似解的基础上，进一步优化了系统的资源分配和布局设计。石楠路[4等人为了降低AGV的换电过程对其调度的影响，为了提高AGV的工作效率，构建了考虑AGV换电过程的混合整数调度模型。周小凡[5]等人考虑了AGV电池的续航能力和重空载的耗电差异等约束，建立以最小化AGV任务完成时间为目标的AGV调度模型。张亚绮[6等人根据电力驱动的AGV的充电需求和运输特性，考虑垂直堆场布局和 AGV充电过程对实际作业的影响，以最大化AGV充电利用率、最小化最末任务完成时间以及最小化AGV空载时间为目标，建立AGV的作业调度模型。吴洪明[等人为了提高自动化集装箱码头AGV的作业效率，考虑AGV的空载重载耗电特性以及充电的非线性的特征，建立以总任务完成时间最短为目标的AGV 调度模型。丁一[8]等人为解决多载 AGV的动态调度问题，考虑AGV的装载能力和充电后的续航能力，采用周期与事件混合驱动的滚动时域的优化策略，构建AGV动态作业调度的混合整数规划模型。郑亚红[9]等人为了减少AGV在换电站中的排队等待时间，构建AGV作业与换电的协同调度优化模型，并设计遗传算法求解模型。傅正堂[10]等人对 AGV 电量在非饱和状态下的放电特性进行研究,对该问题建立数学模型并用CPLEX求解器求解。范厚明[I]等人采用两阶段建模方法，分别建立数学模型，设计枚举法和遗传算法来对双小车岸桥和AGV进行联合配置；宋绍京[12]等人为解决合理规划 AGV数量，以AGV工作效率最大化为目标，结合车间大小和AGV自身特性等因素建立数学模型，通过实际应用场景，验证了模型的有效性。黄宇超[13]从换电站的布局设计、换电站内的设备设施布局以及AGV的调度系统等方面进行分析，设计新的布局方案，通过对比分析，验证了方案的有效性。樊陆彬[14]等人从不确定性的角度出发，分别建立集卡分派子模型和集卡配置子模型，并将完工时刻和集卡数量作为公用设计变量连接两个子模型，通过算例求解该耦合模型，使得延误成本和集卡数量得到有效的减少，验证了模型的有效性。陈香玲[15]等人为了提高AGV在物流中心的工作效率，考虑AGV在搬运工作过程中的电量消耗和其充电特性，提出以AGV剩余电量和包裹时间窗等约束条件，以最小化分拣作业周期为目标的混合整数规划(MIP)模型和约束规划(CP)模型，通过实例分析，验证了模型性能的有效性。

综上可知，在对自动化集装箱码头AGV调度的研究中，大多数是针对AGV的换电模式和策略，对影响AGV换电的因素考虑的还不够全面。因此，本文在已有研究基础上，首先考虑AGV的电池续航及空重载SOC变化特性和不同剩余电量下的空重载速度变化，提高电池包利用率，以降低AGV的总任务完成时间为目标，构建考虑换电因素的AGV集装箱任务调度的上层模型。为了对集装箱任务调度过程中产生的换电任务进行调度，且合理规划换电站内的电池包数量，本文考虑自动化码头中换电站的实际电池包选取原则和换电流程，对换电站和电池包的选择进行决策，以降低换电总时间为目标，构建换电电池包配置下层模型，与上层模型构成解决集装箱任务调度和换电任务调度的双层模型。

# 1 问题描述

图1为垂直式自动化集装箱码头的实际布局示意图，整个自动化码头可分为三个区域：自动化堆场、AGV工作区域和岸桥工作区域，而换电站以及换电站配套设施需要较大的占地面积，一般会布局在AGV行车主干道的尽头两侧。在自动化集装箱码头中，通过利用纯电驱动的AGV来对集装箱进行装卸搬运作业，即将不同的集装箱搬运至相应的堆场缓存区和岸桥缓存区，具体布局如图1。

![](images/4a741cc59c8059d985a7e78ac033055f08c9e8d9cf64fc07b708d5644b6301cc.jpg)  
图1自动化码头垂直式布局图  
Fig.1Vertical layout of automatic Wharf

如图1，在混合装卸作业模式下，AGV小车此次的出口集装箱任务的起点在堆场3，AGV行驶至堆场3处的交互区，从缓冲支架上取得出口集装箱后，根据既定路线，通过行车主干道，将此集装箱运送至对应的岸桥门架小车处进行集装箱交接，若下一个进口集装箱的起点不在此岸桥的中转平台上，则空车行驶至进口集装箱所在中转平台的岸桥处，取得此进口集装箱后，将其运送至对应的终点堆场1处。

在完成一个集装箱任务后，需要判断AGV的剩余电量是否低于阈值，或者是否能够完成下一个集装箱任务，如果不能，则需要去换电站进行换电任务作业，如果满足，则继续执行集装箱任务作业。并且此时还需要根据AGV自身的剩余电量来选择不同的运行速度，当剩余电量较低的时候，为了提高电池的利用率，AGV的运行速度将会有所降低。

在实际换电站中，换电站的硬件设备主要是由换电机器人、充电机组和电池仓组成，电池包的更换流程为：当需要换电的AGV驶向目标换电站，从换电站的一端入口驶入到达指定的换电工位后，由换电机器人从电池仓中选取符合换电要求的电池包，对AGV进行电池包更换，在目前洋山港四期自动化码头中，换电站进行一次更换电池包的平均操作时间为 $3 0 0 \mathrm { s }$ 。与此同时，充电机组将会对从AGV上更换下来的乏电电池包进行充电。当AGV更换好电池包后，从换电站的另一端驶出换电站，驶向下一任务的发箱位置，继续搬运执行任务。

![](images/eb3a81d4315ac914e35248869d2b241ec1809265024e5c43af902b5229c2200e.jpg)  
图2AGV换电流程图  
Fig.2AGV power exchange flow chart

在图2中：当AGV产生换电需求时，首先会根据这一次去不同换电站换电的总时间，判断是去大换电站还是小换电站，紧接着执行换电任务。当AGV到达某换电站的换电工位时，换电机器人需要对电池包的选取作出决策，满电状态和电池仓内SOC最高的电池作为优先选择，由于换电站内是采取边换边充的模式，即换电机器人选取电池包进行换电的同时，充电机组会对换电站内的电量不足的电池包进行充电，这会存在一个最低允许换电电量 $\mathrm { P v }$ ，即当电池仓内的所有电池SOC均小于Pv，则AGV需要等待有电池包充电至Pv，然后更换此电池包再驶出换电站。并且在换电机器人选择SOC最高的电池包进行换电作业时候，如果可选择的电池包有多个，则选取使用次数较多的那一个电池包进行换电作业。

# 2 模型建立

# 2.1上层AGV集装箱任务调度模型

# 2.1.1模型假设

a)AGV初始电量为 $100 \%$ b)在作业过程中，不考虑设备故障以及碰撞等突发因素；c)岸桥、场桥的每个装卸任务的操作顺序和操作时间已知;d)所有集装箱大小均为40 英尺，一辆 AGV一次装载一个集装箱。

# 2.1.2符号说明

本文上层模型使用的符号如表1所示。

表1上层模型的符号说明  
Tab.1Symbol description of upper layer model   

<html><body><table><tr><td>符号</td><td>含义</td></tr><tr><td>V</td><td>V={vo}虚拟开始任务集合</td></tr><tr><td>V</td><td>V={vo}虚拟结束任务集合</td></tr><tr><td>V</td><td>V={1.2.3...t装卸任务集</td></tr><tr><td>K</td><td>K={1.,2....k}，.AGV集合</td></tr><tr><td>Vk</td><td>第k台AGV对应的换电任务集合</td></tr><tr><td>Vb</td><td>V=VVUVU....UV,全部换电任务集合</td></tr><tr><td>V</td><td>V=VUVUV UV,,任务集合</td></tr><tr><td>s1ki s2ki</td><td>第k台AGV执行第i个装卸任务时的空重载速度</td></tr><tr><td>r rr</td><td>AGV空重载和停车每秒耗电百分比</td></tr><tr><td>MC</td><td>执行换电任务的最低电量</td></tr><tr><td>ty tq</td><td>岸桥场桥的平均操作时间</td></tr><tr><td>afix</td><td>一次更换电池包的操作时间</td></tr><tr><td>WWki</td><td>第k台AGV执行换电任务i的排队时间</td></tr><tr><td>fdi</td><td>i任务发箱位置与收箱位置的距离</td></tr><tr><td>qei</td><td>i任务的最早允许开始时刻</td></tr><tr><td>Dij</td><td>i任务终点与j任务起点的距离</td></tr><tr><td>edki</td><td>执行i任务的空驶距离，从紧前任务终点到i任务起点的距离</td></tr><tr><td>Zki</td><td>第k台AGV执行i任务的完成时刻</td></tr><tr><td>Wki</td><td>第k台AGV执行i任务的岸边等待时长</td></tr><tr><td>bki</td><td>第k台AGV开始i任务的电池包剩余电量百分比</td></tr><tr><td>bbki</td><td>第k台AGV完成i任务的电池包剩余电量百分比</td></tr><tr><td>Xki</td><td>决策变量，若第k台AGV在执行任务i之后执行任务j，则</td></tr><tr><td colspan="2">xkij=1，否则为0</td></tr></table></body></html>

# 2.1.3模型建立

式(1)为目标函数，表示最小化最大完工时间;

s.t.

$$
\mathrm { F } \geq \mathrm { Z } _ { \mathrm { k i } } , \forall \mathbf { k } \in \mathbf { K } ; \mathbf { i } \in \mathbf { V }
$$

$$
\sum _ { i \in V _ { 0 } } x _ { k i j } = 1 \quad \forall j \in \mathbf { V } ; k \in K
$$

$$
\sum _ { j \in V _ { 0 } ^ { \prime } } x _ { k i j } = 1 , \forall j \in \mathbf { V } ; k \in K
$$

$$
\sum _ { k \in K } \sum _ { i \in V _ { t } } x _ { k i j } = 1 , \forall j \in V
$$

$$
\sum _ { k \in K } \sum _ { j \in V _ { t } } x _ { k i j } = 1 , \forall i \in V
$$

$$
\sum _ { i \in V } x _ { k i h } = \sum _ { j \in V } x _ { k h j } , \forall h \in V _ { b } \cup V _ { t } ; k \in K
$$

$$
e d _ { k i } = \sum _ { j \in V } x _ { k j i } D _ { j i } , \forall k \in K , i \in V
$$

$$
w _ { k i } = \left\{ \begin{array} { l l } { q e _ { j } - x _ { k i j } \cdot ( z _ { k i } + e d _ { k i } \mathrm { \prime } s _ { 1 } ) , \forall k \in K ; j \in V _ { \mathrm { t } } ; i \in V } \\ { W W _ { k i } , \forall k \in K , i \in V _ { k } } \end{array} \right.
$$

$$
\mathbf { Z } _ { k j } = \left\{ \begin{array} { l } { z _ { k i } + x _ { k i j } \cdot ( w _ { k j } + e d _ { k j } \ ⁄ s _ { 1 } + f d _ { k j } / \ : s _ { 2 } + t y + t q ) , \forall k \in K ; j \in V _ { \mathrm { t } } ; i \in V } \\ { \mathbf { z } _ { k i } + x _ { k i j } \cdot ( w _ { k i } + a _ { f i x } + e d _ { k i } / \ : s _ { 2 } ) , \forall k \in K ; j \in V _ { k } ; i \in V _ { t } } \end{array} \right.
$$

$$
b _ { k j } = b b _ { k i } + M ( 1 - x _ { k i j } ) , \forall k \in K ; i \in V ; \forall j \in V _ { \mathrm { t } }
$$

$$
b _ { k j } \leq M C , \forall k \in K ; j \in V _ { b }
$$

$$
b b _ { k i } = \left\{ { 1 0 0 \mathcal { T } _ { o } } , \forall k \in K ; i \in V _ { 0 } \cup V _ { b } \right.
$$

$$
\sum _ { \forall i \notin V _ { k } } x _ { k i j } = 0 , \forall k \in K ; j \in V
$$

$$
\sum _ { i \in V } x _ { k i j } \le s , \forall k \in K ; j \in V _ { k }
$$

$$
\sum _ { \forall h \in V _ { t } } x _ { k h i } - \sum _ { \forall h ^ { \prime } \in V _ { t } } x _ { k h ^ { \prime } j } \leq 0 , \forall k \in K ; i , j \in V _ { k } , j \leq i
$$

$$
\begin{array} { r } { \mathrm { s } 1 _ { k i } = \left\{ \begin{array} { l l } { s 1 , 0 < b _ { \mathrm { k i } } \leq p s 1 } \\ { s 1 , p s 1 < b _ { \mathrm { k i } } \leq p s 2 \quad , \forall k \in K ; i \in V _ { t } } \\ { s 1 ^ { \ast } , p s 2 < b _ { \mathrm { k i } } \leq 1 0 0 \% } \end{array} \right. } \end{array}
$$

$$
\begin{array} { r } { \mathrm { s } 2 _ { k i } = \left\{ \begin{array} { l l } { s 2 , 0 < b _ { \mathrm { k i } } \leq p s 1 } \\ { s 2 ^ { \cdot } , p s 1 < b _ { \mathrm { k i } } \leq p s 2 \quad , \forall k \in K ; i \in V _ { t } } \\ { s 2 ^ { \cdot } , p s 2 < b _ { \mathrm { k i } } \leq 1 0 0 \% } \end{array} \right. } \end{array}
$$

$$
x _ { k \mathrm { i } j } \in \{ 0 , 1 \} , \forall \mathbf { k } \in K ; i , j \in V
$$

$$
Z _ { k i } > 0 , f > 0 , b b _ { k i } > 0 , b _ { k i } > 0 , w _ { \mathrm { k i } } \geq 0 , e d _ { \mathrm { k i } } \geq 0 , \forall \mathbf { k } \in K ; i \in V 
$$

式(2)表示最终任务完成时间不小于任意任务的完成时间；式(3)和(4)表示每台AGV必须完成虚拟开始和虚拟结束任务；式(5)和(6)表示每个任务仅有一个紧前和后继任务；式(7)表示中间任务必须运输平衡，即输入等于输出；式(8)表示AGV执行任务时的空驶距离；式(9)表示普通任务和换电任务等待时间的计算；式(10)表示普通任务和换电任务完成时间的计算；式(11)表示搬运任务开始时AGV的剩余电量更新：式(12)表示换电任务开始时，AGV剩余电量不大于换电阈值；式(13)表示AGV普通任务和换电任务完成时的剩余电量更新，换电任务完成时电量为 $100 \%$ ；式(14)表示 AGV只能执行属于自己的n个虚拟换电任务；式(15)为一台AGV的换电次数之和，不允许超过最多换电次数s；式(16)表示一台AGV若换电i次，只能完成前i个换电任务；式(17)和(18)为不同剩余电量区间下，AGV空重载的速度差异；式(19)和(20)为变量的约束。

# 2.2下层电池包配置模型

# 2.2.1模型假设

a)不考虑换电工位维护等因素；  
b)每个换电站遵循先到先服务的原则；  
c)电池仓内电池初始电量均为 $100 \%$ d)每个换电工位同一时刻仅为1台AGV更换电池包；  
e)不考虑电池包使用寿命和成本的影响；

# 2.2.2符号说明

本文下层模型使用的符号如表2所示。

# 2.2.3模型建立

式(21)为目标函数，表示最小化AGV总换电时间；

$$
F ^ { \prime } { = } { \sum _ { \mathrm { k } \in \cal K } } { \sum _ { { u } \in \cal U } } ( F \mathrm { t } _ { u k } - S \mathrm { t } _ { u k } )
$$

$$
\sum _ { t \in T } p _ { { \mathrm u k } t } { = } 1 , \forall { \mathbf k } \in { \mathbf K } ; { \mathbf u } \in U _ { k }
$$

$$
\sum _ { k \in K } \sum _ { t \in T } \sum _ { u \in U } q _ { t u z k } = 1 , \forall z \in Z
$$

$$
\boldsymbol { F } \mathrm { t } _ { \mathrm { u } k } = ( L _ { u k t } + D D _ { \mathrm { u k t } } / s _ { 2 } ) \cdot \boldsymbol { p } _ { u k t } , \forall u \in \boldsymbol { U } _ { \mathrm { k } } , k \in \boldsymbol { K } \ , t \in \boldsymbol { T }
$$

$$
A \mathrm { t } _ { u k t } = S t _ { u k } + p _ { \mathrm { u } k t } \cdot D D _ { \mathrm { u } k t } \textit { s } _ { 2 } , \forall u \in U _ { \mathrm { k } } , \mathbf { t } \in \mathrm { T } , k \in K
$$

$$
U _ { t u z k } = \left\{ \begin{array} { l l } { q _ { t u z k } \cdot l d c c _ { t u z } , i f l _ { t u z k } \geq E C } \\ { q _ { t u z k } \cdot E C , i f l _ { t u z k } < E C } \end{array} \right. , \forall u \in U _ { \mathbf { k } } , \mathbf { t } \in \mathrm { T } , k \in K , z \in Z
$$

$$
l l d c c _ { t u z } = q _ { t u z k } l _ { t u z k } , \forall u \in U _ { \mathrm { k } } , \mathbf { t } \in \mathbf { T } , k \in K , z \in Z
$$

$$
l d c c _ { t u z } = \operatorname* { m a x } \{ 1 0 0 \% , ( C t _ { u ^ { \prime } k t z } - L t _ { u k t z } ) \cdot \nu e \} , \forall u \in U _ { \mathbf { k } } , \mathbf { t } \in \mathbf { T } , k \in K , z \in Z
$$

$$
W W _ { \mathrm { u } k t z } \leq \left\{ \begin{array} { l l } { \operatorname* { m a x } ( 0 , L t _ { u ^ { \prime } k ^ { \prime } t } - A t _ { u k t } ) \mathrm { ~ , i f ~ } \boldsymbol { 1 } _ { u z k } \geq E C } \\ { \operatorname* { m a x } ( 0 , L t _ { u ^ { \prime } k ^ { \prime } t } - A t _ { u k t } ) + \mathbf { q } _ { u z k } \cdot \left( \mathrm { E C } - \boldsymbol { 1 } _ { u z k } \right) / \mathrm { v e } \mathrm { , i f ~ } \boldsymbol { 1 } _ { u z k } < E C } \end{array} \right.
$$

$$
\forall \mathsf { t } \in \mathrm { T } , k , k ^ { \prime } \in K , \mathsf { u } \in { U } _ { \mathrm { k } } , u ^ { \prime } \in { U } _ { \mathrm { k } } , z \in Z ;
$$

$$
N + n \leq M
$$

$$
C t _ { \mathrm { u } k t z } = p _ { u k t } \cdot q _ { t u z k } \left( A _ { u k t } + W _ { \mathrm { u } k t z } \right) ; \forall u \in U _ { \mathrm { k } } ; t \in T ; k \in K , z \in Z
$$

$$
L \mathrm { t } _ { u k t z } = C \mathrm { t } _ { u k t z } + a _ { f i x } , \forall u \in U _ { \mathrm { k } } , t \in T , k \in K , z \in Z
$$

$$
\begin{array} { r } { \mathtt { p } _ { \mathtt { u k t } } \in \{ 0 , 1 \} , \forall \mathtt { t } \in \mathrm { T } , k \in K , u \in U _ { \mathrm { k } } , } \end{array}
$$

$$
q _ { t u z k } \in \{ 0 , 1 \} ; \forall \mathrm { t } \in \mathrm { T } , \mathrm { k } , \in \mathrm { K } , \mathrm { u } \in \mathrm { U } _ { K } , \mathrm { z } \in \mathrm { Z }
$$

式(22)表示AGV换电总时间的计算；式(23)表示一台AGV一次换电只能选择一个换电站；式(24)表示每一块电池包每次换电任务只能服务一台AGV；式(25)表示换电完成后到达后继任务起点位置的时刻；式(26)表示到达换电站时刻，即本次换电指令产生时刻与驶向换电站空驶时间之和；式(27)表示换电后AGV电池包电量更新，即所选电池电量需大于最低允许换电电量EC；式(28)表示每次换电任务结束后，电池仓内本次被用过的电池包电量的更新，更新为从AGV上换下来的电量不足的电池包电量；式(29)表示每次换电任务开始时，电池仓内电池包的电量更新，即本次换电开始时间和上一次换电结束时间之差与充电机组充电速率的乘积；式(30)表示换电站等待时长的计算，若到达换电站时前一台AGV尚未完成换电则排队等待，若所选换电电池包电量低于最低换电电量时，则充电等待；式(31)表示大小换电站的电池初始总数量不得多于换电总次数；式(32)表示换电工位开始操作时刻的计算，即到达换电站时刻与排队时长之和；式(33)表示电池包更换完成时刻，即换电开始时刻加上换电的操作时长；式(34)和(35)为变量的约束。

表2下层模型的符号说明  
Tab.2Symbols for lower level model   

<html><body><table><tr><td>符号</td><td>含义</td></tr><tr><td>K</td><td>K={1,2.3....)，AGV集合</td></tr><tr><td>Vk</td><td>Vk={1,2..n},第k台AGV对应的换电任务集合</td></tr><tr><td>Vb</td><td>V=VUVUVU..UV,全部换电任务集合</td></tr><tr><td>T</td><td>T={1,2.3..t)，换电站集合</td></tr><tr><td>Z</td><td>Z={1，2，，z}，电池包集合</td></tr><tr><td>Uk</td><td>换电需求集合，由调度模型可得</td></tr><tr><td></td><td>uEU,U=UUUU...UUk</td></tr><tr><td>W</td><td>换电站换电任务集合</td></tr><tr><td>Nn</td><td>大小换电站的初始电池数量</td></tr><tr><td>s1 s2</td><td>AGV空重载状态下的运行速度</td></tr><tr><td>MC EC</td><td>执行换电任务的最低电量</td></tr><tr><td>M</td><td>允许换电的电池包电量阈值</td></tr><tr><td>afix</td><td>AGV的总换电次数</td></tr><tr><td>ve</td><td>一次更换电池包的操作时间</td></tr><tr><td>Stuk</td><td>换电站的电池包充电速率</td></tr><tr><td></td><td>第k台AGV第u次换电指令产生时刻 第k台AGV完成第u次换电后，到达换电后继任务</td></tr><tr><td>Ftuk</td><td>发箱位置的时刻</td></tr><tr><td>Dukt</td><td>换电站t第u次换电驶向后继任务起点的距离</td></tr><tr><td>Atukt</td><td>第k台AGV第u次换电选择t号换电站的到达时刻</td></tr><tr><td>Ctuktz</td><td>第k台AGV第u次换电选择t号换电站中的z号电</td></tr><tr><td>WWukrz</td><td>池包换电开始操作时刻 第k台AGV第u次换电选择t号换电站中的z号电</td></tr><tr><td></td><td>池包换电的排队时长 第k台AGV第u次换电选择t号换电站中的z号电</td></tr><tr><td>Ltuktrz</td><td>池包换电完成时刻</td></tr><tr><td>luck</td><td>第k台AGV在t换电站进行第u次换电开始时的电 池电量</td></tr><tr><td>ldcc</td><td>第k台AGV在t换电站进行第u次换电结束时的电 池电量</td></tr><tr><td>ldcc uz</td><td>换电站t中第u次换电开始时z号电池包的电量</td></tr><tr><td>lldcc.uz</td><td>换电站t中第u次换电结束时z号电池包的电量</td></tr><tr><td>Pukt</td><td>决策变量，若第k台AGV第u次换电时选择t号电</td></tr><tr><td></td><td>站，则Put=1，否则为0</td></tr><tr><td>qtuzk</td><td>决策变量，若换电站t的z号电池服务第k台AGV 的第u次换电，则qm=1，否则为0</td></tr></table></body></html>

# 3 遗传算法

考虑换电过程和电池包数量的自动化集装箱码头的多AGV调度问题，在本质上与多循环的VRP问题是相似的，也属于NP-hard问题，此类问题的特点就是多循环、高度并发性以及容易陷入局部最优，而遗传算法恰好是一种能够实现高度并发以及全局搜索的全局优化算法，具有很好的收敛性和鲁棒性，并且遗传算法还有灵活的编码方式，可以实现实数编码和二进制编码等，简单有效的编码规则，能够使其遗传操作和种群更新的过程中产生更少的非法解，因此，本文采用遗传算法来求解研究的问题，以获得其近似最优解。

# 3.1染色体编码

本文的遗传算法编码方式采用的是实数编码，实数编码能够很直观用染色体来表达实际问题，如图3，为上层AGV集装箱任务调度模型的一条染色体编码，可以看出整个染色体分为两段，每段染色体上都有 $\mathfrak { n }$ 个基因，n表示集装箱任务的数量，前 $\mathfrak { n }$ 个基因表示 $\mathfrak { n }$ 个集装箱任务的序号，后n个基因表示执行这 $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 个集装箱任务对应的AGV序号，即在2n个基因中，第i( $\mathrm { i } { < } = \mathrm { n } \mathrm { \backslash }$ 个基因表示的集装箱任务序号，它是由第 $\mathrm { i } { + } \mathrm { n }$ 个基因表示的AGV序号进行作业的。

![](images/52c86941dc9f49a150b6477801c15ea87c92f7cf96f2a3de2584ef91a7b5c6d8.jpg)  
图3上层模型染色体编码示意图

下层AGV换电调度模型的染色体编码原理同上层模型，在图4中：整个染色体分为前后两段，前段染色体的基因值1表示小换电站，2表示大换电站。前后两段染色体的长度为在上层调度模型中所有AGV产生的换电次数，后半段染色体的基因值表示换电站中的电池编号，图4染色体中前后段的第一个基因值表示的是：在AGV产生的所有换电需求中，第一次执行换电任务去小换电站，且在小换电站中换电机器人选择2号电池包进行换电作业。

![](images/c778e1cb4b6cb0331bdd16dd3499fa45ff8b4b3786a6c8409cd513cb10535ad2.jpg)  
Fig.3Chromosome coding diagram of upper model   
图4下层模型染色体编码示意图  
Fig.4Chromosome coding diagram of lower model

# 3.2遗传操作

3.2.1选择

本文的双层模型中，均采用的是轮盘赌选择算子，具体的选择步骤如下：

a)：计算每个个体的适应度值 $\mathrm { F m }$ b)：计算每个个体遗传到下一代的概率 $ { \mathrm { P m } }$ c)：计算出每个个体的累计概率 $\mathrm { { C m } }$ d)：产生一个随机数 $\mathbf s \in ( 0 , 1 ]$ ，如果 $\mathrm { C m } { - } 1 \leq \mathbf { s } \leq \mathrm { C m }$ ，则第 $\mathrm { ~ m ~ }$ 个个体被选择;e)：重复步骤4，直到种群数量等于初始种群数量；

# 3.2.2交叉与变异

在上层模型中，采用的是两点交叉和两点变异的遗传操作。

交叉过程为：选取两条父代染色体M1和M2，在两条父代染色体上随机选取两个交叉点r1、r2，将M1上两个交叉点之间的染色体片段 p1与 M2上两个交叉点之间的染色体片段p2进行交叉互换，进而得到两条子代染色体m1和 $\mathbf { m } 2$ 。但是，由于染色体前后两段的基因值表示的实际意义的不同，因此在交叉的时候，不能跨段交叉，并且由于一个集装箱只能被一台AGV搬运的约束，因此在p1与p2交叉互换过后，片段中与染色体中重复的基因值需要更新为整条染色体缺少的基因值，具体的交叉过程示意图，如图5。

![](images/c585d112d1306ea75f4fa2b0b3726f8995f00ac567ee09be9bf801a74fe3004f.jpg)  
Fig.5Schematic diagram of crossing process

两点变异的具体过程为：在一条父代染色体上的前后两段染色体中，分别随机选取一个变异基因位置q1、q2，由于前段染色体表示集装箱任务编号，后段染色体表示相对应的AGV编号，且一台AGV一次只能搬运一个集装箱，因此分别对在前后段两个变异位置上的基因进行集装箱任务编号变异和AGV序号变异，并且从而得到两条子代染色体。具体的变异过程示意图，如图6。

![](images/81aa6ecc4012f27b670493ee268d94932d2695de82f275d78f9d0d56dc6f36d6.jpg)  
图5交叉过程示意图

下层模型的交叉变异的方式和上层模型中的基本相同，由于下层模型的染色体基因个数没有上层模型的规模大，因此为了不破坏染色体的遗传特性，下层模型的交叉和变异采取单点交叉和单点变异的遗传操作。

# 3.3适应度函数

本文构建的双层模型的目标函数分别是最小化最大完工时间和最小化总换电时间，通过解码染色体，最后一个集装箱任务被完成的时间即为最大完工时间，换电完成时刻与换电需求产生时刻的差为一台AGV的换电总时间，即换电总时间为驶向换电站的时间、等待换电的排队时间、等待电池包充电的时间与驶出换电站到达后继任务始点的时间之和。取二者的倒数，分别作为上下层遗传算法中的适应度函数。

# 4 算例分析

# 4.1参数设置

为了评估本文所建立的双层模型的有效性，利用Matlab软件，对以下算例进行求解分析。设计100个集装箱，5台AGV的算例，对于每一个集装箱任务的最早开始时间、起始位置和终止位置等属性，如表3所示。设置种群规模 $\mathrm { N P } { = } 5 0$ 最大迭代次数 $\scriptstyle \mathbf { M } = 1 0 0$ ，在双层遗传算法中，上层交叉概率和变异概率分别为 $\mathtt { p _ { c } } \mathtt { = } 0 . 7$ 、 $\mathsf { p } _ { \mathrm { m } } { = } 0 . 0 1$ ，下层交叉概率和变异概率分别为 $\mathrm { P _ { C } = 0 . 5 , \mathrm { P _ { M } = 0 . 0 1 } }$ 。设置AGV的换电SOC阈值为 $30 \%$ 当AGV的SOC在 $( 0 , 3 0 \% ]$ 区间，其空载运行速度为 $2 . 5 \mathrm { m / s }$ 当AGV的SOC在 $[ 3 0 \% , 6 0 \% ]$ 区间，其空载和重载两种状态的速度分别为： $3 \mathrm { m } / \mathrm { s } , 2 . 5 \mathrm { m } / \mathrm { s }$ ，当SOC在 $[ 6 0 \% , 1 0 0 \% ]$ 区间内，其空重载的速度分别为 $4 ~ \mathrm { m / s }$ 、 $3 ~ \mathrm { m / s }$ ，空载和重载状态下每米耗电速率分别为： $0 . 0 1 \%$ 、 $0 . 0 2 5 \%$ ，当AGV停车等待时，其每秒耗电速率为 $0 . 0 0 5 \%$ 。且一共有两个换电站，一大一小，分别位于AGV行车道的尽头两端，每个换电站设置一个换电工位，且换电站-场桥-岸桥的距离如表4所示，场桥和岸桥执行一次任务分别花费90s和120s，每个换电站的换电机器人换电速率为 $3 0 0 \mathrm { s } /$ 次，大换电站中电池仓内的初始电池包数量是30个，小换电站内有15个，换电站内采取的换电策略是边换电，充电机边充电，最低可换电电量 $\mathrm { P v } { = } 6 0 \%$ ，且参考对电动公交车的研究，设置充电机的充电速率为：每充电一分钟，电池包获得 $8 \mathrm { { m i n } }$ 的续航时间。

Tab.3Attribute table of container task   

<html><body><table><tr><td>任务编号</td><td>任务类型</td><td>任务起点</td><td>任务最早开始时间(s)</td><td>任务终点</td></tr><tr><td>1</td><td>卸船</td><td>QC3</td><td>118</td><td>YC3</td></tr><tr><td>2</td><td>卸船</td><td>QC1</td><td>182</td><td>YC3</td></tr><tr><td>3</td><td>装船</td><td>YC 2</td><td>244</td><td>QC1</td></tr><tr><td>：</td><td>：</td><td>：</td><td>：</td><td>：</td></tr><tr><td>500</td><td>装船</td><td>YC 4</td><td>24420</td><td>QC 2</td></tr></table></body></html>

表4换电站-场桥-岸桥距离表/m

表3集装箱任务属性表  
Tab.4Distance between exchange station,yard bridge and shore bridge   

<html><body><table><tr><td>小</td><td>QC1</td><td>QC2</td><td>QC3</td><td>YC1</td><td>YC2</td><td>YC3</td><td>YC4</td><td>YC5</td><td>大</td></tr><tr><td>小</td><td>0</td><td>360 185</td><td>225</td><td>265</td><td>100</td><td>140</td><td>180</td><td>220</td><td>260</td></tr><tr><td>QC1</td><td>360 0</td><td>265</td><td>225</td><td>185</td><td>260</td><td>220</td><td>180</td><td>140</td><td>100</td></tr><tr><td>QC2</td><td>185 265</td><td>0</td><td>40</td><td>80</td><td>45</td><td>85</td><td>125</td><td>165</td><td>205</td></tr><tr><td>QC3</td><td>225 225</td><td>40</td><td>0</td><td>40</td><td>85</td><td>125</td><td>165</td><td>205</td><td>245</td></tr><tr><td>YC1</td><td>265 185</td><td>80</td><td>40</td><td>0</td><td>125</td><td>165</td><td>205</td><td>245</td><td>285</td></tr><tr><td>YC2</td><td>100 260</td><td>45</td><td>85</td><td>125</td><td>0</td><td>40</td><td>80</td><td>120</td><td>160</td></tr><tr><td>YC3</td><td>140 220</td><td>85</td><td>125</td><td>165</td><td>40</td><td>0</td><td>40</td><td>80</td><td>120</td></tr><tr><td>YC4</td><td>180 180</td><td>125</td><td>165</td><td>205</td><td>80</td><td>40</td><td>0</td><td>40</td><td>80</td></tr><tr><td>YC5</td><td>220 140</td><td>165</td><td>205</td><td>245</td><td>120</td><td>80</td><td>40</td><td>0</td><td>40</td></tr><tr><td>大</td><td>260</td><td>100</td><td>205</td><td>245</td><td>285</td><td>160</td><td>120</td><td>80</td><td>40 0</td></tr></table></body></html>

# 4.2小规模双层模型结果分析

基于上述的参数设置，将此规模的算例和相关参数代入遗传算法进行求解，上层模型的适应度函数收敛过程如图7所示，求解结果如表5所示。从得到近似最优解中可知，此规模的算例中，上层模型的结果为：最大完工时间为 $1 6 7 \mathrm { m i n }$ ，且期间只进行了1次换电，此次换电发生在3号AGV的作业过程中。继续运行下层模型的代码，得下层模型的结果为：此次换电去的是小换电站，换的是4号电池包，换电总时间为 $1 0 . 4 1 6 7 \mathrm { { m i n } }$ 。第3辆AGV的任务作业顺序及时间的甘特图如图8，可知3号AGV一共执行了18个集装箱任务，执行了1个换电任务。

![](images/3cb0b21deb40e3416b8d89b112d2eddb5d43058e5133939de3ad52f558fea08b.jpg)  
Fig.6Schematic diagramof variation process   
图7小规模算例上层模型适应度函数进化曲线图

![](images/9c41b95fb4dc328cfb7a3a3a26b7cf10e68d104422d389b492062cf0a70e5b0b.jpg)  
图6变异过程示意图  
Fig.7Evolution curve of fitness function of upper model under smallscale example   
图8AGV作业甘特图  
Fig.8Gantt chart of AGV operation

Tab.5Numerical results of small-scale calculation example   

<html><body><table><tr><td>换电 次数</td><td>生时间</td><td>换电需求产 换电AGV 序号</td><td>换电 地点</td><td>池包</td><td>时间</td><td>换电电 最大完工换电总时 间</td></tr><tr><td>1</td><td>50.87min</td><td>3</td><td>小换 电站</td><td>4</td><td></td><td>167min 10.4167min</td></tr></table></body></html>

# 4.3大规模双层模型结果分析

小规模算例验证了双层模型的有效性后，将算例规模扩大至集装箱数量 $\scriptstyle \mathtt { n } = 5 0 0$ ，AGV的数量 $\scriptstyle \mathbf { a } = 1 0$ ，对双层模型进行遗传算法求解可知，上层模型输出的结果为：AGV最大完工时间为 $6 3 2 . 6 \mathrm { { m i n } }$ ，10台AGV共进行13次换电，且以3号AGV为例，其作业顺序如表6所示，可知其在执行第77和1号集装箱任务后，产生换电需求。

表63号AGV作业顺序  

<html><body><table><tr><td colspan="2">AGV序号 作业顺序</td></tr><tr><td>3</td><td>334→197→472→462→451→232→482→290→171→385 >308→77→换电→70→216→356→497→318→107→421 →227→58→168→21→437→474→274→201→239→341 →18→28→1→换电→92→426→134→253→473→369→</td></tr></table></body></html>

继续运行得出下层模型的运行结果，其中，下层模型的适应度函数进化结果如图9所示。下层模型中输出的结果为：AGV换电总时间为 $1 6 7 . 8 5 \mathrm { m i n }$ ，且每台AGV的换电次数、换电需求产生时的时间、剩余电量、换电场所、换电电池包编号见表7。

![](images/968d263d052e0520ea514b8820b69122de695329db89cf13be8bc894653f74e9.jpg)

Tab.6Operation sequence of AGV No.3   
Tab.7AGV power exchange results of large-scale calculation example   

<html><body><table><tr><td colspan="4">AGV编号换电次数 换电时刻(min)剩余电量换电场所换电电池包编号</td></tr><tr><td rowspan="2">1</td><td>2</td><td>469.78 34.00%</td><td>小 5</td></tr><tr><td>559.51</td><td>34.84% 小</td><td>4</td></tr><tr><td>2</td><td>1</td><td>455.27 33.79% 小</td><td>12</td></tr><tr><td rowspan="2">3</td><td>2</td><td>512.91 33.35%</td><td>小 2</td></tr><tr><td>605.2</td><td>34.84% 小</td><td>1</td></tr><tr><td>4</td><td>1</td><td>508.14 34.30%</td><td>小 14</td></tr><tr><td>5</td><td>1 547.79</td><td>35.86%</td><td>小 4</td></tr><tr><td>6</td><td>1 457.21</td><td>33.47%</td><td>大 41</td></tr><tr><td>7</td><td>1 479.82</td><td>35.13%</td><td>大 43</td></tr><tr><td>8</td><td>1 543.36</td><td>34.36%</td><td>大 20</td></tr><tr><td>9</td><td>1 494.88</td><td>33.64%</td><td>大 22</td></tr><tr><td rowspan="2">10</td><td></td><td>429.84 34.06%</td><td>小 13</td></tr><tr><td>2 537.81</td><td>33.02% 大</td><td>36</td></tr></table></body></html>

在集装箱数量 $\scriptstyle \mathtt { n } = 5 0 0$ ，AGV数量 $\scriptstyle \mathbf { a } = 1 0$ 的规模算例中，一共产生了13次换电需求。优化前，13次换电需求需要13个电池包来满足，而决策和约束电池包的选择后，13次换电任务中，每次换电任务中换电机器人选择的电池包编号以及大小换电站中的所有电池包的使用次数记录如表8。

# 表8换电站电池包使用次数记录

表5小规模算例运算数值结果表   
Tab.8Records of battery packs used in power station   

<html><body><table><tr><td>电池编号</td><td>1</td><td>2</td><td>3</td><td>6</td><td>7</td><td>20</td><td>22</td><td>38</td><td>38</td><td>38</td></tr><tr><td>使用次数</td><td>1</td><td>1</td><td>3</td><td>1</td><td>2</td><td>1</td><td>1</td><td>1</td><td>1</td><td>1</td></tr></table></body></html>

在表8中：AGV一共在小换电站进行了8次换电，大换电站进行了5次换电，其中1、2、6、20、22、38、41和43号电池包使用了1次，7号电池包使用了2次，3号电池包使用了3次。因此，在集装箱数量为500个，AGV数量为10台的规模算例中，一共产生了13次换电需求，优化后，一共用到了10块电池包，相比于优化前需要的13块电池包，电池包的数量减少了 $23 . 1 \%$ 。

在上层模型中，通过考虑AGV空重载耗电差异和不同剩余电量区间的空重载速度差异，来提高电池包的利用率，通过输出的数据统计结果，优化前后的换电需求产生时的电池利用率如图10。可知优化前产生14次换电，优化后产生13次换电，总换电次数减少1次，优化后的电池平均利用率为 $61 . 3 4 \%$ ，优化后的电池平均利用率为 $67 . 8 0 \%$ ，电池平均利用率提升 $6 . 4 6 \%$ 。

![](images/731b3beceadac48dfd00d1a652a9d91ec0ba23fd459ca437ffcda9034f03c2c4.jpg)  
图10换电需求产生时的电池利用率

# 4.4交叉率灵敏度分析

当算例规模变大，会影响染色体的长度，在染色体进行交叉算子操作的时候，交叉率的大小会对代码运行结果产生不同程度的影响，如图11所示，在不同的上层模型交叉率pc下，上层模型的代码结果即AGV最大完工时间会产生相应的变化，可知，当上层模型交叉率 $\mathtt { p } \mathtt { c } ^ { = } 0 . 6$ 时，结果最为理想。

![](images/79650c73506331f3cb04ff0892c221cf6411d9922e76f4f1f5f84ba4c52ede80.jpg)  
图9大规模算例下层模型适应度函数进化曲线图Fig.9Evolution curve of fitness function oflower model of large-scale example表7大规模算例AGV换电结果  
图11不同pc下的AGV最大完工时间

![](images/721fb686a2068b370890e135cf4432028944f1e9f31545440f8949f017da3c21.jpg)  
Fig.10Battery utilization when power exchange demand is generated   
Fig.11Maximum completion time of AGV under different pc   
图12不同pc 和PC下的AGV总换电时间Fig.12Total power change time of AGV under different pc and PC

在图12中：设置不同的上下层交叉率pc和 $\mathrm { \bf P _ { C } }$ ，得到下层模型的代码运行结果即AGV总换电时间，可知当 $\mathtt { p } \mathtt { c } \mathtt { = } 0 . 6$ $\operatorname* { P c } { = } 0 . 5$ 时，下层模型的结果最为理想，因此，在代码运行的参数设置中，将上层模型交叉率 $\mathfrak { p } _ { \mathtt { c } }$ 设置为0.6，下层模型交叉率 $\mathrm { P _ { C } }$ 设置为0.5。

# 4.5不同剩余电量的AGV速度灵敏度分析

在AGV进行装卸搬运的过程中，结合实际码头运作情况，AGV在不同的剩余电量状态下，其空载重载时的运行速度也是不同的。根据已有研究可知，AGV根据荷电状态(SOC)分为三个区间，分别是强制充电区间 $( 0 , 3 0 \% ]$ ，即只进行换电任务，只有空载速度。机会充电区间 $[ 3 0 \% , 6 0 \% ]$ ，即可执行换电任务也可执行集装箱任务，正常工作区间 $[ 6 0 \% , 1 0 0 \% ]$ ，即只进行集装箱搬运任务，且此区间的空重载的运行速度大于机会充电区间。V0和V1分别为空、重载速度，由于空重载的速度随着剩余电量的减少而降低，并且空重载速度的大小会影响最终完工时间，并且不能设置太高的速度，设置过高，则会导致电量消耗较快，增加换电次数，这与优化最终完工时间背道而驰。因此本文设置五种方案如表9，来对各剩余电量区间的空重载速度进行灵敏度分析，能够有效提高电池包的利用率。

表9五种不同剩余电量的AGV速度方案  
Tab.9Five AGV speed schemes with different residual power   

<html><body><table><tr><td rowspan="2">方案序号</td><td>强制充电区间</td><td colspan="2">机会充电区间</td><td colspan="2">正常工作区间</td></tr><tr><td>V0(m/s)</td><td>V0(m/s)</td><td>V1(m/s)</td><td>V0(m/s)</td><td>V1(m/s)</td></tr><tr><td>1</td><td>2.4</td><td>2.9</td><td>2.4</td><td>3.9</td><td>2.9</td></tr><tr><td>2</td><td>2.5</td><td>3</td><td>2.5</td><td>4</td><td>3</td></tr><tr><td>3</td><td>2.6</td><td>3.1</td><td>2.6</td><td>4.1</td><td>3.1</td></tr><tr><td>4</td><td>2.7</td><td>3.2</td><td>2.7</td><td>4.2</td><td>3.2</td></tr><tr><td>5</td><td>2.8</td><td>3.3</td><td>2.8</td><td>4.3</td><td>3.3</td></tr></table></body></html>

对每种方案进行10次代码运行，取平均值，最后得出五种方案下的AGV最大完工时间如图13所示，从曲线图中可知，方案二的运行结果在五种方案中最优，因此，对AGV根据自身不同的SOC的速度参数设置时，设置SOC在 $[ 0 , 3 0 \% ]$ 时，空载速度为 $2 . 5 \mathrm { m / s }$ ，SOC在 $[ 3 0 \% , 6 0 \% ]$ 时，空载和重载速度分别为 $3 \mathrm { m / s }$ 、 $2 . 5 \mathrm { m / s }$ ，当SOC在 $60 \%$ ， $100 \%$ 时，空载和重载的速度分别为 $4 \mathrm { m / s }$ 、 $3 \mathrm { m / s }$ 。

![](images/847b2c31b070284f46428d0f16aa2e1ad68448bad8ce1f83aceb602c683323af.jpg)  
图13不同方案的AGV最大完工时间  
Fig.13AGV maximum completion time of different schemes

# 5 结束语

自动化集装箱码头的工作效率，在很大程度上受到AGV的影响，本文在前人研究的基础上，本文针对AGV装卸搬运作业过程中，考虑AGV的电池续航时长、空重载 SOC的变化特性以及不同剩余电量的空重载运行速度差异，对AGV在换电站进行电池包更换的过程中，考虑 AGV产生的换电需求以及换电站内电池包的选取原则和流程，对每一次换电需求对应的换电站和换电电池包的选择进行决策，建立AGV的集装箱任务调度模型和换电电池包配置模型，采用GA来对模型进行编码求解，以500个集装箱10台AGV为例，进行求解，结果表明，该双层模型能够有效地减少总任务完成时间和换电总时间，提升了 $6 . 4 6 \%$ 的AGV电池包利用率，并且能够合理有效地规划换电站的电池包储备数量，降低了$2 3 . 1 \%$ 的电池包储备数量。由此可见，该双层模型的研究对提高自动化集装箱码头的运作效率有一定的现实意义，为进行自动化码头换电站内电池包数量的研究提供一种思路。

参考文献：   
[1]Kim KH, Bae JW.A Look-ahead Dispatching Method for Automated Guided Vehiclesin Automated Port Container Terminals[J]. Transportation Science,2004,38 (2).   
[2]Frank S,Ulrich W. Optimization of Battery Charging and Purchasing at Electric VehicleBaterySwapStations[J].TransportationScience,2018, 52 (5):   
[3] Xiang Xi,Liu Changchun. Modeling and analysis for an automated container terminal considering battery management [J]. Computers & IndustrialEngineering,1,6:   
[4]石楠路，梁承姬．考虑换电过程的自动化码头 AGV 调度优化[J]. 现代制造工程，2019(02): $6 { - } 1 1 { + } 1 3 9$ ，(Shi Nanlu,Liang Chengji. Scheduling optimization of automated terminal AGV considering power exchange process [J]. Modern Manufacturing Engineering,2019 (02): 6- （204号 $1 1 + 1 3 9 .$ ）   
[5]周小凡，甚道方，余芳，等．考虑充电和等待时间的集装箱码头 AGV 调度 [J].上海海事大学学报，2019,40 (03): $1 - 5 + 1 3$ (Zhou Xiaofan, Chang Daofang, Yu Fang, et al. AGV scheduling in container terminals considering charging and waiting time [J].Journal of Shanghai Maritime University,2019,40 (03): $\displaystyle { 1 - 5 + 1 3 . }$ ）   
[6] 张亚琦，杨斌，胡志华，等．自动化码头 AGV 充电与作业的集成调 度研究[J].计算机工程与应用,2017,53(18): $2 5 7 - 2 6 2 + 2 7 0$ . (Zhang Yaqi,Yang Bin,Hu Zhihua,et al. Research on integrated scheduling of AGV charging and operation in automated terminals [J].Computer Engineering and Applications,2017,53 (18): 257-262+270.)   
[7]吴洪明，邹梦艳．考虑电池电量约束的自动化码头 AGV 调度[J]. 起重运输机械，2021(03):47-52.(Wu Hongming,Zou Mengyan. Automatic terminal AGV scheduling considering battery power constraints [J].Hoisting and Transportation Machinery,2021 (O3): 47- 52.）   
[8]丁一，陈婷．基于滚动时域优化策略的多载 AGV 充电调度[J]．中 国航海,2020,43(02):80-85.(Ding Yi,Chen Ting.Multi-load AGV charging scheduling based on roling time domain optimization strategy [J].China Navigation,2020,43 (02): 80-85.)   
[9]郑亚红，徐玖龙，谢淳．自动化集装箱码头AGV 换电管理与调度优 化[J].武汉理工大学学报(交通科学与工程版),2021,45(01):1-6. (Zheng Yahong，Xu Jiulong，Xie Chun． AGV power exchange management and scheduling optimization in automated container terminals[J].JournalofWuhanUniversityofTechnology (Transportation Science and Engineering Edition),2021,45 (01):1-6.)   
[10]傅正堂，胡志华，宗康．集装箱码头 AGV 电量非饱和状态下的调度 优化[J].大连海事大学学报,2017,43(03):58-62.(Fu Zhengtang,Hu Zhihua, Zong Kang. Scheduling Optimization of AGV in Container Terminal under Non-saturated State of Electricity[J]. Journal of Dalian Maritime University,2017,43 (03): 58-62.)   
[11]范厚明，郭振峰，岳丽君，等．考虑能耗节约的集装箱码头双小车岸 桥与 AGV 联合配置及调度优化[J]．自动化学报，2021,47(10): 2412-2426.DOI:10.16383/j.aas.c190626.(Fan Houming，Guo Zhenfeng,， Yue Lijun,et al. Combined configurationand scheduling

optimization of dual-trolley quay cranes and AGVs in container terminals considering energy saving[J].Chinese Journal of Automation,2O21,47 (10):2412-2426.DOI: 10.16383/j.aas.c190626.)

[12]宋绍京，羊铭雨，孙磊，等.AGV数量规划及电池充电策略研究[J]. 长春理工大学学报（自然科学版），2019,42(06):73-77.(Song Shaojing,Yang Mingyu,Sun Lei,et al.Research on AGVQuantity Planning and Battery Charging Strategy [J]. Journal of Changchun University of Science and Technology(Natural Science Edition),2019, 42 (06): 73-77.)

[13]黄宇超．自动化码头AGV换电站布局设计[J].港口装卸,2021(04): 61-65.(Huang Yuchao.Layout Design of AGV Swap Station in Automated Wharf[J].PortHandling,2021 (04):61-65.)

[14]樊陆彬，梁承姬，余文婧.不确定环境下的岸桥-集卡协调调度耦合 模型建立与求解[J].计算机应用,2016,36(03):843-848.(FanLubin Liang Chengji, She Wenjing.Establishment and solution of the coupled model of quay crane-truck coordination dispatch in uncertain environment [J].Computer Applications,2016,36 (03): 843-848.)

[15]陈香玲，郭鹏，温昆，等．考虑充电需求和时间窗的多AGV调度优 化建模[J]．河北科技大学学报，2021,42(02):91-100.(Chen Xiangling，Guo Peng，Wen Kun，et al.Multi-AGV scheduling optimization modeling considering charging demand and time window [J].Journal of Hebei University of Science and Technology,2021,42 (02):91-100.)