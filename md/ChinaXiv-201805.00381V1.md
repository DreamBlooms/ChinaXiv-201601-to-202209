# 基于CARLA-PSO组合模型的智能控制器参数学习优化

谷学静1，张明儒1，王志良²，郭宇承

(1.华北理工大学 电气工程学院，河北 唐山 063009;2.北京科技大学 计算机与通信工程学院，北京 100083;3．华北理工大学 轻工学院，河北 唐山 063000)

摘要：对连续动作强化学习自动机（CARLA）进行了改进，应用改进后的CARLA结合粒子群优化算法（PSO）优化PID 参数。以CARLA为基础，建立了CARLA和PSO的组合优化学习模型CARLA-PSO，该模型包含CARLA学习环路和PSO学习环路两个部分，通过优化策略选择器进行学习环路的选择，通过与环境进行相互作用，获得最优控制。本文对连铸结晶器液位控制进行了仿真实验，实验结果表明，CARLA-PSO 在进行PID 参数优化时寻优效率高，全局搜索能力强，能够达到理想的控制效果。具有较好的应用前景。

关键词：连续动作学习强化自动机；粒子群优化算法；智能PID控制器；结晶器液位 中图分类号：TP301.6 doi:10.3969/j.issn.1001-3695.2017.09.0927

# Parameter learning optimization of intelligent controller based on CARLA-PSO Composite Model

Gu Xuejing1, Zhang Mingru1,Wang Zhiliang², Guo Yucheng³ (1.SchoolofElectricalEngineering,NrthChina UniversityofScience&TechnologyangshanHebeiO630l7,China;2. SchoolofComputer&ConmunicationEngineering,UniversityofScience&TechnologyBeijing,Beijinglo83,China;3. Collge ofLight Industry,North China UniversityofScience& Technology,Tangshan Hebei O6300o,China)

ABSTRACTThis paper presented a hybrid approach involving continuous action reinforcement learming automata (CARLA) and particle swarmoptimization (PSO)todesignaoptimaland intellgentproportiona-lintegral-derivative (PID)controllerof an mould level control system.The proposed method is CARLA which isable to explore and learn to improve control performance without the knowledgeof the analytical system model.CARLA-PSO is composed oftwo sections which are the CARLA learning loop,and thePSO learning loop,and select learming loopaccording to the Optimal policyselector.CARLAPSO is a methodthatcombines the features ofPSOand CARLA inorder to improve theoptimizeoperation through interaction withthe environment.The experimentalresultsshowthat CARLA-PSO was indeed more eficientinimproving the stepresponse of an mould level control system.

Key Words: Continuous actionreinforcement learingautomata; particle swarmoptimization;inteligentPIDcontroler;mould level

# 0 引言

结晶器是连铸机上的重要设备，其液位的控制精度对提高生产率、生产特殊钢材、降低连铸的漏钢事故率有重要意义[]。由于结晶器液位控制系统具有非线性、强耦合等特点，且扰动因素较多[2]，传统的PID控制只在特定工艺条件下才能实现较好的液位闭环控制。

智能控制理论是对人或动物局部智能的模仿，已成为解决复杂与难控系统的主要途径。针对传统PID控制方法在结晶器液位控制中的不足，童朝南[3]等将一种基于遗传算法的有约束广义预测控制方法应用于结晶器液位控制，控制效果优于传统PID 控制。为了实现结晶器液位PID控制器参数的自整定，曹光明[4等提出了模糊自适应PID控制策略；房启超[5等提出了基于变惯性性权重和多种群并行优化策略的改进PSO算法。

PSO是一种基于种群的随机优化技术，被广泛用于解决多目标、多参数的学习优化问题[6-8]。强化学习（RL）是一种在线的，介于监督学习和非监督学习之间的机器学习方法[9]，已被用于导弹制导控制与飞机的智能逃避[10]、机器人在未知环境下的自动避障[II]、学习型双连杆机械臂的控制[I2]等智能控制领域。学习自动机（LA）是强化学习的主要工具[I3]，CARLA是其中的一种，其主要特点是可以输出连续的动作，具有很强的全局搜索能力。MNHowell[14]等人将CARLA方法应用于发动机怠速系统PID控制器的参数整定，在系统模型信息不足的情况下,有效的解决了车辆尾气排放超标和汽车失速的问题；MKashki[15]等人将CARLA方法应用于功率同步发电机自动电压调节器PID参数自整定，仿真结果证明，与PSO、遗传算法相比，该方法具有更高的控制精度。

本文以CARLA为基础设计了CARLA-PSO组合优化模型，该组合优化模型优化过程分为两个阶段，每个阶段分别对应着CARLA学习环路、PSO学习环路。前期阶段采用CARLA进行“粗调”优化，使环境适应度评价值迅速收敛到稳定状态；后期阶段采用PSO进行“微调”优化，进一步提高环境适应度评价值的精度。该模型在连铸结晶器液位控制器的参数在线学习优化中表现良好。

# 1 CARLA-PSO组合模型的设计

本文建立了一种CARLA-PSO 组合模型，用于智能控制器参数在线学习优化。如图2所示，通过“策略选择器”进行学习环路选择。启动“策略选择器”，利用CARLA学习环路进行全局搜索，当环境适应度值将为学习环路启动时的 $1 0 \%$ 时，“策略选择开关”拨至PSO学习环路继续搜索最优参数。具体步骤如下：

a)初始化参数，例如：迭代次数、种群个数、粒子范围等。

b)通过CARLA学习环路确定PSO学习环路粒子初始位置。

c)计算每一代的环境适应度值。

d)计算每一代每个粒子群的局部最优位置和全局最优位置。

e)更新粒子群速度、位置、局部最优位置、全局最优位置。

f)重复步骤c)\~e)，直到达到最大代数或连续 $\mathbf { \Sigma } _ { m }$ 代环境适应度值不在发生变化。

![](images/5c4fe18b69010c5a3578bbe85e87c15165f9724237c2c7b3c39e03656c3e7583.jpg)  
图1CARLA-PSO 组合模型学习环路

# 1.1 CARLA学习环路设计

CARLA通过试错、随机行为选择与未知或随机环境交互获得策略的改进，应用于连续变化参数的在线寻优。与常用的强化学习不同的是，CARLA采用连续行为空间取代离散行为空间，通过概率密度函数获得收敛信息，因此CARLA更适合于具有连续特征的工程应用当中。

每个学习变量对应一个CARLA，每个参数的学习过程独立运行，将它们联系起来的唯一因素是动力学环境，并且它们共享代价函数。在每个自动机中，每个行为 $x _ { i }$ 都对应着一个概率密度函数 $f ( x _ { i } )$ 作为行为选择的依据。借助强化信号 $\beta$ 产生表现更好的行为集合，通过学习子系统增大该行为集合被重新选择的概率。CARLA学习环路的设计主要有以下几步：

a）初始化密度函数。采用均匀分布的形式初始化概率密度函数，即根据每个参数的范围，其最大值与最小值之差的倒数作为概率密度函数，具体公式如下：

$$
f ^ { 0 } ( x ) = \left\{ \begin{array} { c c } { 1 } & { x \in [ x _ { \mathrm { m i n } } , x _ { \mathrm { m a x } } ] } \\ { 0 } & { \qquad \quad \mathrm { ~ \# ~ \# ~ \# ~ } } \end{array} \right.
$$

其中： $\mathbf { X } = \{ x _ { 1 } , x _ { 2 } ^ { } \cdots x _ { n } ^ { } \}$ 为决策行为， $f = \{ f _ { 1 } , f _ { 2 } \cdots f _ { n } \}$ 对应每一个行为的密度函数。

b)行为选择。

$$
\int _ { 0 } ^ { x _ { i } ( k ) } f _ { i } ( x _ { i } , k ) d x _ { i } = z _ { i } ( k )
$$

其中：随机数 $z$ 取值范围(0,1)，将行为集合输入到环境中，通过预先定义好的代价函数得到代价值 $J ( k )$

c)行为表现评估计算。得到代价值 $J ( k )$ 后，根据下面的公式评估行为表现评估：

$$
\beta ( k ) = \operatorname* { m i n } \left\{ \operatorname* { m a x } \left\{ 0 , \ \frac { J _ { m e d } - J ( k ) } { J _ { m e d } - J _ { \operatorname* { m i n } } } \right\} , 1 \right\}
$$

其中：通过当前代价值 $J ( k )$ 与历史代价值集合中最小值 $J _ { \operatorname* { m i n } }$ 、中位值 $J _ { { \scriptscriptstyle m e d } }$ 的比较，得当前行为的好坏权重。其中行为表现强化信号 $\beta \in [ 0 , 1 ]$ ，越接近1，说明行为表现越好。越接近0，说明行为表现越差。

d)更新概率密度函数。

$$
f ^ { ( k + 1 ) } ( x ) = \left\{ \begin{array} { c c } { \alpha ^ { k } ( f ^ { ( k ) } ( x ) + \beta ( k ) H ( x , r ) ) } & { x \in [ x _ { \operatorname* { m i n } } , x _ { \operatorname* { m a x } } ] } \\ { 0 } & { \nexists \nparallel \nparallel } \end{array} \right.
$$

其中： $H ( x , r )$ 为高斯近邻函数，其值可以改变行为的可能性。

$$
H ( x , r ) = \lambda \exp \left( - \frac { ( x - r ) ^ { 2 } } { 2 \sigma ^ { 2 } } \right)
$$

$$
\alpha ^ { ( k ) } = \frac { 1 } { \int _ { x _ { i } ^ { \operatorname* { m i n } } } ^ { x _ { i } ^ { \operatorname* { m a x } } } [ f _ { i } ( x _ { i } , k ) + \beta ( k ) H ( x _ { i } , r ) ] d x _ { i } }
$$

$$
\lambda = \frac { g _ { h } } { ( x _ { \operatorname* { m a x } } - x _ { \operatorname* { m i n } } ) }
$$

$$
\sigma = g _ { \mathrm { _ w } } ( x _ { \mathrm { m a x } } - x _ { \mathrm { m i n } } )
$$

其中： ${  { g } _ { h } } \ , \ \mathrm { ~ } \mathrm { ~ } g _ { \mathrm { ~ w ~ } }$ 分别为高斯分布函数的高度和宽度，其值可以决

定学习的速度： $\boldsymbol { r }$ 为本次学习得到的动作值。 $\alpha$ 称为归一化因子，可使密度函数 $f$ 保持在[0,1]内。

# 1.2一种改进的CARLA

CARLA的动作集是一个有限的区间，并采用一种非参数化的概率模型。其初始动作概率为均匀分布，在学习过程中一个对称的高斯近邻函数，将表现较好的动作的奖赏“传播”给相邻动作。由于使用非参数化的概率模型。该方法对概率分布的计算、存储和更新相当复杂，同时在每次学习中都必须进行积分函数的更新，积分方程的求解，计算代价很高，算法的实时性差。

为克服现有算法的不足，本文对CARLA做了一些改进，采用式(5)更新行为向量。

$$
x _ { i } ( k + 1 ) = \left\{ { \begin{array} { c c } { n o r m ( x _ { i } ( k ) , \omega \mathbf { e } ^ { ( 1 - \beta ( k ) ) } ) } & { x _ { i } ( k ) \in [ x _ { \operatorname* { m i n } } , x _ { \operatorname* { m a x } } ] } \\ { x _ { i } ( k ) } & { { \ddag } \sharp / \sharp } \end{array} } \right.
$$

其中： $n o r m ( \mu , \sigma )$ 为正态随机数发生器，其中 $\mu$ 为期望， $\sigma$ 为方差。 $\omega$ 学习速率因子。图2为改进前后算法执行速率对比，由图易知，改进前的CARLA在一定次数的学习后，算法执行时间陡然增加，几乎无法运行。改进后的CARLA学习次数与算法执行时间为线性关系，与改进前相比，计算时间大大缩短，算法的实时性显著提高。

![](images/96fcd5db3da7a24eb0faf8868f0b6fe6a6d191eb4399fea82085d1d341080eb2.jpg)  
图2改进前、后CARLA算法执行时间

# 1.3 PSO学习环路设计

PSO最初由Kennedy和Eberhart提出[16],最初是起源于对简单社会系统的模拟。PSO 结合了鸟类的认知行为和社会合作。该方法在解决非线性。不可微、多极点、高维问题上具有很好的鲁棒性[17]。PSO 模仿鸟群。鱼群的群集行为，这些群体按照一种合作的方式寻找食物，群体中的成员学习它自身的经验和其他成员的经验不断改变其搜索模式。PSO同遗传算法类似，是一种基于迭代的优化算法。系统初始化为一组随机解，通过迭代搜寻最优值。PSO学习环路设计主要有如下几步：

a)初始化。设置粒子群的大小 $\mathbf { \Omega } _ { N }$ ，初始位置（204号 $X _ { i d } = \{ X _ { i 1 } , X _ { i 2 } \cdots , X _ { i n } \}$ ，初始速度 $V _ { i d } ( 0 ) = \{ V _ { i 1 } , V _ { i 2 } { \cdots } , V _ { i n } \}$ ，最大速度区间[Vmin,Vmax]。

b)更新速度和位置公式。

$$
V _ { i d } ( k + 1 ) = \delta V _ { i d } ( k ) + V _ { i d 1 } ( k + 1 ) + V _ { i d 2 } ( k + 1 )
$$

$$
X _ { i d } ( k + 1 ) = X _ { i d } ( k ) + V _ { i d } ( k + 1 )
$$

$$
{ V ^ { p } } _ { i d } ( k + 1 ) = C _ { 1 } r a n d o m ( 0 , 1 ) ( p b e s t _ { i } ( k ) - X _ { i d } ( k ) )
$$

$$
V ^ { g } { } _ { i d } ( k + 1 ) = C _ { 2 } r a n d o m ( 0 , 1 ) ( g b e s t ( k ) - P _ { i d } ( k ) )
$$

其中： $i = 1 , 2 , \cdots , N \ , \ N$ 为粒子群的总数。 $d = 1 , 2 , \cdots n$ ， $n$ 为行为个数， $V _ { i d }$ 为第 $i$ 个粒子中第 $d$ 个行为的速度， $X _ { i d }$ 为第 $i$ 个粒子中第 $d$ 个行为的位置。 $\boldsymbol { \delta }$ 为惯性因子（ $\delta > 0$ )，其值越大，全局寻优能力越强，其值越小，局部寻优能力越强。 $C _ { 1 }$ 和 $C _ { 2 }$ 为称为加速常数，一般的 $C _ { 1 } = C _ { 2 } \in [ 0 , 4 ]$ ，random(0,1)表示区间[0,1]上的均匀随机数， $p b e s t _ { i } ( k )$ 为第 $i$ 个粒子当前最好位置，gbest(k)为整个粒子群当前的最好位置。

c)终止条件。有两种终止条件可以选择：一是达到最大代数 $G _ { \mathrm { m a x } }$ ，二是连续 $\mathbf { \Sigma } _ { m }$ 代环境适应度值不在发生变化即停止。

# 2 应用实例实验

# 2.1结晶器液位控制的描述

如图3所示，连铸工艺结晶器液位控制流程可简述如下：钢液从钢包（1）通过滑动水口流向中间包（2)，控制系统根据浇铸速度通过塞棒（3）的上下移动控制中间包水口的开度。通过控制从中间包流向结晶器（4)钢液的流量来控制结晶器液位的稳定。液位传感器（5）将结晶器液位变化传给控制器（6)，控制器驱动塞棒升降机构（7）改变塞棒位置，控制中间包到结晶器的钢液流量，从而达到结晶器液位稳定的目的。

结晶器液位控制具有非线性、时滞、干扰因素多的特点，常规的PID控制器很难取得满意的控制效果。在这种情况下吸取智能控制思想并利用计算机技术的优势对传统PID控制进行改造，成为当前连铸生产工艺结晶器液位控制研究的热点。本文尝试使用上述组合模型对传统PID控制器进行改进，实现结晶器控制器参数在线学习优化。

![](images/046372a5c272d27d2213792b7d9efec404a12f36a465122ef9363d0dda957027.jpg)  
图3结晶器液位控制系统结构图

# 2.2液位控制模型与参数

本文对唐山某钢厂2号连铸机液位控制对象进行系统辨识，主要参数如表1所示。为了用参数辨识法获得对象的模型，以液压伺服阀开度作为系统输入变量，结晶器液位为系统输出变量。采用最小二乘法辨识系统模型[18]，所得传递函数为

$$
G ( s ) = { \frac { 0 . 0 8 s + 1 } { 0 . 1 1 s ^ { 2 } + 0 . 1 s + 0 . 0 0 2 } } \ \circ
$$

表1液位控制模型参数  

<html><body><table><tr><td>参数名称</td><td>参数符号</td><td>参数取值</td></tr><tr><td>拉坏速度</td><td>V</td><td>2.3m /min</td></tr><tr><td>结晶器长度</td><td>L</td><td>900mm</td></tr><tr><td>铸坏断面(8)</td><td>S</td><td>160mm *160mm</td></tr></table></body></html>

# 2.3环境适应度函数的定义

在设计结晶器液位智能控制器时，首先应该定义控制器性能评价函数（也称环境适应度函数)。典型的时域输出性能指标是系统阶跃响应的超调量、上升时间、稳态时间、稳态误差。总的来讲，常见的控制器性能评价准则有四种：综合绝对误差(IAE， $J = \int \left| \Delta e \right| d t ^ { \mathrm { ~ } } )$ ，平方误差积分（ISE， $\begin{array}{c} J = \int ( \Delta e ) ^ { 2 } d t  \end{array} )$ ，时间加权绝对误差积分（ITAE， $J = \int t { \big | } \Delta e { \big | } d t \ ^ { \mathrm { ~ } } \big )$ ，时间加权平方误差积分（ITSE， $J = \int t ( \Delta e ) ^ { 2 } d t ^ { \mathit { \Sigma } } )$ 。每一种评价准则都有各自的优缺点。通过最小化IAE，ISE能够有效减小超调量，但对缩短稳态时间的影响很小，ITAE、ITSE可以克服前者的不足，但解析公式的推导比较复杂耗时。考虑到结晶器液位控制实际要求，本文采用ITSE评价准则，CARLA-PSO环境适应度函数定义如下:

$$
J ^ { k } = \sum _ { i = 1 } ^ { n } n [ Y _ { i } - { y _ { i } } ^ { k } ] ^ { 2 }
$$

其中： $Y$ 实际响应曲线， $y$ 为理想响应曲线， $\mathbf { \Sigma } _ { n }$ 为采样次数，$k$ 为CARLA-PSO迭代学习的次数。

# 2.4仿真结果分析

依据结晶器液位 $\mathrm { P I D }$ 控制器实际调参经验，设置 $k _ { p } \ 、 k _ { i }$ 、$k _ { d }$ 的动作集区间分别为[0,2]，[0,1]，[0,2]；初始化CARLA学习速率因子 $\scriptstyle \omega = 0 . 1$ ；粒子群大小 $\scriptstyle N = 3 0 0$ ，粒子初始速度$V _ { i d } ( 0 ) = \{ 0 , 0 ^ { \ldots } , 0 \}$ ，粒子搜索速度区间为[-0.5,0.5]，惯性因子$\delta { \bf \phi } ^ { \mathrm { ~ ( ~ } } \delta > 0 { \bf \phi } ^ { \mathrm { ~ ) ~ } }$ 典型取值为0.4或0.9，因为后期为“微调”阶段，所以 $\delta$ 取值应较小，取0.4， $\scriptstyle { C _ { 1 } = \ C _ { 2 } = 0 . 8 }$ 。结晶器液位控制系统输入信号为单位阶跃信号，结晶器液位采样时间为 $5 0 \mathrm { s }$ 。

图 ${ 4 } _ { a _ { , } }$ 给出了原系统在无控制器作用下的响应曲线（实线部分)，存在明显的超调和稳态误差并且响应时间过长。虚线为理想响应曲线。 $b ) \ c ) \ d )$ 给出了具有代表性的三次学习过程，第4次迭代优化后适应度值下降了近一半。当迭代优化次数达到100次后系统响应曲线无明显超调，响应时间大大缩短，适应度值下降至最初的 $10 \%$ 。此时，优化策略选择器断开CARLA学习环路，接通PSO学习环路，系统进入后期优化阶段，CARLA-PSO迭代优化500次后系统响应接近理想状态。e)为CARLA-PSO算法收敛曲线。

为了验证CARLA-PSO算法的性能，本文给出了CARLA与 PSO 算法单独作用下的适应度收敛效果，如图5所示。CARLA-PSO算法结合了CARLA全局搜索能力强与PSO更新速度快的优点，与CARLA算法、PSO 算法相比较，具有更快的收敛速度和更高的优化精度。

![](images/826232ed826de5b10e4557597fffb182d848f3acebf274f054e1e7ae771acc05.jpg)  
图4CARLA-PSO优化过程示意图

![](images/80ea53096fd2d25e491671515d53613a20766687cb73d4773a49a6fe8170c612.jpg)  
图5CARLA-PSO、CARLA、PSO 性能对比

# 3 结束语

本文讨论了CARLA模型，并对传统CARLA更新行为函数进行了修改，设计了一种改进的CARLA，提高了CARLA算法的执行速率，增强了算法的实用性。在此基础上，结合PSO算法，建立了CARLA-PSO组合优化模型。该模型能够自主学习控制规则，收敛速度快，精度高。最后将模型用于连铸结晶器液位控制中，仿真实验表明，在与环境进行多次交互后，模型可自主获取较好的结晶器液位控制规律，与CARLA单独作用于系统相比，CARLA-PSO收敛速度快，优化效率高。对于该模型下一步研究的重点是连铸其他控制环节，并用于真实的结晶器液位控制系统或其他被控对象。

# 参考文献：

[1]李祖林．结晶器液位专家系统控制研究[J].计算机工程与应用,2009,45 (10): 199-201.[2]Passenbrunner T. Mold level control of a continuous casting plant by

switching control strategies [J]. IFAC Proceedings Volumes,2010,43 (14): 1350-1355.   
[3]童朝南，肖磊，彭开香，等．基于遗传算法的结晶器液位约束广义预测 控制[J].控制与决策,2009,24(11):1735-1739.   
[4]曹光明，吴迪，张殿华．基于模糊自适应PID的铸轧机结晶器液位控制 系统[J].控制与决策,2007,22(4):399-402.   
[5]房启超，徐林，王建辉，等.改进的PSO及其在结晶器液位控制中的应 用[J].仪器仪表学报,2006,27(11):1399-1402.   
[6]Delgarm N, Sajadi B,Kowsary F,et al. Multi-objective optimization of the building energy performance:a simulation-based approach by means of particle swarm optimization (PSO)[J].Applied Energy,2016,170: 293-303.   
[7]熊伟丽，徐保国，周其明．基于改进粒子群算法的PID参数优化方法研 究[J].计算机工程,2005,31(24):41-43.   
[8]黄为勇，徐晓菊，潘晓博，等.量子粒子群优化算法的收缩一扩张系数 控制策略研究[J].计算机应用研究,2016,33(9):2592-2595.   
[9]刘晓．基于连续动作学习自动机的联想强化学习[J]．山西大学学报： 自然科学版,2015,38(3):426-431.   
[10]周锐，陈宗基．强化学习在导弹制导中的应用[J].控制理论与应用， 2001,18 (5): 748-750.   
[11]钟宇平，王丽丹，段书凯，等．基于神经网络及强化学习的智能控制系 统[J]．西南大学学报：自然科学版,2013,35(11):172-179.   
[12] Shah H, Gopal M.A reinforcement learning algorithm with evolving fuzzy neural networks [J]. IFAC Proceedings,2014,47(1):1161-1165.   
[13] Mirsaleh MR,Meybodi MR.Alearning automata-based memetic algorithm [J].Genetic Programming& Evolvable Machines,2015,16(4):399-453.   
[14]Howell MN,Gordon TJ,Best M C.The application of continuous action reinforcement learning automata to adaptive PID tuning [Cl// Learning Systems for Control.London: IEEE Xplore,20oo:2//1-2//4.   
[15] Kashki M,Abdel-Magid Y L,Abido M A.A reinforcement learning automata optimization approach for optimum tuning of PID controller in AVR system [C]// Proc of International Conference on Intelligent Computing:Advanced Inteligent Computing Theories and Applicationswith Aspects of Artificial Intelligence.[S.1.[: Springer-Verlag,2008:684- 692.   
[16] Hasanien HM.Design Optimization of PID controller in automatic voltage regulator system using taguchi combined genetic algorithm method [J]. IEEE Systems Journal, 2013,7(4): 825-831.   
[17]宋明智，杨乐．基于改进自适应 PSO 算法的 WSN 覆盖优化方法[J]. 计算机应用研究,2013,30(11):3472-3475.   
[18]章家岩，郎佳红，王金忠．转炉炉口微差压滑模变结构控制技术[J]. 控制工程,2009,16(4):419-422.