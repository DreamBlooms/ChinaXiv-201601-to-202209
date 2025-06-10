# 基于最优阻尼注入的Buck变换器无源控制研究

崔健 王久和

（北京信息科技大学自动化学院北京100192）

![](images/a5f27f7d78042035d05d3fd63237138d2a984a51952e70f83cfca29d3c550d00.jpg)

崔健男1993年生，硕士研究生，主要从事电能变换器系统稳定性方面的研究工作。

摘要：针对目前Buck变换器无源控制器中确定的阻尼注入DI不能使变换器获得好的控制性能的问题，本文提出了一种计算并优化DI的方法。首先，建立了无源控制器控制的Buck变换器系统传递函数，在阶跃输入情况下求系统的输出电流响应及其超调量，通过校正系统电流响应的超调量，最终确定DI的取值范围。在所确定的DI取值范围内，使用遗传算法对DI进行优化，求得最优DI。基于最优DI的无源控制器，可使Buck变换器具有优秀的性能。计算机仿真结果表明，本文提出的基于最优DI的无源控制策略是可行的。

关键词：Buck变换器 无源控制最优阻尼注入遗传算法中图分类号：TM463

# Study of Passivity-Based Control of Buck Converter Based on Optimal Damping Injection

CuiJianWangJuihe （Beijing Information Science & Technology UniversityBeijing100192 China )

![](images/3fc4d640f04f22855810ca2702d710e9cbdc57dacc421933b21f3fcd75b20172.jpg)

王久和男 1959年生，教授，博士生导师主要从事电能变换器非线性控制、电能质量控制及微电网等方面的研究工作。

Abstract: Presently, the damping injection of passivity-based controller of Buck converter can't make converter acquire excellent performance.Aiming at this problem,an approach is proposed which can be used to calculate and optimize damping injection in the paper. Firstly,the transfer function of the Buck converter system based on passivitybased controller is established, the output current and its overshoot of the system is found when input is step,and finally the range of value of the damping injection is decided by correcting overshoot of the output current response. The damping injection is optimized by using genetic algorithm and the optimal damping injection is obtained.The Buck converter can get excellent performance due to passivity-based controller based on optimal damping injection.The simulation results prove the feasibility of the passivity-based control based on optimal damping injection proposed in this paper.

Keywords: Buck converter, passivity-based control, optimal damping injection, genetic algorithm

# 1 引言

随着新能源以及分布式电源的发展，DC/DC变换器被广泛地应用到各种需要升降压的场所。由于DC/DC变换器具有非线性特性，传统的基于小信号处理的线性控制存在较大的局限性[1-2]。为此，越来越多的非线性控制方法被提了出来，如反馈线性化控制、滑模变结构控制、自抗扰控制以及无源控制(Passivity-BasedControl，PBC）等。反馈线性化控制需要全状态可测量、精确抵消动态、引入控制器奇异性，对参数的依赖性大，控制复杂；滑模变结构控制存在抖动问题；自抗扰控制需要一组满意的非线性函数以及相应的参数，计算量大，导致控制周期长，实时性差[3]。以上方法均不能对变换器实现本质上的非线性控制。而PBC理论基于能量的角度，通过阻尼注入达到非线性控制的目的，是一种本质上的非线性控制方法，具有控制简单、响应快、无超调等优点。因此，PBC理论在电能变换器控制中得到了日益广泛的应用，如文献[4-5]针对Buck等DC/DC变换器设计了无源控制器，通过阻尼注入（DampingInjection，DI）使得DC/DC变换器能够稳定运行，并取得了良好的控制效果。

但目前对于DI的确定尚无较好的方法。一般情况下可通过试凑法确定DI，但该方法效率差，且不能确定最优DI。文献[4]通过劳斯-赫尔维茨稳定判据约束DI的取值范围，通过求解不等式取得DI的取值范围，虽然相对简单，但对于一般情况下的变换器系统，如Buck变换器系统，其自身即可稳定运行，劳斯-赫尔维茨稳定判据对其不再有约束作用，所以该方法不再适用。

基于此，本文以Buck变换器为例，提出了通过校正系统的超调量，以约束DI的取值范围的方法，并通过遗传算法（GeneticAlgorithm，GA）优化求得最优DI值。DI不但可以提升变换器的性能，还可以抑制变换器电流响应的超调量，从而减小了冲击电流对系统的不利影响。计算机仿真结果证明了基于最优DI的无源控制策略的可行性。

# 2 Buck变换器的EL模型及控制器设计

# 2.1Buck变换器的EL模型

Buck变换器的主电路如图1所示。图中，VT为开关管；VD为二极管； $i _ { \scriptscriptstyle L }$ 为流过电感器的电流；$u _ { c }$ 为电容器两端电压； $d$ 为开关管VT驱动信号的占空比； $R$ 为负载； $L$ 为电感器的电感； $C$ 为电容器的电容； $U _ { \mathrm { s } }$ 为电源输入电压。

![](images/00e03d9753f66fee256be13151a90e4666743ff090b68682a70bd817c22fa3af.jpg)  
图1Buck 变换器主电路图  
Fig.1The main power circuit diagram of Buck converter

为简化模型建立，假设电路中的元器件均为理想元器件。选择电感电流 $i _ { \scriptscriptstyle L }$ 的开关周期平均值 $i _ { L \mathrm { a v } }$ 和电容电压 $u _ { c }$ 的开关周期平均值 $u _ { \mathrm { { \tiny ~ C a v } } }$ 作为状态变量，由图1可得Buck变换器的数学模型为

$$
\left\{ \begin{array} { l l } { L \displaystyle \frac { \mathrm { d } i _ { L \mathrm { a v } } } { \mathrm { d } t } = d U _ { \mathrm { s } } - u _ { C \mathrm { a v } } } \\ { C \displaystyle \frac { \mathrm { d } u _ { C \mathrm { a v } } } { \mathrm { d } t } = i _ { L \mathrm { a v } } - \displaystyle \frac { u _ { C \mathrm { a v } } } { R } } \end{array} \right.
$$

在连续导通模式（ContinuousConductionMode,CCM）下，令 $x _ { 1 } = i _ { \mathrm { } _ { L \mathrm { { a v } } } } , ~ x _ { 2 } = u _ { \mathrm { } _ { C a v } }$ ，则根据Buck 变换器的数学模型，有

$$
\left\{ \begin{array} { l l } { \displaystyle { \dot { x } } _ { 1 } = - \frac { 1 } { L } x _ { \scriptscriptstyle 2 } + \frac { U _ { \mathrm { s } } } { L } d } \\ { \displaystyle { \dot { x } } _ { 2 } = \frac { 1 } { C } x _ { \scriptscriptstyle 1 } - \frac { 1 } { R C } x _ { \scriptscriptstyle 2 } } \end{array} \right.
$$

将式（2）表示为矩阵形式，可得Buck变换器的EL 模型为

$$
M _ { \mathrm { B u } } { \dot { \boldsymbol { x } } } + J _ { \mathrm { B u } } { \boldsymbol { x } } + R _ { \mathrm { B u } } { \boldsymbol { x } } = d { \pmb { u } }
$$

其中， $M _ { \mathrm { B u } } = \left( \begin{array} { c c } { { L } } & { { 0 } } \\ { { 0 } } & { { C } } \end{array} \right) ; J _ { \mathrm { B u } } = \left( \begin{array} { c c } { { 0 } } & { { 1 } } \\ { { - 1 } } & { { 0 } } \end{array} \right)$ $J _ { \mathrm { B u } }$ 为反对称矩阵，满足 $\boldsymbol { J _ { \mathrm { B u } } } = - \boldsymbol { J } _ { \mathrm { B u } } ^ { \mathrm { T } }$ $\begin{array} { r } { J _ { \mathrm { B u } } ^ { \mathrm { T } } ; R _ { \mathrm { B u } } = \left( \begin{array} { c c } { 0 } & { 0 } \\ { 0 } & { 1 / R } \end{array} \right) ; x = } \end{array}$ $\left( { x _ { 1 } \atop x _ { 2 } } \right) , \quad \pmb { u = } \left( { U _ { \mathrm { s } } \atop 0 } \right) ,$

首先分析带电阻负载Buck变换器的无源性。图1中，假设电路中电源侧端口电压为 $u$ ，电流为$i$ ，不难得出 $i = d i _ { L \mathrm { a v } }$ 。

将式（1）中第一个方程左右两边同乘以 $i _ { L \mathrm { a v } }$ 第二个方程左右两边同乘以 $u _ { \mathrm { { C a v } } }$ ，则有

$$
\left\{ \begin{array} { l } { \displaystyle { L i _ { L \mathrm { a v } } \frac { \mathrm { d } i _ { L \mathrm { a v } } } { \mathrm { d } t } = d i _ { L \mathrm { a v } } U _ { \mathrm { s } } - i _ { L \mathrm { a v } } u _ { C \mathrm { a v } } } } \\ { \displaystyle C u _ { C \mathrm { a v } } \frac { \mathrm { d } u _ { C \mathrm { a v } } } { \mathrm { d } t } = i _ { L \mathrm { a v } } u _ { C \mathrm { a v } } - \frac { u _ { C \mathrm { a v } } ^ { 2 } } { R } } \end{array} \right.
$$

联立并代入 $i = d i _ { L \mathrm { a v } }$ ，可得

$$
L i _ { L \mathrm { a v } } \frac { \mathrm { d } i _ { L \mathrm { a v } } } { \mathrm { d } t } { + } C u _ { C \mathrm { a v } } \frac { \mathrm { d } u _ { C \mathrm { a v } } } { \mathrm { d } t } { = } i U _ { \mathrm { s } } { - } \frac { u _ { C \mathrm { a v } } ^ { 2 } } { R }
$$

对式（5）两侧同时积分，有

$$
\begin{array} { r l } & { \int _ { \mathrm { 0 } } ^ { t } L i _ { \mathrm { L a v } } ( \tau ) \mathrm { d } i _ { \mathrm { L a v } } ( \tau ) + \int _ { \mathrm { 0 } } ^ { t } C u _ { \mathrm { C a v } } ( \tau ) \mathrm { d } u _ { \mathrm { C a v } } ( \tau ) = } \\ & { \int _ { \mathrm { 0 } } ^ { t } i ( \tau ) U _ { \mathrm { s } } \mathrm { d } \tau - \int _ { \mathrm { 0 } } ^ { t } \frac { u _ { \mathrm { C a v } } ^ { 2 } ( \tau ) } { R } \mathrm { d } \tau } \end{array}
$$

整理式 (6)，可得

$$
\underbrace { \frac { 1 } { 2 } L i _ { L \mathrm { a v } } ( \tau ) ^ { 2 } } _ { H _ { L } ( t ) } \underbrace { + \frac { 1 } { 2 } C u _ { C \mathrm { a v } } ( \tau ) ^ { 2 } \Big | _ { 0 } ^ { t } } _ { H _ { C } ( t ) } = \underbrace { \int _ { 0 } ^ { t } i ( \tau ) U _ { \mathrm { s } } \mathrm { d } \tau } _ { \{ \mathrm { i f f } \underset { \mathrm { s f r a p } } { \mathrm { \underbrace { \large ~ \hat { a } ~ \hat { r } ~ a c k } } } }  - \underbrace { \int _ { 0 } ^ { t } \frac { u _ { C \mathrm { a v } } ^ { 2 } ( \tau ) } { R } \mathrm { d } \tau } _ { \mathrm { \normalfont \hat { t } f i f f e r s t } }
$$

式（7）可改写为

$$
\begin{array}{c} \underbrace { H ( t ) } _ { t \parallel \mathbf { \hat { x } } \parallel _ { \mathrm { H E } } ^ { ( \pm ) } } = \underbrace { H ( 0 ) } _ { \mathbf { \hat { y } } \mathbf { \hat { z } } \mathbf { \hat { z } } \mathbf { \hat { z } } \mathbf { \hat { z } } } + \underbrace { \int _ { 0 } ^ { t } i ( \tau ) U _ { \mathrm { s } } \mathrm { d } \tau } _ { \mathbf { \hat { y } } \mathbf { \hat { z } } \mathbf { \hat { z } } \mathbf { \hat { z } } \mathbf { \hat { z } } \mathbf { \hat { z } } } - \underbrace { \int _ { 0 } ^ { t } \frac { u _ { C \mathrm { a v } } ^ { 2 } \left( \tau \right) } { R } \mathrm { d } \tau } _ { \mathbf { \hat { z } } \mathbf { \hat { z } } \mathbf { \hat { z } } \mathbf { \hat { z } } \mathbf { \hat { z } } \mathbf { \hat { z } } }  \end{array}
$$

式中， $H ( t ) = H _ { L } ( t ) + H _ { C } ( t )$ ，为 $\mathbf { \chi } _ { t }$ 时刻电路中存储的能量。

由无源性的定义[可知，若 $R > 0$ ，则带电阻负载的Buck变换器无源，可稳定运行。

# 2.2基于EL模型的无源控制器

设期望的状态矢量为 $\boldsymbol { x } ^ { * } = \left[ x _ { 1 } ^ { * } x _ { 2 } ^ { * } \right] ^ { \mathrm { T } }$ ，状态矢量误差 $e = x - x ^ { * }$ 。其中 $\boldsymbol { x } _ { 2 } ^ { * }$ 由负载需求确定。当Buck变换器工作于平衡点时，有 ${ x _ { 1 } ^ { * } } \mathrm { = } { x _ { 2 } ^ { * } } / R$ 。

由式（3）可得

$$
M _ { \mathrm { B u } } { \dot { e } } + J _ { \mathrm { B u } } e + R _ { \mathrm { B u } } e = d { \boldsymbol { u } } - [ M _ { \mathrm { B u } } { \dot { \boldsymbol { x } } } ^ { * } + J _ { \mathrm { B u } } { \boldsymbol { x } } ^ { * } + R _ { \mathrm { B u } } { \boldsymbol { x } } ^ { * } ]
$$

取误差能量存储函数 $H _ { \mathrm { e } } \left( x \right) = \frac { 1 } { 2 } e ^ { \mathrm { T } } M _ { \mathrm { B u } } \pmb { e }$ ，为使$H _ { \mathrm { e } } ( { \pmb x } )$ 快速收敛到0，现加入DI项。在式（9）两端同时添加DI项 $R _ { \mathrm { a } } e$ ，其中 $\pmb { R } _ { \mathrm { a } }$ 为

$$
R _ { \mathrm { a } } = \left( \begin{array} { c c } { { R _ { \mathrm { a 1 } } } } & { { 0 } } \\ { { 0 } } & { { 1 / R _ { \mathrm { a 2 } } } } \end{array} \right) R _ { \mathrm { a } i } > 0 ( i = 1 , 2 )
$$

则有

$$
\begin{array} { r l } & { M _ { \mathrm { B u } } \dot { e } + J _ { \mathrm { B u } } e + R _ { \mathrm { B u } } e + R _ { \mathrm { a } } e = } \\ & { d \pmb { u } - [ M _ { \mathrm { B u } } \dot { \pmb { x } } ^ { \ast } + J _ { \mathrm { B u } } \pmb { x } ^ { \ast } + R _ { \mathrm { B u } } \pmb { x } ^ { \ast } ] + R _ { \mathrm { a } } e } \end{array}
$$

取无源控制器

$$
d { \pmb u } = [ { \pmb M } _ { \mathrm { B u } } \dot { \pmb x } ^ { \ast } + { \pmb J } _ { \mathrm { B u } } { \pmb x } ^ { \ast } + { \pmb R } _ { \mathrm { B u } } { \pmb x } ^ { \ast } ] - { \pmb R } _ { \mathrm { a } } e
$$

即式（11）右边为零，可得

$$
M _ { \mathrm { B u } } { \dot { e } } + ( J _ { \mathrm { B u } } + R _ { \mathrm { B u } } + R _ { \mathrm { a } } ) e = 0
$$

$H _ { \mathrm { e } } ( \mathbf { x } )$ 对时间的导数为

$$
\begin{array} { r l } & { \dot { H } _ { \mathrm { e } } \left( x \right) = e ^ { \mathrm { T } } M _ { \mathrm { B u } } \dot { e } = - e ^ { \mathrm { T } } \left( J _ { \mathrm { B u } } + R _ { \mathrm { B u } } + R _ { \mathrm { a } } \right) e } \\ & { \qquad = - e ^ { \mathrm { T } } \left( R _ { \mathrm { B u } } + R _ { \mathrm { a } } \right) e < 0 } \end{array}
$$

由式（14）可知，误差能量存储函数能够收敛到0，收敛速度取决于 $R _ { \mathrm { B u } } + R _ { \mathrm { a } }$ 。当 $R _ { \mathrm { a } } \gg R _ { \mathrm { B u } }$ 时，$H _ { \mathrm { e } } ( { \pmb x } )  0$ 的速度取决于 ${ \pmb R } _ { \mathrm { a } }$ ， $R _ { \mathrm { B u } }$ 的影响很小。当$H _ { \mathrm { e } } ( { \pmb x } )  0$ 时，即 $x \to x ^ { * }$ ，所以式（12）无源控制器可实现控制目的。

由于 $x ^ { * }$ 为给定常量，故 $\stackrel { \cdot } { x } ^ { * } = 0$ 。将式（12）展开后，可得无源控制器对应的占空比为

$$
d = \frac { x _ { 2 } ^ { * } } { U _ { \mathrm { s } } } + \frac { R _ { \mathrm { a l } } } { U _ { \mathrm { s } } } ( x _ { 1 } ^ { * } - x _ { 1 } )
$$

由式（15）可得基于无源控制的Buck变换器系统结构如图2所示。其中， ${ i _ { L } } ^ { * }$ 为电感器电流给定值； $u _ { c } ^ { * }$ 为电容器两端电压给定值。无源控制器以 $i _ { \scriptscriptstyle L }$ ，$i _ { L } ^ { * }$ 以及 $u _ { c } ^ { * }$ 为输入信号，经过简单的代数运算后输出占空比 $d$ ，占空比 $d$ 与三角波比较产生PWM波，PWM波经驱动电路驱动开关管，实现控制目的。无源控制器控制简单，且可实现输出电压无超调控制。

![](images/118db78f03e650b39477086e57af225725b975242b9e0da37024e8930e68b032.jpg)  
图2基于无源控制的Buck变换器系统结构图 Fig.2Configuration of Buck converter based on passivity control

由于DI不消耗能量，因此式（13）对于含有DI的闭环控制系统仍然成立，所以带电阻负载的Buck变换器系统在所设计的无源控制器的控制下可稳定运行。

# 3 DI确定

# 3.1 DI范围确定

由式（15）可知，无源控制器控制电感器电流，当电感器电流达到给定值即电路工作于平衡点时，由Buck变换器工作于平衡点时电容器电压与电感器电流的关系可知电容器两端电压也可达到给定值，即无源控制器通过控制电感器电流从而使得电容器电压达到给定值。在该控制器控制下，变换器输出电压无超调，响应快。但当电路开始工作时会出现冲击电流，对电路产生不利影响。对此，可通过DI限制电感器电流的超调量，以限制冲击电流的大小，从而减小冲击电流对电路的不利影响。为得到DI与 $i _ { \scriptscriptstyle L }$ 的超调量 $\sigma \%$ 的定量关系，下面将建立基于PBC 的Buck变换器系统的传递函数。

控制系统框图如图3所示。图中， $G ( s )$ 为Buck变换器电感器电流的拉普拉斯变换 $I _ { L } ( s )$ 对占空比的拉普拉斯变换 $D ( s )$ 的传递函数； $I _ { L } ^ { * } ( s )$ 为电感器电流给定值的拉普拉斯变换。根据图3可求得系统的闭环传递函数，进而求得系统在阶跃输入下的响应与超调量，从而可通过限制超调量确定DI的取值范围。

![](images/8449fb90b17e16100a8acb6d459dfd1341dd6224740dff32119a8df278c376c5.jpg)  
图3基于无源控制的Buck变换器控制系统框图Fig.3Diagram of control system of Buck converter basedon passivity control

根据式（1）可得

$$
G ( s ) = \frac { I _ { L } ( s ) } { D ( s ) } = \frac { ( R C s + 1 ) U _ { \mathrm { s } } } { R L C s ^ { 2 } + L s + R }
$$

根据图3求得系统的闭环传递函数 $\varPhi ( s )$ 为

$$
\phi ( s ) = \frac { I _ { L } ( s ) } { I _ { L } ^ { * } ( s ) } { = } \frac { ( R _ { \mathrm { a l } } + R ) G ( s ) } { U _ { \mathrm { s } } + R _ { \mathrm { a l } } G ( s ) }
$$

将式（16）代入式（17），有

$$
\Phi ( s ) = \frac { R C s + 1 } { \displaystyle \frac { R L C } { R + R _ { \mathrm { a l } } } s ^ { 2 } + \frac { L + R C R _ { \mathrm { a l } } } { R + R _ { \mathrm { a l } } } s + 1 }
$$

设系统输入为 $i _ { L } ^ { * } ( t ) = I _ { L } ^ { * }$ ，则有 $I _ { L } ^ { ' } ( s ) = I _ { L } ^ { ' } / s$ ，系统输出 $I _ { L } ( s )$ 为

$$
I _ { L } ( s ) = I _ { L } ^ { * } ( s ) \varPhi ( s ) = \frac { I _ { L } ^ { * } } { s } \frac { R C s + 1 } { \displaystyle \frac { R L C } { R + R _ { { \mathrm { a l } } } } s ^ { 2 } + \frac { L + R C R _ { { \mathrm { a l } } } } { R + R _ { { \mathrm { a l } } } } s + 1 }
$$

对式（19）求拉普拉斯逆变换，得

$$
{ i _ { L } } ( t ) = { I } _ { L } ^ { * } - { I } _ { L } ^ { * } { \mathbf { e } } ^ { C \times D }
$$

将式（20）对时间 $t$ 求导，并令导数等于零，可得

求得峰值时间 $t _ { \mathrm { p } }$ 为

$$
t _ { \mathrm { p } } = \frac { R L C \ln \left( - \frac { 2 R \sqrt { L C } } { L + 2 N - R C R _ { \mathrm { a l } } } \right) } { N }
$$

由于超调量发生在峰值时间，将式（22）代入式（20）可得峰值为

$$
i _ { L } ( t _ { \mathrm { p } } ) { = } I _ { L } ^ { * } { - } I _ { L } ^ { * } \mathbf { e } ^ { E \times F }
$$

求得超调量为

$$
\sigma \% = - \boldsymbol { \mathrm { e } } ^ { E \times F }
$$

其中 $A = \mathsf { e } ^ { - \frac { Q t } { 2 R L C } }$

$$
B = \frac { Q } { 2 R L C } - \frac { L - C R ^ { 2 } } { R L C }
$$

$$
C = - \frac { ( L + R C R _ { \mathrm { a l } } ) t } { 2 R L C }
$$

$$
E = - { \frac { P ( 1 + R C R _ { \mathrm { a l } } ) } { 2 N } }
$$

$$
M = \frac { N t } { R L C }
$$

$$
N = \sqrt { \frac { C ^ { 2 } R ^ { 2 } R _ { \mathrm { a l } } ^ { 2 } } { 4 } - \frac { R L C R _ { \mathrm { a l } } } { 2 } - R ^ { 2 } C L + \frac { L ^ { 2 } } { 4 } }
$$

$$
P = \ln \left( - { \frac { 2 R { \sqrt { L C } } } { L + 2 N - R C R _ { \mathrm { a l } } } } \right)
$$

$$
\scriptstyle Q = L + R C R _ { \mathrm { a l } }
$$

二阶系统的标准形式在单位阶跃输入且阻尼比$\zeta = 0 . 4 \sim 0 . 8$ 时，超调量 $\sigma \%$ 介于 $1 . 5 \% \sim 2 5 . 4 \%$ 之间[]。按照该标准校正系统，即

$$
1 . 5 \% \leqslant - \mathrm { e } ^ { E \times F } \leqslant 2 5 . 4 \%
$$

选择电路参数见表1。将表1中参数代入式（25）并求解，可得

$$
0 . 7 6 6 \Omega \leqslant R _ { \mathrm { a l } } \leqslant 4 8 \Omega
$$

$\sigma \%$ 与 $R _ { \mathrm { a l } }$ 的关系曲线如图4所示。由图4可知，随着 $R _ { \mathrm { a l } }$ 的增大，超调量 $\sigma \%$ 减小，反之亦然。

# 表1主电路参数

Tab.1 Parameters of power circuit   

<html><body><table><tr><td>参数</td><td>数值</td><td>参数</td><td>数值</td></tr><tr><td>Us/V</td><td>24</td><td>R/Ω</td><td>0.8</td></tr><tr><td>UcV</td><td>12</td><td>L/mH</td><td>0.4</td></tr><tr><td>1/A</td><td>15</td><td>C/uF</td><td>750</td></tr></table></body></html>

![](images/b3d522cd48e8457af0a9ec92869b5fef77a15ff3f977b9ea3b86a198e5e077a8.jpg)  
图4虚拟阻尼 $R _ { \mathrm { a l } }$ 与超调量 $\sigma \%$ 的关系曲线 Fig.4Relation curve of virtual damping $R _ { \mathrm { a l } }$ and overshoot $\sigma \%$ （2

# 3.2 最优DI确定

通过超调量校正系统后，可得到在指定超调量范围内 $R _ { \mathrm { a l } }$ 的取值范围见式 (26)。使用GA优化，确定系统最终的DI值。GA程序参数见表2，程序流程图如图5所示，选择目标函数为

$$
O b j \nu a l = \sqrt { \sum _ { g e n = 1 } ^ { 2 0 } \sum _ { i = 1 } ^ { 1 0 } ( U _ { c } ^ { * } - u _ { c } ( g e n , i ) ) ^ { 2 } }
$$

$$
g e n = 1 , 2 , \cdots , 2 0 ; i = 1 , 2 , \cdots , 1 0
$$

通过GA优化，求得目标函数的最小值，最终可得最优DI值为 $7 . 5 1 3 \ 7 \Omega$ 。

# 表2GA程序参数

Tab.2 Parameters ofGA programs   

<html><body><table><tr><td>参数</td><td>数值</td><td>参数</td><td>数值</td></tr><tr><td>种群大小</td><td>10</td><td>代沟</td><td>1</td></tr><tr><td>最大遗传代数</td><td>20</td><td>交叉概率</td><td>0.8</td></tr><tr><td>个体长度</td><td>6</td><td>变异概率</td><td>0.01</td></tr></table></body></html>

![](images/c82b736c5defd157ea668e9a702341ab1be8bb57b120e88086b38696eaabb2d6.jpg)  
图5GA程序流程图

# 4 阻尼注入后的系统分析

Buck变换器注入阻尼后的等效电路如图6所示。图中， $R _ { \mathrm { a l } }$ 相当于与电感器 $L$ 串联， $R _ { \mathrm { a } 2 }$ 相当于与电容器 $C$ 并联[4]。

![](images/343954417dc75b4b50e096628b11cf880ad2b324763298f03469366cf58c0e3c.jpg)  
Fig.5Flow chart ofGA program   
图6阻尼注入后的Buck变换器等效电路图 Fig.6Equivalent circuit diagram of Buck converter after damping injection

将系统的闭环传递函数改写为

$$
\phi ( s ) = { \frac { R C s + 1 } { { \frac { R L C } { R + R _ { \mathrm { a l } } } } s ^ { 2 } + { \frac { L + R C R _ { \mathrm { a l } } } { R + R _ { \mathrm { a l } } } } s + 1 } }
$$

将式（28）代入电路参数并绘制系统伯德图如图7所示。由图7可知，在低频段，系统的对数幅频特性均为零，即在低频段系统自身即可稳定运行，输出跟随输入。随着频率的增大，系统会出现超调现象，但是随着DI值的增大，这一现象被抑制。从图7还可得出，随着DI值的增大，系统的带宽增大，意味着系统跟踪输入信号的能力增强，但同时系统抑制输入端高频干扰的能力减弱。所以对于DI的大小应该折衷选取。

![](images/970cc9fc06215b716244b93bf23e63a8d3f643e03aacacf77a09bb9121fb8813.jpg)  
图7阻尼注入后的系统伯德图

图8为系统闭环极点分布图。由图8可知，随着 $R _ { \mathrm { a 1 } }$ 的增大，系统的极点逐渐偏离虚轴，系统由欠阻尼变为过阻尼。但系统极点始终位于复平面的左半平面，所以系统始终稳定运行，证明了本文关于系统稳定性分析的正确性。

![](images/2ec06210871adfd75fe7da5e35f79edd5a60051dfb0939460ecf2067b5cc7dc9.jpg)  
Fig.7Bode diagram of system after damping injection   
图8极点分布图Fig.8Pole map

# 5 仿真研究

选取表1电路参数，开关频率为 $1 0 \mathrm { k H z }$ 。使用最优DI值7.5137Ω对Buck变换器进行仿真，同时选用阻值为0.766Ω与 $4 8 \Omega$ 的DI进行仿真对比，仿真结果如图9所示，系统性能指标见表3。由图9a及表3可知，经GA优化得到的最优DI值可使得系统的输出电压值很好地跟随给定电压值，几乎重合，无超调且响应速度快。输出电压值随着DI值的增大而减小。图9b为系统电流响应波形图。由图9b及表3可知，系统电流响应超调量随着DI的增大而减小，与图4所得结论一致，即DI的增大可以减小电流响应的超调量，从而抑制冲击电流。同时，在最优DI时电流纹波最小，跟随给定值；随着DI的增大，上升时间 $t _ { \mathrm { r } }$ 减小，即系统响应速度加快。

![](images/50eaa5fd61b45a732c76fced5f75d406422ae45ef55000f630784d015be0ec8d.jpg)  
图9仿真实验结果  
Fig.9Diagram of simulation results

# 表3系统性能

Tab.3Performance of system   

<html><body><table><tr><td rowspan="2">Ra1/Ω</td><td colspan="3">性能指标</td></tr><tr><td>0%</td><td>t/s</td><td>ess/V</td></tr><tr><td>0.766</td><td>23.3</td><td>3.5×10-4</td><td>-1</td></tr><tr><td>7.513 7</td><td>19.3</td><td>3×10-4</td><td>0</td></tr><tr><td>48</td><td>12.3</td><td>3×10-4</td><td>0.2</td></tr></table></body></html>

# 6 结论

本文使用无源控制器对Buck变换器进行控制。PBC控制简单，在其控制下系统电压响应迅速且无超调。建立了系统的闭环传递函数，从而得到了 $R _ { \mathrm { a l } }$ 与系统电流超调量的关系，通过对系统电流超调量进行校正，确定DI值的取值范围并通过GA优化得到了最优DI值。最优DI不仅可以使Buck变换器输出电压无超调、无静差，还可抑制电流响应超调量，从而减小了冲击电流对电路的不利影响。仿真实验证明本文所使用的确定最优DI值的方法可以取得良好的效果。通过伯德图分析了DI对基于无源控制的Buck变换器系统的影响。当加入DI项后，闭环系统复现输入信号的能力增强，但同时其抑制输入端高频干扰信号的能力减弱。即增大DI值可以提高系统跟随输入信号的能力，但却不利于系统抑制高频干扰，所以对于DI的大小应该折衷选取。

# 参考文献

[1] 刘卓然，徐海平，张祖之，等．Buck类DC/DC变 换器状态反馈精确线性化恒流控制方法[J]．中国 电机工程学报，2017，37(2)：628-634. Liu Zhuoran,Xu Haiping,Zhang Zuzhi,et al.A novel scheme of constant current control strategy basedon state feedbacklinearizationforBuckderived DC/DC converter[J].Proceedings of the CSEE,2017,37(2):628-634.

[2] 岳小龙，卓放，杨书豪，等．Buck变换器的多频 率矩阵模型及其在分布式供电系统中的应用[J]. 电工技术学报，2017，32(4)：250-259. Yue Xiaolong,Zhuo Fang,Yang Shuhao,et al. A multi-frequency matrix model for Buck converter and its application in distributed power systm[J]. Transaction of China Electrotechnical Society, 2017, 32(4): 250-259.   
[3] 王久和．电能变换器及其无源控制[M]．北京：科 学出版社，2014.   
[4] Kwasinski A,Krein P T. Passivity-based control of Buck converters with constant-power loads[C]. Proceedings of IEEE Power Electronics Specialists Conference,Orlando,FL,USA,2007:259-265.   
[5] Kwasinski A,Krein PT.Stabilization of constant power load in DC-DC converters using passivitybased control[C].Proceedings of the International IEEE Telecommunications Energy Conference, Rome,Italy,2007: 867-874.   
[6] 王久和.先进非线性控制理论及其应用[M].北京： 科学出版社，2012.   
[7] 胡寿松．自动控制原理[M]．北京：科学出版社, 2013.