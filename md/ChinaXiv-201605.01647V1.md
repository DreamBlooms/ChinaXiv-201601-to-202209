# 探空火箭通信系统最优信噪比切换阈值的设计

陈萍1²³，熊蔚明}于世强陈志敏(1.中国科学院空间科学与应用研究中心北京100190;2.中国科学院大学,北京100049;3.中国船舶工业系统工程研究院北京100036;4.中国空间技术研究院载人航天总体部,北京100094)

摘要:结合Nakagami衰落信道模型，分析了探空火箭飞行过程中经历的瑞利信道和莱斯信道的特性,以BPSK、QPSK、16QAM、64QAM4种调制方式结合的可变调制传输系统为例提出了可根据地面数据接收站天线的不同仰角，计算最优信噪比切换阈值的方法。最优信噪比切换阈值在满足误码率指标的前提下,使系统的数据吞吐量最大。进一步比较了采用最优信噪比阈值与采用 BPSK固定调制方式、恒定误码率信噪比阈值的吞吐量差异结果表明,采用最优信噪比阈值法得到的数据平均吞吐量分别是另外2种方法的3.89倍和1.043倍。其结果为可变调制技术在探空火箭工程中的应用提供参考依据。

关键词:可变调制;最优信噪比阈值;探空火箭   
中图分类号：V556 文献标识码：A 文章编号:1006-2793(2015)04-0595-06   
DOI:10.7673/j.issn.1006-2793.2015.04.027

# Design of the optimum signal-to-noise ratio switch threshold of sounding socket communication system

CHEN Ping1²³,XIONG Wei-ming1,YU Shi-qiang4 CHEN Zhi-min1 (1.Center for Space Science and Applied Research of Chinese Academy of Sciences,Beijing100190 China;   
2.Graduate University of Chinese Academy of SciencesBeijing10o049 China;   
3.Engineering Research Institute of China State Shipbuilding Corporation System Beijing1Ooo36 China;   
4.Institute of Manned Space System ,China Academy of Space Technology Beijing10o094 China)

Abstract:Combining withNakagami fadingchannelmodel,RayleighchannelsandRicianchannelswereanalyzedbetween soundingrocketsandgroundstationduringtheflightcourse.Itakesanexampleofavariablemodulationsystemwithfourtypesof modulationsincludingBPSKQPSK6QAMand64QAMandproposesamethod toacquiretheoptimumsignal-tonoisetio switchthresholdaccordingtodiferent elevationanglesofgroundreceivingstation.Theoptimumthresholdcouldmaximizethe throughputwhilesatisfyingBERgoal.Furthermore,thepaperanalyzesandcomparesthethroughputdiferencewithoptimumsignalto-noiseratioswitchthresholdBPSKmodulationmethodandconstant-BERsignal-tonoiseratiothreshold.Theresultsshowthatby adoptionof theoptimum thresholdsystemthroughputis3.89 timesand1.043timeshigher thantheothertwomethodsrespectively.Theresultscould providereferenceandbasisfortheapplicationofvariablemodulationtechnologyintopracticalsoundingrockets projects.

Key words: variable modulation; optimum signal-to-noise ratio threshold; sounding rockei

# 0 引言

探空火箭在飞行过程中，与地面数据接收站的距离不断变化，传统的固定调制模式的通信系统只能依据最差的信道条件来设计，在信道条件好的时候不能充分利用信道容量。可变调制系统可根据无线信道的时变特性，动态改变自己的信号发射参数，包括符号率、编码率、编码方式等从而在给定数据传输质量要求的前提下充分利用信道容量提高有效载荷的数据吞吐量。在探空火箭中应用可变调制技术，根据不同的信道条件选择不同的调制方式，能够在不改变系统发射及接收能力、满足自标误码率的前提下提高系统吞吐量是未来提高探空火箭对地数据传输能力的关键技术之一。

许多学者对可变调制技术进行了深入的研究。早在1968年,Hayes提出了根据接收端反馈的信道信息进行可变调制传输[1]的方法,这是最早提出的根据信道状态进行可变调制传输的思想。Webb和Steel最先研究了在加性白色高斯噪声(AWGN)信道条件下正交幅度调制方式(QAM)满足误码率(BER)指标时的信噪比[2]。Torrance 和Hanzo 研究了在系统平均BER的限制下，可变调制方式的BER性能上界和对应的自适应调制系统的数据吞吐量性能[3],提出基于当前信道衰落和系统BER要求来选择合适的调制方式。另外还综合考虑误码率BER代价和吞吐量BPS代价，使其综合加权代价最小而获得最佳切换门限值[4]。Choi和Hanzo采用拉格朗日乘数法得到了在单径瑞利信道模型下自适应正交幅度调制(AQAM)系统的最佳切换门限值[5-6],还将所得结果与加权法所得的最佳门限值作了比较结果表明采用拉格朗日乘数法得的最佳信噪比切换门限值使AQAM系统的平均吞吐量性能更好。但文献[5-6]没有针对火箭或移动卫星信道提出分析方法。文献[7]采用ITU-RM.1225中定义的Ve-hicularTest模型，研究了在该信道模型下自适应调制系统的最佳信噪比门限值，该模型可近似高速移动环境下多径瑞利衰落信道，但与探空火箭的通信信道有明显不同。

回顾最优信噪比切换阈值的研究进展，不难发现，最优信噪比切换阈值的计算一般基于理论模型，而对于火箭或者移动卫星，尚未有最优信噪比门限值计算的相关文献。目前采用的普遍方法是将传输信道近似为AWGN模型,计算AWGN信道模型下每种调制方式满足BER指标时的信噪比。该方法可保证系统采用各调制方式时都能满足预定BER指标，是一种局部最优的方法但是该方法不能使系统整体的吞吐量最大化不是全局最优的方法。此外AWGN信道模型是一种理论模型与探空火箭的信道模型也存在较大差异。

本文采用全局最优的思路结合Nakagami信道模型分析了探空火箭在飞行过程中火箭与地面通信经历的瑞利信道、莱斯信道特性，以BPSK、QPSK、16QAM和64QAM4种调制方式结合的可变调制系统为例，提出了探空火箭最优信噪比切换阈值的计算方法，该方法使系统的吞吐量最大，同时保证系统的误码率达到任务指标的要求。

# 1通信信道与接收天线仰角的关系

探空火箭飞行过程中，火箭与地面通信的信道特性较为复杂目前尚无成熟的理论分析。通过借鉴有关文献对卫星信道的分析[8],认为通信信号因受建筑物、透明体和障碍物等散射、折射和反射的影响，地面遥测接收站接收到的信号是不同强度和相位、不同延迟时间的多径传播信号的叠加。在没有直视分量的情况下，信号的统计特性可以用瑞利(Rayleigh)分布来描述。如果在宽阔地域良好通信环境下，信号中存在直视分量信号,信道特性用莱斯(Rician)分布描述。

为了更好描述信道特性，本文使用了Nakagami衰落信道模型作为仿真模型[9]。该模型也称为广义信道模型，由日本著名学者Nakagami20世纪60年代提出，通过现场测试并用曲线拟合的方法来描述信道，以寻求近似分布。由于Nakagami分布是基于曲线拟合方法得到的因此它并没有相应的物理模型。但是根据该分布的表达形式，可理解为它是由几组多径波组合而成的分布在任何一组多径波组合内散射波的相位是随机的但具有相近的时延而在不同组内，时延差别比较大。平坦Nakagami信道中,信噪比 $\gamma$ 的概率密度函数 $p ( \gamma )$ 表示为

$$
p ( \gamma ) = \frac { m ^ { m } } { T ( \ m ) \ \overline { { { \gamma } } } ^ { m } } \overline { { { \gamma } } } ^ { m - 1 } \exp ( \ - \frac { m \gamma } { \overline { { { \gamma } } } } )
$$

式中 $\bar { \gamma }$ 为平均信噪比; $m$ 为衰落因子。

$m$ 表示信道衰落的严重程度 $\mathbf { \Omega } _ { , m }$ 越小衰落越严重，$m$ 越大衰落越不明显。当 $m = 1$ 时模型为瑞利衰落信道模型；当 $m { > } 1$ 时为莱斯信道模型。通过调整参数 $\mathbf { \nabla } _ { m }$ 的值Nakagami模型能够逼近严重、适中、轻微到无衰落的信道特性。

利用高度为 $3 5 0 ~ \mathrm { k m }$ 的探空火箭弹道数据，计算得到其在飞行全过程中地面数据接收站天线的仰角变化如图1所示接收站天线的仰角变化范围为 $0 ^ { \circ } \sim 8 2 ^ { \circ }$ 。

![](images/f7eb851771bf206cd31220e923008f1160d0e9a9e01530b1c2b98e09240e5497.jpg)  
图1地面数据接收站天线仰角的变化 Fig.1Change of elevation angles of ground data receiving station

当地面站天线仰角小于 $5 ^ { \circ }$ 通信信道受地形地貌等因素的影响明显，多径分量强而直视分量很弱或不存在信道可用瑞利信道近似，相当于Nakagami信道模型参数 $m = 1$ 。当地面站天线仰角大于 $5 ^ { \circ }$ 除直视分量外会出现较多的多径分量信道用莱斯信道近似相当于Nakagami信道模型参数 $m { > } 1$ 。信道类型与天线仰角之间的关系如图2所示。

![](images/44af52d77d079256ce1b1df9e4fe862d6a2d1f22ee2f2970dac056b41e257275.jpg)  
图2地面数据接收站天线仰角的变化 Fig.2Relationship between channel types and elevation angles

为了表征莱斯信道下直射分量与多径分量的相对大小 引入了莱斯因子 $K ^ { [ 1 0 ] }$ 其定义如式(2)所示:

$$
K = { \frac { S ^ { 2 } } { 2 { \sigma } ^ { 2 } } }
$$

式中 $S ^ { 2 }$ 为直视分量的功率; $\sigma ^ { 2 }$ 为被散射多径分量的实部或虚部的均值功率。

实际卫星链路特性的测试结果表明[11-12] ,在树木遮蔽条件下莱斯信道的莱斯因子 $K$ 与遥测接收站天线仰角 $\alpha$ 之间的经验式为

$$
K ( \alpha ) = K _ { 0 } + K _ { 1 } ( \alpha ) + K _ { 2 } \alpha ^ { 2 }
$$

$$
K _ { 0 } = 2 . 7 3 ~ , K _ { 1 } = - 0 . 1 0 ~ 7 4 ~ K _ { 2 } = 0 . 0 0 2 ~ 7 7 4 ~ .
$$

莱斯因子 $K$ 与Nakagami模型衰落因子 $m$ 之间有一一对应关系[13-14]：

$$
m = \frac { \left( K + 1 \right) ^ { 2 } } { 2 \times K + 1 }
$$

根据式(3)和式(4），可由地面站天线仰角的不同得到信道衰落因子 $\mathbf { \nabla } _ { m }$ 的近似值。进一步,由式(1）可知 $m$ 因子一定的情况下还可得到不同平均信噪比条件下对应的信道信噪比的概率密度函数，而概率密度函数是Nakagami信道条件下信噪比切换阈值确定的重要依据。

# 2探空火箭可变调制系统

探空火箭可变调制系统设计为根据不同的信道条件采用不同的信号调制方式。设探空火箭采用 $k$ 种调制方式组合的调制系统，根据接收端测量的信道质量 $\boldsymbol { \xi }$ 来选择相应的调制方式。选择第$k \in \{ 0 \mathrm { ~ , 1 ~ } \mathrm { ~ } , \cdots \mathrm { ~ } , K \mathrm { - } 1 \}$ 种调制方式的准则为

$$
s _ { k } \leqslant \xi \leqslant s _ { k + 1 }
$$

信道质量 $\xi$ 是瞬时信道信噪比，也可是瞬时每符 号信噪比。本文设 $\xi$ 代表瞬时信道信噪比。信噪比切

换阈值 $s _ { k }$ 属于:

$$
s = \left\{ \left. s _ { k } \right| k = 0 \mathrm { ~ , 1 ~ } , \cdots \mathrm { ~ } , K \right\}
$$

通常设 $\scriptstyle s _ { \scriptscriptstyle \mathrm { o } } = 0 \ s _ { \scriptscriptstyle K } = \infty$ 。用 $b _ { k }$ 表示各种调制方式下每符号比特数， $\mathbf { \nabla } _ { m _ { k } }$ 表示各种调制方式的阶数，则$b _ { k } = \log _ { 2 } ( \mathbf { \mu } m _ { k } )$ ,定义 $c _ { k } = b _ { k } - b _ { k - 1 }$ 且有 $c _ { 0 } = b _ { 0 }$ 。假设探空火箭的可变调制系统设计了BPSK、QPSK、16QAM和64QAM4种调制方式进行组合传输，调制方式的参数如表1所示其中 $\mathrm { { N o - T x } }$ 表示不进行传输。

表1不同调制模式的系统参数  
Table1 System parameters of different modulation modes   

<html><body><table><tr><td>参数</td><td>No-Tx</td><td>BPSK</td><td>QPSK</td><td>16QAM</td><td>64QAM</td></tr><tr><td>k</td><td>0</td><td>1</td><td>2</td><td>3</td><td>4</td></tr><tr><td>mk</td><td>0</td><td>2</td><td>4</td><td>16</td><td>64</td></tr><tr><td>bk</td><td>0</td><td>1</td><td>2</td><td>4</td><td>6</td></tr><tr><td>Ck</td><td>0</td><td>1</td><td>1</td><td>2</td><td>2</td></tr></table></body></html>

# 3最优信噪比切换阈值的计算方法

最优信噪比切换阈值的计算方法参考文献[5]利用拉格朗日（Lagrange）乘数法计算最大极值的思路。设系统的平均吞吐量为 $B$ 单位为比特/符号(bit/sym-bol）。已知信噪比概率密度 $p ( \boldsymbol { \lambda } )$ 的表达式如式(1）所示则平均吞吐量可表达为

$$
B ( \stackrel { \_ } { \gamma } ; s ) = \sum _ { k = 0 } ^ { K - 1 } b _ { k } { \int _ { S _ { k } } ^ { S _ { \ k + 1 } } } p ( \ \gamma ) \ d \gamma
$$

设第 $k$ 种调制方式在AWGN信道下的误码率为$p _ { m _ { k } }$ 则在Nakagami信道条件下每种调制方式的误码率可表达为

$$
P _ { \boldsymbol { k } } ( \mathbf { \overline { { \gamma } } } ; \mathbf { s } ) = \int _ { S _ { \boldsymbol { k } } } ^ { S _ { \boldsymbol { k } + 1 } } p _ { m _ { \boldsymbol { k } } } ( \mathbf { \gamma } \gamma ) p ( \mathbf { \gamma } \gamma ) \mathrm { d } \gamma
$$

对PSK调制和QAM调制方式的误码率表达式为

$$
p _ { m _ { k } } ( \gamma ) = \sum _ { i } A _ { i } Q ( \sqrt { a _ { i } \gamma } )
$$

对应于BPSK、QPSK、16QAM和64QAM调制的参数 $\cdot A _ { i } \ a _ { i } \}$ 参见文献 $[ 5 ~ ] _ { \circ }$

设4种调制方式组合情况下的系统平均误码率为$P _ { \mathrm { a v g } }$ 则表达式为

$$
P _ { _ \mathrm { a v g } } ( { \bar { \gamma } } ; s ) = { \frac { 1 } { B ( { \bar { \gamma } } ; s ) } } \sum _ { k = 0 } ^ { 4 } b _ { k } P _ { k }
$$

设预定的误码率指标为 $P _ { \mathrm { t h } }$ 要得到最佳信噪比切换阈值 就要使得系统平均吞吐量 $B$ 在满足约束条件$P _ { \mathrm { a v g } } = P _ { \mathrm { t h } }$ 的情况下取得最大。故有：

$$
P _ { _ { \mathrm { t h } } } B ( \stackrel { - } { \gamma } ; s ) = \sum _ { k = 0 } ^ { 4 } b _ { k } P _ { _ k }
$$

利用等式约束下的拉格朗日最优极值求解方法，求解在约束条件式(10)的条件下吞吐速率 $B ( \stackrel { - } { \gamma } ; s )$ 的

最大值构造如下的拉格朗日函数。

$$
\Lambda ( { \stackrel { \_ } { \gamma } } ; s ) = B ( { \stackrel { \_ } { \gamma } } ; s ) + \lambda \{ P _ { _ { \mathrm { t h } } } B ( { \stackrel { \_ } { \gamma } } ; s ) - \sum _ { k = 0 } ^ { 4 } b _ { k } P _ { k } \}
$$

根据拉格朗日乘数法，最优信噪比切换门限 $s$ 应满足：

$$
\left\{ \begin{array} { l l } { \displaystyle { \frac { \partial A ( { \bar { \boldsymbol { \gamma } } } ; s ) } { \partial s } } = 0 } \\ { \displaystyle { P _ { \mathrm { { t h } } } B ( { \bar { \boldsymbol { \gamma } } } ; s ) } - \sum _ { k = 0 } ^ { 4 } b _ { k } P _ { k } = 0 } \end{array} \right.
$$

对式(13)中的(a)展开得到:

$$
\begin{array} { r l r } { \displaystyle \frac { \partial A ( \overline { { \gamma } } ; s ) } { \partial s } = \frac { \partial } { \partial s } ( B ( \overline { { \gamma } } ; s ) } & { + \lambda \{ P _ { \mathrm { i n } } B ( \overline { { \gamma } } ; s ) - \sum _ { k = 0 } ^ { 4 } b _ { k } P _ { k } \} } & \\ & { = \frac { \partial } { \partial s } ( B ( \overline { { \gamma } } ; s ) ) } & { + \lambda P _ { \mathrm { i n } } \frac { \partial } { \partial s } ( B ( \overline { { \gamma } } ; s ) - } \\ & { } & { \qquad \lambda \frac { \partial } { \partial s } ( \sum _ { k = 0 } ^ { 4 } b _ { k } P _ { k } ) ) } \\ & { = 0 } & { ( } \\ { \displaystyle \frac { \partial } { \partial s } ( \sum _ { k = 0 } ^ { 4 } b _ { k } P _ { k } ) = } & { b _ { k - 1 } p _ { m _ { k - 1 } } ( s _ { k } ) p ( s _ { k } ) - b _ { k } p _ { m _ { k } } ( s _ { k } ) p ( s _ { k } ) } \end{array}
$$

$$
\frac { \partial B ( \stackrel { - } { \gamma } \ s ) } { \partial s } = - c _ { k } p ( \ r _ { s _ { k } } )
$$

把式(15）、式(16)代入式(14)得到:

$$
[ c _ { k } ( 1 - \lambda P _ { \mathrm { \scriptsize ~ t h } } ) \ - \lambda \{ b _ { k - 1 } p _ { m _ { k - 1 } } ( s _ { k } ) \ - b _ { k } p _ { m _ { k } } ( s _ { k } ) \} \ ] p ( s _ { k } ) = 0
$$

式(17)的一个解是 $p ( \boldsymbol { \mathscr { s } } _ { k } ) = 0$ 但不是问题的解，所以有

$$
c _ { k } ( 1 - \lambda P _ { \mathrm { { t h } } } ) - \lambda \{ b _ { k - 1 } p _ { m _ { k - 1 } } ( s _ { k } ) - b _ { k } p _ { m _ { k } } ( s _ { k } ) \} = 0
$$

对式(18)进行等式变形得到：

$$
\frac { 1 - \lambda P _ { \mathrm { t h } } } { \lambda } = \frac { 1 } { c _ { k } } \{ b _ { k - 1 } p _ { m _ { k - 1 } } ( s _ { 1 } ) \ - b _ { k } p _ { m _ { k } } ( s _ { k } ) \}
$$

由于式(18)等式左边为定值，可知对于 $k \in \{ 1$ -$\cdots \ K { - } 1 \}$ 都有如下关系成立：

$$
\frac { 1 } { c _ { k } } \{ b _ { k - 1 } p _ { m _ { k - 1 } } ( s _ { k } ) \ : - b _ { k } p _ { m _ { k } } ( s _ { k } ) \} = \frac { 1 } { c _ { 1 } } \{ b _ { 0 } p _ { m _ { o } } ( s _ { 1 } ) \ : - b _ { 1 } p _ { m _ { 1 } } S _ { 1 } \}
$$

由式(20)可知最佳门限值 $s _ { k }$ 与 $s _ { 1 }$ 之间的关系是确定的与信号功率和信道状态无关，已知 $s _ { 1 }$ 可确定$s _ { k }$ 反之亦然。

进一步地将约束条件式(11)展开得到:

$$
P _ { \mathrm { t h } } \sum _ { k = 0 } ^ { 4 } b _ { k } \int \ d s _ { s _ { k } } ^ { s _ { k + 1 } } p ( \gamma ) \mathrm d \gamma - \sum _ { k = 0 } ^ { 4 } b _ { k } \int \ d s _ { s _ { k } } ^ { s _ { k + 1 } } p _ { m _ { k } } ( \gamma ) p ( \gamma ) \mathrm d ( \gamma ) = 0
$$

对式(21)进行整理得到:

$$
\sum _ { k = 0 } ^ { 4 } b _ { k } \int \ d s _ { s _ { k } } ^ { s _ { k + 1 } } ( P _ { \mathrm { t h } } - p _ { m _ { k } } ( \gamma ) ) p ( \gamma ) \mathrm { d } \gamma = 0
$$

可见尽管 $s _ { k }$ 与 $s _ { 1 }$ 之间的相对关系与信道状态、发射功率无关但是最优切换阈值 $\{ \ : s _ { 1 } \ : \ : s _ { 2 } \ : \ : \cdots \ : s _ { k } \}$ 与 $\mathrm { { N a - } }$ kagami信道的信噪比概率密度 $p ( \gamma )$ 有关而且在调制方式确定的情况下，最优信噪比切换阈值由 $p ( \gamma )$ 决定。因此信噪比最优切换阈值的确定需要围绕 $p ( \gamma )$ 进行数值分析与计算而 $p ( \gamma )$ 又决定于衰落因子 $m$ 和平均信噪比 $\bar { \gamma }$ 。

综上所述，计算探空火箭最优信噪比切换阈值的方法可以总结为图3所示的步骤，得到的结果即为接收站不同仰角条件下的最优信噪比切换阈值。

![](images/2af39cdabdd5d149c7177641d0685a174434cdfcf7926929e5c714f0eb55944b.jpg)  
图3计算探空火箭最优信噪比切换阈值的步骤Fig.3Method of Computing the optimum signal-to-noiseratio switch threshold

# 4 数值分析

下面仍以高度为 $3 5 0 ~ \mathrm { k m }$ 的探空火箭弹道数据为例计算最优信噪比切换阈值。根据式(3)和式(4)确定衰落因子 $m$ 的计算方法取接收天线仰角为以下典型值时，计算对应的信道衰落因子 $\mathbf { \nabla } _ { m }$ 结果见表2。

表2接收天线仰角与 $\textbf { \em m }$ 的对应关系  
Table 2Relationship between elevation angles and $\mathbf { \nabla } m$ value   

<html><body><table><tr><td>天线仰角/(°)</td><td>10</td><td>40</td><td>66</td><td>78</td><td>82</td></tr><tr><td>m</td><td>1.5</td><td>2.2</td><td>4.6</td><td>6.3</td><td>7.2</td></tr></table></body></html>

在信道衰落因子 $m$ 一定的情况下，信噪比概率密度 $p ( \gamma )$ 还决定于平均信噪比 $\bar { \gamma }$ 的大小，平均信噪比不同则信噪比概率密度也不同，对应的最优信噪比切换阈值也不同。因此需要对不同的 $m$ 值以及 $m$ 值一定情况下不同平均信噪比 $\bar { \gamma }$ 对信噪比切换阈值的影响进

行分析和比较。

在误码率为 ${ { 1 0 } ^ { - 6 } }$ 条件下，瑞利信道以及衰落因子$m = 2 , 2 , 6 , 3$ 的莱斯信道条件下的信噪比最优切换阀值如图4所示。在平均信噪比分别为0、5、10、15、20、25、30、35dB的情况下，计算出对应于BPSK、QPSK、16QAM、64QAM这4种调制方式的最优信噪比切换阀值用曲线将仿真的数值点连接起来得到最优信噪比切换阈值与系统平均信噪比之间的关系 图中 $S _ { 1 } , S _ { 2 }$ 、$S _ { 3 } { \cdot } S _ { 4 }$ 分别表示采用BPSK、QPSK、16QAM和64QAM调制方式的最优切换阈值。

![](images/ef8d6d7614f7390c55eec4246cbadcb993c6911a108305e9fbc7ff92232977b6.jpg)  
图4莱斯信道误码率为 $\mathbf { 1 0 ^ { - 6 } }$ 时最优信噪比阈值 Fig.4Optimum SNR threshold with fading Rician channel when BER is $\mathbf { 1 0 ^ { - 6 } }$

由图4可见当误码率一定时随着系统平均信噪比的增加最优切换阈值总体趋势是逐渐减小。这是因为在信道状态不变的情况下平均信噪比增加，表明信号发送功率有所增加，采用较高阶的调制方式仍可满足误码率要求。探空火箭飞行过程中火箭与地面通信经历的信道模型涵盖了瑞利信道及莱斯信道的多种情况，信噪比最优切换阈值也需要结合飞行参数及不同信道模型得到。其中，平均信噪比的值与火箭飞行的弹道关系密切，不同的径向通信距离对应不同的平均信噪比。经过计算，当天线仰角分别为 $0 ^ { \circ } \sim 5 ^ { \circ }$ ： $5 ^ { \circ }$ $\sim 4 0 ^ { \circ } ; 4 0 ^ { \circ } \sim 6 6 ^ { \circ }$ ： $6 6 ^ { \circ } \sim 7 8 ^ { \circ }$ ： $7 8 ^ { \circ } \sim 8 2 ^ { \circ }$ 时地面站收到信号的平均信噪比分别为29282519、11dB。结合不同信道模型下最优切换阈值采用图3所示的方法，可得到表3所示的最优信噪比切换阈值（分别对应于BPSK、QPSK、16QAM、64QAM)

Table 3relationship of elevation angles and $\textbf { \em m }$ values and average SNR per symbol   

<html><body><table><tr><td>信道 类型</td><td>天线仰 角（°)</td><td>m值</td><td>平均信 噪比/dB</td><td>最优切换阈值/dB</td></tr><tr><td>瑞利 信道</td><td>0~5</td><td>1</td><td>29</td><td>[8.7,12 18.9,25.2]</td></tr><tr><td rowspan="4">莱斯 信道</td><td>5~40</td><td>1.5</td><td>28</td><td>[8.8,12.1 19,25.3]</td></tr><tr><td>40~66</td><td>2.2</td><td>25</td><td>[8.8,12.119,25.3]</td></tr><tr><td>66~78</td><td>4.6</td><td>19</td><td>[9.3,12.619.5,25.8]</td></tr><tr><td>78~82</td><td>6.3</td><td>15</td><td>[9,12.4,19.2 25.5]</td></tr></table></body></html>

由前述可知最优信噪比切换阈值是保证系统满足误码率指标要求下，保证系统最大吞吐量的信噪比切换值是基于系统整体最优的方法得到的结果。为了比较最优噪比切换阈值对系统吞吐量的提高，分别采用最优信噪比切换阈值和恒定误码率信噪比切换阀值两种方法计算系统吞吐量，且计算时均采用同样的探空火箭弹道数据模型。恒定误码率信噪比切换阈值依据AWGN信道下不同调制方式的误码率曲线得到，误码率为 ${ { 1 0 } ^ { - 6 } }$ 时信噪比切换阈值见表4，平均吞吐量3.73bit/symbol。采用最优信噪比切换阈值得到的平均吞吐量3.89bit/symbol。如果原有固定调制方式为BPSK,平均吞吐量1bit/symbol,则用最优信噪比切换阈值获得的吞吐量是固定调制方式的3.89倍，是恒定误码率信噪比切换方法的1.043倍提升了 $4 . 3 \%$ 。

表3不同天线仰角对应不同的 $\textbf { \em m }$ 值和平均信噪比  
表4恒定误码率信噪比切换阈值  

<html><body><table><tr><td>rablc4 COnstalltDER S</td><td>S</td><td>S</td><td>S4</td></tr><tr><td>10.5</td><td>13.8</td><td>20.68</td><td>26.97</td></tr></table></body></html>

# 5结论

（1）探空火箭信道模型不能简单近似为AWGN信道模型因为地面接收站收到的信号是不同强度和相位、不同延迟时间的多径传播信号的叠加。因此探空火箭信道模型可用Nakagami信道模型进行分析。

(2)采用拉格朗日乘数法得到的最优信噪比切换阀值，可在保证系统误码率达到指标要求的前提下，使系统平均吞吐量达到最大，该方法是一种系统全局最优的方法。

(3)在探空火箭的对地通信系统中需要紧密结合地面接收站天线的仰角进行具体分析，根据接收站仰角对接收范围进行分段，计算不同仰角的各段对应的最优信噪比，是一种针对探空火箭可变调制系统的具体工程计算方法。

# 参考文献:

[1] Hayes JF.Adaptive feedback communications [J].IEEE Transactions on Communications 1968 16(1) :29-34.   
[2] Webb W T,Steele R.Variable rate QAM for mobile radio [J].IEEE Transactions on Communications ,1995 43(7): 2223-2230.   
[3] Torrance JM Hanzo L.Upper bound performance of adaptive modulation in a slow Rayleigh fading channel[J].Electronics Letters 1996 32:218-719.   
[4] Torrance JM Hanzo L.Optimization of switching levels for adaptive modulation in a slow Rayleigh fading[J].Electronics Letters 1996 32:1167-1169.   
[5]Choi B J,Hanzo L.Optimum mode-switching assisted constant-power single-and multicarrier adaptive modulation[J]. Vehicular Technology 2003 52(3) : 539-541.   
[6] Choi B J,Hanzo L. Optimum mode-switching assisted adaptivemodulation [C]//Global Telecommunications Conference.2001 GLOBECOM01，2001 6:3316-3320.   
[7] 高欢芹广增，朱琦.AQAM系统最佳信噪比门限值的 研究及其在IEEE802116e中的应用[J].电子学报2009， 37(7):1465-469.   
[8] 杨友福张其善，刘建伟.移动卫星信道建模与统计分析 平[J].遥测遥控 2009 30(6):30-34.   
[9] Clarker H.A statistical theory of mobile-radio reception[J]. Bell.Syst.Tech．1968 47(6):957-1000.   
[10] (挪)裴措特，著，王秋爽，译.移动无线信道(第二版) [M].机械工业出版社2014.   
[11] 吴诗其吴廷勇，卓永宁.卫星通信导论[M].电子工业 出版社 2006.   
[12] 吴诗其朱立冬.通信系统概论[M].清华大学出版社， 2005:84.   
[13] 吴志中.移动通信无线电波传播[M].人民邮电出版社， 2002.   
[14] GoldSmith A.Wirelss communication[M].Cambridge University Press 2005.

(编辑:薛永利)

# （上接第594页)

[4]Herman G T.Image reconstruction from projections: the fundamentalsof computerized tomography[M].Academic press INC 1980.   
[5] Herman G T Lung H.Reconstruction from divergent beams: a comparison of algorithms with and without rebinning[J]. Computers in Biology and Medicine 1980 10:131-139.   
[6] Besson G.CT image reconstruction from fan-parallel data [J].Medical Physics 1999 26:415-426.   
[7] DennerleinF,Noo F,HorneggerJ,etal.Fan-beam filteredbackprojection reconstruction without backprojection weight [J].Physics in Medicine and Biology 2007 52:3227-3240.   
[8] Pan X ,Yu L.Image reconstruction with shift-variant filtration and its implication for noise and resolution properties in fanbeam computed tomography[J].Medical Physics ,2O03,30 (4):590-600.   
[9] 马晨欣胡君杰闫镔.CT扇形束滤波反投影图像重建算 法优化[J].激光与光电子学进展2012，46(9)：1-6.   
[10] 叶海霞，王瞿中.工业CT窄角扇束卷积反投影图像 重建[J].微机发展 200313(9):11-2.   
[11] 瞿中邹永贵，沈宽，等.工业CT窄角扇束扫描下的代 数迭代图像重建算法研究[J].计算机研究与发展， 2005 42(11):1882-888.   
[12]陈庆贵刘赵云卢洪义等。基于窄角扇束扫描的固体 火箭发动机CT图像重建[J].固体火箭技术，201437 (6):877-880.   
[13]Shepp L A Logan B F.Reconstructing interior head tissue from X-ray transmissions[J].IEEE transactions on nuclear science 1974 21:228-236.   
[14]庄天戈.CT原理与算法[M].上海:上海交通大学出版 社1992.   
[15]Shepp L A Logan B F.The fourier reconstruction of a head section[J].IEEE transactions on nuclear science ,1974， 21:21-43.   
[16] 张顺利张定华，程云勇，等.基于像素模型的CT仿真 投影快速计算[J].计算机科学 201138(7)：290-293.   
[17] 乔志伟韩炎潘晋孝.解析法图像重建中的理想斜变滤 波器的进一步研究[J].CT理论与应用研究2013，22 (1):1-14.   
[18]胡君杰，马晨欣,闫镔.CT图像重建中滤波函数的优化 [J].CT理论与应用研究 201322(1):85-92.

(编辑:吕耀辉)