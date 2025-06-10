# 多种群遗传算法与截断奇异值分解法在开关电弧反演中的应用

赵宏晨」王　刚²刘晓明（1.沈阳工业大学电气工程学院沈阳 110870)(2.贵州理工学院机械工程学院贵阳 5500033.天津工业大学天津市电工电能新技术重点实验室天津300387）

![](images/ceb40ecf9b8ce79f8539127ad90eddfdcb592da96e72cc7d1f4d02ef682eb927.jpg)

赵宏晨男 1989年生，博士研究生，主要研究方向为电弧反演问题、智能优化算法。

摘要：利用电流与空间磁场的对应关系，将电弧视为具有变弧径多条电流线集合。基于毕奥萨伐尔定律，通过正演分析获取组合电弧电流线在空间的磁场分布。为简化问题复杂度，考虑电弧未入栅片的阶段，利用多种群遗传算法优化目标函数求解电磁逆问题非线性方程组，以确定电弧空间位置。在上述基础上，为解决逆问题不适定性，采用截断奇异值分解法反演电弧电流分布，并通过GCV准则获取正则化参数。反演结果有助于理解开关电弧的物理特性。

关键词：开关电弧反演不适定性多种群遗传算法截断奇异值分解GCV 准则中图分类号：TM501

# Application of Multi-Population Genetic Algorithm and Truncated Singular Value Decomposition in Switching Arc Inversion

![](images/0734b82abbb52f4429f2451b0e94566e600f395532357f32c97710b4d6eeb56b.jpg)

Zhao Hongchen'Wang Gang²Liu Xiaoming? (1.Shenyang University of TechnologyShenyang 110870 China 2.Guizhou Institute of TechnologyGuiyang550003 China 3.Tianjin Polytechnic UniversityTianjin300387 China ）

王刚男1989年生，博士，副教授，主要研究方向为矩阵分析、$H _ { \infty }$ 控制及正则化方法。

Abstract: By using the corresponding relationship between the current and the space magnetic field, the arc is regarded as a set of multiple current lines with variable arc diameters.Based on Biot-Savart's law, the magnetic field distribution of combined arc streamlines in space is obtained by forward analysis.To simplify the complexity of the problem,the research only considers the phase of the arc not entering the splitter plates, and the multi-population genetic algorithm(MPGA) is used to optimize the objective function for solving the nonlinear equations of the electromagnetic inverse problem to determine the space position of the arc. On the basis of the above,the truncated singular value decomposition(TSVD) method is used to inverse the arc current distribution, with the regularization parameters obtained by the GCV criterion. The inversion results will contribute to understand the physical characteristics of the switch arc.

KeyWords: Switching arc inverse problem, ill-posed,MPGA, TSVD, GCV criterion

# 1 引言

断路器作为电力系统中的控制与保护装置，在故障情况下切断线路以保护人身和系统安全。作为有触点开关，断路器在切断电流时伴随触头分离，不可避免地产生电弧[1]。电弧的燃烧是在多物理场耦合作用下复杂的非线性过程，具有随机性和混沌性[2]。常用低压断路器，是以空气为灭弧和绝缘介质，其电弧一方面给系统电路提供导电通路；另一方面电弧将烧蚀电极和灭弧系统内结构部件，影响开关寿命[3]。电弧行为时空域演化研究，对开关电器开断能力和寿命有着重要影响。

目前，开关电弧实验研究主要手段有高速电荷耦合器件（Charge Coupled Device，CCD）摄像[4]、光纤阵列[5、光谱测试[以及磁测试方法等。其中，基于光学的测试方法会影响实验样机的完整性，进而影响灭弧室本体内电弧等离子体的动态特性。磁测试技术多采用非接触式测量手段，基于电弧电流所产生的磁场时空分布反演电弧电流可能存在的空间位置与形态[7-10]。文献[11-12]对比了各优化算法重构电弧的误差，采用模拟退火算法较准确地获取电弧形态，并利用磁成像测量装置检验算法的可行性；文献[13-14]将电弧发生区域剖分，并将电磁正演算子离散化为线性算子，采用正则化方法反演电弧电流；文献[15]比较了各正则化参数选取策略重构低压开关电弧电流的精度，并分析了采样距离以及采样点数量对反演精度的影响。

综上所述，低压开关电弧模型假设为变弧径多电流线集成，基于电弧电流与磁场的对应关系，将求解非线性方程组转化为优化问题，采用多种群遗传算法获取电弧位置及形态分布以建立正演算子。为克服反演的不适定性，采用截断奇异值分解并利用GCV准则求取截断参数，借助于磁场分布捕捉电流分布。结果证实了该方法能较准确地重构电弧电流，有助于指导高性能可靠性开关电器的设计。

# 2 低压开关电弧物理模型

# 2.1模型与相关假设

低压断路器灭弧系统二维简化模型如图1所示。当动静触头分离时，断口间产生电弧，随着行程增加，电弧被拉长，直到完全打开，动触头到达最大开距。在吹弧气流的作用下，电弧运动至灭弧室某位置。根据文献[7]，由于灭弧室器壁的限制，设电弧运动轨迹在 $x O z$ 平面内。电弧模型简化为多条电流线集合，各电流为三段式折线，各条折线的节点位于电极间距的等分线上。由于近极区的电流密度大，因此对弧柱的收缩压力较强，故可暂不考虑近极区的弧柱半径。若各节点坐标为 $A ( x _ { a }$ 0， $\textstyle z _ { a } )$ 、 $B ( x _ { b } , \ 0 , \ z _ { b } )$ 、 $C ( x _ { c } , \ 0 , \ z _ { c } )$ ， $D ( x _ { d } , \ 0 , \ z _ { d } )$ ，如图2所示，则电极间距确定时，各节点的 $z$ 坐标为已知量。根据文献[9]，磁场采样平面距离电弧发生面大于 $1 5 \mathrm { m m }$ 时，栅片等磁性材料对电弧反演精度的误差小于 $5 \%$ ，因此采样距离为 $1 5 \mathrm { m m }$ 。为了验证该方法的可行性，本文仅研究电弧未入栅片的阶段，即图1中虚线包含区域 $\varOmega$ ，该段区间面积为 $5 0 \mathrm { m m } \times 3 0 \mathrm { m m }$ 。磁采样点采用 $4 \times 6$ 的阵列分布，如图2所示。

![](images/6e1134b7a2c88991cb6e2c8a7418b57494d586368e48f90a7cf37daf00d435f5.jpg)  
图1电弧电流线模型

![](images/a8617f74cb08236f7c140705c1a1601138c0a16b2bd2991d8bc26a6841478eab.jpg)  
Fig.1The arc current line model   
图2磁采样点分布  
Fig.2Distribution of the magnetic sampling points

# 2.2电流线元的磁场

根据毕奥萨伐尔定律，空间电流元产生的磁感应强度 $\textbf {  { B } }$ 为

$$
\pmb { { \cal B } } = \frac { \mu _ { 0 } \pmb { { \cal I } } _ { \mathrm { e } } } { 4 \pi d _ { 0 } } ( \cos \theta _ { \mathrm { i } } - \cos \theta _ { 2 } )
$$

式中， $d _ { 0 }$ 、 $\theta _ { 1 }$ 、 $\boldsymbol { \theta } _ { 2 }$ 如图3所示， $\mu _ { 0 }$ 为真空磁导率。图3中，设空间电流线 $\mathbf { \nabla } _ { A B }$ 在 $x O z$ 平面内， $S$ 点位于距离 $\mathbf { \nabla } _ { A B }$ 为 $d$ 的平面 $E F G H$ 内。 $\theta _ { 1 }$ 和 $\theta _ { 2 }$ 分别为端点 $A ( x _ { a } , \ 0 , \ z _ { a } )$ ， $B ( x _ { b } , \ 0 , \ z _ { b } )$ 与该处到采样点 $S ( x _ { s }$ $0 , \ z _ { s } )$ 的夹角。推导得 $s$ 点处 $B _ { x }$ ， $B _ { y }$ 、 $B _ { z }$ 分别为

$$
B _ { x } = \frac { \mu _ { 0 } I } { 4 \pi d _ { 0 } } \frac { b _ { 1 } } { b } ( \cos \theta _ { 1 } - \cos \theta _ { 2 } )
$$

$$
B _ { y } = \frac { \mu _ { 0 } I } { 4 \pi d _ { 0 } } \frac { b _ { 2 } } { b } ( \cos \theta _ { \mathrm { 1 } } - \cos \theta _ { \mathrm { 2 } } )
$$

![](images/2e5264bfdeaabdbfccff69fa0c24f48c671bfae29d4d29e517eba632ecd87200.jpg)  
图3 电弧电流元“AB”

$$
B _ { z } = \frac { \mu _ { 0 } I } { 4 \pi d _ { 0 } } \frac { b _ { 3 } } { b } ( \cos \theta _ { 1 } - \cos \theta _ { 2 } )
$$

式（2）～式（4）中， $d _ { 0 }$ 一定， $\begin{array} { l } { { \dot { \boldsymbol { \gamma } } _ { 1 } , } } \end{array} \boldsymbol { b } _ { 2 } , \boldsymbol { b } _ { 3 } , \boldsymbol { b }$ ，cos $\theta _ { 1 }$ ，cos $\theta _ { 2 }$ 为关于端点 $A$ ， $B$ 坐标的非线性表达式[1]。式（2）～式（4）可表示为

$$
\scriptstyle A x = b
$$

若求解电流 $\pmb { x } = [ I _ { 1 } , I _ { 2 } , \cdots , I _ { i } , \cdots , I _ { n } ]$ 的分布，首先需要确定各电流线节点的坐标。当电弧总电流值$I$ 已知时，可先假设各支线电流值一定，为 $I _ { i } = I / n$ ，$n$ 为电流线条数。通过智能优化方法搜索电弧位置即各电流线坐标，算子 $A$ 即确定。再通过解线性方程组反演 $x$ 。由于栅片等铁磁材料对 $B _ { x }$ 的扰动较小，且 $B _ { x }$ 相对于其他磁感强度分量的值较大，因此在电磁正演分析中，采样点测试采用分量 $B _ { x }$ 的分布。

# 3多种群遗传算法优化

式（5）可以转化为下面的优化问题，即

$$
\operatorname* { m i n } _ { A \in F } \left\| A x - b \right\|
$$

式（6）中，分析 $\operatorname* { m i n } _ { A \in F } \left\| A x - b \right\|$ 的描述，在可行域$F$ 搜索算子 $A$ 的优化过程涉及多参数及复杂运算表达式的这一特殊性，传统的非线性优化方法在解决这类问题时依赖对多变量求极值点的大量计算。采用启发式的随机搜索方法能够克服这一缺点，在这类方法中，遗传算法（GeneticAlgorithm，GA）是一类借鉴生物界进化规律（适者生存、优胜劣汰遗传机制）演化而来的随机化搜索方法，是一种具有并行机制的全局寻优方法。但标准遗传算法存在着早熟收敛问题，即某个体的适定度远超其他个体时，则种群将被该个体控制，群体进化停滞不前。为了提高算法求解的质量，在优化过程中采用了多

种群遗传算法（Multi-Population Genetic Algorithm,MPGA)。MPGA在GA的基础上做了以下改进[17,18]：

(1）多个种群协同进化。各个种群取不同的控制参数，在GA中，交叉算子决定了全局搜索能力，变异算子决定局部搜索能力，交叉概率和变异概率是常数。在MPGA中，不同种群的交叉概率 $P _ { \mathrm { ~ c ~ } }$ 和变异概率 $P _ { \mathrm { { m } } }$ 随机生成，各不相同，即

$$
\begin{array} { l } { \left\{ P _ { \mathrm { c } } = 0 . 7 + ( 0 . 9 - 0 . 7 ) \times r a n d ( N , 1 ) \right. } \\ { \left. \left[ P _ { \mathrm { m } } = 0 . 0 0 1 + ( 0 . 0 5 - 0 . 0 0 1 ) \times r a n d ( N , 1 ) \right. \right. } \end{array}
$$

(2）各种群通过移民算子将进化过程中各种群之间前一种群最优个体代替后一种群中的最差个体，实现各种群之间的信息交换。

(3）在进化的每一代，利用人工选择算子选出种群的最优个体存入精华种群。精华种群不进行选择、交叉、变异操作，只进行更新，以确保最优个体不被破坏和丢失。

MPGA的具体算法流程如图4所示， $t$ 为当前代数，初始化种群个数 $N = 1 0$ ，每个种群的个体数$M = 4 0$ ，最大进化代数 $T = 8 0 0$ ，采用二进制编码。由于电弧磁场反演问题的不适定性，可能导致各电流线的位置交叉。为此，需对算法变量施加约束。

![](images/1fbb65241c7d1f43fe8dd67995ed53afe26bd5f9cbfb6e5d94e9008b324bf13e.jpg)  
Fig.3The arc current unit $" \boldsymbol { A } \boldsymbol { B } "$ =   
图4多种群遗传算法流程Fig.4The flow chart of MPGA

通过引入罚函数，降低不可行解适应度以减小被选择概率，将约束问题转化为无约束求极值问题。

一般约束优化问题为

$$
\left\{ \begin{array} { c c } { \operatorname* { m i n } f ( \pmb { x } ) } & { \pmb { x } \in \pmb { R } ^ { n } } \\ { \mathrm { s . t . } h _ { i } ( \pmb { x } ) = 0 } & { i \in E = \{ 1 , \cdots , l \} } \\ { g _ { i } ( \pmb { x } ) \geqslant 0 } & { i \in I = \{ 1 , \cdots , m \} } \end{array} \right.
$$

可行域 $F$ 记作为

$$
F = \{ { \pmb x } \in R ^ { n } | h _ { i } ( { \pmb x } ) = 0 ( i \in E ) , g _ { i } ( { \pmb x } ) \geqslant 0 ( i \in I ) \}
$$

构造函数 $p ( { \pmb x } , \sigma ) = f ( { \pmb x } ) + \sigma \hat { p } ( { \pmb x } )$ ，其中 $f ( { \boldsymbol { x } } )$ 为原目标函数。 $\hat { p } ( \pmb { x } )$ 为罚函数，且

$$
\widehat { p } ( \pmb { x } ) = \sum _ { i = 1 } ^ { l } h _ { i } ^ { 2 } \left( \pmb { x } \right) + \sum _ { i = 1 } ^ { m } [ \operatorname* { m i n } \left\{ 0 , g _ { i } \left( \pmb { x } \right) \right\} ] ^ { 2 }
$$

其中， $\sigma = 1$ 为惩罚因子。

经过500代的优化过程，MPGA与GA的目标函数进化曲线如图5所示。优化各电流线节点坐标的相对误差曲线如图6所示。可以看出，MPGA能够有效克服GA的早熟收敛。MPGA优化各变量平均相对误差为 $2 . 4 4 \%$ ，GA的最大相对误差为 $3 . 9 2 \%$ 。并且MPGA以较快速度收敛到最优值0.0290，GA收敛到最优值0.0753，说明MPGA能够提高算法的精度。

![](images/6a7cdd42034dc63cafd8f693ddd911ca2f949544cf39667be19dec41cc1d3aad.jpg)  
图5目标函数进化过程

![](images/bf902dbec546a037fc9d7c6bdf13ce32c5140411c2062887c68407784ec15f39.jpg)  
Fig.5Evolution process of the objective function   
图6MPGA和GA优化相对误差曲线  
Fig.6The optimization relative error of MPGA and GA

# 4截断奇异值分解反演电弧电流

通过MPGA的智能优化过程可以确定式（5）中的算子 $A$ 。由于优化得到的算子和原始算子相比存在一定偏差，且电磁逆问题是病态问题，因此采用传统的解线性方程组的方法反演电流会导致误差放大。首先，为了反映问题的病态程度，采用离散Picard条件判断。对算子 $A$ 进行奇异值分解，即

$$
\pmb { A } = \sum _ { i = 1 } ^ { n } \sigma _ { i } \pmb { u } _ { i } \pmb { v } _ { i } ^ { \operatorname { T } }
$$

若傅里叶系数 $| \pmb { u } _ { i } ^ { \mathrm { ~ T ~ } } \pmb { b } |$ 相对于奇异值 $\sigma _ { i }$ 趋于零的速度更快，则方程满足离散Picard条件，可以通过正则化方法得到最佳逼近解。方程 $\scriptstyle A x = b$ 的离散Picard条件判定如图7所示。可以看出，傅里叶系数在后面部分出现波动，说明该处奇异值对应分量受扰动影响较大，需利用正则化方法将该段截断，以得到最优解。截断参数也称为正则化参数，通过参数选择策略求取。

![](images/68cf2ef9dceccb24d4a97b6540710e0a3497c053bfac30e76c432f0f1ba4c962.jpg)  
图7离散Picard 条件 Fig.7Discrete Picard condition

截断参数 $k$ 对于最终的解起着关键作用。当 $k$ 选择过小时，去噪处理过强，解过于平滑；当 $k$ 选择过大时，解包含了噪声影响的不稳定分量。在噪声水平未知的情况下，常用的选择截断参数的方法有L曲线法和GCV准则。L曲线法是通过绘制正则解的残差范数与解范数的对数坐标，即

$$
\scriptstyle { \left\{ \begin{array} { l l } { { \boldsymbol { \rho } } = \log \left\| { \boldsymbol { A } } _ { k } { \boldsymbol { x } } - { \boldsymbol { b } } \right\| } \\ { \eta = \log \left\| { \boldsymbol { x } } \right\| _ { 2 } } \end{array} \right. }
$$

曲率最大的点即对应截断参数。但文献[19]指出L曲线有时过于光滑，很难找出曲率最大的一点。

GCV准则通过定义下面的表达式，寻找其最小值对应的 $k$ 即为截断参数[20]，即

$$
G = \frac { \left\| A _ { k } \pmb { x } - \pmb { b } \right\| _ { 2 } ^ { 2 } } { \left[ t r a c e ( \pmb { I } - A A _ { k } ) \right] ^ { 2 } }
$$

式中， $\mathbf { \nabla } _ { A _ { k } }$ 为正则化算子；trace表示矩阵的迹。对于截断奇异值分解法， $\mathbf { \nabla } _ { A _ { k } }$ 就是将引起扰动的小奇异值直接用0代替。根据 $\mathbf { \nabla } _ { A _ { k } }$ 的广义逆 $\boldsymbol { A } _ { k } ^ { + }$ ，正则解的表达式为

$$
{ \pmb x } _ { k } = A _ { k } ^ { + } b = \sum _ { i = 1 } ^ { k } \frac { { \pmb u } _ { i } ^ { \operatorname { T } } { \pmb b } } { \sigma _ { i } } { \pmb \nu } _ { i }
$$

采用GCV准则选取截断参数如图8所示。求得截断参数 $k = 4$ 。将 $k$ 代入式（14）可解得反演电流分布如图9所示。

![](images/d45bb50f520c48e63a8cc8d80d831b24de000bb58234ed2726e6136d0d8e808c.jpg)  
图8GCV准则选取截断参数

![](images/c06791fd8e98dcdeed30f96aabee0704c72b830b34f2798a62e7444a44ba8d8c.jpg)  
Fig.8Selection of truncated parameter by GCV criterion   
图9反演电流分布  
Fig.9The inversed current distribution

为了说明算法的精度，对比最小二乘法求解 $A x =$ $\textbf { \textit { b } }$ 结果 $x _ { \mathrm { L S } }$ 。最小二乘法是一种常用的求解超定方程组的方法，其解表示为

$$
\pmb { x } _ { \mathrm { L S } } = \left( \pmb { A } ^ { \mathrm { T } } \pmb { A } \right) ^ { - 1 } \pmb { A } ^ { \mathrm { T } } \pmb { b }
$$

通过式（15）可知，当 $k$ 取 $A$ 的秩 $\operatorname { R a n k } ( A )$ 时，式（15）即为传统最小二乘法的解。但最小二乘法容易受问题的不适定性影响使得解的稳定性变差。由图9可知，最小二乘解 $\boldsymbol { x } _ { \mathrm { L S } }$ 远远偏离预设电流，而采用GCV准则选取正则化参数的截断奇异值分解法反演电流能够反映预设电流的分布趋势。电弧电流反演相对误差见下表。在表中，相对误差 $\delta _ { \mathrm { r } }$ 为

表电弧电流反演相对误差  
TabThe relative error of arc current inversion   

<html><body><table><tr><td>电流线标号</td><td>最小二乘法(%)</td><td>截断奇异值分解法(%)</td></tr><tr><td>1</td><td>8.01</td><td>1.14</td></tr><tr><td>2</td><td>28.99</td><td>2.77</td></tr><tr><td>3</td><td>30.85</td><td>3.28</td></tr><tr><td>4</td><td>39.83</td><td>6.56</td></tr><tr><td>5</td><td>31.89</td><td>6.01</td></tr></table></body></html>

$$
\delta _ { \mathrm { r } } = \frac { \biggl | x _ { \mathrm { r e c } } - x _ { \mathrm { r e f } } \biggr | } { x _ { \mathrm { r e f } } } { \times } 1 0 0 \%
$$

式中， $\scriptstyle x _ { \mathrm { r e c } }$ 为反演电流； $\boldsymbol { x } _ { \mathrm { r e f } }$ 为预设电流。可见相比于最小二乘法，截断奇异值分解对于电磁逆问题的病态性具有较好的抗噪能力，重建电流精度较高，证明了正则化方法处理电弧反演问题的有效性。

正则化方法反演电流的误差主要是由智能优化算法的预处理造成的。由于算子是病态的，即使微弱的偏差也会造成解远远偏离真实值，无法通过正则化方法求近似解。因此智能优化算法的结果对方程的不适定程度有较大影响。

# 5 结论

针对低压断路器电弧反演的不适定性，采用多电弧电流线表征变弧径电弧，利用电磁对应关系反演电弧，以简化计算复杂度。通过多种群遗传算法与截断奇异值分解相结合的手段对电弧位置与电流分布进行反演，利用GCV准则选择正则化参数。结果说明该方法对重构电弧电流这一类多变量不适定逆问题误差较小。正则化精度依赖于非线性智能优化结果的优劣。为了增加方法的可行性，降低栅片等非线性材料对反演结果的影响将是下一步工作

的重点。

# 参考文献

[1] 赵宏晨．基于电磁特性分析的开关电弧反演研究 [D]．沈阳：沈阳工业大学，2015.   
[2] 冷雪，刘莉，刘晓明，等．高压 ${ \mathrm { S F } } _ { 6 }$ 断路器不同开 断条件下混沌特性分析[J]．电气工程学报，2015, 10(11): 27-32. Leng Xue,Liu Li, Liu Xiaoming, et al. Chaotic characteristics analysis of high voltage ${ \mathrm { S F } } _ { 6 }$ circuit breaker under different breaking conditions[J]. Journal of Electrical Engineering,2015,10(11): 27- 32.   
[3] 王伟宗，吴翊，荣命哲，等．空气开关电弧仿真技 术及其应用的研究[J]．低压电器，2010(5)：7-11. Wang Weizong,Wu Yi, Rong Mingzhe, et al. Research on the simulation technology and application of the air switch arc[J]. Low Voltage Electrical Apparatus,2010(5): 7-11.   
[4] Yang Fei, Rong Mingzhe,Wu Yi,et al. Numerical analysis of the influence of spliter-plate erosion on an air arc in the quenching chamber of a low-voltage circuit breaker[J]. Journal of Physics D: Applied Physics.2010,43: 1-12.   
[5] 蔡彬，陈德桂，吴锐，等．开关柜内部故障电弧 的在线检测与保护装置[J]．电工技术学报，2005, 20(10): 83-87. Cai Bin, Chen Degui, Wu Rui, et al. Online detecting and protection system for internal faults arc in swithgear[J]. Transactions of China Electrotechnical Society,2005,20(10): 83-87.   
[6] 丁心志，刘柱揆，严跃，等．电弧光光谱成分特性 及其应用分析[J]．电气工程学报，2015，10(5)： 75-81. Ding Xinzhi, Liu Zhukui, Yan Yue, et al. Analysis of characteristics and application for arc spectral components[J]. Journal of Electrical Engineering, 2015, 10(5): 75-81.   
[7] Brdys C, Toumazet JP, Velleaud G,et al. Study of the low-voltage electric breaking arc restrike by means of an inverse method[J]. IEEE Transactions on Plasma Science,1999,27(2): 595-603.   
[8] Debellut E, Gary F, Cajal D, et al. Study of re-strike phenomenon in a low-voltage breaking device by means of the magnetic camera[J]. Journal of Physics D: Applied Physics,2001,34: 1665-1674.   
[9] Brdys C, Toumazet JP, Laurent A, et al. Optical and magnetic diagnostics of the electric arc dynamics in a low voltage circuit breaker[J].Measuremen Science and Technology,2002,13:1146-1153.   
[10] Toumazet J P, Brdys C,Laurent A, et al. Combined use of an inverse method and a voltage measurement: estimation of the arc column volume and its variations[J]. Measurement Science and Technology, 2005,16: 1525-1533.   
[11]张鹏飞，张国钢，杨博宇，等．空气开关电弧电 流密度分布的智能反演方法研究[J]．中国电机工 程学报，2013，33(33)：160-168. Zhang Guogang, Zhang Pengfei, Yang Boyu, et al. Investigations on intelligent inversion methods of current density distribution of electrical arc in air[J]. Proceedings of the CSEE,2013,33(33): 160-168.   
[12]Zhang Pengfei, Zhang Guogang, Dong Jinlong,et al. Non-intrusive magneto-optic detecting system for investigations of air switching arcs[J]. Plasma Science and Technology,2014,16(7): 661-668.   
[13]Luca G, Luca D R, Daniele P, et al. Current identification in vacuum circuit breakers by inverting magnetic field data[C]. International Conference on Electric Power Equipment-Switching Technology, Xi'an, China, 2011: 65-68.   
[14]Luca G, Daniele P, Luca D R. Current density reconstruction in vacuum arcs by inverting magnetic field data[J]. IEEE Transaction on Magnetics, 2012, 48(8): 2324-2333.   
[15]Dong Jinlong, Zhang Guogang, Zhang Zhiqiang, et al.Inverse problem solution and regularization parameter selection for current distribution reconstruction in switching arcs by inverting magnetic fields[J]. Mathematical Problems in Engineering,2018: 1-11.   
[16]赵宏晨，刘晓明，李龙女．采用遗传算法的低压开 关电弧反演[J]．高压电器，2017，53(4)：25-30. Zhao Hongchen,Liu Xiaoming,Li Longnv. Arc inversion with genetic algorithm for low voltage switch[J]. High Voltage Apparatus, 2017, 53(4): 25- 30. 37(21): 52-59.   
[3] 汪际峰，沈国荣．大电网调度智能化的若干关键 技术问题[J]．电力系统自动化，2012，36(1)： 10-16. Wang Jifeng,Shen Guorong. Some key technical issues on intelligent power dispatching of bulk power grid[J].Automation of Electric Power Systems,2012,36(1):10-16.   
[4] 杨清波，李立新，李宇佳，等．智能电网调度控 制系统试验验证技术[J]．电力系统自动化，2015， 39(1):194-199. Yang Qingbo,Li Lixin,Li Yujia,et al. Test and verification technology for smart grid dispatching and control systems[J].Automation of Electric Power Systems,2015,39(1):194-199.   
[5] 陆承宇，阮黎翔，杜奇伟，等．智能变电站远动信 息快速校核方法[J]．电力系统保护与控制，2015, 43(11):128-133. Lu Chengyu,Ruan Lixiang,Du Qiwei,et al.A new method for quickly verifying the remote information of smart substation[J].Power System Protection and Control, 2015,43(11): 128-133.   
[6] 纪陵，李忠明，蒋衍君，等．智能变电站二次系统 仿真测试和集成调试新模式的探索和研究[J]．电 力系统保护与控制，2014，42(22)：119-123. Ji Ling,Li Zhongming,Jiang Yanjun,et al. Exploration and research of smart substation secondary system simulation testing and integration testing new mode[J].Power System Protection and Control, 2014,42(22): 119-123.   
[7] 李瑞生，李燕斌，周逢权．智能变电站功能架 构及设计原则[J]．电力系统保护与控制，2010, 38(17): 24-27. Li Ruisheng,Li Yanbin,Zhou Fengquan.The functional frame and design principles of smart substation[J].Power System Protection and Control, 2010,38(17):24-27.   
[8] 笃竣，祁忠．基于IEC61850的变电站新型远动网 关机[J]．电力自动化设备，2011，31(2)：113-115. Du Jun,Qi Zhong.Telecontrol gateway of substation based on IEC 61850[J].Electric Power Automation Equipment, 2011,31(2):113-115.

# （上接第19页）

[17] 林阳，赵欢，丁汉．基于多种群遗传算法的一般 机器人逆运动学求解[J]．机械工程学报，2017， 53(3):1-8. Lin Yang,Zhao Huan,Ding Han,et al.Solution of inverse kinematics for general robot manipulators based on multiple population genetic algorithm[J]. Journal of Mechanical Engineering,2017,53(3): 1-8.   
[18] 叶满园，周琪琦，蔡鸿，等．基于多种群遗传算 法的多电平逆变器多波段SHEPWM技术[J]．电 工技术学报，2015，30(16)：111-119. Ye Manyuan, Zhou Qiqi, Cai Hong,et al. Multiple population genetic algorithm based on multiband SHEPWM control technology for multi-level inverter[J].Transactions of China Electrotechnical Society,2015,30(16): 111-119.   
[19] Hansen PC,O’Leary DP. The use of the L-curve in the regularization of discrete ill-posed problems[J]. SIAM Journal of Scientific Computing,1993,14(6): 1487-1503.   
[20] 马超，华宏星．一种基于新的正则化技术的冲击载 荷识别法[J]．振动与冲击，2015，34(12)：164- 168. Ma Chao,Hua Hongxing.Impact force identification based on improved regularization technique[J]. Journal of Vibration and Shock,2015,34(12):164- 168.