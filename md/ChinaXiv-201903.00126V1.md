# 一种基于EtherCAT的模块化多电平变流器的控制器架构

![](images/6173de8a6d71d92713e4413c98caa4adbc224e873c8147e8fbbab36d0d7ee2d3.jpg)

王付胜男 1976年生，博士，副教授，研究方向为多电平光伏并网发电、大功率风力发电并网变流器。

王付胜袁照栓鲍金铸 闻俊武（合肥工业大学电气与自动化工程学院 合肥230009）

摘要：模块化多电平变流器（MMC）具有大量子模块，控制结构系统复杂度和成本均大为增加，且传统的CAN通信或RS485 通信传输速率较慢，可靠性较低，导致各子模块之间信号同步性较差，难以满足多个控制器之间协调运行及高速可靠的通信要求。针对这一问题，本文引入EtherCAT工业以太网技术，提出一种基于EtherCAT的模块化多电平变流器的控制器架构方案。相比于传统分层控制方案，该方案仅包括主站控制器和从站控制器两层，简化了控制结构，而且极大地提高了主从站间的传输速率及可靠性，同时该方案可以精确地保证控制器间的载波信号同步。基于该方案搭建了三相MMC实验平台，实验结果表明了该方案的可行性与正确性。

关键词：模块化多电平变流器 EtherCAT 载波信号同步实时性实验平台中图分类号：TM315

# Controller Architecture of a Modular Multilevel Converter Experimental Platform Based on EtherCAT

![](images/17a4a8088ade48769aa5ecde37d9987819006df74dc4d56231b41370d108adb2.jpg)

Wang FushengYuan ZhaoshuanBao JinzhuWen Junwu (Hefei University of Technology Hefei230009 China ）

袁照栓男 1992年生，硕士研究生，研究方向为多电平光伏并网变流器及其控制。

Abstract: There is a large number of sub-modules in modular multilevel converters (MMC).It make the complexity and costs of MMC much high,and the traditional CAN communication or RS 485 communication cannot meet the good performance of real-time transmission and high reliability between sub-modules for its slow transmission rate,low reliability and poor signal synchronization. In the paper, the real-time Ethernet technology is introduced and a MMC control system scheme is designed based on EtherCAT. Compared to the traditional hierarchical control scheme,this scheme simplifies the control structure with only the master controller and the slave controller,and it greatly improves the transmission rate and reliability between master station and slave station.At the same time,it can accurately control the carrier signal synchronization. Three-phase modular multilevel converter experimental platform is built based on the strategy. The validity of proposed controller architecture is verified by experimental results.

Keywords: MMC, EtherCAT, carrier signal synchronization, real time, experimental platform

# 1 引言

由于模块化多电平变流器（ModularMultilevelConverter，MMC）[1]具有易扩展、易实现冗余控制、输出谐波含量低等优点，其数学模型[2-4]、控制方法[5-7]和硬件结构[8-10]等，已成为近年来的研究热点。目前国内外已工程化应用的领域主要是高压直流输电(HVDC)，在实验室进行的应用研究主要包括电池储能、光伏发电、电机驱动、电能质量管理等。

模块化多电平变流器的主电路拓扑如图1所示，共6个桥臂，每个桥臂均由 $N$ 个子模块及一个限流电抗器 $L _ { \mathrm { a r m } }$ 串联构成。每个子模块（SM）由带四个反并联二极管的全桥模块组成，变换器直流侧并联直流电容，交流侧引出并串联电感 $L$ 。

![](images/49e6c8f48ebd54c170de68965201c355ca1f8c58a1bebe1c6173b421224fdf2e.jpg)  
图1模块化多电平变流器拓扑结构

工程应用中，为了实现高压大容量、输出波形质量高等目标，MMC一般需要几十甚至上百个子模块级联，从而带来一系列问题。主要包括： $\textcircled{1}$ 单一控制器难以处理MMC的控制问题，需要用多控制器协调控制的方法实现控制策略，同时需要可靠、高速、大容量的通信方式将控制器连接起来进行数据通信，造成多控制器协调控制难度增大； $\textcircled{2}$ 既要实现子模块与控制器之间的高电位隔离，同时还要实现各个控制器之间载波信号的精确同步，造成控制系统的复杂度和成本都大大增加[]。

为解决上述问题，本文设计了一台基于EtherCAT的九电平MMC实验平台样机，并引入实时以太网EtherCAT通信技术，提出一种基于EtherCAT总线技术的MMC系统控制方案。该方案仅包括PLC主控制器和从站控制器两层，简化了控制结构，且PLC主控制器与各从站控制器间通过EtherCAT数据帧进行通信，相比于传统CAN通信等模式，极大地提高了主从站间的传输速率及可靠性[12]，同时利用EtherCAT技术提供的时钟同步功能，可以精确地保证从站单元控制器间的载波信号同步，增强该方案模块化级联的可扩展性，并通过实验验证了方案的可行性。

# 2 实时以太网EtherCAT工作原理

以太网控制自动化技术（EthernetforControlAutomationTechnology，EtherCAT）是由德国倍福自动化公司（Beckhoff）提出的一种基于以太网的开放架构的现场总线系统。与传统以太网解决方案不同，EtherCAT采用类似于“集总帧”的通信方式，增加了网络数据利用率，进一步提高了网络实时性。EtherCAT网络采用主－从结构，网络中仅设有一个主站用于监控整个网络的数据传输，其余设备作为从站根据主站的配置进行数据交互。EtherCAT网络中从站节点的报文处理过程直接由EtherCAT从站控制器（EtherCAT Slave Controller,ESC）在数据链路层完成，降低了节点的数据处理时延，因此提高了数据实时性。EtherCAT的网络通信原理如图2所示。此外，EtherCAT提供了精准的分布时钟功能用于同步各个从站的时序。

![](images/0fa9b2d36dec5b8d21c376468f8e98719e9f26b504347fd98aa8b9484c6cbc99.jpg)  
Fig.1Topological structure of modular multilevel converter   
图2 EtherCAT工作原理  
Fig.2Working principle of EtherCAT

# 3 实验平台控制器架构方案

# 3.1MMC实验样机控制策略

图3为控制策略框图。上下桥臂能量和控制器通过注入直流分量调节桥臂能量和，上下桥臂能量差控制器通过注入基频分量dif调节桥臂能量差。交流侧电流控制器与常规的两电平或多电平电流控制一致，这里不再赘述。

# 3.2控制系统功能描述

基于EtherCAT的模块化多电平变流器的系统控制结构如图4所示，控制系统包括三层：监控站；主站PLC；从站控制器。

监控站与主控制器进行通信，具体功能如下：实现控制参数下发和指令下达；监测整个系统的运行状态。监控站采用PC，使用人机交互界面，基于TwinCAT软件实现PLC的控制，该软件的优势在于可利用其自带的TwinCAT scope2功能模拟示波器，对程序中出现的任意变量实现波形的实时记录

![](images/06dbf226db53e6984e09e0ebe5501f8811eb28133597df708947c327eff0a7fc.jpg)  
图3控制策略框图

![](images/7a8a2f1278233b0bcb0a7d407d43f251e63b3e4448bf7995da9b9e1ec0e11ecd.jpg)  
Fig.3Control strategy block diagram   
图4基于EtherCAT的MMC控制系统结构图  
Fig.4Structure ofMMC control system based on EtherCAT

与分析。

主站控制器为PLC，具有以下功能：通过EtherCAT工业以太网与6个从站控制器通信，接收从站控制器上传的6个桥臂电流、直流侧电压、三相输出电压和电流以及各个子模块电容电压，并下发相应桥臂调制波信号给从站控制器。主控制器是整个MMC系统的运算及控制核心，主要实现MMC的外功率环、内电流环和环流抑制控制，并生成调制波下发给各个从站控制器。

从站控制器采用德国倍福公司研发的基于从站接口控制器ET1100和DSP芯片TMS320F28335的一套EtherCAT从站设备，主要功能如下：通过A-D 模块采集三相MMC上下桥臂电流、直流侧电压、三相输出电压和电流并上传给主站PLC；接收主站发过来的相应桥臂调制波信号，同时接收子模块上传的电容电压、电容电流及故障信号，并产生PWM信号下发给相应子模块。从站控制器负责MMC系统的调制控制和电容电压均衡控制。需要指出的是，EtherCAT从站设备一共有6块，为了节约资源，每块负责4个子模块即一个桥臂的信号处理。未来如果要扩展电平数，可以选择每块EtherCAT从站设备控制的子模块个数小于或等于4，最终满足每个桥臂子模块级联的数量除以每个桥臂从站控制器个数刚好等于整数即可，这样既节约了成本，又增加了系统结构的灵活性。

此外，实验平台还包括32块功能板：1块A-D板，1块三相主电路板，6块信号转接板，24块子板。A-D板与三相主电路板相连，负责桥臂电流、直流母线电压、MMC交流侧输出电压和电流的采样及硬件故障保护，并将采样值经信号转接板送入EtherCAT从站设备中。信号转接板负责将三相采样信号根据三相进行分类，再分别发给负责控制各相的EtherCAT从站设备，同时将各从站控制下发的PWM信号经隔离后分别发送给各子模块。子板包括单个H桥主电路模块、子模块电容电压和电流的采样和保护模块以及驱动电路，其样板如图5a所示。图5b为MMC实验系统其中一相的实物图。图中左边为PLC，中间部分为从站控制器经信号转接板与4个子模块相连，构成一相上桥臂，右边部分与中间部分相类似为一相下桥臂。

# 4 同步问题及同步方法的实现

由于每个桥臂采用单独的控制器，且有各自独立的时钟和PWM发送器，这就出现了系统上下桥臂间和相与相之间的时钟同步问题[13]。图6举例说明不同步所带来的严重后果。假设一相上下桥臂各有4个模块，前一开关周期各个模块的状态如图6a左半部分所示，且后一周期假设输出零电平状态。理想情况下，各个模块同步进入下一周期，但实际上，假设下桥臂延时T时间段进入下一周期，如图6a右半部分所示，使本应处于关断状态的子模块7和子模块8导通，最终使 $T$ 时间段内该相输出1电平，导致电平发生跳变。时钟不同步带来的最严重的后果是 $T$ 时间段内该相所有子模块全处于切除状态，相当于在此时间段整个直流侧电压全部加在电感上，由式（1）可知环流快速上升，甚至会导致器件烧坏。图6b为该 $T$ 时间段的一相等效电路图。

![](images/1e0cea014acc4a00605fb6b982e45b9d33d19bda8a0b3874637812198deaafda.jpg)  
图5子模块板和MMC实验系统实物图  
Fig.5Submodule board and MMC experimental system physical map 强电侧：1一电解式直流电容组2一主电路开关管MOSFET 弱点侧：3、5、8—电源模块4—驱动电路6—电压采样 7—短路电流保护模块9—电流采样10—ET1100开发板 11—PLC12—一相上桥臂   
(a）状态切换示意图

$$
( L _ { \mathrm { p a } } + L _ { \mathrm { n a } } ) \frac { \mathrm d i _ { \mathrm { d } } } { \mathrm d t } = U _ { \mathrm { d } }
$$

延迟时间： $T _ { \mathrm { s } }$   
子模块1！ 子模块1：投入 子模块1：切除 !子模块1  
子模块2 子模块2：切除 $\mathrm { \big \vert P W M = } 0 . 6 \big \vert$ 子模块2  
子模块3; 子模块3：切除 $\mathrm { P W M } = 1$ ；子模块3  
子模块4i $\mathrm { \vert P W M } = 0 . 5$ 切除 i子模块4  
子模块5！ $\mathrm { \vert P W M } = 0 . 5$ 子模块5：切除 ！子模块5  
子模块6！ 子模块6：切除 子模块6：投入 子模块6  
子模块7 PWM=1 $\mathrm { \big | P W M } = 0 . 4$ 子模块7  
子模块8i 子模块8：投入 切除 i子模块8

![](images/e745cb8f5996767f80172da5da95e3ce4fab191e03b61bd688282c18ec60ae71.jpg)  
图6时钟不同步示意图

本系统所采用的EtherCAT工业以太网技术自带分布时钟的功能，当采用DC同步模式时，默认第一个具有同步时钟功能的从站作为参考时钟，并以参考时钟来同步其他设备和主站的从时钟。在运行阶段，从站ESC芯片分布时钟控制单元产生同步信号Sync0。同步信号Sync0通常情况下为高电平，并周期性产生一小段低电平信号，当分布时钟控制单元产生的Sync0信号由高电平变为低电平时，会产生一个中断事件，并在中断子程序中将用于生成载波信号的时间基准计数器值置零。

同步信号Sync0的周期可以设置成等于载波周期或载波周期的整数倍，同步模式示意图如图7a所示。为了验证同步时钟的功能，通过主站PLC给三个从站发同样的调制波，从站控制器载波频率设为$5 \mathrm { k H z }$ 。当没有采用同步时钟功能时，所测三个从站产生的PWM信号如图7b所示，不同从站PWM信号之间存在偏移，且偏移的时间各不相同，证明从站控制器时钟不同步。当采用同步时钟功能时，所测三个从站产生的PWM信号如图7c和图7d所示，由图可知，各从站PWM信号的偏移时间为 $1 . 4 \mathrm { n s }$ ，可忽略不计，证明各从站被精确同步。

![](images/8afe87902dc41881bec02bd01127d75fc2e7d4129c68d00cc215f2c05497b68e.jpg)  
Fig.6Clock asynchrony diagram   
图7时钟同步示意图  
Fig.7Clock synchronization diagram

# 5 实验

为了验证上述基于EtherCAT的MMC控制系统的可行性以及对同步问题的解决，搭建了三相MMC实验平台，实验参数见下表。

表MMC实验平台参数Tab. MMC experimental platform parameters  

<html><body><table><tr><td>参数</td><td>数值</td></tr><tr><td>直流侧电压Udc/V</td><td>100</td></tr><tr><td>每相子模块数</td><td>8</td></tr><tr><td>调制比m</td><td>0.9</td></tr><tr><td>子模块电容C/mF</td><td>3</td></tr><tr><td>桥臂电感Larm/mH</td><td>4</td></tr><tr><td>负载电感L/mH</td><td>4</td></tr><tr><td>负载电阻R/Ω</td><td>15</td></tr></table></body></html>

# 5.1开环试验验证同步问题

实验采用直接调制法和子模块电压排序法，图8a为没有采用同步时钟功能时的A相输出电压波形，对其中一个周期的电压波形进行放大，可以看到在A点处电平发生了跳变。图8b为应用同步时钟功能时的A相输出电压波形，对一个周期的电压波形进行放大，可以看到电平跳变的现象得到很好地解决。

![](images/d86606d9bcd96c7c2c7edfcbd96bda8f4f6853d50b11518ed187ec2e5712e21b.jpg)  
图8同步前后输出电压波形对比  
Fig.8Comparison of output voltage waveforms before and after synchronization

# 5.2闭环试验

图9a和图9b分别为三相输出电压和三相输出电流波形，从图9a可以看出，MMC三相输出电压由非常细密的9个电平组合而成，构成九电平电路；从图9b可以看出，输出电流较为平滑，接近 $5 0 \mathrm { { H z } }$

（//00)4 w\* （/t(5 ms/格) t(5 ms/格)(a）三相输出相电压 (b）三相输出电流ina idiffa  
(/V1）! 10000000000 27 xssx&s&t(10 ms/格) t(10 ms/格)  
(c）A相桥臂电流、环流 (d）子模块电容电压

正弦波。图9c为A相上下桥臂电流及环流波形，可以看出桥臂电流中除了含有直流和基波分量，还存在2次谐波分量，此2次谐波分量可通过环流抑制策略加以滤除。图9d为子模块电容电压波形，可以看出子模块电容电压稳定在25V左右，较好地实现了均压策略。从图9中MMC的工作情况可以看出，所设计的基于EtherCAT的模块化多电平变流器控制系统可行，且精确地实现了各模块的同步。在此硬件平台上可较好地实现直接调制法和电容电压平衡策略。

# 6 结束语

本文首先针对模块化多电平变流器系统存在的问题，设计了基于EtherCAT的模块化多电平变流器控制系统方案，该系统能有效地降低系统控制复杂度，提高了主从站间的传输速率及可靠性，同时利用其分布时钟功能使从站控制器间载波信号得到精确同步，增强了MMC模块化级联的可扩展性。在此控制系统基础上进行了整个实验平台的硬件构架设计，最后运用直接调制法和电容电压排序算法进行了三相MMC实验，实验结果验证了所提出方案的有效性。

# 参考文献

[1] Marquardt R, Lesnicar.A new modular voltage source inverter topology[C]. Proceeding of EPE’03, Toulouse,France,2003.   
[2] 王姗姗，周孝信，汤广福，等．模块化多电平电 压源变流器的数学模型[J]．中国电机工程学报, 2011，31(24):1-8. Wang Shanshan,Zhou Xiaoxin, Tang Guangfu,et al. Modeling of modular multi-level voltage source converter[J]. Proceedings of the CSEE,2011,31(24): 1-8.   
[3] 周月宾，江道灼，郭捷，等．模块化多电平变流 器模块电容电压波动与内部环流分[J]．中国电机 工程学报，2012，32(24)：8-14. Zhou Yuebin, Jiang Daozhuo, Guo Jie, et al. Analysis of sub-module capacitor voltage ripples and circulating current in modular multilevel converters[J]. Proceedings of the CSEE,2012, 32(24): 8-14.   
[4] 刘栋，汤广福，郑建超，等．模块化多电平变流 器小信号模型及开环响应时间常数分[J]．中国电 机工程学报，2012，32(24)：1-7. Liu Dong, Tang Guangfu, Zheng Jianchao,et al. Small signal modeling and analysis open-loop response time constant of MMC[J]. Proceedings of the CSEE,2012,32(24): 1-7.   
[5] 郭捷，江道灼，周月宾，等．交直流侧电流分别 可控的模块化多电平变流器控制方法[J]．电力系 统自动化，2011，34(19)：64-68. Guo Jie, Jiang Daozhuo, Zhou Yuebin,et al.AC and DC current hybrid control strategy for modular multilevel converter[J]. Automation of Electric Power Systems,2011,34(19): 64-68.   
[6] 赵昕，赵成勇，李广凯，等．采用载波移相技术 的模块化多电平变流器电容电压平衡控制[J]．中 国电机工程学报，2011，31(21)：48-55. Zhao Xin, Zhao Chengyong, Li Guangkai, et al. Submodule capacitance voltage balancing of modular multilevel converter based on carrier phase shifted SPWM technique[J]. Proceedings of the CSEE,2011, 31(21): 48-55.   
[7]江道灼，郭捷，周月宾，等．49 电平模块化多电 平变流器样机设计与实验验证[J]．中国电机工程 学报，2013，33(27)：88-95. Jiang Daozhuo,Guo Jie, Zhou Yuebin, et al. Design and experiment of modular multilevel converter prototype with 49 -level output voltages[J]. Proceedings of the CSEE,2013, 33(27): 88-95.   
[8] Glinka M. Prototype of multi phase modularmultilevel-converter with 2MW power rating and17- level-output-voltage[C]. IEEE Power Electronics Specialists Conference,Aachen,Germany, 2004: 2572-2576.