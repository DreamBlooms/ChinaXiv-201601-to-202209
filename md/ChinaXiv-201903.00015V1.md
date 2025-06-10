# 核电站对时系统设计优化

![](images/ab03dee74cb2ad327eaff3e6ad346df2af7c5f0ec18173785a0d311ba4e8cd1c.jpg)

王军庄男1983年生，助理工程师，主要从事核电厂电气设计方面的工作。

王军庄

（深圳中广核工程设计有限公司深圳 518172)

摘要：核电站厂区大，需要对时的系统多、分布广，而且对精度要求、接口形式各不相同。因此目前核电站内存在多套对时系统，无法实现时钟信号的共享。为解决各系统之间时钟相互独立、对时系统重复配置的问题，本文通过分析核电站内的设备对时方式、精度需求、传输通道，进而采用全厂统一时钟源的对时网络结构。该对时网络配置高精度、高可靠性的主钟系统和GPS/北斗双模天线，系统可用性大大提高；主钟与二级钟之间由光缆连接，通过设置光缆传输延时提高二级钟的精度。分析结果表明，该对时网络在可靠性和对时精度方面都有较大提高，实现了技术和经济上的统一、优化。

关键词：核电站对时网络 对时精度 传输延时中图分类号：TM73

# Design and Optimization of Time Synchronizing System in Nuclear Power Station

Wang Junzhuang (China Nuclear Power Design Co.,Ltd.(Shenzhen) Shenzhen 518172 China )

Abstract: The devices which need time synchronization are numerous and distributed broadly in nuclear power station,and there are different requirements of precision and mode among different devices. Therefore several time synchronizing systems exist in nuclear power station at present.The modes of time adjustment, precision and transmission channel are discussed in this paper,and in order to solute the problem which time synchronizing systems are not unified and mounted repeatedly, a optimal time synchronizing network is presented which has unique time source. This time synchronizing system has high availability and precision because of its main clock and GPS/China compass dual-mode satelite antenna. The main clock and sub-clock is connected through optical fiber and transmission delay is set to improve system precision.Analysis result indicates that the optimal time synchronizing network has higher reliability and precision, and it also realize the optimization of technology and economy.

Keywords: Nuclear power station, time synchronizing network, time synchronizing precision, transmission delay

# 1 引言

随着核电站内电气系统及控制系统自动化、智能化的提高，越来越多设备功能的实现依赖于准确、安全、可靠的时钟。继电保护装置、自动化装置、安全稳定控制系统、生产信息管理系统以及数字仪控系统（DigitalControlSystem，DCS）等均需要统一的时间基准，以满足事件顺序记录、故障录波、实时数据采集的时间一致性要求，并确保线路故障测距、相量和功角动态监测、机组参数校验的准确性和稳定控制水平，提高电厂运行效率及其可靠性[1。核电站厂区面积大，需要对时的系统和设备数量多。核岛、常规岛及辅助系统（BalanceofPlant，BOP）厂房内均有对时需求，而目前大多数系统配有自带对时系统，时钟信号在各个系统间不能共享。核电站对时系统的“各自为政”，造成了技术上的不统一和经济上的浪费，而且有些系统自带的对时系统配置过于简单，精度和可靠性不能满足要求。针对核电站对时系统存在的问题，本文提出一种全厂统一时钟源的高精度、高可靠性对时网络。

# 2 对时方式及传输通道

# 2.1 对时方式

发电厂、变电站自动化设备的对时方式主要有脉冲对时、串行对时、编码对时、网络对时四种。

（1）脉冲对时。脉冲对时也称硬对时，是利用脉冲的准时沿来校准被对时设备。脉冲对时分为秒脉冲信号（PulsePerSecond，PPS）、分脉冲信号(PulsePerMinute，PPM）和时脉冲信号（PulsePerHour，PPH)。

(2）串行接口对时。串行接口对时一般由时钟源通过串行接口向被对时设备发送对时报文的方式实现。串行接口时间信息每秒输出一帧，常用的数据传输速率为 $9 ~ 6 0 0 \mathrm { b i t / s }$ 。串口对时的时间报文内容包括年、月、日、时、分、秒，也可包含用户指定的其他特殊内容，如接收GPS卫星数、告警信号等。

（3）编码对时方式。IRIG时间编码序列由美国靶场仪器组（IRIG）提出，被普遍应用于时间信息传输系统，该时码序列分为G、A、B、E、H、D六种编码格式。IRIG-B时码是六种编码格式中的一种。IRIG-B码含有的时间信息有年、月、日、时、分、秒。IRIG-B码作为国际通用的时间编码，其对时回路简单，并包含了完整的绝对时标信息，在工业控制、电力系统及军事等领域得到了广泛应用。

(4）网络对时。网络对时基于网络时间协议（NetworkTimeProtocal，NTP）和精确时间协议（PrecisionTimeProtocal，PTP），以监控时钟或GPS 时钟为主时钟，将时钟信息以数据帧的形式发送给各个被对时装置。被对时装置接收到报文后通过解析帧获取当前时刻信息，来校正自己的时间，达到与主时钟时钟同步的目的。网络中报文的往返时间可以估算，因而采用补偿算法可以达到精确的对时目的，对时精度取决于同步源和网络路径等特征。IEC61850标准推荐使用的简单网络时间协议（SimpleNetworkTimeProtocal，SNTP）对时方式属于网络对时方式的一种，它简化了NTP服务器和NTP 服务端策略，提供了全面访问国家时间和频率传播服务的机制，组织时间同步子网并且参加子网的每一个地方时钟调整时间。

# 2.2对时信号传输通道

时间信号传输通道应保证主时钟发出的时间信号传输到用户设备时能满足用户设备对时间信号质量的要求，一般可在下列几种通道中选用[2]。

（1）同轴电缆。用于高质量地传输TTL电平信号，如PPS、PPM、PPH和IRIG-B（DC）码TTL电平信号等，传输距离不超过 $1 0 \mathrm { m }$ 。(2）屏蔽双绞线。用于在保护室内传输RS232接口信号，传输距离不超过 $1 5 \mathrm { ~ m ~ }$ ；用于在保护室内传输RS 422、RS485、 $2 0 \mathrm { m A }$ 电流环接口信号，传输距离不超过 $1 5 0 \mathrm { m }$ 。(3）音频通信电缆。用于传输IRIG-B（AC)信号，传输距离不超过 $1 \ 0 0 0 \mathrm { m }$ 。(4）光纤。用于远距离传输各种时间信号，传输距离取决于光纤的类型。一般情况下，多模光纤传输距离不超过 $2 \ 0 0 0 \mathrm { m }$ ，单模光纤传输距离不超过$1 0 \ 0 0 0 \mathrm { m }$ 。户外的通信介质一般情况下都应使用光纤。

# 3核电站对时需求分析

# 3.1需对时的设备

核电站内需要对时的设备主要分布在 $5 0 0 \mathrm { k V }$ 开关站、 $2 2 0 \mathrm { k V }$ 辅助变电站、核岛电气厂房和常规岛厂房。 $5 0 0 \mathrm { k V }$ 开关站、 $2 2 0 \mathrm { k V }$ 辅助变电站和常规岛厂房内需要对时的设备主要是电力系统的保护、测控、故障录波、电源管理系统（PowerManagementUnit，PMU）、故障测距、电能量采集等装置，对时信号类型主要为IRIG-B码；核岛电气厂房需要对时的设备主要为核电站辐射监测、数据采集、仪表系统和DCS系统，以及部分位于核岛内的电气保护测控、装置，对时信号类型有NTP、串口报文和IRIG-B码；此外分布于核电站各个子项的数字时钟系统也需要对时，对时接口为IRIG-B码。

# 3.2对时精度

电力自动化设备（系统）对时间同步精度有不同的等级要求，而不是通常所理解的精度越高越好，对时精度的提高需要付出相应的代价。因此，没有必要盲目追求高精度，原则是满足被对时设备本身的最小分辨率即可。文献[1]研究了电力系统被对时设备对时间同步准确度的要求，大致分为四类，准确度分别不大于 $1 \mu \mathrm { s }$ 、1ms、 $1 0 \mathrm { m s }$ 和1s，对应于核电站的被对时设备的精度要求如下：

（1）时间同步准确度不大于 $1 \mu \mathrm { s }$ ：线路行波故障测距和PMU。(2）时间同步准确度不大于1ms：电力系统继电保护、测控、故障录波装置及核电站监测、数据采集、仪表及DCS 系统。(3）时间同步准确度不大于1s：电能量采集、数字时钟系统。

# 3.3对时精度对系统功能的影响

线路行波故障测距和PMU是核电站内对时钟精度要求最高的两个系统，其功能的实现依赖于时

钟的精度。

行波测距的关键是记录下电流或电压行波到达线路两端的时间，行波的传输速度近似为光速$3 0 0 \mathrm { k m / \mu s }$ ， $1 \mu \mathrm { s }$ 时间误差对应测距误差约为 $1 5 0 \mathrm { m }$ 。为保证故障测距精度在几百米以内，对时系统的误差应该控制在几微秒以内。

PMU需要在全网统一时标下，对电力系统不同节点的电压和电流进行同步采样，生成节点电压和电流进行同步采样，在统一的时间坐标上对电力系统的状态进行分析。对时系统精度对幅值测量的影响不大，而对相角测量的影响较大， $1 \mu \mathrm { s }$ 的时间误差对应 ${ 5 0 } \mathrm { { H z } }$ 电压、电流信号，其相角误差为$0 . 0 1 8 ^ { \circ }$ 。文献[3]分析了PMU系统各个环节中产生的时间误差对系统性能的影响，并给出了解决方案。

# 4 对时网络优化

# 4.1网络结构

时间同步系统有多种组成方式，其典型形式有基本式、主从式、主备式。大型发电厂、 $5 0 0 \mathrm { k V }$ 变电站及有条件的场合宜采用主备式时间同步系统，以提高时间同步系统的可靠性[4]。由于核电站内需要对时的设备更多、分布广，且对时间同步系统的可靠性要求更高，本文提出一种全厂统一的高可靠性、高精度对时网络，结构如下图所示。

![](images/070d657b7e7a5bdb67a30fd5edc03bc4572c5769836ffa48ddbe508852ec15e2.jpg)  
图核电站对时网络结构图  
Fig.Network of time synchronizing system in nuclear power station

在 $5 0 0 \mathrm { k V }$ 开关站和 $2 2 0 \mathrm { k V }$ 辅助变电站内各设置一套独立主时钟系统，以满足这两个厂房内电气设备的对时需求。主时钟系统配置两台主时钟，并且这两台主时钟之间通过IRIG-B码进行互相对时。在核岛电气厂房内设置一台从时钟，从时钟接收来自主时钟的时间基准信号并对时间信号进行扩展。所有的对时扩展装置和从时钟的对时基准信号分别来自上述两套独立的时钟系统，保证时钟信号源的高度可靠性。另外，位于 $2 2 0 \mathrm { k V }$ 辅助变电内的光端机将IRIG-B电信号变为IRIG-B光信号，通过树状光纤网络给全厂的数字时钟对时。

# 4.2主时钟

主时钟由电源处理单元、GPS/北斗卫星信号接收及IRIG-B信号处理单元、中央定时处理单元、人机接口单元和扩展信号输出单元五部分组成。主时钟可接收GPS、北斗及IRIG-B码作为基准时间信号，当其中任意一路当前主用信号出现性能恶化或信号丢失，设备能自动切换跟踪下一可用基准时间信号。若三种基准时间信号都不能使用，主时钟可通过内置高稳晶体振荡器的守时功能，仍维持输出高精度的时间同步信号，守时精度优于 $1 \mu \mathrm { s } / \mathrm { h }$ 。

主时钟配有高精度锁相环路跟踪主用时间基准，对时精度小于 $1 \mu \mathrm { s }$ 。输出的信号类型有IRIG-B码、脉冲信号、串口报文；接口类型有TTL电平、RS422/RS485、网线、光纤。

# 4.3 从时钟

从时钟的特性及工作原理与主时钟相同，但不配置天线，只能接收主时钟输出的IRIG-B码信号作为时间基准信号。

# 4.4 可靠性

每台主时钟均配置GPS/北斗双模天线，既能够接收GPS信号，也能接收北斗时间信号。主时钟可以设置其中的GPS或北斗作为主用时间基准信号，另一个信号作为备用时间基准信号。每套独立的时钟系统有两台主时钟，主时钟之间通过IRIG-B码互校时间，当一台主时钟失去均不影响本套始终系统的正常运行。

时钟扩展装置和从时钟可以从两套独立的主时钟系统中获得时间基准信号，从对时网络结构图中可以看出，每台被对时的设备均能从4台主钟获得对时信号。当一台主时钟柜失去卫星信号或故障时，都不影响对时网络的可靠性。即便是一套时钟系统的两台主时钟因失电而不能正常工作时，全厂的被对时设备还能得到可靠的对时信号。

# 4.5 网络延时

对时系统的精度主要取决于卫星信号精度以及对时设备和网络的处理延时。从工程应用的角度出发，本文不对卫星信号的精度进行分析，简要阐述网络延时对精度的影响。

网络延时是指从主时钟接收到卫星时间信号到时间信号传送到被对时设备所需要的时间，主要包括电子器件对时间信号进行处理、转发产生所产生

的时间和传输通道延时。对于前者，主时钟及从时钟设备都有相应的补偿机制，对该延时进行补偿；对于后者，需要根据信号传输通道的长度进行相应补偿。如主时钟与从时钟之间通过光缆传输时间信号，通道延时 $\tau$ 可由下式计算

$$
\tau = L \frac { n _ { _ { 1 } } } { C }
$$

式中， $C$ 为光速； $L$ 为传输距离； $n _ { 1 }$ 为光芯区折射率，典型值为1.48。

由此可计算出光信号在光纤中每公里的传输延时大致为 $4 . 9 \mu \mathrm { s }$ 。某核电站中的对时光缆长度达到了$3 \mathrm { k m }$ ，对应的网络延时为 $1 5 \mu \mathrm { s }$ 。由此可见为保证对时网络的精度，必须根据每根光缆的长度在从时钟侧进行通道延时补偿。

# 5 结束语

本文通过梳理核电站的对时需求，给出了常用的对时方案和通道要求，进而提出了一种具有高可靠性、高精度的全厂统一对时网络结构，满足核电站对时设备的要求。该对时网络实现了技术和经济上的优化，避免了时钟系统的重复建设，同时考虑到时钟网络扩展的便利性，能够满足不同建设进度厂房内的时钟扩展。该方案对常规电厂的对时网络也有一定的借鉴作用。

# 参考文献

[1] 于跃海，张道农，胡永辉，等．电力系统时间同步方案[J]．电力系统自动化，2008，32(7)：82-86.Yu Yuehai, Zhang Daonong,Hu Yonghui,et al.Time synchronizing system for power system[J].Automation of Electric Power Systems,20o8,32(7):82-86.  
[2] 广东电网公司．Q/GD001.1154.3—2005广东电网变电站GPS时间同步系统技术规范[S]．2005.  
[3] 中华人民共和国能源局．DL/T1100.1—2009电力系统的时间同步系统第1部分：技术规范[S].2009.  
[4] 禹化然，杨贵玉，江道灼，等．基于GPS 同步时钟载波电源的分布式同步测量系统[J]．电力系统自动化，2009，33(17)：66-70.Yu Huaran,Yang Guiyu,Jiang Daozhuo,et al.Adistributed synchronous measuring system based onGPS synchronous clock carrier power source[J].