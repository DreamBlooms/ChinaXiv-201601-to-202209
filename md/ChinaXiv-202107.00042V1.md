# 一种基于相位条纹的高精度码相位测量方法

孙文杰1²，王兆瑞1(1.中国科学院国家天文台,北京100101；2.中国科学院大学，天文与空间科学学院，北京100049)

摘要：GNSS（GlobalNavigation Satellite System，全球导航卫星系统）接收机在接收到卫星信号后，经过捕获、跟踪，得到码相位与载波相位两个基本的测量值。然后通过测量值计算卫星与接收机之间的距离。载波相位测量值比码相位测量值具有更高的测量精度，但由于载波相位测量值具有计算整周模糊度的问题,在实际的计算当中得到高精度的相位测量结果需要付出更多的计算代价。因此，在实际应用中，得到更高精度的码相位测量结果具有更实际的意义。本文在基于相位条纹的技术基础上，通过提取互相关功率谱，提出一种更高精度的码相位测量方法，得到更高精度的码相位测量值，从而得到更高精度的码伪距测量结果，并通过实际的GNSS的信号验证了本方法的有效性。

关键词：GNSS；相位条纹法；码相位

# 0引言

卫星导航接收机通常使用载波辅助的载波跟踪环和码跟踪环实现载波跟踪与码跟踪[1,2]。其中码跟踪环通常使用非相干延迟锁定环 DLL（Delayed Lock Loop）来实现，通过接收到的I、Q两路信号，分别产生超前、即时、滞后的6组信号，利用GNSS 伪随机码的自相关特性，用鉴相器计算出本地产生的码与接收到的码的相位差；在获得相位差的同时，将鉴相结果输入给数字控制振荡器 NCO（Numerically Controlled Oscillator)），调节本地产生的伪码的相位，使之与输入的码的相位进行对齐，完成码跟踪。同时也得到码相位测量值，可以用于计算伪距。以GPS（GlobalPositioning System）为例，GPS 的码速率为 $1 . 0 2 3 \mathrm { M H z }$ ，一个码片的长度为 $2 9 3 \mathrm { m }$ ，码伪距测量误差约为一个码片长度的 $1 \%$ ，大约为3m 的误差。

为得到更高精度的码相位观测值，国内外许多学者尝试改善码环的结构或用其它的方法来提高码环的鉴相精度。国外学者在快速傅里叶变换的基础上提出内插的思想[3-4]，提取相关峰中的最高点与最低点，进行插值处理提取相位，其解决了傅里叶变换计算量大的问题，但是精度没有提高；国内学者在其基础上提出二次插值的方法来获取更精准的码相位测量结果[5-6]，结果表明在信号强的情况下有良好的表现；另外一些学者采用最小二乘法拟合的技术提高码相位测量精度，该方法相较于插值法有实现简单、精度高的特点，但其测量范围较小，仅适合码相位误差在一个采样点以内测量。在此基础上有学者提出基于整体最小二乘法的估计算法[8，虽然精度有所提高，但需要进行矩阵的奇异值分解等运算，运算量过大;深空探测中使用再生伪码来提高码相位测量精度[9-]，再生伪码信号的码相位估计依赖码元中存在显著的时钟分量，利用这一特性，依次实现码片时钟同步和码相位同步，两者实质上分别对应小数位和整数位的码相位值，但目前没有应用在GNSS 接收机中；GNSS 接收机中提高码跟踪环相位的精度方式主要还是在环路的参数设置与选取上[12-13]，通过设置自适应变化环路带宽，实时调整环路的参数，来提高跟踪环路精度。还有研究提出使用卡尔曼滤波跟踪环代替传统码相位跟踪环[14-16]，其提高了环路的跟踪性能与动态范围，降低了码相位误差与抖动，但是计算量过大不易于实际应用；文献[16]提出了使用相位条纹对码相位进行测量的方法，结果表明相位条纹法对比与传统GPS 接收机中鉴相精度有所提高，但是由于是使用仿真数据进行模拟，缺乏实际测量数据的验证。

针对以上问题，本文在文献[16]的基础上引入实际的GPS 信号，针对伪码信号的互相关功率谱，对传统的跟踪环进行改进，提出一种高精度的码相位测量方法。

# 1相位条纹法测量码相位

# 1.1相位条纹法基本原理

相位条纹方法通常用于测量两台接收机之间的距离，同一信号经不同路径到达两台接收机后，通过相关计算得到相位差，从而计算出到达时间差t，乘以光速得到两台接收机的距离。设两个接收机接收到的信号分别为 $f _ { 1 } ( t )$ 和 $f _ { 2 } ( t )$ ，其中 $f _ { 2 } ( t ) = f _ { 1 } ( t - \tau )$ ， $\tau$ 为信号到达两台接收机之间的时延。对两路时域的信号做傅里叶变换，并进行互相关计算，得到的互相关功率谱为：

$$
S _ { 1 2 } ( \omega ) = F _ { 1 } ( \omega ) \cdot F _ { 2 } ^ { * } ( \omega ) { = } F _ { 1 } ^ { 2 } ( \omega ) e ^ { j \omega \tau }
$$

互相关功率谱的相位：

$$
\scriptstyle \phi = \omega \tau = 2 \pi \tau \cdot f
$$

可以看出，在两个接收机的时延 $\tau$ 一定的情况下，互功率谱相位 $\phi$ 与信号的频率 $f$ 为线性关系，斜率为 $2 \pi \tau$ 。通常相位 $\phi$ 的取值范围为 $[ - \pi , \pi ]$ ，将 $\scriptstyle \phi \sim f$ 斜线按照 $[ - \pi , \pi ]$ 的范围切割成周期性的条纹，条纹之间的间隔为 $T _ { \mathrm { 0 } }$ ，其中：

$$
T _ { _ 0 } = \frac { 2 \pi } { 2 \pi \tau } = \frac { 1 } { \tau }
$$

而条纹出现的频率 $f _ { 0 }$ ：

$$
f _ { 0 } = \frac { 1 } { T _ { 0 } }
$$

即通过统计条纹出现的频率，可得到信号的时延。

![](images/3951e62dc3a1811cb211bffcd598a37342631b09890b14436aba2445a087278a.jpg)  
图1．相位条纹示例  
Fig.1 Phase strip example

# 1.2相位条纹法测量接收机码相位

在GNSS 接收机当中，接收的信号经过下变频剥离载波后得到基带信号，基带信号与本地NCO 产生的伪码信号可以视作是两路相关的具有时延的信号。通过计算出其中的待测时延可以得到本地信号与接收到的信号的码相位差，从而得到更高精度的码相位测量值。接收机在

下变频后通常会得到I、Q两个正交的支路，选取I支路的即时信号剥离载波并与本地 NCO产生的码信号做相关运算，得到互相关功率谱，通过统计出现的相位条纹频率，测得接收信号的时延。

但由于接收到的导航信号的信噪比较低，直线拟合的效果较差，故首先对接收的信号与本地的信号进行时域上的分段叠加，提高信号的信噪比。对相位条纹曲线 $\phi ( f )$ 再做一次傅里叶变换，当条纹频率为 $f _ { 0 }$ ，条纹间隔 ${ T _ { 0 } } = 1 / \ f _ { 0 }$ ，单个条纹 $\phi _ { 1 } ( f )$ 可以表示为：

$$
\phi _ { 1 } ( f ) = f \times \left[ u \left( f + \frac { 1 } { 2 f _ { 0 } } \right) - u \left( f - \frac { 1 } { 2 f _ { 0 } } \right) \right]
$$

对 $\phi _ { 1 } ( f )$ 做傅里叶变换，其频谱中的幅度为：

$$
\left| \Phi _ { 1 } ( \psi ) \right| = 2 \times \left( \frac { \sin \frac { \psi } { 2 \pi } } { \psi ^ { 2 } } { - } \frac { \cos \displaystyle \frac { \psi } { 2 \pi } } { \psi } \right)
$$

因为条纹以 $T _ { \mathrm { 0 } }$ 为周期出现，周期性条纹的相位傅里叶变化为：

$$
\left| \Phi ( \psi ) \right| = 2 \times \sum _ { n = 1 } ^ { + \infty } \frac { \delta ( \psi - 2 \pi n f _ { 0 } ) } { n }
$$

由上式可知，相关条纹 $\phi ( f )$ 在进行傅里叶变化后得到的幅度谱 $\left| \Phi ( \psi ) \right|$ ，当式（8）中的 $\mathrm { n } { = } 1$ 时， $\left| \Phi ( \psi ) \right|$ 可得到最大值，此时 $\scriptstyle { \psi = 2 \pi f _ { 0 } }$ 。

另外，由于接收机在跟踪信号时，本地 NCO产生的伪码与接收到的伪码信号小于1个码片，时延 $\tau$ 较小，相位条纹的出现频率较低，为了更加明显的获得相位条纹，可以在本地接收信号时预先补偿一个时延 $\tau _ { 0 }$ ，令 $\tau _ { 0 } \gg \tau$ ，在整体时延变大以后可以获得频率条纹数量，有利于计算出更为精确的时延。在通过条纹频率计算出 $\tau _ { 0 } { + } \tau$ 以后，减去补偿时延 $\tau _ { 0 }$ ，最后得到待测时延 $\tau$ ，即可得到码相位测量值。

相位条纹法测量码相位流程如图所示：

![](images/01c43566da54f9cbd3909dd895f7ff507f6fa19e714e6d4c35cbde2c3ff6730f.jpg)  
图2.相位条纹图步骤  
Fig.2 Phase strip method steps

# 1.3相位条纹方法提高鉴相精度理论分析

克拉美罗下界CRLB（Cramer-Rao Lower Bound）用于计算无偏估计中能够获得的最佳估计精度，因此经常用于计算理论能达到的最佳估计精度，和评估参数估计方法的性能。下面通过分析相位条纹法中的CRLB。

信号经过下变频后的中频信号为：

$$
x ( n ) = A \cdot D ( t ) \cos [ 2 \pi f _ { _ { I F } } n + \tau ] + n _ { _ I }
$$

其中A为信号的幅值， $\tau$ 为待测码相位， $n _ { \scriptscriptstyle I }$ 为方差为 $\sigma$ 高斯白噪声，其余变量均为常量。

其似然函数为：

$$
p ( x ; \tau ) = \frac { 1 } { 2 \pi \sigma ^ { 2 } } \exp \left[ \frac { - \displaystyle \sum _ { n = 0 } ^ { N - 1 } [ x [ n ] - A \cos ( 2 \pi f _ { _ { I F } } n + \tau ) ] ^ { 2 } } { 2 \sigma ^ { 2 } } \right]
$$

求其对数一阶偏导，为：

$$
\frac { \hat { \sigma } \ln p ( x ; \tau ) } { \hat { \sigma } \phi } { = } \frac { - A } { { \sigma ^ { 2 } } } { \sum _ { n = 0 } ^ { N - 1 } } \bigl [ x [ n ] \sin ( 2 \pi f _ { I F } n + \tau ) - A \sin ( 4 \pi f _ { 0 } n + 2 \tau ) \bigr ] ^ { 2 }
$$

其二阶偏导为：

$$
\frac { \hat { \sigma } ^ { 2 } \ln p ( x ; \tau ) } { \hat { \sigma } \phi ^ { 2 } } = \frac { - A } { \sigma ^ { 2 } } { \sum _ { n = 0 } ^ { N - 1 } } \bigl [ x [ n ] \cos ( 2 \pi f _ { I F } n + \tau ) - A \cos ( 4 \pi f _ { 0 } n + 2 \tau ) \bigr ]
$$

二阶偏导的期望为：

$$
  - E \{ \frac { \partial ^ { 2 } \ln p ( x ; \tau ) } { \partial \phi ^ { 2 } } \} = \frac { A } { \sigma ^ { 2 } } \sum _ { n = 0 } ^ { N - 1 } \Bigl [ E \{ x [ n ] \} \cos ( 2 \pi f _ { I F } n + \tau ) - A \cos ( 4 \pi f _ { 0 } n + 2 \tau ) \Bigr ] \} \quad \mathrm { a n d } \quad \Omega .
$$

其中期望 $E \{ x [ n ] \} = A { \cos } ( 2 \pi f _ { _ { I F } } + \tau )$ ，上式期望化简得：

$$
 - E \{ \frac { \hat { \sigma } ^ { 2 } \ln p ( \boldsymbol { x } ; \tau ) } { \hat { \sigma } \phi ^ { 2 } } \} = \frac { A ^ { 2 } } { 2 \sigma ^ { 2 } } [ \sum _ { n = 0 } ^ { N - 1 } 1 - \sum _ { n = 0 } ^ { N - 1 } \cos ( 4 \pi f _ { 0 } n + 2 \tau ) ] \approx \frac { N A ^ { 2 } } { 2 \sigma ^ { 2 } } = N \times S N R
$$

其中N为信号长度，SNR为信号的信噪比。所以，中频信号的克劳美罗届CRLB为：

$$
\operatorname { v a r } \{ \tau \} \geq \frac { 1 } { N \times S N R }
$$

相位条纹方法在计算时通过时域叠加的方法提高了信号的信噪比，因此可以使克拉美罗界更低，提高估计精度。

# 2实际GNSS信号实验

本次实验采用数字采集卡采集的GPS信号来对上述方法进行验证。选用的GPS采集卡为NSL Stereo，其采样频率为 26M，中频载波频率为6.5MHz。对GPS 的 PRN32卫星数据进行采集，其中信号长度为100us，码速率为1.023MHz，设定的补偿时延 $\tau _ { 0 }$ 为600ns。后续的处理过程在Matlab上完成。中间的处理结果如图 $5 ^ { \sim }$ 图7所示：

![](images/f2e7522f8e6ae6a1733f9d09398a1645460efb963a0a44035be01dfe1b7208be.jpg)

![](images/4dca3feb8d8b9ce9b3364accd154e77ae2648f55b39ddc52714180922732a126.jpg)  
图3.采集的中频信号  
Fig3.IF signal collected   
图4.本地码与接收到的码互相关功率谱相位条纹 $\phi ( f )$   
图 5.对相位条纹进行傅里叶变化提取条纹频率 $\Phi ( \psi )$   
Fig.5 Perform Fourier transformation on phase strip to extract strip frequency $\Phi ( \psi )$

Fig4.Local code and received code cross-correlation power spectrum phase strip $\phi ( f )$

0.8 0.6   
0.4   
幅 Nt 0.2 0 1 2 3 4 5 频率 ×10-6

图5为采集的数据中截取的100us 的长度部分，通过对其混频处理后剥离中频载波，留下伪码信号，与本地产生的PRN32号卫星的码做相关运算，得到其相关频率条纹 $\phi ( f )$ ，如图6所示。对 $\phi ( f )$ 再进行傅里叶变化，其得到的功率谱的 $\left| \Phi ( \psi ) \right|$ 的最大值对应的频率即为所需要测得的时延 ${ \tau } + { \tau } _ { 0 }$ ，即图7中 $\left| \Phi ( \psi ) \right|$ 最大值对应的频率为所测时延 ${ \tau } + { \tau } _ { 0 }$ 。经计算，$\tau + \tau _ { _ { 0 } } { = } 6 0 7 . 6 \mathsf { n s }$ ，减去 $\tau _ { \scriptscriptstyle 0 } = 6 0 0 \mathsf { n s }$ ，最后得到 $\tau$ 为=7.6ns。乘以光速后得到的鉴相误差为 $2 . 2 8 \mathsf { m }$ 。

接收机的跟踪环路在进行稳定的跟踪后，其理论热噪声误差的计算如下：

$$
\sigma _ { n } = \sqrt { \frac { B _ { n } } { C N _ { 0 } } ( 1 + \frac { 1 } { 2 C N _ { 0 } T } ) }
$$

将误差转化为距离，可得：

$$
\sigma _ { n , M } = \frac { \lambda } { 2 \pi } \sqrt { \frac { B _ { n } } { C N _ { 0 } } \Bigg ( 1 + \frac { 1 } { 2 C N _ { 0 } T } \Bigg ) }
$$

在公式（9）中， $C N _ { 0 }$ 为接收机的载噪比， $B _ { n }$ 为噪声带宽，T为相关积分时间，在本次实际采样的数据中，载噪比通过采样数据计算出为 $C N _ { \mathrm { 0 } } { = } 4 2 . 6 \mathrm { d B } { \mathrm { - } } \mathrm { H z }$ 。传统的接收机积分时间为 $\scriptstyle \mathrm { { T = 1 m s } }$ ， $B _ { n } = 2 \mathrm { H z }$ ，在载噪比为 $4 2 . 6 \mathrm { d B - H z }$ 时，其理论热噪声误差上限为 $\sigma _ { n , M } = 3 6 . 0 5 9 \mathrm { m }$ 实际使用传统延时锁定环测量结果为 ${ \it 5 . 3 9 \mathrm { m } }$ 。通过相位条纹计算出的误差为 $2 . 2 8 \mathrm { { m } }$ ，优于传统锁相环中非相干点积功率法鉴相的理论误差。

# 4.结论

传统GNSS 接收机在实际的跟踪中的鉴相误差在0.1个码片左右，即为 $2 . 9 3 \mathrm { m }$ ，通过本文中的方法得到的误差为 $2 . 2 8 \mathrm { { m } }$ ，性能提高了 $2 3 \%$ ，在实际的接收机当中，为提供高精度的码相位计算给出了一种方法，从而得到了更高精度的伪距测量值。而在后续的工作中，需要对相位条纹方法中的参数的选取进行进一步的研究。

# A high-precision code phase measurement method based

# on phase strip

Wenjie Sun1.2， Zhaorui Wang

(1．Chinese Academy of Sciences，National Astronomical Observatories of China，Beijing 1Oo0l2，China

2.University of Chinese Academy of Sciences，Schoolof Astronomy and Space Science，Beijing l0oo49，China)

Abstract: After the GNSS (Global Navigation Satellite System) receiver receives the satellite signal, it acquires and tracks the two basic measurement values of code phase and carrier phase. Calculate the distance between the satelite and the receiver based on the measured value.The carrier phase measurement value has a higher measurement accuracy than the code phase measurement value, but because the carrier phase measurement value has the problem of calculating the ambiguity of the whole cycle,in the actual,the high-precision phase measurement result requires more calculation cost. Therefore, in actual calculations, obtaining a higher-precision code phase measurement result has practical measurement significance.Based on the phase strip technology, this paper proposes a higher-precision code phase measurement method by extracting the cross-correlation power spectrum to obtain a higher-precision code phase measurement value, thereby obtaining a higher-precision code pseudo range measurement result, And verify the effectiveness of this method through actual GNSS signals.

Key Words:GNSS; Phase Strip; Code Phase参考文献：[1]鲁郁．北斗/GPS 双模软件接收机原理与实现技术[M]．电子工业出版社,2016.

[2].谢钢.GPS原理与接收机设计[M]．电子工业出版社,2017.

[3] Krasner,Norman F.GPS receiver and method for processing GPS signals .United States Patent 6725159［P]．2000—08—15

[4] Anonymous. Understanding GPS Principles and Applications: Second Edition[J]. Microwave Journal,2008,51(1).

[5]张波，郭英，齐子森,等.PN 码相位精确测量的累加最小二乘法[J].北京航空航天大学学报,2016,42(010):2265-2270.

[6]龚国辉,李思昆.提高 DSSS 信号 PN码相位测量精度的三点二次插值法[J].通信学报,2007(02):130-133.

[7]胡修林,张俊,杨灵.直接序列扩频通信系统中PN码相位的精确测量方法[J].电讯技术,2005(03):128-131.

[8]罗海军,彭卫东.整体最小二乘法在精同步中的应用[J].计算机测量与控

制,2014,22(07):2291-2294.

[9]G.Boscagli, P. Holsters, E.Vassallo and M. Visintin, "PN Regenerative Ranging and Its Compatibility With Telecommand and Telemetry Signals," in Proceedings of the IEEE,vol.95,no. 11,pp. 2224-2234, Nov. 2007,doi: 10.1109/JPROC.2007.905186.

[10]彭保童,马宏,毛鑫峰.基于再生伪码测距的复合码分析[J].电子测量技术,2017,40(10):171-175.

[11]侯彦兵,焦义文,杨文革.基于遥测信号的测距技术及其发展趋势[J].电讯技术,2019,59(07):863-868.

[12]孙慧萍，张丽，王利红,等.GPS 软件接收机码跟踪环的参数设计[J]．山西大同大学学报(自然科学版),2018,034(002):10-12.

[13]刘盟超，赵丙风.GNSS接收机自适应带宽伪码跟踪环路设计[J]．无线电通信技术，2017(4).

[14] M.Lashely, Kalman Filter Based Tracking Algorithms For Software GPS Receivers.[D] 2006.

[15]王丽华，李博扬，寇建辉.GPS 接收机PLL与卡尔曼跟踪环路性能分析[J]．现代导航,2016, 000(001):28-33.

[15] MiaoJ， Wu C， Sun Y,et al. Low C/NO Carrier Tracking Loop Based on Optimal Estimation Algorithm in GPS Software Receivers[J]. Chinese Journal of Aeronautics,2010,23(1):109-116.

[16]傅圣友，王兆瑞，金声震,等．基于相位条纹的高精度GPS 码相位测量方法[J].北京航空航天大学学报,2019,45(009):1824-1830.