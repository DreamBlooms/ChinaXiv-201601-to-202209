# 三线圈无线输电系统的频率分裂特性和抑制方法

路倩云」 王文清² 翟志颖 田子建1（1.中国矿业大学机电与信息工程学院 北京1000832.北京工业职业技术学院北京100042）

![](images/e7fad10fca4fa0dc8418902c7a3dd41827ada316ad98f09d89f1d9fe08350a07.jpg)

路倩云女 1992年生，硕士研究生，研究方向为无线输电。

摘要：首先以基尔霍夫定律为基础，分析三线圈WPT系统的S参数、传输效率以及该系统的频率分裂现象。频率分裂现象是线圈之间的过耦合导致系统出现不止一个谐振频率的现象。频率分裂仅出现在过耦合区域，由于在过耦合区域内阻与系统的输入阻抗不匹配导致频率分裂现象，本文提出一种阻抗匹配方法来抑制该现象。通过在发射端添加L型阻抗匹配网络并且在接收端组成概念性阻抗匹配网络，来实现抑制频率分裂现象、增大系统效率的目的。最后，通过实验和仿真来对比分析所提方法的正确性。

关键词：三线圈无线电能传输系统磁耦合谐振式频率分裂阻抗匹配 中图分类号：TM72

# Frequency Splitting Characteristics and Suppression Method of Three-Coil Wireless Transmission System

![](images/eee7fe0c035524be6423c9310298acbf57cc0d4168123c1a03f542014ce5ca8d.jpg)

王文清男 1963年生，教授级高工，研究方向为智能仪表。

Lu Qianyun'Wang Wenqing²Zhai Zhiying1Tian Zijian' (1. China University of Mining and TechnologyBeijing 100083 China) (2.Beijing Polytechnic College Beijing100042 China ）

Abstract: Based on the Kirchhoff law, the S-parameters, the transmission efficiency and the frequency division of the three-coil WPT system are analyzed. The phenomenon of frequency spliting is that the over-coupling between the coils causes the system to appear more than one resonant frequency. The frequency splitting occurs only in the over-coupled region. Since the internal impedance of the over-coupling region does not match the input impedance of the system,the frequency spliting phenomenon is proposed. Therefore,an impedance matching method is proposed to suppress the frequency splitting phenomenon. By adding an L-shaped impedance matching network at the transmitter and forming a conceptual impedance matching network at the receiving end, the purpose of suppressing the frequency spliting and increasing the efciency of the system is realized. Finally, the correctness of the proposed method is compared by experiment and simulation.

Keywords: Three coil WPT system, magnetic resonance coupling, frequency splitting, impedance matching

# 1 引言

目前人类的输电方式主要是有线输电，但传统的有线输电方式存在很多问题，比如产生电火花和容易老化等；同时还不能在矿井、水下等特殊环境进行输电。因此实现无线输电是人类的一大梦想。特斯拉在1889 年最早发明了无线输电方法，他使用交流电流和线圈发现了无线白炽灯，但由于距离等各种原因，无线输电技术一直没有很大突破。直到2007年，美国麻省理工学院（MIT）的实验再次掀起了无线输电的研究热潮。他们利用电磁共振原理成功点亮了一个距离电源 $2 \mathrm { m }$ 远的60W灯泡，效率达到 $40 \%$ 。MIT实验的优势在于发射线圈和接收线圈位置的灵活性以及较长的传输距离和较高的传输效率[1-2]。现有的无线电能传输方式有三种：感应式无线电能传输、微波无线电能传输和磁耦合谐振式无线电能传输。其中，感应式无线电能传输距离很近且技术已经比较成熟，目前的手机无线充电都是基于感应式无线输电；微波无线电能传输虽然传输距离远，但由于传输损耗大、传输方向受限制以及对人和生物体有很大危害，因此应用范围存在很大局限；磁耦合谐振式无线电能传输是利用共振原理把能量从发射端传输到接收端，与感应式无线输电相比，以相同频率共振的两个谐振线圈可以在更长的操作距离下以更高的效率有效地交换能量。近年来，中等距离传输的磁耦合谐振式无线输电方式由于在生物医学的移植、移动设备的充电和电动汽车的重复充电等领域的潜在应用而受到了广泛关注[3]。然而，实际环境中的谐振式无线输电方式由于传输距离、阻抗的多样化，很多问题，比如本文将要探讨的频率分裂现象仍然需要解决。

由于频率分裂现象普遍存在于磁耦合谐振式无线输电系统中，因此频率分裂现象的研究对于工作在谐振频率的发射线圈和接收线圈实现高效的能量传输是非常重要的。频率分裂现象发生在过耦合区域，是由于发射线圈和接收线圈之间的过耦合导致系统出现多个谐振频率的现象。人们提出了很多方法来抑制频率分裂。例如，文献[4-6]均是建立了二线圈磁耦合WPT系统并详细分析了频率分裂现象，同时提出了通过改变不同传输距离的负载电阻和电容比，使系统工作在一个稳定的谐振频率，从而避免频率分裂现象的发生一一采用一对非同步的发射线圈和接收线圈以抑制频率分裂现象并获得WPT系统的均匀接收功率。而文献[7]则是对四线圈磁耦合WPT系统的频率分裂现象进行分析，并提出了通过调节负载电阻来抑制频率分裂的方法。上述文献分析大都集中在二线圈和四线圈WPT系统，但三线圈的研究也是非常有必要的。例如在电动汽车无线输电系统中，在原来的发射线圈一侧添加一个线圈构成三线圈无线输电系统，发射线圈和接收线圈之间的距离不变，但提高了电动汽车WPT系统的效率。本文重点研究三线圈的频率分裂现象以及抑制方法。

本文首先研究三线圈磁耦合谐振式无线输电系统的理论基础，得到三线圈WPT系统的S参数、传输效率并分析该系统的频率分裂现象。经分析，得到同等距离时，不同的内阻是影响频率分裂的重要因素。频率分裂仅出现在过耦合区域，在过耦合区域由于内阻与系统的输入阻抗不匹配导致了频率分裂现象。因此，本文提出一种阻抗匹配方法来抑制频率分裂现象。通过在发射端添加L型阻抗匹配网络并且在接收端组成概念性阻抗匹配网络，来实现抑制频率分裂现象、增大系统效率的目的。最后通过实验和仿真来对比分析所提方法的正确性。

# 2 系统建模

磁耦合谐振式无线电能传输系统的基本原理是共振。当发射线圈向一个方向发射一个频率的电磁波时，引起接收回路的共振，使它的谐振幅度达到最大，从而将发射的能量大部分吸收，极大地提高了传输功率和效率。对于三线圈WPT系统，发射端由发射线圈和中继线圈组成，它们之间通过直接耦合的方式进行能量传输；接收端由接收线圈组成。而发射端和接收端则是通过磁场的耦合谐振来实现电能的无线输出。

下面首先分析三线圈WPT系统的理论基础。三线圈磁耦合谐振式无线输电系统是由电路元件L、C、R组成，其电路模型如图1所示。

![](images/7c20b8233f6edfcc39feed6e3eeffe1c93655bd97cb3c09f55d064b44f798299.jpg)  
图1三线圈WPT系统电路模型  
Fig.1Three-coil WPT system circuit model

图中， $V _ { \mathrm { { s } } }$ 为系统的高频功率源； $R _ { \mathrm { s } }$ 为高频功率源的内阻； $R _ { \mathrm { p l } }$ 、 $R _ { \mathfrak { p } 2 }$ 、 $R _ { \mathfrak { p } 3 }$ 分别是发射线圈、中继线圈、接收线圈损耗电阻，因为辐射电阻要远远小于损耗电阻，故本文忽略线圈的辐射电阻； $C _ { 1 }$ ， $C _ { 2 }$ ，$C _ { 3 }$ 分别为对应线圈的等效电容； $L _ { 1 }$ 、 $L _ { 2 }$ 、 $L _ { 3 }$ 分别为对应线圈的等效电感； $R _ { \mathrm { L } }$ 为线圈的负载电阻； $f _ { 0 }$ 为系统谐振频率； $L _ { 1 }$ 与 $L _ { 2 }$ 之间互感为 $M _ { 1 2 }$ ， $L _ { 2 }$ 与 $L _ { 3 }$ 之间互感为 $M _ { 2 3 }$ 。同时为了方便计算，本文忽略发射线圈和接收线圈之间的互感。

接下来分析三线圈WPT系统，由基尔霍夫定律，得

$$
\begin{array} { r l } & { \left\{ Z _ { 1 } I _ { 1 } - \mathrm { j } \omega M _ { _ { 1 2 } } I _ { _ { 2 } } = V _ { _ { \mathrm { S } } } \right. } \\ & { \left\{ Z _ { _ { 2 } } I _ { _ { 2 } } + \mathrm { j } \omega M _ { _ { 1 2 } } I _ { _ { 1 } } - \mathrm { j } \omega M _ { _ { 2 3 } } I _ { _ { 3 } } = 0 \right. } \\ & { \left. \left[ Z _ { _ { 3 } } I _ { _ { 3 } } - \mathrm { j } \omega M _ { _ { 2 3 } } I _ { _ { 2 } } = 0 \right. \right. } \end{array}
$$

其中

$$
\left\{ \begin{array} { l l } { Z _ { 1 } = R _ { \mathrm { s } } + R _ { \mathrm { p } 1 } + \mathrm { j } \omega L _ { 1 } + 1 / \mathrm { \ j } \omega C _ { \mathrm { _ 1 } } } \\ { Z _ { 2 } = R _ { \mathrm { p } 2 } + \mathrm { j } \omega L _ { 2 } + 1 / \mathrm { \ j } \omega C _ { \mathrm { _ 2 } } } \\ { Z _ { 3 } = R _ { \mathrm { L } } + R _ { \mathrm { p } 3 } + \mathrm { j } \omega L _ { 3 } + 1 / \mathrm { \ j } \omega C _ { \mathrm { _ 3 } } } \end{array} \right.
$$

$Z _ { 1 }$ ， $Z _ { 2 }$ 、 $Z _ { 3 }$ 的计算应满足式（2）要求，耦合系数满足下式

$$
0 \leqslant k _ { _ { i j } } = \frac { M _ { _ { i j } } } { \sqrt { L _ { _ { i } } L _ { _ { j } } } } \leqslant 1
$$

系统的 $s$ 参数为

$$
S _ { 2 1 } = 2 { \frac { V _ { \mathrm { L } } } { V _ { \mathrm { s } } } } \Bigg ( { \frac { R _ { \mathrm { s } } } { R _ { \mathrm { L } } } } \Bigg ) ^ { 1 / 2 }
$$

$$
\eta = \left| S _ { 2 1 } \right| ^ { 2 }
$$

由式（1)、式（2）和式（4)，得到三线圈 $V _ { \mathrm { L } }$ 与 $V _ { \mathrm { { s } } }$ 的比值

$$
\frac { V _ { _ { \mathrm { ~ L ~ } } } } { V _ { _ { \mathrm { ~ S ~ } } } } = \frac { \omega ^ { 2 } k _ { _ { 1 2 } } k _ { _ { 2 3 } } L _ { _ { 2 } } \sqrt { L _ { 1 } L _ { _ { 3 } } } R _ { _ { \mathrm { ~ L ~ } } } } { Z _ { _ { 1 } } Z _ { _ { 2 } } Z _ { _ { 3 } } + \omega ^ { 2 } ( k _ { _ { 1 2 } } ^ { 2 } L _ { _ { 1 } } L _ { _ { 2 } } Z _ { _ { 3 } } + k _ { _ { 2 3 } } ^ { 2 } L _ { _ { 2 } } L _ { _ { 3 } } Z _ { _ { 1 } } ) }
$$

同时由式（5）和式（6）得到三线圈WPT系统的传输效率

$$
\eta = \frac { k _ { 1 2 } ^ { 2 } \underline { { Q } } _ { 1 } \underline { { Q } } _ { 2 } k _ { 2 3 } ^ { 2 } \underline { { Q } } _ { 2 } \underline { { Q } } _ { 3 } } { ( 1 + k _ { 2 3 } ^ { 2 } \underline { { Q } } _ { 2 } \underline { { Q } } _ { 3 } ) ( 1 + k _ { 1 2 } ^ { 2 } \underline { { Q } } _ { 1 } \underline { { Q } } _ { 2 } + k _ { 2 3 } ^ { 2 } \underline { { Q } } _ { 2 } \underline { { Q } } _ { 3 } ) }
$$

式中， $\boldsymbol { \mathcal { Q } }$ 为线圈的品质因数，品质因数是存储的能量与耗散的能量的比值。 $Q _ { 1 } = \omega L _ { 1 } / ( R _ { \mathrm { p 1 } } + R _ { \mathrm { S } } )$ ，为发射线圈的品质因数； $Q _ { 2 } = \omega L _ { 2 } / R _ { \mathrm { p } 2 }$ ，为中继线圈的品质

因数； $Q _ { 3 } = \omega L _ { 3 } / ( R _ { \mathrm { p } 3 } + R _ { \mathrm { L } } )$ ，为接收线圈的品质因数。

# 3 频率分裂现象

由式（4）和式（6）得到 $S _ { 2 1 }$ 的计算公式，并依据公式以及表1中的参数取值得到3个线圈的WPT系统的 $\left| S _ { 2 1 } \right|$ 、耦合系数 $k _ { 2 3 }$ 以及频率 $f$ 的关系如图2所示[8]。

![](images/8413970a074ba9f807482f28b131d174da8d51b489f4c8f9cff556e3f19b0411.jpg)  
图2三线圈WPT系统 $s$ 参数、耦合系数、频率的关系 Fig.2The relationship between the $S \mathrm { . }$ parameter， the coupling coefficient and the frequency of the three-coil WPT system

在分析图2之前，首先引入一个公式

$$
M _ { _ { 2 3 } } \approx \mu _ { _ 0 } \pi N _ { _ 2 } N _ { _ 3 } r _ { 2 } ^ { 2 } r _ { 3 } ^ { 2 } / ( 2 d _ { _ { 2 3 } } ^ { 3 } )
$$

式中， $\mu _ { 0 }$ 为自由空间磁导率； $N _ { 2 }$ ， $N _ { 3 }$ 为中继线圈和接收线圈的匝数； $r _ { 2 }$ 、 $\boldsymbol { r } _ { 3 }$ 为中继线圈和接收线圈的半径； $d _ { 2 3 }$ 为它们之间的距离。

下面分析磁耦合谐振式无线输电系统的频率分裂现象。该系统的工作区域根据实际耦合系数与临界耦合系数的关系可以分为欠耦合、临界耦合和过耦合，但频率分裂现象仅出现在过耦合区域。由式(8）和图2可以看出，在三线圈自身参数（匝数、半径等）不变的情况下，谐振线圈之间的耦合系数$k _ { 2 3 }$ 与它们之间的距离成反比。在过耦合区域，随着中继线圈和接收线圈之间距离 $d _ { 2 3 }$ 的减小，谐振线圈之间的耦合程度逐渐增大，频率分裂现象也变得越来越明显；而随着距离 $d _ { 2 3 }$ 的增大，谐振线圈之间的耦合程度逐渐减小，频率分裂的两个分支也慢慢汇合直到汇聚到 $f _ { 0 }$ 点， $f _ { 0 }$ 点为临界耦合点，在该点能够实现能量的最大传输效率。临界耦合点是欠耦合状态和过耦合状态的过渡点。欠耦合状态下，仍然能够进行无线电能传输，但是可实现的能量传输效率是有限的。由于发生频率分裂现象时，系统有不止一个谐振点并且每个谐振点都能取到传输效率的极大值，因此有必要采取措施来抑制频率分裂现象。

在分析抑制频率分裂的方法之前，先来看一下图3，该图是对相同内阻不同距离下系统效率的比较以及相同距离不同内阻下系统效率的比较。图3是由表1的相关数据以及式（7）仿真得到，其中3a和3b距离为 $2 0 \mathrm { c m }$ ，内阻 $R _ { \mathrm { s } }$ 分别为 $5 \Omega$ ， $1 5 \Omega$ 3c和3d距离为 $3 0 \mathrm { c m }$ ，内阻 $R _ { \mathrm { s } }$ 分别为 $5 \Omega$ 、 $1 5 \Omega$ ·3e 和3f距离为 $4 5 \mathrm { c m }$ ，内阻 $R _ { \mathrm { s } }$ 分别为 $5 \Omega$ 、 $1 5 \Omega$ 。

由图3可以看出，频率分裂现象仅出现在近距离，即过耦合区域，随着距离的增加，频率分裂现象逐渐消失。此外，在距离为 $2 0 \mathrm { c m }$ 时，出现频率分裂现象，并且内阻 $R _ { \mathrm { S } } = 1 5 \Omega$ 时频率分裂现象要比$R _ { \mathrm { S } } = 5 \Omega$ 时明显很多。在距离为 $3 0 \mathrm { c m }$ 时， $R _ { \mathrm { S } } = 5 \Omega$ 时没有频率分裂现象， $R _ { \mathrm { S } } = 1 5 \Omega$ 时有频率分裂现象但已经不太明显。在距离为 $4 5 \mathrm { c m }$ 时，不再出现频率分裂现象。由此可见，内阻是影响频率分裂的重要因素。

![](images/6d4c175ea899fe2dc763835373849630f25bd4a2783f7a1cc4a03217a25f216b.jpg)  
图3效率与频率的关系  
Fig.3The relationship between efficiency and frequency

根据文献[9]，当处于过耦合状态，发射线圈和接收线圈之间的距离很小，此时发射线圈内阻对WPT系统的效率产生很大的影响。在过耦合状态，原谐振点的输入阻抗具有很大的阻抗角和比较小的幅值，而大的阻抗角导致传输能量很低，小的幅值

导致源电流很大，进而加大了内阻与输入阻抗的差值。但是在低于或者高于原谐振点时，输入阻抗具有相反的特性，有很小的阻抗角和比较大的幅值。由于这两个相反的特性，效率在两个谐振频率点出现极大值即频率分裂现象。由此说明内阻与输入阻抗不匹配导致频率分裂。因此为了减小内阻对频率分裂的影响，下文将通过增加一个阻抗匹配网络来抑制频率分裂现象。

# 4抑制频率分裂的方法

为了抑制频率分裂现象并增大WPT系统的传输效率，本文通过添加阻抗匹配网络来实现。阻抗匹配网络主要有三种型式：L型、 $\pi$ 型、T型。由于适用于传输距离小、等效阻抗大的情况并且结构更简单、更易实现，本文选择L型匹配电路。如图4所示，在源线圈添加L型阻抗匹配电路，同时，本文采用概念性阻抗匹配方法，将中继线圈和接收线圈组成另一个阻抗匹配电路以达到增大WPT系统传输效率的作用[10]。

![](images/6b346b06218632c499e66acea7b87d97b6ef4457a6b91a600577e55049b94a7e.jpg)  
图4阻抗匹配电路  
Fig.4Impedance matching circuit

下面首先对添加了阻抗匹配的系统进行理论分析。根据最大功率传输原则，谐振状态下，发送端的阻抗匹配网络的输入阻抗 $Z _ { \mathrm { i n } }$ 的实部等于源线圈内阻 $R _ { \mathrm { s } }$ 而虚部等于0。设WPT除发送端阻抗匹配电路之外的等效阻抗为 $Z _ { 0 }$ ，如图5所示，得到等效阻抗为

$$
Z _ { _ 0 } = Z _ { _ 1 } ^ { _ { 1 } } + \frac { \omega ^ { 2 } M _ { _ { 1 2 } } ^ { 2 } Z _ { _ 3 } } { Z _ { _ 2 } Z _ { _ 3 } + \omega ^ { 2 } M _ { _ { 2 3 } } ^ { 2 } } - R _ { _ { \mathrm { S } } }
$$

此时，令 $Z _ { \mathrm { i n } }$ 的实部等于 $R _ { \mathrm { s } }$ 虚部等于 $0$ ，得到发射端的匹配电容 $C _ { \mathrm { P } }$ 、匹配电感 $L _ { \mathrm { s } }$ 为

$$
C _ { \mathrm { p } } = { \frac { \mathcal { Q } _ { 1 } } { \omega _ { 0 } Z _ { 0 } } }
$$

$$
L _ { \mathrm { s } } = { \frac { C _ { \mathrm { p } } Z _ { 0 } ^ { 2 } } { \omega _ { \mathrm { 0 } } ^ { 2 } C _ { \mathrm { p } } ^ { 2 } Z _ { 0 } ^ { 2 } + 1 } }
$$

式中， $\omega _ { 0 }$ 为谐振角频率； $\boldsymbol { Q } _ { 1 }$ 为发射端的品质因

数，为

$$
\mathcal { Q } _ { 1 } = \sqrt { \frac { Z _ { 0 } } { R _ { \mathrm { s } } } - 1 }
$$

当 $R _ { \mathrm { S } } < Z _ { 0 }$ 时，式（12）成立。由式（12）看出，距离的变化导致耦合系数的变化，然后等效阻抗 $Z _ { 0 }$ 改变，进而品质因数随之改变，匹配电容和匹配电感也随之改变。

![](images/668884563ba4803a520a66f0fcd5b413e18971a73725478b8092e6ac10cd5223.jpg)  
图6实验装置  
Fig.6Experimental device

# 表1线圈的详细参数

![](images/e1c08fb57d3c2f9f575eef54643632e50482c7e66edcdb3a2f31c8378ff2a1cf.jpg)  
图5等效电路

相似地，谐振状态时，输出匹配网络使接收端的输出阻抗 $Z _ { \mathrm { o u t } }$ 与最优负载阻抗 $R _ { \mathrm { L ( o p t ) } }$ 共轭匹配。最优负载阻抗为

$$
R _ { \mathrm { { L } } } \left( \mathrm { o p t } \right) = R _ { \mathrm { { p 3 } } } \left( \frac { k _ { 2 3 } ^ { 2 } \mathcal { Q } _ { 2 } \mathcal { Q } _ { 3 } } { \sqrt { 1 + k _ { 1 2 } ^ { 2 } \mathcal { Q } _ { 1 } \mathcal { Q } _ { 2 } } } - 1 \right)
$$

以上分析了添加阻抗匹配网络之后WPT系统匹配电容、匹配电感以及输入阻抗输出阻抗的关系式。而对于整个WPT系统来说，在添加阻抗匹配网络后，既要满足输入阻抗与内阻共轭匹配，又要满足输出阻抗与负载共轭匹配，才可在抑制频率分裂现象的同时提高WPT系统的效率。对于源线圈添加的阻抗匹配网络，主要任务是找到匹配电容和电感的值；对于接收端的匹配网络，主要任务是找到耦合系数的值。而它们均受距离因素影响，因此距离是影响本文所提阻抗匹配系统的关键因素。下面本文通过实验和仿真验证所提阻抗匹配方法的正确性。

Tab.1 Details of the coil   

<html><body><table><tr><td>参数</td><td>数值</td><td>参数</td><td>数值</td></tr><tr><td>L/uH</td><td>1.0</td><td>Rp2、Rp3/</td><td>0.5</td></tr><tr><td>L、L3/μH</td><td>20</td><td>Rs、RL/Ω</td><td>50</td></tr><tr><td>C/pF</td><td>253</td><td>k12</td><td>0.1</td></tr><tr><td>C2、C3/pF</td><td>12.67</td><td>f/MHz</td><td>10</td></tr><tr><td>Rp1/Ω</td><td>0.1</td><td></td><td></td></tr></table></body></html>

# 5 实验和仿真分析

本文的实验装置如图6所示，电源WPT采用逆变电源，可以将直流电压转换为固定频率的交流电，其中，固定频率为磁耦合谐振式WPT系统的谐振频率 $f _ { \mathrm { 0 } } = 1 0 \mathrm { M H z }$ ；输入电压 $V _ { \mathrm { { s } } }$ 设为10V，来限制输入电流；发射装置包括发射线圈和中继线圈，接受装置包括接收线圈，线圈的匝数均为10匝，发射线圈半径为 $8 \mathrm { c m }$ ，中继线圈、接收线圈半径为$4 \mathrm { c m }$ ；L型匹配网络由空心电感器和非极化电容器构成，线圈的详细参数见表1。

本文使用上述阻抗匹配方法来抑制频率分裂现象。对此进行实验并得到了不同距离下匹配电容 $C _ { \mathrm { P } }$ 和匹配电感 $L _ { \mathrm { s } }$ 的值，如图7所示。由图7可以看出，距离不同时匹配电容和匹配电感的值是不一样的，这是由距离不同导致的。距离不同导致等效阻抗不同，进而品质因数不同，最终致使匹配电容和匹配电感值不同。由于发射端的L型阻抗匹配网络旨在抑制频率分裂现象，在此同时接收端的阻抗匹配网络用来提高WPT系统效率，表2为本实验中不同距离下该WPT系统的效率值。效率1为加入阻抗匹配网络之前的效率，效率2为加入阻抗匹配网络之后的效率。可以看出，二者相比，效率2在过耦合区域系统的效率明显增加，这是由于频率分裂现象受到抑制；同时可以看出在过耦合区域，系统的效率在不同距离下相差不大，这也是添加阻抗匹配的原因；在欠耦合区域，系统的效率也相对增大，这主要是接收端概念性阻抗匹配网络的作用。

![](images/26caf3d628e36abeceffccfe276afed69360c6cc04a8d87cbe9bf2f58a09c7b3.jpg)  
Fig.5Equivalent Circuit   
图7不同距离下匹配电容和匹配电感的值 Fig.7Value of the matching capacitance and matching inductance at different distances

表2不同距离下的效率值  
Tab.2Efficiency values at different distances   

<html><body><table><tr><td>d/cm</td><td>10</td><td>15</td><td>20</td><td>25</td><td>30</td><td>35</td></tr><tr><td>效率1</td><td>0.21</td><td>0.30</td><td>0.43</td><td>0.59</td><td>0.55</td><td>0.41</td></tr><tr><td>效率2</td><td>0.51</td><td>0.54</td><td>0.60</td><td>0.59</td><td>0.56</td><td>0.50</td></tr></table></body></html>

下面以 $d = 2 0 \mathrm { c m }$ 为例对加入阻抗匹配网络之后的系统进行分析，此时系统仍然处于过耦合状态。在加入阻抗匹配网络之前，在 $d = 2 0 \mathrm { c m }$ 处系统也处于过耦合状态，但由于频率分裂现象因而效率比较低；加入阻抗匹配网络之后，由于输入阻抗与系统内阻基本相等且趋于临界耦合状态、输出阻抗又与负载阻抗共轭匹配，频率分裂现象受到抑制同时系统效率得到比较大的提升。

综上所述，加入阻抗匹配网络之后，在过耦合区域系统的频率分裂现象被抑制并且系统的效率总体上得到了增加(包括欠耦合区域)。因此本文所提阻抗匹配方法可以抑制频率分裂现象，在一定程度上增大系统效率。

# 6 结论

（1）本文重点研究了三线圈磁耦合谐振式WPT系统的频率分裂特性，得到了三线圈WPT系统的S参数和效率并通过关系图详细分析了频率分裂现象。(2）分析得到同等距离时，不同的内阻也是影响频率分裂的重要因素，由于内阻与系统的输入阻抗不匹配导致了频率分裂现象，由此提出了一种阻抗匹配方法。(3）在过耦合区域，使用阻抗匹配方法得到不同距离下的匹配电容和匹配电感，同时因为接收端的概念性阻抗匹配网络，频率分裂现象被抑制同时增大了系统的传输效率，进而通过实验与仿真验证该方法可以抑制频率分裂并且增大系统效率。

# 参考文献

[1] 田子建，杜欣欣，樊京，等．磁耦合谐振式无线输电系统不同拓扑结构的分析[J]．电气工程学报，2015，10(6):47-57.Tian Zijian,Du Xinxin,Fan Jing,et al.Analysis ondifferent topology structures in magnetic coupling

resonant WPT system[J]. Journal of Electrical Engineering,2015,10(6): 47-57.   
[2] 杨庆新，张献，李阳．无线电能传输技术及其应 用[M]．北京：机械工业出版社，2014.   
[3] Andre Kurs,Aristeidis Karalis,Robert Moffatt. Wireless power transfer via strongly coupled magnetic resonances[J]. Science,2007,317(6): 83-86.   
[4] 黄学良，谭林林，陈忠，等．无线电能传输技术研 究与应用综述[J]．电工技术学报，2013，28(10)： 1-11. Huang Xueliang,Tan Linlin, Chen Zhong,et al. Review and research progress on WPT technology[J]. Transactions of China Electrotechnical Society, 2013,28(10): 1-11.   
[5] 张献，杨庆新，陈海燕，等．磁耦合谐振式传能系 统的频率分裂特性研究[J]．电机工程学报，2012, 32(9): 167-171. Zhang Xian, Yang Qingxin, Chen Haiyan, et al. Research on characteristics of frequency splitting in electromagnetic coupling resonant power transmission systems[J]. Proceedings of the CSEE, 2012, 32(9): 167-171.   
[6] Lyu Yuelong, Meng Fanyi. A method of using nonidentical resonant coils for frequency splitting elimination in wireless power transfer[J]. IEEE Transactions on Power Electronics, 2015,30(11): 6097-6107.   
[7] Huang X L, Tan L L, Wang W. Resonant frequency splitting analysis and optimation of wireless power transfer system[C]. PIERS Proceedings, Moscow, 2012,49(1):684-688.   
[8] Huang Runhong, Zhang Bo. Frequency spliting phenomena of magnetic resonant coupling wireless power transfer[J]. IEEE Transactions on Magnetic, 2014, 50(11): 1-4.   
[9] Zhang Yiming, Zhao Zhengming, Chen Kainan. Frequency splitting analysis of magnetically-coupled resonant wireless power transfer[C]. IEEE Energy Conversion Congress and Exposition, 2013: 2227- 2232.   
[10]Huang Yong, Shinohara Naoki, Mitani Tomohiko. Impedance matching in wireless power transfer[J]. IEEE Transactions on Microwave Theory and Techniques, 2017, 65(2): 582-590.