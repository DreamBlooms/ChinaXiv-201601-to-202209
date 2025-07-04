# 一种判决反馈的车车通信快时变信道估计算法

丁青锋，韦民

(华东交通大学 电气与自动化工程学院，南昌 330013)

摘要：针对车车通信中快时变无线通信不稳定性和追踪的复杂性，以及在IEEE802.11a 系统中基于前导码的信道估计方案不能满足高速场景中的要求，提出一种基于盲信道估计过程中的判决反馈信道估计方法。借助来自接收机端解调器的输出判定符号，利用噪声衰落信道传输数据的统计特性追踪快速变化的信道传递函数；使用时间截断技术对获得的信道估计值进行判决反馈降低噪声影响，对载波间干扰进行消除，从而提高快时变信道的估计精度。仿真表明，相对于传统的信道估计算法，所提出的算法具有更优的误码率和均方误差性能。

关键词：车车通信；快时变；判决反馈；信道估计 中图分类号：TN914.4 doi:10.3969/j.issn.1001-3695.2018.05.0324

# Fast time-varying channel estimation algorithm for vehicle-to-vehicle communication based on decision directed

Ding Qingfeng,Wei Min (School ofElectrical &AutomationEngineering,East China Jiaotong University,Nanchang 33oo13,China)

Abstract: In viewof thecomplexityoffastand time-varying wireless communication in vehicle-to-vehicle communication andthecomplexityof the tracking,thechannel estimation scheme basedonthe preamble inthe IEEE802.1lasystemcannot meetthe equirements in the high-speed scene.This paper proposed adecision feedback chanel estimation method based on blind chanel estimation.With thehelpofoutput decision symbols fromthereceiver demodulator,the fastchanging chanel transferfunctionis trackedusingthestatisticalcharacteristicsofthedata transmitedbythenoisefadingchannel.The time truncationtechniqueusesthe decision fedback toreducethe noise influence,eliminatethe intercarrier interferenceand improve the estimation accuracyof the fast time-varying channel.Simulation results show that the proposed algorithm has better BER and MSE performance than these classical channel estimation algorithms.

Key words:V2V; fast time-varying;decision directed; channel estimation

# 0 引言

近年来，由于高速铁路的迅速发展和车载物联网用户急剧增长，引发了许多无线通信问题。在快时变无线通信场景下，以高铁无线通信为例，要得到可靠、快捷的无线通信，需要一个鲁棒性的车辆连接网络[1.2]。车车通信要求车辆之间保持良好的通信性能，可以对任意信息作出及时的反应；充分利用车车通信的优势，建立一种鲁棒性的车辆间通信方法。在科学研究中，一个准确可靠的信道估计算法在高速铁路车车通信中扮演着必不可少的角色[3]。之前的研究也表明IEEE802.11p标准采用的基于前导长训练序列的最小二乘(LS，1east squares)信道估计算法有效地跟踪到信道的快速变化，然而没有考虑通信信道中的噪声对整个通信系统产生的影响，最终会导致系统性能急剧下降[4:5]。

针对上述出现的一系列通信问题，研究人员基于大量的科学研究，提出许多新的信道估计方法。通过分析突发信号的结构特征，提出一种改进的基于压缩感知的稀疏信道估计方法[。针对卡尔曼滤波压缩感知在信道估计时伪测量过程计算效率较低的问题进行研究[7]，仿真结果表明，同等条件下该算法相对于原有算法，估计精度和收敛速度均有较大程度提高，在低信噪比和不同稀疏度下都具有较好的鲁棒性和实用性。为了更好地利用收敛速度和低复杂度的优势，提出一种先进的接收机方案，利用判决导向信道估计的方法，为了让信道平滑，以增加计算复杂度为代价[8]。针对具有较大多普勒扩展和时延扩展的车载通信环境，利用后训练序列信道响应携带的信道变化信息，提出一种结合后训练序列的判决反馈信道估计方法。该方法采用最小二乘算法估计后训练序列的信道响应；对前一个正交频分复用符号和后训练序列的信道响应估计值进行系数加权求和来估计当前正交频分复用（orthogonalfrequencydivisionmultiplexing，OFDM）符号的信道响应，并利用其4个导频子载波的信道频率响应关系自动获取加权系数；最后,对获得的信道响应估计值进行判决反馈和低通滤波以降低噪声影响。要密切跟踪车车通信（vehicletovehicle，V2V）的通道，从而减少数据包错误率（packet error rate，PER）[9-l2]。基于传统的车车通信的信道估计算法，没有考虑到车车通信的快时变性和追踪困难程度，以及复杂的无线信道环境。

本文考虑车车通信中快时变无线通信不稳定性和追踪的复杂性，提出一种基于判决反馈信道估计方法。借助来自接收机端解调器的输出判定符号，通过利用噪声衰落信道传输数据的统计特性追踪快速变化的信道传递函数；使用时间截断技术对获得的信道估计值进行判决反馈降低噪声影响，对载波间干扰进行消除，提高快时变信道的估计精度。仿真表明，该方法在快时变信道的通信场景下，获得较好的信道估计性能。

# 1车车通信系统模型

在快时变信道环境中，由于多普勒效应的存在，信道在一个符号周期内快速变化，称其为快时变信道，然而待估计的信道参数数量大大增加。本文拟采用基扩展模型（BEM,BasicExpansionModel)对每一个正交频分复用OFDM符号块对应的快时变信道建模，该模型可以对快时变信道特性进行较好的拟合，同时也可以降低估计参数数量[13]。

设定 $h ( n , l )$ 为一个OFDM符号周期内第 $l$ 径，第 $n$ 个采样点的信道响应，BEM本身采用一种基函数的线性组合，可以有效的拟合出信道参数，表示如下：

$$
h ( l , n ) = \sum _ { q = 0 } ^ { Q } g _ { q } ( l ) b _ { q } ( n )
$$

其中： $b _ { q } ( n )$ 为BEM 基函数， $g _ { \boldsymbol { q } } ( \boldsymbol { l } )$ 称为BEM系数， $\boldsymbol { \mathcal { Q } }$ 称为BEM阶数。采用BEM通常假定在一个OFDM符号内BEM系数保持不变，而基函数是一组固定的正交基，因此采用BEM可以将待估计的信道参数由 $N \times L$ 个降到 $( \boldsymbol { Q } + \boldsymbol { 1 } ) \times \boldsymbol { L }$ 个，大大减少了估计数量。发送的信号中经过加性高斯白噪声（AWGN，AdditiveWhiteGaussianNoise）信道传输后，接收端接收到的频域信号表示为

$$
Y = H X + W = H _ { a \nu e } X + H _ { I C I } X + W
$$

$$
H _ { _ { k , \nu } } = \frac { 1 } { N } { \sum _ { n = 0 } ^ { N - 1 } \sum _ { l = 0 } ^ { L - 1 } { h _ { _ { l } } ( n ) e ^ { - j \frac { 2 \pi } { N } \left[ \nu ( l - n ) + n k \right] } } }
$$

其中： $X$ 和 $Y$ 分别为频域的发送和接收信号， $W$ 为时域加性高斯白噪声的频域表示， $H _ { \mathrm { k , v } }$ 为信道频域矩阵 $H$ 的元素， $N$ 为OFDM系统子载波个数， $L$ 为抽头数， $H _ { a v e }$ 为对角矩阵，

$H _ { k , k }$ 为其对角元素， $H _ { I C I }$ 为数据子载波对导频子载波的干扰矩阵，其对角线元素为0，非对角线元素为 $H _ { \mathrm { k , v } } ( k \neq \nu )$ 。通过对表达式（3）分析可以得出， $h _ { l } \left( n \right)$ 随时间 $n$ 变化时， $H$ 有非对角元素，即快时变信道中存在载波间干扰（inter-carrierinterference，ICI）项。因此，需要对ICI干扰进行消除，提高快时变信道的估计精度。

# 2 判决反馈算法的设计

# 2.1 时域截断设计

为了利用V2V通信环境的时域信道特性，通过时域截断提升信道估计和跟踪能力以达到解决信道频率响应的相位模糊问题。截断时域中的信道估计值高于V2V信道模型定义的第8个抽头中的值，然后在频域和时域之间来回切换，直到收敛。信道噪声的影响（以及信道估计误差）在时域中被反映为更高的抽头数目，所以利用截断信道冲激响应技术以增强信道估计性能。另一方面，这种技术提升了信道跟踪能力，即使是在高度动态的环境中进行粗略的信道估计。

每次迭代需要一个M点IFFT和一个 $\mathbf { M }$ 点FFT。当 $\mathrm { M } = 6 4$ ，该技术对于IEEE802.11p标准具有低计算复杂度特性。通过搜索 $j$ 候选相位值来解决相位模糊度 $\lambda _ { _ m }$ （调制方式为BPSK时，$\lambda _ { _ { m } }$ 为 $\pm 1$ ；调制方式为QPSK时， $\lambda _ { _ { m } }$ 为 $\left\{ \pm 1 , \pm j \right\} .$ ）， $j$ 表示卷积的倍数，其中 $H _ { f r e q } ( k )$ 是频域中的初始信道估计值，并且$H ^ { \textit { j } }$ 是接收到的信号上升到第j个权值以消除数据影响。具体表达如式（4）所示。

$$
H _ { _ { f r e q } } ( k ) = \arg \left\| { H _ { _ { f r e q } } ( k ) - \lambda _ { m } \Big [ H ^ { j } ( k ) \Big ] ^ { \frac { 1 } { j } } } \right\|
$$

$H _ { f r e q }$ 是 $h _ { t i m e }$ 的快速傅里叶变换， $h _ { t i m e }$ 是 $H _ { f r e q }$ 的快速傅里叶反变换如式（5）（6）所示。

$$
h _ { t i m e } = I F F T ( H _ { f r e q } )
$$

$$
H _ { f r e q } = F F T ( h _ { t i m e } ( 1 : 8 ) )
$$

# 2.2判决反馈信道估计

判决反馈信道估计系统的整体流程框图如图1所示，具体工作流程如下：首先去循环前缀，之后进行快速傅里叶变换，得到信号 $Y _ { t } ( k )$ ，然后进行信号均衡，得到均衡信号 $S _ { t } ( k )$ ，然后解调得到信号 $X _ { t } ( k )$ 。

![](images/2f8587d54ca95ddbccc89089eda6cb68a57700df97844fea6bf992bbfdd1e576.jpg)  
图1判决反馈系统框图

在这部分中，提出一种用于高度动态V2V环境的新型半盲信道估计与跟踪算法。在所提出的算法中，利用判决反馈信道估计来获得初始估计值，然后进行时间截断。算法的解释和分解如下：

基于之前估计的转移因子 $H _ { t - 1 } ( k )$ 作为当前转移因子的预测,其中 $S _ { t } \left( k \right)$ 是时间为t,子载波数为 $\mathbf { k }$ 的均衡符号， $Y _ { t } ( k )$ 表示时间为 $\mathbf { \sigma } _ { \mathbf { t } }$ ，子载波数为 $\mathbf { k }$ 的接收信号， $H _ { t - 1 } ( k )$ 表示前一个符号的信道估计值。具体的如等式（7）所示。

$$
S _ { t } ( k ) = \frac { Y _ { t } ( k ) } { H _ { t - 1 } ( k ) }
$$

使用解调后的数据进行进一步的修正，以计算新的的信道传递因子 $H _ { i n i t , t } ( k )$ ，如式（8）所示。

$$
H _ { i n i t , t } ( k ) = \frac { Y _ { t } ( k ) } { X _ { t } ( k ) }
$$

其中 $X _ { t } ( k )$ 是 $S _ { t } ( k )$ 的解调信号。

在更新因子为 $\gamma$ 的简单递归表达式中进行信道估计值的更新，其中包含信道传递因子 $H _ { t - 1 } ( k )$ ，和当前计算的信道传递因子 $H _ { i n i t , t } ( k )$ ，信道估计值为 $H _ { t } ( k )$ 。

$$
H _ { \mathfrak { r } } ( k ) = \gamma H _ { \mathfrak { i } n i t , \mathfrak { t } } ( k ) + ( 1 - \gamma ) H _ { \mathfrak { r } - 1 } ( k )
$$

进行时间截断的部分每次迭代只需要一个64点FFT和一个64点IFFT。因为信道估计在经过2次迭代后大部分时间都收敛，所以时间截断技术的复杂度较低。

$$
H _ { _ { D D } } ( k ) = \arg \operatorname* { m i n } \left\| H _ { i n i t , t } ( k ) - \lambda _ { m } \Big [ H _ { t } ^ { ^ { j } } ( k ) \Big ] ^ { \frac { 1 } { j } } \right\|
$$

# 2.3判决符号的后验概率

在OFDM系统中，假定接收到的信号 $\mathrm { \Delta Y }$ 是受信道传递因子 H 和加性高斯白噪声 $G ( 0 , \delta ^ { 2 } )$ 干扰的随机变量，其中接收信号表达式如下：

$$
Y = X \cdot H + W
$$

接收信号Y的概率密度函数为

$$
\left. P ( \boldsymbol { Y } \big | \boldsymbol { X } ) = \frac { 1 } { \sqrt { 2 \pi } \delta } \mathrm { e x p } ( - \frac { 1 } { 2 \delta ^ { 2 } } \big | \boldsymbol { Y } - \boldsymbol { X } \cdot \boldsymbol { H } \big | ^ { 2 } ) \right.
$$

在 M-QAM调制方式中， $X _ { m } ( m = 1 , 2 . . M )$ 取自有限字母集合，用小s表示。在发射端，如果所有的符号 $X _ { m }$ 都是均匀分布，根据全概率定理和贝叶斯理论，检测信号后验概率表达式如式（13）所示。

$$
P ( X _ { t } | Y ) = \frac { p ( Y | X _ { t }  ) } { \sum _ { m } P ( Y | X _ { m }  ) } = \frac { \exp ( - \displaystyle \frac { | H | ^ { 2 } } { 2 \delta ^ { 2 } } \cdot | S _ { t } - X _ { t } | ^ { 2 } ) } { \displaystyle \sum _ { m } \exp ( - \displaystyle \frac { | H | ^ { 2 } } { 2 \delta ^ { 2 } } \cdot | S _ { t } - X _ { m } | ) }
$$

其中符号 $X _ { t }$ 为度量符号， $S _ { t }$ 为均衡符号。

等式（13）表明， $\begin{array} { r } { P ( X _ { t } \vert Y ) } \end{array}$ 取决于距离、信道传递因子H和噪声的影响。此外，在集合s中，它表示测量的符号具有最大的后验的概率。很明显：

$$
{ \frac { 1 } { M } } \leq P ( X _ { t } | Y ) \leq 1
$$

# 2.4判决反馈估计的更新因子

递归滤波器生成的更新因子》取决于判决符号的质量，也就是检测符号估计的可靠性。在 $[ 0 , \gamma _ { \mathrm { m a x } } ]$ 内，由于 $\begin{array} { r } { P ( X _ { t } \vert Y ) } \end{array}$ 和》不是均匀分布的，所以归一化的更新因子 $\gamma$ 表达式如下：

$$
\gamma = \gamma _ { \mathrm { m a x } } \left[ \frac { P ( X _ { t } \mid Y ) - \frac { 1 } { M } } { 1 - \frac { 1 } { M } } \right]
$$

# 2.5判决反馈时域截断估计流程

a)设置判决反馈时间截断算法的所有参数以及迭代的终止条件；随后初始化OFDM传输系统的基本模型。

b)对接收信号快速傅里叶变换，得到频域信号 $Y _ { t } ( k )$ 。

c)对 $Y _ { t } ( k )$ 进行均衡，均衡后的结果用 $S _ { t } ( k )$ 表示。

d)令前一个估计的转移因子 $H _ { t - 1 } ( k )$ 作为当前转移因子的预测初始估计值。

e)使用解调后的数据进行进一步的修正，以计算新的的信道传递因子 $H _ { i n i t , t } ( k )$ 。

f)在时变因子为／的简单递归表达式中进行信道估计值的更新。

# 3 仿真结果与分析

本文提出的算法与传统三种的算法（LS、STA、MMSE）相比较，LS为最小二乘估计算法，基本表达式为

$$
\hat { H _ { L S } } = X ^ { - 1 } Y
$$

MMSE为最小均方差估计， $R _ { \scriptscriptstyle H H }$ 为信道的相关矩阵，基本表达式为

$$
\hat { H } = R _ { _ { H H } } ( R _ { _ { H H } } + \frac { \delta _ { z } ^ { 2 } } { \delta _ { x } ^ { 2 } } I ) H
$$

STA 为时间平均估计， $\alpha$ 为遗忘因子， $H _ { { \boldsymbol { u p } } , t }$ 为更新的信道估计值，具体表达式如下：

$$
H _ { s T A , t } = ( 1 - \frac { 1 } { \alpha } ) H _ { s T A , t - 1 } + \frac { 1 } { \alpha } H _ { u p , t }
$$

均方误差（MSE）是判决反馈信道估计的性能指标，误码率（BER）被用来描述整个判决系统的性能指标。MSE定义如式（19）所示，表示信道传递因子 $H _ { i n i t , t } ( k )$ 和其的估计值$H _ { t } ( k )$ 之间的均方误差：

$$
\varepsilon _ { _ { M S E } } = E [ \left| H _ { _ { i n i t , t } } ( k ) - H _ { _ { t } } ( k ) \right| ^ { 2 } ]
$$

本文的仿真是基于MATLAB2010平台进行的，具体的仿真参数设置，如表1所示。

表1仿真参数表  

<html><body><table><tr><td>参数名称</td><td>配置</td></tr><tr><td>子载波数</td><td>64</td></tr><tr><td>循环前缀长度</td><td>8、16</td></tr><tr><td>OFDM符号数</td><td>50、100、200</td></tr><tr><td>调制方式</td><td>16QAM、BPSK、QPSK</td></tr><tr><td>Packet</td><td>50</td></tr><tr><td>Alphabet size</td><td>4、8、16</td></tr><tr><td>信道模型</td><td>BEM</td></tr><tr><td>相位模糊度λ</td><td>{1,±j}</td></tr><tr><td>判决估计参数</td><td>γ =0.2,α =1.5</td></tr></table></body></html>

图1所示在循环前缀长度为8、调制方式BPSK、星座大小为2、最大多普勒频率为 ${ 5 0 0 } \mathrm { H z }$ 、100个OFDM符号时，不同信噪比下各种信道估计算法的误比特率性能曲线。由图1可知，本文提出的DD 算法性能优于其他算法，由于LS 算法在导频数量小于信道长度时会失效，降低了算法的精度。本文提出的方法通过计算初始值来消除噪声使用解调数据进行信道估计，性能得到很大提升，较上述传统算法有着更好的信道估计性能，并且复杂度更低。当信噪比为15dB 时，STA算法和本文提出的算法的误比特率性能差距最大，当信噪比从0-30dB变化时，传统的算法和本文提出的算法之间的误比特率的差别越来越明显，MMSE 算法的估计性能介于LS 算法和STA算法之间。如图1所示当误比特率一定时，很明显，判决反馈方法有更低的信噪比，随着误比特率的逐渐增加，判决反馈算法的信噪比曲线递减得最快。

![](images/31bb465d25711fa68f57d194130a601585af4e28abaf226a5d2c7b3e9395c224.jpg)  
图1不同信噪比下各算法误比特率性能曲线

图2所示为循环前缀长度为8、调制方式为QPSK、星座大小为4、最大多普勒频率为 $1 0 0 0 \mathrm { H z }$ 、500个OFDM符号时，不同信噪比下各种信道估计算法的均方差性能曲线。由图2可知，本文提出的判决反馈算法性能优于其它算法，其均方误差曲线下降的速度更快。LS算法[5本身在每个子载波上的信道频域估计都存在一个高斯噪声项，所以均方误差较高。很明显 STA算法的性能明显优于LS算法。当信噪比为 $3 0 ~ \mathrm { d B }$ 时，STA算法和DD算法的均方误差性能差距最大，STA算法的均方误差在18 dB之后，其性能逐渐优于MMSE 算法[14]。当信噪比在$0 { - } 3 0 ~ \mathrm { d B }$ 之间变化时，传统的信道估计算法和DD算法的均方误差的性能差别越来越明显，当均方误差一定时，很明显，本文提出的方法有更低的信噪比，随着误比特率的逐渐增加，判决反馈算法的信噪比递减的最快。当信噪比在0-5dB范围内，三种算法的均方误差性能差距不明显，在5-30dB 范围内，判决反馈方法的均方误差最小，在30dB 时，其余两种算法和判决反馈方法的均方误差性能差别明显，LS算法和判决反馈算法差距最大。总体来说，MMSE 算法的均方误差性能介于LS算法和DD算法之间，判决反馈方法的性能最好。

![](images/18dba91aff1340651fbf96ac0c23a73c436d192ade35bfd59f66235a1240884a.jpg)  
图2不同信噪比下各算法均方误差性能曲线

图3所示在当导频数等于20、30，调制方式为16QAM星座大小为16、最大多普勒频率为 $1 0 0 0 \mathrm { { H z } }$ 、25个OFDM符号下的不同信噪比下四种信道估计算法的误比特率性能曲线。当导频数越大，DD算法的性能越优异。由图3可知，DD算法的误比特率性能曲线下降的最快，当信噪比为30dB时，DD算法的性能最好，各种算法性能差距最明显，其中MMSE和STA 算法性能差距不明显，但是总体来说，STA 算法的性能要优于MMSE 和LS算法，当信噪比在0-10dB之内，DD算法和其他三种传统算法的性能差距不大，随着信噪比的增加，DD算法的性能明显优于其他三种经典信道估计算法，当误比特率一定时，DD 算法的信噪比较低，然而其他三种算法的信噪比明显大于DD 算法。

图4所示在循环长度为8、16，调制方式为16QAM 星座大小为16、最大多普勒频率为 $1 0 0 0 \mathrm { H z }$ 、500个OFDM符号时下的不同信噪比下四种信道估计算法的误比特率性能曲线，随着信噪比的增加，DD算法的性能明显优于其他三种经典算法。循环长度为16的DD算法性能优于长度为8的判决反馈算法。从图4所知，LS、STA两种算法的曲线下降的速度较缓慢，当信噪比为30dB 时，STA算法和本文提出的算法的误比特率性能差距最大，当信噪比从0-30dB变化时，传统的算法和本文提出的DD算法之间的误比特率的差别越来越明显，当误比特率一定时，很明显，本文提出的DD方法有更低的信噪比，随着误比特率的逐渐增加，判决反馈算法的信噪比递减的最快。然而MMSE算法和其它两种信道估计算法的性能相比，差距不明显。

![](images/b919e784dab68618230764d60f7c73ec148da27484a670ad1b616c09b9d7aa53.jpg)  
图3导频数目不同时，各种算法误比特率性能曲线

![](images/4c27a98be8695d94658702c6e29de27c15dc706bc9ae679ab3d2d9657346ad9f.jpg)  
图4循环前缀长度不同时，各种算法误比特率性能曲线

# 4 结束语

本文针对现有的信道估计算法没有充分考虑车车通信中快时变无线通信不稳定性和追踪复杂性的问题，提出一种基于判决反馈的车车通信快时变OFDM信道估计算法，借助来自接收机端解调器的输出判定符号，通过利用噪声衰落信道传输数据的统计特性追踪快速变化的信道传递函数。使用时间截断技术对获得的信道估计值进行判决反馈降低噪声影响，对载波间干扰进行消除，提高快时变信道的估计精度。理论分析和仿真结果表明判决反馈方法具有良好的信道估计信能、估计精度，也具有很好的鲁棒性。

# 参考文献：

[1]Bilstrup K, Uhlemann E,Strom EG,et al.Evaluation of the IEEE 802.11p MAC method for vehicle-to-vehicle communication [C]// Proc of the 68th IEEE Vehicular Technology Conference.2Oo8:1-5.   
[2] $\Nu _ { \mathrm { g } \mathrm { ~ S ~ C ~ } }$ ，Zhang Wuxiong，Zhang Yu,et al.Analysis of access and connectivity probabilities in vehicular relay networks[J].IEEE Journal on Selected Areas in Communications,2011,29(1): 140-150.   
[3] 蔡明，曾嵘.高速铁路中基于组导频的 OFDM 系统时变信道估计算法 [J]．铁道学报,2015,(5):52-56.(Cai Ming,Zeng Rong.Group-pilot-aided time-varying channel estimation for high-speed railway OFDM system [J]. Journal of The China Railway Society,2015,(5):52-56.   
[4]Zhao Wangxing,Fang Fang，et al.A diverse proof of OFDM channel estimation comparing CP-sequences and training-sequences methods under LS frame [C]// Proc of the 6th IEEE Joint International Information Technology and Artificial Inteligence Conference. 2011: 380-384.   
[5]丁青锋，邱翔．基于差分进化的时变信道最大似然估计算法 [J].高技 术通讯,2016 (6): 528-533.(Ding Qingfeng,Qiu Xiang.Novel diferential evolution algorithm with spatial evolution rules [J].High Technology Letters. 2016 (6): 528-533.   
[6] 田文飚，康健，张洋．基于卡尔曼滤波的压缩感知弱匹配去噪重构[J]. 电子学报,2014,42(6):1061-1067. Tian Wenbiao,Kang Jian,Zhang Yang. Weakly matching pursuit denoising recovery for compressed sensing based onKalman filtering [J]. ACTA Electronica Sinica,2014，42 (6): 1061-1067.   
[7]Chen Baohao,Cui Qimei, Yang Fan,et al.A novel channel estimation method based on Kalman filter compressed sensing for time-varying OFDM system [C]//Proc of the 6th International Conference on Wireless Communications and Signal Processing. 2014: 1-5.   
[8]Wei Chunfan,Lin D,et al.A decision-directed channel estimator for OFDM based bursty vehicular communication [J]. IEEE Transon Vehicular Technology,017,66(6): 4938-4953.   
[9]王彦，邓姣，王超．车载OFDM 通信系统中结合后训练序列的判决反 馈信道估计方法[J].重庆邮电大学学报：自然科学版，2017,(1):1-8. (Wang Yan,Deng Jiao,Wang Chao,et al.A decision-directed channel estimation method with postamble in vehicular OFDM communication system[J] JournalofChongqingUniversityofPostsand Telecommunications: Natural Science Edition,2O17,(1): 1-8.   
[10]Li Changzhen,Yang,Kun,Yu Junyi.et al.V2V radio channel performance based on measurements in ramp scenarios at 5.9 GHz [J]. IEEE Access, 2018, PP (99): 1-1.   
[11] Liu Jianfei,Feng Jie,Wang Mengjun,et al. Downlink channel estimation algorithm in TD-LTE digital relay systems[C]// Procof the14th IEEE International Conference on Communication Technology. 2012: 474-478   
[12] Fernandez JA, Stancil D D,Bai Fan,et al. Dynamic channel equalization for IEEE 802.11p waveforms in the vehicle-to-vehicle channel [C]// Proc of the 48th Annual Conference on Communication,Control,and Computing. 2010: 542-551.   
[13]尹燕，王敏，王传云．引入加权系数消除 ICI的二次快时变信道估计算 法[J].计算机应用研究，2019,36（2）．（YinYan，WangMin，Wang Chuanyun.et al. Twice rapidly time-varying channel estimation algorithm basedon ICI cancellation using weighted coefficient [J] Application Research of Computers,2019,36(2).)   
[14] Janjaap VD B,EdforsO,SandellM,et al.Onchannel estimation in OFDM systems[Cl// Proc of Vehicular Technology Conference.1995: 815-819.