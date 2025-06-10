# 基于虚拟同步机的光伏并网系统控制研究

包广清}谭宏涛」丁 坤2³汪宁渤2 高鹏飞2.3（1.兰州理工大学电气工程与信息工程学院兰州7300502.国网甘肃省电力公司风电技术中心兰州 7300503.甘肃省新能源并网运行控制重点实验室兰州730050）

![](images/c734a8d4dbea91d1233785dc5c277753939e3c35ca4ae37a652da486b749614e.jpg)

包广清女 1972年生，博士，博士生导师，教授，研究方向为特种电机设计、新能源并网稳定性等。

摘要：由于光伏新能源多通过电力电子接口接入电网，使得原先由同步发电机占主导地位的电力系统转变为高频电力电子化的电力系统。针对大规模光伏电源接入电网导致电力系统原有的转动惯量变得更小的问题，以双极式三相并网系统为研究对象，采用虚拟同步发电机控制策略，并在Matlab/Simulink中进行仿真验证。仿真结果表明：采用虚拟同步机控制策略的光伏并网系统能模拟出传统同步机惯性、调频特性。

关键词：光伏并网 虚拟同步机惯性调频中图分类号：TM615

# Research on Grid-Connected Photovoltaic System Control Based on Virtual Synchronous Generator

![](images/1ce46c679b4cbb08bc0047b8278f4774deed4602e8d1b0361792657064fed330.jpg)

Bao Guangqing'Tan Hongtao'Ding Kun2,3 Wang Ningbo2,3 Gao Pengfei2.3 （1.Lanzhou University of TechnologyLanzhou73o050China   
2. State Grid Gansu Electric Power Corporation Wind Power Technology Center Lanzhou730050China 3.Key Laboratory of Wind Power Integration Operation and Control Lanzhou730050 China ）

谭宏涛男 1994年生，硕士研究生，研究方向为大规模风光集群并网稳定性分析。

Abstract: As the new photovoltaic energy access to the power grid through the power electronic interface, the power system,which was originally dominated by the synchronous generator, is transformed into a high frequency power electronic power system. In view of the problem that large scale photovoltaic power grid connected to the power grid leads to the smaller inertia moment of power system, the control strategy of the virtual synchronous generator is adopted in the bipolar three-phase grid system. The simulation results in Matlab/Simulink show that the PV grid system with the control strategy of virtual synchronizer can simulate the inertia and frequency modulation characteristics of the traditional synchronizer.

Keywords: Grid-connected photovoltaic,virtual synchronous generator, inertia, frequency modulation

# 1 引言

当前电力系统源侧仍然是以同步发电机为主导的发电系统，同步发电机在电力系统中具有维持功率平衡和一次调频调压特性。常用的光伏并网方法有如下三种： $\textcircled{1}$ 恒压/恒频控制 (Vf控制)。通过给定电压和频率的参考值来调节逆变器输出电压和频率,多用于孤岛运行模式； $\textcircled{2}$ 恒功率控制 (PQ控制）。按照给定的有功和无功参考值向电网输送功率，但不具备电网调压调频能力； $\textcircled{3}$ 下垂控制（DroopControl)。通过有功和无功调节输出频率和电压，虽然具备了同步发电机的一次调频以及调压特性，但不具备转动惯量和阻尼特性[1-3]。上述三种方法在一定程度上限制了电网对光伏能源的接受能力。

若在光伏并网系统中引入同步发电机的特性，使得光伏并网系统在外特性上能够模拟同步发电机的性能[46，从而提出了虚拟同步机（VirtualSynchronous Generator，VSG）的基本思想[7-8]：通过向分布式发电单元引入储能系统，并配合相应的控制策略，将虚拟旋转量引入到分布发电单元，从而使分布式电源在电网暂态过程中可以具有同步发电机特性。

针对上述并网方法存在的不足，本文构建了在直流侧配备储能系统的光伏并网控制系统，采用虚拟同步机控制策略，深入分析了虚拟同步机控制策略及其实现过程，通过使用虚拟同步机控制策略，使得光伏系统向电网输送平滑功率，减小新能源并入电网时对电网造成的冲击，同时从电网侧向发电系统侧看，光伏并网系统等同于一个同步发电机，具有同步发电机的调频特性，可以根据系统负荷波动，调节自身的输出功率，极大程度上提高了系统的稳定性，利于电网对光伏清洁能源的消纳。最后通过仿真验证了采用虚拟同步机可以实现上述良好性能。

# 2 光伏虚拟同步机系统结构

虚拟同步机硬件结构由主电路和控制电路组成，如图1所示。本文对虚拟同步机的设计研究基于直流侧光－储系统供能，再由并网逆变器实现从直流侧到交流侧的电能转换。其拓扑结构由主电路和控制电路组成，逆变器由光伏电源供电，由储能电池进行稳压，逆变电路由三相全桥电路构成。

# 3 虚拟同步机控制策略分析

虚拟同步机的本体可以通过机械方程和电压方程建模[9-11]，其核心方程为

$$
\left\{ \begin{array} { l l } { \displaystyle J \alpha = J \frac { \mathrm { d } Q } { \mathrm { d } t } = J \frac { \mathrm { d } ( \omega - \omega _ { \mathrm { x } } ) } { \mathrm { d } t } = \Delta T } \\ { \displaystyle \mathcal { Q } = \frac { \omega } { p } } \\ { \displaystyle \Delta T - T _ { \mathrm { u } } - T _ { \mathrm { e } } - D ( \omega - \omega _ { \mathrm { g } } ) } \\ { \displaystyle T _ { \mathrm { M } } - T _ { \mathrm { E } } = \frac { 1 } { \omega } ( P _ { \mathrm { r } } - P _ { \mathrm { E } } ) } \end{array} \right.
$$

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { P - P _ { \mathrm { N } } = D _ { \mathrm { p } } ( \omega _ { \mathrm { N } } - \omega ) } \\ { Q - Q _ { \mathrm { N } } = D _ { \mathrm { q } } ( u _ { \mathrm { N } } - u ) } \end{array} \right. } \end{array}
$$

式中， $\alpha$ 为机械角加速度； $J$ 为转动惯量； $\varOmega$ 为转子机械角速度； $T _ { \mathrm { M } }$ 、 $T _ { \mathrm { E } }$ 分别为机械转矩和电磁转矩，对应 $P _ { \mathrm { { T } } }$ ， $P _ { \mathrm { { E } } }$ 分别为机械功率和电磁功率； $\Delta T$ 为作用在转子轴上的不平衡转矩； $\omega$ ， $\omega _ { \mathrm { g } }$ 和 $\omega _ { \mathrm { N } }$ 分别为实际电角速度、电网电角速度和额定电角速度；$D$ 为阻尼系数； $p$ 为极对数，为简化模型取 $p = 1$

![](images/05adbd2c0e17a54d461baa3a435a0e635005b714a07539063d5ee796afa0407e.jpg)  
图1基于光伏并网系统的虚拟同步机结构  
Fig.1Virtual synchronizer structure

$P _ { \mathrm { { N } } }$ 、 $Q _ { \mathrm { N } }$ ， $P$ 和 $\boldsymbol { \mathcal { Q } }$ 分别为额定有功功率、额定无功功率、输入有功功率和输出无功功率； $D _ { \mathfrak { p } }$ 、 $D _ { \mathfrak { q } }$ 分别为$P \mathcal { - } f$ 下垂系数和 $Q - u$ 下垂系数。

式（2）还可化解为

$$
\varphi = - \frac { \Delta f } { \Delta P }
$$

其中， $\varphi$ 为发电机调差系数， $\varphi = 1 / 2 \pi D _ { \mathrm { p } }$ 。

在虚拟同步机控制策略中， $P$ 与 $P _ { \mathrm { ~ T ~ } }$ 具有相同的物理意义，即 $\scriptstyle P = P _ { \mathrm { T } }$ ；并在电网频率偏移量较小的情况下，可近似取 $\omega _ { \mathrm { g } } = \omega _ { \mathrm { N } }$ ，结合式（1）、式（2）可得

$$
J \frac { \mathrm { d } ( \omega - \omega _ { \mathrm { N } } ) } { \mathrm { d } t } { = } \frac { 1 } { \omega } ( P _ { \mathrm { N } } - P _ { \mathrm { E } } ) { - } D _ { \mathrm { p } } ^ { \prime } ( \omega - \omega _ { \mathrm { N } } )
$$

其中， ${ D _ { \mathrm { p } } } ^ { \prime } \mathrm { = } \left( D _ { \mathrm { p } } + D \omega \right) / \omega$ 。

对式（4）两边同时进行微分，得

$$
\omega = \int \frac { 1 } { J } \Biggl [ \frac { 1 } { \omega } ( P _ { \mathrm { N } } - P _ { \mathrm { E } } ) - D _ { \mathrm { p } } ^ { \prime } ( \omega - \omega _ { \mathrm { N } } ) \Biggr ] \mathrm { d } t + \omega _ { \mathrm { N } }
$$

由式（4）可得虚拟同步机的 $P \mathrm { - } f$ 控制环，其控制框图如图2所示。最后输出电压相位角 $\theta$ ，用于电压矢量合成和内环坐标变换。

![](images/bbf08d4dc03fe4681b46f1579abdc79cb6da28acabc8838b5ddd2af1e5d54fd0.jpg)  
图2VSG $P \mathcal { f }$ 控制环Fig.2VSG $P \mathcal { - } f$ control loop

由上述计算式建立的虚拟同步机本体模型原理如图3所示。其中， $Q _ { \mathrm { V S G } }$ 为虚拟同步机输出的无功功率。在并网条件下，由电网提供电压支撑能力，此时取 $\mathcal { Q } _ { \mathrm { N } } = 0$ ，使系统工作在单位功率因数下，光伏电源最大限度向电网输送有功功率。

![](images/dc481388111afcae93d9ca7ad59b23aace1343dd12a54def90eb277c1e5c5e37.jpg)  
图3VSG本体原理图  
Fig.3 VSG schematic diagram

# 4 系统仿真分析

在Matlab/Simulink上搭建系统的仿真模型，对上述设计方案进行验证，主要仿真参数见下表。

# 表仿真系统参数

Tab.Parameters of simuliation   

<html><body><table><tr><td>主要参数</td><td>数值</td></tr><tr><td>额定有功功率/kW</td><td>20</td></tr><tr><td>额定无功功率/var</td><td>0</td></tr><tr><td>直流电压/V</td><td>800</td></tr><tr><td>额定电压/V</td><td>380</td></tr><tr><td>额定频率/Hz</td><td>50</td></tr><tr><td>开关频率/Hz</td><td>10</td></tr><tr><td>滤波电感及电容/mH，uF</td><td>3，10</td></tr><tr><td>电网电感/mH</td><td>2</td></tr><tr><td>发电机调差系数</td><td>0.0002</td></tr></table></body></html>

系统在初始状态下带负荷20kW在离网状态下运行，为了验证虚拟同步机的动态性能，在0.6s时突增负荷 $1 0 \mathrm { k W }$ ，在1s时突减负荷 $2 0 \mathrm { k W }$ ，在1.4s时突增负荷 $2 0 \mathrm { k W }$ ，虚拟同步机输出电压、电流波形如图4所示。虚拟同步机输出电压能保持恒定，当负荷突变时，电流能够快速响应。

![](images/df1cb5a908ddb93d8bedaedfd6b605a8f98b02de066fbe4b3f18671d169fef97.jpg)  
图4虚拟同步机输出电压、电流波形  
Fig.4 Output voltage and current waveforms ofVSG

虚拟同步机输出频率如图5所示，当负荷突变增加 $1 0 \mathrm { k W }$ 时，系统频率变化 $0 . 2 \mathrm { H z }$ 的变化量符合式(3）与发电机调差系数的设置，并且在转动惯量 $J$ 的作用下，频率的变化呈现出惯性。虚拟同步发电机输出有功功率如图6所示，符合式（2）计算结果。

系统此时带负荷3kW离网运行，在2.4s时闭合并网开关，在并网瞬间，电网输出电流波形有畸变，如图7所示。其畸变率 $\mathrm { T H D } = 2 . 1 6 \%$ ，如图8所示，符合国家电网并网要求，并网后由电网和虚拟同步发电机分配有功功率，总输出功率为 $3 \mathrm { k W }$ ，如图9所示。

![](images/3afe1831613da8006414835f21c53d978740379790211a140dc08f9005252038.jpg)  
图5系统频率波形

![](images/dad008f9b2b0f8c5d29f62f9e1376ccc14fac094d28a3c7adf000ca6159cb65c.jpg)  
Fig.5System frequency waveform

![](images/b3a42c4c82c49485220e3180746d8a9f6b8723de4ce76cec94c29e64085a1bcf.jpg)  
Fig.6System output power waveforms   
图7电网输出电流波形

![](images/8cce2d133537c3b63010c06a85c0392f00c5ba4409ae9e048bad74ed6ccb3fdd.jpg)  
图6系统输出功率波形  
图8 电流畸变率

![](images/1a9177a587e8ea407a8e8f0f247c3c623f90111d482c09ae360a739ce4c38fe9.jpg)  
Fig.7Output current waveform of grid   
Fig.8 Current distortion rate   
图9电网与虚拟同步机输出功率波形 Fig.9Output power waveforms of grid and VSG

# 5 结论

针对传统电网并网方法的不足，采用虚拟同步机的并网控制策略，并对该方法进行仿真分析。首先从同步发电机的数学模型入手，进而与同步发电机下垂方程相结合建立虚拟同步机本体模型，深入分析了虚拟同步机控制策略的实现过程，并在Matlab/Simulink中搭建模型进行仿真实验分析。实验结果表明，采用虚拟同步机控制策略的光伏系统能够主动参与电网频率的调节，体现出虚拟同步机的外特性，即调频、惯性大的特点，在目前新能源渗透率越来越高的发展趋势中具有一定的实用性。

# 参考文献

[1] 曾正，赵荣祥，汤胜清，等．可再生能源分散接入用先进并网逆变器研究综述[J]．中国电机工程学报，2013，33(24)：1-12.Zeng Zheng, Zhao Rongxiang, Tang Shengqing,etal.Review of advanced grid-connected invertersfor renewable energy decentralized access[J].Proceedings of the CSEE,2013,33(24):1-12.  
[2] 郑天文，陈来军，陈天一，等．虚拟同步发电机技术展望[J]．电力系统自动化，2015，39(21)：165-175.Zheng Tianwen,Chen Laijun,Chen Tianyi,etal. Prospect of virtual synchronous generatortechnology[J].Automation of Electric PowerSystems,2015,39(21): 165-175.  
[3] 赵巍．微网综合控制技术研究[D]．南京：南京理工大学，2013.  
[4] 赵海麟．基于虚拟同步机的微网逆变器建模与控制技术研究[D]．杭州：浙江大学，2017.  
[5] 王思耕．基于虚拟同步发电机的光伏控制系统研究[D]．北京：北京交通大学，2013.  
[6] Zhong Qingchang. Synchronverters: invertersthat mimic synchronverters generators[J].IEEETransactions on Indusrial Electronic,2011,58(4):1259-1267.  
[7] 钟庆昌．虚拟同步机与自主电力系统[J]．中国电机工程学报，2017，37(2)：336-348.Zhong Qingchang.Virtual synchronous machine andautonomous power system[J].Proceedings of theCSEE,2017,37(2):336-348.  
[8] 吕志鹏，盛万兴，李海涛，等．虚拟同步机技术在电力系统中的应用与挑战[J]．中国电机工程学报，2017，37(2)：349-359.Lü Zhipeng,Sheng Wanxing,Li Haitao,et al.Application of virtual synchronous machinetechnology in power system[J].Proceedings of theCSEE,2017,37(2): 349-359.  
[9] 钟庆昌，王晓琳，曹鑫，等译．新能源接入智能电网的逆变器控制关键技术[M]．北京：机械工业出版社，2016.  
[10] Zhong Qingchang,Ma Zhenyu, Ming WenLong.Grid-friendly wind power systems based on thesynchronverter technology[J].Energy Conversionand Management, 2015,8(9): 719-726.  
[11] 徐湘楚．基于虚拟同步机的光伏并网发电控制策略研究[D]．北京：华北电力大学，2014.