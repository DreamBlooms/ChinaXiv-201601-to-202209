# 真空断路器触头电磨损在线检测系统研究

胡秋生贺家敏²张鑫² 范兴明2（1.无锡市锡山湖光电器有限公司 无锡2141352.桂林电子科技大学电气工程及其自动化系桂林541004）

![](images/f7b2a1f52e1fa9cd2f5d3728c8a34bcee9bcef94de21845071579fb2fa93ee9d.jpg)

胡秋生男1969年生，工程师，主要研究方向为智能化电器和高压开关电器设计与研发。

摘要：智能电网技术的发展给高压开关设备智能化提出了新的要求和挑战。本文依据高压开关智能化要求，自监测、自诊断和自控制能力，设计真空断路器智能化过程中触头系统电磨损在线监测装置。该装置触头系统磨损量计算采用改进的开断电流累计加权方法，其中权值的选择和磨损总量的计算依据电寿命曲线采用最小二乘法拟合得到，该法具有通用性，可应用于不同型号的真空断路器；加权积分系数 $K$ ，采用训练好的LM-BP神经网络，进行动态预测，使 $K$ 值的选择更加符合工程实际；采用燃弧时间感应器对燃弧时间进行采集，且给出燃弧时间感应器的安装位置和采用的屏蔽措施；硬件处理核心采用TMS320F2812微处理芯片，主要负责算法处理、上位机通信和CAN-BUS控制器局域网通信；短路电流采用罗氏线圈进行采集，且设计电流处理电路，并给出2812AD采样校正办法；最后给出触头系统磨损量在线监测软件流程和设计时应注意的关键技术。

关键词：真空断路器 电磨损 在线监测 触头系统 中图分类号：TM561.2

![](images/664b48623a67d65f79a97979610117f80149b7b14585ebfdf2543d9e4917554c.jpg)

贺家敏男 1983年生，工程师，主要从事智能化电器与应用技术研究。

# The On-Line Monitoring Application Study of Vacuum Circuit Breakers Contact System

Hu Qiusheng' He Jiamin² Zhang Xin² Fan Xingming² (1.Wuxi Xishan Huguang Eletricl Apparatus Co., Ltd. Wuxi 214135 China 2.Guilin University of Electric TechnologyGuilin 541004 China)

Abstract: Vacuum circuit breakers (VCBs) are widely used in power systems to control and protect power lines and power equipments under the conditions of normal, overload, short circuit and other faults. Once a VCB is unable to interrupt or make a current as designed, especially for the short circuit current, heavy losses would be brought about to both the power system and the consumers.In order to reduce the number of accidents and prevent possible troubles due to the failures of VCBs,one valid way is to monitor their performance and condition on-line.Based on the understanding and development of condition based maintenance (CBM) of high-voltage circuit breakers, the authors give some general introduction to electrical endurance on-line condition monitor for VCBs,in which the stress put on the non-intrusive method and device for determination of the arcing duration. The principle and configuration for arcing duration detect are emphatically expounded in our research, in which the electromagnetic induction theory is adopted for the arcing initialization and duration detect. The simulation and experimental results of the arcing detect device are provided in detail.The accuracy and stability of the arcing detect device have been demonstrated and it can distinguish co-existing arc signals in three-phase of circuit breakers.In the end,an algorithm for the electrical endurance of vacuum circuit breakers on-line condition monitoring system is proposed, which based on TMS320F2812 one type of DSP281X series produced by texas instruments semiconductor. The universally accepted approach of accumulative breaking current of high voltage circuit breaker contact to diagnose electrical endurance is used in the high-voltage circuit breakers electrical endurance on-line monitor system.

Keywords: Vacuum circuit-breakers, electrical endurance,on-line monitoring,contact system

# 1 引言

断路器在电网中主要起保护和控制作用，其性能直接影响电网的安全和谐运行。真空断路器以其优良的开断性能和对环境无污染的特性，广泛应用于中低压电力系统中，且向高压超高压领域发展并取得了一定的成果[1-2]。目前在高压、超高压领域,${ \mathrm { S F } } _ { 6 }$ 断路器占主导地位，不过因 ${ \mathrm { S F } } _ { 6 }$ 是温室气体,其地球温暖系数达 $\mathrm { C O } _ { 2 }$ 的24900倍，寿命达3200年[1]。据京都议定书决定，要在2030 年全面禁止使用 ${ \mathrm { S F } } _ { 6 }$ 气体[2]，可以预见真空断路器未来将得到更加广泛的应用。

触头系统是真空断路器核心部件，其寿命直接影响真空断路器的整体寿命。特别是随着智能电网和基于可靠性的的电力设备监测的发展，对其进行寿命评估和在线监测就显得非常重要。其评估和在线监测发展经历三个阶段：一、经动导杆上的标志，示以磨损程度。二、经开断电流加权累计进行评估和监测。三、由改进的开断电流加权累计法进行在线监测和预测。阶段一能大致粗糙地估算出磨损程度，很不精确[3]；阶段二没有考虑实际运行时各相之间电流大小，燃弧时间差别等的影响，导致故障相和非故障相误差很大[3]；阶段三考虑了阶段二忽略的条件，能够工程应用于触头系统电寿命的评估，不过其需要的各参量确定办法没有系统统一的方法，且确定困难[3-4]。

本文主要对阶段三各参量的确定办法进行系统的研究，采用实验室自制的开断电弧起始时刻探测装置确定燃弧时间，并以研究和实验为基础设计VCB触头系统在线监测装置。

# 2 改进的开断电流加权累计参数确定方法

# 2.1电流指数的选择和磨损总量的计算

由法国电力集团（EDF）和意大利工程指导公司（ENEL）得到的 ${ \mathrm { S F } } _ { 6 }$ 触头损耗等效定律[5-6]为启迪，以文献[7]中得到的VCB电寿命折算式为参考，经大量的数学实验和验证分析，本文基于电寿命曲线采用最小二乘法对改进的开断电流累计加权法中的电流指数和理论磨损总量进行选择和分析。

图1所示为一组典型的电寿命曲线，对其进行数学分析可得图2所示开断电流和开断次数关系的拟合曲线。曲线表示开断电流大小和开断次数的关系，公式为对应的拟合公式。研究结果表明曲线具有一定的光滑度，且额定电流大的断路器在相同的开断电流下具有更高的开断次数。

![](images/61ab050b3d32032e3666717615f746e48af55773643004a37d9434a97349b783.jpg)  
图1VCB允许开断次数和开断电流关系 Fig.1Relationship between breaking times and current of VCB

按照文献[3-4]给出的计算理论磨损总量的方法，可得权值和其对应的函数关系，以图1所示额定电流 $I _ { \mathrm { n } } { = } 1 ~ 6 0 0 \mathrm { A }$ 为例子，则磨损总量 $\varrho _ { \mathrm { g } }$ 和权值的关系

![](images/6b242d3ba3a004baa4c3d7a03c2fc27c850691668f33f300836d9b439c8881d3.jpg)  
图2额定开断短路电流 $I _ { \mathrm { s n } } { = } 2 5 \mathrm { k A }$ 时不同额定电流对应的曲线

$$
\mathscr { Q } _ { \mathrm { g } } = \left( \frac { 2 7 3 . 5 3 } { I } \right) ^ { 1 . 9 3 } I ^ { \alpha }
$$

取一定量的开断电流值代入上式，可得图3所示理论磨损总量 $Q _ { \mathrm { g } }$ 和权值 $\alpha$ 的关系图。分析图3可知，在触头材料、结构和灭弧方式等确定之后，理论磨损总量和权值是唯一的，在图中 $\mathcal { Q } _ { \mathrm { g } } = 5 0 ~ 5 0 0$ ，$\alpha = 1 . 9 3$ 。按照本文方法可计算得文献[4]电寿命曲线理论磨损总量 $Q _ { \mathrm { g } }$ 和权值 $\alpha$ 的关系，如图3所示。在文献[4]中选取 $\alpha = 1 . 9 1$ ， $\mathcal { Q } _ { \mathrm { g } } = 8 7 \ 3 0 0$ 。由图3曲线可知， $\alpha = 1 . 9 1 8$ ， $Q _ { \mathrm { g } } = 8 9 \ 9 7 9$ ，比较分析知 $\Delta \alpha =$ $0 . 4 1 8 \%$ ， $\Delta Q _ { \mathrm { g } } = 3 . 0 7 \%$ 。结果表明本文设计方法是可行的。

![](images/352a3a480a5ee40214990345325ce0c6cba58683259a2252405ab036f66478e6.jpg)  
Fig.2The relationship curve for different rating current of the same rating open and short circuit current $2 5 \mathrm { k A }$   
Fig.3Relationship between $\alpha$ and $Q _ { \mathrm { g } }$ of different breaking currents for $I _ { \mathrm { n } } { = } 1 ~ { 6 0 0 } \mathrm { A }$

# 2.2积分电流系数的特性和选择办法

文献[4]按照电接触理论提出了一种改进的开断电流加权累计方法，给出了积分电流系数 $K$ 值的计算方法，其 $K$ 值计算方法基于电寿命曲线按照理想开断进行评估。计算的过程中依据燃弧时间在燃弧区间分布均匀，而实际开断时燃弧时间存在三相不均匀性，这样计算出的 $K$ 值就偏于安全[4]。笔者在文献[4]研究计算 $K$ 值的基础上，考虑燃弧时间区别和分断次数的影响，分析 $K$ 值的分布特性并对其进行动态分析。

经理论计算和实验验证可得图4所示 $K$ 值分布规律图，图中曲线表示不同开断电流时首开相燃弧时间和 $K$ 值的变化关系， $t _ { \mathrm { m i n } }$ 表示最短燃弧时间， $i$ 表示开断次数， $N$ 表示允许的开断次数。A点表示取平均燃弧时间时对应的 $K$ 值，这与文献[4]选取的结果一致。研究可知 $K$ 值在触头材料和结构确定之后是一个随三相开断电流、三相燃弧时间和三相开断次数动态变化的物理量，且其变化规律形成一个包络带，不能应用常规数值方程对其进行预测和确定。故引入LM-BP神经网络算法，依据实际开断过程汇总燃弧时间的变化对积分电流系数 $K$ 进行动态预测和分析，具体构建神经网络模型的过程笔者另有深入的分析和讨论，在此不再赘述。

![](images/c849bbb88d272ebf38badc7ff25448dc56d8e60ed42dbecbddfb8a274b408f6f.jpg)  
图3额定电流1600A时总磨损量、 $\alpha$ 和不同开断电流关系曲线  
图4电流为 $I$ ， $K$ 和首开相时间关系 Fig.4Relationship between $K$ and first breaking pole arcing duration of different breaking currents

# 3燃弧时间起始时刻探测装置设计和仿真

应用改进的开断电流加权累计方法对触头剩余寿命进行评估，除了要确定上述关键参数之外，还需要确定燃弧时间 $t _ { \mathrm { a r c } }$ 。熄弧时间可以依据分断电流波形确定，起弧时间由设计的探测装置确定。起弧时间探测装置设计原理基于真空断路器在开断短路电流时触头间将发生电弧，会在空间产生较强的电磁辐射信号，依据电磁信号变化特性确定燃弧起始时刻。具体的设计结构图和屏蔽措施如图5所示。图中，1起绝缘支撑的作用。2为电磁屏蔽层，在有两相以上开断断路电流时，屏蔽掉其他相电磁信号对本相电磁信号的干扰，保障每相燃弧时间传感器能够精确采集到相应的燃弧起始时间和燃弧时间。3为感应线圈，用来接收和识别开断过程中的电磁信号。4为感应线圈输出端子I，和BNC金属外壳相连，即接地端输出。5为标准BNC接口输出端子，保障燃弧时间传感器具有通用性和良好的抗干扰性能。6为感应线圈输出端子Ⅱ，燃弧时间信号输出端，后接处理电路和采样电路。7为磁心骨架材料，以提高电感量。8为环氧树脂浇注区域，用于固定感应线圈和保护作用[9]

![](images/1b97c83ad126d436f40abf1ccf0d4187decd50df53e769a9aaff8b9480487b51.jpg)

燃弧时间起始信号经BNC端子输出后，送往后级滤波、多级放大之后送往微处理器进行算法运算。经改进的开断电流加权累计算法计算出每次开断的磨损量。图6所示为探测装置后级处理电路仿真结果，表征探测装置的反应灵敏性和响应时间。

![](images/1854fa82a5a06c495a501820c6af820783505bc9d62d9b967947b9d3764c7370.jpg)  
图5真空断路器燃弧时间探测器结构图和安装位置示意图Fig.5VCB arcing detector structure and installationlocation diagram  
Fig.6Simulation results graphs ofVCB arcing detector

# 4监测装置总体结构图和软件设计

监测装置以三相开断电流、三相断路器燃弧时间感应器的输出及三相开关状态信号为输入，系统控制和算法芯片采用TI公司生产的TMS320F2812，内部集成了16路 $\times 1 2$ 位的ADC，是32位定点数字信号处理器，能够单周期完成 $3 2 \mathrm { b i t } \times 3 2 \mathrm { b i }$ t乘法运算，具有强大数字信号处理能力和控制能力。检测装置系统结构如图7所示，图中CT表示电流互感器，对分断电流进行采集。

![](images/cfe212f78f746ef567f15d0ca949c6121b781081e70a9919158c8cb6f181d1bd.jpg)  
图7VCB 触头系统在线监测装置系统结构图Fig.7VCB online monitoring device systemarchitecture diagrams

燃弧时间探测装置每3个一组，用绝缘支撑置于三相灭弧室附近，检测到三相起弧时刻变化经处理后送至DSP进行处理和计算。 $n$ 路电寿命在线检测装置挂在CAN总线上，实现信息和数据的共享；监测的数据经以太网上传至上位机，实现数据的存储，为改善在线监测方法等提供数据支持。

TMS320F2812电磨损在线监测系统主流程图，如图8所示。系统开始时，先判断电网系统有无分闸信号，有无重合闸信号，没有分断信号时，通过以太网进行数据信息传输，有分断信号时进行信息采集。信息采集分别对三相电流信号、三相燃弧时间信号进行采集和对三相开关次数进行捕获，然后对采集的信息进行处理，送至LM-BP算法进行核心算法处理[10]，动态地依据现场信息计算 $K$ 值，最后调用 $K$ 值、 $\alpha$ 值进行加权累计积分得到监测磨损量 $Q _ { \mathrm { z } }$ ，且和理论磨损总量 $Q _ { \mathrm { g } }$ 比较评估VCB触头系统电寿命。

![](images/6f18cae3876422c81c709b14e2ea73aa40396ad4536587611d1a845c6a3b06ee.jpg)  
图6检波信号后级处理电路和仿真  
图8VCB电寿命在线监测主程序流程图Fig.8VCB online monitoring master flowchart

# 5VCB电寿命监测装置性能试验研究

为了验证在线监测装置特别是设计的燃弧时间探测装置的响应特性，笔者在实验室模拟断路器分断产生的高频电磁信号，经燃弧时间探测装置输出。现场测试结果如图9所示，图9a为探测装置输出波形图，曲线1为探测装置输出波形图，曲线2为感应线圈两端的波形图；图9b中曲线1为探测装置上升跳变过程的局部细化图，表征信号由触发到阶跃跳变的时间，反映探测装置的灵敏度。

![](images/c24b3e60a39f1702a4a0912e948f409d39e817a39cf5ffe42ba5b86445f5e920.jpg)  
图9燃弧时间探测装置模拟实验图  
Fig.9 Simulation experiment charts of acing duration detector device

从图中分析可知，在分断产生高频信号时，探测装置会产生一个脉冲信号，脉冲信号上升跳变的时间为 $4 0 \mu \mathrm { s }$ 左右，这和图6所示的仿真结果一致。与持续几个毫秒到十几个毫秒的燃弧时间相比较，显然能够快速灵敏地检测到燃弧时间起始时刻，且与以往的辅助触点相比，具有较高的精度。

# 6 结论

本文重点研究了真空断路器电寿命曲线特征，采用改进的开断电流累计加权法设计了VCB触头电寿命在线监测系统。研究确立了改进算法中关键参数的选择方法和具体实现。以理论分析为基础，研究设计了真空断路器触头电寿命在线监测系统的实现方法，给出了完善的硬件、软件设计以及核心参数的选择方法，使之形成一个可以实际工程应用的方法。文中着重研究计算电流指数、磨损总量和电流系数的方法，使之具有通用性和简洁性，能够应用于实际工程。基于开断时刻灭弧室周围的电磁场变化，设计了燃弧时间起始时刻探测装置，并给出其设计的工作原理、电磁屏蔽措施。本文研究可为高压真空开关触头电寿命在线监测提供了有益的探索和借鉴。

# 参考文献

[1] 王季梅，刘志远，修士新，等．国内外开发研究 高压真空断路器和向超高压发展的概况[J]．电气 技术，2006，12(6)：5-9. Wang Jimei,Liu Zhiyuan,Xiu Shixin,et al.A survey of the development of high voltage vacuum circuit breaker and ultra high-voltage at home and abroad[J].Electrical Engineering,2006,12(6): 5-9.   
[2] 王季梅．论开发750kV超高压真空断路器的必要 性[J]．电力设备，2004，5(9)：1-5. Wang Jimei. Discussion of the necessity to develop $7 5 0 \mathrm { k V }$ ultra high-voltage vacuum circuit breakers[J]. Electrical Equipment, 2004, 5(9): 1-5.   
[3] 范兴明，邹积岩，陈昌龙，等．基于DSP的真空 断路器状态参数在线监测装置[J]．电力系统自动 化，2005，29(8)：99-103. Fan Xingming, Zou Jiyan, Chen Changlong,et al. A VCB parameters on-line condition monitoring system based on DSP[J].Automation of Electric Power Systems,2005,29(8):99-103.   
[4] 关永刚，黄瑜珑，钱家骊．真空断路器电磨损监 测技术的改进[J]．高压电器，2001，37(4)：1-3. Guan Yonggang,Huang Yulong,Qian Jiali. On-line monitoring of the electrical wear of high voltage circuit breaker using an improvement method[J]. High Voltage Apparatus,2001,37(4): 1-3.   
[5] Pons A,Sabot A,Babusci G.Electrical endurance and reliablity of circuit breakers common experience and practice of two utilities[J]. IEEE Transactions on Power Delivery,1993,8(1):168-174.   
[6] 孙福杰，王章启，秦红三，等．高压断路器触头电 寿命诊断技术[J]．电网技术，1999，23(3)：59-61. Sun Fujie,Wang Zhangqi,Qin Hongsan,et al. Electrical endurance diagnosis of high voltage circuit breaker contacts[J].Power System Technology,1999, 23(3): 59-61.   
[7] 黎斌．断路器电寿命的折算、限值及其在线监测 技术[J]．高压电器，2005，41(6)：428-433. Li Bin.Conversion,limit,and on-line monitoring technology of electrical endurance for circuit breakers[J].High Voltage Apparatus,2005,41(6): 428-433.   
[8] 陈奕钪，鞠昱，李彦林，等．基于TDLAS的 ${ \mathrm { S F } } _ { 6 }$ 断路器湿度在线监测技术的应用研究[J]．电气应 用，2016，35(22)：43-46.   
[9] 范兴明，张鑫，李静，等．断路器燃弧时间感应 器及断路器电寿命在线监测系统[P]．中国专利： G01R31/327，2010-11-17.   
[10] He Jiamin,Fan Xingming,Zhang Xin.The assessment and prediction method for VCB contact endurance research based on LM-BP neural network[C].Proceedings of the 24th International Symposium on Discharges and Electrical Insulation in Vacuum,Braunschweig,Germany,2012,45(7): 481-484.