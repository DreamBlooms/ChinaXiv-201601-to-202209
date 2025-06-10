# 基于前导干扰消除的FBMC系统加权信道估计算法

董春波，罗志年

(湖南大学 信息科学与工程学院，长沙 410082)

摘要：针对FBMC 系统信道估计时存在虚部干扰问题，提出一种新的信道估计算法。首先，该算法采用了基于虚部干扰消除的新导频结构；然后，利用两列导频分别作粗信道估计；最后，对粗信道估计采用加权方式进行精信道估计，进一步提高信道估计性能。仿真结果表明，与传统虚部干扰消除算法（IIE）相比，新导频结构算法在误码率为 $1 \%$ 时，可获得1dB-2dB的性能提升。

关键词：FBMC；干扰消除；前导序列；信道估计 中图分类号：TN911.2 doi:10.19734/j.issn.1001-3695.2018.11.0835

Fbmc system weighted channel estimation algorithm based on preamble interference cancellation

Dong Chunbo,Luo Zhinian (College ofComputer Science & Electronics Engineering,Hunan University,Changsha 41082, China)

Abstract: Aiming atthe problemofimaginary part interference inchannel estimationofFBMC system,this paper proposed anewchannelestimationalgorithm.Firstly,thealgorithmadoptedanewpilotstructure basedonimaginarypart interference cancellation.Then,twocolumnsofpilotsareused forrough channelestimationrespectively.Finally,the weightedchael estimationisused forthecoarsechannelestimation，which further improved thechannel estimation performance. Simulationresults showthatthe new pilot structure algorithm can achieve the performance improvement ofldB-2dB when the bit error rate is $1 \%$ compared with the traditional imaginary part interference cancellation algorithm (IIE) .

Key words:FBMC; interference cancellation; preamble sequence; channel estimation

# 0 引言

在未来的通信系统中，移动通信量的增长速度需要更高的频谱效率。虽然正交频分复用（OFDM）具有抗频率选择性衰落、抗窄带干扰等优点在各种无线通信系统中被广泛的采用。但OFDM需要循环前缀(CP)作保护间隔来保证系统的鲁棒性，因此降低了数据传输效率；另外，因OFDM系统时域采用矩形窗滤波器，频域产生的大旁瓣会产生严重的频谱泄露。滤波器组多载波(FBMC)采用的滤波器具有良好的时频聚焦特性，可以提高频谱效率，并且不需要保护间隔来保证系统稳定性。因此，FBMC在学术界和工业界得到高度重视，其成为下一代无线通信系统中取代OFDM的候选者之一[1\~4]

FBMC仅在实数域正交会造成相邻符号间虚部干扰，因此FBMC采用OQAM调制即FBMC/OQAM,OQAM调制保证了时频格点上实部和虚部正交用来避免虚部干扰。精确的信道估计对FBMC/OQAM系统可靠性非常重要。针对信道估计这一问题，很多学者做了广泛而又深入的研究。文献[5]提出了IDPOP算法，算法是利用虚部干扰而不是消除干扰进行信道估计。文献[6采用散状导频，通过引入辅助导频，所接收的主导频利用辅助导频抵消虚部干扰进行信道估计。这种方法复杂度高，难以用于高密度导频进行信道估计。文献[7,8]提出盲信道估计的算法,其中文献[8]利用接收的OQAM信号和干扰分量的统计特性来进行信道估计。因需要在每个子载波位置计算空间符号，计算复杂度非常高。基于前导的导频结构与OFDM系统中的块形导频结构相同，其信道估计方法主要有干扰消除法（IEM)，干扰近似法（IAM）和导频对（POP）算法。文献[9]提出了导频对（POP）算法，利用信道在相邻位置拟不变的特性，通过算法推导出信道频域响应。文献[10]提出新导频(NPS)算法，是结合干扰消除和干扰利用对前导码作出新的组合，利用对称模式消除干扰，进而对信道进行估计。文献[11]采用辅助导频（APM）算法，利用数据和辅助导频来消除虚部干扰进行信道估计。文献[12]提出虚部干扰消除(IIE)算法，算法采用两列相同的FBMC导频符号，第一列导频位置所用滤波器符号与第二列导频位置所用滤波器符号相反，第一列导频的接收信号虚部干扰可以利用第二列导频接受信号干扰消除，并采第一列导频进行信道估计。文献[13]提出了新IAM算法，通过增大伪导频的功率来提高系统估计性能，但是导频开销大，降低了数据传输效率。综上，所提到基于前导的信道估计算法，没有充分利用导频进行信道估计，并且系统性能还有待提高。

本文重点是对FBMC/OQAM系统中基于前导码进行信道估计算法的研究。本文设计的新导频结构，利用两列导频干扰互消，分别采用两列导频作粗信道估计，然后对粗信道估计采用加权算法进行精信道估计。此算法既考虑到了导频对导频的干扰，也考虑了数据对导频的干扰，并且最后采用线性加权组合进一步提升信道估计性能。

# 1 FBMC/OQAM系统信号模型

FBMC/OQAM基带等效信号可以表示为

$$
s ( t ) = \sum _ { m = 0 } ^ { M - 1 } \sum _ { n } a _ { m , n } g _ { m , n } ( t )
$$

其中： $\boldsymbol { a } _ { m , n }$ 表示第 $m$ 个子载波上第 $n$ 个实值符号， $M$ 为子载

波的个数， $g _ { m , n } ( t )$ 为滤波器组，是由原型滤波器 $g ( t )$ 通过时频变换得

$$
g _ { m , n } ( t ) = g ( t - n \tau _ { 0 } ) e ^ { j 2 \pi m F _ { 0 } t } e ^ { j \varphi _ { m , n } }
$$

其中： $F _ { 0 } = 1 / T _ { 0 } = 1 / 2 \tau _ { 0 }$ 表示子载波间的间隔，其中 $T _ { 0 }$ 表示OFDM符号周期， $\tau _ { 0 }$ 表示OQAM符号的实部和虚部之间的时间偏移。 $\varphi _ { m , n } = ( \pi / 2 ) ( m + n ) + \varphi _ { 0 }$ 是由于 $O Q A M$ 符号正交偏移特性产生的相位， $\varphi _ { \mathrm { 0 } }$ 为任意值，本文取 $\varphi _ { \mathrm { 0 } } = - m n \pi$ 。原型滤波器$g ( t )$ 具有良好的时频特性，其时频变换得到的 $g _ { m , n } ( t )$ 具有很好的正交特性。

$$
\mathfrak { R } \{ \underbrace { \int g _ { m , n } ( t ) g _ { m , n } ^ { * } ( t ) d t } _ { \langle g _ { m , n } | g _ { p , q } \rangle } = \delta _ { m , p } \delta _ { n , q }
$$

$$
\zeta _ { m , n } ^ { p , q } = \sum _ { t } g _ { m , n } ( t ) g _ { p , q } ^ { * } ( t )
$$

其中： $\delta _ { i , j }$ 为狄拉克函数。除了 $( m , n ) = ( p , q )$ 时， $\delta _ { i , j }$ 由式（3）可得到， $\zeta _ { m , n } ^ { p , q }$ 的所有值都是纯虚数。这表明FBMC/OQAM系统只满足实数域正交，只有当式（3）成立时，才能得到 $a _ { m , n }$ 的完美重构。假设信道在每个子载波上是平坦衰落信道，当输出位于第 $p$ 个子载波和第 $q$ 个FBMC/OQAM 符号可以表示为

$$
r _ { p , q } = H _ { p , q } a _ { p , q } + \underbrace { \sum _ { m = 0 } ^ { M - 1 } \sum _ { n } H _ { m , n } a _ { m , n } \zeta _ { m , n } ^ { p , q } } _ { I } + \underbrace { \eta _ { m , n } ^ { p , q } } _ 
$$

其中： $H _ { p , q }$ 代表在频域中的信道响应。其中 $I$ 表示虚部干扰，$\eta _ { m , n } ^ { p , q }$ 表示加性高斯白噪声。

# 2 新导频结构设计

# 2.1传统导频结构算法

文献[11,12]提出了两列导频结构的算法，其算法主要采用虚部干扰消除。

文献[12]中第一列导频所对应的滤波器如式（2）所示；第二列导频滤波器如（6）（7）式所示。

$$
g _ { 2 m , n } ( t ) = g ( t - n T ) e ^ { j 2 \pi 2 m F t } e ^ { j \varphi _ { 2 m , n } }
$$

$$
g _ { 2 m + 1 , n } ( t ) = ( - g ( t - n T ) ) e ^ { j 2 \pi ( 2 m + 1 ) F t } e ^ { j \varphi _ { 2 m + 1 , n } }
$$

如式（8）所示，在奇偶行导频符号对应的位置采用不同的滤波器。

$$
s ( t ) = \sum _ { m = 0 } ^ { M / 2 - 1 } \sum _ { n } ( a _ { 2 m , n } g _ { 2 m , n } ( t ) + a _ { 2 m + 1 , n } g _ { 2 m + 1 , n } ( t ) )
$$

结合接收端的两列导频，可以把前列导频虚部干扰消除并进行信道估计。

文献[11]导频结构如图1所示。其中数据符号和导频符号关系表示为

$$
\left\{ \begin{array} { l } { a _ { 2 m - 1 , n } = 0 } \\ { a _ { 2 m - 2 , n } = a _ { 2 m - 2 } } \\ { a _ { 2 m - 1 , n - 1 } = - d _ { 2 m - 1 } } \\ { a _ { 2 m - 1 , n - 1 } = d _ { 2 m - 2 } } \end{array} \right. , m = 1 , . . . , M / 2
$$

其中： $d _ { i } , i = 1 , 2 , . . . , M$ 是在时间点 $( n + 1 ) \tau _ { 0 }$ 发送的数据，$a _ { 2 m - 2 } , m = 1 , 2 , . . . , M / 2$ 是时间点 $n \tau _ { 0 }$ 偶数子载波处参考信号。在时间点 $( n - 1 ) \tau _ { 0 }$ 辅助导频是用来抵消数据的虚部干扰。而奇数子载波通过插值进行信道估计。

上述两种算法虽然都是采用两列导频，相对于传统IAM算法减小了一列导频的开销，但是在信道估计时只考虑到了导频对导频的干扰，没有考虑数据对导频的干扰，并且只考虑了用一列导频进行信道估计。针对上述问题，提出了新导频结构算法。

# 2.2 新导频结构算法

新导频结构既考虑了导频对导频的干扰，又考虑了数据对导频的干扰，同时充分利用两列导频进行信道估计。新导频结构如图2所示。

$a _ { 0 , 0 }$ （20 -a0,1 $\stackrel { d _ { 0 } } { d _ { \cdot } }$   
-a1.0 a1. d   
a2.0 -a2.1 $d _ { 2 }$   
-a3.0 （20 $a _ { 3 , 1 }$ （20 $d _ { 3 }$ （204 数 数 ： ： ：： 据 据 ： dM-4   
（20 $a _ { M - 4 , 0 }$ （2 （20 $\overline { { \mathbf { \Omega } } } \overline { { a } } _ { M - 4 , 1 }$ （20   
-a𝑀-3.0 -aM-1.0 aM-2.0 -aM-2.1 aM-3.1 a𝑀−1,1 dM-3 dM-1 dM-2 导频 数据

![](images/e044a54e45e61689fbe7c442df1723904bcdc731975f69db3045771ca9e690ac.jpg)  
图1传统导频结构  
Fig.1Traditional pilot structure   
图2新导频结构图  
Fig.2New pilot structure   
图3干扰系数权重分布图  
Fig.3Weight distribution of interference coefficient

第一列导频符号的主要干扰来自第二列导频符号，但是第二列导频符号经过特定结构设计，结合滤波器干扰系数权重可以把主要干扰消除。第二列导频的主要干扰不仅来自第一列导频符号，还来自传输数据符号的干扰。其中来自第一列导频符号的干扰可以通过导频特定结构来消除，但是还存在数据的干扰可以加以利用。其原型滤波器的函数以及其干扰系数权重如图3所示。

(-1)δ -β (-1)P8 -(-1)γ ap.q (-1)Y (-1)Pδ $\beta$ 2 (-1)Pδ

$$
\left\{ \begin{array} { c } { { \beta = e ^ { \frac { 2 \pi L _ { \sigma } - 1 } { 2 } } \displaystyle \sum _ { t = 0 } ^ { L _ { \sigma } - 1 } g ^ { 2 } ( t ) e ^ { j \frac { 2 \pi } { M } t } } } \\ { { \gamma = \displaystyle \sum _ { t = M / 2 } ^ { L _ { \sigma } - 1 } g ( t ) g ( t - \frac { M } { 2 } ) } } \\ { { \delta = - j e ^ { \frac { 2 \pi L _ { \sigma } - 1 } { 2 } } \displaystyle \sum _ { t = M / 2 } ^ { L _ { \sigma } - 1 } g ^ { 2 } ( t ) g ( t - \frac { M } { 2 } ) e ^ { j \frac { 2 \pi } { M } t } } } \end{array} \right.
$$

其中: $L _ { g }$ 表示滤波器的有效长度。一般情况 $\beta , \gamma > \delta$ 。取值分别为 $\beta = 0 3 1 8 3 1$ ， $\delta = 0 . 2 5 0 1$ ? $\gamma = 0 . 5 0 0 4$ 。其中 $\gamma \approx 2 \delta$ 。

由式(10)，第一列导频干扰消除的原理如

$$
\begin{array} { r l } & { \tilde { a } _ { m , n } = a _ { m , n } + ( - a _ { m - 1 , n } ) * ( - \beta ) + ( - a _ { m + 1 , n } ) * \beta } \\ & { \qquad + a _ { m - 1 , n + 1 } * \delta + ( - a _ { m , n + 1 } ) * \gamma + a _ { m + 1 , n + 1 } * \delta } \\ & { \qquad \approx a _ { m , n } } \end{array}
$$

其中: $\beta , \delta , \gamma$ 表示滤波器的一阶干扰系数。本文所有的导频取值相等,即 $a _ { m , 0 } = a _ { m , 1 } m = 0 , 1 , . . . , M - 1$ 。

同理，第二列导频可以用前列导频消除虚部干扰，但还存在数据的虚部干扰，其表达式如下：

$$
\begin{array} { r l } & { \tilde { a } _ { m , n } = a _ { m , n } + ( - a _ { m - 1 , n } ) * ( - \beta ) + ( - a _ { m + 1 , n } ) * \beta } \\ & { \qquad + d _ { m - 1 } * \delta + d _ { m } * \gamma + d _ { m + 1 } * \delta + a _ { m - 1 , n - 1 } * \delta } \\ & { \qquad + ( - a _ { m , n - 1 } ) ^ { * } ( - \gamma ) + a _ { m + 1 , n - 1 } * \delta } \\ & { \qquad \neq a _ { m , n } } \end{array}
$$

其中： $d _ { m } , m = 0 , 1 , 2 , . . . , M - 1$ 表示粗信道估计得到的数据。

虽然第二列导频存在数据的虚部干扰，但存在信道估计可用信息，所以对两列导频分别进行粗信道估计，并对粗信道估计采用加权进一步提高信道估计的性能。新算法流程结构如图4所示。

![](images/724d51f22848dc149639e4ca056a078e15f49e66b2a2e7273dab64581b53e2ce.jpg)  
Fig.4Newalgorithm flow structure diagram

数据对导频的虚部干扰表示为

$$
\rho _ { a _ { m , n } } ^ { d _ { m } } = \left\{ \begin{array} { l l } { { \displaystyle { d _ { m } } * \gamma | + | d _ { m + 1 } * \delta | } } & { { \quad m = 0 } } \\ { { \displaystyle { d _ { m - 1 } } * \delta | + | d _ { m } * \gamma | + | d _ { m + 1 } * \delta | } } & { { \quad m = 1 , . . . , M - 2 } } \\ { { \displaystyle { \big | d _ { m - 1 } } * \delta | + | d _ { m } * \gamma | } } & { { \quad m = M - 1 } } \end{array} \right.
$$

其中： $\rho _ { a _ { m , n } } ^ { d _ { m } }$ 表示数据 $\boldsymbol { d } _ { m }$ 对导频 $a _ { m , n }$ 的虚部干扰， $n = 0 , 1$ 。对每个导频点的虚部干扰累加求取平均，表达式为

$$
\rho _ { 0 } = \sum _ { i = 0 } ^ { M - 1 } \rho _ { a _ { i , 0 } } ^ { d _ { i } } \mathrm { ~ / ~ } M , \rho _ { \mathrm { i } } = \sum _ { i = 0 } ^ { M - 1 } \rho _ { a _ { i , 1 } } ^ { d _ { i } } \mathrm { ~ / ~ } M
$$

由式（11）得第一列导频几乎不受虚部干扰，故可采用传统的LS信道估计算法可得到比较精确的信道频域响应，即

$$
\tilde { H } _ { 0 } = \frac { y _ { m , 0 } } { \tilde { a } _ { m , 0 } }
$$

由式（12）可知，虽然第二列导频受到右侧数据虚部干扰，采用LS信道估计算法得到性能较差的信道频域响应：

$$
\tilde { H } _ { 1 } = \frac { y _ { m , 1 } } { \tilde { a } _ { m , 1 } }
$$

由于数据对两列导频都存在干扰，但是数据对第一列导频干扰较小，对第二列导频干扰较大，因此，对信道估计按比例进行加权来提高信道估计精度。采用估计加权算法可得精信道估计为

$$
\tilde { H } = \lambda \tilde { H } _ { 0 } + ( 1 - \lambda ) \tilde { H } _ { 1 }
$$

因此，新信道估计算法可转换为求 $\lambda$ 比例系数， $\lambda$ 的值为

$$
\lambda { = } \frac { \rho _ { 1 } } { \rho _ { 0 } + \rho _ { 1 } }
$$

其中： $\lambda$ 的值随着数据的变化而自适应的变化。

# 3 新导频结构算法性能分析

为了凸显新算法的优势，特别地对算法的复杂度作如下分析：

a）对POP算法进行分析，POP算法是通过数学逻辑运算求得信道频域响应。在进行信道估计时，需要通过3M次乘法计算，M次减法以及M次LS信道估计除法。其中不需要任何滤波器任何信息。

b）APM算法在信道估计时用到的了插值。APM算法在信道估计时需要4M次乘法，M次减法，M次的信道估计除法以及M/2次插值计算，其复杂度比POP算法高，但是估计性能比POP更优。

c）NPS算法在信道估计时需要计算等效导频。需要做4M次乘法，M次加法以及M次除法计算，计算量比APM稍低，但估计性能比APM好。

d）IIE算法是在第二列导频位置处滤波器取反，来处理第一列导频的干扰。需要做4M次乘法，M次滤波器取反的乘法，M次干扰消除减法以及M次信道估计除法。算法复杂度增大，但是性能得到提升。

e）新算法需要4M次乘法，M次固有干扰累加求和以及两次求均值，M次信道估计除法。虽然算法复杂度比POP算法稍大，与APM和NPS算法复杂度相近，比IE 算法复杂度低，但是在算法复杂度相差允许的范围内取得了最优的信道估计性能。

# 4 仿真与分析

为了验证新算法的性能，对上述新导频结构算法在MATLAB环境下对FBMC系统仿真验证。仿真参数设置如表1所示。

表1仿真参数设置  
Table 1Simulation parameter settings   

<html><body><table><tr><td>仿真参数</td><td>取值</td><td>仿真参数</td><td>取值</td></tr><tr><td>FFT点数</td><td>128</td><td>符号数</td><td>10</td></tr><tr><td>调制方式</td><td>4QAM</td><td>仿真信道</td><td>ITU-VA，ITU-PA</td></tr><tr><td>滤波器长度Lg</td><td>512</td><td>仿真次数</td><td>5000</td></tr></table></body></html>

![](images/78685ccead11aa1291edf67e595b16debafe7015f57560b22734242d48a0ee0c.jpg)  
图4新算法流程结构图  
(a）高斯信道下BER性能比较

![](images/b6dc1dea8fc3514d17264e1e1f4039fd85c703caf556aa445cb1255f691d28a1.jpg)  
(a) Comparison ofBER performance under Gaussian channel   
(b）高斯信道下MSE性能比较   
(b) Comparison ofMSE performance under Gaussian channel 图5高斯信道下4-OQAM,16-OQAM,64-OQAM下BER仿真和 MSE 仿真对比   
Fig.5Comparison between BER simulation and MSE simulation under Gaussianchannel4-OQAM16-OQAM-64-OQAM

如图5所示，在高斯信道下分别对五种算法在4-OQAM,16-OQAM和64-OQAM的调制方式下进行仿真对比。从图5（a）中可以看出，无论何种调制方式，新提出的算法误码率性能（BER）都相对优越。图5（b）中是均方误差（MSE）的仿真，MSE其表示的是理想信道和估计信道之间的误差，表现了信道估计的性能好坏。其MSE表达式可以表示为 $M S E = \mid H - { \tilde { H } } \mid ^ { 2 } / \mid H \mid ^ { 2 }$ ， $H$ 是理想信道值， $\tilde { H }$ 是LS算法估计得到的估计值。图中新算法的MSE很明显优于POP，APM和NPS算法，虽然新算法的MSE与IE算法很相近，但是新算法复杂度比IIE算法低。同时，MSE与BER的总体性能趋势一致。

![](images/49a909c9d4f86742f16843929ea2cf22ed62137901eb87283a4bc51ddcb74ac8.jpg)  
图6在ITU-VA和ITU-PA信道模型下算法在不同列导频下的BER仿真对比

从图6可以看出，无论是在PA信道模型还是VA信道模型下，由于第二列导频受到很大数据干扰以至于信道估计的性能最差；第一列导频受到数据的干扰较小，估计性能比前者更优；而提出的加权算法充分利用两列导频进行信道估计取得最好的性能。另外，由于不同信道模型其信道参数不同会使算法性能会有所差异。

![](images/10b7edaea40342249a81f25eba84b3f7f4df130b2f0e1904235690f834a81eea.jpg)  
Fig.6Comparison of BER Simulation of algorithms in different pilots under ITU-VA and ITU-PA Channel models   
图7不同信道模型下的 BER性能比较Fig.7Comparison of BER performance underdifferent channel models

从图7可以看到，新提出的算法在VA和PA多径信道下都取得了最优的BER性能。传统的POP算法性能最差，主要因为POP导频结构设置不合理，抗噪性能差；APM算法其辅助导频是由传送的第一列数据奇偶符号相反得到，中间采用 $a _ { m , n } , m = 0 , 1 , . . . , M - 1 ; n = 1$ 与0相间，最后采用插值方法进行信道估计，由于插值不能完全表现出信道的特征，性能仅比POP算法性能好；NPS算法采用三列导频，考虑到对称结构中的虚部干扰权重，采用对称模式进行虚部干扰消除，相对POP算法和APM算法，其仿真的性能有所改进，但是增加了导频的开销；IIE 算法在减少一列导频开销的情况下,其性能比NPS性能有所改进，总体来说性能比较好，但是导频结构容易受导频取值的影响；而新导频结构算法采用两列导频情况下，通过粗信道估计和精信道估计，系统性能达到最优。

![](images/ed2b4ace82a08dd6b616181aeee8d75f1a93f4cbe13532ef5dd52ca242b3f122.jpg)  
(a)ITU-PA信道下MSE 性能比较

![](images/ae5bd55798aed8f1b4e9f8cf8ab19bb71bd629ae799478325a2a8f7fdbc934ea.jpg)  
(a) Comparison ofMSE performance under ITU-PA channel   
图8不同信道模型下MSE性能比较  
Fig.8Comparison of MSE performance under different channel models

图8为上述导频算法在VA和PA多径信道下MSE性能比较仿真曲线。由于POP算法在设计导频结构时未考虑噪声干扰以及其他干扰，信道估计值和真实值误差比较大，使MSE性能较差；APM算法是在信道估计时对导频的插值，不能完全表现真实信道，性能也较差；NPS算法虽然增大了导频等效功率，但同时导频结构也引入了数据的干扰，致使性能较差；IIE算法没有充分运用导频符号进行信道估计，丢失了一部分有用信息。新算法不仅设计特殊导频结构进行干扰消除，还充分运用导频符号进行信道估计。因此，图8（a）（b）中新算法获得较好的MSE性能。

综上，本文采用的导频结构充分利用两列导频进行信道估计，通过大量的仿真对比分析，在低信噪比下，算法可以取得比较优越的性能。从各个方面验证新算法的正确性，可行性和优越性。

# 5 结束语

5G即将商用，FBMC系统作为候选系统之一，精确的信道估计是5G一个关键的技术。针对传统的信道估计算法，提出了新的导频结构算法。通过理论分析推导和仿真表明，本文提出的导频结构利用干扰相互消除，利用加权算法得到最终精确的信道估计，与传统的POP算法，APM算法和IIE算法相比，性能得到大幅度提升。因此本文提出的导频结构和算法是有效可行。

# 参考文献：

[1]Nissel R,Rupp M.On pilot-symbol aided channel estimation in FBMC/OQAM [C]//Proc of International Conference on Acoustics, Speech and Signal Processing.Piscataway,NJ:IEEE Press，2016: 3681-3685.   
[2]Schaich F,Wild T.Waveform contenders for 5G-OFDM vs.FBMC vs. UFMC[C]//Procofthe6thInternationalSymposium on Communications,Control and Signal Processing.Piscataway,NJ:IEEE Press,2014: 457-460.   
[3]Wunder G,Jung P,Kasparick M,et,al.5GNOW:non-orthogonal, asynchronous waveforms for future mobile applications [J].IEEE Communications Magazine,2014,52(2):97-105.   
[4]Bellanger M,Ruyet DL,Roviras D,et al.FBMC physical layer:a primer[EB/OL].(2010-06). http://www.ict-phydyas.org/teamspace/internal-folder/FBMC-Primer_0 6-2010.pdf   
[5]Choi JM, Oh Y,Lee H,et al. Interference-dependent pair of pilots for channel estimation in FBMC systems [C]// Proc of International Symposium on Broadband Multimedia Systems and Broadcasting. Piscataway,NJ:IEEE Press,2016:1-4.   
[6]Fuhrwerk M,Moghaddamnia S,Peissig J. Scattered pilot-based channel estimation for channel adaptive FBMC-OQAM systems [J].IEEE Trans on Wireless Communications,2017,16(3):1687-1702.   
[7] Yu Bin,Hu Su，Sun Pengfei，et al.Channel estimation using dual-dependentpilotsinFBMC/OQAMsystems[J]. IEEE Communications Letters,2016,20(11):2157-2160.   
[8]Hou Weikun,Champagne B. Semiblind channel estimationfor OFDM/OQAM Systems [J]. IEEE Signal Processing Letters,2015, 22(4):400-403.   
[9]Lélé,C, Javaudin J,Legouable R,et al. Channel estimation methods for preamble based OFDM/OQAM modulations [J].European Trans on Telecommunications,2012,19(7):741-750.   
[10] Wang Han,Du Wencai,Xu Lingwei.Novel preamble design for channel estimation in FBMC/OQAM systems [J].KSII Trans on Internet and Information Systems,2016,10(8): 3672-3688.   
[11] Yuan Hang,Hu Su,Yin Lu,et al.Efficient channel estimation for FBMC systems based on auxiliary preamble design [C]//Proc of the 10th International Conference on Information,Communications and Signal Processing.Piscataway,NJ:IEEE Press,2016:1-5.   
[12] Wang Jinchao,Zhao Hui,Zhang Yuyan,et al. Intrinsic Interference Elimination for Preamble-Based Channel Estimation in FBMC Systems [C]//Proc of GLOBECOM Workshops.Piscataway,NJ:IEEE Press, 2016:1-5.   
[13]Mohammed A,Mohammed M,Radwa A.A proposed preamble based channel estimation method for FBMC in 5G wireless channels [C]// Proc of the 35th National Radio Science Conference.2018:140-148.