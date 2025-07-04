# 基于FPGA步进电机细分控制系统

王天放1²，贾 楠」，彭如意1²，吕建工」，彭吉龙‘，付利平1(1.中国科学院空间科学与应用研究中心北京100190；2.中国科学院大学北京100049)

摘要：现代卫星载荷的探测功能日益强大，电机等活动部件在卫星载荷上的应用也日渐广泛。星上电机寿命和可靠性是制约卫星长期在轨正常工作的主要因素之一，因此星上电机系统设计在满足使用要求的同时，还需充分考虑到寿命和可靠性要求。本文设计了一种基于FPGA的二相混合式步进电机控制系统，采用细分控制方法，提高控制精度,抑制低频振动。除此之外设计加速过程,保证电机可靠启动;采用大电流停止，保证电机迅速停止;静止时使用小电流保持。通过系统测试证明，该系统具有功耗低、起停稳定等优点。

关键词：步进电机；细分控制；FPGA；PWM

中图分类号：TM384；TN709；TN492 文献标识码：A 文章编号:1674-6236(2016)01-0121-03

# Stepper motor subdivision control system based on FPGA

WANG Tian-fang1,2，JIA Nan1,PENG Ru-yi1,2,LV Jian-gong1,PENG Ji-long1，FULi-pingl (1.National Space Science Center,Chinese Academy of Sciences，Beijing 1Oo19o,China; 2.University ofChinese AcademyofSciences，Beijing1OoO49,China)

Abstract: Thecapabilityof the modern payloadsonsatelite is geting strongerand stronger，and the motorhasbeen used widely.Thelifeandreliabilityofthemotorequippedonsatelite wouldbethe maincharacters thatrestrictlong-time workof the satellies.So thedesignofmotorsystemonsatelltes shouldbenotonlysatisfiedwiththeapplicationrequirements，but alsotherequirementsoflifeandreliabilityshouldbefulltakenintoaccountsimultaneously.Inthispaper,a two-phase hybrd stepper motorcontrol system basedonFPGA is introduced.Inorderto improve control accuracyandsuppresslow-frequency vibration,thesystem wasdesignedbasedonsubdivision control methodandanacceleration processwas designedto nsure that motor started properly.Large current was used to stop the motorquickly andsmall current was used to keep the motor motionless.The testresults showed that this system has the advantages of low-power consumption，starting and stopping steadily.

Key words:stepping motor；subdivision control；FPGA；PWM DOI:10.14022/j.cnki.dzsjgc.2016.01.035

随着现代卫星载荷探测功能日益增强，对电机等活动部件的寿命与可靠性提出更高要求。步进电机自身具有体积小、质量轻、易于控制、误差不积累、可靠性高等优点，适合充当星上载荷活动部件。本文中使用一款两相混合式步进电机，该电机步距角为 $1 . 8 ^ { \circ }$ 。为进一步提高电机综合性能，通常使用一些控制方法控制电机运行，步进电机细分控制是一种上世纪70年代发展起来的电机控制技术，可显著改善步进电机综合性能，提高控制精度，抑制低频振荡，充分发挥步进电机作为优良开环组件的优势。

文中设计了一种基于FPGA的二相混合式步进电机控制系统，使用LMD18200作为桥式驱动芯片，SG1525作为脉宽调制芯片，采用8细分方式。测试证明该系统具有功耗低、起停稳定等优点。

# 1细分控制理论简介

细分步进驱动是将全步进驱动时的步距角的各相的电流以阶梯状 $n$ 步逐渐增加[，由于电磁力矩与电流相关，通过减小绕组电流突变，就能减小电磁力矩突变。细分技术使步进电机步距细分，分辨率提高，振动、噪声和转矩波动问题得到很大改善，运转更为平稳[2。获取细分阶梯波形一般采用电流矢量横幅均匀旋转法，对于二相混合型步进电机，为得到细分控制效果，控制两相绕组电流大小，使其矢量叠加后幅值基本保持恒定。

本文采用二相步进电机八细分控制，即在整步运行的每两个阶段中插入7个中间状态，从而将一个步距角分成8步[3]。具体表现为两相绕组中通过相差 $9 0 ^ { \circ }$ 相位的两相正弦波形的绕组电流。参考电平与方向信号如图1所示，其中参考应，二者结合，就能得到两相相位相差 $9 0 ^ { \circ }$ 的正弦波形。对于7个中间状态参考电平的选择，应满足正弦函数，保证电流矢量叠加后幅值恒定。

![](images/73aeb8716010500940e9ba2eae43a53379167ddea96da476ba80c5f7e509bb59.jpg)  
图1两相参考电平与方向信号

# 2步进电机驱动电路设计

目前步进电机驱动电路主要采用集成全桥驱动芯片。文中选用的全桥集成驱动芯片LMD18200，该芯片具备完善的逻辑控制功能和芯片保护功能，工作电压高达55V，峰值输出电流高达6A5]，只需方向信号与PWM(PulseWidthModulation)信号，就可以控制芯片内部DMOS管通断，从而改变电机每相电流大小和方向。

# 2.1 PWM信号发生

PWM是脉冲宽度调制的简称，是一种将占空比变化的数字信号转换成模拟量的技术。步进电机作为感性负载，PWM信号通过控制开关管通断，进而控制步进电机电流连续变化，因此只要提供占空比变化的PWM信号，就能实现电流细分变化。具体情况见图2，当PWM信号处于 $t _ { \mathrm { o n } }$ 时，开关管导通，电流持续上升；当信号处于 $t _ { \mathrm { o f f } }$ 时，开关管关闭，电流下降。当固定占空比的PWM信号持续较长时间，电流在某一固定值附近波动。

![](images/e3fdb22e145463c0d3cad6fd1e174737124e869772cd036375133c39309859c4.jpg)  
Fig.1The reference levels and signals of direction of two phase:   
图2PWM信号与电流关系 Fig.2The relationship between PWM signal and current   
图4SG1525输入电压与占空比关系 Fig.4The relationship between input voltage and duty ratio of SG1525

PWM信号产生方法主要有软件和硬件两种，两种方法各有优缺点。软件产生PWM信号可采用SPWM法（正弦函数脉宽调制法，此方法也可以通过硬件电路实现），即使用固定频率的三角波形与正弦波形的交点作为PWM信号的导通点或截止点。如图3所示，三角波形与阶梯波形较，当三角波形电压高于阶梯波形电压时，输出低电平，否则输出高电平，这样得到PWM信号。如果使用细分控制方法，就用细分阶梯波形代替正弦波形。软件直接产生PWM信号，电路较简单，但程序相对复杂，同时也不利于长线传输（长线传输造成波形畸变，占空比不稳定）。

![](images/e6d63fb2f719dd30db6e6686e8b405883a77786d8e779a529cbc91059707b1be.jpg)  
图3SPWM正弦函数脉宽调制法示意图Fig.3Schematic diagramofSPWM

硬件产生PWM信号通常使用集成PWM控制芯片作为波形发生器。该方法虽然需要更多元件，但软件程序简单，适宜长线传输，能更好保证系统可靠性。本文选用SG1525集成脉宽调制控制芯片产生PWM波形，该芯片内含欠压锁定电路、软启动控制电路、PWM锁存器，有过流保护功能，频率可调，同时能限制最大占空比。对于SG1525芯片，电平由正输入端输入，输出引脚与负输入端相连，形成反馈，这样输入电平高低决定了输出PWM波形的占空比，同时电容与电阻值选取决定PWM波形频率。SG1525输入电平由串行DA—TLV5638给出，输入参考电平与SG1525输出占空比之间的关系如图4所示。

50.0%古空比 3.30.45.6%   
45.0% 3.24.444%   
40.0%   
3.05,406%   
35.0% 2.74，34.3%   
30.0%   
25.0% 2.33.25.8%   
20.0%   
15.0% 1.84,15.8%   
10.0%   
5.0% 0.64.C. 1.25.4.5% 电平/V   
0.0%   
0.00 0.50 1.00 1.50 2.00 2.50 3.00 3.50

# 2.2 硬件电路设计

根据以上描述设计硬件电路，设计框图见图5。根据设计需求，FPGA控制板与步进电机驱动板分开。FPGA输出控制信号通过OC门驱动器，经电缆进入电机驱动板，再经过缓冲器对波形整形，驱动串行DA(TLV5638)与集成电机驱动器(LMD18200)，串行DA为PWM发生器(SG1525)提供细分参考电平，最终由集成电机驱动器产生两相驱动电流，使电机转动。位置传感器获取位置信号，由FPGA采集，作为控制电机起停的依据。

# 3FPGA电机驱动程序设计

FPGA程序提供电机驱动信号，其中包括直接为LMD18200提供两路方向信号，为串行DA提供片选、分频时钟及数据信号，通过串行DA后转换成参考电平。为实现步进电机细分控制，参考电平以细分阶梯波形式给出，如图1所示为两相八细分参考电平与方向信号。

步进电机在启动时有启动频率限制，当实际频率大于启动频率时，电机不能成功启动，造成堵转，因此软件设计必须保证初始频率小于启动频率，因此包含加速过程，逐步达到正常转速。步进电机接收到位置传感器信号后停止，这里没有采用减速曲线的方案，直接使用较大电流持续一段时间，使电机静止。静止时，电机绕组上通较小电流，保持电机静止不晃动。

电机驱动软件使用VHDL硬件编程语言编写，主要分为DETECT、CONTORL和DRIVE3个模块（模块划分及接口见图6)。当外部驱动指令发出，由CONTROL模块负责接收，并根据当前位置，分配驱动方式，并发送信号FIND启动电机。模块DRIVE接收到启动信号，进入加速状态，当加速到正常运行频率，保持速度不变。同时DETECT模块实时监测位置传感器信号，当到达指定位置，向CONTROL模块发送信号EDGE，随后CONTROL模块发送信号FIND，使DRIVE跳转到刹车状态。过一段时间，DRIVE模块进入电流保持状态，并向CONTROL模块反馈STOP信号，CONTROL模块对外发送当前位置信息LOCATION，并等待下一驱动指令。

![](images/bfd4ed16e25054fd02674fa252bf107cf249e6e7b3ac07f62a29c064e0bb654e.jpg)  
图5硬件设计框图  
Fig.5Block diagram of hardware design   
图6软件模块与接口设计  
Fig.6Software module and design of interface   
图7 电机运行电流测试

LOCATION COMMAND FIND DIR_A 电机驱动 DATA_A 指令接收 细分、加速SCLK OP_SIGNAL 传感器 EDEG 反馈发送 STOP 刹车持TAB 信号接收 DIR_B DETECT

# 4系统测试

针对该步进电机控制系统的测试主要包括运行电流测试与电机停止稳定性测试。

运行电流测试使用示波器探头监测LMD18200电流管脚，获得绕组电流。此外在绕组中串联1欧姆电阻，测量该1欧姆电阻两端电压，求差获取电阻两端电压差值。测试得到波形如图7所示。

绕组电压 AwNN

电机停止状况测试使用16位光电编码器作为角度传感器，通过联轴器将步进电机与光电编码器连接，步进电机转动带动编码器转动，测量角度。角度值通过串口发送到计算机，解码得到角度值。通过实际测得电机刚停止时角度与时间关系，可知由于没有采用减速曲线，而使用增大电流的方式使电机停止，晃动不可避免，但电机在40毫秒内恢复稳定。

# 5结束语

文中采用步进电机细分控制方法，设计了一种基于FPGA二相混合式步进电机控制系统，并通过测试对其运行电流与停止状态进行验证。该设计简单可靠，能实现加速启动，能在任意位置稳定起停，且功耗较低，适用于星载步进电机驱动。

# 参考文献：

[1]坂本正文.步进电机应用技术[M].北京:科学出版社,2010.  
[2]谭建成.电机控制专用集成电路[M].北京：机械工业出版社，1997.  
[3]史敬灼.步进电动机伺服控制技术[M].北京:科学出版社，2006.  
[4]桑鹏,吕建工,彭吉龙,等.步进电机变速控制系统设计[J].电子设计工程，2013(22):155-158.  
[5]张军,葛悦,刘超.一种高效的两相步进电机控制技术[J].计算机测量与控制，2012,20(8):2130-2132.  
[6]陶凯，赖康生.基于PWM控制H桥驱动半导体制冷片的恒温系统[J].工业控制计算机，2013，26(4):131-133.