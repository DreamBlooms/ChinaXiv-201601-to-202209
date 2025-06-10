# 基于双DKDP晶体原理的太阳大气实时偏振探测技术研究

胡平1,2.3，顾乃庭1,²，饶长辉1,2

（1.中国科学院光电技术研究所，四川成都610209；2.中国科学院自适应光学重点实验室，四川成都 610209；3.中国科学院大学，北京100049）

摘要：磁场是太阳爆发活动的根本驱动力，高精度实时偏振测量是实现磁场测量的常用方法。然而常用的波片式测量方法需要进行多次测量，且存在机械旋转结构，易导致仪器抖动，降低测量精度；波片旋转或切入切出也会导致测量时间较长。目前，基于DKDP 晶体和波片的太阳大气偏振测量周期较长，实时性不高，无法应用于快速变化的太阳活动磁场探测。基于以上背景，本论文提出了一种基于双DKDP 晶体原理的太阳大气实时偏振探测技术，采用两片快轴方向不同的DKDP 晶体，通过外加不同电压进行快速相位延迟变化，实现对入射太阳光的偏振调制，获取太阳大气偏振斯托克斯矢量。相较于传统旋转波片与DKDP 晶体相结合的方法，本论文提出方法可将单次偏振调制速率从数秒提升到毫秒级，极大地提升了太阳磁场测量实时性。仿真分析结果表明：本文提出方法测量精度达到 $2 \times 1 0 ^ { - 3 }$ 单波长点测量时间分辨率提升了20倍以上，可以实现对太阳磁场偏振信息的实时精确测量。

关键词：太阳磁场；偏振测量；DKDP；实时测量

# 中图分类号：P161.3 文献标识码：A

太阳大气的局部区域中存在有各种不同的活动现象，包括太阳黑子，日冕物质抛射，耀斑爆发等。这些太阳活动作用于日地空间环境，对地球气候、人体健康、电子电力设备、无线电通讯以及航空飞行器飞行都有重大影响[]。通过对太阳活动的研究来实现对这些灾难性的空间天气的有效预报，是当今太阳物理学研究的一项重要课题。太阳磁场是太阳活动的根本驱动力，而对太阳磁场的测量通常是采用对特定磁敏感谱线的偏振测量来实现。太阳谱线在磁场中会发生分裂，其裂距和支线偏振态与磁场强度和方向呈现一定的函数关系，通过精确测量太阳光的偏振状态，建立偏振辐射转移方程，反演太阳大气中的磁场形态，可以研究太阳黑子、耀斑及日冕物质抛射等活动现象，对日地空间环境研究、灾害性空间天气监测和预报以及太阳物理的研究具有重要的意义[2]。

国内外对太阳磁场的观测主要通过在太阳望远镜上安装偏振测量仪器对太阳光谱偏振信息进行测量实现。而地基太阳望远镜的观测会受到大气湍流的影响，当望远镜放大倍率较大时，成像光斑模糊抖动，大大影响观测分辨力，并且白天大气湍流也更强。当偏振测量的时间分辨率较高时，可在一定程度上达到冻结大气湍流的效果，降低大气湍流对测量精度的影响。除此之外，太阳磁场也始终处于快速变化中。为了能够精确测量太阳光的偏振态，反演得到太阳大气的磁场，偏振测量仪器的时间分辨率就成了一个重要指标。

目前，国内太阳望远镜上使用的偏振分析器主要采用的是带有经典波片的调制系统。这种传统的偏振调制器也被许多国外的太阳偏振分析器所使用，如德国GREGOR 望远镜上所装载的理想光谱偏振仪（POLIS)，其波片的旋转频率为 $1 5 \mathrm { { H z } }$ 。美国大熊湖GST 望远镜上的可见光偏振成像仪（VIM）和第二代近红外光谱偏振仪（NIRIS）都采用了旋转波片调制方式。NIRIS 的波片调制器连续旋转，其旋转与红外相机的帧率相结合，以 $2 2 . 5 ^ { \circ }$ 步长旋转一周获得16 帧图像，目前其相机能够以10帧/秒的速度完成低噪声采集；所以，NIRIS 光谱-偏振测量的频率通常为10s；其中VIM的时间分辨率为10s 左右[3.4]。国内的 NVST 望远镜一组8步式调制需要4s左右完成，每个调制位置上耗费的总时间为波片旋转到位所需要的时间与数据采集时间之和，而波片旋转所消耗的时间占了很大一部分[5.6]。在此基础上，怀柔太阳观测站的SMFT采用了波片 $+$ DKDP晶体的调制方式，这种方式可以利用正负电压翻转控制DKDP晶体的延迟，快速采集两个参数的图像，减少了波片旋转的次数，缩短了调制时间[7]。但是，旋转部件的使用会导致仪器抖动，从而降低测量精度，增加系统的质量和体积；而如果波片采用切入切出的方式，其调制时间将大大增加，一次切换时间一般大于5秒。这些缺点对于星载仪器更为严重，并且有机械故障的风险。相对而言，波片+DKDP晶体的调制方式缩短了一些测量时间，但由于波片结构的存在，没有能够充分地利用DKDP晶体快速调制的优点，仍然需要大量调制时间，实时性并不好。DKDP 晶体和液晶材料LCVR都是通过改变偏振相位的方式实现对入射光的偏振调制，二者在材料、性能等方面存在较大区别。相比较而言，LCVR调制频率 $1 0 0 \mathrm { H z }$ 左右，对温度敏感，光谱范围窄，稳定性相对较差，在实际应用中尚未成熟。DKDP材料调制频率较高，可达 $1 0 0 0 \mathrm { H z }$ 以上，重复性好,且在多套系统中成功应用，技术成熟可靠。

基于以上背景，本文提出了基于双DKDP 晶体的实时偏振测量方案。该方法采用了两片DKDP晶体作为偏振调制器件,通过外加电压的方式来控制DKDP晶体的相位延迟变化，而 DKDP 晶体的电压-相位延迟响应速度可以达到毫秒级[8]。这种调制方法没有任何的机械运动，没有移动部件，可以提供毫秒级的快速切换时间，再加上曝光时间短，时间分辨率可达到传统波片 ${ \bf \Lambda } + { \bf D } { \bf K } { \bf D } { \bf P }$ 调制方式的10倍以上，使得冻结大气湍流成为可能。为了进一步验证该方案的可行性，本文在方法原理、参数优化、仿真分析和测量时间等方面进行了分析与验证。

# 1原理和方法

光的偏振信息可以用电矢量、琼斯矢量和斯托克斯矢量表示。其中电矢量和琼斯矢量只能对完全偏振光进行表示，斯托克斯（Stokes）矢量用四个光强参量可以实现对任意偏振态的光进行表示，因而本文选用斯托克斯矢量来表示被测光的偏振态。斯托克斯矢量S的具体表达式如下：

$$
\begin{array} { r l } & { \mathrm { S } = [ \mathrm { I } , \mathrm { Q } , \mathrm { U } , \mathrm { V } ] ^ { T } } \\ & { \mathrm { I } = < { E _ { x } } { E _ { x } } ^ { \ast } + { E _ { y } } { E _ { y } } ^ { \ast } \geq { E _ { x } } ^ { 2 } + { E _ { y } } ^ { 2 } } \\ & { \mathrm { Q } = < { E _ { x } } { E _ { x } } ^ { \ast } - { E _ { y } } { E _ { y } } ^ { \ast } \geq { E _ { x } } ^ { 2 } - { E _ { y } } ^ { 2 } \# ( 1 ) } \\ & { \mathrm { U } = < { E _ { x } } { E _ { y } } ^ { \ast } + { E _ { y } } { E _ { x } } ^ { \ast } > = 2 { E _ { x } } { E _ { y } } c o s \delta } \end{array}
$$

$$
\mathrm { V } = - \mathrm { i } < E _ { x } { E _ { y } } ^ { * } + E _ { y } { E _ { x } } ^ { * } > = 2 E _ { x } E _ { y } s i n \delta
$$

其中\*表示复共轭， $\delta = \varphi _ { y } - \varphi _ { x }$ ，表示 $\boldsymbol { \mathrm { \Sigma } } _ { X }$ 与 $\mathrm { \Delta Y }$ 分量的相位差；I表示光波的总光强，Q表示将光分解到X，Y方向后，X与 $\mathrm { \Delta Y }$ 分量光强的差值，U表示将光分解到 $4 5 ^ { \circ }$ 和 $1 3 5 ^ { \circ }$ 方向后， $4 5 ^ { \circ }$ 和 $1 3 5 ^ { \circ }$ 分量光强的差值， $\mathsf { Q }$ ，U都表示光波的线偏振特性， $\mathrm { \Delta V }$ 表示将光分解为右旋和左旋分量后，右旋与左旋分量光强的产值， $\mathrm { \Delta V }$ 代表了光波的圆偏光特性。

# 1.1传统波片与DKDP晶体的调制方法

传统的偏振测量方案采用了λ/4波片与DKDP晶体作为偏振调制器件，并且一次完整的斯托克斯矢量测量需要进行6次调制得到6组光强值。此方案中DKDP晶体快轴角度为 $4 5 ^ { \circ }$ ，偏振片透光轴角度为 $0 ^ { \circ }$ 。

![](images/0bdb9e5b6f2057df7cb5cd2ee66526c226626f726b7a1a22fcf3caa4e2f03277.jpg)  
图1传统λ/4波片 $+ \mathrm { D K D P }$ 偏振分析器示意图  
Figure 1 Schematic diagram of traditional $\lambda / 4$ wave plate $^ +$ DKDP polarization analyzer

在测量纵向磁场时，四分之一波片在光路之外，在DKDP 晶体上加矩形正负高压，使得相位延迟在 $\pm \lambda / 4$ 之间调制，左右圆偏振光交替通过分析器，Stokes 矢量V信号可以从右旋圆偏振光与左旋圆偏振光的差中得到。测量横向磁场时，将四分之一波片放在光路中，将其光轴方向角调为 $0 ^ { \circ }$ ，然后再DKDP晶体外加矩形正负高压，则偏振方位角分别为 $0 ^ { \circ }$ 和$9 0 ^ { \circ }$ 的线偏振光交替通过检偏器，它们的差值即 Stokes 矢量U信号。调整四分之一波片的光轴方位角为 $4 5 ^ { \circ }$ ，在DKDP晶体外加矩形正负高压，偏振方位角分别为 $4 5 ^ { \circ }$ 和 $1 3 5 ^ { \circ }$ 的线偏振光交替通过，相减后得到Q信号。偏振分析器的调制参数如下表。

表 $\textbf { 1 } \lambda / 4$ 波片 $\mathbf { + D K D P }$ 偏振调制参数  
Table1 λ/4wave plate $\mathbf { + D K D P }$ polarization modulation parameters   

<html><body><table><tr><td>λ/4wave plate</td><td>DKDP crystal</td><td>Polarizer</td><td>Measurement result</td></tr><tr><td>45°</td><td>-90°</td><td>0°</td><td>1 =1+Q</td></tr><tr><td>45°</td><td>90°</td><td>0°</td><td>l2 =1-Q</td></tr><tr><td>0°</td><td>-90</td><td>0°</td><td>l=1+U</td></tr><tr><td>0°</td><td>90°</td><td>0°</td><td>I4 =I-U</td></tr><tr><td></td><td>90°</td><td>0°</td><td>I5=I+V</td></tr><tr><td>---</td><td>-90°</td><td>0°</td><td>I6=I-V</td></tr></table></body></html>

在此方案中，四分之一波片的切换时间为秒量级，且在测量一个波长点时需要采集6帧光强图像，切换3次四分之一波片。在太阳磁场测量中，相比单波长点测量来说，多波长点测量可以避免受到饱和效应造成的非线性、Doppler 位移以及Faraday 效应等的影响。多波长点测量一般选取谱线轮廓上的6个波长点，此时，一次完整的谱线测量至少需要采集36 帧光强图像，切换18次四分之一波片，导致测量时间过长，时间分辨率过低，实时性较差。

# 1.2基于双DKDP晶体的调制方法

当光的偏振态用斯托克斯矢量S表示时，传输介质对光偏振态的作用可以用穆勒矩阵M表示。光束依次经过 $\left. 1 ^ { \ldots } \right| _ { \mathrm { } }$ 个传输介质后，斯托克斯矢量为：

$$
S ^ { \prime } = M _ { n } M _ { n - 1 } \cdots M _ { 2 } M _ { 1 } S \# ( 2 )
$$

偏振测量的原理如下图：

![](images/ab89df29668aeea59c74f8f908f4ec981e054e4aeb9dfbf7180d87816017364e.jpg)  
图2偏振测量原理图  
Figure 2 Polarization measurement principle diagram

偏振测量仪通常由偏振调制器和光强探测器构成。对于斯托克斯矢量S（未知）的待测偏振光，经过调制状态a后，其斯托克斯矢量为 $\boldsymbol { S _ { a } } = [ \mathrm { I } _ { a } , \mathrm { Q } _ { a } , \mathrm { U } _ { a } , \mathrm { V } _ { a } ] ^ { T }$ ,此时调制状态a对应的穆勒矩阵为 $M _ { a }$ 。

$$
M _ { a } = \left[ \begin{array} { l l l l } { a _ { 1 1 } } & { a _ { 1 2 } } & { a _ { 1 3 } } & { a _ { 1 4 } } \\ { a _ { 2 1 } } & { a _ { 2 2 } } & { a _ { 2 3 } } & { a _ { 2 4 } } \\ { a _ { 3 1 } } & { a _ { 3 2 } } & { a _ { 3 3 } } & { a _ { 3 4 } } \\ { a _ { 4 1 } } & { a _ { 4 2 } } & { a _ { 4 3 } } & { a _ { 4 4 } } \end{array} \right] \# ( 3 )
$$

$$
S _ { a } = M _ { a } S
$$

光强探测器只能探测到光强信息，即I的值。满足：

$$
I _ { a } = a _ { 1 1 } I + a _ { 1 2 } Q + a _ { 1 3 } U + a _ { 1 4 } V \# ( 4 )
$$

经过a，b，c， $\textrm { d }$ 四组不同的调制状态后可以得到四组光强值，满足：

$$
{ \left[ \begin{array} { l } { I _ { a } } \\ { I _ { b } } \\ { I _ { c } } \\ { I _ { d } } \end{array} \right] } = { \left[ \begin{array} { l l l l } { a _ { 1 1 } } & { a _ { 1 2 } } & { a _ { 1 3 } } & { a _ { 1 4 } } \\ { b _ { 1 1 } } & { b _ { 1 2 } } & { b _ { 1 3 } } & { a _ { 1 4 } } \\ { c _ { 1 1 } } & { c _ { 1 2 } } & { c _ { 1 3 } } & { c _ { 1 4 } } \\ { d _ { 1 1 } } & { d _ { 1 2 } } & { d _ { 1 3 } } & { d _ { 1 4 } } \end{array} \right] } { \left[ \begin{array} { l } { I } \\ { Q } \\ { U } \\ { U } \end{array} \right] } \# ( 5 )
$$

将上式记为 $I _ { m } = X S$ ，当调制矩阵X可逆，方程有唯一解，待测光斯托克斯矢量为：

$$
S = X ^ { - 1 } I \# ( 6 )
$$

我们提出了一种基于双DKDP 的偏振测量方法，如图3所示。该偏振分析器的偏振调制器由两组快轴方向不同的DKDP晶体和一个偏振片构成，光强探测器为光强采集相机。

![](images/706930451bb74bd0c7e8c0eab7059f70b7a590a46513b4f3e586ded99d228d45.jpg)  
图3基于DKDP的偏振分析器结构示意图

Figure 3 Schematic diagram of the structure of the polarization analyzer based on DKDP

假定入射光斯托克斯矢量为 $\mathsf { S } _ { i n }$ ，

$$
\mathsf { S } _ { i n } = \left[ \begin{array} { l } { I } \\ { Q } \\ { U } \\ { V } \end{array} \right] \# ( 7 )
$$

则通过偏振调制器后的其斯托克斯矢量变为 $\mathbf { \boldsymbol { S _ { o u t } } }$ ，

$$
\mathsf { S } _ { o u t } = M _ { p } \cdot M _ { 2 } \cdot M _ { 1 } \cdot S _ { i n } \# ( 8 )
$$

其中， $M _ { 1 }$ ， $M _ { 2 }$ ， $M _ { p }$ 分别为第一组DKDP 晶体、第二组DKDP 晶体和检偏器的穆勒矩阵。

令DKDP1晶体快轴角度为 $0 ^ { \circ }$ ，相位延迟量为δ，DKDP2晶体快轴角度为 $4 5 ^ { \circ }$ ，相位延迟量为ε，检偏器（偏振片）透光轴为 $0 ^ { \circ }$ 。检偏器的偏振方向角与笛卡尔坐标系的选取有关，为了方便分析，我们此处令检偏器的偏振方向为坐标系的X轴方向。则DKDP 晶体和检偏器的穆勒矩阵 $M _ { 1 }$ ， $M _ { 2 }$ ， $M _ { p }$ 为：

$$
\begin{array} { r } { M _ { 1 } = \left[ \begin{array} { c c c c } { 1 } & { 0 } & { 0 } & { 0 } \\ { 0 } & { 1 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { c o s \delta } & { s i n \delta } \\ { 0 } & { 0 } & { - s i n \delta } & { c o s \delta } \end{array} \right] \# } \\ { M _ { 2 } = \left[ \begin{array} { c c c c } { 1 } & { 0 } & { 0 } & { 0 } \\ { 0 } & { c o s \varepsilon } & { 0 } & { - s i n \varepsilon } \\ { 0 } & { 0 } & { 1 } & { 0 } \\ { 0 } & { s i n \varepsilon } & { 0 } & { c o s \epsilon } \end{array} \right] \# ( \hbar ) } \end{array}
$$

$$
M _ { p } = 0 . 5 \left[ \begin{array} { c c c c } { 1 } & { 1 } & { 0 } & { 0 } \\ { 1 } & { 1 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 0 } & { 0 } \\ { 0 } & { 0 } & { 0 } & { 0 } \end{array} \right] \#
$$

此时，通过偏振分析器后的斯托克斯矢量为：

$$
\mathsf { S } _ { o u t } = \left[ \begin{array} { l } { I } \\ { Q } \\ { U } \\ { V } \end{array} \right] = M _ { p } \cdot M _ { 2 } \cdot M _ { 1 } \cdot S _ { i n } \# ( 1 2 )
$$

光强探测器接收到的光强为：

$$
\mathrm { I } = 0 . 5 ( \mathrm { I } + \mathrm { Q c o s } \varepsilon + \mathrm { U s i n } \varepsilon \mathrm { s i n } \delta - \mathrm { V s i n } \varepsilon \mathrm { c o s } \delta ) \# ( 1 3 )
$$

改变两组DKDP 晶体的外加电压，得到4组不同的偏振调制状态，光强探测器测得 4组不同的光强值 $I _ { o u t } = [ \mathrm { I } _ { 1 } , \mathrm { I } _ { 2 } , \mathrm { I } _ { 3 } , \mathrm { I } _ { 4 } ] ^ { T }$ 。由于一般只需要斯托克斯矢量的相对值，所以式中的0.5可略去，得到偏振调制矩阵为：

$$
X = { \left[ \begin{array} { l l l l } { 1 } & { \cos \varepsilon _ { 1 } } & { \sin \varepsilon _ { 1 } \sin \delta _ { 1 } } & { - \sin \varepsilon _ { 1 } \cos \delta _ { 1 } } \\ { 1 } & { \cos \varepsilon _ { 2 } } & { \sin \varepsilon _ { 2 } \sin \delta _ { 2 } } & { - \sin \varepsilon _ { 2 } \cos \delta _ { 2 } } \\ { 1 } & { \cos \varepsilon _ { 3 } } & { \sin \varepsilon _ { 3 } \sin \delta _ { 3 } } & { - \sin \varepsilon _ { 3 } \cos \delta _ { 3 } } \\ { 1 } & { \cos \varepsilon _ { 4 } } & { \sin \varepsilon _ { 4 } \sin \delta _ { 4 } } & { - \sin \varepsilon _ { 4 } \cos \delta _ { 4 } } \end{array} \right] } \#
$$

则有 $\dot { I } _ { o u t } = 0 . 5 X \cdot S _ { i n }$ ，当偏振调制矩阵X可逆，可得

$$
S _ { i n } = { \binom { I } { Q } } = 2 \mathrm { X } ^ { - 1 } \left[ { \binom { I _ { 1 } } { I _ { 2 } } } \right] \#
$$

$S _ { i n }$ 即为待测光斯托克斯矢量。

# 2 参数最优化设计

偏振测量过程中测量精度会受到偏振调制器调制矩阵误差和光强探测器探测误差等的影响，而偏振调制矩阵参数的不同选择对于误差的传播影响不同。在保证偏振调制矩阵可逆的同时，合理地选用调制参数可以显著减小噪声扰动和系统误差对测量结果的影响。此处以假定只存在光强探测器误差为例。

令I为光强探测值，I为光强真值， $S ^ { \prime }$ 为斯托克斯矢量计算值，S为真值。光强误差 $\Delta I$ 为$\Delta I = I ^ { \prime } - I$ ，斯托克斯矢量误差 $\Delta S$ 为

$$
\Delta S = S ^ { \prime } - S = X ^ { - 1 } I ^ { \prime } - S = X ^ { - 1 } ( I + \Delta I ) - S = X ^ { - 1 } \Delta I
$$

由 $I = X S$ ，得

$$
\begin{array} { c } { \| I \| = \| X S \| \leq \| X \| \| S \| } \\ { \| \Delta S \| = \| X ^ { - 1 } \Delta I \| \leq \| X ^ { - 1 } \| \| \Delta I \| \# ( 1 6 ) } \\ { \frac { \| \Delta S \| } { \| S \| } { \leq } \| X ^ { - 1 } \| \| X \| \frac { \| \Delta I \| } { \| I \| } } \end{array}
$$

上式给出了相对误差 $\| \Delta S \| / \| S \|$ 的误差上界，光强探测器误差在求解过程中可能会被放大$\| X ^ { - 1 } \| \| X \|$ 倍，偏振调制矩阵误差结果相同，在此不做推导。通常称$\scriptstyle \mathrm { c o n d ( X ) = } \| X ^ { - 1 } \| \| X \|$ 为矩阵X的条件数（CN）9]。矩阵X的条件数越小，在矩阵方程求解过程中误差的放大越小。根据研究结果以及仿真验证，对于全斯托克斯矢量测量，偏振调制矩阵的条件数最小值为 $\sqrt { 3 }$ ，因此，当调制矩阵条件数为√3时，偏振调制参数最优。

偏振调制矩阵如式（14）所示，基于优化速度更快的拟牛顿算法，通过最小化矩阵 X的 CN 来实现优化过程[10]。拟牛顿算法是解决无约束优化问题有效且成熟的算法，相对于牛顿算法，其只要求目标函数一次连续可微，易于实现，计算量小。通常情况下，实现相同的最佳优化CN有无限种解决方案，用于偏振测量时，它们具有相同的性能，此处我们仅选取其中一组参数：

# 表2偏振调制方案参数

# Table2 parametersofpolarization modulationscheme

<html><body><table><tr><td>DKDP1 delay（rad)</td><td>DKDP2 delay（rad)</td><td>Polarizer angle</td></tr><tr><td>5.4978</td><td>5.3279</td><td>0°</td></tr><tr><td>5.4978</td><td>0.9553</td><td>0°</td></tr><tr><td>3.9270</td><td>2.1863</td><td>0°</td></tr><tr><td>3.9270</td><td>4.0969</td><td>0°</td></tr></table></body></html>

此时，偏振调制矩阵为

此时，偏振调制矩阵求解时对误差的放大最小。

此外，偏振调制矩阵的等加权方差（EWV）也是评估误差传递的标准之一，但 EWV的值主要受到数据冗余的影响。并且，本文中的新测量方案仅适用于带宽极窄（ $. \Delta \lambda { \leq } 0 . 1 \mathrm { \AA } )$ （204号应用场景下，通常与滤光器配合使用，其光谱色散问题可以忽略，不考虑偏振测量效率。本文所使用的DKDP晶体透过范围为 $2 0 0 { \sim } 2 1 5 0 \mathrm { n m }$ ，在目标波长 $5 3 2 . 4 \mathrm { n m }$ 处透过率可达 $9 7 \%$ 。

# 3仿真分析验证

在传统的波片 ${ \bf \tau } + { \bf D } { \bf K D P }$ 晶体式偏振分析器中，常采用6次调制的测量方案，由于冗余项的存在，其精度会略优于同等条件下（ $\mathrm { C N } = { \sqrt { 3 } } .$ ）的4次调制方案。在此我们比较两者的精度差异，并验证提出的 DKDP 偏振分析器精度是否符合测量要求。在本文中太阳偏振测量精度要求为 $2 \times 1 0 ^ { - 3 }$ 。由于市面上常见偏振片消光比误差约为 $1 0 ^ { - 6 } - 1 0 ^ { - 4 }$ ，其引起的测量误差可以忽略；在此，我们将比较两种调制方案中光强探测器误差、DKDP相位延迟误差以及DKDP晶体和偏振片角度误差对测量结果影响。

# 1）光强探测器误差

测量过程中，受到环境杂散光和光强探测器本身噪声的影响，光强探测器测得的光强值存在一定的误差。此误差将直接反应到待测光的偏振误差，由此我们有必要验证提出测量方案的测量误差满足测量精度。

一般情况下，光强探测器的非线度在 $1 - 2 \%$ ，难以满足偏振测量要求，通常都需要对其响应函数进行标定。假定光强探测器的非线性误差为 $\scriptstyle 8 = 0 . 0 2$ ，且只考虑光强探测器误差，光强误差导致的偏振误差计算方案如下

$$
\Delta S = S ^ { \prime } - S = X ^ { - 1 } I ^ { \prime } - X ^ { - 1 } I \# ( 1 7 )
$$

为了评估方案的性能，我们分析了光强噪声为0.02和0.001（标准差）时，1000个不同入射偏振态(不同偏振分量)的测量精度。一般地，光束的完全偏振态可以用庞加莱球（Poincaré Sphere）球面上的每一个点来表示。我们选取Poincaré球面上的1000个均匀采样点，其中20个不同椭圆度的的圆从南极到北极，每个圆的50个方位角顺时针方向移动指向的偏振态作为入射偏振态。在仿真中，通过添加一个信号独立的高斯噪声，每个状态产生

100组强度值，计算出100组测量误差的标准差作为对应偏振态的测量误差

![](images/ec4afbeeb7ea3934529fec5aace9627d03b7d156d41750622b9553f44028f260.jpg)  
图4庞加莱球

![](images/9cead14ef3d3469e1ac4e9ce81db58a1d9aa2786295efa43a07edde1cc36a897.jpg)  
图5偏振采样点

图6中，Q1-V1为我们提出的DKDP偏振测量方案结果，Q2-V2为传统方案测量结果。显然，两种测量方案的斯托克斯矢量误差在同一数量级，但由于光强探测器非线性在 $2 \%$ 导致了两种方案的误差都达到了 $1 0 ^ { - 2 }$ 误差等级，难以满足测量要求。我们又将光强探测器的非线性降低到 $1 \text{‰}$ 后，得出了图7中结果。可以看到，在光强探测误差为 $1 \text{‰}$ 时，对于斯托克斯矢量Q、U、V分量的测量误差，传统测量方案的误差在 $1 . 4 \times 1 0 ^ { - 3 }$ 左右，而新的偏振测量方案误差在 $1 . 7 \times 1 0 ^ { - 3 }$ 左右，误差均小于 $2 \times 1 0 ^ { - 3 }$ ，满足偏振测量要求。

![](images/04c856ea60e87aaa4a5fee5b4c35ffce49a32fa7d2dcbe2c3b91dab48fc9daae.jpg)  
Figure 4Poincare sphere   
图6Stokes矢量误差比较（ $8 \%$ ）  
Figure 6 Stokes vector error comparison ( $8 = 2 \%$ ）

![](images/96e9d3846551111e0c299515455932d78fec34316f17d7fe3d81ff136a62300c.jpg)  
Figure 5 polarization sampling points   
图7Stokes矢量误差比较（ $8= 1 \text{‰}$ ）Figure 7 Stokes vector error comparison $8 \text{‰}$ ）

2）DKDP晶体相位延迟误差

测量过程中，在控制外加电压切换DKDP 晶体相位延迟时，由于电压-相位延迟曲线会存在一定的误差，导致偏振测量的结果也会出现误差。经过对应波长下（本文为 $5 3 2 . 4 \mathrm { n m } \dot { }$ ）的电压-相位延迟标定后，DKDP 晶体的延迟误差一般小于0.001弧度。我们需要验证两种测量方案下，由相位延迟误差引起的偏振测量误差是否在误差允许范围内。被测偏振态的采样方法与上述方法相同。在仿真时，添加一个独立的标准差为0.001的角度高斯噪声，得到1000 个偏振状态的测量误差。

![](images/c53d1f8167e75a99a141d610fb9b5aa567526e218e07611d858105ebbd20c527.jpg)  
图8DKDP相位延迟误差导致的测量误差比较

Figure 8 Comparison of measurement errors caused by DKDP phase delay error

图8中，Q1-V1为我们提出的双DKDP 偏振测量方案结果，Q2-V2为传统方案测量结果。容易看出，两种测量方式由DKDP相位延迟误差引起的偏振测量误差均小于 $\cdot 1 0 ^ { - 3 }$ ，其中Q分量测量结果优于传统测量方式，U分量和V分量误差值几乎相等，满足测量需求。

3）DKDP晶体快轴与偏振片角度误差

由于DKDP 晶体与偏振片在偏振分析器中固定不动，在对DKDP 晶体的快轴与偏振片角度完成标定后，其角度误差远小于0.001弧度。此处我们假定DKDP 晶体的快轴与偏振片角度误差均为0.001弧度，验证其是否满足测量精度的要求。使用相同的采样方法得到1000个偏振采样点，并添加一个独立的标准差为0.001的高斯噪声到DKDP2 晶体的快轴角度参数，得到受快轴角度误差影响的偏振测量误差。同理得到偏振片角度误差导致的偏振测量误差。

![](images/1c3cb8fc8afaf78719f1da2a24f626bb9a809eca7dd5af9e009e3cf9d738eb10.jpg)  
图9DKDP2快轴角度误差结果 Figure 9 DKDP 2 fast axis angle error results

![](images/b667e4b6effd3d57d88bd241dbf756e96f399fce93f2fbfc6b9d01011dc0b848.jpg)  
图10偏振片角度误差结果  
Figure 1O polarizer angle error results

从图9和图10中我们可以看出，在两种角度误差的影响下，测得的斯托克斯矢量中只有Q分量会受到 DKDP2 晶体快轴角度误差和偏振片角度误差的影响，且其测量误差小于$2 \times 1 0 ^ { - 3 }$ ，满足偏振测量的要求。由于DKDP晶体固定不动，受到快轴角度误差的影响远远小于传统的波片式结构。

最后，我们对两种方案的测量时间进行了对比分析。其中，DKDP 晶体毫秒级的响应时间可忽略不计，令相机采集频率为10帧/秒，为了提高精度，每个调制位置采集两帧图像。

<html><body><table><tr><td colspan="6">Table 3 scheme comparison (single wavelength point)</td></tr><tr><td></td><td>Modulation</td><td>Modulation</td><td>Camera</td><td>image frames</td><td>Measuring time</td></tr><tr><td></td><td>frequency</td><td>steps</td><td>frequency</td><td></td><td></td></tr><tr><td>Traditional scheme</td><td>>5s</td><td>3(wave plate)</td><td>10 frames /</td><td>12 frames</td><td>>16.2s</td></tr><tr><td>DoubleDKDP</td><td>millisecond</td><td>4</td><td>sec 10 frames /</td><td>8 frames</td><td>~0.8s</td></tr><tr><td></td><td></td><td></td><td></td><td></td><td></td></tr><tr><td>scheme</td><td></td><td></td><td>sec</td><td></td><td></td></tr></table></body></html>

表3方案对比（单波长点）  
表4方案对比(6个波长点）  
Table 3 Scheme comparison (6 wavelength points)   

<html><body><table><tr><td></td><td>Modulation frequency</td><td>Modulation steps</td><td>Wavelength point switching time</td><td>image frames</td><td>Measuring time</td></tr><tr><td>Traditional scheme</td><td>>5s</td><td>18</td><td>14s</td><td>72</td><td>>111.2s</td></tr><tr><td>Double DKDP scheme</td><td>millisecond</td><td>24</td><td>14s</td><td>48</td><td>~18.8s</td></tr></table></body></html>

从上面的对比中我们可以看出，在单波长点偏振测量中，传统方案测量时间大于16.2s是双DKDP 测量方案测量时间（0.8s）的 20倍以上；在6个波长点的偏振测量中，传统方案测量时间大于111.2s，双DKDP 测量方案测量时间约为18.8s，由于波长点切换频率较低的影响存在，传统方案测量时间为双DKDP方案的6倍左右。因此，采用本文提出的基于双 DKDP 晶体原理的实时偏振测量方案，在单波长点和多波长点偏振测量中，时间分辨率可分别提升20倍和6倍。

# 4结论

太阳大气探测在空间天气预报和太阳物理研究等方面发挥着重要作用，而太阳磁场驱动太阳活动爆发的根本驱动力，偏振测量是实现太阳磁场探测的重要过程。目前偏振测量的主要手段包括旋转波片调制方式与波片+DKDP 晶体调制方式，波片+DKDP 晶体的测量方法相比旋转波片可以减少旋转波片的次数，缩短测量时间，但由于波片结构的存在，仍然需要大量时间，实时性不佳，且容易出现仪器抖动等问题。基于DKDP 晶体毫秒级的电光响应速度，本文提出了基于双DKDP 晶体原理的实时偏振测量方法，采用了两组DKDP 晶体作为偏振调制器件，调制时间可从数秒提升到毫秒级，大大提升了测量的实时性。本文通过仿真验证了该方法的可行性，在精度上优于 $2 \times 1 0 ^ { - 3 }$ ，在单波长点和多波长点偏振测量中，时间分辨率可提升至传统方案的20倍和6倍，对太阳大气实时偏振探测有重要意义。

# 参考文献

[1] Frank Y.Shih.Automated lfare forecasting using a statistical learning technique[J].Research in Astronomy and Astrophysics,2010,10(08):785-796.

[2] Jie Jiang,Piyali Chaterjee,Arnab Rai Choudhuri. Solar activity forecast with a dynamo model[J]. Monthly Notices of the Royal Astronomical Society,20O7,381(4).

[3] Balthasar H,von der Luhe,O, Kneer F,et al. GREGOR: the New German Solar Telescope[J].   
Astrophysics,2007,368.

[4] Scientific instrumentation for the $1 . 6 \mathrm { ~ m ~ }$ New Solar Telescope in Big Bear[J]. Astronomische Nachrichten,2010, 331(6):636-639.

[5] Rui Wang， Zhi Xu, Zhen-Yu Jin,et al.The first observation and data reduction of the Multi-wavelength Spectrometer on the New Vacuum Solar Telescope[J].Research in Astronomy and Astrophysics,2013,13(10):1240-1254.

[6]覃瑛,彭建国,张涛.NVST 偏振观测系统的运动控制实现[J].天文研究与技术,2018,15(03):315-322.

Ying Q，Jianguo P，Tao Z，et al. The Movement and Control Realization of NVST Polarization Observation System[J]. Astronomical Research & Technology, 2018,15(O3):315-322. [7]艾国祥，胡岳风．太阳磁场望远镜中 ${ \bf K D ^ { * } P }$ 电光调制器[J]．天体物理学报，1981，1(4): 273-284.

Ai Guoxiang,Hu Yuefeng. The $\mathrm { K D ^ { * } P }$ modulator in the solar magnetic field telescope[J]. Acta Astrophysica Sinica, 1981,1(4): 273-284.

[8] Andriyevsky B,Patryn A, Cobet C ,et al. Electronic Properties of KDP and DKDP Crystals: Ab-Initio Calculationsand SpectralElipsometryExperiment[J]. Ferroelectrics，2011, 417(1):2O-24.[9] Peinado Alba, Lizana Angel, Vidal Josep, et al. Optimization and performance criteria of a Stokes polarimeter based on two variable retarders. Optics Express，2010, 18(10):9815-30.

[10] Gu N , Yao B , Huang L,et al. Design and Analysis of a Novel Compact and Simultaneous Polarimeter for Complete Stokes Polarization Imaging with a Piece of Encoded Birefringent Crystal and a Micro-Polarizer Array[J]. IEEE Photonics Journal, 2O18,PP(99):1-1.

# Real time polarization detection of solar atmosphere based on double DKDP crystals principle

Hu Ping23，GuNaiting，Raohang2 (1. Institute of Optics and Electronics, Chinese Academy of Sciences, Chengdu 610209, China; 2. Key Laboratory of Adaptive Optics, Chinese Academy of Sciences, Chengdu 610209, China; 3. University of Chinese Academy of Sciences,Beijing,10o049,China, Email:hulping@foxmail.com)

Abstract: Magnetic field is the fundamental driving force of solar eruptions.High precision real-time polarization measurement is a common method to realize magnetic field measurement. However, the commonly used wave plate measurement method needs to be measured many times, and there is a mechanical rotation structure, which is easy to cause instrument jiter and reduce the measurement accuracy; the rotation or switching of wave plate will also lead to a longer measurement time. At present, the measurement period of solar atmospheric polarization based on DKDP crystal and wave plate is long,and the real-time performance is not well, so it can not be applied to the detection of rapidly changing solar active magnetic field. Based on the above background, this paper proposes a real-time polarization detection technology of the solar atmosphere based on the principle of double DKDP crystals. Two DKDP crystals with different fast axis directions are used to realize the polarization modulation of the incident sunlight and obtain the polarization Stokes vector of the solar atmosphere. Compared with the traditional method of combining rotating wave plate and DKDP crystal, the proposed method can increase the single polarization modulation rate from several seconds to millisecond，which greatly improves the real-time performance of solar magnetic field measurement. The simulation results show that the measurement accuracy of the proposed method is $2 \times 1 0 ^ { - 3 }$ , and the measurement time resolution of single wavelength point is improved by more than 2O times, which can realize the real-time accurate measurement of the polarization information of solar magnetic field.

Key words: Solar magnetic field; Polarization measurement; DKDP; Real-time measurement