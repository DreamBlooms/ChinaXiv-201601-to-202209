# 磁控形状记忆合金传感器优化设计

鲁军苏超锋

（沈阳理工大学自动化与电气工程学院沈阳110159）

鲁军男1965年生，博士，教授，研究方向为智能材料与智能控制系统。

摘要：磁控形状记忆合金（MSMA）是一种具有可逆特性的新型功能材料，利用该材料的逆特性可研制MSMA传感器。基于理论分析，利用有限元分析软件AnsoftMaxwell对MSMA传感器的各部分结构分别进行有限元仿真，设计出结构及形状优化的MSMA传感器，性能更加完善。通过实验验证了MSMA传感器优化的有效性，为MSMA传感器的建模及应用奠定了技术基础。

关键词：MSMA 传感器 优化设计 实验研究中图分类号：TM359

# Optimized Design of Magnetically Controlled Shape Memory Alloy Sensor

Lu Jun Su Chaofeng （ShenyangLigongUniversityShenyang110159 China ）

![](images/3bed5362148f5d9ab02e1a7bc20b79dd9ab22ac279415b81ec0dc6ac7ac09a84.jpg)  
收稿日期：2018-08-24

![](images/8c74650ee658d0d29cd265c02958d2a97dd3316cb82e6e4634b786b616500e21.jpg)

苏超锋男 1991年生，硕士研究生，研究方向为智能检测与信息处理。

Abstract: Magnetically controlled shape memory alloy (MSMA) is a kind of new functional material with reversible properties,which can be used to develop MSMA sensor.Based on the theoretical analysis,the finite element analysis software of Ansoft Maxwell is used to simulate the each parts of the MSMA sensor respectively. The MSMA sensor,which has structure and shape optimization,is design in this paper，optimized sensor can improve its performance.By experimental study, the effectiveness is verified about MSMA sensor optimization, the research works lay a technical foundation for modeling and application of MSMA sensor.

Keywords: Magnetically controlled shape memory alloy, sensor, optimized design, experimental study

# 1 引言

近年来，传感器技术发展迅速，新理论、新感知技术、新材料、新的加工技术和信息处理技术不断地被集成到新传感器的研究和开发中，使得市场上不断涌现出具有新结构和新用途的传感器，促进了磁控形状记忆合金(MagneticallyControlledShape Memory Alloy，MSMA）传感器的研究[1]。

现有文献对MSMA驱动器的理论和应用进行了许多研究[2-3]，但将其应用于传感器的相关研究较少[4-6]。本文通过研究磁控形状记忆合金逆效应，在理论分析和实验研究的基础上，优化传感器结构，并进行实验研究。该传感器将在自动化生产、机器人、汽车等领域发挥越来越重要的作用。

# 2 MSMA传感器数学模型

由励磁线圈、永磁体和铁心组成的传感器系统模型如图1所示[7]。

![](images/c745f5af2f3407f6e5704dad54e40a29ed449946ff1607988e3bbc62d492348b.jpg)  
图1MSMA传感器等效磁路  
Fig.1Equivalent magnetic circuit of MSMA sensor

在等效磁路模型中， $\phi _ { \mathrm { { P } } }$ 为永磁体的磁通； $\phi _ { \mathrm { s } }$ 为永磁体与励磁线圈产生的磁通量之和； $\pmb { \phi } _ { \mathrm { M } }$ 为穿过MSMA元件的磁通量； $\mathbf { \sigma } _ { \varepsilon }$ 为元件的变形量； $R _ { \mathrm { m M } } ( \varepsilon )$ 为MSMA元件变形后产生的磁阻值； $R _ { \mathrm { m G } } ( \varepsilon )$ 为元件发生形变时气隙磁阻值； $R _ { \mathrm { m o } }$ 为穿过MSMA材料的漏磁阻值； $R _ { \mathrm { m S } }$ 为励磁线圈的内磁阻值。则感应线圈的磁通量 $\textstyle \phi _ { \mathrm { { M } } }$ 为

$$
\mathcal { P } _ { \mathrm { M } } = \frac { \mathcal { P } _ { \mathrm { S } } R _ { \mathrm { m S } } } { R _ { \mathrm { m S } } + R _ { \mathrm { m C } } + \displaystyle \frac { [ R _ { \mathrm { m S } } ( \varepsilon ) + R _ { \mathrm { m M } } ( \varepsilon ) ] R _ { \mathrm { m \sigma } } } { R _ { \mathrm { m G } } ( \varepsilon ) + R _ { \mathrm { m M } } ( \varepsilon ) + R _ { \mathrm { m \sigma } } } }
$$

写成一般式为

$$
\varPhi _ { \mathrm { M } } = \alpha B _ { \mathrm { M } } \frac { \varepsilon + \beta } { \varepsilon + \gamma }
$$

式中， $\alpha$ 、 $\beta , \gamma$ 为待辨识的三个系数； $B _ { \mathrm { M } }$ 为MSMA传感器的偏置磁场。

根据感应电压微分方程

$$
U _ { \mathrm { e } } = N \frac { \mathrm { d } \varPhi _ { \mathrm { M } } } { \mathrm { d } t } = N \frac { \mathrm { d } \varPhi _ { \mathrm { M } } } { \mathrm { d } \varepsilon } \frac { \mathrm { d } \varepsilon } { \mathrm { d } t }
$$

经过推导，可得感应电压 $U _ { \mathrm { e } }$ 为

$$
U _ { \mathrm { e } } = N \frac { k _ { 1 } B _ { \mathrm { M } } F _ { \mathrm { m } } \omega \cos \omega t } { S _ { \mathrm { M S M A } } \left( \displaystyle \frac { k _ { 2 } F _ { \mathrm { m } } \sin \omega t } { S _ { \mathrm { M S M A } } } + k _ { 3 } B _ { \mathrm { M } } + k _ { 4 } \right) ^ { 2 } } + k _ { 5 }
$$

# 3 MSMA传感器结构设计

# 3.1励磁线圈

励磁线圈中的电流 $I$ 与线圈中线径 $d$ 的关系为[8-9]

$$
d = { \sqrt { \frac { 4 I } { \pi J } } } = 1 . 1 3 { \sqrt { \frac { I } { J } } }
$$

其中， $J$ 为导线电流密度。一般 $J$ 取值 $2 \sim 5 \mathrm { A } / \mathrm { m m } ^ { 2 }$ 最大励磁电流为1A。

为防止线圈功率过大产生热量，由焦耳定律可知，电阻越大，产生的热量越高， $J { = } 2 \ \mathrm { A } / \mathrm { m m } ^ { 2 }$ 时电阻最小，但求得的导线直径过大，因此本文 $J$ 选取$3 \mathrm { A } / \mathrm { m m } ^ { 2 }$ ，代入式（5），得

$$
d \geqslant 0 . 6 5 \mathrm { m m }
$$

线圈单位长度匝数为

$$
n _ { \mathrm { 1 } } = \frac { 1 0 } { k _ { \mathrm { \eta } } d }
$$

线圈单位厚度上的层数为

$$
n _ { 2 } = \frac { 1 0 } { k _ { \mathrm { { \beta } } } d }
$$

线圈内径为

$$
R _ { \mathrm { l } } = R _ { \mathrm { t } } + { \frac { e _ { \mathrm { l } } } { 2 } } + e _ { \mathrm { 2 } } + e _ { \mathrm { 3 } }
$$

式中， $k _ { \mathfrak { n } }$ 为线圈排绕系数； $k _ { \beta }$ 为线圈叠线系数； $R _ { \mathrm { t } } =$ $1 / ( 2 D )$ ， $D$ 为漆包线的内径； $\boldsymbol { e } _ { 1 }$ 为调节中心位置的缝隙； $e _ { 2 }$ 为线圈骨架的厚度； $e _ { 3 }$ 为线圈与骨架之间所需的绝缘材料厚度。

线圈的外径 $R _ { 2 }$ 及线圈的最大外径 $R _ { 2 \mathrm { { m } } }$ 为

$$
R _ { 2 } = R _ { 1 } + e
$$

$$
R _ { 2 \mathrm { m } } = R _ { 1 } + e + e _ { \mathrm { f } } \left( N _ { 2 } - 1 \right)
$$

式中， $e$ 为线圈厚度； $e _ { \mathrm { f } }$ 为每层绝缘材料的厚度；$N _ { 2 } = n _ { 2 } e$ 为线圈的层数。线圈厚度 $e$ 的计算式为

$$
e = \frac { H } { 4 \pi n _ { 1 } n _ { 2 } I }
$$

线圈的总匝数为

$$
N = ( n _ { \mathrm { { 1 } } } L _ { \mathrm { { c } } } ) ( n _ { \mathrm { { 2 } } } e )
$$

式中， $H$ 为场强； $L _ { \mathrm { c } }$ 为线圈长度。

将式（7）、式（8）、式（12）代入式（13），得到励磁线圈总匝数。当MSMA元件的变形率大于 $3 \%$ ，偏置磁场也需要增加，在保证不产生过多热量的合理范围内增加线圈匝数可以增强输出感应电压的大小。因此，根据计算及励磁线圈电磁仿真的结果，选取励磁线圈的总匝数为1000匝。

根据导线的电阻率，线圈的总电阻计算式为

$$
R = \rho \pi ( R _ { \mathrm { l } } + R _ { \mathrm { 2 m } } ) N / S _ { \mathrm { d } }
$$

式中， $S _ { \mathrm { d } }$ 为导线的有效截面积； $\rho$ 为铜的电阻率。

根据电阻的热功率计算式

$$
P = I ^ { 2 } R
$$

励磁线圈中的电流取最大值1A时，经计算得到的最大励磁功率为 $6 \mathrm { w }$ 。

# 3.2铁心

由全磁路欧姆定律可得MSMA传感器的铁心尺寸为

$$
\Phi \left( \frac { L } { \mu _ { 0 } \mu _ { \mathrm { r } } S } + \frac { \delta } { \mu _ { 0 } S _ { 0 } } \right) = N I
$$

式中， $\phi$ 为磁通； $\mu _ { 0 }$ 为真空磁导率； $\mu _ { \mathrm { r } }$ 为相对磁导率，其值为700； $S$ 为铁心截面积； $S _ { 0 }$ 为永磁体截面积； $L$ 为铁心总长度 (忽略永磁体处长度)，单位为 $\mathrm { m m }$ 。

其中

$$
\varPhi \left( \frac { \delta } { \mu _ { 0 } S _ { 0 } } \right) = H \delta
$$

根据实验采用的MSMA材料的形状尺寸，确定铁心的厚度为 $2 0 \mathrm { m m }$ ，截面宽度为 $1 6 \mathrm { m m }$ ，将数据代入式 (17)，得

$$
L = 3 5 3 . 2 \mathrm { m m }
$$

# 3.3检测线圈

MSMA传感器原理图如图2所示。励磁线圈通入直流电流，气隙处的MSMA材料形变使铁心中的磁通发生变化，感应电压由二次线圈输出。

励磁线圈的磁感应强度为

![](images/77b0fc97ef9fbd68d8e6ffe55bb717913fca2b085ac2092deeff1bde7c94cafb.jpg)  
图2MSMA传感器原理图  
Fig.2Schematic diagram of MSMA sensor

$$
\begin{array} { c } { { B _ { \mathrm { x } } = 2 \pi n _ { 1 } n _ { 2 } \mu _ { 0 } I \left\{ \displaystyle ( X + l ) \ln \frac { R _ { \mathrm { 2 } } + \displaystyle [ R _ { \mathrm { 2 } } ^ { 2 } + \displaystyle ( X + l ) ^ { 2 } ] ^ { \frac { 1 } { 2 } } } { R _ { \mathrm { 1 } } + \displaystyle [ R _ { \mathrm { 1 } } ^ { 2 } + \displaystyle ( X + l ) ^ { 2 } ] ^ { \frac { 1 } { 2 } } } + \right. } } \\ { { \left. ( l - X ) \ln \frac { R _ { \mathrm { 2 } } + \displaystyle [ R _ { \mathrm { 2 } } ^ { 2 } + \displaystyle ( X + l ) ^ { 2 } ] ^ { \frac { 1 } { 2 } } } { R _ { \mathrm { 1 } } + \displaystyle [ R _ { \mathrm { 1 } } ^ { 2 } + \displaystyle ( X + l ) ^ { 2 } ] ^ { \frac { 1 } { 2 } } } \right\} } } \end{array}
$$

式中， $l$ 为线圈长度的一半； $X$ 为线圈轴线上的磁感应强度点到中心点的距离。

根据MSMA传感器的磁路模型，得到铁心中的磁通为

$$
\varPhi _ { \mathrm { M } } = B _ { \mathrm { M } } \frac { a \varepsilon + b } { \varepsilon + c }
$$

式中， $B _ { \mathrm { M } }$ 为偏置磁场， $B _ { \mathrm { M } } = B _ { 0 } + B _ { \mathrm { X } }$ ， $B _ { \mathrm { X } }$ 为励磁线圈产生的磁感应强度， $B _ { 0 }$ 为永磁体产生的磁感应强度，为常数； $\mathbf { \Delta } _ { a }$ ， $b$ 、 $\mathbf { \Psi } _ { c }$ 取决于MSMA材料的几何形状、参数及应变率系数。

感应电动势分别为

$$
e _ { \mathrm { i } } = - N _ { \mathrm { i } } \frac { \mathrm { d } \phi _ { \mathrm { c } } } { \mathrm { d } t }
$$

$$
e _ { _ 2 } = - N _ { _ 2 } \frac { \mathrm { d } \phi _ { \mathrm { c } } } { \mathrm { d } t }
$$

故得励磁与检测线圈的电压比 $k$ 为

$$
k = \frac { e _ { 1 } } { e _ { 2 } } = \frac { N _ { 1 } } { N _ { 2 } }
$$

为了能够输出较高的感应电压，检测线圈的匝数应多于励磁线圈的匝数。另由于检测到的电压中有谐波及感应电压，检测线圈的匝数越多区分度越好，故电压比取为1.5，检测线圈的匝数为1500匝。

# 4传感器磁场有限元分析

由于MSMA传感器是非线性系统，即机械、电磁场、温度等多种物理场耦合系统，因此用有限元仿真[10-13]需模拟实验条件，进而达到优化传感器的目的。根据MSMA传感器的结构设计，传感器结构及优化设计如图3所示。

![](images/e493ff1004217bd77c290236f50c6d808b5b1d555e090e58cfd9f5e4d83184b7.jpg)  
图3MSMA传感器结构示意图

Fig.3Structure diagram of the MSMA sensor

铁心结构确定后，可选择单独线圈励磁或永磁体加线圈励磁两种方式。仅有线圈励磁的磁场分布及气隙处指定位置磁感应强度剖面图如图4所示。

![](images/2e2f994b565328890a3013ad594928fe021375a7a4cb23b28a8257db7b584d28.jpg)

图4无永磁铁时磁场分布及气隙磁通密度剖面图 Fig.4Magnetic field distribution and profile of gap magnetic flux density without permanent magnet

1 丨电气工程学报

给线圈施加1A的最大电流，气隙处的磁感应强度仅为 $3 4 5 . 0 4 \mathrm { m T }$ ，由于此时MSMA材料变形较小，故感应电压较低。为了减少励磁功率，提高感应电压，本实验采用的是永磁体与线圈励磁方式。

当永磁体1宽度选用 $2 0 \mathrm { m m }$ 、永磁体2选用$5 \mathrm { m m }$ 时，磁场分布及磁通密度剖面图如图5所示。MSMA传感器气隙处的磁感应强度满足磁场变化范围且均匀分布。

![](images/4577fd6ea4aad0958f8a7d72e9209764b55ab67fdb91ea71aee0f7fae745de66.jpg)  
图5有永磁铁时磁场分布及气隙磁通密度剖面图 Fig.5Magnetic field distribution and profile of gap magnetic flux density with permanent magnet

# 5 实验研究

# 5.1实验输出波形

MSMA传感器输入参数为激振器的频率、幅值；励磁电流（与永磁体共同作用）产生的偏置磁场，输出参数为检测线圈的感应电压值。激振器的频率为 ${ 5 0 0 } \mathrm { H z }$ 、幅值为 $2 \mathrm { N }$ 、偏置磁场为0.26T时，感应电压波形如图6所示。

从图6可以看出，MSMA传感器的感应电压值与激振器的输入均按照正弦规律变化，且周期、相

![](images/97bca4149e4c0c8590b566b4b453b44127569240ba3853d36ef0a8c0df7537f8.jpg)  
图6传感器输入-输出波形对比图

# 5.2传感器感应电压值与偏置磁场的关系

激振器输入频率为 $2 5 0 \mathrm { H z }$ ，幅值为1.5N时，MSMA传感器的感应电压值如图7所示。由图7可见，感应电压为 $2 4 6 \mathrm { m V }$ ，输出波形谐波明显减少，证明MSMA传感器结构的正确性与稳定性。

![](images/207706915b18fbf5565bfa7f9e4a304c4c2cdd07f69438f9df4c6330302f4760.jpg)

仅改变偏置磁场，模型计算值与实验数据比较如图8所示。当偏置磁场改变时，计算值与实验测量值吻合度较高。由MSMA逆效应机理可知，材料气隙处的磁通密度的变化与感应电压成正比，故感应电压峰-峰输出值随着偏置磁场的增加而增加，呈近似线性关系。

![](images/d28e343ff2fbd48cb61ceb0867752a1f6ee1e870464e2e902c4992c8daf55d70.jpg)  
图7偏置磁场为 $0 . 2 8 \mathrm { T }$ 时的实验输出波形  
图8感应电压峰－峰值和偏置磁场的关系  
Fig.8Comparison calculated value and experiment data when biased magnetic field changes

# 5.3传感器感应电压值与激振器频率关系

当机械力频率太低时，线圈两端的感应电压太小而不易测量。又因材料工作频率的限制，由激振器施加的力的频率不能太高，故激振器的频率设定为 $2 0 0 \sim 1 ~ 0 0 0 \mathrm { H z } .$ 。

频率改变时，由式（4）可得感应电压峰－峰值与相同条件下的实验数据比较如图9所示。可以看出，感应电压的峰－峰值随着激振器频率的增加而线性增加，这是由于随着频率的增高，磁通密度的变化率也随着增大，使输出感应电压值增加，且计算值与实验测量值误差较小。

![](images/26ac41fd1b11030e3a92bfcf2bd007e53c2ffd7fddd44045f624a14bccc814de.jpg)  
Fig.6Comparison of sensor input and output waveforms 位相同。   
图9不同振动频率下感应电压峰－峰值数据比较 Fig.9Comparison calculated value and the experimental data when frequency changes

# 5.4传感器感应电压值与激振力幅值关系

对MSMA传感器施加的磁场强度为 $0 . 2 6 \mathrm { T }$ ，激振器频率为 $7 0 0 \mathrm { { H z } }$ ，仅改变激振器幅值，由式(4)得到感应电压峰－峰值与同等条件下实验输出电压值相比较如图10所示。计算值与实验测量值的误差在工程允许的范围内，感应电压峰－峰值随着激振器输入幅值的增加而增加，但呈非线性关系。

![](images/e71cca4f189ae4667c51febce479253e988c2bea55a23443c25c94fe2cf3e292.jpg)  
Fig.7Experimental output waveform when $B _ { \mathrm { m } } = 0 . 2 8 \mathrm { T }$   
图10不同振动幅值下感应电压峰－峰值数据比较 Fig.10Comparison calculated value and experimental data when amplitude changes

# 5.5传感器优化验证

在相同实验条件下，对于优化前后的MSMA传感器波形比较如图11所示。显而易见，优化后传

感器输出的电压值大于优化前的感应电压值。从实验方面验证了优化后的MSMA传感器的有效性。

![](images/7edad2580539c58c9753e0e2229062f92028e185e104c514bb4a019ecb18bf89.jpg)  
图11结构优化前后感应电压比较图  
Fig.11Comparison of induced voltage before and after structure optimization

# 6 结论

基于电磁学理论，本文对MSMA传感器的励磁线圈、检测线圈、铁心分别进行设计，并对MSMA传感器的磁场进行有限元仿真，确定传感器优化结构与形状，为MSMA传感器的结构设计提供了一种设计依据。对于优化MSMA传感器进行实验研究，得到偏置磁场、激振力（幅值和频率）参数变化时感应电压输出峰－峰值的变化规律，通过实验验证了MSMA传感器的结构的合理性。实验研究表明，优化后的MSMA传感器的输出感应电压值更大，波形更加完善，谐波相对较少，达到了设计要求。

# 参考文献

[1] Wang Fengxiang,Li Wenjun, Zhang Qingxin, et al.Experimental study on characteristics of NiMnGamagnetically controlled shape memory alloy[J].Journal of Material Science & Technology,2006,22(1): 55-58.  
[2] 张庆新，王凤翔，李文君，等．NiMnGa合金磁控形状记忆效应及外特性[J]．稀有金属材料与工程，2005，34(8):1263-1266.Zhang Qingxin,Wang Fengxiang,Li Wnjun,etal.Magnetic shape memory effect and externalcharacteristic of NiMnGa alloy[J].Rare MetalMaterials and Engineering,2005,34(8): 1263-1266.  
[3] 詹建徽，张代远．传感器应用、挑战与发展[J].计算机技术与发展，2013，23(8)：118-121.Zhan Jianhui, Zhang Daiyuan. Sensor application,challenge and development[J]. Computer Technologyand Development, 2013, 23(8): 118-121.鲁军，李敏，王凤翔．基于MSMA逆特性的振动传感器理论及实验[J]．电工技术学报，2014,29(5): 233-237.Lu Jun, Li Min, Wang Fengxiang. Theoretical andexperimental study on vibration sensor based onMSMA inverse characteristics[J]. Transactions ofChina Electrotechnical Society,2014,29(5): 233-237.  
[5] 鲁军，杨宽，王凤翔．磁控形状记忆合金振动传感器模型及实验特性[J]．电机与控制学报，2014,13(8): 20-24.Lu Jun, Yang Kuan, Wang Fengxiang. Model andexperiment characteristic on vibration sensor ofmagnetically controlled shape memory alloy[J].Journal of Electric Machines and Control, 2014,13(8): 20-24.  
[6] 鲁军，李侠，王重马．基于小波分析的 MSMA振动传感器信号处理与故障检测[J]．电工技术学报,2015，30(10):354-360.Lu Jun, Li Xia, Wang Zhongma. Signal processingand fault detection of MSMA vibration sensorsbased on wavelet analysis[J]. Transactions of ChinaElectrotechnical Society, 2015,30(10): 354-360.  
[7] Suorsa I. Performance and modeling of magneticshape memory actuators and sensors[D]. Espoo:Teknillinen korkeakoulu,2005.  
[8] 贾振元，郭东明．超磁致伸缩材料微位移执行器原理与应用[M]．北京：北京科学出版社，2008.  
[9] 王博文，曹淑瑛，黄文美．磁致伸缩材料与器件[M].北京：冶金工业出社，2008.  
[10] 嘉木工作室．ANSYS 有限元实例分析教程[M]．北京：机械工业出版社，2002.  
[11] 王国强，实用工程数值模拟技术及其在ANSYS 上的实践[M]．西安：西北工业大学出版社，2001.  
[12]谭建国．使用ANSYS6.0进行有限元分析[M]．北京：北京大学出版社，2002.  
[13]赵博，张洪亮．Ansoft 12 在工程电磁场中的应用[M]．北京：中国水利电力出版社，2010.