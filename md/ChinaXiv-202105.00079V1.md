# ·基于线性规划的云南40米射电望远镜短期观测编排方法

戴伟13，卫冰涛'，郝龙飞²，卫守林1,，梁波1,31，昆明理工大学信息工程与自动化学院，云南 昆明6505002，中国科学院云南天文台，云南昆明6502163，云南省计算机应用技术重点实验室，云南昆明650500

摘要：望远镜自动化观测编排，是望远镜观测控制系统实现自主观测必不可少的组成部分。云南天文台40 米射电望远镜需要对观测目标制定中长期和短期的纲要，目前对短期的目标进行纲要的编制时，主要依赖观测人员根据经验手动来实现，这种方式不仅低效耗时，更有可能会导致结果显著地偏离最优观测方案，不能充分利用望远镜宝贵的观测时间。本文使用混合整数线性规划模型，分析了云南天文台40米射电望远镜的短期观测目标的问题，定义了短期观测目标调度中的限制条件，以最小化望远镜的寻址时间作为目标函数，使用数学优化来解决射电望远镜短期观测目标编排问题，并在云南天文台40米射电望远镜上进行了测试，能较好地满足目前短期观测目标编排的需求。

关键词：观测编排；线性规划；射电望远镜；自主观测中图分类号：P111.5 文献标识码：A 文章编号：xxx

# 1引言

为了减少电磁干扰对观测的影响，射电望远镜台站都选择在高海拔，人迹稀少的地区，但这同时也限制了人工现场干预观测能力。同时当前望远镜正朝着巨型化、复杂化发展，望远镜的正常运转需要多种组件协同工作[1]，依赖操作人员手工控制已变得越来越困难。因此，自主观测已是每个望远镜观测控制系统的共同需求，自主观测是指根据观测计划自动进行调度的观测模式，而观测计划的编排是望远镜实现自动化观测控制的前提。

观测计划编排已被广泛研究，但主要集中在长期观测申请调度上，通常是望远镜科学委员会根据科学目标，赋予不同的观测申请不同的科学价值权重后，通过优化方法给出长期的计划编排[2l。而对于云南40米射电望远镜一个重要需求是，给出一系列的观测目标，使望远镜尽可能在短时间内完成所有观测目标的观测。通常是一天内完成几十颗源的短期观测编排，显然目前在其他望远镜系统的长期观测编排方法并不能满足云南40米射电望远镜短期编排需求。

不同于长期观测编排，短期编排需要给出观测目标具体的开始和结束观测时间，而时间变量是连续的，因此短期编排属于连续最优化问题。观测目标的位置随着时间不停变化，而不同的观测目标一天内在望远镜视场中出现的时间有限，同时还要考虑从一个观测目标转动到另外一个目标，由于望远镜本身机械问题，可能出现的限位以及观测目标能否获得较好的数据质量，这些都是短期编排区别于长期编排的地方，也是优化的难点。本文首先回顾了当前主要的观测编排方法，接着介绍将望远镜的源的编排转换成混合整数线性规划问题中的决策变量、目标函数和约束条件的定义，给出了该方法在云南40米射电望远镜上的测试结果，最后是本文工作的总结，并讨论了云南40米射电望远镜观测编排未来的研究工作。

# 2相关工作

调度问题已在电力、运输、航空、计算机以及工业生产等领域得到了广泛的研究，望远镜观测目标的编排正是该问题在天文领域的实际应用。哈勃空间望远镜的 Spike系统自1990年起投入使用，提出的核心算法为迭代修正搜索算法[3]。迭代修正搜索算法的核心思路是将望远镜时间分配问题抽象成一个约束优化问题，随后通过三个步骤进行求解：首先通过某种启发式算法构造初始解，该初始解可以违反约束条件，其使用的启发式算法可以根据具体需求进行选择，但启发式过程均基于对约束程度的量化并且选择容易计算的量化方式，随后再利用启发式的修正算法来减少约束的违反。最终通过从时间分配表中去除存在冲突的活动来消除冲突[4]。

绿岸射电望远镜（Green Bank Telescope，GBT）采用了NRAO 开发的一个自动动态调度系统[5]，其核心思想是基于一种排序的算法来确定观测计划之间的优先次序。文献描述了GBT使用的包括预报天气条件、观测效率、目标坐标等变量的排序算法，以及调度观测中使用的一些特定变量。

撒丁岛射电望远镜（Sardinia Radio Telescope，SRT）[参考了GBT的动态调度系统，考虑了长期和短期编排问题，在其模拟结果中，以48小时为周期，每一个小时作为一个时间槽。每个观测计划被赋予一个科学价值，占用2到6小时，使用模拟退火算法优化观测编排，加入了水汽和天气条件等限制条件。

500 米口径球面射电望远镜（Five-hundred-meter Aperture Spherical radio Telescope,FAST）[7]以最小化寻址代价和最大化科学价值作为目标函数，限制条件考虑了源的可见性，射频干扰等因素，同时使用了边缘检测的方式减少问题空间，加快优化速度。使用了中国虚拟天文台的在线观测提案系统，本质上还是中长期的观测编排。

其他的望远镜系统的观测编排也大都是观测提案的编排，比如基于进化算法的LOFAR观测调度[8]，基于模拟退火和动态规划实现的ALMA观测调度[9]。而云南40米射电望远镜作为单碟射电望远镜，在短期的观测编排中，需要在更短的时间槽内，按目标源进行分配，而不是分配观测提案。而现有的中长期的观测提案的编排方法，显然无法解决按目标源进行观测时间分配的需求。

# 3模型设计

# 3.1问题描述

云南 40 米射电望远镜短期观测目标编排需求通常是在一天（或几个小时）内，给定一系列的观测目标信息，包含观测目标的名称（J2000纪元）、位置和所需观测时长，如表1所示。

表1．云南40米射电望远镜观测源信息样例  

<html><body><table><tr><td>观测源名称</td><td>赤经（RA）</td><td>赤纬（DEC)</td><td>观测时长（分钟)</td></tr><tr><td>0034-0721</td><td>0034 08.8703</td><td>-07 21 53.409</td><td>48</td></tr><tr><td>0139+5814</td><td>01 3919.7401</td><td>+58 14 31.819</td><td>48</td></tr><tr><td>1559-4438</td><td>15 59 41. 5261</td><td>-44 38 45.9018</td><td>24</td></tr><tr><td>1745-2900</td><td>17 45 40.190005</td><td>-29 00 30.37032</td><td>48</td></tr></table></body></html>

短期编排的结果是得出每个目标开始和结束的观测时间，并使望远镜的利用率最大化。同时需要考虑：

1）所有观测目标都被安排观测。每颗目标源的观测时长要求集中在24到48分钟，需保证编排时间满足观测时长要求。2）分配时间粒度。时间分配粒度太大，会造成时间片的浪费。如果时间分配粒度太小，会造成参数空间的膨胀，直接影响最优化求解的性能。3）望远镜硬件的限位条件。在观测过程中源的位置不断变化，而望远镜的俯仰角只能在一定的范围转动，因此须满足在源的编排时间范围内，望远镜都可以转动到源目标，也即是满足望远镜硬件的限位条件。4）最优观测时间。根据40米望远镜的历史观测经验，天线俯仰在40-60度内进行观测比较好，这时候增益较大，且增益变化不大，观测源受地面噪声相对较小，观测获取的数据质量也就更好。因此编排时，优先考虑这个位置范围的源，源的位置高度可用Airmass 衡量，Airmass值可近似于 $1 / \sin \alpha$ ，其中 $\alpha$ 为源的高度角。如图1所示，显示了2020年12月21日，源 $2 0 5 5 + 3 6 3 0$ ，0837-4135， $0 3 5 8 + 5 4 1 3$ 的Airmass 随时间变化的曲线。

![](images/4a572e1ea2363d3afb72b3afade9ec5a8b39531e8e093dc37969fc445a2b8c18.jpg)  
图1.源 $2 0 5 5 \substack { + 3 6 3 0 }$ ，0837-4135和 $\boldsymbol { 0 3 5 8 + 5 4 1 3 }$ 在2020年12月21日不同时刻的Airmass值

Figure 1. The Airmass of 2055+3630, 0837-4135， $0 3 5 8 \substack { + 5 4 1 3 }$ at different times on December 21, 2020

根据云南40米射电望远镜短期观测目标编排需求和限制条件，假设总共有 $K$ 个观测目标，一个观测目标在观测过程中需要考虑目标的观测时长以及望远镜从第一颗源的跟踪状态切换到第二颗源的跟踪状态所消耗的时间（SlewTime)，因此，一个观测目标 $\mathbf { \chi } _ { t }$ 占用的时间窗为转向时间 $T _ { s } { + }$ 观测时间 $T _ { o }$ ，可表示为：

$$
T _ { t } ^ { i } = T _ { s } ^ { i - 1  i } + T _ { o }
$$

其中转向时间依赖上个观测目标结束时望远镜的位置（方位、俯仰角度)。如果是首个观测目标，则望远镜的转向时长根据望远镜初始的方位角和高度角进行计算。

# 3.2决策变量

在望远镜短期观测编排中，时间是最主要的变量，时间直接决定了源的位置，也间接影响源的观测时长。在云南40米的短期目标编排中，目标源观测时长的单位是分钟，我们将时间的分配粒度设置为分钟，整个观测计划的总时间 $M$ 为 $2 4 \times 6 0 \times d$ 分钟，其中 $d$ 为编排计划的天数。

首先对于每个观测目标 $\{ T _ { j } , j \in K \}$ ，定义目标 $T _ { j }$ 的开始观测时间为 $t _ { j } ^ { s } \in ~ [ 0 , M ]$ ，结束观测时间为 $t _ { j } ^ { e } \in \ [ 0 , M ]$ ，在优化实现中，为加快求解速度， $t _ { j } ^ { s }$ 和 $t _ { j } ^ { e }$ 范围取目标 $T _ { j }$ 第一个可用时间槽的开始时间和最后一个可用时间槽的结束时间。我们取Airmass 的范围为[2,10]，可计算获得每个观测目标在观测总时间内的 $s$ 个可观测的时间槽，如图2所示，每个观测源在一天内通常有1-4个可观测的时间槽，单个目标在所有可观测时间槽的 Airmass 均在[2,10]。定义二进制变量 $l _ { j , n } = { \binom { 1 } { 0 } }$ 表示目标 $T _ { j }$ 是否在其第 $n$ 个可观测的时间槽内被调度。

![](images/43b0e71f2efaa437feef01de454912e210fc158e617573cade19900302abee3a.jpg)  
图2.源 $0 9 2 2 \substack { + 0 6 3 8 }$ 和源 $1 1 3 6 + 1 5 5 1$ 在2020年12月21日的可用时间槽  
Figure 2.The available time slots of $0 9 2 2 \substack { + 0 6 3 8 }$ and $1 1 3 6 \substack { + 1 5 5 1 }$ on December 21,202(

观测目标编排重要的一点就是编排源的观测顺序，定义二进制变量 $y _ { i , j } = \begin{array} { l } { \left\{ \begin{array} { l l } { 1 } \\ { 0 } \end{array} \right. } \end{array}$ ，表示望远镜是否完成源 $\boldsymbol { T } _ { i }$ 的观测后转动到源 $T _ { j }$ 。

定义目标源的距离矩阵为 $D$ ，其中目标 $T _ { i } ( \alpha _ { 1 } , \delta _ { 1 } )$ 和目标 $T _ { j } ( \alpha _ { 2 } , \delta _ { 2 } )$ 间的距离 $d _ { i j }$ ，使用大圆公式计算[10]：

$$
d _ { i j } = \operatorname { a r c c o s } \left[ \sin \delta _ { 1 } \sin \delta _ { 2 } + \ \cos \delta _ { 1 } \cos \delta _ { 2 } \cos \left( \alpha _ { 1 } - \alpha _ { 2 } \right) \right]
$$

云南 40米望远镜根据经验值，最大的源目标切换时间约为6分钟，这里源切换时间矩阵近似于：

$$
S \approx 6 \times \widetilde { D }
$$

其中 $\widetilde { D }$ 为距离矩阵 $D$ 的0均值归一化矩阵。

# 3.3目标函数

基于最大化望远镜利用率，尽量减少总的望远镜源切换时间的原则，目标函数定义为：

$$
\begin{array} { r } { m i n \sum _ { i \in J } \sum _ { j \in J } y _ { i j } \left( t _ { j } ^ { s } - t _ { i } ^ { e } \right) + y _ { i j } S _ { i j } } \end{array}
$$

# 3.4约束条件

根据云南40米射电望远镜短期观测目标编排的问题描述，在最优化目标函数的过程中需要满足以下约束：

约束一：满足每个观测目标的观测时长的要求。即满足结束调度时间减去开始调度大于等于观测时长 $P _ { j }$ 。

$$
t _ { j } ^ { e } - t _ { j } ^ { s } \geq ~ P _ { j } ~ \vert ~ j ~ \in { \cal K }
$$

约束二：每个目标有不止一个可观测时间槽，需要保证开始时间和结束时间落在同一个时间槽内，如图3所示，观测源 $0 9 2 2 \substack { + 0 6 3 8 }$ 出现的编排1并不满足约束二，结束时间并未落在时间槽内。编排2满足约束二，开始时间和结束时间落在同一个时间槽内。

![](images/7e526a4f31d8c7349e9af655ccc19d7b00f80c0da0078b3753b6715e459d2f64.jpg)  
图3．约束二条件限制示意图  
Figure 3. The diagram of condition restriction under the second constraint

也即是如果目标 $T _ { j }$ 的开始观测时间为 $t _ { j } ^ { s }$ 大于等于一个时间槽的开始时间，则结束时间 $t _ { j } ^ { e }$ 应小于等于这个时间槽的结束时间。

$$
\begin{array} { r } { t _ { j } ^ { s } \geq \sum _ { n = 0 } ^ { N } l _ { j , n } L _ { j } ^ { s n } , \quad t _ { j } ^ { e } \leq \sum _ { n = 0 } ^ { N } l _ { j , n } L _ { j } ^ { e n } } \end{array}
$$

其中 $N$ 是目标 $T _ { j }$ 的可观测时间槽的数量， $L _ { j } ^ { s n }$ 第 $n$ 个时间槽的开始时间， $L _ { j } ^ { e n }$ 第 $n$ 个时间槽的结束时间。 $l _ { j , n } = { \binom { 1 } { 0 } }$ ，表示目标 $T _ { j }$ 是否在其第 $n$ 个可观测的时间槽内被调度，且需满足$\begin{array} { r } { \sum _ { n = 0 } ^ { N } l _ { j , n } = 1 } \end{array}$ ，表示目标 $T _ { j }$ 必须在其中一个时间槽内被调度。

约束三：保证每个观测目标开始观测时间和观测结束时间没有相互重叠。

$$
i f y _ { i j } = 1 \to t _ { j } ^ { s } \geq t _ { i } ^ { e } + S _ { i j }
$$

如果 $y _ { i j } = 1$ ，表示完成源 $\boldsymbol { T } _ { i }$ 的观测后转动到源 $T _ { j }$ ，需要满足源 $T _ { j }$ 的开始时间大于等于源 $\boldsymbol { T } _ { i }$ 的结束时间加上源 $\boldsymbol { T } _ { i }$ 到源 $T _ { j }$ 的转换时间 $S _ { i j }$ 。

# 4实验

实验数据来自云南40米射电望远镜的真实观测源，短期编排的时间区间为1天，共有观测源24颗。每颗源所需观测时长在24-48分钟。实验的硬件环境为1台配置为Intel XeonCPU E5-2660 v4 CPU $@$ 3.4GHz处理器(56核)，512GBRAM的高性能服务器。求解器使用Gurobi9.1，以2020年12年21日为例，如图4所示，24颗目标源被全部编排，并不存在时间交叉的情况，经过验证也都在其可观测的时间槽内。

![](images/214bfee7e39425c1f88aa22f4ed772417ac6b4fcc0a32299412e18e112324e40.jpg)  
图4.24颗观测源在2020年12月21日的观测时间分配

Figure 4. The observation time scheduling results of the 24 sources on December 21,2020

Gap 即百分比界差，是求解大规模混合整数规划问题时非常重要的参数，可视为在去除问题参数整数取值的限制后，问题松弛解与最优解之间的绝对差距：

$$
G a p \ = \left| { \frac { O P T - L P } { L P } } \right|
$$

OPT为当前最优解， $L P$ 为去掉整数约束后的松弛最优解。实验环境中，使用56个线程模型可在300 秒内将 $G a p$ 控制在0.1以下。

# 5总结

本文利用线性规划方法对云南天文台40米射电望远镜的短期观测目标编排问题进行了建模，详述了在短期观测编排过程中遇到的限制条件，利用非线性混合整形线性规划解决了这一约束优化问题。实验结果显示了该方法的可用性。

短期观测目标编排问题中，机会源的临时插入观测，整个观测计划就需要重新编排，因此求解速度也是短期观测目标编排中的重要考量。未来研究使用其他的优化算法进一步提高编排性能，减少望远镜等待编排的时间。同时考虑加入目标源的权重，在望远镜空闲时间对权重高的目标多次观测。此外研究如何利用已观测的脉冲星数据，反演出天线干扰情况与方位以及俯仰之间的关系图，在编排目标源时优先干扰较小的源。在目前的模型中源切换的时间使用球面距离近似估计，不完全准确，未来研究如何在优化过程中根据源的方位角和高度角以及望远镜的实时指向位置动态计算源的切换时间。

参考文献   
[1] 邓辉，钟文杰，付映雪,etal.基于 ZeroMQ 的新一代望远镜自动控制系统的通信框架 设计[J]．天文研究与技术,2018,15(3):308-314.   
Deng Hui, Zhong Wenjie, Fu Yingxue, et al. The Design of Communication Framework for a New Generation of Telescope Autonomous Control System Based on ZeroMQ[J].Astronomical Research and Technology,2018,15(3): 308-314.   
[2]李曼迪，葛亮，姜晓军．望远镜观测调度系统研究进展 [J].天文学进展,2019,37(4): 455-468.   
LI Man-di;GE Liang;JIANG Xiao-jun. Research Progress on Observation Scheduling System of Telescope[J]. Progress In Astronomy, 2019,37(4): 455-468.   
[3] Johnston M D, Miller G. Spike: Intelligent scheduling of hubble space telescope observations [J]. Intelligent Scheduling,1994: 391-422.   
[4] 刘琪．丽江 2.4 米光学望远镜观测时间自动分配算法研究[D]．天津大学,2016.   
Liu Qi. Automatic Time Allocation for Lijiang $2 . 4 \mathrm { m }$ Optical Telescope[D]. Tianjin University, 2016.   
[5] Balser D S, Bignell C, Braatz J, et al. Gbt dynamic scheduling system: Algorithms, metrics, and simulations[C]//Astronomical Data Analysis Software and Systems XVIII. 2009,411: 330. [6] Nasir F T, Castiglia C, Buffa F, et al. Weather forecasting and dynamic scheduling for a modern $\mathrm { c m / m m }$ wave radiotelescope [J]. Experimental Astronomy, 2013,36(1): 407-424.   
[7] Luo Q, Zhao L, Yu C, et al. Cost-effcient scheduling of FAST observations [J]. Experimental Astronomy,2018,45(1): 107-126.   
[8] Grim R, Jansen M，Baan A，et al. Use of evolutionary algorithms for telescope scheduling[C]/Integrated Modeling of Telescopes. International Society for Optics and Photonics, 2002,4757: 51-61.   
[9] Clarke D,Avarias J. ALMA Scheduling: It's Dynamic![J]. Astronomical Data Analysis Software and Systems XXI, 2012,461: 177.   
[10]樊东卫，何勃亮,李长华,etal．球面距离计算方法及精度比较 [J].天文研究与技术, 2019,16(1): 69-76.   
Fan Dongwei, He Boliang, Li Changhua, et al. Research on Spherical Distance Computation and Accuracy Comparison[J]. Astronomical Research and Technology, 2019, 16(1): 69-76

# A Short-term Scheduling Method Based on Linear Programming for Yunnan 40-meter Radio Telescope

Dai Weil,3,Wei Bingtaol,Hao Longfei²,Wei Shoulin1,3,Liang Bo1,3 (1,FacultyoffoatioEgeigndtomationKungUrsityoiecandcholgKninga;

2,Yunnan Observatories,Chinese Academy of Sciences,Kunming 650216,China;

3,KeyLaboratory of Applications of Computer Technology of the Yunnan Province,Kunming 6505oo,China)

Abstract: The observation scheduling is an indispensable part of the telescope observation control system to realize autonomous observation. The 40-meter radio telescope of the Yunnan Observatories combines the requirements of long-term and short-term observation scheduling. In the current practice of short-term observation scheduling, it mainly relies on the observers to manually implement them based on experiences. This method is not only inefficient and time-consuming,but also cause the results to deviate significantly from the optimal observation plan,and the valuable observation time of the telescope cannot be fully utilized.In this paper, the mixed integer linear programming model is used to analyze the problem of the short-term observation target of the $4 0 \mathrm { m }$ radio telescope.We define the constraints in the short-term observation target scheduling，adapt the minimization oftotal slew times as the objective function,and use mathematical optimization to solve the short-term observation target scheduling problem.The proposed method has also been tested on the $4 0 \mathrm { m }$ radio telescope,which can better meet the requirements of current short-term observation target scheduling.

Key words: Observation scheduling; Linear programming; Radio telescope; Autonomous Observation