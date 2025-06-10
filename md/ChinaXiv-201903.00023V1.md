# Z源并网风力发电系统机侧谐波抑制

程谆张阳 邓木生（湖南工业大学电气与信息工程学院株洲 412007)

![](images/e8913b46e0914469603ef317bb827d606c14a6a5cd35e3c757cbbac7358405fb.jpg)

程谆女1988年生，硕士研究生，研究方向为现代电力电子技术。

摘要：传统Z源并网风力发电系统整流侧采用的是三相不可控整流，其定子侧的电流谐波不仅会增大电机的铜耗和铁耗，降低发电效率，还有可能出现电机饱和以及失控等现象，严重影响了系统的稳定性。本文将VIENNA整流器应用于Z源并网风力发电系统，提出一种新的并网变流器控制方法。将定子输出电压的一个周期划分为6个扇区，通过扇区决策控制器给每个扇区内的不导通相提供电流通路，改善了机侧电流与机侧电压的非线性关系。比较了采用三相不可控整流器和VIENNA整流器以及最大升压控制和改进 SVPWM控制下Z源并网风力发电系统的机侧电流谐波。仿真与实验结果表明，本文方法减少了定子侧电流谐波，提高了系统的效率和稳定性。

关键词：Z源逆变器 VIENNA整流器 风力发电谐波抑制 中图分类号：TM614

# Harmonic Suppression for the Motor-Side Converter of the Z-Source Grid-Connected Wind Generation System

![](images/e49f0c0b0a97faead86caf53c76ba3b02fe6ad6a8cd765818e23132aeebe10db.jpg)

Cheng Zhun Zhang Yang Deng Musheng (Hunan University of TechnologyZhuzhou412007 China )

张阳 (通讯作者)男1988年生，讲师，研究方向为电力电子与新能源发电技术、永磁电机优化设计及其控制技术。

Abstract: D-PMSG based on Z-source inverter uses a three-phase diode rectifier. Stator side current harmonics will not only increase the motor's copper and iron losses, but also produce motor saturation and runaway phenomenon. What has seriously affected the stability of the system and reduced power generation efficiency. This paper presents a wind turbine generation system based on the Z-source inverter, which takes in the VIENNA rectifier. A period of stator voltage is divided into six sectors in this paper and equivalent circuit is researched in different working stages.A Z-source inverter control strategy is proposed according to the determination of Z-source inductor value. The simulation and experimental results prove the theoretical analysis very well.

Keywords: Z-source inverter, VIENNA rectifier, wind power generation, harmonic suppression

# 1 引言

与传统逆变器相比，Z源逆变器具有如下优点[]：输出电压具有升降压功能；交流负载既可以是电感性的，也可以是电容性的；主电路既可以用于电压源逆变器，也可以用于电流源逆变器；开关管的控制允许产生直通(无需加入死区时间)，提高了系统可靠性和电磁兼容性。

近年来，Z源逆变器被广泛应用于风力发电等新能源发电中。文献[7]论述了采用Z源变换器的小型风力并网发电系统，通过正弦波调制因子的控制实现并网电流内环的单位功率因数运行和Z源网络电容电压外环的稳压。文献[8]将传统三相PWM并网逆变器模型和等效的Z源网络模型结合，建立了三相Z源并网逆变器的数学模型，分析了直通占空比改变对系统的影响，提出了在并网条件下获取稳定的Z网络电容电压和解耦的dq轴网侧电流分量的控制策略，并给出了外环电压设定值的约束条件，在基于Z源逆变器的小型永磁同步机风力发电系统平台上进行了实验验证。文献[9]提出将新型三相乙源逆变器应用于直驱式风力并网发电系统中，建立了三相Z源并网逆变器的数学模型，提出了在并网条件下获取稳定的Z网络电容电压和解耦的dq轴网侧电流分量的控制策略。文献[10-12]主要研究了Z源逆变器直流链电压稳定的非线性控制方法。国内外鲜有针对Z源并网风力发电系统机侧谐波抑制的研究。

然而，传统Z源并网风力发电系统常采用直驱永磁同步发电机加三相不可控整流，再加Z源逆变器的结构。每个扇区内三相不可控整流器只有两个二极管导通，由此产生的机侧电流谐波不仅会增大电机的损耗，还有可能出现电机饱和以及失控等现象，严重影响了系统的稳定性。本文将VIENNA整流器应用于Z源并网风力发电系统，代替传统的三相不可控整流，提出一种新的机侧变流器控制方法。将定子输出电压的一个周期划分为6个扇区，利用VIENNA整流器独特的拓扑结构，通过扇区决策控制器给每个扇区内的不导通相提供电流通路，改善了机侧电流与机侧电压的非线性关系，减少了定子侧电流谐波，提高了系统的效率和稳定性。

# 2 系统结构及模型分析

基于Z源逆变器的永磁直驱风力发电系统如图1所示，该系统包括风力机、永磁同步发电机、VIENNA整流器、Z源逆变装置和并网变压器。

![](images/d3775736538e3d2d990bb0309b81dec16575d2d9bd49f0969d731d97a8649bca.jpg)  
图1基于Z源逆变器的永磁直驱风电系统拓扑结构

图2将一个交流输入周期划分为6个扇区，每个扇区内，只有最大电压差的两相二极管才能导通。这时，通过扇区决策控制器给每个扇区内的不导通相提供电流通路。由于逆变器的开关周期远大于交流输入周期，可认为在一个开关周期内，输入的电压为定值。而串联的二极管同时导通、同时关断，可等效为一个二极管，这样就可以利用Z源逆变器的基本理论分析该系统在一个开关周期内的等效电路。

![](images/92f0213fc49658bd434538e5b9e3be0bedd6ccd329bd33c43b55a8bf9f5a01b6.jpg)  
Fig.1Proposed Z-source inverter for the wind power system   
图26个扇区内二极管的通断情况  
Fig.2Six possible conduction intervals per cycle

以第一扇区为例，假设电流流向为图3中所示，此时，二极管 $\mathrm { V D } _ { 1 }$ ， $\mathrm { \Delta V D _ { 7 } }$ 和 $\mathrm { \Delta V D _ { 6 } }$ ， $\mathrm { V D } _ { 1 4 }$ 导通，通过扇区决策控制器检测到当前扇区后，导通开关管 $\mathrm { V T } _ { 2 }$ ，原本没有电流流过的C相，形成了 $\mathrm { V D } _ { 1 6 }$ ，$\mathrm { V T } _ { 2 }$ 、 $\mathrm { V D } _ { 1 8 }$ 的电流通路。当Z源逆变器处于非直通零矢量时，二极管 $\mathrm { V D } _ { 1 9 }$ 持续导通，逆变桥可等效为一个电流源，此时系统的等效电路如图3所示。

![](images/efde985a66e86a5e84b9d39d584b1bfb8a0b1173c9b4907934e5b8c67bba236f.jpg)  
图3非直通时系统的等效电路  
Fig.3Equivalent circuit of the Z-source inverter

由Z源网络的对称性可知[13-16]

同理可得

$$
V _ { _ { C 1 } } = V _ { _ { C 2 } } = V _ { _ { C } } \quad V _ { _ { L 1 } } = V _ { _ { L 2 } } = V _ { _ { L } }
$$

由图3可知

$$
\begin{array} { r l } & { \left[ V _ { \mathrm { i n } } = V _ { L } + V _ { C } \right. } \\ & { \left. \begin{array} { l } { V _ { \mathrm { i n } } = 2 V _ { C } - V _ { 0 } } \\ { V _ { \mathrm { d } } = V _ { \mathrm { i n } } } \end{array} \right] } \\ & { \left[ V _ { \mathrm { d } } = V _ { \mathrm { i n } } \right. } \\ & { \left. \begin{array} { l } { i _ { \mathrm { D } } = 2 i _ { L } - i _ { \mathrm { i n } } } \end{array} \right. } \end{array}
$$

式中， $i _ { \mathrm { D } }$ 为流过二极管 $\mathrm { V D } _ { 1 9 }$ 的电流。在设计Z源网络电感时，为避免非直通情况下二极管 $\mathrm { V D } _ { 1 9 }$ 误关断引起的Z源网络输出电压畸变，要求

$$
\left\{ \begin{array} { l l } { \displaystyle L _ { 1 } = L _ { 2 } \geqslant \frac { D _ { 0 } ( 1 - D _ { 0 } ) Z } { \displaystyle f _ { \mathrm { s } } M \left[ \frac { 3 } { 2 ( 1 - 2 D _ { 0 } ) } M \cos \varphi - 1 \right] } } \\ { \displaystyle \frac { 3 } { 2 ( 1 - 2 D _ { 0 } ) } M \cos \varphi - 1 > 0 } \end{array} \right. 
$$

式中， $D _ { 0 }$ 为Z源逆变器的直通占空比； $f _ { \mathrm { s } }$ 为 $Z$ 源逆变器的开关频率； $Z$ 为负载； $M$ 为 $Z$ 源逆变器的调制因数； $\varphi$ 为 $Z$ 源逆变器的输出的功率因数角。由基尔霍夫电压定律可知

$$
L _ { \mathrm { i n } } \left( \frac { \mathrm { d } i } { \mathrm { d } t } - \frac { \mathrm { d } i _ { \mathrm { b } } } { \mathrm { d } t } \right) = \nu _ { \mathrm { a } } - \nu _ { \mathrm { b } } - 2 L _ { \mathrm { z } } \left( \frac { \mathrm { d } i _ { \mathrm { z } } } { \mathrm { d } t } \right) - V _ { \mathrm { i } }
$$

式中， $L _ { \mathrm { i n } }$ 为发电机输入电感； $L _ { \mathrm { Z } }$ 为 $Z$ 源网络电感。

$$
L _ { \mathrm { i n } } \left( { \frac { \mathrm { d } i _ { \mathrm { a } } } { \mathrm { d } t } } - { \frac { \mathrm { d } i _ { \mathrm { c } } } { \mathrm { d } t } } \right) = \nu _ { \mathrm { a } } - \nu _ { \mathrm { c } } - 2 L _ { \mathrm { z } } \left( { \frac { \mathrm { d } i _ { \mathrm { _ { L } } } } { \mathrm { d } t } } \right) - V _ { \mathrm { i } }
$$

将式（4）和式（5）相加得

$$
L _ { \mathrm { i n } } \left( 2 { \frac { \mathrm { d } i _ { \mathrm { a } } } { \mathrm { d } t } } - { \frac { \mathrm { d } i _ { \mathrm { b } } } { \mathrm { d } t } } - { \frac { \mathrm { d } i _ { \mathrm { c } } } { \mathrm { d } t } } \right) = \nu _ { \mathrm { a } } - \nu _ { \mathrm { b } } - \nu _ { \mathrm { c } } - 4 L _ { z } \left( { \frac { \mathrm { d } i _ { \mathrm { _ { _ { L } } } } } { \mathrm { d } t } } \right) - 2 V _ { \mathrm { i } }
$$

由三相输入电压对称可得

$$
3 L _ { _ { \mathrm { i n } } } \frac { \mathrm { d } i _ { _ { \mathrm { a } } } } { \mathrm { d } t } { = } 3 \nu _ { _ { \mathrm { a } } } - 4 L _ { _ { Z } } \left( \frac { \mathrm { d } i _ { _ { L } } } { \mathrm { d } t } \right) - 2 V _ { \mathrm { i } }
$$

由于Z源逆变器输入电压 $V _ { \mathrm { d } }$ 大小的缘故，二极管整流桥有可能不导通，造成正弦波平顶以及过零点前后出现电流恒为零现象。此外，由于每个扇区内，只有具有最大电压差的两相二极管才能导通，造成机侧电流正弦波畸变，通过扇区决策控制器给每个扇区内的不导通相提供电流通路，使式（7）后两项相加为零，保证任意时刻三相都有电流流过，从而减少了定子侧电流谐波。

当Z源逆变器处于直通零矢量时，逆变桥可视为被短路，二极管 $\mathrm { V D } _ { 1 9 }$ 断开，系统的等效电路如图4所示。

由直通时系统的等效电路可知

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { V _ { L } = V _ { C } } \\ { V _ { \mathrm { d } } = 2 V _ { C } } \\ { V _ { \mathrm { i } } = 0 } \end{array} \right. } \end{array}
$$

![](images/e898e53a0dd6d0981b36491f33277a8b9bed9ba5a15f363617f322770e79bf13.jpg)  
Fig.4Equivalent circuit of the Z-source inverter when the inverter bridge is in the shoot-through zero state

由一个开关周期 $T$ 中，电感两端平均电压必然为0可得

$$
\frac { V _ { C } } { V _ { \mathrm { i n } } } = \frac { T - T _ { 0 } } { T - 2 T _ { 0 } } = \frac { 1 - D _ { 0 } } { 1 - 2 D _ { 0 } }
$$

将式（9）带入式（8）可得

$$
V _ { \mathrm { d } } = \frac { 2 ( 1 - D _ { 0 } ) } { 1 - 2 D _ { 0 } } V _ { \mathrm { i n } } = \left( 1 + \frac { 1 } { 1 - 2 D _ { 0 } } \right) V _ { \mathrm { i n } } \geqslant 2 V _ { \mathrm { i n } }
$$

由式（10）可知，直通时二极管 $\mathrm { V D } _ { 1 9 }$ 一定是关断的，此时，发电机不再向Z源网络供电。

# 3并网型Z源逆变器的控制策略

基于Z源逆变器的永磁直驱风电控制系统采用电压电流双闭环控制以及转速电流双闭环控制，通过对Z源网络电感电流给定值的跟踪，实现了直通零矢量的产生。通过扇区决策控制器产生脉冲信号，触发VIENNA整流器的开关器件，为每个扇区内的不导通相提供电流通路。不仅要保证Z源网络电容电压稳定，并网电流谐波含量小、正弦度好、有较快的动态响应，还要实现电机侧的高功率因数，电流正弦度好，谐波含量小的功能。

# 3.1直通零矢量插入方法

适用于Z源逆变器的最大增益升压SPWM直通零矢量插入原理如图5a所示，当三相正弦调制波大于三角波时，输出高电平脉冲；当三相正弦调制波小于三角波时，输出低电平。在此基础上，以传统零状态时三相触发脉冲的最小值，即零状态下可实现直通的最大值作为直通零矢量给定，最大限度地实现升压功能。然而，该方法下阻抗源网络逆变

器的直通占空比以6倍输出频率波动，当最大限度地利用直通零矢量时，由于传统零矢量本身每个开关周期都在变化，所以每个开关周期直通零矢量的大小也都在变化，不仅会导致电感电流中有很大的低次谐波含量，还会导致整流侧电流波形发生畸变。不仅如此，由于直通零矢量安插在传统零矢量中间，因此加倍了一个开关周期内的开关次数，不利于提高系统的开关频率。因此，本文采用改进SVPWM直通零矢量插入方法如图5b所示。对传统SVPWM策略下的功率器件开通关断时间进行提前或延时，在开关转换时刻插入直通零矢量，无需额外开关动作。将一个开关周期内的直通零矢量平均分为6份，将它们插在两个有效矢量之间以及传统零矢量的两边。由于其采用空间矢量方法，具有易于数字化、线性调制范围宽、电压利用率高和电流谐波低等特点，更适用于Z源逆变器。

在传统SVPWM的基础上，增加直通零矢量的产生环节，具体方法如下：由式（11）产生的 $T _ { \mathrm { a l } }$ ，$T _ { \mathrm { b l } }$ 、 $T _ { \mathrm { c 1 } }$ 通过和三角波比较后产生的脉冲用来驱动三相桥上桥臂的3个开关管，由式（12）产生的 $T _ { \mathrm { a 2 } }$ ，$T _ { \flat 2 }$ 、 $T _ { \mathrm { c } 2 }$ 通过和三角波比较后再取反，用来驱动三相桥下桥臂的3个开关管。

![](images/a1fc0ee902755d3ef1f7197016c673857506a5c6a7501a0f1f754f6c774d7ea8.jpg)  
图4直通时系统的等效电路  
(a）最大增益SPWM直通零矢量分布图

![](images/b67e8aa330a79019a1fcc9bcf4d2fa3cb48d0844036fa53940cdd4b7a50157ca.jpg)  
图5最大增益SPWM和改进SVPWM分布图Fig.5Diagram of maximum gain SPWM andimprovedSVPWM

$$
\left\{ \begin{array} { l l } { T _ { \mathrm { a l } } = \left( T _ { \mathrm { p w M } } - T _ { \mathrm { 1 } } - T _ { \mathrm { 2 } } - T _ { \mathrm { 0 } } \right) / 4 } \\ { T _ { \mathrm { b l } } = T _ { \mathrm { a l } } + T _ { \mathrm { 1 } } / 2 + T _ { \mathrm { 0 } } / 6 } \\ { T _ { \mathrm { c l } } = T _ { \mathrm { b l } } + T _ { \mathrm { 2 } } / 2 + T _ { \mathrm { 0 } } / 6 } \end{array} \right.
$$

$$
\begin{array} { r } { \left\{ \begin{array} { c } { T _ { \mathrm { a 2 } } = T _ { \mathrm { a 1 } } + T _ { \mathrm { 0 } } / 6 } \\ { \rule { 0 ex } { 5 ex } } \\ { T _ { \mathrm { b 2 } } = T _ { \mathrm { b 1 } } + T _ { \mathrm { 0 } } / 6 } \\ { T _ { \mathrm { c 2 } } = T _ { \mathrm { c 1 } } + T _ { \mathrm { 0 } } / 6 } \end{array} \right. } \end{array}
$$

# 3.2 双闭环控制

基于Z源逆变器的永磁直驱风电系统在并网时采用电压电流双闭环控制。由式（8）和式（9）可知，加在逆变器上的平均直流电压

$$
\begin{array} { l } { { \displaystyle \vec { V _ { \mathrm { i } } } = [ T _ { \mathrm { 0 } } \times 0 + T _ { \mathrm { 1 } } \times ( 2 V _ { \mathrm { _ C } } - V _ { \mathrm { i n } } ) ] / T } } \\ { { \displaystyle ~ = \frac { T - T _ { \mathrm { 0 } } } { T - 2 T _ { \mathrm { 0 } } } V _ { \mathrm { i n } } = \frac { 1 - D _ { \mathrm { 0 } } } { 1 - 2 D _ { \mathrm { 0 } } } V _ { \mathrm { i n } } = V _ { \mathrm { _ C } } } } \end{array}
$$

式中， $T _ { 0 }$ 为一个开关周期内直通零矢量的时间； $T _ { 1 }$   
为一个开关周期内非直通零矢量的时间。

由式（13）可知，当直通占空比保持不变时，只要使Z源网络电容电压保持恒定，就可以得到逆变桥上稳定的平均直流输入电压，确保Z源逆变器输出交流电压稳定，所以，对于电压外环控制，本文直接对Z源网络中电容电压进行控制。由于直通占空比和调制度的博弈关系，当直通占空比增大时，逆变器直流输入电压平均值增大，调制度降低；当直通占空比减少时，逆变器直流输入电压平均值减小，调制度升高。电容电压稳定时，通过直通占空比可以灵活地控制逆变器输入直流电压。

电流内环采用基于dq坐标变换的电流控制策略，d轴为有功分量参考轴，q轴为无功分量参考轴，从而有功和无功可进行独立控制。当上桥臂导通，下桥臂关断时，开关函数 $S _ { K } = 1$ ，当上桥臂关断，下桥臂导通时，开关函数 $S _ { K } = \ 0$ 。其中， $K =$ a,b,c。

经过同步旋转坐标变换，有

$$
\left\{ \begin{array} { l l } { { { \displaystyle { \cal L } \frac { \mathrm { d } i _ { \mathrm { d } } } { \mathrm { d } t } } = - R i _ { \mathrm { d } } + \omega { \cal L } i _ { \mathrm { q } } + e _ { \mathrm { d } } - S _ { \mathrm { d } } V _ { \mathrm { i n } } } } \\ { ~ } \\ { { \displaystyle { \cal L } \frac { \mathrm { d } i _ { \mathrm { q } } } { \mathrm { d } t } } = - R i _ { \mathrm { q } } + \omega { \cal L } i _ { \mathrm { d } } + e _ { \mathrm { q } } - S _ { \mathrm { q } } V _ { \mathrm { i n } } }  \\ { { ~ } } \\ { { \displaystyle { \cal C } \frac { \mathrm { d } V _ { c } } { \mathrm { d } t } = \frac { 3 } { 2 } ( i _ { \mathrm { q } } S _ { \mathrm { q } } + i _ { \mathrm { d } } S _ { \mathrm { d } } ) } } \end{array} \right.
$$

式中， $S _ { \mathrm { d } }$ 、 $S _ { \mathrm { q } }$ 为开关函数 $S _ { K }$ 变换到dq坐标系中，dq轴相应的开关函数。

由于dq轴变量相互耦合，控制器的设计具有一定困难。为此，在电流调节器采用PI控制时，可运用前馈解耦控制对dq轴变量进行解耦， $\nu _ { \mathrm { d } }$ ， $\nu _ { \mathrm { q } }$ 的控制方程为

$$
\left\{ \begin{array} { l l } { \displaystyle \nu _ { \mathrm { q } } = - \left( K _ { \mathrm { p } } + \frac { K _ { \mathrm { I } } } { s } \right) ( i _ { \mathrm { q } } ^ { \ast } - i _ { \mathrm { q } } ) - \omega L i _ { \mathrm { q } } + e _ { \mathrm { q } } } \\ { \displaystyle \nu _ { \mathrm { d } } = - \left( K _ { \mathrm { p } } + \frac { K _ { \mathrm { I } } } { s } \right) ( i _ { \mathrm { d } } ^ { \ast } - i _ { \mathrm { d } } ) + \omega L i _ { \mathrm { q } } + e _ { \mathrm { d } } } \end{array} \right.
$$

式中， $K _ { \mathrm { P } }$ 、 $K _ { \mathrm { I } }$ 为电流内环比例调节增益和积分调节增益； $i _ { \mathrm { d } } ^ { * }$ ， $i _ { \mathrm { q } } ^ { * }$ 为dq轴分量的指令电流值。

令d轴与电网电动势矢量重合，则d轴电流为有功分量，q轴电流为无功分量，为确保并网电流的正弦度好、谐波含量小，令q轴电流指令值为0。在SVPWM调制中，直通占空比通过对Z源网络电感电流的控制来产生，其中，Z源网络电感电流的给定值由D-PMSG转速差经过PI控制器获得，进而跟踪最优的Z源网络输入电压，从而实现风力机的最佳功率点跟踪。直驱式风力发电系统的三相并网型Z源逆变器控制框图如图6所示。

# 4 仿真研究

仿真系统主要参数见下表。Z源网络电感电流、

![](images/067aa3bcc372b19b86f613aa8bc80e9375b10a7b543bbd19ee3634dcd895f88b.jpg)  
Fig.6The control diagram of three phase Z-source grid-connected inverter

# 表系统参数

Tab.Parameters of system   

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>定子绕组相电阻/Ω</td><td>2.3</td></tr><tr><td>极对数</td><td>2</td></tr><tr><td>额定转速/(r/min)</td><td>1500</td></tr><tr><td>相电压幅值对应的磁通/Wb</td><td>0.804</td></tr><tr><td>系统功率/kW</td><td>7.5</td></tr><tr><td>网侧线电压/V</td><td>380</td></tr><tr><td>电网频率/Hz</td><td>50</td></tr><tr><td>Z 源网络电容电压/V</td><td>570</td></tr><tr><td>Z源网络电容/mF</td><td>2.04</td></tr><tr><td>Z 源网络电感/mH</td><td>5</td></tr></table></body></html>

Z源网络输出电压如图7、图8所示。可见，在直通时间内，Z源网络电容给电感充电，电感电流上升，在非直通时间内，乙源网络电感放电，电感电流下降。逆变器输入电压为正常的方波，并没有出现电压的跌落，说明在直通时间内，二极管电流为0，在非直通时间内，二极管电流并没有下降到0,Z 源网络电感足够大，在非直通状态下，二极管并

![](images/a9c0bc88a2b978f78eec5c6bf7f6d2f8260edd1261e3174d73902f4579c4d883.jpg)  
图6三相并网型乙源逆变器控制框图  
图7乙源网络电感电流波形  
Fig.7Inductance current waveformof Z source network

没有出现误关断，即不会出现Z源逆变器的非正常工作状态。

图9为Z源网络电容电压波形，可见，该电压基本稳定在设定值，电压超调较小，响应时间较短。由于Z源网络电容电压设定了初始值 $4 0 0 \mathrm { V }$ ，起始时刻Z源网络电容电压由电网提供充电电流，所以，Z源网络电感电流在起始时刻有一段时间为负。

![](images/69808ad8645f4d80966c70766644d75de1602326a4bd240fd4c64b0ece032e75.jpg)  
图8Z源网络输出电压波形

![](images/31fc21d7448b4b188d3ccd3b128dceb4297417c796eadd131c1fba8be6d4ab85.jpg)  
Fig.8Output voltage waveform of Z source network

由图10可知，并网电流对称，正弦性好，动态响应较快。通过比较图11和图12可知，采用VIENNA整流器时定子电流波形更接近正弦，且谐波含量明显减少；采用最大升压控制时2次、3次、4次、5次、7次、13次谐波含量比采用改进升压控制时明显增高。

![](images/974efd1444e33a7a903e87744a389a27148cdd1922b6754b872ddb39bb160da6.jpg)  
Fig.9Capacitor voltage waveform of Z source network   
图10 并网三相电流  
Fig.10Waveform of grid-connected current

# 5 实验研究

搭建硬件平台对本文提出的新型Z源并网逆变系统的性能进行了验证，采用异步机拖动永磁同步发电机发电，永磁同步发电机所产生的电能通过VIENNA整流器后，经电压型三相Z源逆变器并网。实验结果的采集使用QualityStar功率分析仪。控制器采用TMS320F28335，Z源网络电容采用 $4 5 0 \mathrm { V } / 6 8 0 \mu \mathrm { F }$ 的电解电容2串6并组成的电容板，Z源网络电感为 $5 \mathrm { m H }$ ，开关频率 $5 \mathrm { k H z }$ 。图13为Z源逆变器稳态实验波形以及Z源网络电感电流和经Z源网络后输出电压的放大波形。由此可知，Z源网络电容电压基本保持恒定，在直通状态时，Z源网络电容给电感充电，电感电流上升，Z源网络输出电压为零，在非直通状态时，Z源网络电感放电，电感电流下降，Z源网络输出电压基本保持稳定。

![](images/48598a8009cdeec08207b626117c8fb73e4023fd82530ed6651285e13231ea0c.jpg)  
图9Z源网络电容电压  
图11采用三相不可控整流时定子电流频谱仿真对比 Fig.11Simulation results of stator current with three-phase diode rectifier

实验系统主要参数见上表，对不同控制方法和不同整流器下的定子电流谐波进行对比分析。图14和图15为定子电流通过三相不可控整流和VIENNA整流时，采用最大增益控制和改进升压控制定子电流的谐波对比结果，由图14可知，定子电流通过三相不可控整流器的情况下，采用最大增益控制时，定子电流中2次、3次、4次、5次、7次、13次谐波幅值比采用改进升压控制时的谐波幅值大很多，由图15可知，定子电流通过VIENNA整流器的情况下，采用改进升压控制比采用最大增益控制定子电流中2次、3次、4次、13次谐波幅值小很多，这是因为最大增益控制比改进升压控制的直通占空比大，导致二极管关断时间更长，另外，由于最大增益控制的直通占空比是变化的，从而引入了低次谐波。由图15b、15d和图14b、14d对比可知，在都采用改进升压控制的前提下，采用VIENNA整流器比三相不可控整流器定子电流中谐波含量小很多，这是因为当定子电流通过VIENNA整流器时，扇区决策控制器给每个扇区内的不导通相提供电流通路，从而改善了机侧的电流谐波。

![](images/5ce06348a078412a48ed5b2808f632488ec10d4858e0195dfc27f24539c18238.jpg)

![](images/33a1a4415b5f7bc126ad147a44298d001e16e14f8ed8a07fe93eea604b60c7ce.jpg)  
图12采用VIENNA整流时定子电流频谱实验对比 Fig.12Simulation results of stator current with VIENNA rectifier   
图13Z源逆变器稳态实验波形  
Fig.13Experimental results of Z-source inverter

![](images/febe8370d37aaab51de800159d1860ae000182bb066f09a41cf7e3dfb6342330.jpg)  
图14采用三相不可控整流时定子电流频谱实验对比 Fig.14Experimental results of stator current with threephase diode rectifier

![](images/18561d7917f5ee29ef8c6475876e86a4cfbe8553be997da9c1b09642e0a70b97.jpg)  
图15采用VIENNA整流时定子电流频谱实验对比 Fig.15Experimental results of stator current with VIENNA rectifier

# 6 结论

本文将Z源逆变器与VIENNA整流器结合后，应用于永磁直驱风力发电系统，通过对系统数学模型和工作原理的分析，提出了一种采用改进SVPWM升压控制的Z源逆变器并网控制策略，改善了由于三相不可控整流引起的机侧电流谐波的问题，通过理论分析以及仿真和实验可知：

(1）在Z源并网风力发电系统中，采用最大增益的控制方法，直通零矢量的大小是变化的，会导致电感电流中有很大的低次谐波含量，另外，由于最大增益控制比改进升压控制的直通占空比大，二极管关断时间更长，将导致整流侧电流波形发生畸变。

(2）将VIENNA整流器应用于基于Z源逆变器的风电并网系统，通过扇区决策控制器给每个扇区内的不导通相提供电流通路，改善了机侧电流与机侧电压的非线性关系，减小了电机定子的谐波电流。

# 参考文献

[1] Peng F Z,Shen M S,Qian Z M. Maximum boost control of the Z-source inverter[J]. IEEE Transactions on Power Electronics,2005,20(4): 833- 838.   
[2] Thangaprakash S,Krishnan Dr A. Z-source inverter fed induction motor drives- -a space vector pulse width modulation based approach[J]. Journal of Applied Science Research,2009,5(5): 579-584.   
[3] Tran Q,Chun T,Ahn J,et al.Algorithms for controlling both the DC boost and AC output voltage of Z-source inverter[J]. IEEE Transactions on Industrial Electronics,2007, 54(5): 2745-2750.   
[4] Murthi G, Ojo O.A comprehensive analysis of a three-phase Z-source DC-AC converter[C]. IEEE Applied Power Electronics Conference,California, 2007.   
[5] Liu J B, Hu JG, Xu L Y. Dynamic modeling and analysis of Z-source converter-derivation of AC small signal model and design-oriented analysis[J]. IEEE Transactions on Power Electronics,2007, 22(5): 1786-1796.   
[6] Ding Xinping,Qian Zhaoming, Xie Yeyuan, et al. Transient modeling and control of the novel ZVS Z-source rectifier[C].37th IEEE Power Electronics Specialists Conference,2006: 1-5.   
[7] 许颇，张兴，张崇巍，等．采用Z 源变换器的小 型风力并网逆变系统[J]．电工技术学报，2008, 23(4): 93-97. Xu Po,Zhang Xing,Zhang Chongwei,et al. Small wind turbine grid-connected systems based on Z-source inverter[J].Transactions of China Electrotechnical Society, 2008,23(4): 93-97.   
[8] 李杰，王得利，陈国呈，等．直驱式风力发电系 统的三相Z源并网逆变器建模与控制[J]．电工技 术学报，2009，24(2)：114-120. Li Jie,Wang Deli, Chen Guocheng, et al. Modeling and control of three-phase Z-source inverter for direct-drive wind generation system[J]. Transactions of China Electrotechnical Society, 2009,24(2):114- 120.   
[9] Li Xiao,Chen Jing,Zhang Jingning. Three-phase Z-source grid-connected wind power generation system based on novel deadbeat control[C]. The Second International Conference on Digital Manufacturing and Automation,Hunan,2011: 1355- 1359.   
[10] 丁新平，钱照明，崔彬，等．基于模糊PID的Z 源逆变器直流链升压电路控制[J]．中国电机工程 学报，2008：28(24)，31-38. Ding Xinping, Qian Zhaoming, Cui Bin, et al. Fuzzy PID controller for DC-link boost voltage in Z-source inverter[J].Proceedings of the CSEE,2008:28(24), 31-38.   
[11] 陈宗祥，蒋贏，潘俊民，等．基于滑模控制的Z 源逆变器在单相光伏系统中的应用[J]．中国电机 工程学报，2008，28(21)：33-39. Chen Zongxiang,Jiang Ying,Pan Junmin,et al. A Z-source inverter for a single-phase PV system based on sliding-mode control[J]. Proceedings of the CSEE,2008,28(21): 33-39.   
[12] Ding Xinping,Qian Zhaoming,Xie Yeyuan,et al. Transient modeling and control of the novel ZVS Z-source rectifier[C].37th IEEE Power Electronics Specialists Conference,2006:1-5.   
[13] 张瑾，齐铂金．Z源三电平中点钳位逆变器中点电 位平衡控制方法[J]．中国电机工程学报，2010, 30(12): 7-13. Zhang Jin,Qi Bojin.Neutral-point potential balancing method for Z-source three-level NPC inverters[J]. Proceedings of the CSEE,2010,30(12): 7-13.   
[14] Loh P C,Vilathgamuwa D M, Gajanayake G J, et al.Transient modeling and analysis of pulse-width modulated Z-source inverter[J].IEEE Transactions on Power Electronics,2007,22(2): 498-507.   
[15] PengF Z,Alen Joseph,Jin Wang.Z-source inverter for motor drives[J].IEEE Transactions on Power Electronics,2005,20(4): 857-863.   
[16] Loh P C,Vilathgamuwa D M,Lai Y S,et al. Pulse width modulation of Z-source inverters[C]. IEEE Industry Applications Society Annual Meeting, 2004: 148-155.