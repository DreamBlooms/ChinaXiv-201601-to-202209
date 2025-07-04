# 广义空一码联合索引调制

冯胜1，杨 勤²，郑鹤²，葛利嘉

(1.重庆邮电大学 移动通信技术重庆市重点实验室，重庆 40065;2.陆军工程大学通信士官学校，重庆 400035;3.重庆临菲电子科技有限公司，重庆 400041)

摘要：针对空间调制天线利用率低、广义空间调制传输速率低等问题，将广义空间调制和码索引调制相结合，提出广义空-码联合索引调制（generalised space code jointindex modulation，GSCJIM）。信息比特在发射端经串并转换后分别映射为伪随机（pseudonoise，PN）码索引、天线索引以及调制符号，调制符号的实部和虚部分别选择激活的伪随机码进行扩频，并通过激活的天线组合将信号发射出去。广义空间调制和码索引调制的结合，提升系统传输速率的同时也提高了天线的利用率，并且抗干扰性能显著增强。分析与仿真结果表明，在传输速率相同时，GSCJIM比广义空间调制节省了索引资源，并且当误比特率为10-3时具备5dB的性能优势。

关键词：高速率；性能优；码索引调制；广义空间调制 中图分类号：TN929.5 doi:10.3969/j.issn.1001-3695.2018.01.0046

# Generalized space code joint index modulation

Feng Shengl, Yang Qin², Zheng $\mathrm { H e } ^ { 2 }$ , Ge Lijia³ (1.Chongqing Key LaboratoryofMobileCommunication Technology,Chongqing UniversityofPast&Telecommunications, Chongqing 400065,China;2.Communication NCO AcademyofAmy Engineering University,Chongqing 40035,China; 3. Chongqing Lynchpin Electronic Technology Co,Ltd, Chongqing 40o041,China)

Abstract:Tosolve theproblems of space modulationantennautilizationand generalizedspatial modulationtransmisionrate arelow.In this paper,we propose a generalized spacecode joint index modulation,which combines generalized spatial modulationandcode index modulation.Theinformation bitsarerespectively mapped intoa (pseudo noise)PNcode ndex,an antenaindexandamodulationsymbolsafterseries-to-parallelconversionatthetransmitingnd.Therealandimaginaryparts of the modulation symbols respectively select theactivated pseudorandom codeto spread spectrum,and the signalsare transmitted through anactivated antenna combination.Thecombinationof generalized spatial modulationand code index modulationimprovesthetransmissonrateofthesystemandtheutilizationoftheantenna.Inadition,itsignificantlyenhances the anti-jamming performance.The analysis and simulation results show that GSCJIM saves index resource more than generalizedspace modulationatthesametransmisionrate,andithasthe performanceadvantageof5dB whenbiterrorrateis 10-3.

Key words: high data rate; excellent performance; code index modulation; generalized space modulation

# 0 引言

近年来，随着人们对高速数据传输速率和频带利用率的需求越来越高，无线通信技术也在迅猛发展。高速的数据传输速率和可靠的传输质量已经成为无线通信发展的必要前提。有限的频谱资源已不能满足用户快速增长的需求。随着空间调制与子载波索引调制的深入研究，人们把索引思想引入到扩频通信，索引调制[1-3]过程中，有一部分信息比特隐形传输，这部分信息比特不会消耗能量，从而提升了系统的信息传输速率和能量效率，并且还保持了扩频通信的高可靠性和良好的抗干扰性能，符合当前绿色通信[4]对实现传输速率与能量效率平衡的要求，对无线通信技术的发展有着非常重要的意义。

无线多输入多输出技术（multipe input multipe output，MIMO）在不增加系统带宽与发射功率的前提下有效提高系统容量和数据传输速率，在很大程度上提升了空间资源利用率[5-6]。空间调制[7-8]（spatialmodulation，SM）技术的提出是索引调制技术的一次重大突破，在发射端信息比特被分为两部分，一部分用于选择天线隐形传输，另一部分则用于传统的基带调制，空间调制在每个传输时隙只激活一根发射天线，因此信息的传输速率和天线的利用率较低。正交空间调制[9-10]（orthogonal spatialmodulation，QSM）与空间调制不同的是：QSM将调制符号分为同相和正交部分，这两部分各自选择一根激活天线将信号发送出去，这样一来就提升了天线的利用率。广义空间调制[11-13]（generalized spatialmodulation，GSM）在每个传输时隙激活的是天线组合，增加了信息的传输速率和天线利用率，但是对天线间同步要求比较高，在工程上实现较困难。

码索引调制[14-16]（code index modulation，CIM）技术的思想来源于空间调制，它是将空间调制的天线索引变为扩频码的索引，在发射端信息比特被分为扩频码索引部分和基带调制部分，基带调制部分又将信息比特调制成调制符号，调制符号的同相部分和正交部分再分别选择激活的扩频码进行扩频，然后将信号发送出去，码索引调制系统增加了信息传输速率和能量效率，并保留了扩频通信原有的抗干扰性能。

本文将结合广义空间调制和码索引调制，提出广义空-码联合索引调制，将索引的维度从一维增加到二维，增加隐形的信息传输比特，从而提高传输速率、降低能量消耗。在传输速率相同时，GSCJIM与GSM等方案进行索引资源使用情况对比分析。然后通过仿真验证本方案的误比特率（biterrorrate,BER）性能并与SM、QSM、GSM等方案对比。

# 1 系统调制方案设计

本方案调制的发射机模型如图1所示。收发端采用$N _ { r } \times N _ { t }$ 的MIMO天线配置，其中 $N _ { { r } }$ 是接收天线的数目，$N _ { { t } }$ 是发射天线的数目。

天线索引表G 天线选择 Tx_l9信息比特 串并转换 GMod 三 武 功率放大器 天线XGcode 并转换 选择 W -sin(2rfot)PN码GCPN码索引表

本方案在每一个传输时隙不止激活一根天线，假设每个时隙激活的天线数目是 $N _ { u }$ ，则激活的所有天线组合为 $N _ { c } ^ { ' } { = } { \binom { N _ { t } } { N _ { u } } } ,$ 其中（·）代表的是组合运算。然而发射天线的组合数目必须是2的整数次幂，也就是说只有 $N _ { c } = 2 ^ { m _ { l } }$ 种组合被使用，其中m=[log），L.]代表的是向下取整符号。假设本方案在每一个传输时隙发射信息比特 $\boldsymbol { q }$ 的长度为 $\log _ { 2 } ( N _ { c } N ^ { 2 } M )$ ，其中（204号 $N$ 代表的是扩频码维度，即 PN 码的个数， $M$ 为系统采用基带调制的调制阶数。信息比特经串并转换后被分为三个部分，分别是天线映射比特部分 $G _ { _ { A n t } }$ 、PN 码映射比特部分 $G _ { c o d e }$ 和调制信息比特部分 $G _ { M o d }$ ，其各自的长度分别为 $\log _ { 2 } ( N _ { c } )$ 、2log(N）、log(M）。PN码映射比特部分 Gcode再次经串并$\log _ { 2 } ( N )$ $G _ { C o d e } ^ { I }$ 序列长度为 $\log _ { 2 } ( N )$ 的正交 PN 码映射块 $G _ { C o d e } ^ { Q }$ ，信息比特 $q$ （20的分割方式如式（1）所示。

$$
\begin{array} { r l } & { q = \left[ b _ { 1 } , b _ { 2 } , . . . , b _ { i } , . . . , b _ { \mathrm { l o g } _ { 2 } \left( N _ { c } N ^ { 2 } M \right) } \right] } \\ & { \quad = \left[ { \cal G } _ { \scriptscriptstyle A n t } ; { \cal G } _ { \scriptscriptstyle C o d e } ; { \cal G } _ { \scriptscriptstyle M o d } \right] } \\ & { \quad = \left[ { \cal G } _ { \scriptscriptstyle A n t } ; { \cal G } _ { \scriptscriptstyle C o d e } ^ { I } , { \cal G } _ { \scriptscriptstyle C o d e } ^ { Q } ; { \cal G } _ { \scriptscriptstyle M o d } \right] } \end{array}
$$

其中： $b _ { i }$ 代表的是信息比特 $q$ 中第 $i$ 位比特。

调制信息比特部分 $G _ { { _ M o d } }$ 经传统的基带调制后变成调制符号 $x$ ，调制符号 $x = x _ { \mathrm { { R e } } } + j x _ { \mathrm { { I m } } }$ ，其中 $x _ { \mathrm { { R e } } } \mathrm { ~ , ~ } x _ { \mathrm { { I m } } }$ 分别代表的是调制符号 $x$ 的实部和虚部。然后进行PN 码索引映射和天线索引映射，在天线的映射过程中，根据天线映射块 $G _ { A n t }$ 查找天线索引表来选择需要激活的天线组合 $T x _ { - } l$ 。在PN 码索引映射过程中，分为同相部分和正交部分独立进行，且这两部分的映射过程完全一样，因此这里只阐述同相部分，同相PN码映射块 $G _ { C o d e } ^ { I }$ ，通过查找 PN 码索引表，选择激活的 PN 码 $w _ { m }$ ，其中 $w _ { m } = [ w _ { m , 1 } \cdots w _ { m , L } ]$ ， $m$ 代表的是同相激活PN 码的索引值， $L$ 代表的是PN码的长度。

接下来就要对调制好的符号进行扩频了，调制符号 $x$ 的实部 $\boldsymbol { x } _ { \mathrm { R e } }$ 经过激活的 PN 码 $w _ { m }$ 扩频后在通过余弦载波调制，经功率放大器后送往天线切换模块，天线切换模块快速将天线切换至激活的天线组合 $T x _ { - } l$ 上，然后将调制信号发射出去。调制符号 $x$ 的实部 $\boldsymbol { x } _ { \mathrm { R e } }$ 与虚部 $x _ { \mathrm { { I m } } }$ 调制原理一样且独立进行。

# 2 索引映射过程

本方案中PN码映射有同相部分和正交部分，均需要查找各自的索引映射表来选择激活的PN码，由于同相部分和正交部分是独立进行且映射过程完全一样，因此这里就只阐述同相部分。天线映射每次激活的是一种天线组合，因此分别建立PN码索引表和天线索引表。假设本系统采用的配置为（ $N _ { t } = 5 , N _ { u } = 2 , N _ { r } = 4 , N = 4 , M = 4$ ），经过计算可以得到同相PN码映射块可以映射2位信息比特。根据排列组合的知识，得到同相PN码索引表如表1所示。

表1PN码索引表  

<html><body><table><tr><td>同相 PN码映射块 （Gcole）</td><td>PN码索引值</td></tr><tr><td>00</td><td>（Wm） W1</td></tr><tr><td>01</td><td>W2</td></tr></table></body></html>

<html><body><table><tr><td>10</td><td>W3</td></tr><tr><td>11</td><td>W4</td></tr></table></body></html>

由表1可以看出，当同相 PN码映射块 $G _ { C o d e } ^ { I }$ 为01时，激活的PN码是 $w _ { 2 }$ ，此时调制符号的实部通过 $w _ { 2 }$ 扩频。

天线索引表的建立与PN码的索引表建立类似，由配置可计算得出天线映射块可以映射3位信息比特，根据排列组合的知识，得到天线索引表如表2所示。

表2天线索引表  

<html><body><table><tr><td>天线映射块 （GAm ）</td><td>天线索引组合值 (Tx_l)</td></tr><tr><td></td><td></td></tr><tr><td>000 001</td><td>(1,2)</td></tr><tr><td>010</td><td>(1,3)</td></tr><tr><td>011</td><td>(1,4)</td></tr><tr><td>100</td><td>(1,5) (2,3)</td></tr><tr><td>101</td><td>(2.4)</td></tr><tr><td>110</td><td>(2,5)</td></tr><tr><td>111</td><td>(3,4)</td></tr></table></body></html>

由表2可以看出，当天线映射块 $G _ { _ { A n t } }$ 为110时，激活的天线组合为（2.5），此时调制符号通过天线组合（2.5）发送。

信号星座图根据调制阶数来建立，由于本方案采用的基带调制阶数为4，那么调制映射块可以映射2位信息比特，因此建立信号星座图如图2所示。由图2可以看出，当调制部分$G _ { { _ M o d } }$ 为00时，调制符号 $x = - 1 - j$ 。

![](images/43eba90d1fcf6e14382e1deb7732633650e509c82a009fa7c2439eefcb5650c0.jpg)  
图2信号星座图  
图3系统接收机模型

假如本方案在某一个时隙发送的信息比特流为$q = 1 0 1 0 0 1 1 0 1$ ，由式（1）可以得到各映射块包含的信息比特依次为：天线映射块 $G _ { _ { A n t } } = 1 0 1$ 、同相 PN 码映射块$G _ { C o d e } ^ { I } = 0 0$ 、正交 PN 码映射块 $G _ { C o d e } ^ { Q } = 1 1$ 、调制部分$G _ { M o d } = 0 1$ 。调制部分 $G _ { { _ M o d } }$ 经基带调制后变成调制符号 $x$ ，星座表示为： $x = - 1 + j$ ，其中实部 $x _ { \mathrm { { R e } } } = - 1$ ，虚部 $x _ { \mathrm { { I m } } } = + 1$ 。$G _ { A n t }$ 、 $G _ { C o d e } ^ { I }$ 和 $G _ { C o d e } ^ { Q }$ 分别通过查找天线索引表和PN码索引表，$G _ { { _ { M o d } } }$ 查找信号星座图，可得到天线、PN 码索引映射和调制部分的关系如表3所示。

表3系统映射表  

<html><body><table><tr><td>GAnt</td><td>GCoe</td><td>Gode</td><td>GMod</td></tr><tr><td>(2,4)</td><td>W1</td><td>W4</td><td>-1+j</td></tr></table></body></html>

发射端调制符号 $x$ 的实部 $x _ { \mathrm { { R e } } } = - 1$ 通过同相 PN 码映射块 $G _ { C o d e } ^ { I }$ 激活的PN码 $w _ { 1 }$ 扩频，虚部 $x _ { \mathrm { { I m } } } = + 1$ 通过正交PN码映射块 $G _ { C o d e } ^ { Q }$ 激活的PN码 $w _ { 4 }$ 扩频。然后分别经载波调制后通过功率放大器、天线切换，再选择由天线映射块激活的组合（2.4)将信号发射出去。

# 3 系统解调方案设计

本方案接收机模型如图3所示，发射端的调制符号 $x$ 扩频后经信道矩阵 $H$ 和高斯白噪声 $n$ 到达接收端。假设在一个传输时隙内信道的参数保持恒定，并且在接收端具有理想的信道估计。其中信道矩阵 $\boldsymbol { H } \in \mathbb { C } ^ { N _ { r } \times N _ { t } }$ ，服从独立分布复高斯随机变量矩阵，其均值为0，方差为 $\sigma ^ { 2 }$ 。其中激活的某一天线组合 $l = ( l _ { 1 } , l _ { 2 } , . . . . , l _ { N _ { u } } ) \in \phi$ ， $l _ { n }$ 表示激活的某一天线组合 $l$ 中第$n$ 根天线， $\phi$ 代表的是所有的激活天线组合， $h _ { l } ^ { ' } = \sum _ { n = 1 } ^ { N _ { u } } { h _ { l } } _ { n }$ 代表的是激活天线信道向量之和， $h _ { l _ { n } }$ 代表的是矩阵 $H$ 的 $l _ { n }$ 列。$\boldsymbol { n } \in \mathbb { C } ^ { N _ { r } \times \mathbf { L } }$ 为 $N _ { r } { \times } L$ 的复加性高斯白噪声矩阵，其均值为0,方差为 $N _ { 0 }$ 。因此接收端经过射频下变频后的基带信号 $y$ 可以表示为

$$
y = { \frac { 1 } { \sqrt { N _ { u } } } } ( h _ { l } ^ { ' } x _ { \mathrm { { R e } } } w _ { m } + j h _ { l } ^ { ' } x _ { \mathrm { { I m } } } w _ { n } ) + n
$$

估计过程 天线索引表 射频下变频 检测激 GN 解映射 2 活天线 并串 q 财频下变频 检测号 XRe G 信 专 解调 转换 Wm Cce 射频下变频 解映射 Wn Goe PN码索引表

接收端的信息比特恢复包括两部分，第一部分是检测调制符号当前扩频的PN码索引值，第二部分就是通过估计的方式检测调制符号和激活的天线组合索引值。第一部分是整个解调的关键，只有确定了调制符号的同相支路和正交支路分别采用的PN码索引值后，才能正确解调恢复出调制符号和激活的天线组合索引值。

同相支路PN码相关检测首先是将接收信号Y的实部 YRe的每一行都要与 $N$ 个PN 码作相关运算，然后在一个码长 $L$ 内求和，则输出的表达式可表示为

$$
\begin{array} { r l } { \boldsymbol { r } _ { m ^ { ' } } = { y _ { \mathrm { R e } } } \boldsymbol { w } _ { m ^ { ' } } ^ { \mathrm { ~ \it ~ T ~ } } } & { { } \boldsymbol { m } ^ { ' } = 1 , 2 , . . . , N } \end{array}
$$

其中 ${ w _ { } } _ { m ^ { ' } } ^ { \phantom { \dagger } }$ 表示的是第 $m ^ { ' }$ 个 PN 码的转置。接下来就将相关输出值在接收天线维度间取绝对值并求和，然后再比较 $N$ 个相关输出值并找出最大值，最大值对应的索引值就是我们要找的扩频码索引值，其表达式如下：

$$
\hat { m } = \arg \operatorname* { m a x } _ { m } = \biggl \{ \sum _ { t = 1 } ^ { N _ { r } } \Bigl | r _ { m } \Bigr . , t \Bigr | \Biggr \}
$$

其中 arg代表的是当表达式取得最大值时 $m ^ { ' }$ 的取值是多少,$r _ { m ^ { ' } , t }$ 表示输出值 $r _ { \mathrm { { } } _ { m } ^ { \mathrm { ~ { ~ } } } }$ 的第 $t$ 行。这样我们就检测出发射端同相分量使用的 PN 码 $w _ { \hat { m } }$ 。正交PN 码 $\boldsymbol { w _ { \hat { n } } }$ 的检测过程与同相 PN码 $\boldsymbol { w _ { \hat { m } } }$ 的检测过程一样，这里就不再赘述。

当得知同相分量的PN码 $\boldsymbol { w } _ { \hat { m } }$ 和正交分量的PN 码 $\boldsymbol { w _ { \hat { n } } }$ 之后接下来就需要对接收端的信号进行解扩，由于同相解扩与正交解扩原理一样，简单起见这里只阐述同相解扩，接收信号 $y$ 的实部 $y _ { \mathrm { { R e } } }$ 的每一行与已知扩频码 $\boldsymbol { w _ { \hat { m } } }$ 作相关，然后在一个码长$L$ 内求和，求和以后再除以码长 $L$ ，这样就实现了信号的解扩，输出的表达式可以表示如下：

$$
{ r } _ { \hat { m } } = \frac { { y } _ { \mathrm { R e } } { w } _ { \hat { m } } ^ { \textit { T } } } { L }
$$

正交部分的解扩与同相部分解扩原理一样，得到同相与正交解扩部分以后，新的解扩信号可以表示如下：

$$
y y = \frac { y _ { \mathrm { R e } } { w _ { \hat { m } } } ^ { T } } { L } + \frac { y _ { \mathrm { I m } } j { w _ { \hat { n } } } ^ { T } } { L }
$$

接下来用最大似然估计的方法对调制符号的实部、虚部以及天线组合索引值进行估计，其表达式如下：

$$
\left[ \hat { l } , \hat { x } _ { \mathrm { { R e } } } , \hat { x } _ { \mathrm { { I m } } } \right] = \arg \operatorname* { m i n } _ { l , x _ { \mathrm { { R e } } } , x _ { \mathrm { { I m } } } } \left\| y y - \frac { 1 } { \sqrt { N _ { u } } } \left( { h } _ { l } ^ { ' } { x } _ { \mathrm { { R e } } } + j { h } _ { l } ^ { ' } { x } _ { \mathrm { { I m } } } \right) \right\| ^ { 2 }
$$

其中： $\hat { l } \in \phi$ ， $x _ { \mathrm { { R e } } } , x _ { \mathrm { { I m } } } \in \mathbb { C } _ { M o d }$ ， $\mathbb { C } _ { M o d }$ 代表的是调制符号正交分量与同相分量的星座集  
合。假如 $A = \left( a _ { i j } \right) \in C ^ { m \times n }$ ，则 $\left\| A \right\| = \left( \sum _ { i = 1 } ^ { m } \sum _ { j = 1 } ^ { n } \Bigl | a _ { i j } \Bigr | ^ { 2 } \right) ^ { \frac { 1 } { 2 } }$ 称为矩阵 $A$ 的 Frobenius 范数。

最后将检测到的调制符号的同相分量与正交分量合成调制符号 $\hat { x } = \hat { x } _ { \mathrm { { R e } } } + j \hat { x } _ { \mathrm { { I m } } }$ ，然后通过解调恢复出调制部分对应的信息比特 $\hat { G } _ { M o d }$ 。再将检测到的索引值 $\hat { l }$ 、 $\hat { m }$ 和 $\hat { n }$ 分别通过反向查找各自天线索引表和 PN 码索引表，解映射恢复出 $\hat { G } _ { A n t }$ 、$\hat { G } _ { C o d e } ^ { I }$ 和 $\hat { G } _ { C o d e } ^ { Q }$ 。最后通过并串转换的方式得到信息比特 $\hat { q }$ 。

# 4 分析与仿真

本小节将对本次提出的方案进行索引资源分析并通过仿真验证方案的性能，然后再与GSM、QSM等索引调制方案进行比较。仿真采用的是等效基带方法，且扩频码是 $L = 3 2$ 位的Walsh码。信道模型是相互独立的平坦瑞利衰落信道，仿真数据量为 $1 0 ^ { 5 }$ ，信噪比定义为 $\mathrm { E _ { s } / N _ { 0 } }$ 。仿真的主要参数在每个仿真图的左下角列出：从左到右依次表示的是方案名称、发射天线根数、接收天线根数、基带调制阶数、PN码的使用个数。下面提到的传输比特均为每一传输时隙的传输比特，也就是每个符号的比特数。

图4是在每一时隙相同传输比特时，本方案与GSM和CIM方案的索引资源对比图，各方案均采用4进制正交振幅调制（QuadratureAmplitudeModulation,QAM），且每一时隙只激活2 根发射天线。假如每一时隙的传输比特为10bits 时，本方案使用7根发射天线和4个PN码，而GSM和CIM方案分别需要24根发射天线和16个PN码。当传输比特增加到12bits时，本方案需要7根发射天线和8个PN码，而GSM和CIM方案分别需要50根发射天线和32个PN码。以上的发射天线根数和PN码的个数是根据数学中排列组合和对数函数计算而来的由此可以得到，在每一时隙传输比特数相同时，本次提出的方案比GSM和CIM方案需要更少的索引资源。

![](images/8e6ae12a39da71df58f47a3fcf3a618b9fdccaaf0d24968e888419c6bfd92922.jpg)  
图4不同方案间的索引资源对比

GSCJIM和GSM这两种方案的BER性能曲线如图5所示。由曲线 $\textcircled{1} \textcircled{3} \textcircled{4}$ 得，这三种方案在每一时隙都传送8bits，由 $\textcircled{1}$ 和 $\textcircled{3}$ 相比可以看出，本方案性能下降约 $1 { \sim } 2 \operatorname { d B }$ ，但 $\textcircled{3}$ 的天线配置却多于 $\textcircled{1}$ 。再将方案 $\textcircled{1}$ 和 $\textcircled{4}$ 进行相比，在保证天线配置相同时，要达到相同的传输速率，则只有增加方案 $\textcircled{4}$ 的调制阶数，此时由仿真图可以看出本方案的性能好了大约5dB。由曲线 $\textcircled{2} \textcircled{5} \textcircled{6}$ 得，这三种方案在每一时隙都传输10bits，由 $\textcircled{2}$ 和 $\textcircled{5}$ 相比可以看出，本方案在16dB以前保持了微弱的性能优势，并且 $\textcircled{5}$ 的天线配置多于 $\textcircled{2}$ 。再将方案 $\textcircled{2}$ 和 $\textcircled{6}$ 进行对比，在保证天线配置相同时，要达到相同的传输速率，则只有增加方案 $\textcircled{6}$ 的调制阶数，此时由仿真图可以看出本方案的性能远远好于方案 $\textcircled{6}$ ，由此可以得出：本方案在传输速率提高时，性能会优于广义空间在图6中，分别比较了GSCJIM方案中不同参数配置下的BER性能。由曲线 $\textcircled{1} \textcircled{2} \textcircled{3}$ 得，GSCJIM方案中PN码的使用个数分别为2、4、8，即扩频码的索引映射比特分别为2、4、6bit。表现为每增加2个传输比特，系统性能几乎不改变，由此我们可以增加扩频码的个数来提高传输速率。由曲线 $\textcircled{2} \textcircled{4} \textcircled{5}$ 得，GSCJIM方案中调制阶数分别为4、8、16，即基带调制比特分别为2、3、4bit。表现为每增加一个传输比特，系统的性能就下降 $1 { \sim } 4 \ \mathrm { d B }$ 。由曲线 $\textcircled{2} \textcircled{6}$ 得，GSCJIM方案中发射天线的根数分别是4根和7根，接收天线保持一致，即天线的索引映射值分别为2bits和4bits，增加了两个传输比特，系统的性能大概下降了1dB左右。

![](images/642d87e442cb251e532873040e10d99c7669c16787ac13b71a968661e7b0889b.jpg)  
图5GSCJIM与GSM误比特率性能对比

![](images/baf85c3292505c865310644c3a2e123abde49b4125c77d7a865b3c6768f17d78.jpg)  
图6不同配置下的GSCJIM误比特率比较

由以上的分析可以得出如下的结论：在GSCJIM中通过增加扩频码的个数来增加传输比特时，性能几乎无变化，通过增加发射天线的根数来增加传输比特时，性能下降相对较小，而通过增加调制阶数来增加传输比特时，性能下降非常明显。这是因为增加发射天线根数和扩频码个数的时候，星座图当中的欧氏距离并没有发生任何变化。而增加调制阶数的时候，星座图中的欧氏距离逐渐减小，这就是导致BER性能下降较明显的原因。此外，假如在每一个传输时隙内传输每个调制比特的能量一定时，在增加发射天线根数或PN码个数，即映射比特数增加，不会耗费额外的传输能量，平均每个信息比特耗费的能量减少，因此系统的能量效率就得以提升。

![](images/2cfa8fe70768d91d62ed7728ad97b044b1940ff9f0d7fec177795293e63161e7.jpg)  
图7不同索引调制方案间的误比特率比较

如图7所示，将GSCJIM与GSM、QSM以及广义空移键控（generalized space shiftkeying,GSSK）方案进行性能对比，这几种方案在每一个传输时隙的传输比特为10bit，其中GSCJIM、GSM、GSSK这三种方案在每一时隙激活两根发射天线。比较曲线 $\textcircled{1} \textcircled{3} \textcircled{5}$ 得，GSM和QSM分别通过增加发射天线根数来达到与GSCJIM相同的传输比特，此时QSM性能好于GSCJIM约1dB左右，而GSCJIM的性能在小于17dB时略优于GSM，但是GSM和QSM这两种方案都耗费了大量的天线资源。由曲线 $\textcircled{1} \textcircled{2} \textcircled{ 4}$ 得，GSM和QSM分别增加调制阶数到256和64以达到和GSCJIM相同的传输速率，性能相比于GSCJIM分别差了8dB和7dB，并且增加调制阶数会增大能量的损耗。由曲线 $\textcircled{1} \textcircled{6}$ 得，为了使GSSK在每一时隙的传输速率与GSCJIM相同，GSSK方案则需要在发射端设置60根发射天线，增加了天线资源的消耗，从图中可以看出，GSCJIM还保持了约1dB的性能优势。

本文提出的GSCJIM方案在接收端的信号检测分为PN码检测部分和最大似然估计部分，相比于GSM、QSM等方案增加了PN码相关检测部分，因此增加了接收端的复杂度。但是从性能方面来看，假设在每个传输时隙传输相同的信息比特，则本文提出的方案会好于传统的索引调制，且传输的信息比特越多效果越明显，这是因为传统的索引调制需要大量的索引资源来达到和本文提出方案相同的信息比特。

# 5 结束语

本文将广义空间调制和码索引调制结合起来，提出广义空-码联合索引调制。在本方案中，每一时隙不止激活一根天线，可以同时激活多根天线，这样就提高了天线的利用率。本方案将天线索引和扩频码的索引结合在一起，将现有的一维索引调制扩展为二维的联合索引调制。通过以上的仿真与分析表明，在每一时隙传输速率相同时，本方案要比广义空间调制、码索引调制使用更少的索引资源，传输速率越高，节省资源的优势就会越明显。通过增加发射天线根数或PN 码个数来增加本方案的传输速率相比于增加调制阶数，系统的性能会更好。在传输速率相同的情况下，本方案的误比特率性能会好于广义空间调制、正交空间调制和广义空移键控。下一步的研究重点将针对三维或更高维度的索引调制，主要是优化接收端的复杂度，力求更简单的解调方法，不断深入对更高维度索引调制的研究。

# 参考文献：

[1]Basar E.Index modulation techniques for 5G wireless networks [J].IEEE Communications Magazine,2016,54(7):168-175.   
[2]Data T,Eshwaraiah H S,Chockalingam A.Generalized space and frequency index modulation [J].IEEE Trans on Vehicular Technology,2015, 65 (7): 4911-4924.   
[3]Basar E. On multiple-input multiple-output ofdm with index modulation for next generation wireless networks [J]. IEEE Trans on Signal Processing, 2016,64(15): 3868-3878.   
[4]Mahapatra R,Nijsure Y,Kaddoum G,et al. Energy efficiency tradeoff mechanism towards wireless green communication:a survey [J].IEEE Communications Surveys & Tutorials,2016,18(1): 686-705.   
[5]傅金琳.MIMO系统关键技术研究[D].天津：天津大学，2010. (FuJinlin.Research on Key Techniques of MIMO Systems [D]. Tianjin: Tianjin University,2010.)   
[6]崔晓芳．无线通信中的空间调制技术[D]．大连：大连海事大学,2011. (Cui Xiaofang. Spatial modulation technology in wireless communications [D]. Dalian: Dalian Maritime University,2011.)   
[7]Mesleh RY,HaasH, Sinanovic S,et al. Spatial modulation [J].IEEE Trans on Vehicular Technology,2008,57(4): 2228-2241.   
[8] Jeganathan J，Ghrayeb A，Szczecinski L，et al. Space shift keying modulationforMIMO channels[J].IEEE Transon Wireless Communications,2009,8(7): 3692-3703.   
[9]Mesleh R,Ikki S,Aggoune HM.Quadrature spatial modulation [J].IEEE Trans on Vehicular Technology,2015,64(6):2738-2742.   
[10] Li Jun,Wen Miaowen,Cheng Xiang,et al. Generalized precoding-aided quadrature spatial modulation [J].IEEE Trans on Vehicular Technology, 2017,66 (2): 1881-1886.   
[11] Jeganathan J,Ghrayeb A,Szczecinski L.Generalized space shift keying modulation for MIMO channels [C]//Proc of IEEE，International Symposium on Personal, Indoor and Mobile Radio Communications.2008: 1-5.   
[12] YounisA,Serafimovski N,MeslehR,et al.Generalized spatial modulation [C]//Conference Record of the 44th Asilomar Conference on Signals,Systes and Computers.2010: 1498-1502.   
[13]刘健伶，陈志刚，王磊．一种自适应广义空间调制及其低复杂度算法 [J]．西安交通大学学报,2016,50(4),48-53.(Liu Jianling,Chen Zhigang, Wang Lei.An adaptive modulation algorithm with low complexity for generalized spatial modulation [J]. Journal of Xi’an Jiaotong University, 2016,50(4),48-53.)   
[14]Kaddoum G,Ahmed MFA,Nijsure Y.Code index modulation: a high data rate and energy efficient communication system[J].IEEE Communications Letters,2015,19(2): 175-178.   
[15]Kaddoum G, Soujeri E.On the comparison between code-index modulation and spatial modulation techniques [C]//Proc of International Conference on Information and Communication Technology Research.2015:24-27.   
[16] Kaddoum G,Nijsure Y,Tran H.Generalized code index modulation technique for high-data-rate communication systems [J]. IEEE Trans on Vehicular Technology,2016,65 (9): 7000-7009.