# 2015年11月4日太阳射电爆发干扰导航信号事件中的X-ray先兆分析

董亮¹，闫小娟²，黄文耿³，李攀4，于超²,高冠男1，阿尔察³，沈发新1.5，郭少杰1

1．中国科学院云南天文台，云南昆明6502162．国家卫星气象中心/国家空间天气监测预警中心，北京，1000813．中国科学院国家空间科学中心，北京，1000904．北京跟踪与通信技术研究所，北京，1000945．中国科学院大学，北京，101408

摘要：太阳射电爆发是无线通信特别是卫星导航通信的潜在影响因素之一。2015年11月4日的太阳射电爆发事件在1415MHz 点频上的流量达到了峰值 5800SFU(Solar Flux Unit），位于日下点的欧洲 GPS 系统和瑞典的航空导航系统均受到了影响。本文分析了该次事件产生源活动区的X-ray 流量变化与射电流量变化之间的时间前后关系；通过比对,X射线的流量抬升时间较之于射电阈值具有30分钟的提前量；随后本文讨论了该提前量之间的物理背景，即软硬X射线分别对应了热电子和非热电子辐射，而非热电子是产生能够造成该类空间天气事件射电爆发的物理条件，X射线由软转硬过程中流量的抬升变化，正好为进一步防控该类空间天气事件提供了一种有效的手段。

关键词：太阳射电爆发；导航信号；同频干扰；X-ray；先兆分析中图分类号：P162文献标识码：A

# 0.引言

太阳从诸多方面影响着人类的生产生活，其中长短期的活动造成了多种空间天气事件。随着 20 世纪开始的无线电技术的广泛使用，使得无线电频谱成为日趋紧张的一种资源，而太阳射电爆发以宽带强无线电辐射方式发射信号，瞬间占用了非常宽带的无线电频段资源，对实时性要求较高的如雷达、导航等系统具有较大影响。

在雷达广泛使用的第二次世界大战期间，1943 年英军雷达受到了来自太阳的强射电爆发干扰，这是人类无线技术系统首次受到太阳射电爆发影响[。随着消费类电子的广泛使用，L.J.Lanzerotti等人与 1999年发现在一次太阳射电爆发期间，迎日面手机基站的通话失败数量（droppedcall rates）较之于背日面有大幅增加，且在时间上与太阳射电爆发持续时间呈很好的正相关性[2]。但是手机通信对实时性要求并不高，为此太阳射电爆发带来的干扰对用户体验感方面几乎没有明显的影响。然而导航系统用户需要较高的，为此该类事件影响将会为导航系统用户带来重大影响，主要体现在信号失锁，定位精度偏离等。为此从GPS组网以来受到过多次太阳射电爆发事件的影响。

第一次影响事件可以追溯到 2003年10月28日的事件，在该次事件中，Chen，Z.，Y.Gao 等人发现GPS于UTC 11:02到11:59GPS 信号出现不同情况的失锁，其中在射电爆发流量最强的11:05分，所有伪随机码接收机均失锁。同时该项研究通过对比四个不同位置 IGS 地面站（BRAZ:-47.9°， $- 1 5 . 9 ^ { \circ }$ ；ALAC : $+ 3 8 . 2 ^ { \circ }$ ’ $- 0 . 3 ^ { \circ }$ ；SIM0:+18.4°， $- 3 4 . 2 ^ { \circ }$ ；NKLG:2.1°， $9 . 4 ^ { \circ }$ ）的失锁情况有所不同，暗示该种事件的影响情况与太阳高度-天线主瓣之间的夹角有关[3]。

第二次典型的事件为2006年12月中上旬的事件（活动区10930)，C.S.Carrano等人经事后分析，发现其中在四天的太阳耀斑爆发事件，在这四次事件中很有趣的是，12月5、6、13、14日均发生了耀斑爆发事件，且对应 X-ray 流量分别达到了X9.0\X6.5\X3.4\X1.5，但是作为X-ray 流量最强的5 日的耀斑事件并没有产生射电爆发[4][5]，没有一一对应关系。为此，常规的一些太阳观测数据也许不能很好的作为一种预警L 波段太阳强射电爆发的手段。

Yue，X.等人对 2006 年以来多起太阳射电爆发干扰导航通信事件进行了分析讨论，结合太阳射电监测网（radio solar telescope network，RSTN）在监测频点 $1 4 1 5 \mathrm { { M H z } }$ 和 GNSS 系统明显失锁之间的时间关系，认为1807SFU（Solar Flux Unit，太阳射电流量单位， ${ \mathrm { 1 S F U { = } 1 0 ^ { - 2 2 } W / \left( m ^ { 2 } { * } H z \right) } }$ ）可以作为影响阈值[6]。

黄文耿、阿尔察等人通过对 2017年9月7日太阳爆发事件中多GNSS 系统的分析，发现了北斗导航系统也受到了太阳射电爆发影响，失锁时间长达几分钟，信噪比损失 $1 0 \mathrm { d B }$ 以上[7]。

董亮、闫小娟、屈会鹏等人于2016年、2018年计算分析了太阳射电爆发干扰导航信号的影响流量阈值，根据 BD、GPS 等不同导航系统采用的不同频点，分析得出其影响阈值在1000-2600SFU之间，且与通信波长的平方成倒数关系[8]-[9]。而L波段内 1000SFU以上的太阳射电爆发是一种比较频繁的事件，这将对导航通信造成严重的影响。

北斗卫星导航系统进入了全球布网服务阶段，由于2015年11月4日的太阳射电爆发事件时，欧洲地区为白天，为此对比GPS 和北斗系统在这两次事件中的表现情况，同时该类事件的流量正好介于L1（1575.42MHz）和L2（1227.60 MHz）的两个通信频段的影响阈值流量之间，即发现L2信号失锁，而L1信号没有受到影响[10]，这次事件反映了L波段太阳射电爆发频谱的复杂性给该类空间天气事件带来的不同表现，是一次比较有代表意义的事件。

对 2015年11月4日太阳射电爆发事件的研究能够为将来北斗有效的全球服务的稳定性提供较好的参考和借鉴意义。

# 1．目前预警该类事件的困难及应对

分米波段是重要的通信、雷达使用频段，在其中富集导航、CDMA、雷达、卫星通信等一系列发射信号，该类发射信号往往具有较强的发射功率，以及多种形态的发射信号频谱。同时该频段也是射电天文、太阳物理、空间天气中重要的观测频段，其在连续谱辐射的背景上叠加了丰富的频谱特征，产生多种频谱形态

的射电爆发。

为此在分米波段的太阳射电监测往往遭遇强无线电干扰，使得在地面精准预测在频段内的太阳射电流量走势显得非常困难。

剧烈太阳射电爆发特别是L波段的爆发均由耀斑爆发产生，太阳耀斑爆发大多数具有很宽的电磁波谱，在X-ray、紫外、EUV 等多个波段均有辐射产生。其中X射线是一个重要的成分，也是观测和研究太阳耀斑的一个重要手段。耀斑中的微波和X射线（特别是硬X射线）具有很好的相关性，一般认为两者是由耀斑加速的同源电子产生。目前国际国内部署了诸多空间X射线探测卫星载荷，如GOES、SMM、Yohkoh 等，国内的风云系列卫星装备了 X射线探测器[10][1]，为此 X-ray 是一种方便获取的太阳观测数据。我们试图通过分析从2015年11月4日事件中 X-ray的观测数据与射电流量之间的变化关系，分析采用 X-ray 观测数据来预警该类空间天气事件的可能性，同时进一步探讨背后的物理背景为预警预报提供理论支撑。

# 2.2015年11月事件及影响描述

2015年处于太阳第24活动中峰年末期,11月4日事件产生活动区AR12443,爆发时的日面位置为N06W10。其中该次射电爆发的前产生了一次X-ray 爆发，流量级别为M3.7级,此次太阳射电爆发峰值流量变化如下图所示[12]：

![](images/8a1add61fbaef1caeddeba2853e8c4f06a94c4db8620e4bfdc9ff55757667c7d.jpg)  
图1．多频点太阳射电流量随时间变化图

Fig.1 The variation of multi-frequency solar radio flux during Nov.4 20l5 event

各主要监测台站测量得到的太阳射电流量如下表所示：

表1．该次事件中多台射电望远镜的观测数据

Table.1 the observation data of several solar radio telescope during this event   

<html><body><table><tr><td>Frequency</td><td>ORFEES</td><td>HSRS</td><td>Callisto</td><td>Callisto</td><td>NOAA</td></tr><tr><td>(MHz)</td><td>(Nancay)</td><td>(Humain)</td><td>(Bleien)</td><td>Zurich</td><td>Report</td></tr></table></body></html>

<html><body><table><tr><td>610</td><td>820</td><td>1034</td><td></td><td></td><td>1000</td></tr><tr><td>1000</td><td>105(饱和)</td><td></td><td></td><td></td><td></td></tr><tr><td>1060</td><td></td><td>1.57*105</td><td>1</td><td></td><td></td></tr><tr><td>1000-1250</td><td></td><td>1</td><td>1.23*106</td><td></td><td>1</td></tr><tr><td>1415,1427</td><td></td><td>5245</td><td></td><td>6310</td><td>5800</td></tr></table></body></html>

据报道，在此次事件中全欧洲的观测台站中观测到GPS 系统的 L1频点没有受到影响，而L2频点受到影响，影响时间为UTC14:20到15:02，其中影响的峰值时间为UTC14:29，平均信噪比损失为 $- 5 . 8 \pm 2 . 2$ dB-Hz,最大信噪比损失为-10dB-Hz(http://gnss.be/Atmospheric_Maps/srb_event.php?date=2015-11-04)。

![](images/4345ff35b52433b2c871f2737b7296805eba5efb03093512c40a2fed449d33f4.jpg)  
图2．GPSL1/L2频段信噪比随时间变化图

Fig.2 The variation of SNR (Signal to Noise Ratio)-time of GPS L1/L2 frequency band

造成两个频段信噪比下降差异的原因在于，L1点频率高于L2 点，其影响阈值更高，在这次事件中在L1频段的太阳射电流量并未超过L1点的阈值，说明目前太阳射电爆发对导航通信影响事件具有极大的不确定性，这也可能在影响事件的反应上带来多种现象，值得进一步深入研究。

# 3.X-ray观测数据和射电流量的时间关系

由于 X-ray 和射电信号一样，均以光速传播，同时根据已有研究表明，X-ray 和分米波段的剧烈太阳射电爆发均来自于同一耀斑区电子的非热辐射（non-thermal)，两者在光变曲线上具有很好的相关性[1]-[14]。而从射电流量开始抬升到其达到影响导航通信的阈值之间是个逐步变化的过程，由于X-ray在空间观测受到的干扰较少（对比强干扰存在的无线电L波段)，同时采用空间卫星观测可实现全天候观测，可以推段采用X-ray的观测是可以作为一种事件较为有效的预警手段。

为此我们就 2015年11月4日事件中X-ray 流量和L波段内的观测点1415MHz 流量变化时间以及GPS 系统的失锁时间点的先后顺序进行分析，探讨。

# 3.1X射线流量随时间的变化情况

此次事件中的 X射线流量数据（来源 GOSE:Geostationary Operational Environmental Satellites卫星）,X-ray爆发起始时间为：UTC 2015-11-413:31:00,结束时间为：UTC 2015-11-414:13:00。随时间变化的信息显示如下图所示：

![](images/252ac6e3b1287ddd5cc93d73af923a706a223357039ae7e5d669504f92b75c7c.jpg)  
图32015年11月4日事件中的两个波段（ $\mathrm { 1 . 0 { - } 8 . 0 \mathrm { A } }$ 和0.5-4.0A）的流量随时间变化图

Fig.3 The variationof flux-time in two bands (1.0-8.0a and 0.5-4.0a)during Nov.4 2015 event

# 3.2射电流量随时间变化数据

根据Yue，X.等人得出的在1415MHz频点流量1807SFU为阈值点,在此次事件中的1415MHz频段上的 RSTN测量得到的峰值数据为 5891SFU，第一次超过1807SFU的时间为，14:25:15，晚于X-ray 的起始时间，甚至晚于X-ray 爆发的结束时间。

![](images/c4bebfbf249e2c90da95a830362f020003274570d647a015eeb966ad5ad0e82b.jpg)  
图4.该次事件中1415MHz频点的太阳射电流量随时间变化曲线

从此次事件的观测数据来看，由于剧烈太阳射电爆发和X-ray爆发总是伴生出现，而由于影响阈值的存在，GNSS 失锁时间晚于 X-ray 爆发开始时间，为此发现X-ray 的流量变化抬升拐点后，极大可能存在一个射电爆发的峰值。

![](images/9ec47f272731dc07c9743d97401167453d4f27b218a1ecfe7d73cb84974dc1b1.jpg)  
Fig.4 The flux variation of solar radio in 1415MHz during this event   
图5.两种爆发流量时间关系  
Fig.5 Time relationship between two burst flows

# 4.物理背景阐释

根据亮温度产生不同物理背景，具有高亮温度（ $_ { ( > 6 0 0 0 \mathrm { K } }$ ）的太阳射电爆发（特别在分米波波段)，均由非热电子或相对论电子在强磁场作用下产生[15]。如下图所示：

![](images/7a0b59aef8164170ca7d52612e07385611a40a341fffaea9786a6b0e6d238b59.jpg)  
图6．射电辐射中热电子、非热电子的亮温度谱和流量谱关系图

Fig.6 The bright temperature and flux spectrum of thermal and non-thermal electron in radio emission

X射线观测分为软X射线和硬X射线两个波段，两者对应的物理起源和辐射机制有所不同，软X射线由热成分产生，而由非热成分产生。而两者之间没有明确的界限。而非热电子是产生X射线辐射特别是硬X射线（ $1 0 ^ { - } 3 0 0 \mathrm { k e V } .$ ）辐射的主要来源[17]。

一个耀斑产生、发展及爆发，均与耀斑内部的等离子体团块演化状态相关，而在耀斑演化早期，其成分主要是热电子此时X射线波段以软X射线，而在耀斑发展过程中，磁场逐渐加强，在磁场作用下，热的等离子体团块逐渐被加速到非热电子,即可在10-300KeV段内辐射出硬X射线，而在射电波段产生较强亮温度的辐射，最终超过射电流量影响阈值，形成干扰事件。

![](images/1ff96a6f5284c324f546395f859e7ecb485265141ff2f901b352e0b82687eeb1.jpg)  
图7.太阳射电爆发事件过程中的X射线及射电流量变化流程

Fig.7 The flux variation of X-ray and solar radio during solar radio burst events

为此，在耀斑演化过程中，软X射线逐渐上升到硬X射线的过程，也是太阳射电流量逐渐上升超过影响阈值的过程，通过监测X射线的变化，可以预示接下来的射电流量增强。

# 5.总结

与其他空间天气事件不同的是，太阳射电爆发产生的强电磁波以光速传递直接作用于阳光下的所有无线电技术设备。具有发生时间快、作用范围广等特点。同时根据Nita等人2004年的统计超10SFU的强太阳射电爆发在太阳活动峰年大约十几天一次，即使在太阳活动宁静年也可能一年有 2-3次，是一种较为常见的空间天气事件。

而X射线是一种太阳常规观测手段，下一步我们将深入分析第23-24太阳活动周中，多起太阳射电爆发干扰导航通信事件时，X-ray 和L波段太阳射电流量之间的关系，探讨利用 X-ray 观测数据预警该类事件的可能性。

# 参考文献：

[1] Hey, J.S., Solar Radiations in the 4--6-meter Radio Wavelength band [J]. Nature,1946(158): 234 [2]LJ. Lanzeroti,D.E.Gary,G.M.Nita,et.al.Noise inwirelesssystems fromsolarradiobursts[]Advanced in

Space Research.2005(36) :2253-2257

[3] Chen,Z,Y.Gao,and Z.Liu,Evaluation of solar radio bursts'effectonGPS receiver signal tracking within International GPS Service network[J]. Radio Sci.,2005(40),RS3012,doi:10.1029/2004RS003066.

[4] C.S.Carrano,C.T.Bridgwood,and K.M. Groves，Impacts of the December 2006 solar radio bursts on the performance of GPS. [J]. RADIO SCIENCE, 2009(44), RS0A25,doi:10.1029/2008RS004071,

[5] Cerruti,A.P.,Kintner,P.M.,Gary,D.E.,Lanzeroti,L.J,De Paula,E.R,&Vo,H.B.Observed solaradio burst effects on GPS/wide area augmentation system carier-to-noise ratio.[J]. Space Weather, 20o6(4). DOI: 10.1029/2006SW000254

[6] Yue,X.,et al.,The effect of solar radio bursts on the GNSS radio occultation signals []. J. Geophys. Res.   
Space Physics,2013(118): 5906-5918,doi:10.1002/jgra.50525.

[7] Wengeng Huang, Ercha A,et.al,Statistical study of GNSS L-band solar radio bursts [].GPS Solutions, 2018(22) :114. https://doi.0rg/10.1007/s10291-018-0780-4

[8] 董亮，太阳射电爆发对无线通信影响、评估及预警平台建立关键技术的研究[D].云南大学 博士论文2016

[9] 董亮、闫小娟、黄文耿等"太阳射电爆发对不同波段无线电信号影响分析[M].全国第三十五届气象年会文集,2018

[10] 于超、李嘉巍、张效信等，风云二号C/D卫星与GOES卫星太阳X射线探测数据交叉比对[C].第八届全国优秀青年气象科技工作者学术研讨会论文汇编,2014

[11]韦飞，张效信、张斌全等，风云二号F星太阳×射线探测器在轨探测初步成果[].地球物理学报，2014  
第57卷，第11期，3812-3821

[13] Christophe Marqué,Karl-Ludwig Klein, Christian Monstein，solar radio emission as a disturbance of aeronautical radio navigation [J].J. Space Weather Space Clime. 2018,8, A42

[14] B.P.Dabrowski,and A.O.Benz Correlation between decametric radio emission and hard X-rays in solar flares [J]. A&A,2009(504):565-573,D01:10.1051/0004-6361/200811108/

[15] Haimin Wang,and Dale E.Gary. Correlation of Microwave and hard X-ray spectral parameters[J]. The Astrophysical Journal, 2000(545), December:1116-1123

[16] Dulk G.A. Radio emisson from the sun and stars[J]. Annual Rev. Astron. Astrophys.,1985,23:169-224

[17]黄光力、Victor Melnikov[俄]、季海生、宁宗军“耀斑环物理"[M].科学出版社,2015   
[18] Nita,G.M,Gary,DE.,Lanzeroti,LJ.,et.al,The peak flux distributionofsolarradiobursts.[J].Astrophys. J., 2002(570): 423-438,   
[19] L.J.Lanzerotti,D.E.Gary,G.M. Nita Noise in wireless systems from solar radio bursts[]. Advances in Space Research,2005(36): 2253-2257

# X-ray aura analysis of the solar radio burst interfering with navigation signal

# events on November 4, 2015

_iang Dong1, Xiaojuan Yan²,Wengeng Huang³, Pan ${ \mathsf { L i } } ^ { 4 }$ ,Chao $\mathsf { Y u } ^ { 2 }$ ,Guannan Gao1, Ercha A³, Faxin Shen15, Shaojie Guo1 1. Yunnan Astronomy Observatory，Chinese Academy of Sciences， Kunming， Yunnan 650216 2.National Satellite Meteorological Centre/National Space Weather Monitoring and Early Warning Centre，Beijing，100081 3. National Center for Space Science， Chinese Academy of Sciences，Beijing，100190 4.Beijing Institute of Tracking and Communication Technology，Beijing，100190 5. University of Chinese Academy of Sciences，Beijing，101408

Abstract: Solar radio burst event (SRB) is an optional factor for wireless communications especially satellites navigation communications. The peak Flux of the SRB event in 4th November reached 5800 SFU(Solar Flux Unit） in 1415MHz.During this event, the GPS receivers in European and the Air navigation systems were all suffered some stronge influences. In this paper, we analysed the relationship between X-ray flux variation and radio flux variation during this event. By comparing, the beginning time of X-ray flux upraising was 30 minutes earlier than radio flux. Furthermore,in this paper we discussed the background of phenomenon ,the soft and hot X-rays correspond to hot and non-hot electron radiation,which is the physical condition that produces radio bursts that can cause such space weather events. The soft-to-hard process of X-rays can offer an effective early alarming

method for this kind of space weather events.

key words: Solar radio burst; Navigation signal; Similar frequency interferences; X-ray; Aura analysis

# 基金项目：

国家自然科学基金,天文联合基金培育项目（U2031133）,重点项目（U1831201），重点专项项目（11941003），云南省应用基础研究计划面上项目（2019FB009），