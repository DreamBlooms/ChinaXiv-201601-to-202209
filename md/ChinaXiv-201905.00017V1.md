# 考虑量化不匹配问题的信息物理系统的安全控制

贾欣婷a，郑柏超aʰ，裴斌a

(南京信息工程大学a.自动化学院;b.江苏省大气环境与装备技术协同创新中心，南京 210044)

摘要：针对一类包含执行器攻击、外部干扰和编码器/解码器不匹配的信息物理系统(cyber-physical systems,CPS)，设计一种新型鲁棒控制器确保其安全稳定运行。控制器线性部分的增益由优化H2性能的线性矩阵不等式给出；控制器的非线性结构包含两部分,一部分用于消除外部干扰、量化误差，另一部分利用对未知执行器攻击参数的自适应估计来实现对攻击的补偿。最后，仿真算例结果表明控制器能保证闭环系统的一致最终有界性，说明了所提方法的有效性。

关键词：信息物理系统；执行器攻击；编码器/解码器失配；一致最终有界 中图分类号：TP273.3 doi: 10.19734/j.issn.1001-3695.2018.11.0890

Security control of cyber-physical systems considering quantization mismatch

Jia Xintinga, Zheng Bochaoa,b, Pei Bina (a.Schoolof Automation，b.Jiangsu Collaborative Innovation Center on Atmospheric Environment& Equipment Technology,Nanjing University of Information Science & Technology,Nanjing210o44,China)

Abstract:This paper proposeda novel robustcontroller to ensure the securityand stability fora classof cyber-physical systemssubject to the efects including actuator attcks，external disturbances，and encoder/decoder mismatches.An optimized H2 performance in the formof linear matrix inequality solves the linear gainofthe constructed controler.The nonlinear structure of the control includes two parts:one aims to eliminate the influence of exteral disturbance and quantizationeror,nd theotherpartcompensates theactuatoratack bymeansofadaptive estimationsofunknownactuator atack parameters.Finally,the simulationresults sow that the controler guarantes uniform ultimate boundednesof the closed-loop dynamical system, which shows the effectiveness of the proposed method.

Key words: cyber-physical system; actuator attacks; encoder/decoder mismatch; uniform ultimate boundednes

# 0 引言

随着信息技术的飞速发展及其数据处理能力的不断提升，使通信和控制系统越来越紧密地联合在一起，信息物理系统(cyber-physical systems,CPS)作为一种新型智能系统应运而生[]。CPS 集成了物理过程，计算资源和通信功能，本质上是具有控制属性的网络，将物理设备连上互联网，但CPS更强调循环反馈。尽管CPS具有良好的广泛的应用前景[2]，但仍然有许多不足之处需要解决，尤其是安全方面的问题[3-6]。

由于CPS使用开放的计算和通信平台架构，很容易受到敌对攻击，攻击者可以访问传感和驱动计算平台，操纵系统测量数据和控制输入命令，严重影响系统的性能和完整性，因此CPS中的安全性比一般计算系统更重要7I。对于CPS的可靠控制问题，针对考虑传感器攻击的CPS，Yucelen 等人[8]提出了自适应控制器以确保系统的稳定性。针对考虑执行器攻击和噪声的CPS，Xie等人I9提出了新颖的切换观测器以确保系统的稳定性。针对同时考虑传感器和执行器攻击的CPS，Jin等人[10]提出了自适应控制器以确保系统的稳定性。

由于数字通信信道在现代工业控制系统中的广泛应用，而通信网络又往往受到通信带宽、有限数据率等困扰，所以通常需要对所测得的信息进行量化处理[I]。信号量化的过程可以看做是编码和解码的过程，编码器和解码器的量化参数必须是相等，Yun等人[12]研究了具有输入量化和外部扰动的不确定线性系统的 $H _ { 2 }$ 状态反馈控制器的设计。由于硬件执行的不理想，在实践中可能会导致量化过程中编码和解码的量化参数不一致的问题。针对此缺陷，Zheng 等人[13]研究了具有量化参数不匹配的线性系统的 $H _ { 2 }$ 控制器的设计。

然而，在CPS的分析与控制的研究中，极少有考虑含信号量化，特别是量化编解码不一致的成果发表。为此，本文研究执行器攻击模式下的含模型不确定[I4]的CPS，并同时考虑量化不匹配问题，通过设计控制器以确保系统的稳定性。控制器的线性部分使模型不确定和量化不匹配的系统实现鲁棒 $H _ { 2 }$ 性能，非线性部分用于消除外部干扰、量化误差以及抑制或抵消状态相关的执行器攻击对系统的影响，从而保证闭环系统的一致最终有界性。

# 1 预备知识及问题描述

# 1.1预备知识

首先介绍本文会用到的投影Proj $: R ^ { n } \times R ^ { n } \to R ^ { n }$ 。给出一个连续可微的凸函数为 $\phi ( \theta ) = : \frac { ( \varepsilon _ { \theta } + 1 ) \theta ^ { T } \theta - \theta _ { \mathrm { m a x } } ^ { 2 } } { \varepsilon _ { \theta } \theta _ { \mathrm { m a x } } ^ { 2 } }$ ，其中 $\theta _ { \mathrm { m a x } } \in R$ 是$\theta \in R ^ { n }$ 的投影范数界， $ { \varepsilon } _ { \theta } > 0$ 是投影容差界限，对于 $y \in R ^ { n }$ ，向

量的投影定义为

$$
\begin{array}{c} \begin{array} { r l } & { \mathrm { P r o j } ( \theta , y ) = : } \\ & { \left\{ \begin{array} { c c } { y } & { \mathrm { i f ~ } \phi ( \theta ) < 0 } \\ { y } & { \mathrm { i f ~ } \phi ( \theta ) \geq 0 , \phi ^ { \prime } ( \theta ) y \leq 0 } \\ { y } & { \mathrm { i f ~ } \phi ( \theta ) \geq 0 , \phi ^ { \prime } ( \theta ) y > 0 } \end{array} \right. } \\ & { \left\{ y - \displaystyle \frac { \phi ^ { \prime } { \cal T } \left( \theta \right) \phi ^ { \prime } ( \theta ) y } { \phi ^ { \prime } ( \theta ) \phi ^ { \prime } { \cal T } \left( \theta \right) } \phi ( \theta ) \right.} & { \mathrm { i f ~ } \phi ( \theta ) \geq 0 , \phi ^ { \prime } ( \theta ) y > 0 } \end{array}   \end{array}
$$

在向量的投影基础上，定义矩阵的投影${ \mathrm { P r o j } } _ { m } : R ^ { n \times m } \times R ^ { n \times m }  R ^ { n \times m }$

$$
\begin{array} { r l } & { \mathrm { P r o j } _ { m } ( \Theta , Y ) = } \\ & { ( \mathrm { P r o j } ( \mathsf { c o l } _ { 1 } ( \Theta ) , \mathsf { c o l } _ { 1 } ( Y ) ) , \cdots , \mathrm { P r o j } ( \mathsf { c o l } _ { m } ( \Theta ) , \mathsf { c o l } _ { m } ( Y ) ) ) } \end{array}
$$

其中: $\Theta \in R ^ { n \times m }$ ， $Y \in R ^ { n \times m }$ ， $\operatorname { c o l } _ { i } ( A )$ 表示矩阵 $A$ 的第 $i$ 列。

文中 $R$ 表示实数集合， $R ^ { n }$ 表示 $n$ 维实数列向量， $R ^ { n \times m }$ 表示 $\boldsymbol { n } \times \boldsymbol { m }$ 维的实矩阵， $A ^ { { \scriptscriptstyle T } }$ 表示矩阵 $A$ 的转置， $A ^ { - 1 }$ 表示矩阵 $A$ 的逆矩阵， $X > 0 ( X \geq 0 )$ 表示 $\boldsymbol { \cal X }$ 是正定（半正定）矩阵， $\left\| \cdot \right\| _ { p }$ 表示向量的 $p$ -范数，即 $\left\| x \right\| _ { p } = ( \left\| x _ { 1 } \right\| ^ { p } + \left\| x _ { 2 } \right\| ^ { p } + \dots + \left\| x _ { n } \right\| ^ { p } ) ^ { 1 / p }$ ， $p { \geq } 1$ ，当 $p = \infty$ 时， $\left\| x \right\| _ { \infty } = \operatorname* { m a x } _ { 1 \leq i \leq n } \left\| x _ { i } \right\|$ ，特别的，表示2-范数，表示Frobenius 矩阵范数， $\overline { { x } } \left( \underline { { x } } \right)$ 表示 $x$ 的上界（下界)，对称矩阵的对称位置用“\*”表示。

# 1.2问题描述

针对遭受执行器攻击的不确定信息物理系统，建立如式（3）所示的动态方程模型。

$$
\dot { x } ( t ) = ( A + \Delta A ( t ) ) x ( t ) + B \tilde { u } ( t ) + B \omega ( t )
$$

其中： $x ( t ) \in R ^ { n }$ 表示系统的状态， $\omega ( t ) \in R ^ { m }$ 是外部干扰， $A$ 和 $B$ 为已知的具有适当维数的常值矩阵， $\Delta A ( t )$ 是适当维数的不确定参数矩阵， $\tilde { u } ( t ) \in R ^ { m }$ 为遭受执行器攻击的控制输入，其数学表达式为

$$
\tilde { u } ( t ) = u ( t ) + \delta _ { a } ( t , x ( t ) )
$$

其中: $\delta _ { a } ( t , x ( t ) ) : R \times R ^ { n } \to R ^ { m }$ 为攻击模式，是发生在控制器与执行器之间通信链路上的攻击。同文献[10]一样，本文假设执行器攻击参数化为 $\delta _ { a } ( t , x ( t ) ) = W ^ { T } ( t ) \varphi ( x ( t ) )$ ，其中， $W ( t ) \in R ^ { p \times m }$ 是未知的时变加权矩阵且 $\left\| W ( t ) \right\| _ { F } \leq \overline { { W } }$ ， $\left\| \dot { W } ( t ) \right\| _ { F } \leq \overline { { \dot { W } } }$ ， $\varphi ( { \boldsymbol { x } } ( t ) ) \in R ^ { p }$ 是结构已知的关于 $x ( t )$ 的非线性函数。从表达式（2）可见，如果$\delta _ { a } ( \cdot , \cdot )$ 非零，则控制输入信号 $u ( t )$ 会被错误（或恶意）的信号$\tilde { u } ( t )$ 取代，即，系统遭受执行器攻击。

另一方面，控制系统的执行过程越来越多的采用远程通信或数字方式来实现，而数字通信网络往往受到通信带宽、有限数据率等困扰，所以通常需要对所测得的信息进行量化处理。量化器 $Q ( \cdot )$ 由向最接近的整数舍入函数 $q ( \cdot )$ 定义，本文采用如下的量化器形式：

$$
Q ( u ( t ) ) = \mu _ { d } ( t ) q { \Biggl ( \frac { u ( t ) } { \mu _ { c } ( t ) } \Biggr ) }
$$

其中， $\mu _ { d } ( t )$ 和 $\mu _ { c } ( t )$ 分别为编码侧和解码侧的量化灵敏度参数，令 $r ( t ) = \mu _ { d } ( t ) / \mu _ { c } ( t )$ ，理想情况下 $\mu _ { d } ( t )$ 和 $\mu _ { c } ( t )$ 是相等的，即 $r = 1$ 。然而在实际控制工程中，由于硬件执行不理想，该要求显然是非常严格且难以实施的，所以本文考虑量化不匹配更一般的情况， $\boldsymbol { r } ( t ) \in ( \underline { { r } } , \overline { { r } } )$ ，其中， $\underline { { r } }$ 和 $\overline { { r } }$ 都是正参数并且 $\overline { { r } } \geq 1 \geq \underline { { r } } > 0$ ，所以 $r = 1$ 也是该情况下的一种特殊情况。

综合上述式（3）～（5)，系统（3）变为式（6）的形式$\dot { x } ( t ) = ( A + \Delta A ( t ) ) x ( t ) + B Q ( \tilde { u } ( t ) ) + B \omega ( t )$ (6)

其中 $Q ( \tilde { { u } } ( t ) )$ 是受到执行器攻击的量化输入

$$
Q ( \tilde { u } ( t ) ) = \mu _ { d } ( t ) \Biggl [ q \Biggl ( \frac { u ( t ) } { \mu _ { c } ( t ) } \Biggr ) + \delta _ { a } ( t , x ( t ) ) \Biggr ]
$$

在信息物理系统（6）的运行过程中，控制输入 $u ( t )$ 经编码器一侧获得量化测量信息 $q ( u ( t ) / \mu _ { c } ( t ) )$ ，在传输编码过的控制信号到解码器处的网络通信链路中，受到网络攻击者恶意注入的执行器攻击 $\delta _ { a } ( t , x ( t ) )$ ，在传输到执行器之前的控制信号需要先进行解码，经解码器获得遭受执行器攻击的量化输入 $Q \big ( \tilde { u } ( t ) \big )$ ，量化反馈的信息物理系统如图1所示。

![](images/b8ffd2e561a7b60675450c4f4714828388a29c61a7bae9776b1b0517a7b5c63e.jpg)  
图1信息物理系统结构图  
Fig.1Structure diagram of cyber-physical system

首先给出以下3个假设：

假设1 系统 $( \boldsymbol { \textbf { \em A } } , \boldsymbol { B } )$ 是可控的。

假设2[13] 时变的不确定矩阵 $\Delta A ( t )$ 满足

$$
\Delta A ( t ) = F _ { 1 } \Delta ( t ) E _ { 1 } , \Delta ( t ) \Delta ( t ) ^ { T } \leq I
$$

其中： $F _ { 1 }$ 和 $E _ { 1 }$ 是已知的具有适当维数的常值矩阵， $\Delta ( t )$ 是未知的时变矩阵。

假设 $3 ^ { [ 1 3 ] }$ 存在已知的参数 $\varepsilon _ { \omega }$ 使得外部干扰 $\omega ( t )$ 满足

$$
\| \omega ( t ) \| _ { \infty } \leq \varepsilon _ { \omega }
$$

在给出本文的控制器设计之前，首先引入如下的 $H _ { 2 }$ 性能指标的概念[12]：

$$
J ( t ) = : \int _ { t } ^ { \infty } \{ x ^ { T } ( s ) Q x ( s ) + x ^ { T } ( s ) K ^ { T } R K x ( s ) \} d s
$$

其中： $\varrho$ 和 $R$ 是给定的对称正定加权矩阵， $\kappa$ 是控制器中给出的线性反馈增益矩阵。

本文用到如下三个引理。

引理 $1 ^ { [ 1 2 ] }$ 对于任意两个 $n$ 维实向量 $\alpha$ 与 $\beta$ ，当 $p { \geq } 1$ ，$q \geq 1$ 且 $p ^ { - 1 } + q ^ { - 1 } = 1$ 时，下列不等式成立

$$
\left\| \alpha ^ { T } \beta \right\| \leq \left\| \alpha \right\| _ { p } \left\| \beta \right\| _ { q }
$$

引理 $2 ^ { [ 1 5 ] }$ 对于任意给定适当维数的实矩阵 $\Pi \setminus X$ 和 $Y$ ，其中 $\pi$ 是对称的，当矩阵 $F ( t )$ 满足 $F ^ { T } ( t ) F ( t ) \leq I$ 时，则

$$
\Pi + X F ( t ) Y + Y ^ { T } F ( t ) ^ { T } X ^ { T } < 0
$$

当且仅当存在一个常数 $\varepsilon > 0$ 使得下列不等式成立

$$
\Pi + \varepsilon X X ^ { T } + \varepsilon ^ { - 1 } Y ^ { T } Y < 0
$$

引理 $3 ^ { [ 1 0 ] }$ 根据矩阵投影 ${ \mathrm { P r o j } _ { m } }$ 的定义，对于给定的$\Theta ^ { * } \in R ^ { n \times m }$ ，下列不等式成立：

$$
\operatorname { t r } ( ( \Theta - \Theta ^ { * } ) ^ { T } ( \operatorname* { P r } o j _ { m } ( \Theta , N ) - N ) ) \leq 0
$$

# 2 量化不匹配CPS的安全控制

针对上述信息物理系统式（6）设计一种新型鲁棒控制器保证闭环系统的一致最终有界性。其线性部分的增益由优化$H _ { 2 }$ 性能的线性矩阵不等式给出；其非线性部分用于消除外部干扰、量化误差以及抑制或抵消状态相关的执行器攻击对系统的影响。构造如下结构的控制器

$$
u ( t ) = K x ( t ) + u _ { n } ( t ) + \nu ( t )
$$

其中：

$$
u _ { n } ( t ) = - ( \frac { \mu _ { c } } { 2 } + \frac { \varepsilon _ { \omega } } { \underline { { r } } } ) \mathrm { s i g n } ( x ^ { T } P B )
$$

$$
\nu ( t ) = - \mu _ { c } \hat { W } ( t ) ^ { T } \varphi ( x ( t ) )
$$

$\hat { W } ( t )$ 满足自适应律：

$$
\dot { \hat { W } } ( t ) = \eta \overline { { r } } \mu _ { c } \mathrm { P r o j } _ { m } ( \hat { W } ( t ) , \varphi ( x ( t ) ) x ^ { T } P B )
$$

参数 $\eta$ 为正的调节增益， $\mathrm { P r o j } _ { m }$ 为矩阵的投影。

$K x ( t )$ 为线性部分,用于使不确定性系统实现如式(10)的$H _ { 2 }$ 性能。

$u _ { n } ( t )$ 与 $\nu ( t )$ 为非线性部分，分别用来处理量化误差和外部干扰、抑制或抵消状态相关的执行器攻击的影响。

为了证明方便，定义 $\tilde { W } = W - \hat { W }$ ， $e _ { \mu _ { c } } = \mu _ { c } q \Bigg ( \frac { u } { \mu _ { c } } \Bigg ) - u$ ，容易得到：

$$
\begin{array} { l } { \displaystyle \dot { x } = ( A + \Delta A ( t ) ) x ( t ) + B [ \frac { \mu _ { d } } { \mu _ { c } } \mu _ { c } ( q ( \frac { u } { \mu _ { c } } ) + \delta _ { a } ( t , x ( t ) ) ) ] + B \omega ( t ) } \\ { \displaystyle \qquad = ( A + F _ { 1 } \Delta _ { 1 } E _ { 1 } ) x ( t ) + r B [ u + e _ { \mu _ { c } } + \mu _ { c } W ^ { T } ( t ) \varphi ( x ( t ) ) ] + B \omega ( t ) } \\ { \displaystyle \qquad = ( A + F _ { 1 } \Delta _ { 1 } E _ { 1 } ) x ( t ) + r B [ K x ( t ) + u _ { n } + e _ { \mu _ { c } } + \mu _ { c } \tilde { W } ^ { T } ( t ) \varphi ( x ( t ) ) ] } \\ { \displaystyle \qquad + B \omega ( t ) } \end{array}
$$

和

$$
\dot { \tilde { W } } ( t ) = \dot { W } ( t ) - \eta \overline { { r } } \mu _ { c } \mathrm { P r o j } _ { m } ( \hat { W } ( t ) , \varphi ( x ( t ) ) x ^ { T } P B )
$$

定理1对于满足假设1\~3的信息物理系统式（6）并且$\delta _ { a } ( t , x ( t ) ) = 0$ ，当 $r \in ( \underline { { r } } , \overline { { r } } )$ 时，存在对称正定矩阵 $\overline { { P } }$ 和 $M$ ，常规矩阵 $\bar { K }$ ，正标量 $\eta _ { 1 }$ ，使以下的优化问题有解。

min Trace $( M )$

$$
\begin{array} { r l } & { ( A + F _ { 1 } \Delta _ { 1 } E _ { 1 } ) ^ { T } P + P ( A + F _ { 1 } \Delta _ { 1 } E _ { 1 } ) + r K ^ { T } B ^ { T } P + r P B K \leq } \\ & { \qquad A ^ { T } P + P A + \eta _ { 1 } ^ { - 1 } E _ { 1 } ^ { T } E _ { 1 } + \eta _ { 1 } P F _ { 1 } F _ { 1 } ^ { T } P + r P B K + r K ^ { T } B ^ { T } P } \end{array}
$$

所以

$$
\dot { V } \le x ^ { T } ( A ^ { T } P + P A + \eta _ { 1 } ^ { - 1 } E _ { 1 } ^ { T } E _ { 1 } + \eta _ { 1 } P F _ { 1 } F _ { 1 } ^ { T } P + r P B K + r K ^ { T } B ^ { T } P ) x
$$

如果不等式

$$
\begin{array} { r l } & { A ^ { T } P + P A + \eta _ { 1 } ^ { - 1 } E _ { 1 } ^ { T } E _ { 1 } + \eta _ { 1 } P F _ { 1 } ^ { T } F _ { 1 } P } \\ & { ~ + r K ^ { T } B ^ { T } P + r P B K + Q + K ^ { T } R K < 0 } \end{array}
$$

成立，可以得到

$$
\dot { V } ( t ) \leq - x ^ { T } ( t ) ( Q + K ^ { T } R K ) x ( t ) \leq \dot { J } ( t )
$$

由于 $J ( \infty ) = V ( \infty ) = 0$ 以及 $\dot { V } ( t ) \leq \dot { J } ( t )$ ，可以得到$J ( t ) \le V ( x ( t ) ) \le V ( x ( 0 ) )$ ，从上述结论可以看出 $H _ { 2 }$ 性能的上界依赖于系统的初始状态 $x ( 0 )$ ，而在实际应用中，很难精确确定系统的初始状态，为了克服这一困难，可以假定初始状态 $x ( 0 )$ 是一个满足 ${ \mathrm { E } } \{ x ( 0 ) x ^ { T } ( 0 ) \} = I$ 的零均值随机变量。通过考虑性能指标的期望值，得到

$$
\overline { { J } } = \operatorname { E } \{ J \} \leq \operatorname { E } \{ x ( 0 ) P x ^ { T } ( 0 ) \} = \operatorname { T r a c e } ( P )
$$

根据Schur补引理[I2]，定理1中的约束条件式（16）等价于 $M > P { > } 0$ ，因此， $M$ 的迹最小化将保证 $P$ 的迹的最小化，即系统 $H _ { 2 }$ 性能上界的最小化。在式（18）两边同乘以 $P ^ { - 1 }$ ，令 $\overline { { P } } = P ^ { - 1 }$ 以及 $K = \bar { K } \bar { P } ^ { - 1 }$ ，根据 Schur补引理，可以得到如式（15)的不等式。因此，通过最小化正定矩阵 $\bar { P }  \ 、 M$ 、常规矩阵 $K$ 、正标量 $\eta _ { 1 }$ ，可以实现最小 $H _ { 2 }$ 性能上界，由此定理1证明完毕。

定理2对于满足假设1\~3的信息物理系统式(6)，对于所有 $( x ( 0 ) , \tilde { W } ( 0 ) ) \in R ^ { n } \times R ^ { p \times m }$ ，由式（11）给出的满足式（ $( 1 2 ) \sim$ （14）的控制器使闭环系统是一致有界的，且 $x ( t )$ 和 $\tilde { W } ( t )$ 最终有界。

$$
\left. \boldsymbol { x } ( t ) \right. \leq [ \frac { 1 } { \lambda _ { \operatorname* { m i n } } ( P ) } ( \lambda _ { \operatorname* { m a x } } ( P ) d _ { 1 } ^ { - 1 } d _ { 2 } + \eta ^ { - 1 } ( \bar { W } + \hat { W } _ { \operatorname* { m a x } } ) ^ { 2 } ) ] ^ { \frac { 1 } { 2 } }
$$

$$
\left[ \begin{array} { c c c c } { { \Gamma } } & { { \overline { { { P } } } E _ { 1 } ^ { T } } } & { { \overline { { { P } } } } } & { { \bar { K } ^ { T } } } \\ { { * } } & { { - \eta _ { 1 } I } } & { { 0 } } & { { 0 } } \\ { { * } } & { { * } } & { { - Q ^ { - 1 } } } & { { 0 } } \\ { { * } } & { { * } } & { { * } } & { { - R ^ { - 1 } } } \end{array} \right] < 0
$$

$$
\begin{array} { r } { { \left[ \begin{array} { l l } { M } & { I } \\ { I } & { { \bar { P } } } \end{array} \right] } > 0 } \end{array}
$$

其中： $\Gamma = A \overline { { { P } } } + \overline { { { P } } } A ^ { T } + \eta _ { 1 } F F ^ { T } + r B \overline { { { K } } } + r \overline { { { K } } } ^ { T } B ^ { T }$ 。当 $K = \bar { K } \bar { P } ^ { - 1 }$ 时，则由式（11）给出的满足式（12）的控制器使闭环系统 $x ( t )$ 轨迹渐近收敛于原点并满足 $H _ { 2 }$ 性能，可以通过最小化矩阵 $M$ 的迹来达到最小的 $H _ { 2 }$ 性能上界。

证明考虑李雅普诺夫函数 $V = x ( t ) ^ { T } P x ( t )$ ， $\mathbf { } V ( t )$ 沿系统轨迹的时间导数为

$$
\begin{array} { r l } & { \dot { V } = \dot { x } ^ { T } P x + x ^ { T } P \dot { x } } \\ & { \qquad = x ^ { T } [ ( A + F _ { \mathrm { l } } \Delta _ { \mathrm { l } } E _ { \mathrm { l } } ) ^ { T } P + P ( A + F _ { \mathrm { l } } \Delta _ { \mathrm { l } } E _ { \mathrm { l } } ) + r K ^ { T } B ^ { T } P + r P B K ] x } \\ & { \qquad + 2 r x ^ { T } P B ( u _ { n } + e _ { \mu _ { c } } ) + 2 x ^ { T } P B \omega ( t ) } \end{array}
$$

根据引理1，假设2、3，因为不等式

$$
\left\| e _ { \mu _ { c } } \right\| _ { \infty } = \left\| \mu _ { c } q \left( \frac { u } { \mu _ { c } } \right) - u \right\| _ { \infty } = \left\| \mu _ { c } ( q ( \frac { u } { \mu _ { c } } ) - \frac { u } { \mu _ { c } } ) \right\| _ { \infty } \leq \mu _ { c } / 2
$$

可得

$$
\begin{array} { r l } & { 2 r x ^ { T } P B ( u _ { n } + e _ { \mu _ { c } } ) + 2 x ^ { T } P B \omega \leq } \\ & { \qquad 2 r x ^ { T } P B u _ { n } + 2 r \left\| x ^ { T } P B \right\| _ { 1 } \left\| e _ { \mu _ { c } } \right\| _ { \infty } + 2 \left\| x ^ { T } P B \right\| _ { 1 } \left\| \omega \right\| _ { \infty } \leq } \\ & { \qquad 2 r x ^ { T } P B u _ { n } + 2 r \left\| x ^ { T } P B \right\| _ { 1 } \displaystyle \frac { \mu _ { c } } { 2 } + 2 \left\| x ^ { T } P B \right\| _ { 1 } \varepsilon _ { \omega } } \end{array}
$$

将式（12）代入式（17）可得

$$
2 r x ^ { T } P B u _ { n } + 2 r \| x ^ { T } P B \| _ { 1 } \frac { \mu _ { c } } { 2 } + 2 \| x ^ { T } P B \| _ { 1 } \varepsilon _ { \omega } \leq 0
$$

根据引理2可得

$$
\begin{array} { r } { \left\| \tilde { W } ( t ) \right\| _ { F } \leq [ \eta \lambda _ { \operatorname* { m a x } } ( P ) d _ { 1 } ^ { - 1 } d _ { 2 } + ( \bar { W } + \hat { W } _ { \operatorname* { m a x } } ) ^ { 2 } ] ^ { \frac { 1 } { 2 } } } \end{array}
$$

其中： $d _ { 1 } = \lambda _ { \operatorname* { m i n } } ( Q + K ^ { T } R K ) \quad , \qquad d _ { 2 } = \frac { 2 ( r - \overline { { r } } ) } { \eta \overline { { r } } } ( \overline { { W } } + \hat { W } _ { \operatorname* { m a x } } ) \dot { \hat { W } } _ { \operatorname* { m a x } } +$

$2 \eta ^ { - 1 } ( \bar { W } + \hat { W } _ { \mathrm { m a x } } ) \bar { \dot { W } } ~ , ~ \hat { W } _ { \mathrm { m a x } } \in R ~ , ~ \dot { \hat { W } } _ { \mathrm { m a x } } \in R$ 是投影的范数界。

证明考虑李雅普诺夫函数 $V = x ( t ) ^ { T } { \cal P } x ( t ) + \eta ^ { - 1 } t r ( \tilde { W } ^ { T } ( t ) \tilde { W } ( t ) )$ ，前面的证明类似定理1， $V ( t )$ 沿系统轨迹的时间导数是

$$
\begin{array} { r l } & { \dot { V } = \dot { x } ^ { T } P x + x ^ { T } P \dot { x } + 2 \eta ^ { - 1 } t r ( \tilde { W } ^ { T } \dot { \tilde { W } } ) \leq } \\ & { \qquad - x ^ { T } ( Q + K ^ { T } R K ) x + 2 r x ^ { T } P B ( \mu _ { c } \tilde { W } ^ { T } \varphi ( x ( t ) ) ) } \\ & { \qquad - 2 \overline { { r } } \mu _ { c } t r [ \tilde { W } ^ { T } \mathrm { P r o j } _ { m } ( \hat { W } , \varphi ( x ( t ) ) x ^ { T } P B ) ] + 2 \eta ^ { - 1 } t r ( \tilde { W } ^ { T } \dot { W } ) } \end{array}
$$

根据引理3可得

$$
\begin{array} { r l } & { 2 r x ^ { T } P B ( \mu _ { c } \tilde { W } ^ { T } \varphi ( x ( t ) ) ) - 2 \overline { { r } } \mu _ { c } t r [ \tilde { W } ^ { T } \operatorname* { P r } \textstyle \rho _ { j _ { m } } ( \hat { W } , \varphi ( x ( t ) ) x ^ { T } P B ) ] = } \\ & { 2 r \mu _ { c } t r [ \tilde { W } ^ { T } \varphi ( x ( t ) ) x ^ { T } P B ] } \\ & { \qquad - 2 ( r - r + \overline { { r } } ) \mu _ { c } t r [ \tilde { W } ^ { T } \operatorname* { P r } \cal { O } j _ { m } ( \hat { W } , \varphi ( x ( t ) ) x ^ { T } P B ) ] = } \\ & { 2 r \mu _ { c } t r [ ( \hat { W } - W ) ^ { T } ( \operatorname* { P r } \cal { O } j _ { m } ( \hat { W } , \varphi ( x ( t ) ) x ^ { T } P B ) - \varphi ( x ( t ) ) x ^ { T } P B ) ] } \\ & { \qquad + 2 ( r - \overline { { r } } ) \mu _ { c } t r [ \tilde { W } ^ { T } \operatorname* { P r } \cal { O } j _ { m } ( \hat { W } , \varphi ( x ( t ) ) x ^ { T } P B ) ] \leq } \\ & { 2 ( r - \overline { { r } } ) \mu _ { c } t r [ \tilde { W } ^ { T } \operatorname* { P r } \cal { O } j _ { m } ( \hat { W } , \varphi ( x ( t ) ) x ^ { T } P B ) ] } \end{array}
$$

所以

$$
\begin{array} { r l r } {  { \dot { V } \le - x ^ { T } ( Q + K ^ { T } R K ) x + \frac { 2 ( r - \overline { { r } } ) } { \eta \overline { { r } } } t r ( \tilde { W } ^ { T } \dot { \hat { W } } ) + 2 \eta ^ { - 1 } t r ( \tilde { W } ^ { T } \dot { W } ) \| x \| ^ { 2 } \le } } \\ & { } & { \quad - d _ { 1 } \| x \| ^ { 2 } + d _ { 2 } } \end{array}
$$

因此，在 $\Omega$ 集合之外， $\dot { V } < 0$ 。

$$
\Omega = \{ ( \boldsymbol { x } ( t ) , \tilde { W } ( t ) ) \in R ^ { n } \times R ^ { p \times m } : \left. \boldsymbol { x } ( t ) \right. \leq \mathcal { S } _ { 1 } , \left. \tilde { W } ( t ) \right. _ { F } \leq \mathcal { S } _ { 2 } \}
$$

其中 $\mathscr { s } _ { 1 } = \sqrt { d _ { 2 } / d _ { 1 } }$ ， $\mathcal { S } _ { 2 } = \overline { { W } } + \hat { W } _ { \operatorname* { m a x } }$ ，这就证明了定理2闭环系统的

一致有界性。

因为

$$
\begin{array} { r } { \lambda _ { \operatorname* { m i n } } ( P ) \left\| x ( t ) \right\| ^ { 2 } + \eta ^ { - 1 } \left\| \tilde { W } \right\| _ { F } ^ { 2 } \leq \upsilon _ { \operatorname* { m a x } } } \end{array}
$$

其中： $\begin{array} { r } { \upsilon _ { \mathrm { m a x } } = \lambda _ { \mathrm { m a x } } ( P ) \vartheta _ { 1 } ^ { 2 } + \eta ^ { - 1 } \vartheta _ { 2 } ^ { 2 } } \end{array}$ ，由式（21）可得 $\left\| x ( t ) \right\| ^ { 2 } \leq \frac { \upsilon _ { \operatorname* { m a x } } } { \lambda _ { \operatorname* { m i n } } ( P ) }$ （20$\left\| \tilde { W } \right\| _ { F } ^ { 2 } \leq \eta v _ { \operatorname* { m a x } }$ ，所以 $x ( t )$ 和 $\tilde { W } ( t )$ 是最终有界的，由此定理2证明完毕。

# 3 实验结果与分析

下面给出一个仿真实例来验证本文所提方法的有效性。考虑如式(6)形式的飞行器动态系统的线性化模型[10]，其中，系统状态 $\boldsymbol { x } ( t ) = [ \beta ( t ) , p ( t ) , \gamma ( t ) ] ^ { \scriptscriptstyle T }$ 包含侧滑角（deg）、滚转率（deg/s）以及偏航率（deg/s），控制输入 $\boldsymbol { u } ( t ) = [ \delta _ { a i l } ( t ) , \delta _ { r u d } ( t ) ] ^ { \scriptscriptstyle T }$ 包含副翼偏转（deg）以及方向舵偏转（deg），系统的矩阵参数如下：

$$
A = \left[ { \begin{array} { c c c } { - 0 . 0 2 5 } & { 0 . 1 0 4 } & { - 0 . 9 9 4 } \\ { 5 7 4 . 7 } & { 0 } & { 0 } \\ { 1 6 . 2 0 } & { 0 } & { 0 } \end{array} } \right] , B = \left[ { \begin{array} { c c c } { 0 . 1 2 2 } & { - 0 . 2 7 6 } \\ { - 5 3 . 6 1 } & { 3 3 . 2 5 } \\ { 1 9 5 . 5 } & { - 5 2 9 . 4 } \end{array} } \right]
$$

$$
F _ { 1 } = [ 1 0 5 ] ^ { T } , E _ { 1 } = [ 1 1 1 ]
$$

仿真中考虑三种情况。

a)为了说明量化不匹配问题对系统稳定性的影响，先进行量化灵敏度参数匹配时的信息物理系统的仿真，对称正定矩阵 $P$ 和控制器增益 $\boldsymbol { K }$ 由文献[12]定理3中的 $L M s$ 求出，控制器中的非线性补偿器 $u _ { n } ( t )$ 采用文献[12]的形式。

b)同上述的对称正定矩阵 $P$ 、控制器增益 $K$ 选取以及补偿器 $u _ { n } ( t )$ 的形式相同，将量化灵敏度参数修改为不匹配时，对信息物理系统进行仿真。

c)针对上述修改为不匹配的量化灵敏度参数，由本文定理1中的 $L M s$ 求解给出对称正定矩阵 $P$ 和控制器增益 $\boldsymbol { K }$ ，控制器中的补偿器 $u _ { n } ( t )$ 如（12）的形式进行仿真。

情况1根据文献[12]中的定理3，选取参数矩阵$Q = 0 . 0 1 I _ { 3 }$ ， $R = 0 . 1 I _ { 3 }$ ，求得

$$
P = { \left[ \begin{array} { l l l } { 2 . 8 2 4 2 } & { 0 . 0 9 7 1 } & { - 0 . 0 1 0 2 } \\ { 0 . 0 9 7 1 } & { 0 . 0 0 4 3 } & { 0 . 0 0 0 1 } \\ { - 0 . 0 1 0 2 } & { 0 . 0 0 0 1 } & { 0 . 0 0 0 6 } \end{array} \right] } , K = { \left[ \begin{array} { l l l } { 3 5 . 4 7 0 8 } & { 1 . 4 3 8 4 } & { - 0 . 0 4 0 6 } \\ { 6 . 4 2 6 8 } & { 0 . 4 7 7 4 } & { 0 . 2 2 6 7 } \end{array} \right] }
$$

选取量化灵敏度参数 $\mu _ { d } = \mu _ { c } = 0 . 0 6$ ，假设执行器攻击为$\begin{array} { r l } { \delta _ { a } ( t , x ( t ) ) = \left[ 0 . 5 \sin t } & { { } \cos ( 2 t ) \right] ^ { T } 0 . 2 \sin ( \beta ( t ) ) \cos ( p ( t ) ) } \end{array}$ 。运用Matlab/Simulink对系统（6）进行仿真，得到系统的响应曲线如图2和图3所示。可以看出，当量化器灵敏度参数匹配时，文献[12]的控制器使信息物理系统的状态和控制输入收敛于原点，系统趋近于稳定。

情况2选取量化灵敏度参数分别为 $\mu _ { d } = 0 . 0 6$ 和 $\mu _ { c } = 0 . 1$ ，运用Matlab/Simulink进行仿真，得到系统的响应曲线如图4和5所示，仿真结果看出，由于编码器和解码器量化灵敏度参数发生不匹配现象，闭环系统状态是发散的，系统呈现不稳定现象，文献[12]的方法失效。

情况3根据本文定理1，可求得

$$
P = { \left[ \begin{array} { l l l } { 0 . 9 3 1 2 } & { 0 . 0 3 6 9 } & { 0 . 0 0 3 0 } \\ { 0 . 0 3 6 9 } & { 0 . 0 0 2 4 } & { 0 . 0 0 0 8 } \\ { 0 . 0 0 3 0 } & { 0 . 0 0 0 8 } & { 0 . 0 0 0 7 } \end{array} \right] } , K = { \left[ \begin{array} { l l l } { 1 9 . 0 5 9 4 } & { - 0 . 3 8 1 3 } & { - 1 . 3 3 8 2 } \\ { 9 . 5 1 2 5 } & { 5 . 1 0 3 8 } & { 4 . 9 2 5 5 } \end{array} \right] }
$$

运用本文定理2中的控制器设计方法，并经MATLAB/Simulink对闭环系统进行仿真，系统的响应曲线如图6和7所示，仿真结果表明设计的控制器在信息物理系统发生量化灵敏度参数不匹配、外部干扰以及模型不确定性时，仍能实

现令人满意的系统性能。

![](images/11694a109078cbf8b0cd081626eb7d0feee0ffe9d5d6dc2f8294213f6fb368fe.jpg)  
图2系统状态响应曲线图

![](images/d7a49cc334acf26356fbb8b5e734fa9a43b4644bbb2bb9e0130b805c6229cb2d.jpg)  
Fig.2The response curves of system states

![](images/ae04c294f646004d1e39377af243de34f10206a50fb49801f320166f03bd4f38.jpg)  
Fig.3The response curves ofcontrol inputs   
图4系统状态响应曲线图

![](images/fb44dae18a5fc987dcae3bee3b01a039b18d303f8dc8ece1cc134a13c9d31c61.jpg)  
图3系统控制输入响应曲线图  
Fig.4The response curves of system states   
图5系统控制输入响应曲线图Fig.5The response curves of control inputs

![](images/648c03420b2b3f9aa64454febc62d86ddddc8359f6345d9319f82c6197c53999.jpg)  
图6系统状态响应曲线图

![](images/222c2f0fb16722efbf0f88d2ed935a4f33f243967fe7abad6e33f094dd9dd753.jpg)  
Fig.6The response curves of system states   
图7系统控制输入响应曲线图  
Fig.7The response curves of control inputs

从上面三种情况的仿真效果对比表明，文献[12]设计的控制器能确保在发生情况1的信息物理系统，即量化匹配的信息物理系统，实现稳定，但当发生量化不匹配时，由仿真图4和5可以看出文献[12]的控制器已经无法确保信息物理系统的稳定，严重时甚至导致系统失稳。由情况 $\textcircled{2}$ 的仿真可以看出，本文设计的控制器能有效克服量化不匹配等的影响，确保信息物理系统的稳定，充分验证了本文控制算法的有效性和优越性。

# 4 结束语

本文研究了存在执行器攻击、外部干扰和量化不匹配的信息物理系统的安全控制问题。设计的控制器由线性和非线性两部分组成，其中，线性部分用于使模型不确定性系统实现 $H _ { 2 }$ 性能；其非线性部分用于消除外部干扰、量化误差以及抑制或抵消状态相关的执行器攻击对系统的影响，以确保闭环系统的一致最终有界性。仿真结果体现了文中算法的有效性与优越性。未来的研究工作中，将重点解决发生通信中断和时延等情形下的信息物理系统的安全可靠控制问题。

# 参考文献：

[1]王中杰，谢璐璐．信息物理融合系统研究综述[J]．自动化学报,2011,37(10):1157-1166.(Wang Zhongjie,Xie Lulu.Cyber-physical

systems: A survey [J]. Acta Automatica Sinica,2011，37(10): 1157-1166. )   
[2]Baheti R,Gill H. Cyber-physical systems [J]. The Impact of Control Technology,2011,12(1): 161-166.   
[3] Burg A, Chattopadhyay A, Lam K Y.Wireless communication and security Issues for cyber-physical systems and the internet-of-things [J]. Proceedings of the IEEE,2018,106(1): 38-60.   
[4]Chen Bo,Ho D W C,Hu Guoqiang,et al. Secure fusion estimation for bandwidth constrained cyber-physical systems under replay atacks [J]. IEEE Trans on Cybernetics,2018,48(6): 1862-1876.   
[5]Wolf M,Serpanos D. Safety and security in cyber-physical systems and internet-of-things systems [J]. Proceedings of the IEEE,2018,106(1): 9-20.   
[6] 陈功谱，曹向辉，孙长银．信息物理系统安全问题研究进展[J]．南 京信息工程大学学报，2017，9(4):372-380.(Chen Gongpu，Cao Xianghui, Sun Changyin.A survey on the security of cyber-physical systems [J]. Journal of Nanjing University of Information Science and Technology,2017,9(4): 372-380.）   
[7] Giraldo J， Sarkar E,Cardenas A，et al. Security and privacy in cyber-physical systems: a survey of surveys [J]. IEEE Design & Test, 2017, 34(4): 7-17.   
[8]Yucelen T,Haddad W M,Feron E M.Adaptive control architectures for mitigating sensor attacks in cyber-physical systems [J]. Cyber-Physical Systems,2016,2(1-4): 24-52.   
[9] Xie Chunhua,Yang Guanghong. Secure estimation for cyber-physical systems under adversarial actuator attacks [J]. IET Control Theory & Applications,2017,11(17): 2939-2946.   
[10] Jin Xu,Haddad W M, Yucelen T.An adaptive control architecture for mitigating sensor and actuator attcks in cyber-physical systems [J]. IEEE Trans on Automatic Control,2017,62(11): 6058-6064.   
[11]李炜，吴晰源，赵正天，等．同时考虑量化误差的网络化控制系统鲁 棒 H完整性设计 [J].计算机应用研究,2012,29(6):2120-2125.(Li Wei, Wu Xiyuan, Zhao Zhengtian,et al. Robust $\mathrm { H } { \infty }$ integrity design of networked control system with quantizing error [J].Application Research of Computers,2012,29(6): 2120-2125.）   
[12] Yun S W, Choi Y J,Park PG.H2 control of continuous-time uncertain linear systems with input quantization and matched disturbances [J]. Automatica,2009,45 (10): 2435-2439.   
[13] Zheng Bochao,Yang Guanghong.H2 control of linear uncertain systems considering input quantization with encoder/decoder mismatch [J]. ISA Trans,2013,52(5): 577-582.   
[14]屈百达，胥吉林，徐保国．不确定多时滞系统的鲁棒 $\mathrm { H } { \infty }$ 控制[J]. 计算机应用研究,2012,29(12):4577-4579.(Qu Baida,Xu Jilin,Xu Baoguo．Robust $\mathrm { H } \infty$ control for uncertain systems with multiple time-delay [J].Application Research of Computers，2012,29(12): 4577-4579. )   
[15] Petersen IR.A stabilization algorithm for a class of uncertain linear systems [J].Systems & Control Leters,1987,8(4): 351-357.