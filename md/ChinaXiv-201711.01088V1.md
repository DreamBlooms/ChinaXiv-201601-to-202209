# 基于两个导电滑环实现天窗驱动和状态检测

陈颖为

（中国科学院国家天文台，北京100012)

摘要：目前，可旋转天文圆顶仍被大量使用，工作时圆顶可 $3 6 0 ^ { \circ }$ 旋转，望远镜通过打开的天窗进行观测。国家天文台兴隆观测基地的天窗选用5个导电滑环，但不能检测状态。为了简化天窗的状态检测、驱动系统，并提高其可靠性，利用二极管的单向导通特性设计了一种新型天窗状态检测、驱动电路。该电路只需要两个导电滑环和两个限位开关，即可实现天窗的状态检测和驱动控制。当天窗处于限位状态时，二极管构成的限位电路只允许电流单向导通。当天窗处于中间位置时，则可双向导通。该电路已经在 $8 5 ~ \mathrm { c m }$ 望远镜等多个圆顶的天窗状态检测控制中成功应用。天窗状态检测、控制电路极大简化了测控系统，并可进行故障检测。

关键词：天窗状态检测；导电滑环；晶闸管；场效应管；桥路开关中图分类号：P111.2 文献标识码：A 文章编号：1672-7673(2016)02-0213-06

圆顶是保护天文望远镜并协同其工作的机械装置。工作时圆顶可 $3 6 0 ^ { \circ }$ 旋转，望远镜通过圆顶上打开的天窗进行观测[1]。目前大量使用的传统圆顶，天窗驱动多选用三相交流供电。向可旋转圆顶供电需在周边安装导电滑环，以保证旋转至任何方位均能开启或关闭天窗[2-3]。采用三相交流供电至少需要3个导电滑环，如果实现天窗开启、关闭限位，还需增加导电滑环。随着望远镜远程控制的需要，不仅要驱动控制天窗，还必须采集天窗状态以确认望远镜工作环境是否正常[4-8]。因此，还要增加状态信号传输。传统的驱动方式采集天窗状态需在天窗上增加较多采集元件并增加传输通道。

本文介绍一种新型的电路设计，通过两个导电滑环实现天窗驱动控制，同时采集天窗的开启到位、关闭到位、停止于中间位置、滑环接触故障、天窗正在开启、天窗正在关闭等6种状态。驱动电路不工作时，导电滑环完全不带电。该电路运行以来，不仅降低了天窗控制电路的故障率，而且因电路实现了模块化，使维护变得简单。

# 工作原理与设计方案

交流供电及 天窗驱动及控制电路 5个供电滑环 限位电路

国家天文台兴隆观测基地的望远镜圆顶多选用5个供电滑环实现天窗的驱动、换向和限位。原理框图如图1。

在三相交流电机驱动的电路中，用于驱动的导电滑环不便直接用于天窗状态的检测，须增加状态信号检测通道，或者增加导电滑环，或者采用无线串口通道。无线方式可减少导电滑环至3个，但会对望远镜和终端仪器的运转带来潜在影响。其原理框图如图2。

不论上述哪种方式，三相交流电源至少有一相需向导电滑环持续供电。在调试和检修中存在触电的安全隐患。导电滑环越多，故障率和维护工作量越高。为此研制了仅用两个供电滑环实现驱动、控制天窗并检测天窗状态的直流驱动电路，驱动电路框图如图3。

交流供电或 天窗驱动或3至5个供电滑环控制电路 控制电路天窗状态检测电路导电滑环或无线 天窗状态检测电路

![](images/5896dd585f89ad4254d8be3eabdf79a145b9a8df38fb5ddcac80aab76a6f904f.jpg)  
图3直流供电天窗状态检测框图 Fig.3The schematic diagram of dome slit state detection powered by three phase DC

# 1. 1 天窗的限位与换向驱动

由于天窗开启和关闭运行的频度不高，这里选用有刷直流电机驱动天窗。采用如图4的简单电路实现天窗的限位和换向驱动。

![](images/8d3840805057b176e5f1e30f2699458f902b379f172bfb8e6543d1b3436a8f59.jpg)  
图2三相交流供电检测天窗状态框图 Fig.2The schematic diagram of dome slit state detection powered by three phase AC   
图4限位电路

图4中 $\mathbf { \alpha } _ { a }$ 点和 $b$ 点是供电滑环的引出端。 $\mathrm { S Q } _ { 1 }$ 为天窗开启限位开关， $\mathrm { S Q } _ { 2 }$ 为天窗关闭限位开关。用二极管 $\mathbf { D } _ { 1 }$ 和 $\mathbf { D } _ { 2 }$ 解决了其中一个限位开关动作后反向供电驱动天窗电机的问题。滑环的另一端是不能旋转的滑环供电触头 $\mathbf { \alpha } _ { a }$ ’和 $_ b \cdot$ 。只需改变向供电触头 $\mathbf { \alpha } _ { a }$ ’和 $_ b \cdot$ 的供电极性，就能实现天窗开启或关闭。天窗开启或关闭至限位位置，触动 $\mathrm { S Q } _ { 1 }$ 或 $\mathrm { S Q } _ { 2 }$ ，切断供电，自动停止。向 $\mathbf { \Phi } _ { a } \cdot \mathbf { \Phi } _ { \mathbf { \Phi } _ { \mathbf { \Lambda } } }$ 和 $\mathbf { \nabla } _ { b } \cdot \mathbf { \nabla } _ { \mathbf { \lambda } }$ 供电可选用继电器电路改变供电极性，也可采用晶体三极管构成的桥路开关改变向 $\mathbf { \Omega } _ { a }$ ’和 $\mathbf { \nabla } _ { b } \cdot \mathbf { \nabla } _ { \mathbf { \lambda } }$ 供电的极性。

当采用晶体三极管构成桥路开关，晶体管的控制端需保持电平才能使天窗持续运行。需选用自锁功能按钮开关维持其电平，因此，在改变电机运行方向前需要释放锁定按钮。这种操作显然有些不方便。为了简化操作，选用场效应管和晶闸管相结合的混合桥路开关。如图5。

![](images/c28bf9dd955df0aaa17c0d3d28fa08823bcc43ead08a273ddac47f8418ad0b64.jpg)  
Fig.4The limit circuit   
图5场效应管和晶闸管混合桥路  
Fig.5Field effect transistor and thyristor hybrid circuit

该电路的优点是可以利用晶闸管被触发后能够维持导通的特性。从图5可知，当晶闸管导通时，其阴极电位和控制级电位均接近电源电位 ${ \mathrm { V } } +$ ，若利用该电位维持场效应管的持续导通，即可维持天窗持续运行。当天窗运行至限位位置时，相应的限位开关 $\mathrm { S Q } _ { 1 }$ 或 $\mathrm { S Q } _ { 2 }$ 被断开。桥路开关中的晶闸管也因此失去电流通路，电流为0而不再导通，开关桥路自动关闭。开关桥路可用电脉冲触发启动，也可选用无锁按钮启动，操作相对简便，只需触发晶闸管导通即可维持天窗持续运行，到达限位位置，桥路开关自动关闭。该电路可采用强迫场效应管截止的方式关闭桥路开关，使天窗运行随时停止。

# 1.2天窗状态的检测原理

从天窗限位电路图4可以看出，当天窗关闭至限位位置时，将小电流恒流源的正端加至 $\mathbf { \alpha } _ { a }$ 端，电源的负端加至 $b$ 端，天窗驱动电路中没有电流流过。将恒流源的极性反过来，天窗驱动电路有电流流过。如果天窗开启至限位位置时，则加电时出现电流的方向正好相反。根据这一现象，可根据电流产生的方向判断天窗的状态。即：当电流只能从 $\mathbf { \alpha } _ { a }$ 流向 $b$ 时，天窗为关闭状态；相反，为开启状态。当$\boldsymbol { a }$ 至 $b$ 和 $b$ 至 $\mathbf { \Omega } _ { a }$ 均有电流流过时，天窗停在中间位置。若 $\mathbf { \Omega } _ { a }$ 至 $b$ 和 $b$ 至 $\mathbf { \Omega } _ { a }$ 均没有电流流过时，则表明供电电路存在故障，很可能是供电滑环触头接触不良。

# 1.3 应用电路举例

混合桥路应用电路如图6，桥路开关的控制端可由计算机输出的开关量直接控制C天窗开、C天窗关、C天窗停控制端，也可用无锁按钮开关 SB1、SB2、SB3触发。由计算机控制的端口选用光耦作隔离。其中T6、T8为桥路开关的互锁电路。确保当T3、T7导通时，T2、T9 可靠关闭。也确保T2、T9 导通时，T3、T7可靠关闭。该桥路开关模块在国家天文台兴隆基地的天窗控制电路中得到了良好的应用，运行可靠，故障率低，而且在镜盖驱动电路中也采用该桥路开关模块。在镜盖应用中还采用了单线制的延迟电路，使得两片镜盖能很好地协调工作，而且接线简单。

![](images/1e6d94957a88aa30b4e1b543e1a25afda3f52db274c78bcc3c260f1abb91b8cd.jpg)  
图6场效应晶闸管混合桥路实际应用电路  
Fig.6Practical application of the field effect thyristor hybrid circuit

实现天窗状态检测电路方案之一，如图7。当天窗处于非驱动状态时，供电驱动桥路开关处于关闭状态，向天窗驱动电路提供约 $5 \mathrm { m A }$ 的检测电流。图7中的T7和T8分别构成恒流电路，其恒流值约为 $5 \mathrm { m A }$ 。T9 控制T6导通，T10控制T5导通。若分别在k7和k8端提供相位相反的方波信号，可在 $\mathbf { \Phi } _ { a } \mathbf { \cdot } \mathbf { \Phi } _ { }$ 和 $_ { b } \cdot$ 端获得方向交替的恒流信号。如果某方向的恒流信号能够流过天窗驱动电路，那么串在恒流电路中的光耦U1或U2被驱动，光耦的输出产生脉动信号。若光耦U1和U2均产生脉动信号，说明天窗停止在中间位置。若只是U1产生脉动信号，则说明天窗关闭限位开关SQ2断开，天窗处于关闭状态。若只是U2产生脉动信号，则说明天窗开启限位开关SQ1断开，天窗处于开启状态。如果U1和U2均无信号输出，则说明供电滑环或驱动电路存在故障，如滑环断开或接触不良等。若对U1和U2输出的脉动信号进行平滑滤波，即可获得稳定的0或1状态，根据输出信号的状态就能获得天窗状态。该状态信号可供计算机采集。

![](images/1b28b0dbf461de361298f5d8478789b0a866262031ad52be51a07c7304eab123.jpg)  
Fig.7The circuit schematic diagram of dome slit state detection

图7中检测电路为一个恒流桥路开关，该桥路开关与驱动桥路开关并联，恒流管选用耐压较高的小功率管，以抵抗电机停止瞬间产生的反峰电压的冲击。由于恒流桥路设计电流值仅为 $5 ~ \mathrm { m A }$ ，即使驱动桥路工作期间，恒流桥路也不会影响驱动电路。R7和R8的限流作用可保护T5、T6不被损坏。在实际应用中，检测电路的电源电压为驱动电路的一半或更低。在驱动电路不工作时，out1端无输出。当驱动电路工作时，out1端有电平输出。利用out1端的电平控制恒流桥路。天窗驱动运行期间，

out1端输出高电压，利用电压控制恒流桥路使之处于关闭状态，从而实现两个并联桥路分时工作。

0055 湘 司 0 0 即 DONP0

在无需实时监控天窗状态时，可在需要采集天窗状态时激励恒流桥路工作。在激励的同时，在光耦的输出端采集天窗状态。如果需要采集天窗正在运行的状态，只需分别在D7和D8串接光电耦合器的二极管，在该光耦的输出端即可分别检测到天窗是在开启运行中还是关闭运行中。图8为天窗状态检测模块图片。该模块应用于兴隆观测基地 $8 0 ~ \mathrm { c m }$ 望远镜的天窗状态检测和控制，如图9。表1列出改造前后的性能对比。

![](images/6171e0203bcd9963dc664b4e6d571404bcaaa52f1d669765838d38a2e784e677.jpg)  
图7天窗状态检测电路原理图  
图8天窗状态检测模块  
Fig.8The circuit board of dome slit state detection   
图9使用中的天文望远镜圆顶Fig.9The dome in working

表1改造前后的性能对比  
Table 1 Performance comparison before and after the reform   

<html><body><table><tr><td>性能</td><td>改造前的三相驱动</td><td>改造后的直流驱动</td><td>改造后获益</td></tr><tr><td>供电滑环数量</td><td>5个</td><td>2个</td><td>减少维护</td></tr><tr><td>供电滑环接触不良导致缺 相损坏电机</td><td>存在风险</td><td>不存在</td><td>远程控制无缺相烧毁电机危险</td></tr><tr><td>供电控制电路</td><td>二次接线控制</td><td>无触点换向模块</td><td>维护简单</td></tr><tr><td>接受计算机控制</td><td>须增加与计算机 控制衔接电路</td><td>可直接接受计算机输 出的电平或触点信号</td><td>与计算机接口方便</td></tr><tr><td>检测天窗状态在天窗上增 加检测元件</td><td>须增加</td><td>无须</td><td>减少天窗状态传感开关使用</td></tr><tr><td>自动检测导电滑环接触不良</td><td>不便检测</td><td>方便检测</td><td>故障自动检测</td></tr><tr><td>增加检测天窗状态信息传 输通道</td><td>须增加</td><td>无须</td><td>驱动滑环和检测滑环可复用</td></tr></table></body></html>

目前有些应用中，为降低成本省去了旋转圆顶的齿盘驱动结构。将驱动电机安装在旋转圆顶上直接驱动轮子在环形轨道上运动。天窗和圆顶的驱动均由可编程逻辑控制器（Programmable LogicController，PLC)控制，可编程逻辑控制器通过无线串口实现与计算机的通讯。本文介绍的基于两根电缆控制和检测天窗状态的原理也可在可编程逻辑控制器上完成。直接用可编程逻辑控制器完成天窗的驱动控制和天窗状态的动态检测。不用增设天窗状态检测元件，直接检测限位开关状态。该方案不仅减少了检测元件的使用，而且也简化了与天窗电路的连线，提高电路的可靠性。由于动态检测较频繁使用输出开关模块，故须将可编程逻辑控制器的输出模块选用晶体管类型，以适应较频繁的开关量输出。

# 2 结论

本文介绍的驱动和检测方法实现了在旋转圆顶上安装最少的导电滑环、最简单的天窗换向、限位电路实现天窗的驱动控制和状态检测。天窗的驱动控制和状态检测均复用两个导电滑环，无须在天窗上另外安装状态检测元件。在实际应用中降低了天窗控制电路的故障率，由于使用了模块化电路使维护工作变得简单。

具有自锁功能的桥路开关模块在望远镜镜盖控制中也得到了良好应用。可广泛应用于其他开启、关闭限位或两端行程限位的场合。可提高电路的可靠性，同时减少电路的连接导线。在需要导电滑环供电的场合，该电路无需在驱动限位端加装状态的检测元件，也无须增加状态信号的传输通道即可实现状态检测。

# 参考文献：

[1] 姚正秋，周放.近代天文圆顶发展概况［J].天文学进展，2001，21(3)：202-218.Yao Zhengqiu， Zhou Fang. Progress in modern astronomical enclosure [J]. Progress in Astronomy,2001，21(3):202-218.  
[2] 毛同生，蒋世仰.2.16米反射望远镜圆顶室［J].天文学报，1992，33(2)：220-228.Mao Tongsheng，Jiang Shiyang. The dome of the 2.16 metre reflecting telescope ［J].ActaAstronomica Sinica，1992，33(2）：220-228.  
[3] 毛同生，蒋世仰. $2 . 1 6 \mathrm { ~ m ~ }$ 天文望远镜圆顶的传动系统［C］/／苏定强.2.16米天文望远镜工程文集．北京：中国科学技术出版社，2001：268-272.  
[4] 高杰，肖宏玲，姜晓军．一种基于AS-I总线的圆顶随动系统［J].天文研究与技术——国家天文台台刊，2004，1(3)：196-202.Gao Jie，Xiao Hongling，Jiang Xiaojun.An astrodome synchronization system based on AS-Ifieldbus ［J].Astronomical Research & Technology———Publications of National AstronomicalObservatories of China，2004，1（3）：196-202.  
[5] 陆栋宁，黄垒，陈颖为，等. $8 5 ~ \mathrm { c m }$ 天文望远镜圆顶和天窗自动化系统研制［J].天文研究与技术——国家天文台台刊，2008，5(4)：386-391.Lu Dongning，Huang Lei，Chen Yingwei，et al.Research and development of the dome slitcontrol system for the $8 5 \mathrm { c m }$ reflector of NOAC-BNU [J]. Astronomical Research & Technology-Publications of National Astronomical Observatories of China，2008，5(4）:386-391.  
[6] 周吉光，李自力，王毕.云南天文台 ${ \mathrm { ~ 1 ~ m ~ } }$ RCC望远镜电气系统的改造［J］.云南天文台台刊，2001(2)：42-47.Zhou Jiguang，Li Zili，Wang Bi. The electronic reform of the 1-m RCC telescope in YunnanObservatory [J].Publications of the Yunnan Observatory，20O1(2）：42-47.  
[7] 祝杰，曹凯，郑义劲.1. $5 6 \mathrm { ~ m ~ }$ 望远镜天文圆顶电控的改造［J]．中国科学院上海天文台年刊，2009(30):79-86.Zhu Jie，Cao Kai，Zheng Yijin.Realization of $1 . 5 6 \mathrm { m }$ telescope dome electric control systemreformation [J]. Annals of Shanghai Astronomical Observatory Chinese Academy of Sciences,2009(30): 79-86.  
[8] 黄垒，魏建彦，姜晓军，等.基于PMAC的天文望远镜控制系统研究及应用［J].天文研究与技术，2015，12(1)：44-53.Huang Lei，Wei Jianyan，Jiang Xiaojun，et al. A study of a PMAC-based astronomical-telescopecontrol system and its application [J]. Astronomical Research & Technology，2015，12(1） : 44-53.

# Achieving Dome Slit Driving and Status Detection with Two Conductive Rings

Chen Yingwei （NationalAstronomicalObservatories，Chinese AcademyofSciences，Beijing1ol2，China，Email：chenyingwei@bao.ac.cn）

Abstract:At present，rotating domes with slit are still widely used in astronomical observations.They could rotate for 360 degrees and the telescope observes stars through the dome slit.In Xinglong Observatory of National Astronomical Observatories，some telescopes use five conductive rings to control the dome slit，but the statecannot be detected.In order to simplifythe detectionand control system and improve thereliabilityof the dome slit，a new type of dome slit state detection and driving circuit is proposed.This circuit only makes use of two conductive rings and two limit switches with diodes to realize the dome slit state detection and driving control.When the dome slitis inthe limit state,the detection electriccurrent isonlyable to transfer in one direction.And when the dome slit is in the middle position,itcould transferin both directions.The circuit has been successfully applied in several dome slits in Xinglong Observatory，for example，the $8 5 \mathrm { c m }$ reflecting telescope.The test and practical use show that the circuit could be wellused in the state detection and driving control process；it greatly simplifies the system；besides，it could also serve the purpose offailure detection. Kev words. Slit ctate detertin. Conductive rino. Thvrictor. Field affert traneictor. Rridoe cwitch