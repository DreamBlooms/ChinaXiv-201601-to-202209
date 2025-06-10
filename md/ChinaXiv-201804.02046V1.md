# 基于循环自相关的NC-OFDM信号参数的盲估计‘

王胜，张天骐，袁帅(重庆邮电大学 信号与信息处理重庆市重点实验室，重庆 400065)

摘要：在认知无线电(CR)环境中，频率资源不足的问题越来越严重，非连续正交频分复用（NC-OFDM）能够工作在非连续的频谱环境，针对NC-OFDM信号的参数估计重要问题，提出用循环自相关的方法。该方法首先分析循环平稳信号特点，然后根据NC-OFDM信号的循环自相关在循环频率 $\scriptstyle a$ 以及时延T切面图具有离散谱线特征进行参数估计，最后对NC-OFDM信号的循环自相关进行数值仿真。仿真结果表明在低信噪比下，能有效估计NC-OFDM信号的参数及识别零前缀的正交频分复用信号（ZP-OFDM)，且实验证明关闭近 $90 \%$ 的子载波数目，都能够实现NC-OFDM信号的参数的盲估计。

关键词：非连续正交频分复用；认知无线电；循环自相关；参数盲估计；零前缀的正交频分复用 中图分类号：TN911.7 doi: 10.3969/j.issn.1001-3695.2017.11.0749

# Parameter blind estimation based on cyclic autocorrelation of NC-OFDM signals

Wang Sheng, Zhang Tianqi, Yuan Shuai (Chongqing KeyLaboratory of Signal& Information Processing,Chongqing Universityof Posts &Telecommunications, Chongqing 400065, China)

Abstract:Inthecognitiveradio(CR)environment,theproblemofinsuficientfrequencyresources gets severe,non-contiuous orthogonal frequency division multiplexing(NC-OFDM)can work in thenon-continuous spectral environment,this paper proposedcyclicautocorrelation methodtodeal withtheimportant problemofparameter estimationofNC-OFDMsignals.Firstly, analysis thecharacteristicsofcyclostationaryof signals.Thenaccording tothecyclicautocorelationoftheNC-OFDMsignal, the parameters are estimated with the characteristics of the discrete spectral lines in the cyclic frequency $a$ and the time delay Tcutaway.Finally,this paper simulate thecyclic autocorelationofthe NC-OFDM signals.The simulationresults show that theparametersofNC-OFDM signalcanbeeffectively estimatedandrecognized zero-prefixorthogonal frequency division multiplexing signals(ZP-OFDM) at low signal-to-noise ratio,and the experiments show that close to $90 \%$ of the number of subcarriers,can achieve NC-OFDM signals parameter blind estimation.

Key words:non-continuous orthogonal frequency division multiplexing (NC-OFDM)；cognitive radio(CR)；cyclic autocorrelation; parameter blind estimation; ZP-OFDM

# 0 引言

近年来，无线通信的迅猛发展，可分配的频谱资源非常匮乏，且根据美国联邦通信委员会(FCC)的研究报告指明，已被分配频段的平均利用效率比较低，在 $1 5 \% { \sim } 8 5 \%$ 范围之间。针对频谱利用效率不高的问题，CR提出一种将授权用户占用的子载波传输0'数据的信号。NC-OFDM信号是CR物理层主要的数据传输方式，其在OFDM信号的基础上将不可用的子载波作置零处理，关闭授权用户占用的子载波，感知用户在剩余的非连续频谱上进行传输信号。NC-OFDM信号的特点成为CR的关键技术。

NC-OFDM信号不仅包含OFDM信号的各项优点，而且相比于OFDM信号还具有以下优势：a)NC-OFDM信号可以灵活利用所有未被占用的频谱资源，从而提高了频谱的利用率；b)NC-OFDM信号形成利用FFT运算降低了计算量；c)在产生NC-OFDM信号中，可以“伺意”将被授权用户占用的子载波进行置零处理形成非连续的信号，不仅可以提高系统的BER性能，而且可以减少频谱的发送功率和抑制窄带干扰，此子载波置零处理的好处是在数据传输时，感知用户不会对授权用户形成干扰，实现感知用户与授权用户的在一段连续的频谱上彼此互不干扰抑制；d)之前的无线通信系统必需要工作在一段连续的频谱的局面，被NC-OFDM信号通信系统打破了，这为快速发展的今天的高速数据传输业务提供了可能。因此研究分析NC-OFDM信号的参数特征在CR中具有重要意义。

目前文献对NC-OFDM参数估计的文献很少，主要研究集中在NC-OFDM信道估计，导频设计，抗干扰或者降低峰均比技术研究等[2-6]。文献[1]利用OFDM信号的循环平稳特性，对OFDM信号的载波频偏进行参数的盲估计；文献[7]基于CR系统中存在许多"0"输入信号这一事实，提出了一种适用于NC-OFDM的低功耗FFT设计方法；文献[8]提出了一种NC-OFDM系统的带内干扰鲁棒同步算法；文献[9]提出一种基于低复杂度的矩阵束方法的OFDM 信号超分辨率 TOA/AOA 二维定位方法；文献[10]和[11]证明了OFDM信号自相关函数为时间 $t$ 的周期函数，并且利用二阶循环平稳性对OFDM信号进行了多个参数的盲估计；文献[12]利用循环自相关算法对OFDM信号与单载波信号的进行调制识别并提出了一种基于小波分解的单载波信号识别方法；文献[13]针对NC-OFDM信统提出了多种群自适应免疫优化子载波分配算法，达到加快收敛速度的同时避免陷入局部最优的目的。本文利用循环自相关算法对NC-OFDM信号的符号周期 $T _ { s }$ 、有用符号周期 $T _ { \phantom { } _ { u } }$ 及循环前缀长度 $T _ { g }$ 多个参数进行盲估计，并实验仿真出NC-OFDM信号的循环自相关的三维图以及参数估计的性能图，实验仿真结果表明，在低信噪比条件下，能有效实现对NC-OFDM信号多个参数的盲估计。

# 1 NC-OFDM信号模型

NC-OFDM是OFDM的一种特殊形式，是基于CR的OFDM。NC-OFDM信号能够非常灵活的利用频谱资源，只利用未被授权用户占用的子载波进行数据传输，通过将被占用的子载波关闭，具体实验是将被占用的子载波作置零处理，形成子载波非连续的OFDM[13]。

![](images/392d74ddf6eddc9614b0b7e8c0875ee4349b96afb07b4cda9c8d1ebf8e93b685.jpg)  
图1NC-OFDM信号的发射端原理

由图1可知NC-OFDM基带信号的表达式

$$
s \big ( t \big ) = \sum _ { k } \sum _ { n = 0 } ^ { N - 1 } d _ { n , k } p ( t - k T _ { s } ) \cdot e ^ { j 2 \pi n \Delta f ( t - k T _ { s } ) } , n \neq \tilde { K }
$$

设 $i \in \left\{ 1 , 2 , . . . N - 1 \right\}$ 且若第 $i$ 个子载波为被授权用户占用的，则式(1)中 $\tilde { K }$ 为所有 $i$ 的取值集合，即表示被授权用户占用的子载波下标的集合； $N$ 为子载波数目； $p ( t )$ 为成型脉冲且其宽度为一个符号周期； $T _ { s } = T _ { u } + T _ { g }$ 为 NC-OFDM的数据符号周期，其中 $T _ { u }$ 为有用数据符号时间， $T _ { g }$ 为循环前缀时间间隔或保护时间间隔； $\Delta f$ 为子载波频率间隔，且 $\Delta f = 1 / T _ { u }$ ；调制方式采用QAM调制， $d _ { n , k }$ 表示第 $n$ 个子载波上的第 $k$ 个调制符号，且 $d _ { n , k }$ 相互独立同分布，均值为0，方差为 $\sigma _ { d } ^ { 2 }$ ，是非周期的齐次马尔科夫链，因此有此特点： $E ( d _ { n , k } ) = 0 \ , \ E ( d _ { n , k } ^ { * } ) = 0 \ , \ E ( d _ { n , k } d _ { m , l } ) = 0$ E(dn,kdm,)=o²δ[n-m]S[k-l]，δ为克罗内克函数[10]。

# 2 循环平稳信号分析

复信号 $x ( t )$ 的自相关函数为

$$
R _ { x } \left( t , \tau \right) = E { \bigg [ } x { \Big ( } t + \tau { \Big / } _ { 2 } { \Big ) } x ^ { * } \left( t - \tau { \Big / } _ { 2 } \right) { \bigg ] }
$$

若 $R _ { x } \left( t , \tau \right) = R _ { x } \left( t + T , \tau \right)$ 成立，则 $x ( t )$ 的自相关函数是时间$t$ 的周期函数且其周期为 $T$ ，称 $x ( t )$ 是二阶循环平稳信号[10]( $E$ 表示求期望， $*$ 表示取共轭， $\tau$ 表示时延)。所以能将 $x ( t )$ 的自相关函数展开成傅里叶级数：

$$
R _ { x } \big ( t , \tau \big ) = \sum _ { \alpha } R _ { x } ^ { \alpha } \big ( \tau \big ) e ^ { j 2 \pi \alpha t }
$$

$$
R _ { x } ^ { \alpha } ( \tau ) = \operatorname* { l i m } _ { T  \infty } \frac { 1 } { T } \int _ { - T _ { 2 } } ^ { T _ { 2 } } R _ { x } ( t , \tau ) e ^ { - j 2 \pi \alpha t } d t
$$

其中: $R _ { x } ^ { \alpha } \left( \tau \right)$ 即为 $x ( t )$ 的循环自相关函数。式(3)中 $\alpha$ 为循环频率，当 $\alpha = 0$ 时 $R _ { x } ^ { 0 } ( \tau )$ 即是传统的自相关函数。本文是利用循环自相关算法对NC-OFDM信号进行多个参数的盲估计以及识别ZP-OFDM信号。

# 3 NC-OFDM信号循环自相关分析

NC-OFDM基带信号表达式为

$$
s \left( t \right) = \sum _ { k } \sum _ { n = 0 } ^ { N - 1 } d _ { n , k } p ( t - k T _ { s } ) e ^ { j 2 \pi n \Delta f \left( t - k T _ { s } \right) } , n \neq \tilde { K }
$$

复基带信号表达式为

$$
r ( t ) = s ( t - t _ { 0 } ) e ^ { j 2 \pi f _ { 0 } t } + n ( t )
$$

式(6)中： $t _ { 0 }$ 为初始时延； $f _ { 0 }$ 为频偏； $n \big ( t \big )$ 为平稳噪声且与$s ( t )$ 相互独立。可得其自相关函数：

$$
R _ { r } ( t , \tau ) = E [ r ( t ) r ^ { * } ( t - \tau ) ]
$$

将式(6)代入式(7)中得

$$
\begin{array} { c } { { R _ { r } \big ( t , \tau \big ) = \displaystyle \sum _ { k , l } \sum _ { n , m = 0 } ^ { N - 1 } E \big \{ { d _ { n , k } d } ^ { * } _ { m , l } \big \} p \big ( t - t _ { 0 } - k T _ { s } \big ) \cdot } } \\ { { p ^ { * } \big ( t - t _ { 0 } - l T _ { s } - \tau \big ) \mathrm { e x p } \big \{ j 2 \pi \big [ \big ( n \Delta f + f _ { 0 } \big ) \cdot } }  \\ { { \big ( t - t _ { 0 } - k T _ { s } \big ) \big ] \big \} \mathrm { e x p } \Big \{ - j 2 \pi \big [ \big ( m \Delta f + f _ { 0 } \big ) \cdot } } \\ { { \big ( t - t _ { 0 } - l T _ { s } - \tau \big ) \big ] \big \} + R _ { n } \big ( \tau \big ) , n \neq \tilde { K } \& m \neq \tilde { K } } } \end{array}
$$

式(8)中 $R _ { n } \left( \tau \right) = E { \left[ n \left( t \right) n ^ { * } \left( t - \tau \right) \right] }$ ；由于 $n ( t )$ 是平稳随机过程，即 $R _ { n } ( \tau )$ 与时间变量 $\mathbf { \chi } _ { t } ^ { }$ 无关，只和时延 $\tau$ 有关。由$E \big \{ d _ { n , k } ^ { } d _ { \phantom { } _ { m , l } } ^ { * } \big \} = \sigma _ { d } ^ { 2 } \delta \big [ n - m \big ] \delta \big [ k - l \big ]$ ，所以式(8)可写为

$$
\begin{array} { r } { R _ { \boldsymbol { r } } \left( t , \tau \right) = \sigma _ { d } ^ { 2 } \underset { k } { \sum } \underset { n = 0 } { \sum } p \left( t - t _ { 0 } - k T _ { s } \right) \cdot p ^ { * } \left( t - t _ { 0 } - \right. } \\ { \left. k T _ { s } - \tau \right) e ^ { j 2 \pi \left( n \Delta f + f _ { 0 } \right) \tau } + R _ { n } \left( \tau \right) , n \neq \tilde { K } } \end{array}
$$

对式(9)整理为下式

$$
\begin{array} { c } { { R _ { _ r } \big ( t , \tau \big ) = \sigma _ { d } ^ { 2 } e ^ { j 2 \pi f _ { 0 } \tau } { \displaystyle \sum _ { n = 0 } ^ { N - 1 } } e ^ { j 2 \pi \tau n \Delta f } \displaystyle \sum _ { k } p \big ( t - t _ { 0 } - k T _ { s } \big ) \cdot } } \\ { { p ^ { \ast } \big ( t - t _ { 0 } - k T _ { s } - \tau \big ) + R _ { _ n } \big ( \tau \big ) , n \neq \tilde { K } } } \end{array}
$$

由式（10）可推得

$$
\begin{array} { c } { { R _ { _ { r } } \big ( t + T _ { s } , \tau \big ) = \sigma _ { _ d } ^ { 2 } e ^ { j 2 \pi f _ { 0 } \tau } { \displaystyle \sum _ { n = 0 } ^ { N - 1 } } e ^ { j 2 \pi \tau n \Delta f } \sum _ { k } p \big ( t - t _ { 0 } - } } \\ { { k T _ { s } + T _ { s } \big ) p ^ { * } \big ( t - t _ { 0 } - k T _ { s } - \tau + T _ { s } \big ) + R _ { _ n } \big ( \tau \big ) , n \not = \tilde { K } } } \end{array}
$$

令

$$
\Phi _ { _ { N } } \left( \tau \right) = \sum _ { n = 0 } ^ { N - 1 } e ^ { j 2 \pi \tau n \Delta f }
$$

经比较式(10)与(11)式可知

$$
R _ { r } \left( t , \tau \right) = R _ { r } \left( t + T _ { s } , \tau \right)
$$

可知 $r ( t )$ 的自相关函数是时间 $t$ 的周期函数且周期为 $T _ { s }$ ，在此还不能证明 $r ( t )$ 是二阶循环平稳信号，还需分析式 $\Phi _ { \scriptscriptstyle N } ( \tau )$ 的性质。由其表达式可知，当 $\tau$ 为 $T _ { \phantom { } _ { u } }$ 整数倍时，其值不为零。由 $p ( t )$ 是成型脉冲，根据其特点，当 $0 \leq \vert \tau \vert \leq T _ { s }$ 时，当且仅当 $\tau$ 取 $0 , \pm T _ { u }$ 时，使 $R _ { r } \big ( t , \tau \big )$ 值不为零。

在NC-OFDM信号无循环前缀情况下，有 $T _ { s } = T _ { u }$ ，可知在确定的 $\tau$ 值情况下 $R _ { r } \left( t , \tau \right)$ 值不随 $t$ 改变；在NC-OFDM信号有循环前缀情况下，有 $T _ { s } > T _ { u }$ 且 $T _ { s } = T _ { u } + T _ { g }$ ，可知在确定的 $\tau$ 值情况下 $R _ { r } \big ( t , \tau \big )$ 值随着 $t$ 的改变而改变，且其周期为 $T _ { s }$ 。这就证明了带有循环前缀的NC-OFDM是二阶循环平稳信号。

由循环自相关的定义可得

$$
\begin{array} { l } { \displaystyle R _ { r } ^ { \alpha } \left( \tau \right) = \frac { 1 } { T _ { s } } \int _ { 0 } ^ { T _ { s } } R _ { r } \left( t , \tau \right) e ^ { - j 2 \pi \alpha t } d t } \\ { \displaystyle = \frac { \sigma _ { d } ^ { 2 } } { T _ { s } } \Phi _ { N } \left( \tau \right) e ^ { j 2 \pi f _ { 0 } \tau } \int _ { 0 } ^ { T _ { s } } \sum _ { k } p \left( t - t _ { 0 } - k T _ { s } + T _ { s } \right) \cdot } \\ { \displaystyle p ^ { * } \left( t - t _ { 0 } - k T _ { s } - \tau + T _ { s } \right) d t + R _ { n } ^ { \alpha } \left( \tau \right) , n \neq \tilde { K } } \end{array}
$$

式(14)中 $\alpha = m / T _ { s }$ ，当 $\alpha$ 取其他值时， $R _ { r } ^ { \alpha } ( \tau )$ 为零。上式的$R _ { n } ^ { \alpha } \left( \tau \right)$ 仅当 $\alpha = 0 , \tau = 0$ 时有值。先忽略噪声 $n ( t )$ 的影响，令$\tilde { t } = t - t _ { 0 } - k T _ { s }$ ，可得

$$
R _ { r } ^ { \alpha } \left( \tau \right) = \frac { \sigma _ { d } ^ { 2 } } { T _ { s } } \Phi _ { N } \left( \tau \right) e ^ { j 2 \pi f _ { 0 } \tau } e ^ { - j 2 \pi \alpha t _ { 0 } } R _ { p } ^ { \alpha } \left( \tau \right) , n \neq \tilde { K }
$$

对式(15)进行取模得

$$
\left| R _ { r } ^ { \alpha } \left( \tau \right) \right| = \frac { \sigma _ { d } ^ { 2 } } { T _ { s } } \Phi _ { N } \left( \tau \right) \left| R _ { p } ^ { \alpha } \left( \tau \right) \right| , n \neq \tilde { K }
$$

式(16)中

$$
R _ { p } ^ { \alpha } \left( \tau \right) = \int _ { - \infty } ^ { \infty } p \left( \tilde { t } \right) p \left( \tilde { t } - \tau \right) e ^ { - j 2 \pi \alpha \tilde { t } } d \tilde { t }
$$

由于关闭子载波对式(17)的计算没有影响，只会影响$\Phi _ { \scriptscriptstyle N } ( \tau )$ 的值，且 $p ( t )$ 是矩形脉冲，即当 $0 \leq t \leq T$ 时， $p \big ( t \big ) = 1$ ，根据定义

$$
\left| R _ { p } ^ { \alpha } \left( \tau \right) \right| = \left\{ \begin{array} { l l } { \displaystyle \left| \frac { \sin \left[ \pi \alpha \left( T _ { s } - | \tau | \right) \right] } { \pi \alpha } \right| , } & { \displaystyle \left( | \tau | \leq T _ { s } \right) } \\ { 0 , } & { \displaystyle \left( \tau > T _ { s } \right) } \end{array} \right.
$$

且式(18)在 $\tau = 0 , \alpha = 0$ 时，表达式取得最大值。

在对 $R _ { r } \big ( t , \tau \big )$ 进行傅里叶变换得到 NC-OFDM 的循环自相关函数且具有离散的谱线，谱线出现在 $\alpha = m / T _ { s }$ 处，当 $m = 1$ 时，$\alpha$ 为基准循环频率；而ZP-OFDM信号不具有离散的谱线。由此特征可知，能利用循环自相关进行OFDM信号有无循环前缀的识别，并进行了数值实验仿真验证。

综上所述，NC-OFDM信号参数估计算法步骤如下：

a)首先通过观察产生循环自相关三维结构图和切面图进行参数估计;

b）其次分析 $\tau = T _ { u }$ 切面图，先搜索谱峰最大值位置对应的坐标值 $\alpha _ { \mathrm { { _ 1 } } }$ ，接着搜索谱峰次大值对应的坐标值 $\alpha _ { 2 }$ ，利用$1 / ( \alpha _ { 2 } - \alpha _ { 1 } )$ 估计得到参数 $T _ { s }$ 。

c）再估计到参数 $T _ { s }$ 的基础上，接着分析 $\alpha = 0$ 切面图，先搜索谱峰最大值位置对应的坐标值 $\tau _ { 1 }$ ，在搜索 $T _ { \phantom { } _ { u } }$ 附近的谱峰最大值位置对应的坐标值 $\tau _ { 2 }$ ，利用 $\tau _ { 2 } - \tau _ { 1 }$ 即可估计参数 $T _ { u }$ 。

d）最后由估计得到的参数 $T _ { u }$ 和参数 $T _ { s }$ 可估计 $T _ { g }$ 。即利用$T _ { g } = T _ { s } - T _ { u }$ 计算可得。

# 4 数值仿真结果分析

采用IEEE802.11a标准进行仿真参数设置，其中，子载波数为 $N = 8 0$ ，循环前缀长度为 $N / 4$ 。信号带宽 $2 0 \mathrm { M H z }$ ，采样频率 $2 0 \mathrm { { M H z } }$ ，即采样为1bit/chip，发送的信息经历瑞利衰落信道（ $K = 0 . 0 1$ )，多径总数为5路，信噪比 $S N R = 0 d B$ 。子载波调制方式采用64QAM，通过IFFT变换，产生100个OFDM符号。

![](images/81965ffc78e5fce8d02d94043774a5bf028ad509ab2aaa6bed1768ebb7b485d8.jpg)  
图2ZP-OFDM信号的循环自相关

![](images/b8b0b43105739f72d2603fd0a706889aa81089b3e536fc5055292407ea688063.jpg)  
图3ZP-OFDM信号 $\alpha = 0$ 时的切片图

![](images/33fba09a2d584b602c0d5ba697a0aa41e22f23cfd758682e9dbe96f2b6aeec29.jpg)  
图4NC-OFDM信号的频谱

![](images/ab05cde60142a48490bc89c57cbf11596160e0176579d6481dc8a059fb9447d5.jpg)  
图5NC-OFDM信号的循环自相关

图2表示ZP-OFDM信号的循环自相关三维图，图3表示ZP-OFDM信号循环自相关 $\alpha = 0$ 的切片图，图4表示NC-OFDM信号的频谱图，图5表示NC-OFDM信号的循环自相关三维图。经比较 $\alpha = 0$ 切片图，NC-OFDM信号的循环自相关在 $\ v { \tau } _ { \tau = 0 , \pm T _ { u } }$ 时出现峰值，而 ZP-OFDM信号在 $\tau = \pm T _ { u }$ 处不会出现峰值，即循环自相关算法可作为一种识别方法来区分NC-OFDM信号和ZP-OFDM信号。

图6表示 $\tau = T _ { u }$ 的切片图，从切片图中可看出谱线出现在$\alpha = m / T _ { s }$ 的位置上，通过上述步骤b方法估计得到参数 $T _ { s }$ 。图7为NC-OFDM信号循环自相关三维图的 $\alpha = 0$ 的切片图，从切片图中可以看出信号的能量主要集中在 $\ v = 0 , \pm T _ { u }$ 的位置。最大值出现在 $\scriptstyle { \tau = 0 }$ 处（噪声的能量也在该点上)，这与理论分析结果相符合，且由于有20个子载波用作保护间隔，使得 $\scriptstyle { \tau = 0 }$ 附近出现一些小的谱线。通过上述步骤c方法检测这3个尖峰间的距离可得到有用的数据周期 $T _ { \phantom { } _ { u } }$ 。利用 $T _ { g } = T _ { s } - T _ { u }$ 可以估计到$T _ { g }$ 。

![](images/65a43cd659a0369afd97acb8ee87de429266f2e8bca981e796d732a76751801d.jpg)  
图6 $\tau = T _ { u }$ 时的切片图(估计 $T _ { s }$ ）

![](images/601ae2a4b5248786c7a42a058296d6db58a3b87511ec2aa1ec52dd0b480285dc.jpg)  
图7 $\alpha = 0$ 时的切片图(估计 $T _ { u }$ ）

从图6和7可知 $T _ { u } = 4 \mu s$ ， $T _ { s } = 5 \mu s$ 。由采样频率20MHZ可知，子载波时间间隔 $T _ { c } = 0 . 0 5 \mu s$ ，用 $T _ { u }$ 除以 $T _ { c }$ 可得子载波数为80，易知相关参数结果符合IEEE802.11a标准。

图8为NC-OFDM信号关闭 $90 \%$ 子载波信号的频谱图，图9为其循环自相关三维图，图10表示 $\tau = T _ { u }$ 的切片图，从切片图中可看出谱线出现在 $\alpha = m / T _ { s }$ 的位置上，通过上述步骤b方法估计得到参数 $T _ { s }$ ：

图11为关闭 $90 \%$ 子载波时NC-OFDM信号循环自相关的$\alpha = 0$ 切片图。通过上述步骤c方法即可得到有用的数据周期$T _ { u }$ ，利用 $T _ { g } = T _ { s } - T _ { u }$ 可以估计到 $T _ { g }$ 。

![](images/269e276ec0625e650c7a3d5743cf8e5483e2b489b0b8e67e616e08dd38846529.jpg)  
图8关闭 $90 \%$ 的子载波的NC-OFDM频谱

![](images/d29ac4525a4ca2f99f19074c1bcaaf6ca997e7fbd0a8ea64650ed5a61e2eb61d.jpg)  
图9关闭 $90 \%$ 子载波的NC-OFDM循环自相关

![](images/caf20590695f945fb475d5be7ea11adc42ba7e0cbe7df86ba0fa8482047c0705.jpg)  
图10 $\tau = T _ { u }$ 的切片图(估计 $T _ { s }$ ）

![](images/a7f50846efe6393a196eb493ca8a294bdc037515df0046aaead381d07d988194.jpg)  
图11 $\alpha = 0$ 时的切片图(估计 $T _ { u }$ ）

从图10和图11可知 $T _ { u } = 4 \mu s$ ， $T _ { s } = 5 \mu s$ 。由采样频率20MHZ 可知，子载波时间间隔 $T _ { c } = 0 . 0 5 \mu s$ ，用 $T _ { u }$ 除以 $T _ { c }$ 可得子载波数为80，易知相关参数结果符合IEEE802.11a标准。

图12为关闭超过 $90 \%$ 的子载波的NC-OFDM频谱图，图13为对应的NC-OFDM信号的循环自相关三维图，仿真结果表明，在关闭子载波数目超过 $90 \%$ 时，循环自相关算法不能有效的对NC-OFDM信号进行参数的盲估计。

综上所述，随着关闭的子载波数目的增加，通过观察NC-OFDM信号的循环自相关三维图及切片图分析，利用本文算法进行NC-OFDM信号的多个参数的盲估计，发现在关闭子载波数目的 $90 \%$ 以内时，都能够有效的进行多个参数的盲估计。

![](images/f0b63ac7907e05f5f57f8bf480ae4fa06ba5e03dee83f616942992bf348f3edb.jpg)  
图12关闭超过 $90 \%$ 的子载波的NC-OFDM频谱

![](images/2e7ff5d8f6bfbcc7e5b85bbf9f71793b259024d99b22a063dab0b96df3c85797.jpg)  
图13关闭超过 $90 \%$ 子载波的NC-OFDM循环自相关

# 5 参数估计性能仿真

图14是本文NC-OFDM信号的 $T _ { u }$ 和 $T _ { s }$ 参数估计的性能曲线，即参数估计的绝对误差随信噪比关系的性能曲线。由性能曲线可知，在低信噪比情况下，本文算法对NC-OFDM信号的$T _ { u }$ 和 $T _ { s }$ 能进行有效估计，并且发现估计 $T _ { u }$ 的性能曲线好于估计 $T _ { s }$ 的性能曲线，原因在于估计 $T _ { s }$ 时，是对NC-OFDM信号自相关函数做了一次傅里叶变换，其估计性能与傅里叶变换的点数有关，且估计性能与变换点数成正比。

![](images/99a033fb6e8f7eac0cc645acc59584aab3863b7462b5c8edd00c74a5ba70625f.jpg)  
图14估计 $T _ { u }$ 和 $T _ { s }$ 的性能曲线

# 6 结束语

NC-OFDM是CR的主要数据传输方式，本文针对非连续正交频分复用（NC-OFDM）信号的多个参数的盲估计及与ZP-

OFDM信号的盲识别，提出了基于循环自相关的算法。从仿真结果分析可知在关闭 $90 \%$ 以内子载波的NC-OFDM信号，利用循环自相关方法均可实现其多个参数的盲估计，包括 $T _ { s }$ 、 $T _ { u }$ 及$T _ { g }$ 。最后从参数估计性能曲线图可知，能在低信噪比下对 $T _ { s }$ 、$T _ { u }$ 进行有效估计。

# 参考文献：

[1]Bolcskei H. Blind estimation of symbol timing and carrier frequency offsetinwireless OFDM systems [J].IEEE Trans on Communications,2001,49(6): 998-999.  
[2]代光发，王勤王，高峰,etal.NC-OFDM系统旁瓣抑制中的可变干扰抵消基函数设计[J]．电子学报,2016,44(5):1156-1161.  
[3]何雪云，宋荣芳，周克琴.认知无线电NC-OFDM系统中基于压缩感知的信道估计新方法 [J].通信学报,2011,32(11):85-94.  
[4]韩英华，汪晋宽，赵强．基于交叉熵的NC-OFDM系统最优导频序列设计算法[J].中国科技论文,2015,10(2):134-138.  
[5]孙慧，杨守义，穆晓敏.NC-OFDM系统导频设计的离散粒子群算法[J].电子技术应用,2014,40(7):99-102.  
[6]周东旭，贾月岭，郭建新.NC-OFDM中改进的子载波预留 PAPR抑制算法[J].计算机工程,2015,41(10):10-13+19.  
[7]JangIG,Piao ZY,Dong ZH,et al.Low-Power FFTDesign for NC-OFDMin Cognitive Radio Systems [C]//Proc of IEEE International Symposium ofCircuits and Systems.2011: 2499-2452.  
[8]Kryszkiewicz P,Bogucka H. In-band-interference robust synchronizationalgorithm for an NC-OFDM system [J].IEEE Trans on Communications,2016,64(5): 2143-2154.  
[9]陈奎，黄为勇，田传耕．基于Matrix Pencil 的OFDM信号的TOA//AOA定位[J].计算机应用研究,2013,30(2):534-536+540.  
[10]蒋清平，杨士中，张天骐.OFDM信号循环谱分析及参数估计[J]．计算机应用研究,2010,27(3):1133-1135.  
[11]蒋清平，杨士中，张天骐.OFDM 信号循环自相关分析及参数估计[J].华中科技大学学报：自然科学报,2010,38(2):118-121.  
[12]王玉娥，张天骐，白娟，等.基于循环自相关的0FDM调制识别方法[J]．电视技术,2012,36(5):44-48.  
[13]郑航，郭建新，周东旭.NC-OFDM多种群自适应免疫优化子载波分配算法[J].空军工程大学学报：自然科学报,2015,16(3):77-81.