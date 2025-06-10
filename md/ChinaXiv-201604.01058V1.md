# GMSK+PN信号信噪比估计

石立国1²，王竹刚¹，熊蔚明（1．中国科学院空间科学与应用研究中心，北京100190；2．中国科学院大学，北京100190)

摘要：针对数传、测距一体化的调制方式高斯最小频移键控复合伪码测距（Gaussian minimum shift keying $+$ pseudo-noise，GMSK十PN)信号的信噪比估计，提出了一种精度较高、复杂度较低的快速算法。该算法采用层状结构分解的方式，将信号分解为若干信号单元，对每一个分解的信号单元进行功率分配计算或信噪比估计，最后快速准确地计算出整个信号的信噪比。信噪比在 $1 { \sim } 1 3$ dB之间时，估计误差小于 $0 . 5 { \mathrm { ~ d B } }$ 。利用Simulink仿真工具，验证了该算法的有效性。

关键词：高斯最小频移键控；再生伪码测距；Tausworthe码；空间数据系统咨询委员会；信噪比中图分类号：TN911.75 文献标志码：A DOI:10.3969/j.issn.1001-506X.2016.01.05

# SNR estimation algorithm for GMSK+PN signal

SHI Li-guo1,²，WANG Zhu-gang1，XIONG Wei-mingl (1. Center for Space Science and Applied Research,Chinese Academy of Sciences， Beijing 100l90, China; 2.University of Chinese Academy of Sciences，Beijinglool90，China)

Abstract:Gaussian minimum shift keying $+$ pseudo-noise $( \mathrm { G M S K + P N } )$ is a modulation method which a chieves simultaneously transmisson of GMSK data and PN.For the signal to noise ratio（SNR）estimation of GMSK+PN modulation，a fast algorithm with high accuracy and low complexity is proposed.This algorithm applies layered structure decomposition to decompose signals into a number of units.Each decomposed signal's power is calculated or SNR is estimated.Then，signal power distribution calculation or SNR estimation is conducted sucessively for according units.Finally，SNR of the entire signal is calculated quickly and accurately. Estimation error is less than O.5 dB when SNR is between $1 \sim 1 3$ dB. Simulink simulation results verify the effectiveness of the proposed algorithm.

Keywords: Gaussian minimum shift keying（GMSK)；regenerative pseudo noise（PN） ranging； Tausworthe code；consultative committee for space data systems (CCSDS)；signal to noise ratio (SNR)

# 0 引言

分布式卫星系统要实现编队飞行，需要在测定子卫星之间相对位置的同时，还要求有子卫星间的数据交互。测距、通信一体化设计在许多卫星通信系统中都有涉及，例如中国科学院空间科学与应用中心的深空应答机。但其采用的一体化设计方案是时分复用的方式，无法实现同时完成测距和通信两种任务。目前，空间数据系统咨询委员会(consultative committee for space data systems,CCSDS)正在酝酿一种可以同时传输高码率数传信号和测距信号的技术体制。它采用高斯最小频移键控（Gaussianminimumshiftkeying，GMSK)1进行数传信号的传输，采用再生伪码(pseudo-noise，PN)进行测距[2]，被称为高斯最小频移键控复合伪码测距（Gaussian minimum shiftkeying $+$ pseudonoise,GMSK十PN)调制方式[3]，并成为NASA月球任务的备选方案之—[4-7]。文献[8]最早对 $\mathrm { G M S K + P N }$ 调制方式的测距信号副载波实现形式进行了频谱分析，并给出了仿真结果。文献9研究了更具一般性的连续相位调制（con-tinuousphasemodulation，CPM)下的测距一体化设计调制解调算法。文献[10-11]给出了 $\mathrm { G M S K + P N }$ 和非平衡四相相移键 控（unbalanced quaternary phase shift keying,UQPSK)的优缺点和性能差异。文献[12-13对GMSK $+$ PN无副载波实现形式的相位抖动和同步进行了仿真。GMSK十PN调制方式从信号层面上来看是真正的测距通信一体化，它兼有GMSK和PN测距的优点[14]：旁瓣衰减快、频谱紧凑、带宽效率高、适合饱和功放；测距捕获时间短，硬件实现复杂度低，测距精度相对较高。由于采用同一个链路同时完成数传和测距两个功能，这种调制方式也有相应的缺点：解调算法相对复杂，数传信号和测距信号互为噪声，影响了解调的性能。因此，为了保证数传信号的误码率性能和测距的精度，数传信号采用相干解调的方式。信噪比估计是信道估计的一个重要组成部分，它提供了切换、功率控制和信道分配算法所需的信道质量信息。在解调过程中，许多解调和译码的算法都需要准确的信噪比信息才能达到最优的性能[15-17]。本文根据GMSK十PN信号的特点，提出了一种适用于 $\mathrm { G M S K + P N }$ 信号的信噪比估计算法。

# 1 $\mathbf { G M S K + P N }$ 调制解调技术

# 1.1 调制技术

基于 $\mathrm { G M S K + P N }$ 的调制体制、能够同时进行数传和测距的系统框图如图1所示。

![](images/6c10df5e7cae0919d39fa90247baaf0062141cfeea0b50ec5830b0a806b20ead.jpg)  
图1 GMSK+PN信号调制框图

测距符号经过电平转换和半正弦滤波后，乘以PN测距调制度(也称测距调制度)得到PN测距信号相位；数传符号经过预编码、电平转换、高斯滤波和积分器后，得到GMSK相位；PN相位和GMSK相位相加后再经过相位调制，即可得到GMSK十PN调制信号

$$
s ( t ) = \sqrt { 2 P _ { \mathrm { t o t } } } \mathrm { c o s } ( \omega _ { c } t + \varphi _ { \mathrm { G M S K } } ( t ) + m _ { d } \varphi _ { \mathrm { P N } } ( t ) )
$$

其中

$$
\varphi _ { \mathrm { P N } } ( t ) = D ( t ) \sin ( \frac { 1 } { 2 } \omega _ { \mathrm { P N } } t )
$$

式中， $\boldsymbol { P } _ { \mathrm { t o t } }$ 为信号的总功率； $\omega _ { c }$ 为载波角频率; $\varphi _ { \mathrm { G M S K } } \left( \ t \right)$ 为数传信号调制相位； $\varphi _ { \mathrm { P N } } \left( t \right)$ 为PN测距信号相位； $D ( t )$ 为PN序列；$m _ { d }$ 为PN测距调制度； $\omega _ { \mathrm { P N } }$ 为PN序列角频率。

# 1.2解调技术

因为基带的GMSK数传信号（所代表的相位)和PN测距信号(所代表的相位)在时域上是按比例相加的，所以如果得到其中的任何一种信号，就可以由复合信号与某一种“再生"的信号“相减”，得到另一种信号8。因为按照常规，GMSK信号在复合信号中所占的能量比例较大。所以，可以直接在已调载波信号上解调，得到GMSK基带信号。再由GMSK基带信号的再调制得到的相位，与输入信号进行复相关，即可得到单独的PN测距信号[18]（见图2）。

![](images/f64f99a8fabd7e549f806ce5dcf11e9497e2265cc105a3fbc57970079f0ab58f.jpg)  
图2 GMSK+PN信号解调框图

# 2 $\mathbf { G M S K + P N }$ 信号信噪比估计

# 2.1 信号简化波形

由于 $\mathrm { G M S K + P N }$ 信号既包括数传信号，又包括伪码测距信号，无法直接进行信噪比估计。而 $\mathrm { G M S K + P N }$ 信号的结构非常特殊，在数传信号的基础上，直接加入了PN测距信号（作为数传信号的相位抖动存在），故可以采用逐层简化的方式，将 $\mathrm { G M S K + P N }$ 信号分解为若干层，如图3所示。本文采取反推的方法，先估计出PN信号中 $\mathrm { ~ C 1 }$ 子码分量的信噪比，即可以通过PN信号与 $C 1$ 子码分量的功率分配，得到PN信号的信噪比。进而，通过 $\mathrm { G M S K + P N }$ 信号的能量分配，得到整个 $\mathrm { G M S K + P N }$ 信号的信噪比。

![](images/b07b1cecaba32c4d37b58b02e74f69fac8956bf6ac45671b1670590178e12a4d.jpg)  
图3信噪比估计简化模型

在图3中，第1层（最内圈)的面积代表噪声的功率$N _ { \mathrm { 0 } }$ ，第2层(最内圈和次内圈之间)的面积代表PN测距信号 $C 1$ 子码分量的功率 $P _ { \mathrm { c 1 } }$ ，第3层(次内圈和次外圈之间)的面积代表PN 测距信号 $C 2 { \sim } C 6$ 子码分量的功率 $P _ { C 2 \sim C 6 }$ ，第4层(次外层和最外层之间)的面积代表数传GMSK信号的功率 $P _ { \mathrm { G M S K } }$ 。 $P _ { \mathrm { C 1 } } / N _ { \mathrm { 0 } }$ 可以通过最常用的均值方差比可以求得；当测距PN的码型确定之后， $P _ { \mathrm { P N } } / P _ { \mathrm { C 1 } }$ 是确定的；$P _ { \mathrm { G M S K } } / P _ { \mathrm { P N } }$ 可以通过 $m _ { d }$ 来计算。简化模型如图3所示。这种新的信噪比估计算法，可以大大降低 $\mathrm { G M S K + P N }$ 信号的信噪比计算的复杂度。

# 2.2 信噪比估计

# 2.2.1数传、测距信号能量分配

由贝塞尔函数可知

$$
\sin [ m \sin ( \alpha t ) ] =
$$

$$
2 \sum _ { k \mathrm { ~ o d d } } J _ { k } \left( m \right) \sin ( k \alpha t ) \cong 2 J _ { 1 } \left( m \right) \sin ( \alpha t )
$$

$$
\cos [ m \sin ( \alpha t ) ] =
$$

$$
J _ { \scriptscriptstyle 0 } \left( m \right) + 2 \sum _ { k \mathrm { ~ e v e n } } J _ { k } \left( m \right) \cos ( k \alpha t ) \cong J _ { \scriptscriptstyle 0 } \left( m \right)
$$

式中， $J _ { \boldsymbol { k } } \left( \boldsymbol { m } \right)$ 为第一类 $k$ 阶贝塞尔函数。

GMSK十PN的调制信号表达式如式（1)所示，将式（3）、式(4)代入式(1)并将其展开

$$
s ( t ) = \sqrt { 2 P _ { \mathrm { t o t } } } J _ { \mathrm { 0 } } \left( m _ { d } \right) \sin ( \omega _ { c } t + \varphi _ { \mathrm { G M S K } } \left( t \right) ) +
$$

$$
\sqrt { 2 P _ { \mathrm { t o t } } } J _ { 1 } \left( m _ { d } \right) \sin \bigg ( \bigg ( \frac { 1 } { 2 } \omega _ { \mathrm { P N } } + \omega _ { c } \bigg ) t + \varphi _ { \mathrm { G M S K } } \left( t \right) \bigg ) +
$$

$$
\sqrt { 2 P _ { \mathrm { t o t } } } J _ { 1 } \left( m _ { d } \right) \sin \Bigl ( \Bigl ( \frac { 1 } { 2 } \omega _ { \mathrm { P N } } - \omega _ { c } \Bigr ) t - \varphi _ { \mathrm { G M S K } } \left( t \right) \Bigr )
$$

对于数传信号的解调，所用的是式(5)中等号右边的第一项；对于测距信号的解调，所用的是式（5)中等号右边的第2项和第3项。因此，令数传信号功率为 $P _ { \mathrm { G M S K } }$ . $\mathrm { P N }$ 测距信号的功率为 $P _ { \mathrm { P N } }$ ，则有

中 $\mathrm { ~ C l ~ }$ 分量成型后即为正弦波，PN信号成型后波形如图5所示。

$$
\left\{ \begin{array} { l l } { \displaystyle { \frac { P _ { \mathrm { G M S K } } } { P _ { \mathrm { t o t } } } } = J _ { \mathrm { 0 } } ^ { 2 } ( m _ { d } ) } \\ { \displaystyle { \frac { P _ { \mathrm { P N } } } { P _ { \mathrm { t o t } } } } = 2 J _ { \mathrm { 1 } } ^ { 2 } ( m _ { d } ) } \\ { \displaystyle { \frac { P _ { \mathrm { P N } } } { P _ { \mathrm { G M S K } } } } = \frac { 2 J _ { \mathrm { 1 } } ^ { 2 } ( m _ { d } ) } { J _ { \mathrm { 0 } } ^ { 2 } ( m _ { d } ) } } \end{array} \right.
$$

![](images/f401699b1d7b974d81733ffe2192118d8dd01d8ce3e878d6ee5d08705b1d3aa2.jpg)  
图5Tausworthe码成型波形

式中， $m _ { d }$ 为测距调制度，是 $\mathrm { G M S K + P N }$ 信号中GMSK信号和PN信号能量分配的唯一参数。随 $m _ { d }$ 变化， ${ \mathrm { G M S K } } +$ PN信号及其数传、测距部分能量的归一化比例的变化趋势如图4所示。

1.0FA0.90.80.7  
例 0.60.50.30.20.10 0.10.20.30.40.50.60.70.80.91.0测距调制度/rad  
-O-：GMSK功率分配；--：PN信号功率分配;  
-：总功率衰减误差; $\twoheadleftarrow$ ：GMSK/PN功率分配

当 $m _ { d }$ 为确定值时， $P _ { \mathrm { G M S K } } / P _ { \mathrm { P N } }$ 也是一个固定值。 $m _ { d }$ 的值偏低时（小于 $0 . 2 \ \mathrm { r a d } ;$ ，则测距部分能量较小，影响测距精度； $m _ { d }$ 的值偏高时（大于 $0 . 4 5 ~ \mathrm { r a d } )$ ，则数传部分能量较小,影响数传解调性能[19-20]。因此,要合理选择 $m _ { d }$ 。

由于Bessel函数存在近似，随着 $\ m _ { d }$ 的变化，GMSK信号的总功率 $\boldsymbol { P } _ { \mathrm { t o t } }$ 存在不同程度的衰减。所以在求得数传信号功率 $P _ { \mathrm { G M S K } }$ 和PN测距信号功率 $P _ { \mathrm { P N } }$ 后，需要对GMSK $+$ PN信号总功率 $\boldsymbol { P } _ { \mathrm { t o t } }$ 进行修正，如式(7)所示。

$$
P _ { \mathrm { t o t } } = { \frac { P _ { \mathrm { G M S K } } + P _ { \mathrm { P N } } } { J _ { \mathrm { 0 } } ^ { 2 } ( m _ { d } ) + 2 \bullet J _ { \mathrm { 1 } } ^ { 2 } ( m _ { d } ) } } = { \frac { J _ { \mathrm { 0 } } ^ { 2 } ( m _ { d } ) P _ { \mathrm { P N } } } { 2 \bullet J _ { \mathrm { 1 } } ^ { 2 } ( m _ { d } ) \bullet J _ { \mathrm { 0 } } ^ { 2 } ( m _ { d } ) + 1 } }
$$

# 2.2.2PN测距信号功率分配

PN测距信号经过半正弦成型后，与正弦波极其相似，其

经过整形后的PN与正弦波相比，其功率有部分衰减，如式(8)所示。

$$
1 0 1 \mathrm { g } \Big ( { \frac { P _ { \mathrm { P N } } } { P _ { \scriptscriptstyle { C 1 } } } } \Big ) = - 2 0 \mathrm { l g } ( \hat { \varsigma } _ { 1 } )
$$

式中， $\pmb { \xi } _ { 1 }$ 为Tausworthe 码中 $C 1$ 分量与复合码同相的比例，其值随码型变化。可以求得

$$
\frac { P _ { \mathrm { { P N } } } } { P _ { \mathrm { { C l } } } } = \frac { 1 } { \xi _ { 1 } ^ { 2 } }
$$

对于平衡2倍加权 Tausworthe 码（weighted-2balancedTausworthe,T2B),有

$$
1 0 1 \mathrm { g } \Big ( \frac { P _ { \mathrm { P N } } } { P _ { \mathit { c } 1 } } \Big ) \approx 4 . 0 4 9 ~ 6 ~ \mathrm { d B }
$$

对于平衡4倍加权tausworthe码（weighted-4balancedTausworthe,T4B)，有

$$
1 0 1 \mathrm { g } \Big ( \frac { P _ { \mathrm { P N } } } { P _ { \scriptscriptstyle { C 1 } } } \Big ) \approx 0 . 5 4 9 ~ 7 ~ \mathrm { d B }
$$

# 2.2.3单音信号信噪比估计

PN测距信号的 $C 1$ 分量，经过半正弦成型滤波后，即为正弦波，而对这种单载波恒包络的信号的信噪比估计可以使用最简单的均值方差比[21]求得

$$
\frac { S } { N } = 1 0 \mathrm { l g } \Big \{ \frac { \mathrm { E } \big [ a ( n ) \big ] ^ { 2 } } { \mathrm { V a r } \big [ a ( n ) \big ] } \Big \}
$$

式中， $a ( n )$ 为PN测距信号 $C 1$ 分量瞬时包络。 $\ C 1$ 分量采样模型如图6所示。其中， $t _ { s }$ 为采样间隔； $t _ { c }$ 为测距码片周期； $A$ 为实际接收信号的幅度。

![](images/424dc4e8c7b240f76a7c6077cbddc5b25947fa7d62fdcd02d121d5223bb14f41.jpg)  
图4GMSK与PN信号功率分配  
图6PN半正弦成型信号采样量化模型

令 $\boldsymbol { A ^ { \prime } }$ 为信号幅度的估计值， $x ( k )$ 为每个采样点的幅 度，则，经过采样后估计的chip幅度为

$$
A ^ { \prime } = \frac { \displaystyle \sum _ { k = 1 } ^ { n } x ( k ) \bullet t _ { s } } { t _ { s } } \bigg | _ { t _ { s } \to 0 } \approx \frac { \displaystyle \int _ { 0 } ^ { t _ { c } } x ( t ) \mathrm { d } t } { t _ { s } } = \frac { \displaystyle \int _ { 0 } ^ { t _ { c } } A \sin ( \frac { \pi t } { t _ { c } } ) \mathrm { d } t } { t _ { s } } =
$$

$$
- \frac { t _ { c } } { \pi } \bullet A \bullet \cos ( \frac { \pi t } { t _ { c } } ) \bigg | _ { 0 } ^ { t _ { c } } = \frac { 2 t _ { c } A } { \pi t _ { s } }
$$

信号功率的估计值 $S ^ { ' }$ 为

$$
S ^ { ' } = \frac { 1 } { 2 } \bullet \colon ( \frac { \pi t _ { s } A ^ { ' } } { 2 t _ { c } } ) ^ { 2 } = \frac { 1 } { 2 } \bullet ( \frac { \pi t _ { s } } { 2 t _ { c } } ) ^ { 2 } \bullet E ^ { 2 } ( A ^ { ' } )
$$

噪声功率估计值 $N ^ { \prime }$ 为

$$
N ^ { \prime } = \frac { t _ { s } } { t _ { c } } \mathrm { V a r } ( A ^ { \prime } )
$$

式中， $C 1$ 分量理论信噪比值为 ，其信噪比估计值 $\frac { P _ { \mathrm { { C l } } } } { N _ { \mathrm { { 0 } } } }$ 为

$$
\begin{array} { r } { \frac { P _ { \mathrm { c 1 } } } { N _ { \mathrm { 0 } } } = \frac { E _ { s } ^ { \prime } } { N _ { \mathrm { 0 } } ^ { \prime } } = \frac { 1 } { 8 } \bullet \frac { \pi ^ { 2 } t _ { s } } { t _ { c } } \bullet \frac { E ^ { 2 } ( A ^ { \prime } ) } { \mathrm { V a r } ( A ^ { \prime } ) } \bullet \frac { f _ { s } } { 2 f _ { c } } } \end{array}
$$

由第2.2.1节、第2.2.2节和第2.2.3节的结论，可以得到 $\mathrm { G M S K + P N }$ 信号总功率与噪声功率之比为

$$
\frac { P _ { \mathrm { t o t } } } { N _ { \mathrm { 0 } } } = \frac { J _ { \mathrm { 0 } } ^ { 2 } ( m _ { d } ) } { 2 J _ { \mathrm { 0 } } ^ { 2 } ( m _ { d } ) J _ { \mathrm { 1 } } ^ { 2 } ( m _ { d } ) + 1 } .
$$

$$
\frac { 1 } { \hat { \varsigma } _ { 1 } ^ { 2 } } \bullet \frac { 1 } { 8 } \bullet \frac { \pi ^ { 2 } t _ { s } } { t _ { c } } \bullet \frac { \mathrm { E } ^ { 2 } ( A ^ { \prime } ) } { \mathrm { V a r } ( A ^ { \prime } ) } \bullet \frac { f _ { s } } { 2 f _ { c } }
$$

# 3 结果分析

通过Simulink搭建仿真模型，取采样率为 $f _ { s } = 1 0 0 ~ \mathrm { M H z }$ PN速率为 $f _ { c } { = } 2 ~ \mathrm { M H z }$ ，测距调制度 $m _ { d } = 0 . 2 \ \mathrm { r a d }$ ，再生PN采用T4B，测得信噪比估计值如图7所示。

14 =-- 二 1 1 □ 12.0 =-- ---- --- --- F---- --- _-- 1=1  
12 __= 11.5 1 = -L = = 1 1 - - = 1- = ---- 1 = 二 = 一 二 = = 1 =1 □ ！ = 1 __== = __-= _--- ！  
10 中 P/ --- ---↓ --- ---1-_= = = -- 11.0 1 二 = 1 = = +-- 1 ---- = +---- 二 = / ---- = 1 t-□ 1 1 1 ---- __--  
P/ 1 1 = 1 =-8 店 = 二 == 1 □ = = 10.5 L = J = 1= 1 一 = 1 = 二 ⊥ = --6 AM = 1 1 _-== --- -= _=== == ！M = == --- _ 14 国 1 A == + = + = 1 + == 10.0 wm = = = _== 冷 = M = 一 T==== T 1 = 一1 _==- _== = / 二 = --- ---+ __- ---全 =9.5 = =2 中 = = 1 = T = 1 = = + † - == = = = = + = = =二 --- --- F---- - = 一 ---- ---- _--- -----? --- - --- _-- _-- --- ---0L 9.00 2 4 6 8 10 12 14 0 2000 40006000 8000 10 000信噪比实际值/dB 估计点数/个：实际值；--：估计值。(a)信噪比实际值与估计值关系 (b)信噪比估计值与估计码片数关系

图7 仿真结果

经过仿真可以发现，信噪比估计值与实际值非常吻合，误差在0.5dB以下。参与计算的码片数在大于1000时，信噪比估计值基本稳定实际值附近。

# 4结论

本文给出了在加性高斯白噪声信道中基带GMSK $+$ PN信号的信号模型，同时给出了在此模型下的简单、快捷的信噪比算法。并通过Simulink对该算法进行了仿真。该算法精确度较高，计算复杂度低，且参与计算的码片数目较少，具有工程的可实现性。

# 参考文献：

[1]CCSDS Recommended Standard 413.0-G-2.Bandwidth-efficient modulations：summary of definition，implementation，and performance [S].Washington，DC：Consultative Committee for Space Data Systems，2009.   
[2]CCSDS Recommended Standard 414.0-G-2. Pseudo-noise（PN) ranging systems[S].Washington,DC:Consultative Committee for Space Data Systems,2014.   
[3]Vassallo E，Visintin M. Analysis of GMSK for simultaneous transmission of ranging and telemetry[C]//Proc.of the CCSDS FallTechnical Meeting，2009：SLS-RFM_09-08.   
[4]Stocklin F,Israel D,DeutschL，et al. Evaluation of multiple access techniques for simultaneous space communications and tracking[C]// Proc.ofthe IEEEAerospace Conference,2oo8:1-30.   
[5]Deutsch L，Stocklin F，Rush J. Modulation and coding for NASA's new space communications architecture[C]//Proc.of the AIAA International Conference on Space Operations，2oo8：1-8.   
[6]Deutsch L，Noreen G K，Hamkins J，et al. Selecting codes, modulations，multiple access schemes and link protocols for future NASA missions[C]//Proc.ofthe IEEEAerospace Con ference，2008：1-9.   
[7]Deutsch L，Hamkins J，Stocklin F. Multiple access schemes for lunarmissions[C]//Proc.of the AIAA International Con ference on Space Operations，20lo：1-8.   
[8]Orr R S，Divsalar D.Combined GMSK modulation and PN ranging for communication and navigation[C]//Proc.of the IEEE Aerospace Conference，20o8：1-18.   
[9]Orr R S，Divsalar D. CPM/PN modulation and ranging for bandwidth-limited multiple access links[C]//Proc.of the IEEE Aerospace Conference，20ll：1-27.   
[10]Vassallo E，Visintin M. Analysis of UQPSK and GMSK/PN for simultaneous transmission of ranging and telemetry：ranging correlator results[C]//Proc.of the CCSDS Spring Technical Meeting, 2010：SLS-RFM_10-03.   
[11]Dennis L. Simulations of GMSK-PN and UQPSK[C]//Proc.of the CCSDSSpring Technical Meeting,2011:SLS-RFM_11-04.   
[12]Sessler G，Vassallo E. Analysis of GMSK/PN modulation: effects of phase jumps and noise[C]//Proc.of the CCSDS Fall Management Meeting，2011：SLS-RFM_11-16.   
[13]Vassallo E，Visintin M.Synchronization analysis for GMSK $+$ PN modulation[C]// Proc.of the CCSDS Spring Technical Meeting，2011：SLS-RFM_11-01.   
[14]Visintin M，Vassallo E.Synchronization analysis for GMSK $^ +$ PN modulation[C]//Proc.of the CCSDSFall Technical Meeting，2013：SLS-FRM_13-12.   
[15]Salman T，Badawy A，Elfouly TM，et al.Non-data-aided SNR estimation for QPSK modulation in AWGN channel[C]// Proc.of the IEEEWireless and Mobile Computing，Networking and Communications(WiMob)，20l4：611-616.   
[16]BelliliF，Methenni A，Affes S.Closed-form CRLBs for SNR estimation from turbo-coded BPSK，MSK-，and square-QAMmodulated signals[J]．  IEEE Trans.on Signal Processing, 2014，62(15):4018-4033.   
[17]He P,Li Z，Wang X.A low-complexity SNR estimation algorithm and channel estimation method for OFDM systems[C]// Proc.oftheInternational ConferenceonIEEEInformation Science and Technology，2014：698-701.   
[18] Shi L，Wang Z，Xiong W.Combined GMSK modulation and PN ranging for satellite telemetry[C]//Proc.of the 27th Conference of Spacecraft TT&C Technology，2014(A-070)：1- 10.（石立国，王竹刚，熊蔚明.基于 $\mathrm { G M S K + P N }$ 体制的遥测与 测距技术[C]//中国宇航协会飞行器测控专业委员会第27届 飞行器测控学术年会论文集，2014（A-070)：1-10.）   
[19] CCSDS Recommended Standard 41x. O-G-0. Simultaneous transmission of GMSK telemetry and PNranging[S].Washington,DC：Consultative Committee for Space Data Systems,2014.   
[20]SesslerG，Vassallo E，CalzolariG P，et al.GMSK/PN for high rate telemetry and high accuracy ranging of lagrange and marsmissions[C]//Proc.of the AIAA International Con ference on Space Operations,20l4:1-14.   
[21]Fan HB，ChenJ，Cao ZG.An algorithm of SNR estimation for non-constant envelope signal in the AWGN channel[J].Acta ElectronicSinica，2002，30(9)：1369-1371.（范海波，陈军，曹志刚. AWGN信道中非恒包络信号的SNR估计方法［J].电子学报， 2002，30(9):1369-1371.)

# 作者简介：

石立国(1984-)，男，博士研究生，主要研究方向为数字信号处理、信号检测与估计。  
E-mail:shiliguo@ nssc.ac.cn  
王竹刚(1974-)，男，研究员，硕士研究生导师，主要研究方向为射频微波通信、数字信号处理。  
E-mail:wangzg@ nssc.ac.cn  
熊蔚明(1963-)，男，研究员，博士研究生导师，主要研究方向为电子、通信、计算机、控制和信号处理相关跨学科研究。  
E-mail:xwm@nssc.ac.cn