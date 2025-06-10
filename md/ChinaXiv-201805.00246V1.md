# 信息物理系统在变压器稳压调节控制中的应用研究

许刚，赵妙颖

(华北电力大学 电气与电子工程学院，北京 102206)

摘要：考虑到现有变压器电压调节方法受调压档位限制，且电压调整判断依据为调度部门确定的电压曲线，难以实现灵活、高效、高精度的变压器输出电压稳定调节，提出一种基于信息物理融合系统的稳压动态调节方法以更好地解决变压器运行过程中出现的电压偏移问题。建立变压器的物理模型与信息模型,通过物理参数与信息属性的相互映射，利用动态链接对物理模型与信息模型在统一仿真平台上进行整合，建立变压器的信息物理融合系统模型，通过信息量对物理量的实时反馈作用机制，控制变压器原副线圈匝数比的自动调节，实现变压器输出稳压。仿真实验结果表明信息物理融合方法在变压器输出电压稳定调节应用中具有一定的有效性。

关键词：信息物理系统；电力变压器；物理模型；信息模型；稳压调节；优化控制中图分类号：TP14 doi: 10.3969/j.issn.1001-3695.2017.08.0719

# Application of cyber physical system on transformer constant voltage modulation control

Xu Gang, Zhao Miaoying (SchoolofElectrical&Electronic Engineering,North China ElectricPower University,Beijing l02206,China)

Abstract:Generayfortelmitedegulatinggearrestrictstexistingtrasformerageegulationmetod,andtierio ofvoltageregulationisthevotagecurvedeterminedbydispatchingdepartment,itisdificulttoachieveaflexible,eicient, andhigh precisionconstantvoltage modulation.Tobettersolve the problem oftransformeroutputvoltage deviation,this paper proposedamethodtodynamicallyadjust the voltage qualitybasedoncyberphysicalsystem.Firstly, transformerphysicalmodel andinformation modelare respectively established with MATLAB Simulinkand EnterpriseArchitect (EA).Thenaccording to the mutual mappngetweenphysical parameters and informationatributes,withthe helpofanintermediary platform—Visual Studio,thedynamic ink libraryisusedto integratethephysicalmodeland informationmodelonaunifiedsimulationplatform. Therefor at lastthe transformer cyber physical system model is established on the MATLAB platform.Through information real-time feedback mechanismon quantities,theautomatic adjustmentof inductor windingratiocan becontroled,and the transformer output voltage can be stabilized.The simulation results show the effctivenessofcyber physical systemon transformer voltage control.

Key Words:cyber physical system;power transformer;physical model;information model; constantvoltage modulation; optimized control

# 0 引言

变压器输出电压的稳定性关系到电能质量的优劣，对电力系统的安全、经济运行，以及保障电气设备的使用寿命都具有重要意义。不同原因造成的变压器运行过程中的电压异常偏移，不仅会有损设备自身性能，还会影响整个电力系统的安全稳定生产。如何对变压器进行有效调节，保证其持续稳定输出，是变压器领域研究中需要解决的一个重要问题。

变压器输出电压调节方法有无载调压和有载调压两种，分别通过无励磁开关和机械有载分接开关实现。采用无载调压方式，需在变压器停电状态下进行，操作不便且会造成电力系统的间断运行。因此目前多采用有载调压方式。文献[1]提出了一种以电力电子器件为分接开关的无冲击有载调压方法，通过负载阻抗角确定调压时刻。文献[2]分析了采用有载调压方式对变压器输出电压分别进行调高与调低操作时分接头变换方式的选择方法。文献[3]设计了一种基于单片机的可调电抗器，通过机械传动，对变压器进行稳压调节，但对电压偏低的情况效果不理想。虽然目前有载调压方式应用广泛且研究较多，但由于调压档位的限制，且电压调整的判断依据是按照调度部门确定的电压曲线进行调节，因此调压精度不高且存在一定延时[3]。

因此，本文研究将信息物理系统融合技术应用于电力变压器，建立变压器的信息物理系统模型，利用信息流对物理网络的反馈控制，实现高效、灵活的变压器实时稳压调节，提高电压调节精度，保证其输出电压的稳定性。同时通过典型电网系统模型仿真，验证变压器信息物理系统建模在电网应用中的适用性、通用性与便利性。

# 1 信息物理系统

信息物理系统（cyber-physical system，CPS)，是以物理空间实体网络为基础，实现计算、通信以及控制技术深度融合的下一代工程系统[4,5]。有别于传统的嵌入式实时系统与无线传感器网络，CPS技术不再单纯的通过对计算机硬件和软件资源的优化利用达到所要求的性能需求，而是通过对信息量的充分开发利用，优化提升物理系统的各方面性能[6]。

电力系统是CPS技术的一个重要应用领域。电力信息物理系统(cyber-physical power system, CPPS 或 cyber-physical energysystem,CPES)被认为是下一代电力系统的基本架构。其主要特征包括：可靠性一一在系统故障或工作环境变化时，CPPS必须是坚强可靠的；自治性一一发生问题时，CPPS能够通过系统闭环控制，自动执行预定义解决方案；高度整合性一一CPPS 需通过网络通信或嵌入式实时系统达到计算与物理动态过程的高度整合；时间与空间的多尺度复杂性一一连续物理系统与离散信息系统的融合[7-10]。随着电网智能化[11]的不断推进，CPPS已成为电力行业的研究热点。目前，国内外学者对CPPS的研究多集中在以下领域：CPPS建模方法与形式化验证，CPPS系统分析方法及CPPS系统控制方法[12]。

在电力信息物理系统建模技术研究中，常用的仿真工具有MatlabSimulink、OPNETModeler、GridLAB-D以及Modelica等[13]。其中，Modelica为基于方程的建模语言，利用微分代数方程，通过数据流同步机制建立连续/离散混合的复杂系统模型[14\~16]。Matlab Simulink 可用于动态多领域系统的分层建模、仿真和分析，在CPPS 建模中主要用作电力系统仿真工具，需结合信息技术仿真工具使用[17]。文献[7,18\~20]提出了信息物理系统的基本建模方法：将系统按功能拆分成若干模块；为每个模块建立一个动态模型，模块中每个物理元件都应有其对应的信息元素；根据物理部分的拓扑关系与信息部分的逻辑关系，对模块进行整合，建立完整的信息物理系统模型。

本文借鉴以上建模方法，利用MATLAB工具在典型电网环境中建立变压器信息物理融合系统模型，通过仿真实验实现现实场景的变压器自动稳压控制。

# 2 电力变压器信息物理融合系统模型

变压器信息物理融合系统的建模过程如图1所示。首先分别对变压器物理系统和信息系统进行分析，建立其物理动态模型与信息模型，并对二者进行综合比对，通过模型优化，实现物理模型参数与信息模型属性的相互映射；然后，分别在控制层面与实现方式层面对变压器物理模型和信息模型进行整合。控制层面，通过信息控制中心对物理系统的造访与反馈，以及物理系统与信息系统间的交互作用，实现信息系统与物理系统的融合，以及变压器信息物理系统对输出电压的稳压调节控制。实现方式层面，最终通过对物理模型与信息模型不同实现方式的整合，在同一仿真平台上建立变压器的信息物理系统模型。

![](images/36b7d5bfb71702913e1191986bddcc4f020e70eb25ae1bd05690e45f8ebc4f88.jpg)  
图1变压器信息物理系统建模过程

# 2.1变压器物理系统建模

在变压器信息物理系统中，物理量与信息量之间存在实时交互，各种物理参数都应可方便地被系统访问与传递。基于以上原则，采用定制s-function模块的方法建立电力变压器的动态物理系统模型。

首先对变压器的物理运行特性进行数学分析。变压器负载运行原理如图2所示[21]。

![](images/666e1d345b4e5ecd132a40e90c9decec116d51f1ad31d8ba95eccc262b57accc.jpg)  
图2电力变压器负载运行原理图

其中， $\dot { U _ { \scriptscriptstyle 1 } }$ 为变压器一次绕组的输入电压， $R _ { \mathrm { { l } } }$ 和 $j X _ { 1 }$ 为一次侧的电阻及漏电抗， $\dot { I } _ { \scriptscriptstyle 1 }$ 为一次侧电流， $R _ { 2 } ^ { \prime }$ 和 $j X _ { 2 } ^ { \prime }$ 是折算后二次绕组的电阻及漏电抗， $Z _ { L } ^ { \prime }$ 为折算后负载阻抗， $\dot { U } _ { 2 } ^ { \prime }$ 为折算后二次侧输出电压， ${ \dot { I } } _ { 2 } ^ { \prime }$ 是折算后二次侧电流， $\boldsymbol { R _ { m } }$ 和 $j X _ { { \scriptscriptstyle m } }$ 分别为电感线圈的励磁电阻和励磁电抗， $\dot { I } _ { \mathrm { 0 } }$ 为励磁电流， $\dot { E } _ { \scriptscriptstyle 1 }$ 和 $\dot { E } _ { 2 } ^ { \prime }$ 分别为一次绕组和折算后二次绕组产生的感应电动势，变压器一次、二次线圈的额定匝数比为 $k$ 。由基尔霍夫定律，可得

$$
\dot { U } _ { 1 } = - \dot { E } _ { 1 } + \dot { I } _ { 1 } \cdot \dot { Z } _ { 1 }
$$

$$
\dot { U } _ { 2 } ^ { \prime } = \dot { E } _ { 2 } ^ { \prime } - \dot { I } _ { 2 } ^ { \prime } \cdot Z _ { 2 } ^ { \prime }
$$

$$
\dot { U } _ { 2 } ^ { \prime } = \dot { I } _ { 2 } ^ { \prime } \cdot Z _ { L } ^ { \prime }
$$

$$
\dot { E } _ { \scriptscriptstyle 1 } = - \dot { I } _ { \scriptscriptstyle 0 } \cdot Z _ { \scriptscriptstyle m }
$$

$$
\dot { I } _ { \scriptscriptstyle 1 } = \dot { I } _ { \scriptscriptstyle 0 } - \dot { I } _ { \scriptscriptstyle 2 } ^ { \prime }
$$

根据变压器绕组折算关系，由式(1)\~(5)推导可得

$$
\dot { I } _ { 2 } ^ { \prime } = - \frac { Z _ { m } \cdot \dot { U } _ { 1 } } { k ^ { 2 } ( Z _ { 1 } + Z _ { m } ) ( Z _ { 2 } + Z _ { L } ) + Z _ { 1 } \cdot Z _ { m } }
$$

则输出电压为

$$
\dot { U } _ { 2 } ^ { \prime } = - \frac { k ^ { 2 } \cdot Z _ { m } \cdot Z _ { L } \cdot \dot { U } _ { 1 } } { k ^ { 2 } ( Z _ { 1 } + Z _ { m } ) ( Z _ { 2 } + Z _ { L } ) + Z _ { 1 } \cdot Z _ { m } }
$$

则

$$
\begin{array} { l } { { \dot { I } _ { 2 } = k \cdot \dot { I } _ { 2 } ^ { \prime } = - \frac { k \cdot Z _ { m } \cdot \dot { U } _ { 1 } } { k ^ { 2 } ( Z _ { 1 } + Z _ { m } ) ( Z _ { 2 } + Z _ { L } ) + Z _ { 1 } \cdot Z _ { m } } } } \\ { { \dot { U } _ { 2 } = \frac { \dot { U } _ { 2 } ^ { \prime } } { k } = - \frac { k \cdot Z _ { m } \cdot Z _ { L } \cdot \dot { U } _ { 1 } } { k ^ { 2 } ( Z _ { 1 } + Z _ { m } ) ( Z _ { 2 } + Z _ { L } ) + Z _ { 1 } \cdot Z _ { m } } } } \end{array}
$$

其中:

$$
Z _ { 1 } = \sqrt { R _ { 1 } ^ { 2 } + X _ { 1 } ^ { 2 } } Z _ { 2 } = \sqrt { R _ { 2 } ^ { 2 } + X _ { 2 } ^ { 2 } } Z _ { m } = \sqrt { R _ { m } ^ { 2 } + X _ { m } ^ { 2 } }
$$

根据以上电力变压器的数学模型，编写s-function 程序文件，实现变压器的物理系统建模。

# 2.2变压器信息系统建模

电力系统的信息模型为公共信息模型（commoninformationmodel,CIM)[22]。在建立变压器信息系统模型时，采用IEC61970中的公共信息模型CIM包，并用UML语言对CIM模型进行描述。

变压器物理模型中的参量需在信息模型中找到相对应的属性，如此才能实现物理系统与信息系统的相互映射。因此，在建立变压器信息模型时，应以变压器物理量为基准，若信息模型中没有与其相对应的信息属性，则需对模型进行类别或属性的扩展，以满足二者的相互映射；若信息模型中的属性超出了物理量的需求范畴，则予以保留。

根据以上原则建立的变压器信息系统CIM模型[23]如图3所示。图中变压器信息模型共包含6个类包，分别为电力变压器类（PowerTransformer）、分接头调节器类（TapChanger）、变压器绕组类（TransformerWinding）、调节计划类（RegulationSchedule）、绕组测试类（WindingTest）与热交换类（HeatExchanger）。其中，电力变压器类与热交换类、变压器绕组类之间存在聚集关系，即热交换与变压器绕组均是电力变压器的一部分。1个热交换只能从属于一个变压器，同时1个变压器可能包含0个或1个热交换；1个变压器绕组只能从属于一个变压器，而1个变压器可能含有1个或多个变压器绕组。分接头调节与变压器绕组之间也存在类似的聚集关系。此外，分接头调节器与调节计划之间存在简单关联，即1个分接头调节器可以有0个或1个调节计划，而1个调节计划可能从属于0个、1个或多个分接头调节器。类似地，变压器绕组与绕组测试之间也存在简单关联。

![](images/e8632067f25e0b427c9b914a6f902f479f8071af7f329edd060dcf66b1c64de1.jpg)  
图3电力变压器CIM框图

变压器信息模型中的每个类都具有若干属性。根据2.1节变压器物理动态模型参数，可在信息模型中提取与之对应的相关属性。由于变压器物理模型中的参数 $k$ ，即变压器原副线圈匝数变比未在变压器CIM模型属性中体现，因此对信息模型中的TransformerWinding类进行扩展，增加 $k$ 属性。变压器信息模型属性与物理模型参数的对应关系如表1所示。

表1电力变压器信息模型属性与物理模型参数映射关系  

<html><body><table><tr><td>属性名称</td><td>所属类</td><td>描述对象</td></tr><tr><td>Phases</td><td>PowerTransformer</td><td>相位</td></tr><tr><td>Bmagsat</td><td>PowerTransformer</td><td>励磁电纳</td></tr><tr><td>rated kV</td><td>TransformerWinding</td><td>额定电压</td></tr><tr><td>R1</td><td>TransformerWinding</td><td>一次线圈电阻</td></tr><tr><td>X1</td><td>TransformerWinding</td><td>一次线圈电抗</td></tr><tr><td>R2</td><td>TransformerWinding</td><td>二次线圈电阻</td></tr><tr><td>X2</td><td>TransformerWinding</td><td>二次线圈电抗</td></tr><tr><td>k</td><td>TransformerWinding</td><td>原副线圈匝数比</td></tr><tr><td>Voltage</td><td>Winding Test</td><td>输出电压</td></tr><tr><td>ExcitingCurrent</td><td>Winding Test</td><td>励磁电流</td></tr><tr><td>LeakageImpedance</td><td>Winding Test</td><td>漏磁阻抗</td></tr><tr><td>From tapstep</td><td>Winding Test</td><td>分接头步数（起点)</td></tr><tr><td>To tapstep</td><td>Winding Test</td><td>分接头步数（终点）</td></tr></table></body></html>

# 2.3变压器信息物理融合系统建模

为了使变压器具有更好的稳压效果，本文设计了控制系统，根据变压器实际输出电压与额定输出电压的偏差，动态调节变压器原副绕组线圈匝数比，以实现变压器的稳定输出[24]。具有动态控制功能的电力变压器信息物理系统融合模型如图4所示。图中实线表示物理量，虚线表示信息量。其中， $U$ 为变压器一次侧输入电压， $\Delta U$ 为对变压器输入电压 $U$ 所加的波动变化量，$U _ { \mathrm { o } }$ 为变压器输出电压， $U _ { _ { 2 } }$ 为变压器额定输出电压， $\Delta U _ { \mathrm { o } }$ 为变压器实际输出电压较额定输出电压的偏差， $k$ 为变压器额定原副线圈匝数变比， $\Delta k$ 为该稳压调节系统中信息控制模块输出的变比变化量， $k ^ { \prime }$ 为调整后的变压器原副线圈匝数变比。系统将具有信息性质的中间量变比 $k$ 与输出电压偏差 $\Delta U _ { \mathrm { o } }$ 从物理动态模块传入信息控制模块，实现信息控制中心对物理运行过

程的造访。

![](images/69f67ff3fc901c3d047f3d3a0021244031d0484f8ef6b35531f8963c8285a0e0.jpg)  
图4电力变压器CPS 模型

具体稳压调节控制过程如图5所示。

![](images/178852c140cabcf2c369e1a28ad7e5a51f49185b3abafc7ab9221de738e49d51.jpg)  
图5变压器CPS模型稳压调节控制过程

系统输入为变压器额定输入电压 $U$ ，在运行过程中对其添加 $\Delta U$ 的波动变化，考察输出电压 $U _ { \mathrm { o } }$ 的偏移情况。当 $\Delta U { = } 0$ 时，系统输出电压 $U _ { \mathrm { o } }$ 应等于额定输出电压 $U _ { _ { 2 } }$ ，此时 $\Delta U _ { \mathrm { o } } { = } 0$ ，变压器变比 $k$ 保持不变。当 $\Delta U \ne 0$ 时，变压器输入电压变为$U + \Delta U$ ，实际输出电压与额定输出电压的偏差为$\Delta U _ { \mathrm { o } } { = } U _ { \mathrm { o } } { - } U _ { \mathrm { 2 } } { \neq } 0$ 。此时在信息控制模块内，程序通过判断 $\Delta U _ { \mathrm { o } }$ 的正负属性确定将变比k 调高或是调低。若△U。=U。-U>0，则需将变比 $k$ 调高；若 $\Delta U _ { \mathrm { o } } = U _ { \mathrm { o } } - U _ { \mathrm { 2 } } < 0$ ，则将变比 $k$ 调低。根据变比公式及输入、输出电压变化，推导可得△k=k·△U/U，则调整后的变压器原副线圈匝数比为 $k ^ { \prime } = k \cdot \left( 1 + \Delta U _ { \mathrm { o } } / U _ { 2 } \right)$ 。信息控制模块在完成实时动态计算后，将具有物理性质的输出结果 $k ^ { \prime }$ 作为制动量反馈作用于物理动态系统，从而实现变压器二次侧的稳定输出。

![](images/61ad4e9aa7a22eaa97581d3280f0e7d9256f2b2a24076027e0920a45f24cda0f.jpg)  
图6变压器信息物理系统模型实现方式

由于该控制系统可根据变压器实际输出电压较额定输出电压的微小变化精细调节变压器变比，不受调压档位的限制，实现无级调压，因此具有比传统调压方法更高的稳压调节精度。

在分别建立了变压器的物理模型与信息模型后，需使用动态链接机制实现二者在统一仿真平台上的整合。图6所示为变压器CPS模型的实现方式。

在MATLAB平台上建立变压器物理系统模型，在EnterpriseArchitect(EA)平台上建立变压器信息系统模型。借助EA可以将UML语言描述的CIM类图转换为 $\mathrm { C } { + } { + }$ 、Java等非图形化的程序语言这一功能，将电力变压器的CIM信息模型转换为 $\mathrm { C } { + } { + }$ 语言程序，在VisualStudio2010平台上进行操作。需要寻找一个连接VisualStudio和Matlab两种仿真平台的桥梁，以实现变压器系统物理流与信息流的真正融合。文献[19]对这个问题提供了一个很好的解决思路，即将 $\mathrm { C } { + } { + }$ 语言程序封装为动态链接库文件，在Matlab平台调用该文件，以实现仿真平台的统一。借鉴这一方法，本文在VisualStudio 环境下，将用来描述变压器信息模型的 $\mathrm { C } { + } { + }$ 语言程序和调节变压器原副绕组线圈匝数比的控制器程序生成动态链接库文件，并在描述变压器物理动态特性的s-function 模块程序中进行调用，实现了物理模型与信息模型在统一仿真平台上的整合。

# 3 仿真实验与结果分析

本文的仿真实验使用Inter(R）Core(TM)i7-4710MQ$\mathrm { C P U } @ 2 . 5 0 \mathrm { G H z }$ 处理器在MatlabR2015a环境下进行。搭建包含电源、输电线路、变压器和负荷等在内的典型电网仿真模型，如图7所示，考察基于CPS建模的变压器稳压调节策略在电网运行中的执行效果。

![](images/ec4c93df64dd5215652ba8f5f7a7c8577d1b6f54d4dcafe95bfe30d7ea580cac.jpg)  
图7变压器稳压调节系统仿真模型

图7中，模块S-Function为只反映变压器物理动态特性的模型，不包含信息模型及相关的信息流控制，S-Function1模块为变压器CPS模型，在物理动态特性模型的基础上调用了CIM信息模型及信息流控制程序生成的动态链接库文件。

图8为利用 Simulink有载调压变压器(On-Load Tap ChangerOLTC）模块建立的仿真模型。对图6、图8中的各模块进行相同参数设置，以比较普通变压器、基于CPS调压变压器与传统OLTC变压器的调压效果。

![](images/1c1b43852aa979fb4b95779e5d70e788698756903abbec77320d4a7dfcdaa1aa.jpg)  
图8OLTC变压器仿真模型

设置电源电压 $1 2 0 ~ \mathrm { V } ,$ 变压器额定变比为120/25。仿真过程中，在 $\Delta U = \pm 1 0 \%$ 范围内动态调节输入电压，观察图7与图8中变压器输出电压偏移情况。其中， $\Delta U = \pm 5 \%$ 属于允许调节范围，此时变压器处于正常工作状态；当输入电压变化超出额定电压的 $\pm 5 \%$ 时，变压器可能出现异常工作情况。仿真结果如表2 所示，其中 $U$ 为输入电压， $U _ { \mathrm { o \_ p } }$ 为无信息模型参与的普通变压器模型输出电压， $U _ { \mathrm { o \_ o L T C } }$ 为传统有载调压变压器模型输出电压， $U _ { \mathrm { o _ { - } C P } }$ 为基于CPS 建模的有载调压变压器模型输出电压。输入电压变化引起的输出电压偏移趋势如图9所示。其中黑色实线所示为无信息量参与的变压器物理模型输出电压随输入电压变化曲线，蓝色点划线所示为OLTC变压器仿真模型输出电压随输入电压变化曲线，红色虚线所示为基于CPS建模的变压器有载调压方法输出电压随输入电压变化曲线。

表2变压器输出电压随输入电压变化偏移情况  

<html><body><table><tr><td>U(kV)</td><td>U_p(kV)</td><td>Uo_oLTc(kV)</td><td>Uo_cP(kV)</td></tr><tr><td>109.2</td><td>22.732</td><td>24.476</td><td>24.798</td></tr><tr><td>110.4</td><td>22.982</td><td>24.518</td><td>24.845</td></tr><tr><td>111.6</td><td>23.232</td><td>24.571</td><td>24.891</td></tr><tr><td>112.8</td><td>23.481</td><td>24.612</td><td>24.936</td></tr><tr><td>114</td><td>23.731</td><td>24.693</td><td>24.938</td></tr><tr><td>115.2</td><td>23.981</td><td>24.768</td><td>24.948</td></tr><tr><td>116.4</td><td>24.231</td><td>24.809</td><td>24.959</td></tr><tr><td>117.6</td><td>24.481</td><td>24.886</td><td>24.969</td></tr><tr><td>118.8</td><td>24.730</td><td>24.928</td><td>24.980</td></tr><tr><td>120</td><td>24.991</td><td>24.991</td><td>24.991</td></tr><tr><td>121.2</td><td>25.230</td><td>25.096</td><td>25.001</td></tr><tr><td>122.4</td><td>25.480</td><td>25.159</td><td>25.011</td></tr><tr><td>123.6</td><td>25.730</td><td>25.207</td><td>25.022</td></tr><tr><td>124.8</td><td>25.979</td><td>25.274</td><td>25.030</td></tr><tr><td>126</td><td>26.229</td><td>25.337</td><td>25.041</td></tr><tr><td>127.2</td><td>26.479</td><td>25.398</td><td>25.069</td></tr><tr><td>128.4</td><td>26.729</td><td>25.458</td><td>25.107</td></tr><tr><td>129.6</td><td>26.979</td><td>25.505</td><td>25.145</td></tr><tr><td>130.8</td><td>27.229</td><td>25.569</td><td>25.183</td></tr><tr><td>132</td><td>27.478</td><td>25.617</td><td>25.219</td></tr></table></body></html>

![](images/4a27822aab758243335843088beb157a9768281f427f4737fdc6802246e031a7.jpg)  
图9变压器输出电压随输入电压变化折线图

从仿真结果可以看出，对于没有信息量参与的变压器物理模型，当输入电压在 $\pm 5 \%$ 范围内变化时，输出电压也随之发生明显变化，波动范围达到 $0 . 9 6 \% { \sim } 5 . 0 4 \%$ ；OLCT变压器由于具有有载调压功能，其输出电压的波动范围可控制在$0 . 2 5 \% { \sim } 1 . 3 8 \%$ ；而基于CPS 的变压器有载调压方法可将输出电压较好地稳定在额定电压附近，波动范围仅为 $0 . 0 4 \% { \sim } 0 . 2 1 \%$ ，提高了稳压调节精度。当变压器输入电压超出额定电压的 $\pm 5 \%$ 时，对于无信息量参与的变压器物理模型，输出电压随输入电压的变化最高可达 $9 . 0 4 \%$ ，超出电压偏移允许范围；而OLTC变压器的输出电压波动范围也达到了 $1 . 5 2 \% { \sim } 2 . 5 \%$ ；与之相比，基于CPS的变压器稳压调节方法仍可将输出电压偏移控制在$0 . 2 2 \% { \sim } 0 . 9 1 \%$ 之间，具有较好的稳压效果。由此可见，基于CPS的变压器有载调压方法，能够通过信息量的灵活控制，对变压器的电压质量进行优化调节，使其具有更为稳定的输出。

# 4 结束语

目前常用的变压器电压调节方法仍存在一些弊端，针对此问题，提出了一种基于信息物理融合的变压器稳压调节方法。通过建立变压器的CPS模型，充分发挥信息量对物理量的反馈控制作用，实时动态调节变压器的原副绕组线圈匝数比，实现变压器输出电压的自动稳压调节，克服了现有调压方式带来的可靠性问题，并提高了稳压调节的精度。不过在工程应用中，需配合可实现无触点无级调压功能的外接电路装置，以实现对变压器的高精度稳压调节控制。

本文的研究为CPS技术在电力变压器中的应用提供了一种思路，后续可对其继续深入研究，基于CPS技术的应用，使变压器具备对自身状态的省察预测和自我配置能力，实现对电力变压器的优化协调控制和有效健康管理。

# 参考文献：

[1]黄俊杰，李晓明.基于电力电子技术有载调压变压器的无冲击调压方 法[J]．电力系统自动化,2009,33(10):69-73.   
[2]赵玉林，张吉冬，高程．无触点有载调压变压器分接头变换方式研究 [J]．东北农业大学学报,2014,45(11):124-128.   
[3]许书娟．变压器自动稳压调节系统的研究[D].青岛：青岛农业大学， 2008.   
[4]Rajkumar R,Lee I, Sha L,et al. Cyber-physical systems: the next computing revolution [Cl// Proc of the 47th ACM//EEE Design Automation Conference.2010:731-736.   
[5]李杰．工业大数据-工业4.0 时代的工业转型与价值创造[M].北京： 机械工业出版社,2015:61-67.   
[6]刘东，盛万兴，王云，等．电网信息物理系统的关键技术及其进展[J]. 中国电机工程学报,2015,35(14):3522-3531.   
[7]Macana CA, Quijano,N,Mojica-Nava E,et al.A survey on Cyber Physical Energy Systems and their applications on smart grids [Cl//Proc of IEEE PES Conference on Innovative Smart Grid Technologies.2011:1-7.   
[8]Shi Jianhua,Wan Jiafu, Yan Hehua,etal.Asurvey of cyber physical systems [C]// Prpc of International Conference on Wireless Communications and Signal Processing. 2011: 1-6.   
[9]Chun I,Park J, Kim W,et al.Autonomic computing technologies for cyberphysical systems $[ \mathrm { C } ] / \AA$ Proc of the l2th International Conference on Advanced Communication Technology.2010:1009-1014.   
[10] Guan X, Yang B,Chen C,et al.Acomprehensive overview ofcyber-physical systems: from perspective of feedback system [J]. IEEE//CAA Journal of Automatica Siniac,2016,3(1): 1-14.   
[11]董朝阳，赵俊华，文福拴，等．从智能电网到能源互联网：基本概念与 研究框架[J].电力系统自动化,2014,38(15):1-11.   
[12]赵俊华，文福拴，薛禹胜等．电力CPS 的架构及其实现技术与挑战[J]. 电力系统自动化,2010,34(16):1-7.   
[13] Palensky P,Widl E,Elsheikh A,et al. Simulating cyber-physical energy systems: challenges,tools and methods [J].IEEE Trans on Systems,Man and Cybernetics: Systems,2014,44(3): 318-326.   
[14] Tang Junjie, Zhao Jianjun,Ding Jianwan,et al. Cyber-physical systems modeling method based on Modelica[C]//Proc ofthe 6th IEEE International Conference on Software Security and Reliability Companion. 2012: 188- 191.   
[15]田光曙．基于modelica的信息物理融合系统的建模方法[D]．广州：广 东工业大学,2014.   
[16]唐俊杰．基于方程的信息物理融合系统建模与仿真技术研究[D].武 汉：华中科技大学,2013.   
[17] Widl E,Palensky P,Elsheikh A,et al.Evaluation of two approaches for simulating cyber-physical energy systems [C]// Proc of the 38th Annual Conference on IEEE Industrial Electronics Society. 2012:3582-3587.   
[18] lic M,Le Xie, Khan UA,etal. Modeling future cyber-physical energy systems [C]// Proc of IEEE Power and Energy Society General Meeting Conversion and Delivery of Electrical Energy in the 21st Century.2008:1- 9.   
[19] Le Xie,Marija D,Ilic.Module-based modeling of cyber-physical power systems [C]// Proc of the 28th International Conference on Distributed Computing Systems Workshops.2008: 513-518.   
[20]曾倬颖，刘东．光伏储能协调控制的信息物理融合建模研究[J]．电网 技术,2013,37(16):1506-1513.   
[21]欧丽娅．基于实时参数统计的变压器合理运行方式[D].广州：广东工 业大学,2007.   
[22]盛成玉，高海翔，陈颖等．信息物理电力系统耦合网络仿真综述及展望 [J]．电网技术,2012,36(12):100-105.   
[23] DL//T 890.301-2004，Draft IEC61970:energy management system application program interface (EMS-API) part3o1:Common Information Model (CIM)[S]. Beijing: China Electric Power Press,2005.   
[24] Rahavendra P,D.N.GAONKAR. Online voltage estimation and control for smart distribution networks [J].Journal of Modern Power Systems and Clean Energy,2016,4(1): 40-46.