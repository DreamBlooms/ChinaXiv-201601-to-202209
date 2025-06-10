# 比值校正法在射电频谱中的应用

张燕坤"²，董亮，李明悦，何乐生，汪敏²(1中国科学院大学天文与空间科学学院，北京 100049)(中国科学院云南天文台，云南 昆明 650216)(云南大学信息学院，云南 昆明 650504)

摘要：分子谱线可以在射电频谱上显现，但是采用离散数字功率谱分析算法会引入离散误差，难以获得分子谱线准确的频谱信息。针对射电频谱上离散数字功率谱分析中带来的频率偏移问题进行比值校正法研究和处理。该方法是频谱矫正方法的一种，特点在于算法简单，方便快捷。利用射频信号相同、分辨率不同和不同射频信号、不同分辨率情况下，归一化频率偏移量的变化确定该方法的校正效果，最终实现了射频为80.0MHz,141.8MHz和270.8MHz的频谱校正，提高了相应的频谱分辨率可达7.5Hz/channel。通过实验结果对比，确定了测试系统的最佳频率分辨率为50Hz/Channel或200Hz/channel。

关键词：离散频谱分析；比值校正法；谱线；频谱分辨率中图分类号： 文献标识码：A 文章编号：1672-7673(2020)03

谱线在研究天体的物理或化学环境、演化历程以及天体分类等方面具有重大作用，是天文学研究的一个工具。与各种辐射机制预言的功率谱相似，谱线研究涉及一个频率、多个频率或者连续谱，可以是吸收线，也可以是发射线。它们来自于不同层级的天体，比如恒星、星云、星系、本星系群或者整个宇宙。通过多波段观测可以对这些天体形成一个系统的认识。在众多的谱线中，H21厘米谱线是验证大爆炸理论，揭示宇宙早期再电离阶段的重要探针"²；光谱学中的各类线系、复合线可以用来研究天体的温度、速度等物理量；尘埃辐射和分子谱线是研究恒星形成、星际介质的重要工具或手段。

各类谱线具有不同的波长，其中很多在射电波段内（ $0 . 3 \mathrm { m m } { \sim } 2 0 \mathrm { m }$ ），可以通过射电望远镜或天线阵列对它们进行探测。为了尽可能探测到较多的谱线，除了需要好的射电天文观测环境外，还要望远镜的灵敏度和分辨率足够好。因此，低噪声放大器、宽带接收机、大口径天线、多波束或焦面阵（大视场）等关键设备的研发成为国际和国内的重大课题。同样，多通道数字终端、高速数据处理和存储设备研发，甚至观测技术或方案等也很重要。

除了空间分辨率以及时间分辨率的要求，分子天体物理和谱线观测对终端设备的频率分辨率也提出了很高的要求[2。在星际介质和恒星形成研究工作中，天体的运动速度或速度梯度场是很重要的物理量。它在天体测量学、星系动力学中定义的本地静止标准中表现为红移或蓝移，即多普勒运动。这个速度会使探测到谱线频率相对于地球上实验室测得的频率有一定漂移，此时终端较高的频率分辨率会使这样的漂移被精确测定，从而提高速度测量的可信度。另外，展宽也就可以定得比较准确。如图1，从H(96)β的离散谱形能够得到天体的速度、温度等物理信息，表明频谱分辨率越高，相关研究越能反映真实的天体物理信息。

![](images/5fbed8c7d472535562fb186edd2d52bdad1a99ae6115eeac4795dc5fd91e8bbb.jpg)  
图1天马65 米望远镜观测到的H(96)β频谱。图像上沿坐标轴显示的是经过多普勒修正后的频率，以MHz 为单位；纵轴表示天线温度，以K为单位。Fig.1The H(96)βspectrumobservedbyTianma65meterstelescope.TheupperhorizontalaxisshowsthefrequencyinunitofMHz after Doppler correction.The vertical axis represents the antenna temperature in unit of K.

实际上，观测设备和观测方法会在频谱上造成一定的频率漂移和速度展宽，从而引入系统误差，因此还需要频谱校正。尽管该技术在工程领域得到广泛应用，但是天文领域的应用仍然欠缺。在频谱分析时，一般采用拟合方法检验通道稳定性和通道间隔一致性，很少用到频谱校正的方法，也没有校正偏移量。这对于频率分辨率要求不高‘ $( \delta { \approx } 1 0 ^ { 1 } { \sim } 1 0 ^ { 2 } \mathrm { { H z } }$ ）的谱线观测是合适的，但是，随着天文观测要求的提高，接收机、终端精度和稳定性也相应提高，此时简单的拟合不再适应，频谱校正就显得尤为重要。

频谱校正是信号处理领域重要的研究课题。由于计算机只能对有限多个样本和采样点数进行计算，因此，需要对时域信号进行截断和数字离散化，这不可避免地造成了能量泄漏和栅栏效应，使得离散频谱的幅值、相位和频率产生较大的误差[3-4]。在对单频率谐波信号加窗处理后，幅值误差最高可达 $3 6 . 4 \%$ ，相位误差可达 $\boldsymbol { \pm } 9 0 ^ { \circ }$ ，频率误差可达 $\pm _ { 0 . 5 }$ 个频率分辨率[5]。

目前，国内外对离散频谱校正的方法有很多，其中比值校正法较为常用。根据原时域信号组成结构的不同,主要分为两类:一类频谱校正方法主要针对单频信号,另一类针对密集频谱。由于射电天文的谱线信号主要是单频信号，即使是能级分裂所造成的各点频信号间隔也较大，因此，本文只讨论单频信号的频谱校正。对于单频信号，国内外有5种对功率谱校正的方法：比值校正法、能量重心校正法、 $\mathrm { F F I + F T }$ 连续细化分析傅里叶变换法、相位差法、相位差法 $^ { \cdot + }$ 单点FT 法。本文的实验模拟了射电天文观测软硬件系统，并采用算法简单、运算速度快、精度较高的比值校正法[7]，对经过LabView 程序、捷变收发器的噪声源信号进行频率定标。

# 1比值校正法

在谱线研究中，频率、流量和偏振是比较重要的观测量。由于频率稳定性和测量偏差在积分观测中会间接影响流量乃至偏振的测量与定标，因此,仅介绍比值校正法在频率定标方面的应用。

利用频率归一化后差值为1的主瓣峰顶附近两条谱线的窗谱函数比值，建立一个以归一化校正频率为变量的方程，解出归一化校正频率，进而进行频率、幅值和相位校正的方法称为比值校正法。解出归一化校正频率的方法有多种，直接导出公式的方法称为比值公式法，利用迭代求解的方法称为比值迭代公式法，用搜索求解的方法称为比值峰搜索法。

假设归一化窗函数的频谱模函数表达式为 $W _ { 1 } ( f ^ { \mathrm { d } } )$ ，由于主瓣内幅值为正，此时频谱模函数与归一化窗谱函数完全相等， $W _ { 1 } ( f ^ { \mathrm { d } } )$ 对称与y轴，即主瓣中心是坐标原点。

如果周期信号的频率恰好对正某一发射（吸收）谱线频率，那么计算得到的频率、幅值和相位都是准确的。更一般的情况是，信号频率没落在通道中心位置，因此，峰值谱反映的频率和幅值都不准确，相位误差也较大。主瓣中心并不在坐标原点，而是有一定偏移 $\nabla f ^ { \mathrm { 1 } }$ （-0.5≤Vf≤0.5)。

在射电天文的高精度实测中，需要精确测量得到谱线的频谱信息，因而频谱的偏移要尽可能消除。

设fy表示谱线发射频率， $f _ { \mathrm r }$ 表示频谱仪接收的频率，则在设备良好的情况下，地面测试实验得到的结果应是 $f _ { \mathrm { y } } { = } f _ { \mathrm { r } }$ 。但是，随着模数转换技术的发展和离散数字信号的应用，连续的频谱被离散化。由于谱线发射频率 $f _ { \mathrm { y } }$ 处在特定通道 $K$ （幅值谱谱线号）内，但不一定处在该通道的中心位置 $f _ { 0 }$ 处，因此 $f _ { \mathrm { y } } { \neq } f _ { 0 }$ 。加上时域信号被截断的影响， $f _ { \mathrm { y } }$ 与 $f _ { 0 }$ 之间的偏差较大。经过频谱校正，可以在较高精度（Hz级）下，可以使得 $f _ { 0 _ { - } c } { = } f _ { \mathrm { y } } { = } f _ { \mathrm { r } }$ 。

实际频谱中，假设采样点数为 $2 N$ ，采样频率为 $2 f _ { \mathrm { s } }$ ，那么通道数为 $N$ ，采样带宽为 $f _ { \mathrm { s } }$ ，且$K ^ { \in } [ 1 , N / 2 \AA - 1 ] ^ { [ 9 ] }$ 。若通道 $K$ 的幅值为 $Y _ { k }$ ，其两侧 $K \mathrm { - } 1$ 、 $\textstyle K + 1$ 通道的幅值分别为 $Y _ { k - 1 }$ 、 $Y _ { k + 1 }$ 。那么 $K$ 通道所对应的频率为

$$
f _ { 0 } = K \frac { f _ { s } } { N }
$$

当 $Y _ { k - 1 } > Y _ { k + 1 }$ 时，如图2，有

$$
\upsilon = - \frac { Y _ { K - 1 } } { Y _ { K } } ( \upsilon \in [ - 0 . 5 , 0 ] )
$$

当 $Y _ { k - 1 } < Y _ { k + 1 }$ 时，如图3，有

$$
\upsilon = \frac { Y _ { _ K } } { Y _ { _ { K + 1 } } } ( \upsilon \in [ 0 , 0 . 5 ] )
$$

对于矩形窗而言，其频率校正量为

$$
\begin{array} { r } { \left\{ \begin{array} { l l } { \displaystyle Y _ { K + 1 } \geq Y _ { K - 1 } \forall \mathrm { f } , \nabla f ^ { 1 } = \frac { 1 } { 1 + \upsilon } } \\ { \displaystyle Y _ { K - 1 } > Y _ { K + 1 } \| \mathrm { f } \forall \mathrm { f } ^ { 1 } = - \frac { 1 } { 1 + \frac { 1 } { \upsilon } } } \end{array} \right. } \end{array}
$$

校正得到的校正频率[10]为

$$
f _ { 0 _ { - } c } \mathbf { = } \ ( \mathbf { K } \mathbf { + } \nabla f ^ { 1 } ) \ \frac { f _ { s } } { N }
$$

如图4，以上校正算法适用于起始频率为 $0 \mathrm { H z }$ 的离散频谱，但实际应用中，该起始频率一般不为 $0 \mathrm { H z }$ ，因此，还需要针对特定领域进一步计算。在射电频谱中，真实的频率为

$$
f _ { \mathrm { r } } { = } f _ { \mathrm { L O } } { + } f _ { 0 \_ c }
$$

其中， $f _ { \mathrm { L O } }$ 表示本地振荡器的频率。若有多级本振，还应把各级本振频率求和，才能得到fLo。

![](images/92f0ce05a151916d7e822d3f1a1c42ae44afc5c9730a021ed54f5772e3a842e3.jpg)  
Fig.2Schematic diagram of discrete signal corresponding to $Y _ { k - 1 } > Y _ { k + 1 }$

![](images/7840b06561980ce1d9c197f69564165ab48b16fcbc9770a56dbe69b96a60f689.jpg)  
图2 $Y _ { k - 1 } > Y _ { k + 1 }$ 时对应的离散信号示意图  
图3 $Y _ { k - 1 } < Y _ { k + 1 }$ 时对应的离散信号示意图

![](images/34b1a466742579da25dbdee48fd0791308d0cfdcb05a0306922b1b564f6ae9e0.jpg)  
Fig.3Schematic diagram of discrete signal corresponding to $Y _ { k - 1 } < Y _ { k + 1 }$   
图4考虑本地振荡频率后的校正示意图  
Fig.4Calibration schematic diagram after considering the local oscillation frequency

# 2实验设置

射电天文观测中，天文谱线信号在L波段及其以上频率（>1GHz)，因此需要降频，以降低数字后端采样的压力。观测源的信号经过天线、接收机后，其频率被调制到几十到几千兆赫兹，随后将这样的中频信号送至终端进行采样和校准。

为了模拟出这样的一个中频信号，采用标准信号源并设置输出频率为$f _ { 0 } { = } 1 4 1 { , } 8 0 0 { , } 0 0 0 . 0 0 \mathrm { { H z } }$ 。同时，使用捷变收发器 NI2901作为模数转换和数据采样设备，并编写LabView 程序设置终端参数和控制运行过程。另外，通过程序中的功率谱计算，在输入带宽内划分出成 $N$ 个数字通道，从而将一定的信号带宽细化，这样就能提高频率分辨率，满足对频谱分辨率的不同需求。

实验设置了不同的频率分辨率，以观察比值校正法在不同天文需求下的表现。虽然分辨率越高对天文观测越有利，但是需要与当前技术发展水平相适应，因此参数配置要合理，具体情况见表1。从表1中载波输入和实际载波部分可以看出，设定的参数与设备响应间有一定的差值，这给数据分析带来不便。同时，为了使实验具有一定的统计意义，对每组设置分别测试 5次。

表1不同频率分辨率下的参数设置Table 1 Parameter Settings at different frequency resolutions  

<html><body><table><tr><td>Freq. Resol. a (Hz/channel)</td><td>IQ rate</td><td>Sig.BWb (Hz)</td><td>Act.BW (Hz)</td><td>Finputd (Hz)</td><td>Factuale (MHz)</td><td>Samp ling points</td><td>Cumulative frequency</td></tr><tr><td>7.5</td><td>100.00K</td><td>122.00K</td><td>122.00K</td><td>141769500</td><td>141. 769</td><td>16384</td><td>1000</td></tr><tr><td>15</td><td>100.00K</td><td>122.00K</td><td>122.00K</td><td>141769500</td><td>141. 769</td><td>8192</td><td>1000</td></tr><tr><td>20</td><td>100.00K</td><td>81.92K</td><td>81.92K</td><td>141769500</td><td>141. 770</td><td>4096</td><td>1000</td></tr><tr><td>30</td><td>100.00K</td><td>122.00K</td><td>122.00K</td><td>141769500</td><td>141. 770</td><td>4096</td><td>1000</td></tr><tr><td>50</td><td>100.00K</td><td>122.00K</td><td>122.00K</td><td>141769500</td><td>141. 770</td><td>2440</td><td>1000</td></tr><tr><td>100</td><td>100.00K</td><td>122.00K</td><td>122.00K</td><td>141769500</td><td>141. 770</td><td>1220</td><td>1000</td></tr><tr><td>200</td><td>100.00K</td><td>122.00K</td><td>122.00K</td><td>141769500</td><td>141. 770</td><td>610</td><td>20000</td></tr><tr><td>500</td><td>100.00K</td><td>122.00K</td><td>122.00K</td><td>141769500</td><td>141. 770</td><td>244</td><td>20000</td></tr><tr><td>1000</td><td>100.00K</td><td>122.00K</td><td>122.00K</td><td>141769500</td><td>141.770</td><td>122</td><td>20000</td></tr></table></body></html>

^ Frequency resolution; b Signal band-width; Actual band-width; d Input carrer frequency;  Actual carrier frequency.

对于特定观测波段，由于观测源和探测的分子不同，其输出的中频信号也不同。考虑到40米射电望远镜分子谱线终端的中频输入带宽是1GHz（升级改造后为 2GHz)，谱线信号则可能出现在带通的几十或几百MHz的位置，因此还设置了80.0MHz和270.8MHz的实验组，以研究比值校正法在不同输出信号、不同频率分辨率下的表现。与表1参数不同的是，当射频信号为80MHz时，载波输入为79.9795MHz，实际载波为79.9795MHz；当射频信号为270.8MHz时，载波输入为270.7695MHz，实际载波为270.77MHz。

# 3结果分析

通过多次测试和数据分析，发现和解决了理论和技术上的缺陷，并有了一些结果。认真分析这些结果，有助于进一步研究频谱校正理论,并把相关的方法应用到实际观测中。本文针对不同目的设置了不同的实验组，下面分别叙述。

首先，归一化频率偏移量 $\nabla f ^ { \mathrm { 1 } }$ 在射频信号相同，频率分辨率不同的情况下表现有一定规律。在表2和图5中，0\~4分别表示5次测试的序号。从图中可以看出，当频率分辨率太高时，各次测试的值不尽相同，而在较低频率分辨率时各次测试一致性较好，这说明系统在较高频谱分辨率要求下不够稳定,并且 $\nabla f ^ { \mathrm { l } }$ 大于0的散点较多，即多数情况是 $Y _ { k - 1 } < Y _ { k + 1 }$ ，这与表3和图6相吻合。另外，图5和图6还表明：不论分辨率的高低，归一化频率偏移量总在[-0.5,0.5]之间。因此，比值校正法在较高频率分辨率下的校正效果更好。对于本实验所用的设备，实际观测时的频率分辨率可在50Hz/channel，100Hz/channel或 200Hz/channel 间选择。

其次，频率分辨率相同，但是射频信号不同，则归一化频率偏移量 $\nabla f ^ { \mathsf { I } }$ 也不同。从表4和图7可以看出，射频信号分别为80MHz，141.8MHz和270MHz时，归一化频率偏移量有较大差别，并且频率分辨率较高和较低时有很大不同。从图中可以看出：当频率分辨率为50Hz/channel或200Hz/channel时，3个信号的归一化频率偏移量 $\nabla f ^ { \mathrm { l } } \in [ - 0 . 2$ ，0.2]。结合图5、图6，可知此时系统最稳定。

以上结果是可以理解的：由于比值校正法只使用了3个临近点，因此,对频率分辨率显示出很高的依赖性。如果在高频率分辨率情况下观测，再分析出归一化频率偏移量，那么比值校正法是最好、最快的校正方法。

# 表2射频为141.8MHz，频率分辨率不同时的多次测试数据

Table 2 Results with radio frequency of 141.8MHz and different frequency resolution   

<html><body><table><tr><td>exnerimofts</td><td>Frz/chanel)</td><td>Vf</td><td>eInerex ofts</td><td>Frzqchrnnel)</td><td>VF</td></tr><tr><td rowspan="8">0</td><td>1000.0000000000</td><td>0.3423212243</td><td></td><td>1000.0000000000</td><td>0.0651720930</td></tr><tr><td>100.0000000000</td><td>0.0142455346</td><td></td><td>100.0000000000</td><td>0.0144940334</td></tr><tr><td>7.4462890625</td><td>-0.0416315433</td><td></td><td>7. 4462890625</td><td>0.0244703661</td></tr><tr><td>500.0000000000</td><td>0.3508046810</td><td></td><td>500.0000000000</td><td>0. 3487047748</td></tr><tr><td>50.0000000000</td><td>0.0387933055</td><td>3</td><td>50.0000000000</td><td>0.0570070349</td></tr><tr><td>29.7851562500</td><td>0.2493147110</td><td></td><td>29.7851562500</td><td>0.3044267795</td></tr><tr><td>200.0000000000</td><td>0.0047153864</td><td></td><td>200.0000000000</td><td>0.0046528023</td></tr><tr><td>14.8925781250</td><td>0.3275106419</td><td></td><td>14. 8925781250</td><td>0. 4384830843</td></tr><tr><td></td><td>20.0000000000</td><td>-0.0530305312</td><td></td><td>20.0000000000</td><td>-0. 0706707358</td></tr><tr><td rowspan="8">1</td><td>1000.0000000000</td><td>0.0655970348</td><td></td><td>1000.0000000000</td><td>0.0651342265</td></tr><tr><td>100.0000000000</td><td>0.0155808114</td><td></td><td>100.0000000000</td><td>0.0185485020</td></tr><tr><td>7.4462890625</td><td>0.0041361850</td><td></td><td>7.4462890625</td><td>0.3064197324</td></tr><tr><td>500.0000000000</td><td>0.3494843586</td><td></td><td>500.0000000000</td><td>0. 3423212243</td></tr><tr><td>50.0000000000</td><td>0.0533924633</td><td>4</td><td>50.0000000000</td><td>0.0598957511</td></tr><tr><td>29.7851562500</td><td>0.2645479331</td><td></td><td>29.7851562500</td><td>0. 4164752968</td></tr><tr><td>200.0000000000</td><td>0.0047438926</td><td></td><td>200.0000000000</td><td>0.0045723524</td></tr><tr><td>14. 8925781250</td><td>0.2875929373</td><td></td><td>14. 8925781250</td><td>-0. 4572477817</td></tr><tr><td rowspan="10">2</td><td>20.0000000000</td><td>-0.0492047472</td><td></td><td>20.0000000000</td><td>-0.0470696696</td></tr><tr><td>1000.0000000000</td><td>0.0653673598</td><td></td><td></td><td></td></tr><tr><td>100.0000000000</td><td>0.0149879265</td><td></td><td></td><td></td></tr><tr><td>7.4462890625</td><td>0. 1447826447</td><td></td><td></td><td></td></tr><tr><td>500.0000000000</td><td>0.3478842095</td><td></td><td></td><td></td></tr><tr><td>50.0000000000</td><td>0.0541893805</td><td></td><td></td><td></td></tr><tr><td>29.7851562500</td><td>-0.4956424680</td><td></td><td></td><td></td></tr><tr><td>200.0000000000</td><td>0.0047095546</td><td></td><td></td><td></td></tr><tr><td>14.8925781250</td><td>0.3512400507</td><td></td><td></td><td></td></tr><tr><td>20.0000000000</td><td>-0.0473347745</td><td></td><td></td><td></td></tr></table></body></html>

表3射频为141.8MHz，频率分辨率不同时f的均值与标准差 able 3 The mean and standard deviation data withradio frequency of 141.8MHz anc different frequency resolution   

<html><body><table><tr><td>Frz/channel)</td><td>Mean of Vf</td><td>Std. of Vf</td></tr><tr><td>100.0000000000</td><td>0.0155713616</td><td>0.0015570680</td></tr><tr><td>7.4462890625</td><td>0.0876354770</td><td>0.1255422437</td></tr><tr><td>1000.0000000000</td><td>0.1207183877</td><td>0.1108015405</td></tr><tr><td>200.0000000000</td><td>0.0046787977</td><td>0.0000608743</td></tr><tr><td>14.8925781250</td><td>0.1895157865</td><td>0.3271404205</td></tr><tr><td>50.0000000000</td><td>0.0526555871</td><td>0. 0072994991</td></tr><tr><td>500.0000000000</td><td>0.3478398496</td><td>0.0029223252</td></tr><tr><td>20.0000000000</td><td>-0.0534620917</td><td>0.0088640367</td></tr><tr><td>29.7851562500</td><td>0.1478244505</td><td>0.3270082220</td></tr></table></body></html>

![](images/e57efc9eaf58983657f64b540e3af21fbbd6a7ca9b144a1e56c001c5705334b3.jpg)  
图5射频为141. ${ 8 } \mathrm { M H z }$ ，频率分辨率不同时的多次测试结果  
Fig.5Multiple test results with radiofrequency of $1 4 1 . 8 M H z$ and different frequency resolution

![](images/1cffe5d97058f95f68af03c8d490d1f1a22acd9d1b24f312c67af83f16075b5b.jpg)  
图6射频为141.8MHz，频率分辨率不同时的分析结果  
Fig.6Analysis results of radio frequency about $1 4 1 . 8 M H z$ with different frequency resolutions

# 表4f在不同射频，不同频率分辨率情况下的值

Table 4 The value ofVfwith different radio frequency and frequency resoluti

<html><body><table><tr><td>(RFz)</td><td>Frzqchanel)</td><td>VF</td><td>(RHz)</td><td>Frz/channel)</td><td>Vf</td></tr><tr><td rowspan="8">80.0</td><td>1000.0000000000</td><td>0.2054970208</td><td></td><td>1000.0000000000</td><td>0.3423212243</td></tr><tr><td>100.0000000000</td><td>0.2095411283</td><td></td><td>100.0000000000</td><td>0.0142455346</td></tr><tr><td>7.4462890625</td><td>0.3715679928</td><td></td><td>7.4462890625</td><td>-0.0416315433</td></tr><tr><td>500.0000000000</td><td>-0.1878904187</td><td></td><td>500.0000000000</td><td>0.3508046810</td></tr><tr><td>50.0000000000</td><td>-0.1722237239</td><td>141.8</td><td>50.0000000000</td><td>0.0387933055</td></tr><tr><td>29.7851562500</td><td>-0.1263683613</td><td></td><td>29.7851562500</td><td>0.2493147110</td></tr><tr><td>200.0000000000</td><td>-0.1672976339</td><td></td><td>200.0000000000</td><td>0.0047153864</td></tr><tr><td>14.8925781250</td><td>-0.1497675356</td><td></td><td>14.8925781250</td><td>0.3275106419</td></tr><tr><td rowspan="8"></td><td>20.0000000000</td><td>-0.0128196597</td><td></td><td>20.0000000000</td><td>-0.0530305312</td></tr><tr><td>1000.0000000000</td><td>-0.0020558727</td><td></td><td></td><td></td></tr><tr><td>100.0000000000</td><td>0.4999769741</td><td></td><td></td><td></td></tr><tr><td>7.4462890625</td><td>0.4074170232</td><td></td><td></td><td></td></tr><tr><td>500.0000000000</td><td>-0.0098171494</td><td></td><td></td><td></td></tr><tr><td>50.0000000000</td><td>0.0112350002</td><td></td><td></td><td></td></tr><tr><td>29.7851562500</td><td>-0.3560928468</td><td></td><td></td><td></td></tr><tr><td>200.0000000000</td><td>-0.0933705315</td><td></td><td></td><td></td></tr><tr><td>14.8925781250 20.0000000000</td><td></td><td>-0.0408522077 0.0727707923</td><td></td><td></td></tr></table></body></html>

![](images/d0795e33eb8a3d0221ff6a50750d1f5e94d430d4d6fc47248d45494d02711db2.jpg)  
图7不同射频信号，不同频率分辨率下的归一化频率偏移量  
Fig.7Normalized frequency offsets at different radio signals and differentfrequency resolutions

# 4总结与展望

比值校正法简单、实用，这给射电天文频谱分析带来了很大的便利。本文基于测试频点已知的情况，虽然与实际观测有一定差距，但是对于未来观测数据质量的提供是一件具有开拓性的工作。当系统误差和外界干扰都能够很好地避免时，天体的动力学或运动学条件、温度和密度等研究工作才有可信度。具体的意义有3点：（1）检验信号源或者本振的频率稳定性，长期监测可以得出它的变化规律；（2）频率切换观测中，需要不断改变本振频率，因此,需要监测本振的频率稳定性和准确性；（3）实际天文观测中，一般不需要对频率稳定性定期检测，但是该工作对确定仪器误差、检测仪器性能以及对更深入的频率定标和监测都有参考价值。

在未来，天线观测谱线信号的频谱前，本文解决了频谱校正的问题，同时也指明了实测时的分辨率设置（50Hz/channel或200Hz/channel）给动态校正频谱的工作提供了参考。另外，天体的多普勒也给频谱带来了频率漂移，这将是下一步研究的内容，可以和选择观测源和谱线等工作一起进行。

致谢衷心感谢杨志坚教授在编程和测试过程中给予理论指导并提供无私帮助

# 参考文献：

[1］ROHLFSK，WILSONTL．射电天文工具[M]．姜碧为，译．北京：北京师范大学出版社，2008：11.  
[2]曾琴,毛瑞青,裴春传.天体物理中的微波谱线诊断[M].北京:中国科学技术出版社,2006:12.  
[3]段虎明,秦树人,李宁．离散频谱的校正方法综述［J]．振动与冲击，2007,26(11)：138-145，189.  
[4]丁康,朱小勇．频谱校正理论的研究与发展[C]//1999年中国神经网络与信号处理学术会议论文集.1999:528-532.[5］朱小勇，丁康．离散频谱校正方法的综合比较[J]．信号处理，2001,17(1)：91-97.[6]丁康,谢明,杨志坚.离散频谱分析校正理论与技术[M].北京:科学出版社,2008.  
[7］宋连珺．射电天文信号密集频谱校正方法研究[D]．昆明：云南大学，2017.  
[8]丁康,谢明,王志杰．离散频谱的幅值_相位和频率的校正方法及误差分析[J]．动态分析与测试技术，1996，14（1）：10-29.[9]谢明,丁康．频谱分析的校正方法［J]．振动工程学报，1994，7（2）：172-179.[10]谢明,丁康．离散频谱分析的一种新校正方法[J]．重庆大学学报(自然科学版)，1995，18(2)：47-54.

# The Application of Ratio Correction in Radio Spectrum

Yankun Zhang1²， Liang Dong²， Mingyue Li³， Lesheng He³， Min Wang²   
(University of Chinese Academic of Sciences,School of astronomy and space science,Beijingloo049,China) (²Chinese Academy of Sciences,Yunnan Astronomical Observatory,Kunming 650216,China) (Yunnan University,School of Information,Kunming 650504,China)

Abstract:Molecular spectral lines can be viewed on the radio spectrum, but discrete digital power spectrum analysis algorithmswould introduce errors that make it difficult to obtain accurate information about spectral lines. In this paper,we studied the ratio correction method and carried it out to solve the problem of frequency offset in discrete digital power spectrum analysis.This method is a kind of spectrum correction method, which is characterized by simple,convenient and fast algorithm.The correction effect of this method is determined by the change of the normalized frequency offset under the condition of the same radio signal,different spectral resolution and different radio signal, different spectral resolution.We finally complete the correction in tests of setting the radio frequency to be $8 0 . 0 \mathrm { M H z }$ ， $1 4 1 . 8 \mathrm { M H z }$ and $2 7 0 . 8 \mathrm { M H z }$ ,and improve the frequency resolution to $7 . 5 ~ \mathrm { H z } /$ channel. By comparing the experimental results,the optimal frequency resolution of the sampling system is determined to be $5 0 . 0 \mathrm { H z } /$ channel and $2 0 0 . 0 \mathrm { H z }$ /channel.

Key words:Discrete digital power spectrum analysis;Ratio correction method;Spectral lines;spectral resolution