# 基于虚拟阻抗的变阻感比低压微电网功率控制策略研究

邢作霞芦彦东 董焕宝（沈阳工业大学电气工程学院沈阳110870）

![](images/cafeb202d1fe05bef5c5a907838190a7d656150e072b3327cee8f3f21ed6ee81.jpg)

邢作霞女 1976年生，博士，副教授，研究方向为风力发电系统控制与测试和智能电网与储能技术。

摘要：低压微电网中传统下垂控制存在耦合，且由于线路阻抗不匹配使逆变器难以精确控制输出功率，容易引起逆变器间环流。本文分析了逆变器输出功率特性，通过引入虚拟功率得出线路阻感比与下垂控制的耦合关系，提出了基于虚拟阻抗的功率解耦控制策略。策略通过增加虚拟阻抗控制坏，改变逆变器输出等效阻感比，实现功率控制的解耦，同时解决了逆变器在正常运行及负载变化时功率不能均分的问题。利用 Matlab/Simulink 搭建了低压微电网基本结构的仿真模型，并与传统下垂控制对比，验证了本策略的有效性。

关键词：低压微电网 虚拟阻感比 功率解耦 功率均分中图分类号：TM464

# Power Decoupling Control Strategy of Variable Impedance Ratio Based on Virtual Impedance for Microgrid

Xing Zuoxia Lu Yandong Dong Huanbao （Shenyang University of TechnologyShenyang110870 China )

![](images/529a966d8511d51865ef4c75d3f68affd96dcb1cae72c0d53787e82d235e58d9.jpg)

芦彦东男 1995年生，硕士研究生，研究方向为电力电子在微电网中的应用。

Abstract: In low-voltage microgrids,coupling of traditional droop control, and mismatched feeder impedances can lead the inverter to control the output power imprecise,could cause the circulation between inverters.This paper analyzed the output power characteristics of the inverter, and concluded the coupling relationship between the line resistance ratio and the droop control by introducing the virtual power. A power decoupling control strategy based on the virtual impedance is proposed. The virtual impedance control loop which is added to this control strategy, can not only changed the output impedance ratio of the inverter to realize the decoupling of the power control, but solved the problem that actual output power could not be equally divided during normal operation and load change.Using Matlab/Simulink platform to build a basic structure of low-voltage microgrid model,and comparison the effectiveness of this strategy is verified by comparison with traditional droop control.

Keywords: Low-voltage microgrid, virtual impedance ratio, power decoupling. power sharing

# 1 引言

微电网与传统电网供电方式不同，在图1所示的微电网结构中，分布式电源（DistributionGeneration，DG）通过逆变器向负荷供电，逆变器是分布式电源的核心[1-4]。当微电网与大电网断开时，网内负荷功率全部由DG单元承担，此时，如何均分各DG单元间的功率是微电网运行控制中的关键问题[5]。

![](images/2bf98683d518fa675d8c3d7bcc90f423551373e2151b99fb6b7f1f2caeacccc1.jpg)  
图1微电网基本结构

目前基于电压和频率的下垂控制是实现功率均分的有效办法[6-7]。下垂控制主要模拟传统电网中同步发电机的一次调压调频特性，通过对有功和无功的控制调节电压和频率[8]。但下垂控制中的耦合会降低功率控制精度，引发逆变器间环流或逆变器过电流问题[9-10]。文献[11]提出了分布式控制方式,统一协调控制各DG单元，且优于传统DG集中控制方式，但需要所有微电网内全部DG单元信息，对通信与信息处理能力要求较高。文献[12]提出了对给定与实际功率差进行积分环节提高功率均分精度的方法，但同样需要进行互联通信且没考虑耦合问题。文献[13]提出了对每个采样周期都进行重复下垂控制实现功率均分的策略。针对下垂控制的耦合问题，文献[14-15]引入了虚拟阻抗，但没有考虑对虚拟阻抗导致的电压损失进行补偿，当系统处于孤岛运行模式时，容易引发电压失稳。

本文提出了基于虚拟阻抗的变阻感比低压微电网功率控制策略，策略从逆变器输出功率特性出发，分析线路阻感比与功率耦合的关系，在传统下垂控制中引入虚拟阻抗环，统一改变逆变器输出阻感比，实现解耦和功率均分，且保留了传统下垂控制无需互联通信的优点。此外，经过分析，在虚拟阻抗参数设计中增加电压补偿环节可以减少虚拟阻抗和负荷变化对母线电压的影响。

# 2微电网中逆变器输出功率特性分析

图2为逆变器功率传输等效模型。假设公共耦合点（PointofCommonCoupling，PCC）的电压为$E \angle 0$ ，线路阻抗为 $Z \angle \theta$ ，DG单元用简化的交流电源 $V \angle \delta$ 表示， $\delta$ 为 $E$ 与 $V$ 的相位差。

![](images/47155f9e27287517087bc62a3463b83e27ad4351c99949ed5484c05a0d5fef90.jpg)  
Fig.1Microgrid system structure   
图2功率传输等效模型  
Fig.2Equivalent model of power transmission

由DG向PCC点输送的视在功率表示为

$$
S = V I ^ { ' } = V \angle \delta \left( \frac { V \angle \delta - E \angle 0 } { Z \angle \theta } \right) ^ { * } = \frac { V ^ { 2 } } { Z } \mathrm { e } ^ { \mathrm { i } \theta } - \frac { E V } { Z } \mathrm { e } ^ { \mathrm { j } ( \theta + \delta ) }
$$

式中，“\*”号代表共轭复数。

将欧拉公式（ $\displaystyle { ' } \mathrm { e } ^ { \mathrm { i } \theta } = \cos \theta + \mathrm { j } \sin \theta )$ 代入式（1) 中可得其线路阻抗的传输的有功功率 $P$ 和无功功率 Q的功率关系为[9]

$$
\left\{ \begin{array} { l } { { \displaystyle P = \frac { V ^ { 2 } } { Z } \mathrm { c o s } \theta { - } \frac { E V } { Z } \mathrm { c o s } \left( \theta { + } \delta \right) } } \\ { { \displaystyle Q { = } \frac { V ^ { 2 } } { Z } \mathrm { s i n } \theta { - } \frac { E V } { Z } \mathrm { s i n } \left( \theta { + } \delta \right) } } \end{array} \right.
$$

从式（2）中可以看出，有功与无功的控制与线路阻抗角存在耦合关系，影响功率控制的精度。当对应的低压微电网为阻性线路时，阻性下垂控制方程可表示为[5]

$$
\begin{array} { l } { \left\{ \boldsymbol { f } - \boldsymbol { f } ^ { * } = - \boldsymbol { k } _ { \mathrm { m } } ( \boldsymbol { Q } - \boldsymbol { Q } ^ { * } ) \right. } \\ { \left. \boldsymbol { V } - \boldsymbol { V } ^ { * } = - \boldsymbol { k } _ { \mathrm { n } } ( \boldsymbol { P } - \boldsymbol { P } ^ { * } ) \right. } \end{array}
$$

式中， $f ^ { * }$ 为微电网系统额定频率； $\boldsymbol { P } ^ { * }$ 为DG 在微电网系统频率为额定频率 $\boldsymbol { f } ^ { * }$ 时输出的有功功率； $\boldsymbol { V } ^ { * }$ 为DG逆变器的额定电压； $\boldsymbol { Q } ^ { * }$ 为在额定电压为 $\boldsymbol { V } ^ { * }$ 时DG 输出的无功功率； $k _ { \mathrm { m } }$ ， $k _ { \mathrm { n } }$ 分别为无功功率和有功功率的下垂系数。阻性下垂控制以线路阻抗特性$X \ll R$ 为解耦和使用条件，当满足条件时选择阻性下垂控制方程可合理分配功率。

虚拟阻抗法是一种常用的提高功率分配精度的方法[16-17]。通过引入虚拟阻抗，降低线路阻抗对耦合程度的影响，在保证微电网稳定性的同时，提高微电网逆变器的功率分配精度。

# 3基于虚拟阻抗的改进下垂控制策略

# 3.1下垂控制的耦合分析

为了具体分析阻性下垂中的耦合关系，引入线性正交旋转矩阵 $T$ ，将逆变器输出的有功 $P$ 与无功$\boldsymbol { \mathcal { Q } }$ 转化为虚拟有功 $P ^ { \prime }$ 和虚拟无功 $\boldsymbol { \mathcal { Q } ^ { \prime } }$ ，即

$$
{ \binom { P ^ { \prime } } { Q ^ { \prime } } } = \pmb { T } { \binom { P } { Q } }
$$

其中，线性正交矩阵 $T$ 为

$$
T = \left( \begin{array} { c c } { { \sin \theta } } & { { - \cos \theta } } \\ { { \cos \theta } } & { { \sin \theta } } \end{array} \right) = \left( \begin{array} { c c } { { X } } & { { - { \underline { { R } } } } } \\ { { Z } } & { { - { \underline { { R } } } } } \\ { { { \underline { { R } } } } } & { { { \underline { { X } } } } } \\ { { Z } } & { { { \overline { { Z } } } } } \end{array} \right)
$$

可得

$$
\left\{ \begin{array} { l l } { \displaystyle { P ^ { \prime } = \frac { E V } { Z } \sin \delta } } \\ { \displaystyle { Q ^ { \prime } = \frac { V ( V - E \cos \delta ) } { Z } } } \end{array} \right.
$$

基于式（4)、式（5）和式（6)，可得

$$
\left\{ \begin{array} { l } { { \displaystyle { \frac { E V } { Z } } \sin \delta = \frac { X } { Z } P - \frac { R } { Z } Q } } \\ { { \displaystyle { \frac { V ^ { 2 } - E V } { Z } } \cos \delta = \frac { R } { Z } P + \frac { X } { Z } Q } } \end{array} \right.
$$

由于相位差 $\delta$ 很小，可令sin $\delta \approx \delta$ ，cos $\delta \approx 1$ ，得出式（8）中阻感比与下垂控制的关系

$$
\left\{ \begin{array} { l } { \displaystyle \delta \approx \frac { X } { E V } \Biggl ( P - \frac { R } { X } { \mathcal Q } \Biggr ) } \\ { \displaystyle V - E \approx \frac { X } { V } \Biggl ( \frac { R } { X } P + { \mathcal Q } \Biggr ) } \end{array} \right.
$$

在低压微电网线路中，感抗相对阻抗不能忽略时，可得下垂控制器输出电压幅值 $V ^ { \prime }$ 和频率 $f ^ { \prime }$ 均与有功功率 $P$ 和无功功率 $\boldsymbol { \mathcal { Q } }$ 相关。可得到线路阻感比与功率控制的耦合关系为

$$
\begin{array} { l } { \displaystyle { \int f ^ { \prime } = f ^ { * } - k _ { \mathrm { m } } \left( P - P ^ { * } \right) + r k _ { \mathrm { m } } \left( Q - Q ^ { * } \right) } } \\ { \displaystyle { \left[ V ^ { \prime } = V ^ { * } - r k _ { \mathrm { n } } \left( P - P ^ { * } \right) - k _ { \mathrm { n } } \left( Q - Q ^ { * } \right) \right. } } \end{array}
$$

式中， $\boldsymbol { r }$ 为线路阻感比值， $r { = } R / X$ t $k _ { \mathrm { m } }$ ， $k _ { \mathrm { n } }$ 为下垂系数。

# 3.2基于虚拟阻抗的功率解耦与均分控制

为实现功率精确解耦，本方案在逆变器的电压外环加入虚拟阻抗，使逆变器输出阻感比值 $R / X$ 变大，消除线路感抗以及阻抗不匹配的影响，提高有功及无功功率解耦精度，实现功率均分。此外，虚拟电阻增加了系统的阻尼可抑制系统振荡，还可实现对系统线路阻抗的间接控制，引入虚拟阻抗后，电压外环参考电压表示为

$$
\nu _ { \mathrm { v i r } } = \nu _ { \mathrm { o } } ^ { * } - Z _ { \mathrm { v i r } } i _ { \mathrm { o a b c } }
$$

式中， $Z _ { \mathrm { v i r } } = R _ { \mathrm { v i r } } + \mathrm { j } \omega L _ { \mathrm { v i r } }$ ， $\nu _ { \mathrm { o } } ^ { * }$ 为经下垂方程得到的输出电压参考； $\nu _ { \mathrm { v i r } }$ 为与虚拟阻抗环合成后的电压闭环的输入参考值； $Z _ { \mathrm { v i r } }$ 为虚拟阻抗； $i _ { \mathrm { o a b c } }$ 为逆变器输出电流。

在dq旋转坐标系下虚拟阻抗控制环表示为

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { \nu _ { \mathrm { v i r d } } = \nu _ { \mathrm { o d } } ^ { * } - R _ { \mathrm { v i r } } i _ { \mathrm { o d } } + \omega L _ { \mathrm { v i r } } i _ { \mathrm { o q } } } \\ { \nu _ { \mathrm { v i r q } } = \nu _ { \mathrm { o q } } ^ { * } - R _ { \mathrm { v i r } } i _ { \mathrm { o q } } - \omega L _ { \mathrm { v i r } } i _ { \mathrm { o d } } } \end{array} \right. } \end{array}
$$

式中， $R _ { \mathrm { v i r } } .$ ， $L _ { \mathrm { v i r } }$ 分别为虚拟电阻和虚拟电感； $\nu _ { \mathrm { v i r d } }$ 和$\nu _ { \mathrm { v i r q } }$ 分别为电压外环在dq旋转坐标系的电压参考；$\omega$ 为dq旋转坐标系的旋转角频率。dq旋转坐标下实现虚拟阻抗的控制环如图3所示。

![](images/6b434b62159279f2f8f58ac1b39d0c278e5d2fb1a57c79016ec24ce00a20aebe.jpg)  
图3虚拟阻抗控制环  
Fig.3Virtual impedance control loop

图3中， $\nu _ { \mathrm { o d } }$ ， $\nu _ { \mathrm { o q } }$ 分别为输出电压反馈值的dq轴分量， $i _ { 1 \mathrm { d } } ^ { * } .$ ： $i _ { \mathrm { l q } } ^ { * }$ 为电流环的dq旋转坐标系参考值分量， $k _ { \mathrm { p v } }$ 、 $k _ { \mathrm { i v } }$ 分别为电压环的比例和积分系数。下垂控制中电压环与电流环的设计可参考文献[13]。

在低压微电网中，引入虚拟电阻 $R _ { \mathrm { v i r } }$ 使系统阻抗 $R \gg X$ ，因此，可忽略线路感抗 $X$ 对系统的影响，使系统输出特性呈阻性，式（9）中， $k _ { \mathrm { m } } ( P \mathrm { ~ - ~ }$ $\boldsymbol { P } ^ { * } )$ 相对于 $r k _ { \mathrm { m } } ( Q - { \mathcal { Q } } ^ { * } )$ 可忽略不计，同理 $k _ { \mathrm { n } } ( Q - Q ^ { * } )$ 相对于 $r k _ { \mathrm { n } } ( P - P ^ { * } )$ 可忽略不计，实现了逆变器输出有功 $P$ 与无功 $\varrho$ 的解耦，统一改变等效阻感比，提高了逆变器输出功率的精确性。

# 3.3虚拟阻抗的参数设计

引入虚拟阻抗后，逆变器的等效框图如图4所示。

![](images/975e4f4a4f23fd3a93dfa9a4164e8f9dbb24309ce9dfbd8e6c102f6dbbedd5aa.jpg)  
Fig.4Equivalent block diagram of inverter

图4中， $\nu _ { \mathrm { o r e f } } ( s )$ 为下垂控制器输出的电压,$G _ { \mathrm { i } } ( s )$ 为电流环传递函数， $G _ { \mathrm { u } } ( s )$ 为电压环传递函数，$u _ { \mathrm { o } } ( s )$ 为逆变器输出电压， $L$ 、 $C$ 分别为主电路的滤波电感和滤波电容， $k _ { \mathrm { P W M } }$ 为逆变器的基波脉宽调制比例系数， $i _ { \mathrm { o } } ( s )$ 为逆变器输出电流。整理逆变器输出电压可以等效为

$$
u _ { \mathrm { o } } \left( s \right) = G ( s ) \nu _ { \mathrm { v i r } } - Z _ { \mathrm { v i r } } \left( s \right) i _ { \mathrm { o } } \left( s \right)
$$

式中， $Z _ { \mathrm { i n v } } ( s )$ 为逆变器等效输出阻抗。

在逆变器控制系统中通过加入虚拟阻抗控制环后，改变了线路阻抗中阻性分量与感性分量的比值，但会造成虚拟阻抗上的电压降，进而对系统电能质量产生不利的影响。可以得出降落在逆变器、线路和虚拟阻抗上的系统电压偏差为

$$
\Delta V = [ Z _ { \mathrm { i n v } } \left( s \right) + Z _ { \mathrm { l i n e } } ] i _ { \circ } \left( s \right)
$$

进而可得重新赋值参考电压为

$$
V _ { \mathrm { r e f } } = V _ { \mathrm { r e f 0 } } + \Delta V
$$

经上述分析造成系统电压降落的原因，为提高系统的电能质量，虚拟阻抗设置为

$$
Z _ { \mathrm { v i r } }  ( s ) = \frac { \displaystyle \frac { V _ { \mathrm { r e f } } - E } { i _ { 0 } ( s ) } - [ Z _ { 0 } ( s ) + Z _ { \mathrm { l i n e } } ] } { G ( s ) }
$$

在式（14）和式（15）中， $V _ { \mathrm { r e f 0 } }$ 为逆变器初始给定电压参考； $V _ { \mathrm { r e f } }$ 为逆变器经补偿后的给定电压参考； $E$ 为负荷侧母线电压幅值； $i _ { 0 } ( s )$ 为负荷侧母线电流。在虚拟阻抗控制环中，虚拟阻抗参数可以根据式（15）进行计算。

# 4逆变器整体控制设计

基于虚拟阻抗的逆变器控制框图如图5所示。首先根据线路电流 $i _ { \mathrm { o a b c } }$ 和电压 $\nu _ { \mathrm { o a b c } }$ 经过dq坐标变换输出的电流 $i _ { \mathrm { o d q } }$ 和电压 $\nu _ { \mathrm { o d q } }$ 计算瞬时有功 $P$ 和无功 $\varrho$ ，根据有功功率与电压、无功功率与频率的下垂特性输出参考电压幅值 $V ^ { \prime }$ 和频率 $f ^ { \prime }$ ，并经过电压合成的 $\nu _ { \mathrm { o d } } ^ { * }$ 、 $\nu _ { \mathrm { o q } } ^ { * }$ ，其与虚拟阻抗控制环在dq 轴的瞬时电压分量合成后的 $\nu _ { \mathrm { v i r d } }$ ， $\nu _ { \mathrm { v i r q } }$ 作为电压外环电压参考，经电压电流双闭环控制输出驱动信号，完成逆变器输出。

![](images/1a9db841b5ede9fb53c3dd73a2e38cc768060725b11157b28e674109cdea591d.jpg)  
图4逆变器等效框图  
图5基于虚拟阻抗的逆变器控制框图  
Fig.5Block diagram of inverter control based on virtual impedance

# 5 仿真结果及分析

本文在低压微电网系统中对改进功率解耦控制策略进行仿真验证。仿真中采用两台同等容量DG并联运行，搭建了孤网下的微电网模型，分别对传统下垂控制和基于虚拟阻抗功率解耦的下垂控制进行对比。仿真时间设置为 $2 . 5 \mathrm { s }$ 。仿真波形分别如图6和图7所示，仿真参数设置见下表。

表仿真系统参数Tab. Simulation system parameters  

<html><body><table><tr><td>系统名称</td><td>参数数值</td></tr><tr><td>380V线路</td><td>R=1.284Ω，R=0.812Ω, L=j0.1930Ω，L=j0.0981Ω Line1=0.2km，Line2=0.192km</td></tr><tr><td>负荷</td><td>loadl=30kW、10kvar load2=10kW、10kvar load3=10kW、10kvar</td></tr></table></body></html>

低压系统中线路阻抗主要呈现阻性，通常采用 $P / / F$ 下垂控制。图6和图7针对传统下垂控制和基于虚拟阻抗解耦的下垂控制的输出功率进行对比。仿真中，在 $0 \sim 0 . 8 \mathrm { s }$ 之间均为Load1，在0.8s和1.6s中分别加入Load2和Load3。可以看到，采用传统 $P / / F$ 下垂控制时，DG1和DG2两逆变器在未加虚拟阻抗控制环时，其有功功率偏差较大，在Load3中加入后更为明显；图6b显示逆变器输出无功功率可以实现均分。

![](images/8df61db3c8d8957f1b00908ff9d5f38202def3b9b8288db44b3316adf64fa613.jpg)

（b）传统下垂控制输出无功功率

![](images/e9b702d1d1853ef49bf28dbf7f7bfc06c4d3fdcb2846ed9ed691bed696aafc09.jpg)  
图6传统下垂控制

![](images/835c38ff349bf27a1a0b86c245e0b66fecc703c68d2a3656a425ca6af5ecc859.jpg)  
Fig.6Traditional droop control   
图7基于虚拟阻抗的改进下垂控制  
Fig.7Improved droop control based on virtual impedance

由图7可知，并联运行的DG1和DG2两逆变器均引入虚拟阻抗控制环后，其总体输出功率符合预定要求。在 $0 . 8 \sim 1 . 6 \mathrm { s }$ 期间，加入Load2后总负荷为 $4 0 \mathrm { k W }$ 、20kvar，DG1和DG2输出功率均为

20kW、10kvar。在1.6s加入Load3，DG1及DG2输出功率均为 $2 5 \mathrm { k W }$ 、15kvar。在负荷变化时，频率满足微电网运行要求。结果表明，逆变器输出的有功及无功功率均实现了精确均分。

在图6c中，在 $t = 0 . 8 \mathrm { s }$ 时加入Load2，此时系统母线电压从 $3 2 5 \mathrm { V }$ 下降到 $3 1 2 \mathrm { V }$ ；在 $t = 1 . 6 \mathrm { s }$ 加入Load3之后，电压幅值下降到 $3 0 3 \mathrm { V }$ 。在图7c中，在 $t = 0 . 8 \mathrm { s }$ 时加入Load2，此时系统母线电压从325V下降到316V；在 $t = 1 . 6 \mathrm { s }$ 加入Load3之后，由于负荷突变电压下降，之后电压幅值恢复到311V，补偿了负荷增加和引入虚拟阻抗后导致的母线电压的降落，提高了低压微电网运行的稳定性。

# 6 结论

针对传统阻性下垂中耦合及逆变器不能精确控制输出功率的问题，提出了基于虚拟阻抗的改进解耦控制策略。本文在逆变器输出功率特性基础上，引入虚拟功率，得出线路阻感比与阻性下垂控制的耦合关系，当感性分量相对阻性分量不可忽略时，产生的耦合对功率控制的精度影响较大。引入虚拟阻抗的控制环后，使逆变器输出等效阻感比 $( R / X )$ $\gg 1$ ，最终实现功率的精确解耦和逆变器间功率均分，适用于等容量并联逆变器运行的低压微电网系统。此外，虚拟阻抗参数设计中的电压补偿环节降低了负荷增加后母线电压的压降，可以提高微电网运行的稳定性。

# 参考文献

[1] 马艺玮，杨苹，王月武，等．微电网典型特征及关 键技术[J]．电力系统自动化，2015，39(8)：168- 175. Ma Yiwei, Yang Ping,Wang Yuewu,et al. Typical characteristics and key technologies of microgrid[J]. Automation of Electric Power Systems,2015,39(8): 168-175.   
[2] 陈萌，肖湘宁．基于分布式内模设计的微电网协调 二次控制策略[J]．电工技术学报，2017，32(10)： 145-153. Chen Meng,Xiao Xiangning.Distributed control strategy for voltage unbalance compensation in islanded microgrid[J]. Transactions of China Electrotechnical Society, 2017,32(10):145-153.   
[3] 王舒娅，苏建徽，杨向真，等．微电网小扰动稳 定性研究综述[J]．电气工程学报，2016，11(7)： 39-45. Wang Shuya, Su Jianhui, Yang Xiangzheng,et al. A review on the small signal stability of microgrid[J] Journal of Electrical Engineering,2016,11(7): 39-45.   
[4] 李大兴，邱文祥，夏革非，等．分布式电源及 微电网接入控制系统研究[J]．电气应用，2016, 35(22): 26-30.   
[5] 郭倩，林燎源，武宏彦，等．考虑自适应虚拟阻 抗的微电网分布式功率控制策略[J]．电力系统自 动化，2016，40(19)：23-29. Guo Qian, Lin Liaoyuan, Wu Hongyan, et al. Distributed power control strategy for microgrids considering adaptive virtual impedance[J]. Automation of Electric Power Systems,2016, 40(19): 23-29.   
[6] 阚志忠，张纯江，薛海芬，等．微网中三相逆变 器无互连线并联新型下垂控制策略[J]．中国电机 工程学报，2011，31(33)：68-74. Kan Zhizhong,Zhang Chunjiang,Xue Haifen,et al.A novel droop control of three-phase inverters in wireless parallel operation in microgird[J]. Proceedings of the CSEE,2011,31(33): 68-74.   
[7] 金鹏，艾欣，王永刚．采用势函数法的微电网无功 控制策略[J]．中国电机工程学报，2012，32(25)： 44-51. Jin Peng, Ai Xin, Wang Yonggang. Reactive power control strategy of microgird using potential function method[J]. Proceedings of the CSEE,2012,32(25): 44-51.   
[8] 朱一昕，卓放，王丰，等．用于微电网无功均衡 控制的虚拟阻抗优化方法[J]．中国电机工程学报, 2016，36(17): 4552-4564. Zhu Yixin, Zhuo Fang,Wang Feng, et al. Virtual impedance optimization method for microgrid reactive power sharing control[J]. Proceedings of the CSEE,2016,36(17): 4552-4564.   
[9] 程军照，王文玺，陈江波．采用功率坐标变换的 微网并联逆变器控制方法[J]．电力系统自动化, 2017，41(1): 117-121. Cheng Junzhao, Wang Wenxi, Chen Jiangbo. Control method for parallel inverters in microgrid based on power coordinate transformation[J]. Automation of Electric Power Systems,2017,41(1): 117-121.   
[10]陈晓祺，贾宏杰，陈硕翼，等．基于线路阻抗辨 识的微电网无功均分改进下垂控制策略[J]．高电 压技术，2017，43(4)：1271-1279. Chen Xiaoqi,Jia Hongjie,Chen Shuoyi,et al. Improved droop control strategy based on line impedance identification for reactive power sharing in microgrid[J].High Voltage Engineering,2017, 43(4): 1271-1279.   
[11] Shafiee Q,Guerrero JM,Vasquez JC.Distributed secondary control for islanded microgrids—a novel approach[J]. IEEE Transactions on Power Electronics,2014,29(2):1018-1031.   
[12] Zhu Yixin,Zhuo Fang,Shi Hongtao.Accurate power sharing strategy for complex microgrid based on droop control method[C].IEEE ECCE Asia Downunder, 2013:344-350.   
[13] 孙孝峰，郝彦丛，赵巍，等．孤岛微电网无通信功 率均分和电压恢复研究[J]．电工技术学报，2016, 31(1): 55-61. Sun Xiaofeng,Hao Yancong,Zhao Wei,et al. Research of power sharing and voltage restoration without communication for islanded microgrid[J]. Transactions of China Electrotechnical Society, 2016,31(1): 55-61.   
[14] Cao Xin, Zhong Qingchang,Ming Wenlong.Ripple eliminator to smooth DC-bus voltage and reduce the total capacitance required[J]. IEEE Transactions on Industrial Electronics,2015,62(4): 2224-2235.   
[15] Guerrero JM,Matas J,Vicuna L G,et al. Decentralized control for parallel operation of distributed generation inverters using resistive output impedance[J].IEEE Transactions on Industrial Electronics,2007,54(2):994-1004.   
[16] He J,Li YW,Guerrero JM,et al. An islanding microgrid power sharing approach using enhanced virtual impedance control scheme[J].IEEE Transactions on Power Electronics,2013,28(11): 5275-5282.   
[17] Matas J,Castilla M,de Vicuna L G,et al.Virtual impedance loop for droop-controlled single-phase parallel inverters using a second-order generalintegrator scheme[J].IEEE on Power Electronics, 2010,25(12):2993-3002.