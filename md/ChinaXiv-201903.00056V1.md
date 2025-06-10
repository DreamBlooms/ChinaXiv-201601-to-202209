# 高压大功率非线性电流型STATCOM在输电网中的应用研究

赵建阳1,²　张福民²刘福贵²刘永和³（1.中国能源建设集团天津电力设计院有限公司天津3004002.河北工业大学电磁场与电器可靠性省部共建重点实验室天津3001303.内蒙古工业大学电力学院呼和浩特010080）

![](images/9ae11767c7dc908df12a9331493216e2f192402920f0467a329c863ac04eaa0f.jpg)

赵建阳男1985年生，博士，研究方向为电力系统及其自动化。

摘要：大功率STATCOM可以为电网电力传输提供大量无功功率，然而其控制系统具有很强的非线性。为了实现 STATCOM无功功率输出的线性控制，本文提出了一种基于多电平电流重注入式电流型换流器（MLCR-CSC）的电流型 STATCOM，阐述了MLCR-CSC 的拓扑结构和新型 STATCOM的工作原理，设计了直接电流控制系统。仿真结果表明，MLCR-CSC的谐波含量低于 $4 \%$ ，基波周期内有6个零电流时刻实现大电流过零关断。电流直接控制方式不但满足输电网对无功功率的需求，而且对不对称故障响应迅速。

关键词：电流型 STATCOM MLCR-CSC非线性控制模型直接电流控制零电流关断

中图分类号：TM315

![](images/60bcc15d1a30a44172e29066b044ab43bf812854a2d30a25b301ea7b8c29a61a.jpg)

张福民男 1965年生，博士，副教授，研究方向为电力电子与电气传动、柔性交流输电和高压直流输电。

# Research on High-Voltage High-Power Nonlinear CurrentSource STATCOM Applied in Power Transmission System

Zhao Jianyangl,2Zhang Fumin² Liu Fugui² Liu Yonghe3   
(1.China Energy Engineering Group Tianjin Electric Power Design Institute Co.,Ltd. Tianjin300400 China   
2.Province-Ministry Joint Key Laboratory of Electromagnetic Field and Electrical   
Apparatus Reliability Hebei University of TechnologyTianjin300130China 3.Faculty of Electric Power Inner Mongolia University of Technology Hohhot010080China）

Abstract: High power STATCOM can provide a large amount of reactive power for power transmission,however, its control system is highly nonlinear. In order to realize linear control reactive power of STATCOM,a new type is proposed based on MLCR-CSC. The STATCOM working principle is introduced, and the direct current control strategy is designed with double closed loop control system. The simulation results show that MLCRCSC harmonic content is lower than $4 \%$ ,and six zero current pulse realized large zero current switching. STATCOM satisfied the demand of reactive power in power grid and gave a quick responds during asymmetric fault.

Keywords: Current-source STATCOM, MLCR-CSC, nonlinear control model, direct current control strategy, zero current switching

# 1 引言

工业快速发展消耗大量电能，发电中心一般远离用电中心，而经济的发展需要电能高效稳定的传输。在高压交流输电网络中，输电线路阻抗及对地导纳与线路长度成正比，非线性负载的频繁接入与退出，引起输电网无功功率需求增大，直接影响输电效率，增加线路损耗[1]；在高压直流输电网络中,三相交流配电网的接入也需要大量无功功率[2]。

在输电网中，STATCOM可以维持或控制节点电压，提高线路输送能力、阻尼功率振荡，提高系统的稳态和暂态稳定性，提高系统运行灵活性。在电网发生故障或负荷突增时，能够动态地提供电压支撑，提高系统安全稳定水平，减少低压释放负荷数量，防止因暂态电压崩溃导致的大面积恶性停电事故发生，同时还具有可以发挥阻尼系统振荡、抑制电压闪变、改善电能质量等作用。

现有的STATCOM拓扑结构都是电压型换流器(VoltageSourceConverter，VSC)，通过基于IGBT（或者IGCT、IEGT）的2H桥单元级联，结合多电平调制技术，取得了很好的理论成果，实际设备在$3 5 \mathrm { k V }$ 以下配电网、风力发电和光伏发电行业中广泛应用[3-4]，如成功运行于南方电网 $3 5 \mathrm { k V } \pm 2 0 0 \mathrm { M }$ var的链式STATCOM装置是投入运行和连接电压等级最高的无功补偿设备，积累了电压型换流器在高压大功率场合使用的宝贵经验。进一步改进电容电压平衡控制策略、优化控制目标和降低设备损耗降，会提升设备运行效率[5-6]。

随着电网输送功率的增加， $5 0 0 \mathrm { k V }$ 及以上电压等级鲜有STATCOM投运案列。单组VSC无功补偿容量高于200Mvar，功率器件的串并联使用会有较大的技术难度，电压均衡问题和设备故障时的安全问题更加凸显[7-9]。

基于电网换相换流器(LineCommutatedConverter，LCC）的高压直流输电技术发展成熟，晶闸管串联使用经验丰富，传统12脉波换流器拓扑结构稳定性高，故障响应迅速[10-11]。文献[12-14]提出了直流纹波的概念，阐述了直流纹波注入技术在换流器中的发展，借助VSC多电平技术，得到一种多电平电流重注入电流型换流器(MultiLevel Current Reinjection-Current Source Converter,MLCR-CSC)，即在传统12脉波换流器基础上增加新的电流重注入回路。该拓扑结构有以下优点：主功率器件使用晶闸管，导通频率 $5 0 \mathrm { { H z } }$ ，降低了设备损耗；基波周期内有6个电流为零时刻，可以实现周期内任意时刻零电流关断；交流侧电流谐波含量低于 $4 \%$ ；直接电流控制保证设备故障响应迅速；电压换相不依赖自然换相点，单位功率因数运行；没有电容均压问题。

本文设计了双组MLCR-CSC拓扑结构，并验证了其在百Mvar以上输电网中无功需求的响应。

# 2 电流型STATCOM拓扑结构及其工作原理

# 2.1 拓扑结构

在输配电网 $2 2 0 \mathrm { k V }$ 及以下线路中，基于VSC的STATCOM技术应用成熟，实际项目成功投入运行，而电流型换流器（CurrentSourceConverter,CSC）拓扑结构在这种应用场合中没有任何优势。然而，在高压大功率场合VSC受到器件特性和安全运行问题的影响，难以超越CSC具有的安全稳定的优势，且电流直接控制可以保障电网稳定和设备本身安全。从技术实现来说，VSC增压扩容的难度较大，而CSC借助LCC易实现在输电网中的应用。从经济价值来说，VSC链式结构在配电网络中可以提高电能质量，CSC拓扑结构在高压特高压场合更易实现电能质量的提高，研发周期短，成本低。本文选用两组MLCR-CSC串联，一方面在传统电网换相换流器的基础上提高换流器的电压等级；另一方面是为了验证MLCR-CSC作为STATCOM换流器在$5 0 0 \mathrm { k V }$ 及以上电网中应用的可行性。双组MLCR-CSC 构成高压大功率 STATCOM，如图1所示。

每组MLCR-CSC由传统12脉波换流器和重注入电路组成。12脉波换流器的连接变压器由一次侧和两个线圈比分别为 $K _ { \mathfrak { n } } : 1$ （Y联结）、 $K _ { \mathfrak { n } } : \sqrt { 3 }$ (D 联结）的二次侧组成。为了分析方便，本文选取注入电流电平数为5。重注入电路由5组反并联自关断器件和2台重注入变压器组成。 $\mathrm { V T } _ { \mathrm { Y 1 } } \sim \mathrm { V T } _ { \mathrm { Y 6 } }$ 为Y桥组主桥晶闸管开关； $\mathrm { V T } _ { \mathrm { D 1 } } \sim \mathrm { V T } _ { \mathrm { D 6 } }$ 为 $\mathrm { ~ D ~ }$ 桥组主桥晶闸管开关； $I _ { \mathrm { a Y } }$ 为主变压器二次侧 $\mathrm { \Delta Y }$ 桥A相绕组电流， $I _ { \mathrm { c a D } }$ 为主变压器二次侧D桥A相绕组电流； $I _ { \mathrm { A } }$ ， $I _ { \mathrm { B } }$ 、 $I _ { \mathrm { C } }$ 为电网1的三相电流； $\mathrm { V T } _ { \mathrm { p j 1 } } \sim \mathrm { V T } _ { \mathrm { n j 4 } }$ 将直流电流分配到多抽头重注入变压器； $I _ { \mathrm { i n j } }$ 为注入电流； $C _ { \mathrm { i } }$ 、 $C _ { \mathrm { j } }$ 分别为直流阻断电容； $\boldsymbol { I } _ { \mathrm { d c } }$ 为直流电流； $L _ { \mathrm { m } }$ 为平波电抗器。

# 2.2无功补偿工作原理

在实际应用中，MLCR-CSC将有功功率和无功功率或者交流输出电流的有功电流和无功电流作为控制变量，由于主电路使用晶闸管，控制变量只有功率角 $\theta$ ，为了使换流器在四象限运行，功率角需在 $\pm 1 8 0 ^ { \circ }$ 范围内变化，所以MLCR-CSC是一个强非线性系统。当MLCR-CSC作为STATCOM时，有功功率和无功功率控制如图2所示。

![](images/3528f7cf3608d1818422926be83968da68515fc55ff278274583b2319a369e52.jpg)  
图1 电流型STATCOM拓扑结构  
Fig.1 Current-source STATCOM configuration

![](images/414b7a322ad7c13c5bd443fb522ffff3d4109e2c717dac1fa938ae7376bc2541.jpg)  
图2MLCR-CSC有功功率和无功功率控制图 Fig.2Block diagram of reactive power and current

图2中， $k _ { \mathrm { u } }$ ， $k _ { \mathrm { i } }$ 为交直流电压、电流转换系数；$U _ { \mathrm { s R M S } }$ ， $I _ { \mathrm { s R M S } }$ 为变压器一次侧相电压电流有效值； $R$ 为直流等效电阻。采用 $\pm 9 0 ^ { \circ } \pm \Delta \theta$ 功率角控制直流侧电流 $\boldsymbol { I } _ { \mathrm { d c } }$ ， $\Delta \theta$ 变化范围很小，在工作点处近似线性变化，这样无功功率的变化由 $\Delta \theta$ 决定， $\pm 9 0 ^ { \circ }$ 的控制角强迫MLCR-CSC工作在感性或者容性状态。但是，单相直流电流的增减幅度不仅由功率角的变化量 $\Delta \theta$ 决定，还和功率角的正负极性有关。

在 $+ 9 0 ^ { \circ }$ 附近，有

$$
\begin{array} { r l } & { \mathrm { d } U _ { \mathrm { d c } } = \mathrm { d } [ k _ { \mathrm { u } } U _ { \mathrm { s R M s } } \cos { ( 9 0 ^ { \circ } + \Delta \theta ) } ] } \\ & { \qquad = - k _ { \mathrm { u } } U _ { \mathrm { s R M s } } ( \sin { \Delta \theta } ) } \\ & { \qquad \approx - k _ { \mathrm { u } } U _ { \mathrm { s R M s } } \mathrm { d } \Delta \theta } \end{array}
$$

在 $- 9 0 ^ { \circ }$ 附近，有

$$
\begin{array} { r l } & { \mathrm { d } U _ { \mathrm { d c } } = \mathrm { d } [ k _ { \mathrm { u } } U _ { \mathrm { s R M S } } \cos { ( - 9 0 ^ { \circ } + \Delta \theta ) } ] } \\ & { \qquad = k _ { \mathrm { u } } U _ { \mathrm { s R M S } } ( \sin { \Delta \theta } ) } \\ & { \qquad \approx k _ { \mathrm { u } } U _ { \mathrm { s R M S } } \mathrm { d } \Delta \theta } \end{array}
$$

为了控制直流电流，在 $\pm 9 0 ^ { \circ }$ 附近功率角的增量 $\Delta \theta$ 必须与换流器工作状态协调，以产生正确的$\Delta \theta$ 变化极性，才能控制无功功率的发出和吸收，满足设备自身损耗的有功功率的流向。

# 3 直接电流控制设计

图3为STATCOM逻辑控制示意图，以交流系统所需的无功功率作为初始输入值，转化为交流侧电流无功分量作为参考指令和无功需求性质的判断。交流侧电流无功分量作为闭环控制系统的直接控制指令，确保MLCR-CSC的直接电流控制；MLCR-CSC的触发脉冲时序与交流电网电压信号同步，从而保证了MLCR-CSC的阶梯形电流与交流电流的同步[15-17]

![](images/cf6e79f81b69da31c8dcc1126ac1a640666e79be2795f7d6635fe3cf12222de8.jpg)  
图3电流型STATCOM逻辑控制示意图  
Fig.3 Current-source STATCOMlogic control block   
图4MLCR-CSC电流合成仿真图  
Fig.4MLCR-CSC current synthetic simulation diagram

通过测量交流三相电压和电流，计算得到实际的交流侧电流无功分量，它与交流侧电流无功分量参考值的差值经过PI控制器产生所需的相角控制指令。通过对交流侧电流无功分量的判断，得到电网所需感性或者容性无功功率，实现对直流侧电流、输出电压的控制，从而得到所需的无功功率值。当检测到电网非对称故障时，STATCOM全功率运行；当直流侧电流 $\boldsymbol { I } _ { \mathrm { d c } }$ 工作在非正常范围时，经过延时发出封锁触发同步信号和锁定重注入脉冲触发时序超前或者滞后 $3 0 ^ { \circ }$ ，使换流器工作在电流过零条件下，从而退出无功补偿。

# 4 仿真验证

以11电平电流作为研究对象进行电流型STATCOM仿真。主要工作包括：电流过零关断验证；网侧输出电流波形THD含量，以及不同零电流脉冲宽度对谐波和幅值的影响；电网对称性扰动和不对称性故障情况下STATCOM的响应。

# 4.1零电流产生与谐波消除

图4为主电路触发角度为 $0 ^ { \circ }$ 的仿真波形，在$0 . 1 7 \mathrm { s }$ ， $I _ { \mathrm { B Y } }$ 幅值达到最大，换流器 $I _ { \mathrm { B D } }$ 的幅值为零，为D 桥换相提供零电流关断（Zero Current Switching,ZCS）条件；在0.175s时， $I _ { \mathrm { B D } }$ 幅值最大，上部换流器 $I _ { \mathrm { B Y } }$ 的幅值为零，为Y桥换相提供了ZCS 条件。

100   
A 50   
AD 0 0.160 0.1620.164 0.166 0.168 0.170 0.172 0.174 0.176 0.178 0.180 t/s (a）MLCR-CSC 换流器 Y桥直流输出电流 $I _ { \mathrm { B Y } }$ 100   
A 合八人 50 0.160 0.162 0.164 0.166 0.168 0.170 0.172 0.174 0.176 0.178 0.180 t/s (b）MLCR-CSC 换流器D 桥直流输出电流 $I _ { \mathrm { D Y } }$ （204号 46   
4 44 42 0.1600.162 0.164 0.166 0.168 0.170 0.172 0.174 0.176 0.178 0.180 t/s （c）MLCR-CSC 换流器直流侧电流 $I _ { \mathrm { d c } }$ 100   
4 -100 0.160 0.162 0.164 0.166 0.168 0.170 0.172 0.174 0.176 0.178 0.180 t/s (d）主变压器二次侧Y桥A相绕组交流电流 $I _ { \mathrm { a Y } }$ 100 【 100 0.160 0.162 0.164 0.166 0.168 0.170 0.172 0.174 0.176 0.178 0.180 t/s (e）主变压器二次侧D桥A相绕组交流电流 $I _ { \mathrm { c a D } }$ （204 100 .\*.\*\*\*\*   
4 0 -100 0.160 0.162 0.164 0.166 0.1680.170 0.172 0.174 0.1760.178 0.180 t/s (f）换流器网侧A相电流 $I _ { \mathrm { A } }$

重注入电流的频率为电网基波频率的6倍；在每个基波周期提供6个电流过零点；主变压器Y接换流器的直流电流 $I _ { \mathrm { B Y } }$ 输出呈现11电平，主变压器D接换流器的直流电流 $I _ { \mathrm { B D } }$ 输出呈现11电平。主变压器二次侧Y接换流器A相交流输出电流 $I _ { \mathrm { a Y } }$ 导通$1 2 0 ^ { \circ }$ ，二次侧D接换流器A相交流输出电流 $I _ { \mathrm { a D } }$ 导通 $1 2 0 ^ { \circ }$ 。二次侧Y接和D接经过主变压器耦合，得到变压器一次侧A相多电平电流，近似于正弦波。

# 4.2最优零电流脉宽

在仿真模型中，重注入电流波形采用一个线性上升和下降的三角波进行调制，重注入电路门极可控器件的开关脉冲宽度以均分（等高等宽）为基准，并且在基波频率周期内提供6个电流过零点。由于重注入电路的开关与网侧电压同步信号没有关系，设定11电平重注入零电流零脉宽基准分别为(1/11，3/11，5/11，7/11，9/11)，设置零电流脉冲宽度为基准值的 $0 . 8 5 0 \sim 1 . 2 0 0$ 倍，得到谐波含量、电流幅值与零电流脉宽基准倍数和主电路触发角度的数据。

![](images/0d446f1ae9d3ebb4bda8637565eeaff072094cc5e8f62886ac635a15fee298be.jpg)  
图5 网侧电流THD与触发角度和零脉宽倍数的关系 Fig.5AC-side current THD relationship between trigger angle and the zero pulse width ratio

![](images/ba4929deee0f61679b5e93490333591778f6a39139935af3aada04822fdb6511.jpg)  
图6网侧电流幅值与触发角度和零脉宽倍数的关系 Fig.6AC-side current amplitude relationship between trigger angle and the zero pulse width ratio

# 4.3输电网电压扰动时的无功补偿特性

图7和图8是在电网电压有较大波动情况下的仿真结果。当 $t = 0 . 1 { \mathrm { s } }$ 时，电网电压为 $0 . 9 5 \mathrm { { p u } }$ STATCOM检测到电网电压降低，发出 $0 . 4 8 \mathrm { p u }$ 无功电流，电流相位超前电压，并网点电压吸收STATCOM无功功率51.4Mvar。当 $t = 0 . 1 5 \mathrm { s }$ 时，电网电压为 $0 . 7 4 \mathrm { p u }$ ，发出lpu无功电流，电流相位超前电压，并网点电压吸收STATCOM无功功率105.4Mvar。当 $t = 0 . 2 \mathrm { s }$ 时，电网电压为 $1 . 0 2 \mathrm { p u }$ ，电流型STATCOM检测到电网电压升高，吸收$0 . 7 8 \mathrm { p u }$ 无功电流，电流滞后电压，并网点电压向STATCOM发出无功功率86.7Mvar。当 $t = 0 . 2 5 \mathrm { s }$ 时，电网电压为 $1 . 1 8 \mathrm { { p u } }$ ，STATCOM检测到电网电压升高，吸收1pu无功电流，电流滞后电压，并网点电压向STATCOM发出无功功率130.2Mvar。整个过程电流型STATCOM直流侧电流保持恒定，它从电网吸收或者回馈少量有功功率满足自身损耗。

![](images/112d577d379da95b28521c1058052569f0df00e5504a6c56d8508a94dd8e729a.jpg)  
图7并网点电压扰动时STATCOM无功控制仿真 Fig.7STATCOM reactive power control simulation with disturbance at PCC

# 4.4输电网非对称性电压故障时的无功补偿特性

图9为电网发生单相接地故障的仿真图，当 $t =$ 0.15s时电网A相接地，STATCOM检测到电网故障，通过直接电流控制策略，STATCOM全功率运行，直流侧电流波动较大，A相补偿电流稍大于其他两相。电流 $t = 0 . 2 5 \mathrm { s }$ 时A相接地故障消除,STATCOM恢复待机状态。

![](images/6dd9d164d8b54707bca4b949e6ec058787716f50767cff5ecc13425767c727d5.jpg)  
图8扰动时并网点的电压无功控制仿真

![](images/512a79d442efbfb9fb4786f06b3c5a52c7fc4a33ebc60f4ef737df798475104c.jpg)  
Fig.9AC-side single-phase grounding fault simulation

![](images/1272f86b314e7b2aa62291fd4901579d9d7ed14fedd22a58ff504bcfe23bca3f.jpg)  
图9网侧单相接地故障仿真

图10为电网发生三相接地故障的仿真曲线。当$t = 0 . 1 5 \mathrm { s }$ 时电网三相接地，STATCOM检测到电网故障，通过直接电流控制策略，STATCOM全功率运行，提供三相补偿电流，直流侧电流下降趋势明显，直流侧电流幅值低于设定值，STATCOM进入零电流关断条件，直接退出运行。电流 $t = 0 . 2 5 \mathrm { s }$ 时A相接地故障消除，STATCOM迅速恢复待机状态。

![](images/1e5c3ce28213adc060dbfbc17b24f1aadeb52291b168e7cd4b78a181a2bbaeb1.jpg)  
Fig.8PCC voltage and reactive power control simulation with disturbance   
图10 网侧三相相接地故障仿真  
Fig.10AC-side three-phase grounding fault simulation

# 5 结束语

（1）11电平MLCR-CSC主电路晶闸管开关频率是 $5 0 \mathrm { { H z } }$ ，重注入电路的门极可关断功率开关频率是 $4 5 0 ~ \mathrm { H z }$ ，降低了功率器件的损耗；实现了晶闸管

柔性关断特性，基波周期内实现零电流关断；实现  
谐波消除，MLCR-CSC的谐波含量并没有随着触发  
角度的变化而变化；实现消除谐波和高功率因数运  
行，简化了设备的整体结构。(2）零电流脉冲宽度在标准脉宽 $0 . 8 5 \sim 1 . 2 \$ 倍  
之间任意调整，并且 $\mathrm { T H D } < 4 \%$ ；当为标准脉宽的  
1.1倍时，THD最低为 $1 . 8 3 \%$ ，为物理平台搭建提  
供了有效的理论数据依据。（3）STATCOM在输电网电压扰动时，能实时  
调整电压等级，当电网电压降低时，支撑电网电压  
升高到额定等级；当电网电压升高时，将电网电压  
降低到额定等级；非对称性故障时，全功率补偿，  
提供电压支撑，响应迅速。（4）电流型STATCOM拓扑结构简单、无耦合  
易扩展，在大容量输电网网络中，通过简单的并联，  
可满足高压或者超高压输电系统的无功功率需求。今后的研究工作可关注两个方面：即电流型  
STATCOM有功功率和无功功率独立控制的研究，  
以及计划研制 $\mathrm { 1 M V \cdot A }$ 容量的MLCR-CSC 实验平  
台，验证拓扑结构和控制策略的可行性。

# 参考文献

[1] 王雅婷，郑彬，申洪，等．西北新能源外送系统 多FACTS协调控制方法[J]．中国电机工程学报, 2013，33(34):162-170. Wang Yating,Zheng Bin,Shen Hong,et al.A coordinated control method of multiple FACTS on the norwest new energy-delivery system[J] Proceedings of the CSEE,2013,33(34):162-170.   
[2] 马为民，吴方劫，杨一鸣，等．柔性直流输电技 术的现状及应用前景分析[J]．高电压技术，2014, 40(8):2429-2439. Ma Weimin,Wu Fangjie,Yang Yiming,et al. Flexible HVDC transmission technology's today and tomorrow[J].High Voltage Engineering,2014,40(8): 2429-2439.   
[3] 饶宏，陈俊，许树楷，等．输电系统用STATCOM 多电平主回路方案选择[J]．电力系统自动化， 2013，37(13):83-87. Rao Hong,Chen Jun,Xu Shukai,et al. Selection of multilevel main circuit schemes of STATCOM for transmission system[J].Automation of Electric Power Systems,2013,37(13):83-87.   
[4] 杨晓峰，范文宝，王晓鹏，等．基于模块组合多 电平变换器的 STATCOM及其控制[J]．电工技术 学报，2011，26(8)：7-13. Yang Xiaofeng, Fan Wenbao, Wang Xiaopeng, et al. Static synchronous compensator based on modular multilevel convertor based STATCOM and its control[J]. Proceedings of the CSEE,2011, 26(8): 7-13.   
[5] 黄伟雄，胡广振，王永源，等．南方电网 （20 $3 5 \mathrm { k V } \pm 2 0 0 \mathrm { M v a r }$ 链式 STATCOM现场试运行[J]. 电力系统自动化，2013，37(19)：122-131. Huang Weixiong, Hu Guangzhen, Wang Yongyuan, et al. On-side commission of $3 5 \mathrm { k V } \pm 2 0 0 \mathrm { M }$ var cascade STATCOM in China southeast power gride[J]. Automation of Electric Power Systems,2013,37(19): 122-131.   
[6] 黄伟雄，刘锦宁，王永源，等． $3 5 \mathrm { k V } \pm 2 0 0 \$ Mvar STATCOM系统总体设计[J]．电力系统自动化, 2013，37(10):136-142. Huang Weixiong, Liu Jinning,Wang Yongyuan, et al. Overall design of $3 5 \mathrm { k V } \pm 2 0 0 \mathrm { M } ^ { \prime }$ varSTATCOM system[J]. Automation of Electric Power Systems, 2013,37(10): 136-142.   
[7]张勇军，姚智聪，王京，等．一种级联H桥型静 止无功发生器电容电压平衡控制策略[J]．中国电 机工程学报，2014，34(27)：4621-4628. Zhang Yongjun, Yao Zhicong, Wang Jing,et al. A direct current capacitor voltage balancing control strategy for H-bridge cascaded static var generator[J]. Proceedings of the CSEE,2014, 34(27): 4621-4628.   
[8] 杜少通，杨擎，汪山林，等．五电平H桥级联型 STATCOM脉冲轮换控制策略研究[J]．电力系统 保护与控制，2014，42(21)：17-22. Du Shaotong, Yang Qing,Wang Shanlin, et al. Research on pulse rotation control strategy for 5-level cascaded H-bridge STATCOM[J]. Power System Protection and Control, 2014, 42(21): 17-22.   
[9] Enrique Acha, Behzad Kazemtabrizi. A new STATCOM model for power flows using the NewtonRaphson method[J]. IEEE Transactions on Power Delivery,2013,28(3): 2455-2465.   
[10]Takayuki Kawaguchi, Tsukasa Sakazaki, Takanori Isobe, et al. Off shore-wind-farm configuration using diode rectifier with MERS in current link topology[J].IEEE Transactions on Industrial Electronics,2013,60(7): 2930-2937.   
[11] GimenezR B,Villalba SA,D'DerleeJR,et al. Diode-based HVDC link for the connection of large offshore wind farms[J]. IEEE Trans.on Energy Convers.,2011,26(2):615-626.   
[12] Baird JF,Arrilaga J.Harmonic reduction in dcripple reinjection[J]. IEE Proceedings,Generation, Transmission and Distribution,1980,127(5):294- 303.   
[13] Bhaba Das,Neville Watson,Yonghe Liu.DC ripple reinjection:a review[J].International Journal of Emerging Electric Power Systems,2011,12(5):15- 23.   
[14] ArrillagaJ,LiuYH,PereraLB,etal.Acurrent reinjection scheme that adds self-commutation and pulse multiplication to the thyristor converter[J]. IEEE Transactions on Power Delivery,20o6,21(3): 1593-1599.   
[15] Wang Y Z,Cheng D Z,Li C W.Dissipative Hamiltonian realization and energy-based L2- disturbance attenuation control of multi-machine power systems[J].IEEE Transactions on Automatic Control,2003,48(8): 1428-1433.   
[16] 阎博，汪可友，MariesaLCROW，等．UPFC状 态反馈精确线性化潮流控制策略[J]．中国电机工 程学报，2012，32(19)：42-48. Yan Bo,Wang Keyou,Mariesa L CROW,et al. UPFC power flow control strategy based on exact linearization via feedback[J].Proceedings of the CSEE,2012,32(19):42-48.   
[17] 查晓明，张茂松，孙建军．链式D-STATCOM 建 模及其状态反馈精确线性化解耦控制[J]．中国电 机工程学报，2010，30(28)：107-113. Zha Xiaoming,Zhang Maosong,Sun Jianju. Modeling of cascade D-STATCOM with decoupled state variable feedback linearization control[J]. Proceedings of the CSEE,2010,30(28):107-113.

# （上接第20页）

[4] Marioni,O'Handley,et al.Pulsed magnetic field induced actuation of Ni-Mn-Ga single crystals[J]. Applied Physics Letters,2003,83(19): 3966-3968.   
[5] 王凤翔，张庆新，吴新杰，等．磁控形状记忆合 金蠕动型直线电机研究[J]．中国电机工程学报, 2004，24(7):140-144. Wang Fengxiang, Zhang Qingxin,Wu Xinjie, et al. Research of magnetic control shape memory alloy creep type linear motor[J].Proceedings of the CSEE, 2004,24(7): 140-144.   
[6] Suorsa I,Tellinen J,Ullakko K,et al.Voltage generation induced by mechanical straining in magnetic shape memory materials[J]. Journal of Applied Physics,2004, 95(12): 8054-8058.   
[7] Karaman I, Basaran B,et al. Energy harvesting using martensite variant reorientation mechanism in NiMnGa shape memory alloy[J].Applied.Physics.Letter., 2007,90(17): 2505-2507.   
[8] 鲁军，李敏，王凤翔．基于MSMA逆特性的振动 传感器理论及实验研究[J]．电工技术学报，2014, 21(5):233-238. Lu Jun,Li Min,Wang Fengxiang.Theoretical and experimental study on vibration sensor based on MSMA inverse characteristics[J].Transactions of China Electrotechnical Society,2014,29(5):233- 238.   
[9] Kiefer B,Lagoudas D C.Magnetic field-induced martensitic variant reorientation in magnetic shape memory alloys[J].Philosophy Magazine,2005, 85(35): 4289-4329.   
[10] Haldar K,Kiefer B,et al.Finite element analysis of the demagnetization effect and stress inhomogeneities in magnetic shape memory alloy samples[J]. Philosophy Magazine,2011,91(32): 4126-4157.   
[11] Sarawate N N,Dapino MJ.Magnetic-field- induced stress and magnetization in mechanically blocked NiMn-Ga[J]. Journal of Applied Physics,2008,103(8): 839-842.