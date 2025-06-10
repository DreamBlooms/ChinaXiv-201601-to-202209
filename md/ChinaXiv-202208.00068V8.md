# 双轴电流源同步机视角下跟网/构网设备建模及其互联系统同步稳定分析

庄可好¹，辛焕海¹，高晖胜‘ (1．浙江大学电气工程学院，浙江省 杭州市 310027)   
The Modeling of Grid-Forming and Grid-Following Devices from the   
Perspective of Dual Axis Current Sources Synchronous Generator and Synchronous Stability Analysis of Interconnected Systems

Zhuang Kehao'， XIN Huanhai，GAO Huisheng (1. College ofElectrical Engineering, Zhejiang University, Hangzhou 310027,Zhejiang Province, China)

ABSTRACT: With the integration of large-scale new energy and power electronics,the power system has gradually formed a form of interconnection between grid forming equipment and grid following equipment. The grid forming equipment mainly includes virtual synchronous machines and synchronous machines,while the grid following equipment mainly consists of phase-locked loop converters.Synchronous stability is crucial as the foundation for the operation of large power grids,but due to the significant differences in synchronization mechanisms between grid forming equipment and grid following equipment, it is extremely difficult to analyze the synchronous stability of interconnected systems.Therefore，this article utilizes the concept of dual excitation winding synchronous machines in physical understanding to construct an equivalent structure that can unify grid forming equipment and grid following equipment. In mathematics,a universal modeling approach is proposed to describe the synchronization characteristics of equipment,and a synchronization stability analysis model for interconnected systems based on current sources is established.Furthermore, the mathematical definition of synchronization stability in interconnected systems and several sufficient conditions for system synchronization stability are given.Finally,a simulation example was built in MATLAB/Simulink to verifythe rationality of the model.

KEYWORDS:Interconnection system; Synchronous stability;   
Dual axis synchronous machine; Current source.

摘要：随着大规模新能源和电力电子技术的发展，电力系统逐渐形成了构网设备和跟网设备互联的形态，其中典型构网设备主要包括虚拟同步机和同步机，典型跟网设备包括锁相环型变流器。同步稳定是大电网运行的基础，但由于构网设备与跟网设备的同步机制存在很大差异，使得互联系统同步稳定分析极为困难。为此，本文从物理上借助双轴同步机的概念构建了可以统一构网设备和跟网设备的等效结构，在数学上提出了描述设备同步特性的通用建模思路，建立了基于双轴电流源同步机的互联系统同步稳定分析模型。进一步，给出了互联系统同步稳定的数学定义和同步稳定的充分条件。最后，在MATLAB/Simulink搭建仿真验证了模型与分析的合理性。

关键词：互联系统；同步稳定；双轴同步机；电流源

# 0 引言

构建新能源电力系统是实现“碳达峰·碳中和”的重要举措，对推动我国能源转型意义重大1。构网设备与跟网设备(Voltage Source Converter,VSC)互联是新能源电力系统的主要特征(后文简称为互联系统)。目前，独立形成电压和频率的构网设备主要包括同步机和虚拟同步机(虚拟同步控制的变流器，Virtual Synchronous Generator,VSG)[23]。跟网设备通过计算或闭环控制来检测电压相位实现与电网同步，下文以典型的锁相环(PhaseLockedLoop,PLL)同步变流器(后文简称为PLL-VSC)作为研究对象。

随着变流器渗透率提高，互联系统的稳定形态与特征发生演变，传统分析方法适应性值得商榷[3]。其中，同步稳定作为交流电网运行的基础，需要被重新认识并扩展相应的分析与控制理论以保障互联系统的稳定运行。因此，如何准确认知互联系统同步稳定特性成为亟待解决的问题。

与同步机固有转子之间相对运动主导的“物理同步”不同，VSG和PLL-VSC的同步机制由控制算法决定，表现为“控制同步”[23]。其中，VSG 模拟同步机转子摇摆方程，通过功率控制实现同步，在正常工况下与同步机都表现为“功角"稳定[23]。然而，变流器的电流限幅约束可能会导致VSG 在大扰动下切换为电流源运行，使得其动态行为更加复杂[23]导致目前尚难以从系统层面认知电流限幅约束下VSG的同步稳定特性。

另外，PLL-VSC的同步稳定机理也尚未形成统一认知。在单PLL-VSC设备并网系统中，已经有学者将锁相环主导的次/超同步振荡和失步问题归为PLL-VSC的同步稳定问题[2][6]。对于锁相环主导的振荡问题，学术界广泛采用的方法是建立频域阻抗模型并基于奈奎斯特判据分析[7-9]。针对锁相环失步的问题，部分论文中提出了广义摇摆方程等建模方法[10-12]，并探讨了等面积方法和直接法在单机暂态同步稳定分析的应用[13-16]。然而，上述研究仍难以直观地给出锁相环与其他控制回路交互作用下动态响应行为的物理理解。在研究多PLL-VSC设备并网系统时，由于其同步动态涉及机电-电磁多时间尺度耦合，系统模型复杂高阶分析极为困难，研究也相对较少。基于模态解耦的方法可将多变流器馈入系统解耦为等效单机[8]，从而降低模型阶数以简化分析难度，便于同步稳定裕度量化，但却难以揭示多机间的同步稳定机理。

虽然单一类型设备的同步稳定分析已经开展了大量研究，但受限于构网设备和跟网设备同步机制的差异，互联场景下的相关研究尚处于起步阶段，目前仅能结合具体场景研究跟网型新能源渗透率、接入点等因素对同步机功角稳定性的影响[17-20]。具体表现为：在设备层面，变流器控制类型多样且控制回路间级联复杂，现有研究尚未理清不同类型变流器间的联系，也未揭示多控制回路在变流器同步过程中的物理作用；在系统层面，受限于变流器与网络电磁动态深度耦合以及构网设备与跟网设备同步机制的差异，互联系统同步稳定分析十分困难，现有研究也大多局限于同步机的功角稳定。

为此，有必要挖掘同步机、VSG和PLL-VSC同步机制的共性并建立合理的模型，为互联系统分析奠定基础。为解决上述问题，本文主要工作如下：

(1)借助“双轴同步机”的概念，构建了同步机和变流器统一的等效结构，两者动态均由控制坐标系相位的动态及d轴、q轴动态组成，同步动态可理解为控制坐标系相位的摇摆，其余控制回路动态被理解为dq轴的电路动态过程。

(2)基于模型鲁棒性和稳定分析便捷性两方面的要求，建立了同步机和变流器的双轴电流源同步机模型，并将两者动态特性差异进行参数化，从而为认知互联系统的动态特性提供理论基础。

(3)给出了互联系统同步稳定的定义，建立了网络和互联系统的简化模型，给出了线性化模型下系统同步稳定的充分条件，为变流器同步控制设计和系统同步稳定分析奠定基础。

# 文中用到的术语说明：

公共坐标系：理想电网的 $x y$ 坐标系，其旋转速度为 $\omega _ { \scriptscriptstyle 0 } = 1 0 0 \pi ( r a d / s )$ ， $x$ 轴的相位为 $\theta _ { 0 }$

控制坐标系：设备dq轴控制的参考坐标系，d轴相位为 $\theta _ { s }$ ，同步机控制坐标系与转子dq轴重合，变流器控制坐标系由同步控制决定；

定向相位：设备输出电压 $V \angle \theta _ { \scriptscriptstyle V }$ 或输出电流$I { \angle { \theta _ { I } } }$ 的相位与控制坐标系d轴相位的差值，表示为 $\theta _ { { \scriptscriptstyle V d q } } = \theta _ { \scriptscriptstyle V } - \theta _ { \scriptscriptstyle s }$ 或 $\theta _ { _ { I d q } } = \theta _ { _ { I } } - \theta _ { _ { S } }$ ;

虚拟功角：设备控制坐标系相位与电网参考电压相位的相位差，表示为 $\delta ^ { ' } = \theta _ { s } - \theta _ { 0 }$ ;

d轴、q轴动态：电气矢量(电压/电流)在控制坐标系中d轴分量和 $\mathsf { q }$ 轴分量的动态；

电压源/电流源建模：设备状态空间建模时选择电压/电流作为输出变量。

双轴同步机：同步机转子dq轴均缠绕励磁绕组，可同时通过励磁控制调节内电势dq轴分量。

上述相位的关系如图1所示。

![](images/e72db2e421ef080d36b3e4700b82bd6b92f24c40a764e96c57e815ddb03f53c9.jpg)  
图1矢量关系图Fig.1Vector diagram

# 1问题描述

# 1.1设备工作原理介绍

同步机通过电磁感应形成内电势，实现机电能量转换；变流器通过开关器件导通与关断，控制电场能量传递，实现直流电-交流电的转换。两者的能量转换机制不同，但却具有类似的结构，图2所示的典型结构作为本文的研究对象。

另外，为对比同步机与变流器，同步机考虑励磁绕组、定子、转子与励磁控制，忽略阻尼绕组;变流器模型考虑平均模型下的调制环节、滤波电感和控制系统。

同步机：同步发电机由定子电枢与转子组成，转子直交轴被定义为同步机dq轴。同步机转子d轴缠绕单轴励磁绕组，在励磁控制作用下通入励磁电势，如图2所示。其中d轴动态包含励磁绕组动态、励磁控制动态；q轴无动态；控制坐标系相位由转子摇摆生成。

变流器：变流器的dq 控制同样在自身控制坐标系下进行，其中PLL-VSC 和VSG的dq轴动态分别为功率-电流双环控制和电压-电流双环控制的动态，控制坐标系相位分别由锁相环和虚拟同步控制的动态决定，如图2所示。

![](images/32bf6c47185f6c4bb456fa60cf41a3ebb5afc497bd202ef9eb32115566a896f0.jpg)  
图2同步机与变流器的对比示意图

# Fig.2 Comparison diagramof synchronous machine and converter

# 1.2同步稳定的统一建模需求

由于PLL-VSC与构网设备的同步机制存在较大差异，它们的建模方法也完全不同，使得如图3所示的互联系统模型中设备与网络的接口变量多种多样，且缺乏清晰的物理意义。另外，VSG在触发电流限幅后会在电压源与电流源间切换，甚至出现复杂的非线性失稳现象[5]。该切换为传统建模中的网络模型与设备模型均引入了不连续和不可解析的函数，在大规模系统的分析中产生严重的维数灾，加剧了互联系统同步稳定分析的困难，从而难以从系统需求角度对VSG提出暂态控制改进方法。

![](images/9a9a476ce8eb7b5151f18315888063183b4dd4abf261874119e26e46fce5e8bb.jpg)  
图3跟网设备与构网设备互联系统示意图Fig.3 Interconnection System Diagram

虽然跟网设备和构网设备存在上述差异，但整体结构相似：同步机与变流器动态均由控制坐标系动态，d轴动态和q轴动态组成。其中，工作原理都是dq轴动态决定输出电压/电流的幅值和定向相位，控制坐标系相位与定向相位共同组成输出电压/电流相位。如果能基于这种相似性建立统一的模型，理解锁相、虚拟同步与转子运动这几种同步机制之间的联系，统一设备与网络的接口变量并避免VSG建模视角的频繁切换，将大大简化互联系统稳定分析的复杂度。因此，有必要深入研究构网设备和跟网设备的区别，探索统一建模方法。

# 1.3拟解决的问题

鉴于目前对于同步机与变流器内在的共性与差异尚不清晰，为了建立适用于同步稳定分析的模型，这背后存在两个问题需要探讨，并分别在第2节和第3节进行了回答。

问题1：同步原理的统一理解方式。同步机通过转子实现控制坐标系相位的动态调整，变流器通过同步控制如锁相环/虚拟同步实现控制坐标系相位的动态调整。如何理解同步机与变流器同步机制的异同之处，解释两者的同步原理？

问题2：同步机制的统一描述方法。同步稳定分析时，同步机被建模为电压源，而变流器有多种建模方式：内电势建模[11]、输出电流建模[12]等。建模方法的差异导致互联系统同步稳定分析十分困难。是否存在合理的建模方法将同步机与变流器用统一的数学方程描述，从而便于分析互联系统同步稳定并进一步指导变流器控制设计？

本文借鉴传统同步机的研究与建模思路[4]，从等效物理意义、详细模型、简化实用模型与简化模型下的同步稳定机理分析几方面开展互联系统同步问题的初步探索。

# 2基于双轴同步机概念的等效结构

本节基于双轴同步机的概念构建了同步机与变流器的统一等效结构：由虚拟“转子”与缠绕在“转子”上的双轴等效“绕组”组成，如图4(a)所示。这种双轴同步机在俄罗斯的实际工程中得到了应用[25]，由于在同步机转子dq轴均缠绕励磁绕组同时控制内电势dq轴分量，可以实现内电势定向相位的灵活控制，故在暂态功角稳定增强方面体现了良好的性能。相比较，目前常见的同步机仅存在单轴励磁绕组，其内电势定向相位不由控制决定，天然定向于转子d轴，可看成双轴同步机略去 $\mathsf { q }$ 轴励磁的特例。

![](images/996581648ad321f68f0a9733416075fd17c8292818fbcaba58057522605688e3.jpg)  
Fig.4 Unified understanding of the perspective of dual axis synchronous machines

# 2.1“转子”同步的统一理解

如图4(b)所示，同步机与变流器的控制坐标系动态均可表示为 $\omega = G _ { \scriptscriptstyle w } \big ( s \big ) \big ( M _ { \scriptscriptstyle r e f } - M \big )$ 。其中， $M$ 表示设备的同步信号，PLL-VSC的 $M$ 为电压 $\mathsf { q }$ 轴分量；VSG/同步机的 $M$ 为有功功率； $G _ { \scriptscriptstyle { w } } { \big ( } s { \big ) }$ 为同步动态过程，表示为惯性环节或PI环节。因此，变流器的控制坐标系可理解为由“转子”摇摆生成，与同步机不同的是“转子”的驱动量 $M$ 可自由选择而不是有功功率。在等效的虚拟“转子”结构下，借鉴传统同步机的同步原理，同步机与变流器的同步过程可统一描述为：在“转子”驱动量与其参考量的不平衡作用下，“转子”不断摇摆调整控制坐标系相位达到平衡，实现设备控制坐标系与电网的同步(即“虚拟功角” $\delta$ 的同步，如图1所示)。

# 2.2dq轴等效电路的统一理解

进一步比较双轴同步机与PLL-VSC的动态，如图4(b)所示，符号意义可参考3.3节。对比发现，PLL-VSC的内环控制、滤波电感和双轴同步机励磁绕组、定子电枢均表征了设备电压/电流dq轴分量间的线性关系，区别在于控制决定的动态方程具有不同形式。值得一提的是当双轴同步机励磁控制改造为磁链和电压前馈的电流控制，其dq轴动态将与变流器相似(可参考同步运行的双馈风机)。

注：双馈风机也是典型的双轴发电机结构，区别在于其励磁电势为交流量，本文不对此深入讨论，

将在后续研究继续展开。

同步机通常被理解为暂态电势/次暂态电势（下文简称为内电势)幅值恒定的电压源，其转子绕组与定子电枢等效为dq 轴电路下的阻抗，如图5(a)所示。因此，同样可以将表征变流器电压/电流dq 轴动态的环节(PLL-VSC的电流内环与滤波器，VSG的电压-电流双环与滤波器)理解为“绕组"，并可被表示为dq 轴电路，等效为图5(a)或图5(b)的一种。同步机与变流器dq轴电路的动态过程可统一描述为：输出电压或电流在电路瞬态过程中快速地实现幅值与定向相位的稳定。

![](images/b12b3a21c618a12226f51bd10aef9627cb0981c246163424864638d86c2a2fe2.jpg)  
图4双轴同步机下的统一理解  
图5设备dq轴等效电路  
Fig.5Device dq axis equivalent circuit

需要说明，同步机与变流器的dq轴动态被统一表示是为了从电路层面理解两者接入电力系统的工作原理，但机侧能量注入方式是不同的：同步机是磁场能量到电场能量的转换过程，变流器是电路上直接从直流侧向交流侧注入能量，能量注入的差异也是两者 dq 轴电路动态不同的原因之一。当考虑同步机的阻尼绕组时，其映射到电路中相当于引入了更复杂的电路动态，表现为等效电抗相位的滞后[27]，并不改变电路动态本质。

相应地，有了“转子”与“绕组”的等效，PLL-VSC的功率/直流电压控制和VSG的无功外环控制可等效理解为“励磁控制”系统。

经过上述对比可以发现，变流器与同步机具有完全相同的等效结构，都可统一用“双轴同步机”描述，由等效的“转子”和dq轴“绕组”组成，分别主导设备的同步过程与电路动态过程。

# 3基于双轴电流源同步机的建模

# 3.1基于电流源的设备建模思路

设备在等效电路中表现为电压源/电流源特性与状态空间模型的输出变量采用电压/电流相对应。但目前变流器在同步稳定分析时究竟采用何种建模方法尚缺乏科学的解释。本小节将兼顾设备模型鲁棒性与同步稳定分析便捷性，提出同步机与变流器的统一电流源建模思路。

# (1）设备模型的鲁棒性

一个具有鲁棒性的设备模型，应当在考虑建模误差等不确定性因素后的稳定分析结果不会大幅变化[2]。线性化模型的鲁棒性是原始非线性模型鲁棒性的必要条件，故线性化模型的鲁棒性就是基本条件之一。例如，针对频域模型 ${ \boldsymbol { y } } = { \boldsymbol { T } } { \left( s \right) } u$ （当 $y$ 为输出电压或电流时，对应的 $T ( s )$ 为阻抗或导纳传递函数矩阵，如图5所示)，该模型是否合理可以从物理和数学两个角度考虑：

物理依据：内阻抗/内导纳越小，设备越接近理想电压源/电流源。

数学依据：阻抗或导纳矩阵的无穷范数(最大奇异值， $\forall \omega : \overline { { \sigma } } \big ( \mathbf { Z } \big ( j \omega \big ) \big )$ 或 $\forall \omega : \overline { { \sigma } } \big ( \mathbf { Y } \big ( j \omega \big ) \big ) .$ )越小，基于电压源/电流源描述的模型鲁棒性高。

注：较大的奇异值意味着设备模型对外部误差的放大倍数更大，未建模部分造成的误差可能会使分析的稳定裕度大幅变化[22]。从数值的仿真分析看，截断误差会在设备模型中放大，造成误差传播[24]。上述两种情况还将在后文算例中进一步讨论。

在同步稳定分析的频段内，变流器采用电流源或电压源模型的鲁棒性讨论参照附录A，正文中不再详细展开，只给出对应结论，如表1所示。

(2）同步稳定分析与控制设计的便捷性

互联系统中电压源/电流源混联建模方式使得网络形式复杂，不利于理解系统同步稳定机理，因此有必要对变流器和同步机进行统一建模。如表1所示，统一建模为电流源可以保证较好的鲁棒性。

另外，在单PLL-VSC 并网系统的同步稳定分析中，已经有大量研究表明相较于电压源建模，电流源建模有着将输出同步转化为状态同步的优势，便于采用解析方法进行分析[16][23]。诺顿等效下同步机/VSG等值为节点注入电流后，其等值电流相位也仍为状态变量，同样方便分析。

将变流器与同步机均建模为电流源，同步机的等效电流由内电势诺顿等效得到[4]，如图6所示。在采用六阶模型或四阶模型时， $E _ { d q }$ 与 $X _ { d q }$ 为次暂态/暂态参数。VSG网侧滤波器与变压器等效电抗可视作诺顿等效的阻抗，大小与同步机暂态电抗相近，因此诺顿等效后与同步机特性相似。

![](images/5cc19d0aecb569e814085429b1046e331b67950044100a8cfde773c6e7f94f57.jpg)  
图6同步机诺顿等效   
Fig.6 Norton equivalence of synchronous machine

更为重要的是，变流器存在电流限幅约束，这决定了其在短时间过程内必须以电流源模式运行。其中，VSG电流限幅控制导致动态模型存在频繁切换的问题，不利于同步稳定分析，也给VSG的改进控制带来挑战[5]。为了在实现变流器构网支撑功能的同时还便于理解电流限幅前后的系统特性以改进变流器的暂态同步控制，从电流源视角理解VSG的同步具有更便捷的优势。例如，电流源视角建模下VSG在电流饱和前后均为电流源特性，区别仅在于VSG并网节点是否存在诺顿等效的对地电感支路，采用成熟的追加支路等方法可方便地处理网络模型。后续将以此为基础深入研究电流限幅下多VSG的同步稳定分析。

# 3.2设备同步动态的数学描述方法

本节以PLL-VSC 与同步机对比为例，如图 7所示，VSG建模方法同理，本文不再赘述。

同步信号的统一：同步机/VSG与PLL-VSC的同步信号分别为有功功率和端口电压q轴分量。有文献指出PLL-VSC在单位功率因数下运行时其同步信号可视作是无功功率，电流幅值为同步回路的增益系数[2I]。但当PLL-VSC 运行在非单位功率因数时，无功功率描述不够准确，此时 $\mathsf { q }$ 轴电压可表示为

$$
V _ { _ q } = \frac { S } { I } \mathrm { s i n } \left( \theta _ { _ V } - \theta _ { _ I } + \theta _ { _ { d q I } } \right) = \frac { S } { I } \mathrm { s i n } \left( \varphi - \varphi _ { _ 0 } \right)
$$

$$
= \frac { - \sin \varphi _ { \mathrm { 0 } } P + \cos \varphi _ { \mathrm { 0 } } Q } { I }
$$

其中 $S = W$ 为端口复功率幅值， $\varphi$ 为功率因数角，9=-0dq,为功率因数角参考值。

表1设备不同建模方式的比较  
Tab.1 Comparison of equipment external characteristics modeling   

<html><body><table><tr><td>建模 方法</td><td>VSG/同步机：端口电压/内电势 PLL-VSC：输出电流</td><td>VSG/同步机：端口电压/内电势诺顿等效 PLL-VSC：输出电流</td><td>VSG/同步机：端口电压/内电势 PLL-VSC：内电势</td></tr><tr><td>鲁棒性</td><td>鲁棒性最好</td><td>鲁棒性较好</td><td>鲁棒性差</td></tr><tr><td>分析 控制</td><td>网络表示复杂不利于分析，难指导控 制</td><td>网络表示为阻抗矩阵便于分析，可指导 VSC 电流限幅控制</td><td>网络表示为导纳矩阵便于考虑VSC 不饱 和下的分析，但难以指导VSC 电流限幅 控制</td></tr></table></body></html>

![](images/c8505d1963b84ab009c4cd3aeb5c6aae209ee960859d4ee7824b1234e76097c1.jpg)  
图7变流器与同步机同步机制的统一建模

Fig.7 Unified Modeling of Synchronization Mechanism between Converter and Synchronous Macl

同步机/VSG的同步信号可表示为

$$
P _ { M } - P = S _ { 0 } \cos \varphi _ { 0 } - S \cos \varphi
$$

其中，同步机/VSG 的 $S _ { 0 }$ 和 $\varphi _ { \mathrm { 0 } }$ 为稳态下平衡点处复功率幅值和功率因数角。

在额定工作点附近同步机/VSG的同步信号近似为 $S _ { 0 } \left( \cos \varphi _ { \mathrm { 0 } } - \cos \varphi \right)$ 。可以发现，同步机与变流器同步信号都是功率因数角的函数 $f \left( \varphi _ { \mathrm { 0 } } , \varphi \right)$ 。因此，变流器与同步机均可视作电流相位对并网点电压相位的跟踪，并保证最终两者相位差为 $\varphi _ { \mathrm { 0 } }$ ，即同步过程可理解为功率因数的跟踪过程[28](对于同步机而言，同步是功角跟踪其稳态值，诺顿等效后表现为功率因数角的跟踪)。

同步方程的统一：同步机和VSG 的同步动态为一阶惯性环节 $1 / { \left( 2 H s + D \right) }$ ，PLL-VSC 的同步动态为PI控制 $k _ { p l l p } + k _ { p l l i } / s$ 。在控制理论中两者均可理解为反馈控制器，在设计控制时采用超前滞后传递函数 $K { \big ( } s + b { \big ) } / { \big ( } s + a { \big ) }$ 可将一阶惯性和 PI控制统一，进一步写为 ${ \left( T _ { p } s + K _ { I } \right) } \mathord { \left/ { \vphantom { \left( T _ { p } s + K _ { I } \right) } } \right. \kern - delimiterspace } { \left( T _ { J } s + K _ { D } \right) }$ 。统一同步机制的时域方程如图7的 $\mathsf { c } ( 4 )$ 所示。

# 3.3设备dq轴等效电路动态的数学描述方法

变流器与同步机的电流动态均可写为

$$
\begin{array} { r }  \Big [ I _ { d } ^ { \phantom { \dagger } } \Big ] = \underbrace { \Big [ \begin{array} { c c } { G _ { d } \left( s \right) } & { 0 } \\ { 0 } & { G _ { q } \left( s \right) } \end{array} \Big ] } _ { \mathrm { G } \left( s \right) } \Big [ \begin{array} { c } { I _ { d } ^ { \ast } } \\ { I _ { d } ^ { \ast } \Big ] - \Big [ \begin{array} { c c } { G _ { R } \left( s \right) } & { B _ { q } \left( s \right) } \\ { B _ { d } \left( s \right) } & { G _ { R } \left( s \right) } \end{array} \Big ] \Big [ V _ { q } ^ { \phantom { \dagger } } \Big ] } \\ { \mathrm { G } \left( s \right) } \end{array} \end{array}
$$

电流方程对应等效电路图见图5(b)， $\mathbf { G } { \big ( } s { \big ) }$ 与$\Upsilon ( s )$ 的具体表达式见图7式(a1)(b1)。PLL-VSC的电流参考值由外环控制给定(本节以PQ外环为例，其他外环同理，在此不再赘述)，同步机电流参考值由励磁控制给定，见图7式(a2)(b2)，具体推导见附录A。其中， $P I _ { \cal I } \left( s \right)$ 和 $P I _ { o } ( s )$ 表示内环和外环PI控制方程， $T _ { \nu }$ 是内环前馈滤波常数， $L _ { \scriptscriptstyle F }$ 是滤波电感;$T _ { d q } ^ { ' }$ 和 $T _ { d q } ^ { " }$ 分别为dq 轴的暂态/次暂态时间常数， $X _ { d q } ^ { ' }$ 和 $\boldsymbol { X } _ { d q } ^ { " }$ 是dq轴暂态/次暂态电抗，$a _ { d } = \bigl ( X _ { d } - X _ { d } ^ { \circ } \bigr ) \bigl / \bigl ( X _ { d } ^ { \circ } - X _ { d } ^ { \circ } \bigr )$ ， $a _ { \scriptscriptstyle q } = \bigl ( X _ { \scriptscriptstyle q } - X _ { \scriptscriptstyle q } ^ { \cdot } \bigr ) \bigl / \bigl ( X _ { \scriptscriptstyle q } ^ { \cdot } - X _ { \scriptscriptstyle q } ^ { \cdot } \bigr )$ $H _ { d q } \left( s \right) = { \left( T _ { d q } ^ { \circ } T _ { d q } ^ { \prime } s ^ { 2 } + \left( T _ { d q } ^ { \prime } + T _ { d q } ^ { \prime } a _ { d q } \right) s + 1 \right) } \mathord { \left/ { \vphantom { \left( T _ { d q } ^ { \circ } T _ { d q } ^ { \prime } \right) s ^ { 2 } } \left( a _ { d q } + s T _ { d q } ^ { \prime } \right) } \right. \kern - delimiterspace } { \left( a _ { d q } + s T _ { d q } ^ { \prime } \right) }$ ， $G _ { \nu } \left( s \right)$ （204号为励磁控制方程。VSG同样可以写为式(3)的形式，区别在于 VSG 的 $\operatorname { G } ( s )$ 与 $\Upsilon ( s )$ 为电压-电流双环控制动态，对此不再展开。

表2PLL-VSC不同阶数的模型表示  
Tab.3Model representationwith different orders   

<html><body><table><tr><td></td><td>10阶</td><td>8阶</td><td>4阶</td><td>2阶</td></tr><tr><td>Gvsc(s)</td><td>图6式(b1)</td><td>图6式(b1)</td><td>12x2</td><td>12x2</td></tr><tr><td>Yvsc(s)</td><td>图6式(b1)</td><td>02x2</td><td>02x2</td><td>02x2</td></tr><tr><td>外环</td><td>图6式(b2)</td><td>图6式(b2)</td><td>图5式(b2)</td><td>Idq= Id</td></tr></table></body></html>

所建立的电流方程考虑了PLL-VSC和同步机的全阶动态。在传统电力系统分析中，同步机的模型根据分析需求可降阶为简化实用模型。对于PLL-VSC而言，在分析不同问题时也可根据需求降阶为简化实用模型：当分析锁相环主导的稳定性时，根据奇异摄动理论可知，内环与滤波电感动态远快于锁相环，当其主导特征值均在左半平面，可忽略前馈和内环快动态(4 阶)，即 ${ \bf G } _ { _ { V S C } } \left( s \right) = { \bf 1 } \ , \ { \bf Y } _ { _ { V S C } } \left( s \right) = { \bf 0 }$ 。当外环动态远慢于锁相环时，可以进一步简化，认为 $\boldsymbol { I } _ { d } ^ { * }$ 与 $\boldsymbol { I } _ { q } ^ { * }$ 不变(2 阶)。因此，根据同步稳定分析的需求，也可将PLL-VSC的模型降阶为简化模型，如表2所示。

# 3.4讨论

基于双轴同步机概念与电流源建模方法，构网设备与跟网设备被统一表征为双轴电流源同步机模型，两者的区别被转化为参数与功率因数的不同。例如，等效“绕组”均表示为二阶导纳形式(图7式(a1)与(b1))，但参数不同；另外，如式(1)所示，PLL-VSC与构网设备“转子”驱动量的差异可理解为功率因数不同，当PLL-VSC运行功率因数为0时，V =P/I。，此时 PLL-VSC 也等效为有功功率同步；而PLL-VSC运行功率因数为1时，则其等效为无功功率同步。因此，以功率因数为0的PLL-VSC 为例，其控制参数设计成与构网设备对应的环节相同时，同样可以表现为构网的特性，这在文献[21]中已经有相应的论述。

# 4同步稳定分析

# 4.1同步稳定的定义

在物理学中，同步被定义为振荡子之间因为相互作用而导致的相位调整，同步稳定指各个振荡子维持同步的能力[23]。本文侧重于考虑频率同步(相角锁定)，其含义具体如下：在含有 $n$ 个振荡子的复杂系统，第 $i$ 个振荡子的相位为时间 $t$ 的函数，表示为 $\theta ( t )$ ，频率则表示为 ${ \dot { \theta } } ( t ) ^ { [ 2 3 ] }$ 。系统中每个振荡子的频率将收敛到一个恒定的共同频率值，此时各振荡子间的相位差也维持恒定。

网络也建立状态空间方程，与设备模型通过输入/输出作为接口连接，互联系统可表示为图8。因此，该互联系统中振荡子同步即为各设备在网络耦合下的同步。有了双轴电流源同步机模型与传统同步机模型的对比，可将互联系统同步稳定描述为“虚拟功角[23]”的同步稳定，即设备控制坐标系相位间的相角锁定，其数学定义为：

$$
\operatorname * { l i m } _ { t  \infty } \delta _ { i j } ( t ) = \operatorname * { l i m } _ { t  \infty } \theta _ { s i } ( t ) - \theta _ { s j } ( t ) = \delta _ { i j 0 } , \forall i , j
$$

其中 $\theta _ { s i }$ 和 $\theta _ { s j }$ 分别为第i个和第 $\mathrm { j }$ 个设备的控制坐标系相位。

传统电力系统的功角稳定是式(4)的等效描述(控制坐标系相位与内电势相位重合)，对应于电流源视角下的互联系统：变流器内环主导的稳定是电气谐振稳定[]，当内环稳定且足够快的前提下，即上文所述可忽略内环动态，简化后同步机与变流器的电流相位为“虚拟功角”的代数方程；此时，同步稳定描述为变流器输出电流和同步机/VSG诺顿等效电流的相角锁定，如图9(b)所示。

![](images/491c37d1461663495c2214ecc5c0ae44bb0a0f01c33b2ae6453ad5d86294a67a.jpg)  
Fig.8 Schematic diagramofstate space model

![](images/445c8992466a5a557f052e4c3e70a295460bb1150478b69fbc347d71ccd97aa0.jpg)  
图8状态空间模型示意图  
图9多机互联系统的示意图  
Fig.9Schematic diagramofinterconnectionsystem还值得一提的是，虚拟功角与简化模型下的电

流相位都是状态变量，可借鉴传统电力系统的状态同步特性认识互联系统的复杂同步问题[23]。在稳态下，虚拟功角与电压相位重合，在工程实际中仍然可以用设备间电压的相位差是否越界做实用化的同步稳定判据。

# 4.2网络的简化模型

互联系统中同步机与变流器的动态经过网络耦合，工频相量模型忽略了网络动态（表示为潮流方程）会引起较大误差[2]。为弥补这一问题，下文将在设备自身控制坐标系下建立网络模型，在保证精度的同时简化互联系统的复杂度。

不失一般性且为了表述简单，在如图9(a)所示系统中，网络仅考虑电感而忽略电阻和对地电容。节点消去后， $L _ { _ { i j } }$ 表示工频标幺值下节点 $i$ 与节点 $j$ 间的等效电感值，网络动态方程可写为

$$
\begin{array} { l } { { \{ [ { \cal { V } } _ { i d } ] = \displaystyle \sum _ { j = 1 } ^ { n } \Gamma _ { j i } (  \omega _ { j } L _ { i j } [ I _ { j d } ] + \displaystyle \frac { L _ { i j } } { \omega _ { 0 } } [ \displaystyle \frac { d I _ { j d } } { d t } ] ) } } \\ { { [ \displaystyle \Gamma _ { j i } = [ \displaystyle \cos \delta _ { i j }  \quad \sin \delta _ { i j } ]  } } \\ { {  - \sin \delta _ { i j } \quad \cos \delta _ { i j } ] } } \end{array}
$$

其中， $\omega _ { 0 } = 1 0 0 \pi \big ( r a d / s \big )$ ， $\omega _ { j }$ 为第 $j$ 个设备控制坐标系旋转角频率； $V _ { i d q }$ 和 $I _ { i d q }$ 表示节点 $i$ 的节点电压和注入电流在自身控制坐标系的dq 轴分量； $T _ { j i }$ 表示节点 $j$ 控制坐标系到节点 $i$ 控制坐标系的变换矩阵。获得式(5)的详细推导见附录B。

和机电暂态模型相比，上述方法将设备角频率变化与线路的耦合表示在代数项 $\omega _ { j } L _ { i j }$ 中，避免了前者忽略微分动态而造成误差较大的问题，精度对比具体见后文算例。类似地，在忽略网络微分动态后，可将RL负荷作为无源节点消去(见式(6))，将吸收功率的储能等负荷看成并网设备并在自身坐标系建立实用化模型。

$$
\left[ V _ { i d } \atop V _ { i q } \right] = \sum _ { j = 1 } ^ { n } \left( \mathrm { T } _ { j i } \left[ R _ { i j } \begin{array} { c c } { R _ { i j } } & { - \omega _ { j } L _ { i j } } \\ { \omega _ { j } L _ { i j } } & { R _ { i j } } \end{array} \right] \left[ I _ { j d } \atop I _ { j q } \right] \right)
$$

# 4.3互联系统的简化模型

以图9(a)所示系统为例，纯感性网络连接 $n$ 个PLL-VSC和 $m$ 个同步机的系统。结合简化下表2的2阶设备模型和式(6)的网络简化模型，可在图7式(c4)基础上，形成第 $i$ 个设备电流相位 $\theta _ { _ { I i } }$ 与网络的闭环二阶方程：

$$
\begin{array} { l } { \displaystyle { \{ \frac { d \theta _ { I i } } { d t } = \frac { T _ { P i } } { T _ { J i } } \Biggl ( M _ { r e f i } - \sum _ { j = 1 } ^ { n } I _ { j } \omega _ { j } L _ { i j } \sin ( \theta _ { i j } - \alpha _ { i } ) \Biggr ) + \tilde { \omega } _ { i } } } \\ { \displaystyle { T _ { J i } \frac { d \tilde { \omega } _ { i } } { d t } = M _ { r e f i } - K _ { I i } \sum _ { j = 1 } ^ { n } I _ { j } \omega _ { j } L _ { i j } \sin ( \theta _ { i j } - \alpha _ { i } ) - K _ { D i } \tilde { \omega } _ { i } } } \end{array}
$$

其中电流幅值为定值， $\theta _ { _ { I i } } { = } \theta _ { _ { s i } } { + } \theta _ { _ { d q I i } }$ ， $\theta _ { i j } = \theta _ { I i } - \theta _ { I j }$ ，同步机 $\alpha _ { i } = 0$ ，变流器 $\alpha _ { i } = \theta _ { \mathit { d q I i } } + \pi / 2$ ，其余变量具体含义见图7。

由于 $\omega _ { i } = d \theta _ { i } / d t + \omega _ { 0 }$ ，进一步可将式(7)的平衡点平移到原点，简化过程见附录B，可得：

$$
\left\{ \begin{array} { l } { \displaystyle \frac { d \theta _ { i } } { d t } = \frac { N _ { i } T _ { \rho _ { i } } } { T _ { i } } \bigg ( M _ { r e \theta } - \sum _ { j = 1 } ^ { n } I _ { j } X _ { \ell } \sin \big ( \theta _ { i j } - \alpha _ { i } \big ) \bigg ) + \tilde { \mathcal { O } } _ { i } } \\ { \displaystyle ~ - \frac { T _ { \rho _ { i } } } { T _ { i } } \sum _ { j = 1 } ^ { n } I _ { j } \frac { L _ { \rho _ { i } } } { \omega _ { 0 } } \sin \big ( \theta _ { i j } - \alpha _ { i } \big ) \tilde { \omega } _ { j } } \\ { \displaystyle T _ { n } \frac { d \tilde { \omega } _ { i } } { d t } = M _ { r e \theta } - K _ { n } \sum _ { j = 1 } ^ { n } I _ { j } X _ { \ell } \sin \big ( \theta _ { i j } - \alpha _ { i } \big ) } \\ { \displaystyle ~ - \frac { K _ { n } T _ { \rho _ { i } } } { T _ { n } } \sum _ { j = 1 } ^ { n } I _ { j } \frac { L _ { \tilde { \boldsymbol { \eta } } _ { i } } } { \omega _ { 0 } } \sin \big ( \theta _ { i j } - \alpha _ { i } \big ) \tilde { \omega } _ { j } - K _ { D i } \tilde { \omega } _ { i } } \end{array} \right.
$$

其中 $X _ { _ { i j } } = L _ { _ { i j } }$ 表示节点 $i$ 和节点 $j$ 之间在工频下的等效感抗， $N _ { i } = 1 + K _ { p i } I _ { i } \left( X _ { i i } / \omega _ { \mathrm { 0 } } \right) \sin \alpha _ { i }$ ， $\tilde { \omega } _ { i }$ 为工频的相对角频率，稳态下为0。

式(8)构成了互联系统同步稳定分析的简化模型，后文简称简化模型

进一步，将式(8)进行线性化，可得到如下以状态空间表示的互联系统线性化模型

$$
\underbrace { \left[ \begin{array} { l l } { \mathrm { I } } & { 0 } \\ { 0 } & { \mathrm { H } } \end{array} \right] } _ { \mathrm { M } } \left[ \begin{array} { l } { \Delta \dot { \Theta } } \\ { \Delta \dot { \tilde { \Theta } } } \end{array} \right] = \underbrace { \left[ \begin{array} { l l } { \mathrm { K } _ { \mathrm { p } } \mathrm { N } _ { \mathrm { I m } } } & { \mathrm { I } + \mathrm { K } _ { \mathrm { p } } \mathrm { N } _ { \mathrm { R e } } } \\ { \mathrm { N } _ { \mathrm { I m } } } & { \mathrm { D } _ { \mathrm { S G } } + \mathrm { N } _ { \mathrm { R e } } } \end{array} \right] } _ { \mathrm { A } } \left[ \begin{array} { l } { \Delta \Theta } \\ { \Delta \tilde { \Theta } } \end{array} \right]
$$

其中， $\Delta \boldsymbol { \Theta } = \big [ \Delta \boldsymbol { \Theta } _ { _ { V S C } } , \Delta \boldsymbol { \Theta } _ { _ { S G } } \big ] ^ { T }$ ， $\Delta \tilde { \omega } = \big [ \Delta \tilde { \omega } _ { { V S C } } , \Delta \tilde { \omega } _ { { S G } } \big ] ^ { T }$ ;$\begin{array} { r } { \mathbf { K _ { \mathrm { p } } } = d i a g \left\{ N _ { \mathrm { l } } T _ { \ L _ { p 1 } } / T _ { \ L _ { J 1 } } , . . . , N _ { \ L _ { ( m + n ) } } T _ { \ L _ { p ( m + n ) } } / T _ { \ L _ { J ( m + n ) } } \right\} \ L } \end{array}$ ： $\mathrm { \Delta N _ { \mathrm { { I m } } } }$ 的非对角元素 $\begin{array} { r } { N _ { _ { \mathrm { 1 + \eta } } \mathrm { I m } ( i , j ) } = I _ { i } I _ { j } X _ { i j } \cos \bigl ( \theta _ { i j } - \alpha _ { i } \bigr ) } \end{array}$ ，对角元素为$\mathrm { N } _ { \mathrm { I m } ( i , i ) } = - \ \sum { \cal I } _ { i } { \cal I } _ { j } X _ { i j } \cos \left( \theta _ { i j } - \alpha _ { i } \right) ;$ $\Nu _ { \mathrm { R e } }$ 的元素为${ \bf N } _ { \mathrm { R e } ( i , j ) } = - \bar { I } _ { i } ^ { \bar { 1 } } { \cal I } _ { j } ^ { j \ne i } { \cal X } _ { i j } \sin \bigl ( \theta _ { i j } - \alpha _ { i } \bigr ) \ ; \quad \mathrm { H } = d i a g \left\{ { \cal T } _ { J 1 } , . . . , { \cal T } _ { J ( m + n ) } \right\}$ ；$\mathrm { D } _ { \scriptscriptstyle \mathrm { S G } } = - d i a g \left\{ K _ { \scriptscriptstyle { D 1 } } , . . . , K _ { \scriptscriptstyle { D ( m + n ) } } \right\} \ : \mathrm { ~ c ~ }$

# 4.4互联系统的同步稳定充分条件

在式(8)所示的互联系统中，一个重要的科学问题是该系统如何在平衡点邻域内维持同步稳定，即互联系统同步稳定的条件。下面利用线性化方法分析系统的同步问题，即分析模型(9)的同步特性。

式(9)所示系统存在一个零特征值和 $2 ( \mathrm { m } \mathrm { + n } \mathrm { - } 1 )$ 个共轭的复特征值。其中零特征值意义类似于传统同步机的惯量中心，表征互联系统频率“中心”，而其它共轭复根表征了各个设备相对摇摆模态，当共轭复根实部小于0表示系统是同步稳定的。物理意义为：在平衡点的邻域内，扰动后各个设备的相位最终会形成满足 $\Delta \theta _ { i j } = 0$ 的平衡流形，各个设备的频率等于零特征值对应的“中心频率”。

定理1(小干扰同步稳定条件)：当 $\mathrm { K } _ { \mathrm { p } }$ 与 $\mathrm { \Delta D _ { S G } }$ 中参数为正且足够大(远大于 $\mathbf { N } _ { \mathrm { R e } }$ 中元素)时，式(9)特征根实部小于0，互联系统可保持同步稳定；反之可能失稳。

证明：见附录C。

值得特别指出的是，构网设备惯量系数远远大于PLL-VSC锁相环时间常数的情况为式(9)的一种特例，上述充分条件仍然满足，此时系统同步过程为：PLL-VSC子系统的同步动态为快流形，先实现同步稳定；构网设备子系统同步动态为慢流形，其内部同步过程中PLL-VSC的相位可认为是理想跟随构网设备相位，直到构网设备子系统实现同步。

通过上述定理可推知， $\Nu _ { \mathrm { R e } }$ 元素表征设备频率变化与网络的耦合阻尼效应，在PLL-VSC中表现为负阻尼。如果网络建模为传统工频相量下的机电模型，相当于式(9)中 $\Nu _ { \mathrm { R e } } = 0$ ，即忽略了网络耦合下的负阻尼效应。另外，设备中 $\mathrm { K } _ { \mathrm { p } }$ 与 $\mathrm { \Delta D } _ { \mathrm { S G } }$ 为阻尼系数，大于0时呈现正阻尼作用。当阻尼系数可补偿网络负阻尼时，能保障平衡点处的同步稳定；若阻尼系数不足以补偿网络负阻尼，则系统会发生同步失稳

上述分析结果是在线性化模型下进行的，如何利用简化模型(8)将传统的暂态功角稳定分析方法拓展到互联系统的暂态同步稳定分析中，是未来需进一步开展的工作。

# 5算例

在MATLAB/Simulink中搭建仿真模型，验证上述理论的合理性，所用参数见文献[9][26]。

# (1）设备模型鲁棒性分析验证

在单机PLL-VSC并网系统中验证设备电压源建模和电流源建模的鲁棒性，此时网络模型分别记为导纳 $Y _ { g } \left( s \right)$ 和阻抗 $Z _ { g } \left( s \right)$ 。为表征网络中的不确定性，对模型进行大小相同、方向任意的乘性摄动，得到考虑不确定性的网络模型 $Y _ { g } \left( s \right) \Delta _ { e i }$ 和 $Z _ { g } \left( s \right) \Delta _ { e i }$ ，其中， $\Delta _ { e i } = 1 + \delta _ { e i } e ^ { j \theta _ { e i } } , \theta _ { e i } \in \left[ 0 , 2 \pi \right)$ 。以相同强度的扰动 $\delta _ { e i } = 5 \%$ 为例，奇异值更大的设备模型对外部误差更灵敏，会导致锁相环主导特征值误差更大，结果如图10所示。由该图可知，相同强度扰动下电压源建模相比于电流源建模的锁相环主导特征值变化更大，这与奇异值所分析的结果一致，说明同步稳定分析时采用电流源模型具有更好的鲁棒性。

进一步，采用上述模型验证仿真时的数值鲁棒性。在0.05s时在PLL-VSC 端口注入电流扰动，分别采用步长 $1 0 ^ { - 4 } \mathrm { s }$ ， $1 0 ^ { - 5 } \mathrm { s }$ ， $1 0 ^ { - 6 } \mathrm { s }$ 进行仿真，结果如图

11所示，可以发现电压源建模相比于电流源建模需要更小的步长才能实现仿真的数值稳定，说明电流源模型具有更好的数值鲁棒性。

$\times$ 电流源建模特征值虚部 ×电压源建模特征值  
55.1七 xXx X X X xX摄动前特征值 +车车区  
54.9 X  
54.8 +++ X xxxxx 十十十+车 实部-3.6 -3.55 -3.5 -3.45 -3.4 -3.35 -3.3

![](images/5a5dd4566edf43209811cc9b24ba0b6c99b7c782ce92000115eb85f495412003.jpg)  
图10摄动下锁相环主导特征值变化 Fig.10 Change in perturbation eigenvalues   
图11不同步长下的仿真结果

(2）互联系统简化模型有效性验证

搭建两区四机模型[26验证简化模型的有效性(两区域各接入一个PLL-VSC和同步机)， $\mathrm { { \ t = 0 . 1 s } }$ 时施加三相接地短路故障，并在 $\scriptstyle { \mathrm { t = } } 0 . 2 { \mathrm { s } }$ 时清除，比较详细电磁模型(模型1)，传统机电模型(模型2)和所提简化模型(模型3)的时域响应轨迹。图12分别给出了变流器的q轴电压分量的响应波形。可以看到简化模型与电磁模型在故障清除后的首摆轨迹相近，而传统机电模型与两者有较大的偏差，验证了简化模型的有效性，说明简化模型可较为准确地描述互联系统的同步稳定动态特性。

![](images/151bd31ed1579ce129ff2d28242c58362b472fada98606787e7d36a8132123fe.jpg)  
Fig.11 Simulationresultsunder different step sizes   
图12故障下模型的时域响应对比  
Fig.12 Time domain response comparison of models

(3）同步稳定分析验证

在两区四机模型中， $\scriptstyle 1 = 0 . 5 \mathrm { s }$ 时对变流器施加相位扰动，锁相环输出相位突增1rad，改变PLL-VSC的比例项参数，以变流器和同步机电流相位差 $\theta _ { 1 2 }$ 为例观察系统的稳定性，如图13所示。

其中，当 $k _ { p l l p } { = } 4$ 时，系统振荡失稳； $k _ { p l l p }$ 大于4时，振荡逐渐收敛，系统最终稳定。以 $\mathbf { D } _ { \mathrm { v s c } }$ 最小对角元素大于 $\Nu _ { \mathrm { R e } }$ 最大元素的10 倍为条件，计算得到 $k _ { p l l p } { > } 1 5$ ，即：当 $k _ { P l l p } { > } 1 5$ 时，系统必然是小扰动稳定的，也验证了定理1中结论的正确性。

![](images/9df0bf694fb30b7aca58334e307baffc8ea71a764098002c54c42e920697f569.jpg)  
图13小扰动时域响应波形  
Fig.13 Small disturbance time domain response

# 6 结论与展望

(1）同步机和变流器均可统一理解为“双轴同步机”，两者的动态过程分别为“转子”的同步动态过程和“绕组”的电路动态过程，区别在于“绕组”动态与“转子”驱动变量不同。(2）基于双轴电流源同步机的视角，同步机与变流器的同步特性可以统一表征为状态同步，且它们动态特性的差异可理解为部分参数的不同，方便指导电流限幅约束下变流器同步控制设计。(3）互联系统中，PLL-VSC 的锁相环比例系数或同步机阻尼系数较小时，网络负阻尼效应可能导致系统不稳定；提高锁相环比例系数和同步机阻尼系数有助于提升互联系统同步稳定性。

本文借助双轴电流源同步机的概念对互联系统的同步稳定进行了初步探索，未来需要进一步探索互联系统的其它稳定问题机理及其分析方法。

# 参考文献

[1］辛保安，单葆国，李琼慧，等．“双碳”目标下“能源三 要素”再思考[J]．中国电机工程学报,2022,42(09): 3117-3126. BAOAN X,BAOGUO S, QIONGHUI L, et al. Rethinking of the“Three Elements of Energy”Toward Carbon Peak and Carbon Neutrality [J]. Proceedings of the CSEE,2022, 42(09):3117-3126.   
[2]姜齐荣，赵崇滨．并网逆变器的电磁暂态同步稳定问题 [J]．清华大学学报(自然科学版),2021,61(05):415-428. QIRONG J,CHONGBIN Z. Electromagnetic transient synchronization stability with grid-connected inverters [J]. Journal ofTsinghua University(Science and Technology), 2021,61(05): 415-428.   
[3]WANG X, TAUL M G, WUH, et al. Grid-Synchronization Stability of Converter-Based Resources-An Overview [J]. IEEE Open Journal of Industry Applications,2020,1(115- 134.   
[4] 倪以信，陈寿孙，张宝霖．动态电力系统的理论和分析 [M].：北京：清华大学出版社,2002.   
[5]L.Huang,H.Xin,Z.Wang et al. Transient Stability Analysis and Control Design of Droop-Controlled Voltage Source Converters Considering Current Limitation [J]. IEEE Transactions on Smart Grid, vol.10, no.1, pp. 578- 591, Jan. 2019.   
[6] 宫泽旭，艾力西尔·亚尔买买提，辛焕海，等．新能源电 力系统并网设备小扰动稳定分析(二)：导出机理与稳定 性分类探讨 [J]．中国电机工程学报,1-15. ZEXU G,AILIXIER Y,HUANHAI X, et al. Small Signal Stability Analysis of Grid-connected Equipment in Power System (Part I):Discussion on Mechanism Derivation and Classification of Stability [J]. Proceedings of the CSEE,1- 15.   
[7] AMINM， MOLINASM. Small-SignalStability Assessment ofPower Electronics Based Power Systems:A Discussion of Impedance- and Eigenvalue-Based Methods [J].IEEE Transactions on Industry Applications,2017, 53(5): 5014-5030.   
[8]辛焕海，董炜，袁小明,等．电力电子多馈入电力系统 的广义短路比[J].中国电机工程学报,2016,36(22): 6013-6027. HUANHAI X,WEI D, XIAOMING Y, et al. Generalized Short Circuit Ratio for Multi Power Electronic Based Devices Infeed to Power Systems [J].Proceedings of the CSEE,2016,36(22): 6013-6027.   
[9] 辛焕海，李子恒，董炜，等．三相变流器并网系统的广 义阻抗及稳定判据[J]．中国电机工程学报，2017, 37(05): 1277-1293. HUANHAI X, ZIHENG L, WEI D, et al. Generalizedimpedance and Stability Criterion for Grid-connected Converters [J].Proceedings of the CSEE,2017,37(05): 1277-1293.   
[10]唐王倩云，周保荣，胡家兵，等．锁相同步型风机－同 步机互联电力系统转子转速尺度暂态同步稳定性分析 [J]．中国电机工程学报,2021,41(20):6900-6916. WANGQIANYUN T, BAORONG Z, JIABING H, et al. Transient Synchronous Stability of PLL-based Wind Power-SynchronousGeneration Interconnected Power System in Rotor Speed Control Timescale [J]. Proceedings of the CSEE,2021,41(20): 6900-6916.   
[11]袁豪，袁小明．用于系统直流电压控制尺度暂态过程研 究的电压源型并网变换器幅相运动方程建模与特性分 析[J]．中国电机工程学报，2018,38(23):6882- $6 8 9 2 + 7 1 2 2$ ： HAO Y,XIAOMING Y. Modeling and Characteristic Analysis of Grid-Connected VSCs Based on AmplitudePhase Motion Equation Method for Power System Transient Process Study in DC-Link Voltage Control Timescale [J]. Proceedings of the CSEE,2018,38(23): （20 $6 8 8 2 { \cdot } 6 8 9 2 { + } 7 1 2 2$   
[12] MA R,LI J, KURTHS J, et al. Generalized Swing Equation and Transient Synchronous Stability With PLL-Based VSC [J]. IEEE Transactions on Energy Conversion,2022,37(2): 1428-1441.   
[13] TANG Y, TIAN Z, ZHA X, et al. An Improved Equal Area Criterion for Transient Stability Analysis of ConverterBased Microgrid Considering Nonlinear Damping Effect [J].IEEE Transactions on Power Electronics,2022,37(9): 11272-11284.   
[14] HU Q, FU L, MA F, et al. Large Signal Synchronizing Instability of PLL-Based VSC Connected to Weak AC Grid [J].IEEE Transactions on Power Systems,2019,34(4): 3220-3229.   
[15] ZARIF MANSOUR M,ME S P, HADAVI S,et al. Nonlinear Transient Stability Analysis of Phased-Locked Loop-Based Grid-Folowing Voltage-Source Converters Using Lyapunov’s Direct Method [J]. IEEE Journal of Emerging and Selected Topics in Power Electronics, 2022, 10(3): 2699-2709.   
[16]张宇，张琛，蔡旭，等．并网变换器的暂态同步稳定性 分析：稳定域估计与镇定控制[J].中国电机工程学报, 1-15. YU Z,CHEN Z,XU C,et al. Transient Synchronization Stability Analysis of Voltage Source Converters: A Review [J]. Proceedings of the CSEE,1-15.   
[17]董哲，周明，李庚银,等．风机有功控制对系统暂态功 角第二摆稳定性影响机理 [J].中国电机工程学报, 2017, 37(16): 4680-4690+4893. ZHE D，MING Z,GENGYIN L，et al. Influence Mechanism of Active Power Control of Wind Turbine Generators on Power System Transient Second Swing Stability [J]. Proceedings of the CSEE 2017,37(16): 4680- $4 6 9 0 + 4 8 9 3$ ：   
[18]易相彤，沈超，彭也伦，等．基于同调等值的多变流器 系统聚合降阶建模[J].中国电机工程学报,1-12. XIANGTONG Y, CHAO S, YELUN P, et al. Aggregation Reduced-order Modeling of Multi-converter Systems Based on Coherency Equivalence Method [J]. Proceedings of the CSEE,1-12.   
[19] YANG Z, YU J, KURTHS J, et al. Nonlinear Modeling of Multi-Converter Systems Within DC-Link Timescale [J]. IEEE Journal on Emerging and Selected Topics in Circuits and Systems,2021, 11(1): 5-16.   
[20]KABALAN M，SINGH P,NIEBUR D. Nonlinear Lyapunov Stability Analysis of Seven Models of a DC/AC Droop Controlled Inverter Connected to an Infinite Bus [J]. IEEE Transactions on Smart Grid,2019,10(1): 772-781.   
[21] LI Y,GU Y, GREEN T.Revisiting Grid-Forming and GridFollowing Inverters:A Duality Theory[J].IEEE Transactions on Power Systems,2022,1-1.   
[22]宫泽旭，艾力西尔·亚尔买买提，辛焕海，等．新能源电 力系统并网设备小扰动稳定分析(一)：机理模型与稳定 判据适用性 [J].中国电机工程学报,1-16. ZEXU G,AILIXIER Y,HUANHAI X, et al. Small Signal Stability Analysis of Equipment in Renewable Energy Power System (Part I): Mechanism Model and Adaptation of Stability [J]. Proceedings ofthe CSEE 1-16.   
[23]黄林彬，辛焕海，鞠平，等．电力电子并网装备的同步 稳定分析与统一同步控制结构[J].电力自动化设备, 2020,40(09): 10-25. LINBIN H, HUANHAI X, PING J, et al. Synchronization stability analysis and unified synchronization control Structure of grid-connected power electronic devices [J]. Electric Power Automation Equipment, 2020,40(09): 10- 25.   
[24] J.Li, Y.Li and Y. Gu, The Impact of Frame Transformations on Power System EMT Simulation, IEEE Transactions on Power Systems, early access.   
[25]许国瑞,胡一平,李伟力等.双轴励磁同步电机同步电抗 随运行工况的变化规律[J].电工技术学 报,2020,35(02):236-245. Guorui X,Yiping H, Weili L,et al. The variation of synchronous reactance of dual axis excitation synchronous motors with operating conditions [J]. Journal of Electrical Engineering Technology,2020,35 (02): 236-245   
[26]黄林彬．高比例电力电子装备电力系统的同步稳定分 析与控制设计[D].浙江大学,2020. Linbin H， Synchronous Stability Analysis and Control Design of High Ratio Power Electronic Equipment Power System[D].ZhejiangUniversity, 2020   
[27]L.Huang,H.Xin,H.Yuan, et al.Damping Effect of Virtual Synchronous Machines Providedbya Dynamical Virtual Impedance,IEEE Transactionson Energy Conversion, 2021， 36(1): 570-573.   
[28]Z.Yang，M.Zhan，D.Liu，C，et al.Small-Signal Synchronous Stability of a New-Generation Power System With $100 \%$ Renewable Energy， IEEE Transactions on Power Systems,early access.

# 附录A

同步机以内电势为输出变量建模时，其阻抗模型 $Z _ { S G } \left( s \right)$ 推导可见[4]，其方程为式(A1)。

当同步机采用诺顿等效时，导纳模型 $Y _ { S G } \left( s \right)$ 见正文图7式(a1)，与阻抗模型的区别在于将次暂态电势通过等效电流(A2)进行变量代换。

$$
\begin{array} { c } { { \boxed { Z _ { s \varepsilon } \left( s \right) = \left[ \begin{array} { c c } { { 0 } } & { { - Z _ { q } \left( s \right) } } \\ { { Z _ { d } \left( s \right) } } & { { 0 } } \end{array} \right] } } } \\ { { \left\{ Z _ { d } \left( s \right) = \frac { \omega _ { s \varepsilon } \left( X _ { d } ^ { ' } - X _ { d } ^ { ' } \right) \left( T _ { d } ^ { ' } s + a _ { d } \right) } { T _ { d } ^ { ' } { T _ { d } ^ { ' } s } ^ { 2 } + \left( T _ { d } ^ { ' } + T _ { d } ^ { ' } \right) s + 1 } \right\} } } \\ { { \left[ Z _ { q } \left( s \right) = \frac { \omega _ { s \varepsilon } \left( X _ { q } ^ { ' } - X _ { q } ^ { ' } \right) \left( T _ { q } ^ { ' } s + a _ { q } \right) } { T _ { q } ^ { ' } { T _ { q } ^ { ' } s } ^ { 2 } + \left( T _ { q } ^ { ' } + T _ { q } ^ { ' } \right) s + 1 } \right. } } \end{array}
$$

$$
\left\{ \begin{array} { l l } { \dot { e _ { d } } = X _ { q } ^ { * } I _ { q } } \\ { \dot { e _ { q } } = - X _ { d } ^ { * } I _ { d } } \end{array} \right.
$$

变流器仅考虑电流内环，采用电流为输出变量建模时，其导纳模型 $Y _ { _ { V S C } } \left( s \right)$ 推导见文献[10]。变流器采用内电势为输出变量建模时，其阻抗模型为$Z _ { \scriptscriptstyle V S C } \left( s \right) ^ { \left[ 1 2 \right] } ,$ 0

$Z _ { _ { S G } } ( s ) , Z _ { _ { S G } } ^ { - 1 } ( s ) , Y _ { _ { S G } } ( s )$ 和 $Z _ { _ { V S C } } \left( s \right) , Y _ { _ { V S C } } \left( s \right) , Y _ { _ { V S C } } ^ { - 1 } \left( s \right)$ 在$0 . 1 \mathrm { - } 1 0 0 0 \mathrm { H z }$ 的最大奇异值如图A1所示，可表征模型的鲁棒性[7]。在同步机转子主导动态的低频段，内电势的电压源建模 $\left( Z _ { _ { S G } } \left( s \right) \right)$ 最大奇异值最小，其次是诺顿等效下的电流源建模( $\because \sum _ { S G } \left( s \right)$ )与 $Z _ { S G } \left( s \right)$ 相差较小，直接以电流为输出的模型鲁棒性不好$\left( Z _ { S G } ^ { - 1 } \left( s \right) \right)$ ；在锁相环主导的频段 $( 5 - 1 0 0 \mathrm { H z } )$ ，以电流为输出的建模( $\because Y _ { _ { V S C } } ( s )$ )的鲁棒性最好，其余两种建模方式鲁棒性相对欠佳。

![](images/aafc7a8e86135378daeb0f5bc1f2d44dbcd4e6913ef4c901156f96f85d493320.jpg)  
图A1同步机与变流器不同模型下的最大奇异值  
Fig.A1MaximumSingularValueofSynchronousMachine

and ConverterunderDifferentModels

# 附录B

定义矩阵 $B$ 为系统机电模型下的导纳矩阵，通过节点消去内部无源节点，仅保留设备(同步机与变流器)节点。定义 $N$ 为设备节点， $M$ 为无源节点，则节点消去后

$$
B ^ { r e d } = B _ { _ { N N } } - B _ { _ { N M } } \times B _ { _ { M M } } ^ { - 1 } \times B _ { _ { M N } }
$$

矩阵求逆后得到的 $X ^ { r e d } = \left( B ^ { r e d } \right) ^ { - 1 }$ ，其中每个元素 $X _ { i j }$ 的含义为节点 $i$ 与节点 $j$ 间的等效电抗。

当节点 $j$ 注入电流时，其他节点开路，节点 $i$ 电压响应的动态方程表示为

$$
\left\{ \begin{array} { l } { { \displaystyle { \frac { L _ { i j } } { \omega _ { 0 } } \frac { d I _ { j d } } { d t } } = V _ { i d j } + I _ { j q } \omega _ { j } L _ { i j } } } \\ { { \displaystyle { \frac { L _ { i j } } { \omega _ { 0 } } \frac { d I _ { j q } } { d t } } = V _ { i q j } - I _ { j q } \omega _ { j } L _ { i j } } } \end{array} \right.
$$

其中， $V _ { i d q j }$ 表示节点 $i$ 的电压在第 $j$ 个设备控制坐标系下的dq轴分量。将电压 $V _ { i d j } + j V _ { i q j }$ 转化到设备 $i$ 的dq坐标系下表示为

$$
\boxed { V _ { i d i } } = T _ { j i } \boxed { V _ { i d j } }
$$

同理，对 $\mathfrak { n }$ 个注入电流的电压响应均转换至节点 $i$ 控制坐标系进行叠加后可得正文式(5)。

由正文式(7)得

$$
\begin{array} { l } { \displaystyle \frac { d \theta _ { _ { I i } } } { d t } + \frac { T _ { _ { P i } } } { T _ { _ { J i } } } \sum _ { j = 1 } ^ { n } I _ { j } \frac { L _ { i j } } { \omega _ { 0 } } \mathrm { s i n } \big ( \theta _ { i j } - \alpha _ { i } \big ) \frac { d \theta _ { _ { I j } } } { d t } } \\ { \displaystyle = \frac { T _ { _ { P i } } } { T _ { _ { J i } } } \Bigg ( M _ { _ { r e f i } } - \sum _ { j = 1 } ^ { n } I _ { j } X _ { _ { i j } } \mathrm { s i n } \big ( \theta _ { i j } - \alpha _ { i } \big ) \Bigg ) + \tilde { \omega } _ { i } } \end{array}
$$

多机下可写为

$$
\bigl ( \mathbf { I } _ { n \times n } + \Delta \mathbf { A } _ { n \times n } \bigr ) \dot { \boldsymbol { \Theta } } _ { n \times n } = \mathbf { V } _ { n }
$$

其中 $\Delta \mathbf { A } _ { i j } = \frac { T _ { P i } } { T _ { J i } } I _ { j } \frac { L _ { i j } } { \omega _ { 0 } } \mathrm { s i n } \big ( \theta _ { i j } - \alpha _ { i } \big ) , \mathrm { V } _ { i }$ 如(B4)右半侧。

因为 $\big \| \Delta \mathbf { A } \big \| \ll 1$ 成立，故 $\left( \mathrm { I } + \Delta \mathrm { A } \right) ^ { - 1 } \approx \mathrm { I } - \Delta \mathrm { A }$ ，从而有 $\dot { \boldsymbol { \theta } } \approx \big ( \mathrm { I } - \Delta \mathrm { A } \big ) \mathrm { V } _ { n }$ 。再进一步忽略三角函数的二次项，可得正文式(8)。

# 附录C

定义线性变换矩阵

$$
\mathrm { \bf T } = \left[ \begin{array} { c c } { \mathrm { \bf I } } & { \mathrm { \bf \Sigma - K _ { p } H ^ { - 1 } } } \\ { 0 } & { \mathrm { \bf I } } \end{array} \right]
$$

其中， $\mathbf { K _ { p } H ^ { - 1 } } = d i a g \{ T _ { p 1 } , . . . , T _ { p n } , 0 . . . , 0 \}$ 为对角矩阵。

对状态空间方程做线性变换 $\mathrm { T } \big ( \mathrm { M } ^ { \mathrm { - 1 } } \mathrm { A } \big ) \mathrm { T } ^ { \mathrm { - 1 } }$

$$
\left[ \begin{array} { l l } { \mathrm { I } _ { n \times n } } & { 0 } \\ { 0 } & { \mathrm { H } } \end{array} \right] \left[ \begin{array} { l } { \Delta \dot { \mathrm { x } } _ { 1 } } \\ { \Delta \dot { \mathrm { x } } _ { 2 } } \end{array} \right] = \left[ \begin{array} { c c } { 0 } & { \mathrm { I } } \\ { \mathrm { N } _ { \mathrm { I m } } } & { \tilde { \mathrm { D } } } \end{array} \right] \left[ \begin{array} { l } { \Delta \mathrm { x } _ { 1 } } \\ { \Delta \mathrm { x } _ { 2 } } \end{array} \right]
$$

其中 $\tilde { \mathrm { D } } = \mathrm { D } _ { \mathrm { v s c } } + \mathrm { D } _ { \mathrm { s G } } + \mathrm { N } _ { \mathrm { R e } } \mathrm { , D } _ { \mathrm { v s c } } { = } \mathrm { N } _ { \mathrm { I m } } \left( \mathrm { K } _ { \mathrm { p } } \mathrm { H } ^ { - 1 } \right) \mathrm { ~ c ~ }$

上式的特征方程可描述为二次特征值问题，其形式为

$$
\mathbf { H } \mathsf { \widehat { A } } ^ { 2 } + \bigl ( - \mathbf { \widetilde { D } } \bigr ) \mathsf { \widehat { A } } + \bigl ( - \mathbf { N } _ { \mathrm { I m } } \bigr ) = 0
$$

进一步，考虑到这些接入设备间电压相角差较小，则 $\mathrm { N } _ { \mathrm { I m } }$ ， $\Nu _ { \mathrm { R e } }$ ， $\mathbf { D } _ { \mathrm { v s c } }$ 和 $\mathrm { D } _ { \mathrm { { s G } } }$ 近似为：

$$
\begin{array} { r } { \{ \mathbf { N } _ { \mathrm { I m } } = [ \begin{array} { c c } { \mathbf { N } _ { \mathrm { I m ( 1 ) } } } & { \mathbf { N } _ { \mathrm { I m ( 2 ) } } } \\ { 0 } & { \mathbf { N } _ { \mathrm { I m ( 4 ) } } } \end{array} ] , \ \mathbf { N } _ { \mathrm { R e } } = [ \begin{array} { c c } { \mathbf { N } _ { \mathrm { R e ( 1 ) } } } & { 0 } \\ { \mathbf { N } _ { \mathrm { R e ( 3 ) } } } & { 0 } \end{array} ]  } \\ {  [ \begin{array} { c c } { \mathbf { D } _ { \mathrm { S G } } = [ \begin{array} { c c } { 0 } & { 0 } \\ { 0 } & { \mathbf { D } _ { \mathrm { S G ( 4 ) } } } \end{array} ] , \ \mathbf { D } _ { \mathrm { V S C } } = [ \begin{array} { c c } { \mathbf { D } _ { \mathrm { V S C ( 1 ) } } } & { 0 } \\ { 0 } & { 0 } \end{array} ] } \end{array}  } \end{array}
$$

其中， $\mathrm { \Delta N } _ { \mathrm { I m ( 1 ) } }$ 为对角阵， $\mathbf { N } _ { \mathrm { I m ( 1 ) } }$ 对角元素为 $\mathbf { N } _ { \mathrm { I m } ( 2 ) }$ 的行元素之和； $ { \mathbf { N } } _ { \mathrm { I m } ( 2 ) }$ 和 $\Nu _ { \mathrm { R e } ( 3 ) }$ 为满阵， $\mathbf { N } _ { \mathrm { R e ( 1 ) } }$ 和 $\mathrm { N } _ { \mathrm { I m } ( 4 ) }$ 为对称满阵； $\mathrm { \Delta D } _ { \mathrm { S G } }$ 和 $\mathrm { \Delta D _ { v s c } }$ 均为对角矩阵。

当 $\mathrm { D } _ { \mathrm { v s c } } { + } \mathrm { D } _ { \mathrm { s G } }$ 的对角元素均小于0，且绝对值远大于 $\Nu _ { \mathrm { R e } }$ 的元素时，此时可以忽略 $\Nu _ { \mathrm { R e } }$ 的非对角元素， $\tilde { \mathrm { ~ D ~ } }$ 可近似为矩阵元素均小于0的对角矩阵。

再考虑到 $\mathrm { \Delta N _ { \mathrm { { I m } } } }$ 左下角元素近似为0，故(C4)可解耦为

$$
\begin{array}{c} \begin{array} { r } { \left\{ \mathrm { H } _ { ( 1 ) } \lambda _ { 1 } ^ { 2 } + \left( - \tilde { \mathrm { D } } _ { \mathrm { v s c } ( 1 ) } \right) \lambda _ { 1 } + \left( - \mathrm { N } _ { \mathrm { I m } ( 1 ) } \right) = 0 \right.} \\ { \mathrm { H } _ { ( 4 ) } \lambda _ { 2 } ^ { 2 } + \left( - \tilde { \mathrm { D } } _ { \mathrm { S G } ( 4 ) } \right) \lambda _ { 2 } + \left( - \mathrm { N } _ { \mathrm { I m } ( 3 ) } \right) = 0 } \end{array}   \end{array}
$$

由于(C5)中 $\mathrm { N } _ { \mathrm { I m } ( 4 ) }$ 为正定矩阵，其余矩阵为对角正定矩阵，易知其二次特征值实部小于0，故系统可同步稳定。此外，根据特征值对矩阵元素的连续性质，只要 $\mathrm { D } _ { \mathrm { v s c } } { + } \mathrm { D } _ { \mathrm { s G } }$ 中元素数值够大使得系统特征值离右半平面距离足够远，当考虑设备间电压相角差、线路电阻以及 $\Nu _ { \mathrm { R e } }$ 中元素时，互联系统仍然是同步稳定的。