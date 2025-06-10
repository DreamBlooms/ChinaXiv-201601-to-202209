# 基于多普勒测风激光雷达的锁频系统与激光测速系统的设计与实现

杜丽芳1，杨国韬」，程学武²,王继红」，岳川¹，陈林祥1(1.中国科学院国家空间科学中心空间天气学国家重点实验室，北京100190;2.中国科学院武汉物理与数学研究所，湖北武汉 430071)

摘要：在非相干多普勒测风激光雷达系统中，激光的线宽与频率的稳定性是影响测量结果准确性的两个重要因素。研制的激光雷达系统采用种子注入方法产生窄线宽脉冲激光，采用碘分子饱和吸收稳频的方法,利用VB 语言基于PID算法编写仪器控制程序,将种子激光器的频率锁定在碘分子吸收线1109线的高波数边缘上，长时间 $\mathrm { > } 4 \mathrm { ~ h } )$ 锁频的精度 $\leqslant 0 . 5 ~ \mathrm { M H z }$ ,频率的长期稳定度为 $3 . 5 5 \times 1 0 ^ { - 9 }$ 。设计了连续光测速系统，得出多普勒频移测得的实验值与实际斩波盘的速度值曲线，速度误差小于$0 . 4 ~ \mathrm { m / s }$ 。由此也说明，所设计的连续光测速系统可以对整个锁频系统进行校准。该实验也为测风激光雷达的建设提供指导意义。

关键词：多普勒测风激光雷达；锁频；PID；测速中图分类号：TN958.98 文献标志码：A 文章编号：1007-2276(2015)09-2562-07

# Design and realization of frequency locking system and laser velocity measuring system based on Doppler wind lidar

Du Lifang1，Yang Guotaol, Cheng Xuewu²，Wang Jihongl，Yue Chuan', Chen Linxiang (l.State Key Laboratory of Space Weather,National Space Science Center,CAS，Beijing lOol9o,China; 2.Wuhan Institute of Physics and Mathematics,CAS,Wuhan 43OO7l,China)

Abstract:In the noncoherent Doppler wind lidar system,the laser line width and frequency stability are two important factors influencing the accuracy of measurement results.The injection seeding technique method was used to obtain narrow linewidth of $5 3 2 \ \mathrm { n m }$ lidar.The iodine filters as receiv frequency discriminators and lock the transmiter laser frequency.Using VB language writing instrument control program based on PID algorithm,the frequency of seed laser locked in iodine molecular absorption lines, which was l lO9 line of high reflection on the edge.The frequency stability was better then $\pm 0 . 5 ~ \mathrm { M H z }$ for $^ \mathrm { ~ 4 ~ h ~ }$ ，the long-term frequency stability as $3 . 5 5 \times 1 0 ^ { - 9 }$ . Design the continuous light velocity measuring system，which concluded the cure about Doppler frequency shift and actual speed of chopped wave plate, the velocity error was less than $0 . 4 \mathrm { ~ m } / \mathrm { s }$ . This also shows that the laser velocity measuring system can be calibrated on the lock the frequency of the whole system. Thisexperiment also providesguidance significance for the construction of wind lidar.

Key words:Doppler wind lidar; frequency locking; proportion integration differentiation; velocity measurement

# 0引言

多普勒测风激光雷达是利用电磁波与运动物体作用的多普勒效应，以大气中气溶胶、大气分子等为示踪物，通过测量后向散射回波信号与发射激光的多普勒频移来反演大气风场。它是目前测量大气风场最先进的手段之一，可以在晴空条件下实时提供高精度、高时空分辨的大气风场信息[1-2]。文中所提到的激光雷达系统是在子午工程北京延庆台站研制并建设。

文中是通过种子注入技术将单纵模连续的种子激光注入[3到脉冲放大的激光腔中，实现了单脉冲激光放大输出[4]。在锁频系统中由单纵模连续激光器、碘分子吸收池、信号采集与输出板卡、探测器共同组成的闭环结构伺服反馈系统，利用VB语言控术，编写上位机软件，实现了对单频种子光输出频率的锁定，频率稳定在气态碘在 $5 3 2 { \mathrm { n m } }$ 处的强吸收线上。通过调节种子激光器的注入频率最终直接稳定了用于测风激光的频率。

种子激光频率锁定的精确性与稳定性，直接影响脉冲激光频率的精确性与稳定性，而这些将会影响大气回波信号的数据反演的结果。对于分析激光频率是否锁定在了实验系统中设计的频率上、以及锁频系统的稳定性，一般的方法就是通过长期进行监测，测量激光的长时间稳定性，以及通过一些别的检测手段进行数据对比。文中提出了以稳频系统的连续光测速[5的方法来验证锁频系统的可靠性，为测风激光雷达的建设提供指导意义。

# 1测风激光雷达锁频系统的原理及方法

在非相干检测多普勒测风激光雷达中，激光发射系统的频率稳定性对测风精度的影响是显著的。一般情况下，激光频率的稳定性低于 $4 ~ \mathrm { M H z / m i n }$ ,就会产生 $\mathrm { 1 m / s }$ 的测风误差，所以在测风激光雷达系统中均有激光稳频系统。文中研制的多普勒测风激光雷达系统就是采用非相干检测法，即大气后向散射光进入到高分辨率的干涉滤光器中进行多普勒频率检测，系统中所使用的稳频与鉴频滤波器均为碘分子滤波器[6]。

碘分子在可见区电子跃迁大约有2000多条吸收光谱线，其中有8根 $( 1 8 7 8 6 \mathrm { c m } ^ { - 1 } { \sim } 1 8 7 8 9 \mathrm { c m } ^ { - 1 } )$ 主要的多普勒展宽线在Nd：YAG的倍频光 $5 3 2 { \mathrm { n m } }$ 附近，其吸收线系数为 $1 \ 1 0 4 { \sim } 1 \ 1 1 2$ 。由于碘分子吸收线的峰值位置是碘分子固有的特性，所以是绝对不变的，这就为频率的标定提供了一个良好的准确的基准。在实验系统中，采用碘分子滤波器作为稳频器件，因此碘分子吸收线的特性对整个系统来说至关重要。在激光出射频率 $5 3 2 { \mathrm { n m } }$ 附近，综合吸收线的强度、形状、与周围吸收线的间距等因素，在实验系统中选用1109线作为频率锁定的标准。

该实验系统中，所使用的种子激光器只能发射$1 0 6 4 { \mathrm { n m } }$ 波长的连续激光，为了利用碘分子滤光器实现对种子激光的锁频，需要先将 $1 0 6 4 { \mathrm { n m } }$ 的连续光倍频得到 $5 3 2 { \mathrm { n m } }$ 的连续光，并将1109线吸收翼的侧翼作为锁频点，利用 $\mathrm { P I D ^ { [ 7 ] } }$ 反馈控制技术实现了种子激光的高精度锁频。首先通过调节种子激光器温度和PZT电压将倍频的 $5 3 2 { \mathrm { n m } }$ 激光频率调在碘分子滤光器1109吸收线右边缘中部，通过碘分子吸收池把光频率检测转换为光信号强度的检测，透过率的变化反映了种子激光输出频率的变化，根据透过率的变化通过PID反馈算法调整种子激光器的PZT电压，即调整 $5 3 2 { \mathrm { n m } }$ 激光频率使其稳定在吸收线某一点，实现种子激光器的频率锁定。

# 1.1碘泡温度稳定性测试与结果分析

碘分子吸收线的形状受其温度的影响很大。因此，碘分子滤波器的温度[的稳定性是影响激光稳频精度的重要因素。在实验设计的碘泡温控系统中，碘指与泡壁采用NTClOK测温热敏电阻作为探测器，采用PID控制方法，控制碘分子泡的温度，控制精度为 $0 . 0 1 \mathrm { { } ^ { \circ } C }$ 。为了将环境因素对碘分子泡的影响降到最低，实验中的碘分子泡腔体又加了温控装置，称之为碘室。碘室的设计思想是在碘分子泡的温控腔体外侧放置加热材料，由温控精度为 $0 . 1 \mathrm { { } ^ { \circ } C }$ 的温控仪对其进行整体碘室的温度控制。

在稳频实验进行前，先对碘泡的温控系统进行测试，保证稳频的可靠性。

在相同实验条件下，测试了不同温度下碘分子吸收线的情况，如图1所示。从图中可以得出，不同的温度下，碘分子的吸收线存在差异，所以利用单边缘稳频的方法，需要对碘泡进行精确的温度控制，以免带给测风计算系统误差。从图中可以看出，随着碘指温度的增加，碘分子1109吸收线光谱宽度加宽，吸收能力增强，这有利于提高检测频率。同时，随着碘指温度的增加，该边缘的斜率虽变化不是很大，但是边缘部分的线性范围明显减少，这对于检测频率的范围很不利的。综合考虑上述两方面因素，实际雷达系统中，碘指的温度[9选定在 $3 3 3 { \sim } 3 4 3 \mathrm { K }$ 之间。在实验稳频过程中，控制碘指温度为 $5 5 ~ \mathrm { ^ q C }$ ,泡壁温度为 $6 0 ^ { \circ } \mathrm { C }$ ,整个碘室温度设定为 $5 5 ^ { \circ } \mathrm { { C } }$ 。

![](images/023b08f82a8d4ec9751be1ed3542bbb2caa569568d354303cad96fbf15aa4e08.jpg)  
图1不同温度下碘分子的光谱吸收线

在实际测风雷达系统中，应达到激光雷达具有长时间运行的能力。为了保证所使用的碘分子滤光器系统能达到长时间的稳定性，满足整体测风雷达参数的要求，对碘分子滤光器系统进行了长期稳定性测量，结果如图2所示。在实验中，选用的碘指的温度为 $3 2 8 \mathrm { ~ K ~ }$ ，泡壁温度为 $3 3 3 \mathrm { ~ K ~ }$ ，整个碘室温度设定为 $3 2 8 \mathrm { ~ K ~ }$ 。在碘泡温控稳定之后，每隔1h扫一次碘泡的吸收谱线，共测试了四次。由图2可以看出，不同时间下的四条吸收谱线完全重合在一起，这说明所设计制作的碘分子滤光器的温控系统的稳定性与精度都达到实验要求，能够保证稳频的精度。

![](images/38400375e116295dd171f929d3ab81424a44eacac86c614c1e17f2fe27b92736.jpg)  
Fig.l Spectral absorption lines of iodine molecule at different temperatures

# 1.2种子激光器稳频系统实验装置

实验中多普勒测风激光雷达系统采用连续光稳频方法，最终将稳频之后的单频种子光注入到脉冲主激光器，形成激光雷达的发射系统。种子激光器内部频率的调节有两种方式：调节温度与改变激光腔内PZT加载电压的方法。其中温度调节属于粗调，调节速度慢，需要较长时间稳定，但是调节范围很大，可达 $2 0 { \sim } 3 0 \mathrm { G H z }$ ；调节腔内PZT加载电压方法属于细调，频率调节速度快，频率稳定时间极短，调节范围 $1 0 \mathrm { G H z }$ 。调节腔内PZT加载电压方法尽管调节波长范围有限但是调节速度快，而且完全覆盖了碘分子1109吸收谱线的范围。所以可以利用调节PZT的方法来快速锁定激光频率。文中所述锁频方法就是利用PID控制程序通过控制PZT上的电压对激光进行细调，最终达到锁频的目的，实验系统如图3所示。

锁频采用的 $5 3 2 { \mathrm { n m } }$ 激光是连续种子激光经过倍频系统得到的。输出的 $5 3 2 { \mathrm { n m } }$ 的光经过差分锁频系统，最终进入数据采集控制反馈系统进行数据分析处理，通过数字PID反馈控制程序产生的反馈电压信号经过高压放大后控制激光器的PZT，来实现对种子激光器输出频率的锁定。

![](images/40905dde40a797f9b2109912c8c048a598014d00b01b8078090684b43b299b3f.jpg)  
图2同一温度、相同时间间隔的碘分子的光谱吸收线 Fig.2 Spectral absorption lines of iodine molecule at the same temperatures under the same time interval   
图3稳频系统示意图  
Fig.3 Frequency stabilization system of experimental setup

# 1.3稳频系统的结果分析

系统工作时，首先通过调节种子激光器温度和PZT电压将倍频的 $5 3 2 { \mathrm { n m } }$ 激光频率调在碘分子滤光器1109吸收线右边缘中部,并确定锁频点[1]。在调节种子激光器的温度过程中，同时扫描碘分子吸收曲线如图4所示，此时确定锁频点为0.8，此值指的是经过分光镜分光后通过碘泡探测到的信号与直接探测到的信号的比值。确定锁频点后，打开锁频软件，在程序中输入锁频点的值，开始运行软件。在程序控制下锁频结果如图5所示，锁频精度 $\leqslant \pm 0 . 5 \ : \mathrm { M H z }$ 。另外，此种子激光器在自由运转的情况下，出厂报告每小时频率漂移 $\mathrm { 5 0 } \mathrm { M H z }$ ，实际测试结果如图6所示，预热后1h波长漂移为 $0 . 2 5 \mathrm { p m }$ ,约为 $6 3 . 5 0 \mathrm { M H z }$ 。

![](images/3b0bb12d8d3599d943bf75f215f855d5bdafa441ef0ceb94f932988d0081df7a.jpg)  
图4碘分子吸收线锁频点

![](images/615bc273039f6052cfc6fb9b87459dcf218553c29802cc62bd490a186425756d.jpg)  
Fig.4Lock frequencypoint of iodinemolecular

![](images/9f86855a446c44ded7d391f629614182d38f6193306d9b44e099e0e5cb3793af.jpg)  
Fig.5Measurement resultsof frequency-Locked   
图6自由运转种子激光器频率漂移 Fig.6Free running seeder laser frequency shifts

稳频后的长期稳定度为：

$$
S _ { \nu ( \tau ) } ^ { - 1 } { = } \frac { \Delta \nu ( \tau ) } { \bar { \nu } } { = } \frac { 1 \mathrm { M H z } } { 2 . 1 8 9 4 4 2 8 \times 1 0 ^ { 1 4 } \mathrm { M H z } } { = } 3 . 5 5 { \times } 1 0 ^ { - 9 }
$$

式中： $\bar { \nu }$ 为 $^ { 4 \mathrm { h } }$ 内频率的平均值。 $1 0 ^ { - 9 }$ 的稳定度完全可以满足探测的需求。

# 2激光测速系统实现

测风激光雷达作为一种测量预报的手段，风速测量的准确性是评判该雷达系统是否可以正常工作的标准[1]。一般在激光雷达研制成功后，均会对整个雷达系统进行风速的校准，常见的校准手段是与其他探测方法得到的结果进行比对，例如与探空仪，卫星数据，放气球等方法。由于这些方法自身存在一定的误差，精度有限。为此，文中实验系统搭建了连续光测速系统来初步验证锁频系统的精度与可靠性。

# 2.1实验原理

连续光测速原理与多普勒测风激光雷达测风原理是一致的，是利用电磁波与运动物体作用的多普勒效应，以斩波器作为硬目标，通过测量后向散射光信号与发射激光的多普勒频差来反演风速[12]。

激光多普勒测风原理如图7所示，发射激光频率为 $\nu _ { 0 }$ ,仰角为 $\theta$ ,探测物体的水平速的速度分量称为径向速度 $V _ { \mathrm { r } } = V \mathrm { c o s } \theta$ 。在探测物体 $B$ 点，观察到的激光频率为：

$$
\nu _ { \mathrm { l } } { = } \frac { \nu _ { \mathrm { 0 } } } { \sqrt { 1 { - } \frac { V _ { \mathrm { r } } ^ { 2 } } { c ^ { 2 } } } } \cdot ( 1 { + } \frac { V _ { \mathrm { r } } } { c } ) \approx \nu _ { \mathrm { 0 } } { \cdot } ( \frac { c { + } V _ { \mathrm { r } } } { c } )
$$

地面接收的后向散射光的频率为：

$$
\nu _ { \mathrm { l } } { = } \frac { \nu _ { \mathrm { 0 } } } { \sqrt { 1 { - } \frac { V _ { \mathrm { r } } ^ { 2 } } { c ^ { 2 } } } } \cdot ( 1 { + } \frac { V _ { \mathrm { r } } } { c } ) \approx \nu _ { \mathrm { 0 } } { \cdot } ( \frac { c { + } V _ { \mathrm { r } } } { c } )
$$

通过接收光与发射光之间的频移可以计算得到物体的径向速度：

$$
\Delta \nu = \nu _ { 2 } - \nu _ { 0 } \approx \nu _ { 0 } \cdot \frac { 2 V _ { \mathrm { r } } } { c }
$$

$$
V _ { \mathrm { r } } { = } \frac { c } { 2 } \cdot \frac { \Delta \nu } { \nu _ { \mathrm { 0 } } }
$$

![](images/4193c063bc743d0f358e30d97398c0b60385de96736b29bc966e03d69783f020.jpg)  
图5种子锁频测结果  
图7多普勒测风激光雷达原理图  
Fig.7Principle diagram of the Doppler wind lidar

由多普勒频移 $\Delta \nu$ 的正负可以判断物体运动的方向：若 $\Delta \nu$ 为正，则说明物体在径向上靠近雷达站运动；若 $\Delta \nu$ 为负，则说明物体在径向上远离雷达站

运动。

# 2.2实验装置

实验中采用斩波器做为硬目标，斩波器的斩波盘侧面贴有反光膜，激光入射到斩波盘上会产生散射光。斩波盘直径 $2 0 0 \mathrm { m m }$ ,斩波器自身带有编码器，可以调节和读取斩波盘的转动频率。采用与稳频碘分子泡相同的碘泡做为频率检测器件，利用差分法接收到后向散射光通过碘分子泡的信号和直接探测到信号。

在整个实验系统中，使用示波器进行接收并监测由光电探测器收到的信号，共有三个通道，分别为斩波器同步信号通道、通过碘泡信号通道和能量检测信号通道。接收到的原始信号如图8所示。实验中，为了不引入系统仪器误差，所用的光电探测器型号相同。由于斩波器对光的调制作用，反射光形成了一系列具有一定间隔的脉冲光信号。

![](images/770fed331a885b3807db7aa511089f4e14473427f514efc38e19c2fe27bd3fb8.jpg)  
图8示波器采集到的原始信号

# 2.3结果与讨论

基于实验中斩波轮共有四个反射面，而每个反射面的反射率也不尽相同，实验中选择了一个反射率最高的面采集信号数据 (未饱和)。在信号采集过程中，由于反射面并不是完全光滑，激光在扫过反射面过程中，两个通道的信号比会出现涨落，将一次采集的所有数据累加平均作为测试结果；在数据处理中，为保证数据的可靠性，只保留信噪比大于10的数据。

由于斩波器频率的不同，导致在测试点的线速度的不同。实验中，通过测试不同斩波器频率，设置斩波器频率为 $0 ~ \mathrm { H z } \ , 4 0 ~ \mathrm { H z } \ , 8 0 ~ \mathrm { H z } \ , 1 2 0 ~ \mathrm { H z } \ , 1 8 0 ~ \mathrm { H z } \ ,$ $2 0 0 \mathrm { { H z } }$ 进行测试，分析两通道接收到的信号比率，结果如图9所示。图10是测量的第二组数据，斩波器频率从 $0 { \sim } 2 0 0 \mathrm { H z }$ ,频率间隔为 $2 0 \mathrm { { H z } }$ 。对于斩波器的任一个频率，斩波盘的激光产生的频移量都是不相同的。频移量的不同使得后向散射光的频率不同。这样对于入射到碘泡中的后向散射光来说，碘分子的1109线上对不同频率的光有不同的吸收率。在上述测试结果中，通道比率是指探测器接收到的通过碘泡的信号与未通过碘泡的信号的比。从测试结果可以看出，随着斩波器频率的增加，光通过碘泡的透过率增加，激光频率向短波长方向移动，这与理论分析是一致的，两组测试结果也吻合得很好。

![](images/0689971791fb3dcc157c1f63955d80866a86d14a2f1096b7cda55b72bd5e05d5.jpg)  
图9斩波器频率间隔 $4 0 \mathrm { { H z } }$ 两通道的比率变化

![](images/3e0726e316bbdf68de7e5039e98a53e5992452d89360577c7f261ffd84075933.jpg)  
Fig.8 Oscilloscope collected original signal   
Fig.9 Chopper $4 0 \mathrm { { H z } }$ frequency interval with change of ratio of two channels   
图10斩波器频率间隔 $2 0 \mathrm { H z }$ 两通道的比率变化 Fig.10 Chopper $2 0 \mathrm { H z }$ frequency interval with change of ratio of two channels

利用激光雷达测速原理将通道比反演为对应的频移。

由实验原理可知，多普勒频移与径向速度的对应关系为 $V _ { \mathrm { r } } { = } \frac { c } { 2 } \cdot \frac { \Delta \nu } { \nu _ { \mathrm { 0 } } }$ ,其中 $\nu _ { 0 }$ 为发射激光频率。根据实验光路，可以测量出入射激光与入射面的夹角，反射光与反射面的夹角，入射点到斩波盘中心的距离，就可以计算得到入射点的径向速度的值，如图11中黑线所示。通过激光多普勒频移测得的实验值，如图

![](images/ce1b173d4772985c0601a2349c68164937dcc702e126cf97b6742f4953921119.jpg)  
图11不同斩波器频率对应的多普勒频移  
Fig.llDifferentchopperfrequency correspondingto theDoppler frequency shift

11圆点所示，将两者进行对比，可以看出多普勒频移测得的实验值与实际斩波盘的速度值是相吻合的,速度误差小于 $0 . 4 \mathrm { m / s }$ 。由此也说明，文中所研制的激光雷达系统中的稳频系统满足实验需求，可以进行整个系统的集成。

# 2.4误差分析

从实验结果来看，两者还是存在一定的误差，分析两个速度存在偏差的原因主要有以下几个方面：

(1)由于实验过程中所贴的锡纸的反射面并不完全光滑，故激光在扫过反射面的过程中，径向速度存在抖动，对应的多普勒频移也会存在抖动，带来计算误差；

(2)斩波轮自带的频率监测系统显示出的斩波频率可能与真实值有偏差；

(3)测量光点半径和入射角度时引入测量误差。

# 3结论

该实验系统采用碘分子饱和吸收稳频的方法，结合上位机仪器控制技术，将种子激光器的频率锁定在碘分子吸收线1109线的高波数边缘上，长时间$( > 4 \mathrm { h } )$ 锁频的精度 $\leqslant \pm 0 . 5 \ : \mathrm { M H z }$ ,在最终反演计算中带来 $0 . 2 5 \mathrm { m / s }$ 的风速误差，满足了测风激光雷达系统的要求。在整个激光雷达系统研制过程中，需要对设计的每一个细节进行验证，设计了连续光测速系统，对锁频系统的结果进行了验证，为测风激光雷达的建设提供指导意义。当然，在连续光测速系统中，还有许多影响因素需要探索和优化，比如激光入射到测试点的角度，斩波盘的直径大小，斩波盘测试面处反射率的影响以及斩波盘自身频率的稳定性等，这些因素可能都会对测试结果有影响，这些探索性的想法将在以后的工作中逐步完善。

# 参考文献：

[1]Garnier A L,Chanin M.Description of a Doppler rayleigh LIDAR for measuring winds in the middle atmosphere [J]. Applied PhysicsB,1992,55(1):35-40.   
[2]Souprayen C,Garnier A,Hertzog A. Rayleigh-Mie Doppler wind lidar for atmospheric measurements．I. Instrumental setup，validation,and first climatological results [J].Applied Optics,1999,38(12): 2410-2421.   
[3]Liu Z,Wu S,Liu B. Seed injection and frequency-locked Nd:YAG laser for direct detection wind lidar[J].Opt& Lasers in Eng，2007,39(3): 541-545.   
[4]Chen Weibiao,Zhou Jun，Liu Jiqiao，et al.Doppler lidar and it'sall solid-state single frequency laser [J].Infrared and Laser Engineering,2008,37(l):57-60.(in Chinese) 陈卫标，周军，刘继桥，等.多普勒激光雷达及其单纵模全 固态激光器[J].红外与激光工程，2008,37(1):57-60.   
[5]Wang Jie,Gao Jing，Yang Baodong，et al. Comparison of frequency lockingof $7 8 0 ~ \mathrm { ~ n m }$ diode laser via rubidium saturatedabsorptionandpolarizationspectroscopies [J]. Chinese Optics,201l,4(3):305-3l2.(in Chinese) 王杰，高静，杨保东，等．铷原子饱和吸收光谱与偏振光谱 对 $7 8 0 ~ \mathrm { n m }$ 半导体激光器稳频的比较[J].中国光学，2011, 4(3): 305-312.   
[6]Liu Lisheng，Zhang Heyong，Guo Jin,et al.High precise measurement oftargetvelocityusinglaserheterodyne technology [J].Opticsand Precision Enginering，2011,19 (10)：2366-2372. (in Chinese) 刘立生，张合勇，郭劲，等．用激光外差技术高精度测量目 标速度[J].光学 精密工程，20ll,19(10):2366-2372.   
[7]Yang Yang，Shen Fahua,Dong Jingjing.Designment for incident and receiving angle of verifying attachment for Doppler wind lidar[J]. Technical Exploration,2007,12:29- 31. (in Chinese) 杨洋，沈法华，董晶晶.多普勒测风激光雷达校准仪中激 光入射和接收角度设计[J].中国仪器仪表，2007，12:29- 31.   
[8]Yang Yang，Wang Li,Hao Haiyan，et al. Key technologies about doppler wind lidarspeed calibrator [J].Instrument Technique and Sensor,20l0(8):93-95.(in Chinese) 杨洋，王力，郝海燕，等.多普勒测风激光雷达速度校准仪 的关键技术研究[J].仪表技术与传感器，2010(8)：93-95.   
[9] Shen Hongchao，Wu Songhua,QinShengguang，etal. Frequency stability based on molecular absorption spectrum of single-frequency pulse laser[J].Chinese Journal of Lasers, 2014,41(9): 0902010-1-7. (in Chinese) 沈红超，吴松华，秦胜光，等．单频脉冲激光器的分子吸收 光谱频率稳定技术研究[J]．中国激光，20l4，41(9)： 0902010-1-7.   
[l0]He Zhigang，Deng Lunhua,Wang Guishi,et al．Nd:YAG laserfrequency stabilization technologybased on digital feedback control [J].Chinese Journal ofLasers，2Ol2，39 (7):0702009.(in Chinese) 贺志刚，邓伦华，王贵师，等．基于数字反馈控制的Nd: YAG 激光器频率稳定技术[J].中国激光，2012，39(7): 0702009.   
[ll]Deng Ke,Guo Tao,He Dingwu,et al.Effect of buffer gas ratioson the relationship between cell temperatureand frequency shifts of the coherent population trapping resonance [J].Appl Phys Lett,2008,92(2l):211104.   
[12] Liu Z,Wu D,Liu Jin T,et al.Low-altitude atmospheric wind measurement from the combined mie and rayleigh backscattering by doppler lidarwith an iodine filter[J]. Applied0ptics，2002，41(33):7079-7086.   
[l3]Tang Lei,Wu Haibin, Sun Dongsong,et al. Dunamic frequency tracking system for doppler lidar wind measurement based on Rayleigh scattering[J].Infrared andLaserEngineering,201l, 40(6):1049-1053.(in Chinese) 唐磊，吴海滨，孙东松，等.瑞利散射多普勒测风激光雷达 频率动态跟踪系统[J].红外与激光工程，20l1，40(6): 1049-1053.   
[14] Zhang Haiyang，Wang Jingfeng，Zhao Changming，et al. Coherent solid -state lidarand itsapplication in Doppler velocitymeasurement [J].Infrared and Laser Engineering, 2006,35(S):284-288.(in Chinese) 张海洋，王景峰，赵长明，等．固体相干激光雷达多普勒测 速实验[J].红外与激光工程，2006，35(S)：284-288.   
[15] QuYi.Technicalstatusand developmenttendencyof atmosphere optical remote and monitoring[J].Chinese Optics, 2013,6(6): 834-840.(in Chinese) 曲艺.大气光学遥感监测技术现状与发展趋势[J].中国光 学，2013,6(6):834-840.   
[l6]Liu Changwen,Luo Shijin，Liu Jie，et al.Counting LDA signal processor and its application [J].Optics and Precision Enginerring，2004，12(6):58l-586.(in Chinese) 刘昌文，罗诗金，刘杰，等．计数型激光测速仪信号处理器 及其应用研究[J].光学精密工程，2004，12(6)：581-586.