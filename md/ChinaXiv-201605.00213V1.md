# 二维耦合光学摆镜伺服控制系统

毛博年1²孟 新」卞春江」高 东」张 磊1

(1.中国科学院空间科学与应用研究中心复杂航天系统电子信息技术重点实验室,北京100190；2.中国科学院大学 ,北京 100049)

摘要：二维耦合光学摆镜是扫描式星载红外光学系统的关键运动部件，其运动特性对伺服系统提出了高精度位置控制与运动解耦的特殊要求。在建模与仿真分析的基础上，提出了一种新的耦合偏移补偿与分割步进的解耦策略，采用位置环与速度环双闭环的PID控制算法，使用有限转角力矩电机和高精度旋转变压器作为执行与测量元件，以DSP为核心构建了二维耦合光学摆镜伺服控制系统。实验结果表明：该方法设计的控制系统二维运动解耦正确,控制精度高，响应时间短，动态特性好且超调小，可厂泛应用于高精度摆动扫描控制系统的研究领域，具有很好的工程应用前景。

关键词：伺服控制系统；运动解耦；PID；有限转角力矩电机中图分类号：TP275 文献标志码：A 文章编号：1007-2276(2015)02-0544-05

# Servo control system in two-dimensional coupled optics swing mirror

Mao Bonianl,²,Meng Xin1，Bian Chunjiang1,Gao Dongl,Zhang Leil .KeyLaboratory of Electronics and Imformation Technology for Space Systems,CSSAR,CAS,Beijing lOol9o,China; 2.University of Chinese Academy of Sciences,Beijing lOoo49,China)

Abstract: Two-dimensional coupled optics swing mirror is a core module in an infrared optical scanning system of space，which demands special requirements of high precision and decoupling movement in a servo control system.A novel decoupling strategy called coupled ofset compensation and segmentation stepping method was proposed based on accurate system modeling，abundant simulating and analysis results.The proposed servo control system of optics swing mirror was mainly constructed with a DSP chip,high precision brushless resolvers and limited angle brushless torque motors，which adopted position feedback and velocity feedback by PID algorithm. The experimental results indicate that the novel decoupling strategies are correct and that the servo control system makes the swing mirror achieve high precision movement which has a good dynamic characteristics，short response time and small overshoot. The method applied to the servo control system can be widely used in the field of high-precision swing scanning control system and possesses a great application prospect.

Key words: servo control system；decoupling movement;PID；limited angle brushless torque motor

# 0引言

二维耦合光学摆镜(以下简称摆镜)是扫描式星载红外光学系统的关键运动部件，其运动的高精度位置控制及运动解耦十分关键，直接影响着系统的性能。

目前，国内外对有限转角力矩电机伺服控制系统的研究主要应用在导弹陀螺、航空伺服阀、导弹舵机、雷达天线、电子调速机构上,且比较成熟[1-4]。而摆动扫描控制系统作为运动控制系统的一种形式，主要应用在激光测距仪、红外自标模拟器、摆动式红外地球敏感器等航天领域，国内外关于摆动扫描控制系统高精度快速响应方面，尤其是具有运动耦合关系的二维摆动扫描控制系统的研究相对薄弱，因此，文中对具有二维耦合机构的光学摆镜伺服控制系统进行了深入研究。

# 1摆镜工作原理

二维耦合摆镜结构如图1所示。其中轴1、轴2、轴3上的传动轮直径相等，轴1称为方位轴，轴3称为俯仰轴。设轴1、轴2、轴3的转角分别为01、02、03,则可推出：

$$
\left\{ \begin{array} { l l } { \mathrm { M 1 ~ } \ddag \ddag \iff \iff } \\ { \mathrm { M 2 ~ } \ddag \ddag \iff \iff } \end{array} \right.
$$

![](images/717ea2a514220d7e7b6b4cb7aa121b2420f28f6f66101f48752b7142b561989e.jpg)  
图1光学摆镜示意图  
Fig.l Schematic diagram of optics swing mirror

摆镜工作原理如图2所示，通过控制方位轴与俯仰轴电机的转动，可使反射镜进行方位和俯仰运动，最终使像点在像方坐标系 $( x , y )$ 上做指定轨迹的二维运动。

摆镜对伺服控制系统的要求是：在 $\pm 2 . 5 ^ { \circ }$ 的范围内，以 $1 5 ^ { \circ } / \mathrm { s }$ 的速度实现误差不超过 $\pm 0 . 0 5 ^ { \circ }$ 的精确运动，且像点二维运动轨迹偏差不超过 $\pm 0 . 0 5 ^ { \circ }$

Incident light Optical lens Reflector Image point Pitch:axis Azimuth:axis Acoordinate ： systemof Angles ofmotor1 image space andmotor2s,t (x,y） Angles of azimuth and pitch axis u,v

# 2摆镜数字控制器

二维耦合光学摆镜系统是一个双输入双输出的耦合系统，俯仰轴和方位轴之间不仅存在位置耦合，而且还存在由反射镜及其传动机构的转动惯量引起的动态力矩耦合。故首先应消除俯仰轴和方位轴之间的位置和力矩耦合，然后再将系统分解为两个相互独立的角位移伺服系统进行控制器的设计与实现。

# 2.1位置解耦策略

摆镜像方坐标系为平面直角坐标系，如图3所示。其中，定义原点位于出瞳处光学成像圆视场中心， $x$ 为水平坐标轴， $y$ 为垂直坐标轴， $( x , y )$ 表示像点在圆视场像面上的坐标位置。

![](images/65222df07ed2f30b45b18deb395f426e5b1424fa2e1adb59481908d779382838.jpg)  
图2摆镜光学成像示意图  
Fig.2 Image-forming diagram of mirror   
图3摆镜运动轨迹示意图  
Fig.3Trajectory of the swing mirror

反射镜从光学零位分别沿方位轴与俯仰轴分别逆时针方向转动 $\boldsymbol { u } _ { \boldsymbol { \cdot } \boldsymbol { \nu } }$ ,由公式(1)可以推出：

$$
\left\{ \begin{array} { l l } { \displaystyle u = \frac { \varphi ( s - s _ { 0 } ) } { 2 ^ { n } } } \\ { \displaystyle \nu = \frac { \varphi ( t - t _ { 0 } ) } { 2 ^ { n } } - \frac { \varphi ( s - s _ { 0 } ) } { 2 ^ { n } } } \end{array} \right.
$$

式中： $n$ 为M1和M2数字绝对式角位置传感器的分辨率， $\varphi$ 为其满量程角度。设当 $s { = } s _ { 0 }$ 且 $\scriptstyle t = t _ { 0 }$ 时，光点位于 $( x , y )$ 的原点，则定义绝对转角 $s { = } s _ { 0 }$ 且 $\scriptstyle t = t _ { 0 }$ 为系统的光学零位。又根据图2中两组光学透镜的特性可知：

$$
\left\{ { \begin{array} { l } { x = { \frac { u } { \alpha } } } \\ { y = { \frac { \nu } { \beta } } } \end{array} } \right.
$$

式中： $\alpha$ 与 $\beta$ 为光学放大系数。则有：

$$
\left\{ \begin{array} { l } { { \displaystyle { s = \frac { 2 ^ { n } \alpha x } { \varphi } } } } \\ { { } } \\ { { \displaystyle t = \frac { 2 ^ { n } ( \alpha x + \beta y ) } { \varphi } + t _ { 0 } } } \end{array} \right.
$$

上式为摆镜运动位置解耦的数学模型。由此模型可知，摆镜轴1处于不同的位置时，对轴2产生不同的位置偏移，可在轴2输入通道加上轴1对其耦合的位置偏移作为轴2最终位置给定信号，即摆镜的耦合关系可采用耦合偏移补偿的策略进行位置解耦。

如图3所示，当像点从 $A ( x _ { 1 } , y _ { 1 } )$ 运动至 $B ( x _ { n } , y _ { n } )$ 时，根据公式(4)可分别计算出点 $A$ 和 $B$ 对应的电机Ml与M2的绝对转角 $( s _ { 1 } , t _ { 1 } )$ 与 $( s _ { n } , t _ { n } )$ ,即实现了摆镜的位置解耦。

# 2.2力矩解耦策略

将像点 $A , B$ 经过位置解耦后的电机参数发送至控制器，像点会从 $A$ 点运动至 $B$ 点。然而，由于驱动轴1和轴2的电机M1与M2的实际运动方向、速度大小的差异，轴1和轴2通过钢带相连，存在阻力形式的耦合力矩，将导致像点无法从 $A$ 以指定二维轨迹 $L _ { 0 }$ 运动至 $B$ ，即像点的实际运动轨迹是一条任意轨迹的二维曲线 $L _ { 1 }$ 。

在像方坐标系下，通常可以通过设定沿 $x$ 轴和y轴运动的速度大小的比例关系来控制像点的运动方向轨迹。然而，由于摆镜钢带、轴承摩擦之类的非线性，电机输出力矩与响应延迟的差异性，使得像点无法做指定轨迹的二维运动。

为此，文中提出了一个新的分割步进的解耦策略。该策略将指定运动轨迹分割成若干固定间隔，在每个间隔内，像点先沿 $x$ 轴方向运动一步，此时电机M1与M2运动方向与大小相同，不存在阻力形式的耦合力矩；然后再沿 $y$ 轴方向运动一步，此时电机M1保持不动，而M2电机运动一步。摆镜等间隔逐级步进，最终到达指定位置，如图3中所示轨迹 $L _ { 1 }$ 。

为了达到 $1 5 ^ { \circ } / \mathrm { s }$ 的速度的要求，需将电机速度的指标至少调整为 $3 0 ^ { \circ } / \mathrm { s }$ 。当分割间隔足够小时，电机间的耦合力矩可忽略不计，同时轨迹 $L _ { 1 }$ 可近似拟合成一条直线 $L _ { 0 }$ ，从而实现了摆镜的力矩解耦，完成了指定轨迹的二维运动。

# 2.3控制器设计与仿真

二维耦合摆镜解耦后的独立伺服系统采用速度环与位置环双闭环的控制方法，控制系统结构如图4所示，其中 $G _ { 1 } ( s )$ 和 $G _ { 2 } ( s )$ 分别为位置控制环与速度控制环校正网络的传递函数， $G _ { 3 } ( s )$ 为被控对象，即有限转角力矩电机及其负载摆镜反射镜的等效传递函数， $K _ { 1 }$ 为PWM功率放大器的放大系数， $K _ { 2 }$ 为速度反馈系数。

![](images/0d53551fcc861ced2b15ac0f958183e6cfba36c4600ebfe6a022ed90b3f0f9dc.jpg)  
图4控制系统结构图  
Fig.4 Structure diagram of control system

有限转角力矩电机及其负载的数学模型为：

$$
G _ { 3 } ( s ) { = } \frac { 1 / K _ { \mathrm { e } } } { ( T _ { \mathrm { m } } s { + } 1 ) ( T _ { \mathrm { e } } s { + } 1 ) }
$$

式中： $K _ { \mathrm { e } }$ 为电机电动势系数； $T _ { \mathrm { m } }$ 为机电时间常数; $T _ { \mathrm { e } }$ 为电气时间常数。速度控制环由速度环校正函数$G _ { 2 } ( s )$ 、PWM功率放大器、力矩电机、负载及旋转变压器组成。速度环必须满足系统所要求的速度范围，同时满足位置回路所要求的动态特性要求。校正函数 $G _ { 2 } ( s )$ 由串联滞后校正环节与PI控制器级联而成，可实现速度的快速控制。加入串联滞后校正环节的作用是：降低系统的截止频率，提高系统的稳定性能，并对高频噪声有抑制作用。 $G _ { 2 } ( s )$ 传递函数的形式为：

$$
G _ { 2 } ( s ) { = } K _ { p 1 } \Big ( 1 { + } \frac { 1 } { T _ { i } s } \Big ) \cdot \frac { b T s { + } 1 } { T s { + } 1 }
$$

则速度控制环的闭环传递函数为：

$$
G _ { \nu } ( s ) { = } \frac { K _ { 1 } G _ { 2 } ( s ) G _ { 3 } ( s ) } { 1 { + } K _ { 1 } K _ { 2 } G _ { 2 } ( s ) G _ { 3 } ( s ) }
$$

在设计系统位置控制环路时，可将速度环作为位置控制回路中的一个子环节考虑。为有效地抑制系统的超调，同时实现位置的精确控制，位置环校正函数 $G _ { 1 } ( s )$ 采用PD控制器，其传递函数的形式为：

$$
G _ { 1 } ( s ) \mathrm { { = } } K _ { p 2 } ( 1 { + } T _ { d } s )
$$

从而，位置控制环的开环传递函数为：

$$
G _ { p k } ( s ) = { \frac { G _ { 1 } ( s ) G _ { \nu } ( s ) } { s } }
$$

其闭环传递函数为：

$$
G _ { p } { = } \frac { G _ { p k } } { 1 { + } G _ { p k } }
$$

将有限转角力矩电机及负载的相关参数代入公式(l0)，经matlab计算及仿真，可得 $K _ { p 1 } { = } 2 0 , K _ { i } { = } 0 . 0 8$ ，$b { = } 0 . 1 , T { = } 2 0 0 , K _ { p 2 } { = } 0 . 4 5 , K _ { d } { = } 0 . 1 3 ,$ 0

系统开环频率特性曲线与闭环阶跃响应曲线分别如图5、6所示。

![](images/81c5178133aeb1374ded06565be76cd830ba96c8ddfe5176b6b33ffab0d7b827.jpg)  
图5系统开环Bode图

![](images/b2852fe981dd3d159b23ded0d5035116ef15201c65539b568a3967ded9f98da6.jpg)  
Fig.5 Bode diagram of open loop   
Fig.6 Step response curve of close loop

由图可知，系统开环幅值裕度 $4 7 . 5 \ : \mathrm { d B }$ ，相角裕度 $8 6 . 5 ^ { \circ }$ 。系统闭环超调量 $\sigma$ 小于 $0 . 1 9 \%$ ，调节时间$t _ { s } { = } 0 . 0 3 7 \mathrm { ~ s ~ }$ ,完全满足系统对位置回路超调量小、过渡平稳的性能要求。

同时还可以看出，单独采用位置回路进行控制的方案系统超调量大且频率特性差。在光学摆镜中必须保证低速平稳性和位置跟踪精度的重要环节，因此，设计完善速度环是保证伺服系统控制性能的关键一环。

# 2.4数字控制器实现方法

文中的控制算法通过恒稳变换方法一双线性变换，将连续系统校正函数 $G _ { 1 } ( s )$ 与 $G _ { 2 } ( s )$ 进行离散化。双线性变换的形式为：

$$
s \approx \frac { 2 } { T } \cdot \frac { 1 - z ^ { - 1 } } { 1 + z ^ { - 1 } }
$$

式中： $T$ 为系统采样周期，取 $T { = } 0 . 0 4 ~ \mathrm { m s }$ 。对 $G _ { 1 } ( s )$ 与$G _ { 2 } ( s )$ 分别进行双线性变换后得到其离散形式，然后进行计算机软件编程实现摆镜的数字控制。

# 2.5控制系统硬件实现

文中使用有限转角力矩电机作为执行元件，以高精度旋转变压器作为绝对式角位置/速度传感器，以DSP为核心构建了如图7所示的摆镜伺服控制系统。上位机采用基于RTX实时扩展模块的Windows操作系统，通过PCI9054卡与摆镜数字控制器进行通信。PCI9054卡采取3路LVDS信号进行数据传输，速率可达120Mbps，完全满足系统通信高速实时的苛刻要求。控制器不断采集旋转变压器的位置与速度信号，与给定位置比较，经计算输出PWM信号至L298H电机驱动模块，逐渐修正摆镜的位置偏差，从而控制摆镜进行精确的二维运动。

![](images/8c363bfeb8eb2cc3e289ca8c1ba2be8b5dba74b986b75d2ecad76cd8aeff458a.jpg)  
图6系统闭环阶跃响应曲线  
图7摆镜伺服控制系统  
Fig.7 Servo control system of swing mirror

# 3实验与分析

动态特性实验结果如图8所示。电机运动范围为 $5 . 5 ^ { \circ }$ ，在该范围内系统的稳态误差 $e _ { \mathrm { s s } } { = } 0 . 0 0 5 ^ { \circ }$ ，运动速度为 $3 8 . 4 6 ^ { \circ } / \mathrm { s }$ ,响应时间约为 $\mathrm { { 1 3 0 m s } }$ ,基本无超调，达到了光学摆镜对力矩电机高精度位置控制与快速响应的技术要求。

48000 M1target position M1 position response   
IJO 47000   
46000 M2 target position M2 position response   
nosge 45000 1 1   
43000 1 1 0.5 1.0 1.5 2.0 2.5 3.0 3.5 t/s

像点运动轨迹实验结果如图9所示。像点从$( 0 , 0 )$ 以 $3 0 ^ { \circ } / \mathrm { s }$ 的速度沿 $Y$ 轴运动至(0,2.5)，左侧是旋转变压器返回数据生成的轨迹曲线，右侧为通过黑体点光源模拟入射光，使用红外热像仪拍摄的像点轨迹照片。从图中可以看出，摆镜二维运动解耦正确，像点实际运动轨迹与给定轨迹基本一致，二维运动轨迹偏差为 $\pm 0 . 0 1 7 ^ { \circ }$ ,达到了总体设计的技术要求。

![](images/2310ddd5fb15f3dc3da588d422d4ff65cf619a910e523b838a0213ae4b008ef3.jpg)  
图8力矩电机位置响应曲线  
Fig.8 Torque motors position response curve   
图9像点运动轨迹  
Fig.9 Trajectory of image-forming spot

# 4结论

实验结果表明，该方法设计的伺服控制系统，二维耦合摆镜解耦控制正确，像点实现了指定轨迹的高精度二维运动(轨迹偏差 $e { = } { \pm } 0 . 0 1 7 ^ { \circ }$ )；位置随动控制精度高 $( e _ { \mathrm { s s } } { = } 0 . 0 0 5 ^ { \circ }$ ),基本无超调；电机响应时间短，动态特性好 ${ 5 . 5 ^ { \circ } }$ 响应时间 $\mathrm { 1 3 0 m s } )$ ；取得了很好的控制效果。该方法可广泛应用于摆动扫描控制系统高精度位置控制的研究领域，具有很好的工程应用前景。

# 参考文献：

[1] Ghazali R,Sam Y M,Rahmat MF,et al.Position tracking control of an electro-hydraulic servo system using sliding mode control[C]//SCOReD 20l0,2010:240-245.   
[2] Anas S R，Jaison H,Gopinath A，et al．Modeling and simulation analysis of a redundant electromechanical actuator based position servo system[C]//ICCCET20ll, 20ll: 358-363.   
[3] Masuda S.A direct PID gains tuning method for DC motor control using an input-output data generated by disturbance response[C]//IEEEInternationalConferenceControl Applications，201l:724-729.   
[4] Shardlow M A,Greening JJ.D.C．motor control [C]//IET Seminar Digest,2008,1239l:64-83.   
[5] Chen Zhibin，Liang Yan．Full automatic testingtechnology about resolution of aiming systemof laser range finder [J]. Infrared and Laser Engineering，2004,34(5):453-457.(in Chinese)   
[6] O'Neil R R,Gibson JJ.Infrared earth limb and terrestrial background measurements from the MSX satellite [C]//43rd AIAAAerospace Sciences Meetingand Exhibit， 2005: 11971-11977.   
[7] Soto-Romero G,Bony F,Simonne JJ,et al．Micro infrared earth sensor project: an integrated IR camera for earth remote sensing[C]//SPIE,200l,4540:176-187.   
[8] Zhao Jianhui,Tian Xinling．Analysis and implementation of limited angleswing scanning control system [J].Infrared and Laser Engineering，2007,36(3):357-360.(in Chinese)