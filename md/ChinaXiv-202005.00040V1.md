# 全日面磁场与活动监测望远镜轴系升级

陈垂裕1,2,郭晶晶1,2,林佳本‘，邓元勇1,2

(1.中国科学院国家天文台太阳活动重点实验室，北京 100101;2.中国科学院大学，北京 100049;)

摘要：在天文观测中，需要望远镜能快速、准确的指向目标天体（如太阳等），并对其进行稳定跟踪。本文针对怀柔太阳观测基地（HSOS）的全日面磁场与活动监测望远镜（SMAT）进行轴系升级，使用伺服电机轴上23位高精度绝对式编码器替代光栅钢带码盘；通过VSOP87行星理论实时计算日面中心位置，使用基于大面阵CCD的高精度导行系统不间断跟踪太阳并记录太阳位置，利用最小二乘法分段拟合太阳实时位置与绝对值编码器数值，建立起指向算法并实现日面中心指向。经实测，赤经方向的指向误差约为 $3 6 . 6 9 ^ { \prime \prime }$ ，赤纬方向的指向误差约为 $2 1 . 4 9 "$ ，满足SMAT的指向要求，该方法成本低兼容性高，对于其他赤道式望远镜的升级改造具有借鉴意义。关键词：指向控制，指向误差，轴系升级，太阳观测、赤道式望远镜

中图分类号：P111.41

# 0引言

怀柔太阳观测基地(Huairou Solar Observing Station,HSOS)是在国际太阳物理界享有高知名度的太阳磁场和速度场观测研究基地和学术研究中心。全日面太阳磁场望远镜（The Solar Magnetism and ActivityTelescope，SMAT）是怀柔太阳观测基地的重要观测设备之一（如图1)，属于国家空间天气部门支持的重大课题，于2005年12月实现首光，2006年5月通过验收投入常规观测[1]。该望远镜主要由 $\mathrm { H } \alpha$ 望远镜和全日面矢量磁场望远镜两部分组成，旨在通过观测太阳光球大尺度矢量磁场演化和色球活动现象，研究太阳活动爆发的动力学过程和触发机理[2]。目前，该望远镜已经投入观测超过14年，为了保证望远镜的长期稳定观测，提升观测效率，需要对轴系系统进行改造和升级。

![](images/cce7f9bd7bc72653306558eeb8159fa675c57896b3845c20b17a0ff747904d86.jpg)  
图1全日面磁场与活动监测望远镜  
Fig.1 SolarMagnetismand the Activity Telescope (SMAT)

SMAT属于赤道式望远镜，该望远镜的机架上有两个望远镜镜筒，分别为全日面太阳磁场望远镜和全日面太阳 $\mathrm { H } \alpha$ 望远镜，部分设计参数如表1所示。设计之初安装了光栅钢带码盘作为位置检测元件，基于此元件构建了相应的位置闭环跟踪系统[3]。2012年，码盘发生故障无法利用其进行望远镜的跟踪导行。该望远镜无自动指向功能，需要观测员凭经验通过手柄控制望远镜指向太阳，指向精度不高且效率低。本研究针对 SMAT进行了轴系升级，将高精度的轴上编码器替代光栅钢带码盘，以更低成本和代价实现望远镜位置检测。使用轴上编码器作为反馈机构，利用高精度的导行系统，跟踪太阳并记录太阳实时位置和编码器数值，建立起望远镜坐标体系，实现了望远镜的指向功能，可在正常观测时段指向日面中心，提升望远镜观测效率。

表1SMAT望远镜部分设计指标参数  
Tab.1 Key design parameters of SMAT telescope   

<html><body><table><tr><td></td><td>全日面太阳磁场望远镜</td><td>全日面Hα太阳望远镜</td></tr><tr><td>入瞳直径</td><td>100mm</td><td>200mm</td></tr><tr><td>工作谱线</td><td>532.40nm</td><td>656.28nm</td></tr><tr><td>有效视场</td><td>33′×33'</td><td>34'×34'</td></tr><tr><td>透过波长半宽</td><td>0.0125nm</td><td>0.025nm</td></tr><tr><td>空间分辨率</td><td>优于5"</td><td>优于2"</td></tr><tr><td>CCD</td><td>1K*1K</td><td>2K*2K</td></tr><tr><td>跟踪精度</td><td>1"/30 分钟内(rms)</td><td>1"/30 分钟内(rms),</td></tr><tr><td>磁场分辨率</td><td>纵横磁场优于5高斯；横向磁场</td><td>/</td></tr><tr><td></td><td>优于150 高斯</td><td></td></tr></table></body></html>

本文第一部分将介绍太阳望远镜指向的基本原理，利用该原理实现太阳实时位置的计算，使用基于大面阵CCD 的高精度导行系统不间断跟踪太阳并记录太阳位置[4]，利用最小二乘法分段拟合太阳实时位置与绝对值编码器数值设计指向算法。第二部分，搭建软硬件平台并完成望远镜的升级改造。第三部分，处理并分析实测数据计算指向误差。

# 1太阳望远镜指向基本原理与算法设计

指向控制系统是望远镜轴系运动控制的重要子系统，其功能是能够自动将望远镜对准太阳，无需观测人员手动调整望远镜对准太阳。如图2所示，首先需要建立太阳实时位置和望远镜实时位置模型。依据位置模型，计算出望远镜位置和太阳位置之间的位置差。然后根据位置差，换算到运动控制系统的脉冲量上，将脉冲量发送到轴系控制系统，由轴系控制系统驱动望远镜指向太阳。望远镜的指向控制系统要求能快速、准确的把望远镜指向观测目标。考虑望远镜实际情况，SMAT指向精度的指标为 $1 ^ { \prime }$ 。

![](images/9c62ed00882ae643969f3899ce73b95c13c6dee59809a5f1371714ea4eb6f537.jpg)  
图2系统控制流程图  
Fig.2System control flowchart

# 1.1计算日面中心坐标

指向的目标是日面中心，实现指向首先需要计算实时的日面中心坐标。本文采用 P.Bretagnon 和G.Francou 提出的VSOP87行星理论[5],该方法可以较为准确的计算出任意给定时刻太阳系内八大行星相对于太阳的位置分布情况，计算过程较为简便，计算误差在 $2 ^ { \prime \prime }$ 以内[]。

根据该理论对应的地球周期项系数，可以计算：

$$
\begin{array} { c } { { l = \displaystyle \sum _ { i = 1 } ^ { n } L _ { i } \tau ^ { i } } } \\ { { \left. b = \displaystyle \sum _ { i = 1 } ^ { n } B _ { i } \tau ^ { i } \right\} } } \\ { { \left. r = \displaystyle \sum _ { i = 1 } ^ { n } B _ { i } \tau ^ { i } \right) } } \end{array}
$$

式(1)中， $\tau$ 为当前儒略日距离J2000. $o$ 的千年数， $l$ 为日心黄经， $b$ 为日心黄纬, $\boldsymbol { r }$ 为日心距离， ${ L _ { i } } , { B _ { i } } , { R _ { i } }$ 为周期项系数。

$$
\left. \begin{array} { l } { L = l + \pi + \Delta \lambda _ { 1 } + \Delta \lambda _ { 2 } } \\ { B = - b } \end{array} \right\}
$$

式（2）中将日心黄经、日心黄纬转化为地心黄经、地心黄纬后，考虑章动修正量 $\varDelta \lambda _ { 1 }$ 和光行差 $\varDelta \lambda _ { 2 }$ 可得到视黄经 $L$ 、视黄纬 $B$ 。通过 $L$ 和 $B$ 可计算视赤经、视赤纬：

$$
\left. \begin{array} { l } { { t a n \alpha = \frac { s i n L c o s e - t a n B c o s e } { c o s L } } } \\ { { s i n \delta = s i n B c o s e + c o s B s i n e s i n L } } \end{array} \right\}
$$

式（3）中， $\alpha$ 为视赤经， $\delta$ 为视赤纬， $e$ 为真黄赤交角。通过 $\alpha$ 可计算时角 $t { \mathrm { : } }$

$$
t = S _ { 0 } + T + \Delta T - \alpha
$$

式（4）中， $S _ { 0 }$ 是当天平时 $0 ^ { h }$ 的恒星时， $T$ 是当前的北京时间， $\angle T = 1 2 0 ^ { \circ } - \lambda$ 是当地的地理经度与东经$1 2 0 ^ { \circ }$ 的差，以时分秒为单位。

$$
\scriptstyle { \left\{ { \begin{array} { l } { x } \\ { y } \\ { z } \end{array} } \right\} } = { \left\{ { \begin{array} { l l l } { \cos \alpha } & { - \sin \alpha } & { 0 } \\ { \sin \alpha } & { \cos \alpha } & { 0 } \\ { 0 } & { 0 } & { 1 } \end{array} } \right\} } { \left\{ { \begin{array} { l } { x ^ { \prime } } \\ { y ^ { \prime } } \\ { z ^ { \prime } } \end{array} } \right\} }
$$

通过式（5)，可以将赤道坐标转化为地平坐标。式（6）（7）可以通过视赤纬 $\delta$ 和时角 $t$ 得到方位角 $A$ 和高度角H:

$$
\cos A = { \frac { \sin \delta - \sin H \sin \phi } { \cos H \cos \phi } }
$$

综上，利用上述公式可以实时计算日面中心坐标。图3为怀柔太阳观测基地不同节气太阳方位角、高度角的变化。

![](images/6268c550158c7e11e5d9b75fe41fb60384509ea095d526bc035ff276f59ac0cd.jpg)  
图3怀柔太阳观测基地不同节气太阳方位角、高度角的变化  
Fig.3 Changes in solar azimuth and altitude at different solar terms in HSOS

# 1.2望远镜坐标的建立

通过轴上编码器，可实现对电机转动量的测量。电机驱动望远镜机架的转动，利用编码器可以反映望远镜在赤经、赤纬方向的运动情况。通过标定，可以建立编码器数值与望远镜赤经、赤纬方向转动角度的对应关系。从而通过读取编码器数值，建立望远镜坐标，得到望远镜当前位置的具体信息。

利用望远镜自带的刻度盘和陀螺仪，测量编码器数值与望远镜实际位置，可以得到表2、表3。多圈数指电机旋转的圈数，即电机旋转了几圈；单圈数指电机旋转后的细分位置（23位的分辨率，每个多圈被细分为6388608个位置)；总圈数 $\varXi$ 多圈数 $^ { * } 6 3 8 8 6 0 8 +$ 单圈数。

表2不同赤经（时角）对应的编码器数值  
Tab.2 Encoder values for different right ascension (hour angle)   

<html><body><table><tr><td>赤经（时角）</td><td>单圈数</td><td>多圈数</td><td>方位总圈数</td></tr><tr><td>06:00</td><td>5639173</td><td>64118</td><td>537866406917</td></tr><tr><td>08:00</td><td>6374936</td><td>64586</td><td>541793011224</td></tr><tr><td>10:00</td><td>2614303</td><td>65063</td><td>545790616607</td></tr><tr><td>12:00</td><td>4478367</td><td>65543</td><td>549819012511</td></tr><tr><td>14:00</td><td>5799792</td><td>66020</td><td>553821699952</td></tr><tr><td>16:00</td><td>3612120</td><td>66500</td><td>557846044120</td></tr><tr><td>18:00</td><td>6809296</td><td>66961</td><td>561716389584</td></tr></table></body></html>

将时角转化成角度（以正北为 $0 ^ { \circ }$ ，顺时针为正)，并将时角与对应的方位总圈数进行线性拟合可得到如下关系：

$$
y _ { \neq \neq z } = k _ { 1 } x + b _ { 1 }
$$

其中 $k _ { 1 } { = } 1 3 2 9 6 0 8 2 9 . 9 3$ 为赤经-圈数转换系数， $b _ { 1 } { = } 5 2 5 8 7 4 6 4 7 8 8 6 . 8 6$ 为选取的零位相关的截距。拟合后相关系数 $R ^ { 2 } { = } 0 . 9 9 9 9 8 8 1 2$ 。

在初期调试中，我们发现由于望远镜本身存在轴系误差，在望远镜跨过平衡位置前后，通过少量的数据并不能很好的拟合时角与圈数的关系。为了进一步提升指向精度，利用郭晶晶[4等人提出利用大面阵CCD采集主望远镜的全日面 $\mathrm { H } \alpha$ 太阳像进行高精度导行，跟踪太阳并记录每一秒太阳实时位置和编码器数值。通过全天的跟踪，利用最小二乘法建立分段拟合关系。

$$
y _  \widecheck { \mathcal { H } _ { \widecheck { \leq x } } } = \left\{ \begin{array} { c c } { k _ { 1 } x + b _ { 1 } } & { \qquad 9 0 ^ { \circ } \leq x < 1 5 0 ^ { \circ } } \\ { k _ { 2 } x + b _ { 2 } } & { 1 5 0 ^ { \circ } \leq x < 1 8 0 ^ { \circ } } \\ { k _ { 3 } x + b _ { 3 } } & { 1 8 0 ^ { \circ } \leq x < 2 1 0 ^ { \circ } } \\ { k _ { 4 } x + b _ { 4 } } & { 2 1 0 ^ { \circ } \leq x < 2 7 0 ^ { \circ } } \end{array} \right.
$$

其中， $k _ { i }$ 为赤经-圈数转换系数， $b _ { i }$ 为选取的零位相关的截距。经拟合后得到：

$$
\left. \begin{array} { l l } { { k _ { 1 } = 1 3 3 9 8 9 3 9 6 . 0 3 } } \\ { { k _ { 2 } = 1 3 4 1 1 9 3 2 4 . 6 4 } } \\ { { k _ { 3 } = 1 3 4 0 9 6 5 6 7 . 0 9 } } \\ { { k _ { 4 } = 1 3 3 9 3 4 6 8 3 . 6 8 } } \end{array} \right. \quad \left\{ \begin{array} { l l } { { b _ { 1 } = 5 2 5 6 3 5 6 7 9 4 7 5 . 3 7 } } \\ { { b _ { 2 } = 5 2 5 6 1 6 2 5 5 9 1 6 . 9 8 } } \\ { { b _ { 3 } = 5 2 5 6 2 1 3 1 1 1 0 9 . 3 0 } } \\ { { b _ { 4 } = 5 2 5 6 5 6 4 0 5 6 3 1 . 1 9 } } \end{array} \right.
$$

$R _ { i } ^ { 2 }$ 为拟合后的相关系数，经导行数据分段拟合后比原先的相关系数提升了两个数量级。

$$
\left\{ { \begin{array} { l } { R _ { 1 } ^ { 2 } = 0 . 9 9 9 9 9 9 5 0 } \\ { R _ { 2 } ^ { 2 } = 0 . 9 9 9 9 9 9 8 8 } \\ { R _ { 3 } ^ { 2 } = 0 . 9 9 9 9 9 9 6 2 } \\ { R _ { 4 } ^ { 2 } = 0 . 9 9 9 9 9 9 3 5 } \end{array} } \right.
$$

表3不同赤纬对应的编码器数值  
Tab.3Encoder valuesfordifferentdeclination   

<html><body><table><tr><td>赤纬（角度）</td><td>单圈数</td><td>多圈数</td><td>高度总圈数</td></tr><tr><td>30</td><td>2660548</td><td>65129</td><td>537866406917</td></tr><tr><td>20</td><td>4427532</td><td>65289</td><td>541793011224</td></tr><tr><td>10</td><td>1283567</td><td>65450</td><td>545790616607</td></tr><tr><td>0</td><td>3586696</td><td>65609</td><td>549819012511</td></tr><tr><td>-10</td><td>7425139</td><td>65767</td><td>553821699952</td></tr><tr><td>-20</td><td>2753279</td><td>65928</td><td>557846044120</td></tr><tr><td>-30</td><td>544914</td><td>66089</td><td>561716389584</td></tr></table></body></html>

将赤纬参数转化成角度（以水平为 $0 ^ { \circ }$ ，向上为正)，将角度与对应的方位总圈数进行线性拟合可得到如下关系：

$$
y _ { \tt _ { \tt \tt { j \# } \tt { k } \tt { \sharp } \# } } = k _ { 2 } x + b _ { 2 }
$$

其中 $k _ { 2 } { = }  { - } 3 9 8 8 8 2 4 8 9 . 7 8$ 为赤纬-圈数转换系数， $b _ { 2 } { = } 5 4 9 8 0 7 5 9 7 2 7 3 . 5 7$ 与选取的零位相关。拟合后相关系数 $R ^ { 2 } { = } 0 . 9 9 9 9 8 8 1 2$ 。

# 1.3指向的基本算法

通过读取时间和地理位置信息，实时计算日面中心坐标。利用轴上编码器计算出望远镜位置，并将望远镜位置和日面中心的位置差作为输入。控制器将根据下列公式换算为相应的指令信号发送到驱动器。驱动器根据指令将脉冲信号发送到伺服电机，由电机驱动望远镜轴系系统指向太阳。

# 日面中心赤经（赤纬）对应总单圈数－望远镜当前赤经（赤纬）总单圈数

# 驱动器发送脉冲数 $\mathbf { \Sigma } = \mathbf { \Sigma }$

# 电机每旋转1单圈输出脉冲数

利用上述原理和算法研究，可以实现太阳实时位置和望远镜实际位置的计算。下一步需要对 SMAT 进行软硬件改造与升级，结合望远镜的实际情况，完成硬件选型、搭建和调试等工作，并将算法编写进入控制软件，通过软硬件平台结合实现算法功能。

# 2轴系系统的改造与升级

2012年，SMAT的光栅钢带码盘发生故障，轴系电机也因年代较为久远无法读取轴上编码器数值，望远镜无位置检测装置。如果重新安装光栅码盘，需要根据望远镜结构量身定制，更换过程涉及到望远镜光机结构的调整，更换后可能还需要重新对望远镜轴系进行校正。同时，安装新的光栅码盘，还需要研发相应的数据采集系统并确保该系统可以与望远镜控制软件兼容，整个过程需要投入较多的人力物力。为了降低成本并提升兼容性，我们决定将原电机更换为带有23位绝对编码器的伺服电机，通过集成控制器、驱动器制作新的轴系系统控制箱，实现硬件的改造。同时将编码器数据采集和指向功能集成进怀柔太阳观测基地全日面望远镜控制系统软件，可以通过该软件实现对轴系系统的全面控制。

# 2.1硬件系统的改造

在改造升级前，SMAT使用的是型号为HC-SFS52的三菱电机，额定功率750W，带有17位增量式编码器，分辨率为131072 p/rev。为了实现更高精度的位置检测和建立稳定的望远镜坐标，将电机更换为型号MSMF082L1U2M的松下A6伺服电机，驱动器型号为MCDLT35SF。该电机有23位轴上绝对式编码器，分辨率达到8388608 prev。相比于增量式编码器，绝对值编码器的位置是由输出代码的读数来确定的，在一转内每个位置的读数是唯一的[8。绝对式编码器构成绝对式系统时，接通电源时不需要进行原点复位，可以建立稳定的望远镜坐标系，这对于指向功能的实现是极为重要的。发生断电或意外移位时，有独立电源的绝对式编码器也不会丢失编码信息。

轴上编码器的采集系统集成在伺服电机里，上位机控制器通过RS485通信或RS232通信可以同时连接赤经、赤纬方向的电机，把位置信息作为串行数据进行读取，将各个数据进行处理后即可以得到两个轴的绝对位置信息。相比于光栅钢带码盘，轴上编码器无需进行特殊定制，有成熟的通用型产品成本较低。轴上编码器的数据采集相对简单，不需要额外配置光栅读数头和数据采集卡，也不要过多考虑安装精度和系统校准等问题。另一层的考虑是直接更换电机，不会涉及到望远镜结构的位移，不需要对轴系进行重新校正。

更换了新的轴系系统控制箱（如图4)，控制器采用型号为ADT-8860的众为兴可编程控制器。能实现对伺服电机的控制，可读取编码器数值，同时控制箱具备单独的硬限位、手柄控制等接口，可以不经过软件就能实现相应的功能。

![](images/400c27a219eebe7796d80cfafd7ea70bbb895005da65ba6d7cb73549a7d7d136.jpg)  
图4新轴系系统控制箱

# 2.2软件系统的升级

$\mathrm { H } \alpha$ 望远镜的观测软件（如图5）是在VS2010的开发平台下，使用面向对象的 $\mathrm { C } { + } { + }$ 语言开发的。在原有怀柔全日面望远镜控制系统的基础上，实现了实时读取和显示赤经赤纬编码器单圈/多圈数值。添加了“方位指向”“高度指向”等功能，实现日面中心的实时指向，并可通过输入时角、赤纬等参数实现在望远镜轴系允许范围内的指向。

![](images/cbdabdf15008c0069c49ca065789ed654d4301a02457e90be7804f4d7797bc43.jpg)  
Fig 4 New shafting system control box   
图5全日面望远镜控制系统界面  
Fig5Full-disk Solar telescope control systeminterface

# 3测试结果

# 3.1实验室测试结果

2020 年1月4日，在SMAT进行了指向功能的实际测试。预先设定基准图像（如图6)，从早上8:55到下午15:55，期间每隔15分钟进行指向，并保留指向后的全日面 $\mathrm { H } \alpha$ 太阳像，图7为每隔60分钟指向后的 $\mathrm { H } \alpha$ 太阳像。通过基于Hough变换的太阳图像质心与半径检测算法对图像进行分析，并与基准图像对比计算误差。通过全天的指向，得到表4:

![](images/7f95e86ee1a6b38054e39dbe456f21df3d66cb6f4ba1cb96bea2fd5ce1aa6779.jpg)  
图6基准太阳图像

![](images/3afb2b42408880e0f1317dde1f1d8014dbbfb12dbef604d453c1bfef99ece215.jpg)  
Fig.6 The reference H-alpha image   
图7八个时刻指向后的Hα太阳像  
Fig.7 H-alpha images of eight moments after pointing

经计算，基准图像的圆心坐标为（1207.0,1211.0)。当天 $\mathrm { H } \alpha$ 太阳像直径 $R { \approx } 2 2 9 6 . 5 9 3 0 8 4$ pixels，中午12 时太阳视直径 $R ^ { \prime } { = } 3 2 ^ { \prime } 3 2 . 0 1 ^ { \prime \prime }$ ，可知图6中1 pixels≈0.849959"。

# 表4不同时刻指向后的数据

Tab.4 Data at different times after pointing   

<html><body><table><tr><td>时间</td><td>圆心赤经坐标 /pixel</td><td>赤经偏移量</td><td>圆心赤纬坐标 /pixel</td><td>赤纬偏移量 /pixel</td><td>半径长度/pixel</td></tr><tr><td>08:55</td><td>1239</td><td>/pixel 32</td><td>1207</td><td>-4</td><td>1147.2</td></tr><tr><td>09:10</td><td>1241</td><td>34</td><td>1213</td><td>2</td><td>1146.6</td></tr><tr><td>09:25</td><td>1257</td><td>50</td><td>1207</td><td>-4</td><td>1146.2</td></tr><tr><td>09:40</td><td>1279</td><td>72</td><td>1203</td><td>-8</td><td>1146.6</td></tr><tr><td>09:55</td><td>1287</td><td>80</td><td>1185</td><td>-26</td><td>1147.2</td></tr><tr><td>10:10</td><td>1247</td><td>40</td><td>1201</td><td>-10</td><td>1149.4</td></tr><tr><td>10:25</td><td>1247</td><td>40</td><td>1193</td><td>-18</td><td>1148.4</td></tr><tr><td>10:40</td><td>1241</td><td>34</td><td>1193</td><td>-18</td><td>1148.8</td></tr><tr><td>10:55</td><td>1235</td><td>28</td><td>1185</td><td>-26</td><td>1149.6</td></tr><tr><td>11:10</td><td>1231</td><td>24</td><td>1215</td><td>4</td><td>1146.2</td></tr><tr><td>11:25</td><td>1259</td><td>52</td><td>1195</td><td>-16</td><td>1147.4</td></tr><tr><td>11:40</td><td>1267</td><td>60</td><td>1195</td><td>-16</td><td>1150.4</td></tr><tr><td>11:55</td><td>1243</td><td>36</td><td>1215</td><td>4</td><td>1146.2</td></tr><tr><td>12:10</td><td>1231</td><td>24</td><td>1201</td><td>-10</td><td>1148.8</td></tr><tr><td>12:25</td><td>1249</td><td>42</td><td>1195</td><td>-16</td><td>1147.8</td></tr><tr><td>12:40</td><td>1271</td><td>64</td><td>1189</td><td>-22</td><td>1148.4</td></tr><tr><td>12:55</td><td>1259</td><td>52</td><td>1189</td><td>-22</td><td>1150.6</td></tr><tr><td>13:10</td><td>1257</td><td>50</td><td>1191</td><td>-20</td><td>1149.2</td></tr><tr><td>13:25</td><td>1269</td><td>62</td><td>1187</td><td>-24</td><td>1150.2</td></tr><tr><td>13:40</td><td>1235</td><td>28</td><td>1187</td><td>-24</td><td>1146.2</td></tr><tr><td>13:55</td><td>1231</td><td>24</td><td>1197</td><td>-14</td><td>1151.6</td></tr><tr><td>14:10</td><td>1213</td><td>6</td><td>1193</td><td>-18</td><td>1150.0</td></tr><tr><td>14:25</td><td>1229</td><td>22</td><td>1203</td><td>-8</td><td>1149.2</td></tr><tr><td>14:40</td><td>1205</td><td>-2</td><td>1209</td><td>-2</td><td>1149.2</td></tr><tr><td>14:55</td><td>1217</td><td>10</td><td>1211</td><td>0</td><td>1150.2</td></tr><tr><td>15:10</td><td>1235</td><td>28</td><td>1239</td><td>28</td><td>1148.8</td></tr><tr><td>15:25</td><td>1195</td><td>-12</td><td>1263</td><td>52</td><td>1145.8</td></tr><tr><td>15:40</td><td>1265</td><td>58</td><td>1293</td><td>82</td><td>1144.8</td></tr><tr><td>15:55</td><td>1259</td><td>52</td><td>1257</td><td>46</td><td>1149.6</td></tr></table></body></html>

图（8)为赤经、赤纬与基准图像的指向偏差。利用公式(8),可计算指向的标准偏差， $S _ { R A } = 4 3 . 1 6 9 2 7 3 8 8$ $S _ { D E } = 2 5 . 2 8 1 8 5 9 3 8$ 。经过换算，赤经方向的指向误差约为 $3 6 . 6 9 ^ { \prime \prime }$ ，赤纬方向的指向误差约为 $2 1 . 4 9 ^ { \prime \prime }$ ，指向精度 $\leqslant 1 ^ { \prime }$ ，满足指向精度的指标要求。

$$
S = \sqrt { \frac { \sum _ { i = 1 } ^ { N } ( x _ { i } - \mu ) ^ { 2 } } { N } }
$$

![](images/311743a24acfad86a0038702fc237c4f6fb278eeb24bece1f1731623d5a1cce1.jpg)  
图8不同时间点对应的赤经（赤纬）指向偏差  
Fig.8Right ascension (declination) pointing deviation atdifferent time points

# 3.2 结论

本文通过对 SMAT轴系系统的升级改造，通过利用高精度的导行系统对太阳进行跟踪，记录太阳实时位置与绝对值编码器数值，并分段进行线性拟合建立起指向算法的控制方法。该方法成本低，可移植性强，对赤道式望远镜轴系的兼容性高，可以适用于使用年限较长的望远镜的升级改造。通过实际测试，指向精度优于 $1 ^ { \prime }$ ，实现了指向的功能要求，能成功将太阳像引入视场进行导行。

值得一提的是，目前的工作虽然已经达到了SMAT 使用需求，但还有进一步的提升空间，有许多因素可能会导致指向误差：望远镜本身轴系误差、指向算法误差、大气蒙气差甚至是图像质心与半径检测算法等，后期仍需通过量化分析建立误差模型来进一步提升指向精度。

致谢：感谢怀柔太阳观测基地的汪国萍、荆帅等观测人员在研究过程中给予的协助与支持，感谢荀辉、杨潇、张鑫伟、佟立越在研究过程中提供的帮助和宝贵意见，感谢王强提供的基于Hough 变换的太阳图像质心与半径检测算法，本项目研究过程中获得了国家自然科学基金（11427901、11427803）、中国科学院战略性先导科技专项(A类）（XDA15320102）、科学院关键技术人才项目、国家天文台台级调控项目的资助与支持，特此致谢。

参考文献

[1]林佳本,沈洋斌,朱晓明,邓元勇,曾真.怀柔太阳观测基地全日面磁场自动化观测系统[J].天文研究与技术,2013,10(04):392-396.  
[2]Solar Magnetism and the Activity Telescope at HSOS[J].Chinese Journal of Astronomy and Astrophysics,2007(02):281-288.  
[3]吴春晖,朱庆生,周小军.全日面太阳光学和磁场望远镜的自动跟踪与导行方法[J].天文研究与技术,2007(02):147-152+146.  
[4]郭晶晶,杨云飞,冯松,季凯帆,林佳本,曾真,王丙祥.太阳望远镜高精度导行方法[J].科学通报，  
2016,61(10):1112-1120.  
[5] BRETAGNON,FRANCOU. Planetary theories in rectangular and spherical variables. VSOP 87 solutions[J].1988,202(1-2):309-315.  
[6] 柳光乾．一米红外太阳望远镜控制系统研制[D].2011.  
[7]严灵杰．光电望远镜视轴指向及预测技术研究[D].中国科学院大学(中国科学院光电技术研究所),2019.  
[8]程晓莉，谢剑英，王林．绝对式编码器在电机定位中的应用[J]．控制工程,2007,14(5):548-550.  
[9]柯子博，晏磊，王东光．大气偏振中性点遥感观测系统研制与验证[J]．影像科学与光化学，2019,  
37(03):85.

# Shafting System Upgrade for The Solar Magnetism and Activity Telescope

Chen Chuiyu1,2,Guo Jingjing1,2,Lin Jiaben1,Deng Yuanyong 1,2 (1.University of Chinese Academy of Science，Beijing 1OoO49，China;

2.National AstronomicalObservatory，Chinese Academyof Sciences，Beijing 1Ool01，China，Email:cychen@nao.cas.cn)

Abstract: Inastronomical observation,telescopes need tobeable toquicklyand accuratelypointtotheobjectbody(such as the solar)andtrack them stably.Inthis paper,theshaft systemupgrade is performedforTheSolar MagnetismandActivityTelescope (SMAT)in Huairou Solar Observing Station(HSOS).Weuse 23-bit high-precision absolute encoderonthe servo motortoreplace theangleencoders withgraduatioonsteltape.Real-timecalculationofthecenterpositionofthesolarthrough VSOP87 planetary theory,andusingahigh-precisionguidingsystembaseonalargeareaCCDtocontinuouslytrack thesolarandrecordthepositionof thesun.The least square methodisused tosegmented fit thereal time positionofthesunandthevalueoftheabsoluteecoder. Finaly,the pointingalgorithmisestablishedandthesolarcenterpointing isrealized.According totheactualmeasurement,the pointing erorofrightascensiondirectionisabout36.69",andthatofdeclinationdirectionisabout21.49".Theproposedmethod mts therequirementsofSMAT,haslowcostandhighcompatibilityandisofreferentialsignificance totheupgradingofother equatorial telescopes.

Key words:Pointingcontrol,ointing error,haftinguprade,Solartelescope,olarobservation,Equatorialtelecope