# 耀变体 $\mathtt { C G R a B S \_ l 0 8 3 5 + 6 8 3 5 }$ 的射电QPO及多普勒因子分析

龚云露，易庭丰}²，杨 星，常鑫，李永}(1.云南师范大学 物理与电子信息学院，云南 昆明 650500;2.广西相对论天体物理重点实验室，广西 南宁 530004)

摘要：基于Owens Valley Radio Observatory(OVRO）40米望远镜观测数据，我们收集了耀变体CGRaBS $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 在 $1 5 \mathrm { G H z }$ 射电波段的数据（约12年）。利用Lomb-Scargleperiodogram (LSP)方法和加权小波Z变换(Weight Wavelet Z-transform，WWZ)方法，我们检测到了CGRaBS $\mathbf { J 0 8 3 5 + 6 8 3 5 }$ 存在一个约560天左右的准周期震荡(Quasi-periodicOscillation,QPO)。我们运用超大质量双黑洞系统中的螺旋喷流模型，估算了它的主黑洞质量M的范围约为 $3 . 7 { \times } 1 0 ^ { 8 } \mathsf { M } _ { \odot } { \sim } 3 . 5 \mathrm { X } 1 0 ^ { 9 } \mathsf { M } _ { \odot } ,$ 。为了探究此源是否存在聚束效应，我们使用双指数函数拟合6个爆发过程，发现光变多普勒因子δv的平均值约为10.76。这表明此源的射电辐射存在明显的聚束效应。

关键词：耀变体；CGRaBS $\operatorname { J } 0 8 3 5 + 6 8 3 5$ ；LSP方法；WWZ方法中图分类号：P141.5 文献标识码：A 文章编号：

# 0引言

耀变体（Blazar）是活动星系核(ActiveGalactic Nuclei，AGNs）中比较特殊的一个子类，是最活跃的天体之一。其辐射主要来自于喷流中的高能粒子，由于相对论聚束效应，使得其可以在伽玛波段观测到辐射活动。耀变体可分平谱射电耀变体（FSRQ）和蝎虎座BL型天体（BLLac）两个子类。它在观测上的特征包括高光度、高偏振、快速光变以及非热辐射等[2]。能谱分布（Spectra Energy Distribution，SED）呈现出双峰结构，低能峰是由于同步辐射产生，高能峰是由于电子的逆康普顿辐射过程或者强子辐射产生[-4]。估算多普勒因子的方法有很多种，其中通过射电光变估算多普勒因子(δv)的方法是比较简单的一种因而被广泛应用[5-6]。光变研究能探索耀变体内部辐射过程和物理机制，因此研究天体的光变,及其可能的周期性，对了解活动星系核具有重要意义。

耀变体CGRaBS $\lceil 0 8 3 5 + 6 8 3 5$ （BWE $0 8 3 0 \substack { + 6 8 4 5 }$ ）是一颗红移 $\mathrm { z } { = } 1 . 4 1 4$ 的天体（ $\scriptstyle { \mathfrak { a } } = 0 8$ 3547. 6080866785, $8 \mathrm { = } \mathrm { + } 6 8$ 35 11.493386746）[7]。Romani等人测到这个源在R波段的流量为0.00013mJy[8]。Snellen等人在研究GHz峰频的样本源时，给出了此源在 $3 2 5 \mathrm { M H z }$ 、609MHz和5GHz等不同频率下的流量密度[9]。本文利用欧文斯谷射电天文台（Owens Valley Radio Observatory,OVRO)的长时间监测数据(15GHz)研究CGRaBS $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 的射电光变，检测是否存在准周期振荡。我们还使用双指数函数拟合爆发过程，检验是否存在明显的聚束效应。目前对耀变体光变曲线准周期振荡进行分析的方法主要有两种：Lomb-Scargle periodogram(LSP)[10]和加权小波Z变换(Weighted Wavelet Z Transform，WWZT)[1]。这两种方法非常适合处理非等间隔数据。本文中我们将用这两种方法对耀变体CGRaBS $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 的15GHz射电波段的光变周期性进行研究，并对得到的结果的可靠性和置信度进行评估。

# 1光变曲线

如图1是来自于Owens Valley Radio Observatory(OVRO)40米望远镜观测的耀变体CGRaBS$\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 在 $1 5 \ : \mathrm { G H z }$ 射电波段的光变曲线，去除少量的坏点后，采用460个数据点，约化儒略日MJD范围约为54908\~58871。我们采用光变指数 $\mathrm { \cdot A ^ { [ 1 2 - 1 3 ] } }$ 来判断天体的活跃程度。

$$
A = \frac { f _ { \operatorname* { m a x } } - f _ { \operatorname* { m i n } } } { f _ { \operatorname* { m a x } } + f _ { \operatorname* { m i n } } } .
$$

其中 $\mathrm { f } _ { \mathrm { m a x } }$ 和 $ { \mathrm { f } _ { \mathrm { m i n } } }$ 分别表示流量的最大值和最小值，光变指数 $\mathrm { ~ A ~ }$ 值越大表示天体越活跃。通过计算可以得到CGRaBS $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 天体在射电波段的光变指数为0.98，这表明CGRaBS（204号 $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 是个非常活跃的天体。

![](images/8a099d12999d3ae497e29fa4a3a0f9bc3bfc0e56bad9174e077698775c7611ed.jpg)  
图1蓝线表示耀变体CGRaBS $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 在15GHz射电波段的光变曲线，红线表示正弦函数对光变曲线的大致拟合。

Fig.1 The blue line represents the light curve of the blazar CGRaBS $\lceil 0 8 3 5 + 6 8 3 5$ in the $1 5 ~ \mathrm { G H z }$ radio band,and the red line represents the rough fit of the sine function to the light curve.

# 2光变曲线的周期分析

# 2.1 LSP方法

检测隐藏在噪声中的周期性信号是天文数据时间序列分析中的一个重要目标。Lomb-Scargleperiodogram（LSP）方法可以对非均匀采样的时间序列周期图进行相位修正处理，能够在一定范围内对非均匀采样的时间间隔引起的误报周期进行修正[10]。因此，Lomb-Scargle periodogram方法能很好的寻找隐藏在噪声中的准周期振荡光变。LSP方法的原理是基于傅立叶变换，使用正弦函数模型，基本公式如下[14-15]。

$$
\begin{array} { c l l } { \displaystyle P x ( \omega ) = \frac { 1 } { 2 } \left\{ \frac { \displaystyle \sum _ { j = 1 } ^ { N _ { 0 } } \left( x ( t _ { j } ) - \overline { { x } } \right) \cos \omega \left( t _ { j } - \tau \right) } { \displaystyle \sum _ { j = 1 } ^ { N _ { 0 } } C O S ^ { 2 } \omega \left( t _ { j } - \tau \right) } + \frac { \displaystyle \sum _ { j = 1 } ^ { N _ { 0 } } \left( x ( t _ { j } ) - \overline { { x } } \right) \sin \omega \left( t _ { j } - \tau \right) } { \displaystyle \sum _ { j = 1 } ^ { N _ { 0 } } \sin ^ { 2 } \omega \left( t _ { j } - \tau \right) } \right\} } \end{array}
$$

其中t为对应时间t的相位修正，计算公式为：

$$
\tan ( 2 \omega \tau ) = \frac { \sum _ { j = 1 } ^ { N _ { 0 } } s i n ^ { 2 } 2 \omega t _ { j } } { \sum _ { j = 1 } ^ { N _ { 0 } } c o s ^ { 2 } 2 \omega t _ { j } }
$$

运用（2）式有几个优点是通常的离散傅立叶变换所不具备的。首先，公式中包含时间项t使得周期计算不随时间原点的变化而变化。其次，这种形式使得周期图分析完全等价于正弦曲线对数据的最小二乘拟合。为了验证LSP方法计算准周期的正确性，如图2所示，我们先对周期图进行幂率拟合，得到蒙特卡罗方法计算置信度的所需参数幂率指数β[16]，然后用Python编写程序计算了CGRaBS： $\lceil 0 8 3 5 + 6 8 3 5$ 天体的置信度结果，如图3所示。图3中绿色线表示准周期图，其峰值就是准周期结果；蓝色、红色、黑色线分别代表蒙特卡罗模拟的 $9 5 \%$ 、$9 9 \%$ 、 $9 9 . 7 \%$ 置信度。图3中的绿线有两个明显的峰值分别为562天和1020天，并且两个峰的置信度都超过了 $9 9 . 7 \%$ ，说明两个峰值结果都是可靠的，但是1020天约为562天的两倍，所以我们取最小正周期即562天作为CGRaBS $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 天体的准周期结果。

![](images/0b5d728daf484c17bd094d5f27cba0a93259aea5414ac1ff0e07814dae957122.jpg)  
图2CGRaBS $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 在射电波段的对数幂率谱。

![](images/b815c709771e6b5a18b4fa1d11d8dd4da216c9a6f514607fd063dae689167949.jpg)  
Fig.2 CGRaBS J0835-6835 ob ject logpower spectrum in radio band.   
图3CGRaBS $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 在射电波段的QPO的置信度的蒙特卡罗模拟分析结果。 Fig.3 The Monte Carlo simulation analysis results of the confidence level of the $\boldsymbol { \mathrm { { Q P 0 } } }$ of CGRaBS J0835-6835 in radio band.

# 2.2加权小波Z变换方法

小波分析（WaveletAanlysis）是一种新的分析方法，他是继Fourier分析之后纯粹数学和应用数学完美结合的又一光辉典范。利用 Morlet小波作为小波母函数进行变换，复Morlet 小波为[17]：

$$
\psi \big ( \mathrm { t } \big ) = e ^ { - t ^ { 2 } / 2 } \big ( e ^ { i w _ { 0 } t } - e ^ { - w _ { 0 } / 2 } \big ) ,
$$

Foster定义了加权小波变换(WWT）[18]：

$$
W W T = \frac { \left( N _ { \mathrm { e f f } } - 1 \right) V _ { y } } { 2 V _ { x } } ,
$$

其中

$$
N _ { \mathrm { e f f } } = \frac { \left( \sum \omega _ { \alpha } \right) ^ { 2 } } { \sum \omega _ { \alpha } ^ { \ 2 } } , V _ { x } = \frac { \sum \omega _ { \alpha } x ^ { 2 } \left( t _ { \alpha } \right) } { \displaystyle \sum \omega _ { \beta } } - \left[ \frac { \sum \omega _ { \alpha } x \left( t _ { \alpha } \right) } { \displaystyle \sum \omega _ { \beta } } \right] ^ { 2 } , V _ { y } = \frac { \sum \omega _ { \alpha } y ^ { 2 } \left( t _ { \alpha } \right) } { \displaystyle \sum _ { \beta } \omega _ { \beta } } - \left[ \frac { \sum \omega _ { \alpha } y \left( t _ { \alpha } \right) } { \displaystyle \sum _ { \beta } \omega _ { \beta } } \right] ^ { 2 } .
$$

由于小波形状的变化，低频部分的有效数据 $\mathbf { N } _ { \mathrm { e f f } }$ 会比高频部分的有效数据多，因此WWT 的值会向高频部分偏移，导致结果出现偏差。于是Foster 根据他所提出的Z统计量定义了加权小波 $Z$ 变换为[10]:

$$
Z = \frac { \big ( N _ { \mathrm { e f f } } - 3 \big ) V _ { y } } { 2 \big ( V _ { x } - V _ { y } \big ) } ,
$$

利用(6)式可以得到如图4的准周期图，左图是时间周期平面中WWZ功率彩色缩放的分布，右图是时间平均功率（黑色曲线）作为周期的函数图，其中蓝色虚线表示置信概率在99.7%和 $9 5 \%$ 的位置。根据WWZ图的极大值就可以确定光变曲线的周期。图4中显示了一个明显的极大值560天且置信概率超过了 $9 9 . 7 \%$ ，也就是说560天的准周期结果是可靠的。

![](images/246aba1d7f222f379314a12bc2f54f68706228c8b650185fc8c1cff013176e86.jpg)  
图4WWZT方法对CGRaBSJ $0 8 3 5 + 6 8 3 5$ 在射电波段QPO的分析结果。  
Fig.4 The WWZT test result for QPO search CGRaBS $1 0 8 3 5 + 6 8 3 5$ at radio band.

# 3多普勒因子分析

多普勒因子(8)可以通过喷流中物质流速度(V)以及视角(0)两个本征参数定义。然而这两个量都是难以直接观测的量，因此，有多用间接方法估算多普勒因子。在各种估算多普勒因子的方法中，通过射电光变估算多普勒因子 $( \delta _ { \mathrm { v } } )$ 的方法相对比较简单，因而被广泛应用。

![](images/5e9f5a86dd248450ceaf26f51a556ea6892686a52ec5464703eb3b1d1304e798.jpg)  
图5双指数函数对CGRaBSJ $0 8 3 5 + 6 8 3 5$ 的6个爆发（flare）过程的曲线拟合。MJD为约化儒略日，单位是天。  
Fig.5 The double exponential function fits the curves of the 6 flares of CGRaBS $1 0 8 3 5 \substack { + 6 8 3 5 }$ .MJDis Modified Juliai

Day，the unit is day.

文献[19-20]中详细介绍了亮温度和双指数函数公式及估算多普勒因子的过程。双指数函数公式如下：

$$
\mathrm { F ( t ) } = F _ { c } + F _ { 0 } ( e ^ { \frac { t _ { 0 - t } } { t _ { r } } } + e ^ { \frac { t - t _ { 0 } } { t _ { d } } } ) ^ { - 1 }
$$

我们利用亮温度公式估算CGRaBS $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 天体的射电亮温度约分布在 $3 . 7 \times 1 0 ^ { 1 3 } { \sim } 2 . 3 \times$ ${ 1 0 } ^ { 1 4 } \mathrm { K } ,$ ，超过逆康普顿极限温度或平衡亮温度几个量级，表明此源的射电辐射存在明显的聚束效应。双指数函数拟合的6个爆发过程如图5所示。类似文献[21]选取平衡亮温度作为内禀亮温度，进一步估算对应的光变多普勒因子。每个爆发过程的拟合参数如表1，第1列为约化儒略日范围；第2列为拟合所得的约化最小残差平方和 $\hat { \beta }$ ，其详细的定义见文献[22]；第3列为归一化后的卡方值，其定义为 $\chi ^ { 2 } / \mathrm { d o f }$ ， $\begin{array} { r } { \chi ^ { 2 } = \sum _ { i = 1 } ^ { N } \left( \frac { { F _ { i } } - { f _ { i } } } { \sigma } \right) ^ { 2 } } \end{array}$ ，其中 $\mathrm { F _ { i } }$ 为实测流量，fi为拟合流量， $\sigma$ 为残差绝对值的标准偏差，自由度 ${ \mathrm { d o f } } = \Nu - 5$ ；第4列为拟合峰值对应的约化儒略日及误差；第5列为基底流量及误差；第6列为爆发的幅度及误差；第7列和第8列分别为指数上升时标和下降时标及误差；第9列为每个爆发过程所对应的多普勒因子。δv的值分布在 $8 . 8 7 { \pm } 0 . 6 8 { \sim } 1 4 . 4 5 { \pm } 0 . 2 3$ ，平均值约为10.76。

表1爆发过程的拟合结果  

<html><body><table><tr><td colspan="9">Table1 The results of flare fitting</td></tr><tr><td>peak range</td><td></td><td>x2/dof</td><td>to</td><td>Fc</td><td>Fo</td><td>tr</td><td>td</td><td>v</td></tr><tr><td></td><td>(2）</td><td>(3)</td><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>(1）</td><td></td><td></td><td>（4）</td><td>(5）</td><td>(6)</td><td>（7）</td><td>(8）</td><td>(9）</td></tr><tr><td>54908.9-55366.2</td><td>1.52E-04</td><td>1.54</td><td>55062.97±26.79</td><td>0.06±0.04</td><td>0.26±0.03</td><td>140.51±49.16</td><td>69.25±24.09</td><td>9.63±0.34</td></tr><tr><td>55623.2-56414.8</td><td>3.98E-04</td><td>2.94</td><td>55978.50±9.63</td><td>0.07±0.04</td><td>0.33±0.11</td><td>152.17±48.32</td><td>98.21±56.41</td><td>8.87±0.68</td></tr><tr><td>56487.6-57146.8</td><td>3.14E-04</td><td>1.63</td><td>56909.21±27.48</td><td>0.14±0.02</td><td>0.31±0.17</td><td>146.58±20.94</td><td>64.17±44.78</td><td>10.43±0.35</td></tr><tr><td>57186.7-57671.5</td><td>1.43E-04</td><td>1.95</td><td>57336.36±26.94</td><td>0.24±0.06</td><td>0.33±0.03</td><td>95.97±28.51</td><td>123.84±24.31</td><td>9.36±0.12</td></tr><tr><td>57717.3-58174.0</td><td>4.23E-04</td><td>1.15</td><td>57978.93±11.71</td><td>0.11±0.01</td><td>0.36±0.03</td><td>123.38±43.37</td><td>53.92±19.23</td><td>11.77±0.84</td></tr><tr><td>58257.7-58724.5</td><td>1.08E-04</td><td>2.79</td><td>58589.75±18.08</td><td>0.07±0.04</td><td>0.11±0.01</td><td>33.51±38.41</td><td>128.52±47.14</td><td>14.45±0.23</td></tr></table></body></html>

# 4讨论与结论

通过收集欧文斯谷射电天文台的长时间监测数据，我们利用LSP方法和加权小波Z变换方法对CGRaBS $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 的射电波段光变曲线的准周期振荡进行分析。LSP方法分析得到的准周期约为562天和1020天，并且其置信度都大于 $3 \sigma$ ( $9 9 . 7 \%$ ），1020天大约是562天的两倍，故可以认为CGRaBS $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 的准周期约为562天。加权小波Z变换方法得到的准周期约为560天，且置信度也超过了 $3 \sigma$ （ $9 9 . 7 \% \AA \mathrm { , }$ ）。两种检测准周期的方法得到的结果都大致约为560天，检验的结果相互印证，所以我们认为CGRaBS！ $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 天体的准周期约为560天。同时，我们利用双指数函数拟合了6个爆发过程，得到 $| \delta _ { \mathrm { V } }$ 的值分布 $8 . 8 7 { \pm } 0 . 6 8 { \sim } 1 4 . 4 5 { \pm } 0 . 2 3$ ，平均值约为10.76。结果表明CGRaBS $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 的射电辐射存在明显的聚束效应，支持相对论性喷流模型。耀变体长周期光变的物理模型现在仍然是悬而未决的问题，为了解决这些问题，已有很多物理模型被提出，例如：双黑洞模型[23]、螺旋喷流模型[24]和薄吸积盘理论[25]等。

根据CGRaBS $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 天体产生的560天准周期，其物理过程可能是喷流的螺旋运动[26]。Rieger在2004年给出了观测准周期P与实际物理驱动周期 $P _ { d }$ 之间的关系公式为：

$$
P _ { \mathrm { \it d } } ~ \approx ~ \frac { \gamma _ { b } ^ { 2 } } { 1 ~ + ~ z } ~ P
$$

其中红移 $z = 1 . 4 1 4 ^ { [ 7 ] }$ ， $\boldsymbol { \gamma } _ { b }$ 是体洛伦兹因子约等于 $7 . 5 ^ { [ 2 7 ] }$ 。基于（7）式可以得到实际物理驱动周期 $P _ { d } { \approx } 3 5 . 7 5 \mathrm { y r }$ 。另外，如果 $8 \mathit { \Pi } _ { b } { = } 1 5$ 作为参数[28]， $P _ { d } { \approx } 1 4 3 . 0 0 ~ \mathrm { y r }$ 。如果主黑洞和次黑洞之间的质量比 $R { \leqslant } 1 / 3$ ，称之为“majormerger”（主并合）。如果 $3 { \leqslant } R { \leqslant } 1 0 ^ { 4 }$ ，称之为“minormerger”(次并合)[29]。无论质量比如何，主黑洞的质量都可以用如下公式估计[30]：

$$
M \ \approx \ P _ { d } ^ { \frac { 8 } { 5 } } R ^ { \frac { 3 } { 5 } } 1 0 ^ { 6 } \mathrm { M } _ { \odot }
$$

其中 $P _ { d }$ 以年为单位计，对于SMBBH系统的“主并合”，质量比可以假设为 $R { = } 3 / 2$ 。把我们的参数代入到（8）式中，得到CGRaBS） $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 的主黑洞质量大约为 $M { = } 3 . 7 { \times } 1 0 ^ { 8 } \mathrm { M } _ { \odot }$ 。同理，如果使用 $\gamma _ { b } = 1 5$ 作为参数，次并合的SMBBH系统的主黑洞质量为 $M = 3 . 5 { \times } 1 0 ^ { 9 } \mathrm { M } _ { \odot }$ ，故我们取CGRaBS $\mathrm { J 0 8 3 5 + 6 8 3 5 }$ 的主黑洞质量 $M$ 的范围约为 $3 . 7 { \times } 1 0 ^ { 8 } \mathrm { M } _ { \odot } { \sim } 3 . 5 { \times } 1 0 ^ { 9 } \mathrm { M } _ { \odot }$ 。

# 参考文献：

[1]UrryCMegan,PadovaniPaolo.Unified Schemes forRadio-LoudActive Galactic Nuclei[J].Publicationsofthe Astronomical Society of the Pacific,1995,107(715): 803-845. [2]DondiL,GhiseliniG.Gamma-ray-loudblazarsandbeaming[J].MonthlyNoticesoftheRoyalAstronomical Society995, 273(3): 583-595.   
[3]Xie G Z,BaiJM,Zhang X,et al.The massve blackhole in thecenterof theactive galaxy MRK421[J].Astronomyand Astrophysics,1998,334: L29-L31.   
[4]Zhang X,ZhaoG,ZhengYG,et al.CCDphotometryandoptical variabiltyof gamma-ray-loudBLLacertaeobjectOJ287ina low,fainter state [J]. The Astronomical Journal,20o7,133(5):1995.   
[5]ValtaojaE，LahteenmakiA，Terasranta H，etal.Total Flux Density Variationsin ExtragalacticRadio Sources.I. Decompositionof Variations into Exponential Flares[J].Astrophysical Jourmal Supplement,1999,12O(1):95-99.   
[6]Laehteenmaeki A,ValtaojaE.TotalFluxDensityVariations inExtragalacticRadio Sources.3.DoplerBosting21Factors, Lorentz Factors and Viewing Angles for Active Galactic Nuclei[J].The Astrophysical Journal,20o9,521(2):493.   
[7]MasaroE，GommiP,etal.Roma-BZCAT:AmultifrequencycatalogueofBlazars[J].AstronomyandAstrophysics,29,495 (2): 691-697.   
[8]Healey SE，Romani R W，CoterG,et al.CGRaBS:An Al-Sky Survey of Gamma-Ray Blazar Candidates[J].The Astrophysical Journal Supplement Series,20o8,175(1):97.   
[9]A.G.Snellen，R.T.Schilizzi,etal.ANew SampleofFaint Gigahertz Peaked Spectrum Radio Sources[J].Astronomyand Astrophysics,1998,13(1):18.   
[10]RejkubaM,MinitiD,SilvaDR.Long periodvariables inNGC5128-ICatalogue[J]. Astronomyand Astrophysics,203, 406(1).   
[11]FOSTERG.Time Series Analysis byProjection．I.Statistical PropertiesofFourier Analysis[J.The AstrophysicalJoual, 1996,(111) :541-554.   
[12]Zhang,L,Fan,J.-H,Cheng,K.-S.The Multiwavelength DoplerFactors foraSampleofGamma-RayLoudBlazars[J]. Publications of the Astronomical Society of Japan,54(2):159-169..   
[13]Li,HZ,Chen,LE,Dai,H,etal.ThePeriodicityAalysisoftheLightCurveofC279andImplicationsforthePrecesioJet[J]. Publications of the Astronomical Society of the Pacific,2009,121(885):1172-1179.   
[14]Seperuelo Duarte E,Alencar S HP,Batalha C,et al. Spectrophotometric analysis ofthe TTauri starGQLupi A[J]. Astronomy and Astrophysics,2008,489(1):349-357.   
[15]Yang X,YiTF,et al. The $\boldsymbol { \gamma }$ Ray and Optical Variability Analysis of the BLLac Object 3FGL J0449.4-4350[J].Publications of the Astronomical Society of the Pacific,2020,132(1010): 044101. [16] Timmer,J, Koenig,M. On generating power law noise.[J]. astronomy & astrophysics,1995,300:707--710.   
[17]GrossmanA,MorletJ.DecompositionofHardyfunctions intosquare integrable wavelets ofconstantshape[J].SIAMjoural on mathematical analysis,1984,15(4): 723-736.   
[18]FOSTERG.Wavelets forperiodanalysis ofunevenlysampled time series [J]．The AstrophysicalJournal,1996,(12): 1709-1729. [19]Wagner S.J,A Witzel. Intraday variability in the BLLac object $0 9 5 4 + 6 5 8 [ \mathrm { J } ]$ .astronomy & astrophysics,1993,271(1):344. [20]Ackermann M，Ajell M，Baldini L，et al.FERMI GAMMA-RAY SPACE TELESCOPE OBSERVATIONS OF GAMMA-RAY OUTBURSTSFROM 3C 454.3 IN 2009 DECEMBER AND 2010 APRIL[J].The Astrophysical Journal, 2010,721(2):1383-1396. [21]Lhteenmki A,ValtaojaE,WiikAK.Total Flux Density Variations inExtragalactic Radio Sources.II Determining the Limiting Brightness Temperature for Synchrotron Sources[J].The Astrophysical Journal,2Oo9,511(1):12. [22]杨星，易庭丰，毛李胜．平谱射电类星体 $\mathrm { B } 3 0 3 0 7 + 3 8 0$ 的15GHz射电光变分析[J].天文研究与技术，2020, 17(2):1189-1196. Yang Xing,Yi Tingfeng,MaoLisheng.The 15GHz radio photo-change analysis of the flat-spectrum radio quasar ${ \bf B } 3 0 3 0 7 +$ 380[J].Astronomy Research and Technology,2020,17(2):1189-1196. [23]ValtaojaE,TerasrantaH,Tormikoski M,etal.Radio MonitoringofOJ287andBinary Black Hole Models forPeriodic Outbursts [J].The Astrophysical Journal,2008,531(2):744. [24]Rani B, Wita PJ, Gupta A C.NEARLY PERIODIC FLUCTUATIONS IN THE LONG-TERM X-RAY LIGHT CURVES OF THE BLAZARS AO $0 2 3 5 \substack { + 1 6 4 }$ AND 1ES 2321+419[J].Astrophysical Jourmal, 2009,696(2):2170-2178. [25]Zhang X,XieGZ,BaiJM.Ahistorical lightcurve of3C345anditsperiodic analysis[J].Astronomyand Astrophysics, 1998,330(2):469-473. [26]NemmenRS,Georganopoulos MGuiriecS,etal.AUniversal Scaling fortheEnergeticsofRelativistic Jets fromBlack Hole Systems[J]. Science,2012,338(6113):1445-1448. [27]Henri,G.，& Sauge,L.The bulk Lorentz factor crisis of TeV blazars $\because$ evidence for an inhomogeneous pileup energy distribution ?[J]. The Astrophysical Journal,2006,640(1):185. [28]Guinevere K，Martin H.Aunified modelfortheevolutionof galaxies andquasars[J].MonthlyNoticesof theRoyal Astronomical Society. 2000,311(3):576-588. [29]Begelman M C，Blandford R D，Rees MJ.Massve black hole binaries in active galactic nuclei[J]. Nature,1980, 287(5780):307-309. [30]William,H,Le,etal.Resoance inForcedOscilatiosofAccetionDiskandKioert Quasi-peiodicOsilios[J]. Astrophysical Journal Letters,2004. 603:L93-L96.

# Radio quasi-period oscillation analysis of blazar CGRaBS J0835+6835

Gong Yunlu’，Yi Tingfeng'²， Yang Xing'，Chang Xin'，Li Yong' (1.Schooloficsdeectronicinforatio,YuanalUiversityKuningoo,hina,yiigfeng98@.com; Guangxi Key Laboratory for the Relativistic Astrophysics,Nanning 53ooO4,China)

2.

Abstract: Based on the Owens Valley Radio Observatory (OVR) $4 0 \mathrm { m }$ telescope observation database，we collected data from the blazar CGRaBS $\mathbf { J 0 8 3 5 + 6 8 3 5 }$ in the $1 5 ~ \mathrm { { G H z } }$ radio band (approximately 12 years). Using the Lomb-Scargle periodogram (LSP) method and the Weight Wavelet Z-transform (WWZ) method, we detected a quasi-period oscilltion of about 560 days in the CGRaBS $\mathbf { J 0 8 3 5 + 6 8 3 5 }$ object. We used a spiral jet model in the supermassive dual black hole system to estimate the mass range of its primary black hole M range is $3 . 7 { \times } 1 0 ^ { 8 } \mathrm { M o }$ to $3 . 5 { \times } 1 0 ^ { 9 } \mathrm { M } _ { \odot }$ To investigate whether there is a beam effect in this source, we used a double exponential function to fit six burst processes and found that the average value of the variability Doppler factor $\delta _ { \mathrm { V } }$ is about 1O.76.This result indicates there is a significant beam effect in the radio radiation of this source.

Keywords: Blazar; CGRaBS JO835-6835; LSP Method; WWZ Method