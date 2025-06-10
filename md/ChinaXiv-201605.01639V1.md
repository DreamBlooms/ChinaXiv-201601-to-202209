# 本振相位噪声及其对GMSK解调性能的影响

周玉冰，屈晨阳(1.中国科学院大学,北京100190；2.中国科学院空间科学与应用研究中心，北京100190）

摘要：GMSK调制方式在空间通信中的应用越来越受重视，本振相位噪声对GMSK解调具有不可忽略的影响。在分析相位噪声产生原理的基础上，推导了其时域和频域表达式，并对其进行了仿真验证。通过在GMSK的Simulink调制解调系统中加入相位噪声，仿真分析了不同程度的相位噪声对解调性能的影响。研究方法和结论可以推广到存在相位噪声的任意调制类型的解调系统，对解调系统的优化具有重要参考价值。

关键词：相位噪声；分形布朗运动；GMSK；解调；Simulink中图分类号：TN911.4 文献标识码：A 文章编号：1000-8829(2015)02-0062-04

# Analysis of Local Oscillator Phase Noise and Its Effect On the Demodulation Performance of GMSK

ZHOU Yu-bing'²,QU Chen-yang² (1.University of Chinese Academy of Sciences,Beijing 1OO190,China; 2.Center for Space Science and Applied Research,CAS,Beijing 1O0190,China)

Abstract: GMSK modulation playsan important role in space telecommunications.Local oscillator phase noise has significant influence on GMSK demodulation system.Some characteristics of phase noise and its math expresions on both time and frequency domains are analyzed.Furthermore,the simulated phase noise sequence isaddedto the GMSKmodulationsystem to show how thedifferent levels of phase noise affectthe demodulation performance.The conclusions have deep reference value to optimize the GMSK demodulation system.This method to analyze phase noise and its effect can be extended to any modulation system.

Key words: phase noise; fractional Brownian motion; GMSK; demodulation; Simulink

在通信系统中，一个理想的本振输出信号频谱是一根单谱线；而实际的本振不可避免地存在随机相位抖动（即相位噪声），通信系统的误码率将恶化。提高本振的频谱纯度可以改善通信系统的误码性能。而当误码率达到一定数量级时，过分追求高性能的本振并不能显著提高系统误码性能，反而会使本振的造价变得非常昂贵甚至不可实现[1]。因此,分析通信系统中本振相位噪声对误码性能的影响，有助于给工程设计提供有效参考，以便兼顾系统的可实现性和高性能。

GMSK调制方式具有恒包络的特性，适用于饱和功放，且带宽效率高，因此GMSK调制方式已经被CCSDS建议为深空通信高速数传的首选调制方式。ESA和JAXA合作研发的计划在2014年发射的水星探测器贝皮-哥伦布（bepicolombo)已经采用GMSK调制体制，这是在深空应答机上首次使用GMSK调制方式，同时国内对空间通信中的GMSK的研究也越来越多[2]

笔者将分析相位噪声的原理，在此基础上推导其时域和频域表达式，并进行仿真分析。通过搭建GM-SK调制解调系统的Simulink模型，分析不同程度的相位噪声对解调系统的影响。

# 1相位噪声原理分析

一个理想的本振输出信号可以表示为

$$
V ( t ) = V _ { 0 } \sin ( 2 \pi f _ { 0 } t )
$$

其中 $V _ { 0 } \sqrt { \phantom { 0 } } _ { 0 }$ 均为常数。这是一个纯净的本振信号，从频域看本振信号为一根纯净谱线，从时域看正弦波的周期为一恒定值。但实际中任何信号不可避免地被噪声调制。

实际本振可表示为

$$
V ( t ) = \left[ V _ { 0 } + \varepsilon ( t ) \right] \sin [ 2 \pi f _ { 0 } t + \varphi ( t ) ] + V _ { 1 } ( t )
$$

${ \pmb \varphi } ( t )$ 为各种原因造成的附加瞬时相位起伏，通常情况下 $\varepsilon ( t ) < < V _ { 0 } , V _ { 1 } ( t ) < < V _ { 0 }$ ,即在接近 $f _ { 0 }$ 的偏移频率上，式(2)可以简化为

$$
V ( t ) = V _ { 0 } \sin [ 2 \pi f _ { 0 } t + \varphi ( t ) ]
$$

本振输出的瞬时频率可以记为

$$
v ( t ) = f _ { 0 } + \frac { 1 } { 2 \pi } \frac { \mathrm { d } \varphi ( t ) } { \mathrm { d } t }
$$

相对瞬时频率抖动可定义为

$$
\gamma ( t ) \equiv \frac { v ( t ) - f _ { 0 } } { f _ { 0 } } = \frac { 1 } { 2 \pi f _ { 0 } } \frac { \mathrm { d } \varphi ( t ) } { \mathrm { d } t }
$$

相对瞬时相位抖动可定义为

$$
{ \boldsymbol { x } } ( t ) = \frac { \varphi ( t ) } { 2 \pi f _ { 0 } }
$$

由晶振自身引起的随机相位抖动就是相位噪声。

$\boldsymbol { y } ( t )$ 包含了频率稳定度的全部信息，参考文献[3] $\sim$ 文献[5]认为， $y ( t )$ 的功率谱密度 $S _ { y } \left( f \right)$ 可以由幂律谱噪声模型表示。

传统的幂律模型如下所示：

$$
S _ { y } ( f ) \ = \ \sum h _ { b } f ^ { b }
$$

式中， $h _ { \delta }$ 为噪声指数是 $b$ 的强度系数。 $\textbf { \textit { b } }$ 取值从（-2,-1,0,1,2)变化[3]。虽然在传统的幂律模型中,只考虑了 $\pmb { b }$ 取整数值的情况，但是在广泛的实验验证中， $\textbf { \textit { b } }$ 为非整数值的噪声源也不容忽视[4]。

由于 ${ \pmb x } ( t )$ 是 $\boldsymbol { y } ( t )$ 的积分，所以 ${ \pmb x } ( t )$ 的功率谱密度与 $s _ { y } ( f )$ 的关系为

$$
S _ { x } ( f ) = \frac { S _ { y } ( f ) } { \left( 2 \pi f \right) ^ { 2 } }
$$

为了简化公式，重新定义变量 $\pmb { \alpha }$ ，可以得到

$$
S _ { \ * } \left( f \right) = \frac { h _ { b } } { \left( 2 \pi \right) ^ { 2 } } f ^ { b - 2 } \propto 1 / f ^ { \alpha }
$$

本振相位噪声具有 $1 / f ^ { \alpha }$ 形式，通常考虑其范围为 $0 <$ $\alpha < 2 ,$ □

由于这些幂律型噪声基本不满足平稳遍历条件，它们的标准方差是不收敛的，因而其频率稳定度的时域表征需要通过Allan方差、修正Allan方差]、Hadamard方差[8]等来表征[9]。

# 2相位噪声序列生成

# 2.1 分形布朗运动模型

基于多年以来相关学者的大量研究，常用的产生$1 / f ^ { \alpha }$ 噪声的连续建模方法被分为三大类[5]：ARMA模型，分形积分，小波分析。本文的离散模型是基于分形积分的方法。

分形之父Mandelbrot观察到1/f“噪声和布朗运动的功率谱密度存在一定的相似性。布朗运动的功率谱密度是正比于1/f的，Mandelbrot将布朗运动的概念进行推广，将1/f“噪声看做一种分形布朗运动（FBM,fractional Brownian motion）[5,10]

布朗运动 $B ( \mathbf { \chi } _ { t } )$ 是零均值的随机过程，且满足以下3个性质：

$$
\textcircled{1} B ( 0 ) = 0 ;
$$

$\textcircled { 2 } B ( t ) - B ( s )$ 是平稳的，且均值为0,方差正比于 $\left( t - s \right) , s \leqslant t ;$

$\textcircled { 3 } B ( t _ { 2 } ) - B ( t _ { 1 } ) , B ( t _ { 3 } ) - B ( t _ { 2 } ) , \cdots , B ( t _ { n } ) \ -$ $B \big ( t _ { n - 1 } \big )$ 是独立的， $\mathbf { \nabla } _ { t _ { 1 } \leqslant t _ { 2 } \leqslant \cdots t _ { n } }$ 。

分形布朗运动 $B _ { f } ( t )$ 可由此定义为满足以下3个性质的零均值随机过程：

$$
\textcircled { \mathbb { 1 } } B _ { f } ( 0 ) = \mathbf { 0 } ;
$$

$\textcircled { 2 } B _ { f } ( t ) - B _ { f } ( s )$ 是平稳的,且均值为0,方差正比于 $( t - s ) ^ { \alpha - 1 } , s \leqslant t ;$

$\textcircled { 3 } B _ { f } ( t _ { 2 } ) - B _ { f } ( t _ { 1 } ) , B _ { f } ( t _ { 3 } ) - B _ { f } ( t _ { 2 } ) , \cdots , B _ { f } ( t _ { n } ) -$ $B _ { f } ( t _ { n - 1 } )$ 是独立的， $t _ { 1 } \leqslant t _ { 2 } \leqslant \cdots t _ { n }$ ·

从大量的实验和观察证明出 $1 / f ^ { \alpha }$ 噪声是自然界的基本性质，是普遍存在的，Mandelbrot将1/f噪声归类为一种随机分形，因此，还加了第4条性质：

$\textcircled{4} B _ { f } ( t )$ 是自相似的(或者说标度不变)，其标度不变是针对功率谱密度来说的，假如频率的标度变了，原先的幅度标度可以由直接乘以一个常数来得到。

# 2.2相位噪声模型推导

# 2.2.1白噪声与布朗运动

由文献[5]可知，布朗运动 $B ( t )$ 是白噪声 ${ \pmb w } ( t )$ 的积分，其表达式为

$$
B ( t ) \ = \int _ { 0 } ^ { t } w ( t ) \mathrm { d } t
$$

对式(10)进行Laplace变换得到

$$
H ( s ) = \frac { 1 } { s }
$$

其对应的离散差分方程为

$$
B _ { k } = B _ { k - 1 } + w _ { k }
$$

对式（12）做 $\pmb { z }$ 变换，得到传递函数

$$
H ( z ) = { \frac { 1 } { 1 - z ^ { - 1 } } }
$$

# 2.2.2相位噪声与白噪声

布朗运动对应到式(9)中即是 $\alpha = 2$ 的情况。正如白噪声是布朗运动的微分，相位噪声 ${ \pmb x } ( t )$ 可由以下分数阶微分来定义[5]

$$
{ \frac { \mathrm { d } ^ { \alpha } } { \mathrm { d } t ^ { \alpha } } } x ( t ) = w ( t )
$$

其中 $\pmb { \alpha }$ 是实数，范围为 $0 < \alpha < 2$ 。由黎曼-刘维尔分形积分公式可以得到式(14)的解为

$$
x ( t ) \ = { \frac { 1 } { { \cal T } ( \alpha / 2 ) } } \int _ { 0 } ^ { t } ( t - \tau ) ^ { \alpha / 2 - 1 } w ( \tau ) \mathrm { d } \tau
$$

这等效于一个由白噪声激励的线性系统，其冲激响应为

$$
h ( t ) = \frac { t ^ { \alpha / 2 - 1 } } { T ( \alpha / 2 ) }
$$

经过Laplace变换和归一化，得到

$$
H _ { f } ( s ) = \frac { 1 } { s ^ { \alpha / 2 } }
$$

由冲激不变法，可得到离散模型传递函数为

$$
H _ { f } ( z ) = { \frac { 1 } { ( 1 - z ^ { - 1 } ) ^ { \alpha / 2 } } } , ( z > 1 )
$$

离散的相位噪声序列 $\pmb { x } _ { k }$ ，可以由高斯白噪声序列$\pmb { w } _ { k }$ 通过传递函数为 $H _ { f } ( z )$ 的线性系统来表示，其 $\pmb { z }$ 域及时域表达式为

$$
\pmb { X } ( z ) = \pmb { H } _ { f } ( z ) \pmb { \operatorname { \mathbb { W } } } ( z )
$$

$$
x _ { k } \ = \ \sum _ { l = 0 } ^ { k - 1 } h _ { l } w _ { k - l }
$$

由文献[5]得到式(19)对应的功率谱密度为

$$
S _ { d } ( f ) = \Delta t Q _ { d } H _ { f } ( z ) H _ { f } ( z ^ { - 1 } )
$$

其中， $Q _ { d }$ 是输入的高斯白噪声序列 $\boldsymbol { w } _ { k }$ 的方差，乘以 $\Delta t$ 是为了使连续系统和离散系统的标度一致。

将式(18)和 $z = e ^ { \mathrm { i } 2 \pi f \Delta t }$ 代人式(21),得到功率谱密度为

$$
S _ { d } ( f ) = \frac { Q _ { d } \Delta t } { ( 2 \sin ( \pi f \Delta t ) ) ^ { \alpha } }
$$

对于 $f$ 远小于奈奎斯特频率的情况，可近似为

$$
S _ { d } ( f ) \cong \frac { Q _ { d } \Delta t ^ { 1 - \alpha } } { ( 2 \pi f ) ^ { \alpha } }
$$

把式(18)按级数展开，有

$$
H _ { f } ( z ) = 1 + { \frac { \alpha } { 2 } } z ^ { - 1 } + { \frac { \alpha / 2 ( \alpha / 2 + 1 ) } { 2 ! } } z ^ { - 2 } + \cdots
$$

式(24)中，各项系数可以由如下递归算法得到：

$$
h _ { 0 } = 1 \ : , h _ { k } = ( \frac { \alpha } { 2 } + k - 1 ) \frac { h _ { k - 1 } } { k }
$$

由此，采用式（25）可计算出冲击响应，代人式(20)可以直接产生相位噪声序列。

# 3相位噪声仿真分析

1/f形式的相位噪声，取 $\pmb { \alpha } = 1$ ,在Simulink中搭建相应模型，由高斯白噪声通过FIR滤波器，生成1/f噪声，其中滤波器的系数由式(25)得到，并且除以一个常数，使得由滤波器引入的功率增益为1，以便控制高斯噪声的 $Q _ { d }$ 就能直接控制相位噪声的Allan方差。生成的噪声序列如图1所示，长度为10000。

求出该序列的功率谱密度，与式(23)的理论值进行比较，如图2所示。

可以看到功率谱密度仿真值和理论值接近，斜率都为1，符合1/f特性。

然而在实际的系统中，相位噪声的频谱并非在全频率范围内都是一个固定的值，其频率特性通常是近似分段线性的，以国家军用标准为例，其参数如表1所

示，其频谱被分为4段。

![](images/5c77bd88192cabf0cee06e65d57ee8f8c34ea2671e17110b589c405c6e7f9317.jpg)  
图1 $\alpha = 1$ 时的噪声序列 $x _ { k }$

![](images/fe2d645140616f6e8b7f419f27d21daee27b68760cf88b5cc00718a83c0a765a.jpg)  
图2功率谱密度 $S _ { d } ( f )$   
图3用Simulink产生分段线性的相位噪声图3中的频谱仪可以显示用该方法产生的相位噪声的频谱图。如图4所示。

表1国家军用标准相噪参数  
根据表1对相位噪声模型进行修改，如图3所示。  

<html><body><table><tr><td>偏移载频频率/kHz</td><td>L(f)/dBc·Hz-1</td><td>频谱分段斜率</td></tr><tr><td>0.1</td><td>-55</td><td>1.5</td></tr><tr><td>1</td><td>-70</td><td>0.7</td></tr><tr><td>10</td><td>-77</td><td>0.5</td></tr><tr><td>100</td><td>-82</td><td>1.8</td></tr><tr><td>1000</td><td>-100</td><td></td></tr></table></body></html>

FDATool   
WA hkf1(z) Gaussian 1 prrry   
Gaussian Noise DiscreteFIRFilter Digital Generator FilterDesign Add FDATool   
w hkf2（z) Gaussian 1 T mmmm   
Gaussian Noise Discete FIRFilter1 Digital Generator1 FilterDesign1 phasenoise   
wA hkf3(z) FDATool To Workspace Gaussian 1 T   
Gaussian Noise Discrete FIRFilter2 Digital ll Generator2 Filter Design2 B-FFT FDATool   
W hkf4（z) Spectrum Gaussian 1 Scope5 中   
Gaussian Noise Discrete FIRFilter3 Digital Generator3 FilterDesign3

![](images/8dd65db8af07deddc1111fe07d5aacbc3479c6fe98bcb4f6f09194e6ca26c0ce.jpg)  
图4相位噪声谱

将图4和表1进行对比，可看出仿真结果和理论值接近，验证了该方法的可行性。

# 4相位噪声对GMSK解调性能的影响

对于空间通信系统，要求解调器具有最小的解调损失，并且能够提取载波，以此来测量积分多普勒从而用于导航[11]。因此,空间通信中GMSK调制系统需要采用相干解调方案。

在相干解调的Simulink仿真中，高斯信道模块噪声模式Eb/N0取0\~11，步进值为1,误码率统计模块可输出在各个Eb/NO取值所对应的误码率结果变量。图3生成的相位噪声加在发端NCO上。

GMSK系统主要参数设置如表2所示。

表2GMSK系统主要参数  

<html><body><table><tr><td>码速率/Mbit·s-1</td><td>中心频率/MHz</td><td>采样率/MHz</td></tr><tr><td>1</td><td>5</td><td>100</td></tr></table></body></html>

取6组不同的数据进行实验，如表3所示。分别仿真无相位噪声、相噪小于国军标（实验一、实验二）、相噪恰好满足国军标（实验三）、相噪大于国军标（实验四、实验五）的情况下对GMSK误码性能的影响。其中均方根抖动与功率谱密度 $L ( f )$ 的关系可参考文献[12]。

表3Simulink仿真相噪参数设置  

<html><body><table><tr><td rowspan="2">偏移载频频率/Hz</td><td colspan="5">L(f)/dBc·Hz-1</td><td rowspan="2">均方根抖 动/（°）</td></tr><tr><td>100</td><td>1k</td><td>10k</td><td>100k</td><td>1M</td></tr><tr><td>无相噪</td><td></td><td></td><td></td><td>NULL</td><td></td><td>0</td></tr><tr><td></td><td>实验一</td><td>-61</td><td>-76</td><td>-83</td><td>-88 -106</td><td>1.94</td></tr><tr><td>有</td><td>实验二</td><td>-58</td><td>-73</td><td>-80 -85</td><td>-103</td><td>2. 75</td></tr><tr><td></td><td>相实验三(国军标)</td><td>-55</td><td>-70</td><td>-77 -82</td><td>-100</td><td>3.88</td></tr><tr><td>噪</td><td>实验四</td><td>-52</td><td>-67</td><td>-74 -79</td><td>-97</td><td>5.48</td></tr><tr><td></td><td>实验五</td><td>-49</td><td>-64</td><td>-71</td><td>-76 -94</td><td>7.73</td></tr></table></body></html>

各实验误码率统计结果如图5所示。

由图5可以看出，当码速率为1Mbit/s时，相位噪声对解调性能有较大影响，可得出如下明显结论：

![](images/c323d570510b402b12f963be820d1aece1cb4bd005bffc62e9f382a4eefec602.jpg)  
图5误码率统计

$\textcircled{1}$ 即便相噪功率谱密度满足国军标，时域的均方 根抖动也达到了 $3 . 8 8 ^ { \circ }$ ,误码率在 $1 0 ^ { - 4 }$ 处的解调损耗 已经大于1dB。

$\textcircled{2}$ 实验一、实验二的解调损耗都小于1dB,结合表3可以看出，实验一、实验二分别对应于相噪功率谱密度比国军标小6dB和 $3 \mathrm { \ d B }$ 。因此，在工程应用上，应尽量将偏离载频1MHz以内的相位噪声控制在至少比国军标低3dB的范围以下，以保证解调损耗小于1 dB。

$\textcircled{3}$ 从实验四、实验五可以看出，随着相位噪声的继续增大，BER曲线严重恶化，提高Eb/NO值对于系统误码率的改善也很小，误码率出现了不归零的趋势。

# 5结束语

在分析了相位噪声的基础上，对相位噪声序列进行仿真，并在Simulink平台仿真不同程度的相位噪声对GMSK解调性能的影响，可以得出如下结论：如果要使相位噪声对解调系统的影响很小，需保持相噪功率谱密度比国军标低3dB的范围以下。

用本文的分析和仿真方法，对相位噪声对解调损耗的影响做前期的定量仿真分析，可以为系统设计环节中相位噪声的指标分配提供一定的参考依据。该方法不仅适用于GMSK调制解调系统，而且可以推广到存在相位噪声的任意调制类型的解调，具有普遍意义。

# 参考文献：

[1]张爱兵,黄普明,张辉.本振相位噪声引起QPSK信号信噪比降低的分析与仿真[J].空间电子技术，2004（1）：37-41.  
[2] SesslerGMA,AbelloR,JamesN,etal.GMSK demodulatorimplementation for ESA deep-space missions[C]//Proceed-ings of theIEEE,2007,95(11):2132-2141.  
[3]焦月,寇艳红.GPS卫星钟差分析、建模及仿真[J].中国科学：物理学力学天文学,2011,41(5)：596-601.

（下转第72页）

![](images/c3efeae0047d9b183b6d90f1d195fc32d2eb513f295d68b474a4935b3d8c5c37.jpg)  
图3人机交互模块程序流程图

# 3 系统测试分析及改进

本系统基于上文原理完成实物并进行多次测试。测试场景选择在放置了一台柜式格力空调的普通房间内，在GSM信号接收正常及红外发射头正对空调红外接收区的情况下，分别发送温度从 $1 6 \sim 3 0 ~ \mathfrak { C }$ 的制冷及制热模式开启空调的指令，指令完成率为 $100 \%$ 且设备距空调可达数米；但在红外发射头与空调接收区呈现一定的角度或其之间有小部分的障碍物时，指令完成率有所下降。

对多次测试后的结果分析，仅有单个红外发射头及较差的网络环境使指令完成率不能达到用户的期望要求，故将红外发射模块及TC35的天线部分进行了改进。在红外发射模块方面，根据每个发射头所能覆

# （上接第65页）

[4] Walter T. Characterizing frequency stability:a continuous power-law model with discrete sampling[J]. IEEE Transactions on Instrumentation and Measurement,1994,43(1）:69 -79.   
[5] Kasdin N J.Discrete simulation of colored noise and stochastic processes and 1/f"power law noise generation[C]//Proceedings of the IEEE,1995,83(5):802-827.   
[6] Allan D W,Weiss MA,Jespersen JL.A frequency-domain view of time-domain characterization of clocks and time and frequency distribution systems[C]//Proceedings of the $4 5 ^ { \mathrm { t b } }$ （204号 Annual Symposium on Frequercy Control.1991:667 -678.   
[7] Allan D W,Barnes JA.A modified allan variance with increased oscillator characterization ability[C]//Proceedings of 35th Annual Frequency Control Symposium.1981:470 -475.

盖到的有效角度范围进行建模，在设备的重要面上加装了5个红外发射头，同时小幅度改进了驱动电路，使红外信号可覆盖整个房间且辐射功率小幅上升；在网络信号方面，改进了设备样式，将天线加强后伸出设备，使网络信号大幅优化。系统改进后，设备的放置位置更加灵活，设备与空调的有效距离有所提升，出现网络错误的概率减小。最后在放置挂式或柜式空调的房间内均进行测试，指令完成率接近 $100 \%$ 。

# 4结束语

智能远程家居控制系统的设计使在任何有GSM网络的地方都能对家居设备进行监控，加快了家庭信息化、自动化的进程。利用上文的思路可以继续添加厨房火警、煤气浓度检测、防盗等模块，同时本系统也可以向工厂、学校等地方扩展，有很高的可扩展性，同时突破了传统的有线控制，具有成本低、智能化高的特点，有很高的市场利用价值。

# 参考文献：

[1］余健.基于TC35I的移动通信终端的研究与实现[D].武汉：武汉理工大学，2012.  
[2] ProsiseJeff,张炜.调制解调器语言：AT指令集[EB/OL].[1995].[2012-04-12].http://wuxizazhi.cnki.net/Ar-ticle/GRDN199502038.html.  
[3] 廉小亲，陈建涛，张晓力，等.基于MSP430的远程空调控制系统控制终端的设计[J].测控技术，2013，32(2).  
[4] 朱高中.基于单片机的红外遥控解码电路的设计[J].计算技术与自动化，2011，30(2)：68-71.  
[5] 张友德，赵志英，涂时亮.单片微型机原理、应用与实验[M].5版.上海：复旦大学出版社，2008.  
[6] 郭天祥.新概念51单片机C语言教程[M].北京：电子工业出版社，2009.  
[8]Howe D A,Beard R L.Crearhal C A,et al.Enhancements toGPS operations and clock evaluations using a“total”had-amard deviation[J].IEEE Transactions on Ultrasonics,Fer-roelectrics and Frequency Control,2005,52（8）:1253-1261.  
[9] 唐素，彭毅，张有正.广义阿仑方差及修正阿仑方差[J].电子学报，1987,15(1)：90-97.  
[10] Kasdin N J,Walter T.Discrete simulation of power lawnoise[C]//Proceedings of the 1992 IEEE Frequency Con-trol Symposium.1992.  
[11] SimonMK.高宽带效率数字调制及其在深空通信中的应用[M].夏云，孙威，译.北京：清华大学出版社，2006.  
[12] Robins W P.Phase Noise in Signal Source[M].London:PeterPeregrinus,1982.