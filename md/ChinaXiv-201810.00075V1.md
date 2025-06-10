# 基于改进NSGA-II算法的微电网多目标优化研究

张军1,2†，任豪1,²，刘廷章3

(1.上海电力大学自动化工程学院，上海 200090;2.上海市电站自动化技术重点实验室，上海 200090;3．上海大学机电工程与自动化学院，上海200072)

摘要：在解决微电网分布式电源多目标优化运行问题时，针对传统NSGA-II算法在逼近性、运算效率等方面的局限性，考虑进化过程个体相似度的差异及算法陷入局部最优的可能性，提出了一种改进型的NSGA-II算法。新算法引入信息熵机制改进算子，将交叉概率、变异概率分别近似为递减函数模型、柯西分布模型，通过算法性能测试证明了新算法有效性。以分布式电源接入IEEE30节点电力系统为例进行仿真实验，通过与传统NSGA-II多目标优化算法对比，证明了改进型算法在提高收敛速度、改善优化指标方面的优越性。

关键词：微电网；多目标优化；信息熵；Pareto最优解集 中图分类号：TM73 doi:10.3969/j.issn.1001-3695.2018.07.0435

Research on multi-objective optimization of micro-grid based on improved NSGA-I algorithm

Zhang Jun1,2†, Ren Hao1,², Liu Tingzhang3 (1.SchoolofAutomationEngineering,ShanghaiUniversityofElectricPower,hanghai2o90,China;2.Shanghai Key LaboratoryofPower StationAutomationTechnology,Shanghai 20o0,China;3.SchoolofMechatronic Engineering& Automation,Shanghai University,Shanghai 20o072,China)

Abstract:In solving the problemof multi-bjective optimizationoperationof distributed power supply in micro-grid,iming atthe limitationsof traditionalNSGA-Ialgorithm in termsofapproximationandcomputational efficiency,consideringthe diference of individual similarity in evolution processand the possibilityof the algorithm fling into local optimum,this paper proposed an improved NSGA-IIalgorithm.The new algorithm introduced the information entropy mechanism to improve theoperator,and approximated the crosover probabilityand mutation probabilityasthedecreasing function model and the Cauchy distribution model respectively.The performance test proves thatthenew algorithm is effective.Taking distributed power suply access to IEEE30-node power system as an example for simulation experiment,compared with the traditional NSGA-II multi-objectiveoptimizationalgorithm,theresult shows thesuperiorityof the improvedalgorithmin improving the convergence speed and the optimization indices.

Key Words: micro-grid; multi-objective optimization; information entropy; Pareto optimal solution

# 0 引言

随着自然资源的日益枯竭和人们对环境保护的重视，分布式能源作为一种灵活利用分散能源的新型用电形式越来越受到人们关注。与传统的煤、石油等化石能源不同，分布式能源主要包括光能、风能、潮汐能、地热能和生物质能等，具有分布广、污染少、便于小规模利用等特点。以微电网的形式对配电网进行规划运行是解决分布式能源调度难、利用率低、电能质量差等问题的方案之一。因此，综合考虑经济指标、技术指标、环境指标等的微电网多目标优化运行成为微电网研究领域的热

点方向。

现有的多目标优化算法对多目标的处理主要有两种方式：a)将各个子目标通过加权处理转变为一个单目标进行处理，该方法将复杂的多目标问题简单化，但在进行权重计算时存在主观性大的问题；b)基于Pareto 非支配解理论，根据优化算法求出多目标问题的Pareto最优解集，再根据要求从解集中选择最优解。现代优化算法种类很多，主要有遗传算法、粒子群群算法，以及与之相似的蚁群、蜂群等算法。随着对算法研究的不断深入，这些常见算法的不足之处逐渐显露出来，如遗传算法容易将求解范围局限在局部最优搜索、粒子群算法存在搜索精度不高的缺点。因此，近年来出现了较多基于基本算法的改进算法来求解微电网的优化运行问题的研究文献[\~7]。

本文研究并网型微电网接入电网的带约束非线性多目标优化问题，以系统的经济指标与技术指标为优化目标，结合精英保留、非劣排序等优化策略，提出改进型的非支配排序遗传算法（NSGAEN)，并通过性能测试证明该算法在逼近性和运行速度上的优势，通过求解分布式电源接入IEEE30节点电力系统的多目标优化问题证明本算法的可行性。

# 1 微电网模型

微电网结构如图1所示。该微电网系统由太阳能发电单元、风力发电单元、微型燃气轮机组及储能单元构成。微网供电系统能够在满足经济指标和技术指标的前提时建立准确的分布式电源功率外特性模型。

# 1.1光伏电池功率模型

并网型光伏发电系统通过逆变器将光伏电池产生的直流电转换为与大电网相同频率的交流电。由于光伏电池的输出特性受到光照、温度及光伏电池板安装角度的影响，在最大功率跟踪模式的情况下，光照强度可近似为服从Beta分布，其概率密度函数为[8]

$$
f ( G ) = \frac { \Gamma ( \alpha + \beta ) } { \Gamma ( \alpha ) \Gamma ( \beta ) } ( \frac { G ( t ) } { G _ { \mathrm { m a x } } } ) ^ { \alpha - 1 } \Biggl ( 1 { - } \frac { G ( t ) } { G _ { \mathrm { m a x } } } \Biggr ) ^ { \beta - 1 }
$$

其中： $G ( t )$ 和 $G _ { \mathrm { m a x } }$ 分别为该时段内的实际光照强度和光照强度最大值； $\mathrm { ~ \tt ~ { ~ a ~ } ~ }$ 和 $\beta$ 为形状参数； $\mu$ 和 $\sigma$ 分别为光照强度的平均值和方差。

$$
\alpha { = } \mu [ \frac { \mu ( 1 { - } \mu ) } { \sigma ^ { 2 } } - 1 ]
$$

$$
\beta { = } ( 1 { - } \mu ) [ \frac { \mu ( 1 { - } \mu ) } { \sigma ^ { 2 } } { - } 1 ]
$$

光伏电池功率输出模型可近似为[9]

$$
P _ { { P V } } = P _ { { S T C } } \frac { G _ { { C } } } { G _ { { S T C } } } [ 1 + k ( T _ { c } - T _ { s T C } ) ]
$$

其中： $P _ { s r c }$ 为标准测试环境下(温度 $2 5 ^ { \circ } \mathrm { C } ,$ 光照强度1000$\mathrm { ~ W ~ / ~ } m ^ { 2 }$ )的最大功率； $G _ { c }$ 为测试时的光照强度； $G _ { s r c }$ 为标准光照强度； $T _ { c }$ 为电池的测试温度； $T _ { s r c }$ 为标准测试温度。

微电网供电系统模型如图1所示。

# 1.2风力发电的功率模型

本文采用的风力发电机组为常见的双馈异步发电机。在实际运行时，当实时风速未达到风机的切入风速时，输出功率为0；当实时风速介于风机的切入风速和额定风速之间时，输出功率与风速之间成三次函数曲线；当实时风速介于额定风速和切出风速之间时，风机的输出功率为额定功率；当实时风速大于切出风速时，为了保护风机部件而将其停机，输出功率为0。因此，风机的输出功率 $P _ { w G }$ 与风速 $\mathbf { v }$ 的关系可表示为[10]

$$
P _ { _ { W G } } = \left\{ \begin{array} { l l } { 0 , \qquad \quad \nu \leq \nu _ { i n } \ o r \ \nu \geq \nu _ { o u t } } \\ { \qquad \nu ^ { 3 } - \nu _ { i n } ^ { 3 } P _ { r } , \ \nu _ { i n } \leq \nu \leq \nu _ { r } } \\ { \qquad \nu _ { r } ^ { 3 } - \nu _ { i n } ^ { 3 } P _ { r } , \ \nu _ { i n } \leq \nu \leq \nu _ { r } } \\ { P _ { r } , \qquad \quad \nu \geq \nu _ { r } } \end{array} \right.
$$

其中： $\nu _ { i n }$ 为切入风速； $\nu _ { o u t }$ 为切出风速； $\nu _ { _ r }$ 为额定风速； $P _ { r }$ 为额定风速。

![](images/784c829f295054b6c6a27c4ba0e0dd9c973a4e0a3d11b8324320b9a6b97fab25.jpg)  
图1微电网供电系统模型

# 1.3微型燃气轮机模型

微型燃气轮机一般以甲烷、天然气等为燃料的热力发电设备，主要由同步发电机、燃气轮机、变换装置、供热和制冷机组构成。微型燃气轮机维护方便，能长时间处在工作状态，排出的尾气可以通过溴化锂制冷机处理以满足冷热负荷的需要，有效提高了能源利用率。

以美国Capstone微燃机公司C600S为例，当微型燃气轮机处于冷热电联合供给发电状态时，其在t时刻的输出功率为

$$
\begin{array} { r l } & { P _ { M T } ( t ) = \rho V _ { i n } ( t ) \cdot L H V _ { f } + C _ { P } \rho V _ { i n } ( t ) ( T _ { 2 } ( t ) - T _ { 1 } ( t ) ) } \\ & { P _ { M T } ^ { ' } ( t ) = C O P \cdot C _ { P } \rho V _ { e x } ( t ) ( T _ { 2 } ( t ) - T _ { 3 } ( t ) ) } \end{array}
$$

其中： $P _ { \scriptscriptstyle M T }$ 代表燃气轮机全负荷情况下的输出功率； $V _ { i n }$ 为燃料进气流量; $\mathbf { \mathit { P } } _ { M T } ^ { ' }$ 表示重新利用的热量； $L H V _ { f }$ 为燃料的低位热值；$\rho$ 为燃烧气体的密度； $V _ { e x }$ 烟气排出的流量； $T _ { \mathrm { l } }$ 为燃料进气温度； $T _ { 2 }$ 为排气温度； $T _ { 3 }$ 为蒸汽的出口温度； $C O P$ 为制热能效比； $C _ { P }$ 为燃烧气体的比热容。

# 2 分布式电源多目标规划的目标函数

根据前文介绍的微电网各个微电源的功率外特性，以改善电能质量、提高经济效益为目标，考虑经济指标和技术指标建立微电网多目标优化模型[11]。

经济目标：分布式电源的投资成本最小、运行成本最小。

$$
C = \sum _ { i = 1 } ^ { N _ { D G } } Y [ ( \frac { r ( 1 + r ) ^ { n } } { ( 1 + r ) ^ { n } - 1 } ) \cdot C _ { M A , i } + C _ { F X , i } ]
$$

其中：C表示微电源的投资运行成本；r为市场贴现率； $C _ { F X , i }$ 表示节点i的安装成本； $C _ { M A , i }$ 表示节点i的运行成本； $\mathfrak { n }$ 表示设备的预计使用寿命（单位年)； $N _ { { D G } }$ 为电网的支路数；Y的取值为0或者1， $\scriptstyle \ Y = 0$ 表示该节点未安装分布式电源， $\mathrm { Y = 1 }$ 表示该节点安装了分布式电源。

技术目标：系统的有功网损最小、节点电压的偏移量最小。

$$
\left\{ \begin{array} { l l } { \displaystyle P _ { l o s s } = \sum _ { k = 1 } ^ { N _ { 1 } } G _ { i j } ( U _ { i } ^ { 2 } + U _ { j } ^ { 2 } - 2 U _ { i } U _ { j } \cos \delta _ { i j } ) } \\ { \displaystyle \Delta U = \sum _ { l = 1 } ^ { N _ { d } } ( \frac { U _ { l } - U _ { N } } { U _ { l } ^ { \mathrm { m a x } } } ) ^ { 2 } } \end{array} \right.
$$

其中： $P _ { l o s s }$ 表示系统的有功网损； $G _ { _ { i j } }$ 为支路ij的电导； $U _ { \scriptscriptstyle i }$ 、$U _ { j }$ 分别为节点 $\mathrm { i . j }$ 的电压幅值； $\delta _ { i j }$ 为节点i、j的电压相角差；$\Delta U$ 为负荷节点电压偏移量； $U _ { \iota }$ 为负荷节点处的实际电压;$U _ { \scriptscriptstyle { N } }$ 为该节点处的额定电压； $U _ { l } ^ { \mathrm { { m a x } } }$ 为允许的最大电压差。

约束条件包括不等式约束和等式约束。等式约束为系统的潮流方程。

$$
\left\{ \begin{array} { l l } { \displaystyle P _ { G i } + P _ { D G i } - P _ { L i } - U _ { i } \sum _ { j = 1 } ^ { n } U _ { j } ( G _ { i j } \cos \delta _ { i j } + B _ { i j } \sin \delta _ { i j } ) = 0 } \\ { \displaystyle Q _ { G i } - Q _ { L i } - U _ { i } \sum _ { j = 1 } ^ { n } U _ { j } ( G _ { i j } \sin \delta _ { i j } + B _ { i j } \cos \delta _ { i j } ) = 0 } \end{array} \right.
$$

不等式约束包括：

$$
\left\{ \begin{array} { l l } { P _ { D G m i n } \leq P _ { D G i } \leq P _ { D G m a x } } \\ { Q _ { D G m i n } \leq Q _ { D G i } \leq Q _ { D G m a x } } \\ { V _ { i \operatorname* { m i n } } \leq V _ { i } \leq V _ { i \operatorname* { m a x } } } \\ { P _ { L } \leq P _ { L \operatorname* { m a x } } } \\ { \sum P _ { D _ { G } } \leq P _ { \operatorname* { m a x } } } \end{array} \right.
$$

其中： $P _ { D G i } \setminus Q _ { D G i }$ 分别为分布式电源i的有功功率和无功功率;$P _ { D G \operatorname * { m a x } } \ , P _ { D G \operatorname * { m i n } } \ \cdot Q _ { D G \operatorname * { m a x } } \ \cdot Q _ { D G \operatorname * { m i n } }$ 分别为有功功率和无功功率的上、下限值； $V _ { i }$ 为节点i的线电压； $V _ { i \operatorname* { m a x } } \setminus V _ { i \operatorname* { m i n } }$ 为其上、下限值； $\sum P _ { D G } , \ P _ { \mathrm { m a x } }$ 为接入配电网的分布式电源总有功功率和容许接入配电网分布式电源最大容量。

# 3 NSGA-I算法的改进

# 3.1传统的 NSGA-I算法

NSGA-II算法是现在流行的多目标优化算法，它基于Pareto理论用精英保留策略对非支配排序产生的个体进行保存，使用拥挤距离排序避免了预先设定参数的困难，这种方法降低了算法的计算复杂性，提高了计算效率[I2]。NSGA-II算法的主要过程如图2所示。

NSGA-II算法的流程如下所示：

a)随机产生一个初始种群 $\mathbf { P } _ { 0 }$ ，然后对该种群进行非劣排序处理，然后在其中选择优秀的个体进行交叉、变异操作，得到新的种群 $Q _ { 0 }$ ，令 $\scriptstyle { \mathrm { t } = 0 }$ 。

b)令 $R _ { t } = P _ { t } \cup Q _ { t }$ ，对新产生的种群 $R _ { t }$ 进行非劣处理，得到非劣前端 F1,F2..。

c)对步骤 b)中产生的非劣前端进行拥挤距离排序，选取其中最优的个体形成新的种群 Pt+。

d)对 $P _ { t + 1 }$ 进行复制、交叉、变异操作，形成新的种群 $\boldsymbol { Q } _ { t + 1 }$ 。

e)若满足迭代的终止条件，结束循环；否则，令 $\scriptstyle { \mathrm { t } } = { \mathrm { t } } + 1$ ，回 到步骤b)。

![](images/3ddc975a4d701383b97e19ebddccd1c4b87505b35b4ab43b39b88e5dd0bd1ce8.jpg)  
图2NSGA-II算法的主要过程

NSGA-II算法的拥挤距离排序机制也有不足之处。在进化产生新种群时层级处于前列，并且拥挤距离较大的个体更容易得到保留[13]。而事实上，个体的拥挤距离与其解密度之间并不一致，这导致部分拥挤距离大且解密度也很大的非支配个体被保留下来，导致算法可能会陷入局部最优，使得所求的最优解分布不均匀。对此，本文引入了信息熵机制来提高算法的局部寻优能力。

# 3.2基于信息熵的NSGA-I算法

信息熵是信息论中的概念，用来描述信息源的不确定度，表征某种特定信息的出现概率。定义种群的信息熵[14]为

$$
E = - { \sum } _ { i = 1 } ^ { m } q _ { i } \log q _ { i }
$$

其中： $q _ { i } = \left| P _ { i } \right| / N$ ， $\mathrm { ~  ~ N ~ }$ 为种群的个体数； $\left| P _ { i } \right|$ 为 $\mathrm { \Delta \mathrm { P i } }$ 所包含的个体数目。将待优化目标在可行解范围上 $\mathrm { ~  ~ N ~ }$ 等分， $\mathrm { ~ m ~ }$ 表示种群在优化目标上处于同一范围的个体数，当 $\mathrm { m } { = } 1$ 时，E取最小值0;当 $\scriptstyle \mathrm { m = N }$ 时，E取最大值 $\log \mathrm { N }$

引入信息熵机制后种群进化的交叉、变异概率分别为

$$
\left\{ \begin{array} { l l } { \displaystyle { P _ { c } ^ { ' } = a _ { 1 } - \frac { a _ { 1 } m } { N } } } \\ { \displaystyle { P _ { m } ^ { ' } = a _ { 2 } - \frac { a _ { 2 } m } { N } } } \end{array} \right.
$$

其中： $a _ { 1 } , ~ a _ { 2 }$ 分别为大于0小于1的常数。由式(13)可知，m越小，遗传概率越大，种群的结构越丰富； $\mathbf { m }$ 越大，遗传概率越小，种群越稳定。信息熵反映个体在解空间分布的均匀程度，用信息熵去改进种群每一代的交叉概率和变异概率，可以提高算法的收敛精度和运算效率。

在种群进化的初始阶段，种群个体的相似度低，增加交叉概率，可加速种群的进化过程,减小种群的变异概率，可减少繁琐的计算过程；在进化过程的中间阶段，适当提高变异概率，能有效地防止算法迭代陷入局部最优；在进化过程的结尾，个体相似度较高，为了使得算法逐步收敛，适当降低交叉概率和变异概率。根据上述原则，将交叉概率在进化代数内近似为递减函数模型，将变异概率近似为柯西分布模型：

$$
\left\{ \begin{array} { l l } { \displaystyle { P _ { c } ^ { * } = a _ { 3 } \cos \frac { \pi } { 2 T } t } } \\ { \displaystyle { P _ { m } ^ { * } = \frac { 1 } { \pi a _ { 4 } [ 1 + ( \frac { t - T / 2 } { a _ { 4 } } ) ^ { 2 } ] } } } \end{array} \right.
$$

其中：t为当前进化代数； $\mathrm { ~ T ~ }$ 为进化的总代数； $a _ { 3 }$ 为大于0小于1的常数； $a _ { 4 }$ 为尺度参数，为大于0的常数。综上，改进算法最终的交叉概率、变异概率为

$$
\left\{ \begin{array} { l l } { \displaystyle P _ { c } = a _ { 1 } ( 1 - \frac { m } { N } ) + a _ { 3 } \cos \frac { \pi } { 2 T } t } \\ { \displaystyle P _ { m } = a _ { 2 } ( 1 - \frac { m } { N } ) + \frac { 1 } { \pi a _ { 4 } [ 1 + ( \frac { t - T / 2 } { a _ { 4 } } ) ^ { 2 } ] } } \end{array} \right.
$$

改进后算法步骤如图3所示。

开始从Rt中选择N  
t=0,随机产生 个最好的个体初始种群Po 放入Pt+1  
快速非劣排 计算Pt+1的信  
序，根据分级 息熵，交叉、确定虚拟 变异得到Qt+1适应度t=t+1  
计算种群信息  
熵，对Po进行  
交叉、变异， 达到最大得到Qo 进化代数？N  
令Rt=P:UQt,  
对Rt进行快速 Y非劣排序 结束

# 3.3算法测试

选择表1所示多目标优化测试函数ZDT1、ZDT6测试算法性能，每个测试函数运行50次取平均值，选取逼近性(AP)、运行时间(TM，单位s)作为评价指标。通过对比表2的测试数据及图4和5中的Pareto前沿可得，基于信息熵机制改进后的NSGAEN算法与传统的NSGA-II算法相比，有更好的收敛性及运行速度，其优化解集更接近真实的Pareto 前沿。

表1标准测试函数  

<html><body><table><tr><td>测试函数</td><td>表达式</td></tr><tr><td>ZDT1</td><td>min f(x)= x min f(x)=g(1-√fi/g) m g(x)=1+9∑xi/(m-1) i=2 s.t.0≤x≤1，i=1,2,·.,30</td></tr></table></body></html>

<html><body><table><tr><td rowspan="3">ZDT6</td><td>min fi(x)=1-exp(-4x𝑖)sin(6π x1) min f(x)=g(1-(f/g)²)</td></tr><tr><td>g(x)=1+9((∑x /(m-1))0.25)</td></tr><tr><td>𝑖=2 s.t.0≤x,≤1，i=1,2,·,10</td></tr></table></body></html>

<html><body><table><tr><td colspan="4">表2算法测试结果对比</td></tr><tr><td>测试函数</td><td>评价指标</td><td>NSGA-II</td><td>NSGAEN</td></tr><tr><td rowspan="2">ZDT1</td><td>AP</td><td>0.0428</td><td>0.0141</td></tr><tr><td>TM/s</td><td>19.483</td><td>17.627</td></tr><tr><td rowspan="2">ZDT2</td><td>AP</td><td>0.1374</td><td>0.0801</td></tr><tr><td>TM/s</td><td>24.354</td><td>19.615</td></tr></table></body></html>

![](images/313880a1359d78e2a4122f91142b24e655b83bfa11a29e40a9e9c4d8c18dbb45.jpg)  
图4算法在ZDT1测试函数的Pareto 最优解

![](images/f4162fd53f37b0fa2ab4b0e1dba7355fad508c271ffdb9f85db07f402e54054e.jpg)  
图3NSGAEN算法步骤  
图5算法在ZDT6 测试函数的Pareto 最优解

# 4 案例分析

选取图6所示的微电网混合仿真系统进行分析。该微电网接入的分布式电源有风力发电机、光伏电池、微型燃气轮机。微电网模型中分布式电源电压电流实验数据由光伏模拟器、双馈风力发电模拟器、燃气轮机模拟器等提供，并通过采集系统接入到仿真平台，实现与微电网能量控制与管理软件数据通信。

由于风力发电(WT)和光伏发电(PV)无燃料成本无污染，所以只计运行维护成本。微型燃气轮机(MT)要考虑发电成本、环境治理成本、运行维护成本，具体如表3所示。

![](images/5dd5d7239c6786e0d61dba9e04bbc6a54e9454ce14d0e23b3a5f358058ba07ac.jpg)  
图6实验用微电网系统仿真平台

表3微电网发电费用系数  

<html><body><table><tr><td>微电源</td><td>燃料费用/元/kWh</td><td>运维费用/元/kWh</td></tr><tr><td>PV</td><td>0</td><td>0.01</td></tr><tr><td>WT</td><td>0</td><td>0.045</td></tr><tr><td>MT</td><td>0.284</td><td>0.125</td></tr></table></body></html>

![](images/36e7bb3ee9a20789870c3f78da8abcd72359a8d29b3ea85af9f32fd16cbada4d.jpg)  
图7IEEE30节点系统结构

以装机容量5MW的微电网接入图7所示的IEEE30节点系统为例，该系统含有6台发电机，4台变压器，系统根节点的电压标么值为1.0，基准功率为 $1 0 0 \ \mathrm { M V A }$ ，将所有电源节点看做PV节点，负荷节点看做PQ节点，设定种群规模为100，进化代数为300代。图8和9分别为节点电压偏移、线路有功网损与经济成本在算法进化到300代时种群的Pareto最优解集。从实验结果得到的Pareto前沿可知，节点电压偏移、线路有功网损和投资运行成本之间存在矛盾关系，较低的投资运行成本对应较高的线路网损与节点电压偏移量，改进的NSGAEN 算法在相同的技术指标下相比于NSGA-II算法有更好的经济性。设计人员可根据实际需求和现场条件在种群的非支配解空间中选择合适的设计方案，合理分配系统的经济目标和技术目标，能有效避免盲目选择而导致的效率低下。

![](images/0a406e0feb84d4b2d4961b6b8d5d73b109e9067929bc79989499b0d7c367fc02.jpg)  
图8有功网损和经济成本的优化结果

![](images/e9d09ca8c40d465f71774ab70cb31aa99798ae48e5e4b5cf266b9a0875ec1767.jpg)  
图9电压偏移和经济成本的优化结果

以系统节点电压偏移量和线路有功网损为指标对算法的收敛性进行分析。表4和5为从系统抽取的节点和支路的优化结果对比，图10和11为这两个参数在两种算法下的收敛性对比。通过比较可知，抽取的节点和支路在改进算法的优化下，节点电压偏移量和线路有功网损都有所改善。两种算法在进化的初始阶段的节点电压偏移量和线路有功网损都比较高；随着进化的深入，传统NSGA-II算法分别在进化的第110代和100代使节点电压偏移量和线路有功网损收敛达到最优，改进后的NSGAEN算法分别在第80代和70代使节点电压偏移量和线路的有功网损收敛达到最优，改进算法的收敛速度更快，且节点电压偏移量和线路有功网损皆小于传统的NSGA-II算法。

表4节点电压偏移量(p.u.)在两种算法下的优化结果  

<html><body><table><tr><td>节点号</td><td>节点2</td><td>节点5</td><td>节点11</td><td>节点15</td><td>节点20</td><td>节点26</td></tr><tr><td>NSGA-II</td><td>0.9967</td><td>0.9814</td><td>0.9627</td><td>0.9568</td><td>0.9915</td><td>0.9756</td></tr><tr><td>NSGAEN</td><td>0.9973</td><td>0.9852</td><td>0.9673</td><td>0.9636</td><td>0.9950</td><td>0.9805</td></tr><tr><td>表5</td><td></td><td></td><td></td><td>线路有功网损(kW)在两种算法下的优化结果</td><td></td><td></td></tr><tr><td>支路号</td><td>K1,2</td><td></td><td>K10,17</td><td>K12,16 K9,10</td><td>K5,7</td><td>K25,27</td></tr><tr><td>NSGA-II</td><td></td><td>15.36</td><td>3.54</td><td>2.53 1.22</td><td>10.33</td><td>3.37</td></tr><tr><td>NSGAEN</td><td>11.32</td><td></td><td>1.96</td><td>1.88 1.14</td><td>5.24</td><td>3.18</td></tr></table></body></html>

![](images/fc6705092bc0ebd189eb0fe22236b05fbb4b890737857a0a07d394805e6899fb.jpg)  
图10节点电压偏移量的收敛特性对比

![](images/34a68bc0f7d68dff80095806448fa7141f441fa055a16999c1cdfcd895b90902.jpg)  
图11线路有功网损的收敛特性对比

# 5 结束语

针对NSGA-II算法在解决微电网多目标优化运行问题时的收敛性、运行速度这一局限性，本文主要做了下列研究工作：

a)基于信息熵机制改进优化算法的交叉算子、变异算子，提出了一种改进的NSGAEN算法。利用测试函数ZDT1、ZDT6对NSGAEN算法进行性能测试，测试结果证明了该算法的有效性。

b)针对微电网的结构及运行特点，建立了多目标数学模型。将NSGAEN算法应用于分布式电源的多目标优化。结果表明，提出的NSGAEN算法相较于原NSGA-II算法能有效改善收敛特性、提高运行效率，进一步验证了该改进算法在解决复杂的微电网多目标优化问题的可行性。

# 参考文献：

[1]路艳雪，赵超凡，吴晓锋，等．基于改进的NSGA-II多目标优化方法研 究[J].计算机应用研究，2018,35(6):1733-1737.(Lu YanXue,Zhao Chaofan,Wu Xiaofeng，et al.Multi-objective optimization method research based on improved NSGA-I[J].Application Research of Computers,2018,35(6):1733-1737.)

[2]陈萍，毛弋，童伟，等．基于多目标粒子群算法的配电网多目标优化重 构[J]．电力系统及其自动化学报,2016,28(7):68-72.(Chen Ping,Mao Yi,Tong Wei,et al.Multi-objective distribution network reconfiguration based on multi-objective particle swarm optimization [J]. Proceedings of the CSU-EPSA,2016,28(7):68-72.)

[3]冯金芝，陈兴，郑松林．一种改进的多目标粒子群优化算法及其应用 [J].计算机应用研究,2014,31(3):675-683.(Feng Jinzhi,Chen Xing, Zheng Songlin. Improved MOPSO algorithm and itsapplication [J]. ApplicationResearchof Computers,2014,31(3):675-683.)

[4]谭兴国，王辉，张黎，等．微电网复合储能多目标优化配置方法及评价 指标[J].电力系统自动化,2014,38(8):7-14.(Tan Xingguo,Wang Hui, Zhang Li,et al. Multi-objective optimization of hybrid energy storage and assessment indices in micro-grid [J].Automation of Electric Power Systems,2014,38 (8): 7-14.)

[5]时统宇，王大志，李召．基于多种群遗传算法的永磁涡流驱动器的多目 标优化设计[J]．电工技术学报，2016,31(2):262-268.(Shi Tongyu, Wang Dazhi,Li Zhao.Multi-objective optimization design ofPMECD by multiplepopulationgenetic algorithm[J]. Transactions of China Electrotechnical Society,2016,31(2): 262-268.)

[6]靳冰洁，张步涵，姚建国，等．基于信息熵的大型电力系统元件脆弱性 评估[J].电力系统自动化，2015,39(5):61-68.(Jin Bingjie,Zhang Buhan，Yao Jianguo，et al.Large-scale power system components vulnerability assessment based on entropy [J].Automation of Electric Power Systems,2015,39(5):61-68.)

[7]于青，刘刚，刘自发，等．基于量子微分进化算法的分布式电源多目标 优化规划[J].电力系统保护与控制,2013,41(14):66-72.(YuQing,Liu Gang,Liu Zifa,et al. Multi-objective optimal planning of distributed generation based on quantum differential evolution algorithm [J].Power System Protection and Control,2013,41 (14): 66-72.)

[8]王鹏飞．基于布谷鸟算法的微电网多目标优化运行研究[D].北京：华 北电力大学,2017.(Wang Pengfei.Research on multi objective optimal operation of micro grid based on cuckoo algorithm [D].Beijing:North China Electric Power University,2017)

[9]Faisal A M,Heikki N K.Online management of micro-grid with battery storage using multi-objective optimization [C]// Proc of International Conference on Power Engineering,Energy and Electrical Drives.2007: 231-236.

[10]孙元章，吴俊，李国杰，等．基于风速预测和随机规划的含风电场电力 系统动态经济调度[J].中国电机工程学报，2009,29(4):41-47.(Sun Yuanzhang，Wu Jun,Li Guojie,et al.Dynamiceconomic dispatch considering wind power penetration based on wind speed forecasting and stochastic programming [J].Proceedings of the CSEE,2009,29(4): 41-47.)

[11]王瑞琪.分布式发电与微网系统多目标优化设计与协调控制研究 [D] 济南：山东 大学，2013.(Wang Ruiqi.Research on multi-objective optimization design and coordinated control of distributed generation and micro-grid [D]. Jinan: Shandong University,2013.)

[12]雷德明，严新平．多目标智能优化算法及其应用[M].北京：科学出版 社，2009:47-49.(Lei Deming,Yan Xinping.Multi-objective intelligent optimization algorithm and its application [M].Beijing:Science Press, 2009:47-49.)

[13]张屹，陈平，万兴余．基于正交设计NSGA-II算法的制动器多目标优化 研究[J].计算机应用研究,2016,33(3):720-725.(ZhangYi,Chen Ping, Wan Xingyu.Multi-objective optimization of automotive brake based on orthogonal design ofNSGA-I [J].Application Research of Computers, 2016,33 (3): 720-725.)

[14]傅平，罗可．基于信息熵的免疫遗传算法聚类分析[J].计算机工程, 2008，34 (6):235-238.(Fu Ping，Luo Ke.Clustering analysis of immune-genetic algorithm based on information entropy [J]. Computer Engineering,2008,34(6): 235-238.)