# 轨道交通用初级永磁型直线电机电磁特性分析

杨　雄」张凤阁」王秀平²（1.沈阳工业大学电气工程学院沈阳1108702.沈阳工程学院电力学院沈阳110136）

![](images/a3fa66baeefa33322f3fef8dae189c21ff01bb1cece46ada879af25562632592.jpg)

杨雄男1993年生，硕士研究生，研究方向为电机及其控制技术。

摘要：直线感应电机应用于轨道交通驱动系统，存在功率因数低、效率低的问题，本文提出了一种新型结构初级永磁型直线电机，该电机采用短初级(动子侧)、长次级（定子侧）结构，电机的电枢绕组和永磁体均安装于初级，次级仅为凸极磁阻结构。该种电机不仅具有常规直线感应电机结构简单和非黏着直接驱动等优点，且功率因数和效率等性能指标优良。论文首先详细介绍了该种电机的结构特点和运行机理，利用等效磁路法推导了该电机的气隙磁通密度方程和同步速方程；然后设计了一台12/8极的初级永磁型直线电机，借助应用有限元软件，进行了参数化建模和磁场分析，得到了次级极弧系数对磁场调制能力的影响规律；接着分析了电机的气隙磁场，得到了绕组反电动势波形图和气隙磁密傅里叶分解图形；最后，研究了电机静态特性，得到了次级结构对定位力的影响，电流大小对静态电磁推力的影响。仿真结果证明了电磁设计方案的合理性，为轨道交通直线驱动电机的研究提供了有价值的参考。

关键词：初级永磁型直线电机轨道交通 极弧系数有限元方法中图分类号：TM359.4

![](images/90710a7cbe03d2a1e9df448c3cf942ab146db3dbc80e79f9b5aa764bc6af7938.jpg)

张凤阁男 1963年生，教授，博士生导师，研究方向为特种电机及其控制技术。

# Electromagnetic Characteristics Analysis of Primary Permanent Magnet Linear Motor for Rail Transit

Yang Xiong'Zhang Fengge' Wang Xiuping² （1. Shenyang University of TechnologyShenyang 110870 China 2.Shenyang Institute of EngineeringShenyang110136 China ）

Abstract: The problem of low power factor and low efficiency is existed in the application of the linear induction drive motor to the rail transit system. This paper puts forward a kind of special structure of primary permanent magnet linear motor. The motor consists of short primary (rator side) and long secondary (stator side),armature windings and permanent magnets are installed in the primary side,and secondary are only salient pole reluctance. This kind of motor not only has the advantages of simple linear structure, non adhesion and direct drive,but also has good performance indexes such as power factor and efficiency,and has broad application prospects.Firstly, the structure characteristics and operation mechanism of the motor are introduced in detail. The air gap flux density equation and the synchronous speed equation are deduced by using the equivalent magnetic circuit method. Second, a 12/8 pole primary permanent magnet linear motor is designed. Parametric modeling and magnetic field analysis are carried out by using finite element software,and the influence of secondary polar arc coefficient on magnetic field modulation capability is obtained.Then,the air gap magnetic field of the motor is analyzed,and the winding back EMF waveform and the gap density fourier decomposition pattern are obtained. Finally,the static characteristics are studied,and the influence of secondary structure on the positioning force and the influence of the magnitude of current on the static electromagnetic thrust are studied.The simulation results show the rationality of the electromagnetic design scheme.It provides a valuable reference for the study of the linear drive motor of rail transit.

Keywords: PPMLM,rail transit, pole-arc coefficient, finite element method

# 1 引言

轨道交通系统使用的驱动电机主要有旋转电机和直线电机两种。与旋转电机驱动方式相比，直线电机驱动方式具有诸多优点，如结构简单、寿命长、爬坡能力强、轮径小、隧道断面小和线路设计自由度大等[1]。较为常见的是直线感应电机和直线式永磁同步电机。目前，直线感应电机驱动的轨道交通系统得到了应用，但存在效率和功率因数低的问题[2]；直线式永磁同步电机具有效率高、功率密度高、体积小且性能好等优点，但是传统直线永磁同步电机的电枢绕组和永磁体分别放置在电机的初级和次级，需沿轨道铺设永磁体，制造和维护成本高，限制了其在城市轨道交通等长距离运行场合中的应用[3]。

文献[4-6]提出的磁通切换永磁电机是一种新型电机，具有感应电动势大、功率密度高等优点。但是，该电机定位力较大，导致电机推力波动较大。T．A．Lipo教授等人在开关磁阻电机的基础上提出了一种双凸极永磁电机[7。此类电机由于是单极性永磁磁链电机，因此其功率密度略低于磁通切换永磁电机。游标永磁电机是近年发展起来的一种新型电机[8-1]，其永磁体置于初级齿端，每个齿有若干对永磁体，次级为凸极结构，绕组可采用分布绕组或集中绕组。该电机能够在低速时利用自身的游标效应产生较大的推力，缺点在于永磁体极间漏磁较大。

本文提出了一种新型初级永磁型直线电机(Primary Permanent Magnet Linear Machine，简 称PPMLM)，该种电机不仅具有常规直线感应电机结构简单和非黏着直接驱动等方面的优点，而且功率因数和效率等性能指标优良[12-13]，同时由于永磁体和绕组均位于电机初级 (动子侧)，沿轨道铺设的次级（定子侧）仅是普通导磁材料制成，该种电机可以显著降低制造成本，基本不需维护，因此在轨道交通领域展现出良好的应用前景。

# 2 电机结构

# 2.1 初级结构

论文提出的12/8极初级永磁型直线电机，其结构如图1所示。电机初级（动子）铁心由普通硅钢片叠压而成，初级上嵌有三相电枢绕组，并放置了永磁体，次级采用了普通凸极结构。电枢绕组极对数为 $\boldsymbol { q }$ ，永磁体极对数为 $p _ { \mathrm { P M } }$ ，两个磁场极对数不同。初级铁心采用半闭口槽设计。运行时，初级电枢磁场和永磁磁场借助次级磁阻的磁耦合作用，实现机电能量转换。这种结构的突出特点是：永磁体放置到了初级上，次级采用了普通凸极结构，降低了成本，提高了运行可靠性，改善了运行性能。

![](images/4d93c3a716698432a40ce0f158420b55c01115a5fe388e25197947942311a348.jpg)  
图112/8极PPMLM截面图  
Fig.1Sectional diagram of 12/8 pole PPMLM

# 2.2 次级结构

电机次级采用凸极磁阻结构，初级对应的凸极数为 $N _ { \mathrm { r } }$ ，且与永磁体和绕组的极对数满足一定的关系，即

$$
N _ { \mathrm { r } } = p _ { \mathrm { P M } } + q
$$

式中， $p _ { \mathtt { P M } }$ 和 $q$ 分别为永磁体和电枢绕组的极对数。图2所示为电机次级结构图，为了方便研究电机结构参数变化对电机性能的影响，可以先定义两个参数。定义极弧系数 $\alpha$ 为凸极部分长度与每极部分占的长度之比，极弧系数的表达式为 $\lambda _ { 1 } / \lambda _ { 2 }$ ，同时定义凸极坡度为 $\beta _ { 1 } / \beta _ { 2 }$ 。本文采用的次级结构既无绕组，也无永磁体，因此结构简单、可靠，特别适合应用于长距离轨道交通系统领域中。

![](images/41c18c69050a2a1b406ab1af985c67a17bb44eeb998a92f35bf0993cca0fbc27.jpg)  
图2次级结构图

# 3 运行原理

当PPMLM稳态运行时，电枢绕组在气隙中形成一个行波磁场，沿着直线方向呈正弦规律分布；永磁体产生一个静止的恒定磁场。这两个磁场通过次级进行调制，实现间接的耦合，并在动子上形成电磁转矩，其耦合原理如图3所示。

![](images/e5aa0775b379cceebf726f62bd90a85d457b7251bab1baf12276a79162b11d1a.jpg)  
Fig.2Secondary structure diagram   
图3耦合原理图  
Fig.3 Coupling schematic diagram

# 3.1气隙磁通密度分析

为了简化推导过程，本文做了一些必要的假设：不考虑初级齿槽影响，忽略漏磁；同时假定次级磁阻具有理想的磁阻特性，即次级齿顶部分的气隙单位面积的磁导是恒值，而次级齿间部分的气隙磁导为零；假设永磁体的相对磁导率为1。当初级和次级静止不动时，理想磁阻次级的气隙比磁导函数可表示为

$$
\lambda _ { \mathrm { g } } \left( x \right) = \lambda _ { 0 } + \sum _ { i = 1 } ^ { \infty } \lambda _ { i } \cos \left[ i N _ { \mathrm { r } } \frac { 2 \pi } { L _ { \mathrm { a } } } ( x - x _ { 0 } ) \right]
$$

式中， $\lambda _ { 0 }$ 为气隙磁导的平均值； $\lambda _ { i }$ 为 $i$ 阶磁导谐波幅值； $N _ { \mathrm { r } }$ 为次级凸极数； $L _ { \mathrm { a } }$ 为电机初级长度； $x _ { 0 }$ 为初级初始位置。

磁导谐波一阶谐波含量最大，通常忽略高阶磁导谐波，则电机空载气隙比磁导可以近似表示为

$$
\lambda _ { \mathrm { g } } \left( x \right) = \lambda _ { 0 } + \lambda _ { \mathrm { l } } \cos \left[ N _ { \mathrm { r } } \frac { 2 \pi } { L _ { \mathrm { a } } } ( x - x _ { 0 } ) \right]
$$

当电机运行后，此时的气隙比磁导相对次级坐标可表示为

$$
\lambda _ { \mathrm { g } } ( x , t ) = \lambda _ { \mathrm { 0 } } + \lambda _ { \mathrm { l } } \cos \left[ N _ { \mathrm { r } } \frac { 2 \pi } { L _ { \mathrm { a } } } ( x - x _ { \mathrm { 0 } } - \nu _ { \mathrm { t } } t ) \right]
$$

式中， $\nu _ { \mathrm { t } }$ 为电机运行速度。

此外，初级齿表面的永磁体在气隙中产生的磁动势也可以用傅里叶级数的形式表示为

$$
F _ { \mathrm { P M } } \left( x \right) = \sum _ { j = 2 n - 1 , n = 1 } ^ { \infty } \frac { 4 B _ { \mathrm { r } } h _ { \mathrm { P M } } } { j \mu _ { 0 } \pi } \mathrm { c o s } \left( j p _ { \mathrm { P M } } \frac { 2 \pi } { L _ { \mathrm { a } } } x \right)
$$

式中， $B _ { \mathrm { r } }$ 为永磁体剩磁； $h _ { \mathrm { P M } }$ 为永磁体厚度； $p _ { \mathtt { P M } }$ 为永磁体极对数； $\mu _ { 0 }$ 为真空磁导率。

忽略高次谐波的影响，永磁体在气隙中产生的磁动势可以近似表示为

$$
F _ { \mathrm { P M } } \left( x \right) = \frac { 4 B _ { \mathrm { r } } h _ { \mathrm { P M } } } { \mu _ { 0 } \pi } \cos \left( p _ { \mathrm { P M } } \frac { 2 \pi } { L _ { \mathrm { a } } } x \right)
$$

因此电机空载运行时，在气隙中产生的气隙磁通密度可近似表示为

$$
\begin{array} { r l } & { B _ { \mathrm { o g } } \left( x , t \right) = F _ { \mathrm { p M } } \left( x \right) \lambda _ { \mathrm { g } } \left( x , t \right) } \\ & { \qquad = \frac { 4 B _ { \mathrm { r } } h _ { \mathrm { p M } } \lambda _ { \mathrm { 0 } } } { \mu _ { 0 } \pi } \cos \left( p _ { \mathrm { p M } } \frac { 2 \pi } { L _ { \mathrm { a } } } x \right) + } \\ & { \qquad \frac { 2 B _ { \mathrm { r } } h _ { \mathrm { p M } } \lambda _ { \mathrm { 0 } } } { \mu _ { 0 } \pi } \cos \left[ \left( p _ { \mathrm { p M } } + N _ { \mathrm { t } } \right) \frac { 2 \pi } { L _ { \mathrm { a } } } \left( x - \frac { N _ { \mathrm { r } } \nu _ { \mathrm { t } } t + N _ { \mathrm { r } } x _ { \mathrm { 0 } } } { p _ { \mathrm { p M } } + N _ { \mathrm { r } } } \right) \right] + } \\ & { \qquad \frac { 2 B _ { \mathrm { r } } h _ { \mathrm { p M } } \lambda _ { \mathrm { 0 } } } { \mu _ { 0 } \pi } \cos \left[ \left( p _ { \mathrm { p M } } - N _ { \mathrm { r } } \right) \frac { 2 \pi } { L _ { \mathrm { a } } } \left( x + \frac { N _ { \mathrm { r } } \nu _ { \mathrm { t } } t + N _ { \mathrm { r } } x _ { \mathrm { 0 } } } { p _ { \mathrm { p M } } - N _ { \mathrm { r } } } \right) \right] } \end{array}
$$

上式中第一项的气隙磁通密度分量由永磁体直接产生，由于贴装于初级齿表面的永磁体与电枢绕组相对静止，因此，该分量并不能在电枢绕组中产生感应电动势；第二项和第三项的气隙磁通密度分量均由永磁磁通经次级凸极磁阻调制产生，其中第二项所表示的磁通波长较短，运行速度慢，而第三项则具有波长较长、运行速度快的特点。由感应电动势原理可知，感应电动势幅值与有效气隙磁通的变化率呈正比，因此选择第三项气隙磁通密度分量作为PPMLM的有效谐波分量，有利于提高电机的感应电动势，进而提高电机的推力密度。由式（7)分析可得有效谐波磁通的极对数 $\boldsymbol { p } _ { \mathrm { f l u x } }$ 和有效谐波运行速度 $\nu _ { \mathrm { f l u x } }$ 的表达式分别为

$$
p _ { \mathrm { f i l u x } } = \Big | p _ { \mathrm { P M } } - N _ { \mathrm { r } } \Big |
$$

$$
\nu _ { \mathrm { f i l u x } } = \frac { N _ { \mathrm { r } } } { p _ { \mathrm { P M } } - N _ { \mathrm { r } } } \bigg | \nu _ { \mathrm { t } }
$$

由式（8）可知，PPMLM的永磁体极对数 $p _ { \mathrm { P M } }$ 和有效谐波磁通极对数 $\boldsymbol { p } _ { \mathrm { f l u x } }$ 不相同，其原因是该有效谐波磁通分量是通过次级凸极磁阻结构调制而成的。电枢绕组极对数则可以按照该有效谐波磁通的极对数进行设计，即电枢绕组极对数 $q$ 等于有效谐波磁通极对数 $\boldsymbol { p } _ { \mathrm { f l u x } }$ 。本文所研究的12/8 极样机的永磁体极对数为6，电枢绕组极对数为4，初级长度对应下的次级凸极数为10。

# 3.2运行速度分析

直线电动机由旋转电动机演变而来，行波磁场的移动速度与旋转磁场在定子内圆表面上的线速度是一样的，行波磁场移动的速度称为直线电机同步速度 $\nu _ { \mathrm { s } }$ 。

在旋转电机中[14]，电机的同步转速为 $n _ { \mathrm { r } }$ ，且

$$
n _ { \mathrm { r } } = { \frac { 6 0 f } { p _ { \mathrm { P M } } + q } }
$$

式中， $f$ 为电枢绕组通入交流电的频率。

PPMLM的同步速可用下列公式表达

$$
\nu _ { \mathrm { { s } } } = { \frac { D } { 2 } } { \frac { 2 \pi n _ { \mathrm { { r } } } } { 6 0 } } = { \frac { D } { 2 } } { \frac { 2 \pi } { 6 0 } } { \frac { 6 0 f } { p _ { \mathrm { { P M } } } + q } } = { \frac { \pi D f } { p _ { \mathrm { { P M } } } + q } } = { \frac { L _ { \mathrm { { a } } } f } { N _ { \mathrm { { r } } } } }
$$

式中， $D$ 为旋转电机定子内圆周的直径； $N _ { \mathrm { r } }$ 为旋转电机同步数。当PPMLM作为电动机运行时，电枢绕组串接变频器起动后，可通过控制电枢绕组的频率来控制电机运行速度。

# 3.3绕组连接方式

本文所研究12/8极PPMLM，初级齿上永磁体极数为12，电枢绕组按8极设计，则每极槽数为0.5。为减小绕组端部长度，如图4所示，可采用集中绕组。

![](images/2bd813d418cc96cb13d2f15cb287aba7ce68b3b07246cc32d99fb768a11bb89b.jpg)  
图4绕组连接方式  
Fig.4Connection mode of winding

# 4 电机的磁耦合能力分析

PPMLM的电枢绕组和永磁体之间理论上是没有任何直接耦合关系，机电能量是通过次级对它们的磁耦合作用来实现的，次级起到了极数转换器的作用，次级耦合能力的强弱对电机性能好坏有很大的影响，因此对电机的次级结构参数的确定尤为重要。本节分析极弧系数对电机耦合能力的影响。

# 4.1凸极极弧系数对磁链的影响

凸极极弧系数是次级结构的主要参数之一，极弧系数决定了凸极间气隙的大小，从而影响次级的耦合能力。为了分析不同极弧系数下电机的性能，在相同电机结构尺寸和运行条件下，分别建立了极弧系数 $0 . 1 \sim 0 . 9$ ，增量为0.05的电机参数化模型。对不同极弧系数情况进行有限元分析，当永磁体单独激励时，如图5所示，分析A相绕组磁链幅值大小的变化，来研究电机的耦合能力。

![](images/e59282d61386f82ad927095770e8e233bf151dd869832cca870bb46749582bbd.jpg)  
图5极弧系数对电机耦合能力影响 Fig.5Influence of polar arc coefficient on motor coupling ability

从图5可以看出，随着极弧系数不断的增大，A相磁链幅值先增大，后减小。在极弧系数 $0 . 3 \sim 0 . 6$ 之间，A相磁链较大。

# 4.2凸极极弧系数对有效谐波含量的影响

对气隙磁通密度进行傅里叶分解，可得到8极有效谐波占基波百分比图形，如图6所示。

从图6可以看出，随着极弧系数不断地增大，电机有效谐波占基波百分比先增大，后逐步减小。这与A相磁链幅值变化规律相同，可得出绕组反电动势波形主要由8极有效谐波磁场产生。在极弧系数 $0 . 3 \sim 0 . 6$ 之间，虽然极弧系数越小，电机的有效次磁场分量含量越大，但较小的极弧系数会增加次级磁路的饱和程度。根据电机极弧系数选取经验，本文所用次级极弧系数取为0.45。

![](images/f4ec3d978b16a88d205d1835df987e7dcfa3d7deac8265d652d4b53956335672.jpg)  
图6有效谐波幅值占基波百分比

所示。将8次谐波磁场作为电机运行的有效气隙磁场，并根据其极对数进行电枢绕组设计，可以获得较大的感应电动势和推力密度。

# 5.3 定位力矩

定位力是端部力和齿槽力的统称，其大小和方向与电机运行状况无关。它是衡量永磁电机性能的重要指标之一，会影响电机起动性能，并造成转矩脉动[15-16]。为了研究凸极高度和坡度对电机定位力的影响，对电机进行参数化建模，从凸极高度$5 \sim 2 0 \mathrm { m m }$ 变化，步长为 $1 \mathrm { m m }$ ；凸极倾斜坡度从$0 \sim 0 . 6$ 变化，步长为0.1来研究电机的定位力变化规律。图9所示为采用Ansoft有限元仿真软件中的虚功法计算得到的电机定位力随凸极高度和坡度变化的规律。综合考虑凸极对磁场的调制作用，最后确定凸极高度取 $1 0 \mathrm { m m }$ ，坡度取0.4，此时电机的定位力为 $4 0 . 2 \mathrm { N }$ 。

![](images/6e74f7efcd0f5b504a308ace9c7e248ea19c7f5f8bcbe08cd9870281b0a3e706.jpg)  
Fig.6The percentage of effective harmonic amplitude accounts for the fundamental wave

# 5 静态特性

# 5.1空载反电动势

空载反电动势是衡量电机性能的重要指标，空载反电动势的大小反映了绕组匝数配合的合理性以及电机的带载能力。图7所示为三相绕组空载反电动势波形，反电势谐波含量较少。

![](images/e8feab094c14406885dffa0d3fc861209c711d32a7a70c052409a8a41ec41e30.jpg)  
图9不同凸极高度和坡度的定位力Fig.9Positioning forces of different pole heightsand gradients

# 5.2气隙磁密分解

基于有限元法对PPMLM的磁场和气隙磁密进行分析，得到垂直方向气隙磁密波形，利用傅里叶变化，分解出8次有效谐波磁密正弦波形。如图8

# 5.4静态电磁推力

![](images/c5bf679d9f098aac9381854211de71bf76d6baf5819566b498b2e691eaa1d705.jpg)  
图7空载感应电动势波形 Fig.7No-load Induced EMF   
图8空载气隙磁密  
Fig.8No-load air-gap flux density

静态电磁推力是指次级不动，初级绕组中通入直流电流，初级随位置变化的力。静态力位移特性是PPMLM最基本的特性，也是动态特性分析的基础。

为了满足轨道交通驱动系统直线电机推力的设计要求，可从直线电机自身的结构特点出发，引入“单元电机”的概念，通过改变这些“单元”的数目，在长度或宽度方向上排列组合，来达到改变电机输出推力的目的，并且可以认为单元间彼此独立，互不影响。

图10所示为不同直流电流下，电机的静态推力。随着通入电流的增大，推力呈现近似直线的增长趋势，这说明电机的铁心还未饱和。当通入电流大于9A时，随着通入电流的增大，推力增加逐渐趋向于平缓，这说明此时电机的铁心趋近于饱和。由仿真结果可知，电机所通电流为9A时，电机的利用率最高。在电流取9A时电机的平均推力约为$4 9 6 \mathrm { N }$ 。

![](images/84f4552c9fee9e50a88e0b17f6baf39dbe308aabf8f21e411d627e068de6e120.jpg)  
图10电机的静态推力 Fig.10Static thrust of motor

# 6 结论

本文提出并设计了一种新型结构初级永磁型直线电机，对该电机的电磁特性进行了分析，得出了电机的气隙磁密和同步速度方程；研究了电机的空载感应电动势、定位力和推力等静态特性。研究表明，基于凸极磁场调制效应，该电机气隙中产生波长长、运行速度快的谐波磁场，使其具有较大的空载感应电动势和电磁推力密度，特别适用于轨道交通系统。

# 参考文献

[1] Hellinger R,Mnich P.Linear motor-powered transportation:history,present status,and future outlook[J].Proceedings of the IEEE,2009,97(11): 1892-1900.   
[2] 韩永春．直线电机气隙与列车能耗的关系研究[J]. 铁道机车车辆，2015，35(6)：69-72. Han Yongchun.Study on the relationship between air gap and train energy consumption of linear motor[J]. Railway Rolling Stock,2015,35(6): 69-72.   
[3] Fan Y,Li G G,Lü G.Linear motors and their application in urban rail transit systems[J].Urban Rapid Rail Transit, 2006,19:1-6.   
[4] Hua W, Cheng M,Zhu Z Q,et al.Analysis and optimization of back EMF waveform of a fluxswitching permanent magnet motor[J].IEEE Transactions on Energy Conversion,20o8,23(3): 727-733.   
[5] Cao R,Cheng M, Mi C,et al. Modeling of a complementary and modular linear flux-switching permanent magnet motor for urban rail transit applications[J]. IEEE Transactions on Energy Conversion,2012,27(2): 489-497.   
[6]Min W, Chen JT, Zhu Z Q,et al. Optimization and comparison of novel e-core and c-core linear switched flux PM machines[J]. IEEE Transactions on Magnetics,2011, 47(8): 2134-2141.   
[7] 程明，周鹗．新型分裂绕组双凸极变速永磁电机的 分析与控制[J]．中国科学(E辑)，2001，31(3)： 228-237. Cheng Ming, Zhou E. Model split winding doubly salient permanent magnet motor analysis and control [J].Chinese Science (Series E),2001,31(3):228- 237.   
[8] Cheng M, Hua W, Zhang J, et al. Overview of statorpermanent magnet brushless machines[J]. IEEE Transactions on Industrial Electronics,2011,58(11): 5087-5101.   
[9] Chung S U, Kim JW, Woo B C,et al.A novel design of modular three-phase permanent magnet vernier machine with consequent pole rotor[J]. IEEE Transactions on Magnetics,2011, 47(10): 4215-4218.   
[10]Nakata Y, Ishiguro H, Kitani K, et al. Development and control of a novel cylindrical IPM linear vernier motor for compliant robot actuation[J]. Industrial Electronics Society,2013, 45(11): 2744-2749.   
[11]Du Y, Chau K T, Cheng M,et al. Design and analysis of linear stator permanent magnet vernier machines[J]. IEEE Transactions on Magnetics,2011, 47(10): 4219-4222.   
[12]杜怿，程明，邹国棠．初级永磁型游标直线电机 设计与静态特性分析[J]．电工技术学报，2012, 27(11): 22-30. Du Wei, Cheng Ming, Zou Guotang. Design and static characteristics analysis of primary permanent magnet linear vernier motor[J]. Journal of Electrotechnical Society,2012,27(11): 22-30.   
[13]刘文庆．直线游标永磁电机驱动系统研究[D]．镇 江：江苏大学，2015.   
[14]张凤阁，贾广隆，郑阳，等．无刷电励磁同步电机 的特性仿真与实验研究[J]．电工技术学报，2015, 30(14): 100-107.

Zhang Fengge,Jia Guanglong,Zheng Yang,et al. Simulation and experimental study of brushless electric excitation synchronous motor[J]. Journal of Electrotechnical Society, 2015,30(14):100-107. [15] 杜卫民．永磁直线电机的电磁设计及磁阻力研究

[D]．焦作：河南理工大学，2009. [16] Wang C F, Shen JX.A method to segregate detent force components in permanent-magnet fluxswitching linear machines[J].IEEE Transactions on Magnetics,2012,48(5):1948-1955.