# 宽带大规模MIMO-OFDM系统自适应稀疏信道估计方案

黄灿，李素月，王安红(太原科技大学 电子信息工程学院，太原 030024)

摘要：大规模 MIMO-OFDM系统下行链路利用压缩感知算法获得信道状态信息需要已知信号的稀疏度作为先验条件，然而实际环境中，无线信道的稀疏度是未知的。利用大规模MIMO信道的空时共同稀疏性的特点与不同 SNR下设置不同停止迭代阈值的思想改进压缩感知重构算法，目的在于使所提算法不仅提升估计性能，还可以准确获得信道的动态稀疏度。通过实验可知，相比传统的CoSaMP算法和 S-CoSaMP算法，SSA-CoSaMP算法在同等信噪比下具有更良好的信道估计性能，并且可以自适应地获取稀疏度。更适合实际工程中应用。

关键词：大规模MIMO；压缩感知；稀疏度自适应；稀疏信道估计；空时共同稀疏性 中图分类号：TP929.5 doi:10.3969/j.issn.1001-3695.2018.04.0321

# Adaptive sparse channel estimation for broadband massive MIMO-OFDM systems

Huang Can, Li Suyue†, Wang Anhong (CollagelofElectronic Information Engineering,Taiyuan UniversityofScience&Technology,TaiYuanO3o024,China)

Abstract:In massive MIMO-OFDM system,most of the compressed sensing theoryreconstruction algorithms nd the sparsityofthe knownsignalasa prioricondition.However,intheactual environment,thesparsityof the wireless channelis unknown.Therefore,the proposed algorithmused thespace-time common sparsityof the Masive MIMO chanel to reasonably set the stopping iteration parameters under diferent SNR to obtain accurate dynamic sparsity.The experimental results showthat,compared with the traditional CoSaMPandS-CoSaMPalgorithms,theSSA-CoSaMPalgorithmhas better channel estimation performance under the same SNR and can obtain the sparsity adaptively.

Key words:massive MIMO;compressve sensing;sparsity adaptive；sparsitychannel estimation；spatio-temporal common sparsity

# 0 引言

大规模MIMO是通过利用在基站侧部署大量的发射天线并且实现同时服务于多个单接收天线用户的系统[1。因此，大规模MIMO表现出良好的抗噪声、抗窄带衰落的能力，以更好的利用日渐珍贵的频谱与能量资源，成为了未来5G发展的关键技术[2.3]。在大规模MIMO系统中，无论是信号检测、波束赋形，还是资源分配、信道分配都需要获得准确的CSI。因此，性能杰出的信道估计方案成为了大规模MIMO的支撑技术。

目前，关于大规模MIMO的绝大多数的研究都是在时分双工(time divisionduplex,TDD)模式下进行的，目的在于利用上下行信道的互易性，通过对上行链路的信道估计而得到下行信道的 CSI[4]。但是，频分双工(frequency division duplex,FDD)模式比 TDD模式的延时更低、通信效率更高，且国际上大部分国家现阶段的蜂窝系统都是FDD 模式的[5]。所以，对于FDD 模式下的大规模MIMO的信道估计研究具有深远的意义。然而，在FDD模式下，对于下行链路进行准确估计是十分困难的[]。基站侧分布着大量发射天线，而这些发射天线同时向用户发送数据，因此，这样就要求用户侧准确估计出每一根发射天线与用户侧的单接收天线所构成的CSI。同时满足较高的精确性和较低的导频开销也是十分困难的。

OFDM系统有诸多优势，例如较高的频谱利用率，良好的抗多径干扰的能力和抗窄带衰落的能力等[7]。在无线通讯用户激增的今天，需要提升更多的系统容量，因此把正交频分复用系统与大规模MIMO系统联合作用，从而实现天线分集与空间复用[7]。当前的通信环境下，可利用的无线带宽频率越来越匮乏，将两种系统结合起来，可以极大地提升频谱资源的利用率，同时还可以针对无线信道频率有选择性衰落环境进行有效处

理。

典型的宽带无线传输环境存在频率选择性衰落的情况，因此，为了解决这一问题，我们将大规模MIMO与OFDM系统联合使用建立大规模MIMO-OFDM系统[8]。

在大规模MIMO-OFDM传输环境中，分布着大量的散射体，形成了瑞利多径传输信道。并且无线信道的绝大多数能量集中在信道冲击响应(channel impulse response,CIR)的极少分量上[9，使得用户侧与基站侧所形成的CSI天然地呈现了稀疏性[10,11]。

根据信道所呈现的稀疏性，可以利用压缩感知(compressivesensing,CS)对信道进行估计[12]。然而，实际环境中，无线信道的稀疏度是未知的。那么就要求在不知道稀疏度的情况下，算法本身可以估计出信道的稀疏度[13]。因此，本文提出稀疏度自适应压缩采样匹配追踪(SSA-CoSaMP)算法，利用空间共同稀疏性不仅可以提升估计性能，还可以节省导频开销，并且使算法获得稀疏度自适应的能力。

本文的主要工作包括以下四个方面：

a)对CoSaMP算法进行稀疏度自适应化改进，使得算法在稀疏度未知的情况下可以自身获取稀疏度；

b)在稀疏度自适应的基础上利用大规模MIMO信道空时共同稀疏特性，进行结构化处理。不仅使获取稀疏度速度更快，而且提升估计性能及准确度；

c)算法停止迭代参数 $\beta$ 的确定；

d)通过仿真程序验证了提出的信道估计算法的精度及性能。

# 1大规模MIMO-OFDM空时共同稀疏性

# 1.1大规模MIMO信道的空间共同稀疏性

在大规模MIMO-OFDM系统信号传输的实际环境中，分布着大量的散射体，形成了瑞利多径传输信道。并且无线信道的绝大多数能量集中在CIR的极少分量上[14]，使得用户侧与基站侧所形成的CSI天然地呈现了稀疏性[15]。

与此同时，基站侧每一根发射天线发出的信号在到达用户侧的接收天线时，所经过的散射体非常相似，几乎一致。也就是用户侧的单天线与基站侧的所有天线有空间共同稀疏性的特点。此外，由于与时间信道相关的路径增益相比，路径延迟的变化慢得多，所以在相干时间期间，这种稀疏性几乎不变[16],形成时间相关性的特点。

典型的单小区下行多用户大规模MIMO-OFDM无线通信系统存在空间共同稀疏性，而这是由多径效应、天线物理特性和无线传输环境等多方面因素共同引起的。在无线传输环境中，散射体使得信号从同一根发射天线到接收天线之间形成多条路径，形成多径效应。然而，就在这些传输路径中，从发射天线到达接收天线的时间也是不一致的[17]。因此，使得极少部分多径分量上有着CIR的绝大多数能量，即CIR能量不是均匀分布在信道的全部抽头上，呈现稀疏性。特别地，大规模MIMO的第 $\mathbf { m }$ 个发射天线和一个单接收天线的用户间形成的CIR可以表达为

$$
h _ { { \scriptscriptstyle m } , r } = \left[ h _ { { \scriptscriptstyle m } , r } ( 1 ) , h _ { { \scriptscriptstyle m } , r } ( 2 ) , . . . , h _ { { \scriptscriptstyle m } , r } ( L ) \right] ^ { T }
$$

其中:r 代表第 $\mathrm { ~ \bf ~ r ~ }$ 个OFDM 符号， $\mathrm { ~ L ~ }$ 代表等效信道长度，$1 \leq m \leq M$ 。

用 $\Gamma _ { m , r }$ 表示 $h _ { { \scriptscriptstyle m } , r }$ 的支撑集，可表示为

$$
\Gamma _ { { m , r } } = \operatorname { s u p p } \{ h _ { { m , r } } \} = \{ \ell . | h _ { { m , r } } [ \ell ] | > \eta _ { { \mathrm { m i n } } } , 1 \le \ell \le L \}
$$

其中: $\eta _ { \mathrm { m i n } }$ 代表信道中噪声最小值。稀疏度 $\lambda _ { _ { m , r } } = \left| \Gamma _ { _ { m , r } } \right| _ { c }$ 是受实际传播环境和多径传播的稀疏特性所影响的，一般情况下$\lambda _ { m , r } \ll L$ 。

![](images/0ad1366ca7660f2da78aa7e427b2206ccbc29531e73de7521e1798dba21d8cb1.jpg)  
图1大规模MIMO空间共同稀疏性

在典型大规模MIMO中，基站侧的天线阵列是密集型的，天线间的间距与到达用户侧单天线的信号所经过的距离相比是相当小的，以至于可以忽略不计的，并且每一对收发天线之间的信道中存在公共的散射体。因此，基站侧的每一根天线与用户的单天线所展现出高度相似的路径延迟[18.19]，如图1。并且不同发送天线对之间的CIR的稀疏特性绝大部分也是重合的。这就是大规模MIMO信道的空间共同稀疏性，即对于第r个OFDM符号，不同发射天线保持相同的稀疏性，可以表达为

$$
\Gamma _ { 1 , r } = \Gamma _ { 2 , r } = . . . = \Gamma _ { M , r }
$$

# 1.2大规模MIMO信道的时间相关性

在时间方面，信道的路径增益变化慢很多[20]，因而显现出了时间相关性的特点，甚至是在快时变的情况下也有同样的特点。换句话说，尽管从一个OFDM符号到下一个OFDM符号，路径增益变化很大，但是路径延迟在连续的几个OFDM符号中几乎保持不变。这是因为时变信道中，路径延迟的变化时间与系统带宽成反比，而路径增益的相干时间与系统载波频率成反比[21]。也就是说，在路径增益的相干时间内，因为路径延迟几乎保持不变，连续G个OFDM符号的CIR保持不变的共同稀疏性，如图2所示，即

$$
\Gamma _ { m , r } = \Gamma _ { m , r + 1 } = . . . = \Gamma _ { m , r + G - 1 }
$$

![](images/a38d5e5b9f04b6ac3aeef1cb4046a1b61f10631e5742bc93db389e819700da0d.jpg)  
图2空时共同稀疏性示意图

综上，将空间共同稀疏性和时间相关性合称为时空共同稀疏性[22]。

# 2 大规模MIMO-OFDM系统模型

建立一个典型的FDD 模式大规模MIMO-OFDM系统，小区内基站侧天线数为 $\mathbf { M }$ ，单天线用户数为 $\mathrm { ~ \bf ~ K ~ }$ ，且 $\mathbf { M } _ { \gg } \mathbf { K }$ ，如图3所示。其中，OFDM符号的子载波总数为 $\mathbf { N }$ ，基站第 $\mathrm { ~ m ~ }$ 根天线发射的信号(包含数据和导频)为 $\pmb { S } _ { m } \in \mathbb { C } ^ { N \times 1 } ( m = 1 , 2 , . . . , M )$ 。那么，用户侧接收到的信号可表达为

$$
y = \sum _ { m = 1 } ^ { M } S _ { { \scriptscriptstyle m } } F h _ { { \scriptscriptstyle m } } + n
$$

T CP CP x'[n,0] 并串转换 V1 串并转换 Y[n，0] 1 . F T ： L   
xn,K-1 y[n,K-1] CP 并串转换 CP 串并转换 . + x[n.0] 1 Y[n,0] L I T ：   
x 1 F Y[ K-1] K

除去保护间隔和进行DFT变换后，用户侧根据导频分配方案 $\delta$ 从接收到的信息 $y$ 中提取出第 $\mathbf { r }$ 个OFDM符号中的导频信息 $y _ { r }$ ， $y _ { r }$ 可以表达为

$$
y _ { r } = \sum _ { m = 1 } ^ { M } d i a g \{ c _ { m } \} F | _ { \mathcal { S } } [  \begin{array} { c } { h _ { m , r } } \\ { O _ { ( N - L ) \times 1 } } \end{array} ] + \bar { \eta } _ { r } = \sum _ { m = 1 } ^ { M } C _ { m } F _ { L } | _ { \delta } h _ { m , r } + \bar { \eta } _ { r }
$$

$$
= \sum _ { m = 1 } ^ { M } \phi _ { { \scriptscriptstyle m } } h _ { { \scriptscriptstyle m } , r } + n _ { r }
$$

其中： $\delta$ 表示在一个OFDM符号中，导频所占子载波的位置信息。

本文导频设计方案为非正交化导频分配方案(详见第3节) $\phi _ { { _ m } } = C _ { { _ m } } F _ { { _ L } } \vert _ { \delta }$ ， $C _ { { \scriptscriptstyle m } } = d i a g \{ c _ { { \scriptscriptstyle m } } \}$ ， $\boldsymbol { c } _ { m } \in \mathbb { C } ^ { N _ { P } \times 1 }$ 表示第 $\mathrm { ~ m ~ }$ 根天线的导频幅值的集合。 $ { N _ { p } }$ 表示在一个OFDM符号里的导频数，即 $N _ { \scriptscriptstyle P } = \left| \delta \right| _ { \scriptscriptstyle C }$ 。 $\boldsymbol { \mathsf { \Pi } } _ { F }$ 表示大小为 $\Nu _ { \times } \Nu$ 的 DFT 矩阵， $\boldsymbol { F } _ { \scriptscriptstyle L }$ 是取 $\boldsymbol { \mathsf { \Pi } } _ { F }$ 的前L行， $\left. F _ { L } \right| _ { \mathcal { S } }$ 表示根据 $\delta$ 取 $\boldsymbol { F } _ { \scriptscriptstyle L }$ 的子矩阵, $n _ { \scriptscriptstyle r }$ 表示第 $\mathbf { r }$ 个OFDM符号在信道中的加性高斯白噪声向量。

将式(5)化简可得

$$
\begin{array} { r } { \pmb { y } _ { r } = \pmb { \phi } \tilde { \pmb { h } } _ { r } + \pmb { n } _ { r } } \end{array}
$$

$$
\boldsymbol { \phi } = [ \phi _ { _ 1 } , \phi _ { _ 2 } , . . . , \phi _ { _ M } ] \in \mathbb { C } ^ { N _ {_ P } \times M L }
$$

$$
\widetilde { \boldsymbol { h } } _ { r } = \left[ \boldsymbol { h } _ { 1 , r } ^ { \mathrm { T } } , \boldsymbol { h } _ { 2 , r } ^ { \mathrm { T } } , . . . , \boldsymbol { h } _ { M , r } ^ { \mathrm { T } } \right] ^ { T } \in \mathbb { C } ^ { M L \times 1 } \mathrm { ~ \textbf ~ { ~ o ~ } ~ }
$$

在大规模 MIMO-OFDM系统中， $N _ { P } \ll \mathrm { M L }$ 。因此式(6)是一个欠定方程，用传统的信道估计方法，如最小二乘(leastsquare,LS)算法不能可靠的进行估计。但是，经过上述的分析可知 $\tilde { h } _ { { } _ { r } }$ 是一个高维稀疏信号，因此，可以利用压缩感知理论从低维的 $\boldsymbol { y } _ { \ u { r } }$ 将 $\tilde { h } _ { { } _ { r } }$ 重构出来。

此外，利用1.1节所提到的大规模MIMO固有的空间共同稀疏性可以提高CS算法的重构性能。

令 $\boldsymbol { d } _ { \iota , r } = \left[ h _ { 1 , r } \mathopen { } \mathclose \bgroup \left( \ell \aftergroup \egroup \right) , . . . , h _ { M , r } \mathopen { } \mathclose \bgroup \left( \ell \aftergroup \egroup \right) \right] ^ { \mathrm { T } }$ ，进而对 $\tilde { h } _ { { } _ { r } }$ 进行重新排列，可以得到：

$$
\tilde { \boldsymbol { d } } _ { \boldsymbol { r } } = \left[ \boldsymbol { d } _ { 1 , \boldsymbol { r } } ^ { \mathrm { scriptscriptstyle T } } , \boldsymbol { d } _ { 2 , \boldsymbol { r } } ^ { \mathrm { scriptscriptstyle T } } , . . . , \boldsymbol { d } _ { L , \boldsymbol { r } } ^ { \mathrm { scriptscriptstyle T } } \right] ^ { T } \in \mathbb { C } ^ { M L \times 1 }
$$

同理， 今 $\pmb { \psi } _ { \prime } = \ \lbrack \pmb { \phi } _ { 1 } ^ { ( \ell ) } , \pmb { \phi } _ { 2 } ^ { ( \ell ) } , . . . , \pmb { \phi } _ { M } ^ { ( \ell ) } ] =$ [γi,Y2.,m.]∈CNp，那么进行重新排列后，可以表达为

$$
\boldsymbol { \psi } _ { = [ } \psi _ { _ { 1 } } , \psi _ { _ { 2 } , \dots , \psi _ { _ { L } } ] \in \mathbb { C } ^ { N _ { P } \times M L } }
$$

因此，式(8)可以整理为

$$
y _ { r } = \psi \tilde { d } _ { r } + n _ { r }
$$

经过上述利用无线大规模MIMO系统的共同稀疏性进行的转换变形， $\tilde { \boldsymbol { d } } _ { \boldsymbol { r } }$ 的稀疏性得到结构化处理，使稀疏性得到增强。

利用1.2节提到的时间相关性，大规模MIMO系统的空间共同稀疏性在相干时间的几个连续的OFDM符号内是几乎不变的。因此，在导频分配方案 $\boldsymbol { \delta }$ 下，对相干时间内连续的R个OFDM符号进行处理，式(9)可以整理为

$$
Y { = } 4 H { + } n
$$

$$
Y = [ y _ { r } , y _ { r + 1 } , . . . , y _ { r + R - 1 } ] \in \mathbb { C } ^ { N _ { P } \times R }
$$

$$
\begin{array} { r } { n = \left[ \eta _ { r } , \eta _ { r + 1 } , . . . , \eta _ { r + R - 1 } \right] \in \mathbb { C } ^ { N _ { P } \times R } \ , H = \left[ \tilde { d } _ { r } , \tilde { d } _ { r + 1 } , . . . , \tilde { d } _ { r + R - 1 } \right] \in \mathbb { C } ^ { M \times R } \ \mathrm { , } } \end{array}
$$

并且 $H$ 亦可以表达为 $H { = } \left[ \begin{array} { l } { H _ { 1 } ^ { \mathrm { r } } , H _ { 2 } ^ { \mathrm { r } } , { \ldots } { \ldots } , H _ { L } ^ { \mathrm { r } } } \end{array} \right] ^ { \mathrm { T } }$ 。

利用无线大规模MIMO信道的时间相关性，在(9)的基础上，进一步使信道CIR矩阵结构化得到(10)，提升稀疏性，更好的提升CS 算法的估计性能。

# 3 非正交化导频设计方案

导频对于信道估计有着至关重要的作用，优秀的导频设计方案可以极大地提升信道估计的性能，如果设计的导频方案不合理或者不适合当前系统，不仅不能进行准确的信道估计，甚至增加导频开销，浪费宽带资源和能量。

# 3.1正交化与非正交化导频

传统正交化导频设计方案是在奈奎斯特采样定理的框架下设计的，它要求不同天线上的导频占据不同的子载波，并且天线上已安排了导频的子载波在其他天线相对应的位置上被要求安排成空导频。现下，正交化的导频设计方案已经被广泛的使用在现存的MIMO系统中，因为天线数量很少，所以导频开销不是很严重的问题，如8天线的LTE-advanced系统。但是，当发展到大规模MIMO时，基站侧天线配置量达到128根乃至更多时，这个问题就不能再忽视了，导频开销会非常严重，造成极大的能源和频谱浪费。

基于上述问题，我们根据文献[23]，在本文应用了非正交化导频设计方案,它是基于CS理论进行设计的。与传统正交化导频方案不同，它允许不同天线上的导频完全占据相同的子载波。通过利用大规模MIMO天然固有的稀疏性，使用于信道估计的导频开销可以实质性的降低。

![](images/8353cc09b27cd0ac34741f9f4f4a0aedd6a0dde2aca0d5360a65b5d49352247a.jpg)  
图4正交化和非正交化导频设计方案

# 3.2非正交化导频设计理论推导

在CS 理论中，根据文献[23]，式(10)中感知矩阵 $\psi$ 的设计对于可以高效可靠压缩高维稀疏信号 $H$ 是非常重要的。在大规模 MIMO 信道估计中， $\psi$ 只由导频分配方案 $\boldsymbol { \delta }$ 和导频序列{cm}_决定确定，所以对ψ的设计可以转化成为对δ和{Cm}的设计。根据CS理论可知，如果ψ具有列之间的相关性，对于进行可靠的恢复稀疏信号是非常有帮助的。这也就启发了对 $\boldsymbol { \delta }$ 和 $\left\{ { \pmb { c } } _ { m } \right\} _ { m = 1 } ^ { M }$ 的设计思路。

首先从导频序列 $\left\{ { \pmb { C } } _ { m } \right\} _ { m = 1 } ^ { M }$ 设计的角度着手研究，目的在于使得 $\psi _ { \iota }$ 中的任意 $\ell$ 列之间具有的互相关性较小。而这种互相关性只由 $\left\{ { \pmb { C } } _ { m } \right\} _ { m = 1 } ^ { M }$ 本身决定，即

$$
\left( \psi _ { m _ { 1 } , \ell } \right) ^ { H } \psi _ { m _ { 2 } , \ell } = \left( \psi _ { \ell } ^ { ( m _ { 1 } ) } \right) ^ { H } \psi _ { \ell } ^ { ( m _ { 2 } ) } = \left( \Phi _ { m _ { 1 } } ^ { \ell } \right) ^ { H } \Phi _ { m _ { 2 } } ^ { \ell }
$$

$$
\begin{array} { r } { \mathbf { \sigma } = \left( \pmb { C _ { m _ { 1 } } } \circ \pmb { F _ { c } ^ { ( \ell ) } } \right) ^ { H } \left( \pmb { C _ { m _ { 2 } } } \circ \pmb { F _ { c } ^ { ( \ell ) } } \right) = \left( \pmb { C _ { m _ { 1 } } } \right) ^ { H } \pmb { C _ { m _ { 2 } } } } \end{array}
$$

其中：F=Flε，1≤m≤m≤M。

为了获得较小的 $\left| \left( \psi _ { m _ { 1 } , \ell } \right) ^ { H } \psi _ { m _ { 2 } , \ell } \right|$ ，因此假设 $\left\{ \theta _ { k , m } \right\} _ { k = 1 , m = 1 } ^ { N _ { p } , M }$ 遵循独立同分布的均匀分布 $U [ 0 , 2 \pi )$ ，其中 $e ^ { j \theta _ { k , m } }$ 表示 $\boldsymbol { c } _ { m } \in \mathbb { C } ^ { N _ { P } \times 1 }$ 的第 $\mathbf { k }$ 个元素。并且 $\psi$ 的每一列的 $\boldsymbol { \ell } _ { 2 }$ 范数都为常量，即lym.l=√N,。此时可以得

$$
\operatorname* { l i m } _ { N _ { p } \to \infty } \frac { \left| \left( \psi _ { m _ { 1 } , \ell } \right) ^ { H } \psi _ { m _ { 2 } , \ell } \right| } { \left\| \psi _ { m _ { 1 } , \ell } \right\| _ { 2 } \left\| \psi _ { m _ { 2 } , \ell } \right\| _ { 2 } } = \operatorname* { l i m } _ { N _ { p } \to \infty } \frac { \left( C _ { m _ { 1 } } \right) ^ { H } C _ { m _ { 2 } } } { N _ { p } } = 0
$$

根据随机矩阵理论（randommatrix theory,RMT)，并且在实际状况下的 $\boldsymbol { N } _ { p }$ 是有限的，因此根据式(12)可得，非正交化导频序列 $\left\{ c _ { m } \right\} _ { m = 1 } ^ { M }$ 可以使得 $\psi _ { \ell }$ 中的任意 $\mathbf { \ell } _ { \ell }$ 列之间具有良好的互相关性。

其次从导频分配方案δ设计的角度继续深入研究.，与Ym,的互相关性。在lC的情况下，δ的设计也可以获得较小的(m,4) Ym2,l

在典型的大规模 MIMO 系统中，存在 $N _ { { p } } > L$ 的特点。例如，在典型的基站侧配置128根天线的大规模MIMO系统中，每根天线上至少要有一个导频才可以保证该天线可以进行信道估计，因此在该系统中，导频数量至少也要是128。此外，信道最大的时延拓展是 $3 \sim 5 \mu s$ 并且典型的LTE-Advanced 系统的带宽是 ${ \boldsymbol { 1 0 } } \mathbf { M } \mathbf { H } \mathbf { z }$ ，因此 $L \leq 1 2 8$ [24]。综上所述，导频数 $\boldsymbol { N } _ { p }$ 必须大于L。

基于 $N _ { \mathnormal { p } } > L$ 这个条件，如果用均匀间隔的方式进行导频分  
配不仅使用范围更宽泛，而且可以使得 $\left| \left( \psi _ { m _ { 1 } , \ell } \right) ^ { H } \psi _ { m _ { 2 } , \ell } \right|$ 更小。均  
匀导频间隔为 $\left\lfloor \frac { N } { N _ { p } } \right\rfloor$ 可将 $\psi _ { m _ { 1 } , \ell _ { 1 } }$ 与 $\psi _ { { m _ { 2 } } , \ell _ { 2 } }$ 的内积表达为  
（204号 $\psi _ { m _ { 2 } , \ell _ { 2 } } = \left( \mathcal { P } _ { m _ { 1 } } ^ { \ell _ { 1 } } \right) ^ { H } \phi _ { m _ { 2 } } ^ { \ell _ { 2 } }$ （204号$\begin{array} { r l } & { \quad = \left( C _ { m _ { \mathrm { s } } } \circ F _ { c } ^ { \left( t \right) } \right) ^ { H } \left( C _ { m _ { \mathrm { s } } } \circ F _ { c } ^ { \left( t _ { 2 } \right) } \right) } \\ & { \quad = \displaystyle \sum _ { k = 1 } ^ { N _ { r } } \mathrm { e x p } \Bigg [ j \frac { 2 \pi } { N } \ell _ { 1 } I \left( k \right) + j \theta _ { k , m _ { \mathrm { s } } } \Bigg ] ^ { H } } \\ & { \quad \quad \times \displaystyle \sum _ { k = 1 } ^ { N _ { r } } \mathrm { e x p } \Bigg ( j \frac { 2 \pi } { N } \ell _ { 2 } I \left( k \right) + j \theta _ { k , m _ { 2 } } \Bigg ) } \\ & { \quad \quad \quad \quad \quad = \displaystyle \sum _ { k = 1 } ^ { N _ { r } } \mathrm { e x p } \Bigg ( j \frac { 2 \pi } { N } \bar { \ell } I \left( k \right) + j \Delta \theta _ { k , m } \Bigg ) } \end{array}$ (13)

其中： $\{ I ( k ) \} _ { k = 1 } ^ { N _ { p } } = \xi$ 是导频子载波的索引集，$1 \leq \tilde { \ell } = \ell _ { _ 2 } - \ell _ { 1 } \leq L - 1 ~ , ~ \Delta \theta _ { k , m } = \theta _ { k , m _ { 2 } } - \theta _ { k , m _ { 1 } }$ 。并且 $\{ I ( k ) \} _ { k = 1 } ^ { N _ { p } }$ 是根据均匀导频间隔 $\left\lfloor { \frac { N } { N _ { p } } } \right\rfloor$ 从集合 $\{ 1 , 2 , 3 , . . . , N \}$ 中得到的；$I \left( k \right) = I _ { 0 } + \left( k - 1 \right) \left\lfloor \frac { N } { N _ { p } } \right\rfloor , \quad 1 \leq k \leq N _ { p }$ ，其中： $I _ { 0 }$ 是第一个导频的子载波集合且1≤I≤ $1 \leq I _ { 0 } \leq \left\lfloor \frac { N } { N _ { p } } \right\rfloor .$

因此，式(13)也可以表达为

$$
\left( { \psi } _ { m _ { 1 } , \ell _ { 1 } } \right) ^ { H } { \psi } _ { m _ { 2 } , \ell _ { 2 } }
$$

$$
= \sum _ { k = 1 } ^ { N _ { p } } \mathrm { e x p } \left( j \frac { 2 \pi } { N } \tilde { \ell } \left( I _ { 0 } + ( k - 1 ) \left\lfloor \frac { N } { N _ { p } } \right\rfloor \right) + j \Delta \theta _ { k , m } \right)
$$

$\varepsilon = \frac { N } { N _ { _ p } } - \left\lfloor \frac { N } { N _ { _ p } } \right\rfloor ( \varepsilon \in [ 0 , 1 ) )$ ，进一步对式(14)进行整理可得

$$
\left( { \psi } _ { m _ { 1 } , \ell _ { 1 } } \right) ^ { H } { \psi } _ { m _ { 2 } , \ell _ { 2 } }
$$

$$
= r _ { 0 } \sum _ { k = 1 } ^ { N _ { p } } \mathrm { e x p } \left( j \frac { 2 \pi } N \tilde { \ell } _ { k } \left( \frac N { N _ { p } } - \varepsilon \right) + j \Delta \theta _ { k , m } \right)
$$

其□ $r _ { 0 } = \exp \left( j \frac { 2 \pi } { N } \tilde { \ell } \left( I _ { 0 } - \frac { N } { N _ { p } } \right) \right) \mathfrak { c }$

考虑当 $m _ { 1 } = m _ { 2 }$ 时的情况，此时有 $\Delta \theta _ { \boldsymbol { k } , m } = 0$ ，则式(15)可化简为

$$
\left( \psi _ { m _ { 1 } , \ell _ { 1 } } \right) ^ { H } \psi _ { m _ { 2 } , \ell _ { 2 } } = r _ { 0 } \sum _ { k = 1 } ^ { N _ { p } } \mathrm { e x p } \Bigg ( j \frac { 2 \pi } { N } \tilde { \ell } _ { k } \left( 1 - \eta \varepsilon \right) \Bigg )
$$

其中： $\eta = \frac { N _ { p } } { N } < 1$ 表示导频占比。因此当 $\eta \varepsilon \approx 0$ ，此时，可以得到：

$$
\begin{array} { c } { { \displaystyle \operatorname* { l i m } _ { N _ { p } \to \infty } \frac { \left( \psi _ { m _ { 1 } , \ell _ { 1 } } \right) ^ { H } \psi _ { m _ { 2 } , \ell _ { 2 } } } { N _ { p } } } } \\ { { = \displaystyle \operatorname* { l i m } _ { N _ { p } \to \infty } \frac { r _ { 0 } \left( 1 - e ^ { j 2 \pi \tilde { \ell } ( 1 - \eta \varepsilon ) } \right) } { N _ { p } \left( 1 - e ^ { j \frac { 2 \pi } { N _ { p } } \tilde { \ell } ( 1 - \eta \varepsilon ) } \right) } = 0 } } \end{array}
$$

其中：由于 $1 \leq \tilde { \ell } \leq L - 1$ 和 $L < N _ { p }$ ，则 $e ^ { j \frac { 2 \pi } { N _ { p } } \widetilde { \ell } ( 1 - \eta \varepsilon ) } \approx e ^ { j \frac { 2 \pi } { N _ { p } } \widetilde { \ell } } \neq 1$ 保证了式(17)的合理有效性。

考虑当 $m _ { 1 } \neq m _ { 2 }$ 时的情况，则式(15)可以表示为

$$
\left( \psi _ { m _ { 1 } , \ell _ { 1 } } \right) ^ { H } \psi _ { m _ { 2 } , \ell _ { 2 } } = \sum _ { k = 1 } ^ { N _ { p } } \mathrm { e x p } \left( j \tilde { \theta } _ { k } \right)
$$

其中： $\tilde { \theta } _ { k } = \frac { 2 \pi } { N } \mathbf { \tilde { \Omega } } / I ( k ) + \Delta \theta _ { k , m }$ 遵循独立同分布的均匀分布$U [ 0 , 2 \pi )$ 且 $1 \leq k \leq N _ { p }$ 。类似于式(12)，可以得到

$$
\operatorname* { l i m } _ { N _ { p } \to \infty } \frac { \left( \psi _ { m _ { 1 } , \ell _ { 1 } } \right) ^ { H } \psi _ { m _ { 2 } , \ell _ { 2 } } } { N _ { p } }
$$

$$
\underset { N _ { p }  \infty } { = \operatorname* { l i m } } \frac { \underset { k = 1 } { \overset { N _ { p } } { \sum } } \mathrm { e x p } \big ( j \tilde { \theta } _ { k } \big ) } { N _ { p } } = 0
$$

综上所述， $\boldsymbol { N } _ { p }$ 有限的实际情况下，根据RMT，对于 $\psi$ 的任意两列间，式(12)(17)(19)的渐进正交性表明了非正交化导频分配方案 $\boldsymbol { \delta }$ 和导频序列 $\left\{ { \pmb { C } } _ { m } \right\} _ { m = 1 } ^ { M }$ 都获得了很好的互相关性。此外，在基于CS 理论的信道估计技术中，相较于广泛使用的传统随机导频分布方案[251，均匀间隔导频分布方案在现实环境下更容易实施。更重要的是，均匀间隔导频分布方案已广泛应用在现阶段的蜂窝网络中，因此它使大规模MIMO系统可以更好地向后兼容进现阶段蜂窝网络。

# 4 改进方案

# 4.1稀疏度自适应原理

在实际通信环境中，信道的稀疏度是未知的，并且信道状态随时间或者空间的变化而变化。因此，为了更好的可以在工程中应用，我们以阈值思想为基础，提出动态稀疏度自适应改进方案。不同于传统重构算法根据稀疏度确定迭代次数，该方案是通过设定阈值来确定迭代次数的，即当残差和观测值之间处于停止迭代参数所要求的比值关系时算法停止迭代。并且，停止迭代参数并不是定值，它在不同信道状态下，停止迭代参数也不同。信道状态我们用SNR来表征。据此，可表示为

$$
\left\| \boldsymbol { V } _ { k } \right\| _ { 2 } \leq \beta \times \left\| \boldsymbol { Y } \right\| _ { 2 }
$$

其中： $V _ { _ k }$ 表示残差， $\gamma$ 表示观测值。 $\beta$ 表示停止迭代参数，它不是一个固定的值，它在不同 SNR下是不同的。

综上所述，可以得知动态稀疏度自适应方案有如下特点：a)稀疏度自适应；在稀疏度未知的情况下仍能通过公式(20)自行控制迭代次数，最后停止迭代并获得稀疏度，从而提高算法在实际工程应用的能力;b)停止迭代参数 $\beta$ 的动态设定；不同的信道状态下，噪声对观测值的影响也会有不同，因此停止迭代参数 $\beta$ 不能设定为一个固定的值，而应该在不同的信道状态下是不同的，用SNR表征信道状态，也就是说，不同SNR下，停正迭代参数 $\beta$ 是不同的。

在文献[26]中也提及了利用阈值的方法来使算法可以自适应获取稀疏度，但设定的停止迭代参数是定值，不能根据信道状态变化停止迭代参数，而本文提出的算法可以动态获取稀疏度。

# 4.2考虑稀疏度自适应的大规模MIMO压缩感知信道估计方案

利用稀疏信道空时共同稀疏性和稀疏度在未知情况下可自身获取的特点，从结构化和动态稀疏度自适应两个方面提升其重构性能，提出稀疏度自适应CoSaMP(SSA-CoSaMP)算法。

表1 SSA-CoSaMP 算法流程

SSA-CoSaMP算法具体如下：

输入：信号观测值 $\gamma$ ，观测矩阵 $\psi$ ，最大信道长度L，基站侧配置天线数M，连续 OFDM符号数R，算法停止参数 $\beta$ 。

输出：估计的CIR 矩阵

a)初始化：初始残差 $V _ { \mathrm { 0 } } = Y$ ；稀疏度 $S = 1$ ；循环次数 $k = 1$ ；支持集（204号 $\Omega _ { 0 } = \phi$

$$
\mathsf { b } ) \boldsymbol { Z } = \boldsymbol { \psi } ^ { H } V _ { \boldsymbol { k } }
$$

c)利用大规模MIMO空时共同稀疏性将余量多个向量合并成一个向量，即（20 $\begin{array} { r } { C \big ( \tau \big ) = \sum _ { r = 1 , i = 0 } ^ { R , M - 1 } \mathopen { } \mathclose \bgroup \left| Z ^ { ( \tau + i L , r ) } \aftergroup \egroup \right| ^ { 2 } \qquad , \qquad 0 \leq \tau \leq L - 1 } \end{array}$ 其中C(τ)=[c(O),.,C(L-1)’，Z("m,n)是Z的第 m行n列。

d) $\Omega = \Omega \cup \cup \operatorname { s u p p } \{ c \rangle _ { { \scriptscriptstyle 2 K } } \}$ 合并集合;  
e $) \Gamma = \Omega \bigcup [ \Omega + L ] \bigcup , \ldots , \cup [ \Omega + L ( M - 1 ) ]$ 合并集合；$\mathrm { f ) } \hat { H } _ { r } = \hat { S } _ { r } ;$

（204号 $^ { \mathrm { g ) } } V _ { \boldsymbol { k } } = y - 4 ^ { \boldsymbol { H } } \Delta \hat { h }$ 对余量进行更新;

h)若满足 $\left\| \boldsymbol { V } _ { k } \right\| _ { 2 } \leq \beta \times \left\| \boldsymbol { Y } \right\| _ { 2 }$ 则停止迭代；否则令 $k = k + 1 , S = S + 1$ 转步骤b)。

从改进后的SSA-CoSaMP算法流程可知，SSA-CoSaMP算法并不是根据提前给定的稀疏度来停止迭代，而是建立残差和观测矩阵间的关系，当满足设定条件时，自动停止迭代，从而实现了算法可以自适应获取稀疏度，为该算法在实际的信道估计中的工程应用提供可能。从SSA-CoSaMP流程可知，主要分为两部分，第一部分是对稀疏度 $s$ 的确定。算法在初始化阶段设定稀疏度 $S = 1$ ，然后利用循环迭代的方法最终得到满足停止迭代的稀疏度 $s$ ，参见上述算法中的步骤a)和h)。第二部分是在预设稀疏度 $s$ 的情况下，利用无线大规模MIMO信道的空时共同稀疏性特点，在对 $\phi$ 进行重构估计的过程中，每次迭代都可以同时对多个稀疏向量进行更新，对应于SSA-CoSaMP算法中的步骤 ${ \bf b } ) { \bf - g } )$ 。最终得到准确的稀疏度和信道CIR。

如果对CoSaMP算法只利用空时共同稀疏性而不考虑稀疏度自适应改进的话，我们将其称为结构化CoSaMP（即S-CoSaMP)算法。S-CoSaMP算法只能根据给定的稀疏度进行循坏迭代的次数，而不是由实际的信道状态进行判断是否结束算法。这样带来的后果有两种:a)算法已经重构出结果，但算法本身为了满足所给定的稀疏度却还需继续循环迭代，造成时间和能量的浪费；b)算法重构出的结果还不够精确，但是给定的稀疏度已经满足循环迭代的次数，迭代停止，造成估计的精度不足。在接下来的第6节仿真数据及结果分析中，给出了S-CoSaMP和SSA-CoSaMP算法的性能对比。

SSA-CoSaMP算法中 $\beta$ 在不同 SNR下是不同的。如果 $\beta$ 的值是固定的，而不是根据信道状态而动态变化的会直接对重构结果造成极其严重的影响。若 $\beta$ 设置的过小，那么会使算法的迭代次数增多，进而引起算法用时过长，不利于工程应用。相反，如果 $\beta$ 设值的过大，那么会造成算法迭代过早结束，重构出的结果误差过大，降低了算法的重构精度。所以， $\beta$ 的设置对重构精度和迭代时间都有至关重要的影响。因此，在接下来的第6节中，我们通过仿真实验确定参数 $\beta$ ，使之在满足重构精度的同时将可能的降低运算时间。

# 5 仿真结果及分析

大规模MIMO无线信道估计技术主要以均方误差(MSE)来评价其性能。可以从以下三个方面试验来体现：a）估计精度对比实验，估计出的多径分量与实际建模相对比，用直观的方法来表征估计性能;b）随导频数变化的性能仿真实验，导频数的降低必然会影响估计性能，用导频数变化来表征估计性能可以更好的反应估计算法是否能在降低导频开销的同时又不过多的影响估计性能；c）随SNR变化的性能仿真实验，SNR可以很好地反映信道状态，用SNR变化来表征估计性能可以很好地反映出估计算法在不同信道状态下的估计情况。所以本方案主要从以上三个方面的实验来说明方案的优越性。

本节利用MATLAB仿真软件对所提出的大规模MIMO-OFDM无线通信系统中的 SSA-CoSaMP算法进行性能验证。系统参数设为基站侧发射天线数量为128根，系统中系统子载波数为1024，信道多径数为256，连续OFDM符号数$\scriptstyle \mathrm { R = 5 }$ 且每个信道为独立同分布的瑞利衰落信道，导频分配方案为非正交化导频分配方案，噪声由零均值单位方差的复高斯随机变量组成。系统模型为国际电信联盟车载B(ITU-B)信道模型。仿真中，还对所提出的SSA-CoSaMP、S-CoSaMP、CoSaMP算法进行了比较。在性能的衡量方面，用归一化均方误差(NMSE)来作为指标。NMSE 越小，估计出来的结果误差就越小，则表明估计性能就越好。

在本章中，均方误差归一化表示，即NMSE，并如下定义，用来作为信道估计性能的衡量指标。

$$
\mathrm { N M S E } = \frac { 1 } { M R } \mathrm { E } \left\| \hat { h } - h \right\| _ { F } ^ { 2 }
$$

作为对比的算法，CoSaMP算法参考文献[27]，S-CoSaMP算法参考文献[28]。

# 5.1停止迭代参数 $\beta$ 的确定

随着信噪比的不断降低，噪声对信号观测值Y的影响将会增大，因此在不同信噪比下， $\beta$ 也会相应变化。本节从对比思想的角度考虑，利用ExactLS 算法来获取 $\beta$ 在不同 SNR下的值。

信道估计算法一般可分为两个阶段，第一阶段，估计重构出抽头所在的位置；第二阶段，估算出该位置抽头的值。而ExactLS 算法直接给定了抽头所在的准确位置，只需估算出该位置抽头的值即可。故而ExactLS算法代表了CS类估计算法的性能基准。因此，在本节实验中，将 $\beta$ 逐渐变化的SSA-CoSaMP算法与ExactLS算法进行NMSE对比。当恰好使两者NMSE相等的 $\beta$ ，就是该SNR下 $\beta$ 的取值。

![](images/999d669a1b11d647749a7db9832cb96a332d4052c153d510021e4890882a7ab5.jpg)  
(b) SNR=20dB

![](images/69dfbed71000c21ffa4ed449e38293be6a341d6eee97a2203e801e8ffc33725e.jpg)  
图5不同 SNR下的停止迭代参数 $\beta$

图5(a)中， $_ { \beta = 0 . 0 5 8 }$ 时，两者的NMSE恰好相等。当大于0.058时，两者NMSE不一致。当小于0.058时，虽然两者NMSE相等，但不是恰好达到相等的临界取值。

同理,根据图5(b)和图5(c)的实验仿真结果,可以归纳出 $\beta$ 取值范围，如表2所示。

表2与SNR相对应的算法停止参数 $\beta$   

<html><body><table><tr><td>SNR</td><td>对应的β</td></tr><tr><td><10dB</td><td>0.058(图5(a))</td></tr><tr><td>10dB—25dB</td><td>0.054(图5(b))</td></tr><tr><td>>25dB</td><td>0.052(图5(c))</td></tr></table></body></html>

# 5.2信道估计算法的精度对比实验

对算法估计出结果的优劣判断可以从两个方面来考察，即估计出抽头的位置和幅值。因此，本节将算法估计出的结果与实验所构建的信道模型进行以上两个方面的对比来验证其性能。

图6(a)是在 $\mathrm { S N R } { = } 2 0 \mathrm { d B }$ 且导频数为700时进行试验的仿真图。根据实验结果可知，CoSaMP算法估计出的结果无论是抽头的位置还是幅值都不准确；而S-CoSaMP算法的结果也只有部分抽头的位置准确，其他结果的抽头位置和幅值都不准确。相比之下，SSA-CoSaMP算法准确了很多，估计出的抽头无论位置还是幅值都很准确。

当 $\mathbf { S N R } { = } 2 0 \mathbf { d B }$ ，导频数为900时，我们将算法估计出的结果和实验建模进行了对比仿真，可以得到图6(b)。根据实验结果可得出，此时CoSaMP算法仍然不能进行准确的估计，而SSA-CoSaMP算法和S-CoSaMP算法的估计性能基本一致，都非常准确。

![](images/b756f44b1267193fc8d769f9d9b35e7532142528d3ff93e3c258654414921616.jpg)

![](images/fcbbbaa32beda6f9dc19dd7c7a9e73a7860b45d24f0d1924b1f367c29efffc54.jpg)  
图6不同的信道估计算法的准确性对比( $\mathrm { S N R } { = } 2 0 \mathrm { d B }$ 门

# 5.3信道估计算法随导频数变化的性能仿真

导频是在基站侧被安排在OFDM 符号某部分特定子载波上的特殊数据，接收端根据收到的导频来对信道进行估计。导频数据占用了一定的传输资源。为了提高系统的频谱效率，必然要降低导频数据在每一帧OFDM符号中的比例，而降低导频数势必会影响估计性能。因此，进行导频数变化对信道估计算法性能影响的仿真试验是十分必要的。

![](images/1f8848aaf84c9527cc12f7b1cb907a49049f292c0f0c9a697f0d0fb4c0f40b7b.jpg)  
图7提出算法随导频数变化的NMSE性能对比

图7是SNR为10dB 和20 dB 时，SSA-CoSaMP算法、S-CoSaMP算法和CoSaMP算法的NMSE 随导频数增加而变化的仿真图。从实验结果可以得出，在不同SNR下，随着导频数的不断增加，三种算法的估计性能都有所改善。当导频数低于750时，SSA-CoSaMP算法的性能最优良，其次是S-CoSaMP算法，而CoSaMP算法的估计性能最差。当导频数高于750时，S-CoSaMP和SSA-CoSaMP算法的估计性能基本一致。

# 5.4信道估计算法随SNR变化的性能仿真

除了第5.3节仿真的导频数变化对估计算法的性能有所影响外，还有一个参数对估计算法的性能也有很大的影响，那就是SNR。为了进一步验证算法的性能与SNR的变化之间的关系，所以本节进行了信道估计算法随SNR变化的性能仿真的实验。图8是信道估计算法随 SNR变化的NMSE仿真图。并且分别选取了导频数为650、750、850时的情况，使实验结果更清晰准确。

从图8(a)可以得知，当导频数为650时，SSA-CoSaMP算法的性能比S-CoSaMP算法优秀了许多。而CoSaMP算法随着

SNR的增加并没有明显变化，处于无法进行出有效运算的状态。该实验结果表明了改进后的算法在低导频的情况下，仍能很好的估计出信道状态，换言之，在要求较低导频开销的情况下，只有SSA-CoSaMP算法才能较好的估计出信道状态。从图8(b)可以得，当导频数提高到750 时，SSA-CoSaMP算法略优于S-CoSaMP。但对于CoSaMP算法，导频数提高到750仍然无法使其进行有效运算。

图8(c)是导频数提高到850的仿真图。当SNR低于15dB。SSA-CoSaMP算法仍优于S-CoSaMP算法；当SNR高于15dB时，SSA-CoSaMP和S-CoSaMP算法的估计性能基本一致。

![](images/feeeca1aa221b8b214b918fe362ae0ee7e36b0dd2b2ace4d8fe69560138fc499.jpg)  
图8提出算法的NMSE性能对比

综合本节的仿真数据可知，CoSaMP算法在任何情况下性能都远不及S-CoSaMP算法和SSA-CoSaMP算法，而当导频数小于750，SSA-CoSaMP算法的性能优于S-CoSaMP算法，并且SSA-CoSaMP算法对稀疏度有自适应能力，更适用于稀疏度未知的实际环境。实验结果表明了SSA-CoSaMP算法增强了稀疏性，同等估计性能条件下，降低了导频开销，节省了频谱资源，在低导频开销的情况下，SSA-CoSaMP更具有优势。

# 6 结束语

本章根据大规模MIMO信道所特有的空时共同稀疏性的这个重要特征入手，从动态稀疏度自适应和结构化两方面对CoSaMP算法进行改进，提出SSA-CoSaMP算法。不仅优化了估计性能，同时还降低导频开销，节省能源消耗和频谱资源。符合我国对于绿色通信成为发展趋势的要求。仿真结果表明，无论是低导频，还是低SNR的状况下，所提出的方法相对传统基于导频的信道估计方法都有明显的性能增益。

在无线通信环境下，结构化特性不仅存在于实际的延迟多径域中，虚拟角度延迟域也存在稀疏度结构化特性的特点。因此，接下来的研究工作主要针对大规模MIMO天线阵列产生的虚拟角度域中稀疏度结构化的问题，使结构化改进方案可以在虚拟角度域中应用，深入探究结构化的使用范围，提升该方案的适用性。

# 参考文献：

[1]Ali E,Ismail M,Nordin R,et al. Beamforming techniques for massive MIMO systems in 5G:overview,classification，and trends for future research [J]. Journal of Zhejiang University Science C,2O17,18(6): 753-772.   
[2]Han Yonghee,Wonjae Shin,Jungwoo Lee.Projection-Based Differential Feedback for FDD Massive MIMO Systems [J].IEEE Trans on Vehicular Technology,2017,66 (1): 202-212.   
[3]Wang Bichai，Dai Linglong，Wang Zhaocheng，et al. Spectrum and energy-efficientbeamspaceMIMO-NOMAformillimeter-wave communications using lens antenna array [J].IEEE Journal on Selected Areas in Communications,2017,35 (10): 2370-2382.   
[4]Zhang Jiayi,Dai Linglong,Li Xu,et al.On low-resolution ADCs in practical 5G millimeter-wave massive MIMO systems[J].IEEE Communications Magazine,2018,56(7): 205-211.   
[5]Emil Bjornson, Jakob Hoydis,Marios Kountouris,et al.Massive MIMO systems with non-ideal hardware:energy efficiency，estimation，and capacity limits [J].IEEE Trans on Information Theory,2015,60(11): 7112-7139.   
[6]Sun Xiaoyu, Gao Xiqi,Li Geoffrey,et al.Agglomerative user clustering and downlink group scheduling for FDD massive MIMO systems [C]// Proc of IEEE International Conference on Communications.2O17: 1-6.   
[7] 杨昉，何丽峰，潘长勇.OFDM 原理与标准[M].北京：电子工业出版 社,2013.(Yang Fang,He Lifeng,Pan Changyong. OFDM Principles and Standards:Evolution of communication techniques[M]. Beijing: Publishing House of Electronics Industry, 2013)   
[8]Dai Linglong，Wang Zhaocheng，Yang Zhixing.Spectrally efficient time-frequency training OFDM for mobile large-scale MIMO systems [J] IEEE Journal on Selected Areas in Communications，2013，31 (2): 251-263.   
[9]Shen Wenqian,Dai Linglong,Shi Yi,et al. Joint channel training and feedback for FDD massive MIMO systems [J]. IEEE Trans on Vehicular Technology,2016,65 (10): 8762-8767.   
[10] Hou Weikun, Chia Wei Lim. Structured compressive channel estimation for large-scale MISO-OFDM Systems [J]. IEEE Communications Letters, 2014,18 (5): 765-768.   
[11] Shen Wenqian,Dai Linglong,Shi Yi,et al. Compressive sensing-based differential channel feedback for massive MIMO[J].Electronics Letters, 2015,51 (22): 1824-1826.   
[12] Zhu Xudong,Dai Linglong,Gui Guan,et al. Structured matching pursuit for reconstruction of dynamic sparse channels [C]// Proc of IEEE Global Communications Conference. 2015: 1-5.   
[13] Gao Zhen,Dai Linglong，Wang Zhaocheng，et al.Spatiallycommon sparsity based adaptive channel estimation and feedback for FDD massive MIMO [J]. IEEE Trans on Signal Processing,2015,63 (23): 6169-6183.   
[14] Shen Wenqian,Dai Linglong,Shi Yi,et al. Joint channel training and feedback for FDD massive MIMO systems [J]. IEEE Trans on Vehicular Technology,2016,65 (10): 8762-8767.   
[15] Qin Qibo,Gui Lin,Gong Bo,et al. Structured distributed compressive channel estimation over doubly selective channels [J].IEEE Trans on Broadcasting,2016, 62 (3): 521-531.   
[16] Uwaechia,AN,Mahyuddin N M.A review on sparse channel estimation in ofdm system using compressed sensing [J]. IETE Technical Review, 2017, 34 (5): 514-531.   
[17] Gao Zhen, Zhang Chao,Wang Zhaocheng,et al. Priori-information aided iterative hard threshold:a low-complexity high-accuracy compressive sensing based channel estimation for TDS-OFDM[J].IEEE Trans on Wireless Communications,2015,14(1): 242-251.   
[18] Zhang Jiankang，Zhang Bo，Chen Sheng，et al. Pilot contamination elimination for large-scale multiple-antenna aided OFDM systems [J]. IEEE Journal of Selected Topics in Signal Processing，2014，8 (5): 759-772.   
[19] Santos Telmelmo,Karedal Johan，Almers Peter，et al.Modeling the ultra-wideband outdoor channel: Measurements and parameter extraction method [J]. IEEE Trans on Wireless Communications，2010,9(1): 282-290.   
[20] Telatar IE,Tse D.Capacity and mutual information of wideband multipath fading channels [J]. IEEE Trans on Information Theory,1998,46 (4): 1384-1400.   
[21] Dai Linglong，Gao Zhen,Wang Zhaoceng，et al. Spectrum-efficient superimposed pilot design based on structured compressive sensing for downlink large-scale MIMO systems [C]//Proc of General Assembly and Scientific Symposium. 2014: 1-4.   
[22] Gao Zhen,Dai Linglong，Yuen Chau,et al.Asymptotic orthogonality analysis of time-domain sparse massive MIMO channels [J].IEEE Communications Letters,2015,19 (10): 1826-1829.   
[23] Gao Zhen，Dai Linglong,Dai Wei，et al.Structured compressive sensing-based spatio-temporal joint channel estimation for FDD massive MIMO [J].IEEE Trans on Communications,2015,64 (2): 601-617.   
[24] Zeng Zhaoquan,Fu Shu,Zhang Huihui,et al.A survey of underwater optical wireless communications [J]. IEEE Communications Surveys and Tutorials,2017,19(1): 204-238.   
[25] Bajwa W U, Haupt JD,Sayeed A M, et al. Compressed channel sensing: a new approach to estimating sparse multipath channels [J]. Proceedings of the IEEE,2010,98(6):1058-1076.   
[26]任晓奎，葛君，孙兴海．基于压缩感知改进算法的 MIMO-OFDM 稀疏 信道估计[J].计算机工程与应用,2016,52(17):112-117.(Ren Xiaokui, Ge Jun,Sun Xinghai. Sparse channel estimation based on modified algorithm for MIMO-OFDM systems [J]. Computer Engineerig and Applications,2016,52 (17): 112-117.)   
[27]杨真真，杨震，孙林慧．信号压缩重构的正交匹配追踪类算法综述[J]. 信号处理,2013,29 (4): 486-496.(Yang Zhenzhen, Yang Zhen,Sun Linhui H.A survey on orthogonal matching pursuit type algorithms for signal compression and reconstruction [J]. Journal of Signal Processing,2013,29 (4): 486-496. )   
[28] Dai Linglong,Gao Zhen，Wang Zhaocheng，et al. Spectrum-efficient superimposed pilot design based on structured compressive sensing for downlink large-scale MIMO systems [C]//Proc of General Assembly and

Scientific Symposium. 2014:1-4.