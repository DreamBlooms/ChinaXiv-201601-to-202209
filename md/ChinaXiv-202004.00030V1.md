# 星载氢原子钟用多段线圈式C场的仿真及应用

潘志兵1,2,谢勇辉1,帅 涛1,陈鹏飞1,裴雨贤1,潘晓燕1,赵阳1,林传富1（1．中国科学院上海天文台，上海 200030；2．中国科学院大学，北京100049）

摘要：星载氢原子钟具有频率稳定度高、频率漂移率低的优点，在卫星导航定位和频率计量中得到了广泛应用。星载氢原子钟的腔泡系统用于实现氢原子的量子跃迁及其信号采集，原子跃迁信号幅度直接决定了系统信噪比，进而影响整机性能指标，所以腔泡系统是星载氢原子钟的核心组件。目前，星载氢原子钟腔泡系统主要采用直螺线管来产生原子跃迁所需的C场。由于星载氢原子钟物理部分的结构限制，直螺线管的磁场均匀度有进一步提高的空间。探讨使用多段线圈代替直螺线管用于产生C场的可行性。首先对多段线圈产生的磁场进行理论分析计算，同时使用ANSYS 电磁场仿真软件对多段线圈的各项参数进行仿真和优化，包括各段长度、段数、间距以及匝数、内径和总长度等。然后优选磁场均匀度较好的线圈配置参数，可将C场的非均匀度由直螺线管约 $10 \%$ 降低到多段线圈约 $1 \%$ 。根据仿真优化结果建立了试验九段线圈，对比测试了原子跃迁信号增益，同时结合电路部分进行了闭环测试，对频率稳定度指标进行了对比。实验结果表明,原子跃迁信号可有效提升，阿伦方差在中短稳(1S-1000S)能表现更好。此项工作为星载氢原子钟整机性能指标的进一步提升打下了基础。

关键字：星载氢原子钟;腔泡系统;C场;多段线圈;均匀磁场;原子跃迁信号增益;频率稳定度；

中图分类号：TB939 文献标识码：A 文章编号：1672-7673(2020)03

星载氢原子钟利用基态氢原子的超精细能级跃迁信号进行计时，具有频率稳定度高、频率漂移率低等优点。目前,其长期频率稳定度可达3E-15/天，频率漂移率小于 5E-15/天，并已在卫星导航定位系统如北斗系统和伽利略系统中得到了广泛应用[1-2]。

星载氢原子钟的发展方向是进一步压缩其重量和体积，并进一步提高性能指标。频率稳定度理论计算公式[3-4]为

$$
\begin{array} { r } { \sigma ( \mathrm { t } ) = \sqrt { \frac { \mathrm { K } _ { s } \mathrm { K T F } _ { \mathrm { r } } } { 2 \mathrm { A } _ { \mathrm { c } } } } \frac { ( 1 + \mathrm { S } _ { 0 } - \alpha ) ^ { 2 } } { \mathrm { Q } _ { 0 } \alpha \sqrt { \mathrm { S } _ { 0 } } ( 1 + \mathrm { S } _ { 0 } ) } \tau ^ { - \frac { 1 } { 2 } } } \end{array}
$$

其中, $\alpha$ 为氢原子钟的振荡参数，定义为

$$
\begin{array} { r } { \alpha = \frac { \mu _ { 0 } \mu _ { \mathrm { B } } { } ^ { 2 } T _ { 1 } T _ { 2 } \phi \eta / Q _ { \mathrm { C } } } { \lambda V _ { \mathrm { b } } } } \end{array}
$$

其中, $Q _ { \mathsf { C } }$ 为腔泡系统的 $Q$ 值， $\eta ^ { \prime }$ 为腔泡系统的微波填充因子。由(1)式和(2)式可知，星载氢原子钟的稳定度指标由腔泡系统的 $Q$ 值、微波填充因子和原子驰豫时间等决定。为了保证星载氢原子钟的稳定度指标，要求腔泡系统具有尽可能高的 $Q$ 值、微波填充因子和原子寿命。因此，腔泡系统的性能直接决定了整机性能指标，是星载氢原子钟的核心组件。

星载氢原子钟储存泡内的氢原子在轴向静磁场（C场）的作用下，由微波腔内的微波场激励氢原子自（ $\scriptstyle { F = 1 }$ ， $\scriptstyle m = 0$ ）态跃迁至（ $\scriptstyle { F = 0 }$ ， $\scriptstyle m = 0$ ）态。腔泡系统的微波填充因子 $\eta ^ { / }$ 反映了微波场与原子体系和轴向静磁场（C场）的耦合情况。C场的作用是将各量子态去简并和为原子跃迁提供量子化轴。如果C场在储存泡区域内的分布与微波场不一致，则处于该非均匀静磁场作用下的氢原子在储存泡内发生共振跃迁时，会有部分原子的跃迁频率偏离期望的原子跃迁中心频率，从而降低了（0-0）跃迁的峰值强度[5-6]，进而影响跃迁谱线的增益和信噪比，所以C场与微波场的耦合度是影响跃迁谱线质量的重要因素。

目前本单位星载氢钟腔泡系统采用了电极式结构，其在储存泡区域内的微波场分布均匀，磁场强度波动小于 $1 \% ^ { [ 7 ] }$ 。因此,要求在储存泡区域内的C 场也应当沿轴向尽可能均匀分布。考虑到星载氢原子钟的重量和体积，一般直接由直螺线管单层线圈，或者含有两端补偿的直螺线管双层线圈产生所需要的C场，但前者产生的磁场均匀度仍可以继续改善，后者增加了物理结构的设计要求，并且两端补偿线圈需要额外供电，也增加了电路部分的设计要求。

通过计算和仿真，设计了磁场均匀度更好的单层式单路供电的制造简单的多段线圈,并应用于星载氢钟腔泡系统，无需对星载氢原子钟电路部分8做任何改动。实验结果显示,可有效提升星载氢钟氢原子（0-0)跃迁的信号强度，并有助于提高频率稳定度指标。

# 1直螺线管分析和仿真

直螺线管中心轴线上的磁感应强度[9]：

$$
\begin{array} { r } { \mathrm { ~ B ~ } { } = \frac { \mu _ { 0 } \mathrm { n I } } { 2 } \left[ \frac { \mathrm { l _ { 1 } } } { ( \mathrm { l _ { 1 } ^ { 2 } } + \mathrm { R ^ { 2 } } ) ^ { 1 / 2 } } + \frac { \mathrm { l _ { 2 } } } { ( \mathrm { l _ { 2 } ^ { 2 } } + \mathrm { R ^ { 2 } } ) ^ { 1 / 2 } } \right] } \end{array}
$$

其中, $\mu _ { 0 }$ 为真空磁导率； $n$ 为单位长度的匝数； $I$ 为通过直螺线管的电流； $R$ 为直螺线管半径； $l _ { 1 } , l _ { 2 }$ 分别为该点到直螺线管两端的距离。由(3)式可知，如果直螺线管的长度比半径大很多 $( l \gg R )$ ，则其中部磁感应强度约为 $B \approx \mu _ { 0 } n I$ ，在靠近直螺线管的两端，磁感应强度将降低至 $B \approx \mu _ { 0 } n I / 2$ 。在直螺线管的中部区域，磁场总体上较为均匀，但两端处的磁感应强度仅为中间区域的一半左右。考虑到星载氢原子钟实际应用时，原子储存泡顶端比较接近直螺线管的端面，必然导致原子储存泡区域内的C场不均匀。

按照星载氢钟当前使用的直螺线管实际尺寸，通过ANSYS 电磁场仿真软件，可以对直螺线管在储存泡区域产生的静磁场进行仿真，仿真模型和结果见(a) (b)

图1。

![](images/f0e75967028c803f9eda48ccd8f4f564901712f4280bc7b63ad8342aa671d21f.jpg)  
图1 (a)直螺线管在储存泡区域的仿真模型；(b)仿真结果  
Fig.1 Simulation model (a)and simulation results(b)of straight solenoid in the area of storage bulb

由(a)

图1仿真结果可知，储存泡内磁场强度最大值为 $6 . 7 1 \mathrm { E ^ { - } 2 A / m }$ ，最小值和最大值差值为 $0 . 7 1 \mathrm { E ^ { - } 2 A / m }$ 两者相差达到 $1 0 . 5 8 \%$ 。由此可见，实际工程上使用的普通直螺线管的磁场均匀度较为一般，有较大的提升空间。

# 1九段线圈分析和仿真

# 1.1多段线圈均匀度理论分析

亥姆霍兹线圈(Helmholtz Coi1)是由两个相同的线圈同轴放置，其中心间距等于线圈的半径。如果这两个线圈通以相同电流，磁场将会叠加增强，并在一定区域内形成均匀磁场[10]。亥姆霍兹两线圈相距为 $d$ 且共轴，半径均为R，取两线圈圆心连线中点为 $x = 0$ 处，线圈中心轴线处磁场可表示为(4)式[1]。当 $d = R$ 时，两线圈圆心之间的区域磁场较强并最均匀，两线圈圆心之外的区域磁场强度逐渐衰减[12]。

$$
\begin{array} { r } { B ( x ) = \frac { \mu _ { 0 } \mathrm { I R } ^ { 2 } } { 2 [ \mathrm { R } ^ { 2 } + ( \frac { \mathrm { d } } { 2 } + \mathrm { x } ) ^ { 2 } ] ^ { 3 / 2 } } + \frac { \mu _ { 0 } \mathrm { I R } ^ { 2 } } { 2 [ \mathrm { R } ^ { 2 } + ( \frac { \mathrm { d } } { 2 } - \mathrm { x } ) ^ { 2 } ] ^ { 3 / 2 } } } \end{array}
$$

两段式亥姆霍兹线圈可在其中部区域产生均匀磁场。星载氢原子钟储存泡的轴向长度为 $1 5 0 \mathrm { m m }$ ，如果使用两段式亥姆霍兹线圈产生包含储存泡在内的较大区域的均匀磁场，则线圈半径约为 $1 5 0 \mathrm { m m }$ ，占用非常大的体积空间。考虑到星载氢原子钟的体积限制，故无法直接使用两段式亥姆霍兹线圈。

参考亥姆霍兹线圈的组合方式，可将多个较小的线圈进行特定的组合，以提高C场均匀度[13]。多段线圈是将通以一路同大小同方向电流的多个线圈同轴组合在一起。多段线圈由 $\boldsymbol { \mathit { \Pi } } _ { n }$ 个线圈组成。假设第 $\boldsymbol { n }$ 个线圈的中心坐标为 $Z _ { \mathrm { n } }$ ，长度为 $L _ { \mathrm { n } }$ ，线圈匝数为 $N _ { \mathrm { n } }$ ，则此线圈在C场中心轴线上产生的磁场可近似用直螺线管的公式计算：

$$
\begin{array} { r } { \mathrm { B _ { n } ( z ) } = \frac { \mathrm { \mathrm { I _ { 0 } N _ { n } I } } } { 2 } \left[ \frac { \frac { \mathrm { L _ { n } } } { 2 } - \mathrm { ( z - Z _ { n } ) } } { \bigl ( \mathrm { R } ^ { 2 } + \bigl ( \frac { \mathrm { L _ { n } } } { 2 } - \mathrm { ( z - Z _ { n } ) } \bigr ) ^ { 2 } \bigr ) ^ { 1 / 2 } } + \frac { \frac { \mathrm { L _ { n } } } { 2 } + \mathrm { ( z - Z _ { n } ) } } { ( \mathrm { R } ^ { 2 } + \bigl ( \frac { \mathrm { L _ { n } } } { 2 } + \mathrm { ( z - Z _ { n } ) } \bigr ) ^ { 2 } ) ^ { 1 / 2 } } \right] } \end{array}
$$

因此， $\scriptstyle n$ 个线圈组成的多段线圈在中心轴线上总的磁感应强度可表示为

$$
\begin{array} { r } { \mathsf { B } ( \mathbf { z } ) = \sum _ { \mathrm { i } = 1 } ^ { \mathrm { n } } \mathsf { B } _ { i } ( \mathbf { z } ) } \end{array}
$$

多段线圈的各项参数，包含各段长度 $L _ { n }$ 、段数 $\cdot \boldsymbol { n }$ 、间距 $Z _ { n + 1 } - Z _ { n }$ ，单位长度匝数 $N _ { \mathrm { n } }$ ，内径 $R$ ，总长度L均可以进行调整。综合考虑上述各个参数，并进行相应调整，即可设计出在整个储存泡区域的磁场均匀度很高的多段线圈。

1.2九段线圈均匀度计算机仿真

(5)式和(6)式均为在C场中心轴线上场强的近似求解，并非精确的解析解，且未计算中心轴线外的整体区域的磁场。计算类似线圈结构中心轴线外的场强有很多方法[1-20]。但此处的多段线圈数量更多结构更复杂，且要同时准确计算中心轴线上和中心轴线外的磁场强度，故采用有限元数值方法即电磁场软件仿真的方式进行整体全区域磁场的求解实现。

多段线圈可调节的参数很多，既要足够的可调节参数，又要降低计算机仿真和物理机械结构实现的复杂性。借助ANSYS 电磁场仿真软件，主要开展段数为九段的多段线圈仿真工作。该模型综合考虑星载氢钟中与C场相关的其他结构，比如C场支架、储存泡和磁屏蔽系统等。线圈输入电流 $0 . 0 2 \mathrm { m A }$ ，刚好可以产生氢原子钟工作时所需要的约1mGauss磁场。经过对九段线圈的各个参数反复调整，获得了一组较优的线圈参数，仿真模型和结果见(a) (b)

![](images/6f0d18fc908712de675a3e7a99a8fba90d553ad522fb2029807d628e770eadf8.jpg)  
图2。  
图2 (a)九段线圈在储存泡区域的仿真模型;(b)仿真结果  
Fig.2Simulation model(a)and simulation results (b)of nine-section coil in the area of storage bulb

由(a)

图2仿真结果可知，在九段线圈参数下，储存泡内磁场强度最大值为 $4 . 6 0 \mathrm { E - 2 A / m }$ ，最小值和最大值差值为 $0 . 0 4 \mathrm { E ^ { - 2 } A / m }$ ，两者相差 $0 . 8 7 \%$ ，磁场均匀度较直螺线管有了较大的提升。

直螺线管和九段线圈在储存泡区域中心轴线上产生的磁场均匀度如 (a)(b)

图3。由(a)

图3可知，直螺线管在储存泡区域中心轴线上产生的磁场均匀度在 $91 \%$ 左右，但九段线圈在储存泡区域中心轴线上产生的磁场均匀度可提升至 $9 9 . 2 \%$ 。

# ChinaXiv合作期刊

![](images/5da356fe89842111cd638c096647ef1f803fa88d476f82c29203f610e87b9a6e.jpg)  
图3(a)直螺线管在储存泡区域中心轴线上的磁场均匀度对比;

Fig.3Comparsofgtifomoeietwetraghtsoledadctioclothtralisoforaubi

计算和仿真表明，多段线圈的段数越多，可调节的参数也越多，更容易实现原子储存泡区域内极佳的磁场均匀度。各类线圈在储存泡区域的磁场均匀度见表1，由表1可知，九段线圈可以在整个储存泡区域实现大于 $9 9 \%$ 的磁场均匀度。

表1各类线圈在储存泡区域的磁场均匀度分布情况  
Table1 Thehomogeneity of magnetic field of various types of coil in the storage bulb area   

<html><body><table><tr><td>Various types of coil</td><td>Difference between maximum and minimum in the storage bulb area</td><td>Maximum in the storage bulb area</td><td>Difference between maximum and minimum in the storage bulb area/Maximum in the storage bulb area (%)</td></tr><tr><td>Straight solenoid</td><td>0.71E-02</td><td>6.71E-02</td><td>10.6%</td></tr><tr><td>Three-section coil</td><td>0.40E-02</td><td>5.90E-02</td><td>6.78%</td></tr><tr><td>Five-section coil</td><td>0.10E-02</td><td>5.06E-02</td><td>1.98%</td></tr><tr><td>Seven-section coil</td><td>0.06E-02</td><td>4.66E-02</td><td>1.29%</td></tr><tr><td>Nine-section coil</td><td>0.04E-02</td><td>4.60E-02</td><td>0.87%</td></tr></table></body></html>

![](images/e398af98750f66d6a28181459e952d7c2abbcb7e2ada3c53d0c2680843e6858f.jpg)  
(b)九段线圈在储存泡区域中心轴线上的磁场均匀度对比

# 2原子跃迁信号对比

按照仿真软件给出的较优的九段线圈设计参数，绕制了实际的C场线圈并应用于星载氢原子钟，如图4。在保持其他实验条件不变的情况下，实际测量了九段线圈作用下的氢原子（0-0）跃迁的信号幅度，并与直螺线管进行对比，从而判断磁场均匀度对信号的提升作用。

在实验过程中，磁屏蔽系统已使用大电流退磁，处于已退磁状态。谐振腔的微波输入功率为-90dBm，微波腔谐振频率调节至原子跃迁频率附近， $1 4 2 0 . 4 0 5 7 5 1 \mathrm { M H z } \pm 5 \mathrm { K H z }$ ，两个线圈产生的C场大小均约为lmGauss。直螺线管线圈作用下的氢原子（0-0)跃迁信号增益为2.9751dB。九段线圈作用下的氢原子（0-0）跃迁信号增益为3.2901dB。九段线圈信号增益较直螺线管增加0.3150dB，提升效果明显，两者对比图见(a) (b)

![](images/3181f56465ceeab7b815278fff9f37b0244d89a080cad37ba473686b8e356a83.jpg)  
图4九段线圈实物图  
Fig.4 The engineering model of nine-section coil   
图5。  
图5(a)直螺线管作为C场后的氢原子（0-0）跃迁信号增益对比  
Fig.5Cmparisonofignalginofhdrogenatom(O-)transitionbetwenstraightsolenoid(a)andnine-sectioncoil(b)usingforCfield

;(b)九段线圈作为C场后的氢原子（0-0）跃迁信号增益对比

# 3频率稳定度性能对比

完成直螺线管和九段线圈各自作为C场的原子跃迁信号幅度测试对比后，联合电路部分进行了闭环测试。保持其他参量不变，将C场线圈作为唯一可变参量，测试两者对星载氢钟频率稳定度性能指标的影响。

每次频率稳定度测试时间均为72小时，阿伦方差测试对比数据见表2和图6。从表2和图6可以看出，在1S-1000S 短稳中，应用九段线圈后的星载氢原子钟具有更高的频率稳定度指标，且在 $1 0 \mathrm { S } \mathrm { \sim } 1 0 0 0 \mathrm { S }$ 表现更为明显。在 10000S 长稳时，九段线圈的性能数据稍好一点，由于极易受到温度波动和频率漂移(FreqDrift/Day $\approx$ 1E-14)等众多因素的影响，以及实验测量环境的限制，暂未得出九段线圈性能明显更优的数据。

表2直螺线管和九段线圈作为C场后的阿伦方差对比测试 Table2 The comparison of Allan deviation between straight solenoid and nine-section coil using for C field   

<html><body><table><tr><td>Averaging Time</td><td>Allan Deviation(straight solenoid)</td><td>Allan Deviation(nine-section coil)</td></tr><tr><td>1</td><td>8.13E-13</td><td>8.00E-13</td></tr><tr><td>2</td><td>7.31E-13</td><td>6.99E-13</td></tr><tr><td>4</td><td>5.79E-13</td><td>5.32E-13</td></tr><tr><td>10</td><td>3.51E-13</td><td>3.20E-13</td></tr><tr><td>20</td><td>2.35E-13</td><td>2.21E-13</td></tr></table></body></html>

<html><body><table><tr><td>40</td><td>1.64E-13</td></tr><tr><td>100</td><td>1.01E-13 9.32E-14</td></tr><tr><td>200</td><td>7.15E-14 6.77E-14</td></tr><tr><td>400</td><td>4.95E-14</td></tr><tr><td>1000</td><td>3.18E-14</td></tr><tr><td>2000</td><td>1.96E-14</td></tr><tr><td>4000</td><td>1.73E-14</td></tr><tr><td>10000</td><td>1.25E-14 1.16E-14</td></tr></table></body></html>

![](images/6dda92b8d12db3f4a2878828871cac6bfbf967d26d8973d8dec8acbaa0d85e6b.jpg)  
图6直螺线管和九段线圈作为C场后的阿伦方差对比测试  
Fig.6 The comparison of Allan deviation between straight solenoid and nine-section coilusing for C field

# 4结论

腔泡系统是星载氢原子钟的核心组件，其微波填充因子 $\cdot \eta ^ { / }$ 反映了微波场与原子体系和C 场的耦合度。电极式腔泡系统储存泡区域内的微波场分布均匀，磁场强度波动小于 $1 \%$ ，因此，C场均匀度是影响氢原子（0-0）跃迁谱线性能的重要因素。软件仿真表明，直螺线管的磁场非均匀度约为 $1 0 \%$ 。而九段线圈可以实现小于 $1 \%$ 的磁场非均匀度。实际工程应用表明，按照仿真设计优化参数绕制的九段线圈，可以有效提升星载氢原子钟腔泡系统的原子跃迁信号。整机性能阿伦方差频率对比表明，配置九段线圈的星载氢原子钟中短期稳定度性能表现更优。九段线圈在星载氢原子钟腔泡系统上的应用，可以在不增加机械结构和电路设计的复杂度的同时，提升星载氢原子钟腔泡系统的性能和整机稳定度指标，并已得到成功验证和应用。未来将对多段线圈长度段数和间距等参数继续探索，寻找静磁场-微波场耦合度更优越的腔泡系统配置方案。

# 参考文献

[1］葡玉亭，韩春好，王晓芳．利用原子钟实现地球时的相关研究[J]．天文研究与技术，2007，4(4):330-336.LIN Yu-ting，HAN Chun-hao，WANG Xiao-fang.The Conception Definition and Realization of TT[J]．.Astronomical Research & Technology，2007，4(4) :330-336.   
[2]钦伟瑾，葛玉龙，杨旭海．伽利略星载被动型氢原子钟性能评估[J]．仪器仪表学报，2018(10)．Qin Weijin，Ge Yulong，Yang Xuhai. Performance evaluation of Galileoon-board passive hydrogen maser[J]. Chinese Journal of Scientific Instrument，2018(10).   
[3] Verification and optimizationof the physics parameters of the onboard Galileo Passive Hydrogen Maser,Wang, Qinghua （Temex Time，Vauseyon 29,2000 Neuch&#226;tel，Switzerland)； Mosset，Pierre；Droz,Fabien； Rochat, Pascal;Busca, Giovanni Source:38th Annual Precise Time and Time Interval (PTTI） Systems and Applications Meeting 2006，p 81-93   
[4]尼古拉·德米朵夫．氢钟开发技术和展望[J]．宇航计测技术(z1):6-14,26．Nikola $\cdot$ Demidov. The Development and Future of Hydrogen Maser Clock Technology[J].Journalof Astronautic Metrology and Measurement(z1):6-14,26.   
[5］王义遒主编，量子频标原理[M]，北京：科学出版社，1986,7．Wang Yiqiu,The principle of Quantum Frequency Standards [M]，Beijing:China Science Publishing，1986.7;   
[6]Vanier J，Audoin C，TheQuantum Physics of Atomic Frequency Standards lMl，Adam Hilger，Bristol and Philadelphia,1989   
[7] YonghuiX,Jiayua D，Wenxing C，et al． Development of passive hydrogen maser in Shanghai Astronomical Observatory[C]// Eftf- European Frequency & Time Forum. IEEE，2010.   
[8]李锡瑞．氢原子钟辅助电子学系统电路设计改进[J]．天文研究与技术，2015(03):62-66．Li Xirui．A Design of Improved Circuits of the Auxiliary Electronic System of a Hydrogen Maser[J]．Astronomical Research & Technology，2015(03) :62-66.   
[9］徐游编著，电磁学[M]，北京：科学出版社，2008.8.Xu You，Electromagnetism［M]．Beijing：China Science Publishing，2008.8;   
[10]高静,孙鑫,刘俊伟.亥姆霍兹线圈磁场空间分布的研究[J].科技通报,2018,34(07):34-37.Gaojing，Sun xin，Liu junwei，Research on the Spatial Distribution of Helmholtz Coil Magnetic Field[J],Bulletin of Science and Technology,2018,34(07) :34-37.   
[11]叶邦角编著，电磁学[M]，合肥：中国科学技术大学出版社，2014.8.Ye Bangjiao，Electromagnetism[M]．Hefei: University of Science and Technology of China Press，2014.8；   
[12]宋新昌，亥姆霍兹线圈及麦克斯韦线圈磁场分布及均匀性比较[J]，磁性材料及器件，2016,47(5)，P16-18,P77.Song Xinchang，Comparison of Magnetic Field Distribution and Homogeneity between Helmholtz coil and Maxwell coil [J]，Journal of Magnetic Materials and Devices，2016,47(5)，Pl6-18,P77;   
[13]张伟．高均匀度磁场线圈的设计[J]．计量学报，2010,31(5):404-407.Zhang Wei，The Designof Magnetic Coil with High Homogeneity[J]，Acta MetrologicaSinica，2010，31(5):404-407.   
[14]王勇，邱实，李建清．被动型氢钟超均匀C场的计算与优化［J]．哈尔滨工程大学学报，2013(6).WANGYong,QIU Shi, LI Jianqing，Calculation and optimization of ultra-uniform C-field for a [14] passive hydrogen clock[J], Journal of Harbin Engineering University， 2013(6).   
[15]张立根,王惠安.计算轴对称场的一种方法[J].大学物理,1989(03):29-44.   
[16] David Halliday，Robert Resnick，Jearl Walker.Fundamentals of physics[M].9th Ed.Hoboken:Wiley,2010: 937-978.   
[17]Jian Wang，Shouxian She,Sijiong Zhang.An improved Helmholtz coil and analysis of its magnetic field homogeneity[J].Review of Scientific Instruments，2002，73(5):2175-2179   
[18]JULIAN VRBANCICH,Magnetic field distributionwithinuniformcurrent densitycoils of non-zero cross-section and the design of Helmholtz coils[M]，DSTO Materials Research Laboratory，1991   
[19] Abbott，Jake J.Parametric designof tri-axial nested Helmholtz coils[J].Reviewof Scientific Instruments, 2015，86(5) :054701.   
[20] Cacak,R. K.Magnetic Field Uniformity around Near-Helmholtz Coil Configurations[J]. Review of Scientific Instruments，1969，40(11) :1468.

# Simulation and Application of Multi-section Coil for C Field

# Used in SpacePassive Hydrogen Maser

Pan Zhibing1, ²Xie Yonghui'Shuai Tao'Chen Pengfeil Pei Yuxianl Pan Xiaoyanl Zhan Yang1 Lin Chuanful (1.Shanghai Astronomical Observatory, Chinese Academy of Sciences,Shanghai 2Ooo3o, China;

Abstract:Space passive hydrogen maser (SPHM) has the advantages of high frequency stability and low frequency drift. It has been widely used in the navigation systems and frequency calibration.The quantum transition of hydrogen atoms and its signal detection is realized in thecavity-bulbassembleof the spaceborne hydrogen atomic clock. Atomic transition signal amplitude of SPHM directly determines the system signal to noise ratio,and thus affct system performance,which makes cavity-bulb assemble one of the most important parts of SPHM.Straight solenoid is widely used incavity-bulb asemble of SPHM to generate the constant magnetic field(C field） for atomic transition.Duetostructural restriction of physical package，there is improvement potential for homogeneityofC field.This paper discusses the feasibility of use of multi-section coil forgeneratingthe C field inSPHM.Firstly,the magnetic field generated by multi-sectioncoils is theoretically analyzed and calculated.Thensimulation and optimization of the parameters of the multi-section coil is carried out by ANSYS electromagnetic simulation software,including each length，number of sections，spacing,turns, diameterand total length.Design of multi-section coil with beter homogeneity for the Cfield can be given by he simulation software. Inhomogeneity of about $2 \%$ of the C field is realized comparing to about $10 \%$ of the straight solenoid.According to the optimization results,the experimental nine-section coilwas manufactured. The testing and comparison of atomic transition signal gainwithdifident C fieldwere carried out. Meanwhile, the closed-loop test was done in combination with the electronic package,and frequency stability of SPHMwas measured and compared. Experimental results show that atomic transition signal gain can be efectively increased with use of multi-section coil,and frequency stabilityis beter in the middleand short-term stability(1s-1Ooos)，which is beneficial to further performance improvement of SPHM.

Key words:space pasive hydrogen maser;cavity-bulb assemble;cfield; multi-section coil; homogeneous magnetic field;atomic transition signal gain; frequency stability;