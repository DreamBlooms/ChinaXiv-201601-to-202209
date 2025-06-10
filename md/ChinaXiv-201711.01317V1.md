# 一种 $5 5 { \sim } 6 5 ~ \mathrm { M H z }$ 频段射电天文天线阵接收机的设计

董亮1,2,3，姜涛4，周绍红4，汪敏1,²，刘俊卿2,3，郭少杰1,2（1.中国科学院云南天文台，云南 昆明650011；2.云南大学-云南天文台信息技术联合实验室，云南 昆明 650001;3.云南大学信息学院，云南 昆明650001；4.云南师范大学物理电子学院，云南 昆明650092)

摘要： $3 0 { \sim } 3 0 0 ~ \mathrm { M H z }$ 的低频段陆基天线阵是重要的射电观测设备，在该频段进行射电观测面临无线电环境复杂、天空背景温度高等特点。介绍了一种基于微波芯片设计的新型低频段模拟接收机。接收机由初级带通滤波器( $ { \langle 3 0 \mathrm { \sim } 7 0 ~ }  { \mathrm { M H z } } ^ { \cdot }$ ）、初级放大器、次级带通滤波器( $5 5 \sim$ $6 5 ~ \mathrm { M H z }$ ）、 ${ 1 8 0 } ^ { \circ }$ 移相器、两个次级放大器组成。在测试云南天文台短波段无线电环境的基础上，接收机实现了对 $5 5 { \sim } 6 5 ~ \mathrm { M H z }$ 可观测频段的选通和放大，整机噪声约为 $3 2 0 \mathrm { K }$ ，增益63dB左右。同时作为中国射电天文低频阵前期研究的一部分，由于采用单片微波集成电路（MonolithicMicrowave Integrated Circuit，MMIC)芯片，接收机具有体积小、成本低、易于量产等特点。

关键词：低频段；MMIC芯片；模拟接收机中图分类号：P162 文献标识码：A 文章编号：1672-7673(2017)02-0157-07

天体的电磁辐射反映了辐射体的重要特性和状态，射电观测是研究包括太阳、地球、行星及太阳系外天体的一种十分重要的手段。频率在 $8 0 ~ \mathrm { M H z }$ 以下的低频段射电辐射在太阳系内提供了大量关于太阳、行星射电和爆发的信息，而且对太阳系以外天体的射电观测，低频段不是现在人类已经能够观测的电磁波段的简单外推，而是一个具有重大意义和重要地位的探索空间。这是因为这个频率范围基本还没有进行过具有有效空间分辨率的观测，人类对宇宙在这个频段的了解基本空白。有很多天文现象只有在低频段才能探测到，预计科学探测内容包括：木星电离层和磁层射电低频段辐射及木星射电爆发；低频和低频段脉冲星辐射、辐射跳变；太阳日冕物质抛射和射电爆；银河系低频段大尺度高分辨率辐射特性；银河电离氢分布勘测；瞬变天体时变频率特性研究等。如图1，低频段具有丰富的天体现象和辐射[1-6]。

（1）日冕物质抛射初始阶段实时动态监测

以超本地AIfven速度运动日冕物质抛射将产生激波，从而激发ⅡI型爆发。与此同时，激波还会加速电子，形成特殊的激波加速III型爆发(III-I)）。此外，日冕物质抛射本身是磁束缚的一团等离子体，会产生热(回旋共振辐射)和非热辐射(回旋同步辐射)。因此，对ⅡI型、I-I、IV型爆发以及日冕物质抛射本身的热/非热辐射的成像观测，将成为对日冕物质抛射初始阶段动态实时监测的有力工具。

# (2）日冕和行星际激波的诊断

日冕物质抛射从触发到加速向外运动，由于起始速度为0，要达到甚至超过当地的Alfven速度需要一段时间并达到一定高度。低频射电成像观测可能揭示Ⅱ型爆发和日冕激波的精确关系。如通过对Ⅱ型爆发的频率、时间、位置成像，配合光学观测，将得到一幅磁流体动力学激波和喷流、日冕物质抛射或爆炸波的相对位置[7]。

（3)日冕能量释放及粒子加速

由于射电观测对靠近或在其中的非热电子产生的等离子体辐射和非热回旋同步辐射敏感，因此，射电成像观测是发现日冕能量释放发生在何时、何地的最好手段。低频成像观测瞄准可能的在中高层日冕的能量释放区，可以对III型爆发做光谱成像观测，由于IⅢ型爆发由高能电子束流沿磁场线运动所致，因此，还可以标志电子束流的位置和轨迹。结合对Ⅱ型爆发的观测，可以解决电子束流的加速者是耀斑还是激波的问题，还可以构成II、II和IV型爆发在时间域、频率域和空间域的相互关系，将为太阳高能粒子事件的起源提供重要探测手段[7]。

# (4)空间天气预警预报

太阳低频射电阵列可以构成在0.5\~2.5个太阳半径范围内，对高能电子/粒子、日冕激波和日冕磁场结构的监测[8]，特别是对朝向地球的高能粒子和激波。它可以在地磁暴发生前数天，预警朝向地球的日冕物质抛射。此外，可以对该范围日冕特征参数，如温度、密度、磁场给出定量的估计，这为空间天气实时预警预报提供了最直接的依据。

对于射电天文的观测，天空背景温度非常高，如图1，可以达到几千甚至上万K，在低频射电观测时达到一定灵敏度，必须通过增加天线有效接收面积的方法。但是低频段的振子天线，有效接收面积有限，很难达到观测要求的灵敏度。低频射电观测必须通过多天线组阵的方式增加有效接收面积[9]。

![](images/ceaefe90d3622facaf130bae20b7dbf0b8d2803dcd09426512326082ff2f9bd8.jpg)  
图1云南天文台 $0 { \sim } 1 4 0 ~ \mathrm { M H z }$ 频段无线电环境图  
Fig.1The radio environment of $0 { - } 1 4 0 \mathrm { M H z }$ band in Yunnan Observatories site

国际上长期以来只有为数不多的天文台在进行低频段射电天文常规观测，如乌克兰的UTR-2天线阵、法国南希天文台、日本东北大学低频干涉阵、美国弗罗里达天文台和夏威夷天文台等。这些天文台目前的空间分辨本领在木星距离上不足 $1 0 ^ { \prime }$ 。目前它们和建设中的低频观测阵（Low-FrequencyArray）和平方千米阵列望远镜（Square Kilo-metre Array）可以提供低频段宽带观测，但是还没有系统开展干涉测量观测，尚未达到建立太阳日冕物质抛射射电辐设模型和木星射电辐射机制模型的能力[4]。为此发展我国自主的陆基低频射电观测网具有非常重大的意义。

进行低频射电相关观测，首先必须进行单站建设和初步观测，单站关键技术问题的设计至关重要。中国科学院云南天文台作为我国陆基低频射电观测网的重要成员，提出研制低频段单观测站关键技术的研究。本文介绍云南天文台在低频段的接收机电路的研发，接收机采用先进的MMIC 微波芯片技术作为设计核心，大大降低了设计成本，提高了系统的集成度和稳定性。

# 1低频频段无线电环境的测量、分析

云南天文台本部位于云南省昆明市东郊，随着无线电技术特别是短波通信技术的发展，低频段无线电干扰是该波段射电观测中不可回避的一个问题，为此研究组利用已有的低频倒V天线进行了无线电环境的测试，测试结果见图1，频带内主要存在的干扰见表1\~2。

表1 ${ \bf 7 5 } \sim { \bf 1 1 0 ~ M H z }$ ，其中离观测带宽比较近的几个强干扰  

<html><body><table><tr><td rowspan="2">干扰频点 /MHz</td><td rowspan="2">强度/dBm （RBW=30 kHz, Atten=OdB，avg=0)</td><td rowspan="2">干扰频点 /MHz</td><td rowspan="2">强度/dBm （RBW=30 kHz,</td></tr><tr><td>Atten=O dB，avg=0)</td></tr><tr><td>77.0</td><td>-61.41</td><td>95.2</td><td>-39.82</td></tr><tr><td>81.2</td><td>-67.47</td><td>97.0</td><td>-37.38</td></tr><tr><td>88.5</td><td>-37. 03</td><td>99.0</td><td>-55.72</td></tr><tr><td>91.8</td><td>-32.99</td><td>105.7</td><td>-34.88</td></tr></table></body></html>

Table1Several strong RFI（radio frequency interferences ) in the 75-11oMHz band near observation band   
表2 $\mathbf { 1 0 } { \sim } 3 0 \mathbf { M H z }$ ，主要无线电干扰 Table 2Several strong RFI in the 10-30MHzband   

<html><body><table><tr><td>干扰频点</td><td>强度/dBm</td></tr><tr><td>/MHz</td><td>（RBW=30 kHz,</td></tr><tr><td></td><td>Atten=O dB，avg=0)</td></tr><tr><td>23.1</td><td>-71. 43</td></tr><tr><td>21.4</td><td>-55.98</td></tr><tr><td>17.5</td><td>-50.23</td></tr><tr><td>15.4</td><td>-41.8</td></tr><tr><td>13.6</td><td>-43.38</td></tr><tr><td>11. 5</td><td>-50. 65</td></tr></table></body></html>

# 2接收机的设计方案

为了规避调频广播和长波电台干扰，选通有效的初步试验“干净”频带，同时由于 ${ 1 0 0 } \mathrm { M H z }$ 以下频段的天空的高噪声背景和无线电环境的不确定性，选择具有高线性动态范围的放大器。基于上述思想，接收机设计原理如图2。

![](images/19cf6fbbd30147d5fbeefe8830976a406f1db7674fb7c2f0dd1a7d344768864e.jpg)  
图2整体系统结构图  
Fig.2The whole system structure chart

首先采用较宽带的带通滤波器MMIC芯片BPF- $\mathrm { C } 4 5 +$ ，选通 $3 0 { \sim } 7 0 ~ \mathrm { M H z }$ 的通带，同时抑制带外强干扰，而后对初步选通的频带由一片Gali $- 7 4 + \mathrm { M M I C }$ ，Gali $^ { . 7 4 + }$ 具有良好的线性动态范围和放大倍数，主要指标如下：

(1) $1 0 0 \ : \mathrm { M H z }$ 时增益为25.1dB；  
(2) $1 0 0 \mathrm { M H z }$ 时的3dB 压缩点 $I P _ { 3 } = 3 8 ~ \mathrm { d B m W }$ ：  
(3) $1 0 0 \mathrm { M H z }$ 时的1dB 压缩点 $I P _ { 1 } = 1 8 . 0 \sim 1 9 . 2 \mathrm { d B m W }$   
(4)典型噪声系数 $N F { = } 2 . 7 ~ \mathrm { d B }$ ，在常温下约合 $2 0 0 \mathrm { K }$ 噪声温度;

经Gali $^ { . 7 4 + }$ 放大后的信号，通过滤波器芯片BPF- ${ \cdot } \mathrm { A } 6 0 { + }$ ，选通 $5 5 { \sim } 6 5 ~ \mathrm { M H z }$ 带内信号，考虑到BPF-$^ { 6 0 + }$ 的阻带抑制效果好，但是插入损耗较大，综合考虑将其作为第2级滤波器比较合理。经 BPF- ${ \cdot 6 0 + }$ 滤波后的信号，通过一个 ${ 1 8 0 } ^ { \circ }$ 移相合成器T1-1-KK81+将来自两臂的信号进行平衡-不平衡转换，形成一路非平衡信号。接收机各元器件参数如表3，同时表4列出了经第1级滤波器后带外干扰的电平情况，确保了后级放大器不会饱和。

Table 3The index of the receiver's components   

<html><body><table><tr><td>器件名称</td><td>增益/dB</td><td>插入损耗/噪声系数/dB</td><td>作用</td></tr><tr><td>BPF-C45+</td><td>0</td><td>0.44@ 60 MHz</td><td>第一级滤波</td></tr><tr><td>Gali-74+</td><td>25.10@100 MHz</td><td>2.7@100 MHz</td><td>第一级放大</td></tr><tr><td>BPF-A60+</td><td>0</td><td>2.16@ 60 MHz</td><td>次级滤波</td></tr><tr><td>T1-1-KK81+</td><td>0</td><td>0. 64@ 50 MHz</td><td>信号移相合成</td></tr><tr><td>Gali-74+</td><td>25.10@100 MHz</td><td>2.7@ 100 MHz</td><td>次级放大</td></tr></table></body></html>

总增益约： $6 3 ~ \mathrm { d B }$ ，总噪声系数约：3.2dB，折合噪声温度约为316K（常温下)

表3接收机各元器件指标一览表  
表4几个最强影响的无线电干扰信号接收机内部经过第一级滤波器后电平一览表  
Table 4Some strong RFI signals’voltage levels after being filtered by the primary filter   

<html><body><table><tr><td>频率/MHz</td><td>入口电平/dBm</td><td>BPF-C45+</td><td>噪声电平@-83dBm 是否低于噪声电平</td></tr><tr><td>77. 0</td><td>-61</td><td>-97</td><td>低于</td></tr><tr><td>81.2</td><td>-67</td><td>-107</td><td>低于</td></tr><tr><td>88.5</td><td>-37</td><td>-87</td><td>低于</td></tr><tr><td>91. 8</td><td>-32</td><td>-92</td><td>低于</td></tr><tr><td>23.1</td><td>-71</td><td>-120</td><td>低于</td></tr></table></body></html>

基于protel99 SE 软件设计的电路如图3。经过焊接制成电路板成品图如图4。

# 3测试结果

整个接收机通带测量结果如图5。其中带内3点的增益在 $6 3 . 5 6 ~ \mathrm { d B } \sim 6 3 . 9 3 ~ \mathrm { d B }$ 之间，带内起伏小于 $\pm 0 . 3 \mathrm { d B }$ 。同时带外主要干扰的抑制除了 $7 7 ~ \mathrm { M H z } ~ 2 5 ~ \mathrm { d B }$ 增益以外，其余频点的抑制度均在-30dB以上，达到设计指标。将接收机接入天线进行初步观测结果如图6。加放大器后形成 $5 5 \sim 6 5 ~ \mathrm { M H z }$ 通带，其余无线电干扰信号得到很好的抑制，无饱和现象。

![](images/3a2430e4376d3d2c0d74a288aff15e0a28bb4adda488f6cd6bc0e91f61c772d4.jpg)  
图3电路原理图

![](images/f9a719d69ce1115a72793bb8fb8f02d6e1cd3587ae54267ba538b8f4dcb070b0.jpg)  
Fig.3Schematic circuit diagram   
图4接收机成品图  
Fig.4Receiver finished product figure

![](images/901738c13b3d7947b23d3e01e7d73def5342401c1c38eb2c5a3746eb62f43e15.jpg)  
Fig.5The testing pass band graph of analog receiver

![](images/e7aaf14522b29231bb34cc3b419ee142f92befff02cab1398e393cff6a99b0ea.jpg)  
图5模拟接收机测试通带图  
图6初步的试观测频谱图 Fig.6The observation spectrograph

# 4总结

云南天文台开展的低频天线阵建设，目前已经初步完成 $2 \times 2$ 子阵建设，包括天文台本部两个子阵，云南大学呈贡校区一个子阵，下一步在此基础上进行跟踪观测实验和双站干涉测量实验。

# 参考文献：

[1] Van Weeren R J,Rotgering HJA，Rafferty DA，et al.First LOFAR observations at very low frequencies of cluster-scale non-thermal emission:the case of Abell 2256 ［J].Astronomy & Astrophysics，2012，543:A43-A55.   
[2] Oberoi D,Kasper J C.LOFAR: the potential for solar and space weather studies [J]. Planetary and Space Science，2004，52(15）:1415-1421.   
[3] Cohen A S，Lane W M，Coton W D，et al. The VLA Low-frequency Sky Survey [J].The Astronomical Journal，2007，134(3）:1245-1262.   
[4] Van Haarlem MP，Wise M W,Gunst A W,et al.LOFAR: the low-frequency arry [J]. Astronomy & Astrophysics，2013，556:A2-A54.   
[5] Schellrt P，Nelles A，Buitink S，et al. Detecting cosmic rays with the LOFAR radio telescope [J].Astronomy & Astrophysics，2013，560：A98-A111.   
[6] 姜碧涝.射电天文工具［M].北京：北京师范大学出版社，2008：25-26.   
[7] 赵仁杨，金声振，傅其骏．太阳射电微波爆发［M]．北京：科学教育出版社，1997：98- 110.   
[8] Zaqarashvili TV，Melnik VN，Brazhenko AI,et al.Radio seismology of the outer solar corona [J].Astronomy & Astrophysics，2013，555:A55-A66.   
[9] Morosan D E,Gallagher P T, Zucca P，et al. LOFAR tied-array imaging of type III solar radio bursts ［J].Astronomy & Astrophysics，2014，568：A67-A74.

# An Analog Receiver Designing of 55-65MHz Band Radio Astronomy Observation

Dong Liang $^ { 1 , 2 , 3 }$ ， Jiang Tao $^ 4$ ， Zhou Shaohong4，Wang Min $^ { 1 , 2 }$ ， Liu Junqing $^ { 2 , 3 }$ ， Guo Shaojie $^ { 1 , 2 }$ (1.Yunnan Observatories，Chinese Academy of Sciences，Kunming，65ool1,China，Email:dongliang@ynao.ac.cn; 2.Yunnan University-Yunnan Observatories Information Technology UnitedLaboratory，Kunming 65ooo1,China; 3.Information College of Yunnan University，Kunming 65ooo1，China； 4.The Schoolof Physicsand Electronic Information Technology，Yunnan Normal University，Kunming 650092,China)

Abstract：The Ground-based antenna arrays are important radio observation instruments in low（Very High Frequency）band，but in this band，the observations have to face thebad radio environments and the high sky temperature.In this paper，we introduce anew kind of analog receiver working in low band based on the MMIC（Microwave Monolithic Integrated Circuit）chips.This receiver consists of primary band pas filter, primary amplifier，secondary band pas filter，18O degree phase shifter and two secondary primary amplifiers. Based on the radio environment testing results in the Yunnan observation site，this analog receiver achieves band passing and amplifying for the observation band from $5 5 - 6 5 \mathrm { M H z }$ ，and this receiver's system noise temperature is nearly 32OK,the gain is nearly 63dB.At the same time,as a part of the Chinese low frequency band observation net，based onthe MMIC technologies，this receiver has smaller volume，lower price and is easy to copy.

Key words: Low frequency band；MMIC chips；Analog receiver