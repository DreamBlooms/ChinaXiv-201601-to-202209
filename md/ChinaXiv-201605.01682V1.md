# 星间测距对小卫星编队相对轨道状态的修正

张晓磊²郑建华}高东钱航}²（1.中国科学院复杂航天系统电子信息技术重点实验室，中国科学院空间科学与应用研究中心北京100190；2.中国科学院大学,北京100190)

摘要：相对轨道状态确定是小卫星编队正常工作的基础和重要保障.针对小型化、低成本的星载GPS接收机定轨精度较低的情况，提出一种利用单纯星间测距信息对卫星编队相对轨道进行修正的方法.引入星间测距信息，采用扩展卡尔曼滤波算法提高编队的相对轨道估计精度.通过仿真验证,证实了该方案的有效性.

关键词：小卫星编队;GPS;星间测距;相对状态确定;扩展卡尔曼滤波

中图分类号：V448.2 文献标志码：A 文章编号:1674-1579(2015)03-0042-05  
DOI: $1 0 . 3 9 6 9 / \mathrm { j }$ .issn.1674-1579.2015.03.009

# Correction of the Relative Orbit States Based on Inter-Satellite Ranging for Micro-Satellites Formation

ZHANG Xiaolei¹²,ZHENG Jianhua’,GAO Dong',Qian Hang¹ ² (1.Key Laboratory of Electronics and Information Technology for Space Systems, NSSC ,CAS ,Beijing 100190 ,China; 2. University of Chinese Academy of Sciences,Beijing 1Oo190 ,China)

Abstract: Determination of the relative states is the primary and important guarantee for normal operation of micro-satellite formation.With the miniaturization and low-cost spaceborne GPS receiver,the accuracy of orbit determination is low.Inorder to solve this problem,a method of correcting the formation relative orbit is given with only inter-satelite ranging information used. Inter-satelite ranging information is introduced and the extended Kalman filter is used to enhance the estimation accuracy of the relative orbit.The numerical simulation results show the validity of this approach.

Keywords:micro-satelite formation; GPS；Inter-satellite ranging;relative state determination; extended Kalman filter

# 0引言

小卫星编队是由若干颗物理上相互分离的小卫星、微小卫星、纳卫星或皮卫星协同工作，通过无线组网技术形成一颗“虚拟整体卫星"[1],共同完成空间任务.小卫星编队具有研发成本低、运行风险小、鲁棒性强等优点还可根据任务需要灵活改变编队的构型和指向[2]在科学探测和军事等领域具有广阔的应用前景.

小卫星编队的星间相对轨道状态确定是队形保持、编队成员协同工作的重要保障.因此，星间相对轨道的精确确定十分必要.目前有多种方法用于星间相对轨道状态确定，主要包括：激光测量法、红外测量法、视觉相对导航法[3]、GPS 测量法[4]等.由于激光波束窄需要额外的引导系统增加了系统的复杂程度，不利于测量系统的小型化；红外测量法测量精度较高，但是只能提供测角信息不能提供测距信息无法单独使用；视觉相对导航法测量精度较高，技术成熟但是其作用距离较近不适合中远程的星间相对导航;基于星载GPS测量系统的相对导航法被认为是有效的高精度相对状态测量敏感器[5]GPS测量法的事后处理相对轨道状态估算精度较高在文献[6]中采用GPS测量系统获得的相对轨道精度达到了毫米量级，但是要想获得较高的实时确定精度需要复杂的数据处理过程小型化的GPS接收机很难实现高精度的相对轨道确定.针对以上问题本文提出了采用星间测距信息对星间初始相对轨道进行修正的方法来提高相对轨道确定精度.编队中的每颗卫星上都安装有星载GPS接收机，利用GPS接收机作为测量设备，可以估算出从星与主星的绝对位置信息，则从星与主星的相对位置信息可以利用绝对位置信息做差分得到.但是此时，从星与主星的相对位置的误差限是绝对位置误差限的2倍，误差限被放大，这是任务所不希望看到的.同时GPS 接收机要实现小型化、低成本这就使得其定位精度进一步降低.因此，本文在GPS测量系统初步确定了卫星编队的相对位置信息后，利用星间测距信息对星间相对轨道进行修正，

# 1动力学模型

本文提出的卫星编队构型为一个主星与多个从星构成的空间特定队形，为了便于研究问题只考虑主星和其中的一个从星的相对轨道状态确定情况，其他从星相对轨道状态可采用同样方法来处理

# 1.1 坐标系定义

描述卫星编队相对运动时需要用到惯性坐标系和相对运动坐标系，为了方便描述其相对运动和建立动力学模型，下面给出这两种坐标系的定义.

惯性坐标系N:坐标系原点 $O _ { \mathrm { { N } } }$ 与地球地心重 合 $\mathbf { \nabla } _ { \mathbf { X } _ { \mathrm { N } } }$ 轴指向春分点方向 $\mathcal { L } _ { \mathrm { v } }$ 轴垂直于赤道面指向 北极 ${ \mathbf { } } , { \{ }  _ { \mathrm { { N } } }$ 轴与 $X _ { \mathrm { { N } } }$ 轴 $\phantom { + } \cdot Z _ { \mathrm { { N } } }$ 轴满足右手定则.

相对运动坐标系H:坐标系原点 $O _ { \mathrm { H } }$ 与卫星质心重合 $X _ { \mathrm { H } }$ 轴方向与主星指向地球的矢径一致 $, Y _ { \mathrm { H } }$ 轴垂直于 $X _ { \mathrm { H } }$ 轴与主星运行速度方向一致 $\boldsymbol { Z } _ { \mathrm { H } }$ 轴与$X _ { \mathrm { H } }$ 轴、 $Y _ { \mathrm { H } }$ 轴满足右手定则.

在描述从星相对位置时，以主星所在的相对运动坐标系作为参考坐标系.从星在参考坐标系中的位置矢量可表示为 $\boldsymbol { r } = \left[ \begin{array} { l l l } { \boldsymbol { x } } & { \boldsymbol { y } } & { \boldsymbol { z } } \end{array} \right] ^ { \mathrm { T } }$ 主星与从星间的距离为 $\boldsymbol { r }$

![](images/cbd5f66e45d95785cbb5718f42f6751bc0b021c9b6acc3aa1fcdc5d98651f58c.jpg)  
图1卫星编队参考坐标系  
Fig.1Reference coordinate system of satellites formation reference coordinate system

# 1.2 卫星动力学方程

环绕地球轨道运行的卫星不仅受到地球球形引力的作用还受到其他摄动力的影响如地球非球形摄动、大气阻力摄动、日月引力摄动、潮汐摄动等根据牛顿力学原理，卫星在惯性坐标系下的动力学方程为

$$
\ddot { \pmb { R } } = - \frac { \mu } { R ^ { 3 } } \pmb { R } + \pmb { a }
$$

式中 $\mathbf { \nabla } _ { \mathcal { R } }$ 为卫星到地心距的大小 $\pmb { R }$ 为卫星地心距矢量 $\mu$ 为地球引力系数 $\pmb { \mathscr { A } }$ 为卫星受到的除地球引力外其他所有摄动加速度之和.

# 1.3 相对运动方程

从星在参考坐标系中的位置为 $( \boldsymbol { \it { \Delta } x } \mathrm { \Delta } _ { \mathcal { Y } } \mathrm { \Delta } _ { z } )$ 速度为$( \Dot { x } \ \Dot { y } \ \Dot { z } )$ .主星为圆轨道，从星与主星的距离远小于主星的轨道半径.因此卫星编队的相对运动可以采用Hill方程来描述[6]

$$
\left\{ \begin{array} { l l } { \ddot { x } - 2 n \dot { y } - 3 n ^ { 2 } x \ = \ a _ { x } } \\ { \ddot { y } + 2 n \dot { x } \ = \ a _ { y } } \\ { \ddot { z } + n ^ { 2 } z \ = \ a _ { z } } \end{array} \right.
$$

式中 $\scriptstyle n$ 为主星的平均角速度

$$
n = \sqrt { \frac { \mu } { R ^ { 3 } } }
$$

$a _ { x } \ a _ { y } \ a _ { z }$ 为相对摄动加速度.由于两载荷距离较近，所受摄动力情况基本相同因此，可忽略相对摄动影响[7]即 $a _ { { \scriptscriptstyle x } } = a _ { { \scriptscriptstyle y } } = a _ { { \scriptscriptstyle z } } = 0$ .求解式(2)可得相对位置$x \ y \ z$ 的解析表达式对相对位置求导可得相对速度 $\dot { \boldsymbol { x } } \dot { \boldsymbol { y } } \dot { \boldsymbol { z } }$ 的解析表达式.采样时间为 $\cdot$ 则离散化的Hill方程为

$$
X _ { _ { k + 1 } } \ : = \ : \pmb { \mathscr { P } } X _ { _ { k } } \ : + \ : \pmb { W } _ { _ { k } }
$$

式中 $\pmb { X } _ { k }$ 为 $k$ 时刻的从星相对轨道状态 $, W _ { k }$ 为过程误差阵 $\mathbfcal { A }$ 为状态矩阵，

$$
\pmb { \phi } = \biggl [ { \pmb \phi } _ { 1 1 } \pmb { \phi } _ { 1 2 } \biggr ] \ ,
$$

式中

$$
\begin{array} { r l } { \phi _ { 1 1 } } & { = \left[ \begin{array} { c c c } { 4 - 3 \cos ( n \pi ) } & { 0 } & { 0 } \\ { 6 ( \sin ( n \pi ) - n \tau ) } & { 1 } & { 0 } \\ { 0 } & { 0 } & { \cos ( n \tau ) } \end{array} \right] , } \\ { \phi _ { 1 2 } } & { = } \\ { \left[ \begin{array} { c c c } { \frac { \sin ( n \tau ) } { n } } & { \frac { 2 \left( 1 - \cos ( n \tau ) \right) } { n } } & { 0 } \\ { \frac { 2 \left( \cos ( n \tau ) - 1 \right) } { n } } & { \frac { 4 \sin ( n \tau ) } { n } - 3 \tau } & { 0 } \\ { 0 } & { 0 } & { \frac { \sin ( n \tau ) } { n } } \end{array} \right] , } \end{array}
$$

$$
\begin{array} { r } { \pmb { \phi } _ { 2 1 } = \left[ \begin{array} { c c c c } { 3 n \mathrm { s i n } ( n \tau ) } & { 0 } & { 0 } \\ { 6 n ( \mathrm { c o s } ( n \tau ) - 1 ) } & { 0 } & { 0 } \\ { 0 } & { 0 } & { - n \mathrm { s i n } ( n \tau ) } \end{array} \right] , } \end{array}
$$

$$
\phi _ { 2 2 } \ = \ \left[ \begin{array} { c c c c } { { \cos ( { \ n \tau } ) } } & { { 2 \sin ( { \ n \tau } ) } } & { { 0 } } \\ { { - 2 \sin ( { \ n \tau } ) } } & { { 4 \cos ( { \ n \tau } ) \ - 3 } } & { { 0 } } \\ { { 0 } } & { { 0 } } & { { \cos ( { \ n \tau } ) } } \end{array} \right] .
$$

# 2测量原理

每个编队成员上都安装有一台星载GPS接收机同时在卫星上安装有无线电测距装置，可以测出主、从星之间的距离.首先，由星载GPS测量系统确定出主星和从星在惯性坐标系下的绝对轨道位置再对其进行差分处理，可得出两星的初始相对轨道位置.将初始相对轨道信息作为下一步的测量值，加入星间测距信息采用扩展卡尔曼滤波算法对相对轨道进行进一步修正.测量原理如图2所示，

![](images/2a5046f45aff39fb5056536734463ee9ca176e1ca09d6bc252ff272a7f5b857e.jpg)  
图2 卫星编队测量原理图  
Fig.2Satellites formation measurement schematics

# 2.1 GPS 测量模型

GPS测量系统基于载波相位的测量模型为

$$
L ( \mathbf { \Psi } _ { t } ) \ = \rho _ { r } ^ { s } ( \mathbf { \Psi } _ { t } ) \ + \it { c } \big ( \delta T _ { r } ( \mathbf { \Psi } _ { t } ) \ - \delta T ^ { s } \big ( \mathbf { \Psi } _ { t } - \tau _ { r } ^ { s } ( \mathbf { \Psi } _ { t } ) \big ) \big ) \big ) \mathrm { ~ \ } + \rho _ { r } ^ { } ( \mathbf { \Psi } _ { t } ) \mathbf { \Psi } _ { t } \big ] \ .
$$

$$
\lambda N + M ( \mathit { \Omega } _ { t } ) \ + \varepsilon ( \mathit { \Omega } _ { t } )
$$

式中 ${ \mathbf { \Omega } } _ { { \mathbf { \Omega } } ^ { t } }$ 为信号接收时间 $\rho _ { r } ^ { s } ( \mathbf { \Omega } _ { t } )$ 为接收机和GPS卫星的几何距离 $\mathbf { \Omega } _ { \mathcal { L } }$ 为光速 $\delta T _ { r } ( \ t )$ 为接收机在 $\mathbf { \chi } _ { t }$ 时刻的钟差 $\pi _ { r } ^ { s } ( \mathbf { \xi } _ { t } )$ 为信号传输时间 ${ \delta } T ^ { s } ( \textit { t } - \tau _ { r } ^ { s } ( \textit { t } ) )$ 为GPS卫星在信号发射时刻 $\mathbf { \nabla } _ { t \mathrm { ~ - ~ } \tau _ { r } ^ { s } \left( \mathbf { \nabla } _ { t } \right) }$ 的钟差 $\mathbf { \lambda } _ { \mathcal { A } }$ 为波长 $\mathbf { \Omega } , N$ 为整周期模糊度 ${ \mathbf { \mathcal { M } } } ( { \mathbf { \Xi } } _ { t } )$ 为其他系统偏差 $\mathbf { \nabla } _ { \mathcal { E } } ( \mathbf { \nabla } _ { t } )$ 为测量噪声.

# 2.2 星间测距信息

无线电测距系统可以测出主星与从星间的距离星间距离表达式为

$$
r = \sqrt { x ^ { 2 } + y ^ { 2 } + z ^ { 2 } } + v
$$

式中 $, { \sqrt { x ^ { 2 } + y ^ { 2 } + z ^ { 2 } } }$ 为主、从星的几何距离 ${ \mathbf { \Omega } } _ { \mathcal { N } }$ 为测量 随机误差.

# 3滤波算法

主、从星通过GPS接收机获得测量值后，利用在惯性系下的动力学方程式(1)和测量方程式（5），采用适当的滤波算法可解算出绝对轨道信息，然后通过作差处理即可获得星间相对轨道初步估计值$\boldsymbol { X } ^ { * } \boldsymbol { \mathbf { \mathit { \Pi } } } = \boldsymbol { \left[ \vec { x } \right. } ^ { * }$ y $z ^ { * }$ $\stackrel { \cdot \ast } { x }$ y\*\*]T再加入星间测距信息采用扩展卡尔曼滤波算法对星间相对轨道状态进行二次修正

选取从星在参考坐标系中的位置和速度为状态量 $X = [ x \quad y \quad z \quad \dot { x } \quad \dot { y } \quad \dot { z } ] ^ { \mathrm { T } }$ 状态方程采用式(4).将基于GPS测量系统得到的初始相对轨道估计值 $\boldsymbol { { X } ^ { * } }$ 作为观测量再加入星间测量信息 $r$ 得到的观测量为

$\pmb { \rho } ( t ) = [ { \pmb x } ^ { * } \mathrm { ~  ~ \pmb ~ { ~ \gamma ~ } ~ } { \pmb z } ^ { * } \mathrm { ~  ~ \pmb ~ { ~ \chi ~ } ~ } ^ { * } \mathrm { ~  ~ \pmb ~ { ~ \chi ~ } ~ } ^ { * } \mathrm { ~  ~ \pmb ~ { ~ \chi ~ } ~ } ^ { * } \mathrm { ~  ~ \pmb ~ { ~ \chi ~ } ~ } ] ^ { \mathrm { { T } } } ( 7 )$ （204则观测方程为

$$
\begin{array} { r l } { \rho _ { k } ^ { \star } } & { = \left[ \begin{array} { c } { x _ { k } ^ { \star } } \\ { y _ { k } ^ { \star } } \\ { z _ { k } ^ { \star } } \\ { \vdots } \\ { x _ { k } ^ { \star } } \\ { \vdots } \\ { y _ { k } ^ { \star } } \\ { z _ { k } ^ { \star } } \\ { \sqrt { x _ { k } ^ { 2 } + y _ { k } ^ { 2 } + z _ { k } ^ { 2 } } } \end{array} \right] + V _ { k } , } \end{array}
$$

可简记为： $\pmb { \rho } _ { k } = h ( \pmb { X } _ { k } ) \ + \pmb { V } _ { k }$ 其中 $, V _ { \boldsymbol { k } }$ 为测量误差阵.

相对轨道状态确定的扩展卡尔曼滤波算法计算过程[8]如下:

首先给定 $k$ 时刻的状态量 $\hat { \pmb { x } } _ { k _ { k } }$ ,状态的一步预报值 $\hat { \pmb { x } } _ { k + 1 ~ k }$ 为

$$
\hat { \mathbf { x } } _ { k + 1 , k } \ = \ \hat { \pmb { p } } \hat { \mathbf { x } } _ { k , k }
$$

预报误差协方差阵为

$$
P _ { k + 1 , k } \ = \ \pmb { \phi } P _ { k , k } \pmb { \phi } ^ { \mathrm { T } } + \pmb { Q } _ { k }
$$

计算滤波增益 $\pmb { K } _ { k + 1 }$

$$
\pmb { K } _ { k + 1 } \ = \pmb { P } _ { k + 1 ~ k } \pmb { H } _ { k + 1 } ^ { \mathrm { T } } \ [ \pmb { H } _ { k + 1 } \pmb { P } _ { k + 1 ~ k } \pmb { H } _ { k + 1 } ^ { \mathrm { T } } \ + \pmb { R } _ { k + 1 } ] ^ { - 1 }
$$

状态估计误差协方差阵为

$$
P _ { \mathrm { \small { k + 1 } } , \mathrm { \small { ~ \scriptstyle { k + 1 } } ~ } } = \ [ I - K _ { \mathrm { \small { k + 1 } } } H _ { k + 1 } ] P _ { \mathrm { \small { k + 1 } } , \mathrm { \small { ~ \scriptstyle { k } } } } [ I - K _ { k + 1 } H _ { k + 1 } ] ^ { \mathrm { \scriptscriptstyle { T } } } \ +
$$

$$
\pmb { K } _ { k + 1 } \pmb { R } _ { k + 1 } \pmb { K } _ { k + 1 } ^ { \mathrm { T } }
$$

式中，

$$
H _ { k + 1 } \ = \ { \frac { \partial h ( \ X _ { k + 1 } ) } { \partial X } } { \left| { \bf \sigma } _ { \hat { X } _ { k + 1 } } \ = \ \left[ { \bf \sigma } _ { H } ^ { I _ { 6 } } \right] \right.}  
$$

其中，

$$
H = \Big [ \frac { x } { \sqrt { x ^ { 2 } + y ^ { 2 } + z ^ { 2 } } } \frac { y } { \sqrt { x ^ { 2 } + y ^ { 2 } + z ^ { 2 } } } \frac { z } { \sqrt { x ^ { 2 } + y ^ { 2 } + z ^ { 2 } } } \frac { \ d z } { \sqrt { x ^ { 2 } + y ^ { 2 } + z ^ { 2 } } } \frac { 0 } { \ d t } \frac { 0 } { \ d t } \Big . 0 1 0 \Big ]
$$

状态的最优估计值 $\hat { \pmb { x } } _ { k + 1 ~ k + 1 }$ 为

$$
\hat { \pmb { x } } _ { k + 1 ~ , k + 1 } = \hat { \pmb { x } } _ { k + 1 ~ , k } + \pmb { K } _ { k + 1 } \left[ \pmb { y } _ { k + 1 } - h ( \textbf { } k + 1 ~ \hat { \pmb { x } } _ { k + 1 ~ , k } ) \right] \mathrm { ~ } ]
$$

式中 $\hat { \mathbf { \Omega } } _ { \pmb { x } _ { k + 1 } , k }$ 为利用 $k$ 时刻状态量的一步预测值，$\hat { \pmb { x } } _ { k + 1 ~ k + 1 }$ 为 $k + 1$ 时刻状态量的最优估计值 $, \pmb { y } _ { k + 1 }$ 为$k + 1$ 时刻的测量值 $\mathbf { \Delta } , \pmb { H } _ { k + 1 }$ 为测量方程的关系矩阵，$\pmb { P } _ { k , k }$ 为 $k$ 时刻的误差协方差阵， $\boldsymbol { Q } _ { k }$ 为系统噪声序列方差阵 $\pmb { R } _ { k + 1 }$ 为量测噪声序列方差阵，

给定相对状态初值 $X _ { 0 }$ 和初始误差协方差阵$\pmb { P } _ { 0 }$ 即可采用EKF算法对编队相对轨道状态进行估计.

# 4仿真结果及分析

主星与从星的轨道高度相同均为 $7 4 0 0 ~ \mathrm { k m }$ 主星的离心率为 $0 ^ { \circ }$ ,轨道倾角为 $3 0 ^ { \circ }$ ,升交点赤经为$1 0 ^ { \circ }$ 近地点幅角为 $6 0 ^ { \circ }$ 主、从星间距离约为 $1 ~ \mathrm { k m }$ 卫星编队相对轨道状态滤波修正过程的原理如图3所示.

作为卫星编队真值的相对轨道信息计算时考虑了 $J _ { 2 }$ 项摄动影响，这样更接近真实运动情况，而在滤波算法中采用了没有考虑任何摄动影响的Hill方程.星间无线电测距精度为1cm.首先初步给出误差较大的从星相对轨道状态.然后以初始相对轨道信息作为下一步修正的测量值，加入星间测距信息，以式(4)作为状态方程，式(8)作为观测方程，采用EKF滤波算法对相对轨道信息进行二次滤波修正.取初始估计的相对轨道状态作为滤波状态初值 $X _ { 0 }$ 1初始协方差阵取 $P _ { \mathrm { { 0 } } } = \mathrm { { d i a g } \{ 1 0 0 , 1 0 0 , 1 0 0 , 1 0 0 , 1 0 0 } $ $1 0 0 \}$ ,过程误差方差阵取 $Q \ = \ \mathrm { d i a g } \{ 1 0 ^ { - 6 } \ \mathrm { ~ }$ 1 $1 0 ^ { - 6 }$ 1$1 0 ^ { - 6 } , 1 0 ^ { - 1 0 } , 1 0 ^ { - 1 0 } , 1 0 ^ { - 1 0 } \}$ ，测量误差方差阵取 $\pmb { R } =$ $\mathrm { d i a g } \{ 1 , 1 , 1 , 1 0 ^ { - 6 } , 1 0 ^ { - 6 } , 1 0 ^ { - 6 } , 1 0 ^ { - 4 } \}$ 修正前和修正后的从星相对轨道状态误差曲线如图4和图5所示.

星载GPS接收机 滤波器 主星绝对位置信息时间同步 主星 主定 星间测距 求差 相对位 滤波器 修正后相对位置星间距离信息  
星载GPS接收 滤波器从星 从星绝对 从星绝对位置信息轨道确定

![](images/1e168199d4259f6afb7f4c380491a9d16094220fbf57286c698d022a0e50073f.jpg)  
图3卫星编队相对状态确定原理图  
Fig.3Schematicdiagramoftherelativestate determinationforsatellitesformation   
图4修正前后从星相对位置误差对比图Fig.4The relative position error contrast

![](images/5d60ef692946db82410f93aaa2ebeb2c18be6ec9306afe6b2e3dd5c92e2f98da.jpg)  
图5 修正前后从星相对速度误差对比Fig.5The relative velocity error contrast

表1相对轨道状态的估计误差Tab.1 Standard deviation of the relative orbit states  

<html><body><table><tr><td></td><td>gx/m</td><td>gy/m</td><td>σ/m</td></tr><tr><td>修正前</td><td>9.806 0</td><td>9.890 3</td><td>10.007 4</td></tr><tr><td>修正后</td><td>0.204 2</td><td>0.194 7</td><td>0.062 5</td></tr><tr><td></td><td>σx/(m/s)</td><td>gvy/(m/s)</td><td>gvz/( m/s)</td></tr><tr><td>修正前</td><td>0.0101</td><td>0.010 1</td><td>0.009 8</td></tr><tr><td>修正后</td><td>5.885 7×10 -4</td><td>5.293 1×10 -4</td><td>2.7278 ×10 -4</td></tr></table></body></html>

从仿真结果可以看出，未采用星间测距信息修正前从星相对位置误差最大约为 $2 0 \mathrm { ~ m ~ }$ ,相对速度误差最大约为 $0 . 0 1 ~ \mathrm { m / s }$ 加入星间测距信息对相对轨道状态修正后，稳定段相对位置最大误差小于$1 \mathrm { ~ m ~ }$ 相对速度最大误差小于 $1 \times 1 0 ^ { - 3 } \mathrm { m / s } .$ 表1给出了修正前后各轴的估计精度.

从表1中可以看出加入星间测距信息修正后，星间相对轨道状态的估计精度明显改善.该方案中测量方程中共有7个测量值，下面考虑减少测量值的数目后是否还能达到修正的目的.在测量方程中减少3个相对速度测量方程变成4维其他条件不变对其进行仿真.下面给出测量方程维数减少后的仿真结果:从星相对位置估计精度 $\sigma _ { x } = 0 . 5 9 3 5 \mathrm { ~ m ~ }$ -$\sigma _ { y } ~ = 0 . 6 7 6 ~ 3 ~ \mathrm { ~ m ~ } ~ \sigma _ { z } ~ = 0 . 1 3 0 ~ 2 ~ \mathrm { ~ m ~ }$ 从星相对速度估计精度 $\sigma _ { v x } = 9 . 4 5 3 4 \times 1 0 ^ { - 4 } \mathrm { ~ m } / \mathrm { s }$ 5 $\sigma _ { \it { v y } } = 9 . 8 2 0 \mathrm { ~ 1 ~ \times ~ }$ $1 0 ^ { - 4 } ~ \mathrm { m / s } ~ \sigma _ { v z } ~ = ~ 3 . 9 0 2 ~ 4 ~ \times 1 0 ^ { - 4 } ~ \mathrm { m / s }$ ：

从仿真结果中可以看出，减少测量方程的维数后星间测距信息对相对轨道状态仍有修正作用，但是修正后的精度有所下降.测量方程的维数减少可以减少一定的计算量降低硬件的负担具有工程实际意义.

# 5结论

本文针对小型化的星载GPS系统对星间相对轨道状态估计精度不高的情况，提出了采用星间测距信息对其进行修正的方案.在测距精度为 $1 ~ \mathrm { c m }$ 的情况下进行了仿真验证，仿真结果表明采用星间测距信息进行修正可以明显地提高相对轨道状态估计精度.同时，文中还讨论了测量方程维数减少的情况此时对相对轨道状态仍有修正作用，但是修正精度有所下降.

# 参考文献

[1] 林来兴.小卫星编队飞行及其轨道构成[J]．中国空 间科学技术，2001(1):23-28. LINL X.Formation flying of small satellite and its orbital configuration [J].Chinese Space Science and Technology,2001(1) :23-28.   
[2]FERGUSON P,HOW JP.Decentralized estimation algorithms for formation flying spacecraft [C]//AIAA Guidance，Navigation and Control Conference and Exhibit.Austin,Texas,2003.   
[3] ALONSOR,CRASSIDISJL,JUNKINSJL.Vision based relative navigation for formation flying of spacecraft[C]//AIAA Guidance，Navigation，and Control Conference and Exhibit.Denver:CO,2000.   
[4] CORAZZINI T,HOW JP.Onboard GPS signal augmentation for spacecraft formation flying[C]//Proceedings of the Institute of Navigation GPS,Institute of Navigation．Nashville,1998,1937-1946.   
[5] OLSEN E.GPS sensing for formation flying vehicles [D]．Stanford，California:The Stanford University, 1999:1-18.   
[6] KROESR,MONTENBRUCKO,BERTIGERW,etal. Precise GRACE Baseline Determination Using GPS[J].

GPS Solution．2005(9) :21-31.

[7]ALFRIENDKT,GIMDW,SCHAUBH.Gravitational perturbations,nonlinearity and circular orbit assumption effects on formation flying control strategies [J].Guidance and control 2000 ,2000:139-158.   
[8] 张洪华林来兴.卫星编队飞行相对轨道的确定[J]. 宇航学报,2002 23(6):77-80. ZHANGHH，LINL X.The determination of relative orbit for formation flying[J].Journal of Astronautics, 2002 23(6):77-80.

[9］秦永元 张洪钺,汪叔华.卡尔曼滤波与组合导航原理[M].西安:西北工业大学出版社2007:182-186.

作者简介：张晓磊(1985一）男，硕士研究生研究方向为小卫星编队自主导航算法设计，飞行器动力学、控制与仿真;郑建华(1966一）女研究员研究方向为飞行器动力学、控制与仿真、深空探测与轨道设计、鲁棒控制理论及应用、小卫星编队飞行动力学与控制;高东(1978一）男副研究员研究方向为小卫星编队飞行姿态控制与自主导航算法设计;钱航(1987一）男，博士研究生，研究方向为太阳帆航天器动力学、控制与仿真，

# （上接第41页）

综上所述:在双曲线轨道自主导航中,远离近点的轨道段导航精度很低，但对自标天体特性依赖小，且在靠近近点的位置进行轨道确定的效果理想能够满足近点自主制动任务要求的精度.在椭圆轨道导航中合理选择计算周期对精度有较大影响，滤波的效果不明显，不适用于近圆轨道，

# 参考文献

[1] YIM JR.Autonomous spacecraft orbit navigation [D]. Huston: Thesis of Texas A&M University.2002.   
[2] RICHARD W Z,SUZANNEE S.An overview of the Mars reconnaissance orbiter（MRO） science mission [J]．Journal of Geophysical Research,20O7,112:1- 22.   
[3] CHENG Y ,MILLERJ.K.Autonomous landmark based space-craft navigation system[J].International Aerospace Abstracts ,2003 114(3):1769-783.   
[4] CANGAHUALAA,BHASKARANS,Owen S.Science benefits of onboard spacecraft navigation [J].EOS, Transactions American Geophysical Union，2012,93 (18):177-78.   
[5] ZUREK WR,LEONARDJM.Interannual variability of planet-encircling dust storms on Mars[J].Journal of Geophysical Research,1993 98(E2) :3247-3259.   
[6]IVASHIN VV.An analysis of characteristics of the satellite autonomous optical navigation system [J].Advances in the Astronautical Sciences,1983 83:328.   
[7］朱圣英常晓华崔祜涛 等.基于视线矢量的深空自 主导航算法研究[J]．空间科学学报,201131(4)： 534-540. ZHU SY CHANG XH CUIHT etal.Research on autonomous navigation algorithm of deep space based on line of sight vector[J].Chinese Journal of Space Science 2011 31(4):534 -540.

作者简介：唐青原(1990一）女硕士研究生研究方向为导航制导与控制；王晓磊(1972一），男研究员，研究方向为导航制导与控制。