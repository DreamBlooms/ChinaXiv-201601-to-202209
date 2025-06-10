![](images/8321b32d010ea91805a07ef98b6f7cf81b7f908b63a1b0d0d9b8e0351d2d47ca.jpg)

单亚运男 1990年生，硕士研究生，研究方向为电力电子装置与系统。

摘要：本文提出以传统PI控制器为基础，结合广泛应用的模糊控制理论以及迅猛发展的分数阶控制理论，设计一种基于模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 的伺服控制器的设想，并在Simulink中搭建仿真模型验证其控制性能。仿真结果显示，本文设计的伺服控制器表现出更为优越的性能。对于高精度伺服系统而言，模糊自适应分数阶PI控制器能够满足其对控制性能的苛刻要求，具有一定的可行性。

关键词：传统PI控制 伺服系统 模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制Simulink中图分类号：TM383

# Research on Servo Control Strategy Based on Fuzzy Adaptive Fractional PI^

Shan Yayun Pang Kewang Liu Xuyu ( Jiangsu University of Science and TechnologyZhenjiang 212000 China）

![](images/0cf156ca2c6639f21b764a194cf331e1411b9fb9b0c186b5fb6cf61c7cfc50e7.jpg)

Abstract: This paper put forward a vision that designing a fuzzy adaptive fractional $\mathrm { P I } ^ { \lambda }$ controller based on the traditional PI control combining the widely used fuzzy control theory and the fast developing fractional theory. Meanwhile dynamic simulation for the feed servo system is done under the SIMULINK，which results show that the servo controller designed in this paper has superior control performance and the adaptive fuzzy fractional $\mathrm { P I } ^ { \lambda }$ can meet the control requirements of high precision servo system. The idea is feasible.

庞科旺男1963年生，副教授，硕士生导师，研究方向为大功率电力电子装置及自动化。

Keywords: Traditional PI control, servo control system, fuzzy adaptive fractional $\mathrm { P I } ^ { \hslash }$ ，Simulink

# 1 引言

伴随着技术的进步和工业化的不断发展，数控领域各个场合对伺服控制系统的要求也随之提高，基于传统PI控制策略的伺服系统已很难满足控制性能的要求。例如在经编机高速横移领域，对位置控制要求十分苛刻，因为位置偏差会引起花型扭曲，导致产品质量下降[1]。

交流伺服控制系统并非是完全线性的，系统内部各参数也在不停地改变，而且它的负载也不是一成不变的，模型也不是完全整数阶的，各种因素的影响使得系统的动态性能呈现很大的差异。传统PI调节器具有很差的自适性能力，在高精度和高可靠性的场合，它的控制性能根本不能达到预想的效果。模糊自适应PI控制器为典型的整数阶控制器，对于分数阶模型同样难以达到理想的控制性能。针对以上问题，文章将广泛引用的模糊自适应控制、近来发展迅猛的分数阶控制理论与当前应用最广的经典PI控制相结合，设计了一种新型的模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 交流伺服控制器[2-6]。最后在 Simulink 中搭建仿真模型，通过仿真验证其控制效果，经试验证实，其确有优越的控制性能。

# 2 永磁同步电机矢量模型

矢量控制是一种借助坐标变换实现对转矩更好控制的高性能交流电机控制技术，坐标变换方法包含Clark 和Park变换两种[7]。永磁同步电机经过坐标变换后得到在dq坐标系中定子电压方程和磁链方程

$$
\left\{ \begin{array} { l } { \displaystyle u _ { \mathrm { d } } = R _ { \mathrm { s } } i _ { \mathrm { d } } + \frac { \mathrm { d } \psi _ { \mathrm { d } } } { \mathrm { d } t } - \omega _ { \mathrm { r } } \varPsi _ { \mathrm { q } } } \\ { \displaystyle u _ { \mathrm { q } } = R _ { \mathrm { s } } i _ { \mathrm { q } } + \frac { \mathrm { d } \psi _ { \mathrm { q } } } { \mathrm { d } t } + \omega _ { \mathrm { r } } \varPsi _ { \mathrm { d } } } \end{array} \right.
$$

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { \boldsymbol { \psi } _ { \mathrm { d } } = L _ { \mathrm { d } } \boldsymbol { i } _ { \mathrm { d } } + \boldsymbol { \psi } _ { \mathrm { f } } } \\ { \left| \boldsymbol { \psi } _ { \mathrm { q } } = L _ { \mathrm { q } } \boldsymbol { i } _ { \mathrm { q } } \right. } \end{array} \right. } \end{array}
$$

式中， $u _ { \mathrm { d } }$ ， $u _ { \mathrm { q } }$ 分别为定子电压矢量在dq轴的分量；$i _ { \mathrm { d } }$ 、 $i _ { \mathrm { q } }$ 分别为定子电流矢量在dq轴的分量； $\psi _ { \mathrm { d } }$ 、 $\psi _ { \mathrm { q } }$ 分别为定子磁链在dq轴的分量； $L _ { \mathrm { d } }$ ， $L _ { \mathrm { q } }$ 分别为dq轴的同步电感； $R _ { \mathrm { s } }$ 为定子每相绕组电阻； $\omega _ { \mathrm { r } }$ 为转子旋转的电角度； $\psi _ { \mathrm { f } }$ 为转子磁链。

转矩方程和运动方程为

$$
T _ { \mathrm { e } } = p _ { \mathrm { n } } ( \psi _ { \mathrm { d } } i _ { \mathrm { q } } - \psi _ { \mathrm { q } } i _ { \mathrm { d } } )
$$

$$
\frac { J } { p _ { \mathrm { n } } } \frac { \mathrm { d } \omega _ { \mathrm { r } } } { \mathrm { d } t } = T _ { \mathrm { e } } - B \frac { \omega _ { \mathrm { r } } } { p _ { \mathrm { n } } } - T _ { \mathrm { L } }
$$

式中， ${ p } _ { \mathrm { n } }$ 为电机磁极对数； $T _ { \mathrm { L } }$ 为负载转矩； $B$ 为黏滞摩擦系数； $J$ 为转动惯量。

从转子坐标来看，经过坐标变换后的三相定子电流最终被等效为力矩电流 $i _ { \mathrm { q } }$ 和励磁电流 $i _ { \mathrm { d } }$ 两个分量。矢量控制有多种不同的控制方式，本文采用 $i _ { \mathrm { d } } =$ 0控制，这种方式可以使电机输出平稳而又最大的转矩。此时得到的电机转矩方程为

$$
T _ { \mathrm { e } } = p _ { \mathrm { n } } \varPsi _ { \mathrm { d } } i _ { \mathrm { d } } = \frac { 3 } { 2 } p _ { \mathrm { n } } \varPsi _ { \mathrm { f } } i _ { \mathrm { q } }
$$

由式（5）可知， $p _ { \mathrm { n } }$ 和 $\psi _ { \mathrm { f } }$ 是永磁同步电机的内部参数，其值固定。为了获得恒定的力矩输出，只要控制 $i _ { \mathrm { q } }$ 为定值即可。

# 3模糊自适应分数阶 $\mathbf { P I } ^ { \lambda }$ 控制器

# 3.1分数阶微积分理论

分数阶微积分是一个古老而又新颖的研究课题，古老是指它的定义由来已久，而新颖指的是它的应用历史非常短暂，直到最近才被大家所关注。分数阶与整数阶微积分最大的不同点，即最重要的特征是，它的微积分算子并不是固定不变的整数阶次，它有可能是分数阶的，更广地来说，它是任意阶的。Grunwald-Letnikov和Riemann-Liouville 是出 现频率最高的两种分数阶微积分定义。 ${ } _ { a } D _ { t } ^ { \alpha }$ 为描述分数阶微分与积分算子， $\boldsymbol { a }$ 和 $t$ 为在微积分求解时变量取值的上下限， $\alpha$ 为算子阶次。

（1）Grunwald-Letnikov分数阶微积分定义为

$$
\begin{array} { l } { { \displaystyle _ { a } D _ { t } ^ { \alpha } f ( t ) = \operatorname* { l i m } _ { h \to \infty } h ^ { - \alpha } \sum _ { j = 0 } ^ { ( t - a ) / h } ( - 1 ) ^ { j } \binom { \alpha } { j } f ( t - j h ) } } \\ { { \displaystyle = \operatorname* { l i m } _ { h \to 0 } \frac { 1 } { \Gamma ( \alpha ) h ^ { \alpha } } \sum _ { j = 0 } ^ { ( t - a ) / h } \frac { \Gamma ( \alpha + j ) } { \Gamma ( j + 1 ) } f ( t - j h ) } } \end{array}
$$

(2）Riemann-Liouville分数阶微积分定义为

$$
{ } _ { a } D _ { t } ^ { \alpha } f ( t ) = { \frac { 1 } { \Gamma ( m - \alpha ) } } { \left( { \frac { \mathrm { d } } { \mathrm { d } t } } \right) } ^ { m } \int _ { a } ^ { t } { \frac { f ( \tau ) } { ( t - \tau ) ^ { 1 - ( m - \alpha ) } } } \mathrm { d } \tau
$$

式中， $m - 1 < \alpha < m$ ， $m { \in } N ,$ 0

# 3.2传统PID 控制器

PID控制的微分方程如式（8）所示，式中，$e ( t )$ 为系统给定值与反馈值之间的偏差量。

$$
u ( t ) = K _ { \mathrm { p } } \left[ e ( t ) + \frac { 1 } { T _ { \mathrm { i } } } { \int _ { 0 } ^ { t } } e ( \tau ) \mathrm { d } \tau + \frac { T _ { \mathrm { d } } \mathrm { d } e ( t ) } { \mathrm { d } t } \right]
$$

进行拉普拉斯变换得传递函数为

$$
G _ { \mathrm { c } } \left( s \right) = K _ { \mathrm { p } } + K _ { \mathrm { i } } \frac { 1 } { s } + K _ { \mathrm { d } } s
$$

式中， $K _ { \mathfrak { p } }$ 为比例系数； $T _ { \mathrm { i } }$ 为积分时间常数； $T _ { \mathrm { d } }$ 为微分时间常数。

PID 控制器由比例、积分、微分三个环节组成。比例环节有减小偏差的作用，但是存在稳态误差；积分环节能够消除稳态误差，但是会降低系统稳定性和动态响应速度；微分环节能够超前作用于偏差，提高系统动态性能，能够降低超调量。

# 3.3分数阶 $\mathbf { P I } ^ { \mathsf { \lambda } } \mathbf { D } ^ { \mathsf { \mu } }$ 控制器

分数阶 $\mathrm { P I } ^ { \lambda } \mathrm { D } ^ { \mu }$ 控制器的微分方程为

$$
u ( t ) = K _ { \mathrm { p } } e ( t ) + K _ { \mathrm { i } } D _ { t } ^ { - \lambda } e ( t ) + K _ { \mathrm { d } } D _ { t } ^ { \mu } e ( t )
$$

式中， $\lambda > 0$ ， $\mu > 0$ 为任意实数， $\lambda$ 、 $\mu$ 分别为分数阶控制器积分和微分环节的阶次； $K _ { \mathfrak { p } }$ ， $K _ { \mathrm { i } }$ ， $K _ { \mathrm { d } }$ 是控制器的比例、积分、微分系数。进行拉普拉斯变换得传递函数为

$$
G _ { \mathrm { { c } } } ( s ) = K _ { \mathrm { { p } } } + K _ { \mathrm { { i } } } s ^ { - \lambda } + K _ { \mathrm { { d } } } s ^ { \mu }
$$

分数阶 $\mathrm { P I } ^ { \lambda } \mathrm { D } ^ { \mu }$ 与传统PID相比增加了两个可调参数 $\lambda$ 、 $\mu$ ，扩大了参数的可调节范围，拓宽了分数阶 $\mathrm { P I } ^ { \lambda } \mathrm { D } ^ { \mu }$ 控制器的应用领域，控制器的应用方式也变得更加灵活多变，但同时也带来了参数整定困难的问题。

# 3.4分数阶微积分的数字实现

分数阶毫无疑问不是一个简单系统，无法用有限的维度简单描述它，它的复杂程度决定了整数阶的控制方法不能直接应用于分数阶系统。面对这一情况，数学家们并没有知难而退，他们另辟蹊径，既然无法直接描述分数阶系统，那么就通过有限的微分方程近似地将它描述出来。本文所采用的逼近方法是Oustaloup方法，它属于间接近似化中的一种。

Oustaloup方法近似的传递函数形式为

$$
H ( s ) = \left( { \frac { s } { \omega _ { _ { \mu } } } } \right) ^ { \alpha } \quad \alpha \in R ^ { + }
$$

在给定频段 $[ \omega _ { \mathrm { A } } , \omega _ { \mathrm { B } } ]$ 内，用 $C _ { 0 } [ ( 1 + s / \omega _ { \mathrm { b } } ) / ( 1 + s / $

$\omega _ { \mathrm { h } } ) ]$ 来代替 $s / \omega _ { \mu }$ ，其中， $\left( \omega _ { \mathrm { b } } \omega _ { \mathrm { h } } \right) ^ { 1 / 2 } = \omega _ { \mu }$ ， $\omega _ { \mathrm { b } } < \omega _ { \mathrm { A } }$ ，$\omega _ { \mathrm { h } } > \omega _ { \mathrm { B } }$ ，且 $C _ { 0 } = \omega _ { \mathrm { b } } / \omega _ { \mathrm { \mu } } = \omega _ { \mathrm { \mu } } / \omega _ { \mathrm { h } }$ ，那么传递函数就能表示成

$$
H ( s ) = C \left( \frac { 1 + s / \omega _ { \mathrm { b } } } { 1 + s / \omega _ { \mathrm { h } } } \right) ^ { \alpha }
$$

式中， $C = C _ { 0 } ^ { \alpha }$ 。

把式（13）写成零点、极点的形式，得到表达式

$$
H ( s ) = \operatorname* { l i m } _ { n  \infty } \hat { H } ( s )
$$

式中

$$
\hat { H } ( s ) = \left( \frac { \omega _ { \mathrm { \scriptscriptstyle u } } } { \omega _ { \mathrm { h } } } \right) ^ { \alpha } \prod _ { k = - N } ^ { N } \frac { 1 + s ~ / \omega _ { \mathrm { k } } ^ { \prime } } { 1 + s ~ / \omega _ { \mathrm { k } } }
$$

可求得

$$
\begin{array} { r l } & { \omega _ { \mathrm { k } } ^ { \prime } = \omega _ { \mathrm { b } } \left( \frac { \omega _ { \mathrm { h } } } { \omega _ { \mathrm { b } } } \right) ^ { \frac { k + N + 0 . 5 ( 1 - \alpha ) } { 2 N + 1 } } } \\ & { \omega _ { \mathrm { k } } = \omega _ { \mathrm { b } } \left( \frac { \omega _ { \mathrm { h } } } { \omega _ { \mathrm { b } } } \right) ^ { \frac { k + N + 0 . 5 ( 1 + \alpha ) } { 2 N + 1 } } } \end{array}
$$

# 3.5模糊自适应分数阶 $\mathbf { P I } ^ { \lambda }$ 控制器设计

模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器如图1所示。

![](images/9f9bd49b79b8fa7f61a318649ca33cff8858085011ead3f3a6db5049ca3e28b2.jpg)  
图1模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器结构图Fig.1Fuzzy adaptive fractional $\mathrm { P I } ^ { \lambda }$ chart

本文模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器的设计思路是，在分数阶 $\mathrm { P I } ^ { \lambda }$ 控制回路中引入模糊推理模块，通过模糊控制规则周期性地推理出每个参数的当前值，再将本周期的参数值实时传递给分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器，从而实现参数在线整定。模糊推理模块输入变量为偏差 $e$ 及其变化率 $e c$ ，输出变量 $\Delta K _ { \mathrm { p } }$ ，$\Delta K _ { \mathrm { i } }$ 、λ，各变量的模糊子集选取相同的 $\{$ 正大、正中、正小、零、负小、负中、负大}，记为 $\{ \mathrm { P B }$ ，PM、PS、ZO、NS、NM、 $\mathrm { N B } \}$ ，选取输入变量 $e$ ，$e c$ 的论域为[-3,3]，输出变量 $\Delta K _ { \mathrm { p } }$ 、 $\Delta K _ { \mathrm { i } }$ 的论域为$[ - 3 , 3 ]$ ，输出变量λ的论域为[0,1]。输入变量 $\boldsymbol { \mathscr { e } }$ 和$e c$ 的隶属度函数采用高斯型隶属函数，输出变量$\Delta K _ { \mathrm { p } }$ 、 $\Delta K _ { \mathrm { i } }$ 、λ的隶属度函数采用对称分布的三角型隶属函数，隶属度函数如图2所示。

![](images/4783ddb197c1900d0e63a9f753750d64fdd575bed08227871447602caff1d707.jpg)  
图2模糊变量隶属度函数

确定好输入输出的隶属度函数之后，开始模糊控制规则的编写工作。模糊控制规则由一系列的条件连接词组成，使用最频繁的条件语句是if_then语句，本次研究即采用此语句，写出格式如下式所示的模糊规则，总共49条；并将其制成表格，最终结果见表1～表3。

if ( $\scriptstyle { \mathcal { e } }$ is NB) and ( $\stackrel { \cdot } { e c }$ is NB) then ( $k _ { \mathfrak { p } }$ is PB)( $k _ { \mathrm { i } }$ is NB)( $\lambda$ is PS)

基于Matlab/Simulink的模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器的模型如图3所示。模糊控制器的模糊逻辑推理采用Mamdani法则，去模糊化方法选择重心法。模糊控制器周期性输出推理值 $\Delta K _ { \mathrm { p } }$ 、 $\Delta K _ { \mathrm { i } }$ 、，$\Delta K _ { \mathrm { p } }$ ， $\Delta K _ { \mathrm { i } }$ 分别与参数预先设定值 $K _ { \mathfrak { p } }$ ， $K _ { \mathrm { i } }$ 相加， $\lambda$ 设置为全局变量，在模型中引入S-Function 模块，仿真过程中重复调用S函数，在S函数中添加修改变量入的代码指令，这样就能够将每个周期修改后的λ值带入到分数阶微积分模块中，实现阶次周期性修改，从而实现分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器参数 $K _ { \mathfrak { p } }$ ， $K _ { \mathrm { i } }$ 和 $\lambda$

表1 $\Delta K _ { \mathrm { p } }$ 的模糊规则表 Tab.1 （204号 $\Delta K _ { \mathrm { p } }$ Fuzzy rule table   

<html><body><table><tr><td>ec e</td><td>NB</td><td>NM</td><td>NS</td><td>ZO</td><td>PS</td><td>PM</td><td>PB</td></tr><tr><td>NB</td><td>PB</td><td>PB</td><td>PM</td><td>PM</td><td>PS</td><td>ZO</td><td>ZO</td></tr><tr><td>NM</td><td>PB</td><td>PB</td><td>PM</td><td>PS</td><td>PS</td><td>ZO</td><td>NS</td></tr><tr><td>NS</td><td>PM</td><td>PM</td><td>PM</td><td>PS</td><td>ZO</td><td>NS</td><td>NS</td></tr><tr><td>ZO</td><td>PM</td><td>PM</td><td>PS</td><td>ZO</td><td>NS</td><td>NM</td><td>NM</td></tr><tr><td>PS</td><td>PS</td><td>PS</td><td>ZO</td><td>NS</td><td>NS</td><td>NM</td><td>NM</td></tr><tr><td>PM</td><td>PS</td><td>ZO</td><td>NS</td><td>NM</td><td>NM</td><td>NM</td><td>NB</td></tr><tr><td>PB</td><td>ZO</td><td>ZO</td><td>NM</td><td>NM</td><td>NM</td><td>NB</td><td>NB</td></tr></table></body></html>

Tab.2 $\Delta K _ { \mathrm { i } }$ Fuzzyrule table   
表3λ的模糊规则表  

<html><body><table><tr><td>ec e</td><td>NB</td><td>NM</td><td>NS</td><td>ZO</td><td>PS</td><td>PM</td><td>PB</td></tr><tr><td>NB</td><td>NB</td><td>NB</td><td>NM</td><td>NM</td><td>NS</td><td>ZO</td><td>ZO</td></tr><tr><td>NM</td><td>NB</td><td>NB</td><td>NM</td><td>NS</td><td>NS</td><td>ZO</td><td>NS</td></tr><tr><td>NS</td><td>NB</td><td>NM</td><td>NS</td><td>NS</td><td>ZO</td><td>PS</td><td>PS</td></tr><tr><td>ZO</td><td>NM</td><td>NM</td><td>NS</td><td>ZO</td><td>PS</td><td>PM</td><td>PM</td></tr><tr><td>PS</td><td>NM</td><td>NS</td><td>ZO</td><td>PS</td><td>PS</td><td>PM</td><td>PB</td></tr><tr><td>PM</td><td>ZO</td><td>ZO</td><td>PS</td><td>PS</td><td>PM</td><td>PB</td><td>PB</td></tr><tr><td>PB</td><td>ZO</td><td>ZO</td><td>PS</td><td>PM</td><td>PM</td><td>PB</td><td>PB</td></tr></table></body></html>

表2 $\Delta K _ { \mathrm { i } }$ 的模糊规则表  
Tab.3λ Fuzzy rule table   

<html><body><table><tr><td>ec e</td><td>NB</td><td>NM</td><td>NS</td><td>ZO</td><td>PS</td><td>PM</td><td>PB</td></tr><tr><td>NB</td><td>PS</td><td>NS</td><td>NB</td><td>NB</td><td>NB</td><td>NM</td><td>PS</td></tr><tr><td>NM</td><td>PS</td><td>NS</td><td>NB</td><td>NM</td><td>NM</td><td>NS</td><td>ZO</td></tr><tr><td>NS</td><td>ZO</td><td>NS</td><td>NM</td><td>NM</td><td>NS</td><td>NS</td><td>ZO</td></tr><tr><td>ZO</td><td>ZO</td><td>NS</td><td>NS</td><td>NS</td><td>NS</td><td>NS</td><td>ZO</td></tr><tr><td>PS</td><td>ZO</td><td>ZO</td><td>ZO</td><td>ZO</td><td>ZO</td><td>ZO</td><td>ZO</td></tr><tr><td>PM</td><td>PB</td><td>NS</td><td>PS</td><td>PS</td><td>PS</td><td>PS</td><td>PB</td></tr><tr><td>PB</td><td>PB</td><td>PM</td><td>PM</td><td>PM</td><td>PS</td><td>PS</td><td>PB</td></tr></table></body></html>

![](images/392a5df4880686953e952638f4503dc9c4f3fea6295a015eca908dad132d4223.jpg)  
Fig.2Fuzzy variable membership function   
图3模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器模型  
Fig.3Fuzzy adaptive fractional $\mathrm { P I } ^ { \mathrm { \lambda } ^ { \mathrm { \lambda } } }$ controller model

的在线整定。

# 4 系统仿真

根据所建立的永磁同步电机矢量控制模型，利用Matlab的Simulink建立了基于模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器的交流伺服控制仿真系统，如图4所示。

![](images/5396ab42338c018ab89de36766fab48a0ed81709fba34b4d3d571f2e0b3932cb.jpg)  
图4基于模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器的交流伺服控制仿真图  
Fig.4Servo control strategy based on fuzzy adaptive fractional $\mathrm { P I } ^ { \lambda }$ simulation chart

仿真系统由位置调节器、转速调节器、电流调节器，Park 逆变换模块、SVPWM模块[8]、永磁同步电机、参数测量模块、Clark 模块、Park模块等组成。系统采用位置、转速和电流三闭环控制方式，内部两控制环均采用数字PI控制器，最外环为位置环，采用本次设计的模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器作为位置调节器。位置给定 $\boldsymbol { \theta } ^ { * }$ 在与转子实际位置 $\theta$ 相比较并求出偏差值后，作为输入变量通过模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器，输出转速给定值 $\omega ^ { * }$ ，与转速测量值 $\omega$ 比较并求出偏差值后，作为输入通过PI控制器，经调节后输出力矩电流给定值 $i _ { \mathrm { q } } ^ { * }$ ，本文矢量控制选择最大转矩方式，取励磁电流给定值 $i _ { \mathrm { d } } ^ { * } = 0$ 。三相电流测量值 $i _ { \mathrm { a } }$ 、 $i _ { \mathrm { b } }$ 和 $i _ { \mathrm { c } }$ 经Clark和Park坐标变换后得到直、交轴电流反馈值 $i _ { \mathrm { q } }$ ， $i _ { \mathrm { d } }$ ，分别与前一步骤确定的力矩电流和励磁电流作比较并求出偏差值，经过电流调节器的调节和电流型逆变器后控制电机三相电流，从而完成对伺服电机的位置控制。

永磁同步电机采用的参数如下：定子绕组电阻 $R _ { \mathrm { s } } = 0 . 6 2 \Omega$ ，d相绕组电感 $L _ { \mathrm { d } } = 0 . 0 0 8 ~ 5 \mathrm { H }$ ，q相绕组电感 $L _ { \mathrm { q } } = 0 . 0 0 8 ~ 5 \mathrm { H }$ ，转子磁场磁通 $\psi _ { \mathrm { f } } = 0 . 1 7 5 \mathrm { W b }$ ，转动惯量 $J = 0 . 0 0 8 \mathrm { k g \cdot m } ^ { 2 }$ ，极对数 $p = 4$ ， $B = 0$ 。仿真系统采用ode3模式，仿真时间选择为 $0 \sim 1 0 \mathrm { s }$ ，比较传统PI和模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器对伺服位置控制阶跃响应的控制效果。

两种控制器作用下伺服系统位置控制的阶跃响应曲线如图5所示。点线是传统PI控制器作用的伺服系统位置控制运行曲线图，单线是模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器作用的伺服系统位置控制运行曲线图。根据图5获得的数据，计算并列出两种控制方式的性能对比见表4。

![](images/bc89b7e113b24cd7168386e470ad554b7d16346bbb89ac49ecfb1f32bcdffe79.jpg)  
图5模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制与PI控制下伺服位置控制阶跃响应曲线图  
Fig.5Fuzzy adaptive fractional $\mathrm { P I } ^ { \lambda }$ and PI control result chart

表4两种位置控制器的性能对照表  
Tab.4Performance comparison table of two position controllers   

<html><body><table><tr><td>控制器</td><td>上升时间 /s</td><td>超调量 (%)</td><td>调节时间 /s</td></tr><tr><td>传统PI控制器</td><td>0.790</td><td>19.3</td><td>5.6</td></tr><tr><td>模糊自适应分数阶PI控制器</td><td>0.745</td><td>1.3</td><td>4.8</td></tr></table></body></html>

通过表4各控制性能的数据对比可知，基于模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器的交流伺服控制系统大幅度地降低了超调量，具有更快的响应速度和更好的控制效果，其动态性、稳态性及鲁棒性都远优于传统PI控制的交流伺服系统。

# 5 结论

本文以提高交流伺服系统控制性能为最终目标，设计了一种基于模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 的伺服控制器。其设计理念是在分数阶 $\mathrm { P I } ^ { \lambda }$ 控制回路中引入模糊推理模块，运用模糊推理规则，得出推理结果，引用结果实时修改分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器参数。分数阶$\mathrm { P I } ^ { \lambda }$ 控制器增加的可调参数入，扩大了参数的可调节范围，拓宽了分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器的应用领域，与此同时也使得它的应用方式变得更加灵活多变。此次研究工作的最后，根据建立的电机矢量模型，使用Simulink搭建了位置、转速及电流三闭环仿真系统，分别采用数字PI和模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器作为位置环调节器进行仿真实验，仿真研究结果表明：模糊自适应分数阶 $\mathrm { P I } ^ { \hslash }$ 控制器产生了更小的超调量，具有更快的响应速度和更好的控制效果，其动态性、稳态性及鲁棒性都远优于传统PI控制的交流伺服系统。对于高精度伺服系统而言，基于模糊自适应分数阶 $\mathrm { P I } ^ { \lambda }$ 控制器的伺服系统能够满足其苛刻的控制要求，是一个可行的方案。

参考文献  
[1] 郭俊华，蒋高明，夏风林．基于伺服控制经编机电子横移系统的研究[J]．针织工业，2007(5)：14-16, 71.Guo Junhua, Jiang Gaoming, Xia Fenglin. Researchon electronic sway system of warp kniting machinebased on servo control[J]. Kniting Industries,2007(5): 14-16, 71.  
[2]窦艳艳，钱蕾，冯金龙．基于Matlab的模糊PID控制系统设计及仿真[J]．电子科技，2015,28(2): 119-112.Dou Yanyan, Qian Lei, Feng Jinlong. Design andsimulation of fuzzy PID control system based onMatlab[J].Electronic Technology, 2015,28(2):119-112.  
[3] 孙书诚，郎朗，陈孟元．模糊自适应PID控制器在交流伺服控制系统中的研究[J]．长春工程学院学报（自然科学版），2012，13(2)：39-42.Sun Shucheng,Lang Lang,Chen Mengyuan.Research on AC servo control system basedonfuzzy adaptive PID controller[J]. Journal ofChangchun Institute of Technology(Natural ScienceEdition),2012,13(2): 39-42.  
[4] 赵春娜，李英顺，陆涛．分数阶系统分析与设计[M].北京：国防工业出版社，2011：42-48.  
[5] Jun Liu, Qian Weixie.Research on the fuzzy PIDspeed control system of permanent magnet linearsynchronous motor based on genetic algorithm[J].Applied Mechanics and Materials, 2014, 2963(494):1582-1586.  
[6] 王思明，王欢．分数阶PID 控制器的设计及仿真[J].现代防御技术，2015，43(6)：204-208.Wang Siming,Wang Huan.Design and simulation offractional-order PID controller[J]. Modern DefenceTechnology,2015,43(6): 204-208.  
[7] 齐乃明，宋志国，秦昌茂．基于最优Oustaloup的分数阶PID参数整定[J]．控制工程，2012,19(2): 283-285.Qi Naiming, Song Zhiguo, Qin Changmao.Fractional-order PID parameter tuning based on optimaloustaloup[J]. Control Engineering, 2012,19(2): 283-285.  
[8] 刘晓黎．基于永磁同步电机数学模型的矢量控制

理论、仿真、实验及应用研究[D]．合肥：合肥工业大学，2017：19-22.[9] 隋峻，王晶，樊键，等．SVPWM在永磁同步电机系统中的应用与仿真[J]．兵工自动化，2011，30(3):55-58.

Sui Jun,Wang Jing,Fan Jian,et al.Application andsimulation of permanent magnet in PMSM system[J].Ordnance Industry Automation,2011,30(3):55-58.[10] 刘金琨．先进PID控制MATLAB仿真[M]．北京：电子工业出版社，2004.