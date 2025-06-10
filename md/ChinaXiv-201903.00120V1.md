# 永磁同步电机转子静止式参数辨识

吕广强闫耀程（南京理工大学自动化学院南京210094）

![](images/2334bdfc4888dd51bf7204a2938f028e9b0fb54cb82c2e006a4996c9415273eb.jpg)

吕广强男1974年生，副教授，博士，研究方向为电能质量检测与治理、电力变换器应用及微网控制。

摘要：本文提出一种在转子完全静止条件下精确辨识永磁同步电机（PMSM）交直轴电感的方法。该方法结合转子初始位置检测技术，在转子静止条件下给电机定子施加高频交流电压，对重构电压和响应电流进行离散傅里叶变换（DFT）后结合电机等效模型分别计算交直轴电感。文章首先叙述了现有永磁同步电机电感参数辨识方法，论述了各方法的优缺点。然后结合永磁同步电机的数学模型，深入分析了本文提出的转子静止式辨识方法的原理和辨识过程中的空间矢量状态。通过建立参数辨识系统与矢量控制系统，在实际电机上验证了该方法的有效性和精确性。结果表明，该方法能够可靠辨识永磁同步电机电感参数，有效减弱电流谐波的影响，尤其适用于空间谐波含量较高的内置式永磁同步电机 (IPM)。

关键词：永磁同步电机转子位置检测 参数辨识转子静止状态中图分类号：TM341

# Inductance Parameters Identification of Permanent Magnet Synchronous Machine at Standstill

![](images/f0bd7422d05863e803d4949ad850f1cf59de4bcf17f57bf6874d06af95df74fe.jpg)

Li GuangqiangYan Yaocheng (Nanjing University of Science and TechnologyNanjing 210094 China ）

闫耀程男 1990年生，硕士研究生，研究方向为电力电子与电机驱动控制。

Abstract: An innovation of inductance parameters identification for permanent magnet synchronous machine (PMSM),combined with the initial rotor position detection technology, was implemented by applying a high frequency voltage to stator. The inductance of d- and q-axis can be calculated from the equivalent model of PMSM after the rebuilt voltage and responsive current signals were processed with Discrete Fourier Transform. Herein,we primarily introduced the merit and defect of the existing inductance identification methods of PMSM and further analyzed the presented principles and states of space vectors in detail using the mathematical model.In order to confirm the efficiency and accuracy of this identification method,parameter identification system and vector control system were established. Ultimately,the results indicated that this method which is particularly suitable for interior permanent magnet synchronous motors,can identify inductance parameters of PMSM satisfactorily and reduce the current harmonics effectively.

Keywords: Permanent magnet synchronous motor, rotor position detection, parameter identification,standstill

# 1 引言

永磁同步电机（PermanentMagnetSynchronousMachine，PMSM）因其结构简单、运行可靠；体积小、质量轻；损耗小、效率高等显著优点，被广泛应用在航空航天、国防和工农业生产等领域[]。拥有准确的电机参数是实现永磁同步电机高性能控制系统的前提条件。永磁同步电机高性能控制系统广泛应用矢量控制技术，该控制系统设计用到的主要电机参数有定子电阻 $R _ { \mathrm { s } }$ ，同步旋转坐标系下的交直轴电感 $L _ { \mathrm { d } }$ ， $L _ { \mathrm { q } }$ ，转子永磁体磁链 $\boldsymbol { \varPsi } _ { \mathrm { f } }$ 等。定子电阻通过施加两段幅值不同的直流定子电流就可以较准确辨识，而转子磁链可以通过电机额定参数计算。辨识交直轴电感参数的传统方法需要转子以恒速旋转，文献[2-6]中介绍了在电机恒速旋转的条件下辨识电机电感的在线辨识方法，但这些方法大都需要冗繁的计算，编程实现难度很大。文献[7-8]中使用的基于信号处理法和系统识别理论的辨识方法，简单易实现，但仍需电机恒速运转。

一般情况下，控制系统需要在起动电机之前获取电机参数，以得到优越的起动动态性能；另外，由于机械连接，很多情况下电机正式工作前不允许转子转动。这些情况必须使用转子静止式的参数辨识策略。因此，对于将电机驱动系统产品化的变频器与伺服电机生产企业，解决电机参数辨识静止化的问题刻不容缓。

文献[2]介绍了离线实验测量得到电机交直轴电感的方法，但很难被工程应用。文献[2]中介绍的电压阶跃响应法在转子静止条件下给定子施加阶跃电压，通过检测响应电流计算电感参数。该方法对电流采样精度的依赖性比小直流电流衰减法小，但不能解决空间谐波的问题，辨识精度和稳定性较差。文献[9]使用有限元法通过复杂计算得到永磁电机的电感参数，该方法考虑了交直轴之间交叉饱和对辨识结果的影响，但是计算过程复杂，程序编写困难。

本文提出一种转子静止条件下辨识永磁同步电机电感的方法。首先寻找转子dq轴初始位置，不需要转子位置拉入。模仿转子位置检测过程中给定子施加高频电压信号的方法，以PMSM矢量控制系统为基础，通过给定子施加类似的高频正弦电压信号激励出正弦电流响应，利用电压重构技术和DFT算法对电压电流信号处理，消除由死区带来的电压偏差，削弱空间谐波的影响，实现电感的精确辨识。

该方法特别适合于内置式永磁同步电机和同步磁阻电机等由于气隙磁场不均匀造成电流谐波含量较高的电机。

# 2 同步旋转坐标系数学模型

同步旋转坐标系下的数学模型是永磁同步电机控制最常使用的模型。它不仅可以用来分析电机的稳态运行性能，也能用于分析电机的瞬态特性[2]。永磁同步电机dq轴等效模型如图1所示。

![](images/bc9c08215c6d932c5d460d54052420c42bee383f8e8647bd1ecd05cc3cc64973.jpg)  
图1永磁同步电机dq轴等效模型  
Fig.1PMSM equivalent model on dq axis

首先假设： $\textcircled{1}$ 忽略电动机铁心的饱和； $\textcircled{2}$ 不计电动机的铁损； $\textcircled{3}$ 电机三相绕组对称，在空间相差$1 2 0 ^ { \circ }$ 电角度，所产生的磁动势沿气隙按正弦规律分布。得到电机dq坐标下的电压方程

$$
\left\{ \begin{array} { l } { \displaystyle u _ { \mathrm { d } } = R _ { \mathrm { s } } i _ { \mathrm { d } } + \frac { \mathrm { d } \psi _ { \mathrm { d } } } { \mathrm { d } t } - \omega \varPsi _ { \mathrm { q } } } \\ { \displaystyle u _ { \mathrm { q } } = R _ { \mathrm { s } } i _ { \mathrm { q } } + \frac { \mathrm { d } \psi _ { \mathrm { q } } } { \mathrm { d } t } + \omega \varPsi _ { \mathrm { q } } } \end{array} \right.
$$

磁链方程为

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { \boldsymbol { \psi } _ { \mathrm { d } } = L _ { \mathrm { d } } \boldsymbol { i } _ { \mathrm { d } } + \boldsymbol { \varPsi } _ { \mathrm { f } } } \\ { \boldsymbol { \psi } _ { \mathrm { q } } = L _ { \mathrm { q } } \boldsymbol { i } _ { \mathrm { q } } } \end{array} \right. } \end{array}
$$

转矩方程为

$$
T _ { \mathrm { e } } = \frac { 3 } { 2 } p ( \psi _ { \mathrm { f } } i _ { \mathrm { q } } + ( { \cal L } _ { \mathrm { d } } - { \cal L } _ { \mathrm { q } } ) i _ { \mathrm { d } } i _ { \mathrm { q } } )
$$

运动方程为

$$
T _ { \mathrm { e } } = T _ { \mathrm { L } } + { \cfrac { J } { p } } { \cfrac { \mathrm { d } \omega } { \mathrm { d } t } }
$$

式中， $i _ { \mathrm { d } }$ 、 $i _ { \mathrm { q } }$ 为定子合成电流在d、q轴上的分量;$L _ { \mathrm { d } }$ 、 $L _ { \mathrm { q } }$ 为定子在d、q轴上的等效电枢电感； $p$ 为极对数； $T _ { \mathrm { L } }$ 为总负载转矩； $J$ 为总转动惯量。

# 3 电感参数辨识

本论文提出的电感参数辨识策略可分为三部分：转子位置检测、直轴电感辨识和交轴电感辨识。

# 3.1转子初始位置检测

永磁同步电机转子初始位置信息不仅是参数辨识的需求，更是电机正常起动运行必备条件。简单的将转子磁极拉到d轴，可以满足电机起动的需要，但不能满足本文转子静止的要求。

本文使用一种无位置传感器转子初始位置检测方法，首先在估算位置下的同步旋转坐标系中注入高频正弦电压信号，通过闭环调节得出转子位置初次估算值，再利用不同磁极下直轴等效电路时间常数不同的特性，判断出d轴正方向，结合初次估算值，得到正确的初始位置信息[10]。

图1为永磁同步电机dq轴电机等效模型。电机静止时，转速 $\omega = 0$ 电机在dq轴上相当于 $R _ { \mathrm { L } }$ 串联负载。电压方程简化为

$$
{ \binom { i _ { \mathrm { d } } } { i _ { \mathrm { q } } } } = \left( \begin{array} { c c } { { 1 / Z _ { \mathrm { d } } } } & { { 0 } } \\ { { 0 } } & { { 1 / Z _ { \mathrm { q } } } } \end{array} \right) \left( { u _ { \mathrm { d } } } \right)
$$

式中， $Z _ { \mathrm { d } }$ ， $Z _ { \mathrm { q } }$ 为交直轴阻抗。

首先，假定位置估算在与定子U相绕组电角度为0处，施加d轴高频正弦电压形式见式 (6)，若估算的位置不正确，那么q轴会有电流响应 $\hat { i } _ { \mathrm { q } } \not = 0$ ，$\hat { i } _ { \mathrm { q } }$ 形式见式（7)。

$$
\begin{array} { r } { ( \hat { u } _ { \mathrm { d } } ) = ( { U } _ { \mathrm { m } } \cos ( \omega _ { \mathrm { h } } t ) ) } \\ { \hat { u } _ { \mathrm { q } } ) ^ { - 1 } = 0 \quad \quad } \end{array}
$$

$$
\left\{ \begin{array} { l l } { \displaystyle \hat { i } _ { \mathrm { q } } = \frac { - \Delta Z \sin \left( 2 \Delta \theta \right) } { Z _ { \mathrm { d } } Z _ { \mathrm { q } } } U _ { \mathrm { m } } \cos \left( \omega _ { \mathrm { h } } t \right) } \\ { \displaystyle } \\ { \Delta Z = \frac { Z _ { \mathrm { d } } - Z _ { \mathrm { q } } } { 2 } } \end{array} \right.
$$

对式（7）进行必要的变换，有

$$
\left\{ \begin{array} { l l } { \displaystyle { \hat { i } _ { \mathrm { q } } = \frac { \omega _ { \mathrm { h } } \Delta L U _ { \mathrm { m } } } { \left| Z _ { \mathrm { d } } \right| \left| Z _ { \mathrm { q } } \right| } \sin { \left( \omega _ { \mathrm { h } } t - \varphi _ { \mathrm { d } } - \varphi _ { \mathrm { q } } \right) } \sin { \left( 2 \Delta \theta \right) } } } \\ { \displaystyle { \Delta L = \frac { L _ { \mathrm { d } } - L _ { \mathrm { q } } } { 2 } } } \end{array} \right.
$$

式中， $\lvert Z _ { \mathrm { d } } \rvert$ ， $| Z _ { \mathrm { q } } |$ 与 $\varphi _ { \mathrm { d } }$ ， $\varphi _ { \mathfrak { q } }$ 分别为d、q轴阻抗幅值和相角。然后对 $\hat { i } _ { \mathrm { q } }$ 进行适当的信号处理， $\hat { i } _ { \mathrm { q } }$ 经过乘法器和低通滤波器后，得到含有位置误差信息的信号 $f _ { \Delta \Theta }$ [10]见式（9)。将信号 $f _ { \Delta \Theta }$ 积分后作为位置估算结果提供给控制系统，形成闭环反馈。数个高频电流周期后，该信号将收敛到一个位置估算值 $\theta$ 。闭环控制系统如图2所示。

$$
f _ { \Delta \theta } = \frac { \omega _ { \mathrm { h } } U _ { \mathrm { m } } \Delta L \cos \left( \varphi _ { \mathrm { d } } + \varphi _ { \mathrm { q } } \right) } { 2 \left| Z _ { \mathrm { d } } \right| \left| Z _ { \mathrm { q } } \right| } \mathrm { s i n } \left( 2 \Delta \theta \right)
$$

![](images/2d68615a1283991dc63e6e9b938630586ce27d8fe7dea5ba183b09d681bfa85f.jpg)  
图2转子初始位置估算控制系统  
Fig.2Initial rotor position detection system

此时得到的估算值并不一定就是要寻找的位置，还有可能是d轴的反方向。将一个电角度分为4个区间，设定初始估算位置为0电角度，若实际的转子位置在区间 $\theta { \in } ( - \pi , \mathbf { \mu } _ { , } - \pi / 2 )$ ，那么 $\Delta \theta \in \mathsf { \Gamma } ( - \pi ,$ $- \pi / 2 )$ ，由式（9）可知 $f _ { \Delta \Theta } > 0$ ，经过图2的系统将收敛于 $\theta + \pi$ 。同理可以得到当转子实际位置在其他3个区间时位置估算值收敛的结果，见表1。

表1不同区间位置收敛值  
Tab.1The convergence value of different interval   

<html><body><table><tr><td>转子实际位置θ</td><td>估算位置收敛值</td></tr><tr><td>θ∈(-π，-π/2)</td><td>0+π</td></tr><tr><td>θ∈(-π/2，0)</td><td>0</td></tr><tr><td>0∈(0，π/2)</td><td>0</td></tr><tr><td>0∈(π/2，π)</td><td>0-π</td></tr></table></body></html>

根据以上分析，得到转子位置收敛结果后只要判断出d轴的正方向，就可以得到正确的转子位置。判断d轴正方向使用的是电感饱和效应[10]。在估算的d轴正反两个方向施加幅值大小合适并且相同的电压脉冲，如果电压脉冲方向与d轴正方向相同，该电压脉冲会增大d轴磁路的饱和，方向相反则会减弱磁路的饱和，两个方向上的电流响应峰值就会一大一小。通过检测两个电流响应的峰值，就可以判断出d轴的正方向，从而得到转子的正确位置信息[10]

# 3.2转子静止式辨识

根据上一节中转子初始位置检测的策略，可以得到d轴正方向的电角度位置 $\theta$ 。电机转子静止时，该角度保持不变，d轴与两相静止坐标系（ $\alpha \beta$ 坐标系） $\mathbf { \alpha } _ { \mathrm { ~ \tiny ~ d ~ } }$ 轴的夹角成为已知条件。不再需要转子位置拉入步骤，避免了转子发生旋转位移。

# 3.2.1 辨识原理

假设前面的转子位置检测结果为 $\theta$ ，向电机打入形如式（6）的交流电压，只是幅值和频率与前者不同，如下

$$
\begin{array} { r } { \left( \boldsymbol { u } _ { \mathrm { d } } \right) = \left( \begin{array} { c } { U _ { \mathrm { m l } } \cos \left( \omega _ { \mathrm { l } } t \right) } \\ { 0 } \end{array} \right) } \end{array}
$$

响应电流形式

$$
\left( { \begin{array} { c } { i _ { \mathrm { d } } } \\ { i _ { \mathrm { q } } } \end{array} } \right) = \left( { \begin{array} { c } { I _ { \mathrm { m 1 } } \cos \left( \omega _ { \mathrm { 1 } } t \right) } \\ { 0 } \end{array} } \right)
$$

由式（5）计算d轴电抗 $Z _ { \mathrm { d } } = U _ { \mathrm { d } } / I _ { \mathrm { d } }$ 。其中， $U _ { \mathrm { d } }$ ，$I _ { \mathrm { d } }$ 均为有效值。只要获得d轴给定交流电压和响应电流的有效值，由式（12）可计算出 $L _ { \mathrm { d } }$ 的值。

$$
\left\{ \begin{array} { l l } { ( \omega L _ { \mathrm { d } } ) ^ { 2 } + R _ { \mathrm { s } } ^ { 2 } = Z _ { \mathrm { d } } ^ { 2 } } \\ { L _ { \mathrm { d } } = \sqrt { Z _ { \mathrm { d } } ^ { 2 } - R _ { \mathrm { s } } ^ { 2 } } / \omega } \end{array} \right.
$$

在数字控制系统中，对电流的采样值为离散量，不能直接得到电流有效值。本文采用了离散傅里叶算法（DFT）辅助电流有效值的获取。DFT算法的思想是：对电流的一个周期 $N$ 次采样，只要采样满足采样定理，根据 $N$ 次的采样值，可直接得到各次谐波分量的实部和虚部，进而计算出相应量的有效值。

对电流一个周期内进行 $N$ 次采样，基波电流实部 $\boldsymbol { a } _ { 1 }$ 和虚部 $b _ { 1 }$ 为

$$
\left\{ \begin{array} { l l } { \displaystyle { a _ { 1 } = \mathrm { R e } [ x ( 1 ) ] = \frac { 2 } { N } \sum _ { n = 0 } ^ { N - 1 } x ( n ) \cos \left( \frac { 2 \pi n } { N } \right) } } \\ { \displaystyle { b _ { 1 } = \mathrm { I m } [ x ( 1 ) ] = \frac { 2 } { N } \sum _ { n = 0 } ^ { N - 1 } x ( n ) \sin \left( \frac { 2 \pi n } { N } \right) } } \end{array} \right.
$$

电流基波有效值为

$$
C _ { 1 } = \sqrt { \big ( a _ { 1 } ^ { 2 } + b _ { 1 } ^ { 2 } \big ) / 2 }
$$

定子三相电流检测值经过 $3 \mathrm { s } / 2 \mathrm { s }$ 变换和 $2 \mathrm { s } / 2 \mathrm { r }$ 变换，再经过上述DFT算法，计算出d轴电流基波分量的有效值 ${ I } _ { \mathrm { d o } }$

由于输出电压为PWM波，等幅不等宽，一般的变频器中没有成本昂贵的电压传感器，不能够直接测得输出电压的大小。由于死区等因素的影响，给定电压和实际输出电压之间存在偏差。为了减小偏差的影响，本文利用电压重构技术，首先还原输出电压为连续量，补偿死区的影响，然后根据DFT算法求出其有效值。

$s _ { 1 }$ 、 $s _ { 2 }$ 、 $s _ { 3 }$ 分别为上桥臂开关管在一个开关周期$T _ { \mathrm { s } }$ 内的给定瞬时相电压占空比[13]。三相电压可以表示为

$$
\begin{array} { r } { \left\{ V _ { \mathrm { a n } } = V _ { \mathrm { d e } } \left( \cfrac { 2 } { 3 } s _ { 1 } - \cfrac { 1 } { 3 } s _ { 2 } - \cfrac { 1 } { 3 } s _ { 3 } \right) } \\ { \right\} } \\ { V _ { \mathrm { b n } } = V _ { \mathrm { d e } } \left( \cfrac { 2 } { 3 } s _ { 2 } - \cfrac { 1 } { 3 } s _ { 1 } - \cfrac { 1 } { 3 } s _ { 3 } \right) } \\ { V _ { \mathrm { c n } } = V _ { \mathrm { d e } } \left( \cfrac { 2 } { 3 } s _ { 3 } - \cfrac { 1 } { 3 } s _ { 1 } - \cfrac { 1 } { 3 } s _ { 2 } \right) } \end{array}
$$

由死区引起的电压偏差量为[13]

$$
\Delta V = \nu _ { \mathrm { s x } } ^ { \ast } - \nu _ { \mathrm { s x } } = \mathrm { s g n } ( i _ { \mathrm { s x } } ) T _ { \mathrm { d } } f _ { \mathrm { s } } U _ { \mathrm { d c } }
$$

$$
\begin{array} { r } { \mathrm { s g n } \left( i _ { \mathrm { s x } } \right) = \left\{ \begin{array} { l l } { 1 } & { i _ { \mathrm { s x } } > 0 } \\ { 0 } & { i _ { \mathrm { s x } } = 0 } \\ { - 1 } & { i _ { \mathrm { s x } } < 0 } \end{array} \right. } \end{array}
$$

式中， $T _ { \mathrm { d } }$ 为死区时间； $f _ { \mathrm { s } }$ 为开关时间； $U _ { \mathrm { d c } }$ 为直流侧电压； $i _ { \mathrm { s x } }$ 为定子a、b、c相电流。

通过幅值不变的坐标变换，可以推导出dq坐标下的直轴电压和交轴电压。对重构出来的d轴电压使用DFT 算法，同样也获得基波分量有效值 $U _ { \mathrm { d } }$ 由式 $Z _ { \mathrm { d } } = U _ { \mathrm { d } } / I _ { \mathrm { d } }$ 与式（12）计算出 $L _ { \mathrm { d } }$ 。

由于只使用了基波分量，电机本身结构等因素所导致的空间谐波对辨识结果的影响将被大大削弱，使本方法比其他辨识策略有更好的精确性，特别适用IPM电机。图3为 $L _ { \mathrm { d } }$ 辨识过程系统框图。

q轴的电感辨识与d轴类似，向电机施加的电压形式见式(18)，响应电流形式见式(19)。

$$
\left( \begin{array} { c } { u _ { \mathrm { d } } } \\ { u _ { \mathrm { q } } } \end{array} \right) = \left( \begin{array} { c } { 0 } \\ { U _ { \mathrm { m 2 } } \cos \left( \omega _ { \mathrm { l } } t \right) } \end{array} \right)
$$

$$
\binom { i _ { \mathrm { d } } } { i _ { \mathrm { q } } } = \binom { 0 } { I _ { \mathrm { m 2 } } \cos \left( \omega _ { \mathrm { l } } t \right) }
$$

使用相同的电压重构技术和DFT技术，使用的q轴电压和电流基波分量有效值计算q轴电感 $L _ { \mathrm { q } }$ 。

![](images/1056e0c1e6dd9ba61b222af19eaa6cb7d9377feb40f3c5e63a4093d395f60f5a.jpg)  
图3电感参数辨识系统框图

# 3.2.2运行状态分析

假设某初始状态下d轴与U轴夹角为 $\theta$ 。图4、图5分别为d轴和q轴电感辨识过程中的矢量图。图4中，只有d轴电流分量、幅值大小按正弦规律在正负反复连续变化，且与转子磁链同轴，d轴磁链矢量与转子磁链矢量亦同轴，定转子磁场之间无力的相互作用。图5中，只有q轴电流分量，幅值大小同样按照正弦规律变化。q轴磁链因此也在q轴与电流同规律变化，并与转子永磁磁链呈 $9 0 ^ { \circ }$ 电角度，dq轴磁场之间产生非常强烈的磁力作用，使电机转子有发生转动的趋势。q轴磁链并不是一个旋转的磁链，而是一个正负之间连续脉动的磁链，所以转子不会发生旋转，而是会产生振动。如果施加的交流电压频率较低，电机转子会有较大振幅，并且产生大的振动噪声。为避免转子发生振动旋转位移和减弱噪声，q轴交流电压的频率必须较高，工程上可以使用 ${ 5 0 0 } \mathrm { H z }$ 。

![](images/a5862639d80f3247e1d2fddc10888c723bb90fd23bbdc1783ec1330ac2061e21.jpg)  
Fig.3Inductance identification system block diagram   
图5无直流分量 $L _ { \mathrm { q } }$ 辨识过程矢量图  
Fig.5Vector diagram of $L _ { \mathrm { q } }$ identification without DC bias

单相高频注入的过程中，可能由于机械振动等原因使转子偏离原位置，这种情况在空载条件下较常见。在d轴方向上增加小直流分量可维持转子位置固定。增加d轴直流分量后，d轴电感辨识过程中的电流合成矢量方向不变，只向d轴正方向偏移一个直流量。q轴电感辨识过程中各矢量关系如图6所示，可以看出，增加直流分量后，电流合成矢量的方向变化范围缩小，不仅能够锁住转子位置，还可以起到降低振动噪声的作用。

![](images/07825a26ad2245b8ac1c90f666bf448b50fadebf66faebf48e3fa9197ed61a25.jpg)  
图4无直流分量 $L _ { \mathrm { d } }$ 辨识过程矢量图  
Fig.4Vector diagram of $L _ { \mathrm { d } }$ identification without DC bias

由式（10）和式（18）得出，带有d轴小直流

![](images/fc93dbf3de85f42e8d8c26c17aca1cc99c176f50de4d0e5ac52bfe9bccc8e393.jpg)  
图6有直流分量 $L _ { \mathrm { q } }$ 辨识过程矢量图

分量的电压给定为：

d轴辨识过程

$$
\binom { u _ { \mathrm { d } } } { u _ { \mathrm { q } } } = \left( \begin{array} { c } { U _ { \mathrm { m l } } \cos { ( \omega _ { \mathrm { l } } t ) } + U _ { \mathrm { D C } } } \\ { 0 } \end{array} \right)
$$

q轴辨识过程

$$
\begin{array} { r } { \left( \begin{array} { c } { u _ { \mathrm { d } } } \\ { u _ { \mathrm { q } } } \end{array} \right) = \left( \begin{array} { c } { U _ { \mathrm { D C } } } \\ { U _ { \mathrm { m l } } \cos \left( \omega _ { \mathrm { l } } t \right) } \end{array} \right) } \end{array}
$$

利用坐标变换并结合式 (11）和式 (19)，得到d、q辨识过程中三相定子电流波形分别满足式(22）和式（23）。

$$
\left( \begin{array} { c } { i _ { \mathrm { a } } } \\ { i _ { \mathrm { b } } } \\ { i _ { \mathrm { c } } } \\ { i _ { \mathrm { c } } } \end{array} \right) = \left( \begin{array} { c } { I _ { \mathrm { p c } } \cos \theta + I _ { \mathrm { m } 1 } \cos \theta \cos \omega _ { \mathrm { 1 } } t } \\ { \cos \left( \theta - \frac { 2 } { 3 } \pi \right) + I _ { \mathrm { m } 1 } \cos \left( \theta - \frac { 2 } { 3 } \pi \right) \cos \omega _ { \mathrm { 1 } } t } \\ { I _ { \mathrm { D c } } \cos \left( \theta + \frac { 2 } { 3 } \pi \right) + I _ { \mathrm { m } 1 } \cos \left( \theta + \frac { 2 } { 3 } \pi \right) \cos \omega _ { \mathrm { 1 } } t } \end{array} \right)
$$

$$
\left( \begin{array} { c } { i _ { \mathrm { a } } } \\ { i _ { \mathrm { s } } } \\ { i _ { \mathrm { c } } } \\ { i _ { \mathrm { c } } } \end{array} \right) = \left( \begin{array} { c } { I _ { \mathrm { D c } } \cos \theta - I _ { \mathrm { m 2 } } \sin \theta \cos \omega _ { \mathrm { 1 } } t } \\ { \cos \left( \theta - \frac { 2 } { 3 } \pi \right) - I _ { \mathrm { m 2 } } \sin \left( \theta - \frac { 2 } { 3 } \pi \right) \cos \omega _ { \mathrm { 1 } } t } \\ { I _ { \mathrm { D c } } \cos \left( \theta + \frac { 2 } { 3 } \pi \right) - I _ { \mathrm { m 2 } } \sin \left( \theta + \frac { 2 } { 3 } \pi \right) \cos \omega _ { \mathrm { 1 } } t } \end{array} \right)
$$

# 4 实验结果

本文使用瑞萨单片机为主芯片搭建了永磁同步电机控制系统实验平台，包括三相不控整流、三相桥式电压源型逆变电路以及采样、调理等电路。

以SVPWM控制技术为基础实现了PMSM的最大转矩电流比控制（Maximum Torque perAmpereControl)。

为验证所提出的电感辨识策略的有效性和精确性，对3台不同品牌的永磁同步电机（PM1：登奇$0 . 7 5 \mathrm { k W }$ ；PM2：士林 $3 . 7 \mathrm { k W }$ ；PM3：朗高 $7 . 5 \mathrm { k W } \cdotp$ ）进行了参数辨识。其中前两台为SPM类型PM，标称参数 $L _ { \mathrm { d } } = L _ { \mathrm { q } }$ 。3台PM的电感参数标称值见表2。

Tab.2Motor nominal parameters   

<html><body><table><tr><td>电机编号</td><td>PM1</td><td>PM2</td><td>PM3</td></tr><tr><td>Ld/mH</td><td>33.25</td><td>1.33</td><td>5.73</td></tr><tr><td>Lq/mH</td><td>33.25</td><td>1.33</td><td>10.38</td></tr></table></body></html>

实验中为保证正确性和降低噪声，选择 ${ 5 0 0 } \mathrm { H z }$ 输出电流频率， $1 0 \mathrm { k H z }$ 载波。表3为本文方案的辨识实验结果，可见辨识结果与电机名牌标称值不完全一致。这是由温升、磁路饱和等因素导致的，也正是需要参数辨识的一个原因。

表2电机标称参数   
表3电机参数辨识结果  
Tab.3 Identification results   

<html><body><table><tr><td>电机编号</td><td>PM1</td><td>PM2</td><td>PM3</td></tr><tr><td>Ld/mH</td><td>30.83</td><td>1.43</td><td>5.27</td></tr><tr><td>Lq/mH</td><td>39.54</td><td>1.52</td><td>9.83</td></tr></table></body></html>

图 $7 \sim 1 0$ 为登奇 $0 . 7 5 \mathrm { k W }$ PM转子初始位置检测、dq轴电感辨识全过程各阶段定子电流波形，图中各通道的纵坐标每格为1A，横坐标每格为1ms或5ms，见图中标注。图7为转子位置估算的收敛过程（为了波形清晰，图中只有三相电流中的两相)，三相电流很快稳定收敛。图8为判断d轴的正方向阶段电流波形。图中正反两个方向的电流响应峰值有明显差异，可正确判定d轴的正方向。图9和图10分别为该位置上的d、q轴电感辨识阶段三相定子电流波形。波形中带有d轴小直流分量，保持电机转子位置固定。波形满足式（22）和式(23)。

![](images/18333ea602a85583c7cfea265c496f7e8c2bdcec134f581811b4dd713cde6be1.jpg)  
Fig.6Vector diagram of $L _ { \mathrm { q } }$ identification with DC bias   
图7转子初始位置检测第一阶段电流波形 Fig.7Stator current during first stage of initial rotor position detection

![](images/0d01039fe68ecd02981792baadeb31cd3482f2fb1dd5035cc43ccfdc8bac1a96.jpg)  
图8转子初始位置检测第二阶段电流波形

以转子静止式辨识方法得到的电机电感参数为基础，结合PI参数整定，建立PMSM最大转矩电流比控制系统。图11为MTPA控制系统框图。

![](images/4e59f9d37468ef2e2b21a8dd333918413714b3d7dd266d28196a621c0330676e.jpg)  
图9d轴电感辨识过程电流波形

![](images/dfef083e0f2b7c5c33ad9af67858917baddae8a109d7a7181cbef3089ff39f25.jpg)  
Fig.9Stator current during $L _ { \mathrm { q } }$ identification   
图10q轴电感辨识过程电流波形  
Fig.10Stator current during $L _ { \mathrm { q } }$ identification

![](images/05c95126e4cc0e7ddf699a384f8604b4ada60d9971327c3ffbca603d60693db1.jpg)  
Fig.8Stator current during second stage of initial rotor position detection   
图11最大转矩电流比控制系统框图  
Fig.11Maximum torque per ampere control system

为确定参数的准确性，分别测试该系统的起动特性，加卸载特性和转矩特性。使用朗高 $7 . 5 \mathrm { k W }$ 内置式PM电机进行上述动态性能测试。该电机各额定标称参数见表4。

图12为起动特性测试结果。图中各条曲线由下至上分别为电机以满载起动并匀加速至 $1 \mathrm { H z }$ ，$1 0 \mathrm { H z }$ ， $3 0 \mathrm { { H z } }$ ， $6 0 \mathrm { { H z } }$ 、 $8 0 \mathrm { H z }$ 和 $1 0 0 \mathrm { H z }$ 。从图中可以看到，电机加速过程平稳，加速度基本恒定，系统起动性能优越。

表4朗高 $7 . 5 \mathrm { k W }$ 电机参数  
Tab.4 Parameterof7.5kWPM   

<html><body><table><tr><td>额定功率</td><td>额定电压</td><td>额定电流</td><td>额定频率</td><td>额定转矩</td><td rowspan="2">极数</td></tr><tr><td>/kW</td><td>/V</td><td>/A</td><td>/Hz</td><td>/N· m</td></tr><tr><td>7.5</td><td>380</td><td>15</td><td>100</td><td>48</td><td>8</td></tr></table></body></html>

![](images/9ffc26b2cc0b4d4ec3173351531a73c65e88a1d0e34900e457583b7d0c606991.jpg)  
图12起动特性测试图

图13为加卸载特性测试结果。电机以 $5 0 \mathrm { { H z } }$ 恒速运行。图中两条曲线分别表示突加、突减 $50 \%$ 额定负载（波动较小者）与突加、突减 $100 \%$ 额定负载（波动较大者）电机转速的变化趋势。可以看到，加卸载过程中电机转速波动幅度较小，加卸载特性优越。

![](images/eb8d7c88ba2421244cdaf82cc4344cfd5783912c61b1667ca36b1d19359b5d65.jpg)  
Fig.12Startup characteristics   
图13加卸载特性测试图  
Fig.13Load/unload characteristics

图14为转矩特性测试结果。图中6条曲线从左至右分别为电机以 $1 \mathrm { H z }$ 、 $1 0 \mathrm { H z }$ 、 $3 0 \mathrm { { H z } }$ 、 $6 0 \mathrm { { H z } }$ ，$8 0 \mathrm { H z }$ 和 $1 0 0 \mathrm { H z }$ 运转时由空载均匀加载至 $1 5 0 \%$ 额定负载的过程。可以看到各条曲线没有明显向左倾斜，说明在负载增加过程中电机转速稳定好，系统转矩特性优越。

![](images/26eadc1b738fabe960aeecfc85a9e67dbc829fe2f7962a277e4587a4063a1b56.jpg)  
图14转矩特性测试图  
Fig.14Torque characteristics

通过测试确定了该控制系统动态性能优越，说明本文提出的参数辨识方法具有足够的精确性。

# 5 结论

本文结合转子初始位置检测使用一种新颖的永磁同步电机电感参数辨识策略，在转子完全静止的条件下实现了永磁同步电机交直轴电感的精确辨识。其转子完全静止的特点使变频控制系统能够应用于电机正式起动前不允许旋转的众多场合。该方法基于永磁同步电机的变频控制平台，不需要额外的硬件电路与测量设备，方便实用。DFT算法和电压重构技术大大削弱了谐波和死区对电流电压值计算的影响，显著提高了辨识精度，使本文策略尤其适用于谐波含量较高的IPM电机。

# 参考文献

[1] 唐任远．现代永磁电机理论与设计[M]．北京：机械工业出版社，1997：3-4.  
[2] 柳晶．变频空调永磁同步电机的参数辨识[D]．哈尔滨：哈尔滨工业大学，2010.  
[3] 赵莉，郭秋鉴，赵峰．内嵌式永磁同步电动机电感参数辨识[J]．微电机，2008，41(10)：35-38.Zhao li,Guo Qiujian,Zhao Feng.Inductanceparameter identification of interior permanent magnetsynchronous motor[J].Micromotors,2008,41(10):35-38.  
[4] JabbarMA,Dong Jing,Liu Zhejie.Determinationof parameters for internal permanent magnetsynchronous motors[C]. 2005:149-156.  
[5] 吴靖．电机传动系统参数辨识方法的研究[D]．杭州：浙江大学，2008.  
[6] 谭泓，曲国杰．基于系统识别理论在线参数辨识的永磁同步电动机无传感器控制[J]．电气技术，2006(10):112-121.Tan Hong,Qu Guojie.Sensorless control ofpermanent-magnet synchronous motors using onlineparameter identfication based on system identificationtheory[J].Electrical Engineering,2006(10):112-121.  
[7] Khwaja M Rahman,Silva Hiti.Identification ofmachine parameters of a synchronous motor[C].IEEE Transactions on Industry Applications,2005,41(2): 557-565.  
[8] 武立国，温旭辉，赵峰．永磁同步电机电感参数测量系统研究[J]．微电机，2008，41(12)：56-59.Wu Liguo,Wen Xuhui, Zhao Feng.Researchon inductance parameter measurement systemfor permanent magnet synchrinous motor[J].Micromotors,2008,41(12): 56-59.  
[9] 王卫平．内置式永磁同步电机交、直轴电枢反应电抗的准确计算[J]．微电机，2009，42(6)：11-13.Wang Weiping. Accurate calculation of quadrature-axis and direct-axis armature reaction reactance for ainterior permanent magnet synchronous machine[J].Microm0tors,2009,42(6): 11-13.  
[10] 刘颖，周波，李帅，等．转子磁钢表贴式永磁同步电机转子初始位置检测[J]．中国电机工程学报,2011，31(18):48-54.Liu Ying,Zhou Bo,Li Shuai,et al. Initial rotorposition detection of surface mounted permanentmagnet synchronous motor[J].Proceedings of theCSEE,2011,31(18): 48-54.  
[11] 高鹏，张斌，刘雨佳．两种智能算法在感应电动机参数辨识中的应用[J]．电气应用，2016，35(3)：45-49.  
[12] 孙向东，尚媛，钟彦儒，等．三相电压源逆变器输出电压重构技术的研究[J]．西安理工大学学报,2005，21(2):122-123.Shun XiangDong,Shang Yuan, Zhong Yanru,et al.Research on the reconstruction of output voltage inthree-Phase voltage source inverter[J].Journal ofXi'an University of Technology,2005,21(2):122-123.  
[13] 贺艳晖，王跃，王兆安．异步电机参数离线辨识改进算法[J]．电工技术学报，2011，26(6)：74-77.He Yanhui,Wang Yue,Wang Zhao'an.An improvedoff-line parameter identification algorithm forinduction motors[J]. Transactions of ChinaElectrotechnical Society, 2011,26(6): 74-77.