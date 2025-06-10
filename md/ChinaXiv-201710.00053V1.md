# 几何参数对紧凑涡轮过渡段内部流动机理影响研究

张燕峰，王晏根，卢新根，韩戈，朱俊强(1.中国科学院工程热物理研究所，北京100190；2.中国科学院大学，北京1000.

摘要：本文深入探讨了定常来流条件下过渡段内部流动机理和损失机制。通过保持过渡段长高比、雷诺数和进口旋流不变，借助实验和数值模拟方法，系统地研究了过渡段中位角和出口面积对其内部流动及气动性能影响。研究发现，过渡段内部流场结构主要以对涡及轮毂和机匣区域附面层分离为主。过渡段来流尾迹、中位角及进出口面积比是影响过渡段内部流动损失的三个主要因素。其中，中位角决定了机匣第一弯逆压梯度强度，面积比主要控制第二弯静压升，上游尾迹是诱发机匣侧流动分离的主要诱因。在大中位角情况下，机匣第一弯的流动分离更严重，分离明显提前。在大面积比情况下，机匣侧不仅出现由上游尾迹堆积产生的流动分离，还会出现机匣附面层自身二维分离。随着过渡段的中位角和面积比增大，损失急剧增加。

关键词：涡轮过渡段；紧凑；流动机理；分离；损失中图分类号：TK14文献标识码：M

# Flow and Control Mechanisms in AggressiveInter-Turbine Ducts

ZHANG Yanfeng， Wang Yangen， LU Xingen， HanGe， ZHU Junqiang (1. Institute of Engineering Thermophysics, Chinese Academy of Sciences,Beijing 100190, China; 2.University of Chinese Academy of Sciences,Beijing 10oo49,China)

Abstract: The present workis aimed at providing detailed understanding ofthe flow physics and loss mechanisms in four different ITD geometries.A systematic experimental and computational study was carred out for varying duct mean rise angles and outlet-to-inlet area ratio while keeping the duct length-to-inlet height ratio,Reynolds number and nlet swirl constant in allfour geometries.The flow structures within the ITDs were found to be dominated by the counter-rotating vortices and boundary layer separation in both the casing and hub regions.The duct mean rise angle determined the severity of adverse pressure gradient in the casing's first bend whereas the duct area ratio mainly governed the second bend's static presure rise.The combination of upstream wake flow and thefirst bend's adverse presure gradient caused the boundary layer to separate and intensify the strength of counter-rotating vortices.At high mean rise angle,the separation became stronger at the casing's first bend and moved farther upstream.At high area ratios,a 2-D separation appeared on the casing. Pressre loss penalties increased significantly with increasing duct mean rise angle and area ratio.

Key word:Inter-turbine ducts; Aggressive; Flow physics; Separation; Loss

# 1、引言

为了提高经济适用性和环境友好性，现代高性能民用航空涡扇发动机通常采用大涵道比。在大涵道比涡扇发动机中，由于高、低压涡轮部件之间的气动匹配需求，通常会在高压和低压涡轮之间布置一段具有较大径向跨距的扩压流道，即涡轮过渡段。涡轮过渡段具有“承上启下”的关键作用，对发动机性能和匹配有重要影响。目前，压气机和涡轮等部件的性能提升难度加大，涡轮过渡段蕴藏的巨大潜能已经受到国内外研究者们的普遍关注。

过渡段的紧凑设计，不仅可以减小自身重量，也可以提高低压涡轮载荷能力，减少叶片(级)数，间接实现低压涡轮减重需求。然而，紧凑涡轮过渡段特有的大曲率弯曲以及高扩压率使得过渡段内部存在复杂轴向逆压力梯度及径向压力梯度，导致过渡段内部极易出现流动分离现象，并诱导出各种复杂涡系结构。另外，上游高压涡轮出口复杂流动特征(尾迹及间隙泄漏流等)与过渡段内部流场的相互作用会改变过渡段内流动损失特性，进一步增加过渡段内部流动的复杂性，强化过渡段内部二次流动，在降低过渡段气动性能的同时，增强下游低压涡轮进口流场畸变，进而恶化低压涡轮气动性能。

为了掌握紧凑涡轮过渡段设计技术，提升航空发动机整体性能，2006年，欧盟“第六框架”计划专门制定了紧凑过渡段(AIDA，AggressiveIntermediateDuctAerodynamics)科研项目，由欧洲主要航空发动机公司、大学及科研院所合作共同参与，对紧凑涡轮过渡段内部流动机理开展了大量研究工作[1-14]，获得了显著的研究成果。并且，相关研究成果已经应用于高性能航空发动机低压涡轮部件气动设计，并取得了良好收益。相关研究成果已经或逐渐得到工程应用。欧洲CFM公司将支板-低压涡轮导向器一体化设计应用于LEAP-X系列发动机，使得低压涡轮部件减重大约在5 磅以上[15]。与此同时，美国通用电气公司也将紧凑涡轮过渡段(TTMF)技术应用于低压涡轮系统设计中，使低压涡轮效率和负荷有所提高的同时，重量也相对减轻[16]。

相比而言，国内相关高校和研究机构针对涡轮过渡段内部流动机理做了大量研究[17-21]，研究内容涉及不同进气条件下过渡段流动机理、端壁型线优化及分离流动控制等方面。虽然取得了一些成果，但相关研究还不够系统全面和深入。并且研究大多采用数值计算，缺乏实验验证。研究发现数值计算在模拟大曲率弯曲、高扩压率和有流动分离的紧凑涡轮过渡段时，存在流场细节捕捉不到位，如预测的附面层分离相比实验结果明显滞后，更甚至会出现完全捕捉不到附面层分离的情况[21]。这给缺乏实验验证的过渡段数值模拟研究带来了一系列问题。

面向高性能航空发动机研制的国家重大需求，深入理解紧凑涡轮过渡段内部流动机理及其损失机制，将是高性能涡轮过渡段设计中最为关键的技术之一。本文基于课题组长期从事紧凑涡轮过渡段的研究基础之上，深入探讨了定常来流条件下过渡段内部流动机理和损失机制，通过改变过渡段中位角和进出口面积比，保持过渡段长高比、雷诺数和进□旋流强度不变，借助实验和数值模拟方法，系统地研究了几何参数对过渡段内部流动及气动性能影响，澄清了紧凑涡轮过渡段内部流动损失机理及其损失机制。

# 2、实验和计算方法

# 2.1试验设备和测量装置

本次实验是在加拿大国家科学院的大型低速过渡段实验台上完成的。气流通过离心鼓风机经扩压段进入稳压箱。在稳压箱之后，气流经收缩段和椭圆形鼻锥加速后进入过渡段测试部分，如图1所示。风洞的自由流湍流度通过鼻锥下游的湍流网格提升到 $2 . 3 \%$ 。在实验中，借助过渡段上游一排48片旋流叶片组成的环形叶栅模拟高压涡轮的尾迹和旋流，旋流角为 $2 0 ^ { \circ }$ 沿径向均布。同时，涡轮过渡段测试部分的机匣和轮毂均可更换。

过渡段轴向静压分布通过端壁静压孔得到。其中，机匣上有一排(40个)静压孔，而轮毂上有两排静压孔，每排40个。在机匣和轮毂表面进行了表面油流显示实验，用来表证近端壁流动状况。总静压及速度分量，通过一个头部直径为 $1 . 6 \mathrm { m m }$ 的L形七孔探针测得获得。探针直线运动机构安装在可旋转机匣上，用以实现探针从轮毂到机匣的径向测量。结合机匣周向旋转，保证探针的截面测量。每个测量面的测量网格在径向方向至少包含31个点，周向31个点 $( 7 . 5 ^ { \circ }$ )以覆盖一个上游旋流叶片通道。测量位置在图1中也给出。

试验中，压力数据通过DSA3217压力扫描仪测得。扫描仪有十六个温度补偿差分压力传感器，量程为 $\pm 1 2 5 0 \mathrm { P a }$ 。压力测量不确定度在量程 $0 . 0 5 \%$ 之内。所测动压和总压不确定度分别为参考动压的土$0 . 5 \%$ 和 $\pm 0 . 2 5 \%$ 。在实验中，基于过渡段进口高度和自由流/参考速度的雷诺数保持为150000。

![](images/a5f7f2c9c60f3baba0008f569e76417f4997080f3e28d1cc650e7e3ec666bccc.jpg)  
图1过渡段试验台

# 2.2研究对象

涡轮过渡段面积比、长高比和中位角分别通过参数AR、 $\mathrm { L } / \mathrm { h } _ { 1 }$ 和 $\Phi$ 来定义。其中，进口高度 $\mathbf { h } _ { 1 }$ 受试验台约束，固定为 $7 6 . 2 \ : \mathrm { m m }$ 。本文共测试四组过渡段，表1与图2给出了各个过渡段相关的几何参数。其中，过渡段原型(ITD-A)是以加普惠公司PW600 型涡扇发动机过渡段参数为原型，在此基础之上，通过使用NUMECA Fine/Design3D 软件，设计三组紧凑涡轮过渡段几何模型，分别为ITD-B，ITD-C和ITD-D。

表1：涡轮过渡段几何参数

![](images/0608e7d8fb0f042d9db3f0771b1b407750eb0e1a010f4b7cd65bd947143489f1.jpg)

![](images/5e269ea1752ea19a0a9ce99b3d979e4f856ff2af673b615e04f1b9f3cb0ab5f4.jpg)  
图2涡轮过渡段几何参数示意图

# 2.3计算模型

数值计算采用NUMECAFINE/Turbo[22]商用软件对雷诺平均Navier-Stokes方程进行了数值求解。图3给出了过渡段计算域网格划分。网格节点总数通过网格依赖性研究得到，大约在是350万。壁面$\mathbf { y } +$ 均小于或等于1。数值模拟进口边界条件通过实验测量所得速度、湍流强度和湍流长度尺度分布来建立。出口边界条件设置为均匀的大气压力，所有固体壁面设为绝热无滑移条件。同时，假设流场发展为充分湍流，湍流方程闭合通过剪切应力输运(SST)k-ω双方程模型实现。这个方法在更早的研究中已被实验证实有效[23]。

![](images/1f4874962c2fbaa9e3c6337c37ea3088257e76be9f1b83efba3244e01b191900.jpg)  
图3过渡段计算域

# 2.4数据处理

过渡段流场测试主要采用七孔探针，测试数据用于计算速度、压力和涡量场。涡轮过渡段的气动性能通过总压损失系数 $\mathrm { Y _ { P } }$ ，以及管道效率n来评估。总压损失和管道效率均参考旋流叶片上游的来流条件，如图1中位置R所表示。

涡量， $\omega$ ，定义为速度矢量的环量 $( { \boldsymbol { \nabla } } { \times } { \mathsf { V } } )$ ，用来衡量流体微团局部旋转速率。速度矢量在径向和切向分量可以从测量中获得，然而根据测量计算轴向速度梯度是相当不合理的，因为测量面之间的轴向距离太大。因此，采用Gregory-Smith et al[24]的方法计算的轴向、切向和径向涡量，即：

$$
\mathfrak { o } _ { \mathrm { x } } = \frac { 1 } { \mathrm { r } } \bigg ( \frac { \partial \big ( \mathrm { r V } _ { \mathrm { t } } \big ) } { \partial \mathrm { r } } - \frac { \partial \mathrm { V } _ { \mathrm { r } } } { \partial \mathrm { t } } \bigg )
$$

$$
\mathfrak { w } _ { \mathrm { t } } = \frac { 1 } { \mathrm { V _ { x } } } \left( \mathrm { V } _ { \mathrm { t } } \mathfrak { w } _ { \mathrm { x } } - \frac { 1 } { \rho } \frac { \hat { \varrho } \mathfrak { p } _ { 0 } } { \hat { \alpha } \mathrm { r } } \right)
$$

$$
\omega _ { \mathrm { r } } = \frac { 1 } { \mathrm { V _ { x } } } \Bigg ( \mathrm { V _ { r } } \omega _ { \mathrm { x } } + \frac { 1 } { \rho \mathrm { r } } \frac { \partial \mathfrak { p } _ { 0 } } { \partial \mathrm { t } } \Bigg )
$$

因此，总涡量， $\omega$ ，定义为：

$$
\mathrm {  ~ \omega ~ } = \frac { \omega _ { mathrm { x } } \mathrm { V _ { x } } + \omega _ { \mathrm { t } } \mathrm { V _ { t } } + \omega _ { \mathrm { r } } \mathrm { V _ { r } } } { \sqrt { { \mathrm { V _ { x } } } ^ { 2 } + { \mathrm { V _ { t } } } ^ { 2 } + { \mathrm { V _ { r } } } ^ { 2 } } }
$$

总涡量， ${ \bf \omega } _ { \infty }$ ，作为涡轮过渡段内涡量强度的一个合理指标。本文中，总涡量进一步用上游参考速度和进口管道高度进行了无量纲化处理，即 $\mathrm { C _ { \omega } { = } \omega \cdot h _ { 1 } / V _ { R } }$ 。在下文的分析中，正涡量对应于朝着上游看是顺时针旋转的涡结构。

# 3、结果及分析

针对涡轮过渡段，通过实验和数值模拟，重点分析中位角Φ和面积比AR对过渡段流场结构和性能的影响。首先对原型ITD-A作详细流场分析。其次对比ITD-B 和原型，以检验在既定面积比时，增加中位角对过渡段的影响。随后，比较ITD-C 和原型，对比既定中位角时，增大进出口面积比，对过渡段影响。然后，分析同时增加面积比和中位角的ITD-D内部流场结构。最后，讨论了过渡段损失和性能。

# 3.1过渡段内部流动机理

如图4给出了ITD-A过渡段的测试结果。图4(a)为轮毂和机匣侧预测的周向质量平均静压系数 $\left( \mathrm { C } _ { \mathrm { P s } } \right)$ 和测量的静压系数。轴向距离按过渡段轴向总长度进行了归一化处理，即位置0和1分别对应于过渡段曲率变化的第一个点和最后一个点。涡轮过渡段在进口位置向上游拓展了 $20 \%$ ，在出口位置向下游拓展了 $40 \%$ 。实验测量和数值结果吻合良好。过渡段看似简单，其内部流场确异常复杂。

从图中可以看出，总体上机匣侧流体主要处于逆压梯度之中，而轮毂侧流体则基本上经历一个顺压梯度。在A3上游，轮毂侧静压比机匣侧高，经过此截面后情况相反。沿机匣，近壁面流体随着进入第一弯开始加速，随后经历一个强逆压梯度至第二弯，最后经一个微弱的顺压梯度至过渡段出口。虽然从图4(a)中的静压数据无法推断流动是否分离，但图4(c)中的油流显示结果表明，机匣表面的强逆压梯度导致了附面层分离。沿轮毂，经过初始区域的一段逆压梯度后，静压几乎保持不变至两个弯处的中间位置。从 $\scriptstyle \mathbf { x } = 0 . 7$ 位置开始出现一个强逆压梯度，使得图4(c)油流结果显示附面层在大约 $\scriptstyle \mathbf { x } = 0 . 9$ 的位置发生分离。

从图4(b)可以发现，由于上游旋流沿径向均匀分布，在过渡段进口(A1)总压亏损尾迹区和轮毂、机匣都几乎垂直。根据角动量守恒，在第一弯，机匣侧旋流角比轮毂侧旋流角减尾迹在第一弯发生了顺时针的偏斜，在第二弯则发生逆时针偏斜。仔细观察A2

![](images/866ccd5999f576087d95b80e01c59e3aa07612a94c85b455503e953dcc1c7265.jpg)  
(a)过渡段沿轴向静压分布

![](images/895fd45c8c9b812ac072c4e74a90a2ac9e0783302d0613368cb56954d551f925.jpg)

![](images/ded2a0601fc35ce3eb0d9dadd64d61b2b4a5ba1b912466d3f904aa1bf6f41790.jpg)  
(b）过渡段内部涡量及总压云图  
(c）过渡段表面油流结果 图4ITD-A过渡段测试结果

轮毂附近流场可以发现，在过渡段第一弯径向向上的压力梯度(图4(a)所示)将轮毂低能附面层流和尾迹向机匣侧输运，并卷起形成一对对旋涡。该轮毂对涡和来自上游的涡系(通道涡和尾迹脱落涡)融合在一起，增强对涡强度。同时，轮毂低能流被夹带进入对涡中心，在大约 $2 5 \%$ 通道高度位置形成一个压损中心。对涡在A3截面之前均保持明显存在。之后，径向向下的压力梯度限制了轮毂处低能流的卷起，使得轮毂对涡在向下游传播过程中逐渐耗散。与此同时，机匣处，由于逆压梯度和轮毂区低能流体共同导致机匣附面层发生显著堆积，形成一个压损中心。直到A3截面下游，在向下径向压力梯度作用下，形成了机匣对涡，该对涡结构成为A3截面下游中的主要流动特征。轮毂和机匣对涡的痕迹可以由图 4(c)油流显示中低剪切应力区所标示。

# 3.2中位角对过渡段影响

过渡段ITD-B，保持和ITD-A 相同的面积比及长高比，但中位角增加 $2 5 \%$ 。图5分别给出了ITD-B过渡段静压系数 $\mathrm { \Delta C _ { P s } }$ 沿轴向分布，六个测量截面上总涡量 $\scriptstyle { \mathrm { C o } }$ 和总压系数 $\mathrm { { C } _ { \mathrm { { P 0 } } } }$ 云图以及机匣处油流显示结果。研究发现，增大中位角影响主要集中在机匣侧流动特征。相比于ITD-A，ITD-B中机匣第一弯的逆压梯度明显增强，使得机匣附面层在第一弯处更厚，且堆积现象更为严重，引发在第一弯上游截面B2位置发生了显著的机匣附面层分离，图5(c)所示。该分离在ITD-A过渡段位于A3截面下游，但几乎难以分辨，见图5(b)。从涡量图上还可以看出，相比于原型ITD-A，机匣侧第二弯形成了更强的对涡。在轮毂侧，两组几何模型中的涡结构和强度相似。虽然两组过渡段流动机制和压力梯度等看上去相当，增加中位角，由于机匣侧更显著的流动分离，导致了损失急剧增大。

# 3.3面积比对过渡段影响

过渡段ITD-C，保持和ITD-A相同中位角和长高比，面积比增大了 $20 \%$ 。图6给出了过渡段端壁面沿轴向静压系数 $\mathrm { C _ { P s } }$ ，过渡段内部涡量及总压云图以及机匣处油流显示结果。首先从图6(a)静压分布中可以看出：这两组过渡段中最明显的差别是由于扩压率变大，在ITD-C第二弯的静压升更大。另外，在第一弯后机匣侧的逆压梯度稍微变大了。从图 6(b)压力场中可看出，由于机匣侧第一弯的逆压梯度增大了，ITD-C 过渡段机

![](images/57b4fe34abc1365532a1106343f30a8177ee833731a4129833f0b7016356f195.jpg)  
(a)过渡段沿轴向静压分布

![](images/17067ef99286aab1d0982df46be414cd4045ee30654e076c588b749a050b3e18.jpg)  
(b)过渡段内部涡量及总压云图

![](images/d91aa29c5ea42960ac0a71533384488159d5cb7f424e8649f64652382d22ddf3.jpg)  
(c）过渡段表面油流结果

图5ITD-B过渡段测试结果

![](images/43307c0ead760c41a8a02522068a990b5da2f9b9d95dd8bb5dfae9a6d57f6c89.jpg)

![](images/3aa31b80751b0b8dd601623931a55955cd3abc5eb5fed49a372cc63e15024de7.jpg)  
(a)过渡段沿轴向静压分布  
图6ITD-C过渡段测试结果

匣附面层堆积现象比ITD-A更强。涡量云图显示，ITD-C中的机匣对涡强度不如原型ITD-A。机匣油流结果显示，ITD-C中周期性流动分离的下游伴随着一个二维流动分离。图中两个红色箭头标示，位于C3截面下游。这种二维分离现象以一股在ITD-A和ITD-B中重未观察到的回流为典型特征。对油流结果进一步观察发现，这股流动分离在流向上基本是二维性。但是，从测试结果无法确定，这股分离是由被输运到机匣处的低能尾迹流导致的，还是由机匣附面层自身由于更高的静压升导致。

为了澄清ITD-C过渡段中机匣附面层分离与上游尾迹之间的关系，分别对上游尾迹在过渡段进口已经充分掺混和尾迹保持其性质向下传播的两组ITD-C进行数值计算。虽然数值模拟对机匣分离位置和对涡强

度的预测不够精准，但是所提供附面层相关信息可以充分回答上述问题。如图7所示为两组模拟结果。

在考虑尾迹低能流体的模拟中，如图7(a)，机匣附面层分离的特征是，由于尾迹堆积团分离和机匣附面层自身二维分离的联合作用，分离线呈周期性波纹状。在尾迹于过渡段进口掺混均匀的模拟结果中，如图7(b)，分离线被一段与机匣附面层自身二维分离直接关联关系的圆弧形分离线代替。由此可以证明，机匣附面层自身二维分离的发生和尾迹低能流体有关。进一步研究发现，将图7(a)的周期性分离线叠加到图7(b)，很快清楚地发现二维分离的位置没有改变，并且看起来像是上游分离填充在波纹分离线和线性分离线之间的区域。因此，可以进一步确认，涡轮过渡段机匣侧这两种分离是完全不同。前者，由一弯处向上径向压力梯度迫使轮毂附近低能流体和尾迹向机匣侧流动迁移、堆积，当其不能克服机匣逆压梯度时，在两个弯之间发生周期性的分离，在ITDITD-B中非常明显。后者，机匣附面层自身二维分离(呈回流现象)仅仅是因为面积增大使得过渡段在第二弯前有更高静压升，在后续ITD-D 中非常明显。

![](images/2478b4d04ff97176cfc8d0dd6fd478f852ff596eab6bf1edf7697fd2c10d27a1.jpg)  
图7有无上游尾迹时ITD-C预测总压系数云图

# 3.4中位角和面积比的共同作用

过渡段ITD-D，综合了ITD-B和ITD-C设计参数，比原型的面积比增大 $20 \%$ 且中位角增大 $2 5 \%$ 。图8给出了ITD-D过渡段静压分布，内部涡量及总压云图以及机匣处油流显示结果。与其他几何模型一样，过渡段第一弯处向上的径向压力梯度驱动轮毂侧低能流体和尾迹向机匣侧运动。机匣侧，由于中位角和面积比同时增大，加大了第一弯区域的径向压力梯度及出口静压升，导致了第一和第二弯之间的大范围附面层分离。机匣分离的开始位置在截面 D3处，表现为高总压损失和强的正涡量。正涡量区域在ITD-A相同位置截面A3中几乎不可见，甚至在机匣分离相当严重的ITD-B 中(B3)也不可见。尽管在ITD-D中机匣附面层堆积现象更为严重，但是机匣对涡相比于原型过渡段中的却更弱。这主要是因为大二维分离和第二弯的静压升抑制了对涡发展。在轮毂侧，顺压梯度使附面层保持附着，且在截面D2，D3，D4 处相对薄一些。

![](images/10fb5976f5b4d99ff7f6b7f9f21f3a5ccd5f2ea12b298f876a646bed3a0f0b6c.jpg)  
(a)过渡段沿轴向静压分布

![](images/ba20e13ed83aae17e0bb009fb0b27d5aebf10ba5e08161b0308bdd9e6f8b7b0a.jpg)  
(b)过渡段内部涡量及总压云图

![](images/80866806b7dbc3b1c1c2c67083502c53e0056a42760deb64c00de54bd0a23aaf.jpg)  
(c）过渡段表面油流结果   
图8ITD-D过渡段测试结果

# 3.5过渡段流动损失机制

本文四组涡轮过渡段差异主要在于机匣侧流动的发展，因此本部分旨在评估紧凑涡轮过渡段中的损失机制，尤其是机匣侧。总压损失通过七孔探针在涡轮过渡段出口面(第五测量面)所测数据计算得到。如图9给出了经周向质量平均的总压系数沿径向分布。第五测量面指的是截面A5、B5、C5、D5，分别对应于过渡段A、B、C、D出口截面。为了验证上游尾迹对损失的影响，继续前一部分的讨论，进行了两组数值模拟。在第一组模拟中，假设在旋流叶片下游有一个混合平面，故上游尾迹被认为在涡轮过渡段进口已充分混合。图9中‘CFDmixed’指的是从这组模拟中计算的损失。在第二组中，允许上游尾迹保持其性质并向下游流动进入过渡段。图9中‘CFD’指的是第二组模拟中计算的损

失。

如图9(a)所示，在ITD-A中，机匣区域是最主要损失源。从‘CFDmixed’的压力分布曲线可明显看出，上游尾迹对减小损失有一定好处。当进口流体被考虑为充分混合时，机匣区域的损失显著增加。因为在这种情况下，对涡不能在机匣区域形成，附面层厚度在机匣壁面上机匣增长，从而增加了压力损失。ITD-B中，增大中位角对机匣区域的损失没有带来显著差别，见图9(b)。虽然CFD 很好地捕捉到了损失的趋势，却低估了机匣区域的损失。在图9(c)中，和原型涡轮过渡段对比，ITD-C中的压力损失在整个叶高范围内加大。由于机匣二维分离，主要损失增加发生在机匣区域。对比‘CFDmixed'和‘CFD'模拟结果，可以看出，在紧凑过渡段中，尾迹对减小机匣区域损失没有效果。在ITD-D中，通过增加中位角和面积比，损失在整个展向上增加。图 9(d)也显示，机匣区损失急剧增加，这主要是由于存在大范围机匣分离。

![](images/da0c2fb1f683b79cc371699c4923cb0ce6b3b48b309aae310e93cef1b582a9ee.jpg)  
图9过渡段出口周向质量平均的总压系数

图10 对比了过渡段出口(第五截面)和下游位置(第六截面)测量的质量平均总压损失系数 $\mathrm { Y _ { P } }$ ，及掺混损失系数 $\mathrm { Y } _ { \mathrm { m i x e d } }$ 。其中，掺混损失系数 $\mathrm { Y } _ { \mathrm { m i x e d } }$ 是衡量过渡段整体上总压损失最具代表性的指标。从图中可以发现，原型过渡段ITD-A损失最小，而ITD-D的损失最大。压力损失在紧凑型设计中显著增加。如前文所诉，损失整体上归因于机匣区域。在ITD-B中，增加中位角，涡轮过渡段第一弯强烈的机匣分离使损失增加。在ITD-C中，增加面积比，损失的增加主要来源于机匣附面层二维分离。明显的机匣侧流动分离和大范围二维分离共同作用于ITD-D，使其损失增大。比较ITD-B和ITD-C的掺混损失系数发现，ITD-B中的损失更大，其原因在于机匣侧存在更强的对涡。

![](images/adca48ac39b23c419f47116b2a20947310fcb2eb594c4082ade6e28ff568257a.jpg)  
图10:总压损失系数

管道效率n和静压恢复系数见表2。最高和最低的管道效率分别在ITD-A和ITD-D中，和前文的分析一致。对于一个给定的面积比，增加管道的中位角会显著降低管道效率。由此得出的结论是，管道的中位角和面积比一样关键，不仅影响流动机理，而且显著影响管道的损失。

表1：压力恢复系数和管道效率  

<html><body><table><tr><td colspan="2">CPI</td><td>Cp:</td><td>n=(Cp:/CPI)</td></tr><tr><td>ITD-A</td><td>0.385</td><td>0.327</td><td>85.0%</td></tr><tr><td>ITD-B</td><td>0.385</td><td>0.290</td><td>75.4%</td></tr><tr><td>ITD-C</td><td>0.571</td><td>0.417</td><td>73.0%</td></tr><tr><td>ITD-D</td><td>0.571</td><td>0.366</td><td>64.1%</td></tr></table></body></html>

# 4、结论

本文旨在对紧凑涡轮过渡段内部流动机理和损失机制有更深入的认识。在保持长高比恒定时，系统地研究改变进出口面积比和中位角对涡轮过渡段内部流动影响。

研究发现涡轮过渡段中流动结构主要是对涡以及机匣和轮毂侧的附面层分离。机匣侧的流动结构受到了几何因素的显著影响。增大中位角，过渡段第一弯逆压梯度增加，结果使机匣侧发生流动分离。这个分离反过来强化了机匣的对涡，导致更大的损失。增加面积比，机匣不仅存在流动分离，而且还发展出一个产生机制明显不同的二维分离。机匣流动分离的本质在于，轮毂低能流体和尾迹输运至机匣的流体不能克服机匣侧的流向逆压梯度。涡轮过渡段第二弯的高静压升是形成二维分离的主因。上游尾迹流、机匣逆压梯度和过渡段第二弯的静压升，这三者实际上控制了过渡段内部流场结构。中位角决定机匣逆压梯度并改变对应区域内的流动。面积比控制过渡段第二弯的静压升，从而影响机匣侧流动。

过渡段总压损失随着其设计更紧凑而显著增加。损失主要归因于机匣区域的流动。上游尾迹在传统涡轮过渡段中是有利因素，它在有大中位角或大面积比的紧凑管道中却导致了显著的损失。增加中位角后，更强烈的机匣分离导致了损失增加。增加面积比后，损失增加是机匣侧有更大二维附面层分离的后果。中位角作为与面积比同样重要的参数，在过渡段设计的初始阶段必须考虑。

AR 面积比 $\mathbf { \alpha } = \mathbf { A } _ { 2 } / \mathbf { A } _ { 1 }$   
$\Phi$ （204号 中位角 $\tau { = } \mathrm { t a n } ^ { - 1 } ( [ \mathrm { R } _ { 2 , \mathrm { m e a n } } \mathrm { - R } _ { 1 , \mathrm { m e a n } } ] / \mathrm { L } )$   
$\mathbf { h } _ { 1 }$ （204号 过渡段进口高度   
L 过渡段轴向长度   
@ 涡量   
$\mathrm { C } _ { \infty }$ （20 涡量系数   
X 轴向坐标

# 参考文献

[1] Couey, P.T., McKeever, C.W., Malak, F.M.. Balamurugan， S.， Veeraraghava, H.and Dhinagaran,R.， 2010,“Computational Study ofGeometricParameterInfluence on Aggressive Inter-Turbine duct Performance" ASME Paper GT2010-23604.   
[2]Dominy, R.G., and Kirkham, D.A., 1995, “The Influence of Swirl on the Performance of Inter-Turbine Diffusers",VDI Berichte 1186, pp.107-122.   
[3]Dominy, R.G., and Kirkham, D.A., 1996, “The Influence of Blade Wakes on the PerformanceofInter-TurbineDiffusers", ASME Journal of Turbomachinery， 118, pp. 347-352.   
[4]Dominy, R.G., Kirkham, D.A., and Smith A.D.，1998，“Flow Developmentthrough   
r 径向坐标   
t 切向坐标   
V 速度   
Cp0 总压系数=(P。-P0,R)/(0.5pV²)   
Cps 静压系数 $= ( \mathrm { P _ { s } } - \mathrm { P _ { s , R } } ) \big / ( 0 . 5 \rho \mathrm { V _ { R } } ^ { 2 } )$ （20   
$\overline { { \widehat { C } } } _ { \Xi \Xi }$ 质量平均的 $\mathrm { C _ { P s } }$ 周向质量平均的总压系数   
$E _ { E B }$ 质量平均的总压系数   
$\sum \limits _ { i = 0 } ^ { \infty } f _ { i , j }$   
$\mathrm { Y } _ { \mathrm { P } }$ （20 参考过渡段进口的质量平均总压损 失系数 $\varXi$ （20 $\overline { { \mathbf { C } _ { \mathrm { \tiny ~ P 0 , i n l e t } } } } - \overline { { \mathbf { C } _ { \mathrm { \tiny ~ P 0 , o u t } } } }$   
Y mixed 参考过渡段进口的掺混总压损失系 数   
（204号 $\mathfrak { a }$ （20 径向气流角 ${ = } \mathrm { t a n } ^ { - 1 } ( \mathrm { V _ { r } / V _ { x } } )$   
$\beta$ 旋流角 ${ = } \mathrm { t a n \mathrm { \overline { { \Omega } } ^ { - 1 } ( V _ { t } / V _ { x } ) } }$ （204   
CPi 理想静压恢复系数 $: = \left( 1 - \mathrm { A R } ^ { - 2 } \right)$   
n 管道效率 $= \overline { { \overline { { \mathsf { C } } } } } _ { \Xi } / ( \bar { \Xi } 1 - \mathrm { A R ^ { - 2 } } )$ （20 Inter-turbine Diffusers",ASME Journal of Turbomachinery, 120, pp.298-304.   
[5]Hu, S. Z., Zhang, Y.F., Zhang, X.F., and Vlasic，E.，2011，“Influences of Inlet Swirl Distributions on an Inter-Turbine Duct,Part I: CasingSwirl Variation”， ASMEPaper, GT2011-45554.   
[6]Zhang,Y.F.,Hu, S.Z., Zhang, X.F.,and Vlasic,E.，2011,“Influences of Inlet Swirl Distributions on an Inter-Turbine Duct, Part II: Hub Swirl Variation",ASME Paper, GT2011-45555.   
[7] Marn A.， Gottlich E.， PecnikR, MalzacherF.J., Schennach O.andPirkerH.P., 2007，“ The Influence of Blade Tip Gap Variation on The Flow Through an Aggressive S-ShapedIntermediate Turbine Duct Downstream of a Transonic Turbine Stage - Part I: Time-Averaged Results",ASME Paper GT2007-27405.   
[8] Gotlich E.， Marn A.， Pecnik R, Malzacher F.J., Schennach O.and Pirker H.P., 2007，“ The influence of Blade Tip Gap Variation on the Flow Through An Aggressive S-shapedIntermediateTurbine Duct Downstream of a Transonic Turbine Stage - Part II: Time-Averaged Results and Surface Flow”,ASME Paper GT2007-28069.   
[9]Marn,A., Gottlich,E., Malzacher F.and Pirker, H.P.,2009，“The Effect of Rotor Tip Clearance Size onto the Separation Flow ThoughaSuper-AggressiveS-shaped Intermediate Turbine Duct Downstream of a Transonic Turbine Stage”，ASME Paper GT2009-59934.   
[10] Norris,G.，Dominy,R.G.，and Smith, A.D.，1998,“A Strut Influenced within a Diffusing Annular S-shaped Duct”，ASME Paper 98-GT-425.   
[11] Norris,G.，and Dominy,R.G.,1997, “Diffusion Rate Influences on Inter-Turbine Diffusers”， Proceedings of the IMechE Part A-Journal of Power and Energy， 211，pp. 235-242.   
[12] Axelsson L.-U.， Arroyo OssoC., Cadrecha D. and Johansson T. G., 2007, "Design, Performance Evaluation and Endwall Flow Structure Investigation of an S-shaped Intermediate Turbine Duct’， ASME Paper GT2007-27650.   
[13] Axelsson，L.-U.，and Johansson， T.G., 2008，“Experimental Investigation of the Time-Averaged Flow in an Intermediate Turbine Duct”,ASME Paper GT2008-50829. [14] Gottlich，E.， 2011," Research on the AerodynamicsofIntermediateTurbine Diffusers", Progress in Aerospace Sciences, 47. pp.249-279.   
[15]Denos,R., 2008,“Gas Turbine Research in European Projects”,2nd Joint EVI-GTI International GasTurbine Instrumentation Conference, Keynote Lecture.   
[16]Walther, R., 2012, "RecentChallengesinAirBreathingPropulsions ", 14th International Symposium on Transport Phenomena and Dynamicsof Rotating Machinery, InvitedLecture.   
[17]安柏涛，韩万金，王松涛，王仲奇,2001， “大扩张角子午流道型线对损失的影响” 推进技术，22(3)：211-214   
[18]陈江，朴龙贤，杜刚，张慧，2011，“涡 轮过渡段气动性能数值优化”工程热物理学 报，32(2): 210-214.   
[19]唐洪飞，黄洪雁，韩万金，2009，“大 子午扩张涡轮过渡段的子午型线”,推进技 术，30(4): 439-445.   
[20]宋石平，吴虎，史俊，毛凯，徐倩楠， 2012，“高涵道比发动机涡轮过渡流道性能 模拟”,航空计算技术，42(1)：24-31.   
[21]胡书珍，2011，“高低压涡轮过渡段内 部复杂流动机理及调控研究”，中国科学院 研究生院博士论文.   
[22] NumecaFine/Design3DV8.9 User Manual, 2011.   
[23] Zhang， X.F.， Hu， S.Z.， Benner,M., Gostelow,P.andVlasic，E.，2010, “Experimental and Numerical Study on an Inter-turbine Duct",ASME 14th International MechanicalEngineeringCongress & Exposition, IMECE 2010-37322.   
[24] Gregory-Smith,D.G.， Graves, C.P.,and Walsh， J.A.， 1988，“Growth of Secondary Loss and Vorticity in an Axial Turbine Cascade", ASME Journal of Turbomachinery, 110, pp. 1-8.