# 基于改进QPSO算法的电动汽车模糊控制器参数优化

袁小平1′，金鹏1，周国鹏²

(1．中国矿业大学 信息与控制工程学院，江苏 徐州 221008;2.湖北科技学院 工程技术研究院，湖北 咸宁 437100)

摘要：目前电动汽车常以直流无刷电机(BLDCM)作为驱动器，但BLDCM调速控制系统中模糊控制器的量化因子和比例因子采用传统方法自调节能力弱，针对该问题提出一种改进QPSO 算法(AMF-QPSO)实现对量化因子和比例因子的自适应调节。AMF-QPSO 算法以收缩一扩张系数(contraction expansion，CE)控制方式为研究重点，提出粒子活性概念，并以其作为反馈量，实现动态自适应调节CE系数。同时，为防止种群高度聚集，采用精英群体随机交叉学习机制，对部分活性低的精英粒子进行扰动，增强种群后期多样性。最后，通过LabVIEW实验平台，以具体案例验证 AMF-QPSO 算法性能。实验结果表明，AMF-QPSO优化的模糊PID 控制器具有比标准模糊PID控制器和QPSO优化的模糊PID 控制器更好的控制性和自适应性。

关键词：电动汽车；直流无刷电机；模糊控制器；量子行为粒子群算法；收缩一扩张系数 中图分类号：TP301． doi: 10.3969/j.issn.1001-3695.2018.06.0395

# Parameter optimization of fuzzy controller for electric vehicle based on improved QPSO algorithm

Yuan Xiaopingl†, Jin Peng1, Zhou Guopeng2 (1.SchoolofInformation&Electric Engineering,China UniversityofMining&Technology,Xuzhou Jiangsu21008,China; 2.InstituteofEngineering&Technology HubeiUniversityofScience&Technology,Xianning Hubei437100,China)

Abstract:At present,electric vehiclesoftenuseDCbrushless motor(BLDCM)as the driver,but the traditional method is diffcult to design quantization factor and proportion factor of fuzzy controler in the BLDCM speed control system.An improved QPSOalgorithm(AMF-QPSO)is proposed for theon-line tuningofthequantizationfactor and proportionfactor.The AMF-QPSO algorithm takes thecontraction-expansioncoeficient (CE)control method as the research focus,proposes the particleactivityconcept,anduses itasthe feedback quantitytorealizethe dynamic adaptive adjustment CEcoefficient.Atthe same time,inorder topreventthe highaggregationofthepopulation,theelite grouprandomcrosslearing mechanismis used to disturb someoftheeliteparticles withlowactivityand enhance the diversityofthepopulation inthelaterperiod.Finally, through theLabVIEW experimental platform,the performanceof the AMF-QPSOalgorithm is verifiedbyaspecificcase.The experimentalresults showthatthe fuzzyPIDcontroler optimized byAMF-QPSO has better control and adaptability than the standard fuzzy PID controller and the fuzzy PID controller optimized by QPSO.

Key Words: electric vehicle; brushlessDC motor;fuzzycontroller;quantum-behaved particle swarm optimization; contractionexpansion

# 0 引言

近些年，随着新材料、先进制造、电力电子等技术的发展，涌现出了一批性能优越的新型电机。无刷直流电机(brushlessdirectcurrentmotor,BLDCM)作为新型电机典型代表，由于损耗小、功率密度高、过载能力强、噪声小、可控性强等一系列优势，受到了伺服控制、交通运输、物料输送、工业自动化等领域人员的青睐[1,2]。在交通运输领域，新能源技术的推广以及绿色崛起战略的实施，以BLDCM为驱动器的电动汽车日益普及。然而电动汽车调速控制系统具有非线性强、变量多、耦合程度高、控制器参数难整定等特性，提高系统可控性和自适应性，优化参数整定方式已成为进一步推广电动汽车的重要手段[3]。

模糊PID控制器作为先进控制器典型代表，运用模糊数学理论，将高等智能生物模糊语言转换为机器可认知的程序语言，算法实现机制类似于人类思维模式，可在被控对象非完全可知条件下进行控制，适用于电动汽车调速控制系统设计与参数优化问题。

但在实际工业应用中，模糊PID控制器参数缺乏在线调整能力，造成系统控制精度不高、抗干扰不强。随着智能算法的发展，将智能算法应用于模糊控制器参数整定已成为研究热点[4.5]。2004 年，Sun 等人[6受量子空间中粒子启发，提出了QPSO算法。量子空间中每个粒子位置相当于一个可行解，其位置坐标由波函数决定，且状态遵循叠加原理，具有很强随机性，智能化程度高。

标准QPSO算法尽管有许多优点，但依然存在不足，其中，收缩—扩张系数(contraction-expansion，CE) $\alpha$ 是除种群规模、粒子维度以及最大迭代次数外，唯一需人工设定的控制参数，其控制策略对算法性能影响大[7]。文献[8]证明CE系数必须满足 $\alpha < 1 . 7 8 1$ 才能使粒子可靠收敛，且比较了固定系数策略和非线性递减策略优缺点。文献[9]提出了动态非线性递减CE系数控制策略，根据不同优化问题特性采用凹凸性不同控制曲线。但无论是固定值、线性递减，还是非线性递减CE系数控制策略，均属无反馈控制策略，系数值及控制曲线由仿真实验或经验公式求得。这类系数控制策略最大不足表现在自调节能力弱，算法只能按照设定好的调节方式调节CE系数值，未能根据粒子搜索阶段的转变而调整系数控制方式。鉴于此，研究人员提出了具有不同反馈机制自适应系数控制策略。文献[10]利用粒子距全局最优点的距离作为CE 系数调控依据。文献[11]提出了进化速度因子和聚集度因子的概念，用于在线修正粒子CE系数值。

受上述文献启发，本文在探究CE系数与势阱长度关系基础上，提出粒子活性概念，以势阱长度相对变化率作为粒子活性度量标准，并以粒子活性作为反馈量，实现自适应调节CE系数；与此同时，为提高收敛精度，防止粒子陷入局部最优，提出精英群体随机交叉学习机制，使得活性低的精英粒子有机会与种群中其他粒子交换维度信息，跳出局部最优，搜寻到全局范围更优解。精英群体随机交叉学习机制既保证了种群收敛速度，又在一定程度上提高了种群后期多样性。最后，针对电动汽车调速控制系统中模糊PID控制器的量化因子和比例因子在线调节能力弱的问题，应用改进QPSO 算法(adaptive mutationQPSO algorithmbased on feedback mechanism，AMF-QPSO)进行优化设计。为验证算法性能，在分析实际应用场景基础上，通过LabVIEW实验平台，以具体控制案例验证AMF-QPSO算法性能，与基本模糊PID及标准QPSO算法优化后的模糊PID 控制器进行性能对比，实验结果表明改进后的控制器具有更好的控制性和自适应性。

# 1 量子行为粒子群算法

QPSO 算法是在PSO 算法基础上提出的一种群智能算法，该算法摆脱传统速度-位移轨道模型限制[12I，采用蒙特卡罗算法确定粒子更新后位置，算法智能化程度更高。其进化方程如式(1)所示。

$$
X ( t + 1 ) = p _ { i , j } ( t ) \pm \frac { L _ { i , j } ( t ) } { 2 } \mathrm { l n } ( \frac { 1 } { u ( t ) } ) , u ( t ) \in U ( 0 , 1 )
$$

其中： $p _ { i , j } ( t )$ 为局部吸引子，决定粒子寻优方向； $L _ { i , j } ( t )$ 为势阱特征长度，其大小直接制约粒子搜索范围； $u ( t )$ 为在(0.1)上的随机分布。Clerc 等人[13]对PSO算法中粒子收敛行为研究表明，要保证算法收敛，必须使每个粒子 $i$ 均收敛到各自局部吸引子$p _ { i , j }$ 点，其中吸引子坐标如式(2)所示。

$$
p _ { i , j } ( t ) = \frac { c _ { 1 } r _ { 1 , j } ( t ) P _ { i , j } ( t ) + c _ { 2 } r _ { 2 , j } ( t ) G _ { j } ( t ) } { c _ { 1 } r _ { 1 , j } ( t ) + c _ { 2 } r _ { 2 , j } ( t ) } , 1 \leq j \leq N
$$

或者

$$
\begin{array} { c } { { p _ { i , j } ( t ) = \varphi _ { i , j } ( t ) P _ { i , j } ( t ) + \left[ 1 - \varphi _ { i , j } ( t ) \right] G _ { j } ( t ) , 1 \leq j \leq N } } \\ { { \varphi _ { i , j } ( t ) = \displaystyle \frac { c _ { 1 } r _ { 1 , j } ( t ) } { c _ { 1 } r _ { 1 , j } ( t ) + c _ { 2 } r _ { 2 , j } ( t ) } } } \end{array}
$$

其中： $c _ { 1 }$ 和 $c _ { 2 }$ 分别为粒子局部学习因子和全局学习因子； $r _ { 1 , j } ( t )$ 和 $r _ { 2 , j } ( t )$ 为(0.1)上的随机分布； $P _ { i , j } ( t )$ 为粒子 $i$ 第 $j$ 维的局部最优位置； $G _ { j } ( t )$ 为粒子 $i$ 第 $j$ 维的全局最优位置。

要保证粒子收敛至各自吸引子，则必须满足

$$
\operatorname* { l i m } _ { \ t \to \infty } L _ { i , j } ( t ) = 0
$$

因此，如何控制 $L _ { i , j } ( t )$ 成为确保算法收敛以及影响算法性能的关键。典型 ${ L } _ { i , j } ( t )$ 控制方式为利用粒子距群体平均最优位置的距离进行调控，记种群平均最优位置坐标为 $C ( t )$ ，其坐标可用式(5)表示。

$$
\begin{array} { l } { \displaystyle { C ( t ) = ( C _ { 1 } ( t ) , C _ { 2 } ( t ) , \cdots C _ { D } ( t ) ) = \frac { 1 } { N } \sum _ { i = 1 } ^ { N } P _ { i } ( t ) } } \\ { \displaystyle { = \left( \frac { 1 } { N } \sum _ { i = 1 } ^ { N } P _ { i , 1 } ( t ) , \frac { 1 } { N } \sum _ { i = 1 } ^ { N } P _ { i , 2 } ( t ) , \cdots , \frac { 1 } { N } \sum _ { i = 1 } ^ { N } P _ { i , D } ( t ) \right) } } \end{array}
$$

其中： $D$ 为粒子维度； $N$ 为种群规模。此时，粒子势阱长度可用(6)式表示。

$$
L _ { i , j } ( t ) = 2 \cdot \alpha \cdot \left| C _ { \mathrm { j } } ( t ) - X _ { i , j } ( t ) \right|
$$

其中： $\alpha$ 即为CE系数。将式(6)代入式(1)，得最终进化方程如(7)式所示。

$$
X _ { i , j } ( t + 1 ) = p _ { i , j } ( t ) \pm \alpha \Big | C _ { j } ( t ) - X _ { i , j } ( t ) \Big | \cdot \ln ( \frac { 1 } { u _ { i , j } ( t ) } )
$$

# 2 基于反馈机制的自适应变异QPSO算法

# 2.1CE系数与势阱长度之间 $\boldsymbol { L }$ 的关系研究

由式(6)可知，势阱长度 $\boldsymbol { L }$ 调节过程中CE系数 $\alpha$ 起着决定性作用， $\alpha$ 取值不同，最直接的效果是增大或者削减粒子搜索空间。当 $\alpha$ 取较大值时，势阱长度 $\textbf { \em L }$ 相对较大，粒子具有较强全局搜索性能，但当 $\alpha$ 过大时，会造成种群发散；当 $\alpha$ 取较小值，势阱长度 $\textbf { \em L }$ 相对较小，粒子具有较强局部搜索性能，但当$\alpha$ 过小时，粒子将失去搜索性能，种群进化处于停滞状态。理想的CE调控方式为前期大，使粒子具有较强全局搜索能力；后期小，使粒子具有较强局部搜索能力。

因此，在保证算法收敛前提下，确定势阱长度 $\textbf { \em L }$ 控制策略关键在于选择CE系数 $\alpha$ 的控制方式，故研究 $\alpha$ 对于势阱长度$\boldsymbol { L }$ 的影响，探究两者间的关系对于算法性能改进研究具有很好指导作用。为便于分析，对一维情况下的进化公式(7)进行化简，将 $p$ 点和C均固定在原点，令粒子初始位置 $X ( 0 ) = 1$ ，则简化后的进化公式如(8)所示。

$$
X _ { i } ( t + 1 ) = \alpha { \left| X _ { i } ( t ) \right| } \cdot \ln ( \frac { 1 } { u _ { i } ( t ) } )
$$

由(8)式可知，要保证算法收敛，即粒子收敛至 $p$ 点(原点)，则此时 $\textbf { \em L }$ 需满足

$$
\operatorname* { l i m } _ { \ t  \infty } L = \operatorname* { l i m } _ { \ t  \infty } \alpha \big | X _ { i } ( t ) \big | = 0
$$

由式(9)可知，算法是否能可靠收敛可转换为观察 $\boldsymbol { L }$ 是否收敛。因此，根据式(8)进行随机模拟实验。图1给出了 $\alpha$ 取不同值时，势阱长度 $\textbf { \em L }$ 的变化情况。其中横坐标为迭代代数 $t$ ，纵坐标为势阱长度 $\textbf { \em L }$ 。为更加清晰观察两者间关系，取以10为底的对数值表示，即 $\log ( L )$ 。

![](images/0a30b1e7083372dc0b60039357222f484cf32a34cf2087200f0ed390fe7e45ae.jpg)  
图1CE系数 $\alpha$ 与势阱长度 $L$ 的关系

表1记录了 $\alpha$ 取不同值时， $\textbf { \em L }$ 收敛时的最大迭代次数 $T$ 或者 $\boldsymbol { L }$ 不收敛时的最大迭代次数。

表1CE系数 $\alpha$ 及相应迭代代数  

<html><body><table><tr><td>α</td><td>0.3</td><td>0.6</td><td>0.9</td><td>1.2</td><td>1.5</td><td>1.77</td><td>1.79</td><td>2.0</td></tr><tr><td>T</td><td>500</td><td>800</td><td>1200</td><td>2000</td><td>6000</td><td>10000</td><td>20000</td><td>20000</td></tr></table></body></html>

由图1和表1可知，当 $\alpha < 1 . 7 7$ 时，随种群更新，势阱长度逐渐减小，直至为零，表明这一参数范围内势阱一直呈现收缩趋势，算法收敛；当 $\alpha$ 小于但接近1.78时，势阱长度收敛过程出现波动，且需要长时间的种群更新才能收敛至零；当 $\alpha { \geq } 1 . 7 9$ 时，势阱长度收敛过程波动更为剧烈，而且经20000次迭代后，势阱长度仍然很难收敛至零，说明粒子难以收敛至 $p$ 点，此时算法不收敛。上述实验结果论证了CE系数与势阱长度 $\boldsymbol { L }$ 之间的高度关联性，且当 $\alpha$ 取不同值时，势阱长度 $\boldsymbol { L }$ 的收敛速度与收敛精度均存在区别，间接造成算法收敛速度和收敛精度的不同。

# 2.2具有反馈机制的CE系数自适应控制策略

由2.1节仿真结果可知，CE系数只有在合适范围内取值，才能使算法收敛，且对于CE系数的调控实质上是对于势阱长度 $\textbf { \em L }$ 的控制。QPSO算法中， $\textbf { \em L }$ 决定粒子搜索范围， $\textbf { \em L }$ 的相对变化率则反映了粒子搜索范围变化情况。根据式(1)可得，若种群聚集度高，粒子较为集中，此时势阱相对变化率将很小或者不再变化，说明粒子已收敛至吸引子，更新基本处于停滞状态；若种群聚集程度低，粒子较为分散，此时粒子势阱长度相对变化率较大，说明粒子位置更新处于活跃状态，粒子还在大范围进行寻优。因此，可用势阱长度相对变化率来表示粒子活性。粒子活性因子 $s _ { i , j }$ 定义如式(10)所示。

$$
s _ { i , j } ( t ) = \frac { \left| L _ { i , j } ( t ) - L _ { i , j } ( t - 3 ) \right| } { \left| L _ { i , j } ( t - 3 ) \right| }
$$

其中： $L _ { i , j } ( t )$ 为粒子 $i$ 第 $j$ 维更新至 $t$ 代时的势阱长度； $L _ { i , j } ( t - 3 )$ 为粒子 $i$ 第 $j$ 维更新至t-3代时的势阱长度； $s _ { i , j } ( t )$ 为粒子 $i$ 第 $j$ 维更新至 $t$ 时的活性因子。由于算法收敛时，势阱呈现收缩趋势势阱长度逐代递减，粒子向全局最优位置移动，即$L _ { i , j } ( t ) < L _ { i , j } ( t - 3 )$ ，所以 $s _ { i , j } ( t ) \in [ 0 , 1 ]$ 。

经理论分析可知， $s _ { i , j }$ 越大，说明势阱长度3代内收缩剧烈，说明粒子活性越强，粒子向全局最优位置移动速度越快； $s _ { i , j }$ 越小，说明势阱长度3代内收缩缓慢，说明粒子活性越弱，粒子向全局最优位置移动速度慢。

2.1节探讨了CE系数与势阱长度 $\textbf { \em L }$ 之间的关系，仿真结果表明CE系数直接影响 $\boldsymbol { L }$ 的取值，制约着粒子搜索范围。而且分析可得，固定系数、线性或非线性递减以及部分自适应控制策略都是一种无反馈的系数控制策略，并未考虑CE系数与被控量 $\textbf { \em L }$ 之间的关系。基于这一发现，本文提出一种具有反馈机制的CE系数控制策略，以 $\textbf { \em L }$ 的相对变化率，即粒子活性因子$s _ { i , j }$ 作为反馈量，构建闭环控制模型，实现 $\alpha _ { i , j }$ 的动态调整。其定义如(11)式所示。

$$
\alpha _ { i , j } ( t ) = \alpha _ { 0 } + ( 1 - s _ { i , j } ( t ) ) \cdot \lambda
$$

其中： $\alpha _ { 0 }$ 为CE系数初值； $\lambda$ 为(0.1)中随机数； $s _ { i , j } ( t )$ 为粒子 $i$ 活性因子。 $\alpha _ { i , j }$ 与 $s _ { i , j }$ 成负相关。当 $s _ { i , j }$ 越小，代表粒子搜索能力

越弱，此时应适当增大 $\alpha _ { i , j }$ ，维持种群多样性；当 $s _ { i , j }$ 越大，代表粒子搜索能力越强，此时 $\alpha _ { i , j }$ 适当取较小值，可防止粒子搜索步长过大，越过最优位置。

将式(11)代入式(7)，可得最终进化公式如式(12)所示。

$$
X _ { i , j } ( t + 1 ) = p _ { i , j } ( t ) \pm ( \alpha _ { 0 } + ( 1 - s _ { i , j } ( t ) ) \cdot \lambda ) \cdot \Big | C _ { j } ( t ) - X _ { i , j } ( t ) \Big | \cdot \ln ( \frac { 1 } { u _ { i , j } ( t ) } )
$$

# 2.3精英粒子的随机交叉学习

以上CE系数控制策略虽在一定程度上改善了QPSO算法搜索速度和收敛精度，但随迭代进行，种群进化后期多样性不可避免有所损失，使得粒子易早熟收敛。为解决该问题，本节提出精英群体的随机交叉学习策略，使得精英群体中粒子活性低于设定阈值 $s _ { l o w }$ 时，让粒子有能力偏离原位置而进入其他空间搜索，使其可能寻找到更优位置。其中，随机交叉学习的定义如下：

定义1随机交叉学习。维度为 $D$ 的搜索空间中，令$X = ( x _ { 1 } , ~ x _ { 2 } , \cdots , ~ x _ { k } , \cdots , ~ x _ { _ D } )$ 为精英粒子位置， $\ v { x } _ { k } ^ { \prime }$ 为 $D$ 维中随机选择的某一维分量，则 $\boldsymbol { \cal X }$ 按概率 $p _ { { } _ { m } }$ 进行随机交叉学习后的新位置坐标为 $X _ { _ { p } } = ( x _ { _ { 1 p } } , ~ x _ { _ { 2 p } } , \ldots , ~ x _ { _ { k p } } , \ldots , ~ x _ { _ { D p } } )$ ，其定义如下：

$$
x _ { k p } = \left\{ \begin{array} { l l l } { x _ { k } ^ { \prime } } & { , } & { r a n d \ > \ p _ { m } } \\ & { x _ { k } } & { , } & { \not \equiv \not \equiv \not \{ \mathrm { t } \} } \end{array} \right.
$$

为保证算法收敛， $p _ { { \mathfrak { m } } }$ 采用自适应线性递减策略，如式(14)所示。

$$
p _ { m } = p _ { \mathrm { m a x } } - ( p _ { \mathrm { m a x } } - p _ { \mathrm { m i n } } ) \cdot t / G _ { \mathrm { m a x } }
$$

其中： $p _ { \operatorname* { m a x } }$ 和 $p _ { \operatorname* { m i n } }$ 分别为最大交叉概率和最小交叉概率； $\textit { t }$ 为当前代数； $G _ { \mathrm { m a x } }$ 为最大迭代次数。

综上所述，精英群体的随机交叉学习伪代码见算法1所示。 算法1精英群体随机交叉学习

1: 计算粒子适应度值，对粒子进行降序排序；  
2: 选取适应度值较优的前 $1 0 \%$ 个粒子组成精英群体;  
3: 计算精英群体中每个粒子活性 $s _ { i , j }$   
4: if $s _ { i , j }$ < $s _ { l o w }$   
5: 按照交叉概率 $p _ { { } _ { m } }$ 产生随机维;  
并执行随机交叉学习，如式(13);  
6: end if

# 2.4基于反馈机制的自适应变异QPSO算法

按照上述讨论，具有反馈机制的自适应变异QPSO算法(AMF-QPSO)具体执行流程如下：a)初始化参数，包括种群规模 $N .$ 、粒子维度 $D$ 、最大迭代数$G _ { \mathrm { m a x } }$ 、粒子搜索空间、初始化空间等;b)在问题空间以随机原则初始化粒子位置；c)按式(5)计算粒子平均最优位置;d)计算粒子当前适应度值，式按(10)计算每个粒子活性因子，更新局部最优位置和全局最优位置；e)选择适应度值最优的前 $10 \%$ 的个体作为精英群体，按式(14)计管精带粒子交概兹”·

f)判断精英粒子活性，若低于设定下限阈值 $s _ { l o w }$ ，则按式(14)

执行随机交叉学习；

g)根据式(12)更新每个粒子位置;   
h)重复步骤 $\mathbf { b } ) { \sim } \mathbf { g } )$ ，直至满足一定的循环结束条件。

# 3 算法性能分析

# 3.1参数设置

为验证AMF-QPSO 算法性能，利用表2中六个典型标准测试函数进行实验。将AMF-QPSO算法分别与固定系数、线性递减、非线性递减三类典型CE系数控制策略进行对比分析。各对比算法的CE系数控制策略按如下设置：固定系数控制策略中 $\alpha = 0 . 8$ ；线性递减CE系数控制策略中初值取 $\alpha _ { 0 } = 1 . 0$ ，终值 $\alpha _ { 1 } = 0 . 5$ ；非线性递减 CE 系数控制策略参考文献[9]，其中$\alpha _ { i n i t a l } = 1 . 6$ ， $n { = } 1 . 0$ (凹函数)；本文提出的 AMF-QPSO 算法中，经大量实验验证，CE 系数初值 $\alpha _ { 0 } = 0 . 8$ ， $\lambda = 0 . 5$ ，交叉概率$p _ { \operatorname* { m a x } } = 1 . 0$ ， $p _ { \mathrm { m i n } } = 0 . 4$ 时，算法性能最佳。

表2标准测试函数  

<html><body><table><tr><td>函数名</td><td>初始化范围</td><td>搜索范围</td></tr><tr><td>Sphere( fi )</td><td>[-100,50]</td><td>[-100,100]</td></tr><tr><td>Rosenbrock(f2)</td><td>[-30,15]</td><td>[-30,30]°</td></tr><tr><td>Rastrigin( fs )</td><td>[-5.12,2.56]</td><td>[-5.12,5.12]b</td></tr><tr><td>Griewank( f4)</td><td>[-600,300]D</td><td>[-600,600]</td></tr><tr><td>Ackley(fs)</td><td>[-32,16]D</td><td>[-32,32]D</td></tr><tr><td>Schwefel( fs)</td><td>[250,500]</td><td>[-500,500]</td></tr></table></body></html>

# 3.2结果分析

为全面论述算法性能优势，采用粒子规模 $N$ 分别为20、50、80，维数 $D$ 分别为10、30、50维，最大迭代代数 $\mathrm { G } _ { \mathrm { m a x } }$ 分别为1000、1500、2000代的种群进行实验。每种情况单独运行100次，记录结果并计算最优解的平均值。各测试函数结果详见表3所示。

由表3可得，绝大多数情况下，CE系数自适应变异控制策略所取得的收敛精度均优于其他三种系数控制策略，说明了具有反馈机制的自适应变异CE系数控制策略的合理性与有效性。为形象地说明算法性能优势，以典型单峰 Sphere 函数和多峰Rastrigin函数来观察固定系数、线性递减、非线性递减以及本文提出的自适应变异四种策略下适应度收敛曲线和CE系数的变化趋势，如图2和3所示。

由图2可得，自适应CE系数控制策略在整个收敛过程呈现为一个凸函数，CE系数前期较大，粒子具有更好全局搜索性能；后期较小，粒子具有更好的局部搜索性能，自适应控制策略能根据粒子不同的搜索阶段来调整得到一个合适的值，使得算法具有更快搜索速度和更好精度。此外，凸函数曲率针对不同优化问题而不同，对于Sphere 这类单峰优化问题，因为全局范围内仅有一个最优值，优化问题简单，势阱会很快收敛，所以这类凸函数曲率较大。

表3不同控制策略的实验结果  

<html><body><table><tr><td rowspan="2">函数</td><td rowspan="2">N</td><td rowspan="2">D</td><td rowspan="2">Gmax</td><td colspan="4">控制策略</td></tr><tr><td>固定</td><td>线性</td><td>非线性</td><td>自适应</td></tr><tr><td></td><td>20</td><td>10</td><td>1000</td><td>7.54E-67</td><td>3.76E-41</td><td>1.64E-27</td><td>4.71E-86</td></tr><tr><td>f</td><td>50</td><td>30</td><td>1500</td><td>2.24E-36</td><td>3.14E-24</td><td>7.68E-20</td><td>8.37E-72</td></tr><tr><td></td><td>80</td><td>50</td><td>2000</td><td>2.86E-21</td><td>1.20E-19</td><td>3.97E-13</td><td>8.09E-68</td></tr><tr><td></td><td>20</td><td>10</td><td>1000</td><td>6.29E+00</td><td>5.49E+00</td><td>5.28E+00</td><td>2.25E+00</td></tr><tr><td>f</td><td>50</td><td>30</td><td>1500</td><td>2.27E+01</td><td>2.50E+01</td><td>2.01E+01</td><td>6.41E+00</td></tr><tr><td></td><td>80</td><td>50</td><td>2000</td><td>5.35E+01</td><td>4.47E+01</td><td>4.16E+01</td><td>3.87E+01</td></tr><tr><td></td><td>20</td><td>10</td><td>1000</td><td>6.60E+00</td><td>5.41E+00</td><td>9.32E+00</td><td>2.98E+00</td></tr><tr><td>f</td><td>50</td><td>30</td><td>1500</td><td>6.21E+01</td><td>2.08E+01</td><td>5.03E+01</td><td>1.69E+00</td></tr><tr><td></td><td>80</td><td>50</td><td>2000</td><td>1.89E+02</td><td>4.47E+01</td><td>6.61E+01</td><td>1.48E+01</td></tr><tr><td></td><td>20</td><td>10</td><td>1000</td><td>9.77E-02</td><td>7.79E-02</td><td>1.42E-02</td><td>9.93E-04</td></tr><tr><td>f</td><td>50</td><td>30</td><td>1500</td><td>2.13E-02</td><td>1.20E-02</td><td>7.05E-03</td><td>2.05E-03</td></tr><tr><td></td><td>80</td><td>50</td><td>2000</td><td>6.67E-03</td><td>5.51E-03</td><td>3.35E-03</td><td>1.11E-03</td></tr><tr><td></td><td>20</td><td>10</td><td>1000</td><td>2.66E-15</td><td>2.66E-15</td><td>2.45E-15</td><td>1.26E-18</td></tr><tr><td>f5</td><td>50</td><td>30</td><td>1500</td><td>7.14E-15</td><td>5.58E-14</td><td>1.19E-10</td><td>1.33E-17</td></tr><tr><td></td><td>80</td><td>50</td><td>2000</td><td>2.52E-15</td><td>3.44E-11</td><td>3.25E-08</td><td>1.24E-17</td></tr><tr><td></td><td>20</td><td>10</td><td>1000</td><td>1.74E+01</td><td>1.84E+02</td><td>1.68E+00</td><td>9.47E-04</td></tr><tr><td>f</td><td>50</td><td>30</td><td>1500</td><td>7.79E+01</td><td>3.75E+01</td><td>7.83E+00</td><td>4.22E-03</td></tr><tr><td></td><td>8050</td><td></td><td>2000</td><td>7.82E+01</td><td>1.97E+02</td><td>1.45E+01</td><td>6.99E-03</td></tr></table></body></html>

1020 1.6 1.4 固定   
度10-20 1.1 非线性   
应 V固定 80.5 自适应   
适10-60 \*线性 A非线性 0.5 10-100 -0 一自适应 0.2 0 0.2 0.40.6 0.81.0 0 0.2 0.40.6 0.81.0 t ×10 t ×10 (a)适应度曲线 (b)CE变化曲线   
10³ 1.4 定   
度10 A非线性 1.1 非线性   
应 自适应 80.9 自适应   
适101 0.5   
10° 0.2 0 0.2 0.40.6 0.81.0 0 0.2 0.40.6 0.81.0 t ×10 t ×10 (a)适应度曲线 (b)CE变化曲线

由图3可得，对于类似Rastrigin的多峰优化问题，由于全局范围内存在多个极值，优化问题复杂，势阱收敛慢，所以凸函数曲率相对较小，后期种群多样性更强。总的来说，自适应策略能根据势阱长度相对变化趋势的不同自适应调整CE变化趋势，保证粒子搜索前期的全局搜索能力和搜索后期的局部挖掘能力，以获得更好收敛速度和搜索精度。

为探究本文控制策略深层次原因，以经典线性递减CE系数控制策略为比较对象，与本文提出的具有反馈机制的CE系数自适应变异控制策略进行对比，观察两种控制策略下平均势阱长度 $L$ 变化趋势，如图4所示，其中平均势阱长度如式(15)所示。

$$
\overline { { L ( t ) } } = \frac { 1 } { N \cdot D } \cdot \sum _ { i = 1 } ^ { N } \sum _ { j = 1 } ^ { D } L _ { i , j } ( t )
$$

5 5 5 -5   
山 L   
8o1 Spherbrock 0 Spsenbrock 25 Rastrigin 25 Rastrigin Griewank Griewank 35 A.20.4 0.6 0.81.0 -35 A0.20.4 0.6 0.81.0 t ×10 t ×10 (a)线性递减策略 (b）自适应策略

由图4(a)可知，线性递减控制策略下，类似 Sphere 的简单单峰优化问题，梯度信息明显，粒子会很快搜索到全局最优位置，种群会迅速聚集，势阱会短时间内收缩；Rosenbrock为复杂单峰优化问题，函数曲面平滑，梯度信息不明显，粒子很难搜索到全局最优位置，势阱收缩较缓慢；而类似Rastrigin的四个多峰优化问题，由于局部极值较多，在整个搜索过程势阱长度变化情况均不明显，造成粒子在后期的局部挖掘能力相对较弱，粒子很难搜寻到全局最优位置，这种控制策略小算法收敛精度低。

由图4(b)可知，在自适应变异控制策略下，类似Sphere 的简单单峰优化问题，势阱收缩更为迅速，不仅有利于加快收敛速度，而且有利于粒子找到更优解；类似Rastrigin的多峰优化，该策略优势尤为明显，与图4(a)相比，在搜索后期，该策略控制下势阱长度明显变小，势阱收缩更为剧烈，说明种群进化未停滞，在自适应以及精英粒子交叉学习作用下，粒子进入小范围精细搜索，这也是改进算法在绝大多数多峰优化问题上收敛精度优于传统算法的原因。

# 4基于改进QPSO算法的电动汽车调速控制器设计

# 4.1电动汽车数学模型

电动汽车行驶过程中阻力主要来源于滚动阻力、空气阻力、加速阻力以及坡度阻力[14]四个方面。总阻力满足式(16)中关系。

$$
F _ { \mathit { \Pi } _ { \Xi } } = F _ { f } + F _ { \mathit { \Pi } _ { w } } + F _ { j } + F _ { i }
$$

其中：滚动阻力 $\boldsymbol { F } _ { f }$ 满足式(17)中关系。

$$
F _ { f } = f m g \cos \theta
$$

其中： $m$ 为汽车质量； $f$ 为滚动摩擦系数； $g$ 为重力加速度系数； $\theta$ 为行驶路面坡度。

空气阻力 $F _ { _ w }$ 满足式(18)中关系。

$$
F _ { _ w } = \frac { C _ { d } A \nu ^ { 2 } } { 2 1 . 1 5 }
$$

其中： $C _ { d }$ 为空气阻力系数； $A$ 为迎风面积； $\nu$ 为汽车行驶速度。加速阻力满足式(19)中关系。

$$
F _ { j } = \delta m { \frac { d \nu } { d t } }
$$

其中： $\delta$ 为质量换算系数。

爬坡阻力满足式(20)中关系。

$$
F _ { i } = m g \sin \theta
$$

汽车行驶过程中，行驶速度与车轮转速之间满足式(21)关系。

$$
\nu = 0 . 3 7 7 \frac { n r } { i _ { 0 } i _ { g } }
$$

其中： $n$ 为电机转速； $\boldsymbol { r }$ 为车轮半径； $i _ { 0 }$ 为变速器传动比； $i _ { _ { g } }$ 为主减速器传动比。

汽车行驶过程中，总转矩和所受总阻力满足式(22)关系。

$$
T _ { _ { \ast } } { = } F _ { _ { \ast } } r
$$

电机负载转矩 $T _ { _ L }$ 与总转矩 $T _ { _ \mathrm { . 5 } }$ 之间满足

$$
T _ { L } = \frac { T _ { \mathrm { g s } } } { \eta i _ { 0 } i _ { g } }
$$

其中： $\eta$ 为传动效率。

# 4.2电机数学模型

电动汽车以BLDCM为驱动器[15]，为建立电机数学模型，进行如下假设：

a)不考虑磁滞损耗与涡流损耗;  
b)忽略磁路饱和，忽略磁槽效应；  
c）三相绕组均匀对称分布于电枢绕组表面。

由基尔霍夫电压定律可得，任意一相绕组上电压平衡方程如式(24)所示。

$$
U = R i + L { \frac { d i } { d t } } + E
$$

对于三相绕组，可等效如式(25)所示。

$$
{ \left[ \begin{array} { l } { u _ { a } } \\ { u _ { b } } \\ { u _ { c } } \\ { u _ { c } } \end{array} \right] } = { \left[ \begin{array} { l l l } { R _ { a } } & { 0 } & { 0 } \\ { 0 } & { R _ { b } } & { 0 } \\ { 0 } & { 0 } & { R _ { c } } \end{array} \right] } { \left[ \begin{array} { l } { i _ { a } } \\ { i _ { b } } \\ { i _ { c } } \end{array} \right] } + { \left[ \begin{array} { l l l } { L _ { a } } & { L _ { a b } } & { L _ { a c } } \\ { L _ { b a } } & { L _ { b } } & { L _ { b c } } \\ { L _ { c a } } & { L _ { c b } } & { L _ { c } } \end{array} \right] } p { \left[ \begin{array} { l } { i _ { a } } \\ { i _ { b } } \\ { i _ { c } } \end{array} \right] } + { \left[ \begin{array} { l } { e _ { a } } \\ { e _ { b } } \\ { e _ { c } } \end{array} \right] }
$$

其中： $u _ { a } , \ u _ { b } , \ u _ { c }$ 为三相定子电压(V)； $e _ { a } \setminus e _ { b } \setminus e _ { c }$ 为三相定子反电动势(V)； $i _ { a } \cdot \ i _ { b } \cdot \ i _ { c }$ 为三相定子相电流(A)； $L _ { a } , \ L _ { b } , \ L _ { c }$ 为三相定子自感 $\mathrm { ( H ) }$ ； $L _ { a b ^ { \setminus } } \ L _ { _ { a c } ^ { \setminus } } \ L _ { _ { b a ^ { \setminus } } } \ L _ { _ { b c } ^ { \setminus } } \ L _ { _ { c a } ^ { \setminus } } \ L _ { _ { c b } }$ 为三相定子绕组之间的互感$\mathrm { ( H ) }$ ； $R _ { a } , \ R _ { b } , \ R _ { c }$ 为三相定子绕组的相电阻 $( \Omega )$ ； $P$ 为微分算子$( d / d t )$ 。

为便于分析，现假设三相绕组完全对称分布，且绕组连接方式采用星型无中线式，则有

$$
\begin{array} { r l } & { L _ { a } = L _ { b } = L _ { c } = L } \\ & { R _ { a } = R _ { b } = R _ { c } = R } \\ & { L _ { a b } = L _ { a c } = L _ { b a } = L _ { b c } = L _ { c a } = L _ { c b } = M } \\ & { i _ { a } + i _ { b } + i _ { c } = 0 } \end{array}
$$

其中： $\textbf { \em L }$ 和 $M$ 分别为定子自感和互感，则式(25)可写成

$$
{ \left[ \begin{array} { l } { u _ { a } } \\ { u _ { b } } \\ { u _ { c } } \end{array} \right] } = { \left[ \begin{array} { l l l } { R } & { 0 } & { 0 } \\ { 0 } & { R } & { 0 } \\ { 0 } & { 0 } & { R } \end{array} \right] } { \left[ \begin{array} { l } { i _ { a } } \\ { i _ { b } } \\ { i _ { c } } \end{array} \right] } + { \left[ \begin{array} { l c c } { L - M } & { 0 } & { 0 } \\ { 0 } & { L - M } & { 0 } \\ { 0 } & { 0 } & { L - M } \end{array} \right] } p { \left[ \begin{array} { l } { i _ { a } } \\ { i _ { b } } \\ { i _ { c } } \end{array} \right] } + { \left[ \begin{array} { l } { e _ { a } } \\ { e _ { b } } \\ { e _ { c } } \end{array} \right] }
$$

由式(27)可得BLDCM的等效电路如图5所示。

![](images/5eb36e4aa6eb2af03d85b47cf1ec393ceb7ff50e5decaf6c3956b82a3b8aec6b.jpg)  
图5BLDCM等效电路图

运行状态下，BLDCM的感应电动势与转速、绕组匝数成正比，因此电枢绕组反向电动势的公式可用式(28)表示。

$$
E = \frac { p _ { n } N } { 1 5 \alpha } \phi _ { m } n = K _ { e } * n
$$

其中： $\boldsymbol { p } _ { n }$ 为极对数； $N$ 表示各相线圈串联匝数； $\phi _ { m }$ 表示每极磁通量； $\alpha$ 为极弧系数； $n$ 为电机转速； $K _ { e }$ 为反电动势系数$\left( k r p m / V \right)$ ）

电机的电磁转矩方程和运动方程如式(29)所示。

$$
\begin{array} { l } { \displaystyle { T _ { e } = \frac { p _ { n } ( e _ { a } i _ { a } + e _ { b } i _ { b } + e _ { c } i _ { c } ) } { n } } } \\ { \displaystyle { J \frac { d n } { d t } = T _ { e } - T _ { L } - B n } } \end{array}
$$

其中：对于单相，可得 $T _ { e } = K _ { T } * i _ { a }$ ; $_ \mathrm { ~ J ~ }$ 为转子惯量 $( \mathrm { g c m } ^ { 2 } )$ ； $B$ 为阻尼系数； $K _ { T }$ 为转矩常数( $N \cdot m / A )$ ； $n$ 为电机转速； $T _ { _ L }$ 为电机负载转矩 $\left( N \cdot m \right)$ ，由式(23)决定。

对上述方程组取拉普拉斯变换，可得BLDCM的动态模型，如图6所示。

![](images/a236a6d4e75347a48409ffda175cb77fcce5eed208749ba0092dfe924514957e.jpg)  
图6BLDCM动态模型图

由图6可得，电机的传递函数可用式(30)表示。

$$
n ( s ) = \frac { K _ { T } } { J L S ^ { 2 } + J R S + K _ { T } K _ { E } } U _ { a } ( s ) - \frac { L S + R } { J L S ^ { 2 } + J R S + K _ { T } K _ { E } } T _ { L } ( s )
$$

# 4.3基于AMF-QPSO算法的控制器设计

电动汽车行驶工况复杂，且需进行频繁调速，传统PID控制器很难取得预期控制效果。本文采用模糊PID作为控制器[16]，系统结构如图7所示。

![](images/cc4e8efaf9d2f262431164522ae9b1a3a330ed93547f8104617eb0fcd63022c1.jpg)  
图7基于模糊自适应PID的BLDCM调速系统

影响控制器性能指标的主要有两大因素：a)PID控制器参数 $k _ { P }$ 、 $k _ { \scriptscriptstyle I }$ 、 $k _ { D }$ ；b）量化因子 $k _ { e }$ 、 $k _ { e c }$ 和比例因子 $k _ { u }$ 。由于模糊PID 控制器对于 $k _ { \scriptscriptstyle P }$ 、 $k _ { \scriptscriptstyle I }$ 、 $\boldsymbol { k } _ { D }$ 具有一定调节能力，但控制器本身自适应性能不高，为进一步优化模糊控制器性能，可从模糊控制器关键参数，即量化因子和比例因子的优化入手。

若以被控量误差 $e$ 及其误差变化率 $e c$ 作为系统输入，设 $\boldsymbol { \mathscr { e } }$ 的基本论域为 $\left[ e _ { L } , e _ { H } \right]$ ， $e c$ 的基本论域为 $\left[ e c _ { L } , e c _ { H } \right]$ ，输出变量 $u$ 的基本论域为 $\left[ u _ { L } , u _ { H } \right]$ 。误差变量模糊论域$\left\{ - i , - i + 1 , \cdots , 0 , \cdots , i - 1 , i \right\} , i \in { \cal N }$ ，误差变量率的模糊论域$\left\{ - j , - j + 1 , \cdots , 0 , \cdots , j - 1 , j \right\} , j \in \cal { N }$ ，输出控制量模糊论域$\left\{ - k , - k + 1 , \cdots , 0 , \cdots , k - 1 , k \right\} , k \in { \cal N }$ ，则量化因子 $k _ { e }$ 、 $k _ { e c }$ 和比例因子 $k _ { u }$ 由式(31)确定。

$$
k _ { e } = \frac { 2 i } { e _ { H } - e _ { L } } k _ { e c } = \frac { 2 j } { e c _ { H } - e c _ { L } } k _ { u } = \frac { u _ { H } - u _ { L } } { 2 k }
$$

但环境因素及各项参数误差，使得理论值与实际值常存在偏差，造成系统性能随机性强，对控制参数敏感，所以实际应用时还需根据经验进行调整。

因此，本节以此为研究重点，在模糊PID基础上，利用AMF-QPSO算法优化模糊PID控制器中量化因子 $k _ { e }$ 、 $k _ { e c }$ 和比例因子$k _ { \scriptscriptstyle \mu }$ 的整定过程，使其能适应系统参数变化，从而增强系统抗干扰和自适应性能。算法结构如图8所示。

![](images/fd521b87e356183b624cc06b5054f63f2f0244c230d519665349a21329f1402b.jpg)  
图8AMF-QPSO 算法优化模糊 PID

整个系统可分为AMF-QPSO 算法执行单元和Simulink仿真单元两大部分。其中 AMF-QPSO 算法由 MATLAB 中的 S-Function函数实现。设粒子维数为3，分别代表2个量化因子和1个输出因子，种群规模为20，最大迭代代数为500，其他控制参数参考3.1小节。模糊 PID控制器及BLDCM控制系统由 Simulink工具箱搭建，其中模糊PID控制器以BLDCM控制系统转速误差e及其变化率 $e c$ 作为模糊控制器输入，以调整量$\Delta k _ { P }$ 、 $\Delta k _ { I }$ 、 $\Delta k _ { D }$ 为控制器输出，模糊集为{NB、NM、NS、ZE、PS、PM、PB}。各变量基本论域和模糊论域如表4所示。模糊规则与文献[17]相同，隶属度函数采用三角型，以ifthen的形式输入模糊控制规则，运用重心法将模糊量进行清晰化处理得到被控系统控制量。

表4模糊自适应PID控制器参数表  

<html><body><table><tr><td>参数</td><td>e</td><td>ec</td><td>△kp</td><td>△k</td><td>△kD</td></tr><tr><td>语言变量</td><td>E</td><td>EC</td><td>kp</td><td>k</td><td>kD</td></tr><tr><td>基本论域</td><td>[-100 100]</td><td>[-106106]</td><td>[-0.01 0.01]</td><td>[-0.1 0.1]</td><td>[-0.01 0.01]</td></tr><tr><td>模糊论域</td><td>[-6 6]</td><td>[-6 6]</td><td>[-6 6]</td><td>[-6 6]</td><td>[-6 6]</td></tr><tr><td>转换因子</td><td>0.06</td><td>6/106</td><td>1/600</td><td>1/60</td><td>1/600</td></tr></table></body></html>

为平衡系统动、静态特性，在保证稳态误差趋于零的同时，使系统的超调量 $\sigma$ 、调节时间 $t _ { s }$ 控制在较小范围内，则适应度函数确定为

$$
f i t n e s s = \int _ { 0 } ^ { \infty } k _ { 1 } \left| e ( t ) \right| d t + k _ { 2 } t _ { s } + k _ { 3 } \sigma
$$

其中： $k _ { \mathrm { 1 } }$ 、 $k _ { 2 }$ 、 $k _ { 3 }$ 为各性能指标的权重系数，由实际系统所侧

重的性能指标来确定大小。

# 5 实验与结果分析

# 5.1搭建实验平台

实际电动汽车调速控制系统工况复杂，包括软、硬件系统。为便于实验室研究，硬件系统设计上，本文以Maxon公司制造的小型BLDCM模拟电动汽车电机。查阅数据手册，详细参数见表5所示。以ST公司的专用集成芯片L6235为核心搭建逆变电路。

表5直流无刷电机参数表  

<html><body><table><tr><td>主要指标</td><td>参数值</td></tr><tr><td>额定电压/U</td><td>24V</td></tr><tr><td>额定功率/P</td><td>90W</td></tr><tr><td>额定转速/n</td><td>5700 r/min</td></tr><tr><td>额定转矩/T</td><td>47 mN ·m</td></tr><tr><td>相感抗/L</td><td>1.6×10 H</td></tr><tr><td>相电阻/R</td><td>0.51 Ω</td></tr><tr><td>反电动势/KE</td><td>1.47×10-³ V · s / rad</td></tr><tr><td>转矩常数/KT</td><td>0.014 N ·m/ A</td></tr><tr><td>转子惯量/J</td><td>5.54×10-7 Kgm²</td></tr></table></body></html>

软件设计上，利用ActiveX技术将LabVIEW和MATLAB联系起来。LabVIEW主要完成数据采集与处理、系统拟合、PWM控制信号输出、网络通信以及图形化界面设计[18]，MATLAB用于执行AMF-QPSO 算法以及对比算法。整个实验平台系统框架如图9所示。

![](images/793d1329a6502aa4d13ad1c4cd376bfeb47f159ecfb6773433ddf382482435e8.jpg)  
图9实验平台系统框图

# 5.2控制器动态性能分析

为验证控制器动态性能，采用单位阶跃信号作为测试信号，MATLAB平台上依次运行传统模糊PID(Fuzzy)算法、QPSO 算法优化后的模糊 PID(QPSO-Fuzzy)算法以及 AMF-QPSO 算法优化后的模糊 PID(AMF-QPSO-Fuzzy)算法。LabVIEW 利用ActiveX技术调用MATLAB算法进程,并通过数据采集卡(DAQ)获取的电机实际工作状态，根据4.1和4.2节构建的数学模型拟合电动汽车速度控制系统模型，最后输出PWM控制信号，控制逆变电路。在上位机界面上观察系统输出响应曲线，实验结果如图10所示。

为定量比较优化后的控制器的性能优势，计算各控制系统单位阶跃下的性能指标，包括稳态误差、超调量以及调节时间，结果如表6所示。

根据图10及表6实验数据可知，经QPSO及AMF-QPSO算法优化后的控制器在稳态误差、超调量以及调节时间上均优于传统模糊PID 控制器。经AMF-QPSO 算法优化后的控制器较QPSO算法优化后的控制器复杂程度更高，故在上升时间上略慢与QPSO 算法优化后的控制器，但AMF-QPSO 算法优化后的控制器在稳态误差、超调量以及调节时间上具有绝对优势。

![](images/fd7669b88d9e7d4da16f019c98d32d102a4f84e3771f82c5fb2931d4d77e870a.jpg)  
图10各控制策略下的阶跃响应曲线

表6各控制系统单位阶跃下的性能指标  

<html><body><table><tr><td>优化算法</td><td>稳态误差δ/%</td><td>超调/%</td><td>调节时间t /s</td></tr><tr><td>Fuzzy</td><td>0.22</td><td>18.5</td><td>0.036</td></tr><tr><td>QPSO-Fuzzy</td><td>0.18</td><td>8.7</td><td>0.022</td></tr><tr><td>AMF-QPSO-Fuzzy</td><td>0.08</td><td>0.5</td><td>0.012</td></tr></table></body></html>

为进一步验证AMF-QPSO 算法优化后的模糊PID控制器的抗干扰及自适应性能，外加幅值为1的方波信号，模拟电动汽车行驶过程中受到的周期干扰信号。实验结果如图11所示，其细节部分如图12所示。

![](images/b6e6c11fbaf5393fbd751aec519e09442871ca2d2add113625b90abe1b70af19.jpg)  
图11各控制策略下的方波响应曲线

![](images/487a62c5b4e446d054fe549756833c97d933fec75a6bf0960d41f89b02eb3884.jpg)  
图12各控制策略下的方波响应曲线局部图

由图11、12可知，AMF-QPSO 算法优化后的模糊 PID 控制器虽在响应速度上略慢与QPSO算法优化后的控制器，但控制器具有超调小、稳态精度高、抗干扰及自适应性能强等绝对

优势。

# 5.3控制器调速性能分析

对系统调速性能进行测试，仿真时长 $0 . 4 \ : \mathrm { s }$ ，主要通过空载和负载实验进行论述。系统空载状况下启动，设定预期转速为$1 0 0 0 \mathrm { r / m i n }$ ，速度稳定后，在 $\mathrm { \ t = 0 . 1 s }$ 时，突加负载 $T _ { L } = 0 . 0 3 N \cdot m$ ，模拟行驶坡度变为 $5 ^ { \circ }$ ，坡度阻力相应增加时系统速度响应;在 $\mathrm { \ t = } 0 . 2 \mathrm { ~ s ~ }$ 时，将转速调节至 $2 0 0 0 \mathrm { r / m i n }$ ，模拟电动汽车突然加速时系统速度响应，观察系统速度响应曲线、转速及其局部放大响应曲线如图13和14所示，转矩响应曲线如图15所示。

![](images/8f908af331c263984c8c6097a4b94b2b88a869ed1ba8ef48a3b617d5687f8279.jpg)  
图13各控制策略下的速度响应曲线

由图13可知，AMF-QPSO算法优化后的控制器在调速性能上优于传统模糊PID控制器及QPSO算法优化后的模糊PID控制器，其性能优势详见图14所示。

![](images/d5b66654ebd84b3ee184ecd67cf7345b3102e3ba9e2e372b2148cc222be48ba3.jpg)  
图14各控制策略下速度响应局部曲线

图14(a)为各控制系统空载启动时速度响应，可得经AMF-QPSO优化后的控制器在响应速度上虽略慢于QPSO优化后的控制器，但在稳态精度上最优，误差仅为 $0 . 0 5 \%$ ； (b)为 $\mathrm { \ t = 0 . 1 s }$ 时，突加负载后各系统速度响应，用于验证系统抗干扰能力。由理论知识可知，突加负载后电机转速会短时下降，此时控制器为维持速度恒定，会迅速提升绕组电流，进而增大输出转矩直至平衡负载转矩，使得系统能尽快跟随系统参数变化。其中转矩的情况可见图15所示。传统模糊PID控制器抗干扰能力差，系统很难恢复至加负载前的转速；经QPSO算法优化后的控制器虽响应速度快，但转速及转矩脉动大；经AMF-QPSO 算法优化后的控制器反映虽相对略慢，但其精度高，转速及转矩脉动小，抗干扰能力强。

![](images/9c253367989913a84efec55505841fdb8c1b5f3a1fbf3201744cc76e332c6e31.jpg)  
图15各控制策略下转矩变化情况

图14(c)为 $\scriptstyle { \mathrm { t = } } 0 . 2 { \mathrm { ~ s ~ } }$ 时，负载调速实验，将转速提升至2000$\mathbf { r } / \mathrm { m i n }$ 时各系统速度响应，用于验证负载状态系统调速性能。由理论知识可知，为实现加速，绕组电流进一步有所提升，反向电动势也会相应变大，使得转矩会短暂性提升，从而让电机具有一定加速度，当速度上升至所需调节速度值后，转矩会恢复至平衡状态值，以维持电机恒速运行。传统模糊PID控制器响应最慢，存在稳态误差，且超调量大，达到 $0 . 3 \%$ ；经QPSO优化后的模糊PID控制器响应速度最快，但也存在稳态误差，超调也较大，达到 $0 . 3 \%$ ；AMF-QPSO算法优化后的控制器速度调节虽略慢，需 $0 . 0 7 5 \mathrm { s }$ ，但该策略下超调小，仅为 $0 . 0 2 5 \%$ ，基本无稳态误差。

综上所述，AMF-QPSO 算法优化后的模糊PID控制器能凭借算法高效精准的全局搜索性能快速将控制参数调整至一个较优值，适应系统参数变化，减小稳态误差，避免速度抖动，提高系统控制性能和抗干扰能力。

# 6 结束语

本文分析了CE系数与势阱长度之间的关系，在此基础上提出了粒子活性概念，以势阱长度相对变化率作为粒子活性衡量标准，并将粒子活性作为反馈量，自适应调节CE系数。同时，为防止种群后期多样性衰减严重，粒子陷入局部最优位置，提出了精英群体的随机交叉学习机制，让活性低的精英个体随机的与种群中其他个体交换部分维度信息，提高种群多样性，加快后期的搜索速度和收敛精度。为验证算法性能，将AMF-QPSO算法应用于电动汽车调速控制系统中模糊控制器参数优化问题中，并以LabVIEW为实验平台，通过与传统模糊PID控制器以及QPSO优化后的模糊PID控制器进行性能对比，实验结果表明 AMF-QPSO 算法优化后的控制器具有良好的响应速度和控制精度，且对于系统扰动具有很好的自适应和自调节能力，对电动汽车速度控制器优化具有重要意义。

# 参考文献：

[1] Wen Jianping,Zhang Chuanwei. Research on modeling and control of regenerative braking for brushless DC machines driven electric vehicles [J]. Mathematical Problems in Engineering,2017,2015(1):1-6.   
[2] 蔡红萍．基于直流无刷电机的光伏扬水系统控制研究[D].杭州：浙江 工业大学,2016.(Cai Hongping. Research of photovoltaic pumping system base on brushless DC motor [D]. Hangzhou: Zhejiang University of Technology, 2016.)   
[3]Ramya A, Imthiaz A,Balaji M.Hybrid self tuned fuzzy PID controller for speed control of brushless DC motor[J].Automatika,2017,57(3): 672-679.   
[4]黄卫华，龙海燕，方康玲．具有加权因子的PID型模糊控制器分析及设 计[J].计算机应用研究,2013,30（7):1967-1970.(Huang Weihua,Long Haiyan,Fang Kangling. Analysis and design of PID-fuzzy controler with weighted factor[J].Application Research ofComputers,2013,30(7):1967- 1970.）   
[5]Huang Wei, Oh S K,Pedrycz W.Fuzzy wavelet polynomial neural networks: analysis and design [J].IEEE Trans on Fuzzy Systems,2017,25(5):1329- 1341.   
[6]Sun Jun,Feng Bin,Xu Wenbo.Particle swarm optimization with particles having quantum behavior [Cl/ Proc of IEEE CEC2004. San Diego: CA Press,2004: 325-331.   
[7]Fang Wei, Juan Liu, Xie Zhenping, et al. Convergence analysis of quantumbehaved particle swarm optimization algorithm and study on its control parameter[J].Acta Physica Sinica,2010,59 (6): 3686-3694.   
[8]Sun Jun,Fang Wei,Wu Xiaojun,et al. Quantum-behaved particle swarm optimization:analysisof individual particle behavior and parameter selection [J].Evolutionary Computation,2014,20 (3): 349-393.   
[9] 黄为勇，徐晓菊，潘晓博，等.量子粒子群优化算法的收缩一扩张系数 控制策略研究[J].计算机应用研究,2016,33(9):2592-2595.(Huang Weiyong,Xu Xiaoju,Pan Xiaobo,et al. Control strategy of contractionexpansion coeficient in quantum-behaved particle swarm optimization [J]. Application Research of Computers,2013,30(7): 1967-1970.)   
[10]康燕，孙俊，须文波．具有量子行为的粒子群优化算法的参数选择 [J]. 计算机工程与应用,2007,43(23):40-42.(Kang Yan,Sun Jun,Xu Wenbo. Parameter selection of quantum-behaved particle swarm optimization [J]. Computer Engineering and Applications,2007,43 (23):40-42.)   
[11]Liu Peilin,Leng Wenhao,Fang Wei.Training ANFIS model with an

improved quantum-behaved particle swarm optimization algorithm [J].

Mathematical Problems in Engineering,2013,2013(1):78-81.   
[12] Frans VD B.An analysis of particle swarm optimizers [D].Pretoria,PhD: UP,Department of Computer Science,2006.   
[13] Clerc M，Kennedy J.The particle swarm-explosion，stability，and convergence in a multidimensional complex space [J].IEEE Trans on Evolutionary Computation,2002,20(1):1671-1676.   
[14]朱骏驰，李文超，陆颖．电动汽车无刷直流电机的改进模糊控制研究 [J]．机械与电子,2017,35(6): 51-54.(Zhu Junchi,Li Wenchao,Lu Ying. Research on the improved fuzzy control of brushless DC motor for electric vehicles [J].Machinery and Electronics,2017,35(6):51-54.)   
[15]KhelifaM,MordjaouiM,MedouedA.An inverse problem methodology for design and optimization of an interior permanent magnetic BLDC motor [J]. International Journal of Hydrogen Energy,2017,28 (42):17733-17740.   
[16]刘慧博，王静，吴彦合．无刷直流电机模糊自适应PID控制研究与仿真 [J].控制工程,2014,21(4): 583-587.(Liu Huibo,Wang Jing,Wu Yanhe. Study and simulationof fuzzy adaptive PID control of brushless DC motor [J].Control Engineering of China,2014,21(4): 583-587.)   
[17]高宏伟，赵宝永．模糊自整定 PID 控制策略的 MATLAB 仿真研究[J]. 电气传动 自动化,2002,24(5):21-23.(Gao Hongwei, Zhao Baoyong,Fu Xingwu.MATLAB simulation research on fuzzy self_adjusting PID control strategy [J]. Electric Drive Automation,2002,34(5):21-28.)   
[18]袁小平，金鹏，蒋硕，等．基于LabVIEW的远程虚拟实验室建设与应 用[J].实验技术与管理,2016,33(12):114-117.(Yuan Xiaoping,Jin Peng,Jiang Shuo,et al.Construction and application of remote virtual laboratorybased on LabVIEW[J].Experimental Technologyand Management,2016,33(12): 114-117.)