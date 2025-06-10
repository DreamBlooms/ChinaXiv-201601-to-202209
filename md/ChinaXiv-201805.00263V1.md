# 引入加权系数消除ICI的二次快时变信道估计算法

尹燕a，王 敏b，王传云b(华东交通大学a.软件学院;b.信息工程学院，南昌 330013)

摘要：针对高速移动环境下由多普勒频移引起的子载波间干扰（inter-carierinterference，ICI），提出一种引入加权系数消除ICI的二次快时变信道估计算法。该算法进行两次信道估计，第一次估计用于提供信道状态信息，在保证符号率的前提下消除 ICI，第二次估计在ICI消除的情况下进行，可以提高信道估计精度；并对简化的并行干扰消除(parallelinterference cancelation，PIC）算法进行改进，基于最小均方误差准则引入加权系数，使得ICI消除后的残余误差最小。仿真结果和理论分析达到很好的一致性，当信道信噪比为0dB时，归一化均方误差（normalizedmean squareerror，NMSE）性能增益最大约为0.0714，提高了快时变信道估计的精度。

关键词：加权系数；ICI消除；二次估计；快时变信道；PIC算法 中图分类号：TN92 doi:10.3969/j.issn.1001-3695.2017.08.0885

# Twice rapidly time-varying channel estimation algorithm based on ICI cancellation using weighted coefficient

Yin Yana, Wang Minbt, Wang Chuanyunb (a.Schoolofsoftware,bSchoolofnformationEngineering,EastChinaJaotong Universitynchang3o3,na)

Abstract:Thispaperproposeda twicechanel estimationalgorithm,inwhichusedweightedcoefcienttocancel Inter-Carrier Interference (ICI)caused byDoppler frequencyshift inhigh speed mobileenvironment.The algorithmachieved twicechanel estimation.The first estimation provided channeltate informationtocancel theICIunderthe premiseofensuring thesymbol rate;inthecaseof ICIcancelation,thesecondestimation enhanced the channel estimation acuracy.Thenthe algorithm improvedthesimplifiedparallel interferencecancelltion(IC)algorithm,and introduced the weightingcoeffcienttomakethe residual eror smallst after ICIcancelation basedon the minimum meansquareeror criterion.Thesimulation results are in good agreement with thetheoretical analysis.Theproposed algorithmimproves theestimationaccuracyofrapidly time-varying chanels. The maximum value of normalized mean square eror(NMSE)performance gain is 0.0714, when the SNR is 0dB. Key Words: weighted coefficient; ICI cancelation; twice estimate; rapidly time-varying channel; PIC algorithm

# 0 引言

随着高速铁路的迅猛发展，高速铁路通信系统正面临着诸多挑战[I]。在高速移动环境下，快时变信道待估计参数的数量将大大增加，因此，需要研究能够减少未知量个数的信道模型来拟合真实的快时变信道。常用的时变信道拟合方法有线性时变模型（linear time-varying，LTV）[2-4]和基扩展模型（basisexpansion model，BEM）[5-7]。BEM作为时频双选信道的最佳模型[5]，近些年来受到普遍关注。文献[6,7]提出了借助于BEM来估计快时变信道的方法，需要的导频数少，性能较好，但由于这些方法没有考虑ICI的影响，在多普勒频移较大的情况下估计精度没有明显提高。

BEM的信道估计方法是将快时变信道估计转换为对基系数的估计。在高速移动环境下，由于多普勒频移的增加会带来严重的ICI，导致基系数估计误差增大，造成系统性能恶化。因此，消除ICI是提高快时变信道估计精度的关键。文献[8]将简化的PIC方案与决策统计组合相结合来消除ICI，降低数据符号检测的误码率。文献[9]提出一种新的PIC算法，在均衡前的每个迭代过程中消除ICI，改进信道估计和均衡的性能。但以上算法都是针对ICI影响的单独考虑，并没有验证ICI消除后信道估计的改善情况。文献[10]将ICI消除与信道估计结合起来，设计了一种接收机结构包括三个主要模块：信道估计、自适应通道参数提取、PIC。采用估计的信道增益来估计ICI增益，然后结合检测信号以消除ICI。通过台湾高铁实际测试结果表明，在高速运动场景下，文献[10]中所提方法性能明显改善（信噪比为30dB时性能增益为2\~8dB）。但采用迭代的PIC 消除ICI,存在误差传播或难以收敛的情况。文献[11]提出一种基于最小均方误差（MMSE）迭代的三步ICI消除算法，包括MMSE信道估计、MMSE均衡和ICI消除，仿真结果表明，该方法明显减小了系统的误码率，但MMSE 算法计算复杂度较大。

本文针对上述文献中提到的问题，提出一种引入加权系数消除ICI的二次快时变信道估计算法。所提算法利用第一次信道估计得到的频域信道矩阵结合检测信号得到ICI干扰项；然后，采用简化的PIC算法消除ICI，由于没有采用迭代的方法逼近真实值，故存在的残余误差不可忽略。因此，本文对简化的PIC算法进行改进，基于最小均方误差准则引入加权系数 $\mu$ 使得ICI消除后的残余误差最小。最后利用ICI消除后的接收信号进行第二次信道估计，综合考虑ICI消除和信道估计之间的相互影响，提高信道估计的精度。

# 1基于ICI消除的二次快时变信道估计算法

# 1.1算法过程

如图1所示，本文提出的二次快时变信道估计算法过程如下：首先采用 BEM对快时变信道建模，并求出估计矩阵 $F _ { \mathit { L M M S E } }$ ；再进行第一次信道估计，得到频域信道矩阵 $\hat { H }$ ；采用改进的简化PIC 算法消除ICI，获得ICI消除后的频域接收信号 $\mathbf { { { \cal { Y } } } } _ { 2 n d }$ ；再用 $\mathbf { { { \cal { Y } } } } _ { 2 n d }$ 进行第二次信道估计，得到 $\hat { H ^ { \prime } }$ ，完成信道估计。采用该方法可以消除ICI对快时变信道估计的影响，进一步提高信道估计精度。

![](images/39a7b8ec4e3214f8f46c5bd41f020fb26bda27ff87b5a633209aba24c11e22e0.jpg)  
图1OFDM系统快时变信道估计框图

# 1.1.1信道模型建立

常用的 BEM 有复指数基扩展模型(complex exponential-BEM,CE-BEM)[12]、广义复指数基扩展模型(generalized complexexponential-BEM,GCE-BEM)[13]、多项式基扩展模型（polynomial-BEM,P-BEM）[14]、离散椭球序列基扩展模型(discrete prolate sequence-BME,DPS-BEM)[15]和离散卡-洛基扩展模型（discrete Karhunen-Loeve-BEM:DKL-BEM）[16]。其中DKL-BEM 为 MMSE 准则下的最优模型[17]。本文选用 DKL-BEM建立信道模型。

利用DKL-BEM来描述双选信道，当最大时延 $\tau _ { \mathrm { m a x } }$ 和最大多普勒频移 $f _ { \mathrm { m a x } }$ 满足 $2 \tau _ { \operatorname* { m a x } } f _ { \operatorname* { m a x } } < 1$ 时，可以将双选信道建模为一个 FIR 滤波器，其每个抽头被表示为一组基函数的叠加，则时域信道响应可以表示为

$$
h _ { \scriptscriptstyle { l } } ( n ) = \sum _ { q = 0 } ^ { \cal Q } g _ { \scriptscriptstyle  q } ( \boldsymbol { l } ) b _ { \scriptscriptstyle q } ( n )
$$

其中: $b _ { _ q } ( n )$ 为 $n$ 时刻DKL-BEM的基函数， $\boldsymbol { \mathscr { Q } }$ 为DKL-BEM的阶数， $g _ { \boldsymbol { q } } ( l )$ 为基系数，在一个OFDM 符号周期内保持不变。

图1中经过加性高斯白噪声AWGN信道传输后，接收端接收到的频域信号表示为[6]：

$$
Y = H X + W = ( H _ { _ { \mathrm { a v e } } } + H _ { _ { I C I } } ) X + W = H _ { _ { \mathrm { a v e } } } X + H _ { _ { I C I } } X + W
$$

$$
H _ { k , \nu } = \frac { 1 } { N } \sum _ { n = 0 } ^ { N - 1 } \sum _ { l = 0 } ^ { L - 1 } h _ { l } ( n ) e ^ { - j \frac { 2 \pi } { N } [ \nu ( l - n ) + n k ] }
$$

其中: $\scriptstyle { \boldsymbol { X } }$ 和 $\boldsymbol { Y }$ 分别为频域的发送和接收信号， $\boldsymbol { \mathsf { \Pi } } _ { W }$ 为时域加性高斯白噪声的频域表示， $H _ { \mathbf { \Phi } _ { k , \nu } }$ 为信道频域矩阵 $\textbf {  { H } }$ 的元素， $\mathrm { ~  ~ N ~ }$ 为OFDM系统子载波个数， $\mathrm { ~ L ~ }$ 为抽头数， ${ \pmb { H } } _ { \alpha \nu e }$ 为（ $N \times N$ ）对角矩阵， $H _ { \boldsymbol { k } , \boldsymbol { k } }$ 为其对角元素， $\pmb { H } _ { _ { I C I } }$ 为（ $N \times N$ ）数据子载波对导频子载波的干扰矩阵，其对角线元素为0，非对角线元素为$H _ { \boldsymbol { k } , \nu }$ $( \mathbf { k } \neq \mathbf { v } )$ 。对式（3）分析可以发现， $h _ { \iota } ( n )$ 随时间 $\mathfrak { n }$ 变化时，$\textbf {  { H } }$ 有非对角元素，即快时变信道中存在ICI项。因此，需要对ICI干扰进行消除，提高快时变信道的估计精度。

# 1.1.2信道估计矩阵

1）导频结构

本文采用常见的频域梳状导频结构（FDKD）进行信道估计，假设一个OFDM符号中有M个导频簇，每个导频簇中有a 个非零导频，非零导频两侧分别有 $\boldsymbol { \mathbf { b } }$ 个零导频。M个导频簇等周期的插入到一个OFDM符号中，每个导频簇矢量记为

$$
\mathbf { x } _ { m } ^ { ( P ) } = [ x ( P _ { m } ) , \cdots , x ( P _ { m } + a + 2 b - 1 ) ] \ , \ \mathbf { m } { = } 0 , 1 , \cdots , \mathbf { M } { - } 1
$$

其中 $\boldsymbol { P _ { m } }$ 为第 $\mathbf { m }$ 个导频簇的起始位置。则可以将一个OFDM符号分成两部分， $x ^ { ( P ) }$ 为所有导频簇符号， $x ^ { ( d ) }$ 为剩下的数据符号。导频结构如图2所示。

![](images/075e469e4190ead1d45800ae6e8e1afadc55c60a46c4304c4b64cdadd8572d4f.jpg)  
图2FDKD 导频结构

2）信道估计方法

BEM采用随时间变化的基函数与不随时间变化的基系数来表征信道，其信道估计问题可以转换为线性参数（基系数）的估计问题，但是，要得到基系数必须先求出估计矩阵。常用的估计方法有最小二乘估计（LS）和线性最小均方误差估计（LMMSE）。LS的估计方法虽然复杂度低，但其没有考虑ICI和噪声干扰，在多普勒频移大或信噪比小的时候，估计效果不理想；而LMMSE 估计方法综合考虑了ICI、噪声以及多径时延的影响，虽然依赖信道信息、涉及自相关矩阵的计算，复杂度较高，但相较于LS估计方法而言有更高的精确度。因此，本文采用LMMSE的方法估计基系数，即找到一个估计矩阵$F _ { \_ M M S E }$ ，使基系数与基系数的估计值之间的均方误差最小。估

计矩阵的表达式为[7]

$$
F _ { _ { L M M S E } } = R _ { g } { D ^ { H } } / ( D R _ { g } { D ^ { H } } + R _ { d } + R _ { w } ^ { ( P ) } )
$$

其中: $( \bullet ) ^ { H }$ 表示对矩阵做共轭转置， $R _ { g } \ , \ R _ { d } \ , \ R _ { W } ^ { ( P ) }$ 分别为BEM的基系数向量、ICI干扰项和噪声的自相关矩阵。

$$
\pmb { { \cal D } } = { \cal A } _ { q } ^ { ( P ) } { \pmb { s } } ^ { ( p ) }
$$

$$
\pmb { A } _ { q } = \pmb { F } d i a g ( \pmb { b } _ { q } ( : , q + 1 ) ) \pmb { F } ^ { H }
$$

$$
s ^ { ( P ) } = I _ { _ { Q + 1 } } \otimes ( d i a g ( X ^ { ^ { ( P ) } } ) F _ { L } ^ { _ { ( P ) } } )
$$

其中: $\otimes$ 表示Kronecker 积； $\pmb { b } _ { q } = [ \pmb { b } _ { 0 } , \pmb { b } _ { 1 } , \cdots , \pmb { b } _ { Q } ]$ 为 $N \times ( Q + 1 )$ 的基函数矩阵； $X ^ { ( P ) }$ 对应于所有导频子载波处的频域发送数据， $\pmb { F } _ { L }$ 表示矩阵 $\sqrt { N } F$ 的前 $\mathrm { ~ L ~ }$ 列。

# 1.1.3第一次信道估计

利用1.2中的估计矩阵进行基系数估计，则基系数可以表示为

$$
\hat { \pmb { g } } = \pmb { F } _ { L M M S E } \pmb { Y } ^ { ( P ) }
$$

$$
{ \pmb Y } ^ { ( P ) } = { \pmb Y } ( p i l o t \_ p o s i t i o n , : )
$$

其中: $\pmb { Y } ^ { ( P ) }$ 对应所有导频子载波处的频域接收数据。求得基系数后，再由式（1）得到时域信道响应，由式（3）得到频域信道矩阵 $\hat { H }$ 。

# 1.1.4ICI消除方法

由式（2）可知，当信道近似线性变化时，ICI可以看做是一种加性干扰，由此文献[18]将基于MMSE准则的均衡器中的$\sigma _ { { } _ { w } } ^ { 2 } / \sigma _ { { } _ { x } } ^ { 2 }$ 改为 $( \sigma _ { w } ^ { 2 } + \sigma _ { I C I } ^ { 2 } ) / \sigma _ { x } ^ { 2 }$

$$
\begin{array} { l } { { \displaystyle { \pmb G } = \hat { \pmb { H } } ^ { H } ( \hat { \pmb { H } } \hat { \pmb { H } } ^ { H } + \frac { \pmb { \sigma } _ { w } ^ { 2 } + \pmb { \sigma } _ { I C I } ^ { 2 } } { \pmb { \sigma } _ { x } ^ { 2 } } { \pmb { I } } ( N ) ) ^ { - 1 } } } \\ { { \displaystyle ~ = \hat { \pmb { H } } ^ { H } ( \hat { \pmb { H } } \hat { \pmb { H } } ^ { H } + \frac { 1 } { S I N R } { \pmb { I } } ( N ) ) ^ { - 1 } } } \end{array}
$$

其中: $( \bullet ) ^ { - 1 }$ 为求逆矩阵， $\pmb { I } ( N )$ 为 $N \times N$ 的单位矩阵， $\sigma _ { x } ^ { 2 }$ 为发送信号的平均功率， $\sigma _ { { } _ { w } } ^ { 2 }$ 为噪声的平均功率， $\sigma _ { I C I } ^ { 2 }$ 为ICI的平均功率，Jakes 信道的 SINR由下式给出。

$$
S I N R = \frac { \displaystyle \frac { \sigma _ { x } ^ { 2 } } { N ^ { 2 } } [ 2 \sum _ { n = 1 } ^ { N - 1 } J _ { 0 } ( \frac { 2 \pi n f _ { \mathrm { m a x } } t _ { s } } { N } ) ( N - n ) + N ] } { \displaystyle \sigma _ { x } ^ { 2 } - \frac { \sigma _ { x } ^ { 2 } } { N ^ { 2 } } [ 2 \sum _ { n = 1 } ^ { N - 1 } J _ { 0 } ( \frac { 2 \pi n f _ { \mathrm { m a x } } t _ { s } } { N } ) ( N - n ) + N ] + \sigma _ { w } ^ { 2 } }
$$

其中: $J _ { 0 } ( \bullet )$ 为零阶贝塞尔函数， $t _ { s }$ 为采样间隔，则检测信号 $X _ { 2 n d }$ 可以表示为

$$
\pmb { X } _ { 2 n d } = \pmb { G } \pmb { Y }
$$

采用简化的PIC算法消除ICI，则经过ICI消除之后的频域接收信号可以表示为

$$
\pmb { Y } _ { 2 n d } = \pmb { Y } - \hat { \pmb { H } } _ { n c I } \pmb { X } _ { 2 n d }
$$

$$
\hat { H } _ { _ { I C I } } = \hat { H } - d i a g ( d i a g ( \hat { H } ) )
$$

其中: $d i a g ( d i a g ( { \hat { H } } ) )$ 为以 $\hat { H }$ 的对角线元素为对角的对角矩阵。

1.1.5第二次信道估计

采用 $Y _ { 2 n d }$ 进行第二次信道估计，则基系数可以表示为：

$$
\hat { \pmb { g } } ^ { \prime } = \pmb { F } _ { L M M S E } \pmb { Y } _ { 2 n d } ^ { ( P ) }
$$

$$
Y _ { 2 n d } ^ { ( P ) } = Y _ { 2 n d } ( p i l o t \_ p o s i t i o n , : )
$$

其中: ${ \pmb Y } _ { 2 n d } ^ { ( P ) }$ 对应于所有导频子载波处的ICI消除后的频域接收数据；求得基系数后，采用与1.3中相同的方法得到频域信道矩

阵 $\hat { H ^ { \prime } }$ ，完成信道估计。

# 1.2算法仿真及分析

本文基于MATLAB仿真平台，在速度为 $3 5 0 \mathrm { k m / h }$ 的情景下，对传统的DKL-BEM算法和所提的基于ICI消除的二次快时变信道估计算法的性能进行对比分析，如图3所示，验证所提算法的正确性和有效性。定义归一化均方误差（NMSE）来衡量信道估计的性能，如式（18）所示。

$$
\begin{array} { r } { N M S E = \frac { \displaystyle \frac { 1 } { N } \sum _ { n = 0 } ^ { N - 1 } E \left\{ \sum _ { l = 0 } ^ { L - 1 } \left| { h _ { l } ^ { \prime } \left( n \right) - \hat { h } _ { l } ^ { \prime } ( n ) } \right| ^ { 2 } \right\} } { \displaystyle \frac { 1 } { N } \sum _ { n = 0 } ^ { N - 1 } E \left\{ \sum _ { l = 0 } ^ { L - 1 } \left| { h _ { l } ^ { \prime } \left( n \right) } \right| ^ { 2 } \right\} } } \end{array}
$$

其中: $h _ { l } ^ { r } ( n )$ 是实际信道的抽头响应（由Jakes 模型产生）。在仿真中系统载波频率 $\scriptstyle \mathbf { G } = 2 \mathbf { G } \mathbf { H } \mathbf { z }$ ，仿真一帧数据包括20个OFDM符号样本，具体参数设置如表1所示。

表1OFDM快时变信道估计仿真参数设置  

<html><body><table><tr><td>参数</td><td>设置值</td></tr><tr><td>子载波个数N</td><td>256</td></tr><tr><td>调制方式</td><td>QPSK</td></tr><tr><td>信道多径数L</td><td>6</td></tr><tr><td>采样时间间隔ts</td><td>1 μs</td></tr><tr><td>循环前缀长度</td><td>32</td></tr><tr><td>BEM阶数Q</td><td>4</td></tr><tr><td>梳状导频簇数M</td><td>8</td></tr><tr><td>每簇中的非零导频个数a</td><td>1</td></tr><tr><td>一侧的零导频个数b</td><td>4</td></tr></table></body></html>

![](images/0f83d3807aefb63e2ba1900ea2c046200decfe9f7a890cbbccc48206598fa894.jpg)  
图3NMSE 随信噪比变化的曲线

(DKL-LMMSE:采用LMMSE 估计的传统DKL-BEM算法性能曲线; DKL-ICI-LMMSE:采用LMMSE 估计的基于ICI消除的二次快时变信 道估计算法并时的性能曲线)

式（11）的信号检测方法是基于信道线性变化给出的，但是在高速移动环境下信道变化是非线性的。当信噪比较小时，噪声较大，ICI的非线性变化对整体估计的影响不明显；但信噪比越大，噪声越小，此时，ICI的微小变化也会对估计结果产生影响。因此，检测信号仍会受到ICI的影响，干扰抵消后会存在残余误差，且在信噪比较大时更为严重。

如图3所示，当 $\mathrm { S N R } { > } 1 4 . 3 \mathrm { d B }$ 时，所提的DKL-ICI-LMMSE算法性能下降不如传统的DKL-LMMSE 算法，即所提算法在信噪比较小的情况下更适用。理论分析与仿真结果的一致性，证明了所提算法的正确性与有效性。为了减小ICI干扰抵消后产生的残余误差，本文对简化的PIC算法进行改进，引入加权系数u，使ICI消除后的残余误差最小。

# 2 引入加权系数消除ICI的二次快时变信道估计算法

# 2.1引入加权系数 $\mu$

为了更深入分析式（14）中的ICI消除问题，将发送数据$\scriptstyle { \boldsymbol { X } }$ 分成两部分：导频部分 $X ^ { ( P ) }$ 和数据部分 $X ^ { \mathrm { ( d ) } }$ 。式（14）中 $\boldsymbol { Y }$ 还可以表示为[19]：

$$
\begin{array} { c } { { \displaystyle Y = \sum _ { q = 0 } ^ { Q } A _ { q } ^ { ( P ) } d i a g ( X ^ { ( P ) } ) F _ { L } ^ { ( P ) } g _ { q } } } \\ { { + \underbrace { \sum _ { q = 0 } ^ { Q } A _ { q } ^ { ( d ) } d i a g ( X ^ { ( d ) } ) F _ { L } ^ { ( d ) } g _ { q } } } } \end{array} + W
$$

将式（19）代入式（14）中则经过ICI消除的频域接收信 号可以表示为

$$
\begin{array} { l } { { \displaystyle Y _ { 2 n d } = \sum _ { q = 0 } ^ { Q } { \pmb A } _ { q } ^ { ( P ) } d i a g ( { \pmb X } ^ { ( P ) } ) { \pmb F } _ { L } ^ { ( P ) } { \pmb g } _ { q } } } \\ { { \displaystyle ~ + \sum _ { q = 0 } ^ { Q } { \pmb A } _ { q } ^ { ( d ) } d i a g ( { \pmb X } ^ { ( d ) } ) { \pmb F } _ { L } ^ { ( d ) } { \pmb g } _ { q } } } \\ { { \displaystyle ~ - \sum _ { q = 0 } ^ { Q } { \pmb A } _ { q } ^ { ( d ) } d i a g ( { \pmb X } _ { 2 n d } ^ { ( d ) } ) { \pmb F } _ { L } ^ { ( d ) } \hat { \pmb g } _ { q } + { \pmb W } } } \end{array}
$$

其中: $\pmb { \hat { g } } _ { q } = [ g _ { q } ( 0 ) , g _ { q } ( 1 ) , \cdots , g _ { q } ( L - 1 ) ]$ 为第一次信道估计的基向量。

令 $\boldsymbol { s } ^ { ( d ) } = \boldsymbol { I } _ { Q + 1 } \otimes ( d i a g ( \boldsymbol { X } ^ { ( d ) } ) \boldsymbol { F } _ { L } ^ { ( d ) } )$ ， $\pmb { c } ^ { ( d ) } = \pmb { I } _ { Q + 1 } \otimes ( d i a g ( \pmb { X } _ { p r e } ^ { ( d ) } ) \pmb { F } _ { L } ^ { ( d ) } )$ ，则式（20）可以表示为

$$
Y _ { \mathrm { 2 n d } } = A _ { q } ^ { ( P ) } { \boldsymbol { s } } ^ { ( P ) } { \pmb { g } } + A _ { q } ^ { ( d ) } ( { \pmb { s } } ^ { ( d ) } { \pmb { g } } - { \pmb { c } } ^ { ( d ) } { \hat { \pmb { g } } } ) + W
$$

其中: $A _ { q } ^ { ( d ) } { s } ^ { ( d ) } { g }$ 表示数据子载波对导频子载波的干扰， $A _ { q } ^ { ( d ) } \pmb { c } ^ { ( d ) } \hat { \pmb { g } }$ （20表示第一次信道估计求得的ICI干扰项。从式（21)可以看出，等式右边第二项是干扰抵消所产生的残余误差。残余误差越小，ICI 消除的效果越好。传统的 PIC 算法采用迭代的方法减小残余误差，但存在误差传播和难以收敛的问题。本文基于最小均方误差准则在简化的 PIC 算法中引入加权系数 $\mu$ 来减小残余误差，则式（21）可以表示为

$$
{ \pmb Y } _ { 2 n d } = { \pmb A } _ { q } ^ { ( P ) } { \pmb s } ^ { ( P ) } { \pmb g } + { \pmb A } _ { q } ^ { ( d ) } ( { \pmb s } ^ { ( d ) } { \pmb g } - \mu { \pmb c } ^ { ( d ) } \hat { \pmb g } ) + { \pmb W }
$$

其中：加权系数 $\mu$ 的选取准则为

$$
\mu = \arg \operatorname* { m i n } { \{ E ( s ^ { ( d ) } { \pmb g } \ – \mu { \pmb c } ^ { ( d ) } \hat { \pmb g } ) ^ { 2 } \} }
$$

引入加权系数 $\mu$ 后的ICI消除的过程如图4所示，由于ICI消除后，其对信道估计的影响变小，故再利用 $\mathbf { { { Y } } } _ { 2 n d }$ 进行第二次信道估计，可以提高信道估计精度。

# 2.2 算法仿真及分析

本节采用与1.2节相同的仿真环境，仿真过程中，图4中的加权系数模块会根据当前的移动速度和信噪比按照均方误差最小准则给出合适的加权系数值，当移动速度和信噪比值发生变化时，μ的最优值也会随之变化。以移动速度 $\mathrm { \Delta \ v = 3 5 0 k m / h }$ ，信噪比 $\mathrm { S N R } { = } 1 5 \mathrm { d B }$ 时为例，采用仿真软件提取参数的方法可以获得加权系数的最优值，u为0.4。

接收信号 移动 信 Y2nd =Y- μHicX2nd +W SNR Y →   
频域信道矩阵 从 ICI消除后的 加权系数模块 接收信号 H ↑ H1cIX2nd X 2nd   
检测信号 ICI干扰项

图5给出了NMSE随加权系数变化的曲线图，理论分析与仿真结果一致，当u为0.4 时所提算法相对于传统的DKL-LMMSE 算法性能增益最大。由图3可知，当 $\mathrm { S N R } { = } 1 5 \mathrm { d B }$ 、μ$^ { = 1 }$ 时，传统的DKL-LMMSE 算法优于所提的DKL-ICI-LMMSE算法。引入加权系数 $\mu$ 后，当 $\mu > 0 . 9 5$ 时，传统的DKL-LMMSE算法优于改进算法，即在速度 $\mathrm { { v = } 3 5 0 k m / h }$ 、信噪比 SNR=15dB这一特定环境下引入的 $\mu$ 值不能大于0.95，且在u为0.4时为最佳取值。

![](images/c800d9f1ab4184e8b7bee71e53671e8fe34b3b48cbea0b28e2fcb740ee04bf7e.jpg)  
图4引入加权系数后的ICI消除过程

图6对加权系数取值的正确性进行了进一步的验证，u分别取0.2、0.4及0.6。由图可以看出，μ为0.4时相比于u为0.2和0.6时性能更好，与理论分析一致。

![](images/4ca1336854947fe5e194004659fe85e9040cede1bec109d85998e1f8eaa11d90.jpg)  
图5NMSE随加权系数 $\mu$ 变化的曲线  
图6不同加权系数条件下NMSE随信噪比变化的曲线

由图7可知，引入加权系数后，残余误差对信道估计的影响明显减小。虽然 $\mu$ 为0.4是 $\mathrm { S N R } { = } 1 5 \mathrm { d B }$ 条件下的最优取值，但是在 SNR 为0-20dB 之间时，所提算法在性能上与传统的DKL-LMMSE算法相比有所提高，且在信噪比为0dB即信噪比为1时，NMSE性能增益最大为0.0714，如表2所示。

![](images/d10ec546e42d09dfdacbca9e1e2f0ec3ea2210191c942cf4c1dab953105bd458.jpg)  
图7NMSE随信噪比变化的曲线

表2两种算法的NMSE 比较  

<html><body><table><tr><td>SNR(dB)</td><td>DKL-LMMSE</td><td>DKL-ICI-LMMSE μ=0.4</td><td>NMSE差值</td></tr><tr><td>0</td><td>0.3896</td><td>0.3182</td><td>0.0714</td></tr><tr><td>5</td><td>0.1377</td><td>0.1115</td><td>0.0262</td></tr><tr><td>10</td><td>0.0568</td><td>0.0456</td><td>0.0112</td></tr><tr><td>15</td><td>0.0253</td><td>0.0200</td><td>0.0053</td></tr><tr><td>20</td><td>0.0134</td><td>0.0122</td><td>0.0012</td></tr></table></body></html>

# 3 结束语

本文首先提出了一种基于ICI消除的二次快时变信道估计算法，采用两次信道估计，第一次信道估计用于提供信道状态信息，在保证符号率的前提下消除ICI，第二次信道估计在ICI消除的情况下进行，可以提高信道估计精度。研究发现，达到一定的信噪比值后，二次信道估计算法不如传统算法。故又对简化的PIC算法进行改进，引入加权系数u，减小残余误差对信道估计的影响。仿真结果表明，在SNR为 $0 { \sim } 2 0 ~ \mathrm { d B }$ 之间时，所提算法在性能上有明显的提高，在信噪比为0dB时，NMSE性能增益为0.0714。

# 参考文献：

[1]Wu Jingxian，Fan Pingzhi.A survey on high mobility wireless communications:challenges,opportunities and solutions [J].IEEE Access. 2016,4: 450-476.   
[2]Jeon W G,Chan K H,Cho Y S.An equalization technique for OFDM systems in time-variant multipath channels [J].IEEE Trans on Commun, 1999.   
[3]Mostofi Y,Cox D C.ICI mitigation for pilot-aided OFDM mobile systems [J].IEEE Trans on Wireless Communications,2005,4(2): 765-774.   
[4]Hao Jinxing,Wang Jintao,Pan Changyong.Low complexity ici mitigation forMIMO-OFDM in time-varying channels [J]. IEEE Transon Broadcasting,2016,62(3): 1-9.   
[5]Zafarani E,Omidi MJ,Heydaryan F,et al. Oversampled Legendre basis expansion model for doubly-selective channels [C]//Proc of the 19th Iranian Conference on Electrical Engineering.[S.1.] :IEEE Press,2011:1-5.

[6]Zuo Huiling,Song Hengguo,Yuan Tianpeng,et al. Channel Modeling and

Estimation in High-SpeedMobile Environment [C]//Proc of the 83rd IEEE

Vehicular Technology Conference. [S.1.]: IEEE Press,2016:1-5.   
[7]Bi Yuming,Zhang Jianhua,Zeng Ming,et al.Channel modeling and estimation for OFDM systems in high-speed trainsscenarios [Cl//Proc of the 83rd IEEE Vehicular Technology Conference.[S.1.]: IEEE Press,2016: 1-6.   
[8]Aboutorab N,Hardjawana W,Vucetic B.A new iterative doppler-assisted channel estimation joint with parallel ICI cancellation for high-mobility MIMO-OFDM systems[J].IEEE Trans on Vehicular Technology,2012,61 (4): 1577-1589.   
[9]Liao Jialing，Qiao Gang，Ma Xuefei.A novel parallel interference cancelltion scheme for OFDM in time-varying underwater acoustic channels [Cl/ Proc of International Conference on Mechatronic Sciences, Electric Engineering and Computer.[S.1.]:IEEEPress,2013:3692-3696.   
[10] Liu Chun Hao,Chuang Gene C H. Joint ICI cancellation and channel estimation with real-time channel adaptation for high-mobility OFDM systems [C]/ Proc of GLOBECOM Workshops.[S.1.]: IEEE Pres,2011: 1376-1381.   
[11] Nissel R,Rupp M. Doubly-selective MMSE channel estimation and ICI mitigation for OFDMsystems [C]/ Proc of IEEE International Conference on Communications. [S.1.]: IEEE Press,2015: 4692-4697.   
[12] Tang Z, Cannizzaro R C,Leus G,et al. Pilot-assisted time-varying channel estimation for OFDM systems [J].IEEE Transon Signal Processing,2007, 55 (5): 2226-2238.   
[13] Guo Qilin,Wu Muqing, Zhang Qinjuan,et al. Iterative decomposed OFDM channel estimation algorithm over highly mobile channels[J].Wireless Personal Communications,2013,71(2): 1137-1158.   
[14] Tomasin S,Gorokhov A,Yang H,et al. Iterative interference cancellation and channel estimation for mobile OFDM[J]. IEEE Trans on Wireles Communications,2005,4(1): 238-245.   
[15] Zemen T, Mecklenbrauker CF.Time-variant channel estimationusing discrete prolate spheroidal sequences [J]. IEEE Trans on Signal Processing 2005,53 (9): 3597-3607.   
[16] Senol H. Joint Channel Estimation and symbol detection for OFDM systems in rapidly time-varying sparse multipath channels [J]. Wireless Personal Communications,2015,82 (3): 1161-1178.   
[17] TeoKAD,Ohno S.Optimal MMSE finite parameter model for doubly selectivechannels [Cl// Procof IEEE Global Telecommunications Conference.[S.1.]: IEEE Press,2005.   
[18]尼俊红，刘泽民．基于MMSE准则的改进型并行迭代ICI消除算法 [J]. 电路与系统学报,2011,16(1):74-78.   
[19] Sheng Zhichao,Fang Yong，Wang Chen.A BEM method of channel estimation for OFDMsystems in high-speed train environment [Cl//Proc of International WorkshoponHighMobiltyWireles CommunicatisS1.]: IEEE Press,2013: 6-9.