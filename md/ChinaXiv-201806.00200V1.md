# 基于特征频带小波包分析的配电网故障选线的研究

叶宝柱¹　薛超宇」 张惠娟」韩叶1,2 刘伯颖（1.河北工业大学电气工程学院天津3001302.台湾勤益科技大学台中411）

![](images/91c9341e14703fa729b9e4a484d9f50e9431947cfad66f690087f233673beb89.jpg)

叶宝柱 男 1991年生，硕士研究生，研究方向为电力系统及其自动化。

摘要：通过对配电网单相接地故障暂态过程的分析，提出了对暂态接地电容电流进行小波包分解，利用能量法提取出能量最大的频带，对各条线路的特征频带利用模极大值和信号奇异性理论，从而判断出故障线路的新方法。对该方法的选线原理进行了一定的介绍，仿真实验表明该方法具有精确、可靠、适应能力强等特点，具有重要的实际应用价值。

关键词：配电网 故障选线 特征频带 小波包 奇异性检测 中图分类号：TM726

# Research on Fault Line Selection in Distribution Network Based on Feature Band Wavelet Packet Analysis

Ye Baozhu'Xue Chaoyu'Zhang Huijuan'Han $Y e ^ { 1 , 2 }$ （ Liu Boying' (1.Hebei University of TechnologyTianjin300130 China 2.National Chin-Yi University of TechnologyTaizhong 411China ）

![](images/fc9fb862d903f164f5df56d9f546fe2c3823d0eed6f7a6fcd71f2c4b5275c573.jpg)

薛超宇男 1994年生，本科生，专业为电力系统及其自动化。

Abstract: Through the analysis of the transient process of single phase to ground fault in distribution network,a new method is presented to study fault line,which decomposes transient grounding capacitive current through the wavelet packet, the maximum energy band is extracted using the energy method,and the modulus maxima and signal singularity theory are used for the characteristic frequency band of each line ，and finally which is the fault line is determined.The line selection principle are introduced as well as the line selection basis.Finally, the simulation experiments show that the proposed method is accurate,reliable and strongly adaptive,and it has an important application value.

Keywords: Distribution network, fault line selection, feature band, wavelet packet, singularity detection

# 1 引言

我国中低压配电网普遍采用小电流接地的方式[1-2]。在电力系统中最常见同时也是最危险的故障是相与相或相与地之间的短路。单相接地故障在配电网中出现的几率最高，可占总故障的 $80 \%$ 以上，此时系统的线电压依然对称，故障电流也较小，不会影响连续供电，故保护装置不必立即跳闸，可以继续运行 $1 \sim 2 \mathrm { h }$ 。但是在单相接地故障发生后，其他两相的对地电压要升高 $\sqrt { 3 }$ 倍。当发生间歇性电弧接地时，可能引起弧光接地过电压，这将危及系统绝缘或造成相间短路而导致跳闸事故[3]。因此，迅速、准确地实现故障选线，对于配电网的安全、可靠运行等有着十分重要的意义。目前国内外对故障选线都进行了大量的深入研究，提出了许多故障选线方法，如首半波法、信号注入法和相关分析法等，并开发了很多相应的装置，但是这些方法和装置都存在一定的局限性，许多问题一直未能得到很好的解决[4]。鉴于此，本文提出了一种基于小波包对特征频带提取并结合模极大值奇异性检测原理进行配电网单相接地故障选线的新方法，以期达到提高供电可靠性、提高供电部门和用户的经济效益、维护电网设备安全性的效果。

# 2 小波包分析理论

相比各种信号分析方法，更加精细的即为小波包分析，它通过对频带进行多层次的划分，进一步分解多分辨率分析并未细分的高频部分，同时可以依据被分析信号的特点，自适应地对频带进行相应的选择，使之与信号频谱相匹配，从而使时域分辨率得到相应的提高，因此，具有十分广泛的实际应用价值[5]

小波包变换：定义子空间 ${ U _ { j } ^ { m } }$ 是函数 $u _ { m } ( t )$ 的闭包空间， $U _ { j } ^ { 2 m }$ 是函数 $u _ { 2 m } ( t )$ 的闭包空间，并令 $u _ { m } ( t )$ 满足双尺度方程

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { \displaystyle \boldsymbol { u } _ { 2 m } ( t ) = \sqrt { 2 } \sum _ { k \in z } h ( k ) \boldsymbol { u } _ { m } ( 2 t - k ) } \\ { \displaystyle \boldsymbol { u } _ { 2 m + 1 } ( t ) = \sqrt { 2 } \sum _ { k \in z } g ( k ) \boldsymbol { u } _ { m } ( 2 t - k ) } \end{array} \right. } \end{array}
$$

其中， $g ( k ) = ( - 1 ) ^ { k } h ( 1 - k )$ ，函数 $u _ { m } ( t )$ ， $m = 0$ ，1，称为由正交尺度函数 $u _ { 0 } = \phi$ 确定的小波包。

设 $g _ { j } ^ { m } ( t ) { \in } U _ { j } ^ { m }$ ，则 ${ g _ { j } } ^ { m } ( t )$ 可以表示为

$$
g _ { { \scriptscriptstyle j } } ^ { m } ( t ) = \sum _ { l } d _ { { \scriptscriptstyle l } } ^ { { \scriptscriptstyle j } , m } u _ { { \scriptscriptstyle m } } ( 2 ^ { { \scriptscriptstyle j } } t - l )
$$

小波包分解为：由 $\{ d _ { l } ^ { j + 1 , m } \}$ 求 $\{ d _ { l } ^ { j , 2 m } \}$ 和 $\{ d _ { l } ^ { j , 2 m + 1 } \}$ ，即

$$
\begin{array} { l } { { \displaystyle { \{ { d } _ { l } ^ { j , 2 m } = \sum _ { k } a _ { k - 2 l } { d } _ { k } ^ { j + 1 , m }  } } } \\ { {  ( { d } _ { l } ^ { j , 2 m + 1 } = \sum _ { k } b _ { k - 2 l } { d } _ { k } ^ { j + 1 , m }  } } \end{array}
$$

式中， $a _ { j } , \ b _ { j }$ 为多尺度分析的分解序列。

随着尺度 $j$ 的减小，正交小波基函数的空间分解率越低，频率分辨率越高。针对这一问题，采用小波包分解，能将随 $j$ 的增大而逐渐变宽的频谱窗口进一步分割变细，从而使正交小波变换的缺陷得到一定的弥补，使其具有更好的时频特性[。

# 3信号奇异性分析和模极大值理论

# 3.1信号奇异性

通常信号的奇异性用lipschitz指数来表示。在数学上，lipschitz指数是一种度量，来表征函数的局部特征，其定义为：设函数 $\mathbf { \mathcal { f } } ( t )$ 在 $t _ { 0 }$ 附近具有如下特征[7]

$$
\begin{array} { r } { \left| f ( t _ { 0 } + k ) - p _ { _ n } ( t _ { 0 } + k ) \right| \leqslant A \left| k \right| ^ { \beta } \quad m < \beta < m + 1 } \end{array}
$$

则称 $\mathbf { \boldsymbol { \mathscr { f } } } ( t )$ 在 $t _ { 0 }$ 处的lipschitz指数为 $\beta$ ，其中 $k$ 是一个小量， $\beta$ 表示函数在该点的正则性，函数在某点的lipschitz指数代表该点的奇异性大小， $\beta$ 越小，函数在该点的奇异性就越大； $\beta$ 越大，函数越光滑并在这点连续、可微。

# 3.2模极大值理论与lipschitz指数对应的关系

设小波函数 $\varPsi ( t )$ 是 $\mathbf { \nabla } _ { m }$ 阶消失距、紧支撑且 $\mathbf { \nabla } _ { m }$ 次连续可微。若函数 $\mathbf { \mathcal { f } } ( t )$ 在 $t _ { 0 }$ 点的lipschitz 指数是$\beta _ { 0 }$ $( \beta _ { 0 } < m )$ ，同时在 $t _ { 0 }$ 附近 $\mathbf { \nabla } _ { m }$ 阶可微，则称小波变换（ $\vert W T _ { f } ( a , b ) \vert$ ）在 $t _ { 0 }$ 处有最大值，这个结论表明了信号中奇异点的位置与小波变换模极大值间是一一对应的关系[8]。

突变点的变化方向用小波变换模极大值的极性表示，突变点的变化强度用模极大值的大小表示。本文的故障选线就利用了这一显著优点，信号的奇异性检测理论指出了信号发生突变和幅值有很大的关系。在实际中，利用小波分析检测信号突变点的做法为：对信号进行多尺度分析，分解到一定的层次后，找出发生突变的信号，其小波变换后的系数具有模极大值，通过对模量极大值点的检测来确定故障发生的时间点[]。

# 4基于小波包特征频带提取的配电网故障选线新方法

# 4.1特征频带的定义

中性点经消弧线圈接地系统中发生单相接地故障的瞬间，零序电压 $\boldsymbol { u } _ { 0 }$ 以及暂态接地电流 $i _ { \mathrm { d . o s } }$ 分别为

$$
u _ { _ { 0 } } = U _ { _ { \mathrm { m } } } \sin { ( \omega t + \varphi ) }
$$

$$
i _ { _ { \mathrm { d . o s } } } = i _ { _ { C . \mathrm { o s } } } + i _ { _ { L . \mathrm { o s } } } = \frac { u _ { _ { 0 } } } { L _ { _ { 0 } } \omega _ { _ { 0 } } } \mathrm { e } ^ { - \alpha t } \sin \omega _ { _ { 0 } } t + I _ { _ { L m } } \cos \varphi \mathrm { e } ^ { - t / \tau _ { L } }
$$

式中， $\omega _ { 0 }$ 为自振荡角频率； $\omega$ 为工频角频率； $L _ { 0 }$ 为三相线路和电源变压器等在零序回路中的等效电感；$\tau _ { L }$ 为电感时间常数。

通常， $\omega _ { 0 } / \omega$ 比较大，而且 $i _ { C . 0 5 }$ 和 $i _ { L . \mathrm { o s } }$ 的频率相差也较大，所以，在发生接地故障的初始阶段，暂态接地电流的主要特征由暂态电容电流确定[10]。

# 4.2特征频带提取

对故障暂态电流进行小波包分解，实质是让信号通过高低通组合的共轭正交滤波器组，不断将信号划分到不同的频带上，滤波器组每作用一次，采样间隔增加一倍，数据点数减半。

按照适当的频带宽度，采用小波包分解故障暂态信号采样序列，分解后得到各频带信号对应的能量的计算式为

$$
\varepsilon = \sum _ { m } \left[ \omega _ { k } ^ { ( j ) } ( m ) \right] ^ { 2 }
$$

式中， $\omega _ { k } ^ { ( j ) } ( m )$ 为小波包分解第 $\left( j , k \right)$ 子频带下的系数，每个子频带下共有 $\mathbf { \Sigma } _ { m }$ 个系数。

采用小波包对故障零序电流作多分辨率分析，根据能量最大的原则选择特征频带来获取暂态电容电流的主要特征。除去工频所在的最低频带后，对中性点不接地配电网，特征频带是能量最大的高频频带；对于中性点经消弧线圈接地的配电网，特征频带是能量次最大的高频频带[1]。这样避免了信号频带能量较小、由于测量和计算误差的存在而导致错误选线的可能，从而为准确可靠的选线提供了基础。

# 4.3选线原理

(1）非故障线路特征频带的能量总是大于零，故障线路特征频带的能量总是小于零，并且其绝对值等于其他非故障线路能量的总和。

（2）母线故障时所有线路特征频带能量都大于零，所有线路的模极大值点的极性都相同。

(3）故障线路的模极大值点的极性和非故障线路模极大值点的极性相反，而且故障线路的模极大值数值最大。

# 5 Matlab仿真实验

运用Matlab仿真库Simulink中的电力系统工具箱，可以建立一个 $1 1 0 / 1 0 \mathrm { k V }$ 电网系统模型，如图1所示，设线路长度分别为： $\operatorname { L 1 } = 9 \mathrm { k m }$ ， $\mathrm { L } 2 = 1 6 \mathrm { k m }$ ，${ \mathrm { L } } 3 = 2 4 { \mathrm { k m } }$ ， $_ { \mathrm { L 4 } } = 1 3 \mathrm { k m }$ ， $\mathrm { L } 5 = 2 7 \mathrm { k m }$ 。

![](images/e14cd4ad07f10c254514aa07910fb30e8bc134395955b72177eff8f521b1d435.jpg)  
图1电网系统模型

线路正序、零序阻抗见表1。

# 表1各出线正序、零序阻抗

Tab.1Positive sequence impedance and zero sequence impedance of outing lines   

<html><body><table><tr><td></td><td>正序阻抗</td><td>零序阻抗</td></tr><tr><td>R/(Ω/km)</td><td>0.51</td><td>0.68</td></tr><tr><td>L/(H/km)</td><td>0.823 7× 10-3</td><td>4.3346×10-3</td></tr><tr><td>C/(F/km)</td><td>69.84×10-9</td><td>48.10 ×10-9</td></tr></table></body></html>

# 5.1仿真实验1

设 $T { = } 0 . 0 1 9 \mathrm { s }$ 时，距离母线 $3 \mathrm { k m }$ 处，线路L4发生A相接地故障。根据本文的分析方法，对该模型仿真，得到系统母线零序电压和各出线零序电流波形分别如图2、图3所示。

![](images/5923f814feec0d3f63438f6aeac49a25afa112766ac6b3b99ee216d3d31c322c.jpg)  
Fig.1Power system model   
图2母线零序电压波形  
Fig.2Zero sequence voltage waveform of the bus

本文选用db10函数，对各出线零序电流进行小波包分解，对于中性点经消弧线圈接地的系统，提取能量次最大的高频频带，得到各条线路零序电流特征频带波形如图4所示。

从图4可以清楚地看出，非故障相(线路L1、

![](images/8103008ed150766017d39a8b0d110becffc7a7c59c6e461650f364ac183a410b.jpg)  
图3各出线零序电流波形

![](images/9071679d2c4e8b2bbdb2360df8e5fb871363c986e1840f2f306dbe36b464c4db.jpg)  
Fig.3Zero sequence current of the outing lines   
图4特征频带波形（ $T { = } 0 . 0 1 9 \ \mathrm { s }$ ）  
Fig.4Feature band waveforms when $T = 0 . 0 1 9$ S

L2、L3、L5）波形的极性均相同且都是向上，故障相（线路L4）波形与非故障相相反，其幅值基本上等于非故障相幅值之和。根据选线原理，证明系统中线路L4发生了故障。

# 5.2仿真实验2

设 $T = 0 . 0 2 5 \mathrm { s }$ 时发生母线接地故障，提取各出线零序电流波形能量次最大的高频频带如图5所示。

从图5可以清楚地看出，各出线电流波形极性基本相同，其幅值没有出现较大波动且比较接近，由此可以证明系统中各子线路正常，只是母线发生了故障。更多的仿真实验情况结果见表2。

由表2可以看出，对于不同故障距离和不同故障时间以及不同故障初始角下发生单相接地故障时，运用本文的分析方法都可以给出正确的选线结果。而且，此选线方法具有很好的抗过渡电阻能力。

# 6 结束语

本文利用小波包变换对配电网发生单相接地故障选线进行了研究，得出以下结论：

（1）提出了一种利用小波包对暂态零序电容电流进行多分辨率分析，根据能量大小的原则对特征频带进行提取，根据特征频带的波形并结合模极大值奇异性检测原理，分析其极性与幅值关系来进行故障选线的新方法。

![](images/e90c93b563e3afe832f4a14f7bf19d8db5c6e18ae04f1607860911b680a66ddc.jpg)  
图5特征频带波形 （ $T = 0 . 0 2 5 \ \mathrm { s } ;$ 1  
Fig.5Feature band waveforms when $T = 0 . 0 2 5$ S

表2其他情况下的选线结果  
Tab.2Fault line selection in other situations   

<html><body><table><tr><td>故障线路</td><td>故障距离/km</td><td>故障初始角/()</td><td>选线结果</td></tr><tr><td>L1</td><td>5</td><td>270</td><td>L1</td></tr><tr><td>L2</td><td>7</td><td>80</td><td>L2</td></tr><tr><td>L3</td><td>4</td><td>18</td><td>L3</td></tr><tr><td>L3</td><td>13</td><td>90</td><td>L3</td></tr><tr><td>L4</td><td>16</td><td>140</td><td>L4</td></tr><tr><td>L5</td><td>12</td><td>30</td><td>L5</td></tr><tr><td>母线</td><td>0</td><td>0</td><td>母线</td></tr><tr><td>母线</td><td>0</td><td>150</td><td>母线</td></tr></table></body></html>

(2）建立了配电网发生单相接地故障的仿真模型，大量仿真结果表明，本选线方法对故障选线准确率的提高有很好的效果，实用性很强。同时还具有较强的躲过过渡电阻的能力，且不受TA不平衡电流、故障位置、故障时间、故障初始角和运行方式等因素的影响，具有很好的可靠性和灵活性。

# 参考文献

[1]李冬辉，史临潼．非直接接地系统单相接地障选线方法综述[J]．继电器，2004，32(18)：74-78.

Li Donghui, Shi lintong. Survey on single phase grounding fault line selection in non-direct grounding system[J].Relay,2004,32(18): 74-78.   
[2] 徐丙垠，薛永端，李天友，等．小电流接地故障 选线技术综述[J]．电力设备，2005，6(4)：1-7. Xu Bingyin, Xue Yongduan, Li tianyou, et al. Survey of fault line selection for small current grounding[J]. Power Equipment, 2005,6(4): 1-7.   
[3] Vukelja P I, Naumov R M,Vucinic M M, et al. Experimental investigations of overvoltages in neutral isolated networks[J].Generation Transmission & Distribution IEE Proceedings C, 1993,140(5):343-350.   
[4] 李光琦．电力系统暂态分析[M]．西安：西安交通 大学出版社，1994.   
[5] 赵彦伟，李志峰．小电流接地选线装置运行现状 分析[J]．电力学报，2006，21(1)：68-69，75. Zhao Yanwei,Li Zhifeng.Analysis on current situation of small current grounding line selection device[J]. Journalof Electric Power,2006,21(1): 68- 69,75.   
[6] 秦前清，杨宗凯．实用小波分析[M]．西安：西安 电子科技大学出版社，1995.   
[7] 张兆宁，毛鹏，孙雅明．电力系统故障暂态信号的 小波奇异性检测[J]．继电器，2000，28(4)：24-27. Zhang Zhaoning,Mao Peng,Sun Yaming.Wavelet singularity detection of fault transient signals in power system[J].Relay,2000,28(4): 24-27.   
[8] Chui K L,Wang J Z. On compactly supported spline wavelets and a duality principle[J].Trans.of the American Mathematicol Society, 1992,330(2):903- 915.   
[9] 肖白，束洪春，穆钢，等．基于模极大值理论的 配电网接地保护研究[J]．继电器，2004，32(10)： 36-39. Xiao Bai, Shu Hongchun,Mu Gang,et al.Study on grounding protection of distribution network based on modulus maximum theory[J]. Relay,2004, 32(10): 36-39.   
[10] 董新洲，毕见广．配电线路暂态行波的分析和接 地选线研究[C]．中国水力发电工程学会，2005： 78-83. Dong Xinzhou,Bi Jianguang.Analysis of transient traveling wave and grounding line selection in power distribution lines[C]. China Society for Hydropower Engineering,2005: 78-83.   
[11] Shyh-Jier Huang,ChengTao Hsieh.High-impedance fault detection utilizing a morlet wavelet transform approach[J].IEEE Transactions on Power Utilizing Dlivery, 1999,14(4): 1401-1410.