# 微型光伏储能系统的并网调峰控制研究

朴政国 张明

(北方工业大学北京电动车辆协同创新中心北京100144)

![](images/9476723f87f24272f983c696ef9cfa6f4b4ebc56f1cacf8f1f8353d7e9e74ea3.jpg)

朴政国男 1979年生，博士，讲师，研究方向光伏发电系统设计、光伏逆变器和开关电源等电力电子变换技术相关领域。

摘要：本文针对新能源发电中的分布式光伏并网系统进行研究，主要研究了并网发电系统的核心逆变器部分，设计了一种新型的含储能装置的两级式并网逆变器；并在新型并网逆变器的设计基础上，针对配电网负荷需求变化引起的电力峰谷问题，进一步研究了含储能装置的分布式光伏并网系统对配电网削峰填谷的控制策略；提出基于并网点电压补偿的调峰控制策略；最终完成了整个系统的参数设计，并分别通过软件仿真和硬件实验平台验证了所设计的两级式并网逆变器的合理性；提升了光伏并网系统的运行效率，有效解决了调峰和稳定并网运行问题，为分布式光伏并网发电系统的设计提供了一种技术参考。

关键词：分布式光伏 反激逆变 软开关 储能装置 负荷调峰中图分类号：TM464

# Research of Grid-Connected Peak Shaving Control for Micro Photovoltaic Energy Storage System

![](images/e9e54c5710d855bbcb0bed6d3ebbea4844f9a7a535960247ff0c7f0ac95062f4.jpg)

Piao Zhengguo Zhang Ming (Collaborative Innovation Center of Electric Vehicles in Beijing North China University of TechnologyBeijing100144 China)

张明男1988年生，硕士研究生，研究方向为分布式光伏发电，电力电子。

Abstract: Aiming at the new energy power generation of distributed photovoltaic (PV) grid system, this paper mainly studied the core of the inverter part in grid connected power generation system. Design a new kind of two-stage grid connected inverter with energy storage device.In addition, aiming at the problem of electricity peak valley when the distribution network load demand change, studies a peak shaving control strategy for the distributed grid-connected PV system with energy storage devices. Present a peak load shaving control strategy based on Point of common coupling voltage compensation. Finally,the parameter design of the whole system is finished,and through software simulation and hardware experiment, the rationality of the two-stage grid connected inverter design is verified. Improve the operation efficiency of PV system, effectively solve the problem of peak load shaving and system stability. Provides technical reference for the design of the distributed photovoltaic grid power system.

Keywords: Distributed photovoltaic,flyback inverter, soft switch, battery energy storage system, peak load shaving

# 1 引言

光伏发电作为新能源发电的一个重要组成部分，近年来发展势头十分迅猛。其中分布式光伏发电具有灵活高效的应用特点，成为一种新型的发展前景广阔的能源利用方式，建设和应用范围日益广泛，是新能源并网发电的一个研究热点。逆变器作为并网发电中电能转换的核心部件，是光伏发电的一个重点研究方向，目前逆变器的研究设计主要集中在如何提高逆变效率和系统的安全稳定性运行上，关键技术主要有逆变器拓扑结构优化设计、电路不同工作模式对系统高效运行的影响、软开关技术以及控制算法的优化等[1-3]。

由于太阳能是一种间歇性能源，光伏发电系统的输出功率具有不稳定、不可预测性，这就会影响电力系统的电能质量和安全稳定运行。另外，随着用户负荷不断增加，以及负荷的波动性，会导致电力负荷峰谷差大的问题[4]。为保证电网稳定运行和供用电的平衡，须采取相应的削峰填谷措施。

蓄电池储能系统（Battery Energy Storage System,BESS）具有储能密度大、安装建设灵活且控制响应速度快等优点[5]，在新能源并网系统中有很大的应用空间[6-8]，储能系统不仅可以用于平抑光伏、风电等间歇性能源的发电功率波动问题[9-10]，同时可以方便地从负荷侧对电网的峰谷进行调节。通过BESS进行调峰控制，不仅可以减少电网侧发、输、配电设备的投资，提高设备利用率，还可以减小线路损耗，获得可观的经济效益，是解决电力峰谷问题的有效途径之一[]。

本文设计了一种新型的两级式微型逆变拓扑结构，蓄电池并接于中间直流母线。前级Boost升压电路控制光伏电池板的输出，实现最大功率点跟踪控制，提高太阳能利用率。后级为反激逆变部分，反激拓扑中加入有源钳位电路，实现主开关管的软开关，减小开关损耗，系统控制策略上实现对蓄电池的充放电控制及并网逆变控制，使逆变器始终工作在高功率状态，提高并网系统的运行效率，实现电网调峰和稳定并网运行。

# 2 光伏并网系统结构及控制策略

为实现光伏并网系统稳定高效运行，设计了额定功率为200W的微型光伏逆变器。两级式微型逆变系统拓扑结构如图1所示。

两级式微型逆变器由Boost升压电路、交错反激电路、有源钳位电路、全桥逆变电路以及LC滤波电路组成。Boost升压电路的输出接蓄电池储能装置，通过对蓄电池的充放电控制，实现配电网的调峰功能。两级式微型逆变器设计参数见下表。

![](images/649c4ea818222de3cd96388c7a6adbef2d150adaf41507a15266f5310ed153e2.jpg)  
图1光伏并网系统拓扑结构  
Fig.1 Grid-connected PV system topological structure

# 表两级式微型逆变器参数

Tab. Two-staged of micro inverter parameters   

<html><body><table><tr><td></td><td>参数类别</td><td>取值范围</td><td>额定值</td></tr><tr><td rowspan="3">Boost电路</td><td>光伏电池板电压Vpv/V</td><td>20～50</td><td>36</td></tr><tr><td>最大功率点电压VMPP/V</td><td>25~45</td><td>36</td></tr><tr><td>Boost电压VBoostV</td><td>46～60</td><td>48</td></tr><tr><td rowspan="5">反激逆变电路</td><td>逆变输出电压Vout/V</td><td>210～242</td><td>220</td></tr><tr><td>并网输出频率four/Hz</td><td>49.3~ 50.7</td><td>50</td></tr><tr><td>额定输出功率Pou/W</td><td>1</td><td>200</td></tr><tr><td>谐波含量 THD(%)</td><td>4.5<</td><td>1</td></tr><tr><td>逆变效率n(%)</td><td>1</td><td>93</td></tr><tr><td rowspan="2">蓄电池</td><td>蓄电池电压Vbat/V</td><td>1</td><td>48</td></tr><tr><td>蓄电池容量C/A·h</td><td>一</td><td>20</td></tr></table></body></html>

反激式逆变拓扑结构优点突出[12]，且同时采用两路反激变压器交错并联的电路拓扑[13-14]，使得在同样电压等级下输出的功率增大一倍，提高效率，保证光伏并网逆变系统高效地输出高质量、低谐波、与电网同频同相的正弦并网电流。

两级式反激逆变器将前级Boost电路输出的直流经过高频变压器转换成准正弦的半波电流，再通过全桥逆变以及滤波，最终输出与电网同频同相的交流电馈入电网。

反激逆变器工作在连续电流模式 (CCM)，在CCM模式下，由开关周期励磁电感伏秒平衡可得反激逆变器输出电压 $V _ { \mathrm { o u t } }$ 和直流侧输入电压 $V _ { \mathrm { i n } }$ 关系为

$$
V _ { \mathrm { o u t } } = n { \frac { D } { 1 - D } } V _ { \mathrm { i n } } 
$$

式中， $n = N _ { \mathrm { s } } / N _ { \mathrm { p } }$ 为反激变压器二次侧和一次侧的匝数之比； $D$ 为稳态占空比。逆变器输出电压 $V _ { \mathrm { o u t } }$ 为滤波电路两端电压 $Z _ { \mathrm { L } } i _ { \mathrm { a c } }$ 与电网电压 $V _ { \mathrm { g r i d } }$ 之和，故稳态占空比 $D$ 为

$$
D = \frac { { { V _ { \mathrm { g r i d } } \left| { \sin \theta } \right| + { Z _ { \mathrm { L } } } { i _ { \mathrm { a c } } } } } } { { { V _ { \mathrm { g r i d } } \left| { \sin \theta } \right| + { Z _ { \mathrm { L } } } { i _ { \mathrm { a c } } } + n { V _ { \mathrm { i n } } } } } }
$$

式中， $i _ { \mathrm { a c } }$ 为并网电流； $Z _ { \mathrm { L } }$ 为滤波器的阻抗。式 (2)可分为两部分，分别用 $D _ { \mathrm { f e e d } }$ 和 $\Delta d$ 表示。

$$
D = D _ { \mathrm { f e e d } } + \Delta d
$$

$$
D _ { \mathrm { f e e d } } = \frac { V _ { \mathrm { g r i d } } \left| \sin \theta \right| } { V _ { \mathrm { g r i d } } \left| \sin \theta \right| + Z _ { \mathrm { L } } i _ { \mathrm { a c } } + n V _ { \mathrm { i n } } }
$$

$$
\Delta d = \frac { Z _ { \mathrm { L } } i _ { \mathrm { a c } } } { V _ { \mathrm { g r i d } } \left| \sin \theta \right| + Z _ { \mathrm { L } } i _ { \mathrm { a c } } + n V _ { \mathrm { i n } } }
$$

由于滤波电路端电压 $Z _ { \mathrm { L } } i _ { \mathrm { a c } }$ 远小于电网电压，故$Z _ { \mathrm { L } } i _ { \mathrm { a c } }$ 可忽略，则 $D _ { \mathrm { f e e d } }$ 可表达为

$$
D _ { \mathrm { f e e d } } = \frac { V _ { \mathrm { g r i d } } \left| \sin \theta \right| } { V _ { \mathrm { g r i d } } \left| \sin \theta \right| + n V _ { \mathrm { i n } } }
$$

加入前馈补偿的优点在于，通过电压前馈补偿，可以减少电网扰动对控制系统的影响，提高控制系统的稳定性和精度。系统控制框图如图2所示。

![](images/fe893b7e18ba4d9fb4a9734d2f8000c123b6ae6f7a18d90961225b8c74635968.jpg)  
图2逆变系统控制结构框图

图2中，电流参考幅值 $I _ { \mathrm { r e f } }$ 与锁相环PLL得到的电网相位信息相结合，得到并网电流参考值 $\boldsymbol { I } _ { \mathrm { a c } } ^ { * }$ 经过PI调节，产生动态占空比调节信号 $\Delta d$ ，再叠加电压前馈补偿 $D _ { \mathrm { f e e d } }$ ，得到稳态占空比 $D$ ，最终得出的调制波再进行高频调制，得到开关管的驱动信号，从而控制电路工作。

# 3 仿真分析

通过对两级式微型逆变器的拓扑结构、工作原理分析，在参数设计和控制策略分析的基础上，利用Matlab软件对系统进行建模，通过模型的仿真来验证设计的合理性。

本文设计的反激逆变电路工作在电流连续模式下，反激输出侧的电流如图3所示，反激逆变输出准正弦半波电流，通过对准正弦半波电流进行区间放大可以看出，电路工作在CCM模式。

![](images/16e4ddbf92636108e0f40969a513dd62e0098b31f6bda1bc3c851604af9b84c2.jpg)  
Fig.2 Inverter control system structure Diagram   
图3反激逆变输出准正弦半波电流波形  
Fig.3The flyback inverter output quasi sine half-wave current waveform

上文提到，为提高光伏系统逆变效率，反激拓扑结构中加入有源钳位电路[15]，实现了主开关管的零电压开通，同时消除高频变压器漏感与主开关管寄生电容间产成的电压尖峰，钳位电路可以吸收回馈漏感能量，提高了逆变效率。

图4为互补型有源钳位软开关实现的仿真工作波形，其中 $V _ { \mathrm { d s } }$ 为主开关管电压， $I _ { \mathrm { p } }$ 为主开关管电流，钳位管驱动信号进行了反向变换。在主开关管开通时刻，其两端电压为零，实现了零电压开通。

![](images/5282814627d6c0af80c385ed29d199b05058d59b35b960e650de2dedeb70b341.jpg)  
图4互补型有源钳位软开关波形

最终，系统并网运行的仿真波形如图5所示，图5中两路波形分别为电网电压及并网电流，由于微型逆变器额定功率为 $2 0 0 \mathrm { W }$ ，并网额定电流为0.91A，为了方便与电网电压进行对比，对电流信号做了50 倍放大。

![](images/3e9de3e756a520393f34a9ebcae34467d887c7002218435156d01a565b0801f1.jpg)  
Fig.4Complementary active clamp soft switching waveforms   
图5并网电流波形  
Fig.5Grid-connected current waveform

由以上各个部分以及并网运行的仿真波形可以看出，仿真结果与理论设计一致，达到了预期的要求，从仿真角度证明了所设计逆变器的合理性及控制方式的正确性。

# 4 调峰控制策略研究

光伏发电系统接入配电网实现并网运行[16-17],其等效电路模型如图6所示。图中， $U _ { \mathrm { s } }$ 为配电网电压，通常认为配电网是一个无穷大系统，电压幅值基本不变； $Z = R + \mathrm { j } X$ 为配电网线路阻抗，其中 $R$ 为电阻分量， $X$ 为电抗分量； $P$ 与 $\varrho$ 分别为电网给本地负荷传输的有功功率和无功功率； $U _ { \mathrm { P C C } }$ 为并网点电压（PointofCommon Coupling，PCC）， $P _ { \mathrm { ~ L ~ } }$ 与 $\varrho _ { \mathrm { L } }$ 分别为PCC本地负荷的有功功率与无功功率； $P _ { \mathrm { G } }$ 为光伏发电系统输出的有功功率，一般光伏发电系统控制功率因数为1，只输出有功。

![](images/16e6a18242e2cc60b441950f7e8dd2009d005c245aecdab80dfd706024db681c.jpg)  
图6光伏发电系统并网等效电路  
Fig.6Grid-connected PV System equivalent circuit

由图6光伏发电系统并网的等效电路可知，配电网与光伏系统并网点之间传输功率为

$$
S = P + \mathrm { j } Q
$$

因此，配电网母线电压 $U _ { \mathrm { s } }$ 与PCC电压 $U _ { \mathrm { P C C } }$ 之间的电压差为

$$
\Delta U = ( R + \mathrm { j } X ) \Bigg ( \frac { P + \mathrm { j } Q } { U _ { \mathrm { P C C } } } \Bigg ) ^ { * }
$$

式中，\*表示取共轭。设 $U _ { \mathrm { P C C } }$ 为参考电压，式（8)可写为

$$
\Delta U = \frac { R P + X Q } { U _ { \mathrm { { P C C } } } } + \mathrm { j } \frac { X P - R Q } { U _ { \mathrm { { P C C } } } }
$$

式中， $P = - P _ { \mathrm { G } } + P _ { \mathrm { L } }$ ： ${ \mathcal { Q } } = - { \mathcal { Q } } _ { \mathrm { c } } + { \mathcal { Q } } _ { \mathrm { L } }$ 。由于线路阻抗中电阻分量与电抗分量相当，式（9）中虚部远小于实部，可忽略不计，由此可以得到

$$
U _ { \mathrm { { P C C } } } \approx U _ { \mathrm { { s } } } + \frac { R ( P _ { \mathrm { { G } } } - P _ { \mathrm { { L } } } ) } { U _ { \mathrm { { P C C } } } } + \frac { X ( Q _ { \mathrm { { G } } } - Q _ { \mathrm { { L } } } ) } { U _ { \mathrm { { P C C } } } }
$$

分布式电源接入配电网后，系统潮流会出现以下情况： $\textcircled{1}$ 当分布式电源（Distributed EnergyResources，DER）出力大于本地负荷需求时，其出力会流向配电网参与潮流分配； $\textcircled{2}$ 当DER出力等于本地负荷需求时，由于供需平衡，则配电网无需供电； $\textcircled{3}$ 当DER小于本地负荷需求时，DER出力直接被本地负荷消纳，同时配电网向负荷供电[18]。

当分布式光伏供电功率与负荷需求功率出现供需不匹配时，会出现电力负荷高峰情况，影响电力系统的可靠性，本文关于调峰控制的研究就是针对这一情况。两级式光伏并网系统优点之一就是由于系统中加入BESS，利用BESS的能量存储特性可以对系统出现的峰谷问题进行调节，通过储能装置来缓冲供用电不匹配的状况，这样就会大大提高配电网的供电稳定性。

在系统的控制策略研究上，由式（10）可以看出，由于线路阻抗的存在，光伏发电系统与配电网之间的功率传输会引起PCC电压的变化，通过监测PCC电压，就可以得出电网负荷的变化情况，进而，通过储能装置的充放电来控制PCC电压的稳定就可以保证供用电的平衡，起到调峰作用，调峰控制策略上，采用基于下垂特性的PCC电压控制策略。

逆变单元的输出功率和输出电压幅值特性可表达为

$$
P _ { \mathrm { o u t } } = P _ { \mathrm { r e f } } - m ( U _ { \mathrm { p c c } } - U _ { \mathrm { r e f } } )
$$

式中， $U _ { \mathrm { r e f } }$ 为PCC电压的参考值； $P _ { \mathrm { r e f } }$ 为对应于 $U _ { \mathrm { r e f } }$ 的有功功率率参考值； $\mathbf { \nabla } _ { m }$ 为有功功率下垂系数； $P _ { \mathrm { o u t } }$ 为经过下垂控制得到的系统实际应输出的有功功率。储能装置参与调峰运行的控制如图7所示。

![](images/2bf3f02115b52c643f641d846d51db163f091cd5cbc44e9acaf22aeeda9d46be.jpg)  
图7储能装置调峰控制图

图7中， $\boldsymbol { I } _ { \mathrm { b a t } } ^ { * }$ 为蓄电池充放电参考电流，即系统实际应输出有功功率对应的电流值， $I _ { \mathrm { b a t } }$ 为蓄电池的实时电流， $\boldsymbol { I } _ { \mathrm { r e f } } ^ { * }$ 为逆变器有功电流参考值， $I _ { \mathrm { a c } }$ 为光伏逆变器输出的电流。系统通过控制蓄电池的充放电功率来跟踪 $P _ { \mathrm { o u t } }$ ，使系统供电功率跟随负载功率，达到调峰的目的。

# 5 实验分析

本文通过搭建的两级式光伏并网逆变系统硬件平台，用实验的方法来验证系统设计的可行性。反激微型逆变器以DSP为控制核心，实验平台集电源供电电路、控制电路、反激主电路、高频变压器、驱动采样电路和滤波电路于一体。反激工作频率为高频 $1 0 0 \mathrm { k H z }$ 。软件设计方面，采用基于模型的设计方式。在完成硬件平台和软件设计的情况下，分别对微逆变器各个部分进行了实验验证。

逆变器反激电路工作时的原边主开关管和钳位开关管的驱动信号如图8所示。

![](images/756200ec2df89f80a66f19aa85dbfaa2ba4a165d72d8ce0613b0d5e1abc506df.jpg)  
图8两路交错运行的主开关管与钳位管驱动信号 Fig.8The main switch tube and clamping tube interleaved running driving signal

图中1通道和3通道为两路交错的主开关管的驱动，电压为 $1 2 \mathrm { V }$ ；2通道和4通道是两路钳位开关管的驱动信号。主开关管的驱动与钳位开关管驱动有 $3 0 0 \mathrm { n s }$ 的死区时间。

首先，对有源钳位软开关电路工作的有效性进行验证，本实验对加入有源钳位电路前后的反激主开关管的电压电流波形进行对比。

图9和图10分别为未加钳位电路和加入钳位电路的主开关管两端电压电流波形。由图可以看出，未加有源钳位电路时主管电压尖峰很大，这将对开关管的工作十分不利。而图10中加入钳位电路后，在同样的功率和电压等级下，由于钳位电路的谐振作用，进行了漏感的吸收与回馈，主开管电压尖峰大大减小。谐振过程中吸收主开关管的寄生电容能量，存在一个短时间的负电流，实现了零电压导通。

![](images/85ddac9baaed92d1c4994894d56f394ef8d7c87f017b08b423d5ebe96a6e15d3.jpg)  
Fig.7Energy storage device in peak shaving control block diagram   
图9未加钳位电路时主开关管电压电流波形 Fig.9The main switch tube voltage and current waveform without clamping circuit

![](images/9fedf8793ef708e1009fda8c749b79be075c3329383ee2e50a6afe887e494f12.jpg)  
图10加入钳位电路时主开关管电压电流波形 Fig.10The main switch tube voltage and current waveform with clamping circuit

最终，在验证电路工作状态和钳位电路实现软开关工作的正确性之后，进行了逆变系统的并网实验，图11为电网电压及并网电流波形。

![](images/97c4498b781770330736df1a76e0417b5811e5294a18b7aadbf456402b623a28.jpg)  
图11 电网电压与并网电流波形

Fig.11Grid voltage and grid-connected current waveform并网过程中，并网电流通过调压器并入电网，由图11可以看出，通道1电压为220V，逆变器并网工作会对调压器产生一定的干扰，所以调压器输出电压会出现一些波动。通道3为并网电流，并网电流有效值为0.907A，并网功率为 $2 0 0 \mathrm { W }$ ，达到了额定功率的设计要求，输出的并网电流与电网电压同频同相，实验结果与理论分析一致，达到了预期的效果，验证了所设计的并网逆变器的正确性和可行性。

# 6 结论

本文针对分布式光伏并网发电系统进行研究，主要设计了一种新型的光伏并网逆变器，完成了对整个系统结构和原理的分析说明，并对系统的各个部分进行了分析，逆变器工作模式选择为连续模式，引入了有源钳位软开关技术，消除高频变压器漏感与主开关管寄生电容间产生的电压尖峰，实现了主开关管的零电压的开通，钳位电路可以吸收回馈漏感能量，提高了逆变效率。

在完成微型逆变器的设计基础上，又进一步研究了加入储能装置的分布式光伏并网系统在配电网调峰方面的控制策略及应用。针对配电网负荷需求变化引起的电力峰谷问题，提出了基于并网点电压补偿控制的调峰控制策略，给储能系统用于调峰控制的研究设计提供了参考。

最后对光伏逆变器进行了仿真和实验验证，并且依次分析了各个实验的结果，验证了所选择电路的工作模式，有源钳位电路实现软开关的技术可行性，以及微逆变器并网运行工作的稳定性。

# 参考文献

[1] 张兴，曹仁贤．太阳能光伏并网发电及其逆变控制[M]．北京：机械工业出版社，2010.  
[2] 王晓曦．光伏并网发电系统的研究[D]．哈尔滨：哈尔滨工业大学，2009.  
[3] 何道清，何涛，丁宏林．太阳能光伏发电系统原理与应用技术[M]．北京：化学工业出版社，2012.  
[4] 周林，黄勇，郭珂，等．微电网储能技术研究综述[J]．电力系统保护与控制，2011，39(7)：147-152.Zhou Lin, Huang Yong, Guo Ke, et al. A survey ofenergy storage technology for micro grid[J]. PowerSystem Protection and Control,2011,39(7):147-152.  
[5] 丁明，陈忠，苏建徽，等．可再生能源发电中的电池储能系统综述[J]．电力系统自动化，2013,37(1): 19-26.Ding Ming,Chen Zhong,Su Jianhui,et al.Anoverview of battery energy storage system forrenewable energy generation[J].Automation ofElectric Power Systems,2013,37(1):19-26.  
[6] 高明杰，惠东，高宗和，等．国家风光储输示范工程介绍及其典型运行模式分析[J]．电力系统自动化，2013，37(1)：59-64.Gao Mingjie,Hui Dong,Gao Zonghe,et al.Presentation of national wind photovoltaic energystorage and transmission demonstration project andanalysis of typical operation modes[J].Automationof Electric Power Systems,2013,37(1): 59-64.  
[7] 田军，朱永强，陈彩虹．储能技术在分布式发电中的应用[J]．电气技术，2010(8)：28-32.Tian Jun, Zhu Yongqiang, Chen Caihong.Applicationof energy storage technologies in distributedgeneration[J]. Electrical Engineering,2010(8): 28-32.  
[8] 王成山，武震，李鹏．分布式电能存储技术的应用前景与挑战[J]．电力系统自动化，2014，38(16)：1-8.Wang Chengshan,Wu Zhen,Li Peng.Prospectsand chal lenges of distributed electricity storagetechnology[J].Automation of Electric Power System,2014,38(16): 1-8.  
[9] 林少伯．含光伏电源的微电网储能控制技术研究[D]．北京：华北电力大学，2013.  
[10] 丁明，徐宁舟，毕锐．用于平抑可再生能源功率波动的储能电站建模及评价[J]．电力系统自动化，2011，35(2): 66-72.Ding Ming,Xu Ningzhou,Bi Rui. Modeling ofBESS for smoothing renewable energy outputfluctuations[J].Automation of Electric PowerSystem,2011,35(2): 66-72.  
[11] 张文亮，丘明，来小康．储能技术在电力系统中的应用[J]．电网技术，2008，32(7)：1-9.Zhang Wenliang, Qiu Ming, Lai Xiaokang.Application of energy storage technologies in powergrids[J]. Power System Technology, 2008,32(7):1-9.  
[12] 张锦吉，王小彬，毛行奎．交错反激微功率光伏并网逆变器的设计[J]．电力电子技术，2013,47(4): 43-45.Zhang Jinji, Wang Xiaobin, Mao Xingkui. Designof photovoltaic grid-connected interleaved flybackinverter[J].Power Electronics,2013,47(4):43-45.  
[13]Li Y, Oruganti R.A low cost flyback CCM inverterfor AC module application[J]. IEEE Transactions onPower Electronics,2012,27(3): 1295-1303.  
[14] Zengin S,Boztepe M. Evaluation of two-stage softswitched flyback micro-inverter for photovoltaicapplications[C]. Electrical and ElectronicsEngineering,2013: 92-96.  
[15] 莫琼．有源钳位反激式光伏并网逆变器的研究[D].杭州：浙江大学，2012.  
[16] 黄欣科，王环，王一波，等．光伏发电系统并网点电压升高调整原理及策略[J]．电力系统自动化，2014，38(3): 112-117.Huang Xinke,Wang Huan,Wang Yibo,et al.Principle and strategies of voltage rise regulation forgrid-connected photovoltaic generation system atpoint of common coupling[J].Automation of ElectricPower Systems,2014,38(3): 112-117.  
[17] Povlsen A F. Impacts of power penetration from pho-tovoltaic power systems in distribution networks[M].International Energy Agency, 2002.  
[18] 杨玉青，牛利勇，田立亭，等．考虑负荷优化控制的区域配电网储能配置[J]．电网技术，2015,39(4): 1019-1025.Yang Yuqing,Niu Liyong,Tian Liting,et al.Configuration of energy storage devices in regionaldistribution network considering optimal loadcontrol[J]. Power System Technology, 2015,39(4):1019-1025.