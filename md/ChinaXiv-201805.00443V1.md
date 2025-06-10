# UFMC系统载波干扰抑制改进算法

龙恳，陈和力，段思睿，周志义(重庆邮电大学 通信与信息工程学院，重庆 400065)

摘要：针对ICI自消除算法导致UFMC 系统频带利用率过低的问题，提出一种联合部分自消除和加升余弦窗的改进方案。该方案具体通过在UFMC 系统发射端子带边界插入自消除子载波，并在UFMC 系统接收端进行时域加窗来达到抑制UFMC 系统干扰、提升系统的频带利用率的目的。对算法进行MATLAB仿真实验，当子带两侧设置4个自消除子载波时，相较自消除算法，系统载波干扰比增大，同时系统的频谱利用率也提升了 $10 \%$ 。仿真结果表明，所提算法能够有效抑制ICI，提高系统抗干扰性能，同时提升系统频带利用率。

关键词：通用滤波多载波；自消除；载波间干扰；升余弦窗；频带利用率 中图分类号：TN929.5 doi: 10.3969/j.issn.1001-3695.2018.04.0181

# Improved algorithm of carrier interference suppression in UFMC system

Long Ken, Chen Heli, Duan Sirui, Zhou Zhiyi (Telecommunication& Information Engineering Institute,Chongqing UniversityofPosts&Telecommunications,Chongqing 400065, China)

Abstract:For the problemthat theICIself-cancelltion algorithm leads tothe underutilizationof the UFMCsystemfrequency band,this paper proposedanimproved schemethatcombines partialself-cancelltionandraisedcosine widows.This scheme specifically inserted theself-eliminating sub-carrers intothe UFMCsystem's transmitting terminalband boundary，and performed windowing inthe time domainat thereceiving end ofthe UFMC systemtoachievethe purposeofsuppressng UFMC system interferenceand improving system bandutilization.This paper conducted simulation experiments of the algorithm on MATLABplatform.There were four self-canceled sub-cariers on both sidesof the sub-band,the system carrer-tointerferenceratio increased compared with theself-cancelationalgorithm,andthespectrum utilizationof thesystemalso increased by $10 \%$ .The simulation results showed that the proposed algorithm could efectively suppress ICI, improve the system's anti-jamming performance,and improve the system bandwidth utilization.

KeyWords: UFMC; SelfCancellation; Inter-carrer interference; Raise cosine window; Frequencyutilization

# 0 引言

通信技术的飞速发展与人们日益提升的通信需求和用户体验息息相关。正交频分复用（OFDM)作为第四代移动通信（4G)中关键技术，凭借其突出的抗干扰能力和较高的频谱利用率而获赞无数，被广泛应用于长期演进（LTE）和无线保真（WIFI)等一系列国际主流标准当中[I]。然而现在迎来了5G 的变革时代，新通信场景面临的是海量连接，超低时延，高频谱利用率以及业务的多样化等一系列的高要求，OFDM技术已经不能够满足当前的通信需求，与此同时通用滤波多载波（UFMC）[2]作为5G的候选波形被提出。UFMC结合了OFDM和滤波器组多载波（FBMC)的技术特点，一方面在OFDM技术的基础之上，取消了循环前缀（CP），提高了符号的频谱利用率；另一方面采用了子带划分机制，使5G业务具有更强的灵活性，最后基于子带的滤波设计也降低了子带间干扰，与FBMC系统相比具有符号长度更短，系统复杂度更低的性能特点[3.4]。

UFMC系统受发送端和接收端晶体振荡器以及多普勒效应的影响而产生载波频率偏差(CFO)时，不仅会导致子带内载波问的干扰(ICI)和子带问的干扰(IBD[5]，子带内载波间的正交性遭到破坏，即使载波频率偏差很小，也会导致UFMC系统的性能急剧下降。因此如何有效减小UFMC系统CFO 带来的干扰已经成为该领域研究的热点。

目前，有关UFMC系统干扰消除的文献相对较少，为了对UFMC系统下的干扰抑制技术进行研究，就需对当前OFDM系统下的干扰抑制技术有整体的了解。文献[6]提出一种运用自适应滤波器的方法来消除OFDM系统中载波频偏引起的干ICI。通过调整自适应滤波器中的滤波系数来使误差达到最小，最后接收端得到输出信号。文献[7]借鉴了认知无线电系统中的主动干扰消除算法(AIC)，将改进的主动干扰消除的方法运用到UFMC系统中，减少了CFO带来的子带间干扰，但该方法实现复杂度较高。文献[8]中提到了ICI自消除算法，主要通过在邻位子载波调制相反数，利用相邻子载波干扰系数相似的原则进行干扰自消除，算法能有效消除ICI，但因为调制子载波占据了数据子载波的一半，导致频谱利用率降低了 $50 \%$ 。

本文针对ICI自消除算法(SC)频带利用率过低的问题，提出了一种部分自消除和加窗的联合改进方案。在新算法中对UFMC系统中的每个子带的边界设置一定比例的自消除子载波数目，通过边带子载波的干扰系数的相似性对系统进行初步干扰抑制，同时在接收端的FFT之前进行升余弦窗处理[9]，进一步抑制系统间的ICI。新方案在提升系统抗干扰性能同时提升原有自消除算法对系统频带利用率的损耗，同时方案实现过程简单有效。

# 1 系统模型

UFMC系统框图如图1所示， $N$ 个子载波被均分进 $N _ { _ B }$ 个子带中，UFMC中单个子带可以看成LTE系统中的物理资源块（PRB），单个子带中含有 $N _ { _ { B C } }$ 个连续的子载波。单个子带频域信号 $S _ { i }$ 通过 $\mathrm { ~  ~ N ~ }$ 点IDFT变换后转换成长度为 $\mathrm { ~  ~ N ~ }$ 的时域信号$s _ { i } ( n )$ ，其中，

$$
s _ { i } ( n ) = { \frac { 1 } { N } } \sum _ { k \in N _ { i } } S _ { i } ( k ) e ^ { j 2 \pi k n / N } , n = 0 , . . . , N - 1
$$

子带叠加符号 $x ( n )$ 可以表示成

$$
\begin{array} { l } { { \displaystyle x ( n ) = \sum _ { i = 1 } ^ { B } x _ { i } ( n ) } \ ~ } \\ { { \displaystyle ~ = \frac 1 N \sum _ { i = 1 } ^ { B } \sum _ { l = 0 } ^ { L - 1 } \sum _ { k = 0 } ^ { K _ { i } - 1 } S _ { i } ( k ) f _ { i } ( n - l ) e ^ { \ j _ { 2 } \pi k n } / N } } \end{array}
$$

假设信道中的归一化频率偏移为 $\varepsilon$ ，经过高斯白噪声信道后，接收信号可以表示为

$$
\begin{array} { l } { { \displaystyle y ( n ) = x ( n ) e ^ { j 2 \pi \varepsilon n / N } + w ( n ) } } \\ { { \displaystyle \quad = \frac { 1 } { N } \sum _ { i = 1 } ^ { B } \sum _ { l = 0 } ^ { L - 1 } \sum _ { k = 0 } ^ { K _ { i } - 1 } S _ { i } ( k ) f _ { i } ( n - l ) \cdot } } \\ { { \displaystyle e ^ { j 2 \pi k n / N } e ^ { j 2 \pi \varepsilon n / N } + w ( n ) } } \end{array}
$$

在接收端信号经过 $2 N$ 点FFT变化之后表达式为

$$
\begin{array} { l } { { \displaystyle y ( m ) = \sum _ { n = 0 } ^ { N + L - 2 } y ( n ) e ^ { - j 2 \pi n m / 2 N } } } \\ { { \displaystyle \ = [ \sum _ { i = 1 } ^ { B } \sum _ { k = 1 } ^ { K _ { i } } S _ { i } ( k ) ] I ( k - m ) + W ( m ) } } \end{array}
$$

其中，载波间干扰系数 $I ( k - m )$ 为：

$$
I ( k - m ) = { \frac { 1 } { N } } \sum _ { n = 0 } ^ { N + L - 2 } \sum _ { L = 0 } ^ { L - 1 } f _ { i } \left( n - l \right) e ^ { j 2 \pi k n / N } .
$$

从式(6)中可以看出系统的ICI是由归一化频偏 $\varepsilon$ 带来的，且随着 $\varepsilon$ 的增大而增大。为了详细分析ICI给系统带来的干扰，将载波干扰比CIR作为衡量指标，CIR的计算公式为

$$
C I R = \frac { E [ \vert C ( m ) ^ { 2 } \vert ] } { E [ \vert I ( m ) ^ { 2 } \vert ] } = \frac { E [ \vert I ( 0 ) \vert ^ { 2 } ] } { E [ \sum _ { i = 1 } ^ { B } \sum _ { k = 0 } ^ { K _ { i } - 1 } I ( k ) \vert ^ { 2 } ] }
$$

从式(7)可以看出随着CFO的增大，CIR减小。消除CFO对UFMC系统带来的载波间干扰意义重大。

其中： $N _ { _ i }$ 是非空集，包含UFMC 符号中的子带 $i$ 。子带滤波后的输出信号 $x _ { i } ( n )$ 为FIR滤波器 $f _ { i }$ 和时域信号 $s _ { i }$ 的离散线性卷积:

$$
x _ { i } ( n ) = s _ { i } ( n ) * f _ { i } ( n )
$$

其中，表示 $*$ 卷积操作符。

![](images/aef6a8f8c2f17766f91cb333180965adf1b7c71771fe1e77f034854abb2d820b.jpg)  
图1UFMC系统框图

# 2 ICI自消除方案

自消除(SC)算法是一种传统的消除载波间干扰的算法，早期应用于OFDM系统中。本小节将SC算法应用于UFMC。在UFMC系统中，从式(6)中可以看出每个子带内的相邻子载波受到其他子载波带来的干扰大小差距很小，所以在相邻子载波调制相反数可以抵消大部分来自相邻子载波的干扰，同时来自其他子载波的干扰也由于相反数的调制关系而被削弱。下面对算法进行详细介绍。

在UFMC系统发射端，将原始数据及其相反数分别调制到对应子带内相邻的子载波上，其中在子带 $i$ 中的数据调制关系为$S _ { i } ( 1 ) = - S _ { i } ( 0 ) , S _ { i } ( 3 ) = - S _ { i } ( 2 ) , . . . , S _ { i } ( N _ { \scriptscriptstyle B C } - 1 ) =$ $- S _ { i } ( N _ { B C } - 2 )$ 。其中： $N _ { _ { B C } }$ 为单个子带内子载波的数目。

经过信道后，系统受到的归一化频偏大小为 $\varepsilon$ ，在接收端信号第 $m$ 个子载波经过 $2 N$ 点FFT变化之后表达式为

$$
\begin{array} { l } { { \displaystyle y ( m ) = \sum _ { n = 0 } ^ { N + L - 2 } y ( n ) e ^ { - j 2 \pi n m / 2 N } } } \\ { { \displaystyle \ = [ \sum _ { i = 1 } ^ { B } \sum _ { k = 0 } ^ { K _ { i } } S _ { i } ( k ) ] [ I ( k - m ) - } } \end{array}
$$

$$
I ( k { + } 1 { - } m ) ] { + } W ( m )
$$

则第 $m + 1$ 个子载波上的接收符号表达式为

$$
y ( m + 1 ) = [ \sum _ { \stackrel { i = 1 } { k = e \nu e n } } ^ { B } \sum _ { \stackrel { k } { m = 0 } } ^ { K _ { i } } S _ { i } ( k ) ] [ I ( k - m - 1 ) -
$$

$$
I ( k - m ) ] + W ( m + 1 )
$$

自消除调制后UFMC系统的ICI系数为

$$
\overset { \cdot } { I ^ { ' } } ( k { - } m ) = I ( k { - } m ) { - } I ( k { + } 1 { - } m )
$$

在接收端，为了进一步减小ICI，将经过自消除解调，即在接收端将第 $m$ 个子载波的接收符号与第 $m + 1$ 个子载波的接收符号进行相减，所以得到的最终符号为

$$
\begin{array} { l } { { \displaystyle y ^ { * } ( m ) = y ( m ) - y ( m + 1 ) } } \\ { { \displaystyle \quad = [ \sum _ { i = 1 } ^ { B } \sum _ { k = 0 \atop k \neq v e n } ^ { K _ { i } } S _ { i } ( k ) ] [ - I ( k - m - 1 ) + } } \\ { { \displaystyle \quad \quad 2 I ( k - m ) - I ( k - m - 1 ) ] + } } \\ { { \displaystyle W ( m ) - W ( m + 1 ) } } \end{array}
$$

经过自消除解调过程后，ICI系数得到了进一步的衰减，系数表达式如下所示：

$$
\begin{array} { c } { { \dot { I ^ { * } } ( k - m ) = - I ( k - m - 1 ) + } } \\ { { 2 I ( k - m ) - I ( k - m - 1 ) } } \end{array}
$$

解调后的系统载波干扰比（CIR）数学表达式为(下列CIR为每个子带中0子载波对应表达式)

$$
\begin{array} { l } { \displaystyle C I R = \frac { E [ | C ( m ) ^ { 2 } | ] } { E [ | I ( m ) ^ { 2 } | ] } } \\ { \displaystyle = \frac { \left| - I ( - 1 ) + 2 I ( 0 ) - I ( 1 ) \right| ^ { 2 } } { E [ \displaystyle \sum _ { i = 1 } ^ { B } \sum _ { k = 0 \atop k = \mathrm { v e n } } ^ { K _ { i } - 1 } | - I ( k - 1 ) + 2 I ( k ) - I ( k + 1 ) | ^ { 2 } ] } } \end{array}
$$

# 3 部分自消除加窗方案

为了解决传统SC算法降低系统频带利用率的问题，同时又不减弱系统的抗干扰性能，提出部分自消除加窗方案，对于改进方案下文统一称为"UFMC-PSC加窗系统”。

传统自消除算法频带利用率只有 $50 \%$ 。UFMC系统中子载波按子带为单位进行分组，考虑到子带间干扰由子带边界向子带内部逐渐减小，通过在子带两侧按比例使用自消除子载波，即只对子带边带的部分子载波相邻位置调制相反数，可以有效提升系统频带利用率，改进方法称为部分自消除（PSC)算法。

但是在减小自消除子载波比例的同时，也减小了UFMC系统抗干扰能力。为了提升系统抗干扰性能，在系统的接收端对信号进行2N点傅里叶变换(FFT)前，对信号进行升余弦加窗处理，信号时域加窗后，子载波的带外衰减(OOB)得到了有效抑制，从而减小了UFMC系统ICI。下面对改进方案进行详细介绍。

首先，在UFMC系统发射端对数据进行调制，因为这里是采用部分自消除算法，所以只需对子带两侧的子载波采用邻位取反的方式调制数据。假设子带每侧的自消除子载波只有两个，每个子带中的数据调制关系如下所示：

$$
S _ { i } \left( 1 \right) = - S _ { i } \left( 0 \right) , S _ { i } \left( 3 \right) = - S _ { i } \left( 2 \right) , S _ { i } \left( 4 \right) , . . . , S _ { i } \left( N _ { B C } - 3 \right) , S _ { i } \left( N _ { B C } - 1 \right) =
$$

$$
- S _ { i } \left( N _ { B C } - 2 \right) \circ
$$

在接收端的接收信号为 $y ( n )$ ，在FFT之前需要对信号进行加窗处理，升余弦窗函数 $p ( n )$ 的数学表达式如下所示：

$$
p ( n ) = \left\{ \begin{array} { l l } { \displaystyle 0 . 5 \times \left[ 1 - \cos \frac { n \pi } { 0 . 5 L - 1 } \right] , ~ n \in [ 0 , 0 . 5 L - 1 ] } \\ { \displaystyle 1 , ~ n \in \left[ 0 . 5 L , 0 . 5 L + N \right] } \\ { \displaystyle 0 . 5 \times \left[ 1 + \cos \left( \frac { n - N - 0 . 5 L + 1 } { 0 . 5 L - 1 } \pi \right) \right] , } \\ { \displaystyle n \in \left[ 0 . 5 L + N + 1 , N + L + 1 \right] } \end{array} \right.
$$

在接收端，对时域信号乘以窗函数，叠加了窗函数的的时域信号表达式如下所示：

$$
\begin{array} { l } { { \displaystyle y ( n ) = [ x ( n ) e ^ { j 2 \pi \varepsilon n / N } + w ( n ) ] p ( n ) } } \\ { { \displaystyle \qquad = \frac { 1 } { N } \sum _ { i = 1 } ^ { B } \sum _ { l = 0 } ^ { L - 1 } \sum _ { k = 0 } ^ { K _ { i } - 1 } S _ { i } ( k ) f _ { i } ( n - l ) p ( n ) \cdot } } \\ { { \displaystyle e ^ { j 2 \pi k n / N } e ^ { j 2 \pi \varepsilon n / N } + w ( n ) p ( n ) } } \end{array}
$$

经过FFT变换后，系统的干扰系数表达式如下所示：

$$
\overset { \cdot } { I ^ { ' } } ( k - m ) = \left\{ \begin{array} { l l } { \overset { } { I } ( k - m ) - \overset { } { I } ( k + 1 - m ) , k \in \{ 0 , 2 , N _ { _ { B C } } - 4 , N _ { _ { B C } } - 2 \} } \\ { \overset { } { I } ( k - m ) , \qquad \overset { } { k } \in [ 3 , N _ { _ { B C } } - 5 ] } \end{array} \right.
$$

其中，载波干扰系数表达式为

$$
I ( k - m ) = \frac { 1 } { N } \sum _ { n = 0 } ^ { N + L - 2 } \sum _ { L = 0 } ^ { L - 1 } f _ { i } ( n - l ) p ( n ) \cdot
$$

从式(14)中可以看出，窗函数的幅值小于1，所以加窗后的ICI系数相较于加窗前得到了降低，即载波间的ICI功率得到了有效的抑制。经过FFT变换后需要要对UFMC进行自消除解调操作，此时只需要对UFMC符号中每个子带的两侧的已调子载波进行解调。则解调后的信号表达式如下所示：

$$
y ^ { \prime } ( n ) = \left\{ \begin{array} { c } { y ( n ) - y ( n + 1 ) , } \\ { \qquad k \in \{ 0 , 2 , N _ { B C } - 4 , N _ { B C } - 2 \} } \\ { y ( n ) , \ k \in [ 3 , N _ { B C } - 5 ] } \end{array} \right.
$$

解调后的UFMC载波干扰系数表达式如下所示：

$$
\bar { I ^ { * } } ( k - m ) = \left\{ \begin{array} { l l } { - I ( { \bf k } - m - 1 ) + 2 I ( k - m ) - } \\ { I ( k - m - 1 ) , } \\ { \quad k \in \{ 0 , 2 , N _ { _ { B C } } - 4 , N _ { _ { B C } } - 2 \} } \\ { I ( k - m ) , } \\ { \quad k \in [ 3 , N _ { _ { B C } } - 5 ] } \end{array} \right.
$$

经过PSC加窗解调模块,系统的载波干扰比的表达式为(下列CIR为每个子带中0子载波对应表达式)：

$$
\begin{array} { r l } { C T R ^ { \prime } = } & { \left\{ \frac { \displaystyle \left[ - I ( - 1 ) + 2 I ( 0 ) - I ( 1 ) \right] ^ { 2 } } { \displaystyle E [ \sum _ { i = 1 } ^ { n } \sum _ { k = 0 } ^ { K - 1 } | - I ( k - 1 ) + 2 I ( k ) - I ( k + 1 ) | ^ { 2 } ] } , \right. } \\ { K ^ { \prime } = } & { \left\{ \begin{array} { l l } { \displaystyle \sum _ { k = 0 } ^ { I } \sum _ { N _ { B C } } - 4 , N _ { B C } - 2 | } \\ { \displaystyle \frac { E [ | I ( 0 ) | ^ { 2 } ] } { E [ \sum _ { i = 1 } ^ { N _ { K } - 1 } ] ^ { I ( k ) } } , } \end{array} \right. } \\ & { } \end{array}
$$

采用PSC加窗方案后，不同位置子载波的载波干扰比有了明显的差异，为了能够正确评价系统抗干扰水平，故计算系统的平均载波干扰比 $\overline { { C I R } }$ ，计算表达式如下所示：

$$
\overline { { C I R } } ^ { \ast } { = } \frac { 1 } { K _ { i } } { \sum _ { k = 1 } ^ { K _ { i } } } C I R _ { k } ^ { \ast }
$$

当系统采用的自消除子载波比例越高时，需要解调的子载波数就越多，平均载波干扰比也就越大，系统的抗干扰性越强，通过灵活设置自消除子载波的个数可以控制系统的性能。通过对系统的平均载波干扰比进行分析，可以对系统的性能做出判断。从而制定优化方案。PSC加窗系统框图如图2所示。

![](images/b704e6d57490cbd2ffe3f7b5650984c31dff421682282774fab3323211982392.jpg)  
图2PSC加窗系统框图  
图3不同算法平均CIR 性能

如图所示，在UFMC系统发射端，首先对每个子带内的子载波进行部分自消除调制，再进行傅里叶逆变换(IFFT)及串并转换等信号处理过程后，得到时域UFMC发射信号。接收端，首先对时域符号进行升余弦窗处理，然后再对信号进行傅里FFT、均衡等其他信号处理，最后对符号进行部分自消除解调处理，还原得到调制子载波上的原始信号。

# 4 仿真及结果分析

为了验证SC算法以及PSC加窗优化方案对UFMC系统干扰抑制的性能，需要对其进行仿真分析。仿真过程中需要对PSC加窗系统中的自消除子载波占比进行设定，其中在UFMC-PSC1加窗系统中每个子带两侧的用于自消除的子载波为2个，UFMC-PSC2加窗系统中每个子带两侧的用于自消除的子载波为4个（当参数为5个时表示子带中所有子载波都使用自消除算法）。仿真参数设置如表1所示。

表1系统仿真参数  

<html><body><table><tr><td>仿真参数</td><td>参数值</td></tr><tr><td>IFFT点数</td><td>512</td></tr><tr><td>子带数</td><td>10</td></tr><tr><td>子载波数/子带</td><td>20</td></tr><tr><td>滤波器类型</td><td>Chebyshev Filter</td></tr><tr><td>滤波器长度</td><td>29</td></tr><tr><td>滤波器衰减系数</td><td>40dB</td></tr><tr><td>调制方式</td><td>QPSK</td></tr><tr><td>信道模型</td><td>AWGN</td></tr><tr><td>窗函数类型</td><td>升余弦窗（RC）</td></tr></table></body></html>

图3是SNR为20dB时，各个系统之间的平均CIR性能仿真图。从图中可以直观地看出平均CIR随着归一化频偏的增大而减小，并且下降的速率越来越小，说明当归一化频偏增大时，系统受到的干扰影响越严重，即载波干扰比越小，产生"地板效应”。从图中可以看出UFMC-SC加窗系统的平均载波干扰比性能最好，未加任何算法的UFMC系统平均CIR性能最差。其中使用了加窗系统的UFMC-SC系统在归一化频偏为0.01时达到了80dB的幅度，即使在归一化频偏达到0.3时，载干比仍接近40dB。UFMC-PSC1加窗系统次之，但平均CIR性能相较于UFMC系统都得到了明显的提升。结果证明部分UFMC-PSC2加窗系统的平均CIR性能优于自消除算法，但是UFMC-PSC2加窗系统性能要低于UFMC-SC加窗系统，说明当自消除子载波的比例下降时，系统的性能受到抑制。

80 O—UFMC X 一UFMC-PSC1加窗 （ & ☆—UFMC-SC 双 △—UFMC-PSC2加窗 60 X 中 UFMC-SC加窗 1 △ 改 A 茶 1 □ △△△△D 000: 40 □ 00000 Q & 20 0 0 0.05 0.1 0.15 0.2 0.25 0.3 归一化频偏

图4为载波频率偏移为0.1的时候，SC算法及其改进算法的误比特性能对比分析。通过图中的分析可知，基本上性能的排序和图3一致，从图中可以看出自消除算法极大地提升了UFMC系统的误比特性能，加窗过程对系统的性能也有很大的提升，自消除子载波占比对系统的影响较大，PSC2加窗系统性能优于PSC1加窗系统。

其中在频带利用率上，UFMC-SC系统对所有数据都采用自消除调制，频带利用率为 $50 \%$ 。在UFMC-PSC1加窗系统中，每个子带中不传递有效数据的子载波为 $2 ^ { * } 2 { = } 4$ 个，所以频带利用率为 $1 6 / 2 0 { = } 8 0 \%$ ，而在UFMC-PSC2加窗系统中，每个子带中不传递有效数据的子载波为 $4 ^ { * } 2 { = } 8$ 个，频带利用率为$12 / 2 0 { = } 6 0 \%$ ，在UFMC-SC系统的基础上提升了 $10 \%$ 的幅度。

![](images/77188f15110c4d43667353e2052ba4a3e30e6f4397e7e3d99050207a8326d5cc.jpg)  
图4 不同算法BER性能

# 5 结束语

本文分析了UFMC系统中对于载波频率偏移而导致的子载波间干扰，进而研究UFMC系统下的ICI自消除算法对系统的抗干扰能力的提升，针对算法频带利用率过低的问题，基于UFMC系统特性，本文提出一种部分自消除和加窗的联合优化方案，通过对子带边界的设置自消除子载波，同时在接收端FFT前进行加窗处理。仿真结果表明，优化方案可以保持UFMC系统传输性能并有效提高系统的频带利用率，算法实现方式简单有效，同时可以根据实际的通讯需求灵活设置自消除子载波的个数，算法具有可变通性，具有一定的实际应用前景。尽管如此，该方法只考虑了升余弦窗的对系统抗干扰能力的影响，在后续工作中可以进一步研究不同窗函数对系统性能的影响。

# 参考文献：

[1]Chen Xiaoming,WolfgangA,Zaidi A.CP-OFDM and UF-OFDM in the

presence of phase noises and their mitigations [C]// Proc of Vehicular Technology Conference. Canada: IEEE Press,2017:1-6.   
[2]Gupta A,Jha R K.A survey of 5G network:architecture and emerging technologies [J].IEEE Access,2015,3:1206-1232.   
[3]Debels E,Fiorentino PD, Vitiello C,et al. Adaptive modulation and coding for BIC-UFMC and BIC-OFDM systems taking CFO into account [C]// Communications and Vehicular Technologies.Mons,Belgium: IEEE Press, 2016: 1-5.   
[4]Zhang Zhaoyang,Wang Hong,Yu Guanding,et al.Universal filtered multicarrier transmission with adaptive active interference cancellation [J].IEEE Trans on Communications,2017,PP(99): 1.   
[5]Duan Sirui，Yu Xiang,Wang Rong.performance analysis on filter parameters and sub-bands distribution of universal filtered multi-carrier [J]. Wireless Personal Communications,2017,95 (3):1-17.   
[6]Khedkar A R,Murugan M M. Trained adaptive filter based approach to mitigate ICI in OFDM system[C]//Proc of International Conference on Pervasive Computing.Pune,India: IEEE Press,2015:1-4.   
[7]Wang Hong, Zhang Zhaoyang, Zhang Yu,et al. Universal filtered multicarrier transmission with active interference cancellation [C]// IEEE Wireless Communications & Signal Processing.Nanjing, China: IEEE Press, 2015: 1-6.   
[8]Singh P, O.P. S.An overview of ICI self cancellation techniques in OFDM systems [C]//Proc of IEEE International Conference on Computational Intelligence & Communication Technology. Ghaziabad,India: IEEE Press, 2015: 299-302.   
[9]Schaich F,Wild T.Relaxed synchronization support of universal filtered multi-carrier including autonomoustiming advance [C]// Procof International Symposium on Wireless Communications Systems.Boston: IEEE,2014:203-208.