# 直流功率调制对黑龙江电网功角稳定性的作用分析

张帆」韩民晓刘晋} 徐洪涛² 边二曼²（1.新能源电力系统国家重点实验室（华北电力大学）北京1022062.国网黑龙江省电力有限公司哈尔滨150000）

![](images/43a3da7012ffbddf48c70e5f924b7e1360722cefebf2b294b605bab902c4bc5c.jpg)

张帆男1994年生，硕士研究生，研究方向为高压直流输电技术。

摘要：以黑龙江电网为研究对象，当南送吉林、辽宁电网的交流通道发生故障时，将导致原来流向吉林、辽宁的潮流沿哈南－华民方向汇入扎鲁特，增加了潮流通道的等效阻抗，给黑龙江电网带来功角稳定性问题。本文利用扎青直流的功率调制来改善黑龙江电网的功角稳定性，提出利用Prony分析法对直流调制器进行参数整定，讨论了调制增益的变化对系统稳定性的影响。研究结果对实际电网运行中功角稳定性的改善具有一定的参考价值。

关键词：高压直流输电黑龙江电网直流功率调制Prony 分析功角稳定中图分类号：TM712

# Study of Rotor Angle Stability of Heilongjiang Power Grid by HVDC Power Modulation

Zhang Fan'Han MinxiaolLiu Jin'Xu Hongtao² Bian Erman² （1.North China Electric Power UniversityBeijing102206 China 2.State Grid Heilongjiang Electric Power CorporationHaerbin150000 China ）

![](images/a686ee43efa96029c2112f2e18d09b6b4212f721fdefb2461e4d7dd914067177.jpg)

韩民晓 男 1963年生，教授，博士生导师研究方向为电力电子在电力系统中的应用。

Abstract: When fault occurs in AC channel which sent electric power from Heilongjiang to Jilin and Liaoning,the unbalance of power and the increase of transfer impedance will bring a great challenge to the rotor angle stability of the Heilongjiang grid. HVDC modulation has been considered to improve the rotor angle transient stability. The Prony method is used to tune the DC power modulator,and the influence of the variation of modulation gain on the stability of the system is also discussed. The study results are expected to be helpful for the operation of Heilongjiang power grid.

Keywords: HVDC, Heilongjiang power grid, DC power modulation, Prony analysis, angle transient stability

# 1 引言

受能源资源和负荷逆向分布的特点所限，在东北地区风电与火电同时存在外送需求，建设特高压直流外送通道已成为优化资源配置的重要方式。扎青特高压直流输电工程投运后，东北电网主要输电格局发生变化，自北部、东部、南部向扎鲁特换流站及近区变电站汇集电力，缓解了黑吉、辽吉省间$5 0 0 \mathrm { k V }$ 交流输电的潮流压力，但原有交流输电仍然承担较大一部分潮流。若省间交流输电出现 $N - 1$ 故障，会出现过剩功率涌向扎鲁特换流站，且会对黑龙江电网带来严重的功角稳定性问题。如何利用直流输电系统有功功率灵活控制的功能，适应故障特性，提高黑龙江电网安全稳定性，成为一个亟待解决的问题。

直流输电的换流器由大量电力电子器件构成，一般具有1.1倍的长期过载能力和3s的1.5倍短时过载能力。在大扰动情况下，利用其短时过载能力，快速调制其注入交流系统的直流功率，可以弥补暂态过程中送、受端的功率不平衡量，提高暂态功角稳定性。直流功率调制分为大方式调制和小方式调制，大方式调制幅度可达直流功率的 $20 \% \sim 5 0 \%$ 旨在提高暂态稳定性，如紧急直流功率支援；小方式调制幅度一般只有直流功率的 $3 \% \sim 1 0 \%$ ，旨在提高动态稳定性，抑制功率振荡。目前在利用直流功率调制提高电力系统稳定性方面已有大量研究[1-13]。当系统发生故障时，电网的结构，运行方式，故障地点、类型及严重程度，决定了直流输电系统将选取何种控制方式、调制信号[14-16]和调制规律[17-19]来提高系统暂态稳定裕度，且必须通过仔细研究和大量仿真才能得出相关结论。虽然目前已有大量文献对直流调制相关问题做了研究分析，但对于调制器参数的选取多采取实际工程经验，并未进行详细、深入的研究。

本文在PSASP中利用黑龙江电网2018年的运算数据，研究了直流功率调制对系统功角稳定性的影响，并利用Prony分析法对调制参数进行整定，对不同增益情况下的功角稳定进行了分析。

# 2 直流功率调制

# 2.1直流功率调制原理

直流功率调制原理是将一个直流功率调制器附加于高压直流输电系统的控制单元中，当系统遭受大扰动后，令其对于故障系统中的过剩功率或功率缺额进行快速吸收或补偿，从而减小了加速面积，增加了减速面积，达到提高系统功角稳定性的目的。

如图1所示，在交直流外送系统中，如果交流线路发生 $N - 1$ 故障，会使 $X _ { \Sigma }$ 增大，容易引起送端系统功角稳定问题。以送端系统电气量作为功率调制器的输入信号，功率调制器输出的功率调制信号与功率控制指令信号进行综合，对直流输出功率进行控制，达到改善系统功角稳定的目的。直流输电控制系统如图2所示。

![](images/558b3e936f14bde7e49ae085c11214ed45a93e9e7fcdcd367ca083d377ae89d7.jpg)  
图1交直流输电系统

![](images/cb917a037c8e89aee25c1fc84d7aa1d60c4b93415e9ea3996d5bf0591ae55baa.jpg)  
Fig.1AC and DC transmission system   
图2直流输电控制系统  
Fig.2DC transmission control system

图2中，功率整定值 $P _ { \mathrm { d r e f } }$ 与功率调制信号 $P _ { \mathrm { M O D } }$ 之和除以直流电压 $U _ { \mathrm { d } }$ 得到电流整定信号，其经过低压限流（VoltageDependentCurrent OrderLimit,VDCOL)和电流控制放大器(CurrentControlAmplifier，CCA)输出为整流侧触发角 $\alpha$ ，进而对换流阀进行控制。

# 2.2直流功率调制器模型

针对 $N - 1$ 故障引起的稳定问题，既可选择功率作为调制输入信号，也可选择频率作为调制输入信号。由于不同线路的有功功率变化不同，当以线路有功功率变化 $\Delta P$ 为输入信号时，需建立专门的信号传输路线，将测量信号从监测点传送至直流换流站。但以母线频率信号或频率变化 $\Delta f$ 为输入信号时，可以直接检测换流站附近母线，无需建立专门的信号传输线路，因此以交流系统母线频率或频率变化为输入信号更为方便，本文选用整流站母线频

率作为调制输入信号。

直流功率调制器结构如图3所示。其中， $s / ( 1 +$ $s T _ { \mathrm { d } } )$ 为微分环节，当微分时间常数 $T _ { \mathrm { d } }$ 很小时，近似为微分器，该环节的主要作用是提取信号中的变化趋势，以得到较好的动态控制效果， $T _ { \mathrm { d } }$ 越大,输出量的相位超前量越小，影响阻尼效果，但 $T _ { \mathrm { d } }$ 值太小，则不能准确反映实际测量回路中无法避免的时间滞后。经综合考虑，计算中取 $T _ { \mathrm { d } }$ 范围为$0 . 1 \sim 1 \mathrm { s }$ 。 $1 / ( 1 + s T _ { \mathrm { f } } )$ 和 $s / ( s + \varepsilon )$ 为低通滤波和高通滤波组合的带通滤波，可以在满足某个固定频率或频带上幅值最大，而在其他频带上被尽量滤除，其中 $T _ { \mathrm { f } }$ 为滤波器时间常数， $\boldsymbol { \varepsilon }$ 为引导补偿因子。 $( s ^ { 2 } +$ $A s + B ) / ( s ^ { 2 } + C s + D )$ 为陷波滤波器，其中 $A$ ， $B$ ， $C$ $D$ 为陷波滤波器参数，工程应用中一般不参与控制作用，取 $A = B = C = D$ 。 $K$ 为调制增益； $P _ { \mathrm { M I N } }$ 为设定的直流功率与功率调制量下限之和； $P _ { \mathrm { M A X } }$ 为设定的直流功率与功率调制量上限之和； $P _ { \mathrm { M O D } }$ 为输出功率调制信号。

![](images/f3c282e1d2ae4cb9ba557240b11c764d15bbe67a2bd1e871445acca6673aee30.jpg)  
图3直流功率调制控制器结构  
Fig.3 Structure ofHVDC power modulation controller

# 3基于Prony分析的调制参数整定

# 3.1 Prony分析法

Prony分析法是用一组指数函数的线性组合来构造数学模型，描述等间距采样数据，形成了一种能够直接估算给定信号的频率、衰减因子、幅值和初相的算法。正是因为Prony分析法能够获得给定信号的特征，因此在电力系统分析中被广泛使用[20]。利用Prony分析法对故障时送端母线频率信号进行频域分析，从而对调制器进行参数设置，具有较好的有效性。

Prony算法可用一组指数函数项的线性组合来拟合系统的实测信号，即

$$
y ( n ) = \sum _ { i = 1 } ^ { p } b _ { i } z _ { i } ^ { n } = \sum _ { i = 1 } ^ { p } A _ { i } \mathrm { e } ^ { \mathrm { i } \theta _ { i } } \mathrm { e } ^ { ( \alpha _ { i } + \mathrm { j } 2 \pi f _ { i } ) \Delta t n }
$$

式中： $n = 0 \sim N - 1$ ， $N$ 为 $y ( n )$ 的数据个数； $p$ 为模型阶数； $A _ { i }$ 为模式幅值； $\theta _ { i }$ 为模式初相位； $\alpha _ { i }$ 为模式衰减因子； $f _ { i }$ 为模式频率； $\Delta t$ 为时间间隔。

Prony分析法信号拟合结果与Prony参数选取关系密切。选取的参数包括采样频率、时间长度、模型阶次等。如果参数选择不当，可能难以得到准确的结果。

（1）采样频率 $f _ { p }$ 。为保证采样频率大于2倍信号最高频率，并抑制频谱混叠现象，通常按照4倍信号最高频率进行采样。过高的采样频率可能使拟合效果变差，反而不利于结果准确性。

（2）时间长度 $T _ { p }$ 。系统故障时，根据故障时间截取适当时间长度的调制信号进行分析。时间长度也不宜过大，因为这可能导致无法辨识出衰减较快的分量，造成信息丢失，不利于对结果的分析。

(3）模型阶次 $p$ 。因为电力系统动态过程中系统阶数非常高，所以一般采用降阶模型来近似拟合。通常，Prony分析法的定阶方法是先取一个较大的初始阶数 $L$ ，使其远大于信号中实际包含的指数项个数，得到 $L$ 个指数项分量。然后从这些分量中选取 $p$ 个分量的最优子集，使它在最小平方意义上逼近观察到的数据。然后用最小二乘法，取使误差平方和最小的 $p$ 为Prony分析时使用的阶数。

# 3.2调制参数选取

调制器参数设置对调制器性能的影响十分显著，以往的文献中多利用工程经验进行参数设置，本文提出基于Prony分析法进行调制参数的选取。

无论哪种故障，在未加入调制手段的条件下，整流侧母线频率信号的频谱中均存在一些能量较为集中的频带；而在系统无故障运行的信号中只存在单一的、能量较低的频率成分；频谱中频率极低的频率成分，可以认为是直流成分，从信号的角度分析，直流量并不会影响系统的稳定性。通过对整流侧母线频率信号进行Prony分析，确定主要的频带和参数，完成调制参数的选取。

从频域角度分析，输出直流调制功率主频率应与母线频率信号主振荡频率相同，才能获得很好的调制效果。可以理解为故障使母线频率信号某一主频带的能量大量增加，直流附加信号对系统进行相同频率的功率支援，即可以减少系统中该频带的功率振荡。从时域角度来看，输出的直流调制附加功率应在母线频率上升时给予正调制，下降时停止调制或者给予负调制，从而达到提高电网同步发电机组功角稳定性的目的。

基于Prony分析的参数选取方法实现流程如下：（1）确定Prony分析时间长度。根据故障开始时间与切除时间确定母线频率的Prony采样时间长度。采样时间长度过长或过短都会造成信息的丢失，系统的极限切除时间一般为 $0 . 2 \sim 0 . 3 \mathrm { s }$ ，一般截取故障后 $0 . 6 \sim 1 \mathrm { s }$ 的信号进行采样。

(2）确定Prony分析的采样频率和阶次。系统 $N - 1$ 故障时，母线频率信号中最高频率范围在$2 0 \sim 2 5 \mathrm { H z }$ 之间，通常按照4倍信号最高频率进行采样，可取采样周期为0.01s；并使用软件自动定阶功能确定阶次。

(3）进行Prony 分析。

（4）根据分析结果确定调制器参数。由 $1 / ( 1 +$ $s T _ { \mathrm { f } } )$ 和 $K s / ( s + \varepsilon )$ 组合而成的带通滤波器的传递函数为

$$
D ( s ) = { \frac { K s } { ( 1 + s T _ { \mathrm { f } } ) ( s + \varepsilon ) } }
$$

其对数幅频特性为

$$
L ( \omega ) = 2 0 1 \mathrm { g } \omega + 2 0 1 \mathrm { g } K - 2 0 1 \mathrm { g } \sqrt { 1 + T _ { \mathrm { f } } ^ { 2 } \omega ^ { 2 } } - 2 0 1 \mathrm { g } \sqrt { \varepsilon ^ { 2 } + \omega ^ { 2 } }
$$

当 $\omega \ll \varepsilon$ 时

$$
L ( \omega ) = 2 0 1 \mathrm { g } \omega - 2 0 \mathrm { l g } { \frac { \varepsilon } { K } }
$$

当 ${ \omega } { \gg } 1 / T _ { \mathrm { f } }$ 时

$$
L ( \omega ) = - 2 0 1 \mathrm { g } \omega + 2 0 \log { \frac { \varepsilon } { T _ { \mathrm { f } } } }
$$

当 $\varepsilon { < } { < } \omega { < } { < } 1 / T _ { \mathrm { f } }$ 时

$$
L ( \omega ) = 2 0 \log K
$$

根据Prony分析的结果获得幅值最大频率 $f _ { \mathrm { l d } }$ 和次极大频率 $f _ { \mathrm { 2 d } }$ ，当满足 $[ f _ { 2 \mathrm { d } }$ ， $f _ { \mathrm { 1 d } } ] \subseteq [ \varepsilon / 2 \pi$ ， $1 / 2 \pi T _ { \mathrm { f } } ]$ 时，在其他频带上被尽量滤除。

# 4 仿真实验

# 4.1仿真背景

黑龙江电网地处东北网的最北部，其结构示意简图如图4所示。通过4回 $5 0 0 \mathrm { k V }$ 交流线路与吉林电网相连。扎青特高压直流投运后，东北电网外送能力得到了较大的提高。黑龙江电网的电力除了一部分汇集扎鲁特送华东地区外，还有一部分流向吉林和辽宁电网。在4回 $5 0 0 \mathrm { k V }$ 黑吉省间交流通道中，潮流较重的哈南－合心线若发生 $N - 1$ 故障，将导致原来流向吉林、辽宁的潮流沿哈南－华民方向汇入扎鲁特，虽甜水-扎鲁特、昌盛-扎鲁特线的潮流也会减少，但总体呈现扎鲁特涌入过剩功率、梨树－蒲河线潮流减少的情况。对于黑龙江电网本身来说，省间较重潮流断面发生故障期间，若稳控措施不当，就会引发黑龙江电网功角稳定性问题，造成较为严重的经济损失。现利用扎青特高压直流输电对于功率的灵活控制，适应故障特性，改善黑龙江电网的功角稳定性。

![](images/730d30b6a12bb062edd468cc6eff9220ebd6b4a28671c4fa8a304946c0e8d5e2.jpg)  
图4东北电网结构简图

# 4.2 仿真算例

设置黑吉省间 $5 0 0 \mathrm { k V }$ 交流通道哈南－合心5s时发生三相短路接地故障，0.2s后切除。利用直流功率调制改善黑龙江电网功角稳定性，并观察比较不同调制增益对于黑龙江电网功角稳定的影响。在仿真中，选取扎鲁特母线作为功率调制器的输入频率信号。在讨论增益变化对功角稳定性的影响前，首先根据Prony分析法对调制器参数进行设置；截取 $5 \sim 5 . 8 \mathrm { s }$ 时间段，即Prony分析时间长度 $T _ { \mathfrak { p } } =$ 0.8s，采样周期0.01s。所得结果见表1，频谱如图5所示。

![](images/533cd38f01e4d83b7aac1eb3c10e3a6bc18331db94896e9342f22291212c9f87.jpg)  
Fig.4Structure of China northeast power grid   
图5Prony分析频谱图  
Fig.5Spectrum plot of Prony

由以上分析结果，可得 $f _ { 1 \mathrm { d } } = 2 4 . 1 0 3 \ 1 3 \mathrm { H z }$ ， $f _ { \mathrm { 2 d } } =$ $2 1 . 7 9 8 ~ 8 5 \mathrm { H z }$ ，则可设置 $\varepsilon = 1 3 6 . 2 7 6$ ， $T _ { \mathrm { f } } = 0 . 0 0 6 \ 6$ 取 $T _ { \mathrm { d } } = 0 . 5$ ， $K = 4 \ 0 0 0$ 。分别观察故障近端新华发电机组与远端鹤岗发电机组在有无功率调制情况下的功角曲线，如图6、图7所示，可见调制后功角首

表1Prony分析结果  
Tab.1 Result of Prony analysis   

<html><body><table><tr><td>幅值</td><td>衰减</td><td>频率/Hz</td><td>阻尼比</td><td>实部</td><td>虚部</td></tr><tr><td>12.817 4</td><td>-28.040 6</td><td>24.103 13</td><td>0.736 148</td><td>-28.040 6</td><td>151.780 7</td></tr><tr><td>9.653 58</td><td>-27.324 2</td><td>21.798 85</td><td>0.487 019</td><td>-27.324 2</td><td>136.901 6</td></tr><tr><td>3.019 32</td><td>-22.902 7</td><td>18.586 1</td><td>0.192 453</td><td>-22.902 7</td><td>116.78</td></tr><tr><td>3.925 24</td><td>-22.036 3</td><td>29.272</td><td>0.155 553</td><td>-22.036 3</td><td>183.939</td></tr><tr><td>3.017 62</td><td>-22.350 7</td><td>11.384 8</td><td>0.298 234</td><td>-22.350 7</td><td>71.532 8</td></tr><tr><td>2.219 2</td><td>-20.156 1</td><td>4.257 52</td><td>0.601 776</td><td>-20.156 1</td><td>26.750 8</td></tr><tr><td>2.576 18</td><td>-21.698</td><td>14.564 6</td><td>0.230 709</td><td>-21.698</td><td>91.511 9</td></tr><tr><td>2.302</td><td>-20.539 2</td><td>20.781 5</td><td>0.136 176</td><td>-20.539 2</td><td>130.424</td></tr><tr><td>1.598 03</td><td>-18.000 2</td><td>16.552 3</td><td>0.170 541</td><td>-18.000 2</td><td>104.001</td></tr><tr><td>1.284 01</td><td>-17.437 7</td><td>20.592 6</td><td>0.133 564</td><td>-17.437 7</td><td>129.387</td></tr><tr><td>1.200 34</td><td>-11.889 4</td><td>5.820 65</td><td>0.309 167</td><td>-11.889 4</td><td>36.572 2</td></tr><tr><td>1.190 84</td><td>-14.756 7</td><td>12.891 7</td><td>0.179 229</td><td>-14.756 7</td><td>81.000 9</td></tr><tr><td>0.411 814</td><td>-12.900 2</td><td>9.288 73</td><td>0.215 826</td><td>-12.900 2</td><td>58.362 8</td></tr><tr><td>0.036 72</td><td>-4.349 09</td><td>2.721 55</td><td>0.246 486</td><td>-4.349 09</td><td>17.1</td></tr><tr><td>0.000 62</td><td>-5.402 94</td><td>4.246 59</td><td>0.035 442</td><td>-5.402 94</td><td>26.668 6</td></tr></table></body></html>

![](images/5ba482be753007e491343f4c2a6a03cc14777c70231c3f738399c2f4b739efb9.jpg)  
图6新华发电机组功角曲线  
图9黑龙江电网部分机组有调制功角曲线 Fig.9Rotor angle curve of some generators with DC power modulation in Heilongjiang power grid

![](images/1036fd0b4296d12bdad872361f2ed989d279c6e4822d8d10ffa330edd6866772.jpg)  
Fig.6Rotor angle curve of Xinhua generator   
图7鹤岗发电机组功角曲线  
Fig.7Rotor angle curve ofHegang generator

摆稳定性有了极大提高。

在黑吉省间 $5 0 0 \mathrm { k V }$ 交流通道设置三相短路接地故障，选取黑龙江电网每个地区部分机组观察其功角曲线，如图8所示，极限切除时间为0.23s。在相同故障时间下，利用直流功率调制，功角曲线如图9所示，调制后可以提高同步机组的极限切除时间。

![](images/110f5432989b81f20c7e0f7cdc8747103ba6d55300b07e0258efe02d2d2f95df.jpg)  
图8黑龙江电网部分机组无调制功角曲线  
Fig.8Rotor angle curve of some generators without DC power modulation in Heilongjiang power grid

240 200 ()/再 160 120 WWW 80 40 P 0 5 10 15 20 时间/s

# 4.3不同调制增益对功角稳定性的影响

由以上分析可知，利用Prony分析法对母线频率信号进行分析，确定滤波器时间常数 $T _ { \mathrm { f } }$ 和引导补偿因子 $\mathbf { \sigma } _ { \varepsilon }$ ，该直流调制有效地提高了黑龙江电网的功角稳定性。本节将在相同的故障背景下，以近端机组新华机组和远端机组鹤岗机组为例，设置5s故障，0.2s后切除，讨论调制增益 $K$ 对系统功角稳定性的影响。

由式（1）可知，当 $n$ 较大且采样时间段较小时，可用连续时间函数 $y ( t )$ 表示表1中任意频率的信号，即

$$
F ( t ) = A \mathrm { e } ^ { \mathrm { j } \theta } \mathrm { e } ^ { ( \alpha + \mathrm { j } \omega ) t }
$$

直流功率调制器传递函数为

$$
G ( s ) = \frac { K s ^ { 2 } } { ( 1 + s T _ { \mathrm { d } } ) ( 1 + s T _ { \mathrm { f } } ) ( s + \varepsilon ) }
$$

则

$$
P _ { \mathrm { M O D } } \left( s \right) = F ( s ) G ( s )
$$

在直流调制过程中，考虑直流系统的过负荷能力 $P _ { \mathrm { M O D } } \leqslant 0 . 1 P _ { \mathrm { d } }$ ，由对数幅频特性得

$$
2 0 1 \mathrm { g } \left| P _ { \mathrm { M O D } } ( \omega ) \right| \leqslant 2 0 \log \left| 0 . 1 P _ { \mathrm { d } } \right|
$$

将幅值最大频率 $f _ { \mathrm { 1 d } }$ 和次极大频率 $f _ { \mathrm { 2 d } }$ 对应幅值、衰减引子等数据分别代入上式，可得 $K \leqslant 5 \ 2 8 7$ 。不同调制增益 $K$ 对功角首摆稳定性的影响见表2，其中新华机组的功角曲线如图10所示。

# 表2采用不同增益时首摆减小幅度

Tab.2Reduction range of the first swing with different modulation parameter   

<html><body><table><tr><td>K值</td><td>100</td><td>500</td><td>1000</td><td>2000</td><td>4000</td><td>8000</td></tr><tr><td>新华机组/()</td><td>2.1</td><td>3.3</td><td>5.7</td><td>9.0</td><td>15.7</td><td>-8.2</td></tr><tr><td>鹤岗机组/()</td><td>2.9</td><td>4.5</td><td>7.1</td><td>10.2</td><td>18.5</td><td>-6.1</td></tr></table></body></html>

![](images/fe5879670c1a1ead89cdfba8e10ca3228258ceba33c1498ea9a3a40d99e63c0c.jpg)  
图10不同增益下新华机组功角曲线Fig.10Rotor angle curves of Xinhua generator withdifferent modulation parameter

表3讨论了不同调制增益对于机组极限切除时间的影响。

表3采用不同增益时的极限切除时间  
Tab.3Limit resection time with different modulation parameter   

<html><body><table><tr><td>K值</td><td>100</td><td>500</td><td>1000</td><td>2000</td><td>4000</td><td>8000</td></tr><tr><td>新华机组/s</td><td>0.23</td><td>0.23</td><td>0.23</td><td>0.24</td><td>0.26</td><td>0.21</td></tr><tr><td>鹤岗机组/s</td><td>0.23</td><td>0.23</td><td>0.24</td><td>0.24</td><td>0.27</td><td>0.22</td></tr></table></body></html>

由表3和新华机组在不同调制增益下的功角可以看出，不同调制增益对同步机组的功角稳定性影响不同。增益较小时，对系统稳定性改善不明显；当增益过大，则会出现超调现象，非但不能提高系统稳定性，还有可能加剧交流系统的失稳。根据故障远端和近端机组在不同调制增益下的功角首摆特性，可知远端机组调制后稳定性改善效果更好。

# 5 结论

本文分析了直流功率调制原理，研究了黑龙江电网发生省间交流系统三相短路接地故障时，扎青特高压直流功率调制对系统功角稳定性的影响，仿真验证了直流频率调制对与黑龙江电网的功角稳定性具有明显的改善作用。

基于Prony分析法对直流功率调制器的参数进行了设置，仿真结果验证了基于Prony分析设置调制器参数的有效性，对东北地区实际电网的稳定控制具有一定的指导意义。

根据直流过负荷能力限定了增益 $K$ 的范围，讨论了不同调制增益对于调制效果的影响，得出不同调制增益对系统的稳定性影响不同。增益较小时，对系统稳定性改善不明显；当增益过大，则会出现超调现象，非但不能提高系统稳定性，还有可能加剧交流系统的失稳。

# 参考文献

[1] 毛晓明，张尧，管霖．基于广域测量信息的直流 调制新方法[J]．电力系统自动化，2007，31(7)： 45-49. Mao Xiaoming,Zhang Yao,Guan Lin.A novel WAMS based HVDC modulation method[J]. Automation of Electric Power Systems,2007,31(7): 45-49.   
[2] 何剑，孙华东，郭剑波，等，直流功率调制抑制 交流联络线随机功率波动的研究[J]．中国电机工 程学报，2013，33(25)：93-98，15. He Jian, Sun Huadong, GuoJianbo,et al. Suppressing AC tie-line stochastic power fluctuation by HVDC power modulation control[J]. Proceedings of the CSEE,2013,33(25):93-98,15.   
[3] 杨卫东，薛禹胜．南方电网中直流输电系统对交流 系统的紧急功率支援[J]．电力系统自动化，2003， 27(17): 68-72. Yang Weidong,Xue Yusheng.Emergency DC power support to AC power system in the South China power grid[J].Automation of Electric Power Systems,2003,27(17): 68-72.   
[4] 徐政，高慧敏，杨靖萍．南方电网中直流紧急功 率调制的作用[J]．高电压技术，2004，30(11)： 24-26. Xu Zhen, Gao Huimin, Yang Jingping. Effect of HVDC emergent power modulation in South China power system[J]. High Voltage Engineering, 2004, 30(11): 24-26.   
[5] 张步涵，陈龙，李皇，等．利用直流功率调制增 强特高压交流互联系统稳定性[J]．高电压技术, 2010,36(1): 116-121. Zhang Buhan, Chen Long,Li Huang, et al. Improving the stability of UHV AC interconnected system by the DC power modulation[J]. High Voltage Engineering,2010,36(1): 116-121.   
[6] 黄震，郑超，庞晓艳，等．四川多回 $\pm 8 0 0 \mathrm { k V }$ 直 流外送系统直流有功功率协调控制[J]．电网技术, 2011,35(5): 52-58. Huang Zhen, Zheng Chao, Pang Xiaoyan, et al. Coordination control of DC active power for multicircuit $\pm 8 0 0 \mathrm { k V }$ DC power delivery system in Sichuan UHVAC/UHVDC hybrid power grid[J]. Power System Technology, 2011,35(5): 52-58.   
[7] 吕清洁，徐政，董桓锋，等．非并联运行交直流 系统直流调制原理及附加控制器设计[J]．电网技 术，2016，40(2): 548-555. Lv Qingjie, Xu Zheng, Dong Huanfeng, et al. HVDC modulation principle and supplementary controller design method of non parallel AC/DC system[J]. Power System Technology, 2016, 40(2): 548-555.   
[8] 朱浩骏，蔡泽祥，刘皓明，等．多馈入交直流输 电系统的模糊控制器协调优化算法[J]．中国电机 工程学报，2006，26(13)：7-13. Zhu Haojun, Cai Zexiang, Liu Haoming,et al. Coordinate optimization algorithm of fuzzy controller in multi-infeed AC/DC power systems[J]. Proceedings of the CSEE,2006,26(13): 7-13.   
[9] 谢惠藩，张尧，夏成军，等．交直流互联电网直流 功率调制相关问题[J]．电网技术，2009，33(4): 43-50. Xie Huifan, Zhang Yao, Xia Chengjun, et al. Issues related to DC power modulation in AC/DC hybrid system[J]. Power System Technology,2009, 33(4): 43-50.   
[10]王茂海，孙元章，宋永华．多馈入直流输电系 统LQR 调制控制器的设计[J]．电力系统自动化, 2006，30(23): 33-37. Wang Maohai, Sun Yuanzhang, Song Yonghua. Design of LQR DC-current modulation controller for multi-infeeded HVDC system[J]. Automation of Electric Power Systems,2006,30(23): 33-37.   
[11]常勇，徐政．考虑多机系统广域信号时滞影响的 直流附加控制器设计[J]．电工技术学报，2007, 22(5): 135-139. Chang Yong,Xu Zheng.Design of HVDC supplementary controller considering signal timedelay in multi-machine system[J]. Transaction of China Electrictechnical Society,2007, 22(5):135- 139.   
[12]卢岑岑，王晓茹．直流有功功率调制对四川电网 暂态稳定性的影响[J]．电网技术，2012，36(11): 140-146. Lu Cencen, Wang Xiaoru. Influences of DC active power modulation on transient stability of Sichuan power grid[J]. Power System Technology, 2012, 36(11): 140-146.   
[13]陈汉雄，刘天琪，刘群英．多馈入交直流混合系 统的智能模糊分散协调控制[J]．电网技术，2004, 28(5): 9-13. Chen Hanxiong, Liu Tianqi, Liu Qunying. Intelligent fuzzy control and decentralized coordinated control for multi-infeed AC/DC systems[J]. Power System Technology, 2004,28(5): 9-13.   
[14]Cresap R L,Scott D N,Mittelstadt W A,et al. Operating experience with modulation of the pacific HVDC inter-tie[J]. IEEE Trans.on Power Apparatus and Systems,1978,PAS-97(4): 1053-1059.   
[15]Grund D E,Bahrman M P, Balu N,et al.Dynamic performance characteristics of north American HVDC systems for transient and dynamic stability evaluations[J]. IEEE Trans. on Power Apparatus and Systems,1981, PAS-100(7): 3356-3363.   
[16]Padiyar K R. HVDC power transmission system: technology and system interactions[M]. Wiley: John Wiley & Sons,1990.   
[17]　李兴源，刘红超，邱晓燕，等．改善暂态稳定性 的 HVDC 非线性控制策略[J]．电力系统自动化,

2002，26(14)：16-19. Li Xingyuan, Liu Hongchao,Qiu Xiaoyan, et al. A nonlinear control strategy of HVDC for improving transient stability of power systems[J].Automation of Electric Power Systems,2002,26(14):16-19. [18] 吴华坚，王渝红，李兴源，等．基于综合性能指 标的交直流混合系统直流调制研究[J]．电力系统 保护与控制，2010，38(22)：68-73. Wu Huajian, Wang Yuhong,Li Xingyuan, et al. Study on DC modulation for AC/DC hybrid transmission system based on comprehensive performance

index[J].Power System Protection and Control,2010,38(22):68-73.  
[19] 王茂海，孙元章，宋永华．基于反步法的多馈入直流输电系统调制控制器设计[J]．中国电机工程学报，2005，25(23)：7-11.Wang Maohai,Sun Yuanzhang,Song Yonghua.Backstepping design of modulation controller formulti-infeed HVDC systems[J]. Proceedings of theCSEE,2005,25(23): 7-11.  
[20] 黄畅想．交直流输电系统一直流功率调制技术的研究[D]．南京：南京理工大学，2017.