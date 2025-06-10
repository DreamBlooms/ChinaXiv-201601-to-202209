# 卫星导航信号稳定性分析方法研究

赵丹宁1,2

(1.中国科学院国家授时中心，陕西 西安710600；2．中国科学院大学，北京100049)

摘要：全球卫星导航系统空间信号分析是系统设计阶段与运行过程中的一项重要工作。首先给出了基于全球卫星导航系统监测接收机观测量的空间信号稳定性分析方法，然后通过数字仿真实验证实了方法的可用性，最后以北斗系统地球同步轨道卫星的实测伪距数据为例，从原始伪距观测数据、伪距拟合残差与伪距拟合残差标准差3方面对信号稳定性进行了分析，实验结果进一步验证了本文方法的可行性与有效性。方法对于保障卫星导航信号的连续性与可靠性具有一定意义。

关键词：全球卫星导航系统；信号质量分析；稳定性；伪距中图分类号：P228.4 文献标识码：A 文章编号：1672-7673(2017)03-0330-07

随着卫星导航技术的发展，世界各大国相继建设了各自的全球卫星导航系统（Global NavigationSatellite System，GNSS)或区域卫星导航系统，例如美国全球定位系统、俄罗斯GLONASS、欧盟伽利略、中国北斗系统。全球卫星导航系统的空间信号质量不仅直接影响着卫星导航系统定位、导航和授时（Positioning，Navigationand Timing，PNT)的性能，而且能够反映卫星有效载荷的在轨状态与各种电性能指标，因此，全球卫星导航系统空间信号质量是衡量卫星导航系统优劣的一个重要指标，相应的信号质量评估技术可以为信号设计、信号在轨测试以及信号在轨监测提供重要支撑，从而为系统故障诊断和空间信号完好性监测等提供重要保障[1]。

由于全球卫星导航系统空间信号评估是系统设计阶段与运行过程中的一项重要工作，因而引起了各国的高度重视，也是当前卫星导航领域的一个研究热点。目前，全球定位系统、北斗系统和伽利略等卫星导航系统均建立了配套的空间信号质量监测和分析系统，如全球定位系统由美国斯坦福国际研究院建立了导航信号监测和特性分析系统，该系统利用 $4 7 \mathrm { ~ m ~ }$ 大口径抛物面天线对全球定位系统空间信号进行全天候实时监测[2]；伽利略由欧洲空间技术研究中心导航实验室建设了导航信号特性分析系统，该系统由全向天线、标准测量仪器和测试接收机等设备组成[3」；北斗系统由中国科学院国家授时中心搭建了全球卫星导航系统空间信号分析平台，以标准测量仪器分析、离线数据评估与监测接收机3种方式对包括北斗系统空间信号在内的多种全球卫星导航系统信号质量进行监测和评估[1,4]。

离线数据分析一方面根据基带信号分析卫星在短时期内的工作状态[5]，另一方面通过监测接收机测量数据对卫星的长期工作性能进行评估[6-7]。本文主要研究基于监测接收机观测量的卫星导航信号稳定性分析方法。

# 卫星导航信号构成

通过简要描述全球卫星导航系统发射的信号大致了解卫星导航信号的组成与特点。导航卫星发射的信号从结构上可分为测距码（伪随机码)、载波与数据码三个层次[8]。在卫星发射信号之前，先对数据码与测距码进行调制，然后再将调制信号和正弦波形式的载波混频，最后卫星把调制后的载波信号

发射出去。图1描述了导航卫星信号的基本构成。

在卫星信号接收终端，全球卫星导航系统接收机根据接收的卫星信号输出伪距（依据测距码相位测量得到的伪距也称作测码伪距）与载波相位（依据载波相位测量得到的伪距也称作测相伪距)两个基本观测量。下面介绍伪距和载波相位两个基本观测量的观测方程。

全球卫星导航系统接收机要实现定位、导航或者授时，必须准确测量卫星与接收机之间的距离。伪距和载波相位是接收机对观测卫星的两个

![](images/9ee53159b749f3aea9304c6b8efaf85a8f2fab8fd824dd2d270a80d240aa800f.jpg)  
图1导航卫星信号构成示意图  
Fig.1Diagram of composition of navigation satellite signals

基本距离观测量。伪距和载波相位一旦发生中断或者跳变，定位、导航和授时精度都不可避免地受到影响。伪距 $P$ 和载波相位 $L$ 的观测方程可分别表示为

$$
P = \rho _ { \mathrm { r } } ^ { \mathrm { s } } + c \big ( \delta t _ { \mathrm { r } } - \delta t ^ { \mathrm { s } } \big ) + T _ { \mathrm { r } } ^ { \mathrm { s } } + I _ { \mathrm { r } } ^ { \mathrm { s } } + \varepsilon _ { \mathrm { r , ~ P } } ^ { \mathrm { s } } ,
$$

$$
L = \rho _ { \mathrm { r } } ^ { \mathrm { s } } + c ( \delta t _ { \mathrm { r } } - \delta t ^ { \mathrm { s } } ) + T _ { \mathrm { r } } ^ { \mathrm { s } } - I _ { \mathrm { r } } ^ { \mathrm { s } } + \lambda N _ { \mathrm { r } } ^ { \mathrm { s } } + \varepsilon _ { \mathrm { r , \mathrm { ~ L ~ } } } ^ { \mathrm { s } } .
$$

其中， $\rho _ { _ { \mathrm { r } } } ^ { \mathrm { s } }$ 为卫星信号发射时刻的卫星位置到信号接收时刻的接收机位置的距离； $\delta t _ { \mathrm { r } }$ 和 $\delta t ^ { \mathrm { s } }$ 分别为接收机时钟钟差和卫星时钟钟差； $T _ { \mathrm { r } } ^ { \mathrm { s } }$ 和 $I _ { \mathrm { r } } ^ { \mathrm { s } }$ 分别为对流层折射误差和电离层折射误差； $ { N _ { \mathrm { r } } } ^ { \mathrm { s } }$ 为载波相位的整周模糊度； $\lambda$ 为信号波长； $\boldsymbol { \mathbf { \mathit { c } } }$ 为光在真空中的传播速度； $\varepsilon _ { \mathrm { r , P } } ^ { \mathrm { s } }$ 为伪距观测噪声和多路径效应误差之和;$\varepsilon _ { \mathrm { r , L } } ^ { \mathrm { s } }$ 为载波相位观测噪声和多路径效应误差之和。

# 2基于全球卫星导航系统接收机的信号稳定性分析方法

全球卫星导航系统空间信号的稳定性分析一般通过评估监测接收机输出的伪距与载波相位的稳定性实现。全球卫星导航系统信号稳定性分为短期稳定性(1天或几小时)和长期稳定性（一星期）。信号短期稳定性主要受接收机短暂失锁和接收机时钟钟跳等因素的影响，这些因素导致载波相位和伪距观测值突然产生跳变，然后又恢复正常，而信号长期稳定性主要与卫星时钟有关，如卫星钟频率漂移导致载波相位和伪距观测量出现缓慢变化，致使两个观测量整体产生漂移，这种现象反映了信号的长期稳定性[9。本节介绍全球卫星导航系统信号稳定性的分析方法，为评估载波相位和伪距测量值的稳定性，主要分析二者的曲线拟合残差。首先利用一段时长的载波相位或伪距测量值，对其进行多项式拟合，然后获得多项式拟合残差。多项式拟合依据最小二乘原理对原始观测数据进行拟合，使得原始观测数据和拟合曲线之间具有最小的差值。具体实现方法为，给定观测数据 $( x _ { i } , y _ { i } ) ( i = 1 , 2 , \cdots ,$ （20号$m$ )，寻找 $n$ 阶多项式 $f _ { n } ( x )$ ，使得拟合误差 $r _ { i } = y _ { i } - f _ { n } ( x _ { i } ) ( i { = } 1 , 2 , \cdots , m )$ 的平方和最小，即

$$
E = \sum _ { i = 1 } ^ { m } \left[ y _ { i } = f _ { n } ( x _ { i } ) \right] ^ { 2 } = \sum _ { i = 1 } ^ { m } \left[ \sum _ { j = 1 } ^ { n } a _ { j } x _ { i } ^ { j } - y _ { i } \right] ^ { 2 } = \operatorname* { m i n } ,
$$

满足(3)式的 $f _ { n } ( x ) = \sum _ { j = 1 } ^ { n } a _ { j } x ^ { j }$ 称作最小二乘拟合多项式，其中 $a _ { j } ( j = 1 , 2 , \cdots , n )$ 为多项式拟合参数。从几何角度而言，最小二乘拟合的目的是寻找与给定点 $\left( x _ { i } , y _ { i } \right) \left( i { = } 1 , 2 , \cdots , n \right)$ 距离平方和最小的曲线$y _ { i } = f _ { n } ( x _ { i } ) ( i = 1 , 2 , \cdots , m )$ ，而 $r _ { i } = y _ { i } - f _ { n } ( x _ { i } ) ( i { = } 1 , 2 , \cdots , m )$ 被称作拟合残差。对于载波相位和伪距拟合而言，电离层折射误差和对流层折射等缓慢变化误差已经大体消除，因此拟合残差能够较好地反应多项式拟合的好坏。实际上，根据最小二乘原理获得的最终拟合结果可以充分消除观测数据中的系统误差，同时也能在一定程度上削弱随机误差的影响，因此得到的拟合结果具有较高的可靠性。

根据多项式拟合残差的变化情况评估载波相位和伪距测量值的稳定性，基本步骤如下：

(1)读取全球卫星导航系统监测接收机的原始观测数据，包括载波相位观测值和伪距观测值;  
(2)绘制载波相位观测值和伪距观测值曲线图，根据曲线图判断观测数据中是否存在跳变点;  
（3)截取一定时长的连续观测数据进行多项式拟合，获得多项式拟合残差；

(4)根据多项式拟合残差的变化范围分析观测值的稳定情况

图2为分析载波相位和伪距观测量稳定性的算法流程图。

# 3数字仿真

# 3.1方法的可行性验证

1天的原始伪距和载波相位观测数据的曲线图近似正弦或余弦函数（可以参见第4节给出的原始伪距测量曲线）。为不失一般性，首先产生一个周期 $( 0 \sim 2 \pi )$ 的叠加高斯白噪声的余弦函数以仿真伪距观测值，总共629个数据点，如图3，然后分别截取 $0 \sim 0 . 6 \pi$ 与 $0 . 7 \ : \pi \sim 1 . 3 \ : \pi$ 这两段模拟数据进行拟合，这两段数据均包含拐点。表1列出了叠加不同高斯白噪声情况下的多项式拟合残差标准差，记为 $\sigma _ { 2 }$ ，同时表1也给出了未叠加高斯白噪声时的拟合残差标准差，记为 $\sigma _ { 1 }$ 。

表1多项式拟合残差标准差  
Table 1 Standard deviation of polynomial fitting residuals   

<html><body><table><tr><td>高斯</td><td colspan="2">0</td><td colspan="2">02</td></tr><tr><td>白噪声</td><td>0~0.6</td><td>0.7~1.3</td><td>0~0.6</td><td>0.7~1.3</td></tr><tr><td>标准差</td><td>T</td><td>T</td><td>T</td><td>T</td></tr><tr><td>0.020</td><td>0. 001</td><td>0.002</td><td>0.024</td><td>0.020</td></tr><tr><td>0. 040</td><td>0. 001</td><td>0.002</td><td>0. 044</td><td>0. 040</td></tr><tr><td>0. 050</td><td>0. 001</td><td>0.002</td><td>0.053</td><td>0. 050</td></tr></table></body></html>

从表1可以看到，对于未叠加高斯白噪声的数据拟合，多项式拟合残差标准差 $\sigma _ { 1 }$ 均比较低,接近于0，这说明运用多项式拟合方法获得的拟合结果与原始观测值之间符合得较好。以未叠加

![](images/41e91c17a616d1c28c86be9826b47df691cf78446d08c9c75db511847d6d0fd3.jpg)  
图2基于全球卫星导航系统接收机的伪距和载波相位稳定性分析流程图

![](images/9b802cc5d0f662f577bdb8daa4d3ba94765b3cf2c71befeb0cd900a475feebc3.jpg)  
Fig.2Flowchart of the method for analyzing the stability of pseudo-range and carrier-phase   
图3叠加高斯白噪声(标准差为0.020)的余弦曲线Fig.3Cosine function with White Gaussian Noise（WGN）（ $\sigma = 0 . 0 2 0$ ）

高斯白噪声的多项式拟合残差标准差为参考，向余弦函数中加入标准差分别为0.020、0.040和0.050的高斯白噪声，获得了含噪数据与拟合数据之间的拟合残差标准差 $\sigma _ { 2 }$ 。经过对比可以发现， $\sigma _ { 2 }$ 和高斯白噪声的标准差非常相近甚至相等，这进一步表明，多项式拟合方法对含噪数据的拟合结果与原始数据之间也具有很好的符合性，剩余的拟合残差一般是混杂在原始数据中的随机噪声成分。

为更加直观地显示多项式拟合结果，图4(a)和图4(b)分别绘出了 $0 \sim 0 . 6 \pi$ 与 $0 . 7 ~ \pi \sim 1 . 3 ~ \pi$ 两段含噪数据曲线和多项式拟合曲线之间的比较。从图4可以看出，多项式拟合方法在图4(a)和图4（b)曲线拐点处的拟合效果不佳，但是总体而言，图4(a)和图4(b)曲线的整体拟合残差较小，拟合残差标准差与叠加的高斯白噪声的标准差非常接近，可见曲线拐点对多项式拟合效果影响不大，所以在曲线拐点处，多项式拟合仍然有效。

# 3.2观测异常仿真

利用数字仿真分析观测数据异常条件下的多项式拟合效果，包括卫星时钟钟跳等导致的测量数据跳变、接收机失锁等因素造成的观测数据缺失。首先采用 $0 \sim 2 \ \pi$ 一个周期的含噪余弦曲线仿真1天的载波相位或伪距观测数据，总共6284个数据点。然后分别在 $0 . \ 1 3 \ \pi \sim 0 . \ 1 5 \ \pi$ 段和 $0 . 7 6 \pi$ 点模拟接收机失锁等引起的数据缺失和卫星时钟钟跳等引起的数据跳变异常，其中数据缺失点为30个，如图5。最后以392个数据为间隔将6284个数据点分为16段，计算在不同噪声条件下每段数据的多项式拟合残差标准差，限于篇幅，图6仅绘出了高斯白噪声标准差为0.050时的拟合残差标准差，表2统计了两种观测异常情况下的拟合残差标准差与其均值之差。

![](images/9d69162c88051cf466256eba8b200916573c3d12a3b61537b7fa5a63c9275f19.jpg)  
Fig.4Comparison between the polynomial fitting and original time-series

![](images/dd24d1f4c1bc2a0eb7602aeadc1f5711bfe24d4e904555a38b38d9f4275b2da1.jpg)  
图4多项式拟合曲线与原始曲线对比

![](images/b4d357ae42afb89694934a9c1684d1d0e4c1cb87a2a5a4d146bb5a24e3d6bad7.jpg)  
图5观测数据异常仿真曲线(高斯白噪声标准差为0.050)Fig.5Simulated observational anomaly with WhiteGaussian Noise（WGN）（ $\sigma = 0 . 0 5 0$ ）  
图6高斯白噪声标准差为0.050时的拟合残差标准差Fig.6Standard deviation of fitting residuals with WhiteGaussian Noise（WGN）( $\sigma = 0 . 0 5 0$ ）

从图6和表2可以发现，观测数据产生缺失和跳变异常现象时，多项式拟合残差标准差较大，这说明当载波相位或伪距出现观测异常时，基于多项式拟合的信号评估方法失效，因此必须截取正常的观测数据进行信号评估。

# 4 工程实例

根据信号稳定性评估方法，对北斗系统G02

# 表2观测异常情况下多项式拟合结果

Table 2Statistics of polynomial fitting in presence of observational anomaly   

<html><body><table><tr><td>高斯白噪声 标准差</td><td>拟合残差 标准差均值</td><td>差值 （数据缺失)</td><td>差值 （数据跳变）</td></tr><tr><td>0.020</td><td>0.048</td><td>0.176</td><td>0.205</td></tr><tr><td>0. 040</td><td>0. 065</td><td>0.161</td><td>0.188</td></tr><tr><td>0. 050</td><td>0. 074</td><td>0. 154</td><td>0.184</td></tr></table></body></html>

地球同步轨道卫星B2频点I支路 2015年3月6日1天的伪距测量数据进行稳定性分析评估，监测接收机输出数据的采样间隔为 $3 0 ~ \mathrm { s }$ ，连续记录2880个观测值。

图7(a)和图7(b)分别绘出了 $0 0 \colon 0 0 \sim 2 4 \colon 0 0 \ 2 4 \mathrm { h }$ 原始伪距观测值曲线及其多项式拟合残差曲线。由图7(a)可以看出，该地球同步轨道卫星的伪距观测曲线平滑，没有发生数据缺失和数据跳变等异常。从图7(b)可以发现，伪距多项式拟合残差曲线在0附近波动，并且在一定范围内变化。由图7(b)还可以发现，相对而言， $0 6 \colon 0 0 \sim 0 9 \colon 0 0$ 时段的多项式拟合残差曲线不如其它时段的拟合残差曲线变化平稳。表3列出了以 $^ 3 \mathrm { ~ h ~ }$ 为一个时段划分的1天的伪距拟合残差标准差及其与标准差均值之差。从表3可以看出，除 $0 6 \colon 0 0 \sim 0 9 \colon 0 0$ 时段外，其它时段的伪距拟合残差标准差相对于标准差均值之差的绝对值均小于 $0 . 1 0 0 \mathrm { ~ m ~ }$ ， $0 6 \colon 0 0 \sim 0 9 \colon 0 0$ 时段的标准差最大，为 $0 . 4 3 4 \mathrm { ~ m ~ }$ ，与标准差均值的偏差为$0 . 1 8 3 \mathrm { ~ m ~ }$ ，与标准差均值差值最小的时段为 $1 2 : 0 0 \sim 1 5 : 0 0$ ，其标准差为 $0 . 2 1 8 \mathrm { ~ m ~ }$ ，偏差值为 $- 0 . 0 3 3 \mathrm { ~ m ~ }$ 。

![](images/08202277f2bbbccda373f681c6f1bb4e4ec08076d3b18de512282f9343f3fb7c.jpg)  
图7伪距原始观测值及其多项式拟合残差  
Fig.7Original pseudo-range measurements and its polynomial fitting residuals

06: $0 0 \sim 0 9 \colon 0 0$ 时段的伪距拟合残差相对于其它时段残差较大的原因在于， $0 6 \colon 0 0 \sim 0 9$ ： 00时段的伪距观测值正好位于 $2 4 \mathrm { ~ h ~ }$ 伪距观测曲线的拐点处。曲线拐点位置的拟合效果一般没有其它时段的拟合效果好，但是曲线拐点处的拟合不会给整体数据的拟合结果带来影响，故多项式拟合结果是可信和可用的，这从表3最后一行给出的标准差均值也可以看出，06： $0 0 \sim 0 9$ ：00时段的拟合没有影响整体数据的拟合结果，并且与3.2节观测异常的模拟结果相比，该时段的伪距拟合残差标准差要比伪距发生观测异常时的拟合残差标准差小很多。因而可以认为， $0 6 \colon 0 0 \sim$ 09：00时段的拟合残差表现较大的现象与拟合时段划分有关，而不是由信号稳定性起伏引起的。

表3伪距多项式拟合残差标准差统计结果  
Table 3Statistics of polynomial fitting residuals   

<html><body><table><tr><td>时段</td><td>拟合残差标 准差/m</td><td>与标准差均 值之差/m</td></tr><tr><td>00:00~03:00</td><td>0. 193</td><td>-0. 058</td></tr><tr><td>03:00~06:00</td><td>0. 299</td><td>0. 048</td></tr><tr><td>06: 00~09: 00</td><td>0. 434</td><td>0.183</td></tr><tr><td>09:00~12:00</td><td>0.298</td><td>0. 047</td></tr><tr><td>12:00~15:00</td><td>0.218</td><td>-0.033</td></tr><tr><td>15:00~18:00</td><td>0.203</td><td>-0. 048</td></tr><tr><td>18:00~21:00</td><td>0. 154</td><td>-0. 097</td></tr><tr><td>21: 00~24: 00</td><td>0. 212</td><td>-0. 039</td></tr><tr><td>均值</td><td>0. 251</td><td>0.000</td></tr></table></body></html>

为了进一步分析 $0 6 \colon 0 0 \sim 0 9 \colon 0 0$ 时段的伪距拟合残差结果，对残差统计特性进行讨论。多项式拟合残差主要包含混杂在原始数据中的随机噪声成分，换言之，伪距拟合残差通常是由观测噪声产生的随机波动，理论上应该服从零均值的高斯分布，然而由(1)式可知，卫星信号在空间传播过程中受到对流层和电离层折射误差等多种因素的影响，从而导致总体方差和总体均值产生变化，若想知道总体方差和总体均值的变化情况，需要对两个高斯分布总体方差比或总体均值差进行估计。这里仅估计两

个高斯分布总体均值差。

选取 $0 6 \colon 0 0 \sim 0 9 \colon 0 0$ 和 $1 5 \colon 0 0 \sim 1 8 \colon 0 0$ 两个时段的多项式拟合残差值(概率分布如图8)作为两个总体（方差和均值等参数见表4），估计两个总体均值差的一个置信度为 $1 - \alpha$ 的置信区间[10],$\theta _ { { \scriptscriptstyle d } } = \mu _ { { \scriptscriptstyle 1 } } - \mu _ { { \scriptscriptstyle 2 } } \pm Z _ { { \scriptscriptstyle \alpha } \ o \gamma } \sqrt { \frac { \sigma _ { { \scriptscriptstyle 1 } } ^ { 2 } } { n _ { { \scriptscriptstyle 1 } } } + \frac { \sigma _ { { \scriptscriptstyle 1 } } ^ { 2 } } { n _ { { \scriptscriptstyle 1 } } } }$ ，其中，Z2表示标准高斯分布的上α/2分位点，本文取α=0.05。经计算获得两个总体均值差的 $9 5 \%$ 置信区间为[-0.358，0.237]。因为此置信区间包括0，因而可以判断这两个时段伪距拟合残差的均值没有显著差别。

![](images/4ba2cf219c1851c7cd876303c9ca676237fe72bcfb795839472c228cfce02acd.jpg)  
图8伪距多项式拟合残差概率分布  
Fig.8Probability distribution of polynomial fiting residuals

# 5结束语

为了分析卫星导航信号的稳定性，以最小二乘拟合原理为基础，通过对监测接收机的载波相位和伪距测量数据进行评估，实现了对全球卫星导航系统空间信号稳定性的分析。数字仿真结果表明，多项式拟合方法在曲线拐点处的拟合效果

表4伪距多项式拟合残差统计参数  
Table 4Statistic parameters of polynomial fitting residuals of pseudo-range   

<html><body><table><tr><td>高斯总体</td><td>样本数</td><td>总体均值</td><td>总体方差</td></tr><tr><td>06: 00~09: 00</td><td>n =10</td><td>μ= 0.040</td><td>σ² = 0. 189</td></tr><tr><td>15: 00~18:00</td><td>n=10</td><td>μ2=0.021</td><td>σ² =0.041</td></tr></table></body></html>

不如曲线其它处，但曲线拐点处的拟合不会影响整体数据的拟合结果。当载波相位或伪距观测量因接收机失锁等因素出现数据缺失或因卫星时钟等因素引起数据跳变观测异常时，多项式拟合法不再适用，因而必须选取正常观测数据进行分析。通过对北斗系统地球同步轨道卫星伪距实测数据的评估可以发现，该卫星发射的I支路信号在1天内是稳定的。由于多项式拟合方法具有一定的局限性，给信号评估结果带来一定的影响，因此如何对拟合方法进行改进是下一步的研究重点。此外，如何根据卫星信号的变化趋势进行信号的长期稳定性评估也是未来研究的关注点。

# 参考文献：

[1] 卢晓春，周鸿伟.GNSS 空间信号质量分析方法研究［J]．中国科学：物理学 力学 天文学，2010，40(5): 528-533.Lu Xiaochun， Zhou Hongwei. Methods of analysis for GNSS signal quality [J]. Scientic Sinica:Physica，Mechanica & Astronomica，2010，40(5）:528-533.  
[2] Christie JR I,Bentley P B,Ciboci JW,et al. GPS signal quality monitoring system [C]//Proceedings of the 17th International Technical Meeting of the Satellite Division of the IONGNSS，2004:2239-2245.  
[3] Spelat M，Hollreiser M，Crisci M，et al.GIOVE-A signal in space test activity at ESTEC[C]//Proceedings of the 19th International Technical Meeting of the Satellite Division of theION GNSS，2016:981-993.  
[4] 贺成艳.GNSS 空间信号质量评估方法研究及测距性能影响分析［D]．西安：中国科学院国家授时中心，2013.He Chengyan. Research on evaluation methods of GNSS signal quality and the influence of GNSSsignal on ranging performance [D]. Xi'an: National Time Service Center， Chinese Academy ofScience，2013s.  
[5] 余宜珂，王萌.基于CAPS系统的信号调制方式的比较研究［J]．天文研究与技术，2014,11(3) : 224-229.Yu Yike，Wang Meng. Comparative studies of signal-modulation methods based on the CAPS[J].Astronomical Research & Technology，2014，11（3）:224-229.  
[6] Soellner M，Kurzhals C，Hechenblaikner G,et al. GNSS offline signal quality assessment [C] //Proceedings of the 21st International Technical Meeting of the ION GNSS,2008 :909-920.  
[7] 石慧慧，卢晓春，饶永南.GNSS信号稳定性评估方法研究［J]．时间频率学报，2013，36(2):97-105.Shi Huihui，Lu Xiaochun，Rao Yongnan. Methods of evaluation for GNSS signal stability[J].Journal of Time and Frequency，2013，36(2）:97-105.  
[8] Jin S G.Global Navigation Satellite Systems: signal， theory and applications [M]. Croatia:InTech Publisher，2012：4.  
[9] 康四林，李语强.GPS 定位中的误差分析［J]．天文研究与技术—国家天文台台刊，2010，7(3):222-230.Kang Silin，Li Yuqiang. Error analysis of GPS positioning [J].Astronomical Research & Technology-Publications of National Astronomical Observatories of China，2010，7(3）：222-230.  
［10］曾五一，肖红叶.统计学导论［M].北京：科学出版社，2007.Zeng Wuyi，Xiao Hongye.Introduction to statistics [M]. Beijing:Scientific Press，2007.

# Study on Methods for Analyzing the Stability of Satellite Navigation Signals

Zhao Danning1,2 (1.National Time ServiceCenter,Chinese Academyof Sciences，Xi'an710600,China,Email:zhaodanning31@163.com; 2.University of Chinese Academy of Sciences，Beijing 1Ooo49,China)

Abstract:The quality assessment of GNSS（Global Navigation Satelite System） space signals plays an importantrole in the design and operation of the system.It is alsoan essential task in the integrity monitoring of space signals.In this paper,the methodology for evaluating GNSS space signals is first described in detail, which is based on pseudo-range or carier-phase observations from a GNSS monitoring receiver. Next，the feasibility of the presentedalgorithm isvalidated byusing a simulation experiment.Furthermore，an experiment on the real BDS pseudo-range measurements is carred out in order to validate the effctiveness of the developed method.The results show that the proposed scheme is highly potential to evaluate the quality of GNSS space signals according to the three metrics，namely original measurements，fiting residuals and standard deviation of fiting residuals. Therefore，the proposed evaluation technique can provide a guarantee and help for the continuity and reliability of GNSS space signals.

Key words:Global Navigation Satelite System （GNSS）；Analysis of the signal quality；Stability；Pseudo-range