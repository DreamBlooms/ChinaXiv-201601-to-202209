# 探测器VLBI信号仿真方法

朱亚立1,4，郑为民1,2.3，童力1，童锋贤1，张娟1，刘磊1（1.中国科学院上海天文台，上海200030；2．中国科学院射电天文重点实验室，江苏南京210008；3．上海市导航定位重点实验室，上海200030；4.中国科学院大学，北京100049）

摘要：为研究VLBI对探测器的数据处理方法并评估其处理能力，现有做法需基于测站VLBI 终端接收的探测器信号进行。采用信号仿真方法可以根据设计轨道与信标特点利用计算机生成需要的探测器VLBI信号，相比试验观测具有独特优势。观测试验时，测站终端接收探测器下行射频信号，通过混频变换为中频信号，再进行数字化采集数据。仿真信号时，为减少计算规模，直接构造数字中频信号，二次采样后提取通道信号，获得数字终端的VLBI仿真信号。由于探测器相对VLBI测站运动，测站接收的探测器下行信号反映目标的视向速度变化。根据探测器信号时延模型，研究了探测器点频信号和有限带宽信号多普勒效应的模拟方法。通过仿真信号与VLBI终端接收信号的对比以及对VLBI相关处理结果的分析，验证了探测器VLBI信号仿真方法的可行性，为后续仿真技术在月球与火星探测器中的VLBI测定轨应用奠定了技术基础。

关键字：信号仿真；深空探测；VLBI；信标中图分类号： 文献标识码：A 文章编号：1672-7673

甚长基线干涉测量[1]（Very Long Baseline Interferometry，VLBI）是 20 世纪 60 年代后期出现的一种射电天文技术。它具有空间分辨率高、测量精度高的特点，现已广泛应用于天体物理、天体测量、天文地球动力学和深空探测领域[2]。我国于 2007 年首次在探月工程中使用 VLBI技术，建立了中国VLBI网（Chinese VLBINetwork，CVN）包括上海佘山站、北京密云站、云南昆明站、乌鲁木齐南山站射电望远镜和上海VLBI数据处理中心。中国VLBI网已参加了探月工程嫦娥系列探测器的多次任务，对关键弧段的快速精密测定轨发挥了不可替代的重要作用[5]。

VLBI测站由天线、接收机、数据采集终端、时间频率系统等组成，在工作时，各测站接收机天线汇集的射频信号放大后，经独立本振进行混频得到中频信号，然后传送至数字化终端，高速模数采样后作数字基带转换，得到所需频率通道的基频信号，最后经过编码，记录在磁盘或者直接通过网络传送到VLBI中心[5]。

为研究VLBI中心对不同探测器的测量方法，评估分析中心各功能模块的能力及整个系统的正确性、可靠性，目前的常规做法是在每次飞行任务前开展大量实际目标联测。对单目标探测器的实际观测演练可评估测站与系统的可靠性。但对于那些全新的深空探测任务，在正式任务前有时难以找到合适的探测器作为试验对象。比如在后续探月工程中，将要开展针对月球轨道的交会对接，届时VLBI需要进行对月球距离的两个动态目标的同波束测量。显然，目前没有类似的实际探测器可作为VLBI动态双目标的观测对象。若采用探测器VLBI信号仿真方法，则可根据探测器的数量、轨道、信标等特点，模拟生成VLBI终端接收的不同探测器信号，提供月球轨道双目标同波束VLBI测量数据，用于研究和改进VLBI处理模块。通过仿真与实际演练两种方法结合，可较好地评估VLBI中心与整个系统对双（多）目标探测器测量能力。因此，研究VLBI信号仿真技术有重要意义与迫切工程需求。

在探月工程中，探测器下行VLBI射频信号为S/X频段，采用调相方式，调制信号在形式上主要包括点频信号和有限带宽信号两类。在仿真信号时，没有直接仿真射频信号，而是先将信号从射频变换至数字中频，然后再对中频信号采样，提取通道信号，最终生成用于验证VLBI数据处理系统的仿真数据，这样既完整地保留了调制信号频谱主要特性，又避免了直接处理需极高采样率的射频信号。

# 1．探测器信号结构

在探月工程中，探测器VLBI下行射频信号采用调相方式，包括遥测信号、单向差分测距（DOR）信号、测距信号、残留遥控信号（图1)。其中，下行载波、测距信号（测距主音和测距次音）和单向差分测距信号为点频信号；遥测信号和遥控信号为经过相位调制的有限带宽信号。这些信号统一调制在下行信号的主载波上，数学模型[5为

$$
\begin{array} { l } { { s ( t ) = \sqrt { 2 P _ { T } } \sin \left( 2 \pi f _ { c } t + \theta _ { 1 } d _ { 1 } ( t ) + \theta _ { 2 } d _ { 2 } ( t ) \right. } } \\ { { \left. \qquad + \phi _ { 1 } \mathrm { s i n } ( 2 \pi f _ { 1 } t ) + \phi _ { 2 } \mathrm { s i n } ( 2 \pi f _ { 2 } t ) \right) } } \end{array}
$$

其中， ${ \mathrm { : } } P _ { T }$ 为总功率； $\mathcal { f } _ { c }$ 为载波频率； $d _ { 1 } ( t )$ 为遥测信号； $\theta _ { 1 }$ 为遥测信号的调制指数； $d _ { 2 } ( t )$

为遥控信号； $\theta _ { 2 }$ 为遥控信号的调制指数； $\mathcal { f } _ { 1 }$ 为测距信号； $\phi _ { 1 }$ 为测距信号的调制指数； $f _ { 2 }$ 为DOR信号； $\phi _ { 2 }$ 为 DOR信号的调制指数。

![](images/fda1cec51c66822750a46d2802b02e3dac777f7cd3ae7846de043081309b89f6.jpg)  
图1X波段下行信号上边带频谱示意图Fig.1 The spectrum of X band downlink signal

# 2．仿真原理与实现方法

2.1探测器信号时延模型构造

VLBI测站与探测器之间存在相对运动，因此在仿真时要考虑相对运动效应引起的测站接收探测器信号的时间延迟（时延）及其变化[5]。时延包含几何时延、引力时延、天线时延修正、源结构时延修正、中性大气与电离层时延修正等[，其中，几何时延是理论时延的主要部分，随目标的运动而变化。

设地心 $o$ 、测站 $A$ 及探测器 $B$ （图2）。 $g _ { 0 } ( t )$ 表示 $t$ 时刻参考点（地心）接收到信号波前的光行时； $g _ { 1 } ( t )$ 表示 $t$ 时刻参考点（地心）信号波前超前到达测站的光行时； $g _ { 2 } ( t )$ 表示 $t$ 时刻参考点（测站）接收到信号波前的光行时。若 $t _ { 2 }$ 时刻从探测器 $B$ 发出信号，同一波前到达地心 $o$ 、测站 $A$ 的时刻分别为 $t _ { 0 } , t _ { 1 }$ ，则根据定义 $g _ { 0 } ( t _ { 0 } )$ 、 $g _ { 1 } ( t _ { 0 } )$ 及 $g _ { 2 } ( t _ { 1 } )$ 分别为

$$
\begin{array} { r } { g _ { 0 } ( t _ { 0 } ) = t _ { 0 } - t _ { 2 } } \\ { g _ { 1 } ( t _ { 0 } ) = t _ { 1 } - t _ { 0 } } \\ { g _ { 2 } ( t _ { 1 } ) = t _ { 1 } - t _ { 2 } } \end{array}
$$

显然，

$$
{ \boldsymbol g _ { 2 } ( t _ { 1 } ) = \boldsymbol g _ { 0 } ( t _ { 0 } ) + \boldsymbol g _ { 1 } ( t _ { 0 } ) }
$$

![](images/415aa656dc66546b35e0ddef8b15a4e2e5dd186cd3e147692b3a61791f5fb647.jpg)  
图2VLBI时延示意图Fig.2 The diagram of VLBI delay

在实际应用中，每个观测弧段的时延模型都以五次时延多项式表示：

$$
g ( t ) = b _ { 0 } + b _ { 1 } t + b _ { 2 } t ^ { 2 } + b _ { 3 } t ^ { 3 } + b _ { 4 } t ^ { 4 } + b _ { 5 } t ^ { 5 } ,
$$

其中， $b _ { 0 } , b _ { 1 } . . . . b _ { 5 }$ 为时延模型多项式系数。

根据实际时延模型 ${ g } _ { 0 } ( t ) , { g } _ { 1 } ( t )$ ，用最小二乘法作五次多项式拟合，得时延模型 $g _ { 2 } ( t )$ 。

# 2.2时延模型线性近似

为减少计算量，在短时间内假设时延模型随时间线性变化，即

$$
g _ { 2 } ^ { \prime } ( t ) = b _ { 0 } + b _ { 1 } t ,
$$

其中，系数 $b _ { 0 } , b _ { 1 }$ 在短时间内为恒常数，忽略时延模型 $g _ { 2 } ( t )$ 高次项。

在短时间内用（5）式表示线性化时延模型存在一定误差，误差大小取决于用线性近似的时间长度和五次时延多项式中高次项系数。相关处理机使用皮秒量级的时延模型精度足以满足应用需求，故误差值在0.01ps（1e-14s)以内的模型误差即可视为满足仿真精度要求。在较短的观测时间内，时延模型 $g _ { 2 } ( t )$ 的二次项是线性近似的主要误差项，其系数 $b _ { 2 }$ 一般为e-11量级，要想使得该项引起的时延误差小于0.01ps,选定的线性化时间长度应小于0.01s。其他高次项的系数 $b _ { 3 }$ ， $b _ { 4 }$ ， $b _ { 5 }$ ，一般在e-14量级，由此引起的误差可忽略。

# 2.3构造中频信号

探测器下行载波信号的类型主要包括点频信号和有限带宽信号。其中点频信号包括：载波、测距信号和单向差分测距信号。有限带宽信号包括遥测信号和遥控信号，是以正弦波为载波的调相信号，调制方式为PCM/PSK/PM，一般可表示为S $\mathrm { i n } \left( 2 \pi f t + \theta \right)$ ，用相位 $\theta$ 的变化传递数字信息。对于二进制相移键控信号， $\theta$ 以 $0 / \pi$ 交替变化表示二进制位 $_ { 0 / 1 }$ ，1对应相位0，-1对应相位 $\pi$ 。因此遥测和遥控信号又可表示为 $A \sin \left( 2 \pi f t \right)$ ， $\mathcal { A }$ 随相位 $\theta$ 的变化而变化。

为完整地保留调制信号及其边带频谱，选择中频信号约为60MHz。有限带宽信号的码速率最大为 2048bit/s，码元变化周期是采样周期的两万九千多倍。在一个码元周期内，有限带宽信号保持不变，对其采样可仿真遥测和遥控有限带宽信号。因此，需选择合适的时间尺度对点频信号和有限带宽信号采样，仿真中频信号。

为简约起见，根据（1）式探测器转发的下行信号一般形式，分析其中典型的点频信号、有限带宽信号多普勒效应影响。信号表达式如下：

$$
f ( t ) = \sin { ( 2 \pi f _ { c } t + \theta _ { 1 } A \sin { ( 2 \pi f _ { 3 } t ) } + \phi _ { 2 } \mathrm { s i n } ( 2 \pi f _ { 2 } t ) ) } ,
$$

其中， $f _ { c }$ ， $f _ { 2 }$ 分别为载波和点频单向差分测距信号； $\mathcal { f } _ { 3 }$ 为有限带宽遥测信号； $A$ 为遥测信号的幅值； $\theta _ { 1 } , \phi _ { 2 }$ 为调制系数。

测站 $t$ 时刻接收的信号 $\tilde { f } ( t )$ 是探测器在 $t \mathrm { ~ - ~ } g _ { 2 } ( t )$ 时刻发出的，短时间内假设时延模型随时间线性变化，用 $g _ { 2 } ^ { \prime } ( t )$ 代替 $g _ { 2 } ( t )$ ， $\tilde { f } ( t )$ 与探测器转发的 $\boldsymbol { f } ( \boldsymbol { t } )$ 关系是

$$
\tilde { f } ( t ) = f ( t - g _ { 2 } ^ { \prime } ( t ) ) ,
$$

将（5）式和（6）式代入（7）式，得到：

$$
\begin{array} { l } { \displaystyle { \widetilde f ( t ) = \sin { ( 2 \pi f _ { c } ( ( 1 - b _ { 1 } ) t - b _ { 0 } ) + \theta _ { 1 } { \cal A } \sin 2 \pi f _ { 3 } ( ( 1 - b _ { 1 } ) t - b _ { 0 } ) } . } } \\ { \displaystyle { \quad \quad + \phi _ { 2 } \sin 2 \pi f _ { 2 } ( ( 1 - b _ { 1 } ) t - b _ { 0 } ) ) } } \end{array}
$$

对比（6）式，测站接收信号 $\tilde { f } ( t )$ 的载波 $\textstyle f _ { c }$ 和信号 $\mathcal { f } _ { 3 }$ ， $f _ { 2 }$ 发生频率偏移，体现了信号传输中由于相对运动产生的多普勒效应。频率偏移量分别为 $b _ { 1 } f _ { c }$ 和 $b _ { 1 } ( f _ { c } + f _ { 3 } ) , b _ { 1 } ( f _ { c } + f _ { 2 } )$ 。

根据（8）式，探测器下行信号在频域上表现为关于载波左右对称，其频谱主要分布在$\left[ \left( 1 - b _ { 1 } \right) \left( f _ { c } - f _ { \operatorname* { m a x } } \right) , \left( 1 - b _ { 1 } \right) \left( f _ { c } + f _ { \operatorname* { m a x } } \right) \right]$ ，其中 $\boldsymbol { f } _ { \mathrm { m a x } }$ 为max $( f _ { 3 } , f _ { 2 } )$ ， $b _ { 1 } \ll 1$ 。

构造中频信号 ${ \hat { f } } ( t )$ 如下：

$$
\begin{array} { l } { { \tilde { { \cal F } } ( t ) = \sin { ( 2 \pi ( f _ { c } ( 1 - b _ { 1 } ) - f _ { d } ) t - f _ { c } b _ { 0 } ) } + \theta _ { 1 } A \sin { 2 \pi f _ { 3 } } ( ( 1 - b _ { 1 } ) t - b _ { 0 } ) } } \\ { { + \phi _ { 2 } \sin { 2 \pi f _ { 2 } } ( ( 1 - b _ { 1 } ) t - b _ { 0 } ) ) } } \end{array}
$$

其中， $f _ { d }$ 为信号起始频点 $( 1 - b _ { 1 } ) ( f _ { c } - f _ { \operatorname* { m a x } } )$ 。

对比（9）式与（8）式，只是载波频率发生变化，其余信号不变。即通过降低载波频率，

将信号从射频搬移到中频，且信号 $f _ { 3 } , f _ { 2 }$ 前后保持不变。

127

综上，VLBI测站接收信号是添加时延的射频信号，由（1）式添加时延并降低载波频率，得到包含多普勒效应的中频信号，形式如下：

$$
\begin{array} { l } { { \tilde { s } ( t ) = \sqrt { 2 P _ { T } } \sin { ( 2 \pi ( f _ { c } ( 1 - b _ { 1 } ) - f _ { d } ) t - f _ { c } b _ { 0 } ) } } } \\ { { + \theta _ { 1 } A \sin { 2 \pi f _ { 3 } } ( ( 1 - b _ { 1 } ) t - b _ { 0 } ) + \theta _ { 2 } A ^ { \prime } \sin { 2 \pi f _ { 4 } } ( ( 1 - b _ { 1 } ) t - b _ { 0 } ) } } \\ { { + \phi _ { 1 } \sin { 2 \pi f _ { 1 } } ( ( 1 - b _ { 1 } ) t - b _ { 0 } ) + \phi _ { 3 } \sin { 2 \pi f _ { 2 } } ( ( 1 - b _ { 1 } ) t - b _ { 0 } ) ) } } \end{array}
$$

其中， $\mathcal { f } _ { 4 }$ 为遥控信号； $A ^ { \prime }$ 为遥控信号幅值。

2.4VLBI终端信号仿真

图3显示了仿真VLBI终端接收信号实现流程。先仿真带有多普勒效应的探测器VLBI下行中频信号，再滤波得到某个通道的频率区间，通过希尔伯特变换保留正频率部分，再通过数字变频移频至基带，经希尔伯特逆变换取实信号，最后通过重采样降低采样率得到通道实信号。通道宽度为2MHz时，采样率取4MHz。

![](images/adde9a081c63bdfbafe895375c8109c8cd2f77e5e744b75ab22143b597a0e4a5.jpg)  
图3信号仿真流程图Fig. 3 Steps of signal simulation

# 3．数值试验

3.1仿真探测器下行中频信号

根据上述方法采用某月球探测器信标实际参数仿真了探测器VLBI下行中频信号，其中包含测距信号（500kHz 主音频率）、遥测信号（副载波 65.536kHz 且码速率 256bit/s）和两对单向差分测距信号。高频信号起始频点 $f _ { d }$ 为8460MHz，降低载波频率后生成探测器下行中频信号，采样率117MHz，快速傅里叶变换点165000。

![](images/4f817e8290468e8143c4319d5d24c444be0934b8fafadf7771d61c38e432b8d1.jpg)  
图4探测器下行中频信号频谱图  
Fig.4 The spectrum of downlink probe quasi-intermediate-frequency signal

图4显示带宽58.5MHz的探测器下行中频信号频谱。图中，箭头3为载波信号，2和4是距载波约3.85MHz的第1对单向差分测距信号（DOR1)；1和5 是距载波约19.27MHz 的第2对DOR信号（DOR2)，载波两侧 500kHz处是测距主音信号。另外，有限带宽的遥测信号（带宽约0.5kHz）靠近载波。

测距信号、遥测信号、单向差分测距信号关于载波对称，调制系数决定各信号的功率分配，其中载波、测距信号和单向差分测距信号较为明显。由于快速傅里叶变换的栅栏效应使图中载波两侧对应频点幅值产生细微差别。其他信号谐波项能量较小，幅度基本在-180dB以下。

# 3.2可行性验证

通过仿真信号与VLBI终端接收信号的对比以及对VLBI相关处理结果的分析，验证了探测器VLBI信号仿真方法的可行性。

图5中（a）为实际信号单通道自功率谱，从中可观察到0.96MHz处的载波信号；距离载波 500kHz、65.536kHz 的测距主音信号和遥测信号；其他为信号谐波项。

图5中（b）为仿真VLBI终端接收信号自功率谱（采样率4M，FFT点262144，采样1s)，包含载波信号、测距信号（500kHz主音频率）、遥测信号（副载波65.536kHz且码速率1024bit/s）、高斯白噪声信号。频率0.968MHz处为载波信号，测距主音信号和有限带宽的遥测信号分别距离载波500kHz、65.536kHz,关于载波对称。距离测距主音65.536kHz、131.072kHz且关于测距主音对称的为遥测信号谐波项。

仿真信号与对应的实际信号对比表明，载波信号、测距信号、遥测信号的频率和功率分配与实际信号一致，噪声信号的功率和分布也与实际信号相同，验证了仿真方法的可行性。

![](images/45bc330af51e1d063ad4e786bc29c3507f63a999406d3866b355e75662eb13e0.jpg)  
图5单通道自功率谱图（A）实际信号；（B）仿真信号 Fig. 5 The auto-power spectrum of channel signal.(A） The auto-power spectrum of real signal; (B）The auto-power spectrum of simulation signal

探测器VLBI下行中频信号分别添加不同时延模型，仿真两台站终端接收信号（采样率4M，FFT点512，采样1秒)。经过VLBI相关处理，可得互功率谱幅度和相位图（图6)。图6 中（C）的幅度谱显示，载波信号和遥测信号在[0.8MHz,1.2MHz]频段，遥测信号的谐波项和测距信号在[0.4MHz,0.6MHz]，[1.4MHz,1.6MHz]频段。图6中（D）的相位谱显示，在载波信号、遥测信号、测距信号分布的主要频段相位谱有明显相关条纹，其它频段的点由于信号较弱，相位分布弥散，条纹较弱，验证了不同台站接收的探测器VLBI下行仿真信号的相关性。

![](images/0b93a0220359661cea54af3f7336fe023dd3d0e84827c8fd12556157459069f7.jpg)  
图6仿真两站信号互功率谱图（a）幅度谱；（b）相位谱与条纹 Fig.6 The cross-power spectrum of two station simulation signal.（a） The amplitude spectrum; (b）The phase spectrum and strip

# 4.结论

本文在研究探测器信号结构的基础上，分析了包含探测器下行点频信号和有限带宽信号的VLBI终端信号仿真方法，构造了中频信号仿真VLBI数字终端接收信号。采用最小二乘法可构造出满足精度的时延模型，用于模拟多普勒效应。通过仿真数字终端信号与实际信号的比较以及对不同台站的仿真信号作相关处理，验证了探测器VLBI信号仿真方法的可行性。后续建立仿真各模块误差分析模型，完善仿真系统，为月球探测器VLBI信号仿真的应用，乃至火星探测器VLBI信号仿真的研究打下良好的基础。

# 参考文献：

[1] Thompson A R, Moran JM, Swenson Jr G W. Interformetry and synthesis in radioastronomy[M]. Weinheim: Wiley Vch & Sons, 2004: 33-37.  
[2] 魏杰昌，郑为民，童力．带有时延的VLBI数字基带信号仿真[J]．中国科学院上海天文台年刊，2015(36)：124-135.

Wei Jiechang, Zheng Weimin， Tong Li. Simulation of VLBI digital baseband signal with time delay[J]. Annals of Shanghai Astronomical Observatory Chinese Academy of Sciences， 2015(36) : 124-135.

[3] 江悟，沈志强，舒逢春，等．利用 DiFX 处理 CVN 天文观测数据进展[J]．天文学进展，2014，32（4)：516-524.  
Jiang Wu， Shen Zhiqiang， Shu Fengchun，et al. The progress of adapting DiFX correlator for  
Chinese VLBl network[J].Progress in Astronomy, 2014,32(4): 516-524.  
[4] 郑鑫，刘庆会，吴亚军，等．基于同波束VLBI差分相延迟的“玉兔”月球车动作监视分析[J]．中国科学：物理学 力学 天文学，2014，44（8)：872-878.  
Zheng Xin, Liu Qinghui, Wu Yajun, et al. Motion monitoring and analysis of Chang'E-3 rover based  
on same-beam VLBl differential phase delay[J]. Science Sinica: Physica， Mechanica &  
Astronomica,2014,44(8): 872-878  
[5] 钱志瀚，李金岭．甚长基线干涉测量技术在深空探测中的应用[M]．北京：中国科学技术出版社，2012：1-14.  
[6] 童锋贤．深空探测器VLBI相位参考测量关键技术研究[D]．北京：中国科学院大学，2016.  
[7] 陈中，郑为民.VLBI软件相关处理机现状和发展趋势[J].天文学进展，2015,33 (4): 489-505.  
Chen Zhong， Zheng Weimin. Current status and development of VLBl software correlator[J].  
Progress in Astronomy, 2015,33(4): 489-505.

# Simulation method of Probe VLBl Signal

ZHU Yali1.4， ZHENG Weimin1,2.3.\*， TONG Li1，TONG Fengxian1， ZHANG Juan1，LIU Lei1 1.Shanghai Astronomical Observatory,Chinese Academy of Sciences,Shanghai 20030; 2.KeyLaboratory of Radio Astronomy,Chinese Academy of Sciences,Nanjing 210008; 3.Shanghai Key Laboratory of Navigation and Positioning,Shanghai 2O0030; 4.University of Chinese Academy of Sciences,Beijing 100049.

Abstract:VLBI (Very Long Baseline Interferometry)technique is an important method for orbit measurement of deep space probe. In order to research the data processing methods of the VLBI center and evaluate the measurement capability of the VLBI system, at present the routine method is observing actual deep space probe by carrying out large observation experiment to get probe signal that received by VLBI terminals. Compared with actual observation, simulating probe signal based on the characteristics of the track and beacon is a better choice. The actual downlink signal is radio-frequency signal, which will be converted to intermediate-frequency signal,then collected by receiver. In simulation,we construct the intermediate-frequency signal directly to reduce the amount of calculation，and generate the digital terminal signal via resampling.Because of the relative motion between the probe and the VLBI station,the frequency of the signal shifts accordingly, which is called Doppler effect. To simulate the actual probe signal, we build the delay model,andinvestigate the simulation methodabout theDoppler effect of the typical point frequency signal and finite bandwidth signal. By comparing the simulated signal with the actual signal received by VLBI terminal, and analyzing the VLBI correlation result， the feasibility of the simulation method is verified,which paves the road forthe following VLBI application in the moon and Mars.

Key words:signal simulation; deep space exploration; VLBI;beacon