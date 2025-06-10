# 两种转子结构的永磁无刷直流高速电机转子受力及损耗温度场分析

![](images/5d1926101efb55a864ed63bb1a2936eea8d9b4dd30fcdfe8bed4f1fc3f94c03c.jpg)

王大朋 马田（沈阳工业大学电气工程学院 沈阳 110870)

王大朋男 1976年生，博士，讲师，主要从事高速电机设计分析研究工作。

摘要：电机的设计是一个多重物理场的综合设计。本文设计了一台 $1 0 \mathrm { k W }$ 、$1 0 \ 0 0 0 \mathrm { r / m i n }$ 的永磁无刷直流高速电机，针对表贴式和内嵌式两种转子结构，分别对内嵌式转子和不同护套的表贴式高速无刷直流电机进行了受力分析、损耗分析和温度场分析。在多物理场分析仿真的基础上，得到了满足转子强度、损耗、温升的综合设计结果。分析了无刷直流电动机的损耗及热场的计算过程，研究了两种电机结构的损耗大小和温度场分布。采用本文提出的方法不仅可以精确计算电机内部损耗的大小，而且可以得到电机内部损耗与热场之间的能量交互过程，研究电机的发热问题。通过仿真结果对比，发现表贴式结构发热比较严重。

关键词：高速无刷直流电机不同转子结构 损耗计算温度场分析中图分类号：TM351，TM355

![](images/0222305274c166a03e141c35823ab29cf21f916f648cd132fd00535246d38062.jpg)

马田男1991年生，硕士，主要从事高速电机设计分析研究工作。

# Loss and Temperature Field Analysis of Permanent Magnet Brushless DC High Speed Motor With Two Rotor Structures

Wang DapengMa Tian ( ShenyangUniversity of TechnologyShenyang 110870 China )

Abstract: The design of the motor is a comprehensive design of multiple physical fields.In this paper, $1 0 \mathrm { k W }$ ， $1 0 \ 0 0 0 \mathrm { r / m i n }$ permanent magnet brushless DC high-speed motor is designed.For surface mount radial excitation and embedded two rotor structure respectively,the high speed brushless DC motor is subjected to force analysis,loss analysis and temperature field analysis on the embedded rotor and different jacket surface. On the basis of multi-physics analysis and simulation, the comprehensive design results of rotor strength,loss and temperature rise are obtained. The calculation of the electromagnetic field and the thermal field of the brushless DC motor are analyzed. The loss and heat field distribution of the two kinds of motor structures are studied. This method not only can accurately calculate the internal loss of the motor, but also can get the internal loss of the motor thermal field between the energy interaction process and the study of the motor heating problem.Through the comparison of the simulation results, it is found that the heat dissipation of the surface structure is serious,and the embedded structure has magnetic flux leakage at the end of the magnet, which causes the current waveform to cause distortion.

Keywords: High speed brushless DC motor, different rotor structure,loss calculation, temperature field analysis

# 1 引言

# 表1电机设计基本参数

无刷直流电动机具有效率高、体积小、可靠性高、特性好、调速方便、结构简单等优点，已广泛应用于航空、航天、航海等领域以及各民用工业领域。无刷直流电动机转子结构形式十分灵活，根据永磁体在转子中放置的位置，可以分为内嵌式和表贴式。不同分法又可以相互组合，因此可以构成许多各有特色的转子磁路结构[1]。无刷直流电动机的磁场分布复杂，而且永磁体随温度的升高将出现退磁现象，直接影响磁场的大小及分布，并使得电机的性能产生波动[2。因此，转子磁路结构不同，损耗大小和发热程度对无刷直流电动机的性能、工艺和适用场合有很大影响，这是无刷直流电动机设计的一个重要环节。内嵌式无刷直流电动机相对于表贴式转子结构形式更灵活，设计参数多，是目前国内外研究的热点[3]

# 2 电机结构及基本参数

本文设计了一台内嵌式转子无刷直流电机，一台合金转子护套表贴式转子结构和一台碳纤维护套表贴转子电机。额定电压、额定功率和转速均分别为 $5 0 0 \mathrm { V }$ 、 $1 0 \mathrm { k W }$ 和 $1 0 \ 0 0 0 \mathrm { r / m i n }$ 的4极、三相永磁无刷直流电机初始结构如图1所示，表1列出了电机的设计参数。

![](images/615fe5465019a4e3a3c21efe893a99345a0543792cd0c2dd08976839f6422c39.jpg)  
图1两种转子结构电机仿真模型

# 3 电机分析

# 3.1转子应力的有限元分析

由于本文设计的电机转速为 $1 0 \ 0 0 0 \mathrm { r / m i n }$ ，比一般电机要大，其转子表面的永磁体承受很大的离心力，因此利用有限元法对永磁体转子应力进行了分析。转速为 $1 0 \ 0 0 0 \mathrm { r / m i n }$ 、运行温度为 $7 5 \mathrm { { ^ \circ C } }$ 的三台电机2D转子应力分布如图2所示。

由图2可知，当转速为 $1 0 \ 0 0 0 \mathrm { r / m i n }$ ，运行温度较高 ( $7 5 \mathrm { ^ \circ C }$ ）时，转子等效应力分别为 $3 4 \mathrm { M P a }$ 、1.446MPa和 $0 . 7 5 0 \ 0 6 \mathrm { M P a }$ ，符合对电机转子的机械强度要求。

Tab.1 Basic parameters of motor design   

<html><body><table><tr><td>参数</td><td>内嵌式</td><td>表贴式</td></tr><tr><td>额定功率/kW</td><td>10</td><td>10</td></tr><tr><td>额定电压/V</td><td>500</td><td>500</td></tr><tr><td>极数</td><td>4</td><td>4</td></tr><tr><td>定子槽数</td><td>12</td><td>12</td></tr><tr><td>轴向长度/mm</td><td>78</td><td>78</td></tr><tr><td>永磁体材料</td><td>NdFeB</td><td>NdFeB</td></tr><tr><td>额定转速/(r/min)</td><td>10 000</td><td>10 00</td></tr><tr><td>额定电流/A</td><td>20</td><td>20</td></tr><tr><td>气隙大小/mm</td><td>1.5</td><td>1.75</td></tr><tr><td>定子外径/mm</td><td>160</td><td>160</td></tr><tr><td>定子内径/mm</td><td>80</td><td>80</td></tr><tr><td>转子外径/mm</td><td>77</td><td>74.5</td></tr><tr><td>转子内径/mm</td><td>25</td><td>25</td></tr></table></body></html>

![](images/2dd1348f06acde88055a2343dac1aa836b0b46f69535e86efe06ab1e9da58eae.jpg)  
Fig.1 Simulation models of two rotor structure motors   
图2电机转子应力分布图  
Fig.2Motor rotor stress distribution diagrams

# 3.2损耗分析

永磁内嵌式无刷直流电机具有高转速、高功率密度、体积小等优势，每单位体积的高功率密度导致的铁心损耗增加将不可避免地引起温度上升[4],因此有效地降低损耗、减少热量损失是永磁内嵌式电机需要解决的关键问题。低速电机铁心损耗可以忽略不计，但在高速电机中，由于高频引起的铁心损耗显著增加[5]，不仅影响永磁内嵌式电动机的效率，同时也增高了电动机本身的温度，因此准确地计算铁心损耗从而控制电机温度，对于提高电动机的效率非常重要[。本文先利用Ansoft分析损耗,得到如图3～图5所示的损耗曲线。

![](images/f6a5117b99fba5fd38f2d5c7906644aa7467788aa3760702ad54acd9551e1be7.jpg)  
(a）内嵌式转子电机定子铁心损耗

![](images/ee2fff3b88111df1ffea716035bbcf31f097ef9a42557ac1de9b6aebfa58b067.jpg)  
(b）内嵌式转子电机转子铁心损耗

![](images/72d2c6ce419b9024a88689aa4c37641541906acad83e871a6ebd7e97ea8b5c82.jpg)  
图3内嵌式转子电机各部分损耗曲线  
Fig.3Loss curves of the embedded rotor motor

本文利用二维有限元法、RMxprt和Ansoft进行电机分析，分别计算得到了三台电机定子的铁心损耗、转子铁心损耗、永磁体涡流损耗和电枢铜耗。由图可知，在额定负载下，内嵌式转子定子铁心损

![](images/e0e199f6dc11907f9552d89fbc01a54968d75e3ebbb16f3a20ed1ae1f5f522e7.jpg)  
(a）碳纤维护套表贴式转子电机定子铁心损耗

![](images/81dd58a97db68e24323cb78589cd109950c0fd75265f38ae6a837a312ab7deb9.jpg)  
(b）碳纤维护套表贴式转子电机转子铁心损耗

![](images/bf9c405949d09b2d28968b43336816d8d65d984cc0ad9faab45f46746480b03d.jpg)  
图4碳纤维护套表贴式转子电机各部分损耗曲线Fig.4Loss curves of the alloy sheathed surface-mountedrotormotor

耗为 $1 8 4 . 1 \mathrm { W }$ ，转子铁心损耗为19.585W，永磁体损耗为 $6 2 . 2 6 5 \mathrm { ~ W ~ }$ ，电枢铜耗为100.694W，总损耗为 $3 6 6 . 6 4 1 \mathrm { W }$ 。合金护套表贴式转子电机定子铁心损耗为 $1 3 7 . 3 \mathrm { W }$ ，转子铁心损耗为1.7523W，永磁体损耗为84.525W，电枢铜耗为87.3161W，护套损耗为 $4 3 6 . 1 \mathrm { W }$ ，总损耗为746.9934W。碳纤维护套表贴式转子电机定子铁心损耗为 $1 3 3 . 4 \mathrm { W }$ ，转子铁心损耗为1.9032W，永磁体损耗为62.265W，电枢铜耗为87.3161W，护套损耗为271.2W，总损耗为556.0843W。可知在额定负载下，内嵌式电机损耗最小，表贴式电机损耗比较大，其中合金护套电机损耗最大。

![](images/de48d74ec2343eb455b506509d8a541bab108e9a7c6375d6a54b9f35420f3349.jpg)  
(a）合金护套表贴式转子电机定子铁心损耗

![](images/20193c63bdf492b9c08a8e16cecd0e96dc08af9b00505fbdc341e818403a0724.jpg)  
(b）合金护套表贴式转子电机转子铁心损耗

![](images/186c2c1b20d168b64eccf63a5451475259a8705cd568486be40d9e57fff27c3b.jpg)  
(c）合金护套表贴式转子电机护套损耗

![](images/3e5acaa230a4396869cee552139cd3c6567a8d093033c2b28dbb8b2dedb0c3b9.jpg)

# 4 温度场分析

高速电机体积小，功率密度大，同时单位体积损耗也大。电机在工作时发热严重，散热也比较困难，因此温升较高。而永磁体材料的性能受温度影响较大，温升较高可能会导致永磁体发生不可逆退磁进而损坏电机[7]，因此对温升进行分析十分重要。

无刷直流电动机内部电磁场分布非常复杂，各部分发热情况不均匀，散热条件也相差悬殊，热源之间又存在一定的热交换，所以该类电机内部的热场分析存在一定困难。电机的热量是由电机各个部分的损耗引起的，这些热量一般通过热传导作用，由发热体的内部传递到发热体表面，然后再通过热对流和热辐射的形式将热量发散到周围介质中[8]。

根据电机内的流体流动和传热情况给出了温度场相应的边界条件，即

（1）风路采用流－固耦合，给定相应入口温度$2 5 \mathrm { { ^ \circ C } }$ 、风速 $1 5 \mathrm { m / s }$ 的风冷和出口压力。

(2）对定子槽内部进行了等效绝缘处理。

(3）电机定子、绕组、护套、永磁体加载相应的温度，作为电机热源。

(4）电机转子部分设定转速，模拟实际电机旋转。

两种转子结构电机求解域模型如图6所示。

![](images/c102002e54c80bb04684bf553363934bd3fb48eeba8a5b4644d6be8240b46b85.jpg)  
图6两种转子结构电机求解域模型  
Fig.6The solution domain models of two rotor structure motor

通过ANSYS软件下的CFX模块对电机的温度场进行分析，得到稳态下电机的整体温度分布情况，如图7所示。图 $\mathrm { 7 a } \sim \mathrm { 7 c }$ 分别为内嵌式转子电机温度场分布、表贴式转子合金护套电机温度场分布和表贴式转子碳纤维护套温度场分布。电机沿轴向和径向方向的温度分布如图8、图9所示，轴向位置0处表示电机轴向中间处，径向位置的温度分布本文取自轴向转轴中间处。

![](images/666d88f6e31f40828e98a1275ad42cb9d5424e9297c38d91d104a1f2a0043b34.jpg)  
图5合金护套表贴式转子结构电机各部分损耗曲线Fig.5Loss curves of carbon fiber sheathed surface-mountedrotormotor  
(a）内嵌式转子电机温度场分布

![](images/97688baf1e7ac8e953c4e3a6e18bc5f663460271c3689d30b0ac1e9859bdfce9.jpg)

![](images/77f6acc790d85dc9c683814bef651f4ff71d5c3de5e16d6d11d5a5fa728e97bd.jpg)  
图7电机温度场分布  
(b）合金护套电机径向温度分布

![](images/cc092beb7717ac36d5fd081b46db782e13693ea4a580f68a29a46895f86ed214.jpg)  
图8电机径向温度分布

![](images/5c729c71fd7ecf033a4a6ebc06c7015deada105ea40246c0d37f7f7c1767cbab.jpg)  
Fig.7Temperature field distribution of motor   
图9电机轴向温度分布  
Fig.9Axial temperature distribution of motor

本文采用的NdFeB永磁体材料所能承受的最高温度为 $1 8 0 ^ { \circ } \mathrm { C }$ ，当永磁体温度高于该温度时，永磁体会发生不可逆退磁，严重影响了电机的可靠运行。本文采用定转子风冷，进口端温度为 $2 5 \mathrm { { ^ \circ C } }$ 、风速为

$1 5 \mathrm { m / s }$ 、压强大约为 $3 0 0 \mathrm { { P a } }$ 的风冷，以使永磁体温度保持在安全范围内。

表2为三台电机的各部件最高温度。从表中可以看出，三台电机在相同功率转速下，内嵌式转子无刷直流电机温度比表贴式温度低，表贴式合金护套转子比碳纤维护套转子温度高。

# 表2三台电机各部件最高热度值

Tab.2Maximum temperature of each part of motor   
(单位：K)   

<html><body><table><tr><td>部件</td><td>内嵌式</td><td>合金护套</td><td>碳纤维护套</td></tr><tr><td>转轴</td><td>315</td><td>579</td><td>538</td></tr><tr><td>转子铁心</td><td>315</td><td>579</td><td>538</td></tr><tr><td>永磁体</td><td>254</td><td>579</td><td>538</td></tr><tr><td>护套</td><td></td><td>579</td><td>538</td></tr><tr><td>绕组</td><td>217</td><td>398</td><td>398</td></tr><tr><td>定子铁心</td><td>247</td><td>416</td><td>402</td></tr><tr><td>机壳</td><td>231</td><td>389</td><td>385</td></tr></table></body></html>

# 5 结论

本文设计了一台 $1 0 \mathrm { k W }$ 、 $1 0 \ 0 0 0 \mathrm { r / m i n }$ 的永磁高速直流电机，并分别设计了内嵌式和表贴式两种不同转子结构，针对表贴式转子结构分析了合金护套和碳纤维护套。通过Ansoft有限元分析，分别得到三台电机各部件损耗曲线参数，通过ANSYS静力分析可知该设计符合电机设计。利用ANSYS软件下的CFX模块建立了两种转子结构的电机三维求解域模型，根据电机内流体流动和传热情况给出了温度场计算相应的边界条件，计算出三台电机的温度场分布。

通过图表参数对比可知在该参数设计下，内嵌式永磁同步无刷直流高速电机损耗更小，表贴式损耗较大，发热较大，容易引起扫膛，嵌入式结构损耗较小，不存在局部发热现象，但在磁钢端部存在明显漏磁，引起环流使电流波形发生畸变[9]。两种转子结构各有利，设计中应根据电机的应用背景及技术指标进行选用。

# 参考文献

[1] Wang Fengxiang.Study on design feature and related technology of high speed electrical machines[J].

Journal of Shenyang University of Technology, 2006, 28(3): 258-263.   
[2] Gerada D, Mebarki A,Brown N L, et al. Highspeed electrical machines: technologies, trends,and developments[J]. IEEE Transactions on Industrial Electronics,2014, 61(6): 2946-2959.   
[3] Kolondzovski Z,Arkkio A,Larjola J, et al. Power limits of high-speed permanent-magnet electrical machines for compressor applications[J]. IEEE Transactions on Energy Conversion, 2011,26(1): 73-82.   
[4] Wang Jiqiang, Wang Fengxiang, Kong Xiaoguang. Design and analysis of electromagnetic properties for high speed PM generator[J]. Proceedings of the CSEE,2008,28(20): 105-110.   
[5] 赵南南，刘卫国．无刷直流电动机电磁场-热场耦 合分析[J]．微特电机，2009，37(3)：9-11. Zhao Nannan,Liu Weiguo.Electromagnetic fieldthermal field coupling analysis of brushless DC motor[J]. Small & Special Electrical Machines, 2009, 37(3): 9-11.   
[6] Zhu Z Q, $\Nu \tt { g } \mathrm { ~ K ~ }$ ， Schofield N, et al. Improved analytical modeling of rotor eddy current loss in brushless machines equipped with surface-mounted permanent magnets[J]. IEE Proceedings on Electric Power Applications,2004,151(6): 641-650.   
[7] 余莉，胡虔生，易龙芳，等．永磁内嵌式无刷直 流电机铁耗的分析和计算[J]．电机与控制应用, 2007，34(4): 11-14. Yu Li, Hu Yusheng, Yi Longfang, et al. Analysis and calculation of iron loss of permanent magnet embedded brushless DC motor[J]. Motor and Control Applications, 2007,34(4): 11-14.   
[8] Evans S A.Novel rotor design for interior permanent magnet brushless machines: initial investigation[C]. International Conference on Electrical Machines, 2008: 1-6.   
[9] Han-WookCho, Seok-Myeong Jang, Sang-Kyu Choi. A design approach to reduce rotor losses in high-speed permanent magnet machine for turbocompressor[J]. IEEE Transactions on Magnetics, 2006, 42(10): 3521-3523.