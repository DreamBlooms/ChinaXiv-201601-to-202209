# 基于转矩平衡的自适应电子差速控制策略研究

吕长吉　张炳义　冯桂宏（沈阳工业大学辽宁省特种电机与高压电器重点实验室 沈阳110870）

![](images/3c60d4b0c1fe0c340530d30119bca314815cd80d985e34db631c6e12f80d6f1f.jpg)

吕长吉男 1990年生，硕士，主要研究方向为电机及其控制。

摘要：针对电动汽车电子差速系统，通过对永磁电机和传统的机械差速转向方式进行理论研究分析，提出了基于两台永磁电机作为驱动电机的转矩平衡自适应控制方案。针对现有的电子差速方案在复杂情况下的路面无法进行有效控制的问题，本文参照传统的机械差速给出了解决方案，计算了转向时各个车轮的速度与转向角度变化的关系，以及转向时各个车轮的转速、功率分配关系，给出了各个车轮协调工作的控制方法，从而确定了电子差速的控制策略。

关键词：电动汽车电子差速 转矩平衡 自适应协调工作 功率分配中图分类号：TM351

# Study of Adaptive Electronic Differential Control Strategy Based on Torque-Balance

![](images/6ba79f29b00fad1250055e618c336e489f4ad06edb09d0eee258fb1414e5c066.jpg)

张炳义男 1954年生，教授，博士生导师，主要研究方向为特种电机及其控制、电力系统自动化。

Lu Changji Zhang Bingyi Feng Guihong (Shenyang University of Technology Key Laboratory of Special Motor and High Voltage Electrical Apparatus ofLiaoning ProvinceShenyang11o870China ）

Abstract: In order to realize the electronic differential(ED) system of electric vehicle(EV), through the study of permanent magnet synchronous motor (PMSM) and traditional mechanical differential,a torque-balance adaptive control method based on PMSM is proposed.For the existing electronic differential method in the complex road conditions can not be effective control, the solution is given with reference to the traditional mechanical differential. The relationship between the speed of each wheel and the change of steering angle is calculated, the speed and power distribution of each wheel are calculated. The control method of each wheel coordination work is given,and the control strategy of electronic difference is determined,and simulated under the Simulink platform.The simulation results show that the electronic differential system can realize the stable steering and straight running of the EV.

Keywords: Electric vehicle, electronic differential, torque-balance, self-adaption, coordination work,power distribution

# 1 引言

所谓电子差速（Electronic Differential，ED）是指完全采用电控的方式来控制每个车轮的转速，让车轮形成速度差从而使整车实现转向。电子差速采用电控的方式，省去了大量的机械传动结构，减少了能量损失，提升了电动汽车的运行效率[1]。我国稀土资源丰富，在电动汽车上使用永磁电机逐渐成为主流，永磁电机具有结构简单，体积小、质量轻、损耗小、效率高及功率因数高等优点，在电动汽车上的应用前景非常广阔。

本文设计的电子差速系统采用轮边直驱的方式，使用永磁电机直接驱动车轮，使输出的转矩直接输送到车轮，省去了传统的离合器等机械结构，降低了整车的质量，简化了机械结构，降低了机械损耗，行驶性能得到显著提高。

本文对一辆传统SUV车型进行改装，保留了加速踏板和制动踏板，对转向系统及动力系统进行了改装，动力方面采用两台独立的永磁电机直接进行驱动，转向方面用电子差速替代了传统的机械差速。同时进行了相关仿真和实验，取得了较好的结果，验证了所设计的电子差速系统是可行的。

# 2 轮边驱动电动汽车结构

轮边驱动汽车结构示意图如图1所示，整车由两台30kW的高效永磁电机作为驱动动力，用磷酸铁锂电池作为动力源，前轮作为驱动轮和转向轮，后轮作为从动轮。整车控制器通过接收驾驶员的控制指令，如加速踏板动作，制动踏板动作，方向盘转向等，每个指令下达，控制器都会对电机做出相应的控制，转向时通过计算两个电机需要的不同的转速，使两个车轮形成速度差来实现转向。

![](images/b77c937e9d4ae13c166f475e6d2ce207043fe4beed7e9a1c3314715d597157a1.jpg)  
图1轮边驱动电动汽车结构示意图  
Fig.1Design of wheel-driven electric vehicle

# 3 车辆动力学方程

# 3.1整车动力学方程

本文针对轮边驱动的电子差速系统的实现方式进行研究，假设车体是刚性，选取横向、纵向和侧向三个自由度建立车辆动力学方程为

$$
\begin{array} { r } { m ( \dot { \nu } _ { x } - \nu _ { y } \gamma ) = F _ { x \mathrm { r } 1 } + F _ { x \mathrm { r } \mathrm { r } } - F _ { y \mathrm { f l } } \sin \delta _ { \mathrm { i n } } F _ { y \mathrm { f r } } \sin \delta _ { \mathrm { o u t } } - } \\ { f m g \cos \alpha - \cfrac { 1 } { 2 } F _ { \mathrm { D } } A \rho \nu ^ { 2 } - m g \sin \alpha } \end{array}
$$

$$
m ( \nu _ { y } - \nu _ { x } \gamma ) = F _ { y \mathrm { f l } } \cos \delta _ { \mathrm { i n } } + F _ { y \mathrm { f r } } \cos \delta _ { \mathrm { o u t } } + F _ { y \mathrm { r l } } + F _ { y \mathrm { r r } }
$$

$$
\begin{array} { r } { I _ { \mathrm { Z } } \dot { \gamma } = l _ { \mathrm { f } } \left( F _ { \mathrm { y f l } } \cos \delta _ { \mathrm { i n } } + F _ { \mathrm { y f r } } \cos \delta _ { \mathrm { o u t } } \right) - l _ { \mathrm { b } } \left( F _ { \mathrm { y r l } } + F _ { \mathrm { y r r } } \right) + } \\ { \displaystyle \frac { d _ { \mathrm { f } } } { 2 } ( F _ { \mathrm { y f r } } \sin \delta _ { \mathrm { o u t } } - F _ { \mathrm { y f l } } \sin \delta _ { \mathrm { i n } } ) + \frac { d _ { \mathrm { r } } } { 2 } ( F _ { \mathrm { x r r } } + F _ { \mathrm { x r l } } ) } \end{array}
$$

式中， $m$ 为整车质量； $\nu _ { x } , \nu _ { y }$ 分别是整车纵向、侧向的速度； $\mathbf { \sigma } _ { \nu }$ 为整车车速，且 $\nu = \sqrt { \nu _ { x } ^ { 2 } + \nu _ { y } ^ { 2 } }$ ; $F _ { x }$ ， $F _ { y }$ 分别为车轮所受的纵向力和横向力； $\delta _ { \mathrm { i n } }$ ， $\delta _ { \mathrm { o u t } }$ 分别为前轮内、外转向角； $f$ 为车轮滚动阻力系数； $g$ 为重力加速度； $\scriptstyle { a }$ 为车辆爬坡角； $F _ { \mathrm { D } }$ 为空气阻力系数；$A$ 为车辆迎风面积； $\rho$ 为空气密度； $l _ { \mathrm { f } }$ 和 $l _ { \mathrm { b } }$ 分别为汽车质心到前后轴的距离； $d _ { \mathrm { f } }$ 和 $d _ { \mathrm { r } }$ 为前后轴车轮轮距； $I _ { \mathrm { Z } }$ 为车辆的转动惯量； $\gamma$ 为横摆角速度。

# 3.2车轮动力学方程

车轮受力方程为

$$
T _ { \mathrm { m } } = T _ { \mathrm { r } } = J _ { \mathrm { m } } { \frac { \mathrm { d } \omega _ { \mathrm { m } } } { \mathrm { d } t } }
$$

式中， $T _ { \mathrm { m } }$ 为单个电机的转矩； $T _ { \mathrm { r } }$ 为车轮的阻力矩，且 $T _ { \mathrm { r } } = F _ { \mathrm { t } } r d$ ， $\boldsymbol { F } _ { \mathrm { t } }$ 为驱动力， $\boldsymbol { r }$ 为车轮半径； $J _ { \mathrm { { m } } }$ 为折算到电机的转动惯量。

向心力可表示为

$$
F = m \nu ( \gamma + { \dot { \beta } } )
$$

轮胎的垂直载荷为[5]

$$
\left\{ \begin{array} { l l } { \displaystyle N _ { \mathrm { t } } = \frac { l _ { \mathrm { r } } } { 2 ( l _ { \mathrm { t } } + l _ { \mathrm { r } } ) } \bigg ( m g - \frac { 2 h F _ { \mathrm { c } } } { d _ { \mathrm { t } } } \bigg ) } \\ { \displaystyle N _ { \mathrm { t r } } = \frac { l _ { \mathrm { r } } } { 2 ( l _ { \mathrm { t } } + l _ { \mathrm { r } } ) } \bigg ( m g + \frac { 2 h F _ { \mathrm { c } } } { d _ { \mathrm { t } } } \bigg ) } \\ { \displaystyle N _ { \mathrm { t } } = \frac { l _ { \mathrm { t } } } { 2 ( l _ { \mathrm { t } } + l _ { \mathrm { r } } ) } \bigg ( m g - \frac { 2 h F _ { \mathrm { c } } } { d _ { \mathrm { r } } } \bigg ) } \\ { \displaystyle N _ { \mathrm { r r } } = \frac { l _ { \mathrm { t } } } { 2 ( l _ { \mathrm { t } } + l _ { \mathrm { r } } ) } \bigg ( m g + \frac { 2 h F _ { \mathrm { c } } } { d _ { \mathrm { r } } } \bigg ) } \end{array} \right.
$$

其中， $h$ 为整车质心的高度。

轮胎侧偏角计算式为

$$
\left\{ \begin{array} { l l } { \displaystyle \alpha _ { \mathrm { f l } } = \beta + \frac { l _ { \mathrm { f } } \gamma } { \nu } - \delta _ { \mathrm { i n } } } \\ { \displaystyle \alpha _ { \mathrm { f r } } = \beta + \frac { l _ { \mathrm { f } } \gamma } { \nu } - \delta _ { \mathrm { o u t } } } \\ { \displaystyle \alpha _ { \mathrm { r i } } = \beta - \frac { l _ { \mathrm { f } } \gamma } { \nu } } \\ { \displaystyle \alpha _ { \mathrm { r i } } = \beta - \frac { l _ { \mathrm { f } } \gamma } { \nu } } \end{array} \right.
$$

其中，整车质心侧偏角 $\beta =$ arctan $( \nu _ { y } / \nu _ { x } )$ 。

轮胎纵向力和横向力计算式为

$$
\begin{array} { c } { \left\{ \begin{array} { c } { F _ { x 1 } = \mu _ { x 1 } N _ { \mathrm { l } } } \\ { F _ { y 1 } = C _ { \mathrm { l } } \alpha _ { \mathrm { l } } } \end{array} \right. } \end{array}
$$

其中， $\mu _ { x 1 }$ 和 $C _ { 1 }$ 为地面相关参数。

# 4 永磁同步电机方程

永磁同步电机具有体积小、功率密度高等特点，因而特别适合在电动汽车上使用，相同功率的电机，永磁同步电机体积更小，质量更轻。永磁同步电机电气特性方程如下[4]：

$$
\left\{ \begin{array} { l l } { \displaystyle \frac { \mathrm { d } } { \mathrm { d } t } i _ { d } = \frac { 1 } { L _ { d } } \nu _ { d } - \frac { R } { L _ { d } } i _ { d } + \frac { L _ { q } } { L _ { q } } p \omega _ { r } i _ { q } } \\ { \displaystyle \frac { \mathrm { d } } { \mathrm { d } t } i _ { q } = \frac { 1 } { L _ { q } } \nu _ { q } - \frac { R } { L _ { q } } i _ { q } - \frac { L _ { q } } { L _ { q } } p \omega _ { r } i _ { q } - \frac { \psi _ { \mathrm { f } } p \omega _ { \mathrm { r } } } { L _ { q } } } \\ { \displaystyle T _ { \mathrm { e } } = \frac { 3 } { 2 } p _ { \mathrm { n } } [ \Psi _ { \mathrm { f } } i _ { q } + ( L _ { d } - L _ { q } ) i _ { d } i _ { q } ] } \end{array} \right.
$$

式中， $L _ { \mathrm { d } }$ ， $L _ { \mathrm { q } }$ 分别为定子绕组交、直轴电感； $R$ 为定子绕组的电阻； $i _ { \mathrm { d } }$ 、 $i _ { \mathrm { q } }$ 分别为交、直轴电流； $\nu _ { d }$ ，$\nu _ { q }$ 分别为交、直轴电压； $\omega _ { \mathrm { r } }$ 为转子的角速度； $\psi _ { \mathrm { f } }$ 为磁链； $p _ { \mathrm { n } }$ 为磁极对数； $T _ { \mathrm { e } }$ 为电磁转矩。

机械特性方程为[4]

$$
\begin{array} { l } { \displaystyle \left[ \frac { \mathrm { d } } { \mathrm { d } t } \omega _ { \mathrm { r } } = \frac { 1 } { J } ( T _ { \mathrm { e } } - T _ { \mathrm { L } } - b \omega _ { \mathrm { m } } ) \right. } \\ { \displaystyle \left. \left[ \frac { \mathrm { d } \theta } { \mathrm { d } t } = \omega _ { \mathrm { r } } \right. \right. } \end{array}
$$

式中， $J$ 为转动惯量； $\theta$ 为转子转角位置； $b$ 为电机阻尼系数。

# 5 电子差速实现方式

电子差速通过接收驾驶者发出的指令，由控制器作用于永磁电机进而来改变车轮的速度，实现整车的转向。也即通过模拟电压以及位移传感器来实施整个指令。本文采用前置驱动方式，即前面两个车轮作为驱动轮和转向轮，后面两个车轮作为从动轮。只需对前面两个车轮进行速度控制来实现差速。

总控制器通过接收指令调节两个电机的转速，由于采用直驱的方式，调节电机的转速就是调节车的转速。当需要转弯时，调节两个电机的转速使左右车轮形成转速差，转向侧的车轮速度慢，外侧车轮速度较快，所以单位时间内外侧车轮行驶的路程比内侧车轮多，整车向转向侧转向，达到转向的目的。具体实现过程如下：转向时驾驶员转动方向盘此时是角度输出，通过位移传感器转换成电信号，传送给控制器，控制器查找转向和电机转速的关系从而确定转向时所需的电机转速，进一步分配电机的转速形成速度差，实现转向。

图2为简化的电子差速分析模型。本文研究电子差速系统在转向时车轮的速度和转向角的关系，假定车体是刚性的，车轮做纯滚动运动，不考虑滑移，忽略地面其他因素，忽略轮胎因素。简化模型涉及到的具体参数有： $\delta$ 为方向盘的转向角；$\delta _ { \mathrm { i n } }$ 为前内轮的转向角； $\delta _ { \mathrm { o u t } }$ 为前外轮转向角；W为车身宽度； $L$ 为车身长度； $R$ 为整车转弯半径；$R _ { \mathrm { i n } }$ 为内侧车轮转弯半径； $R _ { \mathrm { o u t } }$ 为外侧车轮转弯半径； $C _ { \mathrm { i n } }$ 为内侧车轮走过的距离； $C _ { \mathrm { o u t } }$ 为外侧车轮走过的距离； $V _ { \mathrm { c } }$ 为从动轮的线速度；VG为车辆的质心； $\Delta T$ 为车轮转过一圈所需要的时间，其计算式为

![](images/0db0ca6f9eb65e25b1db20b53a0b67e4877a65627c83e1a0831593dd80b66497.jpg)  
图2电子差速模型  
Fig.2Electronic differential model

$$
\left\{ \begin{array} { l l } { R = L / \tan \delta } \\ { R _ { i n } - R - \frac { b } { 2 } } \\ { R _ { i n } - R - \frac { b } { 2 } } \\ { R _ { i n } - R + \frac { b } { 2 } } \\ { K = \frac { R b } { 3 } } \\ { C _ { \mathrm { i n } } - 2 \pi R _ { i n } - 2 \pi R - n b } \\ { C _ { \mathrm { i n } } - 2 \pi R _ { i n } - 2 \pi R + n b } \\ { P _ { i n } - C _ { \mathrm { i n } } / \Delta T - 2 \pi R / \Delta T - \pi b / \Delta R - V _ { c } - K } \\ { V _ { \mathrm { t o n } } - C _ { \mathrm { i n } } / \Delta T - 2 \pi R / \Delta T - \pi b / \Delta R - V _ { c } + K } \end{array} \right.
$$

前轴内外车轮转向角可表示为[5]

$$
\left\{ \begin{array} { l l } { \delta _ { \mathrm { i n } } = \arctan \left\{ \frac { ( l _ { \mathrm { f } } + l _ { \mathrm { r } } ) \tan \delta } { l _ { \mathrm { f } } + l _ { \mathrm { r } } - \frac { L } { 2 } \tan \delta } \right\} } \\ { \delta _ { \mathrm { o u t } } = \arctan \left\{ \frac { ( l _ { \mathrm { f } } + l _ { \mathrm { r } } ) \tan \delta } { l _ { \mathrm { f } } + l _ { \mathrm { r } } + \frac { L } { 2 } \tan \delta } \right\} } \end{array} \right.
$$

式中， $L$ 为两主销线中心延长线到地面交点之间的距离。汽车在良好的路况上行驶时，正常转向此时车轮不发生滑动，四个车轮的角速度相对整车中心点相等，设角速度为 $\omega _ { 0 }$ ，前后轴的转弯半径是方向盘转角和轴距的函数[5]，即

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { V _ { \mathrm { i n } } = \nu ( 1 - \tan \delta W / L ) } \\ { V _ { \mathrm { o u t } } = \nu ( 1 + \tan \delta W / L ) } \end{array} \right. } \end{array}
$$

# 6 电子差速系统设计

实际中路况、轮胎因素很复杂，现在主流的控制方法有基于转速调节的控制方案、基于转矩的控制方案和基于滑移率的控制方案。这三种方案都存在弊端，基于转速调节的方案未考虑路面、轮胎、侧风等外界因素，假定为理想路面；基于转矩控制的方案由于调节的是转矩，路况复杂多变、变化时因不能实时调节转矩而不能达到控制要求；基于滑移率的控制方案，由于不同的路面条件下两个轮胎滑移率不一样而且不可预测，因此无法实时给出控制方案，同样无法达到转向的目的。

本文基于转速调节控制方法进行研究，传统汽车无论是直线行驶还是转向时两侧车轮转矩为平均分配，所以参照传统机械差速方式，对基于转速调节的电子差速方法进行改进，使本文设计的电子差速方法能够适应各种复杂路面状况。车辆直线行驶时控制器保持两个电机转速一致，由于采用直驱方式，控制两个电机的转速就是控制两个车轮的转速，两个车轮的转速保持一致，没有产生差速，左右两个车轮在单位时间内走过的路程相等，所以车辆将保持直线行驶。此时

$$
\left\{ \begin{array} { l } { R _ { \mathrm { a } } = \displaystyle \frac { l _ { \mathrm { f } } + l _ { \mathrm { r } } } { \sin { \bigg ( \displaystyle \frac { \delta _ { \mathrm { i n } } + \delta _ { \mathrm { o u t } } } { 2 } \bigg ) } } } \\ { R _ { \mathrm { b } } = \displaystyle \frac { l _ { \mathrm { f } } + l _ { \mathrm { r } } } { \tan { \bigg ( \displaystyle \frac { \delta _ { \mathrm { i n } } + \delta _ { \mathrm { o u t } } } { 2 } \bigg ) } } } \end{array} \right.
$$

整车相对中心的转弯半径为

$$
R _ { \mathrm { c } } = \sqrt { \left( \frac { l _ { \mathrm { f } } + l _ { \mathrm { r } } } { 2 } \right) + R _ { \mathrm { a } } ^ { 2 } }
$$

其中，旋转角速度为 $\omega _ { 0 } = \left( \nu / R _ { \mathrm { c } } \right)$ 。若 $\omega _ { 0 }$ 用后轴中心速度表示，则 $\omega _ { \mathrm { 0 } } = \big ( \nu _ { \mathrm { f } } + \nu _ { \mathrm { r } } \big ) / 2 R _ { \mathrm { r } }$ ，其中 $\nu _ { \mathrm { f } }$ 和 $\nu _ { \mathrm { r } }$ 为两个驱动轮的线速度，即前轮的线速度。

$\Delta T$ 在电子差速系统中不必像在传统的机械差速系统中通过测量车轮旋转一圈的时间来确定，由于采用轮边直驱的方式，可以直接通过控制器来实现对 $\Delta T$ 的计算。于是可以将式（11）左右车轮速度简化为

$$
\nu _ { \mathrm { { l } } } = \nu _ { \mathrm { { r } } }
$$

式中， $\nu _ { \mathrm { l } }$ 为左侧车轮转速； $\nu _ { \mathrm { r } }$ 为右侧车轮转速。

车辆转向时控制器保证两个电机转矩一致，由永磁电机电磁转矩公式

$$
T _ { \mathrm { e m } } = 1 . 5 p [ \varPsi _ { \mathrm { f } } i _ { q } + ( L _ { d } - L _ { q } ) i _ { d } i _ { q } ]
$$

可知，控制器通过调节 $i _ { d }$ 和 $i _ { \boldsymbol { q } }$ 来保持两个电机的输出电磁转矩相等，即 $T _ { \mathrm { L } } = T _ { \mathrm { R } }$ ，其中 $T _ { \mathrm { L } }$ 为左侧电机转矩， $T _ { \mathrm { R } }$ 为右侧电机转矩。此时电机转速在变化，而转矩保持不变，所以此时控制器需要调节电压来分别调节两台电机的功率，向左转向时实际转矩 $T _ { \mathrm { L } }$ $< T _ { \mathrm { R } }$ ，此时控制器调节功率使 $W _ { \mathrm { L } } < W _ { \mathrm { R } }$ ，其中 $W _ { \mathrm { L } }$ 为左侧电机功率， $W _ { \mathrm { R } }$ 为右侧电机功率，通过两个车轮转矩保持一致而转速不一致来实现转向。向右转向等同此原理。

# 7仿真模型的建立与仿真结果分析

根据以上分析，基于Simulink平台建立电子差

速仿真模型，如图3所示，其中包括转速初值计算模块、永磁电机矢量控制模块、控制器模块。搭建完成后对搭建的电子差速系统进行仿真。

![](images/9758663d5f7c8d5f250c1eaafa9512b633e3ba18277c44a1abe9338483e80af6.jpg)  
图3电子差速仿真模型

仿真车辆主要参数见下表，设车辆初始速度为$2 0 \mathrm { { k m } / h }$ ，向左转向，方向盘最大旋转角度为 $1 2 0 ^ { \circ }$ 从转向开始到回正一共经历了10s的时间。

# 表车辆仿真模型主要参数

TabThe main parameters of vehicle simulation model   

<html><body><table><tr><td>m/kg</td><td>l/mm</td><td>l/mm</td><td>df/mm</td><td>d./mm</td><td>CD</td><td>A/m²</td></tr><tr><td>1 542</td><td>4 690</td><td>1 850</td><td>1585</td><td>1 595</td><td>0.45</td><td>1.6</td></tr><tr><td>r/m</td><td>f</td><td>KE</td><td>KT</td><td>Izz/(kg/m²)</td><td>Uc/V</td><td>h/m</td></tr><tr><td>0.31</td><td>0.013</td><td>0.13525</td><td>1.367 5</td><td>1850</td><td>220</td><td>0.25</td></tr></table></body></html>

# 8 仿真及实验结果分析

电子差速模型仿真结果如图4所示，由于采用恒转矩实现差速方法，所以在车辆转向时，两台电机转矩相同，由于是向左侧转向，左侧车轮转速低于右侧车轮转速。从仿真结果可以看出，在电子差速控制下，经过一定的时间调整，整车各参数都达到稳定，电机转速和车轮转速存在线性关系。电子差速系统很好地实现电子差速的功能，可以保证汽车在直线行驶及转向时能够稳定运行。

![](images/dd0d0827e712b3d93b8749faa6d8f3126bcc2f59d974c8089ff43450412e3d73.jpg)

![](images/315f99d03fed3ead6bd50f1f4c17a9e186d7dbb7e7fef4cf80c61b068cfdc770.jpg)  
Fig.3Electronic differential simulation model

![](images/89129e94a7c86cf99fd7b37e92c57dd508acb7e2c3e596fae31e25d077f125fd.jpg)  
(d）电机转速与转弯半径关系曲线   
图4电子差速模型仿真结果 Fig.4ED model simulation results

# 9 结论

永磁电机是现阶段最适合电动汽车使用的动力源。相对于传统电机，永磁电机功率密度更大，是现阶段电动汽车的主导发展方向。本文针对SUV汽车电子差速控制策略进行深入研究，采用恒转矩方法，通过控制电机转速和电机输出功率来实现电子差速，从而避免现有的控制方法需要对路面复杂情况进行判断而产生的弊端。仿真及实验证明，本文设计的电子差速模型能够实现电动汽车的正常运行。

# 参考文献

[1] Sakhalkars,Dhillonp,Kumarp,et al.Implementation of an electronic differential using torque vectoring[R]. SAE Technical Paper,2014: 655-668.   
[2] Hartani K,Bourahla M,Miloud Y,et al.Electronic differential with direct torque fuzzy control for vehicle propulsion system[J].Turkish Journal of Electrical Engineering& Computer Science,2009, 17(1): 21-38.   
[3] Draou A.A simplified sliding mode controlled electronic differential for an electric vehicle with two independent wheel drives[J].Energy and Power Engineering,2013,5(6): 416-421.   
[4] 唐任远，等．现代永磁电机理论和设计[M]．北京： 机械工业出版社，1997.   
[5] 赵艳娥，张建武．轮毂电机驱动电动汽车电子差 速系统研究[J]．系统仿真学报，2008，20(18): 4767-4771. Zhao Yane,Zhang Jianwu.Hub motor drive electric car electronic difference speed system research[J]. Journal of System Simulation,2008,20(18):4767- 4771.   
[6] 靳立强，王庆年，周雪虎，等．电动轮驱动汽车 电子差速控制策略及仿真[J]．吉林大学学报：工 学版，2008，38(S1)：1-6. Jin Liqiang,Wang Qingnian, Zhou Xuehu,et al. Electric wheel drive car electronic differential control strategy and simulation[J]. Journal of Jilin University: Industry Academic Edition,2008,38 (S1):1-6.   
[7] 葛英辉，李春生，倪光正．新的轮毅电机驱动电 动车电子差速控制系统研究[J]．电机与控制应用， 2003，30(6):46-49. Ge Yinghui, Li Chunsheng,Ni Guangzheng. New wheel motor drive research on motor vehicle electronic differential control system[J].Motor and Control Applications,2003,30(6): 46-49.   
[8] 张弦，罗禹贡，范晶晶，等．电动车辆驱动防滑 控制方法的研究[J]．车辆与动力技术，2007(3)： 13-19. Zhang Xian, Luo Yugong, Fan Jingjing, et al. Electric vehicle drive slip research on control methods[J]. Vehicle and Power Technology,2007(3): 13-19.

# (上接第11页）

[8] Cespedes M,Sun J.Modeling and mitigation of harmonic resonance between wind turbines and the grid[C]. IEEE Energy Conversion Congress and Exposition, 2011:2109-2116.   
[9] 温春雪，李正熙．基于虚拟电阻控制环的并联 逆变器简化控制方法[J]．电工技术学报，2012, 27(6):63-68. Wen Chunxue,Li Zhengxi.A simplified control method of parallel inverters based on virtual

impedance control loop[J]. Transactions of China Electrotechnical Society,2012,27(6): 63-68. [10] 赵巧娥，张乐乐，武晓冬，等．基于并联虚拟电 阻的多逆变器控制策略[J]．电力系统保护与控制， 2017，45(15):30-39. Zhao Qiaoe, Zhang Lele,Wu Xiaodong,et al. Control strategy for multi-inverters based on parallel virtual resiatance[J].Power System Protection and Control,2017,45(15): 30-39.