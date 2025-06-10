# 单相级联型固态变压器直流电压平衡控制研究

季振东李东野² 孙毅超² 赵剑锋² 黄允凯²（1.南京理工大学自动化学院南京2100942.东南大学电气工程学院南京210096）

![](images/a016b98b47617e2d0f3d8a00234e5e00b72fb3544c7cef90fd40f44f9171aa85.jpg)

季振东　男 1986年生，博士，讲师，研究方向为高压大功率电力电子技术、新能源并网发电和电力电子变压器。

摘要：固态变压器可以有效解决传统电力变压器在电力系统中的不足，其中级联型SST可以很好地适应高压电网。但级联结构中存在直流侧平衡问题，这严重影响到装置的可靠性。本文首先分析了单相SST的电路拓扑和工作原理，建立数学模型，进一步对现有的直流电压平衡控制方法进行了比较研究，并确定适合SST的平衡控制方法。通过实验验证了该方法在SST中的有效性和可行性，实验结果表明，该方法在复杂工况下也能够保障装置可靠运行并维持直流电压平衡。

关键词：固态变压器 直流电压平衡控制有功矢量修正级联H桥中图分类号：TM41

# Research on DC Voltage Balancing Strategy of Single-Phase Cascaded Solid State Transformer

Ji Zhendong' Li Dongye² Sun Yichao² Zhao Jianfeng² Huang Yunkai² (1.Nanjing University of Science and TechnologyNanjing210094 China 2.Southeast University Nanjing210096China）

![](images/db04afba13ebc8e131afdc1db77b368528fa4e95717ac5152f1ffc48a8475fd3.jpg)

李东野男 1987年生，博士研究生，研究方向为多电平电力电子变流器技术、电力电子变压器。

Abstract: The disadvantages in power system with traditional industrial frequency transformer can be resolved by SST (solid state transformer). Cascaded SST can be transformerless connected to the high voltage grid. However, the output performance and reliability of cascaded grid-connected inverter are seriously influenced by DC voltage balancing problem which exists in cascaded configuration. Firstly, circuit topology, operating principle and mathematical model of single-phase cascaded SST are analyzed. Then,active power adjusting ability of DC voltage balancing methods are compared. Finally, suitable DC voltage balancing method is confirmed. This method can balance the DC voltages even under complex condition. Experimental results verify the feasibility and validity of this method.

Keywords: Solid state transformer, DC voltage balancing control, active vector correction method, cascaded H-bridge

# 1 引言

固态变压器（SolidStateTransformer，SST）又称电力电子变压器（Power Electronics Transformer,PET）、智能型通用变压器（IntelligentUniversalTransformer，IUT)，是一种通过中（高）频变压器来实现隔离的AC/AC变换技术的电力电子装置。它不仅需要完成常规电力变压器的变压、隔离和能量转换的功能，还应具有电压稳定可调、功率可控、谐波治理、无功补偿和故障隔离等功能。它解决了传统电力变压器在现代电力系统中的不足，将进一步推进了智能电网的发展[1-2]。

中高压大功率的SST及应用研究是近年来的热点，国外已有报道的案例主要有：美国北卡罗莱纳州立大学AlexQ.Huang团队的FREEDM(Future Renewable Electric Energy Delivery andManagement）项目[2.15]、欧洲以阿海珐和诺丁汉大学为主导的Uniflex-PM（UniversalandFlexiblePowerManagement）项目[3]、ABB公司的PETT(Power Electronic Traction Transformer）项目[4以及美国电科院的IUT项目等。以上案例中的SST拓扑在最为重要的高压侧均采用了CHB（CascadedH-Bridge）变换器，其可以无变压器地接入高压电网，结构上易于模块化实现，并具有较低开关损耗和谐波输出的特点，但其结构中相互独立的各个H桥直流侧存在并联型和混合型损耗差异以及脉冲延时差异，连接的电网存在电压不平衡等因素，这就造成了直流侧电压不平衡的问题[6-8]。CHB 的直流侧电压平衡控制可以分别从硬件和软件上得以解决，但硬件方法需要增加额外的电路[9，在控制和结构上加大了复杂度，成本也会提高，相对而言，软件方法更为实用。软件方法可以通过调整各个H桥电压调制波的调制比[10-11]、移相角[12]或者有功分量[13-16]的控制方法得到解决。但 SST中的CHB 不但需要运行在有功状态，还需要发挥无功补偿等电能质量治理的作用，而且由于在直流侧存在可等效成大负载或电流源的装置，自身可能产生更大的不平衡差异，因而选择合适的直流电压平衡方法尤为重要。

本文首先分析了单相SST的电路拓扑和工作原理，建立数学模型，进一步对现有的直流电压平衡控制方法进行比较研究，并确定合适的方法，最终进行了实验验证。

# 2 单相SST数学模型

结合国内外案例，本文所采用的单相SST的拓扑如图1所示，高压级采用了CHB结构，中间级采用DAB与高压级的各直流侧相连，并在输出端进行并联，最终利用输出级的三相四桥臂变流器形成交流输出。

![](images/3a8f4b309608841ed6f16931ff374fb7e6b170749bfd25e200122dfdfba044bb.jpg)  
Fig.1 Circuit topology of single-phase SST

CHB结构中的基本单元为H桥，如图2所示。在理想情况下（不考虑死区)，同一桥臂的上下两个开关管需保持互补状态，进而可以用上管状态表示该桥臂的开关状态。利用H桥中两个上管的开关状态 $s _ { 1 }$ 和 $s _ { 3 }$ （“1”表示开通状态， $^ { 6 6 } 0 ^ { 9 }$ 表示关断状态）将电压、电流与开关状态的关系表示如下

$$
u _ { \mathrm { o } } = ( s _ { 1 } - s _ { 3 } ) U _ { \mathrm { d c } } = S ^ { \prime } u _ { \mathrm { d c } }
$$

$$
\dot { l } _ { \mathrm { o } } = \big ( s _ { 1 } - s _ { 3 } \big ) \dot { l } _ { \mathrm { s } } = S ^ { \prime } \dot { l } _ { \mathrm { s } }
$$

![](images/6f29db7eed82f377384fde217ce299b9776133a5f2ca801c4d44a6bc61ddfa75.jpg)  
图1单相 SST拓扑  
图2H桥单元  
Fig.2H-bridge module

进一步结合图2，并利用基尔霍夫电流定律(KCL）和电压定律（KVL）可以得到基于开关函数的单H桥整流器简化数学模型

$$
\left\{ \begin{array} { l l } { \displaystyle L \frac { \mathrm { d } i _ { \mathrm { s } } ( t ) } { \mathrm { d } t } = e _ { \mathrm { s } } ( t ) - S ^ { \prime } u _ { \mathrm { d c } } ( t ) } \\ { \displaystyle C \frac { \mathrm { d } u _ { \mathrm { d c } } ( t ) } { \mathrm { d } t } = S ^ { \prime } i _ { \mathrm { s } } ( t ) - \frac { u _ { \mathrm { d c } } ( t ) } { R } } \end{array} \right.
$$

利用平均运算对开关周期内的占空比进行定义

$$
d ^ { \prime } = \Bigl \langle S ^ { \prime } \Bigr \rangle _ { T _ { s } } = \frac { 1 } { T } \int _ { t } ^ { t + T _ { s } } S ^ { \prime } ( t ) \mathrm { d } t
$$

将式（3）进行平均化处理，再将式（4）带入，从而得到单相 $\mathrm { ~ H ~ }$ 桥整流器的连续平均数学模型为

$$
\left\{ \begin{array} { l l } { \displaystyle L \frac { \mathrm { d } \big < i _ { \mathrm { s } } \big > _ { T _ { \mathrm { s } } } } { \mathrm { d } t } = \Big < e _ { \mathrm { s } } \Big > _ { T _ { \mathrm { s } } } - d ^ { \prime } \Big < u _ { \mathrm { d c } } \Big > _ { T _ { \mathrm { s } } } } \\ { \displaystyle C \frac { \mathrm { d } \big < u _ { \mathrm { d c } } \big > _ { T _ { \mathrm { s } } } } { \mathrm { d } t } = d ^ { \prime } \Big < i _ { \mathrm { s } } \Big > _ { T _ { \mathrm { s } } } - \frac { \Big < u _ { \mathrm { d c } } \Big > _ { T _ { \mathrm { s } } } } { R } } \end{array} \right.
$$

H桥整流器平均模型如图3所示。

![](images/137f430a87d74dd8dc2607b25295a13688e891b2475c02621ab3d209f4ade97b.jpg)  
图3H桥整流器平均模型

图1的SST可以等效为图4所示的CHB整流器，故而式（5）的平均数学模型可以推广得到图5所示的单相级联型并网变流器的平均模型。从文献[13]可知，单相级联型并网变流器的整体直流侧电压控制与单H桥整流器一致，故而可参照单H桥整流器的控制器设计。

![](images/72565d90580f5213900f92e74514f7c6a94d1b2b692a13c4fe0080f26a215f79.jpg)  
Fig.3Average model of H-bridge module   
图4 SST等效拓扑  
Fig.4Equivalent topology of SST

# 3直流侧电压平衡控制方法比较研究

单相级联型并网逆变器的总有功及无功控制如图6a所示，采用了经典的双环控制策略，其中指令电流 $i _ { \mathrm { s } } ^ { \ast }$ 由两部分组成：总直流侧电压经比例积分调节后形成的电流有功分量（ProportionalIntegral，PI)，指令无功功率计算得来的电流无功分量。指令电流与实际电流 $i _ { \mathrm { s } }$ 的差值再经过比例谐振（ProportionalResonant，PR）控制形成单相级联并网逆变器的总指令输出电压 $u _ { \mathrm { o } } ^ { \ast }$ ，最终得到各单元的平均指令输出电压 $u _ { \mathrm { a v } } ^ { * }$ 。其相内直流侧电压平衡控制主要有两种方法：调制比修正法（图6b）和有功分量修正法(图6c)。调制比修正法仅对调制比进行调整，在调节各 $\mathrm { ~ H ~ }$ 桥单元有功功率的同时也成比例地调整了无功功率；而有功分量修正的方法是对指令电压的有功分量进行调整，从而实现了各单元有功功率按需分配，无功功率平均分配的目标。图7为级联数 $n = 3$ 情况下两种方法的稳态矢量图。可以看出，调整相同的有功功率，使用有功矢量修正法取得 $P _ { i } / \Sigma P _ { i }$ 的最大值。当 $m _ { i } = 1$ ， $n = 3$ 时，根据式(6）及式（7）得到如图8所示的有功功率调节范围分析图，从图中可以看出，总调制比 $M$ 越小，相位角 $| \varphi |$ 越大，各单元所能调节有功功率的范围越大。

![](images/1b8acb4bed8e92f12651e59ceb4feef12e3a526bc643858480685bd52b9ed83d.jpg)  
图5SST的等效平均模型

![](images/d52ffe66864ee93b238337f505d6793d6b5f57c37e7f7e46726594742ef65f10.jpg)  
Fig.5Equivalent average model of SST   
图6直流电压平衡控制方法  
Fig.6DC voltage balancing control methods

![](images/e730ab51cca3c36e5de20626309e6fff23f7156d2292199dd127790ef1523047.jpg)  
Fig.7Vector diagrams in steady state

![](images/6991b02ecf0656704dc0d4f5021e7d9fc88664838c8ba983cf0acfc5fd11b095.jpg)  
图8有功矢量修正法的有功调节范围分析图 Fig.8Analysis diagram of active adjusting range with active vector correctionmethod

而使用调制比修正法时， $i$ 单元的输出电压调制比为

造成的各单元调制比差异更小，且其起到同时调节调制比和调制波相位的作用。

为了进一步量化比较两种方法的有功功率调节能力，假设级联型并网逆变器总输出电压调制比为$M$ ， $\varphi$ 为输出电压与电流的相位角， $P _ { i }$ 为 $i$ 单元的有功功率， $n$ 为级联单元数目，从而可以得到应用有功分量修正法下 $i$ 单元输出电压调制比

$$
m _ { i } = M \left\{ \left( n \frac { P _ { i } } { \displaystyle { \sum _ { i = 1 } ^ { n } } P _ { i } } \cos \varphi \right) ^ { 2 } + \sin ^ { 2 } \varphi \right.
$$

式中， $P _ { i } / \Sigma P _ { i }$ 为 $i$ 单元有功功率占总有功功率的比例，用来指示 $\mathrm { ~ H ~ }$ 桥单元的有功功率调节能力，需要满足如下约束条件

$$
m _ { i } ^ { \prime } = n \frac { P _ { i } } { \displaystyle \sum _ { i = 1 } ^ { n } P _ { i } } M
$$

$$
\frac { P _ { i } } { \displaystyle \sum _ { i = 1 } ^ { n } P _ { i } } \leqslant 1
$$

从式（6）可知，调制比最大时（即 $m _ { i } = 1$ ）可

由式（6）和式（8）进行对比可以发现， $m _ { i } ^ { \prime }$ 的表达式与 $m _ { i }$ 在 $\varphi = 0$ 时的表达式一致，故而将不同 $\varphi$ 值下的有功功率调节范围分析图（见图8）进行投影得到图9。图中， $\varphi = 0$ 对应曲线亦是使用调制比修正法时的有功功率调节能力曲线。当级联逆变器只消耗有功功率且处于额定功率时，假定 $n =$ 3， $M = 0 . 9$ ， $\varphi = \pi / 3 0$ ，从而调制比修正法下的最大有功功率调节比例为 $3 7 . 0 4 \%$ ，而有功矢量修正法为 $3 7 . 2 4 \%$ ，可见纯有功运行状态下两种方法差异不大，图9中 $\varphi = \pi / 3 0$ 与 $\varphi = 0$ 的曲线接近重合也印证了这一点。而从图8也可以看到，随着输出电压的无功分量比例增大，有功矢量修正法的有功功率调节能力强的特点愈发明显。在需要调节相同有功功率情况下，相比于有功矢量修正法，调制比修正的方法需要H桥单元采用更大的输出电压调制比，因而会带来各直流侧电压纹波差异大、电压及电流THD 大等一系列问题。

![](images/e4c89e1b8120d2ac12147c144879b606b89b4a6156e4f651686f87559a2c551e.jpg)  
图7稳态矢量图  
图9不同相位角下的有功功率调节范围  
Fig.9Active adjusting range with different phase angles

由于SST不但需要运行在有功状态，还需要发挥无功补偿等电能质量治理的作用，故而使用有功矢量修正的相内直流侧电压平衡方法更具优势。

# 4 实验验证

为了验证有功矢量修正法在级联型固态变压器中的有效性，采用图10的三模块平台分别构建了单相SST系统，直流输出端连接多组电阻炉作为负载。图11为单相三级的级联型固态变压器的实验波形，直流侧指令值设置为 $5 0 \mathrm { V }$ ，其中，CH1通道为网侧电压波形（100V/div)，CH2为网侧电流波形（10A/div)，CH3为变流器的输出电压（ $1 0 0 \mathrm { V / }$ div)，CH4为装置的直流输出端电压（50V/div)。图11a为网侧电压峰值为130V情况下的运行情况，此时高压侧的三级H桥输出电压为七电平波形；而图11b由于网侧电压较低，变流器的输出电压调制比较低，输出电平仅为五电平。图11c和11d为系统侧电压跌落和抬升过程中的波形，可以看出，在系统电压波动情况下由于负载功率恒定，高压侧的电流会发生变化，但低压直流输出侧一直保持恒定，验证了单相级联型固态变压器具有传统工频变压器所欠缺的一、二次侧故障隔离功能，同时也证明了直流平衡控制方法在各种工况下的有效性。

![](images/4befa85b423b3ee98daabde191623c90d24dc5f81bc6d43545a82c609d6c2aed.jpg)  
图10 实验装置图

# 5 结论

本文在建立单相级联型SST数学模型的基础上，讨论了不同直流电压平衡控制方法在有功功率调节能力方面的区别，指出有功矢量修正法具有更好的调节特性，更适合于单相级联型SST所处的复杂工况。为了验证基于有功矢量修正的直流电压平衡方法在SST中有效性，搭建了三级实验平台并进行试验，结果表明，该方法有较好的稳态和暂态性能，对于SST的未来应用具有重要的价值。

![](images/a0321b7f900de5459ee237ebe0208e751644281594bc4547d3d6866783cf123e.jpg)  
(a）正常稳态波形图

![](images/a9098eaf8464af545057761b6debf5d830cb40183f7398bc37a79fcd95cd010c.jpg)  
(b）网侧欠电压下的稳态波形图

![](images/76853be57b0899c05322cf83a1411418f4fb3aa86fd9ed5acaf7442e38f11968.jpg)  
Fig.10Experimental Apparatus   
(c）系统电压跌落情况下的波形图

![](images/cf820d28f58c3c32ad5ffe0324c1c779a7edb5873d23d712f32eab00b21035b4.jpg)  
  
图11单相级联型固态变压器的相关波形 Fig.11Experimental waveforms of single-phase cascaded SST

# 参考文献

[1] 王丹．配电系统电子电力变压器[D]．华中科技大 学，2006.   
[2] Xu S.Control and design of a high voltage solid state transformer and its integration with renewable energy resources and microgrid system[D]. North Carolina State University, 2013.   
[3] Iov F,Blaabjerg F,Clare J,et al. UNIFLEXPM-A key-enabling technology for future european electricity networks[J]. Epe Journal: European Power Electronics and Drives Association Journal, 2015, 19(4): 6-16.   
[4] Besselmann T,MesterA,Dujic D.Power electronic traction transformer: efficiency improvements under light-load conditions[J].IEEE Transaction on Power Electronics,2013,29(8): 3971-3981.   
[5] LaiJ S,Maitra A,Mansoor A,et al.Multilevel intelligent universal transformer for medium voltage applications[C].IEEE Industry Applications Conference,HongKong,2005:1893-1899.   
[6] 耿俊成，刘文华，袁志昌．链式 STATCOM电容 电压不平衡现象研究（一)仿真和试验[J]．电力 系统自动化，2003，27(16)：53-57. Geng Juncheng,Liu Wenhua, Yuan Zhichang. Research on the voltage unbalance of DC capacitors of cascade statcomPart one simulations and experiments[J]. Automation of Electric Power Systems,2003,27(16): 53-57.   
[7] 胡应宏，任佳佳，王建．级联 STATCOM阀组 直流侧电压不平衡现象及原因分析[J]．电力系统 自动化，2011，35(21)：96-100. Hu Yinghong,Ren Jiajia, Wang Jianze. Analysis of voltage unbalance phenomenon and causes in cluster DC-link of cascade H-bridge STATCOM[J]. Automation of Electric Power Systems,2011, 35(21): 96-100.   
[8] 李祎春，刘文里，霍霖，等．基于ANSYS 的大型 电力变压器外绕组辐向稳定[J]．电气应用，2016, 35(3): 40-44.   
[9] 刘文华，宋强，滕乐天．基于链式逆变器的 $5 0 \mathrm { M V \cdot A }$ 静止同步补偿器的直流电压平衡控制 [J]．中国电机工程学报，2004，24(4)：145-150. Liu Wenhua, Song Qiang, Teng Letian. Balancing control of DC voltages of 50MV $\mathbf { \nabla } \cdot \mathbf { \varepsilon }$ A STATCOM based on cascade multilevel inverters[J].Proceedings of the CSEE,2004, 24(4): 145-150.   
[10]Rivera S, Wu B, Kouro S,et al. Cascaded H-bridge multilevel converter topology and three-phase balance control for large scale photovoltaic systems[C]. IEEE International Symposium on Power Electronics for Distributed Generation Systems,Aalborg, Danmark,2012: 690-697.   
[11]Kouro S,Wu B,Moya A,et al. Control of a cascaded H-bridge multilevel converter for grid connection of photovoltaic systems[C]. Annual Conference of IEEE Industrial Electronics,Porto,Portuguesa, 2009: 3976-3982.   
[12]Peng F, Lai J.A multilevel voltage-source inverter with separates dc sources for static var generation[J]. IEEE Transaction on Industry Applications,1996, 32(5): 1130-1138.   
[13]Aquila A D, Liserre M, Monopoli V G,et al. Overview of PI-based solutions for the control of DC buses of a single-phase H-bridge multilevel active rectifier[J]. IEEE Transactions on Industry Applications, 2008, 44(3): 857-866.   
[14]陶兴华，李永东，孙敏．一种H桥级联型PWM

整流器的直流母线电压平衡控制新方法[J]．电工 技术学报，2011，26(8)：85-90. Tao Xinghua,Li Yongdong,Sun Min.A novel DC-link voltages balancing control method for cascaded H-bridge rectifier[J].Transactions of China Electrotechnical Society, 2011,26(8): 85-90. [15] Zhao T,Wang G,Bhattacharya S.Voltage and power balance control for a cascaded H-bridge converter-based solid-state transformer[J].IEEE

Transaction on Power Electronics,2013,28(4): 1523-1532. [16] 宫力，康勇，陈晶晶．链式STATCOM直流电 容电压分布式控制[J]．电工技术学报，2011, 26(10):217-223. Gong Li,Kang Yong, Chen Jingjing.DC capacitor voltage distributed control system for cascaded multilevel STATCOM[J].Transactions of China Electrotechnical Society,2011,26(10): 217-223.