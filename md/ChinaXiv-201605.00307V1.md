# 基于笔形波束扫描雷达散射计的海洋表面流测量

鲍青柳1,²,董晓龙1,朱迪l，徐星欧1(1.中国科学院空间科学与应用研究中心微波遥感重点实验室,北京 100190；2.中国科学院大学,北京 100049)

摘要：为了研究利用雷达散射计进行海洋表面流直接测量的可行性,本文对传统雷达散射计系统参数进行了改进,推导了相关系数模型及去相关因素的表示形式,给出了相位误差模型,并建立了利用雷达散射计进行海洋表面流直接测量的端到端仿真模型.仿真结果表明，在风速大于 $5 \mathrm { m / s }$ 的海况条件下，顺轨向和交轨向速度分量标准差可达$0 . 1 \mathrm { m / s }$ 以下.风速大于 $7 \mathrm { m / s }$ 时,可用于海洋表面流反演的刈幅范围大于散射计刈幅宽度的 $4 0 \%$ .新型散射计的风单元传递误差无论是在低风速还是在高风速条件下均优于扇形波束扫描散射计的风单元传递误差.

关键词：散射计；海洋表面流；相关系数模型；相位误差模型中图分类号：TP732.1 文献标识码：A 文章编号：0372-2112（2015)06-1200-05电子学报 URL：http://www.ejournal.org.cn DOI:10.3969/j.issn.0372-2112.2015.06.024

# Ocean Surface Current Measurement Using Rotating Pencil-Beam Scatterometer

BAO Qing-liu1,²,DONG Xiao-long1,ZHU Di1,XU Xing-ou1 (1.KeyLaboratoryficrowaveRemoteSensing,CenterforSpace SienceandAppliedResearch，ChineseAcademyofSciences， Beijing100190,China；2.University of Chinese Academy of Sciences,Beijing 10o049,China)

Abstract:Inorder tostudythe feasibilityofoceansurface curent measurementusingradarscaterometer,the systemparametersof thetraditionalsaterometerweremodified,tecoherentcoeffcientmodelanddecorelationfactorswerederived,andthe phaseerormodel wasobtained.Mreover,thispaper establishedanend-to-endmodeltosimulatetheoceansurfacecurrentmeasurement.The input wind speeds ranged from $2 \mathrm { m / s }$ to $2 1 \mathrm { m / s }$ and the wind direction was parallel to the cross track direction.The Tesults show that the current speed standard deviation in along-track and cross-track direction are smaller than $0 . 1 \mathrm { m / s }$ ,when the wind speed is greater than $5 \mathrm { m / s }$ .And the swath that can be used for current speed inversion is greater than $40 \%$ ,when the wind speed is larger than $7 \mathrm { m / s }$ .The width of effective swath increases with the increase of the wind speeds.After parameters’optimization,communicationerorwascalculatedandtheresultsshowthatthecommunicationerorof themodifiedscaterometerisbeter than that of thefan-beam,rotating scatterometer in both the low wind speedand high wind speed conditons.

Key Words:scattrometer;ocean surface current;coherent coeficient model; phase error model

# 1引言

大尺度的海洋循环是全球热平衡和气候变化的基础，对于全面的研究和理解气候变化具有重要意义.海洋表面流的直接测量方法主要包括现场测量和高频地波雷达[1,2],如侯杰昌等的 OSMAR(Ocean State Measuring &AnalyzingRadar)系统.高频地波雷达可对潮汐等表面流进行连续观测，时间分辨率高.利用合成孔径雷达的多普勒中心异常和顺轨干涉技术可以实现海洋表面流的全球观测[3,4].但是,合成孔径雷达受到数据量及观测刈幅等的限制，无法实现快速全球覆盖.利用星载雷达散射计对海洋表面流进行观测无法实现连续观测，但是可实现快速全球覆盖，并反演出海洋表面流的速度矢量.

本文首先介绍了海洋表面流的测量原理及改进后雷达散射计的系统参数，推导了相关系数模型及四种主要去相关因素的表示形式，给出了相位误差模型及速度测量误差，建立了基于笔形波束扫描雷达散射计的海洋表面流测量仿真模型，仿真了不同风速条件下的海洋表面流速度测量精度及风单元的系统传递误差 $K _ { \mathrm { p c } }$ ：

# 2雷达散射计系统及海洋表面流测量原理

# 2.1海洋表面流测量原理

笔形波束圆锥扫描雷达散射计观测角为 $\varphi$ 时的观测几何如图1所示.其中 $s$ 点为雷达散射计， $P$ 点为观测目标.雷达散射计天线与观测目标之间的径向速度$V _ { R }$ 可表示为：

![](images/ca6fccce9c99639dc5fc2c0cde348e5574f66e5e7ee8df2f69462da2eabbbb71.jpg)  
图1雷达散射计观测几何

$$
V _ { R } = \mathrm { s i n } \theta \big [ \big ( { V _ { \mathrm { s a t } } - V _ { x } } \big ) \mathrm { c o s } \varphi - V _ { y } \mathrm { s i n } \varphi \big ]
$$

若雷达两个回波的时间间隔为 $\tau$ ,那么两次回波的干涉相位差可表示为：

$$
\phi = 2 \pi f _ { d } \tau = \frac { 4 \pi V _ { R } \tau } { \lambda } = \frac { 4 \pi { \sin } \theta \big [ \big ( V _ { \mathrm { s a t } } - V _ { x } \big ) { \cos } \varphi - V _ { \gamma } { \sin } \varphi \big ] } { \lambda } \tau
$$

由式(2)解出目标速度 $V _ { x }$ 和 $V _ { y }$ 至少需要两个观测方位角的干涉相位差 $\psi _ { 1 }$ 和 $\psi _ { 2 }$ ,其对应的观测方位角分别 $\varphi _ { 1 }$ 和 $\varphi _ { 2 }$ .解出的 $V _ { x }$ 和 $V _ { y }$ 分别为：

$$
{ \begin{array} { r l } & { V _ { x } = \displaystyle V _ { \mathrm { s a t } } - \frac { \lambda } { 4 \pi \mathrm { s i n } \theta \mathrm { s i n } \left( \varphi _ { 1 } - \varphi _ { 2 } \right) \tau } ( \psi _ { 2 } \mathrm { s i n } \varphi _ { 1 } - \psi _ { 1 } \mathrm { s i n } \varphi _ { 2 } ) } \\ & { V _ { y } = \displaystyle \frac { \lambda } { 4 \pi \mathrm { s i n } \theta \mathrm { s i n } \left( \varphi _ { 1 } - \varphi _ { 2 } \right) \tau } ( \psi _ { 2 } \mathrm { c o s } \varphi _ { 1 } - \psi _ { 1 } \mathrm { c o s } \varphi _ { 2 } ) } \end{array} }
$$

由式(3)可知，利用两个观测方位角的连续两个脉冲回波的干涉相位差可以计算出观测目标的速度矢量.然而，传统雷达散射计系统的连续两个脉冲回波信号不满足干涉测量的要求，需要对传统雷达散射计的系统参数进行改进.

传统的雷达散射计的PRF(脉冲重复频率)较低，如SeaWinds的脉冲频率约为 $1 8 5 \mathrm { H z }$ ，脉冲重复周期约为$5 . 4 \mathrm { m s } ^ { \left[ 5 \right] }$ ,连续两个脉冲回波信号已经不具有相关性.新型的散射计系统对天线口径和PRF提出了新的要求.对于天线进行圆锥扫描的雷达散射计，其回波信号具有有限的多普勒带宽，多普勒带宽主要由天线方位向的波束宽度决定.PRF必须足够高以满足奈奎斯特采样定律.

# 2.2 雷达系统参数

雷达系统仿真的参数如表1所示.

表1雷达散射计系统仿真参数  

<html><body><table><tr><td>天线波束宽度</td><td>0.6°×1.0°</td></tr><tr><td>雷达本地入射角</td><td>47°</td></tr><tr><td>载波频率</td><td>13.5GHz</td></tr><tr><td>发射功率</td><td>200W</td></tr><tr><td>PRF</td><td>8kHz</td></tr><tr><td>信号时宽</td><td>30 pus</td></tr><tr><td>信号带宽</td><td>4MHz</td></tr></table></body></html>

# 3相关系数模型

定义 $t _ { 0 }$ 时刻海面每点的复后向散射系数为 $\boldsymbol { f } ( \boldsymbol { r }$ $\varphi , t _ { 0 } )$ ,雷达系统的脉冲响应为 $\boldsymbol { W } ( \boldsymbol { r } , \varphi )$ ,接收机的热噪声为 $\mathbf { \Omega } _ { n }$ ，则 $t _ { 0 }$ 时刻观测到的雷达回波信号 $S _ { 1 }$ 可表示为[6]：

$$
\begin{array} { l } { { S _ { 1 } \ = \ \displaystyle \iint f ( \boldsymbol { r } , \varphi , t _ { 0 } ) \exp \Big ( \mathrm { - \ j } \ \frac { 4 \pi } { \lambda } \sqrt { H ^ { 2 } + \ { r } ^ { 2 } } \Big ) \ { \cal W } ( \boldsymbol { r } , \varphi ) } } \\ { { \mathrm {  ~ \ r ^ { \prime } ~ } r \ \mathrm { d } r \ \mathrm { d } \varphi + n _ { 1 } } } \end{array}
$$

$t _ { 0 } + T$ 时刻观测到的雷达回波信号 $S _ { 2 }$ 可表示为：

$$
\begin{array} { r l } & { S _ { 2 } \ = \ \displaystyle \iint _ { _ { D ^ { \prime } } } f \big ( \boldsymbol { r } , \boldsymbol { \varphi } , \boldsymbol { t _ { 0 } } + \ T \big ) \mathrm { e x p } \Big ( \ - \ \mathrm { j } \ \frac { 4 \pi } { \lambda } \sqrt { \boldsymbol { H } ^ { 2 } + \ \boldsymbol { r } ^ { 2 } } \Big ) } \\ & { \qquad \cdot \ \mathrm { e x p } \Big ( \mathrm { j } \ \frac { 4 \pi } { \lambda } \boldsymbol { V } _ { \mathrm { s a } } \mathrm { s i n } \theta \mathrm { c o s } \varphi T \Big ) \boldsymbol { W } ( \boldsymbol { r } , \boldsymbol { \varphi } ) } \\ & { \qquad \cdot \ \boldsymbol { r } \ \mathrm { d } \boldsymbol { r } \ \mathrm { d } \boldsymbol { \varphi } + \ n _ { 2 } } \end{array}
$$

其中， $T$ 为两次观测的时间间隔. $H$ 为雷达到地面的距离. $\boldsymbol { r }$ 为雷达天底点到目标点的地面距离. $\varphi$ 为目标点的方位角. $\theta$ 为雷达入射角. $\lambda$ 为雷达电磁波长. $V _ { \mathrm { s a t } }$ 为卫星飞行速度. $D ^ { \prime }$ 和 $D ^ { \prime }$ 分别为两次观测时的雷达观测区域：

$$
\begin{array} { c } { { D ^ { \prime } = D + D _ { 1 } } } \\ { { D ^ { \prime \prime } = D + D _ { 2 } } } \end{array}
$$

假设海面是由均匀分布且互不相关的散射中心组成,那么[6]：

$\left. f ( r , \varphi , t ) \cdot f ^ { * } \left( r ^ { \prime } , \varphi ^ { \prime } , t \right) \right. = \sigma _ { 0 } \delta ( r - r ^ { \prime } , \varphi - \varphi ^ { \prime } )$ (7)其中, $\sigma _ { 0 }$ 为平均的雷达后向散射系数.且两次观测的热噪声互不相关，即

$$
\langle n _ { 1 } \bullet n _ { 2 } ^ { \ast } \rangle = \langle n _ { 1 } \rangle \bullet \langle n _ { 2 } ^ { \ast } \rangle = 0
$$

两次观测的复相关系数可表示为[7,8]：

$$
\gamma = { \frac { \langle S _ { 1 } S _ { 2 } ^ { * } \rangle } { \sqrt { \langle S _ { 1 } S _ { 1 } ^ { * } \rangle \langle S _ { 2 } S _ { 2 } ^ { * } \rangle } } } = \gamma _ { { \mathrm { t h e r m a l } } } \cdot \gamma _ { { \mathrm { f o o t p r i n t } } } \cdot \gamma _ { { \mathrm { s p a t i a l } } } \cdot \gamma _ { { \mathrm { t e m p o r a l } } }
$$

即，雷达两次观测的复相关系数可以表示成不同相关系数乘积的形式.其主要包括四个去相关因素： $\gamma _ { \mathrm { t h e m a l } }$ 热噪声去相关, $\gamma _ { \mathrm { f o o t p r i n t } }$ 不同观测区域去相关, $\gamma _ { \mathrm { s p a t i a l } }$ 空间去相关, $\gamma _ { \mathrm { { t e m p o r a l } } }$ 时间去相关.

# 3.1 热噪声去相关

式(9)中，热噪声去相关可以表示为[6,7」：

$\gamma _ { \mathrm { t h e r m a l } } =$

$$
\frac { 1 } { \sqrt { \left[ \mathbb { 1 } + \frac { \lVert \mathbf { \omega } _ { n _ { 1 } } \rVert ^ { 2 } } { \sigma _ { 0 } \underset { p } { \iint } \mathrm { ~ | ~ } W ( r , \varphi ) \mathrm { ~ | ^ 2 \cdot ~ } r ^ { 2 } \mathrm { ~ d } r \mathrm { ~ d } \varphi } \right] \left[ \mathbf { 1 } + \frac { \lvert \mathbf { \omega } _ { n _ { 2 } } \rvert ^ { 2 } } { \sigma _ { 0 } \underset { w } { \iint } \mathrm { ~ | ~ } W ( r , \varphi ) \mathrm { ~ | ^ 2 \cdot ~ } r ^ { 2 } \mathrm { ~ d } r \mathrm { ~ d } \varphi } \right] } }
$$

$$
= \frac { 1 } { \sqrt { \left[ 1 + \mathrm { S N R } _ { 1 } ^ { - 1 } \right] \left[ 1 + \mathrm { S N R } _ { 2 } ^ { - 1 } \right] } } = \frac { 1 } { 1 + \mathrm { S N R } ^ { - 1 } }
$$

其中，SNR为雷达散射计的信噪比.由式(10)可以看出，

雷达系统信噪比降低会引起相干系数的降低.

# 3.2 不同观测区域去相关

雷达两次观测的观测区域差异主要是由卫星飞行速度和天线圆锥扫描引起的.式(9)中由雷达两次观测时足印位置不同引起的去相关可以表示为：

$\gamma _ { \mathrm { f o o t p r i n t } } =$

$$
\frac { \iint _ { \mathrm { ~ \textstyle ~ l ~ } } | \ \boldsymbol { W } ( \boldsymbol { r } , \varphi ) \ | ^ { 2 } \cdot \boldsymbol { r } ^ { 2 } \mathrm { d } \boldsymbol { r } \ \mathrm { d } \varphi } { \sqrt { \iint _ { \mathrm { ~ \textstyle ~ l ~ } ^ { \prime } } | \ \boldsymbol { W } ( \boldsymbol { r } , \varphi ) \mid ^ { 2 } \cdot \boldsymbol { r } ^ { 2 } \mathrm { d } \boldsymbol { r } \ \mathrm { d } \varphi \cdot \iint _ { \boldsymbol { L } ^ { \prime } } | \ \boldsymbol { W } ( \boldsymbol { r } , \varphi ) \ | ^ { 2 } \cdot \boldsymbol { r } ^ { 2 } \mathrm { d } \boldsymbol { r } \ \mathrm { d } \varphi } }
$$

典型雷达的脉冲响应 $\boldsymbol { W } ( \boldsymbol { r } , \varphi )$ 可以近似为 sinc 函数[6.根据文献[9]及[10],由分辨单元失配引起的相关系数损失可表示为：

$$
\gamma _ { \mathrm { f o o t p r i n t } } = \frac { \sin ( \pi \delta _ { r } ) } { \pi \delta _ { r } } \cdot \frac { \sin ( \pi \delta _ { \varphi } ) } { \pi \delta _ { \varphi } }
$$

其中， $\delta _ { r }$ 和 $\delta _ { \varphi }$ 分别为雷达距离向和方位向分辨单元的相对位移量.雷达在一个PRF间隔内，卫星飞行的距离和天线扫描的角度都远小于距离向和方位向分辨率，因此由不同观测区域引起的去相关对雷达回波相关系数影响不大.

# 3.3 空间去相关

空间去相关是由于雷达两次观测时的空间位置不同而引起的，由于本系统是利用雷达连续两个发射脉冲的回波进行干涉，因此两次观测的雷达位置差为卫星在一个PRF间隔内飞行过的距离，即 $B = ~ V _ { \mathrm { s a t } } / \mathrm { P R F }$ 同样,雷达脉冲响应可利用 sinc 函数近似.由式(9)可知,空间去相关可以表示为：

$$
\gamma _ { \mathrm { s p a t i a l } } ~ = ~ \frac { \displaystyle \int _ { - \infty } \log \Big ( - \mathrm { \scriptsize ~ j ~ } \frac { 4 \pi } { \lambda } V _ { \mathrm { s a t } } \mathrm { s i n } \theta \mathrm { c o s } \varphi T \Big ) \mathrm { s i n c } \left( \frac { \varphi - \varphi _ { 0 } } { R _ { \varphi } } \right) ^ { 2 } \mathrm { d } \varphi } { \displaystyle \int _ { \varphi } \mathrm { s i n c } \left( \frac { \varphi - \varphi _ { 0 } } { R _ { \varphi } } \right) ^ { 2 } \mathrm { d } \varphi }
$$

图2给出了雷达在不同观测方位角进行观测时的空间去相关系数.其中， $0 ^ { \circ }$ 观测方位角对应着正前视，$9 0 ^ { \circ }$ 观测方位角对应着正侧视.

![](images/9453f4c843842e1ddbb97f9d040bd0d6b59af78138448611ba49fa992b648667.jpg)  
图2空间去相关随PRF的变化

由图2可以看出，空间去相关随着脉冲重复频率的减小而增大，即雷达两次观测的时间间隔越大，两次观测时雷达的空间距离越远，空间去相关越严重.同时，由图2中观测方位角 $\varphi _ { 0 } = 9 0 ^ { \circ }$ 的曲线可以看出，当PRF小于雷达最大多普勒带宽(约为 $6 . 9 \mathrm { k H z } \mathrm { \cdot }$ 时，相关系数降为0.因此，想要利用雷达连续两个脉冲回波的干涉相位进行海面表面流速度测量，要求PRF大于最大多普勒带宽.

# 3.4 时间去相关

时间去相关是由海面在两次观测时间间隔内散射点的随机变化引起的，由式(9)可以看出，时间去相关可以表示为[]：

$$
{ \begin{array} { r l } & { \gamma _ { \mathrm { t e m p o r a l } } = { \frac { 1 } { \sigma _ { 0 } } } \langle f ( r , \varphi , t _ { 0 } ) \cdot f ^ { * } \left( r , \varphi , t _ { 0 } + \ T \right) \rangle } \\ & { = { \frac { 1 } { \sigma _ { 0 } } } { \overset { ! } { \int _ { - \infty } } } \exp ( \mathrm { j } 2 \pi f _ { D } T ) S ( f _ { D } ) \mathrm { d } f _ { D } } \end{array} }
$$

其中， $f _ { D }$ 为海面多普勒频率, $S ( f _ { D } )$ 为海面多普勒频率的概率密度函数，即海面多普勒谱， $T$ 为观测时间间隔.如果脉冲重复频率PRF采用 $8 . 3 \mathrm { k H z }$ ，那么脉冲时间间隔为 $0 . 1 2 \mathrm { m s }$ .风速小于 $2 1 \mathrm { m / s }$ 的海面的自相关系数均大于0.99,因此,海面的时间去相关并不是连续两个脉冲回波干涉的主要去相关因素.

# 4系统性能分析

# 4.1速度分量测量精度

对于收发同波束的天线系统，天线扫描损失约为-3.3dB.对不同风速情况下的海面进行仿真，风速范围为 $2 \sim 2 1 \mathrm { m / s }$ ，风向垂直于卫星飞行方向.雷达散射计系统参数如表1所示.不同风速下的顺轨向与交轨向速度分量标准差随交轨向位置的变化如图 $3 ( a ) \lrcorner ( b )$ 所示.空间分辨率为 $2 5 \mathrm { k m } \times 2 5 \mathrm { k m }$ ，时间分辨率为10天.

由图 $3 ( a )$ 可以看出，随着风速的增大，顺轨向速度分量标准差小于 $0 . 1 \mathrm { m / s }$ 的交轨向区域逐渐增大，但是当风速大于 $7 \mathrm { m / s }$ 时,该变化趋于平缓.由图 $3 ( b )$ 可知，当风速小于 $5 \mathrm { m / s }$ 时,交轨向速度标准差均大于 $0 . 1 \mathrm { m / s } .$ 因此，可用于海洋表面流测量的海况条件要求风速大于 $5 \mathrm { m / s }$ ：

表2流场测量有效刈幅 $\left( \mathrm { k m } \right)$   

<html><body><table><tr><td colspan="2">风速(m/s)</td><td>3</td><td>5</td><td>7</td><td>9</td><td>11</td><td>20</td></tr><tr><td rowspan="5">流速精度 (m/s)</td><td>0.1</td><td>0</td><td>113</td><td>397</td><td>467</td><td>514</td><td>592</td></tr><tr><td>0.15</td><td>0</td><td>427</td><td>546</td><td>608</td><td>635</td><td>689</td></tr><tr><td>0.2</td><td>0</td><td>529</td><td>632</td><td>673</td><td>701</td><td>752</td></tr><tr><td>0.25</td><td>389</td><td>600</td><td>682</td><td>718</td><td>740</td><td>787</td></tr><tr><td>0.3</td><td>469</td><td>656</td><td>720</td><td>748</td><td>775</td><td>820</td></tr></table></body></html>

注：散射计刈幅宽度为 $1 0 0 5 \mathrm { k m }$

不同风速及流速测量精度条件下的有效刘幅宽度如表2所示.由表2可知，在低风速条件下，如风速为$5 \mathrm { m / s }$ ,流速精度小于 $0 . 1 \mathrm { m / s }$ 有效刈幅范围约为 $1 1 3 \mathrm { k m }$ =当海面风速为 $7 \mathrm { m / s }$ 时，有效刘幅范围约为 $4 0 0 \mathrm { k m }$ ，约占散射计刘幅宽度的 $4 0 \%$ ，且随着风速的增大，有效刘幅范围变宽.

450 0.6 -0.4 0.4 0.4  
400 A 0.2- 0.15 0.2- 0.15- -0.2。 0.15 -0.1- 0.1-  
350 0.19 0.05 0.05-0.05  
250 5  
200 D  
150 500  
10050 01 0.05 12 4 6 81012 1416 1820风速U/(m/s)(a)顺轨向速度分量  
450 o 0.2 0.15 -0.15- 0.15-  
400 -0.1- -0.1-0.125  
2500  
200  
150 X 02150.1  
100 0.4 0.20.15 0.1 0.15  
50 0.6 0.4 0.2L 0.6 0.4-0.62 4 68 10 12 14 16 1820风速U/(m/s)(b)交轨向速度分量

# 4.2 系统传递误差

受到雷达固有衰落效应和接收机热噪声的影响，回波的能量测量存在误差，其引起的 $\sigma _ { 0 }$ 测量误差称为传递误差，传递误差通常用归一化均方差 $K _ { \mathrm { p c } }$ 表示[12]：

$$
K _ { \mathrm { p c } } = { \sqrt { A + { \frac { B } { \mathrm { S N R } } } + { \frac { C } { \mathrm { S N R } ^ { 2 } } } } }
$$

风单元的大小为 $2 5 \mathrm { k m } \times 2 5 \mathrm { k m }$ 情况下，改进后的散射计与扇形波束扫描散射计的系统传递误差如图4所示，

由图4可以看出，无论是在低风速还是在高风速条件下，系统参数改进后的散射计的风单元传递误差均优于扇形波束扫描散射计.在低风速条件下，改进后的散射计系统依然能够到达较高的后向散射系数测量精度.如在风速为 $4 \mathrm { m / s }$ ，侧风向时，改进后的散射计系统

0.18   
0.16 NewScatter-迎风向 -NewScatter-侧风向 CFOSAT-风向，印近端   
0.1   
0.08   
0.06   
0.04   
0.02 上 L 1 8 6 8 10 12 14 16 18 20 风速U/(m/s)

的风单元 $\sigma _ { 0 }$ 传递误差约为0.03，而扇形波束扫描散射计足印近端的风单元 $\sigma _ { 0 }$ 传递误差约为0.18.在高风速情况下，改进后的散射计系统的风单元 $\sigma _ { 0 }$ 传递误差约为0.01,而扇形波束扫描散射计风单元的 $\sigma _ { 0 }$ 传递误差约为0.05.

# 5总结

本文建立了利用笔形波束扫描雷达散射计进行海洋表面流直接测量的速度测量误差端到端仿真模型，仿真了不同风速条件下的速度分量测量精度.仿真结果表明，在空间分辨率为 $2 5 \mathrm { k m } \times 2 5 \mathrm { k m }$ ，时间分辨率为10天的条件下，当海面风速大于 $5 \mathrm { m / s }$ 时，顺轨向和交轨向速度分量标准差可达 $0 . 1 \mathrm { m / s }$ 以下.当海面风速大于$7 \mathrm { m / s }$ 时，有效刘幅宽度约为 $4 0 0 \mathrm { k m }$ ,约占散射计刘幅宽度的 $4 0 \%$ .且无论是在低风速还是在高风速条件下，系统参数改进后的散射计的风单元传递误差均优于扇形波束扫描散射计.因此，可以利用改进后的笔形波束扫描雷达散射计对海面表面流进行直接测量，同时保证海面风场的测量精度.

# 参考文献

[1]侯杰昌,吴世才,等.海洋表面流的高频雷达遥感[J].地 球物理学报,1997,40(1):18-26. Hou Jie-chang,Wu Shi-cai,et al.Remote sensing of ocean surface currents by HF radar[J].Acta Geophysica Sinica,1997,40 (1):18-26.(in Chinese)   
[2]文必洋,李自立,等.便携式高频地波雷达东海表面流探 测试验[J].电子学报,2009,37(12):2778-2782. Wen Bi-yang,Li Zi-li,et al.Sea surface currents detection at the eastern china sea by HF ground wave radar OSMAR-S[J]. ActaElectronica Sinica,2009,37(12):2778-2782.（in Chinese)   
[3]Barale V,Gower JF R,et al.Oceanography from Space[M]. Netherlands: Springer,2010.73-91.   
[4]Chapron B,Collard F,et al.Direct measurements of ocean surface velocity from space:interpretation and validation[J].J Geophys Res-Oceans,2005,110(C07008):1-17.   
[5] Spencer M W,Wu C L,et al. Improved resolution backscatter measurements with the seawinds pencil-beam scatterometer[J]. IEEE Transactions on Geoscience and Remote Sensing,2000, 38(1):89 -104.   
[6] Zebker H A,Villasenor J.Decorrelation in interferometric radar echoes[J].IEEE Transactions on Geoscience and Remote Sensing,1992,30(5):950-959.   
[7]Bamler R,Hartl P.Synthetic aperture radar interferometry[J]. Inverse Problems,1998,14(4):R1-R54.   
[8]Rosen P A,Hensley S,et al.Synthetic aperture radar interferometry[J].Proceedings of the IEEE,2000,88(3) :333-382.   
[9]Just D,Bamler R.Phase statistics of interferograms with applications to synthetic aperture radar[J].Applied Optics,1994,33 (20):4361-4368.   
[10]Cloude S R.Polarisation:Applications in Remote Sensing [M].New York: Oxford University Press Inc,2010.208- 233.   
[11]Romeiser R,Thompson D R.Numerical study on the alongtrack interferometric radar imaging mechanism of oceanic surface currents[J].IEEE Transactions on Geoscience and Remote Sensing,2000,38(1):446-458.   
[12］Spencer M W.A Methodology for the Design of Spaceborne Pencil-Beam Scatterometer Systems[D].Utah:Department of Electrical and Computer Engineering of Brigham Young University,2001.

# 作者简介

鲍青柳(通信作者）男，1986年10月生于河北省藁城市，博士生，研究方向为雷达波谱仪系统仿真、雷达散射计系统仿真及雷达信号处理.

![](images/a3b6cdeb29296919864fcf8d6f33d7a720117e3c3fa3d34a173e81cc86755b85.jpg)

E-mail: baoqingliu2000@163.com

董晓龙男，1969年9月生于陕西省，研究员，研究方向为微波遥感成像与探测的理论与方法研究，以及微波遥感应用研究.E-mail: dongxiaolong@ mirslab.cn