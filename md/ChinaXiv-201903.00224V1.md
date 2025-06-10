# 2-18GHz超宽带低噪声放大器芯片研制

文晓敏’²，李斌¹

（1.中国科学院上海天文台，上海 200030；2.中国科学院大学，北京100049）摘要：低噪声放大器在射电天文望远镜接收机中是一个重要的前端组件，其性能对接收机的灵敏度和噪声有着至关重要的影响。本文采用OMMIC公司 $7 0 \mathrm { n m }$ GaAsmHEMT工艺研究和设计了一款工作频率为2-18GHz的超宽带单片微波集成低噪声放大器芯片，芯片面积为2$\mathrm { m m } \times \mathrm { 1 m m }$ 。放大器电路采用三级级联放大、双电源供电拓扑结构，常温在片测试结果显示，全频带增益大于28dB，噪声温度平均值为93K，直流功耗 $1 5 0 \mathrm { m W }$ ，无条件稳定。该放大器芯片覆盖了射电天文S、C、X、Ku四个传统观测波段，适用于厘米波段超宽带接收前端和毫米波段超宽带中频放大模块。

关键词：低噪声放大器；GaAsmHEMT；超宽带；单片微波集成电路

中图分类号：TN722.3

基金项目：国家自然科学基金（11473060，11590784)作者简介：文晓敏，女，硕士，研究方向：射电天文.Email:sslnlnss $@$ 126.com

# 1引言

作为射电天文望远镜接收机前端的核心器件，低噪声放大器（Low Niose Amplifier，LNA）不仅要将天线接收到的来自外太空的微弱信号进行低噪声放大，还要求具有较高的增益来抑制后级链路噪声，保持接收系统的灵敏度。单片微波集成电路（Monolithic MicrowaveIntegrated Circuits，MMIC）形式的低噪声放大器芯片是实现超宽带、低噪声、高增益器件的重要途径。mHEMT（Metamorphic High-eletron-mobility Transistor）具有高频、高功率及噪声性能好的优点，广泛应用于雷达、遥感、辐射测量等领域[1]。本文设计MMIC LNA 芯片所用的OMMICD007IHmHEMT工艺，拥有 $7 0 \mathrm { n m }$ 栅长和高掺铟沟道，在变质的缓冲层上生长高铟浓度的外延活跃层，从而实现与GaAs 衬底的平稳过渡，因而使其具有极低的噪声和超高频特性[2]。本文设计的2-18GHz 低噪声放大器芯片频率覆盖达到9个倍频程，结合超宽带馈源和极化网络，可以构建超宽带射电天文接收系统，实现S、C、X、Ku四个传统射电频段的同时观测，极大地提高连续谱观测灵敏度和多谱线观测效率，是国际上射电天文技术发展的重要方向。

2 电路设计

2.1噪声特性及器件选择低噪声放大器级联噪声系数公式为：

$$
N F ( d B ) = N F _ { 1 } + \frac { N F _ { 2 } - 1 } { G _ { 1 } } + \frac { N F _ { 3 } - 1 } { G _ { 1 } G _ { 2 } } + \cdots + \frac { N F _ { n } - 1 } { \Pi G _ { n - 1 } }
$$

其中， ${ N F } _ { n }$ 、 $G _ { n }$ 分别为第 $\mathbf { \eta } _ { \mathrm { ~ n ~ } }$ 级的噪声系数和增益。由公式可知，低噪声放大器的整体噪声性能主要取决于第一级的噪声系数，后级的噪声可通过前级的高增益加以抑制。在对噪声性能要求比较高的射电天文接收系统中，通常会用噪声温度 $T _ { e }$ 来表征其噪声性能。噪声温度与噪声系数的转换关系为：

$$
T _ { e } ( K ) = T _ { 0 } ^ { } * ( 1 0 ^ { \frac { N F ( d B ) } { 1 0 } } - 1 ) \ , T _ { 0 } = 2 9 0 K
$$

晶体管的选择要兼顾噪声、增益以及驻波比的特性。根据FUKUI建立的MESFET最小噪声模型[3]

![](images/e1152662cabe08ec331b69eef238716ce025c46d7736922c2fe776dd7da0222f.jpg)  
图1GaAsMESFET器件噪声等效电路图  
Fig.1 Noise equivalent circuit of GaAs MESFET

$$
N F _ { \mathrm { m i n } } \left( d B \right) = 1 0 1 \mathrm { g } ( 1 + \frac { 2 . 5 f } { f _ { T } } \sqrt { g _ { m } ( R _ { g } + R _ { s } ) } )
$$

同时，对于单指晶体管：

$$
R _ { g } = R _ { g 0 } \times W
$$

对于多指晶体管：

$$
R _ { g } = R _ { g 0 } \times \frac { W } { N _ { b d } ^ { 2 } }
$$

其中， $f _ { T }$ 为晶体管的截止频率， $g _ { \scriptscriptstyle m }$ 为跨导， $R _ { g }$ 栅极金属层总电阻， $R _ { g 0 }$ 为单位宽度栅极金属层电阻，W为晶体管总栅宽， $N _ { b d }$ 为栅指数， $C _ { g s }$ 为栅源极间等效电容， $R _ { s }$ 为源极串联电阻。

![](images/bf0ef594b489dcfab2f5c3b6eab6414effc30cc56aa0d624e7026f7815bcd930.jpg)  
图2单指和多指晶体管版图  
Fig.2 Transistors with single finger and multiple fingers

由（3）～（5）式可知，晶体管最小噪声系数 $N F _ { \mathrm { m i n } }$ 与栅宽、栅指数均有关，且其与总栅宽呈正相关，与栅指数的平方呈负相关，故 $N F _ { \mathrm { m i n } }$ 随栅指数变化的幅度较栅宽大。利用ADS 仿真软件仿真对比OMMIC 提供的元件库中 $2 \times 5 0 ~ { \mu \mathrm { m } }$ 和 $4 { \times } 2 5 ~  { \mu \mathrm { m } }$ 总栅宽为 $1 0 0 \mu \mathrm { m }$ 以及$2 { \times } 1 2 0 ~ { \mu } \mathrm { m }$ 和 $4 { \times } 6 0 \mu \mathrm { m }$ 总栅宽为 $2 4 0 \mu \mathrm { m }$ 四种不同尺寸的小信号模型晶体管在相同偏压下的增益和最小噪声系数。从图3中可以地看到，在总栅宽相同时，2指的晶体管高频增益优于4指，而噪声系数是4指优于2指。当总栅宽增大时，低频增益提高，且随着频率升高增益下降幅度大。同时噪声系数在少指（2指）与多指（4指）之间的差异在高频处更为明显，而增益相差无几。根据高增益、低噪声的指标要求，本文的设计中选用了尺寸为 $4 { \times } 6 0 \mu \mathrm { m }$ 的晶体管。

![](images/0cf5face8fe98ad3e6d8ad7526d097ba6a9b6e7ac78eeb892694653e9b248b7e.jpg)  
图3四种不同尺寸晶体管性能对比  
Fig.3Performance comparison of four different size transistors:(a) Gain (b)Minimum noise figure

# 2.2 稳定性

射频电路中的有源和无源器件都属于双向元件，所以在有源电路输出端的匹配阻抗会通过晶体管的反向传输系数 $S _ { 1 2 }$ 反射回输入端，若反射的信号与由信号源输入的信号同相时，有可能会造成放大器电路震荡[4]。稳定性决定了设计的LNA 是否能正常工作，所以对稳定

性的分析也是设计MMICLNA时不可忽略的环节。1962年，Rollett提出了K指数法则来判断电路的稳定性：

$$
K = \frac { 1 - \left| S _ { 1 1 } \right| ^ { 2 } - \left| S _ { 2 2 } \right| ^ { 2 } + \left| \Delta \right| ^ { 2 } } { 2 \left| S _ { 1 2 } S _ { 2 1 } \right| } , \Delta = S _ { 1 1 } S _ { 2 2 } - S _ { 1 2 } S _ { 2 1 }
$$

只有在全频带内 $K > 1$ 且 $\left| \Delta \right| < 1$ 时，系统才能称之为绝对稳定，此时放大器的状态不会随信号源阻抗和负载阻抗变化而发生变化，也不会在输入信号后产生自激振荡。在晶体管源极与地之间串接反馈电感的方式可以改善LNA稳定性，而在实际在进行电路设计时，通常用微带线代替电感引入少量感性阻抗，既能满足稳定性要求，也方便电路优化。

# 2.3直流偏置电路

直流偏置电路关系到放大器是否能在选定的静态工作点下工作，而不同的静态工作点下晶体管的噪声特性、增益等都有区别。HEMT 常用的直流偏置类型有单电源供电和双电源供电两种方式。图4的单电源供电拓扑结构中，源极通过负反馈电阻将源端电位调节到所需的电压值，不可避免的会消耗直流功率，降低放大器工作效率。

![](images/83f41fe8476aaec9f95892a6b8af8177bdb604541e68764dbd94deaf01c79d3f.jpg)  
图4单电源直流偏置电路拓扑结构  
Fig.4 Single power supply DC bias circuit structure

设计低噪声放大器常用图5所示的双电源供电拓扑结构，其中电感可以防止射频信号进入直流偏置电路，保证电路的稳定性。但是仅仅依靠电感作为射频扼流圈无法完全隔离射频信号，因此为了防止少量射频信号进入直流电源造成电路振荡，通常还需要并联去耦电容以进一步吸收射频信号；输入、输出端常采用隔直电容来防止偏置电路中的直流分量进入射频信号。本文设计的电路中，晶体管所加漏极偏压 $V _ { d }$ 为正电压，栅极偏压 $V _ { g }$ 为负电压以控制漏极电流。值得注意的问题是，双电源供电结构需严格控制加电、去电顺序，否则容易造成晶体管由于瞬间超压而损毁。

![](images/b0f415149eb0cb574a2cf16d16995d41dd20790b91f955f7f0f69dd1a824c3c5.jpg)  
图5双电源直流偏置电路拓扑结构  
Fig.5 Dual power supply DC bias circuit structure

# 2.4匹配电路

匹配电路可调节整个LNA 的噪声、增益及其平坦度和输入输出回波损耗。设计 LNA的匹配电路需要考虑输入匹配、级间匹配和输出匹配，从前面对噪声的分析可知，第一级电路的噪声系数对整个LNA的噪声性能起决定性作用，所以输入匹配采用最佳噪声阻抗匹配方式。级间匹配主要采用最大功率增益匹配来保证电路有足够高的增益，而输出匹配采用最大增益输出匹配方式，同时要考虑输出回波损耗和增益平坦度。各个重要参数之间的变化通常是相互影响、相互牵绊的，所以设计电路时还需要根据实际的指标要求进行取舍。

# 2.5原理图和版图设计

为了满足增益指标要求，LNA芯片采用三级级联放大拓扑结构，直流偏置为双电源供电，三级晶体管采用同一 $\mathrm { \Delta V _ { d } }$ 提供漏极正偏压，同一 $\mathrm { v _ { g } }$ 提供栅极负偏压。由于晶体管的噪声随着频率而增加，使第一级、第二级、第三级电路分别控制高频、中频和低频增益，如此可保证工作带宽内增益和噪声的平坦度。本文设计的 2-18GHz 低噪声放大器芯片电路拓扑结构如图6所示。射频信号从左端输入，先要经过一个大的隔直电容滤除直流杂波，降低噪声。栅极偏压通过大台面电阻给晶体管提供控制电压，防止射频信号进入直接接地造成短路。漏极供电电路上的电感和电阻不仅起到防止射频信号进入直流电源的作用，其数值对增益和增益平坦度的调节也有非常显著的效果，同时第一级的电阻还会对电路的噪声产生影响。源极串接电感可以提高电路的稳定性，对第一级来说，电感值越大稳定性越高，同时噪声也会越大，故为了保证整个电路的噪声性能，尽量取较小的电感值，此时可用一小段微带线来替代。级间电容、电感元件除了作为匹配电路的一部分，还能帮助调整增益、噪声和回波损耗的形状。

![](images/caf9a62c4cecd09347aa64906e40476b11ef229e1c3c14b1417946bd4bbdad05.jpg)  
图6低噪声放大器电路拓扑结构

芯片版图的设计要符合半导体公司的DRC（DesignRuleChecking），还要整洁美观紧凑，节省面积，在电路出现问题时方便排查。同时，为了充分利用版图面积和增加电路的稳定性，在直流偏置的路径上尽可能并联上bypass 电容滤除多次谐波。图7为最终流片获得的 MMICLNA芯片实物图片，芯片面积为 $2 \mathrm { m m } \times 1 \mathrm { m m }$ 。

![](images/10fd7d32f8e22505bb53f1c2c8d89a760cc0a356565430b03c1470d8d5bbc113.jpg)  
Fig.6 The LNA circuit schematic   
图7低噪声放大器芯片实物图  
Fig.7Microphotograph ofLNAMMIC

# 3 常温在片测量结果

常温下，采用微波探针台和矢量网络分析仪等在片测量仪器对LNA芯片进行测量，在进行多组偏压测量调试之后，得到芯片最佳工作状态下的偏压条件为： $\mathrm { V } _ { \mathrm { d } } { = } 2 \mathrm { V }$ ， $\mathrm { I _ { d } } { = } 7 5 ~ \mathrm { m A }$ 。

此时放大器芯片的增益大于 $2 8 \mathrm { d B }$ ，输出回波损耗大于 $1 3 \mathrm { d B }$ ，噪声温度83K\~108K。将LNA芯片S参数和噪声温度的在片测量结果与电磁仿真结果进行对比，图8、图9中虚线为仿真结果，实线为测量结果。从对比图中可以看到，该LNA芯片的反射系数实测和仿真差别不大，而噪声温度在低频处差别较大。造成噪声升高的可能原因有：噪声校准或噪声源本身精确度不够；测量过程使用的探针造成源阻抗匹配效果出现波动；仿真所用噪声模型在低频段不准确等。除了噪声温度差异之外，高频增益也有很明显的抬高现象，不排除元件电磁仿真模型与实际工艺的误差。另外，输入回波损耗与噪声在调节输入匹配时难以同时达到最优，在本次设计中，为了获得低噪声而牺牲了一定的输入回波损耗，故 $\mathbf { S } _ { 1 1 }$ 在低频段略差。

![](images/12c8edba46653a688915791e712f3ac29f346ca4d8227f39fd4aa61303551750.jpg)  
图8S参数仿真与实测对比  
Fig.8 Comparison between simulated and on-wafer measured S-parameter

![](images/11029783bc2996083988fdd779918194b58b985d727dd0ecec16865475bb9e92.jpg)  
图9噪声温度仿真与实测对比图  
Fig.9 Comparison between simulated and on-wafer mesured noise temperature

本文与其他文献中相似频段的低噪声放大器芯片的部分参数对比如表1所示。罗马维尔塔塔大学 W.Ciccognani、美国诺斯罗普格鲁曼航空系统公司 Shih-En Shih 和韩国光云大学Jang-Hoon Han 等人的文献中采用的是 $\cdot$ GaN HEMT工艺[7-9]，俄国托木斯克国立大学Dobush 和南京邮电大学张会等人的文献则是采用 $0 . 1 5 \mu \mathrm { m }$ GaAs pHEMT工艺[10]。由表中数据可以看到，本文设计的低噪声放大器芯片在噪声、增益、直流功耗方面具有一定的优势。

表1本文与其他文献中的低噪声放大器芯片主要参数对比  
Table 1 Main parameters comparison of LNA in this paper and others   

<html><body><table><tr><td>参数 作者</td><td>W.Ciccognani</td><td>Shih-En Shih</td><td>Jang-Hoon Han</td><td>Dobush</td><td>张会</td><td>本人</td></tr><tr><td>工作频率 /GHz</td><td>2-18</td><td>1.2-18</td><td>2-12</td><td>2-18</td><td>3-15</td><td>2-18</td></tr></table></body></html>

<html><body><table><tr><td>噪声温度</td><td>438</td><td>226</td><td>250</td><td>170</td><td>190</td><td></td><td>93</td></tr><tr><td>(平均值） /K</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>增益</td><td></td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>(平均值) /dB</td><td>23.3</td><td>13.3</td><td>16</td><td>11</td><td>31</td><td></td><td>32</td></tr><tr><td>直流功耗 /mW</td><td>12x10³</td><td>500</td><td>1.4×10³</td><td></td><td>200</td><td></td><td>150</td></tr><tr><td>面积/mm²</td><td>2.9x3.8</td><td>2.3×1.4</td><td>2.9×1</td><td>1.3x0.7</td><td></td><td>2x1</td><td>2x1</td></tr></table></body></html>

4结论

本文采用OMMIC公司70nmGaAsmHEMT工艺设计了一款2-18GHz超宽带单片微波集成低噪声放大器芯片。该芯片电路采用三级级联放大、单管共源和双电源供电结构，根据最优噪声输入匹配和最大功率输出匹配进行设计，并在输入回波损耗和噪声性能两者中进行了一定的取舍。其在 $\mathrm { V } _ { \mathrm { d } } { = } 2 \mathrm { V }$ ， $\mathrm { I _ { d } } { = } 7 5 ~ \mathrm { m A }$ 的偏压下获得了大于28dB 的增益，小于108K的噪声温度及良好的输出匹配。本文设计的超宽带低噪声放大器芯片可以用于国际上正在开展的超宽带接收机研究，具有代表性的是国际天文组织IVS（InternationalVLBIService）正在推动的 2-14GHz 下一代全球大地测量观测系统 VGOS（GlobalVLBIObservationSystem）和欧洲VLBI网正在推动的1.5-15.5GHz下一代VLBI观测系统。

参考文献:

[1]黎明.砷化镓基mHEMT器件与电路研究[D].北京:中国科学院微电子研究所,2009:1-4.[2]孙昕.Ka 宽带 MMIC 低噪声放大器研究[D].北京:中国科学院大学,2017:18-19.[3]HATSUAKI FUKUI.Optimal noise figure of microwave GaAsMESFET's[J].IEEE.Transactions on electron devices,1979,26(7):1033-1037.[4]张盛富,戴明凤.射频晶片模组设计[M].台湾:全华图书股份有限公司,2008:83.[5] J.Rollet.Stability and power gain invariants of linear two-ports[J].IRE Transaction on CircuitTheory,1962:29-32.

[6]《中国集成电路大全》编委会.微波集成电路[M].北京:国防工业出版社，1995:24-80.

[7] W.Ciccognani,E.Limiti,P.E.Longhi.An ultra-broadband robust LNA for defense applications in AlGaN/GaN technology[J]. IEEE MTT-S International Microwave Symposium,2010:23-28.

[8] Shih-En Shih,William R.Deal,Derrick M.Yamauchi.Design and analtsis of ultra wideband GaN dual-gate HEMT low-noise amplifiers[C].IEEE Transactions on Microwave Theory and Techniques,2009(57):3270-3277.

[9]Jang-Hoon Han,Jeong-Geun Kim.A S/C/X-Band GaN Low Noise Amplifier MMIC[J],The Journal of Korean Institute of Electromagnetic Engineering and Science,2017,28(5):430-433.

[10] Dobush I.M.,SamuilovA.A.,KalentyevA.A..Design of2-18GHz MMIC lownoise amplifier[C].Microwave and Telecommunication Technolog,2013:151-152.

[11]张会,钱国明.基于 $0 . 1 5 \mu \mathrm { m }$ pHEMT的超宽带低噪声放大器[J].微电子学,2017(47):478-482.

Zhang Hui,Qian Guoming.An Ultra Wideband 0. 15μm pHEMT Low Noise (mplifier[J].Microelectronics,2017(47):478-482.

# Design of 2-18GHz Ultra-wideband Low Noise Amplifier

Wen Xiaomin1,2，Li Bing

(1.Shanghai Astronomical Observatory,Chinese Academy Sciences,Shanghai 2Ooo30,China; 2.University of Chinese Academy Sciences,Beijing 10oo49,China,Email:wxm@ shao.ac.cn)

Abstract: Low-noise amplifier isthe important componentin radio astronomical front-end. It will affectthe sensitivity of receiving system directly. In this paper,an ultra-wideband monolithic microwave integrated low noise amplifier based on $7 0 \mathrm { n m }$ GaAs mHEMT process from OMMIC has been designed. The 2-18GHzfrequency coverage of MMIC LNA covers traditional four astronomical bands, such as S-,C-，X- and $\mathtt { K u }$ -band.It is suitable for the application on the ultra-wideband receiver development for centimeter wave length,and ultra-broadband IF amplifier module for millimeter wave length astronomy.With the DC power dissipation of $1 5 0 \mathrm { m W }$ ,the measured results show that the 3-stage MMIC LNA achieved the gain over 28dB,and the average noise temperature is about 93K.The chip size is $2 \mathrm { m m } \times 1 \mathrm { m m }$

Key words:Low noise amplifier;GaAs mHEMT;Ultra-wideband;MMIC