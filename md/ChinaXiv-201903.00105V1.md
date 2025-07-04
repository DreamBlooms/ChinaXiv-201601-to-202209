# 基于脉振高频电流注入法的SPMSM初始位置检测方法

陈建松1 柏文杰周融刘丽东²刘兵 魏佳丹(1.南京出入境检验检疫局 南京 2111062.中国合格评定国家认可中心 北京 1000623.南京航空航天大学电气工程系 南京 211106)

![](images/b33e1a29dd56ac9445ba5be3caa28d1862f9902b2ae5ddd703cff86394b3504e.jpg)

陈建松 男 1961年生，研究员，博士，研究方向为电机性能检测技术。

摘要：采用脉振高频电流注入法进行表贴式永磁同步电机初始位置估计时需进行磁极判断，针对传统的注入正负脉冲电压的方法存在转子抖动、检测时间长等问题，提出了一种分区间积分的方法，将一个注入信号周期均匀分割成四个区间，在区间I和Ⅲ内对 $d$ 轴高频电压响应进行积分，根据积分值的符号判断 $d$ 轴正方向，该方法无需额外注入正负脉冲信号判断 $d$ 轴正方向，缩短了估计时间，简化了估计过程，避免了小惯量电机在注入正负脉冲电压时可能导致的转子抖动问题，拓宽了应用范围。理论分析、仿真和实验结果均验证了该方法的正确性。

关键词：SPMSM 高频电流注入磁极判断 初始位置检测中图分类号：TM351

# Initial Rotor Position Detection Method of SPMSM Based on High Frequency Current Injection Method

![](images/421e15c1f14bacbf5407a86975a5325966c5694529065d9ab764d44d12454567.jpg)

柏文杰男 1987年生，工程师，研究方向为电机性能检测技术。

Chen Jiansong' Bai Wenjie'Zhou Rong' Liu Lidong²Liu Bing³ WeiJiadan³ (1.Nanjing Entry-Exit Inspection and Quarantine BureauNanjing211106China 2. China National Accreditation Service for Conformity Assessment Beijing100062 China 3.University of Aeronautics & AstronauticsNanjing 21106 China)

Abstract: In the paper, the high frequency sinusoidal current injection method is used to detect the initial rotor position. When a high frequency current is injected into $d$ -axis,the saturation of magnetic field in $d$ -axis can lead to high frequency voltage response.A detailed analysis on the convergence of initial rotor position is given.To solve the problems such as rotor jitter, long testing time,which is introduced by the traditional method of injecting negative and positive pulse voltage, a new polarity detection is proposed.A signal injection cycle is divided into four interval and the $d .$ -axis direction is determined by the sign of the integral value of high frequency voltage response in interval of I and III. This method does not need additional injection of positive and negative pulse signal to determine $d$ -axis direction,shortens the time estimates,simplifies the estimation process,avoids the rotor small vibration problem when injecting positive and negative pulse voltage. The theory analysis, simulation and experimental results validate the effectives of the method.

Keywords: Surfue-mounted permanent-magnet synchronous machines,high frequency current injection, magnetic polarity detection, initial rotor position estimation

# 1 引言

永磁同步电机（Permanent-Magnet SynchronousMachines，PMSM）凭借其高功率密度和高效率的优点得到了广泛的应用。但其控制过程需要准确获知转子位置，而机械式位置传感器存在体积质量大、成本高、安装困难以及特殊应用场合下可靠性差的问题，因此诸多学者致力于PMSM无传感器控制技术的研究，其中电机静止和低速区域的位置估计为一大研究热点和难点。研究大多采用高频信号注入法实现物理凸极或饱和凸极特性的跟踪。对于内埋式永磁同步电机，其交、直轴电感不相等，存在物理凸极，常采用旋转高频信号注入法[1-5]。而对于表贴式永磁同步电机（Surfue-MountedPermanent-Magnet Synchronous Machines，SPMSM)， 其交、直轴电感近似相等，凸极性不明显，需要外加激励信号以产生饱和凸极，因此常采用脉振高频信号注入法[6-10]

传统脉振高频信号注入法多采用电压注入方式，其实现方式相对简单，但需要在dq轴电流回路中加入两个低通滤波器(LowPassFilter，LPF)，这增加了系统的复杂程度。因此，本文选用脉振高频电流注入法进行SPMSM的初始位置检测，与电压注入法相比，结构更加简单，转子位置误差函数的收敛性不受阻抗变化的影响，有利于提高系统稳定性。

初始位置估计分为初次初始位置估计和磁极判断两步。现有文献部分采用脉冲电压注入的方法进行磁极判断，在估计 $d$ 轴的正、负方向分别注入一个幅值和脉宽相等的脉冲电压，以磁极方向与正向脉冲电压同向为例，正向脉冲电压形成正向电流响应，此时磁路饱和，阻抗变小，电流响应的幅值较大；负向脉冲电压形成负向电流响应，此时磁路不饱和，阻抗变大，电流响应的幅值较小，从而可以通过检测正、负向脉冲电压下的电流响应幅值来获取磁极信息。但是额外的电压注入必然会耗费较多的时间，同时注入脉冲电压的幅值和脉宽若选择不当则会影响磁极判断的准确性，在小惯量电机中，注入 $d$ 轴的脉冲电压可能会引起转子的微动，进而造成转子位置估计误差。

综上，若能避免额外注入正、负脉冲电压，而仅从高频电流响应中提取磁极方向信息，那么将简化初始位置估计过程，提高位置估计的可靠性。本文将一个注入信号周期均匀分割成四个区间，在区间I和III内对 $d$ 轴高频电压响应进行积分，根据积分值的符号判断 $d$ 轴正方向，该方法不需要注入正负脉冲电压，缩短了初始位置估计时间，简化了估计过程，降低了电流检测精度的要求，避免了小惯量电机在注入正、负电压脉冲时可能导致的转子抖动问题，拓宽了应用范围，且算法简单，易于实现，仿真和实验结果均验证了理论分析的正确性。

# 2 永磁同步电机数学模型

对于PMSM，假设定子磁场呈正弦分布，并忽略磁滞和涡流损耗等影响，采用 $i _ { d } = 0$ 转子磁场定向控制，在同步旋转坐标系 $d q$ 轴系下的电压方程为

$$
\left\{ \begin{array} { l } { \displaystyle u _ { d } = r _ { \mathrm { s } } i _ { d } + L _ { d } \frac { \mathrm { d } i _ { d } } { \mathrm { d } t } - \omega _ { \mathrm { r } } L _ { q } i _ { q } } \\ { \displaystyle } \\ { u _ { q } = r _ { \mathrm { s } } i _ { q } + L _ { q } \frac { \mathrm { d } i _ { q } } { \mathrm { d } t } + \omega _ { \mathrm { r } } L _ { d } i _ { d } + \omega _ { \mathrm { r } } \varPsi _ { \mathrm { f } } } \end{array} \right.
$$

式中， $u _ { d } , \ u _ { q }$ 为 $d , \ q$ 轴电压； $i _ { d } .$ ， $i _ { \boldsymbol { q } }$ 为 $d , \ q$ 轴电流；$L _ { d }$ ， $L _ { q }$ 为 $d$ ， $q$ 轴电感； $r _ { \mathrm { s } }$ 为定子电阻； $\psi _ { \mathrm { f } }$ 为永磁体与定子交链的磁链； $\omega _ { \mathrm { r } }$ 为转子的电角速度。

在零速或低速时，可忽略式（1）中的交叉耦合项和反电动势部分，dq轴系下的电压方程简化为

$$
\left\{ \begin{array} { l } { \displaystyle u _ { d } = r _ { s } i _ { d } + L _ { d } \frac { \mathrm { d } i _ { d } } { \mathrm { d } t } } \\ { \displaystyle } \\ { u _ { q } = r _ { s } i _ { q } + L _ { q } \frac { \mathrm { d } i _ { q } } { \mathrm { d } t } } \end{array} \right.
$$

# 3 脉振高频电流注入法

# 3.1脉振高频电流注入法原理

定义：实际转子同步旋转坐标系为dq轴系，其$d$ 轴与A相绕组轴线的夹角为 $\theta$ ；估计转子同步旋转坐标系为 $\hat { d } \hat { q }$ 轴系，其 $\hat { d }$ 轴与A相绕组轴线的夹角为 $\hat { \theta }$ ；两相静止坐标系为 $\alpha \beta$ 轴系，其 $\mathbf { \alpha } _ { \mathrm { ~ \textsc ~ { ~ d ~ } ~ } }$ 轴与A相绕组轴重合；位置估计误差为

$$
\Delta \theta = \theta - \hat { \theta }
$$

各坐标系之间的关系如图1所示。

![](images/99eac124a7fe77f4b8baff708d5566d4972e8966bcf20172a8b30e163d03187b.jpg)  
图1各坐标系之间的关系  
Fig.1The relationship among three reference frames

若只在 $\hat { d }$ 轴注入一个幅值合适的高频电流信号，其在估计 $d q$ 轴系下的表达式为

$$
\begin{array} { r } { \left\{ \hat { i } _ { d h } = I _ { \mathrm { m } h } \sin \omega _ { h } t \right. } \\ { \left. \hat { i } _ { q h } = 0 \right. } \end{array}
$$

式中， $\hat { i } _ { d h }$ 为高频电流激励下的 $\hat { d }$ 轴电流； $\hat { \boldsymbol { q } }$ 为高频 电流激励下的dq轴电流； $I _ { \mathrm { m } h }$ 为注入高频电流的幅 值； $\omega$ 为注入高频电流的角频率。

代入永磁同步电机的数学模型，忽略定子阻抗，在轴系下的高频电压响应表达式为

$$
\hat { u } _ { { \boldsymbol q } h } = \omega _ { h } \Delta L \sin 2 \Delta \theta I _ { \mathrm { m } h } \cos \omega _ { h } t
$$

式中， $\hat { u } _ { { \boldsymbol q } h }$ 为 $\hat { q }$ 轴上的高频电压响应； $\Delta L$ 为 $d q$ 轴差模电感，且 $\Delta L = ( L _ { d } - L _ { q } ) / 2$ 。

由式（5）可知，饱和凸极性使得 $\hat { \boldsymbol { q } }$ 轴高频电压响应 $\hat { u } _ { { q } h }$ 中包含位置估计误差 $\Delta \theta$ ，若通过一定的调制提取出 $\Delta \theta$ ，再构建估计位置闭环，将 $\Delta \theta$ 调节到0，从而估计位置就和实际位置重合，实现转子位置估计。

# 3.2初始位置检测

首先从 $q$ 轴电压响应中提取 $\omega _ { h }$ 次谐波，所得高频信号形式见式(5)，将 $\hat { u } _ { { } _ { q h } }$ 与cos $\omega _ { h } t$ 相乘进行调制，可得

$$
\hat { u } _ { q h } \cos \omega _ { h } t = \frac { \omega _ { h } \Delta L I _ { \mathrm { m } h } \sin 2 \Delta \theta ( 1 + \cos 2 \omega _ { h } t ) } { 2 }
$$

式（6）中包含了直流分量和高次谐波分量 $\cos 2 \omega _ { h } t$ 经过低通滤波器提取其中的直流分量，即可得到转子位置误差函数为

$$
f ( \Delta \theta ) = \mathrm { L P F } ( \hat { u } _ { q h } \cos \omega _ { h } t ) = \frac { \omega _ { h } \Delta L I _ { \mathrm { m } h } } { 2 } \sin 2 \Delta \theta
$$

采用PI调节器将 $f ( \Delta \theta )$ 调节到0，得到初次初始位置估计值 $\hat { \theta }$ 。信号处理模块如图2所示。

$$
\xrightarrow [ ] { \cos \omega _ { h } t } [ \mathrm { L P F } ] { f ( \Delta \theta ) } \xrightarrow [ ] { \hat { \omega } } [ \xrightarrow [ ] { \hat { \mathrm { I } } } ] { \hat { \omega } } [ \hat { \mathrm { I } } ] { \hat { \omega } _ { 0 } } .
$$

图2信号处理模块  
Fig.2The signal modulation process   
Fig.3Curve graph of $f ( \Delta \theta )$

# 3.3初始位置收敛性分析

图3为 $f ( \Delta \theta )$ 曲线，当 $f ( \Delta \theta ) = 0$ 时，在闭环调节的作用下 $\Delta \theta$ 可能收敛到0、 $\pi / 2$ 、 $\pi$ 、 $3 \pi / 2$ 和 $2 \pi$ 位置，但有些收敛点的位置是不稳定的。

![](images/1b19eba0cc99c3b76459b77203392e82d0a9f52e99234161e3628def0748179b.jpg)  
图3 $f ( \Delta \theta )$ 曲线

当 $\Delta \theta { \in } ( \pi / 4 , ~ 3 \pi / 4 )$ 时，收敛点处于 $\Delta \theta = \pi / 2$ 位置，若 $\Delta \theta$ 产生一个微小的正向扰动，使得 $\Delta \theta > \pi / 2$ ，则$f ( \Delta \theta ) < 0$ ，经过PI调节器后 $\hat { \theta } _ { 0 }$ 减小，从而 $\Delta \theta = \theta - \hat { \theta }$ 增大，即 $\Delta \theta$ 产生正向扰动时，在调节器的作用下会偏离收敛点 $\Delta \theta = \pi / 2$ ；若 $\Delta \theta$ 产生一个微小的负向扰动，使得 $\Delta \theta < \pi / 2$ ，则 $f ( \Delta \theta ) > 0$ ，经过PI调节器后 $\hat { \theta } _ { 0 }$ 增大，从而 $\Delta \theta = \theta - \hat { \theta }$ 减小，即 $\Delta \theta$ 产生负向扰动时，在调节器的作用下也会偏离收敛点 $\Delta \theta =$ $\pi / 2$ ，因此， $\Delta \theta = \pi / 2$ 是一个不稳定的收敛点，由于$\Delta \theta = \pi / 2$ 是曲线 $f ( \Delta \theta )$ 的一个反向过零点，因此该调节系统对于反向过零点是不稳定的。

当 $\Delta \theta { \in } ( 3 \pi 4 , \ 5 \pi 4 )$ 时，收敛点处于 $\Delta \theta = \pi$ 位置，若 $\Delta \theta$ 产生一个微小的正向扰动，使得 $\Delta \theta = \pi$ ，则$f ( \Delta \theta ) > 0$ ，经过PI调节器后 $\hat { \theta } _ { 0 }$ 增大，从而 $\Delta \theta = \theta - \hat { \theta }$ 减小，即 $\Delta \theta$ 产生正向扰动时，在调节器的作用下会被反向拉回到收敛点 $\Delta \theta = \pi$ ；若 $\Delta \theta$ 产生一个微小的负向扰动，使得 $\Delta \theta < \pi$ ，则 $f ( \Delta \theta ) < 0$ ，经过PI调节器后 $\hat { \theta } _ { 0 }$ 减小，从而 $\Delta \theta = \theta - \hat { \theta }$ 增大，即 $\Delta \theta$ 产生负向扰动时，在调节器的作用下也会被反向拉回到收敛点 $\Delta \theta = \pi$ ，因此， $\Delta \theta = \pi$ 是一个稳定的收敛点，由于 $\Delta \theta = \pi$ 是曲线 $f ( \Delta \theta )$ 的一个正向过零点，因此该调节系统对于正向过零点是稳定的。

综上，该估计位置闭环系统的稳定收敛点为$\Delta \theta = 0$ 或 $\pi$ ，因此，在初次初始位置估计完成后还需对磁极方向进行判断才能得到准确的转子初始位置。

# 3.4分区间磁极判断法

初次初始位置估计结束后，转子位置估计误差$\Delta \theta = 0$ 或 $\pi$ ，估计 $d$ 轴电流在PR调节器的作用下与给定一致，即 $\hat { i } _ { d } = I _ { \mathrm { m } h } \sin \omega _ { h } t$ ，估计 $d$ 轴的电压方程可表示为

$$
\hat { u } _ { d } = R _ { \mathrm { s } } \hat { i } _ { d } + L _ { d } ( i _ { d } ) \frac { \mathrm { d } \hat { i } _ { d } } { \mathrm { d } t }
$$

对应的 $d$ 轴高频电压响应为

$\hat { u } _ { d h } = R _ { s } I _ { \mathrm m h } \sin \omega _ { h } t + \omega _ { h } L _ { d } ( i _ { d } ) I _ { \mathrm m h } \cos \omega _ { h } t$ $\hat { u } _ { d h }$ 和 $\omega _ { h } t$ 的关系如图4所示。

![](images/79e5aa529fb5db45149409e2abc8761e64f0cc31fea4b0ca3e4f1e29a7960ef8.jpg)  
图4號 $\hat { u } _ { d h }$ 波形分割示意图

由于 $d$ 轴磁场的饱和， $d$ 轴电感满足以下关系

$$
L _ { d } ( i _ { d } > 0 ) < L _ { d 0 } < L _ { d } ( i _ { d } < 0 )
$$

对 $\hat { u } _ { d h }$ 的区间进行分割，并分别积分，得

$$
\begin{array} { r l } & { \bigg [ \int _ { 0 } ^ { \pi / 2 } \hat { u } _ { d h } \mathrm { d } ( \omega _ { h } t ) = R _ { s } I _ { \mathrm { m } h } + \int _ { 0 } ^ { \pi / 2 } \big [ \omega _ { h } L _ { d } ( i _ { d } ) I _ { \mathrm { m } h } \cos { \omega _ { h } t } \big ] \mathrm { d } ( \omega _ { h } t ) } \\ & { \bigg [ \int _ { \pi } ^ { 3 \pi / 2 } \hat { u } _ { d h } \mathrm { d } ( \omega _ { h } t ) = - R _ { s } I _ { \mathrm { m } h } + \int _ { \pi } ^ { 3 \pi / 2 } \big [ \omega _ { h } L _ { d } ( i _ { d } ) I _ { \mathrm { m } h } \cos { \omega _ { h } t } \big ] \mathrm { d } ( \omega _ { h } t ) } \end{array}
$$

若 $d$ 轴方向判断正确，则

$$
\begin{array} { r } { \int _ { \mathrm { \Omega } _ { 0 } } ^ { \pi / 2 } \hat { u } _ { d h } \mathrm { d } ( \omega _ { h } t ) < R _ { s } I _ { \mathrm { m } h } + \int _ { \mathrm { \Omega } _ { 0 } } ^ { \pi / 2 } ( \omega _ { h } L _ { d 0 } I _ { \mathrm { m } h } \cos { \omega _ { h } t } ) \mathrm { d } ( \omega _ { h } t ) } \\ { < R _ { s } I _ { \mathrm { m } h } + \omega _ { h } L _ { d 0 } I _ { \mathrm { m } h } ~ ( 1 2 \pi ^ { 2 } \cos { \omega _ { h } t } ) ~ } \end{array}
$$

$$
\begin{array} { r } { \int _ { \pi } ^ { 3 \pi / 2 } \hat { u } _ { d h } \mathrm { d } ( \omega _ { h } t ) < - R _ { s } I _ { \mathrm { m } h } + \int _ { \pi } ^ { 3 \pi / 2 } ( \omega _ { h } L _ { d 0 } I _ { \mathrm { m } h } \cos { \omega _ { h } t } ) \mathrm { d } ( \omega _ { h } t ) } \\ { < - R _ { s } I _ { \mathrm { m } h } - \omega _ { h } L _ { d 0 } I _ { \mathrm { m } h } \qquad ( 1 3 ) } \end{array}
$$

此时，分区间积分值为

$$
k _ { \mathrm { I , I I I } } = \left[ \int _ { 0 } ^ { \pi / 2 } \hat { u } _ { d h } \mathrm { d } ( \omega _ { h } t ) + \int _ { \pi } ^ { 3 \pi / 2 } \hat { u } _ { d h } \mathrm { d } ( \omega _ { h } t ) \right] < 0
$$

同理，若 $d$ 轴方向相反，则

$$
\begin{array} { r l r } { \int _ { 0 } ^ { \pi / 2 } \hat { u } _ { d h } \mathrm { d } ( \omega _ { h } t ) > R _ { s } I _ { \mathrm { m } h } + \int _ { 0 } ^ { \pi / 2 } ( \omega _ { h } L _ { d 0 } I _ { \mathrm { m } h } \cos \omega _ { h } t ) \mathrm { d } ( \omega _ { h } t ) } & { } & \\ { > R _ { s } I _ { \mathrm { m } h } + \omega _ { h } L _ { d 0 } I _ { \mathrm { m } h } } & { } & { ( 1 } \end{array}
$$

$$
\begin{array} { r } { \int _ { \pi } ^ { 3 \pi / 2 } \hat { u } _ { d h } \mathrm { d } ( \omega _ { h } t ) > - R _ { s } I _ { \mathrm { m } h } + \int _ { \pi } ^ { 3 \pi / 2 } ( \omega _ { h } L _ { d 0 } I _ { \mathrm { m } h } \cos { \omega _ { h } t } ) \mathrm { d } ( \omega _ { h } t ) } \\ { > - R _ { s } I _ { \mathrm { m } h } - \omega _ { h } L _ { d 0 } I _ { \mathrm { m } h } \qquad ( 1 6 ) } \end{array}
$$

此时，分区间积分值为

$$
k _ { \mathrm { _ { I , I I I } } } = \left[ \int _ { 0 } ^ { \pi / 2 } \hat { u } _ { d h } \mathrm { d } ( \omega _ { h } t ) + \int _ { \pi } ^ { 3 \pi / 2 } \hat { u } _ { d h } \mathrm { d } ( \omega _ { h } t ) \right] > 0
$$

从上述分析可知，区间I和III的积分值符号可用于判断 $d$ 轴正方向，若积分值小于0，则初始估计位置磁极方向为正；若积分值大于0，则初始估计位置磁极方向为负。

综上所述，采用脉振高频电流注入法实现转子初始位置估计，分为初次初始位置估计和磁极方向判断两步，如图5所示。首先在 $\hat { d }$ 轴注入高频正弦电流，检测 $\hat { q }$ 轴电流响应进行初次初始位置估计，得到初次估计位置 $\hat { \theta } _ { 0 }$ ；然后检测 $\hat { d }$ 轴电压响应进行磁极方向判断，得到补偿角 $\theta _ { \mathrm { c } }$ ，最终估计位置为

$$
\hat { \theta } = \hat { \theta } _ { 0 } ^ { \phantom { \dagger } } + \theta _ { \mathrm { c } } ^ { \phantom { \dagger } }
$$

![](images/e0cb35b756e1bb83eec9b894aec87464a8d251a5a92ad2f82b7085479843c5ff.jpg)  
Fig.4Schematic diagram of $\hat { u } _ { d h }$   
图5转子初始位置估计原理框图  
Fig.5Block diagram of initial rotor position estimation

# 4 仿真与实验结果

根据以上分析搭建了仿真模型，对本文所提出的新型初始位置估计方法进行仿真验证，同时采用OPAL-RT控制器和硬件平台对其进行了实验验证，仿真和实验所采用的SPMSM参数见下表。

表SPMSM基本参数Tab.Parameters ofSPMSM  

<html><body><table><tr><td>参数名称</td><td>数值</td><td>参数名称</td><td>数值</td></tr><tr><td>额定电压UN/V</td><td>300</td><td>每极磁通量Φ/Wb</td><td>0.1063</td></tr><tr><td>额定功率PN/W</td><td>400</td><td>转动惯量J/g·m</td><td>0.0402</td></tr><tr><td>额定转速nn/rpm</td><td>6000</td><td>每相电阻Rs/Ω</td><td>3.2</td></tr><tr><td>额定电流IN/A</td><td>2.1</td><td>直轴电感Ld/mH</td><td>8</td></tr><tr><td>极对数Pn</td><td>2</td><td>交轴电感Lq/mH</td><td>8</td></tr></table></body></html>

# 4.1仿真结果

图6为采用本文所提出的磁极方向判断法进行初始位置估计的仿真波形，设定 $t _ { 1 } = 0 \mathrm { s }$ 时进行初次初始位置估计，设定 $t _ { 2 } = 0 . 3 \mathrm { s }$ 时进行磁极方向判断。其中，图6a对应实际转子初始位置 $\theta = 1$ rad，当 $t$ $= 0 \mathrm { s }$ 时，估计位置 $\hat { \theta }$ 开始收敛到实际位置 $\theta$ ，当 $t =$ 0.3s时，判断 $k _ { \mathrm { I , I I I } }$ 的符号为负，无需对初次初始位置估计角度进行补偿；图6b对应实际转子初始位置$\theta = 3$ rad，当 $t = 0 \mathrm { s }$ 时，估计位置 $\hat { \theta }$ 开始收敛到与实际位置 $\theta$ 相差πrad 的位置，当 $t = 0 . 3 \mathrm { s }$ 时，判断 $k _ { \mathrm { I , I I I } }$ 的符号为正，对初次初始位置估计角度补偿πrad，补偿后估计位置 $\hat { \theta }$ 与实际位置 $\theta$ 一致，且 $k _ { \mathrm { I , I I I } }$ 的符号变为负。

![](images/3df06b917acbace2075af54f7e80b013962741a01245ac4869a2c8a6cd79ad33.jpg)  
图6初始位置估计的仿真波形

# 4.2实验结果

图7为采用本文所提出的磁极方向判断法进行初始位置估计的实验波形，设定 $t _ { \mathrm { 1 } } = 0 . 0 5 \mathrm { s }$ 时进行初次初始位置估计，设定 $t _ { 2 } = 0 . 1 5 \mathrm { s }$ 时进行磁极方向判断。其中，图7a对应实际转子初始位置 $\theta = \pi / 4$ rad,当 $t = 0 . 0 5 \mathrm { s }$ 时，估计位置 $\hat { \theta }$ 开始收敛到实际位置 $\theta$ ，当 $t = 0 . 1 5 \mathrm { s }$ 时，判断 $k _ { \mathrm { I , I I I } }$ 的符号为负，无需对初次初始位置估计角度进行补偿；图7b对应实际转子初始位置 $\theta = \pi \mathrm { r a d }$ ，当 $t = 0 . 0 5 \mathrm { s }$ 时，估计位置 $\hat { \theta }$ 开始收敛到与实际位置 $\theta$ 相差πrad的位置，当 $t = 0 . 1 5 \mathrm { s }$ 时，判断 $k _ { \mathrm { I , I I I } }$ 的符号为正，对初次初始位置估计角度补偿πrad，补偿后估计位置 $\hat { \theta }$ 与实际位置 $\theta$ 一致，且 $k _ { \mathrm { I , I I I } }$ 的符号变为负。

# 5 结束语

本文采用脉振高频电流注入法对SPMSM初始位置估计进行研究，提出一种分区间积分判断磁极方向的方法，该方法无需额外注入正、负电压脉冲，无需比较电流幅值，缩短了初始位置估计的时间，简化了估计过程，降低了电流检测精度的要求，避免了小惯量电机在注入正、负电压脉冲时可能导致的转子抖动问题，拓宽了应用范围，具有较高的意义。仿真和实验结果均很好地验证了该方法的正确性和可行性。

# 参考文献

![](images/de23b5aee63775217e9d4ff1aff7c14c751d13ab97d1e27e2454a7515e28d424.jpg)  
Fig.6Simulation waveforms of initial position estimation   
图7初始位置估计的实验波形  
Fig.7Experimental waveforms of initial position estimation

[1] Raca D,Garcia P, Reigosa D D,etal. Carrier-signal selection for sensorless control of PM synchronous machines at zero and very low speeds[J].IEEE Trans. Ind. Appl.,2010, 46(1): 167-178.   
[2] Raca D,Harke M C,Lorenz R D.Robust magnet polarity estimation for initialization of PM synchronous machines with near-zero saliency[J]. IEEE Trans.Ind.Appl.,2008,44(4):1199-1209.   
[3] Garcia P, Briz F, Degner M W, et al. Accuracy, bandwidth,and stability limits of carrier-signalinjection- based sensorless control methods[J]. IEEE Trans. Ind. Appl., 2007,43(4): 990-1000.   
[4] Degner M W,Lorenz R D.Using multiple saliencies for the estimation of flux,position,and velocity in AC machines[J].IEEE Trans.Ind.Appl.,1998, 34(5): 1097-1104.   
[5] Jansen PL,Lorenz R D.Transducer less position and velocity estimation in induction and salient AC machines[J].IEEE Trans.Ind.Appl.,1995,31(2): 240-247.   
[6] Li Y,Zhu Z Q,Howe D,et al. Improved rotor position estimation by signal injection in brushless AC motors,accounting for cross-coupling magnetic saturation[J]. IEEE Trans.Ind.Appl.,2009,45(5): 1843-1849.   
[7] Linke M, Kennel R,Holtz J. Sensorless position control of permanent magnet synchronous machines without limitation at zero speed[C]. Industrial Electronics Society 28th Annual Conference (IECON 02),2002,1: 674-679.   
[8] Jang JH, Sul S K,Ha JI,et al. Sensorless drive of surface-mounted permanent-magnet motor by high-frequency signal injection based on magnetic saliency[J].IEEE Trans.Ind.Appl.,2003,39(4): 1031-1039.   
[9] Corley MJ,Lorenz RD.Rotor position and velocity estimation for a salient-pole permanent magnet synchronous machine at standstill and high speed[J]. IEEE Trans.Ind.Appl., 1998,34(4): 784-789.   
[10] Ha JI, Sul S K.Physical understanding of high frequency injection method to sensorless drives of an induction machine[C]. Ind.Appl. Conf., IEEE,2000, 3:1802-1808.   
[11] L Ying,Z Bo,F Ying,et al. Sensorless control with two types of pulsating high frequency signal injection methods for SPMSM at low speed[C].2011 4th International Conference on Power Electronics Systems and Applications (PESA),IEEE,2011:1-5.   
[12] L Shuai,Z Bo,L Ying,et al.A novel method of initial rotor position estimation for surface mounted permanent magnet synchronous motor[C].2010 International Conference on Electrical and Control Engineering (ICECE),IEEE,2010:4924-4927.

# （上接第32页）

International Semiconductor Power ConferenceRecord,Lake Buena,1997:399-403.  
[5] Alexander D,Williams S.An optimal PWMalgorithm implementation in high performance 125$\operatorname { k V } \cdot$ A inverter[C].IEEE Applied Power ElectronicsConference and Exposition, San Diego,USA,1993:771-777.  
[6] KolarJ,ErtlH,ZachF.Influence of the modulationmethod on the conduction and switching losses ofa PWM converter system[J].IEEE Transactions onIndustry Application,1991,27(6):1063-1075.  
[7] AsiminoaeiL,Rodriguez P,Blaabjerg F.Applicationof discontinuous PWM modulation in active powerfilters[J].IEEE Trans.on Power Electronics,2008,37(4): 1692-1706.  
[8] 武强．二极管籍位型三电平逆变器 SVPWM及中点平衡电位研究[D]．阜新：辽宁工程技术大学，2010.  
[9] 刘凤君．多电平逆变技术及其应用[M]．北京：机械工业出版社，2007.  
[10] 童鸣庭．三相T型三电平非隔离并网逆变器的研究[D]．合肥：合肥工业大学，2013.  
[11] 张伦健，谭国俊，陈利萍．基于双调制波技术的三电平Z源逆变器中点电位平衡控制[J]．电力系统保护与控制，2013，41(7)：91-96.Zhang Lunjian,Tan Guojun,Chen Liping.Neutral-point potential balance control for three-levelZ-source inverters based on double modulation wavetechnique[J]. Power System Protection and Control,2013,41(7): 91-96.  
[12] 安少亮，孙向东，陈樱娟，等．一种新的不连续PWM统一化实现方法[J]．中国电机工程学报,2012，32(24):59-66.An Shaoliang,Sun Xiangdong,Chen Yingjuan,etal.A new generalized implementation method ofdiscontinuous PWM[J].Proceedings of the CSEE,2012,32(24): 59-66.