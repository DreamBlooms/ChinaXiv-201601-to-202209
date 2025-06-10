# 基于混合动力动车组的新型过分相配合策略

蒋李晨昕」李雪飞²　张馨予³阮白水³(1.株洲中车时代电气股份有限公司株洲4120012.中车长春轨道客车股份有限公司长春1300623.北京交通大学北京市轨道交通电气工程技术研究中心北京100044)

![](images/2f929f0fb1bbaf5f0807250cacd072bf47f707f05f81b0249adec0134627fe47.jpg)

蒋李晨昕男 1992年生，硕士，研究方向为电力电子与电气传动。

摘要：介绍了目前主流的过分相方案，探讨了混合动力动车组以及动力系统中网测变流器的控制策略与动力电池系统概况，提出了基于混合动力动车组的新型过分相方案（三类工况下)。采用该方案可使列车在通过无电区时保持动力，无需损失速度，且辅助机组正常在线。最后，基于实际试验的波形验证了所述理论的科学性与可行性。

关键词：混合动力动车组过分相策略网侧变流器 牵引制动工况无电区中图分类号：TM92

# The New Strategy of Passing Neutral Section Based on Hybrid Electric Multiple Units

Jiang Lichenxin'Li Xuefei²Zhang Xinyu³Ruan Baishui³ (1.Zhuzhou CRRC Times Electric Co.,Ltd. Zhuzhou412001 China 2.CRRC Changchun in Railway Vehicle Co.,Ltd. Changchun130062 China 3.Beijing Jiaotong UniversityBeijing 100044 China）

![](images/c8e8331ee19e842228c85f25e83ef1374fadae8e2cb18460ec2932dd76cd7ed8.jpg)

李雪飞女 1978年生，硕士，高级工程师，研究方向为系统总成技术。

Abstract: First of all, the current mainstream schemes of passing neutral section are introduced in this paper. Secondly, hybrid EMU and its basic configuration of power system are discussed,and then the new strategy of passing neutral section, which contains three conditions,in hybrid EMU is proposed. Train could maintain power and speed with online auxiliary units by using this scheme when passing neutral section. Finally, the scientific and feasibility of theory in the paper is verified based on the actual test waveform.

Keywords: Hybrid EMU, strategy of passing neutral section, grid-side converter, traction and braking condition, areas without electricity

传统的高速动车组采用交流牵引网25kV作为列车的唯一供电方式，这要求列车运行沿线都必须架设牵引网。而动车组网侧变流器为单相大功率电力电子变换设备，若单从电网的一相取电必然会造成电网负荷失衡。因此，为了维持电力系统各相负荷的平衡，保障电气设备的安全运行，电力机车必须采用分段分相的供电方式，即每隔一段距离就换相取电。同时，为了确保受电弓与接触网之间能够保持平稳的接触关系，有必要保持非同相供电臂之间的机械连接，且必须对两个供电臂采取电气隔离措施，设置无电区以避免出现异相短路。这就是分相区的由来[1]。

目前国内外主流的过分相方案主要有两种。第一种为车上断电自动过分相方案，多为欧盟国家所采用。该方案主要由车上设备自动操作完成，列车靠惰行或微制动驶过无电区，但当无电区较长或为上坡路段时，列车会降低相当一部分的车速，这对铁路的运营效率会有所影响[2]。第二种是地面自动过分相方案，其优点是断电时间短，过分相过程基本上不用降低列车车速，目前有应用于日本新干线。而该方案的不足在于开关设备的成本较高和体积较大；而且真空断路器的物理动作速度较慢，无法精确控制分合闸的时间，并且在其分闸过程中会造成过电压冲击，在合闸过程中会导致列车主变压器产生励磁涌流等[3-4]

采用本文提出的基于混合动力动车组的新型过分相策略，列车在过分相过程中可保持良好动力，不损失速度，并且辅助机组正常在线，快速平稳地通过无电区。

# 2 混合动力动车组动力系统配置

混合动力动车组是我国首列专为城际间客运而设计、具有多种动力源的动车组。该型车打破了以往只采用接触网供电的局限性，扩大了列车的运营范围，可实现从干线铁路到支线铁路、电气化铁路到非电气化铁路间的跨线运行。

图1所示为接触网到混合动力动车组牵引传动系统的结构图。在非电气段行驶时，由动力电池或动力包为列车提供动力，在电气段行驶时，铁路从接触网取电为列车提供动力，并且对动力电池进行充电。

# 2.1接触网模式下的网侧变流器

在接触网模式下，由网侧变流器工作为列车提

![](images/1b461c1a3afe8880b0e005f11f915943e2c948496d22c9220571ddf2627722e5.jpg)  
图1混合动力动车组牵引传动系统示意图  
Fig.1The structure of traction driveline of hybrid EMU

供稳定的动力。混合动力动车组网侧变流器采用了基于dq旋转坐标系的改进型解耦控制方法，可独立控制有功和无功功率，有效应对网压波动等工况[5-6]。该方法实质是将时变交流量转化为直流量进行控制，并采用快速虚拟轴计算单元降低引入电流控制内环的控制延时，改善了系统的动态性能[7-8]。

定义 $d$ 轴为有功轴，基于下述三个核心方程和控制框图对混合动力动车组网侧变流器的控制系统进行了设计与实现。即

$$
\begin{array} { l } { \displaystyle { \left[ U _ { d } = - \left( K _ { \mathrm { p } } + \frac { K _ { \mathrm { I } } } { s } \right) ( I _ { d } ^ { * } - I _ { d } ) + \omega L I _ { q } + E _ { d } \right. } } \\ { \displaystyle { \left. \left[ U _ { q } = - \left( K _ { \mathrm { p } } + \frac { K _ { \mathrm { I } } } { s } \right) ( I _ { q } ^ { * } - I _ { q } ) - \omega L I _ { d } + E _ { q } \right. \right. } } \end{array}
$$

$$
\begin{array} { r } { \{ I _ { d } = I _ { \mathrm { a } } \sin \omega t - I _ { \mathrm { \beta } } \cos \omega t  } \\ {  \vphantom { \sum }  [ I _ { q } = I _ { \mathrm { a } } \cos \omega t - I _ { \mathrm { \beta } } \sin \omega t   } \end{array}
$$

$$
I _ { \beta } = \big ( E _ { \beta } - U _ { \beta } \big ) / s L
$$

式中， $E _ { d }$ ， $E _ { q }$ 为电网电压的 $d$ ， $q$ 分量； $U _ { d }$ ， $U _ { q }$ 为输入侧电压的 $d$ ， $q$ 分量；而 $I _ { d }$ ， $I _ { q }$ 则为网侧电流的d、 $q$ 分量； $K _ { \mathrm { P } }$ 和 $K _ { \mathrm { I } }$ 分别为电流内环的比例和积分系数； $L$ 为交流侧电感值； $I _ { \mathrm { { a } } }$ 为实际轴电流； $I _ { \beta }$ 为虚拟轴电流。相关控制框图如图2所示，快速虚拟轴计算单元原理与式（3）对应。

图3所示为动车组实际试验波形，列车先以大级位牵引力加速，然后转惰行，再采取七级制动。可以看到在整个负载变化以及大功率负载投切的过程中，网侧变流器的动静态性能良好。

![](images/258940b9d6cc68853353c79b0320890c6fbc3b76742817f5a4bb43264afe6d2e.jpg)  
图2改进型解耦控制方法的控制框图

![](images/5d9ffd76c576706d35fd36a94d6698930957130723b4943c4dd16be1f85c6dc2.jpg)  
Fig.2The block diagram of improved dq-decoupling control method   
图3列车大级位牵引力加速-惰行-七级电制动 Fig.3Hybrid EMU accelerating,coasting and 7-level electric braking

图4所示为动车组大级位牵引力加速过程。整个电动机负载投切过程中网侧变流器对输入侧电流的控制十分稳定，波形正弦度好。

# 2.2非接触网模式下的动力电池

混合动力动车组的动力电池采用磷酸铁锂电池。这是目前技术较成熟、应用较广泛的一种新型锂电池制备材料，具有容易取得且基本无污染、充放电均无记忆效应等特点。此外，该类电池安全性高，在受到强烈撞击的情况下也不会爆炸[9-10]。选择双向DC-DC变换器作为动力电池的控制主电路。

充电控制策略中设置快速充电和慢速充电两种

CH4 450.0 Ma.ins2h电机保护（0 负载突减 负载突增 列车大级位牵引力加速.00m -450.0 000450.00 LC1输入侧交流电流Isi 2 ns/div97999.95n8 WWWWW时间(20ms/格)

充电模式。由于需保有一定的电池容量用于回收列车再生制动时的能量，所以动力电池组的充电截止SOC设置为 $90 \%$ 。图5所示为动力电池充电控制策略的实际试验波形。

![](images/cac30dbe38aa34709039ca02301eb50763a7e4072d00d7d6c32d2d36f352a852.jpg)  
图4列车大级位牵引力加速时的网侧输入电流 Fig.4The grid-side currents when EMU accelerating with high-level tractive force   
图5动力电池充电储能  
Fig.5The power battery charging

本文基于经典的双闭环系统设计制定了电池放电供能策略[]。动力电池放电为负载供能的实际试验波形如图6所示。

# 3 过分相配合策略

实际铁路上设置有预过分相信号和过分相完成信号两个信号，如图7所示。为方便表述，令预过分相信号为信号1，过分相完成信号为信号2，$\Delta U$ 为设定值。下面探讨三类工况下的过分相配合方案。

![](images/127df36c8e3405f8c6a0c7267d8cd3f8ee00099b90830c8a06bd66e048bf66b2.jpg)  
图6动力电池放电供能

![](images/4c75420aa0e58dced04f3d5b75dedfa1728b153cc37ec168f5571b0ec3a08950.jpg)  
Fig.6The power battery discharging

# 3.1牵引过分相方案

列车处于牵引状态通过分相区时的配合逻辑图如图8所示。进入分相区前，网侧变流器工作为列车提供动力。接收到信号1时若列车处于牵引或惰行状态，牵引力应当逐渐减小，将网侧变流器设定为“仅整流”模式，记录当前的直流电压值 $U _ { \mathrm { d c } }$ 。同时DC-DC系统控制动力电池释放能量，将中间直流环节的电压维持在 $U _ { \mathrm { d c } } + \Delta U _ { \mathrm { c } }$ （204

![](images/428149fa85f67a5ce3f98d9fbfad12f78ba0159b30809f0378bc2566d7976d92.jpg)  
Fig.7The signal configurations   
图8混合动力动车组牵引过分相流程  
Fig.8The processes of passing phase separations for hybrid EMU in traction condition

考虑到多系统间的A-D采样单元在硬件上可能存在一定的差异，在直流电压控制指令值上设置了$\Delta U$ 的差异。通过设置指令量冗余，可以避免多个电压环在控制上的互相干扰，实现供能系统间的平

滑切换。

在此过程中，列车所有的负载可以较为平稳地由网侧变流器系统移交给动力电池系统。当接收到信号1或列车主断路器强制分离后，网侧变流器停止工作，此时由动力电池为列车供电，当接收到信号2时，将动力电池设定为“仅放电”模式，中间直流环节电压维持在 $U _ { \mathrm { d c } } - \Delta U$ ，网侧变流器启动，将直流电压控制在目标电压值 $U _ { \mathrm { d c } }$ ，此后动力电池的输出自然截止。

采用上述方案可实现负载在网侧变流器与动力电池工作两个系统间的平稳移交。这意味着车上辅助设备在牵引过分相过程中无需断电，并且根据需求可以维持或提高列车速度。

# 3.2制动过分相方案

列车处于制动状态通过分相区时的配合逻辑图如图9所示。若列车处于制动状态，网侧变流器吸收列车的制动能量回馈给接触网。当接收到信号1时，考虑电池组的功率吸收能力，牵引电机实际发挥的制动力应酌情适当减小，并且将网侧变流器设定为“仅逆变”模式，记录此时刻直流电压值 $U _ { \mathrm { d c } }$ 。同时DC-DC系统控制动力电池吸收制动能量，将中间直流环节的电压维持在 $U _ { \mathrm { d c } } - \Delta U _ { \mathrm { c } }$ 。在这个过程中，列车所有的负载亦可以较为平稳地由网侧变流器系统移交给动力电池系统。

![](images/e50edf0111787ccd3e554bd23b951fbaed8a3d7c0e441136e6c5165a5d300732.jpg)  
图7分相区信号设置  
图9混合动力动车组制动过分相流程  
Fig.9The processes of passing phase separations for hybrid EMU in braking condition

当确认接收到信号1或是列车强制分离主断路器后，网侧变流器停止工作，此时由动力电池维持中间直流环节电压。

当接收到信号2时，将动力电池设定为“仅充电”模式，中间直流环节电压维持在 $U _ { \mathrm { d c } } + \Delta U$ ，而后网侧变流器启动，将直流电压控制在目标值 $U _ { \mathrm { d c } }$ 此后动力电池停止充电。

采用上述制动过分相策略，在列车以制动状态驶过无电区的过程中，也可实现网侧变流器与动力电池工作的“无缝”切换，维持车上辅助设备正常在线，而多余的制动能量则被回收进入动力电池。

# 3.3电池系统离线工况下的过分相方案

在动车组行驶的复杂车况中，也有可能出现因意外情况导致电池系统离线[12]。当电池系统离线（故障、通信中断、极端低温等情况导致动力电池无法正常发挥性能）时，混合动力动车组的过分相方案配置与车上自动过分相方案类似。

进入分相区之前，由网侧变流器从 $2 5 \mathrm { k V }$ 接触网取电为列车供电，直流电压稳定在 $U _ { \mathrm { d c } }$ 。当接收到信号1时，动车组转为再生制动状态。当主断路器强制断开，网侧变流器停止工作，依靠列车的再生制动能量来维持中间直流环节的电压，部分车载设备暂时离线。当动车组脱离无电区，主断路器自动闭合，然后网侧变流器预充电重启，开始为动车组供电。

# 4 试验研究与分析

在混合动力动车组地面牵引链实验平台上对该新型过分相策略的可行性进行了实验验证。以牵引过分相策略的验证试验为例进行说明。

实验选用网侧变流器和两组动力电池进行，其中一组动力电池设定为“仅充电”模式，等效为列车的部分负载；而另一组动力电池则与网侧变流器配合工作，在过分相过程中“无缝”交接负载，交替承担供能工作。

实际功率试验波形如图10所示。试验分析如下：首先，网侧变流器并网建立了稳定的直流电压，其启动过程平稳，动静态特性良好。然后投入作为负载的电池组，负载整体功率约为 $1 2 0 \mathrm { k W }$ 。进入分相区之前，直流电压稳定在 $1 ~ 6 5 0 \mathrm { V }$ ，网侧变流器带载工作。

![](images/131d6f7dad83ca9cda05264edb428154130d86e54397e80eb87aa7a9b5978d8a.jpg)  
图10牵引过分相策略试验波形  
Fig.10The test waveform of passing phase separations in traction condition

当收到信号1后，将动力电池组的直流电压指令值调整到 $1 ~ 6 8 0 \mathrm { V }$ ，动力电池开始放电，输出功率；与此同时，网侧变流器封锁“逆变”功能，网侧输入电流降为零。即意味着在无电区由电池系统接过负载，为列车提供能量。整个切换过程负载冲击较小，直流电压的控制较为平稳。然后在列车接到信号2后，将动力电池的指令电压调低到 $1 6 2 0 \mathrm { V }$ 且网侧变流器启动。在网侧变流器将实际直流电压升到 $1 ~ 6 2 0 \mathrm { V }$ 以上后，动力电池停止放电；网侧变流器接过负载，开始供电。

因此，通过控制网侧变流器和动力电池的配合工作，实现了混合动力动车组带负载顺利过分相。此外，在过分相时电机实际发挥的牵引力应考虑动力电池组当前能够提供的最大可用功率。

# 5 结束语

在介绍混合动力动车组网侧变流器和动力电池两个控制系统概况的基础上，本文提出了基于该型车的新型过分相配合策略，并根据三种实际工况给出了针对性设计方案，并通过实际试验对该新型过分相方案的科学性与可行性进行了验证。较传统过分相方案而言，不需设置繁杂的地面开关设备，亦可减小动车司机的操作负担。应用该策略后在经过分相区时可确保列车仍保有足够的动力，不损失速度，还能维持辅助机组正常在线，不仅增强了动车组列车的跨线运行能力和适用幅度，也提高了铁路运营效率。

# 参考文献

[1] 姜晓锋，何正友，胡海涛，等．高速铁路过分相电磁暂态过程分析[J]．铁道学报，2013(12)：30-36.Jiang Xiaofeng,He Zhengyou,Hu Haitao,et al.Analysis on electromagnetic transient processof electric multiple unit passing neutral sectiondevices[J]. Journal of the China Railway Society,2013(12):30-36.  
[2] 王术合．高速动车组不断电自动过分相的研究[D].北京：北京交通大学，2012.  
[3] 孙万启，单圣熊，郑国藩．国内外自动过分相装

（下转第50页）