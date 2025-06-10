# 对转压气机内叶排干涉效应的数值分析

高丽敏 苗芳 李瑞宇 刘波（西北工业大学动力与能源学院，西安，710072)

摘要：本文数值模拟了设计工况下对转压气机内部非定常流场，分析了对转压气机内导叶与转子之间以及转子与转子之间的干涉效应对整机的非定常影响。结果表明，两排转子交界面上的非定常流量波动最剧烈，说明两排转子之间动/动干涉的强度大于导叶与转子之间的动/静以及静/动干涉强度；通过典型叶高处的非定常流场分析，结合不同叶排进口处的非定常脉动强度分析，对转压气机内部的设计和流动机理有了深入认识，各排转子进口处的非定常脉动强度沿着流向增强，由于出口导叶与上游转子间的轴向间隙特别小，出口导叶进口处非定常脉动最为强烈。

关键字：对转压气机；转子/转子干涉；导叶/转子干涉；非定常模拟中图分类号：V231.3 文献标识码：A

# Further study on blade interactions in counter-rotating axial flow compressor

GAO Li-min，MIAO Fang，Li Rui-yu,LIU Bo (School of Power and Energy, Northwestern Polytechnical University,Xi'an 710072,China)

Abstract:The unsteady flow field of the counter-rotating axial flow compressor(CRAC) under design condition was time accurately simulated,the unsteady efects between every rotor and guide vane were analyzed,which contains the guide vane/rotor interaction and rotor/rotor interaction.The results indicate thatthe unsteady mass flow on the interface of two rotors fluctuates stronger than the other two interfaces,so the unsteady interaction between two rotors is the strongest in the CRAC.The unsteady flow field at typical height was analyzed;combined with the unsteady fluctuation intensity，the further design and mechanism of the CRAC was investigated. The unsteady fluctuation intensity increases with the flow direction,the axial distance between the second rotor and the outlet guide vane (OGV) is so short that the unsteady fluctuation intensity at the inlet ofthe OGV is the strongest.

Key Words: Counter-rotating compressor; Rotor/rotor interaction; Guide vane/rotor interaction; Unsteady simulation

# 0引言

对转压气机取消了两排转子之间的静子部件，并且两排转子反向旋转，很大程度上提高了推重比而在航空领域备受关注[1-2]。相比常规压气机，对转压气机结构紧凑，做功能力强；但是由于缺少静叶排对气流的梳理，对转压气机内部流场复杂[3]。目前国内外关于对转压气机内部非定常流动机理的研究不多[4-5]，而对转压气机中同时存在转子与转子之间的动/动干涉和导叶与转子之间的静/动干涉，两排转子同时受到尾迹和势流的影响，整机的非定常性值得我们深入研究。本文旨在采用非定常方法模拟对转压气机设计工况下整机非定常流场，充分考虑了进、出口导叶与两排转子之间的相互干涉，目的是对对转压气机试验台内部的非定常流场有更系统深入的认识。

# 1研究对象

本文的研究对象为西北工业大学轴流式双排对转压气机试验台，由进口导叶、两排反向旋转的转子叶排和出口导叶组成，各叶排叶片数分别为22、19、20和32，气动设计参数和试验结果见文献[3],这里不再赘述。

# 2 数值方法

# 2.1计算网格及边界条件

为减少计算通道数，在稠度不变的前提下将各排约化，约化后的叶片数分别为20、20、20和30，非定常计算域包含2个进口导叶（IGV）叶片、2个转子1（ROT1）叶片、2个转子2（ROT2）叶片和3个出口导叶（OGV）叶片；计算网格由Autogrid5生成，其中进、出口延伸段采用H型网格，叶片通道内采用O型结构化网格，叶顶间隙内采用蝶形网格；其中两排转子沿着展向网格数均为81，周向和流向分别为33和225，近壁面网格高度为 $5 { \times } 1 0 ^ { - 6 } \mathrm { m }$ ，${ \mathrm { Y } } ^ { + }$ 值在1-5之间，整个计算网格满足网格无依赖性[6],整个数值计算网格总数约为563万，计算网格见图1。

# 2.2非定常参数设定

非定常计算采用FINETM/Turbo 模块，基于双时间推进求解相对坐标系下的Navier-Stokes方程，湍流模型采用 Spalart-Allmaras 模型，非定常计算以定常计算结果作为初场，叶排间参数传递采用滑移界面法。进口给定总温288.15K，总压 $1 0 1 3 0 0 \mathrm { P a }$ ，轴向进气；出口给定平均静压117500pa；固体边界采用绝热壁面、无滑移条件。非定常计算周期定义为两排转子各自转子2个栅距的时间，每个计算周期内设定80个物理时间步，虚拟时间步数为50步。

# 3计算结果分析

# 3.1典型叶高截面上的非定常流场分析

图2给出了某瞬时 $50 \%$ 叶高对转压气机内熵云图，由于进口导叶采用零弯度设计，相应的尾迹损失很小，向下游传播的过程中在转子1通道逐渐耗散；第一排转子的尾迹被下游反向旋转的转子2切割，向下游传播耗散的过程中，部分低能气体被叶片附面层吸收，加之转子2的气动负荷重，附面层更易分离，从图中可以看到转子2的尾迹损失明显高于转子1；转子1的尾迹段在流经转子2之后并未完全耗散，在出口导叶通道内仍然能够看到转子1与转子2的尾迹交替向下游传播，对出口导叶产生周期性影响，使得出口导叶的进口气流角在一个周期内脉动量特别大，如图3所示，波动过程包含两个波峰，由于转子2尾迹亏损严重，对应大波峰是转子2尾迹扫掠造成的下游进口气流角波动幅度，小波峰则是部分耗散的转子1尾迹碎片周期性扫掠引起的气流角变化。另外，转子2尾迹在出口导叶通道内每隔3个叶片通道复现一次周期性变化。

![](images/11725f4e700d51ed0c18d32a9867abb72d44c1e6fab6d3037a0cc341576bb6ba.jpg)  
图1计算网格示意图  
图2某瞬时 $50 \%$ 叶高熵云图

![](images/2ee2f2761d1dd8bb0f072d573ab8a859e276316227536f76500db1cb33e0a8e0.jpg)  
Fig.1 Computational mesh   
图3出口导叶进口气流角分布Fig.3 Inlet flow angle of OGV

图4和图5分别给出了 $10 \%$ 和 $90 \%$ 叶高处非定常流场，在对转压气机转子叶片叶型设计中，考虑到加功能力和叶片强度，叶型厚度沿着展向逐渐变薄，叶尖处甚至局部达到超音，相比叶根处叶表附面层比较厚；另外，由于两排转子叶根处的轴向间隙比较小，上游尾迹并未得到充分发展就进入了下游转子通道；转子1尾迹段被转子2中的附面层吸收耗散比较大；另外端壁附面层的粘滞作用使得进、出口导叶尾迹损失略微明显，通道内的熵损失略微大于 $50 \%$ 叶高处。

![](images/3ad87218774961190d5ec1eb6224bf3d7e514e41e9267ff59b292f3441a5987b.jpg)  
Fig.2 Entropy contour at $50 \%$ span   
图4某瞬时 $10 \%$ 叶高熵云图  
Fig.4 Entropy contour at $10 \%$ span

图5中 $90 \%$ 叶高处的流场明显不同于其他叶高，由于间隙泄漏流的存在，两排转子尾缘处靠近压力面侧的损失均比较高，尤其是转子2通道内间隙泄漏流占据了通道靠近压力面侧，上游转子的尾迹段集中在通道靠近吸力面侧，间隙泄漏流和尾迹的双重影响加重了转子2叶顶区域尾缘处的损失；对应下游出口导叶通道内的流动损失相比其他叶高也明显增加。

![](images/0a7b55b910d28e62e351ec11c064133c0b158e97ffc381c3f2b74e619b8fcb72.jpg)  
图5某瞬时 $90 \%$ 叶高熵云图Fig.5 Entropy contour at $90 \%$ span

# 3.2各个叶排交界面上的非定常性分析

图6给出了各叶片排之间交界面上的流量波动情况，波动幅值最大的是两排转子之间的交界面（ROT1-ROT2Interface），其次是第二排转子和出口导叶之间的交界面（ROT2-OGVInterface)，进口导叶与第一排转子之间的交界面（IGV-ROT1Interface）上流量波动幅值最小，进一步证实了两排转子之间动/动干涉效应最强，进口导叶与第一排转子之间的静/动干涉的强度最弱，分析主要原因是：在ROT1-ROT2Interface，由于两排反向旋转的转子叶排之间缺少静子叶排对气流的梳理，上游尾迹和下游势反冲效应的影响并存，使得级间的非定常性特别强；对于IGV-ROT1Interface，进口导叶不对气流产生预旋，相应其尾迹对下游的影响很小，而下游转子的势反冲效应是主要的影响因素，因而流量波动情况始终呈现出单波峰形式；由于转子2的气动负荷最大，并且转子2与出口导叶叶排间的轴向间隙特别小，ROT2-OGVInterface 受到的影响比较大，上游两排尾迹的交替扫掠，使得一个叶片经过时间内该交界面上流量变化相对复杂。

对不同交界面上流量波动情况进行FFT变化，如图7所示，通过得到的频谱进一步证实相邻叶排间的影响。对于IGV-ROT1Interface，进口导叶与转子1之间相互扫掠的主频均为1BPF（Blade PassingFrequency，BPF $\mathbf { \dot { \eta } } = \mathbf { \eta }$ 相对转速 $\lvert 6 0 ^ { * }$ 叶片数 $= 2 6 6 6 . 6 7 \mathrm { H z } )$ ，其中2BPF为对应的倍频；两排转子反向旋转，使得相对转速加倍，对应的相互扫掠频率加倍，ROT1-ROT2Interface上流量脉动的主频为2BPF，1BPF为两排转子各自的叶片通过频谱；对于ROT2-OGVInterface，该交界面上流量波动的频率主要集中在1BPF、2BPF，其中转子2的叶片通过频率为1BPF，而出口导叶相对转子2的叶片通过频率为1.5BPF，即上游转子尾迹的影响更大，出口导叶的影响基本可以忽略。

6.5 IGV-ROT1   
6.48 ROT1-ROT2 ROT2-OGV   
6.46 6.4 AA   
6.38   
6.36   
6.34 0 40 80 120 160 Iteration

![](images/25a8ce17f37502bc28f8343ccd2e1b4d9ef4fe857c1d48399f8e247bd3e0c330.jpg)  
图7流量波动频谱分析  
Fig.7FFT analysis of mass flow fluctuation

# 3.3各排转子进口非定常强度分析

进一步分析各叶片排进口处流场的非定常性，下面给出了不同叶片排进口处的脉动强度系数FIC（Fluctuation intensity coefficient）分布情况，其中脉动强度系数的定义为三个方向上的脉动速度的平方和与叶尖线速度平方的比值。

![](images/42261f29df96b67589354b7dbc2dd384cbc8427578fc92bf58ca97e2cc296ca5.jpg)  
图6各叶片排交界面上流量波动情况 Fig.6Mass flow fluctuation at the interface   
图8转子1进口处非定常脉动强度分布  
Fig.8 Unsteady fluctuation intensity at the inlet of ROT1

由图8可知，第一排转子进口流场受到上游导叶尾迹的扫掠呈现周期性变化；由于轮毂设计为逐渐收缩型，根部处受到端壁附面层粘滞作用更强，对应叶根处的脉动强度比较高。当上游尾迹扫掠至转子1前缘处时，部分尾迹被转子1附面层吸收，对应的脉动比较小；当尾迹扫掠至通道中间时，根部处尾迹的脉动略微明显。

![](images/f1242fccb854f0e23a2c0098d69b2ada81d33763eb993f442beab31b6a8959c3.jpg)  
图9转子2进口处非定常脉动强度分布

Fig.9Unsteady fluctuation intensity at the inlet ofROT2

分析第二排转子进口处的脉动情况，如图9所示：上游转子1尾迹在向下游传播的过程中，沿着周向同样存在被下游转子切割、拉伸的过程；一个通道内同时存在两条上游尾迹的周期性扫略，分别标记为A和B；由于转子1沿着叶高方向弯扭比较厉害，使得不同叶高处转子1的尾迹向下游传播的过程中沿着周向存在一定的滞后；转子1尾迹的周期性扫掠是造成转子2进口流场非定常性的根本原因；受上游尾迹的周期性影响，下游转子进口处的脉动强度系数沿着展向周期性的增强；由于叶顶区域同时存在上游尾迹与间隙泄漏流的影响，使得顶部区域的非定常脉动始终比较大，叶顶处的强脉动区域与整个尾迹一起向下游传播。

![](images/fd6a464bf39c61d609bc14207bd4605764c58afdd0a745e5593c2bb612a9a271.jpg)  
图10出口导叶进口处非定常脉动强度分布  
Fig.10Unsteady fluctuation intensity atthe inlet of OGV

对于出口导叶而言，主要受到上游两排转子不同尾迹的交替影响，转子1的尾迹流经转子2的过程中部分被耗散，从图中仍能模糊看到其沿着周向传播过程；相比转子2的尾迹宽度更大，从图中能够非常清晰的看到三个进口导叶进口处两条转子 2尾迹呈现周期性扫掠，之所以在同一时刻两条尾迹扫掠造成的下游导叶进口处的脉动强度略有差异，是因为两条尾迹相对三个出口导叶的位置各异；同样是叶根处的非定常脉动强度比较大。

# 4结论

本文采用非定常数值模拟的方法分析了对转压气机内部非定常流场，研究了对转压气机内转子与转子之间以及转子与导叶之间的非定常干涉效应，主要结论如下：

1）对比各叶排交界面上流量波动情况，两排转子之间的非定常强度最大，即认为两排转子之间的干涉的强度大于转子与导叶之间干涉的强度；  
2）各叶排进口处非定常脉动强度沿着流向逐渐增加，由于出口导叶与上游转子的轴向间隙特别小，使得出口导叶进口处非定常脉动特别剧烈。

# 参考文献

[1] Schimming P, Counter rotating fans—An aircraft propulsion for the future? [J]. Journal of Thermal Science,2003,12(2):   
97-103 [2] Sharma P B,Adekoya A.A review of recent research on counter rotating axial Flow compressor stage [R]. ASME Paper GT-1996-2254 [3]陈云永，对转压气机特性、流场分析及三维优化研究[D], 西北工业大学，2008 Chen Yunyong,Flow field and performance investigation and three-dimension optimization study of contra-rotating compressor [D],Northwestern Polytechnical University,   
2008 [4] Guidotti E,Turner M G. Analysis of unsteady flow in an aspirated counter-rotating compressor using the nonlinear harmonic method [R]. ASME Paper GT-2009- 60285 [5] Meyer R,Knobloch K,Linden J.Hot-wire measurements in a high speed counter rotating turbo fan rig[R].ASME PaperGT2010-22569 [6] 高丽敏，李晓军，冯旭栋等．对转压气机转速比变化对稳 定边界影响的研究[J].推进技术,2012,33(6):881--887 GAO Limin， LI Xiaojun， FENG Xudong， etal. Investigation of influence of rotational speed ratio on stability boundary of counter-rotating compressor [J]. Journal of Propulsion Technology,2012, 33(6): 881-887