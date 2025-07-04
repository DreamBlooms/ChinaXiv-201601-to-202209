# 一种BPM脉冲超宽带发射机设计

谢义方，于庆法，黄永辉，熊蔚明(中国科学院空间科学与应用研究中心，北京100190)(2013年12月17日收稿；2014年8月20日收修改稿)

Xie YF,Yu QF,HuangYH,etal.ABPMpulse UWB transmiterdesign[J].Journalof Universityof Chinese Academy of Sciences,2015 32(3) :373-377.

摘要设计一种新的基于分立器件的 BPM(二相调制)脉冲超宽带发射机.脉冲超宽带发射机由单极性亚纳秒脉冲发生器、双极性脉冲产生电路及高速微波开关组成.发射机在时钟和数据“1"和O"控制下分别输出正、负脉冲.测试结果表明，该发射机输出脉冲宽度 ${ < 4 0 0 \ \mathrm { p s } }$ 带宽$> 1 . 5 \ \mathrm { G H z }$ ,可稳定输出BPM超宽带脉冲信号码速率可达50Mbps,可应用于脉冲超宽带通信系统.

关键词 超宽带；通信；二相调制；发射机 中图分类号：TN957 文献标志码：A doi: 10. 7523/j. issn.2095-6134.2015.03.012

# A BPM pulse UWB transmitter design

XIE Yifang,YU Qingfa ,HUANG Yonghui,XIONG Weiming (Centerfor Space Scienceand Applied Research,ChineseAcademy ofSciencesBeijing1Oo19O,China)

AbstractA new bi-phase modulation(BPM） pulse UWB transmitter manufactured by discrete components is designed. The transmitter consists of mono-polar sub-nanosecond pulse generator ， bipolar pulse generator，and high speed microwave switch． The transmiter transmit positive and negative pulses when controlled by clock signal as well as data $^ { \prime } 1 ^ { \prime }$ and data $' 0 ^ { \prime }$ ，respectively. Experimental results show that the generated pulse width is below 4OO ps,the bandwidth is more than $1 . 5 ~ \mathrm { G H z }$ ，and the data rate is up to 5O Mbps. It can be used in the pulse UWB(ultrawideband） communication systems.

Key wordsultra-wideband; communication;BPM；transmitter

在短距离恶劣环境条件下，脉冲超宽带技术相对传统的连续波窄带技术具有诸多优势[1-3].脉冲超宽带通信、定位技术已成为当前研究热点之一.脉冲超宽带通信是通过发射和接收宽度极窄的脉冲(纳秒级甚至皮秒级)来传输数据.数据对脉冲的调制方式可分为基于时间的调制方式和基于形状的调制方式.其中基于时间的调制方式有脉冲位置调制（PPM），基于形状的调制方式有二相调制（BPM）、开-关键控调制（OOK)、脉冲幅度调制(PAM)及正交脉冲调制(OPM).二相调

制可表示为

$$
s _ { i } = \sigma _ { i } p ( \mathit { t } ) , \sigma _ { i } = 1 , - 1
$$

其中， $p ( \mathbf { \Omega } _ { t } )$ 为基脉冲、 $\sigma _ { i }$ 表示脉冲形状参数.对于二进制系统，二相调制可得到2种脉冲形状： $s _ { 1 }$ $\mathbf { \beta } = \mathbf { \beta } _ { p } ( \mathbf { \beta } _ { t } ) \mathbf { \beta } _ { \mathbf { \beta } _ { s _ { 2 } } } = - \mathbf { \beta } _ { p } ( \mathbf { \beta } _ { t } )$ .相对PPMBPM可获得3dB功率效率增益，同时可降低对时间抖动的要求[4].近年来 各种 BPM调制脉冲超宽带发射机被研制出来.Meng 等[5]设计一款基于 $0 . 1 8 ~ \mu \mathrm { m }$ CMOS工艺的脉冲发射机前端，在芯片上实现了一种脉冲宽度可调的BPM脉冲超宽带发射机.Mohammad[6]提出一种利用 $9 0 \ \mathrm { n m \ C M O S }$ 工艺的低功耗、高码率BPM脉冲发生器设计，并在HSPICE环境中对设计进行仿真分析.上述发射机设计都是通过ASIC实现，ASIC价格昂贵且时间周期较长在一些实验系统中基于分立器件的发射机设计价格低廉、周期短、设计灵活.James[7]基于分立器件实现了一种有载频脉冲超宽带发射机.该发射机可以产生载波调制的超宽带脉冲信号可为实验测试及算法验证提供平台.该发射机所产生的脉冲宽度为3ns.Orlenko[8]提出一种主要基于分立的MOSFET、SRD及电感的无载频超宽带脉冲发生器，该发生器可产生重复频率为$0 . 5 ~ \mathrm { M H z }$ 宽度为纳秒级的负脉冲.上述基于分立器件的超宽带脉冲发生器都无法产生BPM信号.目前基于分立器件的高重复频率、亚纳秒、BPM脉冲发射机尚未公开报道.为了给未来太空探索提供新的技术支持，中国科学院国家空间科学中心近年来逐步开展脉冲超宽带技术及其航天应用研究.本文介绍一种基于分立器件的BPM脉冲超宽带发射机发射机可产生宽度为亚纳秒、重复频率为 $5 0 ~ \mathrm { M H z }$ 的超宽带信号.

# 1系统描述

# 1. 1 系统简介

BPM脉冲超宽带发射机原理图如图1所示，发射机包括单极性脉冲发生器、双极性脉冲发生器及高速微波开关3个部分.单极性脉冲发生器在外部时钟信号控制下产生重复频率与时钟频率一致的亚纳秒超宽带负极性脉冲信号.双极性脉冲发生器实现将单极性脉冲发生器所产生的单通道输入负脉冲转变为双通道输出的对称双极性脉冲.在其中一个通道输出正脉冲 在另一通道输出负脉冲.高速微波开关在外部输入数据信号的控制下实现对双极性脉冲的二选一操作，选择其中一个通道的脉冲信号输出.

时钟□ +3.3V 电 B 双发 LW MR4 生 SN74LVC74A C3 L D2 D3 T1 U3HMC232 江江 E +5V C Q1 非 D1 本 R5 >已调脉冲 上 74ACT14 R2 BFG235 SMMD840L2 ∠   
数据□

# 1. 2 单极性脉冲发生器

单极性脉冲发生器在基带数据控制下产生皮秒级负极性超宽带脉冲信号.发生器主要由纳秒级驱动正脉冲产生电路、高速开关电路及亚纳秒脉冲产生与整形电路3部分组成.单极性脉冲发生器原理框图如图2所示.纳秒级驱动正脉冲产

纳 高速开 亚纳 超宽带时钟产生电路 关电路 整形电路 负脉冲生电路在时钟外部时钟控制下产生纳秒级脉冲信号.如图1所示，正脉冲产生电路主要由D触发器SN74LVC74A、施密特反向器74ACT14及RC充放电电路组成.当时钟上升沿到来时电路产生宽度为几纳秒的正脉冲.脉冲宽度由RC电路放电时间及D触发器传输延时决定.高速开关在纳秒级脉冲信号控制下闭合或断开.当纳秒级正脉冲信号出现时，高速开关闭合，否则高速开关断开高速开关由微波三极管BFG235实现.亚纳秒脉冲产生单元主要由阶跃恢复二极管SMMD840

D1、肖特基二极管BAT15D2、D3、电感、电容及电阻组成.亚纳秒脉冲产生单元在静态时无脉冲产生，当高速开关快速由断开转变为闭合时，电容C3 经L1、D1放电.由于D1为阶跃恢复二极管，在反向偏置时不会马上截止，而是在经历存储时间及阶跃时间后才完全截止.在阶跃时间段电流经肖特基二极管D2、D3流向负载.由于阶跃时间为皮秒级因此在负载上可得到下降沿与阶跃时间相当的脉冲信号.当D1经历阶跃时间截止后，由于储能元件 $\mathrm { L } , \mathrm { C }$ 经负载回路短时储能释放.这样便在负载端得到皮秒级负极性脉冲，

图3所示为单极性脉冲发生器测试结果.其中图3(a)为单极性脉冲发生器产生的负极性脉冲时域波形(测试时衰减 $1 0 ~ \mathrm { d B }$ ）脉冲宽度为263ps( $5 0 \% - 5 0 \%$ ）图3(b)为图3(a)所示脉冲归一化频谱图图(c)为重复频率为 $5 0 ~ \mathrm { M H z }$ 的脉冲串时域波形.由频谱图可知图3(a)所示脉冲带宽为 $2 . 3 \ \mathrm { G H z } ( \mathrm { \Omega } - 1 0 \ \mathrm { d B } )$ ：

# 1.3 双极性脉冲产生电路

双极性脉冲产生电路将单极性脉冲转变为双极性脉冲.如图1所示双极性脉冲产生电路采用Mini-Circuits公司生产的宽带射频传输线变压器TC1-1-13M.该变压器插入损耗小于3dB,工作频带为 $4 . 5 \sim 3 0 0 0 ~ \mathrm { M H z } .$ 双极性脉冲产生电路输入脉冲为图3(c)所示负脉冲输出双极性脉冲如图4所示.图4所示正脉冲幅度为0.3494V，负脉冲幅度为0.3542，正负脉冲之差为 $0 . 0 0 4 8 \mathrm { ~ V ~ }$ ：正脉冲宽度为380ps,负脉冲宽度为390ps.正脉冲带宽为 $1 . 6 2 \mathrm { \ G H z } ( \mathrm { ~ \Omega ~ } - 1 0 \mathrm { \ d B } )$ ，负脉冲带宽为$1 . 5 8 ~ \mathrm { G H z } ( \mathbf { \varepsilon } - 1 0 ~ \mathrm { d B } )$ .由结果可知，虽然由于变压器带宽原因导致双极性脉冲产生电路输出正、负脉冲相比原单极性负脉冲分别展宽117ps和127ps,带宽比原脉冲分别变窄0.68GHz和0.72GHz但正、负脉冲二者之间的幅度相对误差仅为$1 . 3 6 \%$ 脉冲宽度相对误差仅为 $2 . 6 \%$ ：

![](images/6c7cbfa7c5f25b379ac18a7f671314fb4aa270b8b7a1d428be12741b61f96fef.jpg)  
图3单极性脉冲发生器测试结果 Fig.3Test results of the unipolar pulse generator

![](images/101a926001893c314505bf49e0e0218cf35bef8f9e750ce6e27b9aecde748c8e.jpg)  
图4双极性脉冲产生电路测试结果 Fig.4Test results of the bipolar pulse generator

# 1. 4 高速微波开关

高速微波开关实现在数据的控制下对双极性脉冲产生电路输出的双极性脉冲进行选择，当数据为“1"时，与正脉冲输入端相连的开关切换至调制脉冲输出端发射机输出正脉冲信号.与负脉冲输入端相连的开关切换至 $5 0 ~ \Omega$ 负载双极性脉冲产生电路负脉冲输出端匹配，避免了由于开路引入的全反射对正脉冲输出带来不利影响.同样，当数据为 ${ \bf \tilde { \Sigma } } ^ { 6 } { \bf \Sigma } _ { 0 } ^ { 9 }$ 时，与负脉冲输入端相连的开关切换至调制脉冲输出端，发射机输出负脉冲信号.与正脉冲输入端相连的开关切换至 $5 0 ~ \Omega$ 负载双极性脉冲产生电路正脉冲输出端匹配避免了由于开路引入的全反射对负脉冲输出带来不利影响，

高速微波开关电路如图5所示.开关采用Hittite公司生产的HMC232G7,工作频带为DC-$6 ~ \mathrm { G H z }$ 隔离度 ${ > } 3 7$ dB1dB压缩点为 $2 7 ~ \mathrm { d B m }$ 开关时间为 $6 ~ \mathrm { n s }$ 适合作为高码率、中功率脉冲发射机使用.由于开关控制电压为负电压因此在电路中增加了电压转换电路将输入的5V和0V分转换为0V和 $- 5 \mathrm { ~ V ~ }$ ：

![](images/fe6610cf4e673ce2f7e3fe0253ee7c57d9239440d733839784ee79d173ee541f.jpg)  
Fig.5Schematic of the microwave switch

# 2实验测试

对上述BPM脉冲超宽带发射机进行无线测试发射机输出端通过电缆与超宽带发射天线相连超宽带接收天线经电缆与示波器连接码速率为50Mbps,天线采用Vivaldi天线.图6为发射机无线测试结果.其中图6（a）为数据为“1010”时接收天线输出信号时域波形，图6(b)为数据为“1000"时接收天线输出信号时域波形图6(c)所示为数据为“1110”时接收天线输出信号时域波形.由测试结果可知，本文介绍的发射机输出的BPM超宽带脉冲信号与基带数据吻合，当数据由“1"变为“0"时接收脉冲极性同样反转.

![](images/53c3f57ee6830407195aba3765209c20b4563a576e11a96d2d8f572bba2c02b3.jpg)  
图5微波开关电路  
图6无线测试结果  
Fig.6Test results of wireless experiments

# 3 小结

本文介绍一种新的基于分立器件的BPM无载频脉冲超宽带发射机发射机完成了电路设计、电路板制作及实验测试.测试结果表明,发射机性能良好稳定、可靠输出BPM脉冲信号.

在后续研究工作中将对上述发射机进行改进进一步提高输出信号中心频率、带宽及码速率,使其频谱符合FCC规范,降低输出脉冲振铃水平同时研制对应的相干脉冲超宽带接收机，为脉冲超宽带技术研究提供平台为通信、测距应用提供新的技术支持，

# 参考文献

[1]Rolf K，Marcos D K.Short-range wireless communications [M].West Sussex:John Wiley & Sons Ltd ,2009:97-112.   
[2] Domenico P，Walter H.Ultra wideband radio technology: potential and challenges ahead [J].IEEE Communications Magazine,2003,41(7) :66-74.   
[3]Zhang C M，Michael JK.Real-time noncoherent UWB positioning radar with millimeter range accuracy:theory and experiment [J].IEEE Transon Micro Theoryand Techniques,2010,58(1):9-20.   
[4] Ghavami M,MichaelLB,Kohno R.Ultra wideband signals and systems in communication engineering [M].West Sussex:John Wiley & Sons Ltd,2007:110-113.   
[5] Meng M，Huynh C，Nguyen C.Development ofCMOS transmitter frontends for UWB pulse systems [C]//IEEE International Symposium on Antennasand Propagation Proceedings.Spokane: 2011:3174-3 177.   
[6] Mohammad N K.A low power,high data rate IR-UWB pulse generator with BPSK modulation in 90 nm CMOS technology foron-chipwirelessinterconnects [C]//International Conference on Infonnatics，Electronics &Vision．Dhaka: 2012:87-90.   
[7]James C V.Design of a discrete-component impulse-radio ultra wide-band（IR-UWB) testbed and design of a very lowpower IRUWB transmitter in CMOSTechnology[D]. Lausanne:Ecole Polytechnique Federale de Lausanne ,2012.   
[8]Orelenko O．A．UWB pulse generator.ultrawideband and ultrashort impulse signals[C]//Ultrawideband and Ultrashort Impulse Signals. Sevastopol. 2012:75-77.