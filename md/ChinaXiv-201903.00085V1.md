# 动车组直流侧拍频抑制方法研究

邓焯辉」　蒙东毅² 邱瑞昌²(1.广州铁路（集团）公司 广州 5100002.北京交通大学电气工程学院北京 100044)

![](images/3663f2f73cd75dd971cdfcc19de31108cc9649db76c9a2f9ad21cb73e0f424bb.jpg)

邓焯辉男 1980年生，工程师，主要从事动车组运行检修工作。

摘要：伴随着国内城市化进程的快速发展，城际交通的需求日渐增长，而动车组以其灵活的编组方式、优良的调速性能成为城际交通的首选。动车组列车牵引变流器中的拍频现象会导致系统损耗增加、发热及机械抖动严重。本文结合单相整流器的结构特性，对拍频现象的来源及其影响进行了分析，综合比较了国内外各种拍频现象的抑制方法，并进行了归纳总结。

关键词：动车组矢量控制 拍频现象无拍频控制中图分类号：TM392

# Research on Suppression Method of EMU DC-Link Beat Phenomenon

![](images/ca5c81f99cb289d79a30b49ac0f728086ba5f92aa88bd60cbc2fc6a75094eb51.jpg)

Deng Zhuohui'Meng Dongyi²Qiu Ruichang² (1.Guangzhou Railway(Group) CompanyGuangzhou 510000 China 2.Beijing Jiaotong UniversityBeijing100044 China)

蒙东毅男 1992年生，硕士研究生，主要研究方向为电力电子技术及其应用。

Abstract: With the rapid development of nationwide urbanization, there is a growing demand for intercity transportation. EMU becomes the preferred intercity transport with its flexible marshalling approach and excellnt speed performance. Beat phenomenon in EMU traction converters can lead to system loss,severe fever and mechanical shaking. Combined with structural characteristics of single-phase rectifier, sources and influence on the beat phenomenon are analyzed in the paper. The suppression methods of beat phenomenon at home and abroad are compared. The advantages and disadvantages of control modes are summarized.

Keywords: EMU, vector control, beat phenomenon, beat-less control

# 1 引言

动车组是铁路系统中有能力实现小编组、大密度的高效运输工具，具有编组灵活、快捷、安全、可靠、方便、舒适等特点，在交通运输体系中占有日益重要的地位，成为世界铁路发展的潮流。

在动车组牵引传动系统中，由于铁路单相供电的特性，网侧变流器会在中间直流环节产生二倍于网压频率的脉动电压，该脉动电压会在电机侧产生谐波电流和转矩脉动，进一步引起异步电机的温升和损耗，这种现象叫做拍频现象[1]。为进一步提高牵引传动系统的性能，需要在电机控制模块中加入无拍频控制功能以抑制拍频现象。

本文首先结合单相整流器的结构特性，详细分析了直流侧二次脉动电压产生的原因，并对拍频现象的影响进行了定性分析，然后对拍频现象的抑制方法展开研究，比较了多种软硬件控制方式的优缺点，归纳总结得出抑制拍频现象的基本要求。

# 2 拍频现象分析

# 2.1牵引传动系统主电路结构

图1所示为动车组牵引传动系统结构框图。动车组牵引传动系统主要包括受电弓、牵引变压器、四象限整流器、中间直流环节、牵引逆变器和牵引电机[2]。接触网的单相交流电通过受电弓传到牵引变压器，牵引变压器进行降压，并通过四象限整流器整流成稳定的直流电压。网侧交流电感 $L _ { \mathrm { s } }$ 的主要作用是隔离网侧电压与四象限整流器电压，储能并滤去交流电流的谐波，在整流器与电网间进行无功传递。直流环节中的支撑电容 $C _ { \mathrm { d } }$ ，起到了稳定直流电压、抑制谐波、使交流侧与直流侧的能量交换得到缓冲的作用。牵引逆变器是牵引传动系统的重要核心部分，主要功能是将直流电压转换成电压、频率可调的三相交流电驱动牵引电机，从而拖动动车组列车运行。当列车处于再生制动工况时，牵引电机处于发电状态，逆变器工作于整流状态对中间直流环节充电，使直流环节电压上升，四象限整流器工作于逆变状态，将直流电逆变成单相交流电，通过牵引变压器、受电弓等将能量回馈至供电系统，完成机械能和电能的转换。

![](images/ea0f610a3f3b690844d33e3af86eae60f3f9547745789b1f28e3c3779e1c6889.jpg)  
图1动车组牵引传动系统结构框图  
Fig.1Architecture of hybrid EMU traction system

动车组常用逆变器主要有三电平逆变器与传统的两电平逆变器[3]，如CRH2型动车组即采用了三电平逆变器。采用三电平逆变器可以提高直流电压和容量，在同样的开关频率及控制方式下降低电压、电流谐波，但是三电平逆变器同样具有器件多、控制方式复杂、质量大、可靠性低等缺点，因此本文牵引传动系统采用运行可靠且易于控制的两电平逆变器[4]

# 2.2牵引变流器直流电压二次脉动的产生

在图1所示交－直－交牵引传动系统中，铁路系统采用单相工频交流电供电，因此四象限整流器为单相结构。

在仅考虑基波分量的条件下，对单相四象限整流器的输入电压和电流进行定义，即

$$
u _ { \mathrm { s } } = \sqrt { 2 } U _ { \mathrm { s } } \cos \omega _ { \mathrm { g r i d } } t
$$

$$
i _ { \mathrm { s } } = \sqrt { 2 } I _ { \mathrm { s } } \cos { ( \omega _ { \mathrm { g r i d } } t + \varphi ) }
$$

式中， $U _ { \mathrm { s } }$ 和 $I _ { \mathrm { s } }$ 分别为基波下单相四象限整流器的输入电压、电流有效值； $\omega _ { \mathrm { g r i d } }$ 为电网供电的角频率； $\varphi$ 为整流器网侧电流滞后于电压的相位角，即四象限整流器功率因数角。由此可得交流侧的瞬时输入功率并通过三角函数公式化简为

$$
P _ { \mathrm { i } } = u _ { \mathrm { s } } i _ { \mathrm { s } } = U _ { \mathrm { s } } I _ { \mathrm { s } } \cos \varphi + U _ { \mathrm { s } } I _ { \mathrm { s } } \cos \left( 2 \omega _ { \mathrm { g r i d } } t + \varphi \right)
$$

根据瞬时功率平衡的原则[5]，假设整流器中均为理想开关器件，因此忽略四象限整流器的功率损耗，可以得到整流器的输入、输出功率相等，即

$$
P _ { \mathrm { i } } = P _ { \mathrm { o } }
$$

假定实际的直流母线电压中包括稳态电压分量和脉动电压分量，即

$$
u _ { \mathrm { d c } } = U _ { \mathrm { d c } } + \tilde { u } _ { \mathrm { d c } }
$$

式中， $U _ { \mathrm { d c } }$ 为直流侧稳态电压分量； $\tilde { u } _ { \mathrm { d c } }$ 为直流侧脉动电压分量。四象限整流器的输出功率包括稳态分量和脉动分量两部分，即

$$
P _ { \mathrm { o } } = U _ { \mathrm { d c } } I _ { \mathrm { d c } } + U _ { \mathrm { d c } } C \frac { \mathrm { d } \tilde { u } _ { \mathrm { d c } } } { \mathrm { d } t }
$$

式中， $C$ 为直流侧支撑电容； $U _ { \mathrm { d c } }$ 、 $\boldsymbol { I } _ { \mathrm { d c } }$ 为直流侧电压和电流的稳态分量。

将式（3）、式（6）代入式（4）中，输入功率与输出功率中的稳态分量对应相等，脉动分量也对应相等，因此有

$$
U _ { \mathrm { s } } I _ { \mathrm { s } } \cos \varphi = U _ { \mathrm { d c } } I _ { \mathrm { d c } }
$$

$$
U _ { \mathrm { s } } I _ { \mathrm { s } } \cos { ( 2 \omega _ { \mathrm { g r i d } } t + \varphi ) } = U _ { \mathrm { d c } } C \frac { \mathrm { d } \tilde { u } _ { \mathrm { d c } } } { \mathrm { d } t }
$$

将式（7）与式（8）联立并化简，可以得到直流侧脉动电压分量的表达式，即

$$
\tilde { u } _ { \mathrm { d c } } = \frac { I _ { \mathrm { d c } } \sin { ( 2 \omega _ { \mathrm { g r i d } } t + \varphi ) } } { 2 \omega _ { \mathrm { g r i d } } C \cos { \varphi } }
$$

由式（9）可知，直流侧脉动电压分量 $\tilde { u } _ { \mathrm { d c } }$ 的幅值取决于直流侧稳态电流分量 $\boldsymbol { I } _ { \mathrm { d c } }$ 、直流侧支撑电容C 和四象限整流器的功率因数角 $\varphi ^ { [ 6 - 7 ] }$ 。动车组的四象限整流器为了保持高效运行与快速响应多采用瞬态电流控制的双闭环控制策略，通过这种控制策略，可以使四象限整流器的功率因数近似为 $1 ^ { [ 8 ] }$ ，因此在上述表达式中，可以忽略整流器功率因数角 $\varphi$ 的影响。此时脉动电压分量 $\tilde { u } _ { \mathrm { d c } }$ 只与直流侧支撑电容 $C$ 和稳态电流 $\boldsymbol { I } _ { \mathrm { d c } }$ 有关。因此，在牵引传动系统运行时，当直流侧电压 $U _ { \mathrm { d c } }$ 保持稳定，输出功率越大，脉动电压也越大，同时，也可以增大支撑电容 $C$ 的容量以达到减少二次脉动电压的目的。通过式（9）可以看出，直流侧脉动电压的频率是电网供电频率的二倍，当采用单相工频 $5 0 \mathrm { { H z } }$ 交流电供电时，脉动电压频率为 $1 0 0 \mathrm { H z }$ 。

# 2.3脉动电压对电机相电压的影响

根据上述分析，可以得到直流侧电压的表达式为

$$
u _ { \mathrm { d c } } \left( t \right) = U _ { \mathrm { d c } } + \frac { I _ { \mathrm { d c } } \sin { \left( 2 \omega _ { \mathrm { g r i d } } t + \varphi \right) } } { 2 \omega _ { \mathrm { g r i d } } C \cos { \varphi } }
$$

为了方便下文分析，定义

$$
\Delta U _ { \mathrm { d c } } = \frac { I _ { \mathrm { d c } } } { 2 \omega _ { \mathrm { g r i d } } C \cos \varphi }
$$

则式（10）可以写为

$$
u _ { \mathrm { d c } } \left( t \right) = U _ { \mathrm { d c } } + \Delta U _ { \mathrm { d c } } \sin { \left( 2 \omega _ { \mathrm { g r i d } } t + \varphi \right) }
$$

设逆变器在a、b、c三相的开关函数分别为 $S _ { \mathrm { a } }$ ，

$S _ { \mathrm { b } }$ ， $S _ { \mathrm { c } }$ ，则逆变器输出相电压可以表示为

$$
\begin{array} { r } { \left( \begin{array} { l } { u _ { \mathrm { a } } } \\ { u _ { \mathrm { b } } } \\ { u _ { \mathrm { c } } } \end{array} \right) = \left( \begin{array} { l } { S _ { \mathrm { a } } } \\ { S _ { \mathrm { b } } } \\ { S _ { \mathrm { c } } } \end{array} \right) u _ { \mathrm { d c } } \left( t \right) } \end{array}
$$

当不考虑直流侧脉动电压且仅考虑基波分量时，可以得到开关函数的表达式，即

$$
\left( \begin{array} { c } { S _ { \mathrm { s } } } \\ { S _ { \mathrm { s } } } \\ { S _ { \mathrm { c } } } \end{array} \right) = \left( \begin{array} { c } { u _ { \mathrm { a } } ^ { * } } \\ { u _ { \mathrm { b } } ^ { * } } \\ { u _ { \mathrm { c } } ^ { * } } \end{array} \right) \frac { 1 } { U _ { \mathrm { d c } } } = \left( \begin{array} { c } { m \sin \omega _ { \mathrm { e } } t } \\ { m \sin \left( \omega _ { \mathrm { e } } t - \frac { 2 \pi } { 3 } \right) } \\ { m \sin \left( \omega _ { \mathrm { e } } t + \frac { 2 \pi } { 3 } \right) } \end{array} \right)
$$

式中， $u _ { \mathrm { a } } ^ { \ast }$ 、 $u _ { \mathrm { b } } ^ { \ast }$ 、 $u _ { \mathrm { c } } ^ { * }$ 为逆变器输出的理想三相基波电压； $U _ { \mathrm { d c } }$ 为无脉动的直流母线电压。

针对式（13）中a相，其输出相电压的表达式为

$$
\begin{array} { l } { { \displaystyle u _ { \mathrm { a } } ( t ) = m \sin \omega _ { \mathrm { e } } t [ U _ { \mathrm { d c } } + \Delta U _ { \mathrm { d c } } \sin \left( 2 \omega _ { \mathrm { g r i d } } t + \varphi \right) ] } } \\ { ~ } \\ { { \displaystyle ~ = \frac { 1 } { 2 } m \Delta U _ { \mathrm { d c } } \cos \left[ \left( 2 \omega _ { \mathrm { g r i d } } - \omega _ { \mathrm { e } } \right) t + \varphi \right] - } } \\ { { \displaystyle ~ \frac { 1 } { 2 } m \Delta U _ { \mathrm { d c } } \cos \left[ \left( \omega _ { \mathrm { e } } + 2 \omega _ { \mathrm { g r i d } } \right) t + \varphi \right] + U _ { \mathrm { m } } \sin \omega _ { \mathrm { e } } t } } \end{array}
$$

式中， $U _ { \mathrm { m } }$ 为只考虑基波时逆变器输出的相电压有效值； $\omega _ { \mathrm { e } }$ 为只考虑基波时逆变器输出的相电压频率；$\Delta U _ { \mathrm { d c } }$ 为脉动分量幅值； $\omega _ { \mathrm { g r i d } }$ 为电网供电的角频率；$\varphi$ 为整流器网侧电流滞后于电压的相位角，即四象限整流器的功率因数角； $m$ 为正弦脉宽调制深度，且 $m = U _ { \mathrm { m } } / U _ { \mathrm { d c } }$ 。

由式（15）可以看出，逆变器的输出相电压包括直流稳态电压 $U _ { \mathrm { d c } }$ 产生的频率为 $\omega _ { \mathrm { e } }$ 的稳态分量，以及由脉动电压 $\Delta U _ { \mathrm { d c } }$ 产生的频率为 $2 \omega _ { \mathrm { g r i d } } \pm \omega _ { \mathrm { e } }$ 的脉动分量，该脉动分量即逆变器输出电压中的拍频分量[，通过脉动直流母线与逆变器开关函数调制产生。由于高频谐波幅值随着谐波次数增加而降低，在上述推导过程中只考虑了基频分量，因而频率为$2 \omega _ { \mathrm { g r i d } } \pm \omega _ { \mathrm { e } }$ 的脉动电压是逆变器输出电压中的主要拍频分量[10-11]

# 3 拍频现象抑制方法

目前，拍频现象主要有两种抑制方法，一种是采用硬件方法直接抑制直流侧脉动电压，从而消除电机的拍频电流和拍频转矩；另一种是通过软件控制的方法在逆变器中加入无拍频控制策略，削弱脉动电压在电机侧产生的影响。软件控制的方法主要有前馈补偿、单周期控制、频率补偿等。下面对国内外几种主要的试验系统的模式进行比较综述，并归纳总结试验系统的要求。

# 3.1 硬件方法

传统的拍频现象抑制方法是硬件滤波，即在直流母线上并联一个在母线脉动频率点谐振的LC滤波器吸收谐振分量，缺点是滤波器体积和质量较大。此外，还可以采用增大支撑电容容量的方式，由式(9）可知直流脉动电压大小与支撑电容容量有关，支撑电容容量越大，对直流脉动电压的抑制效果越好，当支撑电容趋于无穷时，能够维持直流电压恒定，但是在工程应用中，支撑电容不能取为无限大，因此单纯增大支撑电容容量不能完全抑制直流脉动。

使用硬件方法能够抑制直流侧二倍频的脉动电压，但是硬件滤波的方式存在很大缺点。

（1）牵引传动系统中，电压等级较高而谐振频  
率较低，因此LC滤波器的体积和质量往往较大，  
不但使变流器功率密度降低，而且增大了系统成本。(2）工程中使用的LC谐振滤波器的实际值与  
理论值存在一些偏差，偏差的存在使滤波电路不能  
完全滤去二次脉动，因此直流侧仍然存在纹波，纹  
波电压与等效电阻会使谐振电路产生能量损耗。(3）单纯增大支撑电容以稳定直流电压，增大

了变流器短路危害，使系统稳定性降低。

# 3.2 软件方法

（1）前馈补偿。牵引逆变器的输出电压与直流电压和开关信号有关，根据直流电压的瞬时变化可以修正开关信号，改变调制波的幅值，消除脉动直流电压对逆变器输出电压的影响[12]。

前馈补偿的基本原理是对调制比或脉冲宽度进行实时补偿，即通过实时计算对牵引逆变器的PWM脉冲进行精确补偿，确保逆变器即使工作于母线脉动电压下也能够准确调制出电机所需的电压，不会输出有害的拍频电流。上述分析中，式 (14)为补偿前的开关函数表达式，采用前馈补偿对调制比进行补偿后，得到修正后的开关函数为

$$
\left( \begin{array} { c } { S _ { \mathrm { a } } ^ { \prime } } \\ { S _ { \mathrm { b } } ^ { \prime } } \\ { S _ { \mathrm { c } } ^ { \prime } } \end{array} \right) = m ^ { \prime } \sin \left( \omega _ { \mathrm { c } } t - \frac { 2 \pi } { 3 } \right)
$$

式中， $m ^ { \prime }$ 为修正后的调制深度，且

$$
m ^ { \prime } = m \frac { U _ { \mathrm { d c } } } { u _ { \mathrm { d c } } \left( t \right) } = \frac { U _ { \mathrm { m } } } { U _ { \mathrm { d c } } + \Delta U _ { \mathrm { d c } } \sin \left( 2 \omega _ { \mathrm { g r i d } } t + \varphi \right) }
$$

以a相为例，开关函数修正后逆变器输出相电压为

$$
u _ { \mathrm { a } } = S _ { \mathrm { a } } ^ { \prime } u _ { \mathrm { d c } } ( t ) = m U _ { \mathrm { d c } } \sin { \omega _ { \mathrm { e } } t }
$$

而直流侧无脉动电压时逆变器输出相电压的期望值为 ${ u _ { \mathrm { a } } ^ { * } }$ ，即

$$
U _ { \mathrm { a } } ^ { \mathrm { * } } = U _ { \mathrm { m } } \sin { \omega _ { \mathrm { e } } t } = m U _ { \mathrm { d c } } \sin { \omega _ { \mathrm { e } } t } = u _ { \mathrm { a } }
$$

因此修正后的逆变器输出相电压分量不再含有拍频成分，前馈补偿法能够通过控制调制比控制脉冲宽度，抑制拍频现象。当逆变器检测到直流母线的二倍频脉动电压时，在母线电压脉动的正半周期减小调制深度，减小输出电压脉冲宽度；在母线电压脉动的负半周期增加调制深度，增加输出电压脉冲宽度[13]

前馈补偿方案效果好且易于实现，即使母线电压剧烈脉动仍然可以实现面积等效。然而对于大功率低开关频率场合，如果电机转速过大时，电压幅值已经达到最大，则可调节的调制深度的裕量并不大，同时母线电压真实值与其预测值误差较大，且会增加特定谐波的含量，因此补偿效果不佳。

(2）单周期控制。单周期控制（OOC）是一种针对电力电子变换器的非线性控制技术，而且是一种模拟控制技术，当参考电压信号变化时，单周期控制器在一个开关周期内能够迅速调整开关导通时间，使输出信号的平均值精确等于或正比于指令信号[14]。单周期控制动态响应性能快，抗干扰能力强。

当牵引传动系统工作在逆变器多脉冲调制区时，带复位开关的积分器能够生成逆变器的三角载波参考信号，且载波信号的幅值随着直流侧电压 $U _ { \mathrm { d c } }$ 的变化而变化，当直流侧电压脉动时，单周期控制器输出的PWM脉冲宽度随着 $U _ { \mathrm { d c } }$ 的变化调整，因此，单周期控制算法能够消除脉动直流电压对逆变器输出电压的影响，电机的拍频电流和拍频转矩也能得到抑制。

当牵引传动系统工作在逆变器单脉冲调制区时，调制信号频率与开关频率相同，因此传统单周期控制方式不适于逆变器单脉冲调制[15]。单脉冲调制区的单周期控制采用了伏秒平衡的原理，在直流电压正向脉动时减小脉冲宽度，在直流电压负向脉动时增大脉冲宽度。为了精确补偿脉动直流电压引起的逆变器相电压变化，需要确定脉冲正负半周的切换时间，在数字控制中计算切换点较复杂，而在单周期控制中由于采用了模拟控制方法，切换时间不需要求解，因此能够简单地实现伏秒平衡。

采用单周期控制的无拍频控制方法，动态响应速度快，开关频率恒定，抗干扰能力强，但是这种控制方法在多脉冲调制区与单脉冲调制区采用了不同的控制器，需要在不同的调制区进行切换，增加了系统的复杂性，且模拟电路设计与控制的工作量、复杂度都较大。

(3）频率补偿。频率补偿是通过补偿逆变器的工作频率来抑制脉动分量产生的拍频电流。第一种频率补偿方法如图2所示，对变流器开关函数叠加了一个体现脉动分量的时间函数进行补偿[16]。

![](images/0fa51022b11a512d401972cb0e41ea4fe511f6553d4f9a568dd26d63ce72999d.jpg)  
图2基于频率补偿的开关函数示意图  
Fig.2Frequency modulated switching function

频率补偿应用于转子磁场定向矢量控制系统时，在转速环注入了脉动分量用以补偿逆变器工作频率，从而抑制了异步电机的拍频电流。

补偿前的开关函数可以用傅里叶形式表示为

$$
S ( \theta ) = { \frac { 1 } { 2 } } + \sum _ { k = \mathrm { o d d } } ^ { \infty } A _ { k } \cos k \theta
$$

如果对开关函数补偿一个时间函数，开关函数可以改写为

$$
S ( t ) = \frac { 1 } { 2 } + \sum _ { k = \mathrm { o d d } } ^ { \infty } A _ { k } \cos k [ \omega _ { \mathrm { s } } t + \alpha ( t ) ]
$$

其中

$$
\alpha ( t ) = \frac { 2 \pi \Delta F _ { \mathrm { r } } } { \omega _ { \mathrm { r } } } \sin { ( \omega _ { \mathrm { r } } t + \varphi _ { \mathrm { r } } ) }
$$

则逆变器的瞬时工作频率可以表示为

$$
f _ { \mathrm { i } } = \frac { 1 } { 2 \pi } \frac { \mathrm { d } } { \mathrm { d } t } \theta ( t ) = F _ { \mathrm { s } } + \Delta F _ { \mathrm { r } } \cos { ( \omega _ { \mathrm { r } } t + \varphi _ { \mathrm { r } } ) }
$$

式中， $\Delta F _ { \mathrm { r } }$ 为频率补偿系数； $F _ { \mathrm { s } }$ 为逆变器工作频率。

逆变器开关函数的表达式为

$$
\begin{array} { c } { { S ( t ) = \displaystyle \frac { 1 } { 2 } + \sum _ { k = 0 } ^ { \infty } A _ { k } \{ \cos k \omega _ { s } t \cos \{ k C [ \sin ( \omega _ { \mathrm { r } } t + \varphi _ { \mathrm { r } } ) ] \} - } } \\ { { { } } } \\ { { \sin k \omega _ { s } t \sin \{ k C [ \sin ( \omega _ { \mathrm { r } } t + \varphi _ { \mathrm { r } } ) ] \} } } \\ { { { } } } \\ { { { } = \displaystyle \frac { 1 } { 2 } + A _ { 1 } \{ \cos \omega _ { s } t + \frac { C } { 2 } \Bigl \{ \cos [ ( \omega _ { \mathrm { r } } + \omega _ { s } ) t + \varphi _ { \mathrm { r } } ] - \begin{array} { l } { { { } } } \\ { { { } } } \\ { { } } \end{array}  } } \\ { { \cos [ ( \omega _ { \mathrm { r } } - \omega _ { s } ) t + \varphi _ { \mathrm { r } } ] \Bigr \} } }  \end{array} \quad ( \mathrm { r } ) ,
$$

其中

$$
C = 2 \pi \Delta F _ { \mathrm { r } } / \omega _ { \mathrm { r } }
$$

通过补偿后开关函数与直流侧母线电压表达式能够得到补偿后的逆变器输出相电压表达式，以a相为例，为

$$
\begin{array} { r l } & { v _ { i _ { \mathrm { m } } } = u _ { i _ { \mathrm { m } } } ( S - 1 / 2 ) } \\ & { \quad = U _ { i _ { \mathrm { m } } } \mathcal { A } _ { i _ { \mathrm { m } } } \cos \theta , i ^ { \star } } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \frac { \Delta U _ { i _ { \mathrm { m } } } \mathcal { A } _ { i _ { 1 } } + \Delta _ { i _ { \mathrm { m } } } C U _ { \mathrm { A } } } { 2 } \cos \left[ ( \omega _ { i } + \omega _ { s } ) t + \mathcal { C } _ { r } \right] + } \\ & { \quad \quad \quad \quad \quad \quad \frac { \Delta U _ { i _ { \mathrm { m } } } \mathcal { A } _ { i _ { 1 } } C } { 4 } \cos \left[ ( 2 \omega _ { i } + \omega _ { s } ) t + 2 \varphi _ { i } \right] - } \\ & { \quad \quad \quad \quad \quad \quad \frac { \Delta U _ { i _ { \mathrm { m } } } \mathcal { A } _ { i _ { 1 } } C } { 4 } \cos \left[ ( 2 \omega _ { r } - \omega _ { s } ) t + 2 \varphi _ { r } \right] + } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \frac { \Delta U _ { i _ { \mathrm { m } } } \mathcal { A } _ { i _ { 1 } } - A _ { \mathrm { m } } C U _ { \mathrm { A } } } { 2 } \cos \left[ ( \omega _ { i } - \omega _ { s } ) t + 2 \varphi _ { r } \right] + } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad \quad } \\ & { \quad \quad \quad \quad \quad \quad \quad \quad \quad \frac { \Delta U _ { i _ { \mathrm { m } } } \mathcal { A } _ { i _ { 1 } } - A _ { \mathrm { m } } C U _ { \mathrm { A } } } { 2 } \cos \left[ ( \omega _ { i } - \omega _ { s } ) t + \varphi _ { i } \right] } \end{array}
$$

从式（26）可知，为消除逆变器输出的脉动电压，应该满足

$$
\Delta U _ { \mathrm { d c } } A _ { \mathrm { a l } } - A _ { \mathrm { a l } } C U _ { \mathrm { d c } } = 0
$$

则频率补偿系数可以表示为

$$
\Delta F _ { \mathrm { { r } } } = { \frac { C \omega _ { \mathrm { { r } } } } { 2 \pi } } = { \frac { \omega _ { \mathrm { { r } } } } { 2 \pi } } { \frac { \Delta U _ { \mathrm { { d c } } } } { U _ { \mathrm { { d c } } } } }
$$

通过对逆变器频率进行补偿能够消除频率为$\omega _ { \mathrm { r } } - \omega _ { \mathrm { s } }$ 的拍频相电压分量，但是与补偿前逆变器的相电压相比同时引入了频率为 $2 \omega _ { \mathrm { r } } \pm \omega _ { \mathrm { s } }$ 的谐波电压，在抑制拍频分量的同时引入了高频谐波分量[17]，会对异步电机的性能造成影响。

第二种频率补偿方法通过对异步电机建模分析得到拍频现象的数学模型，并基于频域分析得出无拍频控制策略[18]

从上述分析可知，脉动电压 $V _ { \mathrm { d c } } ^ { \Delta }$ 是产生拍频现象的原因，而传递函数 $G _ { \mathrm { i f } } \left( s \right)$ 和 $G _ { \mathrm { t f } } \left( s \right)$ 定义了拍频电流和拍频转矩与转差频率增量的关系，在无拍频控制系统中，希望能够按照直流电压的脉动规律对转差频率进行补偿，从而抵消脉动电压产生的拍频电流和拍频转矩，因此能够得到如图3所示的无拍频控制器原理框图[19]

![](images/e01020e9c9039ae5c9aa1543230c565c58782063f2d4461ce8886ed7b38b83da.jpg)  
图3无拍频控制原理框图  
Fig.3Schematic of beat-less control

在控制框图中，主电路部分包括牵引逆变器和异步电机的动态模型，可以看出 $V _ { \mathrm { d c } } ^ { \Delta }$ 是导致拍频电流 $\boldsymbol { I } ^ { \Delta }$ 和拍频转矩 $T _ { \mathrm { e } } ^ { \Delta }$ 的原因。在补偿环节中， $G _ { \mathrm { c } } ( s )$ 为无拍频控制器的传递函数，脉动电压 $V _ { \mathrm { d c } } ^ { \Delta }$ 作用于无拍频控制器可以产生补偿的转差频率 $f _ { \mathrm { s l } } ^ { \Delta }$ ，通过补偿环节的无拍频控制可以消除 $V _ { \mathrm { d c } } ^ { \Delta }$ 在主电路中产生的拍频分量 $\boldsymbol { I } ^ { \Delta }$ ， $T _ { \mathrm { e } } ^ { \Delta }$ 。

由上述分析可知，抑制拍频电流 $I ^ { \Delta }$ 即在脉动频率点抑制 $I ^ { \Delta } / V _ { \mathrm { d c } } ^ { \Delta }$ 的增益，抑制拍频转矩 $T _ { \mathrm { e } } ^ { \Delta }$ 即在脉动频率点抑制 $T _ { \mathrm { e } } ^ { \Delta } / V _ { \mathrm { d c } } ^ { \Delta }$ 的增益，因此无拍频控制器 $G _ { \mathrm { c } } ( s )$ 应满足式（29）和式（30）中的关系，在脉动频率点抑制传递函数 $G _ { \mathrm { i } } ( s )$ 和 $G _ { \mathfrak { t } } ( s )$ 的增益，即

$$
\begin{array} { r } { G _ { \mathrm { c } } ( \mathrm { j } \omega _ { \mathrm { r i p p l e } } ) G _ { \mathrm { i f } } ( \mathrm { j } \omega _ { \mathrm { r i p p l e } } ) + G _ { \mathrm { i u } } ( \mathrm { j } \omega _ { \mathrm { r i p p l e } } ) = 0 } \\ { G _ { \mathrm { c } } ( \mathrm { j } \omega _ { \mathrm { r i p p l e } } ) G _ { \mathrm { t f } } ( \mathrm { j } \omega _ { \mathrm { r i p p l e } } ) + G _ { \mathrm { u } } ( \mathrm { j } \omega _ { \mathrm { r i p p l e } } ) = 0 } \end{array}
$$

$$
\begin{array} { l } { \displaystyle { G _ { \mathrm { i } } ( s ) = \frac { I ^ { \Delta } } { V _ { \mathrm { d c } } ^ { \Delta } } = G _ { \mathrm { i u } } \big ( s \big ) + G _ { \mathrm { c } } ( s ) G _ { \mathrm { i f } } ( s ) } } \\ { \displaystyle { G _ { \mathrm { t } } ( s ) = \frac { T _ { \mathrm { e } } ^ { \Delta } } { V _ { \mathrm { d c } } ^ { \Delta } } = G _ { \mathrm { u } } \big ( s \big ) + G _ { \mathrm { c } } ( s ) G _ { \mathrm { t f } } ( s ) } } \end{array}
$$

式中， $\omega _ { \mathrm { r i p p l e } }$ 为脉动频率点的角频率； $G _ { \mathrm { i } } ( s )$ 为采用无拍频控制器后拍频电流的传递函数； $G _ { \mathfrak { t } } ( s )$ 为采用无拍频控制器后拍频转矩的传递函数。

频率补偿是通过补偿逆变器的工作频率来抑制脉动分量产生的拍频电流，通过一定算法对电机频率指令进行修正以达到抑制拍频现象的目的，这种方法需要对脉动分量精确采样，对拍频现象的抑制效果较好。

# 4 结束语

动车组列车牵引变流器中的拍频现象会导致系统损耗增加、发热及机械抖动严重。本文首先结合单相整流器的结构特性，详细分析了直流侧二次脉动电压产生的原因，并对拍频现象的影响进行了定性分析，对拍频现象的软硬件抑制方法展开研究，对比分析了硬件滤波法、前馈补偿法、单周期控制法及频率补偿法，总结了每种控制方法的原理及优缺点，归纳总结得出拍频现象的来源及抑制方法。

# 参考文献

[1] 黄金，陆阳，高翔．动车组、电力机车拍频现象 研究[J]．铁道机车车辆，2013(3)：10-12. Huang Jin,Lu Yang,Gao Xiang. The EMU electric locomotive beat phenomenon research[J]. Railway Locomotive & CAR,2013(3): 10-12.   
[2] 欧阳晖，张凯，张鹏举．牵引变流器直流母线电 压脉动下的无拍频电流控制方法[J]．电工技术学 报，2011，26(8)：14-23. Ouyang Hui, Zhang Kai, Zhang Pengju. Repetitive prediction of fluctuating DC link voltage for traction drives[J]. Transactions of China Electrotechnical Society,2011,26(8): 14-23.   
[3] Prasad N Enjeti, Wajiha Shireen.A new technique to reject DC-link voltage ripple for inverters operating on pragrammed PWM waveforms[J]. IEEE Transactions on Power Electronics,1992,7(1): 171- 180.   
[4] 李伟，马志文，蔡华斌，等．无二次滤波环节的 单相四象限整流器输入电流控制研究[J]．铁道学 报，2014(5)：28-32. Li Wei,Ma Zhiwen,Cai Huabin. Control of input current of PWM rectifier without secondary filter circuit[J]. Journal of The China Railway Society, 2014(5): 28-32.   
[5] Di Zhang,Wang F. DC-link ripple current reduction for paralleled three-phase voltage-source converters with interleaving[J]. Power Electronics, 2011(6): 1741-1753.   
[6] Jalili Kamram,Bernet Steffen.Design of LCL filters of active-front-end two-level voltage-source converters[J]. IEEE Transactions on Industrial Electronics,2009(56): 1674-1689.   
[7] 徐龙．高速列车牵引传动系统直流电压脉动抑制 方法的研究[D]．北京：北京交通大学，2011.   
[8] Ortega D,Shireen W,Castelli F. Control for grid connected PMSG Wind turbine with DC link capacitance reduction[C]. Transmission and Distribution Conference and Exposition(T&D), 2012: 1-8.   
[9] Liu Yong,Shang Jing.Control of induction motor with DC-link voltage ripple for high speed train applications[C]. Electrical Machines and Systems, 2011: 1-4.   
[10] Oliveira Filho ME,Gazoli JR, Sguarezi Filho AJ, et al.A control method for voltage source inverter without DC link capacitor[C]. Power Electronics Specialists Conference,2008:4432-4437.   
[11] Klima J,Chomat M, Schreier L.Analytical closedform investigation of PWM inverter induction motor drive performance under DC bus voltage pulsation[J]. IET Electric Power Applications,2008, 2(6): 341-352.   
[12] Fassinou F,Wang Haifeng,Devarakonda L. Observer-based method for reduction of dc-link voltage ripple in two-stage boost inverters[C]. American Control Conference,2014: 4348-4353.   
[13] Moia J,Perin A,Heldwein M.Three-level-phase PWM converters DC-link voltages ripple reduction technique in the $\alpha \ \beta$ reference frame[C].Applied Power Electronics Conference and Exposition, 2012: 740-747.   
[14] Wensheng S, Smedley K, Xiaoyun F,et al. One-cycle control of induction machine traction drive for high speed railway part I: multi-pulse width modulation region[C].36th Annual Conference on IEEE Industrial Electronics Society,2010: 2346-2351.   
[15] Wensheng S,Smedley K,Xiaoyun F,et al.Onecycle control of induction machine traction drive for high speed railway part II: square wavemodulation region[C].26th Annual IEEE Applied Power Electronics Conference and Exposition,2011:1003- 1009.   
[16] 苟斌，冯晓云，宋文胜．牵引变流器-电机拍频现 象及其抑制方法[J]．中国电机工程学报，2013, 33(9): 55-61. Gou Bin,Feng Xiaoyun,Song Wensheng.Analysis and suppression of beat phenomenon for railway traction converters and motors[J]. Proceedings of the CSEE,2013,33(9): 55-61.   
[17] Gou Bin, Feng Xiaoyun, Song Wensheng. Analysis and compensation of beat phenomenon for railway traction drive system fed with fluctuating DC-link voltage[C]. 7th International Conference on Power Electronics and Motion Control, 2012: 654-659.   
[18] Kimura A. Frequency domain analysis of beatless control method for converter-inverter driving systems applied to AC electroc cars[J]. Electrical Engineering in Japan, 2011,174(4): 51-59.   
[19] Dong Kan,Diao Lijun,Zhao Leiting.Research on beat-less control strategy based on frequencydomain analysis[C].2O13 International Conference on Electrical and Information Technologies for Rail Transportation,2013:129-141.

# （上接第14页）

link capacitance in a capacitor-supported system[J]. IEEE Transactions on Power Electronics,2014, 29(3): 1163-1175.   
[7] Mazumder SK.A novel hybrid modulation scheme for an isolated high-frequency-link fuel cell inverter[C].2009 IEEE/PES Conference on Power Systems Conference and Exposition,Seattle,WA, USA,2009: 1.   
[8] GrahameHolmesD，周克亮．电力电子变换器 PWM技术原理与实践[M]．北京：人民邮电出版 社，2010.   
[9] Habetler TG,Naik R E,Nondahl TA.Design and implementation of an inverter output LC filter used for dv/dt reduction[C].14th Annual Applied Power Electronics Conference and Exposition,Dallas,TX, USA,1999: 1279-1284.   
[10] Dewan S B, Ziogas PD.Optimum flter design for a single-phase solid-state UPS system[J].1979 IEEE Transactions on Industry Applications,1979,IA15(6): 664-669.   
[11] 张承志，丁和生，丘若波．不间断供电系统[M]. 北京：机械工业出版社，1987.