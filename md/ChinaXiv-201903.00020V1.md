# 经验模态分解在EAST超导线圈电压信号分析中的应用

![](images/5ff9ed1b6d4a6e157aac139aac15c1292138c7129aeca35d37511e5ac9e68047.jpg)

陈远洋男1993年生，博士研究生，研究方向为托卡马克装置超导磁体馈电与优化。

陈远洋」鲍晓华」高格²周　洋1（1.合肥工业大学电气与自动化工程学院合肥2300092.中国科学院等离子体物理研究所合肥230031）

摘要：超导托克马克聚变实验装置（EAST）的极向场超导线圈发生失超时，超导线圈电阻变化引起的微弱电压信号变化被强噪声淹没。针对该问题，运用快速傅里叶变化分析线圈电压信号的时频特性。根据分析结果，提出运用经验模态分解 (EMD)方法对超导线圈两端电压信号进行分析，得到若干固有模态分量和余项，并得知微弱信号的能量主要分布在余项中。该方法能够消除坏境影响，检测出电压信号的微弱变化。

关键词：微弱信号 经验模态分解 线圈电压趋势项 中图分类号：TN911

# Application of EMD Algorithm to Analyze Voltage Signals of EAST Superconducting Coils

Chen Yuanyang1Bao Xiaohua'Gao Ge² Zhou Yangl (1.Hefei University of TechnologyHefei230009 China 2.Institute of Plasma Physics Chinese Academy of SciencesHefei 230031 China ）

![](images/f8ee6796fb3f0225007afce9a5c7f867b4a26f66a398f52f87883ead4e96f8df.jpg)

鲍晓华男 1972年生，教授，博士生导师，研究方向为电机噪声与振动的理论与控制技术。

Abstract: In experimental advanced superconducting Tokamak (EAST) device, during the quench process of a superconducting coil, the voltage variation caused by change in coil resistance is so small that is submersed in the background noise.To solve the problem, the time-frequency characteristic of the coil voltage signals is analyzed by Fourier decomposition, then the coil voltage signals is decomposed into several intrinsic mode functions (IMF） and the remainder by empirical mode decomposition (EMD). The result shows that the energy of weak signal is distributed mainly in the remainder and the weak variation can be extracted from the noise by EMD.

Keywords: Weak signal, empirical mode decomposition, coil voltage, the remainder

# 1 引言

超导托克马克核聚变实验装置（ExperimentalAdvanced Superconducting Tokamak，EAST）是我国自主设计的全超导大型非圆截面托克马克装置，其极向场磁体系统由14个超导线圈产生，为了控制等离子体击穿和位形，线圈需要提供足够大的交变电流及极快速的磁通变化[1-4]。为了保证装置的安全运行，需要在超导线圈发生失超初期及时检测到由于电阻变化引起的微弱电压信号变化。

失超是超导体运行的重要现象，极向场线圈采用CICC型导体制成，失超发生时超导线圈会突然出现电阻，并逐渐增大。因为电阻的变化会直接引起电压的变化，所以对电压的检测在众多失超检测方法中更直接快速。极向场超导线圈在工作时处于极为复杂多变的电磁环境中，线圈两端的耦合电压非常强，电阻变化引起的电压变化会被淹没在耦合噪声电压中，因此，消除电压信号噪声，准确地检测电压的变化趋势，对于失超信号的检测十分重要。

近几十年来，国内外专家学者对微弱信号的检测问题进行了广泛的研究。从传统的曲线拟合与平滑、锁定放大、离散量的统计平均、相关检测和自适应噪声抵消等技术，到新兴的随机共振、混沌阵子、经验模态分解和盲源分离等方法，计算机技术和现代电力电子技术的发展为实现这些方法创造了物质条件[5-6]。文献[7]介绍了曲线拟合原理；文献[8]比较了几种不同的平滑降噪方法；文献[9]构建了锁定放大器并将其应用于多频率时变信号的处理，消除了低频噪声的影响，提高了输出信噪比；文献[10]详细讨论了取样积分法的原理；文献[11]为了消除时域平均方法周期截断误差的影响，提出一种采用时域平均计算时的最优分段方法，相关函数是描述信号时域相似度的度量；文献[12]介绍了利用相关函数的自相关法抑制噪声，提取微弱周期信号；文献[13-14]则分别将互相关检测法用于激光远程测距中回波信号和齿轮裂纹故障信号的分析中，有效改善了微弱信号提取的成功率和精度；文献[15]提出了可变步长自适应滤波算法；文献[16]针对广义高斯噪声背景，在能量检测算法的基础上提出了改进的能量检测算法，仿真结果证明了其在低信噪比条件下错误概率明显减小。

本文利用经验模态分解（EmpiricalModeDecom-position，EMD）算法对加入失超信号前后超导线圈两端的电压信号进行处理，得到不同频率的本征特

征函数以及余项，并通过希尔伯特-黄变换计算得到各分量的频谱及边际谱，获得信号的时频分布。通过分析得知微弱的电压变化能从EMD分解的余项中体现出来。

# 2 经验模态分解算法

# 2.1经验模态算法原理

经验模态分解算法是由NordenE.Huang等提出的在内禀模态函数(Intrinsic ModeFunction，IMF)概念基础上，将任意信号分解成若干IMF分量的一种算法。每个IMF分量都表征了原信号的局部特征，可通过对其解析信号相位求导获取瞬时频率，与傅里叶变化相比，其自适应时频分析的特点使分量的频率特性随时间变化而变化，因此更适合分析非平稳、非线性信号。但是EMD算法也有其不足之处，具体表现为以下几点。

(1）端点效应现象。采用样条函数对极值点进行处理时在端点处会产生拟合误差，误差的累积会“污染”整个序列。

(2）包络线拟合问题。三次样条函数在拟合数据时存在过冲和欠冲现象。

(3）模态混叠。由于信号的异常变化导致分解后一个模态分量中存在多个不同的特征时间尺度，使IMF分量失去具体的物理意义。

# 2.2经验模态分解算法步骤

EMD 算法的步骤如下：

(1）找出原信号的极大值和极小值，用三次样条插值函数拟合得到上下包络线。(2）计算上下包络线的均值，将原始信号减去该值得到新的序列。(3）判断该序列是否符合本征模态函数的两个准则，若满足则可以作为一个IMF，否则作为原始信号，重复前两步，直到得到第一个IMF分量。（4）计算剩余信号，将其作为新的信号重复步骤（1）、（2)，直到提取所有的IMF分量。

原始信号可表示为

$$
x ( t ) = \sum _ { i = 1 } ^ { n } c _ { i } ( t ) + r _ { n } ( t )
$$

式中， $c _ { i } ( t )$ 表示第 $i$ 个本征模态函数； $r _ { n } ( t )$ 表示余项。

# 3极向场超导线圈电压信号

# 3.1超导线圈电压的产生

极向场电源是托克马克装置的子系统之一，在等离子电流的产生和控制中起着至关重要的作用。它由12套子电源系统组成，每套电源由相应的控制、测量、保护和驱动等组成，通过控制电流的变化提供极快速的磁通变化以维持等离子体电流的大小和位形。每套电源系统的结构如图1所示。

![](images/c6e417aebe1f406c75d3f14300ffd2a61fa54fa20ad9ad2b980225482f26a666.jpg)  
图1极向场电源系统结构

在每个工作周期中，线圈中的电流都会经历上升段、平顶段及对等离子电流的反馈阶段。线圈两端的电压、电流由霍尔元件测量并传送至Windows平台。图2为一次正常放电实验期间由霍尔电压传感器采集的电压信号及霍尔电流传感器采集的电流信号波形。采样频率为 $1 0 \mathrm { k H z }$ ，采样点数为230000点。图中线圈两端的耦合电压最高达到 $3 0 0 \mathrm { V }$ ，而由失超发生初期的电压变化为数伏特，检测的趋势变化仅占噪声电压的 $1 \%$ 左右。

![](images/2dee7064fd9394e1f3d0ac72ee4dea2da586671ef87f06406add36cc632dc3f1.jpg)  
图2线圈电压及电流信号  
Fig.2The voltage and current of the coil

对于超导体线圈，由于其零电阻特性，若在无干扰的情况下通入电流，其两端的电压接近零，此时能通过监测电压的幅值快速判断超导体是否失超。但是在极向场电源系统中，存在14饼相互平行的超导线圈，各线圈之间存在磁通耦合；等离子体电流在产生或破裂阶段会产生干扰磁场；装置壳体中存在的感应涡流产生磁通耦合干扰。因此，在装置运行时，超导线圈两端存在大量耦合电压，这些电压对于失超信号的检测是极大的干扰，失超引起的电压变化会被淹没在干扰电压中。

# 3.2电压信号幅频特性分析

为了了解电压信号及失超信号的幅频特性，利用快速傅里叶变换进行分析，结果如图3所示，可知电压信号中有6个幅值较大的频率分量，对应整流桥输出电流中较大的谐波分量，同时存在很多杂散分量，低频段的信号尤其丰富。

![](images/dacc3d56aabfe7c8f37fcd4a0a1eba5a59db73cb42ca6be2ccf146740d5b064a.jpg)  
Fig.1Block diagram of polodial field power system   
图3线圈电压幅频曲线

# 4 电压信号的EMD分析

由傅里叶分析知线圈两端电压信号频段宽且有丰富的低频成分，是一种非平稳信号。失超发生时，线圈电阻呈线性增加，而且失超事件可能发生在装置运行的任何时间点。为了模拟失超现象的发生，选取 $5 \sim 7 \mathrm { s }$ 时间段的数据，在原始电压信号上加入人为构造的失超信号，即电阻值乘上实时电流值，取发生失超时刻为0时刻，得到的失超信号如图4所示。

![](images/785275cda477d35b529e54338936c7d9b9afe33a74c9121a5675f12e4a883cfe.jpg)  
Fig.3The magnitude-frequency characteristic of the voltage signal   
图4失超电压信号  
Fig.4The quench voltage signal

失超信号是非周期性信号，近似于一个斜坡信号，其幅值由0V逐渐增加至5V，且线性叠加于原信号上，按照本文第2节的步骤对加入失超信号前后的电压信号进行EMD分析，提取不同频率的IMF分量和趋势项。

图5为加入失超信号前后的EMD分解结果，其中图5a显示原始信号被分解为11个IMF分量，低频分量中存在轻微频率混叠效应，这是由电压信号中的突变点造成的，但不影响趋势项的提取；图5b 显示加入失超信号后，电压被分解为12个IMF分量，说明加入信号的能量并不完全集中在趋势项中，而有部分被提取到了分量中。将原始信号减去各IMF分量，得到电压变化的趋势。图6为EMD分解结果频谱。从分解的最后一层结果看，正常情况下，截取时段电压趋势范围在 $1 1 6 \sim 1 1 8 \mathrm { V }$ ，而加入失超信号后，电压趋势值相应增加，最大达到$1 2 1 \mathrm { V }$ 。将趋势项的变化与加入的失超信号进行对比，如图7所示，用EMD分解出来的趋势项的变化能很好地跟踪叠加到原始电压信号中的失超信号。

![](images/71870c149acbfec57866734ef83edb39c9f0f1ac6fb7890702c78b6451d285cb.jpg)  
(a）正常电压信号的EMD分解

![](images/be84219f1ad5256f890b17751d098be3611012aaebc1d186c00e7c27b7d117fa.jpg)  
图5电压信号的EMD分解  
Fig.5The extraction signals by EMD

![](images/a43bbaa4362618ffc0fc21fb76e99a21cbc72bb24efa980278e44c460701c313.jpg)  
图6EMD分解结果频谱  
Fig.6The spectra of extraction signals by EMD

# 5 结束语

针对EAST极向场超导线圈耦合噪声电压过大、淹没失超信号的问题，分析了电压信号的时频特性，提出用EMD算法分解电压信号，从趋势项中提取电压变化的方法。通过分析得到如下结论：

（1）超导线圈两端的耦合电压的主要成分为6脉波，同时还含有丰富的低频干扰电压，通过快速傅里叶分析可知，主要噪声电压分布在 $0 \sim$ $1 ~ 0 0 0 \mathrm { { H z } }$ 。

![](images/642b567d9e0409bb6f23738fb55570388afa9669247d14f315273ad310d7d303.jpg)  
图7电压信号趋势变化  
Fig.7The variation of voltage signal

(2）通过EMD分解能提取不同频率特性的电压信号，从各分量的频谱图看，分解结果与原信号时频分析大致吻合。提取的余项在端点处有偏差，但总体能较好地体现加入失超信号后电压趋势的变化。

# 参考文献

[1] 王林森，汤伦军，高格，等．EAST极向场电源 控制系统的EMC接地设计[J]．电力电子技术, 2011，45(12):101-103. Wang Linsen,Tang Lunjun,Gao Ge,et al. The grounding design of EAST poloidal power supply for EMC[J].Power Electronics,2011,45(12):101-103.   
[2] 杨亚龙，傅鹏，朱银锋．EAST极向场超导线圈电 源控制网络的可靠性研究[J]．低温与超导，2012, 40(5):30-34，52. Yang Yalong,Fu Peng,Zhu Yinfeng.Research on the reliability in power supply control network for the superconducting coils of EAST poloidal field[J]. Cryogenics & Superconductivity,2012, 40(5): 30-34, 52.   
[3] 郑锐，傅鹏，王林森，等．EAST极向场电源控制 系统的数据采集系统[J]．微计算机信息，2009， 25:15-17. Zheng Rui, Fu Peng,Wang Linsen. Data acquisition system of poloidal field power supply control system of EAST[J]. Microcomputer Information, 2009, 25: 15-17.   
[4] 晁慧丽，肖炳甲，季振山．等离子体电流保护 在 EAST控制系统中的应用[J]．微计算机信息, 2010，28: 34-35，97. Chao Huili, Xiao Bingjia, Ji Zhenshan.Application of plasma current protection in controlling system of EAST Tokamak[J]. Microcomputer Information, 2010,28: 34- 35,97.   
[5] 司文荣，李军浩，袁鹏，等．直流下局部放电序 列信号检测与特性分析[J]．电工技术学报，2010, 25(3): 164-171. Si Wenrong,Li Junhao,Yuan Peng,et al. Measurement and analysis for pulse sequence of partial discharge signals under DC voltage[J]. Transactions of China Electrotechnical Society, 2010,25(3): 164-171.   
[6] 朱文龙，周建中，肖剑，等．独立分量分析-经验 模态分解特征提取在水电机组振动信号中的应用[J]. 中国电机工程学报，2013，33(29)：95-101，14. Zhu Wenlong, Zhou Jianzhong, Xiao Jian, et al. An ICA-EMD feature extraction method and its application to vibration signals of hydroelectric generating units[J]. Transactions of the Chinese Society for Agricultural Machinery,2013,33(29): 95-101, 14.   
[7] Patanadech N, Yutthagowith P. Fast curve fitting algorithm for parameter evaluation in lightning impulse test technique[J]. IEEE Transactions on Dielectrics & Electrical Insulation,2015,22(5): 2931-2936.   
[8] Halim E B,Shah SL, Zuo MJ,et al. Fault detection of gearbox from vibration signals using timefrequency domain averaging[C]. American Control Conference, 2006.   
[9] 彭建学，叶银忠．微弱信号锁定放大器噪声抑制 新技术[J]．控制工程，2007(S2)：65-67. Peng Jianxue, Ye Yinzhong. New technology of noise elimination in ultra weak signal lock-in amplifier[J]. Control Engineering of China, 2007(S2): 65-67.   
[10]孙自强，陈长征，谷艳玲，等．基于混沌和取样 积分技术的大型风电增速箱早期故障诊断[J]．振 动与冲击，2013，32(9)：113-117. Sun Ziqiang, Chen Changzheng, Gu Yanling, et al. Incipient fault diagnosis of large scale wind turbine gearbox based on chaos theory and sampling integral technology[J]. Journal of Vibration & Shock,2013, 32(9): 113-117.   
[11] 邹今春，瞿雷，戴光昊，等．基于分数延时滤波的 时域平均改进算法[J]．机械强度，2015(5)：793- 799. Zou Jinchun,Qu Lei,Dai Guanghao,et al.An improved algorithm for time domain averaging based on fractional delay filtering[J]. Journal ofMechanical Strength,2015(5): 793-799.   
[12] 明安波，褚福磊，张炜．滚动轴承复合故障特征 分离的小波-频谱自相关方法[J]．机械工程学报, 2013，49(3):80-87. Ming Anbo, Chu Fulei, Zhang Wei. Compound fault features separation of rolling element bearing based on the wavelet decomposition and spectrum autocorrelation[J]. Journal of Mechanical Engineering, 2013,49(3): 80-87.   
[13] 章正宇，畦晓林．激光测距弱信号数字相关检测 技术的研究和仿真[J]．中国激光，2002，29(7)： 661-665. Zhang Zhengyu,Gui Xiaolin. Faint signal digital correlation detection of laser ranging: study and simulation[J].Chinese Journal ofLasers,2002, 29(7): 661-665.   
[14] 杨明，董传洋，徐殿国．基于电机驱动系统的齿 轮故障诊断方法综述[J]．电工技术学报，2016, 31(4): 58-63. Yang Ming,Dong Chuanyang,Xu Dianguo.Review of gear fault diagnosis methods based on motor drive system[J].Transactions of China Electrotechnical Society, 2016,31(4):58-63.   
[15] 江涵，江全元．一种可变步长的暂态稳定自适应 修正牛顿组合算法[J]．中国电机工程学报，2011, 31(34):105-112. JiangHan,Jiang Quanyuan.Power system transient stability simulation based on shamanskii-VDHN algorithm with variable step size[J]. Proceedings of the Chinese Society of Electrical Engineering,2011, 31(34): 105-112.   
[16] 支绍龙，吴玉泉，隋天宇，等．一种改进的唤醒 信号能量检测算法及其应用研究[J]．声学技术, 2012，31(2)：162-166. Zhi Shaolong,Wu Yuquan,Sui Tianyu,et al. Research on an improved algorithm for energy detection of wake-up signal and its application[J]. Technical Acoustics,2012,31(2): 162-166.

# （上接第8页）

[12] 陆治国，赵丽丽，吴春军，等．自适应三相平衡控制的级联型三相桥式变换器：中国，CN102223099A[P].  
[13] 龙美志，邓文浪．基于新型两步换流的高频链矩阵整流器控制[J]．电力自动化设备，2013，33(10)：130-135.  
Long Meizhi,Deng Wenlang.Based on the new two-step commutation frequency link matrix convertercontrol[J]. Electric Power Automation Equipment,2013,33(10): 130-135.