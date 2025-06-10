# 基于砷化镓晶体管的1.35 ～ 2.0 GHz 低噪声放大器1

江龙1,2，李建斌1,2,3，刘鸿飞1,3，柴晓明1（1.中国科学院国家天文台，北京100101；2．中国科学院大学，北京10049;3.中国科学院FAST重点实验室，北京10010摘要：低噪声放大器(Low Noise Amplifier,LNA)是接收机系统中的关键器件，其性能决定了接收机系统的噪声温度和对微弱射电信号的放大的能力。本文采用Avago公司碑化镓（GaAs）工艺的pHEMTATF-54134研制了一款可工作在 $1 . 3 5 \sim 2 . 0 \mathsf { G H z }$ 频率范围内的低噪声放大器。该放大器采用两级拓扑结构，单电源自偏置供电。典型增益28dB，典型噪声温度 $3 5 \mathsf { K }$ ，输入回波损耗优于-10dB，输出回波损耗优于-15dB，输入1dB压缩点为-13 dBm。该放大器除了可用于射电天文中对中性氢，脉冲星和羟基进行观测的射电望远镜接收机中以外，还可用于电波环境监测系统中。

关键词：低噪声放大器，射电天文接收机，砷化镓晶体管，输入1dB压缩点，两级拓扑电路中图分类号：TN722.1 文献标识码：xxxx 文章编号：

灵敏度是射电望远镜的一个重要指标，其大小与射电望远镜系统噪声温度成反比。射电望远镜设计完成后，最有效的降低系统噪声温度的方式是降低接收机的噪声温度。低噪声放大器(Low Noise Amplifier,LNA)是射电天文望远镜接收机中的核心器件之一，作用是对来自馈源的输入信号进行放大。LNA的噪声与增益性能共同决定了接收机的噪声温度m，同时增益还决定了接收机对信号的放大能力。1980年高电子迁移率晶体管(High Electron Mobility Transistor,HEMT)问世以来,很快就成为LNA设计常用器件之一2。HEMT是一种调制掺杂的异质结场效应晶体管,是拥有栅极，源极，漏极的三端口器件。电流从漏极流向源极，电子运动的沟道宽度受到栅极信号电压的调控，漏极电流大小发生变化从而产生增益a。HEMT具有高截止频率，高跨导，低噪声系数和低寄生电阻等特性。赝配高电子迁移率晶体（Pseudomorphic High Electron MobilityTransistor,pHEMT）是在HEMT的基础上发展而来，相比HEMT器件有更高的跨导和更好的射频特性4]。

本文选用Avago公司GaAs工艺，栅宽尺寸 $8 0 0 ~ { \mu \mathrm { m } }$ 的pHEMTATF-54143进行LNA设计。该晶体管在工作频率为2GHz时，噪声温度可以达到 $2 8 \mathrm { K }$ 以下。本文设计的 $1 . 3 5 { \sim } 2 . 0 \mathrm { G H z } \mathrm { L N A }$ ，典型增益28dB；典型噪声温度 $3 5 \mathrm { K }$ ；输入回波损耗优于 $- 1 0 ~ \mathrm { d B }$ ；输出回波损耗优于-15dB；输入1dB压缩点输入功率为 $\cdot 1 3 \mathrm { d B m }$ 。

# 1. 电路设计

# 1.1．最小噪声匹配及偏置工作点

LNA可以看作一个由多级晶体管组成系统，系统的噪声可以由式子(1）给出：

$$
F _ { t o t } = F _ { 1 } + \frac { F _ { 2 } - 1 } { G _ { A 1 } } + \ldots + \frac { F _ { k } - 1 } { G _ { A 1 } G _ { A 2 } \ldots G _ { A ( K - 1 ) } }
$$

式中： $F _ { 1 } , F _ { 2 } , F _ { 3 } , , F _ { K }$ 分别为第1级晶体管到第 $\boldsymbol { K }$ 级晶体管的噪声系数， ${ \cal G } _ { A 1 } , \ { \cal G } _ { A 2 } ,$ ’$G _ { A ( K - 1 ) }$ 分别为第1级晶体管到第 $K - 1$ 级晶体管增益。第1级晶体管的噪声对整个接收机噪声水平起到决定性作用，一定的增益还可以抑制后级晶体管产生的噪声。LNA设计时，输入匹配需按照最小噪声系数进行设计，同时第1级晶体管需要有一定的增益。单级晶体管的噪声可以由式子(2）给出:

$$
F _ { k } = F _ { \mathrm { m i n } } + \frac { 4 R _ { n } } { Z _ { 0 } } \frac { \left| \Gamma _ { o p t } - \Gamma _ { s } \right| ^ { 2 } } { \left( 1 - \left| \Gamma _ { s } \right| ^ { 2 } \right) \left| 1 + \Gamma _ { o p t } \right| ^ { 2 } }
$$

式中： $\boldsymbol { R _ { n } }$ 为二端口网络的等效噪声电阻， $\Gamma _ { S }$ 为源端反射系数， $\Gamma _ { o p t }$ 为最小噪声对应的最佳源反射系数， $\textbf { l } _ { m i n } ^ { \prime }$ 为放大器最小噪声系数。

$\textbf { l } _ { m i n } ^ { \prime }$ 由晶体管本身特性决定的，大小受到漏极电流 $I _ { d s }$ 的影响。根据晶体管厂家提供的ATF-54143 晶体管 Datasheet 中噪声系数随漏极电流变化 $\mathbf { I } _ { m i n } ^ { \prime } - I _ { d s }$ 图，晶体管最小噪声随漏极电流 Ids 减小，增益也随之降低。考虑 Ids对最小噪声和增益的影响，结合 ADS 仿真软件对晶体管电路模型的直流偏置点测试结果。本文选择晶体管偏置点漏极电流 $\mathrm { I d s } { = } 6 0 \ \mathrm { m A }$ ，漏极电压 $\mathrm { V d s } { = } 2 . 3 \ \mathrm { V }$ ，栅极电压 $\mathrm { \Delta V g s { = } 0 } . 5 8 \mathrm { \Delta V }$ 。

$\Gamma _ { o p t }$ 为最小噪声对应的最佳源反射系数， $\textbf { I } _ { s } ^ { \ \cdot }$ 是源端反射系数， $\mathbf { I } _ { \textit { s } } ^ { \prime }$ 与 $\Gamma _ { o p t }$ 相等时二端口网络噪声系数最小。为获得最低噪声，输入网络匹配需要按照最小噪声系数进行匹配。一般来说馈源输出端阻抗为50口，因此需要将最佳源反射系数对应的阻抗匹配到50口。本文按照 $1 . 5 \ : \mathrm { G H z }$ 进行输入匹配设计，此时对应最佳源阻抗为 $3 7 . 1 + j * 3 . 7 4$ ，对应最小噪声为0.243 dB。

# 1.2 电路图仿真

为满足增益要求，电路设计使用2个ATF-54143 晶体管组成两级放大电路,如图（1）所示。电路拓扑结构由四部分组成，分别是直流偏置网络，输入输出匹配网络，级间匹配网络，增益压缩网络。

![](images/9f8d85a8aecc5bd42acbd3d0098abd86258eb849a0bd027c1a7048a70d042c02.jpg)  
图1 （20 $1 . 3 5 { \sim } 2 . 0 \mathrm { G H z }$ LNA 电路拓扑结构Fig.1 $1 . 3 5 \mathrm { G H z } { \sim } 2 . 0$ GHz LNA circuit topology

直流偏置网络使用单电源自偏置设计，相比双电源供电，自偏置设计有如下优点：（1）避免了使用双电源供电所需要的开关序列σ。（2）任何漏极电流的改变都会自动调整栅级的偏置电压来保证漏极电流大小的稳定。 $\mathtt { R 1 } = \mathtt { R G } = 2 1 5$ □， $R 3 = \mathbf { R } 4 = 6 0$ □， $\mathtt { R 2 } \mathtt { = } \mathtt { R 5 } = 2 0 0 0$ □，6个村田(Murata)电阻使晶体管在电源电压 ${ \mathrm { V d d } } { = } 6 { \mathrm { V } }$ 时,偏置电压 $\mathrm { V d s } { = } 2 . 3 \mathrm { V } , \mathrm { V g s } { = } 0 . 5 8 \mathrm { V } , \mathrm { I d s } { = } 5 9 . 5 \mathrm { m A } .$ 0$\scriptstyle \mathbf { C } 7 = \mathbf { C } 8 = \mathbf { C } 9 = \mathbf { C } 1 0$ 是 $2 2 ~ \mathrm { p F }$ 的去耦电容，其目的是旁路掉直流电路的高频噪声，同时可以充当储能电容。 $\mathrm { C } 1 1 { = } 1 ~ \mathrm { u F }$ 是电源处的旁路电容，可以去除来自电源的高频噪声m。

$\mathrm { C } 1 { = } 2 . 3 \mathrm { p F }$ ， ${ \mathrm { C } } 2 { = } 2 . 2 { \mathrm { p F } }$ ， $_ { \mathrm { L 1 = 2 . 7 ~ n H } }$ ，构成了输入匹配T型网络，将最佳噪声源阻抗$3 7 . 1 + j * 3 . 7 \angle$ 4共轭匹配到50口。T型网络相对L型网络而言拥有更大的带宽和更大的阻抗变化，可以有效地控制整个频带上的响应。级间匹配同样使用一个T型网络，将第一级输出阻抗$3 5 . 2 4 7 + j \ast 1 8 1 . 1 4 2$ 共轭匹配到晶体管最大增益匹配对应的输入阻抗 $2 . 6 9 4 + j \ast 3 . 0 8 4$

增益压缩网络利用低频时电阻对晶体管增益影响大于电容和电感，高频时电容和电感带来的影响大于电阻，电阻低频损耗大，高频损耗小的原理来调节增益的平坦度。本文使用 $\mathrm { R 7 } { = } 3 3 . 2$ □， $_ { \mathrm { L 4 = 6 . 2 n H } }$ ， ${ \mathrm { C 6 } } { = } 3 . 2 ~ { \mathrm { p F } }$ 组成增益压缩网络，使得仿真时增益平坦度优于1dB。同时，R7,

L4，C6， $_ { \mathrm { L } 3 = 3 . 9 ~ \mathrm { n H } }$ ， ${ \mathrm { C } } 5 { = } 1 . 2 { \mathrm { p H } }$ 共同组成输出匹配网络。

晶体管源极引入负反馈可以增大输入阻抗，从而提高稳定性。源极电阻负反馈会增加噪声，因此使用了L5，L6，L7，L8四个源极反馈电感。实际应用中 $0 . 8 \sim 1 . 5 ~ \mathrm { n H }$ 的小电感就能满足使用需求，这里均使用 $1 ~ \mathrm { { n H } }$ 电感。为尽可能避免分立电感焊接时引起的寄生效应，这里使用微带线代替电感，经过计算得到 $1 ~ \mathrm { { n H } }$ 电感对应微带线长度为 $1 . 7 \mathrm { m m }$ 。

PCB材料的选择对LNA噪声性能有重要影响，输入信号的损耗将会引起噪声的增加，这部

WV园分增加的噪声无法在后续优化过程中去除"。本文使用高频损耗小，标准工艺制造的RO4350B介质板进行电路仿真，介电常数3.66，介质损耗角正切0.0037，板厚 $1 . 5 2 4 \ : \mathrm { m m }$ 。元件库采用Murata公司提供的的元件库，电路板电磁模型如图（2）所示。联合仿真S参数如图（3）所示，噪声参数如图（4）所示。

![](images/82b216e1c44bed56d04e17c952b05d78dfa8ab8985e073618d10748a0f38b228.jpg)  
图2电路板电磁模型 Fig.2 PCB electromagnetic model

# 2. 低噪声放大器制作和测试

# 2.1 PCB工艺

化学镀镍浸工艺（Electroless Nickel Immersion Gold，ENIG）是印制电路板（Printed CircuitBoard，PCB）常用工艺。其工艺流程主要是活化铜，化学镀镍，然后进行化学浸金在镍层上覆盖金层。ENIG工艺的PCB 表面更加平整，适用于焊接焊点更小的元器件。趋肤效应发生在镍层下边的铜层中，对高频信号的传输没有影响。金层厚度应该介于 $0 . 0 0 5 ~ { \mu \mathrm { m } }$ 和 $0 . 1 5 ~ { \mu \mathrm { m } }$ 之间。当金层厚度大于 $0 . 1 5 ~ { \mu \mathrm { m } }$ 时融入焊料中的金含量将超过重量的 $3 \%$ ，此时会使得焊点变脆，易发生断裂，影响焊接可靠性，镍蚀加剧造成黑点。当金层厚度低于 $0 . 0 0 5 ~ { \mu \mathrm { m } }$ 时金层不能完全覆盖镍层表面，会带来黑斑，发白，影响可焊性。本文所使用电路板工艺参数如表1所示：

表1电路板工艺 Table1:Process of Printed Circuit Board   

<html><body><table><tr><td>Process</td><td>Base Material</td><td>Dielectric plate Thickness</td><td>Copper Thickness</td><td>Solder Mask</td><td>Gold Thickness</td></tr><tr><td>ENIG</td><td>RO4350B</td><td>1.524 mm</td><td>1OZ</td><td>No</td><td>0.0254 μm</td></tr></table></body></html>

# 2.2 低噪声放大器测试结果

测试使用Keysight公司的PNA-LNetwork AnalyzerN5232B矢量网络分析仪，测量范围为300$\mathrm { K H z } { \sim } 2 0 \mathrm { G H z }$ ；Agilent Technologies公司的U3606A电压源，电压输出范围为 $0 { \sim } 3 6 \mathrm { V }$ ； N8974A噪声分析仪，测量范围为 $1 0 \mathrm { M H z } { \sim } 6 . 7 \mathrm { G H z }$ 。LNA封装测试如图（5）所示，电源电压为 $6 \mathrm { V }$ ；测试与仿真S参数对比如图（6）所示；测试与仿真噪声参数对比如图（7）所示。

![](images/412145a59318e81a317bae806b010edb2f7359cafdc6628bc06d119154fe0c0a.jpg)  
图5.LNA 铝合金封装测试 Fig.5 LNA’s test with aluminum alloy packing

由图（6）可以看出：1）实测LNA最大增益 $2 8 ~ \mathrm { d B }$ ，略低于仿真结果；增益变化趋势与仿真结果变化趋势基本一致； $1 . 3 5 { \sim } 2 . 0 \mathrm { G H z }$ 频率范围内平坦度优于仿真平坦度。2）S22变化趋势与仿真结果基本一致，整个频带内优于 $- 1 5 \mathrm { d B }$ ，在 $1 . 8 \ : \mathrm { G H z }$ 附近达到了最优。3）S11变化趋势相对仿真结果一致，但谐振频率范围更宽，高频性能更好，低频部分性能略差。 $1 . 3 5 { \sim } 2 . 0 \mathrm { G H z }$ 频率范围内优于 $- 1 0 \ \mathrm { d B }$ 。由图（7）可以看出，实测噪声性能与仿真结果对比有所增高，变化趋势与

图6.LNA封装测试结果与仿真结果对比 (S参数) Fig.6 LNA’s S parameters resulted:Co-Simulation and Measure   
图7.LNA噪声参数封装测试结果  
![](images/4768b76d2ef761a2f601f2e3de72646a9ec31e7e34056ae8a35aece5c80db3f0.jpg)  
Fig.7LNA’s noise parameters resulted:Co-Simulation and Measurec

分析认为，S参数和噪声性能与仿真结果之间的差异可能由以下原因导致：1）实际器件S参数与厂家提供的电路模型不完全一致，热噪声高于理想器件。2）铝合金封装外壳相当于一个波导，改变了LNA工作的电磁环境。3）测量过程中网络分析仪，噪声源以及校准存在误差。4)分立器件的焊点存在寄生效应。

本文测试了LNA在 $4 . 5 \mathrm { V }$ ， $5 . 0 \mathrm { V }$ ， $5 . 5 \mathrm { V }$ ， $6 . 0 \mathrm { V }$ 电源电压下的S参数和噪声温度。如图（8）所示，LNA增益降随着电源电压升高而升高，电源电压为6V时增益与4.5V时增益相差接近1dB。如图（9）所示，S11随着电压降升高降低，S22随着电压升高而升高。如图（10）所示，当电源电压在5.0V和5.5V时噪声性能优于 $4 . 0 \mathrm { V }$ 和 $6 . 0 \mathrm { V }$ 时噪声性能，此时在 $1 . 8 \ : \mathrm { G H z }$ 处噪声系数典型值35K。综合考虑增益，S参数以及噪声系数，本文所研制的LNA工作在电源电压为5.0V可获得最优性能：带内增益大于26dB；典型噪声温度35K；S11优于-10dB；S22优于-15 dB。

![](images/177037c124c227a754387c93226e7f302072700823d5b9a86c46c8f37a80cbe4.jpg)  
图8.不同输入电压下LNA的增益变化 Fig.8.LNA’s gain changing with different supply voltage

![](images/f47952035ec8dd3492c7b3859b6d108d8be48d01f99bead6cbcf92dd8f1dfbce.jpg)  
图9.不同输入电压时LNA的S11,S22变化Fig.9 LNA’s S11and S22 with different supply voltage

![](images/2dafb583d2f6e7dce19c7a3649e356bdebce5b8ca9d7d9d41b940ae81f918ca8.jpg)  
图10.不同输入电压时LNA的噪声温度Fig.10 LNA’s noise temperature with diferent supply voltage

![](images/c3866412c1ee6fc8210503d7bb25cde8d265356e016ea9afe4c1c70442120a02.jpg)  
图11.输入电压5V时1.8GHz 处P1dB 测试 Fig.11.LNA’s P1dB testing in $1 . 8 \mathrm { G H z }$ with $5 \mathrm { V }$ supply voltage

1分贝压缩输出功率（P1dB）是衡量放大器动态范围的一个指标，其值越大说明放大器的线性动态范围越大"。在放大器动态范围内,放大器的输出功率随放大器的输入功率的增加而增加,当输入功率增加到一定程度放大器将进入非线性工作区，放大器输出功率将不再随着输入功率增加而增加，此时输出功率将低于预期值。本文测试了电源电压为5V的情况下，LNA在 $1 . 8 \ : \mathrm { G H z }$ 频点处的1dB压缩点，如图（11）所示。测得输入功率1dB压缩点为-13dBm。

# 3. 结论

本文使用碑化镓工艺的 pHEMTATF-54143 设计了一款可工作在 $1 . 3 5 \sim 2 . 0 \$ GHz频带范围内的LNA。该放大器使用两级拓扑结构，单电源自偏置供电。电源电压 $5 \mathrm { V } { \sim } 6 \mathrm { V }$ 下均能正常工作,且具有良好的输入输出匹配、高增益、噪声温度低、动态范围大等特点。本文所研制的LNA除了可以用在L波段的射电天文望远镜接收机中以外,还可以用于空间卫星通信和电波环境监测系统中。

# 4. 参考文献

[1]MarkcClochdadacsthadvis,oseKbdmpfordroy.C.turoIntegr Circ Conf.Amsterdam,Netherlands.2012: 881-884.  
[2]WeinrebS,FenstermacherDLHarrsRW.Ultralownoise1.2to1.7GHzcooedGaAsFETmplifier[J].IEEETransactionsonMicrowave Theory and Techniques,1982,30(6) $\because$ 849-853.  
[3]David Cuadrado-Calle,Daniell George,etal.Celestial Signals.[J].IEEEMicrowave Magazine,2O17:91-99.  
[4] InderJ.Bahl．射频与微波晶体管放大器基础．鲍景富，孙玲玲等译．北京．电子工业出版.2013年．60.61.  
[5]TheData-sheetATF一54143LowNoisePseudomorphicHEMinaSurface MountPlasticPackage,AvagoTechnlogies,V0488ENJune 8，2012  
[6]文晓敏，李斌.2～18 GHz超宽带低噪声放大器芯片研制[J].天文研究与技术,2019 Vol.16(3):278-284.  
[7]张聚栋，刘景萍，吴磊，王倩．基于ATF54143的2.45 GHz低噪声放大器设计[J].电子设计工程,2017Vol.25(8):131-134.[8] 李斌，梁世光.L波段制冷低噪声放大器 [J].中国科学院上海天文台年刊.2004 (00).  
[9]谢梦,张庶,向勇,徐玉珊,徐景浩,张宣东,何波.化学镀镍浸金和化学镀镍镀钯浸金表面处理工艺概述及发展趋势[J].印制电路信息,2013(S1):185-188  
[10] 林金堵.阻挡层的表面镀覆将走上主导地位[J].印制电路信息,2015,23(10):54-58.  
[11] 邓长开,唐明津,胡义平.安捷伦矢量网络分析仪E5072A射频测控技术应用[J].电子与封装,2019,19(05):8-11.

# 1.35 \~ 2.0 GHz Low Noise Amplifier based on GaAs Transistor

Jiang Long12，Li Jianbin1.23，Liu Hongfei13，Chai Xiaomingt

Natia

Aperture Spherical radio Telescope, Beijing 100101)

Abstract: Low noise amplifier (LNA) is a key device in the receiving system in radio astronomy. The noise performance of LNA dominated the system noise temperature and the ability of radio telescope to detect extremely weak signal. In this paper, we designed an LNA based on GaAs process PHEMT ATF-54143. This LNA used 2-stage transistors topology circuit and supply by single voltage $5 \ \mathrm { V } .$ （20 Measured results show it operation in frequency range from $1 . 3 5 \mathrm { G H z }$ to $2 . 0 \mathrm { G H z }$ achieves better than -10 dB return loses and with a typical noise temperature $3 5 \mathrm { K }$ . It provides a typical gain 28 dB and input 1 dB compression point at $- 1 3 \mathrm { d B m }$ .This amplifier can be used in radio telescope receivers for the observation of neutral hydrogen,pulsars and hydroxyl groups in radio astronomy,as well as in radio environment monitoring systems.

Keyword $\because$ Low noise amplifier, Radio astronomy receivers, GaAs transistor, 1 dB compression point, 2 stages topology circuit.