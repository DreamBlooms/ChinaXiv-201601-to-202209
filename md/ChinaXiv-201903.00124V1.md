# 空间电源DC-DC变换器的研究

宋　丹　吉瑞萍（西安微电子技术研究所西安710000）

宋丹女1990年生，硕士，研究方向为数字电源技术。

摘要：非隔离型Weinberg变换器（NIWC）具有高功率密度、易于并联等优点，适合作为航天电源系统中的蓄电池放电调节器（BDR）和顺序开关分流最大功率调节器（S3MPR）或顺序开关串联分流最大功率调节器（S4MPR）的后级变换器。本文对该变换器的工作原理进行了分析，推导出其小信号模型，在保证输出电压电流纹波的前提下，设计了主电路参数。应用Matlab对系统传递函数进行分析后，设计了有源超前一滞后补偿网络，以保证系统的快速性和稳定性。仿真和实验结果验证了系统设计的正确性。

关键词：空间电源 Weinberg变换器 传递函数补偿网络中图分类号：TM46

# Study of DC-DC Converter for Space Power System

Song DanJi Ruiping (Xi'an Microelectronic Technology InstituteXi'an710000 China ）

![](images/8eee28bfb465e5a1ea6b483031b6fd044b8e83e720178bd27580c5813220f7df.jpg)  
收稿日期：2015-07-29

![](images/46420ba82dd0ad3152d7262757535461add793303eb8fca6bdcc01e5de7e8749.jpg)

吉瑞萍 女 1991年生，博士，研究方向为航空电气系统。

Abstract: With high power density and easy paralleling, the non-isolated Weinberg converter (NIWC) is suitable as battery discharge regulator (BDR) and DC-DC converter after sequential switch shunt maximum power regulator (S3MPR) or sequential switch series shunt maximum power regulator (S4MPR) in space power system. The working principle of the converter is analyzed, its smal-signal model is deduced. In the premise of ensuring output voltage and current ripples, the main circuit parameters are designed. After the analysis of system transfer function with Matlab,in order to ensure rapidity and stability of the system, the active lead-lag compensation network is designed. The simulation and experimental results verify the correctness of system design.

Keywords: Space power system,Weinberg converter, transfer function, compensation network

# 1 引言

卫星电源系统是产生、存储、变换和分配电能的系统，是卫星的重要组成单元，目前 $90 \%$ 以上的航天器采用了太阳能电池阵/蓄电池(SA/B）电源系统。电源控制器（PowerControlUnit,PCU）用来控制太阳能电池阵产生的能量的分配，以及蓄电池的充放电，可使航天器在整个在轨运行期间将功率母线电压稳定在规定范围内。目前我国研制的PCU母线电压有 $2 8 \mathrm { V }$ 、42V和100V三种等级[1]。

当卫星进入阴影区不能从太阳能电池阵得到功率或在光照区太阳能电池阵提供的功率不足时，为保证母线电压稳定，蓄电池向母线提供电能，在此过程中蓄电池放电调节器（BatteryChargeRegulator，BDR）起主要作用。需要研究一款高效率、兼顾动态和稳态性能的DC-DC 模块作为BDR,使得蓄电池经BDR放电时，仍能维持较好的母线性能[2]。

由于太阳能电池的输出特性具有较强的非线性特征，将最大功率点跟踪(MaximumPowerPointTracking，MPPT）技术与顺序开关分流调节拓扑(SequentialSwitchShuntRegulator，S3R）或顺序开关串联分流拓扑（Sequential Switch Series Shunt Regulator,S4R）相结合形成的S3MPR和S4MPR[3]可以实时调整太阳能电池阵的工作点，使之始终工作在最大功率点附近，有利于最大限度利用太阳能电池阵的输出功率。由于母线电压始终保持在太阳能电池阵的最大功率点电压上，因此该电压将随着太阳能电池阵的温度和光照情况而变化。为了获得稳定的直流母线，在S3MPR或S4MPR调节器后面需串联一级高效率、高功率密度的DC-DC 变换器[4]。

选择BDR拓扑和S3MPR或S4MPR后级串联的DC-DC变换器拓扑，主要考虑效率、复杂性、稳定性和升压特性等因素，非隔离型Weinberg变换器（Non-isolated Weinberg Converter，NIWC）能很好地满足这些需求。目前在欧洲和美国，NIWC已经在卫星中成功应用，如Olympus、Inmarsat11、Eurostar 3000、SpaceBus4000 和 BepiColombo 等,国内目前还处于研究和试验阶段[4]。本文分析了NIWC的工作原理，建立其小信号数学模型并对系统稳定性进行分析，进而提出主电路参数和控制环路的设计方法，并进行仿真及实验验证。

# 2 NIWC的原理分析

# 2.1工作状态分析

图1为NIWC的电路拓扑。忽略漏电感和磁化电感的影响，非隔离Weinberg变换器理想工作时有两种工作状态：

![](images/ea34720ecc670cd310c167d78c3d6727fc6545e5b1feab67c31a1886b8e32d9f.jpg)  
图1非隔离Weinberg变换器Fig.1Non-isolated Weinberg converter

（1） $\textstyle \mathbf { Q } _ { 1 }$ 或 $\mathbf { Q } _ { 2 }$ 导通，使得 $\mathrm { V D } _ { 2 }$ 或 $\mathrm { V D } _ { 1 }$ 导通，VD关断。

（2） $\textstyle \mathrm { \mathrm { Q } } _ { 1 }$ 和 $\mathbf { Q } _ { 2 }$ 均关断，VD 导通。

通过产生的PWM波控制 $\mathbf { Q } _ { 1 }$ 和 $\mathbf { Q } _ { 2 }$ 的导通与关断，从而实现输出电压的控制。 $\mathbf { Q } _ { 1 }$ 和 $\mathbf { Q } _ { 2 }$ 交替导通,一个开关周期内有两次MOSFET开通关断，即等效PWM频率是实际频率的两倍。因此在不增加开关损耗的情况下，增加了变换器的带宽，同时有效地减少了磁心元件和滤波器元件的尺寸，提高了功率密度。

# 2.2稳态直流增益

两种工作状态时，输出电流都受到耦合电感或变压器的限制，因此输出电流连续[5]，由此可得Weinberg电路的电压增益为

$$
V _ { \mathrm { O U T } } = ( 1 + D ) V _ { \mathrm { I N } }
$$

式中， $D = t _ { \mathrm { O N } } / T _ { \mathrm { S W I T C H I N G } }$ ， $T _ { \mathrm { S W I T C H I N G } }$ 是实际开关周期的一半。

NIWC的输出电流连续且纹波很小的特点使得该拓扑便于电流型控制，且易于进行多模块并联以扩展功率。

# 2.3小信号模型

根据状态空间平均法可得NIWC的小信号模型等效电路，如图2所示[]。

由图2可得NIWC电压控制方式的传递函数为

![](images/6819c3f84a2e76f425d9fe4834163265838de43ce2fd9023cdbd914ee99b1885.jpg)  
图2NIWC小信号模型等效电路

$$
G _ { \mathrm { v d } } \left( s \right) = \frac { \hat { \nu } _ { \mathrm { o u t } } \left( s \right) } { \hat { \mathrm { d } } \left( s \right) } = \frac { V _ { \mathrm { i n } } } { 4 L C s ^ { 2 } + \displaystyle \frac { 4 L s } R + 1 }
$$

从式（2）的传递函数可知，NIWC的理想化模型为二阶，便于控制系统设计。

# 3 NIWC系统设计

# 3.1主电路参数设计

本文设计的DC-DC变换器的参数如下：母线电压 $4 2 \mathrm { V }$ ；输入电压 $2 5 \sim 3 5 \mathrm { V }$ ；输出功率 $3 0 0 \mathrm { W }$ ；开关频率 $1 0 0 \mathrm { k H z }$ ；输出电流纹波 $10 \%$ ；母线电压纹波$1 \%$ 。根据以上指标，对主电路参数进行优化设计。

（1）耦合电感设计。输出电流纹波由耦合电感的大小决定，即

$$
\Delta i _ { \mathrm { o u t } } = \frac { V _ { \mathrm { o u t } } } { 4 L _ { \mathrm { o n } } f _ { \mathrm { s } } } \Bigg ( \frac { 2 D } { 1 + D } - D \Bigg )
$$

其中， $f _ { \mathrm { s } }$ 为等效开关频率。

由式（3）可知，当 $D = 0 . 4 1 4$ 时输出电流扰动最大。由于本文占空比 $D$ 的范围为 $0 . 2 \sim 0 . 6 8$ ，因此电感值 $L$ 需使 $D = 0 . 4 1 4$ 时的输出电流纹波满足$10 \%$ 的要求。经过计算可得 $L _ { \mathrm { o n } } = 1 2 . 6 \mu \mathrm { H }$ ，留有一定裕度，取耦合电感 $L _ { \mathrm { o n } } = 2 0 \mu \mathrm { H }$ 。

(2）滤波电容设计。为保证Weinberg电路的输出电压纹波大小符合技术指标，需要在输出端加上输出滤波电容。输出滤波电容的设计准则为

$$
C = \frac { \Delta i _ { \mathrm { o } } } { 8 \Delta V _ { \mathrm { o } } f }
$$

经计算可得 $C = 1 . 0 6 \mu \mathrm { F }$ ，留有一定裕度，取输出滤波电容 $C = 1 0 \mu \mathrm { F }$ 。

# 3.2补偿网络设计

要使输出电压在输入电压波动和负载变化情况下经过暂态调节后保持稳定，需要对系统进行闭坏设计，最简单的方法是电压单环补偿[]。

图3为NIWC控制系统框图。其中 $G _ { \mathrm { v d } } ( s )$ 为隔离Weinberg变换器 $\hat { d } ( s )$ 至输出 $\hat { \nu } _ { { } _ { \mathrm { o } } } ( s )$ 的传递函数;$G _ { \mathrm { m } } ( s )$ 为PWM脉宽调制器的传递函数； $H ( s )$ 表示反馈分压网络的传递函数， $G _ { \mathrm { c } } ( s )$ 为补偿网络的传递函数。结合图3，可以得到原始回路增益函数为

![](images/483a7e7cf939fca3f043ace717e9282e2c0ee360d2871b6b2217ca7110104511.jpg)  
Fig.2The small-signal model ofNIWC  
图3NIWC控制系统框图

$$
G _ { \mathrm { o } } = G _ { \mathrm { m } } G _ { \mathrm { v d } } H = \frac { V _ { \mathrm { i n } } } { 4 L C s ^ { 2 } + 4 L s / R + 1 } \frac { 1 } { V _ { \mathrm { m } } } \frac { 1 } { K }
$$

式中， $V _ { \mathrm { m } }$ 为PWM调制器中锯齿波的幅值； $K$ 为反馈分压系数，这里分别取3V和8.3。代入相应参数，可以画出原始回路增益函数 $G _ { \mathfrak { o } } ( s )$ 的Bode图，如图4所示。

![](images/6aba1b354933bd05dc2b1f27bb110ab7f2e8146c31dec60e97f01147c547a537.jpg)  
Fig.3The control system block diagram of NIWC   
图4原始回路增益函数 $G _ { \mathfrak { o } } ( s )$ 的Bode图  
Fig.4The Bode graphs of original loop gain function $G _ { \mathfrak { o } } ( s )$

由图4可知，系统在低频段分贝数较低也不具有 $- 2 0 \mathrm { d B / d e c }$ 下降斜率，中频段不是以 $- 2 0 \mathrm { d B / d e c }$ 穿过零分贝线。另外，通常选择相位裕度在 $4 5 ^ { \circ }$ 左右，幅值裕度在10dB左右，可见原始回路增益函数 $G _ { \mathrm { o } } ( s )$ 频率特性的相位裕度太小。因此虽然系统是稳定的，但存在较大的输出超调量和较长的调节时间，需要进行补偿设计。针对原始回路增益函数 $G _ { \mathrm { o } } ( s )$ 的特点，选用图5的补偿网络进行补偿设计。

图5中，有源超前一滞后补偿问题的传递函数为

$$
G _ { \mathrm { c } } = \frac { \displaystyle { \left( \frac { 1 } { s C _ { 2 } } \right) } / / { \left( R _ { 2 } + \frac { 1 } { s C _ { 1 } } \right) } } { \displaystyle { \left( R _ { 1 } \right) } / / \left( R _ { 3 } + \frac { 1 } { s C _ { 3 } } \right) }
$$

![](images/d7110a378f10192714905bf9053210e2c7f3a97955453e52d7f176476aa6c34f.jpg)  
图5有源超前一滞后补偿网络

$$
= \frac { ( 1 + s R _ { 2 } C _ { 1 } ) [ 1 + s ( R _ { 1 } + R _ { 3 } ) C _ { 3 } ] } { ( 1 + s R _ { 3 } C _ { 3 } ) \left( 1 + s \frac { R _ { 2 } C _ { 1 } C _ { 2 } } { C _ { 1 } + C _ { 2 } } \right) [ s R _ { 1 } ( C _ { 1 } + C _ { 2 } ) ] }
$$

此有源超前一滞后补偿网络有两个零点、三个极点，分别对其进行设计，可得 $R _ { 1 } = 3 . 9 2 \mathrm { k } \Omega$ ， $R _ { 2 } =$ $1 0 \mathrm { k } \Omega$ ， $R _ { 3 } = 5 4 . 4 \mathrm { k } \Omega$ ， $C _ { 1 } = 5 . 7 \mathrm { n F }$ ， $C _ { 2 } = 0 . 8 \mathrm { p F }$ ， $C _ { 3 } =$ $1 4 . 5 \mathrm { n F }$ 。代入相应参数，可以得到补偿网络 $G _ { \mathrm { c } } ( s )$ 的传递函数。

经补偿后的回路增益函数 $G ( s )$ 的Bode图如图6所示。可以看出， $G ( s )$ 在低频段有较高增益，同时以 $- 2 0 \mathrm { d B / d e c }$ 斜率下降，保证系统拥有较好的稳态精度；幅频特性在 $4 0 \mathrm { k H z }$ 处以 $- 2 0 \mathrm { d B / d e c }$ 穿过零分贝线，相位裕度为 $6 3 . 5 ^ { \circ }$ ，幅值裕度为 $1 9 . 7 \mathrm { d B }$ ，保证系统具有较高的稳定裕度。

![](images/d3314d83bc78b7c0af4109b86f80d4dc977a2bb33d6254358994163e5083fb79.jpg)  
图6补偿后回路函数 $G ( s )$ 的Bode图  
Fig.6Bode diagram of compensated loop function $G ( s )$

# 4 仿真与实验验证

为了对本文设计的NIWC系统进行验证，首先在Saber中搭建了仿真电路，如图7所示。系统分为四个模块，分别为主电路、反馈电路、补偿电路和控制与驱动电路。图8、图9为仿真波形。

在仿真基础上，对所设计的NIWC系统进行实验验证，所搭建的实验平台如图10所示。主电路基于图1的NIWC拓扑图，其中MOSFET选择IRF540型，控制电路基于芯片SG3525实现系统补偿和PWM脉冲的产生。对系统进行调试后可以发现，输入在 $2 5 \sim 3 5 \mathrm { V }$ 之间变化，此变换器均能稳定地输出 $4 2 \mathrm { V }$ 。其中，输入为28V时的实验波形如图11、图12所示。

![](images/f9f298c9530da3d3749bf6b06009cfd75fc0fe16f1a737284e72b064954a984c.jpg)  
图7NIWC系统仿真电路

![](images/a57f55e486243527b6707eb7aeb4421da3a8fd0e6fcdbad7777532fed6f98b2c.jpg)  
Fig.5The active lead-lag compensation network   
图8输入、输出电压仿真波形

![](images/78b575b99549578b269b2bc98a27934509073b77b7aa79b2d50290e97c3abe29.jpg)  
Fig.7The simulation circuit of NIWC system   
Fig.8The simulation waveforms of input voltage and output voltage   
图9输出电流及输出电压纹波仿真波形  
Fig.9The simulation waveforms of output current and output voltage ripple

仿真和实验结果说明，输出电流为7A即额定负载下，输入电压在较大范围内突变时，输出电压可以快速进行调整，实现42V的稳态输出，且输出电压纹波基本在 $1 \%$ 范围内。说明此系统主电路参数设计合理，且闭环控制系统具有良好的稳定性和快速性。

![](images/c0e3b11d193ad2ed4a589901b0c1f963818c63174fce3d68b8bc8eb220d5f247.jpg)  
图10NIWC 系统实验电路

![](images/b76276dd933c3c0c8d8898d0e970d97cb341c7967bdabcce46668cff5786bced.jpg)  
Fig.10The experimental circuit of NIWC system   
图11输入、输出电压实验波形

![](images/00f2562fb3b87847dd89024e73228b045156a5636516cec9e17f20c526e32a68.jpg)  
Fig.11The test waveforms of input voltage and output voltage   
图12输出电压纹波实验波形  
Fig.12The test waveform of output voltage ripple

# 5 结束语

本文根据DC-DC变换器分析的基本原理，对非隔离型Weinberg变换器建立了小信号模型，分析了传递函数，设计了补偿网络，搭建了仿真电路与

实验平台。仿真和实验结果表明，该变换器不但能实现升压功能，还具有高功率密度、高效率、输出电流连续等优点，对此变换器的研究为航天电源系统中的BDR电路和S3MPR或S4MPR后级变换器的研制提供了理论基础。

# 参考文献

[1] 郭显鑫，郭祖佑，王卫国，等．空间电源功率调 节技术综述[J]．上海航天，2010，27(3)：30-39. Guo Xianxin, Guo Zuyou, Wang Weiguo, et al. Review on power conditioning unit for spacecraft[J]. Aerospace Shanghai,2010,27(3): 30-39.   
[2] Maset E,Ejea JB, Ferreres A. High-efficiency Weinberg converter for battery discharging in aerospace applications[C]. Procedings of the IEEE Applied Power Electronics Conference,2006:1510- 1516.   
[3] 刘治钢，蔡晓东，陈琦，等．采用MPPT技术的 国外深空探测器电源系统综述[J]．航天器工程, 2011，20(5):105-110. Liu Zhigang,Cai Xiaodong,Chen Qi,et al. Overview of space power syster design using MPPT for deep space spacecraft[J]. Spacecraft Engineering, 2011, 20(5): 105-110.   
[4] 曾毅，崔波．一种新的航天器电源系统拓扑[J]. 航天器工程，2009，18(5)：95-100. Zeng Yi, Cui Bo.A novel topology of spacecraft electric power system[J]. Spacecraft Engineering, 2009,18(5): 95-100.   
[5] Weinberg A K, Rueda Boldo P. A high power, high frequency, DC to DC converter for space applications[C]. 23rd Annual IEEE Power Electronics Specialists Conference (PESC'92),1992: 1140-1147.   
[6] 陈骞，郑岩，郑琼林，等．基于非隔离型Weinberg 变换器多模块并联系统的建模与控制环路设计[J]. 北京交通大学学报，2012，36(5)：36-42. Chen Jian, Zheng Yan, Zheng Qionglin, et al. Modeling and design of control loops for parallel non-isolated Weinberg converter system[J]. Journal of Beijing Jiaotong University,2012,36(5): 36-42.   
[7] 徐德鸿．电力电子系统建模及控制[M]．北京：机 械工业出版社，2005.