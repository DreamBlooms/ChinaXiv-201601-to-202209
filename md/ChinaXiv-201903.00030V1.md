# 改进的感应电机直接转矩控制系统

刘虹厉虹（北京信息科技大学自动化学院北京100192）

![](images/99b97c8b255489f9459de9ba676f95735c94552abd35de12228df3601c2cc9dc.jpg)

刘虹 女 1992年生，硕士研究生，研究方向为电机与电器。

摘要：基于三电平逆变器的感应电机直接转矩控制无速度传感器系统存在着逆变器结构复杂、元器件使用较多、基于转子磁链定向的无速度传感器算法使磁链计算复杂、磁链观测环节不精确等问题。为解决上述问题，对三电平逆变器的拓扑结构进行简化，针对直接转矩控制的特点，采用基于定子磁链的无速度传感器算法，并与改进的磁链观测器相结合，进行速度观测，构建了改进拓扑结构、改进磁链观测算法的感应电机直接转矩控制无速度传感器系统。通过仿真实验验证了上述改进方法在减少开关器件损耗的同时，可提高磁链观测精度，使转速估算更精确。

关键词：感应电机三电平逆变器 模型参考自适应磁链观测直接转矩控制中图分类号：TM343

# Research on Improved Direct Torque Control System of Induction Motor

![](images/13fe06a47ef584607e2b01bf4249af69a7b97cae35fadd0197162f181dcb2cfb.jpg)

Liu Hong Li Hong (Beijing Information Science & Technology UniversityBeijing 100192 China ）

厉虹女1959年生，教授，研究方向为高性能电气传动控制系统。

Abstract: Direct torque control of induction motor three-level inverter speed sensorless inverter system has complex structure,more components,complex flux algorithm due to speed sensorless algorithm based on rotor flux orientation,and inaccuracy of flux observation. To solve the above problems, the topological structure of the three-level inverter is simplified for direct torque control. The speed sensorless algorithm is adopted based on stator flux,and combined with the improved flux observer to observe speed. A modified topology and improved flux observer algorithm of direct torque control of induction motor speed sensorless system are established.The simulation experiments show that the improved method can reduce the loss of the switch device,and improve the precision of the flux observation.It make the speed estimation more accurate.

Keywords: Induction motor, three-level inverter, model reference adaptive, flux observer, direct torque control

# 1 引言

直接转矩控制（DirectTorqueControl，DTC）与多电平逆变器、无速度传感器技术相结合，实现高电压、大功率交流调速，是交流调速的发展趋势[1]。

文献[2-4]中使用的二极钳位式三电平逆变器，由于在可靠性、性能指标方面的优势，在多电平逆变器中最具代表性，使用最广泛[5。但传统二极钳位式三电平逆变器的结构复杂，电力电子器件使用较多。在实验过程中，同时监测每个元器件较为困难。本文针对该问题进行改进，减少每相桥臂的元器件使用量，降低了成本，提高了系统可靠性，使其拓扑结构简单明了，在控制方法上也没有增加复杂性，与传统二极管钳位式三电平逆变器相比，能更好地适用于电压要求较高的场合。

在有速度传感器的电气传动系统中，电机转速检测依赖于各种传感器完成，速度传感器不仅价格昂贵，且易受外界温度和环境的干扰，因此无速度传感器观测技术应运而生。文献[6-8]提出了多种无速度传感器的速度观测方法，其中文献[6]提出的模型参考自适应方法模型简单，鲁棒性强，易于实现，应用最为广泛。但传统的模型参考自适应都是基于转子磁链，在矢量控制系统中搭建并不能体现出直接转矩系统的优点，且易受到转子侧参数的干扰。

本文针对直接转矩控制策略的特点，直接利用基于定子磁链的模型参考自适应算法进行无速度传感器速度辨识，无需再计算转子磁链，使速度辨识算法得到大幅简化；同时对模型中的磁链观测环节进行改进，使用低通滤波器代替纯积分环节，避免了因为积分饱和导致的磁链畸变，提高了定子磁链的观测精度。

实验环节将改进拓扑结构的三电平逆变器与改进的无速度传感器算法相结合，并与传统三电平供电的无速度传感器系统进行比较。仿真实验表明，系统整体控制算法更简单，控制器结构得到简化，可有效抑制磁链和转矩的脉动，适用于高压大功率环境，在工程上更易实现。

# 2简化的三电平逆变器拓扑结构

# 2.1简化后的拓扑结构分析

传统的二极管钳位型（NeutralPointClamped,NPC）三电平逆变器拓扑电路所需功率器件较多，系统稳定性弱，在保留其优点的前提下，对其拓扑结构进行改进。改进后的NPC三电平逆变器中性点电位省去了钳位二极管，使用一组反串联开关管，每相桥臂的功率器件由10个减少到8个，电路拓扑结构得到简化，降低了成本，使得电路损耗减少，提高了系统可操作性，更适用于高压、大功率的工况[9]。改进后的NPC三电平逆变器单相电路如图1所示。

![](images/05a8b71265b45a46e97e26de165d4b5cfeed087e64740d1af135922cd4fdcab4.jpg)  
图1 简化拓扑结构的单相三电平逆变器 Fig.1 Single phase three-level inverter with simplified topology

# 2.2改进三电平逆变器控制方法选择

NPC三电平逆变器在受到外界干扰时将产生低次谐波，导致电机转矩产生脉动，调速性能下降[10]。因此必须解决控制过程中发生的高电压跳变、中性点电位不平衡等问题。系统受外界因素影响的优先级见表1。

# 表1各种因素的优先级别

Tab.1Priority levels of various factors   

<html><body><table><tr><td>影响因素</td><td>潜在危害</td><td>优先级</td></tr><tr><td>高电压跳变</td><td>对逆变器或负载冲击大，损害绝缘</td><td>1</td></tr><tr><td>中性点电位偏移</td><td>电压偏移可能超过IGBT或电容的耐压</td><td>2</td></tr><tr><td>开关频率</td><td>开关损耗</td><td>3</td></tr></table></body></html>

在考虑表1中各因素对系统的影响后，选取固定合成矢量法控制三电平逆变器，采用滞后法控制中性点电位调整。固定合成矢量是由一组空间电压矢量按照固定方式合成一个复合矢量，合成矢量均匀分布于坐标平面上，方向固定、长度可调[]。合成时，为避免矢量切换过程中过高的电压跳变以及对中性点电位的影响，插入零矢量，并选择 $1 \sim 2$ 个冗余状态小矢量，最终得到12个位置固定、大小可调的空间电压矢量。

选用表2固定合成矢量序列。电压序列起始矢量选用零矢量000，实现了矢量间的平滑切换，且相邻矢量间切换的电压幅值跳变低[12]。其中各分矢量在一个采样周期内的作用时间分别为 $0 . 1 T _ { \mathrm { s } }$ ，$0 . 1 5 T _ { \mathrm { s } }$ ， $0 . 1 5 T _ { \mathrm { s } }$ ， $0 . 3 T _ { \mathrm { s } }$ ， $0 . 1 5 T _ { \mathrm { s } }$ ， $0 . 1 5 T _ { \mathrm { s } }$

表2固定合成矢量法的合成矢量  
Tab.2Synthetic vectors of fixed composition vector method   

<html><body><table><tr><td>合成电压矢量</td><td colspan="6">固定合成矢量序列</td></tr><tr><td>V</td><td>000</td><td>100</td><td>1-1-1</td><td>0-1-1</td><td>-1-1-1</td><td>100</td></tr><tr><td>V</td><td>000</td><td>110</td><td>10-1</td><td>0-1-1</td><td>10-1</td><td>110</td></tr><tr><td>V</td><td>000</td><td>00-1</td><td>11-1</td><td>110</td><td>11-1</td><td>00-1</td></tr><tr><td>V4</td><td>000</td><td>-10-1</td><td>01-1</td><td>110</td><td>01-1</td><td>-10-1</td></tr><tr><td>V</td><td>000</td><td>010</td><td>-11-1</td><td>-10-1</td><td>-11-1</td><td>010</td></tr><tr><td>V</td><td>000</td><td>011</td><td>-110</td><td>-10-1</td><td>-110</td><td>011</td></tr><tr><td>V7</td><td>000</td><td>-100</td><td>-111</td><td>011</td><td>-111</td><td>-100</td></tr><tr><td>Vs</td><td>000</td><td>-1-10</td><td>-101</td><td>011</td><td>-101</td><td>-1-10</td></tr><tr><td>V</td><td>000</td><td>001</td><td>-1-11</td><td>-1-10</td><td>-1-11</td><td>001</td></tr><tr><td>V10</td><td>000</td><td>101</td><td>0-11</td><td>-1-10</td><td>0-11</td><td>101</td></tr><tr><td>Vi1</td><td>000</td><td>0-10</td><td>1-11</td><td>101</td><td>1-11</td><td>0-10</td></tr><tr><td>V12</td><td>000</td><td>0-1-1</td><td>1-11</td><td>101</td><td>1-11</td><td>0-1-1</td></tr></table></body></html>

改进拓扑结构的逆变器与传统的二极管钳位式三电平逆变器相比，开关通断组合是相同的，在控制策略上并未增加复杂性。

# 3基于定子磁链的模型参考自适应无速度传感器系统

# 3.1模型参考自适应系统原理

传统的电机无速度传感器系统，主要采用基于转子磁链的模型参考自适应系统（ModelReferenceAdaptiveSystem，MARS），即参考模型为不含待辨识转速的电压方程，可调模型选择含有待辨识转速的电流方程，输出量同为转子磁链，两者输出量比较产生的磁链误差经过自适应模块计算，得到转速估计值[13]。通过进一步调整可调模型中的参数，当两个模型误差趋向于零，便得到了实际转速值。传统模型参考自适应结构如图2所示。

# 3.2基于定子磁链的模型参考自适应

由于直接转矩控制不涉及转子磁链，而基于转子磁链的MARS需要观测转子磁链，这不仅增加了系统的复杂性，且与直接转矩控制的主要优点相背离。

![](images/8b46c8ee7f88e24440797a598b3b9d46f371f7b0c2df49466d8ca4ca9f31b470.jpg)  
图2参考模型自适应结构图  
Fig.2Reference model adaptive structure diagram

基于定子磁链模型的MARS无需对转子磁链、转子电流等进行观测。当误差方程趋于零时，估计定子磁链值可看作实际磁链值，直接用在直接转矩系统后续的磁链控制中。计算相对简单，较大程度地降低了系统的复杂性[14]。具体推导过程为

$$
\begin{array} { r l } & { \left\{ \begin{array} { l l } { \psi _ { \mathrm { s } } = L _ { \mathrm { s } } i _ { \mathrm { s } } + L _ { \mathrm { m } } i _ { \mathrm { r } } } \\ { \psi _ { \mathrm { r } } = L _ { \mathrm { r } } i _ { \mathrm { r } } + L _ { \mathrm { m } } i _ { \mathrm { s } } } \end{array} \right. } \\ & { \left\{ \begin{array} { l l } { u _ { \mathrm { s } } = L _ { \mathrm { s } } i _ { \mathrm { s } } + p \psi _ { \mathrm { s } } } \\ { R _ { \mathrm { r } } i _ { \mathrm { r } } + p \psi _ { \mathrm { r } } - \mathrm { j } \omega _ { \mathrm { r } } \psi _ { \mathrm { r } } = 0 } \end{array} \right. } \end{array}
$$

由式（1）可得异步电机定、转子磁链和电压方程为

$$
\begin{array} { r } { \left\{ \psi _ { _ \mathrm { s o } } = \sigma L _ { \mathrm { s } } i _ { \mathrm { s o } } + \frac { L _ { \mathrm { m } } } { L _ { \mathrm { r } } } \psi _ { _ { \mathrm { r o } } } \right. } \\ { \left\{ \psi _ { _ \mathrm { s } \mathrm { \scriptsize { \beta } } } = \sigma L _ { \mathrm { s } } i _ { \mathrm { s \beta } } + \frac { L _ { \mathrm { m } } } { L _ { \mathrm { r } } } \psi _ { _ { \mathrm { r \beta } } } \right. } \end{array}
$$

其中，σ=4L-L 5

对式（2）两边求导，得

$$
\begin{array}{c} \begin{array} { r } { \left\{ \hat { \psi } _ { \mathrm { s a } } = \sigma L _ { \mathrm { s } } \hat { i } _ { \mathrm { s a } } + \cfrac { L _ { \mathrm { m } } ^ { 2 } } { L _ { \mathrm { r } } T _ { \mathrm { r } } } i _ { \mathrm { s a } } + \cfrac { L _ { \mathrm { m } } } { L _ { \mathrm { r } } } \left( - \cfrac { 1 } { T _ { \mathrm { r } } } \psi _ { \mathrm { r a } } - \omega _ { \mathrm { r } } \psi _ { \mathrm { r \beta } } \right) \right.} \\ { \cfrac { \hat { \psi } _ { \mathrm { s } } } { \psi _ { \mathrm { s } } } = \sigma L _ { \mathrm { s } } \hat { i } _ { \mathrm { s \beta } } + \cfrac { L _ { \mathrm { m } } ^ { 2 } } { L _ { \mathrm { r } } T _ { \mathrm { r } } } i _ { \mathrm { s \beta } } + \cfrac { L _ { \mathrm { m } } } { L _ { \mathrm { r } } } \left( - \cfrac { 1 } { T _ { \mathrm { r } } } \psi _ { \mathrm { r \beta } } + \omega _ { \mathrm { r } } \psi _ { \mathrm { r a } } \right) } \end{array}   \end{array}
$$

联立式（1）、式（3）可得

$$
\left( \hat { \Psi } _ { \mathrm { s \downarrow } } ^ { \phantom { \dagger } } \right) = \sigma L _ { \mathrm { s } } \left( \hat { i } _ { \mathrm { s \downarrow } } ^ { \phantom { \dagger } } \right) + \left( \begin{array} { c c } { - \frac { 1 } { T _ { \mathrm { r } } } } & { - \omega _ { \mathrm { r } } } \\ { \omega _ { \mathrm { r } } } & { - \frac { 1 } { T _ { \mathrm { r } } } } \end{array} \right) \left( \boldsymbol { \Psi } _ { \mathrm { s \downarrow } } ^ { \phantom { \dagger } } \right) + \left( \begin{array} { c c } { \frac { L _ { \mathrm { s } } } { T _ { \mathrm { s } } } } & { \frac { L _ { \mathrm { o } } } { L _ { \mathrm { r } } } \omega _ { \mathrm { r } } } \\ { \frac { L _ { \mathrm { o } } } { L _ { \mathrm { r } } } \omega _ { \mathrm { r } } } & { \frac { L _ { \mathrm { s } } } { T _ { \mathrm { r } } } } \end{array} \right) \left( \hat { i } _ { \mathrm { s \downarrow } } ^ { \phantom { \dagger } } \right)
$$

其中， $L _ { \mathrm { { { \sigma } } } } = L _ { \mathrm { { r } } } L _ { \mathrm { { s } } } - L _ { \mathrm { { m } } } ^ { ~ 2 }$ 。 $L _ { \mathrm { m } }$ 为定、转子间的互感系数；

$L _ { \mathrm { s } }$ 为定子绕组的电感系数； $L _ { \mathrm { r } }$ 为转子绕组的电感系数。

定子磁链表达式为

$$
\begin{array} { r } { \left\{ \hat { \psi } _ { \mathrm { s o } } = U _ { \mathrm { s o } } - R _ { \mathrm { s } } i _ { \mathrm { s o } } \right. } \\ { \left\{ \hat { \psi } _ { \mathrm { s } \beta } = U _ { \mathrm { s } \beta } - R _ { \mathrm { s } } i _ { \mathrm { s } \beta } \right. } \end{array}
$$

将式（5）代入式（4)，可得

$$
\begin{array} { r } { \left( \begin{array} { c } { \hat { i } _ { \mathrm { s t } } } \\ { \hat { i } _ { \mathrm { s t } } } \end{array} \right) = \displaystyle { \frac { 1 } { \sigma L _ { \mathrm { s } } } \left( U _ { \mathrm { s s } } \right) } + \left( \begin{array} { c c } { \bar { R } _ { \mathrm { r } } } & { \underline { { \omega _ { \tau } } } } \\ { \bar { L } _ { \mathrm { o } } } & { \sigma \bar { L } _ { \mathrm { s } } } \end{array} \right) \left( \boldsymbol { \varPsi } _ { \mathrm { s t } } \right) - } \\ { \left( \begin{array} { c c } { \frac { T _ { r } R _ { \mathrm { s } } + L _ { \mathrm { s } } } { \sigma L _ { \mathrm { s } } T _ { \mathrm { s } } } } & { \bar { L } _ { \mathrm { o } } } \\ { \sigma L _ { \mathrm { s } } T _ { \mathrm { s } } } & { \bar { L } _ { \mathrm { s } } } \end{array} \right) \left( \boldsymbol { i } _ { \mathrm { s t } } \right) } \\ { - \omega _ { \mathrm { r } } } & { \frac { T _ { r } R _ { \mathrm { s } } + L _ { \mathrm { s } } } { \sigma L _ { \mathrm { s } } T _ { \mathrm { r } } } } \end{array}
$$

式中， $R _ { \mathrm { r } }$ 为转子电阻； $R _ { \mathrm { s } }$ 为定子电阻。

整理式（4）和式(6)，即得基于定子侧的以定子电流和定子磁链为状态量的可调模型[15]为

$$
\left( \begin{array} { c } { \hat { i } _ { \mathrm { a s } } } \\ { \hat { i } _ { \mathrm { B s } } } \\ { \hat { \psi } _ { \mathrm { a s } } } \\ { \hat { \psi } _ { \mathrm { p s } } } \end{array} \right) \left( \begin{array} { c c c c c } { \displaystyle \frac { - R _ { \mathrm { r } } } { \sigma L _ { \mathrm { r } } } - \frac { 1 } { \sigma L _ { \mathrm { r } } } } & { \displaystyle - \omega _ { \mathrm { r } } } & { \displaystyle \frac { R _ { \mathrm { r } } } { L _ { \mathrm { o } } } } & { \displaystyle \frac { \omega _ { \mathrm { r } } } { \delta L _ { \mathrm { s } } } } \\ { \displaystyle \omega _ { \mathrm { r } } } & { \displaystyle \frac { - R _ { \mathrm { r } } } { \delta L _ { \mathrm { r } } } - \frac { 1 } { \delta L _ { \mathrm { r } } } } & { \displaystyle - \frac { \omega _ { \mathrm { r } } } { \delta L _ { \mathrm { s } } } } & { \displaystyle \frac { R _ { \mathrm { r } } } { L _ { \mathrm { o } } } } \\ { \displaystyle - R _ { \mathrm { s } } } & { \displaystyle 0 } & { 0 } & { 0 } \\ { \displaystyle 0 } & { \displaystyle - R _ { \mathrm { s } } } & { 0 } & { 0 } \end{array} \right) \left( \begin{array} { c } { i _ { \mathrm { a s } } } \\ { i _ { \mathrm { b s } } } \\ { i _ { \mathrm { b s } } } \\ { U _ { \mathrm { a s } } } \\ { U _ { \mathrm { b s } } } \end{array} \right) \left( \begin{array} { c } { U _ { \mathrm { a s } } } \\ { \delta L _ { \mathrm { s } } } \\ { \delta L _ { \mathrm { s } } } \\ { U _ { \mathrm { a r } } } \\ { U _ { \mathrm { b s } } } \end{array} \right)
$$

由可调模型推导模型参考自适应的自适应率为

$$
{ \hat { \omega } } = \left( k _ { \mathrm { p } } + { \frac { k _ { \mathrm { i } } } { s } } \right) \left[ \left( i _ { \mathrm { \beta s } } - { \hat { i } } _ { \mathrm { \beta s } } \right) \left( { \hat { i } } _ { \mathrm { a s } } - { \frac { 1 } { \delta L _ { \mathrm { s } } } } { \hat { \Psi } } _ { \mathrm { a s } } \right) - \left( i _ { \mathrm { a s } } - { \hat { i } } _ { \mathrm { a s } } \right) \left( { \hat { i } } _ { \mathrm { \beta s } } - { \frac { 1 } { \delta L _ { \mathrm { s } } } } { \hat { \Psi } } _ { \mathrm { \beta s } } \right) \right]
$$

式中， $i _ { \mathrm { { o s } } }$ 、 $i _ { \beta \mathrm { s } }$ 可由直接测量电机定子电流值得到;（20 $\hat { i } _ { \alpha s }$ 、 $\hat { i } _ { \beta s }$ 、 $\hat { \psi } _ { \mathrm { a s } }$ 、 $\hat { \psi } _ { \scriptscriptstyle  { \beta s } }$ 可由上述可调模型计算得到。基于定子磁链MARS的框图如图3所示。

![](images/79d469e3b9fed3b457c60231bd4de36bcabc03ba4dc948bd4127f6f4ee33de4c.jpg)  
图3基于定子磁链的模型参考自适应系统框图 Fig.3The block diagram of model reference adaptive system based on stator flux

# 3.3改进定子磁链MARS中磁链观测器部分

以上完全基于定子侧模型MARS的方法中涉及到定子磁链的计算，使用纯积分器造成定子磁链观测器产生直流偏置误差和初始积分误差[16]。改进方法采用低通滤波器替换纯积分器，可消除部分直流误差信号。

模型中定子磁链计算式为

$$
\begin{array} { r } { \displaystyle \int { \varPsi _ { \mathrm { s o } } } = \int E _ { \mathrm { s o } } \mathrm { d } t } \\ { \displaystyle \left[ { \varPsi _ { \mathrm { s } \beta } } = \int E _ { \mathrm { s } \beta } \mathrm { d } t \right. } \end{array}
$$

采用一阶低通滤波器替代纯积分器，输入输出关系为

$$
\left\{ \begin{array} { l l } { \displaystyle \psi _ { \mathrm { s o } } = \frac { 1 } { s + \omega _ { \mathrm { c } } } E _ { \mathrm { s o } } + \frac { \omega _ { \mathrm { c } } } { s + \omega _ { \mathrm { c } } } \psi _ { \mathrm { s o } } } \\ { \displaystyle \psi _ { \mathrm { s } \beta } = \frac { 1 } { s + \omega _ { \mathrm { c } } } E _ { \mathrm { s } \beta } + \frac { \omega _ { \mathrm { c } } } { s + \omega _ { \mathrm { c } } } \psi _ { \mathrm { s } \beta } } \end{array} \right.
$$

式中， $\omega _ { \mathrm { c } }$ 为截止频率。使用低通滤波器消除了积分初值的误差，减小了系统直流偏移，磁链环宽变窄，避免了转矩波动和电机转子振动[17]。

# 3.4改进的感应电机直接转矩控制系统结构

基于改进三电平定子磁链无速度传感器技术的直接转矩控制系统整体结构如图4所示。其中磁链估算值近似等于定子磁链实际值，将此定子磁链值与给定的定子磁链值进行比较；辨识的转速可认为是实际转速。将辨识转速与给定转速进行比较，通过PI调节器得到给定转矩值，同时检测电机输出的定子电压和电流信号，计算实际转矩的大小，与转矩的给定值进行比较。经过上述比较后得到控制信号，采用合成矢量法制定逆变器开关表，最终输出6路PWM控制信号驱动三电平逆变器。实现对电机定子磁链和电磁转矩的控制[18]。

![](images/ab07029bd623288659df2041e86490ad272b56d6c4e50faaf2f7a7c261c9e7c3.jpg)  
图4改进的感应电机直接转矩控制系统 Fig.4The improved direct torque control system of induction motor

# 4 仿真实验

为验证以上分析，在Simulink环境下进行仿真实验。其中逆变器的直流母线电压 $U _ { \mathrm { d } } = 4 0 0 \mathrm { V }$ ，磁链给定值 $\boldsymbol { \varPsi } ^ { * } = 0 . 2 \mathrm { W } \mathrm { b }$ 。感应电机参数为：极对数 $n _ { \mathrm { p } }$ $= 4$ ；定子电阻 $R _ { \mathrm { r } } = 2 . 4 7 3 \Omega$ ；转子电阻 $R _ { \mathrm { s } } = ~ 2 . 4 7 3 \Omega$ 电感 $L _ { d } = L _ { q } = 0 . 9 9 1 \mathrm { m H }$ ；转子磁链 $\psi _ { \mathrm { f } } = 0 . 2 1 5 \mathrm { W b }$ ；转动惯量 $J { = } 0 . 8 \times 1 0 ^ { - 4 } \mathrm { k g \cdot m } ^ { 2 }$ ；摩擦系数 $B = 0$ 。

图5分别是传统DTC系统和改进DTC系统在给定参考定子磁链幅值为 $0 . 2 \mathrm { W b }$ 时的定子磁链轨迹。

![](images/0e8be217f8dcfc7a35540a3f992d1199866ebb176e029138cd7804b1b7b2ccf6.jpg)  
图5定子磁链圆波形

图5表明，在磁链圆给定实际半径幅值为$0 . 2 \mathrm { W b }$ 时，传统DTC系统磁链圆半径在0.215Wb处波动；改进磁链观测器DTC系统定子磁链圆半径为 $0 . 2 \mathrm { W b }$ ，环宽变窄。这说明低通滤波器能有效消除直流偏移量对磁链的影响，减小定子磁链脉动，使定子磁链圆环宽度变窄，磁链观测值更加精确。

图6为给定转速在0.1s时从 $5 0 \mathrm { r / m i n }$ 跳变到$ { 5 0 0 }  { \mathrm { r / m i n } }$ 、转矩在0.2s由 $4 \mathrm { N } \cdot \mathrm { m }$ 跳变到 $1 0 \mathrm { N \cdot m }$ 时，分别采用传统DTC系统和改进DTC系统得到

的电磁转矩响应曲线。

![](images/b7e872676841e4f412ffd32b4356a6c908d11bd8f38501deaa4c3b0adfd7db8b.jpg)  
图6转矩响应曲线  
Fig.6The torque response curves

图6表明，系统在0.2s突加负载时，相比传统DTC系统，改进DTC系统输出电磁转矩脉动减小,转矩的动态响应加快，在外界增加干扰条件下仍能保持比较好的控制效果。这说明改进系统通过准确补偿磁链和转矩的偏差，增强了系统的抗干扰性，实现了磁链和转矩的精确控制。

将系统初始转速设定为 $5 0 \mathrm { r / m i n }$ 低速运行模式。图7分别为传统无速度传感器DTC系统和改进DTC系统的低速响应曲线。

将系统初始转速设定为 $1 ~ 0 0 0 \mathrm { r / m i n }$ 高速运行模式。图8分别为传统DTC系统和改进DTC系统的高速响应曲线。

![](images/419a6a2db86dd2f0c99f43527c1ee30b9bf224d8f3c6e1bffaeff1ebcc587648.jpg)  
Fig.5The stator flux circle waveforms   
(a）传统无速度传感器DTC系统

![](images/00e587af4829e1b411f0265f607a3efd3702f365d1ebc8424508cfc34fa9f98a.jpg)  
图7系统低速响应曲线

![](images/0b581701beb2cd74a0aed88cf93df59844749dc17ec7c9d702f2a7418f31fd55.jpg)  
Fig.7The low speed response curves of system   
图8系统高速响应曲线  
Fig.8The high speed sponse curves of system

表3、表4表明，电机在全速范围内运行时，改进DTC系统与传统无速度传感器DTC系统相比，动态性能指标提高，调节时间缩短，超调量下降，转速稳态精度高。这是由于改进系统通过系统自身具有的磁链观测器来计算磁链，这样既可以降低系统复杂度、缩短系统调节时间，也可以保证磁链观测的准确性，提高控制精度，实现高精度的速度辨识。

以上几种运行状况的仿真实验，验证了三电平逆变器的感应电机直接转矩控制无速度传感器系统的可行性，且系统动态响应加快，抗干扰能力加强。在工程中应用可较大程度地节省开支，克服各种工况扰动，具有很好的实际应用价值。

Tab.3 Comparison of low speed performance indexes   
表4高速性能指标对比  

<html><body><table><tr><td></td><td>超调量(%)</td><td>调节时间/s</td><td>稳态误差(%)</td></tr><tr><td>传统DTC系统</td><td>60</td><td>0.05</td><td>10</td></tr><tr><td>改进 DTC系统</td><td>0.1</td><td>0.001</td><td>0.001</td></tr></table></body></html>

表3低速性能指标对比  
Tab.4 Comparison of high speed performance indexes   

<html><body><table><tr><td></td><td>超调量(%)</td><td>调节时间/s</td><td>稳态误差(%)</td></tr><tr><td>传统DTC系统</td><td>5</td><td>0.07</td><td>3.3</td></tr><tr><td>改进DTC系统</td><td>0.01</td><td>0.09</td><td>0.001</td></tr></table></body></html>

# 5 结论

通过仿真实验，证明了改进感应电机直接转矩控制系统控制策略的有效性。改进的三电平供电技术节省了电力电子器件使用成本；改进的磁链观测器明显降低了直流偏移量对系统的干扰，磁链误差更小，为后续速度计算提供良好的基础数据；基于定子磁链的无速度传感器相比基于转子磁链的无速度传感器较大程度地简化了系统结构，提高了系统的抗干扰能力。整个系统在工程应用中的价值得到提升，具有一定的理论和工程应用意义。

# 参考文献

[1] 王成元，夏加宽，孙标宜．现代电机控制技术[M].北京：机械工业出版社，2014.  
[2] 李永东，侯轩，谭卓辉．三电平逆变器异步电动机直接转矩控制系统——单一矢量法[J]．电工技术学报，2004，19(4)：34-39.Li Yongdong, Hou Xuan, Tan Zhuohui.Direct torquecontrol system of induction motor for three levelinverter single vector method[J].Transactions ofChina Electrotechnical Society,2004,19(4):34-39.  
[3] 李永东，等．三电平逆变器异步电动机直接转矩控制系统合成矢量法[J]．电工技术学报，2004，19(5): 31-35.Li Yongdong,et al. Direct torque control systemfor induction motor with three level invertersynthesis vector method[J].Transactions of ChinaElectrotechnical Society,2004,19(5): 31-35.  
[4]林磊，等．一种具有中点平衡功能的三电平异步电机直接转矩控制方法[J]．中国电机工程学报,2007，27(3): 46-50.Lin Lei, et al.A direct torque control method for threelevel induction motors with neutral point balancingfunction[J]. Proceedings of the Chinese Society ofElectrical Engineering,2007,27(3): 46-50.  
[5] 金晓炜．基于三电平逆变器的异步电动机直接转矩控制研究[D]．杭州：浙江工业大学，2007.  
[6] 理文祥．高性能无速度传感器直接转矩控制系统的研究[D]．广州：华南理工大学，2012.  
[7] 周旭．基于无速度传感器的异步电动机直接转矩控制系统的研究[D]．镇江：江苏大学，2007.  
[8] 李奔，王德军．基于无速度传感器的直接转矩控制系统优化[J]．吉林大学学报（信息科学版），2016，34(1): 39-46.Li Ben, Wang Dejun. Optimization of direct torquecontrol system based on speed sensorless[J]. Journalof Jilin University(Information Science Edition),2016, 34(1): 39-46.  
[9] 王玲，高芳，高锐．一种快速三电平逆变器 SVPWM算法[J]．电气传动，2015，45(10)：26-29.Wang Lin, Gao Fang,Gao Rui. A fast SVPWMalgorithm for three level inverter[J].Electric Drive,2015, 45(10): 26-29.  
[10]杨超，谢维达，袁登科，等．一种新型的三电平逆变器拓扑结构研究[J]．机电一体化，2011,15(5): 74-77.Yang Chao,Xie Weida, Yuan Dengke,et al.A newtype of three level inverter topology research[J].Mechatronics,2011, 15(5): 74-77.  
[11]韩晔，厉虹．基于改进自抗扰控制的永磁同步电机无传感器系统研究[J]．电机与控制应用，2017，44(2): 33-40.Han ye,Li Hong. Research on sensorless systemof PMSM based on improved active disturbancerejection control[J]. Motor and Control Application,2017, 44(2): 33-40.  
[12]祝龙记，王汝琳．基于直接转矩控制的高性能磁链观测与速度观测[J]．电机与控制学报，2004,8(3):209-213.Zhu Longji, Wang Rulin. High performance fluxlinkage observation and speed observation basedon direct torque control[J]. Journal of ElectricalMachinery and Control, 2004,8(3): 209-213.  
[13]刘勇利．三电平逆变器直接转矩控制系统的研究[D]．太原：太原科技大学，2017.  
[14] 赵鹏，郜亚秋，孙树敏，等．基于三电平变流器的 PMSM无速度传感器控制研究[J].大电机技术,2016(6): 31-36.Zhao Peng,Gao Yaqiu,Sun Shumin,et al. Studyon speed sensorless control of PMSM based onthree-level inverter[J].Large Electric Machine andHydraulic Turbine,2016(6): 31-36.  
[15]夏浩瑄，刘子胥．基于SVPWM的变参数 MRAS速度辨识模型仿真与研究[J]．电气传动，2014,44(5):31-34，39.Xia Haoxuan,Liu Zixu.Research and simulationof varying parameters MRAS speed identificationmode1 based on SVPWM[J]. Electric Drive,2014,44(5): 31-34, 39.  
[16] 魏巍．基于三电平逆变器的转子磁场定向控制系统的研究与设计[D]．沈阳：东北大学，2013.  
[17] 周洋．基于DSP的三电平异步电机直接转矩控制的研究[D]．鞍山：辽宁科技大学，2012.  
[18] 朱群．三电平DTC控制逆变器中磁链观测器对电动机输出性能的影响[D]．西安：西安理工大学,2010.