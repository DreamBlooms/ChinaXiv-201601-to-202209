# 空间通信中GMSK信号的载波恢复与时钟同步‘

唐智灵，邹鑫，李思敏

(桂林电子科技大学 广西无线宽带通信和信号处理重点实验室，广西 桂林 541004)

摘要：在空间通信中，过大的多普勒频移和多普勒变化率会造成相干解调接收机无法进行载波恢复与时钟同步。为此，针对高斯最小频移键控（GMSK）信号提出一种可靠且快速克服大多普勒频移的改进平方环方法。首先通过频率估计模块获取粗略载波频率，其次应用改进平方环结构实现GMSK信号的载波恢复和时钟同步。仿真结果显示在输入信噪比 $ { E _ { b } } /  { N _ { 0 } } { = } 5$ dB以及环路噪声带宽为 $5 0 \mathrm { k H z }$ 的条件下,载波恢复环路与时钟同步环路锁定时间约为 $3 . 6 ~ \mathrm { m s }$ 。在低信噪比及大多普勒频移的条件下，该方法能够快速且稳定地实现GMSK信号在空间通信中的载波恢复与时钟同步。

关键词：空间通信；GMSK；多普勒频移；多普勒变化率；平方环 中图分类号：TN911.7 doi:10.19734/j.issn.1001-3695.2018.11.0841

Carrier recovery and clock synchronization of gmsk signals in space communications

Tang Zhiling, Zou Xin, Li Simin† (Guangxi KeyLaboratoryof Wireless Broadband Communication& Signal Processing,Guilin Universityof Electronic Technology,Guilin Guangxi 541004,China)

Abstract:Due to excessive Dopper shiftsand Doplerrate in space communications,the coherent demodulationreceiver failstoperform carierrecoveryand clock synchronization.To thisend,this paper proposedan improvedsquare-loop method to overcome the large Doppler shifts reliablyand quickly for the Gaussan Minimum Shift Keying(GMSK) signal. This methodcould obtain thecoarse carrier estimation bythe frequency estimation module,and then thecarier recovery and clock synchronization were realized by the improved square-loop.With loop noise bandwidth of $5 0 ~ \mathrm { k H z }$ and $ { E _ { b } } /  { N _ { 0 } } { = } 5$ （204号 dB,the simulation showed that the locked time of carrier-recovery loop and clock-synchronization loop was about $3 . 6 ~ \mathrm { m s }$ In space communications，the method is proved can implement carrier recovery and clock synchronization of GMSK signals quickly and stably under the conditions of low SNR and large Doppler shifts.

Key words: space communications; gmsk; doppler shifts; doppler rate; square-loop

# 0 引言

由于深空通信任务中X波段频谱分配的稀缺性，深空通信任务开始转向Ka波段进行数据通信。但是，在深空通信任务中依然需要具备X 波段通信系统，用作应急通信[1.2]。针对频谱资源有限，数据传输速率高，传输距离远等问题，高斯最小频移键控（Gaussian minimum shift keying,GMSK)调制体制以其恒包络，频谱利用率高的特点被国际空间数据系统咨询委员会（Consultative Committee for Space DataSystems，CCSDS）列为深空通信调制方式之一[3\~5]。在2008年，欧洲航天局（European Space Agency，ESA）将GMSK调制体制首次应用于HerschelPlanck卫星测试任务中[6]。

GMSK信号的解调方式包括非相干解调与相干解调，传统的GMSK解调多采用非相干解调，优点是接收机设计复杂度小，但是解调性能比相干解调有一定的恶化。在特定领域如空间通信方面，由于非相干解调存在解调门限的限制，只能通过相干解调方式接收GMSK信号。

在GMSK相干解调接收机中，通常采用锁相环结构实现相干载波的提取，其中平方环和科斯塔斯环是在载波恢复过程中应用最为广泛的两种环路。在环路设计中环路捕获带宽和环路锁定精度是相互矛盾的。尤其在空间通信中，接收信号中往往存在较大的多普勒频移和多普勒变化率，如火星探测任务中多普勒频移最大可以达到 $9 0  { \mathrm { k H z } }$ 左右，多普勒变化率最大达到 $1 0 0 0 ~ \mathrm { H z / s ^ { [ 7 ] } }$ 。如果想要提高捕获范围大小，就意味着增加环路噪声带宽，在低信噪比下，增加环路噪声带宽，会造成锁定精度下降。因此，在实际应用中需要寻找折中的办法来达到工程所需求的性能。与此同时自动频率控制环路，同样可以完成某些调制信号的载波恢复和频偏估计[8.9]，通常应用突发通信，载波恢复速度很快，在信噪比低的情况下时往往锁定精度达不到要求。

在实现载波恢复与频偏估计的工程应用中，文献[10，11]中提出使用通用数字环路对GMSK调制信号进行载波恢复，但是由于鉴相器具有正弦鉴相特性，在较大误差信号下，鉴相曲线并非呈现线性特性。文献[12]中提出基于FPGA线性鉴相全数字锁相环，采用数字计算机算法(coordinaterotationdigitalcomputer,CORDIC)实现线性鉴相范围的扩展。而针对空间通信中出现的大多普勒频移；文献[13]提出一种基于FFT 算法的快速且精准的载波恢复方法，结构简单，估计精度高，通过频率估计加快锁相环锁定；文献[14,15]提出了针对QPSK调制信号的最大似然频偏估计方法，FPGA设计较为复杂，但是估计精度高；文献[16]提出在FFT频偏估计上进行优化算法实现精度提升，实际工程应用较难。

为了在大多普勒频移与低信噪比条件下实现GMSK信号的载波恢复与时钟同步，本文结合前人的工作，提出将平方环与自动频率控制环路相结合的改进平方环方法。运用基于CORDIC算法的FPGA实现完成平方环的线性鉴相。为了实现简易而精准的频偏估计，采用基于FFT算法的自动控制环路的设计，辅助平方环进行载波恢复。为空间通信中GMSK信号载波恢复与时钟同步的FPGA实现，提出一种可行的办法。

# 1 问题分析

空间飞行器，包括人造卫星、载人飞船、航天飞机等，在轨运行时都具有很快的运动速度。因此，地面接收的信号中必然会存在着多普勒现象。多普勒现象包括多普勒频移以及多普勒变化率[17]，两者的数值变化大小，对于锁相环参数设计及其重要。

如图1所示，以近地轨道为模板，假设空间飞行器绕地球进行近似圆周运动且地面接收机与飞行器轨道处于同一平面。根据飞行器运动轨迹图分析地面接收机与空间飞行器通信中存在的多普勒现象。

![](images/b0994b5b0862142a89efba3cc17d9148e21785ca318f7b3658ab20c4be7ca0fd.jpg)  
图1飞行器运动轨迹平面图

以地心O为原点建立坐标系，其中R点为地面接收机位置，S点为空间飞行器当前位置，地球半径为 $r _ { e }$ ，轨道高度为 $h$ ，S点处的线速度为 $\nu _ { s }$ ，假设飞行器从B点运行到S点处，转动角度为 $\theta$ 。 $\alpha$ 是RS与OS的夹角。由牛顿万有引力公式可得

$$
\left\{ \begin{array} { c } { \omega = \displaystyle \frac { \mathrm { d } \theta } { \mathrm { d } t } = \sqrt { \frac { G M } { \left( r _ { e } + h \right) ^ { 3 } } } } \\ { \nu _ { s } = \omega r _ { o } } \end{array} \right.
$$

其中： $r _ { o } = r _ { e } + h$ 为飞行器轨道半径， $\omega$ 是飞行器的角速度， $G$ 是万有引力常量， $M$ 为中心星体的质量，此处是地球的质量。

根据多普勒频移计算公式求得多普勒频移 $f _ { d }$ 为

$$
f _ { d } = \nu _ { d } \frac { f _ { t } } { c }
$$

其中： $\nu _ { d }$ 为飞行器线速度 $\nu _ { s }$ 在向量RS的速度分量， $f _ { t }$ 为无线电信号传输频率， $\boldsymbol { c }$ 为光传播速率。

由速度分解法可得

$$
\nu _ { d } = \left\{ \begin{array} { c c } { { - \nu _ { s } \sin \alpha } } & { { 0 ^ { \circ } \leq \theta \leq 9 0 ^ { \circ } } } \\ { { \nu _ { s } \sin \alpha } } & { { 9 0 ^ { \circ } \leq \theta \leq 1 8 0 ^ { \circ } } } \end{array} \right.
$$

同时根据三角函数定理可得

$$
\sin \alpha = \frac { l _ { R R ^ { \prime } } } { l _ { R S } }
$$

$$
= \left\{ \begin{array} { l l } { \displaystyle { \frac { r _ { e } \cos \theta } { \sqrt { { r _ { e } } ^ { 2 } + { r _ { o } } ^ { 2 } - 2 r _ { e } r _ { o } \sin \theta } } } } & { 0 ^ { \circ } \leq \theta \leq 9 0 ^ { \circ } } \\ { \displaystyle { \frac { - r _ { e } \cos \theta } { \sqrt { { r _ { e } } ^ { 2 } + { r _ { o } } ^ { 2 } - 2 r _ { e } r _ { o } \sin \theta } } } 9 0 ^ { \circ } \leq \theta \leq 1 8 0 ^ { \circ } } \end{array} \right.
$$

将式(3)(4)代入式(2)中可以得到

$$
f _ { d } = \frac { - \nu _ { s } r _ { e } \cos \theta } { \sqrt { { r _ { e } } ^ { 2 } + { r _ { o } } ^ { 2 } - 2 { r _ { e } } { r _ { o } } \sin \theta } } \frac { f _ { t } } { c }
$$

其中 $0 ^ { \circ } \le \theta \le 1 8 0 ^ { \circ }$ 。

多普勒变化率 $a _ { d }$ 为多普勒频移 $f _ { d }$ 在单位时间 $t$ 内的变化值，多普勒频移 $f _ { d }$ 对时间 $t$ 进行求导可以得到多普勒变化率公式为

$$
a _ { d } = { \frac { \mathrm { d } f _ { d } } { \mathrm { d } t } }
$$

$$
= \frac { - \nu _ { s } r _ { e } \left( r _ { e } r _ { o } \sin ^ { 2 } \theta - \left( r _ { e } ^ { 2 } + r _ { o } ^ { 2 } \right) \sin \theta + r _ { e } r _ { o } \right) } { \sqrt { \left( r _ { e } ^ { 2 } + r _ { o } ^ { 2 } - 2 r _ { e } r _ { o } \sin \theta \right) ^ { 3 } } } \frac { f _ { t } } { c } \omega
$$

其中 $0 ^ { \circ } \le \theta \le 1 8 0 ^ { \circ }$ 0

如图1所示，当飞行器处于弧线 $S ^ { \prime } S ^ { \prime \prime }$ 范围内才可以进行 正常的信号发送与接收。即

$$
\left\{ \begin{array} { l l } { \beta = a r c \sin \left( r _ { e } / r _ { o } \right) } \\ { \beta \le \theta \le 1 8 0 ^ { \circ } - \beta } \end{array} \right.
$$

基于以上公式的推导，X波段无线电信号传输频率 $f _ { t }$ 为$8 . 4 \ : \mathrm { G H z }$ ，通过改变飞行器的高度，对多普勒现象的特性进行分析。

如图2所示，飞行器高度越低，多普勒频移最大值越大。高度为 $5 0 0 \mathrm { K M }$ 时，多普勒频移最大值可达到 $2 0 0  { \mathrm { k H z } }$ 左右，在 $\scriptstyle \theta = 9 0 ^ { \circ }$ 时多普勒频移达到最小值 $0 \ : \mathrm { H z }$ 。

![](images/edaae687ffa298abf83d4e99358cce4df4d0f8479e6c158d21cc41df8393043e.jpg)  
图2接收信号中的多普勒频移  
Fig.2Doppler shifts of receive signals

如图3所示，飞行器高度越低，变化率最大值也越大。高度为 $5 0 0 ~ \mathrm { K M }$ 多普勒变化率最大值可达 $3 ~ \mathrm { k H z }$ 左右，且在$\scriptstyle \theta = 9 0 ^ { \circ }$ 时多普勒变化率取得最大值。

![](images/3012c551614064e50f0723331df57940868e2b858b937f6d7b33ac09214b585f.jpg)  
Fig.1Aircraft motion trajectory plan   
图3接收信号中的多普勒变化率 Fig.3Doppler rate of receive signals

# 2 GMSK载波恢复与时钟同步方法

GMSK信号是将码元信号预先经过一个窄带高斯滤波器，然后再进行MSK调制，它同样可以解释为一种调制指数为0.5的连续相位的频移调制（CPFSK）[18]。鉴于在无线通信中采用的是抑制载波调制方式，虽然接收信号本身没有载波的频率分量，但是信号含有载频信息，只要经过非线性变换即可产生载波的倍频分量。

# 2.1 GMSK信号分析

根据MSK调制的特点，每个码元周期相位变化为$\pm \pi \mathrm { t } / 2 T _ { b }$ （ $T _ { b }$ 是码元周期)，那么GMSK信号中每个码元周期的频率变化范围为

$$
\left\{ \begin{array} { l l } { f _ { L } = f _ { c } - 1 / 4 T _ { b } } \\ { f _ { H } = f _ { c } + 1 / 4 T _ { b } } \end{array} \right.
$$

其中 $f _ { c }$ 为载波频率。

假设输入信号为

$$
\mathbf { \boldsymbol { x } } \left( \mathbf { \boldsymbol { t } } \right) = \mathbf { \boldsymbol { s } } \left( \mathbf { \boldsymbol { t } } \right) + \mathbf { \boldsymbol { n } } \left( \mathbf { \boldsymbol { t } } \right)
$$

$$
= m ( t ) \mathrm { s i n } \biggl [ \omega _ { c } t \pm \frac { \pi t } { 2 T _ { b } } \biggr ] + n ( t )
$$

其中： $m ( t )$ 是信号幅度失真， $n \left( t \right) = n _ { c } \left( t \right) + j n _ { s } \left( t \right)$ ， $n _ { c } \left( t \right)$ 与 $n _ { s } \left( t \right)$ 是完全独立的高斯白噪声， $\omega _ { c }$ 为载波角频率。

GMSK信号平方后经带通滤波器得

$$
\mathbf { y } ( \mathbf { t } ) = \left\{ - \frac { 1 } { 2 } m ( t ) + n _ { s } \left( t \right) m ( t ) - \frac { 1 } { 2 } n _ { s } ^ { 2 } \left( t \right) + \frac { 1 } { 2 } n _ { c } ^ { 2 } \left( t \right) \right\} \times
$$

$$
\cos [ 2 \omega _ { c } t + 2 \theta _ { 0 } \left( t \right) ] +
$$

$$
\left[ m ( t ) - n _ { s } \left( t \right) \right] n _ { c } \left( t \right) \sin \left[ 2 \omega _ { c } t + 2 \theta _ { 0 } \left( t \right) \right]
$$

其中： $\theta _ { 0 } ( t ) = \pm \pi t / 2 T _ { b }$ 。

由式(10)知平方后信号存在离散频率 $2 f _ { H }$ 和 $2 f _ { L }$ ，GMSK信号平方频谱如图4所示。

![](images/3190192f99c47e96524de5b8444e8bdcf473a1c6509dffd94ce893d2d5daad9e.jpg)  
图4GMSK信号平方频谱Fig.4Spectrum of GMSK signal square

载波频率与离散频率之间的关系为

$$
\left\{ { { f _ { c } = \frac { { { f _ { H } } + { f _ { L } } } } { 2 } } \atop { { f _ { b } } = 2 { f _ { H } } - 2 { f _ { L } } } } \right.
$$

获取 $2 f _ { H }$ 和 $2 f _ { L }$ 两个离散频率信号，混频后经低通滤波就可以得到时钟频率为 $f _ { b }$ 信号，经脉冲形成后，即可提取时钟信号。

# 2.2改进平方环分析与设计

数字平方环是数字锁相环的一种，包括鉴相器、环路滤波器和数字控制振荡（NCO)。平方环的设计需要分析数字锁相环和模拟锁相环来确定环路参数，文献[19]对基于二阶模拟锁相环的数字锁相环设计作了详细的分析。本文提出的改进平方环结构如图5所示。

![](images/def217c5704160013d564b86ad4fd844e3b0fcd7829bdc153a1f75509d58098e.jpg)  
图5改进平方环结构图

2.2.1全数字锁相环模型分析

图6是二阶模拟锁相环相位模型图，鉴相器鉴相增益为$K _ { d }$ ，环路滤波器S域传递函数为 $F \left( s \right)$ ，压控振荡器S域传递函数为 $V ( s )$ ，鉴相器输出误差电压 $V _ { d } \left( s \right)$ ，经环路滤波器滤波得控制电压 $V _ { c } \left( s \right)$ ，控制输出相位 $\theta _ { 2 } ( s )$ 靠拢输入相位 $\theta _ { 1 } ( s )$ 。模拟锁相环相位模型在线性鉴相区间的S域变换公式为

$$
F ( s ) = { \frac { V _ { c } \left( s \right) } { V _ { d } \left( s \right) } } = { \frac { 1 } { s } } { \frac { \tau _ { 2 } s + 1 } { \tau _ { 1 } } }
$$

$$
V \left( s \right) = \frac { \theta _ { o } \left( s \right) } { V _ { c } \left( s \right) } = \frac { K _ { o } } { s }
$$

$$
\begin{array} { c } { { { \displaystyle H ( s ) = \frac { \theta _ { 2 } \left( s \right) } { \theta _ { 1 } \left( s \right) } = \frac { K _ { d } { \cal F } ( s ) { \cal V } ( s ) } { 1 + K _ { d } { \cal F } ( s ) { \cal V } ( s ) } } } } \\ { { { } } } \\ { { { \displaystyle ~ = \frac { 2 \xi \omega _ { n } s + \omega _ { n } ^ { 2 } } { s ^ { 2 } + 2 \xi \omega _ { n } s + \omega _ { n } ^ { 2 } } } } } \end{array}
$$

其中： $K _ { o }$ 为压控振荡器(VCO)增益， $\tau _ { \mathfrak { l } }$ 和 $\tau _ { 2 }$ 是时间常数，$\omega _ { n } = \sqrt { K _ { d } K _ { o } / \tau _ { \mathrm { l } } }$ 为环路自然角频率， $\xi = \tau _ { 2 } \omega _ { n } / 2$ 为阻尼因子。$H ( s )$ 为模拟锁相环在S域的传递函数。

![](images/71872aa51687a4aac9d7d45de8ff64d99dc4bb0f91a50f345497e74c9c0ffba0.jpg)  
Fig.5Modified square loop structure diagram   
图6二阶模拟锁相环相位模型  
Fig.6Second-order analog phase-locked loop phase model

为了对模拟锁相环数字化，可以通过双线性变换方法[20]实现模拟系统与数字系统之间的转换。变换公式为

$$
\left\{ \begin{array} { l l } { \displaystyle s = \frac { 2 } { T _ { s } } \frac { 1 - z ^ { - 1 } } { 1 + z ^ { - 1 } } } \\ { \displaystyle z = \frac { 1 + \frac { T _ { s } } { 2 } s } { 1 - \frac { T _ { s } } { 2 } s } } \end{array} \right.
$$

其中 $T _ { s }$ 是数字采样周期。

将式(15)分别代入式(12)(13)得

$$
F ( z ) = C _ { 1 } + C _ { 2 } { \frac { 1 } { 1 - z ^ { - 1 } } }
$$

$$
N ( z ) = \frac { K _ { o } z ^ { - 1 } } { 1 - z ^ { - 1 } }
$$

其中： $C _ { 1 } = \big ( 2 \tau _ { 2 } + T \big ) / 2 \tau _ { 1 }$ ， $C _ { 2 } = T _ { s } / \tau _ { 1 }$ 。

数字锁相环的相位模型如图7所示。则数字锁相环 $\textbf { z }$ 域传递函数可以表示为

$$
H \left( z \right) = \frac { \theta _ { 2 } \left( z \right) } { \theta _ { 1 } \left( z \right) }
$$

$$
= \frac { K C _ { 1 } z ^ { - 1 } + \left( K C _ { 2 } - K C _ { 1 } \right) z ^ { - 2 } } { 1 + \left( K C _ { 1 } - 2 \right) z ^ { - 1 } + \left( K C _ { 2 } - K C _ { 1 } + 1 \right) z ^ { - 2 } }
$$

其中 $K = K _ { d } K _ { o }$ ，为数字环路总增益。

![](images/340f59996e95917ea845c199f13a42541f34e5ac09dbe424a03e55ba8b6440fa.jpg)  
Fig.7Second-order digital phase-locked loop phase model

式(18)是根据数字锁相环相位模型推导出来的 $\textbf { z }$ 域系统传递函数，另外还可以将模拟锁相环系统传递函数，采用双线性变换方法变换成数字域的系统函数，将式(15)代入式(14)可以得到

$$
\begin{array} { c } { { H ( z ) = ( [ 4 \xi \omega _ { n } T _ { s } + 2 ( \omega _ { n } T _ { s } ) ^ { 2 } ] + 2 ( \omega _ { n } T _ { s } ) ^ { 2 } z ^ { - 1 } +  } } \\ { {  } } \\ { {  2 ( \omega _ { n } T _ { s } ) ^ { 2 } z ^ { - 1 } + { [ ( \omega _ { n } T _ { s } ) ^ { 2 } - 4 \xi \omega _ { n } T _ { s } ] z ^ { - 2 } } ) \times } } \\ { {  } } \\ { {  [ ( \omega _ { n } T _ { s } ) ^ { 2 } - 4 \xi \omega _ { n } T _ { s } ] z ^ { - 2 } ) \times ( [ 4 + 4 \xi \omega _ { n } T _ { s } + ( \omega _ { n } T _ { s } ) ^ { 2 } ] +  } } \\ { {  [ 2 ( \omega _ { n } T _ { s } ) ^ { 2 } - 8 ] z ^ { - 1 } + [ 4 - 4 \xi \omega _ { n } T _ { s } + ( \omega _ { n } T _ { s } ) ^ { 2 } ] z ^ { - 2 } ) ^ { - 1 } } } \end{array}
$$

通过比较式(18)和(19)可以得出

$$
\begin{array} { r } { \left\{ \begin{array} { c } { C _ { 1 } = \displaystyle \frac { 4 \left( \omega _ { n } T _ { s } \right) ^ { 2 } + 8 \xi \omega _ { n } T _ { s } } { 4 + 4 \xi \omega _ { n } T _ { s } + \left( \omega _ { n } T _ { s } \right) ^ { 2 } } \frac { 1 } { K } } \\ { C _ { 2 } = \displaystyle \frac { 4 \left( \omega _ { n } T _ { s } \right) ^ { 2 } } { 4 + 4 \xi \omega _ { n } T _ { s } + \left( \omega _ { n } T _ { s } \right) ^ { 2 } } \frac { 1 } { K } } \end{array} \right. } \end{array}
$$

2.2.2改进平方环参数计算

由式(18)(20)可知，数字锁相环系统传递函数中，需要计算鉴相增益 $K _ { d }$ 、数字控制振荡器增益 $K _ { o }$ 、环路总增益 $K$ ，阻尼系数 $\xi$ 、环路自然角频率 $\omega _ { n }$ 、二阶环路滤波器积分系数$C _ { 1 }$ 与比例系数 $C _ { 2 }$ 。

首先，文献[21]中提出当阻尼系数 $\xi = 0 . 7 0 7$ 以及 $\omega _ { n } T _ { s } \ll 1$ 时，工程应用效果最好。 $T _ { s }$ 为采样周期。

1)环路自然角频率 ${ \boldsymbol { \omega } } _ { n }$

数字锁相环捕获过程包括频率捕获与相位捕获，改进平方环采用自动控制环路对大频偏进行估计，所以这里讨论相位捕获，快捕带被称为保证环路只有相位捕获过程的最大固有频率值。故快捕带为

$$
\Delta \omega _ { L } = 2 \xi \omega _ { n }
$$

为满足环路稳定环路自然角频率 $\omega _ { n }$ 必须满足

$$
\omega _ { n } \geq \frac { \Delta \omega _ { L } } { 2 \xi }
$$

针对频率斜升信号，频率变化率为 $R$ 时，二阶锁相环路维持环路稳定， $\omega _ { n }$ 满足公式：

$$
\omega _ { n } \geq { \sqrt { R } }
$$

同时，还要从环路噪声性能上对 $\omega _ { n }$ 的进行分析，在空间通信中接收信号存在高斯白噪声的影响，可以得到在输入信号中存在高斯白噪声条件下相位方差 $\sigma ^ { 2 }$ 可以表示为

$$
\sigma ^ { 2 } = \left( \frac { S } { N } \right) _ { i } ^ { - 1 } \frac { B _ { L } } { B _ { i } }
$$

其中: $\left( S \nearrow \ N \right) _ { i }$ 为输入信噪比， $B _ { i }$ 为输入信号带宽， $B _ { \iota }$ 为环路噪声带宽。

环路噪声带宽越小，相位方差 $\sigma ^ { 2 }$ 也就越小，稳态波动也就越小，对于理想二阶环路滤波器环路噪声带宽 $B _ { \iota }$ 可以表示为

$$
B _ { L } = \frac { \omega _ { n } } { 8 \xi } \big ( 1 + 4 \xi ^ { 2 } \big )
$$

环路信噪比 $\left( S / N \right) _ { L }$ 其定义为环路输入信号功率与单边带 $B _ { \iota }$ 的噪声功率之比，表示环路对噪声抑制能力，通常当$\left( S / N \right) _ { L }  \geq 6 \mathrm { d } \mathbf { B }$ 时环路才可以正常锁定， $\left( S / N \right) _ { L }$ 可以表示为

$$
\left( \frac { S } { N } \right) _ { L } = \left( \frac { S } { N } \right) _ { i } \frac { B _ { i } } { B _ { L } }
$$

则由以上分析可以得到

$$
\omega _ { n } \leq \left( \frac { S } { N } \right) _ { i } \frac { 4 \xi B _ { i } } { 3 ( 1 + 4 \xi ^ { 2 } ) }
$$

根据式(22)(23)和(27)可以确定环路自然角频率 $\omega _ { n }$ 的范围为

$$
\left\{ \begin{array} { c } { \displaystyle { \frac { \Delta \omega _ { L } } { 2 \xi } \leq \omega _ { n } \leq \left( \frac { S } { N } \right) _ { i } \frac { 4 \xi B _ { i } } { 3 \left( 1 + 4 \xi ^ { 2 } \right) } } } \\ { \omega _ { n } T _ { s } \ll 1 } \\ { \omega _ { n } \geq \sqrt { R } } \end{array} \right.
$$

2)鉴相增益 $K _ { d }$

鉴相器是一个相位比较装置，用来检测输入相位信号与反馈信号之间的相位差，反正切鉴相器工作原理如图8所示。

![](images/1f3ad7646dff20dfb37bbcf90e6258cd181a4d259702ef7a08d64e316ab44daf.jpg)  
图7二阶数字锁相环相位模型  
图8反正切鉴相原理图  
Fig.8Arctangent Phase discrimination schematic

假设鉴相器输入信号为

$$
u _ { i } \left( t \right) = U _ { i } \cos \left( \omega _ { 1 } t + \theta _ { 1 } \left( t \right) \right)
$$

其中: $\omega _ { \mathrm { i } }$ 为输入信号角频率， $\theta _ { \mathrm { 1 } } ( t )$ 为输入信号初始相位。

数字控制振荡器输出本振信号可以表示为

$$
\begin{array} { r } { \{ u _ { o I } ( t ) = U _ { o } \cos ( \omega _ { 2 } t + \theta _ { 2 } ( t ) ) } \\ { u _ { o Q } ( t ) = U _ { o } \sin ( \omega _ { 2 } t + \theta _ { 2 } ( t ) ) } \end{array}
$$

其中: $\omega _ { 2 }$ 为本振信号角频率， $\theta _ { 2 } ( t )$ 为本振信号初始相位，环路锁定时 $\omega _ { \mathrm { l } } = \omega _ { \mathrm { 2 } }$ 口

输入信号与本振信号经过混频，并通过低通滤波器滤除2倍频信号后得

$$
\left\{ \begin{array} { l } { { \displaystyle u _ { d I } \left( t \right) = \frac { U _ { i } U _ { o } } { 2 } \cos [ \theta _ { e } \left( t \right) ] } } \\ { { \displaystyle u _ { d Q } \left( t \right) = \frac { U _ { i } U _ { o } } { 2 } \sin [ \theta _ { e } \left( t \right) ] } } \end{array} \right.
$$

其中: $\theta _ { e } \left( t \right) = \theta _ { 1 } \left( t \right) - \theta _ { 2 } \left( t \right)$ 。则反正切鉴相器输出误差信号表达式为

$$
\begin{array} { c } { { u _ { d } \left( t \right) = \arctan \left( u _ { d l } \left( t \right) / u _ { d Q } \left( t \right) \right) } } \\ { { } } \\ { { = K _ { d } \theta _ { e } \left( t \right) } } \end{array}
$$

即反正切鉴相增益 $K _ { d } = 1$ 。

3)数字控制振荡器增益 $K _ { o }$

数字控制振荡器它的作用就是产生正交的正弦余弦样本，工作原理如图9所示。

根据锁相环工作原理，环路滤波器输出的控制电压用以修正数字控制振荡器的输出频率，则NCO输出频率为

$$
f _ { o u t } = \frac { f _ { s } } { 2 ^ { N } } \big ( W _ { 0 } + \Delta W \big )
$$

其中： $f _ { s }$ 为采样频率， $N$ 为相位累加字字长， $W _ { 0 }$ 为初始频率字，△W为控制频率字，数字控制振荡器相位增益为

$$
K _ { o } = \frac { 2 \pi f _ { s } } { 2 ^ { N } } T _ { d d s }
$$

其中 $T _ { d d s }$ 为相位累加字更新周期工程应用中取 $T _ { d d s } = 8 T _ { s }$ 。

![](images/83750e646719d77da91f94ba290049902600f9750221c3fb390463002586bd73.jpg)  
Fig.9Numerically controlled oscillator schematic

如图5所示的改进平方环结构，输入信号由于位宽的变化会增加额外的增益，即环路总增益由环路滤波器输出位宽$B _ { l }$ 所影响，最终环路滤波器增益 $K$ 可以重新表示为

$$
K = \left( 2 ^ { B _ { l } - 3 } \right) K _ { d } K _ { o } = \frac { 2 \pi f _ { s } } { 2 ^ { N } } T _ { d d s } \left( 2 ^ { B _ { l } - 3 } \right)
$$

空间通信中，信号处理都是将高频信号搬移到中频进行数据处理，本文中数字信号采样率 $f _ { s } = 5 0 ~ \mathrm { \ M H z }$ ，载波频率$f _ { c } { = } 1 0 ~ \mathrm { M H z }$ ，信息速率 $f _ { b } = 1 ~ \mathrm { M H z }$ ，则GMSK输入信号带宽$B _ { i } { = } 5 0 0 \mathrm { k H z }$ 。

根据图2和3的多普勒现象分析，多普勒频移最大200$\mathbf { k H z }$ ，多普勒变化率最大 $3 \mathrm { k H z }$ 。根据载波估计频偏精度，快捕带 $\Delta \omega _ { L }$ 最大为 $3 \mathrm { \ k H z }$ ，频率变化率R最大为 $3 \mathrm { k H z }$ ，输入信噪比 $E _ { b } / N _ { 0 } = 5 \mathrm { d B }$ ，本文已知阻尼因子 $\xi = 0 . 7 0 7$ ，鉴相增益$K _ { d } = 1$ ，为了提升锁相环精度频率字位宽 $\Nu = 3 2$ ，环路滤波器位宽 $B _ { l } = 2 9$ ，根据式(28)和(35)兼顾锁定时间与稳态相差则可以设定 $\omega _ { n }$ 为

$$
\omega _ { n } = 2 \pi { \times } 5 { \times } 1 0 ^ { 3 } \big ( \mathrm { r a d / s } \big )
$$

根据式(35)(26)及(18)（20）可以计算改进平方环 $\textbf { z }$ 域传递函数为

$$
H ( z ) = { \frac { 0 . 0 2 6 7 z ^ { - 1 } - 0 . 0 2 6 3 z ^ { - 2 } } { 1 - 1 . 9 7 3 3 z ^ { - 1 } + 0 . 9 7 3 7 z ^ { - 2 } } }
$$

根据式(37)可以计算改进平方环的极点为 $0 . 9 8 6 7 { \scriptstyle \frac { 2 } { 4 } } 0 . 0 1 3 2 i$ ，极点位于圆内则证明了该环路是稳定的。

# 2.3 CORDIC 鉴相的FPGA实现

CORDIC算法可以将三角函数计算转换为加减和移位操作，这非常适合于在硬件电路上实现，该算法不仅可以节约FPGA的硬件资源，还能大大提高计算速度[22]。CORDIC算法坐标旋转图如图10所示。

![](images/eda9b1cb43d991028152d3f57858c0b70a98d0ca656c178eeb5bcdd72fcc3e49.jpg)  
图10坐标旋转图

旋转公式为

$$
\left\{ \begin{array} { l l } { x _ { i + 1 } = x _ { i } \cos \theta - y _ { i } \sin \theta } \\ { y _ { i + 1 } = x _ { i } \sin \theta + y _ { i } \cos \theta } \end{array} \right.
$$

通过去除因数 $\displaystyle \cos \theta$ 可以得到伪旋转公式为

$$
\left\{ \begin{array} { l l } { x _ { i + 1 } = x _ { i } - y _ { i } \tan \theta = x _ { i } - y _ { i } 2 ^ { - i } } \\ { y _ { i + 1 } = y _ { i } + x _ { i } \tan \theta = y _ { i } + x _ { i } 2 ^ { - i } } \end{array} \right.
$$

其中 $\tan \theta = 2 ^ { - i }$ 。

同时伪旋转公式可以表示为

$$
\left\{ \begin{array} { l l } { x _ { i + 1 } = x _ { i } - y _ { i } 2 ^ { - i } d _ { i } ? } \\ { y _ { i + 1 } = y _ { i } + x _ { i } 2 ^ { - i } d _ { i } ? } \\ { z _ { i + 1 } = z _ { i } - d _ { i } \arctan 2 ^ { - i } } \end{array} \right.
$$

其中： $\textbf { z }$ 是迭代角度的累加值，每次迭代旋转的角度为arctan $2 ^ { - i }$ ，大小可以通过查表法获取，取值如表1所示。 $d _ { i }$ 等于sgn $\left( \begin{array} { l } { y _ { i } } \end{array} \right)$ ，决定每次旋转的方向。

表1旋转角度值   
Table1 Rotation angle value   

<html><body><table><tr><td>i</td><td>tanθ=2-i</td><td>0(°)</td></tr><tr><td>1</td><td>1.00000000</td><td>45.00000000</td></tr><tr><td>2</td><td>0.50000000</td><td>26.56505118</td></tr><tr><td>3</td><td>0.25000000</td><td>14.03624347</td></tr><tr><td>4</td><td>0.12500000</td><td>7.12501635</td></tr><tr><td>5</td><td>0.06250000</td><td>3.57633437</td></tr><tr><td>6</td><td>0.03125000</td><td>1.78991061</td></tr><tr><td>7</td><td>0.01562500</td><td>0.89517371</td></tr><tr><td>8</td><td>0.00781250</td><td>0.44761417</td></tr><tr><td>9</td><td>0.00390625</td><td>0.22381050</td></tr></table></body></html>

CORDIC鉴相曲线如图11所示。

![](images/afe9b7f90ca3e32d02b382444446da0f394393360949de21a5058bf448bee573.jpg)  
图9数字控制振荡器原理图  
图11CORDIC 算法鉴相曲线  
Fig.11 CORDIC algorithm phase discrimination curve

# 2.4载波频率估计的FPGA实现

锁相环路的捕获时间与初始频差有着直接的关系，初始频差越大，捕获时间越长，受限于锁相环路的性能要求，捕获带宽较小，则在频偏较大的情况下无法完成本地载波与相位的同步，继而无法进行相干解调。通过对输入信号进行分析确定粗略载波频率，控制初始频差在一个较小的范围内，便于锁相环路进行快速捕获。

频率估计模块的原理框图如图12所示。

![](images/17ff47f0fc1790b6a92e37a194b895ca93398c74cf6f0a2ee6fc14824acea857.jpg)  
Fig.10 Coordinate rotation diagram   
图12频率估计原理图  
Fig.12 Frequency estimation schematic

频率估计模块的核心是图12中的N点的FFT运算（采用IP核)。通过对N个输入信号点进行FFT运算后，对运算结果进行求模并查找最大幅值的位置，即谱线点，通过谱线点的位置确定估计值，最后转换成频率字输出。

本方法是基于FFT算法实现频率估计，结构简单，对输入信噪比为 $E _ { b } / N _ { 0 } = 5 \mathrm { d B }$ ，频移在 $- 3 0 0 ~ \mathrm { k H z } \sim 3 0 0 ~ \mathrm { k H z }$ 范围内的GMSK信号的估计精度进行了仿真如图13所示，结果显示能够满足多普勒频移估计要求。

![](images/e8d3cb6d25c1b2c1fd15e266deff088333a5b8be73193398cb9a581340c4cfe1.jpg)  
图13FFT载波估计仿真图

# 3 实验与讨论

文中选用Altera公司的CycloneIV系列的EP4CE75F23C8 芯片，采用QuartusII 和ModelSim 以及MATLAB进行联合仿真测试传统平方环与改进平方环在大多普勒频移，以及不同信噪比条件下的工作性能。

测试输入初始条件：调制方式为GMSK，采样率为50$\mathbf { M H z }$ ，载波频率为 $1 0 \mathrm { M H z }$ ，初始频移为 $2 5 0 \mathrm { k H z }$ ，多普勒变化率为 $3 \mathrm { k H z } / \mathrm { s }$ ，信息速率1Mbps。

# 3.1传统平方环结构

传统平方环中只包含鉴相器、环路滤波器、数字控制振荡器（NCO）三个主要模块，其中鉴相器一般采用的正弦鉴相器实现近似线性鉴相。

实验1传统平方环结构进行GMSK调制信号的载波恢复与时钟同步，输入信噪比为 $E _ { b } / N _ { 0 } = 2 0 \mathrm { d B }$ ，进行ModelSim仿真如图14所示。

![](images/602a93d3d9227733dda0ee78aa935c21be682fbda686a20142f04e6895e0eeb2.jpg)  
图14载波恢复与时钟同步( $E _ { b } / N _ { 0 } = 2 0 \mathrm { d B }$ 门  
Fig.14 Carrier recovery and clock synchronization（ $E _ { b } / N _ { 0 } = 2 0 \mathrm { d b } )$

图14中，载波恢复环路的环路滤波器输出frequency_df_c和时钟同步环路的环路滤波器输出frequency_df_s的输出结果显示未收敛，说明环路处于失锁状态，证明在大多普勒频移和快速多普勒变化率的情况下，环路自然角频率为 $5 0 \mathrm { { k H z } }$ 时，由于环路捕获带宽小于固定频差，传统平方环无法实现GMSK信号的载波恢复与时钟同步。

实验2在传统平方环的基础上加入载波估计模块，目的是克服大多普勒频移的影响，将初始频差控制在较小范围，输入信噪比为 $E _ { b } / N _ { 0 } = 2 0$ dB和 $E _ { b } / N _ { 0 } = 5 \mathrm { d B }$ ，进行ModelSim仿真如图15和16所示。

![](images/96b935183e5ebb0099c1fe521e35971243642045efa81febab6a342397688f4d.jpg)  
图15载波恢复与时钟同步 $\mathrm { ~ \ ' ~ } E _ { b } / N _ { 0 } { = } 2 0 \mathrm { d } \mathrm { B }$

![](images/4460a67cce2af0216bf69fe307dd4238bc7bac36ac3ea43d9f17ec1ca282942c.jpg)  
Fig.13FFT carrier estimation simulation diagram   
Fig.15Carrier recovery and clock synchronization( $E _ { b } / N _ { \mathrm { 0 } } { = } 2 0 \mathrm { d } \mathrm { b } )$   
图16载波恢复与时钟同步( $E _ { b } / N _ { 0 } = 5 \mathrm { d B }$ ）  
Fig.16Carrier recovery and clock synchronization( $E _ { b } / N _ { 0 } = 5 \mathrm { d b } ^ { \cdot }$ 1

图15中，载波恢复环路的环路滤波器输出 frequency_df $\mathrm { ~ - ~ } ^ { \mathrm { ~ c ~ } }$ 和时钟同步环路的环路滤波器输出frequency_df_s同时进入收敛。说明在输入信噪比为 $\phantom { } ^ { \prime } E _ { b } / N _ { 0 } = 2 0$ dB 且频差处于较小范围内的情形下，传统平方环可以完成GMSK信号的载波恢复与时钟同步。载波频率估计模块在 $1 . 2 \mathrm { m s }$ 左右获取载波频率估计的频率字f_c，将频差控制在 $2 1 9 7 ~ \mathrm { H z }$ 左右，环路自然角频率为 $5 0 ~ \mathrm { k H z }$ 的传统平方环在 $5 . 5 \ \mathrm { m s }$ 左右完成载波环路与时钟环路的锁定。

图16中，信噪比为 $E _ { b } / N _ { 0 } = 5$ dB 的情况下，传统平方环载波恢复环路的环路滤波器输出 frequency_df_c和时钟同步环路的环路滤波器输出 frequency_df_s无法收敛。环路未能实现载波恢复与时钟同步的功能，说明在低信噪比条件下传统平方环无法维持其环路的稳定性。

# 3.2 改进平方环结构

本文提出改进平方环的结构是在平方环基础上增加了载波估计模块应对大多普勒频移影响，减小初始频差大小，同时利用CORDIC算法的FPGA实现完成线性鉴相，减少鉴相误差带来的影响，用以提升锁相环的稳定性。

实验3改进平方环结构，输入信噪比为 $E _ { b } / N _ { 0 } = 2 0$ dB,进行ModelSim仿真如图17所示。

将图17中环路滤波器输出、载波输出dout和时钟信号b_clk等数据进行MATLAB分析，结果如图18和19所示。经过 $1 . 2 \mathrm { \ m s }$ 左右的频偏估计，将初始频偏控制在 $2 1 9 7 \mathrm { k H z }$ 左右，环路自然角频率为 $5 0 ~ \mathrm { k H z }$ 的改进平方环在 $2 ~ \mathrm { m s }$ 左右完成相位锁定，并输出频率为 $1 0 . 2 5 \ : \mathrm { M H z }$ 的相干载波，图20可得提取的时钟信号周期为 $1 ~ \mathrm { M H z }$ 。说明在输入信噪比为$E _ { b } / N _ { 0 } = 2 0$ dB 及接收信号中存在大多普勒频移和快速多普勒变化率的情况下，短时间内实现载波恢复与时钟同步。

![](images/4cc2fbaee1d2935ba7af582f808aa0cf2811d3d3f58a0c70d8f86334985d6cff.jpg)  
图17载波恢复与时钟同步( $E _ { b } / N _ { 0 } = 2 0 \mathrm { d B }$ 0

![](images/ea5bc15b95c81e8101cec74217c7d18ad0a0ab743aa42193c456c753ffe978d9.jpg)  
Fig.17Carrier recovery and clock synchronization( $E _ { b } / N _ { 0 } = 2 0 \mathrm { d B }$ ）

![](images/c70ca4a6579007f24fddde4faa2eb6c250dc2ea7640f217d82e95c1cd24f27b5.jpg)  
图18载波环路仿真数据图( $E _ { b } / N _ { 0 } = 2 0 { \mathrm { d B } }$ ）

![](images/1cf55c51b0de4fa215ac11ec56f7c20436e3520d8f3507387c3399f7d34a5724.jpg)  
Fig.19Carrier output simulation data map( $E _ { b } / N _ { 0 } = 2 0$ dB)   
图20时钟同步环路仿真数据图( $E _ { b } / N _ { 0 } = 2 0$ dB)Fig. 20 Clock synchronization loop simulation datadiagram( $E _ { b } / N _ { 0 } = 2 0 \mathrm { d B }$ ）

实验4改进平方环结构，输入信噪比为 $E _ { b } / N _ { 0 } = 5 \mathrm { d B }$ ，进行ModelSim仿真如图21所示。

将图21中环路滤波器输出、载波输出dout、时钟信号b_clk等数据进行MATLAB分析，结果如图22和23所示。载波频偏估计同样将频差控制在 $2 1 9 7 ~ \mathrm { H z }$ 左右，与输入信噪比为 $E _ { b } / N _ { 0 } = 5 \mathrm { d B }$ 的情况下相比，频偏估计时间延长至2.2ms左右，环路锁定时间延长至 $3 . 6 \mathrm { \ m s }$ 左右，输出频率为10.25MHz的相干载波，图24可得时钟信号输出周期为 $1 ~ \mathrm { M H z }$ 。由此验证在输入信噪比为 $E _ { b } / N _ { 0 } = 5 \mathrm { d B }$ 及接收信号存在大多普勒频移和多普勒变化率的情况下，改进平方环依然可以稳定工作。

![](images/7c18d9ee846704327eee2057ab1cb19602ff715bf24d202b2523b72775b19f10.jpg)  
图21载波恢复与时钟同步( $E _ { b } / N _ { 0 } = 5 \mathrm { d B }$ ）

![](images/44311df7d3f457c2eccbe2bbe13c89d3f8d3951a265b27249c8abaeb4a6d1237.jpg)  
Fig.18Carrier loop simulation data map $\rho ( E _ { b } / N _ { 0 } = 2 0 { \mathrm { d } } \mathbf { B }$   
Fig.21 Carrier recovery and clock synchronization( $E _ { b } / N _ { 0 } = 5 \mathrm { d B }$ ）   
图22载波环路仿真数据图( $E _ { b } / N _ { 0 } = 5$ dB)

![](images/a7558602a214868700fc9f772df661144b78676bc31123f980b4ec1400ef531f.jpg)  
图19载波输出仿真数据图( $E _ { b } / N _ { 0 } = 2 0 ~ \mathrm { d B }$   
Fig.22 Carrier output simulation data map( $E _ { b } / N _ { 0 } = 5 \mathrm { d B }$ ）  
图23载波输出仿真数据图( $E _ { b } / N _ { 0 } = 5$ dB)  
Fig.23 Carrier output simulation data map( $E _ { b } / N _ { 0 } = 5 \mathrm { d B }$ 门

综合以上实验可知传统平方环无法在大多普勒频移、快速多普勒变化率以及低信噪比条件下保证环路正常工作的稳定性，而本文提出的改进平方环方案能够在大多普勒频移及低信噪比的条件下完成GMSK信号的载波恢复与时钟同步，与此同时在环路的锁定速度与稳定性上也有了一定的提高。

![](images/b65522a5bf3a215ebbf97f8f8ba466e62afd2d8318ec85a2b7553c081ed98da1.jpg)  
图24时钟同步环路仿真数据图( $E _ { b } / N _ { 0 } = 5 \mathrm { d B }$ ） Fig.24Clock synchronization loop simulation data diagram （20 （20

# 4 结束语

本文针对GMSK信号在空间通信中面临的低信噪比以及多普勒现象的环境进行了详细分析，提出了一种基于FPGA的改进平方环方法。在低信噪比条件下，短时间内快速克服多普勒现象完成载波恢复与时钟同步，并通过QuartusII和ModuleSim以及MATLAB进行联合仿真。仿真表明该方法克服了较大多普勒频移和快速的多普勒变化率的影响，在输入信噪比 $E _ { b } / N _ { 0 } = 5 \mathrm { d B }$ 以及环路噪声带宽为 $5 0 \mathrm { k H z }$ 的条件下，载波环路与时钟同步环路的锁定时间约 $3 . 6 ~ \mathrm { m s }$ 而且在不同噪声环境下的稳定性都能够满足工程需求，证明了该方法满足空间通信中GMSK信号的载波恢复与时钟同步的要求。

# 参考文献：

[1]Shambayati S,Lee D K.GMSK modulation for deep space applications [C]//Proc of IEEE Aerospace Conference.Piscataway,NJ:IEEE Press, 2012:1-13.   
[2]Shambayati S.Ka-Band telemetry operations concept:a statistical approach [J].Proceedings of the IEEE,2007,95(11):2171-2179.   
[3]Jhaidri M A,Laot C,Thomas A.Nonlinear analysis of GMSK carrier phase recovery loop [C]//Proc of International Symposium on Signal, Image,Video and Communications.Piscataway,NJ:IEEE Press,2017.   
[4]吴伟仁,节德刚,丁兴文，等.深空测控通信中GMSK 体制非相干解调 算法研究[J].宇航学报，2014，35(12):1437-1443.(WuWeiren，Jie Degang,Ding Xingwen,et al.A noncoherent demodulation algorithm of GMSK for deep-space missions [J]. Journal of Astronautics,2014, 35(12):1437-1443.)   
[5] 张金荣，吴岭.GMSK+PN 遥外测体制的性能分析[J].南京大学学 报：自然科学版，2018,54(3):489-496.(Zhang Jinrong，Wu Ling. Performance analysis of telemetry and ranging based on $\mathrm { G M S K + P N }$ technique [J]. Journal of Nanjing University：Natural Science,2018, 54(3): 489-496.)   
[6]Sessler G M A，Abello R,James N，et al.GMSK demodulator implementation for ESA deep-space missions [J].Proceedings of the IEEE,2007,95(11):2132-2141.   
[7]Satorius E,Estabrook P,Wilson J,et al.Direct-to-earth communications and signal processing for Mars exploration rover entry,descent,and landing [J]. Interplanetary Network Progress Report,20o3,153:1-35.   
[8]王乐，王竹刚，熊蔚明．基于最大似然频率精细估计的载波捕获算 法[J]．电讯技术，2013,53(1):39-43.（Wang Le，Wang Zhugang, Xiong Weiming. High-accurate carrier acquisition based on maximum likelihood estimation of refined frequency [J].Telecommunication Engineering,2013,53(1): 39-43.)   
[9] Cheng Fi, Cheng Qi. The large sample performance of a maximum likelihood method for OFDM carrier frequency offset estimation [J]. Wireless Personal Communications,2013,72 (1):227-244.   
[10]李炳旭．基于FPGA的GMSK调制解调 SoC芯片的研究与实现[D]. 大连：大连海事大学,2013.(Li Bingxu.Research and realization of GMSK modulation and demodulation SoC chip based on FPGA [D]. Dalian:Dalian Maritime University,2013.）   
[11]康超，陈丽婷，陈建斌.GMSK信号的维特比算法与FPGA实现[J]. 无线电工程,2018,48(7): 541-545.(Kang Chao,Chen Liting,Chen Jianbin.The viterbi algorithm of GMSK signal and implement in FPGA [J]. Radio Engineering,2018,48(7): 541-545.）   
[12] Kumm M,Klingbeil H,Zipf P.An FPGA-based linear all-digital phase-locked loop [J].IEEE Trans on Circuits& Systems IRegular Papers,2010,57(9): 2487-2497.   
[13] Wang Le, Wang Zhugang, Xiong Weiming. A fast and highly accurate carrier acquisition for deep space applications [C]//Proc of International Congress on Image and Signal Processing. Piscataway,NJ:IEEE Press, 2012.   
[14]CativelliFS，Estabrook PSatoriusEH,etal.Carrierrecovery enhancement for maximum-likelihood Doppler shift estimation in Mars exploration missions [J]. IEEE Journal of Selected Topics in Signal Processing,2008,2(5): 658-669.   
[15] Bergogne C, Sehier P, Bousquet M. Reduced complexity frequency estimator for burst transmission [C]//Proc of the 4th IEEE International Conference on Universal Personal Communications.Piscataway, NJ: IEEE Press,1995: 231-235.   
[16]Zhang Zhaowei, Wang Jianwei, Zhang Hailin. Joint-detection for high accelerating Doppler-shift in deep-space communications [C]// Proc of IEEEWirelessCommunicationsand Networking Conference. Piscataway,NJ: IEEE Press,2015:476-481.   
[17] Zheng Chenggong, Chen Xi, Huang Zhen. A comprehensive analysis on Doppler frequency and Doppler frequency rate characterization for GNSS receivers [C]//Proc of the 2nd IEEE International Conference on Computer and Communications.Piscataway，NJ:IEEE Press,2016: 2606-2610.   
[18] Al-Dhahir N，Saulnier G. A high-performance reduced-complexity GMSK demodulator [J]. IEEE Trans on Communications,1998,46(11): 1409-1412.   
[19] Hsieh G C,Hung JC.Phase-locked loop techniques.a survey [J]. IEEE Trans on Industrial Electronics,1996,43(6): 609-615.   
[20] HaykinSS,CarnegieR.Improvedanalogue-digitalfilter transformation [J]. Proceedings of the Institution of Electrical Engineers, 2010,118(6): 759-761.   
[21]杜勇．数字通信同步技术的MATLAB与FPGA实现[M].北京:机械 工业出版社，2013:71-96.(Du Yong．MATLAB and FPGA implementationof digitalcommunicationsynchronization techology [M]. Beijing: Mechanical Industry Pres,2013:71-96.）   
[22] Torres V，Valls J，Canet M J.Optimized CORDIC-based atan2 computation for FPGA implementations [J]. Electronics Letters,2017, 53(19): 1296-1298.