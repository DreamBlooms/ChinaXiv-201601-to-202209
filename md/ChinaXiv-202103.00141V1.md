# 国家授时中心40米射电望远镜Crab脉冲星周期跃变监测

戴顺1²，孙鹏飞²，刘海文，李祎丰²，赵成仕²，罗近涛²,4(1．华东交通大学，江西 南昌330013;2．中国科学院国家授时中心，陕西西安710600；3．西安交通大学，陕西 西安710049;4．中国科学院精密导航定位与定时技术重点实验室，陕西 西安710600)

摘 要：脉冲星周期跃变是一种罕见的现象，是研究其内部结构的探针。针对2019年2月至12月，国家授时中心昊平观测站40米射电望远镜在脉冲星计时观测中，监测Crab脉冲星的数据，采用脉冲星计时方法，用TEMPO2拟合程序进行分析。结果表明Crab脉冲星在2019年7月23日（MJD58687）附近发生了一次周期跃变现象，该跃变自转增量为 $\Delta v _ { g } = 5 . 3 3$ (4)$\times 1 0 ^ { - 7 } \mathrm { H z }$ ，自转变化量为 $\Delta v _ { g } \ / v \ = 1 7 . 9$ （1） $\times { 1 0 } ^ { - 9 }$ ，并伴随着恢复系数 $Q \sim 0 . 8 8$ 的指数恢复过程。此次Crab脉冲星周期跃变的监测及处理，证实了国家授时中 $\therefore \because 4 0$ 米射电望远镜对脉冲星的监测性能，同时为研究周期跃变的产生机理积累了样本。

关键词：周期跃变；脉冲星；蟹状星云脉冲星；计时残差中图分类号：P161.1 文献标识码：A 文章编号：

脉冲星是一种具有极强磁场的高速自转的中子星，其长期稳定度可媲美原子钟[]。部分脉冲星自转表现出计时噪声（timingnoise）和周期跃变（glitch）这两类不稳定性。计时噪声广泛存在于脉冲星中，是一种连续的、小幅度的波动现象[2，在具有较大周期导数的脉冲星中表现更为显著，大部分计时噪声具有准周期特征；周期跃变则表现为自转速度突然增加，通常伴随着时长几周到几年不等的恢复过程[3，周期跃变事件比较罕见，是一种偶发现象，目前无法进行预知[4]。在目前已知的2872颗脉冲星中③，共监测到190颗脉冲星的 567次周期跃变。

在已监测到的大多数周期跃变事件中，没有发现辐射特征的明显变化。因此，周期跃变很可能与脉冲星内部结构的变化有关。目前关于周期跃变的产生机制主要有两种理论模型：星震模型[5]和涡流模型[。星震模型认为，周期跃变是脉冲星壳层形变而导致的现象，即脉冲星自转的稳定减慢会破坏引力与离心力的平衡，脉冲星发生突然收缩，使得脉冲星自转突然加快。涡流模型认为，周期跃变是在脉冲星自转减慢过程中，内部超流体和外部壳层的角速度存在差速旋转，当壳层的旋转速度比内核慢且耦合力不超过某种极限值时，镶嵌在外壳晶格中的涡流只能向外运动，并把角动量传给外壳[7]，于是形成脉冲星自转速度加快现象。星震模型可能适用于小幅度的周期跃变，涡流模型可能适用于大幅度的周期跃变。

1968年发现的Crab脉冲星（PSE $\scriptstyle { \ k \mathrm { B 0 } } 5 3 4 + 2 1$ 或PSR $\mathbf { J } 0 5 3 4 { + } 2 2 0 0$ ）形成于公元1054年，是蟹状星云超新星产生的致密星体，同时是目前已知最年轻的脉冲星之一[8]。Crab脉冲星的自转周期约为 $3 3 \mathrm { m s }$ ，周期导数约为 $\phantom { + } 4 . 2 \times 1 0 ^ { - 1 3 }$ ，有约 $\boldsymbol { 4 \times 1 0 } ^ { 1 2 }$ G的强磁场，具有多波段辐射特性[9]。但由于Crab脉冲星比较年轻，内部结构还不太稳定，因此，研究Crab脉冲星的周期跃变事件可作为研究中子星内部结构的探针，具有重要科学意义。

本文将介绍中国科学院国家授时中心昊平观测站40米望远镜监测Crab脉冲星，在2019年7月23日前后自转周期发生跃变的情况。第一章介绍了用于本次研究的观测数据；第二章描述了数据处理流程；第三章对计时处理结果进行分析，在第四章给出结语

# 1观测

观测使用中国科学院国家授时中心（National Time Service Center,NTSC）的40米射电望远镜（Haoping Radio Telescope,HRT）。该望远镜建于2014年，位于西安以东约100公里的洛南县昊平观测站，坐落在四面环山的秦岭山脉中，电磁环境优良。HRT是一架全可动的卡塞格伦式单口径望远镜，由全面板反射面组成[10]。脉冲星计时观测系统配备L波段常温接收机和FPGA $^ +$ GPU架构的数字终端。其中，接收机带宽为800MHz，在2019年11月之前为右旋圆极化的单极化接收模式，此后升级为双圆极化观测模式。2019年7月开始新增相干消色散模式。系统噪声温度约100K。

昊平观测站望远镜对Crab 脉冲星的观测为2-5天进行一次，观测时长10-75分钟不等。用于本次Crab 脉冲星周期跃变研究数据的时间跨度为2019年2月21日至2019年12月8日（MJD58534-MJD58825)，其中包括非相干消色散和相干消色散[两种观测模式的数据。在非相干消色散模式下，时间分辨率为10.24us，采用1024个频率通道和1024个相位进行数据记录；在相干消色散模式下，时间分辨率为1.28us，采用1024个频率通道和1024个相位进行数据记录，子积分时间为10s。

# 2数据处理流程

计时观测数据处理采用预处理软件PSRCHIVE和计时分析软件TEMPO2。PSRCHIVE[12]是一款科学数据分析的开源软件，应用于脉冲星天文学研究，可实现脉冲星计时观测数据的校准、统计分析与模拟以及可视化。TEMPO2[13]是为脉冲星计时阵列项目开发的一款计时软件，使用国际天文参照系（ICRS）并遵从IAU2000决议，用于拟合周期跃变参数，计时精度可达纳秒级别。

本次数据处理流程如图1所示，对HRT观测所得折叠模式数据，首先使用PSRCHIVE对数据进行消干扰；再对消色散后的子积分轮廓在在时间、频率和偏振上进行叠加，得到平均脉冲轮廓；为了得到更准确的脉冲信号到达时间，通常把所有观测到的脉冲轮廓叠加，得到一个高信噪比的脉冲轮廓，将其作为标准轮廓，再将标准轮廓与每个平均脉冲轮廓做互相关，得到脉冲到达台站的时间。为消除地球运动的影响，通常需要将太阳系质心看做惯性系，把 PSRCHIVE 得到的所有到达时间转换为到达太阳系质心时间，此过程可使用TEMPO2 实现。使用TEMPO2将本次数据中实际观测到达时间与脉冲星计时模型预估到达时间进行拟合，得到计时残差。转换时用到的太阳系星历为DE405，时间系统为质心坐标时TDB。脉冲星的脉冲相位及指数恢复过程分别如式（1）和式（2）所示：

$$
\begin{array} { r } { \varphi ( t ) = \varphi _ { 0 } + v t + \frac 1 2 \dot { v } t ^ { 2 } + \frac 1 6 \ddot { v } t ^ { 3 } } \end{array}
$$

$$
\begin{array} { r } { v ( t ) = v _ { 0 } ( t ) + \Delta v _ { p } + \Delta \dot { v } _ { p } t + \frac 1 2 \Delta \ddot { v } _ { p } t ^ { 2 } + \Delta v _ { d } e ^ { - t / \tau _ { d } } } \end{array}
$$

式（1）中， $\varphi _ { 0 }$ 为 $\scriptstyle t = 0$ 时刻的相位； $v$ ， $\dot { v }$ ，分别为脉冲星的自转频率及其一阶导数和二阶导数。式（2）中， $\Delta v _ { p }$ ， $\Delta \dot { v } _ { p }$ ， $\Delta \ddot { v } _ { p }$ 分别为周期跃变后，自转频率及其一阶导数和二阶导数未衰减的值； $\Delta v _ { d }$ 为恢复幅度； $\boldsymbol { \tau _ { d } }$ 为恢复时标。

![](images/bcf5a4861fdc90fa37f170ed136890278b4a3c24a448ab3924efb3ba84ee4876.jpg)  
图1脉冲星计时数据处理流程

# 3数据处理结果及分析

# 3.1预处理结果

HRT 观测Crab 脉冲星的某次数据经PSRCHIVE 处理，所得轮廓图如图2所示。该轮廓信噪比约为33.445，积分时间约为95分钟。在此轮廓图中，可清楚看到Crab 脉冲星轮廓的三个主成分：分别位于相位0.3和0.7 附近的主脉冲和中介脉冲，以及位于主脉冲前约0.1处的前兆脉冲。PSRCHIVE 处理所得Crab 脉冲星发生周期跃变前的自转参数如表1所示。

![](images/9adc8c083f0920086a6886501bef8ea162819d91177ac64748cb29fae9431ab5.jpg)  
Fig.1Processing flow of pulsar timing data   
图2 Crab 脉冲星轮廓图Fig.2Profile of Crab pulsar

表1周期跃变前的自转参数Tab.1 The parameters of pre-glitch  

<html><body><table><tr><td>Parameter</td><td>Value</td></tr></table></body></html>

<html><body><table><tr><td>MJD</td><td>58676</td></tr><tr><td>R.A. (J2000)</td><td>05:34:31.921 (5)</td></tr><tr><td>Dec.(J2000)</td><td>+22:00:52.16 (6)</td></tr><tr><td>v (s-1)</td><td>29.6169568869（5)</td></tr><tr><td>b(s²)</td><td>-3.683443（8） ×10-10</td></tr><tr><td> (s-³)</td><td>1.2611（1）x10-20</td></tr><tr><td>DM (cm³pc)</td><td>56.7983 (1)</td></tr><tr><td>UNITS</td><td>TDB</td></tr><tr><td>CLK</td><td>TT(TAI)</td></tr><tr><td>EPHEM</td><td>DE405</td></tr></table></body></html>

# 3.2计时观测结果及分析

使用TEMPO2拟合研究数据中Crab 脉冲星的自转频率 $v$ 、自转频率的一阶导数v和自转频率的二阶导数。结果表明该星在2019年7月23日（MDJ58687）附近发生了一次周期跃变事件，计时残差如图3所示。脉冲到达时间拟合得到自转频率及其一阶导数随时间的变化，如图4所示，其中上面板为跃变后的自转频率与其平均值的差值，下面板为自转频率的一阶导数随时间的变化。拟合所得该星跃变后的参数如表2所示。

本次跃变幅度为 $\Delta v _ { g } / v \ = 1 7 . 9 \ ( 1 ) \ \times 1 0 ^ { - 9 }$ ，是该星较大的一次跃变事件。其自转增量为$\Delta v _ { g } = 5 . 3 3 ~ ( 4 ) \times 1 0 ^ { - 7 } \mathrm { H z }$ ；频率一阶导数的变化幅度为 $\Delta \dot { v } _ { g } / \dot { v } \ = 3 . 4 3 \ ( 4 ) \times 1 0 ^ { - 4 }$ ；一阶导数变化量为 $\Delta \dot { v } = - 1 . 2 6$ (1) $\times 1 0 ^ { - 1 3 } \ \mathrm { s } ^ { - 2 }$ 。对周期跃变后的分析表明此次周期跃变伴随着一次指数恢复过程，恢复幅度为 $\Delta { v } _ { d } = 4 . 6 9 2 5 6 0 7 8 ~ ( 3 ) \times 1 0 ^ { - 7 }$ ，恢复系数 $Q { = } \Delta v _ { d } / \Delta v _ { g } \sim 0 . 8 8$ ，恢复时间$\tau _ { d } = 8 . 3$ (3）d。

将数据处理结果与脉冲星周期跃变统计表错误!未找到引用源。结果进行对比，统计表中记录本次跃变事件大小为 $\Delta v _ { g } ~ / v ~ = ~ 3 6 . 0$ （1） $\times { 1 0 } ^ { - 9 }$ ，两者跃变大小在一个量级，数值上的差别或为HRT观测数据在跃变后的部分缺失引起。

![](images/2644744c4e65f79562f4434eaccf6d745abac7a483b39d49f86dc2a16811e50e.jpg)  
图3计时残差  
Fig.3Timing residuals

图4自转频率及其导数随时间的演化  
![](images/afe5d1cdc9209516b86c39b7e7ad2e7d1c5761376c0956730203436af9164331.jpg)  
Fig.4 The evolution of rotation frequency and its derivative with time

表2跃变后的参数  
Tab.2 The parameters of post-glitch   

<html><body><table><tr><td>Parameter</td><td>Value</td></tr><tr><td>MJD</td><td>58742</td></tr><tr><td>R.A. (J2000)</td><td>05:34:31.921 (5)</td></tr><tr><td>Dec.(J2000)</td><td>+22:00:52.16 (6)</td></tr><tr><td>v (s-1)</td><td>29.616957459 (1)</td></tr><tr><td>b(s²)</td><td>-3.68474(6）X10-10</td></tr><tr><td>v (s-3)</td><td>2.2（1）×10-20</td></tr><tr><td>DM (cm³pc)</td><td>56.7983 (1)</td></tr><tr><td>UNITS</td><td>TDB</td></tr><tr><td>CLK</td><td>TT (TAI)</td></tr><tr><td>EPHEM</td><td>DE405</td></tr></table></body></html>

# 3结语

中国科学院国家授时中心昊平观测站40米射电望远镜对Crab脉冲星进行长期计时观测，监测到该星于2019年7月23日附近发生了一次周期跃变现象。通过处理及拟合观测数据，分析了此次周期跃变的过程，结果表明该星跃变幅度为 $\Delta \nu _ { g } / \nu = 1 7 . 9 \ \mathrm { ( 1 ) \times 1 0 ^ { - 9 } }$ ，并伴随着 $\boldsymbol { \tau }$ （204号$\scriptstyle { \mathbf { \Gamma } } _ { d } = 8 . 3$ （3）d的指数恢复过程，恢复系数 $Q \sim 0 . 8 8$ 。目前，周期跃变的物理机制未被合理解释，脉冲星计时观测对研究脉冲星内部结构具有重要意义。

# 参考文献：

[1] TaylorJH.MilisecondPulsars:Nature's Most Stable Clocks [J].Proceedingsof the IEEE,2002,79(7):1054-1062. [2] 高旭东，张双南，付建宁．正常脉冲星计时噪声的研究进展[J].天文学进展，2016,34(2):163-180.GAO Xudong, ZHANG Shuangnan,FUJiang.Reseachprogressof timngoseoformalpulsar[J].rogressinstronom,16,34(2):

163-180.

[3] 王娜，吴鑫基．射电脉冲星周期跃变研究的进展[J].天文学进展,2000,18(3):29-237.WANGNa,WU Xinji.Glitch of the radio pulsars[J]. Progress in Astronomy,200o,18(3): 229-237.   
[4] 周世奇，张洁，袁建平等．PSR J1016-5857 的周期跃变分析[J]．西华师范大学学报:自然科学版，2018，39(1)：78-81. ZHOU Shiji,ZHANG Jie,YUAN Jianping,et al.On pulsar glitches inPSR J1016-5857[J].Journal ofChina West Normal University(Natural Sciences),2018,39(1):78-81.   
[5] Ruderman M,ZhuT,Chen K.Neutron star magnetic field evolution,crust movement and glitches [J].astrophysicaljournal, 1997,492(1): 267-280.   
[6] Ruderman MA.Crust-breaking by neutron superfluidsandthe VELA pulsar glitches[J].TheAstrophysical Joural,1975, 203(1):213-222.   
[7] 李林森．脉冲星磁衰减制动力矩对两成分模型自旋的长期减速(理论研究)[J].天文研究与技术,2020,17(01):21-26.LI Linsen.The impact of magnetic decay braking torque on the secular retardation of spin of two-components of pulsars[J]. Astronomical Research & Technology,2020,17(01): 21-26.   
[8] Wang N, Wu XJ, ManchesterRN,etal.ALarge Glitch in theCrabPulsar[J].Researchin Astronomyand Astrophysics, 2001,1(3):195-199.   
[9] 朱鸿旭，童明雷，杨廷高等．XPNAV-1 卫星先期发布数据的计时分析[J]．宇航学报，2019,40(12):1492-1500.ZHU Hongxu,TONG Minglei,YANGTinggao,etal.Measured data processng and analysis for XPNAV-1[J].Journal of Astronautics,2019,40(12): 1492-1500.   
[10] Luo JT,GaoYP,YangTG,etal.Pulsar Timing Observations with Haoping Radio Telescope[J].Reserch inAstronomyand Astrophysics,2020.   
[11] 黄玉祥,汪敏,郝龙飞,李志玄,徐永华.脉冲星信号相干消色散与非相干消色散的比较研究[J].天文研究与技术，2019, 16(01):16-24.HUANG Yuxiang,WANG Min,HAOLongfei,etal.Comparative study between thecoherentde-dispersion and the incoherent de-dispersion of pulsar signal[J].Astronomical Research & Technology,20l9,16(O1):16-24.   
[12] Straten WV,Manchester RN,Johnston S,et al.PSRCHIVEand PSRFITS: Definition of the Stokes Parameters and Instrumental Basis Conventions[J].Publications of theAstronomical Societyof Australia,2Oo9,27(1):104-109.   
[13] HobbsG,EdwardsR,ManchesterR.TEMPO2:ANew Pulsar Timing Package[J].Monthly Noticesof the Royal Astronomical Society,2006,6(S2): 189-192.

# The Crab Pulsar Glitch Monitoring by the 40-meter Radio Telescope of the National Timing Center

Dai Shun1,2， Sun Pengfei²，Liu Haiwen³，Li Yifeng²， Zhao Chengshi²，Luo Jintao2,4

（1.East China Jiaotong University,Nanchang 33Oo13，China; 2.National Time Service Center, Chinese Academy of Sciences,Xi'an 71O6oo,China; 3.Xi'an Jiaotong University,Xi'an 710049,China;

710600，China)

Abstract: Pulsar glitch, is a rare phenomenon,and is a probe for studying the internal structure of pulsars.From February to December 2O19, time-of-arrival measurements have been collcted for Crab pulsar with the 40-meter radio telescope at Haoping Observatory of the National Timing Center during pulsar timing observations. These measurements are analyzed by “timing solutions” with TEMPO2 fiting program. We have observed a glitch in the Crab pulsar. The glitch occurred around July 23,2019 (MJD58687) when Crab pulsar underwent an increase in the rotation rate of $\Delta ~ \nu _ { g } = ~ 5 . 3 3 ( 4 ) { \times } 1 0 ^ { - 7 } ~ \mathrm { H z }$ ， corresponding to fractional size of $\bigtriangleup \nu _ { g } / \nu =$ （204号 $1 7 . 9 ( 1 ) { \times } 1 0 ^ { - 9 }$ . This event was followed by an exponential recovery process with a degree of recovery $\mathrm { \Delta Q \sim 0 . 8 8 }$ . The monitoring program of the Crab pulsar glitch, indicate that the 4O-meter radio telescope of the National Time Service Center has a pretty good receiving sensitivity and system stability for pulsar timing observations， and contribute samples to study the mechanism of pulsar glitch.

Key words: Glitch; Pulsar; Crab pulsar; Timing residual