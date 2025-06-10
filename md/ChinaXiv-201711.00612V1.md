# 量子斯特林致冷循环性能研究

殷勇1,2 吴锋²陈林根1,3,4,（1.海军工程大学热科学与动力工程研究室，武汉4300332．武汉工程大学理学院武汉4300333.海军工程大学舰船动力工程军队重点实验室，武汉4300334．海军工程大学动力工程学院，武汉430033）

摘要：建立了以无数个无限深势阱中的粒子为工质的不可逆量子斯特林致冷循环模型。势阱中粒子在能级上的分布由吉布斯分布函数决定。该致冷循环由两个等能量过程与两个等势阱壁宽度过程组成，具有高低温热源间的热漏和不完全回热因素。导出了性能系数、致冷率、熵产率和生态学目标函数性能解析式，制冷率与生态学函数的关系曲线是回原点的扭叶型。分析了热漏系数与不完全回热因子对性能系数、致冷率和生态学函数的影响。

关键词：有限时间热力学；一维无限深势阱；量子制冷循环；生态学性能优化中图分类号：TK123 文献标识码：A

# Study on the performance of quantum Stirling refrigeration cycle

YIN Yong1,2 WU Feng 2 CHENLin-genl,3,4\*

(1 Institute ofThermal Science andPowerEnginering,Naval Universityof Engineering,Wuhan 43Oo33,PR China 2 School of Science,Wuhan Institute of Technology,Wuhan 43OO73,China 3MilitaryKeyLaboratoryforNaval Ship Power Enginering,Naval Universityof Engineering,Wuhan 43O33,PR China 4 College of Power Engineering,Naval University of Engineering,Wuhan 43Oo33,PR China)

Abstract: An irreversible quantum Stirling refrigeration model is established in which working substance is a single particle contained in a one-dimensional infinite potential well,and the system consists of countless replicas.The occupation probabilities in each eigenstates of the particleare expressd by the thermal equilibrium Gibbs distributions.The cycle is made of two iso-energy branches and two isochoric branchesand with heat leakage between heat reservoirs and imperfect regeneration. Analytical expressions ofCOP,cooling rate,entropy generation rate and ecological function are derived.The curve between cooling rate and ecological function is a loop-shaped one.Effects of heat leakage and imperfect regeneration on COP,cooling rate and ecological function are analyzed.

Keywords:finite time thermodynamics；one-dimensional infinite potential well; quantum refrigeration cycle; ecological performance optimization

# 0引言

在微纳米尺度[1-4]、低温或高密度条件下，需要考虑热力循环工质的量子特性。应用有限时间热力学理论和方法[5-15],可以建立各种量子循环模型[16-24],研究其热力性质与性能参数，优化其运行区间。实际热机中，存在着热阻、热漏、摩擦、涡流、惯性效应及非平衡的影响，循环为不可逆循环[25]。一些学者也研究了不可逆因素对量子热力循环性能的影响。金晓昌等[26]考虑高、低温热源间的弱耦联作用，引入了旁通热漏。Feldmann 和 Kosloff[27]引入了内摩擦系数来描述量子非绝热现象。吴锋等[28]考虑热漏、热阻以及有限速率传热对不可逆量子斯特林制冷机性能的影响．金晓昌[29]从烟经济学角度研究了量子斯特林制冷机最优性能。

在文献[3,10,14,16,23,28,30]的基础上，本文将建立一个包含高低温热源间的热漏与不完全回热的不可逆斯特林制冷机循环，其工质为无数个囚禁于一维无限深势阱中的粒子。导出循环的性能系数、致冷率、熵产率、生态学函数，分析这些重要的性能参数与热漏率和不完全回热因子之间的关系。

# 1系统的量子力学描述

本文研究的对象是一个囚禁于宽度为 $L$ 的一维无限深势阱中的粒子。其定态波函数满足：

$$
d ^ { 2 } \Psi / d x ^ { 2 } + 2 m E \Psi / \hbar ^ { 2 } = 0
$$

根据波函数 $\psi$ 必须满足的边界条件 $\scriptstyle \psi ( 0 ) = 0$ 和$\scriptstyle \psi ( L ) = 0$ ，可求出波函数为：

$$
\Psi ( x ) = \sum _ { n = 1 } ^ { \infty } a _ { n } \varphi _ { n ( x ) }
$$

式中 $\varphi _ { n } ( x )$ 是归一化的本征函数：

$$
\phi _ { n } ( x ) = \sqrt { 2 / L } \sin ( n \pi x / L )
$$

系数 $a _ { n }$ 满足归一化条件：

$$
\sum _ { n = 1 } ^ { \infty } \bigl | a _ { n } \bigr | ^ { 2 } = \sum _ { n = 1 } ^ { \infty } p _ { n } = 1
$$

式中 $\scriptstyle { p _ { n } = a _ { n } } ^ { 2 }$ ，为概率密度，系统的能量本征值为：

$$
E _ { n } = n ^ { 2 } \pi ^ { 2 } \eta ^ { 2 } / ( 2 m L ^ { 2 } )
$$

式中 $\mathbf { \nabla } _ { m }$ 和 $n$ 分别为粒子的质量与量子数，哈密顿量的期望值为：

$$
E = \sum _ { n = 1 } ^ { \infty } \bigl | a _ { n } \bigr | ^ { 2 } E _ { n } = \sum _ { n = 1 } ^ { \infty } p _ { n } E _ { n }
$$

经典循环中，活塞在气缸中做往复运动，假设势阱壁像经典循环中的活塞一样运动，当势阱宽度 $L$ 变化时，系统的波函数与能级都会随着 $L$ 变化。定义广义力为：

$$
Y _ { n } = - d W / d y _ { n }
$$

式中， $\mathbf { y } _ { n }$ 是与广义力 $Y _ { n }$ 对应的广义坐标。因此，作用在势阱壁的力可以表示成：

$$
F = - d E / d L = \sum _ { n = 1 } ^ { \infty } p _ { _ n } [ n ^ { 2 } \pi ^ { 2 } \mathrm { h } ^ { 2 } / ( m L ^ { 3 } ) ]
$$

2.量子斯特林致冷循环

研究囚禁于一维无限深势阱中的粒子，为简单起见，只考虑两个能级。循环工质为无数个这样的粒子，每一个都被囚禁在一个一维无限深势阱中，粒子在能级上的占有几率由吉布斯分布决定。循环由两个等能量过程与两个等势阱壁的回热过程组成，分别与经典循环中的等温过程与等容过程对应。考虑不完全回热与高低温热源之间的热漏，系统从温度为 $T _ { L }$ 的低温热源吸收热量，放出热量给温度为$T _ { H }$ 的高温热源，如图1所示。该循环是一个不可逆量子斯特林致冷循环。过程1-2为等能量过程，在此过程中系统的总能量保持不变，由此可得：

$$
\begin{array} { r l } & { E _ { h } = p _ { 1 1 } E _ { 1 1 } + p _ { 1 2 } E _ { 1 2 } = } \\ & { p _ { L 1 } E _ { L 1 } + p _ { L 2 } E _ { L 2 } = p _ { 2 1 } E _ { 2 1 } + p _ { 2 2 } E _ { 2 2 } } \end{array}
$$

式中 $P _ { i n } , E _ { i n }$ （ $\cdot _ { i = 1 , 2 , L ; \mathrm { n } = 1 , 2 }$ ）分别表示概率密度与对应能级的能量本征值， $\scriptstyle { \dot { \iota } } = L$ 表示任意态， $n$ 为量子数。把式(4)和(5)代入式(9)可得：

$$
( 4 - 3 p _ { 1 1 } ) / L _ { 1 } ^ { 2 } = ( 4 - 3 p _ { _ { L 1 } } ) / L ^ { 2 } = ( 4 - 3 p _ { _ { 2 1 } } ) / L _ { 2 } ^ { 2 }
$$

![](images/c6ed97f2ca98e38d7df5ef382175155f07661ca32efb2d7b31fb9d9fc1fda4a7.jpg)  
图1量子斯特林致冷循环示意图.  
Figure 1. Sketch of a quantum Stirling refrigeration cycle.

由式(8)和(10)可以求得在等能量过程1-2中，作用在势阱壁上的力为：

$$
F _ { 1 2 } = \pi ^ { 2 } \mathrm { h } ^ { 2 } ( 4 { - } 3 p _ { 1 1 } ) / ( m L L _ { 1 } ^ { 2 } )
$$

等能量过程中系统的总能量保持不变，系统从低温热源吸收的热量全部用来对外做功，因此：

$$
Q _ { 1 2 } = W _ { 1 2 } = \int _ { L _ { 1 } } ^ { L _ { 2 } } \frac { \pi ^ { 2 } \mathrm { h } ^ { 2 } } { m } \frac { 1 } { L _ { 1 } ^ { 2 } } ( 4 - 3 p _ { 1 1 } ) \frac { d L } { L }
$$

$$
= \pi ^ { 2 } \hbar ^ { 2 } ( 4 - 3 p _ { 1 1 } ) ( m L _ { 1 } ^ { 2 } ) ^ { - 1 } \ln ( L _ { 2 } / L _ { 1 } )
$$

同理，在过程3-4中，系统释放给高温热源的热量与外界对系统所做的功等于：

$$
Q _ { 3 4 } = \bigl | W _ { 1 2 } \bigr | = \left| \int _ { L _ { 2 } } ^ { L _ { 1 } } \frac { \pi ^ { 2 }  { \mathrm { h } } ^ { 2 } } { m } \frac { 1 } { L _ { 2 } ^ { 2 } } ( 4 - 3 p _ { 3 1 } ) \frac { 1 } { L } d L \right|
$$

$$
= \pi ^ { 2 } \hbar ^ { 2 } ( 4 - 3 p _ { 3 1 } ) ( m L _ { 2 } ^ { 2 } ) ^ { - 1 } \ln ( L _ { 2 } / L _ { 1 } )
$$

过程2-3与4-1为回热过程，理想回热过程中，在回热器中交换的热量分别为：

$$
Q _ { 2 3 } = \frac { \pi ^ { 2 } \eta ^ { 2 } } { m } \frac { 1 } { L _ { 1 } ^ { 2 } } [ ( 4 - 3 p _ { 1 1 } ) - \frac { L _ { 1 } ^ { 2 } } { L _ { 2 } ^ { 2 } } ( 4 - 3 p _ { 3 1 } ) ]
$$

$$
Q _ { 4 1 } = \frac { \pi ^ { 2 } \mathrm { h } ^ { 2 } } { m } \frac { 1 } { L _ { 1 } ^ { 2 } } [ ( 4 - 3 p _ { 1 1 } ) - \frac { L _ { 1 } ^ { 2 } } { L _ { 2 } ^ { 2 } } ( 4 - 3 p _ { 3 1 } ) ]
$$

从式(14)和(15)可以看出， $\mathrm { Q } _ { 2 3 } \mathrm { = } \mathrm { Q } _ { 4 1 }$ ，这说明，理想量子斯特林制冷机可以实现完全回热。假设高低温热源之间存在热漏，热漏率由下式决定：

$$
\dot { Q } _ { i } = \pi ^ { 2 } \mathrm { h } ^ { 2 } \alpha / ( m L _ { 1 } ^ { 2 } )
$$

式中 $\alpha$ 为常数。则每一个循环的漏热量为：

$$
\boldsymbol { Q } _ { e } = \stackrel { \mathrm { g } } { \boldsymbol { Q } } _ { i } \boldsymbol { \tau }
$$

式中t为循环周期。在4-1这个回热过程中，如果是理想回热过程，系统会在状态1结束回热过程；由于内部不可逆性，实际的斯特林制冷机存在回热损失，因为非理想回热，系统在状态1’结束回热过程。引入一个非理想回热因子 $\mu ( \mu { > } 0 )$ ，则非理想回热过程中的损失可表示为：

$$
Q _ { r } = \mu Q _ { 4 1 }
$$

因此，从低温热源吸收的净热量与释放给高温热源的净热量分别可以表示为：

$$
\begin{array} { r } { Q _ { h } = Q _ { 3 4 } + Q _ { r } + Q _ { e } } \\ { Q _ { L } = Q _ { 1 2 } - Q _ { r } - Q _ { e } } \end{array}
$$

粒子在某一能级上的概率密度由吉布斯分布为：

$$
P _ { 1 1 } = 1 / \{ 1 + \exp [ \pi ^ { 2 } \eta ^ { 2 } / ( k T _ { L } 2 m L _ { 1 } ^ { 2 } ) ] \}
$$

$$
\begin{array} { r l } & { P _ { 2 1 } = 1 / \{ 1 + \exp [ \pi ^ { 2 } \eta ^ { 2 } / ( x ^ { 2 } k T _ { L } 2 m L _ { 1 } ^ { 2 } ) ] \} } \\ & { P _ { 3 1 } = 1 / \{ 1 + \exp [ \pi ^ { 2 } \eta ^ { 2 } / ( x ^ { 2 } k T _ { H } 2 m L _ { 1 } ^ { 2 } ) ] \} } \\ & { P _ { 4 1 } = 1 / \{ 1 + \exp [ \pi ^ { 2 } \eta ^ { 2 } / ( k T _ { H } 2 m L _ { 1 } ^ { 2 } ) ] \} } \end{array}
$$

# 3．循环周期

假设势阱壁以速度 $\nu ( t )$ 运动，平均速度为 $\nu ,$ 可得：

$$
L _ { 2 } \mathrm { - } L _ { 1 } = \int _ { L _ { 1 } } ^ { L _ { 2 } } \nu ( t ) d t = \overline { { \nu } } \tau _ { 1 2 }
$$

等能量过程1-2与3-4所需的时间为：

$$
\tau _ { 1 2 } = \tau _ { 3 4 } = ( L _ { 2 } - L _ { 1 } ) / \nu
$$

过程2-3与4-1为等势阱壁过程，在此过程中系统内能变化。假设内能随时间的变化率为常数，因为在势阱宽度不变时，系统内能是温度的单值函数，故有：

$$
d \mathbf { T } / d t = \pm \mathbf { M } _ { \mathrm { i } }
$$

式中 $M$ 是一个与系统能量无关的常数，它只取决于回热材料的回热特性。正负号分别表示过程 $2 - 3 ( i = 1 )$ 与过程 $\scriptstyle 4 - 1 ( i = 2 )$ ．为简单起见，假设 $\scriptstyle { M _ { I } = M _ { 2 } }$ 。因此，回热过程2-3与4-1所需的时间可分别表示为：

$$
\begin{array} { c } { { \tau _ { _ { 2 3 } } = ( \mathrm { T } _ { _ { H } } - T _ { _ { L } } ) / \mathrm { M } } } \\ { { \tau _ { _ { 4 1 } } = ( \mathrm { T } _ { _ { H } } - T _ { _ { L } } ) / \mathrm { M } } } \end{array}
$$

整个循环的周期可以表示为：

$$
\begin{array} { r l } & { \tau = \tau _ { 1 2 } + \tau _ { 2 3 } + \tau _ { 3 4 } + \tau _ { 4 1 } = } \\ & { 2 ( L _ { 2 } - L _ { 1 } ) / \stackrel { - } { \nu } + 2 ( T _ { H } - T _ { L } ) / M } \end{array}
$$

4.不可逆斯特林制冷循环一些重要性能参数及分析

由式（12）和(13)可得循环的输入功为：

$$
W = \frac { \pi ^ { 2 } \eta ^ { 2 } } { m L _ { 1 } ^ { 2 } } \ln x [ ( 4 - 3 p _ { 1 1 } ) - \frac { 1 } { x ^ { 2 } } ( 4 - 3 p _ { 3 1 } ) ]
$$

式中 $\scriptstyle x = L _ { 2 } / L _ { 1 }$ ，表示势阱宽度比。由式(19)和(31)可得该不可逆量子斯特林制冷机的性能系数(COP)为：

$$
\begin{array} { c c } { { c o p = \{ ( 4 - 3 p _ { 1 1 } ) \ln x - \alpha \tau - \mu [ ( 4 - 3 p _ { 1 1 } ) } }  \\ { { - ( 4 - 3 p _ { 3 1 } ) / x ^ { 2 } ] \} / \{ \ln x [ ( 4 - 3 p _ { 1 1 } ) } } \\  { - ( 4 - 3 p _ { 3 1 } ) / x ^ { 2 } ] \} } \end{array}
$$

联立式(19)与(30)可得的致冷率为：

$$
\begin{array} { r l } & { R = \{ ( 4 - 3 p _ { 1 1 } ) \ln x - \alpha [ 2 L _ { 1 } ( x - 1 ) / \overline { { \nu } } + } \\ & { ~ 2 ( T _ { H } - T _ { L } ) / M ] - \mu [ ( 4 - 3 p _ { 1 1 } ) - } \\ & { ~ ( 4 - 3 p _ { 3 1 } ) / x ^ { 2 } ] \} / \{ 2 L _ { 1 } ( x - 1 ) / \overline { { \nu } } } \\ & { ~ + 2 ( T _ { H } - T _ { L } ) / M \} } \end{array}
$$

熵产率为：

$$
\begin{array} { c c } { { \displaystyle \sigma = \displaystyle \frac { 1 } { \tau } \displaystyle \frac { \pi ^ { 2 } \mathsf { \eta } ^ { 2 } } { m L _ { 1 } ^ { 2 } } \displaystyle \{ \frac { 1 } { T _ { L } } \{ ( 4 - 3 p _ { 1 1 } ) \ln x - \alpha \tau - \mu [ ( 4 - 3 p _ { 1 1 } ) - ( 4 - 3 p _ { 3 1 } ) / x ^ { 2 } ] \} + \displaystyle \frac { 1 } { T _ { H } } \{ - \displaystyle \frac { 1 } { x ^ { 2 } } ( 4 - 3 p _ { 3 1 } ) \log x \} } } \\ { { \ln x + \alpha \tau + \mu [ ( 4 - 3 p _ { 1 1 } ) - ( 4 - 3 p _ { 3 1 } ) / x ^ { 2 } ] \} + 3 [ \displaystyle \frac { k m L _ { 1 } ^ { 2 } } { \pi ^ { 2 } \eta _ { 1 } ^ { 2 } } \ln p _ { 3 1 } + \displaystyle \frac { 1 } { 2 T _ { H } x ^ { 2 } } ( 1 - p _ { 3 1 } ) ] - 3 [ \displaystyle \frac { k m L _ { 1 } ^ { 2 } } { \pi ^ { 2 } \eta _ { 1 } ^ { 2 } } \ln p _ { 2 1 } } } \\ { { + \displaystyle \frac { 1 } { 2 T _ { L } x ^ { 2 } } ( 1 - p _ { 2 1 } ) ] + 3 [ \displaystyle \frac { k m L _ { 1 } ^ { 2 } } { \pi ^ { 2 } \eta _ { 1 } ^ { 2 } } \ln p _ { 1 1 } + \displaystyle \frac { 1 } { 2 T _ { L } x ^ { 2 } } ( 1 - p _ { 1 1 } ) - 3 [ \displaystyle \frac { k m L _ { 1 } ^ { 2 } } { \pi ^ { 2 } \eta _ { 1 } ^ { 2 } } \ln p _ { 4 1 } + \displaystyle \frac { 1 } { 2 T _ { H } x ^ { 2 } } ( 1 - p _ { 4 1 } ) ] } } \end{array}
$$

烟输出率为：

$$
\frac { A } { \tau } = \frac { 1 } { \tau } [ ( \frac { T _ { 0 } } { T _ { L } } - 1 ) Q _ { L } + ( \frac { T _ { 0 } } { T _ { H } } - 1 ) Q _ { H } ] = \frac { 1 } { \tau } \{ ( \frac { T _ { 0 } } { T _ { L } } - 1 ) \frac { \pi ^ { 2 } \eta ^ { 2 } } { m L _ { 1 } ^ { 2 } } \{ ( 4 - 3 p _ { 1 1 } ) \ln x - \alpha \tau - \mu [ ( 4 - 3 p _ { 1 1 } ) - 1 ] \ln x \} \} .
$$

$$
( 4 - 3 p _ { 3 1 } ) / x ^ { 2 } ] \} + ( { \frac { T _ { 0 } } { T _ { H } } } - 1 ) { \frac { \pi ^ { 2 } \eta ^ { 2 } } { m L _ { 1 } ^ { 2 } } } \{ - { \frac { 1 } { x ^ { 2 } } } ( 4 - 3 p _ { 3 1 } ) \ln x + \alpha \tau + \mu [ ( 4 - 3 p _ { 1 1 } ) - ( 4 - 3 p _ { 3 1 } ) / x ^ { 2 } ] \} \}
$$

生态学目标函数[31-33]为：

$$
\begin{array} { l } { { \widetilde { c } = \displaystyle { \frac { A } { \tau } - \widetilde { c } T _ { 1 } } - \widetilde { c } \displaystyle { \frac { ( T _ { 0 } ^ { T } - 1 ) } { \tau } \frac { \widetilde { \pi } ^ { 2 } } { T _ { i } } \displaystyle { \frac { 1 } { m _ { L } ^ { 2 } } \frac { 1 } { 1 } } \left\{ ( 4 - 3 p _ { 1 } ) \ln x - \alpha \tau - \mu [ ( 4 - 3 p _ { 1 } ) - ( 4 - 3 p _ { 1 } ) / x ^ { 2 } ] + ( \frac { T _ { 0 } } { T _ { R } } - 1 ) \ln x - \alpha \tau - \mu [ ( 4 - 3 p _ { 1 } ) / x ^ { 2 } ] \right\} } , } } \\  { \displaystyle { \frac { \tau ^ { 2 } \eta ^ { 2 } } { m _ { L } ^ { 2 } } \displaystyle { \frac { 1 } { \tau } - \frac { 1 } { x ^ { 2 } } ( 4 - 3 p _ { 3 } ) \ln x + \alpha \tau + \mu [ ( 4 - 3 p _ { 1 } ) - ( 4 - 3 p _ { 1 } ) / x ^ { 2 } ] \} } - \frac { T _ { 0 } } { \tau } \displaystyle { \frac { \pi ^ { 2 } \eta ^ { 2 } } { m _ { L } ^ { 2 } } \displaystyle { \frac { 1 } { T _ { L } } \left\{ 4 - 3 p _ { 1 } \right\} } \ln x } } } \\  { \displaystyle { \varepsilon \tau - \mu [ ( 4 - 3 p _ { 1 } ) - ( 4 - 3 p _ { 1 } ) / x ^ { 2 } ] \} + \frac { 1 } { T _ { R } } \left\{ - \frac { 1 } { x ^ { 2 } } ( 4 - 3 p _ { 3 } ) \ln x + \alpha \tau + \mu [ ( 4 - 3 p _ { 1 } ) - ( 4 - 3 p _ { 3 } ) / x ^ { 2 } ] \right\} } } \\   \displaystyle { x ^ { 2 } \} \rceil + 3 \frac { 1 } { \pi ^ { 2 } \eta _ { L } ^ { 2 } } \ln p _ { s _ { 1 } } + \frac { 1 } { 2 T _ { a } x ^ { 2 } } ( 1 - p _ { s _ { 1 } } ) ] - 3 \frac { k m \widetilde { L } } { \tau ^ { 2 } \eta _ { L } ^ { 2 } } \ln p _ { z _ { 1 } } + \frac { 1 } { 2 T _ { L } x ^ { 2 } } ( 1 - p _ { z _ { 1 } } ) + 3 \frac { 1 } { \pi ^ { 2 } \eta _ { L } ^ { 2 } } \ln p _ { z _ { 1 } } + } \\  { \displaystyle { \frac { 1 } { T _ { s } } } ^ { 2 } ( 1 - p _ { 1 } ) - 3 \frac { 1 } { \tau ^ { 2 } \eta _ { S } } \ln \frac { 2 } { \tau ^ { 2 } } ( 1 - p _ { 1 } ) } \end{array}
$$

令 $E ^ { * } = E m L _ { 1 } ^ { 2 } / ( \pi ^ { 2 } \mathrm { h } ^ { 2 } )$ 为无量纲生态学目标函数。由式(27),(28)和(31)可知，对于给定的 $T _ { H } , T _ { L } , T _ { 0 } , L _ { I } ,$ 1 $U , \stackrel { - } { \nu } , \alpha , \mu , C = \pi ^ { 2 } \mathrm { h } ^ { 2 } / ( m L _ { 1 } ^ { 2 } )$ ,制冷机的制冷率、COP和生态学目标函数都是势阱宽度比 $x$ 的函数。图2给出了非理想回热因子 $\mu$ 取不同的值时，性能系数随$x$ 的变化关系。计算中取 $\mathrm { T } _ { L } { = } 2 0 0 \mathrm { K } , \mathrm { T } _ { 0 } { = } 3 0 0 \mathrm { K }$ $\mathrm { M } \mathrm { = } 1 5 , M = 1 5 , 2 / ( L _ { 1 } ^ { - } \bar { \nu } ) = 1 , \alpha = 0 . 0 1 , C / k = 3 0 0 ,$ 0由图可知，制冷机的性能系数随势阱宽度比 $x$ 的增加而减小。随着非理想回热因子u的增加，COP减小。图3给出了 $\scriptstyle \mu = 0 . 0 1$ ， $\alpha$ 取不同的值时，COP 随 $x$ 的变化关系。计算中参数取值与图2相同。从图可知，

COP随着 $\alpha$ 的增加而减小。图4给出了制冷率随 $x$ 的变化关系，计算中 $\scriptstyle \alpha = 0 . 1$ ， $\mu$ 取不同的数值，其他参数的取值与图2相同。从图可知，制冷率随 $x$ 的变化关系为类抛物线关系，由极值条件 $\partial R / \partial x = 0$ 得：

$$
[ \frac { 2 L _ { 1 } } { \stackrel { . . } { \nu } } ( x - 1 ) + \frac { 2 } { M } ( T _ { _ { H } } - T _ { _ { L } } ) ] \{ \frac { 4 - 3 p _ { 1 1 } } { x } - \frac { 2 \alpha L _ { 1 } } { \stackrel { . . } { \nu } } - \frac { 2 \mu } { x ^ { 3 } } [ ( 4 - 3 p _ { 3 1 } ) + 3 p _ { 3 1 } ^ { 2 } \frac { m L _ { 1 } ^ { 2 } } { \pi ^ { 2 } \mathrm { h } ^ { 2 } } \frac { 1 } { k T _ { _ { L } } x ^ { 2 } } ] \}
$$

$$
- \frac { 2 L _ { 1 } } { \nu } \{ ( 4 - 3 p _ { 1 1 } ) \ln x - \alpha \tau - \mu [ ( 4 - 3 p _ { 1 1 } ) - \frac { 1 } { x ^ { 2 } } ( 4 - 3 p _ { 3 1 } ) ] \} = 0
$$

式(36)给出了制冷率与势阱宽度比 $x$ 间优化关系。图5给出了 $\scriptstyle \mu = 0 . 0 1$ ， $\alpha$ 取不同的数值时，制冷率随 $x$ 的变化关系，制冷率随着热漏的增大而降低。

图6给出了无量纲生态学目标函数与制冷率之间的优化关系 $\left( E ^ { * } - R \right)$ 。从图可知， ${ \boldsymbol { E } } ^ { * } { \boldsymbol { R } }$ 优化关系曲线为扭叶型，存在着一个生态学目标函数的极大值点与一个制冷率的极大值点，且每一个生态学目标函数值(除极大值点外)对应两个制冷率取值，显然要取对应的制冷率较大的状态点。热漏不改变曲线的类型，但随着热漏的增加，生态学目标函数值和制冷率都变小，在生态学目标函数取值较小时，热漏对其影响较小，在生态学目标函数取值较大时，热漏对其影响较大。图7给出了 $\mu$ 对 ${ \boldsymbol { E } } ^ { * } { \boldsymbol { R } }$ 关系曲线的影响，比较图6和7可知，热漏对 $\boldsymbol { E } ^ { * } { - } \boldsymbol { R }$ 关系的影响比非理想回热因子的影响大，即热漏是比非理想回热更重要的不可逆因素。

![](images/8306eb28b1fb6cc0b724f65a5a01fd63cd939d7c3a6facbd219c731638d86148.jpg)  
图 $2 \mu$ 对COP与势阱宽度比的关系的影响， Figure 2.Effects of $\mu$ on COP with the ratio of potential well width.

![](images/6f3971cd4c461a0503f433a676b950b7ed59f75b9ccd4a9c517223a847d88943.jpg)  
图 $3 \mathrm { \ : d }$ 对COP与势阱宽度比的关系的影响， Figure 3.Effects of $\alpha$ on COP with the ratio of potential well width.

![](images/6537ed63cbb7b806b607d07b33cd65195c64f0fe54e7affa97dafb4dba7194d7.jpg)  
图4.u对致冷率与势阱宽度比关系的影响 Figure 4.Effects of $\mu$ on cooling rate $( R )$ with the ratio of potential well width

# 5结论

本文建立了以无数个无限深势阱中的粒子为工质的不可逆量子斯特林致冷循环模型。基于薛定谔方程的求解分析了该不可逆量子斯特林制冷机的性能，给出了性能系数、致冷率、熵产率和生态学目标函数，分析了热漏系数与不完全回热因子对性能系数、致冷率以及生态学函数的影响。制冷率与生

![](images/1c146721eab6cf2e48a74c701de0b77bc9bcf063fb1cada8c887b60618c55bc0.jpg)  
图 $5 \alpha$ 对致冷率与势阱宽度比的关系的影响， Figure 5.Effects of $\alpha$ on cooling rate versus the ratio of potential well width .

![](images/41b48238cd4d7b4ece44d69beb3763b4f944a711615bcba12d23d6f1ab456447.jpg)  
图 $6 \mathrm { { a } }$ 对致冷率与无量纲生态学函数关系的影响.

![](images/12b669a447a4da617fbe783aad2d0a0f08f08dfb667d93a156e4f693db554d9c.jpg)  
Figure 6.Effects of $\alpha$ on cooling rate versus dimensionless ecological objective function.   
图 $7 \mu$ 对致冷率与无量纲生态学函数关系的影响.

Figure 7.Effects of $\mu$ on cooling rate versus dimensionless ecological objective function.

制冷率与生态学函数的关系曲线是回原点的扭叶型。存在着一个生态学目标函数极大值与一个制冷率的极大值。这两个极大值之间区域是该制冷机的最优运行区间。本文结果有助于加深对以无限深势阱中粒子为工质的不可逆量子斯特林制冷循环性能的理解。

# 参考文献

[1] WU Feng，CHEN Lingen，SUN Fengrui，et al Performance Characteristicsof a Magnetic Stirling Cooler[J]. International Journal of Energy Research, 2002, 26(3): 217-228.   
[2] WU Feng,CHENLingen,Wu Chi, et al .Optimization of Irreversible Magnetic Stirling Cryocoolers[J]. International Journal of Engineering Science,2001,39(4): 361-368.   
[3] WU Feng，CHEN Lingen， SUN Fengrui. Finite-time Exergoeconomic Performance Bound for a Quantum Stirling Engine[J]. International Journal of Engineering Science,2000,38(2): 239-247.   
[4] Vroylandt H,Bonfils A,Verley G.Eficiency Fluctuations of Small Machines with Unknown Losses[J].Physical Review E,2016,93(5): 052123   
[5] Curzon FL,Ahlborn B.Efficiency of a Carnot Engine at Maximum Power Output[J]. American Journal of Physics, 1975,43(1): 22-24.   
[6] Andresen B,Salamon P,Berry R S. Thermodynamics in Finite Time[J].Physics Today,1984 (Sept.): 62-70.   
[7] CHEN Lingen，WU Chi，SUN Fengrui.Finite Time Thermodynamic Optimization or Entropy Generation MinimizationofEnergySystems[J].Journalof Non-Equilibrium Thermodynamics,1999,24(4): 327-359.   
[8] HoffmanKH,BurzlerJ,FischerA,etal.Optimal Process PathsforEndoreversibleSystems[J].Journalof Non-Equilibrium Thermodynamics,2003,28(3): 233-268.   
[9] CHEN Lingen，SUN Fengrui. Advances in Finite Time Thermodynamics: Analysis and Optimization[M].New York: Nova Science Publishers,2004.   
[10]陈林根．不可逆过程和循环的有限时间热力学分析[M]. 北京：高等教育出版社,2005. CHEN Lingen.Finite Time Thermodynamics Analysis for Irreversible Processes and Cycles[M]. Beijing: Higher Education Press,2005.   
[11] Andresen B. Current Trends in Finite-time Thermodynamics[J]. Angewandte Chemie International Edition,2011,50(12): 2690-2704.   
[12] CHENLingen，MENGFankai, SUN Fengrui. ThermodynamicAnalyses andOptimizations for Thermoelectric Devices: the State of the Arts[J].Science China: Technological Sciences， 2016, 2016, 59(3): 442-455.   
[13] 陈林根，夏少军．不可逆过程的广义热力学动态优化 [M]．北京：科学出版社,2016. CHEN Lingen, XIA Shaojun. Generalized Thermodynamic Dynamic-Optimization for Ireversible Processs. Beijing: Science Press,2016.   
[14] 陈林根，夏少军．不可逆循环的广义热力学动态优化 [M]．北京：科学出版社,2016. CHENLingen,XIA Shaojun. Generalized Thermodynamic Dynamic-Optimization for Irreversible Cycles. Beijing: Science Press,2016.   
[15] Kosloff R. Quantum Thermodynamics:A Dynamical Viewpoit J].Entropy,2013,15(6): 2100-2128.   
[16] YIN Yong,CHEN Lingen,WU Feng. Optimal Power and Efficiency of Quantum Stirling Heat Engines[J].European Physical Journal Plus,2017,132:45.   
[17]吴锋.斯特林机的有限时间热力学研究[D].博士学位论 文，武汉：海军工程学院，1998. WU Feng.Finite Time Thermodynamics Research for Stirling Engine[D].Doctorial Dissertations,WuHan:Naval Engineering College,1998.   
[18]吴锋，陈林根，孙丰瑞，等.斯特林机的有限时间热力学 优化[M].北京：化学工业出版社，2008. WU Feng, CHEN Lingen, SUN Fengrui, et al. Finite Time Thermodynamic Optimization for Stirling Engine[M]. BeiJing: Chemical Industry Press,2008.   
[19] Kosloff R.A Quantum Mechanical Open System as a Model of a Heat Engine[J]. Journal of Chemical Physics, 1984,80(4): 1625-1631.   
[20]Geva E,Kosloff R.On the Classical Limit of Quantum Thermodynamics in Finite Time[J]. Journal of Chemical Physics,1992,97(5):4398-4412.   
[21] 吴锋，孙丰瑞，陈林根．活塞式量子Stirling发动机最优 性能[J]．电站系统工程，1996,12(1):41-43. WU Feng， SUN Fengrui， CHEN Lingen. Optimum Performance of a Piston Quantum Stirling Engine[J].Power System Engineering,1996,12(1):41-43.   
[22]WU Feng，YANG Zhichun,CHEN Lingen，et al.Work Output and Efficiency of a Reversible Quantum Otto Cycle[J]. Thermal Science,2010,14(4): 879-886.   
[23]吴锋，汪拓，陈林根，等.量子斯特林热机的输出功和 热效率[J].机械工程学报，2014,50(4):150-154. WU Feng,WANG Tuo, CHEN Lingen, et al. Work Output and Efficiency of Quantum Stirling Engine[J].Journal of Mechanical Engineering,2014,50(4):150-154.   
[24] 王建辉，熊双泉，何济洲，等.以一维谐振子势阱中的单 粒子为工质的量子热机性能分析[J]．物理学报， 2012,61(8): 080509. WANG Jinhui,XIONG Shuangquan，HE Jizhou,et al. Performance Analysis of a Quantum Heat Engine Working with a Particle in a One-dimensional Harmonic Trap[J]. Acta Physica Sinica,2012,61(8):080509.   
[25] CorreaL A,Palao JP,Alonso D.Internal Dissipation and Heat Leaks in Quantum Thermodynamic Cycles[J]. Physical ReviewE,2015,92(3): 032136.   
[26] 金晓昌，吴锋，孙丰瑞，等.经典极限下量子卡诺热机火 用经济最优性能[J]．电站系统工程，1996,12(6)：42-45. JIN Xiaochang,WU Feng, SUN Fengrui, et al. Optimum Exergoeconomic Performance of Quantum Carnot Heat Engine Under the Classical Limit[J].PowerSystem Engineering,1996,12(6):42-45.   
[27]Feldmann T,Kosloff R.Performance of Discrete Heat Engines and Heat Pumps in Finite Time[J].Physical Review E,2000,61(5): 4774-4790.   
[28] 吴锋，孙丰瑞．不可逆量子斯特林制冷机的最大制冷率 [J]．应用科学学报，1997,15(2)：223-228. WU Feng, SUN Fengrui. Maximum Cooling Rate of a Irreversible Quantum Stirling refrigerator[J].Journal of Applied Science,1997,15(2):223-228.   
[29] 金晓昌．量子斯特林制冷机火用经济优化准则[J].武汉 化工学院学报，1997,19(3)：85-88. JIN Xiaochang. Exergoeconomic Optimum Criterion of Quantum Stirling refrigerator[J].Journal of Wuhan institute of Chemical Technology,1997,19(3):85-88.   
[30]Acikkalp E,Caner N.Application of Exergetic Sustainable Index to the Quantum Irreversible Diesel Refrigerator Cycles for 1D Box System[J].The European Physical Journal Plus,2015,130: 73.   
[31] Angulo-Brown F.An Ecological Optimization Criterion for Finite-Time Heat Engines [J]． Journal of Applied Physics,1991,69(11): 7465-7469.   
[32] Yan Z. Comment on“Ecological Optimization Criterion for Finite-Time Heat Engines”[J].Journal of Applied Physics,1993,73(7): 3583.   
[33]陈林根，孙丰瑞，陈文振．热力循环的生态学品质因素 [J]．热能动力工程,1994,9(6):374-376. CHEN Lingen，SUN Fengrui，CHEN Wenzheng. The EcologicalQualityFactor for Thermodynamic Cycles[J].Journal of Engineering for Thermal Energy and Power,1994,9(6): 374-376.

附：

联系人：陈林根教授  
地址：430033 武汉 海军工程大学 动力工程学院手机号码：13871164396  
邮箱：lingenchen @hotmail.com, lgchenna@yahoo.com